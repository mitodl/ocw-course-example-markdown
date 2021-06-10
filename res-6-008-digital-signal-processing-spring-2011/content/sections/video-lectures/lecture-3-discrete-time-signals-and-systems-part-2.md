---
order_index: null
title: 'Lecture 3: Discrete-Time Signals and Systems, Part 2'
template_type: Tabbed
uid: cbee2b0b473165c25cd6f7c8919f35eb
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-3-discrete-time-signals-and-systems-part-2
short_url: lecture-3-discrete-time-signals-and-systems-part-2
inline_embed_id: '29501923lecture3:discrete-timesignalsandsystems,part272199250'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Stability and causality for discrete-time
  systems, systems described by linear constant-coefficient difference
  equations, frequency response of linear time-invariant systems.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Discrete-Time Signals and Systems, Part 2 (<a
  href="./resolveuid/b80e11f814bd32be987a6264e605b5f8">PDF</a>)</p>
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
  m='24416'>[MUSIC PLAYING]</span> </p><p></p><p><span m='52512'>ALAN V.
  OPPENHEIM:</span> <span m='52990'>In</span> <span m='53100'>the</span> <span
  m='53210'>last</span> <span m='53570'>lecture,</span> <span
  m='54630'>we</span> <span m='55130'>introduced</span> <span
  m='55700'>the</span> <span m='55910'>class</span> <span m='56510'>of</span>
  <span m='57050'>discrete</span> <span m='57440'>time</span> <span
  m='58220'>systems,</span> <span m='59600'>and</span> <span m='59930'>in</span>
  <span m='59990'>particular,</span> <span m='61250'>imposed</span> <span
  m='61790'>the</span> <span m='61910'>conditions</span> <span
  m='62450'>of</span> <span m='63050'>linearity</span> <span
  m='63650'>first</span> <span m='63980'>of</span> <span m='64099'>all,</span>
  <span m='64580'>and</span> <span m='65630'>second,</span> <span
  m='66440'>the</span> <span m='66650'>property</span> <span m='67340'>or</span>
  <span m='67520'>constraint</span> <span m='68000'>of</span> <span
  m='68090'>shift</span> <span m='68360'>invariance.</span> <span
  m='70880'>And</span> <span m='72110'>those</span> <span
  m='72350'>constraints</span> <span m='72920'>led</span> <span
  m='73160'>us</span> <span m='73460'>to</span> <span m='73730'>the</span> <span
  m='73850'>convolution</span> <span m='74510'>sum</span> <span
  m='74810'>representation.</span> </p><p><span m='76880'>In</span> <span
  m='76970'>today's</span> <span m='77330'>lecture,</span> <span
  m='78050'>there</span> <span m='78590'>are</span> <span
  m='79100'>several</span> <span m='80090'>issues</span> <span
  m='80420'>that</span> <span m='80570'>I'd</span> <span m='80690'>like</span>
  <span m='80870'>to</span> <span m='80960'>focus</span> <span
  m='81440'>on.</span> <span m='82470'>The</span> <span m='82570'>first</span>
  <span m='82970'>is</span> <span m='83750'>the</span> <span
  m='86450'>introduction</span> <span m='87260'>of</span> <span
  m='87800'>two</span> <span m='88010'>additional</span> <span
  m='88670'>constraints</span> <span m='89660'>that</span> <span
  m='89990'>it's</span> <span m='90140'>sometimes</span> <span
  m='91070'>useful</span> <span m='91670'>to</span> <span
  m='92120'>impose,</span> <span m='92630'>or</span> <span m='92720'>at</span>
  <span m='92780'>least</span> <span m='92990'>consider,</span> <span
  m='93530'>for</span> <span m='93710'>discrete</span> <span
  m='94100'>time</span> <span m='94400'>systems--</span> <span
  m='95450'>namely</span> <span m='96020'>the</span> <span
  m='96350'>constraints</span> <span m='96920'>or</span> <span
  m='97010'>conditions</span> <span m='97820'>of</span> <span
  m='98360'>causality</span> <span m='99320'>and</span> <span
  m='99500'>stability.</span> </p><p><span m='101630'>Second</span> <span
  m='102020'>of</span> <span m='102140'>all,</span> <span m='102660'>I</span>
  <span m='103340'>would</span> <span m='103490'>like</span> <span
  m='103700'>to</span> <span m='103820'>talk</span> <span
  m='104180'>about</span> <span m='104690'>a</span> <span
  m='105350'>particular</span> <span m='105890'>class,</span> <span
  m='106770'>or</span> <span m='106870'>at</span> <span m='106970'>least</span>
  <span m='107000'>introduce</span> <span m='107600'>a</span> <span
  m='107660'>particular</span> <span m='108170'>class</span> <span
  m='108680'>of</span> <span m='109160'>linear</span> <span
  m='109520'>shift</span> <span m='109820'>invariant</span> <span
  m='110330'>systems,</span> <span m='111440'>namely</span> <span
  m='111800'>those</span> <span m='112220'>representable</span> <span
  m='112970'>by</span> <span m='113150'>linear</span> <span
  m='113480'>constant</span> <span m='113930'>coefficient</span> <span
  m='114560'>difference</span> <span m='114920'>equations.</span> <span
  m='116280'>And</span> <span m='116300'>finally,</span> <span
  m='117120'>I'd</span> <span m='117560'>like</span> <span m='118010'>to</span>
  <span m='119000'>introduce</span> <span m='119990'>a</span> <span
  m='121400'>representation</span> <span m='122600'>of</span> <span
  m='122990'>linear</span> <span m='123380'>shift</span> <span
  m='123650'>invariant</span> <span m='124190'>systems</span> <span
  m='125180'>that</span> <span m='125480'>is</span> <span m='125810'>an</span>
  <span m='125900'>alternative</span> <span m='126680'>to</span> <span
  m='126890'>the</span> <span m='127070'>convolution</span> <span
  m='127770'>sum</span> <span m='128060'>representation,</span> <span
  m='129380'>and</span> <span m='129470'>in</span> <span
  m='129560'>particular,</span> <span m='130160'>that</span> <span
  m='130370'>representation</span> <span m='131270'>corresponds</span> <span
  m='132200'>to</span> <span m='132980'>the</span> <span
  m='133370'>representation</span> <span m='134300'>in</span> <span
  m='134390'>terms</span> <span m='134720'>of</span> <span m='134810'>a</span>
  <span m='134870'>frequency</span> <span m='135380'>response.</span>
  </p><p><span m='137210'>Well,</span> <span m='137840'>let's</span> <span
  m='138320'>begin</span> <span m='138980'>with</span> <span
  m='139520'>the</span> <span m='139820'>notions</span> <span
  m='140630'>of</span> <span m='141380'>stability</span> <span
  m='141980'>and</span> <span m='142100'>causality,</span> <span
  m='143570'>reminding</span> <span m='144080'>you,</span> <span
  m='144440'>first</span> <span m='144800'>of</span> <span
  m='144920'>all,</span> <span m='145280'>that,</span> <span
  m='145610'>as</span> <span m='146150'>we</span> <span m='146330'>talked</span>
  <span m='146660'>about</span> <span m='146930'>last</span> <span
  m='147290'>time,</span> <span m='148370'>we</span> <span m='149090'>can</span>
  <span m='149300'>consider</span> <span m='149780'>a</span> <span
  m='149840'>general</span> <span m='150290'>system--</span> <span
  m='151610'>inputs</span> <span m='152630'>and</span> <span
  m='152750'>outputs</span> <span m='153230'>are</span> <span
  m='153320'>sequences--</span> <span m='154640'>and</span> <span
  m='154880'>in</span> <span m='155000'>general,</span> <span
  m='155570'>the</span> <span m='155720'>system</span> <span
  m='156170'>just</span> <span m='156380'>simply</span> <span
  m='157040'>corresponds</span> <span m='157820'>to</span> <span
  m='157940'>some</span> <span m='158270'>transformation</span> <span
  m='159620'>from</span> <span m='159800'>the</span> <span
  m='159920'>input</span> <span m='160250'>sequence</span> <span
  m='160730'>to</span> <span m='160820'>the</span> <span
  m='160970'>output</span> <span m='161360'>sequence.</span> </p><p><span
  m='163310'>When</span> <span m='163520'>we</span> <span
  m='163640'>impose</span> <span m='164060'>the</span> <span
  m='164180'>conditions</span> <span m='164990'>of</span> <span
  m='165170'>linearity</span> <span m='165950'>and</span> <span
  m='166070'>shift</span> <span m='166450'>invariance,</span> <span
  m='167390'>both</span> <span m='167630'>conditions,</span> <span
  m='169020'>then</span> <span m='169520'>we</span> <span m='169820'>can</span>
  <span m='170330'>express</span> <span m='171290'>the</span> <span
  m='171710'>output</span> <span m='172220'>sequence</span> <span
  m='173780'>in</span> <span m='174500'>this</span> <span m='174800'>form</span>
  <span m='175820'>where</span> <span m='176390'>h of n</span> <span
  m='177260'>is</span> <span m='177890'>the</span> <span
  m='177980'>response</span> <span m='178580'>of</span> <span
  m='178670'>the</span> <span m='178760'>system</span> <span
  m='179240'>to</span> <span m='179420'>a</span> <span m='179480'>unit</span>
  <span m='179780'>sample.</span> <span m='181070'>And</span> <span
  m='182390'>this</span> <span m='182840'>can</span> <span
  m='183050'>also</span> <span m='183650'>be</span> <span
  m='183860'>rearranged</span> <span m='185060'>in</span> <span
  m='185540'>the</span> <span m='185660'>form</span> <span
  m='185930'>that</span> <span m='186050'>I've</span> <span
  m='186200'>indicated</span> <span m='186770'>here,</span> <span
  m='187550'>essentially</span> <span m='188180'>interchanging</span> <span
  m='188900'>the</span> <span m='188990'>role</span> <span m='189500'>of</span>
  <span m='190100'>the</span> <span m='190190'>unit</span> <span
  m='190490'>sample</span> <span m='190880'>response</span> <span
  m='191450'>and</span> <span m='191540'>the</span> <span
  m='191660'>input.</span> <span m='192620'>The</span> <span
  m='193490'>sum</span> <span m='194000'>expressed</span> <span
  m='194570'>in</span> <span m='194670'>either</span> <span m='194960'>of</span>
  <span m='195080'>these</span> <span m='195290'>two</span> <span
  m='195500'>forms,</span> <span m='196430'>we</span> <span
  m='196550'>referred</span> <span m='196940'>to</span> <span
  m='197540'>last</span> <span m='197900'>time</span> <span m='198350'>as</span>
  <span m='198500'>the</span> <span m='198590'>convolution</span> <span
  m='199280'>sum.</span> </p><p><span m='200360'>So</span> <span
  m='201110'>the</span> <span m='201200'>convolution</span> <span
  m='201800'>sum</span> <span m='202460'>comes</span> <span
  m='202760'>out</span> <span m='202970'>of--</span> <span m='204080'>or</span>
  <span m='204230'>is</span> <span m='204320'>a</span> <span
  m='204380'>consequence</span> <span m='205220'>of--</span> <span
  m='205910'>linearity</span> <span m='206810'>and</span> <span
  m='207200'>shift</span> <span m='207530'>invariance.</span> </p><p><span
  m='210210'>Two</span> <span m='210560'>additional</span> <span
  m='211160'>conditions</span> <span m='212120'>are</span> <span
  m='212480'>stability</span> <span m='213230'>and</span> <span
  m='213320'>causality.</span> <span m='215060'>Stability</span> <span
  m='216020'>of</span> <span m='216170'>a</span> <span m='216230'>system,</span>
  <span m='217730'>in</span> <span m='217910'>general,</span> <span
  m='219290'>corresponds</span> <span m='220370'>to</span> <span
  m='221300'>the</span> <span m='221390'>statement</span> <span
  m='222680'>that</span> <span m='223640'>if</span> <span m='224180'>the</span>
  <span m='224390'>input</span> <span m='225050'>sequence</span> <span
  m='226070'>is</span> <span m='226250'>bounded--</span> <span
  m='227780'>in</span> <span m='227870'>other</span> <span
  m='228080'>words,</span> <span m='228780'>if</span> <span m='229340'>x</span>
  <span m='229670'>of</span> <span m='229790'>n,</span> <span
  m='230480'>essentially</span> <span m='230960'>if x</span> <span
  m='231320'>of</span> <span m='231440'>n</span> <span m='231800'>is</span>
  <span m='232550'>finite</span> <span m='233420'>for</span> <span
  m='233660'>all</span> <span m='234020'>n,</span> <span
  m='234410'>including</span> <span m='235070'>as</span> <span
  m='235220'>n</span> <span m='235370'>goes</span> <span m='235640'>to</span>
  <span m='235760'>infinity,</span> <span m='237290'>then</span> <span
  m='237830'>a</span> <span m='237890'>system</span> <span m='238520'>is</span>
  <span m='238670'>said</span> <span m='238880'>to</span> <span
  m='239000'>be</span> <span m='239120'>stable</span> <span m='240260'>if</span>
  <span m='240920'>the</span> <span m='241430'>output</span> <span
  m='242210'>sequence,</span> <span m='242810'>y</span> <span
  m='243110'>of</span> <span m='243220'>n,</span> <span m='243950'>is</span>
  <span m='244370'>also</span> <span m='245090'>bounded.</span> <span
  m='246170'>In</span> <span m='246290'>other</span> <span
  m='246500'>words,</span> <span m='247440'>the</span> <span
  m='247790'>magnitude</span> <span m='248360'>of</span> <span
  m='248450'>y</span> <span m='248720'>of</span> <span m='248840'>n</span> <span
  m='249170'>is</span> <span m='249650'>finite</span> <span
  m='250340'>for</span> <span m='250550'>all</span> <span m='250840'>n.</span>
  </p><p><span m='251900'>If</span> <span m='252080'>that's</span> <span
  m='252350'>true</span> <span m='253130'>for</span> <span m='253400'>any</span>
  <span m='253640'>bounded</span> <span m='254660'>input</span> <span
  m='255080'>sequence</span> <span m='255590'>that</span> <span
  m='255710'>the</span> <span m='255830'>output</span> <span
  m='256190'>sequence</span> <span m='256640'>is</span> <span
  m='256790'>bounded,</span> <span m='257570'>the</span> <span
  m='257690'>system</span> <span m='258079'>is</span> <span
  m='258140'>said</span> <span m='258350'>to</span> <span m='258500'>be</span>
  <span m='258620'>stable.</span> <span m='260420'>Now,</span> <span
  m='260690'>that's</span> <span m='260959'>a</span> <span
  m='261019'>statement</span> <span m='261950'>that</span> <span
  m='262040'>applies</span> <span m='262460'>to</span> <span
  m='262580'>general</span> <span m='263000'>discrete</span> <span
  m='263360'>time</span> <span m='263690'>systems.</span> <span
  m='264920'>For</span> <span m='265370'>the</span> <span
  m='265520'>specific</span> <span m='266060'>class</span> <span
  m='266750'>of</span> <span m='266870'>systems</span> <span
  m='267350'>that</span> <span m='267500'>we'll</span> <span
  m='267650'>be</span> <span m='267800'>dealing</span> <span
  m='268220'>with</span> <span m='268670'>in</span> <span m='269150'>this</span>
  <span m='269300'>set</span> <span m='269540'>of</span> <span
  m='269660'>lessons,</span> <span m='270200'>namely</span> <span
  m='271160'>the</span> <span m='271250'>class</span> <span m='271610'>of</span>
  <span m='271700'>linear</span> <span m='272000'>shift</span> <span
  m='272330'>invariant</span> <span m='272870'>systems,</span> <span
  m='274070'>you</span> <span m='274220'>can</span> <span m='274370'>show</span>
  <span m='275090'>that</span> <span m='275840'>an</span> <span
  m='276620'>equivalent</span> <span m='277130'>statement</span> <span
  m='277790'>of</span> <span m='277880'>stability--</span> <span
  m='278600'>or</span> <span m='280460'>a</span> <span
  m='280640'>necessary</span> <span m='281750'>and</span> <span
  m='281870'>sufficient</span> <span m='282350'>condition</span> <span
  m='282830'>for</span> <span m='282980'>this</span> <span m='283160'>to</span>
  <span m='283310'>be</span> <span m='283460'>true--</span> <span
  m='284450'>is</span> <span m='284570'>simply</span> <span
  m='285410'>that</span> <span m='286070'>the</span> <span
  m='286190'>unit</span> <span m='286490'>sample</span> <span
  m='286940'>response</span> <span m='287630'>of</span> <span
  m='287780'>the</span> <span m='287870'>system</span> <span
  m='288830'>be</span> <span m='289220'>absolutely</span> <span
  m='289850'>summable.</span> <span m='290990'>In</span> <span
  m='291110'>other</span> <span m='291290'>words,</span> <span
  m='291830'>that</span> <span m='292340'>the</span> <span m='292460'>sum</span>
  <span m='292700'>of</span> <span m='292790'>the</span> <span
  m='292850'>magnitudes</span> <span m='293690'>of</span> <span
  m='293990'>the</span> <span m='294080'>values</span> <span
  m='294710'>in</span> <span m='294800'>the</span> <span m='294890'>unit</span>
  <span m='295130'>sample</span> <span m='295520'>response</span> <span
  m='296510'>are</span> <span m='296610'>finite.</span> </p><p><span
  m='298620'>For</span> <span m='298770'>example,</span> <span
  m='299620'>if</span> <span m='299760'>we</span> <span m='299880'>had</span>
  <span m='300060'>a</span> <span m='300120'>unit</span> <span
  m='300390'>sample</span> <span m='300810'>response</span> <span
  m='302010'>which</span> <span m='302280'>was</span> <span m='302850'>2</span>
  <span m='303110'>to</span> <span m='303300'>the</span> <span
  m='303480'>n</span> <span m='303960'>times</span> <span m='304290'>a</span>
  <span m='304350'>unit</span> <span m='304650'>step,</span> <span
  m='306200'>2</span> <span m='306390'>to</span> <span m='306480'>the</span>
  <span m='306690'>n,</span> <span m='306810'>of</span> <span
  m='306900'>course,</span> <span m='307410'>as</span> <span m='307770'>n</span>
  <span m='308200'>increases--</span> <span m='309780'>as</span> <span
  m='309930'>n</span> <span m='310470'>goes</span> <span m='310740'>from</span>
  <span m='310890'>0</span> <span m='311190'>to</span> <span
  m='311340'>infinity--</span> <span m='312500'>2</span> <span
  m='312870'>the</span> <span m='313050'>n</span> <span m='313560'>grows</span>
  <span m='314220'>exponentially,</span> <span m='315060'>in</span> <span
  m='315150'>fact.</span> <span m='316020'>And</span> <span
  m='316170'>so,</span> <span m='316590'>obviously,</span> <span
  m='317670'>this</span> <span m='317880'>is</span> <span m='318000'>not</span>
  <span m='318240'>absolutely</span> <span m='318810'>summable.</span> <span
  m='320430'>So</span> <span m='321390'>this</span> <span m='321600'>is</span>
  <span m='321750'>an</span> <span m='321840'>example</span> <span
  m='322740'>of</span> <span m='323730'>a</span> <span m='323790'>system</span>
  <span m='324660'>that</span> <span m='324840'>would</span> <span
  m='325020'>be</span> <span m='325620'>unstable.</span> </p><p><span
  m='329310'>Whereas,</span> <span m='330090'>if</span> <span m='330730'>h
  of</span> <span m='330990'>n</span> <span m='331440'>were</span> <span
  m='331820'>a</span> <span m='331890'>1/2</span> <span m='332250'>to</span>
  <span m='332400'>the</span> <span m='332550'>n</span> <span
  m='332730'>times</span> <span m='333060'>u of</span> <span
  m='333240'>n,</span> <span m='334110'>so</span> <span m='334320'>that</span>
  <span m='334770'>for</span> <span m='335190'>n</span> <span
  m='335430'>greater</span> <span m='335790'>than</span> <span
  m='335970'>0--</span> <span m='336570'>and</span> <span m='336660'>less</span>
  <span m='336830'>than</span> <span m='336950'>0,</span> <span
  m='337140'>of</span> <span m='337230'>course,</span> <span
  m='337570'>both</span> <span m='337740'>of</span> <span
  m='337800'>these</span> <span m='338010'>are</span> <span
  m='338100'>0--</span> <span m='338970'>for</span> <span m='339120'>n</span>
  <span m='339240'>greater</span> <span m='339600'>than</span> <span
  m='339810'>0,</span> <span m='340280'>this</span> <span m='340470'>were</span>
  <span m='340590'>decaying</span> <span m='341190'>exponentially,</span> <span
  m='342600'>if</span> <span m='342990'>you</span> <span m='343140'>sum</span>
  <span m='343470'>up</span> <span m='344040'>these</span> <span
  m='344250'>values</span> <span m='344790'>from</span> <span
  m='344940'>0</span> <span m='345300'>to</span> <span
  m='345450'>infinity,</span> <span m='346260'>it</span> <span
  m='346410'>converges</span> <span m='346920'>to</span> <span
  m='347070'>a</span> <span m='347130'>finite</span> <span
  m='347580'>number.</span> <span m='348610'>So</span> <span
  m='348720'>that</span> <span m='349140'>this,</span> <span
  m='349410'>in</span> <span m='349530'>fact,</span> <span
  m='350460'>would</span> <span m='350610'>correspond</span> <span
  m='351480'>to</span> <span m='352770'>a</span> <span m='352830'>stable</span>
  <span m='353250'>system.</span> </p><p><span m='355170'>Now,</span> <span
  m='355380'>we</span> <span m='355560'>have</span> <span m='355740'>the</span>
  <span m='355860'>option,</span> <span m='356290'>of</span> <span
  m='356390'>course,</span> <span m='356580'>of</span> <span
  m='356640'>talking</span> <span m='357150'>about</span> <span
  m='357690'>unstable</span> <span m='358260'>systems</span> <span
  m='358830'>or</span> <span m='359070'>stable</span> <span
  m='359520'>systems.</span> <span m='361030'>Generally,</span> <span
  m='362220'>it</span> <span m='362670'>is</span> <span m='363540'>true</span>
  <span m='364110'>that</span> <span m='364710'>stability</span> <span
  m='365610'>is</span> <span m='366180'>a</span> <span
  m='366660'>condition</span> <span m='367230'>on</span> <span
  m='367380'>a</span> <span m='367440'>system</span> <span
  m='368190'>that</span> <span m='368580'>it's</span> <span
  m='368790'>useful</span> <span m='369210'>to</span> <span
  m='369360'>impose.</span> <span m='370410'>In</span> <span
  m='370470'>other</span> <span m='370620'>words,</span> <span
  m='370920'>generally,</span> <span m='371880'>we</span> <span
  m='372240'>would</span> <span m='372450'>like</span> <span
  m='372750'>our</span> <span m='372840'>systems</span> <span
  m='373320'>to</span> <span m='373440'>be</span> <span
  m='373590'>stable,</span> <span m='374160'>although</span> <span
  m='374640'>there</span> <span m='374850'>are</span> <span
  m='375450'>actually</span> <span m='375900'>some</span> <span
  m='376110'>cases</span> <span m='376650'>where</span> <span
  m='377400'>unstable</span> <span m='377940'>systems</span> <span
  m='378480'>are</span> <span m='378540'>useful</span> <span
  m='378960'>to</span> <span m='379080'>talk</span> <span
  m='379380'>about.</span> </p><p><span m='381670'>The</span> <span
  m='382000'>second</span> <span m='384120'>property</span> <span
  m='384870'>or</span> <span m='385830'>condition</span> <span
  m='386970'>that</span> <span m='387480'>it</span> <span m='388110'>is</span>
  <span m='388590'>useful</span> <span m='389010'>sometimes</span> <span
  m='389550'>to</span> <span m='389670'>consider,</span> <span
  m='390270'>is</span> <span m='390570'>the</span> <span
  m='390720'>condition</span> <span m='391140'>of</span> <span
  m='391260'>causality.</span> <span m='393210'>And</span> <span
  m='394170'>causality,</span> <span m='395550'>first</span> <span
  m='395910'>of</span> <span m='396030'>all,</span> <span m='396240'>for</span>
  <span m='396420'>a</span> <span m='396480'>general</span> <span
  m='396900'>system,</span> <span m='398190'>is</span> <span m='398340'>a</span>
  <span m='398400'>statement</span> <span m='399780'>basically</span> <span
  m='400830'>that</span> <span m='401340'>the</span> <span
  m='401460'>system</span> <span m='401910'>doesn't</span> <span
  m='402240'>respond</span> <span m='403230'>before</span> <span
  m='403620'>you</span> <span m='403740'>kick</span> <span m='404010'>it.</span>
  <span m='404950'>In</span> <span m='404970'>other</span> <span
  m='405150'>words,</span> <span m='406270'>if</span> <span m='407040'>we</span>
  <span m='407400'>have</span> <span m='408930'>an</span> <span
  m='409050'>input,</span> <span m='409380'>x</span> <span m='409690'>of
  n,</span> <span m='411210'>the</span> <span m='411390'>output,</span> <span
  m='412200'>y</span> <span m='412560'>of</span> <span m='412710'>n,</span>
  <span m='414270'>for</span> <span m='414450'>some</span> <span
  m='414720'>value</span> <span m='415200'>of</span> <span m='415300'>n--</span>
  <span m='415530'>let's</span> <span m='415710'>say</span> <span
  m='415950'>n</span> <span m='416130'>1--</span> <span
  m='418250'>depends</span> <span m='419060'>only</span> <span
  m='419540'>on</span> <span m='420110'>x of</span> <span m='420430'>n</span>
  <span m='421100'>for</span> <span m='421250'>previous</span> <span
  m='421820'>values</span> <span m='422960'>of</span> <span m='423450'>n.</span>
  </p><p><span m='424130'>So</span> <span m='424790'>for</span> <span
  m='425030'>any</span> <span m='425360'>n</span> <span m='425540'>1,</span>
  <span m='426130'>the</span> <span m='426230'>statement</span> <span
  m='426740'>is</span> <span m='427430'>that</span> <span m='428955'>y</span>
  <span m='429370'>of</span> <span m='429550'>n</span> <span
  m='429830'>only</span> <span m='430160'>depends</span> <span
  m='431330'>on</span> <span m='431680'>x</span> <span m='431970'>of</span>
  <span m='432110'>n</span> <span m='432440'>for</span> <span
  m='432620'>previous</span> <span m='434390'>values</span> <span
  m='435200'>of</span> <span m='435470'>x</span> <span m='435760'>of n.</span>
  <span m='436100'>In</span> <span m='436250'>other</span> <span
  m='436400'>words,</span> <span m='437040'>the</span> <span
  m='437140'>system</span> <span m='437450'>can't</span> <span
  m='437780'>anticipate</span> <span m='438860'>the</span> <span
  m='438980'>values</span> <span m='439610'>that</span> <span
  m='439760'>are</span> <span m='439820'>going</span> <span m='440060'>to</span>
  <span m='440180'>be</span> <span m='440300'>coming</span> <span
  m='440660'>in.</span> </p><p><span m='443240'>For</span> <span
  m='443450'>a</span> <span m='443900'>linear</span> <span
  m='444230'>shift</span> <span m='444790'>invariant</span> <span
  m='445070'>system,</span> <span m='446330'>we</span> <span
  m='446480'>can</span> <span m='446630'>show</span> <span
  m='447740'>that</span> <span m='448490'>a</span> <span
  m='449120'>necessary</span> <span m='449660'>and</span> <span
  m='449750'>sufficient</span> <span m='450230'>condition</span> <span
  m='450800'>for</span> <span m='450980'>causality</span> <span
  m='452270'>is</span> <span m='452870'>that</span> <span m='453170'>the</span>
  <span m='453500'>unit</span> <span m='453860'>sample</span> <span
  m='454250'>response</span> <span m='454790'>of</span> <span
  m='454880'>the</span> <span m='454970'>system</span> <span
  m='456080'>be</span> <span m='456470'>0</span> <span m='457130'>for</span>
  <span m='457520'>n less</span> <span m='457760'>than</span> <span
  m='457910'>0.</span> <span m='458720'>In</span> <span m='458810'>other</span>
  <span m='458990'>words,</span> <span m='459630'>if</span> <span
  m='459830'>the</span> <span m='459920'>unit</span> <span
  m='460160'>sample</span> <span m='460520'>response</span> <span
  m='461450'>of</span> <span m='461510'>the</span> <span
  m='461600'>system</span> <span m='461930'>is</span> <span m='461990'>0</span>
  <span m='462380'>for</span> <span m='462560'>n</span> <span
  m='462680'>less</span> <span m='462890'>than</span> <span m='463040'>0,</span>
  <span m='463940'>the</span> <span m='464030'>system</span> <span
  m='464510'>is</span> <span m='464690'>guaranteed</span> <span
  m='465230'>to</span> <span m='465350'>be</span> <span
  m='465470'>causal.</span> <span m='467120'>If</span> <span
  m='467300'>it's</span> <span m='467450'>not</span> <span m='467690'>0</span>
  <span m='468050'>for</span> <span m='468230'>n</span> <span
  m='468350'>less</span> <span m='468560'>than</span> <span m='468710'>0,</span>
  <span m='469730'>then</span> <span m='470240'>the</span> <span
  m='470360'>system</span> <span m='470870'>is</span> <span
  m='471050'>guaranteed</span> <span m='472010'>not</span> <span
  m='472220'>to</span> <span m='472340'>be</span> <span
  m='472460'>causal.</span> </p><p><span m='474790'>Just</span> <span
  m='475180'>for</span> <span m='475390'>example,</span> <span
  m='476030'>if</span> <span m='476050'>we</span> <span m='476200'>had</span>
  <span m='476440'>a</span> <span m='476500'>unit</span> <span
  m='476770'>sample</span> <span m='477160'>response</span> <span
  m='477760'>which</span> <span m='477940'>was</span> <span m='478090'>2</span>
  <span m='478480'>to the</span> <span m='478660'>n</span> <span
  m='479410'>times</span> <span m='479770'>u</span> <span m='479950'>of</span>
  <span m='480070'>minus</span> <span m='480530'>n--</span> <span
  m='481130'>in</span> <span m='481270'>other</span> <span
  m='481420'>words,</span> <span m='481660'>0</span> <span m='482110'>for</span>
  <span m='482290'>n</span> <span m='482440'>greater</span> <span
  m='482770'>than</span> <span m='482980'>0,</span> <span m='484000'>and</span>
  <span m='484240'>2</span> <span m='484540'>the</span> <span
  m='484690'>n</span> <span m='484830'>for</span> <span m='484990'>n</span>
  <span m='485140'>less</span> <span m='485380'>than</span> <span
  m='485530'>0,</span> <span m='486520'>this,</span> <span m='486730'>of</span>
  <span m='486850'>course,</span> <span m='487240'>would</span> <span
  m='487420'>correspond</span> <span m='488230'>to</span> <span
  m='488650'>a</span> <span m='489400'>non-causal</span> <span
  m='491050'>system,</span> <span m='493780'>since</span> <span
  m='494230'>the</span> <span m='494350'>unit</span> <span
  m='494590'>sample</span> <span m='494980'>response</span> <span
  m='495880'>has</span> <span m='496270'>non-zero</span> <span
  m='496870'>values</span> <span m='497320'>for</span> <span
  m='497440'>negative</span> <span m='498100'>values</span> <span
  m='498580'>of</span> <span m='498700'>n.</span> </p><p><span
  m='500460'>And</span> <span m='501240'>we</span> <span m='501390'>could</span>
  <span m='501540'>also</span> <span m='502110'>examine</span> <span
  m='502560'>stability.</span> <span m='503610'>It</span> <span
  m='503910'>would</span> <span m='504090'>turn</span> <span
  m='504390'>out</span> <span m='504660'>that</span> <span
  m='504810'>this</span> <span m='504990'>corresponds</span> <span
  m='505950'>to</span> <span m='506520'>a</span> <span m='507060'>stable</span>
  <span m='507990'>system,</span> <span m='509280'>although</span> <span
  m='510810'>in</span> <span m='511380'>the</span> <span
  m='511500'>previous</span> <span m='511950'>example,</span> <span
  m='512440'>we</span> <span m='512520'>had talked</span> <span
  m='512850'>about</span> <span m='513120'>2</span> <span m='513350'>to</span>
  <span m='513539'>the</span> <span m='513720'>n</span> <span
  m='514340'>for</span> <span m='514530'>n</span> <span
  m='514740'>positive</span> <span m='515549'>corresponds</span> <span
  m='516210'>to</span> <span m='516360'>an</span> <span
  m='516450'>unstable</span> <span m='516990'>system.</span> <span
  m='517750'>The</span> <span m='517789'>point</span> <span m='518070'>is</span>
  <span m='518220'>that</span> <span m='518340'>if</span> <span
  m='518460'>you</span> <span m='518520'>look</span> <span m='518760'>at</span>
  <span m='518820'>2</span> <span m='519100'>to the</span> <span
  m='519210'>n</span> <span m='519960'>as</span> <span m='520530'>the</span>
  <span m='520710'>index</span> <span m='521100'>n</span> <span
  m='521460'>runs</span> <span m='522270'>negative,</span> <span
  m='523409'>then</span> <span m='524039'>that</span> <span
  m='524340'>is--</span> <span m='525380'>as</span> <span m='525940'>n
  runs</span> <span m='526340'>negative,</span> <span m='527160'>it's</span>
  <span m='527490'>an</span> <span m='527640'>exponential</span> <span
  m='528240'>that's</span> <span m='528450'>decaying</span> <span
  m='529200'>in</span> <span m='529650'>negative</span> <span
  m='529980'>values</span> <span m='530430'>of n.</span> <span
  m='531090'>So</span> <span m='531240'>then,</span> <span m='531420'>in</span>
  <span m='531510'>fact,</span> <span m='531780'>this</span> <span
  m='531960'>is</span> <span m='532080'>absolutely</span> <span
  m='532620'>summable--</span> <span m='533610'>that</span> <span
  m='533760'>makes</span> <span m='534030'>it</span> <span
  m='534120'>stable,</span> <span m='534810'>but</span> <span
  m='535020'>it's</span> <span m='535170'>obviously</span> <span
  m='535680'>non-causal.</span> </p><p><span m='537870'>Now,</span> <span
  m='538080'>I</span> <span m='538170'>want</span> <span m='538380'>to</span>
  <span m='538440'>stress--</span> <span m='539550'>it's</span> <span
  m='539730'>a</span> <span m='540550'>very</span> <span
  m='540720'>important</span> <span m='541110'>point</span> <span
  m='541530'>to</span> <span m='541650'>stress--</span> <span
  m='542790'>that</span> <span m='543480'>causality</span> <span
  m='544530'>is,</span> <span m='545250'>of</span> <span
  m='545340'>course,</span> <span m='545610'>a</span> <span
  m='545640'>useful</span> <span m='546000'>thing</span> <span
  m='546180'>to</span> <span m='546480'>inquire</span> <span
  m='547080'>about</span> <span m='547350'>about</span> <span
  m='547620'>a</span> <span m='547680'>system,</span> <span
  m='548140'>it's</span> <span m='548250'>useful</span> <span
  m='548670'>to</span> <span m='549360'>ask,</span> <span m='549870'>is</span>
  <span m='550050'>the</span> <span m='550140'>system</span> <span
  m='550500'>causal</span> <span m='550980'>or</span> <span m='551070'>is</span>
  <span m='551220'>it</span> <span m='551280'>not</span> <span
  m='551520'>causal?</span> <span m='552570'>But</span> <span
  m='553110'>generally,</span> <span m='554340'>it</span> <span
  m='554640'>is</span> <span m='555030'>not</span> <span
  m='555960'>necessarily</span> <span m='556710'>true</span> <span
  m='557340'>that</span> <span m='557490'>causality</span> <span
  m='558390'>is</span> <span m='558540'>a</span> <span
  m='558600'>condition</span> <span m='559830'>that</span> <span
  m='560010'>we'll</span> <span m='560190'>want</span> <span
  m='560370'>to</span> <span m='560490'>impose</span> <span m='561090'>on</span>
  <span m='561210'>the</span> <span m='561310'>system.</span> <span
  m='562410'>There</span> <span m='562800'>are</span> <span
  m='563010'>many</span> <span m='563340'>examples</span> <span
  m='564180'>of</span> <span m='564480'>useful,</span> <span
  m='565560'>non-causal</span> <span m='566340'>systems,</span> <span
  m='567750'>and</span> <span m='568380'>in</span> <span m='568620'>many</span>
  <span m='568950'>instances,</span> <span m='570070'>we'll</span> <span
  m='570210'>want</span> <span m='570510'>to</span> <span m='570660'>talk</span>
  <span m='571020'>about</span> <span m='571530'>systems</span> <span
  m='572070'>which</span> <span m='572280'>are</span> <span
  m='572340'>non-causal.</span> </p><p><span m='573540'>So</span> <span
  m='573930'>again,</span> <span m='574380'>it's</span> <span
  m='574590'>useful</span> <span m='574890'>to</span> <span
  m='575040'>inquire</span> <span m='575760'>about</span> <span
  m='575970'>whether</span> <span m='576180'>a</span> <span
  m='576210'>system</span> <span m='576540'>is</span> <span
  m='576630'>causal</span> <span m='576990'>or</span> <span
  m='577080'>not</span> <span m='577320'>causal,</span> <span
  m='578250'>but</span> <span m='578730'>it</span> <span m='578940'>is</span>
  <span m='579180'>not</span> <span m='579420'>generally</span> <span
  m='579870'>useful</span> <span m='580380'>to</span> <span
  m='580710'>constrain</span> <span m='581310'>ourselves</span> <span
  m='582420'>to</span> <span m='582570'>talk</span> <span m='582990'>only</span>
  <span m='583410'>about</span> <span m='583830'>causal</span> <span
  m='584310'>systems.</span> </p><p><span m='586120'>The</span> <span
  m='586370'>story</span> <span m='586680'>is</span> <span
  m='586740'>somewhat</span> <span m='587130'>different</span> <span
  m='587430'>for</span> <span m='587550'>stability</span> <span
  m='588150'>in</span> <span m='588240'>the</span> <span m='588330'>sense</span>
  <span m='588720'>that</span> <span m='589380'>an</span> <span
  m='590490'>unstable</span> <span m='591060'>system</span> <span
  m='591480'>is</span> <span m='591540'>somewhat</span> <span
  m='591930'>less</span> <span m='592170'>useful</span> <span
  m='593220'>than</span> <span m='593910'>a</span> <span
  m='594420'>non-causal</span> <span m='595200'>system.</span> </p><p><span
  m='596590'>So</span> <span m='597330'>these</span> <span m='597600'>are</span>
  <span m='597870'>two</span> <span m='598380'>additional</span> <span
  m='599970'>conditions,</span> <span m='600510'>or</span> <span
  m='600600'>properties,</span> <span m='601440'>that</span> <span
  m='601770'>we'll</span> <span m='601980'>sometimes</span> <span
  m='602970'>want</span> <span m='603300'>to</span> <span
  m='603990'>inquire</span> <span m='604590'>about</span> <span
  m='604980'>when</span> <span m='605160'>we</span> <span m='605250'>talk</span>
  <span m='605520'>about</span> <span m='605760'>a</span> <span
  m='605820'>system.</span> </p><p><span m='608670'>In</span> <span
  m='609300'>general,</span> <span m='610050'>for</span> <span
  m='610440'>linear</span> <span m='610770'>shift</span> <span
  m='611100'>invariant</span> <span m='611630'>systems,</span> <span
  m='612480'>there</span> <span m='612930'>is</span> <span m='613140'>a</span>
  <span m='613200'>wide</span> <span m='613860'>latitude</span> <span
  m='614790'>in</span> <span m='615150'>terms</span> <span m='615540'>of</span>
  <span m='615600'>the</span> <span m='615720'>description</span> <span
  m='616500'>of</span> <span m='616650'>those</span> <span
  m='616890'>systems.</span> <span m='618060'>And</span> <span
  m='618810'>that</span> <span m='619260'>is</span> <span m='619860'>a</span>
  <span m='619920'>similar</span> <span m='620640'>type</span> <span
  m='620850'>of</span> <span m='620970'>statement</span> <span
  m='621360'>that</span> <span m='621510'>applies</span> <span
  m='621900'>in</span> <span m='621990'>the</span> <span
  m='622080'>continuous</span> <span m='622620'>time</span> <span
  m='622890'>case,</span> <span m='623250'>also.</span> <span
  m='624420'>Just</span> <span m='624720'>as</span> <span m='624830'>in</span>
  <span m='624960'>the</span> <span m='625050'>continuous</span> <span
  m='625650'>time</span> <span m='625950'>case,</span> <span
  m='626550'>it</span> <span m='627150'>is</span> <span m='627390'>useful</span>
  <span m='628020'>to</span> <span m='628200'>concentrate,</span> <span
  m='629730'>in</span> <span m='629880'>many</span> <span
  m='630330'>cases,</span> <span m='631440'>on</span> <span
  m='632520'>systems</span> <span m='633750'>that</span> <span
  m='634530'>can</span> <span m='634770'>be</span> <span
  m='634920'>implemented</span> <span m='635460'>with</span> <span
  m='635670'>r's,</span> <span m='635925'>l's,</span> <span
  m='636180'>and</span> <span m='636320'>c's--</span> <span
  m='636960'>and</span> <span m='637140'>consequently</span> <span
  m='637485'>are</span> <span m='637830'>representable</span> <span
  m='638580'>by</span> <span m='638760'>linear</span> <span
  m='639030'>constant</span> <span m='639450'>coefficient</span> <span
  m='640050'>differential</span> <span m='640650'>equations.</span> <span
  m='641940'>In</span> <span m='642060'>the</span> <span
  m='642120'>discrete</span> <span m='642510'>time</span> <span
  m='642840'>case,</span> <span m='643290'>it's</span> <span
  m='643500'>often</span> <span m='644130'>useful</span> <span
  m='644760'>to</span> <span m='644880'>concentrate</span> <span
  m='646140'>on</span> <span m='646470'>systems</span> <span
  m='647400'>that</span> <span m='647700'>are</span> <span
  m='649110'>describable</span> <span m='650220'>by</span> <span
  m='651150'>linear</span> <span m='651540'>constant</span> <span
  m='651990'>coefficient</span> <span m='652620'>difference</span> <span
  m='653010'>equations.</span> </p><p><span m='654540'>So</span> <span
  m='655020'>I</span> <span m='655140'>would</span> <span m='655290'>like</span>
  <span m='656100'>to</span> <span m='656820'>just</span> <span
  m='657600'>briefly</span> <span m='658200'>introduce</span> <span
  m='659430'>the</span> <span m='659520'>class</span> <span m='659910'>of</span>
  <span m='660000'>systems</span> <span m='661230'>which</span> <span
  m='661740'>are</span> <span m='662400'>representable</span> <span
  m='663450'>by</span> <span m='664020'>linear</span> <span
  m='664560'>constant</span> <span m='665040'>coefficient</span> <span
  m='665640'>difference</span> <span m='666000'>equations.</span> <span
  m='667230'>And</span> <span m='668790'>the</span> <span
  m='670410'>discussion</span> <span m='670950'>in</span> <span
  m='671040'>this</span> <span m='671220'>lecture</span> <span
  m='671850'>is</span> <span m='672030'>only</span> <span m='672300'>a</span>
  <span m='672330'>brief</span> <span m='672630'>introduction,</span> <span
  m='673440'>and</span> <span m='674040'>we'll,</span> <span
  m='674310'>in</span> <span m='674400'>fact,</span> <span m='674700'>be</span>
  <span m='674820'>returning</span> <span m='675270'>to</span> <span
  m='675390'>this</span> <span m='675540'>class</span> <span
  m='675870'>of</span> <span m='675960'>systems</span> <span
  m='676830'>several</span> <span m='677280'>times</span> <span
  m='677760'>over</span> <span m='678270'>this</span> <span
  m='678420'>set</span> <span m='678660'>of</span> <span
  m='678750'>lessons.</span> </p><p><span m='682380'>We</span> <span
  m='682500'>refer</span> <span m='683430'>to</span> <span m='683940'>an</span>
  <span m='684270'>Nth</span> <span m='684630'>order--</span> <span
  m='685290'>linear</span> <span m='685590'>constant</span> <span
  m='686010'>coefficient</span> <span m='686670'>difference</span> <span
  m='687030'>equation--</span> <span m='688290'>as</span> <span
  m='688500'>being</span> <span m='688980'>in</span> <span m='689130'>the</span>
  <span m='689220'>form</span> <span m='689880'>that</span> <span
  m='690000'>I've</span> <span m='690180'>indicated</span> <span
  m='690780'>here.</span> <span m='691990'>And</span> <span
  m='692580'>what</span> <span m='692820'>it</span> <span
  m='692880'>consists</span> <span m='693540'>of</span> <span
  m='694410'>is</span> <span m='695010'>a</span> <span m='695490'>linear</span>
  <span m='695850'>combination</span> <span m='697470'>of</span> <span
  m='698610'>the</span> <span m='699060'>delayed</span> <span
  m='700170'>output</span> <span m='700770'>sequences</span> <span
  m='702240'>equal</span> <span m='702660'>to</span> <span m='703260'>a</span>
  <span m='703590'>linear</span> <span m='703980'>combination</span> <span
  m='704850'>of</span> <span m='705180'>delayed</span> <span
  m='705690'>input</span> <span m='706080'>sequences.</span> <span
  m='707310'>A</span> <span m='707370'>differential</span> <span
  m='708000'>equation,</span> <span m='708450'>of</span> <span
  m='708510'>course,</span> <span m='708780'>in</span> <span
  m='708870'>continuous</span> <span m='709470'>time</span> <span
  m='709980'>involves</span> <span m='710370'>linear</span> <span
  m='710640'>combinations</span> <span m='711330'>of</span> <span
  m='711420'>derivatives.</span> <span m='712830'>The</span> <span
  m='713820'>corresponding</span> <span m='715260'>situation</span> <span
  m='716010'>in</span> <span m='716100'>the</span> <span
  m='716190'>discrete</span> <span m='716550'>time</span> <span
  m='716850'>case,</span> <span m='717690'>is</span> <span m='718080'>a</span>
  <span m='718320'>linear</span> <span m='718650'>combination</span> <span
  m='719610'>of</span> <span m='720270'>differences.</span> </p><p><span
  m='721870'>So</span> <span m='722610'>this</span> <span m='722880'>is,</span>
  <span m='723360'>then,</span> <span m='723930'>a</span> <span
  m='725310'>general</span> <span m='725940'>Nth</span> <span
  m='726900'>order,</span> <span m='727260'>linear--</span> <span
  m='728520'>in</span> <span m='728610'>the</span> <span m='728700'>sense</span>
  <span m='728970'>that</span> <span m='729090'>it's</span> <span
  m='729210'>a</span> <span m='729270'>linear</span> <span
  m='729630'>combination--</span> <span m='731010'>constant</span> <span
  m='731500'>coefficient--</span> <span m='732870'>meaning</span> <span
  m='733260'>that</span> <span m='734340'>these</span> <span
  m='735240'>are</span> <span m='735600'>constant</span> <span
  m='736170'>numbers,</span> <span m='736620'>as</span> <span
  m='736770'>opposed</span> <span m='737100'>to</span> <span
  m='737190'>being</span> <span m='737430'>functions</span> <span
  m='737920'>of</span> <span m='738060'>n--</span> <span
  m='738780'>difference</span> <span m='739170'>equation--</span> <span
  m='739950'>meaning</span> <span m='740340'>it</span> <span
  m='740520'>involves</span> <span m='741450'>differences</span> <span
  m='742170'>of</span> <span m='742320'>the</span> <span m='742440'>input</span>
  <span m='742740'>and</span> <span m='742830'>output</span> <span
  m='743190'>sequence.</span> <span m='746070'>The</span> <span
  m='746490'>order</span> <span m='746940'>of</span> <span m='747030'>the</span>
  <span m='747120'>difference</span> <span m='747450'>equation</span> <span
  m='748620'>generally</span> <span m='749190'>is</span> <span
  m='749340'>used</span> <span m='749700'>to</span> <span
  m='749850'>refer</span> <span m='750480'>to</span> <span m='751440'>the</span>
  <span m='751680'>number</span> <span m='752040'>of</span> <span
  m='752160'>delays</span> <span m='753120'>required</span> <span
  m='753780'>in</span> <span m='753930'>the</span> <span
  m='754050'>output</span> <span m='754440'>sequence.</span> <span
  m='755790'>In</span> <span m='755940'>general,</span> <span
  m='756790'>the</span> <span m='756810'>number</span> <span
  m='757080'>of</span> <span m='757170'>delays</span> <span m='757770'>in</span>
  <span m='758030'>the</span> <span m='758130'>input</span> <span
  m='758460'>sequence,</span> <span m='759000'>M,</span> <span
  m='760020'>does</span> <span m='760170'>not</span> <span
  m='760380'>have</span> <span m='760590'>to</span> <span m='760710'>be</span>
  <span m='761040'>equal</span> <span m='761460'>to</span> <span
  m='761610'>N.</span> <span m='762420'>But</span> <span m='762630'>it's</span>
  <span m='762720'>generally</span> <span m='763140'>convenient</span> <span
  m='763620'>to</span> <span m='763710'>refer</span> <span m='764070'>to</span>
  <span m='764220'>the</span> <span m='764370'>order</span> <span
  m='764940'>as</span> <span m='765120'>corresponding</span> <span
  m='765960'>to</span> <span m='766140'>the</span> <span
  m='766740'>number</span> <span m='767040'>of</span> <span
  m='767130'>delays</span> <span m='767550'>involved</span> <span
  m='767970'>in</span> <span m='768030'>the</span> <span
  m='768150'>output</span> <span m='768540'>sequence.</span> </p><p><span
  m='771390'>For</span> <span m='772950'>the</span> <span m='773820'>0th</span>
  <span m='774420'>order</span> <span m='774960'>difference</span> <span
  m='775380'>equation,</span> <span m='776550'>the</span> <span
  m='776850'>solution</span> <span m='778170'>if</span> <span
  m='778500'>it</span> <span m='778740'>corresponds</span> <span
  m='779340'>to</span> <span m='779460'>a</span> <span
  m='779490'>representation</span> <span m='780450'>of</span> <span
  m='780540'>a</span> <span m='780570'>linear</span> <span
  m='780870'>shift</span> <span m='781140'>and</span> <span
  m='781290'>invariant</span> <span m='781610'>system,</span> <span
  m='782710'>the</span> <span m='782810'>solution</span> <span
  m='783450'>is</span> <span m='784170'>trivial--</span> <span
  m='785310'>very</span> <span m='785550'>straightforward.</span> <span
  m='786910'>Particular,</span> <span m='787480'>let's</span> <span
  m='787620'>examine</span> <span m='788550'>what</span> <span
  m='788730'>this</span> <span m='788910'>difference</span> <span
  m='789270'>equation</span> <span m='789810'>reduces</span> <span
  m='790380'>to,</span> <span m='791280'>if</span> <span m='791430'>N</span>
  <span m='791670'>is</span> <span m='791820'>equal</span> <span
  m='792120'>to</span> <span m='792270'>0.</span> <span m='793620'>And</span>
  <span m='794040'>just</span> <span m='794250'>for</span> <span
  m='794400'>convenience,</span> <span m='795410'>we'll</span> <span
  m='795690'>choose</span> <span m='796800'>the</span> <span
  m='797010'>coefficients</span> <span m='797760'>to</span> <span
  m='797880'>be</span> <span m='798000'>normalized</span> <span
  m='798870'>so</span> <span m='799050'>that</span> <span m='799290'>a</span>
  <span m='799470'>sub 0</span> <span m='800040'>is</span> <span
  m='800160'>equal</span> <span m='800430'>to</span> <span m='800550'>1.</span>
  <span m='801240'>Obviously</span> <span m='801720'>anything</span> <span
  m='802020'>I</span> <span m='802140'>say</span> <span m='802740'>is</span>
  <span m='803700'>straightforwardly</span> <span m='804600'>generalized</span>
  <span m='805860'>for</span> <span m='806250'>a</span> <span
  m='806410'>0</span> <span m='806730'>not</span> <span m='806940'>equal</span>
  <span m='807210'>to</span> <span m='807330'>1,</span> <span
  m='807620'>but</span> <span m='807990'>that's</span> <span
  m='808290'>just</span> <span m='809420'>a</span> <span
  m='809490'>convenient</span> <span m='810060'>normalization</span> <span
  m='810810'>to</span> <span m='810960'>impose.</span> </p><p><span
  m='813520'>All</span> <span m='813660'>right,</span> <span
  m='813930'>if</span> <span m='814110'>N</span> <span m='814230'>is</span>
  <span m='814350'>equal</span> <span m='814590'>to</span> <span
  m='814710'>0,</span> <span m='815160'>and a 0</span> <span
  m='815520'>is</span> <span m='815610'>equal</span> <span m='815850'>to</span>
  <span m='816000'>1,</span> <span m='816970'>then</span> <span
  m='817080'>what</span> <span m='817260'>this</span> <span
  m='817440'>equation</span> <span m='818010'>looks</span> <span
  m='818280'>like</span> <span m='819120'>is</span> <span m='819720'>just</span>
  <span m='820230'>on</span> <span m='820350'>the</span> <span
  m='820410'>left</span> <span m='820680'>hand</span> <span
  m='820890'>side,</span> <span m='821320'>y</span> <span m='821550'>of</span>
  <span m='821680'>n,</span> <span m='822240'>and</span> <span
  m='822360'>the</span> <span m='822450'>right</span> <span
  m='822660'>hand</span> <span m='822870'>side</span> <span m='823290'>as</span>
  <span m='823470'>it</span> <span m='823590'>is.</span> <span
  m='824880'>So</span> <span m='825390'>we</span> <span m='825570'>have</span>
  <span m='825720'>y</span> <span m='826020'>of</span> <span m='826140'>n</span>
  <span m='826680'>is</span> <span m='826860'>equal</span> <span
  m='827280'>to</span> <span m='828180'>this</span> <span m='828480'>sum.</span>
  <span m='830510'>And</span> <span m='830710'>that</span> <span
  m='830890'>looks</span> <span m='831160'>suspiciously</span> <span
  m='832540'>like</span> <span m='833200'>the</span> <span
  m='833400'>convolution</span> <span m='834170'>sum--</span> <span
  m='834960'>it</span> <span m='835060'>involves</span> <span
  m='836320'>a</span> <span m='836500'>linear</span> <span
  m='836860'>combination</span> <span m='837640'>only</span> <span
  m='838120'>of</span> <span m='838820'>delayed</span> <span
  m='839510'>input</span> <span m='840040'>sequences.</span> </p><p><span
  m='841540'>And</span> <span m='841660'>so,</span> <span m='841990'>in</span>
  <span m='842140'>fact,</span> <span m='844690'>this</span> <span
  m='845260'>is</span> <span m='845740'>identical</span> <span
  m='846370'>to</span> <span m='846490'>the</span> <span
  m='846610'>convolution</span> <span m='847340'>sum.</span> <span
  m='848110'>If</span> <span m='848260'>we</span> <span
  m='848350'>thought</span> <span m='848590'>of</span> <span
  m='848680'>this,</span> <span m='848850'>say,</span> <span
  m='849400'>as</span> <span m='850380'>h</span> <span m='850770'>of</span>
  <span m='850990'>r,</span> <span m='852370'>h of</span> <span m='852760'>r,
  then,</span> <span m='853000'>is</span> <span m='853120'>equal</span> <span
  m='853360'>to</span> <span m='853480'>b</span> <span m='853690'>sub r.</span>
  <span m='854920'>So</span> <span m='855700'>the</span> <span
  m='855820'>unit</span> <span m='856120'>sample</span> <span
  m='856510'>response</span> <span m='857710'>corresponding</span> <span
  m='858550'>to</span> <span m='858880'>the</span> <span m='859000'>0th</span>
  <span m='859450'>order</span> <span m='859720'>difference</span> <span
  m='860110'>equation</span> <span m='862030'>is</span> <span
  m='862210'>just</span> <span m='862720'>this</span> <span
  m='862820'>set</span> <span m='863050'>of</span> <span
  m='863140'>coefficients,</span> <span m='865660'>and,</span> <span
  m='866200'>of</span> <span m='866350'>course,</span> <span m='868300'>r</span>
  <span m='869050'>runs</span> <span m='869320'>only</span> <span
  m='869560'>from</span> <span m='869710'>0</span> <span m='870100'>to</span>
  <span m='870250'>M,</span> <span m='871120'>so</span> <span
  m='871540'>it's</span> <span m='871960'>the</span> <span
  m='872080'>coefficients</span> <span m='872850'>b sub n</span> <span
  m='873730'>for</span> <span m='874210'>n</span> <span
  m='874480'>between</span> <span m='874870'>0</span> <span
  m='875380'>and</span> <span m='875570'>M.</span> <span m='876850'>And</span>
  <span m='877180'>it's</span> <span m='877300'>equal</span> <span
  m='877570'>to</span> <span m='877690'>0,</span> <span
  m='878260'>otherwise.</span> </p><p><span m='879440'>So</span> <span
  m='879610'>that's</span> <span m='879970'>very</span> <span
  m='880230'>straightforward.</span> <span m='881060'>We</span> <span
  m='881080'>can</span> <span m='881260'>pick</span> <span m='881470'>off</span>
  <span m='881650'>the</span> <span m='881770'>solution,</span> <span
  m='882220'>essentially,</span> <span m='882640'>by</span> <span
  m='882790'>recognizing</span> <span m='883570'>this</span> <span
  m='883870'>as</span> <span m='883990'>the</span> <span
  m='884080'>convolution</span> <span m='884770'>sum.</span> <span
  m='886090'>Obviously,</span> <span m='887590'>another</span> <span
  m='887920'>way</span> <span m='888430'>of</span> <span
  m='890880'>obtaining</span> <span m='891720'>the</span> <span
  m='891840'>unit</span> <span m='892110'>sample</span> <span
  m='892500'>response</span> <span m='893010'>corresponding</span> <span
  m='893670'>to</span> <span m='893790'>this</span> <span
  m='893940'>system</span> <span m='894990'>is</span> <span
  m='895200'>simply</span> <span m='895530'>to</span> <span m='895650'>plug
  in</span> <span m='896010'>a</span> <span m='896430'>unit</span> <span
  m='896800'>sample</span> <span m='897300'>for</span> <span m='897480'>x</span>
  <span m='897690'>of n.</span> <span m='898500'>And</span> <span
  m='898590'>you'll</span> <span m='898710'>see,</span> <span
  m='899050'>in</span> <span m='899150'>fact,</span> <span
  m='899500'>that</span> <span m='899520'>what</span> <span
  m='899730'>comes</span> <span m='900000'>rolling</span> <span
  m='900420'>out</span> <span m='900810'>are these</span> <span
  m='901020'>coefficients</span> <span m='901740'>b sub</span> <span
  m='901920'>r,</span> <span m='902460'>or</span> <span m='903110'>b sub</span>
  <span m='903480'>n.</span> </p><p><span m='904260'>So</span> <span
  m='904590'>if</span> <span m='904800'>this</span> <span m='905310'>is</span>
  <span m='905460'>used</span> <span m='905880'>to</span> <span
  m='906060'>describe</span> <span m='906840'>a</span> <span
  m='906990'>linear</span> <span m='907320'>shift</span> <span
  m='907660'>invariant</span> <span m='908090'>system,</span> <span
  m='909120'>the</span> <span m='909220'>unit</span> <span
  m='909360'>sample</span> <span m='909780'>response</span> <span
  m='910440'>corresponds</span> <span m='911040'>simply</span> <span
  m='911970'>to</span> <span m='912300'>the</span> <span
  m='912420'>coefficients</span> <span m='913170'>in</span> <span
  m='913260'>the</span> <span m='913350'>difference</span> <span
  m='913680'>equation.</span> </p><p><span m='916050'>For</span> <span
  m='916260'>n</span> <span m='916710'>not</span> <span m='916950'>equal</span>
  <span m='917190'>to</span> <span m='917310'>0,</span> <span
  m='917920'>it's</span> <span m='918120'>not</span> <span
  m='918330'>quite</span> <span m='918630'>as</span> <span
  m='918690'>straightforward</span> <span m='919500'>as</span> <span
  m='919650'>that.</span> <span m='920910'>First</span> <span
  m='921270'>of</span> <span m='921390'>all,</span> <span m='922240'>let</span>
  <span m='922350'>me</span> <span m='922800'>point</span> <span
  m='923130'>out</span> <span m='923700'>that</span> <span m='924270'>for</span>
  <span m='924990'>N</span> <span m='925500'>not</span> <span
  m='925710'>equal</span> <span m='926010'>to</span> <span m='926160'>0,</span>
  <span m='927150'>the</span> <span m='927240'>left</span> <span
  m='927570'>hand</span> <span m='927780'>side</span> <span m='928110'>of</span>
  <span m='928200'>this</span> <span m='928410'>equation</span> <span
  m='929130'>involves</span> <span m='930630'>y</span> <span
  m='930960'>of</span> <span m='931110'>n,</span> <span m='931650'>y</span>
  <span m='931950'>of</span> <span m='932040'>n</span> <span m='932190'>minus
  1,</span> <span m='932580'>y</span> <span m='932865'>of</span> <span
  m='933150'>minus</span> <span m='933660'>2,</span> <span m='933900'>et
  cetera,</span> <span m='934290'>up</span> <span m='934410'>to</span> <span
  m='934650'>y of</span> <span m='935160'>little</span> <span
  m='935400'>n</span> <span m='935550'>minus</span> <span
  m='935850'>capital</span> <span m='936420'>N.</span> <span
  m='938070'>We</span> <span m='938250'>can</span> <span m='938490'>take</span>
  <span m='939860'>all</span> <span m='940070'>of</span> <span
  m='940190'>the</span> <span m='940280'>terms</span> <span
  m='940760'>except</span> <span m='941330'>the</span> <span
  m='941450'>one</span> <span m='941660'>involving</span> <span
  m='942140'>y</span> <span m='942410'>of</span> <span m='942560'>n</span> <span
  m='943880'>over</span> <span m='944630'>to</span> <span m='945080'>the</span>
  <span m='945200'>right</span> <span m='945440'>hand</span> <span
  m='945680'>side</span> <span m='945980'>of</span> <span m='946070'>the</span>
  <span m='946190'>equation,</span> <span m='947600'>and</span> <span
  m='947690'>end</span> <span m='947900'>up</span> <span m='948020'>with</span>
  <span m='948110'>an</span> <span m='948230'>equation</span> <span
  m='949850'>which</span> <span m='950150'>expresses</span> <span
  m='950690'>y</span> <span m='951020'>of</span> <span m='951170'>n</span> <span
  m='952220'>as</span> <span m='952670'>a</span> <span m='952700'>linear</span>
  <span m='953120'>combination</span> <span m='953810'>of</span> <span
  m='953910'>delayed</span> <span m='954290'>inputs,</span> <span
  m='955640'>and</span> <span m='956180'>a</span> <span m='956240'>linear</span>
  <span m='956600'>combination</span> <span m='957440'>of</span> <span
  m='957590'>past</span> <span m='958700'>output</span> <span
  m='959420'>sequences.</span> </p><p><span m='961440'>If</span> <span
  m='961490'>we</span> <span m='961610'>rewrite</span> <span
  m='962360'>this</span> <span m='962570'>equation</span> <span
  m='963290'>in</span> <span m='963440'>this</span> <span
  m='963620'>form--</span> <span m='964830'>and</span> <span
  m='964850'>again,</span> <span m='965460'>just</span> <span
  m='965570'>for</span> <span m='965690'>convenience,</span> <span
  m='966350'>we'll</span> <span m='966860'>choose</span> <span
  m='968120'>a</span> <span m='968270'>0</span> <span m='968720'>equal</span>
  <span m='968990'>to</span> <span m='969110'>1,</span> <span
  m='969650'>simply</span> <span m='970010'>normalizing</span> <span
  m='971630'>that</span> <span m='971790'>coefficient.</span> <span
  m='973250'>Then,</span> <span m='973970'>the</span> <span
  m='974480'>difference</span> <span m='974870'>equation</span> <span
  m='975800'>that</span> <span m='976190'>we</span> <span m='976370'>end</span>
  <span m='976610'>up</span> <span m='976820'>with</span> <span
  m='977720'>is</span> <span m='978380'>in</span> <span m='978530'>the</span>
  <span m='978620'>form</span> <span m='978950'>that</span> <span
  m='979070'>I've</span> <span m='979190'>indicated</span> <span
  m='979730'>here,</span> <span m='980480'>y</span> <span m='980850'>of</span>
  <span m='981160'>n</span> <span m='982070'>is</span> <span m='982640'>a</span>
  <span m='982700'>linear</span> <span m='983030'>combination</span> <span
  m='983990'>of</span> <span m='984580'>delayed</span> <span
  m='984920'>input</span> <span m='985730'>sequences</span> <span
  m='987200'>minus--</span> <span m='987980'>because</span> <span
  m='988310'>we</span> <span m='988670'>brought</span> <span
  m='988940'>that</span> <span m='989090'>from</span> <span
  m='989270'>the</span> <span m='989390'>other</span> <span
  m='989570'>side</span> <span m='989840'>of</span> <span m='989900'>the</span>
  <span m='990020'>equation--</span> <span m='991130'>minus</span> <span
  m='991550'>a</span> <span m='991610'>linear</span> <span
  m='991910'>combination</span> <span m='992750'>of</span> <span
  m='993250'>past--</span> <span m='993920'>of</span> <span
  m='994070'>the</span> <span m='994190'>previous</span> <span
  m='995240'>output</span> <span m='995660'>values.</span> </p><p><span
  m='998710'>What</span> <span m='998890'>that</span> <span
  m='999130'>says</span> <span m='1000390'>is</span> <span
  m='1000690'>that</span> <span m='1002190'>we</span> <span
  m='1002400'>presumably</span> <span m='1003960'>can</span> <span
  m='1004470'>iterate</span> <span m='1004980'>this</span> <span
  m='1005190'>equation,</span> <span m='1006450'>or</span> <span
  m='1007350'>equivalently,</span> <span m='1007920'>what</span> <span
  m='1008070'>it</span> <span m='1008190'>says</span> <span
  m='1008610'>is</span> <span m='1008730'>that</span> <span
  m='1008910'>the</span> <span m='1009000'>difference</span> <span
  m='1009390'>equation</span> <span m='1009930'>corresponds</span> <span
  m='1011430'>to</span> <span m='1011790'>an</span> <span
  m='1011940'>explicit</span> <span m='1012750'>input/output</span> <span
  m='1013650'>relationship</span> <span m='1015090'>for</span> <span
  m='1015300'>the</span> <span m='1015390'>system,</span> <span
  m='1016320'>because</span> <span m='1017700'>if</span> <span
  m='1017880'>somehow</span> <span m='1018420'>we</span> <span
  m='1018540'>could</span> <span m='1018690'>get</span> <span
  m='1018900'>the</span> <span m='1019020'>equation</span> <span
  m='1019560'>going,</span> <span m='1020940'>then</span> <span
  m='1021420'>we</span> <span m='1021600'>can</span> <span
  m='1021750'>solve</span> <span m='1023070'>for</span> <span
  m='1023250'>y</span> <span m='1023590'>of n--</span> <span
  m='1024089'>we</span> <span m='1024210'>can</span> <span
  m='1024329'>solve</span> <span m='1024569'>for</span> <span
  m='1024720'>y</span> <span m='1025040'>of</span> <span m='1025109'>n</span>
  <span m='1025319'>if</span> <span m='1025470'>we</span> <span
  m='1025589'>have</span> <span m='1026430'>the</span> <span
  m='1026700'>right</span> <span m='1027000'>previous</span> <span
  m='1027930'>values</span> <span m='1028560'>for</span> <span
  m='1028710'>y</span> <span m='1028980'>of</span> <span m='1029150'>n.</span>
  <span m='1029880'>And</span> <span m='1030060'>then</span> <span
  m='1030240'>we</span> <span m='1030359'>can</span> <span
  m='1030510'>solve</span> <span m='1031020'>for</span> <span m='1031260'>y of
  n</span> <span m='1031710'>plus</span> <span m='1031980'>1,</span> <span
  m='1032550'>y of n plus</span> <span m='1032819'>2,</span> <span
  m='1033000'>et cetera.</span> <span m='1033420'>In</span> <span
  m='1033480'>other</span> <span m='1033630'>words,</span> <span
  m='1033940'>we</span> <span m='1033990'>can</span> <span
  m='1034770'>continue</span> <span m='1035310'>to</span> <span
  m='1035460'>iterate</span> <span m='1035880'>the</span> <span
  m='1036000'>equation.</span> </p><p><span m='1037960'>What's</span> <span
  m='1038040'>required</span> <span m='1038579'>to</span> <span
  m='1038730'>do</span> <span m='1038940'>that</span> <span
  m='1039898'>are</span> <span m='1040377'>that</span> <span
  m='1040859'>we</span> <span m='1041010'>have</span> <span
  m='1041190'>to</span> <span m='1041310'>know</span> <span
  m='1041460'>the</span> <span m='1041609'>input--</span> <span
  m='1042140'>and</span> <span m='1042339'>we</span> <span
  m='1042480'>assume,</span> <span m='1042849'>of</span> <span
  m='1042950'>course,</span> <span m='1043210'>that</span> <span
  m='1043310'>we</span> <span m='1043410'>know</span> <span
  m='1043500'>that--</span> <span m='1044339'>and</span> <span
  m='1044550'>we</span> <span m='1044670'>have</span> <span
  m='1044910'>to</span> <span m='1045030'>know</span> <span
  m='1045210'>some</span> <span m='1045390'>previous</span> <span
  m='1046380'>output</span> <span m='1047099'>values.</span> <span
  m='1048750'>And</span> <span m='1050530'>to</span> <span
  m='1050680'>know</span> <span m='1051160'>the</span> <span
  m='1051250'>previous</span> <span m='1051730'>output</span> <span
  m='1052120'>values,</span> <span m='1052960'>then,</span> <span
  m='1054250'>means</span> <span m='1054940'>that</span> <span
  m='1055390'>there</span> <span m='1055500'>is</span> <span
  m='1055600'>some</span> <span m='1055720'>additional</span> <span
  m='1056200'>information</span> <span m='1056800'>that</span> <span
  m='1056890'>we</span> <span m='1057010'>have</span> <span
  m='1057220'>to</span> <span m='1057310'>specify,</span> <span
  m='1058630'>and</span> <span m='1059260'>those</span> <span
  m='1059560'>we'll</span> <span m='1059660'>generally</span> <span
  m='1060100'>refer</span> <span m='1060460'>to</span> <span
  m='1060790'>as</span> <span m='1060940'>the</span> <span
  m='1061030'>boundary</span> <span m='1061390'>conditions,</span> <span
  m='1061960'>or</span> <span m='1062050'>the</span> <span
  m='1062170'>initial</span> <span m='1062500'>conditions.</span> </p><p><span
  m='1063970'>For</span> <span m='1064120'>example,</span> <span
  m='1064930'>let's</span> <span m='1065140'>see</span> <span
  m='1065350'>how</span> <span m='1065530'>this</span> <span
  m='1065740'>equation</span> <span m='1066550'>would</span> <span
  m='1066730'>work</span> <span m='1067990'>if</span> <span
  m='1068530'>we</span> <span m='1069550'>focused</span> <span
  m='1070060'>on</span> <span m='1070150'>the</span> <span
  m='1070240'>first</span> <span m='1070600'>order</span> <span
  m='1070870'>case.</span> <span m='1071950'>So</span> <span
  m='1072730'>the</span> <span m='1072850'>first</span> <span
  m='1073150'>order</span> <span m='1073360'>case,</span> <span
  m='1073750'>capital</span> <span m='1074260'>N</span> <span
  m='1074740'>is</span> <span m='1075190'>equal</span> <span
  m='1075550'>to</span> <span m='1075700'>1.</span> <span m='1077600'>We</span>
  <span m='1077650'>have</span> <span m='1077860'>the</span> <span
  m='1077980'>equation,</span> <span m='1078580'>y</span> <span
  m='1078850'>of</span> <span m='1078970'>n</span> <span
  m='1079150'>minus</span> <span m='1079600'>a,</span> <span m='1079880'>y
  of</span> <span m='1080160'>n</span> <span m='1080290'>minus</span> <span
  m='1080590'>1</span> <span m='1080740'>equals</span> <span
  m='1081040'>x</span> <span m='1081310'>of</span> <span m='1081470'>n.</span>
  <span m='1083110'>And</span> <span m='1083920'>let's</span> <span
  m='1084550'>find</span> <span m='1084940'>the</span> <span
  m='1085030'>unit</span> <span m='1085330'>sample</span> <span
  m='1085750'>response</span> <span m='1086560'>for</span> <span
  m='1086710'>the</span> <span m='1086800'>system--</span> <span
  m='1087950'>in</span> <span m='1088050'>other</span> <span
  m='1088120'>words,</span> <span m='1088510'>choosing</span> <span
  m='1088930'>x</span> <span m='1089140'>of</span> <span m='1089250'>n</span>
  <span m='1089410'>equal</span> <span m='1089680'>to</span> <span
  m='1090150'>a</span> <span m='1090210'>unit</span> <span
  m='1090550'>sample.</span> <span m='1092110'>And</span> <span
  m='1092440'>for</span> <span m='1092590'>the</span> <span
  m='1092710'>initial</span> <span m='1093070'>conditions,</span> <span
  m='1094340'>let's</span> <span m='1094570'>assume</span> <span
  m='1095590'>that,</span> <span m='1096070'>for</span> <span
  m='1096610'>a</span> <span m='1096700'>unit</span> <span
  m='1097030'>sample</span> <span m='1097480'>input,</span> <span
  m='1098560'>the</span> <span m='1098740'>output</span> <span
  m='1099460'>is</span> <span m='1099640'>equal</span> <span
  m='1099910'>to</span> <span m='1100030'>0</span> <span m='1100480'>for</span>
  <span m='1100690'>n</span> <span m='1100840'>less</span> <span
  m='1101080'>than</span> <span m='1101200'>0.</span> </p><p><span
  m='1102730'>Now,</span> <span m='1103150'>when</span> <span
  m='1103270'>we</span> <span m='1103360'>do</span> <span
  m='1103570'>that,</span> <span m='1104160'>we're</span> <span
  m='1104440'>making</span> <span m='1105730'>a</span> <span
  m='1105790'>specific</span> <span m='1106330'>assumption</span> <span
  m='1106780'>about</span> <span m='1107020'>causality--</span> <span
  m='1108250'>we're</span> <span m='1108400'>imposing</span> <span
  m='1109690'>the</span> <span m='1110350'>boundary</span> <span
  m='1110770'>conditions</span> <span m='1111850'>that</span> <span
  m='1112000'>the</span> <span m='1112120'>unit</span> <span
  m='1112420'>sample</span> <span m='1113020'>response</span> <span
  m='1113530'>has</span> <span m='1113770'>to</span> <span m='1113890'>be</span>
  <span m='1113980'>0</span> <span m='1114400'>for</span> <span
  m='1114580'>n</span> <span m='1114730'>less</span> <span
  m='1114940'>than</span> <span m='1115090'>0--</span> <span
  m='1115810'>that's</span> <span m='1115990'>exactly</span> <span
  m='1116470'>the</span> <span m='1116560'>necessary</span> <span
  m='1117070'>and</span> <span m='1117160'>sufficient</span> <span
  m='1117610'>condition</span> <span m='1118600'>that</span> <span
  m='1118870'>we</span> <span m='1118990'>need</span> <span
  m='1119200'>for</span> <span m='1119320'>causality.</span> <span
  m='1120410'>So</span> <span m='1120430'>basically,</span> <span
  m='1120910'>we're</span> <span m='1121030'>saying</span> <span
  m='1122140'>that</span> <span m='1122500'>we're</span> <span
  m='1122770'>imposing</span> <span m='1123850'>on</span> <span
  m='1124060'>the</span> <span m='1124150'>solution</span> <span
  m='1124570'>that</span> <span m='1124660'>we're</span> <span
  m='1124810'>about</span> <span m='1125050'>to</span> <span
  m='1125170'>generate,</span> <span m='1126100'>the</span> <span
  m='1126430'>additional</span> <span m='1127060'>condition</span> <span
  m='1127720'>of</span> <span m='1127870'>causality.</span> </p><p><span
  m='1129880'>All</span> <span m='1129900'>right,</span> <span
  m='1130710'>well</span> <span m='1131190'>now,</span> <span
  m='1132090'>rewriting</span> <span m='1132630'>this</span> <span
  m='1132810'>equation</span> <span m='1133440'>by</span> <span
  m='1133620'>taking</span> <span m='1134010'>this</span> <span
  m='1134190'>term</span> <span m='1134520'>over</span> <span
  m='1134760'>to</span> <span m='1134880'>the</span> <span
  m='1134970'>right</span> <span m='1135210'>hand</span> <span
  m='1135480'>side,</span> <span m='1135990'>and</span> <span
  m='1136110'>taking</span> <span m='1136470'>account</span> <span
  m='1136800'>of</span> <span m='1136920'>the</span> <span
  m='1137040'>fact</span> <span m='1137850'>that</span> <span
  m='1138180'>we're</span> <span m='1139050'>considering</span> <span
  m='1139530'>the</span> <span m='1139650'>input</span> <span
  m='1139980'>to</span> <span m='1140130'>be</span> <span m='1140280'>a</span>
  <span m='1140310'>unit</span> <span m='1140610'>sample,</span> <span
  m='1141660'>we</span> <span m='1141840'>have</span> <span
  m='1142680'>the</span> <span m='1142830'>output</span> <span
  m='1143220'>sequences</span> <span m='1144630'>unit</span> <span
  m='1144960'>sample</span> <span m='1145500'>plus</span> <span
  m='1145950'>a</span> <span m='1146190'>times</span> <span
  m='1147090'>the</span> <span m='1147210'>output</span> <span
  m='1147570'>sequence</span> <span m='1148050'>delayed.</span> <span
  m='1149100'>And</span> <span m='1149220'>now</span> <span
  m='1149790'>let's</span> <span m='1150630'>run</span> <span
  m='1151560'>through</span> <span m='1152190'>an</span> <span
  m='1152340'>iteration</span> <span m='1153510'>of</span> <span
  m='1153630'>this</span> <span m='1153840'>equation,</span> <span
  m='1154810'>obtaining</span> <span m='1155190'>some</span> <span
  m='1155400'>successive</span> <span m='1155940'>values.</span> </p><p><span
  m='1158070'>y</span> <span m='1159090'>of</span> <span
  m='1159150'>minus</span> <span m='1159540'>1 we</span> <span
  m='1159900'>can</span> <span m='1160080'>get</span> <span
  m='1160680'>simply</span> <span m='1161280'>by</span> <span
  m='1161760'>referring</span> <span m='1162270'>to</span> <span
  m='1162390'>the</span> <span m='1162480'>initial</span> <span
  m='1162810'>condition.</span> <span m='1164250'>We</span> <span
  m='1164700'>stated</span> <span m='1165210'>there</span> <span
  m='1165330'>y</span> <span m='1165600'>of n</span> <span m='1165730'>is</span>
  <span m='1165780'>0</span> <span m='1166110'>for</span> <span
  m='1166290'>n</span> <span m='1166380'>less</span> <span
  m='1166620'>than</span> <span m='1166770'>0,</span> <span m='1167400'>and
  so</span> <span m='1167580'>that</span> <span m='1167820'>means,</span> <span
  m='1168190'>of</span> <span m='1168290'>course,</span> <span
  m='1168610'>that</span> <span m='1168660'>y</span> <span m='1168900'>of</span>
  <span m='1169020'>minus</span> <span m='1169410'>1</span> <span
  m='1170670'>is</span> <span m='1170760'>0.</span> <span m='1173090'>y</span>
  <span m='1173360'>of</span> <span m='1173480'>0</span> <span
  m='1174260'>is</span> <span m='1174470'>equal</span> <span
  m='1174890'>to</span> <span m='1175430'>delta</span> <span
  m='1176030'>of</span> <span m='1176250'>0,</span> <span m='1176810'>but</span>
  <span m='1176930'>that's</span> <span m='1177170'>equal</span> <span
  m='1177440'>to</span> <span m='1177590'>1,</span> <span
  m='1178510'>plus</span> <span m='1178970'>a</span> <span
  m='1179210'>times</span> <span m='1179720'>y</span> <span
  m='1180050'>of</span> <span m='1180140'>minus</span> <span
  m='1180530'>1,</span> <span m='1180840'>which</span> <span
  m='1180920'>was</span> <span m='1181010'>0.</span> <span m='1182360'>So</span>
  <span m='1182900'>y</span> <span m='1183200'>of</span> <span
  m='1183330'>0</span> <span m='1184040'>is</span> <span
  m='1184190'>equal</span> <span m='1184490'>to</span> <span
  m='1184690'>1.</span> </p><p><span m='1186644'>y</span> <span
  m='1187620'>of</span> <span m='1187800'>1</span> <span m='1188310'>is</span>
  <span m='1188520'>equal</span> <span m='1188910'>to</span> <span
  m='1189150'>delta</span> <span m='1189570'>of</span> <span
  m='1189690'>1,</span> <span m='1190000'>which</span> <span
  m='1190080'>is</span> <span m='1190140'>0--</span> <span
  m='1190720'>the</span> <span m='1190820'>unit</span> <span
  m='1190920'>sample</span> <span m='1191490'>is</span> <span
  m='1191640'>only</span> <span m='1192180'>non-0</span> <span m='1192810'>at
  n</span> <span m='1193020'>equals</span> <span m='1193260'>0.</span> <span
  m='1194660'>So</span> <span m='1195240'>that</span> <span m='1195450'>0</span>
  <span m='1195930'>plus</span> <span m='1196230'>a</span> <span
  m='1196470'>times</span> <span m='1196800'>y</span> <span
  m='1197130'>of</span> <span m='1197220'>0--</span> <span m='1197940'>y
  of</span> <span m='1198320'>0</span> <span m='1198660'>is</span> <span
  m='1198780'>equal</span> <span m='1199020'>to</span> <span
  m='1199140'>1--</span> <span m='1199880'>so</span> <span m='1200155'>y
  of</span> <span m='1200850'>1</span> <span m='1201570'>is</span> <span
  m='1201750'>equal</span> <span m='1202080'>to</span> <span
  m='1202230'>a</span> <span m='1202500'>times</span> <span
  m='1202860'>1,</span> <span m='1203400'>or</span> <span m='1203760'>a.</span>
  <span m='1206090'>y</span> <span m='1206460'>of</span> <span
  m='1206580'>2,</span> <span m='1207040'>if</span> <span m='1207060'>we</span>
  <span m='1207210'>follow</span> <span m='1207570'>that</span> <span
  m='1207780'>through,</span> <span m='1208320'>is</span> <span
  m='1208500'>equal</span> <span m='1208920'>to</span> <span
  m='1209400'>a</span> <span m='1209610'>squared.</span> </p><p><span
  m='1211030'>And</span> <span m='1211170'>if</span> <span
  m='1211290'>you</span> <span m='1211410'>run</span> <span
  m='1211620'>through</span> <span m='1211830'>a</span> <span
  m='1211860'>few</span> <span m='1212070'>more</span> <span
  m='1212370'>of</span> <span m='1212460'>those,</span> <span
  m='1213100'>you'll</span> <span m='1213150'>see</span> <span
  m='1213450'>rather</span> <span m='1213780'>quickly</span> <span
  m='1214920'>that</span> <span m='1215790'>what</span> <span
  m='1216090'>we</span> <span m='1216240'>get</span> <span
  m='1216510'>for</span> <span m='1216660'>the</span> <span
  m='1216750'>unit</span> <span m='1217020'>sample</span> <span
  m='1217410'>response,</span> <span m='1220200'>imposing</span> <span
  m='1220780'>the</span> <span m='1220860'>condition</span> <span
  m='1221250'>of</span> <span m='1221340'>causality,</span> <span
  m='1222750'>is</span> <span m='1223410'>that</span> <span
  m='1223620'>the</span> <span m='1223710'>unit</span> <span
  m='1223950'>sample</span> <span m='1224370'>response</span> <span
  m='1225180'>is</span> <span m='1226180'>a</span> <span m='1226440'>to</span>
  <span m='1226620'>the</span> <span m='1226800'>N</span> <span
  m='1227490'>for</span> <span m='1227700'>n</span> <span
  m='1227850'>greater</span> <span m='1228240'>than</span> <span
  m='1228390'>0.</span> <span m='1229470'>Of</span> <span
  m='1229560'>course,</span> <span m='1229980'>it's</span> <span
  m='1230170'>0</span> <span m='1230580'>for</span> <span m='1230790'>n</span>
  <span m='1230910'>less</span> <span m='1231150'>than</span> <span
  m='1231330'>0,</span> <span m='1231720'>because</span> <span
  m='1232080'>of</span> <span m='1232200'>our</span> <span
  m='1232320'>initial</span> <span m='1232680'>condition.</span> <span
  m='1233800'>So</span> <span m='1234270'>it's</span> <span m='1234480'>a</span>
  <span m='1234660'>to</span> <span m='1234990'>N</span> <span
  m='1235800'>times</span> <span m='1237270'>u of</span> <span
  m='1237480'>n.</span> </p><p><span m='1239220'>And</span> <span
  m='1240240'>it's</span> <span m='1240390'>obviously</span> <span
  m='1240870'>causal,</span> <span m='1241350'>because</span> <span
  m='1241680'>that's</span> <span m='1241860'>what</span> <span
  m='1241950'>we</span> <span m='1242100'>imposed.</span> <span
  m='1243630'>It</span> <span m='1244290'>may</span> <span m='1244500'>or</span>
  <span m='1244560'>may</span> <span m='1244710'>not</span> <span
  m='1244920'>be</span> <span m='1245070'>stable,</span> <span
  m='1245460'>depending</span> <span m='1245910'>on</span> <span
  m='1246030'>the</span> <span m='1246120'>value</span> <span
  m='1246570'>of</span> <span m='1246670'>a.</span> <span m='1247360'>In</span>
  <span m='1247530'>particular,</span> <span m='1248440'>if</span> <span
  m='1248520'>the</span> <span m='1248610'>magnitude</span> <span
  m='1249210'>of</span> <span m='1249330'>a</span> <span m='1249870'>is</span>
  <span m='1250710'>less</span> <span m='1251040'>than</span> <span
  m='1251220'>1,</span> <span m='1252850'>then</span> <span
  m='1253440'>this</span> <span m='1253620'>sequence</span> <span
  m='1254130'>will</span> <span m='1254250'>be</span> <span
  m='1254400'>decaying</span> <span m='1255330'>exponentially</span> <span
  m='1256200'>as</span> <span m='1256320'>n</span> <span
  m='1256500'>increases.</span> <span m='1257890'>So</span> <span
  m='1258180'>for</span> <span m='1258300'>the</span> <span
  m='1258420'>magnitude</span> <span m='1258930'>of</span> <span
  m='1259050'>a</span> <span m='1259440'>less</span> <span
  m='1259740'>than</span> <span m='1259920'>1,</span> <span
  m='1260850'>this</span> <span m='1261030'>corresponds</span> <span
  m='1262020'>to</span> <span m='1263250'>a</span> <span
  m='1263310'>stable</span> <span m='1263790'>system.</span> </p><p><span
  m='1266590'>Now</span> <span m='1266740'>this</span> <span
  m='1267220'>isn't</span> <span m='1267910'>the</span> <span
  m='1268060'>only</span> <span m='1268630'>initial</span> <span
  m='1268990'>condition</span> <span m='1269920'>that</span> <span
  m='1270670'>we</span> <span m='1270910'>can</span> <span
  m='1271300'>impose</span> <span m='1272050'>on</span> <span
  m='1272230'>the</span> <span m='1272320'>system</span> <span
  m='1273640'>and</span> <span m='1274360'>still</span> <span
  m='1274750'>have</span> <span m='1274930'>it</span> <span
  m='1275020'>correspond</span> <span m='1275650'>to</span> <span
  m='1275770'>a</span> <span m='1275830'>linear</span> <span
  m='1276250'>shift</span> <span m='1276680'>invariant</span> <span
  m='1277180'>system.</span> <span m='1278500'>We</span> <span
  m='1278620'>could,</span> <span m='1278830'>alternatively,</span> <span
  m='1279880'>impose</span> <span m='1280660'>a</span> <span
  m='1280720'>different</span> <span m='1281260'>set</span> <span
  m='1281560'>of</span> <span m='1281680'>initial</span> <span
  m='1282040'>conditions,</span> <span m='1283310'>which</span> <span
  m='1283750'>is</span> <span m='1284500'>the--</span> <span
  m='1285310'>or</span> <span m='1285580'>boundary</span> <span
  m='1285970'>conditions,</span> <span m='1286450'>really,</span> <span
  m='1286720'>because</span> <span m='1287030'>they're</span> <span
  m='1287110'>not,</span> <span m='1288010'>for</span> <span
  m='1288190'>this</span> <span m='1288370'>case,</span> <span
  m='1288640'>initial</span> <span m='1289000'>conditions--</span> <span
  m='1290140'>boundary</span> <span m='1290530'>conditions</span> <span
  m='1291550'>that</span> <span m='1292300'>state</span> <span
  m='1292900'>instead</span> <span m='1293500'>of</span> <span
  m='1294280'>the</span> <span m='1294370'>statement</span> <span
  m='1294760'>that</span> <span m='1294880'>the</span> <span
  m='1294970'>system</span> <span m='1295330'>is</span> <span
  m='1295450'>causal,</span> <span m='1296470'>the</span> <span
  m='1296620'>statement</span> <span m='1297070'>that</span> <span
  m='1297220'>the</span> <span m='1297310'>system</span> <span
  m='1297730'>is</span> <span m='1297880'>totally</span> <span
  m='1298300'>non-causal.</span> </p><p><span m='1299890'>What</span> <span
  m='1300040'>I</span> <span m='1300100'>mean</span> <span
  m='1300430'>is,</span> <span m='1301120'>let's</span> <span
  m='1301600'>take</span> <span m='1301840'>the</span> <span
  m='1301970'>same</span> <span m='1302320'>example--</span> <span
  m='1302890'>the</span> <span m='1302980'>same</span> <span
  m='1303250'>difference</span> <span m='1303670'>equation--</span> <span
  m='1305830'>let's</span> <span m='1306520'>again</span> <span
  m='1307360'>choose</span> <span m='1307660'>the</span> <span
  m='1307810'>input</span> <span m='1308140'>to</span> <span
  m='1308260'>be</span> <span m='1308410'>a</span> <span m='1308440'>unit</span>
  <span m='1308770'>sample,</span> <span m='1310360'>but</span> <span
  m='1310540'>let's</span> <span m='1310870'>impose</span> <span
  m='1311740'>another</span> <span m='1312520'>condition</span> <span
  m='1313990'>on</span> <span m='1314770'>the</span> <span
  m='1316030'>solution,</span> <span m='1317140'>boundary</span> <span
  m='1317530'>condition.</span> <span m='1318580'>Namely</span> <span
  m='1319120'>that</span> <span m='1319690'>the</span> <span
  m='1319780'>unit</span> <span m='1320110'>sample</span> <span
  m='1320530'>response</span> <span m='1321160'>is</span> <span
  m='1321340'>0</span> <span m='1322300'>for</span> <span m='1322480'>n</span>
  <span m='1322660'>greater</span> <span m='1323110'>than</span> <span
  m='1323290'>0,</span> <span m='1324220'>rather</span> <span
  m='1324550'>than</span> <span m='1324700'>the</span> <span
  m='1324820'>boundary</span> <span m='1325180'>condition</span> <span
  m='1325660'>that</span> <span m='1325780'>says</span> <span
  m='1326380'>that</span> <span m='1327060'>it's</span> <span
  m='1327440'>0</span> <span m='1327880'>for</span> <span m='1328120'>n</span>
  <span m='1328300'>less</span> <span m='1328540'>than</span> <span
  m='1328720'>0.</span> </p><p><span m='1330750'>In</span> <span
  m='1330870'>that</span> <span m='1331020'>case,</span> <span
  m='1331680'>it's</span> <span m='1332130'>convenient</span> <span
  m='1333150'>to</span> <span m='1333480'>generate</span> <span
  m='1334230'>the</span> <span m='1334410'>solution</span> <span
  m='1334950'>iteratively</span> <span m='1336030'>by</span> <span
  m='1336210'>running</span> <span m='1336750'>the</span> <span
  m='1336990'>difference</span> <span m='1337410'>equation</span> <span
  m='1338790'>backwards,</span> <span m='1339450'>in</span> <span
  m='1339540'>other</span> <span m='1339720'>words,</span> <span
  m='1340090'>by</span> <span m='1340200'>expressing</span> <span m='1341340'>y
  of</span> <span m='1341670'>n</span> <span m='1341940'>minus</span> <span
  m='1342390'>1,</span> <span m='1343270'>in</span> <span
  m='1343710'>terms</span> <span m='1344100'>of</span> <span
  m='1344220'>y</span> <span m='1344520'>of</span> <span m='1344640'>n</span>
  <span m='1345100'>and x of n--</span> <span m='1346050'>this</span> <span
  m='1346230'>is</span> <span m='1346320'>just</span> <span
  m='1346500'>simply</span> <span m='1346950'>another</span> <span
  m='1347250'>rearrangement</span> <span m='1348000'>of</span> <span
  m='1348090'>the</span> <span m='1348180'>difference</span> <span
  m='1348570'>equation.</span> <span m='1350260'>And</span> <span
  m='1350910'>with</span> <span m='1351090'>this</span> <span
  m='1351330'>initial</span> <span m='1351720'>condition,</span> <span
  m='1353520'>if</span> <span m='1354030'>we</span> <span
  m='1355110'>look</span> <span m='1355320'>at</span> <span m='1355410'>y</span>
  <span m='1355710'>of</span> <span m='1355860'>1--</span> <span
  m='1356580'>of</span> <span m='1356700'>course,</span> <span
  m='1357000'>y</span> <span m='1357270'>of</span> <span m='1357390'>1</span>
  <span m='1357570'>is</span> <span m='1357690'>equal</span> <span
  m='1357930'>to</span> <span m='1358080'>0</span> <span m='1358500'>by</span>
  <span m='1358680'>virtue</span> <span m='1359280'>of</span> <span
  m='1359400'>the</span> <span m='1359760'>boundary</span> <span
  m='1360210'>condition</span> <span m='1360960'>that</span> <span
  m='1361080'>we've</span> <span m='1361320'>imposed,</span> <span
  m='1362430'>so</span> <span m='1362700'>this</span> <span
  m='1362940'>is</span> <span m='1363060'>equal</span> <span
  m='1363330'>to</span> <span m='1363450'>0--</span> <span m='1365130'>y</span>
  <span m='1365430'>of</span> <span m='1365580'>0</span> <span
  m='1366270'>corresponds</span> <span m='1366990'>to</span> <span
  m='1367080'>n</span> <span m='1367240'>equal</span> <span
  m='1367560'>to</span> <span m='1367710'>1</span> <span m='1368010'>in</span>
  <span m='1368100'>this</span> <span m='1368280'>equation.</span> <span
  m='1369790'>So</span> <span m='1369810'>n</span> <span
  m='1369930'>equal</span> <span m='1370260'>to</span> <span
  m='1370410'>1</span> <span m='1370800'>here,</span> <span
  m='1373050'>we</span> <span m='1373200'>have</span> <span m='1373740'>1</span>
  <span m='1373950'>over</span> <span m='1374250'>a</span> <span
  m='1374490'>times</span> <span m='1374880'>y</span> <span
  m='1375330'>of</span> <span m='1375450'>1,</span> <span
  m='1375850'>which</span> <span m='1375930'>is</span> <span
  m='1375990'>0</span> <span m='1376470'>minus</span> <span
  m='1376860'>delta</span> <span m='1377210'>of</span> <span
  m='1377340'>1</span> <span m='1377550'>which</span> <span
  m='1377730'>is</span> <span m='1377790'>0.</span> <span m='1378690'>So</span>
  <span m='1378840'>y</span> <span m='1379080'>of</span> <span
  m='1379230'>0</span> <span m='1379680'>is</span> <span
  m='1379800'>again</span> <span m='1380070'>equal</span> <span
  m='1380340'>to</span> <span m='1380460'>0.</span> </p><p><span
  m='1381970'>y</span> <span m='1382610'>of</span> <span
  m='1382710'>minus</span> <span m='1383160'>1</span> <span
  m='1383400'>corresponds</span> <span m='1384060'>to</span> <span
  m='1384150'>n</span> <span m='1384330'>equal</span> <span
  m='1384570'>to</span> <span m='1384720'>0,</span> <span m='1387030'>so</span>
  <span m='1387300'>we</span> <span m='1387480'>have</span> <span
  m='1388110'>1</span> <span m='1388350'>over</span> <span m='1388620'>a</span>
  <span m='1388860'>times</span> <span m='1389190'>y</span> <span
  m='1389430'>of</span> <span m='1389550'>0,</span> <span
  m='1389940'>which</span> <span m='1390120'>was</span> <span
  m='1390240'>0,</span> <span m='1391140'>minus</span> <span
  m='1391680'>delta</span> <span m='1392130'>of 0,</span> <span
  m='1392650'>which</span> <span m='1392760'>is</span> <span
  m='1392880'>1.</span> <span m='1393790'>So</span> <span m='1393930'>we</span>
  <span m='1394080'>get</span> <span m='1394440'>minus</span> <span
  m='1395600'>a</span> <span m='1396000'>minus</span> <span m='1396470'>to the
  minus</span> <span m='1396930'>1.</span> <span m='1398980'>y of</span> <span
  m='1399070'>minus</span> <span m='1399440'>2,</span> <span
  m='1399770'>we</span> <span m='1399920'>would</span> <span
  m='1400030'>substitute</span> <span m='1400740'>n</span> <span
  m='1400990'>equals</span> <span m='1401170'>minus</span> <span
  m='1401590'>1.</span> <span m='1402736'>y</span> <span m='1403120'>of</span>
  <span m='1403210'>minus</span> <span m='1403660'>1 we</span> <span
  m='1404080'>had</span> <span m='1404340'>as</span> <span
  m='1404470'>minus</span> <span m='1405130'>a</span> <span
  m='1405300'>to</span> <span m='1405360'>the</span> <span
  m='1405490'>minus</span> <span m='1405960'>1.</span> <span
  m='1408430'>And</span> <span m='1409150'>delta</span> <span
  m='1409660'>of</span> <span m='1409810'>minus</span> <span
  m='1410230'>1</span> <span m='1410440'>is</span> <span m='1410500'>0,</span>
  <span m='1411700'>so</span> <span m='1412030'>we</span> <span
  m='1412240'>have</span> <span m='1412600'>here</span> <span
  m='1412960'>minus</span> <span m='1413500'>a</span> <span m='1413980'>to
  the</span> <span m='1414310'>minus</span> <span m='1414810'>2,</span> <span
  m='1415690'>and</span> <span m='1416350'>it</span> <span
  m='1416710'>continues</span> <span m='1417340'>on</span> <span
  m='1418240'>that</span> <span m='1418510'>way.</span> </p><p><span
  m='1419530'>And</span> <span m='1419890'>if</span> <span
  m='1420010'>you</span> <span m='1420100'>generated</span> <span
  m='1420730'>some</span> <span m='1421060'>more</span> <span
  m='1421300'>of</span> <span m='1421420'>these,</span> <span
  m='1421780'>what</span> <span m='1421960'>you'd</span> <span
  m='1422070'>see</span> <span m='1422260'>rather</span> <span
  m='1422560'>quickly</span> <span m='1423190'>is</span> <span
  m='1423460'>that</span> <span m='1424060'>this</span> <span
  m='1424270'>is</span> <span m='1424420'>of</span> <span m='1424540'>the</span>
  <span m='1424660'>form</span> <span m='1424990'>minus</span> <span
  m='1426250'>a</span> <span m='1426550'>to</span> <span m='1426700'>the</span>
  <span m='1426880'>n</span> <span m='1427960'>times</span> <span
  m='1428740'>u</span> <span m='1429220'>of</span> <span
  m='1429790'>minus</span> <span m='1430240'>n</span> <span
  m='1430450'>minus</span> <span m='1430900'>1.</span> <span
  m='1431480'>In</span> <span m='1431500'>other</span> <span
  m='1431680'>words,</span> <span m='1433220'>it</span> <span
  m='1433450'>is</span> <span m='1433780'>an</span> <span
  m='1433870'>exponential</span> <span m='1434530'>to</span> <span
  m='1434650'>form</span> <span m='1435090'>a</span> <span m='1435190'>to
  the</span> <span m='1435370'>n,</span> <span m='1436150'>as</span> <span
  m='1436300'>we</span> <span m='1436420'>found</span> <span
  m='1437110'>for</span> <span m='1437260'>the</span> <span
  m='1437470'>causal</span> <span m='1438040'>solution,</span> <span
  m='1438520'>also.</span> <span m='1439600'>But</span> <span
  m='1439960'>it's</span> <span m='1440170'>0</span> <span
  m='1440560'>for</span> <span m='1440770'>n</span> <span
  m='1440920'>greater</span> <span m='1441250'>than</span> <span
  m='1441430'>0,</span> <span m='1442060'>and</span> <span
  m='1442330'>it's</span> <span m='1442450'>of</span> <span
  m='1442540'>the</span> <span m='1442630'>form</span> <span
  m='1442960'>a</span> <span m='1443140'>to</span> <span m='1443230'>the</span>
  <span m='1443410'>n</span> <span m='1443830'>for</span> <span
  m='1444010'>n</span> <span m='1444190'>less</span> <span
  m='1444460'>than</span> <span m='1444610'>0.</span> </p><p><span
  m='1445600'>What</span> <span m='1445780'>that</span> <span
  m='1445990'>means,</span> <span m='1446500'>in</span> <span
  m='1446620'>particular,</span> <span m='1447160'>is</span> <span
  m='1447280'>that</span> <span m='1447430'>if</span> <span
  m='1447580'>we</span> <span m='1447880'>again</span> <span
  m='1449140'>inquired</span> <span m='1449920'>as</span> <span
  m='1450100'>to</span> <span m='1450220'>whether</span> <span
  m='1450490'>it</span> <span m='1450550'>was</span> <span
  m='1450700'>stable</span> <span m='1451150'>or</span> <span
  m='1451300'>unstable,</span> <span m='1452140'>for</span> <span
  m='1452290'>the</span> <span m='1452380'>magnitude</span> <span
  m='1452890'>of</span> <span m='1453010'>a</span> <span m='1453850'>less</span>
  <span m='1454120'>than</span> <span m='1454330'>1,</span> <span
  m='1455160'>what</span> <span m='1455320'>we</span> <span
  m='1455560'>would</span> <span m='1455680'>find,</span> <span
  m='1456280'>in</span> <span m='1456430'>this</span> <span
  m='1456640'>case,</span> <span m='1457330'>is</span> <span
  m='1457540'>that</span> <span m='1457900'>it's</span> <span
  m='1458080'>unstable</span> <span m='1459430'>rather</span> <span
  m='1459760'>than</span> <span m='1459940'>stable.</span> </p><p><span
  m='1462530'>So</span> <span m='1463340'>what</span> <span
  m='1463550'>we've</span> <span m='1463730'>seen,</span> <span
  m='1464060'>then,</span> <span m='1464450'>is</span> <span
  m='1464660'>that</span> <span m='1465110'>a</span> <span
  m='1465380'>linear</span> <span m='1465710'>constant</span> <span
  m='1466130'>coefficient</span> <span m='1466760'>difference</span> <span
  m='1467120'>equation,</span> <span m='1468920'>by</span> <span
  m='1469160'>itself,</span> <span m='1469940'>doesn't</span> <span
  m='1470270'>specify</span> <span m='1471170'>uniquely</span> <span
  m='1471740'>a</span> <span m='1471800'>system--</span> <span
  m='1472670'>it</span> <span m='1472880'>requires</span> <span
  m='1473390'>a</span> <span m='1473450'>set</span> <span m='1473660'>of</span>
  <span m='1473750'>initial</span> <span m='1474050'>conditions.</span> <span
  m='1476810'>And</span> <span m='1477440'>depending</span> <span
  m='1477920'>on</span> <span m='1478040'>the</span> <span
  m='1478490'>initial</span> <span m='1478850'>conditions</span> <span
  m='1479300'>or</span> <span m='1479360'>boundary</span> <span
  m='1479780'>conditions</span> <span m='1480230'>that</span> <span
  m='1480350'>are</span> <span m='1480470'>imposed,</span> <span
  m='1481520'>it</span> <span m='1481700'>may</span> <span
  m='1482450'>correspond</span> <span m='1482960'>to</span> <span
  m='1483080'>a</span> <span m='1483140'>causal</span> <span
  m='1483590'>system,</span> <span m='1484040'>or</span> <span
  m='1484190'>it</span> <span m='1484250'>may</span> <span
  m='1484430'>correspond</span> <span m='1485030'>to</span> <span
  m='1485150'>a</span> <span m='1485210'>non-causal</span> <span
  m='1485870'>system.</span> <span m='1486920'>And</span> <span
  m='1488180'>in</span> <span m='1488540'>some</span> <span
  m='1488810'>situations,</span> <span m='1489840'>we</span> <span
  m='1489920'>might</span> <span m='1490190'>want</span> <span
  m='1490400'>it</span> <span m='1490490'>to</span> <span
  m='1490610'>correspond</span> <span m='1491270'>to</span> <span
  m='1491510'>either</span> <span m='1491840'>one</span> <span
  m='1492050'>of</span> <span m='1492170'>those</span> <span
  m='1492480'>two.</span> </p><p><span m='1494530'>Something</span> <span
  m='1495220'>that</span> <span m='1495820'>I</span> <span
  m='1496300'>haven't</span> <span m='1496630'>stated</span> <span
  m='1497110'>explicitly,</span> <span m='1497890'>but</span> <span
  m='1498340'>there</span> <span m='1498730'>is</span> <span
  m='1499030'>some</span> <span m='1499210'>discussion</span> <span
  m='1499780'>of</span> <span m='1499900'>this</span> <span
  m='1500320'>in</span> <span m='1500440'>the</span> <span
  m='1500530'>text,</span> <span m='1502180'>is</span> <span
  m='1502510'>the</span> <span m='1502630'>fact</span> <span
  m='1503530'>that</span> <span m='1505400'>it</span> <span
  m='1505550'>is</span> <span m='1505700'>not</span> <span
  m='1506240'>for</span> <span m='1506720'>every</span> <span
  m='1507140'>set</span> <span m='1507380'>of</span> <span
  m='1507470'>boundary</span> <span m='1507890'>conditions</span> <span
  m='1508850'>that</span> <span m='1509210'>a</span> <span
  m='1509450'>linear</span> <span m='1509750'>constant</span> <span
  m='1510200'>coefficient</span> <span m='1510830'>difference</span> <span
  m='1511190'>equation</span> <span m='1512420'>corresponds</span> <span
  m='1513380'>to</span> <span m='1513740'>a</span> <span
  m='1513800'>linear</span> <span m='1514160'>shift</span> <span
  m='1514540'>invariant</span> <span m='1515030'>system,</span> <span
  m='1516200'>but</span> <span m='1516860'>it</span> <span m='1516980'>does
  in</span> <span m='1517340'>particular</span> <span m='1518240'>for</span>
  <span m='1519500'>the</span> <span m='1520160'>two</span> <span
  m='1520310'>sets</span> <span m='1520610'>of</span> <span
  m='1520670'>boundary</span> <span m='1521000'>conditions</span> <span
  m='1521540'>that</span> <span m='1521660'>are</span> <span
  m='1521760'>imposed</span> <span m='1522290'>here.</span> </p><p><span
  m='1522980'>More</span> <span m='1523160'>generally,</span> <span
  m='1523700'>what's</span> <span m='1523910'>required</span> <span
  m='1524450'>of</span> <span m='1524540'>the</span> <span
  m='1524630'>boundary</span> <span m='1525020'>conditions,</span> <span
  m='1526090'>so</span> <span m='1526280'>that</span> <span
  m='1526460'>the</span> <span m='1526550'>difference</span> <span
  m='1526970'>equation</span> <span m='1527960'>corresponds</span> <span
  m='1528590'>to</span> <span m='1528680'>a</span> <span
  m='1528740'>linear</span> <span m='1529070'>shift</span> <span
  m='1529340'>invariant</span> <span m='1529860'>system,</span> <span
  m='1530870'>is</span> <span m='1531050'>that</span> <span
  m='1531740'>the</span> <span m='1531830'>boundary</span> <span
  m='1532190'>conditions</span> <span m='1532700'>have</span> <span
  m='1533060'>to</span> <span m='1533810'>be</span> <span
  m='1533990'>consistent</span> <span m='1534710'>with</span> <span
  m='1534950'>the</span> <span m='1535040'>statement</span> <span
  m='1536330'>that</span> <span m='1536600'>if</span> <span
  m='1536870'>the</span> <span m='1537050'>input,</span> <span
  m='1538190'>x</span> <span m='1538430'>of</span> <span m='1538550'>n</span>
  <span m='1538910'>were</span> <span m='1539120'>0,</span> <span
  m='1542120'>0</span> <span m='1542480'>for</span> <span m='1542660'>all</span>
  <span m='1542930'>n,</span> <span m='1543680'>that</span> <span
  m='1544100'>the</span> <span m='1544280'>output</span> <span
  m='1544790'>would</span> <span m='1544970'>also</span> <span
  m='1545330'>be</span> <span m='1545480'>0</span> <span m='1545810'>for</span>
  <span m='1545990'>all</span> <span m='1546270'>n.</span> <span
  m='1546600'>And</span> <span m='1546750'>there</span> <span
  m='1546830'>is</span> <span m='1546920'>some</span> <span
  m='1547280'>additional</span> <span m='1547700'>discussion</span> <span
  m='1548210'>of</span> <span m='1548300'>this</span> <span
  m='1548780'>in</span> <span m='1548870'>the</span> <span
  m='1548960'>text.</span> </p><p><span m='1549860'>I</span> <span
  m='1551000'>indicate</span> <span m='1551420'>also</span> <span
  m='1551810'>that</span> <span m='1551990'>we'll</span> <span
  m='1552260'>be</span> <span m='1553220'>returning</span> <span
  m='1553910'>from</span> <span m='1554210'>time</span> <span
  m='1554540'>to</span> <span m='1554660'>time</span> <span
  m='1556040'>to</span> <span m='1556880'>further</span> <span
  m='1557240'>discussion</span> <span m='1557930'>of</span> <span
  m='1558140'>linear</span> <span m='1558410'>constant</span> <span
  m='1558830'>coefficient</span> <span m='1559400'>difference</span> <span
  m='1559730'>equations,</span> <span m='1560640'>and</span> <span
  m='1561440'>discussing,</span> <span m='1561920'>in</span> <span
  m='1562010'>particular,</span> <span m='1562550'>other</span> <span
  m='1562820'>ways</span> <span m='1563420'>of</span> <span
  m='1564230'>solving</span> <span m='1565400'>this</span> <span
  m='1565610'>class</span> <span m='1565940'>of</span> <span
  m='1566030'>equations.</span> </p><p><span m='1568310'>For</span> <span
  m='1568400'>the</span> <span m='1568490'>remainder</span> <span
  m='1569210'>of</span> <span m='1569630'>the</span> <span
  m='1570020'>lecture,</span> <span m='1570680'>I'd</span> <span
  m='1570890'>like</span> <span m='1571430'>to</span> <span
  m='1571820'>focus</span> <span m='1572360'>on</span> <span
  m='1573530'>an</span> <span m='1573740'>alternative</span> <span
  m='1574640'>representation</span> <span m='1575840'>of</span> <span
  m='1576050'>linear</span> <span m='1576350'>shift</span> <span
  m='1576650'>invariant</span> <span m='1577190'>systems,</span> <span
  m='1578180'>alternative</span> <span m='1579260'>to</span> <span
  m='1580220'>the</span> <span m='1580850'>time</span> <span
  m='1581210'>domain,</span> <span m='1581900'>or</span> <span
  m='1582080'>convolution</span> <span m='1582830'>sum</span> <span
  m='1583430'>representation,</span> <span m='1584610'>that</span> <span
  m='1585350'>we</span> <span m='1585500'>dealt</span> <span
  m='1585800'>with</span> <span m='1586370'>in</span> <span
  m='1586910'>the</span> <span m='1587030'>last</span> <span
  m='1587390'>lecture.</span> <span m='1588350'>In</span> <span
  m='1588440'>particular,</span> <span m='1589280'>the</span> <span
  m='1590270'>very</span> <span m='1590510'>useful</span> <span
  m='1590990'>alternative</span> <span m='1591890'>is</span> <span
  m='1592370'>a</span> <span m='1592520'>description</span> <span
  m='1593270'>of</span> <span m='1593420'>linear</span> <span
  m='1593720'>shift</span> <span m='1594020'>invariant</span> <span
  m='1594530'>systems</span> <span m='1595580'>in</span> <span
  m='1595730'>terms</span> <span m='1596330'>of</span> <span
  m='1597080'>its</span> <span m='1597230'>frequency</span> <span
  m='1597800'>response.</span> <span m='1598850'>In</span> <span
  m='1598940'>other</span> <span m='1599120'>words,</span> <span
  m='1599520'>in</span> <span m='1599620'>terms</span> <span
  m='1599840'>of</span> <span m='1599930'>its</span> <span
  m='1600080'>response</span> <span m='1600710'>either</span> <span
  m='1601130'>to</span> <span m='1601430'>sinusoidal</span> <span
  m='1602150'>excitations,</span> <span m='1603530'>or</span> <span
  m='1603890'>to</span> <span m='1604370'>complex</span> <span
  m='1604940'>exponential</span> <span m='1605590'>excitations.</span>
  </p><p><span m='1608330'>Well,</span> <span m='1608990'>the</span> <span
  m='1609470'>basic</span> <span m='1610940'>notion</span> <span
  m='1612170'>behind</span> <span m='1613040'>the</span> <span
  m='1613520'>frequency</span> <span m='1614060'>response</span> <span
  m='1614720'>description</span> <span m='1615680'>of</span> <span
  m='1616100'>linear</span> <span m='1616430'>shift</span> <span
  m='1616760'>invariant</span> <span m='1617270'>systems</span> <span
  m='1618740'>is</span> <span m='1619220'>the</span> <span
  m='1619340'>fact</span> <span m='1620120'>that</span> <span
  m='1621870'>complex</span> <span m='1622500'>exponentials</span> <span
  m='1623670'>are</span> <span m='1624030'>eigenfunctions</span> <span
  m='1625380'>of</span> <span m='1625920'>linear</span> <span
  m='1626250'>shift</span> <span m='1626550'>invariant</span> <span
  m='1627110'>systems.</span> <span m='1627930'>What</span> <span
  m='1628050'>I</span> <span m='1628140'>mean</span> <span m='1628410'>by</span>
  <span m='1628590'>that</span> <span m='1629010'>is</span> <span
  m='1629310'>that</span> <span m='1629910'>for</span> <span
  m='1630030'>linear</span> <span m='1630330'>shift</span> <span
  m='1630630'>invariant</span> <span m='1631050'>systems,</span> <span
  m='1631980'>if</span> <span m='1632100'>you</span> <span
  m='1632220'>put</span> <span m='1632480'>in</span> <span m='1632610'>a</span>
  <span m='1632670'>complex</span> <span m='1633210'>exponential,</span> <span
  m='1634350'>you</span> <span m='1634470'>get</span> <span
  m='1634710'>out</span> <span m='1634910'>a</span> <span
  m='1634980'>complex</span> <span m='1635550'>exponential.</span> <span
  m='1637230'>And</span> <span m='1638370'>the</span> <span
  m='1638640'>only</span> <span m='1638910'>change</span> <span
  m='1639660'>is</span> <span m='1640140'>in</span> <span m='1640290'>the</span>
  <span m='1640380'>complex</span> <span m='1640950'>amplitude</span> <span
  m='1641970'>of</span> <span m='1642270'>the</span> <span
  m='1642360'>complex</span> <span m='1642870'>exponential--</span> <span
  m='1643440'>the</span> <span m='1643530'>functional</span> <span
  m='1643950'>form</span> <span m='1645030'>is</span> <span
  m='1645180'>the</span> <span m='1645300'>same,</span> <span
  m='1645990'>so</span> <span m='1646170'>complex</span> <span
  m='1646680'>exponential</span> <span m='1647280'>in</span> <span
  m='1647400'>gives</span> <span m='1647610'>you</span> <span
  m='1647730'>a</span> <span m='1647760'>complex</span> <span
  m='1648270'>exponential</span> <span m='1648960'>out.</span> </p><p><span
  m='1650370'>We</span> <span m='1650490'>can</span> <span
  m='1650670'>see</span> <span m='1650880'>that</span> <span
  m='1652110'>rather</span> <span m='1652440'>easily</span> <span
  m='1653580'>by</span> <span m='1654180'>referring</span> <span
  m='1654750'>to</span> <span m='1654870'>the</span> <span
  m='1654960'>convolution</span> <span m='1655980'>sum</span> <span
  m='1656760'>description</span> <span m='1657570'>of</span> <span
  m='1658740'>linear</span> <span m='1659070'>shift</span> <span
  m='1659370'>invariant</span> <span m='1659880'>systems,</span> <span
  m='1660480'>as</span> <span m='1660630'>I've</span> <span
  m='1660780'>indicated</span> <span m='1661350'>here.</span> <span
  m='1662280'>In</span> <span m='1662400'>particular,</span> <span
  m='1663460'>suppose</span> <span m='1663870'>that</span> <span
  m='1663990'>we</span> <span m='1664140'>choose</span> <span
  m='1665100'>an</span> <span m='1665190'>input</span> <span
  m='1665550'>sequence</span> <span m='1666390'>which</span> <span
  m='1666660'>is</span> <span m='1667140'>a</span> <span
  m='1667440'>complex</span> <span m='1668010'>exponential.</span> <span
  m='1670370'>And</span> <span m='1671010'>let's</span> <span
  m='1671250'>substitute</span> <span m='1672240'>this</span> <span
  m='1672810'>into</span> <span m='1673110'>this</span> <span
  m='1673320'>expression,</span> <span m='1674650'>so</span> <span
  m='1674790'>that</span> <span m='1675270'>the</span> <span
  m='1675420'>output</span> <span m='1675960'>is</span> <span
  m='1676200'>then</span> <span m='1676500'>the</span> <span
  m='1676590'>sum</span> <span m='1677070'>of</span> <span m='1677340'>h</span>
  <span m='1677610'>of</span> <span m='1677750'>k</span> <span
  m='1678500'>e</span> <span m='1678700'>to</span> <span m='1678810'>the</span>
  <span m='1678900'>j</span> <span m='1679110'>omega</span> <span
  m='1679700'>n</span> <span m='1679940'>minus</span> <span
  m='1680370'>k.</span> </p><p><span m='1682140'>This</span> <span
  m='1682380'>term</span> <span m='1684570'>can</span> <span
  m='1684990'>be</span> <span m='1685230'>decomposed</span> <span
  m='1685950'>into</span> <span m='1686190'>a</span> <span
  m='1686250'>product</span> <span m='1686910'>of</span> <span
  m='1687060'>two</span> <span m='1687270'>exponentials,</span> <span
  m='1689050'>e</span> <span m='1689380'>to</span> <span m='1689490'>the</span>
  <span m='1689610'>j</span> <span m='1690510'>omega</span> <span
  m='1691190'>n,</span> <span m='1692840'>and</span> <span m='1693140'>e</span>
  <span m='1693390'>to</span> <span m='1693540'>the</span> <span
  m='1693660'>minus j</span> <span m='1694110'>omega</span> <span
  m='1695770'>k.</span> <span m='1697920'>And</span> <span
  m='1698490'>since</span> <span m='1698820'>e</span> <span
  m='1698940'>to</span> <span m='1699000'>the</span> <span m='1699090'>j
  omega</span> <span m='1699690'>n</span> <span m='1700440'>doesn't</span> <span
  m='1700830'>depend</span> <span m='1701220'>on</span> <span
  m='1701340'>the</span> <span m='1701460'>index</span> <span
  m='1701880'>k,</span> <span m='1702960'>we</span> <span m='1703170'>can</span>
  <span m='1703740'>take</span> <span m='1704100'>that</span> <span
  m='1704430'>piece</span> <span m='1705720'>outside</span> <span
  m='1706350'>the</span> <span m='1706460'>sum,</span> <span
  m='1708450'>and</span> <span m='1708990'>what</span> <span
  m='1709260'>we're</span> <span m='1709410'>left</span> <span
  m='1709710'>with</span> <span m='1710100'>is</span> <span m='1710400'>y</span>
  <span m='1710720'>of</span> <span m='1710850'>n</span> <span
  m='1711750'>is</span> <span m='1712110'>e</span> <span m='1712370'>to</span>
  <span m='1712440'>the</span> <span m='1712560'>j</span> <span
  m='1712800'>omega</span> <span m='1713220'>n</span> <span
  m='1714690'>times</span> <span m='1715170'>the</span> <span
  m='1715260'>sum</span> <span m='1715620'>of</span> <span m='1715710'>h</span>
  <span m='1715920'>of</span> <span m='1716040'>k</span> <span
  m='1716330'>e</span> <span m='1716620'>to</span> <span m='1716850'>the</span>
  <span m='1716940'>minus</span> <span m='1717270'>j omega</span> <span
  m='1717930'>k,</span> <span m='1718950'>as</span> <span
  m='1719490'>I've</span> <span m='1719880'>indicated</span> <span
  m='1720480'>up here.</span> </p><p><span m='1721770'>So</span> <span
  m='1721920'>we</span> <span m='1722040'>started</span> <span
  m='1722730'>with</span> <span m='1723270'>a</span> <span
  m='1723480'>complex</span> <span m='1724050'>exponential</span> <span
  m='1724770'>sequence</span> <span m='1725220'>going</span> <span
  m='1725520'>into</span> <span m='1725760'>the</span> <span
  m='1725850'>system.</span> <span m='1727710'>None</span> <span
  m='1727950'>of</span> <span m='1728040'>this</span> <span
  m='1728220'>stuff</span> <span m='1728520'>over</span> <span
  m='1728760'>here</span> <span m='1728940'>depends</span> <span
  m='1729360'>on</span> <span m='1729510'>n,</span> <span m='1730350'>so</span>
  <span m='1730590'>when</span> <span m='1730740'>we</span> <span
  m='1730860'>sum</span> <span m='1731160'>all</span> <span
  m='1731340'>that</span> <span m='1731520'>up,</span> <span
  m='1731970'>that's</span> <span m='1732180'>just</span> <span
  m='1732410'>a</span> <span m='1732480'>number--</span> <span
  m='1733470'>it's</span> <span m='1733620'>a</span> <span
  m='1733680'>function</span> <span m='1734040'>of</span> <span
  m='1734130'>omega,</span> <span m='1734690'>depends</span> <span
  m='1735090'>on</span> <span m='1735240'>what</span> <span
  m='1735870'>complex</span> <span m='1736320'>frequency</span> <span
  m='1736800'>we've</span> <span m='1736970'>put</span> <span
  m='1737190'>in.</span> <span m='1737850'>But</span> <span
  m='1738120'>it</span> <span m='1738300'>doesn't</span> <span
  m='1738600'>depend</span> <span m='1738990'>on</span> <span
  m='1739210'>n.</span> <span m='1740250'>And,</span> <span
  m='1741540'>in</span> <span m='1741630'>fact,</span> <span
  m='1742350'>notationally,</span> <span m='1744870'>we'll</span> <span
  m='1745860'>refer</span> <span m='1746310'>to</span> <span
  m='1746460'>this</span> <span m='1746720'>as</span> <span
  m='1746880'>the</span> <span m='1747360'>H</span> <span m='1747510'>of e to
  the</span> <span m='1747630'>j</span> <span m='1747840'>omega.</span> <span
  m='1749790'>So</span> <span m='1750690'>consequently,</span> <span
  m='1752220'>the</span> <span m='1752910'>output</span> <span
  m='1753660'>sequence,</span> <span m='1754680'>due</span> <span
  m='1754950'>to</span> <span m='1755160'>a</span> <span
  m='1755220'>complex</span> <span m='1755790'>exponential</span> <span
  m='1756450'>input,</span> <span m='1757560'>is</span> <span
  m='1759370'>this</span> <span m='1760790'>number,</span> <span
  m='1761930'>or</span> <span m='1762260'>function</span> <span
  m='1762800'>of</span> <span m='1762920'>omega,</span> <span
  m='1764240'>times</span> <span m='1764625'>e</span> <span
  m='1765010'>of</span> <span m='1765230'>the</span> <span m='1765350'>j</span>
  <span m='1765560'>omega</span> <span m='1766010'>n.</span> </p><p><span
  m='1766910'>The</span> <span m='1767150'>change</span> <span
  m='1767660'>in</span> <span m='1767810'>the</span> <span
  m='1767870'>complex</span> <span m='1768440'>amplitude,</span> <span
  m='1769010'>then,</span> <span m='1769520'>is</span> <span m='1770000'>H
  of</span> <span m='1770240'>e to the</span> <span m='1770990'>j</span> <span
  m='1771230'>omega,</span> <span m='1772340'>but</span> <span
  m='1772790'>the</span> <span m='1772910'>functional</span> <span
  m='1773360'>form</span> <span m='1773720'>of</span> <span
  m='1773810'>the</span> <span m='1773960'>output</span> <span
  m='1774470'>is</span> <span m='1774650'>the</span> <span
  m='1774740'>same</span> <span m='1775040'>as</span> <span
  m='1775130'>the</span> <span m='1775220'>functional</span> <span
  m='1775610'>form</span> <span m='1775850'>of</span> <span
  m='1775910'>the</span> <span m='1776030'>input.</span> <span
  m='1776820'>And</span> <span m='1776920'>that's</span> <span
  m='1776990'>what</span> <span m='1777080'>we</span> <span
  m='1777260'>mean</span> <span m='1777740'>when</span> <span
  m='1777920'>we</span> <span m='1778040'>say</span> <span
  m='1778490'>that</span> <span m='1779060'>the</span> <span
  m='1779240'>complex</span> <span m='1779780'>exponential</span> <span
  m='1780440'>is</span> <span m='1780560'>an</span> <span
  m='1780680'>eigenfunction</span> <span m='1781730'>of</span> <span
  m='1781850'>a</span> <span m='1781910'>linear</span> <span
  m='1782240'>shift</span> <span m='1782540'>invariant</span> <span
  m='1783060'>system.</span> </p><p><span m='1784860'>So</span> <span
  m='1785120'>finally,</span> <span m='1785510'>H of e</span> <span
  m='1785930'>to</span> <span m='1785990'>the</span> <span m='1786080'>j
  omega</span> <span m='1786710'>is</span> <span m='1787100'>given</span> <span
  m='1787430'>by</span> <span m='1787610'>this</span> <span
  m='1787850'>sum--</span> <span m='1789080'>I've</span> <span
  m='1790250'>just</span> <span m='1791360'>changed</span> <span
  m='1791810'>the</span> <span m='1793250'>index</span> <span
  m='1793670'>of</span> <span m='1793790'>summation</span> <span
  m='1794810'>from</span> <span m='1795230'>what</span> <span
  m='1795380'>I</span> <span m='1795470'>had</span> <span m='1795680'>up</span>
  <span m='1795850'>here,</span> <span m='1796040'>but</span> <span
  m='1796190'>obviously</span> <span m='1796700'>that's</span> <span
  m='1796970'>no</span> <span m='1797420'>important</span> <span
  m='1797870'>change.</span> <span m='1799470'>And</span> <span
  m='1800180'>we</span> <span m='1800780'>will</span> <span
  m='1801260'>refer</span> <span m='1802010'>to</span> <span
  m='1802160'>this,</span> <span m='1802700'>or</span> <span
  m='1802940'>to</span> <span m='1803240'>H of e to the</span> <span
  m='1803510'>j omega,</span> <span m='1804680'>as</span> <span
  m='1805520'>the</span> <span m='1805760'>frequency</span> <span
  m='1806360'>response</span> <span m='1807110'>of</span> <span
  m='1807290'>the</span> <span m='1807380'>system.</span> </p><p><span
  m='1809680'>One</span> <span m='1809860'>of</span> <span
  m='1810070'>the</span> <span m='1810940'>reasons</span> <span
  m='1811960'>why</span> <span m='1812680'>the</span> <span
  m='1812920'>frequency</span> <span m='1813430'>response</span> <span
  m='1814150'>is</span> <span m='1814300'>important--</span> <span
  m='1815330'>of</span> <span m='1815430'>course,</span> <span
  m='1815660'>one</span> <span m='1815800'>of</span> <span
  m='1815890'>the</span> <span m='1816010'>facts</span> <span
  m='1816610'>that</span> <span m='1816760'>you</span> <span
  m='1816880'>can</span> <span m='1817000'>see</span> <span
  m='1817180'>right</span> <span m='1817360'>away</span> <span
  m='1817720'>is</span> <span m='1817900'>that</span> <span
  m='1819470'>it's</span> <span m='1819670'>easily</span> <span
  m='1820090'>obtained</span> <span m='1821170'>directly</span> <span
  m='1821620'>from</span> <span m='1821830'>the</span> <span
  m='1821920'>unit</span> <span m='1822160'>sample</span> <span
  m='1822610'>response.</span> <span m='1824230'>One</span> <span
  m='1824440'>of</span> <span m='1824560'>the</span> <span
  m='1824920'>reasons</span> <span m='1825700'>why</span> <span
  m='1826300'>the</span> <span m='1826450'>frequency</span> <span
  m='1826930'>response</span> <span m='1827650'>is</span> <span
  m='1828370'>useful</span> <span m='1829000'>is</span> <span
  m='1829180'>because</span> <span m='1830380'>it's</span> <span
  m='1830560'>essentially</span> <span m='1831130'>the</span> <span
  m='1831220'>frequency</span> <span m='1831760'>response</span> <span
  m='1832720'>that</span> <span m='1833470'>allows</span> <span
  m='1833980'>us</span> <span m='1834700'>to</span> <span
  m='1835870'>obtain</span> <span m='1836410'>quite</span> <span
  m='1836680'>easily</span> <span m='1837250'>the</span> <span
  m='1837370'>response</span> <span m='1838150'>of</span> <span
  m='1838450'>the</span> <span m='1838540'>system</span> <span
  m='1839230'>to</span> <span m='1840940'>sinusoidal</span> <span
  m='1841720'>excitations.</span> <span m='1843340'>And,</span> <span
  m='1844600'>as</span> <span m='1844780'>we'll</span> <span
  m='1844900'>see</span> <span m='1845350'>in</span> <span
  m='1846160'>later</span> <span m='1846460'>lectures,</span> <span
  m='1846820'>starting</span> <span m='1847300'>actually</span> <span
  m='1847570'>with</span> <span m='1847690'>the</span> <span
  m='1847750'>next</span> <span m='1848020'>lecture,</span> <span
  m='1849730'>essentially</span> <span m='1850360'>arbitrary</span> <span
  m='1851320'>sequences</span> <span m='1852580'>can</span> <span
  m='1852700'>be</span> <span m='1852820'>represented</span> <span
  m='1853510'>either</span> <span m='1853810'>as</span> <span
  m='1853900'>linear</span> <span m='1854200'>combinations</span> <span
  m='1855130'>of</span> <span m='1855310'>complex</span> <span
  m='1855850'>exponentials,</span> <span m='1857110'>or</span> <span
  m='1857530'>as</span> <span m='1857920'>linear</span> <span
  m='1858220'>combinations</span> <span m='1859180'>of</span> <span
  m='1859870'>sinusoidal</span> <span m='1860620'>sequences.</span> </p><p><span
  m='1861910'>And</span> <span m='1862630'>so,</span> <span
  m='1863020'>if</span> <span m='1863200'>we</span> <span
  m='1863290'>know</span> <span m='1863650'>what</span> <span
  m='1863830'>the</span> <span m='1863920'>response</span> <span
  m='1864420'>is</span> <span m='1864820'>to</span> <span m='1865270'>a</span>
  <span m='1865330'>complex</span> <span m='1865840'>exponential</span> <span
  m='1866500'>or</span> <span m='1866590'>to</span> <span
  m='1866710'>sinusoidal</span> <span m='1867340'>sequences,</span> <span
  m='1868360'>we</span> <span m='1868480'>can,</span> <span
  m='1868660'>in</span> <span m='1868780'>effect,</span> <span
  m='1869680'>describe</span> <span m='1870220'>the</span> <span
  m='1870310'>response</span> <span m='1870970'>to</span> <span
  m='1871360'>arbitrary</span> <span m='1871870'>sequences.</span> <span
  m='1872350'>We'll</span> <span m='1872470'>see</span> <span
  m='1872680'>all</span> <span m='1872860'>of</span> <span
  m='1872950'>that</span> <span m='1873640'>coming</span> <span
  m='1873970'>up</span> <span m='1874120'>in</span> <span m='1874210'>the</span>
  <span m='1874270'>next</span> <span m='1874510'>lecture.</span> <span
  m='1876100'>But</span> <span m='1876280'>to</span> <span
  m='1876400'>see</span> <span m='1876760'>how</span> <span
  m='1877270'>this</span> <span m='1877510'>frequency</span> <span
  m='1878110'>response</span> <span m='1879520'>relates</span> <span
  m='1880300'>to</span> <span m='1880900'>the</span> <span
  m='1881140'>sinusoidal</span> <span m='1881950'>response,</span> <span
  m='1883770'>the</span> <span m='1883900'>relation</span> <span
  m='1884470'>essentially</span> <span m='1884980'>pops</span> <span
  m='1885430'>out</span> <span m='1886060'>from</span> <span
  m='1886780'>the</span> <span m='1886900'>fact</span> <span
  m='1887650'>that</span> <span m='1888130'>if</span> <span
  m='1888370'>we</span> <span m='1888580'>have</span> <span m='1889240'>a</span>
  <span m='1889720'>sinusoidal</span> <span m='1890530'>excitation,</span> <span
  m='1893080'>a</span> <span m='1893350'>sinusoidal</span> <span
  m='1893920'>excitation</span> <span m='1895150'>can</span> <span
  m='1895750'>be</span> <span m='1895930'>represented</span> <span
  m='1896830'>as</span> <span m='1897070'>a</span> <span
  m='1897100'>linear</span> <span m='1897460'>combination</span> <span
  m='1898480'>of</span> <span m='1899110'>two</span> <span
  m='1899290'>complex</span> <span m='1899890'>exponentials--</span> <span
  m='1901270'>as</span> <span m='1901390'>I've</span> <span
  m='1901540'>indicated</span> <span m='1902170'>here.</span> </p><p><span
  m='1903420'>So</span> <span m='1903960'>a</span> <span m='1904210'>over</span>
  <span m='1904420'>2</span> <span m='1904660'>to the</span> <span
  m='1904780'>j</span> <span m='1905050'>phi,</span> <span m='1905640'>e</span>
  <span m='1905920'>to</span> <span m='1906040'>j omega</span> <span
  m='1906530'>0</span> <span m='1906940'>n,</span> <span m='1907720'>this</span>
  <span m='1907930'>is</span> <span m='1908050'>one</span> <span
  m='1908380'>complex</span> <span m='1908950'>exponential</span> <span
  m='1909790'>with</span> <span m='1909940'>a</span> <span
  m='1910000'>complex</span> <span m='1910540'>frequency</span> <span
  m='1911110'>omega</span> <span m='1911560'>0,</span> <span
  m='1912820'>and</span> <span m='1913000'>a</span> <span
  m='1913060'>complex</span> <span m='1913630'>amplitude,</span> <span
  m='1914460'>a</span> <span m='1914680'>over</span> <span m='1914920'>2</span>
  <span m='1915340'>e</span> <span m='1915560'>to</span> <span
  m='1915700'>j</span> <span m='1915970'>phi.</span> <span
  m='1917440'>Then</span> <span m='1917620'>its</span> <span
  m='1917740'>complex</span> <span m='1918280'>conjugate</span> <span
  m='1918910'>term,</span> <span m='1919810'>those</span> <span
  m='1920110'>two</span> <span m='1920380'>added</span> <span
  m='1920740'>up</span> <span m='1921340'>give</span> <span
  m='1921580'>us</span> <span m='1921700'>a</span> <span
  m='1921760'>complex</span> <span m='1922300'>exponential.</span> </p><p><span
  m='1924980'>We</span> <span m='1925130'>can</span> <span
  m='1925310'>find</span> <span m='1926090'>the</span> <span
  m='1926180'>response</span> <span m='1927320'>to</span> <span
  m='1927710'>each</span> <span m='1928010'>of</span> <span
  m='1928130'>these</span> <span m='1931310'>simply</span> <span
  m='1931790'>from</span> <span m='1932000'>the</span> <span
  m='1932090'>frequency</span> <span m='1932630'>response.</span> <span
  m='1933200'>We</span> <span m='1933290'>know</span> <span
  m='1933500'>that</span> <span m='1933620'>all</span> <span
  m='1933800'>that</span> <span m='1933920'>happens</span> <span
  m='1934370'>to</span> <span m='1934490'>a</span> <span
  m='1934550'>complex</span> <span m='1935060'>exponential</span> <span
  m='1935870'>is</span> <span m='1936530'>that</span> <span
  m='1936680'>its</span> <span m='1936800'>complex</span> <span
  m='1937400'>amplitude</span> <span m='1938120'>gets</span> <span
  m='1938330'>multiplied</span> <span m='1939260'>by</span> <span
  m='1939470'>the</span> <span m='1939590'>frequency</span> <span
  m='1940100'>response.</span> <span m='1941610'>And</span> <span
  m='1942050'>so</span> <span m='1942230'>this</span> <span
  m='1942440'>is</span> <span m='1942530'>one</span> <span
  m='1942740'>complex</span> <span m='1943250'>exponential,</span> <span
  m='1943970'>and</span> <span m='1944090'>another</span> <span
  m='1944420'>one.</span> </p><p><span m='1945170'>We're</span> <span
  m='1945290'>talking</span> <span m='1945710'>about</span> <span
  m='1945920'>linear</span> <span m='1946310'>systems,</span> <span
  m='1947460'>so</span> <span m='1947750'>the</span> <span
  m='1949460'>response</span> <span m='1949940'>of</span> <span
  m='1950040'>the</span> <span m='1950120'>sum</span> <span
  m='1950450'>of</span> <span m='1950600'>these</span> <span
  m='1950870'>two</span> <span m='1951330'>is</span> <span
  m='1951530'>the</span> <span m='1951620'>sum</span> <span
  m='1951920'>of</span> <span m='1952010'>the</span> <span
  m='1952130'>responses.</span> <span m='1953510'>And</span> <span
  m='1954740'>so</span> <span m='1955370'>if</span> <span m='1955940'>we</span>
  <span m='1956240'>express</span> <span m='1957320'>the</span> <span
  m='1957410'>frequency</span> <span m='1958010'>response</span> <span
  m='1959450'>in</span> <span m='1959840'>a</span> <span
  m='1959900'>polar</span> <span m='1960320'>form,</span> <span
  m='1961100'>as</span> <span m='1962210'>I've</span> <span
  m='1962390'>indicated</span> <span m='1962990'>here,</span> <span
  m='1964400'>in</span> <span m='1964490'>terms</span> <span
  m='1964790'>of</span> <span m='1964880'>magnitude</span> <span
  m='1966200'>and</span> <span m='1966350'>phase,</span> <span
  m='1967850'>and</span> <span m='1968030'>if</span> <span
  m='1968150'>you</span> <span m='1968240'>track</span> <span
  m='1968630'>through</span> <span m='1969350'>what</span> <span
  m='1969560'>happens</span> <span m='1970400'>when</span> <span
  m='1971120'>you</span> <span m='1971240'>multiply</span> <span
  m='1971810'>each</span> <span m='1972050'>of</span> <span
  m='1972110'>these</span> <span m='1972290'>complex</span> <span
  m='1972800'>exponentials</span> <span m='1974180'>by</span> <span
  m='1975080'>the</span> <span m='1975350'>appropriate</span> <span
  m='1976040'>frequency</span> <span m='1976580'>response--</span> <span
  m='1977210'>this</span> <span m='1977360'>one</span> <span
  m='1977540'>at</span> <span m='1977630'>a</span> <span
  m='1977690'>frequency</span> <span m='1978170'>omega</span> <span
  m='1978590'>0,</span> <span m='1979610'>this</span> <span
  m='1979820'>one</span> <span m='1980000'>at</span> <span m='1980090'>a</span>
  <span m='1980150'>frequency</span> <span m='1980630'>minus</span> <span
  m='1981320'>omega</span> <span m='1981720'>0--</span> <span
  m='1982630'>and</span> <span m='1982780'>add</span> <span
  m='1983030'>the</span> <span m='1983120'>terms</span> <span
  m='1983480'>back</span> <span m='1983750'>together</span> <span
  m='1984200'>again,</span> <span m='1985310'>the</span> <span
  m='1985880'>resulting</span> <span m='1986390'>output</span> <span
  m='1986810'>sequence</span> <span m='1987800'>has</span> <span
  m='1988340'>a</span> <span m='1988430'>change</span> <span
  m='1989450'>in</span> <span m='1990080'>real</span> <span
  m='1990470'>amplitude</span> <span m='1992240'>given</span> <span
  m='1992570'>by,</span> <span m='1993530'>or</span> <span
  m='1993620'>dictated</span> <span m='1994130'>by</span> <span
  m='1994970'>the</span> <span m='1995060'>magnitude</span> <span
  m='1996080'>of</span> <span m='1996200'>the</span> <span
  m='1996320'>frequency</span> <span m='1996830'>response,</span> <span
  m='1998030'>and</span> <span m='1998180'>a</span> <span
  m='1998240'>change</span> <span m='1998900'>in</span> <span
  m='1999350'>phase</span> <span m='2000400'>dictated</span> <span
  m='2001270'>by</span> <span m='2002290'>the</span> <span
  m='2002830'>angle</span> <span m='2003700'>of</span> <span
  m='2004210'>the</span> <span m='2004300'>frequency</span> <span
  m='2004780'>response.</span> <span m='2005340'>In</span> <span
  m='2005410'>other</span> <span m='2005590'>words,</span> <span
  m='2005990'>by</span> <span m='2006100'>this</span> <span m='2006270'>theta
  of</span> <span m='2006590'>omega.</span> </p><p><span m='2007900'>So</span>
  <span m='2008260'>the</span> <span m='2008350'>frequency</span> <span
  m='2008860'>response,</span> <span m='2009520'>when</span> <span
  m='2009670'>thought</span> <span m='2009910'>of</span> <span
  m='2010010'>in</span> <span m='2010120'>polar</span> <span
  m='2010480'>form--</span> <span m='2010840'>magnitude</span> <span
  m='2011650'>and</span> <span m='2011830'>angle--</span> <span
  m='2012820'>the</span> <span m='2012940'>magnitude</span> <span
  m='2013660'>represents</span> <span m='2014290'>the</span> <span
  m='2014380'>change</span> <span m='2014980'>in</span> <span
  m='2015190'>the</span> <span m='2015280'>real</span> <span
  m='2015520'>amplitude</span> <span m='2016210'>of</span> <span
  m='2016360'>a</span> <span m='2016390'>sinusoidal</span> <span
  m='2018190'>excitation.</span> <span m='2019600'>And</span> <span
  m='2020560'>the</span> <span m='2020980'>angle,</span> <span
  m='2021610'>or</span> <span m='2021970'>complex</span> <span
  m='2022540'>argument,</span> <span m='2023110'>represents</span> <span
  m='2023890'>the</span> <span m='2024010'>phase</span> <span
  m='2024280'>shift.</span> <span m='2025190'>And</span> <span
  m='2025210'>that</span> <span m='2025420'>is</span> <span
  m='2025600'>exactly</span> <span m='2026200'>analogous,</span> <span
  m='2026770'>exactly</span> <span m='2027250'>identical</span> <span
  m='2028330'>to</span> <span m='2028570'>what</span> <span
  m='2028750'>we're</span> <span m='2028900'>used</span> <span
  m='2029200'>to</span> <span m='2029530'>in</span> <span m='2029620'>the</span>
  <span m='2029710'>continuous</span> <span m='2030280'>time</span> <span
  m='2030550'>case.</span> </p><p><span m='2032260'>Well,</span> <span
  m='2032620'>let's</span> <span m='2032800'>just</span> <span
  m='2032980'>look</span> <span m='2033250'>at</span> <span
  m='2033520'>an</span> <span m='2033670'>example</span> <span
  m='2034210'>of</span> <span m='2034300'>a</span> <span
  m='2034360'>simple</span> <span m='2034930'>linear</span> <span
  m='2035260'>shift</span> <span m='2035680'>invariant</span> <span
  m='2036130'>system,</span> <span m='2036850'>and</span> <span
  m='2037810'>the</span> <span m='2038320'>resulting</span> <span
  m='2038830'>frequency</span> <span m='2039370'>response.</span> <span
  m='2042600'>Let's</span> <span m='2042830'>return</span> <span
  m='2043430'>to</span> <span m='2044030'>the</span> <span
  m='2044600'>first</span> <span m='2044960'>order</span> <span
  m='2045230'>difference</span> <span m='2045620'>equation</span> <span
  m='2046220'>that</span> <span m='2046340'>we</span> <span
  m='2046490'>talked</span> <span m='2046820'>about</span> <span
  m='2047480'>just</span> <span m='2047720'>a</span> <span
  m='2047780'>short</span> <span m='2048050'>time</span> <span
  m='2048380'>ago.</span> <span m='2049969'>We</span> <span
  m='2051380'>saw</span> <span m='2052040'>that</span> <span
  m='2052219'>there</span> <span m='2052370'>were</span> <span
  m='2052489'>two</span> <span m='2052730'>solutions</span> <span
  m='2054650'>that</span> <span m='2054920'>we</span> <span
  m='2055070'>could</span> <span m='2055219'>generate</span> <span
  m='2055730'>for</span> <span m='2055909'>this,</span> <span
  m='2056420'>depending</span> <span m='2056870'>on</span> <span
  m='2056989'>whether</span> <span m='2057230'>we</span> <span
  m='2057380'>assumed</span> <span m='2057770'>that</span> <span
  m='2057889'>it</span> <span m='2057949'>was</span> <span m='2058100'>a</span>
  <span m='2058159'>causal</span> <span m='2058850'>or</span> <span
  m='2059120'>non-causal</span> <span m='2059840'>system.</span> <span
  m='2062030'>Let's</span> <span m='2062270'>focus</span> <span
  m='2062900'>on</span> <span m='2063050'>the</span> <span
  m='2063139'>causal</span> <span m='2063590'>case.</span> </p><p><span
  m='2064790'>If</span> <span m='2064940'>the</span> <span
  m='2065000'>system</span> <span m='2065420'>was</span> <span
  m='2065570'>causal,</span> <span m='2066350'>we</span> <span
  m='2067100'>generated,</span> <span m='2067760'>essentially,</span> <span
  m='2068310'>iteratively</span> <span m='2069710'>the</span> <span
  m='2069889'>solution</span> <span m='2071239'>that</span> <span
  m='2071570'>the</span> <span m='2071659'>unit</span> <span
  m='2071960'>sample</span> <span m='2072380'>response</span> <span
  m='2073460'>is</span> <span m='2073820'>a</span> <span m='2074050'>to</span>
  <span m='2074179'>the</span> <span m='2074330'>n</span> <span
  m='2074510'>times</span> <span m='2074840'>u of</span> <span
  m='2075080'>n.</span> <span m='2076380'>And</span> <span
  m='2076880'>let's</span> <span m='2077150'>assume</span> <span
  m='2077449'>that</span> <span m='2077540'>we're</span> <span
  m='2077659'>talking</span> <span m='2077960'>about</span> <span
  m='2078110'>a</span> <span m='2078170'>stable</span> <span
  m='2078620'>system,</span> <span m='2079580'>so</span> <span
  m='2079820'>that</span> <span m='2080060'>a</span> <span m='2080630'>is</span>
  <span m='2081469'>magnitude</span> <span m='2081909'>of</span> <span
  m='2081980'>a</span> <span m='2082090'>is</span> <span m='2082219'>less</span>
  <span m='2082520'>than</span> <span m='2082699'>1--</span> <span
  m='2083840'>of</span> <span m='2083929'>course,</span> <span
  m='2084230'>this</span> <span m='2084290'>could</span> <span
  m='2084500'>be</span> <span m='2084620'>negative</span> <span
  m='2085010'>and</span> <span m='2085100'>still</span> <span
  m='2085310'>be</span> <span m='2085460'>stable</span> <span
  m='2085969'>between</span> <span m='2086420'>minus</span> <span
  m='2086750'>1</span> <span m='2086929'>and</span> <span m='2087020'>0.</span>
  <span m='2090440'>I'll assume</span> <span m='2091179'>in</span> <span
  m='2091340'>the</span> <span m='2091400'>pictures</span> <span
  m='2091760'>that</span> <span m='2091909'>I</span> <span
  m='2092000'>draw</span> <span m='2092870'>that</span> <span
  m='2093050'>a</span> <span m='2093290'>is,</span> <span m='2093409'>in</span>
  <span m='2093530'>fact,</span> <span m='2094230'>positive,</span> <span
  m='2095150'>and</span> <span m='2096199'>then</span> <span
  m='2096409'>also</span> <span m='2096770'>less</span> <span
  m='2097040'>than</span> <span m='2097190'>1.</span> </p><p><span
  m='2100500'>Now,</span> <span m='2100840'>the</span> <span
  m='2100960'>expression</span> <span m='2101860'>for</span> <span
  m='2102280'>the</span> <span m='2102370'>frequency</span> <span
  m='2102880'>response</span> <span m='2103390'>of</span> <span
  m='2103480'>the</span> <span m='2103570'>system,</span> <span
  m='2104440'>from</span> <span m='2104710'>what</span> <span
  m='2105040'>we</span> <span m='2105550'>derived</span> <span
  m='2106030'>just</span> <span m='2106270'>above,</span> <span
  m='2107410'>is</span> <span m='2108250'>the</span> <span
  m='2108370'>sum</span> <span m='2108760'>overall</span> <span
  m='2109310'>n</span> <span m='2109870'>of</span> <span m='2110680'>h of</span>
  <span m='2111160'>n</span> <span m='2111730'>times</span> <span
  m='2112060'>e</span> <span m='2112240'>to</span> <span m='2112300'>the</span>
  <span m='2112420'>minus</span> <span m='2112750'>j omega</span> <span
  m='2113095'>n.</span> <span m='2115210'>Because</span> <span
  m='2115840'>of</span> <span m='2116050'>the</span> <span
  m='2116170'>unit</span> <span m='2116650'>step</span> <span
  m='2117160'>in</span> <span m='2117370'>here,</span> <span
  m='2118480'>the</span> <span m='2118840'>limits</span> <span
  m='2119260'>on</span> <span m='2119410'>the</span> <span
  m='2119530'>sum</span> <span m='2120010'>change</span> <span
  m='2121180'>from</span> <span m='2121480'>0</span> <span m='2121870'>to</span>
  <span m='2122050'>infinity--</span> <span m='2122660'>in</span> <span
  m='2122760'>other</span> <span m='2122800'>words,</span> <span
  m='2123440'>all</span> <span m='2123610'>of</span> <span
  m='2123730'>this</span> <span m='2123940'>is</span> <span
  m='2124030'>going</span> <span m='2124180'>to</span> <span
  m='2124240'>be</span> <span m='2124360'>0</span> <span m='2125240'>from</span>
  <span m='2125380'>minus</span> <span m='2125770'>infinity</span> <span
  m='2126280'>up</span> <span m='2126400'>to</span> <span m='2126520'>0,</span>
  <span m='2127930'>because</span> <span m='2128260'>of</span> <span
  m='2128350'>the</span> <span m='2128470'>unit</span> <span
  m='2128740'>step.</span> </p><p><span m='2130100'>For</span> <span
  m='2130340'>n</span> <span m='2130520'>greater</span> <span
  m='2130850'>than</span> <span m='2131000'>0,</span> <span
  m='2131390'>we</span> <span m='2131540'>have</span> <span m='2132020'>a</span>
  <span m='2132240'>to</span> <span m='2132440'>the</span> <span
  m='2132620'>n</span> <span m='2132980'>times</span> <span
  m='2133430'>this</span> <span m='2133580'>exponential,</span> <span
  m='2134900'>so</span> <span m='2135140'>we</span> <span
  m='2135320'>have</span> <span m='2136690'>a</span> <span m='2136910'>to</span>
  <span m='2137210'>the n</span> <span m='2138440'>times</span> <span
  m='2139610'>e</span> <span m='2139940'>to</span> <span
  m='2140210'>the--</span> <span m='2141800'>surely</span> <span
  m='2142070'>there's</span> <span m='2142280'>a</span> <span
  m='2142340'>minus</span> <span m='2142730'>sign</span> <span
  m='2143120'>there--</span> <span m='2143680'>e</span> <span
  m='2143880'>to</span> <span m='2143960'>the</span> <span
  m='2144080'>minus</span> <span m='2144650'>j</span> <span
  m='2144920'>omega</span> <span m='2146070'>n.</span> <span
  m='2147920'>If</span> <span m='2148100'>we</span> <span m='2148220'>sum</span>
  <span m='2148580'>this,</span> <span m='2149420'>this is</span> <span
  m='2149900'>just</span> <span m='2150650'>the</span> <span
  m='2150800'>sum</span> <span m='2151280'>of</span> <span m='2151550'>a</span>
  <span m='2151760'>geometric</span> <span m='2152330'>series.</span>
  </p><p><span m='2153380'>In</span> <span m='2153440'>other</span> <span
  m='2153620'>words,</span> <span m='2153990'>it's</span> <span
  m='2154040'>of</span> <span m='2154160'>the</span> <span
  m='2154280'>form,</span> <span m='2155360'>the</span> <span
  m='2155450'>sum</span> <span m='2155780'>of</span> <span
  m='2155900'>alpha</span> <span m='2156380'>to the n--</span> <span
  m='2157610'>alpha</span> <span m='2157910'>equals</span> <span
  m='2158240'>0</span> <span m='2159050'>to</span> <span
  m='2159230'>infinity.</span> <span m='2160610'>Sums</span> <span
  m='2161120'>of</span> <span m='2161210'>this</span> <span
  m='2161450'>form</span> <span m='2162110'>are</span> <span
  m='2162530'>equal</span> <span m='2162860'>to</span> <span
  m='2163010'>1</span> <span m='2163355'>over 1</span> <span
  m='2163700'>minus</span> <span m='2164120'>alpha.</span> <span
  m='2165990'>And</span> <span m='2166960'>alpha,</span> <span
  m='2167230'>in</span> <span m='2167330'>this</span> <span
  m='2167480'>case,</span> <span m='2167810'>is</span> <span
  m='2167960'>a</span> <span m='2168290'>e</span> <span m='2168410'>to
  the</span> <span m='2168530'>minus j</span> <span m='2168860'>omega.</span>
  <span m='2170180'>So</span> <span m='2171020'>that</span> <span
  m='2171410'>sum,</span> <span m='2171800'>then,</span> <span
  m='2172220'>is</span> <span m='2173030'>1</span> <span m='2173270'>over</span>
  <span m='2173540'>1</span> <span m='2173750'>minus</span> <span
  m='2174070'>a</span> <span m='2174330'>e</span> <span m='2174590'>to</span>
  <span m='2174890'>the</span> <span m='2175010'>minus</span> <span
  m='2175335'>j</span> <span m='2175660'>omega.</span> </p><p><span
  m='2178070'>Well,</span> <span m='2178490'>as</span> <span
  m='2178880'>we</span> <span m='2179030'>saw--</span> <span
  m='2179540'>at</span> <span m='2179660'>least</span> <span
  m='2179870'>for</span> <span m='2179990'>the</span> <span
  m='2180230'>sinusoidal</span> <span m='2180950'>response--</span> <span
  m='2181640'>it's</span> <span m='2181820'>useful</span> <span
  m='2182840'>to</span> <span m='2183650'>look</span> <span
  m='2183950'>at</span> <span m='2184400'>the</span> <span
  m='2184670'>magnitude</span> <span m='2185900'>and</span> <span
  m='2185990'>phase</span> <span m='2186650'>of</span> <span
  m='2186830'>this,</span> <span m='2187100'>in</span> <span
  m='2187190'>other</span> <span m='2187310'>words,</span> <span
  m='2187460'>to</span> <span m='2187550'>look</span> <span
  m='2187760'>at</span> <span m='2187910'>it</span> <span m='2188000'>in</span>
  <span m='2188090'>polar</span> <span m='2188450'>form.</span> <span
  m='2189570'>So</span> <span m='2190670'>if</span> <span m='2191060'>we</span>
  <span m='2191270'>want</span> <span m='2191480'>the</span> <span
  m='2191570'>magnitude</span> <span m='2192620'>of</span> <span
  m='2193100'>this</span> <span m='2193280'>frequency</span> <span
  m='2193820'>response,</span> <span m='2195170'>we</span> <span
  m='2195710'>can</span> <span m='2196190'>obtain</span> <span
  m='2196610'>that</span> <span m='2196940'>by</span> <span
  m='2197450'>multiplying</span> <span m='2198140'>this</span> <span
  m='2198920'>by</span> <span m='2199160'>its</span> <span
  m='2199280'>complex</span> <span m='2199850'>conjugate.</span> <span
  m='2201560'>Consequently,</span> <span m='2202280'>the</span> <span
  m='2202400'>magnitude</span> <span m='2203330'>of</span> <span
  m='2203510'>the</span> <span m='2203600'>frequency</span> <span
  m='2204140'>response</span> <span m='2204830'>is</span> <span
  m='2204980'>given</span> <span m='2205370'>by</span> <span m='2206330'>H of
  e</span> <span m='2206870'>to</span> <span m='2206990'>the</span> <span
  m='2207110'>j</span> <span m='2207380'>omega--</span> <span
  m='2208220'>the</span> <span m='2208310'>minus</span> <span
  m='2208610'>sign</span> <span m='2209000'>is</span> <span
  m='2209150'>conveniently</span> <span m='2209810'>there</span> <span
  m='2210020'>for</span> <span m='2210350'>us--</span> <span
  m='2211520'>multiplied</span> <span m='2212150'>by</span> <span
  m='2212330'>its</span> <span m='2212450'>complex</span> <span
  m='2212960'>conjugate,</span> <span m='2213810'>which</span> <span
  m='2213980'>is</span> <span m='2215000'>1</span> <span
  m='2215330'>minus</span> <span m='2215680'>a</span> <span m='2215940'>e</span>
  <span m='2216200'>to</span> <span m='2216380'>the</span> <span
  m='2216470'>minus--</span> <span m='2217210'>I'm</span> <span
  m='2217310'>sorry,</span> <span m='2217610'>1</span> <span
  m='2217910'>over</span> <span m='2218150'>1 minus</span> <span
  m='2218580'>a</span> <span m='2219000'>3</span> <span m='2219330'>to</span>
  <span m='2219650'>the</span> <span m='2219980'>plus</span> <span
  m='2220280'>j</span> <span m='2220520'>omega.</span> </p><p><span
  m='2222530'>If</span> <span m='2223040'>we</span> <span
  m='2223610'>multiply</span> <span m='2224810'>these</span> <span
  m='2225080'>together,</span> <span m='2226190'>then</span> <span
  m='2226970'>what</span> <span m='2227210'>we</span> <span
  m='2227390'>obtain</span> <span m='2228020'>is</span> <span
  m='2229250'>1</span> <span m='2229490'>over</span> <span m='2229820'>1</span>
  <span m='2230090'>plus</span> <span m='2230390'>a</span> <span
  m='2230540'>squared</span> <span m='2231320'>minus</span> <span m='2231710'>2
  a</span> <span m='2232190'>times</span> <span m='2232490'>cosine</span> <span
  m='2233000'>omega.</span> <span m='2234830'>And</span> <span
  m='2235880'>the</span> <span m='2236180'>phase</span> <span
  m='2236570'>angle</span> <span m='2237740'>of</span> <span
  m='2237920'>this</span> <span m='2238550'>is</span> <span
  m='2238760'>equal</span> <span m='2239210'>to</span> <span
  m='2240200'>the</span> <span m='2240410'>arctangent</span> <span
  m='2242030'>of--</span> <span m='2242750'>if</span> <span
  m='2243080'>you</span> <span m='2243200'>just</span> <span
  m='2243380'>simply</span> <span m='2243710'>work</span> <span
  m='2243950'>this</span> <span m='2244130'>out--</span> <span
  m='2244700'>the</span> <span m='2244820'>arctangent</span> <span
  m='2245450'>of a</span> <span m='2245540'>sine</span> <span
  m='2246050'>omega</span> <span m='2246500'>divided</span> <span
  m='2246950'>by</span> <span m='2247340'>1</span> <span
  m='2247610'>minus</span> <span m='2248000'>a</span> <span
  m='2248360'>cosine</span> <span m='2248930'>omega.</span> <span
  m='2250220'>I</span> <span m='2250490'>suspect,</span> <span
  m='2251150'>actually,</span> <span m='2251600'>that</span> <span
  m='2251720'>because</span> <span m='2252140'>of</span> <span
  m='2252410'>that</span> <span m='2252620'>algebraic</span> <span
  m='2253130'>sign</span> <span m='2253490'>error</span> <span
  m='2253820'>I</span> <span m='2253910'>made,</span> <span
  m='2254270'>the</span> <span m='2254750'>minus</span> <span
  m='2255140'>sign</span> <span m='2256310'>down</span> <span
  m='2256610'>here,</span> <span m='2257960'>actually</span> <span
  m='2258320'>I</span> <span m='2258380'>think</span> <span
  m='2258650'>that</span> <span m='2258770'>this</span> <span
  m='2258950'>comes</span> <span m='2259190'>out</span> <span
  m='2259370'>with</span> <span m='2259520'>a</span> <span
  m='2259580'>minus</span> <span m='2259970'>sign.</span> <span
  m='2261060'>But</span> <span m='2262100'>I</span> <span
  m='2262250'>won't</span> <span m='2262940'>guarantee</span> <span
  m='2263510'>that</span> <span m='2263840'>on</span> <span
  m='2263960'>the</span> <span m='2264050'>spot</span> <span
  m='2264380'>right</span> <span m='2264620'>now--</span> <span
  m='2265460'>you</span> <span m='2265580'>can</span> <span
  m='2265700'>simply</span> <span m='2266540'>verify</span> <span
  m='2267050'>that,</span> <span m='2267260'>but</span> <span
  m='2267380'>I</span> <span m='2267440'>suspect</span> <span
  m='2267900'>that</span> <span m='2268920'>there</span> <span
  m='2269030'>should</span> <span m='2269210'>be</span> <span
  m='2269300'>a</span> <span m='2269360'>minus</span> <span
  m='2269660'>sign</span> <span m='2269990'>there.</span> </p><p><span
  m='2271730'>OK,</span> <span m='2272090'>well</span> <span
  m='2273680'>this,</span> <span m='2273920'>then,</span> <span
  m='2274160'>represents</span> <span m='2275090'>the</span> <span
  m='2275450'>phase</span> <span m='2275840'>shift</span> <span
  m='2276590'>that</span> <span m='2277370'>would</span> <span
  m='2277670'>be</span> <span m='2278180'>encountered</span> <span
  m='2278690'>by</span> <span m='2278960'>a</span> <span
  m='2278990'>sinusoidal</span> <span m='2279680'>input</span> <span
  m='2280160'>going</span> <span m='2280520'>through</span> <span
  m='2280910'>the</span> <span m='2281180'>linear</span> <span
  m='2281480'>shift</span> <span m='2281870'>invariant</span> <span
  m='2282320'>system.</span> <span m='2283460'>This</span> <span
  m='2283730'>would</span> <span m='2283910'>represent</span> <span
  m='2284840'>the</span> <span m='2284930'>square</span> <span
  m='2285710'>of</span> <span m='2285860'>the</span> <span
  m='2285980'>magnitude</span> <span m='2286580'>change</span> <span
  m='2287620'>of</span> <span m='2287780'>a</span> <span
  m='2287840'>sinusoidal</span> <span m='2288740'>input.</span> <span
  m='2291030'>And</span> <span m='2292820'>if</span> <span m='2293210'>we</span>
  <span m='2293390'>were</span> <span m='2293540'>to</span> <span
  m='2293690'>sketch</span> <span m='2294230'>this,</span> <span
  m='2295220'>then</span> <span m='2296030'>what</span> <span
  m='2296210'>we</span> <span m='2296390'>see</span> <span m='2296930'>is</span>
  <span m='2297260'>that</span> <span m='2298030'>at</span> <span
  m='2298190'>omega</span> <span m='2298550'>equal</span> <span
  m='2298850'>to</span> <span m='2299000'>0,</span> <span
  m='2300170'>cosine</span> <span m='2300590'>omega</span> <span
  m='2300920'>of</span> <span m='2301010'>course at</span> <span
  m='2301400'>omega</span> <span m='2301670'>equal</span> <span
  m='2301910'>to</span> <span m='2302030'>0</span> <span m='2302310'>is</span>
  <span m='2302450'>1.</span> <span m='2303620'>So</span> <span
  m='2304100'>this</span> <span m='2304310'>is</span> <span m='2304400'>1</span>
  <span m='2304580'>over</span> <span m='2304730'>1</span> <span
  m='2304940'>plus</span> <span m='2305210'>a</span> <span
  m='2305330'>squared</span> <span m='2305660'>minus</span> <span m='2306020'>2
  a,</span> <span m='2306840'>or</span> <span m='2307490'>1</span> <span
  m='2307730'>over</span> <span m='2308120'>1</span> <span
  m='2308360'>minus</span> <span m='2308840'>a</span> <span
  m='2309350'>quantity</span> <span m='2309800'>squared.</span> <span
  m='2311480'>We're</span> <span m='2311630'>assuming</span> <span
  m='2311930'>that</span> <span m='2312140'>a is</span> <span
  m='2312260'>between</span> <span m='2312650'>0</span> <span
  m='2313010'>and</span> <span m='2313100'>1,</span> <span
  m='2314220'>and</span> <span m='2314840'>so</span> <span
  m='2315320'>we're</span> <span m='2315740'>indicated</span> <span
  m='2316240'>that</span> <span m='2316400'>by</span> <span
  m='2316550'>this</span> <span m='2316760'>value.</span> </p><p><span
  m='2319420'>When</span> <span m='2319640'>omega</span> <span
  m='2319970'>is</span> <span m='2320120'>equal</span> <span
  m='2320420'>to</span> <span m='2320540'>pi,</span> <span
  m='2322630'>cosine</span> <span m='2323080'>omega</span> <span
  m='2323410'>is</span> <span m='2323530'>equal</span> <span
  m='2323770'>to</span> <span m='2323890'>minus</span> <span
  m='2324340'>1.</span> <span m='2325300'>This,</span> <span
  m='2325690'>then,</span> <span m='2325930'>comes</span> <span
  m='2326170'>out</span> <span m='2326380'>to</span> <span m='2326530'>be</span>
  <span m='2326650'>1</span> <span m='2326890'>over</span> <span
  m='2327490'>1</span> <span m='2327790'>plus</span> <span m='2328420'>a</span>
  <span m='2328930'>quantity</span> <span m='2329380'>squared,</span> <span
  m='2330470'>which</span> <span m='2330580'>for a</span> <span
  m='2330850'>between</span> <span m='2331270'>0</span> <span
  m='2331600'>and</span> <span m='2331720'>1</span> <span m='2332110'>is</span>
  <span m='2332470'>less</span> <span m='2332770'>than</span> <span
  m='2332920'>this</span> <span m='2333100'>value.</span> <span
  m='2334030'>So</span> <span m='2334240'>the</span> <span
  m='2334330'>frequency</span> <span m='2334870'>response,</span> <span
  m='2335530'>then,</span> <span m='2336220'>between</span> <span
  m='2337300'>minus</span> <span m='2337660'>pi</span> <span
  m='2338200'>and</span> <span m='2338320'>plus</span> <span
  m='2338650'>pi,</span> <span m='2339580'>would</span> <span
  m='2339760'>have</span> <span m='2340300'>the</span> <span
  m='2340390'>shape</span> <span m='2341050'>that</span> <span
  m='2341170'>I've</span> <span m='2341320'>indicated</span> <span
  m='2341890'>here.</span> </p><p><span m='2343700'>Now,</span> <span
  m='2343750'>what</span> <span m='2343930'>happens</span> <span
  m='2344650'>if</span> <span m='2345250'>we</span> <span
  m='2345520'>continue</span> <span m='2346120'>on</span> <span
  m='2346330'>in</span> <span m='2346450'>frequency--</span> <span
  m='2347230'>omega</span> <span m='2347880'>can,</span> <span
  m='2347980'>of</span> <span m='2348100'>course,</span> <span
  m='2348400'>run</span> <span m='2348700'>from</span> <span
  m='2348910'>pi</span> <span m='2349210'>to</span> <span m='2349540'>2</span>
  <span m='2349945'>pi,</span> <span m='2350350'>and</span> <span
  m='2350740'>on</span> <span m='2350950'>past</span> <span
  m='2351310'>that.</span> <span m='2352900'>You</span> <span
  m='2353050'>can</span> <span m='2353620'>verify</span> <span
  m='2354370'>in</span> <span m='2354430'>a</span> <span m='2354490'>very</span>
  <span m='2354700'>straightforward</span> <span m='2355390'>way</span> <span
  m='2355660'>from</span> <span m='2355840'>this</span> <span
  m='2356020'>expression</span> <span m='2357160'>that,</span> <span
  m='2358030'>from</span> <span m='2358240'>pi</span> <span
  m='2358570'>to</span> <span m='2358690'>2</span> <span m='2358930'>pi,</span>
  <span m='2359950'>the</span> <span m='2360070'>frequency</span> <span
  m='2360580'>response</span> <span m='2361750'>will</span> <span
  m='2362230'>look</span> <span m='2362500'>exactly</span> <span
  m='2362950'>like</span> <span m='2363160'>it</span> <span
  m='2363250'>did</span> <span m='2363400'>from</span> <span
  m='2363580'>minus</span> <span m='2363910'>pi</span> <span
  m='2364420'>to</span> <span m='2364570'>pi.</span> <span m='2366220'>It</span>
  <span m='2366400'>will,</span> <span m='2366940'>then,</span> <span
  m='2367540'>look</span> <span m='2368020'>like</span> <span
  m='2368290'>that.</span> </p><p><span m='2369910'>And</span> <span
  m='2370720'>for</span> <span m='2370990'>minus</span> <span
  m='2371350'>pi</span> <span m='2371620'>to</span> <span
  m='2372010'>minus</span> <span m='2372400'>2</span> <span
  m='2372610'>pi,</span> <span m='2373010'>it</span> <span
  m='2373070'>will</span> <span m='2373210'>look</span> <span
  m='2373420'>exactly</span> <span m='2373960'>as</span> <span
  m='2374080'>it</span> <span m='2374140'>did</span> <span
  m='2374350'>from</span> <span m='2374560'>pi</span> <span
  m='2375010'>down</span> <span m='2375280'>to</span> <span
  m='2375400'>0.</span> <span m='2376480'>So</span> <span m='2377110'>it</span>
  <span m='2377260'>will</span> <span m='2377440'>look</span> <span
  m='2378340'>like</span> <span m='2378610'>this.</span> <span
  m='2379850'>And</span> <span m='2379900'>in</span> <span
  m='2380020'>fact,</span> <span m='2381880'>it's</span> <span
  m='2382120'>straightforward</span> <span m='2382840'>to</span> <span
  m='2382960'>verify</span> <span m='2383620'>for</span> <span
  m='2383770'>both</span> <span m='2384010'>the</span> <span
  m='2384100'>magnitude</span> <span m='2384670'>and</span> <span
  m='2384760'>the</span> <span m='2384850'>phase</span> <span
  m='2386140'>that</span> <span m='2386860'>both</span> <span
  m='2387220'>of</span> <span m='2387340'>those</span> <span
  m='2388090'>are</span> <span m='2388930'>periodic</span> <span
  m='2390900'>in</span> <span m='2391090'>omega,</span> <span
  m='2391900'>with</span> <span m='2392050'>a</span> <span
  m='2392110'>period</span> <span m='2392500'>of</span> <span
  m='2392620'>2</span> <span m='2392830'>pi.</span> <span m='2393970'>So</span>
  <span m='2394630'>this</span> <span m='2395200'>is</span> <span
  m='2395500'>one</span> <span m='2395770'>period,</span> <span
  m='2396310'>say,</span> <span m='2396550'>from</span> <span
  m='2396700'>minus</span> <span m='2397030'>pi</span> <span
  m='2397270'>to</span> <span m='2397360'>pi,</span> <span
  m='2398290'>and</span> <span m='2398410'>then</span> <span
  m='2398560'>another</span> <span m='2398890'>period</span> <span
  m='2399250'>would</span> <span m='2399360'>start</span> <span
  m='2399670'>from</span> <span m='2399850'>pi</span> <span
  m='2401020'>to</span> <span m='2402680'>3</span> <span m='2402950'>pi.</span>
  <span m='2403670'>And</span> <span m='2404360'>it</span> <span
  m='2404450'>would</span> <span m='2405080'>continue</span> <span
  m='2405560'>on</span> <span m='2405740'>like</span> <span
  m='2405950'>that.</span> </p><p><span m='2406550'>So,</span> <span
  m='2406730'>in</span> <span m='2406820'>fact,</span> <span
  m='2407220'>if</span> <span m='2407320'>we</span> <span
  m='2407420'>were</span> <span m='2407520'>to</span> <span
  m='2407620'>sketch</span> <span m='2407840'>this</span> <span
  m='2408080'>out</span> <span m='2408980'>over</span> <span
  m='2409520'>a</span> <span m='2409640'>wider</span> <span
  m='2410000'>range</span> <span m='2410300'>of</span> <span
  m='2410420'>omega,</span> <span m='2410810'>we</span> <span
  m='2411020'>would</span> <span m='2411170'>see</span> <span
  m='2411350'>this</span> <span m='2411530'>periodically</span> <span
  m='2412280'>repeating.</span> <span m='2413030'>For</span> <span
  m='2413150'>this</span> <span m='2413300'>example,</span> <span
  m='2413840'>that's</span> <span m='2413960'>straightforward</span> <span
  m='2414560'>to</span> <span m='2414680'>verify.</span> </p><p><span
  m='2416850'>So</span> <span m='2418350'>there</span> <span
  m='2418950'>are,</span> <span m='2419190'>then,</span> <span
  m='2420510'>two</span> <span m='2421140'>properties</span> <span
  m='2422190'>of</span> <span m='2422880'>the</span> <span
  m='2423090'>frequency</span> <span m='2423630'>response</span> <span
  m='2424830'>which</span> <span m='2425340'>I</span> <span
  m='2425430'>would</span> <span m='2425610'>like</span> <span
  m='2425790'>to</span> <span m='2425880'>call</span> <span
  m='2426120'>your</span> <span m='2426270'>attention</span> <span
  m='2426780'>to</span> <span m='2427200'>in</span> <span
  m='2427320'>preparation</span> <span m='2428730'>for</span> <span
  m='2429630'>our</span> <span m='2429870'>discussion</span> <span
  m='2430440'>next</span> <span m='2430710'>time.</span> <span
  m='2432060'>One</span> <span m='2432240'>of</span> <span
  m='2432390'>them</span> <span m='2432720'>is</span> <span
  m='2432930'>the</span> <span m='2433050'>fact,</span> <span
  m='2433620'>very</span> <span m='2433860'>important</span> <span
  m='2434220'>to</span> <span m='2434340'>keep</span> <span
  m='2434610'>in</span> <span m='2434700'>mind,</span> <span
  m='2435870'>that</span> <span m='2436410'>the</span> <span
  m='2436620'>frequency</span> <span m='2437220'>response,</span> <span
  m='2438660'>as</span> <span m='2438810'>we're</span> <span
  m='2438930'>talking</span> <span m='2439380'>about</span> <span
  m='2439740'>it,</span> <span m='2440610'>is</span> <span m='2441390'>a</span>
  <span m='2441600'>function</span> <span m='2442380'>of</span> <span
  m='2442560'>a</span> <span m='2442680'>continuous</span> <span
  m='2443370'>variable,</span> <span m='2443850'>omega.</span> <span
  m='2444960'>Omega,</span> <span m='2445680'>I</span> <span
  m='2445770'>hadn't</span> <span m='2446040'>stressed</span> <span
  m='2446460'>this</span> <span m='2446640'>point</span> <span
  m='2446910'>previously,</span> <span m='2448140'>but</span> <span
  m='2448500'>omega</span> <span m='2450270'>is</span> <span
  m='2450900'>a</span> <span m='2451380'>variable</span> <span
  m='2452370'>that</span> <span m='2452820'>changes</span> <span
  m='2453270'>continuously</span> <span m='2455010'>over</span> <span
  m='2455490'>whatever</span> <span m='2455880'>range</span> <span
  m='2456210'>we're</span> <span m='2456330'>talking</span> <span
  m='2456780'>about,</span> <span m='2457770'>as</span> <span
  m='2457920'>opposed</span> <span m='2458460'>to</span> <span
  m='2459180'>sequences</span> <span m='2460290'>which</span> <span
  m='2460680'>are</span> <span m='2460860'>functions,</span> <span
  m='2461370'>obviously,</span> <span m='2462090'>of</span> <span
  m='2462660'>a</span> <span m='2463080'>discrete</span> <span
  m='2463560'>variable.</span> </p><p><span m='2465000'>Here</span> <span
  m='2465240'>we're</span> <span m='2465360'>talking</span> <span
  m='2465780'>about</span> <span m='2466020'>a</span> <span
  m='2466080'>function</span> <span m='2466590'>of</span> <span
  m='2466710'>a</span> <span m='2466770'>continuous</span> <span
  m='2467340'>variable,</span> <span m='2467820'>omega.</span> <span
  m='2469320'>As</span> <span m='2469500'>we</span> <span
  m='2469620'>saw,</span> <span m='2470380'>for</span> <span
  m='2470765'>our</span> <span m='2471150'>example,</span> <span
  m='2473050'>the</span> <span m='2473130'>frequency</span> <span
  m='2473670'>response</span> <span m='2474300'>is</span> <span
  m='2474480'>a</span> <span m='2474540'>periodic</span> <span
  m='2475200'>function</span> <span m='2475620'>of</span> <span
  m='2475710'>omega.</span> <span m='2477010'>And</span> <span
  m='2477180'>the</span> <span m='2477270'>period</span> <span
  m='2478020'>is</span> <span m='2478260'>equal</span> <span
  m='2478530'>to</span> <span m='2478680'>2</span> <span m='2478880'>pi.</span>
  </p><p><span m='2480280'>Now,</span> <span m='2480630'>the</span> <span
  m='2480780'>reason</span> <span m='2481230'>that</span> <span
  m='2481320'>it's</span> <span m='2481470'>a</span> <span
  m='2481530'>periodic</span> <span m='2482040'>function</span> <span
  m='2482400'>of</span> <span m='2482520'>omega</span> <span
  m='2482970'>is,</span> <span m='2483120'>in</span> <span
  m='2483210'>fact,</span> <span m='2484530'>somewhat</span> <span
  m='2485250'>obvious.</span> <span m='2487080'>Suppose</span> <span
  m='2487650'>that</span> <span m='2487740'>we</span> <span
  m='2488010'>take</span> <span m='2488310'>a</span> <span
  m='2488370'>complex</span> <span m='2488970'>exponential,</span> <span
  m='2490150'>e</span> <span m='2490340'>to</span> <span m='2490500'>the</span>
  <span m='2490620'>j</span> <span m='2491010'>omega</span> <span
  m='2491490'>n,</span> <span m='2492900'>and</span> <span
  m='2493020'>inquire</span> <span m='2493560'>as</span> <span
  m='2493710'>to</span> <span m='2493830'>how</span> <span
  m='2494620'>the</span> <span m='2494720'>complex</span> <span
  m='2495270'>exponential</span> <span m='2495900'>itself</span> <span
  m='2496350'>behaves</span> <span m='2497610'>if</span> <span
  m='2498150'>we</span> <span m='2499380'>change</span> <span
  m='2499800'>omega</span> <span m='2500430'>over</span> <span
  m='2500790'>an</span> <span m='2500910'>interval</span> <span
  m='2501450'>of</span> <span m='2501600'>more</span> <span
  m='2501840'>than</span> <span m='2501960'>2</span> <span
  m='2502170'>pi.</span> </p><p><span m='2503130'>Suppose</span> <span
  m='2503460'>that</span> <span m='2503550'>we</span> <span
  m='2503700'>replace</span> <span m='2504120'>omega</span> <span
  m='2504570'>by</span> <span m='2504810'>omega</span> <span
  m='2505560'>plus</span> <span m='2505830'>2</span> <span m='2506010'>pi</span>
  <span m='2506310'>times</span> <span m='2506670'>k,</span> <span
  m='2508920'>and</span> <span m='2509610'>now</span> <span
  m='2509880'>if</span> <span m='2509970'>we</span> <span
  m='2510090'>decompose</span> <span m='2510690'>this</span> <span
  m='2510900'>into</span> <span m='2511140'>a</span> <span
  m='2511200'>product,</span> <span m='2512220'>we</span> <span
  m='2512370'>have</span> <span m='2512860'>e</span> <span m='2513080'>to</span>
  <span m='2513200'>the</span> <span m='2513300'>j</span> <span
  m='2513510'>omega</span> <span m='2513930'>n,</span> <span
  m='2514710'>times</span> <span m='2515190'>e</span> <span
  m='2515430'>to</span> <span m='2515490'>the</span> <span m='2515610'>j</span>
  <span m='2515910'>2</span> <span m='2516150'>pi</span> <span
  m='2516960'>k</span> <span m='2517410'>times</span> <span
  m='2517830'>n.</span> <span m='2519540'>This</span> <span
  m='2520350'>is</span> <span m='2520800'>an</span> <span
  m='2520950'>integer</span> <span m='2521730'>multiple--</span> <span
  m='2522360'>this</span> <span m='2522510'>exponent</span> <span
  m='2522990'>is</span> <span m='2523080'>an</span> <span
  m='2523170'>integer</span> <span m='2523500'>multiple</span> <span
  m='2523920'>of</span> <span m='2524010'>2</span> <span m='2524220'>pi.</span>
  <span m='2525550'>And</span> <span m='2525720'>so</span> <span
  m='2525900'>this</span> <span m='2526110'>is</span> <span
  m='2526200'>simply</span> <span m='2526590'>equal</span> <span
  m='2526860'>to</span> <span m='2527010'>unity.</span> </p><p><span
  m='2528450'>Now</span> <span m='2528600'>what</span> <span
  m='2528780'>that</span> <span m='2529020'>says,</span> <span
  m='2530160'>is</span> <span m='2530340'>that</span> <span m='2531180'>a</span>
  <span m='2531270'>complex</span> <span m='2531870'>exponential--</span> <span
  m='2533460'>once</span> <span m='2533790'>we've</span> <span
  m='2533970'>varied</span> <span m='2534420'>omega</span> <span
  m='2535650'>over</span> <span m='2536450'>an</span> <span
  m='2536880'>interval</span> <span m='2537540'>of</span> <span
  m='2537660'>2</span> <span m='2537900'>pi,</span> <span m='2539130'>and</span>
  <span m='2539220'>we</span> <span m='2539340'>go</span> <span
  m='2539490'>past</span> <span m='2539940'>that,</span> <span
  m='2540780'>there</span> <span m='2541020'>are</span> <span
  m='2541200'>no</span> <span m='2541770'>more</span> <span
  m='2542190'>no</span> <span m='2542430'>new complex</span> <span
  m='2543030'>exponentials</span> <span m='2543750'>to</span> <span
  m='2543900'>see.</span> <span m='2544170'>We'll</span> <span
  m='2544350'>see</span> <span m='2544500'>the</span> <span
  m='2544620'>same</span> <span m='2544890'>ones</span> <span
  m='2545160'>over</span> <span m='2545430'>and</span> <span
  m='2545520'>over</span> <span m='2545730'>and</span> <span
  m='2545820'>over</span> <span m='2546120'>again.</span> </p><p><span
  m='2546990'>And</span> <span m='2547080'>consequently,</span> <span
  m='2548820'>the</span> <span m='2549090'>system</span> <span
  m='2549510'>response</span> <span m='2550260'>has</span> <span
  m='2550530'>to</span> <span m='2550650'>be</span> <span
  m='2550800'>periodic</span> <span m='2551760'>in</span> <span
  m='2551880'>omega</span> <span m='2552270'>with</span> <span
  m='2552420'>period</span> <span m='2552840'>2 pi,</span> <span
  m='2553860'>because</span> <span m='2554670'>we're</span> <span
  m='2554790'>putting</span> <span m='2555150'>in,</span> <span
  m='2555990'>essentially,</span> <span m='2556440'>the</span> <span
  m='2556560'>same</span> <span m='2556830'>inputs</span> <span
  m='2557250'>over</span> <span m='2557490'>and</span> <span
  m='2557580'>over</span> <span m='2557820'>and</span> <span
  m='2557910'>over</span> <span m='2558180'>again.</span> <span
  m='2559810'>This</span> <span m='2559920'>is</span> <span m='2560010'>a</span>
  <span m='2560070'>point</span> <span m='2560430'>that</span> <span
  m='2560580'>I'll</span> <span m='2561990'>be</span> <span
  m='2562410'>mentioning</span> <span m='2562920'>from</span> <span
  m='2563100'>time</span> <span m='2563370'>to</span> <span
  m='2563490'>time,</span> <span m='2563910'>and</span> <span
  m='2564240'>it's,</span> <span m='2564600'>in</span> <span
  m='2564690'>fact,</span> <span m='2565380'>somewhat</span> <span
  m='2565680'>important</span> <span m='2566530'>to</span> <span
  m='2567910'>keep</span> <span m='2568230'>in</span> <span
  m='2568320'>mind.</span> <span m='2569100'>Also,</span> <span
  m='2569760'>it's</span> <span m='2569970'>discussed</span> <span
  m='2570660'>in</span> <span m='2570780'>some</span> <span
  m='2570990'>detail</span> <span m='2571470'>again</span> <span
  m='2571980'>in</span> <span m='2572100'>the</span> <span
  m='2572190'>text.</span> </p><p><span m='2573630'>So</span> <span
  m='2574410'>these,</span> <span m='2574800'>then, are</span> <span
  m='2574860'>some</span> <span m='2575040'>properties</span> <span
  m='2575760'>of</span> <span m='2575850'>the</span> <span
  m='2575970'>frequency</span> <span m='2576510'>response.</span> <span
  m='2578640'>There</span> <span m='2579120'>is</span> <span
  m='2579390'>a</span> <span m='2579450'>generalization</span> <span
  m='2580530'>of</span> <span m='2580680'>the</span> <span
  m='2580800'>frequency</span> <span m='2581340'>response,</span> <span
  m='2582180'>which</span> <span m='2582720'>is,</span> <span
  m='2583080'>in</span> <span m='2583200'>fact,</span> <span
  m='2584160'>very</span> <span m='2584490'>important</span> <span
  m='2585300'>for</span> <span m='2585660'>describing</span> <span
  m='2586950'>both</span> <span m='2587160'>signals</span> <span
  m='2587700'>and</span> <span m='2587820'>systems.</span> <span
  m='2588900'>The</span> <span m='2588990'>generalization</span> <span
  m='2590130'>is</span> <span m='2591690'>what</span> <span
  m='2591930'>we'll</span> <span m='2592140'>refer</span> <span
  m='2592500'>to</span> <span m='2592740'>as</span> <span m='2592830'>the</span>
  <span m='2593060'>Fourier</span> <span m='2593370'>transform,</span> <span
  m='2594540'>which</span> <span m='2594720'>plays</span> <span
  m='2595290'>the</span> <span m='2595500'>identical</span> <span
  m='2595980'>role</span> <span m='2596250'>in</span> <span
  m='2596340'>the</span> <span m='2596430'>discrete</span> <span
  m='2596790'>time</span> <span m='2597090'>case</span> <span
  m='2597480'>that</span> <span m='2597660'>the</span> <span
  m='2597990'>Fourier</span> <span m='2598590'>transform</span> <span
  m='2599460'>did</span> <span m='2599820'>in</span> <span
  m='2599970'>the</span> <span m='2600030'>continuous</span> <span
  m='2600600'>time</span> <span m='2600930'>case.</span> </p><p><span
  m='2602050'>And</span> <span m='2602100'>so</span> <span m='2602670'>in</span>
  <span m='2602820'>the</span> <span m='2602910'>next</span> <span
  m='2603180'>lecture,</span> <span m='2604230'>we'll</span> <span
  m='2604890'>be</span> <span m='2605340'>going</span> <span
  m='2605760'>on</span> <span m='2606130'>to</span> <span m='2607020'>a</span>
  <span m='2607140'>discussion</span> <span m='2608040'>of</span> <span
  m='2608670'>the</span> <span m='2608790'>Fourier</span> <span
  m='2609240'>transform</span> <span m='2610680'>taking</span> <span
  m='2611100'>off</span> <span m='2611760'>from</span> <span
  m='2612120'>the</span> <span m='2612240'>set</span> <span
  m='2612450'>of</span> <span m='2612540'>ideas</span> <span
  m='2613350'>that</span> <span m='2614040'>we've</span> <span
  m='2614250'>developed</span> <span m='2614730'>here,</span> <span
  m='2615180'>with</span> <span m='2615420'>regard</span> <span
  m='2615990'>to</span> <span m='2616470'>frequency</span> <span
  m='2617010'>response.</span> <span m='2618540'>Thank</span> <span
  m='2618750'>you.</span> </p><p><span m='2620250'>[MUSIC PLAYING]</span>
  </p><p></p>
