---
order_index: null
title: 'Lecture 19: Computation of the Discrete Fourier Transform, Part 2'
template_type: Tabbed
uid: 3293b56b46c3f0890692f41151c66665
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-19-computation-of-the-discrete-fourier-transform-part-2
short_url: lecture-19-computation-of-the-discrete-fourier-transform-part-2
inline_embed_id: '65793054lecture19:computationofthediscretefouriertransform,part250157595'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Interpretation of FFT flow graph for
  in-place computation, bit-reversed data ordering, other decimation-in-time FFT
  algorithms by rearrangement of the flow graph, decimation-in-frequency FFT
  algorithm.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Computation of the Discrete Fourier Transform, Part 2 (<img alt="This
  resource may not render correctly in a screen reader."
  src="/images/inacessible.gif" /><a
  href="./resolveuid/dfb5664fbf195e8514a75f8758b06a4d">PDF</a>)</p>
transcript: >-
  <p><span m='90'>The</span> <span m='180'>following</span> <span
  m='630'>content</span> <span m='1200'>is</span> <span m='1320'>provided</span>
  <span m='1770'>under</span> <span m='2009'>a</span> <span
  m='2070'>Creative</span> <span m='2490'>Commons</span> <span
  m='2910'>license.</span> <span m='4030'>Your</span> <span
  m='4200'>support</span> <span m='4680'>will</span> <span m='4860'>help</span>
  <span m='5100'>MIT</span> <span m='5550'>OpenCourseWare</span> <span
  m='6330'>continue</span> <span m='6850'>to</span> <span m='6960'>offer</span>
  <span m='7380'>high</span> <span m='7590'>quality</span> <span
  m='8100'>educational</span> <span m='8730'>resources</span> <span
  m='9330'>for</span> <span m='9510'>free.</span> <span m='10720'>To</span>
  <span m='10740'>make</span> <span m='10920'>a</span> <span
  m='10980'>donation</span> <span m='11730'>or</span> <span
  m='11940'>view</span> <span m='12390'>additional</span> <span
  m='12810'>materials</span> <span m='13320'>from</span> <span
  m='13500'>hundreds</span> <span m='13920'>of</span> <span m='14040'>MIT</span>
  <span m='14460'>courses,</span> <span m='15550'>visit</span> <span
  m='15780'>MIT</span> <span m='16200'>OpenCourseWare</span> <span
  m='17280'>at</span> <span m='17430'>ocw.mit.edu.</span> </p><p><span
  m='48280'>ALAN OPPENHEIM:</span> <span m='48330'>In</span> <span
  m='48380'>the</span> <span m='48440'>last</span> <span
  m='48740'>lecture,</span> <span m='49400'>we</span> <span
  m='49520'>began</span> <span m='49940'>the</span> <span
  m='50090'>discussion</span> <span m='50900'>of</span> <span
  m='51200'>the</span> <span m='51410'>computation</span> <span
  m='52220'>of</span> <span m='52310'>the</span> <span m='52400'>discrete</span>
  <span m='52760'>Fourier</span> <span m='53180'>transform.</span> <span
  m='54470'>And</span> <span m='54680'>in</span> <span
  m='54770'>particular,</span> <span m='55460'>we</span> <span
  m='55640'>developed</span> <span m='56420'>a</span> <span
  m='56510'>flow</span> <span m='56780'>graph</span> <span m='57350'>for</span>
  <span m='57530'>one</span> <span m='57740'>algorithm.</span> <span
  m='59270'>The</span> <span m='59390'>algorithm</span> <span
  m='60110'>that</span> <span m='60230'>we</span> <span m='60350'>talked</span>
  <span m='60710'>about</span> <span m='60950'>last</span> <span
  m='61280'>time,</span> <span m='62010'>which</span> <span m='62270'>is</span>
  <span m='62420'>referred</span> <span m='62780'>to</span> <span
  m='63140'>as</span> <span m='63560'>the</span> <span
  m='63740'>decimation</span> <span m='64550'>in</span> <span
  m='64700'>time</span> <span m='65330'>form</span> <span m='65810'>of</span>
  <span m='65960'>the</span> <span m='66080'>fast</span> <span
  m='66380'>Fourier</span> <span m='66710'>transform</span> <span
  m='67340'>algorithm,</span> <span m='68570'>was</span> <span
  m='69230'>derived</span> <span m='70010'>by</span> <span
  m='71060'>decomposing</span> <span m='72740'>the</span> <span
  m='73070'>original</span> <span m='73520'>sequence</span> <span
  m='74420'>into</span> <span m='75560'>subsequences.</span> </p><p><span
  m='77100'>First,</span> <span m='77690'>two</span> <span
  m='77870'>subsequences</span> <span m='78860'>consisting</span> <span
  m='79640'>of</span> <span m='80390'>the</span> <span m='80510'>even</span>
  <span m='80810'>numbered</span> <span m='81470'>points</span> <span
  m='82430'>and</span> <span m='82610'>the</span> <span m='82730'>odd</span>
  <span m='82910'>numbered</span> <span m='83270'>points,</span> <span
  m='84950'>implementing</span> <span m='85430'>an</span> <span
  m='85910'>N-over-2-point</span> <span m='87350'>DFT</span> <span
  m='88220'>on</span> <span m='88400'>the</span> <span m='88520'>even</span>
  <span m='88790'>numbered</span> <span m='89120'>points</span> <span
  m='90080'>and</span> <span m='90570'>an</span> <span
  m='90640'>N-over-2-point</span> <span m='91820'>DFT</span> <span
  m='92270'>on</span> <span m='92420'>the</span> <span m='92540'>odd</span>
  <span m='92750'>numbered</span> <span m='93110'>points,</span> <span
  m='94190'>and</span> <span m='94340'>then</span> <span
  m='94700'>combining</span> <span m='95330'>those</span> <span
  m='95600'>results</span> <span m='96140'>in</span> <span m='96290'>an</span>
  <span m='96380'>appropriate</span> <span m='96950'>way</span> <span
  m='97730'>to</span> <span m='97880'>obtain</span> <span m='98510'>the</span>
  <span m='98780'>discrete</span> <span m='99200'>Fourier</span> <span
  m='99590'>transform</span> <span m='100280'>of</span> <span
  m='100370'>the</span> <span m='100520'>overall</span> <span
  m='100910'>sequence.</span> <span m='102350'>And</span> <span
  m='102920'>we</span> <span m='103070'>saw,</span> <span
  m='103340'>first</span> <span m='103700'>of</span> <span
  m='103820'>all,</span> <span m='104370'>that</span> <span
  m='104540'>there</span> <span m='104690'>was</span> <span m='105080'>a</span>
  <span m='105140'>computational</span> <span m='106040'>efficiency</span> <span
  m='107000'>that</span> <span m='107240'>resulted</span> <span
  m='107780'>from</span> <span m='107990'>doing</span> <span
  m='108320'>this.</span> <span m='109290'>And</span> <span
  m='109310'>furthermore,</span> <span m='110060'>we</span> <span
  m='110210'>recognized</span> <span m='111290'>that</span> <span
  m='112460'>we</span> <span m='112670'>could</span> <span
  m='113150'>continue</span> <span m='114040'>this</span> <span
  m='114230'>decomposition</span> <span m='115640'>and</span> <span
  m='115790'>thereby</span> <span m='116480'>achieve</span> <span
  m='117020'>an</span> <span m='117140'>even</span> <span
  m='117380'>greater</span> <span m='118400'>efficiency.</span> </p><p><span
  m='119790'>In</span> <span m='119810'>particular,</span> <span
  m='120680'>with</span> <span m='121190'>N</span> <span
  m='121790'>expressed</span> <span m='122660'>as</span> <span
  m='122840'>a</span> <span m='122900'>power</span> <span m='123320'>of</span>
  <span m='123440'>2,</span> <span m='124370'>we</span> <span
  m='124520'>could</span> <span m='124730'>continue</span> <span
  m='125300'>decomposing</span> <span m='126000'>the</span> <span
  m='126350'>N-over-2-point</span> <span m='127167'>DFTs</span> <span
  m='128360'>into</span> <span m='128560'>N-over-4-point</span> <span
  m='129530'>DFTs,</span> <span m='130729'>the</span> <span
  m='130834'>N-over-4-point</span> <span m='131440'>DFTs</span> <span
  m='132220'>into</span> <span m='132500'>N-over-8-point</span> <span
  m='133330'>DFTs,</span> <span m='133540'>et</span> <span
  m='133910'>cetera.</span> <span m='135650'>The</span> <span
  m='135860'>flow</span> <span m='136160'>graph</span> <span
  m='136760'>that</span> <span m='136940'>resulted</span> <span
  m='137840'>when</span> <span m='138020'>we</span> <span m='138170'>did</span>
  <span m='138410'>this</span> <span m='139520'>was</span> <span
  m='140330'>the</span> <span m='140750'>flow</span> <span
  m='141050'>graph</span> <span m='141950'>indicated</span> <span
  m='142580'>here,</span> <span m='143180'>which</span> <span
  m='143660'>is</span> <span m='144200'>the</span> <span m='144320'>one</span>
  <span m='144500'>that</span> <span m='144620'>we</span> <span
  m='144770'>derived</span> <span m='145520'>last</span> <span
  m='145850'>time.</span> <span m='146870'>It</span> <span
  m='146990'>consists</span> <span m='147530'>essentially</span> <span
  m='148370'>of</span> <span m='148910'>a</span> <span m='148970'>set</span>
  <span m='149330'>of</span> <span m='149510'>butterfly</span> <span
  m='150530'>computations--</span> <span m='152270'>what</span> <span
  m='152420'>we</span> <span m='152570'>refer</span> <span m='152900'>to</span>
  <span m='153230'>as</span> <span m='153620'>butterflies--</span> <span
  m='155450'>a</span> <span m='155540'>multiplication</span> <span
  m='156920'>on</span> <span m='157070'>the</span> <span
  m='157160'>bottom</span> <span m='157490'>branch</span> <span
  m='157910'>of</span> <span m='158000'>the</span> <span
  m='158090'>butterfly</span> <span m='158930'>at</span> <span
  m='159080'>the</span> <span m='159200'>input</span> <span m='159530'>to</span>
  <span m='159650'>the</span> <span m='159740'>butterfly,</span> <span
  m='160670'>and</span> <span m='160850'>then</span> <span m='161430'>an</span>
  <span m='161570'>addition</span> <span m='162200'>and</span> <span
  m='162380'>subtraction.</span> <span m='163610'>And</span> <span
  m='163730'>that</span> <span m='163940'>basically</span> <span
  m='164900'>is</span> <span m='165770'>the</span> <span m='166070'>type</span>
  <span m='166430'>of</span> <span m='166520'>computation</span> <span
  m='167570'>that</span> <span m='167720'>follows</span> <span
  m='168290'>throughout</span> <span m='168680'>the</span> <span
  m='168770'>flow</span> <span m='169040'>graph.</span> </p><p><span
  m='171260'>Now,</span> <span m='172010'>this</span> <span m='172250'>is</span>
  <span m='172370'>a</span> <span m='172430'>flow</span> <span
  m='172760'>graph</span> <span m='173750'>representing</span> <span
  m='174500'>the</span> <span m='174590'>computation</span> <span
  m='175340'>of</span> <span m='175430'>the</span> <span
  m='175520'>discrete</span> <span m='175910'>Fourier</span> <span
  m='176300'>transform.</span> <span m='177800'>And</span> <span
  m='178610'>what</span> <span m='178970'>is</span> <span
  m='179150'>important</span> <span m='179990'>about</span> <span
  m='180290'>the</span> <span m='180380'>flow</span> <span
  m='180680'>graph</span> <span m='181610'>are</span> <span
  m='182390'>the</span> <span m='182510'>nodes</span> <span
  m='183890'>and</span> <span m='184370'>the</span> <span
  m='184490'>connections</span> <span m='185060'>between</span> <span
  m='185450'>the</span> <span m='185540'>nodes</span> <span
  m='186110'>and</span> <span m='186260'>the</span> <span
  m='186350'>transmittances</span> <span m='187490'>on</span> <span
  m='187700'>the</span> <span m='187790'>branches</span> <span
  m='188960'>that</span> <span m='189500'>connect</span> <span
  m='189860'>the</span> <span m='189950'>nodes</span> <span
  m='190280'>together.</span> <span m='192080'>However,</span> <span
  m='193070'>the</span> <span m='193310'>flow</span> <span
  m='193580'>graph</span> <span m='194330'>in</span> <span m='194780'>the</span>
  <span m='194900'>form</span> <span m='195590'>that</span> <span
  m='195860'>is</span> <span m='196040'>depicted</span> <span
  m='196550'>here</span> <span m='198140'>suggests</span> <span
  m='198950'>a</span> <span m='198980'>strategy</span> <span
  m='199820'>for</span> <span m='200000'>organizing</span> <span
  m='200660'>the</span> <span m='200750'>computation</span> <span
  m='201860'>of</span> <span m='202520'>the</span> <span m='202610'>DFT.</span>
  <span m='204500'>In</span> <span m='204650'>particular,</span> <span
  m='205710'>what</span> <span m='205790'>we</span> <span
  m='205940'>recognize</span> <span m='207350'>is</span> <span
  m='207620'>that</span> <span m='208490'>the</span> <span
  m='208580'>flow</span> <span m='208860'>graph</span> <span
  m='209390'>in</span> <span m='209570'>this</span> <span m='209780'>form</span>
  <span m='210920'>tends,</span> <span m='211430'>in</span> <span
  m='211550'>a</span> <span m='211610'>natural</span> <span
  m='212150'>way,</span> <span m='213050'>to</span> <span
  m='213170'>suggest</span> <span m='215060'>organizing</span> <span
  m='215720'>the</span> <span m='215810'>computation</span> <span
  m='217490'>corresponding</span> <span m='218450'>to</span> <span
  m='218780'>a</span> <span m='218840'>computation</span> <span
  m='219950'>of</span> <span m='220400'>an</span> <span m='220520'>input</span>
  <span m='220910'>array--</span> <span m='221240'>a</span> <span
  m='221570'>computation</span> <span m='222230'>on</span> <span
  m='222410'>an</span> <span m='222500'>input</span> <span
  m='222830'>array--</span> <span m='224060'>computing</span> <span
  m='225560'>a</span> <span m='225650'>second</span> <span
  m='226130'>array</span> <span m='226730'>at</span> <span
  m='226910'>this</span> <span m='227090'>stage,</span> <span
  m='228500'>from</span> <span m='229040'>these</span> <span
  m='229340'>points,</span> <span m='230150'>computing</span> <span
  m='232520'>this</span> <span m='232760'>array,</span> <span
  m='233690'>and</span> <span m='233900'>from</span> <span
  m='234080'>these</span> <span m='234320'>points,</span> <span
  m='234840'>finally</span> <span m='235100'>computing</span> <span
  m='236090'>the</span> <span m='236690'>DFT</span> <span
  m='237260'>output</span> <span m='237680'>points.</span> </p><p><span
  m='239940'>If</span> <span m='240150'>we</span> <span m='240270'>do</span>
  <span m='240480'>that</span> <span m='241560'>and</span> <span
  m='242220'>we</span> <span m='242580'>in</span> <span m='242730'>fact</span>
  <span m='243420'>think</span> <span m='243900'>of</span> <span
  m='244560'>these</span> <span m='245190'>points</span> <span
  m='246420'>as</span> <span m='246570'>corresponding</span> <span
  m='247440'>to</span> <span m='247770'>sequential</span> <span
  m='248400'>memory</span> <span m='249060'>registers,</span> <span
  m='250530'>then</span> <span m='251220'>we</span> <span
  m='251400'>know,</span> <span m='251850'>first</span> <span
  m='252240'>of</span> <span m='252360'>all,</span> <span m='253200'>that</span>
  <span m='253710'>the</span> <span m='253920'>input</span> <span
  m='254670'>points</span> <span m='255840'>would</span> <span
  m='255990'>be</span> <span m='256140'>stored</span> <span
  m='256860'>sequentially,</span> <span m='258120'>not</span> <span
  m='258480'>in</span> <span m='259110'>their</span> <span
  m='259260'>normal</span> <span m='259680'>order,</span> <span
  m='260519'>but</span> <span m='260970'>in</span> <span m='261120'>fact,</span>
  <span m='261670'>in</span> <span m='262079'>some</span> <span
  m='262620'>altered</span> <span m='263100'>order.</span> <span
  m='263880'>And</span> <span m='264120'>as</span> <span
  m='264270'>you'll</span> <span m='264390'>see</span> <span
  m='264600'>in</span> <span m='264660'>a</span> <span m='264720'>few</span>
  <span m='264960'>minutes,</span> <span m='265380'>what</span> <span
  m='265560'>this</span> <span m='265770'>order</span> <span
  m='266190'>corresponds</span> <span m='267030'>to</span> <span
  m='267390'>and</span> <span m='267540'>will</span> <span m='267690'>be</span>
  <span m='267810'>referred</span> <span m='268170'>to</span> <span
  m='268680'>as</span> <span m='269520'>is</span> <span m='269980'>bit</span>
  <span m='270210'>reversed</span> <span m='270690'>order.</span> </p><p><span
  m='273290'>However,</span> <span m='273660'>an</span> <span
  m='273780'>additional</span> <span m='274230'>point</span> <span
  m='274620'>that</span> <span m='274740'>I'd</span> <span
  m='274860'>like</span> <span m='275040'>to</span> <span m='275160'>make</span>
  <span m='275400'>first</span> <span m='275730'>about</span> <span
  m='275970'>this</span> <span m='276150'>flow</span> <span
  m='276420'>graph,</span> <span m='276930'>and</span> <span
  m='277050'>that</span> <span m='277260'>is</span> <span m='277740'>that</span>
  <span m='278190'>it</span> <span m='278670'>corresponds--</span> <span
  m='280020'>when</span> <span m='280230'>thought</span> <span
  m='280560'>of</span> <span m='280950'>as</span> <span m='281460'>a</span>
  <span m='281520'>procedure</span> <span m='282030'>for</span> <span
  m='282210'>organizing</span> <span m='282870'>the</span> <span
  m='282960'>computation--</span> <span m='284340'>corresponds</span> <span
  m='285390'>to</span> <span m='285810'>an</span> <span
  m='285990'>in-place</span> <span m='286920'>computation</span> <span
  m='287910'>of</span> <span m='288060'>the</span> <span
  m='288150'>discrete</span> <span m='288540'>Fourier</span> <span
  m='288960'>transform.</span> <span m='290410'>Now,</span> <span
  m='290670'>what</span> <span m='290850'>I</span> <span m='290940'>mean</span>
  <span m='291150'>by</span> <span m='291330'>that</span> <span
  m='291690'>is</span> <span m='291840'>the</span> <span
  m='291960'>following.</span> </p><p><span m='293890'>Let's</span> <span
  m='293970'>suppose</span> <span m='294930'>that</span> <span
  m='295260'>we</span> <span m='295440'>think</span> <span m='295920'>of</span>
  <span m='296580'>this</span> <span m='296790'>set</span> <span
  m='297030'>of</span> <span m='297150'>points</span> <span m='297750'>as</span>
  <span m='297900'>corresponding</span> <span m='298770'>to</span> <span
  m='299040'>sequential</span> <span m='300090'>registers</span> <span
  m='300690'>in</span> <span m='300780'>memory</span> <span
  m='302370'>and</span> <span m='303030'>we'd</span> <span
  m='303180'>like</span> <span m='303420'>to</span> <span
  m='303540'>compute</span> <span m='303960'>from</span> <span
  m='304140'>this</span> <span m='304290'>set</span> <span m='304530'>of</span>
  <span m='304650'>points</span> <span m='305820'>this</span> <span
  m='306480'>second</span> <span m='306930'>array</span> <span
  m='307590'>that</span> <span m='307800'>is</span> <span m='308220'>the</span>
  <span m='308310'>set</span> <span m='308520'>of</span> <span
  m='308610'>points</span> <span m='309030'>here.</span> <span
  m='311010'>What</span> <span m='311160'>we</span> <span
  m='311310'>notice</span> <span m='312000'>is</span> <span
  m='312330'>that</span> <span m='312720'>because</span> <span
  m='313230'>of</span> <span m='313320'>the</span> <span
  m='313440'>butterfly</span> <span m='314400'>structure</span> <span
  m='315150'>of</span> <span m='315300'>this</span> <span
  m='315480'>computation,</span> <span m='318090'>it</span> <span
  m='318360'>is</span> <span m='318720'>these</span> <span m='319050'>two</span>
  <span m='319260'>points</span> <span m='320400'>that</span> <span
  m='320580'>are</span> <span m='320700'>used</span> <span m='321330'>to</span>
  <span m='321480'>compute</span> <span m='322260'>these</span> <span
  m='322530'>two</span> <span m='322740'>points</span> <span
  m='323280'>in</span> <span m='323400'>the</span> <span m='323460'>next</span>
  <span m='323800'>array.</span> <span m='324960'>These</span> <span
  m='325230'>points</span> <span m='325890'>are</span> <span
  m='326010'>used</span> <span m='326280'>to</span> <span
  m='326370'>compute</span> <span m='326760'>these</span> <span
  m='327060'>two</span> <span m='327270'>points</span> <span
  m='327780'>in</span> <span m='327900'>the</span> <span m='327990'>next</span>
  <span m='328320'>array,</span> <span m='328840'>et</span> <span
  m='329150'>cetera,</span> <span m='330210'>so</span> <span
  m='330390'>that</span> <span m='330600'>in</span> <span
  m='330750'>fact,</span> <span m='331450'>we</span> <span m='331500'>can</span>
  <span m='331680'>organize</span> <span m='332250'>the</span> <span
  m='332370'>computation</span> <span m='334290'>by</span> <span
  m='336630'>implementing</span> <span m='337200'>the</span> <span
  m='337290'>computation</span> <span m='338100'>required</span> <span
  m='338790'>on</span> <span m='339390'>these</span> <span m='339720'>two</span>
  <span m='339960'>input</span> <span m='340320'>points,</span> <span
  m='341580'>storing</span> <span m='342120'>the</span> <span
  m='342240'>results</span> <span m='343740'>in</span> <span m='344370'>a</span>
  <span m='344550'>corresponding</span> <span m='345360'>set</span> <span
  m='345720'>of</span> <span m='345810'>memory</span> <span
  m='346170'>locations,</span> <span m='347310'>which</span> <span
  m='347550'>in</span> <span m='347640'>fact</span> <span
  m='348510'>could</span> <span m='348810'>be</span> <span m='349500'>the</span>
  <span m='349710'>original</span> <span m='350160'>memory</span> <span
  m='350490'>locations</span> <span m='351150'>from</span> <span
  m='351330'>which</span> <span m='351750'>we</span> <span
  m='352020'>took</span> <span m='352290'>these</span> <span
  m='352530'>data</span> <span m='352790'>points.</span> </p><p><span
  m='353850'>The</span> <span m='353940'>reason</span> <span
  m='354240'>for</span> <span m='354420'>that</span> <span m='354780'>is</span>
  <span m='354990'>that</span> <span m='355590'>once</span> <span
  m='356130'>we've</span> <span m='356360'>used</span> <span
  m='356670'>these</span> <span m='356880'>two</span> <span
  m='357060'>data</span> <span m='357370'>points,</span> <span
  m='358320'>we</span> <span m='358440'>don't</span> <span
  m='358680'>need</span> <span m='358920'>them</span> <span
  m='359100'>any</span> <span m='359280'>longer.</span> <span
  m='360850'>And</span> <span m='361020'>so</span> <span m='361500'>the</span>
  <span m='361620'>result</span> <span m='362130'>of</span> <span
  m='362250'>this</span> <span m='362460'>butterfly</span> <span
  m='363560'>we</span> <span m='363690'>could</span> <span m='363930'>in</span>
  <span m='364050'>fact</span> <span m='364350'>store</span> <span
  m='365010'>back</span> <span m='365850'>in</span> <span m='365970'>the</span>
  <span m='366060'>original</span> <span m='366480'>memory</span> <span
  m='366810'>locations.</span> <span m='368010'>And</span> <span
  m='369450'>a</span> <span m='369510'>few</span> <span
  m='369750'>minutes</span> <span m='370080'>of</span> <span
  m='370200'>reflection</span> <span m='370980'>on</span> <span
  m='371220'>this</span> <span m='371370'>flow</span> <span
  m='371610'>graph</span> <span m='371940'>in</span> <span
  m='372060'>general</span> <span m='373020'>would</span> <span
  m='373140'>indicate</span> <span m='373830'>that</span> <span
  m='374190'>this</span> <span m='374400'>is</span> <span m='374520'>true</span>
  <span m='374760'>throughout</span> <span m='375180'>the</span> <span
  m='375300'>computation.</span> </p><p><span m='377220'>It's</span> <span
  m='377400'>clearly</span> <span m='377760'>true</span> <span
  m='378000'>in</span> <span m='378090'>going</span> <span
  m='378450'>from</span> <span m='378720'>the</span> <span
  m='378810'>first</span> <span m='379110'>stage</span> <span
  m='379920'>to</span> <span m='380010'>the</span> <span
  m='380130'>second</span> <span m='380490'>stage.</span> <span
  m='381990'>In</span> <span m='382800'>proceeding</span> <span
  m='383340'>from</span> <span m='383580'>this</span> <span
  m='383730'>stage</span> <span m='384720'>to</span> <span m='384840'>the</span>
  <span m='384930'>next</span> <span m='385170'>stage,</span> <span
  m='385740'>we</span> <span m='385890'>see</span> <span
  m='386130'>again,</span> <span m='387150'>for</span> <span
  m='387330'>example</span> <span m='388050'>in</span> <span
  m='388170'>computing</span> <span m='388710'>these</span> <span
  m='389010'>two</span> <span m='389610'>points,</span> <span
  m='390900'>the</span> <span m='391050'>only</span> <span
  m='391500'>input</span> <span m='391860'>points</span> <span
  m='392220'>that</span> <span m='392310'>we</span> <span m='392400'>use</span>
  <span m='392790'>are</span> <span m='393000'>these</span> <span
  m='393360'>two.</span> <span m='394380'>So</span> <span
  m='394710'>again</span> <span m='395310'>we</span> <span
  m='395490'>could</span> <span m='395610'>think</span> <span
  m='395970'>of</span> <span m='396120'>storing</span> <span
  m='396630'>the</span> <span m='396750'>result</span> <span
  m='397290'>of</span> <span m='397500'>this</span> <span
  m='397710'>computation</span> <span m='399210'>for</span> <span
  m='399330'>this</span> <span m='399890'>butterfly,</span> <span
  m='400470'>for</span> <span m='400620'>example,</span> <span
  m='401610'>back</span> <span m='402090'>in</span> <span m='402630'>the</span>
  <span m='402750'>original</span> <span m='403140'>memory</span> <span
  m='403470'>locations.</span> </p><p><span m='405190'>So</span> <span
  m='406230'>if</span> <span m='406440'>we</span> <span m='406620'>think</span>
  <span m='407010'>of</span> <span m='407670'>nodes</span> <span
  m='409050'>on</span> <span m='409260'>the</span> <span m='409350'>same</span>
  <span m='409680'>horizontal</span> <span m='410310'>line</span> <span
  m='411840'>as</span> <span m='412050'>corresponding</span> <span
  m='413280'>to</span> <span m='414240'>identical</span> <span
  m='415290'>memory</span> <span m='415680'>registers,</span> <span
  m='416850'>then</span> <span m='417030'>we</span> <span m='417150'>see</span>
  <span m='417690'>that</span> <span m='417930'>with</span> <span
  m='418200'>the</span> <span m='419130'>computation</span> <span
  m='420090'>organized</span> <span m='421080'>in</span> <span
  m='421200'>the</span> <span m='421320'>way</span> <span m='421740'>that</span>
  <span m='421920'>this</span> <span m='422100'>flow</span> <span
  m='422340'>graph</span> <span m='422640'>suggests,</span> <span
  m='424080'>that</span> <span m='424290'>in</span> <span m='424470'>fact</span>
  <span m='425040'>the</span> <span m='425130'>computation</span> <span
  m='426060'>can</span> <span m='426270'>be</span> <span m='426390'>done</span>
  <span m='426720'>in</span> <span m='426930'>place.</span> <span
  m='428190'>And</span> <span m='428970'>we'll</span> <span
  m='429150'>see</span> <span m='429540'>that</span> <span
  m='429780'>with</span> <span m='430020'>some</span> <span
  m='431010'>other</span> <span m='431550'>alternative</span> <span
  m='432180'>forms</span> <span m='432900'>of</span> <span m='433350'>the</span>
  <span m='433560'>FFT</span> <span m='434070'>algorithm,</span> <span
  m='434660'>some</span> <span m='434820'>alternative</span> <span
  m='435300'>forms</span> <span m='435660'>of</span> <span
  m='435750'>this</span> <span m='435930'>flow</span> <span
  m='436200'>graph,</span> <span m='437310'>there</span> <span
  m='438210'>perhaps</span> <span m='438660'>are</span> <span
  m='438780'>other</span> <span m='439050'>advantages,</span> <span
  m='440130'>but</span> <span m='440700'>for</span> <span m='441030'>some</span>
  <span m='441300'>of</span> <span m='441390'>the</span> <span
  m='441510'>other</span> <span m='441690'>flow</span> <span
  m='441960'>graphs,</span> <span m='442380'>the</span> <span
  m='442500'>computation</span> <span m='443340'>can</span> <span
  m='443490'>no</span> <span m='443640'>longer</span> <span m='444060'>be</span>
  <span m='444180'>done</span> <span m='444390'>in-place.</span> </p><p><span
  m='446190'>So</span> <span m='446400'>first</span> <span m='446700'>of</span>
  <span m='446820'>all,</span> <span m='446970'>this</span> <span
  m='447150'>flow</span> <span m='447420'>graph</span> <span
  m='447960'>represents</span> <span m='449400'>an</span> <span
  m='450270'>in-place</span> <span m='451160'>algorithm.</span> <span
  m='453300'>Second</span> <span m='453720'>of</span> <span
  m='453840'>all,</span> <span m='454500'>the</span> <span
  m='454920'>input</span> <span m='455430'>points</span> <span
  m='455970'>are</span> <span m='456420'>in</span> <span m='456900'>some</span>
  <span m='457380'>altered</span> <span m='457830'>order,</span> <span
  m='458560'>although</span> <span m='459150'>the</span> <span
  m='459360'>DFT</span> <span m='460020'>output</span> <span
  m='460470'>points</span> <span m='461430'>come</span> <span
  m='461640'>out</span> <span m='462000'>in</span> <span m='462750'>what</span>
  <span m='463110'>is</span> <span m='463350'>normal</span> <span
  m='463770'>order.</span> <span m='464040'>That</span> <span
  m='464250'>is,</span> <span m='464340'>sequential</span> <span
  m='464970'>order</span> <span m='465270'>if</span> <span m='465420'>we</span>
  <span m='465510'>think</span> <span m='465780'>of</span> <span
  m='465870'>these</span> <span m='466290'>as</span> <span
  m='466440'>sequential</span> <span m='466980'>registers.</span> <span
  m='468180'>Well,</span> <span m='468660'>let's</span> <span
  m='469170'>examine</span> <span m='469920'>in</span> <span m='470010'>a</span>
  <span m='470040'>little</span> <span m='470220'>more</span> <span
  m='470430'>detail</span> <span m='471210'>what</span> <span
  m='471450'>the</span> <span m='471600'>order</span> <span m='471990'>is</span>
  <span m='472560'>that</span> <span m='472950'>is</span> <span
  m='473160'>being</span> <span m='473430'>generated</span> <span
  m='474090'>here.</span> </p><p><span m='476760'>If</span> <span
  m='477180'>we</span> <span m='477450'>simply</span> <span
  m='478320'>look</span> <span m='478770'>at</span> <span m='481550'>the</span>
  <span m='483230'>memory</span> <span m='484280'>registers</span> <span
  m='485990'>and</span> <span m='486290'>the</span> <span
  m='486410'>corresponding</span> <span m='487160'>data</span> <span
  m='487490'>index</span> <span m='489490'>from</span> <span
  m='489760'>the</span> <span m='489820'>previous</span> <span
  m='490300'>flow</span> <span m='490540'>graph,</span> <span
  m='491200'>in</span> <span m='491380'>storage</span> <span
  m='491800'>registers</span> <span m='492310'>0</span> <span
  m='493150'>we're</span> <span m='493360'>storing</span> <span
  m='493960'>x</span> <span m='494230'>of</span> <span m='494320'>0,</span>
  <span m='495350'>in</span> <span m='495460'>storage</span> <span
  m='495880'>register</span> <span m='496360'>1</span> <span
  m='496720'>we're</span> <span m='496870'>storing</span> <span
  m='497370'>x</span> <span m='497710'>of 4,</span> <span
  m='498310'>storage</span> <span m='498760'>register</span> <span
  m='499190'>2,</span> <span m='499540'>x of</span> <span m='500000'>2,</span>
  <span m='500950'>and</span> <span m='501150'>et cetera.</span> <span
  m='501730'>These</span> <span m='502030'>are</span> <span
  m='502180'>the</span> <span m='502450'>storage</span> <span
  m='502930'>register</span> <span m='503380'>locations.</span> <span
  m='504640'>These</span> <span m='505030'>are</span> <span
  m='505240'>the</span> <span m='505360'>data</span> <span
  m='505810'>indices.</span> </p><p><span m='507960'>If</span> <span
  m='508380'>we</span> <span m='508560'>write</span> <span m='509280'>the</span>
  <span m='509370'>storage</span> <span m='509820'>register</span> <span
  m='510270'>locations</span> <span m='511320'>in</span> <span
  m='511800'>binary</span> <span m='513120'>and</span> <span
  m='513299'>we</span> <span m='513419'>write</span> <span m='513929'>the</span>
  <span m='514049'>data</span> <span m='514409'>index</span> <span
  m='515130'>in</span> <span m='515280'>binary,</span> <span
  m='516380'>what</span> <span m='516570'>we</span> <span m='516750'>see,</span>
  <span m='517169'>interestingly</span> <span m='517799'>enough,</span> <span
  m='518669'>is</span> <span m='518880'>that</span> <span m='519059'>the</span>
  <span m='519179'>data</span> <span m='519630'>index</span> <span
  m='521100'>is</span> <span m='522090'>the</span> <span m='522600'>bit</span>
  <span m='522929'>reversed</span> <span m='523380'>counterpart</span> <span
  m='524430'>of</span> <span m='525180'>the</span> <span
  m='525750'>storage</span> <span m='526290'>register</span> <span
  m='526800'>index.</span> <span m='527730'>So</span> <span
  m='528120'>here,</span> <span m='528390'>for</span> <span
  m='528600'>example,</span> <span m='529210'>we</span> <span
  m='529290'>have</span> <span m='529870'>001,</span> <span
  m='530970'>storage</span> <span m='531420'>register</span> <span
  m='531870'>1.</span> <span m='532950'>Here</span> <span m='533160'>we</span>
  <span m='533340'>have</span> <span m='533880'>100,</span> <span
  m='535200'>which</span> <span m='535500'>is</span> <span
  m='535770'>data</span> <span m='536100'>index</span> <span
  m='536610'>4.</span> <span m='537720'>And</span> <span m='538470'>this</span>
  <span m='538650'>continues</span> <span m='539460'>on</span> <span
  m='539760'>throughout.</span> <span m='540690'>110</span> <span
  m='541870'>is</span> <span m='542040'>storage</span> <span
  m='542490'>register</span> <span m='542920'>6,</span> <span
  m='543860'>bit</span> <span m='544200'>reversed</span> <span
  m='544860'>is</span> <span m='545040'>011,</span> <span
  m='546240'>which</span> <span m='546450'>is</span> <span
  m='546600'>data</span> <span m='546900'>index</span> <span
  m='547410'>3.</span> </p><p><span m='549100'>Now,</span> <span
  m='549570'>it's</span> <span m='549750'>not</span> <span
  m='549990'>accidental</span> <span m='550950'>that</span> <span
  m='552060'>this</span> <span m='552630'>developed</span> <span
  m='553500'>in</span> <span m='555030'>such</span> <span m='555360'>a</span>
  <span m='555420'>way</span> <span m='555690'>that</span> <span
  m='555840'>the</span> <span m='555960'>data</span> <span m='556470'>is</span>
  <span m='556950'>in</span> <span m='557070'>fact</span> <span
  m='557370'>stored</span> <span m='557910'>in</span> <span m='558060'>a</span>
  <span m='558120'>bit</span> <span m='558330'>reversed</span> <span
  m='558780'>order.</span> <span m='559920'>The</span> <span
  m='560010'>reason</span> <span m='560430'>for</span> <span
  m='560610'>that</span> <span m='561270'>basically</span> <span
  m='562290'>is</span> <span m='562740'>because</span> <span
  m='563250'>of</span> <span m='563370'>the</span> <span m='563490'>way</span>
  <span m='564030'>in</span> <span m='564180'>which</span> <span
  m='564600'>we</span> <span m='564900'>originally</span> <span
  m='565440'>sorted</span> <span m='566670'>the</span> <span
  m='567780'>sequence</span> <span m='568710'>into</span> <span
  m='569280'>the</span> <span m='569460'>even</span> <span
  m='569760'>numbered</span> <span m='570060'>points</span> <span
  m='570420'>and</span> <span m='570510'>the</span> <span m='570630'>odd</span>
  <span m='570810'>numbered</span> <span m='571170'>points,</span> <span
  m='571910'>then</span> <span m='572160'>the</span> <span
  m='572280'>even</span> <span m='572580'>numbered</span> <span
  m='572910'>of</span> <span m='573030'>the</span> <span m='573120'>even</span>
  <span m='573390'>numbered</span> <span m='573690'>points,</span> <span
  m='574350'>and</span> <span m='574560'>the</span> <span m='574860'>odd</span>
  <span m='575090'>numbered of the</span> <span m='575490'>even</span> <span
  m='575790'>numbered</span> <span m='576060'>points,</span> <span
  m='576420'>et</span> <span m='576810'>cetera.</span> </p><p><span
  m='578340'>In</span> <span m='578460'>particular,</span> <span
  m='579520'>suppose</span> <span m='580380'>that</span> <span
  m='581670'>we</span> <span m='582360'>considered</span> <span
  m='584390'>a</span> <span m='584480'>tree</span> <span m='585710'>to</span>
  <span m='586040'>carry</span> <span m='586520'>out</span> <span
  m='587030'>the</span> <span m='587150'>sorting</span> <span
  m='588320'>that</span> <span m='588740'>we</span> <span
  m='589010'>implemented</span> <span m='589790'>in</span> <span
  m='590000'>breaking</span> <span m='590510'>the</span> <span
  m='590630'>original</span> <span m='591020'>sequence</span> <span
  m='591860'>up</span> <span m='592190'>into</span> <span
  m='592430'>subsequences.</span> <span m='594520'>Well,</span> <span
  m='595030'>we</span> <span m='595180'>started</span> <span
  m='595570'>with</span> <span m='595720'>the</span> <span
  m='595810'>original</span> <span m='596200'>sequence</span> <span
  m='598430'>and</span> <span m='599050'>we</span> <span
  m='599770'>divided</span> <span m='600280'>that</span> <span
  m='600640'>into</span> <span m='601000'>two</span> <span
  m='601210'>subsequences,</span> <span m='602530'>one</span> <span
  m='603040'>corresponding</span> <span m='603790'>to</span> <span
  m='603910'>the</span> <span m='604060'>even</span> <span
  m='604360'>numbered</span> <span m='604660'>points,</span> <span
  m='605320'>the</span> <span m='605410'>second</span> <span
  m='605770'>corresponding</span> <span m='606490'>to</span> <span
  m='606610'>the</span> <span m='606730'>odd</span> <span
  m='606940'>numbered</span> <span m='607270'>points.</span> </p><p><span
  m='608960'>If</span> <span m='609370'>you</span> <span m='609550'>look</span>
  <span m='609910'>at</span> <span m='610450'>the</span> <span
  m='610780'>binary</span> <span m='611470'>representation</span> <span
  m='612730'>of</span> <span m='612910'>the</span> <span m='613000'>data</span>
  <span m='613360'>index,</span> <span m='614770'>you</span> <span
  m='614920'>can</span> <span m='615070'>identify</span> <span
  m='615790'>the</span> <span m='615940'>even</span> <span
  m='616240'>numbered</span> <span m='616600'>points</span> <span
  m='617440'>by</span> <span m='618070'>the</span> <span
  m='618190'>points</span> <span m='618580'>for</span> <span
  m='618760'>which</span> <span m='619390'>the</span> <span
  m='619510'>least</span> <span m='619780'>significant</span> <span
  m='620590'>binary</span> <span m='621820'>bit</span> <span
  m='622750'>is</span> <span m='622940'>a</span> <span m='623100'>0</span> <span
  m='624070'>and</span> <span m='624190'>the</span> <span m='624340'>odd</span>
  <span m='624520'>numbered</span> <span m='624850'>points</span> <span
  m='625210'>for</span> <span m='625390'>which</span> <span
  m='625600'>the</span> <span m='625690'>least</span> <span
  m='625900'>significant</span> <span m='626620'>binary</span> <span
  m='627070'>bit</span> <span m='627670'>is</span> <span m='627820'>a</span>
  <span m='627910'>1.</span> <span m='629450'>So</span> <span
  m='629560'>we</span> <span m='629680'>divided</span> <span
  m='630940'>the</span> <span m='631120'>original</span> <span
  m='631510'>sequence</span> <span m='632290'>into</span> <span
  m='632590'>two</span> <span m='632830'>subsequences.</span> <span
  m='633760'>The</span> <span m='633880'>top</span> <span m='634270'>half</span>
  <span m='635050'>all</span> <span m='635320'>had</span> <span
  m='635560'>0</span> <span m='636220'>as</span> <span m='636400'>the</span>
  <span m='636490'>least</span> <span m='636700'>significant</span> <span
  m='637270'>bit.</span> <span m='637990'>The</span> <span
  m='638080'>bottom</span> <span m='638440'>half</span> <span
  m='638860'>all</span> <span m='639130'>had</span> <span m='639340'>1</span>
  <span m='639960'>as</span> <span m='640150'>the</span> <span
  m='640210'>least</span> <span m='640420'>significant</span> <span
  m='640990'>bit.</span> </p><p><span m='642270'>Well,</span> <span
  m='642790'>then</span> <span m='643300'>for</span> <span m='643720'>the</span>
  <span m='643870'>even</span> <span m='644200'>numbered</span> <span
  m='644530'>points</span> <span m='645070'>we</span> <span
  m='645220'>wanted</span> <span m='645460'>to</span> <span
  m='645580'>divide</span> <span m='646000'>those</span> <span
  m='646450'>into</span> <span m='646870'>the</span> <span
  m='647050'>even</span> <span m='647380'>numbered</span> <span
  m='647710'>of</span> <span m='647800'>the</span> <span m='647920'>even</span>
  <span m='648190'>numbered</span> <span m='648670'>and</span> <span
  m='648820'>the</span> <span m='648970'>odd</span> <span
  m='649210'>numbered</span> <span m='649560'>of</span> <span
  m='649660'>the</span> <span m='649740'>even</span> <span
  m='650050'>numbered.</span> <span m='650980'>How</span> <span
  m='651170'>would</span> <span m='651280'>we</span> <span m='651400'>do</span>
  <span m='651610'>that?</span> <span m='652220'>Well,</span> <span
  m='652510'>we</span> <span m='652690'>would</span> <span m='652810'>do</span>
  <span m='652990'>that</span> <span m='653290'>by</span> <span
  m='653590'>examining</span> <span m='654730'>the</span> <span
  m='654940'>next</span> <span m='655690'>least</span> <span
  m='655900'>significant</span> <span m='656530'>bit.</span> </p><p><span
  m='657730'>If</span> <span m='657880'>that's a</span> <span
  m='658180'>0,</span> <span m='659320'>then</span> <span m='659620'>we</span>
  <span m='659770'>would</span> <span m='659890'>identify</span> <span
  m='660910'>the</span> <span m='661930'>data</span> <span m='662410'>as</span>
  <span m='662800'>being</span> <span m='663250'>an</span> <span
  m='663370'>even</span> <span m='663700'>numbered</span> <span m='664030'>of
  the</span> <span m='664210'>even</span> <span m='664540'>numbered</span> <span
  m='664900'>points.</span> <span m='665380'>If</span> <span
  m='665500'>it's</span> <span m='665620'>a</span> <span m='665710'>1,</span>
  <span m='666100'>it's</span> <span m='666730'>an</span> <span
  m='666970'>odd</span> <span m='667240'>numbered</span> <span
  m='667750'>of</span> <span m='667930'>the</span> <span m='668020'>even</span>
  <span m='668290'>numbered</span> <span m='668620'>points.</span> <span
  m='669700'>So</span> <span m='670270'>this</span> <span m='670570'>data</span>
  <span m='671110'>was</span> <span m='671290'>sorted</span> <span
  m='671950'>as</span> <span m='672700'>we've</span> <span
  m='672910'>indicated</span> <span m='673480'>here.</span> </p><p><span
  m='674380'>And</span> <span m='674980'>then,</span> <span m='675190'>of</span>
  <span m='675310'>course,</span> <span m='675550'>we</span> <span
  m='675670'>continue</span> <span m='676180'>on</span> <span
  m='676720'>looking</span> <span m='677110'>at</span> <span
  m='677200'>the</span> <span m='677320'>bits</span> <span
  m='678130'>from</span> <span m='678700'>the</span> <span
  m='678820'>right</span> <span m='679660'>to</span> <span m='679780'>the</span>
  <span m='679900'>left.</span> <span m='680950'>So</span> <span
  m='681430'>sorting,</span> <span m='682330'>then</span> <span
  m='682720'>we</span> <span m='682870'>could</span> <span
  m='683020'>sort</span> <span m='683590'>in</span> <span m='683710'>the</span>
  <span m='683860'>order</span> <span m='684220'>that</span> <span
  m='684370'>resulted</span> <span m='685420'>by</span> <span
  m='685960'>constructing</span> <span m='686650'>a</span> <span
  m='686710'>tree,</span> <span m='687310'>as</span> <span
  m='687460'>I've</span> <span m='687610'>indicated</span> <span
  m='688180'>here,</span> <span m='689090'>and</span> <span
  m='689110'>examining</span> <span m='689740'>the</span> <span
  m='689830'>bits</span> <span m='690940'>from</span> <span
  m='691510'>the</span> <span m='691630'>right</span> <span m='692570'>to</span>
  <span m='692680'>the</span> <span m='692800'>left.</span> </p><p><span
  m='694940'>Suppose</span> <span m='695480'>that</span> <span
  m='695600'>we</span> <span m='695720'>wanted</span> <span
  m='696230'>instead</span> <span m='697280'>to</span> <span
  m='697400'>sort</span> <span m='697760'>the</span> <span
  m='697850'>data,</span> <span m='699000'>not</span> <span m='699680'>as</span>
  <span m='699920'>I've</span> <span m='700070'>indicated</span> <span
  m='700640'>here,</span> <span m='701180'>but</span> <span m='701570'>in</span>
  <span m='701840'>normal</span> <span m='702290'>order.</span> <span
  m='703500'>In</span> <span m='703600'>other</span> <span
  m='703670'>words,</span> <span m='704340'>we</span> <span
  m='704390'>have</span> <span m='704570'>a</span> <span
  m='704670'>bucket</span> <span m='704990'>of</span> <span
  m='705110'>data.</span> <span m='705980'>We</span> <span
  m='706100'>want</span> <span m='706610'>to</span> <span m='707120'>sort</span>
  <span m='707510'>the</span> <span m='707630'>data</span> <span
  m='707960'>so</span> <span m='708170'>that</span> <span m='708620'>the</span>
  <span m='708710'>data</span> <span m='709040'>index</span> <span
  m='710540'>comes</span> <span m='710840'>out</span> <span m='711110'>in</span>
  <span m='711230'>normal</span> <span m='711620'>order.</span> <span
  m='712490'>How</span> <span m='712720'>would</span> <span m='712820'>we</span>
  <span m='712940'>do</span> <span m='713150'>that</span> <span
  m='713600'>with</span> <span m='713840'>a</span> <span
  m='713870'>similar</span> <span m='714320'>type</span> <span
  m='714620'>of</span> <span m='714710'>tree</span> <span
  m='714950'>structure?</span> </p><p><span m='716180'>Well,</span> <span
  m='717560'>to</span> <span m='717680'>decide</span> <span
  m='718460'>whether</span> <span m='719750'>the</span> <span
  m='719870'>data</span> <span m='720290'>index</span> <span
  m='721160'>is</span> <span m='721370'>in</span> <span m='721490'>the</span>
  <span m='721610'>top</span> <span m='721940'>half</span> <span
  m='722240'>or</span> <span m='722300'>the</span> <span
  m='722420'>bottom</span> <span m='722780'>half</span> <span
  m='723890'>we</span> <span m='724010'>would</span> <span
  m='724160'>look</span> <span m='724370'>at</span> <span m='724460'>the</span>
  <span m='724550'>most</span> <span m='724820'>significant</span> <span
  m='725420'>bit.</span> <span m='726380'>If</span> <span m='726470'>the</span>
  <span m='726590'>most</span> <span m='726830'>significant</span> <span
  m='727340'>bit</span> <span m='727550'>is</span> <span m='727650'>a</span>
  <span m='727760'>0,</span> <span m='728880'>then</span> <span
  m='728930'>the</span> <span m='729050'>data</span> <span m='729410'>is</span>
  <span m='729650'>in</span> <span m='729770'>the</span> <span
  m='729860'>top</span> <span m='730190'>half</span> <span m='730730'>of</span>
  <span m='731180'>the</span> <span m='731300'>entire</span> <span
  m='731690'>set</span> <span m='731930'>of</span> <span m='732050'>data.</span>
  <span m='732410'>And</span> <span m='732590'>if</span> <span
  m='732710'>the</span> <span m='732800'>most</span> <span
  m='733040'>significant</span> <span m='733550'>bit</span> <span
  m='733790'>is</span> <span m='733880'>a</span> <span m='733970'>1,</span>
  <span m='734690'>the</span> <span m='734810'>data</span> <span
  m='735140'>is</span> <span m='735350'>in</span> <span m='735470'>the</span>
  <span m='735560'>bottom</span> <span m='735890'>half.</span> </p><p><span
  m='737390'>Next,</span> <span m='737750'>we</span> <span
  m='737870'>would</span> <span m='738020'>proceed</span> <span
  m='738650'>to</span> <span m='738800'>the</span> <span
  m='738920'>second</span> <span m='739310'>most</span> <span
  m='739550'>significant</span> <span m='740120'>bit.</span> <span
  m='740810'>If</span> <span m='741320'>the</span> <span
  m='741440'>second</span> <span m='741740'>most</span> <span
  m='741950'>significant</span> <span m='742460'>bit</span> <span m='742670'>is
  a</span> <span m='742920'>0,</span> <span m='744020'>then</span> <span
  m='744650'>we</span> <span m='744830'>fall</span> <span
  m='745460'>either</span> <span m='745700'>into</span> <span
  m='745910'>the</span> <span m='746030'>top</span> <span m='746360'>half</span>
  <span m='746660'>of</span> <span m='746750'>the</span> <span
  m='746870'>top</span> <span m='747200'>half</span> <span m='747530'>or</span>
  <span m='747860'>the</span> <span m='747980'>top</span> <span
  m='748280'>half</span> <span m='748520'>of</span> <span m='748580'>the</span>
  <span m='748700'>bottom</span> <span m='749030'>half.</span> <span
  m='749810'>And</span> <span m='750080'>we</span> <span
  m='750200'>continue</span> <span m='750680'>on</span> <span
  m='750860'>like</span> <span m='751130'>that</span> <span
  m='751820'>going</span> <span m='752120'>through</span> <span
  m='752300'>a</span> <span m='752390'>tree</span> <span
  m='752840'>exactly</span> <span m='753470'>identical</span> <span
  m='754040'>to</span> <span m='754190'>this,</span> <span m='755060'>but</span>
  <span m='755420'>examining</span> <span m='756080'>the</span> <span
  m='756170'>bits</span> <span m='756890'>for</span> <span
  m='757040'>sorting</span> <span m='757520'>in</span> <span
  m='757650'>normal</span> <span m='758000'>order</span> <span
  m='758810'>from</span> <span m='759590'>the</span> <span
  m='759830'>most</span> <span m='760160'>significant</span> <span
  m='760730'>bit</span> <span m='761180'>down</span> <span m='761420'>to</span>
  <span m='761540'>the</span> <span m='761630'>least</span> <span
  m='761840'>significant</span> <span m='762380'>bit.</span> </p><p><span
  m='763470'>So</span> <span m='764270'>it</span> <span m='764720'>is</span>
  <span m='764930'>basically</span> <span m='766190'>that</span> <span
  m='766460'>in</span> <span m='766610'>sorting</span> <span
  m='767060'>the</span> <span m='767150'>data</span> <span m='767690'>as</span>
  <span m='767900'>we</span> <span m='768050'>sorted</span> <span
  m='768500'>it</span> <span m='768860'>to</span> <span
  m='768980'>develop</span> <span m='770060'>the</span> <span
  m='770510'>flow</span> <span m='770810'>graph</span> <span
  m='771440'>that</span> <span m='771860'>we</span> <span
  m='772750'>developed,</span> <span m='774080'>we</span> <span
  m='774350'>examined</span> <span m='774950'>the</span> <span
  m='775040'>bits</span> <span m='775670'>in</span> <span
  m='775820'>exactly</span> <span m='776390'>the</span> <span
  m='776480'>reverse</span> <span m='776930'>order</span> <span
  m='777800'>that</span> <span m='777950'>we</span> <span
  m='778130'>would</span> <span m='778280'>examine</span> <span
  m='778760'>the</span> <span m='778850'>bits</span> <span m='779210'>if</span>
  <span m='779390'>we</span> <span m='779510'>wanted</span> <span
  m='779780'>to</span> <span m='779930'>sort</span> <span m='780260'>the</span>
  <span m='780350'>data</span> <span m='780680'>normally.</span> <span
  m='781640'>And</span> <span m='781760'>consequently</span> <span
  m='782630'>what</span> <span m='782810'>results</span> <span
  m='783500'>is</span> <span m='784160'>data</span> <span
  m='784840'>that's</span> <span m='785050'>sorted</span> <span
  m='785750'>in</span> <span m='786170'>bit</span> <span
  m='786560'>reversed</span> <span m='787160'>order.</span> </p><p><span
  m='791500'>Incidentally,</span> <span m='792370'>speaking</span> <span
  m='792970'>of</span> <span m='793390'>things</span> <span
  m='794260'>being</span> <span m='795370'>bit</span> <span
  m='795550'>reversed,</span> <span m='797440'>the</span> <span
  m='800460'>view</span> <span m='800690'>graph</span> <span
  m='801140'>as</span> <span m='801770'>I</span> <span m='801920'>first</span>
  <span m='802220'>got</span> <span m='802470'>it</span> <span
  m='802580'>back</span> <span m='802910'>from</span> <span
  m='803090'>drafting</span> <span m='803600'>I</span> <span
  m='803690'>thought</span> <span m='803960'>you</span> <span
  m='804110'>might</span> <span m='805610'>enjoy</span> <span
  m='805970'>looking</span> <span m='806330'>at.</span> <span
  m='806720'>And</span> <span m='807440'>if</span> <span m='807620'>you</span>
  <span m='807710'>find</span> <span m='808670'>your</span> <span
  m='808820'>mind</span> <span m='809090'>wandering</span> <span
  m='809570'>during</span> <span m='809780'>the</span> <span
  m='809870'>rest</span> <span m='810140'>of</span> <span m='810200'>the</span>
  <span m='810320'>lecture,</span> <span m='810680'>you</span> <span
  m='810800'>might</span> <span m='810980'>try</span> <span m='811190'>to</span>
  <span m='811280'>figure</span> <span m='811610'>out</span> <span
  m='811730'>exactly</span> <span m='812180'>what</span> <span
  m='812330'>happened</span> <span m='812930'>with</span> <span
  m='813050'>this</span> <span m='813260'>view</span> <span
  m='813440'>graph.</span> </p><p><span m='815030'>The</span> <span
  m='815120'>first</span> <span m='815450'>inclination</span> <span
  m='816170'>is</span> <span m='816350'>that</span> <span m='816530'>I</span>
  <span m='816620'>simply</span> <span m='817040'>have</span> <span
  m='817210'>it</span> <span m='817610'>turned</span> <span
  m='817910'>around,</span> <span m='818330'>so</span> <span
  m='818510'>we</span> <span m='818630'>can</span> <span m='818780'>try</span>
  <span m='819080'>that.</span> <span m='822020'>Well,</span> <span
  m='822530'>that</span> <span m='822710'>doesn't</span> <span
  m='823010'>quite</span> <span m='823280'>do</span> <span m='823460'>it.</span>
  <span m='823580'>So</span> <span m='823730'>maybe</span> <span
  m='824000'>we</span> <span m='824120'>should</span> <span
  m='824270'>turn</span> <span m='824570'>it</span> <span
  m='824660'>over.</span> <span m='825950'>And</span> <span
  m='826250'>that</span> <span m='826670'>doesn't</span> <span
  m='826970'>quite</span> <span m='827270'>do</span> <span m='827480'>it.</span>
  <span m='827760'>And</span> <span m='827840'>in</span> <span
  m='827900'>fact,</span> <span m='830160'>I</span> <span
  m='830180'>haven't</span> <span m='830480'>yet</span> <span
  m='830630'>been</span> <span m='830780'>able</span> <span m='831020'>to</span>
  <span m='831170'>figure</span> <span m='831530'>out</span> <span
  m='831860'>a</span> <span m='831950'>way</span> <span m='832490'>of</span>
  <span m='833210'>sorting</span> <span m='833660'>this</span> <span
  m='833810'>particular</span> <span m='834320'>view</span> <span
  m='834520'>graph</span> <span m='834860'>in</span> <span m='834980'>any</span>
  <span m='835160'>normal</span> <span m='835550'>order</span> <span
  m='836090'>and</span> <span m='837200'>I'd</span> <span m='837290'>be</span>
  <span m='837410'>curious</span> <span m='837860'>as</span> <span
  m='837980'>to</span> <span m='838100'>whether</span> <span
  m='838280'>you</span> <span m='838430'>can</span> <span
  m='838550'>figure</span> <span m='838880'>out</span> <span m='839000'>a</span>
  <span m='839060'>way</span> <span m='839210'>to</span> <span
  m='839300'>straighten</span> <span m='839660'>it</span> <span
  m='839780'>out.</span> </p><p><span m='840710'>Well,</span> <span
  m='841250'>in</span> <span m='841370'>any</span> <span m='841550'>case,</span>
  <span m='843030'>what</span> <span m='843440'>we</span> <span
  m='843620'>have</span> <span m='843920'>then</span> <span m='844460'>is</span>
  <span m='845660'>a</span> <span m='845960'>sorting</span> <span
  m='846560'>of</span> <span m='847160'>the</span> <span
  m='847280'>original</span> <span m='847730'>data--</span> <span
  m='849290'>returning</span> <span m='849740'>now</span> <span
  m='850220'>to</span> <span m='850370'>the</span> <span m='850460'>flow</span>
  <span m='850700'>graph</span> <span m='851210'>that</span> <span
  m='851330'>we</span> <span m='851450'>saw</span> <span
  m='851690'>previously--</span> <span m='852640'>a</span> <span
  m='852720'>sorting</span> <span m='853250'>of</span> <span
  m='853460'>the</span> <span m='853550'>original</span> <span
  m='853970'>data</span> <span m='854930'>in</span> <span m='855050'>bit</span>
  <span m='855240'>reversed</span> <span m='855800'>order</span> <span
  m='856790'>and</span> <span m='857450'>the</span> <span
  m='857630'>output</span> <span m='858460'>resulting</span> <span
  m='859220'>in</span> <span m='859640'>normal</span> <span
  m='860030'>order.</span> <span m='862250'>Well,</span> <span
  m='862640'>of</span> <span m='862790'>course</span> <span
  m='863300'>this</span> <span m='863600'>isn't</span> <span
  m='863870'>the</span> <span m='863990'>only</span> <span m='864260'>way</span>
  <span m='864650'>to</span> <span m='864800'>organize</span> <span
  m='865760'>the</span> <span m='865850'>computation</span> <span
  m='866780'>of</span> <span m='866930'>the</span> <span
  m='866990'>discrete</span> <span m='867380'>Fourier</span> <span
  m='867800'>transform.</span> </p><p><span m='869250'>And</span> <span
  m='869270'>in</span> <span m='869390'>fact,</span> <span m='870110'>an</span>
  <span m='870230'>important</span> <span m='871190'>aspect</span> <span
  m='872000'>of</span> <span m='872600'>the</span> <span m='872690'>flow</span>
  <span m='873020'>graph</span> <span m='874400'>is</span> <span
  m='874910'>as</span> <span m='875240'>I</span> <span
  m='875330'>stressed</span> <span m='875690'>previously</span> <span
  m='876650'>that</span> <span m='876800'>what</span> <span
  m='877010'>counts</span> <span m='877400'>about</span> <span
  m='877670'>the</span> <span m='877790'>flow</span> <span
  m='878090'>graph</span> <span m='878990'>are</span> <span
  m='879590'>the</span> <span m='879710'>nodes</span> <span
  m='880250'>and</span> <span m='880430'>the</span> <span m='880520'>way</span>
  <span m='880730'>they're</span> <span m='880880'>connected</span> <span
  m='881930'>and</span> <span m='882050'>not</span> <span m='882350'>the</span>
  <span m='882470'>way</span> <span m='883100'>the</span> <span
  m='883220'>flow</span> <span m='883490'>graph</span> <span
  m='883940'>is</span> <span m='884120'>laid</span> <span m='884420'>out</span>
  <span m='884750'>in</span> <span m='884900'>a</span> <span
  m='884960'>sheet.</span> <span m='885980'>When</span> <span
  m='886100'>it's</span> <span m='886220'>laid</span> <span
  m='886460'>out</span> <span m='886700'>in</span> <span m='886790'>a</span>
  <span m='886880'>sheet,</span> <span m='888170'>we</span> <span
  m='888290'>were</span> <span m='888410'>able</span> <span m='888830'>to</span>
  <span m='889580'>apply</span> <span m='889970'>some</span> <span
  m='890150'>additional</span> <span m='890570'>interpretation</span> <span
  m='891920'>having</span> <span m='892220'>to</span> <span m='892370'>do</span>
  <span m='892820'>with</span> <span m='893900'>a</span> <span
  m='894020'>way</span> <span m='894530'>of</span> <span
  m='895700'>organizing</span> <span m='896360'>the</span> <span
  m='896450'>computation</span> <span m='897260'>from</span> <span
  m='897410'>stage</span> <span m='897830'>to</span> <span
  m='897950'>stage.</span> <span m='899450'>But</span> <span
  m='899750'>it's</span> <span m='899960'>important</span> <span
  m='900440'>to</span> <span m='900590'>recognize</span> <span
  m='902030'>that</span> <span m='902270'>if</span> <span m='903050'>you</span>
  <span m='903290'>take</span> <span m='903620'>this</span> <span
  m='903830'>flow</span> <span m='904100'>graph,</span> <span
  m='905180'>roll</span> <span m='905510'>it</span> <span m='905600'>up</span>
  <span m='905780'>in</span> <span m='905870'>a</span> <span
  m='905960'>ball,</span> <span m='907670'>as</span> <span
  m='907850'>long</span> <span m='908300'>as</span> <span m='908750'>the</span>
  <span m='908870'>right</span> <span m='909140'>points</span> <span
  m='909560'>are</span> <span m='909650'>connected</span> <span
  m='910100'>to</span> <span m='910220'>the</span> <span m='910340'>right</span>
  <span m='910610'>points,</span> <span m='911660'>then</span> <span
  m='911900'>it</span> <span m='912080'>still</span> <span
  m='912440'>represents</span> <span m='913610'>a</span> <span
  m='913670'>computation</span> <span m='914690'>of</span> <span
  m='914840'>the</span> <span m='914960'>discrete</span> <span
  m='915320'>Fourier</span> <span m='915710'>transform.</span> </p><p><span
  m='916890'>So</span> <span m='916970'>in</span> <span
  m='917060'>particular,</span> <span m='917940'>we</span> <span
  m='918350'>are</span> <span m='918620'>free</span> <span m='918950'>to</span>
  <span m='919130'>rearrange</span> <span m='919760'>this</span> <span
  m='919940'>flow</span> <span m='920240'>graph</span> <span
  m='921320'>in</span> <span m='921470'>any</span> <span m='921740'>way</span>
  <span m='921920'>that</span> <span m='922040'>we</span> <span
  m='922190'>would</span> <span m='922340'>like</span> <span
  m='922610'>to</span> <span m='923390'>as</span> <span m='923570'>long</span>
  <span m='923990'>as</span> <span m='924560'>we</span> <span
  m='924710'>don't</span> <span m='925010'>change</span> <span
  m='925550'>the</span> <span m='925670'>connections</span> <span
  m='926420'>between</span> <span m='926810'>the</span> <span
  m='926920'>notes.</span> <span m='928740'>Well,</span> <span
  m='929310'>one</span> <span m='929700'>possible</span> <span
  m='930270'>thought</span> <span m='930720'>is</span> <span
  m='930990'>to</span> <span m='931230'>rearrange</span> <span
  m='931800'>the</span> <span m='931920'>flow</span> <span
  m='932190'>graph</span> <span m='933120'>so</span> <span
  m='933390'>that</span> <span m='933870'>we</span> <span
  m='934140'>avoid</span> <span m='934530'>this</span> <span
  m='934740'>problem</span> <span m='935460'>of</span> <span
  m='935700'>bit</span> <span m='935910'>reversal</span> <span
  m='936570'>on</span> <span m='936720'>the</span> <span
  m='936840'>input.</span> <span m='937860'>We</span> <span
  m='938010'>can</span> <span m='938190'>think</span> <span m='938730'>of</span>
  <span m='940860'>rearranging</span> <span m='941610'>these</span> <span
  m='941790'>lines</span> <span m='942540'>so</span> <span
  m='942780'>that</span> <span m='943110'>the</span> <span
  m='943260'>input</span> <span m='944700'>is</span> <span
  m='945330'>changed</span> <span m='946080'>to</span> <span
  m='946440'>an</span> <span m='946590'>input</span> <span m='947040'>in</span>
  <span m='947220'>normal</span> <span m='947640'>order.</span> <span
  m='949360'>And</span> <span m='949530'>one</span> <span m='949770'>way</span>
  <span m='949980'>of</span> <span m='950100'>doing</span> <span
  m='950400'>that,</span> <span m='950710'>in</span> <span
  m='950760'>fact,</span> <span m='951660'>is</span> <span m='951900'>to</span>
  <span m='952050'>simply</span> <span m='952650'>take</span> <span
  m='953400'>all</span> <span m='953670'>of</span> <span m='953760'>the</span>
  <span m='953850'>horizontal</span> <span m='954510'>lines</span> <span
  m='955920'>and</span> <span m='956670'>rearrange</span> <span
  m='957390'>them</span> <span m='957750'>so</span> <span m='958080'>that</span>
  <span m='959040'>the</span> <span m='959850'>data</span> <span
  m='960540'>is</span> <span m='960960'>sorted</span> <span
  m='961440'>correctly.</span> </p><p><span m='962180'>So</span> <span
  m='962910'>we</span> <span m='963060'>would</span> <span
  m='963210'>leave</span> <span m='963510'>this</span> <span
  m='963720'>line</span> <span m='964050'>where</span> <span
  m='964290'>it</span> <span m='964410'>is,</span> <span m='964950'>we</span>
  <span m='965070'>would</span> <span m='965190'>take</span> <span
  m='965460'>this</span> <span m='965700'>line</span> <span
  m='966150'>and</span> <span m='966270'>move</span> <span m='966480'>it</span>
  <span m='966570'>up</span> <span m='966720'>to</span> <span
  m='966840'>here,</span> <span m='967710'>this</span> <span
  m='967950'>line</span> <span m='968730'>would</span> <span
  m='968940'>then</span> <span m='969150'>stay</span> <span
  m='969450'>where</span> <span m='969690'>it</span> <span m='969810'>is,</span>
  <span m='970110'>this</span> <span m='970320'>line</span> <span
  m='970620'>would</span> <span m='970740'>move</span> <span
  m='971010'>up,</span> <span m='971610'>and</span> <span m='972120'>they</span>
  <span m='972300'>would</span> <span m='972510'>continue</span> <span
  m='972960'>to</span> <span m='973080'>be</span> <span
  m='973230'>rearranged.</span> <span m='974430'>The</span> <span
  m='974610'>input</span> <span m='975150'>would</span> <span
  m='975360'>be</span> <span m='975900'>then</span> <span m='976140'>in</span>
  <span m='976350'>normal</span> <span m='976740'>order,</span> <span
  m='978610'>the</span> <span m='978660'>output,</span> <span
  m='979200'>of</span> <span m='979380'>course,</span> <span
  m='980070'>would</span> <span m='980520'>be</span> <span
  m='980730'>disturbed,</span> <span m='981840'>and</span> <span
  m='982620'>we</span> <span m='982830'>could</span> <span
  m='983400'>anticipate</span> <span m='984030'>exactly</span> <span
  m='984540'>how</span> <span m='984720'>it's</span> <span
  m='984840'>going</span> <span m='984960'>to</span> <span m='985020'>be</span>
  <span m='985140'>disturbed,</span> <span m='985620'>in</span> <span
  m='985740'>fact.</span> <span m='986520'>The</span> <span
  m='986700'>output</span> <span m='987300'>then</span> <span
  m='989370'>will</span> <span m='989640'>come</span> <span
  m='989850'>out</span> <span m='990150'>in</span> <span m='990330'>bit</span>
  <span m='990510'>reversed</span> <span m='990960'>order.</span> </p><p><span
  m='992320'>That</span> <span m='992570'>flow</span> <span
  m='992870'>graph</span> <span m='993620'>is</span> <span
  m='996970'>then</span> <span m='997330'>as</span> <span m='997630'>I've</span>
  <span m='997780'>indicated</span> <span m='998380'>here.</span> <span
  m='1000760'>And</span> <span m='1001850'>this</span> <span
  m='1002340'>then</span> <span m='1002580'>corresponds</span> <span
  m='1003420'>to</span> <span m='1003600'>a</span> <span
  m='1003660'>rearrangement</span> <span m='1004740'>of</span> <span
  m='1005010'>the</span> <span m='1005100'>previous</span> <span
  m='1005610'>flow</span> <span m='1005850'>graph,</span> <span
  m='1006780'>where</span> <span m='1006960'>we</span> <span
  m='1007110'>have</span> <span m='1007290'>rearranged</span> <span
  m='1008160'>the</span> <span m='1008490'>computation</span> <span
  m='1009900'>so</span> <span m='1010080'>that</span> <span
  m='1010260'>the</span> <span m='1010440'>input</span> <span
  m='1011040'>is</span> <span m='1011220'>now</span> <span m='1011760'>in</span>
  <span m='1011910'>normal</span> <span m='1012330'>order.</span> <span
  m='1014300'>The</span> <span m='1014320'>way</span> <span
  m='1014560'>in</span> <span m='1014680'>which</span> <span
  m='1014890'>we</span> <span m='1015070'>rearranged</span> <span
  m='1015730'>it,</span> <span m='1016060'>the</span> <span
  m='1016240'>output</span> <span m='1016760'>then</span> <span
  m='1018520'>comes</span> <span m='1018790'>out</span> <span
  m='1019090'>in</span> <span m='1019480'>bit</span> <span
  m='1019810'>reversed</span> <span m='1020260'>order.</span> </p><p><span
  m='1021400'>Incidentally,</span> <span m='1022090'>on</span> <span
  m='1022540'>most</span> <span m='1022870'>of</span> <span
  m='1022990'>the</span> <span m='1023200'>following</span> <span
  m='1023620'>view</span> <span m='1023830'>graphs,</span> <span
  m='1024910'>I</span> <span m='1026050'>have</span> <span
  m='1026260'>indicated</span> <span m='1027280'>a</span> <span
  m='1027670'>reference</span> <span m='1028480'>to</span> <span
  m='1028780'>the</span> <span m='1028900'>figure</span> <span
  m='1029380'>in</span> <span m='1029500'>the</span> <span
  m='1029589'>text,</span> <span m='1030319'>which</span> <span
  m='1030430'>this</span> <span m='1030579'>view</span> <span
  m='1030760'>graph</span> <span m='1031660'>corresponds</span> <span
  m='1032380'>to,</span> <span m='1032619'>because</span> <span
  m='1033670'>in</span> <span m='1033790'>fact,</span> <span
  m='1034190'>many</span> <span m='1034359'>of</span> <span
  m='1034480'>these</span> <span m='1034869'>flow</span> <span
  m='1035140'>graphs</span> <span m='1035530'>will</span> <span
  m='1035619'>be</span> <span m='1035740'>going</span> <span
  m='1035980'>through</span> <span m='1036130'>quite</span> <span
  m='1036339'>a</span> <span m='1036400'>number</span> <span m='1036880'>of
  flow</span> <span m='1036970'>graphs.</span> <span m='1038170'>Many</span>
  <span m='1038440'>of</span> <span m='1038589'>them</span> <span
  m='1039069'>look</span> <span m='1039430'>very</span> <span
  m='1039730'>similar,</span> <span m='1041140'>so</span> <span
  m='1041589'>I</span> <span m='1041680'>thought</span> <span
  m='1041950'>perhaps</span> <span m='1042369'>a</span> <span
  m='1042430'>reference</span> <span m='1042849'>to</span> <span
  m='1042940'>the</span> <span m='1043030'>figure</span> <span
  m='1043420'>in</span> <span m='1043510'>the</span> <span
  m='1043599'>text</span> <span m='1044020'>will</span> <span
  m='1044349'>help</span> <span m='1044619'>you</span> <span
  m='1045310'>keep</span> <span m='1045579'>them</span> <span
  m='1045730'>organized.</span> </p><p><span m='1048230'>So</span> <span
  m='1048440'>now</span> <span m='1048950'>we</span> <span
  m='1049160'>have</span> <span m='1050180'>a</span> <span
  m='1052240'>modification</span> <span m='1053320'>of</span> <span
  m='1053500'>the</span> <span m='1053590'>decimation</span> <span
  m='1054280'>in</span> <span m='1054370'>time</span> <span
  m='1054880'>form</span> <span m='1055250'>of</span> <span
  m='1055330'>the</span> <span m='1055450'>FFT</span> <span
  m='1056020'>algorithm,</span> <span m='1057990'>which</span> <span
  m='1059330'>is</span> <span m='1059900'>such</span> <span
  m='1060440'>that</span> <span m='1060740'>if we</span> <span
  m='1061150'>now</span> <span m='1061560'>think</span> <span
  m='1061970'>of</span> <span m='1062450'>this</span> <span
  m='1062840'>as</span> <span m='1063080'>the</span> <span
  m='1063200'>procedure</span> <span m='1063740'>for</span> <span
  m='1063920'>organizing</span> <span m='1064580'>the</span> <span
  m='1064670'>computation,</span> <span m='1065990'>the</span> <span
  m='1066170'>input</span> <span m='1066770'>is</span> <span
  m='1066980'>now</span> <span m='1067460'>in</span> <span
  m='1067640'>normal</span> <span m='1068030'>order,</span> <span
  m='1069360'>the</span> <span m='1069440'>output</span> <span
  m='1070130'>is</span> <span m='1070310'>in</span> <span m='1070430'>bit</span>
  <span m='1070640'>reversed</span> <span m='1071120'>order.</span> <span
  m='1072560'>Have</span> <span m='1072800'>we</span> <span
  m='1072980'>destroyed</span> <span m='1074270'>the</span> <span
  m='1074510'>fact</span> <span m='1075140'>that</span> <span
  m='1075320'>the</span> <span m='1075440'>original</span> <span
  m='1075830'>computation</span> <span m='1076760'>was</span> <span
  m='1076970'>an</span> <span m='1077030'>in-place</span> <span
  m='1077480'>computation?</span> <span m='1078830'>Well,</span> <span
  m='1079130'>in</span> <span m='1079220'>fact,</span> <span
  m='1079550'>we</span> <span m='1079700'>haven't,</span> <span
  m='1080540'>because</span> <span m='1081290'>if</span> <span
  m='1081470'>we</span> <span m='1081590'>look</span> <span
  m='1082040'>at</span> <span m='1082250'>this</span> <span
  m='1083270'>now</span> <span m='1083780'>the</span> <span
  m='1083930'>way</span> <span m='1084140'>that</span> <span
  m='1084260'>it's</span> <span m='1084410'>organized,</span> <span
  m='1085520'>again,</span> <span m='1086150'>thinking</span> <span
  m='1086570'>of</span> <span m='1086660'>this</span> <span
  m='1087260'>as</span> <span m='1087470'>sequential</span> <span
  m='1088490'>memory</span> <span m='1088880'>registers,</span> <span
  m='1090590'>then,</span> <span m='1091040'>again,</span> <span
  m='1092690'>if</span> <span m='1093140'>we,</span> <span
  m='1093380'>for</span> <span m='1093590'>example,</span> <span
  m='1094190'>select</span> <span m='1094670'>this</span> <span
  m='1094880'>butterfly,</span> <span m='1096200'>the</span> <span
  m='1096290'>computation</span> <span m='1097400'>of</span> <span
  m='1097790'>these</span> <span m='1098090'>two</span> <span
  m='1098330'>points</span> <span m='1099680'>requires</span> <span
  m='1100460'>only</span> <span m='1101030'>these</span> <span
  m='1101360'>two</span> <span m='1101870'>input</span> <span
  m='1102350'>points.</span> <span m='1103970'>So</span> <span
  m='1104390'>once</span> <span m='1104690'>we</span> <span
  m='1104830'>have</span> <span m='1104960'>used</span> <span
  m='1105260'>these</span> <span m='1105500'>two</span> <span
  m='1105710'>points,</span> <span m='1106220'>we</span> <span
  m='1106400'>can</span> <span m='1106550'>store</span> <span
  m='1106940'>them</span> <span m='1107120'>back</span> <span
  m='1108080'>in</span> <span m='1108200'>the</span> <span
  m='1108320'>original</span> <span m='1108740'>memory</span> <span
  m='1109070'>locations.</span> </p><p><span m='1110390'>What</span> <span
  m='1110990'>makes</span> <span m='1112160'>the</span> <span
  m='1112310'>flow</span> <span m='1112640'>graph</span> <span
  m='1113300'>correspond</span> <span m='1114020'>to</span> <span
  m='1114200'>an</span> <span m='1114290'>in-place</span> <span
  m='1114830'>computation</span> <span m='1116390'>is</span> <span
  m='1116570'>the</span> <span m='1116660'>fact</span> <span
  m='1117230'>that</span> <span m='1117410'>the</span> <span
  m='1117590'>output</span> <span m='1118100'>nodes</span> <span
  m='1118550'>of</span> <span m='1118700'>the</span> <span
  m='1118790'>butterfly</span> <span m='1120170'>are</span> <span
  m='1121010'>horizontally</span> <span m='1121970'>adjacent</span> <span
  m='1123050'>to</span> <span m='1123710'>the</span> <span
  m='1123890'>input</span> <span m='1124280'>nodes</span> <span
  m='1124580'>of</span> <span m='1124670'>the</span> <span
  m='1124760'>butterfly.</span> <span m='1125720'>If</span> <span
  m='1125900'>that</span> <span m='1126110'>property</span> <span
  m='1126560'>of</span> <span m='1126660'>the</span> <span
  m='1126740'>flow</span> <span m='1126980'>graph</span> <span
  m='1127460'>is</span> <span m='1127640'>destroyed,</span> <span
  m='1128780'>then</span> <span m='1129440'>the</span> <span
  m='1129530'>flow</span> <span m='1129800'>graph</span> <span
  m='1130310'>will</span> <span m='1130670'>no</span> <span
  m='1130880'>longer</span> <span m='1132230'>correspond</span> <span
  m='1133040'>to</span> <span m='1133220'>an</span> <span
  m='1133310'>in-place</span> <span m='1133790'>computation</span> <span
  m='1134750'>if</span> <span m='1135350'>we</span> <span
  m='1135500'>think</span> <span m='1135920'>of</span> <span
  m='1137060'>all</span> <span m='1137330'>nodes</span> <span
  m='1137810'>on</span> <span m='1137960'>the</span> <span
  m='1138050'>same</span> <span m='1138350'>horizontal</span> <span
  m='1138920'>line</span> <span m='1139400'>as</span> <span
  m='1140060'>corresponding</span> <span m='1140930'>to</span> <span
  m='1142790'>identical</span> <span m='1143300'>memory</span> <span
  m='1143660'>registers,</span> <span m='1144320'>or</span> <span
  m='1144470'>equivalently,</span> <span m='1145670'>that</span> <span
  m='1146390'>vertical</span> <span m='1146870'>nodes</span> <span
  m='1147470'>correspond</span> <span m='1148100'>to</span> <span
  m='1148250'>sequential</span> <span m='1149300'>memory</span> <span
  m='1149570'>registers.</span> </p><p><span m='1151700'>Well,</span> <span
  m='1152180'>there</span> <span m='1152570'>are</span> <span
  m='1152780'>a</span> <span m='1152810'>variety</span> <span
  m='1153350'>of</span> <span m='1153470'>other</span> <span
  m='1153650'>ways</span> <span m='1153980'>in</span> <span
  m='1154070'>which</span> <span m='1154280'>we</span> <span
  m='1154430'>can</span> <span m='1154610'>rearrange</span> <span
  m='1155120'>this</span> <span m='1155300'>flow</span> <span
  m='1155570'>graph.</span> <span m='1156860'>We</span> <span
  m='1157430'>can,</span> <span m='1157740'>of</span> <span
  m='1157790'>course,</span> <span m='1158550'>modify</span> <span
  m='1158960'>the</span> <span m='1159080'>flow</span> <span
  m='1159350'>graph</span> <span m='1159740'>so</span> <span
  m='1159950'>that</span> <span m='1160940'>we</span> <span
  m='1162410'>have</span> <span m='1163550'>not</span> <span
  m='1163790'>only</span> <span m='1164840'>normal</span> <span
  m='1165230'>order</span> <span m='1165830'>at</span> <span
  m='1165950'>the</span> <span m='1166100'>input,</span> <span
  m='1167010'>but</span> <span m='1167210'>so</span> <span
  m='1167390'>that</span> <span m='1167690'>we</span> <span
  m='1167900'>also</span> <span m='1168320'>have</span> <span
  m='1169010'>normal</span> <span m='1169430'>order</span> <span
  m='1169790'>at</span> <span m='1169910'>the</span> <span
  m='1170060'>output.</span> <span m='1171000'>And</span> <span
  m='1171100'>we</span> <span m='1171110'>can</span> <span m='1171230'>do</span>
  <span m='1171350'>that</span> <span m='1171560'>simply</span> <span
  m='1172340'>by</span> <span m='1172760'>demanding</span> <span
  m='1173390'>it.</span> <span m='1173600'>In</span> <span
  m='1173750'>other</span> <span m='1173960'>words,</span> <span
  m='1174750'>by</span> <span m='1174830'>rearranging</span> <span
  m='1175550'>these</span> <span m='1175820'>nodes,</span> <span
  m='1176750'>keeping</span> <span m='1177080'>these</span> <span
  m='1177320'>nodes</span> <span m='1177620'>in</span> <span
  m='1177710'>normal</span> <span m='1178070'>order,</span> <span
  m='1178790'>rearranging</span> <span m='1179420'>these</span> <span
  m='1179690'>nodes</span> <span m='1180570'>so</span> <span
  m='1180710'>that</span> <span m='1181130'>they</span> <span
  m='1181340'>also</span> <span m='1182120'>correspond</span> <span
  m='1183200'>to</span> <span m='1183320'>normal</span> <span
  m='1183710'>order.</span> <span m='1184610'>And</span> <span
  m='1185000'>the</span> <span m='1185090'>flow</span> <span
  m='1185360'>graph</span> <span m='1186110'>that</span> <span
  m='1186320'>results</span> <span m='1187040'>in</span> <span
  m='1187160'>that</span> <span m='1187370'>case</span> <span
  m='1189080'>is</span> <span m='1190010'>the</span> <span
  m='1190130'>one</span> <span m='1190640'>that</span> <span
  m='1191000'>I've</span> <span m='1191360'>indicated</span> <span
  m='1191960'>here.</span> </p><p><span m='1194780'>So</span> <span
  m='1195380'>this</span> <span m='1195620'>is</span> <span
  m='1195770'>now</span> <span m='1196070'>the</span> <span
  m='1196190'>decimation</span> <span m='1196940'>in</span> <span
  m='1197030'>time</span> <span m='1197420'>form</span> <span
  m='1197720'>of</span> <span m='1197810'>the</span> <span
  m='1197960'>algorithm</span> <span m='1199160'>with</span> <span
  m='1199400'>the</span> <span m='1199550'>input</span> <span
  m='1200360'>sorted</span> <span m='1201020'>in</span> <span
  m='1201170'>normal</span> <span m='1201560'>order</span> <span
  m='1202160'>and</span> <span m='1202790'>the</span> <span
  m='1202970'>output</span> <span m='1203540'>also</span> <span
  m='1204200'>sorted</span> <span m='1204830'>in</span> <span
  m='1204980'>normal</span> <span m='1205310'>order.</span> <span
  m='1206840'>The</span> <span m='1206940'>computation</span> <span
  m='1207640'>still</span> <span m='1208300'>is</span> <span
  m='1209290'>represented</span> <span m='1209920'>by</span> <span
  m='1210100'>butterflies,</span> <span m='1211300'>but</span> <span
  m='1211480'>the</span> <span m='1211600'>butterflies</span> <span
  m='1212380'>are</span> <span m='1212500'>distorted.</span> <span
  m='1213340'>In</span> <span m='1213520'>other</span> <span
  m='1213730'>words,</span> <span m='1214400'>each</span> <span
  m='1214540'>of</span> <span m='1214630'>the</span> <span
  m='1214750'>butterflies</span> <span m='1216460'>no</span> <span
  m='1216640'>longer</span> <span m='1218020'>corresponds</span> <span
  m='1219010'>to</span> <span m='1220090'>the</span> <span
  m='1221140'>computation</span> <span m='1221950'>of</span> <span
  m='1222130'>horizontally</span> <span m='1223060'>adjacent</span> <span
  m='1223660'>nodes</span> <span m='1224320'>in</span> <span
  m='1224440'>the</span> <span m='1224530'>flow</span> <span
  m='1224770'>graph.</span> </p><p><span m='1226980'>So</span> <span
  m='1227150'>in</span> <span m='1227270'>fact,</span> <span
  m='1228170'>this</span> <span m='1228380'>computation</span> <span
  m='1230540'>is</span> <span m='1231080'>no</span> <span
  m='1231320'>longer</span> <span m='1231960'>an</span> <span
  m='1232140'>in-place</span> <span m='1232700'>computation.</span> <span
  m='1234620'>Well,</span> <span m='1234980'>is</span> <span
  m='1235190'>it</span> <span m='1235310'>an</span> <span
  m='1235400'>in-place</span> <span m='1235820'>computation</span> <span
  m='1236570'>from</span> <span m='1236750'>this</span> <span
  m='1236930'>array</span> <span m='1237290'>to</span> <span
  m='1237440'>this</span> <span m='1237680'>one?</span> <span
  m='1238340'>As</span> <span m='1238520'>it</span> <span
  m='1238610'>happens,</span> <span m='1239060'>it</span> <span
  m='1239150'>is</span> <span m='1239600'>in</span> <span m='1239720'>the</span>
  <span m='1239810'>computation</span> <span m='1240770'>of</span> <span
  m='1240950'>the</span> <span m='1241070'>first</span> <span
  m='1241430'>array,</span> <span m='1242330'>the</span> <span
  m='1242420'>reason</span> <span m='1242810'>being</span> <span
  m='1243410'>that</span> <span m='1244820'>in</span> <span
  m='1245060'>each</span> <span m='1245330'>of</span> <span
  m='1245420'>the</span> <span m='1245540'>butterflies,</span> <span
  m='1246350'>again,</span> <span m='1247350'>the</span> <span
  m='1247400'>output</span> <span m='1247790'>nodes</span> <span
  m='1248270'>are</span> <span m='1248420'>horizontally</span> <span
  m='1249110'>adjacent</span> <span m='1249590'>to</span> <span
  m='1249710'>the</span> <span m='1249830'>input</span> <span
  m='1250220'>nodes.</span> </p><p><span m='1251060'>But</span> <span
  m='1251240'>that</span> <span m='1251480'>property</span> <span
  m='1252170'>is</span> <span m='1252380'>lost</span> <span
  m='1252980'>after</span> <span m='1254120'>this</span> <span
  m='1254390'>array.</span> <span m='1255230'>And</span> <span
  m='1255440'>proceeding</span> <span m='1255890'>from</span> <span
  m='1256070'>this</span> <span m='1256280'>array</span> <span
  m='1256640'>to</span> <span m='1256790'>this</span> <span
  m='1257060'>array,</span> <span m='1258440'>we</span> <span
  m='1258590'>see</span> <span m='1259490'>that</span> <span
  m='1259610'>to</span> <span m='1259760'>compute</span> <span
  m='1260750'>these</span> <span m='1261770'>two</span> <span
  m='1261980'>points--</span> <span m='1262700'>let's</span> <span
  m='1263000'>take</span> <span m='1263510'>this</span> <span
  m='1263750'>one</span> <span m='1264080'>and</span> <span
  m='1264260'>this</span> <span m='1264500'>one--</span> <span
  m='1265580'>we</span> <span m='1265760'>need</span> <span
  m='1267140'>this</span> <span m='1267380'>point</span> <span
  m='1268070'>and</span> <span m='1268220'>this</span> <span
  m='1268430'>point.</span> <span m='1270530'>So</span> <span
  m='1270880'>we</span> <span m='1271030'>couldn't</span> <span
  m='1271630'>store</span> <span m='1272140'>then</span> <span
  m='1272350'>this</span> <span m='1272560'>answer</span> <span
  m='1272920'>back</span> <span m='1273250'>in</span> <span
  m='1273370'>here</span> <span m='1273670'>because</span> <span
  m='1274000'>we're</span> <span m='1274120'>going</span> <span
  m='1274330'>to</span> <span m='1274420'>need</span> <span
  m='1274600'>this</span> <span m='1274810'>point</span> <span
  m='1275200'>to</span> <span m='1275320'>compute</span> <span
  m='1275800'>some</span> <span m='1276010'>other</span> <span
  m='1276220'>output</span> <span m='1276580'>points,</span> <span
  m='1276970'>et cetera.</span> </p><p><span m='1278030'>So</span> <span
  m='1278710'>this</span> <span m='1278920'>flow</span> <span
  m='1279220'>graph</span> <span m='1279670'>in</span> <span
  m='1279820'>this</span> <span m='1280000'>form</span> <span
  m='1281050'>has</span> <span m='1281470'>the</span> <span
  m='1281560'>disadvantage</span> <span m='1282790'>that</span> <span
  m='1283660'>the</span> <span m='1283930'>in-place</span> <span
  m='1284410'>computational</span> <span m='1285520'>aspects</span> <span
  m='1286120'>of</span> <span m='1286180'>the</span> <span
  m='1286270'>flow</span> <span m='1286540'>graph</span> <span
  m='1286870'>are</span> <span m='1286930'>lost</span> <span
  m='1287800'>although</span> <span m='1288220'>the</span> <span
  m='1288400'>input</span> <span m='1288880'>is</span> <span
  m='1289090'>in</span> <span m='1289180'>normal</span> <span
  m='1289570'>order</span> <span m='1289990'>and</span> <span
  m='1290170'>the</span> <span m='1290290'>output</span> <span
  m='1290860'>is</span> <span m='1291010'>in</span> <span
  m='1291130'>normal</span> <span m='1291490'>order.</span> <span
  m='1293530'>It</span> <span m='1293620'>has</span> <span
  m='1293830'>another</span> <span m='1294100'>disadvantage</span> <span
  m='1294850'>incidentally,</span> <span m='1295540'>and</span> <span
  m='1295660'>that</span> <span m='1295840'>is</span> <span
  m='1296050'>that</span> <span m='1296170'>the</span> <span
  m='1296350'>indexing</span> <span m='1296920'>is</span> <span
  m='1297010'>somewhat</span> <span m='1297430'>difficult</span> <span
  m='1298630'>in</span> <span m='1298870'>contrast</span> <span
  m='1299860'>to</span> <span m='1300400'>the</span> <span
  m='1300720'>two</span> <span m='1300940'>flow</span> <span
  m='1301210'>graphs</span> <span m='1301570'>that</span> <span
  m='1301660'>we've</span> <span m='1301810'>talked</span> <span
  m='1302140'>about</span> <span m='1302650'>so</span> <span
  m='1302890'>far</span> <span m='1303790'>where</span> <span
  m='1304180'>the</span> <span m='1304390'>indexing</span> <span
  m='1304960'>strategy</span> <span m='1305740'>is</span> <span
  m='1306100'>relatively</span> <span m='1306640'>straightforward</span> <span
  m='1307540'>from</span> <span m='1307720'>stage</span> <span
  m='1308140'>to</span> <span m='1308260'>stage.</span> </p><p><span
  m='1310960'>Now,</span> <span m='1311380'>there's</span> <span
  m='1311620'>another</span> <span m='1312370'>rearrangement</span> <span
  m='1313510'>of</span> <span m='1315010'>this</span> <span
  m='1315580'>flow</span> <span m='1315880'>graph</span> <span
  m='1317650'>which</span> <span m='1321590'>has</span> <span
  m='1322790'>some</span> <span m='1323180'>advantages</span> <span
  m='1323870'>and</span> <span m='1323960'>also</span> <span
  m='1324290'>some</span> <span m='1324470'>disadvantages.</span> <span
  m='1326240'>First,</span> <span m='1327260'>let</span> <span
  m='1327440'>me</span> <span m='1327590'>return</span> <span
  m='1328190'>to</span> <span m='1328550'>the</span> <span
  m='1328700'>original</span> <span m='1329120'>flow</span> <span
  m='1329390'>graph</span> <span m='1329960'>that</span> <span
  m='1330080'>we</span> <span m='1330230'>began</span> <span
  m='1330710'>with,</span> <span m='1331100'>which</span> <span
  m='1331370'>consisted</span> <span m='1331910'>of</span> <span
  m='1332030'>the</span> <span m='1332180'>input</span> <span
  m='1332570'>sorted</span> <span m='1333290'>in</span> <span
  m='1335780'>bit</span> <span m='1335990'>reversed</span> <span
  m='1336410'>order</span> <span m='1336800'>and</span> <span
  m='1336950'>the</span> <span m='1337070'>output</span> <span
  m='1338120'>sorted</span> <span m='1338720'>in</span> <span
  m='1338870'>normal</span> <span m='1339230'>order.</span> </p><p><span
  m='1341010'>The</span> <span m='1341060'>indexing</span> <span
  m='1342380'>in</span> <span m='1342560'>this</span> <span
  m='1342740'>flow</span> <span m='1343040'>graph</span> <span
  m='1344030'>is</span> <span m='1344240'>relatively</span> <span
  m='1345080'>straightforward</span> <span m='1346050'>in</span> <span
  m='1346190'>that</span> <span m='1347120'>you</span> <span
  m='1347570'>should</span> <span m='1347810'>notice</span> <span
  m='1348290'>that</span> <span m='1348470'>as</span> <span
  m='1348740'>you</span> <span m='1348860'>proceed</span> <span
  m='1349250'>from</span> <span m='1349460'>stage</span> <span
  m='1349910'>to</span> <span m='1350030'>stage,</span> <span
  m='1351170'>the</span> <span m='1351290'>width</span> <span
  m='1351800'>of</span> <span m='1351980'>the</span> <span
  m='1352070'>butterflies</span> <span m='1353390'>continues</span> <span
  m='1354050'>to</span> <span m='1354200'>double.</span> <span
  m='1355010'>So</span> <span m='1355160'>here</span> <span
  m='1355470'>the</span> <span m='1355490'>width</span> <span
  m='1355700'>of</span> <span m='1355790'>the</span> <span
  m='1355910'>butterfly</span> <span m='1356690'>is</span> <span
  m='1356990'>1,</span> <span m='1357890'>here</span> <span
  m='1358200'>the</span> <span m='1358220'>width</span> <span
  m='1358550'>of</span> <span m='1358730'>the</span> <span
  m='1358820'>butterfly</span> <span m='1359810'>is</span> <span
  m='1360050'>2--</span> <span m='1360890'>or</span> <span
  m='1361010'>the</span> <span m='1361100'>height</span> <span
  m='1361310'>of</span> <span m='1361430'>the</span> <span
  m='1361490'>butterfly--</span> <span m='1362540'>here</span> <span
  m='1362750'>the</span> <span m='1362870'>height</span> <span
  m='1363050'>of</span> <span m='1363140'>the</span> <span
  m='1363230'>butterfly</span> <span m='1364070'>is</span> <span
  m='1364280'>4.</span> <span m='1366040'>If</span> <span m='1366200'>we</span>
  <span m='1366290'>were</span> <span m='1366410'>computing</span> <span
  m='1366860'>a</span> <span m='1366920'>larger</span> <span
  m='1367610'>order</span> <span m='1367940'>transform,</span> <span
  m='1368690'>then</span> <span m='1369680'>that</span> <span
  m='1370010'>procedure</span> <span m='1370580'>would</span> <span
  m='1370700'>continue.</span> </p><p><span m='1371870'>But</span> <span
  m='1372350'>as</span> <span m='1372920'>you</span> <span
  m='1373100'>can</span> <span m='1374240'>imagine,</span> <span
  m='1376560'>if</span> <span m='1377070'>we</span> <span
  m='1377670'>were</span> <span m='1378150'>implementing</span> <span
  m='1378840'>this</span> <span m='1380070'>on</span> <span m='1380250'>a</span>
  <span m='1380310'>computer</span> <span m='1380910'>or</span> <span
  m='1381090'>with</span> <span m='1381210'>special</span> <span
  m='1381600'>purpose</span> <span m='1381990'>hardware,</span> <span
  m='1384630'>because</span> <span m='1385110'>of</span> <span
  m='1385200'>the</span> <span m='1385320'>fact</span> <span
  m='1385860'>that</span> <span m='1386040'>the</span> <span
  m='1386160'>data</span> <span m='1386490'>separation</span> <span
  m='1387210'>as</span> <span m='1387360'>we</span> <span
  m='1387480'>compute</span> <span m='1387900'>each</span> <span
  m='1388080'>butterfly</span> <span m='1389610'>increases</span> <span
  m='1390450'>or</span> <span m='1390570'>changes</span> <span
  m='1391110'>as</span> <span m='1391260'>we</span> <span m='1391350'>go</span>
  <span m='1391560'>from</span> <span m='1391740'>stage</span> <span
  m='1392160'>to</span> <span m='1392280'>stage,</span> <span
  m='1393360'>what</span> <span m='1393600'>is</span> <span
  m='1393780'>required</span> <span m='1394560'>is</span> <span
  m='1395130'>random</span> <span m='1395550'>access</span> <span
  m='1396000'>memory.</span> <span m='1397060'>We</span> <span
  m='1397290'>require</span> <span m='1397710'>random</span> <span
  m='1398070'>access</span> <span m='1398460'>memory</span> <span
  m='1398910'>because</span> <span m='1399930'>in</span> <span
  m='1400050'>each</span> <span m='1400290'>array</span> <span
  m='1403320'>we</span> <span m='1403770'>are</span> <span
  m='1403920'>not</span> <span m='1404520'>accessing</span> <span
  m='1405150'>data</span> <span m='1405480'>from</span> <span
  m='1405720'>sequential</span> <span m='1406260'>registers.</span> <span
  m='1407250'>We</span> <span m='1407430'>are</span> <span
  m='1407730'>going</span> <span m='1408000'>from</span> <span
  m='1408390'>this</span> <span m='1408600'>array</span> <span
  m='1408930'>to</span> <span m='1409080'>this</span> <span
  m='1409350'>one.</span> <span m='1409740'>After</span> <span
  m='1410100'>that,</span> <span m='1411030'>in</span> <span
  m='1411150'>computing</span> <span m='1411660'>a</span> <span
  m='1411720'>butterfly,</span> <span m='1412680'>we</span> <span
  m='1412830'>no</span> <span m='1413010'>longer</span> <span
  m='1413550'>are</span> <span m='1413760'>accessing</span> <span
  m='1414420'>sequential</span> <span m='1414960'>registers.</span> </p><p><span
  m='1417360'>There</span> <span m='1417540'>is,</span> <span
  m='1417790'>however,</span> <span m='1418360'>a</span> <span
  m='1418460'>modification</span> <span m='1419400'>of</span> <span
  m='1419580'>this</span> <span m='1419820'>algorithm</span> <span
  m='1421300'>which</span> <span m='1422160'>is</span> <span
  m='1423270'>useful</span> <span m='1424050'>in</span> <span
  m='1424200'>the</span> <span m='1424290'>sense</span> <span
  m='1424980'>that</span> <span m='1425520'>it</span> <span
  m='1425940'>permits</span> <span m='1426330'>the</span> <span
  m='1426420'>computation</span> <span m='1427350'>without</span> <span
  m='1427740'>random</span> <span m='1428100'>access</span> <span
  m='1428550'>memory</span> <span m='1429480'>and</span> <span
  m='1429690'>in</span> <span m='1429780'>particular</span> <span
  m='1430320'>is</span> <span m='1430440'>organized</span> <span
  m='1431130'>so</span> <span m='1431340'>that</span> <span
  m='1431580'>it</span> <span m='1431730'>can</span> <span
  m='1431910'>utilize</span> <span m='1432480'>sequential</span> <span
  m='1433050'>memory,</span> <span m='1433980'>although</span> <span
  m='1435000'>it</span> <span m='1435180'>does</span> <span
  m='1435360'>not</span> <span m='1435570'>correspond</span> <span
  m='1436380'>to</span> <span m='1436830'>an</span> <span
  m='1436980'>in-place</span> <span m='1437430'>computation.</span> <span
  m='1438810'>And</span> <span m='1438990'>that</span> <span
  m='1439170'>form</span> <span m='1439500'>of</span> <span
  m='1439620'>the</span> <span m='1439770'>algorithm,</span> <span
  m='1442860'>I</span> <span m='1443310'>have</span> <span
  m='1443580'>indicated</span> <span m='1444180'>here,</span> <span
  m='1444760'>is</span> <span m='1445740'>a</span> <span m='1446190'>form</span>
  <span m='1446590'>of the</span> <span m='1446730'>algorithm</span> <span
  m='1447840'>that</span> <span m='1448170'>originally</span> <span
  m='1448980'>was</span> <span m='1449280'>proposed</span> <span
  m='1449850'>by</span> <span m='1450090'>singleton.</span> </p><p><span
  m='1451920'>This</span> <span m='1452190'>then</span> <span
  m='1452610'>is</span> <span m='1453150'>a</span> <span m='1453270'>form</span>
  <span m='1453780'>of</span> <span m='1453900'>the</span> <span
  m='1453990'>decimation</span> <span m='1454710'>in</span> <span
  m='1454830'>time</span> <span m='1455730'>algorithm.</span> <span
  m='1457380'>It's</span> <span m='1457530'>a</span> <span
  m='1457620'>rearrangement</span> <span m='1458370'>of</span> <span
  m='1458490'>the</span> <span m='1458730'>flowchart</span> <span
  m='1459810'>so</span> <span m='1460110'>that</span> <span
  m='1461580'>sequential</span> <span m='1462270'>memory</span> <span
  m='1462960'>can</span> <span m='1463140'>be</span> <span
  m='1463260'>used</span> <span m='1464100'>rather</span> <span
  m='1464430'>than</span> <span m='1464820'>random</span> <span
  m='1465150'>access</span> <span m='1465630'>memory.</span> <span
  m='1467260'>Let</span> <span m='1467310'>me</span> <span
  m='1467430'>point</span> <span m='1467700'>out</span> <span
  m='1467850'>first</span> <span m='1468180'>of</span> <span
  m='1468300'>all</span> <span m='1468810'>that</span> <span
  m='1469440'>the</span> <span m='1469560'>input</span> <span
  m='1469980'>is</span> <span m='1470190'>in</span> <span m='1470280'>bit</span>
  <span m='1470490'>reversed</span> <span m='1470970'>order,</span> <span
  m='1471870'>the</span> <span m='1472020'>output</span> <span
  m='1472530'>is</span> <span m='1472740'>in</span> <span
  m='1472860'>normal</span> <span m='1473250'>order,</span> <span
  m='1474040'>and</span> <span m='1474150'>now</span> <span
  m='1474570'>let</span> <span m='1474780'>me</span> <span
  m='1474960'>explain</span> <span m='1475560'>in</span> <span
  m='1475680'>a</span> <span m='1475710'>little</span> <span
  m='1475920'>more</span> <span m='1476130'>detail</span> <span
  m='1477300'>why</span> <span m='1478020'>this</span> <span
  m='1478290'>flow</span> <span m='1478560'>graph</span> <span
  m='1479700'>allows</span> <span m='1480390'>the</span> <span
  m='1480540'>use</span> <span m='1480930'>of</span> <span
  m='1481080'>sequential</span> <span m='1481710'>memory</span> <span
  m='1482520'>rather</span> <span m='1482820'>than</span> <span
  m='1483000'>random</span> <span m='1483300'>access</span> <span
  m='1483750'>memory.</span> </p><p><span m='1484870'>First</span> <span
  m='1485070'>of</span> <span m='1485190'>all,</span> <span
  m='1485740'>let</span> <span m='1485820'>me</span> <span
  m='1486000'>indicate</span> <span m='1486810'>that</span> <span
  m='1488220'>the</span> <span m='1488370'>organization</span> <span
  m='1489300'>of</span> <span m='1489450'>this</span> <span
  m='1489630'>flow</span> <span m='1489900'>graph</span> <span
  m='1490800'>is</span> <span m='1491190'>identical</span> <span
  m='1492150'>from</span> <span m='1492360'>stage</span> <span
  m='1492810'>to</span> <span m='1492930'>stage.</span> <span
  m='1494010'>In</span> <span m='1494100'>other</span> <span
  m='1494280'>words,</span> <span m='1494710'>if</span> <span
  m='1494730'>you</span> <span m='1494850'>think</span> <span
  m='1495300'>of</span> <span m='1496320'>how</span> <span
  m='1497280'>this</span> <span m='1497880'>piece</span> <span
  m='1498150'>of</span> <span m='1498240'>the</span> <span
  m='1498360'>flow</span> <span m='1498600'>graph</span> <span
  m='1498990'>looks</span> <span m='1499450'>in</span> <span
  m='1499660'>computing</span> <span m='1500310'>the</span> <span
  m='1500400'>first</span> <span m='1500700'>stage,</span> <span
  m='1501790'>it</span> <span m='1501920'>is</span> <span
  m='1502080'>exactly</span> <span m='1502620'>the</span> <span
  m='1502740'>same</span> <span m='1503130'>with</span> <span
  m='1503310'>regard</span> <span m='1503710'>to</span> <span
  m='1503850'>data</span> <span m='1504180'>access</span> <span
  m='1505380'>as</span> <span m='1505800'>computing</span> <span
  m='1506370'>this</span> <span m='1506520'>stage</span> <span
  m='1506940'>is</span> <span m='1507720'>in</span> <span
  m='1507810'>relation</span> <span m='1508710'>to</span> <span
  m='1509220'>the</span> <span m='1509340'>one</span> <span
  m='1509520'>before</span> <span m='1510030'>it,</span> <span
  m='1510510'>and</span> <span m='1510780'>this</span> <span
  m='1510960'>continues</span> <span m='1511500'>on</span> <span
  m='1511710'>through.</span> <span m='1512520'>So</span> <span
  m='1512910'>as</span> <span m='1513060'>opposed</span> <span
  m='1513450'>to</span> <span m='1513540'>the</span> <span
  m='1513690'>other</span> <span m='1513870'>forms</span> <span
  m='1514260'>of</span> <span m='1514350'>the</span> <span
  m='1514770'>algorithm,</span> <span m='1516030'>the</span> <span
  m='1516210'>indexing</span> <span m='1516930'>is</span> <span
  m='1517110'>identical</span> <span m='1517740'>from</span> <span
  m='1517950'>stage</span> <span m='1518370'>to</span> <span
  m='1518490'>stage</span> <span m='1519210'>in</span> <span
  m='1519330'>this</span> <span m='1519510'>form</span> <span
  m='1519810'>of</span> <span m='1519900'>the</span> <span
  m='1520050'>algorithm.</span> </p><p><span m='1521940'>Now,</span> <span
  m='1522720'>to</span> <span m='1523170'>utilize</span> <span
  m='1523680'>sequential</span> <span m='1524280'>memory--</span> <span
  m='1524760'>sequential</span> <span m='1525240'>memory</span> <span
  m='1525600'>might</span> <span m='1525900'>be</span> <span
  m='1526170'>disk</span> <span m='1526500'>memory</span> <span
  m='1527040'>or</span> <span m='1527130'>drum</span> <span
  m='1527460'>memory</span> <span m='1528150'>or</span> <span
  m='1528420'>shift</span> <span m='1528720'>register</span> <span
  m='1529200'>memory,</span> <span m='1529670'>for</span> <span
  m='1529860'>example.</span> <span m='1530890'>Generally,</span> <span
  m='1531300'>bulk</span> <span m='1531660'>memory</span> <span
  m='1532320'>is</span> <span m='1534150'>sequential</span> <span
  m='1534690'>memory</span> <span m='1535050'>rather</span> <span
  m='1535380'>than</span> <span m='1535530'>random</span> <span
  m='1535830'>access.</span> <span m='1537270'>Let's</span> <span
  m='1537960'>think</span> <span m='1538410'>of</span> <span
  m='1539100'>the</span> <span m='1539280'>original</span> <span
  m='1539760'>data</span> <span m='1541600'>first</span> <span
  m='1542230'>shuffled</span> <span m='1542890'>in</span> <span
  m='1543070'>bit</span> <span m='1543280'>reversed</span> <span
  m='1543760'>order</span> <span m='1545210'>and</span> <span
  m='1545260'>then</span> <span m='1545710'>stored</span> <span
  m='1546580'>in</span> <span m='1546790'>two</span> <span
  m='1547090'>separate</span> <span m='1547540'>memories.</span> <span
  m='1548710'>Let's</span> <span m='1548950'>call</span> <span
  m='1549190'>them</span> <span m='1549370'>M</span> <span
  m='1549580'>sub</span> <span m='1549795'>A</span> <span m='1550010'>and</span>
  <span m='1550160'>M</span> <span m='1550273'>sub</span> <span
  m='1550386'>B.</span> </p><p><span m='1551380'>The</span> <span
  m='1551500'>first</span> <span m='1551800'>half</span> <span
  m='1552100'>of</span> <span m='1552190'>the</span> <span m='1552280'>data
  is</span> <span m='1552670'>stored</span> <span m='1553150'>in</span> <span
  m='1553330'>memory</span> <span m='1554070'>A.</span> <span
  m='1554890'>The</span> <span m='1555010'>second</span> <span
  m='1555340'>half</span> <span m='1555640'>of</span> <span
  m='1555700'>the</span> <span m='1555820'>data is</span> <span
  m='1556150'>stored</span> <span m='1556510'>in</span> <span
  m='1556630'>memory</span> <span m='1557020'>B.</span> <span
  m='1558370'>And</span> <span m='1558520'>then</span> <span
  m='1559180'>let's</span> <span m='1559660'>permit</span> <span
  m='1560230'>two</span> <span m='1560590'>additional</span> <span
  m='1561100'>sequential</span> <span m='1561670'>memory</span> <span
  m='1562030'>registers,</span> <span m='1564250'>memories</span> <span
  m='1565350'>M</span> <span m='1565555'>sub</span> <span m='1565760'>C</span>
  <span m='1565940'>and</span> <span m='1566040'>M</span> <span
  m='1566140'>sub</span> <span m='1566560'>D</span> <span m='1567220'>for</span>
  <span m='1567370'>storing</span> <span m='1568120'>the</span> <span
  m='1568330'>output</span> <span m='1568960'>of</span> <span
  m='1569110'>the</span> <span m='1569200'>computation.</span> </p><p><span
  m='1570430'>Then</span> <span m='1570550'>the</span> <span
  m='1570640'>computation</span> <span m='1571450'>would</span> <span
  m='1571630'>proceed</span> <span m='1572590'>essentially</span> <span
  m='1573160'>as</span> <span m='1573280'>follows.</span> <span
  m='1575390'>We</span> <span m='1575500'>would</span> <span
  m='1576010'>access</span> <span m='1576760'>the</span> <span
  m='1576880'>first</span> <span m='1577150'>two</span> <span
  m='1577330'>data</span> <span m='1577630'>points</span> <span
  m='1577990'>from</span> <span m='1578140'>memory</span> <span
  m='1578395'>A,</span> <span m='1579640'>use</span> <span
  m='1579940'>those</span> <span m='1580480'>to</span> <span
  m='1580630'>compute</span> <span m='1581080'>the</span> <span
  m='1581200'>first</span> <span m='1582760'>point</span> <span
  m='1583450'>in</span> <span m='1583990'>this</span> <span
  m='1584200'>array,</span> <span m='1585010'>store</span> <span
  m='1585370'>that</span> <span m='1585670'>in</span> <span
  m='1585820'>memory</span> <span m='1586220'>C,</span> <span
  m='1587650'>and</span> <span m='1587800'>use</span> <span
  m='1588040'>that</span> <span m='1588280'>to</span> <span
  m='1588430'>compute</span> <span m='1589900'>the</span> <span
  m='1590020'>first</span> <span m='1590380'>point</span> <span
  m='1590770'>in</span> <span m='1590860'>the</span> <span
  m='1590920'>second</span> <span m='1591310'>half</span> <span
  m='1591940'>of</span> <span m='1592060'>this</span> <span
  m='1592270'>array</span> <span m='1593140'>and</span> <span
  m='1593260'>store</span> <span m='1593590'>that</span> <span
  m='1593920'>in</span> <span m='1594070'>memory</span> <span
  m='1594520'>D.</span> <span m='1596140'>Next,</span> <span
  m='1596560'>we</span> <span m='1596710'>would</span> <span
  m='1596860'>access</span> <span m='1597550'>the</span> <span
  m='1597640'>next</span> <span m='1598030'>two</span> <span
  m='1598240'>input</span> <span m='1598570'>points</span> <span
  m='1598900'>from</span> <span m='1599040'>memory</span> <span
  m='1599320'>A,</span> <span m='1600860'>add</span> <span
  m='1601270'>those--</span> <span m='1603220'>we</span> <span
  m='1603340'>would</span> <span m='1603880'>do</span> <span
  m='1604030'>the</span> <span m='1604150'>required</span> <span
  m='1604540'>computation--</span> <span m='1605470'>store</span> <span
  m='1605860'>the</span> <span m='1605950'>result</span> <span
  m='1606550'>in</span> <span m='1607900'>the</span> <span
  m='1608320'>next</span> <span m='1609040'>location</span> <span
  m='1609790'>in</span> <span m='1609970'>memory</span> <span
  m='1610235'>A,</span> <span m='1611560'>also</span> <span
  m='1612580'>store</span> <span m='1613180'>the</span> <span
  m='1613660'>second</span> <span m='1614080'>half</span> <span
  m='1614320'>of</span> <span m='1614380'>the</span> <span
  m='1614500'>butterfly</span> <span m='1615070'>output</span> <span
  m='1616000'>in</span> <span m='1616150'>the</span> <span
  m='1616660'>second</span> <span m='1617410'>register</span> <span
  m='1618190'>in</span> <span m='1618340'>memory</span> <span
  m='1619120'>D.</span> </p><p><span m='1619540'>So</span> <span
  m='1621370'>as</span> <span m='1621580'>we</span> <span
  m='1621700'>proceed</span> <span m='1622180'>along,</span> <span
  m='1622990'>we</span> <span m='1623140'>access</span> <span
  m='1623950'>the</span> <span m='1624040'>first</span> <span
  m='1624310'>two</span> <span m='1624460'>points</span> <span
  m='1624790'>from</span> <span m='1624910'>memory</span> <span
  m='1625260'>A</span> <span m='1625450'>then</span> <span
  m='1625630'>the</span> <span m='1625690'>next</span> <span
  m='1625930'>two</span> <span m='1626080'>points</span> <span
  m='1626410'>from</span> <span m='1626530'>memory</span> <span
  m='1626950'>A,</span> <span m='1627730'>storing</span> <span
  m='1628420'>in</span> <span m='1629170'>memory</span> <span
  m='1629590'>C</span> <span m='1630070'>and</span> <span
  m='1630220'>memory</span> <span m='1630610'>D.</span> <span
  m='1631610'>When</span> <span m='1632110'>we</span> <span
  m='1632410'>have</span> <span m='1632560'>gone</span> <span
  m='1632830'>through</span> <span m='1633010'>the</span> <span
  m='1633100'>first</span> <span m='1633430'>half</span> <span
  m='1633700'>of</span> <span m='1633790'>the</span> <span
  m='1633910'>data,</span> <span m='1634540'>we</span> <span
  m='1634690'>now</span> <span m='1635110'>access</span> <span
  m='1635650'>the</span> <span m='1635770'>data</span> <span
  m='1636670'>from</span> <span m='1637120'>the</span> <span
  m='1637240'>second</span> <span m='1637660'>input</span> <span
  m='1638020'>memory,</span> <span m='1638710'>memory</span> <span
  m='1639130'>B,</span> <span m='1640060'>the</span> <span
  m='1640150'>first</span> <span m='1640450'>two</span> <span
  m='1640630'>points,</span> <span m='1642640'>do</span> <span
  m='1642910'>the</span> <span m='1643000'>required</span> <span
  m='1643450'>computation,</span> <span m='1644950'>and</span> <span
  m='1645730'>store</span> <span m='1646420'>in</span> <span
  m='1646690'>the</span> <span m='1646780'>next</span> <span
  m='1646990'>sequential</span> <span m='1647530'>registers</span> <span
  m='1648370'>in</span> <span m='1648550'>memory</span> <span
  m='1648940'>C</span> <span m='1649800'>and</span> <span
  m='1649930'>memory</span> <span m='1650305'>D,</span> <span
  m='1650680'>et</span> <span m='1651080'>cetera.</span> </p><p><span
  m='1652060'>So</span> <span m='1652510'>the</span> <span
  m='1652630'>strategy</span> <span m='1653650'>in</span> <span
  m='1653770'>this</span> <span m='1653950'>case,</span> <span
  m='1654340'>then</span> <span m='1654700'>is</span> <span
  m='1655000'>that</span> <span m='1655720'>the</span> <span
  m='1655900'>input</span> <span m='1656290'>is</span> <span
  m='1656410'>stored</span> <span m='1657220'>half</span> <span
  m='1658740'>in</span> <span m='1659850'>memory</span> <span
  m='1660250'>A,</span> <span m='1660480'>half</span> <span
  m='1660780'>in</span> <span m='1660900'>memory</span> <span
  m='1661260'>B.</span> <span m='1663240'>The</span> <span
  m='1663330'>data</span> <span m='1663690'>is</span> <span
  m='1663930'>first</span> <span m='1664260'>accessed</span> <span
  m='1664680'>from</span> <span m='1664860'>memory</span> <span
  m='1665160'>A</span> <span m='1666030'>and</span> <span m='1666570'>we</span>
  <span m='1666780'>alternately</span> <span m='1668100'>put</span> <span
  m='1668340'>results</span> <span m='1669090'>in</span> <span
  m='1669300'>memories</span> <span m='1669660'>C</span> <span
  m='1669960'>and</span> <span m='1670080'>D.</span> <span
  m='1671490'>When</span> <span m='1671670'>we</span> <span
  m='1671790'>finish</span> <span m='1672140'>with</span> <span
  m='1672270'>memory</span> <span m='1672540'>A,</span> <span
  m='1672810'>we</span> <span m='1672960'>then</span> <span
  m='1673140'>proceed</span> <span m='1673530'>to</span> <span
  m='1673680'>memory</span> <span m='1674070'>B,</span> <span
  m='1676490'>access</span> <span m='1676950'>data</span> <span
  m='1677220'>sequentially,</span> <span m='1678420'>and</span> <span
  m='1678690'>continue</span> <span m='1679140'>to</span> <span
  m='1679230'>store</span> <span m='1679530'>the</span> <span
  m='1679620'>results</span> <span m='1680460'>alternating</span> <span
  m='1681450'>in</span> <span m='1681840'>memory</span> <span
  m='1682230'>C</span> <span m='1682500'>and</span> <span m='1682620'>D.</span>
  <span m='1684030'>Now</span> <span m='1684600'>that</span> <span
  m='1684870'>gives</span> <span m='1685170'>us</span> <span
  m='1685800'>the</span> <span m='1685920'>result</span> <span
  m='1686400'>at</span> <span m='1686550'>this</span> <span
  m='1686760'>stage.</span> </p><p><span m='1687660'>To</span> <span
  m='1687750'>compute</span> <span m='1688110'>the</span> <span
  m='1688200'>next</span> <span m='1688440'>stage,</span> <span
  m='1689430'>we</span> <span m='1689580'>now</span> <span
  m='1689790'>start</span> <span m='1690330'>with</span> <span
  m='1690900'>the</span> <span m='1690990'>memory</span> <span
  m='1691410'>C</span> <span m='1691770'>and</span> <span m='1691950'>D</span>
  <span m='1692280'>as</span> <span m='1692460'>the</span> <span
  m='1692640'>inputs</span> <span m='1693660'>and</span> <span
  m='1694560'>store</span> <span m='1695490'>the</span> <span
  m='1695610'>results</span> <span m='1696120'>of</span> <span
  m='1696210'>the</span> <span m='1696330'>computation</span> <span
  m='1697140'>back</span> <span m='1697500'>into</span> <span
  m='1698150'>memories</span> <span m='1698620'>A</span> <span
  m='1698840'>and</span> <span m='1699150'>B.</span> <span m='1699870'>So</span>
  <span m='1700500'>in</span> <span m='1700650'>a</span> <span
  m='1700680'>sense,</span> <span m='1701140'>you</span> <span
  m='1701240'>can</span> <span m='1701280'>think</span> <span
  m='1701550'>of</span> <span m='1701640'>the</span> <span
  m='1701760'>computation</span> <span m='1702163'>then</span> <span
  m='1703680'>as</span> <span m='1704610'>involving</span> <span
  m='1705090'>four</span> <span m='1705390'>memory,</span> <span
  m='1706580'>four</span> <span m='1706830'>separate</span> <span
  m='1707430'>sequential</span> <span m='1707970'>memories,</span> <span
  m='1708255'>A,</span> <span m='1708540'>B,</span> <span m='1708720'>C,</span>
  <span m='1709140'>and</span> <span m='1709260'>D.</span> <span
  m='1709980'>We</span> <span m='1710070'>start</span> <span m='1710430'>with
  A</span> <span m='1710610'>and</span> <span m='1710880'>B,</span> <span
  m='1711690'>flush</span> <span m='1712230'>the</span> <span
  m='1712350'>data</span> <span m='1713370'>into</span> <span
  m='1714270'>memory</span> <span m='1714660'>C</span> <span
  m='1714960'>and</span> <span m='1715080'>D,</span> <span
  m='1715920'>then</span> <span m='1716190'>flush</span> <span
  m='1716580'>the</span> <span m='1716700'>results</span> <span
  m='1717420'>back.</span> </p><p><span m='1718110'>And</span> <span
  m='1718410'>in</span> <span m='1718530'>fact,</span> <span
  m='1718860'>you</span> <span m='1718950'>can</span> <span
  m='1719100'>think</span> <span m='1719370'>of</span> <span
  m='1719460'>the</span> <span m='1719550'>computation</span> <span
  m='1720870'>much</span> <span m='1721080'>the</span> <span
  m='1721170'>same</span> <span m='1721470'>way</span> <span
  m='1721920'>as</span> <span m='1722850'>a</span> <span
  m='1722910'>slinky</span> <span m='1723390'>toy</span> <span
  m='1723870'>where</span> <span m='1724620'>you</span> <span
  m='1724740'>bounce</span> <span m='1725490'>the</span> <span
  m='1726360'>data</span> <span m='1726690'>back</span> <span
  m='1726990'>and</span> <span m='1727080'>forth</span> <span
  m='1727470'>between</span> <span m='1727830'>these</span> <span
  m='1728010'>two</span> <span m='1728160'>sets</span> <span
  m='1728490'>of</span> <span m='1728580'>sequential</span> <span
  m='1729120'>memories.</span> <span m='1732320'>That</span> <span
  m='1732620'>then</span> <span m='1733010'>is</span> <span m='1734060'>a</span>
  <span m='1734150'>form</span> <span m='1734480'>of</span> <span
  m='1734540'>the</span> <span m='1734630'>computation</span> <span
  m='1735620'>which</span> <span m='1735860'>is</span> <span
  m='1736010'>not</span> <span m='1736250'>an</span> <span
  m='1736310'>in-place</span> <span m='1736880'>computation.</span> <span
  m='1737830'>And</span> <span m='1737960'>furthermore,</span> <span
  m='1739250'>the</span> <span m='1739610'>input</span> <span
  m='1740000'>is</span> <span m='1740120'>bit</span> <span
  m='1740330'>reversed,</span> <span m='1740840'>although</span> <span
  m='1741110'>the</span> <span m='1741290'>output</span> <span
  m='1741680'>is</span> <span m='1741830'>in</span> <span
  m='1741950'>normal</span> <span m='1742320'>order,</span> <span
  m='1743400'>and</span> <span m='1744920'>it</span> <span
  m='1745040'>has</span> <span m='1745310'>the</span> <span
  m='1745430'>advantage,</span> <span m='1746000'>though,</span> <span
  m='1746600'>that</span> <span m='1746840'>the</span> <span
  m='1746990'>indexing</span> <span m='1747530'>is</span> <span
  m='1747650'>identical</span> <span m='1748190'>from</span> <span
  m='1748370'>stage</span> <span m='1748760'>to</span> <span
  m='1748880'>stage</span> <span m='1749780'>and</span> <span
  m='1749870'>consequently</span> <span m='1750680'>can</span> <span
  m='1750860'>utilize</span> <span m='1752510'>sequential</span> <span
  m='1753140'>memory</span> <span m='1754100'>rather</span> <span
  m='1754460'>than</span> <span m='1754670'>requiring</span> <span
  m='1755180'>random</span> <span m='1755510'>access</span> <span
  m='1755990'>memory.</span> </p><p><span m='1757810'>Well,</span> <span
  m='1758380'>that</span> <span m='1759130'>then</span> <span
  m='1759580'>completes</span> <span m='1760030'>the</span> <span
  m='1760120'>discussion</span> <span m='1760960'>of</span> <span
  m='1761530'>the</span> <span m='1761890'>decimation</span> <span
  m='1762580'>in</span> <span m='1762660'>time</span> <span
  m='1763000'>form</span> <span m='1763330'>of</span> <span
  m='1763420'>the</span> <span m='1763570'>algorithm.</span> <span
  m='1764890'>There</span> <span m='1765070'>are,</span> <span
  m='1765550'>of</span> <span m='1765700'>course,</span> <span
  m='1766190'>a</span> <span m='1766290'>number</span> <span
  m='1766450'>of</span> <span m='1766750'>other</span> <span
  m='1766990'>variations</span> <span m='1767950'>on</span> <span
  m='1768160'>this</span> <span m='1768490'>and</span> <span
  m='1768580'>some</span> <span m='1768850'>of</span> <span
  m='1768940'>them</span> <span m='1769240'>are</span> <span
  m='1769450'>discussed</span> <span m='1770290'>in</span> <span
  m='1770410'>the</span> <span m='1770540'>text.</span> <span
  m='1772520'>What</span> <span m='1772790'>I'd</span> <span
  m='1772910'>like</span> <span m='1773150'>to</span> <span
  m='1773390'>proceed</span> <span m='1773810'>to</span> <span
  m='1774080'>now</span> <span m='1774590'>is</span> <span m='1774920'>a</span>
  <span m='1774980'>slightly</span> <span m='1776030'>different</span> <span
  m='1776420'>form</span> <span m='1777140'>of</span> <span
  m='1778580'>FFT</span> <span m='1779180'>algorithms</span> <span
  m='1780570'>which</span> <span m='1781040'>are</span> <span
  m='1781280'>really</span> <span m='1781550'>derived</span> <span
  m='1782180'>on</span> <span m='1782390'>a</span> <span
  m='1782900'>somewhat</span> <span m='1783260'>different</span> <span
  m='1783530'>basis</span> <span m='1784130'>than</span> <span
  m='1784310'>the</span> <span m='1784370'>decimation</span> <span
  m='1785030'>in</span> <span m='1785120'>time</span> <span
  m='1785450'>form</span> <span m='1785750'>of</span> <span
  m='1785810'>the</span> <span m='1785960'>algorithms.</span> <span
  m='1787040'>But</span> <span m='1787370'>we'll</span> <span
  m='1787550'>see</span> <span m='1787940'>as</span> <span m='1788180'>we</span>
  <span m='1788960'>finally</span> <span m='1789380'>continue</span> <span
  m='1789830'>the</span> <span m='1789950'>discussion</span> <span
  m='1791030'>that</span> <span m='1791540'>there</span> <span
  m='1791840'>is</span> <span m='1791990'>a</span> <span m='1792050'>very</span>
  <span m='1792290'>close</span> <span m='1792620'>relationship</span> <span
  m='1793820'>between</span> <span m='1794630'>the</span> <span
  m='1794720'>decimation</span> <span m='1795350'>in</span> <span
  m='1795410'>time</span> <span m='1795770'>algorithms</span> <span
  m='1796550'>as</span> <span m='1796790'>we've</span> <span
  m='1796940'>just</span> <span m='1797150'>talked</span> <span
  m='1797480'>about</span> <span m='1798420'>and</span> <span
  m='1798440'>the</span> <span m='1798530'>class</span> <span
  m='1798830'>of</span> <span m='1798950'>algorithms</span> <span
  m='1799950'>which</span> <span m='1800150'>I</span> <span
  m='1800240'>would</span> <span m='1800390'>now</span> <span
  m='1800570'>like</span> <span m='1800780'>to</span> <span
  m='1800870'>introduce,</span> <span m='1801830'>which</span> <span
  m='1802070'>are</span> <span m='1802400'>the</span> <span
  m='1802640'>decimation</span> <span m='1803510'>in</span> <span
  m='1803660'>frequency</span> <span m='1804830'>forms</span> <span
  m='1805370'>of</span> <span m='1805520'>the</span> <span
  m='1805750'>FFT</span> <span m='1806210'>algorithm.</span> </p><p><span
  m='1808150'>Well,</span> <span m='1808420'>in</span> <span
  m='1808540'>particular,</span> <span m='1809590'>the</span> <span
  m='1810250'>notion</span> <span m='1811480'>in</span> <span
  m='1811710'>deriving</span> <span m='1812680'>the</span> <span
  m='1813370'>decimation</span> <span m='1814030'>and</span> <span
  m='1814120'>frequency</span> <span m='1816190'>forms</span> <span
  m='1816640'>of</span> <span m='1816730'>the</span> <span
  m='1816910'>FFT</span> <span m='1817390'>algorithm</span> <span
  m='1818740'>is,</span> <span m='1819670'>essentially,</span> <span
  m='1820150'>rather</span> <span m='1820570'>than</span> <span
  m='1820840'>breaking</span> <span m='1821350'>the</span> <span
  m='1821500'>input</span> <span m='1822180'>up</span> <span
  m='1822490'>into</span> <span m='1823330'>the</span> <span
  m='1823480'>even</span> <span m='1823750'>numbered</span> <span
  m='1824020'>and</span> <span m='1824110'>the</span> <span
  m='1824260'>odd</span> <span m='1824440'>numbered</span> <span
  m='1824770'>points,</span> <span m='1825660'>organize</span> <span
  m='1826210'>the</span> <span m='1826300'>computation</span> <span
  m='1827230'>so</span> <span m='1827410'>that</span> <span
  m='1827650'>we</span> <span m='1827800'>compute</span> <span
  m='1828220'>separately</span> <span m='1829480'>the</span> <span
  m='1829660'>even</span> <span m='1829960'>numbered</span> <span
  m='1830440'>and</span> <span m='1830650'>odd</span> <span
  m='1830860'>numbered</span> <span m='1831340'>output</span> <span
  m='1831820'>points.</span> <span m='1833620'>In</span> <span
  m='1833740'>particular,</span> <span m='1834890'>let's</span> <span
  m='1836140'>look</span> <span m='1836380'>again</span> <span
  m='1836890'>at</span> <span m='1837640'>the</span> <span
  m='1837850'>general</span> <span m='1838270'>form</span> <span
  m='1838840'>for</span> <span m='1839140'>the</span> <span
  m='1839230'>discrete</span> <span m='1839590'>Fourier</span> <span
  m='1840010'>transform</span> <span m='1840700'>x</span> <span
  m='1840940'>of</span> <span m='1841030'>k</span> <span
  m='1841630'>given</span> <span m='1841900'>by</span> <span
  m='1842080'>this</span> <span m='1842320'>sum</span> <span
  m='1844210'>and</span> <span m='1844330'>let's</span> <span
  m='1845080'>consider</span> <span m='1845800'>decomposing</span> <span
  m='1846730'>this</span> <span m='1847270'>into</span> <span
  m='1847840'>a</span> <span m='1847930'>sum</span> <span
  m='1848380'>over</span> <span m='1849310'>the</span> <span
  m='1849430'>first</span> <span m='1849790'>half</span> <span
  m='1850090'>of</span> <span m='1850210'>the</span> <span
  m='1850330'>input</span> <span m='1850660'>points</span> <span
  m='1851740'>and</span> <span m='1852270'>a</span> <span m='1852370'>sum</span>
  <span m='1852880'>over</span> <span m='1853210'>the</span> <span
  m='1853330'>second</span> <span m='1853690'>half</span> <span
  m='1853990'>of</span> <span m='1854080'>the</span> <span
  m='1854230'>input</span> <span m='1854560'>points.</span> </p><p><span
  m='1856480'>Well,</span> <span m='1857020'>the</span> <span
  m='1857140'>sum</span> <span m='1857560'>over</span> <span
  m='1857830'>the</span> <span m='1857920'>second</span> <span
  m='1858280'>half</span> <span m='1858550'>of</span> <span
  m='1858670'>the</span> <span m='1858790'>input</span> <span
  m='1859120'>points</span> <span m='1859810'>we</span> <span
  m='1860020'>can</span> <span m='1860230'>rearrange</span> <span
  m='1861100'>somewhat</span> <span m='1861520'>differently</span> <span
  m='1862690'>by</span> <span m='1863920'>essentially</span> <span
  m='1864460'>implementing</span> <span m='1864970'>a</span> <span
  m='1865030'>substitution</span> <span m='1865780'>of</span> <span
  m='1865840'>variables</span> <span m='1867040'>so</span> <span
  m='1867340'>that</span> <span m='1867640'>the</span> <span
  m='1868510'>index</span> <span m='1869710'>on</span> <span
  m='1869860'>the</span> <span m='1869950'>sum</span> <span
  m='1870430'>is</span> <span m='1870610'>changed</span> <span
  m='1871180'>to</span> <span m='1871330'>an</span> <span
  m='1871420'>index</span> <span m='1871840'>from</span> <span
  m='1872020'>0</span> <span m='1872440'>to</span> <span m='1872620'>N</span>
  <span m='1872770'>over</span> <span m='1873010'>2</span> <span
  m='1873220'>minus</span> <span m='1873640'>1.</span> <span
  m='1875270'>And</span> <span m='1875290'>if</span> <span m='1875410'>we</span>
  <span m='1875560'>do</span> <span m='1875740'>that,</span> <span
  m='1876580'>the</span> <span m='1877090'>sum</span> <span
  m='1877480'>that</span> <span m='1877630'>results</span> <span
  m='1878660'>then,</span> <span m='1879340'>the</span> <span
  m='1879430'>expression</span> <span m='1879940'>that</span> <span
  m='1880060'>results,</span> <span m='1881140'>is</span> <span
  m='1881470'>W</span> <span m='1881950'>sub</span> <span m='1882190'>N</span>
  <span m='1882430'>to</span> <span m='1882540'>the</span> <span
  m='1882670'>N</span> <span m='1882790'>over</span> <span m='1883000'>2</span>
  <span m='1883240'>k</span> <span m='1884260'>times</span> <span
  m='1884590'>the</span> <span m='1884680'>sum</span> <span
  m='1885250'>of</span> <span m='1885580'>x</span> <span m='1885880'>of</span>
  <span m='1886030'>n</span> <span m='1886300'>plus</span> <span
  m='1886540'>capital</span> <span m='1886990'>N</span> <span
  m='1887110'>over</span> <span m='1887290'>2</span> <span
  m='1887620'>times</span> <span m='1887980'>W</span> <span
  m='1888445'>sub</span> <span m='1888677'>N</span> <span m='1888910'>to</span>
  <span m='1889030'>the</span> <span m='1889180'>nk.</span> <span
  m='1890260'>And</span> <span m='1890770'>you</span> <span
  m='1890920'>can</span> <span m='1891070'>easily</span> <span
  m='1891400'>check</span> <span m='1891790'>that</span> <span
  m='1892900'>this</span> <span m='1893260'>is</span> <span
  m='1893410'>correct.</span> </p><p><span m='1893770'>For</span> <span
  m='1893920'>example,</span> <span m='1895090'>for</span> <span
  m='1895510'>little</span> <span m='1895790'>n</span> <span
  m='1895930'>equal</span> <span m='1896170'>to</span> <span
  m='1896290'>capital</span> <span m='1896740'>N</span> <span
  m='1896890'>over</span> <span m='1897100'>2</span> <span
  m='1897610'>here,</span> <span m='1898900'>we</span> <span
  m='1899050'>have</span> <span m='1899380'>x</span> <span m='1899950'>of</span>
  <span m='1900220'>capital</span> <span m='1900700'>N</span> <span
  m='1900820'>over</span> <span m='1901030'>2</span> <span m='1901300'>W
  sub</span> <span m='1901660'>N</span> <span m='1902080'>to</span> <span
  m='1902210'>the</span> <span m='1902290'>capital</span> <span
  m='1902770'>N</span> <span m='1902890'>over</span> <span m='1903100'>2</span>
  <span m='1903340'>k.</span> <span m='1904390'>Here,</span> <span
  m='1904750'>for</span> <span m='1905020'>little n</span> <span
  m='1905380'>equals</span> <span m='1905650'>0,</span> <span
  m='1906670'>we</span> <span m='1906850'>get</span> <span m='1907150'>W</span>
  <span m='1907555'>sub N</span> <span m='1907960'>to</span> <span
  m='1908080'>the</span> <span m='1908170'>capital</span> <span
  m='1908590'>N</span> <span m='1908680'>over</span> <span m='1908890'>2</span>
  <span m='1909100'>k</span> <span m='1910030'>times</span> <span
  m='1910720'>x</span> <span m='1911230'>of</span> <span
  m='1912740'>capital</span> <span m='1913190'>N</span> <span
  m='1913490'>over</span> <span m='1913760'>2,</span> <span
  m='1914210'>and</span> <span m='1914360'>this</span> <span
  m='1914870'>term</span> <span m='1915110'>becomes</span> <span
  m='1915530'>1.</span> <span m='1916130'>Just</span> <span
  m='1916310'>simply</span> <span m='1917590'>a</span> <span
  m='1917660'>substitution</span> <span m='1918380'>of</span> <span
  m='1918470'>variables.</span> </p><p><span m='1920300'>Well,</span> <span
  m='1920720'>we</span> <span m='1920900'>recognize</span> <span
  m='1922610'>this</span> <span m='1923780'>term,</span> <span
  m='1924230'>W</span> <span m='1924620'>sub</span> <span m='1925070'>n</span>
  <span m='1925370'>to</span> <span m='1925520'>the</span> <span
  m='1925640'>N</span> <span m='1925760'>over</span> <span m='1925970'>2</span>
  <span m='1926210'>k,</span> <span m='1927290'>is</span> <span
  m='1927470'>equal</span> <span m='1927830'>to</span> <span
  m='1928880'>minus</span> <span m='1929330'>1.</span> <span
  m='1931280'>And</span> <span m='1931400'>consequently,</span> <span
  m='1932570'>then</span> <span m='1933080'>we</span> <span
  m='1933260'>can</span> <span m='1933440'>rewrite</span> <span
  m='1933950'>this</span> <span m='1935180'>as</span> <span
  m='1935510'>I've</span> <span m='1935690'>indicated</span> <span
  m='1936260'>here,</span> <span m='1936800'>x</span> <span
  m='1937100'>of</span> <span m='1937220'>k</span> <span m='1937730'>is</span>
  <span m='1937940'>equal</span> <span m='1938300'>to</span> <span
  m='1938870'>a</span> <span m='1938930'>sum</span> <span m='1939810'>from
  n</span> <span m='1940140'>equals</span> <span m='1940450'>0</span> <span
  m='1940970'>to</span> <span m='1941150'>N</span> <span m='1941300'>over</span>
  <span m='1941510'>2</span> <span m='1941720'>minus</span> <span
  m='1942140'>1</span> <span m='1943421'>of</span> <span m='1943850'>x of
  n</span> <span m='1944960'>plus</span> <span m='1945650'>minus</span> <span
  m='1946070'>1</span> <span m='1946310'>to</span> <span m='1946430'>the</span>
  <span m='1946550'>k--</span> <span m='1947150'>k</span> <span
  m='1947960'>being</span> <span m='1948560'>the</span> <span
  m='1948800'>index</span> <span m='1949340'>on</span> <span
  m='1949520'>the</span> <span m='1949610'>DFT--</span> <span
  m='1951230'>times</span> <span m='1951650'>x</span> <span
  m='1951890'>of</span> <span m='1951980'>n plus</span> <span
  m='1952340'>capital</span> <span m='1952700'>N</span> <span
  m='1952820'>over</span> <span m='1953000'>2</span> <span m='1953480'>W</span>
  <span m='1953820'>sub N</span> <span m='1954160'>to</span> <span
  m='1954290'>the</span> <span m='1954440'>nk.</span> </p><p><span
  m='1956580'>Well,</span> <span m='1957300'>it's</span> <span
  m='1957510'>tempting</span> <span m='1957990'>to</span> <span
  m='1958110'>look</span> <span m='1958350'>at</span> <span
  m='1958470'>this</span> <span m='1958980'>and</span> <span
  m='1959130'>say</span> <span m='1960390'>kind</span> <span
  m='1960570'>of</span> <span m='1960660'>in</span> <span
  m='1960750'>analogy</span> <span m='1961320'>with</span> <span
  m='1961450'>the</span> <span m='1961530'>decimation</span> <span
  m='1962160'>in</span> <span m='1962250'>time--</span> <span
  m='1962850'>the</span> <span m='1962970'>steps</span> <span
  m='1963240'>we</span> <span m='1963330'>took</span> <span
  m='1963510'>in</span> <span m='1963570'>the</span> <span
  m='1963630'>decimation</span> <span m='1964260'>time</span> <span
  m='1964590'>algorithm,</span> <span m='1965850'>that</span> <span
  m='1966480'>this</span> <span m='1966870'>is</span> <span
  m='1967330'>an</span> <span m='1967450'>N-over-2-point</span> <span
  m='1968287'>DFT.</span> <span m='1969480'>It</span> <span
  m='1969930'>is</span> <span m='1970080'>a</span> <span m='1970140'>sum</span>
  <span m='1970440'>from</span> <span m='1970620'>0</span> <span
  m='1970950'>to</span> <span m='1971040'>N</span> <span m='1971160'>over</span>
  <span m='1971400'>2</span> <span m='1971610'>minus</span> <span
  m='1972030'>1,</span> <span m='1972510'>it's</span> <span m='1972990'>a</span>
  <span m='1973130'>modified</span> <span m='1973890'>input</span> <span
  m='1974340'>sequence,</span> <span m='1975570'>but</span> <span
  m='1975900'>it's</span> <span m='1976140'>not,</span> <span
  m='1976470'>in</span> <span m='1976590'>fact,</span> <span
  m='1976905'>an</span> <span m='1977220'>N-over-2-point</span> <span
  m='1978110'>DFT.</span> <span m='1978930'>And</span> <span
  m='1979050'>the</span> <span m='1979140'>reason</span> <span
  m='1979590'>that</span> <span m='1979740'>it</span> <span
  m='1979830'>isn't</span> <span m='1980820'>is</span> <span
  m='1981210'>that</span> <span m='1982050'>this</span> <span
  m='1982410'>is</span> <span m='1982650'>W</span> <span m='1982945'>sub</span>
  <span m='1983240'>N</span> <span m='1983500'>to</span> <span
  m='1983650'>the</span> <span m='1983820'>nk</span> <span
  m='1985200'>whereas</span> <span m='1985860'>if</span> <span
  m='1986010'>it</span> <span m='1986100'>was</span> <span m='1986340'>an</span>
  <span m='1986490'>N-over-2-point</span> <span m='1987360'>DFT,</span> <span
  m='1988320'>this</span> <span m='1988530'>would</span> <span
  m='1988710'>be</span> <span m='1988990'>W</span> <span m='1989315'>sub</span>
  <span m='1990390'>capital</span> <span m='1990840'>N</span> <span
  m='1991050'>over</span> <span m='1991320'>2</span> <span m='1991830'>to</span>
  <span m='1992130'>the</span> <span m='1992280'>nk.</span> </p><p><span
  m='1994170'>However,</span> <span m='1994890'>let's</span> <span
  m='1995460'>look</span> <span m='1995850'>at</span> <span
  m='1996060'>these</span> <span m='1996990'>DFT</span> <span
  m='1997560'>points</span> <span m='1998580'>for</span> <span
  m='1998730'>two</span> <span m='1999390'>separate</span> <span
  m='1999810'>cases,</span> <span m='2001040'>one</span> <span
  m='2002000'>being</span> <span m='2002780'>that</span> <span
  m='2003080'>for</span> <span m='2003260'>which</span> <span
  m='2003800'>the</span> <span m='2004430'>index,</span> <span
  m='2005030'>the</span> <span m='2005180'>output</span> <span
  m='2005510'>index,</span> <span m='2005830'>is</span> <span
  m='2006050'>even</span> <span m='2007190'>and</span> <span
  m='2007400'>the</span> <span m='2007490'>second</span> <span
  m='2008270'>for</span> <span m='2008390'>which</span> <span
  m='2008750'>the</span> <span m='2008930'>output</span> <span
  m='2009290'>index</span> <span m='2009630'>is</span> <span
  m='2009870'>odd.</span> <span m='2010970'>The</span> <span
  m='2011120'>output</span> <span m='2011450'>index</span> <span
  m='2011705'>is</span> <span m='2011960'>even,</span> <span
  m='2013040'>then</span> <span m='2013430'>we</span> <span
  m='2013580'>can</span> <span m='2013760'>think</span> <span
  m='2014030'>of</span> <span m='2014150'>that</span> <span
  m='2014540'>as</span> <span m='2015050'>indexing</span> <span
  m='2015680'>through</span> <span m='2015920'>the</span> <span
  m='2016040'>DFT</span> <span m='2016610'>points</span> <span
  m='2018350'>with</span> <span m='2018920'>an</span> <span
  m='2019040'>argument</span> <span m='2019700'>x</span> <span
  m='2019970'>of</span> <span m='2020090'>2r,</span> <span
  m='2021140'>where</span> <span m='2021380'>r</span> <span
  m='2021980'>ranges</span> <span m='2022580'>from</span> <span
  m='2022790'>0</span> <span m='2023810'>to</span> <span m='2024110'>N</span>
  <span m='2024290'>over</span> <span m='2024500'>2</span> <span
  m='2024710'>minus</span> <span m='2025160'>1.</span> <span
  m='2026240'>And</span> <span m='2026840'>we</span> <span
  m='2026990'>then</span> <span m='2027230'>have</span> <span
  m='2027920'>this</span> <span m='2028160'>sum</span> <span
  m='2029760'>since</span> <span m='2030500'>k</span> <span
  m='2030740'>is</span> <span m='2030890'>even,</span> <span
  m='2031250'>minus</span> <span m='2031580'>1</span> <span
  m='2031760'>to</span> <span m='2031880'>the</span> <span m='2032000'>k</span>
  <span m='2032540'>is</span> <span m='2032930'>positive</span> <span
  m='2034200'>and</span> <span m='2034490'>we</span> <span
  m='2034670'>have</span> <span m='2034910'>then</span> <span
  m='2035800'>this</span> <span m='2035960'>sum</span> <span
  m='2036530'>that</span> <span m='2036650'>I've</span> <span
  m='2036800'>indicated</span> <span m='2037340'>here,</span> <span
  m='2038630'>whereas</span> <span m='2039590'>for</span> <span
  m='2039830'>k</span> <span m='2040250'>odd,</span> <span m='2041630'>we</span>
  <span m='2041930'>choose</span> <span m='2042380'>an</span> <span
  m='2042470'>index</span> <span m='2043310'>2r</span> <span
  m='2043790'>plus</span> <span m='2044150'>1,</span> <span
  m='2045550'>where</span> <span m='2045920'>again</span> <span
  m='2046430'>r</span> <span m='2046670'>ranges</span> <span
  m='2047240'>from</span> <span m='2047450'>0</span> <span m='2048139'>to</span>
  <span m='2048530'>N</span> <span m='2048710'>over</span> <span
  m='2048949'>2</span> <span m='2049159'>minus</span> <span
  m='2049580'>1.</span> <span m='2050820'>And</span> <span
  m='2050960'>because</span> <span m='2051860'>k</span> <span
  m='2052280'>is</span> <span m='2052520'>odd,</span> <span
  m='2053570'>what</span> <span m='2053900'>results</span> <span
  m='2054380'>in</span> <span m='2054469'>the</span> <span
  m='2054560'>sum</span> <span m='2055190'>is</span> <span m='2055610'>a</span>
  <span m='2055790'>subtraction</span> <span m='2057080'>rather</span> <span
  m='2057409'>than</span> <span m='2057620'>an</span> <span
  m='2057739'>addition.</span> <span m='2059580'>And</span> <span
  m='2060230'>then</span> <span m='2060889'>we</span> <span
  m='2061070'>have</span> <span m='2061429'>substituting</span> <span
  m='2062210'>in</span> <span m='2062360'>also.</span> <span
  m='2062780'>We</span> <span m='2062900'>have</span> <span m='2063100'>W
  sub</span> <span m='2063550'>capital</span> <span m='2063989'>N</span> <span
  m='2064159'>to</span> <span m='2064310'>the</span> <span
  m='2064400'>little</span> <span m='2064699'>n</span> <span
  m='2065310'>times</span> <span m='2065550'>W</span> <span
  m='2065800'>sub</span> <span m='2066110'>capital</span> <span m='2066560'>N
  to</span> <span m='2066800'>the</span> <span m='2066980'>2rn.</span>
  </p><p><span m='2069610'>Now,</span> <span m='2070179'>finally,</span> <span
  m='2070810'>we</span> <span m='2070989'>can</span> <span
  m='2071139'>take</span> <span m='2071380'>advantage</span> <span
  m='2071920'>of</span> <span m='2072040'>the</span> <span
  m='2072130'>fact</span> <span m='2073750'>that</span> <span
  m='2074560'>W</span> <span m='2074910'>sub</span> <span m='2075260'>N
  to</span> <span m='2075400'>the</span> <span m='2075520'>2rn</span> <span
  m='2076870'>can</span> <span m='2077050'>be</span> <span
  m='2077170'>written</span> <span m='2077620'>in</span> <span
  m='2077830'>terms</span> <span m='2078370'>of</span> <span
  m='2078650'>W</span> <span m='2078960'>sub</span> <span
  m='2079270'>capital</span> <span m='2079525'>N</span> <span
  m='2079929'>over</span> <span m='2080179'>2.</span> <span
  m='2081159'>In</span> <span m='2081250'>particular,</span> <span
  m='2082380'>W</span> <span m='2082840'>sub</span> <span
  m='2082929'>capital</span> <span m='2083199'>N</span> <span
  m='2084010'>to</span> <span m='2084130'>the</span> <span
  m='2084219'>2rn</span> <span m='2085900'>is</span> <span
  m='2086050'>equal</span> <span m='2086440'>to</span> <span
  m='2086800'>W</span> <span m='2087639'>sub</span> <span
  m='2087850'>capital</span> <span m='2088389'>N</span> <span
  m='2088510'>over</span> <span m='2088719'>2</span> <span m='2089370'>to</span>
  <span m='2089560'>the</span> <span m='2089739'>rn.</span> <span
  m='2091150'>And</span> <span m='2091840'>that</span> <span
  m='2092230'>follows</span> <span m='2092860'>as</span> <span
  m='2093070'>it</span> <span m='2093130'>did</span> <span
  m='2094239'>and</span> <span m='2094480'>we</span> <span
  m='2094570'>utilize</span> <span m='2095080'>that</span> <span
  m='2095290'>fact</span> <span m='2095650'>also</span> <span
  m='2096130'>in</span> <span m='2096219'>deriving</span> <span
  m='2096639'>the</span> <span m='2096730'>decimation</span> <span
  m='2097330'>in</span> <span m='2097420'>time</span> <span
  m='2097720'>form</span> <span m='2098020'>of</span> <span
  m='2098110'>the</span> <span m='2098260'>algorithm.</span> <span
  m='2099400'>It</span> <span m='2099610'>follows</span> <span
  m='2100000'>simply</span> <span m='2100420'>by</span> <span
  m='2100720'>substituting</span> <span m='2101560'>in</span> <span
  m='2102160'>to</span> <span m='2102580'>the</span> <span
  m='2102730'>expression</span> <span m='2103420'>for</span> <span
  m='2103870'>W</span> <span m='2104080'>sub</span> <span
  m='2104470'>capital</span> <span m='2104730'>N.</span> </p><p><span
  m='2107020'>Finally</span> <span m='2107560'>utilizing</span> <span
  m='2108340'>this,</span> <span m='2110910'>we</span> <span
  m='2111570'>recognize</span> <span m='2113520'>that</span> <span
  m='2114300'>for</span> <span m='2114570'>the</span> <span
  m='2114690'>computation</span> <span m='2115860'>of</span> <span
  m='2116040'>the</span> <span m='2116130'>DFT</span> <span
  m='2117930'>for</span> <span m='2118290'>that</span> <span
  m='2118560'>the</span> <span m='2118950'>output</span> <span
  m='2119550'>index</span> <span m='2120240'>even,</span> <span
  m='2122720'>the</span> <span m='2122850'>computation</span> <span
  m='2124350'>can</span> <span m='2124530'>be</span> <span
  m='2124680'>reduced</span> <span m='2125130'>to</span> <span
  m='2125280'>a</span> <span m='2125340'>sum</span> <span m='2126750'>of</span>
  <span m='2126870'>a</span> <span m='2126900'>sequence</span> <span
  m='2127470'>g</span> <span m='2127710'>of</span> <span m='2127860'>n,</span>
  <span m='2128400'>where</span> <span m='2128775'>g</span> <span
  m='2129150'>of</span> <span m='2129270'>n</span> <span m='2129660'>is</span>
  <span m='2130140'>the</span> <span m='2130260'>sum</span> <span
  m='2130740'>of</span> <span m='2130980'>the</span> <span
  m='2131100'>first</span> <span m='2131460'>half</span> <span
  m='2131970'>and</span> <span m='2132090'>the</span> <span
  m='2132180'>last</span> <span m='2132570'>half</span> <span
  m='2133380'>of</span> <span m='2133560'>the</span> <span
  m='2133710'>input</span> <span m='2134130'>data</span> <span
  m='2134430'>points.</span> <span m='2135930'>That</span> <span
  m='2136230'>multiplied</span> <span m='2137010'>by</span> <span
  m='2137220'>W</span> <span m='2137630'>sub</span> <span
  m='2137790'>capital</span> <span m='2138270'>N</span> <span
  m='2138390'>over</span> <span m='2138680'>2</span> <span m='2139110'>to
  the</span> <span m='2139290'>rn.</span> </p><p><span m='2142130'>Well,</span>
  <span m='2142760'>this</span> <span m='2144180'>is</span> <span
  m='2144680'>now</span> <span m='2145870'>an</span> <span
  m='2146030'>N-over-2-point</span> <span m='2147080'>discrete</span> <span
  m='2147500'>Fourier</span> <span m='2147920'>transform.</span> <span
  m='2149180'>It</span> <span m='2149300'>involves</span> <span
  m='2149960'>N-over-2-points</span> <span m='2152060'>and</span> <span
  m='2152900'>the</span> <span m='2152990'>powers</span> <span
  m='2153560'>of</span> <span m='2153710'>W</span> <span
  m='2154160'>involved</span> <span m='2154850'>are</span> <span
  m='2155570'>the</span> <span m='2155660'>appropriate</span> <span
  m='2156230'>powers</span> <span m='2156650'>of</span> <span
  m='2156750'>W</span> <span m='2157610'>for--</span> <span
  m='2158750'>or</span> <span m='2159230'>rather</span> <span
  m='2159530'>the</span> <span m='2159650'>W</span> <span m='2160670'>is</span>
  <span m='2160820'>involved</span> <span m='2161180'>is</span> <span
  m='2161300'>the</span> <span m='2161390'>appropriate</span> <span
  m='2161910'>W</span> <span m='2162355'>for</span> <span m='2162800'>an</span>
  <span m='2163160'>N-over-2-point</span> <span m='2164480'>DFT.</span> <span
  m='2165590'>That's</span> <span m='2165890'>indicated</span> <span
  m='2166460'>by</span> <span m='2166640'>this</span> <span
  m='2166780'>subscript</span> <span m='2167380'>N</span> <span
  m='2167540'>over</span> <span m='2167750'>2.</span> <span
  m='2169540'>So</span> <span m='2170170'>this</span> <span
  m='2170410'>is</span> <span m='2170560'>to</span> <span
  m='2170680'>compute</span> <span m='2171030'>the</span> <span
  m='2171220'>even</span> <span m='2171490'>numbered</span> <span
  m='2171850'>points.</span> </p><p><span m='2173380'>To</span> <span
  m='2173500'>compute</span> <span m='2173890'>the</span> <span
  m='2174070'>odd</span> <span m='2174280'>numbered</span> <span
  m='2174640'>points,</span> <span m='2175720'>we</span> <span
  m='2175930'>have</span> <span m='2176380'>a</span> <span
  m='2176470'>similar</span> <span m='2177290'>expression.</span> <span
  m='2178540'>We</span> <span m='2178690'>have</span> <span
  m='2179050'>the</span> <span m='2179140'>sum</span> <span
  m='2179680'>of</span> <span m='2180100'>h</span> <span m='2180520'>of n</span>
  <span m='2181690'>times</span> <span m='2182020'>W</span> <span
  m='2182440'>sub</span> <span m='2182530'>capital</span> <span
  m='2183040'>N</span> <span m='2183750'>to</span> <span m='2183880'>the</span>
  <span m='2184060'>n,</span> <span m='2185200'>and</span> <span
  m='2185340'>that</span> <span m='2185560'>times</span> <span
  m='2185920'>W</span> <span m='2186230'>sub N</span> <span
  m='2186460'>over</span> <span m='2186760'>2 to</span> <span
  m='2187150'>the</span> <span m='2187300'>rn,</span> <span
  m='2189010'>where</span> <span m='2189550'>h</span> <span
  m='2189850'>of</span> <span m='2189950'>n</span> <span m='2190460'>is</span>
  <span m='2191260'>the</span> <span m='2191440'>difference</span> <span
  m='2192310'>between</span> <span m='2193240'>the</span> <span
  m='2193360'>first</span> <span m='2193720'>half</span> <span
  m='2193990'>of</span> <span m='2194080'>the</span> <span
  m='2194200'>data</span> <span m='2194470'>points</span> <span
  m='2195160'>and</span> <span m='2195280'>the</span> <span
  m='2195370'>last</span> <span m='2195700'>half</span> <span
  m='2195970'>of</span> <span m='2196030'>the</span> <span
  m='2196120'>data</span> <span m='2196390'>points.</span> <span
  m='2198360'>So</span> <span m='2198540'>basically,</span> <span
  m='2199470'>following</span> <span m='2199920'>this</span> <span
  m='2200100'>strategy,</span> <span m='2201430'>what</span> <span
  m='2201510'>this</span> <span m='2202140'>says</span> <span
  m='2203280'>is</span> <span m='2203490'>that</span> <span
  m='2203970'>we</span> <span m='2204120'>can</span> <span
  m='2204390'>compute</span> <span m='2205290'>the</span> <span
  m='2205380'>discrete</span> <span m='2205800'>Fourier</span> <span
  m='2206210'>transform</span> <span m='2207870'>by</span> <span
  m='2208830'>forming</span> <span m='2209280'>a</span> <span
  m='2209340'>subsequence,</span> <span m='2210420'>which</span> <span
  m='2210660'>is</span> <span m='2210780'>the</span> <span
  m='2210900'>sum</span> <span m='2211290'>of</span> <span
  m='2211410'>the</span> <span m='2211500'>first</span> <span
  m='2211800'>and</span> <span m='2211920'>last</span> <span
  m='2212250'>half</span> <span m='2212670'>of</span> <span
  m='2212850'>the</span> <span m='2212940'>points,</span> <span
  m='2214620'>and</span> <span m='2214800'>computing</span> <span
  m='2215430'>the</span> <span m='2215580'>N-over-2-point</span> <span
  m='2216270'>DFT</span> <span m='2216990'>of</span> <span
  m='2217110'>that,</span> <span m='2218970'>and</span> <span
  m='2219090'>then</span> <span m='2219420'>forming</span> <span
  m='2220200'>a</span> <span m='2220560'>sequence,</span> <span
  m='2221470'>which</span> <span m='2221700'>is</span> <span
  m='2221880'>the</span> <span m='2222030'>difference</span> <span
  m='2222720'>of</span> <span m='2222870'>the</span> <span
  m='2222960'>first</span> <span m='2223290'>and</span> <span
  m='2223360'>the</span> <span m='2223440'>last</span> <span
  m='2223800'>half</span> <span m='2224220'>of</span> <span
  m='2224640'>the</span> <span m='2224790'>input</span> <span
  m='2225150'>points,</span> <span m='2226290'>multiplying</span> <span
  m='2227010'>that</span> <span m='2227280'>by</span> <span m='2227460'>W</span>
  <span m='2227760'>sub</span> <span m='2228060'>capital</span> <span
  m='2228540'>N</span> <span m='2228870'>to</span> <span m='2229140'>the</span>
  <span m='2229230'>little</span> <span m='2229500'>n,</span> <span
  m='2230640'>and</span> <span m='2231330'>computing</span> <span
  m='2232080'>the</span> <span m='2232410'>N-over-2-point</span> <span
  m='2233714'>DFT</span> <span m='2234570'>of</span> <span
  m='2234720'>that.</span> <span m='2236270'>And</span> <span
  m='2237080'>if</span> <span m='2237530'>you</span> <span
  m='2237710'>count</span> <span m='2238100'>up</span> <span
  m='2238610'>the</span> <span m='2238700'>number</span> <span
  m='2239060'>of</span> <span m='2239570'>operations</span> <span
  m='2240290'>involved,</span> <span m='2240920'>multiplications</span> <span
  m='2241790'>and</span> <span m='2241880'>additions,</span> <span
  m='2242900'>you</span> <span m='2243010'>will</span> <span
  m='2243170'>find</span> <span m='2243770'>that</span> <span
  m='2244370'>there</span> <span m='2244550'>is</span> <span
  m='2244670'>exactly</span> <span m='2245240'>the</span> <span
  m='2245360'>same</span> <span m='2245630'>computational</span> <span
  m='2246440'>efficiency</span> <span m='2247160'>implied</span> <span
  m='2248150'>in</span> <span m='2248480'>this decomposition</span> <span
  m='2249470'>as</span> <span m='2249680'>there</span> <span
  m='2249860'>was</span> <span m='2250280'>as</span> <span m='2250490'>we</span>
  <span m='2250610'>went</span> <span m='2250790'>through</span> <span
  m='2250970'>the</span> <span m='2251060'>decimation</span> <span
  m='2251910'>in</span> <span m='2252020'>time</span> <span
  m='2252380'>form</span> <span m='2252680'>of</span> <span
  m='2252740'>the</span> <span m='2252890'>algorithm.</span> </p><p><span
  m='2255800'>So</span> <span m='2256370'>this</span> <span
  m='2256700'>then</span> <span m='2257180'>is</span> <span
  m='2257870'>the</span> <span m='2257990'>basis</span> <span
  m='2258800'>for</span> <span m='2259220'>the</span> <span
  m='2259490'>decimation</span> <span m='2260330'>in</span> <span
  m='2260510'>time</span> <span m='2261470'>form</span> <span
  m='2262040'>of</span> <span m='2263000'>the</span> <span
  m='2263300'>computation</span> <span m='2265730'>and</span> <span
  m='2266180'>it</span> <span m='2266390'>basically</span> <span
  m='2267440'>states</span> <span m='2268940'>that</span> <span
  m='2269480'>we</span> <span m='2269720'>would</span> <span
  m='2270560'>compute</span> <span m='2271310'>the</span> <span
  m='2271670'>discrete</span> <span m='2272150'>Fourier</span> <span
  m='2272540'>transform</span> <span m='2274430'>by</span> <span
  m='2275330'>first</span> <span m='2276230'>forming</span> <span
  m='2276890'>a</span> <span m='2277400'>subsequence,</span> <span
  m='2280190'>which</span> <span m='2280460'>we</span> <span
  m='2280610'>denoted</span> <span m='2281060'>as</span> <span
  m='2281240'>g,</span> <span m='2282440'>which</span> <span
  m='2282620'>we</span> <span m='2282770'>obtain</span> <span
  m='2283310'>by</span> <span m='2283610'>adding</span> <span
  m='2284210'>the</span> <span m='2284360'>first</span> <span
  m='2284720'>half</span> <span m='2285140'>of</span> <span
  m='2285380'>the</span> <span m='2285560'>input</span> <span
  m='2285920'>points</span> <span m='2286400'>to</span> <span
  m='2286520'>the</span> <span m='2286610'>last</span> <span
  m='2286970'>half</span> <span m='2287270'>of</span> <span
  m='2287330'>the</span> <span m='2287480'>input</span> <span
  m='2287810'>points,</span> <span m='2289100'>and</span> <span
  m='2289550'>implementing</span> <span m='2289940'>an</span> <span
  m='2290330'>N-over-2-point</span> <span m='2291370'>DFT</span> <span
  m='2292250'>of</span> <span m='2292370'>that</span> <span
  m='2294340'>to</span> <span m='2294520'>obtain</span> <span
  m='2295240'>the</span> <span m='2295480'>even</span> <span
  m='2295870'>numbered</span> <span m='2297910'>output</span> <span
  m='2298390'>points.</span> <span m='2300080'>And</span> <span
  m='2300100'>then</span> <span m='2300520'>we</span> <span
  m='2300730'>would</span> <span m='2300940'>subtract</span> <span
  m='2301960'>the</span> <span m='2302080'>first</span> <span
  m='2302440'>half</span> <span m='2302830'>of</span> <span
  m='2302980'>the</span> <span m='2303100'>input</span> <span
  m='2303460'>points</span> <span m='2304480'>from</span> <span
  m='2304690'>the</span> <span m='2304750'>last</span> <span
  m='2305110'>half</span> <span m='2305410'>of</span> <span
  m='2305500'>the</span> <span m='2305620'>input</span> <span
  m='2305980'>points,</span> <span m='2307360'>multiply</span> <span
  m='2308500'>that</span> <span m='2309040'>subsequence,</span> <span
  m='2309790'>h,</span> <span m='2310510'>by</span> <span
  m='2311080'>successive</span> <span m='2311680'>powers</span> <span
  m='2312160'>of</span> <span m='2312250'>W,</span> <span
  m='2314140'>compute</span> <span m='2314470'>an</span> <span
  m='2314800'>N-over-2-point</span> <span m='2316390'>DFT</span> <span
  m='2317380'>of</span> <span m='2317530'>that,</span> <span
  m='2318580'>and</span> <span m='2319150'>the</span> <span
  m='2319300'>result</span> <span m='2319900'>would</span> <span
  m='2320110'>then</span> <span m='2320380'>be</span> <span
  m='2321010'>the</span> <span m='2321190'>odd</span> <span
  m='2321490'>numbered</span> <span m='2322660'>output</span> <span
  m='2323080'>points.</span> </p><p><span m='2324530'>Well,</span> <span
  m='2324970'>just</span> <span m='2325270'>as</span> <span
  m='2325390'>we</span> <span m='2325510'>did</span> <span
  m='2325810'>with</span> <span m='2325990'>the</span> <span
  m='2326140'>decimation</span> <span m='2326800'>in</span> <span
  m='2326890'>time</span> <span m='2327220'>form</span> <span
  m='2327550'>of</span> <span m='2327640'>the</span> <span
  m='2327790'>algorithm,</span> <span m='2329020'>we</span> <span
  m='2329200'>can</span> <span m='2329740'>continue</span> <span
  m='2330610'>this</span> <span m='2331090'>procedure.</span> <span
  m='2331790'>In</span> <span m='2331810'>other</span> <span
  m='2331990'>words,</span> <span m='2332360'>we</span> <span
  m='2332410'>can</span> <span m='2332560'>decompose</span> <span
  m='2333760'>the</span> <span m='2333880'>N-over-2-point</span> <span
  m='2334780'>DFTs</span> <span m='2336040'>into</span> <span
  m='2336540'>N-over-4-point</span> <span m='2337396'>DFTs</span> <span
  m='2338230'>by</span> <span m='2338470'>adding</span> <span
  m='2338800'>the</span> <span m='2338890'>first</span> <span
  m='2339190'>half</span> <span m='2339940'>of</span> <span
  m='2340060'>the</span> <span m='2340180'>input</span> <span
  m='2340510'>points</span> <span m='2340870'>here</span> <span
  m='2341050'>to</span> <span m='2341170'>the</span> <span
  m='2341260'>last</span> <span m='2341590'>half,</span> <span
  m='2341890'>et</span> <span m='2342190'>cetera.</span> <span
  m='2343030'>As</span> <span m='2343210'>we</span> <span
  m='2343330'>proceed</span> <span m='2343750'>through,</span> <span
  m='2344150'>we</span> <span m='2344320'>would</span> <span
  m='2344470'>then</span> <span m='2346030'>develop</span> <span
  m='2346480'>a</span> <span m='2346540'>flow</span> <span
  m='2346840'>graph</span> <span m='2347710'>in</span> <span
  m='2347800'>which</span> <span m='2348070'>we</span> <span
  m='2348250'>would</span> <span m='2348400'>compute</span> <span
  m='2348850'>first</span> <span m='2349570'>the</span> <span
  m='2349720'>even</span> <span m='2350050'>numbered</span> <span
  m='2350410'>of</span> <span m='2350500'>the</span> <span
  m='2350620'>even</span> <span m='2350890'>numbered</span> <span
  m='2351190'>output</span> <span m='2351580'>points</span> <span
  m='2352030'>and</span> <span m='2352120'>then</span> <span
  m='2352270'>the</span> <span m='2352390'>odd</span> <span
  m='2352630'>numbered</span> <span m='2352950'>of</span> <span
  m='2353410'>the</span> <span m='2354010'>even</span> <span
  m='2354460'>numbered</span> <span m='2354850'>output</span> <span
  m='2355270'>points,</span> <span m='2356230'>et</span> <span
  m='2356650'>cetera.</span> <span m='2357700'>So</span> <span
  m='2357910'>you</span> <span m='2358060'>can</span> <span
  m='2358180'>imagine</span> <span m='2358750'>that</span> <span
  m='2358930'>as</span> <span m='2359080'>we</span> <span
  m='2359200'>proceed</span> <span m='2359620'>through</span> <span
  m='2359890'>this,</span> <span m='2360670'>we'll</span> <span
  m='2360790'>get</span> <span m='2360970'>a</span> <span
  m='2361030'>flow</span> <span m='2361330'>graph.</span> </p><p><span
  m='2362950'>Similar</span> <span m='2363430'>in</span> <span
  m='2363550'>many</span> <span m='2363790'>respects</span> <span
  m='2364330'>to</span> <span m='2364450'>the</span> <span
  m='2364540'>flow</span> <span m='2364810'>graph</span> <span
  m='2365140'>that</span> <span m='2365260'>we</span> <span
  m='2365380'>developed</span> <span m='2365860'>for</span> <span
  m='2365980'>the</span> <span m='2366100'>decimation</span> <span
  m='2366730'>in</span> <span m='2366850'>time</span> <span
  m='2367180'>form</span> <span m='2367480'>of</span> <span
  m='2367570'>the</span> <span m='2367720'>algorithm,</span> <span
  m='2368440'>and</span> <span m='2368590'>furthermore,</span> <span
  m='2369730'>the</span> <span m='2369820'>flow</span> <span
  m='2370090'>graph</span> <span m='2370570'>as</span> <span
  m='2370750'>it</span> <span m='2370810'>naturally</span> <span
  m='2371350'>develops</span> <span m='2371890'>this</span> <span
  m='2372130'>way</span> <span m='2373000'>will</span> <span
  m='2373600'>result</span> <span m='2374200'>in</span> <span
  m='2375100'>data,</span> <span m='2376510'>the</span> <span
  m='2376750'>DFT</span> <span m='2377380'>output,</span> <span
  m='2378160'>sorted</span> <span m='2378970'>in</span> <span
  m='2379360'>a</span> <span m='2379570'>bit</span> <span
  m='2379780'>reversed</span> <span m='2380230'>order.</span> <span
  m='2381880'>So</span> <span m='2382720'>continuing</span> <span
  m='2383350'>on</span> <span m='2383710'>then,</span> <span
  m='2384790'>here</span> <span m='2385150'>is</span> <span
  m='2385390'>the</span> <span m='2385510'>decomposition</span> <span
  m='2386860'>with</span> <span m='2387370'>the</span> <span
  m='2387640'>N-over-2-point</span> <span m='2388476'>DFTs</span> <span
  m='2389320'>broken</span> <span m='2389950'>into</span> <span
  m='2390610'>N-over-4-point</span> <span m='2391603'>DFTs,</span> <span
  m='2393520'>and</span> <span m='2394180'>we</span> <span
  m='2395140'>are</span> <span m='2395650'>now</span> <span
  m='2396430'>computing</span> <span m='2396910'>the</span> <span
  m='2396970'>even</span> <span m='2397210'>numbered</span> <span
  m='2397510'>of</span> <span m='2397570'>the</span> <span
  m='2397690'>even</span> <span m='2397930'>numbered</span> <span
  m='2398500'>output</span> <span m='2398890'>points</span> <span
  m='2399280'>first.</span> </p><p><span m='2400800'>The</span> <span
  m='2400980'>N-over-4-point</span> <span m='2401790'>DFTs,</span> <span
  m='2402970'>if</span> <span m='2403330'>we</span> <span
  m='2403540'>consider</span> <span m='2404290'>the</span> <span
  m='2404770'>specific</span> <span m='2405340'>case</span> <span m='2405730'>of
  N</span> <span m='2405970'>equals</span> <span m='2406360'>8,</span> <span
  m='2406880'>the</span> <span m='2407130'>N-over-4-point</span> <span
  m='2408090'>DFTs</span> <span m='2408850'>are</span> <span
  m='2409180'>just</span> <span m='2409390'>simply</span> <span
  m='2410435'>2-point</span> <span m='2411263'>DFTs,</span> <span
  m='2412570'>which</span> <span m='2413380'>involve,</span> <span
  m='2414010'>as</span> <span m='2414220'>they</span> <span
  m='2414370'>did</span> <span m='2414760'>in</span> <span
  m='2415000'>the</span> <span m='2415630'>decimation</span> <span
  m='2416500'>in</span> <span m='2416620'>time</span> <span
  m='2417520'>form</span> <span m='2417850'>of</span> <span
  m='2417940'>the</span> <span m='2418090'>algorithm,</span> <span
  m='2419170'>just</span> <span m='2419620'>simply</span> <span
  m='2420040'>a</span> <span m='2420100'>computation</span> <span
  m='2421090'>involving</span> <span m='2422350'>an</span> <span
  m='2422470'>addition</span> <span m='2423260'>and a</span> <span
  m='2423430'>subtraction.</span> <span m='2425050'>In</span> <span
  m='2425140'>other</span> <span m='2425290'>words,</span> <span
  m='2425600'>just</span> <span m='2425710'>a</span> <span
  m='2426160'>simple</span> <span m='2426550'>butterfly.</span> <span
  m='2428650'>So</span> <span m='2429310'>the</span> <span
  m='2429430'>resulting</span> <span m='2430000'>flow</span> <span
  m='2430270'>graph</span> <span m='2431830'>based</span> <span
  m='2432250'>on</span> <span m='2432760'>pursuing</span> <span
  m='2433300'>this</span> <span m='2433450'>strategy</span> <span
  m='2434050'>through</span> <span m='2434260'>the</span> <span
  m='2434380'>entire</span> <span m='2434770'>computation</span> <span
  m='2436360'>is</span> <span m='2436990'>as</span> <span
  m='2437260'>I've</span> <span m='2437410'>indicated</span> <span
  m='2438010'>here,</span> <span m='2438970'>which</span> <span
  m='2439390'>is</span> <span m='2440020'>one</span> <span
  m='2440290'>form</span> <span m='2441040'>of</span> <span
  m='2441520'>the</span> <span m='2441700'>decimation</span> <span
  m='2442480'>in</span> <span m='2442630'>frequency</span> <span
  m='2443860'>form</span> <span m='2444250'>of</span> <span
  m='2444370'>the</span> <span m='2444520'>algorithm.</span> </p><p><span
  m='2446400'>Notice</span> <span m='2447060'>that</span> <span
  m='2447600'>the</span> <span m='2447750'>input</span> <span
  m='2448260'>is</span> <span m='2448710'>in</span> <span
  m='2448890'>normal</span> <span m='2449280'>order,</span> <span
  m='2450550'>the</span> <span m='2450630'>output</span> <span
  m='2451380'>is</span> <span m='2451950'>in</span> <span m='2452130'>bit</span>
  <span m='2452340'>reversed</span> <span m='2452850'>order,</span> <span
  m='2454660'>the</span> <span m='2454750'>flow</span> <span
  m='2455020'>graph</span> <span m='2455560'>as</span> <span
  m='2456580'>it</span> <span m='2457420'>developed</span> <span
  m='2457960'>here,</span> <span m='2458560'>again,</span> <span
  m='2459010'>if</span> <span m='2459190'>we</span> <span
  m='2459340'>think</span> <span m='2459580'>of</span> <span
  m='2459700'>it</span> <span m='2459910'>as</span> <span m='2460510'>a</span>
  <span m='2461470'>computational</span> <span m='2463630'>strategy,</span>
  <span m='2465010'>a</span> <span m='2465280'>strategy</span> <span
  m='2465790'>for</span> <span m='2465970'>organizing</span> <span
  m='2466600'>the</span> <span m='2466690'>computation,</span> <span
  m='2468190'>again,</span> <span m='2469920'>corresponds</span> <span
  m='2470910'>to</span> <span m='2471390'>an</span> <span
  m='2471540'>in-place</span> <span m='2472140'>computation.</span> <span
  m='2473500'>It's</span> <span m='2473700'>an in-place</span> <span
  m='2474180'>computation</span> <span m='2475020'>because</span> <span
  m='2480030'>output</span> <span m='2480450'>nodes</span> <span
  m='2481230'>for</span> <span m='2481560'>a</span> <span
  m='2481650'>butterfly</span> <span m='2482370'>are</span> <span
  m='2482550'>horizontally</span> <span m='2483420'>adjacent</span> <span
  m='2484470'>to</span> <span m='2484590'>the</span> <span
  m='2484770'>input</span> <span m='2485130'>nodes</span> <span
  m='2485640'>of</span> <span m='2485760'>the</span> <span
  m='2485880'>butterfly.</span> </p><p><span m='2487950'>In</span> <span
  m='2488070'>many</span> <span m='2488310'>respects,</span> <span
  m='2489000'>in</span> <span m='2489150'>fact,</span> <span
  m='2489790'>it</span> <span m='2489840'>looks</span> <span
  m='2490500'>somewhat</span> <span m='2491280'>like</span> <span
  m='2491940'>the</span> <span m='2492240'>decimation</span> <span
  m='2493140'>in</span> <span m='2493290'>time</span> <span
  m='2494250'>form</span> <span m='2494580'>of</span> <span
  m='2494700'>the</span> <span m='2494850'>algorithm</span> <span
  m='2495600'>when</span> <span m='2496110'>we</span> <span
  m='2496320'>sorted</span> <span m='2496740'>things</span> <span
  m='2497010'>such</span> <span m='2497340'>that</span> <span
  m='2497490'>the</span> <span m='2497610'>input</span> <span
  m='2498450'>was</span> <span m='2498690'>in</span> <span
  m='2498780'>normal</span> <span m='2499140'>order</span> <span
  m='2499560'>and</span> <span m='2499710'>the</span> <span
  m='2499830'>output</span> <span m='2501120'>was</span> <span
  m='2501330'>in</span> <span m='2501450'>bit</span> <span
  m='2501660'>reversed</span> <span m='2502110'>order.</span> <span
  m='2503010'>In</span> <span m='2503130'>fact,</span> <span
  m='2503700'>there</span> <span m='2503910'>is</span> <span
  m='2504030'>a</span> <span m='2504120'>difference</span> <span
  m='2504750'>between</span> <span m='2505590'>this</span> <span
  m='2505770'>class</span> <span m='2506130'>of</span> <span
  m='2506250'>algorithms</span> <span m='2507000'>and</span> <span
  m='2507150'>the</span> <span m='2507210'>decimation</span> <span
  m='2507960'>in</span> <span m='2508110'>time</span> <span
  m='2508440'>form</span> <span m='2508770'>of</span> <span
  m='2508890'>the</span> <span m='2509070'>algorithm.</span> <span
  m='2510480'>One</span> <span m='2510930'>difference</span> <span
  m='2511710'>that</span> <span m='2512340'>I</span> <span
  m='2512520'>would</span> <span m='2513000'>just</span> <span
  m='2513240'>draw</span> <span m='2513510'>your</span> <span
  m='2513690'>attention</span> <span m='2514200'>to</span> <span
  m='2514410'>quickly</span> <span m='2515970'>is</span> <span
  m='2516150'>the</span> <span m='2516270'>fact</span> <span
  m='2517200'>that</span> <span m='2517710'>the</span> <span
  m='2517830'>butterflies</span> <span m='2519210'>in</span> <span
  m='2520350'>the</span> <span m='2520590'>decimation</span> <span
  m='2521340'>in</span> <span m='2521430'>frequency</span> <span
  m='2521970'>form</span> <span m='2522300'>of</span> <span
  m='2522390'>the</span> <span m='2522540'>algorithm,</span> <span
  m='2523170'>as</span> <span m='2523710'>we've</span> <span
  m='2523890'>just</span> <span m='2524100'>been</span> <span
  m='2524250'>talking</span> <span m='2524700'>about</span> <span
  m='2525060'>it,</span> <span m='2525630'>involve</span> <span
  m='2526350'>additions</span> <span m='2527250'>and</span> <span
  m='2527400'>subtractions,</span> <span m='2529640'>and</span> <span
  m='2530450'>the</span> <span m='2530600'>multiplication</span> <span
  m='2531440'>by</span> <span m='2531620'>powers</span> <span
  m='2532040'>of</span> <span m='2532130'>W</span> <span m='2532700'>is</span>
  <span m='2533360'>implemented</span> <span m='2533960'>on</span> <span
  m='2534110'>the</span> <span m='2534230'>output</span> <span
  m='2534800'>of</span> <span m='2534950'>the</span> <span
  m='2535040'>butterfly.</span> <span m='2536840'>Whereas</span> <span
  m='2537740'>for</span> <span m='2538340'>the</span> <span
  m='2538550'>decimation</span> <span m='2539510'>in</span> <span
  m='2539690'>time</span> <span m='2540380'>form</span> <span
  m='2540770'>of</span> <span m='2540860'>the</span> <span
  m='2541010'>algorithm,</span> <span m='2544260'>the</span> <span
  m='2545130'>multiplication</span> <span m='2546240'>by</span> <span
  m='2546510'>a</span> <span m='2546600'>power</span> <span
  m='2546990'>of</span> <span m='2547080'>W</span> <span m='2547530'>was</span>
  <span m='2547710'>implemented</span> <span m='2548280'>at</span> <span
  m='2548400'>the</span> <span m='2548550'>input</span> <span
  m='2548890'>to</span> <span m='2549000'>the</span> <span
  m='2549120'>butterfly</span> <span m='2550260'>followed</span> <span
  m='2550680'>by</span> <span m='2551280'>an</span> <span
  m='2551400'>addition</span> <span m='2552060'>and</span> <span
  m='2552180'>subtraction.</span> </p><p><span m='2553660'>So</span> <span
  m='2554430'>in</span> <span m='2554580'>fact,</span> <span
  m='2555550'>the</span> <span m='2556950'>decimation</span> <span
  m='2557610'>and</span> <span m='2557700'>frequency</span> <span
  m='2558750'>form</span> <span m='2559110'>of</span> <span
  m='2559200'>the</span> <span m='2559320'>algorithm</span> <span
  m='2560520'>as</span> <span m='2561060'>we've</span> <span
  m='2561270'>just</span> <span m='2561510'>developed</span> <span
  m='2562060'>it</span> <span m='2563310'>is</span> <span
  m='2563430'>somewhat</span> <span m='2563850'>different</span> <span
  m='2564750'>than</span> <span m='2565230'>the</span> <span
  m='2565320'>decimation</span> <span m='2565950'>in</span> <span
  m='2566070'>time</span> <span m='2566370'>form</span> <span
  m='2566700'>of</span> <span m='2566790'>the</span> <span
  m='2566940'>algorithm.</span> <span m='2568830'>As</span> <span
  m='2569040'>we'll</span> <span m='2569220'>see</span> <span
  m='2569670'>as</span> <span m='2570000'>we</span> <span
  m='2570390'>continue</span> <span m='2571140'>in</span> <span
  m='2571320'>the</span> <span m='2571410'>next</span> <span
  m='2571680'>lecture,</span> <span m='2572820'>there</span> <span
  m='2573210'>are</span> <span m='2573390'>modifications</span> <span
  m='2574560'>of</span> <span m='2575130'>this</span> <span
  m='2575340'>form</span> <span m='2575700'>of</span> <span
  m='2575790'>the</span> <span m='2575940'>algorithm</span> <span
  m='2577020'>just</span> <span m='2577320'>as</span> <span
  m='2577470'>there</span> <span m='2577620'>were</span> <span
  m='2577950'>for</span> <span m='2578130'>the</span> <span
  m='2578220'>decimation</span> <span m='2578820'>in</span> <span
  m='2578910'>time</span> <span m='2579240'>form</span> <span
  m='2579570'>of</span> <span m='2579690'>the</span> <span
  m='2579840'>algorithm.</span> <span m='2580950'>And</span> <span
  m='2581520'>we'll</span> <span m='2581760'>also</span> <span
  m='2582120'>see</span> <span m='2582600'>that</span> <span
  m='2582840'>in</span> <span m='2582960'>fact</span> <span
  m='2583710'>there</span> <span m='2584040'>is</span> <span
  m='2584940'>a</span> <span m='2586500'>very</span> <span
  m='2586800'>close</span> <span m='2587160'>relationship</span> <span
  m='2588270'>between</span> <span m='2589080'>these</span> <span
  m='2589290'>two</span> <span m='2589770'>forms</span> <span
  m='2590190'>of</span> <span m='2590280'>the</span> <span
  m='2590430'>algorithm,</span> <span m='2591330'>the</span> <span
  m='2591440'>relationship</span> <span m='2592230'>being</span> <span
  m='2592530'>suggested</span> <span m='2593580'>by</span> <span
  m='2593760'>properties</span> <span m='2594420'>of</span> <span
  m='2594510'>flow</span> <span m='2594780'>graphs</span> <span
  m='2595500'>that</span> <span m='2595920'>we've</span> <span
  m='2596790'>discussed</span> <span m='2597480'>in</span> <span
  m='2598050'>some</span> <span m='2598320'>of</span> <span
  m='2598440'>the</span> <span m='2599430'>previous</span> <span
  m='2599910'>lectures.</span> </p><p><span m='2601740'>So</span> <span
  m='2602250'>at</span> <span m='2602640'>this</span> <span
  m='2602850'>point,</span> <span m='2603340'>then</span> <span
  m='2604500'>we</span> <span m='2604920'>have</span> <span
  m='2605880'>concluded</span> <span m='2606390'>our</span> <span
  m='2606510'>discussion</span> <span m='2607140'>of</span> <span
  m='2607290'>the</span> <span m='2607380'>decimation</span> <span
  m='2608010'>in</span> <span m='2608130'>time</span> <span
  m='2609180'>forms</span> <span m='2609630'>of</span> <span
  m='2609720'>the</span> <span m='2609870'>algorithm,</span> <span
  m='2611010'>we've</span> <span m='2611160'>introduced</span> <span
  m='2612090'>the</span> <span m='2612240'>decimation</span> <span
  m='2612870'>in</span> <span m='2612960'>frequency</span> <span
  m='2614010'>form</span> <span m='2614310'>of</span> <span
  m='2614430'>the</span> <span m='2614580'>algorithm.</span> <span
  m='2615690'>In</span> <span m='2615810'>the</span> <span
  m='2615870'>next</span> <span m='2616140'>lecture,</span> <span
  m='2616990'>what</span> <span m='2617190'>I</span> <span
  m='2617280'>would</span> <span m='2617430'>like</span> <span
  m='2617640'>to</span> <span m='2617790'>do</span> <span m='2618240'>is</span>
  <span m='2619050'>continue</span> <span m='2619740'>on</span> <span
  m='2620010'>a</span> <span m='2620070'>discussion</span> <span
  m='2620850'>of</span> <span m='2621660'>the</span> <span
  m='2621810'>decimation</span> <span m='2622440'>in</span> <span
  m='2622530'>frequency</span> <span m='2623040'>forms,</span> <span
  m='2623940'>in</span> <span m='2624030'>particular</span> <span
  m='2625650'>discussing</span> <span m='2626610'>alternative</span> <span
  m='2627240'>forms</span> <span m='2628540'>which</span> <span
  m='2628890'>are</span> <span m='2629040'>similar</span> <span
  m='2629550'>to</span> <span m='2629700'>the</span> <span
  m='2629820'>alternative</span> <span m='2630390'>forms</span> <span
  m='2630750'>that</span> <span m='2630870'>we</span> <span
  m='2630990'>discussed</span> <span m='2631470'>for</span> <span
  m='2631590'>decimation</span> <span m='2632190'>in</span> <span
  m='2632280'>time.</span> <span m='2632580'>Thank</span> <span
  m='2632880'>you.</span> </p>
