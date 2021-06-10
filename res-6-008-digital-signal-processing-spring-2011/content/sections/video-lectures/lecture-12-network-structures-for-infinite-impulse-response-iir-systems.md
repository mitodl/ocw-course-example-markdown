---
order_index: null
title: 'Lecture 12: Network Structures for Infinite Impulse Response (IIR) Systems'
template_type: Tabbed
uid: 947bb2fb248d5e3a7fd113ebea673243
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-12-network-structures-for-infinite-impulse-response-iir-systems
short_url: lecture-12-network-structures-for-infinite-impulse-response-iir-systems
inline_embed_id: >-
  84037651lecture12:networkstructuresforinfiniteimpulseresponse(iir)systems7870957
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Basic network structures for IIR filters,
  direct cascade and parallel form, canonic structures, transposition theorem
  for digital networks and the resulting transposed forms.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Network Structures for Infinite Impulse Response (IIR) Systems (<img
  src="/images/inacessible.gif" alt="This resource may not render correctly in a
  screen reader." /><a
  href="./resolveuid/e9b11b2996899c5eecd5ea00b0dd6bb2">PDF</a>)</p>
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
  m='48910'>ALAN OPPENHEIM:</span> <span m='49030'>Last</span> <span
  m='49150'>time</span> <span m='49480'>we</span> <span
  m='49780'>introduced</span> <span m='50260'>the</span> <span
  m='50350'>notion</span> <span m='51250'>of</span> <span
  m='51580'>digital</span> <span m='51940'>networks</span> <span
  m='52780'>and</span> <span m='53680'>the</span> <span m='53950'>general</span>
  <span m='54340'>topic</span> <span m='54940'>of</span> <span
  m='55090'>digital</span> <span m='55420'>network</span> <span
  m='55840'>theory.</span> <span m='57470'>There,</span> <span
  m='57970'>of</span> <span m='58120'>course,</span> <span m='58570'>are</span>
  <span m='59470'>lots</span> <span m='59770'>of</span> <span
  m='59860'>directions</span> <span m='60550'>that</span> <span
  m='60670'>that</span> <span m='60880'>discussion</span> <span
  m='61660'>can</span> <span m='61870'>proceed</span> <span m='62320'>in,</span>
  <span m='63100'>but</span> <span m='63550'>during</span> <span
  m='63880'>this</span> <span m='64030'>set</span> <span m='64239'>of</span>
  <span m='64360'>lectures,</span> <span m='65090'>we</span> <span
  m='65140'>won't</span> <span m='65410'>be</span> <span
  m='65860'>talking</span> <span m='66580'>in</span> <span m='66760'>any</span>
  <span m='66940'>more</span> <span m='67150'>detail</span> <span
  m='68170'>about</span> <span m='68470'>the</span> <span
  m='68590'>general</span> <span m='69010'>issues</span> <span
  m='69580'>of</span> <span m='69790'>digital</span> <span
  m='70120'>network</span> <span m='70540'>theory.</span> <span
  m='72370'>In</span> <span m='72460'>this</span> <span m='72670'>lecture</span>
  <span m='73300'>and</span> <span m='73450'>the</span> <span
  m='73540'>next</span> <span m='73810'>lecture,</span> <span m='74600'>I</span>
  <span m='74620'>would</span> <span m='74770'>like</span> <span
  m='75310'>to</span> <span m='75850'>consider,</span> <span m='77290'>in</span>
  <span m='77410'>particular,</span> <span m='78380'>some</span> <span
  m='78640'>of</span> <span m='78730'>the</span> <span m='78850'>more</span>
  <span m='79120'>common</span> <span m='79930'>structures</span> <span
  m='81250'>that</span> <span m='81550'>are</span> <span m='81670'>used</span>
  <span m='82330'>for</span> <span m='82750'>implementing</span> <span
  m='83560'>digital</span> <span m='83920'>filters--</span> <span
  m='85240'>first</span> <span m='85870'>for</span> <span m='86260'>the</span>
  <span m='86380'>case</span> <span m='86680'>of</span> <span
  m='86800'>infinite</span> <span m='87220'>impulse</span> <span
  m='87640'>response</span> <span m='88330'>filters,</span> <span
  m='89030'>which</span> <span m='89170'>we'll</span> <span
  m='89830'>discuss</span> <span m='90310'>in</span> <span m='90400'>this</span>
  <span m='90580'>lecture,</span> <span m='91630'>and</span> <span
  m='91750'>then</span> <span m='92160'>in</span> <span m='92230'>the</span>
  <span m='92320'>next</span> <span m='92590'>lecture</span> <span
  m='93550'>some</span> <span m='93970'>of</span> <span m='94120'>the</span>
  <span m='94210'>more</span> <span m='94420'>common</span> <span
  m='96280'>structures</span> <span m='97090'>for</span> <span
  m='97420'>finite</span> <span m='97870'>impulse</span> <span
  m='98260'>response</span> <span m='98950'>digital</span> <span
  m='99310'>filters.</span> </p><p><span m='100840'>To</span> <span
  m='100960'>begin</span> <span m='101230'>the</span> <span
  m='101320'>discussion,</span> <span m='103360'>let's</span> <span
  m='103630'>consider</span> <span m='105730'>the</span> <span
  m='105850'>most</span> <span m='106360'>general</span> <span
  m='107080'>form,</span> <span m='107830'>once</span> <span
  m='108130'>again,</span> <span m='108850'>for</span> <span
  m='109600'>the</span> <span m='109780'>transfer</span> <span
  m='110320'>function</span> <span m='111070'>of</span> <span
  m='111430'>a</span> <span m='111490'>digital</span> <span
  m='111880'>filter</span> <span m='113380'>where</span> <span
  m='114220'>we</span> <span m='114550'>are</span> <span
  m='114760'>assuming</span> <span m='115570'>that</span> <span
  m='116110'>the</span> <span m='116200'>system</span> <span
  m='116620'>function</span> <span m='117220'>H of z</span> <span
  m='118150'>is</span> <span m='118510'>a</span> <span
  m='118570'>rational</span> <span m='119050'>function</span> <span
  m='119750'>in</span> <span m='119860'>z</span> <span m='120080'>to</span>
  <span m='120140'>the</span> <span m='120250'>minus</span> <span
  m='120610'>1.</span> <span m='122338'>We</span> <span m='122770'>recall</span>
  <span m='123460'>from</span> <span m='124330'>our</span> <span
  m='124510'>previous</span> <span m='124990'>discussions</span> <span
  m='125950'>that</span> <span m='126370'>a</span> <span
  m='126610'>rational</span> <span m='127330'>transfer</span> <span
  m='127840'>function</span> <span m='128530'>of</span> <span
  m='128650'>this</span> <span m='128889'>form</span> <span
  m='130000'>corresponds</span> <span m='130960'>to</span> <span
  m='131560'>a</span> <span m='131770'>linear</span> <span
  m='132160'>constant</span> <span m='132610'>coefficient</span> <span
  m='133210'>difference</span> <span m='133600'>equation,</span> <span
  m='134800'>and</span> <span m='134950'>in</span> <span
  m='135070'>particular,</span> <span m='135940'>the</span> <span
  m='136060'>difference</span> <span m='136420'>equation</span> <span
  m='137020'>corresponding</span> <span m='137800'>to</span> <span
  m='137920'>this</span> <span m='138100'>system</span> <span
  m='138550'>function</span> <span m='139570'>is</span> <span
  m='139750'>the</span> <span m='139870'>difference</span> <span
  m='140200'>equation</span> <span m='141010'>that</span> <span
  m='141160'>I've</span> <span m='141280'>indicated</span> <span
  m='141850'>here.</span> <span m='143440'>The</span> <span
  m='143560'>coefficients</span> <span m='144460'>in</span> <span
  m='144610'>the</span> <span m='144700'>numerator</span> <span
  m='146080'>corresponding</span> <span m='146890'>to</span> <span
  m='147100'>the</span> <span m='147640'>polynomial</span> <span
  m='148810'>that</span> <span m='149080'>represents</span> <span
  m='149770'>the</span> <span m='149890'>0's</span> <span m='150580'>of</span>
  <span m='150700'>the</span> <span m='150820'>transfer</span> <span
  m='151300'>function</span> <span m='152560'>are</span> <span
  m='152920'>identical</span> <span m='153880'>to</span> <span
  m='154150'>the</span> <span m='154240'>coefficients</span> <span
  m='155230'>applied</span> <span m='156310'>to</span> <span
  m='157000'>the</span> <span m='157780'>delayed</span> <span
  m='158620'>values</span> <span m='159460'>of</span> <span
  m='159970'>the</span> <span m='160120'>input,</span> <span
  m='161950'>and</span> <span m='162070'>the</span> <span
  m='162160'>coefficients</span> <span m='162910'>in</span> <span
  m='163000'>the</span> <span m='163090'>denominator</span> <span
  m='164440'>corresponding</span> <span m='165280'>to</span> <span
  m='165610'>the</span> <span m='165730'>coefficients</span> <span
  m='166720'>for</span> <span m='167260'>the</span> <span
  m='167380'>polynomial</span> <span m='168280'>representing</span> <span
  m='168910'>the</span> <span m='169000'>poles</span> <span
  m='170680'>are</span> <span m='171130'>the</span> <span m='171250'>same</span>
  <span m='171550'>coefficients,</span> <span m='172690'>which,</span> <span
  m='172990'>in</span> <span m='173130'>the</span> <span
  m='173200'>difference</span> <span m='173590'>equation,</span> <span
  m='174280'>correspond</span> <span m='175450'>to</span> <span
  m='175570'>the</span> <span m='175690'>weights</span> <span
  m='176140'>applied</span> <span m='176740'>to</span> <span
  m='177430'>delayed</span> <span m='177820'>values</span> <span
  m='178570'>of</span> <span m='178720'>the</span> <span
  m='178870'>output.</span> </p><p><span m='180560'>So</span> <span
  m='180640'>this</span> <span m='180910'>is</span> <span m='181180'>the</span>
  <span m='181270'>general</span> <span m='181690'>form</span> <span
  m='182350'>of</span> <span m='182790'>a</span> <span
  m='182860'>transfer</span> <span m='183370'>function</span> <span
  m='183880'>for</span> <span m='184780'>assuming</span> <span
  m='185200'>that</span> <span m='185320'>the</span> <span
  m='185440'>system</span> <span m='185980'>is</span> <span
  m='186130'>representable</span> <span m='186880'>by</span> <span
  m='187090'>a</span> <span m='187120'>linear</span> <span
  m='187480'>constant</span> <span m='187930'>coefficient</span> <span
  m='188530'>difference</span> <span m='188890'>equation,</span> <span
  m='190060'>and</span> <span m='190900'>the</span> <span
  m='191200'>difference</span> <span m='191650'>equation</span> <span
  m='192760'>corresponding</span> <span m='193510'>to</span> <span
  m='193630'>this</span> <span m='193810'>transfer</span> <span
  m='194290'>function</span> <span m='195010'>is</span> <span
  m='195520'>as</span> <span m='195670'>I've</span> <span
  m='195820'>indicated</span> <span m='196390'>here.</span> <span
  m='198160'>Incidentally,</span> <span m='199000'>let</span> <span
  m='199180'>me</span> <span m='199300'>stress</span> <span m='199970'>as</span>
  <span m='200350'>I</span> <span m='201250'>indicated</span> <span
  m='201790'>in</span> <span m='201880'>the</span> <span m='201970'>last</span>
  <span m='202330'>lecture</span> <span m='203440'>that</span> <span
  m='204070'>our</span> <span m='204280'>assumption</span> <span
  m='205120'>will</span> <span m='205270'>be</span> <span
  m='205510'>throughout</span> <span m='205960'>these</span> <span
  m='206170'>discussions</span> <span m='207400'>that</span> <span
  m='207910'>we</span> <span m='208390'>are</span> <span
  m='210060'>discussing--</span> <span m='210840'>considering</span> <span
  m='211890'>a</span> <span m='212160'>causal</span> <span
  m='212790'>system.</span> <span m='213910'>In</span> <span
  m='213930'>other</span> <span m='214140'>words,</span> <span
  m='214840'>the</span> <span m='214860'>region</span> <span
  m='215190'>of</span> <span m='215280'>convergence</span> <span
  m='216090'>that</span> <span m='216210'>we</span> <span
  m='216360'>would</span> <span m='216480'>associate</span> <span
  m='217290'>with</span> <span m='217440'>this</span> <span
  m='217620'>transfer</span> <span m='218130'>function</span> <span
  m='219120'>is</span> <span m='219270'>the</span> <span
  m='219360'>region</span> <span m='219690'>of</span> <span
  m='219780'>convergence</span> <span m='220620'>that</span> <span
  m='220830'>would</span> <span m='221400'>correspond</span> <span
  m='222120'>to</span> <span m='222270'>a</span> <span m='222330'>causal</span>
  <span m='222750'>system.</span> <span m='223390'>In</span> <span
  m='223440'>other</span> <span m='223620'>words,</span> <span
  m='224380'>the</span> <span m='224480'>region</span> <span
  m='224670'>of</span> <span m='224760'>convergence</span> <span
  m='225420'>is</span> <span m='225540'>outside</span> <span
  m='226020'>the</span> <span m='226170'>outermost</span> <span
  m='226620'>pole.</span> </p><p><span m='229080'>There</span> <span
  m='229560'>are</span> <span m='229980'>a</span> <span
  m='230100'>variety</span> <span m='230940'>of</span> <span
  m='231120'>ways</span> <span m='231960'>in</span> <span
  m='232110'>which</span> <span m='232650'>we</span> <span m='232860'>can</span>
  <span m='233670'>rewrite</span> <span m='234660'>a</span> <span
  m='234720'>transfer</span> <span m='235230'>function</span> <span
  m='235980'>of</span> <span m='236130'>this</span> <span
  m='236370'>form.</span> <span m='237480'>One</span> <span
  m='237960'>possible</span> <span m='238530'>way</span> <span
  m='238950'>of</span> <span m='239130'>writing</span> <span
  m='239460'>this</span> <span m='239610'>transfer</span> <span
  m='240090'>function</span> <span m='240780'>is</span> <span
  m='241260'>as</span> <span m='241710'>I've</span> <span
  m='242130'>indicated</span> <span m='242850'>at</span> <span
  m='242970'>the</span> <span m='243060'>bottom.</span> <span
  m='244050'>That</span> <span m='244260'>is</span> <span m='245490'>an</span>
  <span m='245610'>expression</span> <span m='246390'>corresponding</span> <span
  m='247260'>to</span> <span m='247380'>the</span> <span
  m='247470'>product</span> <span m='248340'>of</span> <span
  m='248490'>two</span> <span m='248700'>functions--</span> <span
  m='250510'>the</span> <span m='250610'>first</span> <span
  m='251010'>representing</span> <span m='251910'>the</span> <span
  m='252000'>polynomial</span> <span m='253020'>for</span> <span
  m='253140'>the</span> <span m='253260'>0's,</span> <span m='254610'>and</span>
  <span m='254730'>the</span> <span m='254850'>second</span> <span
  m='255690'>representing</span> <span m='256620'>the</span> <span
  m='256709'>polynomial</span> <span m='257399'>for</span> <span
  m='257550'>the</span> <span m='257640'>poles.</span> <span
  m='259529'>What</span> <span m='259740'>this</span> <span
  m='259890'>suggests</span> <span m='260760'>is</span> <span
  m='261060'>that</span> <span m='261570'>we</span> <span m='261779'>can</span>
  <span m='262290'>imagine</span> <span m='262860'>implementing</span> <span
  m='263550'>this</span> <span m='263700'>system</span> <span
  m='265020'>by</span> <span m='265410'>implementing</span> <span
  m='266040'>a</span> <span m='266100'>system</span> <span
  m='266820'>which</span> <span m='267030'>realizes</span> <span
  m='268440'>this</span> <span m='268920'>transfer</span> <span
  m='269430'>function,</span> <span m='270600'>and</span> <span
  m='270750'>cascading</span> <span m='271560'>that--</span> <span
  m='272090'>the</span> <span m='272180'>cascade</span> <span
  m='272970'>leading</span> <span m='273300'>to</span> <span
  m='273390'>the</span> <span m='273510'>product</span> <span
  m='273930'>of</span> <span m='273990'>the</span> <span
  m='274110'>system</span> <span m='274500'>functions--</span> <span
  m='275550'>cascading</span> <span m='276250'>that</span> <span
  m='276540'>with</span> <span m='276720'>a</span> <span
  m='276750'>system</span> <span m='277650'>that</span> <span
  m='277800'>implements</span> <span m='278910'>this</span> <span
  m='279090'>system</span> <span m='279510'>function.</span> </p><p><span
  m='281200'>What</span> <span m='281370'>that</span> <span
  m='281580'>corresponds</span> <span m='282750'>to</span> <span
  m='283320'>in</span> <span m='283950'>the</span> <span
  m='284190'>implementation</span> <span m='285150'>of</span> <span
  m='285300'>the</span> <span m='285390'>difference</span> <span
  m='285780'>equation</span> <span m='287130'>is</span> <span
  m='287340'>first</span> <span m='287880'>implementing</span> <span
  m='288600'>in</span> <span m='288750'>terms</span> <span m='289080'>of</span>
  <span m='289170'>multipliers,</span> <span m='289950'>delays,</span> <span
  m='290430'>and</span> <span m='290520'>adders</span> <span
  m='291000'>as</span> <span m='291150'>we</span> <span m='291630'>talked</span>
  <span m='291930'>about</span> <span m='292200'>last</span> <span
  m='292530'>time--</span> <span m='293460'>implementing</span> <span
  m='294090'>first</span> <span m='295140'>the</span> <span
  m='295470'>linear</span> <span m='295830'>combination</span> <span
  m='296790'>of</span> <span m='297270'>the</span> <span
  m='297510'>weighted</span> <span m='298980'>delayed</span> <span
  m='300090'>input</span> <span m='300930'>values,</span> <span
  m='302830'>and</span> <span m='302910'>then</span> <span
  m='303750'>using</span> <span m='304170'>that</span> <span
  m='304530'>as</span> <span m='304710'>the</span> <span m='304860'>input</span>
  <span m='305460'>to</span> <span m='305640'>a</span> <span
  m='305700'>system</span> <span m='306420'>which</span> <span
  m='306630'>implements</span> <span m='307470'>the</span> <span
  m='307590'>weighted</span> <span m='308280'>delayed</span> <span
  m='308970'>output</span> <span m='309420'>values.</span> <span
  m='310600'>So</span> <span m='311310'>implementing</span> <span
  m='312120'>this</span> <span m='312330'>system</span> <span
  m='312750'>function</span> <span m='314250'>with</span> <span
  m='315000'>this</span> <span m='316110'>function</span> <span
  m='317370'>first</span> <span m='318550'>in</span> <span
  m='318720'>cascade</span> <span m='319520'>with</span> <span
  m='319770'>this</span> <span m='320760'>corresponds</span> <span
  m='321750'>to</span> <span m='322050'>implementing</span> <span
  m='322710'>this</span> <span m='323610'>difference</span> <span
  m='324000'>equation</span> <span m='325200'>where</span> <span
  m='325830'>we</span> <span m='326010'>can</span> <span
  m='326190'>imagine</span> <span m='329080'>denoting</span> <span
  m='329920'>this</span> <span m='330160'>first</span> <span
  m='330550'>sum</span> <span m='333090'>as</span> <span m='333760'>x1</span>
  <span m='334500'>of</span> <span m='334780'>n--</span> <span
  m='336840'>implementing</span> <span m='337670'>x1</span> <span
  m='338160'>of</span> <span m='338310'>n--</span> <span
  m='339870'>implementing</span> <span m='340590'>the</span> <span
  m='340680'>function</span> <span m='341140'>x1</span> <span
  m='341550'>of</span> <span m='341700'>n,</span> <span m='342450'>and</span>
  <span m='342570'>then</span> <span m='342780'>using</span> <span
  m='343200'>that</span> <span m='343560'>as</span> <span m='343740'>the</span>
  <span m='343890'>input</span> <span m='344580'>to</span> <span
  m='344730'>a</span> <span m='344790'>system</span> <span
  m='345480'>which</span> <span m='345690'>is</span> <span
  m='345810'>represented</span> <span m='346470'>by</span> <span
  m='346650'>the</span> <span m='346740'>difference</span> <span
  m='347100'>equation</span> <span m='347610'>y</span> <span
  m='347900'>of</span> <span m='348050'>n</span> <span m='348720'>equals</span>
  <span m='349020'>x1</span> <span m='349310'>of</span> <span
  m='349510'>n</span> <span m='350310'>plus</span> <span m='350750'>this</span>
  <span m='351120'>sum.</span> </p><p><span m='352580'>Carrying</span> <span
  m='353000'>that</span> <span m='353210'>out,</span> <span
  m='354260'>the</span> <span m='356120'>digital</span> <span
  m='356480'>network</span> <span m='357230'>that</span> <span
  m='357380'>results</span> <span m='361250'>is</span> <span
  m='361910'>as</span> <span m='362330'>I've</span> <span
  m='362480'>indicated</span> <span m='363080'>here,</span> <span
  m='364530'>where</span> <span m='365120'>we</span> <span
  m='365330'>have,</span> <span m='366000'>first</span> <span
  m='366260'>of</span> <span m='366380'>all,</span> <span m='367320'>the</span>
  <span m='367580'>linear</span> <span m='367940'>combination</span> <span
  m='368990'>of</span> <span m='369470'>weighted</span> <span
  m='370370'>delayed</span> <span m='371270'>input</span> <span
  m='371690'>values.</span> <span m='373080'>So</span> <span
  m='373340'>here</span> <span m='373640'>is</span> <span m='373790'>x</span>
  <span m='374120'>of</span> <span m='374240'>n,</span> <span
  m='375050'>x</span> <span m='375290'>of</span> <span m='375380'>n</span> <span
  m='375530'>minus</span> <span m='375950'>1,</span> <span m='376050'>x</span>
  <span m='376430'>of</span> <span m='376790'>n</span> <span
  m='377030'>minus</span> <span m='377420'>2,</span> <span
  m='378230'>down</span> <span m='378530'>through</span> <span
  m='378860'>x</span> <span m='379130'>of</span> <span m='379250'>n</span> <span
  m='379760'>minus</span> <span m='380090'>capital</span> <span
  m='380600'>N,</span> <span m='381410'>where</span> <span m='381890'>I'm</span>
  <span m='382040'>assuming</span> <span m='383240'>in</span> <span
  m='383390'>drawing</span> <span m='383810'>this</span> <span
  m='384530'>that</span> <span m='384650'>capital</span> <span
  m='385160'>M</span> <span m='385670'>is</span> <span m='385850'>equal</span>
  <span m='386450'>to</span> <span m='386540'>capital</span> <span
  m='387080'>N.</span> <span m='388820'>This</span> <span
  m='389270'>first</span> <span m='389600'>block</span> <span
  m='390020'>then</span> <span m='390500'>implements</span> <span
  m='392240'>this</span> <span m='392690'>summation</span> <span
  m='394040'>to</span> <span m='394160'>form</span> <span m='394700'>x1</span>
  <span m='395180'>of</span> <span m='395300'>n,</span> <span
  m='396680'>and</span> <span m='397790'>then</span> <span m='398570'>the</span>
  <span m='398780'>second</span> <span m='399380'>system</span> <span
  m='400490'>which</span> <span m='400730'>this</span> <span
  m='400910'>has</span> <span m='401030'>cascaded</span> <span
  m='401780'>with</span> <span m='402500'>has</span> <span m='402930'>as</span>
  <span m='403100'>an</span> <span m='403190'>input</span> <span
  m='403620'>x1</span> <span m='404070'>of</span> <span m='404170'>n</span>
  <span m='405020'>and</span> <span m='405320'>added</span> <span
  m='405680'>to</span> <span m='405980'>it</span> <span
  m='406130'>weighted</span> <span m='406820'>delayed</span> <span
  m='407510'>values</span> <span m='407960'>of</span> <span
  m='408080'>the</span> <span m='408200'>output.</span> <span
  m='409200'>So</span> <span m='409520'>here</span> <span m='409780'>is</span>
  <span m='409910'>y</span> <span m='410210'>of n,</span> <span
  m='411020'>y</span> <span m='411290'>of n</span> <span m='411560'>minus</span>
  <span m='411950'>1,</span> <span m='412630'>down</span> <span
  m='412970'>through</span> <span m='413180'>y</span> <span m='413420'>of</span>
  <span m='413540'>n</span> <span m='413690'>minus</span> <span
  m='414020'>capital</span> <span m='414580'>N.</span> <span
  m='415250'>We</span> <span m='415400'>see</span> <span m='415550'>the</span>
  <span m='415670'>coefficients</span> <span m='416830'>a1,</span> <span
  m='417395'>a2,</span> <span m='418165'>through</span> <span
  m='418550'>a</span> <span m='418790'>sub</span> <span
  m='418880'>capital</span> <span m='419390'>N.</span> <span
  m='420200'>Clearly</span> <span m='420860'>in</span> <span
  m='421010'>this</span> <span m='421190'>implementation</span> <span
  m='423140'>this</span> <span m='423410'>block</span> <span
  m='424550'>corresponds</span> <span m='425450'>to</span> <span
  m='425750'>implementing</span> <span m='426320'>the</span> <span
  m='426410'>zeros</span> <span m='426950'>of</span> <span m='427040'>the</span>
  <span m='427130'>system,</span> <span m='428270'>and</span> <span
  m='429110'>this</span> <span m='429380'>block</span> <span
  m='430190'>corresponds</span> <span m='431120'>to</span> <span
  m='431510'>implementing</span> <span m='432080'>the</span> <span
  m='432170'>poles</span> <span m='432590'>of</span> <span m='432680'>the</span>
  <span m='432770'>system.</span> <span m='433640'>So</span> <span
  m='434510'>as</span> <span m='434930'>we've</span> <span
  m='435170'>factored</span> <span m='436130'>the</span> <span
  m='436400'>transfer</span> <span m='436940'>function</span> <span
  m='437990'>into</span> <span m='438520'>the</span> <span m='438650'>0's</span>
  <span m='439340'>followed</span> <span m='439730'>by</span> <span
  m='439910'>the</span> <span m='440030'>poles,</span> <span
  m='441050'>we</span> <span m='441230'>have</span> <span m='441740'>this</span>
  <span m='441950'>system</span> <span m='442460'>implementing</span> <span
  m='443030'>the</span> <span m='443120'>0's</span> <span
  m='443990'>followed</span> <span m='444380'>by</span> <span
  m='444560'>this</span> <span m='444740'>system</span> <span
  m='445370'>implementing</span> <span m='445910'>the</span> <span
  m='446000'>poles.</span> </p><p><span m='448080'>Well,</span> <span
  m='448400'>this,</span> <span m='448640'>of</span> <span
  m='448730'>course,</span> <span m='449240'>is</span> <span
  m='449450'>one</span> <span m='449660'>implementation</span> <span
  m='450680'>of</span> <span m='451160'>the</span> <span
  m='451280'>difference</span> <span m='451640'>equation,</span> <span
  m='452840'>but</span> <span m='453110'>in</span> <span m='453290'>fact,</span>
  <span m='453890'>there</span> <span m='454340'>are</span> <span
  m='454670'>a</span> <span m='454790'>variety</span> <span m='455360'>of</span>
  <span m='455510'>ways</span> <span m='456020'>in</span> <span
  m='456140'>which</span> <span m='456440'>we</span> <span m='456590'>can</span>
  <span m='456770'>manipulate</span> <span m='457910'>the</span> <span
  m='458090'>transfer</span> <span m='458660'>function,</span> <span
  m='459650'>or,</span> <span m='459800'>equivalently,</span> <span
  m='460730'>in</span> <span m='460850'>which</span> <span m='461060'>we</span>
  <span m='461180'>can</span> <span m='461360'>manipulate</span> <span
  m='461990'>the</span> <span m='462110'>difference</span> <span
  m='462500'>equation,</span> <span m='463610'>which</span> <span
  m='464000'>will</span> <span m='464210'>lead</span> <span m='464660'>to</span>
  <span m='465080'>other</span> <span m='465500'>structures</span> <span
  m='466490'>for</span> <span m='466700'>implementing</span> <span
  m='467240'>the</span> <span m='467330'>system</span> <span
  m='468230'>besides</span> <span m='468920'>the</span> <span
  m='469040'>structure</span> <span m='469490'>that</span> <span
  m='469610'>I've</span> <span m='469760'>indicated</span> <span
  m='470330'>here.</span> <span m='471680'>Well,</span> <span
  m='471920'>let's</span> <span m='472130'>consider</span> <span
  m='473000'>one</span> <span m='473210'>simple</span> <span
  m='473870'>way</span> <span m='474320'>of</span> <span
  m='475010'>manipulating</span> <span m='475730'>this</span> <span
  m='475840'>system</span> <span m='476330'>to</span> <span
  m='476450'>generate</span> <span m='477290'>another</span> <span
  m='477650'>structure.</span> </p><p><span m='479510'>We</span> <span
  m='479600'>recognize</span> <span m='480290'>this</span> <span
  m='480650'>as</span> <span m='481310'>two</span> <span
  m='481490'>systems</span> <span m='482000'>in</span> <span
  m='482120'>cascade.</span> <span m='484220'>They</span> <span
  m='484370'>both</span> <span m='484760'>implement</span> <span
  m='485330'>linear</span> <span m='486110'>shift</span> <span
  m='486440'>invariant</span> <span m='487000'>systems,</span> <span
  m='488150'>and</span> <span m='488240'>we</span> <span m='488360'>know</span>
  <span m='488720'>that</span> <span m='489350'>two</span> <span
  m='489530'>linear</span> <span m='489860'>shift</span> <span
  m='490160'>invariant</span> <span m='490680'>systems</span> <span
  m='491150'>in</span> <span m='491270'>cascade</span> <span
  m='492470'>can</span> <span m='492650'>be</span> <span
  m='492800'>cascaded</span> <span m='493730'>in</span> <span
  m='493970'>either</span> <span m='494280'>order</span> <span
  m='495260'>without</span> <span m='495680'>affecting</span> <span
  m='496250'>the</span> <span m='496400'>overall</span> <span
  m='496820'>transfer</span> <span m='497270'>function</span> <span
  m='497660'>of</span> <span m='497720'>the</span> <span
  m='497810'>system.</span> <span m='499430'>So</span> <span
  m='499640'>we</span> <span m='499760'>can</span> <span
  m='499940'>imagine</span> <span m='500960'>just</span> <span
  m='501200'>simply</span> <span m='501830'>breaking</span> <span
  m='502370'>the</span> <span m='502460'>system</span> <span
  m='502880'>at</span> <span m='503000'>this</span> <span
  m='503210'>point,</span> <span m='504560'>interchanging</span> <span
  m='505520'>the</span> <span m='505670'>order</span> <span m='506030'>in</span>
  <span m='506180'>which</span> <span m='506420'>these</span> <span
  m='506630'>two</span> <span m='506810'>systems</span> <span
  m='507290'>are</span> <span m='507380'>cascaded,</span> <span
  m='508550'>and</span> <span m='508700'>obviously</span> <span
  m='509400'>what</span> <span m='509450'>that</span> <span
  m='509630'>leads</span> <span m='509960'>to</span> <span m='510290'>is</span>
  <span m='510560'>a</span> <span m='510620'>second</span> <span
  m='511010'>implementation</span> <span m='511910'>of</span> <span
  m='512059'>the</span> <span m='512150'>same</span> <span
  m='512419'>difference</span> <span m='512809'>equation.</span> <span
  m='514470'>That</span> <span m='514700'>implementation</span> <span
  m='515450'>in</span> <span m='515510'>particular,</span> <span
  m='516289'>whereas</span> <span m='516679'>this</span> <span
  m='516890'>one</span> <span m='517070'>has</span> <span m='517309'>the</span>
  <span m='517400'>zeros</span> <span m='517909'>first</span> <span
  m='518850'>followed</span> <span m='519140'>by</span> <span
  m='519320'>the</span> <span m='519530'>poles--</span> <span
  m='520640'>interchanging</span> <span m='521390'>the</span> <span
  m='521510'>order</span> <span m='521870'>of</span> <span
  m='521990'>those</span> <span m='522320'>two</span> <span
  m='523130'>will</span> <span m='523280'>result</span> <span
  m='523850'>in</span> <span m='523970'>the</span> <span m='524059'>poles</span>
  <span m='524690'>implemented</span> <span m='525230'>first,</span> <span
  m='526050'>followed</span> <span m='526310'>by</span> <span
  m='526490'>the</span> <span m='526580'>0's,</span> <span m='527630'>and</span>
  <span m='527750'>the</span> <span m='527840'>system</span> <span
  m='528560'>that</span> <span m='528740'>results</span> <span
  m='529820'>is</span> <span m='530360'>what</span> <span m='530540'>I've</span>
  <span m='530690'>indicated</span> <span m='532400'>on</span> <span
  m='532970'>this</span> <span m='533180'>next</span> <span
  m='533480'>view</span> <span m='533660'>graph.</span> </p><p><span
  m='535380'>So</span> <span m='536030'>this</span> <span
  m='536240'>system</span> <span m='537290'>is</span> <span
  m='537560'>identical</span> <span m='538130'>to</span> <span
  m='538250'>the</span> <span m='538400'>other</span> <span
  m='538610'>one.</span> <span m='539030'>It's</span> <span
  m='539270'>clearly</span> <span m='539630'>identical</span> <span
  m='540290'>in</span> <span m='540410'>terms</span> <span m='540710'>of</span>
  <span m='540770'>the</span> <span m='540920'>overall</span> <span
  m='541340'>transfer</span> <span m='541820'>function,</span> <span
  m='543060'>and</span> <span m='543160'>what</span> <span
  m='543230'>I've</span> <span m='543380'>done</span> <span
  m='543620'>simply</span> <span m='544460'>is</span> <span
  m='545210'>just</span> <span m='545510'>to</span> <span
  m='545690'>interchange</span> <span m='546950'>the</span> <span
  m='547100'>order</span> <span m='547610'>in</span> <span
  m='547760'>which</span> <span m='548060'>the</span> <span
  m='548180'>0's</span> <span m='548870'>and</span> <span m='549020'>the</span>
  <span m='549110'>poles</span> <span m='550220'>are</span> <span
  m='550670'>implemented.</span> <span m='553120'>Well,</span> <span
  m='553930'>that</span> <span m='554170'>manipulation</span> <span
  m='555460'>that</span> <span m='555640'>is</span> <span
  m='555910'>breaking</span> <span m='556360'>that</span> <span
  m='556510'>system</span> <span m='557080'>and</span> <span
  m='557200'>interchanging</span> <span m='557980'>the</span> <span
  m='558100'>order</span> <span m='558550'>in</span> <span
  m='558670'>which</span> <span m='558850'>the</span> <span
  m='558940'>systems</span> <span m='559390'>are</span> <span
  m='559480'>cascaded</span> <span m='560830'>can</span> <span
  m='561190'>be</span> <span m='561340'>interpreted</span> <span
  m='562090'>in</span> <span m='562270'>terms</span> <span m='562750'>of</span>
  <span m='563110'>either</span> <span m='563420'>a</span> <span
  m='563440'>manipulation</span> <span m='564280'>on</span> <span
  m='564370'>the</span> <span m='564460'>transfer</span> <span
  m='564970'>function</span> <span m='565870'>or</span> <span
  m='566080'>a</span> <span m='566110'>manipulation</span> <span
  m='566890'>on</span> <span m='566980'>the</span> <span
  m='567070'>difference</span> <span m='567460'>equation,</span> <span
  m='568720'>and</span> <span m='569170'>to</span> <span
  m='569290'>indicate</span> <span m='570070'>what</span> <span
  m='570310'>that</span> <span m='570520'>corresponds</span> <span
  m='571360'>to</span> <span m='573040'>let's</span> <span
  m='573310'>return</span> <span m='573970'>to</span> <span
  m='577380'>the</span> <span m='577770'>general</span> <span
  m='578670'>difference</span> <span m='579060'>equation</span> <span
  m='580050'>as</span> <span m='580290'>we</span> <span m='580440'>had</span>
  <span m='580680'>it</span> <span m='580980'>on</span> <span
  m='581130'>the</span> <span m='581250'>first</span> <span
  m='581550'>view</span> <span m='581790'>graph--</span> <span
  m='583320'>the</span> <span m='583440'>transfer</span> <span
  m='583980'>function,</span> <span m='585050'>where</span> <span
  m='585320'>now,</span> <span m='585990'>rather</span> <span
  m='586410'>than</span> <span m='586800'>cascading</span> <span
  m='587580'>this</span> <span m='587820'>system</span> <span
  m='588600'>first</span> <span m='589170'>and</span> <span
  m='589320'>this</span> <span m='589470'>system</span> <span
  m='589920'>second,</span> <span m='590820'>we've</span> <span
  m='590970'>simply</span> <span m='591480'>interchanged</span> <span
  m='592170'>the</span> <span m='592320'>order</span> <span m='592830'>in</span>
  <span m='592980'>which</span> <span m='593220'>those</span> <span
  m='593430'>two</span> <span m='593580'>systems</span> <span
  m='594300'>are</span> <span m='594420'>cascaded.</span> <span
  m='595650'>That's</span> <span m='595920'>interpreting</span> <span
  m='596490'>this</span> <span m='596700'>operation</span> <span
  m='597510'>in</span> <span m='597660'>terms</span> <span m='598140'>of</span>
  <span m='598260'>the</span> <span m='598350'>transfer</span> <span
  m='598830'>function.</span> </p><p><span m='600660'>To</span> <span
  m='600810'>interpret</span> <span m='601290'>it</span> <span
  m='601470'>in</span> <span m='601650'>terms</span> <span m='602160'>of</span>
  <span m='602280'>the</span> <span m='602370'>difference</span> <span
  m='602730'>equation</span> <span m='603900'>is</span> <span
  m='604200'>slightly</span> <span m='604650'>more</span> <span
  m='604890'>involved,</span> <span m='605820'>but</span> <span
  m='606450'>basically</span> <span m='607650'>and</span> <span
  m='607890'>very</span> <span m='608130'>quickly</span> <span
  m='609180'>what</span> <span m='609390'>it</span> <span
  m='609630'>involves</span> <span m='610770'>is</span> <span
  m='611400'>first</span> <span m='611790'>implementing</span> <span
  m='612870'>the</span> <span m='612960'>difference</span> <span
  m='613350'>equation</span> <span m='614100'>in</span> <span
  m='614250'>which</span> <span m='614880'>we</span> <span
  m='615060'>consider</span> <span m='615780'>that</span> <span
  m='615990'>the</span> <span m='616110'>input</span> <span m='616470'>is</span>
  <span m='616560'>just</span> <span m='617030'>x of n</span> <span
  m='618000'>rather</span> <span m='618330'>than</span> <span
  m='618570'>a</span> <span m='618660'>weighted</span> <span
  m='619020'>sum</span> <span m='619410'>of</span> <span
  m='619560'>delayed</span> <span m='620920'>x</span> <span m='621200'>of
  n's</span> <span m='622770'>to</span> <span m='622920'>implement</span> <span
  m='624060'>to</span> <span m='624480'>implement</span> <span
  m='625230'>the</span> <span m='625410'>output</span> <span
  m='625820'>y1</span> <span m='626380'>of n.</span> <span m='628020'>And</span>
  <span m='628170'>then</span> <span m='628620'>since</span> <span
  m='628920'>the</span> <span m='629070'>input</span> <span
  m='629460'>is,</span> <span m='629610'>in</span> <span m='629730'>fact,</span>
  <span m='630120'>a</span> <span m='630150'>linear</span> <span
  m='630570'>combination</span> <span m='631350'>of</span> <span
  m='631440'>weighted</span> <span m='631800'>delayed</span> <span
  m='632270'>inputs,</span> <span m='633180'>the</span> <span
  m='633270'>corresponding</span> <span m='634020'>output</span> <span
  m='634560'>is</span> <span m='634740'>the</span> <span m='634860'>same</span>
  <span m='635310'>linear</span> <span m='635670'>combination</span> <span
  m='636510'>of</span> <span m='636690'>weighted</span> <span
  m='636990'>delayed</span> <span m='637350'>outputs.</span> <span
  m='638190'>That</span> <span m='638520'>essentially</span> <span
  m='639120'>is</span> <span m='639240'>derived</span> <span
  m='639810'>from</span> <span m='640050'>using</span> <span
  m='640500'>properties</span> <span m='641760'>of</span> <span
  m='642090'>linear</span> <span m='642510'>shift</span> <span
  m='642840'>invariant</span> <span m='643350'>systems</span> <span
  m='643890'>that</span> <span m='643980'>we</span> <span
  m='644130'>talked</span> <span m='644460'>about</span> <span
  m='644710'>and</span> <span m='644800'>some</span> <span m='645030'>of</span>
  <span m='645090'>the</span> <span m='645210'>early</span> <span
  m='645480'>lectures.</span> </p><p><span m='647690'>Well,</span> <span
  m='649570'>returning</span> <span m='650560'>to</span> <span
  m='651310'>the</span> <span m='652210'>network</span> <span
  m='653080'>that</span> <span m='653350'>resulted</span> <span
  m='654550'>by</span> <span m='655000'>interchanging</span> <span
  m='656680'>the</span> <span m='656830'>order</span> <span m='657460'>of</span>
  <span m='657610'>these</span> <span m='657880'>two</span> <span
  m='658090'>systems,</span> <span m='659830'>one</span> <span
  m='660010'>of</span> <span m='660070'>the</span> <span
  m='660190'>questions</span> <span m='660640'>we</span> <span
  m='660790'>can</span> <span m='660970'>ask,</span> <span m='661240'>of</span>
  <span m='661360'>course,</span> <span m='661970'>is</span> <span
  m='662050'>whether</span> <span m='662980'>there</span> <span
  m='663370'>is</span> <span m='663550'>any</span> <span
  m='663760'>advantage</span> <span m='665020'>to</span> <span
  m='665320'>implementing</span> <span m='665920'>this</span> <span
  m='666100'>system</span> <span m='666850'>rather</span> <span
  m='667270'>than</span> <span m='667540'>implementing</span> <span
  m='668320'>the</span> <span m='668440'>first</span> <span
  m='668710'>system</span> <span m='669100'>that</span> <span
  m='669220'>we</span> <span m='669370'>derived.</span> <span
  m='670750'>And</span> <span m='670870'>in</span> <span
  m='670960'>answering</span> <span m='671470'>that,</span> <span
  m='672340'>one</span> <span m='672550'>thing</span> <span
  m='672820'>that</span> <span m='672940'>we</span> <span
  m='673090'>notice</span> <span m='673690'>about</span> <span
  m='674050'>this</span> <span m='674230'>system</span> <span
  m='675730'>is</span> <span m='675910'>that</span> <span
  m='676270'>there</span> <span m='676570'>are</span> <span
  m='676720'>two</span> <span m='676990'>parallel</span> <span
  m='677530'>branches</span> <span m='678160'>here</span> <span
  m='680150'>with</span> <span m='680930'>corresponding</span> <span
  m='681770'>delays.</span> <span m='683420'>Now,</span> <span
  m='683690'>what</span> <span m='683900'>does</span> <span
  m='684020'>that</span> <span m='684260'>mean?</span> <span
  m='685350'>Well,</span> <span m='685700'>if</span> <span m='685850'>we</span>
  <span m='685970'>consider</span> <span m='687050'>this</span> <span
  m='687290'>output</span> <span m='688250'>to</span> <span m='688370'>be</span>
  <span m='688550'>y1</span> <span m='689060'>of</span> <span
  m='689190'>n--</span> <span m='689780'>it's</span> <span m='689930'>the</span>
  <span m='690050'>y1</span> <span m='690260'>of</span> <span
  m='690440'>n</span> <span m='690680'>that</span> <span m='690800'>we</span>
  <span m='691040'>had</span> <span m='691190'>defined</span> <span
  m='691580'>in</span> <span m='691670'>the</span> <span
  m='691730'>previous</span> <span m='692120'>slide--</span> <span
  m='693780'>the</span> <span m='693900'>value</span> <span
  m='694290'>appearing</span> <span m='694710'>here</span> <span
  m='694980'>is</span> <span m='695100'>y1</span> <span m='695550'>of</span>
  <span m='695670'>n</span> <span m='695820'>minus</span> <span
  m='696210'>1,</span> <span m='697140'>but</span> <span m='697290'>the</span>
  <span m='697380'>value</span> <span m='697740'>appearing</span> <span
  m='698130'>here</span> <span m='698400'>is</span> <span m='698520'>y1</span>
  <span m='698910'>of</span> <span m='699040'>n</span> <span
  m='699180'>minus</span> <span m='699570'>1.</span> <span m='700396'>The</span>
  <span m='700810'>value</span> <span m='701160'>appearing</span> <span
  m='701490'>here</span> <span m='701820'>is</span> <span m='702300'>y1</span>
  <span m='702570'>of</span> <span m='702800'>n</span> <span
  m='702990'>minus</span> <span m='703380'>2</span> <span m='704030'>and</span>
  <span m='704160'>appearing</span> <span m='704530'>here</span> <span
  m='704790'>is</span> <span m='704940'>y1</span> <span m='705330'>of</span>
  <span m='705440'>n</span> <span m='705600'>minus</span> <span
  m='705960'>2.</span> <span m='706740'>And</span> <span m='706860'>in</span>
  <span m='706950'>fact,</span> <span m='707520'>following</span> <span
  m='708000'>this</span> <span m='708180'>chain</span> <span
  m='709140'>down,</span> <span m='710130'>what</span> <span
  m='710280'>we</span> <span m='710490'>observe</span> <span
  m='711180'>is</span> <span m='711390'>that</span> <span m='711570'>the</span>
  <span m='711720'>output</span> <span m='712200'>of</span> <span
  m='712290'>this</span> <span m='712530'>delay</span> <span
  m='713940'>is</span> <span m='714120'>exactly</span> <span
  m='714720'>the</span> <span m='714840'>same</span> <span m='715200'>as</span>
  <span m='715290'>the</span> <span m='715440'>output</span> <span
  m='715800'>of</span> <span m='715940'>this</span> <span
  m='716140'>delay.</span> </p><p><span m='717780'>Well,</span> <span
  m='718080'>if</span> <span m='718230'>that's</span> <span
  m='718500'>the</span> <span m='718620'>case,</span> <span
  m='719380'>then</span> <span m='719490'>in</span> <span m='719580'>fact</span>
  <span m='720360'>there</span> <span m='720630'>obviously,</span> <span
  m='721470'>if</span> <span m='721620'>we</span> <span m='721740'>think</span>
  <span m='721950'>about</span> <span m='722150'>an</span> <span
  m='722270'>implementation,</span> <span m='723660'>is</span> <span
  m='723810'>no</span> <span m='724050'>reason</span> <span m='725310'>to</span>
  <span m='725730'>separately</span> <span m='726390'>store</span> <span
  m='727170'>this</span> <span m='728190'>delayed</span> <span
  m='728580'>output</span> <span m='729420'>and</span> <span
  m='729570'>this</span> <span m='729780'>delayed</span> <span
  m='730170'>output</span> <span m='730740'>since</span> <span
  m='731020'>they're</span> <span m='731190'>the</span> <span
  m='731310'>same.</span> <span m='732310'>In</span> <span
  m='732330'>other</span> <span m='732540'>words,</span> <span
  m='733150'>we</span> <span m='733260'>can</span> <span
  m='733410'>collapse</span> <span m='734370'>these</span> <span
  m='734940'>delays</span> <span m='735360'>together,</span> <span
  m='736470'>and</span> <span m='737250'>the</span> <span
  m='737370'>network</span> <span m='738030'>that</span> <span
  m='738180'>results</span> <span m='738960'>when</span> <span
  m='739110'>we</span> <span m='739230'>do</span> <span m='739440'>that</span>
  <span m='741210'>is</span> <span m='742050'>the</span> <span
  m='742140'>network</span> <span m='742920'>that</span> <span
  m='743280'>I</span> <span m='743430'>indicate</span> <span
  m='743970'>here,</span> <span m='744920'>where</span> <span
  m='745230'>all</span> <span m='745440'>that</span> <span
  m='745590'>I've</span> <span m='745740'>done</span> <span m='746200'>in</span>
  <span m='746360'>going</span> <span m='746670'>from</span> <span
  m='746820'>the</span> <span m='746910'>previous</span> <span
  m='747390'>network</span> <span m='747870'>to</span> <span
  m='748020'>this</span> <span m='748290'>one</span> <span m='749010'>is</span>
  <span m='749100'>simply</span> <span m='749820'>collapse</span> <span
  m='751020'>the</span> <span m='751110'>delays</span> <span
  m='751590'>together,</span> <span m='752520'>taking</span> <span
  m='752820'>advantage</span> <span m='753330'>of</span> <span
  m='753420'>the</span> <span m='753540'>fact</span> <span
  m='754260'>that</span> <span m='754380'>their</span> <span
  m='754560'>outputs</span> <span m='755040'>were</span> <span
  m='755190'>identical.</span> </p><p><span m='757240'>Now,</span> <span
  m='757560'>in</span> <span m='757710'>drawing</span> <span m='758130'>a</span>
  <span m='758190'>network,</span> <span m='759240'>of</span> <span
  m='759360'>course,</span> <span m='759990'>it</span> <span
  m='760110'>doesn't</span> <span m='760800'>particularly</span> <span
  m='761430'>matter</span> <span m='762300'>whether</span> <span
  m='762930'>we</span> <span m='764040'>conserve</span> <span
  m='764760'>z</span> <span m='765040'>to</span> <span m='765180'>the</span>
  <span m='765270'>minus</span> <span m='765690'>1's</span> <span
  m='766050'>or</span> <span m='766140'>equivalently</span> <span
  m='767040'>whether</span> <span m='767370'>we</span> <span
  m='767520'>collapse</span> <span m='768030'>a</span> <span
  m='768090'>network</span> <span m='768990'>when</span> <span
  m='769470'>we</span> <span m='769620'>can</span> <span m='769770'>take</span>
  <span m='769980'>advantage</span> <span m='770430'>of</span> <span
  m='770520'>the</span> <span m='770610'>fact</span> <span
  m='771000'>that</span> <span m='771120'>the</span> <span
  m='771270'>output</span> <span m='772050'>of</span> <span
  m='772200'>two</span> <span m='772380'>delays</span> <span
  m='772890'>is</span> <span m='773010'>the</span> <span m='773100'>same,</span>
  <span m='774090'>but</span> <span m='774270'>clearly</span> <span
  m='774960'>in</span> <span m='775080'>terms</span> <span m='775410'>of</span>
  <span m='775500'>implementation</span> <span m='776550'>of</span> <span
  m='776700'>a</span> <span m='776760'>digital</span> <span
  m='777150'>filter</span> <span m='777960'>either</span> <span
  m='778230'>in</span> <span m='778350'>terms</span> <span m='778650'>of</span>
  <span m='778770'>a</span> <span m='778830'>program</span> <span
  m='779940'>or</span> <span m='780210'>in</span> <span m='780330'>terms</span>
  <span m='780630'>of</span> <span m='780690'>special</span> <span
  m='781080'>purpose</span> <span m='781470'>hardware,</span> <span
  m='782670'>obviously</span> <span m='783840'>clearly</span> <span
  m='784530'>there's</span> <span m='784770'>an</span> <span
  m='784890'>advantage</span> <span m='786540'>to</span> <span
  m='787470'>reducing</span> <span m='788400'>the</span> <span
  m='788520'>number</span> <span m='789060'>of</span> <span
  m='789270'>delay</span> <span m='789630'>registers</span> <span
  m='790260'>that</span> <span m='790380'>are</span> <span
  m='790440'>required,</span> <span m='791580'>because</span> <span
  m='791970'>you</span> <span m='792090'>see</span> <span m='792960'>each</span>
  <span m='793450'>z</span> <span m='793680'>to</span> <span
  m='793780'>the</span> <span m='793890'>minus</span> <span m='794310'>1
  that</span> <span m='795150'>appears</span> <span m='795600'>in</span> <span
  m='795660'>the</span> <span m='795750'>structure</span> <span
  m='797710'>requires</span> <span m='798490'>in</span> <span
  m='798610'>the</span> <span m='798730'>implementation</span> <span
  m='799900'>a</span> <span m='800380'>register</span> <span
  m='801850'>to</span> <span m='801970'>store</span> <span m='802870'>the</span>
  <span m='803020'>value--</span> <span m='803590'>in</span> <span
  m='803710'>other</span> <span m='803890'>words,</span> <span
  m='804160'>to</span> <span m='804280'>hold</span> <span m='804640'>it</span>
  <span m='804790'>for</span> <span m='804940'>the</span> <span
  m='805030'>next</span> <span m='805300'>iteration.</span> </p><p><span
  m='807080'>So</span> <span m='807640'>in</span> <span m='808390'>this</span>
  <span m='808600'>structure,</span> <span m='809410'>as</span> <span
  m='809650'>it's</span> <span m='809770'>implemented</span> <span
  m='810340'>here,</span> <span m='811240'>we</span> <span
  m='811420'>have</span> <span m='811960'>n</span> <span m='813580'>delay</span>
  <span m='813820'>registers,</span> <span m='814900'>where</span> <span
  m='815110'>again</span> <span m='815410'>I'm</span> <span
  m='815500'>assuming</span> <span m='815950'>that</span> <span
  m='816040'>capital</span> <span m='816510'>M</span> <span
  m='816700'>was</span> <span m='816880'>equal</span> <span m='817120'>to</span>
  <span m='817240'>capital</span> <span m='817720'>N.</span> <span
  m='818680'>There</span> <span m='819070'>are</span> <span m='820120'>N</span>
  <span m='820690'>delay</span> <span m='820990'>registers,</span> <span
  m='822040'>whereas</span> <span m='822610'>in</span> <span
  m='822730'>the</span> <span m='822820'>first</span> <span
  m='823120'>network</span> <span m='823570'>that</span> <span
  m='823690'>we</span> <span m='823810'>generated--</span> <span
  m='825310'>the</span> <span m='825400'>network</span> <span
  m='825730'>corresponding</span> <span m='826420'>to</span> <span
  m='826570'>the</span> <span m='826660'>0's</span> <span
  m='827110'>first</span> <span m='827440'>and</span> <span
  m='827530'>then</span> <span m='827710'>the</span> <span
  m='827770'>poles--</span> <span m='829030'>the</span> <span
  m='829600'>there</span> <span m='829930'>were</span> <span
  m='830230'>two</span> <span m='830530'>M</span> <span m='831130'>delay</span>
  <span m='831400'>registers.</span> </p><p><span m='835830'>In</span> <span
  m='835970'>general,</span> <span m='836790'>a</span> <span
  m='837180'>digital</span> <span m='837570'>filter</span> <span
  m='837930'>structure</span> <span m='839100'>that</span> <span
  m='839670'>has</span> <span m='840390'>the</span> <span
  m='840510'>minimum</span> <span m='840870'>number</span> <span
  m='841230'>of</span> <span m='841320'>delay</span> <span
  m='841620'>registers--</span> <span m='842310'>and</span> <span
  m='842400'>you</span> <span m='842520'>can</span> <span m='842640'>show</span>
  <span m='842910'>that</span> <span m='843060'>the</span> <span
  m='843150'>minimum</span> <span m='843420'>number</span> <span
  m='843780'>required</span> <span m='844530'>is</span> <span
  m='845330'>the</span> <span m='845430'>greater</span> <span
  m='845940'>of</span> <span m='846120'>M</span> <span m='846420'>or</span>
  <span m='846610'>N,</span> <span m='847050'>or</span> <span
  m='847560'>since</span> <span m='847800'>we're</span> <span
  m='847950'>considering</span> <span m='848490'>M</span> <span
  m='848670'>equal</span> <span m='848970'>to</span> <span m='849120'>N,</span>
  <span m='850080'>the</span> <span m='850350'>minimum</span> <span
  m='850710'>number</span> <span m='851160'>is</span> <span m='851370'>N.</span>
  <span m='853050'>The</span> <span m='853110'>structure</span> <span
  m='854010'>that</span> <span m='854700'>has</span> <span
  m='855000'>only</span> <span m='855330'>that</span> <span
  m='855510'>minimum</span> <span m='855840'>number</span> <span
  m='856350'>and</span> <span m='856470'>no</span> <span m='856680'>more</span>
  <span m='857600'>is</span> <span m='857730'>generally</span> <span
  m='858300'>referred</span> <span m='858720'>to</span> <span
  m='859140'>as</span> <span m='859350'>a</span> <span m='859410'>canonic</span>
  <span m='859860'>structure.</span> <span m='861220'>So</span> <span
  m='861720'>the</span> <span m='861840'>structure</span> <span
  m='862620'>that</span> <span m='863160'>I've</span> <span
  m='863370'>indicated</span> <span m='863940'>here</span> <span
  m='864610'>is</span> <span m='864960'>a</span> <span m='865050'>canonic</span>
  <span m='865500'>structure.</span> <span m='866490'>It</span> <span
  m='866580'>has</span> <span m='867180'>the</span> <span
  m='867300'>minimum</span> <span m='867660'>number</span> <span
  m='868230'>of</span> <span m='868410'>delays,</span> <span
  m='870960'>but</span> <span m='871260'>in</span> <span m='871410'>fact,</span>
  <span m='871800'>it's</span> <span m='871860'>not</span> <span
  m='872070'>the</span> <span m='872190'>only</span> <span
  m='872460'>canonic</span> <span m='872910'>structure.</span> <span
  m='873720'>There</span> <span m='874140'>are</span> <span m='874710'>a</span>
  <span m='874800'>large</span> <span m='875130'>variety</span> <span
  m='875850'>of</span> <span m='875970'>canonic</span> <span
  m='876450'>structures,</span> <span m='877890'>and</span> <span
  m='878010'>in</span> <span m='878130'>fact,</span> <span
  m='878760'>there's</span> <span m='878970'>a</span> <span
  m='879030'>canonic</span> <span m='879510'>structure</span> <span
  m='880740'>that</span> <span m='881640'>is</span> <span
  m='881910'>similar</span> <span m='882420'>to</span> <span
  m='882570'>the</span> <span m='882660'>first</span> <span
  m='882990'>structure</span> <span m='883620'>that</span> <span
  m='883800'>we</span> <span m='883950'>derived</span> <span
  m='884670'>in</span> <span m='884790'>the</span> <span m='884880'>sense</span>
  <span m='885450'>that</span> <span m='886140'>it</span> <span
  m='886470'>also</span> <span m='887010'>has--</span> <span
  m='888150'>is</span> <span m='888300'>implemented</span> <span
  m='889080'>with</span> <span m='889260'>the</span> <span m='889380'>0's</span>
  <span m='890100'>first,</span> <span m='891130'>followed</span> <span
  m='891390'>by</span> <span m='891570'>the</span> <span
  m='891660'>poles.</span> </p><p><span m='892950'>Let</span> <span
  m='893130'>me</span> <span m='893250'>remind</span> <span
  m='893640'>you</span> <span m='893760'>again</span> <span
  m='894120'>that</span> <span m='894270'>this</span> <span
  m='894450'>system</span> <span m='895080'>as</span> <span
  m='895290'>it's</span> <span m='895440'>implemented</span> <span
  m='896490'>is</span> <span m='896640'>basically</span> <span
  m='897180'>a</span> <span m='897240'>cascade</span> <span m='898140'>of</span>
  <span m='898360'>the</span> <span m='898420'>system</span> <span
  m='898860'>poles.</span> <span m='900120'>Those</span> <span
  m='900390'>are</span> <span m='900450'>the</span> <span
  m='901110'>a's--</span> <span m='903600'>or</span> <span m='903990'>the</span>
  <span m='904110'>polynomial</span> <span m='904860'>that</span> <span
  m='905340'>this</span> <span m='905550'>implements</span> <span
  m='906270'>corresponds</span> <span m='906960'>to</span> <span
  m='907050'>the</span> <span m='907140'>poles--</span> <span
  m='908100'>followed</span> <span m='908520'>by</span> <span
  m='909030'>an</span> <span m='909180'>implementation</span> <span
  m='909930'>of</span> <span m='910020'>the</span> <span m='910110'>0's,</span>
  <span m='911130'>and</span> <span m='911370'>it's</span> <span
  m='911520'>the</span> <span m='911640'>b's</span> <span m='912000'>that</span>
  <span m='912390'>control</span> <span m='912780'>the</span> <span
  m='912870'>0's.</span> <span m='914490'>Well,</span> <span
  m='914730'>to</span> <span m='914880'>generate</span> <span
  m='915300'>another</span> <span m='915630'>canonic</span> <span
  m='916080'>structure</span> <span m='917700'>we</span> <span
  m='917910'>can</span> <span m='918330'>take</span> <span
  m='918630'>advantage</span> <span m='919530'>of</span> <span
  m='920250'>a</span> <span m='920310'>theorem</span> <span
  m='921540'>that,</span> <span m='922530'>in</span> <span
  m='922620'>fact,</span> <span m='923010'>is</span> <span m='923130'>a</span>
  <span m='923190'>very</span> <span m='923430'>powerful</span> <span
  m='924000'>theorem</span> <span m='924600'>in</span> <span
  m='924750'>dealing</span> <span m='925290'>with</span> <span
  m='925470'>filter</span> <span m='925830'>structures--</span> <span
  m='926860'>the</span> <span m='927000'>theorem,</span> <span
  m='927700'>which</span> <span m='927900'>is</span> <span
  m='928140'>referred</span> <span m='928560'>to</span> <span
  m='928980'>as</span> <span m='930090'>the</span> <span
  m='930330'>transposition</span> <span m='931200'>theorem.</span> </p><p><span
  m='932400'>What</span> <span m='932970'>the</span> <span
  m='933090'>transposition</span> <span m='933870'>theorem</span> <span
  m='934230'>says</span> <span m='935730'>is</span> <span
  m='935970'>that,</span> <span m='937410'>if</span> <span m='938070'>we</span>
  <span m='938220'>have</span> <span m='938490'>a</span> <span
  m='938550'>network</span> <span m='940620'>that</span> <span
  m='940920'>implements</span> <span m='941970'>a</span> <span
  m='942030'>transfer</span> <span m='942570'>function,</span> <span
  m='944520'>and</span> <span m='944600'>if</span> <span m='945020'>we</span>
  <span m='945530'>simply</span> <span m='946040'>reverse</span> <span
  m='946850'>the</span> <span m='946940'>direction</span> <span
  m='947780'>of</span> <span m='947960'>all</span> <span m='948140'>of</span>
  <span m='948230'>the</span> <span m='948350'>branches</span> <span
  m='949340'>in</span> <span m='949460'>the</span> <span
  m='949550'>network</span> <span m='951860'>and</span> <span
  m='952460'>we</span> <span m='952670'>interchange</span> <span
  m='953690'>the</span> <span m='953870'>input</span> <span
  m='954350'>and</span> <span m='954530'>the</span> <span
  m='954650'>output,</span> <span m='956890'>then</span> <span
  m='957420'>the</span> <span m='957540'>transfer</span> <span
  m='958080'>function</span> <span m='958830'>that</span> <span
  m='959010'>results</span> <span m='959700'>is</span> <span
  m='959850'>exactly</span> <span m='960330'>the</span> <span
  m='960450'>same.</span> <span m='962660'>So</span> <span m='962770'>it</span>
  <span m='962860'>says</span> <span m='963790'>take</span> <span
  m='964060'>the</span> <span m='964120'>network,</span> <span
  m='965290'>reverse</span> <span m='965710'>the</span> <span
  m='965800'>direction</span> <span m='966280'>of</span> <span
  m='966340'>the</span> <span m='966460'>branches,</span> <span
  m='967960'>put</span> <span m='968140'>the</span> <span
  m='968290'>input</span> <span m='968650'>where</span> <span
  m='968800'>the</span> <span m='968950'>output</span> <span
  m='969370'>was,</span> <span m='969640'>take</span> <span
  m='969880'>the</span> <span m='970000'>output</span> <span
  m='970540'>where</span> <span m='970720'>the</span> <span
  m='970840'>input</span> <span m='971500'>was,</span> <span
  m='972640'>and</span> <span m='973390'>what</span> <span m='973750'>you</span>
  <span m='973900'>find</span> <span m='974500'>is</span> <span
  m='974710'>that</span> <span m='974860'>the</span> <span
  m='974950'>transfer</span> <span m='975430'>function</span> <span
  m='975850'>of</span> <span m='975910'>the</span> <span
  m='976030'>system</span> <span m='976930'>is</span> <span
  m='977080'>exactly</span> <span m='977560'>the</span> <span
  m='977680'>same.</span> </p><p><span m='979380'>Well,</span> <span
  m='979830'>let</span> <span m='980010'>me</span> <span
  m='980160'>illustrate</span> <span m='981030'>this</span> <span
  m='981240'>theorem.</span> <span m='981750'>We</span> <span
  m='981930'>won't</span> <span m='982230'>incidentally</span> <span
  m='983190'>prove</span> <span m='983490'>the</span> <span
  m='983610'>theorem,</span> <span m='984180'>although</span> <span
  m='985220'>in</span> <span m='985320'>the</span> <span m='985440'>notes</span>
  <span m='986280'>in</span> <span m='986640'>the</span> <span
  m='986700'>text</span> <span m='987330'>at</span> <span m='987540'>the</span>
  <span m='987660'>end</span> <span m='987810'>of</span> <span
  m='987870'>the</span> <span m='987960'>chapter</span> <span
  m='989100'>there,</span> <span m='989520'>in</span> <span
  m='989640'>fact,</span> <span m='989940'>is</span> <span m='990060'>a</span>
  <span m='990120'>proof</span> <span m='990570'>of</span> <span
  m='990660'>the</span> <span m='990750'>transposition</span> <span
  m='991530'>theorem,</span> <span m='993510'>but</span> <span
  m='993960'>let</span> <span m='994170'>me</span> <span
  m='994320'>illustrate</span> <span m='994800'>the</span> <span
  m='994890'>transposition</span> <span m='995640'>theorem--</span> <span
  m='996400'>first</span> <span m='996600'>with</span> <span m='996750'>a</span>
  <span m='996810'>simple</span> <span m='997200'>example</span> <span
  m='998400'>that</span> <span m='998550'>makes</span> <span
  m='998850'>it</span> <span m='999060'>appear</span> <span m='999390'>to</span>
  <span m='999480'>be</span> <span m='999630'>a</span> <span
  m='999690'>trivial</span> <span m='1000350'>theorem,</span> <span
  m='1001220'>and</span> <span m='1001340'>then</span> <span
  m='1001850'>with</span> <span m='1002060'>another</span> <span
  m='1002390'>example</span> <span m='1003020'>that</span> <span
  m='1004550'>suggests</span> <span m='1005060'>that</span> <span
  m='1005180'>perhaps</span> <span m='1005630'>the</span> <span
  m='1005720'>theorem</span> <span m='1006050'>is</span> <span
  m='1006170'>less</span> <span m='1006410'>obvious</span> <span
  m='1007340'>than</span> <span m='1007490'>it</span> <span
  m='1007580'>would</span> <span m='1007910'>at</span> <span
  m='1008000'>first</span> <span m='1008360'>appear.</span> </p><p><span
  m='1010320'>Well,</span> <span m='1010590'>to</span> <span
  m='1010680'>illustrate</span> <span m='1011190'>the</span> <span
  m='1011280'>transposition</span> <span m='1012060'>theorem,</span> <span
  m='1012900'>let's</span> <span m='1013650'>begin</span> <span
  m='1014010'>with</span> <span m='1014160'>a</span> <span
  m='1014220'>simple</span> <span m='1014610'>network--</span> <span
  m='1015810'>just</span> <span m='1016080'>a</span> <span
  m='1016140'>simple</span> <span m='1017070'>first</span> <span
  m='1017430'>order</span> <span m='1017700'>network,</span> <span
  m='1018670'>two</span> <span m='1018900'>coefficient</span> <span
  m='1019560'>branches</span> <span m='1020520'>and</span> <span
  m='1020640'>a</span> <span m='1020700'>delay</span> <span
  m='1021060'>branch.</span> <span m='1023160'>The</span> <span
  m='1023280'>transposition</span> <span m='1024420'>theorem</span> <span
  m='1025109'>says</span> <span m='1027329'>that</span> <span
  m='1027839'>we</span> <span m='1028020'>want</span> <span
  m='1028290'>first</span> <span m='1028650'>of</span> <span
  m='1028770'>all</span> <span m='1029310'>to</span> <span
  m='1029460'>reverse</span> <span m='1029940'>the</span> <span
  m='1030030'>direction</span> <span m='1030960'>of</span> <span m='1032568'>all
  of</span> <span m='1032970'>the</span> <span m='1033060'>branches.</span>
  <span m='1034990'>So</span> <span m='1035099'>this</span> <span
  m='1035310'>branch</span> <span m='1035640'>gets</span> <span
  m='1035849'>turned</span> <span m='1036150'>around,</span> <span
  m='1036900'>again,</span> <span m='1037200'>with</span> <span
  m='1037319'>a</span> <span m='1037380'>gain</span> <span m='1037650'>of</span>
  <span m='1037740'>unity.</span> <span m='1039300'>This</span> <span
  m='1039480'>branch</span> <span m='1039839'>gets</span> <span
  m='1040170'>turned</span> <span m='1040470'>around</span> <span
  m='1040800'>with</span> <span m='1040890'>a</span> <span
  m='1040950'>gain</span> <span m='1041220'>of</span> <span
  m='1041280'>c.</span> <span m='1042390'>This</span> <span
  m='1042599'>branch</span> <span m='1042960'>gets</span> <span
  m='1043170'>turned</span> <span m='1043470'>around</span> <span
  m='1044190'>with</span> <span m='1044339'>a</span> <span
  m='1044369'>gain</span> <span m='1044670'>of</span> <span
  m='1044859'>a.</span> <span m='1045595'>The</span> <span
  m='1045900'>delay</span> <span m='1046319'>branch</span> <span
  m='1047060'>is</span> <span m='1047250'>turned</span> <span
  m='1047550'>around.</span> <span m='1049140'>This</span> <span
  m='1049680'>branch,</span> <span m='1050310'>which</span> <span
  m='1050490'>has</span> <span m='1050670'>a</span> <span
  m='1050730'>gain</span> <span m='1051000'>of</span> <span
  m='1051120'>unity,</span> <span m='1051960'>is</span> <span
  m='1052140'>turned</span> <span m='1052440'>around.</span> <span
  m='1053970'>Put</span> <span m='1054180'>the</span> <span
  m='1054360'>input</span> <span m='1054750'>where</span> <span
  m='1054900'>the</span> <span m='1055080'>output</span> <span
  m='1055500'>was,</span> <span m='1057000'>and</span> <span
  m='1057120'>take</span> <span m='1057690'>the</span> <span
  m='1057870'>output</span> <span m='1058620'>from</span> <span
  m='1058830'>where</span> <span m='1058980'>the</span> <span
  m='1059130'>input</span> <span m='1059520'>was.</span> </p><p><span
  m='1061310'>So</span> <span m='1062540'>the</span> <span
  m='1062780'>transpose</span> <span m='1063950'>of</span> <span
  m='1064160'>this</span> <span m='1064430'>network</span> <span
  m='1065450'>is</span> <span m='1066050'>the</span> <span
  m='1066170'>network</span> <span m='1066950'>that</span> <span
  m='1067370'>I've</span> <span m='1067550'>indicated</span> <span
  m='1068150'>here,</span> <span m='1070610'>and</span> <span
  m='1071140'>now</span> <span m='1071500'>of</span> <span
  m='1071590'>course</span> <span m='1071860'>we</span> <span
  m='1071980'>can</span> <span m='1072160'>redraw</span> <span
  m='1072640'>this</span> <span m='1072940'>network</span> <span
  m='1073900'>by</span> <span m='1074770'>putting</span> <span
  m='1075070'>the</span> <span m='1075190'>input</span> <span
  m='1076600'>on</span> <span m='1076750'>the</span> <span
  m='1076810'>left</span> <span m='1077110'>hand</span> <span
  m='1077380'>side</span> <span m='1078550'>and</span> <span
  m='1078670'>taking</span> <span m='1079060'>the</span> <span
  m='1079180'>output</span> <span m='1079900'>on</span> <span
  m='1080050'>the</span> <span m='1080140'>right</span> <span
  m='1080350'>hand</span> <span m='1080620'>side.</span> <span
  m='1080980'>That</span> <span m='1081160'>is</span> <span
  m='1081640'>taking</span> <span m='1082030'>the</span> <span
  m='1082120'>same</span> <span m='1082420'>network</span> <span
  m='1082840'>and</span> <span m='1082930'>just</span> <span
  m='1083110'>flipping</span> <span m='1083530'>it</span> <span
  m='1083620'>over--</span> <span m='1084010'>flipping</span> <span
  m='1084370'>it</span> <span m='1084430'>over</span> <span
  m='1084730'>because</span> <span m='1085660'>we</span> <span
  m='1085780'>tend</span> <span m='1086020'>to</span> <span
  m='1086140'>have</span> <span m='1086350'>a</span> <span
  m='1086410'>convention</span> <span m='1086980'>that</span> <span
  m='1087100'>the</span> <span m='1087250'>input</span> <span
  m='1087550'>is</span> <span m='1087670'>coming</span> <span
  m='1088000'>in</span> <span m='1088120'>from</span> <span
  m='1088300'>the</span> <span m='1088390'>left</span> <span
  m='1089110'>and</span> <span m='1089230'>the</span> <span
  m='1089320'>output</span> <span m='1089860'>is</span> <span
  m='1089980'>going</span> <span m='1090310'>out</span> <span
  m='1090490'>at</span> <span m='1090580'>the</span> <span
  m='1090700'>right.</span> <span m='1092320'>If</span> <span
  m='1092440'>we</span> <span m='1092560'>do</span> <span
  m='1092800'>that,</span> <span m='1093520'>just</span> <span
  m='1093730'>taking</span> <span m='1094090'>this</span> <span
  m='1094300'>network</span> <span m='1094990'>and</span> <span
  m='1095230'>simply</span> <span m='1095590'>flipping</span> <span
  m='1096130'>it</span> <span m='1096220'>over,</span> <span
  m='1097270'>we</span> <span m='1097420'>have</span> <span m='1097840'>x</span>
  <span m='1098200'>of n</span> <span m='1098410'>coming</span> <span
  m='1098770'>in</span> <span m='1099880'>through</span> <span
  m='1100140'>a</span> <span m='1100300'>unity</span> <span
  m='1100690'>gain.</span> <span m='1101860'>This</span> <span
  m='1102070'>delay</span> <span m='1102490'>has</span> <span
  m='1102610'>now</span> <span m='1102880'>ended</span> <span
  m='1103150'>up</span> <span m='1103510'>on</span> <span m='1103720'>the</span>
  <span m='1103810'>left</span> <span m='1104080'>hand</span> <span
  m='1104320'>side,</span> <span m='1105380'>and</span> <span
  m='1105640'>you</span> <span m='1105790'>can</span> <span
  m='1105940'>verify</span> <span m='1106810'>in</span> <span
  m='1106900'>a</span> <span m='1106960'>straightforward</span> <span
  m='1107620'>way</span> <span m='1107890'>that</span> <span
  m='1108040'>these</span> <span m='1108220'>branches</span> <span
  m='1108910'>are</span> <span m='1109060'>now</span> <span
  m='1109390'>correct</span> <span m='1109900'>if</span> <span
  m='1110020'>we</span> <span m='1110110'>just</span> <span
  m='1110290'>take</span> <span m='1110500'>this</span> <span
  m='1110680'>network</span> <span m='1111070'>and</span> <span
  m='1111160'>flip</span> <span m='1111430'>it</span> <span
  m='1111520'>over.</span> <span m='1112810'>And</span> <span
  m='1113800'>is</span> <span m='1113980'>it</span> <span
  m='1114100'>true</span> <span m='1114970'>that</span> <span
  m='1115210'>the</span> <span m='1115330'>transfer</span> <span
  m='1115810'>function</span> <span m='1116200'>of</span> <span
  m='1116320'>this</span> <span m='1116550'>network</span> <span
  m='1117670'>is</span> <span m='1117910'>identical</span> <span
  m='1118480'>to</span> <span m='1118600'>the</span> <span
  m='1118720'>transfer</span> <span m='1119140'>function</span> <span
  m='1119530'>of</span> <span m='1119620'>this</span> <span
  m='1119830'>network?</span> <span m='1122160'>Well,</span> <span
  m='1122550'>you</span> <span m='1122640'>should</span> <span
  m='1122880'>be</span> <span m='1123030'>able</span> <span
  m='1123300'>to</span> <span m='1123420'>see</span> <span m='1123750'>by</span>
  <span m='1123960'>inspection</span> <span m='1124530'>that</span> <span
  m='1124680'>in</span> <span m='1124800'>fact</span> <span
  m='1125120'>it</span> <span m='1125220'>is</span> <span
  m='1125400'>true.</span> </p><p><span m='1126400'>In</span> <span
  m='1126500'>fact,</span> <span m='1126850'>if</span> <span
  m='1126900'>you</span> <span m='1126990'>compare</span> <span
  m='1127470'>this</span> <span m='1127710'>network</span> <span
  m='1128130'>to</span> <span m='1128280'>this</span> <span
  m='1128520'>one,</span> <span m='1129360'>what's</span> <span
  m='1129600'>the</span> <span m='1129720'>only</span> <span
  m='1129930'>difference?</span> <span m='1130750'>The</span> <span
  m='1130850'>only</span> <span m='1130980'>difference</span> <span
  m='1131360'>is</span> <span m='1131610'>that</span> <span
  m='1131790'>this</span> <span m='1132030'>delay,</span> <span
  m='1133110'>instead</span> <span m='1133440'>of</span> <span
  m='1133530'>being</span> <span m='1133860'>here,</span> <span
  m='1134850'>ended</span> <span m='1135180'>up</span> <span
  m='1135480'>on</span> <span m='1135660'>the</span> <span
  m='1135780'>other</span> <span m='1135960'>side</span> <span
  m='1136470'>of</span> <span m='1136590'>the</span> <span
  m='1136680'>coefficient</span> <span m='1137640'>multiplier.</span> <span
  m='1138810'>And</span> <span m='1138930'>obviously</span> <span
  m='1140310'>since</span> <span m='1140970'>these</span> <span
  m='1141270'>two</span> <span m='1141480'>in</span> <span
  m='1141570'>cascade</span> <span m='1142320'>implement</span> <span
  m='1142890'>a</span> <span m='1143100'>times</span> <span m='1143430'>z</span>
  <span m='1143640'>to</span> <span m='1143790'>the</span> <span
  m='1143880'>minus</span> <span m='1144270'>1,</span> <span
  m='1144610'>it</span> <span m='1145290'>doesn't</span> <span
  m='1145590'>matter</span> <span m='1146160'>whether</span> <span
  m='1146460'>I</span> <span m='1146550'>do</span> <span m='1146730'>the</span>
  <span m='1147060'>multiplication</span> <span m='1147900'>by</span> <span
  m='1148080'>a</span> <span m='1148290'>first</span> <span
  m='1148770'>and</span> <span m='1148920'>then</span> <span
  m='1149190'>delay</span> <span m='1149820'>or</span> <span
  m='1149940'>the</span> <span m='1150060'>reverse.</span> <span
  m='1151170'>So</span> <span m='1151710'>applying</span> <span
  m='1152280'>the</span> <span m='1152460'>transposition</span> <span
  m='1154410'>theorem</span> <span m='1155790'>to</span> <span
  m='1155910'>this</span> <span m='1156150'>simple</span> <span
  m='1156540'>example,</span> <span m='1158320'>we</span> <span
  m='1158370'>see</span> <span m='1158670'>that</span> <span
  m='1158820'>obviously</span> <span m='1159750'>for</span> <span
  m='1159900'>this</span> <span m='1160110'>example</span> <span
  m='1160950'>the</span> <span m='1161070'>transposition</span> <span
  m='1161790'>theorem</span> <span m='1162180'>works.</span> </p><p><span
  m='1163320'>Well,</span> <span m='1164010'>let's</span> <span
  m='1164250'>try</span> <span m='1164580'>it</span> <span m='1164850'>on</span>
  <span m='1165480'>a</span> <span m='1166050'>slightly</span> <span
  m='1166920'>more</span> <span m='1167130'>complicated</span> <span
  m='1168120'>example</span> <span m='1170730'>not</span> <span
  m='1171060'>to</span> <span m='1171240'>verify</span> <span
  m='1171810'>that</span> <span m='1171960'>it</span> <span
  m='1172080'>works,</span> <span m='1172500'>but</span> <span
  m='1172680'>just</span> <span m='1173100'>again</span> <span
  m='1173550'>to</span> <span m='1173670'>emphasize</span> <span
  m='1174960'>how</span> <span m='1175200'>the</span> <span
  m='1175320'>transposition</span> <span m='1176790'>is</span> <span
  m='1176970'>implemented.</span> <span m='1178380'>Here</span> <span
  m='1178620'>I</span> <span m='1178710'>have</span> <span m='1178890'>an</span>
  <span m='1178980'>example</span> <span m='1180060'>in</span> <span
  m='1180210'>which</span> <span m='1180990'>I</span> <span
  m='1181170'>have</span> <span m='1181950'>a</span> <span
  m='1182490'>canonic</span> <span m='1184600'>first</span> <span
  m='1184990'>order</span> <span m='1185260'>system.</span> <span
  m='1186310'>This</span> <span m='1186520'>implements</span> <span
  m='1187300'>one</span> <span m='1187610'>0</span> <span m='1188680'>and</span>
  <span m='1188830'>one</span> <span m='1189060'>pole.</span> <span
  m='1190200'>Here</span> <span m='1190420'>is</span> <span
  m='1190540'>the</span> <span m='1190630'>implementation</span> <span
  m='1191320'>of</span> <span m='1191380'>the</span> <span
  m='1191500'>pole</span> <span m='1192420'>and</span> <span
  m='1192520'>the</span> <span m='1192580'>implementation</span> <span
  m='1193300'>of</span> <span m='1193390'>the</span> <span m='1193480'>0.</span>
  <span m='1195220'>This,</span> <span m='1195430'>in</span> <span
  m='1195550'>fact,</span> <span m='1196030'>is</span> <span
  m='1196270'>the</span> <span m='1196360'>first</span> <span
  m='1196690'>order</span> <span m='1196960'>counterpart</span> <span
  m='1198250'>of</span> <span m='1198700'>the</span> <span
  m='1198820'>canonic</span> <span m='1199300'>structure</span> <span
  m='1200110'>that</span> <span m='1200440'>I</span> <span
  m='1200530'>showed</span> <span m='1200860'>several</span> <span
  m='1201490'>view</span> <span m='1201750'>graphs</span> <span
  m='1202150'>ago.</span> <span m='1203350'>And</span> <span
  m='1204220'>so</span> <span m='1204940'>it's</span> <span
  m='1205150'>one</span> <span m='1205420'>pole,</span> <span
  m='1206230'>and</span> <span m='1206350'>that's</span> <span
  m='1206560'>implemented</span> <span m='1207070'>through</span> <span
  m='1207250'>this</span> <span m='1207490'>loop,</span> <span
  m='1208300'>one</span> <span m='1208540'>0,</span> <span
  m='1209020'>and</span> <span m='1209110'>that's</span> <span
  m='1209350'>implemented</span> <span m='1209920'>through</span> <span
  m='1210100'>this</span> <span m='1210380'>loop.</span> <span
  m='1212130'>And</span> <span m='1212400'>these,</span> <span
  m='1212640'>of</span> <span m='1212730'>course,</span> <span
  m='1213030'>are</span> <span m='1213120'>unity</span> <span
  m='1213540'>gain</span> <span m='1214440'>since</span> <span
  m='1214980'>I</span> <span m='1215130'>put</span> <span m='1215430'>no</span>
  <span m='1215640'>amplitude</span> <span m='1216180'>on</span> <span
  m='1216390'>them.</span> </p><p><span m='1217210'>And</span> <span
  m='1217230'>now</span> <span m='1217440'>to</span> <span
  m='1217590'>apply</span> <span m='1217920'>the</span> <span
  m='1218040'>transposition</span> <span m='1218820'>theorem</span> <span
  m='1219600'>to</span> <span m='1219720'>this</span> <span
  m='1219930'>network,</span> <span m='1220980'>again,</span> <span
  m='1221670'>we</span> <span m='1221850'>interchange</span> <span
  m='1222930'>the--</span> <span m='1223410'>we</span> <span
  m='1224040'>reverse</span> <span m='1224420'>the</span> <span
  m='1224520'>direction</span> <span m='1225270'>of</span> <span
  m='1225420'>all</span> <span m='1225600'>of</span> <span
  m='1225690'>the</span> <span m='1225840'>arrows,</span> <span
  m='1227130'>and</span> <span m='1227280'>you</span> <span
  m='1227430'>can</span> <span m='1227580'>see</span> <span
  m='1227790'>that</span> <span m='1227910'>I've</span> <span
  m='1228060'>done</span> <span m='1228300'>that</span> <span
  m='1228660'>in</span> <span m='1228810'>all</span> <span m='1228990'>of</span>
  <span m='1229080'>these</span> <span m='1229260'>branches.</span> <span
  m='1231250'>The</span> <span m='1231370'>delay</span> <span
  m='1231820'>is</span> <span m='1231940'>likewise</span> <span
  m='1232540'>reversed.</span> <span m='1233590'>The</span> <span
  m='1233760'>a</span> <span m='1234065'>is</span> <span
  m='1234370'>reversed,</span> <span m='1235060'>and</span> <span
  m='1235180'>the</span> <span m='1235270'>b</span> <span m='1235690'>is</span>
  <span m='1235840'>reversed.</span> <span m='1238460'>I</span> <span
  m='1238630'>put</span> <span m='1238870'>the</span> <span
  m='1239020'>input</span> <span m='1239350'>in</span> <span
  m='1239470'>where</span> <span m='1239650'>the</span> <span
  m='1239800'>output</span> <span m='1240250'>was.</span> <span
  m='1241600'>I</span> <span m='1241720'>take</span> <span
  m='1241990'>the</span> <span m='1242140'>output</span> <span
  m='1242530'>out</span> <span m='1242860'>where</span> <span
  m='1243040'>the</span> <span m='1243190'>input</span> <span
  m='1243610'>was,</span> <span m='1245020'>and</span> <span
  m='1245770'>then</span> <span m='1246040'>the</span> <span
  m='1246130'>transposition</span> <span m='1246940'>theorem</span> <span
  m='1247420'>says</span> <span m='1248530'>that</span> <span
  m='1249160'>this</span> <span m='1249580'>first</span> <span
  m='1249970'>order</span> <span m='1250240'>system</span> <span
  m='1251260'>implements</span> <span m='1251890'>exactly</span> <span
  m='1252430'>the</span> <span m='1252550'>same</span> <span
  m='1252790'>transfer</span> <span m='1253240'>function</span> <span
  m='1253960'>as</span> <span m='1254530'>this</span> <span
  m='1254710'>first</span> <span m='1255040'>order</span> <span
  m='1255280'>system</span> <span m='1255730'>does.</span> </p><p><span
  m='1257530'>Well,</span> <span m='1257920'>again,</span> <span
  m='1258490'>we</span> <span m='1258640'>can</span> <span
  m='1258790'>redraw</span> <span m='1259270'>this</span> <span
  m='1259840'>by</span> <span m='1261430'>taking</span> <span
  m='1262030'>again</span> <span m='1262420'>the</span> <span
  m='1262540'>input</span> <span m='1263020'>at</span> <span
  m='1263140'>the</span> <span m='1263230'>left</span> <span
  m='1263530'>hand</span> <span m='1263770'>side,</span> <span
  m='1264370'>the</span> <span m='1264520'>output</span> <span
  m='1264880'>at</span> <span m='1264970'>the</span> <span
  m='1265060'>right</span> <span m='1265300'>hand</span> <span
  m='1265570'>side</span> <span m='1266590'>that</span> <span
  m='1266770'>corresponds</span> <span m='1267490'>to</span> <span
  m='1267640'>just</span> <span m='1267850'>taking</span> <span
  m='1268270'>this</span> <span m='1268570'>and</span> <span
  m='1268720'>flipping</span> <span m='1269080'>it</span> <span
  m='1269170'>over.</span> <span m='1270015'>In</span> <span
  m='1270350'>fact,</span> <span m='1270620'>I</span> <span
  m='1270730'>could</span> <span m='1270850'>do</span> <span
  m='1271060'>that</span> <span m='1271300'>by</span> <span
  m='1271450'>taking</span> <span m='1271780'>the</span> <span
  m='1271870'>view</span> <span m='1272050'>graph</span> <span
  m='1272380'>and</span> <span m='1272470'>just</span> <span
  m='1272680'>flipping</span> <span m='1273040'>it</span> <span
  m='1273100'>over,</span> <span m='1274360'>and</span> <span
  m='1275230'>the</span> <span m='1275350'>result</span> <span
  m='1275830'>then,</span> <span m='1276460'>just</span> <span
  m='1276700'>flipping</span> <span m='1277180'>this</span> <span
  m='1277390'>over,</span> <span m='1279130'>is</span> <span
  m='1279520'>the</span> <span m='1279670'>system</span> <span
  m='1280360'>that</span> <span m='1280690'>I've</span> <span
  m='1280870'>indicated</span> <span m='1281470'>here--</span> <span
  m='1282700'>x</span> <span m='1283140'>of</span> <span m='1283270'>n</span>
  <span m='1283490'>in</span> <span m='1283720'>at the</span> <span
  m='1283810'>left</span> <span m='1284080'>hand</span> <span
  m='1284320'>side,</span> <span m='1285040'>y</span> <span
  m='1285180'>of</span> <span m='1285280'>n</span> <span m='1285520'>out</span>
  <span m='1285700'>at</span> <span m='1285790'>the</span> <span
  m='1285910'>right</span> <span m='1286120'>hand</span> <span
  m='1286390'>side.</span> <span m='1287360'>And</span> <span
  m='1287380'>now</span> <span m='1287620'>in</span> <span
  m='1287710'>comparing</span> <span m='1288700'>these</span> <span
  m='1288970'>two</span> <span m='1289990'>there</span> <span
  m='1290260'>are</span> <span m='1290410'>some</span> <span
  m='1290590'>changes</span> <span m='1291040'>that</span> <span
  m='1291160'>took</span> <span m='1291400'>place.</span> <span
  m='1292510'>In</span> <span m='1292630'>particular,</span> <span
  m='1293470'>we</span> <span m='1293620'>notice</span> <span
  m='1294010'>that</span> <span m='1294160'>the</span> <span
  m='1294250'>direction</span> <span m='1295120'>of</span> <span
  m='1296020'>the</span> <span m='1296550'>delayed</span> <span
  m='1296830'>branch</span> <span m='1297520'>is</span> <span
  m='1297670'>reversed.</span> <span m='1300290'>Furthermore,</span> <span
  m='1301020'>whereas</span> <span m='1301440'>this</span> <span
  m='1301650'>system</span> <span m='1302280'>implemented</span> <span
  m='1303240'>the</span> <span m='1303360'>pole</span> <span
  m='1303810'>first</span> <span m='1304840'>followed</span> <span
  m='1305130'>by</span> <span m='1305310'>the</span> <span m='1305430'>0,</span>
  <span m='1306780'>this</span> <span m='1306960'>system</span> <span
  m='1307710'>implements</span> <span m='1308610'>the</span> <span
  m='1308730'>0</span> <span m='1309180'>first,</span> <span
  m='1310420'>followed</span> <span m='1310680'>by</span> <span
  m='1310890'>the</span> <span m='1310980'>pole.</span> </p><p><span
  m='1312540'>Is</span> <span m='1312690'>this</span> <span
  m='1312840'>still</span> <span m='1313110'>a</span> <span
  m='1313170'>canonic</span> <span m='1313620'>structure?</span> <span
  m='1314310'>Well,</span> <span m='1314670'>of</span> <span
  m='1314790'>course</span> <span m='1315090'>it's</span> <span
  m='1315210'>a</span> <span m='1315270'>canonic</span> <span
  m='1315720'>structure</span> <span m='1316200'>because</span> <span
  m='1317310'>it</span> <span m='1317400'>only</span> <span
  m='1317700'>has</span> <span m='1317910'>one</span> <span
  m='1318150'>delay,</span> <span m='1319320'>and</span> <span
  m='1319890'>obviously,</span> <span m='1320670'>in</span> <span
  m='1320760'>fact,</span> <span m='1321390'>transposing</span> <span
  m='1322170'>a</span> <span m='1322230'>network</span> <span
  m='1323100'>couldn't</span> <span m='1323400'>possibly</span> <span
  m='1324360'>affect</span> <span m='1325230'>the</span> <span
  m='1325320'>number</span> <span m='1325650'>of</span> <span
  m='1325740'>delays</span> <span m='1326190'>in</span> <span
  m='1326280'>the</span> <span m='1326370'>network</span> <span
  m='1327250'>so</span> <span m='1327360'>that,</span> <span
  m='1327690'>if</span> <span m='1327900'>we</span> <span
  m='1327990'>begin</span> <span m='1328320'>with</span> <span
  m='1328460'>a</span> <span m='1328530'>canonic</span> <span
  m='1328950'>structure</span> <span m='1329610'>and</span> <span
  m='1329730'>apply</span> <span m='1330060'>the</span> <span
  m='1330150'>transposition</span> <span m='1330900'>theorem</span> <span
  m='1331260'>to</span> <span m='1331500'>it,</span> <span m='1332010'>we</span>
  <span m='1332100'>must</span> <span m='1332460'>end</span> <span
  m='1332700'>up</span> <span m='1332850'>with</span> <span m='1332970'>a</span>
  <span m='1333030'>canonic</span> <span m='1333480'>structure</span> <span
  m='1334020'>also.</span> <span m='1335670'>Well,</span> <span
  m='1336330'>it</span> <span m='1336450'>shouldn't</span> <span
  m='1336750'>be</span> <span m='1336930'>obvious--</span> <span
  m='1337470'>or,</span> <span m='1337980'>at</span> <span
  m='1338040'>least</span> <span m='1338300'>it</span> <span
  m='1338400'>isn't</span> <span m='1338610'>obvious</span> <span
  m='1339030'>to</span> <span m='1339180'>me</span> <span m='1339630'>by</span>
  <span m='1339840'>inspection--</span> <span m='1341100'>that</span> <span
  m='1341670'>this</span> <span m='1341880'>system</span> <span
  m='1342570'>and</span> <span m='1342720'>this</span> <span
  m='1342870'>system</span> <span m='1343710'>have</span> <span
  m='1344490'>the</span> <span m='1344580'>same</span> <span
  m='1344910'>transfer</span> <span m='1345450'>function,</span> <span
  m='1346410'>but</span> <span m='1346590'>in</span> <span
  m='1346710'>fact</span> <span m='1347040'>you</span> <span
  m='1347160'>can</span> <span m='1347310'>verify</span> <span
  m='1347850'>that</span> <span m='1348570'>in</span> <span m='1348660'>a</span>
  <span m='1348720'>very</span> <span m='1349170'>simple</span> <span
  m='1349590'>and</span> <span m='1349680'>straightforward</span> <span
  m='1350430'>way</span> <span m='1351150'>by</span> <span
  m='1351330'>simply</span> <span m='1351900'>calculating</span> <span
  m='1352650'>what</span> <span m='1352800'>the</span> <span
  m='1352860'>transfer</span> <span m='1353310'>functions</span> <span
  m='1353940'>of</span> <span m='1354060'>these</span> <span
  m='1354270'>two</span> <span m='1354450'>systems</span> <span
  m='1354960'>are.</span> </p><p><span m='1356640'>Well,</span> <span
  m='1357030'>returning</span> <span m='1357630'>then</span> <span
  m='1358230'>to</span> <span m='1359250'>the</span> <span
  m='1360300'>general</span> <span m='1360930'>canonic</span> <span
  m='1361380'>structure</span> <span m='1363240'>that</span> <span
  m='1363390'>we</span> <span m='1363570'>had,</span> <span
  m='1365800'>we</span> <span m='1365950'>can</span> <span
  m='1366130'>generate</span> <span m='1367600'>a</span> <span
  m='1368170'>second</span> <span m='1369100'>canonic</span> <span
  m='1369610'>structure</span> <span m='1370840'>by</span> <span
  m='1371410'>applying</span> <span m='1371950'>the</span> <span
  m='1372070'>transposition</span> <span m='1372850'>theorem</span> <span
  m='1373930'>to</span> <span m='1375100'>this</span> <span
  m='1375310'>structure.</span> <span m='1376720'>That</span> <span
  m='1376960'>is</span> <span m='1377380'>reversing</span> <span
  m='1377920'>the</span> <span m='1378010'>directions</span> <span
  m='1378550'>of</span> <span m='1378670'>all</span> <span m='1378850'>of</span>
  <span m='1378940'>the</span> <span m='1379090'>arrows,</span> <span
  m='1380680'>putting</span> <span m='1380920'>the</span> <span
  m='1381040'>input</span> <span m='1381370'>in</span> <span
  m='1381550'>here,</span> <span m='1382180'>and</span> <span
  m='1382300'>taking</span> <span m='1382630'>the</span> <span
  m='1382750'>output</span> <span m='1383110'>out</span> <span
  m='1383350'>there,</span> <span m='1384310'>and</span> <span
  m='1384460'>then</span> <span m='1385330'>to</span> <span
  m='1385540'>keep</span> <span m='1385840'>our</span> <span
  m='1385990'>convention</span> <span m='1386470'>of</span> <span
  m='1386560'>the</span> <span m='1386680'>input</span> <span
  m='1387010'>in</span> <span m='1387220'>at the</span> <span
  m='1387340'>left,</span> <span m='1387610'>the</span> <span
  m='1387760'>output</span> <span m='1388060'>out</span> <span
  m='1388240'>at</span> <span m='1388330'>the</span> <span
  m='1388450'>right,</span> <span m='1389110'>flip</span> <span
  m='1389440'>that</span> <span m='1389680'>over</span> <span
  m='1390640'>to</span> <span m='1390820'>generate</span> <span
  m='1391600'>a</span> <span m='1391660'>second</span> <span
  m='1392530'>canonic</span> <span m='1393010'>structure,</span> <span
  m='1394030'>which</span> <span m='1394270'>is</span> <span
  m='1394420'>the</span> <span m='1394510'>transpose</span> <span
  m='1395410'>of</span> <span m='1395590'>this</span> <span
  m='1395770'>structure.</span> <span m='1396980'>And</span> <span
  m='1397240'>if</span> <span m='1397360'>we</span> <span m='1397480'>do</span>
  <span m='1397690'>that,</span> <span m='1399730'>the</span> <span
  m='1399950'>two</span> <span m='1400880'>changes</span> <span
  m='1401410'>to</span> <span m='1401530'>focus</span> <span
  m='1401980'>on</span> <span m='1402430'>is</span> <span
  m='1402580'>that</span> <span m='1402730'>the</span> <span
  m='1402850'>direction</span> <span m='1403330'>of</span> <span
  m='1403420'>the</span> <span m='1403510'>delayed</span> <span
  m='1403870'>branches</span> <span m='1404680'>is</span> <span
  m='1404830'>reversed,</span> <span m='1406060'>and</span> <span
  m='1406210'>furthermore,</span> <span m='1407110'>the</span> <span
  m='1407230'>system</span> <span m='1407650'>will</span> <span
  m='1407800'>implement</span> <span m='1408850'>the</span> <span
  m='1409300'>0's</span> <span m='1409840'>first,</span> <span
  m='1410780'>followed</span> <span m='1411070'>by</span> <span
  m='1411250'>the</span> <span m='1411340'>poles.</span> <span
  m='1412420'>In</span> <span m='1412540'>fact,</span> <span
  m='1413230'>the</span> <span m='1413710'>network</span> <span
  m='1414430'>that</span> <span m='1414550'>results</span> <span
  m='1416860'>is</span> <span m='1420440'>what</span> <span
  m='1420800'>I've</span> <span m='1421040'>indicated</span> <span
  m='1421610'>here.</span> <span m='1422390'>This</span> <span
  m='1422630'>is</span> <span m='1423140'>then</span> <span
  m='1423770'>the</span> <span m='1424040'>transposed</span> <span
  m='1424820'>version</span> <span m='1425570'>of</span> <span
  m='1426500'>the</span> <span m='1426740'>structure</span> <span
  m='1427790'>that</span> <span m='1429290'>I</span> <span
  m='1430040'>just</span> <span m='1430400'>showed</span> <span
  m='1430970'>on</span> <span m='1431540'>the</span> <span
  m='1431630'>last</span> <span m='1431930'>view</span> <span
  m='1432110'>graph.</span> <span m='1433070'>The</span> <span
  m='1433160'>0's</span> <span m='1433580'>are</span> <span
  m='1433700'>implemented</span> <span m='1434240'>here.</span> <span
  m='1435110'>The</span> <span m='1435200'>poles</span> <span
  m='1435560'>are</span> <span m='1435650'>implemented</span> <span
  m='1436190'>here,</span> <span m='1437040'>and</span> <span
  m='1437090'>the</span> <span m='1437180'>direction</span> <span
  m='1437810'>of</span> <span m='1437990'>the</span> <span
  m='1438230'>delayed</span> <span m='1438440'>branches</span> <span
  m='1439070'>is</span> <span m='1439280'>reversed,</span> <span
  m='1440090'>but</span> <span m='1440390'>again,</span> <span
  m='1440810'>this</span> <span m='1440990'>is</span> <span m='1441110'>a</span>
  <span m='1441170'>canonic</span> <span m='1441620'>form</span> <span
  m='1441950'>structure.</span> </p><p><span m='1444890'>So</span> <span
  m='1445610'>some</span> <span m='1445910'>structures</span> <span
  m='1446630'>are</span> <span m='1447260'>canonic</span> <span
  m='1448010'>form,</span> <span m='1448400'>and</span> <span
  m='1448490'>some</span> <span m='1448760'>aren't.</span> <span
  m='1449240'>The</span> <span m='1449330'>first</span> <span
  m='1449660'>one,</span> <span m='1449810'>in</span> <span
  m='1449900'>fact,</span> <span m='1450200'>that</span> <span
  m='1450350'>we</span> <span m='1450560'>developed</span> <span
  m='1451160'>wasn't</span> <span m='1451580'>canonic</span> <span
  m='1452090'>form</span> <span m='1452930'>in</span> <span
  m='1453020'>the</span> <span m='1453080'>sense</span> <span
  m='1453470'>that</span> <span m='1453590'>it</span> <span
  m='1453680'>had</span> <span m='1454040'>more</span> <span
  m='1454310'>delays</span> <span m='1454760'>than</span> <span
  m='1454910'>were</span> <span m='1455060'>absolutely</span> <span
  m='1455570'>necessary.</span> <span m='1457160'>The</span> <span
  m='1457460'>last</span> <span m='1457820'>two</span> <span
  m='1458000'>structures</span> <span m='1458570'>that</span> <span
  m='1458690'>we've</span> <span m='1458900'>shown</span> <span
  m='1459560'>are</span> <span m='1460010'>canonic</span> <span
  m='1460490'>form</span> <span m='1460820'>structures</span> <span
  m='1461600'>in</span> <span m='1461810'>that</span> <span
  m='1462110'>they</span> <span m='1462260'>have</span> <span
  m='1462500'>the</span> <span m='1462590'>minimum</span> <span
  m='1462920'>number</span> <span m='1463280'>of</span> <span
  m='1463370'>delays.</span> <span m='1464660'>All</span> <span
  m='1464960'>of</span> <span m='1465050'>these</span> <span
  m='1465200'>structures</span> <span m='1466370'>are</span> <span
  m='1467240'>referred</span> <span m='1467750'>to</span> <span
  m='1468470'>as</span> <span m='1469190'>direct</span> <span
  m='1469640'>form</span> <span m='1470180'>structures--</span> <span
  m='1471800'>direct</span> <span m='1472160'>form</span> <span
  m='1472640'>because</span> <span m='1473840'>they</span> <span
  m='1474500'>are</span> <span m='1475280'>structures</span> <span
  m='1476120'>that</span> <span m='1477860'>involve</span> <span
  m='1478700'>as</span> <span m='1478910'>coefficients</span> <span
  m='1479780'>in</span> <span m='1479950'>them</span> <span
  m='1480800'>the</span> <span m='1480920'>same</span> <span
  m='1481220'>coefficients</span> <span m='1482390'>that</span> <span
  m='1482960'>are</span> <span m='1483170'>present</span> <span
  m='1483860'>in</span> <span m='1484550'>the</span> <span
  m='1484880'>difference</span> <span m='1485300'>equation</span> <span
  m='1485840'>describing</span> <span m='1486410'>the</span> <span
  m='1486530'>overall</span> <span m='1486950'>system.</span> </p><p><span
  m='1488160'>Recall</span> <span m='1488540'>again</span> <span
  m='1489140'>that</span> <span m='1489800'>these</span> <span
  m='1490100'>were</span> <span m='1490490'>the</span> <span
  m='1490610'>coefficients</span> <span m='1491420'>in</span> <span
  m='1491540'>the</span> <span m='1491630'>difference</span> <span
  m='1491960'>equation</span> <span m='1493070'>which</span> <span
  m='1493310'>were</span> <span m='1493460'>applied</span> <span
  m='1493940'>to</span> <span m='1494660'>the</span> <span
  m='1494990'>delayed</span> <span m='1495380'>values</span> <span
  m='1495830'>of</span> <span m='1495920'>the</span> <span
  m='1496040'>input,</span> <span m='1497040'>and</span> <span
  m='1497060'>these</span> <span m='1497270'>were</span> <span
  m='1497360'>the</span> <span m='1497480'>coefficients</span> <span
  m='1498170'>in</span> <span m='1498260'>the</span> <span
  m='1498320'>difference</span> <span m='1498680'>equation</span> <span
  m='1499460'>that</span> <span m='1499610'>were</span> <span
  m='1500090'>applied</span> <span m='1500570'>to</span> <span
  m='1500740'>delayed</span> <span m='1501050'>values</span> <span
  m='1501470'>of</span> <span m='1501590'>the</span> <span
  m='1501740'>output.</span> <span m='1503090'>And</span> <span
  m='1503750'>this</span> <span m='1503960'>structure</span> <span
  m='1504960'>and</span> <span m='1505430'>the</span> <span
  m='1505580'>other</span> <span m='1506120'>structures</span> <span
  m='1506930'>involving</span> <span m='1507410'>the</span> <span
  m='1507500'>coefficients</span> <span m='1508220'>in</span> <span
  m='1508280'>that</span> <span m='1508490'>form</span> <span
  m='1509450'>are</span> <span m='1509840'>often</span> <span
  m='1510260'>referred</span> <span m='1510650'>to</span> <span
  m='1511100'>as</span> <span m='1512000'>direct</span> <span
  m='1512360'>form</span> <span m='1512690'>structures.</span> <span
  m='1515320'>Well,</span> <span m='1515830'>these</span> <span
  m='1515980'>structures</span> <span m='1516490'>are</span> <span
  m='1516580'>fine</span> <span m='1517210'>for</span> <span
  m='1517690'>implementing</span> <span m='1518650'>the</span> <span
  m='1518740'>difference</span> <span m='1519130'>equation,</span> <span
  m='1520120'>although</span> <span m='1520780'>there</span> <span
  m='1521140'>are</span> <span m='1521350'>other</span> <span
  m='1521560'>structures--</span> <span m='1523060'>actually</span> <span
  m='1523510'>there</span> <span m='1523910'>are</span> <span
  m='1524020'>essentially</span> <span m='1524470'>an</span> <span
  m='1524560'>infinite</span> <span m='1524890'>variety</span> <span
  m='1525430'>of</span> <span m='1525520'>structures,</span> <span
  m='1526750'>but</span> <span m='1527170'>there</span> <span
  m='1527350'>are</span> <span m='1527380'>some</span> <span
  m='1527620'>other</span> <span m='1527800'>structures</span> <span
  m='1528610'>that</span> <span m='1529000'>in</span> <span
  m='1529600'>some</span> <span m='1529870'>situations</span> <span
  m='1531430'>are</span> <span m='1533020'>better</span> <span
  m='1533320'>to</span> <span m='1533500'>use</span> <span
  m='1534280'>than</span> <span m='1534850'>the</span> <span
  m='1534970'>direct</span> <span m='1535330'>form</span> <span
  m='1535660'>structures,</span> <span m='1536860'>and</span> <span
  m='1536980'>two</span> <span m='1537220'>of</span> <span
  m='1537310'>the</span> <span m='1537430'>more</span> <span
  m='1537640'>common,</span> <span m='1538360'>which</span> <span
  m='1538750'>I'd</span> <span m='1538900'>like</span> <span
  m='1539140'>to</span> <span m='1539530'>introduce</span> <span
  m='1540070'>now,</span> <span m='1540940'>are</span> <span
  m='1541030'>the</span> <span m='1541120'>cascade</span> <span
  m='1541780'>structure</span> <span m='1542890'>and</span> <span
  m='1543580'>the</span> <span m='1543700'>parallel</span> <span
  m='1544150'>structure.</span> </p><p><span m='1547600'>The</span> <span
  m='1547690'>cascade</span> <span m='1548290'>structure</span> <span
  m='1549160'>is</span> <span m='1549850'>developed</span> <span
  m='1552340'>basically</span> <span m='1553360'>by</span> <span
  m='1553870'>factoring</span> <span m='1554890'>the</span> <span
  m='1555130'>transfer</span> <span m='1555670'>function</span> <span
  m='1556360'>of</span> <span m='1556510'>the</span> <span
  m='1556630'>system</span> <span m='1557800'>into</span> <span
  m='1558250'>a</span> <span m='1558310'>product</span> <span
  m='1558940'>of</span> <span m='1559090'>second</span> <span
  m='1559450'>order</span> <span m='1559720'>sections</span> <span
  m='1560350'>or</span> <span m='1560440'>second</span> <span
  m='1560800'>order</span> <span m='1561040'>factors.</span> <span
  m='1562150'>In</span> <span m='1562270'>particular,</span> <span
  m='1563230'>we</span> <span m='1563890'>have,</span> <span
  m='1564280'>again,</span> <span m='1564740'>the</span> <span
  m='1564840'>general</span> <span m='1565150'>form</span> <span
  m='1565750'>of</span> <span m='1565900'>the</span> <span
  m='1565990'>transfer</span> <span m='1566470'>function--</span> <span
  m='1567520'>H</span> <span m='1567790'>of</span> <span m='1567880'>z</span>
  <span m='1568360'>as</span> <span m='1569260'>the</span> <span
  m='1569320'>numerator</span> <span m='1569770'>polynomial</span> <span
  m='1570550'>for</span> <span m='1570670'>the</span> <span
  m='1570760'>0's,</span> <span m='1571680'>a</span> <span
  m='1571840'>denominator</span> <span m='1572470'>polynomial</span> <span
  m='1573400'>for</span> <span m='1573550'>the</span> <span
  m='1573770'>poles.</span> <span m='1575830'>We</span> <span
  m='1575880'>can</span> <span m='1576030'>factor</span> <span
  m='1576930'>the</span> <span m='1577020'>numerator</span> <span
  m='1577470'>polynomial</span> <span m='1578460'>into</span> <span
  m='1578700'>a</span> <span m='1578760'>product</span> <span
  m='1579420'>of</span> <span m='1579900'>first</span> <span
  m='1580260'>order</span> <span m='1580470'>polynomials</span> <span
  m='1581460'>and the</span> <span m='1581710'>denominator</span> <span
  m='1582330'>polynomial</span> <span m='1583650'>into</span> <span
  m='1583890'>a</span> <span m='1583950'>product</span> <span
  m='1584430'>of</span> <span m='1584550'>first</span> <span
  m='1584880'>order</span> <span m='1585090'>polynomials.</span> <span
  m='1586560'>In</span> <span m='1586680'>general,</span> <span
  m='1587340'>of</span> <span m='1587490'>course,</span> <span
  m='1587820'>these</span> <span m='1588060'>factors</span> <span
  m='1588810'>will</span> <span m='1588990'>be</span> <span
  m='1589140'>complex,</span> <span m='1590160'>and</span> <span
  m='1590280'>these</span> <span m='1590490'>factors</span> <span
  m='1590970'>will</span> <span m='1591120'>be</span> <span
  m='1591270'>complex.</span> </p><p><span m='1593250'>We</span> <span
  m='1593400'>can</span> <span m='1593790'>combine</span> <span
  m='1594270'>together</span> <span m='1594990'>the</span> <span
  m='1595200'>complex</span> <span m='1595820'>conjugate</span> <span
  m='1597080'>0</span> <span m='1597480'>pairs</span> <span
  m='1598020'>and</span> <span m='1598110'>the</span> <span
  m='1598170'>complex</span> <span m='1598680'>conjugate</span> <span
  m='1599190'>pole</span> <span m='1599550'>pairs</span> <span
  m='1600510'>so</span> <span m='1600690'>that</span> <span
  m='1601110'>in</span> <span m='1601230'>fact</span> <span
  m='1601590'>as</span> <span m='1601710'>a</span> <span
  m='1601770'>general</span> <span m='1603000'>cascade</span> <span
  m='1603600'>form</span> <span m='1604200'>it's</span> <span
  m='1604410'>often</span> <span m='1604770'>convenient</span> <span
  m='1606090'>to</span> <span m='1606210'>think</span> <span
  m='1606600'>of</span> <span m='1606780'>a</span> <span
  m='1606840'>factorization</span> <span m='1608130'>of</span> <span
  m='1608490'>each</span> <span m='1608700'>of</span> <span
  m='1608760'>these</span> <span m='1608970'>polynomials</span> <span
  m='1610320'>into</span> <span m='1610560'>second</span> <span
  m='1610920'>order</span> <span m='1611130'>polynomials</span> <span
  m='1612270'>rather</span> <span m='1612570'>than</span> <span
  m='1612720'>first</span> <span m='1613050'>order</span> <span
  m='1613260'>polynomials.</span> <span m='1615420'>Carrying</span> <span
  m='1615840'>that</span> <span m='1616050'>out,</span> <span
  m='1616800'>we</span> <span m='1616950'>end</span> <span m='1617190'>up</span>
  <span m='1617580'>with</span> <span m='1618060'>a</span> <span
  m='1618120'>representation</span> <span m='1619260'>of</span> <span
  m='1619440'>the</span> <span m='1619530'>transfer</span> <span
  m='1620040'>function</span> <span m='1621270'>in</span> <span
  m='1621780'>a</span> <span m='1621870'>form</span> <span m='1623010'>as</span>
  <span m='1623280'>I've</span> <span m='1623430'>indicated</span> <span
  m='1624000'>here--</span> <span m='1625110'>a</span> <span
  m='1625170'>second</span> <span m='1625560'>order</span> <span
  m='1626130'>numerator</span> <span m='1626670'>polynomial</span> <span
  m='1628050'>and</span> <span m='1628260'>a</span> <span
  m='1628320'>second</span> <span m='1628680'>order</span> <span
  m='1628950'>denominator</span> <span m='1629610'>polynomial,</span> <span
  m='1630990'>and,</span> <span m='1631380'>of</span> <span
  m='1631530'>course,</span> <span m='1631860'>it's</span> <span
  m='1632010'>the</span> <span m='1632070'>product</span> <span
  m='1632790'>of</span> <span m='1632990'>these</span> <span
  m='1634110'>that</span> <span m='1634440'>we</span> <span
  m='1634590'>use</span> <span m='1635040'>to</span> <span
  m='1635160'>implement</span> <span m='1635700'>this</span> <span
  m='1635850'>overall</span> <span m='1636630'>transfer</span> <span
  m='1637140'>function</span> <span m='1638190'>with</span> <span
  m='1638790'>some</span> <span m='1639030'>constant</span> <span
  m='1639510'>multiplier</span> <span m='1640380'>out</span> <span
  m='1640620'>in</span> <span m='1640710'>front,</span> <span
  m='1641550'>which</span> <span m='1641760'>is</span> <span
  m='1641850'>required</span> <span m='1643590'>essentially</span> <span
  m='1644100'>because</span> <span m='1644460'>we've</span> <span
  m='1644610'>normalized</span> <span m='1645210'>these</span> <span
  m='1645390'>polynomials</span> <span m='1646680'>to</span> <span
  m='1646800'>have</span> <span m='1647190'>a</span> <span
  m='1647280'>leading</span> <span m='1647580'>coefficient</span> <span
  m='1648240'>of</span> <span m='1648330'>unity.</span> </p><p><span
  m='1650610'>Well,</span> <span m='1651600'>first</span> <span
  m='1651930'>of</span> <span m='1652050'>all,</span> <span
  m='1652800'>why</span> <span m='1653190'>might</span> <span
  m='1653730'>we</span> <span m='1653910'>want</span> <span
  m='1654090'>to</span> <span m='1654180'>do</span> <span
  m='1654390'>this?</span> <span m='1656070'>There</span> <span
  m='1656700'>actually</span> <span m='1657210'>are</span> <span
  m='1657360'>a</span> <span m='1657390'>variety</span> <span
  m='1657930'>of</span> <span m='1658290'>reasons</span> <span
  m='1659130'>for</span> <span m='1659430'>perhaps</span> <span
  m='1659940'>wanting</span> <span m='1660270'>to</span> <span
  m='1660390'>consider</span> <span m='1661140'>an</span> <span
  m='1661260'>implementation</span> <span m='1662010'>of</span> <span
  m='1662130'>the</span> <span m='1662220'>transfer</span> <span
  m='1662700'>function</span> <span m='1663390'>in</span> <span
  m='1663540'>terms</span> <span m='1663990'>of</span> <span
  m='1664140'>a</span> <span m='1664200'>cascade</span> <span
  m='1665100'>of</span> <span m='1665910'>lower</span> <span
  m='1666330'>order</span> <span m='1667080'>systems</span> <span
  m='1668010'>than</span> <span m='1668190'>the</span> <span
  m='1668310'>general</span> <span m='1668790'>n-th</span> <span
  m='1669045'>order</span> <span m='1669300'>system.</span> <span
  m='1671040'>One</span> <span m='1671190'>of</span> <span
  m='1671280'>the</span> <span m='1671370'>more</span> <span
  m='1671550'>common</span> <span m='1671970'>reasons,</span> <span
  m='1672750'>which</span> <span m='1673170'>I'll</span> <span
  m='1673320'>have</span> <span m='1673500'>more</span> <span
  m='1673710'>to</span> <span m='1673830'>say</span> <span
  m='1674100'>about</span> <span m='1675010'>actually</span> <span
  m='1675940'>at</span> <span m='1676650'>the</span> <span
  m='1676800'>end</span> <span m='1676950'>of</span> <span
  m='1677040'>the</span> <span m='1677130'>next</span> <span
  m='1677400'>lecture,</span> <span m='1677810'>but</span> <span
  m='1678150'>I'd</span> <span m='1678270'>like</span> <span
  m='1678450'>to</span> <span m='1678600'>at</span> <span
  m='1678660'>least</span> <span m='1678870'>allude</span> <span
  m='1679170'>to</span> <span m='1679380'>it</span> <span
  m='1679450'>now,</span> <span m='1680510'>is</span> <span
  m='1680640'>the</span> <span m='1680760'>fact</span> <span
  m='1681390'>that</span> <span m='1682260'>any</span> <span
  m='1682530'>time</span> <span m='1682920'>we</span> <span
  m='1683070'>implement</span> <span m='1683520'>a</span> <span
  m='1683580'>system</span> <span m='1685110'>on</span> <span
  m='1685260'>a</span> <span m='1685320'>digital</span> <span
  m='1685680'>computer</span> <span m='1686820'>or</span> <span
  m='1687030'>with</span> <span m='1687180'>special</span> <span
  m='1687600'>purpose</span> <span m='1687960'>hardware</span> <span
  m='1689190'>we're</span> <span m='1689310'>faced</span> <span
  m='1690000'>with</span> <span m='1690240'>the</span> <span
  m='1690330'>problem</span> <span m='1691830'>that</span> <span
  m='1692160'>these</span> <span m='1692400'>coefficients</span> <span
  m='1693750'>can't</span> <span m='1694020'>be</span> <span
  m='1694140'>represented</span> <span m='1694740'>exactly.</span> </p><p><span
  m='1696420'>If</span> <span m='1696600'>we</span> <span
  m='1696720'>have,</span> <span m='1697270'>let's</span> <span
  m='1697350'>say,</span> <span m='1697660'>an</span> <span m='1697760'>18
  bit</span> <span m='1698250'>fixed</span> <span m='1698550'>point</span> <span
  m='1698850'>register,</span> <span m='1699870'>we're</span> <span
  m='1700050'>restricted</span> <span m='1700950'>to</span> <span
  m='1701940'>truncating</span> <span m='1702660'>or</span> <span
  m='1702810'>rounding</span> <span m='1703260'>these</span> <span
  m='1703440'>coefficients</span> <span m='1704280'>to</span> <span
  m='1704640'>18</span> <span m='1705120'>bits.</span> <span
  m='1706110'>If</span> <span m='1706290'>we</span> <span
  m='1706410'>implement</span> <span m='1707100'>a</span> <span
  m='1707160'>filter</span> <span m='1707520'>and</span> <span
  m='1707670'>special</span> <span m='1708030'>purpose</span> <span
  m='1708420'>hardware,</span> <span m='1709500'>we</span> <span
  m='1709620'>might</span> <span m='1710130'>want</span> <span
  m='1710430'>the</span> <span m='1710520'>coefficient</span> <span
  m='1711150'>registers</span> <span m='1711780'>to</span> <span
  m='1711930'>be</span> <span m='1712080'>as</span> <span m='1712200'>low</span>
  <span m='1712410'>as</span> <span m='1712530'>4,</span> <span
  m='1712840'>or</span> <span m='1712890'>5,</span> <span m='1713310'>or</span>
  <span m='1713430'>6,</span> <span m='1713910'>or</span> <span
  m='1714210'>10</span> <span m='1714540'>bits.</span> <span
  m='1715380'>Obviously,</span> <span m='1716220'>the</span> <span
  m='1716340'>more</span> <span m='1716580'>bits,</span> <span
  m='1717180'>the</span> <span m='1718020'>more</span> <span
  m='1718200'>expensive</span> <span m='1719010'>the</span> <span
  m='1719130'>hardware</span> <span m='1719490'>implementation</span> <span
  m='1720300'>is.</span> <span m='1722010'>And</span> <span
  m='1722760'>the</span> <span m='1723270'>statement</span> <span
  m='1723900'>which</span> <span m='1724110'>I'll</span> <span
  m='1724230'>make</span> <span m='1724740'>and</span> <span
  m='1725640'>justify</span> <span m='1726030'>in</span> <span
  m='1726420'>a</span> <span m='1726510'>little</span> <span
  m='1726690'>more</span> <span m='1726900'>detail</span> <span
  m='1727410'>at</span> <span m='1727500'>the</span> <span
  m='1727620'>end</span> <span m='1727800'>of</span> <span
  m='1727890'>the</span> <span m='1727980'>next</span> <span
  m='1728250'>lecture</span> <span m='1729360'>is</span> <span
  m='1729600'>that,</span> <span m='1730290'>if</span> <span
  m='1731160'>I</span> <span m='1731400'>implement</span> <span
  m='1732360'>the</span> <span m='1732480'>poles</span> <span
  m='1732900'>of</span> <span m='1732990'>the</span> <span
  m='1733110'>system</span> <span m='1734460'>through</span> <span
  m='1735060'>a</span> <span m='1735330'>high</span> <span
  m='1735630'>order</span> <span m='1735930'>polynomial,</span> <span
  m='1738210'>errors</span> <span m='1738660'>in</span> <span
  m='1738750'>the</span> <span m='1738840'>coefficients</span> <span
  m='1740670'>lead</span> <span m='1741150'>to</span> <span
  m='1741360'>large</span> <span m='1741750'>errors</span> <span
  m='1742230'>in</span> <span m='1742380'>the</span> <span
  m='1742470'>pole</span> <span m='1742740'>locations</span> <span
  m='1744060'>as</span> <span m='1744240'>compared</span> <span
  m='1744960'>with</span> <span m='1745170'>an</span> <span
  m='1745260'>implementation</span> <span m='1746310'>of</span> <span
  m='1746490'>the</span> <span m='1746580'>poles</span> <span
  m='1747900'>in</span> <span m='1748020'>terms</span> <span
  m='1748530'>of</span> <span m='1748740'>low</span> <span
  m='1749010'>order</span> <span m='1749220'>polynomials.</span> <span
  m='1750420'>That</span> <span m='1750630'>is,</span> <span
  m='1750870'>basically</span> <span m='1751560'>the</span> <span
  m='1751650'>sensitivity</span> <span m='1752430'>of</span> <span
  m='1752520'>pole</span> <span m='1752790'>locations</span> <span
  m='1754250'>to</span> <span m='1754380'>errors</span> <span
  m='1754770'>in</span> <span m='1754860'>the</span> <span
  m='1754950'>coefficients</span> <span m='1756840'>is</span> <span
  m='1757020'>higher</span> <span m='1757950'>the</span> <span
  m='1758070'>higher</span> <span m='1758400'>the</span> <span
  m='1758550'>order</span> <span m='1758820'>of</span> <span
  m='1758880'>the</span> <span m='1759000'>polynomial.</span> </p><p><span
  m='1760710'>Consequently,</span> <span m='1762180'>if</span> <span
  m='1762630'>that</span> <span m='1762990'>indeed</span> <span
  m='1763380'>is</span> <span m='1763500'>an</span> <span
  m='1763620'>issue</span> <span m='1764280'>for</span> <span
  m='1764670'>the</span> <span m='1764760'>filter</span> <span
  m='1765120'>implementation,</span> <span m='1766560'>then</span> <span
  m='1767430'>it</span> <span m='1768360'>is</span> <span
  m='1768540'>better</span> <span m='1769470'>to</span> <span
  m='1769620'>implement</span> <span m='1770910'>a</span> <span
  m='1771030'>system</span> <span m='1772140'>as</span> <span
  m='1772320'>a</span> <span m='1772380'>cascade</span> <span
  m='1773160'>of</span> <span m='1773340'>lower</span> <span
  m='1773730'>order</span> <span m='1774000'>systems</span> <span
  m='1774630'>or</span> <span m='1774780'>lower</span> <span
  m='1775110'>order</span> <span m='1775320'>polynomials</span> <span
  m='1776580'>then</span> <span m='1777030'>as</span> <span
  m='1777540'>one</span> <span m='1777810'>large</span> <span
  m='1778260'>high</span> <span m='1778560'>order</span> <span
  m='1778770'>polynomial.</span> <span m='1781080'>So</span> <span
  m='1782100'>factoring</span> <span m='1783030'>this</span> <span
  m='1783240'>transfer</span> <span m='1783690'>function</span> <span
  m='1784410'>into</span> <span m='1785490'>a</span> <span
  m='1785640'>cascade</span> <span m='1786750'>of</span> <span
  m='1787020'>second</span> <span m='1787380'>order</span> <span
  m='1787620'>sections,</span> <span m='1789060'>what</span> <span
  m='1789660'>this</span> <span m='1789870'>leads</span> <span
  m='1790230'>to</span> <span m='1790560'>is</span> <span m='1790740'>an</span>
  <span m='1790830'>implementation</span> <span m='1792420'>of</span> <span
  m='1793170'>the</span> <span m='1793290'>system</span> <span
  m='1793920'>as</span> <span m='1794100'>a</span> <span
  m='1794160'>cascade</span> <span m='1794970'>of</span> <span
  m='1795120'>second</span> <span m='1795510'>order</span> <span
  m='1796200'>systems,</span> <span m='1797940'>and</span> <span
  m='1798420'>we,</span> <span m='1798630'>again,</span> <span
  m='1798960'>have</span> <span m='1799140'>the</span> <span
  m='1799230'>choice</span> <span m='1799890'>of</span> <span
  m='1800310'>implementing</span> <span m='1800970'>each</span> <span
  m='1801180'>second</span> <span m='1801540'>order</span> <span
  m='1801780'>section</span> <span m='1802920'>in</span> <span
  m='1803430'>a</span> <span m='1803520'>variety</span> <span
  m='1804090'>of</span> <span m='1804210'>ways</span> <span
  m='1805110'>corresponding</span> <span m='1805830'>to</span> <span
  m='1805950'>the</span> <span m='1806910'>various</span> <span
  m='1807420'>direct</span> <span m='1807780'>forms</span> <span
  m='1808350'>that</span> <span m='1808530'>we've</span> <span
  m='1808740'>talked</span> <span m='1809070'>about</span> <span
  m='1809280'>previously.</span> </p><p><span m='1810660'>One</span> <span
  m='1810870'>implementation,</span> <span m='1812920'>which</span> <span
  m='1814080'>is</span> <span m='1814920'>a</span> <span
  m='1815190'>canonic</span> <span m='1816420'>direct</span> <span
  m='1816810'>form,</span> <span m='1818280'>is</span> <span
  m='1818610'>the</span> <span m='1818730'>implementation</span> <span
  m='1819900'>that</span> <span m='1820080'>I</span> <span
  m='1820200'>indicate</span> <span m='1820740'>here,</span> <span
  m='1821760'>where</span> <span m='1823110'>this</span> <span
  m='1824040'>is</span> <span m='1824400'>alpha</span> <span
  m='1824790'>1,1,</span> <span m='1825990'>the</span> <span
  m='1826080'>coefficient</span> <span m='1826620'>alpha</span> <span
  m='1826920'>1,1,</span> <span m='1828030'>the</span> <span
  m='1828200'>coefficient</span> <span m='1828810'>beta</span> <span
  m='1829470'>1,1.</span> <span m='1830040'>It's</span> <span
  m='1830160'>a</span> <span m='1830190'>little</span> <span
  m='1830370'>hard</span> <span m='1830580'>to</span> <span
  m='1830730'>see</span> <span m='1831330'>where</span> <span
  m='1831780'>each</span> <span m='1831990'>of</span> <span
  m='1832050'>these</span> <span m='1832230'>coefficients</span> <span
  m='1832860'>goes,</span> <span m='1833790'>but</span> <span
  m='1834300'>this</span> <span m='1834540'>is</span> <span m='1834720'>a</span>
  <span m='1834780'>canonic</span> <span m='1835230'>form</span> <span
  m='1835530'>implementation</span> <span m='1836670'>of</span> <span
  m='1837890'>a</span> <span m='1837930'>second</span> <span
  m='1838350'>order</span> <span m='1838590'>section</span> <span
  m='1839070'>that</span> <span m='1839250'>has</span> <span
  m='1839400'>two</span> <span m='1839580'>poles</span> <span
  m='1839970'>and</span> <span m='1840060'>two</span> <span
  m='1840240'>0's.</span> <span m='1841620'>So</span> <span
  m='1842460'>as</span> <span m='1842640'>I've</span> <span
  m='1842790'>implemented</span> <span m='1843360'>it,</span> <span
  m='1843540'>I've</span> <span m='1843720'>implemented</span> <span
  m='1844280'>it</span> <span m='1844860'>with</span> <span
  m='1845610'>the</span> <span m='1845730'>poles</span> <span
  m='1846180'>first,</span> <span m='1846940'>followed</span> <span
  m='1847230'>by</span> <span m='1847410'>the</span> <span
  m='1847530'>0's,</span> <span m='1848730'>and</span> <span
  m='1849660'>then</span> <span m='1850170'>this</span> <span
  m='1850380'>is</span> <span m='1850560'>one</span> <span
  m='1851070'>second</span> <span m='1851460'>order</span> <span
  m='1851730'>piece</span> <span m='1852510'>that's</span> <span
  m='1852780'>in</span> <span m='1852900'>cascade</span> <span
  m='1853800'>with</span> <span m='1854070'>the</span> <span
  m='1854190'>next</span> <span m='1854880'>pole</span> <span
  m='1855160'>0</span> <span m='1855570'>pair,</span> <span
  m='1856740'>with</span> <span m='1856860'>the</span> <span
  m='1856950'>next</span> <span m='1857190'>pole</span> <span
  m='1857430'>0</span> <span m='1857760'>pair,</span> <span m='1858060'>et
  cetera.</span> </p><p><span m='1859740'>So</span> <span
  m='1860130'>this</span> <span m='1860370'>is</span> <span m='1860670'>a</span>
  <span m='1860760'>cascade</span> <span m='1862050'>of</span> <span
  m='1862140'>second</span> <span m='1862500'>order</span> <span
  m='1862710'>sections,</span> <span m='1863970'>and,</span> <span
  m='1864060'>of</span> <span m='1864180'>course,</span> <span
  m='1864750'>I</span> <span m='1865020'>can</span> <span
  m='1865500'>generate</span> <span m='1866010'>other</span> <span
  m='1866220'>cascade</span> <span m='1866880'>forms</span> <span
  m='1868680'>was</span> <span m='1868980'>one</span> <span
  m='1869190'>possibility</span> <span m='1870480'>by</span> <span
  m='1870630'>just</span> <span m='1870810'>simply</span> <span
  m='1871200'>applying</span> <span m='1871620'>the</span> <span
  m='1871710'>transposition</span> <span m='1872490'>theorem</span> <span
  m='1873600'>to</span> <span m='1873750'>this</span> <span
  m='1874380'>cascade,</span> <span m='1875670'>and</span> <span
  m='1876300'>basically</span> <span m='1876870'>what</span> <span
  m='1877050'>would</span> <span m='1877200'>result</span> <span
  m='1877830'>is</span> <span m='1878010'>that</span> <span
  m='1878880'>each</span> <span m='1879150'>of</span> <span
  m='1879270'>these</span> <span m='1879830'>delay</span> <span
  m='1880080'>branches</span> <span m='1880710'>would</span> <span
  m='1880980'>be</span> <span m='1881100'>reversed</span> <span
  m='1881580'>in</span> <span m='1881670'>direction,</span> <span
  m='1882780'>and</span> <span m='1883380'>the</span> <span
  m='1883500'>0's</span> <span m='1883980'>would</span> <span
  m='1884070'>be</span> <span m='1884220'>implemented</span> <span
  m='1884730'>first,</span> <span m='1885160'>followed</span> <span
  m='1885390'>by</span> <span m='1885540'>the</span> <span
  m='1885660'>poles.</span> <span m='1887280'>Generally</span> <span
  m='1887730'>what's</span> <span m='1887970'>meant</span> <span
  m='1888240'>though</span> <span m='1888420'>by</span> <span
  m='1888600'>the</span> <span m='1888690'>cascade</span> <span
  m='1889290'>structure,</span> <span m='1889930'>and</span> <span
  m='1890030'>you</span> <span m='1890040'>can</span> <span
  m='1890190'>see</span> <span m='1890580'>again</span> <span
  m='1890970'>that</span> <span m='1891120'>there</span> <span
  m='1891870'>are</span> <span m='1892140'>a</span> <span
  m='1892260'>variety</span> <span m='1892800'>of</span> <span
  m='1892890'>cascade</span> <span m='1893460'>structures</span> <span
  m='1894060'>depending</span> <span m='1894510'>on</span> <span
  m='1894630'>how</span> <span m='1894810'>you</span> <span
  m='1894990'>choose</span> <span m='1895260'>to</span> <span
  m='1895350'>implement</span> <span m='1895880'>the pole</span> <span
  m='1896130'>0</span> <span m='1896630'>pairs--</span> <span
  m='1897840'>what</span> <span m='1897960'>is</span> <span
  m='1898050'>generally</span> <span m='1898440'>meant</span> <span
  m='1898710'>by</span> <span m='1898890'>the</span> <span
  m='1898980'>cascade</span> <span m='1899580'>structure</span> <span
  m='1900120'>or</span> <span m='1900390'>a</span> <span
  m='1900540'>cascade</span> <span m='1901140'>structure</span> <span
  m='1902130'>is</span> <span m='1902880'>an</span> <span
  m='1902970'>implementation</span> <span m='1903750'>of</span> <span
  m='1903840'>the</span> <span m='1903930'>transfer</span> <span
  m='1904410'>function</span> <span m='1905370'>is</span> <span
  m='1905490'>a</span> <span m='1905550'>cascade</span> <span
  m='1906840'>of</span> <span m='1907260'>second</span> <span
  m='1907680'>order</span> <span m='1907920'>sections</span> <span
  m='1908910'>where</span> <span m='1909010'>the</span> <span
  m='1909120'>second</span> <span m='1909480'>order</span> <span
  m='1909720'>sections</span> <span m='1910260'>can</span> <span
  m='1910440'>be</span> <span m='1910590'>implemented</span> <span
  m='1911130'>in</span> <span m='1911250'>a</span> <span
  m='1911310'>variety</span> <span m='1911850'>of</span> <span
  m='1911940'>ways.</span> </p><p><span m='1914470'>Another</span> <span
  m='1916640'>structure</span> <span m='1917840'>which</span> <span
  m='1918620'>is</span> <span m='1918830'>like</span> <span
  m='1919520'>the</span> <span m='1920360'>cascade</span> <span
  m='1921000'>structure</span> <span m='1921680'>in</span> <span
  m='1921890'>that</span> <span m='1922130'>it</span> <span
  m='1922310'>implements</span> <span m='1922880'>the</span> <span
  m='1922970'>poles</span> <span m='1923930'>in</span> <span
  m='1924020'>terms</span> <span m='1924350'>of</span> <span
  m='1924470'>low</span> <span m='1924740'>order</span> <span
  m='1924950'>sections,</span> <span m='1926250'>but</span> <span
  m='1926630'>is</span> <span m='1926870'>different</span> <span
  m='1927380'>in</span> <span m='1927500'>the</span> <span
  m='1927590'>way</span> <span m='1928280'>effectively</span> <span
  m='1928880'>that</span> <span m='1929030'>it</span> <span
  m='1929090'>realizes</span> <span m='1929750'>the</span> <span
  m='1929870'>zeros</span> <span m='1930830'>is</span> <span
  m='1931160'>the</span> <span m='1931280'>so-called</span> <span
  m='1932300'>parallel</span> <span m='1933080'>form</span> <span
  m='1933470'>structure.</span> <span m='1935840'>And</span> <span
  m='1936530'>the</span> <span m='1936650'>parallel</span> <span
  m='1937580'>form</span> <span m='1938000'>structure</span> <span
  m='1939440'>can</span> <span m='1939710'>be</span> <span
  m='1940160'>implemented</span> <span m='1941180'>by--</span> <span
  m='1942404'>can</span> <span m='1943220'>be</span> <span
  m='1943340'>derived</span> <span m='1944540'>by</span> <span
  m='1945590'>expanding</span> <span m='1947510'>the</span> <span
  m='1947630'>transfer</span> <span m='1948170'>function</span> <span
  m='1948620'>of</span> <span m='1948710'>the</span> <span
  m='1948800'>system</span> <span m='1950180'>in</span> <span
  m='1950300'>terms</span> <span m='1950690'>of</span> <span
  m='1950780'>a</span> <span m='1950840'>partial</span> <span
  m='1951290'>fraction</span> <span m='1951800'>expansion.</span> <span
  m='1953960'>That</span> <span m='1954170'>is,</span> <span
  m='1954680'>we</span> <span m='1954860'>can</span> <span
  m='1955010'>expand</span> <span m='1956000'>this</span> <span
  m='1956210'>transfer</span> <span m='1956750'>function</span> <span
  m='1958490'>in</span> <span m='1958640'>terms</span> <span
  m='1959180'>of--</span> <span m='1959960'>and</span> <span
  m='1960080'>let's</span> <span m='1961190'>assume</span> <span
  m='1961490'>first</span> <span m='1961850'>of</span> <span
  m='1961970'>all</span> <span m='1962150'>the</span> <span
  m='1962270'>capital</span> <span m='1962750'>M</span> <span
  m='1963050'>is</span> <span m='1963260'>less</span> <span
  m='1963530'>than</span> <span m='1963680'>capital N.</span> <span
  m='1964550'>If</span> <span m='1964700'>capital</span> <span
  m='1965090'>M</span> <span m='1965210'>were</span> <span
  m='1965300'>less</span> <span m='1965570'>than</span> <span
  m='1965720'>capital</span> <span m='1966200'>N,</span> <span
  m='1967010'>we</span> <span m='1967100'>can</span> <span
  m='1967250'>expand</span> <span m='1967760'>this</span> <span
  m='1968300'>simply</span> <span m='1968930'>as</span> <span
  m='1969530'>a</span> <span m='1969590'>sum</span> <span m='1970220'>of</span>
  <span m='1970400'>residues</span> <span m='1972740'>together</span> <span
  m='1973460'>with</span> <span m='1973640'>first</span> <span
  m='1974000'>order</span> <span m='1974270'>poles,</span> <span
  m='1975920'>or</span> <span m='1976190'>in</span> <span
  m='1976280'>general</span> <span m='1976730'>since</span> <span
  m='1977000'>the</span> <span m='1977120'>poles</span> <span
  m='1977720'>are</span> <span m='1977870'>complex,</span> <span
  m='1979350'>we</span> <span m='1979370'>can</span> <span
  m='1979520'>imagine</span> <span m='1980390'>factoring</span> <span
  m='1980990'>this</span> <span m='1981320'>in</span> <span
  m='1981440'>terms</span> <span m='1982040'>of</span> <span
  m='1982850'>first</span> <span m='1983210'>order</span> <span
  m='1983510'>terms</span> <span m='1984620'>corresponding</span> <span
  m='1985340'>to</span> <span m='1985430'>the</span> <span
  m='1985550'>real</span> <span m='1985820'>poles,</span> <span
  m='1988120'>and</span> <span m='1988840'>then</span> <span
  m='1989050'>second</span> <span m='1989470'>order</span> <span
  m='1989740'>terms</span> <span m='1990220'>where</span> <span
  m='1990460'>we</span> <span m='1990970'>combine</span> <span
  m='1991420'>together</span> <span m='1991990'>first</span> <span
  m='1992350'>order</span> <span m='1992620'>terms</span> <span
  m='1993040'>which</span> <span m='1993220'>are</span> <span
  m='1993280'>complex</span> <span m='1993850'>conjugates</span> <span
  m='1995080'>so</span> <span m='1995290'>that</span> <span
  m='1995620'>we</span> <span m='1995800'>have</span> <span
  m='1995950'>second</span> <span m='1996310'>order</span> <span
  m='1996550'>terms</span> <span m='1997150'>of</span> <span
  m='1997270'>this</span> <span m='1997510'>form.</span> <span
  m='1999450'>If</span> <span m='1999680'>capital</span> <span
  m='2000090'>M</span> <span m='2000490'>is</span> <span m='2000670'>less</span>
  <span m='2000940'>than</span> <span m='2001090'>capital</span> <span
  m='2001610'>N,</span> <span m='2002290'>those</span> <span
  m='2002560'>are</span> <span m='2002650'>the</span> <span
  m='2002770'>only</span> <span m='2003010'>two</span> <span
  m='2003190'>kinds</span> <span m='2003580'>of</span> <span
  m='2003670'>terms</span> <span m='2004600'>that</span> <span
  m='2004870'>would</span> <span m='2005050'>result</span> <span
  m='2005590'>in</span> <span m='2005710'>a</span> <span
  m='2005770'>partial</span> <span m='2006160'>fraction</span> <span
  m='2006610'>expansion.</span> <span m='2008290'>If</span> <span
  m='2008920'>capital</span> <span m='2009500'>M</span> <span
  m='2009730'>is</span> <span m='2009910'>greater</span> <span
  m='2010660'>than</span> <span m='2010960'>or</span> <span
  m='2011140'>equal</span> <span m='2011440'>to</span> <span
  m='2011590'>capital</span> <span m='2012100'>N,</span> <span
  m='2012510'>then</span> <span m='2012790'>we'll</span> <span
  m='2013330'>have</span> <span m='2013720'>additional</span> <span
  m='2014260'>terms</span> <span m='2015130'>corresponding</span> <span
  m='2015910'>simply</span> <span m='2016660'>to</span> <span
  m='2017110'>weighted</span> <span m='2017560'>powers</span> <span
  m='2018460'>of</span> <span m='2018730'>z</span> <span m='2018940'>to</span>
  <span m='2019060'>the</span> <span m='2019180'>minus</span> <span
  m='2019540'>1.</span> </p><p><span m='2020932'>Now,</span> <span
  m='2022120'>as</span> <span m='2022630'>in</span> <span m='2022750'>the</span>
  <span m='2022840'>cascade</span> <span m='2023470'>form,</span> <span
  m='2024010'>generally</span> <span m='2025060'>the</span> <span
  m='2025150'>parallel</span> <span m='2025570'>form</span> <span
  m='2025900'>structure</span> <span m='2026740'>is</span> <span
  m='2027040'>considered</span> <span m='2027550'>to</span> <span
  m='2027700'>be</span> <span m='2027880'>one</span> <span
  m='2028450'>where</span> <span m='2029380'>even</span> <span
  m='2029980'>if</span> <span m='2030490'>we</span> <span
  m='2030670'>have</span> <span m='2031510'>real</span> <span
  m='2032110'>poles</span> <span m='2033160'>we</span> <span
  m='2033310'>combine</span> <span m='2033790'>two</span> <span
  m='2034030'>of</span> <span m='2034120'>the</span> <span
  m='2034240'>real</span> <span m='2034480'>poles</span> <span
  m='2034810'>together</span> <span m='2035830'>to</span> <span
  m='2036100'>implement</span> <span m='2036590'>the</span> <span
  m='2036700'>system</span> <span m='2037090'>in</span> <span
  m='2037150'>terms</span> <span m='2037450'>of</span> <span
  m='2037540'>second</span> <span m='2037870'>order</span> <span
  m='2038110'>sections.</span> <span m='2039250'>If</span> <span
  m='2039340'>we</span> <span m='2039490'>do</span> <span
  m='2039670'>that,</span> <span m='2040420'>then</span> <span
  m='2040630'>the</span> <span m='2041320'>parallel</span> <span
  m='2041740'>form</span> <span m='2042070'>expansion</span> <span
  m='2042970'>for</span> <span m='2043090'>the</span> <span
  m='2043210'>transfer</span> <span m='2043690'>function</span> <span
  m='2044740'>is</span> <span m='2045250'>what</span> <span
  m='2045460'>I've</span> <span m='2045610'>indicated</span> <span
  m='2046180'>here,</span> <span m='2047240'>where</span> <span
  m='2047620'>combining</span> <span m='2048219'>two</span> <span
  m='2048429'>terms</span> <span m='2048909'>of</span> <span
  m='2049000'>this</span> <span m='2049210'>form</span> <span
  m='2049510'>together,</span> <span m='2050080'>or,</span> <span
  m='2050199'>equivalently,</span> <span m='2051370'>looking</span> <span
  m='2051820'>at</span> <span m='2052989'>expansions</span> <span
  m='2053889'>of</span> <span m='2054010'>this</span> <span
  m='2054250'>form,</span> <span m='2055670'>we</span> <span
  m='2055750'>have</span> <span m='2056860'>a</span> <span
  m='2056920'>numerator</span> <span m='2057400'>polynomial</span> <span
  m='2058750'>implementing</span> <span m='2059320'>a</span> <span
  m='2059380'>single</span> <span m='2059739'>0</span> <span
  m='2060940'>and</span> <span m='2061060'>a</span> <span
  m='2061120'>denominator</span> <span m='2061780'>polynomial</span> <span
  m='2062830'>implementing</span> <span m='2063400'>two</span> <span
  m='2063750'>poles.</span> <span m='2065290'>And</span> <span
  m='2065469'>then</span> <span m='2066130'>depending</span> <span
  m='2066580'>on</span> <span m='2066639'>whether</span> <span
  m='2067000'>M</span> <span m='2067270'>is</span> <span
  m='2067389'>greater</span> <span m='2067719'>than</span> <span
  m='2067870'>capital</span> <span m='2068185'>N</span> <span
  m='2068500'>or</span> <span m='2068560'>not,</span> <span
  m='2069070'>there</span> <span m='2069219'>might</span> <span
  m='2069460'>be</span> <span m='2069580'>additional</span> <span
  m='2070060'>terms</span> <span m='2070659'>involving</span> <span
  m='2071440'>simple</span> <span m='2072190'>weighted</span> <span
  m='2073840'>values</span> <span m='2074620'>of</span> <span
  m='2074770'>z</span> <span m='2074980'>to</span> <span m='2075100'>the</span>
  <span m='2075190'>minus--</span> <span m='2076030'>weighted</span> <span
  m='2076510'>powers</span> <span m='2076989'>of</span> <span
  m='2077080'>z</span> <span m='2077260'>to</span> <span m='2077380'>the</span>
  <span m='2077469'>minus</span> <span m='2077830'>1.</span> </p><p><span
  m='2079300'>Let</span> <span m='2079420'>me</span> <span
  m='2079570'>stress</span> <span m='2080530'>that</span> <span
  m='2081250'>there</span> <span m='2081550'>are</span> <span
  m='2081760'>some</span> <span m='2081940'>differences</span> <span
  m='2082960'>between</span> <span m='2083409'>this</span> <span
  m='2083620'>and</span> <span m='2083710'>the</span> <span
  m='2083800'>cascade</span> <span m='2084370'>form</span> <span
  m='2084699'>obviously.</span> <span m='2085960'>One</span> <span
  m='2086170'>of</span> <span m='2086260'>the</span> <span
  m='2086350'>differences</span> <span m='2087130'>is</span> <span
  m='2087370'>that</span> <span m='2087520'>the</span> <span
  m='2087610'>sections</span> <span m='2088480'>used</span> <span
  m='2088900'>for</span> <span m='2089080'>implementing</span> <span
  m='2089679'>the</span> <span m='2089770'>filter</span> <span
  m='2090760'>consist</span> <span m='2091210'>of</span> <span
  m='2091420'>one</span> <span m='2091770'>0</span> <span
  m='2093159'>plus</span> <span m='2094270'>two</span> <span
  m='2094489'>poles,</span> <span m='2096730'>and</span> <span
  m='2097570'>then</span> <span m='2098110'>the</span> <span
  m='2098320'>output</span> <span m='2098770'>is</span> <span
  m='2098920'>formed</span> <span m='2099370'>not</span> <span
  m='2099610'>as</span> <span m='2099730'>a</span> <span
  m='2099790'>cascade</span> <span m='2100630'>of</span> <span
  m='2100780'>sections</span> <span m='2101320'>of</span> <span
  m='2101410'>that</span> <span m='2101620'>type,</span> <span
  m='2102490'>but</span> <span m='2102730'>as</span> <span m='2103060'>a</span>
  <span m='2103390'>sum</span> <span m='2103990'>of</span> <span
  m='2104170'>the</span> <span m='2104290'>outputs</span> <span
  m='2105280'>of</span> <span m='2105400'>sections</span> <span
  m='2105940'>of</span> <span m='2106030'>that</span> <span
  m='2106240'>type</span> <span m='2106960'>since</span> <span m='2107770'>H of
  z</span> <span m='2108460'>here</span> <span m='2108700'>is</span> <span
  m='2108850'>expressed</span> <span m='2109390'>as</span> <span
  m='2109540'>a</span> <span m='2109600'>sum</span> <span m='2110260'>of</span>
  <span m='2110680'>second</span> <span m='2111100'>order</span> <span
  m='2111340'>sections,</span> <span m='2112420'>whereas</span> <span
  m='2112900'>in</span> <span m='2112950'>the</span> <span
  m='2113050'>cascade</span> <span m='2113620'>form</span> <span
  m='2113920'>it</span> <span m='2114000'>is</span> <span
  m='2114130'>expressed</span> <span m='2114760'>as</span> <span
  m='2114910'>a</span> <span m='2114970'>product</span> <span
  m='2115410'>of</span> <span m='2115500'>second</span> <span
  m='2115840'>order</span> <span m='2116050'>sections.</span> </p><p><span
  m='2118270'>Well,</span> <span m='2118720'>the</span> <span
  m='2119080'>general</span> <span m='2119800'>filter</span> <span
  m='2120250'>structure</span> <span m='2121240'>that</span> <span
  m='2121420'>results</span> <span m='2123810'>I've</span> <span
  m='2123990'>indicated</span> <span m='2124590'>here</span> <span
  m='2125010'>for</span> <span m='2125160'>the</span> <span
  m='2125250'>case</span> <span m='2125790'>in</span> <span
  m='2125910'>which</span> <span m='2126360'>we</span> <span
  m='2126540'>have</span> <span m='2126780'>three</span> <span
  m='2127650'>second</span> <span m='2128040'>order</span> <span
  m='2128310'>sections,</span> <span m='2129640'>and</span> <span
  m='2130050'>again,</span> <span m='2130380'>I'm</span> <span
  m='2130500'>assuming</span> <span m='2131040'>that</span> <span
  m='2131280'>capital</span> <span m='2131790'>M</span> <span
  m='2131940'>is</span> <span m='2132060'>equal</span> <span
  m='2132360'>to</span> <span m='2132480'>capital</span> <span
  m='2132735'>N</span> <span m='2133890'>so</span> <span m='2134160'>that</span>
  <span m='2134700'>we</span> <span m='2134910'>have</span> <span
  m='2135180'>one</span> <span m='2135660'>branch,</span> <span
  m='2136450'>which</span> <span m='2136620'>is</span> <span
  m='2136740'>just</span> <span m='2136920'>simply</span> <span
  m='2137250'>a</span> <span m='2137280'>coefficient</span> <span
  m='2137940'>branch.</span> <span m='2138900'>If</span> <span
  m='2139020'>capital</span> <span m='2139500'>M</span> <span
  m='2139950'>was</span> <span m='2140160'>one</span> <span
  m='2140400'>more</span> <span m='2140670'>than</span> <span
  m='2140820'>capital</span> <span m='2141330'>N,</span> <span
  m='2141990'>we</span> <span m='2142080'>would</span> <span
  m='2142200'>have</span> <span m='2142410'>in</span> <span
  m='2142470'>addition</span> <span m='2142890'>to</span> <span
  m='2143010'>that</span> <span m='2143700'>one</span> <span
  m='2143940'>delay</span> <span m='2144270'>branch.</span> <span
  m='2145570'>And</span> <span m='2145590'>then</span> <span
  m='2145950'>we</span> <span m='2146160'>have</span> <span
  m='2146880'>second</span> <span m='2147330'>order</span> <span
  m='2147570'>sections</span> <span m='2149580'>as</span> <span
  m='2149760'>I've</span> <span m='2149910'>indicated</span> <span
  m='2150450'>here,</span> <span m='2151290'>but</span> <span
  m='2151440'>the</span> <span m='2151560'>second</span> <span
  m='2151920'>order</span> <span m='2152160'>sections</span> <span
  m='2153210'>implement</span> <span m='2153870'>only</span> <span
  m='2154230'>a</span> <span m='2154290'>single</span> <span
  m='2154740'>0</span> <span m='2155910'>and</span> <span m='2156540'>a</span>
  <span m='2156630'>pair</span> <span m='2156930'>of</span> <span
  m='2157020'>poles--</span> <span m='2157590'>a</span> <span
  m='2157650'>single</span> <span m='2158010'>0</span> <span
  m='2158700'>and</span> <span m='2158850'>a</span> <span
  m='2158910'>pair</span> <span m='2159180'>of</span> <span
  m='2159400'>poles.</span> </p><p><span m='2161980'>Now,</span> <span
  m='2162670'>why</span> <span m='2163150'>might</span> <span
  m='2163570'>you</span> <span m='2164110'>want</span> <span
  m='2164410'>to</span> <span m='2164530'>use</span> <span m='2164890'>a</span>
  <span m='2164960'>parallel</span> <span m='2165430'>form</span> <span
  m='2166060'>implementation</span> <span m='2167200'>instead</span> <span
  m='2167620'>of</span> <span m='2168070'>a</span> <span
  m='2169480'>cascade</span> <span m='2170020'>form</span> <span
  m='2170350'>implementation?</span> <span m='2171730'>Well,</span> <span
  m='2172180'>there</span> <span m='2172540'>actually</span> <span
  m='2172990'>are</span> <span m='2173080'>several</span> <span
  m='2173530'>reasons.</span> <span m='2174410'>One</span> <span
  m='2174490'>of</span> <span m='2174580'>the</span> <span
  m='2174670'>most</span> <span m='2174910'>common,</span> <span
  m='2175330'>in</span> <span m='2175480'>fact,</span> <span
  m='2176230'>though,</span> <span m='2177520'>is</span> <span
  m='2177700'>that</span> <span m='2178390'>sometimes</span> <span
  m='2179860'>in</span> <span m='2180310'>applying</span> <span
  m='2180790'>filter</span> <span m='2181150'>design</span> <span
  m='2181600'>techniques</span> <span m='2182950'>the</span> <span
  m='2183370'>filter</span> <span m='2185020'>design</span> <span
  m='2185500'>parameters</span> <span m='2186690'>are</span> <span
  m='2188380'>automatically</span> <span m='2189040'>generated</span> <span
  m='2189940'>in</span> <span m='2190090'>a</span> <span
  m='2190150'>parallel</span> <span m='2190750'>form.</span> <span
  m='2191260'>That</span> <span m='2191470'>is,</span> <span
  m='2192400'>rather</span> <span m='2193060'>than</span> <span
  m='2193360'>being</span> <span m='2193600'>generated</span> <span
  m='2194110'>either</span> <span m='2194350'>as</span> <span
  m='2194470'>a</span> <span m='2194530'>ratio</span> <span
  m='2194920'>of</span> <span m='2195040'>polynomials</span> <span
  m='2195910'>or</span> <span m='2196150'>as</span> <span
  m='2196270'>poles</span> <span m='2196630'>and</span> <span
  m='2196750'>0's,</span> <span m='2197890'>it</span> <span
  m='2198010'>might</span> <span m='2198460'>be</span> <span
  m='2198610'>generated</span> <span m='2199390'>in</span> <span
  m='2199540'>terms</span> <span m='2199870'>of</span> <span
  m='2199960'>residues</span> <span m='2200530'>and</span> <span
  m='2200650'>poles.</span> <span m='2201640'>In</span> <span
  m='2201760'>that</span> <span m='2201970'>case,</span> <span
  m='2202270'>of</span> <span m='2202360'>course,</span> <span
  m='2202810'>it's</span> <span m='2202960'>very</span> <span
  m='2203230'>straightforward</span> <span m='2204400'>to</span> <span
  m='2204490'>go</span> <span m='2204730'>to</span> <span m='2204880'>a</span>
  <span m='2204940'>parallel</span> <span m='2205420'>form</span> <span
  m='2205810'>implementation</span> <span m='2207130'>rather</span> <span
  m='2207520'>than</span> <span m='2208090'>a</span> <span
  m='2208360'>cascade</span> <span m='2208990'>form</span> <span
  m='2209290'>implementation.</span> <span m='2210790'>Basically</span> <span
  m='2211360'>the</span> <span m='2211480'>difference</span> <span
  m='2211870'>between</span> <span m='2212230'>the</span> <span
  m='2212320'>two</span> <span m='2212530'>forms</span> <span
  m='2213550'>is</span> <span m='2213670'>that</span> <span
  m='2213820'>the</span> <span m='2213910'>cascade</span> <span
  m='2214540'>form</span> <span m='2216040'>implements</span> <span
  m='2217390'>in</span> <span m='2217480'>terms</span> <span
  m='2217810'>of</span> <span m='2217900'>low</span> <span
  m='2218110'>order</span> <span m='2218320'>sections</span> <span
  m='2219700'>poles</span> <span m='2220210'>and</span> <span
  m='2220360'>0's</span> <span m='2221170'>of</span> <span
  m='2221320'>the</span> <span m='2221410'>system,</span> <span
  m='2222640'>whereas</span> <span m='2223690'>the</span> <span
  m='2223990'>parallel</span> <span m='2224560'>form</span> <span
  m='2225430'>implementation</span> <span m='2227050'>is</span> <span
  m='2227500'>effectively</span> <span m='2228340'>an</span> <span
  m='2228460'>implementation</span> <span m='2229390'>of</span> <span
  m='2229510'>the</span> <span m='2229630'>system</span> <span
  m='2230320'>in</span> <span m='2230440'>terms</span> <span
  m='2230980'>of</span> <span m='2231160'>the</span> <span
  m='2231280'>poles.</span> <span m='2232210'>The</span> <span
  m='2232300'>poles</span> <span m='2232600'>are</span> <span
  m='2232690'>controlled</span> <span m='2233200'>in</span> <span
  m='2233260'>the</span> <span m='2233350'>same</span> <span
  m='2233650'>way</span> <span m='2233980'>as</span> <span
  m='2234130'>they</span> <span m='2234250'>were</span> <span
  m='2234400'>in</span> <span m='2234460'>the</span> <span
  m='2234550'>cascade</span> <span m='2235120'>structure,</span> <span
  m='2236200'>but</span> <span m='2236920'>poles</span> <span
  m='2237370'>and</span> <span m='2237490'>residues</span> <span
  m='2238480'>rather</span> <span m='2238810'>than</span> <span
  m='2238960'>poles</span> <span m='2239320'>and</span> <span
  m='2239450'>0's.</span> </p><p><span m='2241690'>Again,</span> <span
  m='2242050'>with</span> <span m='2242170'>the</span> <span
  m='2242260'>parallel</span> <span m='2242720'>form</span> <span
  m='2243040'>structure,</span> <span m='2243730'>we</span> <span
  m='2243910'>can</span> <span m='2244060'>generate</span> <span
  m='2244510'>other</span> <span m='2244720'>parallel</span> <span
  m='2245200'>form</span> <span m='2245530'>structures</span> <span
  m='2246190'>by</span> <span m='2246460'>considering</span> <span
  m='2247090'>other</span> <span m='2247300'>ways</span> <span
  m='2247840'>of</span> <span m='2247990'>implementing</span> <span
  m='2249070'>the</span> <span m='2249220'>second</span> <span
  m='2249610'>order</span> <span m='2249850'>sections.</span> <span
  m='2250510'>One</span> <span m='2250720'>possibility</span> <span
  m='2251620'>is</span> <span m='2251890'>to</span> <span
  m='2252040'>apply</span> <span m='2252370'>the</span> <span
  m='2252460'>transposition</span> <span m='2253270'>theorem,</span> <span
  m='2254200'>and</span> <span m='2254320'>in</span> <span
  m='2254410'>fact,</span> <span m='2254780'>there</span> <span
  m='2254890'>are</span> <span m='2254920'>other</span> <span
  m='2255130'>implementations</span> <span m='2256180'>of</span> <span
  m='2256330'>second</span> <span m='2256660'>order</span> <span
  m='2256930'>sections,</span> <span m='2259270'>and</span> <span
  m='2259630'>so</span> <span m='2259990'>we</span> <span m='2260140'>can</span>
  <span m='2260290'>talk</span> <span m='2260590'>about</span> <span
  m='2260830'>a</span> <span m='2260860'>variety</span> <span
  m='2261430'>of</span> <span m='2261520'>parallel</span> <span
  m='2261970'>form</span> <span m='2262300'>structures,</span> <span
  m='2263290'>but</span> <span m='2263680'>generally</span> <span
  m='2264430'>when</span> <span m='2264610'>we</span> <span
  m='2264760'>refer</span> <span m='2265120'>to</span> <span
  m='2265690'>a</span> <span m='2265810'>parallel</span> <span
  m='2266320'>form</span> <span m='2266830'>or</span> <span
  m='2266980'>the</span> <span m='2267100'>parallel</span> <span
  m='2267490'>form</span> <span m='2267760'>structures,</span> <span
  m='2268840'>we</span> <span m='2268960'>generally</span> <span
  m='2269470'>mean</span> <span m='2269920'>a</span> <span
  m='2269980'>parallel</span> <span m='2270490'>realization</span> <span
  m='2271360'>of</span> <span m='2271480'>poles</span> <span
  m='2272350'>in</span> <span m='2272440'>terms</span> <span
  m='2272740'>of</span> <span m='2272800'>second</span> <span
  m='2273160'>order</span> <span m='2273370'>sections</span> <span
  m='2274390'>and</span> <span m='2274510'>a weighting</span> <span
  m='2274930'>applied</span> <span m='2275740'>that</span> <span
  m='2275860'>correspond</span> <span m='2276490'>to</span> <span
  m='2276610'>the</span> <span m='2276730'>residues.</span> </p><p><span
  m='2279590'>Now,</span> <span m='2280100'>the</span> <span
  m='2280250'>topic</span> <span m='2280880'>of</span> <span
  m='2281660'>digital</span> <span m='2282020'>filter</span> <span
  m='2282390'>structures</span> <span m='2284420'>is,</span> <span
  m='2284660'>in</span> <span m='2284780'>fact,</span> <span
  m='2285320'>a</span> <span m='2285380'>very</span> <span
  m='2285680'>complicated</span> <span m='2287210'>topic.</span> <span
  m='2288320'>There</span> <span m='2288860'>are</span> <span
  m='2289340'>a</span> <span m='2289460'>lot</span> <span m='2289700'>of</span>
  <span m='2289850'>other</span> <span m='2290450'>filter</span> <span
  m='2290840'>structures</span> <span m='2291710'>which</span> <span
  m='2292190'>can</span> <span m='2292340'>be</span> <span
  m='2292460'>used</span> <span m='2292730'>for</span> <span
  m='2292880'>implementing</span> <span m='2294290'>recursive</span> <span
  m='2295040'>filters,</span> <span m='2295670'>or</span> <span
  m='2295730'>non-recursive</span> <span m='2296480'>filters,</span> <span
  m='2297050'>or</span> <span m='2297950'>a</span> <span
  m='2298250'>finite</span> <span m='2298610'>impulse</span> <span
  m='2299000'>response,</span> <span m='2299540'>or</span> <span
  m='2299630'>infinite</span> <span m='2299960'>impulse</span> <span
  m='2300380'>response.</span> <span m='2301910'>There</span> <span
  m='2302390'>are</span> <span m='2302600'>structures</span> <span
  m='2303170'>referred</span> <span m='2303530'>to</span> <span
  m='2303710'>as</span> <span m='2303800'>continued</span> <span
  m='2304660'>fraction</span> <span m='2305180'>structures.</span> <span
  m='2305870'>There</span> <span m='2306030'>are</span> <span
  m='2306120'>structures</span> <span m='2306590'>referred</span> <span
  m='2306920'>to</span> <span m='2307130'>as</span> <span
  m='2307220'>interpolation</span> <span m='2308570'>structures.</span> <span
  m='2309320'>There are</span> <span m='2309470'>structures</span> <span
  m='2310310'>referred</span> <span m='2310730'>to</span> <span
  m='2310910'>as</span> <span m='2311030'>lattice</span> <span
  m='2311390'>structures,</span> <span m='2311930'>and</span> <span
  m='2312020'>ladder</span> <span m='2312350'>structures,</span> <span
  m='2312970'>et cetera.</span> <span m='2314360'>There</span> <span
  m='2314570'>are</span> <span m='2314750'>a</span> <span
  m='2314780'>large</span> <span m='2315170'>variety</span> <span
  m='2315920'>of</span> <span m='2316010'>structures,</span> <span
  m='2317240'>and</span> <span m='2317360'>in</span> <span
  m='2317450'>fact,</span> <span m='2318060'>one</span> <span
  m='2318230'>of</span> <span m='2318320'>the</span> <span
  m='2318440'>very</span> <span m='2318680'>important</span> <span
  m='2319160'>issues</span> <span m='2319850'>currently</span> <span
  m='2321140'>is</span> <span m='2321770'>the</span> <span
  m='2322550'>design</span> <span m='2323120'>and</span> <span
  m='2323240'>development</span> <span m='2323870'>of</span> <span
  m='2323960'>structures</span> <span m='2324680'>and</span> <span
  m='2324800'>the</span> <span m='2324890'>comparison</span> <span
  m='2325580'>of</span> <span m='2325640'>structures</span> <span
  m='2326750'>in</span> <span m='2326840'>particular</span> <span
  m='2328190'>focusing</span> <span m='2328940'>on</span> <span
  m='2329090'>the</span> <span m='2329180'>trade-offs--</span> <span
  m='2330260'>that</span> <span m='2330440'>is,</span> <span
  m='2330560'>the</span> <span m='2330680'>advantages</span> <span
  m='2331250'>and</span> <span m='2331370'>disadvantages--</span> <span
  m='2332300'>between</span> <span m='2332720'>various</span> <span
  m='2333110'>structures.</span> </p><p><span m='2334720'>The</span> <span
  m='2334850'>structures</span> <span m='2335300'>that</span> <span
  m='2335420'>I've</span> <span m='2335540'>introduced</span> <span
  m='2336080'>here--</span> <span m='2336860'>that</span> <span
  m='2337040'>is,</span> <span m='2337250'>the</span> <span
  m='2337370'>direct</span> <span m='2337700'>form,</span> <span
  m='2338150'>the</span> <span m='2338240'>canonic</span> <span
  m='2338690'>form,</span> <span m='2339560'>cascade,</span> <span
  m='2340160'>and</span> <span m='2340250'>parallel--</span> <span
  m='2341540'>are</span> <span m='2342200'>the</span> <span
  m='2342320'>most</span> <span m='2342620'>common</span> <span
  m='2344060'>structures</span> <span m='2345080'>which</span> <span
  m='2345290'>are</span> <span m='2345410'>used.</span> <span
  m='2346100'>They,</span> <span m='2346520'>in</span> <span
  m='2346640'>fact,</span> <span m='2346970'>tend</span> <span
  m='2347150'>to</span> <span m='2347270'>hold</span> <span
  m='2347540'>up</span> <span m='2347660'>very</span> <span
  m='2347990'>well</span> <span m='2348500'>and</span> <span
  m='2349160'>seem</span> <span m='2349640'>to</span> <span
  m='2349820'>be</span> <span m='2352010'>for</span> <span m='2352190'>a</span>
  <span m='2352220'>variety</span> <span m='2352760'>of</span> <span
  m='2352850'>reasons</span> <span m='2353270'>some</span> <span
  m='2353480'>of</span> <span m='2353570'>the</span> <span
  m='2353660'>more</span> <span m='2353900'>advantageous</span> <span
  m='2354680'>structures.</span> <span m='2356600'>While</span> <span
  m='2357080'>I've</span> <span m='2357320'>presented</span> <span
  m='2357710'>this</span> <span m='2357890'>discussion</span> <span
  m='2361310'>from</span> <span m='2361490'>a</span> <span
  m='2361550'>general</span> <span m='2361910'>point</span> <span
  m='2362240'>of</span> <span m='2362300'>view</span> <span
  m='2363710'>and</span> <span m='2364010'>tended</span> <span
  m='2364340'>to</span> <span m='2364460'>focus</span> <span
  m='2365090'>on</span> <span m='2365570'>infinite</span> <span
  m='2366020'>impulse</span> <span m='2366440'>response</span> <span
  m='2367100'>transfer</span> <span m='2367610'>functions,</span> <span
  m='2368750'>obviously</span> <span m='2369830'>these</span> <span
  m='2370040'>structures</span> <span m='2370790'>can</span> <span
  m='2371000'>be</span> <span m='2371150'>applied</span> <span
  m='2372140'>to</span> <span m='2372500'>finite</span> <span
  m='2373010'>impulse</span> <span m='2373400'>response</span> <span
  m='2374090'>or</span> <span m='2374480'>infinite</span> <span
  m='2375200'>impulse</span> <span m='2375620'>response</span> <span
  m='2376280'>systems.</span> <span m='2377600'>In</span> <span
  m='2377720'>the</span> <span m='2377810'>next</span> <span
  m='2378080'>lecture,</span> <span m='2378860'>I'd</span> <span
  m='2379160'>like</span> <span m='2379400'>to</span> <span
  m='2379700'>continue</span> <span m='2380180'>the</span> <span
  m='2380300'>discussion</span> <span m='2381010'>of</span> <span
  m='2381100'>structures</span> <span m='2382400'>by</span> <span
  m='2383240'>focusing</span> <span m='2384140'>specifically</span> <span
  m='2385550'>on</span> <span m='2385880'>finite</span> <span
  m='2386420'>impulse</span> <span m='2386810'>response</span> <span
  m='2387290'>systems</span> <span m='2388370'>and</span> <span
  m='2389450'>directing</span> <span m='2390080'>our</span> <span
  m='2390230'>attention</span> <span m='2390920'>to</span> <span
  m='2391760'>some</span> <span m='2392120'>specific</span> <span
  m='2392690'>structures</span> <span m='2393710'>that</span> <span
  m='2394400'>apply</span> <span m='2394970'>only</span> <span
  m='2395300'>to</span> <span m='2395420'>find</span> <span
  m='2395730'>an</span> <span m='2395810'>impulse</span> <span
  m='2396230'>response</span> <span m='2397040'>and</span> <span
  m='2397370'>take</span> <span m='2397640'>advantage</span> <span
  m='2398360'>of</span> <span m='2398990'>some</span> <span
  m='2399230'>particular</span> <span m='2399770'>aspects</span> <span
  m='2400460'>of</span> <span m='2400550'>finite</span> <span
  m='2400920'>impulse</span> <span m='2401300'>response</span> <span
  m='2401720'>systems.</span> <span m='2402640'>Thank</span> <span
  m='2402840'>you.</span> </p>
