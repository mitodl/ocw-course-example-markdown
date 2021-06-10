---
order_index: null
title: 'Lecture 11: Representation of Linear Digital Networks'
template_type: Tabbed
uid: 4702023b32f277d17778723243b6c058
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-11-representation-of-linear-digital-networks
short_url: lecture-11-representation-of-linear-digital-networks
inline_embed_id: '74766273lecture11:representationoflineardigitalnetworks90698893'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Block diagram presentation of difference
  equations, linear-signal flow graphs, flow graph representation of difference
  equations, matrix representation of digital networks, computability of digital
  networks.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Representation of Linear Digital Networks (<a
  href="./resolveuid/818a7bf3f67aefa06bcad5fc945950d6">PDF</a>)</p>
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
  m='24344'>[MUSIC PLAYING]</span> </p><p></p><p><span m='55796'>ALAN
  OPPENHEIM:</span> <span m='56038'>In</span> <span m='56280'>several</span>
  <span m='56670'>of</span> <span m='56790'>the</span> <span
  m='57030'>previous</span> <span m='57510'>lessons,</span> <span
  m='58410'>we've</span> <span m='59190'>focused</span> <span
  m='59640'>primarily</span> <span m='60510'>on</span> <span
  m='60750'>the</span> <span m='60840'>class</span> <span m='61220'>of</span>
  <span m='61500'>linear</span> <span m='61800'>shift-invariant</span> <span
  m='62640'>systems</span> <span m='63900'>that</span> <span
  m='64170'>are</span> <span m='64470'>representable</span> <span
  m='65670'>by</span> <span m='65880'>linear</span> <span
  m='66210'>constant</span> <span m='66630'>coefficient</span> <span
  m='67200'>difference</span> <span m='67530'>equations.</span> <span
  m='68650'>And</span> <span m='68700'>we've</span> <span
  m='68850'>talked,</span> <span m='69150'>for</span> <span
  m='69330'>example,</span> <span m='70110'>about</span> <span
  m='70590'>methods</span> <span m='71190'>for</span> <span
  m='71610'>solving</span> <span m='72420'>that</span> <span
  m='72600'>class</span> <span m='73230'>of</span> <span
  m='73890'>equations.</span> <span m='75490'>One</span> <span
  m='75570'>of</span> <span m='75930'>the</span> <span m='76080'>reasons</span>
  <span m='76980'>why</span> <span m='77610'>a</span> <span
  m='77940'>linear</span> <span m='78300'>constant</span> <span
  m='78660'>coefficient</span> <span m='79260'>difference</span> <span
  m='79650'>equations</span> <span m='80790'>represent</span> <span
  m='81330'>a</span> <span m='81390'>particularly</span> <span
  m='81990'>important</span> <span m='82470'>class</span> <span
  m='83220'>of</span> <span m='83460'>discrete</span> <span
  m='83850'>time</span> <span m='84180'>systems</span> <span m='85400'>is</span>
  <span m='85560'>because</span> <span m='85950'>of</span> <span
  m='86040'>the</span> <span m='86160'>fact</span> <span m='86850'>that</span>
  <span m='87330'>they</span> <span m='87510'>have</span> <span
  m='88050'>a</span> <span m='88290'>particularly</span> <span
  m='89470'>straightforward</span> <span m='90570'>implementation</span> <span
  m='92010'>in</span> <span m='92130'>terms</span> <span m='92490'>of</span>
  <span m='92580'>digital</span> <span m='92940'>components.</span> </p><p><span
  m='95530'>So</span> <span m='95940'>in</span> <span m='96570'>this</span>
  <span m='96810'>lecture,</span> <span m='97500'>and</span> <span
  m='97770'>actually</span> <span m='98340'>over</span> <span
  m='99030'>the</span> <span m='99120'>next</span> <span
  m='99300'>several</span> <span m='99720'>lectures,</span> <span
  m='100590'>what</span> <span m='101130'>I'd</span> <span
  m='101310'>like</span> <span m='101550'>to</span> <span
  m='102420'>focus</span> <span m='102930'>on</span> <span m='103980'>is</span>
  <span m='105120'>that</span> <span m='105360'>class</span> <span
  m='105810'>of</span> <span m='105900'>linear</span> <span
  m='106200'>shift-invariant</span> <span m='106980'>systems</span> <span
  m='108000'>and</span> <span m='108150'>in</span> <span
  m='108240'>particular</span> <span m='109230'>the</span> <span
  m='109500'>implementation</span> <span m='110610'>of</span> <span
  m='111270'>that</span> <span m='111480'>class</span> <span
  m='111840'>of</span> <span m='111960'>systems,</span> <span
  m='112860'>in</span> <span m='112980'>other</span> <span
  m='113190'>words,</span> <span m='114000'>digital</span> <span
  m='114360'>networks</span> <span m='115110'>for</span> <span
  m='115980'>the</span> <span m='116220'>implementation</span> <span
  m='117270'>of</span> <span m='117990'>systems</span> <span
  m='118650'>describable</span> <span m='119400'>by</span> <span
  m='119610'>linear</span> <span m='119960'>constant</span> <span
  m='120390'>coefficient</span> <span m='120960'>difference</span> <span
  m='121370'>equations.</span> </p><p><span m='123210'>Well,</span> <span
  m='123840'>as</span> <span m='124560'>we</span> <span m='124890'>have</span>
  <span m='125520'>defined</span> <span m='126000'>previously,</span> <span
  m='128310'>an</span> <span m='128430'>n-th</span> <span
  m='128699'>order</span> <span m='129479'>linear</span> <span
  m='129780'>constant</span> <span m='130199'>coefficient</span> <span
  m='130830'>difference</span> <span m='131220'>equation</span> <span
  m='132720'>essentially</span> <span m='133470'>corresponds</span> <span
  m='134910'>to</span> <span m='135600'>a</span> <span m='136500'>linear</span>
  <span m='136860'>combination</span> <span m='138000'>of</span> <span
  m='138930'>delayed</span> <span m='140460'>output</span> <span
  m='141630'>sequences</span> <span m='143370'>set</span> <span
  m='143700'>equal</span> <span m='144150'>to</span> <span m='144660'>a</span>
  <span m='144750'>linear</span> <span m='145080'>combination</span> <span
  m='146100'>of</span> <span m='146760'>delayed</span> <span
  m='147270'>input</span> <span m='147660'>sequences.</span> <span
  m='148840'>This</span> <span m='149070'>is</span> <span m='149610'>the</span>
  <span m='149910'>general</span> <span m='150330'>form</span> <span
  m='150750'>for</span> <span m='150900'>a</span> <span m='150930'>linear</span>
  <span m='151230'>constant</span> <span m='151680'>coefficient</span> <span
  m='152310'>difference</span> <span m='152670'>equation,</span> <span
  m='153870'>which</span> <span m='154320'>as</span> <span m='154770'>we</span>
  <span m='154890'>discussed</span> <span m='156690'>in</span> <span
  m='156960'>one</span> <span m='157140'>of</span> <span m='157230'>the</span>
  <span m='157350'>early</span> <span m='157860'>lectures,</span> <span
  m='158340'>actually</span> <span m='159060'>Lesson</span> <span
  m='159420'>3,</span> <span m='161580'>corresponds</span> <span
  m='162600'>to</span> <span m='162960'>an</span> <span
  m='163080'>explicit</span> <span m='163830'>input</span> <span
  m='164220'>output</span> <span m='164610'>description</span> <span
  m='165180'>for</span> <span m='165330'>the</span> <span
  m='165450'>system.</span> <span m='166150'>In</span> <span
  m='166200'>other</span> <span m='166410'>words,</span> <span
  m='167410'>we</span> <span m='167460'>can</span> <span m='168570'>solve</span>
  <span m='169020'>this</span> <span m='169260'>equation</span> <span
  m='170340'>by</span> <span m='170520'>taking</span> <span
  m='171360'>this</span> <span m='171570'>set</span> <span m='171810'>of</span>
  <span m='171930'>terms</span> <span m='173010'>over</span> <span
  m='173340'>to</span> <span m='173490'>the</span> <span
  m='173580'>right-hand</span> <span m='174060'>side</span> <span
  m='174360'>of</span> <span m='174480'>the</span> <span
  m='174570'>equation.</span> <span m='175650'>And</span> <span
  m='175800'>the</span> <span m='175890'>difference</span> <span
  m='176250'>equation</span> <span m='176790'>that</span> <span
  m='176910'>results</span> <span m='177600'>is</span> <span m='177900'>a</span>
  <span m='177960'>statement</span> <span m='178530'>that</span> <span
  m='178680'>says</span> <span m='179670'>that</span> <span m='179820'>y</span>
  <span m='180090'>of</span> <span m='180260'>n,</span> <span
  m='180930'>the</span> <span m='181080'>output</span> <span
  m='181440'>sequence</span> <span m='181860'>for</span> <span
  m='181980'>the</span> <span m='182070'>system,</span> <span
  m='183720'>is</span> <span m='184350'>a</span> <span m='184410'>linear</span>
  <span m='184800'>combination</span> <span m='185670'>of</span> <span
  m='186210'>past</span> <span m='186630'>outputs</span> <span
  m='187920'>plus</span> <span m='188430'>a</span> <span
  m='188520'>linear</span> <span m='188850'>combination</span> <span
  m='189810'>of</span> <span m='190530'>delayed</span> <span
  m='191400'>inputs.</span> </p><p><span m='194140'>Now,</span> <span
  m='194700'>we</span> <span m='194880'>also</span> <span
  m='195690'>discussed</span> <span m='196230'>at</span> <span
  m='196320'>that</span> <span m='196830'>point</span> <span
  m='197550'>in</span> <span m='197730'>one</span> <span m='197910'>of</span>
  <span m='198000'>the</span> <span m='198090'>early</span> <span
  m='198360'>lectures</span> <span m='199380'>the</span> <span
  m='199470'>fact</span> <span m='200070'>that</span> <span m='200520'>a</span>
  <span m='200700'>linear</span> <span m='201030'>constant</span> <span
  m='201450'>coefficient</span> <span m='202050'>difference</span> <span
  m='202410'>equation</span> <span m='203610'>is</span> <span
  m='203760'>not</span> <span m='203940'>a</span> <span m='204000'>unique</span>
  <span m='204360'>description</span> <span m='205200'>for</span> <span
  m='205380'>a</span> <span m='205410'>system.</span> <span m='206140'>In</span>
  <span m='206160'>other</span> <span m='206370'>words,</span> <span
  m='206770'>we</span> <span m='206820'>saw</span> <span m='207960'>that</span>
  <span m='209220'>this</span> <span m='209430'>system,</span> <span
  m='210000'>or</span> <span m='210180'>a</span> <span m='210210'>system</span>
  <span m='210570'>that</span> <span m='210690'>satisfies</span> <span
  m='211320'>this</span> <span m='211500'>equation,</span> <span
  m='212550'>could</span> <span m='212700'>correspond</span> <span
  m='213420'>to</span> <span m='213540'>a</span> <span m='213630'>causal</span>
  <span m='214080'>system.</span> <span m='214980'>Or,</span> <span
  m='215400'>in</span> <span m='215550'>fact,</span> <span m='216090'>it</span>
  <span m='216180'>could</span> <span m='216330'>correspond</span> <span
  m='216990'>to</span> <span m='217170'>a</span> <span
  m='217200'>non-causal</span> <span m='217920'>system,</span> <span
  m='218980'>depending</span> <span m='219570'>on</span> <span
  m='220200'>the</span> <span m='220320'>initial</span> <span
  m='220680'>conditions</span> <span m='221400'>or</span> <span
  m='221490'>the</span> <span m='221610'>boundary</span> <span
  m='222030'>conditions</span> <span m='223020'>that</span> <span
  m='223110'>we</span> <span m='223290'>impose</span> <span m='223710'>on</span>
  <span m='223830'>the</span> <span m='223920'>equation.</span> <span
  m='225540'>We</span> <span m='225660'>could</span> <span m='225870'>in</span>
  <span m='225960'>particular</span> <span m='227100'>impose</span> <span
  m='227910'>the</span> <span m='228060'>boundary</span> <span
  m='230190'>conditions</span> <span m='230820'>implied</span> <span
  m='231300'>by</span> <span m='231480'>the</span> <span
  m='231570'>statement</span> <span m='232110'>that</span> <span
  m='232230'>the</span> <span m='232320'>system</span> <span
  m='232710'>is</span> <span m='232830'>causal,</span> <span
  m='233760'>or</span> <span m='234300'>we</span> <span m='234510'>could</span>
  <span m='235140'>impose</span> <span m='235560'>boundary</span> <span
  m='235860'>conditions</span> <span m='236400'>implied</span> <span
  m='236790'>by</span> <span m='236940'>the</span> <span
  m='237060'>statement</span> <span m='237480'>that</span> <span
  m='237600'>the</span> <span m='237690'>system</span> <span
  m='238050'>is</span> <span m='238170'>non-causal.</span> </p><p><span
  m='240480'>For</span> <span m='241260'>this</span> <span
  m='241530'>discussion,</span> <span m='242130'>for</span> <span
  m='242250'>the</span> <span m='242340'>discussion</span> <span
  m='242790'>in</span> <span m='242850'>this</span> <span
  m='243060'>lecture</span> <span m='243450'>and</span> <span
  m='243540'>actually</span> <span m='243930'>over</span> <span
  m='244140'>the</span> <span m='244200'>next</span> <span
  m='244380'>several</span> <span m='244800'>lectures,</span> <span
  m='246000'>the</span> <span m='246300'>assumption</span> <span
  m='247140'>will</span> <span m='247350'>always</span> <span
  m='247800'>be</span> <span m='248580'>that</span> <span
  m='248760'>we're</span> <span m='248910'>talking</span> <span
  m='249600'>about</span> <span m='250170'>a</span> <span
  m='250230'>causal</span> <span m='250890'>system.</span> <span
  m='252160'>In</span> <span m='252180'>other</span> <span
  m='252390'>words,</span> <span m='252850'>the</span> <span
  m='252950'>boundary</span> <span m='253200'>conditions</span> <span
  m='254190'>that</span> <span m='254490'>we're</span> <span
  m='254670'>imposing</span> <span m='255630'>is</span> <span
  m='256260'>that</span> <span m='256620'>for</span> <span m='257130'>the</span>
  <span m='257339'>input</span> <span m='258300'>0</span> <span
  m='259170'>for</span> <span m='259600'>n</span> <span m='259829'>less</span>
  <span m='260130'>than,</span> <span m='260670'>say,</span> <span
  m='261089'>n1,</span> <span m='262110'>the</span> <span
  m='262290'>output</span> <span m='262980'>will</span> <span
  m='263160'>also</span> <span m='263520'>be</span> <span m='263670'>0</span>
  <span m='264120'>for</span> <span m='264330'>n</span> <span
  m='264720'>less</span> <span m='264990'>than</span> <span
  m='265310'>n1.</span> <span m='266470'>So</span> <span m='267330'>we're</span>
  <span m='267630'>implying</span> <span m='268230'>a</span> <span
  m='268290'>set</span> <span m='268500'>of</span> <span
  m='268560'>boundary</span> <span m='268920'>conditions</span> <span
  m='270120'>by</span> <span m='270660'>virtue</span> <span m='271050'>of</span>
  <span m='271110'>the</span> <span m='271230'>fact</span> <span
  m='271620'>that</span> <span m='271740'>we're</span> <span
  m='272160'>assuming</span> <span m='272730'>that</span> <span
  m='272820'>we're</span> <span m='272970'>talking</span> <span
  m='273390'>about</span> <span m='273630'>causal</span> <span
  m='274080'>systems.</span> </p><p><span m='275710'>Now,</span> <span
  m='276240'>in</span> <span m='276690'>implementing</span> <span
  m='277500'>a</span> <span m='277590'>system</span> <span
  m='278250'>describable</span> <span m='279510'>by</span> <span
  m='279900'>a</span> <span m='279960'>difference</span> <span
  m='280350'>equation</span> <span m='280800'>of</span> <span
  m='280890'>this</span> <span m='281100'>form,</span> <span
  m='282780'>what</span> <span m='282930'>we</span> <span m='283080'>see</span>
  <span m='283500'>is</span> <span m='283770'>that</span> <span
  m='284430'>there</span> <span m='284940'>are</span> <span
  m='285300'>three</span> <span m='285660'>basic</span> <span
  m='286080'>operations</span> <span m='286800'>that</span> <span
  m='286920'>are</span> <span m='287040'>involved.</span> <span
  m='288800'>We</span> <span m='288920'>have</span> <span m='289220'>to</span>
  <span m='289670'>somehow</span> <span m='290360'>generate</span> <span
  m='291500'>delayed</span> <span m='292520'>sequences.</span> <span
  m='293450'>We</span> <span m='293600'>have</span> <span m='293780'>to</span>
  <span m='293870'>get</span> <span m='294440'>y</span> <span
  m='294710'>of</span> <span m='294860'>n</span> <span
  m='295010'>delayed.</span> <span m='296270'>We</span> <span
  m='296390'>have</span> <span m='296570'>to</span> <span m='296690'>get</span>
  <span m='296870'>x</span> <span m='297005'>of</span> <span m='297140'>n</span>
  <span m='297410'>delayed.</span> <span m='298010'>So</span> <span
  m='298370'>one</span> <span m='298580'>of</span> <span m='298640'>the</span>
  <span m='298760'>basic</span> <span m='299180'>operations</span> <span
  m='300050'>is</span> <span m='300230'>the</span> <span
  m='300350'>operation</span> <span m='300920'>of</span> <span
  m='301010'>delay.</span> </p><p><span m='303030'>Furthermore,</span> <span
  m='303830'>we</span> <span m='304010'>need</span> <span m='304310'>to</span>
  <span m='304670'>multiply</span> <span m='305870'>these</span> <span
  m='306110'>delayed</span> <span m='306470'>sequences</span> <span
  m='307580'>by</span> <span m='308180'>scalars</span> <span
  m='309410'>and</span> <span m='309590'>these</span> <span
  m='309800'>delayed</span> <span m='310160'>sequences</span> <span
  m='310760'>by</span> <span m='310970'>scalars.</span> <span
  m='312020'>So</span> <span m='312590'>there</span> <span m='313040'>is</span>
  <span m='313220'>the</span> <span m='313310'>additional</span> <span
  m='313730'>operation</span> <span m='314510'>of</span> <span
  m='314960'>multiplication.</span> </p><p><span m='317150'>And</span> <span
  m='317720'>third,</span> <span m='318200'>we</span> <span
  m='318350'>have</span> <span m='318590'>to</span> <span
  m='318710'>accumulate</span> <span m='319850'>these</span> <span
  m='320020'>sums,</span> <span m='320750'>or</span> <span
  m='321230'>accumulate</span> <span m='321860'>these</span> <span
  m='322070'>products.</span> <span m='323610'>And</span> <span
  m='324290'>so</span> <span m='324950'>the</span> <span m='325070'>third</span>
  <span m='325370'>operation</span> <span m='326420'>that</span> <span
  m='326840'>is</span> <span m='327020'>required</span> <span
  m='327680'>in</span> <span m='327770'>the</span> <span
  m='327890'>implementation</span> <span m='328850'>of</span> <span
  m='328970'>a</span> <span m='329030'>linear</span> <span
  m='329330'>constant</span> <span m='329780'>coefficient</span> <span
  m='330380'>difference</span> <span m='330740'>equation</span> <span
  m='331880'>is</span> <span m='332690'>the</span> <span
  m='332810'>operation</span> <span m='333440'>of</span> <span
  m='333530'>addition.</span> </p><p><span m='335390'>Consequently,</span> <span
  m='336500'>if</span> <span m='337040'>we</span> <span m='337250'>were</span>
  <span m='337400'>to</span> <span m='337550'>think</span> <span
  m='337820'>of</span> <span m='337910'>basic</span> <span
  m='338900'>digital</span> <span m='339380'>network</span> <span
  m='339890'>elements,</span> <span m='341270'>we</span> <span
  m='341450'>could</span> <span m='343660'>choose</span> <span
  m='344290'>as</span> <span m='344530'>our</span> <span m='344620'>basic</span>
  <span m='345070'>elements</span> <span m='346340'>the</span> <span
  m='346510'>operations</span> <span m='347650'>corresponding</span> <span
  m='348520'>to</span> <span m='349180'>delay,</span> <span
  m='350320'>multiplication,</span> <span m='351610'>and</span> <span
  m='352090'>addition.</span> <span m='353770'>In</span> <span
  m='353860'>particular</span> <span m='354430'>what</span> <span
  m='354580'>we'd</span> <span m='354730'>like</span> <span m='355000'>to</span>
  <span m='355120'>develop,</span> <span m='355930'>or</span> <span
  m='356080'>generate,</span> <span m='357220'>is</span> <span
  m='357700'>a</span> <span m='357880'>graphical</span> <span
  m='358930'>representation</span> <span m='360130'>of</span> <span
  m='360670'>the</span> <span m='360790'>difference</span> <span
  m='361180'>equation,</span> <span m='362330'>which</span> <span
  m='362500'>is</span> <span m='362650'>what</span> <span
  m='362800'>we'll</span> <span m='362980'>refer</span> <span
  m='363370'>to</span> <span m='363760'>as</span> <span m='363970'>the</span>
  <span m='364060'>digital</span> <span m='364420'>network.</span> <span
  m='365450'>So</span> <span m='365620'>in</span> <span
  m='365710'>essence,</span> <span m='366380'>what</span> <span
  m='366520'>we</span> <span m='366670'>want</span> <span m='367060'>is</span>
  <span m='367240'>a</span> <span m='367300'>graphical</span> <span
  m='367840'>representation</span> <span m='368920'>of</span> <span
  m='369070'>these</span> <span m='369310'>three</span> <span
  m='369550'>operations,</span> <span m='370750'>which</span> <span
  m='371080'>we'll</span> <span m='371290'>combine</span> <span
  m='371710'>together</span> <span m='372310'>into</span> <span
  m='372610'>a</span> <span m='372670'>digital</span> <span
  m='373030'>network.</span> </p><p><span m='375680'>One</span> <span
  m='376550'>type</span> <span m='376850'>of</span> <span
  m='376940'>notation,</span> <span m='377930'>which</span> <span
  m='378500'>is</span> <span m='378800'>essentially</span> <span
  m='379340'>block</span> <span m='379610'>diagram</span> <span
  m='380240'>notation,</span> <span m='381560'>corresponds</span> <span
  m='382460'>to</span> <span m='382820'>representing</span> <span
  m='383480'>the</span> <span m='383630'>operation</span> <span
  m='384260'>of</span> <span m='384550'>delay</span> <span m='386330'>as</span>
  <span m='389110'>a</span> <span m='389170'>box.</span> <span
  m='391840'>The</span> <span m='391960'>input,</span> <span
  m='392480'>of</span> <span m='392580'>course,</span> <span
  m='393040'>is</span> <span m='393640'>the</span> <span
  m='393790'>sequence</span> <span m='394270'>that</span> <span
  m='394420'>we</span> <span m='394540'>want</span> <span m='394780'>to</span>
  <span m='394900'>delay,</span> <span m='395720'>let's</span> <span
  m='395860'>say,</span> <span m='396430'>x</span> <span m='396730'>of</span>
  <span m='396850'>n.</span> <span m='398600'>And</span> <span
  m='399410'>the</span> <span m='399620'>output</span> <span
  m='400340'>then</span> <span m='400850'>is</span> <span m='401180'>that</span>
  <span m='401390'>sequence</span> <span m='401990'>delayed</span> <span
  m='402680'>by</span> <span m='402890'>one</span> <span
  m='403130'>sample,</span> <span m='404120'>x</span> <span m='404380'>of</span>
  <span m='404505'>n</span> <span m='404630'>minus</span> <span
  m='405030'>1.</span> <span m='407505'>And</span> <span
  m='408000'>typically</span> <span m='408750'>in</span> <span
  m='408900'>the</span> <span m='408990'>block</span> <span
  m='409260'>diagram</span> <span m='409920'>type</span> <span
  m='410250'>of</span> <span m='410370'>representation,</span> <span
  m='412140'>this</span> <span m='413160'>element,</span> <span
  m='413940'>or</span> <span m='414450'>block,</span> <span m='415200'>is</span>
  <span m='416100'>denoted</span> <span m='417060'>with</span> <span
  m='417690'>a</span> <span m='418440'>z</span> <span m='418710'>to</span> <span
  m='418860'>the</span> <span m='418980'>minus</span> <span m='419410'>1.</span>
  </p><p><span m='420892'>Well,</span> <span m='421880'>what</span> <span
  m='422150'>does</span> <span m='422240'>z</span> <span m='422540'>to</span>
  <span m='422585'>the</span> <span m='422630'>minus</span> <span
  m='422810'>1</span> <span m='422990'>have</span> <span m='423500'>to</span>
  <span m='423620'>do</span> <span m='424280'>with</span> <span
  m='424640'>the</span> <span m='424820'>operation</span> <span
  m='425390'>of</span> <span m='425480'>delay?</span> <span
  m='426890'>Simply</span> <span m='427700'>that</span> <span
  m='428240'>if</span> <span m='428480'>we</span> <span m='428630'>were</span>
  <span m='428750'>to</span> <span m='428900'>think</span> <span
  m='429380'>of</span> <span m='430250'>the</span> <span m='430505'>z</span>
  <span m='430760'>transform</span> <span m='431600'>of</span> <span
  m='431690'>the</span> <span m='431810'>input</span> <span
  m='432170'>sequence</span> <span m='432890'>and</span> <span
  m='433010'>the</span> <span m='433100'>z</span> <span
  m='433310'>transform</span> <span m='433970'>of</span> <span
  m='434060'>the</span> <span m='434210'>output</span> <span
  m='434600'>sequence,</span> <span m='435770'>what</span> <span
  m='435950'>we</span> <span m='436100'>know</span> <span m='436490'>is</span>
  <span m='436790'>that</span> <span m='437270'>those</span> <span
  m='437630'>are</span> <span m='437720'>related,</span> <span
  m='438540'>in</span> <span m='438590'>fact,</span> <span m='439650'>by</span>
  <span m='440210'>multiplication</span> <span m='441470'>by</span> <span
  m='441860'>z</span> <span m='442070'>to</span> <span m='442220'>the</span>
  <span m='442340'>minus</span> <span m='442730'>1.</span> <span
  m='443690'>So</span> <span m='444260'>the</span> <span
  m='444410'>implication</span> <span m='445430'>in</span> <span
  m='446240'>putting</span> <span m='446690'>inside</span> <span
  m='447560'>the</span> <span m='447680'>box</span> <span m='448910'>the</span>
  <span m='450210'>notation</span> <span m='450830'>z</span> <span
  m='451080'>to</span> <span m='451130'>the</span> <span m='451220'>minus</span>
  <span m='451400'>1,</span> <span m='451580'>the</span> <span
  m='451910'>implication</span> <span m='452630'>is</span> <span
  m='453320'>that</span> <span m='453620'>essentially</span> <span
  m='454220'>what</span> <span m='454370'>this</span> <span
  m='454550'>block</span> <span m='454880'>is</span> <span
  m='455030'>doing</span> <span m='455570'>is</span> <span
  m='456200'>multiplying</span> <span m='457780'>the</span> <span
  m='457880'>z</span> <span m='458060'>transform</span> <span
  m='458540'>of</span> <span m='458600'>the</span> <span m='458690'>input</span>
  <span m='459020'>sequence</span> <span m='459590'>by</span> <span
  m='459800'>z</span> <span m='460010'>to</span> <span m='460110'>the</span>
  <span m='460190'>minus</span> <span m='460580'>1.</span> </p><p><span
  m='462380'>So</span> <span m='462890'>that's</span> <span
  m='463130'>one</span> <span m='463340'>element.</span> <span
  m='464270'>The</span> <span m='464390'>second</span> <span
  m='464720'>element</span> <span m='465290'>that</span> <span
  m='465440'>we</span> <span m='465590'>need</span> <span m='466040'>is</span>
  <span m='466670'>the</span> <span m='466970'>element</span> <span
  m='467300'>for</span> <span m='467450'>multiplication.</span> <span
  m='469820'>And</span> <span m='470570'>typically,</span> <span
  m='471500'>that's</span> <span m='471800'>denoted</span> <span
  m='472550'>simply</span> <span m='473180'>by</span> <span m='473475'>a</span>
  <span m='473770'>line</span> <span m='474590'>with</span> <span
  m='474740'>an</span> <span m='474830'>arrow</span> <span m='475250'>on</span>
  <span m='475460'>it.</span> </p><p><span m='476900'>The</span> <span
  m='477050'>input</span> <span m='477710'>to</span> <span
  m='477830'>this</span> <span m='478040'>branch</span> <span
  m='478730'>is</span> <span m='479090'>x</span> <span m='479555'>of</span>
  <span m='480020'>n.</span> <span m='483320'>Or</span> <span
  m='483455'>it</span> <span m='483590'>could</span> <span m='483800'>be,</span>
  <span m='483950'>of</span> <span m='484010'>course,</span> <span
  m='484280'>y</span> <span m='484450'>of</span> <span m='484620'>n.</span>
  <span m='485360'>The</span> <span m='485480'>output</span> <span
  m='485840'>of</span> <span m='485930'>the</span> <span
  m='486050'>branch</span> <span m='486710'>is</span> <span
  m='487340'>that</span> <span m='487640'>multiplied</span> <span
  m='488330'>by</span> <span m='488810'>a</span> <span m='488870'>scalar,</span>
  <span m='489620'>let's</span> <span m='489830'>say,</span> <span
  m='490835'>a,</span> <span m='491240'>the</span> <span
  m='491690'>scalar</span> <span m='491945'>a.</span> </p><p><span
  m='492200'>And</span> <span m='492590'>this</span> <span
  m='493100'>should</span> <span m='493400'>be</span> <span m='493820'>x</span>
  <span m='494030'>of</span> <span m='494240'>n.</span> <span
  m='494840'>If</span> <span m='494990'>we're</span> <span
  m='495140'>talking</span> <span m='495410'>about</span> <span
  m='495590'>x</span> <span m='495830'>of</span> <span m='496025'>n</span> <span
  m='496220'>in,</span> <span m='496610'>we're</span> <span
  m='496730'>talking</span> <span m='497060'>about</span> <span
  m='497240'>x</span> <span m='497450'>of</span> <span m='497570'>n</span> <span
  m='497750'>out,</span> <span m='498620'>or</span> <span m='498800'>a</span>
  <span m='498980'>times</span> <span m='499280'>x</span> <span
  m='499450'>of</span> <span m='499590'>n</span> <span m='499730'>out.</span>
  <span m='500450'>And</span> <span m='500660'>the</span> <span
  m='500750'>branch</span> <span m='501710'>transmittance</span> <span
  m='502550'>then</span> <span m='503090'>is</span> <span m='503300'>the</span>
  <span m='503390'>coefficient</span> <span m='504060'>a.</span> <span
  m='505490'>So</span> <span m='505820'>this</span> <span
  m='506030'>branch</span> <span m='506390'>allows</span> <span
  m='506750'>for</span> <span m='507590'>coefficient</span> <span
  m='508160'>multiplication.</span> </p><p><span m='509780'>And</span> <span
  m='510140'>finally</span> <span m='510560'>the</span> <span
  m='510680'>third</span> <span m='511730'>element</span> <span
  m='512330'>that</span> <span m='512510'>we</span> <span m='512659'>want</span>
  <span m='513650'>is</span> <span m='514280'>an</span> <span
  m='514429'>element</span> <span m='514940'>that</span> <span
  m='515090'>will</span> <span m='515210'>perform</span> <span
  m='515690'>addition.</span> <span m='516830'>And</span> <span
  m='517669'>that</span> <span m='517909'>element</span> <span
  m='518780'>is</span> <span m='518990'>the</span> <span m='519090'>noted</span>
  <span m='519500'>in</span> <span m='519590'>block</span> <span
  m='519890'>diagram</span> <span m='520429'>notation</span> <span
  m='521720'>as</span> <span m='521900'>a</span> <span m='521960'>summer</span>
  <span m='522980'>with</span> <span m='523250'>two</span> <span
  m='523490'>inputs</span> <span m='525500'>and</span> <span m='526190'>a</span>
  <span m='526250'>single</span> <span m='526640'>output.</span> <span
  m='528140'>The</span> <span m='528290'>input,</span> <span
  m='528890'>let's</span> <span m='529130'>say,</span> <span
  m='529460'>x1</span> <span m='530300'>and</span> <span m='530480'>x2,</span>
  <span m='531920'>then</span> <span m='532610'>the</span> <span
  m='532790'>output</span> <span m='533300'>would</span> <span
  m='533480'>be</span> <span m='533810'>x1</span> <span m='534860'>plus</span>
  <span m='536090'>x2</span> <span m='537200'>of</span> <span
  m='537620'>n</span> <span m='538010'>or</span> <span m='538310'>z,</span>
  <span m='538550'>depending</span> <span m='539240'>on</span> <span
  m='539690'>how</span> <span m='539840'>we</span> <span
  m='539990'>choose</span> <span m='540260'>to</span> <span
  m='540350'>describe</span> <span m='540770'>the</span> <span
  m='540890'>sequence.</span> </p><p><span m='542660'>Now</span> <span
  m='543170'>in</span> <span m='544070'>the</span> <span
  m='544280'>difference</span> <span m='544730'>equation,</span> <span
  m='545390'>of</span> <span m='545480'>course,</span> <span
  m='546080'>we</span> <span m='546260'>had</span> <span m='546410'>to</span>
  <span m='546530'>accumulate</span> <span m='547760'>a</span> <span
  m='547820'>number</span> <span m='548210'>of</span> <span
  m='548330'>turns.</span> <span m='549200'>In</span> <span
  m='549290'>other</span> <span m='549410'>words,</span> <span
  m='549670'>there</span> <span m='550120'>was</span> <span
  m='550280'>more</span> <span m='550460'>than</span> <span
  m='550580'>one</span> <span m='550730'>term</span> <span
  m='551000'>that</span> <span m='551120'>we</span> <span m='551270'>were</span>
  <span m='551420'>adding</span> <span m='551720'>up.</span> <span
  m='553310'>Typically,</span> <span m='554120'>in</span> <span
  m='554360'>either</span> <span m='554570'>digital</span> <span
  m='554990'>hardware</span> <span m='555770'>or</span> <span
  m='556220'>on</span> <span m='556340'>a</span> <span m='556400'>digital</span>
  <span m='556790'>computer,</span> <span m='558050'>when</span> <span
  m='558350'>we're</span> <span m='558500'>forming</span> <span
  m='558950'>additions,</span> <span m='560060'>the</span> <span
  m='560150'>additions</span> <span m='560630'>are</span> <span
  m='560690'>formed</span> <span m='561170'>in</span> <span
  m='561290'>pairs.</span> <span m='561770'>In</span> <span
  m='561860'>other</span> <span m='562040'>words,</span> <span
  m='565910'>we</span> <span m='566060'>accumulate</span> <span
  m='566780'>a</span> <span m='566840'>large</span> <span
  m='567200'>number</span> <span m='567500'>of</span> <span
  m='567590'>terms</span> <span m='568490'>by</span> <span
  m='568760'>adding</span> <span m='569090'>two</span> <span
  m='569570'>terms</span> <span m='569930'>together,</span> <span
  m='570320'>then</span> <span m='570500'>adding</span> <span
  m='570740'>one</span> <span m='570950'>to</span> <span m='571070'>that</span>
  <span m='571370'>and</span> <span m='571460'>adding</span> <span
  m='571700'>another</span> <span m='571970'>one</span> <span
  m='572120'>to</span> <span m='572240'>that,</span> <span
  m='572450'>etc.</span> <span m='573410'>So</span> <span m='573860'>it's</span>
  <span m='574010'>convenient</span> <span m='575600'>in</span> <span
  m='575750'>that</span> <span m='575960'>sense</span> <span
  m='576880'>to</span> <span m='577550'>think</span> <span m='577880'>of</span>
  <span m='578300'>the</span> <span m='578420'>addition</span> <span
  m='578960'>as</span> <span m='579140'>always</span> <span
  m='579470'>being</span> <span m='579720'>a</span> <span m='579770'>two</span>
  <span m='580010'>input</span> <span m='580580'>one</span> <span
  m='580820'>output</span> <span m='581210'>addition.</span> <span
  m='582050'>Of</span> <span m='582170'>course,</span> <span
  m='582440'>if</span> <span m='582590'>we</span> <span
  m='582980'>accumulate</span> <span m='583550'>three</span> <span
  m='583790'>terms,</span> <span m='584690'>then</span> <span
  m='584960'>it</span> <span m='585020'>would</span> <span
  m='585200'>require</span> <span m='585680'>two</span> <span
  m='585950'>adders</span> <span m='586280'>to</span> <span m='586430'>do</span>
  <span m='586580'>that.</span> </p><p><span m='588420'>So</span> <span
  m='589080'>these</span> <span m='589380'>then</span> <span
  m='589560'>are</span> <span m='589650'>the</span> <span
  m='589770'>basic</span> <span m='590160'>elements</span> <span
  m='590730'>that</span> <span m='590850'>correspond</span> <span
  m='591570'>to</span> <span m='591990'>a</span> <span m='592080'>block</span>
  <span m='592410'>diagram</span> <span m='593400'>representation</span> <span
  m='594510'>of</span> <span m='594960'>a</span> <span m='595050'>linear</span>
  <span m='595350'>constant</span> <span m='595770'>coefficient</span> <span
  m='596370'>difference</span> <span m='596730'>equation,</span> <span
  m='598050'>or</span> <span m='598500'>equivalently</span> <span
  m='599100'>correspond</span> <span m='600060'>to</span> <span
  m='600420'>a</span> <span m='600480'>digital</span> <span
  m='600870'>network.</span> <span m='601800'>And</span> <span
  m='602400'>for</span> <span m='602610'>example,</span> <span
  m='603490'>if</span> <span m='603600'>we</span> <span m='603720'>had</span>
  <span m='604250'>a</span> <span m='604320'>first</span> <span
  m='604680'>order</span> <span m='604950'>difference</span> <span
  m='605370'>equation,</span> <span m='606860'>let's</span> <span
  m='607050'>say</span> <span m='607260'>the</span> <span
  m='607380'>equation</span> <span m='607950'>y</span> <span
  m='608240'>of</span> <span m='608390'>n</span> <span m='609240'>is</span>
  <span m='609390'>equal</span> <span m='609810'>to</span> <span
  m='610200'>a</span> <span m='610470'>times</span> <span m='610860'>y</span>
  <span m='611130'>of</span> <span m='611370'>minus</span> <span
  m='611790'>1</span> <span m='612300'>plus</span> <span m='612590'>x</span>
  <span m='612830'>of</span> <span m='613170'>n,</span> <span
  m='614190'>we</span> <span m='614400'>can</span> <span
  m='614970'>represent</span> <span m='615600'>that</span> <span
  m='615810'>equation</span> <span m='616410'>graphically</span> <span
  m='617430'>in</span> <span m='617550'>terms</span> <span m='617970'>of</span>
  <span m='618090'>these</span> <span m='618750'>elements</span> <span
  m='620370'>as</span> <span m='620820'>I've</span> <span
  m='621000'>indicated</span> <span m='621600'>here.</span> </p><p><span
  m='622690'>So</span> <span m='623190'>what</span> <span m='623370'>do</span>
  <span m='623430'>we</span> <span m='623580'>have?</span> <span
  m='624250'>Well,</span> <span m='625410'>we</span> <span
  m='625560'>have</span> <span m='625980'>as</span> <span m='626160'>an</span>
  <span m='626250'>input</span> <span m='626640'>x</span> <span
  m='626880'>of</span> <span m='627060'>n,</span> <span m='628820'>as</span>
  <span m='628970'>an</span> <span m='629090'>output</span> <span
  m='629510'>y</span> <span m='629840'>of</span> <span m='629990'>n.</span>
  <span m='631810'>We</span> <span m='631930'>need</span> <span
  m='633710'>in</span> <span m='634010'>implementing</span> <span
  m='634610'>this</span> <span m='634790'>difference</span> <span
  m='635150'>equation</span> <span m='636200'>to</span> <span
  m='636350'>obtain</span> <span m='637040'>y</span> <span m='637300'>of</span>
  <span m='637440'>n</span> <span m='637580'>minus</span> <span
  m='638030'>1.</span> <span m='638930'>And</span> <span
  m='639020'>that's</span> <span m='639260'>obtained</span> <span
  m='640100'>with</span> <span m='640610'>the</span> <span
  m='640820'>delay</span> <span m='641180'>element.</span> </p><p><span
  m='643490'>y</span> <span m='643670'>of</span> <span m='643850'>n</span> <span
  m='644000'>minus</span> <span m='644390'>1</span> <span m='644840'>is</span>
  <span m='644990'>then</span> <span m='645470'>multiplied</span> <span
  m='646100'>by</span> <span m='646280'>the</span> <span
  m='646370'>coefficient</span> <span m='647180'>a.</span> <span
  m='648140'>So</span> <span m='648410'>here,</span> <span m='648590'>we</span>
  <span m='648740'>have</span> <span m='648950'>a</span> <span
  m='649190'>times</span> <span m='649520'>y</span> <span m='649760'>of</span>
  <span m='649840'>n</span> <span m='650000'>minus</span> <span
  m='650420'>1.</span> <span m='651410'>And</span> <span m='651530'>then</span>
  <span m='652190'>the</span> <span m='652280'>difference</span> <span
  m='652640'>equation</span> <span m='653150'>states</span> <span
  m='653540'>that</span> <span m='653660'>y</span> <span m='653930'>of</span>
  <span m='654050'>n</span> <span m='654320'>is</span> <span
  m='654530'>the</span> <span m='654650'>sum</span> <span m='655220'>of</span>
  <span m='655430'>that</span> <span m='655790'>with</span> <span
  m='656060'>the</span> <span m='656210'>input.</span> <span
  m='657020'>And</span> <span m='657110'>so</span> <span m='657290'>that</span>
  <span m='657530'>goes</span> <span m='657800'>into</span> <span
  m='658040'>the</span> <span m='658230'>adder.</span> <span
  m='658910'>And</span> <span m='659060'>out</span> <span
  m='659290'>comes</span> <span m='659510'>y</span> <span m='659780'>of</span>
  <span m='659880'>n.</span> </p><p><span m='660920'>So</span> <span
  m='661880'>this</span> <span m='662150'>then</span> <span
  m='662510'>corresponds</span> <span m='663470'>to</span> <span
  m='664010'>a</span> <span m='664580'>block</span> <span
  m='664910'>diagram</span> <span m='666110'>representation</span> <span
  m='667340'>of</span> <span m='667580'>the</span> <span
  m='667670'>difference</span> <span m='668060'>equation,</span> <span
  m='669140'>or</span> <span m='669590'>equivalently,</span> <span
  m='670650'>a</span> <span m='671510'>digital</span> <span
  m='671870'>network</span> <span m='672530'>in</span> <span
  m='672650'>block</span> <span m='672980'>diagram</span> <span
  m='673520'>notation.</span> <span m='675590'>This</span> <span
  m='675770'>notation,</span> <span m='676400'>in</span> <span
  m='676490'>fact,</span> <span m='676970'>is</span> <span m='677270'>a</span>
  <span m='677300'>very</span> <span m='677570'>common</span> <span
  m='678260'>type</span> <span m='678530'>of</span> <span
  m='678620'>notation</span> <span m='679220'>for</span> <span
  m='679370'>graphically</span> <span m='680240'>representing</span> <span
  m='681140'>a</span> <span m='681410'>difference</span> <span
  m='681800'>equation,</span> <span m='682250'>or</span> <span
  m='682340'>digital</span> <span m='682730'>network.</span> <span
  m='683900'>There</span> <span m='684380'>is</span> <span m='684590'>an</span>
  <span m='684650'>alternative</span> <span m='685550'>notation,</span> <span
  m='686600'>which</span> <span m='687020'>has</span> <span m='687710'>a</span>
  <span m='687770'>number</span> <span m='688310'>of</span> <span
  m='688490'>important</span> <span m='688940'>advantages,</span> <span
  m='690570'>which</span> <span m='690830'>is</span> <span
  m='691040'>very</span> <span m='691370'>much</span> <span
  m='691910'>like</span> <span m='692210'>the</span> <span
  m='692330'>block</span> <span m='692600'>diagram</span> <span
  m='693710'>with</span> <span m='694220'>just</span> <span m='694490'>a</span>
  <span m='694550'>few</span> <span m='695810'>minor</span> <span
  m='696350'>changes,</span> <span m='697100'>which</span> <span
  m='697370'>turn</span> <span m='697640'>out</span> <span m='697940'>in</span>
  <span m='698270'>some</span> <span m='698510'>instances</span> <span
  m='699500'>to</span> <span m='699620'>be</span> <span
  m='699770'>convenient.</span> <span m='700610'>And</span> <span
  m='700880'>that</span> <span m='701090'>is</span> <span m='701540'>the</span>
  <span m='701900'>graphical</span> <span m='702470'>representation</span> <span
  m='703580'>of</span> <span m='704360'>the</span> <span
  m='704900'>difference</span> <span m='705260'>equation,</span> <span
  m='705770'>or</span> <span m='705860'>the</span> <span
  m='705980'>digital</span> <span m='706340'>network,</span> <span
  m='707390'>in</span> <span m='707540'>terms</span> <span m='708200'>of</span>
  <span m='708920'>signal</span> <span m='709400'>flow</span> <span
  m='709700'>graphs.</span> </p><p><span m='712370'>Well</span> <span
  m='712850'>let</span> <span m='713030'>me</span> <span
  m='713480'>introduce</span> <span m='714230'>the</span> <span
  m='714560'>notation</span> <span m='715490'>of</span> <span
  m='715760'>signal</span> <span m='716120'>flow</span> <span
  m='716390'>graphs</span> <span m='716880'>first</span> <span
  m='717140'>in</span> <span m='717230'>general</span> <span
  m='717890'>and</span> <span m='718040'>then</span> <span
  m='718400'>more</span> <span m='718610'>specifically</span> <span
  m='719360'>as</span> <span m='719510'>it</span> <span
  m='719780'>applies</span> <span m='720350'>to</span> <span
  m='720920'>your</span> <span m='721040'>constant</span> <span
  m='721460'>coefficient</span> <span m='722120'>difference</span> <span
  m='722510'>equations.</span> <span m='724690'>A</span> <span
  m='724760'>signal</span> <span m='725150'>flow</span> <span
  m='725450'>graph</span> <span m='726230'>is</span> <span
  m='728330'>essentially</span> <span m='728870'>by</span> <span
  m='729080'>definition</span> <span m='730070'>a</span> <span
  m='730370'>network</span> <span m='731510'>of</span> <span
  m='732350'>directed</span> <span m='732890'>branches,</span> <span
  m='734090'>which</span> <span m='734300'>are</span> <span
  m='734390'>connected</span> <span m='735110'>at</span> <span
  m='735320'>nodes.</span> <span m='737030'>So</span> <span
  m='737510'>what</span> <span m='737720'>that</span> <span
  m='737960'>says</span> <span m='738530'>is</span> <span m='738770'>that</span>
  <span m='739460'>in</span> <span m='739580'>a</span> <span
  m='739640'>signal</span> <span m='740000'>flow</span> <span
  m='740300'>graph</span> <span m='741290'>we</span> <span
  m='741440'>have</span> <span m='742550'>what</span> <span
  m='742730'>will</span> <span m='743150'>refer</span> <span
  m='743570'>to</span> <span m='743960'>as</span> <span m='744200'>nodes</span>
  <span m='746030'>and</span> <span m='746780'>directed</span> <span
  m='747260'>branches,</span> <span m='748010'>in</span> <span
  m='748160'>other</span> <span m='748340'>words</span> <span
  m='749090'>branches</span> <span m='749960'>with</span> <span
  m='750590'>arrows</span> <span m='751040'>on</span> <span
  m='751280'>them.</span> <span m='753470'>The</span> <span
  m='753590'>nodes</span> <span m='754490'>will</span> <span
  m='755300'>be</span> <span m='755930'>numbered.</span> <span
  m='757460'>And</span> <span m='757820'>so,</span> <span m='758060'>for</span>
  <span m='758300'>example,</span> <span m='759420'>we</span> <span
  m='759470'>would</span> <span m='759620'>have</span> <span m='760190'>a</span>
  <span m='760250'>node</span> <span m='761300'>j</span> <span
  m='762410'>and</span> <span m='763070'>a</span> <span m='763130'>node</span>
  <span m='764210'>k.</span> </p><p><span m='767040'>Furthermore,</span> <span
  m='768190'>each</span> <span m='768460'>node</span> <span m='768760'>in</span>
  <span m='768880'>the</span> <span m='768940'>network</span> <span
  m='769600'>has</span> <span m='770200'>a</span> <span
  m='770290'>variable</span> <span m='770860'>associated</span> <span
  m='771670'>with</span> <span m='771880'>it.</span> <span m='772110'>So</span>
  <span m='772180'>that,</span> <span m='772640'>for</span> <span
  m='772690'>example</span> <span m='773230'>the</span> <span
  m='773320'>j</span> <span m='773700'>node</span> <span m='774100'>has</span>
  <span m='774310'>the</span> <span m='774430'>variable</span> <span
  m='774970'>w</span> <span m='775220'>sub</span> <span m='775620'>j.</span>
  <span m='776240'>The</span> <span m='776580'>k</span> <span
  m='776920'>node</span> <span m='777250'>has</span> <span m='777400'>the</span>
  <span m='777520'>variable</span> <span m='778000'>w</span> <span
  m='778480'>sub</span> <span m='778620'>k.</span> <span m='781680'>And</span>
  <span m='782640'>we</span> <span m='783480'>have</span> <span
  m='784200'>a</span> <span m='784770'>branch</span> <span
  m='785250'>going</span> <span m='785610'>between</span> <span
  m='786000'>the</span> <span m='786090'>j-th</span> <span
  m='786360'>node</span> <span m='786660'>and</span> <span m='786750'>the</span>
  <span m='786840'>k-th</span> <span m='787170'>node,</span> <span
  m='788040'>which</span> <span m='788790'>will</span> <span
  m='788970'>be</span> <span m='789120'>referred</span> <span
  m='789540'>to</span> <span m='789930'>as</span> <span m='790860'>the</span>
  <span m='791020'>jk-th</span> <span m='792240'>branch.</span> <span
  m='794020'>So</span> <span m='794320'>essentially</span> <span
  m='794890'>the</span> <span m='795010'>numbering</span> <span
  m='795460'>of</span> <span m='795550'>the</span> <span m='795640'>nodes</span>
  <span m='796570'>allows</span> <span m='796960'>us</span> <span
  m='797110'>to</span> <span m='797230'>refer</span> <span m='797560'>to</span>
  <span m='797710'>the</span> <span m='797800'>nodes</span> <span
  m='798160'>and</span> <span m='798250'>also</span> <span m='798640'>to</span>
  <span m='798790'>refer</span> <span m='799270'>to</span> <span
  m='799420'>the</span> <span m='799510'>branches,</span> <span
  m='800860'>referring</span> <span m='801340'>to</span> <span
  m='801430'>the</span> <span m='801520'>branches</span> <span
  m='802030'>by</span> <span m='802180'>talking</span> <span
  m='802690'>about</span> <span m='803650'>which</span> <span
  m='803950'>nodes</span> <span m='804310'>the</span> <span
  m='804400'>branches</span> <span m='805210'>go</span> <span
  m='805410'>between.</span> </p><p><span m='807790'>The</span> <span
  m='807910'>nodes</span> <span m='808180'>that</span> <span
  m='808300'>I've</span> <span m='808420'>indicated</span> <span
  m='808990'>here</span> <span m='809230'>correspond</span> <span
  m='810280'>to</span> <span m='810820'>what</span> <span
  m='811030'>we'll</span> <span m='811140'>refer</span> <span
  m='811510'>to</span> <span m='811810'>as</span> <span
  m='811960'>network</span> <span m='812470'>nodes.</span> <span
  m='813670'>There</span> <span m='814150'>are</span> <span
  m='814420'>also</span> <span m='815590'>source</span> <span
  m='816100'>nodes.</span> <span m='817540'>And</span> <span
  m='817660'>I've</span> <span m='817810'>indicated</span> <span
  m='818350'>one</span> <span m='818590'>here.</span> </p><p><span
  m='819070'>A</span> <span m='819160'>source</span> <span
  m='819550'>node</span> <span m='820060'>is</span> <span m='820240'>a</span>
  <span m='820300'>node</span> <span m='821200'>that</span> <span
  m='821350'>has</span> <span m='821860'>no</span> <span
  m='822100'>branches</span> <span m='822580'>coming</span> <span
  m='822910'>into</span> <span m='823270'>it,</span> <span
  m='823780'>only</span> <span m='824080'>branches</span> <span
  m='824560'>leaving</span> <span m='824950'>it.</span> <span
  m='826450'>And</span> <span m='827230'>the</span> <span
  m='828430'>opposite,</span> <span m='829120'>namely</span> <span
  m='829480'>a</span> <span m='829540'>sink</span> <span m='829870'>node,</span>
  <span m='830900'>which</span> <span m='831010'>is</span> <span
  m='831160'>a</span> <span m='831220'>node</span> <span m='831850'>that</span>
  <span m='832030'>has</span> <span m='832990'>no</span> <span
  m='833200'>branches</span> <span m='834280'>going</span> <span
  m='834580'>out</span> <span m='834760'>of</span> <span m='834880'>it</span>
  <span m='835090'>and</span> <span m='835240'>only</span> <span
  m='835450'>branches</span> <span m='835870'>coming</span> <span
  m='836200'>into</span> <span m='836500'>it.</span> <span
  m='837130'>Basically,</span> <span m='838420'>it's</span> <span
  m='838780'>these</span> <span m='839050'>type</span> <span
  m='839350'>of</span> <span m='839470'>nodes</span> <span
  m='840010'>that</span> <span m='840190'>allow</span> <span
  m='840520'>us</span> <span m='840640'>to</span> <span m='840760'>get</span>
  <span m='840970'>inputs</span> <span m='841480'>into</span> <span
  m='841690'>the</span> <span m='841780'>network.</span> <span
  m='842830'>It's</span> <span m='843460'>this</span> <span
  m='843670'>type</span> <span m='844000'>of</span> <span m='844120'>node</span>
  <span m='844750'>that</span> <span m='845440'>we</span> <span
  m='845590'>use</span> <span m='845860'>to</span> <span
  m='845980'>represent</span> <span m='846970'>outputs</span> <span
  m='847840'>from</span> <span m='848050'>the</span> <span
  m='848140'>network.</span> </p><p><span m='850480'>Now,</span> <span
  m='851280'>this</span> <span m='851790'>defines</span> <span
  m='852360'>essentially</span> <span m='852810'>the</span> <span
  m='852900'>notation.</span> <span m='853710'>It</span> <span
  m='853860'>doesn't</span> <span m='854250'>yet</span> <span
  m='854430'>specify</span> <span m='855120'>what</span> <span
  m='855990'>the</span> <span m='856320'>algebraic</span> <span
  m='857400'>construction</span> <span m='858330'>of</span> <span
  m='858740'>a</span> <span m='858810'>signal</span> <span
  m='859140'>flow</span> <span m='859410'>graph</span> <span
  m='859830'>is.</span> <span m='860580'>So</span> <span m='860910'>in</span>
  <span m='861030'>particular,</span> <span m='861910'>there</span> <span
  m='862380'>are</span> <span m='863190'>some</span> <span
  m='863430'>rules</span> <span m='864150'>that</span> <span
  m='864330'>tell</span> <span m='864600'>us</span> <span m='864900'>how</span>
  <span m='865470'>the</span> <span m='865740'>node</span> <span
  m='866040'>variables</span> <span m='866790'>are</span> <span
  m='866910'>related</span> <span m='867930'>to</span> <span
  m='868740'>inputs</span> <span m='869160'>and</span> <span
  m='869250'>outputs</span> <span m='869730'>of</span> <span
  m='869790'>branches</span> <span m='870330'>or</span> <span
  m='870420'>equivalently</span> <span m='871650'>the</span> <span
  m='872130'>inputs</span> <span m='872490'>and</span> <span
  m='872580'>outputs</span> <span m='872970'>of</span> <span
  m='873090'>other</span> <span m='873300'>nodes.</span> </p><p><span
  m='875680'>A</span> <span m='875790'>branch,</span> <span
  m='877050'>the</span> <span m='877140'>jk-th</span> <span
  m='877740'>branch,</span> <span m='878520'>which</span> <span
  m='878730'>originate</span> <span m='878985'>at</span> <span
  m='879240'>node</span> <span m='879560'>j,</span> <span
  m='880230'>terminates</span> <span m='880515'>at</span> <span
  m='880800'>node</span> <span m='881080'>k,</span> <span m='882540'>has</span>
  <span m='883170'>as</span> <span m='883440'>its</span> <span
  m='883620'>input,</span> <span m='885090'>the</span> <span
  m='885420'>variable</span> <span m='886650'>of</span> <span
  m='886770'>the</span> <span m='886890'>node</span> <span
  m='887580'>that</span> <span m='888230'>it</span> <span
  m='888480'>originates</span> <span m='889170'>from.</span> <span
  m='891570'>It</span> <span m='891660'>also</span> <span m='892020'>has</span>
  <span m='892200'>an</span> <span m='892290'>output.</span> <span
  m='893570'>The</span> <span m='893730'>output</span> <span
  m='894450'>we</span> <span m='895080'>will</span> <span
  m='895290'>denote</span> <span m='895710'>as</span> <span m='895920'>v</span>
  <span m='896145'>sub</span> <span m='896370'>jk.</span> <span
  m='897450'>That's</span> <span m='897660'>the</span> <span
  m='897810'>output</span> <span m='898140'>of</span> <span
  m='898200'>the</span> <span m='898320'>jk-th</span> <span
  m='898920'>branch.</span> <span m='900180'>And</span> <span
  m='900300'>what</span> <span m='900480'>it</span> <span m='900570'>is</span>
  <span m='900750'>very</span> <span m='900960'>simply</span> <span
  m='901710'>in</span> <span m='902160'>the</span> <span m='902250'>most</span>
  <span m='902490'>general</span> <span m='902880'>sense,</span> <span
  m='903920'>the</span> <span m='903990'>most</span> <span
  m='904170'>general</span> <span m='904470'>context,</span> <span
  m='905730'>is</span> <span m='906420'>some</span> <span
  m='906810'>function</span> <span m='908130'>of</span> <span
  m='908730'>the</span> <span m='908880'>input</span> <span m='909240'>to</span>
  <span m='909390'>the</span> <span m='909480'>branch.</span> <span
  m='910420'>So</span> <span m='910650'>the</span> <span
  m='910830'>output</span> <span m='911130'>of</span> <span m='911250'>a</span>
  <span m='911310'>branch</span> <span m='911940'>is</span> <span
  m='912570'>some</span> <span m='912840'>function</span> <span
  m='913500'>of</span> <span m='913950'>the</span> <span m='914100'>input</span>
  <span m='914550'>to</span> <span m='914700'>the</span> <span
  m='914790'>branch,</span> <span m='915720'>where</span> <span
  m='916290'>this</span> <span m='916530'>function</span> <span
  m='917280'>is</span> <span m='917490'>different,</span> <span
  m='917790'>of</span> <span m='917910'>course,</span> <span
  m='918180'>for</span> <span m='918300'>different</span> <span
  m='918600'>branches.</span> </p><p><span m='920940'>Finally,</span> <span
  m='922170'>to</span> <span m='922620'>get</span> <span m='923130'>the</span>
  <span m='923850'>values</span> <span m='924630'>of</span> <span
  m='924810'>the</span> <span m='924900'>node</span> <span
  m='925170'>variables,</span> <span m='926640'>the</span> <span
  m='927030'>node</span> <span m='927360'>values</span> <span
  m='928920'>are</span> <span m='929130'>defined</span> <span
  m='930180'>to</span> <span m='930330'>be</span> <span m='930570'>equal</span>
  <span m='931650'>to</span> <span m='932340'>the</span> <span
  m='932430'>sum</span> <span m='933150'>of</span> <span m='933900'>the</span>
  <span m='934110'>outputs</span> <span m='934920'>of</span> <span
  m='935130'>the</span> <span m='935220'>branches</span> <span
  m='935910'>entering</span> <span m='936390'>the</span> <span
  m='936480'>node.</span> <span m='938460'>So</span> <span
  m='939090'>that</span> <span m='939360'>if</span> <span m='939540'>we</span>
  <span m='939690'>were</span> <span m='940170'>to</span> <span
  m='940830'>look</span> <span m='941070'>up</span> <span
  m='941250'>here,</span> <span m='941430'>for</span> <span
  m='941670'>example,</span> <span m='943020'>this</span> <span
  m='944490'>node</span> <span m='944790'>variable</span> <span
  m='946980'>would</span> <span m='947250'>be</span> <span
  m='947940'>equal</span> <span m='948390'>to</span> <span m='949230'>the</span>
  <span m='949410'>output</span> <span m='949980'>of</span> <span
  m='950130'>this</span> <span m='950370'>branch</span> <span
  m='951000'>plus</span> <span m='951750'>the</span> <span
  m='951900'>output</span> <span m='952230'>of</span> <span
  m='952350'>that</span> <span m='952560'>branch.</span> <span
  m='953410'>And</span> <span m='953730'>that's</span> <span
  m='954000'>essentially</span> <span m='954450'>the</span> <span
  m='954570'>algebraic</span> <span m='955110'>construction</span> <span
  m='955950'>of</span> <span m='956550'>flow</span> <span
  m='956790'>graphs.</span> </p><p><span m='958650'>It's</span> <span
  m='958770'>also</span> <span m='959130'>convenient</span> <span
  m='960000'>to</span> <span m='961200'>separate</span> <span
  m='961770'>notationally</span> <span m='963420'>the</span> <span
  m='964650'>output</span> <span m='965220'>of</span> <span
  m='965400'>the</span> <span m='965520'>branches</span> <span
  m='966300'>from</span> <span m='966690'>an</span> <span
  m='966840'>internal</span> <span m='967320'>node</span> <span
  m='967560'>to</span> <span m='967740'>another</span> <span
  m='968070'>internal</span> <span m='968520'>node,</span> <span
  m='969060'>or</span> <span m='969210'>from</span> <span m='969360'>a</span>
  <span m='969390'>network</span> <span m='969750'>node</span> <span
  m='969930'>to</span> <span m='970110'>a</span> <span m='970140'>network</span>
  <span m='970530'>node,</span> <span m='971310'>from</span> <span
  m='973530'>the</span> <span m='973650'>output</span> <span
  m='973950'>of</span> <span m='974010'>those</span> <span
  m='974280'>branches</span> <span m='974790'>that</span> <span
  m='974910'>originate</span> <span m='975225'>at</span> <span
  m='975540'>sources</span> <span m='976410'>and</span> <span
  m='977190'>go</span> <span m='977430'>to</span> <span
  m='977640'>network</span> <span m='978090'>nodes.</span> <span
  m='979050'>And</span> <span m='979680'>the</span> <span
  m='979770'>notation</span> <span m='980340'>that</span> <span
  m='980460'>we'll</span> <span m='980610'>use</span> <span m='981240'>is</span>
  <span m='981600'>sub</span> <span m='981860'>jk</span> <span
  m='983520'>corresponding</span> <span m='984780'>to</span> <span
  m='984930'>the</span> <span m='985080'>output</span> <span
  m='985950'>of</span> <span m='986130'>the</span> <span
  m='986250'>branch</span> <span m='987630'>that</span> <span
  m='987750'>goes</span> <span m='988080'>from</span> <span
  m='988260'>the</span> <span m='988380'>j-th</span> <span
  m='988770'>source--</span> <span m='989970'>the</span> <span
  m='990060'>sources</span> <span m='990480'>being</span> <span
  m='990640'>numbered</span> <span m='990900'>differently</span> <span
  m='991380'>from</span> <span m='991530'>the</span> <span
  m='991590'>network</span> <span m='991980'>nodes--</span> <span
  m='992730'>going</span> <span m='992940'>from</span> <span
  m='993120'>the</span> <span m='993210'>j-th</span> <span
  m='993590'>source</span> <span m='994560'>to</span> <span
  m='995130'>the</span> <span m='995220'>k-th</span> <span
  m='995970'>network</span> <span m='996420'>node.</span> </p><p><span
  m='998590'>OK,</span> <span m='998950'>so</span> <span m='999610'>what</span>
  <span m='1000720'>this</span> <span m='1000960'>says,</span> <span
  m='1001950'>and</span> <span m='1002460'>this</span> <span
  m='1002670'>equation</span> <span m='1003120'>in</span> <span
  m='1003210'>particular</span> <span m='1003750'>says,</span> <span
  m='1004770'>that</span> <span m='1005670'>algebraically</span> <span
  m='1007350'>the</span> <span m='1007470'>node</span> <span
  m='1008070'>variables</span> <span m='1009540'>are</span> <span
  m='1010140'>specified</span> <span m='1011820'>as</span> <span
  m='1012660'>the</span> <span m='1013250'>k-th</span> <span
  m='1013800'>node</span> <span m='1014100'>variable</span> <span
  m='1015780'>being</span> <span m='1016290'>equal</span> <span
  m='1016770'>to</span> <span m='1017730'>the</span> <span
  m='1017910'>sum</span> <span m='1018570'>over</span> <span
  m='1019350'>the</span> <span m='1019530'>internal</span> <span
  m='1020010'>nodes</span> <span m='1021630'>of</span> <span
  m='1022410'>the</span> <span m='1023010'>output</span> <span
  m='1023430'>of</span> <span m='1023490'>the</span> <span
  m='1023580'>branches</span> <span m='1024240'>from</span> <span
  m='1024780'>the</span> <span m='1025020'>network</span> <span
  m='1025470'>nodes</span> <span m='1025829'>to</span> <span
  m='1025980'>the</span> <span m='1026220'>k-th</span> <span
  m='1026609'>node</span> <span m='1027660'>plus</span> <span
  m='1028380'>the</span> <span m='1030310'>output</span> <span
  m='1030760'>of</span> <span m='1030880'>the</span> <span
  m='1030970'>branches</span> <span m='1031569'>from</span> <span
  m='1031750'>the</span> <span m='1031839'>j-th</span> <span
  m='1032670'>over</span> <span m='1032990'>all</span> <span
  m='1033160'>the</span> <span m='1033490'>source</span> <span
  m='1034089'>nodes,</span> <span m='1034599'>from</span> <span
  m='1034780'>the</span> <span m='1034869'>j-th</span> <span
  m='1035800'>source</span> <span m='1036160'>node,</span> <span
  m='1036940'>to</span> <span m='1037329'>the</span> <span
  m='1037450'>network</span> <span m='1037869'>node</span> <span
  m='1038260'>that</span> <span m='1038380'>we're</span> <span
  m='1038500'>focusing</span> <span m='1039069'>on.</span> <span
  m='1039829'>So</span> <span m='1040750'>this</span> <span
  m='1040990'>corresponds</span> <span m='1042099'>to</span> <span
  m='1042790'>the</span> <span m='1043119'>output</span> <span
  m='1043510'>of</span> <span m='1043569'>the</span> <span
  m='1043660'>branches</span> <span m='1044109'>from</span> <span
  m='1044260'>the</span> <span m='1044349'>network</span> <span
  m='1044829'>nodes.</span> <span m='1045790'>And</span> <span
  m='1045970'>this</span> <span m='1046150'>corresponds</span> <span
  m='1047109'>to</span> <span m='1048160'>the</span> <span
  m='1048460'>output</span> <span m='1048880'>of</span> <span
  m='1048970'>the</span> <span m='1049090'>branches</span> <span
  m='1049570'>from</span> <span m='1049720'>the</span> <span
  m='1049810'>source</span> <span m='1050180'>nodes.</span> </p><p><span
  m='1053830'>Well,</span> <span m='1055410'>for</span> <span
  m='1056010'>linear</span> <span m='1056370'>constant</span> <span
  m='1056820'>coefficient</span> <span m='1057420'>difference</span> <span
  m='1057780'>equations,</span> <span m='1059340'>we</span> <span
  m='1059490'>don't</span> <span m='1059700'>need</span> <span
  m='1060000'>all</span> <span m='1060270'>of</span> <span
  m='1060360'>the</span> <span m='1060450'>generality</span> <span
  m='1061440'>that</span> <span m='1061680'>we've</span> <span
  m='1061920'>implied</span> <span m='1062340'>in</span> <span
  m='1062430'>the</span> <span m='1062520'>discussion</span> <span
  m='1063060'>so</span> <span m='1063300'>far.</span> <span
  m='1064300'>In</span> <span m='1064400'>particular,</span> <span
  m='1065350'>what</span> <span m='1065820'>we</span> <span
  m='1066030'>can</span> <span m='1066270'>concentrate</span> <span
  m='1067080'>on</span> <span m='1067800'>is</span> <span m='1068370'>a</span>
  <span m='1068670'>special</span> <span m='1069150'>set</span> <span
  m='1069660'>of</span> <span m='1070050'>signal</span> <span
  m='1070410'>flow</span> <span m='1070710'>graphs,</span> <span
  m='1071700'>namely</span> <span m='1072240'>signal</span> <span
  m='1072570'>flow</span> <span m='1072840'>graphs</span> <span
  m='1073500'>which</span> <span m='1073740'>are</span> <span
  m='1073830'>linear.</span> <span m='1075370'>And</span> <span
  m='1075960'>what</span> <span m='1076170'>we</span> <span
  m='1076290'>mean</span> <span m='1076560'>by</span> <span
  m='1076740'>linear</span> <span m='1077520'>is</span> <span
  m='1077820'>that</span> <span m='1079080'>the</span> <span
  m='1080520'>output</span> <span m='1081270'>of</span> <span
  m='1081420'>a</span> <span m='1081480'>branch</span> <span
  m='1083370'>is</span> <span m='1083850'>equal</span> <span
  m='1084600'>to</span> <span m='1085530'>the</span> <span
  m='1086010'>input</span> <span m='1086430'>to</span> <span
  m='1086580'>the</span> <span m='1086670'>branch</span> <span
  m='1087570'>multiplied</span> <span m='1088470'>by</span> <span
  m='1088680'>some</span> <span m='1088980'>function.</span> <span
  m='1090290'>So</span> <span m='1090800'>that</span> <span
  m='1091080'>it's</span> <span m='1091230'>a</span> <span
  m='1091290'>linear</span> <span m='1091590'>relationship</span> <span
  m='1092640'>between</span> <span m='1092980'>the</span> <span
  m='1093060'>branch</span> <span m='1093420'>output</span> <span
  m='1093950'>in</span> <span m='1094080'>the</span> <span
  m='1094140'>branch</span> <span m='1094500'>input.</span> </p><p><span
  m='1095470'>In</span> <span m='1095490'>other</span> <span
  m='1095700'>words</span> <span m='1096120'>v</span> <span
  m='1096315'>sub</span> <span m='1096510'>jk,</span> <span
  m='1097530'>the</span> <span m='1097680'>output</span> <span
  m='1098040'>of</span> <span m='1098160'>the</span> <span
  m='1098880'>branch</span> <span m='1099600'>from</span> <span
  m='1099930'>the</span> <span m='1100390'>j-th</span> <span
  m='1100720'>node</span> <span m='1100950'>to</span> <span
  m='1101100'>the</span> <span m='1101190'>k-th</span> <span
  m='1101490'>node,</span> <span m='1102510'>is</span> <span
  m='1102630'>equal</span> <span m='1103080'>to</span> <span
  m='1103890'>some</span> <span m='1104760'>function--</span> <span
  m='1105840'>this</span> <span m='1106020'>might</span> <span
  m='1106260'>be</span> <span m='1106560'>simply</span> <span
  m='1106920'>a</span> <span m='1106980'>scalar</span> <span
  m='1107580'>or</span> <span m='1107670'>it</span> <span
  m='1107760'>might</span> <span m='1107970'>be</span> <span
  m='1108060'>a</span> <span m='1108120'>function</span> <span
  m='1108540'>of</span> <span m='1108630'>z,</span> <span m='1108900'>for</span>
  <span m='1109140'>example,</span> <span m='1110100'>which</span> <span
  m='1110310'>it</span> <span m='1110475'>will</span> <span
  m='1110640'>often</span> <span m='1110910'>turn</span> <span
  m='1111180'>out</span> <span m='1111330'>to</span> <span
  m='1111480'>be--</span> <span m='1112410'>multiplied</span> <span
  m='1113490'>by</span> <span m='1113880'>the</span> <span
  m='1114030'>input</span> <span m='1114360'>to</span> <span
  m='1114480'>that</span> <span m='1114690'>branch,</span> <span
  m='1115170'>in</span> <span m='1115230'>other</span> <span
  m='1115410'>words,</span> <span m='1115990'>the</span> <span
  m='1116520'>value</span> <span m='1117210'>of</span> <span
  m='1117990'>the</span> <span m='1118470'>j-th</span> <span
  m='1118820'>node.</span> <span m='1120760'>So</span> <span
  m='1121420'>that</span> <span m='1122170'>is</span> <span
  m='1122440'>then</span> <span m='1122830'>the</span> <span
  m='1122950'>additional</span> <span m='1123370'>constraint</span> <span
  m='1123880'>that</span> <span m='1124000'>we</span> <span
  m='1124150'>impose</span> <span m='1124870'>if</span> <span
  m='1125530'>we're</span> <span m='1125650'>talking</span> <span
  m='1126220'>about</span> <span m='1126490'>linear</span> <span
  m='1127090'>signal</span> <span m='1127450'>flow</span> <span
  m='1127720'>graphs,</span> <span m='1128470'>which</span> <span
  m='1128680'>we'll</span> <span m='1128860'>be</span> <span
  m='1129460'>concentrating</span> <span m='1130210'>on</span> <span
  m='1130390'>for</span> <span m='1130510'>the</span> <span
  m='1130600'>rest</span> <span m='1130870'>of</span> <span
  m='1130930'>the</span> <span m='1131020'>lecture.</span> </p><p><span
  m='1133370'>Well,</span> <span m='1133940'>to</span> <span
  m='1134060'>see</span> <span m='1134510'>how</span> <span m='1135080'>a</span>
  <span m='1136010'>linear</span> <span m='1136340'>constant</span> <span
  m='1136730'>coefficient</span> <span m='1137300'>difference</span> <span
  m='1137690'>equation</span> <span m='1138320'>can</span> <span
  m='1138500'>be</span> <span m='1138620'>represented</span> <span
  m='1139490'>in</span> <span m='1139640'>terms</span> <span
  m='1140210'>of</span> <span m='1140930'>linear</span> <span
  m='1141230'>signal</span> <span m='1141560'>flow</span> <span
  m='1141830'>graphs,</span> <span m='1142820'>let's</span> <span
  m='1143060'>take</span> <span m='1143300'>the</span> <span
  m='1143420'>same</span> <span m='1143720'>example</span> <span
  m='1144560'>that</span> <span m='1145130'>we</span> <span
  m='1147530'>worked</span> <span m='1147800'>with</span> <span
  m='1148010'>previously</span> <span m='1148790'>in</span> <span
  m='1148880'>terms</span> <span m='1149150'>of</span> <span
  m='1149250'>the</span> <span m='1149330'>block</span> <span
  m='1149600'>diagram</span> <span m='1150170'>notation,</span> <span
  m='1151340'>in</span> <span m='1151430'>other</span> <span
  m='1151640'>words,</span> <span m='1152250'>y</span> <span
  m='1152365'>of</span> <span m='1152480'>n</span> <span m='1152990'>is</span>
  <span m='1153110'>equal</span> <span m='1153440'>to</span> <span
  m='1153620'>a</span> <span m='1153860'>times</span> <span m='1154190'>y</span>
  <span m='1154470'>of</span> <span m='1154585'>n</span> <span
  m='1154700'>minus</span> <span m='1155120'>1</span> <span
  m='1155990'>plus</span> <span m='1156560'>x</span> <span m='1156860'>of</span>
  <span m='1157130'>n.</span> <span m='1159310'>Well,</span> <span
  m='1160030'>we</span> <span m='1161290'>have</span> <span m='1161620'>a</span>
  <span m='1161760'>node</span> <span m='1162400'>that's</span> <span
  m='1162670'>a</span> <span m='1162730'>source</span> <span
  m='1163120'>node.</span> <span m='1163420'>That's</span> <span
  m='1163660'>x</span> <span m='1164400'>of</span> <span m='1164885'>n.</span>
  <span m='1165370'>We</span> <span m='1165520'>have</span> <span
  m='1165690'>a</span> <span m='1165760'>node</span> <span
  m='1166000'>that's</span> <span m='1166240'>a</span> <span
  m='1166300'>sink</span> <span m='1166600'>node.</span> <span
  m='1167020'>That's</span> <span m='1167250'>y</span> <span
  m='1167500'>of</span> <span m='1167690'>n.</span> <span
  m='1167860'>That's</span> <span m='1168010'>what</span> <span
  m='1168160'>we'd</span> <span m='1168280'>like</span> <span
  m='1168460'>to</span> <span m='1168550'>get</span> <span
  m='1168700'>out</span> <span m='1168880'>of</span> <span
  m='1168970'>the</span> <span m='1169060'>network.</span> </p><p><span
  m='1170500'>And</span> <span m='1171580'>presumably</span> <span
  m='1172240'>somehow</span> <span m='1173260'>we've</span> <span
  m='1173500'>gotten</span> <span m='1174190'>a</span> <span
  m='1175240'>network</span> <span m='1175720'>node</span> <span
  m='1176260'>whose</span> <span m='1176500'>value</span> <span
  m='1177280'>will</span> <span m='1177460'>be</span> <span m='1177640'>y</span>
  <span m='1177940'>of</span> <span m='1178060'>n</span> <span
  m='1178210'>minus</span> <span m='1178630'>1.</span> <span
  m='1179830'>If</span> <span m='1180040'>we</span> <span
  m='1180220'>have</span> <span m='1180490'>that</span> <span
  m='1180730'>node,</span> <span m='1181630'>then</span> <span
  m='1182530'>what</span> <span m='1182740'>we</span> <span
  m='1182860'>want</span> <span m='1183070'>to</span> <span
  m='1183130'>form</span> <span m='1184120'>to</span> <span
  m='1184240'>get</span> <span m='1184420'>y</span> <span m='1184740'>of</span>
  <span m='1184860'>in</span> <span m='1186600'>is</span> <span
  m='1187710'>a</span> <span m='1187980'>times</span> <span m='1188400'>y</span>
  <span m='1188640'>of</span> <span m='1188760'>n</span> <span
  m='1188910'>minus</span> <span m='1189330'>1.</span> <span
  m='1190990'>So</span> <span m='1191220'>we</span> <span
  m='1191370'>want</span> <span m='1191580'>y</span> <span m='1191850'>of</span>
  <span m='1192090'>minus</span> <span m='1192480'>1</span> <span
  m='1193260'>multiplied</span> <span m='1193890'>by</span> <span
  m='1194190'>a,</span> <span m='1194610'>which</span> <span
  m='1194820'>means</span> <span m='1195300'>that</span> <span
  m='1196140'>this</span> <span m='1196350'>branch</span> <span
  m='1196890'>has</span> <span m='1197100'>a</span> <span
  m='1197160'>transmittance,</span> <span m='1199310'>or</span> <span
  m='1199530'>a</span> <span m='1199727'>gain,</span> <span
  m='1200320'>which</span> <span m='1200430'>is</span> <span
  m='1200600'>a.</span> <span m='1202590'>And</span> <span
  m='1202710'>then</span> <span m='1203490'>because</span> <span
  m='1203910'>of</span> <span m='1204000'>the</span> <span
  m='1204720'>algebraic</span> <span m='1205380'>definition</span> <span
  m='1206010'>at</span> <span m='1206100'>nodes,</span> <span
  m='1207210'>the</span> <span m='1208020'>value</span> <span
  m='1208410'>of</span> <span m='1208500'>this</span> <span
  m='1208740'>node</span> <span m='1209400'>is</span> <span
  m='1210000'>the</span> <span m='1210120'>sum</span> <span
  m='1210690'>of</span> <span m='1211440'>this</span> <span
  m='1211650'>branch</span> <span m='1212370'>and</span> <span
  m='1212970'>the</span> <span m='1213120'>output</span> <span
  m='1213450'>of</span> <span m='1213540'>this</span> <span
  m='1213750'>branch.</span> <span m='1214710'>So</span> <span
  m='1215370'>if</span> <span m='1215580'>this</span> <span
  m='1215790'>branch</span> <span m='1216270'>has</span> <span
  m='1216720'>a</span> <span m='1216780'>gain</span> <span m='1217110'>of</span>
  <span m='1217260'>unity,</span> <span m='1218760'>then</span> <span
  m='1219720'>this</span> <span m='1220020'>node</span> <span
  m='1220350'>variable</span> <span m='1221220'>will</span> <span
  m='1221400'>have</span> <span m='1221640'>the</span> <span
  m='1221730'>value</span> <span m='1222420'>x</span> <span
  m='1222730'>of</span> <span m='1223100'>n</span> <span m='1223470'>plus</span>
  <span m='1223830'>a</span> <span m='1224100'>times</span> <span
  m='1224550'>y</span> <span m='1224820'>the</span> <span
  m='1225060'>minus</span> <span m='1225480'>1.</span> </p><p><span
  m='1227290'>Well,</span> <span m='1228000'>now</span> <span
  m='1228240'>we</span> <span m='1228390'>simply</span> <span
  m='1228720'>have</span> <span m='1228900'>to</span> <span
  m='1228990'>get</span> <span m='1229200'>from</span> <span
  m='1229410'>here</span> <span m='1229860'>all</span> <span
  m='1230070'>the</span> <span m='1230130'>way</span> <span
  m='1230340'>out</span> <span m='1230500'>to</span> <span
  m='1230660'>there.</span> <span m='1231810'>I've</span> <span
  m='1231990'>drawn</span> <span m='1232320'>it,</span> <span
  m='1232980'>the</span> <span m='1233070'>network,</span> <span
  m='1233470'>somewhat</span> <span m='1233820'>inefficiently.</span> <span
  m='1235170'>I</span> <span m='1235260'>can</span> <span m='1235410'>get</span>
  <span m='1235590'>from</span> <span m='1235740'>this</span> <span
  m='1235920'>node</span> <span m='1236160'>to</span> <span
  m='1236310'>this</span> <span m='1236520'>node</span> <span
  m='1236850'>simply</span> <span m='1237210'>with</span> <span
  m='1237660'>a</span> <span m='1238200'>unity</span> <span
  m='1238650'>gain.</span> <span m='1240340'>From</span> <span
  m='1240490'>this</span> <span m='1240700'>node</span> <span
  m='1240970'>to</span> <span m='1241120'>the</span> <span
  m='1241270'>output</span> <span m='1241630'>node</span> <span
  m='1242600'>again,</span> <span m='1242830'>with</span> <span
  m='1242980'>the</span> <span m='1243040'>unity</span> <span
  m='1243400'>gain.</span> </p><p><span m='1246100'>And</span> <span
  m='1246820'>now</span> <span m='1247030'>the</span> <span
  m='1247150'>only</span> <span m='1247360'>question</span> <span
  m='1247840'>is--</span> <span m='1249470'>of</span> <span
  m='1249570'>course,</span> <span m='1249790'>if</span> <span
  m='1250000'>this</span> <span m='1250210'>is</span> <span m='1250330'>y</span>
  <span m='1250630'>of</span> <span m='1250750'>n,</span> <span
  m='1250870'>and</span> <span m='1251080'>this</span> <span
  m='1251260'>node</span> <span m='1251590'>has</span> <span
  m='1251920'>value</span> <span m='1252310'>y</span> <span
  m='1252580'>of</span> <span m='1252710'>n</span> <span
  m='1252850'>also--</span> <span m='1253780'>how</span> <span
  m='1253900'>do</span> <span m='1254080'>I</span> <span m='1254200'>get</span>
  <span m='1254740'>from</span> <span m='1254980'>this</span> <span
  m='1255220'>node</span> <span m='1256450'>to</span> <span
  m='1256600'>this</span> <span m='1256840'>node</span> <span
  m='1257410'>if</span> <span m='1257590'>I'm</span> <span
  m='1257680'>talking</span> <span m='1258130'>about</span> <span
  m='1258400'>a</span> <span m='1258460'>linear</span> <span
  m='1258790'>signal</span> <span m='1259120'>flow</span> <span
  m='1259390'>graph?</span> <span m='1260500'>Well,</span> <span
  m='1261900'>y</span> <span m='1262270'>of</span> <span m='1262390'>n</span>
  <span m='1262480'>minus</span> <span m='1262840'>1,</span> <span
  m='1263020'>of</span> <span m='1263110'>course,</span> <span
  m='1263470'>isn't</span> <span m='1263980'>a</span> <span
  m='1264220'>scalar</span> <span m='1264730'>multiplied</span> <span
  m='1265300'>by</span> <span m='1265510'>y</span> <span m='1265880'>of</span>
  <span m='1266380'>n.</span> <span m='1267400'>But</span> <span
  m='1267910'>y</span> <span m='1268180'>of</span> <span m='1268480'>z,</span>
  <span m='1270010'>or</span> <span m='1270330'>the</span> <span
  m='1270460'>z</span> <span m='1270640'>transform</span> <span
  m='1271270'>rather</span> <span m='1271570'>of</span> <span
  m='1271660'>y</span> <span m='1271900'>of</span> <span m='1272020'>n</span>
  <span m='1272140'>minus</span> <span m='1272530'>1</span> <span
  m='1272980'>is</span> <span m='1273280'>actually</span> <span
  m='1274360'>a</span> <span m='1274420'>scalar</span> <span
  m='1275030'>or</span> <span m='1275070'>a</span> <span
  m='1275110'>function</span> <span m='1275770'>multiplied</span> <span
  m='1276670'>by</span> <span m='1277000'>the</span> <span m='1277090'>z</span>
  <span m='1277300'>transform</span> <span m='1278200'>of</span> <span
  m='1278410'>y</span> <span m='1278680'>of</span> <span m='1278800'>n.</span>
  </p><p><span m='1279550'>So</span> <span m='1279940'>if</span> <span
  m='1280150'>I</span> <span m='1280300'>were</span> <span m='1280450'>to</span>
  <span m='1280600'>think</span> <span m='1280930'>of</span> <span
  m='1281050'>this</span> <span m='1282040'>rather</span> <span
  m='1282430'>than</span> <span m='1282820'>in</span> <span
  m='1283000'>terms</span> <span m='1283720'>of</span> <span
  m='1284980'>the</span> <span m='1285250'>sequences,</span> <span
  m='1286360'>if</span> <span m='1286510'>I</span> <span m='1286600'>were</span>
  <span m='1286750'>to</span> <span m='1286900'>think</span> <span
  m='1287200'>of</span> <span m='1287290'>this</span> <span
  m='1287710'>in</span> <span m='1287860'>terms</span> <span
  m='1288460'>of</span> <span m='1288700'>this</span> <span
  m='1289030'>transform,</span> <span m='1291340'>then</span> <span
  m='1291850'>in</span> <span m='1292000'>fact</span> <span
  m='1293500'>the</span> <span m='1293830'>z</span> <span
  m='1294070'>transform</span> <span m='1295810'>at</span> <span
  m='1295990'>this</span> <span m='1296230'>node</span> <span
  m='1297040'>would</span> <span m='1297250'>be</span> <span
  m='1297940'>z</span> <span m='1298280'>to</span> <span m='1298380'>the</span>
  <span m='1298480'>minus</span> <span m='1298900'>1</span> <span
  m='1299710'>times</span> <span m='1300820'>y</span> <span
  m='1301180'>of</span> <span m='1301622'>z.</span> <span m='1302950'>And</span>
  <span m='1303370'>consequently,</span> <span m='1304600'>thinking</span> <span
  m='1305020'>of</span> <span m='1305170'>it</span> <span m='1305620'>in</span>
  <span m='1305740'>terms</span> <span m='1306370'>of</span> <span
  m='1306640'>z</span> <span m='1306850'>transforms,</span> <span
  m='1308230'>the</span> <span m='1308740'>gain</span> <span
  m='1309250'>of</span> <span m='1309400'>this</span> <span
  m='1309640'>branch</span> <span m='1310330'>then</span> <span
  m='1310900'>is</span> <span m='1313200'>z</span> <span m='1313510'>to</span>
  <span m='1313690'>the</span> <span m='1313780'>minus</span> <span
  m='1314170'>1.</span> </p><p><span m='1315890'>So</span> <span
  m='1316760'>this,</span> <span m='1316970'>in</span> <span
  m='1317090'>fact</span> <span m='1317390'>does,</span> <span
  m='1317600'>correspond</span> <span m='1318200'>to</span> <span
  m='1318320'>multiplication</span> <span m='1319430'>by</span> <span
  m='1320420'>a</span> <span m='1320480'>function</span> <span
  m='1320960'>of</span> <span m='1321050'>z,</span> <span m='1321890'>as</span>
  <span m='1322040'>long</span> <span m='1322430'>as</span> <span
  m='1323300'>in</span> <span m='1323480'>the</span> <span
  m='1323600'>background</span> <span m='1324660'>what</span> <span
  m='1324740'>we</span> <span m='1324890'>remember</span> <span
  m='1325490'>is</span> <span m='1325760'>that</span> <span
  m='1326510'>we're</span> <span m='1326750'>essentially</span> <span
  m='1327260'>thinking</span> <span m='1327800'>of</span> <span
  m='1330140'>the</span> <span m='1330260'>flow</span> <span
  m='1330470'>graph</span> <span m='1330830'>as</span> <span
  m='1330950'>representing</span> <span m='1332150'>relationships</span> <span
  m='1332930'>between</span> <span m='1333260'>the</span> <span
  m='1333350'>z</span> <span m='1333530'>transform.</span> <span
  m='1334670'>Now,</span> <span m='1335000'>obviously,</span> <span
  m='1335810'>we</span> <span m='1336290'>wouldn't</span> <span
  m='1336530'>feel</span> <span m='1336800'>constrained</span> <span
  m='1337210'>to</span> <span m='1337320'>designate</span> <span
  m='1337800'>it</span> <span m='1338030'>that</span> <span
  m='1338240'>way</span> <span m='1338420'>all</span> <span
  m='1338600'>the</span> <span m='1338720'>time.</span> <span
  m='1339300'>In</span> <span m='1339400'>other</span> <span
  m='1339470'>words,</span> <span m='1340800'>I</span> <span
  m='1340900'>would</span> <span m='1341000'>feel</span> <span
  m='1341150'>very</span> <span m='1341390'>comfortable</span> <span
  m='1341900'>about</span> <span m='1342140'>drawing</span> <span
  m='1342530'>this</span> <span m='1342710'>flow</span> <span
  m='1342980'>graph</span> <span m='1343850'>and</span> <span
  m='1344000'>labeling</span> <span m='1344450'>this</span> <span
  m='1344630'>input</span> <span m='1344930'>as</span> <span
  m='1345080'>x</span> <span m='1345310'>of</span> <span m='1345460'>n,</span>
  <span m='1346340'>labeling</span> <span m='1346760'>this</span> <span
  m='1346940'>node</span> <span m='1347210'>is</span> <span m='1347330'>y</span>
  <span m='1347640'>of</span> <span m='1347830'>n,</span> <span
  m='1348020'>and</span> <span m='1348170'>this</span> <span
  m='1348350'>is</span> <span m='1348470'>y</span> <span m='1348740'>of</span>
  <span m='1348820'>n</span> <span m='1348980'>minus</span> <span
  m='1349400'>1,</span> <span m='1349835'>and</span> <span
  m='1350270'>indicating</span> <span m='1350870'>that</span> <span
  m='1351020'>this</span> <span m='1351170'>branch</span> <span
  m='1351620'>has</span> <span m='1351830'>a</span> <span
  m='1351890'>transmittance</span> <span m='1352550'>of</span> <span
  m='1352640'>z</span> <span m='1352880'>the</span> <span
  m='1353030'>minus</span> <span m='1353390'>1.</span> <span
  m='1353825'>Just</span> <span m='1354260'>simply</span> <span
  m='1354590'>in</span> <span m='1354650'>the</span> <span
  m='1354740'>background</span> <span m='1356230'>what</span> <span
  m='1356470'>we</span> <span m='1356600'>realize</span> <span
  m='1357330'>is</span> <span m='1357510'>it's</span> <span
  m='1357650'>not</span> <span m='1357860'>y</span> <span m='1358160'>of</span>
  <span m='1358280'>n</span> <span m='1358430'>that's</span> <span
  m='1358610'>multiplied</span> <span m='1359150'>by</span> <span
  m='1359330'>z</span> <span m='1359510'>to</span> <span m='1359600'>the</span>
  <span m='1359690'>minus</span> <span m='1360080'>1.</span> <span
  m='1360510'>It's</span> <span m='1361370'>y</span> <span m='1361670'>of</span>
  <span m='1361790'>z</span> <span m='1362030'>that's</span> <span
  m='1362180'>multiplied</span> <span m='1362690'>by</span> <span
  m='1362840'>z</span> <span m='1362950'>to</span> <span m='1363060'>the</span>
  <span m='1363170'>minus</span> <span m='1363550'>1.</span> </p><p><span
  m='1365460'>Also,</span> <span m='1366660'>notationally,</span> <span
  m='1367800'>it's</span> <span m='1368400'>usually</span> <span
  m='1368790'>convenient,</span> <span m='1370830'>since</span> <span
  m='1371520'>very</span> <span m='1371880'>often</span> <span
  m='1372300'>we</span> <span m='1372480'>end</span> <span m='1372690'>up</span>
  <span m='1372840'>with</span> <span m='1372990'>branches</span> <span
  m='1373500'>that</span> <span m='1373650'>have</span> <span
  m='1373860'>unity</span> <span m='1374270'>gain,</span> <span
  m='1375780'>to</span> <span m='1377370'>choose</span> <span
  m='1378120'>the</span> <span m='1378390'>convention</span> <span
  m='1379740'>that</span> <span m='1380190'>if</span> <span m='1381150'>a</span>
  <span m='1381360'>branch</span> <span m='1382560'>doesn't</span> <span
  m='1382890'>have</span> <span m='1383130'>the</span> <span
  m='1383220'>game</span> <span m='1383430'>labeled</span> <span
  m='1383910'>on</span> <span m='1384120'>it,</span> <span
  m='1384660'>the</span> <span m='1384810'>implication</span> <span
  m='1385530'>is</span> <span m='1386100'>that</span> <span
  m='1386430'>what</span> <span m='1386640'>the</span> <span
  m='1386730'>gain</span> <span m='1387090'>is,</span> <span
  m='1387450'>in</span> <span m='1387570'>fact,</span> <span
  m='1387930'>is</span> <span m='1388050'>unity.</span> <span
  m='1388950'>So</span> <span m='1389730'>generally,</span> <span
  m='1390540'>actually</span> <span m='1390990'>we</span> <span
  m='1391140'>won't</span> <span m='1392970'>specify</span> <span
  m='1393810'>explicitly</span> <span m='1394800'>unity</span> <span
  m='1395190'>gain.</span> <span m='1396480'>If</span> <span
  m='1397230'>there</span> <span m='1397470'>is</span> <span
  m='1397680'>a</span> <span m='1397740'>branch</span> <span
  m='1398040'>with</span> <span m='1398160'>unity</span> <span
  m='1398520'>gain,</span> <span m='1398820'>we</span> <span
  m='1398940'>simply</span> <span m='1399270'>won't</span> <span
  m='1399640'>label</span> <span m='1399850'>the</span> <span
  m='1400080'>gain.</span> </p><p><span m='1401520'>One</span> <span
  m='1401850'>final</span> <span m='1402240'>point</span> <span
  m='1402660'>and</span> <span m='1402750'>that</span> <span
  m='1402930'>is</span> <span m='1403230'>that</span> <span
  m='1404370'>you</span> <span m='1404580'>can,</span> <span
  m='1405510'>I</span> <span m='1405780'>think,</span> <span
  m='1406680'>see--</span> <span m='1407880'>you</span> <span
  m='1408030'>probably</span> <span m='1408930'>observed</span> <span
  m='1409350'>this</span> <span m='1409530'>for</span> <span
  m='1409620'>yourself</span> <span m='1410040'>already--</span> <span
  m='1411100'>that</span> <span m='1411570'>actually</span> <span
  m='1412080'>this</span> <span m='1412260'>flow</span> <span
  m='1412500'>graph</span> <span m='1412830'>is</span> <span
  m='1412950'>drawn</span> <span m='1413190'>somewhat</span> <span
  m='1413670'>inefficiently</span> <span m='1414600'>as</span> <span
  m='1414810'>I've</span> <span m='1415170'>indicated</span> <span
  m='1415850'>here.</span> <span m='1416640'>Basically,</span> <span
  m='1417240'>I</span> <span m='1417330'>can</span> <span
  m='1417480'>take</span> <span m='1417750'>these</span> <span
  m='1418020'>two</span> <span m='1418230'>nodes</span> <span
  m='1418710'>and</span> <span m='1418800'>collapse</span> <span
  m='1419250'>them</span> <span m='1419400'>together.</span> <span
  m='1421140'>I</span> <span m='1421980'>chose</span> <span
  m='1422370'>to</span> <span m='1422490'>draw</span> <span
  m='1423150'>this</span> <span m='1423360'>flow</span> <span
  m='1423630'>graph</span> <span m='1423990'>this</span> <span
  m='1424200'>way</span> <span m='1425070'>so</span> <span
  m='1425400'>that</span> <span m='1425730'>it</span> <span
  m='1425880'>looks</span> <span m='1426240'>as</span> <span
  m='1426420'>much</span> <span m='1426720'>like</span> <span
  m='1427080'>the</span> <span m='1427170'>block</span> <span
  m='1427470'>diagram</span> <span m='1428520'>representation</span> <span
  m='1429630'>as</span> <span m='1430380'>possible.</span> </p><p><span
  m='1431590'>And</span> <span m='1431610'>in</span> <span
  m='1431700'>fact,</span> <span m='1432100'>if</span> <span
  m='1432200'>you</span> <span m='1432210'>compare</span> <span
  m='1432600'>it</span> <span m='1432660'>back</span> <span
  m='1432930'>to</span> <span m='1433020'>the</span> <span
  m='1433110'>block</span> <span m='1433380'>diagram</span> <span
  m='1433860'>representation,</span> <span m='1434940'>it</span> <span
  m='1435600'>is</span> <span m='1435750'>basically</span> <span
  m='1436290'>the</span> <span m='1436380'>same</span> <span
  m='1436950'>except</span> <span m='1437310'>for</span> <span
  m='1437430'>the</span> <span m='1437550'>fact</span> <span
  m='1438300'>that</span> <span m='1438420'>we've</span> <span
  m='1438600'>chosen</span> <span m='1439050'>to</span> <span
  m='1439170'>represent</span> <span m='1439710'>this</span> <span
  m='1439890'>delay</span> <span m='1440190'>branch</span> <span
  m='1440580'>a</span> <span m='1440610'>little</span> <span
  m='1440850'>differently.</span> <span m='1441900'>And</span> <span
  m='1442020'>we've</span> <span m='1442200'>used</span> <span
  m='1442530'>the</span> <span m='1442800'>algebra</span> <span
  m='1444090'>of</span> <span m='1445260'>signal</span> <span
  m='1445620'>flow</span> <span m='1445920'>graphs</span> <span
  m='1446400'>to</span> <span m='1446550'>do</span> <span m='1446730'>the</span>
  <span m='1446850'>addition</span> <span m='1447390'>at</span> <span
  m='1447600'>nodes</span> <span m='1448380'>rather</span> <span
  m='1448710'>than</span> <span m='1448860'>explicitly</span> <span
  m='1449460'>putting</span> <span m='1449790'>in</span> <span
  m='1449910'>an</span> <span m='1450000'>adder.</span> <span
  m='1450330'>And</span> <span m='1450450'>that's</span> <span
  m='1450630'>really</span> <span m='1450900'>the</span> <span
  m='1451020'>only</span> <span m='1451290'>difference.</span> </p><p><span
  m='1455220'>Now,</span> <span m='1456790'>what</span> <span
  m='1457150'>a</span> <span m='1457660'>flow</span> <span
  m='1458080'>graph</span> <span m='1458800'>or</span> <span
  m='1458905'>a</span> <span m='1459010'>block</span> <span
  m='1459340'>diagram</span> <span m='1460210'>is,</span> <span
  m='1460780'>as</span> <span m='1460990'>I've</span> <span
  m='1461140'>stressed,</span> <span m='1461920'>is</span> <span
  m='1462370'>a</span> <span m='1462610'>graphical</span> <span
  m='1463240'>representation</span> <span m='1464470'>of</span> <span
  m='1465280'>that</span> <span m='1465400'>difference</span> <span
  m='1465820'>equation.</span> <span m='1467560'>And</span> <span
  m='1468190'>what</span> <span m='1468490'>it</span> <span
  m='1468910'>in</span> <span m='1469345'>turn</span> <span
  m='1469780'>corresponds</span> <span m='1470650'>to</span> <span
  m='1471610'>is</span> <span m='1472090'>a</span> <span
  m='1472330'>graphical</span> <span m='1472870'>representation</span> <span
  m='1474040'>of</span> <span m='1474700'>a</span> <span
  m='1475360'>linear</span> <span m='1476110'>set</span> <span
  m='1476380'>of</span> <span m='1476470'>equations,</span> <span
  m='1477040'>a</span> <span m='1477100'>set</span> <span m='1477340'>of</span>
  <span m='1477400'>equations,</span> <span m='1478670'>which</span> <span
  m='1479170'>describe</span> <span m='1479950'>the</span> <span
  m='1480550'>relationships</span> <span m='1481510'>among</span> <span
  m='1481960'>the</span> <span m='1482080'>various</span> <span
  m='1482500'>variables</span> <span m='1483340'>or</span> <span
  m='1484120'>among</span> <span m='1484750'>the</span> <span
  m='1484840'>nodes</span> <span m='1485380'>in</span> <span
  m='1485500'>the</span> <span m='1485590'>digital</span> <span
  m='1485920'>network.</span> <span m='1487690'>If</span> <span
  m='1487840'>I</span> <span m='1487930'>were,</span> <span
  m='1488870'>for</span> <span m='1488920'>example,</span> <span
  m='1489280'>going</span> <span m='1489490'>to</span> <span
  m='1489550'>implement</span> <span m='1490240'>a</span> <span
  m='1491260'>difference</span> <span m='1491650'>equation</span> <span
  m='1492040'>or</span> <span m='1492100'>a</span> <span
  m='1492130'>single</span> <span m='1492430'>flow</span> <span
  m='1492700'>graph</span> <span m='1493660'>on</span> <span
  m='1493780'>a</span> <span m='1493840'>digital</span> <span
  m='1494200'>computer,</span> <span m='1496540'>what</span> <span
  m='1497080'>I</span> <span m='1497260'>would</span> <span
  m='1497590'>implement</span> <span m='1498280'>in</span> <span
  m='1498370'>effect</span> <span m='1499450'>is</span> <span
  m='1500380'>not</span> <span m='1500890'>the</span> <span
  m='1501040'>graphics</span> <span m='1501940'>of</span> <span
  m='1502630'>the</span> <span m='1502780'>signal</span> <span
  m='1503140'>flow</span> <span m='1503440'>graph.</span> <span
  m='1504220'>I</span> <span m='1504370'>would</span> <span
  m='1504880'>implement</span> <span m='1505360'>the</span> <span
  m='1505510'>algebra</span> <span m='1506020'>of</span> <span
  m='1506110'>the</span> <span m='1506200'>signal</span> <span
  m='1506530'>flow</span> <span m='1506800'>graph.</span> <span
  m='1507380'>In</span> <span m='1507480'>other</span> <span
  m='1507550'>words,</span> <span m='1507920'>I</span> <span
  m='1507940'>would</span> <span m='1508090'>implement</span> <span
  m='1509350'>the</span> <span m='1509740'>linear</span> <span
  m='1510130'>set</span> <span m='1510370'>of</span> <span
  m='1510430'>equations</span> <span m='1511540'>that</span> <span
  m='1511960'>the</span> <span m='1512050'>flow</span> <span
  m='1512350'>graph</span> <span m='1512680'>corresponds</span> <span
  m='1513460'>to.</span> </p><p><span m='1515170'>Consequently,</span> <span
  m='1516280'>what</span> <span m='1516460'>I'd</span> <span
  m='1516610'>like</span> <span m='1517240'>to</span> <span
  m='1517660'>spend</span> <span m='1518020'>the</span> <span
  m='1518110'>remainder</span> <span m='1518500'>of</span> <span
  m='1518590'>the</span> <span m='1518680'>lecture</span> <span
  m='1519100'>on</span> <span m='1519640'>is</span> <span
  m='1520810'>focusing</span> <span m='1521560'>on</span> <span
  m='1522280'>the</span> <span m='1523090'>equivalent</span> <span
  m='1524320'>linear</span> <span m='1524710'>set</span> <span
  m='1524920'>of</span> <span m='1525010'>equations</span> <span
  m='1525790'>that</span> <span m='1525940'>the</span> <span
  m='1526060'>signal</span> <span m='1526360'>flow</span> <span
  m='1526660'>graph</span> <span m='1527350'>corresponds</span> <span
  m='1528130'>to,</span> <span m='1528970'>in</span> <span
  m='1529090'>other</span> <span m='1529270'>words,</span> <span
  m='1529970'>the</span> <span m='1530140'>matrix</span> <span
  m='1530620'>representation</span> <span m='1531730'>of</span> <span
  m='1532180'>a</span> <span m='1532240'>digital</span> <span
  m='1532600'>network.</span> <span m='1533680'>And</span> <span
  m='1534490'>the</span> <span m='1534760'>matrix</span> <span
  m='1535180'>representation</span> <span m='1536020'>is</span> <span
  m='1536140'>important</span> <span m='1537040'>from</span> <span
  m='1537700'>a</span> <span m='1537760'>number</span> <span
  m='1538690'>of</span> <span m='1538810'>points</span> <span
  m='1539170'>of</span> <span m='1539230'>view.</span> <span
  m='1540220'>One</span> <span m='1540460'>is,</span> <span
  m='1541060'>of</span> <span m='1541180'>course,</span> <span
  m='1541570'>that</span> <span m='1541840'>as</span> <span
  m='1542020'>I've</span> <span m='1542140'>just</span> <span
  m='1542350'>stressed</span> <span m='1542980'>it's</span> <span
  m='1543130'>important</span> <span m='1543700'>for</span> <span
  m='1544060'>the</span> <span m='1544180'>actual</span> <span
  m='1544630'>implementation</span> <span m='1545560'>of</span> <span
  m='1545710'>the</span> <span m='1545800'>digital</span> <span
  m='1546130'>network.</span> <span m='1547330'>It's</span> <span
  m='1547450'>also</span> <span m='1547780'>important</span> <span
  m='1548410'>in</span> <span m='1548550'>a</span> <span
  m='1548620'>sense</span> <span m='1549070'>that</span> <span
  m='1549700'>lots</span> <span m='1550030'>of</span> <span
  m='1550090'>properties</span> <span m='1550750'>of</span> <span
  m='1550840'>digital</span> <span m='1551200'>networks</span> <span
  m='1552310'>fall</span> <span m='1552760'>out</span> <span
  m='1553540'>from</span> <span m='1554590'>the</span> <span
  m='1555550'>properties</span> <span m='1556150'>of</span> <span
  m='1556240'>matrices.</span> <span m='1558580'>We</span> <span
  m='1558730'>won't,</span> <span m='1559060'>in</span> <span
  m='1559210'>fact,</span> <span m='1559640'>in</span> <span
  m='1559740'>this</span> <span m='1559750'>set</span> <span
  m='1559990'>of</span> <span m='1560320'>lectures</span> <span
  m='1560800'>be</span> <span m='1560950'>exploiting</span> <span
  m='1561880'>that</span> <span m='1562090'>particularly,</span> <span
  m='1563080'>but</span> <span m='1563850'>it</span> <span m='1564270'>is</span>
  <span m='1564700'>one</span> <span m='1564910'>of</span> <span
  m='1565030'>the</span> <span m='1565120'>reasons</span> <span
  m='1565660'>why</span> <span m='1565870'>the</span> <span
  m='1565960'>matrix</span> <span m='1566620'>representation</span> <span
  m='1567430'>of</span> <span m='1567490'>digital</span> <span
  m='1567850'>networks</span> <span m='1568360'>is</span> <span
  m='1568510'>also</span> <span m='1568930'>important</span> <span
  m='1569410'>to</span> <span m='1569560'>be</span> <span
  m='1569680'>aware</span> <span m='1570010'>of.</span> </p><p><span
  m='1571910'>So</span> <span m='1572860'>let's</span> <span
  m='1573430'>then</span> <span m='1573910'>see</span> <span
  m='1574300'>what</span> <span m='1574840'>this</span> <span
  m='1575290'>graphical</span> <span m='1575830'>representation,</span> <span
  m='1576910'>or</span> <span m='1577090'>the</span> <span
  m='1577210'>linear</span> <span m='1577480'>single</span> <span
  m='1577780'>flow</span> <span m='1578035'>graph</span> <span
  m='1578290'>representation,</span> <span m='1579970'>corresponds</span> <span
  m='1580780'>to</span> <span m='1581110'>in</span> <span
  m='1581260'>terms</span> <span m='1581650'>of</span> <span
  m='1581740'>a</span> <span m='1581800'>set</span> <span m='1582220'>of</span>
  <span m='1582580'>linear</span> <span m='1582970'>equations,</span> <span
  m='1583600'>or</span> <span m='1583690'>in</span> <span
  m='1583780'>terms</span> <span m='1584080'>of</span> <span
  m='1584140'>a</span> <span m='1584170'>set</span> <span m='1584380'>of</span>
  <span m='1584470'>matrices.</span> <span m='1586210'>So</span> <span
  m='1586720'>we're</span> <span m='1587050'>considering</span> <span
  m='1587720'>then</span> <span m='1589340'>a</span> <span
  m='1589440'>general</span> <span m='1590160'>network.</span> <span
  m='1591270'>It</span> <span m='1591360'>has</span> <span
  m='1591960'>some</span> <span m='1592260'>internal</span> <span
  m='1592710'>nodes,</span> <span m='1593160'>branches,</span> <span
  m='1593610'>coming</span> <span m='1593940'>into</span> <span
  m='1594210'>them.</span> <span m='1595560'>I've</span> <span
  m='1595740'>indicated</span> <span m='1596250'>one</span> <span
  m='1596490'>source</span> <span m='1596880'>node</span> <span
  m='1597110'>and</span> <span m='1597190'>one</span> <span
  m='1597390'>sink</span> <span m='1597750'>node.</span> <span
  m='1598470'>More</span> <span m='1598650'>generally,</span> <span
  m='1599190'>there</span> <span m='1599340'>would</span> <span
  m='1599460'>be</span> <span m='1599580'>a</span> <span m='1599610'>set</span>
  <span m='1599880'>of</span> <span m='1599970'>source</span> <span
  m='1600360'>nodes</span> <span m='1600660'>and</span> <span
  m='1600750'>a</span> <span m='1600810'>set</span> <span m='1601020'>of</span>
  <span m='1601110'>sink</span> <span m='1601410'>nodes.</span> </p><p><span
  m='1603060'>The</span> <span m='1603690'>algebraic</span> <span
  m='1604410'>equations</span> <span m='1605670'>that</span> <span
  m='1606330'>the</span> <span m='1606930'>flow</span> <span
  m='1607260'>graph</span> <span m='1607980'>corresponds</span> <span
  m='1608790'>to</span> <span m='1609780'>is</span> <span m='1610320'>a</span>
  <span m='1610410'>statement</span> <span m='1614760'>of</span> <span
  m='1614970'>how</span> <span m='1615330'>the</span> <span
  m='1615450'>node</span> <span m='1615840'>variables</span> <span
  m='1616650'>are</span> <span m='1616830'>related</span> <span
  m='1617280'>to</span> <span m='1617490'>each</span> <span
  m='1617700'>other.</span> <span m='1618510'>And</span> <span
  m='1619770'>just</span> <span m='1619980'>to</span> <span
  m='1620130'>remind</span> <span m='1620490'>you</span> <span
  m='1620610'>of</span> <span m='1620700'>how</span> <span
  m='1620910'>that's</span> <span m='1621150'>generated--</span> <span
  m='1623230'>and</span> <span m='1623340'>I'm</span> <span
  m='1623490'>expressing</span> <span m='1623970'>this</span> <span
  m='1624120'>now</span> <span m='1624300'>in</span> <span
  m='1624360'>terms</span> <span m='1624660'>of</span> <span
  m='1624720'>the</span> <span m='1624840'>z</span> <span
  m='1625020'>transforms</span> <span m='1625890'>of</span> <span
  m='1626010'>the</span> <span m='1626100'>node</span> <span
  m='1626310'>variables--</span> <span m='1627660'>the</span> <span
  m='1628020'>z</span> <span m='1628200'>transform</span> <span
  m='1628710'>of</span> <span m='1628770'>the</span> <span
  m='1628970'>k-th</span> <span m='1629200'>node</span> <span
  m='1629430'>variable</span> <span m='1630540'>is</span> <span
  m='1630780'>the</span> <span m='1630870'>sum</span> <span
  m='1631440'>over</span> <span m='1631830'>the</span> <span
  m='1631920'>network</span> <span m='1632430'>nodes</span> <span
  m='1633930'>of</span> <span m='1634560'>the</span> <span
  m='1634860'>branch</span> <span m='1635340'>outputs--</span> <span
  m='1636540'>that's</span> <span m='1636960'>indicated</span> <span
  m='1637560'>here--</span> <span m='1638490'>plus</span> <span
  m='1639120'>the</span> <span m='1639420'>sum</span> <span
  m='1640020'>over</span> <span m='1640740'>the</span> <span
  m='1641550'>source</span> <span m='1643020'>branch</span> <span
  m='1643590'>outputs.</span> </p><p><span m='1645090'>And</span> <span
  m='1646110'>incidentally,</span> <span m='1647130'>I've</span> <span
  m='1648000'>assumed</span> <span m='1648450'>that</span> <span
  m='1648570'>it's</span> <span m='1648720'>just--</span> <span
  m='1649890'>best</span> <span m='1650190'>to</span> <span
  m='1650310'>assume</span> <span m='1650640'>this</span> <span
  m='1651000'>because</span> <span m='1651360'>of</span> <span
  m='1651450'>notational</span> <span m='1652020'>convenience--</span> <span
  m='1653190'>that</span> <span m='1653310'>there's</span> <span
  m='1653520'>a</span> <span m='1653580'>branch</span> <span
  m='1653970'>from</span> <span m='1654150'>every</span> <span
  m='1654480'>network</span> <span m='1654930'>node</span> <span
  m='1655140'>to</span> <span m='1655230'>every</span> <span
  m='1655500'>other</span> <span m='1655680'>network</span> <span
  m='1656160'>node.</span> <span m='1656910'>Obviously</span> <span
  m='1657480'>I</span> <span m='1657600'>can</span> <span
  m='1657750'>always</span> <span m='1658020'>get</span> <span
  m='1658140'>away</span> <span m='1658410'>with</span> <span
  m='1658590'>that.</span> <span m='1659310'>If</span> <span
  m='1659760'>that</span> <span m='1659940'>branch</span> <span
  m='1660270'>doesn't</span> <span m='1660510'>really</span> <span
  m='1660780'>exist,</span> <span m='1661140'>I</span> <span
  m='1661230'>simply</span> <span m='1661590'>set</span> <span
  m='1662130'>the</span> <span m='1662580'>gain</span> <span
  m='1663060'>of</span> <span m='1663480'>that</span> <span
  m='1663690'>branch</span> <span m='1664050'>equal</span> <span
  m='1664320'>to</span> <span m='1664440'>zero.</span> </p><p><span
  m='1666210'>Now,</span> <span m='1666570'>furthermore,</span> <span
  m='1667170'>we</span> <span m='1667320'>have</span> <span
  m='1667500'>the</span> <span m='1667590'>relationship</span> <span
  m='1668520'>that</span> <span m='1668730'>defines</span> <span
  m='1669570'>what</span> <span m='1669780'>the</span> <span
  m='1669900'>branch</span> <span m='1670290'>output</span> <span
  m='1670770'>is</span> <span m='1671490'>in</span> <span
  m='1671640'>terms</span> <span m='1672180'>of</span> <span
  m='1672450'>the</span> <span m='1672570'>branch</span> <span
  m='1672960'>input</span> <span m='1673350'>or</span> <span
  m='1673500'>in</span> <span m='1673620'>terms</span> <span
  m='1674040'>of</span> <span m='1674220'>the</span> <span
  m='1674310'>node</span> <span m='1674580'>variables.</span> <span
  m='1675970'>So</span> <span m='1676470'>we</span> <span
  m='1676620'>have</span> <span m='1676800'>specifically</span> <span
  m='1677490'>the</span> <span m='1677610'>statement</span> <span
  m='1678330'>that</span> <span m='1678480'>v</span> <span
  m='1678675'>sub</span> <span m='1678870'>jk,</span> <span
  m='1679890'>the</span> <span m='1680040'>output</span> <span
  m='1680310'>of</span> <span m='1680370'>the</span> <span
  m='1680460'>jk-th</span> <span m='1681060'>branch,</span> <span
  m='1682380'>is</span> <span m='1682470'>some</span> <span
  m='1682770'>function</span> <span m='1683520'>of</span> <span
  m='1683640'>z</span> <span m='1685830'>multiplied</span> <span
  m='1686670'>by</span> <span m='1687390'>the</span> <span
  m='1687510'>branch</span> <span m='1687900'>input.</span> <span
  m='1689390'>And</span> <span m='1690120'>furthermore,</span> <span
  m='1690990'>the</span> <span m='1691290'>source</span> <span
  m='1691710'>branch</span> <span m='1692130'>output</span> <span
  m='1693180'>is</span> <span m='1693840'>some</span> <span
  m='1694710'>function,</span> <span m='1695220'>or</span> <span
  m='1695340'>scalar,</span> <span m='1696330'>multiplied</span> <span
  m='1697350'>by</span> <span m='1698400'>the</span> <span
  m='1699000'>source</span> <span m='1699900'>node</span> <span
  m='1700520'>value.</span> </p><p><span m='1702880'>Well,</span> <span
  m='1703290'>if</span> <span m='1703470'>we</span> <span
  m='1703590'>substitute</span> <span m='1704160'>these</span> <span
  m='1704430'>two</span> <span m='1704610'>equations</span> <span
  m='1705450'>into</span> <span m='1705900'>the</span> <span
  m='1706020'>previous</span> <span m='1706470'>equation,</span> <span
  m='1706950'>which</span> <span m='1707160'>defined</span> <span
  m='1707970'>what</span> <span m='1708120'>the</span> <span
  m='1708210'>node</span> <span m='1709140'>values</span> <span
  m='1709650'>are,</span> <span m='1711180'>we</span> <span
  m='1711330'>end</span> <span m='1711480'>up</span> <span
  m='1711660'>with</span> <span m='1711750'>a</span> <span
  m='1711810'>statement</span> <span m='1712290'>that</span> <span
  m='1712440'>says</span> <span m='1713100'>that</span> <span
  m='1713400'>the</span> <span m='1713850'>node</span> <span
  m='1714330'>variables</span> <span m='1717120'>are</span> <span
  m='1717360'>equal</span> <span m='1717660'>to</span> <span
  m='1718470'>a</span> <span m='1718500'>linear</span> <span
  m='1718860'>combination</span> <span m='1719910'>of</span> <span
  m='1721110'>the</span> <span m='1721500'>node</span> <span
  m='1721830'>variables,</span> <span m='1722910'>the</span> <span
  m='1723000'>linear</span> <span m='1723300'>combination</span> <span
  m='1723960'>specified</span> <span m='1724800'>by</span> <span
  m='1725370'>the</span> <span m='1725640'>branch</span> <span
  m='1726010'>transmit</span> <span m='1726480'>answers,</span> <span
  m='1727860'>plus</span> <span m='1728460'>a</span> <span
  m='1728520'>linear</span> <span m='1728850'>combination</span> <span
  m='1729840'>of</span> <span m='1730620'>the</span> <span
  m='1731160'>source</span> <span m='1733570'>node</span> <span
  m='1734050'>values.</span> <span m='1735340'>And</span> <span
  m='1736090'>this</span> <span m='1736390'>then</span> <span
  m='1736780'>is</span> <span m='1737320'>a</span> <span m='1737380'>set</span>
  <span m='1737770'>of</span> <span m='1737920'>linear</span> <span
  m='1738250'>equations</span> <span m='1739450'>that,</span> <span
  m='1740570'>in</span> <span m='1740590'>essence,</span> <span
  m='1741280'>defines</span> <span m='1741970'>the</span> <span
  m='1742030'>digital</span> <span m='1742420'>network.</span> <span
  m='1744590'>This</span> <span m='1744670'>is</span> <span m='1744970'>a</span>
  <span m='1745030'>set</span> <span m='1745210'>of</span> <span
  m='1745300'>equations,</span> <span m='1745810'>of</span> <span
  m='1745900'>course,</span> <span m='1746230'>because</span> <span
  m='1747460'>we</span> <span m='1747640'>have</span> <span
  m='1747970'>an</span> <span m='1748060'>equation</span> <span
  m='1748510'>like</span> <span m='1748810'>this</span> <span
  m='1749500'>for</span> <span m='1749680'>each</span> <span
  m='1749860'>value</span> <span m='1750280'>of</span> <span
  m='1750370'>k</span> <span m='1750850'>as</span> <span m='1751000'>k</span>
  <span m='1751240'>runs</span> <span m='1751570'>over</span> <span
  m='1752020'>all</span> <span m='1752260'>the</span> <span
  m='1752350'>network</span> <span m='1752770'>nodes,</span> <span
  m='1753160'>in</span> <span m='1753250'>other</span> <span
  m='1753430'>words,</span> <span m='1754090'>for</span> <span
  m='1754210'>k</span> <span m='1754660'>starting</span> <span
  m='1755080'>from</span> <span m='1755290'>1</span> <span
  m='1755500'>and</span> <span m='1755620'>running</span> <span
  m='1755860'>up</span> <span m='1755990'>to</span> <span m='1756140'>n.</span>
  </p><p><span m='1758370'>We</span> <span m='1758520'>can</span> <span
  m='1759060'>express</span> <span m='1759930'>the</span> <span
  m='1760060'>set</span> <span m='1760290'>of</span> <span
  m='1760410'>linear</span> <span m='1760740'>equations</span> <span
  m='1761580'>in</span> <span m='1762060'>matrix</span> <span
  m='1762570'>notation.</span> <span m='1764610'>If</span> <span
  m='1764790'>we</span> <span m='1765330'>think</span> <span
  m='1765720'>of</span> <span m='1766230'>a</span> <span
  m='1766500'>column</span> <span m='1766920'>vector</span> <span
  m='1767370'>corresponding</span> <span m='1768390'>to</span> <span
  m='1769110'>the</span> <span m='1769890'>node</span> <span
  m='1770220'>variables,</span> <span m='1772380'>then</span> <span
  m='1772890'>this</span> <span m='1773130'>equation</span> <span
  m='1773670'>says</span> <span m='1774690'>that</span> <span
  m='1775500'>the</span> <span m='1777150'>vector</span> <span
  m='1777690'>or</span> <span m='1778710'>column</span> <span
  m='1779580'>matrix</span> <span m='1780660'>of</span> <span
  m='1781350'>node</span> <span m='1781650'>variables</span> <span
  m='1782940'>is</span> <span m='1783090'>equal</span> <span
  m='1783540'>to</span> <span m='1784290'>a</span> <span
  m='1784350'>matrix</span> <span m='1784800'>of</span> <span
  m='1784920'>coefficients</span> <span m='1785940'>dictated</span> <span
  m='1786510'>by</span> <span m='1786660'>the</span> <span
  m='1786780'>branch</span> <span m='1787110'>transmittances</span> <span
  m='1788730'>multiplied</span> <span m='1789390'>again</span> <span
  m='1789960'>by</span> <span m='1790200'>the</span> <span
  m='1790290'>node</span> <span m='1790530'>variables</span> <span
  m='1792030'>plus</span> <span m='1792540'>a</span> <span
  m='1792600'>second</span> <span m='1793320'>matrix</span> <span
  m='1795180'>multiplied</span> <span m='1796080'>by</span> <span
  m='1796740'>the</span> <span m='1796980'>column</span> <span
  m='1797580'>of</span> <span m='1798270'>source</span> <span
  m='1799530'>node</span> <span m='1799860'>values.</span> </p><p><span
  m='1802140'>And</span> <span m='1802950'>there</span> <span
  m='1803190'>is</span> <span m='1803460'>one</span> <span
  m='1803880'>peculiar</span> <span m='1804390'>thing</span> <span
  m='1804870'>that</span> <span m='1805050'>happens</span> <span
  m='1805890'>notationally</span> <span m='1806640'>here,</span> <span
  m='1806940'>which</span> <span m='1807480'>it's</span> <span
  m='1808080'>worthwhile</span> <span m='1808620'>to</span> <span
  m='1808770'>straighten</span> <span m='1809190'>out.</span> <span
  m='1811240'>It</span> <span m='1811390'>happens</span> <span
  m='1811870'>because</span> <span m='1812200'>of</span> <span
  m='1812320'>the</span> <span m='1812410'>way</span> <span
  m='1813070'>that</span> <span m='1813310'>we</span> <span
  m='1813430'>chose</span> <span m='1813790'>to</span> <span
  m='1813910'>write</span> <span m='1814150'>these</span> <span
  m='1814390'>equations</span> <span m='1815650'>that</span> <span
  m='1817000'>the</span> <span m='1817240'>branch</span> <span
  m='1817630'>transmittance</span> <span m='1818980'>values</span> <span
  m='1820690'>come</span> <span m='1820960'>in</span> <span
  m='1821380'>to</span> <span m='1822040'>the</span> <span
  m='1822610'>matrix,</span> <span m='1824210'>as</span> <span
  m='1824440'>I've</span> <span m='1824590'>indicated</span> <span
  m='1825160'>here.</span> <span m='1825530'>So</span> <span
  m='1825610'>the</span> <span m='1825700'>first</span> <span
  m='1826060'>row,</span> <span m='1826270'>for</span> <span
  m='1826420'>example,</span> <span m='1827210'>contains</span> <span
  m='1827530'>F</span> <span m='1827957'>1</span> <span m='1828384'>1,</span>
  <span m='1828811'>F2</span> <span m='1829240'>through</span> <span
  m='1829540'>F</span> <span m='1829820'>sub</span> <span m='1829970'>N1.</span>
  <span m='1831280'>As</span> <span m='1832000'>you're</span> <span
  m='1832180'>well</span> <span m='1832390'>aware,</span> <span
  m='1833410'>typically</span> <span m='1834220'>in</span> <span
  m='1835120'>defining</span> <span m='1835630'>a</span> <span
  m='1835690'>matrix</span> <span m='1836760'>and</span> <span
  m='1836890'>matrix</span> <span m='1837310'>elements,</span> <span
  m='1838390'>the</span> <span m='1838690'>general</span> <span
  m='1839380'>convention</span> <span m='1840190'>is</span> <span
  m='1840400'>to</span> <span m='1840550'>refer</span> <span
  m='1841060'>to</span> <span m='1841210'>the</span> <span
  m='1841300'>matrix</span> <span m='1841720'>elements</span> <span
  m='1842710'>with</span> <span m='1842890'>the</span> <span
  m='1842980'>first</span> <span m='1843280'>index</span> <span
  m='1843640'>corresponding</span> <span m='1844240'>to</span> <span
  m='1844360'>the</span> <span m='1844450'>row,</span> <span
  m='1844680'>the</span> <span m='1844780'>second</span> <span
  m='1845080'>index</span> <span m='1845410'>corresponding</span> <span
  m='1846100'>to</span> <span m='1846190'>the</span> <span
  m='1846280'>column.</span> <span m='1847300'>So</span> <span
  m='1847630'>the</span> <span m='1849680'>tendency</span> <span
  m='1850310'>is</span> <span m='1850670'>to</span> <span
  m='1850850'>refer</span> <span m='1851210'>to</span> <span
  m='1851330'>the</span> <span m='1851420'>matrix</span> <span
  m='1851870'>elements</span> <span m='1852770'>as</span> <span
  m='1853160'>A1</span> <span m='1853610'>1,</span> <span m='1854060'>A</span>
  <span m='1854510'>1</span> <span m='1854750'>2</span> <span
  m='1855200'>through</span> <span m='1855470'>A</span> <span
  m='1855890'>1N,</span> <span m='1856730'>etc.</span> </p><p><span
  m='1858020'>So</span> <span m='1859490'>that</span> <span
  m='1859670'>simply</span> <span m='1860060'>means</span> <span
  m='1860630'>that</span> <span m='1861170'>in</span> <span
  m='1861800'>writing</span> <span m='1862250'>this</span> <span
  m='1862400'>set</span> <span m='1862580'>of</span> <span
  m='1862670'>equations</span> <span m='1864230'>in</span> <span
  m='1864440'>compact</span> <span m='1865040'>matrix</span> <span
  m='1866240'>form,</span> <span m='1868220'>it's</span> <span
  m='1868700'>convenient</span> <span m='1869300'>to</span> <span
  m='1869450'>do</span> <span m='1869660'>that</span> <span
  m='1870320'>by</span> <span m='1870530'>referring</span> <span
  m='1871100'>to</span> <span m='1871490'>the</span> <span
  m='1871610'>transpose</span> <span m='1872660'>of</span> <span
  m='1873680'>a</span> <span m='1873710'>matrix</span> <span
  m='1874400'>of</span> <span m='1874670'>coefficients</span> <span
  m='1875510'>rather</span> <span m='1875900'>than</span> <span
  m='1876530'>directly</span> <span m='1876980'>to</span> <span
  m='1877100'>the</span> <span m='1877190'>matrix</span> <span
  m='1877580'>of</span> <span m='1877640'>coefficients</span> <span
  m='1878330'>itself.</span> <span m='1878850'>In</span> <span
  m='1878950'>other</span> <span m='1878990'>words,</span> <span
  m='1879780'>it's</span> <span m='1879880'>convenient</span> <span
  m='1880430'>when</span> <span m='1880640'>I</span> <span
  m='1881030'>write</span> <span m='1881540'>this</span> <span
  m='1881720'>set</span> <span m='1881930'>of</span> <span
  m='1882020'>equations,</span> <span m='1882740'>or</span> <span
  m='1882870'>a</span> <span m='1882930'>set</span> <span m='1883160'>of</span>
  <span m='1883220'>equations</span> <span m='1884490'>in</span> <span
  m='1884660'>compact</span> <span m='1885290'>matrix</span> <span
  m='1885740'>notation,</span> <span m='1887390'>to</span> <span
  m='1887990'>write</span> <span m='1888290'>it</span> <span
  m='1888550'>as</span> <span m='1888800'>I've</span> <span
  m='1888950'>indicated</span> <span m='1889550'>here.</span> <span
  m='1891800'>We</span> <span m='1891950'>have</span> <span m='1892610'>a</span>
  <span m='1892670'>column</span> <span m='1893060'>vector</span> <span
  m='1893750'>of</span> <span m='1894740'>node</span> <span
  m='1895040'>values,</span> <span m='1895415'>node</span> <span
  m='1896060'>variables,</span> <span m='1897590'>equal</span> <span
  m='1898070'>to</span> <span m='1898640'>a</span> <span
  m='1899840'>transpose</span> <span m='1901190'>coefficient</span> <span
  m='1901850'>matrix</span> <span m='1902990'>multiplied</span> <span
  m='1903860'>by</span> <span m='1904760'>the</span> <span
  m='1905090'>column</span> <span m='1905450'>vector</span> <span
  m='1905900'>of</span> <span m='1906050'>node</span> <span
  m='1906770'>variables.</span> <span m='1908000'>And</span> <span
  m='1908150'>then</span> <span m='1908600'>the</span> <span
  m='1908810'>transpose</span> <span m='1909740'>of</span> <span
  m='1910580'>the</span> <span m='1910940'>transmittances</span> <span
  m='1911930'>that</span> <span m='1912050'>connect</span> <span
  m='1912380'>the</span> <span m='1912470'>sources</span> <span
  m='1912980'>to</span> <span m='1913100'>the</span> <span
  m='1913250'>internal</span> <span m='1913670'>network</span> <span
  m='1914120'>nodes</span> <span m='1914930'>multiplied</span> <span
  m='1915620'>by</span> <span m='1916280'>the</span> <span
  m='1916550'>source</span> <span m='1916940'>vector,</span> <span
  m='1918650'>where</span> <span m='1919070'>the</span> <span
  m='1919190'>matrix</span> <span m='1919790'>F</span> <span
  m='1920060'>of</span> <span m='1920210'>z,</span> <span m='1921180'>the</span>
  <span m='1921670'>jk-th</span> <span m='1921980'>element</span> <span
  m='1922430'>of</span> <span m='1922550'>the</span> <span
  m='1922640'>matrix</span> <span m='1923120'>F</span> <span
  m='1923330'>of</span> <span m='1923450'>z</span> <span m='1923990'>is</span>
  <span m='1924550'>F</span> <span m='1924780'>sub</span> <span
  m='1925055'>jk</span> <span m='1925770'>of</span> <span m='1925970'>z.</span>
  </p><p><span m='1927920'>I</span> <span m='1927980'>think</span> <span
  m='1928250'>that</span> <span m='1928520'>it</span> <span
  m='1929480'>takes</span> <span m='1929780'>just</span> <span
  m='1929960'>a</span> <span m='1930020'>few</span> <span
  m='1930200'>minutes</span> <span m='1930530'>of</span> <span
  m='1931220'>private</span> <span m='1931640'>reflection</span> <span
  m='1932360'>to</span> <span m='1932720'>see</span> <span
  m='1933050'>that</span> <span m='1933470'>this</span> <span
  m='1933680'>works</span> <span m='1933980'>out</span> <span
  m='1934190'>notationally.</span> <span m='1935560'>But</span> <span
  m='1936030'>it's</span> <span m='1936260'>this</span> <span
  m='1936530'>reason,</span> <span m='1936950'>it's</span> <span
  m='1938200'>to</span> <span m='1938420'>interface</span> <span
  m='1939140'>the</span> <span m='1939470'>matrix</span> <span
  m='1939890'>notation</span> <span m='1940490'>and</span> <span
  m='1940580'>the</span> <span m='1940625'>flow</span> <span
  m='1940670'>graph</span> <span m='1941210'>notation</span> <span
  m='1942350'>that</span> <span m='1942470'>makes</span> <span
  m='1942740'>it</span> <span m='1942800'>convenient</span> <span
  m='1943730'>to</span> <span m='1944510'>refer</span> <span
  m='1944900'>to</span> <span m='1945020'>the</span> <span
  m='1945110'>transpose,</span> <span m='1946040'>to</span> <span
  m='1946190'>a</span> <span m='1946250'>transpose</span> <span
  m='1946850'>matrix</span> <span m='1947330'>here,</span> <span
  m='1947930'>rather</span> <span m='1948260'>than</span> <span
  m='1949130'>omitting</span> <span m='1949610'>the</span> <span
  m='1949670'>transposition.</span> </p><p><span m='1953450'>It's</span> <span
  m='1954860'>typical</span> <span m='1955790'>and</span> <span
  m='1956420'>notationally</span> <span m='1957200'>what</span> <span
  m='1957740'>will</span> <span m='1957950'>also</span> <span
  m='1958340'>stick</span> <span m='1958700'>with</span> <span
  m='1959570'>in</span> <span m='1960470'>representing</span> <span
  m='1961520'>a</span> <span m='1961760'>digital</span> <span
  m='1962180'>network</span> <span m='1964190'>with</span> <span
  m='1964700'>flow</span> <span m='1964970'>graph</span> <span
  m='1965300'>notation</span> <span m='1966800'>to</span> <span
  m='1968840'>restrict</span> <span m='1969350'>ourselves</span> <span
  m='1970220'>always</span> <span m='1971330'>to</span> <span
  m='1971480'>branches</span> <span m='1972890'>that</span> <span
  m='1973670'>are</span> <span m='1974000'>either</span> <span
  m='1974540'>simply</span> <span m='1974960'>co-efficient</span> <span
  m='1975620'>branches--</span> <span m='1976160'>in</span> <span
  m='1976250'>other</span> <span m='1976400'>words,</span> <span
  m='1976950'>they</span> <span m='1977030'>correspond</span> <span
  m='1977570'>to</span> <span m='1977690'>multiplication</span> <span
  m='1978440'>by</span> <span m='1978650'>a</span> <span
  m='1978680'>scalar--</span> <span m='1980090'>or</span> <span
  m='1980640'>they're</span> <span m='1980810'>simply</span> <span
  m='1981230'>delay</span> <span m='1981590'>branches.</span> <span
  m='1982220'>In</span> <span m='1982310'>other</span> <span
  m='1982490'>words,</span> <span m='1983010'>they</span> <span
  m='1983870'>have</span> <span m='1984110'>a</span> <span
  m='1984140'>transmittance</span> <span m='1985160'>which</span> <span
  m='1985550'>is</span> <span m='1985960'>z</span> <span m='1986150'>to</span>
  <span m='1986270'>the</span> <span m='1986390'>minus</span> <span
  m='1986780'>1.</span> </p><p><span m='1988772'>And</span> <span
  m='1989270'>with</span> <span m='1989540'>that</span> <span
  m='1989780'>restriction,</span> <span m='1990860'>it's</span> <span
  m='1991070'>convenient</span> <span m='1992060'>for</span> <span
  m='1992780'>a</span> <span m='1992840'>number</span> <span
  m='1993380'>of</span> <span m='1993560'>reasons,</span> <span
  m='1994100'>and</span> <span m='1994190'>in</span> <span
  m='1994310'>particular</span> <span m='1994730'>for</span> <span
  m='1994880'>developing</span> <span m='1995420'>some</span> <span
  m='1995600'>network</span> <span m='1995990'>properties,</span> <span
  m='1997400'>to</span> <span m='1998030'>consider</span> <span
  m='1999860'>decomposing</span> <span m='2001840'>this</span> <span
  m='2002470'>matrix</span> <span m='2002980'>equation</span> <span
  m='2004270'>in</span> <span m='2004390'>such</span> <span m='2004690'>a</span>
  <span m='2004750'>way</span> <span m='2005410'>that</span> <span
  m='2005590'>we</span> <span m='2005740'>separate</span> <span
  m='2006400'>out</span> <span m='2006910'>with</span> <span
  m='2007390'>the</span> <span m='2007480'>matrix</span> <span
  m='2007960'>F</span> <span m='2008140'>transpose</span> <span
  m='2008860'>of</span> <span m='2008980'>z</span> <span m='2010080'>the</span>
  <span m='2010210'>part</span> <span m='2010510'>of</span> <span
  m='2010630'>that</span> <span m='2010840'>matrix</span> <span
  m='2011800'>that</span> <span m='2015160'>doesn't</span> <span
  m='2015580'>involve</span> <span m='2016000'>any</span> <span
  m='2016180'>delay</span> <span m='2016540'>terms</span> <span
  m='2017170'>and</span> <span m='2017320'>the</span> <span
  m='2017410'>part</span> <span m='2017680'>of</span> <span
  m='2017770'>that</span> <span m='2017950'>matrix</span> <span
  m='2018490'>that</span> <span m='2018610'>does</span> <span
  m='2019210'>involve</span> <span m='2019630'>delay</span> <span
  m='2019930'>terms.</span> <span m='2021310'>In</span> <span
  m='2021400'>particular,</span> <span m='2022570'>we</span> <span
  m='2022690'>can</span> <span m='2022870'>write</span> <span
  m='2023650'>the</span> <span m='2023800'>transpose</span> <span
  m='2024610'>matrix</span> <span m='2025180'>F</span> <span
  m='2025300'>transposed</span> <span m='2025960'>of</span> <span
  m='2026050'>z.</span> <span m='2026980'>We</span> <span m='2027040'>can</span>
  <span m='2027190'>separate</span> <span m='2027730'>it</span> <span
  m='2027850'>into</span> <span m='2028030'>the</span> <span
  m='2028150'>sum</span> <span m='2028390'>of</span> <span
  m='2028480'>two</span> <span m='2028660'>matrices.</span> </p><p><span
  m='2030160'>One</span> <span m='2030400'>matrix</span> <span
  m='2031000'>is</span> <span m='2031180'>simply</span> <span
  m='2031750'>a</span> <span m='2031990'>coefficient</span> <span
  m='2032680'>matrix.</span> <span m='2035110'>In</span> <span
  m='2035130'>other</span> <span m='2035280'>words,</span> <span
  m='2035590'>it</span> <span m='2035690'>involves</span> <span
  m='2036330'>no</span> <span m='2036570'>terms</span> <span
  m='2037400'>z</span> <span m='2037600'>to</span> <span m='2037770'>the</span>
  <span m='2037860'>minus</span> <span m='2038250'>the</span> <span
  m='2038700'>1.</span> <span m='2039600'>The</span> <span
  m='2040050'>second</span> <span m='2040830'>matrix</span> <span
  m='2042120'>contains</span> <span m='2042660'>only</span> <span
  m='2043140'>terms</span> <span m='2043590'>involving</span> <span
  m='2044070'>z</span> <span m='2044250'>to</span> <span m='2044400'>the</span>
  <span m='2044490'>minus</span> <span m='2044880'>1.</span> <span
  m='2045075'>And,</span> <span m='2045270'>of</span> <span
  m='2045360'>course,</span> <span m='2045630'>we</span> <span
  m='2045750'>can</span> <span m='2045870'>pull</span> <span
  m='2046080'>the</span> <span m='2046170'>z</span> <span m='2046280'>to</span>
  <span m='2046390'>the</span> <span m='2046500'>minus</span> <span
  m='2046680'>1</span> <span m='2046860'>outside.</span> <span
  m='2048239'>And</span> <span m='2048989'>so</span> <span m='2049590'>we</span>
  <span m='2049800'>have</span> <span m='2050340'>the</span> <span
  m='2050550'>delay</span> <span m='2050880'>terms</span> <span
  m='2051270'>isolated.</span> <span m='2053070'>In</span> <span
  m='2053190'>other</span> <span m='2053370'>words,</span> <span
  m='2053679'>we</span> <span m='2053699'>have</span> <span m='2053850'>a</span>
  <span m='2053909'>matrix</span> <span m='2054510'>of</span> <span
  m='2054630'>coefficients</span> <span m='2055320'>here,</span> <span
  m='2055889'>all</span> <span m='2056460'>of</span> <span
  m='2056580'>the</span> <span m='2056670'>terms</span> <span
  m='2057030'>multiplied</span> <span m='2057590'>by</span> <span
  m='2057780'>z</span> <span m='2057960'>to</span> <span m='2058090'>the</span>
  <span m='2058170'>minus</span> <span m='2058530'>1.</span> </p><p><span
  m='2059469'>So</span> <span m='2060090'>the</span> <span
  m='2060179'>matrix</span> <span m='2060630'>f</span> <span
  m='2060810'>of</span> <span m='2060900'>z</span> <span m='2061500'>can</span>
  <span m='2061679'>be</span> <span m='2062010'>separated</span> <span
  m='2062850'>into</span> <span m='2063960'>a</span> <span
  m='2064110'>coefficient</span> <span m='2064800'>matrix</span> <span
  m='2065460'>and</span> <span m='2065580'>a</span> <span
  m='2065639'>delay</span> <span m='2066000'>matrix.</span> <span
  m='2068050'>And</span> <span m='2068460'>if</span> <span m='2068760'>we</span>
  <span m='2069630'>now</span> <span m='2069900'>substitute</span> <span
  m='2070739'>that</span> <span m='2071730'>back</span> <span
  m='2072120'>into</span> <span m='2072870'>our</span> <span
  m='2073380'>original</span> <span m='2073770'>matrix</span> <span
  m='2074280'>equation,</span> <span m='2075420'>then</span> <span
  m='2075960'>we</span> <span m='2076170'>have</span> <span
  m='2076830'>the</span> <span m='2077520'>statement</span> <span
  m='2078090'>that</span> <span m='2078239'>says</span> <span
  m='2079110'>that</span> <span m='2079530'>the</span> <span
  m='2079770'>vector</span> <span m='2080400'>of</span> <span
  m='2080940'>node</span> <span m='2081210'>variables</span> <span
  m='2082480'>is</span> <span m='2083280'>a</span> <span
  m='2083460'>coefficient</span> <span m='2084090'>matrix</span> <span
  m='2084570'>multiplied</span> <span m='2085290'>by</span> <span
  m='2085920'>that</span> <span m='2086130'>vector,</span> <span
  m='2087290'>a</span> <span m='2087389'>delay</span> <span
  m='2088170'>matrix</span> <span m='2088679'>multiplied</span> <span
  m='2089250'>by</span> <span m='2089429'>that</span> <span
  m='2089639'>vector.</span> <span m='2090760'>And</span> <span
  m='2091380'>then</span> <span m='2091980'>I'm</span> <span
  m='2092100'>assuming</span> <span m='2092580'>incidentally</span> <span
  m='2093270'>in</span> <span m='2093360'>this</span> <span
  m='2093510'>notation</span> <span m='2094170'>and,</span> <span
  m='2094320'>of</span> <span m='2094409'>course,</span> <span
  m='2094679'>it</span> <span m='2094739'>can</span> <span m='2094860'>be</span>
  <span m='2094980'>generalized</span> <span m='2095730'>quite</span> <span
  m='2095969'>easily</span> <span m='2097110'>that</span> <span
  m='2097830'>the</span> <span m='2098550'>sources</span> <span
  m='2099210'>are</span> <span m='2099330'>connected</span> <span
  m='2100050'>only</span> <span m='2100470'>with</span> <span
  m='2100830'>non-delay</span> <span m='2101430'>branches.</span> </p><p><span
  m='2104420'>I</span> <span m='2104870'>have</span> <span
  m='2105560'>suppressed</span> <span m='2106130'>incidentally</span> <span
  m='2106820'>in</span> <span m='2106910'>the</span> <span
  m='2107000'>discussion</span> <span m='2107780'>up</span> <span
  m='2107930'>to</span> <span m='2108050'>this</span> <span
  m='2108260'>point,</span> <span m='2109760'>the</span> <span
  m='2110330'>additional</span> <span m='2110840'>statement</span> <span
  m='2111410'>that</span> <span m='2111560'>we</span> <span
  m='2111710'>need,</span> <span m='2111920'>the</span> <span
  m='2112010'>additional</span> <span m='2112370'>set</span> <span
  m='2112580'>of</span> <span m='2112670'>equations</span> <span
  m='2113270'>that</span> <span m='2113360'>we</span> <span
  m='2113510'>need,</span> <span m='2114330'>that</span> <span
  m='2114470'>tell</span> <span m='2114770'>us</span> <span
  m='2115460'>how</span> <span m='2115740'>finally</span> <span
  m='2116240'>we</span> <span m='2116390'>get</span> <span
  m='2116840'>from</span> <span m='2117440'>the</span> <span
  m='2117590'>set</span> <span m='2117980'>of</span> <span
  m='2118100'>internal</span> <span m='2118580'>network</span> <span
  m='2119120'>nodes</span> <span m='2120020'>to</span> <span
  m='2120440'>the</span> <span m='2120560'>network</span> <span
  m='2121130'>output.</span> <span m='2122990'>We</span> <span
  m='2123530'>have</span> <span m='2124130'>then</span> <span
  m='2126050'>an</span> <span m='2126170'>additional</span> <span
  m='2126650'>set</span> <span m='2126890'>of</span> <span
  m='2126950'>equations</span> <span m='2128420'>that</span> <span
  m='2129200'>specify</span> <span m='2130640'>what</span> <span
  m='2131240'>the</span> <span m='2131570'>sink</span> <span
  m='2131960'>node</span> <span m='2132800'>values</span> <span
  m='2133340'>are</span> <span m='2134390'>in</span> <span
  m='2134540'>terms</span> <span m='2135140'>of</span> <span
  m='2135710'>the</span> <span m='2135980'>internal</span> <span
  m='2136850'>network</span> <span m='2137300'>nodes.</span> <span
  m='2138260'>And</span> <span m='2138590'>often</span> <span
  m='2139040'>in</span> <span m='2139160'>referring</span> <span
  m='2139610'>to</span> <span m='2139730'>the</span> <span
  m='2139820'>matrix</span> <span m='2140210'>equations</span> <span
  m='2141140'>for</span> <span m='2141275'>a</span> <span
  m='2141410'>signal</span> <span m='2141740'>flow</span> <span
  m='2142010'>graph,</span> <span m='2143780'>sometimes</span> <span
  m='2144440'>we'll</span> <span m='2144590'>include</span> <span
  m='2144980'>this</span> <span m='2145190'>equation</span> <span
  m='2145670'>explicitly,</span> <span m='2146450'>and</span> <span
  m='2146540'>sometimes</span> <span m='2147080'>we'll</span> <span
  m='2147200'>tend</span> <span m='2147410'>to</span> <span
  m='2147560'>suppress</span> <span m='2148040'>it.</span> </p><p><span
  m='2149780'>Now,</span> <span m='2150320'>looking</span> <span
  m='2150860'>at</span> <span m='2151550'>this</span> <span
  m='2151790'>equation</span> <span m='2152840'>where</span> <span
  m='2153440'>we've</span> <span m='2153770'>separated</span> <span
  m='2154310'>out</span> <span m='2154460'>the</span> <span
  m='2154550'>coefficient</span> <span m='2155330'>and</span> <span
  m='2155510'>delay</span> <span m='2155810'>branches,</span> <span
  m='2157130'>we</span> <span m='2157310'>can</span> <span
  m='2157670'>alternatively</span> <span m='2158600'>reinterpret</span> <span
  m='2159320'>that</span> <span m='2159530'>equation</span> <span
  m='2160640'>in</span> <span m='2160760'>the</span> <span
  m='2160850'>time</span> <span m='2161180'>domain.</span> <span
  m='2161600'>It's</span> <span m='2161750'>expressed</span> <span
  m='2162260'>here</span> <span m='2162800'>in</span> <span
  m='2163160'>terms</span> <span m='2163520'>of</span> <span
  m='2163580'>z</span> <span m='2163760'>transforms.</span> <span
  m='2165170'>In</span> <span m='2165580'>the</span> <span
  m='2165740'>time</span> <span m='2166100'>domain,</span> <span
  m='2167270'>then</span> <span m='2167960'>this</span> <span
  m='2169250'>corresponds</span> <span m='2169970'>again</span> <span
  m='2170300'>to</span> <span m='2170510'>a</span> <span
  m='2170720'>matrix</span> <span m='2171140'>set</span> <span
  m='2171350'>of</span> <span m='2171440'>equations</span> <span
  m='2172850'>stating</span> <span m='2173420'>that</span> <span
  m='2174440'>the</span> <span m='2174590'>column</span> <span
  m='2174950'>vector</span> <span m='2175430'>w</span> <span
  m='2175850'>of</span> <span m='2175970'>n</span> <span m='2177410'>is</span>
  <span m='2177560'>equal</span> <span m='2178010'>to</span> <span
  m='2178550'>a</span> <span m='2179270'>coefficient</span> <span
  m='2180020'>matrix</span> <span m='2180500'>multiplied</span> <span
  m='2181700'>by</span> <span m='2182270'>the</span> <span
  m='2182390'>present</span> <span m='2182780'>state--</span> <span
  m='2183420'>in</span> <span m='2183520'>other</span> <span
  m='2183620'>words,</span> <span m='2184410'>the</span> <span
  m='2184430'>same</span> <span m='2185210'>column</span> <span
  m='2185870'>vector--</span> <span m='2187130'>plus</span> <span
  m='2187580'>another</span> <span m='2187910'>matrix</span> <span
  m='2188960'>multiplied</span> <span m='2189920'>by</span> <span
  m='2191090'>that</span> <span m='2192120'>set</span> <span
  m='2192350'>of</span> <span m='2192470'>node</span> <span
  m='2193550'>variables,</span> <span m='2194390'>one</span> <span
  m='2194660'>iteration</span> <span m='2195170'>previously,</span> <span
  m='2196730'>and</span> <span m='2197330'>then,</span> <span
  m='2197510'>of</span> <span m='2197600'>course,</span> <span
  m='2197900'>an</span> <span m='2197990'>equation</span> <span
  m='2198620'>coupling</span> <span m='2199310'>the</span> <span
  m='2199430'>sources</span> <span m='2199940'>into</span> <span
  m='2200210'>that</span> <span m='2200700'>and</span> <span
  m='2200720'>finally</span> <span m='2201140'>an</span> <span
  m='2201230'>equation</span> <span m='2202220'>that</span> <span
  m='2202340'>generates</span> <span m='2203090'>the</span> <span
  m='2203240'>sync</span> <span m='2203540'>node</span> <span
  m='2203810'>outputs</span> <span m='2204320'>from</span> <span
  m='2204470'>the</span> <span m='2204560'>node</span> <span
  m='2204830'>variables.</span> </p><p><span m='2206300'>But</span> <span
  m='2206900'>if</span> <span m='2207110'>you</span> <span
  m='2207290'>look</span> <span m='2207530'>at</span> <span
  m='2207680'>this,</span> <span m='2208380'>what</span> <span
  m='2211700'>this</span> <span m='2211880'>corresponds</span> <span
  m='2212500'>to,</span> <span m='2212600'>of</span> <span
  m='2212690'>course,</span> <span m='2213260'>is</span> <span
  m='2214250'>a</span> <span m='2214790'>set</span> <span m='2216110'>of</span>
  <span m='2216890'>first</span> <span m='2217310'>order</span> <span
  m='2217580'>difference</span> <span m='2218030'>equations,</span> <span
  m='2219230'>so</span> <span m='2219470'>that</span> <span
  m='2219800'>essentially</span> <span m='2220430'>what</span> <span
  m='2220580'>we've</span> <span m='2220790'>done,</span> <span
  m='2221600'>starting</span> <span m='2222020'>from</span> <span
  m='2222230'>our</span> <span m='2222380'>n-th</span> <span
  m='2222620'>order</span> <span m='2223130'>linear</span> <span
  m='2223400'>constant</span> <span m='2223790'>coefficient</span> <span
  m='2224330'>difference</span> <span m='2224690'>equation,</span> <span
  m='2225890'>through</span> <span m='2226340'>the</span> <span
  m='2226520'>signal</span> <span m='2226880'>flow</span> <span
  m='2227180'>graph</span> <span m='2227540'>representation,</span> <span
  m='2229040'>we</span> <span m='2229310'>have</span> <span
  m='2229640'>in</span> <span m='2229850'>essence</span> <span
  m='2230270'>decomposed</span> <span m='2231080'>that</span> <span
  m='2231740'>into</span> <span m='2232460'>a</span> <span
  m='2232820'>set</span> <span m='2233960'>of</span> <span
  m='2234380'>first</span> <span m='2234770'>order</span> <span
  m='2235490'>linear</span> <span m='2235790'>constant</span> <span
  m='2236210'>coefficient</span> <span m='2236780'>difference</span> <span
  m='2237080'>equations,</span> <span m='2237650'>of</span> <span
  m='2237770'>course,</span> <span m='2238040'>all</span> <span
  m='2238190'>of</span> <span m='2238280'>them</span> <span
  m='2238400'>coupled.</span> <span m='2240260'>And</span> <span
  m='2241880'>the</span> <span m='2243620'>discussion</span> <span
  m='2243980'>in</span> <span m='2244340'>the</span> <span
  m='2244540'>next</span> <span m='2244720'>several</span> <span
  m='2245030'>lectures</span> <span m='2245540'>will</span> <span
  m='2245750'>in</span> <span m='2245840'>fact</span> <span
  m='2246200'>involve</span> <span m='2246890'>what</span> <span
  m='2247850'>the</span> <span m='2248540'>various</span> <span
  m='2249050'>options</span> <span m='2249530'>are</span> <span
  m='2249830'>in</span> <span m='2249980'>terms</span> <span
  m='2250490'>of</span> <span m='2250820'>what</span> <span
  m='2251720'>various</span> <span m='2252230'>forms</span> <span
  m='2252840'>we</span> <span m='2252890'>can</span> <span
  m='2253070'>use,</span> <span m='2253580'>or</span> <span
  m='2253960'>are</span> <span m='2254180'>commonly</span> <span
  m='2254660'>used,</span> <span m='2255560'>in</span> <span
  m='2256100'>representing</span> <span m='2256730'>this</span> <span
  m='2256940'>large</span> <span m='2257300'>n-th</span> <span
  m='2257480'>order</span> <span m='2257750'>equation.</span> <span
  m='2258560'>But</span> <span m='2258710'>what</span> <span
  m='2258890'>we</span> <span m='2259040'>see</span> <span m='2259430'>is</span>
  <span m='2259550'>that</span> <span m='2259670'>the</span> <span
  m='2259760'>signal</span> <span m='2260090'>flow</span> <span
  m='2260360'>graph</span> <span m='2260810'>in</span> <span
  m='2260960'>essence</span> <span m='2262010'>breaks</span> <span
  m='2262340'>down</span> <span m='2262610'>the</span> <span
  m='2262730'>n-th</span> <span m='2262940'>order</span> <span
  m='2263210'>equation</span> <span m='2263900'>into</span> <span
  m='2264740'>a</span> <span m='2265760'>set</span> <span m='2266660'>of</span>
  <span m='2267170'>first</span> <span m='2267500'>order</span> <span
  m='2267770'>difference</span> <span m='2268130'>equations.</span> </p><p><span
  m='2270350'>Well,</span> <span m='2270770'>let's</span> <span
  m='2270980'>just</span> <span m='2271730'>finally</span> <span
  m='2272120'>look</span> <span m='2272330'>at</span> <span
  m='2272390'>an</span> <span m='2272480'>example</span> <span
  m='2273260'>of</span> <span m='2273620'>how</span> <span
  m='2274250'>the</span> <span m='2275480'>set</span> <span
  m='2275750'>of</span> <span m='2275810'>equations</span> <span
  m='2276500'>might</span> <span m='2276710'>look</span> <span
  m='2277460'>for</span> <span m='2278300'>a</span> <span
  m='2278840'>single</span> <span m='2279170'>flow</span> <span
  m='2279440'>graph,</span> <span m='2279830'>a</span> <span
  m='2279890'>relatively</span> <span m='2281030'>simple</span> <span
  m='2282470'>example,</span> <span m='2283370'>and</span> <span
  m='2283970'>incidentally</span> <span m='2284480'>somewhat</span> <span
  m='2284870'>meaningless</span> <span m='2285350'>in</span> <span
  m='2285440'>the</span> <span m='2285530'>sense</span> <span
  m='2285980'>that</span> <span m='2286760'>it's</span> <span
  m='2286940'>not</span> <span m='2287150'>a</span> <span
  m='2287210'>flow</span> <span m='2287450'>graph</span> <span
  m='2287870'>that</span> <span m='2288530'>is</span> <span
  m='2289070'>motivated</span> <span m='2289730'>by</span> <span
  m='2290630'>anything</span> <span m='2291320'>other</span> <span
  m='2291560'>than</span> <span m='2291950'>something</span> <span
  m='2292370'>to</span> <span m='2292490'>draw</span> <span
  m='2292820'>here</span> <span m='2293060'>for</span> <span
  m='2293240'>discussion.</span> </p><p><span m='2295070'>Well,</span> <span
  m='2295390'>all</span> <span m='2295530'>right,</span> <span
  m='2295670'>here's</span> <span m='2295940'>a</span> <span
  m='2296270'>linear</span> <span m='2296600'>signal</span> <span
  m='2296930'>flow</span> <span m='2297230'>graph.</span> <span
  m='2298070'>It</span> <span m='2298160'>has</span> <span
  m='2298520'>these</span> <span m='2298760'>unity</span> <span
  m='2299390'>gain</span> <span m='2299720'>branches.</span> <span
  m='2300380'>It</span> <span m='2300470'>has</span> <span m='2300710'>a</span>
  <span m='2301220'>branch</span> <span m='2301550'>with</span> <span
  m='2301710'>gain</span> <span m='2301950'>b</span> <span
  m='2302210'>and</span> <span m='2302330'>a</span> <span
  m='2302510'>branch</span> <span m='2302870'>with</span> <span
  m='2302990'>gain</span> <span m='2303350'>a</span> <span
  m='2303610'>and</span> <span m='2304340'>the</span> <span
  m='2304430'>two</span> <span m='2304640'>delay</span> <span
  m='2305000'>branches.</span> <span m='2307100'>According</span> <span
  m='2307490'>to</span> <span m='2307640'>the</span> <span
  m='2307850'>algebra</span> <span m='2308360'>for</span> <span
  m='2308480'>the</span> <span m='2308570'>flow</span> <span
  m='2308870'>graph,</span> <span m='2310160'>this</span> <span
  m='2310370'>node</span> <span m='2310670'>variable</span> <span
  m='2311450'>is</span> <span m='2311630'>equal</span> <span
  m='2311930'>to</span> <span m='2312050'>B</span> <span
  m='2312350'>times</span> <span m='2312680'>this</span> <span
  m='2312860'>node</span> <span m='2313130'>variable.</span> <span
  m='2314190'>So</span> <span m='2314240'>that's</span> <span
  m='2314450'>this</span> <span m='2314660'>equation.</span> <span
  m='2316040'>This</span> <span m='2316220'>node</span> <span
  m='2316520'>variable</span> <span m='2317390'>is</span> <span
  m='2318110'>this</span> <span m='2318350'>one</span> <span
  m='2318530'>delayed</span> <span m='2319130'>plus</span> <span
  m='2319500'>this</span> <span m='2319700'>one</span> <span
  m='2319910'>delayed.</span> <span m='2320240'>That's</span> <span
  m='2320960'>this</span> <span m='2321170'>equation</span> <span
  m='2322430'>and</span> <span m='2323390'>this</span> <span
  m='2323630'>node--</span> <span m='2325550'>I'm</span> <span
  m='2325640'>sorry,</span> <span m='2325850'>this</span> <span
  m='2326090'>node</span> <span m='2326960'>is</span> <span m='2327830'>a</span>
  <span m='2328070'>times</span> <span m='2328430'>w2</span> <span
  m='2328730'>of</span> <span m='2329030'>n</span> <span m='2329590'>plus</span>
  <span m='2329930'>the</span> <span m='2330020'>source.</span> </p><p><span
  m='2330810'>So</span> <span m='2330890'>those</span> <span
  m='2331070'>are</span> <span m='2331130'>the</span> <span
  m='2331220'>linear</span> <span m='2331550'>equations</span> <span
  m='2332210'>defining</span> <span m='2332990'>the</span> <span
  m='2333260'>internal</span> <span m='2333770'>network</span> <span
  m='2334220'>nodes.</span> <span m='2336380'>And</span> <span
  m='2337190'>this</span> <span m='2337910'>corresponds</span> <span
  m='2338690'>then</span> <span m='2338960'>to</span> <span m='2339500'>a</span>
  <span m='2341300'>matrix</span> <span m='2341780'>equation.</span> <span
  m='2342870'>Let</span> <span m='2342920'>me</span> <span
  m='2343040'>draw</span> <span m='2343310'>your</span> <span
  m='2343460'>attention</span> <span m='2343940'>to</span> <span
  m='2344030'>the</span> <span m='2344150'>fact,</span> <span
  m='2344540'>incidentally,</span> <span m='2345950'>that</span> <span
  m='2346520'>the</span> <span m='2346670'>way</span> <span
  m='2346850'>that</span> <span m='2346970'>I've</span> <span
  m='2347120'>numbered</span> <span m='2347810'>these</span> <span
  m='2348080'>nodes</span> <span m='2348680'>in</span> <span
  m='2348830'>fact</span> <span m='2349190'>is</span> <span
  m='2349310'>not</span> <span m='2349940'>the</span> <span
  m='2350090'>order</span> <span m='2350600'>in</span> <span
  m='2350750'>which</span> <span m='2350960'>I</span> <span
  m='2351110'>can</span> <span m='2351290'>compute</span> <span
  m='2351740'>them</span> <span m='2352130'>if</span> <span m='2352340'>I</span>
  <span m='2352460'>were</span> <span m='2353240'>to</span> <span
  m='2353540'>compute</span> <span m='2353990'>them</span> <span
  m='2354560'>successively.</span> </p><p><span m='2355970'>Now,</span> <span
  m='2356120'>what</span> <span m='2356240'>I</span> <span
  m='2356330'>mean</span> <span m='2356570'>by</span> <span
  m='2356810'>that</span> <span m='2358130'>is</span> <span
  m='2358880'>suppose</span> <span m='2359360'>that</span> <span
  m='2359600'>in</span> <span m='2359750'>my</span> <span
  m='2359900'>numbering</span> <span m='2361070'>what</span> <span
  m='2361250'>I</span> <span m='2361340'>decide</span> <span
  m='2361910'>is</span> <span m='2362290'>that</span> <span
  m='2362450'>what</span> <span m='2362630'>the</span> <span
  m='2362720'>numbering</span> <span m='2363140'>means</span> <span
  m='2363680'>is</span> <span m='2364010'>that</span> <span
  m='2364610'>node</span> <span m='2364870'>1</span> <span
  m='2365090'>I'll</span> <span m='2365180'>compute</span> <span
  m='2365600'>first,</span> <span m='2365930'>node</span> <span
  m='2366140'>2</span> <span m='2366290'>I'll</span> <span
  m='2366440'>compute</span> <span m='2366830'>second,</span> <span
  m='2367240'>node</span> <span m='2367485'>3</span> <span
  m='2367607'>I'll</span> <span m='2367730'>compute</span> <span
  m='2368240'>third.</span> <span m='2370370'>To</span> <span
  m='2370490'>compute</span> <span m='2370850'>node</span> <span
  m='2371180'>1,</span> <span m='2372320'>I</span> <span m='2372440'>need</span>
  <span m='2372650'>node</span> <span m='2372890'>3.</span> <span
  m='2374070'>And</span> <span m='2375470'>I</span> <span
  m='2375620'>don't</span> <span m='2375800'>have</span> <span
  m='2376010'>node</span> <span m='2376410'>3</span> <span m='2376760'>if</span>
  <span m='2376970'>I'm</span> <span m='2377030'>going</span> <span
  m='2377150'>to</span> <span m='2377210'>compute</span> <span
  m='2377540'>that</span> <span m='2377750'>after</span> <span
  m='2378050'>node</span> <span m='2378320'>1.</span> <span
  m='2379100'>So</span> <span m='2379520'>actually</span> <span
  m='2380780'>the</span> <span m='2380960'>order</span> <span
  m='2381290'>that</span> <span m='2381440'>I've</span> <span
  m='2381560'>specified</span> <span m='2382280'>here</span> <span
  m='2382460'>for</span> <span m='2382610'>the</span> <span
  m='2382700'>nodes</span> <span m='2383540'>is</span> <span
  m='2383690'>not</span> <span m='2384260'>an</span> <span
  m='2384380'>order</span> <span m='2384860'>in</span> <span
  m='2385070'>which</span> <span m='2385700'>I</span> <span
  m='2385850'>can</span> <span m='2386000'>compute</span> <span
  m='2386930'>the</span> <span m='2387020'>network.</span> <span
  m='2388190'>Or</span> <span m='2389390'>another</span> <span
  m='2389690'>way</span> <span m='2389810'>to</span> <span
  m='2389930'>say</span> <span m='2390170'>that</span> <span
  m='2390560'>is</span> <span m='2390740'>that</span> <span
  m='2391640'>this</span> <span m='2391880'>network</span> <span
  m='2392510'>as</span> <span m='2392690'>I've</span> <span
  m='2392840'>numbered</span> <span m='2393230'>the</span> <span
  m='2393320'>nodes</span> <span m='2393950'>is</span> <span
  m='2394100'>not</span> <span m='2394310'>computable.</span> </p><p><span
  m='2396260'>But</span> <span m='2396620'>let's</span> <span
  m='2396890'>go</span> <span m='2397100'>on,</span> <span
  m='2398780'>and</span> <span m='2399410'>we'll</span> <span
  m='2399920'>look</span> <span m='2400410'>in</span> <span
  m='2400430'>fact</span> <span m='2400730'>at</span> <span m='2400820'>a</span>
  <span m='2400850'>rearrangement</span> <span m='2401420'>of</span> <span
  m='2401480'>the</span> <span m='2401570'>nodes</span> <span
  m='2402020'>that</span> <span m='2402170'>is</span> <span
  m='2402320'>computable.</span> <span m='2402980'>But</span> <span
  m='2403130'>let's</span> <span m='2403310'>see</span> <span
  m='2403580'>how</span> <span m='2403730'>the</span> <span
  m='2403820'>matrix</span> <span m='2404240'>equation</span> <span
  m='2405020'>looks.</span> </p><p><span m='2405980'>Simply,</span> <span
  m='2406400'>this</span> <span m='2406640'>equation</span> <span
  m='2408800'>rewritten</span> <span m='2409700'>in</span> <span
  m='2409850'>terms</span> <span m='2410480'>of</span> <span
  m='2410930'>a</span> <span m='2410990'>set</span> <span m='2411260'>of</span>
  <span m='2411350'>matrices,</span> <span m='2412640'>then</span> <span
  m='2413810'>it</span> <span m='2414230'>comes</span> <span
  m='2414530'>out</span> <span m='2414680'>as</span> <span
  m='2414800'>I've</span> <span m='2414950'>indicated</span> <span
  m='2415520'>here.</span> <span m='2416360'>We</span> <span
  m='2416510'>have</span> <span m='2416750'>the</span> <span
  m='2416840'>matrix</span> <span m='2417350'>F</span> <span
  m='2417570'>sub</span> <span m='2418030'>c.</span> <span
  m='2418490'>This</span> <span m='2418670'>is</span> <span
  m='2418790'>the</span> <span m='2419090'>coefficient</span> <span
  m='2419750'>matrix.</span> <span m='2421140'>This</span> <span
  m='2421430'>is</span> <span m='2422000'>the</span> <span
  m='2422180'>delay</span> <span m='2422510'>matrix.</span> <span
  m='2422990'>So</span> <span m='2423230'>it</span> <span
  m='2423290'>involves</span> <span m='2423980'>a</span> <span
  m='2424040'>vector</span> <span m='2424460'>of</span> <span
  m='2424610'>only</span> <span m='2425090'>delayed</span> <span
  m='2425450'>sequences</span> <span m='2426290'>and</span> <span
  m='2426410'>then</span> <span m='2427040'>the</span> <span
  m='2427280'>input</span> <span m='2427850'>coupled</span> <span
  m='2428300'>in.</span> </p><p><span m='2430510'>Let</span> <span
  m='2430660'>me</span> <span m='2431230'>point</span> <span
  m='2431500'>out</span> <span m='2431740'>incidentally--</span> <span
  m='2432950'>just</span> <span m='2433420'>keep</span> <span
  m='2433630'>track</span> <span m='2434020'>of</span> <span
  m='2434470'>the</span> <span m='2434560'>fact</span> <span
  m='2435760'>that</span> <span m='2436540'>this</span> <span
  m='2436840'>matrix,</span> <span m='2437410'>the</span> <span
  m='2437500'>coefficient</span> <span m='2438130'>matrix,</span> <span
  m='2439270'>happens</span> <span m='2439750'>to</span> <span
  m='2439930'>have</span> <span m='2440620'>an</span> <span
  m='2440770'>element</span> <span m='2441850'>on</span> <span
  m='2442150'>or</span> <span m='2442240'>above</span> <span
  m='2442870'>the</span> <span m='2442990'>major</span> <span
  m='2443320'>diagonal.</span> <span m='2444580'>And</span> <span
  m='2445540'>that</span> <span m='2445780'>shouldn't</span> <span
  m='2446020'>have</span> <span m='2446200'>any</span> <span
  m='2446320'>particular</span> <span m='2446770'>meaning</span> <span
  m='2447070'>right</span> <span m='2447250'>now,</span> <span
  m='2447490'>but</span> <span m='2447640'>it</span> <span
  m='2447700'>will</span> <span m='2448150'>in</span> <span m='2448270'>a</span>
  <span m='2448330'>couple</span> <span m='2448570'>of</span> <span
  m='2448660'>minutes.</span> </p><p><span m='2450910'>All</span> <span
  m='2451020'>right,</span> <span m='2451490'>let's</span> <span
  m='2451690'>consider</span> <span m='2452890'>a</span> <span
  m='2453250'>slightly</span> <span m='2453850'>different</span> <span
  m='2454390'>ordering</span> <span m='2455260'>for</span> <span
  m='2455440'>the</span> <span m='2456160'>network</span> <span
  m='2456640'>nodes.</span> <span m='2457820'>This</span> <span
  m='2457960'>is</span> <span m='2458410'>the</span> <span
  m='2458500'>same</span> <span m='2458800'>network.</span> <span
  m='2461080'>I</span> <span m='2461740'>now</span> <span
  m='2462130'>have</span> <span m='2462310'>ordered</span> <span
  m='2462610'>the</span> <span m='2462730'>node</span> <span
  m='2463100'>slightly</span> <span m='2463540'>differently.</span> <span
  m='2464120'>I'm</span> <span m='2464230'>calling</span> <span
  m='2464560'>this</span> <span m='2464890'>node</span> <span
  m='2465220'>1,</span> <span m='2466000'>this</span> <span
  m='2466210'>node</span> <span m='2466510'>2,</span> <span
  m='2467020'>and</span> <span m='2467140'>this</span> <span
  m='2467320'>node</span> <span m='2467620'>3.</span> <span
  m='2468640'>And</span> <span m='2468760'>let's</span> <span
  m='2469060'>just</span> <span m='2469420'>inquire</span> <span
  m='2470140'>as</span> <span m='2470410'>to</span> <span
  m='2470560'>whether</span> <span m='2472450'>the</span> <span
  m='2473050'>nodes</span> <span m='2473530'>ordered</span> <span
  m='2474430'>as</span> <span m='2474610'>I've</span> <span
  m='2474730'>indicated</span> <span m='2475270'>here</span> <span
  m='2475750'>are</span> <span m='2475870'>now</span> <span
  m='2476080'>computable.</span> </p><p><span m='2477730'>Well,</span> <span
  m='2478570'>to</span> <span m='2478690'>get</span> <span
  m='2478900'>node</span> <span m='2479230'>1,</span> <span m='2480310'>I</span>
  <span m='2480400'>need</span> <span m='2481510'>w</span> <span
  m='2482230'>of</span> <span m='2482470'>n</span> <span
  m='2482680'>minus</span> <span m='2483100'>1,</span> <span
  m='2483440'>which</span> <span m='2483670'>of</span> <span
  m='2483820'>course</span> <span m='2484060'>I</span> <span
  m='2484160'>got</span> <span m='2484450'>because</span> <span
  m='2484750'>that's</span> <span m='2485030'>from</span> <span
  m='2485350'>the</span> <span m='2485440'>previous</span> <span
  m='2485860'>iteration.</span> <span m='2487240'>I</span> <span
  m='2487360'>need</span> <span m='2487660'>w3</span> <span
  m='2488300'>of</span> <span m='2488410'>n</span> <span
  m='2488520'>minus</span> <span m='2488850'>1.</span> <span
  m='2489000'>And</span> <span m='2489100'>that</span> <span
  m='2489280'>I've</span> <span m='2489430'>got</span> <span
  m='2489820'>from</span> <span m='2489970'>the</span> <span
  m='2490030'>previous</span> <span m='2490450'>iteration.</span> <span
  m='2491540'>So</span> <span m='2491650'>this</span> <span
  m='2491860'>node</span> <span m='2492130'>can</span> <span
  m='2492310'>be</span> <span m='2492430'>computed.</span> </p><p><span
  m='2494380'>To</span> <span m='2494500'>compute</span> <span
  m='2494860'>this</span> <span m='2495100'>node,</span> <span
  m='2495740'>I</span> <span m='2495840'>need</span> <span
  m='2495910'>the</span> <span m='2496000'>source,</span> <span
  m='2496420'>which</span> <span m='2496600'>I</span> <span
  m='2496750'>have.</span> <span m='2497620'>And</span> <span
  m='2497740'>I</span> <span m='2497830'>need</span> <span m='2498010'>w1</span>
  <span m='2498320'>of</span> <span m='2498670'>n,</span> <span
  m='2498820'>which</span> <span m='2499000'>I</span> <span
  m='2499090'>just</span> <span m='2499600'>got.</span> <span
  m='2500260'>So</span> <span m='2500830'>this</span> <span
  m='2500980'>can</span> <span m='2501130'>be</span> <span
  m='2501280'>computed.</span> <span m='2502330'>And</span> <span
  m='2502450'>then</span> <span m='2502600'>to</span> <span
  m='2502720'>compute</span> <span m='2503140'>w3</span> <span
  m='2503770'>of</span> <span m='2503870'>n,</span> <span m='2504340'>I</span>
  <span m='2504460'>need</span> <span m='2504950'>w2</span> <span
  m='2505270'>of</span> <span m='2505390'>n,</span> <span
  m='2506110'>which</span> <span m='2506320'>I</span> <span
  m='2506530'>just</span> <span m='2506800'>computed.</span> <span
  m='2507760'>And</span> <span m='2508480'>so,</span> <span
  m='2509140'>in</span> <span m='2509260'>fact,</span> <span
  m='2509920'>the</span> <span m='2510010'>nodes</span> <span
  m='2510580'>numbered</span> <span m='2511090'>in</span> <span
  m='2511210'>this</span> <span m='2511420'>order</span> <span
  m='2511840'>are</span> <span m='2512080'>computable,</span> <span
  m='2513220'>whereas</span> <span m='2513520'>the</span> <span
  m='2513610'>nodes</span> <span m='2513940'>numbered</span> <span
  m='2514450'>in</span> <span m='2514540'>the</span> <span
  m='2514630'>previous</span> <span m='2515110'>order</span> <span
  m='2515650'>are</span> <span m='2515740'>not</span> <span
  m='2515950'>computable.</span> </p><p><span m='2518110'>If</span> <span
  m='2518740'>I</span> <span m='2519070'>look</span> <span m='2519340'>at</span>
  <span m='2519430'>the</span> <span m='2519730'>equations</span> <span
  m='2520720'>for</span> <span m='2520900'>this,</span> <span
  m='2522460'>they're,</span> <span m='2522870'>of</span> <span
  m='2523000'>course,</span> <span m='2523510'>the</span> <span
  m='2523630'>same</span> <span m='2523930'>equations</span> <span
  m='2524530'>as</span> <span m='2524650'>I</span> <span m='2524740'>had</span>
  <span m='2525160'>previously,</span> <span m='2526120'>except</span> <span
  m='2526930'>that</span> <span m='2527410'>some</span> <span
  m='2527620'>of</span> <span m='2527710'>the</span> <span
  m='2527830'>indices</span> <span m='2528340'>are</span> <span
  m='2528430'>changed.</span> <span m='2529360'>And</span> <span
  m='2529510'>so</span> <span m='2529720'>it</span> <span
  m='2529900'>simply</span> <span m='2530290'>involves</span> <span
  m='2531220'>changing</span> <span m='2531730'>some</span> <span
  m='2531970'>of</span> <span m='2532060'>the</span> <span
  m='2532150'>rows</span> <span m='2532450'>and</span> <span
  m='2532540'>columns.</span> <span m='2533650'>And</span> <span
  m='2534520'>what</span> <span m='2535560'>it</span> <span
  m='2535840'>comes</span> <span m='2536140'>out</span> <span
  m='2536350'>to</span> <span m='2536470'>look</span> <span
  m='2536710'>like,</span> <span m='2537280'>in</span> <span
  m='2537370'>fact,</span> <span m='2538480'>is</span> <span
  m='2539350'>what</span> <span m='2539530'>I've</span> <span
  m='2539680'>indicated</span> <span m='2540250'>here.</span> </p><p><span
  m='2541990'>Again,</span> <span m='2542620'>the</span> <span
  m='2542800'>coefficient</span> <span m='2543460'>matrix--</span> <span
  m='2545860'>the</span> <span m='2546700'>same</span> <span
  m='2547420'>elements</span> <span m='2547840'>appear,</span> <span
  m='2548270'>but</span> <span m='2548500'>the</span> <span
  m='2548620'>order</span> <span m='2549010'>is</span> <span
  m='2549160'>swapped</span> <span m='2549610'>around--</span> <span
  m='2550870'>multiplied</span> <span m='2551590'>by</span> <span
  m='2552490'>the</span> <span m='2553390'>vector</span> <span
  m='2553930'>of</span> <span m='2554110'>current</span> <span
  m='2554650'>node</span> <span m='2555430'>states</span> <span
  m='2556840'>and</span> <span m='2556990'>then</span> <span
  m='2557380'>a</span> <span m='2557950'>delay</span> <span
  m='2558280'>matrix</span> <span m='2560410'>multiplied</span> <span
  m='2560950'>by</span> <span m='2561100'>the</span> <span
  m='2561220'>vector</span> <span m='2561790'>of</span> <span
  m='2562480'>delayed</span> <span m='2563320'>states,</span> <span
  m='2564430'>and</span> <span m='2564550'>then</span> <span
  m='2564730'>the</span> <span m='2564850'>input</span> <span
  m='2565360'>coupled</span> <span m='2565780'>in.</span> <span
  m='2566720'>And</span> <span m='2567490'>notice</span> <span
  m='2567940'>that</span> <span m='2568120'>in</span> <span
  m='2568240'>this</span> <span m='2568450'>case,</span> <span
  m='2569530'>we</span> <span m='2569650'>don't</span> <span
  m='2569980'>have</span> <span m='2570580'>any</span> <span
  m='2571300'>non-zero</span> <span m='2571960'>values</span> <span
  m='2572680'>on</span> <span m='2573190'>or</span> <span
  m='2573310'>above</span> <span m='2574270'>the</span> <span
  m='2574810'>main</span> <span m='2575050'>diagonal.</span> </p><p><span
  m='2577280'>It</span> <span m='2577380'>turns</span> <span
  m='2577660'>out</span> <span m='2578350'>that</span> <span
  m='2578950'>you</span> <span m='2579100'>can</span> <span
  m='2579250'>show</span> <span m='2579810'>it,</span> <span
  m='2580030'>and</span> <span m='2580270'>it's</span> <span
  m='2580420'>not</span> <span m='2582430'>too</span> <span
  m='2582610'>difficult</span> <span m='2583090'>to</span> <span
  m='2583240'>do,</span> <span m='2584260'>you</span> <span
  m='2584350'>can</span> <span m='2584500'>show</span> <span
  m='2585220'>that</span> <span m='2586090'>a</span> <span
  m='2586630'>necessary</span> <span m='2587170'>and</span> <span
  m='2587260'>sufficient</span> <span m='2587680'>condition</span> <span
  m='2589060'>for</span> <span m='2589900'>the</span> <span
  m='2590230'>node</span> <span m='2590560'>numbering</span> <span
  m='2591310'>to</span> <span m='2591430'>correspond</span> <span
  m='2592120'>to</span> <span m='2592270'>a</span> <span
  m='2592300'>computable</span> <span m='2592900'>network,</span> <span
  m='2593830'>or</span> <span m='2594040'>to</span> <span m='2594190'>be</span>
  <span m='2594340'>a</span> <span m='2594400'>computer</span> <span
  m='2594970'>numbering,</span> <span m='2596200'>is</span> <span
  m='2596500'>that</span> <span m='2597310'>this</span> <span
  m='2597520'>coefficient</span> <span m='2598210'>matrix</span> <span
  m='2599230'>has</span> <span m='2599620'>to</span> <span
  m='2600820'>have</span> <span m='2601090'>the</span> <span
  m='2601210'>form</span> <span m='2601930'>that</span> <span
  m='2602500'>there</span> <span m='2602650'>are</span> <span
  m='2602680'>no</span> <span m='2602890'>non-zero</span> <span
  m='2603550'>elements</span> <span m='2604090'>on</span> <span
  m='2604690'>or</span> <span m='2604810'>above</span> <span
  m='2605320'>the</span> <span m='2605410'>major</span> <span
  m='2605740'>diagonal.</span> </p><p><span m='2608140'>So</span> <span
  m='2609310'>often</span> <span m='2609940'>if</span> <span
  m='2610570'>the</span> <span m='2610660'>nodes</span> <span
  m='2610900'>are</span> <span m='2610990'>numbered</span> <span
  m='2611650'>in</span> <span m='2612040'>a</span> <span
  m='2612100'>non-computable</span> <span m='2612970'>order,</span> <span
  m='2613540'>the</span> <span m='2613660'>order</span> <span
  m='2613900'>can</span> <span m='2614020'>simply</span> <span
  m='2614350'>be</span> <span m='2614530'>rearranged</span> <span
  m='2615490'>so</span> <span m='2615700'>that</span> <span
  m='2616000'>it</span> <span m='2616120'>is</span> <span
  m='2616300'>computable.</span> <span m='2618790'>It</span> <span
  m='2619420'>does</span> <span m='2620170'>turn</span> <span
  m='2620470'>out</span> <span m='2621160'>incidentally</span> <span
  m='2622060'>that</span> <span m='2622630'>there</span> <span
  m='2623230'>are</span> <span m='2623710'>some</span> <span
  m='2623950'>networks</span> <span m='2625150'>for</span> <span
  m='2625330'>which</span> <span m='2625690'>no</span> <span
  m='2625840'>matter</span> <span m='2626110'>how</span> <span
  m='2626320'>you</span> <span m='2626470'>number</span> <span
  m='2626770'>the</span> <span m='2626890'>nodes,</span> <span
  m='2627790'>you</span> <span m='2628510'>can't</span> <span
  m='2628810'>number</span> <span m='2629170'>them</span> <span
  m='2629500'>in</span> <span m='2629920'>an</span> <span
  m='2630040'>order</span> <span m='2630520'>that</span> <span
  m='2630670'>makes</span> <span m='2630940'>the</span> <span
  m='2631030'>network</span> <span m='2631390'>computable.</span> </p><p><span
  m='2633370'>Computability,</span> <span m='2634090'>as</span> <span
  m='2634210'>I've</span> <span m='2634300'>just</span> <span
  m='2634510'>said,</span> <span m='2634960'>is</span> <span
  m='2635170'>the</span> <span m='2635260'>statement</span> <span
  m='2635710'>that</span> <span m='2635860'>the</span> <span
  m='2635980'>notes</span> <span m='2636250'>can</span> <span
  m='2636400'>be</span> <span m='2636490'>numbered</span> <span
  m='2637780'>in</span> <span m='2638350'>such</span> <span m='2638680'>a</span>
  <span m='2638740'>way</span> <span m='2639130'>that</span> <span
  m='2639890'>it's</span> <span m='2640120'>0</span> <span
  m='2640540'>above</span> <span m='2640900'>or</span> <span
  m='2641020'>on</span> <span m='2641620'>the</span> <span
  m='2641830'>main</span> <span m='2642100'>diagonal.</span> <span
  m='2643780'>As</span> <span m='2644380'>you'll</span> <span
  m='2644530'>see</span> <span m='2644740'>as</span> <span
  m='2644860'>you</span> <span m='2644920'>work</span> <span
  m='2645110'>some</span> <span m='2645250'>problems</span> <span
  m='2645730'>in</span> <span m='2645790'>the</span> <span
  m='2645880'>study</span> <span m='2646240'>guide,</span> <span
  m='2647740'>a</span> <span m='2648310'>non-computable</span> <span
  m='2649060'>network,</span> <span m='2649990'>in</span> <span
  m='2650110'>essence,</span> <span m='2650540'>what</span> <span
  m='2650590'>happens</span> <span m='2651640'>is</span> <span
  m='2652360'>that</span> <span m='2652810'>we</span> <span
  m='2652990'>have</span> <span m='2653230'>a</span> <span
  m='2653290'>set</span> <span m='2653530'>of</span> <span
  m='2653650'>nodes</span> <span m='2654250'>in</span> <span
  m='2654430'>the</span> <span m='2654490'>network</span> <span
  m='2655690'>all</span> <span m='2655900'>of</span> <span
  m='2656020'>which</span> <span m='2656350'>are</span> <span
  m='2656500'>connected</span> <span m='2656980'>together</span> <span
  m='2658030'>by</span> <span m='2659580'>non-delay</span> <span
  m='2660370'>branches.</span> <span m='2661550'>And</span> <span
  m='2661640'>so</span> <span m='2661780'>you</span> <span
  m='2661960'>can</span> <span m='2662110'>see</span> <span
  m='2662320'>that</span> <span m='2662440'>what</span> <span
  m='2662590'>happens</span> <span m='2663070'>is</span> <span
  m='2663520'>to</span> <span m='2663640'>compute</span> <span
  m='2664030'>this</span> <span m='2664300'>one</span> <span
  m='2664960'>I</span> <span m='2665020'>need</span> <span
  m='2665230'>that</span> <span m='2665500'>one.</span> <span
  m='2665950'>But</span> <span m='2666310'>to</span> <span
  m='2666430'>compute</span> <span m='2666730'>that</span> <span
  m='2666970'>when,</span> <span m='2667120'>I</span> <span
  m='2667180'>need</span> <span m='2667390'>this</span> <span
  m='2667630'>one.</span> <span m='2667810'>But</span> <span
  m='2667960'>to</span> <span m='2668050'>compute</span> <span
  m='2668410'>this</span> <span m='2668650'>one,</span> <span
  m='2668800'>I</span> <span m='2668860'>need</span> <span
  m='2668960'>this.</span> <span m='2669060'>But</span> <span
  m='2669390'>to</span> <span m='2669520'>compute</span> <span
  m='2669850'>that,</span> <span m='2670090'>I</span> <span
  m='2670150'>need</span> <span m='2670330'>that.</span> <span
  m='2670960'>There's</span> <span m='2671110'>no</span> <span
  m='2671290'>way</span> <span m='2671470'>to</span> <span
  m='2671560'>get</span> <span m='2671710'>out</span> <span
  m='2671860'>of</span> <span m='2671920'>that</span> <span
  m='2672130'>loop.</span> </p><p><span m='2673340'>So</span> <span
  m='2674710'>if</span> <span m='2674890'>there's</span> <span
  m='2675100'>a</span> <span m='2675190'>delay</span> <span
  m='2675580'>free</span> <span m='2675820'>loop</span> <span
  m='2676060'>in</span> <span m='2676150'>the</span> <span
  m='2676210'>network,</span> <span m='2676660'>it</span> <span
  m='2676720'>turns</span> <span m='2677110'>out</span> <span
  m='2677620'>that</span> <span m='2678250'>that</span> <span
  m='2678430'>corresponds</span> <span m='2679120'>to</span> <span
  m='2679240'>a</span> <span m='2679270'>non-computable</span> <span
  m='2680050'>network.</span> <span m='2681050'>Although</span> <span
  m='2681460'>it's</span> <span m='2681640'>important</span> <span
  m='2682150'>to</span> <span m='2682300'>stress</span> <span
  m='2683230'>that</span> <span m='2684070'>the</span> <span
  m='2684580'>non-computability</span> <span m='2685570'>doesn't</span> <span
  m='2685930'>mean</span> <span m='2686500'>that</span> <span
  m='2686740'>the</span> <span m='2686890'>set</span> <span
  m='2687100'>of</span> <span m='2687190'>equations</span> <span
  m='2687790'>can't</span> <span m='2688060'>be</span> <span
  m='2688210'>solved,</span> <span m='2689410'>the</span> <span
  m='2689530'>set</span> <span m='2689680'>of</span> <span
  m='2689770'>equations</span> <span m='2690490'>can</span> <span
  m='2690640'>still</span> <span m='2690880'>be</span> <span
  m='2691000'>solved,</span> <span m='2691930'>or</span> <span
  m='2692140'>the</span> <span m='2692230'>network</span> <span
  m='2692530'>can</span> <span m='2692680'>be</span> <span
  m='2692830'>rearranged.</span> <span m='2694480'>What</span> <span
  m='2694630'>it</span> <span m='2694720'>simply</span> <span
  m='2695080'>means</span> <span m='2695560'>is</span> <span
  m='2695830'>that</span> <span m='2696220'>non-computability</span> <span
  m='2697090'>means</span> <span m='2697630'>that</span> <span
  m='2698170'>we</span> <span m='2698290'>can't</span> <span
  m='2698590'>compute</span> <span m='2699280'>the</span> <span
  m='2700090'>node</span> <span m='2700780'>variables</span> <span
  m='2702040'>in</span> <span m='2702310'>sequence.</span> <span
  m='2702820'>We</span> <span m='2702910'>can't</span> <span
  m='2703120'>start</span> <span m='2703360'>with</span> <span
  m='2703450'>w1</span> <span m='2703720'>of</span> <span m='2703930'>n</span>
  <span m='2704200'>and</span> <span m='2704290'>then</span> <span
  m='2704410'>go</span> <span m='2704590'>on</span> <span m='2704690'>the</span>
  <span m='2704800'>w2</span> <span m='2705280'>of</span> <span
  m='2705370'>n</span> <span m='2705520'>and</span> <span
  m='2705630'>then</span> <span m='2705760'>w3</span> <span
  m='2706015'>of</span> <span m='2706270'>n,</span> <span
  m='2706510'>etc.</span> </p><p><span m='2708130'>Well,</span> <span
  m='2708340'>this</span> <span m='2708550'>issue</span> <span
  m='2709030'>of</span> <span m='2709150'>non-computability</span> <span
  m='2710860'>is</span> <span m='2711730'>just</span> <span
  m='2712180'>one</span> <span m='2712720'>brief</span> <span
  m='2713050'>glimpse</span> <span m='2713470'>in</span> <span
  m='2713590'>fact</span> <span m='2714100'>into</span> <span
  m='2715510'>the</span> <span m='2716500'>kinds</span> <span
  m='2717070'>of</span> <span m='2717250'>network</span> <span
  m='2717700'>properties</span> <span m='2718960'>that</span> <span
  m='2719530'>can</span> <span m='2719920'>be</span> <span
  m='2720130'>pulled</span> <span m='2720520'>out</span> <span
  m='2720760'>of</span> <span m='2721120'>either</span> <span
  m='2721360'>the</span> <span m='2721480'>signal</span> <span
  m='2721810'>flow</span> <span m='2722110'>graph</span> <span
  m='2722770'>representation</span> <span m='2723570'>of</span> <span
  m='2723640'>properties</span> <span m='2724150'>of</span> <span
  m='2724240'>signal</span> <span m='2724540'>flow</span> <span
  m='2724840'>graphs</span> <span m='2725680'>or</span> <span
  m='2726160'>out</span> <span m='2726340'>of</span> <span
  m='2726430'>the</span> <span m='2726550'>matrix</span> <span
  m='2727420'>representation.</span> <span m='2729400'>As</span> <span
  m='2729610'>I</span> <span m='2729760'>indicated</span> <span
  m='2730210'>at</span> <span m='2730270'>the</span> <span
  m='2730360'>beginning</span> <span m='2730720'>of</span> <span
  m='2730810'>the</span> <span m='2730900'>lecture,</span> <span
  m='2731920'>we</span> <span m='2732040'>won't</span> <span
  m='2732280'>be</span> <span m='2732580'>exploiting</span> <span
  m='2733600'>these</span> <span m='2733810'>kinds</span> <span
  m='2734110'>of</span> <span m='2734170'>properties.</span> <span
  m='2734740'>There</span> <span m='2734920'>is,</span> <span
  m='2735140'>in</span> <span m='2735160'>fact,</span> <span
  m='2736520'>a</span> <span m='2736620'>rather</span> <span
  m='2736840'>lengthy</span> <span m='2737170'>discussion</span> <span
  m='2738010'>of</span> <span m='2738760'>properties</span> <span
  m='2739390'>of</span> <span m='2739480'>digital</span> <span
  m='2739820'>networks</span> <span m='2740560'>in</span> <span
  m='2740680'>the</span> <span m='2740770'>text,</span> <span
  m='2741410'>which</span> <span m='2741670'>we</span> <span
  m='2742060'>won't</span> <span m='2742300'>be</span> <span
  m='2742420'>going</span> <span m='2742690'>into</span> <span
  m='2743020'>further.</span> </p><p><span m='2744100'>In</span> <span
  m='2744610'>the</span> <span m='2744730'>next</span> <span
  m='2744910'>several</span> <span m='2745300'>lectures</span> <span
  m='2746140'>what</span> <span m='2746530'>we'll</span> <span
  m='2747010'>concentrate</span> <span m='2747820'>on</span> <span
  m='2748780'>are</span> <span m='2749260'>the</span> <span
  m='2749410'>more</span> <span m='2749650'>common</span> <span
  m='2750820'>digital</span> <span m='2751960'>network</span> <span
  m='2752500'>structures</span> <span m='2753760'>for</span> <span
  m='2753910'>implementing</span> <span m='2755140'>both</span> <span
  m='2757600'>infinite</span> <span m='2757960'>impulse</span> <span
  m='2758350'>response,</span> <span m='2758840'>or</span> <span
  m='2758920'>recursive</span> <span m='2759730'>digital</span> <span
  m='2760060'>filters,</span> <span m='2760990'>and</span> <span
  m='2761200'>finite</span> <span m='2761680'>impulse</span> <span
  m='2762070'>response,</span> <span m='2762700'>or</span> <span
  m='2763120'>non-recursive</span> <span m='2763780'>digital</span> <span
  m='2764110'>filters.</span> <span m='2764840'>Thank</span> <span
  m='2765080'>you.</span> </p>