embedded_media:
  - uid: dfb5664fbf195e8514a75f8758b06a4d
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: MITRES_6_008S11_lec19.pdf
    title: MITRES_6_008S11_lec19.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-19-computation-of-the-discrete-fourier-transform-part-2/MITRES_6_008S11_lec19.pdf
  - uid: 68397e68c42c522fd1437d3791a00726
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: 4Gy1mik0tr4
  - uid: b2a6a939f42e8a9dab03dfc30aaccf26
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-19-computation-discrete/id481803782?i=108362008
  - uid: 8b50b231c06d51d56f6dd49ef7fb1fde
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec19_300k.mp4'
  - uid: 60b2123cfd3e89bb40b4bb6c0d53adab
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/4Gy1mik0tr4/default.jpg'
  - uid: 50c1989267a41f68fc682602b70cbc42
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: 4Gy1mik0tr4
  - uid: b9ac19c9ba6e5a761d6599281dce6594
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: 4Gy1mik0tr4.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-19-computation-of-the-discrete-fourier-transform-part-2/4Gy1mik0tr4.srt
  - uid: 79556faeac862e27193979411d70804a
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: 4Gy1mik0tr4.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-19-computation-of-the-discrete-fourier-transform-part-2/4Gy1mik0tr4.pdf
  - uid: fdaa9ba8a7a1b6693e9e88a5e52dcea9
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 5231d5b4176bad2ca8882492e45329f2
    parent_uid: 3293b56b46c3f0890692f41151c66665
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