embedded_media:
  - uid: e9b11b2996899c5eecd5ea00b0dd6bb2
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: MITRES_6_008S11_lec12.pdf
    title: MITRES_6_008S11_lec12.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-12-network-structures-for-infinite-impulse-response-iir-systems/MITRES_6_008S11_lec12.pdf
  - uid: 110419c3f820407d70eb66ccd4d23d00
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: mUpwOQ0w2vk
  - uid: abca4256f2bd33312745a20fdaf2bd3f
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-12-network-structures/id481803782?i=108362000
  - uid: 3c8d3693d38ef495281289e8e0afdd49
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec12_300k.mp4'
  - uid: 270139c544ad77d07a386eb8be981edd
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/mUpwOQ0w2vk/default.jpg'
  - uid: e6384472d41c4dfbd8049306e69754a7
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: mUpwOQ0w2vk
  - uid: 5a305fa73257cc7229b6f8bdac4346e6
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: mUpwOQ0w2vk.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-12-network-structures-for-infinite-impulse-response-iir-systems/mUpwOQ0w2vk.srt
  - uid: d59d3798ae54db5d0604e233b870b4b5
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: mUpwOQ0w2vk.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-12-network-structures-for-infinite-impulse-response-iir-systems/mUpwOQ0w2vk.pdf
  - uid: 848453870d7d4ccec77ed6e252acc0e7
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: e61de1e9dc179052642fee79f118e792
    parent_uid: 947bb2fb248d5e3a7fd113ebea673243
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