embedded_media:
  - uid: 818a7bf3f67aefa06bcad5fc945950d6
    parent_uid: 4702023b32f277d17778723243b6c058
    id: MITRES_6_008S11_lec11.pdf
    title: MITRES_6_008S11_lec11.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-11-representation-of-linear-digital-networks/MITRES_6_008S11_lec11.pdf
  - uid: 11ab684b5d4a5ea753942ff4988df348
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: xwRn_lTA6JY
  - uid: 5dc588d28f386481b20f0aed271f9d1c
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-11-representation/id481803782?i=108361992
  - uid: f4843be9654dc9896c63b24e73f9423a
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec11_300k.mp4'
  - uid: 1345967a3d26643cf4c8f6024e6f98c6
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/xwRn_lTA6JY/default.jpg'
  - uid: edef69e8ac0df85920602bdef4fded58
    parent_uid: 4702023b32f277d17778723243b6c058
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: xwRn_lTA6JY
  - uid: 965ddd8698ec7430637621e9a1888c81
    parent_uid: 4702023b32f277d17778723243b6c058
    id: xwRn_lTA6JY.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-11-representation-of-linear-digital-networks/xwRn_lTA6JY.srt
  - uid: 963ebb3e618731eb7a84bb972a3c820e
    parent_uid: 4702023b32f277d17778723243b6c058
    id: xwRn_lTA6JY.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-11-representation-of-linear-digital-networks/xwRn_lTA6JY.pdf
  - uid: c585dbe8d2ad1d541716bb058a5d7f95
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 8202d632aa6ba8e442627813eb7414a6
    parent_uid: 4702023b32f277d17778723243b6c058
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
