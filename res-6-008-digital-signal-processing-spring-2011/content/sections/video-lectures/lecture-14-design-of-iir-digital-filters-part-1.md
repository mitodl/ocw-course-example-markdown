---
order_index: null
title: 'Lecture 14: Design of IIR Digital Filters, Part 1'
template_type: Tabbed
uid: 839a64db7fb18dcca85023c4ccd0da51
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-14-design-of-iir-digital-filters-part-1
short_url: lecture-14-design-of-iir-digital-filters-part-1
inline_embed_id: '78880126lecture14:designofiirdigitalfilters,part136142450'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Transformation of analog filter designs to
  digital filter designs, approximation of derivatives by differences, impulse
  invariant design procedures.</p> <p><strong>Instructor:</strong> Prof. Alan V.
  Oppenheim</p>
related_resources_text: >-
  <p>Design of IIR Digital Filters, Part 1 (<a
  href="./resolveuid/70cf0d53f7ef869c6bbcfbb060aec824">PDF</a>)</p>
transcript: >-
  <p><span m='135'>The</span> <span m='180'>following</span> <span
  m='630'>content</span> <span m='1200'>is</span> <span m='1320'>provided</span>
  <span m='1770'>under</span> <span m='2009'>a</span> <span
  m='2070'>Creative</span> <span m='2490'>Commons</span> <span
  m='2910'>license.</span> <span m='4030'>Your</span> <span
  m='4200'>support</span> <span m='4680'>will</span> <span m='4860'>help</span>
  <span m='5100'>MIT</span> <span m='5550'>OpenCourseWare</span> <span
  m='6330'>continue</span> <span m='6850'>to</span> <span m='6960'>offer</span>
  <span m='7380'>high-quality</span> <span m='8100'>educational</span> <span
  m='8730'>resources</span> <span m='9330'>for</span> <span
  m='9510'>free.</span> <span m='10720'>To</span> <span m='10740'>make</span>
  <span m='10920'>a</span> <span m='10980'>donation</span> <span
  m='11730'>or</span> <span m='11940'>view</span> <span
  m='12390'>additional</span> <span m='12810'>materials</span> <span
  m='13320'>from</span> <span m='13500'>hundreds</span> <span
  m='13920'>of</span> <span m='14040'>MIT</span> <span m='14460'>courses,</span>
  <span m='15550'>visit</span> <span m='15780'>MIT</span> <span
  m='16200'>OpenCourseWare</span> <span m='17280'>at</span> <span
  m='17430'>ocw.mit.edu.</span> </p><p><span m='25439'>[MUSIC PLAYING]</span>
  </p><p></p><p><span m='56892'>ALAN OPPENHEIM:</span> <span
  m='57060'>Throughout</span> <span m='57420'>these</span> <span
  m='57630'>lectures,</span> <span m='58510'>we</span> <span
  m='58830'>have</span> <span m='59220'>been</span> <span
  m='59790'>considering</span> <span m='60660'>the</span> <span
  m='61170'>analysis</span> <span m='62010'>and</span> <span
  m='62160'>the</span> <span m='62280'>implementation</span> <span
  m='63330'>of</span> <span m='64319'>discrete</span> <span
  m='64739'>time</span> <span m='65370'>linear</span> <span
  m='65700'>shift</span> <span m='66000'>invariant</span> <span
  m='66540'>systems,</span> <span m='67200'>or</span> <span
  m='67800'>what</span> <span m='67980'>we've</span> <span m='68160'>been</span>
  <span m='68310'>referring</span> <span m='68730'>to</span> <span
  m='69090'>as</span> <span m='69480'>digital</span> <span
  m='69870'>filters.</span> <span m='71670'>In</span> <span
  m='71730'>this</span> <span m='71940'>lecture,</span> <span m='72610'>I</span>
  <span m='72660'>would</span> <span m='72810'>like</span> <span
  m='73080'>to</span> <span m='73560'>begin</span> <span m='73920'>the</span>
  <span m='74010'>discussion</span> <span m='74850'>of</span> <span
  m='75420'>the</span> <span m='75660'>design</span> <span m='76320'>of</span>
  <span m='76470'>digital</span> <span m='76830'>filters.</span> <span
  m='78840'>Now</span> <span m='79230'>the</span> <span
  m='79350'>rationale</span> <span m='80280'>for</span> <span
  m='80430'>digital</span> <span m='80820'>filters</span> <span
  m='81660'>is</span> <span m='82050'>exactly</span> <span m='82590'>the</span>
  <span m='82680'>same</span> <span m='83220'>as</span> <span
  m='83430'>it</span> <span m='83550'>is</span> <span m='84000'>for</span> <span
  m='84210'>analog</span> <span m='84660'>filters.</span> <span
  m='86160'>In</span> <span m='86250'>particular,</span> <span
  m='87300'>we</span> <span m='87600'>have</span> <span m='88080'>taken</span>
  <span m='88440'>advantage</span> <span m='89430'>several</span> <span
  m='89910'>times</span> <span m='91080'>of</span> <span m='91740'>the</span>
  <span m='92010'>important</span> <span m='92460'>property</span> <span
  m='93180'>of</span> <span m='93330'>linear</span> <span m='93690'>shift</span>
  <span m='94010'>in</span> <span m='94130'>variance</span> <span
  m='94600'>systems</span> <span m='95850'>that</span> <span
  m='96390'>complex</span> <span m='96990'>exponentials</span> <span
  m='98310'>are</span> <span m='98700'>eigenfunctions</span> <span
  m='99960'>of</span> <span m='100140'>this</span> <span m='100320'>class</span>
  <span m='100680'>of</span> <span m='100800'>systems.</span> <span
  m='101880'>In</span> <span m='102000'>other</span> <span
  m='102210'>words,</span> <span m='102790'>then</span> <span
  m='103080'>with</span> <span m='103230'>a</span> <span
  m='103290'>complex</span> <span m='103860'>exponential</span> <span
  m='104550'>input,</span> <span m='105810'>the</span> <span
  m='105990'>output</span> <span m='106890'>is</span> <span m='107040'>a</span>
  <span m='107070'>complex</span> <span m='107610'>exponential</span> <span
  m='108450'>of</span> <span m='108600'>the</span> <span m='108720'>same</span>
  <span m='108990'>complex</span> <span m='109590'>frequency</span> <span
  m='110820'>multiplied</span> <span m='111780'>by</span> <span
  m='111990'>the</span> <span m='112080'>system</span> <span
  m='112500'>function</span> <span m='113130'>H</span> <span m='113290'>v</span>
  <span m='113610'>to</span> <span m='113710'>the</span> <span
  m='113820'>j</span> <span m='114060'>omega.</span> <span m='115080'>Or</span>
  <span m='115470'>equivalently,</span> <span m='116700'>with</span> <span
  m='116880'>a</span> <span m='116910'>sinusoidal</span> <span
  m='117720'>input,</span> <span m='118830'>the</span> <span
  m='119010'>output</span> <span m='119640'>is</span> <span
  m='120120'>likewise</span> <span m='120660'>sinusoidal</span> <span
  m='121710'>with</span> <span m='121860'>the</span> <span
  m='121980'>same</span> <span m='122280'>frequency</span> <span
  m='123480'>but</span> <span m='123660'>with</span> <span m='123840'>a</span>
  <span m='123900'>change</span> <span m='124260'>in</span> <span
  m='124350'>amplitude</span> <span m='125250'>and</span> <span
  m='125370'>with</span> <span m='125510'>a</span> <span
  m='125550'>change</span> <span m='125940'>in</span> <span
  m='126030'>phase.</span> </p><p><span m='128100'>Now</span> <span
  m='128639'>what</span> <span m='129090'>this</span> <span
  m='129330'>property</span> <span m='130080'>of</span> <span
  m='130199'>linear</span> <span m='131190'>shift</span> <span
  m='131490'>invariant</span> <span m='132060'>systems</span> <span
  m='133380'>permits</span> <span m='133830'>us</span> <span
  m='134070'>to</span> <span m='134250'>consider</span> <span
  m='135450'>is</span> <span m='136110'>the</span> <span
  m='136230'>separation</span> <span m='137610'>of</span> <span
  m='137730'>signals</span> <span m='138930'>that</span> <span
  m='139080'>have</span> <span m='139230'>been</span> <span
  m='139410'>added</span> <span m='140040'>when</span> <span
  m='140220'>these</span> <span m='140430'>signals</span> <span
  m='141480'>occupy</span> <span m='142230'>different</span> <span
  m='142560'>frequency</span> <span m='143100'>bands.</span> <span
  m='144870'>Specifically,</span> <span m='145990'>we</span> <span
  m='146040'>can</span> <span m='146220'>consider</span> <span
  m='147720'>a</span> <span m='147810'>signal</span> <span
  m='148740'>composed</span> <span m='149520'>of</span> <span
  m='150060'>the</span> <span m='150180'>sum</span> <span m='150660'>of</span>
  <span m='150840'>two</span> <span m='151050'>signals,</span> <span
  m='152520'>one</span> <span m='152730'>of</span> <span m='152820'>which</span>
  <span m='153270'>we</span> <span m='153420'>want,</span> <span
  m='154470'>the</span> <span m='154620'>other</span> <span m='155010'>of</span>
  <span m='155190'>which</span> <span m='155490'>we</span> <span
  m='155640'>don't</span> <span m='155910'>want,</span> <span
  m='156240'>or</span> <span m='156360'>we</span> <span m='156510'>would</span>
  <span m='156630'>like</span> <span m='156840'>to</span> <span
  m='156930'>suppress.</span> <span m='158850'>And</span> <span
  m='159000'>if</span> <span m='159240'>those</span> <span m='159480'>two</span>
  <span m='159690'>signals</span> <span m='160620'>are</span> <span
  m='160890'>in</span> <span m='161040'>different</span> <span
  m='161370'>frequency</span> <span m='161940'>bands--</span> <span
  m='162390'>in</span> <span m='162480'>other</span> <span
  m='162690'>words,</span> <span m='163510'>their</span> <span
  m='163560'>spectra</span> <span m='165630'>occupy</span> <span
  m='166320'>different</span> <span m='167070'>segments</span> <span
  m='167820'>of</span> <span m='168600'>the</span> <span
  m='169500'>frequency</span> <span m='170130'>axis,</span> <span
  m='171360'>then</span> <span m='171960'>we</span> <span m='172110'>can</span>
  <span m='172320'>choose</span> <span m='172980'>the</span> <span
  m='173070'>system</span> <span m='173520'>function</span> <span
  m='174180'>for</span> <span m='174690'>the</span> <span
  m='174810'>linear</span> <span m='175140'>shift</span> <span
  m='175530'>invariant</span> <span m='175980'>system</span> <span
  m='177210'>so</span> <span m='177420'>that</span> <span m='177780'>it</span>
  <span m='178200'>is</span> <span m='178890'>unity</span> <span
  m='179700'>in</span> <span m='179850'>the</span> <span m='179940'>band</span>
  <span m='180270'>of</span> <span m='180360'>frequencies</span> <span
  m='181680'>that</span> <span m='182010'>we</span> <span m='182160'>want</span>
  <span m='182340'>to</span> <span m='182430'>keep</span> <span
  m='183180'>and</span> <span m='183330'>at</span> <span m='183450'>0</span>
  <span m='184080'>in</span> <span m='184230'>the</span> <span
  m='184320'>band</span> <span m='184560'>of</span> <span
  m='184620'>frequencies</span> <span m='185580'>that</span> <span
  m='185700'>we</span> <span m='185850'>want</span> <span m='186060'>to</span>
  <span m='186120'>reject.</span> <span m='187590'>That</span> <span
  m='187770'>of</span> <span m='187860'>course,</span> <span
  m='188800'>is</span> <span m='189150'>exactly</span> <span
  m='189660'>the</span> <span m='189750'>same</span> <span
  m='190020'>notion</span> <span m='190560'>as</span> <span m='190740'>we</span>
  <span m='190890'>have</span> <span m='191280'>in</span> <span
  m='191400'>continuous</span> <span m='192000'>time</span> <span
  m='192450'>or</span> <span m='193110'>analog</span> <span
  m='193620'>systems</span> <span m='194190'>or</span> <span
  m='194340'>filters.</span> </p><p><span m='196000'>So</span> <span
  m='196410'>for</span> <span m='196620'>example,</span> <span
  m='198190'>if</span> <span m='198270'>we</span> <span m='198450'>had</span>
  <span m='198870'>a</span> <span m='198960'>signal,</span> <span
  m='199410'>which</span> <span m='199620'>was</span> <span
  m='199830'>the</span> <span m='199950'>sum</span> <span m='200220'>of</span>
  <span m='200340'>two</span> <span m='200520'>components,</span> <span
  m='201850'>one</span> <span m='201990'>of</span> <span m='202110'>which</span>
  <span m='202620'>was</span> <span m='203010'>low</span> <span
  m='203220'>frequency,</span> <span m='204000'>and</span> <span
  m='204180'>that</span> <span m='204330'>we</span> <span
  m='204480'>wanted</span> <span m='204750'>to</span> <span
  m='204870'>keep,</span> <span m='205680'>and</span> <span
  m='205880'>the</span> <span m='205980'>other</span> <span m='206220'>of</span>
  <span m='206340'>which</span> <span m='206580'>was</span> <span
  m='206730'>high</span> <span m='206970'>frequency</span> <span
  m='207780'>and</span> <span m='207900'>that</span> <span m='208080'>we</span>
  <span m='208230'>wanted</span> <span m='208500'>to</span> <span
  m='208620'>suppress,</span> <span m='209910'>then</span> <span
  m='210420'>we</span> <span m='210600'>can</span> <span
  m='210810'>consider</span> <span m='211980'>extracting</span> <span
  m='212670'>the</span> <span m='212760'>wanted</span> <span
  m='213090'>signal</span> <span m='214800'>with</span> <span
  m='215160'>a</span> <span m='215220'>system</span> <span
  m='216030'>whose</span> <span m='216270'>frequency</span> <span
  m='216870'>response</span> <span m='217770'>ideally</span> <span
  m='219000'>is</span> <span m='219180'>unity</span> <span m='220260'>at</span>
  <span m='220380'>the</span> <span m='220470'>low</span> <span
  m='220680'>frequency</span> <span m='221370'>end</span> <span
  m='222120'>and</span> <span m='222280'>at</span> <span m='222390'>zero</span>
  <span m='223800'>at</span> <span m='224220'>the</span> <span
  m='224340'>high</span> <span m='224550'>frequency</span> <span
  m='225210'>end,</span> <span m='225480'>or</span> <span
  m='225840'>after</span> <span m='226170'>some</span> <span
  m='226380'>cutoff</span> <span m='226800'>frequency,</span> <span
  m='227550'>which</span> <span m='227850'>I've</span> <span
  m='228030'>denoted</span> <span m='228690'>by</span> <span
  m='229080'>omega</span> <span m='229500'>sub</span> <span m='230000'>P.</span>
  </p><p><span m='231270'>So</span> <span m='231750'>this</span> <span
  m='231990'>then</span> <span m='232350'>is</span> <span m='232590'>one</span>
  <span m='232860'>type</span> <span m='233220'>of</span> <span
  m='233280'>filter</span> <span m='233790'>and</span> <span
  m='233910'>one</span> <span m='234090'>class</span> <span m='234480'>of</span>
  <span m='234540'>filtering</span> <span m='235080'>problems,</span> <span
  m='236070'>generally,</span> <span m='236830'>what</span> <span
  m='236940'>we</span> <span m='237090'>would</span> <span
  m='237270'>refer</span> <span m='237660'>to</span> <span m='238050'>as</span>
  <span m='238710'>frequency</span> <span m='239250'>selective</span> <span
  m='239820'>filters.</span> <span m='241050'>We've</span> <span
  m='241440'>illustrated</span> <span m='242070'>that</span> <span
  m='242310'>here</span> <span m='242760'>with</span> <span
  m='243240'>the</span> <span m='243660'>example</span> <span
  m='244380'>of</span> <span m='244530'>a</span> <span
  m='244560'>low-pass</span> <span m='245160'>filter.</span> <span
  m='246090'>But</span> <span m='246300'>of</span> <span
  m='246390'>course</span> <span m='246840'>there</span> <span
  m='247050'>are</span> <span m='247260'>other</span> <span
  m='247500'>kinds</span> <span m='247830'>of</span> <span
  m='247890'>frequency</span> <span m='248400'>selective</span> <span
  m='248850'>filters--</span> <span m='249430'>for</span> <span
  m='249480'>example,</span> <span m='250585'>high-pass,</span> <span
  m='251360'>band-pass,</span> <span m='252140'>band-stop,</span> <span
  m='253980'>multiple</span> <span m='254460'>band</span> <span
  m='254760'>filters,</span> <span m='255210'>et</span> <span
  m='255465'>cetera.</span> <span m='257240'>Furthermore,</span> <span
  m='258870'>the</span> <span m='259500'>filtering</span> <span
  m='260070'>problem,</span> <span m='261329'>both</span> <span
  m='261600'>digital</span> <span m='262050'>and</span> <span
  m='262200'>analog,</span> <span m='263010'>is</span> <span
  m='263280'>of</span> <span m='263370'>course,</span> <span
  m='263790'>not</span> <span m='264090'>restricted</span> <span
  m='265170'>to</span> <span m='265290'>just</span> <span
  m='265560'>simply</span> <span m='266040'>frequency</span> <span
  m='266610'>selective</span> <span m='267090'>filters.</span> <span
  m='268230'>We</span> <span m='268440'>can</span> <span m='269730'>think</span>
  <span m='270060'>of</span> <span m='270180'>problems--</span> <span
  m='271050'>we</span> <span m='271230'>can</span> <span m='271890'>talk</span>
  <span m='272190'>about</span> <span m='272490'>a</span> <span
  m='272550'>wide</span> <span m='272790'>variety</span> <span
  m='273240'>of</span> <span m='273330'>problems,</span> <span
  m='273900'>in</span> <span m='274020'>fact--</span> <span
  m='274920'>where</span> <span m='275520'>the</span> <span
  m='275820'>frequency</span> <span m='276450'>characteristics</span> <span
  m='277950'>that</span> <span m='278130'>are</span> <span
  m='278280'>desired</span> <span m='279870'>are</span> <span
  m='280020'>not</span> <span m='280590'>piecewise</span> <span
  m='281190'>constant</span> <span m='281850'>as</span> <span
  m='282030'>they</span> <span m='282240'>are</span> <span m='282630'>in</span>
  <span m='282870'>the</span> <span m='282990'>frequency</span> <span
  m='283530'>selective</span> <span m='284040'>filter</span> <span
  m='284460'>case,</span> <span m='285420'>but</span> <span
  m='285930'>might</span> <span m='286290'>be</span> <span
  m='288680'>non-piecewise</span> <span m='289550'>constant</span> <span
  m='290030'>such</span> <span m='290330'>as,</span> <span m='290580'>for</span>
  <span m='290660'>example,</span> <span m='291570'>with</span> <span
  m='291680'>the</span> <span m='291800'>case</span> <span m='292310'>of</span>
  <span m='292790'>a</span> <span m='293000'>differentiator,</span> <span
  m='294470'>in</span> <span m='294530'>which</span> <span
  m='294800'>case</span> <span m='295100'>the</span> <span
  m='295220'>desired</span> <span m='295700'>frequency</span> <span
  m='296210'>characteristic</span> <span m='297470'>is</span> <span
  m='297620'>in</span> <span m='297710'>fact,</span> <span
  m='298040'>linear</span> <span m='298460'>with</span> <span
  m='298670'>frequency,</span> <span m='299870'>or</span> <span
  m='300290'>in</span> <span m='300440'>the</span> <span
  m='300560'>inverse</span> <span m='300950'>filtering</span> <span
  m='301460'>problem</span> <span m='302450'>where</span> <span
  m='302840'>the</span> <span m='302960'>desired</span> <span
  m='303440'>frequency</span> <span m='303980'>characteristic</span> <span
  m='305030'>is</span> <span m='306230'>in</span> <span
  m='306350'>general</span> <span m='307160'>of</span> <span m='307430'>a</span>
  <span m='307490'>somewhat</span> <span m='307880'>arbitrary</span> <span
  m='308510'>shape.</span> <span m='309350'>And</span> <span
  m='309560'>so</span> <span m='309830'>in</span> <span m='309950'>this</span>
  <span m='310130'>more</span> <span m='310310'>general</span> <span
  m='310760'>sense,</span> <span m='311360'>the</span> <span
  m='311480'>filtering</span> <span m='312020'>problem</span> <span
  m='313700'>can</span> <span m='313940'>be</span> <span
  m='314090'>thought</span> <span m='314450'>of</span> <span
  m='315170'>in</span> <span m='315320'>terms</span> <span m='315890'>of</span>
  <span m='316730'>the</span> <span m='316880'>implementation</span> <span
  m='318080'>of</span> <span m='318860'>a</span> <span m='318920'>linear</span>
  <span m='319280'>shift</span> <span m='319610'>invariant</span> <span
  m='320150'>system</span> <span m='321200'>with</span> <span
  m='321350'>a</span> <span m='321410'>specified</span> <span
  m='322910'>frequency</span> <span m='323840'>response</span> <span
  m='324470'>characteristic</span> <span m='325520'>that</span> <span
  m='325700'>we</span> <span m='326240'>wish</span> <span m='326480'>to</span>
  <span m='326630'>achieve.</span> </p><p><span m='329370'>To</span> <span
  m='330600'>carry</span> <span m='330960'>out</span> <span
  m='331140'>the</span> <span m='331230'>discussion,</span> <span
  m='332100'>all</span> <span m='332370'>the</span> <span
  m='332490'>discussion</span> <span m='332970'>that</span> <span
  m='333060'>will</span> <span m='333210'>be</span> <span
  m='333330'>carrying</span> <span m='333780'>out</span> <span
  m='334230'>today</span> <span m='334590'>and</span> <span m='334710'>in</span>
  <span m='334830'>fact</span> <span m='335370'>throughout</span> <span
  m='335940'>most</span> <span m='336270'>of</span> <span
  m='336390'>these</span> <span m='336870'>lectures</span> <span
  m='337440'>on</span> <span m='337620'>digital</span> <span
  m='337950'>filter</span> <span m='338340'>design,</span> <span
  m='339420'>I'll</span> <span m='339930'>relate</span> <span
  m='340800'>primarily</span> <span m='341850'>to</span> <span
  m='342870'>frequency</span> <span m='343380'>selective</span> <span
  m='343860'>filters</span> <span m='344265'>and</span> <span
  m='344670'>in</span> <span m='344790'>fact,</span> <span m='345330'>to</span>
  <span m='345450'>low-pass</span> <span m='346050'>filters,</span> <span
  m='346900'>although</span> <span m='347220'>it's</span> <span
  m='347340'>important</span> <span m='347760'>to</span> <span
  m='347880'>keep</span> <span m='348150'>in</span> <span m='348270'>mind</span>
  <span m='348840'>that</span> <span m='349500'>the</span> <span
  m='349710'>digital</span> <span m='350100'>filter</span> <span
  m='351000'>problem,</span> <span m='351780'>the</span> <span
  m='351900'>digital</span> <span m='352230'>filter</span> <span
  m='352560'>design</span> <span m='353010'>problem,</span> <span
  m='353940'>is</span> <span m='354090'>not</span> <span
  m='354330'>restricted</span> <span m='355200'>to</span> <span
  m='355320'>just</span> <span m='355620'>that</span> <span
  m='355800'>class</span> <span m='356190'>of</span> <span
  m='356250'>filters.</span> </p><p><span m='358600'>Well,</span> <span
  m='359470'>for</span> <span m='359890'>the</span> <span m='360010'>case</span>
  <span m='360550'>of</span> <span m='361330'>an</span> <span
  m='361450'>ideal</span> <span m='361770'>low-pass</span> <span
  m='362470'>filter,</span> <span m='362920'>or</span> <span m='363070'>a</span>
  <span m='363100'>low-pass</span> <span m='363670'>filter,</span> <span
  m='364120'>this</span> <span m='364360'>is</span> <span m='364600'>the</span>
  <span m='364870'>desired</span> <span m='365410'>frequency</span> <span
  m='365950'>characteristic.</span> <span m='367360'>And</span> <span
  m='367390'>so</span> <span m='367600'>what's</span> <span
  m='367870'>the</span> <span m='367960'>problem?</span> <span
  m='369400'>Well,</span> <span m='370840'>we</span> <span
  m='371410'>have</span> <span m='371590'>seen</span> <span m='372100'>in</span>
  <span m='372640'>the</span> <span m='372730'>last</span> <span
  m='373030'>several</span> <span m='373420'>lectures</span> <span
  m='374380'>that</span> <span m='375010'>for</span> <span m='375550'>the</span>
  <span m='375730'>implementation</span> <span m='376930'>of</span> <span
  m='377080'>digital</span> <span m='377470'>filters,</span> <span
  m='378520'>it's</span> <span m='378670'>particularly</span> <span
  m='379390'>convenient</span> <span m='381100'>to</span> <span
  m='381430'>have</span> <span m='381700'>a</span> <span
  m='381790'>filter</span> <span m='382990'>or</span> <span m='383095'>a</span>
  <span m='383200'>system</span> <span m='384340'>whose</span> <span
  m='384520'>system</span> <span m='385030'>function</span> <span
  m='385780'>is</span> <span m='385960'>representable</span> <span
  m='387280'>as</span> <span m='387730'>a</span> <span
  m='387820'>rational</span> <span m='388600'>function</span> <span
  m='389080'>of</span> <span m='389170'>z,</span> <span m='390010'>or</span>
  <span m='390130'>equivalently</span> <span m='390970'>whose</span> <span
  m='391780'>input-output</span> <span m='392470'>characteristic</span> <span
  m='393520'>can</span> <span m='393730'>be</span> <span
  m='394540'>related</span> <span m='395500'>by</span> <span
  m='395740'>means</span> <span m='396280'>of</span> <span m='396910'>a</span>
  <span m='397840'>linear</span> <span m='398170'>constant</span> <span
  m='398590'>coefficient</span> <span m='399190'>difference</span> <span
  m='399550'>equation.</span> </p><p><span m='401430'>A</span> <span
  m='401500'>linear</span> <span m='402070'>constant</span> <span
  m='402550'>coefficient</span> <span m='403150'>difference</span> <span
  m='403540'>equation,</span> <span m='404800'>or</span> <span
  m='405160'>a</span> <span m='405250'>rational</span> <span
  m='406120'>system</span> <span m='406570'>function,</span> <span
  m='407680'>can't</span> <span m='408310'>achieve</span> <span
  m='409000'>exactly</span> <span m='409930'>an</span> <span
  m='410110'>ideal</span> <span m='410560'>low-pass</span> <span
  m='411130'>filter</span> <span m='411490'>characteristic</span> <span
  m='412420'>as</span> <span m='412570'>we</span> <span m='412720'>have</span>
  <span m='412990'>here,</span> <span m='413710'>and</span> <span
  m='413830'>in</span> <span m='413920'>general</span> <span
  m='414340'>can't</span> <span m='414700'>achieve</span> <span
  m='415870'>any</span> <span m='416410'>ideal</span> <span
  m='417010'>frequency</span> <span m='417610'>selective</span> <span
  m='418150'>characteristic</span> <span m='419410'>where</span> <span
  m='419950'>the</span> <span m='420160'>transition</span> <span
  m='420790'>from</span> <span m='421000'>one</span> <span
  m='421210'>band</span> <span m='421870'>to</span> <span
  m='422050'>another</span> <span m='422530'>is</span> <span
  m='423040'>as</span> <span m='423250'>abrupt</span> <span m='423730'>as</span>
  <span m='423910'>we</span> <span m='424060'>would</span> <span
  m='424210'>like</span> <span m='424420'>it</span> <span m='424510'>to</span>
  <span m='424630'>be</span> <span m='424810'>ideally.</span> <span
  m='426640'>So</span> <span m='427090'>in</span> <span m='427240'>fact,</span>
  <span m='429100'>what's</span> <span m='429580'>required</span> <span
  m='430330'>is</span> <span m='430600'>to</span> <span
  m='430780'>approximate</span> <span m='432190'>this</span> <span
  m='432400'>ideal</span> <span m='432850'>frequency</span> <span
  m='433420'>characteristic,</span> <span m='434960'>and</span> <span
  m='435490'>the</span> <span m='435610'>approximation</span> <span
  m='436720'>of</span> <span m='436960'>the</span> <span m='437530'>ideal</span>
  <span m='437920'>frequency</span> <span m='438460'>characteristic,</span>
  <span m='439430'>and</span> <span m='440140'>the</span> <span
  m='440410'>design</span> <span m='441430'>of</span> <span m='442120'>a</span>
  <span m='442240'>rational</span> <span m='442810'>transfer</span> <span
  m='443320'>function</span> <span m='443890'>to</span> <span
  m='444040'>implement</span> <span m='444820'>that</span> <span
  m='444970'>approximation</span> <span m='446350'>is</span> <span
  m='446560'>what</span> <span m='447340'>the</span> <span
  m='447580'>digital</span> <span m='448090'>filter</span> <span
  m='448540'>design</span> <span m='449110'>problem</span> <span
  m='449650'>is</span> <span m='449770'>about.</span> </p><p><span
  m='451700'>So</span> <span m='452350'>whereas</span> <span
  m='452980'>we</span> <span m='453160'>talk</span> <span
  m='453520'>ideally</span> <span m='454180'>about</span> <span
  m='454450'>a</span> <span m='454510'>filter</span> <span
  m='454840'>characteristic,</span> <span m='455800'>as</span> <span
  m='455980'>I've</span> <span m='456130'>indicated</span> <span
  m='456730'>here,</span> <span m='457730'>in</span> <span
  m='457750'>fact,</span> <span m='458600'>we</span> <span
  m='459250'>have</span> <span m='459520'>to</span> <span
  m='459730'>allow</span> <span m='460060'>some</span> <span
  m='460270'>deviation</span> <span m='461230'>from</span> <span
  m='461470'>this</span> <span m='461680'>ideal</span> <span
  m='462100'>characteristic</span> <span m='463480'>so</span> <span
  m='463720'>that</span> <span m='464770'>we</span> <span
  m='465190'>would</span> <span m='465340'>permit</span> <span
  m='466390'>as</span> <span m='466630'>an</span> <span
  m='466720'>example</span> <span m='468400'>a</span> <span
  m='469930'>frequency</span> <span m='470530'>response,</span> <span
  m='471760'>rather</span> <span m='472120'>than</span> <span
  m='472300'>being</span> <span m='472570'>unity</span> <span
  m='473350'>in</span> <span m='474010'>the</span> <span
  m='474130'>passband,</span> <span m='475410'>to</span> <span
  m='475540'>deviate</span> <span m='476410'>from</span> <span
  m='476590'>unity</span> <span m='477130'>by</span> <span
  m='477370'>some</span> <span m='477640'>amount.</span> <span
  m='478180'>And</span> <span m='478360'>let's</span> <span
  m='479260'>designate</span> <span m='479890'>that</span> <span
  m='480220'>by</span> <span m='480790'>say,</span> <span
  m='481090'>delta</span> <span m='481510'>sub</span> <span m='481720'>P,</span>
  <span m='482690'>denoting</span> <span m='483310'>a</span> <span
  m='483580'>passband</span> <span m='484240'>deviation.</span> <span
  m='485680'>So</span> <span m='485890'>that</span> <span m='486160'>in</span>
  <span m='486310'>fact</span> <span m='486700'>where</span> <span
  m='486820'>we</span> <span m='486970'>might</span> <span
  m='487210'>specify</span> <span m='488320'>is</span> <span m='488560'>a</span>
  <span m='488650'>filter</span> <span m='490090'>which</span> <span
  m='491140'>in</span> <span m='491680'>the</span> <span
  m='491770'>passband,</span> <span m='492770'>in</span> <span
  m='492880'>the</span> <span m='492970'>band</span> <span m='493240'>of</span>
  <span m='493300'>frequencies</span> <span m='493930'>that</span> <span
  m='494020'>we</span> <span m='494200'>wish</span> <span m='494440'>to</span>
  <span m='494530'>pass,</span> <span m='495520'>rather</span> <span
  m='495880'>than</span> <span m='496060'>being</span> <span
  m='496300'>exactly</span> <span m='496870'>unity,</span> <span
  m='497890'>is</span> <span m='498010'>constrained</span> <span
  m='498850'>in</span> <span m='499000'>the</span> <span
  m='499540'>interval</span> <span m='500770'>between</span> <span
  m='501550'>unity</span> <span m='502390'>and</span> <span m='502600'>1</span>
  <span m='502840'>minus</span> <span m='503260'>delta</span> <span
  m='503660'>sub</span> <span m='503905'>P.</span> </p><p><span
  m='505940'>Similarly,</span> <span m='507330'>we</span> <span
  m='508400'>might</span> <span m='508730'>permit</span> <span
  m='509480'>the</span> <span m='509690'>frequency</span> <span
  m='510230'>characteristics,</span> <span m='511190'>rather</span> <span
  m='511580'>than</span> <span m='512240'>requiring</span> <span
  m='512870'>them</span> <span m='513049'>to</span> <span m='513169'>be</span>
  <span m='513320'>exactly</span> <span m='513860'>0</span> <span
  m='514580'>in</span> <span m='515299'>a</span> <span
  m='515360'>stopband</span> <span m='516070'>region.</span> <span
  m='517309'>We</span> <span m='517760'>might</span> <span
  m='518059'>permit</span> <span m='518690'>the</span> <span
  m='518780'>frequency</span> <span m='519470'>characteristic</span> <span
  m='520370'>to</span> <span m='520490'>deviate</span> <span
  m='521240'>from</span> <span m='521480'>0</span> <span m='522440'>by</span>
  <span m='522620'>some</span> <span m='522890'>amount</span> <span
  m='523429'>which</span> <span m='523909'>we</span> <span m='524120'>can</span>
  <span m='524330'>denote</span> <span m='524690'>as</span> <span
  m='524810'>delta</span> <span m='525170'>sub</span> <span m='525575'>S,</span>
  <span m='526670'>which</span> <span m='526940'>is</span> <span
  m='527270'>the</span> <span m='527570'>stopband</span> <span
  m='528260'>deviation,</span> <span m='529640'>in</span> <span
  m='529730'>which</span> <span m='530000'>case</span> <span
  m='531560'>we</span> <span m='531740'>would</span> <span m='531890'>ask</span>
  <span m='532700'>that</span> <span m='532850'>the</span> <span
  m='532970'>filter</span> <span m='533450'>fall</span> <span
  m='533840'>between</span> <span m='534350'>0</span> <span
  m='535490'>and</span> <span m='535970'>delta</span> <span
  m='536330'>sub</span> <span m='536735'>S,</span> <span m='537470'>that</span>
  <span m='537710'>is</span> <span m='538280'>that</span> <span
  m='538880'>the</span> <span m='539000'>filter</span> <span
  m='539480'>that</span> <span m='539660'>we</span> <span
  m='539810'>actually</span> <span m='540230'>design</span> <span
  m='541400'>be</span> <span m='541880'>restricted</span> <span
  m='542810'>to</span> <span m='542930'>this</span> <span
  m='543440'>frequency</span> <span m='544400'>range.</span> <span
  m='546150'>And</span> <span m='546170'>finally</span> <span
  m='546770'>recognizing</span> <span m='547730'>that</span> <span
  m='548300'>in</span> <span m='548450'>reality</span> <span
  m='549290'>we</span> <span m='549410'>can't</span> <span
  m='549710'>achieve</span> <span m='550130'>a</span> <span
  m='550190'>discontinuity</span> <span m='551120'>in</span> <span
  m='551180'>the</span> <span m='551270'>frequency</span> <span
  m='551810'>response</span> <span m='552500'>as</span> <span
  m='552620'>sharp</span> <span m='553070'>as</span> <span
  m='553220'>I've</span> <span m='553400'>indicated</span> <span
  m='553970'>here,</span> <span m='554900'>we</span> <span
  m='555020'>would</span> <span m='555200'>permit</span> <span
  m='555680'>also</span> <span m='556940'>a</span> <span
  m='558590'>transition</span> <span m='559280'>region.</span> <span
  m='560900'>That</span> <span m='561110'>is,</span> <span m='561920'>we</span>
  <span m='562130'>would</span> <span m='563270'>permit</span> <span
  m='563690'>a</span> <span m='563780'>region,</span> <span
  m='566500'>after</span> <span m='566950'>which</span> <span
  m='567760'>the</span> <span m='567850'>frequency</span> <span
  m='568450'>characteristic</span> <span m='569440'>must</span> <span
  m='569710'>be</span> <span m='569890'>below</span> <span
  m='570220'>delta</span> <span m='570610'>sub</span> <span m='570955'>S,</span>
  <span m='571660'>and</span> <span m='571810'>before</span> <span
  m='572260'>which</span> <span m='572770'>the</span> <span
  m='572890'>frequency</span> <span m='573370'>characteristic</span> <span
  m='574180'>must</span> <span m='574420'>be</span> <span
  m='574690'>between</span> <span m='575110'>1</span> <span
  m='575380'>and</span> <span m='575470'>1</span> <span m='575680'>minus</span>
  <span m='576010'>delta</span> <span m='576275'>sub</span> <span
  m='576540'>P,</span> <span m='577420'>but</span> <span
  m='577960'>allowing</span> <span m='578410'>a</span> <span
  m='578470'>region</span> <span m='579100'>for</span> <span
  m='579550'>it</span> <span m='579760'>to</span> <span m='580060'>make</span>
  <span m='580330'>the</span> <span m='580420'>transition</span> <span
  m='581140'>from</span> <span m='581350'>the</span> <span
  m='581470'>passband</span> <span m='582040'>to</span> <span
  m='582200'>the</span> <span m='582490'>stopband.</span> </p><p><span
  m='584130'>So</span> <span m='584850'>these</span> <span m='585330'>are</span>
  <span m='585420'>the</span> <span m='585600'>kinds</span> <span
  m='585990'>of</span> <span m='586050'>specifications</span> <span
  m='587310'>on</span> <span m='587820'>a</span> <span m='587880'>filter.</span>
  <span m='588990'>And</span> <span m='590160'>a</span> <span
  m='590460'>typical</span> <span m='590940'>kind</span> <span
  m='591210'>of</span> <span m='591330'>characteristic</span> <span
  m='592200'>then</span> <span m='592620'>that</span> <span
  m='592800'>might</span> <span m='593070'>result</span> <span
  m='593610'>is</span> <span m='593760'>a</span> <span m='593820'>filter</span>
  <span m='594270'>perhaps</span> <span m='594780'>that</span> <span
  m='594900'>ripples</span> <span m='597150'>between</span> <span
  m='597630'>these</span> <span m='597840'>limits</span> <span
  m='598290'>1</span> <span m='598620'>and</span> <span m='598710'>1</span>
  <span m='598920'>minus</span> <span m='599250'>delta</span> <span
  m='599650'>sub</span> <span m='599805'>P</span> <span m='599960'>in</span>
  <span m='600060'>the</span> <span m='600150'>passband,</span> <span
  m='601620'>and</span> <span m='601770'>then</span> <span
  m='603150'>makes</span> <span m='603450'>the</span> <span
  m='603570'>transition</span> <span m='604440'>into</span> <span
  m='605040'>a</span> <span m='605100'>stopband</span> <span
  m='605790'>region</span> <span m='606840'>and</span> <span
  m='607020'>perhaps</span> <span m='607800'>wiggles</span> <span
  m='608250'>around</span> <span m='609720'>in</span> <span
  m='609990'>the</span> <span m='610080'>stopband</span> <span
  m='610680'>region,</span> <span m='611160'>sometimes</span> <span
  m='611820'>perhaps</span> <span m='612690'>touching</span> <span
  m='613050'>the</span> <span m='613110'>limits</span> <span
  m='613500'>and</span> <span m='613590'>sometimes</span> <span
  m='614190'>not.</span> </p><p><span m='615720'>So</span> <span
  m='616410'>what</span> <span m='616740'>the</span> <span
  m='616950'>digital</span> <span m='617340'>filter</span> <span
  m='617700'>design</span> <span m='618150'>problem</span> <span
  m='618870'>is</span> <span m='619380'>then,</span> <span m='620950'>is</span>
  <span m='621180'>given</span> <span m='621480'>a</span> <span
  m='621540'>set</span> <span m='621780'>of</span> <span
  m='621840'>specifications</span> <span m='623340'>on</span> <span
  m='623520'>the</span> <span m='623610'>filter,</span> <span
  m='624390'>recognizing</span> <span m='625170'>that</span> <span
  m='625290'>we</span> <span m='625440'>can</span> <span
  m='625710'>implement</span> <span m='626130'>an</span> <span
  m='626220'>ideal</span> <span m='626700'>filter,</span> <span
  m='627570'>but</span> <span m='627810'>in</span> <span m='627930'>fact</span>
  <span m='628260'>allowing</span> <span m='628650'>some</span> <span
  m='628830'>deviation</span> <span m='629490'>from</span> <span
  m='629670'>the</span> <span m='629790'>ideal</span> <span
  m='630210'>filter.</span> <span m='631180'>The</span> <span
  m='631290'>digital</span> <span m='631680'>filter</span> <span
  m='632040'>design</span> <span m='632490'>problem</span> <span
  m='633600'>is</span> <span m='633780'>then</span> <span m='634590'>to</span>
  <span m='634860'>design</span> <span m='636390'>a</span> <span
  m='636460'>rational</span> <span m='637020'>transfer</span> <span
  m='637560'>function,</span> <span m='639220'>which</span> <span
  m='639900'>approximates</span> <span m='641190'>in</span> <span
  m='641340'>some</span> <span m='641580'>sense,</span> <span
  m='642490'>this</span> <span m='642600'>ideal</span> <span
  m='643050'>filter</span> <span m='644250'>maintaining</span> <span
  m='645180'>the</span> <span m='645300'>specifications</span> <span
  m='646530'>of</span> <span m='647460'>passband</span> <span
  m='648180'>and</span> <span m='648330'>stopband</span> <span
  m='648900'>deviation</span> <span m='650100'>that</span> <span
  m='650550'>we've</span> <span m='651180'>imposed</span> <span
  m='651690'>on</span> <span m='651810'>the</span> <span
  m='651870'>problem.</span> </p><p><span m='654900'>Now,</span> <span
  m='655410'>there</span> <span m='655890'>are</span> <span
  m='656760'>several</span> <span m='657570'>classes</span> <span
  m='658350'>of</span> <span m='658890'>design</span> <span
  m='659340'>techniques</span> <span m='660300'>that</span> <span
  m='660810'>we</span> <span m='660960'>can</span> <span
  m='661140'>consider.</span> <span m='662950'>The</span> <span
  m='663080'>first</span> <span m='663350'>class</span> <span
  m='663740'>of</span> <span m='663860'>design</span> <span
  m='664220'>techniques,</span> <span m='665360'>which</span> <span
  m='665870'>in</span> <span m='666020'>fact,</span> <span m='666590'>we</span>
  <span m='666830'>won't</span> <span m='667070'>be</span> <span
  m='667190'>talking</span> <span m='667850'>much</span> <span
  m='668120'>about,</span> <span m='668660'>is</span> <span
  m='669470'>the</span> <span m='669560'>class</span> <span
  m='670160'>that</span> <span m='670530'>I've</span> <span
  m='670620'>referred</span> <span m='671060'>to</span> <span
  m='671420'>as</span> <span m='671720'>analytical</span> <span
  m='672410'>design</span> <span m='672860'>techniques.</span> <span
  m='673950'>Basically</span> <span m='675020'>what</span> <span
  m='675200'>I</span> <span m='675290'>mean</span> <span m='675530'>by</span>
  <span m='675740'>that</span> <span m='676100'>are</span> <span
  m='676250'>design</span> <span m='676670'>techniques</span> <span
  m='677540'>that</span> <span m='678740'>permit</span> <span
  m='679550'>the</span> <span m='679670'>approximation</span> <span
  m='680810'>of</span> <span m='680960'>the</span> <span m='681110'>ideal</span>
  <span m='681440'>frequency</span> <span m='681950'>characteristic.</span>
  </p><p><span m='683720'>The</span> <span m='683840'>approximation</span> <span
  m='684590'>is</span> <span m='684710'>carried</span> <span
  m='685130'>out</span> <span m='686510'>through</span> <span
  m='686720'>an</span> <span m='686840'>analytical</span> <span
  m='687410'>procedure</span> <span m='688550'>and</span> <span
  m='688970'>results</span> <span m='689570'>in</span> <span m='689870'>a</span>
  <span m='689960'>closed</span> <span m='690350'>form</span> <span
  m='690680'>transfer</span> <span m='691160'>function.</span> <span
  m='693410'>That</span> <span m='693680'>in</span> <span m='693830'>fact</span>
  <span m='694400'>is</span> <span m='695090'>a</span> <span
  m='695240'>very</span> <span m='695510'>common</span> <span
  m='695930'>class</span> <span m='696290'>of</span> <span
  m='696410'>techniques</span> <span m='697190'>for</span> <span
  m='698880'>continuous</span> <span m='699510'>time</span> <span
  m='700020'>or</span> <span m='700350'>analog</span> <span
  m='701520'>filter</span> <span m='701910'>design.</span> <span
  m='703170'>And</span> <span m='704040'>that</span> <span
  m='704340'>leads</span> <span m='704670'>us</span> <span m='705150'>to</span>
  <span m='705450'>the</span> <span m='705570'>second</span> <span
  m='705930'>class</span> <span m='706290'>of</span> <span
  m='706380'>design</span> <span m='706800'>techniques,</span> <span
  m='707880'>namely</span> <span m='708450'>the</span> <span
  m='708570'>class</span> <span m='708920'>of</span> <span
  m='709020'>design</span> <span m='709410'>techniques</span> <span
  m='710070'>that</span> <span m='710370'>I</span> <span m='710490'>refer</span>
  <span m='710880'>to</span> <span m='711300'>as</span> <span
  m='712140'>mapping</span> <span m='713070'>continuous</span> <span
  m='713730'>time</span> <span m='714500'>to</span> <span
  m='714630'>discrete</span> <span m='715080'>time.</span> </p><p><span
  m='716910'>Well,</span> <span m='717180'>why</span> <span m='717450'>in</span>
  <span m='717540'>the</span> <span m='717630'>world</span> <span
  m='717930'>would</span> <span m='718080'>we</span> <span
  m='718260'>ever</span> <span m='718440'>want</span> <span m='718640'>a</span>
  <span m='718710'>map</span> <span m='719280'>from</span> <span
  m='719520'>continuous</span> <span m='720150'>time</span> <span
  m='720420'>to</span> <span m='720540'>discrete</span> <span
  m='720960'>time?</span> <span m='722960'>Well,</span> <span
  m='723310'>the</span> <span m='723460'>reason,</span> <span
  m='724060'>very</span> <span m='724330'>simply,</span> <span
  m='725410'>is</span> <span m='725710'>that</span> <span m='726670'>a</span>
  <span m='726730'>lot</span> <span m='727030'>of</span> <span
  m='727210'>work.</span> <span m='728440'>And</span> <span m='728560'>a</span>
  <span m='728620'>lot</span> <span m='728860'>of</span> <span
  m='728950'>results</span> <span m='729640'>have</span> <span
  m='729880'>developed</span> <span m='731020'>for</span> <span
  m='731650'>the</span> <span m='732760'>design</span> <span
  m='733720'>of</span> <span m='734350'>continuous</span> <span
  m='735070'>time</span> <span m='735820'>filters.</span> <span
  m='736915'>And</span> <span m='737320'>in</span> <span m='737440'>fact,</span>
  <span m='738200'>a</span> <span m='738300'>lot</span> <span
  m='738400'>of</span> <span m='738520'>these</span> <span
  m='738700'>procedures</span> <span m='739510'>are</span> <span
  m='739840'>analytical</span> <span m='740470'>procedures.</span> <span
  m='741070'>They</span> <span m='741190'>lead</span> <span m='741820'>to</span>
  <span m='742240'>analytical,</span> <span m='743020'>or</span> <span
  m='743230'>they</span> <span m='743410'>lead</span> <span m='743590'>to</span>
  <span m='743740'>closed</span> <span m='744130'>form</span> <span
  m='744550'>designs</span> <span m='745180'>and</span> <span
  m='745330'>their</span> <span m='745480'>analytical</span> <span
  m='746050'>procedures</span> <span m='747160'>that</span> <span
  m='747310'>can</span> <span m='747460'>be</span> <span m='747610'>used.</span>
  <span m='748930'>Now,</span> <span m='749320'>if</span> <span
  m='749560'>it's</span> <span m='749680'>possible</span> <span
  m='751360'>to</span> <span m='751510'>map</span> <span m='752500'>those</span>
  <span m='752830'>designs</span> <span m='754270'>to</span> <span
  m='754870'>digital</span> <span m='755800'>designs,</span> <span
  m='757000'>then</span> <span m='757150'>in</span> <span
  m='757270'>fact,</span> <span m='757750'>that's</span> <span
  m='757930'>something</span> <span m='758350'>we</span> <span
  m='758470'>should</span> <span m='758680'>do</span> <span
  m='759280'>simply</span> <span m='759850'>to</span> <span
  m='760000'>take</span> <span m='760300'>advantage</span> <span
  m='761290'>of</span> <span m='761470'>the</span> <span m='761590'>kinds</span>
  <span m='761950'>of</span> <span m='762040'>results</span> <span
  m='762670'>that</span> <span m='762820'>have</span> <span
  m='762910'>been</span> <span m='763030'>worked</span> <span
  m='763330'>out</span> <span m='763510'>previously</span> <span
  m='764290'>in</span> <span m='764380'>the</span> <span
  m='764470'>design</span> <span m='765130'>of</span> <span
  m='765550'>analog</span> <span m='766090'>filters.</span> </p><p><span
  m='768290'>An</span> <span m='768390'>important</span> <span
  m='769110'>point</span> <span m='769380'>to</span> <span
  m='769530'>keep</span> <span m='769800'>in</span> <span
  m='769890'>mind,</span> <span m='770220'>however,</span> <span
  m='771340'>is</span> <span m='771420'>that</span> <span m='771660'>we</span>
  <span m='771810'>don't</span> <span m='772140'>mean</span> <span
  m='772470'>by</span> <span m='772710'>this</span> <span
  m='773640'>approximating</span> <span m='776556'>an</span> <span
  m='776940'>analog</span> <span m='777480'>filter</span> <span
  m='778380'>with</span> <span m='778530'>a</span> <span
  m='778590'>digital</span> <span m='779010'>filter.</span> <span
  m='780030'>That's</span> <span m='780270'>not</span> <span
  m='780510'>the</span> <span m='780630'>objective,</span> <span
  m='781110'>that's</span> <span m='781320'>a</span> <span
  m='781380'>point</span> <span m='781890'>that</span> <span
  m='782010'>we've</span> <span m='782190'>stressed</span> <span
  m='782640'>throughout</span> <span m='783060'>these</span> <span
  m='783270'>lectures.</span> <span m='783870'>Our</span> <span
  m='784020'>objective</span> <span m='784500'>is</span> <span
  m='784650'>not</span> <span m='785280'>to</span> <span
  m='785430'>approximate</span> <span m='786660'>an</span> <span
  m='786810'>analog</span> <span m='787320'>filter</span> <span
  m='787710'>with</span> <span m='787860'>a</span> <span
  m='787890'>digital</span> <span m='788310'>filter.</span> <span
  m='789240'>But</span> <span m='789600'>if</span> <span m='789870'>in</span>
  <span m='789990'>fact,</span> <span m='790690'>we</span> <span
  m='790770'>can</span> <span m='790950'>utilize</span> <span
  m='792030'>analog</span> <span m='792540'>designs</span> <span
  m='794100'>in</span> <span m='794610'>designing</span> <span
  m='795150'>digital</span> <span m='795540'>filters,</span> <span
  m='796330'>then</span> <span m='796380'>that's</span> <span
  m='796560'>something</span> <span m='796950'>we</span> <span
  m='797070'>should</span> <span m='797280'>do.</span> <span
  m='797640'>And</span> <span m='797790'>in</span> <span m='797880'>fact,</span>
  <span m='798640'>there</span> <span m='798690'>are</span> <span
  m='798810'>some</span> <span m='799020'>procedures</span> <span
  m='799710'>that</span> <span m='799860'>allow</span> <span
  m='800190'>us</span> <span m='800310'>to</span> <span m='800430'>do</span>
  <span m='800640'>this</span> <span m='801060'>that</span> <span
  m='801210'>are</span> <span m='801270'>very</span> <span
  m='801510'>successful.</span> </p><p><span m='804470'>The</span> <span
  m='805310'>third</span> <span m='805940'>class</span> <span
  m='806330'>of</span> <span m='806450'>design</span> <span
  m='806840'>techniques</span> <span m='807590'>are</span> <span
  m='808160'>what</span> <span m='808490'>are</span> <span
  m='808610'>referred</span> <span m='809000'>to</span> <span
  m='809450'>as</span> <span m='809900'>algorithmic</span> <span
  m='810860'>or</span> <span m='811190'>computer-aided</span> <span
  m='812330'>design</span> <span m='812720'>techniques.</span> <span
  m='814010'>And</span> <span m='814610'>the</span> <span
  m='814730'>basic</span> <span m='815390'>idea</span> <span
  m='815840'>here</span> <span m='817190'>is</span> <span m='818060'>that</span>
  <span m='818870'>there</span> <span m='819230'>are</span> <span
  m='819680'>a</span> <span m='819770'>variety</span> <span m='820400'>of</span>
  <span m='820520'>algorithmic</span> <span m='821180'>procedures,</span> <span
  m='822230'>iterative</span> <span m='822680'>procedures</span> <span
  m='823880'>that</span> <span m='824000'>we</span> <span m='824180'>can</span>
  <span m='824360'>go</span> <span m='824570'>through</span> <span
  m='825560'>to</span> <span m='827230'>carry</span> <span m='827650'>out</span>
  <span m='828070'>the</span> <span m='828160'>digital</span> <span
  m='828520'>filter</span> <span m='828910'>design.</span> <span
  m='830110'>And</span> <span m='830740'>we'll</span> <span
  m='831010'>see</span> <span m='831850'>a</span> <span m='832360'>brief</span>
  <span m='832840'>discussion</span> <span m='833620'>of</span> <span
  m='834460'>a</span> <span m='834520'>number</span> <span m='834880'>of</span>
  <span m='835000'>these</span> <span m='835780'>in</span> <span
  m='836260'>the</span> <span m='836350'>next</span> <span
  m='836560'>several</span> <span m='836950'>lectures,</span> <span
  m='837910'>both</span> <span m='838240'>for</span> <span
  m='838540'>infinite</span> <span m='838930'>impulse</span> <span
  m='839350'>response</span> <span m='839890'>filters</span> <span
  m='840520'>and</span> <span m='840640'>for</span> <span
  m='840790'>finite</span> <span m='841210'>impulse</span> <span
  m='841600'>response</span> <span m='842110'>filters.</span> </p><p><span
  m='844030'>Now,</span> <span m='844480'>in</span> <span m='844630'>fact</span>
  <span m='844990'>on</span> <span m='845110'>the</span> <span
  m='845230'>issue</span> <span m='845650'>of</span> <span
  m='845950'>infinite</span> <span m='846370'>impulse</span> <span
  m='846790'>response</span> <span m='847270'>and</span> <span
  m='847360'>finite</span> <span m='847810'>impulse</span> <span
  m='848230'>response,</span> <span m='849400'>it</span> <span
  m='849490'>turns</span> <span m='849910'>out</span> <span
  m='850420'>that</span> <span m='851710'>it's</span> <span
  m='852100'>convenient</span> <span m='853090'>to</span> <span
  m='853210'>separate</span> <span m='854740'>the</span> <span
  m='854920'>design</span> <span m='855430'>issues</span> <span
  m='856870'>for</span> <span m='857290'>infinite</span> <span
  m='857710'>impulse</span> <span m='858160'>response</span> <span
  m='858880'>and</span> <span m='859060'>for</span> <span
  m='859600'>finite</span> <span m='860050'>impulse</span> <span
  m='860440'>response</span> <span m='861010'>filters.</span> <span
  m='862210'>There</span> <span m='862510'>are</span> <span
  m='862660'>techniques</span> <span m='863290'>for</span> <span
  m='863410'>the</span> <span m='863500'>finite</span> <span
  m='863920'>impulse</span> <span m='864310'>response</span> <span
  m='864820'>case</span> <span m='865540'>that</span> <span
  m='865930'>are</span> <span m='866050'>not</span> <span
  m='866260'>applicable</span> <span m='867190'>to</span> <span
  m='867310'>the</span> <span m='867460'>infinite</span> <span
  m='867820'>impulse</span> <span m='868240'>response</span> <span
  m='868780'>case,</span> <span m='869560'>and</span> <span
  m='869710'>vice</span> <span m='870040'>versa.</span> <span
  m='870970'>And</span> <span m='871090'>consequently,</span> <span
  m='872080'>as</span> <span m='872260'>we</span> <span m='872380'>talk</span>
  <span m='872740'>about</span> <span m='873160'>digital</span> <span
  m='873490'>filter</span> <span m='873880'>design</span> <span
  m='874540'>techniques,</span> <span m='875650'>we'll</span> <span
  m='875800'>be</span> <span m='875920'>talking</span> <span
  m='876610'>first</span> <span m='877060'>about</span> <span
  m='877900'>the</span> <span m='878020'>design</span> <span
  m='878740'>of</span> <span m='879100'>infinite</span> <span
  m='879550'>impulse</span> <span m='879970'>response,</span> <span
  m='880690'>or</span> <span m='881350'>what</span> <span m='881650'>we</span>
  <span m='881890'>alternatively</span> <span m='882610'>refer</span> <span
  m='882970'>to</span> <span m='883270'>as</span> <span
  m='883420'>recursive</span> <span m='884440'>digital</span> <span
  m='884800'>filters,</span> <span m='885820'>and</span> <span
  m='885970'>then</span> <span m='886480'>we'll</span> <span
  m='886780'>talk</span> <span m='887110'>separately</span> <span
  m='887950'>about</span> <span m='888700'>some</span> <span
  m='888940'>design</span> <span m='889540'>procedures</span> <span
  m='890320'>for</span> <span m='890640'>finite</span> <span
  m='891040'>impulse</span> <span m='891400'>response</span> <span
  m='892000'>or</span> <span m='892540'>non-recursive</span> <span
  m='893260'>digital</span> <span m='893620'>filters.</span> </p><p><span
  m='895430'>So</span> <span m='895900'>for</span> <span m='896050'>this</span>
  <span m='896290'>lecture,</span> <span m='897820'>and</span> <span
  m='898660'>in</span> <span m='898780'>fact</span> <span m='899410'>for</span>
  <span m='902770'>this</span> <span m='903010'>lecture</span> <span
  m='903580'>and</span> <span m='903730'>the</span> <span m='903850'>next</span>
  <span m='904120'>lecture,</span> <span m='905160'>and</span> <span
  m='905400'>in</span> <span m='905500'>fact</span> <span m='905770'>for</span>
  <span m='906610'>this</span> <span m='906820'>and</span> <span
  m='906970'>the</span> <span m='907030'>next</span> <span m='907240'>two</span>
  <span m='907450'>lectures,</span> <span m='908540'>we'll</span> <span
  m='908650'>be</span> <span m='908800'>focusing</span> <span
  m='909400'>entirely</span> <span m='910300'>on</span> <span
  m='910930'>the</span> <span m='911020'>design</span> <span
  m='911620'>of</span> <span m='911950'>infinite</span> <span
  m='912370'>impulse</span> <span m='912790'>response</span> <span
  m='914020'>digital</span> <span m='914380'>filters.</span> <span
  m='915340'>And</span> <span m='915430'>in</span> <span m='915520'>the</span>
  <span m='915610'>lecture</span> <span m='915970'>following</span> <span
  m='916450'>that,</span> <span m='916750'>we'll</span> <span
  m='916900'>consider</span> <span m='917320'>some</span> <span
  m='917530'>design</span> <span m='917920'>procedures</span> <span
  m='918700'>for</span> <span m='919270'>finite</span> <span
  m='919660'>impulse</span> <span m='920050'>response</span> <span
  m='920530'>filters.</span> </p><p><span m='922660'>All</span> <span
  m='922750'>right,</span> <span m='922990'>well,</span> <span
  m='924490'>the</span> <span m='924820'>first</span> <span
  m='925390'>class</span> <span m='925840'>of</span> <span
  m='925960'>procedures,</span> <span m='926980'>design</span> <span
  m='927400'>techniques</span> <span m='928210'>that</span> <span
  m='928570'>I'd</span> <span m='928720'>like</span> <span m='928930'>to</span>
  <span m='929050'>discuss,</span> <span m='930190'>are</span> <span
  m='930340'>ones</span> <span m='930940'>related</span> <span
  m='931870'>to</span> <span m='932260'>mapping</span> <span
  m='932800'>from</span> <span m='932980'>continuous</span> <span
  m='933640'>time</span> <span m='934480'>to</span> <span
  m='934570'>discrete</span> <span m='934990'>time--</span> <span
  m='935860'>that</span> <span m='936040'>is,</span> <span
  m='936760'>taking</span> <span m='937810'>analog</span> <span
  m='938650'>filter</span> <span m='939100'>design</span> <span
  m='941110'>techniques</span> <span m='942220'>and</span> <span
  m='942340'>utilizing</span> <span m='943090'>them</span> <span
  m='943480'>for</span> <span m='943630'>the</span> <span
  m='943750'>design</span> <span m='944380'>of</span> <span
  m='944530'>digital</span> <span m='944860'>filters.</span> <span
  m='947180'>So</span> <span m='947950'>the</span> <span
  m='948040'>procedure</span> <span m='948580'>basically</span> <span
  m='950050'>is</span> <span m='950290'>that</span> <span
  m='951100'>we're</span> <span m='951220'>mapping</span> <span
  m='951670'>from</span> <span m='951850'>continuous</span> <span
  m='952660'>time</span> <span m='952990'>to</span> <span
  m='953110'>discrete</span> <span m='953560'>time.</span> <span
  m='955040'>We</span> <span m='955090'>have</span> <span m='956230'>a</span>
  <span m='956440'>continuous</span> <span m='957160'>time</span> <span
  m='957610'>system</span> <span m='958060'>function,</span> <span
  m='958830'>H</span> <span m='959021'>sub</span> <span m='959213'>a</span>
  <span m='959596'>of</span> <span m='959980'>S,</span> <span
  m='961310'>which</span> <span m='961520'>is</span> <span m='961700'>the</span>
  <span m='961790'>Laplace</span> <span m='962240'>transform</span> <span
  m='962900'>of</span> <span m='962990'>the</span> <span
  m='963110'>impulse</span> <span m='963560'>response,</span> <span
  m='964770'>H</span> <span m='965060'>sub</span> <span m='965225'>a</span>
  <span m='965390'>of</span> <span m='965510'>T,</span> <span
  m='966110'>the</span> <span m='966200'>H</span> <span
  m='966290'>standing</span> <span m='967100'>for</span> <span
  m='967280'>analog.</span> <span m='969380'>And</span> <span
  m='969950'>we'd</span> <span m='970160'>like</span> <span m='970400'>to</span>
  <span m='970550'>map</span> <span m='970940'>that</span> <span
  m='972710'>to</span> <span m='973340'>a</span> <span m='973640'>digital</span>
  <span m='974030'>filter</span> <span m='974660'>transfer</span> <span
  m='975170'>function,</span> <span m='975710'>H</span> <span
  m='976010'>of</span> <span m='976130'>z,</span> <span m='977150'>or</span>
  <span m='977330'>equivalently</span> <span m='978320'>map</span> <span
  m='978800'>the</span> <span m='978950'>impulse</span> <span
  m='979400'>response</span> <span m='980420'>to</span> <span
  m='980870'>a</span> <span m='981230'>digital</span> <span
  m='982400'>filter</span> <span m='983240'>unit</span> <span
  m='983570'>sample</span> <span m='983960'>response,</span> <span
  m='984610'>H</span> <span m='984890'>of</span> <span m='985220'>n.</span>
  <span m='986180'>And</span> <span m='986300'>we'd</span> <span
  m='986450'>like</span> <span m='986630'>to</span> <span m='986750'>do</span>
  <span m='986960'>this,</span> <span m='987330'>of</span> <span
  m='987350'>course,</span> <span m='988350'>in</span> <span
  m='988450'>such</span> <span m='988610'>a</span> <span m='988670'>way</span>
  <span m='989270'>that</span> <span m='989630'>if</span> <span
  m='990230'>this</span> <span m='990530'>was</span> <span m='990740'>a</span>
  <span m='990800'>good</span> <span m='991040'>filter</span> <span
  m='992450'>in</span> <span m='992930'>the</span> <span
  m='993140'>analog</span> <span m='993620'>domain,</span> <span
  m='994640'>then</span> <span m='994790'>this</span> <span
  m='995000'>will</span> <span m='995130'>be</span> <span m='995300'>a</span>
  <span m='995390'>good</span> <span m='995600'>filter</span> <span
  m='996140'>in</span> <span m='996290'>the</span> <span
  m='996380'>digital</span> <span m='996770'>domain.</span> </p><p><span
  m='999390'>Well,</span> <span m='999720'>of</span> <span
  m='999870'>course</span> <span m='1000470'>in</span> <span
  m='1000950'>designing</span> <span m='1001520'>digital</span> <span
  m='1001910'>filters</span> <span m='1002810'>by</span> <span
  m='1003200'>implementing</span> <span m='1003740'>and</span> <span
  m='1003830'>mapping</span> <span m='1004760'>of</span> <span
  m='1005210'>the</span> <span m='1005330'>type</span> <span
  m='1005750'>that</span> <span m='1005900'>we're</span> <span
  m='1006020'>talking</span> <span m='1006500'>about,</span> <span
  m='1007340'>there</span> <span m='1007730'>are</span> <span
  m='1007910'>some</span> <span m='1008120'>obvious</span> <span
  m='1008540'>restrictions</span> <span m='1009680'>that</span> <span
  m='1009920'>we</span> <span m='1010100'>would</span> <span
  m='1010250'>like</span> <span m='1010430'>to</span> <span
  m='1010610'>impose,</span> <span m='1012230'>one</span> <span
  m='1012440'>of</span> <span m='1012590'>which</span> <span
  m='1013160'>is</span> <span m='1013400'>that</span> <span
  m='1013790'>we</span> <span m='1014000'>would</span> <span
  m='1014180'>like</span> <span m='1015680'>the</span> <span
  m='1015800'>behavior</span> <span m='1016970'>of</span> <span
  m='1017510'>H</span> <span m='1017770'>sub</span> <span m='1017940'>a</span>
  <span m='1018110'>of</span> <span m='1018500'>S,</span> <span
  m='1018710'>the</span> <span m='1018860'>analog</span> <span
  m='1019340'>system</span> <span m='1019760'>function,</span> <span
  m='1021440'>on</span> <span m='1021680'>the</span> <span m='1021800'>j</span>
  <span m='1022070'>omega</span> <span m='1022460'>axis</span> <span
  m='1024740'>to</span> <span m='1024859'>map</span> <span m='1025550'>to</span>
  <span m='1026569'>a</span> <span m='1026780'>corresponding</span> <span
  m='1028069'>behavior</span> <span m='1028910'>on</span> <span
  m='1029089'>the</span> <span m='1029180'>unit</span> <span
  m='1029480'>circle.</span> <span m='1030940'>The</span> <span
  m='1031030'>point,</span> <span m='1031430'>of</span> <span
  m='1031450'>course,</span> <span m='1032089'>is</span> <span
  m='1032260'>that</span> <span m='1034050'>an</span> <span
  m='1034380'>analog</span> <span m='1034920'>system</span> <span
  m='1035339'>function</span> <span m='1036240'>or</span> <span
  m='1036599'>an</span> <span m='1036720'>analog</span> <span
  m='1037349'>filter,</span> <span m='1038690'>an</span> <span
  m='1038790'>analog</span> <span m='1039180'>frequency</span> <span
  m='1039720'>response,</span> <span m='1040980'>when</span> <span
  m='1041130'>we</span> <span m='1041220'>talk</span> <span
  m='1041550'>about</span> <span m='1041760'>the</span> <span
  m='1041880'>frequency</span> <span m='1042390'>response,</span> <span
  m='1043319'>we're</span> <span m='1043440'>looking</span> <span
  m='1043829'>in</span> <span m='1043950'>the</span> <span
  m='1044069'>s-plane</span> <span m='1044700'>on</span> <span
  m='1044849'>the</span> <span m='1044970'>j</span> <span
  m='1045225'>omega</span> <span m='1045599'>axis.</span> <span
  m='1047040'>And</span> <span m='1047819'>for</span> <span
  m='1048210'>the</span> <span m='1048329'>digital</span> <span
  m='1048750'>filter,</span> <span m='1049795'>it</span> <span
  m='1050090'>is</span> <span m='1051030'>the</span> <span
  m='1051180'>behavior</span> <span m='1051810'>of</span> <span
  m='1051930'>the</span> <span m='1052020'>system</span> <span
  m='1052440'>function</span> <span m='1052920'>on</span> <span
  m='1053130'>the</span> <span m='1053220'>unit</span> <span
  m='1053550'>circle</span> <span m='1054270'>that</span> <span
  m='1054390'>dictates</span> <span m='1055020'>what</span> <span
  m='1055200'>the</span> <span m='1055290'>frequency</span> <span
  m='1055830'>response</span> <span m='1056340'>is</span> <span
  m='1056490'>like.</span> <span m='1058020'>If</span> <span
  m='1058170'>the</span> <span m='1058290'>analog</span> <span
  m='1058740'>filter</span> <span m='1059190'>has</span> <span
  m='1059400'>a</span> <span m='1059460'>good</span> <span
  m='1060300'>frequency</span> <span m='1060840'>response--</span> <span
  m='1061500'>in</span> <span m='1061620'>other</span> <span
  m='1061800'>words,</span> <span m='1062200'>it</span> <span
  m='1062300'>has</span> <span m='1062700'>a</span> <span
  m='1062820'>good</span> <span m='1063030'>behavior</span> <span
  m='1063660'>on</span> <span m='1063780'>the</span> <span m='1064080'>j</span>
  <span m='1064180'>omega</span> <span m='1064440'>axis--</span> <span
  m='1065710'>that's</span> <span m='1065940'>what</span> <span
  m='1066120'>we</span> <span m='1066270'>would</span> <span
  m='1066420'>like</span> <span m='1066660'>to</span> <span
  m='1066780'>have</span> <span m='1066990'>mapped</span> <span
  m='1067380'>over</span> <span m='1068280'>to</span> <span m='1068940'>a</span>
  <span m='1069690'>good</span> <span m='1070110'>behavior</span> <span
  m='1071070'>in</span> <span m='1071190'>the</span> <span
  m='1071280'>z-plane</span> <span m='1072000'>on</span> <span
  m='1072180'>the</span> <span m='1072270'>unit</span> <span
  m='1072570'>circle.</span> </p><p><span m='1074380'>So</span> <span
  m='1074820'>this</span> <span m='1075330'>then</span> <span
  m='1075750'>is</span> <span m='1076680'>the</span> <span
  m='1076740'>first</span> <span m='1077040'>condition</span> <span
  m='1077550'>that</span> <span m='1077640'>we</span> <span
  m='1077820'>would</span> <span m='1077940'>like</span> <span
  m='1078150'>to</span> <span m='1078300'>impose.</span> <span
  m='1079500'>And</span> <span m='1079680'>a</span> <span
  m='1079740'>second</span> <span m='1080070'>condition</span> <span
  m='1080850'>that</span> <span m='1081030'>it's</span> <span
  m='1081180'>reasonable</span> <span m='1081720'>to</span> <span
  m='1081870'>impose</span> <span m='1082590'>is</span> <span
  m='1082860'>that</span> <span m='1083910'>a</span> <span
  m='1084630'>stable</span> <span m='1086220'>analog</span> <span
  m='1086760'>system</span> <span m='1087180'>function</span> <span
  m='1088350'>mapped</span> <span m='1088760'>to</span> <span
  m='1089250'>a</span> <span m='1089310'>stable</span> <span
  m='1090240'>digital</span> <span m='1090900'>system</span> <span
  m='1091320'>function.</span> <span m='1092830'>In</span> <span
  m='1092950'>other</span> <span m='1093100'>words,</span> <span
  m='1093310'>we'd</span> <span m='1093460'>like</span> <span
  m='1093700'>to</span> <span m='1093850'>be</span> <span
  m='1093970'>confident</span> <span m='1095560'>that</span> <span
  m='1095800'>our</span> <span m='1095980'>design</span> <span
  m='1096460'>procedure</span> <span m='1097060'>is</span> <span
  m='1097150'>such</span> <span m='1098290'>that</span> <span
  m='1098680'>if</span> <span m='1099220'>we</span> <span m='1099490'>had</span>
  <span m='1099730'>a</span> <span m='1099820'>good</span> <span
  m='1100300'>analog</span> <span m='1100810'>filter</span> <span
  m='1101230'>and</span> <span m='1101320'>it</span> <span
  m='1101380'>was</span> <span m='1101530'>stable,</span> <span
  m='1103390'>that</span> <span m='1103570'>when</span> <span
  m='1103750'>we</span> <span m='1103900'>were</span> <span
  m='1104050'>all</span> <span m='1104260'>done,</span> <span
  m='1104770'>we</span> <span m='1104950'>would</span> <span
  m='1105100'>end</span> <span m='1105340'>up</span> <span
  m='1105670'>with</span> <span m='1105820'>a</span> <span
  m='1105880'>good</span> <span m='1106090'>digital</span> <span
  m='1106510'>filter</span> <span m='1107200'>that</span> <span
  m='1107350'>was</span> <span m='1107500'>also</span> <span
  m='1107860'>stable.</span> <span m='1108970'>So</span> <span
  m='1109510'>these,</span> <span m='1109840'>then,</span> <span
  m='1110260'>are</span> <span m='1110650'>two</span> <span
  m='1110890'>of</span> <span m='1111040'>the</span> <span
  m='1111580'>conditions</span> <span m='1112690'>that</span> <span
  m='1113050'>are</span> <span m='1113230'>basic</span> <span
  m='1114280'>to</span> <span m='1114640'>any</span> <span
  m='1114910'>design</span> <span m='1115360'>procedure</span> <span
  m='1116440'>that</span> <span m='1116590'>maps</span> <span
  m='1117010'>from</span> <span m='1117250'>continuous</span> <span
  m='1117850'>time</span> <span m='1118180'>to</span> <span
  m='1118300'>discrete</span> <span m='1118690'>time.</span> </p><p><span
  m='1121350'>Well,</span> <span m='1121770'>there</span> <span
  m='1122250'>are</span> <span m='1122760'>a</span> <span
  m='1122850'>number</span> <span m='1123510'>of</span> <span
  m='1124080'>procedures</span> <span m='1125220'>that</span> <span
  m='1125760'>are</span> <span m='1125970'>available.</span> <span
  m='1127420'>One</span> <span m='1127470'>of</span> <span
  m='1127560'>the</span> <span m='1127650'>first</span> <span
  m='1128490'>that</span> <span m='1129570'>tends</span> <span
  m='1129870'>to</span> <span m='1130020'>come</span> <span
  m='1130230'>to</span> <span m='1130380'>mind</span> <span
  m='1130830'>when</span> <span m='1131010'>you</span> <span
  m='1131130'>think</span> <span m='1131460'>of</span> <span
  m='1131610'>mapping</span> <span m='1132720'>a</span> <span
  m='1132840'>continuous</span> <span m='1133450'>time</span> <span
  m='1133740'>filter</span> <span m='1134430'>to</span> <span
  m='1134640'>a</span> <span m='1134670'>discrete</span> <span
  m='1135090'>time</span> <span m='1135390'>filter</span> <span
  m='1136470'>is</span> <span m='1136920'>to</span> <span
  m='1137100'>approximate</span> <span m='1137940'>in</span> <span
  m='1138090'>some</span> <span m='1138360'>sense,</span> <span
  m='1139380'>let's</span> <span m='1139470'>say</span> <span
  m='1139650'>the</span> <span m='1139770'>differential</span> <span
  m='1140370'>equation</span> <span m='1141000'>for</span> <span
  m='1141150'>the</span> <span m='1141300'>analog</span> <span
  m='1141990'>filter,</span> <span m='1143100'>by</span> <span
  m='1143310'>simply</span> <span m='1143940'>replacing</span> <span
  m='1144720'>the</span> <span m='1144810'>derivatives</span> <span
  m='1145410'>by</span> <span m='1145590'>differences.</span> <span
  m='1147760'>So</span> <span m='1148230'>the</span> <span
  m='1148350'>first</span> <span m='1148860'>method</span> <span
  m='1149250'>that</span> <span m='1149370'>I'd</span> <span
  m='1149520'>like</span> <span m='1149700'>to</span> <span
  m='1149820'>talk</span> <span m='1150180'>about</span> <span
  m='1150690'>is</span> <span m='1151500'>a</span> <span
  m='1151560'>method</span> <span m='1153210'>which</span> <span
  m='1153840'>corresponds</span> <span m='1155160'>to</span> <span
  m='1156390'>going</span> <span m='1156750'>from</span> <span
  m='1157170'>the</span> <span m='1157350'>analog</span> <span
  m='1157830'>filter</span> <span m='1158220'>to</span> <span
  m='1158370'>the</span> <span m='1158460'>digital</span> <span
  m='1158880'>filter</span> <span m='1160080'>by</span> <span
  m='1160710'>mapping</span> <span m='1161220'>differentials</span> <span
  m='1162720'>in</span> <span m='1162810'>the</span> <span
  m='1162930'>analog</span> <span m='1163410'>domain</span> <span
  m='1164310'>to</span> <span m='1164430'>differences</span> <span
  m='1165450'>in</span> <span m='1166290'>the</span> <span
  m='1166530'>digital</span> <span m='1166920'>domain.</span> <span
  m='1167940'>And</span> <span m='1168090'>let</span> <span
  m='1168240'>me</span> <span m='1168750'>tell</span> <span
  m='1168960'>you</span> <span m='1169110'>in</span> <span
  m='1169230'>advance</span> <span m='1170100'>that</span> <span
  m='1171150'>what</span> <span m='1171330'>we'll</span> <span
  m='1171510'>see,</span> <span m='1171900'>in</span> <span
  m='1172020'>fact,</span> <span m='1172590'>is</span> <span
  m='1172830'>that</span> <span m='1173040'>although</span> <span
  m='1173370'>this</span> <span m='1173610'>is</span> <span
  m='1173820'>intuitively</span> <span m='1175500'>one</span> <span
  m='1175740'>of</span> <span m='1175980'>the</span> <span
  m='1176100'>first</span> <span m='1176400'>methods</span> <span
  m='1177060'>that</span> <span m='1177180'>tends</span> <span
  m='1177510'>to</span> <span m='1177630'>come</span> <span
  m='1177870'>to</span> <span m='1177990'>mind,</span> <span
  m='1179220'>that</span> <span m='1179550'>in</span> <span
  m='1179730'>fact,</span> <span m='1180390'>it</span> <span
  m='1180680'>is</span> <span m='1180930'>not</span> <span m='1181290'>a</span>
  <span m='1181440'>particularly</span> <span m='1182130'>good</span> <span
  m='1182340'>method</span> <span m='1182820'>in</span> <span
  m='1182970'>terms</span> <span m='1183510'>of</span> <span
  m='1183870'>the</span> <span m='1183960'>basic</span> <span
  m='1184320'>guidelines</span> <span m='1184950'>that</span> <span
  m='1185070'>we've</span> <span m='1185220'>set</span> <span
  m='1185490'>down.</span> </p><p><span m='1186730'>But</span> <span
  m='1186780'>let's</span> <span m='1186990'>go</span> <span
  m='1187140'>through</span> <span m='1187350'>the</span> <span
  m='1187440'>method</span> <span m='1187770'>anyway.</span> <span
  m='1189480'>Here</span> <span m='1189690'>we</span> <span
  m='1189840'>have</span> <span m='1190050'>an</span> <span
  m='1190140'>analog</span> <span m='1190650'>system</span> <span
  m='1191040'>function,</span> <span m='1191810'>H</span> <span
  m='1192210'>sub</span> <span m='1192285'>a</span> <span m='1192360'>of</span>
  <span m='1192675'>S.</span> <span m='1194080'>And</span> <span
  m='1194860'>the</span> <span m='1195040'>corresponding</span> <span
  m='1195790'>differential</span> <span m='1196390'>equation,</span> <span
  m='1197830'>the</span> <span m='1197920'>filter</span> <span
  m='1198400'>then</span> <span m='1198730'>is</span> <span
  m='1198940'>described</span> <span m='1199900'>in</span> <span
  m='1200020'>terms</span> <span m='1200590'>of</span> <span
  m='1201040'>a</span> <span m='1201130'>linear</span> <span
  m='1201430'>combination</span> <span m='1202120'>of</span> <span
  m='1202210'>derivatives</span> <span m='1202810'>of</span> <span
  m='1202930'>the</span> <span m='1203080'>output</span> <span
  m='1204280'>equal</span> <span m='1204640'>to</span> <span
  m='1204850'>a</span> <span m='1204880'>linear</span> <span
  m='1205210'>combination</span> <span m='1206140'>of</span> <span
  m='1206680'>derivatives</span> <span m='1207400'>of</span> <span
  m='1207580'>the</span> <span m='1207730'>input.</span> </p><p><span
  m='1209390'>Now</span> <span m='1210010'>we</span> <span
  m='1210190'>want</span> <span m='1210760'>to</span> <span
  m='1211000'>convert</span> <span m='1211510'>this</span> <span
  m='1212050'>in</span> <span m='1212170'>some</span> <span
  m='1212500'>way</span> <span m='1213400'>to</span> <span m='1213880'>a</span>
  <span m='1213970'>difference</span> <span m='1214390'>equation.</span> <span
  m='1215880'>And</span> <span m='1217120'>so</span> <span m='1217630'>we</span>
  <span m='1217840'>can</span> <span m='1218050'>consider</span> <span
  m='1220140'>replacing</span> <span m='1221730'>y</span> <span
  m='1222020'>sub</span> <span m='1222205'>a</span> <span m='1222390'>of</span>
  <span m='1222540'>t</span> <span m='1224290'>by</span> <span
  m='1224950'>y</span> <span m='1225310'>of</span> <span m='1225460'>n,</span>
  <span m='1225820'>y</span> <span m='1226090'>of</span> <span
  m='1226220'>n,</span> <span m='1226360'>of</span> <span
  m='1226450'>course</span> <span m='1226750'>is</span> <span
  m='1226870'>the</span> <span m='1226990'>output</span> <span
  m='1227380'>of</span> <span m='1227470'>the</span> <span
  m='1227560'>digital</span> <span m='1227980'>filter,</span> <span
  m='1229270'>in</span> <span m='1229390'>such</span> <span m='1229690'>a</span>
  <span m='1229780'>way</span> <span m='1230830'>that</span> <span
  m='1231460'>the</span> <span m='1231580'>derivative,</span> <span
  m='1232330'>a</span> <span m='1232390'>first</span> <span
  m='1232720'>derivative</span> <span m='1233980'>sampled</span> <span
  m='1234940'>at</span> <span m='1235120'>t</span> <span
  m='1235630'>equal</span> <span m='1235990'>to</span> <span
  m='1236245'>n</span> <span m='1236500'>times</span> <span m='1237580'>T</span>
  <span m='1239270'>gets</span> <span m='1239510'>replaced</span> <span
  m='1240110'>by</span> <span m='1240800'>the</span> <span
  m='1240920'>first</span> <span m='1241280'>difference</span> <span
  m='1242030'>of</span> <span m='1242360'>the</span> <span
  m='1242480'>output</span> <span m='1242870'>of</span> <span
  m='1242960'>the</span> <span m='1243080'>digital</span> <span
  m='1243440'>filter.</span> <span m='1245030'>Where</span> <span
  m='1245660'>the</span> <span m='1245780'>first</span> <span
  m='1246110'>difference</span> <span m='1246820'>I'm</span> <span
  m='1247040'>defining</span> <span m='1247790'>as</span> <span
  m='1248660'>the</span> <span m='1248750'>first</span> <span
  m='1249200'>forward</span> <span m='1249680'>difference.</span> <span
  m='1250490'>That</span> <span m='1250700'>is,</span> <span
  m='1250880'>y</span> <span m='1251015'>of</span> <span m='1251150'>n</span>
  <span m='1251420'>plus</span> <span m='1251720'>1</span> <span
  m='1252170'>minus</span> <span m='1252500'>y</span> <span
  m='1252820'>of</span> <span m='1253125'>n</span> <span
  m='1253430'>divided</span> <span m='1253850'>by</span> <span
  m='1254030'>T.</span> <span m='1255710'>So</span> <span m='1255920'>the</span>
  <span m='1256040'>idea</span> <span m='1256460'>here</span> <span
  m='1257360'>is</span> <span m='1257480'>basically</span> <span
  m='1258050'>to</span> <span m='1258140'>say,</span> <span
  m='1258410'>well</span> <span m='1258530'>look,</span> <span
  m='1258830'>I</span> <span m='1259010'>can</span> <span
  m='1259190'>generate</span> <span m='1259880'>a</span> <span
  m='1259940'>difference</span> <span m='1260390'>equation</span> <span
  m='1261410'>from</span> <span m='1261590'>this</span> <span
  m='1261740'>differential</span> <span m='1262340'>equation</span> <span
  m='1263540'>by</span> <span m='1264080'>replacing</span> <span
  m='1264710'>the</span> <span m='1264830'>derivatives</span> <span
  m='1266030'>by</span> <span m='1266810'>differences--</span> <span
  m='1267530'>in</span> <span m='1267860'>the</span> <span
  m='1267980'>particular</span> <span m='1268430'>case</span> <span
  m='1268830'>I'm</span> <span m='1268880'>talking</span> <span
  m='1269330'>about,</span> <span m='1269630'>by</span> <span
  m='1269810'>forward</span> <span m='1270230'>differences.</span> </p><p><span
  m='1271370'>And</span> <span m='1271500'>what</span> <span
  m='1271705'>will</span> <span m='1271910'>result</span> <span
  m='1272330'>is</span> <span m='1272450'>a</span> <span
  m='1272510'>difference</span> <span m='1272900'>equation,</span> <span
  m='1273500'>and</span> <span m='1273620'>consequently</span> <span
  m='1274340'>what</span> <span m='1274490'>also</span> <span
  m='1274820'>results</span> <span m='1275360'>is</span> <span
  m='1275510'>a</span> <span m='1275570'>digital</span> <span
  m='1275930'>filter.</span> <span m='1278240'>Incidentally,</span> <span
  m='1279020'>I'm</span> <span m='1279410'>talking</span> <span
  m='1279890'>about</span> <span m='1280280'>this</span> <span
  m='1280670'>here</span> <span m='1281930'>for</span> <span
  m='1282650'>the</span> <span m='1282740'>case</span> <span
  m='1283130'>of</span> <span m='1283220'>forward</span> <span
  m='1283610'>differences</span> <span m='1284720'>in</span> <span
  m='1284810'>the</span> <span m='1284900'>text</span> <span
  m='1285980'>to</span> <span m='1286370'>see</span> <span
  m='1286610'>the</span> <span m='1286700'>contrast.</span> <span
  m='1289336'>We</span> <span m='1289760'>talk</span> <span
  m='1290060'>about</span> <span m='1290570'>a</span> <span
  m='1290630'>similar</span> <span m='1291050'>procedure,</span> <span
  m='1291710'>but</span> <span m='1292340'>with</span> <span
  m='1292520'>the</span> <span m='1292580'>use</span> <span
  m='1292820'>of</span> <span m='1292910'>backward</span> <span
  m='1293330'>differences</span> <span m='1293900'>rather</span> <span
  m='1294200'>than</span> <span m='1294350'>forward</span> <span
  m='1294770'>differences.</span> </p><p><span m='1297370'>All</span> <span
  m='1297460'>right,</span> <span m='1297670'>well</span> <span
  m='1298390'>let's</span> <span m='1298630'>see,</span> <span
  m='1299050'>in</span> <span m='1299230'>fact,</span> <span
  m='1299680'>what</span> <span m='1299920'>happens</span> <span
  m='1300400'>then.</span> <span m='1301420'>We</span> <span
  m='1302020'>want</span> <span m='1302260'>to</span> <span
  m='1302350'>replace</span> <span m='1303160'>a</span> <span
  m='1304180'>first</span> <span m='1304510'>derivative</span> <span
  m='1305530'>by</span> <span m='1305740'>a</span> <span
  m='1305800'>first</span> <span m='1306400'>forward</span> <span
  m='1306820'>difference.</span> <span m='1308080'>More</span> <span
  m='1308320'>generally,</span> <span m='1309260'>what</span> <span
  m='1309400'>we</span> <span m='1309580'>would</span> <span
  m='1309730'>want</span> <span m='1309970'>to</span> <span
  m='1310540'>replace</span> <span m='1311320'>a</span> <span
  m='1311770'>k-th</span> <span m='1312670'>derivative</span> <span
  m='1313450'>by</span> <span m='1314530'>is</span> <span m='1315130'>the</span>
  <span m='1315250'>k-th</span> <span m='1315910'>forward</span> <span
  m='1316420'>difference,</span> <span m='1317560'>where</span> <span
  m='1318130'>the</span> <span m='1318250'>k-th</span> <span
  m='1318640'>forward</span> <span m='1319120'>difference</span> <span
  m='1319750'>is</span> <span m='1319930'>defined</span> <span
  m='1320440'>iteratively.</span> <span m='1322090'>In</span> <span
  m='1322210'>other</span> <span m='1322420'>words,</span> <span
  m='1322970'>the</span> <span m='1323070'>k-th</span> <span
  m='1323230'>forward</span> <span m='1323680'>difference</span> <span
  m='1324190'>of</span> <span m='1324310'>y</span> <span m='1324600'>of</span>
  <span m='1324730'>n</span> <span m='1325510'>is</span> <span
  m='1325660'>the</span> <span m='1325780'>first</span> <span
  m='1326350'>forward</span> <span m='1326770'>difference</span> <span
  m='1327490'>of</span> <span m='1327940'>the</span> <span m='1328060'>k</span>
  <span m='1328300'>minus</span> <span m='1328670'>first</span> <span
  m='1329680'>forward</span> <span m='1330040'>difference</span> <span
  m='1330460'>of</span> <span m='1330580'>y</span> <span m='1330765'>of</span>
  <span m='1330950'>n.</span> <span m='1331510'>Simply</span> <span
  m='1332500'>the</span> <span m='1332590'>k-th</span> <span
  m='1332860'>forward</span> <span m='1333220'>difference</span> <span
  m='1334120'>to</span> <span m='1334210'>correspond</span> <span
  m='1334990'>to</span> <span m='1335110'>the</span> <span
  m='1335230'>k-th</span> <span m='1335560'>derivative</span> <span
  m='1336670'>is</span> <span m='1337570'>the</span> <span
  m='1337840'>first</span> <span m='1338560'>difference</span> <span
  m='1339730'>implemented</span> <span m='1340240'>over</span> <span
  m='1340510'>and</span> <span m='1340600'>over</span> <span
  m='1340840'>and</span> <span m='1340930'>over</span> <span
  m='1341170'>again,</span> <span m='1341590'>k</span> <span
  m='1341890'>times.</span> </p><p><span m='1343870'>So</span> <span
  m='1344320'>what</span> <span m='1344560'>results</span> <span
  m='1345090'>then</span> <span m='1347500'>by</span> <span
  m='1347710'>making</span> <span m='1348100'>this</span> <span
  m='1348250'>substitution,</span> <span m='1349870'>is</span> <span
  m='1350080'>that</span> <span m='1350260'>the</span> <span
  m='1350380'>differential</span> <span m='1351010'>equation</span> <span
  m='1351730'>that</span> <span m='1351880'>we</span> <span
  m='1352060'>had,</span> <span m='1353000'>which</span> <span
  m='1353110'>was</span> <span m='1353290'>a</span> <span
  m='1353350'>linear</span> <span m='1353680'>combination</span> <span
  m='1354670'>of</span> <span m='1355670'>the</span> <span
  m='1355810'>derivatives</span> <span m='1356650'>of</span> <span
  m='1356800'>y</span> <span m='1357130'>of</span> <span m='1357250'>t</span>
  <span m='1357730'>equal</span> <span m='1358180'>to</span> <span
  m='1358360'>a</span> <span m='1358390'>linear</span> <span
  m='1358690'>combination</span> <span m='1359470'>of</span> <span
  m='1359650'>the</span> <span m='1359740'>derivatives</span> <span
  m='1360340'>of</span> <span m='1360460'>x</span> <span m='1360700'>of</span>
  <span m='1360820'>t,</span> <span m='1361780'>that's</span> <span
  m='1362050'>replaced</span> <span m='1362530'>by</span> <span
  m='1362740'>the</span> <span m='1362860'>same</span> <span
  m='1363130'>linear</span> <span m='1363430'>combination</span> <span
  m='1364420'>of</span> <span m='1365110'>the</span> <span
  m='1365200'>k-th</span> <span m='1365920'>difference</span> <span
  m='1366400'>of</span> <span m='1366520'>y</span> <span m='1366790'>of</span>
  <span m='1366940'>n</span> <span m='1367690'>equal</span> <span
  m='1368050'>to</span> <span m='1368620'>the</span> <span
  m='1368950'>corresponding</span> <span m='1369700'>linear</span> <span
  m='1370030'>combination</span> <span m='1370840'>of</span> <span
  m='1371560'>the</span> <span m='1371800'>k-th</span> <span
  m='1372370'>differences</span> <span m='1373600'>of</span> <span
  m='1373960'>x</span> <span m='1374260'>of</span> <span m='1374360'>n.</span>
  <span m='1375650'>And</span> <span m='1376520'>this</span> <span
  m='1376790'>then</span> <span m='1377390'>is</span> <span m='1377930'>a</span>
  <span m='1377990'>difference</span> <span m='1378470'>equation,</span> <span
  m='1380510'>because</span> <span m='1380900'>of</span> <span
  m='1381020'>the</span> <span m='1381110'>fact</span> <span
  m='1381860'>that</span> <span m='1382220'>each</span> <span
  m='1382490'>of</span> <span m='1382610'>these</span> <span
  m='1382790'>differences,</span> <span m='1384350'>each</span> <span
  m='1384620'>of</span> <span m='1384980'>these</span> <span
  m='1385220'>four</span> <span m='1385550'>differences,</span> <span
  m='1386150'>or</span> <span m='1386240'>the</span> <span
  m='1386360'>k-th</span> <span m='1386630'>forward</span> <span
  m='1386900'>difference,</span> <span m='1387440'>involves</span> <span
  m='1388370'>differences</span> <span m='1389090'>of</span> <span
  m='1389270'>y</span> <span m='1389520'>of</span> <span m='1389730'>n.</span>
  <span m='1389850'>That</span> <span m='1389960'>is</span> <span
  m='1390080'>why</span> <span m='1390330'>even</span> <span
  m='1390530'>plus</span> <span m='1390830'>1</span> <span
  m='1391040'>minus</span> <span m='1391400'>y</span> <span
  m='1391670'>of</span> <span m='1391770'>n</span> <span m='1392540'>So</span>
  <span m='1393260'>this</span> <span m='1393470'>is</span> <span
  m='1393620'>a</span> <span m='1393680'>difference</span> <span
  m='1394070'>equation</span> <span m='1395390'>derived</span> <span
  m='1396200'>from</span> <span m='1396860'>the</span> <span
  m='1397130'>differential</span> <span m='1397760'>equation</span> <span
  m='1398780'>by</span> <span m='1398930'>replacing</span> <span
  m='1399560'>the</span> <span m='1399650'>k-th</span> <span
  m='1399950'>derivative</span> <span m='1400850'>by</span> <span
  m='1401000'>the</span> <span m='1401090'>k-th</span> <span
  m='1401390'>forward</span> <span m='1401790'>difference.</span> </p><p><span
  m='1403690'>Well</span> <span m='1403810'>let's</span> <span
  m='1403960'>see</span> <span m='1404170'>what</span> <span
  m='1404320'>this</span> <span m='1404530'>means</span> <span
  m='1404980'>in</span> <span m='1405100'>terms</span> <span
  m='1405670'>of</span> <span m='1406840'>the</span> <span
  m='1407530'>mapping</span> <span m='1408100'>from</span> <span
  m='1408310'>the</span> <span m='1408460'>s-plane</span> <span
  m='1408940'>to</span> <span m='1409060'>the</span> <span
  m='1409180'>z-plane.</span> <span m='1411790'>First</span> <span
  m='1412120'>of</span> <span m='1412240'>all,</span> <span
  m='1412790'>let</span> <span m='1412870'>me</span> <span
  m='1413020'>remind</span> <span m='1413530'>you</span> <span
  m='1414130'>that</span> <span m='1414850'>in</span> <span
  m='1415090'>the</span> <span m='1415240'>continuous</span> <span
  m='1415840'>time</span> <span m='1416170'>domain,</span> <span
  m='1417730'>the</span> <span m='1417820'>Laplace</span> <span
  m='1418300'>transform</span> <span m='1419320'>of</span> <span
  m='1420070'>the</span> <span m='1420160'>derivative</span> <span
  m='1421000'>of</span> <span m='1421150'>a</span> <span m='1421210'>time</span>
  <span m='1421540'>function</span> <span m='1423040'>is</span> <span
  m='1423190'>equal</span> <span m='1423670'>to</span> <span
  m='1424000'>s</span> <span m='1424840'>times</span> <span
  m='1425260'>the</span> <span m='1425350'>Laplace</span> <span
  m='1425770'>transform</span> <span m='1426370'>of</span> <span
  m='1426490'>the</span> <span m='1426580'>time</span> <span
  m='1426880'>function.</span> <span m='1427360'>That</span> <span
  m='1427540'>is,</span> <span m='1428620'>the</span> <span
  m='1429100'>operation</span> <span m='1429700'>of</span> <span
  m='1429790'>differentiation</span> <span m='1430590'>in</span> <span
  m='1430990'>the</span> <span m='1431320'>Laplace</span> <span
  m='1431690'>transform</span> <span m='1432310'>domain</span> <span
  m='1433210'>gets</span> <span m='1433390'>carried</span> <span
  m='1433810'>over</span> <span m='1434170'>to</span> <span m='1434320'>a</span>
  <span m='1434380'>multiplication</span> <span m='1435190'>by</span> <span
  m='1435430'>s.</span> </p><p><span m='1437470'>Similarly,</span> <span
  m='1438640'>we</span> <span m='1438820'>can</span> <span
  m='1438970'>look</span> <span m='1439180'>at</span> <span
  m='1439270'>the</span> <span m='1439360'>z</span> <span
  m='1439600'>transform</span> <span m='1440590'>of</span> <span
  m='1441280'>the</span> <span m='1441400'>first</span> <span
  m='1441730'>difference,</span> <span m='1443650'>the</span> <span
  m='1443920'>z</span> <span m='1444160'>transform</span> <span
  m='1444880'>of</span> <span m='1445000'>the</span> <span
  m='1445120'>first</span> <span m='1445420'>difference,</span> <span
  m='1445960'>y</span> <span m='1446120'>of</span> <span m='1446280'>n</span>
  <span m='1446440'>plus</span> <span m='1446740'>1</span> <span
  m='1446980'>minus</span> <span m='1447310'>y</span> <span
  m='1447580'>of</span> <span m='1447670'>n</span> <span
  m='1447850'>divided</span> <span m='1448240'>by</span> <span
  m='1448760'>T,</span> <span m='1449890'>simply</span> <span
  m='1450310'>by</span> <span m='1450610'>applying</span> <span
  m='1451000'>the</span> <span m='1451090'>properties</span> <span
  m='1451690'>of</span> <span m='1451780'>z</span> <span
  m='1451990'>transforms,</span> <span m='1453430'>results</span> <span
  m='1453970'>in</span> <span m='1454420'>z</span> <span
  m='1454690'>minus</span> <span m='1455110'>1</span> <span
  m='1455500'>divided</span> <span m='1455950'>by</span> <span
  m='1456490'>T</span> <span m='1457420'>times</span> <span
  m='1457930'>the</span> <span m='1458050'>z</span> <span
  m='1458260'>transform</span> <span m='1459190'>of</span> <span
  m='1459970'>y</span> <span m='1460240'>of</span> <span m='1460340'>n.</span>
  <span m='1461590'>So</span> <span m='1462430'>the</span> <span
  m='1462580'>operation</span> <span m='1463420'>of</span> <span
  m='1463690'>taking</span> <span m='1464110'>the</span> <span
  m='1464200'>first</span> <span m='1464500'>difference</span> <span
  m='1466180'>corresponds</span> <span m='1466930'>to</span> <span
  m='1467080'>multiplying</span> <span m='1467740'>the</span> <span
  m='1467830'>z</span> <span m='1468010'>transform</span> <span
  m='1468700'>by</span> <span m='1468880'>z</span> <span
  m='1469090'>minus</span> <span m='1469480'>1</span> <span
  m='1469720'>divided</span> <span m='1470140'>by</span> <span
  m='1470640'>T.</span> </p><p><span m='1472090'>So</span> <span
  m='1472390'>in</span> <span m='1472510'>the</span> <span
  m='1472600'>continuous</span> <span m='1473110'>time</span> <span
  m='1473410'>domain,</span> <span m='1474520'>the</span> <span
  m='1474610'>derivative</span> <span m='1475480'>corresponded</span> <span
  m='1475765'>to</span> <span m='1476170'>multiplication</span> <span
  m='1476980'>by</span> <span m='1477310'>s.</span> <span m='1478090'>In</span>
  <span m='1478210'>the</span> <span m='1478480'>z</span> <span
  m='1478690'>transform</span> <span m='1479320'>domain,</span> <span
  m='1479860'>first</span> <span m='1480190'>differencing</span> <span
  m='1481210'>corresponded</span> <span m='1481900'>to</span> <span
  m='1482020'>multiplication</span> <span m='1482860'>by</span> <span
  m='1483040'>z</span> <span m='1483250'>minus</span> <span m='1483640'>1</span>
  <span m='1483850'>divided</span> <span m='1484270'>by</span> <span
  m='1485130'>T.</span> <span m='1485950'>And</span> <span
  m='1486070'>it's</span> <span m='1486220'>straightforward</span> <span
  m='1487270'>to</span> <span m='1487390'>show</span> <span
  m='1487930'>that,</span> <span m='1489650'>in</span> <span
  m='1489700'>fact,</span> <span m='1490430'>the</span> <span
  m='1490630'>k-th</span> <span m='1491680'>forward</span> <span
  m='1492070'>difference</span> <span m='1493150'>corresponds</span> <span
  m='1494110'>to</span> <span m='1494380'>multiplying</span> <span
  m='1495010'>by</span> <span m='1495220'>z</span> <span
  m='1495430'>minus</span> <span m='1495850'>1</span> <span
  m='1496030'>over</span> <span m='1496210'>t</span> <span m='1496410'>to</span>
  <span m='1496520'>the</span> <span m='1496630'>k.</span> <span
  m='1497680'>And</span> <span m='1498070'>we</span> <span
  m='1498220'>know</span> <span m='1498490'>that</span> <span
  m='1498730'>the</span> <span m='1498850'>k-th</span> <span
  m='1499270'>derivative</span> <span m='1500200'>corresponds</span> <span
  m='1501070'>to</span> <span m='1501250'>multiplication</span> <span
  m='1502030'>by</span> <span m='1502330'>s</span> <span m='1502570'>to</span>
  <span m='1502690'>the</span> <span m='1502810'>k.</span> </p><p><span
  m='1503980'>So</span> <span m='1504610'>if</span> <span m='1505120'>you</span>
  <span m='1505240'>track</span> <span m='1505630'>that</span> <span
  m='1505900'>through,</span> <span m='1506650'>put</span> <span
  m='1506890'>that</span> <span m='1507100'>into</span> <span
  m='1507370'>the</span> <span m='1507490'>difference</span> <span
  m='1507970'>equation,</span> <span m='1508690'>and</span> <span
  m='1510210'>obtain</span> <span m='1510640'>the</span> <span
  m='1510730'>system</span> <span m='1511150'>function</span> <span
  m='1511870'>for</span> <span m='1512020'>the</span> <span
  m='1512140'>digital</span> <span m='1512530'>system,</span> <span
  m='1513460'>and</span> <span m='1513550'>compare</span> <span
  m='1514000'>it</span> <span m='1514120'>with</span> <span
  m='1514270'>the</span> <span m='1514360'>system</span> <span
  m='1514750'>function</span> <span m='1515410'>for</span> <span
  m='1516160'>the</span> <span m='1516610'>analog</span> <span
  m='1517120'>system,</span> <span m='1518630'>what</span> <span
  m='1518890'>you</span> <span m='1519040'>see</span> <span
  m='1519770'>resulting</span> <span m='1520660'>is</span> <span
  m='1520900'>that</span> <span m='1522130'>the</span> <span
  m='1522520'>operation</span> <span m='1523450'>of</span> <span
  m='1524650'>replacing</span> <span m='1525280'>differentials</span> <span
  m='1526090'>by</span> <span m='1526750'>differences</span> <span
  m='1528010'>corresponds</span> <span m='1529120'>to</span> <span
  m='1529540'>obtaining</span> <span m='1531430'>the</span> <span
  m='1531760'>transfer</span> <span m='1532330'>function</span> <span
  m='1533020'>of</span> <span m='1533710'>the</span> <span
  m='1534010'>digital</span> <span m='1534460'>filter</span> <span
  m='1535690'>from</span> <span m='1536110'>the</span> <span
  m='1536200'>transfer</span> <span m='1536680'>function</span> <span
  m='1537220'>of</span> <span m='1537340'>the</span> <span
  m='1537490'>analog</span> <span m='1537970'>filter</span> <span
  m='1538990'>by</span> <span m='1539910'>the</span> <span
  m='1540010'>substitution</span> <span m='1541120'>s</span> <span
  m='1541480'>equal</span> <span m='1541870'>to</span> <span
  m='1542350'>z</span> <span m='1542620'>minus</span> <span m='1543010'>1</span>
  <span m='1543580'>divided</span> <span m='1544030'>by</span> <span
  m='1544390'>T.</span> <span m='1546950'>So</span> <span
  m='1547790'>it's</span> <span m='1547970'>basically</span> <span
  m='1548570'>a</span> <span m='1548630'>mapping</span> <span
  m='1549140'>then,</span> <span m='1550160'>S</span> <span
  m='1550880'>being</span> <span m='1551150'>replaced</span> <span
  m='1551840'>by</span> <span m='1552110'>z</span> <span
  m='1552320'>minus</span> <span m='1552680'>1</span> <span
  m='1553040'>over</span> <span m='1553770'>T,</span> <span
  m='1554720'>or</span> <span m='1554870'>equivalently,</span> <span
  m='1556190'>z</span> <span m='1556940'>is</span> <span
  m='1557120'>equal</span> <span m='1557420'>to</span> <span
  m='1557570'>1</span> <span m='1557870'>plus</span> <span m='1558290'>s</span>
  <span m='1558720'>times</span> <span m='1559580'>T.</span> <span
  m='1560510'>First</span> <span m='1560780'>point</span> <span
  m='1561110'>then</span> <span m='1561680'>is</span> <span
  m='1561860'>that</span> <span m='1562490'>this</span> <span
  m='1562670'>technique</span> <span m='1563180'>in</span> <span
  m='1563300'>fact</span> <span m='1563750'>corresponds</span> <span
  m='1565130'>to</span> <span m='1565280'>a</span> <span
  m='1565340'>mapping</span> <span m='1565910'>from</span> <span
  m='1566090'>the</span> <span m='1566240'>s-plane</span> <span
  m='1566780'>to</span> <span m='1566900'>the</span> <span
  m='1566990'>z-plane,</span> <span m='1568490'>with</span> <span
  m='1569000'>s</span> <span m='1569690'>replaced</span> <span
  m='1570230'>by</span> <span m='1570440'>a</span> <span
  m='1570500'>function</span> <span m='1570920'>of</span> <span
  m='1571010'>z.</span> </p><p><span m='1573420'>Well,</span> <span
  m='1573900'>let's</span> <span m='1574140'>see</span> <span
  m='1574320'>what</span> <span m='1574530'>this</span> <span
  m='1574680'>mapping</span> <span m='1575130'>is,</span> <span
  m='1575310'>in</span> <span m='1575430'>fact,</span> <span
  m='1576120'>and</span> <span m='1576660'>decide</span> <span
  m='1577200'>whether</span> <span m='1577710'>it</span> <span
  m='1578040'>satisfies</span> <span m='1578730'>the</span> <span
  m='1578850'>objectives</span> <span m='1579710'>that</span> <span
  m='1580110'>we</span> <span m='1580410'>set</span> <span
  m='1580710'>down</span> <span m='1580980'>before.</span> <span
  m='1583270'>Here</span> <span m='1583720'>is</span> <span m='1584350'>a</span>
  <span m='1584410'>picture</span> <span m='1584830'>of</span> <span
  m='1584920'>the</span> <span m='1585085'>s-plane,</span> <span
  m='1585850'>and</span> <span m='1586000'>here's</span> <span
  m='1586240'>the</span> <span m='1586360'>j</span> <span
  m='1586570'>omega</span> <span m='1586930'>axis.</span> <span
  m='1588520'>Below</span> <span m='1589300'>we</span> <span
  m='1589480'>have</span> <span m='1589720'>the</span> <span
  m='1589840'>z-plane,</span> <span m='1591640'>the</span> <span
  m='1591760'>imaginary</span> <span m='1592360'>axis,</span> <span
  m='1592810'>real</span> <span m='1593140'>axis,</span> <span
  m='1593860'>and</span> <span m='1594010'>the</span> <span
  m='1594100'>unit</span> <span m='1594370'>circle.</span> <span
  m='1596210'>And</span> <span m='1596320'>the</span> <span
  m='1596410'>first</span> <span m='1596950'>question</span> <span
  m='1597760'>is,</span> <span m='1598960'>what</span> <span
  m='1599740'>does</span> <span m='1600340'>the</span> <span
  m='1600460'>j</span> <span m='1600730'>omega</span> <span
  m='1601090'>axis</span> <span m='1601780'>in</span> <span
  m='1601900'>the</span> <span m='1602020'>s-plane</span> <span
  m='1603130'>map</span> <span m='1603460'>to</span> <span m='1603910'>in</span>
  <span m='1604090'>the</span> <span m='1604150'>z-plane?</span> <span
  m='1605650'>Well,</span> <span m='1606220'>we</span> <span
  m='1606370'>substitute</span> <span m='1607000'>s</span> <span
  m='1607180'>equals</span> <span m='1607510'>j</span> <span
  m='1607750'>omega,</span> <span m='1608950'>so</span> <span
  m='1609130'>that</span> <span m='1609760'>z</span> <span m='1610480'>is</span>
  <span m='1610660'>equal</span> <span m='1611020'>to</span> <span
  m='1611230'>1</span> <span m='1611560'>plus</span> <span m='1612040'>j</span>
  <span m='1612490'>omega</span> <span m='1612970'>times</span> <span
  m='1613720'>T.</span> <span m='1615310'>Consequently,</span> <span
  m='1616660'>the</span> <span m='1616780'>j</span> <span
  m='1617160'>omega</span> <span m='1617480'>axis</span> <span
  m='1618430'>in</span> <span m='1618550'>the</span> <span
  m='1618670'>s-plane</span> <span m='1619870'>for</span> <span
  m='1619990'>this</span> <span m='1620170'>particular</span> <span
  m='1620800'>method</span> <span m='1621850'>maps</span> <span
  m='1622660'>to</span> <span m='1623350'>this</span> <span
  m='1623650'>line</span> <span m='1624370'>in</span> <span
  m='1624520'>the</span> <span m='1624610'>z-plane.</span> </p><p><span
  m='1626170'>Well,</span> <span m='1626470'>is</span> <span
  m='1626590'>that</span> <span m='1626800'>good?</span> <span
  m='1627580'>No,</span> <span m='1627760'>it's</span> <span
  m='1627880'>not</span> <span m='1628150'>good,</span> <span
  m='1628900'>because</span> <span m='1629560'>it</span> <span
  m='1629740'>says</span> <span m='1630490'>that</span> <span
  m='1631120'>if</span> <span m='1631390'>we</span> <span m='1631540'>saw</span>
  <span m='1632080'>a</span> <span m='1632170'>good</span> <span
  m='1632440'>filter</span> <span m='1633040'>as</span> <span
  m='1633220'>we</span> <span m='1633370'>ran</span> <span m='1633640'>up</span>
  <span m='1633790'>and</span> <span m='1633880'>down</span> <span
  m='1634150'>this</span> <span m='1634360'>axis,</span> <span
  m='1635840'>we</span> <span m='1635920'>would</span> <span
  m='1636040'>see</span> <span m='1636490'>a</span> <span
  m='1636580'>good</span> <span m='1636850'>filter</span> <span
  m='1637360'>as</span> <span m='1637570'>we</span> <span m='1637690'>run</span>
  <span m='1637930'>up</span> <span m='1638080'>and</span> <span
  m='1638170'>down</span> <span m='1638440'>this</span> <span
  m='1638650'>line.</span> <span m='1640510'>However,</span> <span
  m='1641230'>where</span> <span m='1642130'>we</span> <span
  m='1642850'>are</span> <span m='1643030'>interested</span> <span
  m='1643870'>in</span> <span m='1644260'>the</span> <span
  m='1644380'>filter</span> <span m='1644740'>characteristics</span> <span
  m='1645540'>ending</span> <span m='1645880'>up</span> <span
  m='1646520'>are</span> <span m='1646910'>on</span> <span
  m='1647320'>the</span> <span m='1647410'>unit</span> <span
  m='1647710'>circle,</span> <span m='1648820'>which</span> <span
  m='1649030'>in</span> <span m='1649150'>fact,</span> <span
  m='1649570'>are</span> <span m='1649720'>only</span> <span
  m='1649990'>close</span> <span m='1650350'>to</span> <span
  m='1650500'>this</span> <span m='1650710'>line</span> <span
  m='1651490'>when</span> <span m='1651850'>we're</span> <span
  m='1652060'>in</span> <span m='1652180'>the</span> <span
  m='1652450'>vicinity</span> <span m='1653290'>of</span> <span
  m='1653770'>z</span> <span m='1654030'>equal</span> <span
  m='1654310'>to</span> <span m='1654460'>1.</span> </p><p><span
  m='1656290'>So</span> <span m='1656740'>in</span> <span
  m='1656890'>fact,</span> <span m='1658390'>the</span> <span
  m='1658480'>first</span> <span m='1659110'>condition</span> <span
  m='1659590'>that</span> <span m='1659710'>we</span> <span
  m='1659860'>wanted</span> <span m='1660250'>isn't</span> <span
  m='1660490'>satisfied,</span> <span m='1661780'>namely</span> <span
  m='1662080'>the</span> <span m='1662200'>j</span> <span
  m='1662410'>omega</span> <span m='1662740'>axis</span> <span
  m='1663160'>does</span> <span m='1663370'>not</span> <span
  m='1663910'>get</span> <span m='1664090'>mapped</span> <span
  m='1664660'>to</span> <span m='1664780'>the</span> <span
  m='1664900'>unit</span> <span m='1665200'>circle.</span> <span
  m='1667710'>Furthermore,</span> <span m='1669640'>stable</span> <span
  m='1670960'>analog</span> <span m='1671470'>filters</span> <span
  m='1672370'>do</span> <span m='1672490'>not</span> <span
  m='1672700'>necessarily</span> <span m='1673480'>map</span> <span
  m='1674050'>to</span> <span m='1674350'>stable</span> <span
  m='1674830'>digital</span> <span m='1675220'>filters.</span> <span
  m='1675830'>For</span> <span m='1675910'>example,</span> <span
  m='1677720'>if</span> <span m='1677800'>we</span> <span m='1677920'>had</span>
  <span m='1678100'>a</span> <span m='1678160'>pole,</span> <span
  m='1679270'>let's</span> <span m='1679510'>say</span> <span
  m='1679810'>in</span> <span m='1679900'>the</span> <span
  m='1680110'>s-plane</span> <span m='1680620'>there,</span> <span
  m='1682310'>then</span> <span m='1683510'>it</span> <span
  m='1683660'>would</span> <span m='1683900'>fall</span> <span
  m='1684740'>in</span> <span m='1684860'>the</span> <span
  m='1684950'>z-plane,</span> <span m='1685820'>let's</span> <span
  m='1686060'>say</span> <span m='1686360'>there.</span> </p><p><span
  m='1687020'>Well,</span> <span m='1687380'>that's</span> <span
  m='1687650'>all</span> <span m='1687770'>right.</span> <span
  m='1688160'>That's</span> <span m='1688400'>a</span> <span
  m='1688460'>stable</span> <span m='1689510'>pole,</span> <span
  m='1690560'>stable</span> <span m='1690950'>analog</span> <span
  m='1691400'>filter</span> <span m='1692060'>mapping</span> <span
  m='1692480'>to</span> <span m='1692600'>a</span> <span
  m='1692660'>stable</span> <span m='1693050'>digital</span> <span
  m='1693440'>filter.</span> <span m='1694840'>However,</span> <span
  m='1695560'>here's</span> <span m='1696080'>an</span> <span
  m='1696230'>even</span> <span m='1697070'>more</span> <span
  m='1697370'>stable</span> <span m='1698660'>analog</span> <span
  m='1699230'>filter.</span> <span m='1700430'>And</span> <span
  m='1700880'>if</span> <span m='1701090'>this</span> <span
  m='1701270'>pole</span> <span m='1701660'>is</span> <span
  m='1704150'>negative</span> <span m='1704660'>enough,</span> <span
  m='1705470'>then</span> <span m='1705650'>in</span> <span
  m='1705740'>fact,</span> <span m='1706220'>it</span> <span
  m='1706370'>falls</span> <span m='1706910'>outside</span> <span
  m='1707420'>the</span> <span m='1707540'>unit</span> <span
  m='1707810'>circle</span> <span m='1708470'>in</span> <span
  m='1708590'>the</span> <span m='1708680'>z-plane,</span> <span
  m='1709250'>and</span> <span m='1709370'>consequently</span> <span
  m='1710090'>the</span> <span m='1710210'>digital</span> <span
  m='1710570'>filter</span> <span m='1711260'>will</span> <span
  m='1711410'>be</span> <span m='1711590'>unstable.</span> </p><p><span
  m='1713750'>That</span> <span m='1714080'>incidentally</span> <span
  m='1714950'>is</span> <span m='1715520'>a</span> <span
  m='1715610'>well-known</span> <span m='1716120'>property</span> <span
  m='1716630'>in</span> <span m='1716720'>numerical</span> <span
  m='1717260'>analysis</span> <span m='1718070'>of</span> <span
  m='1718460'>forward</span> <span m='1718940'>differences--</span> <span
  m='1720200'>that</span> <span m='1720410'>is,</span> <span
  m='1720560'>the</span> <span m='1720680'>notion</span> <span
  m='1721310'>that</span> <span m='1721430'>forward</span> <span
  m='1721820'>differences</span> <span m='1722360'>are</span> <span
  m='1722480'>unstable.</span> <span m='1723630'>And</span> <span
  m='1724160'>this</span> <span m='1724370'>is</span> <span
  m='1724490'>one</span> <span m='1724700'>way</span> <span
  m='1724910'>of</span> <span m='1725000'>seeing</span> <span
  m='1725390'>that</span> <span m='1725750'>by</span> <span
  m='1726020'>interpreting</span> <span m='1726590'>it</span> <span
  m='1726680'>in</span> <span m='1726800'>terms</span> <span
  m='1727130'>of</span> <span m='1727220'>a</span> <span
  m='1727280'>mapping</span> <span m='1727760'>from</span> <span
  m='1727940'>the</span> <span m='1728070'>s-plane</span> <span
  m='1728510'>to</span> <span m='1728630'>the</span> <span
  m='1728720'>z-plane.</span> <span m='1730300'>We</span> <span
  m='1730420'>know</span> <span m='1730780'>incidentally</span> <span
  m='1732580'>that</span> <span m='1734140'>at</span> <span
  m='1734230'>least</span> <span m='1734440'>in</span> <span
  m='1734560'>an</span> <span m='1734650'>intuitive</span> <span
  m='1735160'>sense,</span> <span m='1735880'>it's</span> <span
  m='1736090'>reasonable</span> <span m='1736720'>to</span> <span
  m='1736930'>imagine</span> <span m='1737890'>that</span> <span
  m='1738910'>if</span> <span m='1739810'>we</span> <span
  m='1740710'>pick</span> <span m='1740980'>samples</span> <span
  m='1741970'>of</span> <span m='1742780'>a</span> <span
  m='1743230'>continuous</span> <span m='1743710'>time</span> <span
  m='1743980'>signal</span> <span m='1745030'>close</span> <span
  m='1745390'>enough</span> <span m='1745630'>together,</span> <span
  m='1746650'>that</span> <span m='1746800'>at</span> <span
  m='1746860'>least</span> <span m='1747160'>intuitively</span> <span
  m='1748120'>we</span> <span m='1748330'>ought</span> <span
  m='1748570'>to</span> <span m='1748690'>be</span> <span
  m='1748870'>able</span> <span m='1749110'>to</span> <span
  m='1749290'>approximate</span> <span m='1750940'>a</span> <span
  m='1751810'>derivative</span> <span m='1752920'>by</span> <span
  m='1753130'>a</span> <span m='1753190'>difference.</span> <span
  m='1754120'>And</span> <span m='1754240'>in</span> <span
  m='1754360'>fact,</span> <span m='1756070'>that</span> <span
  m='1756400'>fits</span> <span m='1756790'>in</span> <span
  m='1757150'>with</span> <span m='1757660'>the</span> <span
  m='1757840'>kinds</span> <span m='1758260'>of</span> <span
  m='1758350'>things</span> <span m='1758650'>that</span> <span
  m='1758770'>we've</span> <span m='1758950'>been</span> <span
  m='1759100'>seeing</span> <span m='1759430'>here</span> <span
  m='1759700'>in</span> <span m='1759790'>the</span> <span
  m='1759850'>following</span> <span m='1760300'>sense.</span> </p><p><span
  m='1761686'>If</span> <span m='1762080'>we</span> <span
  m='1762370'>very</span> <span m='1762820'>highly</span> <span
  m='1763300'>oversample</span> <span m='1764500'>the</span> <span
  m='1764590'>signal,</span> <span m='1765460'>much</span> <span
  m='1765730'>higher</span> <span m='1766060'>than</span> <span
  m='1766240'>the</span> <span m='1766330'>Nyquist</span> <span
  m='1766840'>rate,</span> <span m='1767800'>then</span> <span
  m='1767980'>in</span> <span m='1768070'>fact,</span> <span
  m='1768670'>the</span> <span m='1768790'>portion</span> <span
  m='1769480'>of</span> <span m='1769690'>the</span> <span
  m='1769780'>z-plane</span> <span m='1770560'>where</span> <span
  m='1770770'>the</span> <span m='1770890'>signal</span> <span
  m='1771250'>spectrum</span> <span m='1771790'>falls</span> <span
  m='1773140'>is</span> <span m='1773650'>the</span> <span
  m='1773800'>portion</span> <span m='1774280'>of</span> <span
  m='1774370'>the</span> <span m='1774460'>z-plane</span> <span
  m='1775870'>around</span> <span m='1776590'>in</span> <span
  m='1776740'>the</span> <span m='1776830'>vicinity</span> <span
  m='1777580'>of</span> <span m='1777700'>z</span> <span
  m='1777940'>equal</span> <span m='1778210'>to</span> <span
  m='1778360'>1.</span> <span m='1780010'>And</span> <span
  m='1780130'>you</span> <span m='1780250'>can</span> <span
  m='1780430'>see</span> <span m='1780820'>that</span> <span
  m='1781450'>in</span> <span m='1781600'>that</span> <span
  m='1781810'>case,</span> <span m='1782590'>that</span> <span
  m='1782830'>portion</span> <span m='1783610'>of</span> <span
  m='1783820'>the</span> <span m='1783940'>unit</span> <span
  m='1784210'>circle</span> <span m='1785230'>is</span> <span
  m='1785770'>pretty</span> <span m='1786040'>close</span> <span
  m='1786970'>to</span> <span m='1787480'>this</span> <span
  m='1787720'>line</span> <span m='1788200'>which</span> <span
  m='1788410'>was</span> <span m='1788560'>the</span> <span
  m='1788650'>mapping</span> <span m='1789070'>from</span> <span
  m='1789220'>the</span> <span m='1789520'>j</span> <span
  m='1789620'>omega</span> <span m='1789910'>axis</span> <span
  m='1790960'>into</span> <span m='1791290'>the</span> <span
  m='1792130'>z-plane.</span> <span m='1793420'>And</span> <span
  m='1793510'>so</span> <span m='1793690'>consequently,</span> <span
  m='1794680'>if</span> <span m='1794830'>we</span> <span
  m='1794980'>oversample</span> <span m='1796090'>rather</span> <span
  m='1796750'>extensively,</span> <span m='1798160'>then</span> <span
  m='1799060'>we</span> <span m='1799270'>can,</span> <span
  m='1799640'>in</span> <span m='1799740'>fact,</span> <span
  m='1800230'>map,</span> <span m='1800740'>more</span> <span
  m='1801070'>or</span> <span m='1801100'>less,</span> <span
  m='1801610'>our</span> <span m='1801820'>analog</span> <span
  m='1802300'>filter</span> <span m='1802960'>to</span> <span
  m='1803110'>a</span> <span m='1803170'>digital</span> <span
  m='1803560'>filter.</span> <span m='1804370'>But</span> <span
  m='1804580'>in</span> <span m='1804700'>fact,</span> <span
  m='1806140'>in</span> <span m='1806260'>the</span> <span
  m='1806350'>more</span> <span m='1806530'>usual</span> <span
  m='1807040'>case,</span> <span m='1807900'>the</span> <span
  m='1808510'>digital</span> <span m='1808900'>signal</span> <span
  m='1809260'>spectrum</span> <span m='1809830'>occupies</span> <span
  m='1811030'>the</span> <span m='1811150'>entire</span> <span
  m='1811570'>unit</span> <span m='1811930'>circle.</span> <span
  m='1812860'>And</span> <span m='1813010'>clearly</span> <span
  m='1813610'>away</span> <span m='1813940'>from</span> <span
  m='1814150'>the</span> <span m='1814240'>regions</span> <span
  m='1814720'>equals</span> <span m='1815170'>1,</span> <span
  m='1815570'>the</span> <span m='1815970'>unit</span> <span
  m='1816250'>circle</span> <span m='1816670'>deviates</span> <span
  m='1817270'>rather</span> <span m='1817600'>dramatically</span> <span
  m='1818650'>from</span> <span m='1818830'>this</span> <span
  m='1818980'>vertical</span> <span m='1819400'>line.</span> </p><p><span
  m='1820960'>All</span> <span m='1821050'>right,</span> <span
  m='1821210'>so</span> <span m='1821350'>this</span> <span
  m='1821560'>is</span> <span m='1821680'>a</span> <span
  m='1821770'>method</span> <span m='1822130'>then</span> <span
  m='1823090'>of</span> <span m='1824380'>filter</span> <span
  m='1824770'>design,</span> <span m='1826030'>which</span> <span
  m='1827560'>didn't</span> <span m='1827860'>satisfy</span> <span
  m='1828520'>either</span> <span m='1828790'>one</span> <span
  m='1829000'>of</span> <span m='1829120'>our</span> <span
  m='1829780'>initial</span> <span m='1830620'>guidelines.</span> <span
  m='1831370'>Namely,</span> <span m='1832030'>it</span> <span
  m='1832150'>didn't</span> <span m='1832390'>map</span> <span
  m='1832630'>the</span> <span m='1832750'>j</span> <span
  m='1832930'>omega</span> <span m='1833290'>axis</span> <span
  m='1834460'>to</span> <span m='1834580'>the</span> <span
  m='1834700'>unit</span> <span m='1834970'>circle.</span> <span
  m='1835510'>And</span> <span m='1836110'>also,</span> <span
  m='1836680'>it</span> <span m='1836800'>didn't</span> <span
  m='1837070'>map</span> <span m='1837310'>a</span> <span
  m='1839080'>stable</span> <span m='1839500'>analog</span> <span
  m='1839980'>filter</span> <span m='1840520'>to</span> <span
  m='1840700'>a</span> <span m='1840760'>stable</span> <span
  m='1841150'>digital</span> <span m='1841510'>filter.</span> </p><p><span
  m='1843560'>Well,</span> <span m='1843820'>let's</span> <span
  m='1844090'>go</span> <span m='1844300'>on</span> <span m='1844990'>to</span>
  <span m='1845470'>a</span> <span m='1845530'>second</span> <span
  m='1845920'>method,</span> <span m='1846550'>which</span> <span
  m='1847660'>is</span> <span m='1848560'>better</span> <span
  m='1849010'>in</span> <span m='1849190'>both</span> <span
  m='1849490'>of</span> <span m='1849580'>those</span> <span
  m='1849850'>respects.</span> <span m='1851020'>And</span> <span
  m='1851620'>this</span> <span m='1851860'>is</span> <span m='1851980'>a</span>
  <span m='1852040'>method</span> <span m='1852790'>that</span> <span
  m='1853150'>is</span> <span m='1853570'>commonly</span> <span
  m='1854080'>referred</span> <span m='1854500'>to</span> <span
  m='1855670'>as</span> <span m='1855880'>the</span> <span
  m='1856000'>method</span> <span m='1856540'>of</span> <span
  m='1856900'>impulse</span> <span m='1857380'>invariance.</span> <span
  m='1859000'>And</span> <span m='1859150'>again,</span> <span
  m='1859660'>it's</span> <span m='1860650'>a</span> <span
  m='1861310'>filter</span> <span m='1861670'>design</span> <span
  m='1862120'>method,</span> <span m='1863020'>which</span> <span
  m='1863800'>intuitively</span> <span m='1864880'>is</span> <span
  m='1865960'>very</span> <span m='1866230'>reasonable.</span> <span
  m='1867700'>The</span> <span m='1867820'>basic</span> <span
  m='1868300'>idea</span> <span m='1869170'>of</span> <span
  m='1869320'>impulse</span> <span m='1869800'>invariance</span> <span
  m='1871240'>is</span> <span m='1872080'>to</span> <span
  m='1872470'>convert</span> <span m='1874170'>an</span> <span
  m='1874570'>analog</span> <span m='1875530'>filter</span> <span
  m='1876700'>to</span> <span m='1876880'>a</span> <span
  m='1876940'>digital</span> <span m='1877360'>filter,</span> <span
  m='1878570'>simply</span> <span m='1879160'>by</span> <span
  m='1879370'>choosing</span> <span m='1879850'>the</span> <span
  m='1879940'>unit</span> <span m='1880210'>sample</span> <span
  m='1880660'>response</span> <span m='1881290'>of</span> <span
  m='1881410'>the</span> <span m='1881530'>digital</span> <span
  m='1881920'>filter</span> <span m='1882910'>to</span> <span
  m='1883030'>be</span> <span m='1883390'>equally</span> <span
  m='1883810'>spaced</span> <span m='1884350'>samples</span> <span
  m='1885250'>of</span> <span m='1885850'>the</span> <span
  m='1886090'>impulse</span> <span m='1886540'>response</span> <span
  m='1887200'>of</span> <span m='1887350'>the</span> <span
  m='1887470'>analog</span> <span m='1887920'>filter.</span> <span
  m='1888950'>So</span> <span m='1889030'>the</span> <span
  m='1889150'>unit</span> <span m='1889390'>sample</span> <span
  m='1889780'>response</span> <span m='1890440'>h</span> <span
  m='1890640'>of</span> <span m='1890840'>n</span> <span m='1892140'>is</span>
  <span m='1892330'>chosen</span> <span m='1893470'>to</span> <span
  m='1893620'>be</span> <span m='1894130'>equally</span> <span
  m='1894550'>spaced</span> <span m='1894910'>samples,</span> <span
  m='1895480'>samples</span> <span m='1895900'>spaced</span> <span
  m='1896260'>by</span> <span m='1896920'>T,</span> <span
  m='1897940'>equally</span> <span m='1898360'>spaced</span> <span
  m='1898690'>samples</span> <span m='1899440'>of</span> <span
  m='1899800'>the</span> <span m='1899950'>analog</span> <span
  m='1900550'>or</span> <span m='1900880'>continuous</span> <span
  m='1901480'>time</span> <span m='1902260'>filter.</span> </p><p><span
  m='1904720'>Well,</span> <span m='1905610'>in</span> <span
  m='1906060'>at</span> <span m='1906240'>least</span> <span
  m='1907140'>one</span> <span m='1907560'>sense,</span> <span
  m='1908890'>we</span> <span m='1908970'>can</span> <span
  m='1909150'>see</span> <span m='1909450'>that</span> <span
  m='1910860'>this</span> <span m='1911280'>certainly</span> <span
  m='1912180'>leads</span> <span m='1912690'>to</span> <span
  m='1912900'>a</span> <span m='1912960'>good</span> <span
  m='1913470'>filter.</span> <span m='1914580'>And</span> <span
  m='1914730'>that</span> <span m='1914940'>is,</span> <span
  m='1915570'>if</span> <span m='1916080'>we</span> <span m='1916260'>had</span>
  <span m='1917040'>a</span> <span m='1917550'>continuous</span> <span
  m='1918180'>time</span> <span m='1918660'>analog</span> <span
  m='1919200'>filter</span> <span m='1920370'>that</span> <span
  m='1920520'>had</span> <span m='1921090'>good</span> <span
  m='1921420'>impulse</span> <span m='1921990'>response</span> <span
  m='1922500'>characteristics,</span> <span m='1924180'>then</span> <span
  m='1925290'>those</span> <span m='1926280'>good</span> <span
  m='1926580'>impulse</span> <span m='1927030'>response</span> <span
  m='1927480'>characteristics</span> <span m='1928350'>would</span> <span
  m='1928470'>be</span> <span m='1928590'>carried</span> <span
  m='1928980'>over</span> <span m='1929670'>to</span> <span
  m='1929790'>the</span> <span m='1929910'>digital</span> <span
  m='1930270'>filter</span> <span m='1930990'>unit</span> <span
  m='1931260'>sample</span> <span m='1931620'>response.</span> <span
  m='1932200'>For</span> <span m='1932250'>example,</span> <span
  m='1933460'>if</span> <span m='1933810'>we</span> <span
  m='1933960'>were</span> <span m='1934110'>interested</span> <span
  m='1934560'>in</span> <span m='1934680'>a</span> <span
  m='1934740'>filter</span> <span m='1935970'>with</span> <span
  m='1936270'>very</span> <span m='1936510'>low</span> <span
  m='1936750'>ringing</span> <span m='1937380'>or</span> <span
  m='1937590'>very</span> <span m='1937860'>short</span> <span
  m='1938280'>impulse</span> <span m='1938790'>response,</span> <span
  m='1939900'>then</span> <span m='1940080'>if</span> <span
  m='1940200'>we</span> <span m='1940320'>had</span> <span m='1940470'>an</span>
  <span m='1940590'>analog</span> <span m='1941070'>filter</span> <span
  m='1941430'>with</span> <span m='1941550'>those</span> <span
  m='1941790'>characteristics,</span> <span m='1943170'>then</span> <span
  m='1943560'>the</span> <span m='1943680'>digital</span> <span
  m='1944040'>filter</span> <span m='1944670'>would</span> <span
  m='1944850'>likewise</span> <span m='1945570'>have</span> <span
  m='1946080'>good</span> <span m='1946320'>impulse</span> <span
  m='1946800'>response</span> <span m='1947280'>characteristics.</span>
  </p><p><span m='1949600'>However</span> <span m='1949920'>we've</span> <span
  m='1950100'>been</span> <span m='1950220'>phrasing</span> <span
  m='1950640'>most</span> <span m='1950940'>of</span> <span
  m='1951030'>our</span> <span m='1951150'>discussion</span> <span
  m='1951930'>in</span> <span m='1952110'>terms</span> <span
  m='1952530'>of</span> <span m='1952590'>frequency</span> <span
  m='1953100'>response</span> <span m='1953610'>characteristics,</span> <span
  m='1955230'>we</span> <span m='1955380'>know</span> <span
  m='1955890'>from</span> <span m='1956100'>the</span> <span
  m='1956190'>discussion</span> <span m='1956910'>of</span> <span
  m='1957060'>sampling</span> <span m='1957870'>that</span> <span
  m='1958110'>we</span> <span m='1958260'>had</span> <span m='1958440'>a</span>
  <span m='1958500'>number</span> <span m='1958800'>of</span> <span
  m='1958890'>lectures</span> <span m='1959370'>ago</span> <span
  m='1960420'>that</span> <span m='1960930'>periodic</span> <span
  m='1961530'>sampling</span> <span m='1962040'>of</span> <span
  m='1962130'>this</span> <span m='1962370'>type</span> <span
  m='1963720'>results</span> <span m='1964440'>in</span> <span
  m='1964980'>a</span> <span m='1965610'>frequency</span> <span
  m='1966720'>response</span> <span m='1968040'>for</span> <span
  m='1969060'>the</span> <span m='1969930'>digital</span> <span
  m='1970470'>system,</span> <span m='1972160'>which</span> <span
  m='1972570'>is</span> <span m='1973050'>basically</span> <span
  m='1973860'>an</span> <span m='1974010'>aliased</span> <span
  m='1974460'>version</span> <span m='1975150'>of</span> <span
  m='1975780'>the</span> <span m='1975900'>frequency</span> <span
  m='1976440'>response</span> <span m='1977160'>for</span> <span
  m='1977310'>the</span> <span m='1977460'>analog</span> <span
  m='1977940'>system.</span> <span m='1978900'>That</span> <span
  m='1979110'>is,</span> <span m='1979770'>the</span> <span
  m='1979860'>digital</span> <span m='1980250'>frequency</span> <span
  m='1980820'>response</span> <span m='1981840'>is</span> <span
  m='1981990'>given</span> <span m='1982380'>by</span> <span
  m='1983880'>the</span> <span m='1984150'>sum</span> <span
  m='1984510'>that</span> <span m='1984630'>I've</span> <span
  m='1984810'>indicated</span> <span m='1985380'>here,</span> <span
  m='1986380'>which</span> <span m='1986520'>consists</span> <span
  m='1987180'>of</span> <span m='1987960'>scaled</span> <span
  m='1988560'>replicas</span> <span m='1989640'>of</span> <span
  m='1989850'>the</span> <span m='1990270'>Fourier</span> <span
  m='1990690'>transform</span> <span m='1991740'>of</span> <span
  m='1992100'>the</span> <span m='1992280'>analog</span> <span
  m='1995790'>filter,</span> <span m='1997290'>repeated</span> <span
  m='1997770'>over</span> <span m='1998040'>and</span> <span
  m='1998130'>over</span> <span m='1998460'>again</span> <span
  m='1999510'>with</span> <span m='1999920'>a</span> <span
  m='2000010'>spacing</span> <span m='2000890'>in</span> <span
  m='2001550'>little</span> <span m='2001820'>omega</span> <span
  m='2002990'>of</span> <span m='2003440'>2</span> <span m='2003620'>pi.</span>
  <span m='2004760'>Well,</span> <span m='2005270'>let's</span> <span
  m='2005780'>take</span> <span m='2006020'>a</span> <span
  m='2006080'>look</span> <span m='2006290'>at</span> <span
  m='2006380'>that</span> <span m='2006770'>in</span> <span m='2007280'>a</span>
  <span m='2007310'>little</span> <span m='2007520'>more</span> <span
  m='2007730'>detail.</span> </p><p></p><p><span m='2013470'>Here</span> <span
  m='2013920'>we</span> <span m='2014130'>have</span> <span
  m='2014700'>the</span> <span m='2016620'>analog</span> <span
  m='2018630'>frequency</span> <span m='2019200'>response.</span> <span
  m='2019830'>And</span> <span m='2019920'>let's</span> <span
  m='2020130'>say</span> <span m='2020880'>that</span> <span
  m='2021900'>we're</span> <span m='2022290'>considering</span> <span
  m='2022860'>this</span> <span m='2023100'>for</span> <span
  m='2023220'>the</span> <span m='2023310'>case</span> <span
  m='2023610'>of</span> <span m='2023700'>a</span> <span
  m='2023760'>low-pass</span> <span m='2024300'>filter,</span> <span
  m='2024750'>which</span> <span m='2025020'>is</span> <span
  m='2025140'>what</span> <span m='2025350'>we've</span> <span
  m='2025530'>tended</span> <span m='2025980'>to</span> <span
  m='2026100'>focus</span> <span m='2026520'>on</span> <span
  m='2026730'>in</span> <span m='2026820'>this</span> <span
  m='2027000'>lecture.</span> <span m='2028140'>So</span> <span
  m='2028320'>that</span> <span m='2028590'>if</span> <span
  m='2028860'>we</span> <span m='2029010'>had</span> <span m='2029430'>an</span>
  <span m='2029580'>analog</span> <span m='2030060'>low-pass</span> <span
  m='2030630'>filter,</span> <span m='2031560'>cutoff</span> <span
  m='2031920'>frequency</span> <span m='2033420'>between</span> <span
  m='2033960'>minus</span> <span m='2034380'>omega</span> <span
  m='2034740'>sub</span> <span m='2034910'>a</span> <span m='2035080'>and</span>
  <span m='2035190'>plus</span> <span m='2035490'>omega</span> <span
  m='2035700'>sub</span> <span m='2035910'>a,</span> <span
  m='2038130'>then</span> <span m='2039090'>in</span> <span
  m='2039470'>forming</span> <span m='2040350'>the</span> <span
  m='2040710'>digital</span> <span m='2041160'>filter</span> <span
  m='2042570'>frequency</span> <span m='2043140'>response,</span> <span
  m='2044400'>we</span> <span m='2044520'>first</span> <span
  m='2044940'>want</span> <span m='2045150'>to</span> <span
  m='2045240'>form</span> <span m='2045950'>h</span> <span
  m='2046220'>sub</span> <span m='2046510'>a</span> <span m='2046800'>of</span>
  <span m='2046990'>j</span> <span m='2047280'>omega</span> <span
  m='2048060'>divided</span> <span m='2048540'>by</span> <span
  m='2048780'>T,</span> <span m='2050520'>and</span> <span
  m='2050639'>then</span> <span m='2051030'>shift</span> <span
  m='2051449'>that</span> <span m='2052080'>in</span> <span
  m='2052679'>omega</span> <span m='2053460'>by</span> <span
  m='2054000'>integer</span> <span m='2054389'>multiples</span> <span
  m='2054989'>of</span> <span m='2055080'>2</span> <span m='2055320'>pi</span>
  <span m='2056219'>and</span> <span m='2056400'>add</span> <span
  m='2056639'>up</span> <span m='2056790'>those</span> <span
  m='2057000'>results.</span> </p><p><span m='2058210'>So</span> <span
  m='2058679'>the</span> <span m='2058800'>first</span> <span
  m='2059070'>step</span> <span m='2059489'>is</span> <span
  m='2059699'>the</span> <span m='2059790'>scaling,</span> <span
  m='2060719'>basically</span> <span m='2061290'>replacing</span> <span
  m='2062310'>Omega</span> <span m='2063449'>by</span> <span
  m='2064350'>omega</span> <span m='2064770'>divided</span> <span
  m='2065219'>by</span> <span m='2065940'>T,</span> <span m='2067320'>in</span>
  <span m='2067380'>which</span> <span m='2067650'>case</span> <span
  m='2068909'>plotted</span> <span m='2069449'>as</span> <span
  m='2069630'>a</span> <span m='2069690'>function</span> <span
  m='2070350'>of</span> <span m='2070830'>omega,</span> <span
  m='2072120'>the</span> <span m='2072210'>cutoff</span> <span
  m='2072659'>frequency</span> <span m='2073500'>is</span> <span
  m='2073710'>then</span> <span m='2074130'>omega</span> <span
  m='2074710'>sub</span> <span m='2074880'>a</span> <span m='2075870'>T</span>
  <span m='2076350'>and</span> <span m='2076500'>minus</span> <span
  m='2076889'>omega</span> <span m='2077280'>sub</span> <span
  m='2077370'>a</span> <span m='2078060'>T,</span> <span m='2078870'>so</span>
  <span m='2079020'>that</span> <span m='2079620'>this</span> <span
  m='2079860'>step</span> <span m='2081659'>results</span> <span
  m='2082230'>in</span> <span m='2082620'>a</span> <span
  m='2082679'>linear</span> <span m='2083100'>scaling</span> <span
  m='2084540'>of</span> <span m='2085139'>the</span> <span
  m='2085260'>frequency</span> <span m='2085889'>axis</span> <span
  m='2086969'>so</span> <span m='2087239'>that</span> <span
  m='2088139'>Omega</span> <span m='2088739'>is</span> <span
  m='2088949'>replaced</span> <span m='2089400'>by</span> <span
  m='2089820'>omega</span> <span m='2090239'>divided</span> <span
  m='2090659'>by</span> <span m='2091215'>T.</span> <span m='2093179'>The</span>
  <span m='2093270'>second</span> <span m='2094020'>step</span> <span
  m='2094469'>then</span> <span m='2094860'>is</span> <span
  m='2095639'>to</span> <span m='2095969'>add</span> <span
  m='2096750'>together</span> <span m='2097800'>replicas</span> <span
  m='2098760'>of</span> <span m='2098970'>this</span> <span
  m='2099540'>analog</span> <span m='2100230'>frequency</span> <span
  m='2100800'>response</span> <span m='2102000'>separated</span> <span
  m='2102930'>in</span> <span m='2103410'>omega</span> <span
  m='2104400'>by</span> <span m='2104700'>integer</span> <span
  m='2105090'>multiples</span> <span m='2105630'>of</span> <span
  m='2105750'>2</span> <span m='2105960'>pi.</span> <span m='2106620'>And</span>
  <span m='2106890'>that's</span> <span m='2107100'>what</span> <span
  m='2107190'>I've</span> <span m='2107340'>indicated</span> <span
  m='2107910'>here.</span> <span m='2109260'>Of</span> <span
  m='2109410'>course,</span> <span m='2109710'>this</span> <span
  m='2109860'>periodically</span> <span m='2110580'>repeats</span> <span
  m='2111000'>over</span> <span m='2111270'>and</span> <span
  m='2111360'>over</span> <span m='2111660'>again,</span> <span
  m='2112470'>but</span> <span m='2112800'>I've</span> <span
  m='2112980'>sketched</span> <span m='2113400'>it</span> <span
  m='2113490'>just</span> <span m='2113850'>from</span> <span
  m='2114030'>minus</span> <span m='2114450'>2</span> <span
  m='2114660'>pi</span> <span m='2115530'>to</span> <span
  m='2115650'>plus</span> <span m='2115950'>2</span> <span
  m='2116160'>pi.</span> <span m='2117210'>We</span> <span
  m='2117360'>have</span> <span m='2117540'>the</span> <span
  m='2117630'>factor</span> <span m='2118110'>1</span> <span
  m='2118350'>over</span> <span m='2119160'>T</span> <span
  m='2119490'>out</span> <span m='2119670'>in</span> <span
  m='2119760'>front</span> <span m='2120180'>for</span> <span
  m='2120330'>the</span> <span m='2120480'>amplitude.</span> </p><p><span
  m='2122040'>But</span> <span m='2122490'>an</span> <span
  m='2122610'>important</span> <span m='2123660'>aspect</span> <span
  m='2124350'>of</span> <span m='2124530'>this</span> <span
  m='2125430'>is</span> <span m='2125640'>that</span> <span
  m='2126450'>we</span> <span m='2126630'>have</span> <span
  m='2127170'>in</span> <span m='2127320'>going</span> <span
  m='2127650'>from</span> <span m='2127860'>the</span> <span
  m='2127980'>analog</span> <span m='2128490'>frequency</span> <span
  m='2129000'>variable</span> <span m='2129600'>to</span> <span
  m='2129750'>the</span> <span m='2129870'>digital</span> <span
  m='2130230'>frequency</span> <span m='2130800'>variable,</span> <span
  m='2132100'>a</span> <span m='2132360'>linear</span> <span
  m='2132870'>scaling</span> <span m='2133770'>in</span> <span
  m='2133950'>the</span> <span m='2134040'>frequency</span> <span
  m='2134610'>axis.</span> <span m='2136080'>That</span> <span
  m='2136260'>doesn't</span> <span m='2136560'>show</span> <span
  m='2136800'>up</span> <span m='2136920'>particularly</span> <span
  m='2137760'>for</span> <span m='2137940'>a</span> <span
  m='2138000'>piecewise</span> <span m='2138570'>constant</span> <span
  m='2139110'>frequency</span> <span m='2139590'>characteristic</span> <span
  m='2140370'>as</span> <span m='2140520'>I</span> <span m='2140640'>have</span>
  <span m='2140940'>here.</span> <span m='2141750'>But</span> <span
  m='2141930'>generally,</span> <span m='2142740'>if</span> <span
  m='2142920'>I</span> <span m='2143040'>had</span> <span
  m='2143280'>some</span> <span m='2143460'>complicated</span> <span
  m='2144240'>shape,</span> <span m='2145800'>then</span> <span
  m='2146580'>when</span> <span m='2146940'>I</span> <span
  m='2147060'>convert</span> <span m='2147540'>to</span> <span
  m='2147810'>h</span> <span m='2148140'>sub</span> <span m='2148290'>a</span>
  <span m='2148710'>of</span> <span m='2148920'>j</span> <span
  m='2149160'>omega</span> <span m='2149550'>over</span> <span
  m='2150490'>T,</span> <span m='2151320'>that</span> <span
  m='2151560'>basic</span> <span m='2152010'>shape</span> <span
  m='2152580'>will</span> <span m='2152730'>be</span> <span
  m='2152910'>preserved.</span> <span m='2154120'>And</span> <span
  m='2155100'>it</span> <span m='2155280'>will</span> <span
  m='2155550'>only</span> <span m='2156210'>be</span> <span
  m='2156390'>distorted</span> <span m='2157050'>by</span> <span
  m='2157530'>a</span> <span m='2157770'>linear</span> <span
  m='2158400'>scaling</span> <span m='2158970'>in</span> <span
  m='2159060'>the</span> <span m='2159120'>frequency</span> <span
  m='2159690'>axis.</span> <span m='2160530'>And</span> <span
  m='2160680'>that</span> <span m='2160980'>is</span> <span
  m='2161400'>an</span> <span m='2161520'>important</span> <span
  m='2162150'>advantage</span> <span m='2163020'>of</span> <span
  m='2163680'>the</span> <span m='2163980'>technique</span> <span
  m='2164640'>of</span> <span m='2164910'>impulse</span> <span
  m='2165390'>invariance.</span> </p><p><span m='2167820'>Now</span> <span
  m='2168450'>there</span> <span m='2168630'>are</span> <span
  m='2168660'>some</span> <span m='2168870'>problems,</span> <span
  m='2170080'>one</span> <span m='2170280'>in</span> <span
  m='2170370'>particular.</span> <span m='2171120'>And</span> <span
  m='2171870'>this</span> <span m='2172080'>is</span> <span
  m='2172200'>the</span> <span m='2172290'>major</span> <span
  m='2172680'>problem.</span> <span m='2173810'>And</span> <span
  m='2173910'>that</span> <span m='2174120'>is</span> <span
  m='2174630'>that</span> <span m='2174930'>as</span> <span
  m='2175230'>I've</span> <span m='2175770'>drawn</span> <span
  m='2176100'>this</span> <span m='2176340'>example,</span> <span
  m='2177750'>we've</span> <span m='2177990'>considered</span> <span
  m='2178710'>an</span> <span m='2179460'>analog</span> <span
  m='2179970'>filter</span> <span m='2180390'>whose</span> <span
  m='2180600'>frequency</span> <span m='2181110'>response</span> <span
  m='2181800'>is</span> <span m='2181980'>strictly</span> <span
  m='2182490'>bandlimited.</span> <span m='2183990'>And</span> <span
  m='2184140'>so</span> <span m='2184350'>of</span> <span
  m='2184470'>course</span> <span m='2185100'>there</span> <span
  m='2185430'>is</span> <span m='2185580'>no</span> <span
  m='2185790'>aliasing</span> <span m='2186750'>that</span> <span
  m='2186900'>results.</span> </p><p><span m='2188070'>But</span> <span
  m='2188400'>more</span> <span m='2188670'>generally,</span> <span
  m='2189600'>the</span> <span m='2189720'>kind</span> <span
  m='2189990'>of</span> <span m='2190050'>frequency</span> <span
  m='2190590'>characteristic</span> <span m='2192180'>that</span> <span
  m='2192570'>we</span> <span m='2192750'>would</span> <span
  m='2192930'>have</span> <span m='2196020'>would</span> <span
  m='2196170'>look</span> <span m='2198360'>perhaps</span> <span
  m='2199320'>like</span> <span m='2199650'>this,</span> <span
  m='2200580'>as</span> <span m='2201450'>an</span> <span
  m='2201570'>approximation,</span> <span m='2202620'>admittedly</span> <span
  m='2203160'>a</span> <span m='2203220'>somewhat</span> <span
  m='2203550'>crude</span> <span m='2203820'>approximation,</span> <span
  m='2204780'>to</span> <span m='2204930'>this</span> <span
  m='2205140'>ideal</span> <span m='2205520'>low-pass</span> <span
  m='2206070'>filter.</span> <span m='2207390'>In</span> <span
  m='2207480'>which</span> <span m='2207720'>case,</span> <span
  m='2208420'>as</span> <span m='2208920'>we</span> <span m='2209160'>add</span>
  <span m='2209400'>up</span> <span m='2210090'>the</span> <span
  m='2210390'>replicas</span> <span m='2211440'>of</span> <span
  m='2212040'>the</span> <span m='2212160'>scaled</span> <span
  m='2213000'>frequency</span> <span m='2213540'>response,</span> <span
  m='2214950'>then</span> <span m='2215580'>we</span> <span
  m='2215970'>in</span> <span m='2216090'>general</span> <span
  m='2216690'>will</span> <span m='2216930'>have</span> <span
  m='2217260'>interference</span> <span m='2218070'>or</span> <span
  m='2218280'>aliasing</span> <span m='2219450'>between</span> <span
  m='2219900'>different</span> <span m='2220230'>terms</span> <span
  m='2220590'>in</span> <span m='2220710'>this</span> <span
  m='2220860'>sum.</span> <span m='2222090'>So</span> <span
  m='2222270'>that</span> <span m='2222450'>in</span> <span
  m='2222570'>that</span> <span m='2222750'>case,</span> <span
  m='2223650'>while</span> <span m='2224040'>we</span> <span
  m='2224220'>start</span> <span m='2224730'>with</span> <span
  m='2225090'>an</span> <span m='2225210'>analog</span> <span
  m='2225660'>frequency</span> <span m='2226170'>characteristic</span> <span
  m='2227280'>that's</span> <span m='2227550'>desirable,</span> <span
  m='2229080'>the</span> <span m='2229290'>resulting</span> <span
  m='2229860'>digital</span> <span m='2230250'>frequency</span> <span
  m='2230790'>characteristic</span> <span m='2232170'>will</span> <span
  m='2232530'>be</span> <span m='2232740'>distorted</span> <span
  m='2233370'>somewhat</span> <span m='2234960'>because</span> <span
  m='2235650'>of</span> <span m='2236310'>the</span> <span
  m='2236490'>aliasing</span> <span m='2237450'>that</span> <span
  m='2237600'>results</span> <span m='2238590'>due</span> <span
  m='2238920'>to</span> <span m='2239340'>the</span> <span
  m='2239790'>separate</span> <span m='2240240'>terms</span> <span
  m='2240660'>that</span> <span m='2240780'>are</span> <span
  m='2240900'>added</span> <span m='2241140'>together</span> <span
  m='2241590'>in</span> <span m='2241680'>this</span> <span
  m='2241820'>sum.</span> <span m='2242830'>And</span> <span
  m='2243480'>one</span> <span m='2243690'>of</span> <span
  m='2244020'>the</span> <span m='2244560'>important</span> <span
  m='2245280'>aspects</span> <span m='2246060'>of</span> <span
  m='2246420'>implementing</span> <span m='2247050'>an</span> <span
  m='2248400'>impulse</span> <span m='2248790'>invariant</span> <span
  m='2249220'>filter</span> <span m='2249690'>design,</span> <span
  m='2250440'>then,</span> <span m='2250890'>is</span> <span
  m='2251700'>to</span> <span m='2251970'>in</span> <span
  m='2252120'>some</span> <span m='2252450'>way</span> <span
  m='2253290'>account</span> <span m='2253710'>for</span> <span
  m='2254220'>and</span> <span m='2254370'>hopefully</span> <span
  m='2254760'>minimize</span> <span m='2255390'>the</span> <span
  m='2255510'>effect</span> <span m='2255840'>of</span> <span
  m='2255900'>this</span> <span m='2256110'>aliasing.</span> </p><p><span
  m='2257640'>All</span> <span m='2257730'>right,</span> <span
  m='2257970'>so</span> <span m='2260240'>with</span> <span
  m='2260650'>the</span> <span m='2260760'>impulse</span> <span
  m='2261180'>invariant</span> <span m='2261780'>method,</span> <span
  m='2262770'>one</span> <span m='2262980'>of</span> <span
  m='2263400'>the</span> <span m='2264060'>important</span> <span
  m='2265440'>advantages</span> <span m='2266130'>of</span> <span
  m='2266220'>impulse</span> <span m='2266670'>invariance</span> <span
  m='2268680'>is</span> <span m='2269370'>the</span> <span
  m='2269490'>fact</span> <span m='2270060'>that</span> <span
  m='2270420'>it</span> <span m='2270570'>tends</span> <span
  m='2270930'>to</span> <span m='2271050'>preserve</span> <span
  m='2271890'>good</span> <span m='2272640'>time</span> <span
  m='2272940'>domain</span> <span m='2273360'>characteristics.</span> <span
  m='2274470'>That</span> <span m='2274620'>is,</span> <span
  m='2274740'>the</span> <span m='2274860'>impulse</span> <span
  m='2275280'>response</span> <span m='2276300'>characteristics</span> <span
  m='2277080'>were</span> <span m='2277230'>preserved.</span> <span
  m='2279100'>And</span> <span m='2279430'>also,</span> <span
  m='2280360'>it</span> <span m='2282370'>provides</span> <span
  m='2283420'>a</span> <span m='2284830'>linear</span> <span
  m='2285550'>scaling</span> <span m='2286570'>from</span> <span
  m='2287260'>analog</span> <span m='2287740'>frequency</span> <span
  m='2288280'>to</span> <span m='2288400'>digital</span> <span
  m='2288820'>frequency</span> <span m='2289960'>so</span> <span
  m='2290140'>that</span> <span m='2290410'>if</span> <span
  m='2290740'>we</span> <span m='2290950'>had</span> <span m='2291400'>an</span>
  <span m='2291550'>analog</span> <span m='2292120'>filter</span> <span
  m='2293140'>with</span> <span m='2293290'>a</span> <span
  m='2293320'>very</span> <span m='2293560'>complicated</span> <span
  m='2294790'>frequency</span> <span m='2295420'>response,</span> <span
  m='2296740'>then</span> <span m='2297130'>we</span> <span
  m='2297310'>could</span> <span m='2297430'>be</span> <span
  m='2297580'>assured</span> <span m='2298330'>that</span> <span
  m='2298780'>the</span> <span m='2298900'>corresponding</span> <span
  m='2299530'>digital</span> <span m='2299920'>filter</span> <span
  m='2300370'>except</span> <span m='2300850'>for</span> <span
  m='2301060'>aliasing</span> <span m='2302320'>would</span> <span
  m='2302770'>have</span> <span m='2303280'>that</span> <span
  m='2303490'>same</span> <span m='2304270'>shape,</span> <span
  m='2305240'>but</span> <span m='2305440'>only</span> <span
  m='2305830'>with</span> <span m='2306310'>a</span> <span
  m='2306550'>linear</span> <span m='2306880'>scaling</span> <span
  m='2307390'>of</span> <span m='2307450'>the</span> <span
  m='2307570'>frequency</span> <span m='2308110'>axis.</span> </p><p><span
  m='2309600'>It</span> <span m='2309670'>should</span> <span
  m='2309820'>be</span> <span m='2309940'>pointed</span> <span
  m='2310300'>out</span> <span m='2310480'>incidentally</span> <span
  m='2311710'>that</span> <span m='2312970'>impulse</span> <span
  m='2313480'>invariance</span> <span m='2314620'>doesn't</span> <span
  m='2315070'>imply</span> <span m='2315840'>step</span> <span
  m='2316200'>invariance,</span> <span m='2316840'>and</span> <span
  m='2316930'>you'll</span> <span m='2317050'>see</span> <span
  m='2317290'>this</span> <span m='2317710'>in</span> <span
  m='2318010'>the</span> <span m='2318100'>problems</span> <span
  m='2319030'>that</span> <span m='2319240'>you</span> <span
  m='2319360'>work</span> <span m='2319600'>through</span> <span
  m='2319780'>the</span> <span m='2319870'>study</span> <span
  m='2320200'>guide.</span> <span m='2321190'>Impulse</span> <span
  m='2321610'>invariance</span> <span m='2322060'>does</span> <span
  m='2322240'>not</span> <span m='2322510'>imply</span> <span
  m='2322900'>step</span> <span m='2323220'>invariance</span> <span
  m='2324370'>so</span> <span m='2324580'>that</span> <span
  m='2324820'>in</span> <span m='2324940'>fact,</span> <span
  m='2325300'>if</span> <span m='2325450'>it</span> <span m='2325570'>was</span>
  <span m='2325990'>the</span> <span m='2326350'>step</span> <span
  m='2326770'>response</span> <span m='2327310'>characteristics</span> <span
  m='2328360'>that</span> <span m='2328510'>we</span> <span
  m='2328630'>wanted</span> <span m='2328900'>to</span> <span
  m='2329020'>preserve,</span> <span m='2330010'>then</span> <span
  m='2330700'>the</span> <span m='2330790'>technique</span> <span
  m='2331690'>here</span> <span m='2332260'>isn't</span> <span
  m='2332560'>what</span> <span m='2332740'>we</span> <span
  m='2332890'>would</span> <span m='2333040'>use.</span> <span
  m='2333490'>We</span> <span m='2333610'>would</span> <span
  m='2333760'>use</span> <span m='2333970'>a</span> <span
  m='2334030'>modified</span> <span m='2334600'>technique,</span> <span
  m='2335170'>which</span> <span m='2335350'>would</span> <span
  m='2335530'>be</span> <span m='2336160'>not</span> <span
  m='2336370'>impulse</span> <span m='2336820'>invariance,</span> <span
  m='2337420'>but</span> <span m='2337570'>step</span> <span
  m='2337860'>invariance.</span> </p><p><span m='2340000'>Well,</span> <span
  m='2340450'>let's</span> <span m='2340990'>finally</span> <span
  m='2341830'>look</span> <span m='2342190'>at</span> <span
  m='2343240'>what</span> <span m='2343480'>impulse</span> <span
  m='2343950'>invariance</span> <span m='2344650'>means</span> <span
  m='2345460'>in</span> <span m='2345610'>terms</span> <span
  m='2346150'>of</span> <span m='2346420'>a</span> <span
  m='2346480'>mapping</span> <span m='2347470'>from</span> <span
  m='2347650'>the</span> <span m='2347800'>s-plane</span> <span
  m='2348490'>to</span> <span m='2348640'>the</span> <span
  m='2348730'>z-plane.</span> <span m='2349330'>Let's</span> <span
  m='2349600'>look</span> <span m='2349870'>at</span> <span
  m='2350110'>it</span> <span m='2350560'>in</span> <span m='2350620'>a</span>
  <span m='2350680'>slightly</span> <span m='2351070'>different</span> <span
  m='2351430'>way</span> <span m='2351640'>than</span> <span
  m='2351790'>we've</span> <span m='2351970'>looked</span> <span
  m='2352240'>at</span> <span m='2352390'>it</span> <span
  m='2352480'>here.</span> <span m='2354350'>And</span> <span
  m='2354700'>we</span> <span m='2354850'>can</span> <span m='2355060'>do</span>
  <span m='2355270'>that</span> <span m='2355870'>by</span> <span
  m='2356740'>expressing</span> <span m='2357700'>the</span> <span
  m='2357910'>analog</span> <span m='2358420'>system</span> <span
  m='2359050'>function</span> <span m='2361420'>in</span> <span
  m='2361570'>a</span> <span m='2361630'>partial</span> <span
  m='2362080'>fraction</span> <span m='2362560'>expansion,</span> <span
  m='2364300'>in</span> <span m='2364450'>terms</span> <span
  m='2364900'>of</span> <span m='2364990'>a</span> <span m='2365050'>sum</span>
  <span m='2365350'>of</span> <span m='2365440'>factors</span> <span
  m='2365950'>of</span> <span m='2366070'>this</span> <span
  m='2366280'>form.</span> <span m='2366670'>So</span> <span
  m='2366910'>we</span> <span m='2367090'>have</span> <span
  m='2367900'>residues</span> <span m='2368245'>A</span> <span
  m='2368820'>sub</span> <span m='2368950'>k,</span> <span
  m='2370030'>poles</span> <span m='2370960'>s</span> <span
  m='2371550'>at</span> <span m='2371700'>s</span> <span
  m='2371890'>equals</span> <span m='2372190'>s</span> <span
  m='2372460'>of</span> <span m='2372590'>k,</span> <span m='2373480'>and</span>
  <span m='2373810'>we're</span> <span m='2373990'>expressing</span> <span
  m='2374530'>the</span> <span m='2374620'>system</span> <span
  m='2375010'>function</span> <span m='2375580'>as</span> <span
  m='2375760'>a</span> <span m='2375790'>linear</span> <span
  m='2376150'>combination</span> <span m='2377050'>of</span> <span
  m='2377200'>terms</span> <span m='2377560'>of</span> <span
  m='2377650'>this</span> <span m='2377830'>form.</span> </p><p><span
  m='2379640'>If</span> <span m='2379880'>there</span> <span
  m='2380090'>are</span> <span m='2380150'>multiple</span> <span
  m='2380600'>order</span> <span m='2380840'>poles,</span> <span
  m='2381350'>this</span> <span m='2381560'>expression</span> <span
  m='2382130'>is</span> <span m='2382190'>slightly</span> <span
  m='2382580'>more</span> <span m='2382790'>complicated.</span> <span
  m='2383720'>And</span> <span m='2384500'>what</span> <span
  m='2384830'>I'm</span> <span m='2385070'>about</span> <span
  m='2385400'>to</span> <span m='2385520'>say</span> <span
  m='2385970'>can</span> <span m='2386120'>be</span> <span
  m='2386240'>generalized</span> <span m='2386900'>to</span> <span
  m='2387020'>that</span> <span m='2387230'>case.</span> <span
  m='2388010'>But</span> <span m='2388340'>let's</span> <span
  m='2388610'>consider</span> <span m='2389090'>it</span> <span
  m='2389210'>here</span> <span m='2389510'>just</span> <span
  m='2389780'>for</span> <span m='2389870'>the</span> <span
  m='2389990'>case</span> <span m='2390290'>of</span> <span
  m='2390350'>simple</span> <span m='2390740'>poles,</span> <span
  m='2391670'>so</span> <span m='2391820'>that</span> <span
  m='2392240'>the</span> <span m='2392390'>system</span> <span
  m='2392810'>function</span> <span m='2393230'>in</span> <span
  m='2393320'>fact</span> <span m='2393620'>can</span> <span
  m='2393740'>be</span> <span m='2393920'>expanded</span> <span
  m='2394490'>out</span> <span m='2394790'>in</span> <span
  m='2394910'>the</span> <span m='2395000'>form</span> <span
  m='2395330'>that</span> <span m='2395450'>I</span> <span
  m='2395540'>have</span> <span m='2395810'>here.</span> </p><p><span
  m='2397750'>All</span> <span m='2397810'>right,</span> <span
  m='2398050'>well,</span> <span m='2398440'>if</span> <span
  m='2398650'>this</span> <span m='2398860'>is</span> <span
  m='2399040'>the</span> <span m='2399370'>analog</span> <span
  m='2399880'>system</span> <span m='2400300'>function,</span> <span
  m='2401530'>then</span> <span m='2402370'>you</span> <span
  m='2402490'>should</span> <span m='2402730'>recall</span> <span
  m='2403390'>that</span> <span m='2403690'>the</span> <span
  m='2403840'>analog</span> <span m='2405100'>impulse</span> <span
  m='2405610'>response--</span> <span m='2406710'>that</span> <span
  m='2406870'>is,</span> <span m='2406990'>the</span> <span
  m='2407110'>inverse</span> <span m='2407440'>Laplace</span> <span
  m='2407890'>transform</span> <span m='2408550'>of</span> <span
  m='2408670'>this--</span> <span m='2409720'>is</span> <span
  m='2409850'>the</span> <span m='2409930'>sum</span> <span
  m='2410560'>of</span> <span m='2411040'>exponentials</span> <span
  m='2413740'>with</span> <span m='2414040'>amplitudes</span> <span
  m='2414790'>A</span> <span m='2415070'>sub</span> <span m='2415260'>k,</span>
  <span m='2416410'>the</span> <span m='2416500'>same</span> <span
  m='2416770'>amplitudes</span> <span m='2417310'>as</span> <span
  m='2417430'>we</span> <span m='2417580'>have</span> <span
  m='2417850'>here,</span> <span m='2418990'>and</span> <span
  m='2419110'>complex</span> <span m='2419680'>exponentials</span> <span
  m='2420920'>e</span> <span m='2421160'>to</span> <span m='2421330'>s</span>
  <span m='2421420'>sub</span> <span m='2421510'>k.</span> <span
  m='2422950'>And</span> <span m='2423070'>this</span> <span
  m='2423190'>should</span> <span m='2423430'>be</span> <span
  m='2423970'>a</span> <span m='2424360'>t,</span> <span m='2424990'>not</span>
  <span m='2425170'>a</span> <span m='2425740'>T.</span> <span
  m='2426910'>That</span> <span m='2427180'>is</span> <span
  m='2427420'>time,</span> <span m='2428320'>t.</span> </p><p><span
  m='2429400'>So</span> <span m='2430180'>this</span> <span
  m='2430420'>then</span> <span m='2430690'>is</span> <span
  m='2430810'>the</span> <span m='2430930'>form</span> <span
  m='2431320'>of</span> <span m='2431410'>the</span> <span
  m='2431530'>impulse</span> <span m='2431920'>response,</span> <span
  m='2432560'>which</span> <span m='2432640'>corresponds</span> <span
  m='2433780'>to</span> <span m='2433900'>this</span> <span
  m='2434050'>system</span> <span m='2434500'>function.</span> <span
  m='2435730'>And</span> <span m='2435850'>now</span> <span
  m='2436030'>the</span> <span m='2436180'>impulse</span> <span
  m='2436810'>invariant</span> <span m='2437380'>method</span> <span
  m='2438700'>says,</span> <span m='2440230'>replace</span> <span
  m='2440800'>this</span> <span m='2441700'>by</span> <span m='2442570'>a</span>
  <span m='2442690'>unit</span> <span m='2443020'>sample</span> <span
  m='2443440'>response</span> <span m='2443950'>for</span> <span
  m='2444070'>the</span> <span m='2444160'>digital</span> <span
  m='2444550'>filter,</span> <span m='2445570'>which</span> <span
  m='2445960'>is</span> <span m='2446110'>obtained</span> <span
  m='2446590'>by</span> <span m='2446740'>replacing</span> <span
  m='2447610'>t</span> <span m='2448300'>by</span> <span m='2448540'>n</span>
  <span m='2448840'>times</span> <span m='2449620'>T.</span> <span
  m='2449920'>That</span> <span m='2450070'>is,</span> <span
  m='2452170'>obtaining</span> <span m='2452860'>the</span> <span
  m='2453010'>unit</span> <span m='2453280'>sample</span> <span
  m='2453640'>response</span> <span m='2454150'>of</span> <span
  m='2454240'>the</span> <span m='2454330'>digital</span> <span
  m='2454720'>filter</span> <span m='2455710'>by</span> <span
  m='2456130'>sampling</span> <span m='2457360'>the</span> <span
  m='2457780'>impulse</span> <span m='2458260'>response</span> <span
  m='2458740'>of</span> <span m='2458830'>the</span> <span
  m='2458950'>analog</span> <span m='2459430'>filter,</span> <span
  m='2460450'>in</span> <span m='2460570'>which</span> <span
  m='2460840'>case</span> <span m='2461620'>we</span> <span
  m='2461800'>get</span> <span m='2462610'>the</span> <span
  m='2462700'>sum</span> <span m='2463720'>of</span> <span m='2464080'>A</span>
  <span m='2464380'>sub</span> <span m='2464500'>k,</span> <span
  m='2465535'>E</span> <span m='2465970'>to</span> <span m='2466120'>s</span>
  <span m='2466270'>of</span> <span m='2466600'>k.</span> <span
  m='2467140'>And</span> <span m='2467320'>now</span> <span
  m='2467770'>time,</span> <span m='2468340'>t,</span> <span
  m='2469270'>is</span> <span m='2469420'>replaced</span> <span
  m='2469990'>by</span> <span m='2470470'>n</span> <span
  m='2470855'>times</span> <span m='2471240'>T.</span> </p><p><span
  m='2473420'>A</span> <span m='2473530'>sampled</span> <span
  m='2474080'>unit</span> <span m='2474400'>step,</span> <span
  m='2475510'>a</span> <span m='2475990'>sampled</span> <span
  m='2476470'>analog</span> <span m='2477010'>unit</span> <span
  m='2477390'>step,</span> <span m='2478000'>results</span> <span
  m='2478630'>in</span> <span m='2479380'>a</span> <span
  m='2479860'>discrete</span> <span m='2480340'>time</span> <span
  m='2480910'>unit</span> <span m='2481250'>step.</span> <span
  m='2482080'>And</span> <span m='2482170'>so</span> <span
  m='2482350'>consequently,</span> <span m='2483490'>the</span> <span
  m='2483580'>unit</span> <span m='2483850'>sample</span> <span
  m='2484270'>response</span> <span m='2484930'>that</span> <span
  m='2485050'>we</span> <span m='2485230'>end</span> <span m='2485410'>up</span>
  <span m='2485620'>with</span> <span m='2486340'>is</span> <span
  m='2487020'>A</span> <span m='2487300'>sub</span> <span m='2487420'>k,</span>
  <span m='2487720'>the</span> <span m='2487840'>same</span> <span
  m='2488230'>coefficients</span> <span m='2488950'>as</span> <span
  m='2489100'>we</span> <span m='2489220'>had</span> <span
  m='2489430'>here,</span> <span m='2490200'>e</span> <span
  m='2490520'>to</span> <span m='2490690'>the</span> <span m='2490800'>s</span>
  <span m='2491110'>sub</span> <span m='2491200'>k,</span> <span
  m='2491680'>n</span> <span m='2491980'>times</span> <span m='2492380'>T</span>
  <span m='2493450'>times</span> <span m='2493750'>the</span> <span
  m='2493810'>unit</span> <span m='2494100'>step.</span> </p><p><span
  m='2495910'>Well,</span> <span m='2496120'>we</span> <span
  m='2496270'>can</span> <span m='2496420'>write</span> <span
  m='2496660'>that</span> <span m='2497020'>in</span> <span m='2497200'>a</span>
  <span m='2497260'>slightly</span> <span m='2497680'>different</span> <span
  m='2498100'>way.</span> <span m='2499450'>We</span> <span
  m='2499540'>can</span> <span m='2499690'>write</span> <span
  m='2499960'>that</span> <span m='2500320'>as</span> <span
  m='2501250'>the</span> <span m='2501370'>sum</span> <span
  m='2501940'>of</span> <span m='2502120'>A</span> <span m='2502390'>sub</span>
  <span m='2502560'>k,</span> <span m='2503920'>and</span> <span
  m='2504460'>some</span> <span m='2504760'>factor,</span> <span
  m='2505210'>e</span> <span m='2505660'>to</span> <span m='2505780'>the</span>
  <span m='2505900'>s</span> <span m='2506015'>sub</span> <span
  m='2506130'>k</span> <span m='2506845'>T</span> <span m='2507190'>is</span>
  <span m='2507310'>what</span> <span m='2507490'>it</span> <span
  m='2507610'>is.</span> <span m='2508390'>Some</span> <span
  m='2508495'>factor</span> <span m='2508600'>raised</span> <span
  m='2509410'>to</span> <span m='2509560'>the</span> <span
  m='2509680'>n-th</span> <span m='2509920'>power</span> <span
  m='2510890'>times</span> <span m='2511230'>the</span> <span
  m='2511300'>unit</span> <span m='2511660'>step.</span> <span
  m='2512860'>And</span> <span m='2512980'>consequently</span> <span
  m='2513880'>we</span> <span m='2514030'>can</span> <span
  m='2514180'>write</span> <span m='2514420'>down</span> <span
  m='2514690'>by</span> <span m='2514870'>inspection</span> <span
  m='2516430'>the</span> <span m='2516850'>z</span> <span
  m='2517150'>transform</span> <span m='2518080'>or</span> <span
  m='2518230'>system</span> <span m='2518680'>function</span> <span
  m='2519490'>that</span> <span m='2519760'>corresponds</span> <span
  m='2520660'>to</span> <span m='2520780'>this</span> <span
  m='2520990'>unit</span> <span m='2521260'>sample</span> <span
  m='2521650'>response.</span> <span m='2522880'>In</span> <span
  m='2523000'>particular,</span> <span m='2523810'>it</span> <span
  m='2524110'>is</span> <span m='2525050'>H</span> <span m='2525267'>of</span>
  <span m='2525485'>z</span> <span m='2526930'>equal</span> <span
  m='2527320'>to</span> <span m='2527470'>the</span> <span
  m='2527590'>sum</span> <span m='2528640'>of</span> <span m='2528850'>A</span>
  <span m='2529160'>sub</span> <span m='2529330'>k,</span> <span
  m='2530260'>times</span> <span m='2530680'>1</span> <span
  m='2530950'>minus</span> <span m='2531480'>8,</span> <span
  m='2531660'>e</span> <span m='2531790'>the</span> <span m='2531940'>s</span>
  <span m='2532210'>of</span> <span m='2532330'>k</span> <span
  m='2533080'>times</span> <span m='2533350'>T</span> <span m='2534100'>z</span>
  <span m='2534340'>to</span> <span m='2534490'>the</span> <span
  m='2534580'>minus</span> <span m='2535000'>1,</span> <span
  m='2535780'>that's</span> <span m='2535930'>simply</span> <span
  m='2536380'>by</span> <span m='2536620'>inspection</span> <span
  m='2537490'>of</span> <span m='2538000'>this</span> <span
  m='2538180'>expression.</span> </p><p><span m='2540450'>All</span> <span
  m='2540540'>right.</span> <span m='2540900'>Well,</span> <span
  m='2541530'>so</span> <span m='2542010'>we</span> <span
  m='2542190'>started</span> <span m='2543120'>with</span> <span
  m='2544670'>an</span> <span m='2544820'>analog</span> <span
  m='2545420'>system</span> <span m='2545870'>function</span> <span
  m='2546830'>of</span> <span m='2546980'>this</span> <span
  m='2547250'>form,</span> <span m='2548910'>these</span> <span
  m='2549150'>coefficients</span> <span m='2549900'>in</span> <span
  m='2549990'>these</span> <span m='2550200'>poles.</span> <span
  m='2552010'>We</span> <span m='2552160'>ended</span> <span
  m='2552430'>up</span> <span m='2552700'>with</span> <span m='2553270'>a</span>
  <span m='2553660'>digital</span> <span m='2554080'>system</span> <span
  m='2554560'>function</span> <span m='2555130'>of</span> <span
  m='2555280'>this</span> <span m='2555550'>form,</span> <span
  m='2556240'>the</span> <span m='2556330'>same</span> <span
  m='2556600'>coefficients,</span> <span m='2557980'>and</span> <span
  m='2558160'>poles</span> <span m='2558820'>instead</span> <span
  m='2559240'>of</span> <span m='2559450'>at</span> <span m='2559555'>s</span>
  <span m='2559607'>sub</span> <span m='2559660'>k,</span> <span
  m='2560470'>as</span> <span m='2560590'>they</span> <span
  m='2560710'>were</span> <span m='2560860'>in</span> <span
  m='2560950'>the</span> <span m='2561070'>analog</span> <span
  m='2561490'>case,</span> <span m='2562290'>at</span> <span
  m='2562490'>e</span> <span m='2562700'>to</span> <span m='2562900'>the</span>
  <span m='2562960'>s</span> <span m='2563020'>sub</span> <span
  m='2563080'>k</span> <span m='2564080'>T.</span> </p><p><span
  m='2566260'>So</span> <span m='2566410'>this</span> <span
  m='2566600'>says</span> <span m='2566920'>then</span> <span
  m='2567490'>that</span> <span m='2569200'>the</span> <span
  m='2569380'>impulse</span> <span m='2569890'>invariant</span> <span
  m='2570430'>method</span> <span m='2571690'>maps</span> <span
  m='2572510'>a</span> <span m='2572925'>pole</span> <span m='2573610'>in</span>
  <span m='2573730'>the</span> <span m='2573850'>s-plane</span> <span
  m='2574780'>which</span> <span m='2574990'>was</span> <span
  m='2575170'>at</span> <span m='2575450'>s</span> <span m='2575940'>sub</span>
  <span m='2576185'>k,</span> <span m='2577210'>maps</span> <span
  m='2577660'>it</span> <span m='2578320'>to</span> <span m='2578920'>a</span>
  <span m='2579220'>pole</span> <span m='2580330'>in</span> <span
  m='2580420'>the</span> <span m='2580510'>z-plane</span> <span
  m='2581350'>at</span> <span m='2581560'>z</span> <span
  m='2582010'>equal</span> <span m='2582430'>to</span> <span
  m='2582820'>e</span> <span m='2583015'>to</span> <span m='2583210'>the</span>
  <span m='2583360'>s</span> <span m='2583577'>sub</span> <span
  m='2583795'>k,</span> <span m='2584470'>T.</span> <span
  m='2586930'>Well,</span> <span m='2587020'>does</span> <span
  m='2587200'>that</span> <span m='2587440'>mean</span> <span
  m='2588220'>that</span> <span m='2588640'>impulse</span> <span
  m='2589120'>invariance</span> <span m='2589780'>is</span> <span
  m='2589900'>basically</span> <span m='2590500'>a</span> <span
  m='2590560'>method</span> <span m='2591790'>which</span> <span
  m='2592000'>maps</span> <span m='2592600'>s</span> <span m='2593110'>to</span>
  <span m='2593260'>z</span> <span m='2594130'>according</span> <span
  m='2594940'>to</span> <span m='2595750'>this</span> <span
  m='2596320'>transformation.</span> </p><p><span m='2597700'>Well</span> <span
  m='2598030'>no,</span> <span m='2598300'>it</span> <span
  m='2598390'>doesn't</span> <span m='2598660'>do</span> <span
  m='2598870'>that.</span> <span m='2599550'>What</span> <span
  m='2599710'>it</span> <span m='2599800'>does</span> <span
  m='2600340'>is</span> <span m='2600550'>it</span> <span
  m='2600670'>maps</span> <span m='2601030'>the</span> <span
  m='2601150'>poles</span> <span m='2601780'>in</span> <span
  m='2601870'>the</span> <span m='2601990'>s-plane</span> <span
  m='2603000'>to</span> <span m='2603130'>poles</span> <span
  m='2603640'>in</span> <span m='2603730'>the</span> <span
  m='2603820'>z-plane</span> <span m='2604990'>according</span> <span
  m='2605440'>to</span> <span m='2605560'>this</span> <span
  m='2605800'>mapping.</span> <span m='2607630'>The</span> <span
  m='2607780'>other</span> <span m='2607990'>thing</span> <span
  m='2608230'>that</span> <span m='2608350'>it</span> <span
  m='2608410'>preserves</span> <span m='2609220'>are</span> <span
  m='2609340'>these</span> <span m='2609670'>coefficients,</span> <span
  m='2610600'>the</span> <span m='2610720'>coefficients</span> <span
  m='2611155'>A</span> <span m='2611590'>sub</span> <span m='2611730'>k,</span>
  <span m='2612400'>that</span> <span m='2612550'>is</span> <span
  m='2612640'>the</span> <span m='2612760'>residues</span> <span
  m='2613360'>of</span> <span m='2613450'>the</span> <span
  m='2613540'>poles.</span> <span m='2614380'>So</span> <span
  m='2614530'>it</span> <span m='2614590'>maintains</span> <span
  m='2615160'>the</span> <span m='2615280'>residues</span> <span
  m='2615820'>of</span> <span m='2615940'>the</span> <span
  m='2616060'>poles.</span> <span m='2616960'>It</span> <span
  m='2617110'>maps</span> <span m='2617480'>the</span> <span
  m='2617590'>poles</span> <span m='2618100'>according</span> <span
  m='2618490'>to</span> <span m='2618610'>z</span> <span
  m='2619060'>equals</span> <span m='2619240'>e</span> <span
  m='2619360'>to</span> <span m='2619480'>the</span> <span
  m='2619720'>st.</span> </p><p><span m='2621610'>The</span> <span
  m='2621750'>0s,</span> <span m='2622520'>by</span> <span
  m='2622790'>the</span> <span m='2622880'>way,</span> <span
  m='2623870'>in</span> <span m='2624100'>general</span> <span
  m='2624680'>will</span> <span m='2624920'>not</span> <span
  m='2625220'>come</span> <span m='2625460'>out</span> <span
  m='2626510'>to</span> <span m='2626810'>have</span> <span
  m='2627020'>been</span> <span m='2627200'>mapped</span> <span
  m='2627680'>according</span> <span m='2628130'>to</span> <span
  m='2628220'>the</span> <span m='2628340'>same</span> <span
  m='2628610'>mappings</span> <span m='2629180'>equals</span> <span
  m='2629550'>e</span> <span m='2629653'>to</span> <span m='2629756'>the</span>
  <span m='2629860'>st.</span> <span m='2630460'>In</span> <span
  m='2630590'>other</span> <span m='2630770'>words,</span> <span
  m='2631530'>if</span> <span m='2631550'>we</span> <span m='2631670'>had</span>
  <span m='2631850'>a</span> <span m='2631910'>0</span> <span
  m='2632600'>at</span> <span m='2632870'>s</span> <span
  m='2633140'>equals</span> <span m='2633420'>s</span> <span
  m='2633680'>sub</span> <span m='2633870'>0,</span> <span m='2635330'>as</span>
  <span m='2635540'>we'll</span> <span m='2635660'>see</span> <span
  m='2635960'>actually</span> <span m='2636320'>in</span> <span
  m='2636440'>an</span> <span m='2636530'>example</span> <span
  m='2636990'>that</span> <span m='2637100'>we'll</span> <span
  m='2637250'>work</span> <span m='2637520'>next</span> <span
  m='2637790'>time,</span> <span m='2638750'>the</span> <span
  m='2638840'>0</span> <span m='2639380'>in</span> <span m='2639500'>the</span>
  <span m='2639590'>z-plane</span> <span m='2640160'>will</span> <span
  m='2640280'>not</span> <span m='2640550'>come</span> <span
  m='2640820'>out,</span> <span m='2641090'>will</span> <span
  m='2641270'>not</span> <span m='2641570'>come</span> <span
  m='2641780'>out</span> <span m='2642140'>at</span> <span m='2642350'>z</span>
  <span m='2642710'>equals</span> <span m='2642990'>e</span> <span
  m='2643270'>to</span> <span m='2643440'>the</span> <span m='2643550'>s</span>
  <span m='2643970'>0</span> <span m='2644840'>T.</span> <span
  m='2645620'>The</span> <span m='2645710'>poles</span> <span
  m='2646430'>are</span> <span m='2646550'>mapped</span> <span
  m='2646880'>according</span> <span m='2647270'>to</span> <span
  m='2647330'>that</span> <span m='2647540'>mapping,</span> <span
  m='2648180'>and</span> <span m='2648200'>the</span> <span
  m='2648290'>residues</span> <span m='2648830'>are</span> <span
  m='2648920'>preserved.</span> <span m='2649820'>And</span> <span
  m='2649970'>that</span> <span m='2650300'>is</span> <span
  m='2650930'>essentially</span> <span m='2651470'>what</span> <span
  m='2651650'>defines</span> <span m='2652100'>the</span> <span
  m='2652220'>impulse</span> <span m='2652610'>invariant</span> <span
  m='2653070'>mapping.</span> </p><p><span m='2655520'>Well,</span> <span
  m='2656600'>we</span> <span m='2656810'>had</span> <span
  m='2657020'>our</span> <span m='2657230'>two</span> <span
  m='2657470'>initial</span> <span m='2657830'>guidelines.</span> <span
  m='2658880'>One</span> <span m='2659150'>is</span> <span
  m='2659330'>that</span> <span m='2659690'>we</span> <span
  m='2659900'>want</span> <span m='2660380'>the</span> <span
  m='2660500'>behavior</span> <span m='2661130'>on</span> <span
  m='2661280'>the</span> <span m='2661370'>j</span> <span
  m='2661610'>omega</span> <span m='2661970'>axis</span> <span
  m='2663020'>to</span> <span m='2663140'>map</span> <span m='2663740'>to</span>
  <span m='2664670'>the</span> <span m='2664760'>behavior</span> <span
  m='2665930'>in</span> <span m='2666080'>the</span> <span
  m='2666620'>digital</span> <span m='2666980'>domain</span> <span
  m='2667610'>on</span> <span m='2667760'>the</span> <span
  m='2667850'>unit</span> <span m='2668150'>circle.</span> <span
  m='2669620'>Does</span> <span m='2669980'>the</span> <span
  m='2670100'>impulse</span> <span m='2670520'>invariant</span> <span
  m='2670910'>method</span> <span m='2671240'>do</span> <span
  m='2671420'>that?</span> <span m='2672200'>Well,</span> <span
  m='2672590'>it</span> <span m='2672740'>does,</span> <span
  m='2673710'>except</span> <span m='2674330'>for</span> <span
  m='2675020'>the</span> <span m='2675170'>effect</span> <span
  m='2675490'>of</span> <span m='2675620'>aliasing.</span> <span
  m='2676670'>But</span> <span m='2677090'>basically,</span> <span
  m='2677990'>it</span> <span m='2678290'>is</span> <span m='2679040'>the</span>
  <span m='2679370'>analog</span> <span m='2680480'>frequency</span> <span
  m='2681050'>response</span> <span m='2682130'>that</span> <span
  m='2682280'>dictates</span> <span m='2683090'>what</span> <span
  m='2683330'>the</span> <span m='2683420'>digital</span> <span
  m='2683780'>frequency</span> <span m='2684320'>response</span> <span
  m='2684910'>is.</span> <span m='2685610'>And</span> <span
  m='2685730'>so</span> <span m='2686720'>in</span> <span
  m='2686870'>that</span> <span m='2687080'>sense,</span> <span
  m='2687920'>impulse</span> <span m='2688400'>invariance</span> <span
  m='2688940'>satisfies</span> <span m='2689630'>that</span> <span
  m='2689810'>objective.</span> <span m='2691040'>The</span> <span
  m='2691130'>second</span> <span m='2691520'>question</span> <span
  m='2692150'>is</span> <span m='2692690'>whether</span> <span
  m='2693230'>it</span> <span m='2693530'>maintains</span> <span
  m='2694210'>the</span> <span m='2694260'>ability</span> <span
  m='2694730'>of</span> <span m='2694850'>the</span> <span
  m='2694940'>filter.</span> <span m='2696260'>And</span> <span
  m='2696380'>the</span> <span m='2696500'>answer</span> <span
  m='2696830'>there</span> <span m='2697250'>also</span> <span
  m='2697730'>is</span> <span m='2697850'>that</span> <span
  m='2698000'>it</span> <span m='2698090'>does,</span> <span
  m='2698350'>so</span> <span m='2698450'>we</span> <span m='2698540'>can</span>
  <span m='2698690'>see</span> <span m='2698900'>that</span> <span
  m='2699110'>very</span> <span m='2699320'>easily.</span> </p><p><span
  m='2700280'>In</span> <span m='2700400'>particular,</span> <span
  m='2701610'>if</span> <span m='2701660'>we</span> <span
  m='2701780'>have</span> <span m='2701990'>an</span> <span
  m='2702080'>analog</span> <span m='2702950'>pole</span> <span
  m='2704580'>with</span> <span m='2705240'>a</span> <span
  m='2705510'>real</span> <span m='2705780'>part</span> <span
  m='2706140'>sigma</span> <span m='2706580'>sub</span> <span
  m='2706680'>k,</span> <span m='2707580'>an</span> <span
  m='2707700'>imaginary</span> <span m='2708210'>part</span> <span
  m='2708490'>omega</span> <span m='2708760'>sub</span> <span
  m='2709030'>k,</span> <span m='2710490'>then</span> <span
  m='2711360'>the</span> <span m='2711630'>digital</span> <span
  m='2712080'>pole,</span> <span m='2713370'>the</span> <span
  m='2713460'>pole</span> <span m='2713850'>of</span> <span
  m='2713940'>the</span> <span m='2714030'>digital</span> <span
  m='2714390'>filter,</span> <span m='2715440'>maps</span> <span
  m='2715950'>to</span> <span m='2717240'>z</span> <span m='2717455'>sub</span>
  <span m='2717670'>k</span> <span m='2718170'>equal</span> <span
  m='2718560'>to</span> <span m='2718770'>e</span> <span m='2719000'>to</span>
  <span m='2719160'>the</span> <span m='2719210'>s</span> <span
  m='2719260'>sub</span> <span m='2719310'>k</span> <span m='2719970'>T,</span>
  <span m='2720756'>e</span> <span m='2721150'>to</span> <span
  m='2721290'>the</span> <span m='2721410'>j</span> <span
  m='2721770'>omega</span> <span m='2722310'>sub</span> <span
  m='2722400'>k</span> <span m='2723150'>T.</span> <span m='2725040'>And</span>
  <span m='2725790'>the</span> <span m='2725910'>magnitude</span> <span
  m='2726870'>of</span> <span m='2727080'>this</span> <span
  m='2728670'>is</span> <span m='2728820'>equal</span> <span
  m='2729210'>to</span> <span m='2729950'>of</span> <span
  m='2730080'>course,</span> <span m='2731970'>the</span> <span
  m='2732090'>product</span> <span m='2732510'>of</span> <span
  m='2732570'>the</span> <span m='2732690'>magnitudes.</span> <span
  m='2734040'>The</span> <span m='2734160'>magnitude</span> <span
  m='2734730'>of</span> <span m='2734820'>this</span> <span
  m='2735060'>term</span> <span m='2735720'>is</span> <span
  m='2736560'>unity.</span> <span m='2738390'>So</span> <span
  m='2738730'>all</span> <span m='2738860'>that</span> <span
  m='2738960'>we</span> <span m='2739080'>care</span> <span
  m='2739350'>about</span> <span m='2739590'>is</span> <span
  m='2739710'>the</span> <span m='2739800'>magnitude</span> <span
  m='2741070'>of</span> <span m='2741150'>the</span> <span
  m='2741570'>sigma</span> <span m='2741940'>sub</span> <span
  m='2742160'>k</span> <span m='2742380'>T.</span> <span
  m='2743820'>Well,</span> <span m='2744600'>if</span> <span
  m='2744750'>the</span> <span m='2744870'>analog</span> <span
  m='2745320'>filter</span> <span m='2745680'>is</span> <span
  m='2745770'>stable,</span> <span m='2746930'>sigma</span> <span
  m='2747390'>sub</span> <span m='2747570'>k</span> <span m='2747810'>is</span>
  <span m='2747930'>negative.</span> <span m='2749060'>If</span> <span
  m='2749190'>sigma</span> <span m='2749490'>sub</span> <span
  m='2749870'>k</span> <span m='2749950'>is</span> <span
  m='2750030'>negative,</span> <span m='2750990'>then</span> <span
  m='2751170'>either</span> <span m='2751470'>the</span> <span
  m='2751590'>sigma</span> <span m='2751960'>sub</span> <span
  m='2752090'>k</span> <span m='2752890'>T</span> <span m='2753210'>has</span>
  <span m='2753420'>a</span> <span m='2753480'>magnitude</span> <span
  m='2754050'>less</span> <span m='2754320'>than</span> <span
  m='2754470'>1.</span> <span m='2755590'>So</span> <span
  m='2755700'>consequently,</span> <span m='2757170'>if</span> <span
  m='2757770'>the</span> <span m='2757890'>real</span> <span
  m='2758220'>part</span> <span m='2758790'>of</span> <span m='2758970'>s</span>
  <span m='2759210'>sub</span> <span m='2759330'>k</span> <span
  m='2760020'>is</span> <span m='2760260'>less</span> <span
  m='2760500'>than</span> <span m='2760650'>0,</span> <span
  m='2761430'>negative,</span> <span m='2762540'>then</span> <span
  m='2763140'>the</span> <span m='2763260'>magnitude</span> <span
  m='2764370'>of</span> <span m='2764640'>z</span> <span m='2764775'>sub</span>
  <span m='2764910'>k,</span> <span m='2765300'>the</span> <span
  m='2765390'>magnitude</span> <span m='2765930'>of</span> <span
  m='2766020'>the</span> <span m='2766110'>pole</span> <span
  m='2766620'>is</span> <span m='2767100'>less</span> <span
  m='2767340'>than</span> <span m='2767490'>1.</span> </p><p><span
  m='2769210'>So</span> <span m='2769800'>this</span> <span
  m='2770220'>in</span> <span m='2770370'>fact</span> <span
  m='2771000'>is</span> <span m='2772020'>a</span> <span
  m='2772680'>digital</span> <span m='2773040'>filter</span> <span
  m='2773430'>design</span> <span m='2773820'>technique</span> <span
  m='2774570'>that</span> <span m='2775620'>has</span> <span
  m='2777000'>a</span> <span m='2777060'>number</span> <span
  m='2777420'>of</span> <span m='2777510'>advantages.</span> <span
  m='2779900'>And</span> <span m='2780860'>in</span> <span
  m='2781340'>fact,</span> <span m='2781700'>it's</span> <span
  m='2781820'>a</span> <span m='2781880'>very</span> <span
  m='2782090'>useful</span> <span m='2783020'>design</span> <span
  m='2783440'>technique.</span> <span m='2784010'>It's</span> <span
  m='2784160'>one</span> <span m='2784370'>of</span> <span
  m='2784700'>the</span> <span m='2784820'>standard</span> <span
  m='2785300'>digital</span> <span m='2785660'>filter</span> <span
  m='2786230'>design</span> <span m='2786680'>techniques.</span> </p><p><span
  m='2789390'>In</span> <span m='2790020'>the</span> <span
  m='2790650'>next</span> <span m='2790980'>lecture,</span> <span
  m='2791950'>I</span> <span m='2792510'>will</span> <span
  m='2793200'>briefly</span> <span m='2793680'>present</span> <span
  m='2794310'>an</span> <span m='2794400'>example</span> <span
  m='2795210'>of</span> <span m='2795960'>an</span> <span
  m='2796050'>impulse</span> <span m='2796470'>invariant</span> <span
  m='2797190'>design,</span> <span m='2797760'>just</span> <span
  m='2797940'>simply</span> <span m='2798810'>to</span> <span
  m='2798930'>remind</span> <span m='2799410'>you</span> <span
  m='2799530'>actually</span> <span m='2800310'>again</span> <span
  m='2800850'>of</span> <span m='2801000'>the</span> <span
  m='2801120'>fact</span> <span m='2801660'>that</span> <span
  m='2802440'>aliasing</span> <span m='2803010'>is</span> <span
  m='2803130'>an</span> <span m='2803250'>issue,</span> <span
  m='2803890'>number</span> <span m='2804090'>one,</span> <span
  m='2804970'>and</span> <span m='2805070'>number</span> <span
  m='2805230'>two,</span> <span m='2805650'>that</span> <span
  m='2806250'>it</span> <span m='2806370'>maps</span> <span
  m='2806780'>poles</span> <span m='2807570'>according</span> <span
  m='2808020'>to</span> <span m='2808295'>z</span> <span
  m='2808570'>equals</span> <span m='2808850'>z</span> <span
  m='2809070'>to</span> <span m='2809160'>the</span> <span
  m='2809310'>st,</span> <span m='2809730'>but</span> <span
  m='2809940'>not</span> <span m='2810510'>0s.</span> <span
  m='2811170'>In</span> <span m='2811260'>fact,</span> <span
  m='2811530'>the</span> <span m='2811590'>0s</span> <span
  m='2811980'>end</span> <span m='2812160'>up</span> <span
  m='2812310'>someplace</span> <span m='2812850'>else.</span> <span
  m='2814110'>And</span> <span m='2814740'>in</span> <span
  m='2814920'>addition</span> <span m='2815790'>in</span> <span
  m='2815910'>that</span> <span m='2816120'>lecture,</span> <span
  m='2817050'>we'll</span> <span m='2817230'>talk</span> <span
  m='2817590'>about</span> <span m='2818190'>another</span> <span
  m='2819450'>design</span> <span m='2820080'>technique,</span> <span
  m='2821100'>which</span> <span m='2821460'>is</span> <span
  m='2821850'>likewise</span> <span m='2822450'>one</span> <span
  m='2822630'>of</span> <span m='2822750'>the</span> <span
  m='2823050'>classical</span> <span m='2823650'>digital</span> <span
  m='2824040'>filter</span> <span m='2824400'>design</span> <span
  m='2825060'>methods,</span> <span m='2826030'>which</span> <span
  m='2826110'>is</span> <span m='2826200'>referred</span> <span
  m='2826560'>to</span> <span m='2826770'>as</span> <span m='2826890'>the</span>
  <span m='2826980'>bilinear</span> <span m='2827460'>transformation.</span>
  <span m='2829080'>And</span> <span m='2829170'>the</span> <span
  m='2829260'>lecture</span> <span m='2829620'>following</span> <span
  m='2830130'>that</span> <span m='2830850'>then</span> <span
  m='2831360'>I</span> <span m='2831690'>will</span> <span
  m='2833460'>show</span> <span m='2833880'>some</span> <span
  m='2834120'>examples</span> <span m='2834930'>of</span> <span
  m='2836120'>some</span> <span m='2836340'>digital</span> <span
  m='2836670'>filter</span> <span m='2837030'>designs,</span> <span
  m='2838290'>using</span> <span m='2838710'>both</span> <span
  m='2838950'>impulse</span> <span m='2839430'>invariance</span> <span
  m='2840090'>and</span> <span m='2840300'>the</span> <span
  m='2840390'>bilinear</span> <span m='2840870'>transformation</span> <span
  m='2841650'>to</span> <span m='2841770'>compare</span> <span
  m='2842160'>them.</span> <span m='2842510'>Thank</span> <span
  m='2842710'>you.</span> </p><p></p>
