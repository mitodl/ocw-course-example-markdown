---
order_index: null
title: 'Lecture 18: Computation of the Discrete Fourier Transform, Part 1'
template_type: Tabbed
uid: b909330a94772374a9d125b7ebd1870a
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-18-computation-of-the-discrete-fourier-transform-part-1
short_url: lecture-18-computation-of-the-discrete-fourier-transform-part-1
inline_embed_id: '52669017lecture18:computationofthediscretefouriertransform,part182396866'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Direct computation of the discrete-time
  Fourier transform, computation resulting from successive decimation of the
  sequences, the decimation-in-time form of the fast Fourier transform (FFT)
  algorithm, basic butterfly computation.</p> <p><strong>Instructor:</strong>
  Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Computation of the Discrete Fourier Transform, Part 1 (<img
  src="/images/inacessible.gif" alt="This resource may not render correctly in a
  screen reader." /><a
  href="./resolveuid/4753a56f0fd115a04b158b64b0e6853c">PDF</a>)</p>
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
  m='21980'>[MUSIC PLAYING]</span> </p><p></p><p><span m='45340'>ALAN
  OPPENHEIM:</span> <span m='45390'>In</span> <span m='45440'>this</span> <span
  m='45620'>lecture,</span> <span m='46530'>we</span> <span
  m='46880'>will</span> <span m='47120'>begin</span> <span m='47420'>the</span>
  <span m='47480'>discussion</span> <span m='48320'>of</span> <span
  m='48620'>the</span> <span m='48740'>computation</span> <span
  m='49790'>of</span> <span m='49970'>the</span> <span m='50090'>discrete</span>
  <span m='50450'>Fourier</span> <span m='50870'>transform.</span> <span
  m='53160'>This</span> <span m='53510'>is</span> <span m='53870'>an</span>
  <span m='53960'>extremely</span> <span m='54830'>important</span> <span
  m='55310'>topic</span> <span m='55940'>in</span> <span m='56360'>this</span>
  <span m='56510'>set</span> <span m='56750'>of</span> <span
  m='56840'>lectures</span> <span m='57320'>for</span> <span m='57470'>a</span>
  <span m='57500'>number</span> <span m='57800'>of</span> <span
  m='57920'>reasons.</span> <span m='59490'>One</span> <span m='59570'>of</span>
  <span m='59660'>the</span> <span m='59750'>reasons</span> <span
  m='60500'>is</span> <span m='61100'>that</span> <span m='61700'>the</span>
  <span m='61910'>principal</span> <span m='62480'>algorithm</span> <span
  m='63500'>that</span> <span m='63620'>we'll</span> <span m='63800'>be</span>
  <span m='63950'>discussing,</span> <span m='65300'>the</span> <span
  m='65930'>algorithm,</span> <span m='66530'>which</span> <span
  m='66890'>we'll</span> <span m='67100'>refer</span> <span m='67430'>to</span>
  <span m='67640'>as</span> <span m='67760'>the</span> <span
  m='67850'>fast</span> <span m='68180'>Fourier</span> <span
  m='68540'>transform</span> <span m='69200'>algorithm,</span> <span
  m='70520'>relies,</span> <span m='71210'>for</span> <span m='71450'>its</span>
  <span m='71600'>derivation,</span> <span m='72500'>on</span> <span
  m='72740'>many</span> <span m='72980'>of</span> <span m='73070'>the</span>
  <span m='73190'>properties</span> <span m='73820'>of</span> <span
  m='73910'>the</span> <span m='74000'>discrete</span> <span
  m='74260'>Fourier</span> <span m='74760'>transform.</span> <span
  m='76040'>And</span> <span m='76070'>so,</span> <span m='76340'>in</span>
  <span m='76460'>fact,</span> <span m='77780'>developing</span> <span
  m='78380'>this</span> <span m='78560'>algorithm,</span> <span
  m='79610'>provides</span> <span m='80090'>us</span> <span
  m='80240'>with</span> <span m='80420'>an</span> <span
  m='80510'>opportunity</span> <span m='81860'>to</span> <span
  m='82160'>exercise</span> <span m='83240'>some</span> <span
  m='83510'>of</span> <span m='83570'>the</span> <span
  m='83690'>intuition</span> <span m='84860'>and</span> <span
  m='85250'>some</span> <span m='85490'>of</span> <span m='85580'>the</span>
  <span m='86060'>results</span> <span m='86720'>related</span> <span
  m='87260'>to</span> <span m='87440'>discrete</span> <span
  m='87800'>Fourier</span> <span m='88220'>transforms.</span> </p><p><span
  m='90750'>Of</span> <span m='91260'>much</span> <span m='91530'>more</span>
  <span m='91740'>practical</span> <span m='92310'>importance</span> <span
  m='93080'>is</span> <span m='93240'>the</span> <span m='93360'>fact</span>
  <span m='93900'>that</span> <span m='94500'>the</span> <span
  m='95300'>fast</span> <span m='95660'>Fourier</span> <span
  m='95970'>transform</span> <span m='96600'>algorithm,</span> <span
  m='97410'>which</span> <span m='97620'>we'll</span> <span m='97740'>be</span>
  <span m='97890'>presenting,</span> <span m='99180'>is</span> <span
  m='99810'>a</span> <span m='100440'>highly</span> <span
  m='100950'>efficient</span> <span m='101460'>algorithm</span> <span
  m='102270'>for</span> <span m='102660'>computing</span> <span
  m='103350'>the</span> <span m='103470'>discrete</span> <span
  m='103860'>Fourier</span> <span m='104250'>transform.</span> <span
  m='105660'>And</span> <span m='105690'>in</span> <span m='105810'>fact,</span>
  <span m='106450'>as</span> <span m='106590'>we'll</span> <span
  m='106740'>see,</span> <span m='107880'>it</span> <span m='108390'>is</span>
  <span m='108870'>orders</span> <span m='109470'>of</span> <span
  m='109680'>magnitude</span> <span m='110730'>more</span> <span
  m='110940'>efficient</span> <span m='111990'>than</span> <span
  m='112440'>a</span> <span m='112620'>straightforward</span> <span
  m='113580'>direct</span> <span m='113970'>computation</span> <span
  m='114840'>of</span> <span m='114930'>the</span> <span
  m='115020'>discrete</span> <span m='115410'>Fourier</span> <span
  m='115800'>transform.</span> </p><p><span m='117500'>Now,</span> <span
  m='119400'>We've</span> <span m='119610'>indicated</span> <span
  m='120390'>in</span> <span m='120570'>previous</span> <span
  m='121080'>lectures,</span> <span m='121980'>and</span> <span
  m='122520'>you</span> <span m='122730'>can</span> <span m='122880'>well</span>
  <span m='123090'>imagine</span> <span m='124230'>that</span> <span
  m='124620'>this</span> <span m='124830'>is</span> <span
  m='124980'>true,</span> <span m='125880'>that</span> <span
  m='126240'>there</span> <span m='126690'>are</span> <span
  m='126960'>many</span> <span m='127260'>contexts</span> <span
  m='128310'>in</span> <span m='128460'>which</span> <span m='128910'>we</span>
  <span m='129120'>would</span> <span m='129539'>want</span> <span
  m='129810'>to</span> <span m='129960'>explicitly</span> <span
  m='130889'>compute</span> <span m='131340'>the</span> <span
  m='131460'>discrete</span> <span m='131850'>Fourier</span> <span
  m='132240'>transform.</span> <span m='133470'>For</span> <span
  m='133650'>example,</span> <span m='134370'>obviously,</span> <span
  m='135210'>in</span> <span m='135450'>spectral</span> <span
  m='135930'>analysis</span> <span m='136710'>of</span> <span
  m='136980'>discrete</span> <span m='137370'>time</span> <span
  m='137880'>data,</span> <span m='138750'>we</span> <span
  m='138900'>would</span> <span m='139050'>want</span> <span
  m='139260'>to</span> <span m='139320'>use</span> <span m='139680'>the</span>
  <span m='140370'>computation</span> <span m='141150'>of</span> <span
  m='141210'>the</span> <span m='141330'>discrete</span> <span
  m='141660'>Fourier</span> <span m='142110'>transform.</span> <span
  m='143400'>And</span> <span m='144090'>we've</span> <span
  m='144300'>seen</span> <span m='144600'>also</span> <span
  m='145440'>that</span> <span m='145800'>the</span> <span
  m='145950'>discrete</span> <span m='146310'>Fourier</span> <span
  m='146700'>transform</span> <span m='148020'>can</span> <span
  m='148200'>be</span> <span m='148320'>used</span> <span m='148830'>for</span>
  <span m='149190'>the</span> <span m='149340'>implementation</span> <span
  m='150420'>of</span> <span m='151020'>finite</span> <span
  m='151410'>impulse</span> <span m='151830'>response</span> <span
  m='152430'>digital</span> <span m='152790'>filters,</span> <span
  m='153300'>or</span> <span m='153450'>more</span> <span
  m='153630'>generally,</span> <span m='154590'>can</span> <span
  m='154740'>be</span> <span m='154860'>used</span> <span m='155160'>to</span>
  <span m='155280'>implement</span> <span m='155730'>a</span> <span
  m='155790'>convolution.</span> </p><p><span m='158440'>It</span> <span
  m='158770'>will</span> <span m='159100'>turn</span> <span
  m='159460'>out</span> <span m='160030'>that</span> <span
  m='160450'>because</span> <span m='160930'>of</span> <span
  m='161020'>the</span> <span m='161110'>efficiency</span> <span
  m='162160'>of</span> <span m='163150'>the</span> <span
  m='163600'>algorithm</span> <span m='164650'>that</span> <span
  m='164860'>we'll</span> <span m='165040'>be</span> <span
  m='165160'>discussing</span> <span m='166060'>in</span> <span
  m='166210'>these</span> <span m='166420'>lectures,</span> <span
  m='167550'>it,</span> <span m='167870'>in</span> <span m='168190'>fact,</span>
  <span m='169580'>in</span> <span m='169660'>many</span> <span
  m='169930'>cases</span> <span m='171220'>is</span> <span
  m='171640'>more</span> <span m='171940'>efficient</span> <span
  m='173200'>to</span> <span m='173530'>implement</span> <span
  m='174040'>the</span> <span m='174130'>convolution</span> <span
  m='175540'>by</span> <span m='175900'>explicitly</span> <span
  m='176680'>computing</span> <span m='177610'>a</span> <span
  m='177700'>discrete</span> <span m='178120'>Fourier</span> <span
  m='178510'>transform,</span> <span m='179800'>multiplying</span> <span
  m='180460'>the</span> <span m='180550'>transforms</span> <span
  m='181240'>together,</span> <span m='181870'>and</span> <span
  m='182050'>then</span> <span m='182230'>Inverse</span> <span
  m='182680'>transforming</span> <span m='183400'>the</span> <span
  m='183490'>result.</span> <span m='184330'>Of</span> <span
  m='184480'>course,</span> <span m='185210'>keeping</span> <span
  m='185440'>track</span> <span m='185800'>of</span> <span m='185890'>the</span>
  <span m='186010'>fact</span> <span m='186430'>that</span> <span
  m='186690'>that</span> <span m='187060'>implements</span> <span
  m='187540'>a</span> <span m='187570'>circular</span> <span
  m='188050'>convolution</span> <span m='188860'>and</span> <span
  m='189010'>doing</span> <span m='189460'>the</span> <span
  m='189550'>necessary</span> <span m='190180'>things</span> <span
  m='190480'>that</span> <span m='190600'>need</span> <span m='190780'>to</span>
  <span m='190900'>be</span> <span m='191050'>done</span> <span
  m='191830'>if</span> <span m='192070'>we're</span> <span
  m='192220'>interested</span> <span m='192700'>in</span> <span
  m='192820'>a</span> <span m='192880'>linear</span> <span
  m='193210'>convolution.</span> </p><p><span m='195840'>Now,</span> <span
  m='196040'>I'd</span> <span m='196220'>like,</span> <span
  m='196700'>just</span> <span m='197450'>briefly,</span> <span
  m='198260'>to</span> <span m='198440'>remark</span> <span
  m='199190'>that</span> <span m='200330'>this</span> <span
  m='200570'>algorithm,</span> <span m='201590'>this--</span> <span
  m='201980'>actually,</span> <span m='202370'>it's</span> <span
  m='202490'>a</span> <span m='202550'>class</span> <span m='202910'>of</span>
  <span m='203030'>algorithms,</span> <span m='203940'>which</span> <span
  m='204140'>I'll</span> <span m='204260'>refer</span> <span
  m='204590'>to</span> <span m='204920'>as</span> <span m='205130'>the</span>
  <span m='205220'>fast</span> <span m='205520'>Fourier</span> <span
  m='205820'>transform</span> <span m='206360'>algorithms,</span> <span
  m='208800'>were</span> <span m='209520'>a</span> <span m='210120'>major</span>
  <span m='210570'>landmark</span> <span m='211590'>in</span> <span
  m='212040'>the</span> <span m='212160'>development</span> <span
  m='213150'>of</span> <span m='213690'>the</span> <span m='213810'>field</span>
  <span m='214260'>of</span> <span m='214320'>digital</span> <span
  m='214680'>signal</span> <span m='215040'>processing</span> <span
  m='215820'>in</span> <span m='215940'>its</span> <span
  m='216060'>present</span> <span m='216420'>form.</span> <span
  m='217770'>The</span> <span m='217950'>algorithm,</span> <span
  m='219090'>one</span> <span m='219330'>of</span> <span m='219450'>the</span>
  <span m='219660'>forms</span> <span m='220020'>of</span> <span
  m='220110'>the</span> <span m='220260'>algorithm,</span> <span
  m='221400'>was</span> <span m='222030'>disclosed</span> <span
  m='222780'>in</span> <span m='222900'>a</span> <span m='222960'>paper</span>
  <span m='223350'>by</span> <span m='223800'>Cooley</span> <span
  m='224190'>and</span> <span m='224280'>Tukey</span> <span m='224880'>in</span>
  <span m='225030'>1965.</span> <span m='227230'>And</span> <span
  m='227850'>it</span> <span m='228000'>turns</span> <span
  m='228360'>out,</span> <span m='229350'>though,</span> <span
  m='230010'>that</span> <span m='231270'>the</span> <span
  m='231660'>algorithm</span> <span m='232380'>has,</span> <span
  m='232830'>in</span> <span m='232920'>a</span> <span m='232980'>variety</span>
  <span m='233550'>of</span> <span m='233610'>forms,</span> <span
  m='234240'>been</span> <span m='234450'>reinvented</span> <span
  m='235230'>several</span> <span m='235710'>times</span> <span
  m='236160'>over</span> <span m='236370'>the</span> <span
  m='236460'>past</span> <span m='236790'>20</span> <span m='237090'>or</span>
  <span m='237180'>30</span> <span m='237510'>years.</span> <span
  m='238870'>So</span> <span m='239610'>it</span> <span m='239760'>is</span>
  <span m='239850'>mainly</span> <span m='240240'>this</span> <span
  m='240420'>class</span> <span m='240750'>of</span> <span
  m='240840'>algorithms</span> <span m='241860'>that</span> <span
  m='242550'>we'll</span> <span m='242670'>be</span> <span
  m='242790'>talking</span> <span m='243240'>about</span> <span
  m='243780'>in</span> <span m='243930'>the</span> <span m='243990'>next</span>
  <span m='244200'>several</span> <span m='244590'>lectures.</span> <span
  m='245640'>And</span> <span m='246300'>I</span> <span m='246480'>stress</span>
  <span m='246840'>again</span> <span m='247800'>that</span> <span
  m='248250'>one</span> <span m='248490'>of</span> <span m='248640'>the</span>
  <span m='249210'>primary</span> <span m='251230'>reasons</span> <span
  m='252100'>why</span> <span m='252700'>this</span> <span m='252910'>is</span>
  <span m='253000'>so</span> <span m='253300'>important</span> <span
  m='254500'>is</span> <span m='255010'>because</span> <span
  m='255700'>of</span> <span m='256060'>the</span> <span
  m='256240'>rather</span> <span m='256570'>dramatic</span> <span
  m='257200'>improvements</span> <span m='257920'>in</span> <span
  m='258040'>efficiency</span> <span m='259240'>that</span> <span
  m='259390'>it</span> <span m='259480'>offers</span> <span
  m='260079'>over</span> <span m='260680'>just</span> <span m='260950'>a</span>
  <span m='261070'>straightforward</span> <span m='261850'>computation</span>
  <span m='262780'>of</span> <span m='262960'>the</span> <span
  m='263050'>discrete</span> <span m='263440'>Fourier</span> <span
  m='263800'>transform.</span> </p><p><span m='265630'>Well,</span> <span
  m='266110'>let's</span> <span m='266500'>look</span> <span
  m='266740'>specifically</span> <span m='267670'>at</span> <span
  m='268120'>what's</span> <span m='268390'>involved</span> <span
  m='268990'>in</span> <span m='269080'>the</span> <span
  m='269170'>computation</span> <span m='270160'>of</span> <span
  m='270850'>the</span> <span m='270970'>discrete</span> <span
  m='271360'>Fourier</span> <span m='271760'>transform.</span> <span
  m='274070'>The</span> <span m='274180'>discrete</span> <span
  m='274540'>Fourier</span> <span m='274930'>transform,</span> <span
  m='275840'>as</span> <span m='276160'>we</span> <span m='276280'>know,</span>
  <span m='276880'>is</span> <span m='277060'>given</span> <span
  m='277960'>by</span> <span m='278470'>the</span> <span m='278590'>sum</span>
  <span m='279160'>of</span> <span m='279520'>x</span> <span
  m='279820'>sub</span> <span m='279940'>n</span> <span m='280240'>times</span>
  <span m='280570'>W</span> <span m='280930'>sub n</span> <span
  m='281980'>to</span> <span m='282070'>the</span> <span m='282220'>nk,</span>
  <span m='283870'>where</span> <span m='284200'>W</span> <span m='284670'>sub
  n</span> <span m='285610'>is</span> <span m='285760'>the</span> <span
  m='285850'>complex</span> <span m='286420'>exponential,</span> <span
  m='287230'>e</span> <span m='287470'>to</span> <span m='287530'>the</span>
  <span m='287620'>minus</span> <span m='288010'>j,</span> <span
  m='288385'>2</span> <span m='288760'>pi</span> <span m='289300'>over</span>
  <span m='289570'>capital</span> <span m='290080'>n.</span> <span
  m='291400'>So</span> <span m='292360'>it</span> <span m='292540'>is</span>
  <span m='293020'>this</span> <span m='293260'>expression</span> <span
  m='294220'>that</span> <span m='294520'>we</span> <span m='294640'>want</span>
  <span m='294820'>to</span> <span m='294910'>compute.</span> <span
  m='296620'>Or</span> <span m='296920'>equivalently,</span> <span
  m='297850'>there</span> <span m='298240'>is</span> <span m='298840'>the</span>
  <span m='299050'>inverse</span> <span m='299500'>discrete</span> <span
  m='299920'>Fourier</span> <span m='300340'>transform</span> <span
  m='301750'>given</span> <span m='302320'>by</span> <span m='302950'>1</span>
  <span m='303190'>over</span> <span m='303430'>capital</span> <span
  m='303970'>N</span> <span m='304390'>times</span> <span m='304750'>the</span>
  <span m='304840'>sum</span> <span m='305350'>of</span> <span
  m='305680'>x</span> <span m='305980'>of</span> <span m='306100'>k,</span>
  <span m='306520'>the</span> <span m='306610'>DFT,</span> <span
  m='307930'>times</span> <span m='308290'>W sub N</span> <span
  m='309370'>to</span> <span m='309490'>the</span> <span m='309580'>minus</span>
  <span m='309970'>nk.</span> </p><p><span m='311320'>Now,</span> <span
  m='312400'>hopefully</span> <span m='312910'>you</span> <span
  m='313060'>recall</span> <span m='313630'>from</span> <span
  m='313990'>the</span> <span m='314140'>discussion</span> <span
  m='314680'>of</span> <span m='314770'>the</span> <span
  m='314860'>discrete</span> <span m='315220'>Fourier</span> <span
  m='315640'>transform,</span> <span m='316960'>that</span> <span
  m='318040'>the</span> <span m='318280'>inverse</span> <span
  m='319060'>DFT</span> <span m='320080'>is</span> <span
  m='320320'>really</span> <span m='320650'>the</span> <span
  m='320740'>same</span> <span m='321100'>as</span> <span m='321220'>the</span>
  <span m='321310'>discrete</span> <span m='321730'>Fourier</span> <span
  m='322150'>transform</span> <span m='323110'>if</span> <span
  m='323650'>we</span> <span m='323830'>reverse</span> <span
  m='324280'>the</span> <span m='324400'>result</span> <span
  m='324680'>in</span> <span m='324960'>N,</span> <span m='325210'>et
  cetera.</span> <span m='326200'>In</span> <span m='326320'>other</span> <span
  m='326530'>words,</span> <span m='327940'>computation</span> <span
  m='329020'>of</span> <span m='329320'>the</span> <span
  m='329500'>inverse</span> <span m='330010'>DFT</span> <span
  m='331420'>is</span> <span m='332050'>really</span> <span
  m='332950'>essentially</span> <span m='333670'>the</span> <span
  m='333760'>same</span> <span m='334750'>as</span> <span m='335020'>the</span>
  <span m='335140'>computation</span> <span m='336100'>of</span> <span
  m='336760'>the</span> <span m='336880'>DFT.</span> <span m='338020'>So</span>
  <span m='338800'>whereas</span> <span m='339190'>we'll</span> <span
  m='339310'>be</span> <span m='339460'>referring</span> <span
  m='339910'>the</span> <span m='340000'>discussion</span> <span
  m='340690'>to</span> <span m='340840'>the</span> <span
  m='340930'>computation</span> <span m='341830'>of</span> <span
  m='342010'>the</span> <span m='342100'>discrete</span> <span
  m='342490'>Fourier</span> <span m='342910'>transform,</span> <span
  m='344380'>essentially</span> <span m='345070'>everything</span> <span
  m='345580'>that</span> <span m='345700'>we</span> <span m='345850'>say</span>
  <span m='346690'>applies</span> <span m='347230'>also</span> <span
  m='347710'>to</span> <span m='348670'>a</span> <span
  m='348760'>computation</span> <span m='349780'>of</span> <span
  m='350410'>the</span> <span m='350560'>inverse</span> <span
  m='351010'>DFT.</span> </p><p><span m='353300'>Well,</span> <span
  m='353750'>let's</span> <span m='354050'>look,</span> <span
  m='354480'>first</span> <span m='354740'>of</span> <span
  m='354890'>all,</span> <span m='355440'>at</span> <span m='355910'>what</span>
  <span m='356360'>would</span> <span m='356570'>be</span> <span
  m='356750'>involved</span> <span m='357620'>in</span> <span
  m='357890'>just</span> <span m='358370'>a</span> <span
  m='358640'>straightforward</span> <span m='359810'>computation</span> <span
  m='360860'>of</span> <span m='361040'>the</span> <span
  m='361160'>discrete</span> <span m='361520'>Fourier</span> <span
  m='361910'>transform.</span> <span m='363200'>Basically</span> <span
  m='363890'>what</span> <span m='364070'>this</span> <span
  m='364250'>expression</span> <span m='364820'>says</span> <span
  m='365900'>is</span> <span m='366290'>to</span> <span m='366410'>take</span>
  <span m='366740'>x</span> <span m='366970'>of</span> <span
  m='367110'>n,</span> <span m='368570'>multiply</span> <span
  m='368900'>it</span> <span m='369230'>by</span> <span m='369500'>the</span>
  <span m='369620'>appropriate</span> <span m='370130'>powers</span> <span
  m='370580'>of</span> <span m='370670'>W,</span> <span m='371810'>and</span>
  <span m='371990'>then</span> <span m='372350'>sum</span> <span
  m='372780'>the</span> <span m='372800'>result</span> <span
  m='373520'>from</span> <span m='373760'>0</span> <span m='374330'>to</span>
  <span m='374480'>capital</span> <span m='374960'>N</span> <span
  m='375380'>minus</span> <span m='375770'>1.</span> <span m='376810'>And</span>
  <span m='377360'>so,</span> <span m='377600'>we</span> <span
  m='377750'>basically</span> <span m='378350'>have</span> <span
  m='378590'>that</span> <span m='378800'>set</span> <span m='379010'>of</span>
  <span m='379100'>operations</span> <span m='380300'>to</span> <span
  m='380420'>carry</span> <span m='380870'>out</span> <span
  m='381350'>for</span> <span m='381860'>each</span> <span
  m='382550'>value</span> <span m='383150'>of</span> <span m='383300'>k</span>
  <span m='384320'>for</span> <span m='384470'>which</span> <span
  m='384740'>we're</span> <span m='384920'>computing</span> <span
  m='385490'>the</span> <span m='385580'>discrete</span> <span
  m='385970'>Fourier</span> <span m='386390'>transform.</span> </p><p><span
  m='388190'>Well,</span> <span m='388670'>if</span> <span m='388850'>we</span>
  <span m='388970'>think</span> <span m='389240'>of</span> <span
  m='389360'>x</span> <span m='389600'>of</span> <span m='389660'>n</span> <span
  m='389870'>as</span> <span m='389960'>being</span> <span
  m='390230'>complex,</span> <span m='391040'>which</span> <span
  m='391400'>in</span> <span m='391520'>the</span> <span m='391580'>most</span>
  <span m='391820'>general</span> <span m='392210'>case</span> <span
  m='392540'>it</span> <span m='392630'>will</span> <span m='392870'>be,</span>
  <span m='394190'>then</span> <span m='395150'>we</span> <span
  m='395330'>have</span> <span m='396020'>in</span> <span m='396680'>the</span>
  <span m='397610'>direct</span> <span m='398420'>computation</span> <span
  m='399620'>of</span> <span m='400220'>the</span> <span m='400310'>DFT,</span>
  <span m='402440'>we</span> <span m='402590'>have</span> <span
  m='402830'>to</span> <span m='402950'>form</span> <span m='403250'>the</span>
  <span m='403340'>product,</span> <span m='404180'>x</span> <span
  m='404450'>of</span> <span m='404600'>n</span> <span m='404900'>times</span>
  <span m='405230'>W sub N</span> <span m='406340'>to</span> <span
  m='406460'>the</span> <span m='406610'>nk.</span> <span m='408440'>And</span>
  <span m='408620'>what</span> <span m='408800'>that</span> <span
  m='409010'>involves</span> <span m='410270'>is</span> <span
  m='411050'>one</span> <span m='411620'>complex</span> <span
  m='412190'>multiplication.</span> <span m='414860'>This</span> <span
  m='415040'>is</span> <span m='415160'>a</span> <span m='415190'>complex</span>
  <span m='415730'>number.</span> <span m='416190'>That's</span> <span
  m='416360'>a</span> <span m='416420'>complex</span> <span
  m='416990'>number.</span> <span m='417800'>Multiplying</span> <span
  m='418460'>the</span> <span m='418550'>two</span> <span m='418970'>is</span>
  <span m='419180'>then</span> <span m='419360'>one</span> <span
  m='419570'>complex</span> <span m='420140'>multiply,</span> <span
  m='421400'>or</span> <span m='421580'>equivalently,</span> <span
  m='422810'>four</span> <span m='423710'>real</span> <span
  m='424490'>multiplies</span> <span m='425470'>and</span> <span
  m='425590'>two</span> <span m='426230'>real</span> <span
  m='426690'>adds.</span> </p><p><span m='429680'>OK,</span> <span
  m='430070'>well</span> <span m='430700'>now</span> <span
  m='431330'>that</span> <span m='431660'>is</span> <span m='432080'>to</span>
  <span m='432230'>form</span> <span m='432560'>one</span> <span
  m='432800'>term</span> <span m='433280'>in</span> <span m='433430'>the</span>
  <span m='433520'>sum.</span> <span m='435410'>We</span> <span
  m='435560'>have</span> <span m='437820'>n</span> <span m='439230'>terms</span>
  <span m='439910'>altogether</span> <span m='440580'>in</span> <span
  m='440670'>the</span> <span m='440760'>sum,</span> <span m='441270'>or</span>
  <span m='441480'>capital</span> <span m='442020'>N</span> <span
  m='442680'>minus</span> <span m='443040'>one</span> <span
  m='443430'>additions,</span> <span m='444090'>complex</span> <span
  m='444630'>additions,</span> <span m='445800'>to</span> <span
  m='446100'>implement</span> <span m='446750'>in</span> <span
  m='446910'>the</span> <span m='447000'>sum.</span> <span m='447990'>So</span>
  <span m='448710'>to</span> <span m='448860'>compute</span> <span
  m='450720'>the</span> <span m='451650'>DFT</span> <span m='452940'>for</span>
  <span m='453120'>one</span> <span m='453360'>value</span> <span
  m='453810'>of</span> <span m='453940'>k</span> <span m='455680'>will</span>
  <span m='455890'>require</span> <span m='457180'>capital</span> <span
  m='457690'>N</span> <span m='458380'>complex</span> <span
  m='458920'>multiplications</span> <span m='460660'>and</span> <span
  m='460870'>capital</span> <span m='461350'>N</span> <span m='461500'>minus
  1</span> <span m='461920'>complex</span> <span m='463210'>additions.</span>
  <span m='465100'>Well</span> <span m='465730'>to</span> <span
  m='465880'>compute</span> <span m='466270'>the</span> <span
  m='466360'>discrete</span> <span m='466690'>Fourier</span> <span
  m='467020'>transform</span> <span m='468130'>for</span> <span
  m='468790'>all</span> <span m='469120'>capital</span> <span
  m='469630'>N</span> <span m='469840'>values</span> <span m='470590'>of</span>
  <span m='470770'>k</span> <span m='472600'>requires</span> <span
  m='473260'>then</span> <span m='473990'>n</span> <span
  m='474220'>squared</span> <span m='475240'>complex</span> <span
  m='475810'>multiplies</span> <span m='477250'>and</span> <span
  m='477550'>n</span> <span m='478180'>times</span> <span m='478810'>n</span>
  <span m='479050'>minus 1</span> <span m='479470'>complex</span> <span
  m='480910'>additions.</span> <span m='481940'>Or</span> <span
  m='483880'>basically</span> <span m='484780'>if</span> <span
  m='484990'>capital</span> <span m='485480'>N</span> <span m='485650'>is</span>
  <span m='486550'>any</span> <span m='486820'>reasonable</span> <span
  m='487360'>number,</span> <span m='488200'>we</span> <span
  m='488320'>can</span> <span m='488440'>approximate</span> <span
  m='489130'>this</span> <span m='489610'>as</span> <span m='490000'>N</span>
  <span m='490230'>squared.</span> <span m='491380'>And</span> <span
  m='491530'>so,</span> <span m='492190'>approximately,</span> <span
  m='493690'>the</span> <span m='493780'>computation</span> <span
  m='494710'>involved</span> <span m='495730'>is</span> <span
  m='496060'>on</span> <span m='496240'>the</span> <span m='496390'>order</span>
  <span m='497020'>of</span> <span m='497770'>capital</span> <span
  m='498250'>N</span> <span m='498460'>squared</span> <span
  m='499480'>complex</span> <span m='500500'>multiplies</span> <span
  m='501460'>and</span> <span m='501640'>adds.</span> </p><p><span
  m='503680'>Now,</span> <span m='504160'>a</span> <span m='504220'>few</span>
  <span m='504460'>remarks</span> <span m='505000'>here.</span> <span
  m='505530'>One,</span> <span m='506140'>first</span> <span
  m='506500'>of</span> <span m='506620'>all,</span> <span m='507010'>is</span>
  <span m='507310'>that</span> <span m='508240'>in</span> <span
  m='508990'>counting</span> <span m='509410'>up</span> <span
  m='509590'>the</span> <span m='509680'>number</span> <span
  m='509950'>of</span> <span m='510040'>complex</span> <span
  m='510580'>multiplies</span> <span m='511240'>and</span> <span
  m='511360'>adds,</span> <span m='512650'>we</span> <span
  m='513309'>didn't</span> <span m='513610'>particularly</span> <span
  m='514210'>take</span> <span m='514520'>account</span> <span
  m='515080'>of</span> <span m='515289'>multiplies</span> <span
  m='516640'>by</span> <span m='517450'>unity.</span> <span
  m='518140'>For</span> <span m='518350'>example,</span> <span
  m='518860'>when</span> <span m='519039'>k</span> <span m='519340'>is</span>
  <span m='519490'>equal</span> <span m='519789'>to</span> <span
  m='519909'>0,</span> <span m='520929'>W</span> <span m='521260'>sub N</span>
  <span m='521710'>to</span> <span m='521830'>the</span> <span
  m='521980'>nk</span> <span m='522390'>is</span> <span m='522520'>equal</span>
  <span m='522760'>to</span> <span m='522909'>unity,</span> <span
  m='523809'>and</span> <span m='524169'>we,</span> <span m='524380'>in</span>
  <span m='524500'>fact,</span> <span m='524800'>wouldn't</span> <span
  m='525070'>have</span> <span m='525370'>to</span> <span
  m='525850'>carry</span> <span m='526270'>out</span> <span m='526780'>a</span>
  <span m='526840'>multiplication.</span> <span m='528400'>But</span> <span
  m='529540'>there</span> <span m='529960'>are</span> <span m='531360'>a</span>
  <span m='531460'>small</span> <span m='531880'>enough</span> <span
  m='532150'>number</span> <span m='532660'>of</span> <span
  m='532810'>those</span> <span m='533080'>cases</span> <span
  m='533770'>in</span> <span m='533920'>comparison</span> <span
  m='534640'>to</span> <span m='534760'>all</span> <span m='535000'>of</span>
  <span m='535090'>the</span> <span m='535180'>multiplies</span> <span
  m='535870'>involved</span> <span m='536920'>so</span> <span
  m='537160'>that</span> <span m='537820'>this</span> <span m='538120'>is</span>
  <span m='538390'>generally</span> <span m='539260'>an</span> <span
  m='539410'>indication</span> <span m='540340'>of</span> <span
  m='540610'>what</span> <span m='540760'>the</span> <span
  m='540880'>dependence</span> <span m='541720'>of</span> <span
  m='541870'>the</span> <span m='541960'>computation</span> <span
  m='542770'>is</span> <span m='543130'>on N.</span> </p><p><span
  m='544990'>Second</span> <span m='545350'>of</span> <span
  m='545470'>all,</span> <span m='546070'>and</span> <span
  m='546220'>this</span> <span m='546430'>will</span> <span
  m='547120'>occur</span> <span m='547450'>throughout</span> <span
  m='548800'>this</span> <span m='549190'>next</span> <span
  m='549430'>set</span> <span m='549610'>of</span> <span
  m='549730'>lectures,</span> <span m='551330'>we</span> <span
  m='551620'>are</span> <span m='552010'>tying</span> <span m='552850'>a</span>
  <span m='552940'>discussion</span> <span m='553810'>of</span> <span
  m='553960'>the</span> <span m='554050'>computational</span> <span
  m='555040'>complexity</span> <span m='555880'>or</span> <span
  m='556030'>efficiency</span> <span m='557680'>to</span> <span
  m='558190'>counting</span> <span m='559030'>the</span> <span
  m='559150'>number</span> <span m='559630'>of</span> <span
  m='559810'>complex</span> <span m='560710'>multiplies</span> <span
  m='561400'>and</span> <span m='561490'>adds</span> <span
  m='562390'>that</span> <span m='562870'>are</span> <span
  m='563170'>involved</span> <span m='563860'>in</span> <span
  m='563950'>the</span> <span m='564010'>computation</span> <span
  m='564760'>of</span> <span m='564880'>x</span> <span m='565090'>of</span>
  <span m='565210'>k,</span> <span m='566020'>and</span> <span
  m='566140'>not</span> <span m='566320'>particularly</span> <span
  m='566920'>focusing</span> <span m='567730'>on</span> <span
  m='568060'>other</span> <span m='568360'>issues,</span> <span
  m='568820'>such</span> <span m='568960'>as</span> <span
  m='569080'>indexing,</span> <span m='569680'>bookkeeping,</span> <span
  m='570250'>et cetera.</span> <span m='571270'>So</span> <span
  m='571630'>in</span> <span m='571810'>discussing</span> <span
  m='572470'>the</span> <span m='572560'>computational</span> <span
  m='573370'>complexity</span> <span m='574060'>or</span> <span
  m='574210'>efficiency,</span> <span m='575470'>we'll</span> <span
  m='575620'>tend</span> <span m='576220'>to</span> <span
  m='576370'>refer</span> <span m='577510'>to</span> <span m='578320'>the</span>
  <span m='578440'>number</span> <span m='579100'>of</span> <span
  m='579190'>multiplications</span> <span m='580240'>and</span> <span
  m='580360'>adds</span> <span m='581050'>that</span> <span
  m='581200'>are</span> <span m='581290'>involved</span> <span
  m='581920'>in</span> <span m='582040'>implementing</span> <span
  m='582580'>the</span> <span m='582770'>transform.</span> </p><p><span
  m='585320'>Well,</span> <span m='586310'>we</span> <span
  m='586460'>have</span> <span m='586730'>then</span> <span m='587270'>a</span>
  <span m='587330'>direct</span> <span m='587690'>computation,</span> <span
  m='588980'>which</span> <span m='589220'>involves</span> <span
  m='589850'>on</span> <span m='590030'>the</span> <span m='590150'>order</span>
  <span m='590600'>of</span> <span m='590990'>n</span> <span
  m='591200'>squared</span> <span m='591980'>complex</span> <span
  m='592520'>multiplies</span> <span m='593180'>and</span> <span
  m='593300'>adds.</span> <span m='594590'>And</span> <span
  m='595430'>the</span> <span m='595700'>important</span> <span
  m='596240'>point</span> <span m='596600'>then</span> <span
  m='596930'>is</span> <span m='597140'>its</span> <span
  m='597290'>dependency</span> <span m='598100'>on</span> <span
  m='598310'>N,</span> <span m='599000'>namely</span> <span m='599450'>N</span>
  <span m='599630'>squared.</span> <span m='601190'>There</span> <span
  m='602060'>are</span> <span m='602240'>a</span> <span
  m='602270'>variety</span> <span m='602810'>of</span> <span
  m='602930'>algorithms</span> <span m='603830'>that</span> <span
  m='604220'>have</span> <span m='605000'>been</span> <span
  m='605150'>known</span> <span m='605510'>for</span> <span
  m='605690'>some</span> <span m='605960'>time,</span> <span
  m='606350'>in</span> <span m='606440'>fact,</span> <span m='607340'>and</span>
  <span m='608090'>ones</span> <span m='608450'>that</span> <span
  m='608600'>you</span> <span m='608720'>can</span> <span
  m='608870'>generate</span> <span m='609320'>yourself</span> <span
  m='610040'>by</span> <span m='610760'>taking</span> <span
  m='611120'>advantage</span> <span m='611690'>of</span> <span
  m='611750'>various</span> <span m='612170'>symmetry</span> <span
  m='612620'>properties</span> <span m='613430'>of</span> <span
  m='613820'>these</span> <span m='614000'>complex</span> <span
  m='614570'>exponentials.</span> <span m='616220'>To</span> <span
  m='616730'>reduce</span> <span m='618260'>the</span> <span
  m='618380'>constant</span> <span m='619190'>of</span> <span
  m='619340'>proportionality</span> <span m='621200'>on</span> <span
  m='621710'>the</span> <span m='621830'>computation,</span> <span
  m='622880'>that</span> <span m='623090'>is,</span> <span m='623990'>to</span>
  <span m='624410'>make</span> <span m='624650'>the</span> <span
  m='624740'>computation</span> <span m='626120'>perhaps</span> <span
  m='626960'>not</span> <span m='627200'>involve</span> <span
  m='627710'>N</span> <span m='627920'>squared</span> <span
  m='628310'>multiplies</span> <span m='628970'>and</span> <span
  m='629060'>adds</span> <span m='629780'>but</span> <span
  m='629960'>only</span> <span m='630560'>1/2</span> <span m='631070'>N</span>
  <span m='631280'>squared</span> <span m='631820'>or</span> <span
  m='631970'>1/4</span> <span m='632420'>N</span> <span
  m='632570'>squared.</span> <span m='633650'>But</span> <span
  m='634160'>still,</span> <span m='634700'>in</span> <span
  m='634850'>cases</span> <span m='635330'>like</span> <span
  m='635600'>that,</span> <span m='636410'>the</span> <span
  m='637100'>algorithms</span> <span m='637940'>involved</span> <span
  m='638450'>basically</span> <span m='639170'>fooling</span> <span
  m='639590'>around</span> <span m='640460'>with</span> <span
  m='641300'>a</span> <span m='641540'>constant</span> <span
  m='642050'>of</span> <span m='642140'>proportionality</span> <span
  m='643460'>out</span> <span m='643670'>in</span> <span
  m='643760'>front,</span> <span m='645530'>whereas</span> <span
  m='646160'>the</span> <span m='646640'>main</span> <span
  m='646940'>dependence</span> <span m='647720'>on</span> <span
  m='647930'>N,</span> <span m='648710'>the</span> <span m='648800'>size</span>
  <span m='649190'>of</span> <span m='649280'>the</span> <span
  m='649500'>transform,</span> <span m='650360'>remains</span> <span
  m='650780'>the</span> <span m='650870'>same.</span> </p><p><span
  m='653430'>And</span> <span m='654360'>you</span> <span m='654550'>can,</span>
  <span m='654810'>I think,</span> <span m='655110'>convince</span> <span
  m='655560'>yourself</span> <span m='656160'>rather</span> <span
  m='656490'>quickly</span> <span m='657180'>with</span> <span
  m='657510'>some</span> <span m='657780'>fairly</span> <span
  m='659880'>standard</span> <span m='661530'>computers</span> <span
  m='663000'>that</span> <span m='663630'>if,</span> <span m='663870'>in</span>
  <span m='663990'>fact,</span> <span m='664410'>the</span> <span
  m='664530'>computation</span> <span m='666210'>to</span> <span
  m='666330'>be</span> <span m='666450'>done</span> <span m='667650'>is</span>
  <span m='667920'>proportional</span> <span m='668580'>to</span> <span
  m='668700'>N</span> <span m='668910'>squared,</span> <span
  m='670170'>then</span> <span m='670860'>very</span> <span
  m='671190'>large</span> <span m='671550'>transforms</span> <span
  m='672690'>certainly</span> <span m='673380'>aren't</span> <span
  m='673710'>possible</span> <span m='674490'>in</span> <span
  m='674670'>very</span> <span m='674940'>reasonable</span> <span
  m='675450'>amounts</span> <span m='675810'>of</span> <span
  m='675900'>time.</span> <span m='677230'>For</span> <span
  m='677340'>example,</span> <span m='678160'>if</span> <span
  m='678330'>N</span> <span m='678510'>is</span> <span m='678660'>on</span>
  <span m='678780'>the</span> <span m='678900'>order</span> <span
  m='679200'>of</span> <span m='679320'>1,000,</span> <span
  m='680370'>then</span> <span m='680580'>we're</span> <span
  m='680700'>talking</span> <span m='681180'>about</span> <span
  m='681660'>on</span> <span m='681810'>the</span> <span m='681930'>order</span>
  <span m='682320'>of</span> <span m='682440'>a</span> <span
  m='682500'>million</span> <span m='683340'>complex</span> <span
  m='683910'>multiplies</span> <span m='684570'>and</span> <span
  m='684660'>adds.</span> <span m='685980'>And</span> <span m='687060'>if</span>
  <span m='687450'>we</span> <span m='687870'>assume</span> <span
  m='688260'>that</span> <span m='688410'>one</span> <span m='688620'>of</span>
  <span m='688740'>those</span> <span m='689070'>took,</span> <span
  m='689310'>say,</span> <span m='690360'>two</span> <span
  m='690570'>microseconds</span> <span m='691410'>or</span> <span
  m='691500'>three</span> <span m='691740'>microseconds</span> <span
  m='692490'>to</span> <span m='692580'>implement,</span> <span
  m='693120'>or</span> <span m='693210'>even</span> <span m='693450'>one</span>
  <span m='693660'>microsecond,</span> <span m='694980'>then</span> <span
  m='695310'>clearly</span> <span m='695700'>we're</span> <span
  m='695820'>talking</span> <span m='696180'>about</span> <span
  m='696390'>computation</span> <span m='697170'>on</span> <span
  m='697290'>the</span> <span m='697380'>order</span> <span m='697650'>of</span>
  <span m='697710'>seconds.</span> <span m='698790'>And</span> <span
  m='699420'>you</span> <span m='699600'>can</span> <span
  m='699720'>convince</span> <span m='700080'>yourself</span> <span
  m='700470'>rather</span> <span m='700740'>quickly</span> <span
  m='701220'>that</span> <span m='701340'>the</span> <span
  m='701460'>computation</span> <span m='702270'>grows</span> <span
  m='703350'>very</span> <span m='703650'>fast</span> <span m='704490'>as</span>
  <span m='704940'>N</span> <span m='705120'>increases</span> <span
  m='705750'>from</span> <span m='706350'>1,000</span> <span
  m='706920'>to</span> <span m='707040'>2,000</span> <span m='707760'>to</span>
  <span m='707850'>4,000,</span> <span m='708540'>et</span> <span
  m='708610'>cetera.</span> </p><p><span m='710220'>All</span> <span
  m='710310'>right,</span> <span m='710550'>so</span> <span
  m='710790'>direct</span> <span m='711150'>computation,</span> <span
  m='711590'>the</span> <span m='712110'>dependency</span> <span
  m='712920'>is</span> <span m='713160'>an</span> <span m='713310'>n</span>
  <span m='713520'>squared</span> <span m='714330'>type</span> <span
  m='714630'>of</span> <span m='714720'>dependency.</span> <span
  m='716190'>And</span> <span m='716280'>this</span> <span m='716490'>is</span>
  <span m='716610'>in</span> <span m='716700'>contrast</span> <span
  m='717870'>to</span> <span m='718710'>the</span> <span
  m='718950'>primary</span> <span m='719520'>algorithm</span> <span
  m='720450'>that</span> <span m='720630'>we</span> <span m='720750'>want</span>
  <span m='720960'>to</span> <span m='721020'>discuss,</span> <span
  m='721960'>which</span> <span m='722160'>is</span> <span m='722460'>the</span>
  <span m='722580'>fast</span> <span m='722940'>Fourier</span> <span
  m='723300'>transform</span> <span m='723960'>algorithm.</span> <span
  m='726480'>Basically,</span> <span m='727530'>the</span> <span
  m='727860'>fast</span> <span m='728220'>Fourier</span> <span
  m='728610'>transform</span> <span m='729270'>algorithm</span> <span
  m='731940'>is</span> <span m='732780'>directed</span> <span
  m='733890'>at</span> <span m='734400'>computing</span> <span
  m='735570'>the</span> <span m='735660'>discrete</span> <span
  m='736080'>Fourier</span> <span m='736500'>transform</span> <span
  m='738450'>for</span> <span m='740490'>a</span> <span m='740580'>choice</span>
  <span m='741090'>of</span> <span m='741330'>N,</span> <span
  m='742290'>the</span> <span m='742590'>size</span> <span m='743010'>of</span>
  <span m='743100'>the</span> <span m='743290'>transform,</span> <span
  m='744630'>highly</span> <span m='745110'>composite.</span> <span
  m='746100'>That</span> <span m='746340'>is,</span> <span m='747330'>N</span>
  <span m='748590'>is,</span> <span m='749130'>in</span> <span
  m='749310'>general--</span> <span m='749940'>of</span> <span
  m='750030'>course,</span> <span m='750300'>any</span> <span
  m='750630'>N</span> <span m='751050'>can</span> <span m='751230'>be</span>
  <span m='751350'>represented</span> <span m='752100'>as</span> <span
  m='752250'>a</span> <span m='752310'>product</span> <span m='752790'>of</span>
  <span m='752880'>primes.</span> <span m='754110'>And</span> <span
  m='754230'>as</span> <span m='754450'>we'll</span> <span
  m='754540'>see,</span> <span m='755760'>the</span> <span
  m='756120'>larger</span> <span m='756660'>the</span> <span
  m='756780'>number</span> <span m='757230'>of</span> <span
  m='757350'>primes</span> <span m='758370'>involved</span> <span
  m='759060'>in</span> <span m='759210'>the</span> <span
  m='759400'>decomposition</span> <span m='760290'>of</span> <span
  m='760470'>N,</span> <span m='761430'>the</span> <span
  m='761700'>greater</span> <span m='762210'>the</span> <span
  m='762360'>efficiency</span> <span m='763350'>of</span> <span
  m='764070'>the</span> <span m='764190'>fast</span> <span
  m='764550'>Fourier</span> <span m='764940'>transform</span> <span
  m='765810'>as</span> <span m='765960'>an</span> <span
  m='766050'>algorithm</span> <span m='767160'>for</span> <span
  m='767370'>computing</span> <span m='767940'>the</span> <span
  m='768060'>discrete</span> <span m='768450'>Fourier</span> <span
  m='768840'>transform.</span> </p><p><span m='770810'>In</span> <span
  m='770910'>particular,</span> <span m='771600'>we'll</span> <span
  m='771810'>see</span> <span m='772770'>that</span> <span m='773610'>for</span>
  <span m='773850'>N, a</span> <span m='774300'>product</span> <span
  m='774810'>of</span> <span m='774900'>primes,</span> <span
  m='776930'>using</span> <span m='777830'>the</span> <span
  m='777920'>fast</span> <span m='778280'>Fourier</span> <span
  m='778640'>transform</span> <span m='779330'>algorithm,</span> <span
  m='780860'>the</span> <span m='781520'>number</span> <span
  m='781970'>of</span> <span m='782060'>complex</span> <span
  m='783080'>multiplies</span> <span m='783830'>and</span> <span
  m='783930'>additions</span> <span m='784760'>involved</span> <span
  m='787070'>will</span> <span m='787280'>turn</span> <span
  m='787550'>out</span> <span m='787730'>to</span> <span m='787910'>be</span>
  <span m='788300'>proportional</span> <span m='789470'>not</span> <span
  m='789740'>to</span> <span m='789890'>N</span> <span m='790100'>squared</span>
  <span m='790850'>as</span> <span m='791090'>it</span> <span
  m='791210'>is</span> <span m='791510'>in</span> <span m='791660'>the</span>
  <span m='791780'>direct</span> <span m='792140'>computation,</span> <span
  m='793620'>but</span> <span m='793730'>proportional</span> <span
  m='794420'>to</span> <span m='794600'>N</span> <span m='795620'>times</span>
  <span m='796260'>a</span> <span m='796340'>sum</span> <span
  m='797120'>of</span> <span m='797300'>the</span> <span
  m='797420'>primes</span> <span m='798500'>involved</span> <span
  m='799250'>in</span> <span m='799400'>that</span> <span
  m='799510'>decomposition</span> <span m='800390'>of</span> <span
  m='800480'>N.</span> <span m='801650'>So</span> <span m='802610'>the</span>
  <span m='802910'>greater</span> <span m='803600'>the</span> <span
  m='804170'>number</span> <span m='804530'>of</span> <span
  m='804620'>primes</span> <span m='805190'>that</span> <span
  m='805310'>we</span> <span m='805430'>can</span> <span
  m='805610'>decompose</span> <span m='806300'>N</span> <span
  m='806540'>in</span> <span m='807550'>and</span> <span m='807680'>the</span>
  <span m='807770'>smaller</span> <span m='808370'>each</span> <span
  m='808640'>of</span> <span m='808760'>those</span> <span
  m='809000'>primes,</span> <span m='810170'>the</span> <span
  m='810260'>higher</span> <span m='810920'>the</span> <span
  m='811100'>efficiency</span> <span m='812000'>of</span> <span
  m='812120'>the</span> <span m='812240'>fast</span> <span
  m='812600'>Fourier</span> <span m='812930'>transform</span> <span
  m='813500'>algorithm</span> <span m='814010'>will</span> <span
  m='814160'>be.</span> <span m='816800'>Well,</span> </p><p><span
  m='817190'>The</span> <span m='817310'>most</span> <span
  m='817610'>highly</span> <span m='817970'>composite</span> <span
  m='818870'>that</span> <span m='819290'>we</span> <span m='819500'>can</span>
  <span m='819680'>make</span> <span m='819950'>N,</span> <span
  m='821180'>and</span> <span m='821810'>at</span> <span m='821960'>the</span>
  <span m='822080'>same</span> <span m='822350'>time</span> <span
  m='822650'>keeping</span> <span m='823430'>the</span> <span
  m='823910'>primes,</span> <span m='824390'>p,</span> <span
  m='824780'>as</span> <span m='824900'>small</span> <span m='825260'>as</span>
  <span m='825380'>possible,</span> <span m='826700'>is</span> <span
  m='827180'>to</span> <span m='827360'>choose</span> <span m='827840'>N</span>
  <span m='828650'>to</span> <span m='828770'>be</span> <span
  m='829220'>a</span> <span m='829280'>power</span> <span m='829730'>of</span>
  <span m='829850'>2.</span> <span m='830760'>So</span> <span
  m='830810'>that</span> <span m='830990'>N</span> <span m='831350'>is</span>
  <span m='831770'>of</span> <span m='831950'>the</span> <span
  m='832040'>form</span> <span m='832380'>2</span> <span m='832880'>the</span>
  <span m='833000'>nu,</span> <span m='834210'>where</span> <span
  m='834550'>nu</span> <span m='834830'>is</span> <span m='834920'>the</span>
  <span m='835010'>log</span> <span m='835340'>to</span> <span
  m='835460'>the</span> <span m='835550'>base</span> <span m='835850'>2</span>
  <span m='836260'>of</span> <span m='836440'>N.</span> <span
  m='837710'>And</span> <span m='837800'>it</span> <span m='837890'>will</span>
  <span m='838070'>turn</span> <span m='838340'>out,</span> <span
  m='838520'>in</span> <span m='838640'>that</span> <span
  m='838850'>case,</span> <span m='839510'>that</span> <span
  m='839720'>the</span> <span m='839810'>complex</span> <span
  m='840380'>multiplies</span> <span m='841040'>and</span> <span
  m='841130'>additions</span> <span m='842570'>is</span> <span
  m='842750'>proportional</span> <span m='844070'>to</span> <span
  m='844340'>N</span> <span m='844910'>times</span> <span m='845270'>log</span>
  <span m='845570'>to</span> <span m='845690'>the</span> <span
  m='845810'>base</span> <span m='846110'>2</span> <span m='846470'>N,</span>
  <span m='847280'>rather</span> <span m='847640'>than,</span> <span
  m='847925'>in</span> <span m='848210'>the</span> <span
  m='848300'>direct</span> <span m='848600'>computation,</span> <span
  m='849530'>proportional</span> <span m='850160'>to</span> <span
  m='850310'>N</span> <span m='850490'>squared.</span> </p><p><span
  m='851900'>Let</span> <span m='852080'>me</span> <span
  m='852410'>incidentally</span> <span m='853610'>comment</span> <span
  m='854180'>that</span> <span m='854420'>although</span> <span
  m='854840'>I've</span> <span m='854990'>referred</span> <span
  m='855650'>to</span> <span m='855800'>these</span> <span m='856250'>p's</span>
  <span m='856790'>as</span> <span m='856970'>primes,</span> <span
  m='858170'>they,</span> <span m='858320'>in</span> <span
  m='858410'>fact,</span> <span m='859010'>don't</span> <span
  m='859220'>have</span> <span m='859460'>to</span> <span m='859580'>be</span>
  <span m='859730'>primes.</span> <span m='860750'>The</span> <span
  m='860840'>important</span> <span m='861890'>issue,</span> <span
  m='862400'>as</span> <span m='862610'>we'll</span> <span
  m='862730'>see,</span> <span m='863280'>is</span> <span m='863450'>that</span>
  <span m='864190'>N</span> <span m='864440'>be</span> <span
  m='864590'>representable</span> <span m='865430'>as</span> <span
  m='865610'>a</span> <span m='865670'>product</span> <span m='866150'>of</span>
  <span m='866240'>numbers.</span> <span m='867050'>And</span> <span
  m='867170'>it's</span> <span m='867290'>not</span> <span
  m='867470'>particularly</span> <span m='868070'>important</span> <span
  m='868550'>that</span> <span m='868670'>those</span> <span
  m='868880'>numbers</span> <span m='869450'>turn</span> <span
  m='869720'>out</span> <span m='869870'>to</span> <span m='870020'>be</span>
  <span m='870110'>primes.</span> </p><p><span m='872600'>Well,</span> <span
  m='873340'>OK,</span> <span m='873760'>so</span> <span m='874990'>this</span>
  <span m='875470'>then</span> <span m='875950'>is</span> <span
  m='876580'>the</span> <span m='876700'>kind</span> <span m='876970'>of</span>
  <span m='877090'>efficiency</span> <span m='879160'>that</span> <span
  m='879700'>we</span> <span m='880030'>will</span> <span m='880270'>get</span>
  <span m='880570'>out</span> <span m='880750'>of</span> <span
  m='880840'>the</span> <span m='880930'>fast</span> <span
  m='881260'>Fourier</span> <span m='881620'>transform</span> <span
  m='882280'>algorithm.</span> <span m='883420'>And</span> <span
  m='883960'>let</span> <span m='884200'>me</span> <span m='885160'>begin</span>
  <span m='885520'>the</span> <span m='885610'>discussion</span> <span
  m='886180'>of</span> <span m='886270'>the</span> <span
  m='886450'>algorithm</span> <span m='887530'>by</span> <span
  m='887740'>concentrating</span> <span m='888850'>on</span> <span
  m='889780'>the</span> <span m='889900'>case</span> <span m='890530'>in</span>
  <span m='890680'>which</span> <span m='891160'>N</span> <span
  m='891490'>is</span> <span m='891790'>a</span> <span m='891850'>power</span>
  <span m='892240'>of</span> <span m='892360'>2.</span> <span
  m='892560'>Well,</span> <span m='895820'>basically,</span> <span
  m='897020'>the</span> <span m='897320'>idea</span> <span
  m='897770'>behind</span> <span m='898160'>the</span> <span
  m='898250'>fast</span> <span m='898580'>Fourier</span> <span
  m='898910'>transform</span> <span m='899540'>algorithm</span> <span
  m='901010'>is</span> <span m='901790'>to</span> <span
  m='901940'>decompose</span> <span m='903260'>the</span> <span
  m='903350'>computation</span> <span m='904460'>of</span> <span
  m='904640'>the</span> <span m='904730'>discrete</span> <span
  m='905150'>Fourier</span> <span m='905580'>transform</span> <span
  m='908200'>into</span> <span m='909340'>a</span> <span m='909580'>set</span>
  <span m='910090'>of</span> <span m='910270'>subsequences.</span> <span
  m='912740'>And</span> <span m='913820'>this</span> <span
  m='914330'>is--</span> <span m='915080'>this</span> <span
  m='915320'>generates</span> <span m='916280'>a</span> <span
  m='917330'>class</span> <span m='917960'>of</span> <span
  m='918410'>forms</span> <span m='918950'>for</span> <span
  m='919070'>the</span> <span m='919220'>algorithm,</span> <span
  m='920300'>which</span> <span m='920540'>are</span> <span
  m='920660'>referred</span> <span m='921110'>to</span> <span
  m='921560'>as</span> <span m='922490'>decimation-in-time</span> <span
  m='923600'>forms</span> <span m='923990'>of</span> <span m='924080'>the</span>
  <span m='924230'>algorithm.</span> </p><p><span m='925280'>In</span> <span
  m='925370'>particular,</span> <span m='926790'>suppose</span> <span
  m='927650'>that</span> <span m='927920'>we</span> <span
  m='928340'>consider</span> <span m='929210'>decomposing</span> <span
  m='930410'>the</span> <span m='930530'>original</span> <span
  m='930950'>sequence</span> <span m='931460'>x</span> <span m='931880'>of
  n</span> <span m='933170'>into</span> <span m='933410'>two</span> <span
  m='933620'>subsequences.</span> <span m='935330'>One</span> <span
  m='935540'>sequence,</span> <span m='936620'>subsequence,</span> <span
  m='937430'>consists</span> <span m='938060'>of</span> <span
  m='938780'>the</span> <span m='938960'>even-numbered</span> <span
  m='939680'>points</span> <span m='940040'>of</span> <span m='940130'>x</span>
  <span m='940390'>of</span> <span m='940540'>n.</span> <span
  m='941690'>And</span> <span m='942410'>the</span> <span
  m='942650'>second</span> <span m='943040'>subsequence</span> <span
  m='943910'>consists</span> <span m='944450'>of</span> <span
  m='944630'>the</span> <span m='944780'>odd-numbered</span> <span
  m='945680'>points</span> <span m='946070'>of</span> <span m='946220'>x</span>
  <span m='946400'>of</span> <span m='946500'>n.</span> <span
  m='947390'>Well,</span> <span m='947780'>let's</span> <span
  m='948110'>just</span> <span m='948350'>do</span> <span m='948560'>that</span>
  <span m='948860'>and</span> <span m='948980'>see</span> <span
  m='949160'>where</span> <span m='949340'>it</span> <span
  m='949430'>gets</span> <span m='949730'>us.</span> <span m='951020'>We</span>
  <span m='951200'>can</span> <span m='951380'>then</span> <span
  m='952130'>rewrite</span> <span m='952910'>the</span> <span
  m='953000'>discrete</span> <span m='953390'>Fourier</span> <span
  m='953810'>transform</span> <span m='955610'>as</span> <span
  m='956060'>a</span> <span m='956150'>sum</span> <span m='956810'>over</span>
  <span m='957290'>n</span> <span m='957740'>even</span> <span
  m='959000'>of</span> <span m='959240'>x</span> <span m='959540'>of</span>
  <span m='959660'>n</span> <span m='959870'>times</span> <span m='960200'>W sub
  N</span> <span m='961070'>to</span> <span m='961230'>the</span> <span
  m='961370'>nk</span> <span m='962570'>plus</span> <span m='962870'>the</span>
  <span m='962960'>sum</span> <span m='964280'>over</span> <span
  m='964640'>n</span> <span m='964910'>odd</span> <span m='965390'>of</span>
  <span m='965660'>x</span> <span m='965950'>of n</span> <span
  m='966530'>W</span> <span m='967040'>sub N</span> <span m='967460'>to</span>
  <span m='967610'>the</span> <span m='967760'>nk.</span> <span
  m='968750'>Simply</span> <span m='969230'>pulling</span> <span
  m='969590'>out</span> <span m='969800'>from</span> <span
  m='970010'>this</span> <span m='970790'>the</span> <span
  m='970970'>even-numbered</span> <span m='972110'>values</span> <span
  m='973280'>and</span> <span m='974000'>the</span> <span
  m='974150'>odd-numbered</span> <span m='974720'>values.</span> </p><p><span
  m='976976'>All</span> <span m='977390'>right,</span> <span
  m='977670'>now</span> <span m='977880'>by</span> <span m='978060'>a</span>
  <span m='978120'>substitution</span> <span m='978870'>of</span> <span
  m='978930'>variables,</span> <span m='979980'>we</span> <span
  m='980190'>can</span> <span m='981000'>substitute</span> <span
  m='982470'>for</span> <span m='982710'>n</span> <span m='983420'>2</span>
  <span m='983760'>r</span> <span m='985170'>in</span> <span
  m='986160'>the</span> <span m='986340'>even-numbered</span> <span
  m='987020'>terms.</span> <span m='988260'>And</span> <span
  m='988410'>we</span> <span m='988530'>can</span> <span
  m='988710'>substitute</span> <span m='989370'>n</span> <span
  m='989640'>equals</span> <span m='990060'>2</span> <span m='990330'>r</span>
  <span m='990540'>plus</span> <span m='990870'>1</span> <span
  m='991950'>for</span> <span m='992070'>the</span> <span
  m='992250'>odd-number</span> <span m='992880'>terms,</span> <span
  m='994080'>in</span> <span m='994200'>which</span> <span
  m='994440'>case,</span> <span m='995170'>when</span> <span
  m='995250'>we</span> <span m='995370'>convert</span> <span
  m='995820'>these</span> <span m='996060'>two</span> <span
  m='996210'>sums</span> <span m='996720'>over</span> <span m='997020'>r,</span>
  <span m='998430'>the</span> <span m='998550'>sum</span> <span
  m='998850'>on</span> <span m='999000'>r</span> <span m='999780'>will</span>
  <span m='999900'>now</span> <span m='1000170'>range</span> <span
  m='1000560'>from</span> <span m='1000770'>0</span> <span m='1001760'>to</span>
  <span m='1001880'>capital</span> <span m='1002360'>N</span> <span
  m='1002480'>over</span> <span m='1002720'>2</span> <span
  m='1002930'>minus</span> <span m='1003320'>1.</span> <span
  m='1004700'>As</span> <span m='1004880'>r</span> <span m='1005090'>runs</span>
  <span m='1005360'>from</span> <span m='1005540'>0</span> <span
  m='1005900'>to</span> <span m='1006050'>capital</span> <span
  m='1006470'>N</span> <span m='1006590'>over</span> <span m='1006800'>2</span>
  <span m='1006980'>minus</span> <span m='1007400'>1,</span> <span
  m='1008300'>2</span> <span m='1008570'>r</span> <span
  m='1008900'>ranges</span> <span m='1009380'>over</span> <span
  m='1009890'>the</span> <span m='1010070'>even-numbered</span> <span
  m='1010730'>terms,</span> <span m='1011810'>and</span> <span
  m='1012230'>2</span> <span m='1012500'>r</span> <span m='1012740'>plus</span>
  <span m='1013100'>1</span> <span m='1013760'>ranges</span> <span
  m='1014210'>over</span> <span m='1014480'>the</span> <span
  m='1014630'>odd-numbered</span> <span m='1015130'>terms.</span> </p><p><span
  m='1017250'>All</span> <span m='1017340'>right,</span> <span
  m='1017730'>so</span> <span m='1018030'>making</span> <span
  m='1018420'>the</span> <span m='1018520'>substitution</span> <span
  m='1019290'>of</span> <span m='1019350'>variables</span> <span
  m='1020310'>then,</span> <span m='1021650'>this</span> <span
  m='1021960'>sum</span> <span m='1023730'>is</span> <span
  m='1024119'>converted</span> <span m='1024990'>into</span> <span
  m='1026339'>a</span> <span m='1026400'>sum</span> <span
  m='1027540'>from</span> <span m='1027750'>r equals</span> <span
  m='1028170'>0</span> <span m='1028770'>to</span> <span m='1028920'>N</span>
  <span m='1029099'>over</span> <span m='1029310'>2</span> <span
  m='1029520'>minus</span> <span m='1029940'>1.</span> <span
  m='1031186'>x</span> <span m='1031569'>of</span> <span m='1031770'>2r</span>
  <span m='1032440'>W sub</span> <span m='1032855'>N</span> <span m='1033270'>to
  the</span> <span m='1033480'>2rk</span> <span m='1035490'>plus</span> <span
  m='1035940'>a</span> <span m='1036010'>sum--</span> <span
  m='1036400'>those</span> <span m='1036630'>are</span> <span
  m='1036690'>the</span> <span m='1036810'>even-numbered</span> <span
  m='1037400'>terms--</span> <span m='1038640'>plus</span> <span
  m='1038930'>a</span> <span m='1039020'>sum</span> <span
  m='1039630'>over</span> <span m='1039839'>the</span> <span
  m='1040020'>odd-numbered</span> <span m='1040560'>terms</span> <span
  m='1041550'>from</span> <span m='1041730'>0</span> <span m='1042510'>to</span>
  <span m='1042630'>n</span> <span m='1042810'>over</span> <span
  m='1043050'>2</span> <span m='1043260'>minus</span> <span
  m='1043650'>1.</span> <span m='1043750'>x</span> <span m='1044550'>of</span>
  <span m='1044910'>2r</span> <span m='1045450'>plus</span> <span
  m='1045780'>1,</span> <span m='1046109'>the</span> <span
  m='1046230'>odd-numbered</span> <span m='1047130'>points,</span> <span
  m='1048250'>times</span> <span m='1048569'>W sub N</span> <span
  m='1049590'>to</span> <span m='1049740'>the</span> <span m='1049860'>2r</span>
  <span m='1050310'>plus</span> <span m='1050640'>1</span> <span
  m='1051210'>times</span> <span m='1051530'>k.</span> </p><p><span
  m='1053760'>Well,</span> <span m='1054210'>let's</span> <span
  m='1054450'>look</span> <span m='1054660'>at</span> <span
  m='1054750'>this</span> <span m='1054930'>factor.</span> <span
  m='1055820'>W</span> <span m='1056130'>sub N</span> <span m='1056520'>to
  the</span> <span m='1056640'>2r</span> <span m='1057000'>plus</span> <span
  m='1057300'>1</span> <span m='1057510'>times</span> <span
  m='1057870'>k,</span> <span m='1059220'>that's</span> <span
  m='1059520'>equal</span> <span m='1059970'>to</span> <span m='1061200'>W sub
  N</span> <span m='1062220'>to</span> <span m='1062370'>the</span> <span
  m='1062460'>k,</span> <span m='1063780'>because</span> <span
  m='1064110'>of</span> <span m='1064200'>the</span> <span m='1064320'>1,</span>
  <span m='1066170'>and</span> <span m='1066320'>W sub</span> <span
  m='1066800'>N</span> <span m='1067280'>to</span> <span m='1067380'>the</span>
  <span m='1067560'>2rk.</span> <span m='1070080'>So</span> <span
  m='1070920'>we</span> <span m='1071070'>can,</span> <span
  m='1071220'>first</span> <span m='1071520'>of</span> <span
  m='1071670'>all,</span> <span m='1072150'>break</span> <span
  m='1072570'>this</span> <span m='1072810'>term</span> <span
  m='1073230'>up</span> <span m='1073530'>into</span> <span m='1073770'>a</span>
  <span m='1073830'>product</span> <span m='1074310'>of</span> <span
  m='1074430'>these</span> <span m='1074670'>two</span> <span
  m='1074880'>terms.</span> <span m='1076560'>And</span> <span
  m='1076650'>now,</span> <span m='1076800'>let's</span> <span
  m='1077040'>look</span> <span m='1077250'>at</span> <span
  m='1077370'>this</span> <span m='1077610'>one,</span> <span m='1078060'>W sub
  N</span> <span m='1078860'>to</span> <span m='1078990'>the</span> <span
  m='1079110'>2rk.</span> <span m='1081420'>Well,</span> <span m='1082020'>W sub
  N</span> <span m='1082800'>squared</span> <span m='1084466'>is</span> <span
  m='1084910'>equal</span> <span m='1085480'>to</span> <span
  m='1085930'>e</span> <span m='1086220'>to</span> <span m='1086290'>the</span>
  <span m='1086380'>minus</span> <span m='1086800'>j</span> <span
  m='1087055'>2</span> <span m='1087310'>pi</span> <span m='1087610'>over</span>
  <span m='1087850'>capital</span> <span m='1088360'>N</span> <span
  m='1088840'>squared.</span> <span m='1090410'>So</span> <span
  m='1090460'>the</span> <span m='1090550'>factor</span> <span
  m='1090970'>of</span> <span m='1091070'>2.</span> <span m='1092960'>If</span>
  <span m='1093060'>we</span> <span m='1093100'>take</span> <span
  m='1093340'>the</span> <span m='1093460'>2</span> <span
  m='1093700'>down</span> <span m='1093970'>in</span> <span
  m='1094090'>the</span> <span m='1094180'>denominator</span> <span
  m='1094960'>and</span> <span m='1095050'>associate it</span> <span
  m='1095800'>with</span> <span m='1095980'>the</span> <span
  m='1096130'>N,</span> <span m='1097150'>we</span> <span m='1097270'>can</span>
  <span m='1097450'>rewrite</span> <span m='1097870'>this</span> <span
  m='1098110'>as</span> <span m='1098260'>e</span> <span m='1098440'>to</span>
  <span m='1098500'>the</span> <span m='1098620'>minus</span> <span
  m='1098980'>j</span> <span m='1099250'>2</span> <span m='1099520'>pi</span>
  <span m='1100870'>over</span> <span m='1101560'>N/2.</span> <span
  m='1103820'>So</span> <span m='1104450'>what</span> <span m='1104960'>W sub
  N</span> <span m='1105680'>squared</span> <span m='1106160'>is</span> <span
  m='1106310'>equal</span> <span m='1106640'>to</span> <span
  m='1107210'>is</span> <span m='1107750'>W</span> <span m='1108770'>sub</span>
  <span m='1109610'>capital</span> <span m='1110090'>N</span> <span
  m='1110480'>over</span> <span m='1110750'>2.</span> <span
  m='1111540'>In</span> <span m='1111560'>other</span> <span
  m='1111740'>words,</span> <span m='1112110'>the</span> <span
  m='1112130'>W</span> <span m='1112610'>that</span> <span m='1112730'>we</span>
  <span m='1112910'>would</span> <span m='1113030'>associate</span> <span
  m='1114020'>with</span> <span m='1114320'>an</span> <span
  m='1114500'>N/2</span> <span m='1114680'>point</span> <span
  m='1115670'>discrete</span> <span m='1116060'>Fourier</span> <span
  m='1116450'>transform.</span> </p><p><span m='1118580'>Finally,</span> <span
  m='1119960'>substituting</span> <span m='1121940'>this</span> <span
  m='1122720'>together</span> <span m='1123470'>with</span> <span
  m='1123650'>this</span> <span m='1123860'>statement</span> <span
  m='1125030'>back</span> <span m='1125390'>into</span> <span
  m='1125780'>this</span> <span m='1125990'>expression,</span> <span
  m='1127470'>we</span> <span m='1127550'>have,</span> <span
  m='1128300'>for</span> <span m='1129440'>x</span> <span m='1129830'>of</span>
  <span m='1130020'>k,</span> <span m='1131850'>the</span> <span
  m='1132000'>sum</span> <span m='1132690'>from</span> <span
  m='1132900'>0</span> <span m='1133320'>to</span> <span m='1133440'>N/2</span>
  <span m='1134010'>minus</span> <span m='1134430'>1,</span> <span
  m='1135240'>x</span> <span m='1135540'>of</span> <span m='1135660'>2r</span>
  <span m='1136600'>W</span> <span m='1137400'>sub N</span> <span
  m='1137700'>over 2</span> <span m='1137960'>to</span> <span
  m='1138370'>the</span> <span m='1138550'>rk</span> <span
  m='1140010'>plus</span> <span m='1140640'>W</span> <span m='1140970'>sub
  N</span> <span m='1141280'>to</span> <span m='1141510'>the</span> <span
  m='1141600'>k</span> <span m='1142710'>times</span> <span
  m='1143100'>the</span> <span m='1143220'>sum</span> <span
  m='1143910'>of</span> <span m='1144270'>x of</span> <span
  m='1144575'>2r</span> <span m='1145080'>plus</span> <span m='1145410'>1</span>
  <span m='1145800'>W sub</span> <span m='1146190'>N</span> <span
  m='1146520'>over</span> <span m='1146860'>2 to</span> <span
  m='1147240'>the</span> <span m='1147380'>rk.</span> <span
  m='1149630'>Well,</span> <span m='1149940'>what</span> <span
  m='1150140'>this</span> <span m='1150380'>looks</span> <span
  m='1150710'>like</span> <span m='1151970'>is</span> <span
  m='1152270'>an</span> <span m='1152570'>N/2</span> <span
  m='1153200'>point</span> <span m='1153830'>discrete</span> <span
  m='1154250'>Fourier</span> <span m='1154610'>transform.</span> <span
  m='1156420'>And</span> <span m='1156570'>what</span> <span
  m='1156750'>this</span> <span m='1156990'>looks</span> <span
  m='1157260'>like</span> <span m='1157700'>is</span> <span
  m='1157870'>an</span> <span m='1158030'>N/2</span> <span
  m='1158850'>point</span> <span m='1159330'>discrete</span> <span
  m='1159720'>Fourier</span> <span m='1160050'>transform.</span> <span
  m='1160320'>And</span> <span m='1160590'>in</span> <span
  m='1160650'>fact,</span> <span m='1161050'>that's</span> <span
  m='1161160'>what</span> <span m='1161340'>they</span> <span
  m='1161520'>are.</span> </p><p><span m='1162550'>This</span> <span
  m='1162720'>is</span> <span m='1163260'>an</span> <span m='1163470'>N/2</span>
  <span m='1163800'>point</span> <span m='1164684'>DFT</span> <span
  m='1166020'>of</span> <span m='1166230'>the</span> <span
  m='1166380'>even-numbered</span> <span m='1167100'>points</span> <span
  m='1167880'>in</span> <span m='1167990'>a</span> <span
  m='1168060'>sequence</span> <span m='1168540'>x</span> <span m='1168760'>of
  n.</span> <span m='1170100'>This</span> <span m='1170490'>is</span> <span
  m='1171860'>an</span> <span m='1172180'>N/2</span> <span
  m='1172710'>point</span> <span m='1174000'>of</span> <span
  m='1174180'>the</span> <span m='1174330'>odd-numbered</span> <span
  m='1174960'>points</span> <span m='1175560'>in</span> <span
  m='1175680'>the</span> <span m='1175770'>sequence</span> <span
  m='1176370'>x</span> <span m='1176650'>of n.</span> <span
  m='1177870'>So</span> <span m='1178050'>this</span> <span
  m='1178260'>says</span> <span m='1179100'>we</span> <span
  m='1179220'>can</span> <span m='1179400'>compute</span> <span
  m='1179880'>x</span> <span m='1180120'>of</span> <span m='1180240'>k</span>
  <span m='1181110'>by</span> <span m='1181260'>computing</span> <span
  m='1181920'>an N/2</span> <span m='1182460'>point</span> <span
  m='1182920'>DFT,</span> <span m='1184920'>another</span> <span
  m='1185620'>N/2</span> <span m='1185700'>point</span> <span
  m='1185910'>DFT,</span> <span m='1187680'>and</span> <span
  m='1187780'>combining</span> <span m='1188400'>those</span> <span
  m='1188640'>two</span> <span m='1188850'>together</span> <span
  m='1189900'>with</span> <span m='1190380'>this</span> <span
  m='1190560'>factor</span> <span m='1191010'>out</span> <span
  m='1191160'>in</span> <span m='1191280'>front,</span> <span m='1191910'>W sub
  N</span> <span m='1192690'>to</span> <span m='1192820'>the</span> <span
  m='1192900'>k.</span> </p><p><span m='1194520'>Now,</span> <span
  m='1194910'>it's</span> <span m='1195090'>not</span> <span
  m='1195270'>particularly</span> <span m='1195930'>obvious</span> <span
  m='1196350'>yet</span> <span m='1196810'>that,</span> <span
  m='1197100'>in</span> <span m='1197250'>fact,</span> <span
  m='1197710'>in</span> <span m='1197810'>doing</span> <span
  m='1198060'>this,</span> <span m='1198450'>we've</span> <span
  m='1198690'>saved</span> <span m='1198990'>something</span> <span
  m='1199380'>in</span> <span m='1199470'>computation.</span> <span
  m='1200980'>But</span> <span m='1201390'>let's</span> <span
  m='1201930'>look</span> <span m='1202380'>at</span> <span
  m='1203010'>what</span> <span m='1203250'>this</span> <span
  m='1203730'>implies</span> <span m='1204600'>in</span> <span
  m='1204750'>terms</span> <span m='1205260'>of</span> <span
  m='1205950'>the</span> <span m='1206070'>computational</span> <span
  m='1206910'>steps</span> <span m='1207840'>in</span> <span
  m='1207960'>a</span> <span m='1207990'>little</span> <span
  m='1208200'>more</span> <span m='1208380'>detail.</span> <span
  m='1211210'>So</span> <span m='1211680'>here</span> <span
  m='1211950'>we</span> <span m='1212100'>have,</span> <span
  m='1212850'>again,</span> <span m='1216950'>X of k</span> <span
  m='1217910'>as</span> <span m='1218780'>an</span> <span m='1219750'>N/2</span>
  <span m='1220190'>point</span> <span m='1220567'>DFT</span> <span
  m='1223250'>involving</span> <span m='1224060'>the</span> <span
  m='1224240'>even-numbered</span> <span m='1224900'>points</span> <span
  m='1225260'>in</span> <span m='1225380'>x</span> <span m='1225580'>of n</span>
  <span m='1228020'>plus</span> <span m='1228770'>an</span> <span
  m='1228920'>N/2</span> <span m='1229070'>point</span> <span
  m='1229280'>DFT</span> <span m='1230660'>involving</span> <span
  m='1231290'>the</span> <span m='1231490'>odd-numbered</span> <span
  m='1232010'>points</span> <span m='1232760'>in</span> <span
  m='1232910'>x</span> <span m='1233110'>of n.</span> <span
  m='1234590'>Those</span> <span m='1234800'>are</span> <span
  m='1234860'>both</span> <span m='1235160'>N/2</span> <span
  m='1235640'>point</span> <span m='1236090'>DFTs.</span> <span
  m='1237620'>This</span> <span m='1237890'>one,</span> <span
  m='1238850'>if</span> <span m='1239000'>we</span> <span
  m='1239150'>refer</span> <span m='1239480'>to</span> <span
  m='1239690'>as</span> <span m='1239840'>G</span> <span m='1240080'>of</span>
  <span m='1240200'>k,</span> <span m='1241250'>this</span> <span
  m='1241460'>one,</span> <span m='1241640'>if</span> <span
  m='1241760'>we</span> <span m='1241910'>refer</span> <span
  m='1242270'>to</span> <span m='1242780'>as</span> <span m='1243290'>H</span>
  <span m='1243610'>of</span> <span m='1243730'>k,</span> <span
  m='1244670'>then</span> <span m='1244820'>the</span> <span
  m='1244910'>computation</span> <span m='1245960'>of</span> <span
  m='1246110'>the</span> <span m='1246230'>DFT,</span> <span
  m='1246920'>X</span> <span m='1247220'>of</span> <span m='1247340'>k</span>
  <span m='1248240'>is</span> <span m='1248450'>G</span> <span
  m='1248720'>of</span> <span m='1248840'>k</span> <span m='1249740'>plus</span>
  <span m='1249980'>W sub</span> <span m='1250385'>N</span> <span
  m='1250790'>to</span> <span m='1250940'>the</span> <span m='1251030'>k</span>
  <span m='1251810'>times</span> <span m='1252320'>H</span> <span
  m='1252590'>of</span> <span m='1252680'>k.</span> </p><p><span
  m='1254790'>All</span> <span m='1254880'>right,</span> <span
  m='1255000'>let's</span> <span m='1255210'>see</span> <span
  m='1255360'>what</span> <span m='1255540'>this</span> <span
  m='1256020'>means</span> <span m='1256410'>in</span> <span
  m='1256500'>terms</span> <span m='1256830'>of</span> <span
  m='1256890'>computation,</span> <span m='1258540'>computational</span> <span
  m='1259320'>complexity.</span> <span m='1261180'>We</span> <span
  m='1261230'>have</span> <span m='1261440'>to</span> <span
  m='1261560'>compute</span> <span m='1262870'>an</span> <span
  m='1263030'>N/2</span> <span m='1263150'>point</span> <span
  m='1263420'>DFT.</span> <span m='1265910'>We</span> <span
  m='1266030'>just</span> <span m='1266360'>argued</span> <span
  m='1267110'>that</span> <span m='1267650'>an</span> <span
  m='1267770'>endpoint</span> <span m='1268280'>DFT</span> <span
  m='1269240'>involves</span> <span m='1270430'>N</span> <span
  m='1270650'>squared</span> <span m='1271700'>complex</span> <span
  m='1272600'>multiplies</span> <span m='1273260'>and</span> <span
  m='1273350'>adds.</span> <span m='1274950'>So</span> <span
  m='1275090'>the</span> <span m='1275210'>computation</span> <span
  m='1276050'>of</span> <span m='1276140'>G</span> <span m='1276350'>of</span>
  <span m='1276470'>k</span> <span m='1277040'>involves</span> <span
  m='1278260'>N/2</span> <span m='1278960'>squared</span> <span
  m='1280430'>complex</span> <span m='1280970'>multiplies</span> <span
  m='1281660'>and</span> <span m='1281750'>adds.</span> <span
  m='1283010'>The</span> <span m='1283100'>computation</span> <span
  m='1284120'>of</span> <span m='1284270'>H</span> <span m='1284540'>of</span>
  <span m='1284660'>k</span> <span m='1286160'>involves,</span> <span
  m='1286970'>likewise,</span> <span m='1287900'>N/2</span> <span
  m='1288530'>squared</span> <span m='1289490'>complex</span> <span
  m='1290060'>multiplies</span> <span m='1290750'>and</span> <span
  m='1290840'>adds.</span> <span m='1292010'>So</span> <span
  m='1292820'>we</span> <span m='1293030'>have</span> <span
  m='1293300'>then</span> <span m='1293780'>2</span> <span
  m='1294050'>times</span> <span m='1294530'>N/2</span> <span
  m='1295070'>squared</span> <span m='1296060'>multiplies</span> <span
  m='1296710'>and</span> <span m='1296810'>adds</span> <span
  m='1297785'>due</span> <span m='1298100'>to</span> <span
  m='1298250'>the</span> <span m='1298340'>computation</span> <span
  m='1299390'>of</span> <span m='1299600'>these</span> <span
  m='1300170'>two</span> <span m='1301070'>N/2</span> <span
  m='1301220'>point</span> <span m='1301460'>DFT.</span> </p><p><span
  m='1304400'>In</span> <span m='1304490'>addition,</span> <span
  m='1305610'>we</span> <span m='1305660'>have</span> <span
  m='1305900'>to</span> <span m='1306020'>combine</span> <span
  m='1306500'>these</span> <span m='1306740'>together</span> <span
  m='1307970'>by</span> <span m='1308270'>multiplying</span> <span
  m='1308930'>by</span> <span m='1309080'>W</span> <span m='1309410'>sub
  N</span> <span m='1309720'>to</span> <span m='1309920'>the</span> <span
  m='1310030'>k.</span> <span m='1311810'>That</span> <span
  m='1312110'>involves</span> <span m='1313400'>capital</span> <span
  m='1313940'>N</span> <span m='1314810'>complex</span> <span
  m='1315380'>multiplies</span> <span m='1316010'>and</span> <span
  m='1316130'>adds,</span> <span m='1316430'>because</span> <span
  m='1317450'>k</span> <span m='1317780'>ranges</span> <span
  m='1318380'>from</span> <span m='1318560'>0</span> <span m='1319040'>to</span>
  <span m='1319190'>N</span> <span m='1319400'>minus</span> <span
  m='1319790'>1.</span> <span m='1320430'>In</span> <span
  m='1320450'>other</span> <span m='1320660'>words,</span> <span
  m='1321500'>k</span> <span m='1321830'>ranges</span> <span
  m='1322340'>over</span> <span m='1322760'>N</span> <span
  m='1323240'>different</span> <span m='1323570'>values.</span> <span
  m='1324570'>So</span> <span m='1324790'>there are</span> <span
  m='1325120'>N</span> <span m='1325340'>complex</span> <span
  m='1325910'>multiplies</span> <span m='1326690'>involved</span> <span
  m='1327290'>in</span> <span m='1327470'>this,</span> <span
  m='1328580'>and</span> <span m='1328700'>then</span> <span
  m='1329140'>N</span> <span m='1329450'>complex</span> <span
  m='1330110'>adds</span> <span m='1330590'>in</span> <span
  m='1330740'>combining</span> <span m='1331280'>these</span> <span
  m='1331520'>together.</span> </p><p><span m='1332610'>So</span> <span
  m='1332900'>in</span> <span m='1333080'>addition</span> <span
  m='1333650'>to</span> <span m='1333800'>the</span> <span
  m='1333890'>computation</span> <span m='1334790'>of</span> <span
  m='1334940'>the</span> <span m='1335030'>two</span> <span
  m='1335810'>N/2</span> <span m='1336200'>point</span> <span
  m='1336560'>DFTs,</span> <span m='1338000'>we</span> <span
  m='1338120'>have</span> <span m='1338600'>the</span> <span
  m='1338720'>combination</span> <span m='1339500'>of</span> <span
  m='1339680'>them.</span> <span m='1340430'>And</span> <span
  m='1340940'>the</span> <span m='1341060'>resulting</span> <span
  m='1341540'>computation</span> <span m='1342890'>involves</span> <span
  m='1343520'>N</span> <span m='1344510'>plus</span> <span m='1345290'>N</span>
  <span m='1345500'>squared</span> <span m='1346550'>over</span> <span
  m='1346880'>2</span> <span m='1347930'>complex</span> <span
  m='1348740'>multiplies</span> <span m='1349400'>and</span> <span
  m='1349490'>adds.</span> <span m='1350720'>And</span> <span
  m='1351260'>you</span> <span m='1351410'>can</span> <span
  m='1351560'>convince</span> <span m='1351950'>yourself</span> <span
  m='1352490'>on</span> <span m='1352580'>the</span> <span
  m='1352670'>back</span> <span m='1352910'>of</span> <span
  m='1353000'>an</span> <span m='1353090'>envelope</span> <span
  m='1353540'>very</span> <span m='1353750'>quickly</span> <span
  m='1354800'>that</span> <span m='1355190'>this</span> <span
  m='1355430'>number</span> <span m='1356420'>will</span> <span
  m='1356600'>always</span> <span m='1356960'>turn</span> <span
  m='1357170'>out</span> <span m='1357350'>to</span> <span m='1357500'>be</span>
  <span m='1357710'>less</span> <span m='1358100'>than</span> <span
  m='1358355'>N</span> <span m='1358610'>squared,</span> <span
  m='1359330'>except,</span> <span m='1359720'>I</span> <span
  m='1359810'>think,</span> <span m='1360080'>for</span> <span
  m='1361190'>some</span> <span m='1361430'>trivial</span> <span
  m='1361820'>cases</span> <span m='1362390'>like</span> <span
  m='1362660'>N</span> <span m='1362840'>equals</span> <span
  m='1363110'>1</span> <span m='1363350'>or N</span> <span
  m='1363470'>equals</span> <span m='1363860'>2.</span> </p><p><span
  m='1366410'>Now,</span> <span m='1367220'>one</span> <span
  m='1368690'>minor</span> <span m='1369170'>point</span> <span
  m='1369500'>to</span> <span m='1369650'>be</span> <span
  m='1369770'>made--</span> <span m='1371490'>in</span> <span
  m='1371670'>combining</span> <span m='1372210'>these</span> <span
  m='1372420'>two</span> <span m='1372570'>together,</span> <span
  m='1373230'>I</span> <span m='1373320'>commented</span> <span
  m='1373890'>that</span> <span m='1374010'>k</span> <span
  m='1374340'>has</span> <span m='1374550'>to</span> <span
  m='1374700'>run</span> <span m='1374940'>from</span> <span
  m='1375150'>0</span> <span m='1376110'>to</span> <span
  m='1376230'>capital</span> <span m='1376710'>N</span> <span
  m='1376830'>minus</span> <span m='1377220'>1.</span> <span
  m='1378080'>That</span> <span m='1378510'>is,</span> <span
  m='1378660'>there</span> <span m='1378930'>are</span> <span
  m='1379200'>N</span> <span m='1380010'>different</span> <span
  m='1380340'>values</span> <span m='1380880'>that k</span> <span
  m='1381440'>ranges</span> <span m='1381810'>over,</span> <span
  m='1382890'>so</span> <span m='1383100'>doesn't</span> <span
  m='1383430'>that</span> <span m='1383700'>say</span> <span
  m='1384990'>that</span> <span m='1385230'>in</span> <span
  m='1385380'>computing</span> <span m='1386040'>G</span> <span
  m='1386280'>of</span> <span m='1386400'>k,</span> <span m='1388050'>I</span>
  <span m='1388170'>can't</span> <span m='1388560'>just</span> <span
  m='1388800'>compute</span> <span m='1389320'>it</span> <span
  m='1389940'>from</span> <span m='1390150'>k</span> <span
  m='1390540'>equals</span> <span m='1390660'>0</span> <span
  m='1391500'>to</span> <span m='1391650'>n</span> <span m='1391860'>over</span>
  <span m='1392100'>2</span> <span m='1392310'>minus</span> <span
  m='1392730'>1</span> <span m='1393120'>as</span> <span m='1393300'>I</span>
  <span m='1393390'>normally</span> <span m='1393870'>would</span> <span
  m='1394110'>in</span> <span m='1394260'>computing</span> <span
  m='1394770'>a</span> <span m='1394830'>DFT?</span> <span
  m='1396050'>Don't</span> <span m='1396330'>I</span> <span
  m='1396450'>have</span> <span m='1396660'>to</span> <span
  m='1396780'>compute</span> <span m='1397150'>it</span> <span
  m='1397680'>from</span> <span m='1397910'>0</span> <span
  m='1398670'>all</span> <span m='1398880'>the</span> <span
  m='1398970'>way</span> <span m='1399150'>up</span> <span m='1399330'>to</span>
  <span m='1399450'>N</span> <span m='1399870'>or</span> <span
  m='1400110'>all</span> <span m='1400230'>the</span> <span
  m='1400290'>way</span> <span m='1400440'>up</span> <span m='1400590'>to</span>
  <span m='1400710'>N</span> <span m='1400860'>minus</span> <span
  m='1401250'>1?</span> <span m='1402050'>Well,</span> <span
  m='1402450'>sure</span> <span m='1402780'>I</span> <span
  m='1402900'>do.</span> <span m='1403620'>I</span> <span m='1403770'>do,</span>
  <span m='1404040'>because</span> <span m='1404820'>those</span> <span
  m='1405090'>are</span> <span m='1405150'>the</span> <span
  m='1405240'>values</span> <span m='1406230'>that</span> <span
  m='1406380'>I</span> <span m='1406440'>need</span> <span m='1406800'>in</span>
  <span m='1406980'>here</span> <span m='1407370'>and</span> <span
  m='1407510'>in</span> <span m='1407610'>here.</span> </p><p><span
  m='1409110'>But</span> <span m='1409260'>what</span> <span
  m='1409470'>does</span> <span m='1409590'>that</span> <span
  m='1409800'>imply</span> <span m='1410310'>in</span> <span
  m='1410400'>terms</span> <span m='1410700'>of</span> <span
  m='1410790'>computation?</span> <span m='1412380'>Well,</span> <span
  m='1412560'>we</span> <span m='1412710'>know</span> <span
  m='1413760'>that</span> <span m='1414465'>an</span> <span
  m='1414720'>N/2</span> <span m='1415560'>point</span> <span
  m='1416220'>DFT</span> <span m='1417840'>is</span> <span
  m='1418050'>periodic</span> <span m='1419550'>in</span> <span
  m='1419740'>k,</span> <span m='1421550'>so</span> <span
  m='1421880'>that</span> <span m='1422450'>if</span> <span
  m='1422660'>we</span> <span m='1422780'>compute</span> <span
  m='1424070'>only</span> <span m='1424430'>the</span> <span
  m='1424520'>first</span> <span m='1424830'>N/2</span> <span
  m='1425450'>points,</span> <span m='1427070'>we</span> <span
  m='1427190'>know</span> <span m='1427520'>that</span> <span
  m='1427670'>the</span> <span m='1427790'>next</span> <span
  m='1428090'>N/2</span> <span m='1428660'>points</span> <span
  m='1429110'>are</span> <span m='1429230'>going</span> <span
  m='1429470'>to</span> <span m='1429590'>look</span> <span
  m='1429800'>exactly</span> <span m='1430430'>the</span> <span
  m='1430550'>same.</span> <span m='1431000'>And</span> <span
  m='1431120'>so,</span> <span m='1431270'>there's</span> <span
  m='1431450'>no</span> <span m='1431630'>point</span> <span
  m='1431900'>in</span> <span m='1432020'>computing</span> <span
  m='1432275'>them.</span> <span m='1433100'>So</span> <span
  m='1433250'>the</span> <span m='1433370'>point</span> <span
  m='1433730'>then</span> <span m='1434090'>is</span> <span
  m='1434360'>that</span> <span m='1434930'>in</span> <span
  m='1435050'>computing</span> <span m='1435620'>G</span> <span
  m='1435830'>of</span> <span m='1435950'>k</span> <span m='1437330'>for</span>
  <span m='1437480'>this</span> <span m='1437720'>computation,</span> <span
  m='1439220'>even</span> <span m='1439520'>though</span> <span
  m='1439670'>we</span> <span m='1439850'>want</span> <span m='1440090'>k</span>
  <span m='1440450'>to</span> <span m='1440630'>run</span> <span
  m='1441380'>from</span> <span m='1441560'>0</span> <span m='1441980'>to</span>
  <span m='1442160'>N</span> <span m='1442400'>minus</span> <span
  m='1442790'>1,</span> <span m='1443900'>we</span> <span
  m='1444080'>only</span> <span m='1444410'>need</span> <span
  m='1444680'>to</span> <span m='1444920'>explicitly</span> <span
  m='1445700'>do</span> <span m='1445940'>this</span> <span
  m='1446150'>computation</span> <span m='1447500'>for</span> <span
  m='1447680'>k</span> <span m='1448610'>from</span> <span m='1448790'>0</span>
  <span m='1449720'>to</span> <span m='1449840'>N</span> <span
  m='1450020'>over</span> <span m='1450230'>2</span> <span
  m='1450440'>minus</span> <span m='1450830'>1.</span> <span
  m='1451170'>And</span> <span m='1451220'>then</span> <span
  m='1451400'>we</span> <span m='1451520'>simply</span> <span
  m='1451880'>use</span> <span m='1452180'>those</span> <span
  m='1452480'>values</span> <span m='1453320'>over</span> <span
  m='1453710'>again</span> <span m='1454490'>for</span> <span
  m='1455060'>the</span> <span m='1455180'>second</span> <span
  m='1455570'>range</span> <span m='1456110'>from</span> <span
  m='1456290'>k</span> <span m='1456710'>from N/2</span> <span
  m='1457580'>to</span> <span m='1457730'>N</span> <span
  m='1457910'>minus</span> <span m='1458300'>1.</span> <span
  m='1459320'>And</span> <span m='1459440'>that,</span> <span
  m='1459710'>by</span> <span m='1459920'>the</span> <span
  m='1460040'>way,</span> <span m='1461090'>is</span> <span
  m='1461960'>the</span> <span m='1462140'>essential</span> <span
  m='1462770'>key</span> <span m='1463820'>in</span> <span
  m='1464660'>the</span> <span m='1465290'>fast</span> <span
  m='1465650'>Fourier</span> <span m='1466040'>transform</span> <span
  m='1466670'>algorithm.</span> <span m='1467300'>It's</span> <span
  m='1467510'>basically</span> <span m='1468710'>that</span> <span
  m='1468950'>periodicity</span> <span m='1470060'>in</span> <span
  m='1470190'>the</span> <span m='1470270'>discrete</span> <span
  m='1470660'>Fourier</span> <span m='1471080'>transform</span> <span
  m='1472220'>that</span> <span m='1472340'>will</span> <span
  m='1472460'>lead</span> <span m='1472760'>to</span> <span
  m='1472910'>the</span> <span m='1473030'>kind</span> <span
  m='1473270'>of</span> <span m='1473360'>computational</span> <span
  m='1474140'>efficiency</span> <span m='1474800'>that's</span> <span
  m='1474980'>about</span> <span m='1475280'>to</span> <span
  m='1475400'>result.</span> </p><p><span m='1476630'>All</span> <span
  m='1476720'>right,</span> <span m='1476960'>so</span> <span
  m='1477410'>let's</span> <span m='1477980'>look</span> <span
  m='1478280'>then</span> <span m='1478760'>at</span> <span
  m='1479000'>how</span> <span m='1479240'>we</span> <span
  m='1479450'>would</span> <span m='1479750'>actually</span> <span
  m='1480260'>do</span> <span m='1480440'>the</span> <span
  m='1480560'>computation</span> <span m='1481580'>of</span> <span
  m='1482330'>the</span> <span m='1482420'>discrete</span> <span
  m='1482810'>Fourier</span> <span m='1483230'>transform.</span> <span
  m='1484970'>We</span> <span m='1485090'>know</span> <span
  m='1485330'>then</span> <span m='1486320'>that</span> <span
  m='1487280'>we</span> <span m='1487730'>will</span> <span
  m='1487940'>break</span> <span m='1488210'>the</span> <span
  m='1488330'>computation</span> <span m='1490430'>into</span> <span
  m='1491600'>a</span> <span m='1491660'>computation</span> <span
  m='1493370'>involving</span> <span m='1494420'>the</span> <span
  m='1496010'>even-numbered</span> <span m='1497060'>points</span> <span
  m='1497510'>and</span> <span m='1497600'>x</span> <span m='1497830'>of</span>
  <span m='1498110'>n</span> <span m='1499280'>and</span> <span
  m='1500060'>the</span> <span m='1500210'>odd-numbered</span> <span
  m='1500810'>points</span> <span m='1501200'>and</span> <span
  m='1501290'>x</span> <span m='1501530'>of</span> <span m='1501650'>n.</span>
  <span m='1502880'>Compute</span> <span m='1503150'>an</span> <span
  m='1503420'>N/2</span> <span m='1504335'>point</span> <span
  m='1504620'>discrete</span> <span m='1505010'>Fourier</span> <span
  m='1505400'>transform</span> <span m='1506750'>to</span> <span
  m='1506840'>obtain</span> <span m='1507200'>the</span> <span
  m='1507290'>sequence</span> <span m='1508130'>G</span> <span
  m='1508370'>of</span> <span m='1508490'>k,</span> <span
  m='1509720'>another</span> <span m='1510270'>N/2</span> <span
  m='1510785'>point</span> <span m='1511040'>discrete</span> <span
  m='1511400'>Fourier</span> <span m='1511790'>transform</span> <span
  m='1512510'>to</span> <span m='1512630'>compute</span> <span
  m='1512990'>the</span> <span m='1513080'>sequence</span> <span
  m='1513800'>H</span> <span m='1514070'>of</span> <span m='1514190'>k,</span>
  <span m='1515090'>and</span> <span m='1515210'>then</span> <span
  m='1515390'>combine</span> <span m='1516350'>the</span> <span
  m='1516440'>results</span> <span m='1516890'>together</span> <span
  m='1517940'>by</span> <span m='1518390'>multiplying</span> <span
  m='1519080'>H</span> <span m='1519320'>of</span> <span m='1519440'>k</span>
  <span m='1519740'>by</span> <span m='1519950'>W sub</span> <span
  m='1520340'>N</span> <span m='1520730'>to</span> <span m='1520850'>the</span>
  <span m='1520970'>k</span> <span m='1521720'>and</span> <span
  m='1521900'>adding</span> <span m='1522330'>that</span> <span
  m='1522850'>to</span> <span m='1522980'>G of</span> <span
  m='1523360'>k.</span> </p><p><span m='1524510'>I'll</span> <span
  m='1524660'>illustrate</span> <span m='1525860'>the</span> <span
  m='1526070'>computation,</span> <span m='1526820'>incidentally,</span> <span
  m='1528140'>with</span> <span m='1529190'>choosing</span> <span
  m='1529820'>N</span> <span m='1530210'>equal</span> <span
  m='1530600'>to</span> <span m='1530750'>8,</span> <span
  m='1531230'>simply</span> <span m='1531920'>because</span> <span
  m='1532220'>I</span> <span m='1532310'>have</span> <span m='1532490'>to</span>
  <span m='1532580'>choose</span> <span m='1532850'>N</span> <span
  m='1532970'>equal</span> <span m='1533210'>to</span> <span
  m='1533330'>something.</span> <span m='1534450'>And</span> <span
  m='1534470'>it</span> <span m='1534530'>turns</span> <span
  m='1534920'>out,</span> <span m='1535160'>interestingly</span> <span
  m='1535820'>enough,</span> <span m='1536690'>that</span> <span
  m='1537505'>N</span> <span m='1537810'>equals</span> <span
  m='1538340'>8</span> <span m='1538880'>is</span> <span
  m='1539120'>sufficiently</span> <span m='1540800'>general,</span> <span
  m='1541880'>so</span> <span m='1542150'>that</span> <span
  m='1542570'>you</span> <span m='1542750'>can</span> <span
  m='1542900'>infer</span> <span m='1543320'>the</span> <span
  m='1544130'>generality</span> <span m='1544940'>for</span> <span
  m='1545150'>N</span> <span m='1545300'>equal</span> <span
  m='1545660'>to</span> <span m='1546080'>an</span> <span
  m='1546200'>arbitrary</span> <span m='1546710'>power</span> <span
  m='1547070'>of</span> <span m='1547190'>2</span> <span m='1547850'>just</span>
  <span m='1548120'>from</span> <span m='1548870'>the</span> <span
  m='1549410'>computational</span> <span m='1550520'>issues</span> <span
  m='1550940'>that</span> <span m='1551210'>we'll</span> <span
  m='1551420'>raise</span> <span m='1551960'>for</span> <span
  m='1552080'>this</span> <span m='1552260'>particular</span> <span
  m='1552770'>case.</span> <span m='1553760'>All</span> <span
  m='1553850'>right,</span> <span m='1554090'>so</span> <span
  m='1554630'>we</span> <span m='1554810'>have</span> <span
  m='1554990'>N/2</span> <span m='1555440'>point</span> <span
  m='1555910'>DFT</span> <span m='1556850'>of</span> <span
  m='1557090'>the</span> <span m='1557240'>even-numbered</span> <span
  m='1557870'>points,</span> <span m='1559110'>the</span> <span
  m='1559310'>N/2</span> <span m='1559670'>point</span> <span
  m='1560060'>DFT</span> <span m='1560840'>of</span> <span
  m='1561020'>the</span> <span m='1561140'>odd-numbered</span> <span
  m='1561680'>points.</span> </p><p><span m='1563210'>And</span> <span
  m='1563330'>now,</span> <span m='1564260'>to</span> <span
  m='1564410'>compute</span> <span m='1565640'>the</span> <span
  m='1566330'>output</span> <span m='1566810'>points,</span> <span
  m='1567470'>the</span> <span m='1567560'>discrete</span> <span
  m='1567920'>Fourier</span> <span m='1568280'>transform,</span> <span
  m='1569180'>X</span> <span m='1569450'>of</span> <span m='1569610'>k,</span>
  <span m='1572540'>we</span> <span m='1572750'>then</span> <span
  m='1574130'>want</span> <span m='1574460'>to</span> <span
  m='1574880'>take</span> <span m='1576170'>G</span> <span m='1576410'>of</span>
  <span m='1576530'>0</span> <span m='1578450'>and</span> <span
  m='1578660'>add</span> <span m='1578960'>it</span> <span m='1579350'>to</span>
  <span m='1579650'>H</span> <span m='1579960'>of 0</span> <span
  m='1580610'>multiplied</span> <span m='1581280'>by</span> <span m='1581480'>W
  sub</span> <span m='1581870'>N</span> <span m='1582260'>to</span> <span
  m='1582390'>the</span> <span m='1582500'>0.</span> <span m='1583790'>So</span>
  <span m='1584300'>using</span> <span m='1584720'>flow</span> <span
  m='1585020'>graph</span> <span m='1585380'>notation,</span> <span
  m='1586820'>we</span> <span m='1586970'>have</span> <span m='1587300'>G</span>
  <span m='1587530'>of</span> <span m='1587650'>0</span> <span
  m='1589040'>added</span> <span m='1589880'>to</span> <span
  m='1590320'>H</span> <span m='1590600'>of</span> <span m='1590870'>0</span>
  <span m='1592010'>multiplied</span> <span m='1592880'>by</span> <span
  m='1593120'>W sub</span> <span m='1593515'>N</span> <span
  m='1593910'>so</span> <span m='1594020'>the</span> <span m='1594150'>0.</span>
  <span m='1596370'>For</span> <span m='1596550'>x</span> <span
  m='1596760'>of</span> <span m='1596910'>1,</span> <span m='1597510'>we</span>
  <span m='1597690'>want</span> <span m='1598170'>G</span> <span
  m='1598470'>of</span> <span m='1598590'>1</span> <span
  m='1599580'>added</span> <span m='1600030'>to</span> <span
  m='1600930'>H</span> <span m='1601230'>of</span> <span m='1601380'>1</span>
  <span m='1601950'>multiplied</span> <span m='1602640'>by</span> <span
  m='1602850'>W sub</span> <span m='1603225'>N</span> <span
  m='1603600'>to</span> <span m='1603720'>the</span> <span m='1603810'>1.</span>
  <span m='1605830'>For</span> <span m='1606220'>x</span> <span
  m='1606490'>of</span> <span m='1606610'>2,</span> <span m='1607180'>we</span>
  <span m='1607360'>want</span> <span m='1608020'>G</span> <span
  m='1608290'>of</span> <span m='1608410'>2</span> <span m='1609400'>plus</span>
  <span m='1610030'>H</span> <span m='1610300'>of</span> <span
  m='1610420'>2</span> <span m='1611050'>multiplied</span> <span
  m='1611710'>by</span> <span m='1611860'>W sub</span> <span
  m='1612220'>N</span> <span m='1612580'>squared.</span> <span
  m='1613630'>And</span> <span m='1614090'>for</span> <span m='1614570'>x</span>
  <span m='1614890'>of</span> <span m='1615010'>3,</span> <span
  m='1615590'>likewise,</span> <span m='1616660'>G</span> <span
  m='1616900'>of</span> <span m='1617050'>3</span> <span
  m='1617590'>added</span> <span m='1618010'>to</span> <span
  m='1618390'>H</span> <span m='1618670'>of</span> <span m='1618790'>3</span>
  <span m='1619360'>multiplied</span> <span m='1620020'>by</span> <span
  m='1620260'>W sub</span> <span m='1620670'>N</span> <span
  m='1621080'>cubed.</span> <span m='1621970'>So</span> <span
  m='1622870'>that</span> <span m='1623560'>computation,</span> <span
  m='1624490'>then,</span> <span m='1625180'>gives</span> <span
  m='1625480'>us</span> <span m='1625690'>x</span> <span m='1625990'>of</span>
  <span m='1626080'>0</span> <span m='1626890'>through</span> <span
  m='1627430'>x</span> <span m='1627700'>of</span> <span m='1627790'>3.</span>
  </p><p><span m='1629650'>For</span> <span m='1629800'>x</span> <span
  m='1630020'>of</span> <span m='1630100'>4,</span> <span m='1631750'>we</span>
  <span m='1631900'>want</span> <span m='1632140'>G of</span> <span
  m='1632470'>4</span> <span m='1633700'>plus</span> <span m='1634270'>W</span>
  <span m='1634670'>sub N</span> <span m='1635070'>to the</span> <span
  m='1635170'>4</span> <span m='1635500'>times</span> <span m='1635830'>H</span>
  <span m='1636070'>of</span> <span m='1636160'>4.</span> <span
  m='1637420'>But</span> <span m='1637540'>what's</span> <span m='1637810'>G
  of</span> <span m='1638110'>4?</span> <span m='1639190'>G</span> <span
  m='1639430'>of</span> <span m='1639520'>4</span> <span m='1640120'>is</span>
  <span m='1640330'>equal</span> <span m='1640570'>to</span> <span
  m='1640720'>G</span> <span m='1640960'>of</span> <span m='1641050'>0,</span>
  <span m='1642130'>because</span> <span m='1642580'>of</span> <span
  m='1642640'>the</span> <span m='1642760'>fact</span> <span
  m='1643420'>that</span> <span m='1643570'>G of</span> <span
  m='1643790'>k</span> <span m='1644950'>is</span> <span
  m='1645100'>periodic</span> <span m='1646210'>with</span> <span
  m='1646480'>period</span> <span m='1647040'>4.</span> <span
  m='1647560'>This</span> <span m='1647770'>is</span> <span m='1647890'>a</span>
  <span m='1647950'>four-point</span> <span m='1648330'>DFT</span> <span
  m='1648730'>that</span> <span m='1649040'>we're</span> <span
  m='1649210'>computing.</span> <span m='1650190'>So</span> <span
  m='1650350'>G</span> <span m='1650590'>of</span> <span m='1650710'>k</span>
  <span m='1651130'>is</span> <span m='1651280'>periodic</span> <span
  m='1651910'>with</span> <span m='1652030'>period</span> <span
  m='1652480'>4.</span> <span m='1653350'>And</span> <span
  m='1653470'>consequently,</span> <span m='1655040'>H</span> <span
  m='1655470'>of</span> <span m='1656110'>4</span> <span m='1656470'>and</span>
  <span m='1656830'>G</span> <span m='1657070'>of</span> <span
  m='1657160'>4</span> <span m='1658030'>are</span> <span
  m='1658180'>equal</span> <span m='1658630'>to</span> <span m='1659080'>H
  of</span> <span m='1659500'>0</span> <span m='1660100'>and</span> <span
  m='1660460'>G</span> <span m='1660630'>of</span> <span m='1660790'>0.</span>
  </p><p><span m='1661870'>So</span> <span m='1662470'>to</span> <span
  m='1662620'>compute</span> <span m='1663340'>the</span> <span
  m='1664180'>next</span> <span m='1664750'>four</span> <span
  m='1665050'>points,</span> <span m='1667000'>we</span> <span
  m='1667150'>can</span> <span m='1667300'>likewise</span> <span
  m='1668440'>use</span> <span m='1680790'>the</span> <span
  m='1681000'>outputs</span> <span m='1681600'>of</span> <span
  m='1682020'>these</span> <span m='1682320'>N/2</span> <span
  m='1682740'>point</span> <span m='1683145'>DFTs.</span> <span
  m='1685560'>To</span> <span m='1685680'>compute</span> <span
  m='1686070'>x</span> <span m='1686310'>of</span> <span m='1686400'>4,</span>
  <span m='1687660'>we</span> <span m='1687780'>want</span> <span m='1687990'>G
  of</span> <span m='1688310'>4,</span> <span m='1688900'>which</span> <span
  m='1689010'>is</span> <span m='1689130'>equal</span> <span
  m='1689370'>to</span> <span m='1689490'>G</span> <span m='1689700'>of</span>
  <span m='1689790'>0,</span> <span m='1690240'>because</span> <span
  m='1690570'>of</span> <span m='1690660'>the</span> <span
  m='1690750'>periodicity,</span> <span m='1692400'>plus</span> <span
  m='1692700'>W sub</span> <span m='1693150'>N</span> <span
  m='1693600'>to</span> <span m='1693830'>4</span> <span
  m='1694260'>times</span> <span m='1694590'>H</span> <span
  m='1694800'>of</span> <span m='1694890'>4.</span> <span m='1695520'>H</span>
  <span m='1695730'>of</span> <span m='1695820'>4</span> <span
  m='1696030'>is</span> <span m='1696120'>equal</span> <span
  m='1696330'>to</span> <span m='1696420'>H of</span> <span
  m='1696760'>0.</span> <span m='1697830'>So</span> <span m='1698460'>we</span>
  <span m='1698640'>have</span> <span m='1698910'>then</span> <span
  m='1699120'>for</span> <span m='1699300'>x</span> <span m='1699610'>of</span>
  <span m='1699850'>4,</span> <span m='1700470'>G</span> <span
  m='1700755'>of</span> <span m='1701040'>0</span> <span m='1701700'>plus</span>
  <span m='1702000'>W sub</span> <span m='1702375'>N</span> <span
  m='1702750'>to</span> <span m='1702950'>4</span> <span
  m='1703640'>times</span> <span m='1703980'>H</span> <span
  m='1704190'>of</span> <span m='1704310'>0.</span> <span
  m='1705730'>Likewise,</span> <span m='1706380'>for</span> <span
  m='1707460'>x</span> <span m='1707730'>of</span> <span m='1707820'>5,</span>
  <span m='1709200'>we</span> <span m='1709260'>have</span> <span m='1709440'>G
  of</span> <span m='1709650'>5,</span> <span m='1710040'>or</span> <span
  m='1710280'>G</span> <span m='1710640'>of</span> <span m='1710770'>1,</span>
  <span m='1712440'>plus</span> <span m='1713220'>W sub</span> <span
  m='1713550'>N</span> <span m='1713880'>to</span> <span m='1714000'>the</span>
  <span m='1714120'>5th</span> <span m='1714690'>times</span> <span
  m='1715120'>H of</span> <span m='1715470'>5,</span> <span
  m='1716280'>or</span> <span m='1716760'>H</span> <span m='1717000'>of</span>
  <span m='1717150'>1</span> <span m='1717390'>because</span> <span
  m='1717720'>of</span> <span m='1717810'>the</span> <span
  m='1717930'>periodicity,</span> <span m='1719160'>and</span> <span
  m='1719310'>likewise,</span> <span m='1720090'>down</span> <span
  m='1720390'>through</span> <span m='1720600'>the</span> <span
  m='1720720'>remaining</span> <span m='1721140'>four</span> <span
  m='1721410'>points.</span> </p><p><span m='1722560'>So</span> <span
  m='1723690'>we</span> <span m='1724050'>showed</span> <span
  m='1724560'>previous--</span> <span m='1725310'>on</span> <span
  m='1725400'>the</span> <span m='1725490'>previous</span> <span
  m='1725890'>view</span> <span m='1726060'>graph,</span> <span
  m='1726360'>the</span> <span m='1726480'>computation</span> <span
  m='1727170'>for</span> <span m='1727260'>the</span> <span
  m='1727350'>first</span> <span m='1727650'>four</span> <span
  m='1727920'>points.</span> <span m='1729310'>And</span> <span
  m='1729750'>here</span> <span m='1730020'>we</span> <span
  m='1730170'>have</span> <span m='1730350'>the</span> <span
  m='1730440'>computation</span> <span m='1731310'>for</span> <span
  m='1731460'>the</span> <span m='1731550'>last</span> <span
  m='1731850'>four</span> <span m='1732150'>points.</span> <span
  m='1733140'>Putting</span> <span m='1733410'>those</span> <span
  m='1733680'>two</span> <span m='1734040'>together</span> <span
  m='1734680'>then,</span> <span m='1735570'>the</span> <span
  m='1735660'>computation</span> <span m='1736920'>for</span> <span
  m='1737670'>the</span> <span m='1738740'>eight-point</span> <span
  m='1740250'>DFT</span> <span m='1742050'>is,</span> <span
  m='1743730'>as</span> <span m='1744180'>I've</span> <span
  m='1744360'>indicated</span> <span m='1744960'>here,</span> <span
  m='1746040'>the</span> <span m='1746220'>even-numbered</span> <span
  m='1746790'>points</span> <span m='1747330'>into</span> <span
  m='1747630'>an</span> <span m='1747750'>N/2</span> <span
  m='1747870'>point</span> <span m='1748080'>DFT,</span> <span
  m='1749850'>the</span> <span m='1750000'>odd-numbered</span> <span
  m='1750540'>points</span> <span m='1751050'>into</span> <span
  m='1751350'>an</span> <span m='1751440'>N/2</span> <span
  m='1751560'>point</span> <span m='1751770'>DFT,</span> <span
  m='1753630'>and</span> <span m='1754260'>the</span> <span
  m='1754380'>results</span> <span m='1755340'>combined</span> <span
  m='1755820'>together</span> <span m='1756870'>according</span> <span
  m='1757320'>to</span> <span m='1757410'>the</span> <span
  m='1757500'>computation</span> <span m='1758640'>that</span> <span
  m='1758790'>we've</span> <span m='1758940'>shown</span> <span
  m='1759240'>here.</span> </p><p><span m='1760600'>Now,</span> <span
  m='1761310'>a</span> <span m='1761400'>couple</span> <span
  m='1761730'>of</span> <span m='1762120'>things</span> <span
  m='1762420'>that</span> <span m='1762510'>I'd</span> <span
  m='1762630'>like</span> <span m='1762810'>to</span> <span
  m='1762900'>draw</span> <span m='1763140'>your</span> <span
  m='1763290'>attention</span> <span m='1763770'>to</span> <span
  m='1764250'>about</span> <span m='1765030'>the</span> <span
  m='1765150'>flow</span> <span m='1765420'>graph</span> <span
  m='1765780'>as</span> <span m='1765920'>it's</span> <span
  m='1766070'>developing.</span> <span m='1767430'>First</span> <span
  m='1767730'>of</span> <span m='1767850'>all,</span> <span
  m='1768460'>note</span> <span m='1768900'>that</span> <span
  m='1769650'>the</span> <span m='1769860'>flow</span> <span
  m='1770160'>graph,</span> <span m='1770790'>as</span> <span
  m='1771000'>we're</span> <span m='1771120'>looking</span> <span
  m='1771480'>at</span> <span m='1771630'>it</span> <span
  m='1771720'>here,</span> <span m='1772680'>involves</span> <span
  m='1773180'>a</span> <span m='1773250'>computation,</span> <span
  m='1774960'>which</span> <span m='1775500'>if</span> <span
  m='1775710'>we</span> <span m='1775920'>were</span> <span
  m='1776190'>to</span> <span m='1776370'>just</span> <span
  m='1776910'>pull</span> <span m='1777210'>out</span> <span
  m='1778200'>the</span> <span m='1778380'>computation</span> <span
  m='1779220'>of</span> <span m='1779340'>these</span> <span
  m='1779580'>two</span> <span m='1779790'>points,</span> <span
  m='1780300'>or</span> <span m='1780450'>these</span> <span
  m='1780720'>two</span> <span m='1780900'>points,</span> <span m='1781350'>et
  cetera,</span> <span m='1782550'>it</span> <span m='1782640'>has</span> <span
  m='1782970'>the</span> <span m='1783060'>structure</span> <span
  m='1784440'>of</span> <span m='1784890'>a</span> <span m='1784980'>set</span>
  <span m='1785490'>of</span> <span m='1786210'>butterfly-looking</span> <span
  m='1788190'>flow</span> <span m='1788490'>graphs.</span> <span
  m='1789450'>And,</span> <span m='1789570'>in</span> <span
  m='1789660'>fact,</span> <span m='1790230'>we'll</span> <span
  m='1790380'>find</span> <span m='1790680'>it</span> <span
  m='1790770'>convenient</span> <span m='1791820'>to</span> <span
  m='1792000'>refer</span> <span m='1792390'>to</span> <span
  m='1792570'>these</span> <span m='1793440'>as</span> <span
  m='1793650'>butterflies</span> <span m='1794760'>in</span> <span
  m='1794880'>the</span> <span m='1794970'>computation.</span> </p><p><span
  m='1797680'>The</span> <span m='1797800'>second</span> <span
  m='1798490'>thing</span> <span m='1798730'>that</span> <span
  m='1798850'>I'd</span> <span m='1798970'>like</span> <span
  m='1799150'>to</span> <span m='1799270'>draw</span> <span
  m='1799510'>your</span> <span m='1799660'>attention</span> <span
  m='1800170'>to</span> <span m='1800620'>is</span> <span
  m='1800980'>that</span> <span m='1801760'>the</span> <span
  m='1801850'>multiplications</span> <span m='1804190'>by</span> <span
  m='1804400'>powers</span> <span m='1804910'>of</span> <span
  m='1805020'>W</span> <span m='1807110'>always</span> <span
  m='1807950'>are</span> <span m='1808190'>applied</span> <span
  m='1809630'>to</span> <span m='1810350'>the</span> <span
  m='1810830'>branches</span> <span m='1811940'>which</span> <span
  m='1812390'>come</span> <span m='1813020'>from</span> <span
  m='1813620'>this</span> <span m='1813830'>bottom</span> <span
  m='1814220'>transform.</span> <span m='1814970'>And</span> <span
  m='1815090'>that's</span> <span m='1815330'>because</span> <span
  m='1816590'>we</span> <span m='1816740'>had</span> <span
  m='1816890'>the</span> <span m='1817010'>expression</span> <span
  m='1817550'>that</span> <span m='1817700'>X</span> <span m='1817930'>of</span>
  <span m='1818090'>k</span> <span m='1818390'>was</span> <span
  m='1818570'>equal</span> <span m='1818810'>to</span> <span m='1818930'>G of
  k</span> <span m='1820160'>plus</span> <span m='1820730'>W sub</span> <span
  m='1821040'>N</span> <span m='1821350'>to</span> <span m='1821560'>the</span>
  <span m='1821660'>k</span> <span m='1821930'>times</span> <span
  m='1822320'>H</span> <span m='1822590'>of</span> <span m='1822710'>k,</span>
  <span m='1823460'>and</span> <span m='1823580'>this</span> <span
  m='1823760'>was</span> <span m='1823940'>the</span> <span m='1824060'>H</span>
  <span m='1824270'>of</span> <span m='1824390'>k.</span> <span
  m='1825560'>So</span> <span m='1826460'>it's</span> <span
  m='1826760'>in</span> <span m='1826970'>the</span> <span
  m='1827180'>bottom</span> <span m='1827960'>branch</span> <span
  m='1828560'>of</span> <span m='1828710'>these</span> <span
  m='1828920'>butterflies</span> <span m='1830390'>that</span> <span
  m='1831230'>we</span> <span m='1831890'>see</span> <span
  m='1832370'>always</span> <span m='1833450'>the</span> <span
  m='1833540'>multiplication</span> <span m='1834410'>by</span> <span
  m='1834560'>these</span> <span m='1834770'>powers</span> <span
  m='1835160'>of</span> <span m='1835250'>W.</span> <span m='1836090'>And</span>
  <span m='1836180'>I</span> <span m='1836270'>say</span> <span
  m='1836540'>that,</span> <span m='1837050'>I</span> <span
  m='1837440'>want</span> <span m='1837620'>to</span> <span
  m='1837680'>point</span> <span m='1837950'>that</span> <span
  m='1838190'>out</span> <span m='1838600'>hit</span> <span
  m='1838850'>now,</span> <span m='1839210'>because</span> <span
  m='1840650'>it's</span> <span m='1840860'>somewhat</span> <span
  m='1841220'>difficult</span> <span m='1841760'>in</span> <span
  m='1841850'>drawing</span> <span m='1842210'>these</span> <span
  m='1842390'>flow</span> <span m='1842660'>graphs</span> <span
  m='1843620'>to</span> <span m='1843890'>always</span> <span
  m='1844310'>get</span> <span m='1844730'>these</span> <span
  m='1844940'>powers</span> <span m='1845300'>of</span> <span
  m='1845390'>W</span> <span m='1846860'>close</span> <span
  m='1847220'>enough</span> <span m='1847940'>to</span> <span
  m='1848060'>the</span> <span m='1848210'>arrow</span> <span
  m='1848610'>so</span> <span m='1848780'>that</span> <span
  m='1848930'>it's</span> <span m='1849050'>clear</span> <span
  m='1849320'>where</span> <span m='1849470'>the</span> <span
  m='1849590'>computation,</span> <span m='1850850'>where</span> <span
  m='1850970'>the</span> <span m='1851060'>multiplication</span> <span
  m='1851840'>needs</span> <span m='1852050'>to</span> <span
  m='1852140'>be</span> <span m='1852230'>carried</span> <span
  m='1852620'>out.</span> </p><p><span m='1854110'>All</span> <span
  m='1854170'>right,</span> <span m='1854500'>so</span> <span
  m='1854770'>here's</span> <span m='1855040'>where</span> <span
  m='1855250'>we're</span> <span m='1855430'>at.</span> <span
  m='1856330'>We</span> <span m='1856690'>had</span> <span m='1856900'>counted
  out</span> <span m='1857380'>previously</span> <span m='1858400'>the</span>
  <span m='1858790'>number</span> <span m='1859150'>of</span> <span
  m='1859240'>complex</span> <span m='1859840'>multiplies</span> <span
  m='1860470'>and</span> <span m='1860560'>adds</span> <span
  m='1860840'>involved,</span> <span m='1861850'>and</span> <span
  m='1861970'>we</span> <span m='1862090'>found</span> <span
  m='1862750'>that</span> <span m='1863050'>it</span> <span
  m='1863230'>was</span> <span m='1864280'>on</span> <span
  m='1864430'>the</span> <span m='1864550'>order</span> <span
  m='1864940'>of</span> <span m='1865130'>N</span> <span m='1865750'>plus</span>
  <span m='1866350'>2</span> <span m='1866620'>times</span> <span
  m='1867280'>and</span> <span m='1867460'>over</span> <span
  m='1867700'>2</span> <span m='1867800'>squared,</span> <span
  m='1868870'>which</span> <span m='1869350'>is</span> <span
  m='1870490'>less</span> <span m='1870850'>than</span> <span
  m='1871210'>N</span> <span m='1871450'>squared.</span> <span
  m='1872080'>And</span> <span m='1872200'>consequently,</span> <span
  m='1873070'>this</span> <span m='1873280'>is</span> <span m='1873430'>a</span>
  <span m='1873490'>more</span> <span m='1873730'>efficient</span> <span
  m='1874180'>way</span> <span m='1874960'>to</span> <span
  m='1875080'>compute</span> <span m='1875530'>the</span> <span
  m='1875620'>discrete</span> <span m='1876010'>Fourier</span> <span
  m='1876370'>transform</span> <span m='1877510'>than</span> <span
  m='1877630'>simply</span> <span m='1878380'>a</span> <span
  m='1878440'>direct</span> <span m='1878770'>computation.</span> </p><p><span
  m='1880540'>However,</span> <span m='1882770'>like</span> <span
  m='1883040'>this</span> <span m='1883670'>assumes</span> <span
  m='1885140'>that</span> <span m='1886430'>we're</span> <span
  m='1886610'>going</span> <span m='1886880'>to</span> <span
  m='1887030'>compute</span> <span m='1887450'>these</span> <span
  m='1887780'>N/2</span> <span m='1888140'>point</span> <span
  m='1888483'>DFTs</span> <span m='1890660'>as</span> <span m='1890900'>a</span>
  <span m='1890960'>direct</span> <span m='1891290'>computation.</span> <span
  m='1893130'>But</span> <span m='1893330'>in</span> <span
  m='1893510'>fact,</span> <span m='1894360'>if</span> <span
  m='1894880'>N/2</span> <span m='1895840'>is</span> <span m='1895970'>a</span>
  <span m='1896030'>composite</span> <span m='1896600'>number,</span> <span
  m='1896990'>in</span> <span m='1897080'>particular</span> <span
  m='1897620'>a</span> <span m='1897680'>power</span> <span
  m='1898100'>of</span> <span m='1898190'>2,</span> <span
  m='1899210'>which</span> <span m='1899420'>it</span> <span
  m='1899540'>is</span> <span m='1899900'>if</span> <span m='1900080'>N</span>
  <span m='1900260'>was</span> <span m='1900410'>a</span> <span
  m='1900470'>power</span> <span m='1900890'>of</span> <span
  m='1901030'>2,</span> <span m='1902060'>then</span> <span
  m='1902450'>we</span> <span m='1902630'>can</span> <span
  m='1902780'>apply</span> <span m='1903140'>the</span> <span
  m='1903260'>same</span> <span m='1903590'>strategy</span> <span
  m='1904880'>to</span> <span m='1904970'>the</span> <span
  m='1905090'>computation</span> <span m='1906140'>of</span> <span
  m='1906800'>these</span> <span m='1907100'>N/2</span> <span
  m='1907580'>point</span> <span m='1907990'>DFTs.</span> <span
  m='1909530'>So</span> <span m='1910130'>we</span> <span m='1910310'>can</span>
  <span m='1910460'>break</span> <span m='1910760'>these</span> <span
  m='1910970'>N/2</span> <span m='1911090'>point</span> <span
  m='1911330'>DFT</span> <span m='1912350'>computations</span> <span
  m='1914090'>into--</span> <span m='1915920'>each</span> <span
  m='1916160'>one</span> <span m='1916370'>of</span> <span
  m='1916490'>these--</span> <span m='1916940'>into</span> <span
  m='1917360'>two</span> <span m='1917960'>N/4</span> <span
  m='1918770'>point</span> <span m='1919160'>DFTs</span> <span
  m='1920870'>plus</span> <span m='1921620'>some</span> <span
  m='1922340'>additional</span> <span m='1923570'>arithmetic</span> <span
  m='1925040'>in</span> <span m='1925160'>order</span> <span
  m='1925550'>to</span> <span m='1925730'>form</span> <span
  m='1926210'>the</span> <span m='1926330'>N/2</span> <span
  m='1926990'>point</span> <span m='1927490'>DFTs.</span> </p><p><span
  m='1929250'>So</span> <span m='1929850'>each</span> <span
  m='1930120'>one</span> <span m='1930300'>of</span> <span
  m='1930420'>the</span> <span m='1930660'>N/2</span> <span
  m='1931040'>point</span> <span m='1931513'>DFTs</span> <span
  m='1933210'>can</span> <span m='1933420'>then</span> <span
  m='1933840'>be</span> <span m='1934020'>decomposed</span> <span
  m='1937140'>into</span> <span m='1938400'>an N/4</span> <span
  m='1939300'>point</span> <span m='1940350'>DFT</span> <span
  m='1940890'>computation,</span> <span m='1942690'>into</span> <span
  m='1942930'>two</span> <span m='1943260'>N/4</span> <span
  m='1943920'>point</span> <span m='1944190'>DFT</span> <span
  m='1944700'>computations.</span> <span m='1946440'>In</span> <span
  m='1946560'>particular,</span> <span m='1948270'>we</span> <span
  m='1948420'>had,</span> <span m='1948960'>recall,</span> <span
  m='1950220'>for</span> <span m='1950850'>the</span> <span
  m='1951420'>top</span> <span m='1951780'>half</span> <span
  m='1952380'>of</span> <span m='1952560'>the</span> <span
  m='1952650'>previous</span> <span m='1953370'>view</span> <span
  m='1953580'>graph,</span> <span m='1954600'>the</span> <span
  m='1954780'>even-numbered</span> <span m='1955950'>points</span> <span
  m='1956820'>in</span> <span m='1956910'>the</span> <span
  m='1957000'>original</span> <span m='1957390'>sequence.</span> <span
  m='1958890'>All</span> <span m='1958950'>right,</span> <span
  m='1959190'>now</span> <span m='1959490'>we</span> <span
  m='1959640'>want</span> <span m='1959790'>to</span> <span
  m='1959850'>compute</span> <span m='1960180'>the</span> <span
  m='1960300'>DFT</span> <span m='1961050'>of</span> <span
  m='1961140'>those</span> <span m='1961380'>even-numbered</span> <span
  m='1962010'>points.</span> <span m='1963100'>So</span> <span
  m='1963420'>we</span> <span m='1963570'>can</span> <span m='1963750'>go</span>
  <span m='1963990'>through</span> <span m='1964230'>exactly</span> <span
  m='1964710'>the</span> <span m='1964800'>same</span> <span
  m='1965100'>steps.</span> <span m='1965670'>We</span> <span
  m='1965820'>can</span> <span m='1966000'>break</span> <span
  m='1966300'>that</span> <span m='1966660'>into</span> <span
  m='1967820'>its</span> <span m='1968100'>even-numbered</span> <span
  m='1968730'>points</span> <span m='1969360'>and</span> <span
  m='1969540'>its</span> <span m='1969840'>odd</span> <span
  m='1970080'>numbered</span> <span m='1970440'>points.</span> </p><p><span
  m='1972550'>So</span> <span m='1972630'>we</span> <span
  m='1972780'>have</span> <span m='1973380'>the</span> <span
  m='1973560'>even</span> <span m='1973890'>numbered</span> <span
  m='1974220'>of</span> <span m='1974340'>the</span> <span
  m='1974430'>even-numbered</span> <span m='1975090'>points</span> <span
  m='1976590'>into</span> <span m='1977130'>an</span> <span
  m='1977250'>N/4</span> <span m='1978112'>point</span> <span
  m='1978584'>DFT,</span> <span m='1980280'>the</span> <span
  m='1980460'>odd</span> <span m='1980820'>numbered</span> <span
  m='1981330'>of</span> <span m='1981480'>the</span> <span
  m='1981630'>even-numbered</span> <span m='1982290'>points</span> <span
  m='1983400'>into</span> <span m='1984030'>a</span> <span
  m='1984120'>second</span> <span m='1984560'>N/4</span> <span
  m='1985230'>point</span> <span m='1985560'>DFT,</span> <span
  m='1987060'>and</span> <span m='1987210'>then</span> <span
  m='1987720'>those</span> <span m='1988080'>results</span> <span
  m='1988650'>are</span> <span m='1988740'>combined</span> <span
  m='1989910'>in</span> <span m='1990060'>exactly</span> <span
  m='1990720'>the</span> <span m='1990810'>same</span> <span
  m='1991170'>way</span> <span m='1991980'>as</span> <span
  m='1992520'>the</span> <span m='1992810'>N/2</span> <span
  m='1993040'>point</span> <span m='1993780'>DFTs</span> <span
  m='1994470'>were</span> <span m='1994620'>combined</span> <span
  m='1995400'>in</span> <span m='1996360'>the</span> <span
  m='1996480'>previous</span> <span m='1996960'>view</span> <span
  m='1997140'>graph,</span> <span m='1997890'>but</span> <span
  m='1998100'>now</span> <span m='1998790'>with</span> <span
  m='1999840'>N/2</span> <span m='2001010'>as</span> <span
  m='2001310'>the</span> <span m='2001400'>subscript</span> <span
  m='2002420'>rather</span> <span m='2002780'>than</span> <span
  m='2002960'>N</span> <span m='2003320'>as</span> <span m='2003500'>the</span>
  <span m='2003590'>subscript,</span> <span m='2004160'>because</span> <span
  m='2004880'>here</span> <span m='2005240'>what</span> <span
  m='2005420'>we're</span> <span m='2005600'>computing</span> <span
  m='2006670'>is</span> <span m='2006880'>an</span> <span m='2007010'>N/2</span>
  <span m='2007190'>point</span> <span m='2007430'>DFT.</span> <span
  m='2010310'>However,</span> <span m='2010670'>in</span> <span
  m='2010760'>drawing</span> <span m='2011060'>the</span> <span
  m='2011150'>flow</span> <span m='2011420'>graph,</span> <span
  m='2012020'>we</span> <span m='2012230'>can</span> <span
  m='2012410'>re-express</span> <span m='2013970'>the</span> <span
  m='2014180'>powers</span> <span m='2014750'>of</span> <span m='2014870'>W
  sub</span> <span m='2015215'>N</span> <span m='2015560'>over</span> <span
  m='2015830'>2</span> <span m='2016820'>in</span> <span
  m='2016970'>terms</span> <span m='2017420'>of</span> <span
  m='2017510'>powers</span> <span m='2017990'>of</span> <span m='2018110'>W
  sub</span> <span m='2018470'>N,</span> <span m='2019520'>because</span> <span
  m='2019940'>of</span> <span m='2020030'>the</span> <span
  m='2020150'>fact</span> <span m='2020960'>that</span> <span m='2021080'>W
  sub</span> <span m='2021425'>N</span> <span m='2021770'>squared</span> <span
  m='2022640'>is</span> <span m='2022820'>equal</span> <span
  m='2023060'>to</span> <span m='2023180'>W sub</span> <span
  m='2023540'>N</span> <span m='2023900'>over</span> <span m='2024140'>2</span>
  <span m='2024770'>or</span> <span m='2024980'>vice</span> <span
  m='2025250'>versa.</span> </p><p><span m='2027120'>All</span> <span
  m='2027220'>right,</span> <span m='2027380'>so</span> <span
  m='2027770'>we</span> <span m='2027950'>have</span> <span
  m='2028220'>this</span> <span m='2028490'>then</span> <span
  m='2029480'>apply</span> <span m='2029930'>to</span> <span
  m='2030050'>the</span> <span m='2030200'>even-numbered</span> <span
  m='2030860'>points</span> <span m='2032150'>and</span> <span
  m='2032390'>to</span> <span m='2032540'>the</span> <span
  m='2032690'>odd-numbered</span> <span m='2033260'>points.</span> <span
  m='2033710'>And</span> <span m='2033800'>when</span> <span
  m='2033950'>we</span> <span m='2034100'>do</span> <span
  m='2034310'>that,</span> <span m='2035060'>then</span> <span
  m='2035690'>the</span> <span m='2035990'>flow</span> <span
  m='2036290'>graph</span> <span m='2037250'>that</span> <span
  m='2037430'>results</span> <span m='2040140'>is</span> <span
  m='2041700'>as</span> <span m='2042090'>I've</span> <span
  m='2042240'>indicated</span> <span m='2042830'>here.</span> <span
  m='2044910'>We</span> <span m='2045330'>have</span> <span
  m='2045870'>the</span> <span m='2046080'>even</span> <span
  m='2046320'>numbered</span> <span m='2046620'>of</span> <span
  m='2046710'>the</span> <span m='2046800'>even-numbered</span> <span
  m='2047490'>points</span> <span m='2048040'>and</span> <span
  m='2048179'>the</span> <span m='2048300'>odd</span> <span
  m='2048540'>numbered</span> <span m='2048929'>of</span> <span
  m='2049020'>the</span> <span m='2049139'>even-numbered</span> <span
  m='2049710'>points.</span> <span m='2050969'>We</span> <span
  m='2051150'>have</span> <span m='2051659'>the</span> <span
  m='2051840'>even</span> <span m='2052110'>numbered</span> <span
  m='2052409'>of</span> <span m='2052530'>the</span> <span
  m='2052650'>odd-numbered</span> <span m='2053219'>points</span> <span
  m='2053760'>and</span> <span m='2053880'>the</span> <span
  m='2054030'>odd</span> <span m='2054239'>numbered</span> <span
  m='2054630'>of</span> <span m='2054719'>the</span> <span
  m='2054870'>odd-numbered</span> <span m='2055380'>points.</span> <span
  m='2057480'>Those</span> <span m='2058050'>are</span> <span
  m='2058380'>each</span> <span m='2058650'>going</span> <span
  m='2059010'>into</span> <span m='2059460'>N/4</span> <span
  m='2059850'>point</span> <span m='2060210'>DFTs.</span> </p><p><span
  m='2063429'>Here</span> <span m='2064000'>is</span> <span
  m='2064239'>then</span> <span m='2064840'>the</span> <span
  m='2064929'>sequence</span> <span m='2065969'>G</span> <span
  m='2066219'>of</span> <span m='2066409'>k.</span> <span m='2069429'>I'm</span>
  <span m='2069550'>sorry.</span> <span m='2069850'>Here</span> <span
  m='2070090'>is</span> <span m='2070210'>the</span> <span
  m='2070300'>sequence</span> <span m='2071170'>G</span> <span
  m='2071409'>of</span> <span m='2071530'>k.</span> <span
  m='2073030'>Here</span> <span m='2073210'>is</span> <span
  m='2073330'>the</span> <span m='2073420'>sequence</span> <span
  m='2073900'>H</span> <span m='2074170'>of</span> <span m='2074320'>k.</span>
  <span m='2075699'>This</span> <span m='2076179'>then</span> <span
  m='2078219'>implements</span> <span m='2078760'>the</span> <span
  m='2078850'>computation</span> <span m='2079719'>of</span> <span
  m='2079960'>the</span> <span m='2080080'>N/2</span> <span
  m='2080199'>point</span> <span m='2080409'>DFTs</span> <span
  m='2081580'>that</span> <span m='2081699'>we</span> <span
  m='2081850'>had</span> <span m='2082030'>before.</span> <span
  m='2083110'>And</span> <span m='2083739'>then</span> <span
  m='2084159'>we</span> <span m='2084340'>have</span> <span
  m='2084550'>the</span> <span m='2084670'>output</span> <span
  m='2085540'>DFT</span> <span m='2086350'>obtained</span> <span
  m='2086770'>by</span> <span m='2086980'>combining</span> <span
  m='2087489'>those.</span> <span m='2088900'>So</span> <span
  m='2090409'>this</span> <span m='2090889'>flow</span> <span
  m='2091190'>graph</span> <span m='2091580'>results</span> <span
  m='2092150'>from</span> <span m='2092360'>simply</span> <span
  m='2092750'>carrying</span> <span m='2093260'>the</span> <span
  m='2093350'>previous</span> <span m='2093830'>strategy</span> <span
  m='2094969'>back</span> <span m='2095300'>one</span> <span
  m='2095570'>step</span> <span m='2096440'>to</span> <span
  m='2096590'>implementing</span> <span m='2097520'>the</span> <span
  m='2097670'>N/2</span> <span m='2098030'>point</span> <span
  m='2098503'>DFTs.</span> </p><p><span m='2100300'>All</span> <span
  m='2100370'>right,</span> <span m='2100580'>well,</span> <span
  m='2100760'>now</span> <span m='2101000'>we</span> <span
  m='2101150'>have</span> <span m='2101240'>the</span> <span
  m='2101360'>computation</span> <span m='2102350'>of</span> <span
  m='2102990'>N/4</span> <span m='2103520'>point</span> <span
  m='2104110'>DFTs.</span> <span m='2106040'>And</span> <span
  m='2106700'>we</span> <span m='2106910'>can</span> <span m='2107180'>do</span>
  <span m='2107510'>exactly</span> <span m='2108110'>the</span> <span
  m='2108230'>same</span> <span m='2108560'>thing</span> <span
  m='2109550'>with</span> <span m='2110030'>the N/4</span> <span
  m='2110550'>point</span> <span m='2110913'>DFTs,</span> <span
  m='2113090'>except</span> <span m='2113540'>that</span> <span
  m='2114170'>for</span> <span m='2114320'>this</span> <span
  m='2114500'>particular</span> <span m='2115070'>example,</span> <span
  m='2116310'>N/4--</span> <span m='2117680'>if</span> <span
  m='2117840'>N</span> <span m='2117960'>is</span> <span
  m='2118070'>equal</span> <span m='2118310'>to</span> <span
  m='2118370'>8,</span> <span m='2118610'>N/4</span> <span m='2119210'>is</span>
  <span m='2119330'>equal</span> <span m='2119600'>to</span> <span
  m='2119800'>2.</span> <span m='2120950'>The</span> <span
  m='2121070'>computation</span> <span m='2122150'>of</span> <span
  m='2122680'>the</span> <span m='2122810'>two-point</span> <span
  m='2123180'>DFTs</span> <span m='2124490'>is</span> <span m='2125330'>a</span>
  <span m='2125930'>relatively</span> <span m='2126530'>straightforward</span>
  <span m='2127310'>thing.</span> <span m='2128130'>But</span> <span
  m='2128300'>in</span> <span m='2128480'>general,</span> <span
  m='2129530'>if</span> <span m='2129690'>N</span> <span
  m='2129920'>wasn't</span> <span m='2130310'>equal</span> <span
  m='2130580'>to</span> <span m='2130710'>8,</span> <span m='2130940'>if</span>
  <span m='2131060'>it</span> <span m='2131180'>was</span> <span
  m='2131660'>a</span> <span m='2131690'>more</span> <span
  m='2131930'>general</span> <span m='2132320'>power</span> <span
  m='2132680'>of</span> <span m='2132800'>2,</span> <span m='2133580'>we</span>
  <span m='2133700'>could</span> <span m='2133850'>likewise</span> <span
  m='2134450'>apply</span> <span m='2134780'>this</span> <span
  m='2134930'>strategy</span> <span m='2135530'>to</span> <span
  m='2135620'>the</span> <span m='2135740'>computation</span> <span
  m='2136400'>of</span> <span m='2136490'>the</span> <span
  m='2136660'>N/4</span> <span m='2137120'>point</span> <span
  m='2137486'>DFTs,</span> <span m='2138220'>the</span> <span
  m='2138530'>N/8</span> <span m='2139050'>point</span> <span
  m='2139430'>DFTs,</span> <span m='2140140'>and</span> <span
  m='2140300'>over</span> <span m='2140480'>16</span> <span
  m='2140890'>point</span> <span m='2141210'>DFTs,</span> <span m='2141870'>et
  cetera,</span> <span m='2142760'>until</span> <span m='2143090'>we</span>
  <span m='2143240'>got</span> <span m='2143960'>to</span> <span
  m='2144590'>the</span> <span m='2144710'>computation</span> <span
  m='2145670'>of</span> <span m='2146200'>two-point</span> <span
  m='2146693'>DFTs.</span> </p><p><span m='2148950'>All</span> <span
  m='2149040'>right,</span> <span m='2149250'>so</span> <span
  m='2150060'>just</span> <span m='2150240'>simply</span> <span
  m='2150630'>inserting</span> <span m='2151080'>the</span> <span
  m='2151170'>computation</span> <span m='2151980'>for</span> <span
  m='2152100'>these</span> <span m='2152280'>two-point</span> <span
  m='2152850'>DFTs,</span> <span m='2153600'>which</span> <span
  m='2153780'>involves</span> <span m='2154140'>simply</span> <span
  m='2154530'>adding--</span> <span m='2157290'>well,</span> <span
  m='2157890'>adding</span> <span m='2158340'>x</span> <span
  m='2158610'>of</span> <span m='2158700'>4</span> <span m='2158970'>to</span>
  <span m='2159240'>x</span> <span m='2159510'>of</span> <span
  m='2159600'>0,</span> <span m='2160560'>multiplying</span> <span
  m='2161400'>x</span> <span m='2161610'>of</span> <span m='2161670'>4</span>
  <span m='2161970'>by</span> <span m='2162150'>W sub</span> <span
  m='2162525'>N</span> <span m='2162900'>to</span> <span m='2162990'>the</span>
  <span m='2163110'>4</span> <span m='2163620'>and</span> <span
  m='2163740'>adding it to</span> <span m='2164160'>x</span> <span
  m='2164460'>of</span> <span m='2164550'>0.</span> <span m='2165690'>The</span>
  <span m='2166170'>resulting</span> <span m='2167640'>flow</span> <span
  m='2167970'>graph</span> <span m='2169020'>for</span> <span
  m='2169590'>the</span> <span m='2169740'>entire</span> <span
  m='2170160'>computation</span> <span m='2172230'>is</span> <span
  m='2173400'>as</span> <span m='2173940'>I</span> <span m='2174180'>show</span>
  <span m='2174540'>here,</span> <span m='2175860'>where</span> <span
  m='2176610'>we</span> <span m='2176790'>have</span> <span
  m='2177510'>now</span> <span m='2178440'>the</span> <span
  m='2178770'>input</span> <span m='2179460'>points.</span> <span
  m='2180990'>We</span> <span m='2181140'>have</span> <span
  m='2181590'>the</span> <span m='2181740'>output</span> <span
  m='2182220'>points.</span> <span m='2183690'>Here</span> <span
  m='2183930'>we're</span> <span m='2184110'>computing</span> <span
  m='2185160'>the</span> <span m='2187580'>two-point</span> <span
  m='2188360'>DFTs,</span> <span m='2192410'>combining</span> <span
  m='2192980'>those</span> <span m='2193220'>together</span> <span
  m='2194090'>to</span> <span m='2194210'>get</span> <span
  m='2194390'>the</span> <span m='2194510'>four-point</span> <span
  m='2195320'>DFTs,</span> <span m='2196880'>combining</span> <span
  m='2197690'>those</span> <span m='2198020'>together</span> <span
  m='2198800'>to</span> <span m='2198920'>get</span> <span
  m='2199550'>the</span> <span m='2199700'>eight-point</span> <span
  m='2200180'>DFTs,</span> <span m='2201090'>et cetera.</span> </p><p><span
  m='2202190'>And</span> <span m='2203240'>I'll</span> <span
  m='2203330'>remind</span> <span m='2203780'>you</span> <span
  m='2203870'>again</span> <span m='2204230'>that</span> <span
  m='2204350'>the</span> <span m='2204440'>basic</span> <span
  m='2204800'>computation</span> <span m='2206000'>that's</span> <span
  m='2206210'>involved</span> <span m='2207620'>throughout</span> <span
  m='2208070'>these</span> <span m='2208250'>stages</span> <span
  m='2209120'>is</span> <span m='2209690'>the</span> <span
  m='2209870'>butterfly</span> <span m='2210530'>computation.</span> <span
  m='2211970'>We</span> <span m='2212060'>see</span> <span m='2212300'>it</span>
  <span m='2212390'>here,</span> <span m='2212810'>we</span> <span
  m='2212990'>see</span> <span m='2213230'>it</span> <span
  m='2213560'>here,</span> <span m='2215940'>and</span> <span
  m='2216810'>we</span> <span m='2216930'>see</span> <span m='2217260'>it</span>
  <span m='2217500'>here.</span> <span m='2219560'>And</span> <span
  m='2219920'>always,</span> <span m='2220820'>the</span> <span
  m='2220940'>multiplication</span> <span m='2221900'>by</span> <span
  m='2222080'>powers</span> <span m='2222500'>of</span> <span
  m='2222620'>W</span> <span m='2223250'>is</span> <span
  m='2223400'>applied</span> <span m='2224330'>to</span> <span
  m='2224960'>the</span> <span m='2226620'>branches</span> <span
  m='2227130'>coming</span> <span m='2227520'>from</span> <span
  m='2228030'>the</span> <span m='2228150'>bottom</span> <span
  m='2228540'>node</span> <span m='2229020'>of</span> <span
  m='2229200'>the</span> <span m='2229290'>butterfly.</span> <span
  m='2230130'>And</span> <span m='2230280'>that's</span> <span
  m='2230550'>because</span> <span m='2231390'>of</span> <span
  m='2232350'>the</span> <span m='2232470'>fact</span> <span
  m='2233160'>that</span> <span m='2233910'>X</span> <span m='2234180'>of</span>
  <span m='2234300'>k</span> <span m='2234720'>is</span> <span
  m='2234840'>expressed</span> <span m='2235470'>as</span> <span m='2235680'>G
  of k</span> <span m='2236400'>plus</span> <span m='2236700'>W sub</span> <span
  m='2237030'>N</span> <span m='2237360'>to</span> <span m='2237480'>the</span>
  <span m='2237570'>k</span> <span m='2238280'>times</span> <span
  m='2238530'>H</span> <span m='2238800'>of</span> <span m='2238920'>k.</span>
  <span m='2239280'>And</span> <span m='2239400'>it's</span> <span
  m='2239490'>always</span> <span m='2239760'>the</span> <span m='2239880'>H
  of</span> <span m='2240210'>Ks</span> <span m='2241140'>that</span> <span
  m='2241440'>are</span> <span m='2241950'>what</span> <span
  m='2242130'>are</span> <span m='2242220'>being</span> <span
  m='2242490'>computed</span> <span m='2243160'>in</span> <span
  m='2243360'>the</span> <span m='2243420'>bottom</span> <span
  m='2243780'>half</span> <span m='2244500'>as</span> <span
  m='2244740'>we've</span> <span m='2244950'>been</span> <span
  m='2245130'>developing</span> <span m='2245670'>this</span> <span
  m='2245790'>flow</span> <span m='2246060'>graph.</span> <span
  m='2246900'>It</span> <span m='2246990'>will</span> <span
  m='2247110'>turn</span> <span m='2247350'>out</span> <span
  m='2247500'>that</span> <span m='2247620'>that's</span> <span
  m='2247830'>not</span> <span m='2248010'>true</span> <span
  m='2248430'>for</span> <span m='2248700'>other</span> <span
  m='2249510'>forms</span> <span m='2249930'>of</span> <span
  m='2250020'>the</span> <span m='2250170'>algorithm,</span> <span
  m='2250840'>but</span> <span m='2250920'>for</span> <span
  m='2251040'>the</span> <span m='2251130'>form</span> <span
  m='2251400'>that</span> <span m='2251490'>we're</span> <span
  m='2251610'>developing</span> <span m='2252150'>here</span> <span
  m='2252390'>it</span> <span m='2252480'>is.</span> </p><p><span
  m='2254140'>All right,</span> <span m='2254430'>well,</span> <span
  m='2255150'>having</span> <span m='2255510'>carried</span> <span
  m='2256620'>this</span> <span m='2257700'>all</span> <span
  m='2257940'>the</span> <span m='2258060'>way</span> <span
  m='2258270'>back</span> <span m='2259110'>to</span> <span
  m='2259560'>the</span> <span m='2259840'>two-point</span> <span
  m='2260257'>DFTs,</span> <span m='2262110'>let's</span> <span
  m='2262350'>see</span> <span m='2262890'>what</span> <span
  m='2263520'>this</span> <span m='2263760'>has</span> <span
  m='2264210'>accomplished</span> <span m='2264870'>for</span> <span
  m='2265170'>us</span> <span m='2265920'>in</span> <span
  m='2266040'>terms</span> <span m='2266580'>of</span> <span
  m='2267030'>computational</span> <span m='2267930'>efficiency.</span> <span
  m='2270620'>We</span> <span m='2270740'>began</span> <span
  m='2271550'>with</span> <span m='2271730'>N</span> <span
  m='2271880'>equal</span> <span m='2272120'>to</span> <span
  m='2272270'>a</span> <span m='2272330'>power</span> <span
  m='2272750'>of</span> <span m='2272870'>2.</span> <span m='2275410'>We</span>
  <span m='2275590'>thought</span> <span m='2276070'>about</span> <span
  m='2276580'>computing</span> <span m='2277480'>a</span> <span
  m='2277750'>direct</span> <span m='2278500'>discrete</span> <span
  m='2278920'>Fourier</span> <span m='2279340'>transform,</span> <span
  m='2281000'>but</span> <span m='2281080'>that</span> <span
  m='2281320'>involved</span> <span m='2282040'>N</span> <span
  m='2282250'>squared</span> <span m='2283030'>complex</span> <span
  m='2283630'>multiplies</span> <span m='2284320'>and</span> <span
  m='2284450'>adds.</span> <span m='2286720'>Instead</span> <span
  m='2287140'>of</span> <span m='2287260'>that,</span> <span
  m='2287800'>we</span> <span m='2288040'>broke</span> <span
  m='2288400'>the</span> <span m='2288490'>computation</span> <span
  m='2289510'>into</span> <span m='2289840'>two</span> <span
  m='2290260'>N/2</span> <span m='2290680'>point</span> <span
  m='2291440'>DFTs</span> <span m='2293350'>plus</span> <span
  m='2293950'>some</span> <span m='2294250'>diddling</span> <span
  m='2294970'>to</span> <span m='2295090'>fit</span> <span
  m='2295330'>those</span> <span m='2295600'>together.</span> <span
  m='2297460'>The</span> <span m='2297580'>computation</span> <span
  m='2298360'>of</span> <span m='2298480'>the</span> <span
  m='2298570'>two</span> <span m='2298970'>N/2</span> <span
  m='2299350'>point</span> <span m='2299800'>DFTs</span> <span
  m='2301720'>involved</span> <span m='2303730'>complex</span> <span
  m='2304660'>multiplies</span> <span m='2305320'>and</span> <span
  m='2305430'>adds</span> <span m='2306580'>equal</span> <span
  m='2306970'>to</span> <span m='2307150'>2,</span> <span
  m='2307960'>because</span> <span m='2308260'>there</span> <span
  m='2308350'>were</span> <span m='2308470'>two</span> <span
  m='2308710'>of</span> <span m='2308830'>them,</span> <span
  m='2309450'>times</span> <span m='2309750'>N/2</span> <span
  m='2310330'>squared</span> <span m='2311680'>plus</span> <span
  m='2312560'>N</span> <span m='2313450'>for</span> <span m='2313540'>the</span>
  <span m='2313660'>diddles--</span> <span m='2314470'>the</span> <span
  m='2314560'>diddles</span> <span m='2315070'>being</span> <span
  m='2315370'>involved</span> <span m='2316000'>in</span> <span
  m='2316260'>fitting</span> <span m='2316570'>those</span> <span
  m='2316810'>two</span> <span m='2317560'>N/2</span> <span
  m='2317680'>point</span> <span m='2317920'>DFTs</span> <span
  m='2319030'>together.</span> <span m='2320240'>And</span> <span
  m='2320260'>this,</span> <span m='2321430'>for</span> <span
  m='2321770'>N</span> <span m='2322000'>greater</span> <span
  m='2322270'>than</span> <span m='2322420'>two,</span> <span
  m='2322820'>is</span> <span m='2322990'>a</span> <span
  m='2323080'>bigger</span> <span m='2323350'>number</span> <span
  m='2323650'>than</span> <span m='2323830'>that.</span> </p><p><span
  m='2326010'>All</span> <span m='2326100'>right,</span> <span
  m='2326520'>then</span> <span m='2326910'>we</span> <span
  m='2327060'>said,</span> <span m='2327270'>well,</span> <span
  m='2327420'>why</span> <span m='2327630'>stop</span> <span
  m='2328050'>there?</span> <span m='2328510'>Let's</span> <span
  m='2329010'>break</span> <span m='2329370'>these</span> <span
  m='2330210'>two</span> <span m='2330420'>N/2</span> <span
  m='2330800'>point</span> <span m='2331135'>DFTs</span> <span
  m='2331870'>into</span> <span m='2332190'>four</span> <span
  m='2333150'>N/4</span> <span m='2333630'>point</span> <span
  m='2334045'>DFTs.</span> <span m='2336670'>That</span> <span
  m='2336940'>meant</span> <span m='2337780'>then</span> <span
  m='2338320'>that</span> <span m='2338710'>this</span> <span
  m='2338860'>N/2</span> <span m='2339460'>squared,</span> <span
  m='2340250'>which</span> <span m='2340420'>came</span> <span
  m='2340870'>from</span> <span m='2341110'>a</span> <span
  m='2341170'>direct</span> <span m='2341620'>computation</span> <span
  m='2342430'>of</span> <span m='2342520'>the</span> <span
  m='2342620'>DFT,</span> <span m='2345340'>gets</span> <span
  m='2345610'>replaced</span> <span m='2346270'>instead</span> <span
  m='2348010'>by</span> <span m='2349010'>two</span> <span
  m='2349960'>N/4</span> <span m='2350740'>point</span> <span
  m='2351610'>DFTs.</span> <span m='2352330'>So</span> <span
  m='2352540'>we</span> <span m='2352660'>have</span> <span m='2353350'>2</span>
  <span m='2353680'>times</span> <span m='2354040'>N/4</span> <span
  m='2354730'>squared</span> <span m='2356890'>plus</span> <span
  m='2357940'>N/2,</span> <span m='2359380'>which</span> <span
  m='2359710'>are</span> <span m='2359860'>the</span> <span
  m='2359980'>diddles</span> <span m='2360520'>involved</span> <span
  m='2361420'>in,</span> <span m='2361930'>again,</span> <span
  m='2362770'>fitting</span> <span m='2363370'>those</span> <span
  m='2363670'>together.</span> </p><p><span m='2364760'>So</span> <span
  m='2365170'>the</span> <span m='2365410'>N/2</span> <span
  m='2365860'>squared,</span> <span m='2367130'>which</span> <span
  m='2367300'>involved</span> <span m='2367960'>computing</span> <span
  m='2368520'>one</span> <span m='2369130'>N/2</span> <span
  m='2369250'>point</span> <span m='2369460'>DFT</span> <span
  m='2370450'>gets</span> <span m='2370660'>replaced</span> <span
  m='2371110'>by</span> <span m='2371350'>this</span> <span
  m='2372290'>when</span> <span m='2372520'>we</span> <span
  m='2372640'>go</span> <span m='2372970'>to</span> <span m='2373120'>the</span>
  <span m='2373240'>N/4</span> <span m='2373600'>point</span> <span
  m='2374260'>DFTs.</span> <span m='2375730'>And</span> <span
  m='2375880'>consequently,</span> <span m='2376660'>substituting</span> <span
  m='2377260'>this</span> <span m='2377500'>in</span> <span
  m='2377680'>there,</span> <span m='2377970'>the</span> <span
  m='2378100'>computation</span> <span m='2379060'>is--</span> <span
  m='2380170'>instead</span> <span m='2380560'>of</span> <span
  m='2380680'>that,</span> <span m='2382070'>it's</span> <span
  m='2382240'>N/4</span> <span m='2382840'>squared</span> <span
  m='2383200'>times</span> <span m='2383560'>4</span> <span
  m='2384460'>plus</span> <span m='2384790'>N</span> <span
  m='2385570'>plus</span> <span m='2385900'>N.</span> <span
  m='2387160'>This</span> <span m='2387400'>N</span> <span
  m='2387610'>coming</span> <span m='2388000'>from</span> <span
  m='2388180'>that</span> <span m='2388390'>2</span> <span
  m='2388750'>times</span> <span m='2389140'>this</span> <span
  m='2389310'>N/2.</span> </p><p><span m='2390580'>Well,</span> <span
  m='2390900'>we</span> <span m='2391060'>can</span> <span m='2391180'>go</span>
  <span m='2391390'>through</span> <span m='2391630'>this</span> <span
  m='2391840'>again.</span> <span m='2393670'>We</span> <span
  m='2393790'>broke</span> <span m='2394060'>the</span> <span
  m='2394300'>N/4</span> <span m='2394780'>point</span> <span
  m='2395080'>DFTs</span> <span m='2395890'>into</span> <span
  m='2397310'>N/8</span> <span m='2397720'>point</span> <span
  m='2398230'>DFTs.</span> <span m='2399730'>Therefore,</span> <span
  m='2400120'>the</span> <span m='2400360'>N/4</span> <span
  m='2400840'>squared</span> <span m='2401320'>got</span> <span
  m='2401560'>replaced</span> <span m='2402130'>by</span> <span
  m='2402760'>N/8</span> <span m='2403420'>squared</span> <span
  m='2404020'>twice,</span> <span m='2405430'>plus</span> <span
  m='2405830'>N/4</span> <span m='2406750'>to</span> <span
  m='2406870'>fit</span> <span m='2407080'>those</span> <span
  m='2407380'>together.</span> <span m='2409290'>That</span> <span
  m='2409740'>gets</span> <span m='2409950'>substituted</span> <span
  m='2410670'>in</span> <span m='2410820'>for</span> <span
  m='2410940'>this</span> <span m='2411150'>N/4</span> <span
  m='2412020'>squared.</span> <span m='2412350'>We</span> <span
  m='2412440'>get</span> <span m='2413160'>8</span> <span
  m='2413430'>times</span> <span m='2413790'>N/8</span> <span
  m='2414320'>squared.</span> <span m='2415200'>We</span> <span
  m='2415290'>pick</span> <span m='2415530'>up</span> <span
  m='2415680'>another</span> <span m='2416070'>N,</span> <span
  m='2416580'>which</span> <span m='2416820'>is</span> <span
  m='2416970'>this</span> <span m='2417180'>4</span> <span
  m='2418050'>times</span> <span m='2418320'>that</span> <span
  m='2418530'>N/4.</span> <span m='2420820'>And</span> <span
  m='2421420'>you</span> <span m='2421540'>can</span> <span
  m='2421690'>see</span> <span m='2421960'>that</span> <span
  m='2422110'>each</span> <span m='2422320'>time</span> <span
  m='2422590'>we</span> <span m='2422710'>do</span> <span
  m='2422920'>this,</span> <span m='2423900'>this</span> <span
  m='2424390'>number</span> <span m='2424720'>gets</span> <span
  m='2424960'>smaller,</span> <span m='2426810'>and</span> <span
  m='2427410'>we</span> <span m='2427590'>keep</span> <span
  m='2428010'>picking</span> <span m='2428400'>up</span> <span
  m='2428850'>another</span> <span m='2429720'>factor</span> <span
  m='2430320'>of</span> <span m='2430470'>N</span> <span
  m='2430980'>added</span> <span m='2431340'>in.</span> </p><p><span
  m='2432450'>Well,</span> <span m='2432870'>if</span> <span
  m='2433020'>you</span> <span m='2433110'>track</span> <span
  m='2433500'>this</span> <span m='2433740'>through,</span> <span
  m='2434430'>what</span> <span m='2434640'>you</span> <span
  m='2434760'>find</span> <span m='2435420'>is</span> <span
  m='2435660'>that</span> <span m='2435810'>for</span> <span
  m='2435990'>N</span> <span m='2436140'>equal</span> <span
  m='2436380'>to</span> <span m='2436530'>a</span> <span
  m='2436590'>power</span> <span m='2436980'>of</span> <span
  m='2437100'>2,</span> <span m='2437970'>in</span> <span
  m='2438120'>fact,</span> <span m='2438780'>the</span> <span
  m='2438870'>computation</span> <span m='2440370'>then</span> <span
  m='2441180'>comes</span> <span m='2441450'>out</span> <span
  m='2442050'>proportional</span> <span m='2443550'>to</span> <span
  m='2444610'>N</span> <span m='2444900'>plus</span> <span m='2445260'>N</span>
  <span m='2445470'>plus</span> <span m='2446790'>N</span> <span
  m='2447900'>nu</span> <span m='2448110'>times,</span> <span
  m='2448860'>where</span> <span m='2449040'>nu</span> <span
  m='2449460'>is</span> <span m='2449700'>log</span> <span
  m='2450000'>for</span> <span m='2450090'>the</span> <span
  m='2450180'>base</span> <span m='2450450'>2</span> <span m='2450690'>of</span>
  <span m='2450810'>N.</span> <span m='2452160'>And</span> <span
  m='2452580'>so,</span> <span m='2453660'>the</span> <span
  m='2453930'>number</span> <span m='2454290'>of</span> <span
  m='2454380'>complex</span> <span m='2454950'>multiplies</span> <span
  m='2455610'>and</span> <span m='2455700'>adds</span> <span
  m='2456660'>involved</span> <span m='2457620'>in</span> <span
  m='2457950'>implementing</span> <span m='2459060'>the</span> <span
  m='2459180'>discrete</span> <span m='2459600'>Fourier</span> <span
  m='2460020'>transform</span> <span m='2461550'>using</span> <span
  m='2462510'>the</span> <span m='2462900'>fast</span> <span
  m='2463260'>Fourier</span> <span m='2463620'>transform</span> <span
  m='2464250'>algorithm</span> <span m='2465420'>is</span> <span
  m='2465570'>proportional</span> <span m='2466500'>to</span> <span
  m='2466920'>N</span> <span m='2467430'>times</span> <span
  m='2467860'>nu</span> <span m='2468840'>rather</span> <span
  m='2469200'>than</span> <span m='2469680'>proportional</span> <span
  m='2470340'>to</span> <span m='2470460'>N</span> <span
  m='2470660'>squared.</span> <span m='2471200'>A</span> <span
  m='2471270'>rather</span> <span m='2471600'>dramatic</span> <span
  m='2472050'>savings.</span> </p><p><span m='2474840'>OK,</span> <span
  m='2475200'>well</span> <span m='2475710'>there</span> <span
  m='2476370'>is</span> <span m='2476970'>one--</span> <span
  m='2478000'>there</span> <span m='2478080'>are</span> <span
  m='2478110'>a</span> <span m='2478140'>number</span> <span
  m='2478410'>of</span> <span m='2478470'>modifications</span> <span
  m='2479700'>that</span> <span m='2480090'>we're</span> <span
  m='2480420'>going</span> <span m='2480690'>to</span> <span
  m='2480810'>want</span> <span m='2481080'>to</span> <span
  m='2481170'>make</span> <span m='2481950'>to</span> <span
  m='2482160'>this</span> <span m='2482370'>basic</span> <span
  m='2483060'>structure</span> <span m='2483660'>for</span> <span
  m='2483810'>the</span> <span m='2483900'>computation</span> <span
  m='2484800'>as</span> <span m='2484980'>we</span> <span m='2485100'>go</span>
  <span m='2486180'>through</span> <span m='2486390'>this</span> <span
  m='2486600'>lecture</span> <span m='2487230'>and</span> <span
  m='2487350'>the</span> <span m='2487440'>next</span> <span
  m='2487620'>several</span> <span m='2488010'>lectures.</span> <span
  m='2489660'>The</span> <span m='2489780'>first</span> <span
  m='2490380'>is</span> <span m='2491070'>to</span> <span
  m='2492360'>introduce</span> <span m='2493260'>a</span> <span
  m='2494790'>fairly</span> <span m='2495180'>straightforward</span> <span
  m='2496200'>simplification</span> <span m='2498240'>by,</span> <span
  m='2500770'>first</span> <span m='2500970'>of</span> <span
  m='2501120'>all,</span> <span m='2501790'>again,</span> <span
  m='2502290'>reminding</span> <span m='2502890'>you</span> <span
  m='2503700'>that</span> <span m='2503820'>the</span> <span
  m='2503940'>basic</span> <span m='2504300'>computation</span> <span
  m='2505290'>involved</span> <span m='2507500'>always,</span> <span
  m='2508220'>from</span> <span m='2508490'>one</span> <span
  m='2508700'>stage</span> <span m='2509150'>to</span> <span
  m='2509330'>the</span> <span m='2509420'>next,</span> <span
  m='2510590'>is</span> <span m='2510890'>always</span> <span
  m='2511760'>a</span> <span m='2512090'>butterfly</span> <span
  m='2513650'>type</span> <span m='2513950'>of</span> <span
  m='2514040'>computation</span> <span m='2516050'>with</span> <span
  m='2516920'>multiplications</span> <span m='2517790'>by</span> <span
  m='2517970'>powers</span> <span m='2518420'>of</span> <span
  m='2518510'>W</span> <span m='2519260'>applied</span> <span
  m='2520190'>to</span> <span m='2520490'>the</span> <span
  m='2520610'>signal</span> <span m='2521300'>from</span> <span
  m='2521510'>the</span> <span m='2521600'>bottom</span> <span
  m='2521960'>node.</span> </p><p><span m='2523280'>And</span> <span
  m='2524540'>you</span> <span m='2524810'>should</span> <span
  m='2525080'>notice,</span> <span m='2525980'>and</span> <span
  m='2526580'>it's</span> <span m='2527390'>rather</span> <span
  m='2527720'>straightforward</span> <span m='2528260'>to</span> <span
  m='2528380'>verify</span> <span m='2529340'>why</span> <span
  m='2529610'>this</span> <span m='2529850'>is</span> <span
  m='2529970'>true,</span> <span m='2530910'>that</span> <span
  m='2531260'>in</span> <span m='2531500'>each</span> <span
  m='2531770'>of</span> <span m='2531860'>these</span> <span
  m='2532070'>butterflies,</span> <span m='2533540'>the</span> <span
  m='2533630'>separation</span> <span m='2536710'>in</span> <span
  m='2536930'>powers</span> <span m='2537320'>of</span> <span
  m='2537440'>W</span> <span m='2538580'>between</span> <span
  m='2539420'>the</span> <span m='2540500'>factor</span> <span
  m='2541220'>going</span> <span m='2541520'>to</span> <span
  m='2541640'>the</span> <span m='2541730'>top</span> <span
  m='2542090'>node</span> <span m='2542420'>at</span> <span
  m='2542510'>the</span> <span m='2542660'>end</span> <span
  m='2542780'>of</span> <span m='2542870'>the</span> <span
  m='2542990'>butterfly</span> <span m='2543770'>and</span> <span
  m='2543860'>the</span> <span m='2543950'>factor</span> <span
  m='2544330'>going</span> <span m='2544550'>to</span> <span
  m='2544610'>the</span> <span m='2544730'>bottom</span> <span
  m='2545060'>node</span> <span m='2545960'>in</span> <span
  m='2546650'>the</span> <span m='2546740'>butterfly,</span> <span
  m='2548090'>they</span> <span m='2548300'>are</span> <span
  m='2548510'>always</span> <span m='2548840'>separated</span> <span
  m='2549830'>by</span> <span m='2550340'>N/2.</span> <span
  m='2551780'>So</span> <span m='2551900'>that</span> <span
  m='2552170'>means</span> <span m='2552770'>that</span> <span
  m='2552920'>the</span> <span m='2553040'>basic</span> <span
  m='2553430'>computation</span> <span m='2556040'>in</span> <span
  m='2556760'>the</span> <span m='2558890'>computation</span> <span
  m='2559850'>of</span> <span m='2560540'>the</span> <span
  m='2560630'>DFT,</span> <span m='2561590'>as</span> <span m='2562440'>I</span>
  <span m='2562700'>illustrated</span> <span m='2563330'>on</span> <span
  m='2563480'>the</span> <span m='2563540'>previous</span> <span
  m='2564020'>flow</span> <span m='2564260'>graph,</span> <span
  m='2565250'>is</span> <span m='2565400'>a</span> <span
  m='2565460'>butterfly,</span> <span m='2567410'>where</span> <span
  m='2567650'>the</span> <span m='2567770'>characteristic</span> <span
  m='2568610'>of</span> <span m='2568760'>it</span> <span m='2569090'>is</span>
  <span m='2569390'>that</span> <span m='2569840'>it's</span> <span
  m='2570020'>multiplication</span> <span m='2570920'>by</span> <span
  m='2571100'>unity</span> <span m='2571760'>from</span> <span
  m='2572300'>the</span> <span m='2572390'>top</span> <span
  m='2572750'>node,</span> <span m='2573770'>and</span> <span
  m='2573890'>multiplication</span> <span m='2574940'>by</span> <span
  m='2575810'>some</span> <span m='2576110'>power</span> <span
  m='2576530'>of</span> <span m='2576620'>W</span> <span m='2577610'>from</span>
  <span m='2577790'>the</span> <span m='2577880'>bottom</span> <span
  m='2578420'>to</span> <span m='2578570'>the</span> <span
  m='2578690'>top</span> <span m='2579020'>node,</span> <span
  m='2580160'>and</span> <span m='2580700'>a</span> <span
  m='2580760'>power</span> <span m='2581180'>of</span> <span
  m='2581270'>W</span> <span m='2582740'>displaced</span> <span
  m='2583400'>from</span> <span m='2583610'>this</span> <span
  m='2583850'>one</span> <span m='2584360'>by</span> <span
  m='2584630'>N/2</span> <span m='2586310'>from</span> <span
  m='2586550'>the</span> <span m='2586640'>bottom</span> <span
  m='2586970'>node</span> <span m='2587600'>to</span> <span
  m='2587690'>the</span> <span m='2587810'>bottom</span> <span
  m='2588170'>node.</span> </p><p><span m='2589400'>Well,</span> <span
  m='2589880'>let's</span> <span m='2590630'>decompose</span> <span
  m='2591560'>this</span> <span m='2591830'>power</span> <span
  m='2592310'>of</span> <span m='2592400'>W</span> <span m='2593480'>into</span>
  <span m='2593720'>W sub</span> <span m='2594110'>N</span> <span
  m='2594500'>to</span> <span m='2594650'>the</span> <span m='2594830'>r</span>
  <span m='2595730'>times</span> <span m='2596030'>W</span> <span
  m='2596730'>sub N</span> <span m='2597710'>to</span> <span
  m='2597830'>the</span> <span m='2597980'>N/2.</span> <span
  m='2600520'>W</span> <span m='2600820'>sub N to</span> <span
  m='2601300'>the</span> <span m='2601420'>N/2.</span> <span
  m='2601810'>Well,</span> <span m='2602260'>what</span> <span
  m='2602440'>is</span> <span m='2602590'>that?</span> <span m='2602920'>That's
  e</span> <span m='2603160'>to</span> <span m='2603410'>the</span> <span
  m='2603490'>minus j</span> <span m='2603880'>2</span> <span
  m='2604360'>pi</span> <span m='2604630'>over</span> <span
  m='2604840'>capitalized</span> <span m='2605215'>N--</span> <span
  m='2605590'>that's</span> <span m='2605820'>W</span> <span m='2606320'>sub
  N--</span> <span m='2607420'>raised</span> <span m='2607750'>to</span> <span
  m='2607870'>the</span> <span m='2608020'>N/2</span> <span
  m='2608590'>power.</span> <span m='2609820'>The</span> <span
  m='2609910'>capital</span> <span m='2610390'>N's</span> <span
  m='2610630'>cancel</span> <span m='2611140'>out.</span> <span
  m='2611440'>The</span> <span m='2611560'>2's</span> <span
  m='2611860'>cancel</span> <span m='2612370'>out.</span> <span
  m='2612700'>We're</span> <span m='2612850'>left</span> <span
  m='2613180'>with</span> <span m='2613360'>e to</span> <span
  m='2613600'>the</span> <span m='2613720'>minus j</span> <span
  m='2614050'>pi,</span> <span m='2614840'>which</span> <span
  m='2614950'>is</span> <span m='2615070'>equal</span> <span
  m='2615310'>to</span> <span m='2615460'>minus</span> <span
  m='2615850'>1.</span> <span m='2616820'>So</span> <span
  m='2616870'>then,</span> <span m='2617020'>in</span> <span
  m='2617110'>fact,</span> <span m='2617950'>this</span> <span
  m='2618700'>factor,</span> <span m='2619510'>or</span> <span
  m='2619750'>equivalently,</span> <span m='2620350'>this</span> <span
  m='2620620'>factor,</span> <span m='2621730'>is</span> <span
  m='2621880'>equal</span> <span m='2622300'>to</span> <span
  m='2622870'>minus</span> <span m='2623155'>1 or</span> <span
  m='2623440'>minus</span> <span m='2625330'>W sub</span> <span
  m='2625696'>N</span> <span m='2626790'>to</span> <span m='2626920'>the</span>
  <span m='2627110'>r.</span> </p><p><span m='2628450'>Consequently,</span>
  <span m='2629870'>we</span> <span m='2630020'>could</span> <span
  m='2630200'>redraw</span> <span m='2631100'>the</span> <span
  m='2631220'>butterfly</span> <span m='2633360'>so</span> <span
  m='2633660'>that</span> <span m='2634800'>rather</span> <span
  m='2635520'>than</span> <span m='2636030'>implementing</span> <span
  m='2637320'>that</span> <span m='2637560'>multiplication</span> <span
  m='2639330'>in</span> <span m='2639450'>both</span> <span
  m='2640290'>the</span> <span m='2640560'>branch</span> <span
  m='2640920'>going</span> <span m='2641190'>to</span> <span
  m='2641280'>the</span> <span m='2641400'>top</span> <span
  m='2641730'>node</span> <span m='2642150'>and</span> <span
  m='2642240'>the</span> <span m='2642330'>branch</span> <span
  m='2642660'>going</span> <span m='2642930'>to</span> <span
  m='2643020'>the</span> <span m='2643110'>bottom</span> <span
  m='2643470'>node,</span> <span m='2644370'>we</span> <span
  m='2644490'>simply</span> <span m='2645510'>multiply</span> <span
  m='2646980'>the</span> <span m='2647070'>value</span> <span
  m='2648060'>coming</span> <span m='2648360'>into</span> <span
  m='2648570'>the</span> <span m='2648690'>butterfly</span> <span
  m='2649620'>by</span> <span m='2649800'>W sub</span> <span
  m='2650175'>N</span> <span m='2650550'>to</span> <span m='2650670'>the</span>
  <span m='2650860'>r,</span> <span m='2652200'>and</span> <span
  m='2652350'>then</span> <span m='2652680'>add</span> <span
  m='2652950'>it</span> <span m='2653880'>to</span> <span
  m='2654540'>this</span> <span m='2654810'>value</span> <span
  m='2655410'>at</span> <span m='2655590'>the</span> <span
  m='2655710'>top</span> <span m='2656010'>node,</span> <span
  m='2656850'>and</span> <span m='2657030'>subtract it</span> <span
  m='2658260'>from</span> <span m='2658860'>this</span> <span
  m='2659070'>value</span> <span m='2659640'>at</span> <span
  m='2659760'>the</span> <span m='2659880'>bottom</span> <span
  m='2660240'>node.</span> <span m='2661320'>So</span> <span
  m='2661620'>we</span> <span m='2661770'>could</span> <span
  m='2661950'>redraw</span> <span m='2663150'>our</span> <span
  m='2663330'>original</span> <span m='2663720'>flow</span> <span
  m='2664020'>graph</span> <span m='2665960'>by</span> <span
  m='2667710'>replacing</span> <span m='2668490'>the</span> <span
  m='2668580'>butterfly</span> <span m='2669120'>computation</span> <span
  m='2670080'>in</span> <span m='2670230'>the</span> <span
  m='2670320'>previous</span> <span m='2670800'>flow</span> <span
  m='2671070'>graph</span> <span m='2671850'>by</span> <span
  m='2672030'>this</span> <span m='2672270'>butterfly</span> <span
  m='2673020'>computation,</span> <span m='2674400'>where</span> <span
  m='2674520'>the</span> <span m='2674640'>multiplication</span> <span
  m='2675540'>by</span> <span m='2675690'>the</span> <span
  m='2675810'>power</span> <span m='2676230'>of</span> <span
  m='2676320'>W</span> <span m='2677400'>is</span> <span
  m='2677970'>extracted</span> <span m='2678660'>from</span> <span
  m='2678900'>inside</span> <span m='2679350'>the</span> <span
  m='2679470'>butterfly,</span> <span m='2680580'>so</span> <span
  m='2680790'>that</span> <span m='2681150'>basically</span> <span
  m='2681750'>we</span> <span m='2681900'>reduce</span> <span
  m='2682800'>the</span> <span m='2683100'>number</span> <span
  m='2683430'>of</span> <span m='2683490'>multiplications</span> <span
  m='2684480'>by</span> <span m='2684690'>W</span> <span m='2685230'>that</span>
  <span m='2685380'>we</span> <span m='2685530'>have</span> <span
  m='2685740'>to</span> <span m='2685830'>implement</span> <span
  m='2686820'>by</span> <span m='2687180'>a</span> <span
  m='2687210'>factor</span> <span m='2687660'>of</span> <span
  m='2687780'>2.</span> </p><p><span m='2689430'>The</span> <span
  m='2689520'>flow</span> <span m='2689760'>graph</span> <span
  m='2690300'>that</span> <span m='2690510'>results</span> <span
  m='2691140'>when</span> <span m='2691320'>we</span> <span
  m='2691440'>do</span> <span m='2691620'>that</span> <span
  m='2693500'>we</span> <span m='2693650'>have</span> <span
  m='2694010'>here</span> <span m='2694730'>then,</span> <span
  m='2696500'>where</span> <span m='2697430'>the</span> <span
  m='2697550'>powers</span> <span m='2698000'>of</span> <span
  m='2698090'>W</span> <span m='2698870'>are</span> <span m='2699020'>now</span>
  <span m='2699950'>slid</span> <span m='2700580'>out</span> <span
  m='2700790'>of</span> <span m='2700910'>the</span> <span
  m='2701000'>butterfly</span> <span m='2702680'>to</span> <span
  m='2703160'>the</span> <span m='2703310'>entering</span> <span
  m='2703690'>node</span> <span m='2704360'>to</span> <span
  m='2704480'>the</span> <span m='2704570'>butterfly.</span> <span
  m='2706500'>And</span> <span m='2707270'>we</span> <span
  m='2707420'>now</span> <span m='2707720'>have,</span> <span
  m='2708200'>rather</span> <span m='2708560'>than</span> <span
  m='2708740'>multiplication</span> <span m='2709550'>by</span> <span
  m='2709730'>powers</span> <span m='2710150'>of</span> <span
  m='2710240'>W</span> <span m='2710900'>in</span> <span m='2710990'>the</span>
  <span m='2711080'>butterfly,</span> <span m='2712460'>each</span> <span
  m='2712820'>butterfly</span> <span m='2713390'>computation</span> <span
  m='2714740'>consists</span> <span m='2715340'>of</span> <span
  m='2716200'>an</span> <span m='2716300'>addition</span> <span
  m='2717860'>and</span> <span m='2718130'>a</span> <span
  m='2718400'>subtraction.</span> <span m='2719670'>So</span> <span
  m='2719750'>the</span> <span m='2719870'>basic</span> <span
  m='2720230'>computation</span> <span m='2721070'>now</span> <span
  m='2721610'>is</span> <span m='2721970'>a</span> <span
  m='2722030'>multiplication</span> <span m='2722990'>by</span> <span
  m='2723170'>a</span> <span m='2723230'>power</span> <span
  m='2723650'>of</span> <span m='2723740'>W</span> <span
  m='2725240'>followed</span> <span m='2725690'>by</span> <span
  m='2726620'>an</span> <span m='2726740'>addition</span> <span m='2727490'>and
  a</span> <span m='2727760'>subtraction.</span> <span m='2729020'>And</span>
  <span m='2729140'>this</span> <span m='2729350'>follows</span> <span
  m='2729740'>all</span> <span m='2729920'>the</span> <span
  m='2730010'>way</span> <span m='2730160'>through</span> <span
  m='2730960'>a</span> <span m='2731030'>multiplication</span> <span
  m='2731990'>by</span> <span m='2732170'>a</span> <span
  m='2732260'>power</span> <span m='2732650'>of</span> <span
  m='2732770'>W</span> <span m='2733850'>and</span> <span
  m='2734000'>then</span> <span m='2734370'>an</span> <span
  m='2734510'>addition</span> <span m='2736610'>and</span> <span
  m='2737015'>a</span> <span m='2737420'>subtraction,</span> <span
  m='2738380'>this</span> <span m='2738560'>minus 1</span> <span
  m='2738950'>being</span> <span m='2739430'>associated</span> <span
  m='2740750'>with</span> <span m='2741170'>this</span> <span
  m='2741410'>line.</span> <span m='2742280'>The</span> <span
  m='2742370'>minus</span> <span m='2742760'>1's,</span> <span
  m='2743060'>of</span> <span m='2743180'>course,</span> <span
  m='2744110'>always</span> <span m='2744770'>occur</span> <span
  m='2745340'>on</span> <span m='2745670'>the</span> <span
  m='2745760'>branches</span> <span m='2746870'>coming</span> <span
  m='2747260'>from</span> <span m='2748070'>the</span> <span
  m='2748850'>bottom</span> <span m='2749180'>node</span> <span
  m='2749540'>of</span> <span m='2749630'>the</span> <span
  m='2749750'>butterfly.</span> <span m='2750330'>That's</span> <span
  m='2750530'>consistent</span> <span m='2751190'>with</span> <span
  m='2751490'>everything</span> <span m='2752300'>that</span> <span
  m='2752690'>we've</span> <span m='2752870'>been</span> <span
  m='2753020'>saying</span> <span m='2753830'>throughout</span> <span
  m='2754220'>this</span> <span m='2754400'>discussion.</span> </p><p><span
  m='2756700'>All</span> <span m='2756800'>right,</span> <span
  m='2756960'>so</span> <span m='2757560'>this</span> <span
  m='2757890'>then</span> <span m='2758340'>is</span> <span
  m='2759300'>one</span> <span m='2759570'>form</span> <span
  m='2760290'>of</span> <span m='2761930'>an</span> <span
  m='2762360'>algorithm,</span> <span m='2763410'>referred</span> <span
  m='2763740'>to</span> <span m='2763950'>as</span> <span m='2764070'>the</span>
  <span m='2764160'>fast</span> <span m='2764460'>Fourier</span> <span
  m='2764790'>transform</span> <span m='2765420'>algorithm,</span> <span
  m='2766620'>for</span> <span m='2767550'>implementing</span> <span
  m='2768300'>the</span> <span m='2768390'>computation</span> <span
  m='2769470'>of</span> <span m='2769650'>the</span> <span
  m='2769740'>discrete</span> <span m='2770130'>Fourier</span> <span
  m='2770550'>transform.</span> <span m='2772110'>As</span> <span
  m='2772320'>the</span> <span m='2772470'>algorithm</span> <span
  m='2773010'>developed,</span> <span m='2773870'>it</span> <span
  m='2774030'>developed</span> <span m='2774720'>somewhat</span> <span
  m='2775140'>naturally</span> <span m='2776670'>in</span> <span
  m='2777150'>a</span> <span m='2777240'>flow</span> <span
  m='2777570'>graph</span> <span m='2777870'>form.</span> <span
  m='2779490'>And</span> <span m='2780090'>in</span> <span
  m='2780270'>fact,</span> <span m='2781060'>we</span> <span
  m='2781110'>can</span> <span m='2781230'>interpret</span> <span
  m='2781860'>this</span> <span m='2782040'>flow</span> <span
  m='2782370'>graph</span> <span m='2783360'>as</span> <span
  m='2783540'>a</span> <span m='2783630'>computational</span> <span
  m='2784500'>recipe</span> <span m='2785640'>for</span> <span
  m='2786000'>computing</span> <span m='2786600'>the</span> <span
  m='2786690'>discrete</span> <span m='2787110'>Fourier</span> <span
  m='2787500'>transform.</span> </p><p><span m='2789900'>There</span> <span
  m='2790440'>are</span> <span m='2790980'>a</span> <span m='2791040'>few</span>
  <span m='2791340'>things</span> <span m='2792360'>that</span> <span
  m='2793050'>I</span> <span m='2793440'>would</span> <span
  m='2793650'>like</span> <span m='2793860'>to</span> <span
  m='2793980'>draw</span> <span m='2794220'>your</span> <span
  m='2794400'>attention</span> <span m='2794910'>to.</span> <span
  m='2795450'>One</span> <span m='2795930'>primary</span> <span
  m='2796440'>one</span> <span m='2796620'>in</span> <span
  m='2796710'>particular</span> <span m='2797550'>at</span> <span
  m='2797670'>this</span> <span m='2797850'>point,</span> <span
  m='2798920'>that</span> <span m='2799170'>is</span> <span
  m='2799800'>that</span> <span m='2800850'>we</span> <span
  m='2801000'>notice</span> <span m='2801840'>that</span> <span
  m='2802380'>the</span> <span m='2803400'>input</span> <span
  m='2803820'>sequence</span> <span m='2804330'>values,</span> <span
  m='2805110'>because</span> <span m='2805500'>of</span> <span
  m='2805590'>the</span> <span m='2805710'>way</span> <span
  m='2805950'>that</span> <span m='2806070'>we</span> <span
  m='2806190'>derive</span> <span m='2806640'>this</span> <span
  m='2806880'>algorithm,</span> <span m='2808140'>the</span> <span
  m='2808260'>input</span> <span m='2808800'>sequence</span> <span
  m='2809340'>values</span> <span m='2810030'>got</span> <span
  m='2810480'>rearranged</span> <span m='2811440'>in</span> <span
  m='2811590'>a</span> <span m='2811650'>somewhat</span> <span
  m='2812820'>funny</span> <span m='2813180'>order</span> <span
  m='2814830'>at</span> <span m='2815280'>the</span> <span
  m='2815610'>input</span> <span m='2816030'>to</span> <span
  m='2816150'>the</span> <span m='2816240'>flow</span> <span
  m='2816540'>graph.</span> <span m='2817410'>Although,</span> <span
  m='2818130'>they</span> <span m='2818280'>come</span> <span
  m='2818460'>out</span> <span m='2818610'>of</span> <span
  m='2818700'>the</span> <span m='2818820'>flow</span> <span
  m='2819120'>graph</span> <span m='2820110'>in</span> <span
  m='2820680'>a</span> <span m='2821490'>sequential</span> <span
  m='2822150'>order,</span> <span m='2822420'>0,</span> <span
  m='2822850'>1,</span> <span m='2823060'>2,</span> <span m='2823240'>3,</span>
  <span m='2823440'>et cetera.</span> <span m='2824850'>Over</span> <span
  m='2825150'>here,</span> <span m='2825520'>it's</span> <span
  m='2826770'>an</span> <span m='2826960'>order of</span> <span
  m='2827440'>0,</span> <span m='2827790'>4,</span> <span m='2828230'>2,
  6</span> <span m='2828670'>1,</span> <span m='2829110'>5,</span> <span
  m='2829440'>3,</span> <span m='2829875'>7.</span> </p><p><span
  m='2830745'>It</span> <span m='2831180'>will</span> <span
  m='2831360'>turn</span> <span m='2831690'>out</span> <span
  m='2832290'>that</span> <span m='2833070'>that</span> <span
  m='2833460'>order</span> <span m='2834120'>has</span> <span
  m='2834780'>a</span> <span m='2834810'>certain</span> <span
  m='2835170'>amount</span> <span m='2835410'>of</span> <span
  m='2835500'>significance.</span> <span m='2836310'>In</span> <span
  m='2836430'>fact,</span> <span m='2837310'>as</span> <span
  m='2837780'>we'll</span> <span m='2837960'>see,</span> <span
  m='2838770'>as</span> <span m='2839040'>we</span> <span
  m='2839160'>continue</span> <span m='2840180'>this</span> <span
  m='2840360'>discussion</span> <span m='2840930'>in</span> <span
  m='2841020'>the</span> <span m='2841110'>next</span> <span
  m='2841410'>lecture,</span> <span m='2842490'>that</span> <span
  m='2843270'>this</span> <span m='2844620'>is</span> <span
  m='2845100'>in</span> <span m='2845220'>fact</span> <span m='2845550'>a</span>
  <span m='2845610'>bit</span> <span m='2845880'>reversed</span> <span
  m='2846390'>order.</span> <span m='2847260'>It</span> <span
  m='2847440'>corresponds</span> <span m='2848190'>to</span> <span
  m='2848520'>rearranging</span> <span m='2849210'>the</span> <span
  m='2849300'>order</span> <span m='2849630'>of</span> <span
  m='2849720'>the</span> <span m='2849840'>bits</span> <span
  m='2851100'>in</span> <span m='2851730'>the</span> <span
  m='2852330'>binary</span> <span m='2852780'>representation</span> <span
  m='2853950'>of</span> <span m='2854580'>the</span> <span
  m='2855000'>indices.</span> <span m='2856320'>And</span> <span
  m='2856450'>furthermore,</span> <span m='2857370'>it's</span> <span
  m='2857550'>possible</span> <span m='2858750'>to</span> <span
  m='2859170'>interpret</span> <span m='2860130'>this</span> <span
  m='2860340'>flow</span> <span m='2860640'>graph</span> <span
  m='2861900'>in</span> <span m='2862080'>terms,</span> <span
  m='2862870'>not</span> <span m='2863070'>just</span> <span
  m='2863580'>of</span> <span m='2864540'>the</span> <span
  m='2864720'>computation</span> <span m='2866610'>of</span> <span
  m='2867240'>the</span> <span m='2867570'>discrete</span> <span
  m='2867960'>Fourier</span> <span m='2868380'>transform,</span> <span
  m='2869860'>but</span> <span m='2870120'>it</span> <span
  m='2870300'>also</span> <span m='2871230'>suggests</span> <span
  m='2872460'>how</span> <span m='2872940'>to</span> <span
  m='2873480'>arrange</span> <span m='2874410'>the</span> <span
  m='2875100'>memory,</span> <span m='2876360'>that</span> <span
  m='2876540'>is,</span> <span m='2876960'>the</span> <span
  m='2877110'>storage</span> <span m='2877920'>of</span> <span
  m='2878370'>the</span> <span m='2878520'>input</span> <span
  m='2878890'>sequence</span> <span m='2880020'>and</span> <span
  m='2880530'>the</span> <span m='2880620'>resulting</span> <span
  m='2881100'>storage</span> <span m='2881580'>of</span> <span
  m='2881640'>the</span> <span m='2881790'>output</span> <span
  m='2882150'>sequence.</span> <span m='2883690'>There</span> <span
  m='2883800'>are</span> <span m='2883830'>some</span> <span
  m='2884040'>efficiencies</span> <span m='2884850'>that</span> <span
  m='2885000'>result</span> <span m='2885900'>when</span> <span
  m='2886020'>we</span> <span m='2886140'>do</span> <span
  m='2886350'>that.</span> <span m='2887200'>And</span> <span
  m='2888240'>that's</span> <span m='2888690'>one</span> <span
  m='2888870'>of</span> <span m='2888960'>the</span> <span
  m='2889050'>first</span> <span m='2889320'>topics</span> <span
  m='2890010'>that</span> <span m='2890310'>we'll</span> <span
  m='2890940'>begin</span> <span m='2891270'>with</span> <span
  m='2891450'>next</span> <span m='2891750'>time.</span> </p><p><span
  m='2892590'>So</span> <span m='2893280'>in</span> <span m='2893880'>the</span>
  <span m='2893970'>next</span> <span m='2894240'>lecture</span> <span
  m='2894660'>then,</span> <span m='2895980'>we</span> <span
  m='2896310'>will</span> <span m='2897210'>continue</span> <span
  m='2898050'>on</span> <span m='2899100'>the</span> <span
  m='2899790'>development</span> <span m='2900660'>of</span> <span
  m='2900810'>the</span> <span m='2900900'>fast</span> <span
  m='2901230'>Fourier</span> <span m='2901590'>transform</span> <span
  m='2902220'>algorithm,</span> <span m='2903510'>picking</span> <span
  m='2903870'>up</span> <span m='2904260'>from</span> <span
  m='2904890'>the</span> <span m='2905010'>point</span> <span
  m='2905550'>that</span> <span m='2906000'>we've</span> <span
  m='2906210'>reached</span> <span m='2906630'>so</span> <span
  m='2906900'>far,</span> <span m='2907350'>which</span> <span
  m='2907650'>is--</span> <span m='2909150'>the</span> <span
  m='2909300'>point</span> <span m='2909540'>that</span> <span
  m='2909630'>we've</span> <span m='2909810'>reached</span> <span
  m='2910350'>is</span> <span m='2911040'>to</span> <span
  m='2911790'>have</span> <span m='2911970'>exposed</span> <span
  m='2913020'>one</span> <span m='2913290'>form</span> <span
  m='2914010'>of</span> <span m='2914570'>the</span> <span
  m='2914730'>fast</span> <span m='2915030'>Fourier</span> <span
  m='2915360'>transform</span> <span m='2915960'>algorithm.</span> <span
  m='2917010'>There</span> <span m='2917430'>are</span> <span
  m='2917700'>some</span> <span m='2918030'>important</span> <span
  m='2918450'>points</span> <span m='2918780'>to</span> <span
  m='2918870'>be</span> <span m='2918960'>made</span> <span
  m='2919200'>about</span> <span m='2919440'>that</span> <span
  m='2919690'>form.</span> <span m='2920250'>And</span> <span
  m='2920430'>then</span> <span m='2921060'>a</span> <span
  m='2921120'>variety</span> <span m='2922140'>of</span> <span
  m='2922500'>modifications</span> <span m='2924060'>of</span> <span
  m='2924180'>that</span> <span m='2924420'>form</span> <span
  m='2924930'>that</span> <span m='2925110'>have</span> <span
  m='2925440'>some</span> <span m='2925680'>advantages,</span> <span
  m='2926490'>and,</span> <span m='2926660'>as</span> <span
  m='2926820'>it</span> <span m='2926880'>will</span> <span
  m='2927000'>turn</span> <span m='2927270'>out,</span> <span
  m='2927480'>also</span> <span m='2928050'>some</span> <span
  m='2928260'>disadvantages.</span> <span m='2929510'>Thank</span> <span
  m='2929650'>you.</span> </p><p><span m='2932350'>[MUSIC PLAYING]</span>
  </p><p></p>
