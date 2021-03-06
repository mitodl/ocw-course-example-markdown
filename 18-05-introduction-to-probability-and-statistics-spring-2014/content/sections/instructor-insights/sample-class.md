---
order_index: null
title: 'Sample Class: Class 11–Bayesian Updating: Discrete Priors'
template_type: Embed
uid: b09c96b115749aa10e37c1edf840eb0f
parent_uid: 1b6858820e39dbc6ba03dc47858871bd
technical_location: >-
  https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/instructor-insights/sample-class
short_url: sample-class
inline_embed_id: 59498249sampleclass37170367
about_this_resource_text: ''
related_resources_text: ''
transcript: >-
  <p><span m='70'>The</span> <span m='190'>following</span> <span
  m='630'>content</span> <span m='1230'>is</span> <span m='1340'>provided</span>
  <span m='1790'>under</span> <span m='2070'>a</span> <span
  m='2090'>Creative</span> <span m='2500'>Commons</span> <span
  m='2910'>license.</span> <span m='4010'>Your</span> <span
  m='4200'>support</span> <span m='4700'>will</span> <span m='4870'>help</span>
  <span m='5100'>MIT</span> <span m='5580'>OpenCourseWare</span> <span
  m='6360'>continue</span> <span m='6870'>to</span> <span m='6950'>offer</span>
  <span m='7380'>high</span> <span m='7590'>quality</span> <span
  m='8119'>educational</span> <span m='8740'>resources</span> <span
  m='9390'>for</span> <span m='9520'>free.</span> <span m='10710'>To</span>
  <span m='10730'>make</span> <span m='10930'>a</span> <span
  m='10980'>donation</span> <span m='11620'>or</span> <span
  m='11930'>view</span> <span m='12340'>additional</span> <span
  m='12800'>materials</span> <span m='13340'>from</span> <span
  m='13500'>hundreds</span> <span m='13930'>of</span> <span m='14040'>MIT</span>
  <span m='14460'>courses,</span> <span m='15570'>visit</span> <span
  m='15790'>MIT</span> <span m='16219'>OpenCourseWare</span> <span
  m='17260'>at</span> <span m='17430'>ocw.mit.edu.</span> </p><p><span
  m='21030'>PROFESSOR: All right, I</span> <span m='21080'>guess</span> <span
  m='21300'>we can</span> <span m='21400'>get</span> <span
  m='21640'>started</span> <span m='22060'>here.</span> <span
  m='23110'>So</span> <span m='23260'>welcome.</span> <span
  m='24670'>Today</span> <span m='25060'>we're</span> <span
  m='25190'>going</span> <span m='25330'>to</span> <span m='25400'>do</span>
  <span m='25980'>Bayesian</span> <span m='26920'>updating,</span> <span
  m='28070'>which</span> <span m='28290'>is</span> <span m='28390'>to</span>
  <span m='28500'>say</span> <span m='28670'>we're</span> <span
  m='28790'>going</span> <span m='28900'>to</span> <span m='28950'>be</span>
  <span m='29040'>using</span> <span m='29360'>Bayes'</span> <span
  m='29730'>Theorem</span> <span m='30490'>to</span> <span
  m='30650'>learn</span> <span m='31000'>from</span> <span
  m='31210'>data.</span> <span m='31560'>We're</span> <span
  m='31680'>going</span> <span m='31790'>to</span> <span m='31890'>update</span>
  <span m='32369'>our</span> <span m='32540'>beliefs</span> <span
  m='33200'>about</span> <span m='34250'>various</span> <span
  m='34610'>hypotheses</span> <span m='35850'>based</span> <span
  m='36170'>on</span> <span m='36280'>the</span> <span m='36380'>data.</span>
  <span m='36950'>For</span> <span m='37140'>this</span> <span
  m='37450'>week,</span> <span m='38550'>we're</span> <span
  m='38860'>going</span> <span m='38960'>to</span> <span m='39020'>have</span>
  <span m='39200'>known</span> <span m='39630'>priors.</span> <span
  m='40190'>We're</span> <span m='40300'>going</span> <span m='40420'>to</span>
  <span m='40500'>know</span> <span m='41100'>our</span> <span
  m='41240'>belief</span> <span m='41590'>about</span> <span
  m='41850'>the</span> <span m='41940'>data</span> <span m='42360'>ahead</span>
  <span m='42570'>of</span> <span m='42680'>time</span> <span
  m='43470'>for</span> <span m='43640'>certain.</span> <span
  m='43960'>We'll</span> <span m='44100'>draw</span> <span
  m='44730'>coins</span> <span m='45170'>out</span> <span m='45360'>of</span>
  <span m='48520'>drawers</span> <span m='49090'>or</span> <span
  m='49880'>pull</span> <span m='50080'>things</span> <span m='50350'>out</span>
  <span m='50480'>of</span> <span m='50550'>hats,</span> <span
  m='51160'>things</span> <span m='51410'>like</span> <span
  m='51590'>that.</span> </p><p><span m='52020'>Starting</span> <span
  m='52460'>next</span> <span m='52780'>week,</span> <span m='53160'>and</span>
  <span m='53440'>we</span> <span m='53630'>discussed</span> <span
  m='54120'>this</span> <span m='54300'>a</span> <span m='54370'>little</span>
  <span m='54620'>last</span> <span m='54980'>time,</span> <span
  m='55850'>we'll</span> <span m='56060'>have</span> <span
  m='56340'>unknown</span> <span m='56840'>priors,</span> <span
  m='57340'>which</span> <span m='57550'>is</span> <span m='57690'>you'll</span>
  <span m='57940'>have</span> <span m='58050'>to</span> <span
  m='58140'>be</span> <span m='58260'>making</span> <span m='58620'>up</span>
  <span m='58810'>those</span> <span m='59040'>priors.</span> <span
  m='59380'>And</span> <span m='59500'>we'll</span> <span m='60530'>teach</span>
  <span m='60910'>you</span> <span m='61650'>techniques</span> <span
  m='62220'>for</span> <span m='62330'>making</span> <span m='62700'>it</span>
  <span m='62810'>up.</span> <span m='63050'>So</span> <span
  m='64640'>the</span> <span m='64819'>first</span> <span m='65099'>slide</span>
  <span m='65480'>is</span> <span m='65680'>just</span> <span
  m='66860'>XKCD's</span> <span m='67800'>view</span> <span m='67990'>of</span>
  <span m='68100'>Bayes'</span> <span m='68500'>Theorem.</span> <span
  m='70440'>Let's</span> <span m='70630'>go on.</span> <span m='70860'>We</span>
  <span m='70970'>want</span> <span m='71130'>to</span> <span
  m='71180'>start</span> <span m='72110'>with</span> <span m='72350'>a</span>
  <span m='73620'>clicker</span> <span m='73980'>question</span> <span
  m='74390'>here.</span> </p><p><span m='77920'>So</span> <span
  m='78130'>the</span> <span m='78240'>question</span> <span m='78640'>is</span>
  <span m='79650'>which</span> <span m='79850'>treatment</span> <span
  m='80350'>would</span> <span m='80520'>you</span> <span
  m='80630'>choose</span> <span m='81040'>if</span> <span m='81170'>you</span>
  <span m='81280'>needed</span> <span m='81610'>a</span> <span
  m='81670'>treatment?</span> <span m='82110'>Treatment</span> <span
  m='82460'>1</span> <span m='83180'>cured</span> <span m='83510'>100%</span>
  <span m='84320'>of</span> <span m='84400'>the</span> <span
  m='84490'>patients.</span> <span m='85870'>Treatment</span> <span
  m='86240'>2</span> <span m='86440'>cured</span> <span m='86700'>95%</span>
  <span m='88310'>in</span> <span m='88540'>a</span> <span
  m='88610'>trial.</span> <span m='89060'>And</span> <span
  m='89200'>treatment</span> <span m='89550'>3</span> <span
  m='89800'>cured</span> <span m='90110'>90%.</span> <span m='91930'>So</span>
  <span m='92600'>with</span> <span m='92790'>this</span> <span
  m='93020'>information</span> <span m='94060'>which</span> <span
  m='94290'>would</span> <span m='94420'>you</span> <span
  m='94520'>choose?</span> </p><p><span m='99830'>AUDIENCE: With only this
  information?</span> </p><p><span m='100770'>PROFESSOR: With</span> <span
  m='101010'>only</span> <span m='101290'>this.</span> <span
  m='101470'>If</span> <span m='101630'>this</span> <span m='101820'>is</span>
  <span m='101970'>all</span> <span m='102150'>I</span> <span
  m='102240'>told</span> <span m='102580'>you.</span> <span
  m='104610'>Which</span> <span m='105000'>would you</span> <span
  m='105440'>choose?</span> <span m='106020'>I</span> <span
  m='106320'>recognizing</span> <span m='106625'>that</span> <span
  m='106930'>you</span> <span m='107020'>might</span> <span
  m='107210'>not</span> <span m='107410'>be</span> <span m='107790'>too</span>
  <span m='107970'>happy</span> <span m='108400'>with</span> <span
  m='108570'>just this</span> <span m='109000'>information,</span> <span
  m='109600'>but</span> <span m='109740'>if</span> <span m='109830'>this</span>
  <span m='110050'>is</span> <span m='110230'>their</span> <span
  m='110370'>best</span> <span m='110730'>information,</span> <span
  m='112300'>what</span> <span m='112430'>would</span> <span
  m='112560'>you</span> <span m='112650'>choose?</span> <span
  m='113590'>All</span> <span m='113690'>right,</span> <span
  m='114100'>there's</span> <span m='114580'>some</span> <span m='115080'>hold
  outs</span> <span m='115660'>for</span> <span m='115770'>the</span> <span
  m='115910'>95%</span> <span m='116880'>cure.</span> <span
  m='117110'>I'm</span> <span m='117200'>not</span> <span m='117420'>sure</span>
  <span m='117610'>why.</span> <span m='120470'>Really,</span> <span
  m='120970'>that</span> <span m='121160'>95%</span> <span m='122120'>was</span>
  <span m='122320'>just, you know,</span> <span m='122740'>they've</span> <span
  m='123620'>cured</span> <span m='123920'>one</span> <span
  m='124220'>person</span> <span m='124760'>19</span> <span
  m='125260'>out</span> <span m='125400'>of</span> <span m='125610'>20.</span>
  <span m='128139'>They</span> <span m='128310'>got</span> <span
  m='128470'>them</span> <span m='128520'>19</span> <span m='129340'>out</span>
  <span m='129449'>of</span> <span m='129539'>20</span> <span
  m='129860'>well,</span> <span m='130630'>or however you say that.</span>
  </p><p><span m='131640'>Yeah.</span> <span m='132390'>All</span> <span
  m='132490'>right,</span> <span m='132720'>so</span> <span
  m='133840'>there's</span> <span m='134060'>even</span> <span
  m='134280'>a</span> <span m='134330'>few</span> <span m='134530'>more</span>
  <span m='134780'>holdouts.</span> <span m='136880'>All</span> <span
  m='136980'>right,</span> <span m='137240'>what</span> <span
  m='137430'>if</span> <span m='137560'>I</span> <span m='137630'>gave</span>
  <span m='137920'>you</span> <span m='138280'>this</span> <span
  m='138710'>information?</span> <span m='140790'>Treatment</span> <span
  m='141100'>1</span> <span m='141390'>cured</span> <span m='143300'>3</span>
  <span m='143670'>out</span> <span m='143790'>of</span> <span
  m='143910'>3</span> <span m='144100'>patients.</span> <span
  m='144590'>That's</span> <span m='144770'>100%.</span> <span
  m='146430'>Treatment</span> <span m='146880'>2</span> <span
  m='147120'>cured</span> <span m='147380'>19</span> <span m='147920'>of</span>
  <span m='148130'>20</span> <span m='148440'>patients.</span> <span
  m='148990'>That's</span> <span m='150440'>95%.</span> <span
  m='152230'>Or,</span> <span m='152420'>you</span> <span m='152520'>have</span>
  <span m='152640'>a</span> <span m='152690'>standard</span> <span
  m='153230'>treatment</span> <span m='153600'>which</span> <span
  m='153830'>has</span> <span m='153980'>cured</span> <span
  m='154310'>90,000</span> <span m='155260'>out</span> <span
  m='155410'>of</span> <span m='156070'>100,000</span> <span
  m='156850'>patients,</span> <span m='157540'>90%,</span> <span
  m='158920'>in</span> <span m='159180'>clinical</span> <span
  m='159620'>practice.</span> <span m='161120'>Now</span> <span
  m='161380'>which</span> <span m='161550'>one</span> <span
  m='161740'>would</span> <span m='161910'>you</span> <span
  m='162010'>choose?</span> </p><p><span m='170610'>PROFESSOR 2: It's</span>
  <span m='170750'>very</span> <span m='170920'>interesting.</span> <span
  m='173865'>Yeah, it</span> <span m='174306'>totally changed.</span>
  </p><p><span m='174747'>PROFESSOR: What's that?</span> </p><p><span
  m='175670'>PROFESSOR 2: It totally shifted.</span> </p><p><span
  m='176580'>PROFESSOR: It</span> <span m='177080'>totally</span> <span
  m='177410'>shifted,</span> <span m='177670'>really?</span> </p><p><span
  m='178360'>PROFESSOR 2: We have</span> <span m='178480'>a bunch of</span>
  <span m='178520'>very</span> <span m='178960'>conservative</span> <span
  m='179370'>people.</span> </p><p><span m='180230'>PROFESSOR: Right.</span>
  <span m='182400'>So</span> <span m='182850'>the</span> <span
  m='183020'>majority</span> <span m='183570'>would</span> <span
  m='183900'>choose</span> <span m='185810'>the</span> <span
  m='186010'>third</span> <span m='186370'>choice,</span> <span
  m='186800'>90</span> <span m='187260'>out</span> <span m='187440'>of</span>
  <span m='187840'>100,000.</span> <span m='189720'>I</span> <span
  m='190100'>think--</span> <span m='190490'>well</span> <span
  m='190730'>someone</span> <span m='191080'>tell</span> <span
  m='191250'>me,</span> <span m='191370'>what's</span> <span
  m='191600'>the</span> <span m='191700'>intuition</span> <span
  m='192310'>there?</span> </p><p><span m='193554'>AUDIENCE: Because it's been
  more tested.</span> </p><p><span m='195330'>PROFESSOR: It's been</span> <span
  m='195440'>more</span> <span m='195630'>tested.</span> <span
  m='196130'>3</span> <span m='196420'>out</span> <span m='196530'>of</span>
  <span m='196650'>3</span> <span m='196880'>is</span> <span
  m='197000'>100%,</span> <span m='197340'>but</span> <span m='197705'>do</span>
  <span m='198070'>you</span> <span m='198190'>really</span> <span
  m='198390'>believe</span> <span m='199640'>100%?</span> <span
  m='200480'>Not</span> <span m='200740'>yet.</span> <span
  m='201300'>Maybe</span> <span m='201630'>it'll</span> <span
  m='201750'>prove</span> <span m='202000'>out</span> <span m='202160'>in</span>
  <span m='202290'>time.</span> <span m='203590'>19</span> <span m='203930'>out
  of</span> <span m='204170'>20 is</span> <span m='204600'>a</span> <span
  m='204670'>little</span> <span m='204900'>more,</span> <span
  m='205210'>but</span> <span m='205660'>for</span> <span m='205850'>most</span>
  <span m='206250'>people,</span> <span m='207780'>for</span> <span
  m='208120'>79%</span> <span m='209220'>of</span> <span m='209300'>you,</span>
  <span m='209430'>that's</span> <span m='209740'>not</span> <span
  m='209980'>enough.</span> <span m='211620'>The</span> <span
  m='211760'>90</span> <span m='212150'>out</span> <span m='212270'>of</span>
  <span m='212360'>100,000</span> <span m='213100'>seems</span> <span
  m='213350'>like</span> <span m='213570'>good</span> <span
  m='213780'>odds,</span> <span m='216110'>and</span> <span
  m='216310'>it's</span> <span m='216470'>well</span> <span
  m='216760'>tested.</span> <span m='217900'>19</span> <span
  m='218280'>out</span> <span m='218400'>of</span> <span m='218510'>20,</span>
  <span m='219350'>if</span> <span m='219570'>the</span> <span
  m='219670'>next</span> <span m='219960'>person</span> <span
  m='221790'>tested</span> <span m='222810'>doesn't</span> <span
  m='223130'>get</span> <span m='223320'>better,</span> <span
  m='224130'>now</span> <span m='224260'>you</span> <span m='224400'>back</span>
  <span m='224690'>to</span> <span m='224810'>90%.</span> <span
  m='226570'>So</span> <span m='226750'>that</span> <span
  m='227110'>doesn't</span> <span m='227460'>seem</span> <span
  m='227630'>like</span> <span m='228060'>quite</span> <span
  m='228300'>enough.</span> <span m='228650'>What if</span> <span
  m='228970'>were</span> <span m='229200'>95</span> <span m='230560'>out</span>
  <span m='230700'>of</span> <span m='230770'>100</span> <span
  m='231240'>patients.</span> <span m='233700'>We'll</span> <span
  m='233770'>let</span> <span m='233950'>you</span> <span
  m='234050'>click</span> <span m='234310'>in</span> <span
  m='234400'>there.</span> <span m='234580'>Change</span> <span
  m='234890'>number</span> <span m='235150'>2</span> <span m='235350'>to</span>
  <span m='235480'>95</span> <span m='236100'>out</span> <span
  m='236210'>of</span> <span m='236270'>100 and</span> <span
  m='236750'>let's</span> <span m='237020'>see</span> <span
  m='237140'>what</span> <span m='237710'>people</span> <span
  m='238000'>would</span> <span m='238150'>do.</span> <span m='240370'>Oh,
  you're</span> <span m='240530'>very</span> <span m='240820'>obliging,</span>
  <span m='241480'>95</span> <span m='242100'>out</span> <span
  m='242210'>of</span> <span m='242270'>100--</span> </p><p><span
  m='242780'>PROFESSOR 2: Now</span> <span m='243263'>it's about 50-50.</span>
  </p><p><span m='244230'>PROFESSOR: About</span> <span m='244540'>50-50.</span>
  </p><p><span m='246270'>PROFESSOR 2: Between 2 and 3.</span> </p><p><span
  m='249530'>PROFESSOR: Realistically,</span> <span m='250370'>of</span> <span
  m='250490'>course,</span> <span m='250750'>what would</span> <span
  m='250990'>you</span> <span m='251080'>want</span> <span m='251210'>to</span>
  <span m='251280'>do?</span> <span m='251450'>You'd</span> <span
  m='251600'>want</span> <span m='251760'>to</span> <span m='251830'>do</span>
  <span m='252130'>a</span> <span m='252240'>little</span> <span
  m='252470'>more</span> <span m='253680'>research</span> <span
  m='254240'>and</span> <span m='254360'>find</span> <span m='254630'>out</span>
  <span m='254800'>what</span> <span m='255050'>these</span> <span
  m='255290'>trials</span> <span m='255760'>were,</span> <span
  m='256620'>how</span> <span m='256779'>good</span> <span
  m='256980'>experiments</span> <span m='257600'>you</span> <span
  m='257730'>thought</span> <span m='258010'>they</span> <span
  m='258450'>were,</span> <span m='258640'>what</span> <span
  m='258970'>people</span> <span m='259230'>are</span> <span
  m='259329'>thinking</span> <span m='259750'>about</span> <span
  m='260029'>it.</span> <span m='260820'>But with</span> <span
  m='261050'>just</span> <span m='261269'>this</span> <span
  m='261510'>data,</span> <span m='262450'>that's</span> <span
  m='262610'>what</span> <span m='262760'>people</span> <span
  m='262980'>would</span> <span m='263090'>choose.</span> <span m='263330'>And
  would</span> <span m='263450'>people would</span> <span
  m='263830'>choose</span> <span m='264090'>differently.</span> <span
  m='265040'>OK.</span> </p><p><span m='267360'>PROFESSOR 2: Let's</span> <span
  m='267570'>see.</span> <span m='269810'>So</span> <span m='270280'>now</span>
  <span m='271010'>I'm</span> <span m='271110'>going</span> <span
  m='271190'>to</span> <span m='271230'>give</span> <span m='271390'>you</span>
  <span m='271500'>a</span> <span m='271550'>toy</span> <span
  m='271760'>problem</span> <span m='272680'>that</span> <span
  m='273390'>actually</span> <span m='273750'>mirrors</span> <span
  m='274350'>the</span> <span m='274450'>same</span> <span
  m='274980'>kind</span> <span m='275200'>of</span> <span
  m='275260'>effect</span> <span m='275590'>we</span> <span
  m='275670'>saw</span> <span m='276020'>on</span> <span m='276200'>the</span>
  <span m='276270'>last</span> <span m='276530'>slide.</span> <span
  m='277470'>So,</span> <span m='277920'>suppose</span> <span
  m='279020'>in</span> <span m='279190'>this</span> <span m='279630'>MIT</span>
  <span m='280030'>mug,</span> <span m='282350'>I</span> <span
  m='282450'>have</span> <span m='282600'>dice</span> <span m='283120'>of</span>
  <span m='283230'>two</span> <span m='283340'>types,</span> <span
  m='284100'>4-sided</span> <span m='285300'>and</span> <span
  m='286100'>20-sided.</span> <span m='287720'>All right?</span> <span
  m='288210'>So</span> <span m='288340'>I'm</span> <span m='288410'>going</span>
  <span m='288490'>to</span> <span m='288540'>reach</span> <span
  m='288770'>into</span> <span m='288940'>the</span> <span
  m='289020'>mug.</span> <span m='290760'>I'm</span> <span m='291040'>not</span>
  <span m='291220'>going</span> <span m='291320'>to</span> <span
  m='291370'>look.</span> <span m='293380'>Much.</span> <span
  m='295880'>I'm</span> <span m='296030'>going to</span> <span
  m='296160'>randomly</span> <span m='296610'>pull</span> <span
  m='296890'>out</span> <span m='297010'>a</span> <span m='297070'>die.</span>
  <span m='299540'>I'm going to roll it.</span> <span m='302750'>All
  right,</span> <span m='302840'>I</span> <span m='302880'>got</span> <span
  m='303020'>a</span> <span m='303080'>1.</span> </p><p><span
  m='305200'>OK.</span> <span m='306450'>I</span> <span m='306540'>got</span>
  <span m='306690'>a</span> <span m='306740'>1.</span> <span
  m='307270'>Now,</span> <span m='309590'>just</span> <span
  m='309830'>based</span> <span m='310140'>on</span> <span
  m='310240'>this</span> <span m='310410'>information,</span> <span
  m='312060'>which</span> <span m='312590'>type</span> <span
  m='312820'>of</span> <span m='312930'>die</span> <span m='313190'>do</span>
  <span m='313260'>you</span> <span m='313370'>think</span> <span
  m='313700'>I</span> <span m='313840'>randomly</span> <span
  m='314220'>chose?</span> <span m='317340'>The</span> <span
  m='317440'>4-sided.</span> <span m='318260'>Someone</span> <span
  m='318540'>want</span> <span m='318670'>to</span> <span m='318710'>give</span>
  <span m='318860'>an</span> <span m='318940'>explanation</span> <span
  m='319580'>of</span> <span m='319680'>why</span> <span m='319840'>they</span>
  <span m='319970'>think</span> <span m='320170'>the</span> <span
  m='320250'>4-sided</span> <span m='320630'>is</span> <span
  m='320750'>more</span> <span m='320870'>likely?</span> </p><p><span
  m='321728'>AUDIENCE: It's greater probability.</span> </p><p><span
  m='323680'>PROFESSOR 2: It's</span> <span m='323890'>greater</span> <span
  m='324140'>probability.</span> <span m='324890'>What's</span> <span
  m='325270'>the</span> <span m='325340'>probability</span> <span
  m='325880'>of</span> <span m='325940'>getting</span> <span m='326150'>a</span>
  <span m='326240'>1</span> <span m='326490'>on</span> <span
  m='326570'>the</span> <span m='326630'>4-sided</span> <span
  m='327090'>die?</span> <span m='328180'>And</span> <span
  m='328290'>what</span> <span m='328410'>about</span> <span m='328680'>a</span>
  <span m='328730'>20-sided</span> <span m='328980'>sided?</span> <span
  m='330230'>OK.</span> <span m='330960'>So</span> <span m='332470'>we</span>
  <span m='332620'>see</span> <span m='332790'>that</span> <span
  m='332930'>it</span> <span m='332990'>would</span> <span m='333120'>be</span>
  <span m='333200'>more</span> <span m='333390'>likely</span> <span
  m='333830'>to</span> <span m='333950'>roll</span> <span m='334180'>a 1</span>
  <span m='335300'>with</span> <span m='335430'>a</span> <span
  m='335480'>4-sided</span> <span m='335960'>die</span> <span
  m='336160'>than</span> <span m='336280'>with</span> <span m='336400'>a</span>
  <span m='336440'>20-sided</span> <span m='336970'>die.</span> </p><p><span
  m='338180'>So,</span> <span m='340660'>suppose</span> <span
  m='341020'>I</span> <span m='341090'>tell</span> <span m='341330'>you</span>
  <span m='341480'>that</span> <span m='342010'>I</span> <span
  m='342380'>really</span> <span m='342700'>in</span> <span
  m='342800'>this</span> <span m='343050'>cup</span> <span
  m='343330'>only</span> <span m='343570'>have</span> <span
  m='343830'>one</span> <span m='344220'>die of</span> <span
  m='344560'>each</span> <span m='344760'>type.</span> <span
  m='346820'>So</span> <span m='346980'>does</span> <span m='347090'>that</span>
  <span m='347260'>change</span> <span m='348720'>your</span> <span
  m='348840'>analysis</span> <span m='349380'>of</span> <span
  m='349450'>which</span> <span m='349690'>die is</span> <span
  m='349910'>most</span> <span m='350130'>likely?</span> <span m='350820'>Don't
  hit</span> <span m='351140'>forward</span> <span m='351510'>yet.</span>
  </p><p><span m='352680'>PROFESSOR: I</span> <span m='352760'>would</span>
  <span m='353070'>think</span> <span m='353260'>of it.</span> <span
  m='354120'>My hands are</span> <span m='354310'>staying.</span> </p><p><span
  m='356450'>PROFESSOR 2: Or</span> <span m='356600'>do</span> <span
  m='356660'>you</span> <span m='356780'>want</span> <span m='356920'>to</span>
  <span m='356980'>stick</span> <span m='357210'>with</span> <span
  m='357340'>the</span> <span m='358380'>same</span> <span
  m='358620'>reasoning?</span> <span m='360130'>All</span> <span
  m='360210'>right.</span> <span m='360850'>Let</span> <span m='361110'>me
  show</span> <span m='361240'>you what's</span> <span
  m='361400'>actually</span> <span m='361720'>in</span> <span
  m='361790'>this</span> <span m='361950'>cup.</span> </p><p><span
  m='369002'>PROFESSOR: Ouch.</span> </p><p><span m='369960'>PROFESSOR 2:
  Oh,</span> <span m='370100'>you</span> <span m='370180'>can't</span> <span
  m='370400'>see it</span> <span m='370560'>yet.</span> <span
  m='372630'>Let's</span> <span m='372870'>go</span> <span
  m='373050'>with</span> <span m='374420'>the</span> <span
  m='374830'>document</span> <span m='375230'>camera.</span> <span
  m='378940'>OK,</span> <span m='379240'>that</span> <span m='379420'>was</span>
  <span m='379550'>actually</span> <span m='379880'>what</span> <span
  m='380010'>I</span> <span m='380070'>had</span> <span m='380250'>in</span>
  <span m='380340'>this</span> <span m='380510'>cup.</span> <span
  m='382610'>Now</span> <span m='383580'>what?</span> <span m='384560'>So</span>
  <span m='385040'>does</span> <span m='385190'>this</span> <span
  m='385330'>change</span> <span m='385650'>at</span> <span
  m='385710'>all</span> <span m='385980'>of</span> <span m='386090'>your</span>
  <span m='386200'>analysis</span> <span m='387200'>which</span> <span
  m='387470'>die</span> <span m='387720'>you</span> <span
  m='387850'>think</span> <span m='388050'>I</span> <span
  m='388100'>rolled</span> <span m='388480'>and</span> <span
  m='388650'>got</span> <span m='388770'>a</span> <span m='388820'>1</span>
  <span m='389000'>with?</span> <span m='389250'>What</span> <span
  m='389430'>type</span> <span m='389630'>of</span> <span m='389730'>die,</span>
  <span m='389920'>rather?</span> </p><p><span m='391230'>AUDIENCE: Yes.</span>
  </p><p><span m='391665'>PROFESSOR 2: Yeah?</span> <span m='392100'>Now</span>
  <span m='392380'>what</span> <span m='392470'>do</span> <span
  m='392510'>you</span> <span m='392630'>think</span> <span m='392860'>is</span>
  <span m='392970'>more</span> <span m='393100'>likely?</span> <span
  m='393810'>4-sided</span> <span m='393990'>or</span> <span
  m='394330'>20-sided?</span> </p><p><span m='394940'>AUDIENCE: How many
  20-sided are there?</span> </p><p><span m='396400'>PROFESSOR 2: I</span> <span
  m='396470'>think</span> <span m='396660'>I</span> <span m='396690'>got</span>
  <span m='396870'>20</span> <span m='397150'>20-sided</span> <span
  m='397700'>die</span> <span m='397880'>there.</span> <span
  m='405110'>All</span> <span m='405200'>right,</span> <span
  m='405370'>so</span> <span m='405460'>raise</span> <span
  m='405650'>your</span> <span m='405770'>hand</span> <span m='406080'>if</span>
  <span m='406190'>you</span> <span m='406290'>like</span> <span
  m='406450'>a</span> <span m='406510'>4-sided</span> <span
  m='406990'>die.</span> <span m='409080'>Raise</span> <span
  m='409250'>your</span> <span m='409350'>hand</span> <span m='409520'>if</span>
  <span m='409590'>you</span> <span m='409660'>like</span> <span
  m='409830'>the</span> <span m='409880'>20-sided</span> <span
  m='410410'>die.</span> <span m='411880'>Great.</span> <span
  m='412350'>So</span> <span m='412540'>that</span> <span
  m='412850'>reasoning</span> <span m='413350'>that</span> <span
  m='413470'>you're</span> <span m='413550'>doing</span> <span
  m='413770'>intuitively</span> <span m='415230'>is</span> <span
  m='415380'>something</span> <span m='415680'>that</span> <span
  m='415780'>we</span> <span m='415870'>want</span> <span m='416000'>to</span>
  <span m='416050'>formalize</span> <span m='417170'>this</span> <span
  m='417360'>week</span> <span m='417560'>and</span> <span
  m='417640'>next</span> <span m='417900'>week</span> <span
  m='418800'>using</span> <span m='419110'>Bayes'</span> <span
  m='419420'>Theorem</span> <span m='419930'>to</span> <span
  m='420040'>do</span> <span m='420150'>these</span> <span
  m='420290'>calculations</span> <span m='420940'>in</span> <span
  m='421000'>a</span> <span m='421050'>systematic</span> <span
  m='421610'>way,</span> <span m='422460'>to</span> <span
  m='422630'>evaluate</span> <span m='423890'>hypotheses</span> <span
  m='424940'>based</span> <span m='425180'>on</span> <span
  m='425290'>data.</span> <span m='426380'>And</span> <span
  m='426770'>these</span> <span m='427140'>numbers,</span> <span
  m='428670'>for</span> <span m='428710'>example,</span> <span
  m='429700'>how</span> <span m='429910'>many</span> <span m='430230'>die</span>
  <span m='430540'>I</span> <span m='430630'>had of</span> <span
  m='430940'>one</span> <span m='431150'>type</span> <span
  m='431330'>versus</span> <span m='431620'>another,</span> <span
  m='432370'>we</span> <span m='432500'>can</span> <span
  m='432680'>encode</span> <span m='432860'>that</span> <span
  m='433060'>information</span> <span m='433320'>in</span> <span
  m='433580'>what's</span> <span m='433780'>called</span> <span
  m='434100'>a</span> <span m='434190'>prior,</span> <span m='434980'>and</span>
  <span m='435110'>we'll</span> <span m='435190'>come</span> <span
  m='435360'>to</span> <span m='435440'>that</span> <span
  m='436080'>today.</span> <span m='436420'>And you</span> <span
  m='436520'>should've</span> <span m='436750'>seen in your</span> <span
  m='437070'>reading</span> <span m='437880'>this</span> <span
  m='438070'>idea.</span> </p><p><span m='442810'>PROFESSOR: OK</span> <span
  m='443030'>so</span> <span m='443200'>I'm</span> <span m='443560'>going</span>
  <span m='443670'>to</span> <span m='443730'>work</span> <span
  m='443960'>through</span> <span m='444110'>an</span> <span
  m='444180'>example</span> <span m='444820'>to</span> <span
  m='444960'>start</span> <span m='445250'>with.</span> <span
  m='445420'>We</span> <span m='445540'>have</span> <span m='445890'>3</span>
  <span m='446580'>types</span> <span m='446910'>of</span> <span
  m='447030'>coins:</span> <span m='448400'>type A,</span> <span
  m='448670'>B,</span> <span m='449150'>and</span> <span m='449290'>C.</span>
  <span m='450640'>However</span> <span m='451090'>it</span> <span
  m='451170'>happens,</span> <span m='451720'>the</span> <span
  m='451810'>probability</span> <span m='452420'>of</span> <span
  m='452490'>getting</span> <span m='452770'>heads</span> <span
  m='453110'>with</span> <span m='453250'>type</span> <span m='453580'>A</span>
  <span m='454210'>is</span> <span m='454420'>0.5.</span> <span
  m='455040'>That's</span> <span m='455250'>a</span> <span
  m='455310'>fair</span> <span m='455660'>coin.</span> <span
  m='456130'>The</span> <span m='456590'>probability</span> <span
  m='457150'>of</span> <span m='457210'>getting</span> <span
  m='457520'>heads</span> <span m='457830'>with</span> <span
  m='458590'>type</span> <span m='458860'>B</span> <span m='459090'>is</span>
  <span m='459280'>0.6,</span> <span m='460820'>and</span> <span
  m='461200'>of</span> <span m='461430'>type</span> <span m='461650'>C</span>
  <span m='462370'>is</span> <span m='462550'>0.9.</span> <span
  m='464000'>And</span> <span m='464210'>here's</span> <span m='464490'>a</span>
  <span m='464540'>box</span> <span m='464940'>that</span> <span
  m='465070'>contains</span> <span m='466580'>two</span> <span
  m='466780'>of</span> <span m='466890'>the</span> <span m='467000'>fair</span>
  <span m='467320'>coins</span> <span m='468210'>and</span> <span
  m='468370'>one</span> <span m='468600'>of</span> <span m='468690'>each</span>
  <span m='468880'>of</span> <span m='468950'>the</span> <span
  m='469110'>other.</span> <span m='469460'>So</span> <span
  m='469510'>two</span> <span m='469690'>of</span> <span m='469790'>type
  A,</span> <span m='470270'>one</span> <span m='470510'>of</span> <span
  m='470610'>type</span> <span m='470880'>B,</span> <span m='471580'>and</span>
  <span m='471760'>one</span> <span m='471930'>of</span> <span
  m='472030'>type</span> <span m='472270'>C.</span> </p><p><span
  m='474070'>Suppose</span> <span m='474450'>I</span> <span
  m='474540'>pick</span> <span m='474910'>one</span> <span m='475120'>at</span>
  <span m='475240'>random</span> <span m='475780'>and</span> <span
  m='475900'>I</span> <span m='475960'>get</span> <span m='476170'>heads.</span>
  <span m='476490'>So</span> <span m='476650'>this</span> <span
  m='476830'>is</span> <span m='476980'>like</span> <span m='477160'>John</span>
  <span m='477630'>picking</span> <span m='478000'>a</span> <span m='478060'>die
  at</span> <span m='478480'>random,</span> <span m='479400'>and</span> <span
  m='479570'>getting</span> <span m='479830'>a</span> <span m='479900'>1.</span>
  <span m='480160'>I</span> <span m='480210'>get</span> <span
  m='480390'>heads.</span> <span m='482900'>Here's</span> <span
  m='483140'>the</span> <span m='483200'>question:</span> <span
  m='483630'>before</span> <span m='484080'>I</span> <span
  m='484190'>flipped</span> <span m='484630'>it,</span> <span
  m='484900'>I</span> <span m='485040'>have</span> <span m='485190'>a</span>
  <span m='485250'>prior</span> <span m='486290'>belief</span> <span
  m='486730'>in</span> <span m='488250'>the</span> <span
  m='488350'>probability</span> <span m='488930'>that</span> <span
  m='489110'>the</span> <span m='489210'>coin</span> <span m='489490'>was</span>
  <span m='489860'>of</span> <span m='490050'>each</span> <span
  m='490310'>type</span> <span m='490990'>based</span> <span
  m='491290'>on</span> <span m='491400'>the</span> <span
  m='491510'>number</span> <span m='491890'>in</span> <span m='491970'>my</span>
  <span m='492100'>drawer.</span> <span m='493610'>After</span> <span
  m='494040'>flipping</span> <span m='494490'>it,</span> <span
  m='496380'>my</span> <span m='496470'>believe</span> <span
  m='496850'>changes.</span> <span m='497390'>The</span> <span
  m='497470'>probability</span> <span m='498140'>will</span> <span
  m='498320'>change</span> <span m='499560'>based</span> <span
  m='499940'>on</span> <span m='500250'>the</span> <span m='500420'>data</span>
  <span m='500720'>I</span> <span m='500790'>get.</span> <span
  m='502180'>And</span> <span m='502420'>so</span> <span m='502900'>a</span>
  <span m='503000'>question</span> <span m='503340'>you</span> <span
  m='503410'>could</span> <span m='503520'>ask:</span> <span
  m='503770'>what</span> <span m='503940'>was</span> <span
  m='504160'>learned</span> <span m='504690'>by</span> <span
  m='504830'>flipping</span> <span m='505230'>the</span> <span
  m='505330'>coin?</span> </p><p><span m='507590'>What</span> <span
  m='507740'>we</span> <span m='507790'>want</span> <span m='507960'>to</span>
  <span m='509340'>teach</span> <span m='509610'>you</span> <span
  m='509700'>to</span> <span m='509790'>do</span> <span m='509950'>to</span>
  <span m='510080'>answer</span> <span m='510370'>these</span> <span
  m='510590'>questions,</span> <span m='511150'>we</span> <span
  m='511250'>have</span> <span m='511350'>a</span> <span m='511450'>nice</span>
  <span m='511680'>way</span> <span m='511880'>of</span> <span
  m='512000'>summarizing</span> <span m='513270'>all</span> <span
  m='513539'>of</span> <span m='513650'>that</span> <span m='513990'>once</span>
  <span m='515030'>in</span> <span m='515220'>a</span> <span
  m='515309'>table.</span> <span m='516280'>So</span> <span
  m='516940'>here</span> <span m='517289'>the</span> <span
  m='518559'>notation,</span> <span m='519669'>we</span> <span
  m='519870'>have</span> <span m='519980'>this</span> <span
  m='520159'>nice</span> <span m='521500'>scripty</span> <span
  m='522990'>H--</span> <span m='524090'>that's</span> <span
  m='524360'>no</span> <span m='524460'>good.</span> <span m='528110'>H</span>
  <span m='528810'>is</span> <span m='529000'>our</span> <span
  m='529110'>hypothesis.</span> <span m='532820'>That</span> <span
  m='533020'>is,</span> <span m='533200'>you're  of</span> <span
  m='533520'>type</span> <span m='535170'>A</span> <span m='536660'>or</span>
  <span m='536870'>B</span> <span m='538140'>or</span> <span
  m='538370'>C.</span> <span m='538740'>We're</span> <span
  m='538880'>going</span> <span m='538990'>to</span> <span
  m='539040'>make</span> <span m='539280'>a</span> <span
  m='539480'>conjecture</span> <span m='540530'>on</span> <span
  m='540730'>what</span> <span m='540930'>we</span> <span
  m='541080'>think</span> <span m='543990'>the</span> <span
  m='544160'>coin</span> <span m='544490'>was.</span> </p><p><span
  m='546690'>Before</span> <span m='547360'>we</span> <span m='547530'>do</span>
  <span m='547700'>anything,</span> <span m='548260'>we</span> <span
  m='548430'>have</span> <span m='550700'>a</span> <span
  m='550820'>prior.</span> <span m='551330'>So</span> <span
  m='551490'>what's</span> <span m='551680'>the</span> <span
  m='551760'>probability</span> <span m='553120'>of--</span> <span
  m='553680'>how</span> <span m='553910'>did</span> <span m='554110'>I</span>
  <span m='554330'>label</span> <span m='554730'>this--</span> <span
  m='555670'>that the</span> <span m='555950'>coin</span> <span
  m='556260'>was</span> <span m='556440'>of</span> <span m='556540'>type</span>
  <span m='556890'>A?</span> <span m='561240'>Where</span> <span
  m='561460'>all</span> <span m='561640'>you know is</span> <span
  m='562290'>I</span> <span m='562420'>pulled</span> <span m='562780'>it</span>
  <span m='562870'>out</span> <span m='563040'>of</span> <span
  m='563130'>the</span> <span m='563240'>drawer.</span> <span
  m='564045'>So</span> <span m='564350'>what's</span> <span
  m='564720'>the</span> <span m='564800'>probability</span> <span
  m='565430'>it's</span> <span m='565590'>of</span> <span m='565690'>type</span>
  <span m='566160'>A.</span> </p><p><span m='566933'>PROFESSOR 2: Let me</span>
  <span m='567396'>go back</span> <span m='567859'>and remind you what
  the</span> <span m='568785'>drawer</span> <span m='569248'>looks like.</span>
  <span m='571570'>What is</span> <span m='572200'>it?</span> </p><p><span
  m='573850'>PROFESSOR: 0.5.</span> <span m='575040'>0.5,</span> <span
  m='575650'>or</span> <span m='575750'>I'll</span> <span
  m='575890'>write</span> <span m='576070'>it</span> <span
  m='576150'>like</span> <span m='576340'>this.</span> <span m='576590'>2</span>
  <span m='576820'>out</span> <span m='576950'>of</span> <span
  m='577040'>4,</span> <span m='578120'>which</span> <span m='578350'>is</span>
  <span m='578470'>0.5.</span> <span m='579390'>And</span> <span
  m='579590'>what's</span> <span m='579820'>the</span> <span
  m='579900'>probability--</span> <span m='581070'>I'll</span> <span
  m='581240'>shorten</span> <span m='581640'>this--</span> <span
  m='582010'>for</span> <span m='582160'>just</span> <span
  m='582530'>type</span> <span m='584170'>B.</span> <span
  m='587316'>Yeah,</span> <span m='587760'>1/4</span> <span m='588410'>or</span>
  <span m='588700'>0.25.</span> <span m='592180'>The</span> <span
  m='592270'>probability</span> <span m='592730'>that</span> <span
  m='592840'>we're</span> <span m='592970'>of</span> <span
  m='593060'>type</span> <span m='594910'>C</span> <span m='595790'>is</span>
  <span m='596530'>1/4</span> <span m='597800'>or</span> <span
  m='597970'>0.25.</span> <span m='598940'>This</span> <span
  m='599020'>was</span> <span m='599850'>one</span> <span m='600130'>of</span>
  <span m='600220'>our</span> <span m='600310'>simpler</span> <span
  m='600800'>counting</span> <span m='601250'>problems.</span> <span
  m='604130'>In</span> <span m='604300'>the</span> <span
  m='604410'>table,</span> <span m='604760'>you</span> <span
  m='604870'>can</span> <span m='605000'>see</span> <span
  m='605170'>that's</span> <span m='605430'>encoded</span> <span
  m='606380'>in</span> <span m='606560'>the</span> <span m='606650'>line</span>
  <span m='607540'>in</span> <span m='607670'>the</span> <span
  m='607770'>column</span> <span m='608220'>marked</span> <span
  m='608510'>prior.</span> <span m='609860'>Before</span> <span
  m='610140'>we</span> <span m='610270'>take</span> <span m='610560'>any</span>
  <span m='610780'>data,</span> <span m='612110'>this</span> <span
  m='612310'>is</span> <span m='612440'>what</span> <span m='612610'>we'd</span>
  <span m='612760'>say.</span> <span m='613150'>This</span> <span
  m='613400'>is</span> <span m='613610'>the</span> <span m='613900'>sort</span>
  <span m='614160'>of</span> <span m='614260'>odds</span> <span
  m='614690'>we'd</span> <span m='616110'>give if we were</span> <span
  m='616260'>going</span> <span m='616370'>to</span> <span m='616430'>bet</span>
  <span m='616700'>on</span> <span m='616850'>this.</span> </p><p><span
  m='618440'>But</span> <span m='618640'>now</span> <span m='618830'>we</span>
  <span m='618940'>have</span> <span m='619110'>some</span> <span
  m='619310'>data.</span> <span m='622790'>So</span> <span
  m='622860'>once</span> <span m='623040'>we</span> <span m='623150'>have</span>
  <span m='623340'>data</span> <span m='624090'>we</span> <span
  m='624230'>can</span> <span m='624340'>get</span> <span m='627600'>the</span>
  <span m='627710'>likelihood.</span> <span m='632470'>The</span> <span
  m='632580'>likelihood</span> <span m='633120'>is</span> <span
  m='633330'>the</span> <span m='633420'>probability</span> <span
  m='634540'>of</span> <span m='634700'>seeing</span> <span
  m='635220'>the</span> <span m='635340'>data</span> <span
  m='636250'>given</span> <span m='636900'>a</span> <span
  m='637180'>hypothesis.</span> <span m='640200'>I won't</span> <span
  m='640470'>write</span> <span m='640670'>this</span> <span
  m='640870'>out,</span> <span m='641030'>I'll</span> <span
  m='641140'>just</span> <span m='641380'>point</span> <span
  m='641690'>at</span> <span m='641900'>the</span> <span
  m='642980'>slide.</span> <span m='643590'>John</span> <span
  m='643890'>has</span> <span m='644110'>a--</span> <span m='644830'>you
  were</span> <span m='645080'>going</span> <span m='645190'>to</span> <span
  m='645230'>make</span> <span m='645410'>your</span> <span
  m='645490'>mouse</span> <span m='645740'>bigger.</span> </p><p><span
  m='646810'>PROFESSOR 2:  I was.</span> </p><p><span m='647540'>PROFESSOR:
  OK.</span> <span m='650790'>So</span> <span m='651560'>the</span> <span
  m='651740'>likelihood</span> <span m='652290'>column,</span> <span
  m='652830'>we</span> <span m='652970'>use</span> <span m='653180'>this</span>
  <span m='653380'>term</span> <span m='653750'>when</span> <span m='653890'>we
  are</span> <span m='654120'>talking</span> <span m='654470'>about</span> <span
  m='654740'>maximum</span> <span m='655250'>likelihood,</span> <span
  m='656210'>is</span> <span m='657590'>the</span> <span
  m='657690'>probability</span> <span m='658310'>of</span> <span
  m='658390'>the</span> <span m='658510'>data</span> <span
  m='659240'>given</span> <span m='659480'>the</span> <span
  m='659540'>hypothesis.</span> <span m='660240'>And</span> <span
  m='660340'>this</span> <span m='660500'>is</span> <span
  m='660640'>typically</span> <span m='661770'>easy,</span> <span
  m='662730'>or</span> <span m='663260'>often</span> <span
  m='663690'>easy,</span> <span m='664470'>to</span> <span
  m='664800'>figure</span> <span m='665180'>out.</span> <span
  m='666010'>What's</span> <span m='666250'>the</span> <span
  m='666320'>probability</span> <span m='666980'>of</span> <span
  m='667070'>seeing</span> <span m='667370'>heads?</span> <span
  m='667800'>Our</span> <span m='667880'>data</span> <span m='668170'>was</span>
  <span m='668820'>I</span> <span m='668960'>flipped</span> <span m='669320'>a
  heads</span> <span m='670410'>if</span> <span m='670590'>my</span> <span
  m='670740'>coin</span> <span m='671120'>is</span> <span m='671300'>a</span>
  <span m='671490'>0.5</span> <span m='672260'>probability</span> <span
  m='672930'>coin.</span> </p><p><span m='677560'>So</span> <span
  m='677660'>the</span> <span m='677760'>probability</span> <span
  m='678790'>of</span> <span m='678940'>seeing</span> <span
  m='679780'>heads</span> <span m='682320'>given</span> <span
  m='682700'>a</span> <span m='682810'>type</span> <span m='683065'>A</span>
  <span m='683320'>coin</span> <span m='685550'>is</span> <span
  m='685770'>what?</span> <span m='686170'>Somebody.</span> <span
  m='688660'>It's</span> <span m='688850'>0.5.</span> <span
  m='690960'>This</span> <span m='691060'>is</span> <span
  m='691190'>particularly</span> <span m='691710'>easy</span> <span
  m='691910'>because</span> <span m='692090'>that's</span> <span
  m='692310'>what</span> <span m='692390'>we</span> <span m='692500'>told</span>
  <span m='692800'>you.</span> <span m='692890'>The</span> <span
  m='692990'>probability</span> <span m='693550'>of</span> <span
  m='693640'>heads</span> <span m='693900'>with</span> <span m='694010'>a</span>
  <span m='694110'>type A</span> <span m='694540'>coin</span> <span
  m='695680'>is</span> <span m='695900'>0.5.</span> <span m='698480'>What</span>
  <span m='698630'>about</span> <span m='698940'>for</span> <span
  m='699060'>B</span> <span m='699350'>and</span> <span m='699490'>C.</span>
  <span m='702270'>0.6</span> <span m='703170'>and</span> <span
  m='703520'>0.9.</span> <span m='707160'>So</span> <span
  m='707370'>there</span> <span m='709660'>right</span> <span
  m='709860'>here</span> <span m='710060'>is</span> <span m='710160'>the</span>
  <span m='710290'>likelihood</span> <span m='711350'>column</span> <span
  m='711720'>in</span> <span m='711780'>the</span> <span
  m='711890'>table.</span> </p><p><span m='712650'>Now,</span> <span
  m='712850'>how</span> <span m='712880'>do</span> <span m='712980'>we</span>
  <span m='713100'>get</span> <span m='714280'>the</span> <span
  m='714470'>posterior?</span> <span m='716350'>Bayes'</span> <span
  m='716730'>Theorem</span> <span m='719260'>says</span> <span
  m='719540'>the</span> <span m='719620'>probability</span> <span
  m='720830'>of</span> <span m='721520'>H</span> <span m='722390'>given</span>
  <span m='722720'>D,</span> <span m='723920'>which</span> <span
  m='724110'>is</span> <span m='724210'>what</span> <span m='724370'>I</span>
  <span m='724630'>want. I</span> <span m='724890'>want</span> <span
  m='725080'>to</span> <span m='725130'>know,</span> <span
  m='725260'>given</span> <span m='725600'>this</span> <span
  m='725810'>data,</span> <span m='726450'>what</span> <span
  m='726630'>do</span> <span m='726710'>I</span> <span m='726800'>believe</span>
  <span m='727240'>the</span> <span m='727340'>coin</span> <span
  m='727630'>to</span> <span m='727740'>be?</span> <span
  m='728670'>What's</span> <span m='728920'>its</span> <span
  m='729110'>probability?</span> <span m='731060'>Is</span> <span
  m='731670'>the</span> <span m='731790'>probability</span> <span
  m='732970'>of</span> <span m='733540'>D</span> <span m='733800'>given</span>
  <span m='734160'>H</span> <span m='735250'>times</span> <span
  m='735610'>the</span> <span m='735680'>probability</span> <span
  m='736430'>of</span> <span m='736520'>H</span> <span m='737610'>all</span>
  <span m='737940'>over</span> <span m='739180'>the</span> <span
  m='739290'>probability</span> <span m='739950'>of</span> <span
  m='740080'>D.</span> </p><p><span m='740840'>Well</span> <span
  m='741010'>notice</span> <span m='741560'>this</span> <span
  m='741850'>numerator</span> <span m='742490'>right</span> <span
  m='742650'>here.</span> <span m='744230'>That's</span> <span
  m='744420'>just</span> <span m='744750'>our</span> <span
  m='745090'>likelihood</span> <span m='746950'>times</span> <span
  m='747430'>our</span> <span m='747550'>hypothesis,</span> <span
  m='748430'>our</span> <span m='748550'>prior</span> <span
  m='748920'>belief</span> <span m='749250'>in our</span> <span
  m='749330'>hypothesis.</span> <span m='752280'>And</span> <span
  m='752390'>so</span> <span m='753810'>what</span> <span m='754120'>do</span>
  <span m='754170'>we</span> <span m='754270'>get</span> <span
  m='754440'>when</span> <span m='754600'>I</span> <span
  m='754650'>multiply</span> <span m='755590'>the</span> <span
  m='755690'>prior</span> <span m='756080'>column</span> <span
  m='756390'>by</span> <span m='756510'>the</span> <span
  m='756610'>likelihood</span> <span m='757100'>column?</span> <span
  m='757860'>I</span> <span m='757960'>get</span> <span m='758060'>this</span>
  <span m='758250'>column</span> <span m='758610'>in</span> <span
  m='758710'>red.</span> <span m='759720'>And</span> <span
  m='759820'>I'll</span> <span m='759930'>call</span> <span
  m='760120'>that</span> <span m='760280'>the unnormalized</span> <span
  m='761260'>posterior.</span> <span m='761910'>Why</span> <span
  m='762190'>unnormalized</span> <span m='762880'>because</span> <span
  m='763190'>it</span> <span m='763340'>doesn't</span> <span
  m='763690'>sum</span> <span m='764010'>to</span> <span m='765480'>1.</span>
  <span m='766320'>How</span> <span m='766470'>do</span> <span
  m='766570'>I</span> <span m='766640'>get</span> <span m='766830'>it</span>
  <span m='766950'>to</span> <span m='767040'>sum</span> <span
  m='767330'>to</span> <span m='767450'>1?</span> <span m='768160'>There</span>
  <span m='768290'>I</span> <span m='768390'>have</span> <span
  m='768560'>to</span> <span m='768670'>divide</span> <span m='770575'>by</span>
  <span m='770980'>the</span> <span m='771050'>probability</span> <span
  m='771650'>of</span> <span m='771750'>the</span> <span m='771850'>data.
  And</span> <span m='772290'>how</span> <span m='772400'>do</span> <span
  m='772480'>I</span> <span m='772550'>get</span> <span m='772720'>the</span>
  <span m='772800'>probability</span> <span m='773420'>of</span> <span
  m='773520'>the</span> <span m='773620'>data?</span> </p><p><span
  m='778190'>That's</span> <span m='778410'>called</span> <span
  m='778710'>the--</span> <span m='782356'>I</span> <span m='782830'>see</span>
  <span m='783160'>someone</span> <span m='783530'>mouthing it.</span> <span
  m='784000'>The</span> <span m='784100'>Law of</span> <span
  m='784440'>Total</span> <span m='784730'>Probability.</span> <span
  m='787920'>And the</span> <span m='788430'>Law of</span> <span
  m='788720'>Total</span> <span m='788970'>Probability</span> <span
  m='789830'>says</span> <span m='790540'>you</span> <span
  m='790640'>multiply</span> <span m='791870'>for</span> <span
  m='792150'>each</span> <span m='792350'>hypothesis</span> <span
  m='794330'>this</span> <span m='794760'>value</span> <span
  m='795160'>times</span> <span m='795440'>this</span> <span
  m='795600'>value</span> <span m='795940'>and</span> <span
  m='796050'>add</span> <span m='796320'>them</span> <span m='796500'>up.</span>
  <span m='799340'>Which</span> <span m='799570'>is</span> <span
  m='799710'>in</span> <span m='799840'>fact</span> <span m='800170'>just</span>
  <span m='800470'>the</span> <span m='800570'>sum</span> <span
  m='803470'>of</span> <span m='803920'>the</span> <span m='804050'>red</span>
  <span m='804310'>column.</span> <span m='805820'>So</span> <span
  m='806010'>there</span> <span m='806200'>I've</span> <span
  m='806340'>written</span> <span m='806560'>it</span> <span
  m='806880'>0.625.</span> </p><p><span m='808340'>And</span> <span
  m='808500'>now</span> <span m='808660'>how</span> <span m='808830'>do</span>
  <span m='808940'>I</span> <span m='809040'>normalize?</span> <span
  m='809750'>I</span> <span m='809810'>just</span> <span
  m='810010'>divide</span> <span m='810430'>by</span> <span
  m='810730'>all</span> <span m='810980'>my</span> <span
  m='811140'>values</span> <span m='811640'>in</span> <span m='811750'>my</span>
  <span m='811950'>unnormalized</span> <span m='812750'>column</span> <span
  m='814160'>by</span> <span m='814320'>that</span> <span
  m='814540'>normalizing</span> <span m='815200'>factor,</span> <span
  m='815660'>0.625,</span> <span m='817430'>and</span> <span m='817630'>I</span>
  <span m='817680'>get</span> <span m='817990'>these,</span> <span
  m='819470'>what</span> <span m='819860'>I</span> <span m='819930'>call</span>
  <span m='820200'>the</span> <span m='820290'>posterior.</span> </p><p><span
  m='824690'>Let's</span> <span m='825020'>say--</span> <span
  m='826230'>well</span> <span m='826390'>now</span> <span
  m='826570'>let's</span> <span m='826790'>analyze</span> <span
  m='827140'>this.</span> <span m='827240'>So</span> <span m='827340'>now</span>
  <span m='827480'>what's</span> <span m='827710'>your</span> <span
  m='827820'>belief?</span> <span m='828200'>Which</span> <span
  m='828470'>coin</span> <span m='829260'>is</span> <span m='829490'>the</span>
  <span m='829590'>most</span> <span m='829860'>likely</span> <span
  m='830230'>coin?</span> <span m='832130'>After</span> <span
  m='832480'>seeing</span> <span m='832770'>this</span> <span
  m='832960'>data.</span> <span m='836760'>Still</span> <span
  m='837130'>A.</span> <span m='838330'>But</span> <span
  m='838470'>what's</span> <span m='838670'>happened</span> <span
  m='838970'>to</span> <span m='839050'>the</span> <span
  m='839160'>probability</span> <span m='839870'>from</span> <span
  m='840090'>our</span> <span m='840220'>prior</span> <span
  m='840590'>probability?</span> <span m='842770'>It's</span> <span
  m='843010'>dropped.</span> <span m='843370'>Which</span> <span
  m='843560'>one</span> <span m='843740'>has</span> <span
  m='843890'>gained</span> <span m='844310'>probability.</span> </p><p><span
  m='846076'>AUDIENCE: C.</span> </p><p><span m='846540'>PROFESSOR: C.</span>
  <span m='846790'>Does</span> <span m='846950'>that</span> <span
  m='847110'>make</span> <span m='847330'>sense?</span> <span
  m='847600'>If</span> <span m='848090'>I</span> <span m='848210'>flip</span>
  <span m='848500'>a</span> <span m='848630'>heads,</span> <span
  m='849720'>which</span> <span m='849980'>coin</span> <span
  m='850290'>is</span> <span m='850430'>the</span> <span m='850550'>most</span>
  <span m='851880'>likely</span> <span m='852310'>to</span> <span
  m='852400'>flip</span> <span m='852700'>heads?</span> <span
  m='854440'>C.</span> <span m='855020'>So</span> <span m='855180'>I've</span>
  <span m='855270'>shifted</span> <span m='855800'>it.</span> <span
  m='855930'>Suppose</span> <span m='856280'>I</span> <span
  m='856370'>flipped</span> <span m='856710'>heads</span> <span
  m='857360'>three</span> <span m='857590'>more</span> <span
  m='857830'>times.</span> <span m='859120'>What</span> <span
  m='859330'>would</span> <span m='859470'>you</span> <span
  m='859550'>see</span> <span m='859730'>in</span> <span m='859860'>the</span>
  <span m='860450'>probability</span> <span m='861160'>as</span> <span
  m='861280'>I</span> <span m='861350'>kept</span> <span
  m='861650'>updating?</span> </p><p><span m='870369'>PROFESSOR 2: Say it
  again.</span> </p><p><span m='870846'>AUDIENCE: The probability of C gets
  bigger.</span> </p><p><span m='872290'>PROFESSOR 2: The</span> <span
  m='872510'>probability</span> <span m='873030'>of</span> <span
  m='873120'>C</span> <span m='873340'>would</span> <span m='873480'>get</span>
  <span m='873690'>bigger</span> <span m='875000'>at</span> <span
  m='875180'>the</span> <span m='875260'>expense</span> <span
  m='875770'>of</span> <span m='875900'>the</span> <span
  m='876000'>probabilities</span> <span m='876800'>of</span> <span
  m='876900'>the</span> <span m='877060'>others.</span> <span m='877830'>If
  I</span> <span m='877950'>flipped</span> <span m='878260'>heads</span> <span
  m='878650'>9</span> <span m='879000'>times</span> <span m='879330'>in</span>
  <span m='879430'>a</span> <span m='879480'>row,</span> <span m='879740'>I'd 
  be</span> <span m='880030'>very</span> <span m='880320'>convinced</span> <span
  m='882100'>that</span> <span m='882260'>I</span> <span m='882360'>had</span>
  <span m='883960'>a</span> <span m='884100'>type</span> <span
  m='884690'>C</span> <span m='885020'>coin.</span> <span m='886120'>One</span>
  <span m='886320'>last</span> <span m='886640'>thing</span> <span
  m='886850'>to</span> <span m='886980'>note</span> <span
  m='887190'>about</span> <span m='887450'>this</span> <span
  m='887660'>table.</span> <span m='889240'>I</span> <span m='889350'>put</span>
  <span m='889620'>totals</span> <span m='890050'>down</span> <span
  m='890300'>here.</span> <span m='890920'>What</span> <span
  m='891090'>does</span> <span m='891210'>this</span> <span
  m='891370'>total</span> <span m='891700'>of</span> <span m='891800'>1</span>
  <span m='892070'>represent</span> <span m='892690'>in</span> <span
  m='892790'>the</span> <span m='892870'>first</span> <span
  m='893190'>column?</span> <span m='896460'>Emily.</span> </p><p><span
  m='896690'>AUDIENCE:</span> <span m='896830'>The total</span> <span
  m='897190'>probabilities</span> <span m='897550'>of</span> <span
  m='898888'>anything,</span> <span m='899334'>so the total space.</span>
  </p><p><span m='901120'>PROFESSOR: Yeah.</span> <span m='902800'>When</span>
  <span m='903030'>I</span> <span m='903100'>sum</span> <span
  m='903440'>up</span> <span m='903620'>the</span> <span m='903710'>total</span>
  <span m='904020'>probabilities,</span> <span m='904760'>they</span> <span
  m='904870'>sum</span> <span m='905150'>up</span> <span m='905280'>to</span>
  <span m='905400'>1.</span> <span m='907200'>Same</span> <span
  m='907600'>with</span> <span m='907780'>this</span> <span
  m='907980'>last.</span> <span m='908440'>That's</span> <span
  m='908700'>a</span> <span m='908750'>probability.</span> <span
  m='910030'>This</span> <span m='910310'>I</span> <span m='910400'>could</span>
  <span m='910590'>sum,</span> <span m='910990'>because</span> <span
  m='911320'>they</span> <span m='911420'>were</span> <span
  m='911570'>probabilities.</span> <span m='912390'>Why</span> <span
  m='912630'>didn't</span> <span m='912920'>I</span> <span m='913010'>sum</span>
  <span m='913980'>this</span> <span m='914280'>column?</span> <span
  m='920980'>Those</span> <span m='921380'>are</span> <span
  m='921460'>the</span> <span m='921590'>likelihoods,</span> <span
  m='922330'>and</span> <span m='922400'>what's</span> <span
  m='922670'>changing</span> <span m='923240'>as</span> <span
  m='923400'>I</span> <span m='923460'>move</span> <span m='923720'>down</span>
  <span m='923990'>this</span> <span m='924200'>column?</span> <span
  m='926010'>What's</span> <span m='926200'>changing</span> <span
  m='926680'>is</span> <span m='926860'>H.</span> <span m='928150'>That's</span>
  <span m='928380'>not</span> <span m='928610'>a</span> <span
  m='928670'>probability</span> <span m='929420'>function.</span> <span
  m='930570'>It</span> <span m='930620'>doesn't</span> <span
  m='930990'>sum</span> <span m='931220'>to</span> <span m='931380'>1.</span>
  <span m='932970'>There's</span> <span m='933160'>no</span> <span
  m='933340'>reason</span> <span m='934230'>that</span> <span
  m='935960'>the</span> <span m='936120'>likelihoods</span> <span
  m='936760'>have</span> <span m='936960'>to</span> <span m='937080'>sum</span>
  <span m='937270'>to</span> <span m='937380'>1,</span> <span
  m='937540'>and</span> <span m='937580'>here</span> <span m='937760'>you</span>
  <span m='937850'>can</span> <span m='938000'>see</span> <span
  m='938180'>they</span> <span m='938580'>clearly</span> <span
  m='939000'>don't</span> <span m='939340'>sum</span> <span m='939620'>to</span>
  <span m='939740'>1.</span> </p><p><span m='942200'>So</span> <span
  m='942360'>I</span> <span m='942450'>don't</span> <span m='942780'>sum</span>
  <span m='943060'>that.</span> <span m='943330'>That's</span> <span
  m='944100'>an</span> <span m='945510'>important,</span> <span
  m='946840'>maybe</span> <span m='947150'>slightly</span> <span
  m='947600'>subtle</span> <span m='948030'>point,</span> <span m='948390'>that
  the</span> <span m='949130'>likelihood</span> <span m='950040'>function</span>
  <span m='950970'>is</span> <span m='951130'>not</span> <span
  m='951320'>a</span> <span m='951360'>probability</span> <span
  m='952070'>function.</span> <span m='954110'>OK,</span> <span
  m='954290'>any</span> <span m='954480'>questions</span> <span
  m='955010'>here?</span> </p><p><span m='958644'>PROFESSOR 2: All right.</span>
  <span m='960500'>So,</span> <span m='961200'>let's</span> <span
  m='961380'>go</span> <span m='961490'>back</span> <span m='962440'>to</span>
  <span m='962620'>this</span> <span m='963490'>document</span> <span
  m='963980'>camera.</span> <span m='966760'>I</span> <span
  m='967160'>got</span> <span m='967290'>my</span> <span
  m='967380'>trusty</span> <span m='967770'>platonic</span> <span
  m='968240'>solids.</span> <span m='974680'>So,</span> <span
  m='976810'>we're</span> <span m='976930'>going</span> <span
  m='977020'>to</span> <span m='977060'>go</span> <span
  m='977210'>through</span> <span m='977360'>a</span> <span
  m='977420'>series</span> <span m='977900'>of</span> <span
  m='978060'>board</span> <span m='978190'>questions</span> <span
  m='978620'>now,</span> <span m='978810'>three</span> <span
  m='979040'>board</span> <span m='979270'>questions</span> <span
  m='980370'>which</span> <span m='981560'>are</span> <span
  m='981690'>going</span> <span m='981780'>to</span> <span m='981840'>allow
  you</span> <span m='982010'>to</span> <span m='982100'>practice</span> <span
  m='982640'>making</span> <span m='982910'>these</span> <span
  m='983070'>tables</span> <span m='984180'>and</span> <span
  m='984340'>getting</span> <span m='984510'>a</span> <span
  m='984560'>sense</span> <span m='985040'>for</span> <span
  m='985150'>how</span> <span m='985240'>to</span> <span m='985320'>do</span>
  <span m='985410'>Bayesian</span> <span m='985700'>Updating,</span> <span
  m='986040'>how to</span> <span m='986380'>iterate</span> <span
  m='986880'>it,</span> <span m='987890'>just</span> <span m='988070'>how</span>
  <span m='988200'>it</span> <span m='988240'>works.</span> </p><p><span
  m='989470'>And</span> <span m='990180'>our</span> <span m='990350'>toy</span>
  <span m='990560'>problem</span> <span m='991070'>is</span> <span
  m='991190'>going</span> <span m='991390'>to</span> <span m='991450'>be</span>
  <span m='992140'>involving</span> <span m='993280'>these</span> <span
  m='993600'>5</span> <span m='993780'>platonic</span> <span
  m='994200'>dice.</span> <span m='994800'>You</span> <span
  m='994930'>all</span> <span m='995090'>have</span> <span
  m='995320'>them,</span> <span m='995590'>but</span> <span
  m='995820'>let's</span> <span m='996470'>not</span> <span
  m='996730'>break</span> <span m='996910'>them</span> <span
  m='997050'>out</span> <span m='997220'>today,</span> <span
  m='997590'>because</span> <span m='997860'>it would</span> <span
  m='997900'>be</span> <span m='998010'>very</span> <span
  m='998190'>noisy</span> <span m='998560'>with</span> <span
  m='998640'>the</span> <span m='998720'>cameras</span> <span
  m='999070'>I</span> <span m='999120'>think.</span> <span
  m='999900'>We'll</span> <span m='1000150'>use</span> <span
  m='1002080'>our</span> <span m='1002390'>4-sided--</span> <span
  m='1003990'>here,</span> <span m='1004200'>I</span> <span
  m='1004250'>got</span> <span m='1004410'>big</span> <span
  m='1004530'>ones.</span> <span m='1006440'>We've</span> <span m='1006540'>got
  our</span> <span m='1006690'>4-sided,</span> <span m='1007880'>8-sided,</span>
  <span m='1008670'>6-sided.</span> <span m='1009690'>No</span> <span
  m='1009930'>6-sided.</span> <span m='1010880'>No,</span> <span
  m='1011340'>I</span> <span m='1011540'>don't</span> <span
  m='1011680'>have</span> <span m='1011810'>a 6-sided.</span> <span
  m='1013546'>I</span> <span m='1013980'>have</span> <span
  m='1014090'>the</span> <span m='1014170'>wrong</span> <span
  m='1014370'>dice.</span> <span m='1014910'>Hold</span> <span
  m='1015100'>on.</span> <span m='1015800'>We</span> <span
  m='1015910'>got</span> <span m='1016090'>20,</span> <span
  m='1016790'>we</span> <span m='1016910'>got</span> <span m='1017100'>4,</span>
  <span m='1018230'>we</span> <span m='1018320'>got</span> <span
  m='1018600'>12,</span> <span m='1020200'>we got</span> <span
  m='1020370'>8,</span> <span m='1020900'>ah--</span> <span
  m='1021940'>10,</span> <span m='1022290'>what</span> <span
  m='1022410'>are</span> <span m='1022430'>you</span> <span
  m='1022540'>doing</span> <span m='1022790'>there?</span> <span
  m='1023950'>That's</span> <span m='1024210'>not</span> <span
  m='1024349'>platonic.</span> </p><p><span m='1029800'>OK,</span> <span
  m='1032230'>and</span> <span m='1032400'>6.</span> <span m='1035670'>So</span>
  <span m='1035829'>now</span> <span m='1036030'>I'm</span> <span
  m='1036190'>actually</span> <span m='1036560'>going</span> <span
  m='1036670'>to</span> <span m='1036730'>take</span> <span
  m='1036950'>these.</span> <span m='1037760'>You</span> <span
  m='1037880'>can</span> <span m='1037980'>watch</span> <span
  m='1038250'>this.</span> <span m='1038609'>All right,</span> <span
  m='1038829'>this</span> <span m='1039030'>is</span> <span
  m='1040010'>empty</span> <span m='1040200'>cup.</span> <span
  m='1044079'>OK,</span> <span m='1044349'>they're</span> <span
  m='1044430'>in</span> <span m='1044490'>there right?</span> <span
  m='1045890'>OK.</span> <span m='1048950'>How</span> <span
  m='1049080'>do</span> <span m='1049140'>we</span> <span m='1049240'>do</span>
  <span m='1049360'>this?</span> <span m='1050710'>How</span> <span
  m='1050830'>do</span> <span m='1050900'>we</span> <span
  m='1050970'>convince</span> <span m='1051330'>them?</span> </p><p><span
  m='1051780'>PROFESSOR: Should we choose one at random?</span> </p><p><span
  m='1052810'>PROFESSOR 2: Yeah.</span> <span m='1057330'>All right,</span>
  <span m='1057780'>choose it.</span> <span m='1057860'>Don't</span> <span
  m='1057960'>let</span> <span m='1058130'>anyone</span> <span
  m='1058440'>see.</span> <span m='1060580'>Hand</span> <span
  m='1060810'>it</span> <span m='1060890'>me.</span> <span
  m='1061810'>OK.</span> <span m='1063270'>So</span> <span m='1063700'>I</span>
  <span m='1063790'>have</span> <span m='1063960'>this</span> <span
  m='1064050'>die.</span> <span m='1065100'>Don't</span> <span
  m='1065260'>look</span> <span m='1065400'>at</span> <span
  m='1065460'>the</span> <span m='1065580'>others.</span> <span
  m='1067190'>I'm</span> <span m='1067310'>going</span> <span
  m='1067390'>to</span> <span m='1067430'>start</span> <span
  m='1067630'>rolling</span> <span m='1067940'>it,</span> <span
  m='1068760'>all</span> <span m='1068860'>right?</span> <span
  m='1070300'>In</span> <span m='1070410'>this</span> <span
  m='1070560'>secret</span> <span m='1070880'>bin.</span> <span
  m='1071710'>Jerry,</span> <span m='1071870'>you</span> <span
  m='1071990'>can</span> <span m='1072120'>ver--</span> <span
  m='1072460'>we</span> <span m='1072640'>can have</span> <span
  m='1072760'>a</span> <span m='1072820'>student</span> <span
  m='1073150'>come</span> <span m='1073300'>verify</span> <span
  m='1073700'>that</span> <span m='1073840'>I'm</span> <span
  m='1073910'>not</span> <span m='1074060'>making</span> <span
  m='1074320'>this</span> <span m='1074490'>up.</span> </p><p><span
  m='1076200'>You ready?</span> <span m='1077640'>OK,</span> <span
  m='1077870'>here</span> <span m='1077990'>we</span> <span
  m='1078090'>go.</span> <span m='1079596'>OK,</span> <span
  m='1080030'>what</span> <span m='1080240'>did I</span> <span
  m='1080280'>get?</span> <span m='1081360'>8.</span> <span
  m='1082220'>All</span> <span m='1082300'>right.</span> <span
  m='1083200'>So,</span> <span m='1083940'>which</span> <span
  m='1084180'>die</span> <span m='1084400'>is</span> <span m='1084520'>it</span>
  <span m='1084740'>so</span> <span m='1084930'>far?</span> <span
  m='1085430'>What</span> <span m='1085570'>do</span> <span
  m='1085610'>you</span> <span m='1085660'>think?</span> <span
  m='1086340'>Could</span> <span m='1086610'>it</span> <span
  m='1086880'>be</span> <span m='1086970'>4,</span> <span m='1087220'>the
  4-sided die?</span> <span m='1088340'>6-sided?</span> <span
  m='1089580'>8?</span> <span m='1090921'>12?</span> <span
  m='1092262'>20?</span> <span m='1093480'>What's</span> <span
  m='1093670'>most</span> <span m='1093850'>likely?</span> <span
  m='1095460'>All</span> <span m='1095550'>right.</span> </p><p><span
  m='1097940'>Come</span> <span m='1098130'>take</span> <span
  m='1098280'>a</span> <span m='1098350'>look</span> <span m='1098540'>at</span>
  <span m='1098590'>another</span> <span m='1098860'>one.</span> <span
  m='1100544'>Ready?</span> <span m='1105802'>Ah,</span> <span
  m='1106290'>got</span> <span m='1106430'>a</span> <span m='1106470'>1.</span>
  </p><p><span m='1108041'>AUDIENCE: It's the same die?</span> </p><p><span
  m='1108430'>PROFESSOR 2: It's</span> <span m='1108880'>the</span> <span
  m='1108990'>same</span> <span m='1109230'>die,</span> <span
  m='1109750'>it's</span> <span m='1109830'>the</span> <span
  m='1109930'>same</span> <span m='1110160'>die.</span> <span
  m='1110910'>All</span> <span m='1110970'>right,</span> <span
  m='1111540'>so</span> <span m='1111700'>now</span> <span
  m='1111870'>what?</span> <span m='1113061'>How</span> <span
  m='1113460'>does</span> <span m='1113580'>this</span> <span
  m='1113720'>change,</span> <span m='1114370'>anyone</span> <span
  m='1115050'>want</span> <span m='1115200'>to</span> <span
  m='1115240'>tell</span> <span m='1115390'>me</span> <span
  m='1115470'>how</span> <span m='1115600'>would</span> <span
  m='1115970'>this</span> <span m='1116240'>now</span> <span
  m='1116500'>change</span> <span m='1117480'>from</span> <span
  m='1117730'>before</span> <span m='1118310'>what</span> <span
  m='1118550'>you</span> <span m='1118620'>believe</span> <span
  m='1119190'>to</span> <span m='1119290'>be?</span> <span
  m='1120450'>Does</span> <span m='1120610'>it</span> <span
  m='1120700'>change</span> <span m='1120920'>what</span> <span
  m='1121030'>you</span> <span m='1121120'>believe</span> <span
  m='1121610'>at</span> <span m='1121730'>all,</span> <span
  m='1122390'>in</span> <span m='1122520'>any</span> <span
  m='1122680'>way?</span> </p><p><span m='1123060'>You</span> <span
  m='1123170'>still</span> <span m='1123350'>think</span> <span
  m='1123510'>it's</span> <span m='1123620'>the</span> <span
  m='1123760'>8-sided.</span> <span m='1124930'>Does</span> <span
  m='1125090'>it</span> <span m='1125420'>make</span> <span
  m='1125620'>the</span> <span m='1125840'>8-sided</span> <span m='1126680'>less
  like,</span> <span m='1126960'>more</span> <span m='1127410'>likely</span>
  <span m='1128020'>relative</span> <span m='1128350'>to</span> <span
  m='1128440'>the</span> <span m='1128560'>others?</span> <span
  m='1129880'>More</span> <span m='1130170'>likely.</span> <span
  m='1130700'>Wonderful.</span> <span m='1131190'>See</span> <span
  m='1131340'>you</span> <span m='1131520'>guys</span> <span
  m='1131760'>all</span> <span m='1131850'>sense</span> <span
  m='1132140'>this</span> <span m='1132300'>in</span> <span
  m='1132430'>your</span> <span m='1132540'>bones.</span> <span
  m='1133090'>It's</span> <span m='1133260'>great.</span> <span m='1133690'>This
  is going to be</span> <span m='1133810'>so</span> <span
  m='1134000'>easy.</span> <span m='1134340'>For</span> <span
  m='1134460'>all</span> <span m='1134590'>of</span> <span
  m='1134690'>you.</span> <span m='1135340'>All</span> <span
  m='1135430'>right.</span> <span m='1136870'>We've</span> <span
  m='1136950'>got</span> <span m='1137130'>to</span> <span
  m='1137210'>keep</span> <span m='1137580'>going until</span> <span
  m='1137720'>we</span> <span m='1137970'>figure</span> <span
  m='1138140'>out</span> <span m='1138360'>with this die.</span> </p><p><span
  m='1140310'>You,</span> <span m='1140700'>you love to</span> <span
  m='1141040'>participate.</span> <span m='1141630'>Come</span> <span
  m='1141840'>on.</span> <span m='1145376'>Ready?</span> </p><p><span
  m='1147760'>AUDIENCE: 3.</span> </p><p><span m='1148240'>PROFESSOR 2:
  3,</span> <span m='1149160'>oh</span> <span m='1149280'>man.</span> <span
  m='1149670'>All</span> <span m='1149740'>right.</span> <span
  m='1152860'>Ready?</span> </p><p><span m='1154805'>AUDIENCE: 12.</span>
  </p><p><span m='1156110'>PROFESSOR 2: Ooh.</span> <span m='1161780'>Now</span>
  <span m='1161980'>what</span> <span m='1162120'>happened?</span> <span
  m='1164190'>It's</span> <span m='1164310'>a 12-sided</span> <span
  m='1164870'>die?</span> <span m='1165060'>But</span> <span
  m='1165260'>it</span> <span m='1165350'>could</span> <span m='1165510'>be
  a</span> <span m='1165640'>20-sided</span> <span m='1166170'>die,</span> <span
  m='1166370'>right?</span> <span m='1167270'>All</span> <span
  m='1167340'>right,</span> <span m='1167500'>let</span> <span
  m='1167580'>me</span> <span m='1167660'>just</span> <span m='1167860'>do
  a</span> <span m='1167940'>few</span> <span m='1168090'>more,</span> <span
  m='1168240'>I'll</span> <span m='1168320'>tell</span> <span
  m='1168440'>you</span> <span m='1168540'>it</span> <span m='1168600'>I</span>
  <span m='1168640'>get.</span> <span m='1169170'>I</span> <span
  m='1169260'>get</span> <span m='1169420'>1,</span> <span m='1170660'>I</span>
  <span m='1170770'>get</span> <span m='1171920'>10,</span> <span
  m='1172990'>I</span> <span m='1173120'>get</span> <span m='1173600'>10,</span>
  <span m='1174680'>I</span> <span m='1174800'>get</span> <span
  m='1175120'>12,</span> <span m='1176330'>I</span> <span m='1176420'>get</span>
  <span m='1177680'>3,</span> <span m='1178680'>I</span> <span
  m='1178760'>get</span> <span m='1179010'>10.</span> <span
  m='1179580'>All</span> <span m='1179890'>right.</span> <span
  m='1181060'>Who</span> <span m='1181140'>wants</span> <span
  m='1181340'>to</span> <span m='1181420'>bet?</span> <span
  m='1183660'>What</span> <span m='1183800'>would</span> <span
  m='1183920'>you</span> <span m='1183980'>be</span> <span
  m='1184040'>willing</span> <span m='1184300'>to</span> <span
  m='1184370'>bet?</span> </p><p><span m='1185380'>Suppose</span> <span
  m='1185790'>I</span> <span m='1185910'>was</span> <span
  m='1186130'>willing</span> <span m='1186370'>to</span> <span
  m='1186560'>give</span> <span m='1186780'>you</span> <span
  m='1186910'>like,</span> <span m='1187680'>I</span> <span m='1187790'>don't
  know,</span> <span m='1187930'>10</span> <span m='1188370'>to</span> <span
  m='1188450'>1</span> <span m='1188620'>odds</span> <span
  m='1189500'>that</span> <span m='1189640'>it's</span> <span
  m='1189790'>a</span> <span m='1189840'>20-sided</span> <span
  m='1190430'>die.</span> <span m='1195080'>I</span> <span
  m='1195130'>mean,</span> <span m='1195290'>of</span> <span
  m='1195360'>course,</span> <span m='1196070'>maybe</span> <span
  m='1196550'>I</span> <span m='1196620'>know</span> <span
  m='1196790'>something.</span> <span m='1197640'>I</span> <span
  m='1197760'>can</span> <span m='1197930'>see</span> <span
  m='1198050'>the</span> <span m='1198180'>die.</span> <span
  m='1199990'>Right,</span> <span m='1200360'>so</span> <span
  m='1200700'>what</span> <span m='1200940'>we</span> <span
  m='1200980'>want</span> <span m='1201140'>to</span> <span
  m='1201180'>be</span> <span m='1201290'>able</span> <span
  m='1201420'>to</span> <span m='1201490'>do</span> <span m='1201990'>is</span>
  <span m='1202150'>precisely</span> <span m='1202760'>answer</span> <span
  m='1203510'>that</span> <span m='1203720'>question.</span> <span
  m='1204920'>All right, and</span> <span m='1205290'>it's</span> <span
  m='1205510'>just</span> <span m='1205770'>through this</span> <span
  m='1205950'>Bayesian</span> <span m='1206260'>Updating.</span> <span
  m='1206570'>It's</span> <span m='1206720'>not</span> <span
  m='1206890'>so</span> <span m='1207020'>hard,</span> <span
  m='1207530'>but</span> <span m='1207690'>organizing</span> <span
  m='1208230'>your</span> <span m='1208300'>work</span> <span
  m='1208490'>is</span> <span m='1208570'>really</span> <span
  m='1208760'>important.</span> </p><p><span m='1209800'>So,</span> <span
  m='1210590'>all</span> <span m='1210680'>right.</span> <span
  m='1211000'>It</span> <span m='1211080'>was</span> <span
  m='1211270'>the</span> <span m='1211330'>12-sided</span> <span
  m='1212430'>after</span> <span m='1212820'>all.</span> <span m='1213190'>So
  you all</span> <span m='1213560'>did</span> <span m='1213690'>good.</span>
  <span m='1215180'>All</span> <span m='1215260'>right,</span> <span
  m='1215470'>so</span> <span m='1215590'>this</span> <span
  m='1215760'>is</span> <span m='1215840'>the</span> <span
  m='1215910'>first</span> <span m='1216170'>board</span> <span
  m='1216340'>question.</span> <span m='1218290'>All</span> <span
  m='1218360'>right.</span> <span m='1218640'>I</span> <span
  m='1218740'>want</span> <span m='1218940'>to</span> <span
  m='1219230'>practice</span> <span m='1219480'>making</span> <span
  m='1219830'>the</span> <span m='1219920'>table</span> <span
  m='1220230'>Jerry</span> <span m='1220400'>showed</span> <span
  m='1220700'>you.</span> <span m='1221700'>Make</span> <span
  m='1221930'>one</span> <span m='1222120'>for if</span> <span
  m='1222340'>it</span> <span m='1222470'>were</span> <span
  m='1222570'>13.</span> <span m='1223640'>Make</span> <span
  m='1223870'>one</span> <span m='1224010'>if</span> <span m='1225070'>I
  had</span> <span m='1225370'>rolled</span> <span m='1225440'>5</span> <span
  m='1225740'>instead.</span> <span m='1226240'>Or</span> <span
  m='1226550'>do</span> <span m='1226740'>the</span> <span
  m='1226820'>same</span> <span m='1227050'>question</span> <span
  m='1227400'>if</span> <span m='1227510'>I</span> <span m='1227600'>had
  rolled</span> <span m='1227760'>a</span> <span m='1227880'>9.</span> <span
  m='1228430'>In</span> <span m='1228570'>each</span> <span
  m='1228780'>case,</span> <span m='1229120'>compute</span> <span
  m='1229790'>the</span> <span m='1229870'>posterior</span> <span
  m='1230340'>probabilities</span> <span m='1231710'>of each of the</span> <span
  m='1231780'>5</span> <span m='1232180'>types</span> <span
  m='1232530'>of</span> <span m='1232620'>dice.</span> </p><p></p><p><span
  m='1247220'>PROFESSOR: You</span> <span m='1247480'>knew</span> <span
  m='1247770'>it was</span> <span m='1247880'>a</span> <span
  m='1247960'>20-sided</span> <span m='1248235'>die?</span> </p><p><span
  m='1248960'>AUDIENCE: Yeah.</span> </p><p><span m='1249410'>PROFESSOR: All
  right,</span> <span m='1249710'>what</span> <span m='1249900'>about</span>
  <span m='1250230'>if</span> <span m='1250330'>it's</span> <span
  m='1250480'>a</span> <span m='1250530'>5?</span> </p><p><span
  m='1251230'>AUDIENCE: Yeah.</span> </p><p><span m='1252950'>PROFESSOR:
  But</span> <span m='1253140'>that's</span> <span m='1253360'>it.</span> <span
  m='1253460'>But</span> <span m='1253580'>you</span> <span m='1253660'>see
  how</span> <span m='1253960'>that</span> <span m='1254130'>captures</span>
  <span m='1254620'>it</span> <span m='1254710'>very</span> <span
  m='1254950'>nicely</span> <span m='1255380'>in</span> <span
  m='1255480'>a</span> <span m='1255570'>table.</span> <span
  m='1257580'>All</span> <span m='1257820'>of</span> <span
  m='1257920'>your</span> <span m='1258040'>intuition.</span> <span
  m='1258540'>You</span> <span m='1258620'>knew</span> <span
  m='1258800'>it</span> <span m='1258840'>was a--</span> </p><p></p><p><span
  m='1286780'>PROFESSOR 2: So</span> <span m='1286970'>right</span> <span
  m='1287150'>now</span> <span m='1287260'>you're</span> <span
  m='1287390'>doing</span> <span m='1287630'>the</span> <span
  m='1287710'>D</span> <span m='1287985'>equals</span> <span
  m='1288260'>13</span> <span m='1288620'>case?</span> </p><p><span
  m='1289310'>AUDIENCE: Yeah,</span> <span m='1290258'>or I guess</span> <span
  m='1290732'>we could combine the tables.</span> </p><p><span
  m='1294050'>PROFESSOR 2: Oh,</span> <span m='1294390'>I'm sorry.</span> <span
  m='1294520'>You're</span> <span m='1294660'>not</span> <span
  m='1294790'>combining</span> <span m='1295130'>tables.</span> <span
  m='1295400'>This is</span> <span m='1295560'>your</span> <span
  m='1295700'>likelihood</span> <span m='1296010'>column</span> <span
  m='1296300'>here?</span> </p><p><span m='1296590'>AUDIENCE: Yeah.</span>
  </p><p><span m='1296930'>PROFESSOR 2: And</span> <span m='1297020'>then</span>
  <span m='1297140'>this</span> <span m='1297310'>is</span> <span
  m='1297410'>your</span> <span m='1297820'>unnormalized</span> <span
  m='1298070'>posterior</span> <span m='1298770'>column.</span> <span
  m='1299550'>Is</span> <span m='1299940'>that</span> <span
  m='1300000'>right?</span> <span m='1300590'>Or,</span> <span m='1301000'>no
  this</span> <span m='1301340'>is</span> <span m='1301450'>actually</span>
  <span m='1301690'>normalized.</span> </p><p><span m='1302640'>AUDIENCE: This
  is for</span> <span m='1303310'>if</span> <span m='1303550'>it</span> <span
  m='1303640'>were</span> <span m='1303850'>like</span> <span
  m='1304080'>any</span> <span m='1304360'>number.</span> <span
  m='1304800'>Like</span> <span m='1304870'>if we didn't</span> <span
  m='1305170'>know</span> <span m='1305270'>what number</span> <span
  m='1305380'>it was.</span> </p><p><span m='1308590'>PROFESSOR 2: The</span>
  <span m='1309120'>likelihood?</span> </p><p><span m='1309600'>AUDIENCE:
  Yes.</span> </p><p><span m='1310050'>PROFESSOR 2: Absolutely.</span> <span
  m='1310530'>So</span> <span m='1310660'>the</span> <span
  m='1310750'>likelihood</span> <span m='1311120'>doesn't</span> <span
  m='1311350'>depend</span> <span m='1311690'>on--</span> <span
  m='1313600'>wait.</span> <span m='1315130'>What</span> <span
  m='1315320'>are</span> <span m='1315360'>we</span> <span
  m='1315450'>doing?</span> <span m='1315680'>Rolling</span> <span
  m='1315850'>a</span> <span m='1315940'>5 or a</span> <span
  m='1316320'>13?</span> </p><p><span m='1316900'>AUDIENCE: Rolling a 13,
  right?</span> </p><p><span m='1318840'>PROFESSOR 2: Right,</span> <span
  m='1319110'>so</span> <span m='1319290'>rolling</span> <span
  m='1319510'>a</span> <span m='1319580'>13,</span> <span m='1319935'>for</span>
  <span m='1320290'>the</span> <span m='1320620'>likelihood</span> <span
  m='1321090'>you're</span> <span m='1321180'>computing</span> <span
  m='1321500'>the</span> <span m='1321570'>probability</span> <span
  m='1322070'>of</span> <span m='1322170'>data</span> <span
  m='1322820'>that</span> <span m='1322940'>you</span> <span
  m='1323020'>saw,</span> <span m='1323510'>the</span> <span
  m='1323600'>13,</span> <span m='1324750'>given</span> <span
  m='1325610'>the</span> <span m='1326530'>hypothesis</span> <span
  m='1327460'>say</span> <span m='1327630'>that</span> <span
  m='1327770'>it's</span> <span m='1327930'>the</span> <span
  m='1328010'>4-sided</span> <span m='1328450'>die.</span> </p><p><span
  m='1328710'>AUDIENCE: Right.</span> </p><p><span m='1329010'>PROFESSOR 2:
  It's</span> <span m='1329290'>the</span> <span m='1329340'>4-sided</span>
  <span m='1329770'>die,</span> <span m='1330130'>what's</span> <span
  m='1330380'>the</span> <span m='1330450'>probability</span> <span
  m='1331170'>you</span> <span m='1331270'>would</span> <span
  m='1331370'>roll</span> <span m='1332230'>a</span> <span
  m='1332350'>13?</span> </p><p><span m='1332480'>AUDIENCE: 0.</span>
  </p><p><span m='1333750'>PROFESSOR 2: Great. Same</span> <span
  m='1333960'>with</span> <span m='1334080'>this,</span> <span m='1334450'>this
  and</span> <span m='1334530'>this.</span> <span m='1334790'>But</span> <span
  m='1334890'>what</span> <span m='1334900'>about</span> <span
  m='1335080'>here?</span> <span m='1335850'>If</span> <span
  m='1335960'>it's</span> <span m='1336110'>the</span> <span
  m='1336160'>20-sided</span> <span m='1336740'>die,</span> <span
  m='1337295'>if</span> <span m='1337560'>that's</span> <span
  m='1337770'>your</span> <span m='1338100'>hypothesis,</span> <span
  m='1338440'>what's</span> <span m='1338600'>the</span> <span
  m='1338680'>probability</span> <span m='1339150'>you'd roll a</span> <span
  m='1339380'>13.</span> </p><p><span m='1339860'>AUDIENCE: Oh no.</span> <span
  m='1340840'>Oh</span> <span m='1341330'>1/20.</span> </p><p><span
  m='1341820'>PROFESSOR 2: Exactly.</span> <span m='1342800'>So</span> <span
  m='1342970'>that's</span> <span m='1343380'>the</span> <span
  m='1343620'>likelihood</span> <span m='1344090'>column.</span> <span
  m='1345130'>So</span> <span m='1345300'>this</span> <span m='1345650'>we're
  going to erase.</span> <span m='1346992'>OK.</span> </p><p><span
  m='1348840'>AUDIENCE 2: Then we multiply</span> <span m='1349302'>this by
  this</span> <span m='1351150'>and get that.</span> </p><p><span
  m='1351620'>PROFESSOR 2: Exactly.</span> </p><p><span m='1352440'>AUDIENCE:
  [INAUDIBLE]</span> <span m='1353352'>divide</span> <span m='1353808'>by</span>
  <span m='1354264'>[INAUDIBLE].</span> </p><p><span m='1357000'>PROFESSOR 2:
  Exactly,</span> <span m='1357455'>exactly.</span> <span
  m='1358420'>Does</span> <span m='1358990'>that</span> <span
  m='1359030'>make</span> <span m='1359200'>sense?</span> </p><p><span
  m='1359950'>AUDIENCE: Wait,</span> <span m='1360320'>we</span> <span
  m='1360690'>multiply</span> <span m='1361080'>these</span> <span
  m='1361335'>together--</span> </p><p><span m='1361590'>AUDIENCE 2: Multiply
  those three</span> <span m='1361790'>together.</span> <span
  m='1374088'>And</span> <span m='1374585'>then</span> <span m='1375082'>we
  divide</span> <span m='1375579'>1 over</span> <span m='1376076'>100,</span>
  <span m='1376573'>so it's going</span> <span m='1377070'>to be 0--</span>
  </p><p><span m='1383550'>PROFESSOR 2: So,</span> <span m='1384160'>yeah</span>
  <span m='1384390'>so</span> <span m='1384530'>you</span> <span
  m='1384620'>get</span> <span m='1384770'>to</span> <span
  m='1384870'>just--</span> </p><p><span m='1386740'>AUDIENCE: And then
  HD.</span> </p><p><span m='1388090'>PROFESSOR 2: No, no. Oh yeah, you're
  right.</span> <span m='1389610'>HD.</span> <span m='1392630'>One</span> <span
  m='1392870'>thing</span> <span m='1393010'>I</span> <span
  m='1393040'>want</span> <span m='1393190'>to</span> <span
  m='1393240'>point</span> <span m='1393460'>out</span> <span
  m='1394200'>is</span> <span m='1396070'>instead</span> <span
  m='1396400'>of</span> <span m='1396490'>using</span> <span
  m='1396720'>a</span> <span m='1396790'>comma,</span> <span
  m='1397350'>all</span> <span m='1397750'>right,</span> <span
  m='1398290'>this</span> <span m='1398440'>is</span> <span
  m='1398530'>conditional</span> <span m='1398980'>probability</span> <span
  m='1399810'>so</span> <span m='1399990'>it's</span> <span
  m='1400270'>probability</span> <span m='1400620'>of</span> <span
  m='1401430'>D</span> <span m='1401520'>given</span> <span
  m='1401680'>H,</span> <span m='1402730'>like</span> <span
  m='1402920'>this.</span> <span m='1404070'>OK.</span> <span m='1404660'>There
  you</span> <span m='1404870'>go.</span> <span m='1406590'>So</span> <span
  m='1406740'>that's</span> <span m='1406900'>absolutely</span> <span
  m='1407170'>right.</span> <span m='1407580'>At</span> <span
  m='1407730'>the</span> <span m='1407830'>end,</span> <span m='1408570'>we want
  to know</span> <span m='1408810'>how</span> <span m='1409030'>likely</span>
  <span m='1409330'>each</span> <span m='1409630'>die</span> <span
  m='1409850'>was</span> <span m='1410280'>given</span> <span
  m='1410500'>the</span> <span m='1410580'>data.</span> </p><p><span
  m='1411000'>AUDIENCE: Because this total is just P.</span> </p><p><span
  m='1413490'>PROFESSOR 2: That's</span> <span m='1414070'>right.</span> <span
  m='1417790'>Which</span> <span m='1418070'>is</span> <span
  m='1418170'>1</span> <span m='1418330'>over</span> <span
  m='1418450'>100.</span> <span m='1427700'>Great.</span> <span
  m='1428200'>So</span> <span m='1428360'>now,</span> <span
  m='1429090'>do</span> <span m='1429200'>it</span> <span
  m='1429250'>again.</span> <span m='1429650'>Yeah,</span> <span
  m='1429820'>exactly.</span> <span m='1430170'>You</span> <span
  m='1430220'>don't</span> <span m='1430340'>even</span> <span m='1430630'>need
  to</span> <span m='1430910'>make a new</span> <span m='1430930'>table.</span>
  </p><p></p><p><span m='1442450'>PROFESSOR 2: Awesome</span> </p><p><span
  m='1444692'>AUDIENCE: So</span> <span m='1445170'>this</span> <span
  m='1445648'>column</span> <span m='1446126'>[INAUDIBLE]</span> <span
  m='1446604'>to the</span> <span m='1447082'>probability,</span> <span
  m='1447560'>because</span> <span m='1448038'>[INAUDIBLE].</span> </p><p><span
  m='1451980'>PROFESSOR 2: Yeah,</span> <span m='1453330'>you</span> <span
  m='1453440'>take</span> <span m='1453640'>each</span> <span
  m='1453780'>hypothesis</span> <span m='1454470'>times</span> <span
  m='1454790'>probability</span> <span m='1455090'>of</span> <span
  m='1455250'>data</span> <span m='1455430'>given</span> <span
  m='1455490'>that</span> <span m='1455610'>process,</span> <span
  m='1456120'>which</span> <span m='1456150'>is</span> <span
  m='1456240'>the</span> <span m='1456320'>same</span> <span
  m='1456630'>as</span> <span m='1457260'>the</span> <span
  m='1457410'>probability</span> <span m='1458020'>of</span> <span
  m='1458710'>D</span> <span m='1459260'>and</span> <span m='1459630'>H.</span>
  </p><p><span m='1460720'>AUDIENCE: Yeah, exactly.</span> </p><p><span
  m='1461210'>PROFESSOR 2: So</span> <span m='1461370'>your</span> <span
  m='1461500'>partitioning</span> <span m='1462050'>it</span> <span
  m='1462130'>up,</span> <span m='1462410'>sort</span> <span
  m='1462610'>of</span> <span m='1463170'>based</span> <span
  m='1463440'>on</span> <span m='1463530'>hypotheses.</span> </p><p><span
  m='1463690'>AUDIENCE: Because</span> <span m='1463820'>this</span> <span
  m='1463920'>equals</span> <span m='1464968'>that</span> <span
  m='1465406'>times</span> <span m='1465844'>probability</span> <span
  m='1466282'>of D.</span> </p><p><span m='1468040'>PROFESSOR 2: That's</span>
  <span m='1468220'>right.</span> </p><p><span m='1468585'>AUDIENCE: D confuses
  me.</span> <span m='1469724'>What is P of D?</span> </p><p><span
  m='1470500'>PROFESSOR 2: Probability</span> <span m='1471170'>of</span> <span
  m='1471220'>the</span> <span m='1471320'>data.</span> <span
  m='1471730'>So,</span> <span m='1473510'>right</span> <span
  m='1473770'>so</span> <span m='1474010'>a priori,</span> <span
  m='1474160'>you</span> <span m='1474660'>don't</span> <span
  m='1474930'>know</span> <span m='1475040'>which</span> <span
  m='1475770'>die</span> <span m='1476030'>it is,</span> <span
  m='1476190'>right?</span> <span m='1477020'>But</span> <span
  m='1477150'>there's</span> <span m='1477290'>still a</span> <span
  m='1477520'>probability</span> <span m='1479860'>of</span> <span
  m='1479970'>getting</span> <span m='1480180'>a</span> <span
  m='1480230'>13.</span> <span m='1480810'>Right?</span> <span
  m='1481420'>And</span> <span m='1482140'>what</span> <span
  m='1482320'>is</span> <span m='1482420'>the</span> <span
  m='1482530'>probability?</span> <span m='1483140'>Well</span> <span
  m='1483210'>first,</span> <span m='1484130'>we</span> <span
  m='1484280'>would</span> <span m='1484400'>have</span> <span
  m='1484650'>to,</span> <span m='1485650'>in</span> <span
  m='1485760'>this</span> <span m='1485920'>case,</span> <span
  m='1486140'>we</span> <span m='1486220'>could</span> <span
  m='1486320'>only</span> <span m='1486570'>pick</span> <span
  m='1486790'>the</span> <span m='1486870'>20-sided</span> <span
  m='1487350'>die,</span> <span m='1487685'>that has</span> <span
  m='1488020'>a</span> <span m='1488130'>1/5</span> <span
  m='1488440'>chance</span> <span m='1488610'>of</span> <span
  m='1488810'>happening.</span> <span m='1489470'>And</span> <span
  m='1489630'>then,</span> <span m='1490200'>given</span> <span
  m='1490400'>that</span> <span m='1490500'>we</span> <span
  m='1490590'>picked</span> <span m='1490770'>the</span> <span
  m='1490850'>20-sided</span> <span m='1491320'>die,</span> <span
  m='1491970'>we</span> <span m='1492100'>have</span> <span
  m='1492280'>to</span> <span m='1492390'>roll</span> <span m='1492850'>a</span>
  <span m='1493620'>13,</span> <span m='1494140'>which</span> <span
  m='1494330'>is a 1/20</span> <span m='1494670'>chance.</span> <span
  m='1495010'>Which</span> <span m='1495160'>is</span> <span
  m='1495240'>exactly</span> <span m='1495690'>why</span> <span
  m='1496970'>this</span> <span m='1497550'>sums</span> <span
  m='1497950'>to</span> <span m='1498040'>100.</span> <span
  m='1499780'>And</span> <span m='1499910'>then</span> <span
  m='1500010'>more</span> <span m='1500140'>generally,</span> <span
  m='1500730'>you</span> <span m='1500820'>have</span> <span
  m='1501110'>the</span> <span m='1501160'>Law</span> <span m='1501390'>of
  Total</span> <span m='1501530'>Probability.</span> </p><p><span
  m='1509310'>So</span> <span m='1509890'>here,</span> <span
  m='1513190'>I</span> <span m='1513300'>think</span> <span
  m='1513600'>you</span> <span m='1513680'>should</span> <span
  m='1514060'>keep</span> <span m='1514270'>in</span> <span
  m='1514380'>mind,</span> <span m='1515180'>which</span> <span
  m='1515360'>is</span> <span m='1515560'>the</span> <span m='1515670'>D
  and</span> <span m='1516080'>which</span> <span m='1516270'>is</span> <span
  m='1516360'>H.</span> <span m='1516460'>Maybe</span> <span
  m='1516960'>write</span> <span m='1517100'>it</span> <span
  m='1517170'>above,</span> <span m='1518230'>otherwise</span> <span
  m='1519020'>it's</span> <span m='1519230'>a</span> <span
  m='1519290'>little</span> <span m='1519470'>confusing</span> <span
  m='1520000'>to</span> <span m='1520110'>know</span> <span
  m='1520270'>what--</span> <span m='1522640'>great.</span> <span
  m='1524050'>OK,</span> <span m='1524350'>and</span> <span
  m='1524460'>so</span> <span m='1525500'>these</span> <span m='1525560'>are
  the</span> <span m='1525910'>final</span> <span
  m='1526130'>probabilities</span> <span m='1526610'>you</span> <span
  m='1526690'>got</span> <span m='1527010'>if</span> <span
  m='1527160'>you</span> <span m='1527290'>rolled</span> <span
  m='1527720'>a</span> <span m='1527810'>9.</span> <span m='1529138'>Is that
  right?</span> <span m='1530620'>So</span> <span m='1530780'>there's</span>
  <span m='1531510'>something</span> <span m='1531830'>off</span> <span
  m='1532020'>here</span> <span m='1532110'>right?</span> </p><p><span
  m='1532775'>AUDIENCE: Sorry, these are our priors.</span> <span
  m='1536464'>I'm</span> <span m='1536963'>not labeling</span> <span
  m='1537462'>this.</span> <span m='1538959'>These are priors.</span> <span
  m='1539458'>This is</span> <span m='1539957'>gonna be</span> <span
  m='1540456'>[INAUDIBLE].</span> </p><p><span m='1545460'>PROFESSOR 2:
  So</span> <span m='1545610'>actually</span> <span m='1545950'>here,</span>
  <span m='1546200'>I</span> <span m='1546280'>think</span> <span
  m='1546520'>you have</span> <span m='1546600'>likelihood.</span> <span
  m='1547590'>This</span> <span m='1547800'>is</span> <span
  m='1547950'>likelihood</span> <span m='1548480'>here,</span> <span
  m='1548760'>exactly.</span> <span m='1550230'>That's</span> <span
  m='1550540'>likelihood.</span> <span m='1552390'>Your</span> <span
  m='1552520'>prior</span> <span m='1553000'>should</span> <span
  m='1553220'>be</span> <span m='1554280'>what?</span> </p><p><span
  m='1554710'>AUDIENCE: 0.2.</span> </p><p><span m='1556860'>PROFESSOR 2: What
  should it be?</span> </p><p><span m='1557240'>AUDIENCE: 0.2 for each
  one.</span> </p><p><span m='1558030'>PROFESSOR 2: Yeah,</span> <span
  m='1558240'>1/5.</span> <span m='1558410'>Oh,</span> <span m='1558750'>I
  didn't</span> <span m='1559140'>see the</span> <span
  m='1559220'>points.</span> <span m='1559540'>Yeah,</span> <span
  m='1560030'>so</span> <span m='1560180'>that's</span> <span
  m='1560370'>your</span> <span m='1560470'>prior,</span> <span m='1561220'>1/5
  for each.</span> <span m='1562260'>This</span> <span m='1562430'>is</span>
  <span m='1562510'>your</span> <span m='1562610'>likelihood.</span> <span
  m='1563620'>Then</span> <span m='1563770'>you</span> <span
  m='1563860'>multiply</span> <span m='1564370'>them,</span> <span
  m='1565120'>and</span> <span m='1565230'>that's</span> <span m='1565410'>the
  unnormalized</span> <span m='1566110'>posterior,</span> <span
  m='1566330'>right?</span> </p><p><span m='1569480'>Let's</span> <span
  m='1569670'>have</span> <span m='1569840'>a</span> <span
  m='1570010'>brief</span> <span m='1570190'>discussion</span> <span
  m='1570640'>about</span> <span m='1570900'>it,</span> <span
  m='1571050'>and</span> <span m='1571120'>then</span> <span
  m='1571190'>we're</span> <span m='1571270'>going</span> <span
  m='1571350'>to</span> <span m='1571390'>give</span> <span
  m='1571550'>you</span> <span m='1571630'>something</span> <span
  m='1571980'>a</span> <span m='1572040'>little</span> <span
  m='1572200'>more</span> <span m='1572350'>challenging.</span> </p><p><span
  m='1575910'>So</span> <span m='1576630'>for</span> <span
  m='1576750'>rolling</span> <span m='1577010'>a</span> <span
  m='1577310'>13,</span> <span m='1578400'>right,</span> <span
  m='1579020'>the</span> <span m='1579120'>first</span> <span
  m='1579380'>thing</span> <span m='1579510'>you</span> <span
  m='1579600'>do</span> <span m='1580050'>is</span> <span
  m='1580330'>ask,</span> <span m='1580680'>what</span> <span
  m='1580870'>is</span> <span m='1581030'>the</span> <span
  m='1581110'>prior?</span> <span m='1582510'>And</span> <span
  m='1582720'>you</span> <span m='1582980'>saw, I</span> <span
  m='1583140'>had</span> <span m='1583330'>5</span> <span
  m='1583660'>dice.</span> <span m='1583980'>I</span> <span
  m='1584030'>shook</span> <span m='1584320'>it</span> <span
  m='1584380'>around.</span> <span m='1585370'>A</span> <span
  m='1585460'>student</span> <span m='1585880'>reached</span> <span
  m='1586150'>in</span> <span m='1586280'>randomly,</span> <span
  m='1586670'>not</span> <span m='1586850'>even</span> <span
  m='1587040'>me.</span> <span m='1587840'>So</span> <span m='1588040'>we</span>
  <span m='1588130'>can</span> <span m='1588260'>trust</span> <span
  m='1588870'>that</span> <span m='1589000'>it</span> <span
  m='1589060'>was</span> <span m='1589325'>1/5</span> <span
  m='1591220'>each</span> <span m='1591480'>die.</span> <span
  m='1591800'>Equally</span> <span m='1592140'>likely,</span> <span
  m='1592570'>that's a</span> <span m='1592740'>uniform</span> <span
  m='1593580'>prior,</span> <span m='1594050'>right,</span> <span
  m='1594590'>discrete</span> <span m='1595330'>probability</span> <span
  m='1595800'>mass</span> <span m='1596060'>function.</span> <span
  m='1597920'>Great.</span> </p><p><span m='1599200'>Likelihood.</span> <span
  m='1600140'>Well,</span> <span m='1600570'>that's</span> <span
  m='1600860'>going</span> <span m='1600960'>to</span> <span
  m='1601020'>depend</span> <span m='1601480'>on</span> <span
  m='1601660'>data,</span> <span m='1602430'>because</span> <span
  m='1602610'>it's</span> <span m='1602740'>the</span> <span
  m='1602820'>probability</span> <span m='1603370'>of</span> <span
  m='1603430'>the</span> <span m='1603530'>data</span> <span
  m='1604040'>given</span> <span m='1604700'>the</span> <span
  m='1604790'>hypotheses.</span> <span m='1605740'>The</span> <span
  m='1605820'>hypothesis</span> <span m='1606310'>in</span> <span
  m='1606360'>this</span> <span m='1606530'>case</span> <span
  m='1606810'>is</span> <span m='1607330'>how</span> <span
  m='1607480'>many</span> <span m='1607640'>sides</span> <span
  m='1607920'>on</span> <span m='1608000'>the</span> <span
  m='1608040'>die.</span> <span m='1609310'>So,</span> <span
  m='1610020'>if</span> <span m='1610150'>the</span> <span
  m='1610230'>data's</span> <span m='1610510'>13,</span> <span
  m='1611560'>what's</span> <span m='1611770'>the</span> <span
  m='1611860'>probability</span> <span m='1613200'>that</span> <span
  m='1613360'>I</span> <span m='1613430'>would</span> <span
  m='1613930'>roll</span> <span m='1614420'>that</span> <span
  m='1614650'>data,</span> <span m='1614935'>a</span> <span
  m='1615220'>13,</span> <span m='1615970'>given</span> <span
  m='1617090'>that</span> <span m='1617220'>it</span> <span
  m='1617280'>was</span> <span m='1617430'>the</span> <span
  m='1617490'>4-sided</span> <span m='1617950'>die.</span> <span
  m='1619300'>0.</span> <span m='1619970'>Right,</span> <span
  m='1620390'>it's</span> <span m='1620550'>impossible.</span> <span
  m='1621150'>Similarly</span> <span m='1621730'>4,</span> <span
  m='1621930'>6,</span> <span m='1622690'>8</span> <span m='1622920'>and</span>
  <span m='1623020'>12</span> <span m='1623250'>sides.</span> <span
  m='1624780'>But</span> <span m='1625530'>given</span> <span
  m='1625890'>that</span> <span m='1626030'>I</span> <span
  m='1626110'>had</span> <span m='1626310'>the</span> <span
  m='1626410'>20-sided</span> <span m='1627140'>die,</span> <span
  m='1627440'>there would</span> <span m='1627650'>be</span> <span
  m='1627770'>a</span> <span m='1627830'>1/20</span> <span
  m='1628420'>probability</span> <span m='1629190'>of</span> <span
  m='1629290'>rolling</span> <span m='1629690'>a</span> <span
  m='1629760'>13.</span> <span m='1630850'>That's</span> <span
  m='1630980'>the</span> <span m='1631070'>likelihood</span> <span
  m='1631450'>column.</span> <span m='1632306'>All right.</span> </p><p><span
  m='1633280'>The</span> <span m='1633380'>next</span> <span
  m='1633640'>column,</span> <span m='1634270'>what</span> <span
  m='1634380'>we</span> <span m='1634470'>called</span> <span
  m='1634610'>the</span> <span m='1634730'>unnormalized</span> <span
  m='1635370'>posterior,</span> <span m='1635980'>we</span> <span
  m='1636140'>multiply,</span> <span m='1636980'>everything</span> <span
  m='1637350'>is</span> <span m='1637440'>0,</span> <span m='1637780'>and</span>
  <span m='1637870'>then</span> <span m='1637940'>we</span> <span
  m='1638040'>get</span> <span m='1638190'>1</span> <span m='1638370'>out
  of</span> <span m='1638550'>100</span> <span m='1639840'>as</span> <span
  m='1640070'>the</span> <span m='1640140'>product</span> <span
  m='1641170'>for</span> <span m='1643310'>the</span> <span
  m='1643470'>20-sided</span> <span m='1643990'>die.</span> <span
  m='1645140'>If</span> <span m='1645280'>we</span> <span m='1645380'>sum</span>
  <span m='1645740'>this</span> <span m='1645960'>up</span> <span
  m='1647800'>by</span> <span m='1647940'>the</span> <span
  m='1648010'>Law</span> <span m='1648440'>of Total</span> <span
  m='1648540'>Probability,</span> <span m='1649100'>we</span> <span
  m='1649200'>get</span> <span m='1649850'>the</span> <span
  m='1649960'>probability</span> <span m='1650640'>of</span> <span
  m='1650720'>the</span> <span m='1650810'>data.</span> <span
  m='1651650'>Now,</span> <span m='1651710'>a</span> <span m='1651910'>student
  asked,</span> <span m='1652185'>what</span> <span m='1652460'>does</span>
  <span m='1652550'>that</span> <span m='1652690'>mean?</span> <span
  m='1652950'>We</span> <span m='1653030'>don't</span> <span
  m='1653160'>know</span> <span m='1653240'>which</span> <span m='1653440'>die
  it</span> <span m='1653600'>was?</span> </p><p><span m='1654770'>In</span>
  <span m='1654910'>this</span> <span m='1655070'>case,</span> <span
  m='1655440'>what</span> <span m='1655640'>it</span> <span
  m='1655710'>means</span> <span m='1656310'>is</span> <span
  m='1656890'>that</span> <span m='1657350'>it's</span> <span
  m='1657850'>reasonable</span> <span m='1658660'>to</span> <span
  m='1658760'>ask</span> <span m='1658990'>the</span> <span
  m='1659090'>question,</span> <span m='1661040'>well,</span> <span
  m='1661700'>if</span> <span m='1661820'>someone</span> <span
  m='1662070'>reaches</span> <span m='1662410'>in,</span> <span
  m='1662630'>grabs</span> <span m='1662870'>1</span> <span
  m='1662990'>of</span> <span m='1663030'>these</span> <span
  m='1663200'>5</span> <span m='1663640'>dice</span> <span
  m='1664210'>randomly</span> <span m='1664990'>and</span> <span
  m='1665140'>rolls</span> <span m='1665410'>it</span> <span
  m='1665780'>and</span> <span m='1665930'>gets--</span> <span
  m='1666770'>I</span> <span m='1666840'>mean,</span> <span
  m='1667260'>what's</span> <span m='1667440'>the</span> <span
  m='1667510'>probability</span> <span m='1668070'>that</span> <span
  m='1668210'>the</span> <span m='1668290'>result</span> <span
  m='1668920'>would</span> <span m='1669050'>be</span> <span
  m='1669330'>a</span> <span m='1669370'>13.</span> <span
  m='1670440'>Right?</span> <span m='1670980'>That's</span> <span
  m='1671200'>a</span> <span m='1671230'>reasonable</span> <span
  m='1671580'>question.</span> <span m='1673270'>And</span> <span
  m='1674420'>in</span> <span m='1674530'>this</span> <span
  m='1674690'>case,</span> <span m='1674910'>it's</span> <span
  m='1675030'>not</span> <span m='1675170'>so</span> <span
  m='1675250'>hard</span> <span m='1675420'>to</span> <span
  m='1675480'>analyze</span> <span m='1675860'>that</span> <span
  m='1676030'>directly,</span> <span m='1676790'>because</span> <span
  m='1677340'>the</span> <span m='1677470'>only</span> <span
  m='1677840'>way</span> <span m='1678100'>that</span> <span
  m='1678230'>could</span> <span m='1678330'>happen</span> <span
  m='1678870'>is</span> <span m='1679010'>if</span> <span
  m='1679110'>they</span> <span m='1679220'>think</span> <span
  m='1679400'>the</span> <span m='1679450'>20-sided</span> <span
  m='1679970'>die</span> <span m='1680530'>and</span> <span
  m='1680720'>then</span> <span m='1680940'>rolled</span> <span
  m='1681140'>a</span> <span m='1681210'>13.</span> <span
  m='1682780'>Well,</span> <span m='1683690'>given</span> <span
  m='1683990'>that</span> <span m='1684130'>they</span> <span
  m='1684510'>picked</span> <span m='1684640'>the</span> <span
  m='1684720'>20-sided</span> <span m='1685220'>die.</span> </p><p><span
  m='1686370'>Well, there's</span> <span m='1686540'>a</span> <span
  m='1686590'>1/5</span> <span m='1686960'>chance</span> <span
  m='1687270'>they</span> <span m='1687380'>picked</span> <span
  m='1687510'>the</span> <span m='1687590'>20-sided</span> <span
  m='1688110'>die,</span> <span m='1689440'>and</span> <span
  m='1689560'>then</span> <span m='1689660'>a</span> <span
  m='1689710'>1/20</span> <span m='1690880'>chance</span> <span
  m='1691320'>they</span> <span m='1691490'>roll</span> <span
  m='1691830'>of</span> <span m='1691920'>13</span> <span
  m='1692380'>given</span> <span m='1692780'>that</span> <span
  m='1692920'>they</span> <span m='1693010'>picked</span> <span
  m='1693180'>the</span> <span m='1693240'>20-sided</span> <span
  m='1693750'>die.</span> <span m='1695080'>So</span> <span
  m='1695290'>the</span> <span m='1696600'>probability</span> <span
  m='1697340'>of</span> <span m='1697460'>rolling</span> <span
  m='1697730'>a</span> <span m='1697780'>13</span> <span
  m='1698850'>overall</span> <span m='1699730'>is 1 in</span> <span
  m='1700090'>100.</span> <span m='1700880'>The</span> <span
  m='1700980'>probability</span> <span m='1701640'>of</span> <span
  m='1701990'>the</span> <span m='1702090'>data.</span> </p><p><span
  m='1703590'>PROFESSOR: John,</span> <span m='1704150'>let</span> <span
  m='1704230'>me</span> <span m='1704340'>just</span> <span
  m='1704580'>say</span> <span m='1704720'>one</span> <span
  m='1704890'>thing.</span> <span m='1705160'>The</span> <span
  m='1705230'>way</span> <span m='1705400'>we</span> <span
  m='1705520'>would</span> <span m='1705630'>have</span> <span
  m='1705720'>done</span> <span m='1705900'>this</span> <span
  m='1706060'>before</span> <span m='1706450'>is</span> <span
  m='1706540'>you</span> <span m='1706660'>would</span> <span
  m='1706760'>have</span> <span m='1706840'>made</span> <span
  m='1707030'>a</span> <span m='1707110'>tree.</span> <span
  m='1708990'>The</span> <span m='1709540'>top</span> <span
  m='1709860'>branch</span> <span m='1710150'>of</span> <span
  m='1710200'>the</span> <span m='1710290'>tree</span> <span
  m='1710500'>would</span> <span m='1710600'>have</span> <span
  m='1710690'>gone</span> <span m='1710920'>to</span> <span
  m='1711030'>the</span> <span m='1711160'>5</span> <span
  m='1711530'>types</span> <span m='1711830'>of</span> <span
  m='1711930'>die,</span> <span m='1712320'>and</span> <span
  m='1712530'>then</span> <span m='1712710'>each</span> <span
  m='1712970'>of</span> <span m='1713080'>those</span> <span
  m='1713230'>die</span> <span m='1713440'>would</span> <span
  m='1713570'>have</span> <span m='1713660'>gone</span> <span
  m='1713860'>to</span> <span m='1713940'>all</span> <span
  m='1714100'>the</span> <span m='1714190'>possibilities.</span> <span
  m='1715570'>And</span> <span m='1715760'>the</span> <span
  m='1715870'>only</span> <span m='1716180'>branch that</span> <span
  m='1716670'>leads</span> <span m='1717000'>to</span> <span
  m='1717340'>a</span> <span m='1717830'>13</span> <span m='1719340'>is</span>
  <span m='1719540'>down</span> <span m='1719830'>to</span> <span
  m='1719950'>the</span> <span m='1720360'>20-sided</span> <span
  m='1721060'>die</span> <span m='1721480'>and</span> <span
  m='1721650'>then</span> <span m='1721810'>down</span> <span
  m='1722070'>to</span> <span m='1722170'>the</span> <span
  m='1722310'>13.</span> </p><p><span m='1723730'>PROFESSOR 2: Notice</span>
  <span m='1723890'>also</span> <span m='1724150'>that</span> <span
  m='1724300'>this</span> <span m='1724440'>would</span> <span
  m='1724540'>be</span> <span m='1724670'>a</span> <span m='1724720'>very</span>
  <span m='1725220'>big</span> <span m='1725720'>tree,</span> <span
  m='1726840'>right?</span> <span m='1727100'>You</span> <span
  m='1727200'>have</span> <span m='1728030'>5</span> <span
  m='1728310'>branches,</span> <span m='1728810'>and</span> <span
  m='1728930'>then</span> <span m='1729550'>this</span> <span
  m='1729710'>would</span> <span m='1729820'>have</span> <span
  m='1730060'>4</span> <span m='1730570'>and 6, and 8, and 12,</span> <span
  m='1731350'>and</span> <span m='1731430'>20</span> <span
  m='1731660'>coming</span> <span m='1731890'>off</span> <span
  m='1732060'>of</span> <span m='1732140'>it.</span> <span
  m='1733480'>Finally</span> <span m='1733820'>we</span> <span
  m='1733910'>normalize.</span> <span m='1734630'>Using</span> <span
  m='1734870'>Bayes</span> <span m='1735110'>Rule,</span> <span
  m='1735520'>this</span> <span m='1735690'>gives</span> <span
  m='1735870'>us</span> <span m='1735990'>a</span> <span
  m='1736040'>posterior</span> <span m='1736660'>probability</span> <span
  m='1737090'>mass</span> <span m='1737330'>function.</span> <span
  m='1737890'>It's</span> <span m='1739040'>for</span> <span
  m='1739170'>everything</span> <span m='1739550'>but</span> <span
  m='1739710'>the</span> <span m='1739790'>20-sided</span> <span
  m='1740310'>hypothesis.</span> <span m='1741370'>Therefore,</span> <span
  m='1742160'>we</span> <span m='1742310'>get</span> <span
  m='1743420'>100%</span> <span m='1744250'>belief,</span> <span
  m='1744650'>100%</span> <span m='1745170'>probability</span> <span
  m='1746090'>given</span> <span m='1746300'>that</span> <span
  m='1746420'>we</span> <span m='1746450'>rolled</span> <span
  m='1746660'>a</span> <span m='1746700'>13,</span> <span
  m='1748170'>that</span> <span m='1748710'>it</span> <span
  m='1748820'>was</span> <span m='1749000'>a</span> <span
  m='1749060'>20-sided</span> <span m='1749570'>die.</span> </p><p><span
  m='1749930'>Now</span> <span m='1750070'>of</span> <span
  m='1750160'>course</span> <span m='1751220'>you</span> <span
  m='1751350'>all</span> <span m='1751460'>knew</span> <span
  m='1751590'>that</span> <span m='1752380'>immediately.</span> <span
  m='1752870'>If you</span> <span m='1752980'>roll a</span> <span
  m='1753190'>13,</span> <span m='1753680'>it has</span> <span
  m='1753900'>to</span> <span m='1753950'>be</span> <span m='1754050'>the
  20-sided</span> <span m='1754540'>die.</span> <span m='1755140'>So</span>
  <span m='1755300'>let's</span> <span m='1755470'>look</span> <span
  m='1755630'>at</span> <span m='1755690'>a</span> <span m='1755730'>more</span>
  <span m='1755890'>interesting</span> <span m='1756210'>one</span> <span
  m='1756880'>that</span> <span m='1757020'>you</span> <span
  m='1757090'>did,</span> <span m='1757540'>the</span> <span
  m='1757620'>5.</span> <span m='1758050'>So</span> <span
  m='1758180'>what</span> <span m='1758390'>changes?</span> <span
  m='1758950'>That's</span> <span m='1759180'>the</span> <span
  m='1759250'>big</span> <span m='1759410'>question.</span> <span
  m='1761270'>The</span> <span m='1761390'>only</span> <span
  m='1761800'>thing</span> <span m='1762380'>that</span> <span
  m='1762670'>changes</span> <span m='1765400'>is</span> <span
  m='1766440'>the</span> <span m='1766550'>likelihood.</span> <span
  m='1767570'>I</span> <span m='1767640'>mean,</span> <span
  m='1767930'>granted</span> <span m='1768180'>the</span> <span
  m='1768260'>rest</span> <span m='1768510'>changes.</span> <span
  m='1768910'>But</span> <span m='1769250'>everything</span> <span
  m='1769740'>these</span> <span m='1769960'>two</span> <span
  m='1770110'>columns</span> <span m='1770540'>are</span> <span
  m='1770670'>computed</span> <span m='1771170'>from</span> <span
  m='1771400'>the</span> <span m='1771470'>first</span> <span
  m='1771750'>two.</span> <span m='1772250'>The</span> <span
  m='1772360'>prior</span> <span m='1772730'>stays</span> <span
  m='1772960'>the</span> <span m='1773040'>same,</span> <span
  m='1774660'>but</span> <span m='1775040'>the</span> <span
  m='1775140'>likelihood</span> <span m='1775550'>function</span> <span
  m='1776220'>changes</span> <span m='1777080'>because</span> <span
  m='1777350'>we</span> <span m='1777420'>have</span> <span
  m='1777540'>different</span> <span m='1777870'>data.</span> </p><p><span
  m='1778860'>In</span> <span m='1778990'>this</span> <span
  m='1779170'>case,</span> <span m='1779440'>if</span> <span
  m='1779520'>we</span> <span m='1779620'>roll</span> <span m='1779830'>a
  5,</span> <span m='1780470'>we</span> <span m='1780600'>can't</span> <span
  m='1780890'>get</span> <span m='1781040'>that</span> <span
  m='1781210'>on</span> <span m='1781280'>the</span> <span
  m='1781340'>4-sided</span> <span m='1781820'>die.</span> <span m='1782980'>We
  have</span> <span m='1783120'>a</span> <span m='1783170'>1/6</span> <span
  m='1783710'>chance</span> <span m='1784120'>on</span> <span
  m='1784220'>the</span> <span m='1784290'>6-sided,</span> <span
  m='1784810'>1/8</span> <span m='1785180'>on</span> <span
  m='1785250'>the</span> <span m='1785370'>8-sided,</span> <span
  m='1785930'>1/12</span> <span m='1786656'>on the 12-sided</span> <span
  m='1787020'>and</span> <span m='1787460'>1/20</span> <span m='1787900'>on the
  20-sided.</span> <span m='1788970'>Multiply</span> <span
  m='1789550'>those</span> <span m='1789770'>columns,</span> <span
  m='1790560'>get the</span> <span m='1790670'>unnormalize</span> <span
  m='1791220'>probability,</span> <span m='1792270'>or the unnormalized</span>
  <span m='1792810'>posterior.</span> <span m='1794860'>That</span> <span
  m='1795090'>sums</span> <span m='1795690'>to</span> <span
  m='1795790'>the</span> <span m='1795870'>probability</span> <span
  m='1796620'>of</span> <span m='1796740'>getting</span> <span
  m='1796960'>a</span> <span m='1797010'>5.</span> <span m='1798040'>When</span>
  <span m='1798170'>you</span> <span m='1798250'>divide</span> <span
  m='1798620'>by</span> <span m='1798810'>it</span> <span
  m='1799150'>normalizes</span> <span m='1799880'>the</span> <span
  m='1799950'>posterior,</span> <span m='1801160'>and</span> <span
  m='1801550'>what</span> <span m='1801680'>do</span> <span
  m='1801730'>we</span> <span m='1801810'>see?</span> <span
  m='1802990'>Well,</span> <span m='1804710'>of</span> <span
  m='1804830'>course</span> <span m='1805120'>you</span> <span
  m='1805250'>couldn't</span> <span m='1805550'>have</span> <span
  m='1805630'>used</span> <span m='1805840'>the</span> <span
  m='1805920'>4-sided</span> <span m='1806390'>die,</span> <span
  m='1807260'>and</span> <span m='1807420'>of</span> <span
  m='1807540'>the</span> <span m='1807630'>remaining</span> <span
  m='1808660'>the</span> <span m='1808780'>most</span> <span
  m='1809140'>likely,</span> <span m='1810410'>the</span> <span
  m='1810510'>most</span> <span m='1810750'>probable,</span> <span
  m='1811500'>given</span> <span m='1811840'>the</span> <span
  m='1811910'>data,</span> <span m='1812760'>is</span> <span
  m='1813710'>the</span> <span m='1813800'>6-sided</span> <span
  m='1814340'>die.</span> <span m='1815560'>It</span> <span
  m='1815720'>has</span> <span m='1815890'>a</span> <span
  m='1815940'>probability,</span> <span m='1816590'>that</span> <span
  m='1816770'>hypothesis</span> <span m='1817310'>has</span> <span
  m='1817410'>a</span> <span m='1817450'>probability</span> <span
  m='1818020'>of</span> <span m='1818100'>about</span> <span
  m='1818500'>40%,</span> <span m='1820160'>compared</span> <span
  m='1820450'>to</span> <span m='1820500'>the</span> <span
  m='1820600'>20-sided</span> <span m='1821150'>die,</span> <span
  m='1821470'>which</span> <span m='1821660'>is</span> <span
  m='1821750'>only</span> <span m='1822380'>about</span> <span
  m='1822780'>12%.</span> </p><p><span m='1824020'>OK.</span> <span
  m='1825270'>Last</span> <span m='1825530'>one.</span> <span
  m='1827450'>So</span> <span m='1827630'>this</span> <span
  m='1827800'>is</span> <span m='1827850'>the</span> <span
  m='1827930'>same</span> <span m='1828210'>deal.</span> <span
  m='1828620'>Again,</span> <span m='1828940'>the</span> <span
  m='1829030'>likelihood</span> <span m='1829370'>function</span> <span
  m='1830760'>changes.</span> <span m='1831530'>The</span> <span
  m='1831620'>prior's</span> <span m='1831940'>the</span> <span
  m='1832010'>same.</span> <span m='1832890'>We</span> <span
  m='1832990'>go</span> <span m='1833150'>through</span> <span
  m='1833260'>the</span> <span m='1833370'>table.</span> <span
  m='1834230'>The</span> <span m='1834350'>only</span> <span
  m='1834540'>two</span> <span m='1834670'>possibilities</span> <span
  m='1835340'>are</span> <span m='1835380'>the</span> <span
  m='1835450'>12</span> <span m='1835700'>and</span> <span
  m='1835770'>20-sided,</span> <span m='1836450'>and</span> <span
  m='1836540'>the</span> <span m='1836630'>12-sided,</span> <span
  m='1837690'>given</span> <span m='1837890'>that</span> <span
  m='1838010'>you</span> <span m='1838170'>rolled</span> <span
  m='1838230'>a</span> <span m='1838320'>9,</span> <span m='1838850'>is</span>
  <span m='1839000'>about</span> <span m='1839370'>twice</span> <span
  m='1839680'>as</span> <span m='1839800'>likely</span> <span
  m='1840470'>as</span> <span m='1841080'>the</span> <span
  m='1841180'>20-sided,</span> <span m='1842220'>which</span> <span
  m='1842360'>should</span> <span m='1842500'>fit</span> <span
  m='1842700'>with</span> <span m='1842830'>your</span> <span
  m='1842930'>intuition.</span> </p><p><span m='1845680'>OK.</span> <span
  m='1846530'>So</span> <span m='1846710'>next,</span> <span
  m='1847520'>we</span> <span m='1847630'>want</span> <span
  m='1847990'>you</span> <span m='1848220'>to</span> <span
  m='1848860'>not</span> <span m='1849110'>erase,</span> <span
  m='1849620'>but</span> <span m='1849760'>go</span> <span
  m='1849870'>back</span> <span m='1850150'>to</span> <span
  m='1850250'>the</span> <span m='1850320'>boards</span> <span
  m='1850560'>you've</span> <span m='1850690'>already</span> <span
  m='1850890'>made,</span> <span m='1851810'>and</span> <span
  m='1851980'>we're</span> <span m='1852080'>going</span> <span
  m='1852170'>to</span> <span m='1852210'>explore</span> <span
  m='1852630'>a</span> <span m='1852680'>little</span> <span
  m='1852860'>bit</span> <span m='1853050'>the</span> <span
  m='1853150'>idea</span> <span m='1853430'>of</span> <span
  m='1853920'>repeated</span> <span m='1854370'>trials.</span> <span
  m='1855160'>Right?</span> <span m='1855570'>Often</span> <span
  m='1856670'>if</span> <span m='1856800'>you're</span> <span
  m='1856910'>collecting</span> <span m='1857280'>data,</span> <span
  m='1857590'>you</span> <span m='1857760'>don't</span> <span
  m='1857910'>just</span> <span m='1858070'>collect</span> <span
  m='1858540'>one</span> <span m='1858770'>data</span> <span
  m='1858980'>point,</span> <span m='1859520'>you</span> <span
  m='1859660'>collect</span> <span m='1860120'>a</span> <span
  m='1860240'>series</span> <span m='1860860'>of</span> <span
  m='1860970'>data</span> <span m='1861170'>points,</span> <span
  m='1861420'>maybe</span> <span m='1861610'>a</span> <span
  m='1861650'>series</span> <span m='1862020'>of</span> <span
  m='1862130'>patients</span> <span m='1862860'>in</span> <span
  m='1862980'>a</span> <span m='1863030'>clinical</span> <span
  m='1863350'>trial.</span> <span m='1863950'>You have</span> <span
  m='1864090'>data</span> <span m='1864320'>coming</span> <span
  m='1864630'>in,</span> <span m='1865060'>right?</span> <span
  m='1865520'>And</span> <span m='1865650'>you</span> <span
  m='1865730'>can</span> <span m='1865870'>update.</span> <span
  m='1866730'>You</span> <span m='1866840'>can</span> <span
  m='1866970'>update</span> <span m='1867240'>each</span> <span
  m='1867410'>time</span> <span m='1867700'>you</span> <span
  m='1867750'>get</span> <span m='1867890'>more</span> <span
  m='1868030'>data.</span> </p><p><span m='1869110'>And</span> <span
  m='1869230'>when you</span> <span m='1869380'>do</span> <span
  m='1869530'>this,</span> <span m='1870510'>your</span> <span
  m='1870650'>prior</span> <span m='1871300'>becomes</span> <span m='1871590'>a
  posterior</span> <span m='1872780'>on</span> <span m='1872930'>the</span>
  <span m='1872990'>first</span> <span m='1873250'>update,</span> <span
  m='1873690'>and</span> <span m='1873770'>then</span> <span
  m='1873870'>you</span> <span m='1873960'>use</span> <span
  m='1874260'>that</span> <span m='1874410'>posterior</span> <span
  m='1874990'>as</span> <span m='1875320'>the</span> <span
  m='1875410'>prior</span> <span m='1876050'>for</span> <span
  m='1876120'>the</span> <span m='1876220'>next</span> <span
  m='1876490'>update.</span> <span m='1877110'>Your</span> <span
  m='1877220'>beliefs</span> <span m='1878390'>are</span> <span
  m='1878600'>being</span> <span m='1878830'>updated</span> <span
  m='1879310'>as</span> <span m='1879440'>more</span> <span
  m='1879590'>data</span> <span m='1879800'>comes</span> <span
  m='1880070'>in.</span> <span m='1881680'>If</span> <span
  m='1881780'>you</span> <span m='1881870'>think</span> <span
  m='1882050'>about</span> <span m='1882300'>it,</span> <span
  m='1882510'>like</span> <span m='1882770'>when</span> <span
  m='1882880'>you</span> <span m='1882970'>walk</span> <span
  m='1883190'>outside</span> <span m='1883480'>this</span> <span
  m='1883610'>course,</span> <span m='1884390'>if</span> <span
  m='1884550'>you're</span> <span m='1884650'>like</span> <span
  m='1884810'>me</span> <span m='1885100'>you'll</span> <span
  m='1885610'>sort</span> <span m='1885800'>of</span> <span
  m='1886440'>suddenly</span> <span m='1886860'>realize</span> <span
  m='1887160'>you're</span> <span m='1887260'>doing</span> <span
  m='1887510'>this</span> <span m='1887640'>process</span> <span
  m='1887970'>all</span> <span m='1888270'>the</span> <span
  m='1888350'>time</span> <span m='1888610'>in</span> <span
  m='1888660'>your</span> <span m='1888760'>life,</span> <span
  m='1889040'>and</span> <span m='1889150'>you'll</span> <span
  m='1889190'>start</span> <span m='1889370'>approaching</span> <span
  m='1889700'>problems</span> <span m='1890010'>this</span> <span
  m='1890160'>way.</span> <span m='1890500'>And</span> <span
  m='1890550'>if</span> <span m='1890650'>you</span> <span
  m='1890790'>really</span> <span m='1890990'>like</span> <span
  m='1891200'>me,</span> <span m='1891640'>you'll</span> <span
  m='1891760'>change</span> <span m='1892030'>your</span> <span
  m='1892050'>religion</span> <span m='1892430'>on</span> <span
  m='1892550'>Facebook</span> <span m='1893040'>to</span> <span
  m='1893250'>Bayesian.</span> <span m='1894530'>But</span> <span
  m='1895200'>you</span> <span m='1895320'>have</span> <span
  m='1895440'>to</span> <span m='1895520'>be</span> <span
  m='1895590'>that</span> <span m='1895750'>extreme.</span> </p><p><span
  m='1897110'>So</span> <span m='1898380'>great.</span> <span
  m='1899180'>So</span> <span m='1899370'>here</span> <span
  m='1899530'>what</span> <span m='1899710'>we want</span> <span
  m='1899770'>you</span> <span m='1899970'>to</span> <span m='1900040'>do</span>
  <span m='1900550'>is</span> <span m='1901450'>pretend</span> <span
  m='1901810'>that</span> <span m='1902010'>I</span> <span
  m='1902140'>roll</span> <span m='1902340'>the</span> <span
  m='1902420'>die</span> <span m='1902970'>and</span> <span
  m='1903160'>then</span> <span m='1903220'>got</span> <span
  m='1903370'>a</span> <span m='1903400'>5.</span> <span m='1903860'>And</span>
  <span m='1903980'>then</span> <span m='1904090'>I</span> <span
  m='1904160'>rolled</span> <span m='1904400'>the</span> <span
  m='1904490'>same</span> <span m='1904950'>die,</span> <span
  m='1905320'>I</span> <span m='1905390'>didn't</span> <span
  m='1905590'>get</span> <span m='1905680'>a</span> <span
  m='1905730'>different.</span> <span m='1906200'>I just</span> <span
  m='1906360'>rolled the</span> <span m='1906460'>same</span> <span
  m='1906740'>die,</span> <span m='1907180'>just</span> <span
  m='1907330'>like</span> <span m='1907470'>I</span> <span
  m='1907500'>did</span> <span m='1907660'>in</span> <span
  m='1907710'>that</span> <span m='1907840'>demonstration,</span> <span
  m='1908490'>and</span> <span m='1908640'>then</span> <span
  m='1908760'>I</span> <span m='1908810'>got</span> <span m='1908990'>a</span>
  <span m='1909050'>9.</span> <span m='1909950'>OK,</span> <span
  m='1910450'>so</span> <span m='1910610'>now</span> <span m='1910710'>we</span>
  <span m='1910800'>have</span> <span m='1911000'>a</span> <span
  m='1911130'>sequence</span> <span m='1911600'>of</span> <span
  m='1911700'>two</span> <span m='1911850'>pieces</span> <span
  m='1912100'>of</span> <span m='1912190'>data,</span> <span
  m='1912560'>5</span> <span m='1912890'>and</span> <span m='1913010'>9.</span>
  </p><p><span m='1914110'>So</span> <span m='1915290'>I</span> <span
  m='1915390'>want</span> <span m='1915610'>to</span> <span
  m='1915680'>find</span> <span m='1916380'>the</span> <span
  m='1916470'>posterior</span> <span m='1918040'>that--</span> <span
  m='1924110'>update</span> <span m='1924430'>in</span> <span
  m='1924520'>two</span> <span m='1924660'>steps.</span> <span
  m='1926120'>I'm</span> <span m='1926340'>doing</span> <span
  m='1926530'>this</span> <span m='1926680'>one.</span> <span
  m='1927590'>I'm</span> <span m='1927810'>doing</span> <span
  m='1928020'>this</span> <span m='1928200'>one!</span> <span
  m='1928990'>OK,</span> <span m='1929860'>so</span> <span
  m='1929980'>let</span> <span m='1930040'>me</span> <span
  m='1930120'>show</span> <span m='1930260'>you</span> <span
  m='1930350'>how</span> <span m='1930450'>to</span> <span m='1930540'>do</span>
  <span m='1930670'>this,</span> <span m='1932300'>and</span> <span
  m='1932410'>then</span> <span m='1932510'>you'll</span> <span
  m='1932640'>do</span> <span m='1932760'>it.</span> <span
  m='1934090'>OK,</span> <span m='1934420'>so</span> <span
  m='1934570'>first</span> <span m='1934810'>we're</span> <span
  m='1934870'>going</span> <span m='1934970'>to update</span> <span
  m='1935240'>for</span> <span m='1935330'>the</span> <span
  m='1935400'>5.</span> <span m='1935770'>Then</span> <span
  m='1935880'>we're</span> <span m='1936000'>going</span> <span
  m='1936100'>to</span> <span m='1936140'>update</span> <span
  m='1936950'>again</span> <span m='1937370'>for</span> <span
  m='1937480'>the</span> <span m='1937570'>9.</span> <span
  m='1939310'>Magic!</span> </p><p><span m='1941530'>The</span> <span
  m='1941640'>prior,</span> <span m='1942190'>1/5</span> <span
  m='1942620'>for</span> <span m='1942740'>each,</span> <span
  m='1943190'>right?</span> <span m='1944410'>That's</span> <span
  m='1944620'>where</span> <span m='1944690'>we're</span> <span
  m='1944770'>starting</span> <span m='1945110'>from.</span> <span
  m='1946030'>We</span> <span m='1946150'>roll a</span> <span
  m='1946430'>5.</span> <span m='1947400'>That's</span> <span
  m='1947630'>our</span> <span m='1947690'>likelihood.</span> <span
  m='1948890'>Again,</span> <span m='1949210'>you</span> <span
  m='1949270'>get</span> <span m='1949400'>a</span> <span m='1949520'>0</span>
  <span m='1950400'>for</span> <span m='1950490'>the</span> <span
  m='1950560'>4-sided</span> <span m='1951410'>and</span> <span
  m='1951550'>you</span> <span m='1951620'>get</span> <span m='1952350'>1</span>
  <span m='1952560'>over</span> <span m='1952790'>n</span> <span
  m='1953130'>for</span> <span m='1953240'>each</span> <span
  m='1953440'>of</span> <span m='1953510'>the</span> <span
  m='1953650'>other</span> <span m='1954220'>n-sided</span> <span
  m='1955070'>possibilities.</span> <span m='1956050'>We</span> <span
  m='1956240'>multiply.</span> <span m='1957300'>That</span> <span
  m='1957380'>gives</span> <span m='1957540'>us</span> <span m='1957690'>our
  unnormalized</span> <span m='1958360'>posterior</span> <span
  m='1959090'>for</span> <span m='1959180'>the</span> <span
  m='1959270'>first</span> <span m='1959520'>piece</span> <span
  m='1959690'>of</span> <span m='1959780'>data.</span> <span
  m='1960630'>Great.</span> <span m='1961420'>Now</span> <span
  m='1961620'>that</span> <span m='1962530'>is</span> <span
  m='1962730'>going</span> <span m='1962890'>to</span> <span
  m='1962990'>be</span> <span m='1963550'>our</span> <span
  m='1963720'>new</span> <span m='1964700'>prior.</span> </p><p><span
  m='1965620'>Now,</span> <span m='1965970'>you</span> <span
  m='1966080'>may</span> <span m='1966200'>complain,</span> <span
  m='1966740'>wait</span> <span m='1966920'>a</span> <span
  m='1966970'>minute.</span> <span m='1967570'>This</span> <span
  m='1967790'>doesn't</span> <span m='1968040'>add</span> <span
  m='1968160'>to</span> <span m='1968250'>1.</span> <span m='1969170'>But</span>
  <span m='1970680'>it's</span> <span m='1970840'>OK,</span> <span
  m='1971240'>because</span> <span m='1971650'>we're</span> <span
  m='1971750'>going</span> <span m='1971860'>to</span> <span
  m='1971920'>do</span> <span m='1972070'>it</span> <span
  m='1972120'>again.</span> <span m='1973340'>At</span> <span
  m='1973500'>the</span> <span m='1973570'>very</span> <span
  m='1973810'>end</span> <span m='1974030'>we'll</span> <span
  m='1974170'>normalize,</span> <span m='1975350'>and</span> <span
  m='1975490'>we'll</span> <span m='1975590'>get</span> <span
  m='1975680'>the</span> <span m='1975770'>same</span> <span
  m='1976030'>answer</span> <span m='1976430'>as</span> <span
  m='1976540'>if</span> <span m='1976670'>we</span> <span m='1976750'>had</span>
  <span m='1976850'>normalized</span> <span m='1977470'>here</span> <span
  m='1977880'>and</span> <span m='1978010'>then</span> <span
  m='1978150'>normalized</span> <span m='1978730'>again.</span> <span
  m='1979240'>Because</span> <span m='1979590'>we're</span> <span
  m='1979680'>just</span> <span m='1980210'>multiplying</span> <span
  m='1980860'>the</span> <span m='1980980'>whole</span> <span
  m='1981440'>column</span> <span m='1981840'>by</span> <span
  m='1981960'>the</span> <span m='1982050'>same</span> <span
  m='1982390'>scalar,</span> <span m='1982800'>by</span> <span
  m='1982900'>the</span> <span m='1982990'>same</span> <span m='1983230'>real
  number.</span> <span m='1983700'>OK?</span> <span m='1984130'>So</span> <span
  m='1984250'>it</span> <span m='1984360'>saves</span> <span
  m='1984590'>you</span> <span m='1984690'>work</span> <span
  m='1985290'>to</span> <span m='1985400'>not</span> <span
  m='1985600'>bother</span> <span m='1986020'>to</span> <span
  m='1986130'>normalize</span> <span m='1986960'>the</span> <span
  m='1987050'>first</span> <span m='1987290'>time.</span> </p><p><span
  m='1989050'>Great.</span> <span m='1989450'>So</span> <span
  m='1989620'>that's</span> <span m='1989820'>our</span> <span
  m='1989910'>new</span> <span m='1990070'>prior.</span> <span
  m='1991440'>We</span> <span m='1991930'>get</span> <span
  m='1992060'>our</span> <span m='1992130'>next</span> <span
  m='1992340'>piece</span> <span m='1992500'>of</span> <span
  m='1992580'>data,</span> <span m='1992780'>the</span> <span
  m='1992890'>9.</span> <span m='1993740'>We</span> <span
  m='1993830'>have</span> <span m='1993930'>0,</span> <span
  m='1994210'>0,</span> <span m='1994430'>0,</span> <span
  m='1995420'>1/12</span> <span m='1995900'>and</span> <span
  m='1995980'>1/20</span> <span m='1996590'>as</span> <span
  m='1996730'>the</span> <span m='1996820'>likelihood.</span> <span
  m='1998460'>We</span> <span m='1998590'>multiply</span> <span
  m='1999120'>this</span> <span m='2000520'>new</span> <span
  m='2000710'>prior</span> <span m='2001400'>by</span> <span
  m='2001610'>this</span> <span m='2001860'>likelihood,</span> <span
  m='2002450'>get</span> <span m='2002620'>the</span> <span m='2002980'>new
  unnormalized</span> <span m='2004200'>posterior.</span> <span
  m='2005220'>It</span> <span m='2005420'>only</span> <span
  m='2005620'>has</span> <span m='2005980'>two</span> <span
  m='2006360'>possible</span> <span m='2008360'>nonzero</span> <span
  m='2008920'>probabilities</span> <span m='2009530'>in</span> <span
  m='2009630'>it.</span> <span m='2010390'>The sum,</span> <span
  m='2011540'>the</span> <span m='2011630'>total</span> <span
  m='2011880'>probability</span> <span m='2013300'>of</span> <span
  m='2013480'>rolling</span> <span m='2014070'>a</span> <span
  m='2014160'>5</span> <span m='2014450'>and</span> <span m='2014540'>then
  a</span> <span m='2014730'>9</span> <span m='2015680'>is</span> <span
  m='2016500'>only</span> <span m='2018170'>0.0019,</span> <span
  m='2021280'>OK?</span> </p><p><span m='2024646'>PROFESSOR: That's</span> <span
  m='2025117'>[INAUDIBLE]</span> <span m='2025588'>unnormalized</span> <span
  m='2026059'>[INAUDIBLE].</span> </p><p><span m='2027001'>PROFESSOR 2:
  Ah!</span> <span m='2028890'>Jerry</span> <span m='2029190'>caught</span>
  <span m='2029440'>me.</span> <span m='2029580'>I was</span> <span
  m='2029650'>hoping</span> <span m='2029940'>a</span> <span
  m='2029990'>student</span> <span m='2030230'>would</span> <span
  m='2030340'>catch</span> <span m='2030540'>me.</span> <span
  m='2031730'>OK,</span> <span m='2031960'>maybe</span> <span
  m='2032190'>not.</span> <span m='2032470'>Maybe</span> <span
  m='2032760'>I</span> <span m='2032800'>was</span> <span
  m='2033170'>fooling</span> <span m='2033530'>myself.</span> <span
  m='2034550'>We</span> <span m='2034580'>haven't</span> <span
  m='2034780'>normalized.</span> <span m='2036130'>So,</span> <span
  m='2037180'>it's</span> <span m='2037330'>not</span> <span
  m='2037470'>quite</span> <span m='2037670'>right.</span> <span
  m='2039250'>If</span> <span m='2039370'>we had</span> <span
  m='2039480'>normalized</span> <span m='2039980'>here,</span> <span
  m='2040620'>then</span> <span m='2040830'>by</span> <span
  m='2040940'>the</span> <span m='2041040'>time</span> <span
  m='2041230'>we</span> <span m='2041310'>got to</span> <span
  m='2041500'>here,</span> <span m='2041800'>we</span> <span
  m='2041900'>could</span> <span m='2042030'>interpret</span> <span
  m='2042470'>this</span> <span m='2043020'>as</span> <span
  m='2044230'>that</span> <span m='2044440'>total</span> <span
  m='2044640'>probability.</span> <span m='2045280'>But</span> <span
  m='2045410'>in</span> <span m='2045510'>any</span> <span
  m='2045660'>case,</span> <span m='2046470'>the</span> <span
  m='2046560'>point</span> <span m='2046790'>is</span> <span
  m='2047050'>we</span> <span m='2047180'>can</span> <span
  m='2047300'>normalize</span> <span m='2047890'>to</span> <span
  m='2048010'>get</span> <span m='2048130'>to</span> <span
  m='2048230'>the</span> <span m='2048360'>final</span> <span
  m='2048719'>stage,</span> <span m='2049130'>this</span> <span
  m='2049300'>final</span> <span m='2049580'>posterior,</span> <span
  m='2050750'>by</span> <span m='2050880'>dividing</span> <span
  m='2051290'>by</span> <span m='2051560'>the</span> <span
  m='2051690'>sum</span> <span m='2052050'>here.</span> </p><p><span
  m='2053120'>Now</span> <span m='2053310'>it adds</span> <span
  m='2053540'>to</span> <span m='2053630'>1,</span> <span m='2054739'>and</span>
  <span m='2054870'>at</span> <span m='2054960'>the</span> <span
  m='2055050'>end</span> <span m='2055170'>of</span> <span
  m='2055239'>the</span> <span m='2055300'>day,</span> <span
  m='2055590'>what</span> <span m='2055730'>do</span> <span
  m='2055770'>we</span> <span m='2055870'>conclude?</span> <span
  m='2056360'>We</span> <span m='2056449'>conclude</span> <span
  m='2056790'>that</span> <span m='2056929'>it's</span> <span
  m='2057080'>almost</span> <span m='2057360'>three</span> <span
  m='2057610'>times</span> <span m='2058060'>more</span> <span
  m='2058270'>likely</span> <span m='2060199'>that</span> <span
  m='2060350'>it</span> <span m='2060409'>was</span> <span
  m='2061139'>the</span> <span m='2061250'>12-sided</span> <span
  m='2061870'>die</span> <span m='2062650'>than</span> <span m='2063560'>that
  it</span> <span m='2063770'>was</span> <span m='2064250'>the</span> <span
  m='2064340'>20-sided</span> <span m='2064889'>die.</span> <span
  m='2066125'>Right?</span> </p><p><span m='2066600'>So</span> <span
  m='2066730'>this</span> <span m='2066860'>is</span> <span
  m='2067000'>very</span> <span m='2067260'>similar</span> <span
  m='2067620'>to</span> <span m='2067719'>what</span> <span
  m='2067840'>happened</span> <span m='2068250'>when</span> <span
  m='2069199'>randomly</span> <span m='2069880'>had</span> <span
  m='2070090'>the</span> <span m='2070159'>12-sided</span> <span
  m='2070370'>and</span> <span m='2070760'>rolled</span> <span
  m='2071150'>it.</span> <span m='2071600'>After</span> <span
  m='2071870'>two</span> <span m='2072030'>times,</span> <span
  m='2072449'>I</span> <span m='2072510'>had</span> <span
  m='2072719'>data</span> <span m='2072929'>that</span> <span
  m='2073080'>looked</span> <span m='2073239'>a</span> <span
  m='2073300'>lot</span> <span m='2073489'>like</span> <span
  m='2073659'>this,</span> <span m='2074800'>and</span> <span
  m='2075330'>if</span> <span m='2075469'>we</span> <span m='2075550'>had</span>
  <span m='2075639'>rigorously</span> <span m='2076090'>computed</span> <span
  m='2076530'>those</span> <span m='2076600'>probabilities,</span> <span
  m='2077290'>this</span> <span m='2077429'>is</span> <span
  m='2077520'>what</span> <span m='2077639'>we</span> <span
  m='2077699'>would</span> <span m='2077810'>have</span> <span
  m='2077900'>gotten.</span> <span m='2079170'>OK?</span> </p><p><span
  m='2081489'>So</span> <span m='2081690'>now,</span> <span
  m='2082260'>now</span> <span m='2082639'>it's</span> <span
  m='2082770'>your</span> <span m='2082909'>turn.</span> <span
  m='2084639'>So,</span> <span m='2085330'>we</span> <span
  m='2085690'>want</span> <span m='2085870'>to</span> <span
  m='2085989'>try</span> <span m='2086219'>the</span> <span
  m='2086310'>same</span> <span m='2086570'>thing,</span> <span
  m='2087280'>but</span> <span m='2087429'>in</span> <span
  m='2087489'>the</span> <span m='2087600'>other</span> <span
  m='2087760'>order.</span> <span m='2088190'>Suppose</span> <span
  m='2088520'>I</span> <span m='2088590'>first</span> <span
  m='2088940'>roll</span> <span m='2089070'>the</span> <span
  m='2089159'>9</span> <span m='2089620'>and</span> <span
  m='2089800'>then</span> <span m='2089929'>I</span> <span
  m='2089969'>roll</span> <span m='2090190'>the</span> <span
  m='2090230'>5.</span> <span m='2091100'>So</span> <span
  m='2091230'>that's</span> <span m='2091389'>the</span> <span
  m='2091480'>first</span> <span m='2091739'>question.</span> <span
  m='2092469'>The</span> <span m='2092570'>second</span> <span
  m='2092780'>question</span> <span m='2093139'>is,</span> <span
  m='2094320'>can</span> <span m='2094440'>you</span> <span
  m='2094500'>do</span> <span m='2094630'>it</span> <span m='2094690'>in</span>
  <span m='2094800'>one</span> <span m='2095040'>go?</span> <span
  m='2095600'>Instead</span> <span m='2095889'>of</span> <span
  m='2095969'>doing</span> <span m='2096239'>it</span> <span
  m='2096679'>updating</span> <span m='2097230'>for</span> <span
  m='2097340'>the</span> <span m='2097590'>9</span> <span m='2097970'>and</span>
  <span m='2098070'>then</span> <span m='2098190'>for</span> <span
  m='2098290'>the</span> <span m='2098380'>5,</span> <span
  m='2099120'>can</span> <span m='2099450'>you</span> <span
  m='2100130'>incorporate</span> <span m='2101060'>both</span> <span
  m='2101350'>the</span> <span m='2101460'>9</span> <span m='2101730'>and</span>
  <span m='2101930'>the</span> <span m='2102000'>5</span> <span
  m='2102340'>into</span> <span m='2102570'>a</span> <span
  m='2102620'>single</span> <span m='2103330'>likelihood</span> <span
  m='2103810'>function</span> <span m='2105800'>and</span> <span
  m='2105960'>do</span> <span m='2106040'>the</span> <span
  m='2106160'>updating</span> <span m='2106500'>in</span> <span
  m='2106590'>one</span> <span m='2106770'>step?</span> <span m='2107520'>All
  right,</span> <span m='2107800'>so</span> <span m='2108130'>try</span> <span
  m='2108380'>these</span> <span m='2108990'>and</span> <span
  m='2109140'>think</span> <span m='2109310'>about</span> <span
  m='2109580'>what's</span> <span m='2109780'>similar,</span> <span
  m='2110080'>what's</span> <span m='2110280'>different</span> <span
  m='2110830'>than</span> <span m='2110940'>what</span> <span
  m='2111060'>I</span> <span m='2111120'>just</span> <span
  m='2111580'>did.</span> </p><p><span m='2112510'>You don't</span> <span
  m='2112980'>have to.</span> <span m='2113920'>You don't have to.</span> <span
  m='2115800'>You could</span> <span m='2116270'>normalize it,</span> <span
  m='2116740'>then</span> <span m='2117080'>you</span> <span
  m='2117170'>would</span> <span m='2117330'>multiply</span> <span
  m='2118180'>by</span> <span m='2118270'>the</span> <span
  m='2118370'>likelihood.</span> <span m='2119000'>You'd</span> <span
  m='2119120'>get</span> <span m='2119550'>something</span> <span
  m='2119860'>again</span> <span m='2120110'>unnormalized,</span> <span
  m='2120850'>and then</span> <span m='2121130'>you'd have</span> <span
  m='2121350'>normalize</span> <span m='2121760'>again,</span> <span
  m='2122590'>and</span> <span m='2122710'>then</span> <span
  m='2122830'>you'd</span> <span m='2122920'>get to</span> <span
  m='2123100'>your</span> <span m='2123270'>final</span> <span
  m='2123580'>answer.</span> <span m='2124210'>Or,</span> <span
  m='2124840'>don't</span> <span m='2125030'>bother</span> <span
  m='2125380'>normalizing</span> <span m='2125850'>at</span> <span
  m='2125930'>this</span> <span m='2126030'>stage.</span> <span
  m='2127430'>Just</span> <span m='2127600'>multiply</span> <span
  m='2128060'>this</span> <span m='2128415'>by the</span> <span
  m='2128770'>likelihood,</span> <span m='2129530'>and</span> <span
  m='2129690'>then</span> <span m='2130040'>just</span> <span
  m='2130170'>only</span> <span m='2130290'>normalize</span> <span
  m='2130690'>once</span> <span m='2130890'>at</span> <span
  m='2130980'>the</span> <span m='2131060'>very</span> <span
  m='2131290'>end.</span> <span m='2131600'>And you'll</span> <span
  m='2131820'>get</span> <span m='2131930'>the</span> <span
  m='2132010'>same</span> <span m='2132250'>answer</span> <span
  m='2132790'>because,</span> <span m='2134131'>you know,</span> <span
  m='2134580'>normalizing</span> <span m='2135080'>once</span> <span
  m='2135560'>and then</span> <span m='2135815'>normalizing</span> <span
  m='2136070'>again</span> <span m='2136530'>is</span> <span
  m='2136990'>the</span> <span m='2137260'>same</span> <span
  m='2137540'>as</span> <span m='2138010'>just</span> <span
  m='2138190'>normalizing</span> <span m='2138970'>at</span> <span
  m='2139120'>the</span> <span m='2139180'>very</span> <span
  m='2139430'>end.</span> <span m='2139740'>You're</span> <span
  m='2139870'>just</span> <span m='2140100'>multiplying</span> <span
  m='2140600'>a</span> <span m='2140650'>vector,</span> <span
  m='2141030'>this</span> <span m='2141180'>column,</span> <span
  m='2141620'>by</span> <span m='2142820'>rescaling</span> <span
  m='2143210'>it</span> <span m='2143620'>to</span> <span m='2143720'>make
  it</span> <span m='2143970'>unit</span> <span m='2144180'>length--</span>
  </p><p><span m='2145540'>AUDIENCE: And then  you're</span> <span
  m='2145790'>multiplying</span> <span m='2146130'>it by something else--</span>
  </p><p><span m='2147590'>PROFESSOR 2: Exactly.</span> <span
  m='2147890'>Exactly.</span> </p><p><span m='2148890'>AUDIENCE: Isn't</span>
  <span m='2149220'>number</span> <span m='2149550'>1</span> <span
  m='2149840'>going</span> <span m='2150200'>to be</span> <span
  m='2150616'>the</span> <span m='2151032'>same</span> <span
  m='2151448'>answer</span> <span m='2151864'>as</span> <span m='2152280'>the
  example</span> <span m='2152390'>we just</span> <span m='2152650'>did,</span>
  <span m='2153130'>because</span> <span m='2153405'>you're</span> <span
  m='2153680'>going to be updating--</span> <span m='2154420'>I mean,</span>
  <span m='2154820'>it's</span> <span m='2155020'>going</span> <span
  m='2155230'>different.</span> <span m='2155615'>OK, we just</span> <span
  m='2156000'>have to do it.</span> </p><p><span m='2158380'>PROFESSOR 2:
  Absolutely.</span> <span m='2159060'>So,</span> <span m='2160390'>yes,</span>
  <span m='2160797'>absolutely.</span> <span m='2162020'>All of</span> <span
  m='2162300'>these</span> <span m='2162500'>could</span> <span
  m='2162590'>give</span> <span m='2162740'>you</span> <span
  m='2162780'>the</span> <span m='2162890'>same</span> <span
  m='2163120'>answer</span> <span m='2163490'>because</span> <span
  m='2163710'>it's</span> <span m='2163870'>the</span> <span
  m='2163950'>same</span> <span m='2164250'>exact</span> <span
  m='2164540'>data,</span> <span m='2164820'>right?</span> <span
  m='2165100'>Starting</span> <span m='2165430'>from</span> <span
  m='2165470'>the</span> <span m='2165530'>same</span> <span
  m='2165740'>priors.</span> <span m='2166790'>But</span> <span
  m='2167080'>what</span> <span m='2167190'>we</span> <span
  m='2167270'>want</span> <span m='2167490'>you</span> <span
  m='2167590'>to</span> <span m='2167680'>really</span> <span
  m='2167950'>see</span> <span m='2168400'>is</span> <span
  m='2168700'>how</span> <span m='2168910'>the</span> <span
  m='2169000'>math</span> <span m='2170196'>proves</span> <span
  m='2170660'>that.</span> </p><p><span m='2171120'>AUDIENCE:  I mean
  we're</span> <span m='2171550'>just</span> <span m='2171980'>multiplying  in
  different order.</span> </p><p><span m='2173160'>PROFESSOR 2: That's</span>
  <span m='2173510'>right.</span> <span m='2173810'>So</span> <span
  m='2173970'>it</span> <span m='2174060'>all</span> <span
  m='2174200'>comes</span> <span m='2174410'>down</span> <span
  m='2174580'>to</span> <span m='2174680'>what?</span> <span
  m='2176900'>What</span> <span m='2177050'>property</span> <span
  m='2177660'>of</span> <span m='2177770'>multiplication?</span> </p><p><span
  m='2179280'>AUDIENCE: Associative?</span> </p><p><span m='2181390'>AUDIENCE:
  Commutative.</span> </p><p><span m='2181860'>PROFESSOR 2: Commutative.</span>
  <span m='2182820'>I</span> <span m='2183010'>guess</span> <span
  m='2183250'>you're</span> <span m='2183350'>also</span> <span
  m='2183540'>using</span> <span m='2183740'>associativity.</span> <span
  m='2184400'>It's</span> <span m='2184810'>just</span> <span
  m='2185105'>that</span> <span m='2185400'>multiplication</span> <span
  m='2186040'>is</span> <span m='2186200'>commutative,</span> <span
  m='2186940'>right?</span> <span m='2187290'>So</span> <span
  m='2187580'>it</span> <span m='2187650'>doesn't</span> <span
  m='2187900'>matter</span> <span m='2188150'>what</span> <span
  m='2188300'>order</span> <span m='2188520'>you</span> <span
  m='2188940'>multiply</span> <span m='2189390'>these</span> <span
  m='2189570'>columns</span> <span m='2189960'>in,</span> <span
  m='2190640'>the</span> <span m='2190740'>final</span> <span
  m='2191020'>result's</span> <span m='2191390'>going to be</span> <span
  m='2191510'>the</span> <span m='2191670'>same.</span> <span
  m='2192776'>So</span> <span m='2193190'>just</span> <span
  m='2193520'>about</span> <span m='2194090'>how</span> <span
  m='2194320'>the</span> <span m='2194420'>order</span> <span
  m='2194850'>changes</span> <span m='2195480'>depending</span> <span
  m='2195860'>on</span> <span m='2196560'>the</span> <span
  m='2196640'>order</span> <span m='2197240'>of</span> <span
  m='2197350'>the</span> <span m='2197430'>5</span> <span m='2197830'>versus
  the</span> <span m='2197940'>9,</span> <span m='2198260'>and</span> <span
  m='2198350'>also,</span> <span m='2198780'>what</span> <span
  m='2198850'>happens</span> <span m='2199180'>if</span> <span
  m='2199270'>you</span> <span m='2199380'>think</span> <span
  m='2199530'>of</span> <span m='2199650'>both</span> <span
  m='2199910'>at</span> <span m='2199990'>once,</span> <span
  m='2200490'>how</span> <span m='2200620'>would</span> <span
  m='2200700'>you</span> <span m='2200950'>then make</span> <span m='2201090'>a
  table</span> <span m='2201410'>directly</span> <span m='2201770'>for
  that?</span> </p><p><span m='2203195'>[INTERPOSING VOICES]</span> </p><p><span
  m='2223650'>PROFESSOR: 5.</span> <span m='2224435'>Oh, I see.</span> <span
  m='2224720'>So</span> <span m='2224860'>you</span> <span
  m='2225000'>multiplied--</span> <span m='2226350'>here,</span> <span
  m='2226665'>is this your</span> <span m='2226980'>likelihood?</span> <span
  m='2229000'>So you</span> <span m='2229110'>multiplied</span> <span
  m='2229270'>that.</span> <span m='2229560'>Where's</span> <span
  m='2229850'>your</span> <span m='2230130'>plus</span> <span
  m='2230460'>times</span> <span m='2230710'>this?</span> <span
  m='2231890'>Oh,</span> <span m='2232380'>you</span> <span
  m='2232540'>even</span> <span m='2232760'>normalized.</span> <span
  m='2234850'>Right.</span> <span m='2235380'>So</span> <span
  m='2235550'>did</span> <span m='2235700'>you</span> <span
  m='2235770'>understand</span> <span m='2236330'>John's</span> <span
  m='2236580'>statement</span> <span m='2236940'>that you</span> <span
  m='2237100'>didn't</span> <span m='2237310'>actually</span> <span
  m='2237600'>have</span> <span m='2237740'>to</span> <span
  m='2237860'>normalize?</span> </p><p><span m='2239016'>AUDIENCE: 
  Right.</span> <span m='2239750'>I mean,</span> <span m='2239900'>if you'd
  already done it.</span> </p><p><span m='2240960'>PROFESSOR: No,</span> <span
  m='2241160'>I</span> <span m='2241310'>understand.</span> <span
  m='2241870'>It's</span> <span m='2242110'>a</span> <span
  m='2242180'>nicer</span> <span m='2242490'>number</span> <span
  m='2242800'>than 1/60.</span> <span m='2243430'>But</span> <span
  m='2243840'>if</span> <span m='2243960'>you</span> <span
  m='2244040'>didn't</span> <span m='2244250'>have</span> <span
  m='2244480'>it,</span> <span m='2244560'>you</span> <span
  m='2244660'>could</span> <span m='2244860'>have just</span> <span
  m='2245060'>used</span> <span m='2245180'>this</span> <span
  m='2245420'>column</span> <span m='2245770'>and</span> <span
  m='2245840'>normalized</span> <span m='2246280'>at the end.</span> <span
  m='2247010'>That</span> <span m='2247080'>make</span> <span
  m='2247250'>sense?</span> <span m='2247880'>Excellent.</span> </p><p><span
  m='2255190'>I'm not trying to--</span> </p><p><span m='2255840'>AUDIENCE: This
  is just</span> <span m='2256335'>if you do</span> <span m='2256830'>it in one
  step.</span> </p><p><span m='2257820'>PROFESSOR: I</span> <span
  m='2257930'>see.</span> </p><p><span m='2258286'>AUDIENCE: You just
  multiply.</span> </p><p><span m='2259000'>PROFESSOR: Did</span> <span
  m='2259140'>you</span> <span m='2259200'>get</span> <span
  m='2259340'>different</span> <span m='2259620'>answers?</span> </p><p><span
  m='2260040'>AUDIENCE: No, it's the same.</span> </p><p><span
  m='2260740'>PROFESSOR: It's the same.</span> <span m='2261250'>It</span> <span
  m='2261520'>makes</span> <span m='2261770'>sense.</span> <span
  m='2262040'>You</span> <span m='2262120'>have</span> <span
  m='2262270'>the</span> <span m='2262370'>data.</span> <span
  m='2262670'>That's</span> <span m='2262920'>the</span> <span
  m='2263030'>evidence</span> <span m='2263420'>you</span> <span
  m='2263520'>have.</span> <span m='2264852'>Right.</span> <span
  m='2266620'>So</span> <span m='2266950'>was</span> <span
  m='2267140'>this</span> <span m='2267360'>all</span> <span
  m='2267580'>clear?</span> <span m='2268410'>Was</span> <span
  m='2268610'>John's</span> <span m='2268690'>statement</span> <span
  m='2269100'>about</span> <span m='2269320'>not</span> <span
  m='2269560'>only</span> <span m='2269800'>needing</span> <span m='2269990'>the
  unnormalized</span> <span m='2270880'>posterior</span> <span
  m='2271440'>in</span> <span m='2271530'>the</span> <span
  m='2271600'>middle</span> <span m='2272820'>reasonably</span> <span
  m='2273010'>clear?</span> </p><p><span m='2274334'>AUDIENCE: What</span> <span
  m='2274771'>were</span> <span m='2275210'>talking</span> <span
  m='2275570'>about is if</span> <span m='2275930'>you</span> <span
  m='2276070'>were</span> <span m='2276390'>to</span> <span
  m='2276620'>use</span> <span m='2276890'>the</span> <span
  m='2277160'>normalized one,</span> <span m='2279394'>would</span> <span
  m='2279892'>then your</span> <span m='2280390'>unnormalized</span> <span
  m='2280888'>posterior</span> <span m='2281386'>be</span> <span m='2281884'>the
  actual</span> <span m='2282382'>probabilities?</span> </p><p><span
  m='2283690'>PROFESSOR: No.</span> <span m='2284860'>No,</span> <span
  m='2285390'>because</span> <span m='2286730'>in</span> <span
  m='2287050'>order</span> <span m='2287270'>to</span> <span
  m='2287390'>use</span> <span m='2287640'>the</span> <span
  m='2287710'>Law</span> <span m='2287880'>of</span> <span
  m='2287940'>Total</span> <span m='2288220'>Probability,</span> <span
  m='2289430'>you</span> <span m='2289530'>have</span> <span
  m='2289640'>to</span> <span m='2289740'>multiply</span> <span
  m='2290160'>your</span> <span m='2290240'>likelihood</span> <span
  m='2290860'>by</span> <span m='2291210'>genuine</span> <span
  m='2291800'>probabilities.</span> <span m='2292730'>And</span> <span
  m='2293310'>the</span> <span m='2293420'>unnormalized</span> <span
  m='2293930'>posterior</span> <span m='2294580'>is not a</span> <span
  m='2294810'>genuine</span> <span m='2295380'>probability.</span> </p><p><span
  m='2296210'>AUDIENCE: But</span> <span m='2296440'>if you use</span> <span
  m='2296620'>the normalized one.</span> </p><p><span m='2297240'>PROFESSOR: If
  you</span> <span m='2297460'>used the</span> <span
  m='2297520'>normalized</span> <span m='2297940'>one,</span> <span
  m='2298090'>then</span> <span m='2298270'>it</span> <span m='2298320'>would
  be--</span> <span m='2300550'>that</span> <span m='2300800'>would</span> <span
  m='2300910'>be</span> <span m='2301020'>the</span> <span
  m='2301130'>total</span> <span m='2301410'>probability</span> <span
  m='2302914'>of</span> <span m='2303291'>that.</span> <span
  m='2304210'>That's</span> <span m='2304430'>exactly right.</span> </p><p><span
  m='2306100'>AUDIENCE: But, in this case,</span> <span m='2306370'>it's</span>
  <span m='2306610'>this</span> <span m='2306700'>that's</span> <span
  m='2307150'>the total</span> <span m='2307600'>probability, right?</span>
  </p><p><span m='2308050'>PROFESSOR: Yeah.</span> <span m='2308500'>This</span>
  <span m='2308710'>is</span> <span m='2308820'>now</span> <span
  m='2309030'>your</span> <span m='2309130'>posterior</span> <span
  m='2309780'>probability.</span> <span m='2312150'>These  are now</span> <span
  m='2312430'>the probability.</span> <span m='2312690'>So,</span> <span
  m='2313580'>make</span> <span m='2313790'>a</span> <span
  m='2313830'>distinction.</span> <span m='2314110'>The</span> <span
  m='2314390'>total</span> <span m='2314720'>probability</span> <span
  m='2315320'>is</span> <span m='2315440'>about</span> <span
  m='2315690'>the</span> <span m='2315780'>data,</span> <span
  m='2316970'>and</span> <span m='2317150'>these</span> <span
  m='2317380'>probabilities</span> <span m='2318060'>here are</span> <span
  m='2318470'>about</span> <span m='2318820'>the</span> <span
  m='2319740'>hypotheses.</span> </p><p><span m='2322249'>AUDIENCE: Sort of
  like</span> <span m='2322742'>the fit</span> <span m='2323235'>of the
  hypothesis</span> <span m='2323728'>to the data.</span> </p><p><span
  m='2325700'>PROFESSOR:  You</span> <span m='2325930'>could</span> <span
  m='2326080'>think</span> <span m='2326250'>of</span> <span
  m='2326330'>that.</span> <span m='2326640'>They're</span> <span
  m='2326780'>genuine</span> <span m='2327220'>probabilities.</span> <span
  m='2327880'>This</span> <span m='2328050'>is</span> <span
  m='2328690'>the</span> <span m='2328930'>probability</span> <span
  m='2330350'>that</span> <span m='2330560'>you</span> <span
  m='2331250'>chose</span> <span m='2331550'>the</span> <span
  m='2331660'>12-sided</span> <span m='2332300'>die</span> <span
  m='2332540'>given</span> <span m='2332850'>the</span> <span
  m='2332940'>data.</span> <span m='2333200'>That</span> <span
  m='2333380'>is,</span> <span m='2333830'>if</span> <span m='2335020'>I
  did</span> <span m='2335380'>this</span> <span m='2335710'>a</span> <span
  m='2335760'>million</span> <span m='2336110'>times</span> <span
  m='2337110'>and</span> <span m='2337270'>every</span> <span
  m='2337480'>time,</span> <span m='2339410'>I</span> <span
  m='2339520'>only</span> <span m='2339800'>looked</span> <span
  m='2340040'>at</span> <span m='2340100'>the</span> <span
  m='2340180'>times</span> <span m='2340420'>I</span> <span m='2340610'>rolled
  a</span> <span m='2340820'>9</span> <span m='2341120'>and</span> <span
  m='2341210'>then</span> <span m='2341310'>the</span> <span
  m='2341390'>5,</span> <span m='2342360'>you</span> <span
  m='2342510'>would</span> <span m='2342640'>find</span> <span
  m='2342950'>this</span> <span m='2343130'>fraction of</span> <span
  m='2343540'>those</span> <span m='2343870'>times</span> <span
  m='2345160'>would</span> <span m='2345350'>be--</span> <span
  m='2346420'>it</span> <span m='2346540'>would</span> <span
  m='2346650'>be</span> <span m='2346760'>a</span> <span
  m='2346830'>12-sided</span> <span m='2347460'>and</span> <span
  m='2347660'>this</span> <span m='2347840'>fraction</span> <span
  m='2348220'>would</span> <span m='2348360'>be</span> <span
  m='2348480'>a</span> <span m='2348540'>20-sided.</span> <span
  m='2349060'>So,</span> <span m='2349700'>I</span> <span
  m='2349820'>forget</span> <span m='2350060'>what</span> <span
  m='2350160'>the</span> <span m='2350250'>numbers</span> <span
  m='2350510'>were,</span> <span m='2350600'>like</span> <span
  m='2350790'>3</span> <span m='2350980'>to</span> <span m='2351060'>1.</span>
  <span m='2352320'>Yeah.</span> <span m='2352920'>Makes</span> <span
  m='2353090'>sense?</span> <span m='2353942'>Excellent.</span> </p><p><span
  m='2355270'>AUDIENCE:  So</span> <span m='2355410'>we</span> <span
  m='2355490'>multiply them</span> <span m='2356010'>together,</span> <span
  m='2356620'>but then--</span> </p><p><span m='2359010'>PROFESSOR 2: You</span>
  <span m='2359110'>get</span> <span m='2359670'>the</span> <span
  m='2359830'>same</span> <span m='2360060'>exact</span> <span
  m='2360350'>answer,</span> <span m='2360615'>right?</span> </p><p><span
  m='2361170'>AUDIENCE: So</span> <span m='2361370'>we</span> <span
  m='2361960'>get</span> <span m='2362220'>these,</span> <span
  m='2362460'>this</span> <span m='2362896'>answer.</span> </p><p><span
  m='2363332'>AUDIENCE 2: That's</span> <span m='2363770'>right,</span> <span
  m='2364080'>so it's unnormalized.</span> </p><p><span m='2365790'>PROFESSOR:
  And</span> <span m='2365910'>then</span> <span m='2366010'>you</span> <span
  m='2366080'>normalize</span> <span m='2366520'>it and</span> <span
  m='2366620'>you</span> <span m='2366690'>get</span> <span
  m='2366850'>this,</span> <span m='2367430'>right.</span> </p><p><span
  m='2367770'>AUDIENCE: There's no way to</span> <span
  m='2367990'>normalize</span> <span m='2369770'>it</span> <span
  m='2369870'>without--</span> </p><p><span m='2371630'>PROFESSOR 2: All</span>
  <span m='2371860'>right,</span> <span m='2372180'>let's</span> <span
  m='2372370'>come</span> <span m='2372520'>back</span> <span
  m='2372690'>together</span> <span m='2373090'>and</span> <span
  m='2373220'>take</span> <span m='2373390'>a</span> <span
  m='2373470'>look</span> <span m='2373720'>at</span> <span
  m='2374180'>what</span> <span m='2374430'>happened</span> <span
  m='2374720'>here.</span> <span m='2378470'>I</span> <span
  m='2378610'>saw</span> <span m='2378840'>some</span> <span
  m='2379080'>aha</span> <span m='2379370'>moments.</span> <span
  m='2379910'>That</span> <span m='2380020'>was</span> <span
  m='2380200'>great.</span> <span m='2383490'>Some</span> <span
  m='2383750'>people</span> <span m='2384000'>cited</span> <span
  m='2384290'>The</span> <span m='2384390'>Commutative</span> <span
  m='2384800'>Property</span> <span m='2385160'>of</span> <span
  m='2385220'>Multiplication.</span> <span m='2386040'>That</span> <span
  m='2386170'>made</span> <span m='2386280'>me</span> <span
  m='2386380'>very</span> <span m='2386550'>happy.</span> <span
  m='2389510'>So,</span> <span m='2389830'>what</span> <span
  m='2389950'>do</span> <span m='2389990'>we</span> <span m='2390100'>do?</span>
  </p><p><span m='2392100'>So</span> <span m='2392310'>when we</span> <span
  m='2392440'>do</span> <span m='2392560'>the</span> <span m='2392660'>9</span>
  <span m='2392990'>and</span> <span m='2393070'>then</span> <span
  m='2393180'>the</span> <span m='2393250'>5,</span> <span m='2394330'>it</span>
  <span m='2394450'>looks</span> <span m='2394680'>just</span> <span
  m='2394880'>like</span> <span m='2395030'>what</span> <span
  m='2395140'>I</span> <span m='2395240'>did</span> <span
  m='2395410'>with</span> <span m='2395480'>the</span> <span
  m='2395570'>5</span> <span m='2395820'>and</span> <span m='2395880'>the</span>
  <span m='2395970'>9,</span> <span m='2396300'>except</span> <span
  m='2396590'>the</span> <span m='2396670'>likelihood</span> <span
  m='2397330'>columns</span> <span m='2397920'>are</span> <span
  m='2398100'>flipped.</span> <span m='2399240'>So</span> <span
  m='2400110'>we</span> <span m='2400210'>have</span> <span
  m='2400410'>our</span> <span m='2400510'>prior,</span> <span
  m='2401480'>the</span> <span m='2401580'>likelihood</span> <span
  m='2403310'>for</span> <span m='2403440'>the</span> <span m='2403540'>9</span>
  <span m='2404490'>gives</span> <span m='2404710'>us</span> <span
  m='2405040'>this</span> <span m='2405230'>column.</span> <span
  m='2407050'>The</span> <span m='2407150'>product</span> <span
  m='2407700'>gives</span> <span m='2407880'>us</span> <span
  m='2408000'>an,</span> <span m='2408240'>first,</span> <span
  m='2408560'>unnormalized</span> <span m='2409130'>posterior.</span> <span
  m='2410550'>Then</span> <span m='2410680'>we</span> <span
  m='2410770'>do</span> <span m='2410870'>the</span> <span
  m='2410970'>likelihood</span> <span m='2412020'>for</span> <span
  m='2412160'>rolling</span> <span m='2412400'>a</span> <span
  m='2412440'>5.</span> <span m='2414540'>The</span> <span
  m='2414640'>product</span> <span m='2415590'>of</span> <span
  m='2415700'>the</span> <span m='2415820'>unnormalized</span> <span
  m='2416330'>posterior</span> <span m='2417000'>and the</span> <span
  m='2417190'>second</span> <span m='2417450'>likelihood</span> <span
  m='2418240'>gives</span> <span m='2418490'>us</span> <span
  m='2418750'>our</span> <span m='2419240'>final</span> <span
  m='2419820'>unnormalized</span> <span m='2420420'>posterior.</span>
  </p><p><span m='2422410'>And</span> <span m='2423390'>notice</span> <span
  m='2423850'>the</span> <span m='2423940'>sum</span> <span
  m='2424200'>is</span> <span m='2424280'>still</span> <span
  m='2424490'>exactly</span> <span m='2424860'>what</span> <span
  m='2424950'>it</span> <span m='2424990'>was</span> <span
  m='2425210'>before,</span> <span m='2425550'>0.019.</span> <span
  m='2427910'>When</span> <span m='2428050'>we</span> <span
  m='2428130'>normalize,</span> <span m='2429380'>we</span> <span
  m='2429480'>get</span> <span m='2429590'>exactly</span> <span
  m='2429920'>the</span> <span m='2430010'>same</span> <span
  m='2430230'>answer</span> <span m='2430940'>that</span> <span
  m='2431070'>we</span> <span m='2431150'>had</span> <span
  m='2431340'>before.</span> <span m='2431810'>Now,</span> <span m='2431960'>if
  you</span> <span m='2432110'>contrast</span> <span m='2432580'>this</span>
  <span m='2433300'>with</span> <span m='2433870'>the</span> <span
  m='2433980'>table</span> <span m='2434720'>we</span> <span
  m='2434910'>looked</span> <span m='2435150'>at</span> <span
  m='2435570'>when</span> <span m='2435700'>we</span> <span
  m='2435800'>did</span> <span m='2435880'>the</span> <span m='2435970'>5</span>
  <span m='2436260'>and then</span> <span m='2436680'>the 9,</span> <span
  m='2437430'>what</span> <span m='2437680'>changed</span> <span
  m='2438350'>is</span> <span m='2438960'>these</span> <span
  m='2439190'>two</span> <span m='2439340'>columns</span> <span
  m='2439960'>were</span> <span m='2440040'>flipped</span> <span
  m='2440270'>around.</span> <span m='2441940'>And</span> <span
  m='2442100'>so</span> <span m='2442220'>I</span> <span
  m='2442290'>suppose</span> <span m='2442940'>this</span> <span
  m='2443160'>column</span> <span m='2443680'>was</span> <span
  m='2443870'>different</span> <span m='2444300'>and</span> <span
  m='2444380'>this</span> <span m='2444540'>column</span> <span
  m='2444820'>was</span> <span m='2444970'>different</span> <span
  m='2445360'>as</span> <span m='2445490'>a</span> <span
  m='2445520'>result.</span> <span m='2445960'>And</span> <span
  m='2446050'>then</span> <span m='2446170'>the</span> <span
  m='2446240'>final</span> <span m='2446660'>result,</span> <span
  m='2447150'>however,</span> <span m='2448050'>was</span> <span
  m='2448190'>exactly</span> <span m='2448580'>the</span> <span
  m='2448670'>same.</span> </p><p><span m='2450740'>Now,</span> <span
  m='2452090'>what</span> <span m='2452260'>if</span> <span
  m='2452400'>we</span> <span m='2453120'>do</span> <span
  m='2453220'>them</span> <span m='2453370'>both</span> <span
  m='2453440'>at</span> <span m='2453530'>once?</span> <span
  m='2453890'>What</span> <span m='2454070'>should</span> <span
  m='2454140'>that</span> <span m='2454300'>mean?</span> <span
  m='2457340'>If</span> <span m='2457460'>we</span> <span m='2457530'>do
  them</span> <span m='2457740'>both</span> <span m='2457940'>at</span> <span
  m='2458020'>once</span> <span m='2458990'>then,</span> <span
  m='2459500'>well</span> <span m='2459700'>we</span> <span
  m='2459800'>start</span> <span m='2460120'>from</span> <span
  m='2460170'>the</span> <span m='2460250'>same</span> <span
  m='2460670'>uniform</span> <span m='2461030'>prior,</span> <span
  m='2462220'>and</span> <span m='2462410'>our</span> <span
  m='2462540'>likelihood--</span> <span m='2463710'>now,</span> <span
  m='2464380'>we</span> <span m='2464500'>should</span> <span
  m='2464670'>think</span> <span m='2464840'>of</span> <span
  m='2464930'>the</span> <span m='2465020'>data</span> <span
  m='2465780'>as</span> <span m='2466700'>both</span> <span
  m='2466980'>rolls,</span> <span m='2467660'>the</span> <span
  m='2467750'>5</span> <span m='2468320'>and</span> <span m='2468630'>the</span>
  <span m='2468710'>9.</span> <span m='2469700'>OK.</span> </p><p><span
  m='2470790'>Now</span> <span m='2470920'>what's</span> <span
  m='2471060'>important</span> <span m='2471480'>here</span> <span
  m='2471910'>is</span> <span m='2472090'>that</span> <span
  m='2473950'>if</span> <span m='2474100'>we</span> <span
  m='2474230'>condition</span> <span m='2475100'>on</span> <span
  m='2475400'>a</span> <span m='2475430'>given</span> <span
  m='2475690'>hypothesis.</span> <span m='2476400'>For</span> <span
  m='2476500'>example,</span> <span m='2476830'>if</span> <span
  m='2476930'>we</span> <span m='2477030'>condition</span> <span
  m='2477420'>on</span> <span m='2477620'>the</span> <span
  m='2477680'>hypothesis</span> <span m='2478970'>that</span> <span
  m='2479100'>it's a</span> <span m='2479250'>12-sided</span> <span
  m='2479760'>die,</span> <span m='2481010'>then</span> <span
  m='2482000'>the</span> <span m='2482120'>first</span> <span
  m='2482490'>roll</span> <span m='2482980'>and</span> <span
  m='2483120'>the</span> <span m='2483190'>second</span> <span
  m='2483540'>roll</span> <span m='2483950'>are</span> <span
  m='2484130'>independent</span> <span m='2485170'>events,</span> <span
  m='2486180'>right?</span> <span m='2487130'>It</span> <span
  m='2487280'>means</span> <span m='2487570'>that</span> <span
  m='2488030'>we</span> <span m='2488160'>can</span> <span
  m='2488310'>figure</span> <span m='2488510'>out</span> <span
  m='2488620'>the</span> <span m='2488700'>probability</span> <span
  m='2490470'>of a</span> <span m='2490590'>5</span> <span
  m='2491260'>and</span> <span m='2491400'>the</span> <span m='2491460'>9</span>
  <span m='2492220'>on</span> <span m='2492330'>the</span> <span
  m='2492410'>12-sided</span> <span m='2492870'>die.</span> <span
  m='2493430'>It's</span> <span m='2493560'>just</span> <span
  m='2493710'>the</span> <span m='2493790'>product</span> <span
  m='2494940'>of</span> <span m='2495040'>the</span> <span
  m='2495110'>probability</span> <span m='2495610'>of a</span> <span
  m='2495780'>5</span> <span m='2496180'>and</span> <span m='2496230'>a</span>
  <span m='2496290'>12-sided</span> <span m='2496740'>die</span> <span
  m='2497240'>and</span> <span m='2497360'>the</span> <span
  m='2497420'>probability</span> <span m='2498150'>of a</span> <span
  m='2498330'>9</span> <span m='2498820'>on</span> <span m='2498930'>a</span>
  <span m='2499190'>12-sided</span> <span m='2499350'>die.</span> </p><p><span
  m='2500140'>That's</span> <span m='2500410'>why</span> <span
  m='2500510'>we're</span> <span m='2500610'>justified</span> <span
  m='2501140'>in</span> <span m='2501230'>taking</span> <span
  m='2501530'>the</span> <span m='2501620'>product.</span> <span
  m='2502270'>If</span> <span m='2502370'>we</span> <span
  m='2502720'>condition</span> <span m='2503700'>on</span> <span
  m='2504070'>the</span> <span m='2504160'>die</span> <span
  m='2504430'>that</span> <span m='2504580'>it</span> <span
  m='2504670'>is,</span> <span m='2504950'>on</span> <span
  m='2505150'>the</span> <span m='2505210'>hypothesis,</span> <span
  m='2505890'>12-sided,</span> <span m='2506840'>then</span> <span
  m='2507540'>the</span> <span m='2507630'>rolls</span> <span
  m='2507960'>are</span> <span m='2508070'>all</span> <span
  m='2508270'>independent</span> <span m='2508690'>of</span> <span
  m='2508760'>each</span> <span m='2508910'>other.</span> <span m='2510280'>In
  particular,</span> <span m='2510740'>we</span> <span m='2510980'>get</span>
  <span m='2511640'>1/12</span> <span m='2512090'>times</span> <span
  m='2512340'>1/12</span> <span m='2514330'>for</span> <span
  m='2514440'>rolling</span> <span m='2514670'>a</span> <span
  m='2514740'>5</span> <span m='2515070'>and</span> <span
  m='2515160'>then</span> <span m='2515270'>rolling</span> <span
  m='2515510'>a</span> <span m='2515560'>9.</span> <span m='2516080'>And</span>
  <span m='2516230'>for</span> <span m='2516280'>the</span> <span
  m='2516360'>20-sided</span> <span m='2516860'>die,</span> <span
  m='2517050'>we</span> <span m='2517160'>get</span> <span
  m='2517370'>1/20</span> <span m='2518040'>times</span> <span
  m='2518560'>1/20.</span> </p><p><span m='2521750'>So</span> <span
  m='2521790'>now</span> <span m='2521950'>in</span> <span
  m='2522030'>one</span> <span m='2522270'>step,</span> <span
  m='2522700'>we</span> <span m='2522840'>update.</span> <span
  m='2525260'>Same</span> <span m='2525970'>exact</span> <span
  m='2526320'>sum,</span> <span m='2527780'>we</span> <span
  m='2527900'>normalize,</span> <span m='2530240'>same</span> <span
  m='2530470'>exact</span> <span m='2530770'>answer.</span> <span
  m='2532100'>And</span> <span m='2532270'>I</span> <span
  m='2532310'>mentioned</span> <span m='2533960'>that</span> <span
  m='2534560'>some</span> <span m='2534810'>groups,</span> <span
  m='2535570'>maybe</span> <span m='2535860'>when</span> <span
  m='2536020'>slightly</span> <span m='2536300'>prompted</span> <span
  m='2536620'>by</span> <span m='2536760'>me,</span> <span
  m='2537590'>said</span> <span m='2538680'>oh,</span> <span
  m='2539430'>multiplication</span> <span m='2540150'>is</span> <span
  m='2540260'>commutative.</span> <span m='2541290'>Right?</span> <span
  m='2542020'>That's</span> <span m='2542710'>all</span> <span
  m='2542950'>that's</span> <span m='2543150'>going</span> <span
  m='2543380'>on</span> <span m='2543540'>here.</span> <span
  m='2544390'>In</span> <span m='2544510'>the</span> <span
  m='2544620'>end,</span> <span m='2545000'>all</span> <span
  m='2545250'>we're</span> <span m='2545360'>doing</span> <span
  m='2545740'>is</span> <span m='2545860'>taking</span> <span
  m='2546260'>our</span> <span m='2546370'>prior,</span> <span
  m='2547280'>the</span> <span m='2547380'>first</span> <span
  m='2547670'>likelihood</span> <span m='2548230'>column,</span> <span
  m='2548560'>the</span> <span m='2548640'>second</span> <span
  m='2548940'>likelihood</span> <span m='2549300'>column,</span> <span
  m='2549760'>multiplying</span> <span m='2550310'>them</span> <span
  m='2550420'>together</span> <span m='2550850'>and</span> <span
  m='2550960'>then</span> <span m='2551080'>normalizing</span> <span
  m='2551660'>it.</span> <span m='2552180'>Right?</span> </p><p><span
  m='2553210'>It</span> <span m='2553340'>doesn't</span> <span
  m='2553650'>matter</span> <span m='2554010'>what</span> <span
  m='2554170'>order</span> <span m='2554500'>those</span> <span
  m='2554690'>likelihood</span> <span m='2555040'>columns</span> <span
  m='2555390'>are</span> <span m='2555510'>in.</span> <span
  m='2555680'>It</span> <span m='2555750'>doesn't</span> <span
  m='2555980'>matter</span> <span m='2556220'>if</span> <span
  m='2556290'>we</span> <span m='2556390'>think</span> <span
  m='2556590'>of</span> <span m='2556680'>the</span> <span m='2556770'>5</span>
  <span m='2557090'>in</span> <span m='2557270'>the</span> <span
  m='2557380'>9,</span> <span m='2557760'>the 9</span> <span
  m='2557990'>in</span> <span m='2558060'>the</span> <span m='2558140'>5,</span>
  <span m='2558480'>or</span> <span m='2558720'>the</span> <span
  m='2558800'>5</span> <span m='2559070'>and</span> <span m='2559240'>9</span>
  <span m='2559310'>multiplied</span> <span m='2559790'>together</span> <span
  m='2560420'>to</span> <span m='2560520'>make</span> <span
  m='2560650'>their</span> <span m='2560790'>own likelihood</span> <span
  m='2561260'>column.</span> <span m='2561900'>You</span> <span
  m='2562020'>get</span> <span m='2562240'>the</span> <span
  m='2562300'>same</span> <span m='2562630'>exact</span> <span
  m='2563050'>unnormalized</span> <span m='2563610'>result</span> <span
  m='2563950'>no</span> <span m='2564020'>matter</span> <span
  m='2564240'>what.</span> </p><p><span m='2565870'>OK.</span> <span
  m='2566580'>So</span> <span m='2566730'>this</span> <span
  m='2567090'>is</span> <span m='2567470'>all</span> <span
  m='2567700'>there</span> <span m='2567850'>is</span> <span
  m='2567990'>to</span> <span m='2568450'>why</span> <span m='2569800'>it</span>
  <span m='2569940'>doesn't</span> <span m='2570190'>matter</span> <span
  m='2570380'>what</span> <span m='2570530'>order</span> <span
  m='2571320'>you</span> <span m='2571580'>update</span> <span
  m='2571920'>the</span> <span m='2571990'>data</span> <span
  m='2572240'>in</span> <span m='2572470'>sequentially,</span> <span
  m='2573900'>it</span> <span m='2574280'>just</span> <span
  m='2574490'>matters</span> <span m='2574750'>what</span> <span
  m='2574850'>the</span> <span m='2574920'>data</span> <span
  m='2575100'>is.</span> <span m='2576110'>Now</span> <span m='2576230'>I</span>
  <span m='2576290'>also</span> <span m='2576590'>had</span> <span
  m='2576670'>a</span> <span m='2576710'>question.</span> <span
  m='2577960'>Why</span> <span m='2579190'>if</span> <span
  m='2579320'>you</span> <span m='2579420'>could</span> <span
  m='2579530'>do</span> <span m='2579640'>it</span> <span m='2579710'>all</span>
  <span m='2579910'>once</span> <span m='2580880'>would</span> <span
  m='2581020'>you</span> <span m='2581100'>even</span> <span
  m='2581310'>bother</span> <span m='2582940'>with</span> <span
  m='2583790'>doing</span> <span m='2584000'>it</span> <span
  m='2584100'>once</span> <span m='2584530'>and</span> <span
  m='2584620'>then</span> <span m='2584740'>doing</span> <span
  m='2584950'>it</span> <span m='2585010'>again?</span> <span
  m='2586280'>It's</span> <span m='2586420'>a</span> <span
  m='2586460'>very</span> <span m='2586650'>good</span> <span
  m='2586770'>question.</span> <span m='2588180'>Does</span> <span
  m='2588290'>anyone</span> <span m='2589810'>want</span> <span
  m='2589990'>to</span> <span m='2590340'>suggest</span> <span
  m='2590740'>a</span> <span m='2590780'>reason?</span> <span
  m='2591360'>Maybe</span> <span m='2591600'>other</span> <span
  m='2591760'>than</span> <span m='2592130'>the</span> <span
  m='2592210'>group</span> <span m='2592450'>that I</span> <span
  m='2592570'>talked to</span> <span m='2592920'>specifically</span> <span
  m='2593380'>about</span> <span m='2593600'>it</span> <span
  m='2595530'>Yeah.</span> </p><p><span m='2596670'>AUDIENCE: Well,</span> <span
  m='2597150'>I'm</span> <span m='2597390'>just thinking,</span> <span
  m='2598010'>as</span> <span m='2598170'>you're</span> <span
  m='2598310'>saying,</span> <span m='2598900'>if</span> <span m='2599110'>you
  have ongoing</span> <span m='2599390'>patients</span> <span
  m='2600146'>and</span> <span m='2600512'>you have to</span> <span
  m='2600880'>like</span> <span m='2601200'>continuously</span> <span
  m='2601790'>update,</span> <span m='2602450'>then</span> <span
  m='2603656'>the</span> <span m='2604000'>first</span> <span
  m='2604390'>data</span> <span m='2604750'>set</span> <span
  m='2605000'>may</span> <span m='2605510'>be</span> <span
  m='2605770'>all</span> <span m='2605950'>that</span> <span
  m='2606100'>you</span> <span m='2606290'>have</span> <span m='2606773'>at that
  moment,</span> <span m='2607256'>but then you have</span> <span
  m='2607739'>to</span> <span m='2608705'>keeping adding on to it.</span>
  </p><p><span m='2609190'>PROFESSOR 2: That's</span> <span
  m='2609390'>exactly</span> <span m='2609920'>right.</span> <span
  m='2610420'>That's</span> <span m='2610510'>exactly</span> <span
  m='2610920'>right.</span> <span m='2611370'>So,</span> <span
  m='2612830'>in</span> <span m='2613000'>life</span> <span
  m='2613590'>and</span> <span m='2613860'>in</span> <span
  m='2613950'>clinical</span> <span m='2614280'>trials,</span> <span
  m='2616280'>you</span> <span m='2616390'>don't</span> <span
  m='2616580'>get</span> <span m='2616670'>all</span> <span
  m='2616790'>the</span> <span m='2616870'>data</span> <span
  m='2617310'>necessarily</span> <span m='2618110'>at</span> <span
  m='2618260'>once.</span> <span m='2618680'>It</span> <span
  m='2618800'>sort</span> <span m='2618940'>of</span> <span
  m='2619040'>comes</span> <span m='2619330'>in</span> <span
  m='2620600'>continuously.</span> <span m='2622710'>When</span> <span
  m='2622860'>I</span> <span m='2622900'>wake</span> <span m='2623120'>up</span>
  <span m='2623240'>in</span> <span m='2623320'>the</span> <span
  m='2623380'>morning,</span> <span m='2624150'>I</span> <span
  m='2624160'>don't</span> <span m='2624290'>know</span> <span
  m='2624370'>what</span> <span m='2624480'>temperature</span> <span
  m='2624960'>it</span> <span m='2625060'>is</span> <span
  m='2625160'>outside.</span> <span m='2626900'>I</span> <span
  m='2627030'>have</span> <span m='2627180'>a</span> <span
  m='2627240'>prior,</span> <span m='2627860'>based</span> <span
  m='2628140'>on</span> <span m='2628470'>what</span> <span
  m='2628670'>temperature</span> <span m='2629070'>it was</span> <span
  m='2629240'>yesterday</span> <span m='2629720'>at about</span> <span
  m='2629950'>the</span> <span m='2630010'>same</span> <span
  m='2630230'>time,</span> <span m='2630670'>like</span> <span
  m='2630760'>I</span> <span m='2630790'>have</span> <span m='2630930'>a</span>
  <span m='2630980'>memory</span> <span m='2631290'>of</span> <span
  m='2631380'>that.</span> <span m='2632240'>So</span> <span
  m='2632370'>it</span> <span m='2632450'>gives</span> <span
  m='2632590'>me</span> <span m='2632680'>some</span> <span
  m='2632850'>prior</span> <span m='2633230'>distribution</span> <span
  m='2633810'>on</span> <span m='2633900'>the</span> <span
  m='2633980'>temperature.</span> <span m='2635180'>OK,</span> <span
  m='2635380'>that</span> <span m='2635490'>might</span> <span
  m='2635620'>be</span> <span m='2635710'>a</span> <span
  m='2635750'>continuous</span> <span m='2636270'>one,</span> <span
  m='2636480'>like</span> <span m='2636640'>maybe</span> <span
  m='2636870'>a</span> <span m='2636910'>bell</span> <span
  m='2637120'>curve.</span> <span m='2637640'>We're</span> <span
  m='2637780'>going</span> <span m='2637860'>to</span> <span
  m='2637900'>get</span> <span m='2638080'>to</span> <span
  m='2638160'>that</span> <span m='2638370'>next</span> <span
  m='2638610'>week,</span> <span m='2638900'>these</span> <span
  m='2639050'>continuous</span> <span m='2640050'>updating</span> <span
  m='2640480'>problems.</span> <span m='2640940'>OK.</span> </p><p><span
  m='2642110'>And</span> <span m='2642240'>then,</span> <span
  m='2642570'>when</span> <span m='2642720'>I</span> <span
  m='2642760'>get</span> <span m='2643010'>out of</span> <span
  m='2643060'>bed,</span> <span m='2643470'>I</span> <span
  m='2643590'>see</span> <span m='2643790'>that</span> <span
  m='2643920'>the</span> <span m='2644010'>window is</span> <span
  m='2644490'>covered</span> <span m='2644860'>in</span> <span
  m='2645290'>condensation.</span> <span m='2646940'>That's</span> <span
  m='2647140'>some</span> <span m='2647260'>data.</span> <span
  m='2648310'>I</span> <span m='2648400'>can</span> <span
  m='2648560'>update</span> <span m='2648850'>my</span> <span
  m='2648950'>beliefs.</span> <span m='2649440'>Probably</span> <span
  m='2650150'>means</span> <span m='2650360'>it's</span> <span
  m='2650650'>kind</span> <span m='2650790'>of</span> <span
  m='2650850'>cold.</span> <span m='2652790'>Great.</span> <span
  m='2653910'>Then</span> <span m='2654160'>I</span> <span
  m='2654240'>can</span> <span m='2655250'>open</span> <span
  m='2655530'>the</span> <span m='2655620'>window</span> <span
  m='2655850'>to</span> <span m='2655940'>let</span> <span
  m='2656060'>the</span> <span m='2656150'>cat</span> <span
  m='2656390'>out,</span> <span m='2656640'>and a</span> <span
  m='2656740'>burst</span> <span m='2657500'>of</span> <span
  m='2657580'>freezing</span> <span m='2658080'>cold</span> <span
  m='2658290'>air</span> <span m='2658420'>comes</span> <span
  m='2658680'>in,</span> <span m='2658870'>like</span> <span
  m='2659000'>it</span> <span m='2659080'>did</span> <span
  m='2659190'>this</span> <span m='2659410'>morning--</span> <span
  m='2659780'>well, actually</span> <span m='2659980'>not</span> <span
  m='2660180'>this</span> <span m='2660350'>morning.</span> <span
  m='2660830'>This</span> <span m='2661020'>morning</span> <span
  m='2661260'>was</span> <span m='2661410'>great.</span> <span
  m='2662960'>Yesterday</span> <span m='2663930'>it</span> <span
  m='2664050'>was</span> <span m='2664200'>cold.</span> </p><p><span
  m='2665700'>And</span> <span m='2666310'>again,</span> <span m='2666960'>now
  I</span> <span m='2667120'>have</span> <span m='2667250'>more</span> <span
  m='2667420'>data</span> <span m='2667750'>and</span> <span
  m='2667840'>I</span> <span m='2667950'>update</span> <span
  m='2668310'>my</span> <span m='2668410'>beliefs.</span> <span m='2669000'>All
  right.</span> <span m='2669340'>You</span> <span m='2669570'>can go</span>
  <span m='2669750'>through</span> <span m='2669890'>life</span> <span
  m='2670090'>this</span> <span m='2670250'>way.</span> <span
  m='2670500'>It'll</span> <span m='2670600'>give</span> <span
  m='2670690'>you</span> <span m='2670780'>a</span> <span
  m='2670800'>headache,</span> <span m='2671100'>but</span> <span
  m='2671210'>you</span> <span m='2671280'>can</span> <span
  m='2671390'>do</span> <span m='2671530'>it.</span> <span
  m='2672810'>Now</span> <span m='2673280'>with</span> <span
  m='2673950'>clinical</span> <span m='2674270'>trials,</span> <span
  m='2674950'>the</span> <span m='2675040'>same</span> <span
  m='2675260'>thing</span> <span m='2675420'>can</span> <span
  m='2675530'>happen.</span> <span m='2676070'>Maybe</span> <span
  m='2676450'>you do</span> <span m='2676570'>a</span> <span
  m='2676620'>pilot</span> <span m='2676950'>study.</span> <span
  m='2677320'>Maybe</span> <span m='2677650'>you</span> <span
  m='2677730'>have</span> <span m='2677920'>some</span> <span
  m='2678090'>belief</span> <span m='2678430'>that</span> <span
  m='2679880'>eating</span> <span m='2681450'>almonds</span> <span
  m='2681970'>causes</span> <span m='2684930'>something,</span> <span
  m='2685970'>stomach</span> <span m='2687220'>cramps.</span> <span
  m='2688220'>Great.</span> <span m='2688970'>And</span> <span
  m='2689540'>maybe</span> <span m='2689770'>it's</span> <span
  m='2689870'>just</span> <span m='2690020'>for</span> <span
  m='2690110'>you.</span> <span m='2690940'>But</span> <span
  m='2691600'>you</span> <span m='2691730'>want</span> <span
  m='2691840'>to</span> <span m='2691890'>do</span> <span m='2691990'>a</span>
  <span m='2692050'>study</span> <span m='2692330'>about</span> <span
  m='2692570'>that.</span> </p><p><span m='2693050'>So maybe</span> <span
  m='2693350'>you know for</span> <span m='2693720'>yourself</span> <span
  m='2694120'>that eating</span> <span m='2694310'>almonds</span> <span
  m='2694720'>give</span> <span m='2694870'>you</span> <span m='2695040'>stomach
  cramps.</span> <span m='2696500'>You're</span> <span m='2697240'>at</span>
  <span m='2697400'>the</span> <span m='2697510'>Harvard</span> <span
  m='2697810'>School of</span> <span m='2697900'>Public</span> <span
  m='2698140'>Health</span> <span m='2698550'>and</span> <span
  m='2698810'>you</span> <span m='2698910'>really</span> <span
  m='2699090'>want</span> <span m='2699270'>to</span> <span
  m='2699590'>investigate</span> <span m='2700090'>this</span> <span
  m='2700250'>further,</span> <span m='2700820'>so</span> <span
  m='2700980'>you</span> <span m='2701470'>gather</span> <span
  m='2701870'>a</span> <span m='2701910'>few</span> <span
  m='2702460'>willing</span> <span m='2702700'>subjects,</span> <span
  m='2703130'>you</span> <span m='2703240'>feed</span> <span
  m='2703390'>them</span> <span m='2703520'>some</span> <span
  m='2703650'>almonds,</span> <span m='2704440'>you</span> <span
  m='2704530'>see</span> <span m='2704740'>if they</span> <span
  m='2704860'>get</span> <span m='2705020'>stomach</span> <span
  m='2705310'>cramps,</span> <span m='2705780'>how</span> <span
  m='2705890'>many</span> <span m='2706130'>of</span> <span
  m='2706210'>them.</span> <span m='2707080'>And</span> <span
  m='2707790'>maybe</span> <span m='2708430'>your</span> <span
  m='2708570'>prior</span> <span m='2708900'>ahead</span> <span m='2709170'>was
  you</span> <span m='2709400'>just</span> <span m='2709560'>kind</span> <span
  m='2709720'>of</span> <span m='2709800'>felt</span> <span
  m='2710080'>like</span> <span m='2710280'>you</span> <span m='2710410'>had
  this</span> <span m='2710490'>really</span> <span m='2710800'>strong</span>
  <span m='2711070'>belief</span> <span m='2711460'>that</span> <span
  m='2712060'>almonds</span> <span m='2712390'>cause</span> <span
  m='2712570'>stomach</span> <span m='2712730'>cramps,</span> <span
  m='2713150'>because</span> <span m='2713580'>it</span> <span
  m='2713690'>does</span> <span m='2713880'>for</span> <span
  m='2713960'>you</span> <span m='2714220'>and</span> <span
  m='2714300'>you</span> <span m='2714380'>really haven't</span> <span
  m='2714480'>even</span> <span m='2714670'>asked</span> <span
  m='2714880'>a</span> <span m='2714930'>lot</span> <span m='2715050'>of</span>
  <span m='2715110'>other</span> <span m='2715240'>people.</span> <span
  m='2715650'>So</span> <span m='2715790'>you</span> <span
  m='2715910'>might</span> <span m='2716040'>have</span> <span
  m='2716120'>a</span> <span m='2716170'>lot</span> <span m='2716470'>of</span>
  <span m='2716540'>prior</span> <span m='2716770'>probability</span> <span
  m='2717470'>on</span> <span m='2717740'>that</span> <span
  m='2717880'>hypothesis</span> <span m='2718440'>being</span> <span
  m='2718650'>true.</span> </p><p><span m='2719630'>Once</span> <span
  m='2719870'>you</span> <span m='2719970'>collect</span> <span
  m='2720390'>a</span> <span m='2720500'>few</span> <span
  m='2720660'>more</span> <span m='2720810'>people</span> <span
  m='2721060'>and</span> <span m='2721130'>maybe</span> <span
  m='2721210'>you</span> <span m='2721330'>ask</span> <span
  m='2721490'>your</span> <span m='2721580'>friends,</span> <span
  m='2722410'>maybe</span> <span m='2722830'>you</span> <span
  m='2722930'>find</span> <span m='2723170'>that</span> <span
  m='2723270'>most</span> <span m='2723510'>of</span> <span
  m='2723550'>them</span> <span m='2723690'>don't</span> <span
  m='2723870'>have</span> <span m='2724000'>the</span> <span
  m='2724070'>same</span> <span m='2724270'>problem.</span> <span
  m='2724730'>Suddenly</span> <span m='2725810'>your</span> <span
  m='2725930'>posterior</span> <span m='2726560'>belief</span> <span
  m='2727190'>changes</span> <span m='2727920'>and</span> <span
  m='2728490'>now</span> <span m='2728670'>you're</span> <span
  m='2728850'>not</span> <span m='2729010'>quite</span> <span
  m='2729230'>so</span> <span m='2729350'>convinced</span> <span
  m='2729650'>that</span> <span m='2729760'>it's</span> <span
  m='2729920'>true.</span> <span m='2730880'>And</span> <span
  m='2731050'>then,</span> <span m='2731580'>if</span> <span
  m='2731730'>you're</span> <span m='2731860'>really</span> <span
  m='2732050'>ambitious</span> <span m='2732470'>and</span> <span
  m='2732540'>you</span> <span m='2732590'>have</span> <span
  m='2732760'>a</span> <span m='2732790'>lot</span> <span m='2732940'>of</span>
  <span m='2732990'>grant</span> <span m='2733210'>money</span> <span
  m='2733930'>from</span> <span m='2734060'>the</span> <span
  m='2734160'>NIH,</span> <span m='2735010'>you</span> <span
  m='2735270'>recruit</span> <span m='2735460'>1,000</span> <span
  m='2735870'>people</span> <span m='2736510'>and</span> <span
  m='2736640'>you</span> <span m='2736720'>do</span> <span m='2736880'>a</span>
  <span m='2736950'>randomized</span> <span m='2737370'>controlled</span> <span
  m='2737730'>trial</span> <span m='2738160'>with</span> <span
  m='2738290'>placebo</span> <span m='2739020'>and</span> <span
  m='2739080'>you</span> <span m='2739170'>find</span> <span
  m='2739460'>out</span> <span m='2740410'>that</span> <span
  m='2740840'>exactly</span> <span m='2741540'>10%</span> <span
  m='2742020'>of</span> <span m='2742070'>the</span> <span
  m='2742210'>folks</span> <span m='2743760'>complain</span> <span
  m='2744210'>about</span> <span m='2745250'>the</span> <span
  m='2745370'>stomach</span> <span m='2745550'>cramps</span> <span
  m='2745815'>with</span> <span m='2746080'>almonds.</span> <span
  m='2746310'>Maybe</span> <span m='2746520'>10%</span> <span
  m='2747040'>on</span> <span m='2747170'>placebo</span> <span
  m='2747550'>also,</span> <span m='2747840'>so</span> <span
  m='2748130'>you're</span> <span m='2748230'>not</span> <span
  m='2748380'>quite</span> <span m='2748560'>sure</span> <span
  m='2748700'>what's</span> <span m='2748860'>going</span> <span
  m='2749110'>on.</span> <span m='2749360'>But</span> <span
  m='2749370'>the</span> <span m='2749450'>point</span> <span
  m='2749650'>is,</span> <span m='2750070'>you're</span> <span
  m='2750200'>getting</span> <span m='2750530'>data</span> <span
  m='2751766'>a</span> <span m='2752180'>little</span> <span
  m='2752360'>more,</span> <span m='2752670'>a little more. And</span> <span
  m='2752760'>you</span> <span m='2752860'>can</span> <span
  m='2752980'>keep</span> <span m='2753590'>incorporating</span> <span
  m='2754220'>it,</span> <span m='2754350'>updating</span> <span
  m='2755140'>your</span> <span m='2755680'>beliefs.</span> </p><p><span
  m='2757410'>So</span> <span m='2757930'>that's</span> <span
  m='2758150'>the</span> <span m='2758230'>principal.</span> <span
  m='2758810'>One</span> <span m='2759080'>last</span> <span
  m='2759300'>thing</span> <span m='2759430'>I'll</span> <span
  m='2759540'>point</span> <span m='2759750'>out</span> <span
  m='2759930'>is,</span> <span m='2760660'>what</span> <span
  m='2760940'>if</span> <span m='2761520'>you</span> <span
  m='2761620'>have</span> <span m='2761760'>a</span> <span
  m='2761820'>prior</span> <span m='2762120'>belief</span> <span
  m='2762510'>that</span> <span m='2762640'>is</span> <span
  m='2762720'>so</span> <span m='2763040'>strong,</span> <span
  m='2764810'>so</span> <span m='2764940'>you</span> <span
  m='2765080'>are</span> <span m='2765140'>so</span> <span
  m='2765530'>sure,</span> <span m='2766020'>for</span> <span
  m='2766040'>example,</span> <span m='2767210'>that</span> <span
  m='2768060'>almonds</span> <span m='2768560'>don't</span> <span
  m='2768720'>cause</span> <span m='2769210'>stomach</span> <span
  m='2769560'>pain,</span> <span m='2770730'>because</span> <span
  m='2770870'>it</span> <span m='2770940'>doesn't</span> <span
  m='2771200'>for</span> <span m='2771280'>you</span> <span
  m='2771570'>and</span> <span m='2771650'>you're</span> <span
  m='2771720'>just</span> <span m='2771870'>sure</span> <span
  m='2772090'>that</span> <span m='2772290'>that</span> <span
  m='2772400'>would</span> <span m='2772470'>be</span> <span
  m='2772570'>ridiculous,</span> <span m='2773050'>right?</span> <span
  m='2774230'>So</span> <span m='2774360'>you've</span> <span
  m='2774490'>put</span> <span m='2774650'>your</span> <span
  m='2774760'>prior</span> <span m='2775050'>probability</span> <span
  m='2775490'>at</span> <span m='2775580'>0.</span> <span m='2778740'>How</span>
  <span m='2778890'>much</span> <span m='2779090'>evidence</span> <span
  m='2779490'>will it</span> <span m='2779670'>take,</span> <span
  m='2779970'>how</span> <span m='2780040'>much</span> <span
  m='2780230'>data</span> <span m='2780480'>will</span> <span
  m='2780640'>take</span> <span m='2781490'>for</span> <span
  m='2781870'>you</span> <span m='2782020'>to</span> <span m='2782070'>be</span>
  <span m='2782180'>convinced?</span> </p><p><span m='2785280'>Infinite.</span>
  <span m='2786150'>No</span> <span m='2786710'>amount</span> <span
  m='2787280'>of</span> <span m='2787420'>data</span> <span
  m='2788460'>it's</span> <span m='2788610'>going</span> <span
  m='2788720'>to</span> <span m='2788770'>convince</span> <span
  m='2789060'>you</span> <span m='2789170'>otherwise.</span> <span
  m='2790480'>This</span> <span m='2790650'>is</span> <span
  m='2790760'>why</span> <span m='2790960'>whenever</span> <span
  m='2791550'>you</span> <span m='2791690'>do</span> <span
  m='2792200'>this</span> <span m='2792360'>kind</span> <span
  m='2792490'>of</span> <span m='2792530'>Bayesian</span> <span
  m='2792840'>Updating,</span> <span m='2793580'>it's</span> <span
  m='2793800'>generally</span> <span m='2794120'>best</span> <span
  m='2795000'>to</span> <span m='2795130'>leave</span> <span
  m='2795620'>a</span> <span m='2795710'>little</span> <span
  m='2796080'>bit</span> <span m='2796240'>of</span> <span
  m='2797020'>possibility</span> <span m='2797620'>for</span> <span
  m='2797710'>Santa</span> <span m='2797950'>Claus,</span> <span
  m='2798770'>OK.</span> <span m='2799580'>Like</span> <span
  m='2800150'>a</span> <span m='2800240'>little</span> <span
  m='2800450'>bit.</span> <span m='2801300'>Just</span> <span
  m='2801500'>so</span> <span m='2801630'>that</span> <span
  m='2802160'>should</span> <span m='2803950'>a</span> <span
  m='2804050'>fat</span> <span m='2804290'>white</span> <span
  m='2804470'>man</span> <span m='2804720'>come</span> <span
  m='2804880'>down</span> <span m='2805100'>your</span> <span
  m='2805170'>chimney</span> <span m='2806040'>and</span> <span
  m='2806170'>deliver</span> <span m='2806410'>the</span> <span
  m='2806490'>presents</span> <span m='2806860'>one</span> <span
  m='2807040'>year,</span> <span m='2808170'>you</span> <span
  m='2808280'>have</span> <span m='2808400'>a</span> <span
  m='2808440'>possibility</span> <span m='2809450'>to</span> <span
  m='2809700'>adjust.</span> </p><p><span m='2812300'>So</span> <span
  m='2813410'>those</span> <span m='2813600'>are</span> <span
  m='2813680'>some</span> <span m='2814160'>things</span> <span
  m='2814350'>to</span> <span m='2814430'>keep</span> <span
  m='2814580'>in</span> <span m='2814670'>mind.</span> <span
  m='2815340'>I</span> <span m='2815550'>think</span> <span
  m='2815740'>we've</span> <span m='2815840'>got</span> <span
  m='2816120'>one</span> <span m='2816460'>more</span> <span
  m='2817130'>board</span> <span m='2817360'>question</span> <span
  m='2817770'>that</span> <span m='2817960'>Jerry's</span> <span
  m='2818280'>going</span> <span m='2818420'>to lead.</span> </p><p><span
  m='2819860'>PROFESSOR: Right</span> <span m='2820120'>so</span> <span
  m='2822160'>it's</span> <span m='2822380'>nice</span> <span
  m='2822750'>to</span> <span m='2822870'>get</span> <span
  m='2824270'>probabilities</span> <span m='2825080'>for</span> <span
  m='2825230'>hypotheses,</span> <span m='2826020'>but</span> <span
  m='2826180'>one</span> <span m='2826380'>thing</span> <span
  m='2826590'>you</span> <span m='2826710'>also</span> <span
  m='2827090'>want</span> <span m='2827280'>to</span> <span
  m='2827350'>do</span> <span m='2828110'>is</span> <span
  m='2828300'>predict</span> <span m='2828640'>what's</span> <span
  m='2828860'>going</span> <span m='2828990'>to</span> <span
  m='2829050'>come</span> <span m='2829260'>next.</span> <span
  m='2830850'>And</span> <span m='2831000'>so</span> <span
  m='2831110'>that's</span> <span m='2831400'>what</span> <span
  m='2831570'>we</span> <span m='2831680'>call</span> <span
  m='2831970'>probabilistic</span> <span m='2832830'>prediction.</span> <span
  m='2835320'>If</span> <span m='2835590'>I</span> <span m='2836300'>pick</span>
  <span m='2836540'>one</span> <span m='2836720'>of</span> <span
  m='2836900'>the</span> <span m='2837050'>John's</span> <span
  m='2837480'>5</span> <span m='2837820'>die,</span> <span
  m='2838700'>and</span> <span m='2838950'>I'm</span> <span
  m='2839020'>about</span> <span m='2839310'>to</span> <span
  m='2839420'>roll</span> <span m='2839750'>it,</span> <span
  m='2839870'>you</span> <span m='2840020'>could</span> <span
  m='2840190'>tell</span> <span m='2840430'>me</span> <span
  m='2840600'>using</span> <span m='2840970'>the</span> <span
  m='2841070'>Law</span> <span m='2841260'>of</span> <span
  m='2841360'>Total</span> <span m='2841630'>Probability</span> <span
  m='2843200'>the</span> <span m='2843310'>probability</span> <span
  m='2843880'>that</span> <span m='2844060'>I</span> <span
  m='2844120'>get</span> <span m='2844420'>a</span> <span m='2845380'>5.</span>
  </p><p><span m='2847740'>And</span> <span m='2847900'>we've</span> <span
  m='2848060'>done</span> <span m='2848280'>that,</span> <span
  m='2848620'>we</span> <span m='2848720'>did</span> <span
  m='2848810'>that</span> <span m='2849240'>in</span> <span
  m='2849450'>the</span> <span m='2849940'>first</span> <span
  m='2850250'>unit</span> <span m='2850530'>on</span> <span
  m='2850670'>probability</span> <span m='2851270'>in</span> <span
  m='2851370'>this</span> <span m='2851570'>class.</span> <span
  m='2852890'>But</span> <span m='2853470'>suppose</span> <span
  m='2853910'>he</span> <span m='2854020'>rolls</span> <span
  m='2854420'>a</span> <span m='2854530'>5</span> <span
  m='2855140'>first.</span> <span m='2857960'>Now</span> <span
  m='2858310'>I</span> <span m='2858400'>can</span> <span
  m='2858650'>update</span> <span m='2859790'>my</span> <span
  m='2860660'>probabilities</span> <span m='2861360'>for</span> <span
  m='2861460'>which</span> <span m='2861650'>die</span> <span
  m='2862070'>it</span> <span m='2862440'>is,</span> <span m='2862540'>which is
  going</span> <span m='2862680'>to</span> <span m='2862780'>update</span> <span
  m='2863200'>my</span> <span m='2863380'>estimation</span> <span
  m='2864580'>of</span> <span m='2864740'>the</span> <span
  m='2864840'>probability</span> <span m='2865570'>of</span> <span
  m='2865680'>rolling,</span> <span m='2866550'>say</span> <span
  m='2866770'>a</span> <span m='2866850'>4</span> <span m='2868200'>on</span>
  <span m='2868340'>the</span> <span m='2868440'>next</span> <span
  m='2868730'>roll.</span> <span m='2869830'>This is what</span> <span
  m='2869960'>we'll</span> <span m='2870230'>call</span> <span
  m='2870460'>probabilistic</span> <span m='2871350'>prediction.</span> <span
  m='2871820'>We</span> <span m='2871940'>can</span> <span
  m='2872100'>predict</span> <span m='2872560'>what's</span> <span
  m='2872790'>going</span> <span m='2872940'>to</span> <span
  m='2873020'>happen</span> <span m='2873410'>next,</span> <span
  m='2874240'>at</span> <span m='2874380'>least</span> <span
  m='2874660'>with</span> <span m='2874810'>probabilities,</span> <span
  m='2876550'>based</span> <span m='2876990'>on</span> <span
  m='2878590'>the</span> <span m='2878770'>data</span> <span
  m='2879110'>that</span> <span m='2879270'>we've</span> <span
  m='2879490'>seen.</span> <span m='2879770'>We</span> <span
  m='2879950'>update</span> <span m='2881220'>our</span> <span
  m='2881420'>predictions</span> <span m='2882410'>based</span> <span
  m='2882910'>on</span> <span m='2883050'>that.</span> </p><p><span
  m='2883660'>So</span> <span m='2883830'>here's</span> <span
  m='2884550'>a</span> <span m='2884680'>set</span> <span m='2884900'>up.</span>
  <span m='2885220'>D1</span> <span m='2885420'>is</span> <span
  m='2885780'>the</span> <span m='2885870'>first</span> <span
  m='2886240'>roll.</span> <span m='2886510'>D2</span> <span
  m='2886840'>is</span> <span m='2886990'>the</span> <span
  m='2887060'>second.</span> <span m='2890840'>I'll</span> <span
  m='2891040'>do</span> <span m='2891170'>this</span> <span
  m='2891650'>example.</span> <span m='2892240'>Oh no,</span> <span
  m='2892510'>this</span> <span m='2892690'>a</span> <span
  m='2892750'>board</span> <span m='2893040'>question.</span> <span
  m='2893410'>You're</span> <span m='2893590'>going</span> <span
  m='2893740'>to</span> <span m='2893780'>do</span> <span
  m='2893930'>this.</span> <span m='2895280'>You're on</span> <span
  m='2895440'>your</span> <span m='2895590'>own</span> <span
  m='2895750'>here.</span> <span m='2896430'>So</span> <span
  m='2896630'>first,</span> <span m='2898000'>you</span> <span
  m='2898110'>don't</span> <span m='2898280'>know</span> <span
  m='2898410'>anything</span> <span m='2898860'>about</span> <span
  m='2899510'>the</span> <span m='2899660'>die</span> <span
  m='2899980'>except</span> <span m='2900450'>that 1</span> <span
  m='2901550'>of</span> <span m='2901650'>the</span> <span m='2901750'>5</span>
  <span m='2902130'>was</span> <span m='2902290'>chosen</span> <span
  m='2902700'>at</span> <span m='2902790'>random.</span> <span
  m='2903510'>What's</span> <span m='2903920'>the</span> <span
  m='2904010'>probability</span> <span m='2904820'>that</span> <span
  m='2905130'>the</span> <span m='2905470'>first</span> <span
  m='2905810'>roll</span> <span m='2905990'>will</span> <span
  m='2906130'>be</span> <span m='2906280'>a</span> <span m='2906330'>5?</span>
  </p><p><span m='2907320'>Now</span> <span m='2907480'>you've</span> <span
  m='2907640'>rolled</span> <span m='2908140'>that</span> <span
  m='2908350'>once,</span> <span m='2910470'>and</span> <span
  m='2910620'>you're</span> <span m='2910710'>going</span> <span
  m='2910810'>to</span> <span m='2910860'>roll</span> <span
  m='2911120'>again.</span> <span m='2911690'>And</span> <span
  m='2911830'>you</span> <span m='2911930'>can</span> <span
  m='2912070'>ask,</span> <span m='2912340'>well</span> <span
  m='2912540'>now</span> <span m='2912790'>I've</span> <span
  m='2913240'>seen</span> <span m='2913510'>some</span> <span
  m='2913700'>data.</span> <span m='2914030'>I</span> <span
  m='2914110'>have</span> <span m='2914280'>some</span> <span
  m='2914460'>information</span> <span m='2915100'>about</span> <span
  m='2915740'>which</span> <span m='2916180'>die</span> <span
  m='2916440'>was</span> <span m='2916670'>chosen.</span> <span
  m='2918350'>What's</span> <span m='2918590'>the</span> <span
  m='2918670'>probability</span> <span m='2919340'>that</span> <span
  m='2919530'>I'll</span> <span m='2919640'>see</span> <span
  m='2919840'>a</span> <span m='2919900'>4</span> <span m='2920560'>on</span>
  <span m='2920670'>the</span> <span m='2920760'>next</span> <span
  m='2921120'>die.</span> <span m='2921810'>So</span> <span
  m='2922000'>that's</span> <span m='2922530'>your</span> <span
  m='2922660'>job</span> <span m='2923010'>to</span> <span
  m='2923430'>find</span> <span m='2923730'>that</span> <span
  m='2924470'>for</span> <span m='2924610'>this</span> <span
  m='2924830'>problem.</span> </p><p><span m='2932545'>PROFESSOR 2: Cool,</span>
  <span m='2933020'>alright</span> <span m='2933290'>so this is</span> <span
  m='2933360'>your</span> <span m='2933460'>first</span> <span
  m='2933830'>answer?</span> </p><p><span m='2934826'>AUDIENCE: Right.</span>
  <span m='2935324'>And</span> <span m='2935822'>then,</span> <span
  m='2936320'>now we're</span> <span m='2936818'>just</span> <span
  m='2937316'>multiplying</span> <span m='2937814'>across.</span> <span
  m='2938810'>You</span> <span m='2939308'>get 0.</span> <span
  m='2943292'>1/180,</span> <span m='2947276'>1/320,</span> <span
  m='2949766'>1/740,</span> <span m='2952256'>[INAUDIBLE].</span> <span
  m='2954248'>And</span> <span m='2954746'>then</span> <span m='2956738'>add
  those up.</span> </p><p><span m='2959726'>PROFESSOR 2: Yeah,</span> <span
  m='2960250'>get out your</span> <span m='2960500'>calculator.</span>
  </p><p><span m='2962150'>What</span> <span m='2962640'>are</span> <span
  m='2962680'>you</span> <span m='2962850'>dividing</span> <span
  m='2962950'>by</span> <span m='2963310'>to</span> <span
  m='2963430'>normalize?</span> </p><p><span m='2963775'>AUDIENCE: Is
  this--</span> <span m='2964505'>I don't know.</span> </p><p><span
  m='2965660'>PROFESSOR 2: That's</span> <span m='2965870'>right.</span> <span
  m='2966480'>So</span> <span m='2966650'>this</span> <span
  m='2968430'>is,</span> <span m='2968980'>when</span> <span
  m='2969120'>you</span> <span m='2969200'>add</span> <span
  m='2969330'>these</span> <span m='2969510'>up,</span> <span
  m='2969720'>exactly</span> <span m='2970220'>the</span> <span
  m='2970300'>probability</span> <span m='2971190'>of</span> <span
  m='2971260'>the</span> <span m='2971340'>5,</span> <span
  m='2971640'>right?</span> <span m='2972380'>So</span> <span
  m='2972530'>now</span> <span m='2972670'>if</span> <span
  m='2972730'>you</span> <span m='2972810'>want</span> <span
  m='2972910'>to</span> <span m='2972950'>repeat</span> <span
  m='2973180'>this</span> <span m='2973340'>process,</span> <span
  m='2974040'>you</span> <span m='2974140'>need</span> <span
  m='2974310'>to</span> <span m='2974650'>use</span> <span
  m='2975460'>your</span> <span m='2975560'>normalized</span> <span
  m='2975840'>posterior</span> <span m='2976400'>instead</span> <span
  m='2976920'>of</span> <span m='2977130'>the</span> <span
  m='2977250'>original</span> <span m='2977540'>prior.</span> </p><p><span
  m='2977920'>AUDIENCE: That's what</span> <span m='2978373'>we were--</span>
  </p><p><span m='2978826'>PROFESSOR 2: Yeah.</span> <span
  m='2979732'>Great.</span> <span m='2981550'>Now, you just</span> <span
  m='2981690'>need</span> <span m='2981860'>to do</span> <span
  m='2982273'>division.</span> <span m='2983100'>That</span> <span
  m='2983440'>I</span> <span m='2983780'>can't</span> <span
  m='2984200'>help</span> <span m='2984360'>you</span> <span
  m='2984800'>with.</span> <span m='2986140'>Calculator.</span> <span
  m='2988780'>Division</span> <span m='2989330'>skills,</span> <span
  m='2989870'>either way.</span> </p><p><span m='2998670'>[INTERPOSING
  VOICES]</span> </p><p><span m='3014060'>AUDIENCE: Now</span> <span
  m='3014410'>this</span> <span m='3014540'>is</span> <span
  m='3014690'>the</span> <span m='3014760'>probability</span> <span
  m='3015280'>of</span> <span m='3015360'>4, or</span> <span
  m='3015750'>the</span> <span m='3015830'>probability</span> <span
  m='3016170'>of</span> <span m='3016250'>4</span> <span m='3016600'>getting
  5?</span> </p><p><span m='3018250'>PROFESSOR 2: That's right.</span> <span
  m='3021350'>So</span> <span m='3021550'>tell</span> <span
  m='3021690'>me</span> <span m='3022010'>what</span> <span
  m='3022140'>you</span> <span m='3022200'>did</span> <span
  m='3022580'>to</span> <span m='3022650'>get</span> <span
  m='3022800'>these.</span> </p><p><span m='3025700'>AUDIENCE: So this
  column</span> <span m='3026692'>[INAUDIBLE]</span> <span
  m='3028676'>which</span> <span m='3029172'>we calculated</span> <span
  m='3029668'>for,</span> <span m='3030660'>and then you</span> <span
  m='3031156'>sum it</span> <span m='3031652'>up</span> <span m='3032148'>to
  get</span> <span m='3032644'>the total</span> <span
  m='3033140'>probability</span> <span m='3033636'>of getting a 5.</span> <span
  m='3034628'>And then</span> <span m='3035124'>[INAUDIBLE]</span> <span
  m='3035620'>normalized it,</span> <span m='3036116'>and</span> <span
  m='3036612'>then</span> <span m='3037108'>took</span> <span m='3037604'>the
  new</span> <span m='3038100'>[INAUDIBLE]</span> <span m='3038596'>times</span>
  <span m='3039092'>the same--</span> </p><p><span m='3040100'>PROFESSOR 2:
  The</span> <span m='3040670'>same</span> <span m='3041000'>likelihood.</span>
  </p><p><span m='3041700'>AUDIENCE: And then you</span> <span m='3042090'>get
  the new</span> <span m='3042480'>column and then</span> <span m='3042870'>you
  add it up.</span> <span m='3044265'>[INAUDIBLE].</span> </p><p><span
  m='3046590'>PROFESSOR 2: Perfect.</span> <span m='3047300'>Now</span> <span
  m='3047450'>you</span> <span m='3047570'>said,</span> <span
  m='3048730'>just</span> <span m='3048990'>for</span> <span
  m='3049070'>the</span> <span m='3049160'>heck of it you</span> <span
  m='3049540'>normalized</span> <span m='3050000'>it,</span> <span
  m='3050070'>but</span> <span m='3050200'>it's</span> <span
  m='3050320'>actually</span> <span m='3050580'>really</span> <span
  m='3050780'>important</span> <span m='3051390'>that</span> <span
  m='3051510'>you</span> <span m='3051580'>normalize</span> <span
  m='3052040'>it,</span> <span m='3052290'>because</span> <span
  m='3052820'>if</span> <span m='3053040'>you're</span> <span
  m='3053140'>going</span> <span m='3053240'>to</span> <span
  m='3053280'>use</span> <span m='3053600'>the Law of Total</span> <span
  m='3054060'>Probably</span> <span m='3054530'>again,</span> <span
  m='3055100'>right,</span> <span m='3055460'>you've</span> <span
  m='3055530'>got</span> <span m='3055640'>to</span> <span m='3055690'>be</span>
  <span m='3055780'>working</span> <span m='3056080'>with</span> <span
  m='3056510'>a</span> <span m='3056570'>probability</span> <span
  m='3057310'>mass</span> <span m='3057580'>function,</span> <span
  m='3057960'>something</span> <span m='3058170'>that</span> <span
  m='3058530'>adds</span> <span m='3058580'>to 1</span> <span
  m='3058770'>here.</span> <span m='3059640'>If</span> <span m='3059740'>you
  didn't</span> <span m='3059870'>normalize,</span> <span
  m='3060250'>then</span> <span m='3060630'>your</span> <span
  m='3060810'>final</span> <span m='3061100'>answer</span> <span
  m='3061320'>would get</span> <span m='3061460'>multiplied</span> <span
  m='3062000'>by</span> <span m='3062110'>something,</span> <span
  m='3062520'>right?</span> <span m='3063300'>Whatever</span> <span
  m='3063530'>that</span> <span m='3063650'>normalization</span> <span
  m='3064230'>constant</span> <span m='3065000'>was,</span> <span m='3065220'>or
  its</span> <span m='3065590'>reciprocal.</span> <span
  m='3065710'>Perfect.</span> </p><p><span m='3073700'>Check these guys
  out.</span> </p><p><span m='3080110'>PROFESSOR: And</span> <span
  m='3080460'>this</span> <span m='3080630'>right</span> <span
  m='3080850'>here</span> <span m='3081160'>is</span> <span
  m='3081270'>not</span> <span m='3082710'>a</span> <span
  m='3082810'>probability,</span> <span m='3083800'>because</span> <span
  m='3084030'>it's</span> <span m='3084160'>unnormalized.</span> <span
  m='3084700'>So</span> <span m='3084850'>what</span> <span
  m='3085000'>should</span> <span m='3085140'>you</span> <span
  m='3085230'>normalize</span> <span m='3085770'>this</span> <span
  m='3085970'>by?</span> </p><p><span m='3086670'>AUDIENCE: [INAUDIBLE]</span>
  </p><p><span m='3089230'>PROFESSOR: Yeah.</span> <span m='3089920'>In</span>
  <span m='3090150'>other words,</span> <span m='3090280'>if</span> <span
  m='3090370'>you</span> <span m='3090460'>made</span> <span
  m='3090680'>a</span> <span m='3090740'>normalized</span> <span
  m='3091530'>probability</span> <span m='3092130'>here,</span> <span
  m='3092410'>it would</span> <span m='3092540'>be</span> <span
  m='3092800'>this</span> <span m='3093190'>divided</span> <span
  m='3093540'>by</span> <span m='3093660'>that,</span> <span
  m='3093960'>this</span> <span m='3094310'>divided</span> <span m='3094460'>by
  that.</span> </p><p><span m='3094810'>AUDIENCE: So all we need</span> <span
  m='3095140'>to do</span> <span m='3095260'>is divide</span> <span
  m='3095460'>this--</span> </p><p><span m='3096010'>PROFESSOR: Exactly</span>
  <span m='3096360'>right.</span> </p><p><span m='3114100'>PROFESSOR 2:
  How's</span> <span m='3114260'>it going?</span> </p><p><span
  m='3115208'>AUDIENCE: It's going fine.</span> <span m='3117580'>So
  we're</span> <span m='3117920'>just saying--</span> </p><p><span
  m='3118920'>[INTERPOSING VOICES]</span> </p><p><span m='3137860'>PROFESSOR 2:
  So, what</span> <span m='3138155'>did</span> <span m='3138450'>you</span>
  <span m='3138570'>get</span> <span m='3138770'>for</span> <span
  m='3138840'>this?</span> <span m='3139170'>How did</span> <span
  m='3139350'>you</span> <span m='3139430'>find</span> <span
  m='3139650'>it?</span> <span m='3140490'>So</span> <span
  m='3140730'>you</span> <span m='3140860'>summed</span> <span
  m='3141220'>up</span> <span m='3142300'>this,</span> <span
  m='3142640'>right?</span> <span m='3143480'>Great,</span> <span
  m='3144010'>and</span> <span m='3144200'>then</span> <span
  m='3145230'>what</span> <span m='3145630'>did you</span> <span m='3145720'>do
  next?</span> </p><p><span m='3146390'>AUDIENCE: We</span> <span m='3146705'>do
  the</span> <span m='3147020'>same thing for</span> <span m='3147375'>4.</span>
  </p><p><span m='3147730'>PROFESSOR 2: So,</span> <span
  m='3148140'>starting</span> <span m='3148670'>from</span> <span
  m='3148810'>scratch.</span> </p><p><span m='3149300'>AUDIENCE: Yeah,</span>
  <span m='3149890'>starting from scratch</span> <span m='3150350'>if you roll
  a</span> <span m='3150780'>4.</span> </p><p><span m='3151940'>AUDIENCE:
  OK.</span> <span m='3152800'>So</span> <span m='3153480'>how</span> <span
  m='3153640'>does</span> <span m='3153800'>that</span> <span
  m='3153940'>incorporated</span> <span m='3156250'>the</span> <span
  m='3156500'>fact</span> <span m='3156780'>that</span> <span
  m='3157200'>you</span> <span m='3157633'>first</span> <span
  m='3158500'>rolled</span> <span m='3158700'>a 5?</span> </p><p><span
  m='3158840'>AUDIENCE: So we're</span> <span m='3159180'>trying to</span> <span
  m='3159220'>go</span> <span m='3159350'>back</span> <span
  m='3159630'>to</span> <span m='3159790'>the</span> <span
  m='3160212'>original</span> <span m='3160634'>Bayes,</span> <span
  m='3161478'>but that</span> <span m='3161900'>didn't</span> <span
  m='3162420'>work</span> <span m='3162620'>out so well</span> <span
  m='3163040'>because</span> <span m='3163210'>we</span> <span
  m='3163310'>don't</span> <span m='3163470'>know how to</span> <span
  m='3163840'>calculate</span> <span m='3164580'>this.</span> </p><p><span
  m='3164960'>PROFESSOR 2: Exactly,</span> <span m='3165340'>all right.</span>
  <span m='3166010'>So this</span> <span m='3166140'>is</span> <span
  m='3166240'>no</span> <span m='3166420'>easier</span> <span
  m='3166740'>than</span> <span m='3166850'>that.</span> <span
  m='3167990'>So</span> <span m='3168190'>here's the idea:</span> <span
  m='3171800'>so</span> <span m='3172190'>you</span> <span
  m='3172300'>start</span> <span m='3172540'>with</span> <span
  m='3172840'>this</span> <span m='3173510'>belief, right?</span> <span
  m='3174230'>And</span> <span m='3174830'>you</span> <span
  m='3174960'>have</span> <span m='3175110'>your</span> <span
  m='3175190'>likelihood.</span> <span m='3175660'>You</span> <span
  m='3175750'>multiply</span> <span m='3176190'>them,</span> <span
  m='3176450'>Law of   Total</span> <span m='3176590'>Probability,</span> <span
  m='3176930'>and</span> <span m='3177270'>you</span> <span
  m='3177420'>get</span> <span m='3177580'>the</span> <span
  m='3177660'>probability</span> <span m='3178170'>of</span> <span
  m='3178240'>rolling a</span> <span m='3178500'>5.</span> <span
  m='3179850'>Now</span> <span m='3179990'>at</span> <span
  m='3180050'>that</span> <span m='3180270'>point,</span> <span
  m='3181310'>after</span> <span m='3181420'>you've</span> <span
  m='3181640'>rolled</span> <span m='3182116'>this 5,</span> <span
  m='3183070'>your</span> <span m='3183210'>beliefs</span> <span
  m='3183570'>have</span> <span m='3183700'>changed</span> <span
  m='3184500'>based</span> <span m='3184780'>on</span> <span
  m='3184870'>that</span> <span m='3185070'>about</span> <span
  m='3185570'>the</span> <span m='3185680'>probability</span> <span
  m='3186300'>that</span> <span m='3186410'>you</span> <span
  m='3186490'>have</span> <span m='3186680'>each</span> <span
  m='3187010'>of</span> <span m='3187100'>the</span> <span m='3187190'>5</span>
  <span m='3187420'>dice.</span> <span m='3188370'>So</span> <span
  m='3188550'>if</span> <span m='3188630'>we</span> <span
  m='3188730'>take</span> <span m='3189250'>that</span> <span m='3190200'>and
  you</span> <span m='3190390'>use</span> <span m='3190690'>that</span> <span
  m='3191160'>as</span> <span m='3191250'>your</span> <span
  m='3191610'>prior</span> <span m='3192500'>here,</span> <span
  m='3192990'>then</span> <span m='3193140'>the</span> <span
  m='3193230'>likelihood,</span> <span m='3194050'>multiply</span> <span
  m='3194760'>and</span> <span m='3194930'>sum,</span> <span
  m='3196320'>that</span> <span m='3196780'>should</span> <span
  m='3196940'>give</span> <span m='3197080'>you--</span> </p><p><span
  m='3198770'>AUDIENCE: I like that.</span> </p><p><span m='3199220'>PROFESSOR
  2: OK?</span> </p><p><span m='3200130'>AUDIENCE: Oh,</span> <span
  m='3200250'>but now we</span> <span m='3200340'>have decimals.</span>
  </p><p><span m='3202270'>AUDIENCE: Now</span> <span m='3202740'>you
  have</span> <span m='3202790'>decimals.</span> <span m='3203190'>I
  can't</span> <span m='3203660'>make</span> <span m='3203890'>your life
  too</span> <span m='3204170'>easy.</span> </p><p><span m='3211427'>AUDIENCE:
  Use these.</span> </p><p><span m='3215430'>PROFESSOR: Right,</span> <span
  m='3216000'>so</span> <span m='3216180'>you</span> <span
  m='3216330'>multiply</span> <span m='3216790'>this</span> <span
  m='3217750'>number</span> <span m='3218010'>by</span> <span
  m='3218190'>this,</span> <span m='3218920'>this</span> <span
  m='3219160'>number</span> <span m='3219390'>by</span> <span
  m='3219540'>this.</span> <span m='3220320'>So in the end,</span> <span
  m='3220470'>you'll get</span> <span m='3220900'>all of</span> <span
  m='3221250'>these</span> <span m='3221500'>numbers</span> <span
  m='3221900'>except</span> <span m='3222170'>they're</span> <span
  m='3222310'>all</span> <span m='3222440'>multiplied</span> <span
  m='3223010'>by,</span> <span m='3223210'>divided</span> <span
  m='3223620'>by.</span> <span m='3224440'>So</span> <span
  m='3224600'>you</span> <span m='3224740'>should</span> <span
  m='3224940'>divide</span> <span m='3225310'>this</span> <span
  m='3225590'>by--</span> <span m='3226640'>to</span> <span
  m='3226760'>get</span> <span m='3226900'>a</span> <span
  m='3226950'>probability.</span> <span m='3228540'>That</span> <span
  m='3228680'>make</span> <span m='3228850'>sense?</span> <span
  m='3230940'>So</span> <span m='3231090'>you</span> <span
  m='3231200'>have</span> <span m='3231360'>to</span> <span
  m='3231470'>be</span> <span m='3231610'>careful</span> <span
  m='3231990'>for</span> <span m='3234030'>figuring</span> <span
  m='3234640'>out</span> <span m='3235010'>probabilities</span> <span
  m='3235670'>of</span> <span m='3235730'>hypotheses,</span> <span
  m='3237140'>we</span> <span m='3237280'>can</span> <span
  m='3237420'>avoid</span> <span m='3237790'>using</span> <span m='3238220'>the
  unnormalized.</span> <span m='3239760'>We</span> <span
  m='3240065'>don't</span> <span m='3240370'>have</span> <span
  m='3240560'>to</span> <span m='3240650'>keep</span> <span
  m='3240860'>normalizing.</span> <span m='3241450'>But</span> <span
  m='3242300'>when</span> <span m='3242410'>you</span> <span
  m='3242490'>want</span> <span m='3242600'>to</span> <span
  m='3242640'>do</span> <span m='3242760'>posterior</span> <span
  m='3243370'>prediction,</span> <span m='3243890'>you</span> <span
  m='3244040'>want</span> <span m='3244210'>real</span> <span
  m='3244770'>probabilities</span> <span m='3245620'>of</span> <span
  m='3245730'>data.</span> <span m='3247280'>So</span> <span
  m='3247440'>you're</span> <span m='3248250'>going</span> <span
  m='3248370'>to</span> <span m='3248410'>have</span> <span
  m='3248510'>to</span> <span m='3248630'>normalize</span> <span
  m='3249280'>these</span> <span m='3249500'>numbers</span> <span
  m='3249910'>at</span> <span m='3249980'>some point.</span> <span
  m='3251700'>Either</span> <span m='3252010'>first</span> <span
  m='3252480'>or</span> <span m='3252990'>at</span> <span m='3253110'>the</span>
  <span m='3253260'>end.</span> <span m='3254050'>It's</span> <span
  m='3254130'>probably,</span> <span m='3254400'>if you're</span> <span
  m='3254610'>going to</span> <span m='3254670'>do</span> <span m='3254810'>it
  a</span> <span m='3254890'>lot,</span> <span m='3255300'>easier</span> <span
  m='3255670'>to</span> <span m='3255850'>just keep doing it.</span>
  </p><p><span m='3256345'>AUDIENCE:  OK, Thanks.</span> </p><p><span
  m='3270700'>AUDIENCE: How are we doing?</span> </p><p><span
  m='3272210'>PROFESSOR: You</span> <span m='3272620'>tell</span> <span
  m='3272810'>me.</span> <span m='3276090'>It's</span> <span
  m='3276340'>a</span> <span m='3276400'>beautiful</span> <span
  m='3276810'>use</span> <span m='3277010'>of</span> <span
  m='3277100'>color.</span> </p><p><span m='3280740'>[INTERPOSING VOICES]</span>
  </p><p><span m='3288860'>PROFESSOR: So</span> <span m='3289040'>is</span>
  <span m='3289140'>this</span> <span m='3289690'>normalized</span> <span
  m='3290300'>or</span> <span m='3290400'>not</span> <span
  m='3290610'>normalized?</span> </p><p><span m='3290860'>AUDIENCE: This is
  normalized.</span> </p><p><span m='3291980'>PROFESSOR: Normalized.</span>
  <span m='3292240'>Good,</span> <span m='3292470'>because</span> <span
  m='3292660'>you</span> <span m='3292790'>are</span> <span
  m='3292950'>real</span> <span m='3293170'>probabilities</span> <span
  m='3293570'>there.</span> <span m='3294960'>Yes,</span> <span
  m='3295310'>thank</span> <span m='3295520'>you.</span> </p><p><span
  m='3295670'>AUDIENCE: [INAUDIBLE]</span> </p><p><span m='3300107'>AUDIENCE:
  And so then</span> <span m='3300600'>we multiply by</span> <span
  m='3301093'>what are the likelihoods.</span> </p><p><span
  m='3303400'>PROFESSOR: Yeah.</span> </p><p><span m='3304234'>AUDIENCE:
  [INAUDIBLE]</span> </p><p><span m='3307200'>PROFESSOR: And</span> <span
  m='3307420'>now</span> <span m='3307520'>you're</span> <span m='3307700'>going
  to</span> <span m='3307750'>sum it up.</span> </p><p><span
  m='3308520'>AUDIENCE: Yeah.</span> </p><p><span m='3309452'>PROFESSOR: That's
  perfect.</span> </p><p><span m='3310850'>AUDIENCE: Way to go Caitlin!</span>
  </p><p><span m='3312720'>PROFESSOR: Because</span> <span
  m='3312840'>the</span> <span m='3313030'>Law</span> <span
  m='3313390'>of</span> <span m='3313430'>Total</span> <span
  m='3313680'>Probabilities</span> <span m='3314410'>says</span> <span
  m='3314560'>multiply</span> <span m='3315020'>this</span> <span
  m='3315350'>by</span> <span m='3315480'>this.</span> <span
  m='3316280'>That's</span> <span m='3316470'>just</span> <span
  m='3316620'>what</span> <span m='3316710'>you</span> <span
  m='3316880'>did</span> <span m='3317060'>with</span> <span
  m='3317230'>the</span> <span m='3317330'>trees,</span> <span m='3317710'>do
  you</span> <span m='3317850'>see</span> <span m='3318050'>the</span> <span
  m='3318280'>trees</span> <span m='3318550'>when</span> <span
  m='3318700'>I</span> <span m='3318730'>wave</span> <span m='3318950'>my</span>
  <span m='3319070'>hands?</span> <span m='3324470'>Beautiful.</span>
  </p><p><span m='3324952'>AUDIENCE: [INAUDIBLE]</span> </p><p><span
  m='3332182'>AUDIENCE: Our new prior</span> <span m='3332670'>is</span> <span
  m='3332935'>given</span> <span m='3333470'>the</span> <span m='3333735'>data
  we had before.</span> </p><p><span m='3334700'>PROFESSOR: Yes.</span> <span
  m='3340210'>That's good.</span> </p><p><span m='3342182'>PROFESSOR 2: You're
  adding them up?</span> <span m='3344880'>OK,</span> <span
  m='3345330'>so</span> <span m='3345650'>that looks</span> <span
  m='3345810'>right.</span> <span m='3349050'>So</span> <span
  m='3350110'>let's</span> <span m='3350330'>think,</span> <span
  m='3350910'>how</span> <span m='3350960'>does</span> <span
  m='3351100'>this</span> <span m='3351270'>number</span> <span
  m='3351530'>compare</span> <span m='3352780'>to</span> <span
  m='3352930'>what</span> <span m='3353070'>you</span> <span
  m='3353170'>would</span> <span m='3353250'>have,</span> <span
  m='3353410'>if</span> <span m='3353520'>you</span> <span
  m='3353600'>didn't</span> <span m='3353900'>know</span> <span m='3354400'>this
  other</span> <span m='3354740'>information?</span> <span m='3355230'>So</span>
  <span m='3355310'>suppose</span> <span m='3355870'>you knew</span> <span
  m='3356070'>nothing</span> <span m='3356390'>going</span> <span
  m='3356890'>in,</span> <span m='3359250'>do you</span> <span
  m='3359430'>think</span> <span m='3359640'>that</span> <span
  m='3361230'>the</span> <span m='3361330'>fact</span> <span
  m='3361550'>that</span> <span m='3361660'>you</span> <span
  m='3361800'>rolled</span> <span m='3361900'>a</span> <span
  m='3361980'>5</span> <span m='3362420'>the</span> <span
  m='3362580'>first</span> <span m='3362840'>time</span> <span
  m='3363480'>makes</span> <span m='3363730'>it</span> <span
  m='3363820'>more</span> <span m='3364030'>or</span> <span
  m='3364050'>less</span> <span m='3364250'>likely</span> <span m='3364650'>that
  you</span> <span m='3364710'>roll a</span> <span m='3364930'>4</span> <span
  m='3365350'>the second time.</span> </p><p><span m='3365840'>AUDIENCE: It
  should be less likely.</span> </p><p><span m='3367800'>PROFESSOR 2: Is
  it</span> <span m='3368180'>less</span> <span m='3368440'>likely?</span>
  </p><p><span m='3368620'>AUDIENCE: Because</span> <span m='3368790'>you</span>
  <span m='3369080'>get</span> <span m='3369290'>rid</span> <span
  m='3369490'>of</span> <span m='3369680'>the 4--</span> <span
  m='3370580'>the</span> <span m='3371030'>die</span> <span m='3371480'>has only
  4 sides.</span> </p><p><span m='3373280'>PROFESSOR 2: So</span> <span
  m='3373460'>it</span> <span m='3373530'>might</span> <span
  m='3373700'>make</span> <span m='3373860'>you</span> <span
  m='3373930'>go</span> <span m='3374050'>down,</span> <span
  m='3374460'>right?</span> <span m='3375370'>On</span> <span
  m='3375440'>the</span> <span m='3375530'>other</span> <span
  m='3375700'>hand,</span> <span m='3376220'>you're</span> <span
  m='3376340'>going</span> <span m='3376430'>to</span> <span
  m='3376470'>give</span> <span m='3376590'>more</span> <span
  m='3376790'>probability</span> <span m='3377430'>to</span> <span
  m='3377640'>the 6-sided,</span> <span m='3378900'>let's</span> <span
  m='3379100'>say</span> <span m='3379270'>that,</span> <span
  m='3379800'>than</span> <span m='3380300'>it</span> <span
  m='3380510'>had</span> <span m='3380660'>originally. So they're sort of</span>
  <span m='3380710'>competing</span> <span m='3381170'>forces.</span> <span
  m='3382160'>So</span> <span m='3382430'>I'm actually</span> <span
  m='3382680'>not sure.</span> <span m='3383200'>I'm</span> <span
  m='3383730'>not</span> <span m='3383980'>actually</span> <span
  m='3384330'>sure</span> <span m='3384600'>which</span> <span
  m='3384790'>is</span> <span m='3384870'>the</span> <span
  m='3384940'>right</span> <span m='3385080'>answer.</span> <span
  m='3385520'>But</span> <span m='3385930'>anyway, it's</span> <span
  m='3386300'>something</span> <span m='3386570'>you</span> <span
  m='3386650'>can</span> <span m='3386760'>easily</span> <span
  m='3387030'>check</span> <span m='3387260'>or compute.</span> </p><p><span
  m='3390980'>PROFESSOR: This</span> <span m='3391130'>is</span> <span
  m='3391210'>a</span> <span m='3391300'>standard</span> <span
  m='3391900'>day.</span> <span m='3392120'>We</span> <span
  m='3392320'>always</span> <span m='3392760'>finish</span> <span
  m='3393090'>ahead</span> <span m='3393280'>of</span> <span
  m='3393390'>time.</span> <span m='3398480'>I</span> <span
  m='3398810'>don't</span> <span m='3398960'>need</span> <span
  m='3399130'>that</span> <span m='3399410'>right</span> <span
  m='3399560'>here.</span> <span m='3406020'>Like</span> <span
  m='3406260'>with</span> <span m='3406540'>all the</span> <span
  m='3406690'>other</span> <span m='3406890'>answers</span> <span
  m='3407220'>today,</span> <span m='3408140'>we'll</span> <span
  m='3408350'>use</span> <span m='3408590'>the</span> <span
  m='3408990'>screens</span> <span m='3409580'>to</span> <span
  m='3411240'>show</span> <span m='3411510'>the</span> <span
  m='3411630'>table.</span> <span m='3414850'>So</span> <span m='3415100'>when
  we</span> <span m='3415220'>go</span> <span m='3415380'>through</span> <span
  m='3415680'>it,</span> <span m='3416340'>we</span> <span m='3416490'>do</span>
  <span m='3417110'>the</span> <span m='3417210'>usual</span> <span
  m='3417670'>thing</span> <span m='3417920'>we</span> <span
  m='3418040'>did</span> <span m='3418210'>before.</span> <span
  m='3418540'>We</span> <span m='3418660'>started</span> <span
  m='3419070'>with</span> <span m='3419190'>a</span> <span m='3419290'>5,</span>
  <span m='3419800'>so</span> <span m='3419950'>we'll</span> <span
  m='3420120'>update</span> <span m='3422030'>our</span> <span
  m='3422380'>probabilities</span> <span m='3423160'>of</span> <span
  m='3423260'>the</span> <span m='3423350'>hypotheses</span> <span
  m='3424820'>based</span> <span m='3425180'>on</span> <span
  m='3425300'>that</span> <span m='3425530'>5.</span> <span
  m='3425860'>So</span> <span m='3425990'>that's</span> <span
  m='3426270'>the</span> <span m='3426850'>first</span> <span
  m='3427710'>column</span> <span m='3428080'>is</span> <span
  m='3428240'>the</span> <span m='3428290'>prior,</span> <span
  m='3428780'>then</span> <span m='3428970'>the</span> <span
  m='3429060'>likelihood</span> <span m='3429650'>of</span> <span
  m='3429740'>getting</span> <span m='3430030'>a</span> <span
  m='3430100'>5,</span> <span m='3431720'>which</span> <span
  m='3432260'>is</span> <span m='3432370'>0</span> <span m='3432860'>if</span>
  <span m='3432940'>you</span> <span m='3433010'>have</span> <span
  m='3433110'>the</span> <span m='3433210'>4-sided</span> <span
  m='3433800'>die:</span> <span m='3433980'>1/6,</span> <span
  m='3434480'>1/8,</span> <span m='3434680'>1/12</span> <span
  m='3435400'>and</span> <span m='3435500'>1/20.</span> </p><p><span
  m='3436850'>We</span> <span m='3436990'>get</span> <span m='3437140'>our
  unnormalized</span> <span m='3438080'>posterior.</span> <span
  m='3438810'>And</span> <span m='3438960'>then</span> <span
  m='3439100'>in</span> <span m='3439180'>this</span> <span
  m='3439380'>table,</span> <span m='3440140'>I</span> <span
  m='3440260'>actually</span> <span m='3440580'>got</span> <span
  m='3440800'>the</span> <span m='3440910'>normalized</span> <span
  m='3441530'>posterior,</span> <span m='3442090'>because</span> <span
  m='3442370'>when</span> <span m='3442480'>you're</span> <span
  m='3442590'>computing</span> <span m='3443500'>predictive</span> <span
  m='3444080'>probabilities,</span> <span m='3445570'>you</span> <span
  m='3445730'>need</span> <span m='3446130'>to</span> <span
  m='3446220'>use</span> <span m='3446460'>normalized</span> <span
  m='3447090'>probabilities.</span> <span m='3447790'>They</span> <span
  m='3447880'>should</span> <span m='3448100'>be</span> <span
  m='3448240'>true</span> <span m='3448460'>probabilities.</span> <span
  m='3450430'>So</span> <span m='3450670'>we</span> <span m='3451620'>use</span>
  <span m='3451980'>this</span> <span m='3452950'>column</span> <span
  m='3453320'>here</span> <span m='3453590'>of</span> <span
  m='3453690'>the</span> <span m='3454690'>posterior</span> <span
  m='3455260'>probability.</span> <span m='3455750'>There's</span> <span
  m='3456070'>different</span> <span m='3456400'>orders</span> <span
  m='3456820'>you</span> <span m='3456940'>could</span> <span
  m='3457110'>do</span> <span m='3457250'>this</span> <span
  m='3457440'>calculation.</span> <span m='3458160'>I</span> <span
  m='3458220'>think</span> <span m='3458480'>this</span> <span
  m='3458710'>is</span> <span m='3459450'>one</span> <span m='3459630'>of</span>
  <span m='3459700'>the</span> <span m='3459800'>straightforward</span> <span
  m='3460510'>ones.</span> </p><p><span m='3462700'>Then</span> <span
  m='3463230'>we</span> <span m='3463490'>look</span> <span
  m='3463820'>at</span> <span m='3463920'>the</span> <span
  m='3464040'>likelihood</span> <span m='3467470'>of</span> <span
  m='3467820'>D2</span> <span m='3469000'>in</span> <span m='3469170'>the</span>
  <span m='3469270'>next</span> <span m='3469590'>column.</span> <span
  m='3470400'>Now</span> <span m='3470500'>I</span> <span m='3470580'>put</span>
  <span m='3470780'>a</span> <span m='3470830'>star</span> <span
  m='3471400'>for</span> <span m='3471750'>H4</span> <span
  m='3472000'>because</span> <span m='3472310'>there's</span> <span
  m='3472500'>no</span> <span m='3472700'>way</span> <span
  m='3472980'>you</span> <span m='3473130'>could</span> <span
  m='3473320'>get</span> <span m='3475210'>a</span> <span
  m='3475320'>probability</span> <span m='3476060'>there</span> <span
  m='3476990'>if</span> <span m='3477300'>you</span> <span
  m='3477460'>have</span> <span m='3478050'>D1</span> <span
  m='3478335'>and</span> <span m='3478620'>D2.</span> <span
  m='3479180'>If</span> <span m='3479530'>I had</span> <span
  m='3479710'>left</span> <span m='3480050'>off</span> <span m='3480290'>the
  D1,</span> <span m='3480860'>which</span> <span m='3481060'>most</span> <span
  m='3481340'>people</span> <span m='3481650'>did</span> <span
  m='3481880'>and</span> <span m='3481950'>which</span> <span m='3482160'>is
  OK</span> <span m='3482280'>because</span> <span m='3483080'>of</span> <span
  m='3483760'>the</span> <span m='3483920'>independence</span> <span
  m='3484580'>John</span> <span m='3484860'>talked</span> <span
  m='3485160'>about,</span> <span m='3485440'>given</span> <span
  m='3485710'>the</span> <span m='3485780'>hypothesis</span> <span
  m='3487100'>the</span> <span m='3487240'>rolls</span> <span
  m='3487560'>are</span> <span m='3487660'>independent,</span> <span
  m='3488650'>I</span> <span m='3488780'>would</span> <span
  m='3488950'>have</span> <span m='3489040'>had</span> <span
  m='3489220'>a</span> <span m='3489300'>1/4</span> <span
  m='3489910'>where</span> <span m='3490050'>I</span> <span
  m='3490100'>have</span> <span m='3490310'>the</span> <span
  m='3490400'>star.</span> <span m='3491230'>But</span> <span
  m='3491400'>I'm</span> <span m='3491480'>going</span> <span
  m='3491560'>to</span> <span m='3491600'>multiply it</span> <span
  m='3492080'>by</span> <span m='3492260'>0</span> <span
  m='3492690'>anyway,</span> <span m='3494290'>so</span> <span
  m='3494530'>who</span> <span m='3494660'>cares.</span> </p><p><span
  m='3494990'>So</span> <span m='3495140'>I</span> <span m='3495240'>have</span>
  <span m='3496060'>my</span> <span m='3496960'>new</span> <span
  m='3497230'>priors--</span> <span m='3498810'>excuse me,</span> <span
  m='3499580'>my</span> <span m='3499730'>new</span> <span
  m='3499900'>likelihoods</span> <span m='3501010'>for</span> <span
  m='3501180'>the</span> <span m='3501290'>second</span> <span
  m='3501720'>bit</span> <span m='3501900'>of</span> <span
  m='3501990'>data,</span> <span m='3503210'>which</span> <span
  m='3503450'>are</span> <span m='3503520'>the</span> <span
  m='3503640'>same</span> <span m='3503960'>as</span> <span
  m='3504080'>the</span> <span m='3504200'>old</span> <span
  m='3504370'>ones:</span> <span m='3504580'>1/6,</span> <span
  m='3505060'>1/8,</span> <span m='3505480'>1/12,</span> <span
  m='3505970'>1/20.</span> <span m='3507060'>Now</span> <span
  m='3507170'>my</span> <span m='3507330'>total</span> <span
  m='3507680'>probability</span> <span m='3508530'>is</span> <span
  m='3508740'>done</span> <span m='3509410'>the</span> <span
  m='3509520'>same</span> <span m='3509810'>way.</span> <span
  m='3510000'>You</span> <span m='3510110'>multiply</span> <span
  m='3511330'>in</span> <span m='3511880'>this</span> <span
  m='3512170'>new</span> <span m='3512330'>language</span> <span
  m='3512830'>posterior</span> <span m='3513200'>1,</span> <span
  m='3513960'>which</span> <span m='3514210'>is</span> <span
  m='3514320'>your</span> <span m='3514480'>prior</span> <span
  m='3515810'>for</span> <span m='3515980'>likelihood 2,</span> <span
  m='3517610'>times</span> <span m='3517910'>likelihood</span> <span
  m='3518490'>2</span> <span m='3519430'>and</span> <span m='3519620'>sum</span>
  <span m='3519910'>them</span> <span m='3520100'>up,</span> <span
  m='3521110'>and</span> <span m='3521290'>I</span> <span m='3521360'>get</span>
  <span m='3521640'>this</span> <span m='3521850'>last</span> <span
  m='3522310'>column.</span> </p><p><span m='3527720'>So</span> <span
  m='3527900'>again,</span> <span m='3528430'>once</span> <span
  m='3528810'>I</span> <span m='3528930'>have</span> <span m='3529280'>my</span>
  <span m='3529470'>new,</span> <span m='3530880'>my</span> <span
  m='3531040'>posterior</span> <span m='3531730'>for</span> <span
  m='3531890'>the</span> <span m='3532000'>first</span> <span
  m='3532300'>bit</span> <span m='3532440'>of</span> <span
  m='3532530'>data,</span> <span m='3532820'>I</span> <span
  m='3532940'>can</span> <span m='3533150'>use</span> <span
  m='3533470'>that</span> <span m='3534250'>in</span> <span
  m='3534410'>the</span> <span m='3534510'>Law</span> <span
  m='3534760'>of</span> <span m='3534870'>Total</span> <span
  m='3535170'>Probability</span> <span m='3536210'>to</span> <span
  m='3536370'>make</span> <span m='3536600'>a</span> <span
  m='3536660'>prediction.</span> <span m='3537920'>So</span> <span
  m='3538030'>what's</span> <span m='3538250'>happened</span> <span
  m='3538640'>right</span> <span m='3538850'>here?</span> <span
  m='3539000'>What's</span> <span m='3539370'>become</span> <span
  m='3539730'>more</span> <span m='3539930'>likely?</span> <span
  m='3545120'>This</span> <span m='3545420'>0.124</span> <span
  m='3548290'>seems</span> <span m='3548660'>a</span> <span
  m='3548740'>little</span> <span m='3548960'>bit</span> <span
  m='3549670'>larger</span> <span m='3550240'>than</span> <span
  m='3550450'>I</span> <span m='3550510'>would</span> <span
  m='3550670'>have</span> <span m='3550800'>guessed</span> <span
  m='3551560'>ahead</span> <span m='3551890'>of</span> <span
  m='3552010'>time.</span> <span m='3555790'>What's</span> <span
  m='3556030'>happened</span> <span m='3556370'>with</span> <span
  m='3556540'>rolling</span> <span m='3556910'>a</span> <span
  m='3556960'>5</span> <span m='3557380'>and</span> <span
  m='3557470'>then</span> <span m='3557590'>a</span> <span m='3557670'>4</span>
  <span m='3558100'>to</span> <span m='3558230'>make</span> <span
  m='3558430'>that</span> <span m='3558550'>a</span> <span
  m='3558610'>little</span> <span m='3558810'>bit</span> <span
  m='3558990'>bigger?</span> <span m='3565620'>Any</span> <span
  m='3565840'>ideas?</span> </p><p><span m='3573700'>AUDIENCE: When</span> <span
  m='3574570'>you roll</span> <span m='3574840'>a</span> <span m='3575290'>5
  first,</span> <span m='3575340'>it increases</span> <span
  m='3575818'>the</span> <span m='3576296'>probability</span> <span
  m='3576774'>that it's</span> <span m='3577252'>one of the</span> <span
  m='3577730'>lower</span> <span m='3578490'>dice.</span> </p><p><span
  m='3579030'>PROFESSOR: Excellent.</span> </p><p><span m='3579710'>AUDIENCE:
  So</span> <span m='3580177'>then</span> <span m='3580644'>it makes</span>
  <span m='3581111'>it more likely</span> <span m='3581578'>that you'll get a
  4.</span> </p><p><span m='3583450'>PROFESSOR: Excellent.</span> <span
  m='3583800'>That's</span> <span m='3584360'>what</span> <span
  m='3584550'>I</span> <span m='3584650'>would</span> <span
  m='3584850'>think</span> <span m='3585070'>too.</span> <span
  m='3585850'>Seeing</span> <span m='3586180'>a</span> <span
  m='3586290'>5--</span> <span m='3586800'>a</span> <span m='3587090'>4,</span>
  <span m='3587650'>what</span> <span m='3587840'>did</span> <span
  m='3587980'>roll first?</span> <span m='3588400'>The</span> <span
  m='3588490'>5--</span> <span m='3589480'>makes</span> <span
  m='3589820'>the</span> <span m='3589930'>smaller</span> <span
  m='3590490'>die</span> <span m='3590750'>more</span> <span
  m='3590970'>likely.</span> <span m='3591820'>If</span> <span
  m='3592020'>the</span> <span m='3592110'>smaller</span> <span
  m='3592530'>die</span> <span m='3592780'>is</span> <span
  m='3592920'>more</span> <span m='3593090'>likely,</span> <span
  m='3593540'>then</span> <span m='3593710'>you're</span> <span
  m='3593830'>more</span> <span m='3594060'>likely</span> <span
  m='3594540'>to</span> <span m='3594720'>roll</span> <span m='3596220'>a</span>
  <span m='3596340'>4</span> <span m='3596740'>and</span> <span m='3596840'>a
  5.</span> <span m='3597170'>For</span> <span m='3597420'>instance,</span>
  <span m='3597560'>if</span> <span m='3597650'>I</span> <span
  m='3597750'>had</span> <span m='3597940'>the</span> <span
  m='3598030'>6-sided</span> <span m='3598910'>die,</span> <span
  m='3600780'>what's</span> <span m='3601000'>the</span> <span
  m='3601080'>probability</span> <span m='3601690'>I'd</span> <span
  m='3602060'>roll a</span> <span m='3602150'>4</span> <span m='3602450'>and
  a</span> <span m='3602550'>5</span> <span m='3602960'>with</span> <span
  m='3603120'>the</span> <span m='3603180'>6-sided</span> <span
  m='3603770'>die?</span> <span m='3607520'>1</span> <span m='3608080'>in</span>
  <span m='3608200'>36</span> <span m='3608940'>which</span> <span
  m='3609190'>is</span> <span m='3609360'>about</span> <span
  m='3609690'>3%.</span> <span m='3611030'>So</span> <span
  m='3611190'>this</span> <span m='3611350'>doesn't</span> <span
  m='3611630'>get</span> <span m='3611750'>up</span> <span m='3611890'>to</span>
  <span m='3611990'>3%,</span> <span m='3612710'>but</span> <span
  m='3612840'>it's</span> <span m='3613010'>a</span> <span
  m='3613080'>little</span> <span m='3613300'>bigger</span> <span
  m='3613660'>than</span> <span m='3614300'>if</span> <span m='3614540'>I</span>
  <span m='3614640'>had</span> <span m='3614790'>the</span> <span
  m='3614860'>20-sided</span> <span m='3615610'>die</span> <span
  m='3615850'>where</span> <span m='3616090'>would</span> <span
  m='3616250'>be--</span> <span m='3616440'>what's</span> <span
  m='3616790'>1/400.</span> </p><p><span m='3619045'>PROFESSOR 2: Very
  small.</span> </p><p><span m='3620380'>PROFESSOR: Small,</span> <span
  m='3620940'>John</span> <span m='3621260'>says it's</span> <span
  m='3621480'>small.</span> </p><p><span m='3623030'>PROFESSOR 2: So,</span>
  <span m='3623900'>this</span> <span m='3624090'>is</span> <span
  m='3624210'>one</span> <span m='3624360'>argument</span> <span
  m='3624660'>you</span> <span m='3624810'>can</span> <span
  m='3624950'>make,</span> <span m='3625300'>right?</span> <span
  m='3625580'>That</span> <span m='3625770'>ruling</span> <span
  m='3626190'>the</span> <span m='3626510'>5</span> <span
  m='3626790'>makes</span> <span m='3627690'>it</span> <span
  m='3627760'>likely</span> <span m='3628100'>that</span> <span
  m='3628230'>it's</span> <span m='3628380'>a</span> <span
  m='3628640'>smaller</span> <span m='3629090'>die,</span> <span
  m='3630470'>and</span> <span m='3630610'>therefore</span> <span
  m='3630920'>more</span> <span m='3631110'>likely</span> <span
  m='3631460'>to</span> <span m='3631550'>roll</span> <span m='3631750'>a</span>
  <span m='3631950'>4 next.</span> <span m='3632290'>But</span> <span
  m='3633320'>is</span> <span m='3633450'>there</span> <span
  m='3633550'>another</span> <span m='3633810'>argue</span> <span
  m='3634010'>that</span> <span m='3634130'>you</span> <span
  m='3634380'>can</span> <span m='3634520'>make</span> <span
  m='3634800'>for</span> <span m='3634910'>why</span> <span
  m='3635080'>maybe</span> <span m='3636020'>rolling</span> <span
  m='3636250'>the</span> <span m='3636330'>5</span> <span
  m='3637260'>would</span> <span m='3637370'>have</span> <span
  m='3637470'>the</span> <span m='3637570'>opposite</span> <span
  m='3637910'>effect?</span> <span m='3638300'>It</span> <span
  m='3638390'>might</span> <span m='3638800'>make</span> <span
  m='3639040'>it</span> <span m='3639160'>less</span> <span
  m='3639410'>likely</span> <span m='3639690'>to</span> <span
  m='3639760'>roll</span> <span m='3639970'>a</span> <span m='3640170'>4
  next?</span> </p><p><span m='3642910'>AUDIENCE: My initial</span> <span
  m='3643185'>thought</span> <span m='3643460'>was</span> <span m='3644800'>if
  you</span> <span m='3644900'>roll</span> <span m='3645250'>a</span> <span
  m='3645700'>5, you know</span> <span m='3645930'>it's</span> <span
  m='3646120'>not</span> <span m='3646320'>the</span> <span
  m='3646410'>4-sided</span> <span m='3646730'>die.</span> <span
  m='3647950'>And</span> <span m='3648270'>that's your</span> <span
  m='3648590'>die</span> <span m='3649720'>that</span> <span
  m='3649930'>you're</span> <span m='3650030'>most</span> <span
  m='3650380'>likely</span> <span m='3651020'>to</span> <span
  m='3651070'>roll</span> <span m='3651360'>for.</span> </p><p><span
  m='3652430'>PROFESSOR 2: That's</span> <span m='3652650'>right.</span> <span
  m='3653290'>So</span> <span m='3653990'>I'm</span> <span
  m='3654110'>not</span> <span m='3654300'>as</span> <span m='3654340'>sure 
  as</span> <span m='3654610'>you</span> <span m='3655040'>as</span> <span
  m='3655240'>to</span> <span m='3655360'>whether</span> <span
  m='3655600'>this</span> <span m='3655800'>goes</span> <span
  m='3656180'>up</span> <span m='3656350'>or</span> <span
  m='3656430'>down.</span> <span m='3656880'>I</span> <span
  m='3656940'>think</span> <span m='3657130'>there</span> <span
  m='3657310'>are</span> <span m='3657400'>two</span> <span
  m='3657720'>competing</span> <span m='3658480'>arguments.</span> <span
  m='3659680'>That</span> <span m='3660100'>on</span> <span
  m='3660200'>the</span> <span m='3660270'>one</span> <span
  m='3660480'>hand,</span> <span m='3661330'>it</span> <span
  m='3661440'>makes</span> <span m='3661620'>it</span> <span
  m='3661680'>more</span> <span m='3661870'>likely</span> <span
  m='3662190'>it's  a</span> <span m='3662350'>6</span> <span
  m='3662590'>or</span> <span m='3662660'>8-sided,</span> <span
  m='3663530'>but</span> <span m='3663640'>it</span> <span
  m='3663710'>also</span> <span m='3663960'>makes</span> <span
  m='3664180'>it</span> <span m='3664240'>completely</span> <span
  m='3664650'>impossible</span> <span m='3665150'>that</span> <span
  m='3665270'>it's</span> <span m='3665380'>a</span> <span
  m='3665420'>4-sided.</span> </p><p><span m='3666005'>PROFESSOR: I'll give
  you</span> <span m='3666570'>3 to 1 odds</span> <span m='3667090'>that it goes
  up.</span> </p><p><span m='3667460'>PROFESSOR 2: Aw</span> <span
  m='3667820'>crap.</span> </p><p><span m='3670290'>PROFESSOR: So</span> <span
  m='3670490'>what  he</span> <span m='3670700'>doesn't</span> <span
  m='3671030'>know</span> <span m='3671250'>is</span> <span
  m='3671350'>whether</span> <span m='3671520'>I've</span> <span
  m='3671720'>computed</span> <span m='3672370'>already</span> <span
  m='3672710'>or</span> <span m='3672780'>not.</span> </p><p><span
  m='3673550'>PROFESSOR 2: He</span> <span m='3673640'>probably</span> <span
  m='3674040'>has.</span> <span m='3675770'>But  he</span> <span
  m='3676060'>probably</span> <span m='3676330'>did</span> <span m='3676490'>it
  at</span> <span m='3676720'>like</span> <span m='3676920'>3</span> <span
  m='3677080'>AM,</span> <span m='3677460'>so</span> <span m='3677720'>I</span>
  <span m='3677830'>don't</span> <span m='3678050'>trust</span> <span
  m='3678330'>it.</span> </p><p><span m='3678730'>PROFESSOR: I</span> <span
  m='3678850'>simulated</span> <span m='3679195'>it</span> <span
  m='3679540'>in</span> <span m='3679770'>[INAUDIBLE].</span> </p><p><span
  m='3680530'>PROFESSOR 2:  I</span> <span m='3680640'>see.</span> <span
  m='3682460'>Are</span> <span m='3682700'>there</span> <span
  m='3682860'>any</span> <span m='3683140'>questions?</span> <span
  m='3684390'>That's</span> <span m='3684640'>what</span> <span
  m='3684720'>we</span> <span m='3684800'>have</span> <span
  m='3684970'>for</span> <span m='3685060'>today,</span> <span
  m='3685330'>so</span> <span m='3685470'>are</span> <span
  m='3685530'>there</span> <span m='3685660'>any</span> <span
  m='3685800'>questions</span> <span m='3686230'>about</span> <span
  m='3686520'>Bayseian</span> <span m='3686840'>Updating</span> <span
  m='3687340'>or</span> <span m='3687410'>doing</span> <span
  m='3687610'>these</span> <span m='3687740'>computations?</span> <span
  m='3692190'>All</span> <span m='3692370'>right,</span> <span
  m='3692690'>great.</span> </p>
