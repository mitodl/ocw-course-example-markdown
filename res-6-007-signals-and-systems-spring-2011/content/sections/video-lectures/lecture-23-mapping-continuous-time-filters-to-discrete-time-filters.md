---
order_index: null
title: 'Lecture 23: Mapping Continuous-Time Filters to Discrete-Time Filters'
template_type: Tabbed
uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
parent_uid: a781d5ac598bc6063ba6ac8138e446cf
technical_location: >-
  https://ocw.mit.edu/resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-23-mapping-continuous-time-filters-to-discrete-time-filters
short_url: lecture-23-mapping-continuous-time-filters-to-discrete-time-filters
inline_embed_id: '96546394lecture23:mappingcontinuous-timefilterstodiscrete-timefilters5013188'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Properties of the z-transform; Analyzing
  systems characterized by linear constant-coefficient difference equations;
  Transformations between continuous-time and discrete-time systems, impulse
  invariance, backward difference approximation to differential equations.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Mapping Continuous-time Filters to Discrete-time Filters (<img
  src="/images/inacessible.gif" alt="This resource may not render correctly in a
  screen reader." /><a target="_blank"
  href="./resolveuid/7247d3ddec258fb20a5be9203c106f01">PDF</a>)</p>
transcript: >-
  <p><span m='40'>The</span> <span m='150'>following</span> <span
  m='600'>content</span> <span m='1190'>is</span> <span m='1310'>provided</span>
  <span m='1750'>under</span> <span m='2040'>a</span> <span
  m='2060'>Creative</span> <span m='2470'>Commons</span> <span
  m='2870'>license.</span> <span m='3880'>Your</span> <span
  m='4160'>support</span> <span m='4670'>will</span> <span m='4840'>help</span>
  <span m='5070'>MIT</span> <span m='5540'>OpenCourseWare</span> <span
  m='6320'>continue</span> <span m='6830'>to</span> <span m='6920'>offer</span>
  <span m='7340'>high</span> <span m='7560'>quality</span> <span
  m='8090'>educational</span> <span m='8700'>resources</span> <span
  m='9350'>for</span> <span m='9490'>free.</span> <span m='10570'>To</span>
  <span m='10700'>make</span> <span m='10900'>a</span> <span
  m='10950'>donation</span> <span m='11580'>or</span> <span
  m='11890'>view</span> <span m='12310'>additional</span> <span
  m='12770'>materials</span> <span m='13310'>from</span> <span
  m='13470'>hundreds</span> <span m='13900'>of</span> <span m='14000'>MIT</span>
  <span m='14430'>courses,</span> <span m='15440'>visit</span> <span
  m='15760'>MIT</span> <span m='16190'>OpenCourseWare</span> <span
  m='17220'>at</span> <span m='19290'>ocw.mit.edu.</span> </p><p><span
  m='20600'>[MUSIC PLAYING]</span> </p><p><span m='55444'>PROFESSOR:</span>
  <span m='55870'>Last</span> <span m='56160'>time,</span> <span
  m='56470'>we</span> <span m='56640'>began</span> <span m='57060'>the</span>
  <span m='57250'>discussion</span> <span m='58360'>of</span> <span
  m='58510'>the</span> <span m='58610'>z-transform.</span> <span
  m='61240'>As</span> <span m='61520'>with</span> <span m='61780'>the</span>
  <span m='61880'>Laplace</span> <span m='62420'>transform</span> <span
  m='62765'>in</span> <span m='63110'>continuous</span> <span
  m='63700'>time,</span> <span m='64010'>we</span> <span
  m='64110'>developed</span> <span m='64629'>it</span> <span m='64879'>as</span>
  <span m='65360'>a</span> <span m='65430'>generalization</span> <span
  m='66190'>of</span> <span m='66570'>the</span> <span m='66900'>Fourier</span>
  <span m='67380'>transform.</span> <span m='69000'>The</span> <span
  m='69420'>expression</span> <span m='70270'>that</span> <span
  m='70420'>we</span> <span m='70560'>got</span> <span m='70950'>for</span>
  <span m='71020'>the</span> <span m='71100'>z-transform</span> <span
  m='72280'>is</span> <span m='73380'>the</span> <span m='73860'>sum</span>
  <span m='74230'>that</span> <span m='74350'>I</span> <span
  m='74460'>indicate</span> <span m='74980'>here.</span> <span
  m='77050'>We</span> <span m='77270'>also</span> <span m='77510'>briefly</span>
  <span m='77990'>talked</span> <span m='78350'>about</span> <span
  m='78840'>an</span> <span m='79110'>inverse</span> <span
  m='79760'>z-transform</span> <span m='80750'>integral</span> <span
  m='81430'>and</span> <span m='81650'>some</span> <span m='81830'>other</span>
  <span m='82600'>informal</span> <span m='83450'>methods</span> <span
  m='84430'>of</span> <span m='84780'>computing</span> <span
  m='85320'>the</span> <span m='85430'>inverse</span> <span
  m='86010'>z-transform.</span> <span m='87660'>But</span> <span
  m='88040'>we</span> <span m='88580'>focused</span> <span m='89170'>in</span>
  <span m='89250'>particular</span> <span m='90060'>on</span> <span
  m='90810'>the</span> <span m='91020'>relationship</span> <span
  m='91830'>between</span> <span m='92220'>the</span> <span
  m='92300'>z-transform</span> <span m='93470'>and</span> <span
  m='93600'>the</span> <span m='93680'>Fourier</span> <span
  m='94190'>transform,</span> <span m='95680'>pointing</span> <span
  m='96090'>out</span> <span m='96570'>first</span> <span m='96910'>of</span>
  <span m='97020'>all</span> <span m='97570'>that</span> <span
  m='98370'>the</span> <span m='98470'>z-transform,</span> <span
  m='100620'>when</span> <span m='101240'>we</span> <span
  m='101420'>choose</span> <span m='101800'>the</span> <span
  m='101900'>magnitude</span> <span m='102520'>of</span> <span
  m='102600'>z</span> <span m='103480'>equal</span> <span m='103880'>to</span>
  <span m='104000'>1--</span> <span m='104590'>so</span> <span
  m='104960'>the</span> <span m='105050'>magnitude</span> <span
  m='105580'>of</span> <span m='105650'>z</span> <span m='106070'>of</span>
  <span m='106190'>the</span> <span m='106280'>form</span> <span
  m='106650'>e</span> <span m='106800'>to</span> <span m='106880'>the</span>
  <span m='106980'>j</span> <span m='107330'>omega--</span> <span
  m='108440'>just</span> <span m='108700'>simply</span> <span
  m='109600'>reduces</span> <span m='110820'>to</span> <span
  m='111530'>the</span> <span m='111630'>Fourier</span> <span
  m='112150'>transform</span> <span m='112880'>of</span> <span
  m='112970'>the</span> <span m='113050'>sequence.</span> </p><p><span
  m='115210'>Then,</span> <span m='115740'>in</span> <span
  m='116120'>addition,</span> <span m='116770'>we</span> <span
  m='117510'>explored</span> <span m='117775'>the</span> <span
  m='118040'>z-transform</span> <span m='119240'>for</span> <span
  m='119460'>z,</span> <span m='119910'>a</span> <span m='119970'>more</span>
  <span m='120160'>general</span> <span m='120650'>complex</span> <span
  m='121260'>number.</span> <span m='122640'>In</span> <span
  m='122820'>the</span> <span m='123110'>discrete</span> <span
  m='123520'>time</span> <span m='123790'>z-transform</span> <span
  m='124670'>case,</span> <span m='125520'>we</span> <span
  m='125900'>expressed</span> <span m='126390'>that</span> <span
  m='126610'>complex</span> <span m='127190'>number</span> <span
  m='127710'>in</span> <span m='127820'>polar</span> <span
  m='128199'>form</span> <span m='129050'>as</span> <span m='129270'>r</span>
  <span m='129445'>e</span> <span m='129970'>to</span> <span
  m='130030'>the</span> <span m='130139'>j</span> <span m='130430'>omega,</span>
  <span m='132130'>and</span> <span m='132870'>recognize</span> <span
  m='134090'>that</span> <span m='134680'>the</span> <span
  m='134780'>z-transform</span> <span m='135670'>expression</span> <span
  m='136900'>in</span> <span m='137080'>fact</span> <span
  m='137800'>corresponds</span> <span m='138900'>to</span> <span
  m='139670'>the</span> <span m='139770'>Fourier</span> <span
  m='140340'>transform</span> <span m='141340'>of</span> <span
  m='141940'>the</span> <span m='142040'>sequence</span> <span
  m='142900'>exponentially</span> <span m='143670'>weighted.</span> <span
  m='145400'>Because</span> <span m='145890'>of</span> <span
  m='146250'>the</span> <span m='146400'>exponential</span> <span
  m='147040'>weighting,</span> <span m='148440'>the</span> <span
  m='149130'>z-transform</span> <span m='150610'>converges</span> <span
  m='151840'>for</span> <span m='152010'>some</span> <span
  m='152580'>values</span> <span m='153100'>of</span> <span m='153240'>r</span>
  <span m='153760'>corresponding</span> <span m='154470'>to</span> <span
  m='154590'>some</span> <span m='155100'>exponential</span> <span
  m='155770'>waiting,</span> <span m='156630'>and</span> <span
  m='156830'>perhaps</span> <span m='157290'>not</span> <span
  m='157700'>for</span> <span m='157930'>others,</span> <span
  m='158710'>and</span> <span m='159320'>that</span> <span m='159690'>led</span>
  <span m='160090'>to</span> <span m='160250'>a</span> <span
  m='160300'>notion</span> <span m='161150'>which</span> <span
  m='162470'>corresponded</span> <span m='163390'>to</span> <span
  m='163980'>the</span> <span m='164420'>region</span> <span
  m='164790'>of</span> <span m='164890'>convergence</span> <span
  m='166190'>associated</span> <span m='167150'>with</span> <span
  m='167360'>the</span> <span m='167430'>z-transform.</span> <span
  m='169180'>We</span> <span m='169360'>talked</span> <span
  m='169790'>some</span> <span m='170070'>about</span> <span
  m='170580'>properties</span> <span m='171140'>of</span> <span
  m='171210'>the</span> <span m='171300'>region</span> <span
  m='171590'>of</span> <span m='171680'>convergence,</span> <span
  m='172640'>particularly</span> <span m='173410'>in</span> <span
  m='173510'>relation</span> <span m='174080'>to</span> <span
  m='175230'>the</span> <span m='175410'>pole-zero</span> <span
  m='176010'>pattern.</span> </p><p><span m='177900'>Now,</span> <span
  m='178490'>they</span> <span m='178750'>z-transform</span> <span
  m='179910'>has</span> <span m='180950'>a</span> <span m='181040'>number</span>
  <span m='181620'>of</span> <span m='182140'>important</span> <span
  m='182610'>and</span> <span m='182690'>useful</span> <span
  m='183090'>properties,</span> <span m='183720'>just</span> <span
  m='184040'>as</span> <span m='184190'>the</span> <span
  m='184300'>Laplace</span> <span m='184740'>transform</span> <span
  m='185360'>does.</span> <span m='186780'>As</span> <span m='186960'>one</span>
  <span m='187170'>part</span> <span m='187440'>of</span> <span
  m='187520'>this</span> <span m='187730'>lecture,</span> <span
  m='188230'>what</span> <span m='188480'>we'll</span> <span
  m='188860'>want</span> <span m='189120'>to</span> <span m='189210'>do</span>
  <span m='190010'>is</span> <span m='190580'>exploit</span> <span
  m='191330'>some</span> <span m='191630'>of</span> <span
  m='191710'>these</span> <span m='191930'>properties</span> <span
  m='193160'>in</span> <span m='193330'>the</span> <span
  m='193420'>context</span> <span m='194190'>of</span> <span
  m='194440'>systems</span> <span m='194930'>described</span> <span
  m='195450'>by</span> <span m='195570'>linear</span> <span
  m='195920'>constant</span> <span m='196340'>coefficient</span> <span
  m='196930'>difference</span> <span m='197260'>equations.</span> <span
  m='199360'>These</span> <span m='199860'>particular</span> <span
  m='200450'>properties</span> <span m='201230'>that</span> <span
  m='201690'>play</span> <span m='202780'>an</span> <span
  m='202910'>important</span> <span m='203330'>role</span> <span
  m='203600'>in</span> <span m='203660'>that</span> <span
  m='203900'>context</span> <span m='204590'>are</span> <span
  m='204660'>the</span> <span m='204730'>properties</span> <span
  m='205280'>that</span> <span m='205400'>I</span> <span
  m='205470'>indicate</span> <span m='205990'>here.</span> <span
  m='207570'>In</span> <span m='207760'>particular,</span> <span
  m='208430'>there</span> <span m='208900'>is--</span> <span
  m='209500'>as</span> <span m='209980'>with</span> <span
  m='210240'>continuous</span> <span m='210880'>time--</span> <span
  m='211780'>a</span> <span m='212320'>linearity</span> <span
  m='212520'>property</span> <span m='213180'>that</span> <span
  m='213370'>tells</span> <span m='213720'>us</span> <span
  m='214350'>that</span> <span m='214610'>the</span> <span
  m='214870'>z-transform</span> <span m='216500'>of</span> <span
  m='216630'>a</span> <span m='216680'>linear</span> <span
  m='217070'>combination</span> <span m='217790'>of</span> <span
  m='217860'>sequences</span> <span m='219600'>is</span> <span
  m='219700'>the</span> <span m='219790'>same</span> <span
  m='220410'>linear</span> <span m='220870'>combination</span> <span
  m='221520'>of</span> <span m='221590'>the</span> <span
  m='221670'>z-transforms,</span> <span m='224240'>a</span> <span
  m='224340'>shifting</span> <span m='225140'>property</span> <span
  m='225940'>that</span> <span m='227010'>indicates</span> <span
  m='227800'>that</span> <span m='228290'>the</span> <span
  m='228660'>z-transform</span> <span m='229820'>of</span> <span
  m='229960'>x</span> <span m='230270'>of</span> <span m='230380'>n</span> <span
  m='230580'>shifted</span> <span m='231620'>is</span> <span
  m='232310'>the</span> <span m='232400'>z</span> <span
  m='232650'>transform</span> <span m='233620'>of</span> <span
  m='233940'>x</span> <span m='234066'>of</span> <span m='234193'>n</span> <span
  m='235070'>multiplied</span> <span m='236000'>by</span> <span
  m='236210'>a</span> <span m='236280'>factor</span> <span m='236740'>z</span>
  <span m='236960'>to</span> <span m='237020'>the</span> <span
  m='237110'>minus</span> <span m='237520'>n</span> <span m='237710'>0.</span>
  <span m='239780'>Then</span> <span m='240210'>the</span> <span
  m='240580'>convolution</span> <span m='241330'>property</span> <span
  m='242560'>for</span> <span m='242730'>which</span> <span
  m='243460'>the</span> <span m='244170'>z-transform</span> <span
  m='245830'>of</span> <span m='245980'>a</span> <span
  m='246120'>convolution</span> <span m='246870'>of</span> <span
  m='246940'>sequences</span> <span m='248100'>is</span> <span
  m='249020'>the</span> <span m='249520'>product</span> <span
  m='250220'>of</span> <span m='250480'>the</span> <span
  m='250580'>associated</span> <span m='251500'>z-transforms.</span>
  </p><p><span m='254250'>With</span> <span m='254640'>all</span> <span
  m='254880'>of</span> <span m='254960'>these</span> <span
  m='255190'>properties,</span> <span m='255990'>of</span> <span
  m='256120'>course,</span> <span m='256519'>there</span> <span
  m='256850'>is</span> <span m='257050'>again</span> <span m='257630'>the</span>
  <span m='257769'>issue</span> <span m='258240'>of</span> <span
  m='258920'>what</span> <span m='259250'>the</span> <span
  m='259380'>associated</span> <span m='260019'>region</span> <span
  m='260320'>of</span> <span m='260410'>convergence</span> <span
  m='261029'>is</span> <span m='261510'>in</span> <span
  m='261760'>comparison</span> <span m='262400'>with</span> <span
  m='262530'>the</span> <span m='262610'>region</span> <span
  m='262880'>of</span> <span m='262970'>convergence</span> <span
  m='263720'>of</span> <span m='263840'>the</span> <span
  m='263940'>original</span> <span m='264300'>sequences.</span> <span
  m='266500'>That</span> <span m='266820'>is</span> <span m='267570'>an</span>
  <span m='267710'>issue</span> <span m='267950'>that's</span> <span
  m='268150'>addressed</span> <span m='268680'>somewhat</span> <span
  m='269400'>more</span> <span m='269810'>in</span> <span m='269930'>the</span>
  <span m='270040'>text</span> <span m='270450'>and</span> <span
  m='270550'>let's</span> <span m='270770'>not</span> <span m='270970'>go</span>
  <span m='271130'>into</span> <span m='271380'>it</span> <span
  m='271430'>here.</span> </p><p><span m='274240'>With</span> <span
  m='274630'>the</span> <span m='275170'>convolution</span> <span
  m='275990'>property,</span> <span m='278380'>the</span> <span
  m='278770'>convolution</span> <span m='279470'>property</span> <span
  m='280250'>as</span> <span m='280710'>in</span> <span
  m='280890'>continuous</span> <span m='281570'>time,</span> <span
  m='282610'>of</span> <span m='282700'>course,</span> <span
  m='283000'>provides</span> <span m='283480'>a</span> <span
  m='283540'>mechanism</span> <span m='284750'>for</span> <span
  m='285220'>dealing</span> <span m='285990'>with</span> <span
  m='286430'>linear</span> <span m='286810'>time</span> <span
  m='287130'>invariant</span> <span m='287690'>systems.</span> <span
  m='288750'>In</span> <span m='288930'>particular,</span> <span
  m='290030'>in</span> <span m='290170'>the</span> <span m='290280'>time</span>
  <span m='290600'>domain</span> <span m='291330'>a</span> <span
  m='291430'>linear</span> <span m='291790'>time</span> <span
  m='292080'>invariant</span> <span m='292640'>system</span> <span
  m='293250'>is</span> <span m='293540'>described</span> <span
  m='294190'>through</span> <span m='294980'>convolution--</span> <span
  m='295980'>namely,</span> <span m='296710'>the</span> <span
  m='297000'>output</span> <span m='297640'>is</span> <span
  m='297850'>the</span> <span m='297940'>convolution</span> <span
  m='299150'>of</span> <span m='299550'>the</span> <span m='299730'>input</span>
  <span m='300430'>and</span> <span m='300610'>the</span> <span
  m='300700'>impulse</span> <span m='301170'>response.</span> <span
  m='302770'>Because</span> <span m='303400'>of</span> <span
  m='303630'>the</span> <span m='304090'>convolution</span> <span
  m='304830'>property</span> <span m='305880'>associated</span> <span
  m='306580'>with</span> <span m='306750'>the</span> <span
  m='306810'>z-transform,</span> <span m='308740'>the</span> <span
  m='308820'>z-transform</span> <span m='309810'>of</span> <span
  m='309900'>the</span> <span m='310060'>output</span> <span
  m='310920'>is</span> <span m='311255'>the</span> <span
  m='311590'>z-transform</span> <span m='312680'>of</span> <span
  m='312790'>the</span> <span m='312900'>input</span> <span
  m='313690'>times</span> <span m='314410'>the</span> <span
  m='314500'>z-transform</span> <span m='315650'>of</span> <span
  m='315820'>the</span> <span m='315930'>impulse</span> <span
  m='316380'>response.</span> <span m='317580'>Again,</span> <span
  m='318310'>very</span> <span m='318540'>much</span> <span
  m='318800'>the</span> <span m='318900'>same</span> <span m='319390'>as</span>
  <span m='320110'>what</span> <span m='320370'>we</span> <span
  m='320500'>had</span> <span m='321000'>in</span> <span
  m='321240'>continuous</span> <span m='321850'>time</span> <span
  m='322410'>and</span> <span m='322860'>also</span> <span
  m='323340'>what</span> <span m='323560'>we</span> <span m='323710'>had</span>
  <span m='324580'>in</span> <span m='325120'>the</span> <span
  m='325280'>context</span> <span m='325840'>of</span> <span
  m='325920'>the</span> <span m='326000'>discussion</span> <span
  m='326460'>with</span> <span m='326590'>the</span> <span
  m='326660'>Fourier</span> <span m='327110'>transform.</span> </p><p><span
  m='329410'>In</span> <span m='329560'>fact,</span> <span
  m='330430'>because</span> <span m='330850'>of</span> <span
  m='330960'>the</span> <span m='331040'>relationship</span> <span
  m='331870'>between</span> <span m='332230'>the</span> <span
  m='332290'>z-transform</span> <span m='332870'>and</span> <span
  m='333220'>the</span> <span m='333300'>Fourier</span> <span
  m='333790'>transform,</span> <span m='335240'>the</span> <span
  m='335330'>z-transform</span> <span m='336740'>of</span> <span
  m='337280'>the</span> <span m='337460'>impulse</span> <span
  m='337920'>response</span> <span m='339690'>evaluated</span> <span
  m='340490'>on</span> <span m='340610'>the</span> <span m='340700'>unit</span>
  <span m='341010'>circle--</span> <span m='341690'>in</span> <span
  m='341840'>other</span> <span m='342010'>words,</span> <span
  m='342310'>for</span> <span m='342400'>the</span> <span
  m='342500'>magnitude</span> <span m='343040'>of</span> <span
  m='343135'>z</span> <span m='343230'>equal</span> <span m='343630'>to</span>
  <span m='343740'>1--</span> <span m='344570'>in</span> <span
  m='344730'>fact</span> <span m='345440'>corresponds</span> <span
  m='346380'>to</span> <span m='346960'>the</span> <span
  m='347070'>frequency</span> <span m='347620'>response</span> <span
  m='348110'>of</span> <span m='348190'>the</span> <span
  m='348270'>system.</span> <span m='350060'>More</span> <span
  m='350260'>generally,</span> <span m='351050'>when</span> <span
  m='351210'>we</span> <span m='351330'>talk</span> <span
  m='351620'>about</span> <span m='351900'>the</span> <span
  m='351970'>z-transform</span> <span m='353110'>of</span> <span
  m='353280'>the</span> <span m='353400'>impulse</span> <span
  m='353860'>response,</span> <span m='355090'>we</span> <span
  m='355660'>will</span> <span m='355860'>refer</span> <span
  m='356240'>to</span> <span m='356470'>it</span> <span m='356700'>as</span>
  <span m='357390'>the</span> <span m='357800'>system</span> <span
  m='358300'>function</span> <span m='359020'>associated</span> <span
  m='359730'>with</span> <span m='359910'>the</span> <span
  m='359970'>system.</span> </p><p><span m='363130'>Now,</span> <span
  m='363390'>the</span> <span m='363510'>convolution</span> <span
  m='364140'>property</span> <span m='364590'>and</span> <span
  m='364670'>these</span> <span m='364860'>other</span> <span
  m='365070'>properties,</span> <span m='365860'>as</span> <span
  m='366030'>I</span> <span m='366110'>indicated,</span> <span
  m='367110'>we</span> <span m='367710'>will</span> <span m='367870'>find</span>
  <span m='368200'>useful</span> <span m='368840'>in</span> <span
  m='368980'>talking</span> <span m='369420'>about</span> <span
  m='369740'>systems</span> <span m='370390'>which</span> <span
  m='370610'>are</span> <span m='370680'>described</span> <span
  m='371800'>by</span> <span m='371980'>linear</span> <span
  m='372310'>constant</span> <span m='372690'>coefficient</span> <span
  m='373260'>difference</span> <span m='373600'>equations,</span> <span
  m='374680'>and</span> <span m='375420'>in</span> <span m='375560'>fact,</span>
  <span m='376130'>we'll</span> <span m='376820'>do</span> <span
  m='376990'>that</span> <span m='377250'>shortly.</span> <span
  m='378460'>But</span> <span m='378820'>first</span> <span
  m='379120'>what</span> <span m='379230'>I'd</span> <span
  m='379350'>like</span> <span m='379560'>to</span> <span m='379670'>do</span>
  <span m='380110'>is</span> <span m='381120'>to</span> <span
  m='382210'>continue</span> <span m='383290'>to</span> <span
  m='383500'>focus</span> <span m='384140'>on</span> <span m='384860'>the</span>
  <span m='385320'>system</span> <span m='385770'>function</span> <span
  m='386780'>for</span> <span m='386980'>linear</span> <span
  m='387300'>time</span> <span m='387560'>invariant</span> <span
  m='388070'>systems,</span> <span m='389120'>and</span> <span
  m='389270'>make</span> <span m='389470'>a</span> <span
  m='389530'>couple</span> <span m='389830'>of</span> <span
  m='389930'>comments</span> <span m='390670'>that</span> <span
  m='391150'>tie</span> <span m='391630'>back</span> <span m='392050'>to</span>
  <span m='392700'>some</span> <span m='392900'>things</span> <span
  m='393220'>that</span> <span m='393350'>we</span> <span m='393470'>said</span>
  <span m='393930'>in</span> <span m='394050'>the</span> <span
  m='394140'>last</span> <span m='394510'>lecture</span> <span
  m='395620'>relating</span> <span m='396240'>to</span> <span
  m='396820'>the</span> <span m='396950'>relationship</span> <span
  m='398280'>between</span> <span m='399340'>the</span> <span
  m='399900'>region</span> <span m='400300'>of</span> <span
  m='400390'>convergence</span> <span m='401290'>of</span> <span
  m='401430'>a</span> <span m='401480'>system,</span> <span
  m='402290'>or--</span> <span m='403510'>I'm</span> <span
  m='403630'>sorry,</span> <span m='403870'>the</span> <span
  m='403970'>region</span> <span m='404240'>of</span> <span
  m='404320'>convergence</span> <span m='405380'>of</span> <span
  m='405520'>a</span> <span m='405560'>z-transform--</span> <span
  m='407080'>and</span> <span m='407900'>the</span> <span
  m='408270'>issue</span> <span m='409070'>of</span> <span
  m='411030'>where</span> <span m='411330'>that</span> <span
  m='411520'>is</span> <span m='411800'>in</span> <span
  m='411930'>relation</span> <span m='412410'>to</span> <span
  m='412740'>the</span> <span m='413430'>poles</span> <span m='413940'>of</span>
  <span m='414040'>the</span> <span m='414110'>z-transform.</span> </p><p><span
  m='416980'>In</span> <span m='417140'>particular,</span> <span
  m='417900'>we</span> <span m='418110'>can</span> <span m='418350'>draw</span>
  <span m='418600'>some</span> <span m='418810'>conclusions</span> <span
  m='419620'>tying</span> <span m='419910'>back</span> <span
  m='420170'>to</span> <span m='420260'>that</span> <span
  m='420480'>discussion</span> <span m='421650'>about</span> <span
  m='422320'>the</span> <span m='423270'>pole</span> <span
  m='423590'>locations</span> <span m='424590'>of</span> <span
  m='425220'>the</span> <span m='425320'>system</span> <span
  m='425780'>function</span> <span m='427310'>in</span> <span
  m='427480'>relation</span> <span m='428370'>to</span> <span
  m='428900'>whether</span> <span m='429410'>the</span> <span
  m='429560'>system</span> <span m='430240'>is</span> <span
  m='430960'>stable</span> <span m='431810'>and</span> <span
  m='431980'>whether</span> <span m='432690'>the</span> <span
  m='432790'>system</span> <span m='433370'>is</span> <span
  m='433730'>causal.</span> <span m='435510'>In</span> <span
  m='435650'>particular,</span> <span m='436530'>recall</span> <span
  m='437280'>from</span> <span m='438190'>one</span> <span m='438360'>of</span>
  <span m='438440'>the</span> <span m='438600'>early</span> <span
  m='438860'>lectures</span> <span m='439420'>way</span> <span
  m='439620'>back</span> <span m='439960'>when</span> <span
  m='440850'>that</span> <span m='441420'>stability</span> <span
  m='442120'>for</span> <span m='442265'>a</span> <span m='442410'>system</span>
  <span m='444190'>corresponded</span> <span m='445560'>to</span> <span
  m='445720'>the</span> <span m='445830'>statement</span> <span
  m='446540'>that</span> <span m='447100'>the</span> <span
  m='447340'>impulse</span> <span m='447850'>response</span> <span
  m='448500'>is</span> <span m='448690'>absolutely</span> <span
  m='449230'>summable.</span> <span m='451450'>Furthermore,</span> <span
  m='452370'>when</span> <span m='452530'>we</span> <span
  m='452660'>talked</span> <span m='453050'>about</span> <span
  m='453600'>the</span> <span m='453760'>Fourier</span> <span
  m='454270'>transform,</span> <span m='455640'>the</span> <span
  m='455740'>Fourier</span> <span m='456240'>transform</span> <span
  m='457220'>of</span> <span m='458080'>a</span> <span
  m='458170'>sequence</span> <span m='459330'>converges</span> <span
  m='460740'>if</span> <span m='461770'>the</span> <span
  m='462220'>sequence</span> <span m='462890'>is</span> <span
  m='463030'>absolutely</span> <span m='463570'>summable.</span> <span
  m='464500'>So</span> <span m='464780'>in</span> <span m='464860'>fact,</span>
  <span m='465560'>the</span> <span m='465900'>condition</span> <span
  m='466340'>for</span> <span m='466500'>stability</span> <span
  m='468580'>of</span> <span m='469060'>a</span> <span m='469170'>system</span>
  <span m='470250'>and</span> <span m='470530'>the</span> <span
  m='470630'>condition</span> <span m='471090'>for</span> <span
  m='471230'>convergence</span> <span m='471870'>of</span> <span
  m='471950'>the</span> <span m='472020'>Fourier</span> <span
  m='472460'>transform</span> <span m='473230'>of</span> <span
  m='473400'>its</span> <span m='473540'>impulse</span> <span
  m='473980'>response</span> <span m='475930'>are</span> <span
  m='476590'>the</span> <span m='476680'>same</span> <span
  m='477050'>condition,</span> <span m='477640'>namely</span> <span
  m='478280'>absolute</span> <span m='478820'>summability.</span> </p><p><span
  m='480900'>Now</span> <span m='481350'>what</span> <span
  m='481530'>does</span> <span m='481660'>this</span> <span
  m='481890'>mean?</span> <span m='482750'>What</span> <span
  m='482910'>it</span> <span m='483030'>means</span> <span m='483740'>is</span>
  <span m='484080'>that</span> <span m='484680'>if</span> <span
  m='485180'>the</span> <span m='485290'>Fourier</span> <span
  m='485700'>transform</span> <span m='486600'>converges,</span> <span
  m='487870'>that</span> <span m='488120'>means</span> <span
  m='488520'>that</span> <span m='488690'>the</span> <span
  m='488760'>z-transform</span> <span m='489840'>converges</span> <span
  m='490820'>on</span> <span m='491050'>the</span> <span m='491140'>unit</span>
  <span m='491450'>circle.</span> <span m='493640'>Consequently,</span> <span
  m='494650'>if</span> <span m='494790'>the</span> <span
  m='494880'>system</span> <span m='495280'>is</span> <span
  m='495380'>stable,</span> <span m='496660'>then</span> <span
  m='497460'>the</span> <span m='497710'>system</span> <span
  m='498200'>function,</span> <span m='499360'>the</span> <span
  m='499440'>z-transform</span> <span m='499925'>or</span> <span
  m='500210'>the</span> <span m='500320'>impulse</span> <span
  m='500730'>response,</span> <span m='501740'>must</span> <span
  m='502500'>also</span> <span m='503370'>converge</span> <span
  m='504060'>on</span> <span m='504250'>the</span> <span m='504350'>unit</span>
  <span m='504640'>circle.</span> <span m='505210'>In</span> <span
  m='505330'>other</span> <span m='505530'>words,</span> <span
  m='506320'>the</span> <span m='506470'>impulse</span> <span
  m='506960'>response</span> <span m='507690'>must</span> <span
  m='507960'>have</span> <span m='508130'>a</span> <span
  m='508180'>Fourier</span> <span m='508610'>transform</span> <span
  m='509520'>that</span> <span m='509750'>converges.</span> <span
  m='511160'>So</span> <span m='511640'>for</span> <span m='511870'>a</span>
  <span m='511920'>stable</span> <span m='512360'>system,</span> <span
  m='513490'>then,</span> <span m='514419'>the</span> <span
  m='515150'>region</span> <span m='515520'>of</span> <span
  m='515610'>convergence</span> <span m='516409'>of</span> <span
  m='516549'>the</span> <span m='516630'>system</span> <span
  m='517049'>function</span> <span m='518070'>must</span> <span
  m='518530'>include</span> <span m='519049'>the</span> <span
  m='519130'>unit</span> <span m='519450'>circle</span> <span
  m='520169'>in</span> <span m='520320'>the</span> <span
  m='520390'>z-plane.</span> </p><p><span m='522620'>So</span> <span
  m='523210'>we</span> <span m='523340'>see</span> <span m='523679'>how</span>
  <span m='524270'>stability</span> <span m='525410'>relates</span> <span
  m='526640'>to</span> <span m='527140'>the</span> <span
  m='527600'>location</span> <span m='528450'>of</span> <span
  m='529260'>the</span> <span m='530080'>region</span> <span
  m='530410'>of</span> <span m='530500'>convergence,</span> <span
  m='531710'>and</span> <span m='531970'>we</span> <span m='532090'>can</span>
  <span m='532230'>also</span> <span m='532550'>relate</span> <span
  m='532920'>causality</span> <span m='533980'>to</span> <span
  m='534450'>the</span> <span m='534540'>region</span> <span
  m='534860'>of</span> <span m='534940'>convergence.</span> <span
  m='535670'>In</span> <span m='535810'>particular,</span> <span
  m='536900'>we</span> <span m='537080'>know</span> <span m='537650'>that</span>
  <span m='538110'>if</span> <span m='538510'>a</span> <span
  m='538600'>system</span> <span m='539210'>is</span> <span
  m='539420'>causal,</span> <span m='541140'>then</span> <span
  m='541700'>the</span> <span m='541850'>impulse</span> <span
  m='542320'>response</span> <span m='543010'>is</span> <span
  m='543190'>right-sided.</span> <span m='545980'>For</span> <span
  m='546110'>a</span> <span m='546240'>sequence</span> <span
  m='546407'>that's</span> <span m='546910'>right-sided,</span> <span
  m='547770'>the</span> <span m='547860'>region</span> <span
  m='548160'>of</span> <span m='548250'>convergence</span> <span
  m='549030'>of</span> <span m='549240'>its</span> <span
  m='549430'>z-transform</span> <span m='550670'>must</span> <span
  m='550950'>be</span> <span m='551120'>outside</span> <span
  m='552060'>the</span> <span m='552220'>outermost</span> <span
  m='552760'>pole.</span> <span m='555110'>So</span> <span m='555630'>for</span>
  <span m='555790'>causality,</span> <span m='556860'>the</span> <span
  m='557400'>region</span> <span m='557690'>of</span> <span
  m='557750'>convergence</span> <span m='558290'>of</span> <span
  m='558370'>the</span> <span m='558440'>system</span> <span
  m='558800'>function</span> <span m='559200'>must</span> <span
  m='559390'>be</span> <span m='559520'>outside</span> <span
  m='559970'>the</span> <span m='560110'>outermost</span> <span
  m='560630'>pole.</span> <span m='561710'>For</span> <span
  m='562430'>stability,</span> <span m='563610'>the</span> <span
  m='563720'>region</span> <span m='564030'>of</span> <span
  m='564100'>convergence</span> <span m='564670'>must</span> <span
  m='564890'>include</span> <span m='565260'>the</span> <span
  m='565350'>unit</span> <span m='565650'>circle,</span> <span
  m='566750'>and</span> <span m='568470'>we</span> <span m='568620'>can</span>
  <span m='568760'>also</span> <span m='569140'>then</span> <span
  m='569370'>draw</span> <span m='569600'>from</span> <span
  m='569820'>that</span> <span m='570060'>the</span> <span
  m='570150'>conclusion</span> <span m='571170'>that</span> <span
  m='571480'>if</span> <span m='571770'>we</span> <span m='571900'>have</span>
  <span m='572140'>a</span> <span m='572190'>system</span> <span
  m='572880'>that's</span> <span m='573170'>causal</span> <span
  m='573500'>unstable,</span> <span m='574840'>then</span> <span
  m='575090'>all</span> <span m='575430'>poles</span> <span
  m='575870'>must</span> <span m='576120'>be</span> <span
  m='576330'>inside</span> <span m='577190'>the</span> <span
  m='577280'>unit</span> <span m='577580'>circle</span> <span
  m='578610'>because</span> <span m='579240'>of</span> <span
  m='579340'>the</span> <span m='579430'>fact</span> <span
  m='579950'>that</span> <span m='580120'>the</span> <span
  m='580200'>poles</span> <span m='580630'>must--</span> <span
  m='581130'>because</span> <span m='581580'>of</span> <span
  m='581640'>the</span> <span m='581720'>fact</span> <span
  m='582260'>that</span> <span m='582400'>the</span> <span
  m='582480'>region</span> <span m='582800'>of</span> <span
  m='582880'>convergence</span> <span m='583560'>must</span> <span
  m='583860'>be</span> <span m='584420'>outside</span> <span
  m='584930'>the</span> <span m='585050'>outermost</span> <span
  m='585580'>pole</span> <span m='586400'>and</span> <span m='586550'>has</span>
  <span m='586830'>to</span> <span m='587150'>also</span> <span
  m='587480'>include</span> <span m='587810'>the</span> <span
  m='587880'>unit</span> <span m='588180'>circle.</span> </p><p><span
  m='589910'>So</span> <span m='590340'>for</span> <span
  m='590500'>example,</span> <span m='591270'>if</span> <span
  m='591790'>we</span> <span m='592020'>had</span> <span m='593140'>let's</span>
  <span m='593450'>say</span> <span m='593860'>a</span> <span
  m='593930'>system</span> <span m='594840'>with</span> <span
  m='595690'>a</span> <span m='595780'>system</span> <span
  m='596210'>function</span> <span m='597540'>as</span> <span
  m='598890'>I</span> <span m='599050'>indicate</span> <span
  m='599590'>here</span> <span m='604210'>with</span> <span
  m='604710'>the</span> <span m='605250'>algebraic</span> <span
  m='605840'>expression</span> <span m='606410'>for</span> <span
  m='606510'>the</span> <span m='606630'>system</span> <span
  m='607020'>function</span> <span m='607950'>being</span> <span
  m='608790'>the</span> <span m='609390'>expression</span> <span
  m='609930'>that</span> <span m='610060'>I</span> <span
  m='610140'>indicate</span> <span m='610650'>here</span> <span
  m='610980'>with</span> <span m='611070'>the</span> <span
  m='611170'>pole</span> <span m='611750'>at</span> <span m='612130'>z</span>
  <span m='612450'>equals</span> <span m='612480'>a</span> <span
  m='612510'>third</span> <span m='613560'>and</span> <span
  m='613810'>another</span> <span m='614160'>pole</span> <span
  m='614670'>at</span> <span m='614765'>z</span> <span m='614860'>equals</span>
  <span m='615240'>2</span> <span m='615400'>and</span> <span
  m='615560'>a</span> <span m='615720'>zero</span> <span m='616160'>at</span>
  <span m='616250'>the</span> <span m='616390'>origin.</span> <span
  m='618290'>If,</span> <span m='618600'>in</span> <span m='618740'>fact,</span>
  <span m='620490'>the</span> <span m='620600'>system</span> <span
  m='621420'>was</span> <span m='622280'>causal,</span> <span
  m='623120'>corresponding</span> <span m='623940'>to</span> <span
  m='624120'>an</span> <span m='624210'>impulse</span> <span
  m='624610'>response</span> <span m='625070'>that's</span> <span
  m='625260'>right-sided,</span> <span m='626600'>this</span> <span
  m='627190'>then</span> <span m='627810'>would</span> <span
  m='628050'>be</span> <span m='628870'>the</span> <span
  m='629410'>region</span> <span m='629790'>of</span> <span
  m='629890'>convergence</span> <span m='631330'>of</span> <span
  m='631470'>the</span> <span m='631560'>system</span> <span
  m='631970'>function.</span> </p><p><span m='634050'>Alternatively,</span>
  <span m='635200'>if</span> <span m='635450'>I</span> <span
  m='635520'>knew</span> <span m='635780'>that</span> <span
  m='635970'>the</span> <span m='636050'>system</span> <span
  m='636480'>was</span> <span m='636610'>stable,</span> <span
  m='637950'>then</span> <span m='638150'>I</span> <span m='638220'>know</span>
  <span m='638590'>that</span> <span m='639060'>the</span> <span
  m='639170'>region</span> <span m='639490'>of</span> <span
  m='639580'>convergence</span> <span m='640200'>must</span> <span
  m='640440'>include</span> <span m='640830'>the</span> <span
  m='640910'>unit</span> <span m='641230'>circle,</span> <span
  m='641860'>and</span> <span m='642030'>so</span> <span m='642820'>this</span>
  <span m='643080'>would</span> <span m='643270'>be</span> <span
  m='644000'>then</span> <span m='644550'>the</span> <span
  m='644650'>region</span> <span m='644980'>of</span> <span
  m='645080'>convergence.</span> <span m='646640'>And</span> <span
  m='647700'>what</span> <span m='647900'>you</span> <span
  m='648000'>might</span> <span m='648440'>now</span> <span
  m='649000'>want</span> <span m='649320'>to</span> <span m='649640'>ask</span>
  <span m='649990'>yourselves</span> <span m='651330'>is</span> <span
  m='652370'>if</span> <span m='652760'>instead</span> <span
  m='653690'>the</span> <span m='653810'>region</span> <span
  m='654140'>of</span> <span m='654220'>convergence</span> <span
  m='655100'>for</span> <span m='655200'>the</span> <span
  m='655290'>system</span> <span m='655680'>function</span> <span
  m='656390'>is</span> <span m='656690'>this,</span> <span
  m='657980'>then</span> <span m='658660'>is</span> <span m='658940'>the</span>
  <span m='659040'>system</span> <span m='659510'>causal?</span> <span
  m='660570'>That's</span> <span m='660930'>the</span> <span
  m='661290'>first</span> <span m='661730'>question.</span> <span
  m='662390'>The</span> <span m='662700'>second</span> <span
  m='663070'>question</span> <span m='663350'>is</span> <span
  m='664080'>is</span> <span m='664370'>the</span> <span
  m='664460'>system</span> <span m='664840'>stable?</span> <span
  m='666340'>Remembering</span> <span m='666920'>that</span> <span
  m='667150'>for</span> <span m='667300'>causality,</span> <span
  m='668410'>the</span> <span m='668490'>region</span> <span
  m='668750'>of</span> <span m='668840'>convergence</span> <span
  m='669440'>must</span> <span m='669680'>be</span> <span
  m='669830'>outside</span> <span m='670320'>the</span> <span
  m='670430'>outermost</span> <span m='670930'>pole,</span> <span
  m='671750'>and</span> <span m='671980'>for</span> <span
  m='672150'>stability</span> <span m='672940'>it</span> <span
  m='673050'>must</span> <span m='673320'>include</span> <span
  m='673690'>the</span> <span m='673760'>unit</span> <span
  m='674040'>circle.</span> </p><p><span m='676540'>Now</span> <span
  m='677740'>what</span> <span m='678070'>I'd</span> <span
  m='678210'>like</span> <span m='678460'>to</span> <span m='678590'>do</span>
  <span m='679110'>is</span> <span m='679810'>look</span> <span
  m='680260'>at</span> <span m='680850'>the</span> <span
  m='682210'>properties</span> <span m='683250'>of</span> <span
  m='684700'>the</span> <span m='685200'>z-transform,</span> <span
  m='686340'>and</span> <span m='686540'>in</span> <span
  m='686630'>particular</span> <span m='687470'>exploit</span> <span
  m='688000'>these</span> <span m='688220'>properties</span> <span
  m='689310'>in</span> <span m='689430'>the</span> <span
  m='689530'>context</span> <span m='690320'>of</span> <span
  m='690400'>systems</span> <span m='691450'>that</span> <span
  m='691760'>are</span> <span m='692000'>described</span> <span
  m='692700'>by</span> <span m='693470'>linear</span> <span
  m='693850'>constant</span> <span m='694260'>coefficient</span> <span
  m='694850'>difference</span> <span m='695170'>equations.</span> <span
  m='696930'>The</span> <span m='697010'>three</span> <span
  m='697230'>basic</span> <span m='697630'>properties</span> <span
  m='698710'>that</span> <span m='699100'>play</span> <span m='699245'>a</span>
  <span m='699390'>key</span> <span m='699640'>role</span> <span
  m='699960'>in</span> <span m='700030'>that</span> <span
  m='700230'>discussion</span> <span m='701320'>are</span> <span
  m='702250'>the</span> <span m='702690'>linearity</span> <span
  m='702950'>property,</span> <span m='704380'>the</span> <span
  m='704470'>shifting</span> <span m='704980'>property,</span> <span
  m='706250'>and</span> <span m='707020'>the</span> <span
  m='707140'>convolution</span> <span m='707840'>property.</span> <span
  m='709860'>These,</span> <span m='710340'>then,</span> <span
  m='710710'>are</span> <span m='711450'>the</span> <span
  m='711540'>properties</span> <span m='712430'>that</span> <span
  m='713060'>I</span> <span m='713710'>want</span> <span m='713930'>to</span>
  <span m='714050'>exploit.</span> </p><p><span m='715380'>So</span> <span
  m='715960'>let's</span> <span m='716290'>do</span> <span
  m='716430'>that</span> <span m='716800'>by</span> <span
  m='716980'>first</span> <span m='717530'>looking</span> <span
  m='718160'>at</span> <span m='718690'>a</span> <span m='719160'>first</span>
  <span m='719490'>order</span> <span m='719740'>difference</span> <span
  m='720110'>equation.</span> <span m='722480'>In</span> <span
  m='722560'>the</span> <span m='722640'>case</span> <span m='723130'>of</span>
  <span m='723600'>a</span> <span m='723940'>first</span> <span
  m='724310'>order</span> <span m='724520'>difference</span> <span
  m='724880'>equation,</span> <span m='725490'>which</span> <span
  m='726310'>I've</span> <span m='726500'>written</span> <span
  m='726960'>as</span> <span m='727150'>I</span> <span
  m='727260'>indicate</span> <span m='727810'>here--</span> <span
  m='729170'>no</span> <span m='729330'>terms</span> <span m='729740'>on</span>
  <span m='729840'>the</span> <span m='729910'>right</span> <span
  m='730160'>hand</span> <span m='730450'>side,</span> <span
  m='730890'>but</span> <span m='731030'>we</span> <span m='731170'>could</span>
  <span m='731380'>have</span> <span m='731560'>terms</span> <span
  m='731930'>of</span> <span m='732030'>course,</span> <span
  m='732370'>in</span> <span m='732510'>general--</span> <span
  m='733860'>y</span> <span m='734150'>of</span> <span m='734280'>n</span> <span
  m='734480'>minus</span> <span m='734850'>ay</span> <span m='735200'>of</span>
  <span m='735290'>n</span> <span m='735430'>minus</span> <span
  m='735800'>1</span> <span m='736020'>equals</span> <span m='736300'>x</span>
  <span m='736560'>of</span> <span m='736680'>n.</span> <span
  m='737900'>We</span> <span m='738020'>can</span> <span m='738190'>use</span>
  <span m='739070'>the</span> <span m='739910'>linearity</span> <span
  m='740610'>property,</span> <span m='742580'>so</span> <span
  m='742990'>that</span> <span m='743500'>if</span> <span m='743760'>we</span>
  <span m='744350'>take</span> <span m='744630'>the</span> <span
  m='744700'>z-transform</span> <span m='745610'>of</span> <span
  m='745680'>both</span> <span m='745930'>sides</span> <span
  m='746280'>of</span> <span m='746370'>this</span> <span
  m='746570'>expression,</span> <span m='747680'>that</span> <span
  m='748010'>will</span> <span m='748570'>then</span> <span m='748850'>be</span>
  <span m='749300'>the</span> <span m='749610'>z-transform</span> <span
  m='750220'>of</span> <span m='750310'>this</span> <span m='750550'>term</span>
  <span m='750950'>plus</span> <span m='751240'>the</span> <span
  m='751310'>z-transform</span> <span m='752110'>of</span> <span
  m='752210'>this</span> <span m='752440'>term.</span> <span
  m='754180'>So</span> <span m='754560'>using</span> <span
  m='755280'>those</span> <span m='755530'>properties</span> <span
  m='756650'>and</span> <span m='758110'>together</span> <span
  m='758600'>with</span> <span m='759170'>the</span> <span
  m='759270'>shifting</span> <span m='759790'>property,</span> <span
  m='761300'>the</span> <span m='761480'>property</span> <span
  m='761910'>that</span> <span m='762060'>tells</span> <span
  m='762400'>us</span> <span m='762620'>that</span> <span m='762790'>the</span>
  <span m='762850'>z-transform</span> <span m='764010'>of</span> <span
  m='764510'>y</span> <span m='764830'>of</span> <span m='764960'>n</span> <span
  m='765100'>minus</span> <span m='765510'>1</span> <span m='766040'>is</span>
  <span m='766770'>z</span> <span m='767000'>to</span> <span
  m='767120'>the</span> <span m='767200'>minus</span> <span m='767590'>1</span>
  <span m='767880'>times</span> <span m='768180'>the</span> <span
  m='768240'>z-transform</span> <span m='769110'>of</span> <span
  m='769190'>y</span> <span m='769490'>of</span> <span m='769620'>n,</span>
  <span m='770440'>we</span> <span m='771170'>then</span> <span
  m='771630'>convert</span> <span m='772260'>the</span> <span
  m='772350'>difference</span> <span m='772740'>equation</span> <span
  m='773310'>to</span> <span m='773440'>an</span> <span
  m='773520'>algebraic</span> <span m='774160'>expression.</span> <span
  m='775400'>And</span> <span m='775720'>we</span> <span m='775860'>can</span>
  <span m='776000'>solve</span> <span m='776370'>this</span> <span
  m='776560'>algebraic</span> <span m='777140'>expression</span> <span
  m='778010'>for</span> <span m='778860'>the</span> <span
  m='778940'>z-transform</span> <span m='779920'>of</span> <span
  m='780020'>the</span> <span m='780160'>output</span> <span
  m='781210'>in</span> <span m='781360'>terms</span> <span m='781790'>of</span>
  <span m='782480'>the</span> <span m='782600'>z-transform</span> <span
  m='783450'>of</span> <span m='783530'>the</span> <span
  m='783660'>input.</span> </p><p><span m='786100'>Now</span> <span
  m='786650'>what</span> <span m='786850'>we</span> <span m='786970'>know</span>
  <span m='787440'>from</span> <span m='788480'>the</span> <span
  m='788780'>convolution</span> <span m='789510'>property</span> <span
  m='790500'>is</span> <span m='790850'>that</span> <span m='791820'>for</span>
  <span m='791965'>a</span> <span m='792110'>system,</span> <span
  m='792860'>the</span> <span m='793050'>z-transform</span> <span
  m='793795'>of</span> <span m='794090'>the</span> <span
  m='794230'>output</span> <span m='794790'>is</span> <span
  m='795190'>the</span> <span m='795270'>system</span> <span
  m='795670'>function</span> <span m='796130'>times</span> <span
  m='796410'>the</span> <span m='796470'>z-transform</span> <span
  m='797280'>of</span> <span m='797370'>the</span> <span
  m='797490'>input.</span> <span m='798440'>So</span> <span
  m='799140'>this</span> <span m='799390'>factor</span> <span
  m='800240'>that</span> <span m='800420'>we</span> <span
  m='800560'>have,</span> <span m='800900'>then,</span> <span
  m='801620'>must</span> <span m='801940'>correspond</span> <span
  m='803000'>to</span> <span m='803890'>the</span> <span
  m='804720'>system</span> <span m='805200'>function,</span> <span
  m='806440'>or</span> <span m='806850'>equivalently</span> <span
  m='808030'>the</span> <span m='808120'>z-transform</span> <span
  m='809260'>of</span> <span m='809410'>the</span> <span
  m='809550'>impulse</span> <span m='810020'>response</span> <span
  m='810490'>of</span> <span m='810570'>the</span> <span
  m='810650'>system.</span> <span m='812360'>In</span> <span
  m='812460'>fact,</span> <span m='812840'>then,</span> <span
  m='813670'>if</span> <span m='813840'>we</span> <span m='813950'>have</span>
  <span m='814060'>this</span> <span m='814530'>z-transform,</span> <span
  m='815300'>we</span> <span m='815500'>could</span> <span
  m='815760'>figure</span> <span m='816200'>out</span> <span
  m='816710'>what</span> <span m='817590'>the</span> <span
  m='817930'>impulse</span> <span m='818370'>response</span> <span
  m='818850'>of</span> <span m='818940'>the</span> <span
  m='819020'>system</span> <span m='819480'>is</span> <span m='819950'>by</span>
  <span m='820820'>computing</span> <span m='821560'>or</span> <span
  m='821880'>determining</span> <span m='822750'>what</span> <span
  m='823000'>the</span> <span m='823150'>inverse</span> <span
  m='823870'>z-transform,</span> <span m='825240'>except</span> <span
  m='825730'>for</span> <span m='825820'>the</span> <span m='825940'>fact</span>
  <span m='827730'>that</span> <span m='827970'>expression</span> <span
  m='829200'>is</span> <span m='829400'>an</span> <span
  m='829470'>algebraic</span> <span m='830120'>expression</span> <span
  m='831940'>and</span> <span m='832590'>doesn't</span> <span
  m='833010'>yet</span> <span m='833390'>totally</span> <span
  m='833790'>specify</span> <span m='834450'>the</span> <span
  m='834760'>z-transform</span> <span m='835500'>because</span> <span
  m='835850'>we</span> <span m='835940'>don't</span> <span m='836200'>yet</span>
  <span m='836440'>know</span> <span m='836600'>what</span> <span
  m='836790'>the</span> <span m='836870'>region</span> <span
  m='837190'>of</span> <span m='837270'>convergence</span> <span
  m='837890'>is.</span> </p><p><span m='840210'>How</span> <span
  m='840330'>do</span> <span m='840400'>we</span> <span m='840520'>get</span>
  <span m='840740'>the</span> <span m='840830'>region</span> <span
  m='841110'>of</span> <span m='841190'>convergence?</span> <span
  m='842670'>Well,</span> <span m='843070'>we</span> <span
  m='843180'>have</span> <span m='843390'>the</span> <span
  m='843460'>same</span> <span m='843760'>issue</span> <span
  m='844020'>here</span> <span m='844460'>as</span> <span m='844640'>we</span>
  <span m='844760'>had</span> <span m='845000'>with</span> <span
  m='845090'>the</span> <span m='845320'>Laplace</span> <span
  m='845660'>transform--</span> <span m='846980'>namely,</span> <span
  m='847400'>the</span> <span m='847510'>point</span> <span
  m='848400'>that</span> <span m='848950'>the</span> <span
  m='849040'>difference</span> <span m='849480'>equation</span> <span
  m='851470'>tells</span> <span m='851920'>us,</span> <span m='853440'>in</span>
  <span m='853640'>essence,</span> <span m='854340'>what</span> <span
  m='854630'>the</span> <span m='854780'>algebraic</span> <span
  m='855440'>expression</span> <span m='856080'>is</span> <span
  m='856720'>for</span> <span m='856850'>the</span> <span
  m='856940'>system</span> <span m='857340'>function,</span> <span
  m='858420'>but</span> <span m='858700'>doesn't</span> <span
  m='859330'>specify</span> <span m='860140'>the</span> <span
  m='860260'>region</span> <span m='860570'>of</span> <span
  m='860660'>convergence.</span> <span m='862080'>That</span> <span
  m='862590'>is</span> <span m='862800'>specified</span> <span
  m='863790'>by</span> <span m='864400'>either</span> <span
  m='864770'>explicitly,</span> <span m='865730'>because</span> <span
  m='866440'>one</span> <span m='866640'>way</span> <span m='866780'>or</span>
  <span m='866910'>another</span> <span m='867240'>we</span> <span
  m='867400'>know</span> <span m='867930'>what</span> <span
  m='868100'>the</span> <span m='868180'>impulse</span> <span
  m='868610'>response</span> <span m='868842'>is,</span> <span
  m='870140'>or</span> <span m='870590'>implicitly,</span> <span
  m='871760'>because</span> <span m='872560'>we</span> <span
  m='872690'>know</span> <span m='872850'>certain</span> <span
  m='873200'>properties</span> <span m='873790'>of</span> <span
  m='873860'>the</span> <span m='873940'>system,</span> <span
  m='874820'>such</span> <span m='875270'>as</span> <span
  m='875830'>causality</span> <span m='877150'>and</span> <span
  m='877400'>or</span> <span m='877540'>stability.</span> </p><p><span
  m='880130'>If</span> <span m='880660'>I,</span> <span m='882610'>let's</span>
  <span m='882960'>say,</span> <span m='883790'>imposed</span> <span
  m='884350'>on</span> <span m='884500'>this</span> <span
  m='884740'>system,</span> <span m='885420'>in</span> <span
  m='885540'>addition</span> <span m='885930'>to</span> <span
  m='886030'>the</span> <span m='886120'>difference</span> <span
  m='886510'>equation,</span> <span m='887710'>the</span> <span
  m='888010'>condition</span> <span m='888710'>of</span> <span
  m='889610'>causality,</span> <span m='894770'>then</span> <span
  m='895580'>what</span> <span m='895740'>that</span> <span
  m='895960'>requires</span> <span m='896800'>is</span> <span
  m='897040'>that</span> <span m='897540'>the</span> <span
  m='897690'>impulse</span> <span m='898450'>response</span> <span
  m='899400'>be</span> <span m='899530'>right-sided</span> <span
  m='900860'>or</span> <span m='901530'>the</span> <span
  m='901630'>region</span> <span m='901990'>of</span> <span
  m='902060'>convergence</span> <span m='902860'>be</span> <span
  m='903060'>outside</span> <span m='903580'>the</span> <span
  m='903700'>outermost</span> <span m='904260'>pole.</span> <span
  m='905330'>So,</span> <span m='905530'>for</span> <span m='905650'>this</span>
  <span m='905860'>example</span> <span m='906950'>that</span> <span
  m='907160'>would</span> <span m='907300'>require,</span> <span
  m='907860'>then,</span> <span m='908580'>that</span> <span
  m='909200'>the</span> <span m='909350'>region</span> <span
  m='909690'>of</span> <span m='909780'>convergence</span> <span
  m='910440'>correspond</span> <span m='911250'>to</span> <span
  m='912090'>the</span> <span m='912200'>magnitude</span> <span
  m='912840'>of</span> <span m='912940'>z</span> <span m='913790'>greater</span>
  <span m='914200'>than</span> <span m='914900'>the</span> <span
  m='915010'>magnitude</span> <span m='915590'>of</span> <span
  m='915670'>a.</span> </p><p><span m='918190'>What</span> <span
  m='918460'>you</span> <span m='918540'>might</span> <span
  m='918990'>think</span> <span m='919210'>about</span> <span
  m='919670'>is</span> <span m='920450'>whether</span> <span m='920830'>I</span>
  <span m='920900'>would</span> <span m='921080'>get</span> <span
  m='921250'>the</span> <span m='921330'>same</span> <span
  m='921670'>condition</span> <span m='922900'>if</span> <span
  m='923510'>I</span> <span m='924180'>required</span> <span
  m='924800'>instead</span> <span m='925780'>that</span> <span
  m='925960'>the</span> <span m='926030'>system</span> <span
  m='927010'>be</span> <span m='927150'>stable.</span> <span
  m='929310'>Furthermore,</span> <span m='929820'>you</span> <span
  m='929950'>could</span> <span m='930110'>think</span> <span
  m='930290'>about</span> <span m='930540'>the</span> <span
  m='930620'>question</span> <span m='931000'>of</span> <span
  m='931080'>whether</span> <span m='931500'>I</span> <span
  m='931680'>could</span> <span m='932430'>specify</span> <span
  m='933480'>or</span> <span m='933780'>impose</span> <span m='934150'>on</span>
  <span m='934270'>this</span> <span m='934370'>system</span> <span
  m='934850'>that</span> <span m='934980'>it</span> <span m='935070'>be</span>
  <span m='935200'>both</span> <span m='935480'>stable</span> <span
  m='935910'>and</span> <span m='936010'>causal.</span> <span
  m='937090'>The</span> <span m='937210'>real</span> <span
  m='937490'>issue--</span> <span m='937780'>and</span> <span
  m='937850'>let</span> <span m='937960'>me</span> <span m='938100'>just</span>
  <span m='938390'>kind</span> <span m='938590'>of</span> <span
  m='938700'>point</span> <span m='939070'>to</span> <span
  m='939230'>it--</span> <span m='939760'>is</span> <span m='940100'>that</span>
  <span m='940570'>the</span> <span m='940780'>answer</span> <span
  m='941220'>to</span> <span m='941340'>those</span> <span
  m='941600'>questions</span> <span m='942440'>relate</span> <span
  m='943010'>to</span> <span m='943770'>whether</span> <span
  m='943970'>the</span> <span m='944090'>magnitude</span> <span
  m='944670'>of</span> <span m='944770'>a</span> <span m='944910'>is</span>
  <span m='945070'>less</span> <span m='945340'>than</span> <span
  m='945480'>1</span> <span m='945950'>or</span> <span m='946030'>the</span>
  <span m='946120'>magnitude</span> <span m='946570'>of</span> <span
  m='946650'>a</span> <span m='946730'>is</span> <span m='946890'>greater</span>
  <span m='947180'>than</span> <span m='947370'>1.</span> <span
  m='948160'>If</span> <span m='948290'>the</span> <span
  m='948380'>magnitude</span> <span m='948860'>of</span> <span
  m='948940'>a</span> <span m='949030'>is</span> <span m='949170'>less</span>
  <span m='949460'>than</span> <span m='949590'>1</span> <span
  m='950040'>and</span> <span m='950150'>I</span> <span
  m='950200'>specify</span> <span m='950810'>causality,</span> <span
  m='952030'>that</span> <span m='952240'>will</span> <span
  m='952450'>also</span> <span m='954830'>mean</span> <span
  m='955350'>that</span> <span m='955520'>the</span> <span
  m='955600'>system</span> <span m='956010'>is</span> <span
  m='956090'>stable.</span> <span m='957320'>In</span> <span
  m='957470'>any</span> <span m='957650'>case,</span> <span
  m='958500'>given</span> <span m='958780'>this</span> <span
  m='958980'>region</span> <span m='959310'>of</span> <span
  m='959410'>convergence,</span> <span m='960710'>then</span> <span
  m='961510'>the</span> <span m='962170'>impulse</span> <span
  m='962690'>response</span> <span m='963480'>is</span> <span
  m='964520'>the</span> <span m='964800'>inverse</span> <span
  m='965220'>transform</span> <span m='965565'>of</span> <span
  m='965910'>that</span> <span m='966340'>z-transform,</span> <span
  m='967040'>which</span> <span m='967230'>is</span> <span m='967390'>a</span>
  <span m='967560'>to</span> <span m='967650'>the</span> <span
  m='967810'>n</span> <span m='968030'>times</span> <span m='968320'>u</span>
  <span m='968540'>of</span> <span m='968660'>n.</span> </p><p><span
  m='971490'>Now</span> <span m='971860'>let's</span> <span
  m='972210'>look</span> <span m='972480'>at</span> <span m='973602'>a</span>
  <span m='973980'>second</span> <span m='974370'>order</span> <span
  m='974650'>equation,</span> <span m='975170'>and</span> <span
  m='975290'>there's</span> <span m='975490'>a</span> <span
  m='975680'>very</span> <span m='975850'>similar</span> <span
  m='976280'>strategy.</span> <span m='977470'>For</span> <span
  m='977560'>the</span> <span m='977670'>second</span> <span
  m='978030'>order</span> <span m='978280'>equation,</span> <span
  m='979110'>the</span> <span m='979250'>one</span> <span m='979440'>that</span>
  <span m='979530'>I've</span> <span m='979640'>picked</span> <span
  m='980130'>is</span> <span m='980780'>of</span> <span m='981430'>this</span>
  <span m='981660'>particular</span> <span m='982210'>form,</span> <span
  m='982770'>and</span> <span m='982880'>I've</span> <span
  m='983050'>written</span> <span m='983860'>the</span> <span
  m='983980'>coefficients</span> <span m='984700'>parametrically</span> <span
  m='985480'>as</span> <span m='985600'>I</span> <span
  m='985700'>indicate</span> <span m='986190'>here</span> <span
  m='986600'>for</span> <span m='986800'>a</span> <span
  m='986850'>specific</span> <span m='987420'>reason,</span> <span
  m='988270'>which</span> <span m='988470'>we'll</span> <span
  m='988580'>see</span> <span m='988780'>shortly.</span> <span
  m='989880'>Again,</span> <span m='990470'>I</span> <span m='990670'>can</span>
  <span m='990860'>apply</span> <span m='991190'>the</span> <span
  m='991520'>z-transform</span> <span m='992500'>to</span> <span
  m='992650'>this</span> <span m='992870'>expression,</span> <span
  m='994250'>and</span> <span m='995010'>I've</span> <span
  m='995270'>skipped</span> <span m='996370'>an</span> <span
  m='996520'>algebraic</span> <span m='997110'>step</span> <span
  m='997420'>or</span> <span m='997520'>two</span> <span m='997750'>here.</span>
  <span m='998580'>When</span> <span m='998750'>I</span> <span
  m='998840'>do</span> <span m='999120'>this,</span> <span
  m='999530'>then,</span> <span m='1000370'>again</span> <span
  m='1000930'>I</span> <span m='1001020'>use</span> <span m='1001310'>the</span>
  <span m='1001580'>linearity</span> <span m='1002160'>property</span> <span
  m='1002820'>and</span> <span m='1002970'>the</span> <span
  m='1003000'>shifting</span> <span m='1003480'>property,</span> <span
  m='1004580'>and</span> <span m='1005260'>I</span> <span m='1005360'>end</span>
  <span m='1005570'>up</span> <span m='1005740'>with</span> <span
  m='1005890'>this</span> <span m='1006090'>algebraic</span> <span
  m='1006790'>expression.</span> <span m='1007890'>If</span> <span
  m='1008080'>I</span> <span m='1008170'>now</span> <span
  m='1008390'>solve</span> <span m='1008890'>that</span> <span
  m='1010540'>to</span> <span m='1010680'>express</span> <span
  m='1011130'>y</span> <span m='1011490'>of</span> <span m='1011590'>z</span>
  <span m='1012180'>in</span> <span m='1012340'>terms</span> <span
  m='1012700'>of</span> <span m='1012800'>x</span> <span m='1013080'>of</span>
  <span m='1013200'>z</span> <span m='1014090'>and</span> <span
  m='1014240'>a</span> <span m='1014280'>function</span> <span
  m='1014730'>of</span> <span m='1014830'>z,</span> <span
  m='1015930'>then</span> <span m='1016790'>this</span> <span
  m='1017160'>is</span> <span m='1017770'>what</span> <span m='1018140'>I</span>
  <span m='1018320'>get</span> <span m='1018790'>for</span> <span
  m='1018910'>the</span> <span m='1019010'>system</span> <span
  m='1019430'>function.</span> <span m='1022430'>So</span> <span
  m='1023170'>this</span> <span m='1023410'>is</span> <span
  m='1023560'>now</span> <span m='1024220'>a</span> <span
  m='1024310'>second</span> <span m='1024660'>order</span> <span
  m='1024940'>system</span> <span m='1025310'>function,</span> <span
  m='1026460'>and</span> <span m='1026780'>we'll</span> <span
  m='1026970'>have</span> <span m='1027359'>two</span> <span
  m='1027540'>zeroes</span> <span m='1028010'>at</span> <span
  m='1028099'>the</span> <span m='1028230'>origin</span> <span
  m='1028990'>and</span> <span m='1029579'>it</span> <span
  m='1029670'>will</span> <span m='1029890'>have</span> <span
  m='1030119'>two</span> <span m='1030310'>poles.</span> </p><p><span
  m='1032960'>Again,</span> <span m='1034540'>there's</span> <span
  m='1034869'>the</span> <span m='1034910'>question</span> <span
  m='1035490'>of</span> <span m='1036270'>what</span> <span
  m='1036520'>we</span> <span m='1036640'>assume</span> <span
  m='1036940'>about</span> <span m='1037260'>the</span> <span
  m='1037339'>region</span> <span m='1037630'>of</span> <span
  m='1037710'>convergence--</span> <span m='1038349'>I</span> <span
  m='1038410'>haven't</span> <span m='1038700'>specified</span> <span
  m='1039349'>that</span> <span m='1039579'>yet.</span> <span
  m='1040240'>But</span> <span m='1041099'>if</span> <span
  m='1041780'>we,</span> <span m='1042150'>let's</span> <span
  m='1042400'>say,</span> <span m='1042550'>assume</span> <span
  m='1043020'>that</span> <span m='1043560'>the</span> <span
  m='1044970'>system</span> <span m='1045369'>is</span> <span
  m='1045500'>causal,</span> <span m='1045990'>which</span> <span
  m='1046210'>I</span> <span m='1046310'>will</span> <span
  m='1046530'>tend</span> <span m='1046800'>to</span> <span
  m='1046910'>do,</span> <span m='1047730'>then</span> <span
  m='1047920'>that</span> <span m='1048140'>means</span> <span
  m='1048460'>that</span> <span m='1048580'>the</span> <span
  m='1048670'>region</span> <span m='1048950'>of</span> <span
  m='1049050'>convergence</span> <span m='1049670'>is</span> <span
  m='1049800'>outside</span> <span m='1050260'>the</span> <span
  m='1050400'>outermost</span> <span m='1050910'>pole.</span> </p><p><span
  m='1052830'>Now,</span> <span m='1053210'>where</span> <span
  m='1053460'>are</span> <span m='1053515'>the</span> <span
  m='1053570'>poles?</span> <span m='1054080'>Well,</span> <span
  m='1054610'>let</span> <span m='1054830'>me</span> <span
  m='1055030'>just</span> <span m='1055350'>kind</span> <span
  m='1055540'>of</span> <span m='1055610'>indicate</span> <span
  m='1056680'>that</span> <span m='1058110'>if--</span> <span
  m='1058920'>and</span> <span m='1059060'>you</span> <span
  m='1059170'>can</span> <span m='1059310'>verify</span> <span
  m='1059790'>this</span> <span m='1060010'>algebraically</span> <span
  m='1061610'>at</span> <span m='1061910'>your</span> <span
  m='1062040'>leisure--</span> <span m='1063250'>that</span> <span
  m='1064370'>if</span> <span m='1064890'>the</span> <span
  m='1065300'>cosine</span> <span m='1066190'>theta</span> <span
  m='1066810'>term</span> <span m='1068300'>is</span> <span
  m='1069040'>less</span> <span m='1069420'>than</span> <span
  m='1069560'>1,</span> <span m='1071100'>then</span> <span
  m='1072010'>the</span> <span m='1072320'>roots</span> <span
  m='1072680'>of</span> <span m='1072830'>this</span> <span
  m='1073400'>polynomial</span> <span m='1074420'>will</span> <span
  m='1074590'>be</span> <span m='1074740'>complex.</span> <span
  m='1076110'>And</span> <span m='1076290'>in</span> <span
  m='1076390'>fact,</span> <span m='1077100'>the</span> <span
  m='1077200'>poles</span> <span m='1077940'>are</span> <span
  m='1078440'>at</span> <span m='1079310'>r</span> <span m='1080160'>e</span>
  <span m='1080370'>to</span> <span m='1080500'>the</span> <span
  m='1080570'>plus</span> <span m='1080880'>or</span> <span
  m='1080930'>minus</span> <span m='1081310'>j</span> <span
  m='1081540'>theta.</span> <span m='1082740'>So</span> <span
  m='1083160'>for</span> <span m='1083320'>cosine</span> <span
  m='1083770'>theta</span> <span m='1084080'>less</span> <span
  m='1084330'>than</span> <span m='1084470'>1,</span> <span
  m='1085310'>then</span> <span m='1086200'>the</span> <span
  m='1086300'>poles</span> <span m='1086930'>are</span> <span
  m='1087590'>complex,</span> <span m='1088970'>and</span> <span
  m='1089660'>the</span> <span m='1089780'>complex</span> <span
  m='1090280'>poles</span> <span m='1091240'>at</span> <span
  m='1091410'>an</span> <span m='1091520'>angle</span> <span
  m='1091920'>theta</span> <span m='1092590'>and</span> <span
  m='1093490'>with</span> <span m='1093850'>a</span> <span
  m='1093960'>distance</span> <span m='1094370'>from</span> <span
  m='1094540'>the</span> <span m='1094660'>origin</span> <span
  m='1095780'>equal</span> <span m='1096150'>to</span> <span
  m='1096250'>the</span> <span m='1096340'>parameter</span> <span
  m='1096910'>r.</span> </p><p><span m='1098070'>In</span> <span
  m='1098130'>fact,</span> <span m='1098440'>let's</span> <span
  m='1098750'>just</span> <span m='1099330'>look</span> <span
  m='1099570'>at</span> <span m='1099670'>that.</span> <span
  m='1101550'>What</span> <span m='1101800'>I</span> <span
  m='1102280'>show</span> <span m='1102620'>here</span> <span
  m='1103030'>is</span> <span m='1103450'>the</span> <span
  m='1104340'>pole</span> <span m='1104610'>zero</span> <span
  m='1105660'>pattern.</span> <span m='1107640'>Assuming</span> <span
  m='1108420'>that</span> <span m='1109280'>r</span> <span m='1109780'>is</span>
  <span m='1110200'>less</span> <span m='1110490'>than</span> <span
  m='1110650'>1,</span> <span m='1111740'>and</span> <span
  m='1112920'>that</span> <span m='1113160'>cosine</span> <span
  m='1113660'>theta</span> <span m='1114220'>is</span> <span
  m='1114490'>less</span> <span m='1114770'>than</span> <span
  m='1114910'>1,</span> <span m='1115720'>and</span> <span m='1115930'>we</span>
  <span m='1116060'>have</span> <span m='1116280'>a</span> <span
  m='1116340'>complex</span> <span m='1116900'>pole</span> <span
  m='1117210'>pair</span> <span m='1117860'>shown</span> <span
  m='1118240'>here--</span> <span m='1120300'>now</span> <span
  m='1120700'>if</span> <span m='1121080'>we</span> <span
  m='1121540'>assume</span> <span m='1121830'>that</span> <span
  m='1121980'>the</span> <span m='1122060'>system</span> <span
  m='1122430'>was</span> <span m='1122590'>causal,</span> <span
  m='1123770'>that</span> <span m='1123960'>means</span> <span
  m='1124210'>that</span> <span m='1124350'>the</span> <span
  m='1124440'>region</span> <span m='1124730'>of</span> <span
  m='1124820'>convergence</span> <span m='1125430'>is</span> <span
  m='1125570'>outside</span> <span m='1126060'>these</span> <span
  m='1126310'>poles.</span> <span m='1128240'>That</span> <span
  m='1128550'>would</span> <span m='1128760'>then</span> <span
  m='1129050'>include</span> <span m='1129500'>the</span> <span
  m='1129590'>unit</span> <span m='1129910'>circle,</span> <span
  m='1130630'>which</span> <span m='1130830'>means</span> <span
  m='1131160'>that</span> <span m='1131300'>the</span> <span
  m='1131380'>system</span> <span m='1131990'>is</span> <span
  m='1132430'>also</span> <span m='1132800'>stable.</span> <span
  m='1134290'>In</span> <span m='1134360'>fact,</span> <span
  m='1134700'>as</span> <span m='1134810'>long</span> <span
  m='1135070'>as</span> <span m='1135190'>the</span> <span
  m='1135280'>reach</span> <span m='1135530'>of</span> <span
  m='1135630'>convergence</span> <span m='1136830'>includes</span> <span
  m='1137270'>the</span> <span m='1137370'>unit</span> <span
  m='1137670'>circle,</span> <span m='1138660'>we</span> <span
  m='1138840'>can</span> <span m='1139060'>also</span> <span
  m='1139760'>talk</span> <span m='1140230'>about</span> <span
  m='1141230'>the</span> <span m='1141800'>frequency</span> <span
  m='1142320'>response</span> <span m='1142850'>of</span> <span
  m='1142930'>the</span> <span m='1143010'>system--</span> <span
  m='1143680'>namely,</span> <span m='1144010'>we</span> <span
  m='1144140'>can</span> <span m='1144260'>evaluate</span> <span
  m='1144790'>the</span> <span m='1144870'>system</span> <span
  m='1145240'>function</span> <span m='1145970'>on</span> <span
  m='1146180'>the</span> <span m='1146270'>unit</span> <span
  m='1146570'>circle.</span> </p><p><span m='1148500'>We,</span> <span
  m='1148650'>in</span> <span m='1148740'>fact,</span> <span
  m='1149080'>evaluated</span> <span m='1149990'>the</span> <span
  m='1150240'>Fourier</span> <span m='1151700'>transform</span> <span
  m='1152630'>associated</span> <span m='1153270'>with</span> <span
  m='1153440'>this</span> <span m='1154020'>pole</span> <span
  m='1154230'>zero</span> <span m='1154530'>pattern</span> <span
  m='1154930'>last</span> <span m='1155280'>time.</span> <span
  m='1156660'>Recall</span> <span m='1157330'>that</span> <span
  m='1158030'>the</span> <span m='1158930'>frequency</span> <span
  m='1159420'>response,</span> <span m='1160010'>then,</span> <span
  m='1160400'>is</span> <span m='1160640'>one</span> <span
  m='1161050'>that</span> <span m='1161210'>has</span> <span
  m='1161760'>a</span> <span m='1162070'>resonant</span> <span
  m='1162660'>character</span> <span m='1163930'>with</span> <span
  m='1164440'>the</span> <span m='1164620'>resonant</span> <span
  m='1165080'>peak</span> <span m='1165730'>being</span> <span
  m='1166620'>roughly</span> <span m='1167260'>in</span> <span
  m='1167430'>the</span> <span m='1167820'>vicinity</span> <span
  m='1168870'>of</span> <span m='1169360'>the</span> <span
  m='1170760'>angle</span> <span m='1171210'>of</span> <span
  m='1171350'>the</span> <span m='1171440'>pole</span> <span
  m='1171720'>location.</span> <span m='1173010'>As</span> <span
  m='1173160'>the</span> <span m='1173250'>parameter</span> <span
  m='1173800'>r</span> <span m='1174510'>varies--</span> <span
  m='1174650'>let's</span> <span m='1174840'>say,</span> <span
  m='1174960'>as</span> <span m='1175130'>r</span> <span m='1175300'>gets</span>
  <span m='1175490'>smaller--</span> <span m='1176490'>this</span> <span
  m='1176680'>peak</span> <span m='1176930'>tends</span> <span
  m='1177260'>to</span> <span m='1177680'>broaden.</span> <span
  m='1178710'>As</span> <span m='1178950'>r</span> <span m='1179590'>gets</span>
  <span m='1179800'>closer</span> <span m='1180220'>to</span> <span
  m='1180370'>1,</span> <span m='1181060'>the</span> <span
  m='1181180'>resonance</span> <span m='1181980'>tends</span> <span
  m='1182260'>to</span> <span m='1182360'>get</span> <span
  m='1182510'>sharper.</span> </p><p><span m='1189020'>This</span> <span
  m='1189470'>is</span> <span m='1190260'>now</span> <span m='1191510'>a</span>
  <span m='1192370'>look</span> <span m='1192740'>at</span> <span
  m='1193080'>the</span> <span m='1193390'>z-transform,</span> <span
  m='1194270'>and</span> <span m='1194420'>we</span> <span
  m='1194540'>see</span> <span m='1194830'>very</span> <span
  m='1195100'>strong</span> <span m='1195560'>parallels</span> <span
  m='1196470'>to</span> <span m='1196620'>the</span> <span
  m='1196730'>Laplace</span> <span m='1197230'>transform.</span> <span
  m='1199000'>In</span> <span m='1199130'>fact,</span> <span
  m='1200220'>throughout</span> <span m='1200740'>the</span> <span
  m='1200850'>course,</span> <span m='1202380'>I've</span> <span
  m='1202540'>tried</span> <span m='1202840'>to</span> <span
  m='1202920'>emphasize--</span> <span m='1203700'>and</span> <span
  m='1203775'>it</span> <span m='1203850'>just</span> <span
  m='1204110'>naturally</span> <span m='1204580'>happens--</span> <span
  m='1205590'>that</span> <span m='1206060'>there</span> <span
  m='1206490'>are</span> <span m='1206690'>very</span> <span
  m='1207010'>strong</span> <span m='1207800'>relationships</span> <span
  m='1208950'>and</span> <span m='1209140'>parallels</span> <span
  m='1210370'>between</span> <span m='1211520'>continuous</span> <span
  m='1212130'>time</span> <span m='1212450'>and</span> <span
  m='1212520'>discrete</span> <span m='1212950'>time.</span> <span
  m='1214890'>In</span> <span m='1214980'>fact,</span> <span
  m='1216040'>at</span> <span m='1216170'>one</span> <span
  m='1216380'>point</span> <span m='1216830'>we</span> <span
  m='1217600'>specifically</span> <span m='1219020'>mapped</span> <span
  m='1219520'>from</span> <span m='1219940'>continuous</span> <span
  m='1220500'>time</span> <span m='1220770'>to</span> <span
  m='1220870'>discrete</span> <span m='1221310'>time</span> <span
  m='1221610'>when</span> <span m='1221730'>we</span> <span
  m='1221860'>talked</span> <span m='1222250'>about</span> <span
  m='1222960'>discrete</span> <span m='1223410'>time</span> <span
  m='1223630'>processing</span> <span m='1224410'>of</span> <span
  m='1224670'>continuous</span> <span m='1225250'>time</span> <span
  m='1225510'>signals.</span> <span m='1227460'>What</span> <span
  m='1227640'>I'd</span> <span m='1227780'>like</span> <span
  m='1228000'>to</span> <span m='1228110'>do</span> <span m='1228340'>now</span>
  <span m='1229000'>is</span> <span m='1229720'>turn</span> <span
  m='1229960'>our</span> <span m='1230130'>attention</span> <span
  m='1230900'>to</span> <span m='1232030'>another</span> <span
  m='1232760'>very</span> <span m='1233120'>important</span> <span
  m='1233920'>reason</span> <span m='1235140'>for</span> <span
  m='1235340'>mapping</span> <span m='1236100'>from</span> <span
  m='1236990'>continuous</span> <span m='1237620'>time</span> <span
  m='1238000'>to</span> <span m='1238130'>discrete</span> <span
  m='1238640'>time,</span> <span m='1239520'>and</span> <span
  m='1239680'>in</span> <span m='1239760'>the</span> <span
  m='1239830'>process</span> <span m='1240340'>of</span> <span
  m='1240440'>doing</span> <span m='1240770'>this,</span> <span
  m='1241320'>what</span> <span m='1241600'>we'll</span> <span
  m='1241810'>need</span> <span m='1242020'>to</span> <span
  m='1242140'>do</span> <span m='1242490'>is</span> <span
  m='1242650'>exploit</span> <span m='1243380'>fairly</span> <span
  m='1243750'>heavily</span> <span m='1245030'>the</span> <span
  m='1246060'>insight,</span> <span m='1246670'>intuition,</span> <span
  m='1247490'>and</span> <span m='1248040'>procedures</span> <span
  m='1248880'>that</span> <span m='1249380'>we've</span> <span
  m='1249600'>developed</span> <span m='1250230'>for</span> <span
  m='1250850'>the</span> <span m='1251210'>Laplace</span> <span
  m='1251570'>transform</span> <span m='1252470'>and</span> <span
  m='1252600'>the</span> <span m='1252870'>z-transform.</span> </p><p><span
  m='1255150'>Specifically,</span> <span m='1256100'>what</span> <span
  m='1256550'>I</span> <span m='1256620'>would</span> <span
  m='1256760'>like</span> <span m='1257020'>to</span> <span
  m='1257270'>begin</span> <span m='1257740'>is</span> <span
  m='1257890'>a</span> <span m='1257950'>discussion</span> <span
  m='1259540'>relating</span> <span m='1260190'>to</span> <span
  m='1260900'>mapping</span> <span m='1262230'>continuous</span> <span
  m='1262980'>time</span> <span m='1263930'>filters</span> <span
  m='1265090'>to</span> <span m='1265810'>discrete</span> <span
  m='1266270'>time</span> <span m='1266530'>filters,</span> <span
  m='1268360'>or</span> <span m='1269020'>continuous</span> <span
  m='1269590'>time</span> <span m='1269820'>system</span> <span
  m='1270260'>functions</span> <span m='1271260'>to</span> <span
  m='1271840'>discrete</span> <span m='1272260'>time</span> <span
  m='1272470'>system</span> <span m='1272860'>functions.</span> <span
  m='1274410'>Now,</span> <span m='1275000'>why</span> <span
  m='1275220'>would</span> <span m='1275390'>we</span> <span
  m='1275500'>want</span> <span m='1275680'>to</span> <span
  m='1275750'>do</span> <span m='1275950'>that?</span> <span
  m='1277170'>Well,</span> <span m='1277710'>there</span> <span
  m='1278240'>are</span> <span m='1278760'>at</span> <span
  m='1278890'>least</span> <span m='1279020'>several</span> <span
  m='1279500'>reasons</span> <span m='1279940'>for</span> <span
  m='1280040'>wanting</span> <span m='1280430'>to</span> <span
  m='1281130'>map</span> <span m='1281420'>continuous</span> <span
  m='1282000'>time</span> <span m='1282260'>filters</span> <span
  m='1282870'>to</span> <span m='1283190'>discrete</span> <span
  m='1283670'>time</span> <span m='1283910'>filters.</span> <span
  m='1285140'>One,</span> <span m='1285370'>of</span> <span
  m='1285480'>course,</span> <span m='1285970'>is</span> <span
  m='1286390'>the</span> <span m='1286490'>fact</span> <span
  m='1287080'>that</span> <span m='1287860'>in</span> <span
  m='1287980'>some</span> <span m='1288230'>situations</span> <span
  m='1289630'>what</span> <span m='1289940'>we're</span> <span
  m='1290140'>interested</span> <span m='1290600'>in</span> <span
  m='1291240'>doing</span> <span m='1291850'>is</span> <span
  m='1292140'>processing</span> <span m='1293280'>continuous</span> <span
  m='1293890'>time</span> <span m='1294140'>signals</span> <span
  m='1295260'>with</span> <span m='1296010'>discrete</span> <span
  m='1296470'>time</span> <span m='1297000'>systems--</span> <span
  m='1298220'>or,</span> <span m='1299030'>said</span> <span
  m='1299330'>another</span> <span m='1299640'>way,</span> <span
  m='1300440'>simulate</span> <span m='1301750'>continuous</span> <span
  m='1302370'>time</span> <span m='1303520'>systems</span> <span
  m='1304550'>with</span> <span m='1305050'>discrete</span> <span
  m='1305450'>time</span> <span m='1305670'>systems.</span> <span
  m='1306690'>So</span> <span m='1306930'>it</span> <span
  m='1306970'>would</span> <span m='1307150'>be</span> <span
  m='1307290'>natural</span> <span m='1307790'>in</span> <span
  m='1307860'>a</span> <span m='1307910'>setting</span> <span
  m='1308260'>like</span> <span m='1308500'>that</span> <span
  m='1309070'>to</span> <span m='1309200'>think</span> <span
  m='1309450'>of</span> <span m='1309530'>mapping</span> <span
  m='1310050'>the</span> <span m='1311490'>desired</span> <span
  m='1312120'>continuous</span> <span m='1312650'>time</span> <span
  m='1312880'>filter</span> <span m='1313320'>to</span> <span
  m='1313460'>a</span> <span m='1313500'>discrete</span> <span
  m='1313910'>time</span> <span m='1314220'>filter.</span> </p><p><span
  m='1315840'>So</span> <span m='1316050'>that's</span> <span
  m='1316350'>one</span> <span m='1316650'>very</span> <span
  m='1316890'>important</span> <span m='1317330'>context.</span> <span
  m='1318480'>There's</span> <span m='1318670'>another</span> <span
  m='1319170'>very</span> <span m='1319470'>important</span> <span
  m='1319890'>context</span> <span m='1320650'>in</span> <span
  m='1321240'>which</span> <span m='1321710'>this</span> <span
  m='1321930'>is</span> <span m='1322100'>done,</span> <span
  m='1322880'>and</span> <span m='1323070'>that</span> <span
  m='1323370'>is</span> <span m='1323770'>in</span> <span m='1323880'>the</span>
  <span m='1326900'>context</span> <span m='1327640'>or</span> <span
  m='1328520'>for</span> <span m='1328640'>the</span> <span
  m='1328740'>purpose</span> <span m='1329870'>of</span> <span
  m='1330370'>exploiting</span> <span m='1331650'>established</span> <span
  m='1332340'>design</span> <span m='1332730'>procedures</span> <span
  m='1333400'>for</span> <span m='1333830'>continuous</span> <span
  m='1334390'>time</span> <span m='1334630'>filters.</span> <span
  m='1336180'>The</span> <span m='1336280'>point</span> <span
  m='1336540'>is</span> <span m='1336660'>the</span> <span
  m='1336740'>following.</span> <span m='1338440'>We</span> <span
  m='1338570'>may</span> <span m='1338760'>or</span> <span
  m='1338860'>may</span> <span m='1339030'>not</span> <span
  m='1339780'>be</span> <span m='1339890'>processing</span> <span
  m='1340930'>a</span> <span m='1341290'>sample</span> <span
  m='1341750'>continuous</span> <span m='1342240'>time</span> <span
  m='1342460'>signal</span> <span m='1342810'>with</span> <span
  m='1342990'>our</span> <span m='1343350'>discrete</span> <span
  m='1343740'>time</span> <span m='1343970'>filter--</span> <span
  m='1344255'>it</span> <span m='1344540'>may</span> <span
  m='1344700'>just</span> <span m='1345100'>be</span> <span
  m='1345260'>discrete</span> <span m='1345690'>time</span> <span
  m='1345910'>signals</span> <span m='1346380'>that</span> <span
  m='1346490'>we're</span> <span m='1346630'>working</span> <span
  m='1347060'>with.</span> <span m='1348630'>But</span> <span
  m='1349770'>in</span> <span m='1349920'>that</span> <span
  m='1350320'>situation,</span> <span m='1351690'>still,</span> <span
  m='1352740'>we</span> <span m='1352880'>need</span> <span
  m='1353130'>to</span> <span m='1353230'>design</span> <span
  m='1354150'>the</span> <span m='1354460'>appropriate</span> <span
  m='1355000'>discrete</span> <span m='1355390'>time</span> <span
  m='1355610'>filter.</span> </p><p><span m='1358280'>Historically,</span> <span
  m='1359490'>there</span> <span m='1359990'>is</span> <span
  m='1360610'>a</span> <span m='1361170'>very</span> <span
  m='1362420'>rich</span> <span m='1363610'>history</span> <span
  m='1365290'>associated</span> <span m='1366110'>with</span> <span
  m='1366300'>design</span> <span m='1366880'>of</span> <span
  m='1367020'>continuous</span> <span m='1367640'>time</span> <span
  m='1367910'>filters.</span> <span m='1370290'>In</span> <span
  m='1370510'>many</span> <span m='1370780'>cases,</span> <span
  m='1371580'>it's</span> <span m='1371780'>possible</span> <span
  m='1372970'>and</span> <span m='1373420'>very</span> <span
  m='1373680'>worthwhile</span> <span m='1374720'>and</span> <span
  m='1374860'>efficient</span> <span m='1376020'>to</span> <span
  m='1376760'>take</span> <span m='1377070'>those</span> <span
  m='1377350'>designs</span> <span m='1378730'>and</span> <span
  m='1378920'>map</span> <span m='1379310'>them</span> <span
  m='1380120'>to</span> <span m='1380790'>discrete</span> <span
  m='1381260'>time</span> <span m='1381510'>designs</span> <span
  m='1382320'>to</span> <span m='1382430'>use</span> <span
  m='1382740'>them</span> <span m='1382950'>as</span> <span
  m='1383170'>discrete</span> <span m='1383580'>time</span> <span
  m='1383810'>filters.</span> <span m='1384880'>So,</span> <span
  m='1385500'>another</span> <span m='1385840'>very</span> <span
  m='1386110'>important</span> <span m='1386540'>reason</span> <span
  m='1387480'>for</span> <span m='1387750'>talking</span> <span
  m='1388260'>about</span> <span m='1388580'>the</span> <span
  m='1388650'>kinds</span> <span m='1388970'>of</span> <span
  m='1389040'>mappings</span> <span m='1389570'>that</span> <span
  m='1389850'>we</span> <span m='1390240'>will</span> <span
  m='1390390'>be</span> <span m='1390510'>going</span> <span
  m='1390820'>into</span> <span m='1391820'>is</span> <span
  m='1392240'>to</span> <span m='1392340'>simply</span> <span
  m='1393120'>take</span> <span m='1393410'>advantage</span> <span
  m='1394500'>of</span> <span m='1394820'>what</span> <span
  m='1395010'>has</span> <span m='1395200'>been</span> <span
  m='1395360'>done</span> <span m='1395600'>historically</span> <span
  m='1396610'>in</span> <span m='1396710'>the</span> <span
  m='1396800'>continuous</span> <span m='1397360'>time</span> <span
  m='1397640'>case.</span> </p><p><span m='1401960'>Now,</span> <span
  m='1403320'>if</span> <span m='1403660'>we</span> <span
  m='1403830'>want</span> <span m='1404010'>to</span> <span
  m='1404070'>map</span> <span m='1404960'>continuous</span> <span
  m='1405430'>time</span> <span m='1405630'>filters</span> <span
  m='1406060'>to</span> <span m='1406160'>discrete</span> <span
  m='1406560'>time</span> <span m='1406800'>filters,</span> <span
  m='1408750'>then</span> <span m='1409370'>in</span> <span
  m='1409690'>continuous</span> <span m='1410270'>time,</span> <span
  m='1410770'>we're</span> <span m='1410960'>talking</span> <span
  m='1411330'>about</span> <span m='1411540'>a</span> <span
  m='1411580'>system</span> <span m='1412000'>function</span> <span
  m='1413660'>and</span> <span m='1414000'>an</span> <span
  m='1414100'>associated</span> <span m='1414820'>differential</span> <span
  m='1415380'>equation.</span> <span m='1417840'>In</span> <span
  m='1418030'>discrete</span> <span m='1418510'>time,</span> <span
  m='1418940'>there</span> <span m='1419310'>is</span> <span
  m='1419650'>the</span> <span m='1419850'>corresponding</span> <span
  m='1421710'>system</span> <span m='1422130'>function</span> <span
  m='1423230'>and</span> <span m='1423940'>the</span> <span
  m='1424330'>corresponding</span> <span m='1425490'>difference</span> <span
  m='1425850'>equation.</span> <span m='1429170'>Basically</span> <span
  m='1429690'>what</span> <span m='1429900'>we</span> <span
  m='1430010'>want</span> <span m='1430200'>to</span> <span
  m='1430280'>do</span> <span m='1430750'>is</span> <span
  m='1431540'>generate</span> <span m='1432490'>from</span> <span
  m='1433130'>a</span> <span m='1433350'>continuous</span> <span
  m='1433960'>time</span> <span m='1434560'>system</span> <span
  m='1435990'>in</span> <span m='1436140'>some</span> <span
  m='1436430'>way</span> <span m='1436950'>a</span> <span
  m='1437570'>discrete</span> <span m='1438000'>time</span> <span
  m='1438220'>system</span> <span m='1438940'>that</span> <span
  m='1439640'>meets</span> <span m='1440330'>an</span> <span
  m='1440500'>associated</span> <span m='1441730'>set</span> <span
  m='1442240'>of</span> <span m='1442520'>desired</span> <span
  m='1442970'>specifications.</span> </p><p><span m='1445650'>Now,</span> <span
  m='1446280'>there</span> <span m='1446450'>are</span> <span
  m='1446510'>certain</span> <span m='1447190'>constraints</span> <span
  m='1448030'>that</span> <span m='1448510'>it's</span> <span
  m='1449530'>reasonable</span> <span m='1450190'>and</span> <span
  m='1450270'>important</span> <span m='1450930'>to</span> <span
  m='1451410'>impose</span> <span m='1452090'>on</span> <span
  m='1452730'>whatever</span> <span m='1453060'>kinds</span> <span
  m='1453360'>of</span> <span m='1453410'>mappings</span> <span
  m='1453910'>we</span> <span m='1454030'>use.</span> <span
  m='1455940'>Obviously,</span> <span m='1456440'>we</span> <span
  m='1456490'>want</span> <span m='1456710'>a</span> <span
  m='1456770'>mapping</span> <span m='1457250'>that</span> <span
  m='1457400'>will</span> <span m='1457560'>take</span> <span
  m='1457990'>our</span> <span m='1458670'>continuous</span> <span
  m='1459230'>time</span> <span m='1459460'>system</span> <span
  m='1459870'>function</span> <span m='1460900'>and</span> <span
  m='1461030'>map</span> <span m='1461280'>it</span> <span m='1461410'>to</span>
  <span m='1461580'>a</span> <span m='1461900'>discrete</span> <span
  m='1462330'>time</span> <span m='1462570'>system</span> <span
  m='1462990'>function.</span> <span m='1464780'>Correspondingly</span> <span
  m='1464900'>in</span> <span m='1464980'>the</span> <span
  m='1465100'>time</span> <span m='1465390'>domain,</span> <span
  m='1466480'>there</span> <span m='1466870'>is</span> <span
  m='1467420'>a</span> <span m='1467680'>continuous</span> <span
  m='1468210'>time</span> <span m='1468480'>impulse</span> <span
  m='1468940'>response</span> <span m='1470260'>that</span> <span
  m='1470600'>maps</span> <span m='1470930'>to</span> <span
  m='1471030'>the</span> <span m='1471790'>associated</span> <span
  m='1472520'>discrete</span> <span m='1472900'>time</span> <span
  m='1473130'>impulse</span> <span m='1473550'>response.</span> <span
  m='1475610'>These</span> <span m='1475870'>are</span> <span
  m='1476140'>more</span> <span m='1476380'>or</span> <span
  m='1476410'>less</span> <span m='1476670'>natural.</span> <span
  m='1477710'>The</span> <span m='1477840'>two</span> <span
  m='1478180'>that</span> <span m='1478430'>are</span> <span
  m='1478550'>important</span> <span m='1479240'>and</span> <span
  m='1479960'>sometimes</span> <span m='1480440'>easy</span> <span
  m='1480670'>to</span> <span m='1480750'>lose</span> <span
  m='1480970'>sight</span> <span m='1481310'>of</span> <span
  m='1482030'>are</span> <span m='1482430'>the</span> <span
  m='1482650'>two</span> <span m='1482830'>that</span> <span
  m='1482980'>I</span> <span m='1483080'>indicate</span> <span
  m='1483550'>here.</span> </p><p><span m='1485450'>In</span> <span
  m='1485610'>particular,</span> <span m='1486670'>if</span> <span
  m='1487230'>we</span> <span m='1487650'>are</span> <span
  m='1488570'>mapping</span> <span m='1490070'>a</span> <span
  m='1490150'>continuous</span> <span m='1490720'>time</span> <span
  m='1490970'>filter</span> <span m='1491430'>with,</span> <span
  m='1491610'>let's</span> <span m='1491860'>say,</span> <span
  m='1492450'>a</span> <span m='1492970'>desired</span> <span
  m='1493650'>or</span> <span m='1493740'>desirable</span> <span
  m='1494590'>frequency</span> <span m='1495130'>response</span> <span
  m='1496400'>to</span> <span m='1496890'>a</span> <span
  m='1497060'>discrete</span> <span m='1497500'>time</span> <span
  m='1497720'>filter</span> <span m='1498420'>and</span> <span
  m='1498520'>we</span> <span m='1498660'>would</span> <span
  m='1498800'>like</span> <span m='1499530'>to</span> <span
  m='1499680'>preserve</span> <span m='1500310'>the</span> <span
  m='1500400'>good</span> <span m='1500650'>qualities</span> <span
  m='1501280'>of</span> <span m='1501340'>that</span> <span
  m='1501560'>frequency</span> <span m='1502060'>response</span> <span
  m='1503060'>as</span> <span m='1503240'>we</span> <span
  m='1503360'>look</span> <span m='1503680'>at</span> <span
  m='1503920'>the</span> <span m='1503990'>discrete</span> <span
  m='1504410'>time</span> <span m='1504640'>frequency</span> <span
  m='1505160'>response,</span> <span m='1508040'>then</span> <span
  m='1509250'>it's</span> <span m='1509460'>important</span> <span
  m='1510580'>what</span> <span m='1511660'>happens</span> <span
  m='1512280'>in</span> <span m='1512500'>the</span> <span
  m='1512680'>s-plane</span> <span m='1513770'>for</span> <span
  m='1513900'>the</span> <span m='1514150'>continuous</span> <span
  m='1514680'>time</span> <span m='1514910'>filter</span> <span
  m='1515400'>along</span> <span m='1515690'>the</span> <span
  m='1515770'>j</span> <span m='1516010'>omega</span> <span
  m='1516370'>axis</span> <span m='1517900'>relate</span> <span
  m='1518430'>in</span> <span m='1518610'>a</span> <span m='1518670'>nice</span>
  <span m='1518990'>way</span> <span m='1519750'>to</span> <span
  m='1519860'>what</span> <span m='1520020'>happens</span> <span
  m='1520860'>in</span> <span m='1521330'>the</span> <span
  m='1521430'>z-plane</span> <span m='1522410'>around</span> <span
  m='1522710'>the</span> <span m='1522790'>unit</span> <span
  m='1523110'>circle,</span> <span m='1524310'>because</span> <span
  m='1525350'>it's</span> <span m='1525590'>this</span> <span
  m='1525870'>over</span> <span m='1526160'>here</span> <span
  m='1527790'>that</span> <span m='1527950'>represents</span> <span
  m='1528550'>the</span> <span m='1528630'>frequency</span> <span
  m='1529170'>response</span> <span m='1529900'>in</span> <span
  m='1530020'>continuous</span> <span m='1530630'>time</span> <span
  m='1531520'>and</span> <span m='1531690'>this</span> <span
  m='1531880'>contour</span> <span m='1532510'>over</span> <span
  m='1532720'>here</span> <span m='1533440'>that</span> <span
  m='1533580'>represents</span> <span m='1534130'>the</span> <span
  m='1534200'>frequency</span> <span m='1534670'>response</span> <span
  m='1535440'>in</span> <span m='1535560'>discrete</span> <span
  m='1535980'>time.</span> <span m='1536570'>So</span> <span
  m='1536750'>that's</span> <span m='1537170'>an</span> <span
  m='1537260'>important</span> <span m='1537670'>property.</span> <span
  m='1538090'>We</span> <span m='1538180'>want</span> <span
  m='1538490'>to</span> <span m='1538800'>kind</span> <span
  m='1538960'>of</span> <span m='1539020'>the</span> <span m='1539150'>j</span>
  <span m='1539540'>omega</span> <span m='1539750'>axis</span> <span
  m='1540960'>to</span> <span m='1541100'>map</span> <span m='1542180'>to</span>
  <span m='1542830'>the</span> <span m='1542930'>unit</span> <span
  m='1543240'>circle.</span> <span m='1544370'>Another</span> <span
  m='1545330'>more</span> <span m='1545610'>or</span> <span
  m='1545630'>less</span> <span m='1545840'>natural</span> <span
  m='1546430'>condition</span> <span m='1546920'>to</span> <span
  m='1547080'>impose</span> <span m='1548730'>is</span> <span
  m='1549090'>a</span> <span m='1549160'>condition</span> <span
  m='1549670'>that</span> <span m='1550350'>if</span> <span
  m='1550550'>we</span> <span m='1552060'>are</span> <span
  m='1552450'>assured</span> <span m='1552870'>in</span> <span
  m='1552960'>some</span> <span m='1553230'>way</span> <span
  m='1553570'>that</span> <span m='1553790'>our</span> <span
  m='1553960'>continuous</span> <span m='1554490'>time</span> <span
  m='1554740'>filter</span> <span m='1555160'>is</span> <span
  m='1555230'>stable,</span> <span m='1556410'>then</span> <span
  m='1557270'>we</span> <span m='1557400'>would</span> <span
  m='1557580'>like</span> <span m='1558360'>to</span> <span
  m='1559400'>concentrate</span> <span m='1560060'>on</span> <span
  m='1560160'>design</span> <span m='1560510'>procedures</span> <span
  m='1561460'>that</span> <span m='1561990'>more</span> <span
  m='1562210'>or</span> <span m='1562260'>less</span> <span
  m='1562510'>preserve</span> <span m='1563060'>that</span> <span
  m='1563830'>and</span> <span m='1564140'>will</span> <span
  m='1564300'>give</span> <span m='1564530'>us</span> <span
  m='1564910'>stable</span> <span m='1565410'>digital</span> <span
  m='1565760'>filters.</span> </p><p><span m='1567550'>So</span> <span
  m='1567690'>these</span> <span m='1567980'>are</span> <span
  m='1568800'>kind</span> <span m='1568930'>of</span> <span
  m='1569060'>reasonable</span> <span m='1570510'>conditions</span> <span
  m='1571010'>to</span> <span m='1571150'>impose</span> <span
  m='1571560'>on</span> <span m='1571670'>the</span> <span
  m='1571740'>procedure.</span> <span m='1573150'>What</span> <span
  m='1573350'>I'd</span> <span m='1573520'>like</span> <span
  m='1573860'>to</span> <span m='1575000'>do</span> <span m='1575520'>in</span>
  <span m='1575590'>the</span> <span m='1575660'>remainder</span> <span
  m='1576060'>of</span> <span m='1576165'>this</span> <span
  m='1576270'>lecture</span> <span m='1576780'>is</span> <span
  m='1576960'>look</span> <span m='1577180'>at</span> <span
  m='1577380'>two</span> <span m='1578990'>common</span> <span
  m='1580030'>procedures</span> <span m='1580710'>for</span> <span
  m='1580820'>mapping</span> <span m='1581230'>continuous</span> <span
  m='1581820'>time</span> <span m='1582040'>filters</span> <span
  m='1582570'>to</span> <span m='1582690'>discrete</span> <span
  m='1583120'>time</span> <span m='1583340'>filters.</span> </p><p><span
  m='1585370'>The</span> <span m='1585470'>first</span> <span
  m='1585780'>one</span> <span m='1585930'>that</span> <span
  m='1586090'>I</span> <span m='1586410'>want</span> <span m='1586590'>to</span>
  <span m='1586660'>talk</span> <span m='1586960'>about</span> <span
  m='1587280'>is</span> <span m='1587400'>one</span> <span
  m='1587660'>that,</span> <span m='1587860'>in</span> <span
  m='1588020'>fact,</span> <span m='1588590'>is</span> <span
  m='1589260'>very</span> <span m='1589700'>frequently</span> <span
  m='1590270'>used,</span> <span m='1592150'>and</span> <span
  m='1592950'>also</span> <span m='1593800'>one</span> <span
  m='1594440'>that,</span> <span m='1594830'>as</span> <span
  m='1595070'>we'll</span> <span m='1595210'>see</span> <span
  m='1595730'>for</span> <span m='1595940'>a</span> <span
  m='1595980'>variety</span> <span m='1596440'>of</span> <span
  m='1596550'>reasons,</span> <span m='1597220'>is</span> <span
  m='1597910'>highly</span> <span m='1598480'>undesirable.</span> <span
  m='1600990'>The</span> <span m='1601100'>second</span> <span
  m='1601820'>is</span> <span m='1602050'>one</span> <span
  m='1602610'>that</span> <span m='1603010'>is</span> <span
  m='1603240'>also</span> <span m='1603560'>frequently</span> <span
  m='1604080'>used,</span> <span m='1604530'>and</span> <span
  m='1604660'>as</span> <span m='1604830'>we'll</span> <span
  m='1604930'>see</span> <span m='1605760'>is,</span> <span
  m='1607350'>in</span> <span m='1607470'>certain</span> <span
  m='1607760'>situations,</span> <span m='1608570'>very</span> <span
  m='1608830'>desirable.</span> </p><p><span m='1610280'>The</span> <span
  m='1610380'>first</span> <span m='1610700'>one</span> <span
  m='1610850'>that</span> <span m='1610960'>I</span> <span
  m='1611010'>want</span> <span m='1611200'>to</span> <span
  m='1611260'>talk</span> <span m='1611590'>about</span> <span
  m='1612080'>is</span> <span m='1613020'>the</span> <span
  m='1613320'>more</span> <span m='1613570'>or</span> <span
  m='1613600'>less</span> <span m='1613830'>intuitive</span> <span
  m='1614930'>simple</span> <span m='1615880'>procedure</span> <span
  m='1617550'>of</span> <span m='1617850'>mapping</span> <span
  m='1618310'>a</span> <span m='1619680'>differential</span> <span
  m='1620260'>equation</span> <span m='1620800'>to</span> <span
  m='1620930'>a</span> <span m='1620990'>difference</span> <span
  m='1621340'>equation</span> <span m='1622440'>by</span> <span
  m='1623430'>simply</span> <span m='1623790'>replacing</span> <span
  m='1624790'>derivatives</span> <span m='1626070'>by</span> <span
  m='1626890'>differences.</span> <span m='1629890'>The</span> <span
  m='1630030'>idea</span> <span m='1630380'>is</span> <span
  m='1630710'>that</span> <span m='1630970'>a</span> <span
  m='1631400'>derivative</span> <span m='1632010'>is</span> <span
  m='1632150'>more</span> <span m='1632380'>or</span> <span
  m='1632420'>less</span> <span m='1632720'>a</span> <span
  m='1632790'>difference,</span> <span m='1633870'>and</span> <span
  m='1634130'>there's</span> <span m='1634300'>some</span> <span
  m='1634520'>dummy</span> <span m='1634840'>parameter</span> <span
  m='1635350'>capital</span> <span m='1635840'>T</span> <span
  m='1636100'>that</span> <span m='1636240'>I've</span> <span
  m='1636390'>thrown</span> <span m='1636700'>in</span> <span
  m='1636830'>here,</span> <span m='1637230'>which</span> <span
  m='1637640'>I</span> <span m='1637720'>won't</span> <span
  m='1638040'>focus</span> <span m='1638460'>too</span> <span
  m='1638590'>much</span> <span m='1638900'>on.</span> </p><p><span
  m='1639720'>But</span> <span m='1640490'>in</span> <span
  m='1640650'>any</span> <span m='1640850'>case,</span> <span
  m='1642350'>this</span> <span m='1643230'>seems</span> <span
  m='1643600'>to</span> <span m='1643725'>have</span> <span
  m='1643850'>some</span> <span m='1644080'>plausibility.</span> <span
  m='1644870'>If</span> <span m='1645000'>we</span> <span
  m='1645110'>take</span> <span m='1645450'>the</span> <span
  m='1645570'>differential</span> <span m='1646160'>equation</span> <span
  m='1646860'>and</span> <span m='1647040'>do</span> <span
  m='1647190'>this</span> <span m='1647430'>with</span> <span
  m='1647560'>all</span> <span m='1647730'>the</span> <span
  m='1647830'>derivatives,</span> <span m='1649710'>both</span> <span
  m='1649990'>in</span> <span m='1650080'>terms</span> <span
  m='1650380'>of</span> <span m='1650510'>y</span> <span m='1650740'>of</span>
  <span m='1650840'>t</span> <span m='1651010'>and</span> <span
  m='1651100'>x</span> <span m='1651340'>of</span> <span m='1651450'>t,</span>
  <span m='1652240'>what</span> <span m='1652410'>we'll</span> <span
  m='1652580'>end</span> <span m='1652770'>up</span> <span
  m='1652950'>with</span> <span m='1653340'>is</span> <span m='1653870'>a</span>
  <span m='1653930'>difference</span> <span m='1654320'>equation.</span>
  </p><p><span m='1656560'>Now</span> <span m='1657170'>what</span> <span
  m='1657360'>we</span> <span m='1657490'>can</span> <span
  m='1657670'>use</span> <span m='1658350'>are</span> <span
  m='1658980'>the</span> <span m='1659220'>properties</span> <span
  m='1660974'>of</span> <span m='1661800'>the</span> <span
  m='1662180'>Laplace</span> <span m='1662540'>transform</span> <span
  m='1663140'>and</span> <span m='1663220'>the</span> <span
  m='1663520'>z-transform</span> <span m='1664480'>to</span> <span
  m='1664590'>see</span> <span m='1665140'>what</span> <span
  m='1665330'>this</span> <span m='1665510'>means</span> <span
  m='1665820'>in</span> <span m='1665920'>terms</span> <span
  m='1666220'>of</span> <span m='1666310'>a</span> <span
  m='1666370'>mapping--</span> <span m='1667440'>in</span> <span
  m='1667580'>particular,</span> <span m='1669060'>using</span> <span
  m='1669430'>the</span> <span m='1669510'>differentiation</span> <span
  m='1670310'>property</span> <span m='1670750'>for</span> <span
  m='1670940'>Laplace</span> <span m='1671360'>transforms.</span> <span
  m='1672390'>In</span> <span m='1672480'>the</span> <span
  m='1672640'>Laplace</span> <span m='1672960'>transform</span> <span
  m='1673530'>domain,</span> <span m='1674790'>we</span> <span
  m='1675240'>would</span> <span m='1675400'>have</span> <span
  m='1675690'>this.</span> <span m='1676970'>Using</span> <span
  m='1677760'>the</span> <span m='1678220'>properties</span> <span
  m='1679280'>for</span> <span m='1680020'>the</span> <span
  m='1680340'>z-transform,</span> <span m='1681072'>the</span> <span
  m='1681720'>z-transform</span> <span m='1682400'>of</span> <span
  m='1682500'>this</span> <span m='1682720'>expression</span> <span
  m='1683270'>would</span> <span m='1683450'>be</span> <span
  m='1683610'>this.</span> <span m='1684740'>So,</span> <span
  m='1685290'>in</span> <span m='1685390'>effect,</span> <span
  m='1685830'>what</span> <span m='1685980'>it</span> <span
  m='1686120'>says</span> <span m='1687690'>is</span> <span
  m='1687970'>that</span> <span m='1688770'>every</span> <span
  m='1689050'>place</span> <span m='1689380'>in</span> <span
  m='1689430'>the</span> <span m='1689510'>system</span> <span
  m='1689950'>function</span> <span m='1690730'>or</span> <span
  m='1690960'>in</span> <span m='1691015'>the</span> <span
  m='1691070'>differential</span> <span m='1691560'>equation</span> <span
  m='1692100'>that</span> <span m='1692230'>we</span> <span
  m='1692370'>would</span> <span m='1692530'>be</span> <span
  m='1692650'>multiplying</span> <span m='1693280'>by</span> <span
  m='1693550'>s</span> <span m='1694450'>when</span> <span
  m='1694720'>Laplace</span> <span m='1695140'>transformed.</span> <span
  m='1696460'>In</span> <span m='1696610'>the</span> <span
  m='1696690'>difference</span> <span m='1697060'>equation,</span> <span
  m='1697620'>we</span> <span m='1697790'>would</span> <span
  m='1697900'>be</span> <span m='1698000'>multiplying</span> <span
  m='1698670'>by</span> <span m='1698830'>this</span> <span
  m='1699070'>factor.</span> </p><p><span m='1701070'>In</span> <span
  m='1701240'>fact,</span> <span m='1701800'>what</span> <span
  m='1702030'>this</span> <span m='1702260'>means</span> <span
  m='1703020'>is</span> <span m='1703300'>that</span> <span
  m='1704200'>the</span> <span m='1705500'>mapping</span> <span
  m='1706600'>from</span> <span m='1706840'>continuous</span> <span
  m='1707420'>time</span> <span m='1707730'>to</span> <span
  m='1707830'>discrete</span> <span m='1708320'>time</span> <span
  m='1709260'>corresponds</span> <span m='1711000'>to</span> <span
  m='1711500'>taking</span> <span m='1711900'>the</span> <span
  m='1712000'>system</span> <span m='1712450'>function</span> <span
  m='1713610'>and</span> <span m='1714440'>replacing</span> <span
  m='1715110'>s</span> <span m='1715960'>wherever</span> <span
  m='1716360'>we</span> <span m='1716510'>see</span> <span m='1716770'>it</span>
  <span m='1717380'>by</span> <span m='1717980'>1</span> <span
  m='1718200'>minus</span> <span m='1718630'>z</span> <span
  m='1718740'>to</span> <span m='1718810'>the</span> <span
  m='1718900'>minus</span> <span m='1719270'>1</span> <span
  m='1719490'>over</span> <span m='1719710'>capital</span> <span
  m='1720180'>T.</span> <span m='1721890'>So</span> <span m='1722560'>if</span>
  <span m='1722750'>we</span> <span m='1722870'>have</span> <span
  m='1723060'>a</span> <span m='1723110'>system</span> <span
  m='1723550'>function</span> <span m='1724720'>in</span> <span
  m='1724870'>continuous</span> <span m='1725490'>time</span> <span
  m='1726460'>and</span> <span m='1726600'>we</span> <span
  m='1726730'>map</span> <span m='1727030'>it</span> <span m='1727220'>to</span>
  <span m='1727340'>a</span> <span m='1727400'>discrete</span> <span
  m='1727840'>time</span> <span m='1728280'>system</span> <span
  m='1728710'>function</span> <span m='1729830'>this</span> <span
  m='1730070'>way</span> <span m='1730530'>by</span> <span
  m='1730720'>replacing</span> <span m='1731220'>derivatives</span> <span
  m='1731750'>by</span> <span m='1731880'>differences,</span> <span
  m='1733070'>then</span> <span m='1733720'>that</span> <span
  m='1733980'>corresponds</span> <span m='1734990'>to</span> <span
  m='1735700'>replacing</span> <span m='1736300'>s</span> <span
  m='1736690'>by</span> <span m='1737480'>1</span> <span
  m='1737690'>minus</span> <span m='1738060'>z</span> <span
  m='1738160'>to</span> <span m='1738220'>the</span> <span
  m='1738300'>minus</span> <span m='1738680'>1</span> <span
  m='1739080'>over</span> <span m='1739320'>capital</span> <span
  m='1739800'>T.</span> </p><p><span m='1741390'>Now</span> <span
  m='1741680'>we'll</span> <span m='1741860'>see</span> <span
  m='1742650'>shortly</span> <span m='1743420'>what</span> <span
  m='1744290'>this</span> <span m='1744620'>mapping</span> <span
  m='1745340'>actually</span> <span m='1745740'>means</span> <span
  m='1746190'>more</span> <span m='1746350'>specifically</span> <span
  m='1747370'>in</span> <span m='1747540'>relating</span> <span
  m='1747760'>the</span> <span m='1747980'>s-plane</span> <span
  m='1748550'>to</span> <span m='1748640'>the</span> <span
  m='1748760'>z-plane.</span> <span m='1749980'>Let</span> <span
  m='1750150'>me</span> <span m='1750270'>just</span> <span
  m='1750540'>quickly,</span> <span m='1750910'>because</span> <span
  m='1751290'>I</span> <span m='1751320'>want</span> <span m='1751540'>to</span>
  <span m='1751580'>refer</span> <span m='1751980'>to</span> <span
  m='1752070'>this,</span> <span m='1752990'>also</span> <span
  m='1753370'>point</span> <span m='1753720'>to</span> <span
  m='1753870'>another</span> <span m='1755000'>procedure</span> <span
  m='1755550'>very</span> <span m='1755760'>much</span> <span
  m='1756010'>like</span> <span m='1756260'>backward</span> <span
  m='1756670'>differences</span> <span m='1757750'>which</span> <span
  m='1758040'>corresponds</span> <span m='1758820'>to</span> <span
  m='1758930'>replacing</span> <span m='1759480'>derivatives</span> <span
  m='1760660'>not</span> <span m='1760910'>by</span> <span
  m='1761050'>the</span> <span m='1761150'>backward</span> <span
  m='1761660'>differences</span> <span m='1762160'>that</span> <span
  m='1762260'>I</span> <span m='1762330'>just</span> <span
  m='1762540'>showed,</span> <span m='1763310'>but</span> <span
  m='1763600'>by</span> <span m='1763770'>forward</span> <span
  m='1764300'>differences.</span> <span m='1765640'>In</span> <span
  m='1765740'>that</span> <span m='1766020'>case,</span> <span
  m='1766700'>then,</span> <span m='1767680'>the</span> <span
  m='1767790'>mapping</span> <span m='1768820'>corresponds</span> <span
  m='1769210'>to</span> <span m='1769600'>replacing</span> <span
  m='1770230'>s</span> <span m='1770630'>by</span> <span m='1771940'>z</span>
  <span m='1772056'>to</span> <span m='1772173'>the</span> <span
  m='1772290'>minus</span> <span m='1773020'>1</span> <span
  m='1773420'>over</span> <span m='1773790'>capital</span> <span
  m='1774290'>T.</span> <span m='1775442'>It</span> <span
  m='1775800'>looks</span> <span m='1776030'>very</span> <span
  m='1776220'>similar</span> <span m='1776620'>to</span> <span
  m='1776670'>the</span> <span m='1776750'>previous</span> <span
  m='1777270'>case.</span> <span m='1779270'>So</span> <span
  m='1779890'>there</span> <span m='1780540'>the</span> <span
  m='1780980'>relationship</span> <span m='1781720'>between</span> <span
  m='1782070'>these</span> <span m='1782200'>system</span> <span
  m='1782610'>functions</span> <span m='1783330'>is</span> <span
  m='1783880'>what</span> <span m='1784040'>I</span> <span
  m='1784110'>indicate</span> <span m='1784580'>here.</span> </p><p><span
  m='1787800'>Let's</span> <span m='1788300'>just</span> <span
  m='1789370'>take</span> <span m='1789580'>a</span> <span
  m='1789650'>look</span> <span m='1789970'>at</span> <span
  m='1790650'>what</span> <span m='1791950'>those</span> <span
  m='1792250'>mappings</span> <span m='1792710'>correspond</span> <span
  m='1793390'>to</span> <span m='1793590'>when</span> <span
  m='1793760'>we</span> <span m='1793860'>look</span> <span
  m='1794080'>at</span> <span m='1794200'>this</span> <span
  m='1794430'>specifically</span> <span m='1795780'>in</span> <span
  m='1795910'>the</span> <span m='1796040'>s-plane</span> <span
  m='1796730'>and</span> <span m='1796900'>in</span> <span
  m='1797010'>the</span> <span m='1797120'>z-plane.</span> <span
  m='1799250'>What</span> <span m='1799430'>I</span> <span
  m='1799490'>show</span> <span m='1799790'>here</span> <span
  m='1800250'>is</span> <span m='1801010'>the</span> <span
  m='1801500'>s-plane,</span> <span m='1802890'>and</span> <span
  m='1803640'>of</span> <span m='1803770'>course</span> <span
  m='1804210'>it's</span> <span m='1804920'>things</span> <span
  m='1805290'>on</span> <span m='1805340'>the</span> <span
  m='1805420'>left</span> <span m='1805740'>half</span> <span
  m='1805980'>of</span> <span m='1806080'>the</span> <span
  m='1806410'>s-plane,</span> <span m='1806720'>poles</span> <span
  m='1807020'>on</span> <span m='1807055'>the</span> <span
  m='1807090'>left</span> <span m='1807350'>half</span> <span
  m='1807560'>of</span> <span m='1807680'>the</span> <span
  m='1807830'>s-plane</span> <span m='1808010'>that</span> <span
  m='1808320'>would</span> <span m='1808480'>guarantee</span> <span
  m='1808950'>stability.</span> <span m='1810350'>It's</span> <span
  m='1811210'>the</span> <span m='1811460'>j</span> <span
  m='1811690'>omega</span> <span m='1812000'>axis</span> <span
  m='1812550'>the</span> <span m='1812680'>tells</span> <span
  m='1813030'>us</span> <span m='1813190'>about</span> <span
  m='1813550'>the</span> <span m='1813760'>frequency</span> <span
  m='1814340'>response,</span> <span m='1816570'>and</span> <span
  m='1817170'>in</span> <span m='1817340'>the</span> <span
  m='1817410'>z-plane</span> <span m='1819330'>it's</span> <span
  m='1819850'>the</span> <span m='1820010'>unit</span> <span
  m='1820330'>circle</span> <span m='1821110'>that</span> <span
  m='1821630'>tells</span> <span m='1821950'>us</span> <span
  m='1822100'>about</span> <span m='1822380'>the</span> <span
  m='1822450'>frequency</span> <span m='1822990'>response.</span> <span
  m='1824490'>Things</span> <span m='1824780'>inside</span> <span
  m='1825200'>the</span> <span m='1825270'>unit</span> <span
  m='1825560'>circle,</span> <span m='1826470'>or</span> <span
  m='1826580'>poles</span> <span m='1826930'>inside</span> <span
  m='1827280'>the</span> <span m='1827340'>unit</span> <span
  m='1827560'>circle,</span> <span m='1827930'>that</span> <span
  m='1827980'>guarantee</span> <span m='1828460'>stability.</span> </p><p><span
  m='1830170'>Now</span> <span m='1830960'>the</span> <span
  m='1831080'>mapping</span> <span m='1831710'>from</span> <span
  m='1833110'>s-plane</span> <span m='1833680'>to</span> <span
  m='1833760'>the</span> <span m='1833840'>z-plane</span> <span
  m='1834470'>corresponding</span> <span m='1835310'>to</span> <span
  m='1835600'>replacing</span> <span m='1836250'>derivatives</span> <span
  m='1836900'>by</span> <span m='1837600'>backward</span> <span
  m='1838060'>differences</span> <span m='1839330'>in</span> <span
  m='1839480'>fact</span> <span m='1840660'>can</span> <span
  m='1841230'>be</span> <span m='1841380'>shown</span> <span
  m='1841810'>to</span> <span m='1841940'>correspond</span> <span
  m='1843380'>to</span> <span m='1844050'>mapping</span> <span
  m='1845110'>the</span> <span m='1845220'>j</span> <span
  m='1845570'>omega</span> <span m='1845820'>axis</span> <span
  m='1847700'>not</span> <span m='1848140'>to</span> <span
  m='1848370'>the</span> <span m='1848390'>unit</span> <span
  m='1848760'>circle,</span> <span m='1849750'>but</span> <span
  m='1850290'>to</span> <span m='1850420'>the</span> <span
  m='1850520'>little</span> <span m='1850770'>circle</span> <span
  m='1851220'>that</span> <span m='1851350'>I</span> <span
  m='1851430'>show</span> <span m='1851780'>here,</span> <span
  m='1852160'>which</span> <span m='1852390'>is</span> <span
  m='1852510'>inside</span> <span m='1852940'>the</span> <span
  m='1853010'>unit</span> <span m='1853290'>circle.</span> <span
  m='1855230'>The</span> <span m='1855360'>left</span> <span
  m='1855690'>half</span> <span m='1856530'>of</span> <span
  m='1856730'>the</span> <span m='1857100'>s-plane</span> <span
  m='1857820'>maps</span> <span m='1858300'>to</span> <span
  m='1858420'>the</span> <span m='1858550'>inside</span> <span
  m='1858960'>of</span> <span m='1859010'>that</span> <span
  m='1859230'>circle.</span> <span m='1860430'>What</span> <span
  m='1860630'>does</span> <span m='1860730'>that</span> <span
  m='1860960'>mean?</span> </p><p><span m='1861210'>That</span> <span
  m='1861400'>means</span> <span m='1861840'>that</span> <span
  m='1862430'>if</span> <span m='1862630'>we</span> <span
  m='1862770'>have</span> <span m='1863640'>a</span> <span
  m='1863730'>really</span> <span m='1864140'>good</span> <span
  m='1864880'>frequency</span> <span m='1865390'>response</span> <span
  m='1866500'>characteristic</span> <span m='1867180'>along</span> <span
  m='1867470'>this</span> <span m='1868610'>contour</span> <span
  m='1869500'>in</span> <span m='1869630'>the</span> <span
  m='1869980'>s-plane,</span> <span m='1870980'>we'll</span> <span
  m='1871150'>see</span> <span m='1871360'>that</span> <span
  m='1871590'>same</span> <span m='1871970'>frequency</span> <span
  m='1872530'>response</span> <span m='1873270'>along</span> <span
  m='1873610'>this</span> <span m='1873800'>little</span> <span
  m='1874050'>circle.</span> <span m='1874910'>That's</span> <span
  m='1875160'>not</span> <span m='1875400'>the</span> <span
  m='1875500'>one</span> <span m='1875690'>that</span> <span
  m='1875795'>we</span> <span m='1875900'>want,</span> <span
  m='1876200'>though--</span> <span m='1877030'>we</span> <span
  m='1877160'>would</span> <span m='1877310'>like</span> <span
  m='1877580'>to</span> <span m='1877690'>see</span> <span
  m='1878050'>that</span> <span m='1878270'>same</span> <span
  m='1878500'>frequency</span> <span m='1879010'>response</span> <span
  m='1879980'>around</span> <span m='1880340'>the</span> <span
  m='1880420'>unit</span> <span m='1880720'>circle.</span> </p><p><span
  m='1882080'>To</span> <span m='1882190'>emphasize</span> <span
  m='1883110'>this</span> <span m='1883330'>point</span> <span
  m='1884000'>even</span> <span m='1884280'>more--</span> <span
  m='1884630'>suppose,</span> <span m='1885250'>for</span> <span
  m='1885380'>example,</span> <span m='1886960'>that</span> <span
  m='1887220'>we</span> <span m='1887370'>had</span> <span m='1888570'>a</span>
  <span m='1888680'>pair</span> <span m='1889010'>of</span> <span
  m='1889090'>poles</span> <span m='1890510'>in</span> <span
  m='1891040'>our</span> <span m='1892070'>continuous</span> <span
  m='1892640'>time</span> <span m='1892860'>system</span> <span
  m='1893230'>function</span> <span m='1893770'>that</span> <span
  m='1893890'>looked</span> <span m='1894170'>like</span> <span
  m='1894460'>this.</span> <span m='1896000'>Then,</span> <span
  m='1896630'>where</span> <span m='1897120'>they're</span> <span
  m='1897400'>likely</span> <span m='1897790'>to</span> <span
  m='1897880'>end</span> <span m='1898170'>up</span> <span m='1899240'>in</span>
  <span m='1899880'>the</span> <span m='1899960'>z-plane</span> <span
  m='1901950'>is</span> <span m='1902610'>inside</span> <span
  m='1903090'>the</span> <span m='1903160'>unit</span> <span
  m='1903410'>circle,</span> <span m='1903790'>of</span> <span
  m='1903910'>course.</span> <span m='1905050'>But</span> <span
  m='1906040'>if</span> <span m='1906570'>the</span> <span
  m='1906670'>poles</span> <span m='1907230'>here</span> <span
  m='1907670'>are</span> <span m='1907890'>close</span> <span
  m='1908230'>to</span> <span m='1908330'>the</span> <span m='1908420'>j</span>
  <span m='1908740'>omega</span> <span m='1908960'>axis,</span> <span
  m='1910080'>that</span> <span m='1910290'>means</span> <span
  m='1910580'>that</span> <span m='1910740'>these</span> <span
  m='1911020'>poles</span> <span m='1911770'>will</span> <span
  m='1911950'>be</span> <span m='1912090'>close</span> <span
  m='1912460'>to</span> <span m='1912580'>this</span> <span
  m='1912840'>circle,</span> <span m='1913930'>but</span> <span
  m='1914090'>in</span> <span m='1914200'>fact</span> <span
  m='1914610'>might</span> <span m='1914800'>be</span> <span
  m='1914940'>very</span> <span m='1915270'>far</span> <span
  m='1915560'>away</span> <span m='1915820'>from</span> <span
  m='1915990'>the</span> <span m='1916070'>unit</span> <span
  m='1916360'>circle.</span> <span m='1918320'>What</span> <span
  m='1918660'>would</span> <span m='1918870'>happen,</span> <span
  m='1919080'>then,</span> <span m='1919490'>is</span> <span
  m='1919930'>that</span> <span m='1920550'>if</span> <span
  m='1920780'>we</span> <span m='1920910'>saw</span> <span m='1921290'>in</span>
  <span m='1921440'>the</span> <span m='1921530'>continuous</span> <span
  m='1922060'>time</span> <span m='1922300'>filter</span> <span
  m='1922750'>a</span> <span m='1922790'>very</span> <span
  m='1922990'>sharp</span> <span m='1923370'>resonance,</span> <span
  m='1925710'>the</span> <span m='1925800'>discrete</span> <span
  m='1926220'>time</span> <span m='1926460'>filter</span> <span
  m='1927180'>in</span> <span m='1927280'>fact</span> <span
  m='1927600'>might</span> <span m='1927780'>very</span> <span
  m='1927960'>well</span> <span m='1928130'>have</span> <span
  m='1928280'>that</span> <span m='1928440'>resonance</span> <span
  m='1928900'>broadened</span> <span m='1929410'>considerably</span> <span
  m='1930630'>because</span> <span m='1931210'>the</span> <span
  m='1931300'>poles</span> <span m='1931680'>are</span> <span
  m='1931740'>so</span> <span m='1931950'>far</span> <span
  m='1932260'>away</span> <span m='1932500'>from</span> <span
  m='1932660'>the</span> <span m='1932730'>unit</span> <span
  m='1932990'>circle.</span> </p><p><span m='1934500'>Now,</span> <span
  m='1935060'>one</span> <span m='1937170'>plus</span> <span
  m='1937840'>with</span> <span m='1938250'>this</span> <span
  m='1938470'>method,</span> <span m='1938950'>and</span> <span
  m='1939060'>it's</span> <span m='1939180'>about</span> <span
  m='1939430'>the</span> <span m='1939530'>only</span> <span
  m='1939760'>one,</span> <span m='1940950'>is</span> <span
  m='1941180'>the</span> <span m='1941270'>fact</span> <span
  m='1941710'>that</span> <span m='1942560'>the</span> <span
  m='1943070'>left</span> <span m='1943400'>half</span> <span
  m='1943640'>of</span> <span m='1943720'>the</span> <span
  m='1943800'>s-plane</span> <span m='1944580'>maps</span> <span
  m='1945570'>inside</span> <span m='1947130'>the</span> <span
  m='1947220'>unit</span> <span m='1947540'>circle--</span> <span
  m='1947920'>in</span> <span m='1948070'>fact,</span> <span
  m='1948460'>inside</span> <span m='1949210'>a</span> <span
  m='1949290'>circle</span> <span m='1949700'>inside</span> <span
  m='1950110'>the</span> <span m='1950180'>unit</span> <span
  m='1950440'>circle,</span> <span m='1950940'>and</span> <span
  m='1951080'>so</span> <span m='1951250'>stability</span> <span
  m='1951820'>is</span> <span m='1951980'>always</span> <span
  m='1952250'>guaranteed.</span> <span m='1953870'>Let</span> <span
  m='1954000'>me</span> <span m='1954110'>just</span> <span
  m='1954340'>quickly</span> <span m='1954710'>mention,</span> <span
  m='1955170'>and</span> <span m='1955260'>you'll</span> <span
  m='1955550'>have</span> <span m='1955690'>a</span> <span
  m='1955770'>chance</span> <span m='1956070'>to</span> <span
  m='1956170'>look</span> <span m='1956380'>at</span> <span
  m='1956470'>this</span> <span m='1956680'>a</span> <span
  m='1956740'>little</span> <span m='1956910'>more</span> <span
  m='1957300'>carefully</span> <span m='1957810'>in</span> <span
  m='1957920'>the</span> <span m='1958270'>video</span> <span
  m='1958590'>course</span> <span m='1958910'>manual,</span> <span
  m='1960090'>that</span> <span m='1960830'>for</span> <span
  m='1961480'>forward</span> <span m='1962040'>differences</span> <span
  m='1962580'>instead</span> <span m='1962890'>of</span> <span
  m='1962960'>backward</span> <span m='1963420'>differences,</span> <span
  m='1965020'>this</span> <span m='1966900'>contour</span> <span
  m='1967470'>in</span> <span m='1967520'>the</span> <span
  m='1967900'>s-plane</span> <span m='1969130'>maps</span> <span
  m='1970400'>to</span> <span m='1971120'>a</span> <span m='1971255'>line</span>
  <span m='1971660'>in</span> <span m='1971750'>the</span> <span
  m='1971820'>z-plane,</span> <span m='1973120'>which</span> <span
  m='1973410'>is</span> <span m='1973780'>a</span> <span m='1973987'>line</span>
  <span m='1974840'>tangent</span> <span m='1975830'>to</span> <span
  m='1975960'>the</span> <span m='1976060'>unit</span> <span
  m='1976380'>circle,</span> <span m='1977870'>and</span> <span
  m='1978470'>in</span> <span m='1978630'>fact</span> <span
  m='1978990'>is</span> <span m='1979090'>the</span> <span
  m='1979180'>line</span> <span m='1979480'>that</span> <span
  m='1979610'>I</span> <span m='1979680'>showed</span> <span
  m='1980030'>there.</span> <span m='1981250'>So</span> <span
  m='1981810'>not</span> <span m='1982030'>only</span> <span
  m='1982470'>are</span> <span m='1982650'>forward</span> <span
  m='1983020'>differences</span> <span m='1984890'>equally</span> <span
  m='1985260'>bad</span> <span m='1985610'>in</span> <span
  m='1985890'>terms</span> <span m='1986240'>of</span> <span
  m='1986310'>the</span> <span m='1986420'>issue</span> <span
  m='1986710'>of</span> <span m='1986800'>whether</span> <span
  m='1987100'>they</span> <span m='1987260'>map</span> <span
  m='1988110'>from</span> <span m='1988260'>the</span> <span
  m='1988350'>j</span> <span m='1988580'>omega</span> <span
  m='1988810'>axis</span> <span m='1989270'>to</span> <span
  m='1989370'>the</span> <span m='1989460'>unit</span> <span
  m='1989740'>circle,</span> <span m='1990770'>but</span> <span
  m='1991570'>they</span> <span m='1991740'>have</span> <span
  m='1992340'>a</span> <span m='1992410'>further</span> <span
  m='1992820'>difficulty</span> <span m='1993440'>associated</span> <span
  m='1994140'>with</span> <span m='1994370'>them,</span> <span
  m='1995170'>which</span> <span m='1995470'>is</span> <span
  m='1996430'>the</span> <span m='1996560'>difficulty</span> <span
  m='1997360'>they</span> <span m='1998320'>may</span> <span
  m='1998540'>not</span> <span m='1999360'>and</span> <span
  m='1999840'>generally</span> <span m='2000260'>don't</span> <span
  m='2000780'>guarantee</span> <span m='2001240'>stability.</span> </p><p><span
  m='2005070'>Now,</span> <span m='2006190'>that's</span> <span
  m='2006480'>one</span> <span m='2007030'>method,</span> <span
  m='2007620'>and</span> <span m='2008620'>one,</span> <span
  m='2008930'>as</span> <span m='2009060'>I</span> <span
  m='2009160'>indicated,</span> <span m='2009650'>that's</span> <span
  m='2009840'>often</span> <span m='2010170'>used</span> <span
  m='2011020'>partly</span> <span m='2014380'>because</span> <span
  m='2015020'>it</span> <span m='2015220'>seems</span> <span
  m='2015600'>so</span> <span m='2015790'>intuitively</span> <span
  m='2016310'>plausible.</span> <span m='2017510'>What</span> <span
  m='2017700'>you</span> <span m='2017810'>can</span> <span
  m='2017950'>see</span> <span m='2018400'>is</span> <span
  m='2018670'>that</span> <span m='2019320'>by</span> <span
  m='2019580'>understanding</span> <span m='2020210'>carefully</span> <span
  m='2020770'>the</span> <span m='2020960'>issues</span> <span
  m='2021590'>and</span> <span m='2021780'>the</span> <span
  m='2021880'>techniques</span> <span m='2022300'>of</span> <span
  m='2022560'>Laplace</span> <span m='2022745'>and</span> <span
  m='2022930'>z-transforms,</span> <span m='2024350'>you</span> <span
  m='2024500'>can</span> <span m='2024660'>begin</span> <span
  m='2024970'>to</span> <span m='2025090'>see</span> <span
  m='2025390'>what</span> <span m='2025600'>some</span> <span
  m='2025780'>of</span> <span m='2025840'>the</span> <span
  m='2025920'>difficulties</span> <span m='2026550'>with</span> <span
  m='2028020'>those</span> <span m='2028280'>methods</span> <span
  m='2028670'>are.</span> </p><p><span m='2030450'>The</span> <span
  m='2030540'>next</span> <span m='2030790'>method</span> <span
  m='2031370'>that</span> <span m='2031840'>I'd</span> <span
  m='2032000'>like</span> <span m='2032210'>to</span> <span
  m='2032320'>talk</span> <span m='2032620'>about</span> <span
  m='2033120'>is</span> <span m='2033560'>a</span> <span
  m='2033630'>method</span> <span m='2034080'>that,</span> <span
  m='2034290'>in</span> <span m='2034390'>fact,</span> <span
  m='2034760'>is</span> <span m='2034890'>very</span> <span
  m='2035810'>commonly</span> <span m='2036360'>used.</span> <span
  m='2037000'>It's</span> <span m='2037140'>a</span> <span
  m='2037190'>very</span> <span m='2037400'>important,</span> <span
  m='2038200'>useful</span> <span m='2038600'>method,</span> <span
  m='2039490'>which</span> <span m='2040570'>kind</span> <span
  m='2040860'>of</span> <span m='2041100'>can</span> <span m='2041250'>be</span>
  <span m='2041360'>motivated</span> <span m='2042160'>by</span> <span
  m='2042350'>thinking</span> <span m='2042840'>along</span> <span
  m='2043190'>the</span> <span m='2043270'>lines</span> <span
  m='2043980'>of</span> <span m='2045220'>mapping</span> <span
  m='2046080'>the</span> <span m='2046330'>continuous</span> <span
  m='2046880'>time</span> <span m='2047120'>filter</span> <span
  m='2047600'>to</span> <span m='2048040'>a</span> <span
  m='2048280'>discrete</span> <span m='2048760'>time</span> <span
  m='2049010'>filter</span> <span m='2051100'>in</span> <span
  m='2051239'>such</span> <span m='2051580'>a</span> <span
  m='2051630'>way</span> <span m='2052389'>that</span> <span
  m='2053150'>the</span> <span m='2053630'>shape</span> <span
  m='2054219'>of</span> <span m='2054350'>the</span> <span
  m='2054469'>impulse</span> <span m='2054929'>response</span> <span
  m='2055254'>is</span> <span m='2055580'>preserved--</span> <span
  m='2056620'>and,</span> <span m='2056820'>in</span> <span
  m='2056920'>fact,</span> <span m='2057320'>more</span> <span
  m='2058179'>specifically</span> <span m='2060000'>so</span> <span
  m='2060280'>that</span> <span m='2060690'>the</span> <span
  m='2060989'>discrete</span> <span m='2061449'>time</span> <span
  m='2061690'>impulse</span> <span m='2062120'>response</span> <span
  m='2063150'>corresponds</span> <span m='2064100'>to</span> <span
  m='2064480'>samples</span> <span m='2065900'>of</span> <span
  m='2066460'>the</span> <span m='2066590'>continuous</span> <span
  m='2067159'>time</span> <span m='2067440'>impulse</span> <span
  m='2067840'>response.</span> <span m='2068960'>And</span> <span
  m='2069280'>this</span> <span m='2069440'>is</span> <span m='2069590'>a</span>
  <span m='2069630'>method</span> <span m='2070080'>that's</span> <span
  m='2070330'>referred</span> <span m='2070790'>to</span> <span
  m='2071159'>as</span> <span m='2072040'>impulse</span> <span
  m='2072800'>invariance.</span> </p><p><span m='2075260'>So</span> <span
  m='2075730'>what</span> <span m='2075889'>impulse</span> <span
  m='2076330'>invariance</span> <span m='2077440'>corresponds</span> <span
  m='2078250'>to</span> <span m='2079360'>is</span> <span
  m='2080250'>designing</span> <span m='2080790'>the</span> <span
  m='2080880'>filter</span> <span m='2081350'>in</span> <span
  m='2081420'>such</span> <span m='2081679'>a</span> <span
  m='2081760'>way</span> <span m='2082620'>that</span> <span
  m='2083270'>the</span> <span m='2083780'>discrete</span> <span
  m='2084280'>time</span> <span m='2085179'>filter</span> <span
  m='2086100'>impulse</span> <span m='2086600'>response</span> <span
  m='2087860'>is</span> <span m='2088460'>simply</span> <span
  m='2089199'>a</span> <span m='2089300'>sample</span> <span
  m='2089760'>version</span> <span m='2090830'>of</span> <span
  m='2091250'>the</span> <span m='2091550'>continuous</span> <span
  m='2092130'>time</span> <span m='2092380'>filter</span> <span
  m='2092760'>impulse</span> <span m='2093139'>response</span> <span
  m='2094310'>with</span> <span m='2094750'>a</span> <span
  m='2095310'>sampling</span> <span m='2097200'>period</span> <span
  m='2097650'>which</span> <span m='2097870'>I</span> <span
  m='2097950'>denote</span> <span m='2098220'>here</span> <span
  m='2098490'>as</span> <span m='2098620'>capital</span> <span
  m='2099100'>T.</span> <span m='2100650'>That</span> <span
  m='2100810'>will</span> <span m='2100940'>turn</span> <span
  m='2101190'>into</span> <span m='2101450'>a</span> <span
  m='2101520'>slightly</span> <span m='2101940'>confusing</span> <span
  m='2103150'>parameter</span> <span m='2104890'>shortly,</span> <span
  m='2105520'>and</span> <span m='2105640'>perhaps</span> <span
  m='2106010'>carried</span> <span m='2106350'>over</span> <span
  m='2106590'>into</span> <span m='2106790'>the</span> <span
  m='2106890'>next</span> <span m='2107180'>lecture.</span> <span
  m='2108270'>Hopefully,</span> <span m='2108680'>we'll</span> <span
  m='2108830'>get</span> <span m='2109000'>that</span> <span
  m='2109220'>straighted</span> <span m='2109540'>out,</span> <span
  m='2109760'>though,</span> <span m='2111220'>within</span> <span
  m='2111900'>those</span> <span m='2112140'>two</span> <span
  m='2112290'>lectures.</span> </p><p><span m='2114030'>Remembering</span> <span
  m='2114810'>the</span> <span m='2115000'>issues</span> <span
  m='2115350'>of</span> <span m='2115430'>sampling,</span> <span
  m='2116760'>the</span> <span m='2117400'>discrete</span> <span
  m='2117840'>time</span> <span m='2118680'>frequency</span> <span
  m='2119270'>response,</span> <span m='2120280'>then</span> <span
  m='2121490'>since</span> <span m='2121770'>the</span> <span
  m='2121850'>frequency</span> <span m='2122290'>responses</span> <span
  m='2122900'>the</span> <span m='2122970'>Fourier</span> <span
  m='2123370'>transform</span> <span m='2124010'>of</span> <span
  m='2124090'>the</span> <span m='2124190'>impulse</span> <span
  m='2124630'>response</span> <span m='2125770'>is</span> <span
  m='2125960'>related</span> <span m='2126840'>to</span> <span
  m='2127180'>the</span> <span m='2127300'>continuous</span> <span
  m='2127890'>time</span> <span m='2128320'>impulse</span> <span
  m='2128780'>response</span> <span m='2129110'>as</span> <span
  m='2129440'>I</span> <span m='2129540'>indicate</span> <span
  m='2130050'>here,</span> <span m='2131950'>what</span> <span
  m='2132160'>this</span> <span m='2132410'>says</span> <span
  m='2133320'>is</span> <span m='2133650'>that</span> <span
  m='2134110'>it</span> <span m='2134440'>is</span> <span m='2136600'>the</span>
  <span m='2137590'>superposition</span> <span m='2140090'>of</span> <span
  m='2141130'>replications</span> <span m='2142000'>of</span> <span
  m='2142600'>the</span> <span m='2142800'>continuous</span> <span
  m='2143440'>time</span> <span m='2143620'>frequency</span> <span
  m='2144190'>response,</span> <span m='2146600'>linearly</span> <span
  m='2147140'>scaled</span> <span m='2147570'>in</span> <span
  m='2147700'>frequency</span> <span m='2149160'>and</span> <span
  m='2150420'>shifted</span> <span m='2151020'>and</span> <span
  m='2151440'>added</span> <span m='2152050'>to</span> <span
  m='2152210'>each</span> <span m='2152410'>other.</span> <span
  m='2153120'>It's</span> <span m='2153440'>the</span> <span
  m='2153520'>same</span> <span m='2153770'>old</span> <span
  m='2154940'>sort</span> <span m='2155055'>of</span> <span
  m='2155170'>shifting,</span> <span m='2155670'>adding,</span> <span
  m='2155980'>or</span> <span m='2156340'>aliasing</span> <span
  m='2156830'>issue--</span> <span m='2157170'>the</span> <span
  m='2157240'>same</span> <span m='2157450'>sampling</span> <span
  m='2157950'>issues</span> <span m='2158290'>that</span> <span
  m='2158430'>we've</span> <span m='2158710'>addressed</span> <span
  m='2159090'>before.</span> </p><p><span m='2161740'>This</span> <span
  m='2161950'>equation</span> <span m='2162490'>will</span> <span
  m='2162670'>help</span> <span m='2162950'>us</span> <span
  m='2163120'>understand</span> <span m='2163920'>what</span> <span
  m='2164080'>the</span> <span m='2164170'>frequency</span> <span
  m='2164690'>response</span> <span m='2165210'>looks</span> <span
  m='2165480'>like.</span> <span m='2166290'>But</span> <span
  m='2166720'>in</span> <span m='2166870'>terms</span> <span
  m='2167310'>of</span> <span m='2168020'>an</span> <span
  m='2168170'>analytical</span> <span m='2168720'>procedure</span> <span
  m='2169600'>for</span> <span m='2170470'>mapping</span> <span
  m='2171430'>the</span> <span m='2171560'>continuous</span> <span
  m='2172120'>time</span> <span m='2172360'>system</span> <span
  m='2172780'>function</span> <span m='2173740'>to</span> <span
  m='2173850'>a</span> <span m='2173910'>discrete</span> <span
  m='2174340'>time</span> <span m='2174540'>system</span> <span
  m='2174940'>function,</span> <span m='2176080'>we</span> <span
  m='2176290'>can</span> <span m='2176450'>see</span> <span
  m='2176990'>that</span> <span m='2177950'>and</span> <span
  m='2178120'>develop</span> <span m='2178580'>it</span> <span
  m='2179800'>in</span> <span m='2179940'>the</span> <span
  m='2180020'>following</span> <span m='2180530'>way.</span> </p><p><span
  m='2182200'>Let's</span> <span m='2182670'>consider</span> <span
  m='2183890'>the</span> <span m='2184270'>continuous</span> <span
  m='2184830'>time</span> <span m='2185070'>system</span> <span
  m='2185460'>function</span> <span m='2186140'>expanded</span> <span
  m='2187000'>in</span> <span m='2187790'>a</span> <span
  m='2187870'>partial</span> <span m='2188270'>fraction</span> <span
  m='2189150'>expansion.</span> <span m='2190250'>And</span> <span
  m='2190440'>just</span> <span m='2190660'>for</span> <span
  m='2190800'>convenience,</span> <span m='2191520'>I'm</span> <span
  m='2191720'>picking</span> <span m='2192040'>first</span> <span
  m='2192400'>order</span> <span m='2192740'>poles--</span> <span
  m='2193320'>this</span> <span m='2193490'>can</span> <span
  m='2193610'>be</span> <span m='2195020'>generalized</span> <span
  m='2201590'>multiple</span> <span m='2202080'>order</span> <span
  m='2202300'>poles,</span> <span m='2203340'>and</span> <span
  m='2204430'>we</span> <span m='2204540'>won't</span> <span
  m='2204760'>do</span> <span m='2204870'>that</span> <span
  m='2205080'>here.</span> <span m='2205730'>The</span> <span
  m='2205820'>same</span> <span m='2206050'>basic</span> <span
  m='2206410'>strategy</span> <span m='2206930'>applies.</span> <span
  m='2208200'>If</span> <span m='2208460'>we</span> <span
  m='2208870'>expand</span> <span m='2209320'>this</span> <span
  m='2209500'>in</span> <span m='2209580'>a</span> <span
  m='2209630'>partial</span> <span m='2210040'>fraction</span> <span
  m='2210520'>expansion,</span> <span m='2212640'>and</span> <span
  m='2213450'>we</span> <span m='2214120'>look</span> <span
  m='2214380'>at</span> <span m='2214460'>the</span> <span
  m='2214560'>impulse</span> <span m='2215010'>response</span> <span
  m='2215440'>associated</span> <span m='2216180'>with</span> <span
  m='2216390'>this--</span> <span m='2216880'>we</span> <span
  m='2217020'>know</span> <span m='2217210'>how</span> <span
  m='2217300'>to</span> <span m='2217420'>take</span> <span
  m='2217670'>the</span> <span m='2217770'>inverse</span> <span
  m='2218110'>of</span> <span m='2218170'>Laplace</span> <span
  m='2218540'>transform</span> <span m='2219160'>of</span> <span
  m='2219270'>this,</span> <span m='2219940'>where</span> <span
  m='2220460'>I'm</span> <span m='2220650'>just</span> <span
  m='2220860'>naturally</span> <span m='2221350'>assuming</span> <span
  m='2221740'>causality</span> <span m='2222940'>throughout</span> <span
  m='2223280'>the</span> <span m='2223360'>discussion--</span> <span
  m='2225490'>the</span> <span m='2225610'>continuous</span> <span
  m='2226140'>time</span> <span m='2226390'>impulse</span> <span
  m='2226810'>response,</span> <span m='2227370'>then,</span> <span
  m='2227780'>is</span> <span m='2228610'>the</span> <span
  m='2228700'>sum</span> <span m='2228980'>of</span> <span
  m='2229070'>exponentials</span> <span m='2230580'>with</span> <span
  m='2231240'>these</span> <span m='2231520'>amplitudes</span> <span
  m='2232790'>and</span> <span m='2233570'>at</span> <span
  m='2233990'>these</span> <span m='2234610'>complex</span> <span
  m='2235090'>exponential</span> <span m='2235680'>frequencies.</span>
  </p><p><span m='2237910'>Now,</span> <span m='2238260'>impulse</span> <span
  m='2238720'>invariance</span> <span m='2239370'>corresponds</span> <span
  m='2240020'>to</span> <span m='2240130'>sampling</span> <span
  m='2240700'>this,</span> <span m='2241570'>and</span> <span
  m='2241950'>so</span> <span m='2242200'>the</span> <span
  m='2242790'>discrete</span> <span m='2243270'>time</span> <span
  m='2243780'>impulse</span> <span m='2244290'>response</span> <span
  m='2245530'>is</span> <span m='2245680'>simply</span> <span
  m='2246040'>a</span> <span m='2246090'>sampled</span> <span
  m='2246520'>version</span> <span m='2246940'>of</span> <span
  m='2247100'>this.</span> <span m='2249700'>The</span> <span
  m='2249910'>A</span> <span m='2250020'>sub</span> <span m='2250230'>k,</span>
  <span m='2250440'>of</span> <span m='2250550'>course,</span> <span
  m='2250900'>carries</span> <span m='2251340'>down.</span> <span
  m='2253720'>We</span> <span m='2253860'>have</span> <span
  m='2254080'>the</span> <span m='2254210'>exponential--</span> <span
  m='2255440'>we're</span> <span m='2255550'>sampling</span> <span
  m='2256380'>at</span> <span m='2256760'>t</span> <span
  m='2256890'>equals</span> <span m='2257240'>n</span> <span
  m='2257430'>capital</span> <span m='2257910'>T,</span> <span
  m='2258320'>and</span> <span m='2258500'>so</span> <span
  m='2259230'>we've</span> <span m='2259340'>replaced</span> <span
  m='2259830'>that</span> <span m='2260030'>here,</span> <span
  m='2260520'>and</span> <span m='2260750'>then</span> <span
  m='2261460'>the</span> <span m='2261560'>unit</span> <span
  m='2261950'>step</span> <span m='2262650'>to</span> <span
  m='2263020'>truncate</span> <span m='2263550'>things</span> <span
  m='2263790'>for</span> <span m='2263900'>negative</span> <span
  m='2264290'>time.</span> </p><p><span m='2266550'>Let's</span> <span
  m='2266740'>manipulate</span> <span m='2267340'>this</span> <span
  m='2268130'>further,</span> <span m='2268760'>and</span> <span
  m='2269370'>eventually</span> <span m='2269850'>what</span> <span
  m='2270030'>we</span> <span m='2270140'>want</span> <span
  m='2270320'>to</span> <span m='2270360'>get</span> <span m='2270810'>is</span>
  <span m='2271620'>a</span> <span m='2271680'>relationship--</span> <span
  m='2272530'>a</span> <span m='2272600'>mapping--</span> <span
  m='2273230'>from</span> <span m='2274040'>the</span> <span
  m='2274200'>continuous</span> <span m='2274810'>time</span> <span
  m='2275080'>to</span> <span m='2275190'>the</span> <span
  m='2275290'>discrete</span> <span m='2275710'>time</span> <span
  m='2276070'>filter.</span> <span m='2278360'>We</span> <span
  m='2278480'>have</span> <span m='2278670'>this</span> <span
  m='2278970'>step,</span> <span m='2279290'>and</span> <span
  m='2279430'>we</span> <span m='2279560'>can</span> <span
  m='2279710'>rewrite</span> <span m='2280190'>that</span> <span
  m='2281630'>now</span> <span m='2282230'>as</span> <span m='2283870'>I</span>
  <span m='2284000'>show</span> <span m='2284380'>here,</span> <span
  m='2284840'>just</span> <span m='2285400'>simply</span> <span
  m='2285760'>taking</span> <span m='2286740'>this</span> <span
  m='2286980'>n</span> <span m='2287680'>outside,</span> <span
  m='2288060'>and</span> <span m='2288440'>we</span> <span
  m='2288560'>have</span> <span m='2288730'>e</span> <span m='2288795'>to</span>
  <span m='2288860'>the</span> <span m='2288925'>s</span> <span
  m='2288990'>sub</span> <span m='2289330'>k</span> <span
  m='2289540'>capital</span> <span m='2290050'>T.</span> <span
  m='2291220'>Now</span> <span m='2291490'>this</span> <span
  m='2291700'>is</span> <span m='2291830'>of</span> <span m='2291930'>the</span>
  <span m='2292020'>form</span> <span m='2293260'>the</span> <span
  m='2293390'>sum</span> <span m='2293670'>of</span> <span
  m='2293770'>terms</span> <span m='2294220'>like</span> <span
  m='2294520'>A</span> <span m='2294710'>sub</span> <span m='2294980'>k</span>
  <span m='2296320'>times</span> <span m='2296690'>is</span> <span
  m='2296930'>beta</span> <span m='2297330'>to</span> <span
  m='2297470'>the</span> <span m='2297660'>n.</span> <span m='2299100'>We</span>
  <span m='2299230'>can</span> <span m='2299410'>compute</span> <span
  m='2299880'>the</span> <span m='2299950'>z-transform</span> <span
  m='2300930'>of</span> <span m='2301040'>this,</span> <span
  m='2302070'>and</span> <span m='2302800'>the</span> <span
  m='2302880'>z-transform</span> <span m='2303750'>that</span> <span
  m='2303880'>we</span> <span m='2304010'>get</span> <span m='2305010'>I</span>
  <span m='2305120'>show</span> <span m='2305960'>here--</span> <span
  m='2306840'>it's</span> <span m='2307050'>simply</span> <span
  m='2307470'>A</span> <span m='2307610'>sub</span> <span m='2307840'>k</span>
  <span m='2308300'>over</span> <span m='2308620'>1</span> <span
  m='2308870'>minus</span> <span m='2309410'>e</span> <span
  m='2309890'>to</span> <span m='2309915'>the</span> <span m='2309940'>s</span>
  <span m='2309965'>sub</span> <span m='2309990'>k</span> <span
  m='2310190'>capital</span> <span m='2310680'>T</span> <span
  m='2311125'>z</span> <span m='2311570'>to</span> <span m='2311640'>the</span>
  <span m='2311720'>minus</span> <span m='2312130'>1,</span> <span
  m='2312750'>simply</span> <span m='2313120'>carrying</span> <span
  m='2314250'>this</span> <span m='2315110'>term</span> <span
  m='2315610'>or</span> <span m='2316240'>this</span> <span
  m='2316700'>parameter</span> <span m='2317570'>down.</span> </p><p><span
  m='2319720'>So</span> <span m='2320290'>we</span> <span
  m='2320410'>started</span> <span m='2320870'>with</span> <span
  m='2321330'>a</span> <span m='2321420'>continuous</span> <span
  m='2322040'>time</span> <span m='2322380'>system</span> <span
  m='2322750'>function,</span> <span m='2323230'>which</span> <span
  m='2323480'>was</span> <span m='2323730'>a</span> <span m='2323790'>sum</span>
  <span m='2323990'>of</span> <span m='2324110'>terms</span> <span
  m='2324700'>like</span> <span m='2325320'>A</span> <span
  m='2325480'>sub</span> <span m='2325710'>k</span> <span
  m='2326190'>over</span> <span m='2326560'>s</span> <span
  m='2326800'>minus</span> <span m='2327120'>s</span> <span
  m='2327400'>sub</span> <span m='2327540'>k--</span> <span
  m='2327790'>the</span> <span m='2327880'>poles</span> <span
  m='2328200'>were</span> <span m='2328330'>at</span> <span m='2328460'>s</span>
  <span m='2328590'>sub</span> <span m='2328710'>k.</span> <span
  m='2329730'>We</span> <span m='2329860'>now</span> <span
  m='2330540'>have</span> <span m='2330760'>the</span> <span
  m='2331290'>discrete</span> <span m='2331690'>time</span> <span
  m='2331930'>filter</span> <span m='2332400'>in</span> <span
  m='2332470'>this</span> <span m='2332710'>form.</span> <span
  m='2334200'>Consequently,</span> <span m='2335160'>then,</span> <span
  m='2335800'>this</span> <span m='2336000'>procedure</span> <span
  m='2336335'>of</span> <span m='2336670'>impulse</span> <span
  m='2337110'>invariance</span> <span m='2338470'>corresponds</span> <span
  m='2340350'>to</span> <span m='2342060'>mapping</span> <span
  m='2342610'>the</span> <span m='2342710'>continuous</span> <span
  m='2343180'>time</span> <span m='2343400'>filter</span> <span
  m='2343780'>to</span> <span m='2343900'>a</span> <span
  m='2343950'>discrete</span> <span m='2344380'>time</span> <span
  m='2344610'>filter</span> <span m='2345690'>by</span> <span
  m='2346320'>mapping</span> <span m='2346810'>the</span> <span
  m='2346900'>poles</span> <span m='2347740'>in</span> <span
  m='2347840'>the</span> <span m='2347920'>continuous</span> <span
  m='2348500'>time</span> <span m='2348770'>filter.</span> <span
  m='2350080'>According</span> <span m='2350680'>to</span> <span
  m='2351560'>this</span> <span m='2351830'>mapping,</span> <span
  m='2354130'>the</span> <span m='2354220'>continuous</span> <span
  m='2354740'>time</span> <span m='2354980'>filter</span> <span
  m='2355320'>pole</span> <span m='2355770'>at</span> <span m='2355870'>s</span>
  <span m='2356080'>sub</span> <span m='2356200'>k</span> <span
  m='2356500'>gets</span> <span m='2356730'>mapped</span> <span
  m='2356990'>to</span> <span m='2357080'>a</span> <span m='2357150'>pole</span>
  <span m='2357580'>e</span> <span m='2357930'>to</span> <span
  m='2358017'>the</span> <span m='2358105'>s</span> <span m='2358192'>sub</span>
  <span m='2358280'>k</span> <span m='2358580'>capital</span> <span
  m='2359090'>T,</span> <span m='2360530'>and</span> <span
  m='2361380'>the</span> <span m='2361520'>coefficients</span> <span
  m='2362990'>A</span> <span m='2363280'>sub</span> <span m='2363400'>k</span>
  <span m='2364350'>are</span> <span m='2365040'>preserved.</span> <span
  m='2367280'>That,</span> <span m='2367540'>then,</span> <span
  m='2367820'>algebraically,</span> <span m='2368890'>is</span> <span
  m='2369720'>what</span> <span m='2369990'>the</span> <span
  m='2370070'>procedure</span> <span m='2370700'>of</span> <span
  m='2370790'>impulse</span> <span m='2371210'>invariance</span> <span
  m='2371750'>corresponds</span> <span m='2372420'>to.</span> </p><p><span
  m='2374960'>Let's</span> <span m='2375980'>look</span> <span
  m='2376260'>at</span> <span m='2377290'>how</span> <span m='2377590'>we</span>
  <span m='2377750'>interpret</span> <span m='2378400'>some</span> <span
  m='2378590'>of</span> <span m='2378720'>this</span> <span
  m='2379100'>in</span> <span m='2379630'>the</span> <span
  m='2379820'>frequency</span> <span m='2380360'>domain.</span> <span
  m='2382180'>In</span> <span m='2382310'>particular,</span> <span
  m='2384910'>we</span> <span m='2385050'>have</span> <span
  m='2386210'>the</span> <span m='2386700'>expression</span> <span
  m='2387630'>that</span> <span m='2388020'>tells</span> <span
  m='2388340'>us</span> <span m='2388530'>how</span> <span
  m='2389020'>the</span> <span m='2389810'>discrete</span> <span
  m='2390290'>time</span> <span m='2391020'>frequency</span> <span
  m='2391620'>response</span> <span m='2393180'>is</span> <span
  m='2393350'>related</span> <span m='2394010'>to</span> <span
  m='2394600'>the</span> <span m='2394700'>continuous</span> <span
  m='2395310'>time</span> <span m='2395940'>frequency</span> <span
  m='2396410'>response.</span> <span m='2397470'>This</span> <span
  m='2397700'>is</span> <span m='2398140'>the</span> <span
  m='2398260'>expression</span> <span m='2398850'>that</span> <span
  m='2399130'>we</span> <span m='2399280'>had</span> <span
  m='2400080'>previously</span> <span m='2401570'>when</span> <span
  m='2402230'>we</span> <span m='2402400'>had</span> <span
  m='2402570'>talked</span> <span m='2402880'>about</span> <span
  m='2403210'>issues</span> <span m='2403580'>of</span> <span
  m='2403660'>sampling.</span> <span m='2405490'>So</span> <span
  m='2405670'>that</span> <span m='2405890'>means</span> <span
  m='2406300'>that</span> <span m='2406600'>we</span> <span
  m='2406770'>would</span> <span m='2406900'>form</span> <span
  m='2407220'>the</span> <span m='2407290'>discrete</span> <span
  m='2407700'>time</span> <span m='2407910'>frequency</span> <span
  m='2408380'>response</span> <span m='2409330'>by</span> <span
  m='2409500'>taking</span> <span m='2409810'>the</span> <span
  m='2409910'>continuous</span> <span m='2410490'>time</span> <span
  m='2410810'>1,</span> <span m='2411760'>scaling</span> <span
  m='2412460'>it</span> <span m='2412890'>in</span> <span
  m='2413030'>frequency</span> <span m='2414430'>according</span> <span
  m='2414840'>to</span> <span m='2414960'>this</span> <span
  m='2415120'>parameter</span> <span m='2415580'>capital</span> <span
  m='2416080'>T,</span> <span m='2416960'>and</span> <span
  m='2417100'>then</span> <span m='2417380'>adding</span> <span
  m='2417810'>replications</span> <span m='2418700'>of</span> <span
  m='2418800'>that</span> <span m='2419290'>together.</span> </p><p><span
  m='2421190'>So</span> <span m='2421780'>if</span> <span
  m='2422050'>this</span> <span m='2422450'>is</span> <span
  m='2422900'>the</span> <span m='2423700'>continuous</span> <span
  m='2424340'>time</span> <span m='2425130'>frequency</span> <span
  m='2425640'>response,</span> <span m='2426540'>just</span> <span
  m='2426890'>simply</span> <span m='2427950'>an</span> <span
  m='2428080'>ideal</span> <span m='2428430'>low-pass</span> <span
  m='2428990'>filter</span> <span m='2429370'>with</span> <span
  m='2429490'>a</span> <span m='2429570'>cutoff</span> <span
  m='2429950'>frequency</span> <span m='2430460'>of</span> <span
  m='2430560'>omega</span> <span m='2430950'>sub</span> <span
  m='2431130'>c,</span> <span m='2432720'>then</span> <span
  m='2433660'>the</span> <span m='2434400'>frequency</span> <span
  m='2434890'>scaling</span> <span m='2435410'>operation</span> <span
  m='2436400'>would</span> <span m='2437250'>keep</span> <span
  m='2437540'>the</span> <span m='2437620'>same</span> <span
  m='2437910'>basic</span> <span m='2438380'>shape</span> <span
  m='2439080'>but</span> <span m='2441200'>linearly</span> <span
  m='2441700'>scale</span> <span m='2442060'>the</span> <span
  m='2442130'>frequency</span> <span m='2442710'>axis</span> <span
  m='2443150'>so</span> <span m='2443290'>that</span> <span
  m='2443500'>we</span> <span m='2443610'>now</span> <span
  m='2443810'>have</span> <span m='2444030'>omega</span> <span
  m='2444400'>sub</span> <span m='2444605'>c</span> <span
  m='2444810'>times</span> <span m='2445600'>T.</span> <span
  m='2447100'>Then</span> <span m='2447600'>the</span> <span
  m='2448160'>discrete</span> <span m='2448690'>time</span> <span
  m='2449430'>frequency</span> <span m='2449970'>response</span> <span
  m='2451610'>would</span> <span m='2451850'>be</span> <span
  m='2452010'>a</span> <span m='2452060'>superposition</span> <span
  m='2452890'>of</span> <span m='2453020'>these</span> <span
  m='2454120'>added</span> <span m='2454570'>together</span> <span
  m='2455250'>at</span> <span m='2455660'>multiples</span> <span
  m='2456480'>of</span> <span m='2456700'>2</span> <span m='2456890'>pi</span>
  <span m='2457400'>in</span> <span m='2457640'>discrete</span> <span
  m='2458060'>time</span> <span m='2458290'>frequency.</span> <span
  m='2460190'>So</span> <span m='2460360'>that's</span> <span
  m='2461080'>what</span> <span m='2461690'>we</span> <span
  m='2462210'>have</span> <span m='2462560'>here--</span> <span
  m='2463350'>so</span> <span m='2463570'>this</span> <span
  m='2463900'>is</span> <span m='2464320'>the</span> <span
  m='2464770'>discrete</span> <span m='2465200'>time</span> <span
  m='2465410'>frequency</span> <span m='2465910'>response.</span> </p><p><span
  m='2468920'>This</span> <span m='2469130'>looks</span> <span
  m='2469320'>very</span> <span m='2469510'>nice--</span> <span
  m='2469850'>it</span> <span m='2469930'>looks</span> <span
  m='2470290'>like</span> <span m='2470650'>impulse</span> <span
  m='2471100'>invariance</span> <span m='2471810'>will</span> <span
  m='2472640'>take</span> <span m='2473020'>the</span> <span
  m='2473240'>continuous</span> <span m='2473730'>time</span> <span
  m='2473960'>frequency</span> <span m='2474450'>response,</span> <span
  m='2475430'>just</span> <span m='2475610'>simply</span> <span
  m='2476040'>linearly</span> <span m='2476490'>scale</span> <span
  m='2476850'>the</span> <span m='2476920'>frequency</span> <span
  m='2477490'>axis,</span> <span m='2478070'>and</span> <span
  m='2478470'>incidentally</span> <span m='2479150'>periodically</span> <span
  m='2479840'>repeat</span> <span m='2479990'>it.</span> <span
  m='2481210'>We</span> <span m='2481360'>know</span> <span
  m='2481720'>that</span> <span m='2482270'>for</span> <span
  m='2483120'>an</span> <span m='2483240'>ideal</span> <span
  m='2483540'>low-pass</span> <span m='2484030'>filter,</span> <span
  m='2484360'>that</span> <span m='2484560'>looks</span> <span
  m='2484800'>just</span> <span m='2485090'>fine.</span> <span
  m='2485670'>In</span> <span m='2485760'>fact,</span> <span
  m='2486750'>for</span> <span m='2486960'>a</span> <span
  m='2487010'>band-limited</span> <span m='2487670'>frequency</span> <span
  m='2488140'>response,</span> <span m='2488940'>that</span> <span
  m='2489100'>looks</span> <span m='2489360'>just</span> <span
  m='2489640'>fine.</span> <span m='2491300'>But</span> <span
  m='2491810'>we</span> <span m='2492040'>know</span> <span
  m='2492215'>also</span> <span m='2492830'>that</span> <span
  m='2493380'>any</span> <span m='2493660'>time</span> <span
  m='2493980'>that</span> <span m='2494080'>we're</span> <span
  m='2494220'>sampling--</span> <span m='2495355'>and</span> <span
  m='2495760'>here</span> <span m='2495980'>we're</span> <span
  m='2496080'>sampling</span> <span m='2496520'>the</span> <span
  m='2496590'>impulse</span> <span m='2497020'>response--</span> <span
  m='2498210'>we</span> <span m='2498440'>have</span> <span
  m='2499710'>an</span> <span m='2499850'>effect</span> <span
  m='2500330'>in</span> <span m='2500420'>the</span> <span
  m='2500500'>frequency</span> <span m='2501010'>domain</span> <span
  m='2501980'>or</span> <span m='2502110'>the</span> <span
  m='2502210'>potential</span> <span m='2502720'>for</span> <span
  m='2502825'>an</span> <span m='2502930'>affect</span> <span
  m='2503210'>an</span> <span m='2503320'>effect</span> <span
  m='2503910'>that</span> <span m='2504440'>we</span> <span
  m='2504570'>refer</span> <span m='2504930'>to</span> <span
  m='2505180'>as</span> <span m='2505340'>aliasing.</span> </p><p><span
  m='2506710'>So</span> <span m='2507000'>in</span> <span
  m='2507080'>fact,</span> <span m='2507690'>if</span> <span
  m='2508160'>instead</span> <span m='2508570'>of</span> <span
  m='2508680'>the</span> <span m='2508830'>ideal</span> <span
  m='2509680'>low-pass</span> <span m='2510260'>filter</span> <span
  m='2511640'>we</span> <span m='2511860'>had</span> <span
  m='2512810'>taken</span> <span m='2513450'>a</span> <span
  m='2513550'>filter</span> <span m='2513990'>that</span> <span
  m='2514140'>was</span> <span m='2514330'>an</span> <span
  m='2514390'>approximation</span> <span m='2515250'>to</span> <span
  m='2515390'>a</span> <span m='2515450'>low-pass</span> <span
  m='2516030'>filter,</span> <span m='2517300'>then</span> <span
  m='2518100'>the</span> <span m='2518780'>corresponding</span> <span
  m='2519630'>frequency</span> <span m='2520180'>scale</span> <span
  m='2520620'>version</span> <span m='2521310'>would</span> <span
  m='2521510'>look</span> <span m='2521740'>as</span> <span
  m='2521890'>I've</span> <span m='2522010'>shown</span> <span
  m='2522380'>here.</span> <span m='2523590'>And</span> <span
  m='2524230'>now</span> <span m='2524720'>as</span> <span m='2525010'>we</span>
  <span m='2525250'>add</span> <span m='2525540'>these</span> <span
  m='2525800'>together,</span> <span m='2527090'>then</span> <span
  m='2527860'>what</span> <span m='2528060'>we</span> <span
  m='2528190'>will</span> <span m='2528390'>have</span> <span
  m='2528910'>is</span> <span m='2529720'>some</span> <span
  m='2529970'>potential</span> <span m='2530810'>for</span> <span
  m='2531040'>distortion</span> <span m='2532190'>corresponding</span> <span
  m='2532940'>to</span> <span m='2533070'>the</span> <span
  m='2533160'>fact</span> <span m='2533760'>that</span> <span
  m='2534190'>these</span> <span m='2534750'>replications</span> <span
  m='2535530'>overlap,</span> <span m='2536620'>and</span> <span
  m='2537310'>what</span> <span m='2537530'>that</span> <span
  m='2537780'>will</span> <span m='2537930'>lead</span> <span
  m='2538230'>to</span> <span m='2538610'>is</span> <span
  m='2539190'>aliasing.</span> </p><p><span m='2542330'>So</span> <span
  m='2542820'>some</span> <span m='2543010'>things</span> <span
  m='2543360'>that</span> <span m='2543650'>we</span> <span
  m='2543820'>can</span> <span m='2543960'>say</span> <span
  m='2544450'>about</span> <span m='2544780'>impulse</span> <span
  m='2545190'>invariance</span> <span m='2546330'>is</span> <span
  m='2546720'>that</span> <span m='2547550'>we</span> <span
  m='2547700'>have</span> <span m='2547950'>an</span> <span
  m='2548040'>algebraic</span> <span m='2548550'>procedure--</span> <span
  m='2549270'>and</span> <span m='2549350'>I'll</span> <span
  m='2549890'>illustrate</span> <span m='2550530'>with</span> <span
  m='2550650'>another</span> <span m='2550900'>example</span> <span
  m='2551350'>shortly--</span> <span m='2552370'>for</span> <span
  m='2552700'>taking</span> <span m='2553070'>a</span> <span
  m='2553170'>continuous</span> <span m='2553740'>time</span> <span
  m='2553940'>system</span> <span m='2554320'>function</span> <span
  m='2554530'>and</span> <span m='2554740'>mapping</span> <span
  m='2555090'>it</span> <span m='2555200'>to</span> <span m='2555310'>a</span>
  <span m='2555370'>discrete</span> <span m='2555780'>time</span> <span
  m='2556160'>system</span> <span m='2556570'>function.</span> <span
  m='2557680'>It</span> <span m='2558140'>has</span> <span m='2558650'>a</span>
  <span m='2558770'>very</span> <span m='2558990'>nice</span> <span
  m='2559280'>property</span> <span m='2559810'>in</span> <span
  m='2559920'>terms</span> <span m='2562580'>of</span> <span
  m='2562750'>mapping,</span> <span m='2563730'>the</span> <span
  m='2563850'>mapping</span> <span m='2564290'>from</span> <span
  m='2565320'>the</span> <span m='2565430'>frequency</span> <span
  m='2565930'>axis</span> <span m='2566700'>in</span> <span
  m='2566890'>continuous</span> <span m='2567410'>time</span> <span
  m='2567710'>due</span> <span m='2568160'>to</span> <span
  m='2568300'>the</span> <span m='2568910'>unit</span> <span
  m='2569220'>circle--</span> <span m='2570190'>namely,</span> <span
  m='2572200'>to</span> <span m='2572350'>a</span> <span
  m='2572410'>first</span> <span m='2572720'>approximation.</span> <span
  m='2573750'>As</span> <span m='2573900'>long</span> <span
  m='2574120'>as</span> <span m='2574220'>there's</span> <span
  m='2574410'>no</span> <span m='2574580'>aliasing,</span> <span
  m='2575720'>the</span> <span m='2575830'>mapping</span> <span
  m='2577090'>is</span> <span m='2577410'>just</span> <span
  m='2577900'>simply</span> <span m='2578440'>a</span> <span
  m='2578530'>linear</span> <span m='2578830'>scaling</span> <span
  m='2579300'>of</span> <span m='2579390'>the</span> <span
  m='2579470'>frequency</span> <span m='2580010'>axis,</span> <span
  m='2580520'>although</span> <span m='2581100'>there</span> <span
  m='2581200'>may</span> <span m='2581400'>be</span> <span
  m='2581560'>some</span> <span m='2581760'>aliasing.</span> <span
  m='2582910'>That</span> <span m='2583120'>means,</span> <span
  m='2583430'>of</span> <span m='2583520'>course,</span> <span
  m='2584070'>that</span> <span m='2584270'>this</span> <span
  m='2584460'>method</span> <span m='2585020'>can</span> <span
  m='2585170'>only</span> <span m='2585450'>be</span> <span
  m='2585600'>used</span> <span m='2586640'>if</span> <span
  m='2587080'>the</span> <span m='2587170'>frequency</span> <span
  m='2587660'>response</span> <span m='2588260'>that's</span> <span
  m='2588460'>being</span> <span m='2588730'>mapped,</span> <span
  m='2589560'>or</span> <span m='2589720'>if</span> <span m='2589765'>the</span>
  <span m='2589810'>system</span> <span m='2590180'>that's</span> <span
  m='2590330'>being</span> <span m='2590570'>mapped,</span> <span
  m='2591640'>has</span> <span m='2591890'>a</span> <span
  m='2591940'>frequency</span> <span m='2592480'>response</span> <span
  m='2593300'>that's</span> <span m='2593900'>approximately</span> <span
  m='2594630'>low-pass--</span> <span m='2595300'>it</span> <span
  m='2595370'>has</span> <span m='2595660'>to</span> <span m='2595770'>be</span>
  <span m='2596010'>approximately</span> <span m='2596680'>band-limited.</span>
  <span m='2600520'>Then</span> <span m='2600870'>what</span> <span
  m='2601020'>we</span> <span m='2601160'>have</span> <span
  m='2601400'>is</span> <span m='2601450'>some</span> <span
  m='2602050'>of</span> <span m='2602110'>potential</span> <span
  m='2602610'>distortion,</span> <span m='2603400'>which</span> <span
  m='2603970'>comes</span> <span m='2604200'>about</span> <span
  m='2604480'>because</span> <span m='2604790'>of</span> <span
  m='2604870'>aliasing.</span> </p><p><span m='2606540'>Also</span> <span
  m='2606910'>because</span> <span m='2607280'>of</span> <span
  m='2607370'>the</span> <span m='2607460'>mapping,</span> <span
  m='2608360'>the</span> <span m='2608460'>fact</span> <span
  m='2608830'>that</span> <span m='2608970'>poles</span> <span
  m='2609370'>at</span> <span m='2609480'>s</span> <span m='2609710'>sub</span>
  <span m='2609830'>k</span> <span m='2610660'>get</span> <span
  m='2610850'>mapped</span> <span m='2611230'>to</span> <span
  m='2611310'>poles</span> <span m='2611810'>at</span> <span
  m='2611970'>e</span> <span m='2612180'>to</span> <span m='2612310'>the</span>
  <span m='2612480'>s</span> <span m='2612650'>sub</span> <span
  m='2612750'>k</span> <span m='2612980'>capital</span> <span
  m='2613480'>T,</span> <span m='2615830'>if</span> <span m='2616150'>the</span>
  <span m='2616290'>analog</span> <span m='2616870'>or</span> <span
  m='2617060'>continuous</span> <span m='2617600'>time</span> <span
  m='2617840'>filter</span> <span m='2618550'>is</span> <span
  m='2619160'>stable--</span> <span m='2619960'>meaning</span> <span
  m='2620270'>that</span> <span m='2620410'>the</span> <span
  m='2620500'>real</span> <span m='2620810'>part</span> <span
  m='2621100'>of</span> <span m='2621190'>s</span> <span m='2621410'>sub</span>
  <span m='2621510'>k</span> <span m='2621700'>is</span> <span
  m='2621870'>negative--</span> <span m='2623050'>then</span> <span
  m='2623880'>the</span> <span m='2624100'>discrete</span> <span
  m='2624560'>time</span> <span m='2624800'>filter</span> <span
  m='2625380'>is</span> <span m='2625540'>guaranteed</span> <span
  m='2626070'>to</span> <span m='2626130'>be</span> <span
  m='2626270'>stable.</span> <span m='2627240'>In</span> <span
  m='2627390'>other</span> <span m='2627570'>words,</span> <span
  m='2628360'>the</span> <span m='2628450'>magnitude</span> <span
  m='2629230'>of</span> <span m='2629350'>z</span> <span m='2629580'>sub</span>
  <span m='2629800'>k</span> <span m='2630350'>will</span> <span
  m='2630540'>be</span> <span m='2630660'>guaranteed</span> <span
  m='2631220'>to</span> <span m='2631280'>be</span> <span
  m='2631420'>less</span> <span m='2631690'>than</span> <span
  m='2631800'>1.</span> <span m='2633060'>I'm</span> <span
  m='2633220'>assuming,</span> <span m='2633620'>of</span> <span
  m='2633710'>course,</span> <span m='2633990'>in</span> <span
  m='2634060'>that</span> <span m='2634240'>discussion</span> <span
  m='2634880'>that</span> <span m='2635480'>we</span> <span
  m='2635920'>are</span> <span m='2636300'>always</span> <span
  m='2637070'>imposing</span> <span m='2637600'>causality</span> <span
  m='2638270'>on</span> <span m='2638360'>the</span> <span
  m='2638420'>systems.</span> </p><p><span m='2641700'>To</span> <span
  m='2641980'>just</span> <span m='2642250'>look</span> <span
  m='2642410'>at</span> <span m='2642490'>the</span> <span
  m='2642620'>algebraic</span> <span m='2643520'>mapping</span> <span
  m='2645570'>a</span> <span m='2645640'>little</span> <span
  m='2645810'>more</span> <span m='2646030'>carefully,</span> <span
  m='2646580'>let's</span> <span m='2646860'>take</span> <span
  m='2647150'>a</span> <span m='2647210'>simple</span> <span
  m='2647600'>example.</span> <span m='2649650'>Here</span> <span
  m='2650160'>is</span> <span m='2650890'>an</span> <span
  m='2651020'>example</span> <span m='2652830'>of</span> <span
  m='2653300'>a</span> <span m='2653410'>system,</span> <span
  m='2654200'>a</span> <span m='2654360'>continuous</span> <span
  m='2654900'>time</span> <span m='2655130'>system,</span> <span
  m='2656150'>where</span> <span m='2656710'>I</span> <span
  m='2656790'>simply</span> <span m='2657240'>have</span> <span
  m='2658190'>a</span> <span m='2658280'>resident</span> <span
  m='2658750'>pole</span> <span m='2659080'>pair</span> <span
  m='2660390'>with</span> <span m='2661640'>an</span> <span
  m='2661690'>imaginary</span> <span m='2662250'>part</span> <span
  m='2662710'>along</span> <span m='2663080'>the</span> <span
  m='2663880'>imaginary</span> <span m='2664320'>axis</span> <span
  m='2664790'>of</span> <span m='2664970'>omega</span> <span
  m='2665260'>sub</span> <span m='2665400'>r</span> <span m='2666000'>and</span>
  <span m='2666270'>a</span> <span m='2666340'>real</span> <span
  m='2666560'>part</span> <span m='2666890'>of</span> <span
  m='2666960'>minus</span> <span m='2667390'>alpha.</span> <span
  m='2668660'>And</span> <span m='2669420'>so</span> <span
  m='2670140'>the</span> <span m='2670260'>associated</span> <span
  m='2670920'>system</span> <span m='2671320'>function</span> <span
  m='2671820'>then</span> <span m='2672750'>is</span> <span
  m='2674200'>just</span> <span m='2674520'>the</span> <span
  m='2674650'>expression</span> <span m='2675650'>which</span> <span
  m='2675970'>incorporates</span> <span m='2677060'>the</span> <span
  m='2677160'>two</span> <span m='2677360'>poles,</span> <span
  m='2678130'>and</span> <span m='2678540'>I've</span> <span
  m='2678600'>put</span> <span m='2678860'>in</span> <span m='2679110'>a</span>
  <span m='2679360'>scale</span> <span m='2679750'>factor</span> <span
  m='2680200'>of</span> <span m='2680310'>2</span> <span
  m='2680420'>omega</span> <span m='2680780'>sub</span> <span
  m='2680930'>r.</span> </p><p><span m='2682850'>And</span> <span
  m='2683010'>now</span> <span m='2683370'>to</span> <span
  m='2683750'>design</span> <span m='2684850'>the</span> <span
  m='2685350'>discrete</span> <span m='2685780'>time</span> <span
  m='2686030'>filter</span> <span m='2686380'>using</span> <span
  m='2686750'>impulse</span> <span m='2687160'>invariance,</span> <span
  m='2688390'>you</span> <span m='2688600'>would</span> <span
  m='2688795'>carry</span> <span m='2688990'>out</span> <span
  m='2689080'>a</span> <span m='2689130'>partial</span> <span
  m='2689540'>fraction</span> <span m='2689990'>expansion</span> <span
  m='2690650'>of</span> <span m='2690750'>this,</span> <span
  m='2691690'>and</span> <span m='2692150'>that</span> <span
  m='2692330'>partial</span> <span m='2692670'>fraction</span> <span
  m='2693080'>expansion</span> <span m='2693620'>is</span> <span
  m='2693690'>shown</span> <span m='2694020'>below.</span> <span
  m='2695990'>We</span> <span m='2696090'>have</span> <span m='2696280'>a</span>
  <span m='2696340'>pole</span> <span m='2696550'>at</span> <span
  m='2696760'>minus</span> <span m='2697140'>alpha</span> <span
  m='2697440'>minus</span> <span m='2697800'>j</span> <span
  m='2697990'>omega</span> <span m='2698370'>r</span> <span
  m='2698850'>and</span> <span m='2698985'>at</span> <span
  m='2699120'>minus</span> <span m='2699550'>alpha</span> <span
  m='2699840'>plus</span> <span m='2700160'>j</span> <span
  m='2700380'>omega</span> <span m='2700770'>r.</span> <span
  m='2702130'>And</span> <span m='2703060'>to</span> <span
  m='2703840'>determine</span> <span m='2704400'>the</span> <span
  m='2705290'>discrete</span> <span m='2705720'>time</span> <span
  m='2705960'>filter</span> <span m='2706530'>based</span> <span
  m='2706880'>on</span> <span m='2707000'>impulse</span> <span
  m='2707430'>invariance,</span> <span m='2708480'>we</span> <span
  m='2708630'>would</span> <span m='2708780'>map</span> <span
  m='2709050'>the</span> <span m='2709150'>poles</span> <span
  m='2709660'>and</span> <span m='2709770'>preserve</span> <span
  m='2710550'>the</span> <span m='2710640'>coefficients</span> <span
  m='2711350'>a</span> <span m='2711470'>sub</span> <span m='2711700'>k,</span>
  <span m='2712460'>referred</span> <span m='2712870'>to</span> <span
  m='2712980'>as</span> <span m='2713090'>the</span> <span
  m='2713170'>residues.</span> <span m='2714480'>And</span> <span
  m='2714670'>so</span> <span m='2715370'>the</span> <span
  m='2716090'>discrete</span> <span m='2716530'>time</span> <span
  m='2716780'>filter</span> <span m='2717560'>that</span> <span
  m='2718040'>we</span> <span m='2718200'>would</span> <span
  m='2718330'>end</span> <span m='2718540'>up</span> <span
  m='2718740'>with</span> <span m='2720560'>as</span> <span m='2721060'>a</span>
  <span m='2721150'>system</span> <span m='2721580'>function,</span> <span
  m='2722380'>which</span> <span m='2723205'>I</span> <span
  m='2723520'>indicate</span> <span m='2724300'>here--</span> <span
  m='2725560'>and</span> <span m='2726390'>we</span> <span
  m='2726870'>have,</span> <span m='2727180'>as</span> <span
  m='2727320'>I</span> <span m='2727710'>said,</span> <span
  m='2728220'>preserved</span> <span m='2728650'>the</span> <span
  m='2728760'>residue,</span> <span m='2729980'>and</span> <span
  m='2730770'>the</span> <span m='2730870'>pole</span> <span
  m='2731370'>is</span> <span m='2731510'>now</span> <span m='2732010'>at</span>
  <span m='2732550'>a</span> <span m='2732576'>to</span> <span
  m='2732603'>the</span> <span m='2732630'>minus</span> <span
  m='2733030'>alpha</span> <span m='2733340'>T,</span> <span
  m='2734240'>e</span> <span m='2734265'>to</span> <span m='2734290'>the</span>
  <span m='2734370'>minus</span> <span m='2734680'>j</span> <span
  m='2734820'>omega</span> <span m='2735090'>sub</span> <span
  m='2735280'>r</span> <span m='2735610'>T.</span> <span
  m='2736930'>That's</span> <span m='2737160'>one</span> <span
  m='2737420'>term,</span> <span m='2738450'>and</span> <span
  m='2738820'>the</span> <span m='2738950'>other</span> <span
  m='2739170'>term</span> <span m='2739880'>in</span> <span
  m='2740020'>the</span> <span m='2740110'>sum</span> <span
  m='2741120'>has</span> <span m='2741640'>a</span> <span
  m='2741740'>pole</span> <span m='2742230'>at</span> <span
  m='2742320'>the</span> <span m='2742400'>complex</span> <span
  m='2742940'>conjugate</span> <span m='2743630'>location.</span> </p><p><span
  m='2744950'>If</span> <span m='2745530'>we</span> <span
  m='2745810'>were</span> <span m='2746040'>to</span> <span
  m='2746220'>add</span> <span m='2746540'>these</span> <span
  m='2746800'>two</span> <span m='2747180'>factors</span> <span
  m='2747760'>together,</span> <span m='2749030'>then</span> <span
  m='2749720'>what</span> <span m='2749940'>we</span> <span
  m='2750090'>would</span> <span m='2750270'>get</span> <span
  m='2750610'>is</span> <span m='2752130'>both</span> <span
  m='2752460'>poles</span> <span m='2753260'>and</span> <span
  m='2753910'>a</span> <span m='2753990'>0</span> <span m='2754660'>at</span>
  <span m='2754830'>the</span> <span m='2754950'>origin.</span> <span
  m='2757420'>In</span> <span m='2757550'>fact,</span> <span
  m='2757940'>then,</span> <span m='2758730'>the</span> <span
  m='2759650'>pole</span> <span m='2760260'>is</span> <span
  m='2760670'>defined</span> <span m='2761230'>by</span> <span
  m='2762350'>its</span> <span m='2762890'>angle,</span> <span
  m='2763650'>and</span> <span m='2764070'>this</span> <span
  m='2764270'>angle</span> <span m='2768150'>is</span> <span
  m='2768650'>e</span> <span m='2768970'>to</span> <span m='2769260'>the</span>
  <span m='2769650'>j</span> <span m='2770670'>omega</span> <span
  m='2771160'>sub</span> <span m='2771330'>r</span> <span
  m='2772000'>capital</span> <span m='2772450'>T,</span> <span
  m='2773700'>and</span> <span m='2774250'>by</span> <span
  m='2774850'>its</span> <span m='2775050'>radius,</span> <span
  m='2776340'>and</span> <span m='2777300'>this</span> <span
  m='2777510'>radius</span> <span m='2778130'>is</span> <span
  m='2778650'>e</span> <span m='2778870'>to</span> <span m='2779010'>the</span>
  <span m='2779100'>minus</span> <span m='2779620'>alpha</span> <span
  m='2780340'>capital</span> <span m='2780790'>T.</span> <span
  m='2784030'>Now</span> <span m='2784690'>we</span> <span
  m='2784840'>can</span> <span m='2785280'>look</span> <span
  m='2785540'>at</span> <span m='2785690'>the</span> <span
  m='2785990'>frequency</span> <span m='2786530'>response</span> <span
  m='2787560'>associated</span> <span m='2788310'>with</span> <span
  m='2788480'>that,</span> <span m='2788740'>and</span> <span
  m='2789920'>let's</span> <span m='2790170'>just</span> <span
  m='2790430'>do</span> <span m='2790610'>that.</span> <span
  m='2791600'>For</span> <span m='2792510'>the</span> <span
  m='2794050'>original</span> <span m='2794800'>continuous</span> <span
  m='2795460'>time</span> <span m='2796290'>frequency</span> <span
  m='2796830'>response,</span> <span m='2799950'>what</span> <span
  m='2800730'>we</span> <span m='2800950'>have</span> <span
  m='2801460'>is</span> <span m='2801630'>simply</span> <span
  m='2802300'>a</span> <span m='2802400'>resonant</span> <span
  m='2802980'>character,</span> <span m='2804160'>as</span> <span
  m='2804380'>I've</span> <span m='2804480'>shown</span> <span
  m='2804810'>here.</span> <span m='2805900'>And</span> <span
  m='2806670'>if</span> <span m='2807120'>we</span> <span m='2808290'>map</span>
  <span m='2808630'>this</span> <span m='2809080'>using</span> <span
  m='2809440'>impulse</span> <span m='2809840'>invariance,</span> <span
  m='2810410'>which</span> <span m='2810630'>we</span> <span
  m='2810730'>just</span> <span m='2811050'>did,</span> <span
  m='2811960'>the</span> <span m='2812520'>resulting</span> <span
  m='2813160'>frequency</span> <span m='2813680'>response</span> <span
  m='2814970'>that</span> <span m='2815140'>we</span> <span
  m='2815270'>get</span> <span m='2816920'>is</span> <span
  m='2817340'>the</span> <span m='2817420'>frequency</span> <span
  m='2817880'>response</span> <span m='2818390'>which</span> <span
  m='2818580'>I</span> <span m='2818670'>indicate.</span> <span
  m='2819670'>We</span> <span m='2819850'>see</span> <span
  m='2820100'>that</span> <span m='2820240'>that's</span> <span
  m='2820700'>basically</span> <span m='2821340'>identical</span> <span
  m='2822740'>to</span> <span m='2823180'>the</span> <span
  m='2823310'>continuous</span> <span m='2823920'>time</span> <span
  m='2824180'>frequency</span> <span m='2824720'>response,</span> <span
  m='2826850'>except</span> <span m='2827350'>for</span> <span
  m='2828510'>a</span> <span m='2828580'>linear</span> <span
  m='2828930'>scaling</span> <span m='2829370'>in</span> <span
  m='2829430'>the</span> <span m='2829500'>frequency</span> <span
  m='2830070'>axis,</span> <span m='2830600'>if</span> <span
  m='2830720'>you</span> <span m='2830850'>just</span> <span
  m='2831090'>compare</span> <span m='2832780'>the</span> <span
  m='2832960'>dimensions</span> <span m='2833510'>along</span> <span
  m='2833750'>which</span> <span m='2833960'>the</span> <span
  m='2834040'>frequency</span> <span m='2834540'>axis</span> <span
  m='2834970'>is</span> <span m='2835060'>shown</span> <span
  m='2838980'>except</span> <span m='2839340'>for</span> <span
  m='2839430'>one</span> <span m='2839700'>minor</span> <span
  m='2841210'>issue,</span> <span m='2842130'>which</span> <span
  m='2843240'>is</span> <span m='2843340'>particularly</span> <span
  m='2843920'>highlighted</span> <span m='2844980'>when</span> <span
  m='2845110'>we</span> <span m='2845240'>look</span> <span
  m='2845440'>at</span> <span m='2845500'>the</span> <span
  m='2845570'>frequency</span> <span m='2846090'>response</span> <span
  m='2846800'>at</span> <span m='2846920'>higher</span> <span
  m='2847250'>frequencies.</span> </p><p><span m='2850180'>What's</span> <span
  m='2850440'>the</span> <span m='2850550'>reason</span> <span
  m='2851380'>why</span> <span m='2852390'>those</span> <span
  m='2852710'>two</span> <span m='2852840'>curves</span> <span
  m='2853970'>don't</span> <span m='2854430'>quite</span> <span
  m='2854780'>follow</span> <span m='2855140'>each</span> <span
  m='2855350'>other</span> <span m='2856100'>at</span> <span
  m='2856220'>higher</span> <span m='2856510'>frequencies?</span> <span
  m='2858980'>Well,</span> <span m='2859390'>the</span> <span
  m='2859540'>reason</span> <span m='2859920'>is</span> <span
  m='2860590'>aliasing.</span> <span m='2861790'>In</span> <span
  m='2861850'>other</span> <span m='2862000'>words,</span> <span
  m='2862260'>what's</span> <span m='2862460'>happened</span> <span
  m='2863040'>is</span> <span m='2863330'>that</span> <span
  m='2864790'>in</span> <span m='2864910'>the</span> <span
  m='2864980'>process</span> <span m='2865720'>so</span> <span
  m='2866450'>applying</span> <span m='2866950'>impulse</span> <span
  m='2867360'>invariance,</span> <span m='2868590'>the</span> <span
  m='2869820'>frequency</span> <span m='2870320'>response</span> <span
  m='2870990'>of</span> <span m='2871130'>the</span> <span
  m='2871240'>original</span> <span m='2871600'>continuous</span> <span
  m='2872150'>time</span> <span m='2872410'>filter</span> <span
  m='2873480'>is</span> <span m='2873770'>approximately</span> <span
  m='2874480'>preserved,</span> <span m='2875720'>except</span> <span
  m='2876180'>for</span> <span m='2876390'>some</span> <span
  m='2876650'>distortion,</span> <span m='2877540'>that</span> <span
  m='2877730'>distortion</span> <span m='2878410'>corresponding</span> <span
  m='2878795'>to</span> <span m='2879180'>aliasing.</span> </p><p><span
  m='2881420'>Well,</span> <span m='2881950'>just</span> <span
  m='2882200'>for</span> <span m='2882500'>comparison,</span> <span
  m='2884200'>let's</span> <span m='2884760'>look</span> <span
  m='2885070'>at</span> <span m='2885270'>what</span> <span
  m='2885660'>would</span> <span m='2886000'>happen</span> <span
  m='2886830'>if</span> <span m='2887100'>we</span> <span
  m='2887230'>took</span> <span m='2887450'>the</span> <span
  m='2887530'>same</span> <span m='2887830'>example--</span> <span
  m='2888490'>and</span> <span m='2888750'>we're</span> <span
  m='2888900'>not</span> <span m='2888960'>going</span> <span
  m='2889045'>to</span> <span m='2889130'>work</span> <span
  m='2889400'>it</span> <span m='2889500'>through</span> <span
  m='2889670'>here</span> <span m='2889910'>carefully.</span> <span
  m='2890710'>We're</span> <span m='2890840'>not</span> <span
  m='2890940'>work</span> <span m='2891070'>it</span> <span
  m='2891200'>through</span> <span m='2891390'>it</span> <span
  m='2891460'>all,</span> <span m='2892490'>not</span> <span
  m='2892650'>even</span> <span m='2892820'>not</span> <span
  m='2893030'>carefully.</span> <span m='2895100'>If</span> <span
  m='2895270'>we</span> <span m='2895370'>took</span> <span
  m='2895580'>the</span> <span m='2895670'>same</span> <span
  m='2895960'>example</span> <span m='2896990'>and</span> <span
  m='2897610'>mapped</span> <span m='2898060'>it</span> <span
  m='2898520'>to</span> <span m='2899000'>a</span> <span
  m='2899160'>discrete</span> <span m='2899560'>time</span> <span
  m='2899790'>filter</span> <span m='2900810'>by</span> <span
  m='2900970'>replacing</span> <span m='2901500'>derivatives</span> <span
  m='2902130'>by</span> <span m='2902260'>backward</span> <span
  m='2902720'>differences,</span> <span m='2904660'>what</span> <span
  m='2904780'>happens</span> <span m='2905170'>in</span> <span
  m='2905250'>that</span> <span m='2905500'>case</span> <span
  m='2906630'>is</span> <span m='2906970'>that</span> <span
  m='2907550'>we</span> <span m='2907690'>get</span> <span m='2908160'>a</span>
  <span m='2908200'>frequency</span> <span m='2908710'>response</span> <span
  m='2910400'>that</span> <span m='2910530'>I</span> <span
  m='2910630'>indicate</span> <span m='2911460'>here.</span> <span
  m='2912030'>Notice</span> <span m='2912920'>that</span> <span
  m='2913480'>the</span> <span m='2913590'>resonance</span> <span
  m='2915200'>in</span> <span m='2915320'>the</span> <span
  m='2915420'>original</span> <span m='2915860'>continuous</span> <span
  m='2916460'>time</span> <span m='2916720'>filter</span> <span
  m='2917720'>is</span> <span m='2918550'>totally</span> <span
  m='2919010'>lost.</span> <span m='2921020'>In</span> <span
  m='2921160'>fact,</span> <span m='2922110'>basically</span> <span
  m='2922600'>the</span> <span m='2922710'>character</span> <span
  m='2923760'>of</span> <span m='2924340'>the</span> <span
  m='2924440'>continuous</span> <span m='2924950'>time</span> <span
  m='2925190'>frequency</span> <span m='2925660'>response</span> <span
  m='2925980'>is</span> <span m='2926300'>lost.</span> </p><p><span
  m='2927510'>What's</span> <span m='2927770'>the</span> <span
  m='2927870'>reason?</span> <span m='2928410'>Well,</span> <span
  m='2928670'>the</span> <span m='2928750'>reason</span> <span
  m='2929060'>goes</span> <span m='2929310'>back</span> <span
  m='2929620'>to</span> <span m='2929730'>the</span> <span
  m='2929920'>picture</span> <span m='2930270'>that</span> <span
  m='2930420'>I</span> <span m='2930490'>drew</span> <span
  m='2930710'>before.</span> <span m='2931810'>The</span> <span
  m='2931910'>continuous</span> <span m='2932480'>time</span> <span
  m='2933370'>filter</span> <span m='2934490'>had</span> <span
  m='2935000'>a</span> <span m='2935300'>pair</span> <span m='2935790'>of</span>
  <span m='2937520'>resident</span> <span m='2938060'>poles</span> <span
  m='2938620'>close</span> <span m='2938920'>to</span> <span
  m='2939010'>the</span> <span m='2939100'>j</span> <span
  m='2939390'>omega</span> <span m='2939590'>axis.</span> <span
  m='2940830'>When</span> <span m='2940960'>those</span> <span
  m='2941220'>get</span> <span m='2941410'>mapped</span> <span
  m='2941740'>using</span> <span m='2942050'>backward</span> <span
  m='2942490'>differences,</span> <span m='2943490'>they</span> <span
  m='2943640'>end</span> <span m='2943850'>up</span> <span
  m='2943990'>close</span> <span m='2944320'>to</span> <span
  m='2944420'>this</span> <span m='2944620'>little</span> <span
  m='2944850'>circle</span> <span m='2945390'>that's</span> <span
  m='2945600'>inside</span> <span m='2946030'>the</span> <span
  m='2946100'>unit</span> <span m='2946430'>circle,</span> <span
  m='2947850'>but</span> <span m='2948120'>in</span> <span
  m='2948240'>fact</span> <span m='2949020'>for</span> <span
  m='2949120'>this</span> <span m='2949320'>example,</span> <span
  m='2949980'>are</span> <span m='2950110'>far</span> <span
  m='2950450'>away</span> <span m='2950700'>from</span> <span
  m='2950870'>the</span> <span m='2950960'>unit</span> <span
  m='2951240'>circle.</span> </p><p><span m='2956350'>So</span> <span
  m='2956620'>far</span> <span m='2956960'>we</span> <span
  m='2957100'>have</span> <span m='2958160'>one</span> <span
  m='2958760'>useful</span> <span m='2959230'>technique</span> <span
  m='2959730'>for</span> <span m='2959870'>mapping</span> <span
  m='2960320'>continuous</span> <span m='2960870'>time</span> <span
  m='2961090'>filters</span> <span m='2961540'>to</span> <span
  m='2961660'>discrete</span> <span m='2962070'>time</span> <span
  m='2962300'>filters.</span> <span m='2963600'>In</span> <span
  m='2963680'>part</span> <span m='2964330'>to</span> <span
  m='2964860'>highlight</span> <span m='2965350'>some</span> <span
  m='2965480'>of</span> <span m='2965620'>the</span> <span
  m='2965750'>issues,</span> <span m='2966330'>I</span> <span
  m='2966660'>focused</span> <span m='2967160'>attention</span> <span
  m='2967600'>also</span> <span m='2968210'>on</span> <span
  m='2969190'>some</span> <span m='2969390'>not</span> <span
  m='2969650'>so</span> <span m='2969760'>useful</span> <span
  m='2970190'>methods--</span> <span m='2971780'>namely,</span> <span
  m='2972340'>mapping</span> <span m='2973300'>derivatives</span> <span
  m='2974290'>to</span> <span m='2974520'>forward</span> <span
  m='2974920'>or</span> <span m='2974970'>backward</span> <span
  m='2975410'>differences.</span> <span m='2977630'>Next</span> <span
  m='2977900'>time</span> <span m='2978610'>what</span> <span
  m='2979120'>I</span> <span m='2979730'>would</span> <span
  m='2980460'>like</span> <span m='2980710'>to</span> <span
  m='2980830'>do</span> <span m='2981240'>is</span> <span
  m='2982420'>look</span> <span m='2982730'>at</span> <span
  m='2982920'>impulse</span> <span m='2983360'>invariance</span> <span
  m='2984450'>for</span> <span m='2984600'>another</span> <span
  m='2984930'>example--</span> <span m='2986470'>namely,</span> <span
  m='2987370'>the</span> <span m='2987480'>design</span> <span
  m='2988200'>of</span> <span m='2989040'>a</span> <span
  m='2989250'>Butterworth</span> <span m='2989820'>filter,</span> <span
  m='2990300'>and</span> <span m='2990380'>I'll</span> <span
  m='2991360'>talk</span> <span m='2991640'>more</span> <span
  m='2991790'>specifically</span> <span m='2992440'>about</span> <span
  m='2992700'>what</span> <span m='2992880'>Butterworth</span> <span
  m='2993660'>filters</span> <span m='2994120'>are</span> <span
  m='2994970'>at</span> <span m='2995130'>the</span> <span
  m='2995200'>beginning</span> <span m='2995530'>of</span> <span
  m='2995580'>that</span> <span m='2995770'>lecture.</span> </p><p><span
  m='2997550'>Then,</span> <span m='2997900'>in</span> <span
  m='2998060'>addition,</span> <span m='2998780'>what</span> <span
  m='2999000'>we'll</span> <span m='2999200'>introduce</span> <span
  m='2999860'>is</span> <span m='3000030'>another</span> <span
  m='3000910'>very</span> <span m='3001170'>useful</span> <span
  m='3001630'>technique,</span> <span m='3002970'>which</span> <span
  m='3003560'>has</span> <span m='3004230'>some</span> <span
  m='3004440'>difficulties</span> <span m='3005340'>which</span> <span
  m='3005600'>impulse</span> <span m='3006010'>invariance</span> <span
  m='3006550'>doesn't</span> <span m='3006860'>have,</span> <span
  m='3007720'>but</span> <span m='3008130'>avoids</span> <span
  m='3009690'>the</span> <span m='3009800'>principal</span> <span
  m='3011360'>difficulty</span> <span m='3011990'>that</span> <span
  m='3012110'>impulse</span> <span m='3012540'>invariance</span> <span
  m='3013030'>does</span> <span m='3013240'>have--</span> <span
  m='3013480'>namely,</span> <span m='3013870'>aliasing.</span> <span
  m='3014950'>That</span> <span m='3015190'>method</span> <span
  m='3015730'>is</span> <span m='3015950'>referred</span> <span
  m='3016360'>to</span> <span m='3017360'>the</span> <span
  m='3017450'>bilinear</span> <span m='3017950'>transformation,</span> <span
  m='3019360'>which</span> <span m='3019880'>we</span> <span
  m='3020310'>will</span> <span m='3021020'>define</span> <span
  m='3021730'>and</span> <span m='3022640'>utilize</span> <span
  m='3023210'>next</span> <span m='3023440'>time.</span> <span
  m='3024090'>Thank</span> <span m='3024300'>you.</span> </p>
