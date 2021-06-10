---
order_index: null
title: 'Lecture 12: Sums'
template_type: Tabbed
uid: 3ab159732cf8753652d2c1ff154f1a4a
parent_uid: 7e5e792254d703550b60881541fa6160
technical_location: >-
  https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2010/video-lectures/lecture-12-sums
short_url: lecture-12-sums
inline_embed_id: '11096608lecture12:sums32536052'
about_this_resource_text: >-
  <p><strong>Description:</strong> An introduction to sums through examination
  of real&ndash;world problems like annuities. Covers finding closed form
  solutions and bounds with the perturbation, derivative, and integral
  methods.</p> <p><strong>Speaker:</strong> Tom Leighton</p>
related_resources_text: ''
transcript: >-
  <p><span m='360'>PROFESSOR: The</span> <span m='490'>following</span> <span
  m='940'>content</span> <span m='1530'>is</span> <span m='1650'>provided</span>
  <span m='2100'>under</span> <span m='2350'>a</span> <span
  m='2400'>Creative</span> <span m='2800'>Commons</span> <span
  m='3220'>license.</span> <span m='4340'>Your</span> <span
  m='4510'>support</span> <span m='5050'>will</span> <span m='5200'>help</span>
  <span m='5500'>MIT</span> <span m='5870'>OpenCourseWare</span> <span
  m='6660'>continue</span> <span m='7170'>to</span> <span m='7290'>offer</span>
  <span m='7690'>high</span> <span m='7910'>quality</span> <span
  m='8420'>educational</span> <span m='9060'>resources</span> <span
  m='9640'>for</span> <span m='9820'>free.</span> <span m='11020'>To</span>
  <span m='11040'>make</span> <span m='11250'>a</span> <span
  m='11290'>donation</span> <span m='11980'>or</span> <span
  m='12230'>view</span> <span m='12680'>additional</span> <span
  m='13120'>materials</span> <span m='13640'>from</span> <span
  m='13830'>hundreds</span> <span m='14240'>of</span> <span m='14360'>MIT</span>
  <span m='14760'>courses,</span> <span m='15840'>visit</span> <span
  m='16100'>MIT</span> <span m='16510'>OpenCourseWare</span> <span
  m='17560'>at</span> <span m='17750'>ocw.mit.edu.</span> </p><p><span
  m='22940'>Today</span> <span m='23230'>we're</span> <span
  m='23330'>going</span> <span m='23450'>to</span> <span m='23520'>start</span>
  <span m='23820'>with</span> <span m='23950'>a</span> <span
  m='24000'>simple</span> <span m='24350'>problem</span> <span
  m='24740'>that</span> <span m='24880'>many</span> <span m='25220'>of</span>
  <span m='25300'>you</span> <span m='25800'>may</span> <span
  m='25980'>have</span> <span m='26110'>already</span> <span
  m='26400'>encountered.</span> <span m='27670'>For</span> <span
  m='27800'>example,</span> <span m='28220'>when</span> <span
  m='28350'>you</span> <span m='28410'>got</span> <span m='28580'>a</span> <span
  m='28620'>student</span> <span m='28990'>loan</span> <span m='29840'>or</span>
  <span m='30240'>if</span> <span m='30350'>your</span> <span
  m='30620'>family</span> <span m='31150'>took</span> <span m='31350'>a</span>
  <span m='31400'>loan</span> <span m='31680'>out</span> <span
  m='31880'>on</span> <span m='32140'>your</span> <span m='32299'>house,</span>
  <span m='32564'>you</span> <span m='32652'>know,</span> <span
  m='32741'>a</span> <span m='32830'>home</span> <span m='33270'>mortgage</span>
  <span m='33640'>loan,</span> <span m='34540'>and</span> <span
  m='34720'>it's</span> <span m='34850'>the</span> <span
  m='34940'>problem</span> <span m='35310'>of</span> <span
  m='35450'>pricing</span> <span m='36070'>an</span> <span
  m='36200'>annuity.</span> <span m='37420'>An</span> <span
  m='37480'>annuity</span> <span m='37970'>is</span> <span m='38150'>a</span>
  <span m='38220'>financial</span> <span m='38800'>instrument</span> <span
  m='39720'>that</span> <span m='40440'>pays</span> <span m='40850'>a</span>
  <span m='40900'>fixed</span> <span m='41230'>amount</span> <span
  m='41590'>of</span> <span m='41690'>money</span> <span m='42660'>every</span>
  <span m='43080'>year</span> <span m='43610'>for</span> <span
  m='43790'>some</span> <span m='44010'>number</span> <span m='44320'>of</span>
  <span m='44410'>years,</span> <span m='44910'>and</span> <span
  m='45050'>it</span> <span m='45120'>has</span> <span m='45330'>a</span> <span
  m='45370'>value</span> <span m='45830'>associated</span> <span
  m='46400'>with</span> <span m='46570'>it.</span> </p><p><span
  m='47170'>For</span> <span m='47200'>example,</span> <span
  m='47720'>with</span> <span m='47820'>a</span> <span m='47920'>student</span>
  <span m='48140'>loan,</span> <span m='48390'>the</span> <span
  m='48460'>value</span> <span m='49150'>is</span> <span m='49280'>the</span>
  <span m='49340'>amount</span> <span m='49570'>of</span> <span
  m='49630'>money</span> <span m='49950'>they</span> <span m='50130'>gave</span>
  <span m='50460'>you</span> <span m='51190'>to</span> <span
  m='51310'>pay</span> <span m='51540'>MIT,</span> <span m='52540'>then</span>
  <span m='52750'>later</span> <span m='53020'>in</span> <span
  m='53100'>life--</span> <span m='54080'>every</span> <span
  m='54550'>year</span> <span m='55160'>or</span> <span m='55350'>every</span>
  <span m='55680'>month--</span> <span m='56070'>you're</span> <span
  m='56180'>going</span> <span m='56300'>to</span> <span m='56370'>send</span>
  <span m='56550'>them</span> <span m='56630'>a</span> <span
  m='56690'>check.</span> <span m='57860'>And</span> <span m='57950'>you</span>
  <span m='58030'>want</span> <span m='58220'>to</span> <span
  m='58240'>sort</span> <span m='58260'>of</span> <span m='58280'>equate</span>
  <span m='58890'>those</span> <span m='59130'>two</span> <span
  m='59300'>things</span> <span m='59690'>to</span> <span m='59770'>find</span>
  <span m='60100'>out,</span> <span m='60960'>are</span> <span
  m='61310'>you</span> <span m='61410'>getting</span> <span
  m='61640'>enough</span> <span m='61860'>money</span> <span
  m='62150'>for</span> <span m='62270'>the</span> <span m='62350'>money</span>
  <span m='62570'>you're</span> <span m='62660'>going</span> <span
  m='62780'>to</span> <span m='62840'>pay</span> <span m='63030'>back</span>
  <span m='63290'>monthly</span> <span m='63680'>sometime</span> <span
  m='64150'>in</span> <span m='64220'>the</span> <span m='64280'>future?</span>
  </p><p><span m='65489'>So</span> <span m='65650'>let's</span> <span
  m='65860'>define</span> <span m='66320'>this,</span> <span
  m='68310'>and</span> <span m='68420'>there's</span> <span m='68560'>a</span>
  <span m='68620'>lot</span> <span m='68920'>of</span> <span
  m='68990'>variations</span> <span m='69990'>on</span> <span
  m='70230'>annuities,</span> <span m='71970'>but</span> <span
  m='72230'>we'll</span> <span m='72490'>start</span> <span
  m='72830'>with</span> <span m='73010'>one</span> <span m='73360'>that's</span>
  <span m='73520'>called</span> <span m='74430'>an</span> <span
  m='74620'>n-year</span> <span m='78580'>$m-dollar</span> <span
  m='81170'>payment</span> <span m='83690'>annuity,</span> <span
  m='90450'>and</span> <span m='90640'>it</span> <span m='90750'>works</span>
  <span m='91090'>by</span> <span m='91290'>paying</span> <span
  m='93190'>m</span> <span m='93530'>dollars</span> <span m='95890'>at</span>
  <span m='96080'>the</span> <span m='96160'>start</span> <span
  m='96610'>of</span> <span m='96700'>each</span> <span m='96910'>year,</span>
  <span m='106950'>and</span> <span m='107130'>it</span> <span
  m='107230'>lasts</span> <span m='107670'>for</span> <span m='107830'>n</span>
  <span m='108120'>years.</span> <span m='112770'>Now,</span> <span
  m='112960'>usually</span> <span m='113640'>n</span> <span m='113840'>is</span>
  <span m='114000'>finite,</span> <span m='114480'>but</span> <span
  m='114630'>not</span> <span m='114860'>always,</span> <span
  m='115380'>and</span> <span m='115620'>in</span> <span m='115800'>a</span>
  <span m='115840'>few</span> <span m='116010'>minutes</span> <span
  m='116390'>we'll</span> <span m='116490'>talk</span> <span
  m='116610'>about</span> <span m='116770'>the</span> <span
  m='116840'>case</span> <span m='117160'>when</span> <span
  m='117280'>it's</span> <span m='117430'>infinite.</span> </p><p><span
  m='119150'>But</span> <span m='119320'>this</span> <span
  m='119520'>includes</span> <span m='120930'>home</span> <span
  m='121210'>mortgages,</span> <span m='121850'>where</span> <span
  m='121960'>you</span> <span m='122060'>pay</span> <span
  m='122320'>every</span> <span m='122500'>month</span> <span
  m='122710'>for</span> <span m='122810'>30</span> <span
  m='123110'>years.</span> <span m='123690'>Megabucks,</span> <span
  m='124420'>the</span> <span m='124510'>lottery.</span> <span
  m='125800'>They</span> <span m='125940'>don't</span> <span
  m='126080'>actually</span> <span m='126370'>give</span> <span
  m='126560'>you</span> <span m='126640'>the</span> <span
  m='126720'>million</span> <span m='127040'>dollars.</span> <span
  m='127890'>They</span> <span m='128039'>give</span> <span
  m='128240'>you</span> <span m='128340'>$50,000</span> <span
  m='129610'>per</span> <span m='129850'>year</span> <span m='130120'>for</span>
  <span m='130250'>20</span> <span m='130570'>years,</span> <span
  m='131030'>and</span> <span m='131170'>call</span> <span m='131430'>it</span>
  <span m='131490'>a</span> <span m='131530'>million</span> <span
  m='131840'>bucks.</span> <span m='133250'>Retirement</span> <span
  m='133900'>plans.</span> <span m='134880'>You</span> <span
  m='135150'>pay</span> <span m='135550'>in</span> <span m='136250'>every</span>
  <span m='136610'>year,</span> <span m='136940'>and</span> <span
  m='137050'>then</span> <span m='137190'>you</span> <span m='137270'>get</span>
  <span m='137840'>some</span> <span m='138640'>big</span> <span
  m='138890'>lump</span> <span m='139090'>sum</span> <span
  m='139310'>later.</span> <span m='139620'>Life</span> <span
  m='139920'>insurance</span> <span m='140500'>benefits,</span> <span
  m='141920'>you</span> <span m='142020'>know,</span> <span
  m='142140'>and</span> <span m='142230'>so</span> <span
  m='142410'>forth.</span> </p><p><span m='142880'>Now,</span> <span
  m='143850'>if</span> <span m='144030'>you</span> <span m='144110'>go</span>
  <span m='144210'>to</span> <span m='144310'>Wall</span> <span
  m='144600'>Street,</span> <span m='144860'>this</span> <span
  m='145010'>is</span> <span m='145100'>a</span> <span m='145150'>big</span>
  <span m='145390'>deal.</span> <span m='145940'>A</span> <span
  m='145990'>lot</span> <span m='146440'>of</span> <span m='146500'>the</span>
  <span m='146570'>stuff</span> <span m='146820'>that</span> <span
  m='146930'>happens</span> <span m='147290'>on</span> <span
  m='147420'>Wall</span> <span m='147700'>Street</span> <span
  m='148080'>involves</span> <span m='148760'>annuities</span> <span
  m='149730'>in</span> <span m='149860'>one</span> <span m='150100'>form</span>
  <span m='150320'>or</span> <span m='150350'>another,</span> <span
  m='150580'>packaging</span> <span m='151170'>them</span> <span
  m='151310'>all</span> <span m='151570'>up</span> <span m='152400'>and,</span>
  <span m='152890'>in</span> <span m='152980'>fact,</span> <span
  m='153730'>we'll</span> <span m='154230'>look</span> <span
  m='154430'>at</span> <span m='154560'>later</span> <span
  m='154800'>when</span> <span m='154950'>we</span> <span m='154990'>do</span>
  <span m='155030'>probability.</span> <span m='156120'>It</span> <span
  m='156370'>was</span> <span m='156540'>how</span> <span
  m='156780'>these</span> <span m='157020'>things</span> <span
  m='157230'>were</span> <span m='157330'>packaged</span> <span
  m='157860'>and</span> <span m='157970'>sold</span> <span
  m='158380'>that</span> <span m='158510'>led</span> <span m='158710'>to</span>
  <span m='158780'>the</span> <span m='159290'>sub-prime</span> <span
  m='159850'>mortgage</span> <span m='160220'>disaster,</span> <span
  m='161270'>and</span> <span m='161410'>we'll</span> <span
  m='161500'>see</span> <span m='161720'>how</span> <span m='161890'>some</span>
  <span m='162070'>confusion</span> <span m='162650'>over</span> <span
  m='163350'>independents,</span> <span m='164160'>when</span> <span
  m='164270'>you</span> <span m='164370'>look</span> <span m='164560'>at</span>
  <span m='164980'>random</span> <span m='165360'>variables,</span> <span
  m='165940'>led</span> <span m='166190'>to</span> <span m='166700'>the</span>
  <span m='166810'>global</span> <span m='167150'>recession,</span> <span
  m='167680'>a</span> <span m='167790'>real</span> <span
  m='167960'>disaster.</span> </p><p><span m='169040'>Of</span> <span
  m='169100'>course,</span> <span m='169300'>some</span> <span
  m='169520'>people</span> <span m='169880'>understood</span> <span
  m='170380'>how</span> <span m='170510'>all</span> <span m='170660'>that</span>
  <span m='170850'>worked,</span> <span m='171220'>made</span> <span
  m='171520'>hundreds</span> <span m='172120'>of</span> <span
  m='172190'>billions</span> <span m='172490'>of</span> <span
  m='172550'>dollars</span> <span m='173090'>at</span> <span
  m='173150'>the</span> <span m='173220'>same</span> <span
  m='173500'>time.</span> <span m='173820'>So</span> <span m='173990'>it</span>
  <span m='174100'>was</span> <span m='174220'>sort</span> <span
  m='174370'>of</span> <span m='175030'>money</span> <span
  m='175270'>went</span> <span m='175450'>from</span> <span
  m='175570'>one</span> <span m='175730'>place</span> <span m='175970'>to</span>
  <span m='176090'>another.</span> <span m='177260'>So</span> <span
  m='177360'>it's</span> <span m='177730'>pretty</span> <span
  m='177940'>important</span> <span m='178380'>to</span> <span
  m='178440'>understand</span> <span m='179790'>how</span> <span
  m='180060'>much</span> <span m='180570'>this</span> <span m='180940'>is</span>
  <span m='181140'>worth.</span> <span m='182930'>What</span> <span
  m='183250'>is</span> <span m='183910'>this</span> <span
  m='184180'>instrument--</span> <span m='184790'>a</span> <span
  m='184870'>piece</span> <span m='185120'>of</span> <span
  m='185200'>paper</span> <span m='185550'>that</span> <span
  m='185740'>says</span> <span m='186010'>it</span> <span m='186080'>will</span>
  <span m='186170'>pay</span> <span m='186470'>you</span> <span
  m='186620'>m</span> <span m='186770'>dollars</span> <span m='187290'>at</span>
  <span m='187370'>the</span> <span m='187430'>beginning</span> <span
  m='187710'>of</span> <span m='187780'>each</span> <span m='187940'>year</span>
  <span m='188100'>for</span> <span m='188230'>n</span> <span
  m='188370'>years,</span> <span m='188900'>what</span> <span
  m='189160'>is</span> <span m='189300'>that</span> <span
  m='189530'>worth</span> <span m='190290'>today?</span> </p><p><span
  m='191430'>For</span> <span m='191580'>example,</span> <span
  m='193130'>say</span> <span m='193400'>I</span> <span m='193480'>gave</span>
  <span m='193740'>you</span> <span m='193880'>a</span> <span
  m='193930'>choice--</span> <span m='194650'>the</span> <span
  m='194730'>Megabucks</span> <span m='195260'>choice--</span> <span
  m='196310'>$50,000</span> <span m='197200'>a</span> <span
  m='197250'>year</span> <span m='197580'>for</span> <span m='197710'>20</span>
  <span m='198070'>years</span> <span m='199320'>or</span> <span
  m='199510'>a</span> <span m='199560'>million</span> <span
  m='199910'>dollars</span> <span m='200630'>today.</span> <span
  m='201950'>How</span> <span m='202140'>many</span> <span
  m='202330'>people</span> <span m='202640'>would</span> <span
  m='202770'>prefer</span> <span m='203200'>the</span> <span
  m='203290'>$50,000</span> <span m='204050'>a</span> <span
  m='204090'>year</span> <span m='204270'>for</span> <span m='204400'>20</span>
  <span m='204700'>years?</span> <span m='206430'>A</span> <span
  m='206530'>few</span> <span m='206740'>of</span> <span m='206885'>you.</span>
  <span m='207030'>How</span> <span m='207190'>many</span> <span
  m='207350'>would</span> <span m='207460'>prefer</span> <span
  m='207760'>the</span> <span m='207850'>million</span> <span
  m='208340'>bucks</span> <span m='208830'>right</span> <span
  m='209060'>up</span> <span m='209170'>front?</span> <span
  m='210840'>Much</span> <span m='211120'>better.</span> <span
  m='211670'>OK.</span> <span m='212630'>Always</span> <span
  m='213160'>better</span> <span m='213380'>to</span> <span
  m='213480'>have</span> <span m='213680'>the</span> <span
  m='213760'>cash</span> <span m='214130'>in</span> <span
  m='214260'>hand,</span> <span m='214970'>because</span> <span
  m='215310'>there's</span> <span m='215490'>things</span> <span
  m='215710'>like</span> <span m='215890'>inflation--</span> <span
  m='216900'>pretty</span> <span m='217130'>low</span> <span
  m='217370'>now--</span> <span m='218820'>interest.</span> <span
  m='219680'>You</span> <span m='219960'>can</span> <span m='220060'>put</span>
  <span m='220230'>the</span> <span m='220290'>money</span> <span
  m='220580'>in</span> <span m='220660'>the</span> <span m='220740'>bank</span>
  <span m='221160'>or</span> <span m='221240'>invest</span> <span
  m='221650'>it</span> <span m='221740'>and</span> <span m='221880'>make</span>
  <span m='222110'>some</span> <span m='222280'>money</span> <span
  m='222840'>hopefully.</span> </p><p><span m='224980'>So</span> <span
  m='225180'>the</span> <span m='225280'>million</span> <span
  m='225630'>dollars</span> <span m='225960'>today</span> <span
  m='226180'>is</span> <span m='226260'>a</span> <span m='226320'>lot</span>
  <span m='226540'>better,</span> <span m='227170'>which</span> <span
  m='227430'>is</span> <span m='227530'>why</span> <span m='227720'>the</span>
  <span m='227810'>State</span> <span m='228240'>pays</span> <span
  m='228530'>you</span> <span m='229312'>50</span> <span m='229660'>grand</span>
  <span m='229940'>a</span> <span m='230000'>year</span> <span
  m='230150'>for</span> <span m='230270'>20</span> <span
  m='230540'>years.</span> <span m='230960'>It's</span> <span
  m='231240'>better</span> <span m='231470'>for</span> <span
  m='231610'>them,</span> <span m='231850'>and</span> <span
  m='231950'>they</span> <span m='232000'>call</span> <span m='232280'>it</span>
  <span m='232340'>a</span> <span m='232370'>million</span> <span
  m='232670'>bucks.</span> <span m='233810'>So</span> <span
  m='233960'>that</span> <span m='234090'>was</span> <span
  m='234240'>pretty</span> <span m='234470'>clear,</span> <span
  m='234710'>but</span> <span m='234840'>what</span> <span m='235030'>if</span>
  <span m='235130'>I</span> <span m='235220'>gave</span> <span
  m='235450'>you</span> <span m='235550'>this</span> <span
  m='235840'>option--</span> <span m='237720'>700</span> <span
  m='238580'>grand</span> <span m='238950'>today</span> <span
  m='240400'>or</span> <span m='240830'>50</span> <span m='241330'>grand</span>
  <span m='241680'>a</span> <span m='241750'>year</span> <span
  m='241950'>for</span> <span m='242070'>20</span> <span
  m='242420'>years?</span> <span m='243700'>How</span> <span
  m='243860'>many</span> <span m='244050'>people</span> <span
  m='244400'>want</span> <span m='244630'>the</span> <span
  m='244710'>cash</span> <span m='245100'>upfront--</span> <span
  m='245510'>700</span> <span m='246170'>grand</span> <span
  m='246560'>only.</span> <span m='248090'>A</span> <span m='248170'>few.</span>
  </p><p><span m='248660'>How</span> <span m='248820'>many</span> <span
  m='249010'>people</span> <span m='249300'>want</span> <span
  m='250410'>50</span> <span m='250720'>grand</span> <span m='250970'>a</span>
  <span m='251030'>year</span> <span m='251190'>for</span> <span
  m='251300'>20</span> <span m='251560'>years?</span> <span
  m='253310'>All</span> <span m='253400'>right,</span> <span
  m='253440'>we're</span> <span m='253580'>almost--</span> <span
  m='253990'>that's</span> <span m='254170'>pretty</span> <span
  m='254360'>close</span> <span m='254600'>to</span> <span
  m='254700'>half</span> <span m='254900'>way.</span> <span
  m='255770'>How</span> <span m='256029'>about</span> <span
  m='256420'>500</span> <span m='257550'>grand</span> <span
  m='258019'>today</span> <span m='258529'>versus</span> <span
  m='259000'>50</span> <span m='259430'>grand</span> <span m='259800'>a</span>
  <span m='259850'>year</span> <span m='260000'>for</span> <span
  m='260120'>20</span> <span m='260420'>years?</span> <span
  m='260750'>How</span> <span m='260899'>many</span> <span
  m='261060'>want</span> <span m='261930'>half</span> <span m='262200'>a</span>
  <span m='262250'>million</span> <span m='262620'>today?</span> <span
  m='264670'>A</span> <span m='264770'>lot</span> <span m='264890'>of</span>
  <span m='264950'>people</span> <span m='265130'>like</span> <span
  m='265310'>the</span> <span m='265390'>cash.</span> <span
  m='265760'>You</span> <span m='265820'>know,</span> <span
  m='265910'>it's</span> <span m='266030'>this</span> <span
  m='266190'>kind</span> <span m='266360'>of</span> <span m='266430'>a</span>
  <span m='266470'>time,</span> <span m='266830'>you</span> <span
  m='266900'>have</span> <span m='267020'>the</span> <span
  m='267090'>recession,</span> <span m='268140'>it's</span> <span
  m='268240'>a</span> <span m='268290'>disaster</span> <span
  m='268860'>on</span> <span m='268980'>Wall</span> <span
  m='269360'>Street.</span> <span m='269740'>You</span> <span
  m='269930'>know,</span> <span m='270120'>Street</span> <span
  m='270270'>Wall</span> <span m='270460'>Street</span> <span
  m='270610'>didn't</span> <span m='270740'>like</span> <span
  m='270900'>the</span> <span m='270970'>cash.</span> </p><p><span
  m='271700'>How</span> <span m='271860'>many</span> <span
  m='272050'>want,</span> <span m='272630'>instead</span> <span
  m='273050'>of</span> <span m='273130'>a</span> <span m='273190'>half</span>
  <span m='273450'>a</span> <span m='273670'>million</span> <span
  m='274100'>up</span> <span m='274260'>front,</span> <span m='274730'>50</span>
  <span m='275040'>grand</span> <span m='275300'>a</span> <span
  m='275330'>year</span> <span m='275430'>for</span> <span m='275530'>20</span>
  <span m='275790'>years?</span> <span m='277260'>All</span> <span
  m='277340'>right,</span> <span m='277420'>now</span> <span
  m='277670'>we're</span> <span m='277730'>about</span> <span
  m='277990'>halfway.</span> <span m='278710'>All</span> <span
  m='278890'>right,</span> <span m='279040'>well</span> <span
  m='279190'>that's</span> <span m='279420'>pretty</span> <span
  m='279630'>good.</span> <span m='279850'>So</span> <span
  m='279910'>we're</span> <span m='279970'>going</span> <span
  m='280090'>to</span> <span m='280150'>find</span> <span m='280430'>out</span>
  <span m='280550'>what</span> <span m='280690'>you</span> <span
  m='280770'>should</span> <span m='281000'>pay,</span> <span
  m='281815'>or</span> <span m='282290'>at</span> <span m='282350'>least</span>
  <span m='282550'>one</span> <span m='282740'>way</span> <span
  m='282950'>of</span> <span m='283300'>estimating</span> <span
  m='283820'>that.</span> </p><p><span m='284750'>Now,</span> <span
  m='284920'>to</span> <span m='285020'>do</span> <span m='285240'>that,</span>
  <span m='286520'>we've</span> <span m='286690'>got</span> <span
  m='286800'>to</span> <span m='286860'>figure</span> <span
  m='287210'>out</span> <span m='287500'>what</span> <span m='288460'>$1</span>
  <span m='289370'>today</span> <span m='290630'>is</span> <span
  m='290820'>worth</span> <span m='291130'>in</span> <span m='291210'>a</span>
  <span m='291300'>year.</span> <span m='293670'>And</span> <span
  m='293920'>to</span> <span m='293990'>do</span> <span m='294210'>that,</span>
  <span m='294860'>we</span> <span m='295050'>make</span> <span
  m='295300'>an</span> <span m='295380'>assumption,</span> <span
  m='300680'>and</span> <span m='300750'>the</span> <span
  m='300820'>assumption</span> <span m='301300'>is</span> <span
  m='301510'>that</span> <span m='301610'>there's</span> <span
  m='301780'>a</span> <span m='301840'>fixed--</span> <span
  m='303750'>we'll</span> <span m='303890'>call</span> <span
  m='304140'>it</span> <span m='304200'>an</span> <span
  m='304350'>interest</span> <span m='304800'>rate.</span> <span
  m='306600'>It's</span> <span m='306810'>sort</span> <span m='306990'>of</span>
  <span m='307060'>the</span> <span m='307420'>devaluation</span> <span
  m='308290'>of</span> <span m='308350'>the</span> <span m='308420'>money</span>
  <span m='308940'>per</span> <span m='309120'>year.</span> <span
  m='312180'>And</span> <span m='312340'>we're</span> <span
  m='312470'>going</span> <span m='312590'>to</span> <span
  m='312650'>call</span> <span m='312930'>it</span> <span m='313040'>p.</span>
  <span m='313490'>Later</span> <span m='313760'>we'll</span> <span
  m='313890'>plug</span> <span m='314100'>in</span> <span
  m='314310'>values</span> <span m='314690'>for</span> <span
  m='314800'>p,</span> <span m='315000'>but</span> <span m='315120'>you</span>
  <span m='315240'>can</span> <span m='315360'>think</span> <span
  m='315570'>of</span> <span m='315650'>it</span> <span m='315740'>as</span>
  <span m='315880'>like</span> <span m='316600'>6%,</span> <span
  m='317900'>1%.</span> <span m='318890'>You</span> <span
  m='319010'>know,</span> <span m='319150'>it's</span> <span
  m='319290'>the</span> <span m='319520'>money,</span> <span
  m='319840'>if</span> <span m='319930'>you</span> <span m='320010'>put</span>
  <span m='320210'>money</span> <span m='320400'>in</span> <span
  m='320480'>a</span> <span m='320530'>bank,</span> <span
  m='320880'>they'll</span> <span m='321000'>give</span> <span
  m='321180'>you</span> <span m='321280'>some</span> <span
  m='321540'>percent</span> <span m='321940'>back</span> <span
  m='322300'>every</span> <span m='322500'>year.</span> <span
  m='323650'>And,</span> <span m='323780'>of</span> <span
  m='323850'>course,</span> <span m='324640'>the</span> <span
  m='324740'>fact</span> <span m='325040'>that</span> <span
  m='325230'>different</span> <span m='325600'>people</span> <span
  m='325830'>have</span> <span m='325940'>different</span> <span
  m='326230'>ideas</span> <span m='326590'>of</span> <span
  m='326690'>what</span> <span m='326860'>this</span> <span
  m='327020'>would</span> <span m='327150'>be,</span> <span
  m='327430'>allows</span> <span m='327790'>people</span> <span
  m='328020'>to</span> <span m='328080'>make</span> <span
  m='328260'>money</span> <span m='328510'>on</span> <span
  m='328620'>Wall</span> <span m='328860'>Street.</span> <span
  m='329950'>As</span> <span m='330160'>we'll</span> <span
  m='330290'>see,</span> <span m='330590'>a</span> <span
  m='330810'>slight</span> <span m='331290'>difference</span> <span
  m='331640'>in</span> <span m='332090'>p</span> <span m='332440'>can</span>
  <span m='332615'>make</span> <span m='333130'>big</span> <span
  m='333330'>differences</span> <span m='333820'>in</span> <span
  m='333920'>what</span> <span m='334110'>the</span> <span
  m='334610'>annuity</span> <span m='335020'>is</span> <span
  m='335150'>worth.</span> </p><p><span m='336460'>So</span> <span
  m='336700'>for</span> <span m='336830'>example,</span> <span
  m='339750'>$1</span> <span m='340380'>today</span> <span m='345580'>is</span>
  <span m='345740'>going</span> <span m='345950'>to</span> <span
  m='346020'>equal</span> <span m='347460'>1</span> <span m='347850'>plus</span>
  <span m='348130'>p</span> <span m='348380'>dollars</span> <span
  m='349830'>in</span> <span m='349980'>one</span> <span m='350200'>year.</span>
  <span m='354360'>Similarly,</span> <span m='354960'>$1</span> <span
  m='355490'>today--</span> <span m='356670'>how</span> <span
  m='356850'>much</span> <span m='357040'>is</span> <span m='357130'>that</span>
  <span m='357290'>going</span> <span m='357410'>to</span> <span
  m='357470'>be</span> <span m='357540'>worth</span> <span m='358760'>in</span>
  <span m='358960'>two</span> <span m='359150'>years?</span> <span
  m='363910'>Say</span> <span m='364160'>that</span> <span m='364250'>p</span>
  <span m='364520'>stays</span> <span m='364800'>fixed,</span> <span
  m='365270'>the</span> <span m='365400'>same</span> <span
  m='365720'>over</span> <span m='365900'>all</span> <span
  m='366080'>time.</span> <span m='370060'>One</span> <span
  m='370390'>plus</span> <span m='370680'>p</span> <span
  m='370970'>squared,</span> <span m='373410'>because</span> <span
  m='373770'>every</span> <span m='374030'>year</span> <span
  m='374240'>you</span> <span m='374360'>multiply</span> <span
  m='374870'>what</span> <span m='375060'>you</span> <span m='375150'>got</span>
  <span m='375470'>by</span> <span m='375570'>1</span> <span
  m='375840'>plus</span> <span m='376100'>p,</span> <span
  m='376570'>because</span> <span m='376750'>that's</span> <span
  m='376970'>the</span> <span m='377100'>interest</span> <span
  m='377410'>you're</span> <span m='377500'>getting.</span> <span
  m='378560'>All</span> <span m='378625'>right,</span> <span
  m='378690'>we'll</span> <span m='378810'>think</span> <span
  m='379020'>of</span> <span m='379090'>it</span> <span m='379150'>in</span>
  <span m='379240'>terms</span> <span m='379520'>of</span> <span
  m='379610'>interest.</span> <span m='380940'>In</span> <span
  m='381090'>three</span> <span m='381460'>years,</span> <span
  m='382050'>$1</span> <span m='382510'>today</span> <span m='383510'>is</span>
  <span m='383750'>worth</span> <span m='385250'>1</span> <span
  m='385490'>plus</span> <span m='385760'>p</span> <span m='385950'>cubed</span>
  <span m='387900'>in</span> <span m='388070'>three</span> <span
  m='388330'>years</span> <span m='389380'>and</span> <span m='389590'>so</span>
  <span m='389790'>forth.</span> </p><p><span m='392740'>All</span> <span
  m='392920'>right.</span> <span m='393160'>Now,</span> <span
  m='393650'>what</span> <span m='393760'>we</span> <span
  m='393880'>really</span> <span m='394230'>care</span> <span
  m='394540'>about</span> <span m='394850'>is</span> <span
  m='394970'>what's</span> <span m='395190'>$1,</span> <span
  m='395870'>or</span> <span m='396030'>m</span> <span
  m='396300'>dollars,</span> <span m='396750'>worth</span> <span
  m='397610'>today</span> <span m='398360'>if</span> <span
  m='398460'>you're</span> <span m='398580'>getting</span> <span
  m='398890'>it</span> <span m='399220'>next</span> <span
  m='399570'>year?</span> <span m='400090'>So</span> <span m='400120'>we</span>
  <span m='400190'>need</span> <span m='400330'>to</span> <span
  m='400410'>sort</span> <span m='400640'>of</span> <span m='401110'>flip</span>
  <span m='401610'>this</span> <span m='403000'>back</span> <span
  m='403310'>the</span> <span m='403430'>other</span> <span
  m='403580'>way.</span> <span m='407930'>So</span> <span m='408390'>what</span>
  <span m='408670'>is</span> <span m='409300'>$1</span> <span
  m='411210'>in</span> <span m='411370'>a</span> <span m='411470'>year</span>
  <span m='412230'>worth</span> <span m='412590'>today</span> <span
  m='415700'>in</span> <span m='415780'>terms</span> <span m='416050'>of</span>
  <span m='416140'>p?</span> <span m='419160'>So</span> <span
  m='419300'>if</span> <span m='419380'>I'm</span> <span m='419510'>going</span>
  <span m='419630'>to</span> <span m='419690'>be</span> <span
  m='419750'>paid</span> <span m='420030'>$1</span> <span m='420470'>in</span>
  <span m='420560'>a</span> <span m='420610'>year,</span> <span
  m='421870'>what</span> <span m='422040'>would</span> <span
  m='422160'>be</span> <span m='422290'>the</span> <span
  m='422380'>equivalent</span> <span m='422920'>amount</span> <span
  m='423170'>to</span> <span m='423230'>be</span> <span m='423330'>paid</span>
  <span m='423650'>today?</span> <span m='427580'>One</span> <span
  m='428040'>over</span> <span m='428240'>1</span> <span m='428490'>plus</span>
  <span m='428770'>p,</span> <span m='431680'>because</span> <span
  m='432020'>what's</span> <span m='432190'>happening</span> <span
  m='432640'>here</span> <span m='433480'>is,</span> <span m='434010'>as</span>
  <span m='434150'>you</span> <span m='434230'>go</span> <span
  m='434390'>forward</span> <span m='434880'>in</span> <span m='434980'>a</span>
  <span m='435080'>year,</span> <span m='435420'>you</span> <span
  m='435500'>just</span> <span m='435700'>multiply</span> <span
  m='436120'>by</span> <span m='436260'>1</span> <span m='436550'>plus</span>
  <span m='436790'>p.</span> <span m='437690'>So</span> <span
  m='437930'>1</span> <span m='438530'>over</span> <span m='438870'>1</span>
  <span m='439110'>plus</span> <span m='439380'>p</span> <span
  m='439890'>turns</span> <span m='440240'>into</span> <span
  m='440820'>$1</span> <span m='442890'>in</span> <span m='443040'>a</span>
  <span m='443110'>year--</span> <span m='444270'>being</span> <span
  m='444510'>paid</span> <span m='444750'>in</span> <span m='444810'>a</span>
  <span m='444900'>year.</span> <span m='447270'>All</span> <span
  m='447500'>right.</span> <span m='448130'>What</span> <span
  m='448490'>is</span> <span m='449270'>$1</span> <span m='449960'>a</span>
  <span m='450090'>year</span> <span m='450730'>in</span> <span
  m='450890'>two</span> <span m='451170'>years</span> <span
  m='454250'>worth</span> <span m='454590'>today?</span> <span
  m='457650'>One</span> <span m='458370'>over</span> <span m='458760'>1</span>
  <span m='459060'>plus</span> <span m='459380'>p</span> <span
  m='460270'>squared.</span> <span m='462610'>So</span> <span
  m='462790'>$1</span> <span m='463195'>in</span> <span m='463600'>two</span>
  <span m='463775'>years</span> <span m='463950'>is</span> <span
  m='464070'>worth</span> <span m='464460'>this</span> <span
  m='464710'>much</span> <span m='465250'>today.</span> </p><p><span
  m='468060'>Well,</span> <span m='468380'>now</span> <span m='468770'>we</span>
  <span m='468910'>can</span> <span m='469140'>use</span> <span
  m='469530'>this</span> <span m='470070'>to</span> <span m='470200'>go</span>
  <span m='470370'>figure</span> <span m='470800'>out</span> <span
  m='471880'>the</span> <span m='472000'>current</span> <span
  m='472530'>value</span> <span m='473040'>of</span> <span
  m='473140'>that</span> <span m='473350'>annuity.</span> <span
  m='475080'>We</span> <span m='475210'>just</span> <span
  m='475410'>figure</span> <span m='475660'>out</span> <span
  m='475800'>what</span> <span m='475930'>every</span> <span
  m='476170'>payment</span> <span m='476600'>is</span> <span
  m='476700'>worth</span> <span m='478130'>today</span> <span
  m='478930'>and</span> <span m='479030'>then</span> <span m='479060'>add</span>
  <span m='479230'>it</span> <span m='479320'>up.</span> <span
  m='481380'>So</span> <span m='481530'>we'll</span> <span m='481650'>put</span>
  <span m='481830'>the</span> <span m='481910'>payments</span> <span
  m='482580'>over</span> <span m='482800'>here,</span> <span
  m='484220'>and</span> <span m='484380'>we'll</span> <span
  m='484470'>compute</span> <span m='484880'>the</span> <span
  m='484940'>current</span> <span m='485380'>value</span> <span
  m='486890'>of</span> <span m='487070'>every</span> <span
  m='487280'>payment</span> <span m='487880'>on</span> <span
  m='488050'>this</span> <span m='488200'>side.</span> <span
  m='491840'>So</span> <span m='492080'>with</span> <span m='492190'>the</span>
  <span m='492270'>annuity,</span> <span m='493150'>the</span> <span
  m='493260'>way</span> <span m='493390'>we've</span> <span
  m='493580'>set</span> <span m='493840'>it</span> <span m='493930'>up</span>
  <span m='494150'>is</span> <span m='494250'>it</span> <span
  m='494360'>pays</span> <span m='494800'>n</span> <span
  m='495060'>dollars</span> <span m='495460'>at</span> <span
  m='495530'>the</span> <span m='495610'>start</span> <span m='495980'>of</span>
  <span m='496080'>every</span> <span m='496290'>year,</span> <span
  m='496630'>so</span> <span m='496750'>the</span> <span m='496820'>first</span>
  <span m='497670'>payment</span> <span m='498040'>is</span> <span
  m='498170'>now.</span> <span m='499970'>So</span> <span m='500150'>the</span>
  <span m='500240'>first</span> <span m='500610'>of</span> <span
  m='500680'>the</span> <span m='500790'>n</span> <span
  m='500900'>payments</span> <span m='502080'>is</span> <span
  m='502390'>now,</span> <span m='503710'>and</span> <span
  m='504100'>since</span> <span m='504300'>it's</span> <span
  m='504420'>being</span> <span m='504670'>paid</span> <span
  m='505010'>now,</span> <span m='505380'>that's</span> <span
  m='505620'>worth</span> <span m='505940'>m</span> <span
  m='506290'>dollars.</span> <span m='507130'>There's</span> <span
  m='507350'>no</span> <span m='508540'>devaluation.</span> </p><p><span
  m='510320'>The</span> <span m='510430'>next</span> <span
  m='510750'>payment</span> <span m='511430'>is</span> <span m='511810'>m</span>
  <span m='512049'>dollars</span> <span m='514280'>in</span> <span
  m='514490'>one</span> <span m='514750'>year,</span> <span
  m='516789'>and</span> <span m='517010'>so</span> <span
  m='517120'>that's</span> <span m='517400'>going</span> <span
  m='517530'>to</span> <span m='517590'>be</span> <span m='517700'>worth</span>
  <span m='519730'>m</span> <span m='520230'>over</span> <span
  m='520460'>1</span> <span m='520679'>plus</span> <span m='520970'>p</span>
  <span m='521169'>today.</span> <span m='523360'>And</span> <span
  m='523510'>the</span> <span m='523570'>next</span> <span
  m='523850'>payment</span> <span m='524420'>is</span> <span m='525110'>m</span>
  <span m='525360'>dollars</span> <span m='525930'>in</span> <span
  m='526160'>two</span> <span m='526420'>years.</span> <span
  m='528850'>That's</span> <span m='529250'>worth</span> <span
  m='530760'>m</span> <span m='531150'>over</span> <span m='531690'>1</span>
  <span m='531930'>plus</span> <span m='532220'>p</span> <span
  m='532400'>squared,</span> <span m='533870'>and</span> <span
  m='534010'>we</span> <span m='534100'>keep</span> <span m='534390'>on</span>
  <span m='534600'>going</span> <span m='535480'>until</span> <span
  m='535770'>the</span> <span m='535840'>last</span> <span
  m='536340'>payment.</span> <span m='537880'>It's</span> <span
  m='538130'>the</span> <span m='538310'>n-th</span> <span
  m='538820'>payment,</span> <span m='539570'>so</span> <span
  m='539750'>it's</span> <span m='539920'>m</span> <span
  m='540160'>dollars</span> <span m='540790'>in</span> <span m='541940'>n</span>
  <span m='542200'>minus</span> <span m='542530'>1</span> <span
  m='543200'>years.</span> <span m='546330'>And</span> <span
  m='546540'>so</span> <span m='547410'>that's</span> <span
  m='547770'>going</span> <span m='547890'>to</span> <span m='547970'>be</span>
  <span m='548140'>worth</span> <span m='548630'>m</span> <span
  m='550740'>over</span> <span m='551220'>1</span> <span m='551560'>plus</span>
  <span m='551880'>p</span> <span m='553260'>to</span> <span
  m='553380'>the</span> <span m='553510'>n</span> <span m='553650'>minus</span>
  <span m='553970'>1.</span> </p><p><span m='557120'>All</span> <span
  m='557230'>right.</span> <span m='557390'>So</span> <span m='557480'>we</span>
  <span m='557560'>can</span> <span m='557690'>compute</span> <span
  m='558060'>the</span> <span m='558130'>current</span> <span
  m='558540'>value</span> <span m='558860'>of</span> <span m='558950'>all</span>
  <span m='559160'>those</span> <span m='559380'>payments,</span> <span
  m='560440'>then</span> <span m='560610'>the</span> <span
  m='560740'>annuity</span> <span m='562620'>is</span> <span
  m='562800'>computed--</span> <span m='563330'>the</span> <span
  m='563390'>value</span> <span m='563750'>is</span> <span
  m='563840'>computed</span> <span m='564250'>just</span> <span
  m='564430'>by</span> <span m='564630'>adding</span> <span
  m='564990'>these</span> <span m='565210'>up,</span> <span m='566780'>of</span>
  <span m='566890'>all</span> <span m='567060'>the</span> <span
  m='567130'>current</span> <span m='567440'>values.</span> <span
  m='568820'>So</span> <span m='568970'>the</span> <span m='569050'>total</span>
  <span m='569410'>current</span> <span m='569720'>value</span> <span
  m='573040'>is</span> <span m='573440'>the</span> <span m='573530'>sum</span>
  <span m='575860'>i</span> <span m='576150'>equals</span> <span
  m='576590'>0</span> <span m='577070'>to</span> <span m='577180'>n</span> <span
  m='577290'>minus</span> <span m='577650'>1</span> <span m='579012'>of</span>
  <span m='579498'>m</span> <span m='580470'>over</span> <span
  m='580890'>1</span> <span m='581250'>plus</span> <span m='581580'>p</span>
  <span m='582650'>to</span> <span m='582780'>the</span> <span
  m='582970'>i.</span> <span m='584490'>And</span> <span m='584620'>that</span>
  <span m='584810'>is</span> <span m='584960'>the</span> <span
  m='585070'>total</span> <span m='585510'>current</span> <span
  m='585840'>value.</span> <span m='590300'>That's</span> <span
  m='590630'>what</span> <span m='590800'>you</span> <span
  m='590910'>should</span> <span m='591130'>pay</span> <span
  m='591440'>today</span> <span m='594670'>for</span> <span
  m='594940'>the</span> <span m='595050'>annuity.</span> <span
  m='596830'>Any</span> <span m='597010'>questions?</span> <span
  m='599590'>What</span> <span m='599730'>we</span> <span m='599820'>did</span>
  <span m='600020'>here?</span> </p><p><span m='602150'>All</span> <span
  m='602400'>right.</span> <span m='603890'>Well,</span> <span
  m='605040'>of</span> <span m='605100'>course,</span> <span
  m='605370'>what</span> <span m='605470'>we'd</span> <span
  m='605500'>like</span> <span m='606050'>is</span> <span m='606190'>a</span>
  <span m='606240'>closed</span> <span m='606640'>form</span> <span
  m='606880'>expression</span> <span m='607370'>here.</span> <span
  m='608530'>Something</span> <span m='608870'>that's</span> <span
  m='608990'>simple</span> <span m='609610'>so</span> <span m='609740'>we</span>
  <span m='609820'>could</span> <span m='609930'>actually</span> <span
  m='610260'>get</span> <span m='610430'>a</span> <span m='610470'>feel</span>
  <span m='610760'>without</span> <span m='610990'>having</span> <span
  m='611160'>to</span> <span m='611560'>add</span> <span m='611810'>up</span>
  <span m='611930'>all</span> <span m='612120'>those</span> <span
  m='612340'>terms,</span> <span m='614980'>and</span> <span
  m='615470'>that's</span> <span m='615650'>not</span> <span
  m='615810'>hard</span> <span m='615990'>to</span> <span m='616050'>get.</span>
  <span m='616520'>In</span> <span m='616650'>fact,</span> <span
  m='617880'>let's</span> <span m='619030'>put</span> <span
  m='619350'>this</span> <span m='619790'>sum</span> <span m='620070'>in</span>
  <span m='620150'>a</span> <span m='620190'>form</span> <span
  m='620560'>that</span> <span m='620680'>might</span> <span
  m='621000'>be</span> <span m='621120'>more</span> <span
  m='621320'>familiar.</span> </p><p><span m='623420'>This</span> <span
  m='623580'>equals--</span> <span m='624280'>we'll</span> <span
  m='624440'>pull</span> <span m='624670'>the</span> <span m='624820'>m</span>
  <span m='625030'>out</span> <span m='625750'>in</span> <span
  m='625890'>front--</span> <span m='627310'>and</span> <span
  m='627530'>let's</span> <span m='627890'>use</span> <span m='628400'>x</span>
  <span m='628710'>to</span> <span m='628800'>be</span> <span
  m='628890'>1</span> <span m='629160'>over</span> <span m='629320'>1</span>
  <span m='629500'>plus</span> <span m='629710'>p</span> <span
  m='629820'>to</span> <span m='629910'>the</span> <span m='630040'>i.</span>
  <span m='637140'>And</span> <span m='637270'>so</span> <span
  m='637730'>x</span> <span m='640740'>equals</span> <span m='641220'>1</span>
  <span m='641440'>over</span> <span m='641570'>1</span> <span
  m='641740'>plus</span> <span m='641980'>p,</span> <span m='646000'>and</span>
  <span m='646140'>I</span> <span m='646360'>wrote</span> <span
  m='646650'>it</span> <span m='646730'>this</span> <span m='646950'>way</span>
  <span m='647330'>because</span> <span m='647820'>this</span> <span
  m='649200'>might</span> <span m='649470'>be</span> <span
  m='649580'>familiar.</span> <span m='651350'>Does</span> <span
  m='651620'>everybody</span> <span m='651910'>remember</span> <span
  m='652260'>that</span> <span m='652520'>from--</span> <span
  m='652760'>I</span> <span m='652830'>think</span> <span m='653040'>it</span>
  <span m='653110'>was</span> <span m='653350'>the</span> <span
  m='654230'>second</span> <span m='654660'>recitation?</span> <span
  m='657950'>Anybody</span> <span m='658240'>remember</span> <span
  m='658490'>the</span> <span m='658570'>formula?</span> <span
  m='659070'>What</span> <span m='659230'>this</span> <span
  m='659420'>evaluates</span> <span m='659930'>to?</span> <span
  m='662980'>The</span> <span m='663110'>sum</span> <span m='663470'>of</span>
  <span m='663600'>x</span> <span m='663790'>to</span> <span
  m='663870'>the</span> <span m='664020'>i,</span> <span m='664520'>where</span>
  <span m='665020'>i</span> <span m='665250'>goes</span> <span
  m='665610'>from</span> <span m='665770'>0</span> <span m='666140'>to</span>
  <span m='666220'>n</span> <span m='666390'>minus</span> <span
  m='666710'>1?</span> <span m='669380'>Remember</span> <span
  m='669580'>that?</span> <span m='671170'>One</span> <span
  m='671580'>minus</span> <span m='672020'>x</span> <span m='672240'>to</span>
  <span m='672340'>the</span> <span m='672510'>n.</span> <span
  m='675730'>Remember</span> <span m='676190'>1</span> <span
  m='676670'>minus</span> <span m='677050'>x.</span> <span m='678820'>In</span>
  <span m='678910'>the</span> <span m='678980'>second</span> <span
  m='679500'>recitation,</span> <span m='680190'>I</span> <span
  m='680250'>think,</span> <span m='680550'>we</span> <span
  m='680660'>proved</span> <span m='681980'>that</span> <span
  m='682180'>this</span> <span m='682590'>equals</span> <span
  m='682930'>that.</span> <span m='683550'>What</span> <span
  m='683740'>was</span> <span m='683870'>the</span> <span
  m='683950'>proof</span> <span m='684210'>technique</span> <span
  m='684590'>we</span> <span m='684710'>used?</span> <span
  m='686370'>Induction.</span> <span m='687560'>OK?</span> </p><p><span
  m='693490'>So,</span> <span m='693660'>in</span> <span m='693750'>fact,</span>
  <span m='696320'>there's</span> <span m='696530'>a</span> <span
  m='696570'>theorem</span> <span m='697040'>here.</span> <span
  m='701060'>For</span> <span m='701250'>all</span> <span m='701590'>n</span>
  <span m='702420'>bigger</span> <span m='702650'>and</span> <span
  m='702720'>equal</span> <span m='702910'>to</span> <span m='702980'>1</span>
  <span m='703420'>and</span> <span m='703660'>x</span> <span
  m='703980'>not</span> <span m='704230'>equal</span> <span m='704540'>to</span>
  <span m='704640'>1,</span> <span m='706730'>we</span> <span
  m='706940'>proved</span> <span m='708600'>the</span> <span
  m='708700'>sum</span> <span m='709070'>from</span> <span m='709230'>i</span>
  <span m='709390'>equals</span> <span m='709550'>0</span> <span
  m='709820'>to</span> <span m='709900'>n</span> <span m='710090'>minus</span>
  <span m='710450'>1</span> <span m='711250'>x</span> <span m='711570'>to</span>
  <span m='711650'>the</span> <span m='712260'>i</span> <span
  m='712360'>equals</span> <span m='712810'>1</span> <span
  m='713070'>minus</span> <span m='713430'>x</span> <span m='713640'>to</span>
  <span m='713730'>the</span> <span m='713870'>n</span> <span
  m='714810'>over</span> <span m='714960'>1</span> <span m='715150'>minus</span>
  <span m='715500'>x.</span> <span m='717270'>And</span> <span
  m='717370'>so</span> <span m='717450'>this</span> <span m='717610'>is</span>
  <span m='717700'>a</span> <span m='717760'>nice,</span> <span
  m='718030'>closed</span> <span m='718400'>form.</span> <span
  m='718870'>No</span> <span m='719060'>sum</span> <span m='719330'>any</span>
  <span m='719510'>more,</span> <span m='719690'>just</span> <span
  m='720440'>that,</span> <span m='721810'>which</span> <span
  m='721970'>is</span> <span m='722120'>nice.</span> </p><p><span
  m='724040'>Now,</span> <span m='724250'>induction</span> <span
  m='724990'>proved</span> <span m='725450'>it</span> <span
  m='725540'>was</span> <span m='725650'>the</span> <span
  m='725770'>right</span> <span m='726010'>answer.</span> <span
  m='727960'>Once</span> <span m='729060'>you</span> <span
  m='729890'>knew</span> <span m='730170'>it--</span> <span m='731320'>we</span>
  <span m='731630'>gave</span> <span m='731910'>it</span> <span
  m='731990'>to</span> <span m='732110'>you--</span> <span
  m='732740'>using</span> <span m='733060'>induction</span> <span
  m='733450'>to</span> <span m='733520'>prove</span> <span
  m='733770'>that</span> <span m='733930'>theorem</span> <span
  m='734240'>wasn't</span> <span m='734520'>hard.</span> <span
  m='736100'>What</span> <span m='736250'>we're</span> <span
  m='736370'>going</span> <span m='736490'>to</span> <span
  m='736550'>look</span> <span m='736730'>at</span> <span
  m='736820'>doing</span> <span m='737430'>this</span> <span
  m='737730'>week</span> <span m='738030'>and</span> <span
  m='738130'>next</span> <span m='738450'>week</span> <span m='739310'>is</span>
  <span m='739520'>figuring</span> <span m='739880'>out</span> <span
  m='740460'>how</span> <span m='740700'>to</span> <span
  m='740810'>figure</span> <span m='741230'>out</span> <span
  m='741410'>this</span> <span m='741580'>was</span> <span m='741730'>the</span>
  <span m='741870'>answer</span> <span m='742160'>in</span> <span
  m='742230'>the</span> <span m='742300'>first</span> <span
  m='742610'>place.</span> <span m='743550'>Methods</span> <span
  m='744320'>for</span> <span m='744460'>doing</span> <span
  m='744780'>that--</span> <span m='745220'>to</span> <span
  m='745320'>evaluate</span> <span m='745810'>the</span> <span
  m='745880'>sum--</span> <span m='747760'>and</span> <span
  m='748090'>there's</span> <span m='748240'>a</span> <span
  m='748300'>lot</span> <span m='748560'>of</span> <span m='748640'>ways</span>
  <span m='749090'>that</span> <span m='749260'>you</span> <span
  m='749370'>can</span> <span m='749570'>do</span> <span m='750420'>that</span>
  <span m='750620'>particular</span> <span m='751100'>sum.</span> </p><p><span
  m='752050'>Probably</span> <span m='752410'>the</span> <span
  m='752590'>easiest</span> <span m='754790'>is</span> <span
  m='755030'>known</span> <span m='755260'>as</span> <span m='755380'>the</span>
  <span m='755450'>perturbation</span> <span m='756160'>method.</span> <span
  m='760050'>This</span> <span m='760310'>sometimes</span> <span
  m='760890'>works.</span> <span m='762090'>Certainly</span> <span
  m='762420'>with</span> <span m='762520'>sums</span> <span
  m='762770'>like</span> <span m='762980'>that,</span> <span
  m='763200'>it</span> <span m='763280'>often</span> <span
  m='763620'>works.</span> <span m='765200'>The</span> <span
  m='765380'>idea</span> <span m='765680'>is</span> <span m='765760'>as</span>
  <span m='765900'>follows.</span> <span m='766460'>We're</span> <span
  m='766470'>trying</span> <span m='766780'>to</span> <span
  m='766850'>compute</span> <span m='767860'>the</span> <span
  m='767980'>sum</span> <span m='768340'>S,</span> <span m='768840'>which</span>
  <span m='769020'>is</span> <span m='769120'>1</span> <span
  m='769460'>plus</span> <span m='769830'>x</span> <span m='770750'>plus</span>
  <span m='771110'>x</span> <span m='771310'>squared</span> <span
  m='773730'>plus</span> <span m='774070'>x</span> <span m='774320'>to</span>
  <span m='774400'>the</span> <span m='774530'>n</span> <span
  m='774660'>minus</span> <span m='774990'>1,</span> <span m='777500'>and</span>
  <span m='777650'>what</span> <span m='777740'>we're</span> <span
  m='777830'>going</span> <span m='777950'>to</span> <span m='778030'>do</span>
  <span m='778280'>is</span> <span m='778420'>perturb</span> <span
  m='779040'>it</span> <span m='779190'>a</span> <span m='779270'>little</span>
  <span m='779500'>bit</span> <span m='781230'>and</span> <span
  m='781400'>then</span> <span m='781800'>subtract</span> <span
  m='782600'>to</span> <span m='782680'>get</span> <span m='783080'>big</span>
  <span m='783380'>cancellation.</span> </p><p><span m='785210'>In</span> <span
  m='785370'>this</span> <span m='785520'>case,</span> <span
  m='785760'>it's</span> <span m='785880'>pretty</span> <span
  m='786120'>simple.</span> <span m='786620'>We</span> <span
  m='787540'>multiply</span> <span m='788250'>the</span> <span
  m='788350'>sum</span> <span m='788680'>by</span> <span m='788820'>x</span>
  <span m='789410'>to</span> <span m='789520'>get</span> <span
  m='790600'>x</span> <span m='791050'>plus</span> <span m='791430'>x</span>
  <span m='791660'>squared</span> <span m='792210'>plus--</span> <span
  m='798970'>I've</span> <span m='799130'>defined</span> <span
  m='799630'>S</span> <span m='799830'>to</span> <span m='799920'>be</span>
  <span m='800010'>that,</span> <span m='800540'>x</span> <span
  m='800820'>times</span> <span m='801220'>S--</span> <span
  m='802090'>well,</span> <span m='802240'>I</span> <span m='802380'>get</span>
  <span m='802780'>x</span> <span m='803150'>plus</span> <span
  m='803580'>x</span> <span m='803800'>squared</span> <span
  m='804340'>and</span> <span m='805200'>so</span> <span
  m='805450'>forth,</span> <span m='805850'>up</span> <span m='805970'>to</span>
  <span m='806050'>x</span> <span m='806240'>to</span> <span
  m='806320'>the</span> <span m='806440'>n,</span> <span m='808450'>and</span>
  <span m='808660'>now</span> <span m='809020'>I</span> <span
  m='809140'>can</span> <span m='809320'>subtract</span> <span
  m='810040'>one</span> <span m='810230'>from</span> <span m='810390'>the</span>
  <span m='810540'>other</span> <span m='811790'>and</span> <span
  m='812020'>almost</span> <span m='812420'>everything</span> <span
  m='812740'>cancels.</span> <span m='816020'>So</span> <span
  m='816170'>I</span> <span m='816260'>get</span> <span m='816780'>1</span>
  <span m='817150'>minus</span> <span m='817550'>x</span> <span
  m='817880'>times</span> <span m='818200'>S</span> <span
  m='819360'>equals</span> <span m='821240'>1.</span> <span
  m='822220'>These</span> <span m='822480'>cancel,</span> <span
  m='822970'>cancel,</span> <span m='823800'>cancel.</span> <span
  m='825450'>Minus</span> <span m='825860'>x</span> <span m='826070'>to</span>
  <span m='826160'>the</span> <span m='826320'>n.</span> <span
  m='828750'>And</span> <span m='828930'>therefore</span> <span
  m='830520'>S</span> <span m='830880'>equals</span> <span m='831320'>1</span>
  <span m='831550'>minus</span> <span m='831890'>x</span> <span
  m='832200'>to</span> <span m='832270'>the</span> <span m='832340'>n</span>
  <span m='832726'>over</span> <span m='833112'>1</span> <span
  m='833500'>minus</span> <span m='833870'>x.</span> </p><p><span
  m='837000'>So</span> <span m='837090'>that's</span> <span m='839220'>a</span>
  <span m='839260'>vague</span> <span m='839940'>method.</span> <span
  m='841820'>This</span> <span m='842030'>gets</span> <span
  m='842230'>used</span> <span m='842500'>all</span> <span m='842740'>the</span>
  <span m='842840'>time</span> <span m='843900'>in</span> <span
  m='844050'>applied</span> <span m='844400'>mathematics,</span> <span
  m='844930'>and</span> <span m='845020'>they</span> <span
  m='845080'>call</span> <span m='845280'>it</span> <span m='845350'>the</span>
  <span m='845420'>perturbation</span> <span m='846020'>method.</span> <span
  m='846930'>Take</span> <span m='847180'>your</span> <span
  m='847290'>sum,</span> <span m='848880'>wiggle</span> <span
  m='849050'>it</span> <span m='849220'>around</span> <span m='849530'>a</span>
  <span m='849570'>little</span> <span m='849790'>bit,</span> <span
  m='850150'>get</span> <span m='850340'>something</span> <span
  m='850460'>that</span> <span m='850560'>looks</span> <span
  m='850730'>close,</span> <span m='851160'>subtract</span> <span
  m='851800'>it,</span> <span m='851990'>everything</span> <span
  m='852370'>cancels,</span> <span m='852850'>life</span> <span
  m='853100'>is</span> <span m='853220'>nice,</span> <span m='854310'>and</span>
  <span m='854450'>all</span> <span m='854600'>of</span> <span
  m='854670'>a</span> <span m='854710'>sudden</span> <span
  m='855060'>you've</span> <span m='855180'>figured</span> <span
  m='855440'>out</span> <span m='855730'>the</span> <span
  m='855860'>answer.</span> </p><p><span m='861530'>So</span> <span
  m='862980'>getting</span> <span m='863260'>back</span> <span
  m='863490'>to</span> <span m='863620'>our</span> <span
  m='863820'>annuity</span> <span m='864150'>problem,</span> <span
  m='866930'>we</span> <span m='867070'>can</span> <span m='867210'>plug</span>
  <span m='867610'>that</span> <span m='867840'>formula</span> <span
  m='869690'>back</span> <span m='869990'>in</span> <span
  m='870100'>here.</span> <span m='871660'>So</span> <span m='871850'>the</span>
  <span m='871920'>value</span> <span m='872430'>of</span> <span
  m='872510'>the</span> <span m='872610'>annuity</span> <span
  m='875010'>is</span> <span m='875320'>m</span> <span m='876280'>times</span>
  <span m='877580'>1</span> <span m='877810'>minus</span> <span
  m='878270'>x</span> <span m='878530'>to</span> <span m='878630'>the</span>
  <span m='878790'>n</span> <span m='879030'>over</span> <span
  m='879210'>1</span> <span m='879420'>minus</span> <span m='879770'>x.</span>
  <span m='881080'>We'll</span> <span m='881270'>plug</span> <span
  m='881675'>in</span> <span m='882080'>x</span> <span m='882410'>equals</span>
  <span m='884320'>1</span> <span m='884660'>over</span> <span
  m='884880'>1</span> <span m='885140'>plus</span> <span m='885460'>p,</span>
  <span m='887570'>and</span> <span m='887800'>we</span> <span
  m='887930'>get</span> <span m='889450'>m</span> <span m='890642'>1</span>
  <span m='891050'>minus</span> <span m='891590'>1</span> <span
  m='891860'>over</span> <span m='892120'>1</span> <span m='892440'>plus</span>
  <span m='892760'>p</span> <span m='894670'>to</span> <span
  m='894750'>the</span> <span m='894960'>n</span> <span m='896330'>over</span>
  <span m='896660'>1</span> <span m='896950'>minus</span> <span
  m='897330'>1</span> <span m='897550'>over</span> <span m='897740'>1</span>
  <span m='897970'>plus</span> <span m='898300'>p,</span> <span
  m='899870'>just</span> <span m='900050'>plugging</span> <span
  m='900440'>in.</span> <span m='901830'>And</span> <span m='902080'>now</span>
  <span m='902380'>to</span> <span m='902490'>simplify</span> <span
  m='903200'>this,</span> <span m='903510'>I'll</span> <span
  m='903630'>multiply</span> <span m='904160'>the</span> <span
  m='904260'>top</span> <span m='904650'>and</span> <span
  m='904780'>bottom</span> <span m='905150'>by</span> <span m='905290'>1</span>
  <span m='905520'>plus</span> <span m='905770'>p,</span> <span
  m='908970'>and</span> <span m='909160'>I'll</span> <span m='909220'>get</span>
  <span m='909420'>1</span> <span m='909660'>plus</span> <span
  m='909870'>p</span> <span m='910030'>minus</span> <span m='911110'>1</span>
  <span m='911450'>on</span> <span m='911510'>the</span> <span
  m='911570'>bottom.</span> <span m='911920'>Just</span> <span
  m='912070'>gives</span> <span m='912210'>me</span> <span m='912310'>a</span>
  <span m='912460'>p</span> <span m='912610'>on</span> <span
  m='912720'>the</span> <span m='912790'>bottom.</span> <span
  m='914080'>I</span> <span m='914140'>have</span> <span m='914200'>a</span>
  <span m='914260'>1</span> <span m='914460'>plus</span> <span
  m='914710'>p</span> <span m='914880'>on</span> <span m='914970'>the</span>
  <span m='915040'>top</span> <span m='916380'>minus</span> <span
  m='918160'>1</span> <span m='918520'>over</span> <span m='918790'>1</span>
  <span m='919040'>plus</span> <span m='919370'>p</span> <span
  m='921030'>to</span> <span m='921150'>the</span> <span m='921280'>n</span>
  <span m='921470'>minus</span> <span m='921880'>1,</span> <span
  m='922860'>all</span> <span m='923200'>over</span> <span m='923400'>p.</span>
  </p><p><span m='927740'>So</span> <span m='927850'>now</span> <span
  m='928160'>we</span> <span m='928300'>have</span> <span m='928670'>a</span>
  <span m='928770'>formula--</span> <span m='929460'>closed</span> <span
  m='929930'>form</span> <span m='930230'>expression</span> <span
  m='930850'>formula--</span> <span m='931840'>for</span> <span
  m='931980'>the</span> <span m='932060'>value</span> <span m='932510'>of</span>
  <span m='932580'>the</span> <span m='932680'>annuity.</span> <span
  m='933840'>All's</span> <span m='934040'>we've</span> <span
  m='934240'>got</span> <span m='934390'>to</span> <span m='934430'>plug</span>
  <span m='934665'>in</span> <span m='934900'>is</span> <span
  m='935500'>m,</span> <span m='936090'>the</span> <span
  m='936200'>payment</span> <span m='936630'>every</span> <span
  m='936870'>year,</span> <span m='937400'>n,</span> <span m='937710'>the</span>
  <span m='937770'>number</span> <span m='938060'>of</span> <span
  m='938150'>years,</span> <span m='939200'>and</span> <span
  m='939350'>then</span> <span m='939510'>p,</span> <span m='939880'>the</span>
  <span m='940010'>interest</span> <span m='940330'>rate.</span> <span
  m='941560'>And</span> <span m='941630'>so,</span> <span m='941870'>for</span>
  <span m='942180'>example,</span> <span m='946080'>if</span> <span
  m='946340'>we</span> <span m='946440'>made</span> <span m='947370'>m</span>
  <span m='947830'>be</span> <span m='947940'>$50,000,</span> <span
  m='951540'>as</span> <span m='951770'>in</span> <span m='951830'>the</span>
  <span m='951910'>lottery.</span> <span m='952390'>We</span> <span
  m='952500'>made</span> <span m='952760'>n</span> <span m='953130'>be</span>
  <span m='953240'>20</span> <span m='953600'>years,</span> <span
  m='955580'>and</span> <span m='955880'>say</span> <span m='956380'>we</span>
  <span m='956500'>took</span> <span m='956730'>6%</span> <span
  m='957360'>interest,</span> <span m='958420'>which</span> <span
  m='958640'>is</span> <span m='958760'>actually</span> <span
  m='959060'>very</span> <span m='959360'>good</span> <span
  m='959560'>these</span> <span m='959760'>days,</span> <span
  m='962050'>and</span> <span m='962170'>I</span> <span m='962230'>plug</span>
  <span m='962590'>those</span> <span m='962820'>in</span> <span
  m='962980'>here,</span> <span m='963710'>the</span> <span
  m='963830'>value</span> <span m='964330'>is</span> <span
  m='964440'>going</span> <span m='964570'>to</span> <span m='964640'>be</span>
  <span m='965960'>$607,906.</span> </p><p><span m='972710'>All</span> <span
  m='972920'>right.</span> <span m='973210'>So</span> <span
  m='973330'>those</span> <span m='973650'>of</span> <span m='973750'>you</span>
  <span m='973960'>that</span> <span m='974460'>preferred</span> <span
  m='975520'>700</span> <span m='976260'>grand--</span> <span
  m='976700'>if</span> <span m='976780'>you</span> <span
  m='976880'>assume</span> <span m='977160'>6%</span> <span
  m='977680'>interest--</span> <span m='978420'>you're</span> <span
  m='978600'>right.</span> <span m='979560'>Those</span> <span
  m='979860'>of</span> <span m='979885'>you</span> <span m='979910'>who</span>
  <span m='980050'>preferred</span> <span m='980440'>500</span> <span
  m='980960'>grand,</span> <span m='981470'>no,</span> <span
  m='981920'>you're</span> <span m='982080'>better</span> <span
  m='982280'>off</span> <span m='982450'>waiting</span> <span
  m='983310'>and</span> <span m='983450'>getting</span> <span
  m='983650'>your</span> <span m='983740'>50</span> <span
  m='984030'>grand</span> <span m='984310'>a</span> <span
  m='984370'>year.</span> </p><p><span m='985360'>Now,</span> <span
  m='985530'>of</span> <span m='985600'>course,</span> <span
  m='985900'>if</span> <span m='986000'>the</span> <span
  m='986120'>interest</span> <span m='986460'>rate</span> <span
  m='987110'>is</span> <span m='987310'>lower,</span> <span
  m='988500'>well,</span> <span m='988910'>that</span> <span
  m='989250'>changes</span> <span m='989700'>things.</span> <span
  m='991020'>That</span> <span m='991340'>shifts</span> <span
  m='991810'>it</span> <span m='991945'>even</span> <span
  m='992080'>more.</span> <span m='992800'>The</span> <span
  m='993230'>annuity</span> <span m='993570'>is</span> <span
  m='993670'>worth</span> <span m='993860'>even</span> <span
  m='994080'>more</span> <span m='994430'>if</span> <span m='994520'>the</span>
  <span m='994630'>interest</span> <span m='994930'>rate</span> <span
  m='995070'>is</span> <span m='995200'>lower--</span> <span
  m='996360'>if</span> <span m='996480'>p</span> <span m='996650'>is</span>
  <span m='996780'>smaller.</span> <span m='998540'>In</span> <span
  m='998690'>fact,</span> <span m='998970'>say</span> <span m='999250'>p</span>
  <span m='999510'>was</span> <span m='999670'>0.</span> <span
  m='1002400'>Say</span> <span m='1002670'>the</span> <span
  m='1002740'>interest</span> <span m='1003150'>rate</span> <span
  m='1003300'>is</span> <span m='1003390'>0,</span> <span m='1003870'>so</span>
  <span m='1004040'>$1</span> <span m='1004390'>today</span> <span
  m='1004580'>equals</span> <span m='1004770'>$1</span> <span
  m='1005050'>tomorrow,</span> <span m='1005310'>then</span> <span
  m='1005510'>what</span> <span m='1005760'>is</span> <span
  m='1005920'>the</span> <span m='1006180'>lottery</span> <span
  m='1006600'>worth?</span> <span m='1008350'>A</span> <span
  m='1008460'>million</span> <span m='1008800'>dollars.</span> <span
  m='1010130'>And</span> <span m='1010320'>the</span> <span
  m='1010390'>bigger</span> <span m='1010720'>p</span> <span
  m='1010970'>gets,</span> <span m='1011770'>the</span> <span
  m='1011890'>less</span> <span m='1012180'>your</span> <span
  m='1012290'>payment</span> <span m='1012660'>is</span> <span
  m='1012760'>worth.</span> <span m='1017660'>Any</span> <span
  m='1017840'>questions</span> <span m='1018250'>about</span> <span
  m='1018480'>that?</span> <span m='1021530'>OK.</span> </p><p><span
  m='1023320'>What</span> <span m='1023670'>if</span> <span
  m='1024900'>you</span> <span m='1025109'>were</span> <span
  m='1025250'>paid</span> <span m='1025800'>$50,000</span> <span
  m='1027450'>a</span> <span m='1027599'>year</span> <span
  m='1028010'>forever--</span> <span m='1029780'>you</span> <span
  m='1029950'>live</span> <span m='1030170'>forever</span> <span
  m='1031170'>or</span> <span m='1031460'>it</span> <span
  m='1031560'>goes</span> <span m='1031890'>to</span> <span
  m='1031980'>your</span> <span m='1032160'>estate</span> <span
  m='1032619'>and</span> <span m='1032740'>your</span> <span
  m='1032880'>heirs,</span> <span m='1033950'>$50,000</span> <span
  m='1035079'>a</span> <span m='1035150'>year</span> <span
  m='1035349'>forever</span> <span m='1036170'>or</span> <span
  m='1037640'>a</span> <span m='1037750'>million</span> <span
  m='1038140'>dollars</span> <span m='1038520'>today.</span> <span
  m='1041609'>How</span> <span m='1041770'>many</span> <span
  m='1041940'>people</span> <span m='1042250'>want</span> <span
  m='1042470'>the</span> <span m='1042510'>million</span> <span
  m='1042849'>dollars</span> <span m='1043180'>today?</span> <span
  m='1045200'>How</span> <span m='1045390'>many</span> <span
  m='1045560'>want</span> <span m='1045880'>50</span> <span
  m='1046319'>grand</span> <span m='1046730'>a</span> <span
  m='1046829'>year</span> <span m='1047150'>forever?</span> <span
  m='1049530'>Sounds</span> <span m='1050120'>good.</span> <span
  m='1050730'>You</span> <span m='1050860'>know,</span> <span
  m='1051480'>that's</span> <span m='1051550'>an</span> <span
  m='1051620'>infinite</span> <span m='1052020'>amount</span> <span
  m='1052300'>of</span> <span m='1052370'>money,</span> <span
  m='1052700'>sort</span> <span m='1053060'>of.</span> <span
  m='1054560'>It's</span> <span m='1054820'>not</span> <span
  m='1055070'>as</span> <span m='1055190'>good</span> <span
  m='1055340'>as</span> <span m='1055460'>it</span> <span
  m='1055580'>sounds.</span> <span m='1056190'>Let's</span> <span
  m='1056730'>see</span> <span m='1056930'>why.</span> </p><p><span
  m='1059290'>So</span> <span m='1059500'>this</span> <span
  m='1059700'>is</span> <span m='1059820'>a</span> <span m='1059890'>case</span>
  <span m='1060350'>where</span> <span m='1060750'>n</span> <span
  m='1060970'>equals</span> <span m='1061220'>infinity,</span> <span
  m='1065150'>and</span> <span m='1065590'>so</span> <span
  m='1065720'>I'll</span> <span m='1065810'>claim</span> <span
  m='1066320'>that</span> <span m='1066460'>if</span> <span m='1066880'>n</span>
  <span m='1067240'>equals</span> <span m='1067830'>infinity,</span> <span
  m='1070840'>then</span> <span m='1071060'>the</span> <span
  m='1071130'>value</span> <span m='1071800'>of</span> <span
  m='1071910'>this</span> <span m='1072140'>annuity</span> <span
  m='1074280'>is</span> <span m='1074460'>just</span> <span m='1075040'>m</span>
  <span m='1075280'>times</span> <span m='1075840'>1</span> <span
  m='1076100'>plus</span> <span m='1076420'>p</span> <span
  m='1076640'>over</span> <span m='1076830'>p.</span> <span
  m='1080100'>Let's</span> <span m='1080300'>see</span> <span
  m='1080430'>why</span> <span m='1080610'>that's</span> <span
  m='1080860'>the</span> <span m='1080930'>case.</span> <span
  m='1082880'>You</span> <span m='1082990'>know,</span> <span
  m='1083090'>it</span> <span m='1083170'>sounds</span> <span
  m='1083510'>hard</span> <span m='1083730'>to</span> <span
  m='1083840'>evaluate,</span> <span m='1084330'>because</span> <span
  m='1084510'>it's</span> <span m='1084580'>an</span> <span
  m='1084650'>infinite</span> <span m='1085010'>number</span> <span
  m='1085210'>of</span> <span m='1085290'>payments,</span> <span
  m='1087930'>but</span> <span m='1088140'>what</span> <span
  m='1088340'>happens</span> <span m='1088870'>here</span> <span
  m='1089200'>when</span> <span m='1089390'>n</span> <span
  m='1089610'>goes</span> <span m='1089850'>to</span> <span
  m='1089950'>infinity?</span> <span m='1092250'>What</span> <span
  m='1092340'>happens</span> <span m='1092690'>to</span> <span
  m='1092780'>this</span> <span m='1092970'>thing?</span> <span
  m='1095300'>That</span> <span m='1095490'>goes</span> <span
  m='1095740'>to</span> <span m='1095830'>0</span> <span m='1097150'>as</span>
  <span m='1097450'>n</span> <span m='1097790'>goes</span> <span
  m='1098040'>to</span> <span m='1098160'>infinity,</span> <span
  m='1098530'>as</span> <span m='1098620'>long</span> <span
  m='1098780'>as</span> <span m='1098890'>p</span> <span m='1099090'>is</span>
  <span m='1099230'>bigger</span> <span m='1099450'>than</span> <span
  m='1099590'>0.</span> </p><p><span m='1100000'>So</span> <span
  m='1100180'>we're</span> <span m='1100290'>going</span> <span
  m='1100410'>to</span> <span m='1100470'>assume</span> <span
  m='1100880'>6%</span> <span m='1101490'>interest.</span> <span
  m='1102800'>So</span> <span m='1102990'>that</span> <span
  m='1103200'>goes</span> <span m='1103420'>away,</span> <span
  m='1103940'>so</span> <span m='1103990'>the</span> <span
  m='1104100'>annuity</span> <span m='1104460'>is</span> <span
  m='1104590'>worth</span> <span m='1105050'>just</span> <span
  m='1105340'>that,</span> <span m='1105650'>m</span> <span
  m='1105840'>times</span> <span m='1106140'>1</span> <span
  m='1106440'>plus</span> <span m='1106720'>p</span> <span
  m='1106930'>over</span> <span m='1107120'>p,</span> <span
  m='1109200'>because</span> <span m='1109640'>the</span> <span
  m='1110340'>limit</span> <span m='1110690'>as</span> <span
  m='1110840'>n</span> <span m='1111000'>goes</span> <span m='1111240'>to</span>
  <span m='1111350'>infinity</span> <span m='1112810'>of</span> <span
  m='1113250'>1</span> <span m='1113580'>over</span> <span m='1113770'>1</span>
  <span m='1113960'>plus</span> <span m='1114270'>p</span> <span
  m='1114840'>to</span> <span m='1114930'>the</span> <span m='1115050'>n</span>
  <span m='1115180'>minus</span> <span m='1115530'>1,</span> <span
  m='1116550'>that's</span> <span m='1116860'>going</span> <span
  m='1117120'>to</span> <span m='1117200'>0.</span> <span m='1119890'>So</span>
  <span m='1120070'>the</span> <span m='1120150'>value</span> <span
  m='1122840'>for</span> <span m='1123250'>m</span> <span m='1123580'>is</span>
  <span m='1123760'>$50,000,</span> <span m='1128140'>and</span> <span
  m='1128450'>at</span> <span m='1128560'>6%</span> <span m='1132860'>V</span>
  <span m='1133190'>is</span> <span m='1133420'>only</span> <span
  m='1133800'>$883,000.</span> <span m='1142390'>So</span> <span
  m='1142590'>you're</span> <span m='1142710'>better</span> <span
  m='1143110'>off</span> <span m='1143370'>taking</span> <span
  m='1143660'>a</span> <span m='1143710'>million</span> <span
  m='1144060'>dollars</span> <span m='1144450'>today</span> <span
  m='1145700'>than</span> <span m='1145870'>$50,000</span> <span
  m='1146870'>a</span> <span m='1146950'>year</span> <span
  m='1147180'>forever.</span> </p><p><span m='1148780'>Now,</span> <span
  m='1149080'>if</span> <span m='1149240'>you</span> <span
  m='1149330'>think</span> <span m='1149620'>about</span> <span
  m='1149940'>it,</span> <span m='1150060'>and</span> <span
  m='1150190'>think</span> <span m='1150370'>about</span> <span
  m='1150570'>it</span> <span m='1150620'>as</span> <span m='1150670'>an</span>
  <span m='1150770'>interest</span> <span m='1151150'>rate,</span> <span
  m='1151790'>why</span> <span m='1152090'>should</span> <span
  m='1152270'>it</span> <span m='1152350'>be</span> <span
  m='1152660'>obvious</span> <span m='1153370'>that</span> <span
  m='1153470'>you're</span> <span m='1153590'>better</span> <span
  m='1153930'>off</span> <span m='1154160'>with</span> <span
  m='1154270'>a</span> <span m='1154310'>million</span> <span
  m='1154620'>dollars</span> <span m='1154950'>today</span> <span
  m='1156220'>than</span> <span m='1156390'>50</span> <span
  m='1156700'>grand</span> <span m='1157000'>a</span> <span
  m='1157080'>year</span> <span m='1157250'>forever?</span> <span
  m='1159180'>Think</span> <span m='1159400'>about</span> <span
  m='1159680'>what</span> <span m='1159860'>you</span> <span
  m='1159960'>could</span> <span m='1160130'>do</span> <span
  m='1160340'>with</span> <span m='1160460'>that</span> <span
  m='1160640'>million</span> <span m='1160930'>dollars</span> <span
  m='1161470'>if</span> <span m='1161570'>you</span> <span
  m='1161690'>had</span> <span m='1161870'>it</span> <span
  m='1161950'>today</span> <span m='1163990'>at</span> <span
  m='1164170'>6%</span> <span m='1164910'>interest.</span> <span
  m='1167790'>What</span> <span m='1168020'>would</span> <span
  m='1168130'>you</span> <span m='1168210'>do</span> <span
  m='1168420'>with</span> <span m='1168570'>it</span> <span
  m='1168680'>to</span> <span m='1169070'>make</span> <span
  m='1169320'>more</span> <span m='1169560'>money</span> <span
  m='1169880'>than</span> <span m='1171130'>50</span> <span
  m='1171420'>grand</span> <span m='1171710'>a</span> <span
  m='1171790'>year</span> <span m='1171950'>forever?</span> <span
  m='1172360'>Yeah.</span> </p><p><span m='1173752'>AUDIENCE: You</span> <span
  m='1174216'>could</span> <span m='1174293'>have</span> <span
  m='1174370'>like--</span> <span m='1174448'>you</span> <span
  m='1174525'>could</span> <span m='1174602'>make</span> <span
  m='1174680'>$50,000</span> <span m='1175610'>per</span> <span
  m='1175856'>year</span> <span m='1176102'>just off of</span> <span
  m='1176594'>[INAUDIBLE].</span> </p><p><span m='1178070'>PROFESSOR:
  Yeah.</span> <span m='1178420'>In</span> <span m='1178540'>this</span> <span
  m='1178740'>model,</span> <span m='1179480'>if</span> <span
  m='1179720'>the</span> <span m='1179820'>interest</span> <span
  m='1180030'>rate</span> <span m='1180150'>is</span> <span
  m='1180230'>6%,</span> <span m='1180850'>you</span> <span
  m='1180930'>can</span> <span m='1181030'>put</span> <span
  m='1181210'>in</span> <span m='1181270'>the</span> <span
  m='1181340'>bank.</span> <span m='1181820'>It</span> <span
  m='1182160'>makes</span> <span m='1182440'>6%</span> <span
  m='1182930'>every</span> <span m='1183100'>year,</span> <span
  m='1183220'>that's</span> <span m='1183370'>60</span> <span
  m='1183740'>grand</span> <span m='1184060'>a</span> <span
  m='1184140'>year</span> <span m='1184370'>forever.</span> <span
  m='1185300'>Better</span> <span m='1185570'>than</span> <span
  m='1185710'>50</span> <span m='1186020'>grand</span> <span
  m='1186280'>a</span> <span m='1186340'>year</span> <span
  m='1186750'>forever.</span> <span m='1188150'>So</span> <span
  m='1188290'>maybe</span> <span m='1188510'>it's--</span> <span
  m='1189456'>even</span> <span m='1189648'>without</span> <span
  m='1189840'>doing</span> <span m='1190000'>the</span> <span
  m='1190070'>math,</span> <span m='1190340'>you</span> <span
  m='1190440'>can</span> <span m='1190550'>tell</span> <span
  m='1190720'>which</span> <span m='1190890'>way</span> <span
  m='1191000'>it's</span> <span m='1191090'>going</span> <span
  m='1191210'>to</span> <span m='1191270'>go,</span> <span
  m='1191960'>but</span> <span m='1192090'>this</span> <span
  m='1192280'>tells</span> <span m='1192610'>you</span> <span
  m='1193070'>exactly</span> <span m='1193710'>what</span> <span
  m='1193850'>it's</span> <span m='1193990'>worth.</span> <span
  m='1198460'>Any</span> <span m='1198640'>questions?</span> <span
  m='1202340'>OK.</span> <span m='1204380'>Yeah.</span> </p><p><span
  m='1204862'>AUDIENCE:</span> <span m='1205344'>[INAUDIBLE]</span> <span
  m='1205826'>current</span> <span m='1206308'>value--</span> <span
  m='1206428'>that's</span> <span m='1206549'>how</span> <span
  m='1206669'>much</span> <span m='1206790'>it's</span> <span
  m='1207272'>worth</span> <span m='1207754'>to</span> <span
  m='1207874'>you</span> <span m='1207995'>right</span> <span
  m='1208115'>now.</span> </p><p><span m='1208720'>PROFESSOR: Yeah.</span>
  </p><p><span m='1209220'>AUDIENCE:  So</span> <span m='1209720'>and,</span>
  <span m='1211220'>like,</span> <span m='1212220'>if you</span> <span
  m='1212720'>have</span> <span m='1212970'>$1</span> <span
  m='1213220'>in</span> <span m='1213386'>the</span> <span
  m='1213553'>future--</span> </p><p><span m='1214010'>PROFESSOR: Yeah.</span>
  </p><p><span m='1215086'>AUDIENCE: --where</span> <span m='1215534'>S</span>
  <span m='1215758'>right</span> <span m='1215982'>now</span> <span
  m='1216430'>is</span> <span m='1216878'>m</span> <span m='1216967'>over</span>
  <span m='1217057'>1</span> <span m='1217146'>plus</span> <span
  m='1217236'>p--</span> </p><p><span m='1218230'>PROFESSOR:  Yeah.</span>
  </p><p><span m='1218535'>AUDIENCE:</span> <span m='1218611'>--is</span> <span
  m='1218687'>it</span> <span m='1218763'>worth</span> <span
  m='1218840'>less</span> <span m='1218994'>to</span> <span
  m='1219148'>you</span> <span m='1219302'>[INAUDIBLE]</span> <span
  m='1219764'>then</span> <span m='1220226'>later</span> <span
  m='1220688'>on,</span> <span m='1220919'>it's</span> <span
  m='1221150'>going</span> <span m='1221304'>to</span> <span
  m='1221458'>be</span> <span m='1221612'>worth</span> <span
  m='1221727'>more</span> <span m='1221843'>to</span> <span
  m='1221958'>you.</span> </p><p><span m='1223000'>PROFESSOR: Ah,</span> <span
  m='1223150'>so</span> <span m='1223740'>if</span> <span m='1223890'>you</span>
  <span m='1224020'>move</span> <span m='1224370'>yourself</span> <span
  m='1224930'>forward</span> <span m='1225220'>in</span> <span
  m='1225330'>time,</span> <span m='1225870'>$1</span> <span
  m='1226440'>a</span> <span m='1226560'>year,</span> <span
  m='1226980'>in</span> <span m='1227230'>a</span> <span m='1227480'>year</span>
  <span m='1227535'>it'll</span> <span m='1227590'>worth</span> <span
  m='1227810'>$1</span> <span m='1228197'>to</span> <span
  m='1228390'>you--</span> </p><p><span m='1228584'>AUDIENCE: Yeah.</span>
  </p><p><span m='1229360'>PROFESSOR: --but</span> <span
  m='1229550'>today</span> <span m='1231030'>it's</span> <span
  m='1231240'>worth</span> <span m='1231540'>less</span> <span
  m='1231810'>than</span> <span m='1231910'>$1</span> <span
  m='1232290'>to</span> <span m='1232420'>you,</span> <span
  m='1232490'>because</span> <span m='1232640'>you</span> <span
  m='1232750'>could</span> <span m='1232900'>take</span> <span
  m='1234020'>the</span> <span m='1234140'>dollar</span> <span
  m='1234460'>today</span> <span m='1234690'>and</span> <span
  m='1234780'>invest</span> <span m='1235070'>in</span> <span
  m='1235150'>the</span> <span m='1235230'>bank,</span> <span
  m='1235520'>and</span> <span m='1235620'>it's</span> <span
  m='1235910'>worth</span> <span m='1236190'>more</span> <span
  m='1236500'>in</span> <span m='1236570'>a</span> <span
  m='1236630'>year,</span> <span m='1237680'>because</span> <span
  m='1237850'>the</span> <span m='1237910'>money</span> <span
  m='1238180'>grows</span> <span m='1238570'>in</span> <span
  m='1238680'>value,</span> <span m='1239950'>as</span> <span
  m='1240060'>a</span> <span m='1240090'>way</span> <span m='1240200'>to</span>
  <span m='1240270'>think</span> <span m='1240490'>of</span> <span
  m='1240580'>it,</span> <span m='1241700'>because</span> <span
  m='1241890'>you</span> <span m='1241980'>can</span> <span
  m='1242190'>earn</span> <span m='1242360'>interest</span> <span
  m='1242680'>on</span> <span m='1242820'>it.</span> <span
  m='1243510'>What's</span> <span m='1243690'>that?</span> </p><p><span
  m='1244104'>AUDIENCE:</span> <span m='1244518'>You</span> <span
  m='1244725'>could</span> <span m='1244932'>spend</span> <span
  m='1245139'>it.</span> </p><p><span m='1245760'>PROFESSOR: Yeah.</span> <span
  m='1246480'>Yeah,</span> <span m='1246850'>if</span> <span
  m='1246910'>you</span> <span m='1246970'>just</span> <span
  m='1247030'>spend</span> <span m='1247380'>it,</span> <span
  m='1247680'>well,</span> <span m='1248030'>then</span> <span
  m='1248170'>at</span> <span m='1248270'>least</span> <span
  m='1248470'>you</span> <span m='1248550'>had</span> <span
  m='1248690'>the</span> <span m='1248790'>use</span> <span
  m='1249110'>of</span> <span m='1249210'>what</span> <span
  m='1249360'>you</span> <span m='1249440'>spent</span> <span
  m='1249690'>it</span> <span m='1249770'>on</span> <span m='1249910'>for</span>
  <span m='1250030'>the</span> <span m='1250130'>year.</span> <span
  m='1251100'>So</span> <span m='1251150'>there's</span> <span
  m='1251300'>some</span> <span m='1251470'>other</span> <span
  m='1251670'>kind</span> <span m='1251910'>of</span> <span
  m='1251980'>value,</span> <span m='1252500'>right?</span> <span
  m='1252800'>Maybe</span> <span m='1252940'>you</span> <span
  m='1253400'>bought</span> <span m='1253640'>a</span> <span
  m='1253700'>house</span> <span m='1254210'>or</span> <span
  m='1254950'>something</span> <span m='1255660'>that--</span> <span
  m='1256310'>maybe</span> <span m='1256540'>something</span> <span
  m='1256750'>that</span> <span m='1256840'>even</span> <span
  m='1257020'>appreciated</span> <span m='1257560'>in</span> <span
  m='1257640'>value.</span> <span m='1259410'>OK.</span> </p><p><span
  m='1260610'>But</span> <span m='1261000'>these</span> <span
  m='1261210'>things</span> <span m='1261480'>get</span> <span
  m='1262750'>sort</span> <span m='1263370'>of</span> <span
  m='1263440'>squishy,</span> <span m='1264650'>and</span> <span
  m='1264800'>that</span> <span m='1264940'>is</span> <span
  m='1265170'>where</span> <span m='1265360'>a</span> <span
  m='1265420'>lot</span> <span m='1265530'>of</span> <span
  m='1265590'>people</span> <span m='1265770'>make</span> <span
  m='1266290'>money</span> <span m='1266520'>on</span> <span
  m='1266610'>Wall</span> <span m='1266780'>Street,</span> <span
  m='1267510'>is</span> <span m='1267700'>because</span> <span
  m='1268170'>different</span> <span m='1268460'>companies</span> <span
  m='1268890'>have</span> <span m='1269030'>different</span> <span
  m='1269330'>needs</span> <span m='1269940'>for</span> <span
  m='1270060'>money.</span> <span m='1270330'>They</span> <span
  m='1270410'>have</span> <span m='1270500'>different</span> <span
  m='1270780'>views</span> <span m='1271040'>of</span> <span
  m='1271100'>what</span> <span m='1271220'>the</span> <span
  m='1271310'>interest</span> <span m='1271630'>rates</span> <span
  m='1271820'>are</span> <span m='1271860'>going</span> <span
  m='1271980'>to</span> <span m='1272040'>be,</span> <span
  m='1272190'>and</span> <span m='1272290'>you</span> <span
  m='1272360'>can</span> <span m='1272470'>play</span> <span
  m='1272700'>in</span> <span m='1272770'>the</span> <span
  m='1272830'>middle</span> <span m='1274180'>and</span> <span
  m='1274820'>make</span> <span m='1275040'>a</span> <span
  m='1275090'>lot</span> <span m='1275250'>of</span> <span
  m='1275310'>money</span> <span m='1275500'>that</span> <span
  m='1275720'>way.</span> </p><p><span m='1295220'>So</span> <span
  m='1295850'>more</span> <span m='1296030'>generally,</span> <span
  m='1296840'>there's</span> <span m='1297030'>a</span> <span
  m='1297070'>corollary</span> <span m='1297630'>to</span> <span
  m='1297720'>the</span> <span m='1297800'>theorem,</span> <span
  m='1299620'>and</span> <span m='1299710'>that</span> <span
  m='1299910'>is</span> <span m='1300290'>that</span> <span
  m='1300810'>if</span> <span m='1300960'>the</span> <span
  m='1301080'>absolute</span> <span m='1301520'>value</span> <span
  m='1301790'>of</span> <span m='1301880'>x</span> <span m='1302150'>is</span>
  <span m='1302290'>less</span> <span m='1302600'>than</span> <span
  m='1302730'>1,</span> <span m='1304030'>then</span> <span
  m='1304210'>the</span> <span m='1304280'>sum</span> <span m='1305960'>i</span>
  <span m='1306350'>equals</span> <span m='1306500'>0</span> <span
  m='1308100'>to</span> <span m='1308250'>infinity</span> <span
  m='1309820'>x</span> <span m='1310080'>to</span> <span m='1310180'>the</span>
  <span m='1310330'>i</span> <span m='1311650'>is</span> <span
  m='1311870'>just</span> <span m='1312210'>1</span> <span
  m='1312440'>over</span> <span m='1312650'>1</span> <span
  m='1312870'>minus</span> <span m='1313220'>x.</span> <span
  m='1316080'>We</span> <span m='1316180'>didn't</span> <span
  m='1316470'>prove</span> <span m='1316800'>this</span> <span
  m='1317920'>back</span> <span m='1318210'>in</span> <span
  m='1318290'>the</span> <span m='1318360'>second</span> <span
  m='1318700'>recitation,</span> <span m='1319350'>because</span> <span
  m='1320030'>there's</span> <span m='1320220'>no</span> <span
  m='1320420'>n</span> <span m='1320710'>to</span> <span
  m='1320830'>induct</span> <span m='1321240'>on</span> <span
  m='1321390'>here,</span> <span m='1322130'>but</span> <span
  m='1322300'>the</span> <span m='1322390'>proof</span> <span
  m='1322680'>is</span> <span m='1322790'>simple</span> <span
  m='1323320'>from</span> <span m='1323510'>the</span> <span
  m='1323570'>theorem.</span> <span m='1325220'>And</span> <span
  m='1325400'>it's</span> <span m='1325500'>simply</span> <span
  m='1325770'>because</span> <span m='1326900'>if</span> <span
  m='1327070'>x</span> <span m='1327470'>is</span> <span m='1327600'>less</span>
  <span m='1327820'>than</span> <span m='1327920'>1,</span> <span
  m='1328060'>an</span> <span m='1328150'>absolute</span> <span
  m='1328550'>value,</span> <span m='1329340'>as</span> <span
  m='1329550'>n</span> <span m='1329740'>goes</span> <span m='1329970'>to</span>
  <span m='1330070'>infinity,</span> <span m='1331510'>that</span> <span
  m='1331750'>goes</span> <span m='1332010'>to</span> <span
  m='1332100'>0,</span> <span m='1333330'>and</span> <span m='1333490'>so</span>
  <span m='1333560'>you're</span> <span m='1333620'>just</span> <span
  m='1333890'>left</span> <span m='1334100'>with</span> <span
  m='1334210'>1</span> <span m='1334410'>over</span> <span m='1334550'>1</span>
  <span m='1334720'>minus</span> <span m='1335040'>x.</span> </p><p><span
  m='1346650'>So,</span> <span m='1346990'>for</span> <span
  m='1347130'>example,</span> <span m='1350770'>what's</span> <span
  m='1351210'>this</span> <span m='1351500'>sum?</span> <span
  m='1351680'>This</span> <span m='1351830'>one</span> <span
  m='1351990'>you</span> <span m='1352090'>all</span> <span
  m='1352280'>know,</span> <span m='1352500'>I'm</span> <span
  m='1352620'>sure.</span> <span m='1357010'>Out</span> <span
  m='1357220'>to</span> <span m='1357330'>infinity.</span> <span
  m='1357880'>What's</span> <span m='1358000'>that</span> <span
  m='1358190'>sum</span> <span m='1358440'>to?</span> <span
  m='1360970'>To</span> <span m='1361160'>2.</span> <span
  m='1361600'>Yeah.</span> <span m='1362250'>It's</span> <span
  m='1362860'>1</span> <span m='1363180'>over</span> <span m='1363450'>1</span>
  <span m='1363720'>minus</span> <span m='1364110'>1/2,</span> <span
  m='1365480'>which</span> <span m='1365700'>is</span> <span
  m='1365820'>2.</span> <span m='1367710'>What</span> <span
  m='1367940'>about</span> <span m='1368380'>this</span> <span
  m='1368849'>sum</span> <span m='1374740'>out</span> <span
  m='1374940'>to</span> <span m='1375030'>infinity?</span> <span
  m='1375370'>What</span> <span m='1375520'>does</span> <span
  m='1375600'>that</span> <span m='1375780'>sum</span> <span
  m='1376040'>to?</span> </p><p><span m='1379263'>AUDIENCE:</span> <span
  m='1379696'>[INAUDIBLE]</span> </p><p><span m='1381430'>PROFESSOR:
  Yeah,</span> <span m='1382090'>3/2,</span> <span m='1383400'>1 over</span>
  <span m='1383650'>1</span> <span m='1383890'>minus</span> <span
  m='1384240'>1/3</span> <span m='1384738'>is</span> <span
  m='1385236'>3/2.</span> <span m='1387700'>So,</span> <span
  m='1387820'>easy</span> <span m='1388150'>corollaries.</span> <span
  m='1389920'>These</span> <span m='1390150'>are</span> <span
  m='1390210'>all</span> <span m='1390410'>examples</span> <span
  m='1390910'>of</span> <span m='1390990'>geometric</span> <span
  m='1391660'>series.</span> <span m='1392460'>That's</span> <span
  m='1392680'>what</span> <span m='1392780'>a</span> <span
  m='1392820'>definition</span> <span m='1393330'>of</span> <span
  m='1393390'>a</span> <span m='1393430'>geometric</span> <span
  m='1393950'>series</span> <span m='1394400'>is.</span> <span
  m='1394600'>Something</span> <span m='1394880'>that's</span> <span
  m='1395000'>going</span> <span m='1395260'>down</span> <span
  m='1395480'>by</span> <span m='1395620'>a</span> <span
  m='1395670'>fixed--</span> <span m='1396410'>each</span> <span
  m='1396620'>term</span> <span m='1396810'>goes</span> <span
  m='1396970'>down</span> <span m='1397130'>by</span> <span
  m='1397420'>the</span> <span m='1397540'>same</span> <span
  m='1397820'>fixed</span> <span m='1398120'>amount</span> <span
  m='1398360'>every</span> <span m='1398520'>time.</span> <span
  m='1399490'>And</span> <span m='1399700'>geometric</span> <span
  m='1400250'>series,</span> <span m='1401310'>generally</span> <span
  m='1401850'>sum</span> <span m='1402580'>to</span> <span
  m='1403440'>something</span> <span m='1403830'>that</span> <span
  m='1404190'>is</span> <span m='1404350'>very</span> <span
  m='1404550'>close</span> <span m='1404910'>to</span> <span
  m='1404990'>the</span> <span m='1405070'>largest</span> <span
  m='1405550'>term.</span> <span m='1406140'>In</span> <span
  m='1406280'>this</span> <span m='1406430'>case,</span> <span
  m='1406730'>it's</span> <span m='1407030'>1.</span> <span
  m='1408590'>Very</span> <span m='1408870'>common,</span> <span
  m='1410410'>because</span> <span m='1410730'>of</span> <span
  m='1410790'>that</span> <span m='1410940'>formula.</span> <span
  m='1411380'>It's</span> <span m='1411495'>1</span> <span
  m='1411610'>over</span> <span m='1411740'>1</span> <span
  m='1411950'>minus</span> <span m='1412280'>x.</span> <span
  m='1420270'>Any</span> <span m='1420450'>questions</span> <span
  m='1421280'>about</span> <span m='1422400'>this</span> <span
  m='1422710'>or</span> <span m='1422770'>geometric</span> <span
  m='1423220'>series?</span> <span m='1426760'>All</span> <span
  m='1426820'>right.</span> </p><p><span m='1428280'>Well,</span> <span
  m='1429220'>those</span> <span m='1429550'>are</span> <span
  m='1429640'>straight</span> <span m='1430100'>geometric</span> <span
  m='1430680'>sums.</span> <span m='1431140'>Sometimes</span> <span
  m='1431810'>you</span> <span m='1431930'>run</span> <span
  m='1432130'>into</span> <span m='1432280'>things</span> <span
  m='1432650'>that</span> <span m='1432750'>are</span> <span
  m='1432790'>a</span> <span m='1432840'>little</span> <span
  m='1433140'>bit</span> <span m='1433300'>more</span> <span
  m='1433500'>complicated.</span> <span m='1434930'>For</span> <span
  m='1435050'>example,</span> <span m='1436900'>say</span> <span
  m='1437170'>I</span> <span m='1437250'>have</span> <span
  m='1437650'>this</span> <span m='1437830'>kind</span> <span
  m='1438010'>of</span> <span m='1438070'>a</span> <span m='1438110'>sum,</span>
  <span m='1438670'>i</span> <span m='1438980'>equals</span> <span
  m='1439400'>1</span> <span m='1439700'>to</span> <span m='1439850'>n,</span>
  <span m='1441570'>i</span> <span m='1441930'>times</span> <span
  m='1442650'>x</span> <span m='1442920'>to</span> <span m='1443030'>the</span>
  <span m='1443130'>i.</span> <span m='1445030'>Now,</span> <span
  m='1445145'>those</span> <span m='1445260'>are</span> <span
  m='1445360'>adding</span> <span m='1445740'>up</span> <span
  m='1445990'>x</span> <span m='1446470'>plus</span> <span m='1446790'>2x</span>
  <span m='1447350'>squared</span> <span m='1448430'>plus</span> <span
  m='1448710'>3x</span> <span m='1449340'>cubed,</span> <span
  m='1451100'>and</span> <span m='1451210'>so</span> <span
  m='1451450'>forth,</span> <span m='1452420'>up</span> <span
  m='1452640'>to</span> <span m='1453000'>n</span> <span m='1453560'>x</span>
  <span m='1453850'>to</span> <span m='1453960'>the</span> <span
  m='1454110'>n.</span> <span m='1456780'>You</span> <span
  m='1456870'>know,</span> <span m='1456950'>that's</span> <span
  m='1457150'>a</span> <span m='1457200'>little</span> <span
  m='1457410'>more</span> <span m='1457550'>complicated.</span> <span
  m='1458160'>The</span> <span m='1458220'>terms</span> <span
  m='1458680'>are</span> <span m='1458730'>getting--</span> <span
  m='1460610'>decreasing</span> <span m='1461480'>by</span> <span
  m='1461630'>a</span> <span m='1461690'>factor</span> <span
  m='1462010'>of</span> <span m='1462100'>x,</span> <span
  m='1462520'>increasing</span> <span m='1463090'>by</span> <span
  m='1463230'>1</span> <span m='1463620'>in</span> <span
  m='1463700'>terms</span> <span m='1463940'>of</span> <span
  m='1464000'>the</span> <span m='1464060'>coefficient</span> <span
  m='1464680'>every</span> <span m='1464880'>time.</span> <span
  m='1465420'>A</span> <span m='1465450'>little</span> <span
  m='1465630'>trickier.</span> </p><p><span m='1467200'>So</span> <span
  m='1467240'>say</span> <span m='1467510'>we</span> <span
  m='1467630'>wanted</span> <span m='1467910'>to</span> <span
  m='1468030'>get</span> <span m='1468220'>a</span> <span
  m='1468280'>closed</span> <span m='1468910'>form</span> <span
  m='1469210'>expression</span> <span m='1469760'>for</span> <span
  m='1469890'>that?</span> <span m='1471280'>There</span> <span
  m='1471390'>are</span> <span m='1471430'>several</span> <span
  m='1471760'>ways</span> <span m='1472140'>we</span> <span
  m='1472240'>can</span> <span m='1472410'>do</span> <span
  m='1472620'>it.</span> <span m='1473130'>The</span> <span
  m='1473270'>first</span> <span m='1473680'>would</span> <span
  m='1473790'>be</span> <span m='1473890'>to</span> <span m='1473990'>try</span>
  <span m='1474220'>to</span> <span m='1474360'>use</span> <span
  m='1475370'>perturbation--</span> <span m='1476450'>the</span> <span
  m='1476590'>perturbation</span> <span m='1477190'>method.</span> <span
  m='1477900'>Let's</span> <span m='1478560'>try</span> <span
  m='1478860'>that.</span> <span m='1480730'>So</span> <span
  m='1480810'>we</span> <span m='1480890'>write</span> <span
  m='1481220'>S</span> <span m='1481600'>equals</span> <span
  m='1482090'>x</span> <span m='1482490'>plus</span> <span m='1482770'>2x</span>
  <span m='1483260'>squared</span> <span m='1483880'>plus</span> <span
  m='1484150'>3x</span> <span m='1484930'>cubed</span> <span
  m='1486990'>plus</span> <span m='1487460'>nx</span> <span
  m='1488370'>to</span> <span m='1488460'>the</span> <span m='1488630'>n,</span>
  <span m='1490220'>and</span> <span m='1490400'>let's</span> <span
  m='1490550'>try</span> <span m='1490780'>the</span> <span
  m='1490870'>same</span> <span m='1491170'>perturbation.</span> <span
  m='1491920'>Multiply</span> <span m='1492420'>by</span> <span
  m='1492610'>x,</span> <span m='1494960'>I</span> <span m='1495150'>get</span>
  <span m='1495550'>that</span> <span m='1496190'>x</span> <span
  m='1496470'>squared</span> <span m='1497610'>plus</span> <span
  m='1497910'>2x</span> <span m='1498377'>cubed</span> <span
  m='1501180'>plus</span> <span m='1501710'>n</span> <span
  m='1501980'>minus</span> <span m='1502380'>1x</span> <span
  m='1503190'>to</span> <span m='1503270'>the</span> <span m='1503440'>n,</span>
  <span m='1504280'>plus</span> <span m='1505050'>nx</span> <span
  m='1506240'>to</span> <span m='1506300'>the</span> <span m='1506640'>n</span>
  <span m='1506770'>plus</span> <span m='1506900'>1.</span> <span
  m='1509420'>And</span> <span m='1509730'>then</span> <span
  m='1509970'>I</span> <span m='1510300'>subtract</span> <span
  m='1511190'>to</span> <span m='1511340'>try</span> <span m='1511510'>to</span>
  <span m='1511590'>get</span> <span m='1511720'>all</span> <span
  m='1511830'>the</span> <span m='1511900'>cancellation.</span> </p><p><span
  m='1515220'>So</span> <span m='1515460'>then</span> <span m='1515580'>I</span>
  <span m='1516970'>do</span> <span m='1517160'>that.</span> <span
  m='1517410'>I</span> <span m='1517440'>get</span> <span m='1517600'>1</span>
  <span m='1517790'>minus</span> <span m='1518160'>x</span> <span
  m='1518450'>times</span> <span m='1518830'>S.</span> <span
  m='1521230'>Well,</span> <span m='1521400'>I</span> <span
  m='1521450'>didn't</span> <span m='1521660'>quite</span> <span
  m='1522320'>cancel</span> <span m='1523100'>everything.</span> <span
  m='1524540'>X</span> <span m='1525020'>plus</span> <span m='1525920'>x</span>
  <span m='1526290'>squared</span> <span m='1527840'>plus</span> <span
  m='1528420'>x</span> <span m='1528520'>cubed</span> <span
  m='1531240'>plus</span> <span m='1531670'>x</span> <span m='1531960'>to</span>
  <span m='1532050'>the</span> <span m='1532220'>n</span> <span
  m='1533120'>plus</span> <span m='1533640'>n--</span> <span
  m='1534610'>or</span> <span m='1534740'>minus</span> <span
  m='1535750'>nx</span> <span m='1536340'>to</span> <span m='1536430'>the</span>
  <span m='1536750'>n</span> <span m='1536880'>plus</span> <span
  m='1537010'>1.</span> <span m='1537960'>Ah,</span> <span m='1538310'>it</span>
  <span m='1538425'>didn't</span> <span m='1538540'>quite</span> <span
  m='1538800'>work.</span> <span m='1541010'>Anybody</span> <span
  m='1541380'>see</span> <span m='1541590'>a</span> <span m='1541660'>way</span>
  <span m='1541880'>that</span> <span m='1542010'>I</span> <span
  m='1542120'>can</span> <span m='1542660'>fix</span> <span
  m='1542980'>this</span> <span m='1543230'>up?</span> <span
  m='1549480'>What</span> <span m='1549620'>about</span> <span
  m='1549860'>this</span> <span m='1550050'>piece?</span> <span
  m='1551610'>That's</span> <span m='1551830'>still</span> <span
  m='1552170'>a</span> <span m='1552230'>mess</span> <span
  m='1552560'>here.</span> <span m='1553020'>Can</span> <span
  m='1553170'>I</span> <span m='1553250'>simplify</span> <span
  m='1553770'>that?</span> <span m='1556240'>Yeah?</span> </p><p><span
  m='1557522'>AUDIENCE:</span> <span m='1557998'>[INAUDIBLE]</span> </p><p><span
  m='1565150'>PROFESSOR: Yeah.</span> <span m='1567090'>There's</span>
  </p><p><span m='1567260'>a</span> <span m='1567320'>simpler</span> <span
  m='1567910'>way.</span> <span m='1568990'>Yeah.</span> </p><p><span
  m='1569882'>AUDIENCE:</span> <span m='1570030'>That's</span> <span
  m='1570179'>a</span> <span m='1570328'>geometric</span> <span
  m='1570551'>series.</span> </p><p><span m='1571220'>PROFESSOR: That's</span>
  <span m='1571430'>a</span> <span m='1571470'>geometric</span> <span
  m='1571950'>series.</span> <span m='1573160'>We</span> <span
  m='1573240'>just</span> <span m='1573530'>got</span> <span
  m='1573710'>the</span> <span m='1573780'>formula</span> <span
  m='1574280'>for</span> <span m='1574590'>it,</span> <span
  m='1574900'>so</span> <span m='1575000'>that's</span> <span
  m='1575280'>easy.</span> <span m='1576360'>This</span> <span
  m='1577490'>equals</span> <span m='1579790'>1</span> <span
  m='1580130'>minus</span> <span m='1580560'>x</span> <span
  m='1580820'>to</span> <span m='1580910'>the</span> <span m='1581060'>n</span>
  <span m='1581400'>over</span> <span m='1581710'>1</span> <span
  m='1582010'>minus</span> <span m='1582410'>x</span> <span
  m='1583640'>minus</span> <span m='1584130'>the</span> <span
  m='1584620'>1,</span> <span m='1585140'>because</span> <span
  m='1585300'>I'm</span> <span m='1585410'>missing</span> <span
  m='1585750'>the</span> <span m='1585830'>1</span> <span
  m='1586090'>here.</span> <span m='1586910'>So</span> <span
  m='1587080'>we</span> <span m='1587180'>can</span> <span
  m='1587340'>rewrite</span> <span m='1587730'>this</span> <span
  m='1587900'>whole</span> <span m='1588130'>thing</span> <span
  m='1588400'>over</span> <span m='1588570'>here.</span> <span
  m='1599720'>Oops.</span> <span m='1600050'>Yikes.</span> <span
  m='1600540'>Got</span> <span m='1601010'>attacked.</span> <span
  m='1609880'>What's</span> <span m='1610080'>that?</span> </p><p><span
  m='1610560'>AUDIENCE:</span> <span m='1611040'>Would it be</span> <span
  m='1611520'>1 minus x</span> <span m='1612000'>should be</span> <span
  m='1612480'>n plus</span> <span m='1612973'>1?</span> </p><p><span
  m='1613960'>PROFESSOR: Yes</span> <span m='1615790'>it</span> <span
  m='1615940'>would.</span> <span m='1616710'>That's</span> <span
  m='1616980'>right.</span> <span m='1617360'>I've</span> <span
  m='1617420'>got</span> <span m='1617540'>to</span> <span
  m='1617600'>add</span> <span m='1617810'>1</span> <span m='1618010'>to</span>
  <span m='1618120'>there.</span> <span m='1619630'>OK.</span> <span
  m='1620200'>So</span> <span m='1621100'>that's</span> <span
  m='1621340'>good.</span> <span m='1622630'>So</span> <span
  m='1622820'>that</span> <span m='1623030'>says</span> <span
  m='1623500'>that</span> <span m='1624790'>1</span> <span
  m='1625180'>minus</span> <span m='1625690'>x</span> <span
  m='1627210'>times</span> <span m='1627530'>S</span> <span
  m='1628040'>equals</span> <span m='1628930'>1</span> <span
  m='1629230'>minus</span> <span m='1629630'>x</span> <span
  m='1629890'>to</span> <span m='1629980'>the</span> <span m='1630110'>n</span>
  <span m='1630270'>plus</span> <span m='1630610'>1</span> <span
  m='1631520'>over</span> <span m='1631720'>1</span> <span
  m='1631930'>minus</span> <span m='1632440'>x</span> <span
  m='1633360'>minus</span> <span m='1633870'>1,</span> <span
  m='1635320'>and</span> <span m='1635460'>then</span> <span
  m='1635570'>I've</span> <span m='1635620'>got</span> <span
  m='1635770'>to</span> <span m='1635830'>remember</span> <span
  m='1636100'>to</span> <span m='1636390'>subtract</span> <span
  m='1636850'>that</span> <span m='1637050'>term</span> <span
  m='1637250'>too.</span> <span m='1637650'>Minus</span> <span
  m='1638020'>nx</span> <span m='1639020'>to</span> <span m='1639150'>the</span>
  <span m='1639280'>n</span> <span m='1639410'>plus</span> <span
  m='1639700'>1.</span> <span m='1641630'>That</span> <span
  m='1641920'>means</span> <span m='1642310'>now</span> <span
  m='1642490'>I</span> <span m='1642570'>just</span> <span
  m='1642750'>divide</span> <span m='1643140'>through,</span> <span
  m='1644700'>and</span> <span m='1644910'>I</span> <span
  m='1645010'>simplify--</span> <span m='1645770'>divide</span> <span
  m='1646120'>through</span> <span m='1646230'>by</span> <span
  m='1646360'>1</span> <span m='1646540'>minus</span> <span
  m='1646840'>x--</span> <span m='1647050'>and</span> <span
  m='1647160'>simplify,</span> <span m='1647990'>and</span> <span
  m='1648110'>I</span> <span m='1648170'>get</span> <span m='1648340'>the</span>
  <span m='1648410'>following</span> <span m='1648810'>formula.</span> <span
  m='1650070'>I</span> <span m='1650190'>won't</span> <span
  m='1650490'>go</span> <span m='1650640'>through</span> <span
  m='1650820'>all</span> <span m='1650930'>the</span> <span
  m='1651010'>details,</span> <span m='1651470'>but</span> <span
  m='1651570'>it's</span> <span m='1651690'>not</span> <span
  m='1651890'>hard.</span> </p><p><span m='1665460'>Let's</span> <span
  m='1666520'>see</span> <span m='1666690'>if</span> <span m='1666750'>I</span>
  <span m='1666810'>got</span> <span m='1667000'>that</span> <span
  m='1667230'>right.</span> <span m='1668590'>Yeah,</span> <span
  m='1669060'>that</span> <span m='1669140'>looks</span> <span
  m='1669400'>right.</span> <span m='1670450'>OK,</span> <span
  m='1670760'>so</span> <span m='1670900'>that</span> <span
  m='1671150'>is</span> <span m='1671460'>the</span> <span
  m='1671540'>closed</span> <span m='1672000'>form</span> <span
  m='1672230'>expression</span> <span m='1672780'>for</span> <span
  m='1672870'>that</span> <span m='1673070'>sum,</span> <span
  m='1674540'>which</span> <span m='1674750'>we</span> <span
  m='1674840'>can</span> <span m='1675000'>get</span> <span
  m='1675180'>from</span> <span m='1675310'>the</span> <span
  m='1675390'>perturbation</span> <span m='1676010'>method</span> <span
  m='1676380'>and</span> <span m='1676500'>the</span> <span
  m='1676560'>fact</span> <span m='1676850'>that</span> <span
  m='1676950'>we'd</span> <span m='1677070'>already</span> <span
  m='1677380'>done</span> <span m='1677690'>the</span> <span
  m='1677760'>geometric</span> <span m='1678270'>series.</span> </p><p><span
  m='1680940'>There's</span> <span m='1681130'>another</span> <span
  m='1681510'>way</span> <span m='1681780'>to</span> <span
  m='1681850'>compute</span> <span m='1682270'>these</span> <span
  m='1682450'>kinds</span> <span m='1682780'>of</span> <span
  m='1684020'>sums,</span> <span m='1685700'>which</span> <span
  m='1685910'>I</span> <span m='1685950'>want</span> <span m='1686160'>to</span>
  <span m='1686220'>show</span> <span m='1686500'>you,</span> <span
  m='1686760'>because</span> <span m='1687320'>it</span> <span
  m='1687450'>can</span> <span m='1687690'>be</span> <span
  m='1687800'>useful.</span> <span m='1696170'>So</span> <span
  m='1696310'>we're</span> <span m='1696370'>going</span> <span
  m='1696490'>to</span> <span m='1696550'>do</span> <span m='1696610'>the</span>
  <span m='1696710'>same</span> <span m='1697120'>sum</span> <span
  m='1697880'>and</span> <span m='1698330'>derive</span> <span
  m='1698680'>the</span> <span m='1698750'>formula</span> <span
  m='1699180'>a</span> <span m='1699210'>different</span> <span
  m='1699530'>way.</span> <span m='1701180'>This</span> <span
  m='1701440'>method</span> <span m='1701770'>is</span> <span
  m='1701900'>called</span> <span m='1702200'>the</span> <span
  m='1702280'>derivative</span> <span m='1702780'>method,</span> <span
  m='1711720'>and</span> <span m='1711880'>the</span> <span
  m='1711980'>idea</span> <span m='1712340'>is</span> <span
  m='1712430'>to</span> <span m='1712530'>start</span> <span
  m='1713030'>with</span> <span m='1713200'>a</span> <span
  m='1713240'>geometric</span> <span m='1713820'>series</span> <span
  m='1714260'>which</span> <span m='1714440'>it's</span> <span
  m='1714560'>close</span> <span m='1714900'>to</span> <span
  m='1715890'>and</span> <span m='1716060'>then</span> <span
  m='1716210'>take</span> <span m='1716440'>a</span> <span
  m='1716490'>derivative.</span> </p><p><span m='1719280'>So</span> <span
  m='1719470'>for</span> <span m='1719630'>x</span> <span m='1720010'>not</span>
  <span m='1720280'>equal</span> <span m='1720490'>to</span> <span
  m='1720570'>1,</span> <span m='1721060'>we</span> <span
  m='1721180'>already</span> <span m='1721450'>know</span> <span
  m='1722990'>from</span> <span m='1723140'>the</span> <span
  m='1723210'>theorem</span> <span m='1723700'>that</span> <span
  m='1724210'>i</span> <span m='1724520'>equals</span> <span
  m='1724880'>0</span> <span m='1725850'>to</span> <span m='1726020'>n,</span>
  <span m='1726520'>x</span> <span m='1726770'>to</span> <span
  m='1726880'>the</span> <span m='1727100'>i</span> <span
  m='1727740'>equals</span> <span m='1728690'>1</span> <span
  m='1728950'>minus</span> <span m='1729490'>x</span> <span
  m='1729740'>to</span> <span m='1729820'>the</span> <span m='1729920'>n</span>
  <span m='1730080'>plus</span> <span m='1730320'>1</span> <span
  m='1731180'>over</span> <span m='1731410'>1</span> <span
  m='1731620'>minus</span> <span m='1731970'>x.</span> <span
  m='1733170'>That</span> <span m='1733400'>was</span> <span
  m='1733530'>the</span> <span m='1733600'>theorem.</span> <span
  m='1734120'>We</span> <span m='1734270'>already</span> <span
  m='1734480'>know</span> <span m='1734670'>that.</span> <span
  m='1737010'>Now,</span> <span m='1737320'>I</span> <span
  m='1737420'>can</span> <span m='1737600'>take</span> <span
  m='1737800'>the</span> <span m='1737870'>derivative</span> <span
  m='1738520'>of</span> <span m='1738630'>both</span> <span
  m='1738920'>sides,</span> <span m='1739670'>and</span> <span
  m='1739800'>let's</span> <span m='1739950'>see</span> <span
  m='1740140'>what</span> <span m='1740270'>we</span> <span
  m='1740360'>get</span> <span m='1741040'>by</span> <span
  m='1741150'>taking</span> <span m='1741460'>the</span> <span
  m='1741540'>derivative.</span> <span m='1743220'>Well,</span> <span
  m='1743410'>here</span> <span m='1746370'>I</span> <span
  m='1746510'>get</span> <span m='1746660'>the</span> <span
  m='1746730'>sum.</span> <span m='1747440'>The</span> <span
  m='1747500'>derivative</span> <span m='1747840'>of</span> <span
  m='1747980'>x</span> <span m='1748150'>to</span> <span m='1748230'>the</span>
  <span m='1748350'>i</span> <span m='1748700'>is</span> <span
  m='1748870'>just</span> <span m='1748940'>i</span> <span
  m='1749330'>times</span> <span m='1749730'>x</span> <span
  m='1749860'>to</span> <span m='1749990'>the</span> <span m='1750120'>i</span>
  <span m='1750320'>minus</span> <span m='1750580'>1.</span> </p><p><span
  m='1753020'>The</span> <span m='1753170'>derivative</span> <span
  m='1753690'>over</span> <span m='1753880'>here</span> <span
  m='1754320'>is</span> <span m='1754420'>a</span> <span
  m='1754480'>little</span> <span m='1754710'>messier.</span> <span
  m='1756310'>I've</span> <span m='1756430'>got</span> <span
  m='1756600'>to</span> <span m='1756690'>have--</span> <span
  m='1757480'>well,</span> <span m='1757580'>I</span> <span
  m='1757680'>take</span> <span m='1758520'>1</span> <span
  m='1758870'>minus</span> <span m='1759210'>x</span> <span
  m='1759400'>times</span> <span m='1759610'>a</span> <span
  m='1759670'>derivative</span> <span m='1760020'>of</span> <span
  m='1760110'>that.</span> <span m='1763530'>Derivative</span> <span
  m='1763780'>of</span> <span m='1763950'>this</span> <span
  m='1764350'>is</span> <span m='1765740'>now</span> <span
  m='1766060'>minus</span> <span m='1767480'>n</span> <span
  m='1767750'>plus</span> <span m='1768080'>1,</span> <span m='1769920'>x</span>
  <span m='1770290'>to</span> <span m='1770420'>the</span> <span
  m='1770830'>n.</span> <span m='1773020'>Then</span> <span m='1773190'>I</span>
  <span m='1773260'>take</span> <span m='1774160'>this</span> <span
  m='1774460'>times</span> <span m='1774700'>the</span> <span
  m='1774770'>derivative</span> <span m='1775190'>of</span> <span
  m='1775425'>that</span> <span m='1776980'>is</span> <span
  m='1777220'>now</span> <span m='1778055'>minus</span> <span
  m='1778870'>minus</span> <span m='1779290'>1,</span> <span
  m='1781160'>1</span> <span m='1781420'>minus</span> <span m='1781720'>x</span>
  <span m='1781980'>to</span> <span m='1782060'>the</span> <span
  m='1782170'>n</span> <span m='1782330'>plus</span> <span m='1782600'>1,</span>
  <span m='1784790'>and</span> <span m='1784910'>then</span> <span
  m='1785040'>I</span> <span m='1785130'>divide</span> <span
  m='1785710'>by</span> <span m='1787360'>that</span> <span
  m='1787660'>squared.</span> </p><p><span m='1792730'>Now,</span> <span
  m='1792910'>when</span> <span m='1793030'>we</span> <span
  m='1793320'>compute</span> <span m='1793710'>all</span> <span
  m='1793900'>that</span> <span m='1794130'>out,</span> <span
  m='1794720'>we</span> <span m='1794900'>get</span> <span
  m='1795160'>this,</span> <span m='1797240'>1</span> <span
  m='1797590'>minus</span> <span m='1798150'>n</span> <span
  m='1798390'>plus</span> <span m='1798690'>1,</span> <span m='1799960'>x</span>
  <span m='1800260'>to</span> <span m='1800360'>the</span> <span
  m='1800540'>n</span> <span m='1802010'>plus</span> <span m='1802400'>nx</span>
  <span m='1803290'>to</span> <span m='1803380'>the</span> <span
  m='1803480'>n</span> <span m='1803670'>plus</span> <span m='1803940'>1</span>
  <span m='1805920'>over</span> <span m='1806460'>1</span> <span
  m='1806690'>minus</span> <span m='1807070'>x</span> <span
  m='1807310'>squared.</span> <span m='1809700'>I</span> <span
  m='1809920'>won't</span> <span m='1810180'>drag</span> <span
  m='1810460'>you</span> <span m='1810530'>through</span> <span
  m='1810690'>the</span> <span m='1810850'>algebra,</span> <span
  m='1811230'>but</span> <span m='1811320'>it's</span> <span
  m='1811420'>not</span> <span m='1811630'>hard</span> <span
  m='1811830'>to</span> <span m='1811900'>go</span> <span
  m='1812070'>from</span> <span m='1812240'>there</span> <span
  m='1812400'>to</span> <span m='1812470'>there.</span> <span
  m='1813480'>This</span> <span m='1813690'>is</span> <span
  m='1813820'>pretty</span> <span m='1814040'>close</span> <span
  m='1814390'>to</span> <span m='1814470'>what</span> <span
  m='1814600'>we</span> <span m='1814710'>wanted.</span> <span
  m='1817020'>We're</span> <span m='1817170'>trying</span> <span
  m='1817590'>to</span> <span m='1817650'>figure</span> <span
  m='1818020'>out</span> <span m='1819420'>this,</span> <span
  m='1821610'>and</span> <span m='1821790'>we</span> <span
  m='1821880'>almost</span> <span m='1822450'>got</span> <span
  m='1822760'>there.</span> <span m='1825540'>What</span> <span
  m='1825700'>do</span> <span m='1825790'>I</span> <span m='1825880'>do</span>
  <span m='1826440'>to</span> <span m='1826560'>finish</span> <span
  m='1826920'>it</span> <span m='1827010'>up?</span> </p><p><span
  m='1828978'>AUDIENCE:</span> <span m='1829101'>Multiply</span> <span
  m='1829224'>by</span> <span m='1829347'>x.</span> </p><p><span
  m='1829470'>PROFESSOR: Multiply</span> <span m='1830060'>by</span> <span
  m='1830280'>x.</span> <span m='1830900'>Good.</span> <span
  m='1831730'>So</span> <span m='1831970'>if</span> <span m='1832070'>I</span>
  <span m='1832150'>take</span> <span m='1832430'>this</span> <span
  m='1832700'>and</span> <span m='1832790'>multiply</span> <span
  m='1833170'>by</span> <span m='1833400'>x,</span> <span m='1838450'>i</span>
  <span m='1838705'>equals</span> <span m='1838960'>zero</span> <span
  m='1839530'>to</span> <span m='1839720'>n,</span> <span m='1840140'>ix</span>
  <span m='1841200'>to</span> <span m='1841280'>the</span> <span
  m='1841480'>i</span> <span m='1841940'>equals</span> <span
  m='1844040'>x</span> <span m='1844530'>minus</span> <span m='1845180'>n</span>
  <span m='1845430'>plus</span> <span m='1845730'>1,</span> <span
  m='1847130'>x</span> <span m='1847460'>to</span> <span m='1847560'>the</span>
  <span m='1847680'>n</span> <span m='1847830'>plus</span> <span
  m='1848140'>1,</span> <span m='1849060'>plus</span> <span
  m='1849440'>nx</span> <span m='1850200'>to</span> <span m='1850290'>the</span>
  <span m='1850410'>n</span> <span m='1850550'>plus</span> <span
  m='1850860'>2,</span> <span m='1852110'>all</span> <span
  m='1852420'>over</span> <span m='1852690'>1</span> <span
  m='1852890'>minus</span> <span m='1853230'>x</span> <span
  m='1853400'>squared.</span> <span m='1856240'>OK?</span> </p><p><span
  m='1857890'>Which</span> <span m='1858140'>should</span> <span
  m='1858380'>be</span> <span m='1858540'>the</span> <span
  m='1858640'>same--</span> <span m='1859120'>yeah--</span> <span
  m='1859270'>the</span> <span m='1859360'>same</span> <span
  m='1859590'>formula</span> <span m='1859970'>we</span> <span
  m='1860050'>had</span> <span m='1860230'>up</span> <span
  m='1860350'>there.</span> <span m='1862110'>So</span> <span
  m='1862210'>that's</span> <span m='1862310'>called</span> <span
  m='1862520'>the</span> <span m='1862590'>derivative</span> <span
  m='1863050'>method.</span> <span m='1863400'>You</span> <span
  m='1863470'>can</span> <span m='1863570'>start</span> <span
  m='1863840'>manipulating--</span> <span m='1864800'>you</span> <span
  m='1864910'>treat</span> <span m='1865110'>these</span> <span
  m='1865280'>things</span> <span m='1865470'>as</span> <span
  m='1865580'>polynomials--</span> <span m='1866490'>these</span> <span
  m='1866570'>sums--</span> <span m='1867050'>and</span> <span
  m='1867150'>you</span> <span m='1867210'>start</span> <span
  m='1868530'>manipulating</span> <span m='1869100'>them</span> <span
  m='1869230'>like</span> <span m='1869390'>you</span> <span
  m='1869450'>would</span> <span m='1869590'>polynomials.</span> <span
  m='1870930'>In</span> <span m='1871035'>fact,</span> <span
  m='1871140'>there's</span> <span m='1871280'>a</span> <span
  m='1871350'>whole</span> <span m='1871650'>branch</span> <span
  m='1872830'>of</span> <span m='1873050'>mathematics</span> <span
  m='1873670'>called</span> <span m='1873890'>generating</span> <span
  m='1874460'>functions</span> <span m='1874900'>that</span> <span
  m='1875000'>we</span> <span m='1875090'>won't</span> <span
  m='1875420'>have</span> <span m='1875610'>time</span> <span
  m='1875830'>to</span> <span m='1875900'>do</span> <span m='1876080'>in</span>
  <span m='1876170'>this</span> <span m='1876310'>class</span> <span
  m='1878000'>that's</span> <span m='1878200'>in</span> <span
  m='1878340'>chapter</span> <span m='1879010'>12</span> <span
  m='1879470'>of</span> <span m='1879660'>the</span> <span
  m='1879750'>text.</span> <span m='1880560'>But</span> <span
  m='1880690'>you</span> <span m='1880900'>do</span> <span
  m='1881110'>things</span> <span m='1881500'>like</span> <span
  m='1881750'>that</span> <span m='1883170'>to</span> <span
  m='1883690'>get</span> <span m='1883980'>sums.</span> <span
  m='1889820'>Any</span> <span m='1889990'>questions</span> <span
  m='1890500'>about</span> <span m='1891370'>what</span> <span
  m='1891520'>we</span> <span m='1891620'>did</span> <span
  m='1891820'>there?</span> </p><p><span m='1893430'>You</span> <span
  m='1893550'>can</span> <span m='1893670'>also</span> <span
  m='1893950'>do</span> <span m='1894080'>a</span> <span
  m='1894150'>version</span> <span m='1894580'>where</span> <span
  m='1894680'>you</span> <span m='1894750'>take</span> <span
  m='1895000'>integrals</span> <span m='1896040'>of</span> <span
  m='1896190'>this</span> <span m='1896800'>if</span> <span
  m='1896950'>you</span> <span m='1897050'>want,</span> <span
  m='1898350'>and</span> <span m='1898440'>then</span> <span
  m='1898550'>you</span> <span m='1898630'>get</span> <span
  m='1898780'>the</span> <span m='1898890'>i's</span> <span
  m='1899260'>in</span> <span m='1899350'>the</span> <span
  m='1899420'>denominator</span> <span m='1900590'>instead</span> <span
  m='1900870'>of</span> <span m='1901100'>those</span> <span
  m='1901240'>coefficients.</span> </p><p><span m='1905340'>For</span> <span
  m='1905530'>homework,</span> <span m='1906400'>I</span> <span
  m='1906550'>think</span> <span m='1906810'>we've</span> <span
  m='1906970'>given</span> <span m='1907310'>you</span> <span
  m='1908980'>the</span> <span m='1909110'>sum</span> <span
  m='1909630'>of</span> <span m='1909850'>i</span> <span
  m='1910180'>squared</span> <span m='1910870'>x</span> <span
  m='1911100'>to</span> <span m='1911190'>the</span> <span m='1911330'>i.</span>
  <span m='1912761'>How</span> <span m='1913240'>do</span> <span
  m='1913310'>you</span> <span m='1913390'>think</span> <span
  m='1913560'>you're</span> <span m='1913650'>going</span> <span
  m='1913770'>to</span> <span m='1913850'>do</span> <span
  m='1913980'>that?</span> <span m='1916640'>Any</span> <span
  m='1916810'>thoughts</span> <span m='1917080'>about</span> <span
  m='1917230'>how</span> <span m='1917310'>you're</span> <span
  m='1917384'>going</span> <span m='1917458'>to</span> <span
  m='1917532'>solve</span> <span m='1917606'>that?</span> <span
  m='1919220'>Get</span> <span m='1919370'>the</span> <span
  m='1919450'>sum,</span> <span m='1919700'>a</span> <span
  m='1919950'>closed</span> <span m='1920320'>form</span> <span
  m='1920570'>for</span> <span m='1920670'>the</span> <span
  m='1920760'>sum</span> <span m='1920990'>of</span> <span m='1921180'>i</span>
  <span m='1921440'>squared</span> <span m='1921790'>x</span> <span
  m='1921908'>to</span> <span m='1922027'>the</span> <span m='1922145'>i?</span>
  </p><p><span m='1924160'>AUDIENCE: Do</span> <span m='1924634'>the</span>
  <span m='1924792'>derivative</span> <span m='1924950'>method</span> <span
  m='1925108'>twice.</span> </p><p><span m='1926060'>PROFESSOR:  Yeah,</span>
  <span m='1926380'>do</span> <span m='1926510'>it</span> <span
  m='1926600'>twice.</span> <span m='1926920'>Take</span> <span
  m='1927130'>this,</span> <span m='1927700'>which</span> <span
  m='1927870'>now</span> <span m='1928040'>you</span> <span
  m='1928266'>know.</span> <span m='1928946'>Take</span> <span
  m='1929400'>the</span> <span m='1929460'>derivative</span> <span
  m='1929820'>again.</span> <span m='1931700'>Won't</span> <span
  m='1931790'>be</span> <span m='1931930'>too</span> <span
  m='1932710'>hard.</span> </p><p><span m='1938530'>You</span> <span
  m='1938670'>can</span> <span m='1938810'>also</span> <span
  m='1939060'>take</span> <span m='1939360'>the</span> <span
  m='1939430'>version</span> <span m='1939810'>of</span> <span
  m='1939890'>this</span> <span m='1940210'>where</span> <span
  m='1941300'>n</span> <span m='1941560'>goes</span> <span m='1941810'>to</span>
  <span m='1941920'>infinity.</span> <span m='1943980'>Let's</span> <span
  m='1944110'>do</span> <span m='1944250'>that.</span> <span
  m='1950120'>If</span> <span m='1950560'>the</span> <span
  m='1950670'>absolute</span> <span m='1951090'>value</span> <span
  m='1951370'>of</span> <span m='1951480'>x</span> <span m='1951730'>is</span>
  <span m='1951860'>less</span> <span m='1952090'>than</span> <span
  m='1952220'>1,</span> <span m='1953700'>the</span> <span
  m='1953800'>sum</span> <span m='1954460'>i</span> <span
  m='1954900'>equals</span> <span m='1956150'>1</span> <span
  m='1956540'>to</span> <span m='1956680'>infinity</span> <span
  m='1958730'>of</span> <span m='1959050'>ix</span> <span m='1959580'>to</span>
  <span m='1959670'>the</span> <span m='1959840'>i,</span> <span
  m='1960870'>what</span> <span m='1961050'>does</span> <span
  m='1961240'>that</span> <span m='1961530'>equal?</span> </p><p><span
  m='1964560'>This</span> <span m='1964760'>one,</span> <span
  m='1964880'>you</span> <span m='1964950'>can</span> <span
  m='1965060'>see</span> <span m='1965320'>it</span> <span
  m='1965380'>easier</span> <span m='1965760'>up</span> <span
  m='1965890'>here.</span> <span m='1969020'>What</span> <span
  m='1969200'>happens</span> <span m='1970700'>when</span> <span
  m='1970970'>n</span> <span m='1971310'>goes</span> <span m='1971590'>to</span>
  <span m='1971700'>infinity?</span> <span m='1973890'>What</span> <span
  m='1974010'>does</span> <span m='1974130'>this</span> <span
  m='1974310'>do?</span> <span m='1977390'>X</span> <span m='1977700'>is</span>
  <span m='1977820'>less</span> <span m='1978030'>than</span> <span
  m='1978140'>1,</span> <span m='1978650'>an</span> <span
  m='1978780'>absolute</span> <span m='1979175'>value.</span> <span
  m='1979570'>What</span> <span m='1979800'>happens</span> <span
  m='1980120'>to</span> <span m='1980190'>this</span> <span
  m='1980390'>as</span> <span m='1980475'>n</span> <span m='1980560'>goes</span>
  <span m='1980900'>to</span> <span m='1980980'>infinity?</span> <span
  m='1982990'>This</span> <span m='1983070'>term.</span> <span
  m='1986380'>Goes</span> <span m='1986670'>to</span> <span
  m='1986760'>0,</span> <span m='1988650'>right?</span> <span
  m='1989010'>This</span> <span m='1989190'>gets</span> <span
  m='1989420'>big,</span> <span m='1989780'>but</span> <span
  m='1989900'>this</span> <span m='1990060'>gets</span> <span
  m='1990250'>smaller</span> <span m='1990800'>faster.</span> <span
  m='1991930'>What</span> <span m='1992130'>happens</span> <span
  m='1992450'>to</span> <span m='1992520'>this</span> <span
  m='1992720'>term</span> <span m='1992960'>as</span> <span m='1993090'>n</span>
  <span m='1993230'>goes</span> <span m='1993430'>to</span> <span
  m='1993520'>infinity?</span> <span m='1996230'>Same</span> <span
  m='1996580'>thing,</span> <span m='1997030'>0.</span> <span
  m='1998500'>All</span> <span m='1998830'>I'm</span> <span
  m='1998940'>left</span> <span m='1999210'>with</span> <span
  m='1999340'>is</span> <span m='1999490'>x</span> <span m='1999820'>over</span>
  <span m='1999960'>1</span> <span m='2000160'>minus</span> <span
  m='2000490'>x</span> <span m='2000650'>squared.</span> </p><p><span
  m='2009570'>Now,</span> <span m='2010180'>this</span> <span
  m='2010510'>formula</span> <span m='2011380'>is</span> <span
  m='2011600'>useful</span> <span m='2012650'>if</span> <span
  m='2012810'>you're</span> <span m='2012930'>trying</span> <span
  m='2013300'>to,</span> <span m='2013420'>say,</span> <span
  m='2015260'>get</span> <span m='2015410'>the</span> <span
  m='2015490'>value</span> <span m='2015870'>of</span> <span
  m='2015950'>a</span> <span m='2016020'>company,</span> <span
  m='2017410'>and</span> <span m='2017560'>the</span> <span
  m='2017620'>company</span> <span m='2018030'>is</span> <span
  m='2018150'>growing.</span> <span m='2019490'>Every</span> <span
  m='2019870'>year</span> <span m='2020250'>the</span> <span
  m='2020340'>company</span> <span m='2021400'>grows</span> <span
  m='2021840'>its</span> <span m='2022000'>bottom</span> <span
  m='2022390'>line</span> <span m='2022820'>by</span> <span m='2023040'>m</span>
  <span m='2023320'>dollars.</span> <span m='2024850'>So</span> <span
  m='2025100'>the</span> <span m='2025180'>first</span> <span
  m='2025540'>year,</span> <span m='2025700'>the</span> <span
  m='2025790'>company</span> <span m='2026140'>generates</span> <span
  m='2026580'>m</span> <span m='2026780'>dollars,</span> <span
  m='2027240'>the</span> <span m='2027310'>next</span> <span
  m='2027610'>year</span> <span m='2027770'>it</span> <span
  m='2027860'>generates</span> <span m='2028300'>two</span> <span
  m='2028590'>m</span> <span m='2028760'>dollars</span> <span
  m='2029220'>in</span> <span m='2029320'>profit,</span> <span
  m='2030060'>the</span> <span m='2030170'>next</span> <span
  m='2030420'>year</span> <span m='2030590'>is</span> <span
  m='2030740'>three</span> <span m='2031040'>m</span> <span
  m='2031210'>dollars.</span> <span m='2032150'>So</span> <span
  m='2032310'>you've</span> <span m='2032410'>got</span> <span
  m='2032600'>an</span> <span m='2032710'>entity</span> <span
  m='2033150'>that</span> <span m='2033300'>every</span> <span
  m='2033580'>year</span> <span m='2033760'>is</span> <span
  m='2033880'>growing</span> <span m='2034300'>by</span> <span
  m='2034460'>a</span> <span m='2034510'>fixed</span> <span
  m='2034890'>amount.</span> <span m='2035260'>It's</span> <span
  m='2035400'>not</span> <span m='2035910'>doubling</span> <span
  m='2036440'>every</span> <span m='2036640'>year,</span> <span
  m='2037210'>but</span> <span m='2037450'>every</span> <span
  m='2037670'>year</span> <span m='2037870'>adds</span> <span
  m='2038170'>in</span> <span m='2038340'>m</span> <span
  m='2038540'>dollars</span> <span m='2038900'>more</span> <span
  m='2039210'>of</span> <span m='2039300'>profit.</span> </p><p><span
  m='2040760'>What</span> <span m='2041090'>would</span> <span
  m='2041240'>you</span> <span m='2041380'>pay</span> <span
  m='2041730'>to</span> <span m='2041820'>buy</span> <span
  m='2042100'>that</span> <span m='2042320'>company?</span> <span
  m='2043400'>What</span> <span m='2043620'>is</span> <span
  m='2043720'>that</span> <span m='2043940'>worth?</span> <span
  m='2045550'>So</span> <span m='2045650'>you</span> <span
  m='2045750'>can</span> <span m='2045850'>think</span> <span
  m='2045970'>of</span> <span m='2046050'>this</span> <span
  m='2046500'>as,</span> <span m='2047450'>again,</span> <span
  m='2047750'>an</span> <span m='2047820'>annuity.</span> <span
  m='2053900'>Here</span> <span m='2054300'>the</span> <span
  m='2054469'>annuity</span> <span m='2057620'>pays</span> <span
  m='2061090'>im</span> <span m='2061830'>dollars,</span> <span
  m='2064469'>in</span> <span m='2064580'>this</span> <span
  m='2064750'>case,</span> <span m='2065090'>at</span> <span
  m='2065179'>the</span> <span m='2065400'>end,</span> <span
  m='2067030'>not</span> <span m='2067230'>the</span> <span
  m='2067300'>beginning,</span> <span m='2067555'>say,</span> <span
  m='2068810'>of</span> <span m='2069540'>the</span> <span
  m='2069780'>year</span> <span m='2070179'>i</span> <span
  m='2071760'>forever.</span> </p><p><span m='2079070'>This</span> <span
  m='2079210'>company</span> <span m='2079830'>is--</span> <span
  m='2080100'>or</span> <span m='2080239'>this</span> <span
  m='2080389'>annuity--</span> <span m='2080929'>is</span> <span
  m='2081130'>worth,</span> <span m='2083139'>well,</span> <span
  m='2083409'>we</span> <span m='2083489'>just</span> <span
  m='2084010'>plug</span> <span m='2084330'>into</span> <span
  m='2084489'>the</span> <span m='2084570'>formula.</span> <span
  m='2086190'>Instead</span> <span m='2086489'>of</span> <span
  m='2087159'>$1</span> <span m='2087969'>each</span> <span
  m='2088139'>year,</span> <span m='2088300'>it's</span> <span
  m='2088469'>m</span> <span m='2088770'>so</span> <span
  m='2088900'>there's</span> <span m='2089030'>an</span> <span
  m='2089139'>m</span> <span m='2089330'>out</span> <span
  m='2089489'>front.</span> <span m='2090469'>x</span> <span
  m='2090790'>is</span> <span m='2090929'>1</span> <span m='2091130'>over</span>
  <span m='2091260'>1</span> <span m='2091460'>plus</span> <span
  m='2091730'>p,</span> <span m='2096070'>and</span> <span
  m='2096239'>then</span> <span m='2096389'>we</span> <span
  m='2096520'>have</span> <span m='2097270'>1</span> <span
  m='2097490'>minus</span> <span m='2097930'>1</span> <span
  m='2098120'>over</span> <span m='2098280'>1</span> <span
  m='2098490'>plus</span> <span m='2098770'>p</span> <span
  m='2099230'>squared.</span> <span m='2102620'>And</span> <span
  m='2102680'>if</span> <span m='2102760'>we</span> <span
  m='2102850'>multiply</span> <span m='2103290'>the</span> <span
  m='2103390'>top</span> <span m='2103710'>and</span> <span
  m='2103840'>bottom</span> <span m='2104170'>by</span> <span
  m='2104310'>1</span> <span m='2104630'>plus</span> <span m='2104910'>p</span>
  <span m='2105180'>squared,</span> <span m='2106840'>we</span> <span
  m='2107000'>get</span> <span m='2108660'>m</span> <span m='2109210'>1</span>
  <span m='2109460'>plus</span> <span m='2109760'>p</span> <span
  m='2110870'>over</span> <span m='2111230'>p</span> <span
  m='2111470'>squared.</span> </p><p><span m='2115190'>So</span> <span
  m='2115300'>it's</span> <span m='2115440'>possible</span> <span
  m='2115715'>with</span> <span m='2115990'>a</span> <span
  m='2116020'>very</span> <span m='2116320'>simple</span> <span
  m='2116660'>formula</span> <span m='2117840'>to</span> <span
  m='2117970'>figure</span> <span m='2118270'>out</span> <span
  m='2118520'>how</span> <span m='2118710'>much</span> <span
  m='2118920'>you</span> <span m='2119010'>should</span> <span
  m='2119190'>spend</span> <span m='2119520'>to</span> <span
  m='2119590'>buy</span> <span m='2119830'>this</span> <span
  m='2120000'>company,</span> <span m='2120930'>what</span> <span
  m='2121130'>its</span> <span m='2121260'>value</span> <span
  m='2121680'>is</span> <span m='2121820'>today.</span> <span
  m='2122730'>So,</span> <span m='2122910'>for</span> <span
  m='2123020'>example,</span> <span m='2123500'>say</span> <span
  m='2123760'>the</span> <span m='2123840'>company</span> <span
  m='2124230'>was</span> <span m='2124910'>adding</span> <span
  m='2125990'>$50,000</span> <span m='2127470'>a</span> <span
  m='2127540'>year</span> <span m='2129590'>in</span> <span
  m='2129760'>profit.</span> <span m='2131650'>The</span> <span
  m='2131840'>interest</span> <span m='2132210'>rate</span> <span
  m='2133200'>was</span> <span m='2133740'>6%,</span> <span
  m='2135970'>the</span> <span m='2136110'>value</span> <span
  m='2136590'>of</span> <span m='2136670'>this</span> <span
  m='2136830'>company</span> <span m='2137300'>is</span> <span
  m='2137470'>$14</span> <span m='2137930'>million--</span> <span
  m='2138190'>$14.7</span> <span m='2139560'>million,</span> <span
  m='2144890'>just</span> <span m='2145220'>plugging</span> <span
  m='2145510'>into</span> <span m='2145680'>that</span> <span
  m='2145860'>formula.</span> </p><p><span m='2147960'>So</span> <span
  m='2148070'>people</span> <span m='2148390'>that</span> <span
  m='2149580'>buy</span> <span m='2149900'>companies</span> <span
  m='2150440'>and</span> <span m='2150550'>stuff,</span> <span
  m='2151380'>they</span> <span m='2151550'>use</span> <span
  m='2151800'>formulas</span> <span m='2152410'>like</span> <span
  m='2152630'>this</span> <span m='2153000'>to</span> <span
  m='2153580'>figure</span> <span m='2154050'>out</span> <span
  m='2155010'>what</span> <span m='2155200'>it's</span> <span
  m='2155340'>worth.</span> <span m='2155990'>Of</span> <span
  m='2156050'>course,</span> <span m='2156390'>you've</span> <span
  m='2156410'>got</span> <span m='2156500'>to</span> <span
  m='2156570'>make</span> <span m='2156730'>sure</span> <span
  m='2156910'>it's</span> <span m='2157090'>really</span> <span
  m='2157320'>going</span> <span m='2157440'>to</span> <span
  m='2157500'>keep</span> <span m='2157710'>paying</span> <span
  m='2158690'>the</span> <span m='2158930'>$50,000</span> <span
  m='2159810'>more</span> <span m='2160470'>every</span> <span
  m='2160790'>year</span> <span m='2161780'>and</span> <span
  m='2161970'>that</span> <span m='2162120'>this</span> <span
  m='2162320'>is</span> <span m='2162530'>the</span> <span
  m='2162630'>right</span> <span m='2162810'>interest</span> <span
  m='2163160'>rate</span> <span m='2163370'>to</span> <span
  m='2163470'>be</span> <span m='2163550'>thinking</span> <span
  m='2163870'>about.</span> </p><p><span m='2165910'>You</span> <span
  m='2165977'>know,</span> <span m='2166045'>and</span> <span
  m='2166180'>the</span> <span m='2166240'>guys</span> <span
  m='2166540'>on</span> <span m='2166660'>Wall</span> <span
  m='2166890'>Street--</span> <span m='2167090'>the</span> <span
  m='2167160'>bankers</span> <span m='2167530'>on</span> <span
  m='2167650'>Wall</span> <span m='2167860'>Street--</span> <span
  m='2168070'>they</span> <span m='2168200'>all</span> <span
  m='2168330'>have</span> <span m='2169190'>their</span> <span
  m='2169350'>estimations</span> <span m='2170040'>for</span> <span
  m='2170160'>what</span> <span m='2170350'>these</span> <span
  m='2170600'>things</span> <span m='2171650'>are--</span> <span
  m='2172670'>the</span> <span m='2172780'>value</span> <span
  m='2173080'>of</span> <span m='2173160'>p</span> <span m='2173400'>they</span>
  <span m='2173510'>would</span> <span m='2173600'>put</span> <span
  m='2173800'>into</span> <span m='2173950'>these</span> <span
  m='2174120'>formulas.</span> <span m='2176200'>Any</span> <span
  m='2176360'>questions</span> <span m='2176780'>about</span> <span
  m='2177010'>that?</span> <span m='2179410'>Yeah.</span> </p><p><span
  m='2180715'>AUDIENCE:</span> <span m='2181150'>[INAUDIBLE]</span> </p><p><span
  m='2182460'>PROFESSOR: OK.</span> <span m='2182830'>Good.</span> <span
  m='2184290'>So</span> <span m='2185340'>this</span> <span
  m='2185600'>one</span> <span m='2185770'>is</span> <span
  m='2185880'>OK?</span> <span m='2187170'>OK.</span> <span m='2188040'>I</span>
  <span m='2188210'>plugged</span> <span m='2189350'>x</span> <span
  m='2189850'>equals</span> <span m='2190380'>1</span> <span
  m='2190630'>over</span> <span m='2190870'>1</span> <span
  m='2191180'>plus</span> <span m='2191530'>p,</span> <span
  m='2192910'>like</span> <span m='2193110'>we</span> <span
  m='2193200'>did</span> <span m='2193370'>before--</span> <span
  m='2194050'>remember</span> <span m='2194340'>for</span> <span
  m='2194450'>the</span> <span m='2194550'>annuity--</span> <span
  m='2194920'>because</span> <span m='2195770'>every</span> <span
  m='2196120'>year</span> <span m='2197160'>you're</span> <span
  m='2197350'>degrading</span> <span m='2198000'>it,</span> <span
  m='2198090'>devaluing</span> <span m='2198750'>by</span> <span
  m='2198870'>1</span> <span m='2199200'>over</span> <span m='2199380'>1</span>
  <span m='2199550'>plus</span> <span m='2199770'>p.</span> <span
  m='2200430'>So</span> <span m='2200580'>that's</span> <span
  m='2200800'>the</span> <span m='2200960'>x</span> <span
  m='2201260'>term,</span> <span m='2202720'>and</span> <span
  m='2203680'>it's</span> <span m='2203940'>paying--</span> <span
  m='2205300'>in</span> <span m='2205750'>the</span> <span
  m='2206030'>i-th</span> <span m='2206340'>year,</span> <span
  m='2207160'>it's</span> <span m='2207460'>paying</span> <span
  m='2208620'>im</span> <span m='2209310'>dollars.</span> <span
  m='2211400'>All</span> <span m='2211570'>right?</span> </p><p><span
  m='2212250'>So</span> <span m='2212480'>the</span> <span
  m='2212560'>first</span> <span m='2212980'>year</span> <span
  m='2213190'>it</span> <span m='2213280'>pays</span> <span m='2213670'>n</span>
  <span m='2213890'>dollars,</span> <span m='2214940'>the</span> <span
  m='2215060'>next</span> <span m='2215360'>year</span> <span
  m='2215610'>2</span> <span m='2215840'>m,</span> <span m='2216470'>the</span>
  <span m='2216560'>next</span> <span m='2216850'>year</span> <span
  m='2216990'>3</span> <span m='2217420'>m,</span> <span m='2218270'>the</span>
  <span m='2218340'>next</span> <span m='2218580'>year</span> <span
  m='2218700'>4</span> <span m='2219120'>m,</span> <span m='2220830'>but</span>
  <span m='2221110'>every</span> <span m='2221400'>year</span> <span
  m='2221590'>you're</span> <span m='2221720'>knocking</span> <span
  m='2222100'>it</span> <span m='2222200'>down</span> <span
  m='2222490'>by</span> <span m='2222610'>1</span> <span m='2222910'>plus</span>
  <span m='2223140'>1</span> <span m='2223310'>over</span> <span
  m='2223500'>p</span> <span m='2223940'>to</span> <span m='2224110'>the</span>
  <span m='2224250'>number</span> <span m='2224510'>of</span> <span
  m='2224600'>years.</span> <span m='2226070'>So</span> <span
  m='2226290'>what</span> <span m='2226470'>you</span> <span
  m='2226570'>get--</span> <span m='2226900'>the</span> <span
  m='2226980'>sum</span> <span m='2227260'>you've</span> <span
  m='2227400'>really</span> <span m='2227620'>got</span> <span
  m='2227890'>here--</span> <span m='2231520'>is</span> <span
  m='2231690'>i</span> <span m='2231880'>equals</span> <span
  m='2232020'>1</span> <span m='2232180'>to</span> <span
  m='2232290'>infinity,</span> <span m='2233250'>im</span> <span
  m='2233740'>dollars</span> <span m='2234180'>are</span> <span
  m='2234250'>paid,</span> <span m='2235130'>but</span> <span
  m='2235310'>those</span> <span m='2235540'>dollars</span> <span
  m='2236030'>are</span> <span m='2236110'>worth</span> <span
  m='2237320'>1</span> <span m='2237550'>over</span> <span m='2237690'>1</span>
  <span m='2237860'>plus</span> <span m='2238120'>p</span> <span
  m='2238300'>to</span> <span m='2238390'>the</span> <span m='2238550'>i</span>
  <span m='2239700'>today,</span> <span m='2240280'>the</span> <span
  m='2240380'>current</span> <span m='2240680'>value.</span> <span
  m='2241370'>That's</span> <span m='2241590'>a</span> <span
  m='2241630'>good</span> <span m='2241770'>question.</span> <span
  m='2242110'>I</span> <span m='2242160'>should've</span> <span
  m='2243080'>said</span> <span m='2243300'>that.</span> <span
  m='2244350'>That's</span> <span m='2244520'>a</span> <span
  m='2244570'>great</span> <span m='2244780'>question.</span> </p><p><span
  m='2246670'>So</span> <span m='2246720'>that's</span> <span
  m='2247030'>how</span> <span m='2247150'>we</span> <span
  m='2247250'>connected</span> <span m='2247690'>this</span> <span
  m='2247870'>up,</span> <span m='2248030'>because</span> <span
  m='2248180'>you're</span> <span m='2248280'>getting</span> <span
  m='2248570'>paid</span> <span m='2248920'>this</span> <span
  m='2249140'>much</span> <span m='2249830'>in</span> <span
  m='2250010'>our</span> <span m='2250180'>years,</span> <span
  m='2251130'>and</span> <span m='2251320'>that's</span> <span
  m='2251490'>worth</span> <span m='2252160'>that</span> <span
  m='2252470'>much</span> <span m='2252690'>degradation</span> <span
  m='2253390'>or</span> <span m='2253470'>that</span> <span
  m='2253620'>much</span> <span m='2253800'>devaluation</span> <span
  m='2254520'>today,</span> <span m='2255130'>and</span> <span
  m='2255270'>now</span> <span m='2255540'>we</span> <span
  m='2255740'>add</span> <span m='2255780'>up</span> <span m='2255820'>a</span>
  <span m='2255870'>total</span> <span m='2256140'>current</span> <span
  m='2256420'>value.</span> <span m='2258930'>So</span> <span
  m='2259050'>even</span> <span m='2259300'>a</span> <span
  m='2259340'>company</span> <span m='2259760'>that</span> <span
  m='2259860'>is</span> <span m='2259970'>paying</span> <span
  m='2260240'>you</span> <span m='2260330'>more</span> <span
  m='2260710'>and</span> <span m='2260870'>more</span> <span
  m='2261190'>every</span> <span m='2261510'>year</span> <span
  m='2261980'>still</span> <span m='2262200'>has</span> <span
  m='2262370'>a</span> <span m='2262430'>finite</span> <span
  m='2262820'>value,</span> <span m='2264740'>because</span> <span
  m='2266030'>the</span> <span m='2266240'>extra--</span> <span
  m='2267220'>the</span> <span m='2267300'>payments</span> <span
  m='2267900'>are</span> <span m='2268020'>increasing</span> <span
  m='2268570'>but</span> <span m='2268670'>only</span> <span
  m='2268890'>linearly.</span> <span m='2269990'>The</span> <span
  m='2270090'>value</span> <span m='2270480'>today</span> <span
  m='2270770'>is</span> <span m='2270870'>decreasing</span> <span
  m='2271360'>geometrically,</span> <span m='2272670'>and</span> <span
  m='2272820'>the</span> <span m='2272890'>geometric</span> <span
  m='2273490'>decrease</span> <span m='2273960'>wipes</span> <span
  m='2274390'>out</span> <span m='2274630'>the</span> <span
  m='2274700'>value</span> <span m='2275040'>of</span> <span
  m='2275100'>the</span> <span m='2275160'>company</span> <span
  m='2275480'>in</span> <span m='2275540'>the</span> <span
  m='2275600'>future.</span> <span m='2276600'>Yeah.</span> </p><p><span
  m='2277100'>AUDIENCE:</span> <span m='2277600'>Are you</span> <span
  m='2278600'>[? squaring ?]</span> <span m='2280600'>quantity</span> <span
  m='2281003'>of</span> <span m='2281406'>[INAUDIBLE].</span> </p><p><span
  m='2285640'>PROFESSOR: What</span> <span m='2285750'>did</span> <span
  m='2285850'>I</span> <span m='2285920'>do?</span> <span m='2286780'>Oh,</span>
  <span m='2287040'>wait,</span> <span m='2287350'>wait,</span> <span
  m='2287740'>wait.</span> <span m='2289030'>I</span> <span
  m='2289170'>screwed</span> <span m='2289440'>up</span> <span
  m='2289610'>here</span> <span m='2290071'>too.</span> <span
  m='2292380'>Is</span> <span m='2292510'>that</span> <span
  m='2292660'>what</span> <span m='2292760'>you're</span> <span
  m='2292870'>asking</span> <span m='2293110'>about?</span> <span
  m='2294700'>Yeah.</span> <span m='2295160'>That's</span> <span
  m='2295390'>what</span> <span m='2295490'>I</span> <span
  m='2295530'>should</span> <span m='2295680'>have</span> <span
  m='2295770'>done,</span> <span m='2295970'>right?</span> <span
  m='2296140'>Because</span> <span m='2296290'>I</span> <span
  m='2296340'>got</span> <span m='2296550'>1</span> <span
  m='2297020'>minus</span> <span m='2297450'>x</span> <span
  m='2298250'>is</span> <span m='2298430'>1</span> <span
  m='2298730'>minus</span> <span m='2299050'>1</span> <span
  m='2299270'>over</span> <span m='2299340'>1</span> <span
  m='2299580'>plus</span> <span m='2299830'>p.</span> <span
  m='2300600'>That</span> <span m='2301200'>gets</span> <span
  m='2301400'>squared,</span> <span m='2302800'>and</span> <span
  m='2302960'>now</span> <span m='2303260'>when</span> <span
  m='2303380'>I</span> <span m='2303420'>multiply</span> <span
  m='2303980'>1</span> <span m='2304250'>plus</span> <span m='2304510'>p</span>
  <span m='2304740'>squared,</span> <span m='2305970'>it's</span> <span
  m='2306150'>multiplying</span> <span m='2306570'>this</span> <span
  m='2306740'>by</span> <span m='2306840'>1</span> <span m='2307040'>plus</span>
  <span m='2307310'>p.</span> <span m='2308310'>It's</span> <span
  m='2308610'>1</span> <span m='2308850'>plus</span> <span m='2309080'>p</span>
  <span m='2309280'>minus</span> <span m='2309730'>1</span> <span
  m='2310020'>is</span> <span m='2310170'>p.</span> <span m='2310630'>So</span>
  <span m='2310770'>I</span> <span m='2310800'>have</span> <span
  m='2310910'>p</span> <span m='2311070'>squared.</span> <span
  m='2312490'>All</span> <span m='2312640'>right,</span> <span
  m='2312780'>so</span> <span m='2312855'>this</span> <span
  m='2312930'>part's</span> <span m='2313200'>OK.</span> <span
  m='2313550'>That</span> <span m='2313780'>part</span> <span
  m='2313980'>I</span> <span m='2314050'>wrote</span> <span
  m='2314270'>wrong.</span> <span m='2315610'>That's</span> <span
  m='2315890'>good.</span> <span m='2316280'>Any</span> <span
  m='2316480'>other</span> <span m='2316630'>questions?</span> </p><p><span
  m='2326430'>So</span> <span m='2326540'>let's</span> <span
  m='2326680'>do</span> <span m='2326820'>a</span> <span
  m='2326880'>simple</span> <span m='2327280'>example.</span> <span
  m='2343230'>What</span> <span m='2343550'>is</span> <span
  m='2344380'>this</span> <span m='2344610'>sum?</span> <span
  m='2354026'>A</span> <span m='2354510'>1/2</span> <span
  m='2355270'>plus</span> <span m='2356480'>2/4</span> <span
  m='2357910'>plus</span> <span m='2358310'>3/8</span> <span
  m='2359630'>plus</span> <span m='2360180'>4/16</span> <span
  m='2363060'>forever.</span> <span m='2363580'>What's</span> <span
  m='2363930'>that</span> <span m='2364700'>sum</span> <span
  m='2366130'>equal?</span> <span m='2372970'>You</span> <span
  m='2373120'>can</span> <span m='2373270'>plug</span> <span
  m='2373420'>that</span> <span m='2373580'>in</span> <span
  m='2373640'>the</span> <span m='2373700'>formula.</span> </p><p><span
  m='2375975'>AUDIENCE:</span> <span m='2376430'>[INAUDIBLE]</span> </p><p><span
  m='2378060'>PROFESSOR: Yeah.</span> <span m='2380440'>That's</span> <span
  m='2380650'>right.</span> <span m='2381260'>Good.</span> <span
  m='2383350'>These</span> <span m='2383530'>details.</span> <span
  m='2386310'>Otherwise</span> <span m='2386710'>that</span> <span
  m='2386890'>sum</span> <span m='2387140'>would</span> <span
  m='2387260'>be</span> <span m='2387370'>what?</span> <span
  m='2388156'>If</span> <span m='2388550'>I</span> <span
  m='2388660'>didn't</span> <span m='2388810'>put</span> <span
  m='2388930'>the</span> <span m='2389000'>negative</span> <span
  m='2389430'>here,</span> <span m='2390640'>it's</span> <span
  m='2390730'>going</span> <span m='2390840'>to</span> <span
  m='2391030'>be</span> <span m='2391400'>infinity,</span> <span
  m='2391500'>and</span> <span m='2391700'>that's</span> <span
  m='2391900'>not</span> <span m='2392150'>so</span> <span
  m='2392360'>interesting.</span> <span m='2393510'>The</span> <span
  m='2393640'>negative</span> <span m='2394030'>makes</span> <span
  m='2394270'>it</span> <span m='2394340'>more</span> <span
  m='2394540'>interesting,</span> <span m='2394970'>so</span> <span
  m='2395120'>I</span> <span m='2395170'>got</span> <span m='2395380'>1</span>
  <span m='2395580'>over</span> <span m='2395740'>2</span> <span
  m='2395970'>to</span> <span m='2396035'>the</span> <span m='2396100'>i</span>
  <span m='2396280'>in</span> <span m='2396400'>there.</span> <span
  m='2397810'>What's</span> <span m='2398030'>it</span> <span
  m='2398110'>worth</span> <span m='2398340'>then?</span> <span
  m='2401790'>Well,</span> <span m='2402180'>I</span> <span
  m='2402240'>can</span> <span m='2402350'>plug</span> <span
  m='2402545'>in</span> <span m='2402740'>the</span> <span
  m='2402810'>formula.</span> <span m='2404030'>What's</span> <span
  m='2404310'>x?</span> <span m='2406650'>One</span> <span
  m='2407060'>half.</span> <span m='2407760'>So</span> <span
  m='2407940'>I</span> <span m='2408010'>get</span> <span m='2408170'>1/2</span>
  <span m='2409150'>over</span> <span m='2409560'>1</span> <span
  m='2409840'>minus</span> <span m='2410250'>1/2</span> <span
  m='2410870'>squared</span> <span m='2412670'>is</span> <span
  m='2413500'>1/2</span> <span m='2414510'>over</span> <span
  m='2415300'>1/4,</span> <span m='2416740'>and</span> <span
  m='2416910'>that's</span> <span m='2417270'>2.</span> <span
  m='2424710'>Any</span> <span m='2424860'>questions</span> <span
  m='2425300'>on</span> <span m='2425420'>that</span> <span
  m='2426250'>formula?</span> <span m='2428925'>It's</span> <span
  m='2429210'>amazing</span> <span m='2429550'>how</span> <span
  m='2429700'>useful</span> <span m='2430080'>these</span> <span
  m='2430270'>things</span> <span m='2430470'>get</span> <span
  m='2430620'>to</span> <span m='2430690'>be</span> <span
  m='2430800'>later.</span> </p><p><span m='2434910'>So</span> <span
  m='2435230'>that's</span> <span m='2435710'>sort</span> <span
  m='2435870'>of</span> <span m='2435940'>the</span> <span
  m='2436000'>geometric</span> <span m='2436940'>kinds</span> <span
  m='2437400'>of</span> <span m='2437490'>things.</span> <span
  m='2439130'>Next</span> <span m='2439420'>I</span> <span
  m='2439460'>want</span> <span m='2439630'>to</span> <span
  m='2439700'>talk</span> <span m='2439980'>about</span> <span
  m='2440710'>more</span> <span m='2440940'>of</span> <span
  m='2441000'>the</span> <span m='2441120'>arithmetic</span> <span
  m='2441910'>kinds</span> <span m='2442260'>of</span> <span
  m='2442340'>sums</span> <span m='2443160'>and</span> <span
  m='2443310'>what</span> <span m='2443480'>you</span> <span
  m='2443550'>do</span> <span m='2443720'>there.</span> <span
  m='2445440'>In</span> <span m='2445600'>fact,</span> <span
  m='2445930'>we've</span> <span m='2445970'>already</span> <span
  m='2446200'>seen</span> <span m='2446680'>one</span> <span
  m='2447020'>that</span> <span m='2447110'>we've</span> <span
  m='2447270'>done.</span> <span m='2449210'>If</span> <span
  m='2449390'>I</span> <span m='2449550'>sum</span> <span m='2450890'>i</span>
  <span m='2451230'>equals</span> <span m='2451680'>1</span> <span
  m='2452050'>to</span> <span m='2452160'>n</span> <span m='2452960'>of</span>
  <span m='2453120'>i--</span> <span m='2454110'>I</span> <span
  m='2454570'>think</span> <span m='2454730'>we've</span> <span
  m='2454900'>already</span> <span m='2455100'>done</span> <span
  m='2455390'>this</span> <span m='2455610'>one--</span> <span
  m='2455860'>that's</span> <span m='2456080'>just</span> <span
  m='2456370'>n</span> <span m='2457310'>times</span> <span m='2457420'>n</span>
  <span m='2457700'>plus</span> <span m='2457990'>1</span> <span
  m='2458460'>over</span> <span m='2458720'>2,</span> <span
  m='2459500'>and</span> <span m='2459890'>probably</span> <span
  m='2460220'>most</span> <span m='2460530'>of</span> <span
  m='2460610'>you</span> <span m='2460740'>even</span> <span
  m='2460870'>learned</span> <span m='2461170'>that</span> <span
  m='2461390'>formula</span> <span m='2461820'>back</span> <span
  m='2462650'>in</span> <span m='2462810'>middle</span> <span
  m='2463050'>school,</span> <span m='2463380'>I'm</span> <span
  m='2463500'>guessing--</span> <span m='2464170'>maybe</span> <span
  m='2464440'>before.</span> </p><p><span m='2467220'>How</span> <span
  m='2467410'>many</span> <span m='2467620'>people</span> <span
  m='2468210'>know</span> <span m='2468460'>the</span> <span
  m='2468630'>answer</span> <span m='2468950'>for</span> <span
  m='2469090'>this</span> <span m='2469370'>sum?</span> <span
  m='2475000'>The</span> <span m='2475110'>sum</span> <span
  m='2475520'>of</span> <span m='2475650'>the</span> <span
  m='2475720'>squares--</span> <span m='2476650'>the</span> <span
  m='2476750'>first</span> <span m='2476990'>n</span> <span
  m='2477130'>squares.</span> <span m='2477970'>Somebody</span> <span
  m='2478210'>knows.</span> <span m='2478390'>What</span> <span
  m='2478770'>is</span> <span m='2478870'>it?</span> </p><p><span
  m='2479720'>AUDIENCE:</span> <span m='2480080'>n</span> <span
  m='2480850'>times</span> <span m='2481240'>n</span> <span
  m='2481430'>plus</span> <span m='2481650'>1</span> <span
  m='2483378'>times</span> <span m='2483594'>2n</span> <span
  m='2483940'>plus</span> <span m='2484180'>1,</span> <span
  m='2485590'>all</span> <span m='2485770'>over</span> <span
  m='2485950'>6.</span> </p><p><span m='2486940'>PROFESSOR: Very</span> <span
  m='2487220'>good.</span> <span m='2487470'>That</span> <span
  m='2487630'>is</span> <span m='2487800'>correct.</span> <span
  m='2489160'>Most</span> <span m='2489410'>people</span> <span
  m='2489650'>don't</span> <span m='2490610'>remember</span> <span
  m='2491020'>that</span> <span m='2491230'>one.</span> <span
  m='2491450'>It's</span> <span m='2491485'>a</span> <span
  m='2491520'>little</span> <span m='2491790'>harder</span> <span
  m='2492250'>to</span> <span m='2492420'>derive.</span> <span
  m='2495140'>How</span> <span m='2495370'>would</span> <span
  m='2495490'>you</span> <span m='2495570'>prove</span> <span
  m='2495940'>this</span> <span m='2497980'>by</span> <span
  m='2498230'>induction?</span> <span m='2499410'>Unfortunately,</span> <span
  m='2500080'>induction</span> <span m='2500550'>doesn't</span> <span
  m='2500860'>tell</span> <span m='2501060'>you</span> <span
  m='2501200'>how</span> <span m='2501380'>to</span> <span
  m='2501490'>remember</span> <span m='2502000'>what</span> <span
  m='2502200'>the</span> <span m='2502270'>formula</span> <span
  m='2502720'>was,</span> <span m='2504260'>and</span> <span
  m='2504480'>there's</span> <span m='2504630'>a</span> <span
  m='2504680'>couple</span> <span m='2504980'>of</span> <span
  m='2505060'>ways</span> <span m='2505410'>you</span> <span
  m='2505520'>can</span> <span m='2506050'>go</span> <span
  m='2506220'>about</span> <span m='2506540'>that.</span> </p><p><span
  m='2507700'>One</span> <span m='2508070'>is,</span> <span
  m='2508330'>you</span> <span m='2508450'>can</span> <span
  m='2508860'>remember</span> <span m='2509580'>or</span> <span
  m='2509780'>guess</span> <span m='2510460'>that</span> <span
  m='2510640'>the</span> <span m='2510830'>answer</span> <span
  m='2511240'>is</span> <span m='2511410'>a</span> <span
  m='2511500'>polynomial</span> <span m='2511885'>in</span> <span
  m='2512270'>n.</span> <span m='2513222'>In</span> <span
  m='2513700'>fact,</span> <span m='2514080'>because</span> <span
  m='2514720'>you're</span> <span m='2514860'>summing</span> <span
  m='2515180'>squares,</span> <span m='2515710'>you</span> <span
  m='2515800'>might</span> <span m='2516040'>guess</span> <span
  m='2516520'>that</span> <span m='2517380'>it's</span> <span
  m='2517680'>a</span> <span m='2517770'>cubic</span> <span
  m='2518260'>polynomial</span> <span m='2518880'>in</span> <span
  m='2518940'>n,</span> <span m='2520100'>and</span> <span m='2520270'>if</span>
  <span m='2520360'>you</span> <span m='2520480'>remember</span> <span
  m='2520840'>just</span> <span m='2521140'>that</span> <span
  m='2521380'>or</span> <span m='2521430'>guess</span> <span
  m='2521780'>just</span> <span m='2522130'>that,</span> <span
  m='2523340'>then</span> <span m='2523800'>you</span> <span
  m='2523890'>could</span> <span m='2524030'>actually</span> <span
  m='2524340'>plug</span> <span m='2524555'>in</span> <span
  m='2524770'>values</span> <span m='2525380'>and</span> <span
  m='2525490'>get</span> <span m='2525640'>the</span> <span
  m='2525770'>answer.</span> </p><p><span m='2528540'>And</span> <span
  m='2528680'>this</span> <span m='2528870'>is--</span> <span
  m='2529370'>you</span> <span m='2529585'>know,</span> <span
  m='2529800'>a</span> <span m='2530160'>common</span> <span
  m='2530570'>method</span> <span m='2530870'>of</span> <span
  m='2530980'>solving</span> <span m='2531410'>these</span> <span
  m='2531600'>sums</span> <span m='2531960'>is</span> <span
  m='2532070'>you</span> <span m='2532160'>sort</span> <span
  m='2532360'>of</span> <span m='2532450'>guess</span> <span
  m='2532850'>the</span> <span m='2532920'>form</span> <span
  m='2533290'>of</span> <span m='2533370'>the</span> <span
  m='2533440'>solution.</span> <span m='2535010'>In</span> <span
  m='2535150'>this</span> <span m='2535330'>case</span> <span
  m='2537150'>you</span> <span m='2537310'>might</span> <span
  m='2537640'>guess</span> <span m='2542070'>that</span> <span
  m='2542280'>for</span> <span m='2542470'>all</span> <span
  m='2542760'>n,</span> <span m='2543760'>the</span> <span
  m='2543940'>sum</span> <span m='2544480'>i</span> <span
  m='2544810'>equals</span> <span m='2545180'>1</span> <span
  m='2545480'>to</span> <span m='2545610'>n</span> <span m='2545920'>of</span>
  <span m='2546015'>i</span> <span m='2546110'>squared</span> <span
  m='2547570'>equals</span> <span m='2548710'>a</span> <span
  m='2548830'>cubic.</span> <span m='2554730'>And</span> <span
  m='2555310'>then</span> <span m='2555560'>what</span> <span
  m='2555750'>you</span> <span m='2555850'>would</span> <span
  m='2555970'>do</span> <span m='2556300'>is</span> <span
  m='2556460'>plug</span> <span m='2556640'>in</span> <span
  m='2558300'>the</span> <span m='2558400'>value</span> <span
  m='2559160'>n</span> <span m='2559360'>equals</span> <span
  m='2560710'>1,</span> <span m='2561380'>n</span> <span
  m='2561560'>equals</span> <span m='2562110'>2,</span> <span
  m='2562490'>maybe</span> <span m='2562680'>even--</span> <span
  m='2563520'>we'll</span> <span m='2563650'>make</span> <span
  m='2563860'>it</span> <span m='2564040'>n</span> <span
  m='2564200'>equals</span> <span m='2564520'>0--</span> <span
  m='2565510'>make</span> <span m='2565690'>it</span> <span
  m='2565790'>simple</span> <span m='2566940'>and</span> <span
  m='2567080'>start</span> <span m='2567350'>getting</span> <span
  m='2567560'>some</span> <span m='2568120'>constraints</span> <span
  m='2568770'>on</span> <span m='2568970'>the</span> <span
  m='2569380'>coefficients.</span> <span m='2571380'>If</span> <span
  m='2571480'>you</span> <span m='2571610'>would</span> <span
  m='2571730'>plug</span> <span m='2571968'>in</span> <span m='2575480'>n</span>
  <span m='2575940'>equals</span> <span m='2576730'>0,</span> <span
  m='2577990'>the</span> <span m='2578110'>sum</span> <span
  m='2578560'>is</span> <span m='2578680'>0.</span> </p><p><span
  m='2582300'>The</span> <span m='2582400'>polynomial</span> <span
  m='2583120'>evaluates</span> <span m='2583810'>to</span> <span
  m='2583920'>d.</span> <span m='2586250'>That</span> <span
  m='2586360'>tells</span> <span m='2586570'>you</span> <span
  m='2586670'>what</span> <span m='2586790'>d</span> <span
  m='2586920'>has</span> <span m='2587010'>got</span> <span
  m='2587140'>to</span> <span m='2587200'>be</span> <span
  m='2587300'>right</span> <span m='2587470'>away.</span> <span
  m='2587935'>n</span> <span m='2588400'>equals</span> <span
  m='2588710'>1.</span> <span m='2590160'>The</span> <span
  m='2590290'>sum</span> <span m='2590800'>is</span> <span m='2591010'>1,</span>
  <span m='2592520'>and</span> <span m='2592760'>when</span> <span
  m='2592870'>you</span> <span m='2592940'>plug</span> <span
  m='2593240'>into</span> <span m='2593400'>the</span> <span
  m='2593480'>polynomial,</span> <span m='2594050'>you</span> <span
  m='2594110'>get</span> <span m='2594260'>a</span> <span
  m='2594720'>plus</span> <span m='2595020'>b</span> <span
  m='2595890'>plus</span> <span m='2596170'>c</span> <span
  m='2596560'>plus</span> <span m='2596860'>d.</span> <span m='2598760'>n</span>
  <span m='2598790'>equals</span> <span m='2599110'>2.</span> <span
  m='2601540'>Well,</span> <span m='2601940'>that's</span> <span
  m='2602200'>1</span> <span m='2602440'>plus</span> <span m='2602660'>4</span>
  <span m='2602960'>is</span> <span m='2603070'>5,</span> <span
  m='2605540'>2</span> <span m='2605840'>cubed</span> <span
  m='2606230'>is</span> <span m='2606430'>8,</span> <span m='2606710'>so</span>
  <span m='2606855'>you</span> <span m='2607000'>have</span> <span
  m='2607145'>8a</span> <span m='2608450'>plus</span> <span
  m='2608710'>4b</span> <span m='2610160'>plus</span> <span
  m='2610440'>2c</span> <span m='2611170'>plus</span> <span
  m='2611380'>d,</span> <span m='2612680'>and</span> <span
  m='2612930'>you'll</span> <span m='2613030'>need</span> <span
  m='2613260'>one</span> <span m='2613540'>more</span> <span
  m='2613860'>since</span> <span m='2614070'>you've</span> <span
  m='2614170'>got</span> <span m='2614340'>four</span> <span
  m='2614600'>variables.</span> <span m='2616720'>Let's</span> <span
  m='2616920'>see,</span> <span m='2617105'>1</span> <span
  m='2617290'>plus</span> <span m='2617570'>4</span> <span
  m='2617870'>plus</span> <span m='2618130'>9</span> <span m='2618420'>is</span>
  <span m='2618530'>14.</span> <span m='2620950'>I've</span> <span
  m='2621300'>now</span> <span m='2621590'>got</span> <span m='2622160'>3</span>
  <span m='2622490'>cubed</span> <span m='2622980'>is</span> <span
  m='2623385'>27a</span> <span m='2625100'>plus</span> <span
  m='2626190'>9b</span> <span m='2627270'>plus</span> <span
  m='2627640'>3c</span> <span m='2628510'>plus</span> <span
  m='2628760'>d.</span> </p><p><span m='2630690'>So</span> <span
  m='2630850'>now</span> <span m='2631040'>I've</span> <span
  m='2631130'>got</span> <span m='2631320'>four</span> <span
  m='2631640'>equations</span> <span m='2632230'>and</span> <span
  m='2632350'>four</span> <span m='2632590'>variables</span> <span
  m='2634120'>and,</span> <span m='2634580'>with</span> <span
  m='2634750'>any</span> <span m='2634940'>luck,</span> <span
  m='2635240'>I</span> <span m='2635280'>can</span> <span
  m='2635420'>solve</span> <span m='2635730'>that</span> <span
  m='2635900'>system</span> <span m='2636250'>of</span> <span
  m='2636330'>equations</span> <span m='2637360'>and</span> <span
  m='2637510'>get</span> <span m='2637660'>the</span> <span
  m='2637780'>answer.</span> <span m='2638930'>And,</span> <span
  m='2639120'>in</span> <span m='2639180'>fact,</span> <span
  m='2639490'>you</span> <span m='2639570'>can.</span> <span
  m='2640090'>When</span> <span m='2640240'>you</span> <span
  m='2640310'>solve</span> <span m='2640690'>this</span> <span
  m='2640780'>system,</span> <span m='2641290'>you</span> <span
  m='2641390'>get</span> <span m='2642790'>a</span> <span
  m='2643120'>equals</span> <span m='2643470'>1/3,</span> <span
  m='2645100'>b</span> <span m='2645520'>equals</span> <span
  m='2645870'>1/2,</span> <span m='2647300'>c</span> <span
  m='2647790'>equals</span> <span m='2648110'>1/6,</span> <span
  m='2649250'>and</span> <span m='2649500'>d</span> <span
  m='2649710'>equals</span> <span m='2649920'>0.</span> <span
  m='2651460'>And</span> <span m='2651640'>that's</span> <span
  m='2651830'>exactly</span> <span m='2652340'>what</span> <span
  m='2652510'>you</span> <span m='2652600'>get</span> <span
  m='2653300'>in</span> <span m='2653390'>that</span> <span
  m='2653540'>formula.</span> <span m='2654970'>So</span> <span
  m='2655000'>that's</span> <span m='2655150'>a</span> <span
  m='2655200'>way</span> <span m='2655350'>to</span> <span
  m='2655460'>reproduce</span> <span m='2656240'>the</span> <span
  m='2656320'>formula</span> <span m='2656750'>if</span> <span
  m='2656840'>you</span> <span m='2656930'>forgot</span> <span
  m='2657310'>it.</span> </p><p><span m='2659650'>Now,</span> <span
  m='2660710'>this</span> <span m='2661070'>method--</span> <span
  m='2662580'>really</span> <span m='2662900'>to</span> <span
  m='2662960'>be</span> <span m='2663090'>sure</span> <span
  m='2663330'>you</span> <span m='2663410'>got</span> <span
  m='2663560'>the</span> <span m='2663650'>right</span> <span
  m='2663850'>answer--</span> <span m='2665200'>you've</span> <span
  m='2665350'>got</span> <span m='2665460'>to</span> <span m='2665520'>go</span>
  <span m='2665620'>prove</span> <span m='2665830'>it</span> <span
  m='2665920'>by</span> <span m='2666080'>induction,</span> <span
  m='2667490'>because</span> <span m='2667650'>I</span> <span
  m='2668960'>derived</span> <span m='2669810'>the</span> <span
  m='2669980'>answer--</span> <span m='2670510'>if</span> <span
  m='2670720'>it</span> <span m='2670800'>was</span> <span m='2670920'>a</span>
  <span m='2670990'>polynomial,</span> <span m='2671740'>I</span> <span
  m='2671840'>would</span> <span m='2671960'>have</span> <span
  m='2672050'>gotten</span> <span m='2672230'>it</span> <span
  m='2672340'>right,</span> <span m='2672530'>but</span> <span
  m='2672640'>I</span> <span m='2672690'>might</span> <span
  m='2672900'>be</span> <span m='2673000'>wrong</span> <span
  m='2673250'>in</span> <span m='2673320'>my</span> <span
  m='2673420'>guess.</span> <span m='2674480'>And</span> <span
  m='2674580'>to</span> <span m='2674640'>make</span> <span
  m='2674790'>sure</span> <span m='2674900'>your</span> <span
  m='2675020'>guess</span> <span m='2675330'>is</span> <span
  m='2675440'>right,</span> <span m='2675710'>you've</span> <span
  m='2675800'>got</span> <span m='2675910'>to</span> <span m='2675970'>go</span>
  <span m='2676070'>back</span> <span m='2676330'>and</span> <span
  m='2676430'>use</span> <span m='2676590'>induction</span> <span
  m='2676990'>to</span> <span m='2677070'>prove</span> <span
  m='2677300'>it</span> <span m='2678060'>for</span> <span
  m='2678170'>this</span> <span m='2678310'>approach.</span> <span
  m='2678786'>Yeah.</span> </p><p><span m='2679262'>AUDIENCE:</span> <span
  m='2679740'>How do you know</span> <span m='2680143'>that it would be</span>
  <span m='2680546'>[INAUDIBLE]</span> <span m='2681392'>and</span> <span
  m='2681834'>not</span> <span m='2681981'>some</span> <span
  m='2682128'>higher</span> <span m='2682276'>power?</span> </p><p><span
  m='2683160'>PROFESSOR: Well,</span> <span m='2683630'>it</span> <span
  m='2683800'>turns</span> <span m='2683970'>out</span> <span
  m='2684680'>that</span> <span m='2685040'>anytime</span> <span
  m='2685580'>you're</span> <span m='2685710'>summing</span> <span
  m='2686520'>powers,</span> <span m='2687570'>the</span> <span
  m='2687720'>answer</span> <span m='2688130'>is</span> <span
  m='2688640'>a</span> <span m='2688790'>polynomial</span> <span
  m='2689380'>to</span> <span m='2689460'>one</span> <span
  m='2689630'>higher</span> <span m='2689840'>degree.</span> <span
  m='2691540'>So</span> <span m='2691900'>if</span> <span m='2692150'>you</span>
  <span m='2692210'>just</span> <span m='2692380'>remembered</span> <span
  m='2692640'>that</span> <span m='2692860'>fact,</span> <span
  m='2693065'>or</span> <span m='2693270'>you</span> <span
  m='2693380'>guessed</span> <span m='2693720'>that</span> <span
  m='2693920'>fact.</span> <span m='2694750'>Another</span> <span
  m='2695040'>way</span> <span m='2695160'>to</span> <span
  m='2695230'>sort</span> <span m='2695560'>of</span> <span
  m='2695620'>imagine</span> <span m='2696100'>that</span> <span
  m='2696250'>might</span> <span m='2696450'>be</span> <span
  m='2696550'>true</span> <span m='2698000'>is</span> <span
  m='2698570'>that</span> <span m='2699720'>I'm</span> <span
  m='2700090'>getting</span> <span m='2700460'>n</span> <span
  m='2700650'>of</span> <span m='2700760'>them,</span> <span
  m='2701040'>so</span> <span m='2701080'>I</span> <span
  m='2701120'>might</span> <span m='2701320'>be</span> <span
  m='2701410'>multiplying--</span> <span m='2702120'>the</span> <span
  m='2702270'>top</span> <span m='2702580'>one</span> <span
  m='2702770'>is</span> <span m='2702910'>n</span> <span
  m='2703060'>squared,</span> <span m='2704500'>so</span> <span
  m='2705270'>I'm</span> <span m='2705450'>going</span> <span
  m='2705590'>to</span> <span m='2705650'>have</span> <span m='2705840'>n</span>
  <span m='2705906'>of</span> <span m='2705973'>them</span> <span
  m='2706240'>about</span> <span m='2706600'>n</span> <span
  m='2706750'>squared.</span> <span m='2707900'>Might</span> <span
  m='2708080'>be</span> <span m='2708160'>something</span> <span
  m='2708430'>like</span> <span m='2708630'>n</span> <span
  m='2708740'>cubed.</span> <span m='2711370'>That's</span> <span
  m='2711610'>another</span> <span m='2711810'>way</span> <span
  m='2712670'>you</span> <span m='2712800'>could</span> <span
  m='2712900'>think</span> <span m='2713120'>of</span> <span
  m='2713200'>it,</span> <span m='2714230'>to</span> <span
  m='2714340'>guess</span> <span m='2714640'>that.</span> <span
  m='2716660'>Any</span> <span m='2716860'>other</span> <span
  m='2717010'>questions</span> <span m='2719560'>on</span> <span
  m='2719700'>this?</span> </p><p><span m='2725130'>So</span> <span
  m='2725400'>far,</span> <span m='2725620'>all</span> <span
  m='2725960'>these</span> <span m='2726190'>sums</span> <span
  m='2726810'>had</span> <span m='2727030'>nice</span> <span
  m='2727310'>closed</span> <span m='2727620'>forms,</span> <span
  m='2729110'>and</span> <span m='2729310'>a</span> <span m='2729340'>lot</span>
  <span m='2729600'>of</span> <span m='2729670'>them</span> <span
  m='2729970'>do</span> <span m='2730350'>that</span> <span
  m='2730480'>you'll</span> <span m='2730640'>encounter</span> <span
  m='2731190'>later</span> <span m='2731520'>on,</span> <span
  m='2732240'>but</span> <span m='2732450'>not</span> <span
  m='2732710'>all,</span> <span m='2733410'>and</span> <span
  m='2733640'>sometimes</span> <span m='2734260'>you</span> <span
  m='2734340'>get</span> <span m='2734540'>sums</span> <span
  m='2735510'>that</span> <span m='2735750'>don't</span> <span
  m='2736130'>have</span> <span m='2736730'>a</span> <span
  m='2736780'>nice</span> <span m='2737020'>closed</span> <span
  m='2737310'>form--</span> <span m='2737580'>at</span> <span
  m='2737650'>least</span> <span m='2737880'>nobody</span> <span
  m='2738210'>has</span> <span m='2738320'>ever</span> <span
  m='2738470'>figured</span> <span m='2738790'>out</span> <span
  m='2738980'>one,</span> <span m='2739670'>and</span> <span
  m='2740170'>probably</span> <span m='2740720'>doesn't</span> <span
  m='2741040'>always</span> <span m='2741300'>exist.</span> <span
  m='2742560'>For</span> <span m='2742710'>example,</span> <span
  m='2743280'>what</span> <span m='2743570'>if</span> <span m='2743710'>I</span>
  <span m='2743940'>want</span> <span m='2744200'>to</span> <span
  m='2744260'>sum</span> <span m='2745540'>the</span> <span
  m='2745680'>first</span> <span m='2746330'>n</span> <span
  m='2746820'>square</span> <span m='2747380'>roots</span> <span
  m='2748390'>of</span> <span m='2748550'>integers?</span> <span
  m='2753340'>Let's</span> <span m='2753490'>write</span> <span
  m='2753918'>that</span> <span m='2754346'>down.</span> </p><p><span
  m='2764400'>So</span> <span m='2764690'>say</span> <span m='2764990'>I</span>
  <span m='2765040'>want</span> <span m='2765390'>a</span> <span
  m='2765470'>closed</span> <span m='2765990'>form</span> <span
  m='2766520'>for</span> <span m='2766920'>this</span> <span
  m='2767120'>guy.</span> <span m='2773560'>Nobody</span> <span
  m='2773970'>knows</span> <span m='2774870'>an</span> <span
  m='2775030'>answer</span> <span m='2775290'>for</span> <span
  m='2775410'>that,</span> <span m='2776940'>but</span> <span
  m='2777150'>there</span> <span m='2777340'>are</span> <span
  m='2777640'>ways</span> <span m='2778610'>of</span> <span
  m='2778880'>getting</span> <span m='2779240'>very</span> <span
  m='2779750'>good,</span> <span m='2780500'>close</span> <span
  m='2780990'>bounds</span> <span m='2781480'>on</span> <span
  m='2781660'>it</span> <span m='2781840'>that</span> <span
  m='2782000'>are</span> <span m='2782040'>closed</span> <span
  m='2782410'>form,</span> <span m='2782930'>and</span> <span
  m='2783070'>these</span> <span m='2783290'>are</span> <span
  m='2783340'>very</span> <span m='2783680'>important,</span> <span
  m='2783950'>and</span> <span m='2784220'>we're</span> <span
  m='2784320'>going</span> <span m='2784420'>to</span> <span
  m='2784520'>use</span> <span m='2784590'>this</span> <span
  m='2785280'>the</span> <span m='2785440'>rest</span> <span
  m='2785660'>of</span> <span m='2785730'>today</span> <span
  m='2786060'>and</span> <span m='2786150'>the</span> <span
  m='2786220'>rest</span> <span m='2786450'>of</span> <span
  m='2786520'>next</span> <span m='2786770'>time.</span> <span
  m='2787890'>And</span> <span m='2788280'>they're</span> <span
  m='2788390'>based</span> <span m='2788770'>on</span> <span
  m='2789420'>replacing</span> <span m='2790090'>the</span> <span
  m='2790160'>sum</span> <span m='2791040'>with</span> <span
  m='2791230'>an</span> <span m='2791320'>integral,</span> <span
  m='2792740'>and</span> <span m='2792890'>the</span> <span
  m='2792990'>integral</span> <span m='2793490'>is</span> <span
  m='2793740'>very</span> <span m='2794050'>close</span> <span
  m='2794370'>to</span> <span m='2794440'>the</span> <span
  m='2794520'>right</span> <span m='2794730'>answer,</span> <span
  m='2795140'>and</span> <span m='2795240'>then</span> <span
  m='2795340'>we</span> <span m='2795440'>can</span> <span
  m='2795470'>see</span> <span m='2795640'>what</span> <span
  m='2795760'>the</span> <span m='2795860'>error</span> <span
  m='2796070'>terms</span> <span m='2796370'>are.</span> </p><p><span
  m='2797820'>So</span> <span m='2798120'>let's</span> <span
  m='2798340'>first</span> <span m='2798680'>look</span> <span
  m='2798810'>at</span> <span m='2798880'>the</span> <span
  m='2798950'>case</span> <span m='2799390'>when</span> <span
  m='2799580'>we've</span> <span m='2799700'>got</span> <span
  m='2799880'>a</span> <span m='2799910'>sum</span> <span
  m='2800270'>where</span> <span m='2800370'>the</span> <span
  m='2800460'>terms</span> <span m='2800900'>are</span> <span
  m='2801020'>increasing</span> <span m='2801970'>as</span> <span
  m='2802150'>i</span> <span m='2802560'>grows,</span> <span
  m='2806960'>and</span> <span m='2807320'>we'll</span> <span
  m='2807480'>call</span> <span m='2807710'>these</span> <span
  m='2808010'>integration</span> <span m='2808650'>bounds,</span> <span
  m='2814240'>and</span> <span m='2814410'>a</span> <span
  m='2814440'>general</span> <span m='2814930'>sum</span> <span
  m='2815145'>will</span> <span m='2815360'>look</span> <span
  m='2815590'>like</span> <span m='2815800'>this--</span> <span
  m='2816560'>i</span> <span m='2816840'>equals</span> <span
  m='2817000'>1</span> <span m='2817230'>to</span> <span m='2817380'>n</span>
  <span m='2817790'>of</span> <span m='2818140'>f</span> <span
  m='2818400'>of</span> <span m='2818550'>i,</span> <span m='2820690'>and</span>
  <span m='2820890'>the</span> <span m='2820950'>first</span> <span
  m='2821300'>case</span> <span m='2822170'>is</span> <span
  m='2822360'>when</span> <span m='2822620'>f</span> <span m='2822990'>is</span>
  <span m='2823200'>a</span> <span m='2823330'>positive</span> <span
  m='2824330'>increasing</span> <span m='2824870'>function,</span> <span
  m='2832330'>increasing</span> <span m='2832850'>in</span> <span
  m='2832950'>i.</span> <span m='2840660'>Integration</span> <span
  m='2841040'>bounds,</span> <span m='2841470'>and</span> <span
  m='2841600'>so</span> <span m='2841780'>we're</span> <span
  m='2841990'>increasing</span> <span m='2842475'>function.</span> <span
  m='2848160'>So</span> <span m='2848250'>let</span> <span m='2848340'>me</span>
  <span m='2848420'>draw</span> <span m='2848670'>a</span> <span
  m='2848720'>picture</span> <span m='2849340'>that</span> <span
  m='2849480'>will</span> <span m='2849820'>hopefully</span> <span
  m='2851530'>make</span> <span m='2851790'>the</span> <span
  m='2851860'>bounds</span> <span m='2852145'>that</span> <span
  m='2852430'>we're</span> <span m='2852480'>going</span> <span
  m='2852600'>to</span> <span m='2852680'>get</span> <span
  m='2853310'>pretty</span> <span m='2853600'>easy.</span> </p><p><span
  m='2867550'>So</span> <span m='2868210'>let's</span> <span
  m='2869080'>draw</span> <span m='2870890'>the</span> <span
  m='2871032'>sum</span> <span m='2871460'>here</span> <span
  m='2873130'>as</span> <span m='2873360'>follows.</span> <span
  m='2873590'>I've</span> <span m='2873620'>got</span> <span
  m='2873780'>0,</span> <span m='2874320'>1,</span> <span m='2875100'>2,</span>
  <span m='2876320'>3,</span> <span m='2879190'>n</span> <span
  m='2879450'>minus</span> <span m='2879810'>2,</span> <span
  m='2880900'>n</span> <span m='2881160'>minus</span> <span
  m='2881510'>1,</span> <span m='2882686'>n,</span> <span m='2884360'>and</span>
  <span m='2885430'>draw</span> <span m='2885620'>the</span> <span
  m='2885720'>values</span> <span m='2886160'>of</span> <span
  m='2886290'>f</span> <span m='2886520'>here.</span> <span
  m='2886840'>Here's</span> <span m='2887110'>f</span> <span
  m='2887410'>of</span> <span m='2887640'>1,</span> <span m='2889650'>f</span>
  <span m='2889900'>of</span> <span m='2890020'>2--</span> <span
  m='2890620'>it's</span> <span m='2890750'>increasing--</span> <span
  m='2892900'>f</span> <span m='2893030'>of</span> <span m='2893160'>3,</span>
  <span m='2897260'>f</span> <span m='2897330'>of</span> <span
  m='2897400'>n</span> <span m='2897470'>minus</span> <span
  m='2897820'>1,</span> <span m='2898290'>and</span> <span m='2898760'>f</span>
  <span m='2899240'>of</span> <span m='2899310'>n.</span> <span
  m='2903180'>Then</span> <span m='2903370'>I'll</span> <span
  m='2903490'>draw</span> <span m='2903960'>the</span> <span
  m='2906430'>rectangles</span> <span m='2907210'>here.</span> <span
  m='2911640'>So</span> <span m='2911970'>this</span> <span
  m='2912200'>has</span> <span m='2912520'>area</span> <span
  m='2914290'>of</span> <span m='2914675'>f</span> <span m='2915060'>of</span>
  <span m='2915160'>1,</span> <span m='2916000'>this</span> <span
  m='2916240'>has</span> <span m='2916510'>area</span> <span
  m='2916810'>f</span> <span m='2917070'>of</span> <span m='2917170'>2,</span>
  <span m='2918620'>this</span> <span m='2918850'>has</span> <span
  m='2919080'>area</span> <span m='2919370'>f</span> <span m='2919590'>of</span>
  <span m='2919670'>3,</span> <span m='2921500'>and</span> <span
  m='2921620'>we</span> <span m='2921700'>keep</span> <span
  m='2921950'>on</span> <span m='2922160'>going.</span> <span
  m='2923630'>Let's</span> <span m='2924120'>see,</span> <span
  m='2925620'>this</span> <span m='2925840'>will</span> <span
  m='2925930'>be</span> <span m='2926100'>f</span> <span m='2926240'>of</span>
  <span m='2926360'>n</span> <span m='2926480'>minus</span> <span
  m='2926790'>2</span> <span m='2927070'>on</span> <span m='2927180'>this</span>
  <span m='2927380'>one--</span> <span m='2927750'>I'll</span> <span
  m='2927868'>just</span> <span m='2927986'>do</span> <span m='2928460'>f</span>
  <span m='2928530'>of</span> <span m='2928605'>n</span> <span
  m='2928680'>minus</span> <span m='2928970'>1,</span> <span
  m='2929210'>draw</span> <span m='2929420'>this</span> <span
  m='2929580'>guy</span> <span m='2930420'>here.</span> </p><p><span
  m='2933950'>So</span> <span m='2934020'>its</span> <span
  m='2934140'>unit</span> <span m='2934510'>width,</span> <span
  m='2934870'>its</span> <span m='2934990'>height</span> <span
  m='2935320'>is</span> <span m='2935710'>f</span> <span m='2935900'>of</span>
  <span m='2935990'>n</span> <span m='2936100'>minus</span> <span
  m='2936400'>1,</span> <span m='2936670'>so</span> <span m='2936870'>its</span>
  <span m='2937090'>area</span> <span m='2937410'>is</span> <span
  m='2937500'>f</span> <span m='2937585'>of</span> <span m='2937780'>n</span>
  <span m='2937900'>minus</span> <span m='2938200'>1,</span> <span
  m='2939240'>and</span> <span m='2939430'>then</span> <span
  m='2942040'>f</span> <span m='2942240'>of</span> <span m='2942688'>n.</span>
  <span m='2945690'>And</span> <span m='2945780'>let</span> <span
  m='2945880'>me</span> <span m='2946010'>also--</span> <span
  m='2946600'>so</span> <span m='2946840'>the</span> <span
  m='2947060'>sum</span> <span m='2949460'>of</span> <span m='2949890'>f</span>
  <span m='2950110'>of</span> <span m='2950280'>i</span> <span
  m='2951240'>is</span> <span m='2951500'>the</span> <span
  m='2951720'>areas</span> <span m='2953010'>in</span> <span
  m='2953170'>the</span> <span m='2953260'>rectangles.</span> <span
  m='2954500'>That's</span> <span m='2954730'>what</span> <span
  m='2954830'>the</span> <span m='2954890'>sum</span> <span
  m='2955160'>is,</span> <span m='2956300'>and</span> <span m='2956440'>I</span>
  <span m='2956500'>want</span> <span m='2956760'>to</span> <span
  m='2957300'>get</span> <span m='2957480'>bounds</span> <span
  m='2957930'>on</span> <span m='2958070'>this</span> <span
  m='2958330'>sum</span> <span m='2959580'>using</span> <span
  m='2959900'>the</span> <span m='2960000'>integral,</span> <span
  m='2961120'>because</span> <span m='2961310'>integrals</span> <span
  m='2961700'>are</span> <span m='2961830'>easier</span> <span
  m='2962120'>to</span> <span m='2962190'>compute.</span> </p><p><span
  m='2963510'>So</span> <span m='2963690'>let's</span> <span
  m='2964080'>draw</span> <span m='2964450'>the</span> <span
  m='2964540'>function</span> <span m='2966670'>f</span> <span
  m='2966890'>of</span> <span m='2967020'>x</span> <span m='2967890'>from</span>
  <span m='2968070'>1</span> <span m='2968310'>to</span> <span
  m='2968410'>n.</span> <span m='2975720'>All</span> <span
  m='2975860'>right,</span> <span m='2976030'>so</span> <span
  m='2976160'>this</span> <span m='2976470'>is</span> <span m='2977920'>f</span>
  <span m='2978140'>of</span> <span m='2978280'>x</span> <span
  m='2979120'>as</span> <span m='2979290'>a</span> <span
  m='2979330'>function.</span> <span m='2982380'>Now</span> <span
  m='2982630'>I</span> <span m='2982740'>claim</span> <span
  m='2984490'>that</span> <span m='2985080'>the</span> <span
  m='2985180'>sum</span> <span m='2987480'>i</span> <span
  m='2987790'>equals</span> <span m='2988270'>1</span> <span
  m='2988620'>to</span> <span m='2988800'>n</span> <span m='2989630'>of</span>
  <span m='2989830'>f</span> <span m='2990000'>of</span> <span
  m='2990477'>i</span> <span m='2991910'>is</span> <span m='2992200'>at</span>
  <span m='2992370'>least</span> <span m='2993700'>f</span> <span
  m='2993950'>of</span> <span m='2994070'>1</span> <span m='2994970'>plus</span>
  <span m='2995380'>the</span> <span m='2995560'>integral</span> <span
  m='2996040'>from</span> <span m='2996230'>1</span> <span m='2996450'>to</span>
  <span m='2996590'>n,</span> <span m='2997610'>f</span> <span
  m='2997840'>of</span> <span m='2997970'>x,</span> <span m='2998420'>dx.</span>
  </p><p><span m='3001570'>Now,</span> <span m='3001760'>the</span> <span
  m='3001930'>integral</span> <span m='3002960'>from</span> <span
  m='3003240'>1</span> <span m='3003670'>to</span> <span m='3003790'>n</span>
  <span m='3004810'>of</span> <span m='3005030'>f</span> <span
  m='3005260'>of</span> <span m='3005400'>x</span> <span m='3007590'>is</span>
  <span m='3008030'>this</span> <span m='3008220'>stuff,</span> <span
  m='3008530'>the</span> <span m='3008630'>stuff</span> <span
  m='3008950'>under</span> <span m='3009300'>the</span> <span
  m='3009390'>curve.</span> <span m='3010786'>It</span> <span
  m='3011200'>comes</span> <span m='3011490'>down</span> <span
  m='3011790'>here,</span> <span m='3013010'>starts</span> <span
  m='3013590'>at</span> <span m='3013680'>1,</span> <span m='3014680'>and</span>
  <span m='3014840'>it's</span> <span m='3014930'>the</span> <span
  m='3015010'>stuff</span> <span m='3015270'>under</span> <span
  m='3015430'>the</span> <span m='3015530'>curve.</span> <span
  m='3017760'>And</span> <span m='3017790'>what</span> <span
  m='3017900'>I'm</span> <span m='3018010'>saying</span> <span
  m='3018510'>here</span> <span m='3018930'>is</span> <span
  m='3019120'>that</span> <span m='3019220'>if</span> <span
  m='3019300'>you</span> <span m='3019410'>take</span> <span
  m='3019800'>that</span> <span m='3020020'>stuff</span> <span
  m='3020240'>under</span> <span m='3020360'>the</span> <span
  m='3020490'>curve</span> <span m='3020930'>and</span> <span
  m='3021080'>add</span> <span m='3021490'>f</span> <span m='3021690'>of</span>
  <span m='3021800'>1,</span> <span m='3022700'>which</span> <span
  m='3022950'>is</span> <span m='3023120'>this</span> <span
  m='3023350'>piece,</span> <span m='3024600'>that's</span> <span
  m='3025000'>a</span> <span m='3025180'>lower</span> <span
  m='3025570'>bound</span> <span m='3026710'>on</span> <span
  m='3026890'>our</span> <span m='3027030'>sum.</span> <span
  m='3028230'>The</span> <span m='3028290'>sum's</span> <span
  m='3028620'>bigger</span> <span m='3028870'>than</span> <span
  m='3029000'>that.</span> <span m='3031140'>So</span> <span
  m='3031230'>what</span> <span m='3031340'>I'm</span> <span
  m='3031440'>saying</span> <span m='3031840'>is</span> <span
  m='3032020'>the</span> <span m='3032180'>area</span> <span
  m='3032620'>in</span> <span m='3032690'>the</span> <span
  m='3032790'>rectangles</span> <span m='3034620'>is</span> <span
  m='3034820'>at</span> <span m='3034940'>least</span> <span
  m='3035240'>as</span> <span m='3035380'>big</span> <span m='3035750'>as</span>
  <span m='3036470'>the</span> <span m='3036630'>area</span> <span
  m='3036920'>in</span> <span m='3036990'>the</span> <span
  m='3037060'>first</span> <span m='3037380'>rectangle</span> <span
  m='3038440'>plus</span> <span m='3039400'>the</span> <span
  m='3039570'>area</span> <span m='3040010'>under</span> <span
  m='3040260'>the</span> <span m='3040360'>curve.</span> <span
  m='3042250'>Does</span> <span m='3042280'>everybody</span> <span
  m='3042520'>see</span> <span m='3042650'>why</span> <span
  m='3042800'>that</span> <span m='3042990'>is?</span> </p><p><span
  m='3045190'>I'm</span> <span m='3045500'>saying</span> <span
  m='3045810'>the</span> <span m='3045870'>sum</span> <span
  m='3046370'>is</span> <span m='3046500'>the</span> <span
  m='3046630'>area</span> <span m='3046930'>in</span> <span
  m='3047000'>the</span> <span m='3047080'>rectangles,</span> <span
  m='3049110'>right?</span> <span m='3049340'>That's</span> <span
  m='3049530'>pretty</span> <span m='3049720'>clear.</span> <span
  m='3051050'>And</span> <span m='3051300'>that</span> <span
  m='3051630'>is</span> <span m='3052480'>at</span> <span
  m='3052660'>least</span> <span m='3053000'>as</span> <span
  m='3053180'>big</span> <span m='3053540'>as</span> <span
  m='3054530'>the</span> <span m='3054640'>first</span> <span
  m='3055060'>rectangle</span> <span m='3055570'>f</span> <span
  m='3055670'>of</span> <span m='3055790'>1</span> <span m='3056760'>plus</span>
  <span m='3057200'>the</span> <span m='3057290'>stuff</span> <span
  m='3057770'>under</span> <span m='3058070'>the</span> <span
  m='3058170'>curve,</span> <span m='3059530'>which</span> <span
  m='3059610'>is</span> <span m='3059700'>the</span> <span
  m='3059810'>integral,</span> <span m='3060730'>and</span> <span
  m='3060870'>I've</span> <span m='3061030'>left--</span> <span
  m='3061360'>I've</span> <span m='3061560'>chopped</span> <span
  m='3061970'>off</span> <span m='3062310'>these</span> <span
  m='3062550'>guys.</span> <span m='3063040'>That's</span> <span
  m='3063360'>extra.</span> <span m='3064500'>OK?</span> <span
  m='3066410'>Is</span> <span m='3066530'>that</span> <span
  m='3066680'>all</span> <span m='3066780'>right?</span> <span
  m='3067710'>So</span> <span m='3067880'>lower</span> <span
  m='3068110'>bound.</span> <span m='3070200'>Any</span> <span
  m='3070370'>questions</span> <span m='3070820'>on</span> <span
  m='3070920'>the</span> <span m='3070990'>lower</span> <span
  m='3071240'>bound?</span> </p><p><span m='3072510'>This</span> <span
  m='3072680'>is</span> <span m='3072800'>a</span> <span
  m='3072860'>picture</span> <span m='3073230'>proof,</span> <span
  m='3074520'>which</span> <span m='3074750'>we</span> <span
  m='3074910'>always</span> <span m='3075120'>tell</span> <span
  m='3075240'>you</span> <span m='3075350'>not</span> <span
  m='3075620'>to</span> <span m='3075710'>do,</span> <span
  m='3076120'>but</span> <span m='3076460'>we're</span> <span
  m='3076650'>going</span> <span m='3076790'>to</span> <span
  m='3076860'>do</span> <span m='3077110'>one</span> <span
  m='3078100'>here.</span> <span m='3081830'>And,</span> <span
  m='3081920'>of</span> <span m='3081980'>course,</span> <span
  m='3082940'>it</span> <span m='3083240'>totally</span> <span
  m='3083610'>hides</span> <span m='3084810'>why</span> <span
  m='3085180'>did</span> <span m='3085310'>I</span> <span
  m='3085370'>need</span> <span m='3085650'>f</span> <span m='3085830'>is</span>
  <span m='3085970'>increasing,</span> <span m='3086450'>but</span> <span
  m='3086570'>we'll</span> <span m='3086660'>see</span> <span
  m='3086810'>that</span> <span m='3086970'>in</span> <span m='3087030'>a</span>
  <span m='3087070'>minute.</span> <span m='3087410'>The</span> <span
  m='3087510'>proof</span> <span m='3087770'>would</span> <span
  m='3087870'>not</span> <span m='3088090'>work</span> <span
  m='3088360'>unless</span> <span m='3088650'>it</span> <span
  m='3088860'>is</span> <span m='3089040'>increasing</span> <span
  m='3089530'>here.</span> <span m='3093310'>Any</span> <span
  m='3093460'>questions,</span> <span m='3093910'>because</span> <span
  m='3094070'>now</span> <span m='3094200'>going</span> <span
  m='3094320'>I'm</span> <span m='3094340'>going</span> <span
  m='3094360'>to</span> <span m='3094380'>do</span> <span m='3094480'>the</span>
  <span m='3094580'>other</span> <span m='3094750'>bound,</span> <span
  m='3095260'>the</span> <span m='3095360'>other</span> <span
  m='3095510'>side.</span> </p><p><span m='3097390'>I</span> <span
  m='3097680'>also</span> <span m='3097960'>claim--</span> <span
  m='3099170'>this</span> <span m='3099320'>will</span> <span
  m='3099380'>be</span> <span m='3099440'>a</span> <span
  m='3099490'>little</span> <span m='3099670'>trickier</span> <span
  m='3100000'>to</span> <span m='3100080'>see--</span> <span
  m='3101300'>that</span> <span m='3101550'>the</span> <span
  m='3101620'>sum</span> <span m='3104190'>is</span> <span m='3104400'>at</span>
  <span m='3104530'>most</span> <span m='3105720'>f</span> <span
  m='3105950'>of</span> <span m='3106040'>n</span> <span m='3106830'>plus</span>
  <span m='3107400'>the</span> <span m='3107540'>integral</span> <span
  m='3108460'>from</span> <span m='3108630'>1</span> <span m='3108810'>to</span>
  <span m='3108890'>n.</span> <span m='3113420'>So</span> <span
  m='3113570'>this</span> <span m='3113820'>is</span> <span
  m='3113950'>the</span> <span m='3114080'>lower</span> <span
  m='3114420'>bound</span> <span m='3115090'>add</span> <span
  m='3115310'>in</span> <span m='3115410'>f</span> <span m='3115460'>of</span>
  <span m='3115510'>1,</span> <span m='3116110'>the</span> <span
  m='3116240'>upper</span> <span m='3116410'>bound</span> <span
  m='3116770'>just</span> <span m='3116970'>add</span> <span
  m='3117100'>in</span> <span m='3117180'>f</span> <span m='3117260'>of</span>
  <span m='3117340'>n.</span> <span m='3117810'>So</span> <span
  m='3117905'>let's</span> <span m='3118000'>see</span> <span
  m='3118130'>why</span> <span m='3118320'>that's</span> <span
  m='3118540'>true.</span> <span m='3120440'>Now,</span> <span
  m='3121610'>to</span> <span m='3121740'>see</span> <span
  m='3122040'>that,</span> <span m='3122500'>this</span> <span
  m='3122700'>is--</span> <span m='3122890'>I'm</span> <span
  m='3123020'>not</span> <span m='3123140'>going</span> <span
  m='3123270'>to</span> <span m='3123470'>be</span> <span
  m='3123572'>able</span> <span m='3123675'>to</span> <span
  m='3123777'>draw</span> <span m='3123880'>it.</span> <span
  m='3125400'>I</span> <span m='3125510'>want</span> <span
  m='3125760'>you</span> <span m='3125840'>to</span> <span
  m='3125940'>imagine</span> <span m='3126480'>taking</span> <span
  m='3126910'>this</span> <span m='3127450'>curve</span> <span
  m='3127910'>and</span> <span m='3127980'>the</span> <span
  m='3128090'>area</span> <span m='3128420'>under</span> <span
  m='3128740'>it,</span> <span m='3129950'>down</span> <span
  m='3130210'>to</span> <span m='3130280'>here,</span> <span
  m='3131990'>and</span> <span m='3132170'>sliding</span> <span
  m='3132790'>it</span> <span m='3132930'>left</span> <span
  m='3133360'>one</span> <span m='3133640'>unit.</span> </p><p><span
  m='3136480'>sliding</span> <span m='3137170'>it</span> <span
  m='3137300'>left</span> <span m='3138950'>to</span> <span
  m='3139100'>here,</span> <span m='3140590'>sliding</span> <span
  m='3141130'>it</span> <span m='3141250'>left</span> <span
  m='3141560'>one</span> <span m='3141780'>unit</span> <span
  m='3143180'>over</span> <span m='3143390'>to</span> <span
  m='3143470'>here.</span> <span m='3146950'>Now,</span> <span
  m='3147140'>when</span> <span m='3147230'>I</span> <span
  m='3147350'>slide</span> <span m='3147850'>it</span> <span
  m='3147970'>left</span> <span m='3148820'>one</span> <span
  m='3149120'>unit,</span> <span m='3149480'>did</span> <span
  m='3149840'>the</span> <span m='3150150'>area</span> <span
  m='3150570'>under</span> <span m='3150890'>it</span> <span
  m='3150980'>change?</span> <span m='3153750'>No.</span> <span
  m='3154280'>It's</span> <span m='3154390'>the</span> <span
  m='3154450'>same</span> <span m='3154730'>area</span> <span
  m='3155080'>under</span> <span m='3155360'>it,</span> <span
  m='3156360'>just</span> <span m='3156650'>where</span> <span
  m='3156860'>it</span> <span m='3156950'>sits</span> <span
  m='3157190'>on</span> <span m='3157270'>the</span> <span
  m='3157350'>picture</span> <span m='3157760'>is</span> <span
  m='3157910'>now</span> <span m='3158920'>out</span> <span
  m='3159355'>here.</span> <span m='3162950'>It's</span> <span
  m='3163140'>this</span> <span m='3163410'>area</span> <span
  m='3163760'>under</span> <span m='3163980'>this</span> <span
  m='3164190'>guy,</span> <span m='3164400'>but</span> <span
  m='3164530'>it's</span> <span m='3164640'>the</span> <span
  m='3164710'>same</span> <span m='3165010'>thing,</span> <span
  m='3165320'>its</span> <span m='3165340'>the</span> <span
  m='3165410'>same</span> <span m='3165630'>integral.</span> <span
  m='3167300'>And</span> <span m='3167530'>you</span> <span
  m='3167600'>can</span> <span m='3167750'>see</span> <span
  m='3168090'>that</span> <span m='3168230'>it's</span> <span
  m='3168690'>more</span> <span m='3169230'>than</span> <span
  m='3170390'>what's</span> <span m='3170680'>in</span> <span
  m='3170770'>these</span> <span m='3170960'>rectangles,</span> <span
  m='3171510'>because</span> <span m='3171670'>I</span> <span
  m='3171740'>got</span> <span m='3171950'>all</span> <span
  m='3172040'>this</span> <span m='3172200'>stuff.</span> </p><p><span
  m='3175110'>And,</span> <span m='3175460'>of</span> <span
  m='3175530'>course,</span> <span m='3175940'>I</span> <span
  m='3176020'>didn't</span> <span m='3176200'>even</span> <span
  m='3176360'>include</span> <span m='3176770'>this,</span> <span
  m='3177050'>so</span> <span m='3177150'>now</span> <span m='3177310'>I</span>
  <span m='3177420'>add</span> <span m='3177580'>the</span> <span
  m='3177770'>f</span> <span m='3178237'>n.</span> <span m='3181040'>So</span>
  <span m='3181190'>if</span> <span m='3181270'>I</span> <span
  m='3181350'>take</span> <span m='3181610'>the</span> <span
  m='3181770'>area</span> <span m='3182320'>under</span> <span
  m='3182580'>the</span> <span m='3182680'>curve,</span> <span
  m='3183230'>which</span> <span m='3183280'>is</span> <span
  m='3183370'>the</span> <span m='3183510'>integral,</span> <span
  m='3184640'>shift</span> <span m='3184885'>it</span> <span
  m='3185130'>left</span> <span m='3185510'>one,</span> <span
  m='3185890'>so</span> <span m='3185965'>it</span> <span
  m='3186040'>only</span> <span m='3186190'>goes</span> <span
  m='3186340'>up</span> <span m='3186450'>to</span> <span
  m='3186520'>here</span> <span m='3186780'>now,</span> <span
  m='3187430'>and</span> <span m='3187600'>then</span> <span
  m='3187770'>add</span> <span m='3188090'>in</span> <span
  m='3188260'>this</span> <span m='3188440'>rectangle,</span> <span
  m='3189950'>that</span> <span m='3190240'>dominates</span> <span
  m='3191100'>the</span> <span m='3191240'>area</span> <span
  m='3191820'>in</span> <span m='3191940'>the</span> <span
  m='3192020'>rectangles.</span> <span m='3194590'>Bigger</span> <span
  m='3194850'>than.</span> <span m='3198890'>Do</span> <span
  m='3199090'>you</span> <span m='3199170'>see</span> <span
  m='3199340'>that?</span> <span m='3203400'>I</span> <span
  m='3203520'>could</span> <span m='3203660'>do</span> <span
  m='3203760'>a</span> <span m='3203830'>lot</span> <span m='3204030'>of</span>
  <span m='3204090'>equations</span> <span m='3204600'>on</span> <span
  m='3204660'>the</span> <span m='3204730'>board</span> <span
  m='3205020'>but,</span> <span m='3205140'>for</span> <span
  m='3205250'>sure,</span> <span m='3205770'>that</span> <span
  m='3205950'>would</span> <span m='3206060'>be</span> <span
  m='3206210'>hopeless</span> <span m='3206720'>to</span> <span
  m='3207170'>follow.</span> <span m='3209550'>Any</span> <span
  m='3209630'>questions</span> <span m='3210170'>about</span> <span
  m='3210430'>this?</span> <span m='3211160'>Yeah.</span> </p><p><span
  m='3211896'>AUDIENCE:</span> <span m='3212352'>I</span> <span
  m='3212808'>guess</span> <span m='3213264'>I</span> <span
  m='3213492'>understand</span> <span m='3213530'>the</span> <span
  m='3213606'>lower</span> <span m='3213682'>amounts</span> <span
  m='3213720'>because</span> <span m='3214632'>we're</span> <span
  m='3215088'>cutting</span> <span m='3215544'>off</span> <span
  m='3215696'>the</span> <span m='3215848'>triangles.</span> </p><p><span
  m='3216460'>PROFESSOR: Yeah.</span> </p><p><span m='3218360'>But</span> <span
  m='3220250'>is</span> <span m='3220720'>there--</span> <span
  m='3221190'>is</span> <span m='3221660'>it</span> <span m='3222160'>a</span>
  <span m='3222285'>lot</span> <span m='3222410'>of</span> <span
  m='3222535'>hand</span> <span m='3222660'>waving,</span> <span
  m='3222760'>or</span> <span m='3222860'>am</span> <span m='3222960'>I</span>
  <span m='3223060'>just</span> <span m='3223160'>missing</span> <span
  m='3223660'>something,</span> <span m='3224160'>that</span> <span
  m='3224326'>it's</span> <span m='3224493'>always</span> <span
  m='3224660'>going</span> <span m='3224910'>to</span> <span
  m='3225160'>be</span> <span m='3225660'>the</span> <span m='3226160'>f</span>
  <span m='3226326'>of</span> <span m='3226493'>n</span> <span
  m='3226660'>is</span> <span m='3227150'>what</span> <span
  m='3227395'>we--</span> </p><p><span m='3228130'>PROFESSOR: Yeah.</span> <span
  m='3228670'>There's</span> <span m='3228820'>a</span> <span
  m='3228850'>little</span> <span m='3229070'>hand</span> <span
  m='3229290'>waving</span> <span m='3229530'>going</span> <span
  m='3229790'>on,</span> <span m='3230750'>but</span> <span m='3230870'>I</span>
  <span m='3230940'>do</span> <span m='3231140'>believe</span> <span
  m='3231420'>it</span> <span m='3231890'>is</span> <span
  m='3231970'>true.</span> <span m='3233090'>With</span> <span
  m='3233340'>equations</span> <span m='3233870'>you</span> <span
  m='3233930'>can</span> <span m='3234020'>make</span> <span
  m='3234170'>it</span> <span m='3234230'>precise.</span> <span
  m='3234700'>Let's</span> <span m='3234920'>look</span> <span
  m='3235090'>at</span> <span m='3235200'>it</span> <span
  m='3235280'>again,</span> <span m='3236320'>do</span> <span
  m='3236450'>this</span> <span m='3236650'>one</span> <span
  m='3236810'>more</span> <span m='3237000'>time.</span> </p><p><span
  m='3237876'>AUDIENCE:</span> <span m='3238314'>[INAUDIBLE]</span> </p><p><span
  m='3239980'>PROFESSOR: Yeah,</span> <span m='3240160'>I'm</span> <span
  m='3240300'>waving</span> <span m='3240550'>hands</span> <span
  m='3240790'>a</span> <span m='3240840'>little</span> <span
  m='3241050'>bit,</span> <span m='3241440'>but</span> <span
  m='3241560'>it</span> <span m='3241690'>also--</span> <span
  m='3242280'>hopefully</span> <span m='3242730'>the</span> <span
  m='3242860'>intuition</span> <span m='3243350'>comes</span> <span
  m='3243580'>across,</span> <span m='3244940'>because</span> <span
  m='3247000'>when</span> <span m='3247170'>I</span> <span
  m='3247270'>shift</span> <span m='3247720'>left</span> <span
  m='3248610'>by</span> <span m='3248780'>one,</span> <span
  m='3250220'>this</span> <span m='3250430'>point</span> <span
  m='3250730'>becomes</span> <span m='3251200'>this</span> <span
  m='3251420'>point,</span> <span m='3252360'>and</span> <span
  m='3252510'>that</span> <span m='3252700'>point</span> <span
  m='3252920'>becomes</span> <span m='3253230'>that</span> <span
  m='3253450'>point,</span> <span m='3254210'>and</span> <span
  m='3254390'>I'm</span> <span m='3254510'>catching</span> <span
  m='3255890'>sort</span> <span m='3256300'>of</span> <span
  m='3256360'>the</span> <span m='3256420'>cusp</span> <span
  m='3256890'>of</span> <span m='3257000'>these</span> <span
  m='3257170'>rectangles,</span> <span m='3258370'>and</span> <span
  m='3258530'>now</span> <span m='3258740'>I</span> <span
  m='3258830'>take</span> <span m='3259630'>this</span> <span
  m='3259940'>curve</span> <span m='3261160'>here,</span> <span
  m='3264300'>shifting</span> <span m='3264750'>the</span> <span
  m='3264830'>whole</span> <span m='3265080'>curve</span> <span
  m='3265400'>left</span> <span m='3265880'>one</span> <span
  m='3266090'>unit,</span> <span m='3268120'>and</span> <span
  m='3268250'>the</span> <span m='3268340'>area</span> <span
  m='3268620'>doesn't</span> <span m='3268860'>change.</span> <span
  m='3270430'>It</span> <span m='3270640'>would</span> <span
  m='3270730'>be</span> <span m='3270800'>equivalent</span> <span
  m='3271300'>of</span> <span m='3271440'>taking</span> <span
  m='3271800'>the</span> <span m='3271960'>integral</span> <span
  m='3272510'>from</span> <span m='3272700'>0</span> <span m='3273010'>to</span>
  <span m='3273090'>n</span> <span m='3273290'>minus</span> <span
  m='3273650'>1.</span> <span m='3275170'>You</span> <span
  m='3275300'>notice</span> <span m='3275390'>what</span> <span
  m='3275570'>I'm</span> <span m='3275670'>doing--</span> <span
  m='3275950'>of</span> <span m='3276650'>f</span> <span m='3276900'>of</span>
  <span m='3277040'>x</span> <span m='3277350'>plus</span> <span
  m='3277710'>1.</span> <span m='3279360'>There's</span> <span
  m='3279450'>another</span> <span m='3279660'>way</span> <span
  m='3279760'>to</span> <span m='3279830'>look</span> <span
  m='3280020'>at</span> <span m='3280110'>it</span> <span
  m='3280200'>mathematically,</span> <span m='3280850'>maybe--</span> <span
  m='3281270'>probably</span> <span m='3281640'>the</span> <span
  m='3281700'>formal</span> <span m='3282070'>way</span> <span
  m='3282170'>to</span> <span m='3282260'>do</span> <span
  m='3282460'>it--</span> <span m='3283410'>but</span> <span
  m='3283630'>the</span> <span m='3283720'>idea</span> <span
  m='3284010'>is</span> <span m='3284090'>that</span> <span
  m='3284220'>this</span> <span m='3284430'>now</span> <span
  m='3284790'>contains</span> <span m='3286060'>all</span> <span
  m='3286460'>these</span> <span m='3286740'>first</span> <span
  m='3287070'>n</span> <span m='3287210'>minus</span> <span m='3287500'>1</span>
  <span m='3287660'>rectangles,</span> <span m='3288580'>are</span> <span
  m='3288750'>contained</span> <span m='3289250'>underneath</span> <span
  m='3289680'>it.</span> <span m='3291180'>And</span> <span
  m='3291230'>then</span> <span m='3291370'>I</span> <span
  m='3291450'>just</span> <span m='3291700'>add</span> <span
  m='3291930'>this</span> <span m='3292160'>in,</span> <span
  m='3294170'>and</span> <span m='3294880'>I'm</span> <span
  m='3295060'>good</span> <span m='3295190'>to</span> <span
  m='3295270'>go.</span> <span m='3295580'>I've</span> <span
  m='3295730'>contained</span> <span m='3296070'>all</span> <span
  m='3296210'>the</span> <span m='3296300'>rectangles</span> <span
  m='3296930'>now</span> <span m='3297370'>for</span> <span
  m='3297516'>the</span> <span m='3297663'>upper</span> <span
  m='3297810'>bounds.</span> <span m='3300690'>All</span> <span
  m='3300750'>right,</span> <span m='3300900'>mathematically</span> <span
  m='3301500'>what</span> <span m='3301650'>this</span> <span
  m='3302035'>is,</span> <span m='3302227'>this</span> <span
  m='3302420'>curve</span> <span m='3302800'>is</span> <span
  m='3303770'>0</span> <span m='3304180'>to</span> <span m='3304270'>n</span>
  <span m='3304440'>minus</span> <span m='3304790'>1,</span> <span
  m='3306270'>fx</span> <span m='3306750'>plus</span> <span
  m='3306990'>1,</span> <span m='3308100'>which</span> <span
  m='3308440'>is</span> <span m='3308590'>the</span> <span
  m='3308670'>same</span> <span m='3308980'>thing</span> <span
  m='3309260'>as</span> <span m='3310000'>what</span> <span
  m='3310170'>that</span> <span m='3310350'>is.</span> <span
  m='3313810'>Any</span> <span m='3314360'>questions</span> <span
  m='3316380'>for</span> <span m='3316510'>that?</span> </p><p><span
  m='3319180'>But</span> <span m='3319280'>now</span> <span m='3319460'>I</span>
  <span m='3319560'>have</span> <span m='3319910'>good</span> <span
  m='3320080'>bounds</span> <span m='3320660'>on</span> <span
  m='3320930'>the</span> <span m='3320990'>sum.</span> <span
  m='3323160'>We</span> <span m='3323260'>know</span> <span
  m='3323490'>that</span> <span m='3323670'>the</span> <span
  m='3323740'>sum</span> <span m='3324190'>is</span> <span m='3324500'>at</span>
  <span m='3324620'>least</span> <span m='3325040'>this</span> <span
  m='3325990'>and</span> <span m='3326130'>at</span> <span
  m='3326210'>most</span> <span m='3326510'>that,</span> <span
  m='3328100'>and</span> <span m='3328300'>those</span> <span
  m='3328620'>two</span> <span m='3329830'>bounds</span> <span
  m='3330320'>only</span> <span m='3330540'>differ</span> <span
  m='3330860'>by</span> <span m='3331070'>a</span> <span
  m='3331120'>single</span> <span m='3331450'>term</span> <span
  m='3333310'>in</span> <span m='3333460'>the</span> <span
  m='3333530'>sum,</span> <span m='3333990'>so</span> <span
  m='3334170'>they're</span> <span m='3334310'>very</span> <span
  m='3334610'>close.</span> <span m='3336380'>These</span> <span
  m='3336600'>actually</span> <span m='3336910'>are</span> <span
  m='3336950'>good</span> <span m='3337120'>formulas</span> <span
  m='3337540'>to</span> <span m='3337630'>write</span> <span
  m='3337830'>down</span> <span m='3338040'>for</span> <span
  m='3338130'>your</span> <span m='3338220'>crib</span> <span
  m='3338450'>sheet.</span> <span m='3338810'>That</span> <span
  m='3339050'>is</span> <span m='3339200'>worth</span> <span
  m='3339400'>doing</span> <span m='3341850'>on</span> <span
  m='3342040'>the</span> <span m='3342110'>test,</span> <span
  m='3345100'>and</span> <span m='3345280'>we'll</span> <span
  m='3345570'>use</span> <span m='3345830'>them</span> <span
  m='3347270'>more</span> <span m='3348350'>today,</span> <span
  m='3348880'>and</span> <span m='3349080'>we'll</span> <span
  m='3349170'>also</span> <span m='3349450'>use</span> <span
  m='3349650'>them</span> <span m='3350670'>on</span> <span
  m='3350870'>Thursday.</span> </p><p><span m='3356730'>So</span> <span
  m='3356870'>now</span> <span m='3357170'>we</span> <span
  m='3357280'>can</span> <span m='3357450'>actually</span> <span
  m='3358030'>get</span> <span m='3358280'>close</span> <span
  m='3358770'>bounds</span> <span m='3359400'>on</span> <span
  m='3359670'>the</span> <span m='3359740'>sum</span> <span
  m='3360030'>of</span> <span m='3360090'>the</span> <span
  m='3360150'>square</span> <span m='3360500'>roots.</span> <span
  m='3362850'>So</span> <span m='3362960'>let's</span> <span
  m='3363140'>see</span> <span m='3363290'>how</span> <span
  m='3363420'>this</span> <span m='3363620'>works</span> <span
  m='3364030'>for</span> <span m='3366200'>f</span> <span m='3366365'>of</span>
  <span m='3366530'>i</span> <span m='3367120'>equal</span> <span
  m='3367480'>to</span> <span m='3367520'>the</span> <span
  m='3367560'>square</span> <span m='3367820'>root</span> <span
  m='3367920'>of</span> <span m='3368060'>i,</span> <span
  m='3368890'>which</span> <span m='3369160'>is</span> <span
  m='3369340'>increasing.</span> <span m='3371120'>So</span> <span
  m='3371300'>I</span> <span m='3371350'>compute</span> <span
  m='3371720'>the</span> <span m='3371850'>integral</span> <span
  m='3372210'>from</span> <span m='3372400'>1</span> <span m='3372630'>to</span>
  <span m='3373150'>n</span> <span m='3373620'>of</span> <span
  m='3373900'>square</span> <span m='3374350'>root</span> <span
  m='3374580'>of</span> <span m='3374830'>x</span> <span m='3375307'>dx,</span>
  <span m='3377470'>and</span> <span m='3377600'>that's</span> <span
  m='3377800'>just</span> <span m='3378190'>x</span> <span m='3378430'>to</span>
  <span m='3378510'>the</span> <span m='3378600'>3/2</span> <span
  m='3379620'>over</span> <span m='3380580'>3/2,</span> <span
  m='3381830'>evaluated</span> <span m='3382590'>at</span> <span
  m='3382750'>n</span> <span m='3382920'>and</span> <span m='3383090'>1,</span>
  <span m='3384960'>and</span> <span m='3385110'>that</span> <span
  m='3385340'>just</span> <span m='3385445'>equals</span> <span
  m='3385550'>2/3</span> <span m='3388260'>n</span> <span m='3388580'>to</span>
  <span m='3388650'>the</span> <span m='3388720'>3/2</span> <span
  m='3389820'>minus</span> <span m='3390185'>1.</span> </p><p><span
  m='3392660'>And</span> <span m='3392830'>now</span> <span m='3393060'>I</span>
  <span m='3393140'>can</span> <span m='3393290'>compute</span> <span
  m='3393620'>the</span> <span m='3393690'>bounds</span> <span
  m='3394250'>on</span> <span m='3395080'>the</span> <span
  m='3395200'>sum</span> <span m='3395820'>of</span> <span
  m='3395950'>the</span> <span m='3396010'>first</span> <span
  m='3396370'>n</span> <span m='3396530'>square</span> <span
  m='3396820'>roots.</span> <span m='3399920'>So</span> <span
  m='3400070'>I</span> <span m='3400150'>know</span> <span
  m='3400490'>that</span> <span m='3401860'>square</span> <span
  m='3402290'>root</span> <span m='3403040'>i</span> <span
  m='3403390'>equals</span> <span m='3403740'>1</span> <span
  m='3404000'>to</span> <span m='3404180'>n--</span> <span
  m='3407600'>well,</span> <span m='3407750'>the</span> <span
  m='3407890'>upper</span> <span m='3408100'>bound</span> <span
  m='3408560'>is</span> <span m='3409000'>f</span> <span m='3409473'>n</span>
  <span m='3410420'>plus</span> <span m='3411060'>the</span> <span
  m='3411210'>integral,</span> <span m='3417000'>and</span> <span
  m='3417150'>the</span> <span m='3417210'>lower</span> <span
  m='3417560'>bound</span> <span m='3418250'>is</span> <span
  m='3418490'>f</span> <span m='3418710'>of</span> <span m='3418810'>1</span>
  <span m='3420540'>plus</span> <span m='3421620'>the</span> <span
  m='3421770'>integral.</span> <span m='3427590'>What</span> <span
  m='3427850'>is</span> <span m='3428710'>f</span> <span m='3428930'>of</span>
  <span m='3429020'>n?</span> <span m='3432280'>That's</span> <span
  m='3432510'>the</span> <span m='3432580'>square</span> <span
  m='3432850'>root</span> <span m='3432970'>of</span> <span
  m='3433080'>n.</span> <span m='3435150'>What</span> <span
  m='3435390'>is</span> <span m='3435520'>f</span> <span m='3435710'>of</span>
  <span m='3435820'>1?</span> <span m='3438330'>The</span> <span
  m='3438760'>square</span> <span m='3439030'>root</span> <span
  m='3439130'>of</span> <span m='3439200'>1,</span> <span
  m='3439510'>which</span> <span m='3439690'>is</span> <span
  m='3439800'>1.</span> <span m='3441860'>So</span> <span
  m='3442300'>I'll</span> <span m='3442400'>plug</span> <span
  m='3443590'>that</span> <span m='3443880'>in</span> <span
  m='3444060'>here.</span> <span m='3444310'>I</span> <span
  m='3444390'>get</span> <span m='3445200'>2/3</span> <span m='3446890'>n</span>
  <span m='3447140'>to</span> <span m='3447210'>the</span> <span
  m='3447290'>3/2</span> <span m='3449040'>plus</span> <span
  m='3449410'>1</span> <span m='3449660'>minus</span> <span
  m='3450080'>2/3</span> <span m='3450770'>is</span> <span
  m='3450880'>plus</span> <span m='3451170'>1/3,</span> <span
  m='3454440'>and</span> <span m='3454690'>here</span> <span
  m='3455060'>I</span> <span m='3455150'>get</span> <span m='3456050'>2/3</span>
  <span m='3457680'>n</span> <span m='3457940'>to</span> <span
  m='3458000'>the</span> <span m='3458060'>3/2</span> <span
  m='3460130'>plus</span> <span m='3460560'>the</span> <span
  m='3460640'>square</span> <span m='3460900'>root</span> <span
  m='3461020'>of</span> <span m='3461150'>n</span> <span
  m='3461830'>minus</span> <span m='3462360'>2/3.</span> <span
  m='3466210'>So</span> <span m='3466920'>now</span> <span m='3467280'>I</span>
  <span m='3467400'>have</span> <span m='3467630'>pretty</span> <span
  m='3467890'>good</span> <span m='3468110'>bounds</span> <span
  m='3468710'>on</span> <span m='3468830'>the</span> <span
  m='3468900'>sum</span> <span m='3469170'>of</span> <span
  m='3469240'>the</span> <span m='3469300'>first</span> <span
  m='3469670'>n</span> <span m='3469840'>square</span> <span
  m='3470080'>roots</span> <span m='3470870'>using</span> <span
  m='3471190'>this</span> <span m='3471370'>method.</span> </p><p><span
  m='3474320'>So</span> <span m='3474540'>for</span> <span
  m='3474680'>example,</span> <span m='3476070'>take</span> <span
  m='3476660'>n</span> <span m='3476830'>equals</span> <span
  m='3477070'>100.</span> <span m='3483180'>This</span> <span
  m='3483520'>number</span> <span m='3483940'>evaluates</span> <span
  m='3484540'>to</span> <span m='3484650'>667.</span> <span
  m='3487270'>This</span> <span m='3487530'>number</span> <span
  m='3487830'>evaluates</span> <span m='3488420'>to</span> <span
  m='3488540'>676,</span> <span m='3491110'>and</span> <span
  m='3491380'>the</span> <span m='3491440'>difference</span> <span
  m='3492130'>is</span> <span m='3492430'>9,</span> <span
  m='3492950'>which</span> <span m='3493210'>is</span> <span
  m='3493360'>the</span> <span m='3493440'>square</span> <span
  m='3493720'>root</span> <span m='3493820'>of</span> <span
  m='3493880'>100</span> <span m='3494180'>minus</span> <span
  m='3494480'>1.</span> <span m='3496290'>This</span> <span
  m='3496570'>is</span> <span m='3497780'>the</span> <span
  m='3497840'>square</span> <span m='3498060'>root</span> <span
  m='3498160'>of</span> <span m='3498250'>n,</span> <span
  m='3499210'>this</span> <span m='3499450'>is</span> <span
  m='3499570'>1,</span> <span m='3500010'>so</span> <span m='3500140'>the</span>
  <span m='3500240'>gap</span> <span m='3500590'>here,</span> <span
  m='3500880'>square</span> <span m='3501050'>root</span> <span
  m='3501220'>of</span> <span m='3501320'>n</span> <span
  m='3501460'>minus</span> <span m='3501800'>1,</span> <span
  m='3503150'>and</span> <span m='3503350'>n</span> <span
  m='3503480'>equals</span> <span m='3503700'>100.</span> <span
  m='3504210'>Square</span> <span m='3504340'>root</span> <span
  m='3504470'>of</span> <span m='3504530'>100</span> <span
  m='3504800'>minus</span> <span m='3505080'>1</span> <span
  m='3505230'>is</span> <span m='3505360'>9,</span> <span m='3505830'>so</span>
  <span m='3506020'>I</span> <span m='3506110'>shouldn't</span> <span
  m='3506370'>be</span> <span m='3506430'>surprised</span> <span
  m='3506840'>my</span> <span m='3506950'>gap</span> <span
  m='3507340'>here</span> <span m='3507470'>is</span> <span
  m='3507590'>nine.</span> </p><p><span m='3508670'>So</span> <span
  m='3508820'>I</span> <span m='3508880'>didn't</span> <span
  m='3509060'>get</span> <span m='3509170'>exactly</span> <span
  m='3509650'>the</span> <span m='3509760'>right</span> <span
  m='3509970'>answer,</span> <span m='3510350'>but</span> <span
  m='3510510'>I'm</span> <span m='3510910'>pretty</span> <span
  m='3511140'>close</span> <span m='3512560'>here.</span> <span
  m='3516030'>Now,</span> <span m='3517420'>as</span> <span m='3517750'>n</span>
  <span m='3518030'>grows,</span> <span m='3521200'>what</span> <span
  m='3521400'>happens</span> <span m='3521770'>to</span> <span
  m='3521860'>the</span> <span m='3521960'>gap</span> <span
  m='3522370'>between</span> <span m='3523210'>the</span> <span
  m='3523480'>upper</span> <span m='3523650'>bound</span> <span
  m='3524670'>and</span> <span m='3524830'>the</span> <span
  m='3524900'>lower</span> <span m='3525160'>bound?</span> <span
  m='3527820'>What</span> <span m='3527940'>does</span> <span
  m='3528040'>it</span> <span m='3528120'>do?</span> <span m='3529370'>It</span>
  <span m='3529500'>gets</span> <span m='3529700'>bigger.</span> <span
  m='3531000'>So</span> <span m='3531460'>my</span> <span m='3531610'>gap</span>
  <span m='3531960'>gets</span> <span m='3532170'>bigger.</span> <span
  m='3533010'>That's</span> <span m='3533220'>not</span> <span
  m='3533410'>so</span> <span m='3533600'>nice.</span> <span
  m='3534490'>Doesn't</span> <span m='3534770'>always</span> <span
  m='3535000'>stay</span> <span m='3535245'>9</span> <span
  m='3535490'>forever,</span> <span m='3537320'>but</span> <span
  m='3538980'>somehow</span> <span m='3539610'>though</span> <span
  m='3540440'>this</span> <span m='3540660'>is</span> <span
  m='3540750'>still</span> <span m='3541000'>pretty</span> <span
  m='3541240'>good,</span> <span m='3541590'>because</span> <span
  m='3543890'>the</span> <span m='3544020'>gap</span> <span
  m='3544350'>grows</span> <span m='3544890'>but</span> <span
  m='3544990'>the</span> <span m='3545080'>gap</span> <span
  m='3545360'>only</span> <span m='3545560'>grows</span> <span
  m='3546180'>as</span> <span m='3547130'>square</span> <span
  m='3547440'>root</span> <span m='3547560'>of</span> <span
  m='3547650'>n,</span> <span m='3549420'>where</span> <span
  m='3550150'>the</span> <span m='3550370'>answer--</span> <span
  m='3550800'>the</span> <span m='3550870'>bounds--</span> <span
  m='3551135'>are</span> <span m='3551400'>growing</span> <span
  m='3551850'>as</span> <span m='3552160'>n</span> <span m='3552420'>to</span>
  <span m='3552480'>the</span> <span m='3552550'>3/2.</span> </p><p><span
  m='3554670'>In</span> <span m='3554820'>other</span> <span
  m='3554990'>words,</span> <span m='3555390'>my</span> <span
  m='3555560'>error</span> <span m='3557400'>is</span> <span
  m='3557590'>somewhere</span> <span m='3558000'>around</span> <span
  m='3558350'>here,</span> <span m='3559500'>and</span> <span
  m='3559570'>that</span> <span m='3559760'>gets</span> <span
  m='3559980'>smaller</span> <span m='3561090'>compared</span> <span
  m='3561660'>to</span> <span m='3561790'>my</span> <span
  m='3562020'>answer,</span> <span m='3563060'>which</span> <span
  m='3563150'>is</span> <span m='3563240'>somewhere</span> <span
  m='3563610'>around</span> <span m='3563900'>there.</span> <span
  m='3565970'>And</span> <span m='3566060'>there's</span> <span
  m='3566210'>a</span> <span m='3566270'>special</span> <span
  m='3566770'>notation</span> <span m='3567450'>that</span> <span
  m='3567560'>people</span> <span m='3567860'>use.</span> <span
  m='3570010'>In</span> <span m='3570460'>fact,</span> <span
  m='3571810'>let's</span> <span m='3572010'>write</span> <span
  m='3572240'>that</span> <span m='3572400'>down</span> <span
  m='3572610'>and</span> <span m='3572700'>then</span> <span
  m='3572830'>do</span> <span m='3572930'>the</span> <span
  m='3573010'>notation.</span> </p><p><span m='3585570'>Another</span> <span
  m='3585830'>way</span> <span m='3585990'>of</span> <span
  m='3586110'>writing</span> <span m='3586510'>this</span> <span
  m='3586760'>is</span> <span m='3588180'>that</span> <span
  m='3588360'>the</span> <span m='3590910'>sum</span> <span m='3592835'>i</span>
  <span m='3593240'>equals</span> <span m='3593610'>1</span> <span
  m='3593950'>to</span> <span m='3594110'>n</span> <span m='3594440'>of</span>
  <span m='3594500'>square</span> <span m='3594740'>root</span> <span
  m='3594850'>of</span> <span m='3595030'>i.</span> <span m='3596820'>The</span>
  <span m='3597000'>leading</span> <span m='3597400'>term</span> <span
  m='3597850'>here</span> <span m='3598210'>is</span> <span
  m='3598390'>2/3</span> <span m='3598940'>n</span> <span m='3599080'>to</span>
  <span m='3599170'>the</span> <span m='3599230'>3/2,</span> <span
  m='3602670'>and</span> <span m='3602840'>then</span> <span
  m='3603000'>there's</span> <span m='3603230'>some</span> <span
  m='3603660'>error</span> <span m='3604010'>term--</span> <span
  m='3604450'>delta</span> <span m='3604770'>term</span> <span
  m='3605120'>here.</span> <span m='3605630'>We'll</span> <span
  m='3606060'>call</span> <span m='3606360'>that</span> <span
  m='3606990'>delta</span> <span m='3607370'>n,</span> <span
  m='3609020'>and</span> <span m='3609330'>we</span> <span
  m='3609430'>know</span> <span m='3609830'>that</span> <span
  m='3613470'>the</span> <span m='3613660'>error</span> <span
  m='3613970'>term</span> <span m='3614430'>is</span> <span
  m='3614540'>at</span> <span m='3614640'>least</span> <span
  m='3614950'>1/3</span> <span m='3617640'>and,</span> <span
  m='3617880'>at</span> <span m='3617980'>most,</span> <span
  m='3619190'>the</span> <span m='3619220'>square</span> <span
  m='3619340'>root</span> <span m='3619460'>of</span> <span m='3619600'>n</span>
  <span m='3619740'>minus</span> <span m='3620120'>2/3.</span> <span
  m='3625100'>So</span> <span m='3625330'>this</span> <span
  m='3625620'>delta</span> <span m='3626040'>term</span> <span
  m='3627220'>is</span> <span m='3627430'>bound</span> <span
  m='3627810'>by</span> <span m='3627950'>the</span> <span
  m='3628000'>square</span> <span m='3628280'>root</span> <span
  m='3628350'>of</span> <span m='3628390'>n.</span> <span
  m='3629090'>That's</span> <span m='3629330'>getting</span> <span
  m='3629610'>bigger</span> <span m='3629920'>as</span> <span
  m='3630040'>n</span> <span m='3630160'>gets</span> <span
  m='3630370'>big,</span> <span m='3631220'>but</span> <span
  m='3632480'>this</span> <span m='3632770'>value</span> <span
  m='3633210'>compared</span> <span m='3633720'>to</span> <span
  m='3633780'>your</span> <span m='3633940'>answer</span> <span
  m='3634790'>is</span> <span m='3634930'>getting</span> <span
  m='3635160'>small.</span> <span m='3636920'>That's</span> <span
  m='3637260'>nice,</span> <span m='3637990'>and</span> <span
  m='3638160'>so</span> <span m='3638290'>the</span> <span
  m='3638380'>way</span> <span m='3638740'>that</span> <span
  m='3638920'>gets</span> <span m='3639130'>represented</span> <span
  m='3640530'>is</span> <span m='3641330'>as</span> <span
  m='3641510'>follows.</span> </p><p><span m='3642050'>We</span> <span
  m='3642060'>would</span> <span m='3642200'>say--</span> <span
  m='3642690'>it's</span> <span m='3642780'>using</span> <span
  m='3643040'>that</span> <span m='3643200'>tilde</span> <span
  m='3643550'>notation.</span> <span m='3646620'>We</span> <span
  m='3646770'>write</span> <span m='3647020'>tilde</span> <span
  m='3649000'>2/3</span> <span m='3650000'>times</span> <span
  m='3650230'>n</span> <span m='3650500'>to</span> <span m='3650560'>the</span>
  <span m='3650640'>3/2,</span> <span m='3651960'>and</span> <span
  m='3652110'>now</span> <span m='3652280'>we've</span> <span
  m='3652450'>gotten</span> <span m='3652790'>rid</span> <span
  m='3652990'>of</span> <span m='3653060'>the</span> <span
  m='3653140'>delta,</span> <span m='3653620'>because</span> <span
  m='3654020'>this</span> <span m='3654200'>tilde</span> <span
  m='3654620'>is</span> <span m='3654730'>telling</span> <span
  m='3655110'>us</span> <span m='3655260'>that</span> <span
  m='3655420'>everything</span> <span m='3655830'>else</span> <span
  m='3656060'>out</span> <span m='3656200'>here</span> <span
  m='3657550'>gets</span> <span m='3657810'>small</span> <span
  m='3658510'>compared</span> <span m='3658950'>to</span> <span
  m='3659020'>this</span> <span m='3659630'>as</span> <span m='3659840'>n</span>
  <span m='3660060'>gets</span> <span m='3660270'>big.</span> <span
  m='3661500'>And</span> <span m='3661660'>the</span> <span
  m='3661730'>formal</span> <span m='3662180'>definition--</span> <span
  m='3663800'>Let's</span> <span m='3663910'>write</span> <span
  m='3664140'>out</span> <span m='3664260'>the</span> <span
  m='3664330'>formal</span> <span m='3664720'>definition</span> <span
  m='3665157'>for</span> <span m='3665594'>it.</span> <span
  m='3682720'>Now,</span> <span m='3682890'>a</span> <span
  m='3682930'>lot</span> <span m='3683120'>of</span> <span
  m='3683190'>times</span> <span m='3683630'>you'll</span> <span
  m='3683780'>see</span> <span m='3684030'>people</span> <span
  m='3684670'>use</span> <span m='3685110'>this</span> <span
  m='3685290'>symbol</span> <span m='3685600'>to</span> <span
  m='3685670'>mean</span> <span m='3685990'>about.</span> <span
  m='3687170'>That's</span> <span m='3687440'>informal.</span> <span
  m='3688790'>When</span> <span m='3688990'>I'm</span> <span
  m='3689130'>using</span> <span m='3689430'>it</span> <span
  m='3689520'>here,</span> <span m='3690330'>it's</span> <span
  m='3690600'>a</span> <span m='3690640'>very</span> <span
  m='3690970'>formal</span> <span m='3691440'>meaning</span> <span
  m='3692180'>mathematically.</span> <span m='3695580'>A</span> <span
  m='3695670'>function</span> <span m='3696190'>g</span> <span
  m='3696450'>of</span> <span m='3696570'>x</span> <span m='3697340'>is</span>
  <span m='3697480'>tilde,</span> <span m='3698140'>a</span> <span
  m='3698240'>function</span> <span m='3698660'>h</span> <span
  m='3698990'>of</span> <span m='3699100'>x</span> <span
  m='3702930'>means</span> <span m='3703780'>that</span> <span
  m='3703930'>the</span> <span m='3704010'>limit</span> <span
  m='3705810'>as</span> <span m='3706250'>x</span> <span m='3706620'>goes</span>
  <span m='3707060'>to</span> <span m='3707380'>infinity</span> <span
  m='3708700'>of</span> <span m='3709090'>g</span> <span m='3710860'>over</span>
  <span m='3711260'>h</span> <span m='3713700'>is</span> <span
  m='3713890'>1.</span> </p><p><span m='3716840'>In</span> <span
  m='3716990'>other</span> <span m='3717160'>words,</span> <span
  m='3717560'>that</span> <span m='3717660'>as</span> <span m='3717740'>x</span>
  <span m='3718030'>goes</span> <span m='3718290'>to</span> <span
  m='3718380'>infinity--</span> <span m='3718750'>as</span> <span
  m='3718880'>x</span> <span m='3719010'>gets</span> <span
  m='3719260'>big--</span> <span m='3719900'>the</span> <span
  m='3720050'>ratio</span> <span m='3720570'>of</span> <span
  m='3720650'>these</span> <span m='3720870'>guys</span> <span
  m='3721190'>becomes</span> <span m='3721550'>1.</span> <span
  m='3724480'>And</span> <span m='3724570'>let's</span> <span
  m='3724750'>see</span> <span m='3724900'>if</span> <span
  m='3725000'>that's</span> <span m='3725220'>true</span> <span
  m='3725520'>here.</span> <span m='3729040'>Well,</span> <span
  m='3731270'>square</span> <span m='3731680'>root</span> <span
  m='3731720'>of</span> <span m='3731760'>i</span> <span
  m='3731900'>equals</span> <span m='3732540'>this,</span> <span
  m='3732930'>so</span> <span m='3733090'>I</span> <span m='3733170'>need</span>
  <span m='3733330'>to</span> <span m='3733400'>show</span> <span
  m='3733610'>the</span> <span m='3733700'>limit</span> <span
  m='3734570'>of</span> <span m='3734760'>this</span> <span
  m='3735750'>over</span> <span m='3736060'>that</span> <span
  m='3736730'>is</span> <span m='3736930'>1.</span> <span m='3737730'>So</span>
  <span m='3737910'>let's</span> <span m='3738130'>check</span> <span
  m='3738390'>that.</span> <span m='3740550'>A</span> <span
  m='3740610'>limit</span> <span m='3740920'>as</span> <span
  m='3741070'>n</span> <span m='3741220'>goes</span> <span m='3741440'>to</span>
  <span m='3741540'>infinity</span> <span m='3743540'>of</span> <span
  m='3743840'>2/3</span> <span m='3745180'>n</span> <span m='3745440'>to</span>
  <span m='3745500'>the</span> <span m='3745570'>3/2</span> <span
  m='3746360'>plus</span> <span m='3746950'>that</span> <span
  m='3747920'>delta</span> <span m='3748250'>term</span> <span
  m='3749690'>over</span> <span m='3750810'>2/3</span> <span
  m='3751520'>n</span> <span m='3751670'>to</span> <span m='3751740'>the</span>
  <span m='3751800'>3/2.</span> <span m='3753710'>Well,</span> <span
  m='3754020'>that</span> <span m='3754350'>equals--</span> <span
  m='3755950'>divide</span> <span m='3756360'>out</span> <span
  m='3756710'>by</span> <span m='3756940'>2/3</span> <span m='3757390'>n</span>
  <span m='3757530'>to</span> <span m='3757565'>the</span> <span
  m='3757600'>3/2,</span> <span m='3758050'>I</span> <span
  m='3758120'>get</span> <span m='3758250'>a</span> <span m='3758310'>1.</span>
  </p><p><span m='3766100'>Did</span> <span m='3766230'>I--</span> <span
  m='3766330'>should</span> <span m='3766580'>I</span> <span
  m='3766690'>have</span> <span m='3766800'>subtracted?</span> <span
  m='3767150'>No,</span> <span m='3767500'>that's</span> <span
  m='3767966'>OK.</span> <span m='3769830'>One</span> <span
  m='3770500'>plus</span> <span m='3772160'>delta</span> <span
  m='3772620'>n</span> <span m='3773160'>over</span> <span
  m='3774060'>2/3</span> <span m='3774870'>n</span> <span m='3775030'>to</span>
  <span m='3775090'>the</span> <span m='3775160'>3/2.</span> <span
  m='3777850'>If</span> <span m='3777930'>I</span> <span m='3777980'>can</span>
  <span m='3778110'>pull</span> <span m='3778320'>the</span> <span
  m='3778390'>1</span> <span m='3778620'>out</span> <span
  m='3778780'>front,</span> <span m='3779100'>that's</span> <span
  m='3779320'>1</span> <span m='3779680'>plus</span> <span
  m='3780190'>the</span> <span m='3780300'>limit,</span> <span
  m='3782090'>and</span> <span m='3782320'>this</span> <span
  m='3782560'>is</span> <span m='3782720'>now</span> <span
  m='3783270'>delta</span> <span m='3783610'>n</span> <span
  m='3783830'>is</span> <span m='3783930'>at</span> <span
  m='3784000'>most</span> <span m='3784230'>square</span> <span
  m='3784490'>root</span> <span m='3784600'>of</span> <span
  m='3784740'>n,</span> <span m='3785840'>so</span> <span m='3785990'>I</span>
  <span m='3786050'>get</span> <span m='3786230'>square</span> <span
  m='3786570'>root</span> <span m='3786615'>of</span> <span m='3786760'>n</span>
  <span m='3787580'>over</span> <span m='3788550'>2/3</span> <span
  m='3789350'>n</span> <span m='3789550'>to</span> <span m='3789610'>the</span>
  <span m='3789670'>3/2.</span> <span m='3791860'>Square</span> <span
  m='3792250'>root</span> <span m='3792350'>of</span> <span m='3792440'>n</span>
  <span m='3792720'>over</span> <span m='3792980'>n</span> <span
  m='3793110'>to</span> <span m='3793180'>the</span> <span
  m='3793250'>3/2,</span> <span m='3794050'>that</span> <span
  m='3794350'>goes</span> <span m='3794670'>to</span> <span
  m='3794790'>0.</span> <span m='3797110'>So</span> <span
  m='3797350'>this</span> <span m='3797620'>equals</span> <span
  m='3798050'>1.</span> <span m='3802280'>So</span> <span
  m='3802390'>this</span> <span m='3802640'>limit</span> <span
  m='3802950'>is</span> <span m='3803150'>1,</span> <span m='3803670'>and</span>
  <span m='3803800'>so</span> <span m='3803920'>therefore</span> <span
  m='3804370'>I</span> <span m='3804440'>can</span> <span m='3804600'>say</span>
  <span m='3805030'>that</span> <span m='3806130'>the</span> <span
  m='3806240'>sum</span> <span m='3806500'>of</span> <span
  m='3806580'>the</span> <span m='3806640'>first</span> <span
  m='3807170'>n</span> <span m='3807420'>square</span> <span
  m='3807720'>roots</span> <span m='3808140'>is</span> <span
  m='3808360'>tilde</span> <span m='3809570'>2/3</span> <span
  m='3810090'>n</span> <span m='3810230'>to</span> <span m='3810290'>the</span>
  <span m='3810350'>3/2.</span> <span m='3812500'>Any</span> <span
  m='3812670'>questions</span> <span m='3814890'>about</span> <span
  m='3815150'>this?</span> <span m='3815320'>We're</span> <span
  m='3815380'>going</span> <span m='3815510'>to</span> <span
  m='3815570'>do</span> <span m='3815630'>a</span> <span m='3815690'>lot</span>
  <span m='3816100'>of</span> <span m='3816160'>this</span> <span
  m='3816300'>kind</span> <span m='3816450'>of</span> <span
  m='3816510'>notation</span> <span m='3817400'>next</span> <span
  m='3817570'>time.</span> <span m='3818050'>Yeah.</span> </p><p><span
  m='3819274'>AUDIENCE:</span> <span m='3819756'>When you took</span> <span
  m='3820240'>the integral</span> <span m='3820690'>and</span> <span
  m='3821140'>got</span> <span m='3821530'>2/3</span> <span
  m='3821670'>into</span> <span m='3821930'>the</span> <span
  m='3822400'>3/2</span> <span m='3822760'>minus</span> <span
  m='3823000'>1,</span> <span m='3824460'>why</span> <span
  m='3824850'>did</span> <span m='3825080'>the</span> <span
  m='3825450'>minus</span> <span m='3825840'>1</span> <span
  m='3827170'>not</span> <span m='3827400'>become</span> <span
  m='3827720'>part</span> <span m='3827910'>of</span> <span
  m='3828000'>the</span> <span m='3828620'>actual</span> <span
  m='3828880'>solution</span> <span m='3829050'>and</span> <span
  m='3829220'>become</span> <span m='3829530'>part</span> <span
  m='3829615'>of</span> <span m='3829657'>the</span> <span
  m='3829700'>delta?</span> </p><p><span m='3831430'>PROFESSOR: OK.</span> <span
  m='3831900'>So</span> <span m='3832330'>you</span> <span
  m='3832530'>brought</span> <span m='3832770'>it</span> <span
  m='3832875'>up</span> <span m='3832980'>to</span> <span
  m='3833060'>here,</span> <span m='3833330'>right?</span> <span
  m='3834500'>OK.</span> <span m='3835360'>So</span> <span
  m='3836250'>then</span> <span m='3836530'>I</span> <span
  m='3836620'>plug</span> <span m='3837660'>that</span> <span
  m='3838220'>into</span> <span m='3838880'>the</span> <span
  m='3839030'>integral</span> <span m='3839220'>that</span> <span
  m='3839410'>appears</span> <span m='3839840'>on</span> <span
  m='3839930'>both</span> <span m='3840150'>sides</span> <span
  m='3840490'>here,</span> <span m='3840640'>and</span> <span
  m='3840730'>here</span> <span m='3840920'>I</span> <span
  m='3841060'>add</span> <span m='3841190'>the</span> <span m='3841290'>f</span>
  <span m='3841480'>1,</span> <span m='3841790'>here</span> <span
  m='3841970'>I</span> <span m='3842070'>add</span> <span m='3842300'>f</span>
  <span m='3842605'>n,</span> <span m='3844200'>and</span> <span
  m='3844380'>now</span> <span m='3844580'>I</span> <span
  m='3844680'>have</span> <span m='3845450'>the</span> <span
  m='3845610'>lower</span> <span m='3845890'>bound</span> <span
  m='3846240'>here</span> <span m='3846720'>and</span> <span
  m='3846830'>the</span> <span m='3846910'>upper</span> <span
  m='3847060'>bound</span> <span m='3847320'>here.</span> <span
  m='3847480'>Are</span> <span m='3847570'>you</span> <span
  m='3847650'>good</span> <span m='3847820'>with</span> <span
  m='3847930'>those?</span> <span m='3849150'>All</span> <span
  m='3849370'>right.</span> </p><p><span m='3849590'>Now</span> <span
  m='3849980'>some</span> <span m='3850170'>judgment</span> <span
  m='3850620'>takes</span> <span m='3850890'>place,</span> <span
  m='3852100'>and</span> <span m='3852340'>what</span> <span
  m='3852450'>I'm</span> <span m='3852590'>really</span> <span
  m='3852880'>trying</span> <span m='3853150'>to</span> <span
  m='3853230'>do</span> <span m='3853490'>here</span> <span
  m='3854310'>is</span> <span m='3854540'>figure</span> <span
  m='3854830'>out</span> <span m='3855020'>what</span> <span
  m='3855310'>are</span> <span m='3855400'>the</span> <span
  m='3855520'>important</span> <span m='3856100'>terms</span> <span
  m='3857590'>in</span> <span m='3857790'>these</span> <span
  m='3857980'>bounds</span> <span m='3858820'>as</span> <span
  m='3859050'>n</span> <span m='3859200'>gets</span> <span
  m='3859410'>big?</span> <span m='3860250'>How</span> <span
  m='3860530'>big</span> <span m='3860800'>is</span> <span
  m='3860970'>this</span> <span m='3861260'>growing</span> <span
  m='3861730'>as</span> <span m='3861870'>n</span> <span m='3862070'>gets</span>
  <span m='3862250'>big?</span> <span m='3863440'>Well,</span> <span
  m='3863570'>as</span> <span m='3863700'>n</span> <span m='3863890'>gets</span>
  <span m='3864060'>big,</span> <span m='3865240'>the</span> <span
  m='3865340'>1/3</span> <span m='3865860'>is</span> <span
  m='3866000'>not</span> <span m='3866220'>doing</span> <span
  m='3866490'>much.</span> <span m='3868350'>As</span> <span
  m='3868600'>n</span> <span m='3868820'>gets</span> <span
  m='3869070'>big,</span> <span m='3869890'>the</span> <span
  m='3870010'>square</span> <span m='3870370'>root</span> <span
  m='3870490'>of</span> <span m='3870610'>n</span> <span
  m='3870730'>grows,</span> <span m='3872060'>but</span> <span
  m='3872270'>it's</span> <span m='3872430'>nothing</span> <span
  m='3872920'>like</span> <span m='3873070'>what's</span> <span
  m='3873240'>happening</span> <span m='3873610'>here.</span> </p><p><span
  m='3874370'>If</span> <span m='3874520'>you</span> <span
  m='3874670'>had</span> <span m='3874840'>to</span> <span
  m='3874910'>describe</span> <span m='3875420'>to</span> <span
  m='3875490'>somebody</span> <span m='3875820'>what's</span> <span
  m='3876050'>going</span> <span m='3876270'>on</span> <span
  m='3876400'>in</span> <span m='3876480'>this</span> <span
  m='3876660'>bound,</span> <span m='3878230'>would</span> <span
  m='3878400'>you</span> <span m='3878480'>start</span> <span
  m='3878810'>here</span> <span m='3879510'>or</span> <span
  m='3879680'>here?</span> <span m='3880710'>No.</span> <span
  m='3880990'>You'd</span> <span m='3881170'>start</span> <span
  m='3881450'>here.</span> <span m='3881650'>This</span> <span
  m='3881880'>is</span> <span m='3881980'>the</span> <span
  m='3882110'>action,</span> <span m='3883040'>and</span> <span
  m='3883240'>there's</span> <span m='3883420'>a</span> <span
  m='3883480'>little</span> <span m='3883720'>bit--</span> <span
  m='3883980'>the</span> <span m='3884060'>rest</span> <span
  m='3884330'>is</span> <span m='3884430'>just</span> <span
  m='3884750'>in</span> <span m='3884830'>the</span> <span
  m='3884890'>slop,</span> <span m='3885380'>in</span> <span
  m='3885500'>the</span> <span m='3885630'>air.</span> <span
  m='3886600'>And</span> <span m='3886840'>so</span> <span
  m='3886940'>now</span> <span m='3887110'>I've</span> <span
  m='3887190'>used</span> <span m='3887470'>judgement</span> <span
  m='3887860'>to</span> <span m='3887920'>say</span> <span
  m='3888810'>that</span> <span m='3888920'>delta</span> <span
  m='3890040'>is</span> <span m='3890270'>somewhere</span> <span
  m='3891080'>in</span> <span m='3891200'>this</span> <span
  m='3891390'>stuff</span> <span m='3891810'>here.</span> </p><p><span
  m='3893640'>What's</span> <span m='3893820'>really</span> <span
  m='3894200'>happening,</span> <span m='3894620'>and</span> <span
  m='3894930'>the</span> <span m='3895000'>nice</span> <span
  m='3895085'>thing</span> <span m='3895170'>is</span> <span
  m='3895310'>they</span> <span m='3895430'>match.</span> <span
  m='3895830'>The</span> <span m='3895910'>lower</span> <span
  m='3896160'>bound</span> <span m='3897130'>and</span> <span
  m='3897240'>the</span> <span m='3897320'>upper</span> <span
  m='3897490'>bound</span> <span m='3897750'>match</span> <span
  m='3898150'>on</span> <span m='3898250'>that</span> <span
  m='3898430'>term.</span> <span m='3899770'>So</span> <span
  m='3899870'>what</span> <span m='3899990'>I</span> <span m='3900060'>do</span>
  <span m='3900280'>is</span> <span m='3900400'>I</span> <span
  m='3900500'>write</span> <span m='3902190'>it</span> <span
  m='3902430'>equals</span> <span m='3903550'>this</span> <span
  m='3903890'>term</span> <span m='3904750'>plus</span> <span
  m='3905160'>something</span> <span m='3905970'>that's</span> <span
  m='3906150'>smaller</span> <span m='3908370'>and,</span> <span
  m='3908860'>in</span> <span m='3908960'>particular,</span> <span
  m='3910390'>it's</span> <span m='3910650'>between</span> <span
  m='3910970'>1/3</span> <span m='3911340'>and</span> <span
  m='3911520'>square</span> <span m='3911660'>root</span> <span
  m='3911800'>of</span> <span m='3911905'>n</span> <span
  m='3912010'>minus</span> <span m='3912290'>2/3.</span> <span
  m='3914080'>All</span> <span m='3914110'>right.</span> </p><p><span
  m='3914780'>So</span> <span m='3914810'>what</span> <span
  m='3914900'>I'm</span> <span m='3915010'>trying</span> <span
  m='3915450'>to</span> <span m='3915520'>capture</span> <span
  m='3916040'>here</span> <span m='3916890'>is</span> <span
  m='3918100'>just</span> <span m='3918340'>the</span> <span
  m='3918430'>guts</span> <span m='3919010'>of</span> <span
  m='3919100'>what's</span> <span m='3919360'>happening</span> <span
  m='3919830'>to</span> <span m='3919940'>this</span> <span
  m='3920140'>function</span> <span m='3920730'>as</span> <span
  m='3920920'>n</span> <span m='3921070'>grows,</span> <span
  m='3922040'>and</span> <span m='3922220'>the</span> <span
  m='3922300'>guts</span> <span m='3922630'>of</span> <span
  m='3922730'>it</span> <span m='3923300'>is</span> <span
  m='3923520'>this.</span> <span m='3924530'>It's</span> <span
  m='3924730'>not</span> <span m='3924940'>exactly</span> <span
  m='3925480'>equal</span> <span m='3925720'>to</span> <span
  m='3925820'>2/3</span> <span m='3926550'>times</span> <span
  m='3926800'>n</span> <span m='3926900'>to</span> <span m='3926995'>the</span>
  <span m='3927090'>3/2,</span> <span m='3928210'>but</span> <span
  m='3928370'>it's</span> <span m='3928530'>close</span> <span
  m='3929510'>and,</span> <span m='3929660'>in</span> <span
  m='3929760'>fact,</span> <span m='3930270'>if</span> <span
  m='3930350'>I</span> <span m='3930440'>take</span> <span
  m='3930670'>the</span> <span m='3930740'>limit</span> <span
  m='3931230'>of</span> <span m='3931480'>this</span> <span
  m='3931880'>over</span> <span m='3932230'>that,</span> <span
  m='3932585'>that</span> <span m='3932940'>limit</span> <span
  m='3933180'>goes</span> <span m='3933380'>to</span> <span
  m='3933470'>1.</span> </p><p><span m='3934930'>It's</span> <span
  m='3935110'>a</span> <span m='3935160'>way</span> <span m='3935460'>of</span>
  <span m='3935550'>saying</span> <span m='3936020'>they're</span> <span
  m='3936790'>approximately</span> <span m='3937670'>the</span> <span
  m='3937770'>same</span> <span m='3939060'>that's</span> <span
  m='3939260'>called</span> <span m='3939540'>asymptotically</span> <span
  m='3940450'>the</span> <span m='3940550'>same,</span> <span
  m='3941760'>and</span> <span m='3941890'>we'll</span> <span
  m='3941980'>talk</span> <span m='3942170'>a</span> <span
  m='3942220'>lot</span> <span m='3942560'>more</span> <span
  m='3942780'>about</span> <span m='3943000'>asymptotic</span> <span
  m='3943620'>notation</span> <span m='3944760'>next</span> <span
  m='3944910'>time.</span> <span m='3945150'>We'll</span> <span
  m='3945360'>give</span> <span m='3945540'>you</span> <span
  m='3945610'>five</span> <span m='3945970'>more</span> <span
  m='3946140'>symbols</span> <span m='3946560'>besides</span> <span
  m='3947120'>tilde</span> <span m='3948380'>that</span> <span
  m='3948500'>people</span> <span m='3948760'>use.</span> <span
  m='3951900'>Any</span> <span m='3952050'>questions</span> <span
  m='3952540'>about--</span> <span m='3953250'>maybe</span> <span
  m='3953500'>start</span> <span m='3953770'>with</span> <span
  m='3953870'>the</span> <span m='3953930'>bounds.</span> <span
  m='3954670'>Any</span> <span m='3954860'>question</span> <span
  m='3955230'>on</span> <span m='3955310'>the</span> <span
  m='3955380'>bounds</span> <span m='3955730'>that</span> <span
  m='3955820'>we</span> <span m='3955900'>got?</span> <span
  m='3957110'>That's</span> <span m='3957350'>the</span> <span
  m='3957470'>integration</span> <span m='3957970'>method,</span> <span
  m='3958250'>first</span> <span m='3958570'>getting</span> <span
  m='3958760'>the</span> <span m='3958830'>bounds.</span> <span
  m='3961790'>You</span> <span m='3961900'>take</span> <span
  m='3962150'>the</span> <span m='3962280'>integral,</span> <span
  m='3964050'>you</span> <span m='3964235'>add</span> <span m='3964420'>f</span>
  <span m='3964580'>of</span> <span m='3964680'>1</span> <span
  m='3964920'>for</span> <span m='3964990'>the</span> <span
  m='3965070'>lower</span> <span m='3965320'>bound,</span> <span
  m='3965650'>you</span> <span m='3965730'>add</span> <span m='3966010'>f</span>
  <span m='3966190'>of</span> <span m='3966335'>n</span> <span
  m='3966480'>for</span> <span m='3966550'>the</span> <span
  m='3966660'>upper</span> <span m='3966830'>bound,</span> <span
  m='3968180'>and</span> <span m='3968330'>it's</span> <span
  m='3968480'>in</span> <span m='3968580'>between,</span> <span
  m='3969010'>somewhere</span> <span m='3969360'>in</span> <span
  m='3969440'>there.</span> <span m='3972570'>Questions</span> <span
  m='3972940'>there?</span> </p><p><span m='3974960'>All</span> <span
  m='3975160'>right.</span> <span m='3975470'>Then</span> <span
  m='3975670'>we</span> <span m='3975770'>plugged</span> <span
  m='3976100'>it</span> <span m='3976170'>in,</span> <span
  m='3977630'>and</span> <span m='3977800'>now</span> <span
  m='3978090'>we</span> <span m='3978590'>look</span> <span
  m='3978830'>at</span> <span m='3979420'>this</span> <span
  m='3979690'>tilde</span> <span m='3980040'>notation</span> <span
  m='3980590'>that</span> <span m='3980720'>says--</span> <span
  m='3981860'>well,</span> <span m='3981960'>first</span> <span
  m='3982210'>we'd</span> <span m='3982300'>write</span> <span
  m='3982470'>it</span> <span m='3982540'>like</span> <span
  m='3982700'>this.</span> <span m='3982940'>The</span> <span
  m='3983100'>sum</span> <span m='3983510'>is</span> <span
  m='3984120'>this</span> <span m='3984340'>value</span> <span
  m='3984650'>plus</span> <span m='3984910'>an</span> <span
  m='3985000'>error</span> <span m='3985270'>term</span> <span
  m='3986030'>and,</span> <span m='3986240'>lo</span> <span
  m='3986400'>and</span> <span m='3986500'>behold,</span> <span
  m='3987390'>that</span> <span m='3987620'>error</span> <span
  m='3987890'>term</span> <span m='3988150'>is</span> <span
  m='3988230'>small.</span> <span m='3990840'>If</span> <span
  m='3990875'>I</span> <span m='3990910'>take</span> <span
  m='3991150'>the</span> <span m='3991220'>limit</span> <span
  m='3991690'>of</span> <span m='3991850'>the</span> <span
  m='3991930'>whole</span> <span m='3992180'>thing</span> <span
  m='3992570'>divided</span> <span m='3992960'>by</span> <span
  m='3993250'>the</span> <span m='3993670'>big</span> <span
  m='3993920'>term,</span> <span m='3994480'>I</span> <span
  m='3994590'>get</span> <span m='3994800'>1,</span> <span
  m='3995760'>which</span> <span m='3995940'>means</span> <span
  m='3996170'>this</span> <span m='3996360'>thing</span> <span
  m='3996560'>is</span> <span m='3997090'>really</span> <span
  m='3997440'>not</span> <span m='3997620'>important.</span> <span
  m='3998780'>So</span> <span m='3998940'>I</span> <span
  m='3999000'>write</span> <span m='3999250'>this.</span> <span
  m='4002630'>Questions</span> <span m='4003090'>on</span> <span
  m='4003220'>that?</span> <span m='4005840'>All</span> <span
  m='4006090'>right.</span> </p><p><span m='4008500'>There's</span> <span
  m='4008710'>one</span> <span m='4009050'>more</span> <span
  m='4009480'>case</span> <span m='4009780'>to</span> <span
  m='4009880'>consider,</span> <span m='4011560'>and</span> <span
  m='4011750'>now</span> <span m='4011830'>we're</span> <span
  m='4011910'>going</span> <span m='4011990'>to</span> <span
  m='4012050'>go</span> <span m='4012160'>back</span> <span
  m='4012560'>to</span> <span m='4012740'>the</span> <span
  m='4012860'>integration</span> <span m='4013380'>bounds,</span> <span
  m='4013750'>and</span> <span m='4013850'>that</span> <span
  m='4014070'>is</span> <span m='4014450'>when</span> <span m='4014950'>f</span>
  <span m='4015330'>is</span> <span m='4015510'>a</span> <span
  m='4015890'>decreasing</span> <span m='4016520'>function,</span> <span
  m='4017780'>and</span> <span m='4017860'>we're</span> <span
  m='4017940'>going</span> <span m='4018120'>to</span> <span
  m='4018190'>do</span> <span m='4018350'>the</span> <span
  m='4018450'>analysis</span> <span m='4018930'>for</span> <span
  m='4019050'>that,</span> <span m='4019390'>and</span> <span
  m='4019490'>then</span> <span m='4019500'>we'll</span> <span
  m='4019610'>be</span> <span m='4019740'>all</span> <span
  m='4019930'>done.</span> </p><p><span m='4024480'>So</span> <span
  m='4024550'>we're</span> <span m='4024610'>going</span> <span
  m='4024730'>to</span> <span m='4024790'>look</span> <span
  m='4025030'>at</span> <span m='4025250'>integration</span> <span
  m='4025910'>bounds</span> <span m='4029740'>when</span> <span
  m='4030140'>f</span> <span m='4031170'>is</span> <span
  m='4031650'>decreasing</span> <span m='4032690'>and</span> <span
  m='4032910'>positive</span> <span m='4033370'>still.</span> <span
  m='4045660'>The</span> <span m='4045790'>example</span> <span
  m='4046290'>here</span> <span m='4046650'>might</span> <span
  m='4046900'>be,</span> <span m='4048190'>for</span> <span
  m='4048220'>example,</span> <span m='4053540'>the</span> <span
  m='4053580'>sum</span> <span m='4054450'>i</span> <span
  m='4054810'>equals</span> <span m='4055190'>1</span> <span
  m='4055470'>to</span> <span m='4055570'>n,</span> <span m='4056750'>1</span>
  <span m='4057250'>over</span> <span m='4057640'>the</span> <span
  m='4057730'>square</span> <span m='4058020'>root</span> <span
  m='4058140'>of</span> <span m='4058270'>i.</span> <span m='4060260'>Say</span>
  <span m='4060590'>you</span> <span m='4060720'>had</span> <span
  m='4060970'>to</span> <span m='4061040'>get</span> <span
  m='4061310'>some</span> <span m='4061660'>idea</span> <span
  m='4062050'>of</span> <span m='4062130'>how</span> <span
  m='4062370'>fast</span> <span m='4062830'>that</span> <span
  m='4063020'>function</span> <span m='4063430'>is</span> <span
  m='4063550'>growing</span> <span m='4064600'>as</span> <span
  m='4064770'>a</span> <span m='4064820'>function</span> <span
  m='4065190'>of</span> <span m='4065300'>n.</span> <span m='4065970'>I'm</span>
  <span m='4066190'>summing</span> <span m='4066720'>the</span> <span
  m='4066850'>first</span> <span m='4068150'>n</span> <span
  m='4070120'>inverse</span> <span m='4070630'>as</span> <span
  m='4070750'>the</span> <span m='4070810'>square</span> <span
  m='4071140'>roots.</span> <span m='4073030'>What</span> <span
  m='4073210'>is</span> <span m='4073330'>that</span> <span
  m='4073550'>roughly</span> <span m='4073960'>going</span> <span
  m='4074090'>to</span> <span m='4074180'>be?</span> <span
  m='4074370'>How</span> <span m='4074530'>fast</span> <span
  m='4074880'>does</span> <span m='4074935'>that</span> <span
  m='4074990'>grow</span> <span m='4075185'>as</span> <span m='4075380'>a</span>
  <span m='4075420'>function</span> <span m='4075780'>of</span> <span
  m='4075880'>n?</span> <span m='4077860'>So</span> <span
  m='4078210'>let's</span> <span m='4078380'>do</span> <span
  m='4078550'>that.</span> </p><p><span m='4082510'>And,</span> <span
  m='4082640'>of</span> <span m='4082700'>course,</span> <span
  m='4083000'>1</span> <span m='4083150'>over</span> <span
  m='4083330'>square</span> <span m='4083520'>root</span> <span
  m='4083620'>of</span> <span m='4083720'>i</span> <span
  m='4083880'>decreases</span> <span m='4085330'>as</span> <span
  m='4085520'>i</span> <span m='4085670'>gets</span> <span
  m='4085890'>bigger.</span> <span m='4088500'>So</span> <span
  m='4088700'>let's</span> <span m='4088960'>do</span> <span
  m='4089090'>the</span> <span m='4089200'>general</span> <span
  m='4089677'>picture</span> <span m='4090631'>again</span> <span
  m='4094240'>and</span> <span m='4094300'>see</span> <span
  m='4094480'>what</span> <span m='4094640'>happens.</span> <span
  m='4095990'>So</span> <span m='4096149'>we</span> <span
  m='4096240'>have</span> <span m='4096370'>0,</span> <span
  m='4097840'>1,</span> <span m='4098750'>2,</span> <span m='4099790'>3,</span>
  <span m='4101700'>n</span> <span m='4101920'>minus</span> <span
  m='4102270'>2,</span> <span m='4103290'>n</span> <span
  m='4103460'>minus</span> <span m='4103810'>1,</span> <span
  m='4104979'>n,</span> <span m='4106939'>and</span> <span
  m='4107120'>now</span> <span m='4108220'>f</span> <span m='4108479'>of</span>
  <span m='4108634'>n</span> <span m='4108790'>is</span> <span
  m='4108890'>the</span> <span m='4108970'>small</span> <span
  m='4109340'>term</span> <span m='4111550'>and</span> <span
  m='4111990'>f</span> <span m='4112189'>of</span> <span m='4112330'>n</span>
  <span m='4112450'>minus</span> <span m='4112790'>1,</span> <span
  m='4115450'>f</span> <span m='4115830'>of</span> <span m='4116010'>3</span>
  <span m='4116689'>here,</span> <span m='4121040'>f</span> <span
  m='4121250'>of</span> <span m='4121359'>1.</span> </p><p><span
  m='4123090'>Now,</span> <span m='4123910'>I'm</span> <span
  m='4123979'>going</span> <span m='4124100'>to</span> <span
  m='4124160'>draw</span> <span m='4124490'>the</span> <span
  m='4124600'>rectangle.</span> <span m='4125250'>This</span> <span
  m='4125590'>has</span> <span m='4125899'>area</span> <span
  m='4126359'>f</span> <span m='4126620'>of</span> <span m='4126720'>1.</span>
  <span m='4129470'>This</span> <span m='4129750'>one</span> <span
  m='4130080'>has</span> <span m='4130470'>area</span> <span
  m='4131399'>f</span> <span m='4131609'>of</span> <span m='4131700'>2.</span>
  <span m='4135080'>This</span> <span m='4135370'>one</span> <span
  m='4135680'>has</span> <span m='4135939'>area</span> <span
  m='4136380'>f</span> <span m='4136600'>of</span> <span m='4136720'>3,</span>
  <span m='4141210'>and</span> <span m='4141550'>then</span> <span
  m='4141760'>this</span> <span m='4141990'>one</span> <span
  m='4143130'>has</span> <span m='4143569'>area</span> <span
  m='4145229'>f</span> <span m='4145410'>of</span> <span m='4145529'>n</span>
  <span m='4145660'>minus</span> <span m='4146010'>1</span> <span
  m='4146450'>here,</span> <span m='4149640'>and</span> <span
  m='4149870'>then,</span> <span m='4150029'>lastly,</span> <span
  m='4150710'>area</span> <span m='4151050'>f</span> <span m='4151310'>of</span>
  <span m='4151430'>n.</span> <span m='4154279'>So</span> <span
  m='4154460'>the</span> <span m='4154569'>sum</span> <span
  m='4155689'>is</span> <span m='4156029'>the</span> <span
  m='4156180'>area</span> <span m='4156620'>in</span> <span
  m='4156819'>the</span> <span m='4156910'>rectangles,</span> <span
  m='4157500'>just</span> <span m='4157770'>like</span> <span
  m='4157939'>before,</span> <span m='4158819'>except</span> <span
  m='4159050'>now</span> <span m='4159229'>the</span> <span
  m='4159330'>rectangles</span> <span m='4159790'>are</span> <span
  m='4159840'>getting</span> <span m='4160050'>smaller.</span> <span
  m='4162020'>Let's</span> <span m='4162260'>draw</span> <span
  m='4162510'>the</span> <span m='4162660'>integral</span> <span
  m='4164569'>like</span> <span m='4164800'>we</span> <span
  m='4164880'>did</span> <span m='4165029'>before.</span> <span
  m='4167350'>The</span> <span m='4168350'>integral</span> <span
  m='4168870'>is</span> <span m='4168950'>the</span> <span
  m='4169080'>area</span> <span m='4169510'>under</span> <span
  m='4169760'>this</span> <span m='4170000'>curve,</span> <span
  m='4170660'>f</span> <span m='4170870'>of</span> <span m='4170979'>x</span>
  <span m='4171290'>here,</span> <span m='4172380'>just</span> <span
  m='4172760'>like</span> <span m='4172930'>before.</span> <span
  m='4175960'>So</span> <span m='4176120'>this</span> <span
  m='4176319'>is</span> <span m='4176450'>f</span> <span m='4176620'>of</span>
  <span m='4176729'>x,</span> <span m='4178270'>only</span> <span
  m='4178520'>it's</span> <span m='4178660'>decreasing.</span> </p><p><span
  m='4181840'>Now,</span> <span m='4183200'>let's</span> <span
  m='4183590'>take</span> <span m='4183859'>the</span> <span
  m='4184029'>area</span> <span m='4184550'>under</span> <span
  m='4184850'>this</span> <span m='4185069'>curve,</span> <span
  m='4188560'>and</span> <span m='4188770'>add</span> <span m='4189149'>f</span>
  <span m='4189340'>of</span> <span m='4189430'>1</span> <span
  m='4189670'>to</span> <span m='4189850'>it.</span> <span m='4191540'>If</span>
  <span m='4191710'>I</span> <span m='4191859'>take</span> <span
  m='4192130'>the</span> <span m='4192279'>area</span> <span
  m='4192670'>under</span> <span m='4192899'>this</span> <span
  m='4193354'>curve,</span> <span m='4194460'>all</span> <span
  m='4194720'>the</span> <span m='4194780'>way</span> <span
  m='4194910'>down</span> <span m='4195150'>to</span> <span
  m='4195220'>here</span> <span m='4197360'>and</span> <span
  m='4197510'>then</span> <span m='4197700'>add</span> <span
  m='4199040'>f</span> <span m='4199280'>of</span> <span m='4199390'>1,</span>
  <span m='4200000'>what</span> <span m='4200180'>do</span> <span
  m='4200290'>I</span> <span m='4200390'>get?</span> <span
  m='4204440'>Upper</span> <span m='4204760'>bound</span> <span
  m='4205870'>on</span> <span m='4206150'>my</span> <span
  m='4206290'>sum.</span> <span m='4207840'>OK.</span> <span
  m='4208290'>So</span> <span m='4208490'>the</span> <span
  m='4208600'>sum</span> <span m='4209910'>i</span> <span
  m='4210170'>equals</span> <span m='4210600'>1</span> <span
  m='4210880'>to</span> <span m='4211330'>n</span> <span m='4211780'>f</span>
  <span m='4212230'>of</span> <span m='4212640'>i</span> <span
  m='4213460'>is</span> <span m='4213910'>upper</span> <span
  m='4214220'>bounded</span> <span m='4214720'>by</span> <span
  m='4216670'>that</span> <span m='4216940'>guy,</span> <span
  m='4217270'>which</span> <span m='4217370'>is</span> <span
  m='4217460'>f</span> <span m='4217650'>of</span> <span m='4217750'>1,</span>
  <span m='4219610'>plus</span> <span m='4220100'>my</span> <span
  m='4220270'>integral,</span> <span m='4224850'>which</span> <span
  m='4225010'>is</span> <span m='4225120'>the</span> <span
  m='4225260'>area</span> <span m='4225540'>under</span> <span
  m='4225680'>the</span> <span m='4225760'>curve.</span> <span
  m='4227520'>The</span> <span m='4227690'>integral</span> <span
  m='4228060'>is</span> <span m='4228140'>the</span> <span
  m='4228270'>area</span> <span m='4228530'>under</span> <span
  m='4228720'>that</span> <span m='4228970'>curve,</span> <span
  m='4229540'>starting</span> <span m='4230020'>here,</span> <span
  m='4231400'>and</span> <span m='4231520'>that</span> <span
  m='4232360'>contains</span> <span m='4232990'>all</span> <span
  m='4233230'>these</span> <span m='4233480'>rectangles,</span> <span
  m='4235110'>and</span> <span m='4235390'>then</span> <span
  m='4235510'>I</span> <span m='4235640'>just</span> <span
  m='4235860'>add</span> <span m='4236090'>in</span> <span m='4236500'>f</span>
  <span m='4236710'>of</span> <span m='4236800'>1</span> <span
  m='4237180'>to</span> <span m='4237290'>get</span> <span m='4237420'>an</span>
  <span m='4237480'>upper</span> <span m='4237650'>bound.</span> </p><p><span
  m='4241540'>Now,</span> <span m='4241820'>for</span> <span
  m='4241940'>the</span> <span m='4242010'>lower</span> <span
  m='4242340'>bound,</span> <span m='4243430'>think</span> <span
  m='4243710'>about</span> <span m='4244060'>shifting</span> <span
  m='4244750'>the</span> <span m='4244840'>whole</span> <span
  m='4245340'>curve</span> <span m='4245910'>left</span> <span
  m='4246440'>by</span> <span m='4246630'>one.</span> <span
  m='4247830'>That</span> <span m='4248080'>goes</span> <span
  m='4248280'>to</span> <span m='4248370'>there,</span> <span
  m='4249430'>this</span> <span m='4249630'>goes</span> <span
  m='4249880'>to</span> <span m='4249970'>here,</span> <span
  m='4251190'>that</span> <span m='4251390'>goes</span> <span
  m='4251660'>to</span> <span m='4251750'>here,</span> <span
  m='4252800'>that</span> <span m='4253010'>goes</span> <span
  m='4253260'>to</span> <span m='4253340'>there,</span> <span
  m='4253840'>and</span> <span m='4254240'>that</span> <span
  m='4254540'>goes</span> <span m='4254770'>to</span> <span
  m='4254860'>there.</span> <span m='4256740'>The</span> <span
  m='4257210'>area</span> <span m='4257600'>under</span> <span
  m='4257750'>the</span> <span m='4257840'>curve</span> <span
  m='4258210'>did</span> <span m='4258340'>not</span> <span
  m='4258740'>change</span> <span m='4259200'>when</span> <span
  m='4259320'>I</span> <span m='4259410'>shifted</span> <span
  m='4259870'>it</span> <span m='4259980'>left</span> <span
  m='4260240'>by</span> <span m='4260390'>one.</span> <span
  m='4262710'>This</span> <span m='4262980'>is</span> <span
  m='4263060'>now</span> <span m='4263310'>my</span> <span
  m='4263490'>area</span> <span m='4263890'>under</span> <span
  m='4264060'>the</span> <span m='4264160'>curve.</span> <span
  m='4266760'>Stops</span> <span m='4267180'>here.</span> <span
  m='4268830'>What</span> <span m='4269060'>do</span> <span m='4269170'>I</span>
  <span m='4269260'>get</span> <span m='4269480'>when</span> <span
  m='4269600'>I</span> <span m='4269660'>take</span> <span
  m='4269970'>that</span> <span m='4270260'>area</span> <span
  m='4271310'>and</span> <span m='4271500'>add</span> <span
  m='4271690'>in</span> <span m='4271820'>this</span> <span
  m='4271980'>last</span> <span m='4272250'>box,</span> <span
  m='4272800'>f</span> <span m='4273271'>of</span> <span m='4273742'>n?</span>
  <span m='4276570'>A</span> <span m='4276690'>lower</span> <span
  m='4277050'>bound,</span> <span m='4278540'>because</span> <span
  m='4278750'>it's</span> <span m='4278920'>contained</span> <span
  m='4279780'>in</span> <span m='4279970'>all</span> <span
  m='4280190'>the</span> <span m='4280280'>rectangles.</span> </p><p><span
  m='4290900'>Now,</span> <span m='4291120'>what's</span> <span
  m='4291410'>really</span> <span m='4291840'>weird</span> <span
  m='4293340'>about</span> <span m='4293720'>these</span> <span
  m='4293940'>formulas,</span> <span m='4296520'>do</span> <span
  m='4296640'>they</span> <span m='4296780'>look</span> <span
  m='4296930'>familiar?</span> <span m='4300280'>Yeah.</span> <span
  m='4301780'>Yeah.</span> <span m='4303300'>I</span> <span
  m='4303430'>switched</span> <span m='4303760'>them.</span> <span
  m='4305290'>Yeah.</span> <span m='4305460'>They're</span> <span
  m='4305560'>the</span> <span m='4305660'>same</span> <span
  m='4306010'>formulas</span> <span m='4306470'>we</span> <span
  m='4306610'>had</span> <span m='4306810'>over</span> <span
  m='4307020'>here,</span> <span m='4308870'>except</span> <span
  m='4309630'>we</span> <span m='4309780'>switched</span> <span
  m='4310090'>the</span> <span m='4310160'>direction</span> <span
  m='4310770'>on</span> <span m='4310850'>the</span> <span
  m='4310910'>less</span> <span m='4311150'>than</span> <span
  m='4311350'>and</span> <span m='4311460'>greater</span> <span
  m='4311730'>than</span> <span m='4312040'>signs.</span> <span
  m='4313970'>Well,</span> <span m='4314130'>I</span> <span
  m='4314190'>swapped</span> <span m='4314670'>f</span> <span
  m='4314830'>of</span> <span m='4314920'>1</span> <span m='4315130'>and</span>
  <span m='4315220'>f</span> <span m='4315380'>of</span> <span
  m='4315540'>n,</span> <span m='4315700'>however</span> <span
  m='4315930'>you</span> <span m='4316000'>want</span> <span
  m='4316140'>to</span> <span m='4316210'>think</span> <span
  m='4316390'>about</span> <span m='4316630'>it.</span> <span
  m='4317280'>The</span> <span m='4318070'>lower</span> <span
  m='4318500'>bound</span> <span m='4319020'>here</span> <span
  m='4320010'>in</span> <span m='4320100'>that</span> <span
  m='4320280'>case</span> <span m='4320570'>became</span> <span
  m='4320910'>the</span> <span m='4321040'>upper</span> <span
  m='4321230'>bound</span> <span m='4322250'>in</span> <span
  m='4322390'>this</span> <span m='4322560'>case.</span> <span
  m='4325000'>Is</span> <span m='4325070'>that</span> <span
  m='4325290'>possible</span> <span m='4325780'>that</span> <span
  m='4326250'>the</span> <span m='4326360'>lower</span> <span
  m='4326570'>bound</span> <span m='4326780'>became</span> <span
  m='4327050'>the</span> <span m='4327140'>upper</span> <span
  m='4327300'>bound?</span> <span m='4329330'>Yeah.</span> <span
  m='4329880'>Yeah,</span> <span m='4330650'>because</span> <span
  m='4330970'>what</span> <span m='4331170'>really</span> <span
  m='4331470'>happened</span> <span m='4331820'>here--</span> <span
  m='4331910'>which</span> <span m='4332090'>is</span> <span
  m='4332190'>the</span> <span m='4332270'>big</span> <span
  m='4332510'>term</span> <span m='4332790'>in</span> <span
  m='4332860'>this</span> <span m='4333020'>case,</span> <span
  m='4333300'>fn</span> <span m='4333660'>or</span> <span m='4333760'>f1?</span>
  <span m='4335240'>f1</span> <span m='4335650'>is</span> <span
  m='4335720'>the</span> <span m='4335790'>big</span> <span
  m='4336000'>term</span> <span m='4336280'>because</span> <span
  m='4336440'>it's</span> <span m='4336580'>decreasing,</span> <span
  m='4337290'>so</span> <span m='4337390'>it's</span> <span
  m='4337590'>totally</span> <span m='4338180'>symmetric.</span> <span
  m='4339650'>All</span> <span m='4339830'>right?</span> </p><p><span
  m='4340680'>The</span> <span m='4340810'>proof</span> <span
  m='4341160'>was</span> <span m='4341300'>very</span> <span
  m='4341560'>similar,</span> <span m='4342370'>so</span> <span
  m='4342510'>the</span> <span m='4342600'>nice</span> <span
  m='4342830'>thing</span> <span m='4342970'>is</span> <span
  m='4343090'>you've</span> <span m='4343290'>only</span> <span
  m='4343345'>got</span> <span m='4343400'>to</span> <span
  m='4343460'>remember</span> <span m='4344400'>the</span> <span
  m='4344510'>bounds</span> <span m='4344850'>are</span> <span
  m='4344900'>now</span> <span m='4345120'>simple</span> <span
  m='4345710'>for</span> <span m='4345870'>any</span> <span
  m='4346060'>sum</span> <span m='4346440'>as</span> <span
  m='4346550'>long</span> <span m='4346720'>as</span> <span
  m='4346840'>an</span> <span m='4346970'>increasing</span> <span
  m='4347490'>or</span> <span m='4347530'>decreasing,</span> <span
  m='4348550'>it's</span> <span m='4348730'>the</span> <span
  m='4348820'>same</span> <span m='4349120'>as</span> <span
  m='4349230'>the</span> <span m='4349360'>integral.</span> <span
  m='4350490'>The</span> <span m='4350620'>lower</span> <span
  m='4350920'>bound</span> <span m='4351260'>is</span> <span
  m='4351360'>the</span> <span m='4351440'>smaller</span> <span
  m='4352860'>of</span> <span m='4353010'>the</span> <span
  m='4353070'>first</span> <span m='4353370'>and</span> <span
  m='4353460'>last</span> <span m='4353670'>term,</span> <span
  m='4353920'>and</span> <span m='4353965'>the</span> <span
  m='4354010'>upper</span> <span m='4354150'>bounds</span> <span
  m='4354420'>are</span> <span m='4354480'>larger</span> <span
  m='4354900'>of</span> <span m='4354970'>the</span> <span
  m='4355040'>first</span> <span m='4355330'>and</span> <span
  m='4355420'>last</span> <span m='4355680'>term.</span> <span
  m='4356650'>Very</span> <span m='4357070'>easy</span> <span
  m='4357400'>to</span> <span m='4357490'>remember.</span> <span
  m='4357930'>Probably</span> <span m='4358180'>don't</span> <span
  m='4358260'>even</span> <span m='4358340'>need</span> <span
  m='4358550'>the</span> <span m='4358610'>crib</span> <span
  m='4358810'>sheet</span> <span m='4359040'>for</span> <span
  m='4359240'>it,</span> <span m='4359770'>although</span> <span
  m='4360080'>to</span> <span m='4360170'>be</span> <span
  m='4360260'>safe,</span> <span m='4361481'>want</span> <span
  m='4361890'>to</span> <span m='4362368'>write</span> <span
  m='4362846'>that</span> <span m='4363324'>down.</span> <span
  m='4366200'>So</span> <span m='4366310'>now</span> <span
  m='4366650'>it's</span> <span m='4366780'>easy</span> <span
  m='4367050'>to</span> <span m='4367120'>compute</span> <span
  m='4368520'>good</span> <span m='4368810'>bounds</span> <span
  m='4369340'>on</span> <span m='4369520'>the</span> <span
  m='4369600'>sum</span> <span m='4370060'>of</span> <span
  m='4370340'>the</span> <span m='4370560'>inverse</span> <span
  m='4371055'>square</span> <span m='4371302'>roots.</span> <span
  m='4382020'>Any</span> <span m='4382190'>questions</span> <span
  m='4383390'>there</span> <span m='4383570'>before</span> <span
  m='4383880'>I</span> <span m='4383980'>go</span> <span m='4386450'>do</span>
  <span m='4386650'>it?</span> </p><p><span m='4388530'>So</span> <span
  m='4388880'>let's</span> <span m='4389100'>take</span> <span
  m='4389270'>the</span> <span m='4389340'>case</span> <span
  m='4389770'>where</span> <span m='4390000'>we're</span> <span
  m='4390120'>summing</span> <span m='4391170'>1</span> <span
  m='4391440'>over</span> <span m='4391660'>square</span> <span
  m='4391900'>root</span> <span m='4392010'>of</span> <span
  m='4392140'>i.</span> <span m='4395360'>So</span> <span m='4395820'>we</span>
  <span m='4395910'>compute</span> <span m='4396240'>the</span> <span
  m='4396430'>integral</span> <span m='4398640'>of</span> <span
  m='4398840'>1</span> <span m='4399050'>over</span> <span
  m='4399220'>square</span> <span m='4399450'>root</span> <span
  m='4399570'>of</span> <span m='4399660'>x</span> <span m='4400630'>dx.</span>
  <span m='4402970'>That</span> <span m='4403220'>equals</span> <span
  m='4403810'>the</span> <span m='4403890'>square</span> <span
  m='4404130'>root</span> <span m='4404250'>of</span> <span m='4404360'>x</span>
  <span m='4404650'>over</span> <span m='4404940'>1/2,</span> <span
  m='4406530'>evaluated</span> <span m='4407130'>at</span> <span
  m='4407250'>n</span> <span m='4407445'>and</span> <span m='4407640'>1.</span>
  <span m='4409500'>That</span> <span m='4409740'>equals</span> <span
  m='4410610'>2</span> <span m='4411210'>square</span> <span
  m='4411600'>root</span> <span m='4411665'>of</span> <span m='4411730'>n</span>
  <span m='4412140'>minus</span> <span m='4412520'>1,</span> <span
  m='4413650'>or</span> <span m='4413840'>two</span> <span
  m='4414160'>square</span> <span m='4414280'>root</span> <span
  m='4414400'>of</span> <span m='4414520'>n</span> <span
  m='4415930'>minus</span> <span m='4416190'>2,</span> <span
  m='4418300'>and</span> <span m='4418620'>now</span> <span
  m='4418910'>we</span> <span m='4419040'>can</span> <span
  m='4419510'>bound</span> <span m='4420030'>the</span> <span
  m='4420120'>sum.</span> <span m='4428650'>The</span> <span
  m='4428780'>upper</span> <span m='4428960'>bound</span> <span
  m='4429440'>is</span> <span m='4430020'>f</span> <span m='4430240'>of</span>
  <span m='4430350'>1</span> <span m='4430960'>plus</span> <span
  m='4432280'>the</span> <span m='4432420'>integral.</span> <span
  m='4434380'>The</span> <span m='4434480'>lower</span> <span
  m='4434780'>bound</span> <span m='4435940'>is</span> <span
  m='4436570'>f</span> <span m='4436780'>of</span> <span m='4436820'>n</span>
  <span m='4438140'>plus</span> <span m='4438460'>the</span> <span
  m='4438550'>integral.</span> <span m='4442420'>What</span> <span
  m='4442670'>is</span> <span m='4443010'>f</span> <span m='4443163'>of</span>
  <span m='4443316'>1?</span> <span m='4445770'>One?</span> <span
  m='4448070'>One</span> <span m='4448140'>over</span> <span
  m='4448183'>the</span> <span m='4448226'>square</span> <span
  m='4448270'>root</span> <span m='4448490'>of</span> <span m='4448570'>1</span>
  <span m='4448770'>is</span> <span m='4448890'>1.</span> <span
  m='4449530'>What</span> <span m='4449760'>is</span> <span m='4449980'>f</span>
  <span m='4450133'>of</span> <span m='4450286'>n?</span> <span
  m='4454120'>One</span> <span m='4454380'>over</span> <span
  m='4454550'>the</span> <span m='4454630'>square</span> <span
  m='4454870'>root</span> <span m='4454980'>of</span> <span
  m='4455100'>n.</span> <span m='4455400'>Small.</span> </p><p><span
  m='4457350'>So</span> <span m='4457480'>these</span> <span
  m='4457750'>bounds</span> <span m='4458110'>are</span> <span
  m='4458170'>pretty</span> <span m='4458550'>close</span> <span
  m='4458990'>here,</span> <span m='4459250'>right?</span> <span
  m='4460290'>In</span> <span m='4460400'>fact,</span> <span
  m='4460730'>this</span> <span m='4460950'>gets</span> <span
  m='4461160'>really</span> <span m='4461470'>tiny</span> <span
  m='4461820'>as</span> <span m='4461910'>n</span> <span m='4462080'>gets</span>
  <span m='4462280'>big,</span> <span m='4462570'>so</span> <span
  m='4462700'>I'm</span> <span m='4462790'>just</span> <span
  m='4462930'>going</span> <span m='4463050'>to</span> <span
  m='4463110'>replace</span> <span m='4463520'>this</span> <span
  m='4463730'>with</span> <span m='4464120'>2</span> <span
  m='4464330'>square</span> <span m='4464480'>root</span> <span
  m='4464630'>of</span> <span m='4464785'>n</span> <span
  m='4464940'>minus</span> <span m='4465290'>2</span> <span
  m='4465590'>and</span> <span m='4465690'>make</span> <span
  m='4465840'>it</span> <span m='4465910'>a</span> <span
  m='4465940'>strict</span> <span m='4466320'>lower</span> <span
  m='4466570'>bound,</span> <span m='4467880'>and</span> <span
  m='4468100'>this--</span> <span m='4469450'>cancel</span> <span
  m='4469870'>there--</span> <span m='4470020'>I</span> <span
  m='4470185'>get</span> <span m='4470350'>2</span> <span
  m='4470590'>square</span> <span m='4470970'>root</span> <span
  m='4471015'>of</span> <span m='4471060'>n</span> <span
  m='4472110'>minus</span> <span m='4472500'>1.</span> <span
  m='4474350'>Wow,</span> <span m='4474740'>these</span> <span
  m='4475140'>bounds</span> <span m='4475430'>are</span> <span
  m='4475480'>great.</span> <span m='4476050'>They're</span> <span
  m='4476190'>within</span> <span m='4476430'>one</span> <span
  m='4478040'>for</span> <span m='4478270'>all</span> <span
  m='4478540'>n.</span> <span m='4480280'>That's</span> <span
  m='4480580'>really</span> <span m='4480810'>good.</span> </p><p><span
  m='4483260'>So</span> <span m='4484240'>we</span> <span m='4484500'>can</span>
  <span m='4484710'>rewrite</span> <span m='4485220'>this</span> <span
  m='4485650'>in</span> <span m='4485750'>terms</span> <span
  m='4486080'>of</span> <span m='4487430'>what</span> <span
  m='4487840'>really</span> <span m='4488080'>matters.</span> <span
  m='4488570'>What</span> <span m='4489030'>really</span> <span
  m='4489290'>matters</span> <span m='4489680'>in</span> <span
  m='4489750'>these</span> <span m='4489930'>bounds?</span> <span
  m='4492510'>How</span> <span m='4492750'>fast</span> <span
  m='4493140'>is</span> <span m='4493240'>this</span> <span
  m='4493410'>function</span> <span m='4493780'>growing?</span> </p><p><span
  m='4494560'>AUDIENCE:</span> <span m='4494880'>2</span> <span
  m='4494986'>root</span> <span m='4495093'>n.</span> </p><p><span
  m='4495420'>PROFESSOR: 2</span> <span m='4495570'>root</span> <span
  m='4495770'>n.</span> <span m='4496000'>That's</span> <span
  m='4496220'>what</span> <span m='4496330'>really</span> <span
  m='4496560'>matters,</span> <span m='4496990'>so</span> <span
  m='4497165'>let's</span> <span m='4497340'>write</span> <span
  m='4497503'>that</span> <span m='4497666'>down.</span> <span
  m='4506020'>So</span> <span m='4506310'>this</span> <span
  m='4506490'>says</span> <span m='4506960'>that</span> <span
  m='4507360'>the</span> <span m='4507760'>sum</span> <span m='4508310'>i</span>
  <span m='4508620'>equals</span> <span m='4508760'>1</span> <span
  m='4509133'>to</span> <span m='4509319'>n</span> <span m='4509506'>of</span>
  <span m='4509693'>1</span> <span m='4509880'>over</span> <span
  m='4510140'>square</span> <span m='4510470'>root</span> <span
  m='4510555'>i</span> <span m='4513470'>equals</span> <span
  m='4514780'>2</span> <span m='4515180'>square</span> <span
  m='4515530'>root</span> <span m='4515585'>of</span> <span
  m='4515640'>n--</span> <span m='4516692'>we</span> <span
  m='4516926'>have</span> <span m='4517160'>a</span> <span
  m='4517400'>minus</span> <span m='4517880'>delta</span> <span
  m='4518510'>n,</span> <span m='4519770'>where</span> <span
  m='4520440'>delta</span> <span m='4521090'>is</span> <span
  m='4521290'>between</span> <span m='4523660'>1</span> <span
  m='4524170'>and</span> <span m='4524340'>2.</span> <span
  m='4526990'>And</span> <span m='4527170'>so</span> <span m='4527460'>if</span>
  <span m='4527570'>I</span> <span m='4527640'>use</span> <span
  m='4527930'>the</span> <span m='4528010'>tilde</span> <span
  m='4528370'>notation,</span> <span m='4533600'>what</span> <span
  m='4533820'>would</span> <span m='4533920'>I</span> <span
  m='4533990'>write</span> <span m='4534250'>down</span> <span
  m='4534520'>here</span> <span m='4534690'>for</span> <span
  m='4534810'>the</span> <span m='4534880'>tilde?</span> <span
  m='4536210'>Past</span> <span m='4536520'>the</span> <span
  m='4536770'>tilde?</span> <span m='4539180'>I</span> <span
  m='4539280'>don't</span> <span m='4539400'>want</span> <span
  m='4539530'>to</span> <span m='4539590'>mess--</span> </p><p><span
  m='4539970'>AUDIENCE: Tilde.</span> </p><p><span m='4540110'>PROFESSOR: 
  --I</span> <span m='4540410'>don't</span> <span m='4540640'>want</span> <span
  m='4540705'>to</span> <span m='4540770'>keep</span> <span
  m='4540806'>track</span> <span m='4540843'>of</span> <span
  m='4540880'>all</span> <span m='4541026'>the</span> <span
  m='4541173'>delta</span> <span m='4541320'>stuff</span> <span
  m='4541670'>as</span> <span m='4541770'>n</span> <span m='4541940'>gets</span>
  <span m='4542070'>big.</span> </p><p><span m='4542640'>AUDIENCE:  2</span>
  <span m='4542900'>root</span> <span m='4542980'>n.</span> </p><p><span
  m='4543390'>PROFESSOR: 2</span> <span m='4543520'>root</span> <span
  m='4543645'>n,</span> <span m='4545720'>because</span> <span
  m='4547320'>this</span> <span m='4547610'>term</span> <span
  m='4548420'>over</span> <span m='4548680'>that</span> <span
  m='4549390'>goes</span> <span m='4549650'>to</span> <span m='4549750'>0</span>
  <span m='4550260'>as</span> <span m='4550390'>n</span> <span
  m='4550880'>gets</span> <span m='4551130'>large,</span> <span
  m='4552010'>so</span> <span m='4552160'>let's</span> <span
  m='4552310'>just</span> <span m='4552550'>check</span> <span
  m='4552820'>that.</span> <span m='4556630'>So</span> <span
  m='4556790'>we</span> <span m='4556880'>take</span> <span
  m='4557170'>the</span> <span m='4557260'>limit</span> <span
  m='4557980'>as</span> <span m='4558200'>n</span> <span m='4558370'>goes</span>
  <span m='4558620'>to</span> <span m='4558740'>infinity</span> <span
  m='4560360'>of</span> <span m='4560840'>2</span> <span m='4561240'>root</span>
  <span m='4561530'>n</span> <span m='4562300'>minus</span> <span
  m='4562670'>delta</span> <span m='4563030'>n</span> <span
  m='4564600'>over</span> <span m='4565000'>2</span> <span
  m='4565260'>root</span> <span m='4565470'>n.</span> <span
  m='4566235'>I'm</span> <span m='4566610'>just</span> <span
  m='4566880'>checking</span> <span m='4567190'>the</span> <span
  m='4567270'>definition</span> <span m='4567810'>now.</span> <span
  m='4568150'>That's</span> <span m='4568310'>what</span> <span
  m='4568400'>the</span> <span m='4568470'>definition</span> <span
  m='4568950'>would</span> <span m='4569060'>be.</span> <span
  m='4571020'>Equals</span> <span m='4571860'>1</span> <span
  m='4573990'>minus</span> <span m='4574550'>the</span> <span
  m='4574640'>limit</span> <span m='4576800'>as</span> <span
  m='4576980'>n</span> <span m='4577150'>goes</span> <span m='4577380'>to</span>
  <span m='4577490'>infinity</span> <span m='4578410'>of</span> <span
  m='4578620'>2</span> <span m='4579190'>over</span> <span m='4579520'>2</span>
  <span m='4579800'>root</span> <span m='4580030'>n.</span> <span
  m='4581200'>This</span> <span m='4581590'>is</span> <span
  m='4581760'>0.</span> <span m='4583250'>So</span> <span m='4583450'>it</span>
  <span m='4583520'>equals</span> <span m='4583840'>1.</span> <span
  m='4585750'>And</span> <span m='4585880'>so</span> <span
  m='4585980'>now</span> <span m='4586190'>you</span> <span
  m='4586340'>know</span> <span m='4586770'>that</span> <span
  m='4587970'>the</span> <span m='4588140'>sum</span> <span
  m='4588450'>of</span> <span m='4588510'>the</span> <span
  m='4588570'>first</span> <span m='4588940'>n</span> <span
  m='4589410'>inverse</span> <span m='4589740'>square</span> <span
  m='4589980'>roots</span> <span m='4590390'>grows</span> <span
  m='4591110'>as</span> <span m='4591340'>2</span> <span m='4591510'>root</span>
  <span m='4591680'>n,</span> <span m='4592120'>which</span> <span
  m='4592310'>is</span> <span m='4592430'>the</span> <span
  m='4592520'>integral.</span> <span m='4592900'>Yeah.</span> </p><p><span
  m='4593357'>AUDIENCE:</span> <span m='4593814'>[INAUDIBLE]</span> <span
  m='4594271'>dropped</span> <span m='4594500'>off</span> <span
  m='4594730'>the</span> <span m='4594870'>lower</span> <span
  m='4595233'>bound</span> <span m='4595960'>that</span> <span
  m='4596316'>f</span> <span m='4596434'>of</span> <span m='4596553'>n</span>
  <span m='4597030'>was</span> <span m='4597210'>1</span> <span
  m='4597365'>over</span> <span m='4597520'>root</span> <span
  m='4597676'>n?</span> </p><p><span m='4598610'>PROFESSOR: Yeah,</span> <span
  m='4599160'>I</span> <span m='4599330'>dropped</span> <span
  m='4599820'>it</span> <span m='4599900'>off,</span> <span
  m='4600720'>because</span> <span m='4600900'>it</span> <span
  m='4601030'>was</span> <span m='4601670'>so</span> <span
  m='4601970'>tiny</span> <span m='4602400'>and</span> <span
  m='4602520'>going</span> <span m='4602640'>to</span> <span
  m='4602710'>zero,</span> <span m='4603140'>I</span> <span
  m='4603210'>just</span> <span m='4603470'>made</span> <span
  m='4603623'>a</span> <span m='4603776'>strict</span> <span
  m='4603930'>less</span> <span m='4604270'>than.</span> <span
  m='4605150'>In</span> <span m='4605250'>fact,</span> <span
  m='4605590'>yes.</span> <span m='4605850'>I</span> <span
  m='4605940'>don't</span> <span m='4606170'>hurt</span> <span
  m='4606490'>myself</span> <span m='4606950'>by</span> <span
  m='4607990'>dropping</span> <span m='4608480'>it</span> <span
  m='4608580'>off.</span> <span m='4608810'>In</span> <span
  m='4608880'>fact,</span> <span m='4609100'>the</span> <span
  m='4609170'>lower</span> <span m='4609420'>bound</span> <span
  m='4609680'>was</span> <span m='4609780'>a</span> <span
  m='4609840'>little</span> <span m='4610100'>bit--</span> <span
  m='4611040'>I</span> <span m='4611170'>made</span> <span m='4611350'>a</span>
  <span m='4611400'>little</span> <span m='4611680'>weaker</span> <span
  m='4612020'>lower</span> <span m='4612260'>bound.</span> <span
  m='4613210'>So</span> <span m='4613360'>this</span> <span
  m='4613560'>is</span> <span m='4613640'>still</span> <span
  m='4613880'>true.</span> <span m='4615110'>I</span> <span
  m='4615220'>just--</span> <span m='4615460'>it</span> <span
  m='4615570'>wasn't</span> <span m='4615830'>as</span> <span
  m='4615920'>tight</span> <span m='4616130'>as</span> <span
  m='4616230'>it</span> <span m='4616320'>used</span> <span
  m='4616520'>to</span> <span m='4616580'>be,</span> <span m='4616710'>so</span>
  <span m='4616860'>I</span> <span m='4616920'>could</span> <span
  m='4617250'>keep</span> <span m='4618290'>it</span> <span
  m='4618360'>around.</span> </p><p><span m='4619980'>Yeah,</span> <span
  m='4620240'>it</span> <span m='4620285'>doesn't</span> <span
  m='4620330'>hurt</span> <span m='4620470'>to</span> <span
  m='4620550'>keep</span> <span m='4620750'>it</span> <span
  m='4620820'>around,</span> <span m='4621140'>then</span> <span
  m='4621250'>it's</span> <span m='4621380'>a</span> <span
  m='4621460'>less</span> <span m='4621630'>than</span> <span
  m='4621770'>or</span> <span m='4621860'>equal</span> <span
  m='4622120'>there.</span> <span m='4624280'>And</span> <span
  m='4624440'>now</span> <span m='4624710'>this</span> <span
  m='4624920'>would</span> <span m='4625070'>be</span> <span
  m='4630780'>something</span> <span m='4631020'>like</span> <span
  m='4631170'>that.</span> <span m='4631430'>So</span> <span
  m='4631520'>I</span> <span m='4631560'>could</span> <span
  m='4631770'>keep</span> <span m='4631950'>it</span> <span
  m='4632020'>around,</span> <span m='4632240'>but</span> <span
  m='4632330'>I'm</span> <span m='4632390'>going</span> <span
  m='4632510'>to</span> <span m='4632570'>get</span> <span
  m='4632730'>rid</span> <span m='4632980'>of</span> <span m='4633050'>it</span>
  <span m='4633140'>anyway,</span> <span m='4633430'>because</span> <span
  m='4633580'>I'm</span> <span m='4633610'>going</span> <span
  m='4633730'>to</span> <span m='4633790'>go</span> <span m='4633900'>to</span>
  <span m='4633970'>the</span> <span m='4634060'>tilde</span> <span
  m='4634350'>notation,</span> <span m='4636430'>and</span> <span
  m='4636830'>as</span> <span m='4637210'>n</span> <span m='4637370'>gets</span>
  <span m='4637550'>big,</span> <span m='4637800'>this</span> <span
  m='4638000'>is</span> <span m='4638110'>really</span> <span
  m='4638370'>tiny.</span> <span m='4639880'>So</span> <span
  m='4639980'>in</span> <span m='4640040'>this</span> <span
  m='4640210'>case,</span> <span m='4640450'>the</span> <span
  m='4640520'>bounds</span> <span m='4640870'>are</span> <span
  m='4640910'>great.</span> <span m='4641460'>You</span> <span
  m='4641570'>can</span> <span m='4641850'>nail</span> <span
  m='4642230'>it</span> <span m='4642340'>pretty</span> <span
  m='4642580'>much</span> <span m='4643410'>right</span> <span
  m='4643700'>on.</span> <span m='4646540'>Yeah.</span> </p><p><span
  m='4647290'>AUDIENCE:</span> <span m='4647790'>You</span> <span
  m='4648290'>said</span> <span m='4648456'>one over</span> <span
  m='4648623'>n</span> <span m='4648790'>still there,</span> <span
  m='4650290'>the</span> <span m='4650540'>number</span> <span
  m='4650790'>is</span> <span m='4650956'>bigger</span> <span
  m='4651123'>than</span> <span m='4651178'>it</span> <span
  m='4651234'>would</span> <span m='4651290'>normally</span> <span
  m='4651790'>be,</span> <span m='4652290'>so</span> <span
  m='4652515'>when</span> <span m='4652740'>you</span> <span
  m='4653190'>take</span> <span m='4653640'>it</span> <span
  m='4653752'>out,</span> <span m='4653865'>it</span> <span
  m='4653977'>becomes</span> <span m='4654090'>smaller,</span> <span
  m='4654540'>so</span> <span m='4654990'>how</span> <span
  m='4655890'>could</span> <span m='4656340'>you</span> <span
  m='4656562'>go</span> <span m='4656785'>to</span> <span m='4656896'>a</span>
  <span m='4657007'>less</span> <span m='4657118'>than</span> <span
  m='4657230'>[INAUDIBLE]?</span> </p><p><span m='4659460'>PROFESSOR:
  Well,</span> <span m='4659620'>you're</span> <span m='4659730'>saying</span>
  <span m='4659960'>you</span> <span m='4660030'>don't</span> <span
  m='4660230'>like</span> <span m='4660510'>the</span> <span
  m='4660580'>fact</span> <span m='4660800'>I</span> <span
  m='4660920'>dropped</span> <span m='4661210'>it</span> <span
  m='4661280'>here?</span> </p><p><span m='4662246'>AUDIENCE: Yes.</span> <span
  m='4662729'>When</span> <span m='4662970'>you</span> <span
  m='4663212'>drop</span> <span m='4663453'>it,</span> <span
  m='4663695'>why</span> <span m='4663791'>do</span> <span
  m='4663888'>you</span> <span m='4663984'>go</span> <span m='4664081'>to</span>
  <span m='4664178'>a</span> <span m='4664339'>less</span> <span
  m='4664500'>than</span> <span m='4664661'>instead</span> <span
  m='4664902'>of</span> <span m='4665144'>[INAUDIBLE]?</span> </p><p><span
  m='4665627'>PROFESSOR: Oh,</span> <span m='4666110'>because</span> <span
  m='4666370'>I've</span> <span m='4667140'>got</span> <span
  m='4667330'>a</span> <span m='4669220'>bigger</span> <span
  m='4669460'>bound</span> <span m='4669890'>that</span> <span
  m='4670010'>I</span> <span m='4670080'>made</span> <span
  m='4670340'>less</span> <span m='4671610'>when</span> <span
  m='4671770'>I</span> <span m='4671850'>dropped</span> <span
  m='4672250'>it.</span> <span m='4672480'>I</span> <span
  m='4672600'>took</span> <span m='4672830'>something</span> <span
  m='4673110'>away,</span> <span m='4673770'>so</span> <span
  m='4673950'>I</span> <span m='4674050'>know</span> <span m='4674350'>I</span>
  <span m='4674430'>could</span> <span m='4674610'>never</span> <span
  m='4674860'>equal</span> <span m='4675300'>this,</span> <span
  m='4675550'>because</span> <span m='4675710'>I</span> <span
  m='4675790'>know</span> <span m='4675950'>it's</span> <span
  m='4676090'>bigger</span> <span m='4676350'>than</span> <span
  m='4676500'>this.</span> <span m='4678760'>I</span> <span
  m='4678900'>know</span> <span m='4679090'>that</span> <span
  m='4679210'>the</span> <span m='4679310'>real</span> <span
  m='4679560'>answer</span> <span m='4679820'>has</span> <span
  m='4680030'>to</span> <span m='4680090'>be</span> <span m='4680170'>at</span>
  <span m='4680260'>least</span> <span m='4680540'>this</span> <span
  m='4680740'>big,</span> <span m='4681710'>and</span> <span
  m='4681880'>so</span> <span m='4682100'>it</span> <span m='4682210'>has</span>
  <span m='4682420'>to</span> <span m='4682500'>be</span> <span
  m='4682610'>bigger</span> <span m='4683130'>than</span> <span
  m='4683300'>something</span> <span m='4683600'>smaller.</span> <span
  m='4684990'>That's</span> <span m='4685140'>why</span> <span
  m='4685320'>I</span> <span m='4685470'>did</span> <span m='4685620'>it.</span>
  <span m='4689960'>Any</span> <span m='4690190'>other</span> <span
  m='4690360'>questions?</span> <span m='4693240'>We'll</span> <span
  m='4693380'>get</span> <span m='4693550'>more</span> <span
  m='4693720'>practice</span> <span m='4694220'>tomorrow</span> <span
  m='4694740'>and</span> <span m='4694880'>next</span> <span
  m='4695180'>time</span> <span m='4695280'>with</span> <span
  m='4695380'>this</span> <span m='4695480'>stuff.</span> </p>
embedded_media:
  - uid: aa11a32c2470e1f08abb0738fd168291
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: fAeShezAGLE
  - uid: 6319fe3bd0b0ecae1c072e1079565b0f
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/fAeShezAGLE/default.jpg'
  - uid: c2ac112a4615b033c26f441b00b360e5
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-12-sums/id503873536?i=110644979
  - uid: 05dcecde20a0e1ca51a6c8ab1a6e04e9
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MIT6.042JF10/MIT6_042JF10_lec12_300k.mp4'
  - uid: b885a8041a64ebaa5058da2e2c98f711
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: fAeShezAGLE
  - uid: 4dac2e484bc076380eda2458b4fd2fb5
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: fAeShezAGLE.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-042j-mathematics-for-computer-science-fall-2010/4dac2e484bc076380eda2458b4fd2fb5_fAeShezAGLE.srt
  - uid: 35c5b44faacb08f9bcd51cdf5d22506e
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: fAeShezAGLE.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-042j-mathematics-for-computer-science-fall-2010/35c5b44faacb08f9bcd51cdf5d22506e_fAeShezAGLE.pdf
  - uid: 1f686d0bf4b0ed8b196dcd97b989a885
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 7ac98b194790dbac97be952e67a2924b
    parent_uid: 3ab159732cf8753652d2c1ff154f1a4a
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: 6-042j-mathematics-for-computer-science-fall-2010
type: course
layout: video
---