---
order_index: null
title: 'Lecture 2: Discrete-Time Signals and Systems, Part 1'
template_type: Tabbed
uid: 3c54b2e23f5a897cbee4f090666b233a
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-2-discrete-time-signals-and-systems-part-1
short_url: lecture-2-discrete-time-signals-and-systems-part-1
inline_embed_id: '84869313lecture2:discrete-timesignalsandsystems,part184096795'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Definitions of basic discrete-time
  signals: The unit sample, unit step, exponential and sinusoidal sequences,
  definitions and representations of linear time-invariant discrete-time
  systems, properties of discrete-time convolution.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Discrete-Time Signals and Systems, Part 1 (<img
  src="/images/inacessible.gif" alt="This resource may not render correctly in a
  screen reader." /><a
  href="./resolveuid/7d2257580e542e72484fb71db7187630">PDF</a>)</p>
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
  m='10980'>donation,</span> <span m='11730'>or</span> <span
  m='11940'>view</span> <span m='12390'>additional</span> <span
  m='12810'>materials</span> <span m='13320'>from</span> <span
  m='13500'>hundreds</span> <span m='13920'>of</span> <span m='14040'>MIT</span>
  <span m='14460'>courses,</span> <span m='15550'>visit</span> <span
  m='15780'>MIT</span> <span m='16200'>OpenCourseWare</span> <span
  m='17280'>at</span> <span m='17430'>ocw.mit.edu.</span> </p><p><span
  m='25400'>[MUSIC PLAYING]</span> </p><p></p><p><span m='57360'>ALAN
  OPPENHEIM:</span> <span m='57510'>Well,</span> <span m='57660'>last</span>
  <span m='57960'>time</span> <span m='58950'>we</span> <span
  m='59370'>had</span> <span m='59580'>discussed,</span> <span
  m='60090'>in</span> <span m='60180'>a</span> <span m='60330'>very</span> <span
  m='60600'>general</span> <span m='61020'>way,</span> <span
  m='61860'>the</span> <span m='62250'>field</span> <span m='62640'>of</span>
  <span m='62730'>digital</span> <span m='63090'>signal</span> <span
  m='63420'>processing,</span> <span m='64800'>and</span> <span
  m='65340'>hopefully</span> <span m='66180'>one</span> <span
  m='66360'>of</span> <span m='66450'>the</span> <span m='66540'>things</span>
  <span m='66960'>that</span> <span m='67260'>you</span> <span
  m='67410'>were</span> <span m='67530'>convinced</span> <span
  m='67785'>of</span> <span m='68400'>was</span> <span m='69480'>the</span>
  <span m='69570'>importance</span> <span m='70440'>of</span> <span
  m='71160'>this</span> <span m='71330'>set</span> <span m='71550'>of</span>
  <span m='71670'>techniques</span> <span m='72480'>in</span> <span
  m='72600'>a</span> <span m='72660'>general</span> <span
  m='73080'>sense.</span> <span m='74230'>What</span> <span
  m='74400'>we'd</span> <span m='74520'>like</span> <span m='74760'>to</span>
  <span m='75000'>begin</span> <span m='75360'>on</span> <span
  m='75570'>now</span> <span m='76080'>is</span> <span m='77400'>a</span> <span
  m='77520'>discussion</span> <span m='78270'>of</span> <span
  m='79140'>some</span> <span m='79380'>of</span> <span m='79440'>the</span>
  <span m='79560'>details</span> <span m='80910'>of</span> <span
  m='81060'>digital</span> <span m='81420'>signal</span> <span
  m='81780'>processing.</span> <span m='83250'>And</span> <span
  m='83580'>in</span> <span m='83700'>particular,</span> <span
  m='84690'>in</span> <span m='84810'>this</span> <span
  m='85020'>lecture,</span> <span m='86620'>I</span> <span
  m='86640'>would</span> <span m='86790'>like</span> <span m='87060'>to</span>
  <span m='87480'>introduce</span> <span m='88320'>the</span> <span
  m='88440'>class</span> <span m='89010'>of</span> <span
  m='89790'>discrete</span> <span m='90180'>time</span> <span
  m='90540'>signals,</span> <span m='91740'>and</span> <span
  m='92040'>also</span> <span m='92490'>the</span> <span m='92610'>class</span>
  <span m='93000'>of</span> <span m='93090'>discrete</span> <span
  m='93450'>time</span> <span m='93750'>systems.</span> </p><p><span
  m='96070'>Well,</span> <span m='96360'>last</span> <span
  m='96750'>time,</span> <span m='97590'>I</span> <span
  m='98610'>reminded</span> <span m='99210'>you</span> <span
  m='99750'>that</span> <span m='101760'>I</span> <span m='102330'>will</span>
  <span m='102510'>be</span> <span m='102660'>assuming</span> <span
  m='103920'>a</span> <span m='105540'>familiarity</span> <span
  m='106650'>with</span> <span m='107190'>continuous</span> <span
  m='107850'>time</span> <span m='108510'>signals</span> <span
  m='109050'>and</span> <span m='109140'>systems.</span> <span
  m='110460'>And</span> <span m='111030'>what</span> <span
  m='111240'>you'll</span> <span m='111420'>see</span> <span
  m='111900'>as</span> <span m='112170'>we</span> <span m='112320'>go</span>
  <span m='112530'>through</span> <span m='112800'>this</span> <span
  m='113040'>lecture--</span> <span m='113580'>and</span> <span
  m='113730'>in</span> <span m='113820'>fact,</span> <span m='114180'>as</span>
  <span m='114300'>we</span> <span m='114420'>go</span> <span
  m='114600'>through</span> <span m='114840'>all</span> <span
  m='115020'>of</span> <span m='115110'>these</span> <span
  m='115290'>lectures--</span> <span m='116460'>is</span> <span
  m='116850'>a</span> <span m='116910'>very</span> <span
  m='117150'>strong</span> <span m='117570'>similarity</span> <span
  m='118710'>between</span> <span m='119670'>the</span> <span
  m='120570'>results</span> <span m='121320'>that</span> <span
  m='121560'>you're</span> <span m='121710'>familiar</span> <span
  m='122190'>with</span> <span m='122590'>in</span> <span m='122700'>the</span>
  <span m='122820'>continuous</span> <span m='123390'>time</span> <span
  m='123720'>case,</span> <span m='125110'>and</span> <span
  m='125490'>results</span> <span m='126060'>that</span> <span
  m='126360'>will</span> <span m='126660'>develop</span> <span
  m='127560'>for</span> <span m='127680'>the</span> <span
  m='127800'>discrete</span> <span m='128190'>time</span> <span
  m='128490'>case.</span> </p><p><span m='129690'>Obviously,</span> <span
  m='130470'>of</span> <span m='130590'>course,</span> <span
  m='131280'>there</span> <span m='131550'>will</span> <span
  m='132000'>also</span> <span m='132450'>be</span> <span m='132930'>some</span>
  <span m='133140'>differences.</span> <span m='134380'>And</span> <span
  m='134610'>these</span> <span m='134790'>differences</span> <span
  m='135630'>are</span> <span m='135810'>important,</span> <span
  m='136500'>and</span> <span m='136830'>they</span> <span
  m='136880'>will</span> <span m='136980'>be</span> <span
  m='137070'>important</span> <span m='137490'>to</span> <span
  m='137610'>focus</span> <span m='138030'>on.</span> <span m='138840'>So</span>
  <span m='139410'>there</span> <span m='139620'>will</span> <span
  m='139800'>be</span> <span m='140880'>a</span> <span m='140970'>great</span>
  <span m='141270'>deal</span> <span m='141510'>of</span> <span
  m='141600'>similarity,</span> <span m='142800'>also</span> <span
  m='143340'>a</span> <span m='143400'>few</span> <span
  m='143640'>differences.</span> <span m='144580'>And</span> <span
  m='144690'>these</span> <span m='144870'>few</span> <span
  m='145020'>differences</span> <span m='145620'>are</span> <span
  m='145680'>very</span> <span m='145950'>important.</span> </p><p><span
  m='148440'>In</span> <span m='149160'>the</span> <span
  m='149400'>discrete</span> <span m='149820'>time</span> <span
  m='150120'>domain,</span> <span m='150930'>we're</span> <span
  m='151200'>concerned</span> <span m='152130'>with</span> <span
  m='152460'>processing</span> <span m='153150'>signals</span> <span
  m='154470'>that</span> <span m='155040'>are</span> <span
  m='155310'>sequences.</span> <span m='156150'>That</span> <span
  m='156390'>is,</span> <span m='157110'>these</span> <span
  m='157290'>signals</span> <span m='158010'>are</span> <span
  m='158310'>functions</span> <span m='159090'>of</span> <span
  m='159330'>an</span> <span m='159450'>integer</span> <span
  m='159870'>variable,</span> <span m='161080'>which</span> <span
  m='161310'>we'll</span> <span m='161520'>call</span> <span
  m='161940'>n.</span> <span m='163650'>Typically,</span> <span
  m='164520'>will</span> <span m='165060'>depict</span> <span
  m='165780'>sequences</span> <span m='166770'>graphically,</span> <span
  m='167730'>as</span> <span m='168150'>I've</span> <span
  m='168330'>illustrated</span> <span m='169560'>here</span> <span
  m='170130'>on</span> <span m='170700'>this</span> <span
  m='170880'>first</span> <span m='171180'>viewgraph,</span> <span
  m='173460'>where</span> <span m='173910'>I've</span> <span
  m='174570'>denoted</span> <span m='175260'>a</span> <span
  m='175350'>general</span> <span m='175800'>sequence--</span> <span
  m='177120'>which</span> <span m='177330'>I</span> <span m='177420'>call</span>
  <span m='177900'>x</span> <span m='178140'>of n--</span> <span
  m='179910'>a</span> <span m='179970'>function</span> <span
  m='180600'>of</span> <span m='180780'>the</span> <span
  m='180900'>energy</span> <span m='181260'>variable</span> <span
  m='181890'>n,</span> <span m='183030'>and</span> <span m='183810'>the</span>
  <span m='184080'>sequence</span> <span m='184620'>values,</span> <span
  m='185430'>I've</span> <span m='185640'>represented</span> <span
  m='186840'>by</span> <span m='187290'>a</span> <span m='187380'>bar</span>
  <span m='187710'>graph</span> <span m='188730'>with</span> <span
  m='189270'>the</span> <span m='189390'>height</span> <span
  m='189720'>of</span> <span m='189900'>each</span> <span m='190140'>bar</span>
  <span m='190890'>corresponding</span> <span m='191820'>to</span> <span
  m='191970'>the</span> <span m='192060'>sequence</span> <span
  m='192540'>value.</span> </p><p><span m='194340'>So</span> <span
  m='195330'>we</span> <span m='195510'>have,</span> <span
  m='196020'>then,</span> <span m='196830'>for</span> <span
  m='197010'>example,</span> <span m='197880'>at</span> <span
  m='198450'>n</span> <span m='198705'>equals</span> <span m='198960'>0,</span>
  <span m='200320'>a</span> <span m='200430'>line</span> <span
  m='200940'>of</span> <span m='201090'>height</span> <span m='201450'>x</span>
  <span m='201740'>of</span> <span m='201870'>0</span> <span
  m='203040'>at</span> <span m='203220'>n</span> <span m='203495'>equals</span>
  <span m='203770'>1</span> <span m='204230'>a line</span> <span
  m='204690'>of</span> <span m='204780'>height</span> <span m='205200'>x</span>
  <span m='205500'>of</span> <span m='205650'>1,</span> <span m='206310'>et
  cetera.</span> <span m='208380'>Of</span> <span m='208440'>course,</span>
  <span m='209250'>as</span> <span m='209700'>I've</span> <span
  m='209880'>drawn</span> <span m='210180'>this</span> <span
  m='210390'>horizontal</span> <span m='211020'>axis,</span> <span
  m='211740'>I've</span> <span m='212250'>drawn</span> <span
  m='212640'>it</span> <span m='213360'>as</span> <span m='213540'>a</span>
  <span m='213600'>continuous</span> <span m='214290'>line,</span> <span
  m='215670'>but</span> <span m='216360'>it's</span> <span
  m='216540'>important</span> <span m='217320'>to</span> <span
  m='217440'>keep</span> <span m='217740'>in</span> <span m='217860'>mind</span>
  <span m='218940'>that</span> <span m='219480'>the</span> <span
  m='219600'>sequences</span> <span m='221010'>only</span> <span
  m='221550'>are</span> <span m='221700'>defined--</span> <span
  m='222600'>or</span> <span m='222810'>only</span> <span m='223110'>make</span>
  <span m='223350'>sense--</span> <span m='224400'>for</span> <span
  m='224580'>integer</span> <span m='224970'>values</span> <span
  m='225510'>of</span> <span m='225600'>the</span> <span
  m='225750'>argument.</span> </p><p><span m='227530'>If</span> <span
  m='227680'>n</span> <span m='227870'>is</span> <span m='228010'>an</span>
  <span m='228130'>integer,</span> <span m='229220'>then</span> <span
  m='229540'>x</span> <span m='229840'>of</span> <span m='229990'>n</span> <span
  m='230650'>makes</span> <span m='230890'>sense.</span> <span
  m='231940'>If</span> <span m='232120'>n</span> <span m='232390'>is</span>
  <span m='232630'>not</span> <span m='232870'>an</span> <span
  m='232990'>integer,</span> <span m='233980'>it's</span> <span
  m='234190'>not</span> <span m='234730'>just</span> <span
  m='235210'>that</span> <span m='236080'>x</span> <span m='236350'>of n</span>
  <span m='237010'>is</span> <span m='237790'>0</span> <span
  m='238570'>or</span> <span m='239080'>something</span> <span
  m='239560'>like</span> <span m='239830'>that,</span> <span
  m='240420'>it's</span> <span m='240820'>simply</span> <span
  m='241390'>that</span> <span m='241660'>x</span> <span m='241930'>of n</span>
  <span m='242200'>is</span> <span m='242320'>not</span> <span
  m='242530'>defined.</span> <span m='243470'>In</span> <span
  m='243490'>other</span> <span m='243700'>words,</span> <span
  m='244550'>x</span> <span m='244720'>of n</span> <span m='245230'>makes</span>
  <span m='245530'>sense,</span> <span m='245950'>or</span> <span
  m='246100'>is</span> <span m='246220'>defined</span> <span
  m='246790'>for</span> <span m='246970'>n</span> <span m='247170'>an</span>
  <span m='247300'>integer,</span> <span m='248260'>and</span> <span
  m='248440'>does</span> <span m='248620'>not</span> <span
  m='248830'>make</span> <span m='249070'>sense,</span> <span
  m='249550'>or</span> <span m='249730'>is</span> <span m='249820'>not</span>
  <span m='250060'>defined,</span> <span m='250780'>if</span> <span
  m='251140'>n</span> <span m='251350'>is</span> <span m='251470'>not</span>
  <span m='251710'>an</span> <span m='251800'>integer.</span> </p><p><span
  m='253940'>So</span> <span m='254470'>this,</span> <span
  m='254800'>then,</span> <span m='255280'>is</span> <span m='255970'>a</span>
  <span m='256240'>graphical</span> <span m='257079'>representation</span> <span
  m='258279'>of</span> <span m='258850'>a</span> <span m='258940'>general</span>
  <span m='259390'>sequence.</span> <span m='261579'>And</span> <span
  m='262180'>just</span> <span m='262600'>as</span> <span m='262960'>in</span>
  <span m='263080'>the</span> <span m='263170'>continuous</span> <span
  m='263800'>time</span> <span m='264160'>case,</span> <span
  m='265430'>we</span> <span m='265510'>have</span> <span m='266200'>a</span>
  <span m='266260'>number</span> <span m='266830'>of</span> <span
  m='267250'>important</span> <span m='267910'>basic</span> <span
  m='268390'>sequences</span> <span m='269680'>that</span> <span
  m='270160'>we</span> <span m='270340'>would</span> <span
  m='270490'>like</span> <span m='270670'>to</span> <span
  m='270790'>focus</span> <span m='271270'>on.</span> </p><p><span
  m='273930'>The</span> <span m='274020'>first</span> <span m='274350'>of</span>
  <span m='274470'>these</span> <span m='275070'>that</span> <span
  m='275190'>I'd</span> <span m='275310'>like</span> <span m='275490'>to</span>
  <span m='275640'>introduce</span> <span m='276480'>is</span> <span
  m='277200'>the</span> <span m='277800'>unit</span> <span
  m='278190'>sample,</span> <span m='279150'>or</span> <span
  m='279540'>impulse</span> <span m='280020'>sequence,</span> <span
  m='281390'>which</span> <span m='282060'>we'll</span> <span
  m='282510'>denote</span> <span m='283110'>by</span> <span
  m='283710'>delta</span> <span m='284130'>of n.</span> <span
  m='285850'>The</span> <span m='285990'>unit</span> <span
  m='286230'>sample</span> <span m='286650'>sequence</span> <span
  m='287310'>is</span> <span m='287490'>a</span> <span
  m='287550'>sequence</span> <span m='288540'>whose</span> <span
  m='288750'>value</span> <span m='289410'>is</span> <span
  m='290250'>unity</span> <span m='291030'>at</span> <span m='291180'>n</span>
  <span m='291330'>equals</span> <span m='291600'>0,</span> <span
  m='293070'>and</span> <span m='293460'>it's</span> <span
  m='293640'>equal</span> <span m='293970'>to</span> <span m='294120'>0</span>
  <span m='294870'>otherwise.</span> <span m='295800'>That</span> <span
  m='296010'>is</span> <span m='296700'>delta</span> <span m='297160'>of
  n</span> <span m='297300'>equals</span> <span m='297660'>1</span> <span
  m='298170'>at</span> <span m='298410'>n</span> <span m='298680'>equals</span>
  <span m='298950'>0,</span> <span m='299910'>and</span> <span
  m='300030'>delta</span> <span m='300460'>of n</span> <span
  m='300840'>is</span> <span m='301050'>equal</span> <span m='301320'>to</span>
  <span m='301440'>0</span> <span m='302260'>for</span> <span
  m='302460'>n</span> <span m='302940'>not</span> <span m='303150'>equal</span>
  <span m='303420'>to</span> <span m='303540'>0.</span> </p><p><span
  m='305660'>The</span> <span m='305750'>unit</span> <span
  m='306050'>sample</span> <span m='306830'>sequence</span> <span
  m='307790'>plays</span> <span m='308210'>the</span> <span
  m='308300'>same</span> <span m='308630'>role</span> <span m='309230'>in</span>
  <span m='309710'>the</span> <span m='309830'>discrete</span> <span
  m='310220'>time</span> <span m='310550'>case</span> <span
  m='311570'>that</span> <span m='311960'>the</span> <span
  m='312110'>unit</span> <span m='312440'>impulse</span> <span
  m='312950'>time</span> <span m='313280'>function</span> <span
  m='313910'>plays</span> <span m='314410'>in</span> <span m='314510'>the</span>
  <span m='314600'>continuous</span> <span m='315170'>time</span> <span
  m='315470'>case.</span> <span m='316400'>Let</span> <span m='316550'>me</span>
  <span m='316700'>just</span> <span m='317180'>mention,</span> <span
  m='317660'>however,</span> <span m='318300'>that</span> <span
  m='318860'>the</span> <span m='318980'>unit</span> <span
  m='319280'>sample</span> <span m='319700'>sequence</span> <span
  m='320720'>is</span> <span m='321410'>very</span> <span
  m='321800'>easily</span> <span m='322280'>defined.</span> <span
  m='323610'>There's</span> <span m='323780'>no</span> <span
  m='324140'>issue</span> <span m='324920'>here</span> <span
  m='325280'>about</span> <span m='325580'>the</span> <span
  m='325670'>definition.</span> <span m='326900'>In</span> <span
  m='326990'>contrast</span> <span m='327710'>with</span> <span
  m='327860'>the</span> <span m='327950'>usual</span> <span
  m='328460'>mathematical</span> <span m='329210'>problems</span> <span
  m='330050'>with</span> <span m='330530'>a</span> <span
  m='330620'>continuous</span> <span m='331190'>time</span> <span
  m='331520'>impulse--</span> <span m='332550'>which</span> <span
  m='332720'>is</span> <span m='333230'>infinitely</span> <span
  m='333800'>big</span> <span m='334670'>at</span> <span m='334820'>the</span>
  <span m='334970'>origin,</span> <span m='335480'>and</span> <span
  m='335570'>0</span> <span m='335900'>every</span> <span
  m='336110'>place</span> <span m='336500'>else,</span> <span
  m='337310'>but</span> <span m='337670'>has</span> <span m='337910'>some</span>
  <span m='338090'>area,</span> <span m='338480'>et cetera.</span> <span
  m='339650'>So</span> <span m='340370'>there's</span> <span m='340550'>a</span>
  <span m='340580'>very</span> <span m='340820'>precise</span> <span
  m='341330'>definition</span> <span m='341960'>here</span> <span
  m='343160'>of</span> <span m='343370'>the</span> <span m='343520'>unit</span>
  <span m='343790'>sample,</span> <span m='344630'>or</span> <span
  m='345110'>unit</span> <span m='345440'>impulse</span> <span
  m='346340'>sequence,</span> <span m='347570'>and</span> <span
  m='347870'>it</span> <span m='347930'>will</span> <span m='348050'>play</span>
  <span m='348320'>a</span> <span m='348410'>role</span> <span
  m='348980'>similar</span> <span m='349640'>to</span> <span
  m='350030'>the</span> <span m='350180'>unit</span> <span
  m='350480'>impulse</span> <span m='351080'>time</span> <span
  m='351380'>function</span> <span m='352030'>in</span> <span
  m='352160'>the</span> <span m='352250'>continuous</span> <span
  m='352850'>time</span> <span m='353150'>case.</span> </p><p><span
  m='355430'>Another</span> <span m='356120'>important</span> <span
  m='356780'>basic</span> <span m='357260'>sequence</span> <span
  m='358850'>is</span> <span m='359480'>the</span> <span m='359600'>unit</span>
  <span m='359880'>step</span> <span m='360200'>sequence,</span> <span
  m='361310'>which</span> <span m='361950'>I'm</span> <span
  m='362150'>denoting</span> <span m='362900'>by</span> <span m='363620'>u
  of</span> <span m='364010'>n.</span> <span m='365180'>And</span> <span
  m='365810'>the</span> <span m='365930'>unit</span> <span
  m='366230'>step</span> <span m='366530'>sequence</span> <span
  m='367220'>is</span> <span m='367400'>equal</span> <span m='367700'>to</span>
  <span m='367850'>unity</span> <span m='369020'>for</span> <span
  m='369470'>n</span> <span m='370550'>greater</span> <span
  m='370940'>than</span> <span m='371300'>or</span> <span
  m='371450'>equal</span> <span m='371780'>to</span> <span m='371900'>0,</span>
  <span m='373100'>and</span> <span m='373490'>is</span> <span
  m='373640'>equal</span> <span m='373910'>to</span> <span m='374060'>0</span>
  <span m='375080'>for</span> <span m='375560'>n</span> <span
  m='376160'>less</span> <span m='376430'>than</span> <span m='376610'>0.</span>
  <span m='378980'>So</span> <span m='379670'>the</span> <span
  m='379790'>unit</span> <span m='380090'>step</span> <span
  m='380600'>sequence,</span> <span m='381200'>then,</span> <span
  m='381620'>is</span> <span m='382330'>0</span> <span m='382960'>for</span>
  <span m='383240'>n</span> <span m='383420'>less</span> <span
  m='383690'>than</span> <span m='383870'>0,</span> <span m='384680'>it's</span>
  <span m='384890'>unity</span> <span m='386510'>four</span> <span
  m='386810'>n</span> <span m='387350'>greater</span> <span
  m='387710'>than</span> <span m='388100'>or</span> <span
  m='388280'>equal</span> <span m='388580'>to</span> <span m='388700'>0.</span>
  <span m='390890'>This</span> <span m='391160'>shouldn't</span> <span
  m='391460'>be,</span> <span m='391730'>incidentally,</span> <span
  m='392240'>less</span> <span m='392480'>than</span> <span m='392630'>or</span>
  <span m='392720'>equal</span> <span m='392990'>to</span> <span
  m='393110'>0,</span> <span m='393560'>this</span> <span
  m='393700'>should</span> <span m='393920'>be</span> <span m='394220'>n</span>
  <span m='394760'>less</span> <span m='395000'>than</span> <span
  m='395150'>0.</span> </p><p><span m='396590'>And</span> <span
  m='397850'>it</span> <span m='398330'>is--</span> <span
  m='398900'>again,</span> <span m='399620'>does</span> <span
  m='399800'>not</span> <span m='400040'>have</span> <span m='400760'>the</span>
  <span m='402410'>difficulties</span> <span m='403160'>in</span> <span
  m='403250'>definition</span> <span m='404300'>that</span> <span
  m='404550'>a</span> <span m='404630'>continuous</span> <span
  m='405290'>time</span> <span m='405890'>unit</span> <span
  m='406210'>step</span> <span m='406730'>normally</span> <span
  m='407180'>has.</span> <span m='409170'>It's</span> <span
  m='409960'>the</span> <span m='410060'>change</span> <span
  m='410510'>in</span> <span m='410630'>value</span> <span
  m='411200'>from</span> <span m='411580'>n</span> <span
  m='411730'>equals</span> <span m='412010'>minus</span> <span
  m='412430'>1</span> <span m='413090'>to</span> <span m='413250'>n</span> <span
  m='413420'>equals</span> <span m='413690'>0</span> <span m='414710'>is</span>
  <span m='415040'>precisely</span> <span m='415850'>and</span> <span
  m='415940'>easily</span> <span m='416330'>defined.</span> <span
  m='417590'>Here</span> <span m='417830'>the</span> <span
  m='417950'>unit</span> <span m='418220'>step</span> <span m='418520'>is</span>
  <span m='418600'>0,</span> <span m='419390'>here</span> <span
  m='419540'>the</span> <span m='419660'>unit</span> <span
  m='419940'>step</span> <span m='420230'>is</span> <span m='420410'>1.</span>
  <span m='421520'>There's</span> <span m='421730'>no</span> <span
  m='422000'>issue,</span> <span m='422610'>as</span> <span
  m='422660'>there</span> <span m='422870'>is</span> <span m='423050'>in</span>
  <span m='423140'>the</span> <span m='423200'>continuous</span> <span
  m='423740'>time</span> <span m='424040'>case,</span> <span
  m='424850'>about</span> <span m='425180'>discontinuity.</span> </p><p><span
  m='428680'>Just</span> <span m='429010'>as</span> <span m='429370'>in</span>
  <span m='429490'>the</span> <span m='429580'>continuous</span> <span
  m='430180'>time</span> <span m='430510'>case,</span> <span
  m='431100'>there</span> <span m='431290'>is</span> <span m='431410'>a</span>
  <span m='431500'>simple</span> <span m='431860'>relationship</span> <span
  m='432940'>between</span> <span m='433840'>the</span> <span
  m='434740'>unit</span> <span m='435070'>sample,</span> <span
  m='436810'>or</span> <span m='437350'>a</span> <span m='437440'>unit</span>
  <span m='437770'>impulse,</span> <span m='438520'>and</span> <span
  m='438670'>the</span> <span m='438760'>unit</span> <span
  m='439100'>step.</span> <span m='440020'>In</span> <span m='440130'>a</span>
  <span m='440230'>discrete</span> <span m='440650'>time</span> <span
  m='440980'>case,</span> <span m='441460'>there</span> <span
  m='441580'>is</span> <span m='441670'>likewise</span> <span
  m='442420'>a</span> <span m='442480'>simple</span> <span
  m='442870'>relationship</span> <span m='444100'>between</span> <span
  m='444790'>the</span> <span m='444910'>unit</span> <span
  m='445180'>sample</span> <span m='445780'>sequence,</span> <span
  m='446650'>and</span> <span m='447160'>the</span> <span m='447280'>unit</span>
  <span m='447560'>step</span> <span m='447850'>sequence.</span> <span
  m='449530'>In</span> <span m='449620'>particular,</span> <span
  m='450580'>the</span> <span m='451480'>unit</span> <span
  m='451840'>sample</span> <span m='452260'>sequence</span> <span
  m='453220'>can</span> <span m='453370'>be</span> <span
  m='453550'>obtained</span> <span m='454000'>from</span> <span
  m='454270'>the</span> <span m='455000'>unit</span> <span
  m='455360'>step</span> <span m='455890'>sequence</span> <span
  m='457210'>by</span> <span m='457660'>constructing</span> <span
  m='458650'>the</span> <span m='458770'>first</span> <span
  m='459100'>difference.</span> <span m='461370'>The</span> <span
  m='461500'>unit</span> <span m='461770'>sample</span> <span
  m='462190'>sequence,</span> <span m='462580'>delta</span> <span
  m='463250'>of</span> <span m='463470'>n,</span> <span m='464410'>is</span>
  <span m='464620'>equal</span> <span m='465070'>to</span> <span
  m='465885'>u</span> <span m='466160'>of</span> <span m='466410'>n,</span>
  <span m='467050'>the</span> <span m='467190'>unit</span> <span
  m='467510'>step,</span> <span m='468310'>minus</span> <span
  m='469140'>the</span> <span m='469240'>unit</span> <span
  m='469570'>step</span> <span m='470170'>delayed</span> <span
  m='470710'>by</span> <span m='471250'>1</span> <span m='471490'>sample.</span>
  </p><p><span m='472690'>And</span> <span m='472840'>we</span> <span
  m='472960'>can</span> <span m='473110'>see</span> <span m='473920'>that</span>
  <span m='474160'>that</span> <span m='474400'>obviously</span> <span
  m='475030'>is</span> <span m='475150'>the</span> <span m='475240'>case,</span>
  <span m='475910'>if</span> <span m='475990'>we</span> <span
  m='476110'>look</span> <span m='476410'>at</span> <span m='477070'>the</span>
  <span m='477160'>unit</span> <span m='477410'>step</span> <span
  m='477700'>sequence,</span> <span m='478210'>u</span> <span
  m='478450'>of</span> <span m='478610'>n.</span> <span m='479740'>Here</span>
  <span m='480190'>we</span> <span m='480400'>have</span> <span
  m='480910'>the</span> <span m='481060'>unit</span> <span
  m='481360'>step</span> <span m='481660'>sequence</span> <span
  m='482500'>delayed</span> <span m='482890'>by</span> <span
  m='483130'>1--</span> <span m='484000'>so</span> <span m='484180'>this</span>
  <span m='484600'>occurs</span> <span m='485020'>at</span> <span
  m='485110'>n</span> <span m='485300'>equals</span> <span m='485470'>0,</span>
  <span m='486250'>this</span> <span m='486460'>is</span> <span
  m='486770'>n</span> <span m='486970'>equals</span> <span m='487460'>1.</span>
  <span m='488132'>And</span> <span m='488470'>clearly,</span> <span
  m='489220'>the</span> <span m='489340'>difference</span> <span
  m='489790'>between</span> <span m='490300'>those</span> <span
  m='490600'>two</span> <span m='491520'>will</span> <span
  m='491650'>generate</span> <span m='492430'>a</span> <span
  m='492490'>sample</span> <span m='493000'>at</span> <span m='493120'>n</span>
  <span m='493340'>equals</span> <span m='493560'>0,</span> <span
  m='494920'>0,</span> <span m='495370'>of</span> <span
  m='495490'>course,</span> <span m='495910'>for</span> <span
  m='496090'>n</span> <span m='496240'>less</span> <span m='496510'>than</span>
  <span m='496660'>0,</span> <span m='497710'>and</span> <span
  m='498310'>0,</span> <span m='498970'>likewise,</span> <span
  m='499600'>for</span> <span m='499780'>n</span> <span
  m='499930'>greater</span> <span m='500260'>than</span> <span
  m='500470'>0,</span> <span m='501250'>because</span> <span
  m='502090'>these</span> <span m='502270'>sequence</span> <span
  m='502780'>values</span> <span m='503260'>will</span> <span
  m='503380'>be</span> <span m='503530'>canceled</span> <span
  m='504010'>out</span> <span m='504640'>by</span> <span m='504790'>those</span>
  <span m='505060'>sequence</span> <span m='505510'>values.</span> </p><p><span
  m='506740'>So</span> <span m='507670'>the</span> <span m='507790'>unit</span>
  <span m='508030'>sample</span> <span m='508450'>sequence</span> <span
  m='509230'>is</span> <span m='509950'>the</span> <span m='510040'>unit</span>
  <span m='510340'>step</span> <span m='510910'>minus</span> <span
  m='511780'>the</span> <span m='511960'>delayed</span> <span
  m='512230'>unit</span> <span m='512530'>step,</span> <span
  m='513010'>or</span> <span m='513720'>the</span> <span m='513820'>unit</span>
  <span m='514059'>sample</span> <span m='514450'>sequence</span> <span
  m='515110'>is</span> <span m='515320'>equal</span> <span m='515679'>to</span>
  <span m='516309'>the</span> <span m='516400'>first</span> <span
  m='516730'>difference</span> <span m='517330'>of</span> <span
  m='517480'>the</span> <span m='517570'>unit</span> <span
  m='517850'>step</span> <span m='518140'>sequence.</span> </p><p><span
  m='520150'>Similarly,</span> <span m='521110'>we</span> <span
  m='521320'>can</span> <span m='521830'>obtain</span> <span
  m='522250'>the</span> <span m='522340'>unit</span> <span
  m='522659'>step</span> <span m='522970'>sequence</span> <span
  m='523929'>from</span> <span m='524680'>the</span> <span
  m='524800'>unit</span> <span m='525070'>sample</span> <span
  m='525490'>sequence</span> <span m='526600'>by</span> <span
  m='526780'>constructing</span> <span m='527620'>a</span> <span
  m='527710'>running</span> <span m='528070'>sum.</span> <span
  m='530190'>In</span> <span m='530290'>particular,</span> <span
  m='531930'>the</span> <span m='532060'>unit</span> <span
  m='532540'>step</span> <span m='532960'>sequence</span> <span
  m='533950'>is</span> <span m='534130'>equal</span> <span m='534550'>to</span>
  <span m='535280'>a</span> <span m='535400'>running</span> <span
  m='535780'>sum</span> <span m='536890'>of</span> <span m='537640'>the</span>
  <span m='537730'>unit</span> <span m='538030'>sample</span> <span
  m='538480'>sequence.</span> <span m='539980'>In</span> <span
  m='540100'>other</span> <span m='540310'>words,</span> <span
  m='540860'>we're</span> <span m='540940'>constructing</span> <span
  m='541630'>here</span> <span m='541990'>a</span> <span m='542050'>sum</span>
  <span m='542650'>from</span> <span m='542860'>k equals</span> <span
  m='543370'>minus</span> <span m='543730'>infinity</span> <span
  m='544720'>to</span> <span m='544840'>the</span> <span
  m='546130'>independent</span> <span m='546640'>variable</span> <span
  m='547450'>n</span> <span m='548750'>of</span> <span m='549070'>the</span>
  <span m='549160'>sequence,</span> <span m='550060'>delta</span> <span
  m='550390'>of</span> <span m='550570'>k.</span> </p><p><span
  m='552280'>Here</span> <span m='552520'>we</span> <span m='552700'>have</span>
  <span m='553300'>the</span> <span m='553390'>sequence,</span> <span
  m='553870'>delta</span> <span m='554230'>of</span> <span m='554380'>k.</span>
  <span m='556060'>If</span> <span m='556390'>n</span> <span
  m='556900'>is</span> <span m='557680'>less</span> <span m='558010'>than</span>
  <span m='558190'>0,</span> <span m='559240'>then</span> <span
  m='559600'>we're</span> <span m='559870'>adding</span> <span
  m='560230'>up</span> <span m='560380'>sequence</span> <span
  m='560920'>values</span> <span m='562000'>from</span> <span
  m='562150'>minus</span> <span m='562540'>infinity</span> <span
  m='563620'>to</span> <span m='564010'>some</span> <span
  m='564280'>negative</span> <span m='565060'>value</span> <span
  m='565510'>of</span> <span m='565630'>k.</span> <span m='567160'>And</span>
  <span m='567760'>the</span> <span m='567880'>only</span> <span
  m='568120'>values</span> <span m='568540'>that</span> <span
  m='568690'>we</span> <span m='568840'>collect</span> <span
  m='569260'>when</span> <span m='569380'>we</span> <span m='569500'>do</span>
  <span m='569680'>that</span> <span m='570040'>are</span> <span
  m='570160'>values</span> <span m='570610'>equal</span> <span
  m='570880'>to</span> <span m='571000'>0.</span> <span m='572230'>So</span>
  <span m='572710'>for</span> <span m='572890'>n</span> <span
  m='573070'>less</span> <span m='573340'>than</span> <span m='573490'>0,</span>
  <span m='574120'>we</span> <span m='574270'>see</span> <span
  m='574660'>that</span> <span m='575320'>we</span> <span
  m='575470'>obtain</span> <span m='576520'>0</span> <span m='577270'>for</span>
  <span m='577390'>this</span> <span m='577600'>sum.</span> <span
  m='578770'>If</span> <span m='578920'>n</span> <span m='579070'>is</span>
  <span m='579220'>greater</span> <span m='579640'>than</span> <span
  m='579820'>0,</span> <span m='580510'>as</span> <span m='580660'>I've</span>
  <span m='580840'>indicated</span> <span m='581440'>here,</span> <span
  m='582700'>then</span> <span m='583330'>the</span> <span
  m='583450'>sum,</span> <span m='584140'>as</span> <span m='584350'>we</span>
  <span m='584470'>collect</span> <span m='584860'>sequence</span> <span
  m='585400'>values</span> <span m='585910'>from</span> <span
  m='586090'>minus</span> <span m='586450'>infinity</span> <span
  m='587140'>up</span> <span m='587290'>to</span> <span m='587470'>n,</span>
  <span m='588490'>we</span> <span m='588610'>collect</span> <span
  m='589180'>1</span> <span m='589780'>non-0</span> <span
  m='590470'>sequence</span> <span m='591010'>value</span> <span
  m='591940'>which</span> <span m='592120'>is</span> <span
  m='592240'>equal</span> <span m='592540'>to</span> <span m='592720'>1.</span>
  <span m='593440'>Consequently</span> <span m='594160'>for</span> <span
  m='594370'>n</span> <span m='594520'>greater</span> <span
  m='594850'>than</span> <span m='595030'>0,</span> <span m='596110'>we</span>
  <span m='596290'>obtain,</span> <span m='596840'>in</span> <span
  m='596950'>this</span> <span m='597310'>running</span> <span
  m='597640'>sum,</span> <span m='598450'>u of</span> <span m='598660'>n</span>
  <span m='598990'>equal</span> <span m='599230'>to</span> <span
  m='599380'>1.</span> </p><p><span m='600790'>This</span> <span
  m='601390'>plays</span> <span m='601690'>a</span> <span
  m='601780'>role,</span> <span m='602380'>this</span> <span
  m='602560'>running</span> <span m='602860'>sum</span> <span
  m='603130'>plays</span> <span m='603430'>a</span> <span
  m='603490'>role,</span> <span m='604600'>similar</span> <span
  m='605440'>to</span> <span m='605800'>the</span> <span
  m='605980'>integral</span> <span m='606580'>in</span> <span
  m='606700'>the</span> <span m='606790'>continuous</span> <span
  m='607360'>time</span> <span m='607690'>case.</span> <span
  m='608720'>And</span> <span m='609100'>so</span> <span m='609280'>now</span>
  <span m='609490'>we</span> <span m='609670'>have</span> <span
  m='610150'>a</span> <span m='610240'>relationship</span> <span
  m='611020'>between</span> <span m='611410'>the</span> <span
  m='611470'>unit</span> <span m='611770'>sample</span> <span
  m='612160'>sequence,</span> <span m='612970'>and</span> <span
  m='613060'>the</span> <span m='613150'>unit</span> <span
  m='613420'>step</span> <span m='613720'>sequence.</span> </p><p><span
  m='616250'>There</span> <span m='616510'>are</span> <span
  m='616720'>other</span> <span m='616960'>basic</span> <span
  m='617410'>sequences</span> <span m='618190'>that</span> <span
  m='618490'>will</span> <span m='618970'>play</span> <span m='619240'>an</span>
  <span m='619360'>important</span> <span m='619810'>role,</span> <span
  m='620830'>just</span> <span m='621130'>as</span> <span m='621280'>they</span>
  <span m='621430'>do</span> <span m='621880'>in</span> <span
  m='622090'>the</span> <span m='622180'>continuous</span> <span
  m='622780'>time</span> <span m='623110'>case.</span> <span
  m='625660'>In</span> <span m='625780'>particular,</span> <span
  m='627080'>we</span> <span m='627160'>have</span> <span m='627850'>the</span>
  <span m='628210'>real</span> <span m='628840'>exponential</span> <span
  m='629860'>sequence.</span> <span m='632110'>The</span> <span
  m='632270'>sequence</span> <span m='633280'>x</span> <span m='633600'>of
  n</span> <span m='634090'>is</span> <span m='634300'>equal</span> <span
  m='634660'>to</span> <span m='635530'>alpha</span> <span m='636430'>to</span>
  <span m='636550'>the</span> <span m='636730'>n.</span> <span
  m='638560'>I've</span> <span m='638710'>depicted</span> <span
  m='639640'>the</span> <span m='639880'>exponential</span> <span
  m='640540'>sequence</span> <span m='641050'>here</span> <span
  m='642040'>for</span> <span m='642640'>the</span> <span m='642760'>case</span>
  <span m='643240'>in</span> <span m='643390'>which</span> <span
  m='644350'>alpha</span> <span m='645190'>is</span> <span
  m='645520'>positive</span> <span m='646270'>but</span> <span
  m='646450'>less</span> <span m='646750'>than</span> <span
  m='646900'>unity,</span> <span m='648040'>so</span> <span
  m='648280'>that</span> <span m='649120'>as</span> <span m='649520'>n</span>
  <span m='649890'>increases,</span> <span m='651320'>the</span> <span
  m='651340'>exponential</span> <span m='652540'>decreases.</span> </p><p><span
  m='653710'>So</span> <span m='654130'>alpha</span> <span m='654490'>to</span>
  <span m='654640'>the</span> <span m='654790'>n,</span> <span
  m='655030'>if</span> <span m='655210'>alpha</span> <span m='655750'>is</span>
  <span m='655930'>between</span> <span m='656350'>0</span> <span
  m='656830'>and</span> <span m='656950'>1,</span> <span
  m='657910'>decreases</span> <span m='658600'>with</span> <span
  m='658750'>increasing</span> <span m='659100'>n.</span> <span
  m='660280'>If</span> <span m='660430'>alpha</span> <span m='661030'>is</span>
  <span m='661240'>greater</span> <span m='661630'>than</span> <span
  m='661840'>1,</span> <span m='662560'>then</span> <span m='662740'>the</span>
  <span m='662830'>exponential</span> <span m='663400'>sequence</span> <span
  m='663910'>grows,</span> <span m='664510'>of</span> <span
  m='664600'>course,</span> <span m='664900'>exponentially.</span> </p><p><span
  m='667660'>We</span> <span m='668050'>have,</span> <span
  m='668470'>also,</span> <span m='669370'>the</span> <span
  m='669880'>sinusoidal</span> <span m='670630'>sequence.</span> <span
  m='672640'>The</span> <span m='672820'>general</span> <span
  m='673240'>form</span> <span m='673630'>of</span> <span m='673720'>the</span>
  <span m='673810'>sinusoidal</span> <span m='674530'>sequence</span> <span
  m='675220'>is</span> <span m='676030'>x</span> <span m='676300'>of</span>
  <span m='676420'>n</span> <span m='676750'>is</span> <span
  m='676960'>equal</span> <span m='677350'>to</span> <span m='677710'>a</span>
  <span m='678490'>cosine</span> <span m='679160'>omega</span> <span
  m='679540'>0</span> <span m='679990'>n</span> <span m='680710'>plus</span>
  <span m='681110'>phi--</span> <span m='681730'>phi</span> <span
  m='682060'>a</span> <span m='682130'>phase</span> <span
  m='682510'>angle,</span> <span m='683400'>omega</span> <span
  m='683770'>0</span> <span m='684520'>we'll</span> <span
  m='684730'>refer</span> <span m='685090'>to</span> <span m='685330'>as</span>
  <span m='685450'>the</span> <span m='685540'>frequency,</span> <span
  m='686740'>a,</span> <span m='687100'>of</span> <span
  m='687250'>course,</span> <span m='687820'>is</span> <span
  m='687970'>the</span> <span m='688150'>amplitude.</span> <span
  m='689500'>I've</span> <span m='689620'>illustrated</span> <span
  m='690730'>a</span> <span m='691000'>sinusoidal</span> <span
  m='691750'>sequence</span> <span m='692350'>here</span> <span
  m='693640'>for</span> <span m='694020'>a</span> <span
  m='694090'>particular</span> <span m='694600'>choice</span> <span
  m='694990'>of</span> <span m='695080'>omega</span> <span m='695450'>0</span>
  <span m='695890'>and</span> <span m='696040'>phi,</span> <span
  m='696940'>namely</span> <span m='697240'>omega</span> <span
  m='697610'>0</span> <span m='697960'>equal</span> <span m='698200'>to</span>
  <span m='698320'>pi</span> <span m='698590'>over</span> <span
  m='698830'>4,</span> <span m='699310'>and</span> <span m='699430'>phi</span>
  <span m='699700'>equal</span> <span m='699910'>minus</span> <span
  m='700390'>pi</span> <span m='700690'>over</span> <span m='700990'>8.</span>
  </p><p><span m='702580'>And</span> <span m='703090'>in</span> <span
  m='703660'>looking</span> <span m='704260'>at</span> <span
  m='704410'>this,</span> <span m='705080'>we</span> <span m='705160'>see</span>
  <span m='705730'>that</span> <span m='706480'>we</span> <span
  m='706630'>get</span> <span m='707590'>a</span> <span
  m='707860'>periodic</span> <span m='708880'>sequence</span> <span
  m='709990'>that</span> <span m='710170'>is,</span> <span m='710410'>for</span>
  <span m='710560'>this</span> <span m='710770'>choice</span> <span
  m='711130'>of</span> <span m='711220'>parameters,</span> <span
  m='712420'>this</span> <span m='712560'>sequence</span> <span
  m='713200'>is</span> <span m='713350'>periodic.</span> <span
  m='715390'>However,</span> <span m='715900'>an</span> <span
  m='715990'>important</span> <span m='716410'>distinction</span> <span
  m='717250'>between</span> <span m='717670'>the</span> <span
  m='717760'>continuous</span> <span m='718390'>time</span> <span
  m='718690'>case</span> <span m='719390'>and</span> <span m='719490'>the</span>
  <span m='719590'>discrete</span> <span m='719890'>time</span> <span
  m='720250'>case,</span> <span m='721330'>is</span> <span
  m='721570'>that</span> <span m='722350'>a</span> <span
  m='722590'>discrete</span> <span m='723070'>time</span> <span
  m='723610'>sinusoidal</span> <span m='724510'>signal</span> <span
  m='725590'>is</span> <span m='725770'>not</span> <span
  m='726310'>necessarily</span> <span m='727210'>periodic.</span> </p><p><span
  m='729070'>Particular,</span> <span m='729910'>I've</span> <span
  m='730120'>illustrated</span> <span m='730750'>here</span> <span
  m='731260'>another</span> <span m='731830'>sinusoidal</span> <span
  m='732580'>sequence</span> <span m='733840'>with</span> <span
  m='734260'>a</span> <span m='734350'>different</span> <span
  m='734710'>choice</span> <span m='735130'>for</span> <span
  m='735280'>omega</span> <span m='735680'>0</span> <span m='736270'>and</span>
  <span m='736420'>phi.</span> <span m='737560'>In</span> <span
  m='737680'>this</span> <span m='737890'>case,</span> <span
  m='738980'>omega</span> <span m='739440'>0</span> <span
  m='739840'>equal</span> <span m='740110'>to</span> <span m='740230'>3</span>
  <span m='740470'>pi</span> <span m='740800'>over</span> <span
  m='741040'>7.</span> <span m='742840'>With</span> <span m='743020'>that</span>
  <span m='743200'>choice</span> <span m='743560'>of</span> <span
  m='743650'>omega</span> <span m='744010'>0,</span> <span
  m='744850'>these</span> <span m='745120'>are</span> <span
  m='745210'>the</span> <span m='745330'>sequence</span> <span
  m='745780'>values</span> <span m='746530'>we</span> <span
  m='746710'>obtain.</span> <span m='747760'>And</span> <span
  m='748330'>it</span> <span m='748480'>should</span> <span m='748660'>be</span>
  <span m='748840'>obvious</span> <span m='749560'>by</span> <span
  m='749980'>examining</span> <span m='750880'>this</span> <span
  m='751000'>sequence</span> <span m='751990'>that</span> <span
  m='752500'>this</span> <span m='752680'>sequence</span> <span
  m='753340'>is</span> <span m='753490'>no</span> <span m='753670'>longer</span>
  <span m='754000'>periodic,</span> <span m='755170'>whereas</span> <span
  m='755920'>this</span> <span m='756070'>sequence</span> <span
  m='756610'>was.</span> </p><p><span m='757930'>So</span> <span
  m='758740'>the</span> <span m='758860'>sinusoidal</span> <span
  m='759490'>sequence</span> <span m='760270'>may</span> <span
  m='760480'>or</span> <span m='760570'>may</span> <span m='760720'>not</span>
  <span m='760960'>be</span> <span m='761110'>periodic.</span> <span
  m='762190'>Of</span> <span m='762310'>course,</span> <span
  m='763150'>let</span> <span m='763300'>me</span> <span
  m='763420'>remind</span> <span m='763870'>you</span> <span
  m='763990'>that</span> <span m='764230'>if</span> <span m='764440'>n</span>
  <span m='764680'>was</span> <span m='764890'>allowed</span> <span
  m='765310'>to</span> <span m='765460'>vary</span> <span
  m='766780'>continuously--</span> <span m='767690'>if</span> <span
  m='767800'>it</span> <span m='767860'>was</span> <span m='768010'>not</span>
  <span m='768220'>an</span> <span m='768340'>integer</span> <span
  m='768700'>variable--</span> <span m='769780'>x of</span> <span
  m='770050'>n</span> <span m='770620'>would</span> <span m='770830'>be</span>
  <span m='770980'>periodic.</span> <span m='772290'>The</span> <span
  m='772420'>periodicity</span> <span m='773560'>is</span> <span
  m='773770'>lost</span> <span m='774550'>because</span> <span
  m='775180'>n</span> <span m='775660'>is</span> <span m='775870'>now</span>
  <span m='776140'>constrained</span> <span m='776800'>to</span> <span
  m='776920'>be</span> <span m='777370'>an</span> <span
  m='777520'>integer</span> <span m='777850'>variable.</span> <span
  m='779710'>And</span> <span m='780220'>that</span> <span m='780520'>is</span>
  <span m='780670'>one</span> <span m='780850'>of</span> <span
  m='780940'>the</span> <span m='781060'>important</span> <span
  m='781480'>distinctions</span> <span m='782440'>between</span> <span
  m='782920'>continuous</span> <span m='783520'>time</span> <span
  m='784180'>signals</span> <span m='784660'>and</span> <span
  m='784750'>systems,</span> <span m='785380'>and</span> <span
  m='785500'>discrete</span> <span m='785890'>time</span> <span
  m='786310'>signals</span> <span m='786790'>and</span> <span
  m='786880'>systems.</span> </p><p><span m='788500'>Another</span> <span
  m='789040'>point</span> <span m='789490'>which</span> <span
  m='790030'>I'll</span> <span m='790990'>suggest</span> <span
  m='792100'>now,</span> <span m='793120'>although</span> <span
  m='794080'>it's</span> <span m='794260'>a</span> <span m='794330'>point</span>
  <span m='794680'>that</span> <span m='795000'>I'll</span> <span
  m='795220'>want</span> <span m='795460'>to</span> <span
  m='795520'>refer</span> <span m='795850'>to</span> <span m='797020'>in</span>
  <span m='797170'>more</span> <span m='797350'>detail</span> <span
  m='798100'>in</span> <span m='798760'>some</span> <span m='799120'>of</span>
  <span m='799270'>the</span> <span m='799480'>future</span> <span
  m='799870'>lectures,</span> <span m='801400'>is</span> <span
  m='801880'>that</span> <span m='802750'>the</span> <span
  m='802870'>sinusoidal</span> <span m='803890'>sequence</span> <span
  m='808120'>is</span> <span m='809050'>only</span> <span
  m='809890'>distinguishable</span> <span m='811480'>as</span> <span
  m='811900'>omega</span> <span m='812380'>0</span> <span m='813280'>runs</span>
  <span m='814030'>from</span> <span m='815220'>over</span> <span
  m='815470'>the</span> <span m='815590'>range</span> <span m='815980'>0</span>
  <span m='816370'>to</span> <span m='816520'>2</span> <span
  m='816730'>pi</span> <span m='817240'>or</span> <span m='817690'>minus</span>
  <span m='818080'>pi</span> <span m='818320'>to</span> <span
  m='818440'>pi.</span> <span m='820060'>If</span> <span m='820240'>omega</span>
  <span m='820700'>0--</span> <span m='821570'>if</span> <span
  m='821620'>we</span> <span m='821740'>were</span> <span m='822250'>to</span>
  <span m='822400'>replace</span> <span m='822880'>omega</span> <span
  m='823240'>0</span> <span m='823960'>by</span> <span m='824410'>omega</span>
  <span m='824860'>0</span> <span m='825340'>plus</span> <span
  m='825640'>2</span> <span m='825850'>pi,</span> <span m='827690'>then</span>
  <span m='828070'>we</span> <span m='828220'>would</span> <span
  m='828340'>have</span> <span m='828550'>in</span> <span m='828640'>this</span>
  <span m='828850'>argument</span> <span m='829450'>omega</span> <span
  m='829840'>0</span> <span m='830230'>n</span> <span m='830560'>plus</span>
  <span m='830830'>2</span> <span m='831070'>pi</span> <span
  m='831560'>n.</span> <span m='832180'>The</span> <span m='832270'>2</span>
  <span m='832480'>pi</span> <span m='832840'>n,</span> <span
  m='832990'>of</span> <span m='833080'>course,</span> <span
  m='833380'>would</span> <span m='833500'>have</span> <span
  m='833710'>no</span> <span m='833890'>effect,</span> <span
  m='834370'>and</span> <span m='834490'>we'd</span> <span m='834640'>end</span>
  <span m='834850'>up</span> <span m='835030'>with</span> <span
  m='835120'>the</span> <span m='835210'>same</span> <span
  m='835480'>sequence.</span> </p><p><span m='836480'>So</span> <span
  m='836890'>in</span> <span m='837010'>fact</span> <span m='837370'>as,</span>
  <span m='837520'>we</span> <span m='837670'>varied</span> <span
  m='838150'>omega</span> <span m='838540'>0</span> <span
  m='839560'>between</span> <span m='839920'>minus</span> <span
  m='840340'>pi</span> <span m='840730'>and</span> <span m='840850'>plus</span>
  <span m='841150'>pi,</span> <span m='841590'>you</span> <span
  m='842110'>will</span> <span m='842620'>have</span> <span
  m='842800'>seen</span> <span m='843460'>all</span> <span m='843940'>of</span>
  <span m='844540'>the</span> <span m='844630'>sinusoidal</span> <span
  m='845290'>sequences</span> <span m='846820'>with</span> <span
  m='846970'>this</span> <span m='847180'>amplitude</span> <span
  m='847930'>and</span> <span m='848050'>this</span> <span
  m='848230'>phase</span> <span m='848830'>that</span> <span
  m='848950'>we</span> <span m='849070'>can</span> <span
  m='849220'>possibly</span> <span m='849700'>generate.</span> </p><p><span
  m='852820'>One</span> <span m='853000'>of</span> <span m='853360'>the</span>
  <span m='853810'>important</span> <span m='856660'>of</span> <span
  m='858010'>this</span> <span m='858190'>set</span> <span m='858430'>of</span>
  <span m='858490'>basic</span> <span m='858910'>signals</span> <span
  m='860020'>is</span> <span m='860230'>that</span> <span m='860620'>they</span>
  <span m='860980'>can</span> <span m='861220'>be</span> <span
  m='861340'>used</span> <span m='861730'>to</span> <span
  m='861880'>represent</span> <span m='862750'>a</span> <span
  m='863170'>more</span> <span m='863410'>general</span> <span
  m='864160'>class</span> <span m='864850'>of</span> <span
  m='865330'>signals,</span> <span m='866500'>just</span> <span
  m='866830'>as</span> <span m='867070'>in</span> <span m='867160'>the</span>
  <span m='867250'>continuous</span> <span m='867850'>time</span> <span
  m='868180'>case,</span> <span m='868880'>we</span> <span m='868960'>use</span>
  <span m='869350'>impulses,</span> <span m='870610'>or</span> <span
  m='871060'>we</span> <span m='871270'>use</span> <span
  m='871600'>complex</span> <span m='872170'>exponentials,</span> <span
  m='873040'>or</span> <span m='873280'>we</span> <span m='873400'>use</span>
  <span m='873550'>sinusoids</span> <span m='874990'>to</span> <span
  m='875110'>represent</span> <span m='875740'>very</span> <span
  m='876070'>general</span> <span m='876490'>signals,</span> <span
  m='877570'>we</span> <span m='877870'>can</span> <span
  m='878560'>develop</span> <span m='879040'>similar</span> <span
  m='879460'>representations</span> <span m='880420'>here.</span> </p><p><span
  m='881500'>Let</span> <span m='881650'>me</span> <span
  m='881800'>illustrate</span> <span m='882310'>this</span> <span
  m='883180'>with</span> <span m='883360'>an</span> <span
  m='883420'>example</span> <span m='886360'>where</span> <span
  m='887050'>I</span> <span m='887260'>consider</span> <span m='889860'>a</span>
  <span m='889930'>general</span> <span m='890380'>sequence</span> <span
  m='892530'>here,</span> <span m='893300'>x of</span> <span
  m='893715'>n.</span> <span m='895440'>The</span> <span
  m='895540'>sequence</span> <span m='896050'>values</span> <span
  m='896980'>are</span> <span m='897370'>x</span> <span m='897640'>of</span>
  <span m='897730'>0,</span> <span m='898180'>x</span> <span
  m='898390'>of</span> <span m='898510'>1,</span> <span m='898960'>x</span>
  <span m='899270'>of</span> <span m='899390'>2,</span> <span m='900220'>et
  cetera.</span> <span m='901180'>And</span> <span m='901480'>I</span> <span
  m='901570'>mean</span> <span m='901900'>to</span> <span
  m='902020'>suggest</span> <span m='902590'>here</span> <span
  m='903400'>a</span> <span m='903460'>very</span> <span
  m='903730'>general</span> <span m='904120'>sequence.</span> </p><p><span
  m='905860'>Now,</span> <span m='907240'>I</span> <span m='907390'>can</span>
  <span m='907960'>decompose</span> <span m='908770'>this</span> <span
  m='908920'>sequence</span> <span m='910360'>into</span> <span
  m='911320'>a</span> <span m='911890'>linear</span> <span
  m='912430'>combination</span> <span m='914140'>of</span> <span
  m='914740'>weighted,</span> <span m='915550'>delayed</span> <span
  m='916210'>unit</span> <span m='916590'>samples,</span> <span
  m='917790'>unit</span> <span m='918040'>sample</span> <span
  m='918430'>sequences,</span> <span m='919900'>by</span> <span
  m='920410'>simply</span> <span m='920920'>extracting</span> <span
  m='921880'>individual</span> <span m='922630'>sequence</span> <span
  m='923110'>values</span> <span m='923710'>out</span> <span
  m='923860'>of</span> <span m='923980'>x</span> <span m='924220'>of</span>
  <span m='924320'>n.</span> <span m='924910'>For</span> <span
  m='925090'>example,</span> <span m='927230'>let's</span> <span
  m='927400'>consider</span> <span m='928210'>the</span> <span
  m='928300'>sequence</span> <span m='929420'>x</span> <span
  m='929670'>of</span> <span m='929810'>0</span> <span m='930670'>times</span>
  <span m='931030'>delta</span> <span m='931410'>of</span> <span
  m='931790'>n,</span> <span m='932350'>as</span> <span m='932560'>I've</span>
  <span m='932890'>illustrated</span> <span m='933550'>here.</span> <span
  m='934340'>X</span> <span m='934580'>of</span> <span m='934690'>0</span> <span
  m='934990'>times</span> <span m='935320'>delta</span> <span
  m='935580'>of</span> <span m='935840'>n</span> <span m='936640'>is</span>
  <span m='936790'>equal</span> <span m='937210'>to</span> <span
  m='937840'>the</span> <span m='937960'>original</span> <span
  m='938380'>sequence</span> <span m='938890'>x</span> <span
  m='939190'>of</span> <span m='939340'>n</span> <span m='940330'>at</span>
  <span m='940480'>n</span> <span m='940630'>equals</span> <span
  m='940900'>0,</span> <span m='941740'>and</span> <span m='941860'>it's</span>
  <span m='942010'>equal</span> <span m='942280'>to</span> <span
  m='942400'>0</span> <span m='942840'>otherwise.</span> </p><p><span
  m='946290'>A</span> <span m='946360'>second</span> <span
  m='946750'>sequence,</span> <span m='947590'>x</span> <span
  m='947860'>of</span> <span m='948010'>1</span> <span m='948370'>times</span>
  <span m='948730'>delta</span> <span m='949060'>of</span> <span
  m='949240'>n</span> <span m='949390'>minus</span> <span m='949840'>1,</span>
  <span m='950860'>is</span> <span m='951040'>a</span> <span
  m='951100'>unit</span> <span m='951400'>sample</span> <span
  m='952390'>sequence,</span> <span m='953380'>delayed</span> <span
  m='953830'>by</span> <span m='954100'>1</span> <span m='955510'>and</span>
  <span m='955630'>having</span> <span m='955930'>an</span> <span
  m='956020'>amplitude</span> <span m='956710'>equal</span> <span
  m='957070'>to</span> <span m='957190'>x</span> <span m='957460'>of</span>
  <span m='957610'>1.</span> <span m='958600'>So</span> <span
  m='959140'>this</span> <span m='959350'>sequence</span> <span
  m='960010'>is</span> <span m='960190'>equal</span> <span m='960490'>to</span>
  <span m='960640'>this</span> <span m='960910'>one</span> <span
  m='961380'>at</span> <span m='961530'>n</span> <span m='961896'>equals</span>
  <span m='962262'>1,</span> <span m='963100'>and</span> <span
  m='963220'>it's</span> <span m='963370'>equal</span> <span
  m='963640'>to</span> <span m='963760'>0,</span> <span
  m='964150'>otherwise.</span> <span m='965320'>The</span> <span
  m='965410'>sum</span> <span m='965740'>of</span> <span m='965860'>these</span>
  <span m='966160'>two,</span> <span m='966610'>of</span> <span
  m='966730'>course,</span> <span m='967810'>is</span> <span
  m='967960'>equal</span> <span m='968740'>to</span> <span
  m='969730'>this</span> <span m='970720'>x</span> <span m='970990'>of</span>
  <span m='971120'>n</span> <span m='971650'>at</span> <span
  m='971830'>these</span> <span m='972130'>two</span> <span
  m='972370'>values,</span> <span m='973150'>and</span> <span
  m='973270'>equal</span> <span m='973540'>to</span> <span m='973660'>0,</span>
  <span m='974020'>otherwise.</span> </p><p><span m='975100'>Similarly,</span>
  <span m='976030'>we</span> <span m='976210'>can</span> <span
  m='976570'>consider</span> <span m='978160'>x</span> <span
  m='978400'>of</span> <span m='978520'>minus</span> <span m='978970'>1</span>
  <span m='979330'>times</span> <span m='979660'>delta</span> <span
  m='980020'>of n</span> <span m='980350'>plus</span> <span m='980710'>1.</span>
  <span m='981890'>That's</span> <span m='982030'>a</span> <span
  m='982090'>unit</span> <span m='982360'>sample</span> <span
  m='983020'>at</span> <span m='983430'>n</span> <span m='983735'>equals</span>
  <span m='984040'>minus</span> <span m='984460'>1,</span> <span
  m='984820'>with</span> <span m='985180'>an</span> <span
  m='985270'>amplitude</span> <span m='986020'>of</span> <span
  m='986350'>x</span> <span m='986620'>of</span> <span m='986770'>minus</span>
  <span m='987190'>1,</span> <span m='988070'>which</span> <span
  m='988150'>picks</span> <span m='988480'>up</span> <span
  m='988900'>this</span> <span m='989040'>sequence</span> <span
  m='989560'>value.</span> <span m='991060'>x</span> <span m='991300'>of</span>
  <span m='991420'>minus</span> <span m='991840'>2</span> <span
  m='992320'>times</span> <span m='992650'>delta</span> <span
  m='993010'>of</span> <span m='993190'>n</span> <span m='993340'>plus</span>
  <span m='993710'>2</span> <span m='994870'>is</span> <span m='995230'>a</span>
  <span m='995290'>unit</span> <span m='995620'>sample</span> <span
  m='996310'>at</span> <span m='997300'>n</span> <span m='997600'>equals</span>
  <span m='997930'>minus</span> <span m='998350'>2</span> <span
  m='998830'>multiplied</span> <span m='999730'>by</span> <span
  m='999940'>an</span> <span m='1000030'>amplitude</span> <span
  m='1000870'>x</span> <span m='1001140'>of</span> <span
  m='1001260'>minus</span> <span m='1001680'>2,</span> <span
  m='1002650'>which</span> <span m='1002820'>picks</span> <span
  m='1003120'>up</span> <span m='1003300'>this</span> <span
  m='1003430'>sequence</span> <span m='1003930'>value,</span> <span
  m='1004500'>et</span> <span m='1005730'>cetera.</span> </p><p><span
  m='1007450'>So</span> <span m='1008100'>I</span> <span
  m='1008220'>think</span> <span m='1008520'>you</span> <span
  m='1008610'>can</span> <span m='1008790'>see,</span> <span
  m='1009090'>then,</span> <span m='1009660'>that</span> <span
  m='1010050'>as</span> <span m='1010740'>we</span> <span m='1010980'>add</span>
  <span m='1011280'>these</span> <span m='1011610'>up,</span> <span
  m='1012870'>what</span> <span m='1013140'>we'll</span> <span
  m='1013350'>generate</span> <span m='1014250'>is</span> <span
  m='1014820'>this</span> <span m='1015030'>arbitrary</span> <span
  m='1015630'>sequence,</span> <span m='1016230'>x</span> <span m='1016500'>of
  n.</span> <span m='1017710'>In</span> <span m='1017730'>other</span> <span
  m='1017910'>words,</span> <span m='1019000'>we</span> <span
  m='1019050'>can</span> <span m='1019260'>construct</span> <span
  m='1019890'>x</span> <span m='1020080'>of</span> <span m='1020280'>n,</span>
  <span m='1020970'>an</span> <span m='1021090'>arbitrary</span> <span
  m='1021570'>sequence,</span> <span m='1023490'>as</span> <span
  m='1023850'>a</span> <span m='1023910'>linear</span> <span
  m='1024300'>combination</span> <span m='1025380'>of</span> <span
  m='1026010'>weighted</span> <span m='1026430'>delayed</span> <span
  m='1027180'>unit</span> <span m='1027490'>samples--</span> <span
  m='1029060'>x</span> <span m='1029890'>of</span> <span m='1030089'>0</span>
  <span m='1030540'>times</span> <span m='1030900'>delta</span> <span
  m='1031260'>of</span> <span m='1031480'>n</span> <span m='1032190'>plus</span>
  <span m='1032550'>x</span> <span m='1032849'>of</span> <span
  m='1033030'>1</span> <span m='1033359'>times</span> <span
  m='1033720'>delta</span> <span m='1034050'>of</span> <span
  m='1034230'>n</span> <span m='1034380'>minus</span> <span m='1034829'>1</span>
  <span m='1035700'>plus</span> <span m='1035940'>x</span> <span
  m='1036180'>of</span> <span m='1036300'>minus</span> <span
  m='1036720'>1</span> <span m='1037050'>delta</span> <span m='1037430'>n</span>
  <span m='1037650'>plus</span> <span m='1037980'>1,</span> <span m='1038450'>et
  cetera.</span> <span m='1039060'>Or,</span> <span m='1040020'>more</span>
  <span m='1040260'>generally,</span> <span m='1041420'>the</span> <span
  m='1041550'>sum</span> <span m='1042119'>from</span> <span
  m='1042300'>k</span> <span m='1042710'>equals</span> <span
  m='1042839'>minus</span> <span m='1043230'>infinity</span> <span
  m='1043829'>to</span> <span m='1044010'>plus</span> <span
  m='1044280'>infinity</span> <span m='1045390'>of</span> <span
  m='1045869'>x</span> <span m='1046170'>of</span> <span m='1046310'>k</span>
  <span m='1046920'>times</span> <span m='1047640'>delta</span> <span
  m='1047989'>of</span> <span m='1048339'>n</span> <span
  m='1048480'>minus</span> <span m='1048840'>k.</span> </p><p><span
  m='1050010'>This,</span> <span m='1050640'>then,</span> <span
  m='1052080'>corresponds</span> <span m='1053190'>to</span> <span
  m='1053790'>a</span> <span m='1054390'>general</span> <span
  m='1054900'>representation</span> <span m='1056490'>of</span> <span
  m='1056640'>an</span> <span m='1056730'>arbitrary</span> <span
  m='1057390'>sequence</span> <span m='1058500'>in</span> <span
  m='1058650'>terms</span> <span m='1059340'>of</span> <span
  m='1059820'>weighted</span> <span m='1060600'>delayed</span> <span
  m='1061020'>unit</span> <span m='1061320'>samples.</span> <span
  m='1062740'>And</span> <span m='1063090'>it's</span> <span
  m='1063240'>a</span> <span m='1063300'>representation</span> <span
  m='1064800'>that</span> <span m='1065130'>we'll</span> <span
  m='1065310'>want</span> <span m='1065520'>to</span> <span
  m='1065580'>refer</span> <span m='1065910'>back</span> <span
  m='1066210'>to</span> <span m='1066600'>in</span> <span m='1066720'>a</span>
  <span m='1066780'>few</span> <span m='1067020'>minutes.</span> <span
  m='1067980'>It's</span> <span m='1068160'>not,</span> <span
  m='1068610'>as</span> <span m='1068790'>I've</span> <span
  m='1068940'>indicated,</span> <span m='1069750'>the</span> <span
  m='1069900'>only</span> <span m='1070140'>representation</span> <span
  m='1071400'>of</span> <span m='1071820'>arbitrary</span> <span
  m='1072420'>sequences--</span> <span m='1073490'>we'll</span> <span
  m='1073680'>also</span> <span m='1074040'>be</span> <span
  m='1074220'>developing</span> <span m='1075030'>representations</span> <span
  m='1076230'>in</span> <span m='1076380'>terms</span> <span
  m='1076860'>of</span> <span m='1076980'>complex</span> <span
  m='1077520'>exponentials,</span> <span m='1078450'>or</span> <span
  m='1078600'>real</span> <span m='1078900'>exponentials,</span> <span
  m='1080190'>or</span> <span m='1080370'>in</span> <span
  m='1080460'>terms</span> <span m='1080790'>of</span> <span
  m='1080880'>sines</span> <span m='1081240'>and</span> <span
  m='1081330'>cosines.</span> </p><p><span m='1083700'>OK,</span> <span
  m='1084360'>that</span> <span m='1086820'>is</span> <span
  m='1087210'>an</span> <span m='1087330'>introduction</span> <span
  m='1088350'>to</span> <span m='1088980'>the</span> <span
  m='1089370'>basic</span> <span m='1089850'>class</span> <span
  m='1090510'>of</span> <span m='1091410'>signals</span> <span
  m='1092760'>and</span> <span m='1092940'>the</span> <span
  m='1093030'>notion</span> <span m='1093360'>of</span> <span
  m='1093420'>sequences.</span> <span m='1094800'>What</span> <span
  m='1094920'>I'd</span> <span m='1095010'>like</span> <span
  m='1095220'>to</span> <span m='1095340'>do</span> <span m='1095520'>now</span>
  <span m='1096090'>is</span> <span m='1096720'>focus</span> <span
  m='1097470'>on</span> <span m='1098190'>the</span> <span
  m='1098310'>class</span> <span m='1098730'>of</span> <span
  m='1098820'>discrete</span> <span m='1099210'>time</span> <span
  m='1099540'>systems,</span> <span m='1100830'>and</span> <span
  m='1101040'>then</span> <span m='1101490'>refer</span> <span
  m='1101880'>back</span> <span m='1102210'>to</span> <span
  m='1102330'>some</span> <span m='1102600'>of</span> <span
  m='1102690'>these</span> <span m='1102930'>results</span> <span
  m='1103800'>to</span> <span m='1103890'>develop</span> <span
  m='1104430'>a</span> <span m='1104490'>general</span> <span
  m='1104850'>representation</span> <span m='1105840'>for</span> <span
  m='1106050'>a</span> <span m='1106080'>special</span> <span
  m='1106530'>class</span> <span m='1107130'>of</span> <span
  m='1107580'>discrete</span> <span m='1107940'>time</span> <span
  m='1108240'>systems.</span> </p><p><span m='1115160'>First</span> <span
  m='1115390'>of</span> <span m='1115510'>all,</span> <span
  m='1116150'>let</span> <span m='1116260'>me</span> <span
  m='1116860'>begin</span> <span m='1117520'>with</span> <span
  m='1117660'>a</span> <span m='1117730'>general</span> <span
  m='1118150'>system,</span> <span m='1120870'>which</span> <span
  m='1121560'>is</span> <span m='1123900'>a</span> <span
  m='1124110'>discrete</span> <span m='1124560'>time</span> <span
  m='1124860'>system</span> <span m='1126150'>that</span> <span
  m='1126600'>has</span> <span m='1126840'>an</span> <span
  m='1126930'>input--</span> <span m='1127540'>which</span> <span
  m='1127770'>is</span> <span m='1128130'>a</span> <span
  m='1128190'>sequence</span> <span m='1128960'>x</span> <span m='1129220'>of
  n.</span> <span m='1130200'>It</span> <span m='1130290'>has</span> <span
  m='1130500'>an</span> <span m='1130590'>output,</span> <span
  m='1131130'>which</span> <span m='1131370'>is</span> <span
  m='1131490'>a</span> <span m='1131580'>sequence</span> <span
  m='1132270'>y</span> <span m='1132570'>of</span> <span m='1132780'>n.</span>
  <span m='1133680'>And</span> <span m='1133860'>it</span> <span
  m='1133950'>has</span> <span m='1134190'>a</span> <span
  m='1134250'>system</span> <span m='1134910'>transformation,</span> <span
  m='1136150'>which</span> <span m='1136350'>I've</span> <span
  m='1136530'>denoted</span> <span m='1137310'>by</span> <span
  m='1137490'>T.</span> <span m='1139320'>Of</span> <span
  m='1139440'>course,</span> <span m='1139920'>there</span> <span
  m='1140070'>isn't</span> <span m='1140280'>much</span> <span
  m='1140760'>that</span> <span m='1141150'>you</span> <span
  m='1141300'>can</span> <span m='1141420'>do</span> <span
  m='1141600'>with</span> <span m='1141710'>a</span> <span
  m='1141780'>general</span> <span m='1142200'>system--</span> <span
  m='1143850'>the</span> <span m='1144780'>difficulty</span> <span
  m='1145680'>with</span> <span m='1145860'>trying</span> <span
  m='1146160'>to</span> <span m='1146250'>describe</span> <span
  m='1146910'>a</span> <span m='1146970'>general</span> <span
  m='1147360'>system</span> <span m='1147960'>in</span> <span
  m='1148080'>general</span> <span m='1149100'>is</span> <span
  m='1149280'>that</span> <span m='1149550'>there</span> <span
  m='1149700'>are</span> <span m='1149730'>no</span> <span
  m='1149880'>properties</span> <span m='1150450'>that</span> <span
  m='1150600'>you</span> <span m='1150690'>can</span> <span
  m='1150840'>take</span> <span m='1151080'>advantage</span> <span
  m='1151590'>of.</span> </p><p><span m='1152920'>So</span> <span
  m='1153660'>always,</span> <span m='1154440'>in</span> <span
  m='1154680'>characterizing</span> <span m='1155520'>systems,</span> <span
  m='1156240'>it's</span> <span m='1156450'>useful</span> <span
  m='1157050'>to</span> <span m='1157170'>specialize</span> <span
  m='1157860'>the</span> <span m='1157980'>class</span> <span
  m='1158310'>of</span> <span m='1158430'>systems--</span> <span
  m='1159630'>that</span> <span m='1159810'>is,</span> <span
  m='1160020'>impose</span> <span m='1160440'>properties</span> <span
  m='1161010'>on</span> <span m='1161140'>the</span> <span
  m='1161250'>system</span> <span m='1161850'>which</span> <span
  m='1162060'>you</span> <span m='1162150'>can</span> <span
  m='1162300'>exploit</span> <span m='1163560'>to</span> <span
  m='1163950'>represent</span> <span m='1164550'>the</span> <span
  m='1164640'>system,</span> <span m='1165330'>or</span> <span
  m='1166200'>to</span> <span m='1166590'>implement</span> <span
  m='1167100'>the</span> <span m='1167220'>system,</span> <span m='1168060'>et
  cetera.</span> <span m='1168930'>The</span> <span m='1169020'>special</span>
  <span m='1169440'>class</span> <span m='1170040'>that</span> <span
  m='1170190'>we'll</span> <span m='1170370'>want</span> <span
  m='1170550'>to</span> <span m='1170640'>consider</span> <span
  m='1171900'>is</span> <span m='1172380'>the</span> <span
  m='1172500'>class</span> <span m='1172950'>of</span> <span
  m='1173070'>systems</span> <span m='1173820'>which</span> <span
  m='1174000'>are,</span> <span m='1174090'>first</span> <span
  m='1174390'>of</span> <span m='1174480'>all,</span> <span
  m='1174630'>linear.</span> <span m='1176250'>And</span> <span
  m='1176760'>second</span> <span m='1177180'>of</span> <span
  m='1177300'>all,</span> <span m='1177900'>shift</span> <span
  m='1178210'>invariant.</span> </p><p><span m='1180210'>And</span> <span
  m='1180540'>this</span> <span m='1180780'>class</span> <span
  m='1181350'>corresponds,</span> <span m='1182760'>in</span> <span
  m='1182880'>the</span> <span m='1182970'>continuous</span> <span
  m='1183540'>time</span> <span m='1183840'>case,</span> <span
  m='1184650'>to</span> <span m='1184890'>the</span> <span
  m='1184980'>class</span> <span m='1185310'>of</span> <span
  m='1185400'>systems</span> <span m='1186240'>that</span> <span
  m='1186540'>we</span> <span m='1186720'>normally</span> <span
  m='1187140'>refer</span> <span m='1187500'>to</span> <span
  m='1187770'>as</span> <span m='1187920'>linear</span> <span
  m='1188340'>and</span> <span m='1188430'>time</span> <span
  m='1188800'>invariant.</span> <span m='1190470'>We'll</span> <span
  m='1190710'>tend</span> <span m='1190920'>to</span> <span
  m='1191040'>refer</span> <span m='1191370'>to</span> <span
  m='1191520'>these</span> <span m='1191850'>as</span> <span
  m='1192000'>linear</span> <span m='1192480'>and</span> <span
  m='1192570'>shift</span> <span m='1192900'>invariant,</span> <span
  m='1193700'>and</span> <span m='1193830'>for</span> <span m='1194010'>a</span>
  <span m='1194070'>shorthand</span> <span m='1194610'>notation,</span> <span
  m='1195810'>just</span> <span m='1196230'>express</span> <span
  m='1196770'>this</span> <span m='1197120'>as</span> <span
  m='1197910'>well</span> <span m='1198210'>LSI.</span> <span
  m='1200700'>When</span> <span m='1200850'>I</span> <span
  m='1200910'>refer</span> <span m='1201270'>to</span> <span
  m='1201450'>an</span> <span m='1201540'>LSI</span> <span
  m='1202110'>system,</span> <span m='1203010'>what</span> <span
  m='1203130'>I</span> <span m='1203250'>mean</span> <span m='1203610'>is</span>
  <span m='1203730'>a</span> <span m='1203790'>system</span> <span
  m='1204330'>that</span> <span m='1204600'>is</span> <span
  m='1205020'>linear</span> <span m='1205500'>and</span> <span
  m='1205590'>shift</span> <span m='1205900'>invariant.</span> </p><p><span
  m='1207180'>Well,</span> <span m='1207660'>let's</span> <span
  m='1207900'>define</span> <span m='1208320'>these</span> <span
  m='1208530'>terms.</span> <span m='1209740'>First</span> <span
  m='1209970'>of</span> <span m='1210090'>all,</span> <span
  m='1210690'>linearity.</span> <span m='1214170'>Linearity</span> <span
  m='1215540'>states</span> <span m='1216500'>that</span> <span
  m='1217190'>if</span> <span m='1217700'>I</span> <span
  m='1218210'>excite</span> <span m='1218690'>the</span> <span
  m='1218780'>system</span> <span m='1220190'>with</span> <span
  m='1220520'>a</span> <span m='1220580'>sequence</span> <span m='1221060'>x
  1</span> <span m='1221335'>of</span> <span m='1221610'>n,</span> <span
  m='1223100'>and</span> <span m='1223460'>I</span> <span m='1223550'>get</span>
  <span m='1223790'>at</span> <span m='1223880'>the</span> <span
  m='1224060'>output</span> <span m='1224750'>a</span> <span
  m='1225140'>sequence</span> <span m='1225680'>y 1 of</span> <span
  m='1226190'>n,</span> <span m='1227630'>and</span> <span m='1227720'>if</span>
  <span m='1227930'>I</span> <span m='1228110'>excite</span> <span
  m='1228470'>with</span> <span m='1228620'>x 2</span> <span
  m='1229080'>of</span> <span m='1229300'>n,</span> <span m='1230120'>and</span>
  <span m='1230270'>get</span> <span m='1230600'>at</span> <span
  m='1230840'>the</span> <span m='1231020'>output</span> <span
  m='1231710'>y</span> <span m='1232010'>2</span> <span m='1232300'>of n,</span>
  <span m='1234390'>then</span> <span m='1235610'>the</span> <span
  m='1235910'>condition</span> <span m='1236420'>of</span> <span
  m='1236510'>linearity</span> <span m='1237470'>is</span> <span
  m='1238070'>that</span> <span m='1238760'>the</span> <span
  m='1238850'>linear</span> <span m='1239180'>combination,</span> <span
  m='1240160'>a x</span> <span m='1240620'>1 of n</span> <span
  m='1241460'>plus</span> <span m='1241730'>b x</span> <span
  m='1242300'>2</span> <span m='1242510'>of</span> <span m='1242650'>n,</span>
  <span m='1243530'>produces</span> <span m='1244110'>at</span> <span
  m='1244220'>the</span> <span m='1244370'>output</span> <span
  m='1245330'>a</span> <span m='1245630'>y1 of</span> <span m='1246130'>n</span>
  <span m='1246690'>plus</span> <span m='1247040'>b</span> <span m='1247280'>y
  2</span> <span m='1247560'>of</span> <span m='1247850'>n.</span> <span
  m='1248570'>That</span> <span m='1248810'>is,</span> <span
  m='1249500'>the</span> <span m='1249620'>response</span> <span
  m='1250130'>of</span> <span m='1250190'>the</span> <span
  m='1250310'>system</span> <span m='1251300'>to</span> <span
  m='1251690'>a</span> <span m='1251750'>sum</span> <span m='1252080'>of</span>
  <span m='1252200'>inputs,</span> <span m='1253630'>or</span> <span
  m='1253970'>a</span> <span m='1254000'>linear</span> <span
  m='1254300'>combination</span> <span m='1254930'>of</span> <span
  m='1255050'>inputs,</span> <span m='1255860'>is</span> <span
  m='1256250'>a</span> <span m='1256310'>linear</span> <span
  m='1256640'>combination</span> <span m='1257420'>of</span> <span
  m='1257570'>the</span> <span m='1257660'>corresponding</span> <span
  m='1258350'>outputs.</span> </p><p><span m='1260130'>Now,</span> <span
  m='1260420'>by</span> <span m='1260750'>repeated</span> <span
  m='1261200'>application</span> <span m='1262190'>of</span> <span
  m='1262670'>just</span> <span m='1262940'>this</span> <span
  m='1263120'>statement,</span> <span m='1264230'>we</span> <span
  m='1264410'>can</span> <span m='1264920'>make</span> <span
  m='1265160'>a</span> <span m='1265220'>more</span> <span
  m='1265430'>general</span> <span m='1265850'>statement,</span> <span
  m='1267120'>which</span> <span m='1267290'>is</span> <span
  m='1267950'>that</span> <span m='1268640'>the</span> <span
  m='1268760'>sum</span> <span m='1269330'>of</span> <span m='1269540'>a</span>
  <span m='1269840'>sub</span> <span m='1269990'>k</span> <span
  m='1271010'>times</span> <span m='1271370'>x</span> <span
  m='1271700'>sub</span> <span m='1271810'>k of</span> <span
  m='1272250'>n</span> <span m='1273950'>produces,</span> <span
  m='1274910'>as</span> <span m='1275120'>an</span> <span
  m='1275210'>output,</span> <span m='1276380'>the</span> <span
  m='1276500'>sum</span> <span m='1278300'>of</span> <span m='1278750'>a</span>
  <span m='1278940'>sub</span> <span m='1279210'>k</span> <span
  m='1280160'>times</span> <span m='1281170'>y</span> <span
  m='1281540'>sub</span> <span m='1281660'>k</span> <span m='1281910'>of</span>
  <span m='1281980'>n.</span> <span m='1284090'>Linearity</span> <span
  m='1284690'>is</span> <span m='1284750'>stated</span> <span
  m='1285170'>here,</span> <span m='1285410'>of</span> <span
  m='1285500'>course,</span> <span m='1286130'>for</span> <span
  m='1286640'>two</span> <span m='1286910'>inputs,</span> <span
  m='1288050'>but</span> <span m='1288500'>we</span> <span
  m='1288680'>can</span> <span m='1289460'>obviously</span> <span
  m='1290060'>extend</span> <span m='1290510'>that</span> <span
  m='1291050'>to</span> <span m='1291800'>an</span> <span
  m='1291890'>arbitrary</span> <span m='1292430'>number</span> <span
  m='1292730'>of</span> <span m='1292820'>inputs</span> <span
  m='1293790'>so</span> <span m='1293930'>that</span> <span
  m='1294590'>the</span> <span m='1294770'>statement</span> <span
  m='1295190'>of</span> <span m='1295280'>linearity,</span> <span
  m='1296030'>as</span> <span m='1296150'>we'll</span> <span
  m='1296360'>refer</span> <span m='1296690'>to</span> <span
  m='1296870'>it,</span> <span m='1297410'>will</span> <span
  m='1297530'>generally</span> <span m='1298070'>be</span> <span
  m='1298580'>that</span> <span m='1299300'>a</span> <span
  m='1299360'>general</span> <span m='1299750'>linear</span> <span
  m='1300110'>combination</span> <span m='1300770'>of</span> <span
  m='1300890'>inputs</span> <span m='1301760'>produces,</span> <span
  m='1302120'>at</span> <span m='1302480'>the</span> <span
  m='1302600'>output,</span> <span m='1303260'>the</span> <span
  m='1303350'>same</span> <span m='1303950'>linear</span> <span
  m='1304280'>combination</span> <span m='1305180'>of</span> <span
  m='1305300'>the</span> <span m='1305390'>corresponding</span> <span
  m='1306080'>outputs.</span> </p><p><span m='1307820'>So</span> <span
  m='1307940'>that's</span> <span m='1308480'>the</span> <span
  m='1309560'>condition</span> <span m='1310160'>of</span> <span
  m='1310310'>linearity.</span> <span m='1311630'>The</span> <span
  m='1311720'>second</span> <span m='1312080'>condition</span> <span
  m='1312860'>that</span> <span m='1313160'>we</span> <span
  m='1313280'>want</span> <span m='1313460'>to</span> <span
  m='1313580'>impose</span> <span m='1314270'>on</span> <span
  m='1314450'>our</span> <span m='1314510'>class</span> <span
  m='1314870'>of</span> <span m='1314960'>systems</span> <span
  m='1316040'>is</span> <span m='1316220'>the</span> <span
  m='1316310'>condition</span> <span m='1316760'>of</span> <span
  m='1316820'>shift</span> <span m='1317150'>invariance.</span> <span
  m='1318880'>What</span> <span m='1318950'>shift</span> <span
  m='1319220'>invariance</span> <span m='1320360'>says,</span> <span
  m='1320870'>simply,</span> <span m='1322100'>is</span> <span
  m='1322760'>that</span> <span m='1323960'>if</span> <span m='1324710'>x</span>
  <span m='1325010'>of n</span> <span m='1325630'>produces</span> <span
  m='1326600'>y</span> <span m='1326970'>of</span> <span m='1327110'>n,</span>
  <span m='1328130'>then</span> <span m='1328430'>x</span> <span m='1328760'>of
  n</span> <span m='1329240'>minus</span> <span m='1329630'>n</span> <span
  m='1329840'>0</span> <span m='1330680'>produces</span> <span
  m='1331610'>y</span> <span m='1332060'>of</span> <span m='1332210'>n</span>
  <span m='1332360'>minus</span> <span m='1332900'>n 0.</span> <span
  m='1333710'>It's</span> <span m='1333860'>basically</span> <span
  m='1334400'>a</span> <span m='1334460'>statement</span> <span
  m='1335270'>that</span> <span m='1335480'>the</span> <span
  m='1335570'>system</span> <span m='1336170'>doesn't</span> <span
  m='1336470'>particularly</span> <span m='1337160'>care</span> <span
  m='1338150'>what</span> <span m='1338390'>you</span> <span
  m='1338510'>call</span> <span m='1338930'>n</span> <span
  m='1339080'>equals</span> <span m='1339360'>0.</span> <span
  m='1340460'>In</span> <span m='1340550'>other</span> <span
  m='1340760'>words,</span> <span m='1341820'>if</span> <span
  m='1342050'>we</span> <span m='1342230'>shift</span> <span
  m='1342500'>the</span> <span m='1342680'>input</span> <span m='1343480'>in
  n,</span> <span m='1344120'>we</span> <span m='1344240'>shift</span> <span
  m='1344540'>the</span> <span m='1344690'>output</span> <span
  m='1345110'>in</span> <span m='1345240'>n.</span> <span
  m='1345830'>It's</span> <span m='1346130'>exactly</span> <span
  m='1346670'>like</span> <span m='1347060'>the</span> <span
  m='1347150'>condition</span> <span m='1347570'>of</span> <span
  m='1347660'>time</span> <span m='1348030'>invariance</span> <span
  m='1348740'>in</span> <span m='1348830'>the</span> <span
  m='1348920'>continuous</span> <span m='1349490'>time</span> <span
  m='1349770'>case.</span> </p><p><span m='1352570'>For</span> <span
  m='1352780'>example,</span> <span m='1353780'>if</span> <span
  m='1354340'>we</span> <span m='1354820'>excited</span> <span
  m='1355360'>the</span> <span m='1355480'>system</span> <span
  m='1356230'>with</span> <span m='1356380'>a</span> <span
  m='1356430'>unit</span> <span m='1356710'>sample,</span> <span
  m='1357920'>to</span> <span m='1358060'>get</span> <span
  m='1358570'>the</span> <span m='1358690'>unit</span> <span
  m='1358960'>sample</span> <span m='1359800'>response,</span> <span
  m='1360720'>h</span> <span m='1360985'>of</span> <span m='1361250'>n,</span>
  <span m='1362470'>then</span> <span m='1363610'>the</span> <span
  m='1363850'>response</span> <span m='1364420'>of</span> <span
  m='1364480'>the</span> <span m='1364600'>system,</span> <span
  m='1365500'>if</span> <span m='1365680'>the</span> <span
  m='1365770'>system</span> <span m='1366130'>is</span> <span
  m='1366190'>shift</span> <span m='1366490'>invariant,</span> <span
  m='1367480'>to</span> <span m='1367630'>a</span> <span
  m='1367690'>delayed</span> <span m='1368110'>unit</span> <span
  m='1368410'>sample</span> <span m='1369340'>is</span> <span
  m='1370150'>the</span> <span m='1370630'>delayed</span> <span
  m='1371020'>version</span> <span m='1371620'>of</span> <span
  m='1371860'>the</span> <span m='1371950'>unit</span> <span
  m='1372190'>sample</span> <span m='1372580'>response.</span> </p><p><span
  m='1374150'>So</span> <span m='1374290'>this</span> <span
  m='1374500'>is</span> <span m='1374590'>shift</span> <span
  m='1374920'>invariance.</span> <span m='1376390'>We</span> <span
  m='1376510'>had</span> <span m='1376690'>the</span> <span
  m='1376780'>condition</span> <span m='1377230'>of</span> <span
  m='1377320'>linearity.</span> <span m='1378460'>These</span> <span
  m='1378640'>are</span> <span m='1378730'>two</span> <span
  m='1378970'>independent</span> <span m='1379600'>conditions</span> <span
  m='1380810'>which</span> <span m='1381130'>we'll</span> <span
  m='1381370'>now</span> <span m='1381820'>want</span> <span
  m='1382030'>to</span> <span m='1382090'>put</span> <span
  m='1382330'>together</span> <span m='1383020'>to</span> <span
  m='1383140'>develop</span> <span m='1383740'>a</span> <span
  m='1383800'>general</span> <span m='1384190'>representation</span> <span
  m='1385390'>for</span> <span m='1386290'>linear</span> <span
  m='1386950'>shift</span> <span m='1387310'>invariant</span> <span
  m='1387850'>systems.</span> </p><p><span m='1390200'>Well,</span> <span
  m='1391330'>let</span> <span m='1391510'>me</span> <span
  m='1391690'>remind</span> <span m='1392230'>you</span> <span
  m='1392680'>from</span> <span m='1393430'>the</span> <span
  m='1393790'>last</span> <span m='1394150'>viewgraph</span> <span
  m='1394990'>that</span> <span m='1395110'>we</span> <span
  m='1395290'>had</span> <span m='1395410'>looked</span> <span
  m='1395710'>at,</span> <span m='1396870'>that</span> <span
  m='1397300'>we</span> <span m='1397480'>had</span> <span m='1397720'>a</span>
  <span m='1398020'>general</span> <span m='1398470'>representation</span> <span
  m='1399820'>for</span> <span m='1400120'>a</span> <span
  m='1400150'>sequence</span> <span m='1401110'>in</span> <span
  m='1401230'>terms</span> <span m='1401920'>of</span> <span
  m='1402730'>weighted</span> <span m='1403240'>delayed</span> <span
  m='1403690'>units</span> <span m='1404020'>samples.</span> <span
  m='1405040'>That</span> <span m='1405220'>is,</span> <span
  m='1406330'>previously</span> <span m='1407440'>we</span> <span
  m='1407980'>had</span> <span m='1408610'>developed</span> <span
  m='1409070'>a</span> <span m='1409150'>representation,</span> <span
  m='1410180'>x</span> <span m='1410480'>of n,</span> <span
  m='1411590'>of</span> <span m='1411850'>this</span> <span
  m='1412090'>form,</span> <span m='1413470'>which</span> <span
  m='1413710'>expresses</span> <span m='1414880'>an</span> <span
  m='1414970'>arbitrary</span> <span m='1415510'>sequence</span> <span
  m='1416200'>in</span> <span m='1416320'>terms</span> <span
  m='1416860'>of</span> <span m='1417400'>weighted</span> <span
  m='1417760'>delayed</span> <span m='1418080'>unit</span> <span
  m='1418450'>samples.</span> </p><p><span m='1420370'>Well,</span> <span
  m='1421330'>this,</span> <span m='1421630'>then,</span> <span
  m='1422080'>says</span> <span m='1422410'>that</span> <span
  m='1422530'>x</span> <span m='1422760'>of n</span> <span m='1423370'>is</span>
  <span m='1423580'>expressed</span> <span m='1424480'>as</span> <span
  m='1425110'>a</span> <span m='1425170'>linear</span> <span
  m='1425500'>combination</span> <span m='1426520'>of</span> <span
  m='1426610'>basic</span> <span m='1427090'>inputs,</span> <span
  m='1428260'>and</span> <span m='1428890'>if</span> <span m='1429460'>we</span>
  <span m='1429880'>restrict</span> <span m='1430390'>ourselves</span> <span
  m='1431320'>to</span> <span m='1431650'>linear</span> <span
  m='1432040'>systems,</span> <span m='1433210'>then</span> <span
  m='1433780'>the</span> <span m='1433960'>output</span> <span
  m='1434800'>must</span> <span m='1435070'>correspond</span> <span
  m='1436300'>to</span> <span m='1436870'>the</span> <span
  m='1438100'>same</span> <span m='1438580'>linear</span> <span
  m='1438940'>combination</span> <span m='1439870'>of</span> <span
  m='1440050'>the</span> <span m='1440140'>corresponding</span> <span
  m='1440860'>outputs.</span> <span m='1442000'>Well,</span> <span
  m='1443260'>delta</span> <span m='1443650'>of n</span> <span
  m='1443965'>minus</span> <span m='1444280'>k</span> <span
  m='1444820'>into</span> <span m='1445150'>a</span> <span
  m='1445240'>linear</span> <span m='1445600'>shift</span> <span
  m='1446010'>invariant</span> <span m='1446430'>system</span> <span
  m='1447910'>will</span> <span m='1448060'>produce,</span> <span
  m='1448790'>at</span> <span m='1448990'>the</span> <span
  m='1449140'>output,</span> <span m='1451960'>by</span> <span
  m='1452470'>virtue</span> <span m='1453160'>of</span> <span
  m='1453580'>the</span> <span m='1453700'>property</span> <span
  m='1454150'>of</span> <span m='1454240'>shift</span> <span
  m='1454530'>invariance,</span> <span m='1457390'>the</span> <span
  m='1457480'>sequence</span> <span m='1458380'>h</span> <span m='1458620'>of
  n</span> <span m='1458890'>minus</span> <span m='1459250'>k.</span>
  </p><p><span m='1461500'>And</span> <span m='1462250'>the</span> <span
  m='1462310'>linear</span> <span m='1462670'>combination</span> <span
  m='1463840'>of</span> <span m='1464680'>these</span> <span
  m='1465130'>delayed</span> <span m='1465520'>unit</span> <span
  m='1465840'>samples</span> <span m='1466900'>will</span> <span
  m='1467050'>produce</span> <span m='1467320'>at</span> <span
  m='1467590'>the</span> <span m='1467770'>output,</span> <span
  m='1468310'>by</span> <span m='1468490'>virtue</span> <span
  m='1468880'>of</span> <span m='1468970'>linearity,</span> <span
  m='1470380'>the</span> <span m='1470500'>same</span> <span
  m='1471280'>linear</span> <span m='1471640'>combination</span> <span
  m='1475180'>of</span> <span m='1476140'>the</span> <span
  m='1476470'>responses</span> <span m='1478000'>to</span> <span
  m='1478300'>delta</span> <span m='1478670'>of n</span> <span
  m='1478980'>minus</span> <span m='1479290'>k.</span> <span
  m='1480130'>So</span> <span m='1481120'>if</span> <span m='1481570'>we</span>
  <span m='1481750'>consider</span> <span m='1482320'>a</span> <span
  m='1482380'>linear</span> <span m='1482740'>shift</span> <span
  m='1483070'>invariant</span> <span m='1483610'>system,</span> <span
  m='1484650'>and</span> <span m='1484780'>because</span> <span
  m='1485200'>of</span> <span m='1485320'>this</span> <span
  m='1485530'>representation,</span> <span m='1487150'>we</span> <span
  m='1487270'>can</span> <span m='1487450'>say</span> <span
  m='1488110'>that</span> <span m='1488860'>the</span> <span
  m='1488950'>response</span> <span m='1489630'>due</span> <span
  m='1489850'>to</span> <span m='1490030'>an</span> <span
  m='1490120'>arbitrary</span> <span m='1490720'>input</span> <span
  m='1492190'>is</span> <span m='1493090'>equal</span> <span
  m='1493600'>to</span> <span m='1494320'>a</span> <span
  m='1494380'>linear</span> <span m='1494740'>combination</span> <span
  m='1495760'>of</span> <span m='1496940'>delayed</span> <span
  m='1497800'>unit</span> <span m='1498130'>sample</span> <span
  m='1498550'>responses.</span> <span m='1499900'>Where,</span> <span
  m='1500110'>in</span> <span m='1500200'>general,</span> <span
  m='1500810'>this</span> <span m='1500890'>is</span> <span m='1501010'>a</span>
  <span m='1501100'>sum</span> <span m='1501490'>from</span> <span m='1501940'>k
  equals</span> <span m='1502450'>minus</span> <span m='1502810'>infinity</span>
  <span m='1503290'>to</span> <span m='1503380'>plus</span> <span
  m='1503680'>infinity.</span> </p><p><span m='1505990'>Well,</span> <span
  m='1506410'>this</span> <span m='1506860'>is</span> <span
  m='1507550'>the</span> <span m='1507670'>key</span> <span
  m='1507910'>result--</span> <span m='1508450'>this</span> <span
  m='1508660'>is</span> <span m='1508810'>a</span> <span
  m='1508870'>statement</span> <span m='1509770'>that</span> <span
  m='1509920'>says</span> <span m='1510610'>that</span> <span
  m='1510880'>if</span> <span m='1511300'>we</span> <span
  m='1511480'>talk</span> <span m='1511810'>about</span> <span
  m='1512170'>linear</span> <span m='1512530'>shift</span> <span
  m='1512860'>invariant</span> <span m='1513400'>systems,</span> <span
  m='1514750'>then</span> <span m='1515800'>all</span> <span
  m='1516010'>that</span> <span m='1516130'>we</span> <span
  m='1516250'>need</span> <span m='1516430'>to</span> <span
  m='1516550'>know</span> <span m='1516730'>about</span> <span
  m='1516970'>the</span> <span m='1517090'>system</span> <span
  m='1517480'>to</span> <span m='1517600'>characterize</span> <span
  m='1518430'>it</span> <span m='1519040'>is</span> <span m='1519700'>its</span>
  <span m='1519850'>response</span> <span m='1520480'>to</span> <span
  m='1520630'>a</span> <span m='1520660'>unit</span> <span
  m='1520960'>sample.</span> <span m='1521980'>If</span> <span
  m='1522130'>we</span> <span m='1522250'>have</span> <span
  m='1522430'>its</span> <span m='1522580'>response</span> <span
  m='1523060'>to</span> <span m='1523180'>a</span> <span m='1523210'>unit</span>
  <span m='1523540'>sample,</span> <span m='1524410'>we</span> <span
  m='1524530'>can</span> <span m='1524710'>construct</span> <span
  m='1525750'>y</span> <span m='1526070'>of n</span> <span m='1526430'>in</span>
  <span m='1526660'>general--</span> <span m='1527620'>that</span> <span
  m='1527830'>is,</span> <span m='1528100'>we</span> <span
  m='1528250'>can</span> <span m='1528400'>construct</span> <span
  m='1528910'>the</span> <span m='1529060'>output</span> <span
  m='1529900'>for</span> <span m='1530230'>an</span> <span
  m='1530350'>arbitrary</span> <span m='1530980'>input,</span> <span
  m='1531340'>x</span> <span m='1531580'>of</span> <span m='1531670'>k.</span>
  </p><p><span m='1534670'>This</span> <span m='1534910'>is</span> <span
  m='1535090'>generally</span> <span m='1535870'>referred</span> <span
  m='1536350'>to</span> <span m='1536860'>as</span> <span m='1537520'>the</span>
  <span m='1537610'>convolution</span> <span m='1538390'>sum.</span> <span
  m='1540150'>In</span> <span m='1540280'>analogy</span> <span
  m='1541060'>with</span> <span m='1541330'>the</span> <span
  m='1541420'>convolution</span> <span m='1542170'>integral</span> <span
  m='1542860'>in</span> <span m='1543370'>the</span> <span
  m='1543580'>continuous</span> <span m='1544420'>time</span> <span
  m='1544750'>case,</span> <span m='1546550'>this</span> <span
  m='1546760'>is</span> <span m='1546910'>one</span> <span
  m='1547150'>way</span> <span m='1547360'>of</span> <span
  m='1547450'>writing</span> <span m='1547780'>the</span> <span
  m='1547870'>convolution</span> <span m='1548560'>sum.</span> <span
  m='1549880'>There</span> <span m='1550270'>is</span> <span
  m='1550450'>an</span> <span m='1550540'>alternative,</span> <span
  m='1551510'>which</span> <span m='1552250'>is</span> <span
  m='1553450'>interesting</span> <span m='1554170'>in</span> <span
  m='1554380'>that</span> <span m='1554830'>it</span> <span
  m='1555010'>suggests</span> <span m='1555610'>some</span> <span
  m='1556150'>important</span> <span m='1556600'>properties</span> <span
  m='1557350'>of</span> <span m='1557500'>linear</span> <span
  m='1557860'>shift</span> <span m='1558160'>invariant</span> <span
  m='1558670'>systems,</span> <span m='1559810'>and</span> <span
  m='1560020'>it's</span> <span m='1560170'>obtained</span> <span
  m='1560590'>simply</span> <span m='1561100'>by</span> <span
  m='1561340'>applying</span> <span m='1561790'>a</span> <span
  m='1561820'>substitution</span> <span m='1562600'>of</span> <span
  m='1562660'>variables</span> <span m='1563470'>to</span> <span
  m='1563620'>this</span> <span m='1563830'>expression.</span> </p><p><span
  m='1565120'>In</span> <span m='1565210'>particular,</span> <span
  m='1565970'>suppose</span> <span m='1566770'>that</span> <span
  m='1567430'>we</span> <span m='1568360'>replace</span> <span
  m='1569020'>n</span> <span m='1569290'>minus</span> <span m='1569710'>k</span>
  <span m='1570970'>by</span> <span m='1571420'>the</span> <span
  m='1571540'>variable</span> <span m='1572180'>r,</span> <span
  m='1573730'>or</span> <span m='1574900'>equivalently,</span> <span
  m='1576280'>k</span> <span m='1576880'>is</span> <span
  m='1577120'>equal</span> <span m='1577510'>to</span> <span
  m='1577990'>n</span> <span m='1578200'>minus</span> <span
  m='1578620'>r.</span> <span m='1580510'>Then</span> <span
  m='1581170'>what</span> <span m='1581380'>we</span> <span
  m='1581560'>obtain</span> <span m='1582460'>is</span> <span
  m='1583520'>y</span> <span m='1583620'>of</span> <span m='1583860'>n</span>
  <span m='1584890'>is</span> <span m='1585070'>now</span> <span
  m='1585430'>equal</span> <span m='1585790'>to</span> <span
  m='1586320'>a</span> <span m='1586420'>sum--</span> <span
  m='1587050'>and</span> <span m='1587170'>this</span> <span
  m='1587350'>is</span> <span m='1587440'>now</span> <span m='1587680'>a</span>
  <span m='1587710'>sum</span> <span m='1588020'>on</span> <span
  m='1588200'>r.</span> <span m='1589480'>For</span> <span m='1589660'>k,</span>
  <span m='1589930'>we</span> <span m='1590080'>have</span> <span
  m='1590320'>n</span> <span m='1590470'>minus</span> <span
  m='1590890'>r.</span> <span m='1591400'>So</span> <span
  m='1591640'>this</span> <span m='1591880'>is</span> <span m='1592210'>x</span>
  <span m='1592690'>of</span> <span m='1592990'>n</span> <span
  m='1593230'>minus</span> <span m='1593650'>r</span> <span
  m='1594910'>times</span> <span m='1595990'>h</span> <span
  m='1596416'>of</span> <span m='1597268'>n</span> <span
  m='1597694'>minus</span> <span m='1598120'>k,</span> <span
  m='1599000'>which</span> <span m='1599110'>is</span> <span
  m='1599230'>equal</span> <span m='1599830'>to</span> <span
  m='1600040'>r.</span> <span m='1601030'>So</span> <span
  m='1601630'>this</span> <span m='1601840'>h</span> <span m='1602020'>of</span>
  <span m='1602380'>r.</span> </p><p><span m='1604060'>Well,</span> <span
  m='1604450'>it's</span> <span m='1604570'>a</span> <span
  m='1604630'>simple</span> <span m='1604990'>step</span> <span
  m='1605650'>to</span> <span m='1605770'>take,</span> <span
  m='1606790'>but</span> <span m='1607090'>in</span> <span
  m='1607240'>fact,</span> <span m='1608200'>what</span> <span
  m='1608380'>it</span> <span m='1608470'>says</span> <span
  m='1609500'>is</span> <span m='1609790'>that</span> <span
  m='1611410'>the</span> <span m='1611530'>system</span> <span
  m='1612370'>doesn't</span> <span m='1612730'>particularly</span> <span
  m='1613420'>care</span> <span m='1614740'>what</span> <span
  m='1615190'>you</span> <span m='1615370'>call</span> <span
  m='1616180'>the</span> <span m='1616330'>input</span> <span
  m='1616660'>to</span> <span m='1616780'>the</span> <span
  m='1616900'>system,</span> <span m='1617560'>and</span> <span
  m='1617680'>what</span> <span m='1617920'>you</span> <span
  m='1618010'>call</span> <span m='1618610'>the</span> <span
  m='1618730'>unit</span> <span m='1618970'>sample</span> <span
  m='1619330'>response</span> <span m='1619810'>of</span> <span
  m='1619870'>the</span> <span m='1619960'>system.</span> <span
  m='1621780'>Said</span> <span m='1622060'>another</span> <span
  m='1622390'>way,</span> <span m='1623680'>it</span> <span
  m='1623800'>says</span> <span m='1624460'>that</span> <span
  m='1624880'>convolution</span> <span m='1626500'>is</span> <span
  m='1626710'>commutative--</span> <span m='1627760'>that</span> <span
  m='1628000'>is,</span> <span m='1628480'>if</span> <span m='1628660'>we</span>
  <span m='1628780'>represent</span> <span m='1630070'>the</span> <span
  m='1630160'>convolution</span> <span m='1631510'>of</span> <span
  m='1631660'>x</span> <span m='1631910'>of n</span> <span m='1632380'>with
  h</span> <span m='1632590'>of</span> <span m='1632995'>n</span> <span
  m='1633940'>with</span> <span m='1634060'>an</span> <span
  m='1634150'>asterisk,</span> <span m='1635800'>then,</span> <span
  m='1636220'>because</span> <span m='1636640'>of</span> <span
  m='1636730'>the</span> <span m='1636850'>fact</span> <span
  m='1637450'>that</span> <span m='1637840'>we</span> <span
  m='1638020'>were</span> <span m='1638170'>able</span> <span
  m='1638650'>to</span> <span m='1638770'>interchange</span> <span
  m='1639730'>the</span> <span m='1639850'>roles</span> <span
  m='1640330'>of</span> <span m='1640480'>x</span> <span m='1640750'>of</span>
  <span m='1641010'>n and</span> <span m='1641140'>h</span> <span
  m='1641360'>of</span> <span m='1641685'>n,</span> <span
  m='1642400'>that</span> <span m='1642580'>implies,</span> <span
  m='1643120'>essentially,</span> <span m='1644020'>that</span> <span
  m='1644620'>x</span> <span m='1644890'>of n</span> <span
  m='1645030'>convolved</span> <span m='1645850'>with</span> <span m='1645970'>h
  o</span> <span m='1646240'>n</span> <span m='1647020'>is</span> <span
  m='1647140'>the</span> <span m='1647230'>same</span> <span
  m='1647560'>thing</span> <span m='1648130'>as</span> <span
  m='1648530'>h</span> <span m='1648870'>of n</span> <span
  m='1649080'>convolved</span> <span m='1649340'>with</span> <span
  m='1649600'>x</span> <span m='1649880'>of n.</span> </p><p><span
  m='1651940'>That</span> <span m='1652930'>implies,</span> <span
  m='1653620'>as</span> <span m='1653830'>I</span> <span
  m='1653950'>indicated,</span> <span m='1654820'>that</span> <span
  m='1655120'>if</span> <span m='1655330'>we</span> <span m='1655450'>had</span>
  <span m='1655630'>a</span> <span m='1655660'>system</span> <span
  m='1657610'>with</span> <span m='1657760'>an</span> <span
  m='1657850'>impulse</span> <span m='1658300'>response</span> <span
  m='1659110'>or</span> <span m='1659230'>unit</span> <span
  m='1659470'>sample</span> <span m='1659890'>response,</span> <span
  m='1660690'>h of</span> <span m='1661125'>n,</span> <span
  m='1662060'>and</span> <span m='1662200'>input</span> <span
  m='1662530'>x</span> <span m='1662770'>of n,</span> <span
  m='1663970'>and</span> <span m='1664660'>output</span> <span
  m='1665200'>y</span> <span m='1665530'>of</span> <span m='1665690'>n,</span>
  <span m='1666670'>that</span> <span m='1667090'>if</span> <span
  m='1667270'>I</span> <span m='1667360'>call</span> <span
  m='1667720'>this</span> <span m='1667990'>the</span> <span
  m='1668170'>input,</span> <span m='1668960'>and</span> <span
  m='1668980'>I</span> <span m='1669040'>call</span> <span
  m='1669340'>this</span> <span m='1669790'>the</span> <span
  m='1670100'>unit</span> <span m='1670420'>sample</span> <span
  m='1670840'>response--</span> <span m='1671950'>as</span> <span
  m='1672100'>I've</span> <span m='1672280'>done</span> <span
  m='1672490'>here--</span> <span m='1673690'>we</span> <span
  m='1673840'>obtain</span> <span m='1674170'>the</span> <span
  m='1674260'>same</span> <span m='1674530'>output.</span> <span
  m='1675220'>That</span> <span m='1675400'>is,</span> <span m='1676030'>h
  of</span> <span m='1676495'>n</span> <span m='1677290'>into</span> <span
  m='1677560'>a</span> <span m='1677620'>system</span> <span
  m='1678340'>with</span> <span m='1678520'>unit</span> <span
  m='1678790'>sample</span> <span m='1679180'>response,</span> <span
  m='1679660'>x</span> <span m='1679960'>of n,</span> <span
  m='1680860'>gives</span> <span m='1681130'>us</span> <span m='1681520'>at
  the</span> <span m='1681700'>output,</span> <span m='1682240'>y</span> <span
  m='1682540'>of</span> <span m='1682660'>n,</span> <span
  m='1682810'>also.</span> </p><p><span m='1685600'>An</span> <span
  m='1685720'>implication</span> <span m='1686410'>of</span> <span
  m='1686500'>that</span> <span m='1687130'>is</span> <span
  m='1687400'>that</span> <span m='1688060'>linear</span> <span
  m='1688480'>shift</span> <span m='1688840'>invariant</span> <span
  m='1689440'>systems</span> <span m='1690190'>in</span> <span
  m='1690340'>cascade</span> <span m='1691600'>don't</span> <span
  m='1691840'>particularly</span> <span m='1692800'>care</span> <span
  m='1693940'>which</span> <span m='1694540'>order</span> <span
  m='1695050'>the</span> <span m='1695200'>systems</span> <span
  m='1695800'>are</span> <span m='1695950'>cascaded</span> <span
  m='1696670'>in.</span> <span m='1697300'>That</span> <span
  m='1697510'>is,</span> <span m='1698500'>if</span> <span m='1698740'>I</span>
  <span m='1698830'>have</span> <span m='1699010'>a</span> <span
  m='1699070'>system</span> <span m='1699730'>h 1</span> <span
  m='1699990'>of</span> <span m='1700250'>n--</span> <span
  m='1701470'>that</span> <span m='1701680'>is</span> <span
  m='1701800'>with</span> <span m='1701950'>unit</span> <span
  m='1702160'>sample</span> <span m='1702550'>response,</span> <span
  m='1703000'>h 1 of</span> <span m='1703250'>n--</span> <span
  m='1704360'>and</span> <span m='1704500'>cascade</span> <span
  m='1705460'>with</span> <span m='1705880'>a</span> <span
  m='1705910'>system</span> <span m='1706930'>with</span> <span
  m='1707080'>unit</span> <span m='1707380'>sample</span> <span
  m='1707800'>response</span> <span m='1708490'>h</span> <span m='1708710'>2
  of</span> <span m='1709210'>n,</span> <span m='1710710'>and</span> <span
  m='1711010'>input</span> <span m='1711400'>x of</span> <span
  m='1711760'>n,</span> <span m='1713470'>the</span> <span
  m='1713830'>unit</span> <span m='1714190'>sample</span> <span
  m='1714550'>response</span> <span m='1715090'>of</span> <span
  m='1715180'>this</span> <span m='1715360'>overall</span> <span
  m='1715870'>system</span> <span m='1716920'>is</span> <span m='1717160'>h 1
  of</span> <span m='1717640'>n</span> <span m='1718330'>convolved</span> <span
  m='1718870'>with</span> <span m='1719010'>h 2 of</span> <span
  m='1719470'>n.</span> <span m='1721090'>But</span> <span
  m='1721300'>since</span> <span m='1721540'>convolution</span> <span
  m='1722230'>is</span> <span m='1722350'>commutative,</span> <span
  m='1723250'>we</span> <span m='1723400'>could</span> <span
  m='1723520'>just</span> <span m='1723820'>as</span> <span
  m='1723970'>easily</span> <span m='1724400'>convolve</span> <span
  m='1724870'>h 2</span> <span m='1725330'>with</span> <span m='1725480'>h
  1,</span> <span m='1726700'>and</span> <span m='1726820'>that</span> <span
  m='1727030'>corresponds</span> <span m='1728230'>to</span> <span
  m='1728890'>a</span> <span m='1728980'>cascade</span> <span
  m='1729820'>of</span> <span m='1730450'>the</span> <span
  m='1730540'>system</span> <span m='1731200'>h 2</span> <span
  m='1731680'>of</span> <span m='1732080'>n</span> <span m='1732340'>with</span>
  <span m='1732640'>the</span> <span m='1732730'>system</span> <span
  m='1733150'>h 1 of</span> <span m='1733510'>n.</span> </p><p><span
  m='1734380'>So</span> <span m='1734980'>simply</span> <span
  m='1735460'>because</span> <span m='1735850'>of</span> <span
  m='1735940'>the</span> <span m='1736060'>fact</span> <span
  m='1736810'>that</span> <span m='1737320'>convolution</span> <span
  m='1738400'>is</span> <span m='1738610'>commutative,</span> <span
  m='1742020'>that</span> <span m='1742230'>implies</span> <span
  m='1743250'>that,</span> <span m='1744750'>for</span> <span
  m='1744990'>example,</span> <span m='1746010'>that</span> <span
  m='1747090'>linear</span> <span m='1747510'>shift</span> <span
  m='1747840'>invariant</span> <span m='1748320'>systems</span> <span
  m='1748830'>in</span> <span m='1748950'>cascade</span> <span
  m='1749860'>don't</span> <span m='1750060'>particularly</span> <span
  m='1750780'>care</span> <span m='1751320'>in</span> <span
  m='1751470'>which</span> <span m='1751710'>order</span> <span
  m='1752010'>their</span> <span m='1752190'>cascaded.</span> <span
  m='1753720'>There</span> <span m='1753840'>are</span> <span
  m='1753900'>lots</span> <span m='1754170'>of</span> <span
  m='1754260'>other</span> <span m='1754980'>properties</span> <span
  m='1755550'>of</span> <span m='1755670'>convolution</span> <span
  m='1756420'>and</span> <span m='1756510'>simple</span> <span
  m='1756840'>properties</span> <span m='1757620'>of</span> <span
  m='1757920'>linear</span> <span m='1758250'>shift</span> <span
  m='1758550'>invariant</span> <span m='1759060'>systems</span> <span
  m='1760200'>that</span> <span m='1760500'>are</span> <span
  m='1760670'>a</span> <span m='1761100'>direct</span> <span
  m='1761460'>consequence</span> <span m='1762600'>of</span> <span
  m='1763350'>convolution,</span> <span m='1764910'>and</span> <span
  m='1765420'>some</span> <span m='1765690'>of</span> <span
  m='1765990'>the</span> <span m='1766110'>properties</span> <span
  m='1766620'>that</span> <span m='1766710'>we've</span> <span
  m='1766860'>mentioned</span> <span m='1767300'>of</span> <span
  m='1767400'>convolution.</span> <span m='1768300'>And</span> <span
  m='1768690'>a</span> <span m='1768720'>number</span> <span
  m='1769050'>of</span> <span m='1769170'>these,</span> <span
  m='1769870'>we'll</span> <span m='1770010'>see</span> <span
  m='1770220'>in</span> <span m='1770310'>the</span> <span
  m='1770400'>lectures</span> <span m='1770970'>as</span> <span
  m='1771120'>we</span> <span m='1771240'>go</span> <span
  m='1771450'>along,</span> <span m='1772470'>and</span> <span
  m='1772950'>also</span> <span m='1773370'>a</span> <span
  m='1773430'>number</span> <span m='1773760'>of</span> <span
  m='1773850'>them</span> <span m='1774360'>you'll</span> <span
  m='1774570'>have</span> <span m='1774750'>a</span> <span
  m='1774810'>chance</span> <span m='1775290'>to</span> <span
  m='1775770'>wrestle</span> <span m='1776130'>with</span> <span
  m='1776880'>in</span> <span m='1777090'>the</span> <span
  m='1777180'>study</span> <span m='1777510'>guide.</span> </p><p><span
  m='1779780'>OK,</span> <span m='1780210'>so</span> <span
  m='1780900'>this</span> <span m='1781560'>is</span> <span m='1782070'>a</span>
  <span m='1782730'>development</span> <span m='1783330'>of</span> <span
  m='1783420'>the</span> <span m='1783510'>convolution</span> <span
  m='1784200'>sum.</span> <span m='1785790'>One</span> <span
  m='1786030'>of</span> <span m='1786360'>the</span> <span
  m='1786510'>important</span> <span m='1786930'>aspects</span> <span
  m='1787710'>of</span> <span m='1788160'>the</span> <span
  m='1788280'>convolution</span> <span m='1789030'>sum</span> <span
  m='1790500'>is</span> <span m='1791220'>the</span> <span
  m='1791610'>steps</span> <span m='1792090'>involved</span> <span
  m='1792900'>in</span> <span m='1793230'>actually</span> <span
  m='1793800'>computing</span> <span m='1794430'>it--</span> <span
  m='1794970'>that</span> <span m='1795150'>is,</span> <span
  m='1796410'>the</span> <span m='1796560'>manipulations</span> <span
  m='1797340'>involved</span> <span m='1797910'>in</span> <span
  m='1798030'>forming</span> <span m='1798510'>this</span> <span
  m='1798700'>sum.</span> <span m='1799650'>And</span> <span
  m='1800220'>as</span> <span m='1800610'>the</span> <span
  m='1800700'>last</span> <span m='1801000'>point</span> <span
  m='1801300'>that</span> <span m='1801420'>I'd</span> <span
  m='1801540'>like</span> <span m='1801750'>to</span> <span
  m='1801870'>make</span> <span m='1802080'>in</span> <span
  m='1802170'>this</span> <span m='1802350'>lecture,</span> <span
  m='1803410'>I'd</span> <span m='1803430'>like</span> <span
  m='1803730'>to</span> <span m='1804120'>illustrate,</span> <span
  m='1804870'>first</span> <span m='1805590'>with</span> <span
  m='1806220'>a</span> <span m='1806810'>viewgraph,</span> <span
  m='1807600'>and</span> <span m='1809310'>then</span> <span
  m='1810000'>with</span> <span m='1810240'>a</span> <span
  m='1810300'>movie,</span> <span m='1811560'>the</span> <span
  m='1812310'>computation,</span> <span m='1813390'>or</span> <span
  m='1813630'>the</span> <span m='1813750'>implementation,</span> <span
  m='1814740'>of</span> <span m='1814890'>the</span> <span
  m='1814980'>convolution</span> <span m='1815630'>sum.</span> </p><p><span
  m='1816600'>So</span> <span m='1817170'>let's</span> <span
  m='1817500'>return</span> <span m='1818010'>to</span> <span
  m='1818190'>the</span> <span m='1818820'>viewgraph.</span> </p><p><span
  m='1830850'>And</span> <span m='1831360'>I've</span> <span
  m='1831750'>indicated</span> <span m='1832440'>here,</span> <span
  m='1833640'>again,</span> <span m='1834300'>the</span> <span
  m='1834570'>convolution</span> <span m='1835350'>sum</span> <span
  m='1835920'>as--</span> <span m='1836550'>we've</span> <span
  m='1836790'>derived</span> <span m='1837280'>it--</span> <span m='1837990'>y
  of</span> <span m='1838230'>n</span> <span m='1838560'>is</span> <span
  m='1838680'>the</span> <span m='1838800'>sum</span> <span
  m='1839130'>of</span> <span m='1839250'>x</span> <span m='1839490'>of</span>
  <span m='1839610'>k</span> <span m='1840090'>h</span> <span m='1840390'>of
  n</span> <span m='1840720'>minus</span> <span m='1841050'>k.</span> <span
  m='1841980'>Now,</span> <span m='1842340'>in</span> <span
  m='1842490'>implementing</span> <span m='1843030'>the</span> <span
  m='1843120'>convolution</span> <span m='1843840'>sum,</span> <span
  m='1844890'>let</span> <span m='1845040'>me</span> <span
  m='1845190'>stress</span> <span m='1846180'>that</span> <span
  m='1847410'>it</span> <span m='1847620'>is</span> <span m='1849540'>for</span>
  <span m='1849750'>n,</span> <span m='1850350'>which</span> <span
  m='1850590'>is</span> <span m='1850740'>the</span> <span
  m='1850860'>independent</span> <span m='1851460'>variable</span> <span
  m='1852120'>for</span> <span m='1852270'>which</span> <span
  m='1852540'>we</span> <span m='1852600'>are</span> <span
  m='1852660'>computing</span> <span m='1853710'>the</span> <span
  m='1853830'>output--</span> <span m='1854370'>that</span> <span
  m='1854550'>is,</span> <span m='1855250'>k</span> <span m='1855720'>is</span>
  <span m='1855900'>just</span> <span m='1856080'>simply</span> <span
  m='1856620'>a</span> <span m='1856710'>dummy</span> <span
  m='1857070'>variable</span> <span m='1858090'>inside</span> <span
  m='1858630'>this</span> <span m='1858780'>summation.</span> </p><p><span
  m='1860670'>Well,</span> <span m='1861120'>I've</span> <span
  m='1861300'>illustrated</span> <span m='1861960'>here,</span> <span
  m='1863190'>for a</span> <span m='1863550'>specific</span> <span
  m='1864180'>example,</span> <span m='1865430'>a</span> <span
  m='1865500'>sequence,</span> <span m='1866160'>x</span> <span
  m='1866490'>of</span> <span m='1866590'>k,</span> <span
  m='1868080'>which</span> <span m='1868590'>is</span> <span
  m='1869220'>a</span> <span m='1869310'>constant</span> <span
  m='1870480'>from</span> <span m='1870720'>0</span> <span m='1871430'>to</span>
  <span m='1871950'>I</span> <span m='1872070'>guess</span> <span
  m='1872550'>n</span> <span m='1872730'>equals</span> <span
  m='1873090'>10,</span> <span m='1874920'>equal</span> <span
  m='1875250'>to</span> <span m='1875370'>unity</span> <span
  m='1876420'>for</span> <span m='1876720'>n</span> <span
  m='1876840'>equals</span> <span m='1877080'>0</span> <span
  m='1877560'>to</span> <span m='1877800'>10,</span> <span
  m='1878610'>and</span> <span m='1878730'>0</span> <span
  m='1879330'>otherwise.</span> <span m='1880660'>And</span> <span
  m='1880890'>I've</span> <span m='1881490'>indicated</span> <span
  m='1882150'>the</span> <span m='1882330'>sequence</span> <span
  m='1883080'>a</span> <span m='1883110'>little</span> <span
  m='1883350'>differently</span> <span m='1883860'>here</span> <span
  m='1884130'>than</span> <span m='1884310'>I</span> <span
  m='1884400'>had</span> <span m='1884610'>previously,</span> <span
  m='1886110'>since</span> <span m='1886470'>I</span> <span
  m='1886560'>want</span> <span m='1886830'>to</span> <span
  m='1887070'>distinguish</span> <span m='1887700'>between</span> <span
  m='1888120'>the</span> <span m='1888240'>x's,</span> <span
  m='1888720'>h's,</span> <span m='1889290'>and</span> <span
  m='1889410'>the</span> <span m='1889500'>y's.</span> <span
  m='1890610'>The</span> <span m='1890700'>sequence</span> <span
  m='1891150'>x</span> <span m='1891390'>of</span> <span m='1891510'>k,</span>
  <span m='1891870'>I'm</span> <span m='1892230'>denoting</span> <span
  m='1893310'>with</span> <span m='1893490'>little</span> <span
  m='1893730'>x's--</span> <span m='1895020'>the</span> <span
  m='1895140'>sequence</span> <span m='1895460'>h,</span> <span
  m='1895780'>I'll</span> <span m='1895980'>denote</span> <span
  m='1896070'>note</span> <span m='1896250'>with</span> <span
  m='1896380'>little</span> <span m='1896640'>h's,</span> <span
  m='1897630'>and</span> <span m='1898020'>later</span> <span
  m='1898350'>on,</span> <span m='1898560'>the</span> <span
  m='1898650'>sequence</span> <span m='1899130'>y,</span> <span
  m='1899880'>we'll</span> <span m='1900060'>denote</span> <span
  m='1900360'>with</span> <span m='1900510'>little</span> <span
  m='1900690'>y's.</span> </p><p><span m='1902190'>All</span> <span
  m='1902270'>right,</span> <span m='1902430'>so</span> <span
  m='1903180'>here</span> <span m='1903390'>we</span> <span
  m='1903570'>have</span> <span m='1904350'>the</span> <span
  m='1904440'>sequence</span> <span m='1904785'>a,</span> <span
  m='1906870'>that's</span> <span m='1907140'>this</span> <span
  m='1907380'>one.</span> <span m='1908790'>And</span> <span
  m='1909720'>plotted</span> <span m='1910770'>as</span> <span
  m='1910980'>a</span> <span m='1911040'>function</span> <span
  m='1911490'>of</span> <span m='1911580'>k.</span> <span
  m='1913530'>Here,</span> <span m='1914100'>I</span> <span
  m='1914580'>have</span> <span m='1915090'>the</span> <span
  m='1915210'>sequence,</span> <span m='1915810'>h</span> <span
  m='1916080'>of</span> <span m='1916200'>k,</span> <span
  m='1917130'>which</span> <span m='1917490'>I've</span> <span
  m='1917640'>chosen</span> <span m='1918090'>to</span> <span
  m='1918240'>be</span> <span m='1918390'>an</span> <span
  m='1918480'>exponential</span> <span m='1919290'>for</span> <span
  m='1919470'>k</span> <span m='1919710'>greater</span> <span
  m='1920070'>than</span> <span m='1920250'>0,</span> <span
  m='1920880'>and</span> <span m='1921030'>0</span> <span m='1921660'>for</span>
  <span m='1921840'>k</span> <span m='1922080'>less</span> <span
  m='1922380'>than</span> <span m='1922530'>0.</span> <span
  m='1923460'>But</span> <span m='1923700'>it's</span> <span
  m='1923910'>not</span> <span m='1924210'>h</span> <span m='1924450'>of</span>
  <span m='1924540'>k</span> <span m='1925290'>that</span> <span
  m='1925530'>we</span> <span m='1925710'>want</span> <span
  m='1925980'>in</span> <span m='1926100'>this</span> <span
  m='1926220'>sum.</span> <span m='1927360'>It's</span> <span m='1927630'>h
  of</span> <span m='1928120'>n</span> <span m='1928610'>minus</span> <span
  m='1929100'>k.</span> </p><p><span m='1929840'>And</span> <span
  m='1929980'>what's</span> <span m='1930320'>n?</span> <span
  m='1930930'>Well,</span> <span m='1931290'>n</span> <span
  m='1931680'>is</span> <span m='1931860'>whatever</span> <span
  m='1932310'>value</span> <span m='1933390'>of</span> <span
  m='1933480'>the</span> <span m='1933630'>output</span> <span
  m='1933990'>sequence</span> <span m='1934470'>we're</span> <span
  m='1934590'>trying</span> <span m='1934890'>to</span> <span
  m='1935010'>compute.</span> <span m='1936340'>So</span> <span
  m='1936750'>if</span> <span m='1936930'>n</span> <span m='1937080'>was</span>
  <span m='1937260'>equal</span> <span m='1937590'>to</span> <span
  m='1937710'>0,</span> <span m='1938400'>for</span> <span
  m='1938610'>example,</span> <span m='1940000'>we</span> <span
  m='1940080'>would</span> <span m='1940290'>want</span> <span
  m='1940530'>the</span> <span m='1940620'>sequence,</span> <span
  m='1941310'>h</span> <span m='1941700'>of</span> <span m='1942000'>0</span>
  <span m='1942810'>minus</span> <span m='1943210'>k.</span> <span
  m='1943680'>And</span> <span m='1943920'>that's</span> <span
  m='1944190'>this</span> <span m='1944700'>sequence.</span> </p><p><span
  m='1945880'>It's</span> <span m='1946290'>h</span> <span m='1946590'>of</span>
  <span m='1946810'>k,</span> <span m='1947730'>flipped</span> <span
  m='1948180'>around</span> <span m='1948600'>in</span> <span
  m='1948730'>k,</span> <span m='1950040'>because</span> <span
  m='1950700'>of</span> <span m='1950850'>this</span> <span
  m='1951060'>minus</span> <span m='1951450'>sign,</span> <span
  m='1952410'>and</span> <span m='1952500'>not</span> <span
  m='1952740'>shifted</span> <span m='1953190'>one</span> <span
  m='1953430'>way</span> <span m='1953580'>or</span> <span
  m='1953670'>the</span> <span m='1953850'>other</span> <span
  m='1954300'>simply</span> <span m='1954720'>because</span> <span
  m='1955110'>we</span> <span m='1955230'>have</span> <span m='1955480'>a
  0</span> <span m='1955920'>here.</span> <span m='1956890'>So</span> <span
  m='1957570'>here's</span> <span m='1957870'>h</span> <span
  m='1958110'>of</span> <span m='1958230'>k,</span> <span m='1959280'>but</span>
  <span m='1959430'>that's</span> <span m='1959700'>not</span> <span
  m='1959910'>what</span> <span m='1960270'>you</span> <span
  m='1960420'>want.</span> <span m='1960870'>It's</span> <span
  m='1961100'>h</span> <span m='1961400'>of</span> <span m='1962290'>0</span>
  <span m='1962760'>minus</span> <span m='1963240'>k.</span> <span
  m='1964260'>And</span> <span m='1964470'>now</span> <span
  m='1964740'>to</span> <span m='1964890'>compute</span> <span
  m='1965700'>y</span> <span m='1966060'>of</span> <span m='1966180'>0,</span>
  <span m='1967690'>we</span> <span m='1967740'>would</span> <span
  m='1967890'>multiply</span> <span m='1968610'>this</span> <span
  m='1968820'>sequence</span> <span m='1970140'>by</span> <span
  m='1970380'>this</span> <span m='1970650'>one,</span> <span
  m='1971910'>and</span> <span m='1972180'>compute</span> <span
  m='1972600'>the</span> <span m='1972720'>sum</span> <span
  m='1973320'>from</span> <span m='1973550'>minus</span> <span
  m='1973890'>infinity</span> <span m='1974400'>to</span> <span
  m='1974520'>plus</span> <span m='1974790'>infinity.</span> <span
  m='1975720'>That</span> <span m='1975870'>would</span> <span
  m='1976020'>give</span> <span m='1976230'>us</span> <span
  m='1976380'>the</span> <span m='1976500'>value,</span> <span
  m='1977220'>y</span> <span m='1977520'>of</span> <span m='1977610'>0.</span>
  </p><p><span m='1978810'>For</span> <span m='1979320'>a</span> <span
  m='1979380'>different</span> <span m='1979710'>value</span> <span
  m='1980100'>of</span> <span m='1980220'>n,</span> <span m='1981060'>we</span>
  <span m='1981210'>would</span> <span m='1981330'>have</span> <span
  m='1981600'>to</span> <span m='1981930'>look</span> <span
  m='1982230'>at</span> <span m='1982500'>h of</span> <span m='1982900'>n</span>
  <span m='1983300'>minus</span> <span m='1983700'>k,</span> <span
  m='1984030'>for</span> <span m='1984210'>whichever</span> <span
  m='1984630'>value</span> <span m='1985020'>of</span> <span
  m='1985140'>n</span> <span m='1985290'>we</span> <span m='1985440'>were</span>
  <span m='1985560'>computing</span> <span m='1986070'>this</span> <span
  m='1986280'>for.</span> <span m='1986960'>For</span> <span
  m='1987300'>example,</span> <span m='1988150'>if</span> <span
  m='1988290'>n</span> <span m='1988440'>is</span> <span
  m='1988590'>equal</span> <span m='1988860'>to</span> <span
  m='1989010'>minus</span> <span m='1989430'>4,</span> <span
  m='1990660'>the</span> <span m='1990750'>sequence</span> <span
  m='1991260'>that</span> <span m='1991380'>we</span> <span
  m='1991560'>want</span> <span m='1992070'>is</span> <span m='1992370'>h</span>
  <span m='1992610'>of</span> <span m='1993030'>minus 4</span> <span
  m='1993450'>minus</span> <span m='1993870'>k,</span> <span
  m='1994830'>and</span> <span m='1995010'>that</span> <span
  m='1995340'>is</span> <span m='1996030'>this</span> <span
  m='1996240'>sequence</span> <span m='1997050'>shifted</span> <span
  m='1997860'>to</span> <span m='1997980'>the</span> <span
  m='1998100'>left</span> <span m='1998700'>by</span> <span
  m='1998910'>4.</span> <span m='1999930'>So</span> <span m='2000770'>to</span>
  <span m='2000890'>compute</span> <span m='2001580'>y</span> <span
  m='2002180'>of</span> <span m='2002450'>minus</span> <span
  m='2002900'>4,</span> <span m='2003800'>we</span> <span
  m='2003920'>want</span> <span m='2004190'>this</span> <span
  m='2004370'>sequence</span> <span m='2005450'>multiplied</span> <span
  m='2006410'>by</span> <span m='2006590'>this</span> <span
  m='2006860'>one,</span> <span m='2008060'>and</span> <span
  m='2008210'>the</span> <span m='2008300'>sum</span> <span
  m='2008570'>computed</span> <span m='2009260'>from</span> <span
  m='2009470'>minus</span> <span m='2009830'>infinity</span> <span
  m='2010310'>to</span> <span m='2010430'>plus</span> <span
  m='2010700'>infinity.</span> </p><p><span m='2011570'>And</span> <span
  m='2012050'>you</span> <span m='2012200'>can</span> <span
  m='2012320'>see,</span> <span m='2012560'>obviously,</span> <span
  m='2013670'>for</span> <span m='2013820'>that</span> <span
  m='2014000'>particular</span> <span m='2014540'>case--</span> <span
  m='2014960'>that</span> <span m='2015140'>is</span> <span m='2015500'>n</span>
  <span m='2016010'>equal</span> <span m='2016370'>to</span> <span
  m='2016490'>minus</span> <span m='2016910'>4--</span> <span
  m='2017750'>the</span> <span m='2017870'>product</span> <span
  m='2018320'>of</span> <span m='2018440'>this</span> <span
  m='2018890'>and</span> <span m='2019010'>this</span> <span
  m='2019250'>is</span> <span m='2019310'>0,</span> <span m='2020300'>and</span>
  <span m='2020540'>the</span> <span m='2020630'>sum</span> <span
  m='2020900'>will</span> <span m='2021020'>be</span> <span
  m='2021230'>equal</span> <span m='2021410'>to</span> <span
  m='2021530'>0.</span> </p><p><span m='2021730'>Well,</span> <span
  m='2024170'>let's</span> <span m='2024560'>look</span> <span
  m='2024890'>at</span> <span m='2025340'>this</span> <span
  m='2025550'>example</span> <span m='2027630'>a</span> <span
  m='2027730'>little</span> <span m='2027800'>more</span> <span
  m='2028010'>dynamically,</span> <span m='2029180'>with</span> <span
  m='2029600'>a</span> <span m='2029660'>movie</span> <span
  m='2030290'>that</span> <span m='2030740'>was</span> <span
  m='2031190'>prepared</span> <span m='2032120'>at</span> <span
  m='2032360'>Bell</span> <span m='2032600'>Telephone</span> <span
  m='2033110'>Laboratories</span> <span m='2034370'>by</span> <span
  m='2034520'>Dr.</span> <span m='2034850'>Ronald</span> <span
  m='2035260'>Shaefer.</span> </p><p></p><p></p><p><span m='2046710'>OK,</span>
  <span m='2046860'>the</span> <span m='2047000'>convolution</span> <span
  m='2047670'>sum,</span> <span m='2047970'>then,</span> <span
  m='2048449'>we</span> <span m='2048630'>have</span> <span
  m='2048960'>is</span> <span m='2049110'>the</span> <span
  m='2049199'>sum</span> <span m='2049500'>of</span> <span m='2049590'>x</span>
  <span m='2049830'>of k,</span> <span m='2049949'>h of</span> <span
  m='2050370'>n</span> <span m='2050909'>minus</span> <span
  m='2051300'>k.</span> <span m='2052469'>And</span> <span m='2053159'>so</span>
  <span m='2053670'>what</span> <span m='2053850'>we</span> <span
  m='2054000'>would</span> <span m='2054090'>like</span> <span
  m='2054300'>to</span> <span m='2054389'>illustrate</span> <span
  m='2055110'>is</span> <span m='2055590'>the</span> <span
  m='2055739'>operation</span> <span m='2056580'>of</span> <span
  m='2056790'>evaluating</span> <span m='2058050'>this</span> <span
  m='2058199'>sum.</span> <span m='2059370'>On</span> <span
  m='2059460'>the</span> <span m='2059550'>top,</span> <span
  m='2059889'>we</span> <span m='2060060'>have</span> <span m='2060659'>x</span>
  <span m='2060929'>of</span> <span m='2061060'>k.</span> <span
  m='2061770'>On</span> <span m='2061889'>the</span> <span
  m='2061980'>bottom</span> <span m='2062400'>we</span> <span
  m='2062550'>have</span> <span m='2062760'>h</span> <span m='2063030'>of</span>
  <span m='2063150'>k--</span> <span m='2063420'>he</span> <span
  m='2063690'>of</span> <span m='2064095'>k</span> <span
  m='2064500'>being</span> <span m='2064739'>an</span> <span
  m='2064830'>exponential.</span> <span m='2066300'>And</span> <span
  m='2066480'>now,</span> <span m='2067139'>we</span> <span
  m='2067260'>see</span> <span m='2067949'>h</span> <span m='2068199'>of
  minus</span> <span m='2068556'>k,</span> <span m='2069270'>namely</span> <span
  m='2069690'>h</span> <span m='2069960'>of</span> <span m='2070050'>k</span>
  <span m='2070350'>flipped</span> <span m='2070710'>over.</span> <span
  m='2071909'>As</span> <span m='2072090'>we</span> <span
  m='2072210'>shift</span> <span m='2072630'>h</span> <span
  m='2072929'>of</span> <span m='2073020'>k</span> <span m='2073260'>to</span>
  <span m='2073409'>the</span> <span m='2073500'>left,</span> <span
  m='2074730'>corresponding</span> <span m='2075330'>to</span> <span
  m='2075400'>n</span> <span m='2075489'>equals</span> <span
  m='2075780'>minus</span> <span m='2076230'>1,</span> <span
  m='2077020'>then</span> <span m='2077130'>back</span> <span
  m='2077400'>to</span> <span m='2077550'>0,</span> <span m='2079260'>and</span>
  <span m='2079380'>now</span> <span m='2079710'>to</span> <span
  m='2079889'>the</span> <span m='2080010'>right.</span> </p><p><span
  m='2082969'>So</span> <span m='2083320'>we</span> <span
  m='2083469'>have</span> <span m='2083679'>h</span> <span m='2083920'>of</span>
  <span m='2084040'>1</span> <span m='2084310'>minus</span> <span
  m='2084719'>k.</span> <span m='2085929'>And</span> <span
  m='2086920'>then</span> <span m='2087219'>to</span> <span m='2087370'>4</span>
  <span m='2087600'>y</span> <span m='2087750'>of</span> <span
  m='2088040'>n,</span> <span m='2088719'>we</span> <span
  m='2088870'>want</span> <span m='2089110'>the</span> <span
  m='2089199'>product</span> <span m='2090159'>of</span> <span
  m='2090520'>h</span> <span m='2090830'>of minus</span> <span
  m='2091200'>k</span> <span m='2091570'>shifted</span> <span
  m='2092590'>with</span> <span m='2092949'>x</span> <span m='2093250'>of</span>
  <span m='2093370'>k,</span> <span m='2094120'>that</span> <span
  m='2094300'>product</span> <span m='2094750'>sum</span> <span
  m='2095110'>from</span> <span m='2095350'>minus</span> <span
  m='2095710'>infinity</span> <span m='2096219'>to</span> <span
  m='2096340'>plus</span> <span m='2096639'>infinity.</span> <span
  m='2098360'>So</span> <span m='2098380'>here,</span> <span
  m='2098560'>we</span> <span m='2098710'>see</span> <span m='2099040'>x</span>
  <span m='2099280'>of</span> <span m='2099400'>k</span> <span
  m='2099820'>times</span> <span m='2100710'>h</span> <span
  m='2101050'>of</span> <span m='2101620'>1</span> <span
  m='2101830'>minus</span> <span m='2102190'>k,</span> <span
  m='2102640'>2</span> <span m='2102880'>minus</span> <span
  m='2103300'>k,</span> <span m='2104230'>3</span> <span
  m='2104560'>minus</span> <span m='2104920'>k,</span> <span m='2105220'>et
  cetera.</span> <span m='2106300'>Those</span> <span
  m='2106540'>multiplied</span> <span m='2107230'>and</span> <span
  m='2107350'>then</span> <span m='2107500'>summed</span> <span
  m='2107890'>from</span> <span m='2108070'>minus</span> <span
  m='2108430'>infinity</span> <span m='2108880'>to</span> <span
  m='2108970'>plus</span> <span m='2109270'>infinity,</span> <span
  m='2112480'>we</span> <span m='2112580'>see</span> <span
  m='2112680'>during</span> <span m='2112780'>this</span> <span
  m='2112880'>portion</span> <span m='2112980'>that</span> <span
  m='2113080'>more</span> <span m='2113180'>and</span> <span
  m='2113280'>more</span> <span m='2113380'>values</span> <span
  m='2113740'>of</span> <span m='2113860'>h</span> <span m='2114250'>are</span>
  <span m='2114400'>engaged</span> <span m='2114910'>with</span> <span
  m='2115060'>non-0</span> <span m='2115690'>values</span> <span
  m='2116170'>of</span> <span m='2116290'>x,</span> <span m='2116770'>and</span>
  <span m='2116920'>so</span> <span m='2117130'>y</span> <span
  m='2117430'>of</span> <span m='2117550'>n</span> <span
  m='2117730'>grows</span> <span m='2118780'>until</span> <span
  m='2119380'>we</span> <span m='2119560'>reach</span> <span
  m='2119950'>the</span> <span m='2120070'>point</span> <span
  m='2120490'>where</span> <span m='2120700'>values</span> <span
  m='2121240'>fall</span> <span m='2121540'>off</span> <span
  m='2121720'>the</span> <span m='2121870'>end</span> <span
  m='2122740'>of</span> <span m='2123340'>the</span> <span
  m='2123550'>non-0</span> <span m='2124150'>values</span> <span
  m='2124630'>of</span> <span m='2124750'>x,</span> <span
  m='2125500'>where</span> <span m='2125890'>y</span> <span
  m='2126250'>of</span> <span m='2126400'>n</span> <span
  m='2126670'>decays.</span> </p><p><span m='2128320'>So</span> <span
  m='2128620'>this,</span> <span m='2128890'>then,</span> <span m='2130270'>is
  an</span> <span m='2130390'>illustration</span> <span m='2131410'>of</span>
  <span m='2132190'>the</span> <span m='2132280'>linear</span> <span
  m='2132670'>convolution</span> <span m='2133780'>of</span> <span
  m='2134620'>x</span> <span m='2134890'>of</span> <span m='2135010'>k</span>
  <span m='2135790'>with</span> <span m='2136000'>h of</span> <span
  m='2136330'>k.</span> </p><p><span m='2140830'>OK,</span> <span
  m='2141360'>this</span> <span m='2141600'>completes</span> <span
  m='2142320'>our</span> <span m='2142860'>introduction</span> <span
  m='2143850'>to</span> <span m='2144420'>discrete</span> <span
  m='2144870'>time</span> <span m='2145350'>signals</span> <span
  m='2145860'>and</span> <span m='2145980'>systems.</span> <span
  m='2147150'>There</span> <span m='2148080'>were</span> <span
  m='2148350'>a</span> <span m='2148410'>number</span> <span
  m='2148740'>of</span> <span m='2148860'>important</span> <span
  m='2150060'>points</span> <span m='2150480'>that</span> <span
  m='2150630'>we've</span> <span m='2150810'>made</span> <span
  m='2151500'>during</span> <span m='2151770'>this</span> <span
  m='2151950'>lecture.</span> <span m='2153010'>But</span> <span
  m='2153120'>the</span> <span m='2153210'>key</span> <span
  m='2153450'>result,</span> <span m='2154320'>and</span> <span
  m='2155010'>the</span> <span m='2156270'>result</span> <span
  m='2156990'>that</span> <span m='2157290'>it's</span> <span
  m='2157500'>important</span> <span m='2157980'>to</span> <span
  m='2158130'>develop</span> <span m='2158520'>some</span> <span
  m='2158670'>experience</span> <span m='2159390'>with,</span> <span
  m='2160290'>is</span> <span m='2160620'>the</span> <span
  m='2160740'>convolution</span> <span m='2161430'>sum.</span> </p><p><span
  m='2163140'>Next</span> <span m='2163440'>time,</span> <span
  m='2164160'>we'll</span> <span m='2164850'>introduce</span> <span
  m='2165330'>some</span> <span m='2165540'>additional</span> <span
  m='2165960'>considerations,</span> <span m='2167490'>namely</span> <span
  m='2168060'>the</span> <span m='2168180'>considerations</span> <span
  m='2169290'>of</span> <span m='2169590'>stability</span> <span
  m='2170190'>and</span> <span m='2170280'>causality</span> <span
  m='2171510'>for</span> <span m='2171630'>discrete</span> <span
  m='2172020'>time</span> <span m='2172350'>systems.</span> <span
  m='2173760'>And</span> <span m='2174230'>we'll</span> <span
  m='2174480'>also</span> <span m='2175230'>discuss,</span> <span
  m='2175800'>briefly,</span> <span m='2176460'>the</span> <span
  m='2176580'>class</span> <span m='2177150'>of</span> <span
  m='2177330'>linear</span> <span m='2177660'>shift</span> <span
  m='2177960'>invariant</span> <span m='2178530'>systems</span> <span
  m='2179670'>that</span> <span m='2180210'>are</span> <span
  m='2180450'>represented</span> <span m='2181410'>by</span> <span
  m='2181980'>linear</span> <span m='2182580'>constant</span> <span
  m='2183060'>coefficient</span> <span m='2183660'>difference</span> <span
  m='2184050'>equations.</span> </p><p><span m='2185320'>Finally,</span> <span
  m='2185970'>we'll</span> <span m='2186570'>try</span> <span
  m='2186810'>to</span> <span m='2186930'>tie</span> <span
  m='2187230'>some</span> <span m='2187470'>of</span> <span
  m='2187560'>this</span> <span m='2187770'>together</span> <span
  m='2189220'>and</span> <span m='2189470'>in</span> <span
  m='2189690'>particular,</span> <span m='2191310'>present</span> <span
  m='2192120'>what</span> <span m='2192450'>will</span> <span
  m='2192600'>be</span> <span m='2192750'>called</span> <span
  m='2193140'>the</span> <span m='2193260'>frequency</span> <span
  m='2193770'>response</span> <span m='2194400'>of</span> <span
  m='2194550'>the</span> <span m='2194640'>systems.</span> <span
  m='2195660'>And</span> <span m='2196050'>this</span> <span
  m='2196290'>will</span> <span m='2196440'>eventually</span> <span
  m='2196890'>lead</span> <span m='2197280'>into</span> <span
  m='2197580'>a</span> <span m='2197610'>discussion</span> <span
  m='2198360'>of</span> <span m='2198460'>Fourier</span> <span
  m='2198870'>transforms.</span> <span m='2200146'>Thank you.</span>
  </p><p></p><p><span m='2202626'>[MUSIC PLAYING]</span> </p><p></p>