embedded_media:
  - uid: 121f43730a980f57669ab32be3f88ec7
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: z8sXXQxcmN4
  - uid: ae2702dc100a9fcb28a08cb1f175ce5b
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/z8sXXQxcmN4/default.jpg'
  - uid: b1058c9ffef52e99c9c74c5d56a5019e
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/podcast/lecture-23-mapping-continuous/id458320213?i=96641904
  - uid: ff3af3b476086637a3139b99dd462987
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: >-
      http://www.archive.org/download/MITRES.6.007S11/MITRES_6-007S11lec23_300k.mp4
  - uid: 7247d3ddec258fb20a5be9203c106f01
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: MITRES_6_007S11_lec23.pdf
    title: MITRES_6_007S11_lec23.pdf
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-23-mapping-continuous-time-filters-to-discrete-time-filters/MITRES_6_007S11_lec23.pdf
  - uid: bd4719059095f4d8764835a61f48d5f8
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: z8sXXQxcmN4
  - uid: 0cae4a79e7638268055db1a947a36877
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: z8sXXQxcmN4.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-23-mapping-continuous-time-filters-to-discrete-time-filters/z8sXXQxcmN4.srt
  - uid: 13da5d1caacaa4792032e0b6c7b4eb4d
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: z8sXXQxcmN4.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-23-mapping-continuous-time-filters-to-discrete-time-filters/z8sXXQxcmN4.pdf
  - uid: 8ca35ac2caad1a1828f87fb79cea7459
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 5da364af0c28dd818672a2ba07980aeb
    parent_uid: 08a3ee1bbf42fab54283c5b2ec68e4f5
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-007-signals-and-systems-spring-2011
type: course
layout: video
---