embedded_media:
  - uid: 70cf0d53f7ef869c6bbcfbb060aec824
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: MITRES_6_008S11_lec14.pdf
    title: MITRES_6_008S11_lec14.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-14-design-of-iir-digital-filters-part-1/MITRES_6_008S11_lec14.pdf
  - uid: 1ab5b5f13b6178b8d979498c1f88584e
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: U13m6L6R58w
  - uid: dc3f8243b39d4127baf9a6ec0538b5b6
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-14-design-iir-digital/id481803782?i=106433646
  - uid: c54624ca2aab23a985400d5f93e7a00a
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec14_300k.mp4'
  - uid: 536d198bcd825661e106546a6d1cfb76
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/U13m6L6R58w/default.jpg'
  - uid: 2f7c89056836048099796c5aa136f15d
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: U13m6L6R58w
  - uid: 779dc8ec9fecf3b4350ed5d44ae35918
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: U13m6L6R58w.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-14-design-of-iir-digital-filters-part-1/U13m6L6R58w.srt
  - uid: 559f1c6f24fe8c551240d1dc1100ac2c
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: U13m6L6R58w.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-14-design-of-iir-digital-filters-part-1/U13m6L6R58w.pdf
  - uid: ee11d1d1c28ce3759c61b2ed45ca8c56
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: ad6703bf1573eb9a91bd46aa1fd48175
    parent_uid: 839a64db7fb18dcca85023c4ccd0da51
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