embedded_media:
  - uid: 4753a56f0fd115a04b158b64b0e6853c
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: MITRES_6_008S11_lec18.pdf
    title: MITRES_6_008S11_lec18.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-18-computation-of-the-discrete-fourier-transform-part-1/MITRES_6_008S11_lec18.pdf
  - uid: cb1f2755dc9dd8a79ac6de3d16a150ef
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: 14Vg7GyCVLY
  - uid: 576104a918f2f5bb93c59b6c293b34e2
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-18-computation-discrete/id481803782?i=108362011
  - uid: 99fe75525fefbe7b27835ee94785e998
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec18_300k.mp4'
  - uid: 0496d17778fa5c660e1ccea862da9501
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/14Vg7GyCVLY/default.jpg'
  - uid: e49aecba60a9b45742a30b151af357be
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: 14Vg7GyCVLY
  - uid: d5974c5eb6a1ad1dc579d787a9600511
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: 14Vg7GyCVLY.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-18-computation-of-the-discrete-fourier-transform-part-1/14Vg7GyCVLY.srt
  - uid: 1b2cf4212470a58b890c90622587a3de
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: 14Vg7GyCVLY.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-18-computation-of-the-discrete-fourier-transform-part-1/14Vg7GyCVLY.pdf
  - uid: 36bca3797bcff374fda321ed4f5007d4
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 9bf507e9a708bf4cb65f91904c6f919f
    parent_uid: b909330a94772374a9d125b7ebd1870a
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