embedded_media:
  - uid: 0829245a7a249111015fb54d775c2ed7
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: DyuQsaqXhwU
  - uid: d47e80265158c06437953ebf5f7c50a4
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/DyuQsaqXhwU/default.jpg'
  - uid: f61376941f6a80049e61194f34b28416
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'https://archive.org/download/MIT18.05S14/MIT18_05S14_class12_300k.mp4'
  - uid: d813c2146a1d049d944dc4e3c50148d9
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: 3Play-3PlayYouTubeid-PDF
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: DyuQsaqXhwU
  - uid: 933cba3059def3d7fdda9f307a71c8c0
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: DyuQsaqXhwU.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/18-05-introduction-to-probability-and-statistics-spring-2014/933cba3059def3d7fdda9f307a71c8c0_DyuQsaqXhwU.srt
  - uid: 4f0443556eed1ef14440d5d1b4a1b220
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: DyuQsaqXhwU.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/18-05-introduction-to-probability-and-statistics-spring-2014/4f0443556eed1ef14440d5d1b4a1b220_DyuQsaqXhwU.pdf
  - uid: 73fa4db53fefde506763c3a3361fedeb
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 2c0103c885c26e3188d504ac71abdb00
    parent_uid: b09c96b115749aa10e37c1edf840eb0f
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: 18-05-introduction-to-probability-and-statistics-spring-2014
type: course
layout: video
---