embedded_media:
  - uid: 7d2257580e542e72484fb71db7187630
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: MITRES_6_008S11_lec02.pdf
    title: MITRES_6_008S11_lec02.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-2-discrete-time-signals-and-systems-part-1/MITRES_6_008S11_lec02.pdf
  - uid: 656016e3647e6178fa94157b7603c3f3
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: TuCYGjp7WKU
  - uid: 1b5369b77072c955f8d60a3817ed2b95
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-2-discrete-time-signals/id481803782?i=108361999
  - uid: e34226eb29f6934e1e96e8fde0d8c4d9
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec02_300k.mp4'
  - uid: 09d9b052bb125ad42a4cf31318ab87b1
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/TuCYGjp7WKU/default.jpg'
  - uid: 7d38b30a39d9e336231604ea44a089c2
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: TuCYGjp7WKU
  - uid: 746c52429f8c5338a1e3d68d47043bc1
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: TuCYGjp7WKU.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-2-discrete-time-signals-and-systems-part-1/TuCYGjp7WKU.srt
  - uid: 3cf3faafccd8d4b9e42edc574386fecc
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: TuCYGjp7WKU.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-2-discrete-time-signals-and-systems-part-1/TuCYGjp7WKU.pdf
  - uid: a47696539b613c194d7aaa2e514db234
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: fca6fc5cf6192614729cbf33064839f7
    parent_uid: 3c54b2e23f5a897cbee4f090666b233a
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