embedded_media:
  - uid: b80e11f814bd32be987a6264e605b5f8
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: MITRES_6_008S11_lec03.pdf
    title: MITRES_6_008S11_lec03.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-3-discrete-time-signals-and-systems-part-2/MITRES_6_008S11_lec03.pdf
  - uid: 04861ba6ee52175a1f9268c17265735f
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: XT6o4IRTcLk
  - uid: aa7b406c7d44aa3e395d0a4ae0de7174
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-3-discrete-time-signals/id481803782?i=108362003
  - uid: 9d2bf26e23fc96f389bf103d5de161e2
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec03_300k.mp4'
  - uid: fb187eabd8e67f6f55d1d383634c029e
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/XT6o4IRTcLk/default.jpg'
  - uid: 2b3c00721340d7deae18a13f899fc5da
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: XT6o4IRTcLk
  - uid: 369e628f534ded661b80e8c20daa2803
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: XT6o4IRTcLk.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-3-discrete-time-signals-and-systems-part-2/XT6o4IRTcLk.srt
  - uid: bf2938a32e74749cd551fc2906d3211a
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: XT6o4IRTcLk.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-3-discrete-time-signals-and-systems-part-2/XT6o4IRTcLk.pdf
  - uid: b69bcf3422640691cdd2067c4013ed87
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 1e083c8e4411ad878bad2ed97b37eead
    parent_uid: cbee2b0b473165c25cd6f7c8919f35eb
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
