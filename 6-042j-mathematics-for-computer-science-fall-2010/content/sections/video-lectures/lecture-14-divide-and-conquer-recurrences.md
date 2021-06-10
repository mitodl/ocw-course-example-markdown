---
order_index: null
title: 'Lecture 14: Divide and Conquer Recurrences'
template_type: Tabbed
uid: 098ba0041cbb6df383f0decb5057952b
parent_uid: 7e5e792254d703550b60881541fa6160
technical_location: >-
  https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2010/video-lectures/lecture-14-divide-and-conquer-recurrences
short_url: lecture-14-divide-and-conquer-recurrences
inline_embed_id: '73619078lecture14:divideandconquerrecurrences14180388'
about_this_resource_text: >-
  <p><strong>Description:</strong> Introduces the concept of recursion applied
  to various recurrence problems, such as the Towers of Hanoi and the Merge Sort
  algorithm, as well as their asymptotic analysis using the Akra&ndash;Bazzi
  method.</p> <p><strong>Speaker:</strong> Tom Leighton</p>
related_resources_text: ''
transcript: >-
  <p><span m='360'>The</span> <span m='490'>following</span> <span
  m='940'>content</span> <span m='1530'>is</span> <span m='1650'>provided</span>
  <span m='2100'>under</span> <span m='2350'>a</span> <span
  m='2400'>Creative</span> <span m='2800'>Commons</span> <span
  m='3230'>license.</span> <span m='4340'>Your</span> <span
  m='4510'>support</span> <span m='5050'>will</span> <span m='5200'>help</span>
  <span m='5430'>MIT</span> <span m='5870'>OpenCourseWare</span> <span
  m='6660'>continue</span> <span m='7170'>to</span> <span m='7290'>offer</span>
  <span m='7690'>high</span> <span m='7910'>quality</span> <span
  m='8420'>educational</span> <span m='9060'>resources</span> <span
  m='9640'>for</span> <span m='9820'>free.</span> <span m='11020'>To</span>
  <span m='11040'>make</span> <span m='11250'>a</span> <span
  m='11290'>donation</span> <span m='11990'>or</span> <span
  m='12230'>view</span> <span m='12680'>additional</span> <span
  m='13120'>materials</span> <span m='13640'>from</span> <span
  m='13830'>hundreds</span> <span m='14240'>of</span> <span m='14360'>MIT</span>
  <span m='14760'>courses,</span> <span m='15840'>visit</span> <span
  m='16100'>MIT</span> <span m='16510'>OpenCourseWare</span> <span
  m='17560'>at</span> <span m='17750'>ocw.mit.edu.</span> </p><p><span
  m='22870'>TOM LEIGHTON: This</span> <span m='23070'>week</span> <span
  m='24010'>we're</span> <span m='24140'>going</span> <span m='24260'>to</span>
  <span m='24350'>talk</span> <span m='24670'>about</span> <span
  m='24950'>recurrences,</span> <span m='26010'>how</span> <span
  m='26180'>to</span> <span m='26280'>set</span> <span m='26540'>them</span>
  <span m='26680'>up,</span> <span m='26940'>how</span> <span
  m='27100'>to</span> <span m='27190'>model</span> <span m='27590'>a</span>
  <span m='27660'>problem</span> <span m='28460'>as</span> <span
  m='28650'>a</span> <span m='28710'>recurrent</span> <span
  m='29120'>problem,</span> <span m='29570'>and</span> <span
  m='29660'>then</span> <span m='29990'>how</span> <span m='30140'>to</span>
  <span m='30250'>solve</span> <span m='30610'>them.</span> <span
  m='31950'>This</span> <span m='32200'>stuff</span> <span m='32470'>is</span>
  <span m='32659'>really</span> <span m='33100'>useful</span> <span
  m='33520'>when</span> <span m='33650'>you</span> <span m='33720'>get</span>
  <span m='33910'>into</span> <span m='34180'>algorithm</span> <span
  m='34710'>design</span> <span m='35160'>and</span> <span
  m='35260'>algorithm</span> <span m='35710'>analysis.</span> <span
  m='36770'>6006</span> <span m='37950'>and</span> <span m='38200'>6046,</span>
  <span m='39270'>we</span> <span m='39380'>you</span> <span
  m='39440'>use</span> <span m='39600'>this</span> <span m='39750'>stuff</span>
  <span m='40080'>a</span> <span m='40170'>lot.</span> </p><p><span
  m='41060'>We're</span> <span m='41370'>going</span> <span m='41490'>to</span>
  <span m='41550'>start</span> <span m='41880'>with</span> <span
  m='42010'>a</span> <span m='42050'>very</span> <span m='42310'>famous</span>
  <span m='43140'>recurrent</span> <span m='43600'>problem</span> <span
  m='44020'>known</span> <span m='44290'>as</span> <span m='44410'>the</span>
  <span m='44490'>Towers</span> <span m='44950'>of</span> <span
  m='45110'>Hanoi</span> <span m='45480'>problem.</span> <span
  m='46430'>And</span> <span m='46590'>I'm</span> <span
  m='46740'>guessing</span> <span m='47090'>that</span> <span
  m='47230'>many</span> <span m='47640'>of</span> <span m='47710'>you</span>
  <span m='47920'>have</span> <span m='48130'>seen</span> <span
  m='48480'>this</span> <span m='48650'>problem</span> <span m='48970'>in</span>
  <span m='49030'>one</span> <span m='49250'>form</span> <span
  m='49480'>or</span> <span m='49520'>another.</span> <span m='51300'>In</span>
  <span m='51520'>the</span> <span m='51690'>Tower</span> <span
  m='52050'>of</span> <span m='52120'>Hanoi</span> <span
  m='52490'>problem,</span> <span m='53860'>you've</span> <span
  m='54030'>got</span> <span m='54350'>three</span> <span m='54660'>pegs</span>
  <span m='56020'>and</span> <span m='56540'>n</span> <span
  m='57270'>disks,</span> <span m='58190'>these</span> <span
  m='58440'>little</span> <span m='58630'>guys</span> <span
  m='58970'>here.</span> <span m='60260'>All</span> <span
  m='60490'>different</span> <span m='60790'>sizes.</span> <span
  m='62040'>And</span> <span m='62760'>the</span> <span m='63220'>object</span>
  <span m='63870'>is</span> <span m='64160'>to</span> <span
  m='64849'>start</span> <span m='65230'>with</span> <span m='65370'>a</span>
  <span m='65420'>stack</span> <span m='65980'>like</span> <span
  m='66260'>this</span> <span m='67340'>and</span> <span m='67600'>move</span>
  <span m='67940'>the</span> <span m='68020'>disks</span> <span
  m='68440'>around</span> <span m='69090'>so</span> <span m='69210'>they</span>
  <span m='69320'>wind</span> <span m='69760'>up</span> <span
  m='69990'>with</span> <span m='70750'>the</span> <span m='70870'>stack</span>
  <span m='71860'>on</span> <span m='72250'>another</span> <span
  m='72550'>disk.</span> </p><p><span m='73640'>Now,</span> <span
  m='73970'>the</span> <span m='74080'>rules</span> <span m='74490'>are</span>
  <span m='74790'>you</span> <span m='74900'>can</span> <span
  m='75050'>only</span> <span m='75280'>move</span> <span m='75510'>one</span>
  <span m='75900'>disk</span> <span m='76240'>at</span> <span m='76320'>a</span>
  <span m='76370'>time.</span> <span m='78750'>And</span> <span
  m='79020'>you</span> <span m='79090'>can</span> <span m='79250'>never</span>
  <span m='79550'>put</span> <span m='79750'>a</span> <span m='79810'>big</span>
  <span m='80160'>disk</span> <span m='81240'>over</span> <span
  m='81570'>a</span> <span m='81650'>little</span> <span m='81900'>disk.</span>
  <span m='82270'>So</span> <span m='82900'>that</span> <span
  m='83170'>you</span> <span m='83260'>can't</span> <span m='83560'>do.</span>
  <span m='84720'>So</span> <span m='84890'>that</span> <span
  m='85100'>would</span> <span m='85220'>have</span> <span m='85400'>to</span>
  <span m='85480'>go</span> <span m='85670'>there.</span> <span
  m='86900'>Then</span> <span m='87140'>you</span> <span m='87250'>could</span>
  <span m='87520'>do</span> <span m='87690'>this.</span> <span
  m='89200'>And</span> <span m='89530'>now</span> <span m='89730'>I've</span>
  <span m='89880'>gotten</span> <span m='91300'>the</span> <span
  m='91420'>top</span> <span m='91810'>two</span> <span m='92310'>moved</span>
  <span m='92640'>over</span> <span m='92870'>to</span> <span
  m='92950'>here.</span> <span m='94220'>And</span> <span m='94330'>the</span>
  <span m='94410'>goal</span> <span m='94840'>is</span> <span
  m='94950'>to</span> <span m='95030'>take</span> <span m='95280'>the</span>
  <span m='95360'>minimum</span> <span m='95790'>number</span> <span
  m='96110'>of</span> <span m='96210'>moves</span> <span m='97650'>to</span>
  <span m='97750'>get</span> <span m='97930'>the</span> <span
  m='98020'>whole</span> <span m='98280'>stack</span> <span
  m='99200'>moved</span> <span m='99500'>over</span> <span m='99730'>to</span>
  <span m='99830'>here,</span> <span m='100980'>and to</span> <span
  m='101240'>even</span> <span m='101540'>figure</span> <span
  m='101840'>out</span> <span m='102570'>if</span> <span
  m='102770'>that's</span> <span m='103210'>doable.</span> </p><p><span
  m='105010'>Now,</span> <span m='106720'>this</span> <span
  m='107000'>was</span> <span m='107680'>invented</span> <span
  m='109030'>by</span> <span m='109450'>a</span> <span m='109560'>famous</span>
  <span m='110060'>French</span> <span m='110560'>mathematician</span> <span
  m='111910'>named</span> <span m='112360'>Edward</span> <span
  m='112780'>Lucas</span> <span m='113510'>in</span> <span
  m='113670'>1883.</span> <span m='115470'>And</span> <span m='115720'>in</span>
  <span m='115800'>the</span> <span m='115930'>original</span> <span
  m='116690'>legend</span> <span m='117400'>around</span> <span
  m='117750'>this</span> <span m='117920'>puzzle,</span> <span
  m='118750'>there</span> <span m='118970'>were</span> <span
  m='119130'>64</span> <span m='120030'>disks.</span> <span
  m='120870'>This</span> <span m='121100'>one</span> <span m='121310'>has</span>
  <span m='121700'>just</span> <span m='122030'>seven</span> <span
  m='122350'>on</span> <span m='122510'>it.</span> <span m='123770'>And</span>
  <span m='125160'>the</span> <span m='125380'>story</span> <span
  m='125840'>was</span> <span m='126270'>at</span> <span m='126370'>the</span>
  <span m='126450'>beginning</span> <span m='126880'>of</span> <span
  m='126980'>time,</span> <span m='128030'>God</span> <span
  m='128430'>placed</span> <span m='129039'>the</span> <span
  m='129110'>64</span> <span m='129800'>disks</span> <span m='130660'>on</span>
  <span m='131500'>one</span> <span m='131870'>of</span> <span
  m='131990'>the</span> <span m='132220'>three</span> <span
  m='132630'>golden</span> <span m='133110'>pegs.</span> </p><p><span
  m='134390'>And</span> <span m='134610'>he</span> <span m='135160'>got</span>
  <span m='135360'>an</span> <span m='135540'>order</span> <span
  m='135920'>of</span> <span m='136030'>monks</span> <span
  m='136890'>whose</span> <span m='137840'>lifelong</span> <span
  m='138470'>mission</span> <span m='138900'>was</span> <span
  m='139090'>to</span> <span m='139190'>move</span> <span m='139990'>the</span>
  <span m='140110'>disks</span> <span m='140510'>one</span> <span
  m='140710'>at</span> <span m='140770'>a</span> <span m='140830'>time</span>
  <span m='141680'>so</span> <span m='141910'>at</span> <span
  m='142000'>the</span> <span m='142170'>end</span> <span m='142440'>all</span>
  <span m='142720'>64</span> <span m='143380'>disks</span> <span
  m='143750'>were</span> <span m='143970'>lined</span> <span
  m='144350'>up</span> <span m='144800'>on</span> <span m='145030'>an</span>
  <span m='145110'>adjacent</span> <span m='145590'>peg.</span> <span
  m='146550'>And</span> <span m='146950'>according</span> <span
  m='147300'>to</span> <span m='147380'>legend,</span> <span
  m='148100'>when</span> <span m='148380'>that</span> <span
  m='148580'>task</span> <span m='148990'>was</span> <span
  m='149140'>done</span> <span m='149990'>the</span> <span
  m='150870'>tower</span> <span m='151210'>would</span> <span
  m='151380'>crumble</span> <span m='152220'>and</span> <span
  m='152530'>the</span> <span m='152600'>world</span> <span
  m='152930'>would</span> <span m='153090'>end.</span> <span
  m='154540'>Sort</span> <span m='154810'>of</span> <span
  m='154880'>explains</span> <span m='155390'>why</span> <span
  m='156550'>monks</span> <span m='156990'>are</span> <span
  m='157240'>never</span> <span m='157520'>smiling,</span> <span
  m='158100'>because</span> <span m='158330'>they</span> <span
  m='158780'>work</span> <span m='159240'>forever</span> <span
  m='159750'>and</span> <span m='159870'>then</span> <span
  m='160135'>just</span> <span m='160400'>something</span> <span
  m='160860'>bad</span> <span m='161230'>happens.</span> </p><p><span
  m='162530'>Now,</span> <span m='163080'>the</span> <span
  m='163180'>question</span> <span m='163570'>we</span> <span
  m='163670'>want</span> <span m='163900'>to</span> <span m='164010'>be</span>
  <span m='164100'>able</span> <span m='164240'>to</span> <span
  m='164320'>answer</span> <span m='164830'>is,</span> <span
  m='165170'>how</span> <span m='165430'>long</span> <span
  m='166010'>till</span> <span m='166260'>the</span> <span
  m='166340'>world</span> <span m='166750'>ends?</span> <span
  m='168220'>So</span> <span m='169700'>we</span> <span m='169840'>can</span>
  <span m='170030'>start</span> <span m='170440'>with</span> <span
  m='170670'>a</span> <span m='170730'>simpler</span> <span
  m='171200'>version.</span> <span m='173300'>Say</span> <span
  m='175590'>let's</span> <span m='175770'>take</span> <span
  m='176010'>three</span> <span m='176450'>disks</span> <span
  m='177080'>and</span> <span m='177180'>start</span> <span
  m='177490'>with</span> <span m='177590'>that.</span> <span
  m='178940'>And</span> <span m='179060'>let's</span> <span
  m='179230'>see,</span> <span m='179940'>is</span> <span m='180280'>it</span>
  <span m='180370'>doable?</span> <span m='180890'>Well,</span> <span
  m='181100'>we</span> <span m='181220'>could.</span> <span
  m='182660'>That's</span> <span m='182910'>one,</span> <span
  m='184880'>that's</span> <span m='185190'>two,</span> <span
  m='187260'>three,</span> <span m='189480'>four,</span> <span
  m='191590'>five,</span> <span m='193520'>six,</span> <span
  m='195230'>seven.</span> </p><p><span m='196740'>So</span> <span
  m='196980'>it's</span> <span m='197100'>doable</span> <span
  m='197670'>with</span> <span m='197860'>three</span> <span
  m='198130'>disks.</span> <span m='198820'>And</span> <span
  m='199010'>we</span> <span m='199100'>took</span> <span
  m='199360'>seven</span> <span m='199730'>moves.</span> <span
  m='200180'>Maybe</span> <span m='200870'>there's</span> <span
  m='201060'>a</span> <span m='201120'>better</span> <span
  m='201380'>way,</span> <span m='201680'>and</span> <span
  m='201780'>that's</span> <span m='202220'>part</span> <span
  m='202470'>of</span> <span m='202540'>what</span> <span
  m='202690'>we'll</span> <span m='202810'>try</span> <span m='203020'>to</span>
  <span m='203340'>study</span> <span m='203720'>today.</span> <span
  m='205420'>In</span> <span m='205570'>fact,</span> <span
  m='206210'>what</span> <span m='206420'>we'd</span> <span
  m='206560'>like</span> <span m='206780'>to</span> <span m='206860'>know</span>
  <span m='207710'>is</span> <span m='209160'>how</span> <span
  m='209370'>many</span> <span m='209550'>moves</span> <span
  m='210060'>for</span> <span m='210440'>n</span> <span m='211040'>disks?</span>
  <span m='214820'>And</span> <span m='215050'>is</span> <span
  m='215190'>it</span> <span m='215280'>even</span> <span
  m='215490'>finite?</span> <span m='216470'>So</span> <span
  m='216640'>we're</span> <span m='216710'>going</span> <span
  m='216830'>to</span> <span m='216960'>define</span> <span m='217220'>t</span>
  <span m='217480'>sub</span> <span m='217620'>n</span> <span
  m='219000'>to</span> <span m='219110'>be</span> <span m='219260'>the</span>
  <span m='219420'>minimum</span> <span m='219980'>number</span> <span
  m='222330'>of</span> <span m='222980'>moves</span> <span m='226450'>for</span>
  <span m='227640'>n</span> <span m='227970'>disks.</span> <span
  m='229330'>So</span> <span m='229570'>to</span> <span m='229650'>take</span>
  <span m='229850'>a</span> <span m='229890'>stack</span> <span
  m='230360'>of</span> <span m='230430'>n disks</span> <span
  m='231010'>and</span> <span m='231130'>move</span> <span
  m='231340'>them</span> <span m='231880'>to</span> <span m='232010'>an</span>
  <span m='232080'>adjacent</span> <span m='232560'>peg.</span> </p><p><span
  m='234510'>So,</span> <span m='234750'>for</span> <span
  m='234890'>example,</span> <span m='235720'>what's</span> <span
  m='235870'>t1?</span> <span m='238040'>One.</span> <span m='238510'>I
  got</span> <span m='238980'>one peg,</span> <span m='239300'>I</span> <span
  m='239380'>just</span> <span m='239590'>move</span> <span
  m='239760'>it.</span> <span m='239860'>That's</span> <span
  m='240110'>easy.</span> <span m='241726'>t2,</span> <span m='244080'>3.</span>
  <span m='245040'>Move</span> <span m='245350'>the</span> <span
  m='245430'>little</span> <span m='245680'>guy,</span> <span
  m='246670'>move</span> <span m='246980'>the</span> <span
  m='247050'>base,</span> <span m='247870'>move</span> <span
  m='248060'>the</span> <span m='248130'>little</span> <span
  m='248360'>guy</span> <span m='248570'>back</span> <span m='248880'>on</span>
  <span m='249030'>top.</span> <span m='250000'>That's</span> <span
  m='250250'>the</span> <span m='250330'>best</span> <span m='250600'>you</span>
  <span m='250670'>can</span> <span m='250820'>do.</span> <span
  m='252090'>And</span> <span m='252410'>we've</span> <span
  m='252610'>seen</span> <span m='253080'>that</span> <span m='253230'>t3</span>
  <span m='253960'>is</span> <span m='254130'>at</span> <span
  m='254250'>most</span> <span m='254950'>7.</span> <span
  m='256510'>Maybe</span> <span m='257510'>there's</span> <span
  m='257690'>a</span> <span m='257750'>better</span> <span
  m='258010'>way.</span> </p><p><span m='259060'>But</span> <span
  m='259269'>let's</span> <span m='259490'>try</span> <span m='259700'>to</span>
  <span m='259920'>first</span> <span m='260250'>get</span> <span
  m='260380'>an</span> <span m='260490'>upper</span> <span
  m='260690'>bound</span> <span m='261040'>on</span> <span
  m='261220'>this.</span> <span m='262930'>Any</span> <span
  m='263150'>thoughts</span> <span m='263690'>about</span> <span
  m='264140'>how</span> <span m='264290'>we</span> <span m='264390'>might</span>
  <span m='264640'>go</span> <span m='264800'>about</span> <span
  m='265380'>a</span> <span m='265490'>general</span> <span
  m='266010'>upper</span> <span m='266220'>bound</span> <span
  m='266590'>for</span> <span m='266730'>n</span> <span m='269450'>for</span>
  <span m='269580'>this</span> <span m='269760'>problem?</span> <span
  m='271710'>Like</span> <span m='271970'>say</span> <span m='272310'>I</span>
  <span m='273060'>had</span> <span m='273340'>four</span> <span
  m='273690'>disks.</span> <span m='275270'>Any</span> <span
  m='275480'>thoughts</span> <span m='275920'>about</span> <span
  m='276530'>a</span> <span m='276620'>strategy</span> <span
  m='277390'>where</span> <span m='277540'>we</span> <span
  m='277660'>might</span> <span m='277870'>be</span> <span
  m='277940'>able</span> <span m='278060'>to</span> <span
  m='278140'>analyze</span> <span m='279000'>or</span> <span
  m='279110'>get</span> <span m='279270'>an</span> <span m='279350'>upper</span>
  <span m='279510'>bound</span> <span m='279850'>the</span> <span
  m='279910'>number</span> <span m='280090'>of</span> <span
  m='280150'>steps</span> <span m='280510'>for</span> <span
  m='280630'>four</span> <span m='281060'>disks</span> <span
  m='281530'>here?</span> <span m='283570'>Or</span> <span
  m='283790'>more</span> <span m='284070'>disks.</span> <span
  m='284400'>Any</span> <span m='284580'>thoughts?</span> <span
  m='285564'>Yeah.</span> </p><p></p><p><span m='287999'>AUDIENCE: You</span>
  <span m='288482'>can</span> <span m='288965'>look</span> <span
  m='289126'>at</span> <span m='289287'>the</span> <span
  m='290414'>previous</span> <span m='290900'>problem</span> <span
  m='291412'>and</span> <span m='292276'>then</span> <span m='292708'>add</span>
  <span m='293140'>a</span> <span m='293572'>certain</span> <span
  m='294010'>number of</span> <span m='294432'>[INAUDIBLE].</span> </p><p><span
  m='295890'>TOM LEIGHTON: Look</span> <span m='296240'>at</span> <span
  m='296330'>the</span> <span m='296570'>three</span> <span
  m='296870'>disk</span> <span m='297230'>problem.</span> <span
  m='297780'>That's</span> <span m='298040'>a</span> <span
  m='298100'>good</span> <span m='298300'>idea.</span> <span
  m='299370'>In</span> <span m='299490'>fact,</span> <span m='301360'>you</span>
  <span m='301490'>know,</span> <span m='301730'>I</span> <span
  m='301810'>could</span> <span m='302000'>look</span> <span
  m='302190'>at</span> <span m='302270'>the</span> <span m='302350'>three</span>
  <span m='302670'>disk</span> <span m='302860'>problem</span> <span
  m='303240'>recursively.</span> <span m='304210'>I</span> <span
  m='304330'>got</span> <span m='304520'>these</span> <span
  m='304770'>three</span> <span m='305000'>disks.</span> <span
  m='305450'>Say</span> <span m='305700'>I</span> <span m='305790'>move</span>
  <span m='306120'>them</span> <span m='307100'>over</span> <span
  m='307400'>a</span> <span m='307460'>series</span> <span m='307940'>of</span>
  <span m='308030'>steps,</span> <span m='308670'>seven</span> <span
  m='309020'>steps</span> <span m='309350'>at</span> <span
  m='309450'>most,</span> <span m='310160'>to</span> <span m='310300'>put</span>
  <span m='310470'>them</span> <span m='310580'>here.</span> <span
  m='312035'>What</span> <span m='312520'>would</span> <span m='312660'>I</span>
  <span m='312720'>do</span> <span m='312860'>next?</span> <span
  m='316240'>Move</span> <span m='316530'>the</span> <span
  m='316620'>lower</span> <span m='316930'>one</span> <span
  m='317870'>and</span> <span m='318060'>then</span> <span m='318540'>do</span>
  <span m='318770'>this</span> <span m='319010'>recurrent</span> <span
  m='319540'>problem</span> <span m='320000'>again</span> <span
  m='321060'>back.</span> </p><p><span m='322860'>All</span> <span
  m='323010'>right,</span> <span m='323210'>so</span> <span m='323320'>we</span>
  <span m='323410'>can</span> <span m='323560'>take</span> <span
  m='323880'>a</span> <span m='323970'>problem</span> <span
  m='324470'>with</span> <span m='324730'>n</span> <span m='325190'>disks</span>
  <span m='326310'>and</span> <span m='326480'>solve</span> <span
  m='326850'>it</span> <span m='327020'>recursively.</span> <span
  m='329900'>Let's</span> <span m='330130'>see</span> <span
  m='330300'>what</span> <span m='330460'>happens</span> <span
  m='330840'>when</span> <span m='330950'>we</span> <span m='331060'>do</span>
  <span m='331260'>that.</span> <span m='335250'>So</span> <span
  m='335410'>let's</span> <span m='335550'>look</span> <span
  m='335670'>at</span> <span m='335740'>a</span> <span
  m='335800'>recursive</span> <span m='336350'>solution.</span> <span
  m='343920'>And</span> <span m='344090'>let's</span> <span
  m='344900'>draw</span> <span m='345330'>it</span> <span m='345410'>for</span>
  <span m='345570'>n.</span> <span m='346000'>So</span> <span
  m='346270'>the</span> <span m='346400'>first</span> <span
  m='346750'>phase</span> <span m='348840'>that</span> <span
  m='348960'>you</span> <span m='349050'>described</span> <span
  m='350220'>is</span> <span m='350410'>I</span> <span m='350490'>start,</span>
  <span m='351280'>here</span> <span m='351510'>are my</span> <span
  m='351650'>three</span> <span m='351880'>pegs,</span> <span
  m='352430'>and</span> <span m='352530'>I</span> <span m='352570'>start</span>
  <span m='352890'>with</span> <span m='353020'>this,</span> <span
  m='353300'>1,</span> <span m='353640'>2,</span> <span m='353890'>3</span>
  <span m='355060'>down</span> <span m='355310'>to</span> <span
  m='355400'>end</span> <span m='355700'>here,</span> <span
  m='355900'>and</span> <span m='356020'>nothing</span> <span
  m='356370'>on</span> <span m='356460'>these</span> <span
  m='356660'>pegs.</span> </p><p><span m='358170'>And</span> <span
  m='358930'>I'm</span> <span m='359080'>going</span> <span m='359200'>to</span>
  <span m='359270'>use</span> <span m='359490'>recursion</span> <span
  m='360100'>to</span> <span m='360170'>take</span> <span m='360440'>the</span>
  <span m='360510'>top</span> <span m='360950'>and</span> <span
  m='361150'>minus</span> <span m='361500'>1</span> <span m='362520'>and</span>
  <span m='362700'>move</span> <span m='362840'>them</span> <span
  m='362980'>out</span> <span m='363150'>here.</span> <span m='364510'>So</span>
  <span m='364680'>I</span> <span m='364750'>leave</span> <span m='364990'>the
  nth</span> <span m='365330'>guy</span> <span m='365560'>there.</span> <span
  m='366130'>Nothing</span> <span m='366510'>here.</span> <span
  m='367680'>And</span> <span m='367830'>I</span> <span m='367900'>go</span>
  <span m='368560'>1,</span> <span m='368920'>2,</span> <span
  m='369970'>to</span> <span m='370410'>n</span> <span m='370660'>minus</span>
  <span m='370970'>1.</span> <span m='372870'>How</span> <span
  m='373130'>many</span> <span m='373340'>steps</span> <span
  m='374820'>does</span> <span m='375000'>that</span> <span
  m='375240'>move</span> <span m='375510'>take,</span> <span
  m='376880'>that</span> <span m='377060'>series</span> <span
  m='377470'>of</span> <span m='377540'>moves</span> <span
  m='377870'>take,</span> <span m='378200'>that</span> <span
  m='378380'>phase?</span> <span m='380650'>In</span> <span
  m='380750'>terms</span> <span m='381030'>of</span> <span m='381160'>t.</span>
  <span m='383740'>t</span> <span m='384170'>of</span> <span m='384310'>n</span>
  <span m='384460'>minus</span> <span m='384810'>1,</span> <span
  m='385130'>because</span> <span m='385290'>I'm</span> <span
  m='385420'>taking</span> <span m='385820'>an</span> <span m='385900'>n</span>
  <span m='386050'>minus</span> <span m='386390'>1</span> <span
  m='387200'>disk</span> <span m='387520'>stack</span> <span
  m='388020'>and</span> <span m='388130'>moving</span> <span
  m='388470'>it.</span> <span m='388980'>So</span> <span m='389150'>that</span>
  <span m='389430'>is</span> <span m='390640'>tn</span> <span
  m='391100'>minus</span> <span m='391430'>1</span> <span
  m='391660'>steps.</span> </p><p><span m='396230'>All</span> <span
  m='396430'>right,</span> <span m='396720'>now</span> <span
  m='396870'>my</span> <span m='397030'>next</span> <span m='397460'>move</span>
  <span m='399310'>is</span> <span m='399760'>to</span> <span
  m='399860'>take</span> <span m='400150'>this</span> <span
  m='400380'>guy</span> <span m='400600'>and</span> <span
  m='400710'>stick</span> <span m='400970'>him</span> <span
  m='401070'>here.</span> <span m='404120'>So</span> <span
  m='404190'>we'll</span> <span m='404280'>draw</span> <span
  m='404550'>that</span> <span m='404750'>over</span> <span
  m='404930'>here.</span> <span m='406460'>So</span> <span m='406710'>the</span>
  <span m='407060'>nth</span> <span m='407330'>guy</span> <span
  m='407500'>moves</span> <span m='407780'>there</span> <span
  m='408010'>and</span> <span m='408110'>I</span> <span m='408170'>leave</span>
  <span m='408430'>all</span> <span m='408590'>these</span> <span
  m='408790'>guys</span> <span m='409070'>here.</span> <span
  m='412030'>That's</span> <span m='412300'>going</span> <span
  m='412430'>to</span> <span m='412500'>be</span> <span m='412640'>phase</span>
  <span m='413030'>two.</span> <span m='417840'>I</span> <span
  m='418000'>move</span> <span m='418300'>the</span> <span
  m='418390'>largest</span> <span m='418870'>disk.</span> <span
  m='424120'>And</span> <span m='424340'>how</span> <span m='424480'>many</span>
  <span m='424650'>steps</span> <span m='424970'>did that</span> <span
  m='425210'>take?</span> <span m='427590'>One</span> <span
  m='427900'>step.</span> <span m='428500'>Just</span> <span
  m='428740'>move</span> <span m='428910'>one</span> <span
  m='429130'>disk.</span> <span m='433430'>One</span> <span
  m='433630'>step</span> <span m='433850'>for</span> <span
  m='433950'>that.</span> <span m='434370'>And</span> <span
  m='434490'>then</span> <span m='434630'>my</span> <span m='434770'>last</span>
  <span m='436200'>phase</span> <span m='437260'>is</span> <span
  m='437480'>to</span> <span m='437580'>take</span> <span m='437850'>all</span>
  <span m='438140'>these</span> <span m='438620'>and</span> <span
  m='438740'>move</span> <span m='438880'>them</span> <span
  m='439000'>onto</span> <span m='439250'>here.</span> <span
  m='450240'>And</span> <span m='450410'>so</span> <span m='450530'>then</span>
  <span m='450730'>it</span> <span m='450830'>looks</span> <span
  m='451080'>like</span> <span m='452370'>the</span> <span
  m='452430'>final</span> <span m='452750'>result,</span> <span
  m='453260'>1,</span> <span m='453530'>2,</span> <span m='454800'>over</span>
  <span m='454900'>n</span> <span m='455150'>minus</span> <span
  m='455480'>1</span> <span m='455850'>over n.</span> <span
  m='456930'>And</span> <span m='457090'>how</span> <span m='457280'>many</span>
  <span m='457470'>steps</span> <span m='457910'>this</span> <span
  m='458110'>phase</span> <span m='458440'>three</span> <span
  m='458670'>take?</span> <span m='462200'>tn</span> <span
  m='462640'>minus</span> <span m='463040'>1.</span> <span
  m='463914'>Good.</span> </p><p><span m='467710'>All</span> <span
  m='467820'>right,</span> <span m='467990'>so</span> <span
  m='468070'>we've</span> <span m='468180'>got</span> <span m='468400'>an</span>
  <span m='468490'>algorithm</span> <span m='469000'>now,</span> <span
  m='469660'>a</span> <span m='470550'>recursive</span> <span
  m='471090'>algorithm.</span> <span m='472080'>And</span> <span
  m='472440'>the</span> <span m='472510'>total</span> <span
  m='472950'>time,</span> <span m='478670'>the</span> <span
  m='478730'>number</span> <span m='479040'>of</span> <span
  m='479130'>moves</span> <span m='483080'>tn</span> <span m='483610'>is</span>
  <span m='483720'>at</span> <span m='483870'>most</span> <span
  m='485650'>tn</span> <span m='486010'>minus</span> <span m='486350'>1</span>
  <span m='486810'>plus</span> <span m='487090'>tn</span> <span
  m='487390'>minus</span> <span m='487720'>1</span> <span m='487970'>is</span>
  <span m='488210'>2tn</span> <span m='488880'>minus</span> <span
  m='489200'>1</span> <span m='490820'>plus</span> <span m='491190'>the</span>
  <span m='491270'>one</span> <span m='491490'>step</span> <span
  m='492600'>up</span> <span m='492820'>there.</span> <span
  m='494970'>For</span> <span m='495220'>example,</span> <span
  m='496080'>which</span> <span m='496270'>we</span> <span
  m='496370'>already</span> <span m='496600'>know,</span> <span
  m='496930'>t3</span> <span m='498270'>is</span> <span m='498430'>at</span>
  <span m='498540'>most</span> <span m='498910'>2t2</span> <span
  m='500520'>plus</span> <span m='500840'>1,</span> <span
  m='501740'>which</span> <span m='502010'>is</span> <span m='502140'>2</span>
  <span m='502360'>times</span> <span m='502740'>3</span> <span
  m='503340'>plus</span> <span m='503600'>1</span> <span m='503930'>is</span>
  <span m='504050'>7.</span> <span m='506070'>So</span> <span
  m='506200'>we</span> <span m='506300'>already</span> <span
  m='506560'>knew</span> <span m='506740'>we</span> <span
  m='506870'>could</span> <span m='506990'>do</span> <span m='507090'>it</span>
  <span m='507160'>in</span> <span m='507260'>seven.</span> <span
  m='508470'>What's</span> <span m='508700'>an</span> <span
  m='508780'>upper</span> <span m='508980'>bound</span> <span
  m='509570'>on</span> <span m='509790'>the</span> <span m='509860'>time</span>
  <span m='510240'>to</span> <span m='510320'>move</span> <span
  m='510520'>four</span> <span m='510750'>disks?</span> <span
  m='513210'>15.</span> <span m='514559'>OK?</span> <span m='516330'>All</span>
  <span m='516510'>right,</span> <span m='516730'>so</span> <span
  m='516940'>t4</span> <span m='518370'>is</span> <span m='518600'>at</span>
  <span m='518700'>most</span> <span m='519049'>15.</span> </p><p><span
  m='521390'>But</span> <span m='521549'>maybe</span> <span
  m='521770'>there's</span> <span m='521940'>a</span> <span
  m='521990'>better</span> <span m='522320'>way.</span> <span
  m='523070'>This</span> <span m='523270'>is</span> <span m='523350'>just</span>
  <span m='523590'>one</span> <span m='523890'>way</span> <span
  m='524039'>to</span> <span m='524130'>do</span> <span m='524360'>it.</span>
  <span m='525740'>How</span> <span m='525900'>many</span> <span
  m='526060'>people</span> <span m='526330'>think</span> <span
  m='526570'>there's</span> <span m='526740'>a</span> <span
  m='526790'>better</span> <span m='527150'>way</span> <span
  m='528420'>than</span> <span m='528590'>this</span> <span
  m='528750'>approach?</span> <span m='531590'>How</span> <span
  m='531730'>many</span> <span m='531870'>people</span> <span
  m='532090'>think</span> <span m='532270'>there</span> <span
  m='532380'>is</span> <span m='532530'>no</span> <span m='532670'>better</span>
  <span m='532890'>way?</span> <span m='533770'>All right,</span> <span
  m='534520'>very</span> <span m='534850'>good.</span> <span
  m='535250'>Yeah,</span> <span m='535470'>this</span> <span
  m='535670'>is</span> <span m='535760'>the</span> <span m='535850'>best</span>
  <span m='536270'>you</span> <span m='536370'>can</span> <span
  m='536550'>do.</span> <span m='537570'>And</span> <span
  m='537700'>let's</span> <span m='537910'>prove</span> <span
  m='538250'>that.</span> <span m='538710'>Let's</span> <span
  m='538880'>get</span> <span m='539010'>a</span> <span m='539060'>lower</span>
  <span m='539380'>bound.</span> </p><p><span m='547500'>All</span> <span
  m='547720'>right,</span> <span m='547900'>to</span> <span
  m='547970'>see</span> <span m='548250'>why</span> <span m='548480'>this</span>
  <span m='548720'>is</span> <span m='549060'>optimal,</span> <span
  m='551410'>think</span> <span m='551760'>about</span> <span
  m='552890'>the</span> <span m='553040'>step</span> <span
  m='553610'>where</span> <span m='553830'>the</span> <span
  m='554170'>nth</span> <span m='554790'>disk</span> <span
  m='555710'>moves.</span> <span m='557010'>At</span> <span
  m='557190'>some</span> <span m='557670'>point</span> <span
  m='558620'>in</span> <span m='558760'>our</span> <span
  m='558880'>procedure,</span> <span m='559910'>the</span> <span
  m='560070'>biggest</span> <span m='560580'>disk</span> <span
  m='561200'>has</span> <span m='561480'>to</span> <span m='561580'>move.</span>
  <span m='563600'>Now,</span> <span m='563890'>it</span> <span
  m='563960'>could</span> <span m='564090'>move</span> <span
  m='564340'>to</span> <span m='564430'>this</span> <span m='564640'>peg
  or</span> <span m='564940'>that</span> <span m='565200'>peg,</span> <span
  m='565670'>doesn't</span> <span m='566040'>really</span> <span
  m='566340'>matter.</span> <span m='566700'>But</span> <span
  m='566890'>when</span> <span m='567060'>it</span> <span
  m='567200'>moves,</span> <span m='568990'>what</span> <span
  m='569260'>do</span> <span m='569410'>I</span> <span m='569700'>know
  had</span> <span m='570240'>to</span> <span m='570340'>have</span> <span
  m='570460'>happened</span> <span m='570880'>before</span> <span
  m='571230'>that</span> <span m='571560'>guy</span> <span
  m='571780'>moved?</span> <span m='577150'>Everything</span> <span
  m='577690'>on</span> <span m='577890'>top</span> <span m='578200'>of</span>
  <span m='578350'>it</span> <span m='578820'>had</span> <span
  m='579170'>to</span> <span m='579250'>move</span> <span m='579750'>to</span>
  <span m='579880'>the</span> <span m='580230'>other</span> <span
  m='580600'>peg.</span> <span m='582360'>I</span> <span
  m='582510'>started</span> <span m='582950'>with</span> <span
  m='583120'>1</span> <span m='583380'>through</span> <span m='583550'>n</span>
  <span m='583650'>minus</span> <span m='583970'>1</span> <span
  m='584220'>here.</span> <span m='584840'>None</span> <span
  m='585160'>of</span> <span m='585260'>them</span> <span m='585420'>can</span>
  <span m='585580'>be</span> <span m='585700'>here.</span> <span
  m='586410'>They</span> <span m='586590'>all</span> <span
  m='587030'>have</span> <span m='587260'>to</span> <span m='587360'>be</span>
  <span m='587540'>here.</span> <span m='589680'>OK?</span> <span
  m='590970'>So</span> <span m='591790'>that</span> <span
  m='592040'>means</span> <span m='592350'>that</span> <span m='592470'>I</span>
  <span m='592570'>have</span> <span m='592890'>to have</span> <span
  m='593210'>had</span> <span m='594100'>tn</span> <span m='594460'>minus</span>
  <span m='594800'>1</span> <span m='595030'>steps.</span> <span
  m='597330'>So</span> <span m='597610'>at</span> <span m='597730'>least</span>
  <span m='598170'>tn</span> <span m='598490'>minus</span> <span
  m='598810'>1</span> <span m='598980'>steps</span> <span
  m='602750'>before</span> <span m='605150'>the</span> <span
  m='605270'>big</span> <span m='606930'>disk</span> <span
  m='607320'>moves.</span> <span m='612520'>All</span> <span
  m='612720'>right?</span> </p><p><span m='613560'>Then</span> <span
  m='614800'>there</span> <span m='615050'>is</span> <span m='615260'>the</span>
  <span m='615370'>step</span> <span m='615890'>when</span> <span
  m='616060'>the</span> <span m='616130'>big</span> <span m='616410'>guy</span>
  <span m='616680'>moves.</span> <span m='618850'>One</span> <span
  m='619200'>step</span> <span m='619490'>for</span> <span m='619590'>the</span>
  <span m='619670'>big</span> <span m='619890'>guy</span> <span
  m='620050'>to</span> <span m='620130'>move.</span> <span
  m='628020'>Because</span> <span m='628200'>it's</span> <span
  m='628320'>got</span> <span m='628490'>to</span> <span m='628550'>move</span>
  <span m='628720'>at</span> <span m='628800'>least</span> <span
  m='629090'>once.</span> <span m='633490'>And</span> <span
  m='633670'>then</span> <span m='634350'>after</span> <span
  m='634820'>it</span> <span m='634960'>moves,</span> <span m='636560'>I</span>
  <span m='636680'>got</span> <span m='636890'>to</span> <span
  m='636950'>get</span> <span m='637120'>everything</span> <span
  m='637590'>else,</span> <span m='638660'>one</span> <span
  m='638970'>way</span> <span m='639140'>or</span> <span
  m='639200'>another,</span> <span m='640360'>on</span> <span
  m='640600'>top</span> <span m='640880'>of</span> <span m='641000'>it.</span>
  <span m='642500'>At</span> <span m='642690'>some</span> <span
  m='643030'>point</span> <span m='643790'>after</span> <span
  m='644070'>the</span> <span m='644150'>last</span> <span
  m='644620'>time</span> <span m='644910'>the</span> <span m='644980'>big</span>
  <span m='645180'>guy</span> <span m='645390'>moves,</span> <span
  m='646110'>everything</span> <span m='646470'>else</span> <span
  m='646640'>has</span> <span m='646810'>to</span> <span m='646900'>go</span>
  <span m='647020'>on</span> <span m='647170'>top.</span> <span
  m='648890'>And</span> <span m='649100'>that's</span> <span
  m='649450'>another</span> <span m='649920'>tn</span> <span
  m='650260'>minus</span> <span m='650560'>1</span> <span
  m='650760'>steps.</span> </p><p><span m='655350'>So</span> <span
  m='655420'>after</span> <span m='655790'>the</span> <span
  m='655870'>last</span> <span m='656250'>time</span> <span
  m='656450'>the</span> <span m='656530'>big</span> <span m='656740'>guy</span>
  <span m='656920'>moves,</span> <span m='664160'>you've</span> <span
  m='664340'>got</span> <span m='664490'>to</span> <span m='664560'>take</span>
  <span m='664940'>tn</span> <span m='665020'>minus</span> <span
  m='665320'>1</span> <span m='665490'>steps.</span> <span m='670560'>OK,</span>
  <span m='670980'>so</span> <span m='671170'>that</span> <span
  m='671450'>means</span> <span m='671760'>there's</span> <span
  m='671920'>a</span> <span m='671980'>lower</span> <span
  m='672310'>bound</span> <span m='672640'>that</span> <span
  m='672740'>no</span> <span m='672830'>matter</span> <span
  m='673030'>what</span> <span m='673330'>you</span> <span m='673430'>do</span>
  <span m='675670'>tn</span> <span m='676630'>is</span> <span
  m='676820'>at</span> <span m='676960'>least</span> <span m='677380'>2tn</span>
  <span m='677950'>minus</span> <span m='678300'>1</span> <span
  m='679500'>plus</span> <span m='679820'>1.</span> <span m='681420'>And</span>
  <span m='681610'>so</span> <span m='681780'>in</span> <span
  m='681870'>fact,</span> <span m='682520'>it's</span> <span
  m='682580'>equal.</span> <span m='684880'>tn</span> <span
  m='685430'>equals</span> <span m='686130'>2tn</span> <span
  m='686710'>minus</span> <span m='687030'>1</span> <span m='687830'>plus</span>
  <span m='688150'>1.</span> <span m='690730'>So</span> <span
  m='690960'>t3</span> <span m='691370'>is</span> <span m='691590'>7,</span>
  <span m='692055'>t4</span> <span m='692520'>is</span> <span
  m='692750'>15.</span> <span m='694750'>Any</span> <span
  m='694930'>questions</span> <span m='698390'>about</span> <span
  m='698640'>that?</span> </p><p><span m='702080'>All</span> <span
  m='702310'>right,</span> <span m='702480'>well</span> <span
  m='702580'>we'd</span> <span m='702730'>like</span> <span m='702960'>to</span>
  <span m='703050'>know</span> <span m='703520'>how</span> <span
  m='703710'>long</span> <span m='704020'>till</span> <span
  m='704150'>the</span> <span m='704230'>world</span> <span
  m='704590'>ends,</span> <span m='705750'>which</span> <span
  m='705940'>is</span> <span m='706050'>t64.</span> <span m='707580'>So</span>
  <span m='707720'>we'd</span> <span m='707830'>like</span> <span
  m='708000'>to</span> <span m='708080'>get</span> <span m='708240'>a</span>
  <span m='708310'>formula</span> <span m='709700'>for</span> <span
  m='709850'>t</span> <span m='710080'>of</span> <span m='710200'>n.</span>
  <span m='710440'>We</span> <span m='710540'>could</span> <span
  m='710780'>just</span> <span m='711080'>compute</span> <span
  m='711520'>it</span> <span m='711640'>64</span> <span m='712170'>times</span>
  <span m='712600'>and</span> <span m='712730'>see.</span> <span
  m='714080'>But</span> <span m='714240'>much</span> <span
  m='714490'>nicer</span> <span m='714790'>just</span> <span
  m='714990'>to</span> <span m='715050'>get</span> <span m='715160'>a</span>
  <span m='715190'>formula.</span> <span m='716710'>And</span> <span
  m='716960'>that's</span> <span m='717170'>what</span> <span
  m='717290'>we're</span> <span m='717370'>going</span> <span
  m='717490'>to</span> <span m='717550'>learn</span> <span m='717710'>how</span>
  <span m='717800'>to</span> <span m='717880'>do</span> <span
  m='718050'>this</span> <span m='718250'>week</span> <span m='718570'>is</span>
  <span m='718790'>to</span> <span m='718880'>get</span> <span
  m='719110'>formulas,</span> <span m='719990'>closed</span> <span
  m='720310'>form</span> <span m='720520'>expressions,</span> <span
  m='721570'>to</span> <span m='721720'>solve</span> <span
  m='722050'>recurrences.</span> <span m='723420'>And</span> <span
  m='723620'>there's</span> <span m='723780'>a</span> <span
  m='723830'>bunch</span> <span m='724160'>of</span> <span
  m='724230'>different</span> <span m='724500'>methods</span> <span
  m='724810'>you</span> <span m='724890'>can</span> <span m='725060'>use</span>
  <span m='725470'>and</span> <span m='725590'>we're</span> <span
  m='725660'>going</span> <span m='725780'>to</span> <span
  m='725840'>talk</span> <span m='726150'>about</span> <span
  m='726420'>them.</span> <span m='727380'>The</span> <span
  m='727930'>simplest</span> <span m='729490'>is</span> <span
  m='729840'>to</span> <span m='729950'>guess</span> <span m='730490'>the</span>
  <span m='730670'>answer</span> <span m='731760'>and</span> <span
  m='731930'>then</span> <span m='732110'>check</span> <span
  m='732400'>it.</span> <span m='732500'>It's</span> <span
  m='732940'>called</span> <span m='733220'>guess</span> <span
  m='733860'>and</span> <span m='734040'>verify,</span> <span
  m='736110'>also</span> <span m='736460'>known</span> <span
  m='736750'>as</span> <span m='736910'>the</span> <span
  m='736990'>substitution</span> <span m='737810'>method.</span> </p><p><span
  m='753140'>Now,</span> <span m='754710'>what's</span> <span
  m='754990'>a</span> <span m='755050'>good</span> <span m='755270'>guess</span>
  <span m='756160'>for</span> <span m='756300'>t</span> <span
  m='756510'>of</span> <span m='756640'>n?</span> <span m='760070'>2 to</span>
  <span m='760340'>the</span> <span m='760450'>n</span> <span
  m='760590'>minus</span> <span m='760950'>1.</span> <span m='761250'>You</span>
  <span m='761380'>got</span> <span m='761960'>t</span> <span
  m='762140'>of</span> <span m='762260'>1</span> <span m='762650'>is</span>
  <span m='762820'>1,</span> <span m='763770'>t</span> <span
  m='763990'>of</span> <span m='764100'>2</span> <span m='764380'>is</span>
  <span m='764590'>3,</span> <span m='765600'>t of</span> <span
  m='765690'>3</span> <span m='765910'>is</span> <span m='766040'>7,</span>
  <span m='766800'>t of</span> <span m='767180'>4</span> <span
  m='767680'>is</span> <span m='767820'>15.</span> <span m='769170'>You</span>
  <span m='769680'>won't</span> <span m='769950'>compute</span> <span
  m='770300'>too</span> <span m='770440'>many</span> <span
  m='770670'>before</span> <span m='770980'>you</span> <span
  m='771070'>guess</span> <span m='775910'>that</span> <span m='776490'>t</span>
  <span m='776700'>of</span> <span m='776820'>n</span> <span
  m='777730'>is</span> <span m='777980'>2 to</span> <span m='778220'>the</span>
  <span m='778360'>n</span> <span m='778490'>minus</span> <span
  m='778820'>1.</span> <span m='782570'>Now,</span> <span m='782740'>that</span>
  <span m='782880'>doesn't</span> <span m='783220'>mean</span> <span
  m='783470'>it's</span> <span m='783610'>true.</span> </p><p><span
  m='784900'>So</span> <span m='785120'>how</span> <span m='785370'>are</span>
  <span m='785430'>we</span> <span m='785570'>going</span> <span
  m='785700'>to</span> <span m='785770'>verify</span> <span
  m='786410'>that</span> <span m='786630'>guess?</span> <span
  m='788760'>What</span> <span m='788950'>proof</span> <span
  m='789190'>technique?</span> <span m='791360'>Induction.</span> <span
  m='792600'>It</span> <span m='792720'>just</span> <span
  m='792910'>keeps</span> <span m='793170'>coming</span> <span
  m='793460'>back.</span> <span m='794060'>You</span> <span
  m='794140'>just</span> <span m='794360'>never</span> <span
  m='794970'>finish</span> <span m='795320'>with</span> <span
  m='795440'>induction.</span> <span m='796880'>So</span> <span
  m='797000'>we're</span> <span m='797080'>going</span> <span
  m='797200'>to</span> <span m='797260'>verify</span> <span
  m='797880'>this</span> <span m='800490'>by</span> <span
  m='800720'>induction.</span> </p><p><span m='809080'>What's</span> <span
  m='809330'>our</span> <span m='809450'>induction</span> <span
  m='809820'>hypothesis?</span> <span m='813020'>Any</span> <span
  m='813190'>thoughts?</span> <span m='818280'>Right</span> <span
  m='818510'>there.</span> <span m='819190'>p of</span> <span
  m='819380'>n</span> <span m='819645'>is</span> <span m='819910'>going</span>
  <span m='820040'>to</span> <span m='820110'>be</span> <span
  m='820430'>that</span> <span m='820660'>tn</span> <span
  m='821230'>equals</span> <span m='821570'>2</span> <span m='821790'>to
  the</span> <span m='821880'>n</span> <span m='822010'>minus</span> <span
  m='822330'>1.</span> <span m='823670'>Very</span> <span
  m='824010'>typical.</span> <span m='827390'>So</span> <span
  m='827550'>the</span> <span m='827640'>predicate</span> <span
  m='828230'>is</span> <span m='828690'>that</span> <span m='829060'>t</span>
  <span m='829320'>of</span> <span m='829440'>n</span> <span
  m='830290'>is</span> <span m='830470'>2</span> <span m='830680'>to the</span>
  <span m='830800'>n</span> <span m='830940'>minus</span> <span
  m='831260'>1.</span> <span m='832670'>Base</span> <span
  m='832980'>case.</span> <span m='837970'>We'll</span> <span
  m='838170'>pick</span> <span m='838460'>n</span> <span
  m='838640'>equals</span> <span m='838930'>1.</span> <span m='840150'>T</span>
  <span m='840370'>of</span> <span m='840480'>1</span> <span
  m='840770'>is</span> <span m='840940'>1</span> <span m='842210'>and</span>
  <span m='842460'>that</span> <span m='842710'>is</span> <span
  m='843150'>2</span> <span m='843330'>to the</span> <span m='843500'>1</span>
  <span m='843750'>minus</span> <span m='844080'>1.</span> <span
  m='845260'>So</span> <span m='845410'>the</span> <span m='845480'>base</span>
  <span m='845740'>case</span> <span m='846030'>works.</span> </p><p><span
  m='849120'>Now</span> <span m='849270'>we'll</span> <span m='849380'>do</span>
  <span m='849560'>the</span> <span m='849900'>inductive</span> <span
  m='850340'>step.</span> <span m='856950'>We're</span> <span
  m='857080'>going</span> <span m='857340'>to</span> <span
  m='857450'>assume</span> <span m='859530'>p</span> <span m='859740'>of</span>
  <span m='859790'>n.</span> <span m='860330'>We're</span> <span
  m='860470'>going</span> <span m='860600'>to</span> <span
  m='860660'>assume</span> <span m='861110'>that</span> <span
  m='861270'>tn</span> <span m='862330'>equals</span> <span m='862730'>2</span>
  <span m='862920'>to</span> <span m='863000'>the</span> <span
  m='863120'>n</span> <span m='863270'>minus</span> <span m='863610'>1</span>
  <span m='864320'>to</span> <span m='864470'>prove</span> <span
  m='864950'>pn</span> <span m='865280'>minus</span> <span m='865630'>1,</span>
  <span m='868100'>which</span> <span m='868420'>is</span> <span
  m='868890'>tn</span> <span m='869280'>plus</span> <span m='869580'>1</span>
  <span m='870130'>equals</span> <span m='870640'>2</span> <span
  m='870940'>to</span> <span m='871030'>the</span> <span m='871160'>n</span>
  <span m='871310'>plus</span> <span m='871610'>1</span> <span
  m='872440'>minus</span> <span m='872830'>1.</span> <span m='873970'>So</span>
  <span m='874120'>a</span> <span m='874150'>very</span> <span
  m='874570'>standard</span> <span m='874930'>induction.</span> <span
  m='875960'>So</span> <span m='876020'>let's</span> <span
  m='876240'>look</span> <span m='876440'>at</span> <span m='876530'>tn</span>
  <span m='876840'>plus</span> <span m='877100'>1</span> <span
  m='877320'>now.</span> <span m='879600'>tn</span> <span m='879950'>plus</span>
  <span m='880230'>1</span> <span m='880590'>equals</span> <span
  m='881380'>2n</span> <span m='883970'>plus</span> <span m='884320'>1.</span>
  <span m='885910'>Yeah,</span> <span m='886330'>2tn</span> <span
  m='887170'>plus</span> <span m='887430'>1.</span> <span m='889220'>Now</span>
  <span m='889480'>we</span> <span m='889590'>plug in</span> <span
  m='890200'>here.</span> <span m='891320'>That's</span> <span
  m='891520'>just</span> <span m='891670'>the</span> <span
  m='891750'>recurrence.</span> <span m='892500'>Now</span> <span
  m='892690'>we</span> <span m='892790'>plug in</span> <span
  m='893890'>using</span> <span m='894250'>our</span> <span
  m='894380'>assumption</span> <span m='894870'>from</span> <span
  m='895000'>the</span> <span m='895080'>induction.</span> <span
  m='896490'>This</span> <span m='896730'>is</span> <span m='896890'>2</span>
  <span m='900500'>to</span> <span m='900790'>the</span> <span
  m='900970'>n</span> <span m='901500'>minus</span> <span m='901920'>1</span>
  <span m='902710'>plus</span> <span m='903000'>1.</span> <span
  m='904580'>Multiply</span> <span m='904980'>the</span> <span
  m='905070'>2.</span> <span m='905330'>That's</span> <span m='905590'>2
  to</span> <span m='905880'>the</span> <span m='906010'>n</span> <span
  m='906160'>plus</span> <span m='906440'>1.</span> <span
  m='907430'>Minus</span> <span m='907920'>2</span> <span m='908260'>plus</span>
  <span m='908810'>1</span> <span m='909020'>is</span> <span
  m='909140'>minus</span> <span m='909550'>1.</span> <span m='911730'>And</span>
  <span m='911900'>so</span> <span m='912080'>we're</span> <span
  m='912190'>done.</span> </p><p><span m='914870'>All</span> <span
  m='914950'>right,</span> <span m='915070'>so</span> <span m='915170'>we</span>
  <span m='915260'>guessed</span> <span m='915630'>the</span> <span
  m='915820'>answer.</span> <span m='916150'>It was</span> <span
  m='916280'>a</span> <span m='916350'>pretty</span> <span
  m='916590'>easy</span> <span m='916810'>guess.</span> <span
  m='917600'>Very</span> <span m='917960'>simple</span> <span
  m='918310'>to</span> <span m='918420'>prove</span> <span m='918630'>it</span>
  <span m='918720'>by</span> <span m='918890'>induction.</span> <span
  m='921160'>Any</span> <span m='921340'>questions?</span> </p><p><span
  m='924250'>All right,</span> <span m='925000'>how</span> <span
  m='925180'>long</span> <span m='925420'>would</span> <span
  m='925520'>it</span> <span m='925600'>take</span> <span m='925850'>me</span>
  <span m='925980'>to</span> <span m='926060'>do</span> <span
  m='926280'>all</span> <span m='926540'>seven</span> <span
  m='926960'>disks</span> <span m='927480'>on</span> <span
  m='927650'>this</span> <span m='927810'>puzzle</span> <span
  m='928180'>here?</span> <span m='931010'>How</span> <span
  m='931150'>many</span> <span m='931310'>steps?</span> <span
  m='935118'>127</span> <span m='936070'>steps.</span> <span
  m='937060'>How</span> <span m='937270'>long</span> <span
  m='937500'>till</span> <span m='937640'>the</span> <span m='937760'>end</span>
  <span m='937910'>of</span> <span m='937970'>the</span> <span
  m='938030'>world?</span> <span m='940350'>A</span> <span
  m='940490'>long</span> <span m='941010'>time.</span> <span m='941500'>2</span>
  <span m='941720'>to</span> <span m='941790'>the</span> <span
  m='941900'>64th</span> <span m='942570'>minus</span> <span m='942900'>1</span>
  <span m='943190'>is</span> <span m='943910'>18</span> <span
  m='944490'>billion,</span> <span m='945000'>billion</span> <span
  m='945600'>moves.</span> <span m='946070'>So</span> <span
  m='946800'>going</span> <span m='946930'>to</span> <span
  m='946990'>keep</span> <span m='947160'>those</span> <span
  m='947350'>monks</span> <span m='947700'>busy</span> <span
  m='947990'>for</span> <span m='948110'>a</span> <span m='948150'>little</span>
  <span m='948320'>while</span> <span m='950020'>before</span> <span
  m='950220'>the</span> <span m='950310'>world</span> <span
  m='950670'>ends.</span> </p><p><span m='952180'>Now</span> <span
  m='952880'>in</span> <span m='953040'>general,</span> <span
  m='954110'>this</span> <span m='954360'>method</span> <span
  m='955760'>is</span> <span m='955950'>sort</span> <span m='956110'>of</span>
  <span m='956170'>the</span> <span m='956240'>best</span> <span
  m='956620'>method</span> <span m='956900'>for</span> <span
  m='957010'>solving</span> <span m='957420'>a</span> <span
  m='957470'>recurrence.</span> <span m='958620'>We'll</span> <span
  m='958760'>see</span> <span m='958930'>lots</span> <span m='959270'>of</span>
  <span m='959340'>examples</span> <span m='959910'>where it</span> <span
  m='960310'>works</span> <span m='960600'>great.</span> <span
  m='961950'>The</span> <span m='961960'>only</span> <span
  m='962160'>problem</span> <span m='962620'>is</span> <span
  m='962790'>it</span> <span m='962870'>requires</span> <span
  m='963440'>that</span> <span m='963650'>divine</span> <span
  m='964050'>insight</span> <span m='964530'>thing,</span> <span
  m='965120'>that</span> <span m='965370'>guess</span> <span
  m='965980'>to</span> <span m='966090'>guess</span> <span m='966360'>the</span>
  <span m='966440'>right</span> <span m='966650'>answer.</span> <span
  m='966970'>Obviously</span> <span m='967390'>if we guess</span> <span
  m='967610'>the</span> <span m='967690'>wrong</span> <span
  m='967980'>answer,</span> <span m='968440'>it's</span> <span
  m='969060'>not</span> <span m='969250'>going</span> <span m='969370'>to</span>
  <span m='969430'>work.</span> <span m='970480'>Guessing</span> <span
  m='970900'>is</span> <span m='971530'>many</span> <span
  m='971910'>times</span> <span m='972260'>easy,</span> <span
  m='972560'>but</span> <span m='972840'>not</span> <span
  m='973160'>always.</span> <span m='975520'>So</span> <span
  m='975870'>you</span> <span m='976010'>need</span> <span
  m='976170'>other</span> <span m='976320'>methods</span> <span
  m='976900'>when</span> <span m='977030'>you</span> <span
  m='977100'>can't</span> <span m='977370'>guess</span> <span
  m='977640'>it.</span> </p><p><span m='978220'>The</span> <span
  m='978320'>next</span> <span m='978680'>most</span> <span
  m='978910'>common</span> <span m='979300'>method</span> <span
  m='980530'>has</span> <span m='980700'>a</span> <span m='980760'>lot</span>
  <span m='980970'>of</span> <span m='981030'>names.</span> <span
  m='981320'>It's called</span> <span m='981660'>plug</span> <span
  m='982000'>and</span> <span m='982140'>chug,</span> <span
  m='983990'>expansion,</span> <span m='985570'>iteration,</span> <span
  m='986780'>brute</span> <span m='987130'>force,</span> <span
  m='988360'>exhaustion.</span> <span m='990760'>Let</span> <span
  m='990890'>me</span> <span m='990970'>show</span> <span m='991140'>you</span>
  <span m='991230'>how</span> <span m='991360'>that</span> <span
  m='991550'>works</span> <span m='991830'>in</span> <span
  m='991920'>this</span> <span m='992110'>example.</span> </p><p><span
  m='1004640'>OK,</span> <span m='1005030'>so</span> <span
  m='1005360'>plug</span> <span m='1005650'>and</span> <span
  m='1005770'>chug.</span> <span m='1011040'>So</span> <span
  m='1011180'>we'll</span> <span m='1011280'>solve</span> <span
  m='1011700'>the</span> <span m='1011760'>same</span> <span
  m='1012160'>recurrence.</span> <span m='1014410'>So</span> <span
  m='1014610'>we've</span> <span m='1014720'>got</span> <span
  m='1014990'>tn</span> <span m='1015930'>equals,</span> <span
  m='1016560'>and</span> <span m='1016700'>I'm</span> <span
  m='1016760'>going</span> <span m='1016880'>to</span> <span
  m='1016940'>write</span> <span m='1017190'>it</span> <span
  m='1017820'>just</span> <span m='1018060'>reversed,</span> <span
  m='1018530'>1</span> <span m='1018800'>plus</span> <span
  m='1019100'>2tn.</span> <span m='1021030'>Because</span> <span
  m='1021220'>I'm</span> <span m='1021320'>going</span> <span
  m='1021450'>to</span> <span m='1021520'>expand</span> <span
  m='1022290'>out</span> <span m='1023190'>the</span> <span
  m='1023310'>recurrent</span> <span m='1023760'>term.</span> <span
  m='1024280'>That's</span> <span m='1024410'>why</span> <span
  m='1024550'>it's</span> <span m='1024660'>called</span> <span
  m='1024910'>expansion</span> <span m='1025760'>also.</span> <span
  m='1028109'>Well,</span> <span m='1028359'>that's</span> <span
  m='1028630'>equal</span> <span m='1028839'>to</span> <span
  m='1028920'>1</span> <span m='1029490'>plus</span> <span m='1030380'>2.</span>
  <span m='1031150'>Now I</span> <span m='1031480'>expand</span> <span
  m='1032030'>this</span> <span m='1032210'>out</span> <span
  m='1032430'>using</span> <span m='1032780'>the</span> <span
  m='1032859'>recurrence.</span> <span m='1034230'>1</span> <span
  m='1034579'>plus</span> <span m='1034940'>2</span> <span m='1035630'>tn</span>
  <span m='1036250'>minus</span> <span m='1036569'>1.</span> <span
  m='1040048'>All right,</span> <span m='1040849'>now</span> <span
  m='1041079'>I</span> <span m='1041150'>do</span> <span m='1041270'>a</span>
  <span m='1041310'>little</span> <span m='1041510'>chugging</span> <span
  m='1041910'>here.</span> <span m='1042250'>So</span> <span
  m='1042369'>I</span> <span m='1042430'>plugged</span> <span
  m='1042869'>here.</span> <span m='1044700'>Now</span> <span
  m='1044940'>I'll</span> <span m='1045030'>do</span> <span
  m='1045180'>chug.</span> <span m='1047089'>That's</span> <span
  m='1047290'>1</span> <span m='1047720'>plus</span> <span m='1048490'>2</span>
  <span m='1049070'>plus</span> <span m='1049410'>4</span> <span
  m='1050290'>tn</span> <span m='1051000'>minus</span> <span
  m='1051340'>1.</span> <span m='1053420'>Now</span> <span
  m='1053600'>I'm</span> <span m='1053710'>going</span> <span
  m='1053840'>to</span> <span m='1053910'>plug in</span> <span
  m='1054410'>again.</span> <span m='1057580'>What's</span> <span
  m='1057750'>that?</span> </p><p><span m='1059178'>AUDIENCE:
  [INAUDIBLE].</span> </p><p><span m='1062700'>TOM LEIGHTON: You're</span> <span
  m='1063040'>right.</span> <span m='1065290'>You're</span> <span
  m='1065540'>right,</span> <span m='1065880'>I've</span> <span
  m='1065970'>got</span> <span m='1066100'>to</span> <span
  m='1066160'>get</span> <span m='1066280'>minus</span> <span
  m='1066700'>1</span> <span m='1066900'>here</span> <span
  m='1067290'>and</span> <span m='1067430'>minus</span> <span
  m='1067790'>2</span> <span m='1068060'>here.</span> <span
  m='1069140'>That</span> <span m='1069320'>is</span> <span
  m='1069450'>correct.</span> <span m='1070390'>Very</span> <span
  m='1070540'>good.</span> <span m='1070810'>I</span> <span m='1070910'>would
  have</span> <span m='1071090'>run</span> <span m='1071270'>into</span> <span
  m='1071400'>trouble.</span> <span m='1072400'>That's</span> <span
  m='1072650'>good.</span> <span m='1075730'>Now</span> <span
  m='1075920'>I</span> <span m='1075990'>plug in</span> <span
  m='1076460'>here.</span> <span m='1077350'>1</span> <span
  m='1077630'>plus</span> <span m='1077960'>2</span> <span
  m='1078390'>plus</span> <span m='1078760'>4,</span> <span m='1079770'>1</span>
  <span m='1080150'>plus</span> <span m='1080550'>2</span> <span
  m='1080825'>tn</span> <span m='1081520'>minus</span> <span
  m='1081860'>3.</span> <span m='1084680'>Then</span> <span
  m='1084900'>we</span> <span m='1085000'>do</span> <span m='1085150'>the</span>
  <span m='1085250'>chug.</span> <span m='1099230'>1</span> <span
  m='1099630'>plus</span> <span m='1100050'>2</span> <span
  m='1100530'>plus</span> <span m='1100920'>4</span> <span
  m='1101940'>plus</span> <span m='1102370'>8</span> <span m='1103400'>tn</span>
  <span m='1103800'>minus</span> <span m='1104130'>3.</span> </p><p><span
  m='1106770'>All</span> <span m='1106900'>right,</span> <span
  m='1107100'>and</span> <span m='1107200'>now</span> <span
  m='1107530'>we're</span> <span m='1107650'>going</span> <span
  m='1107780'>to</span> <span m='1108300'>try</span> <span m='1108590'>to</span>
  <span m='1108710'>observe</span> <span m='1109270'>the</span> <span
  m='1109350'>pattern</span> <span m='1109840'>we're</span> <span
  m='1109970'>getting.</span> <span m='1110430'>So</span> <span
  m='1110600'>there's</span> <span m='1110700'>a</span> <span
  m='1110740'>little</span> <span m='1110980'>bit</span> <span
  m='1111100'>of</span> <span m='1111180'>a</span> <span
  m='1111250'>guess</span> <span m='1111600'>going</span> <span
  m='1111850'>on</span> <span m='1112030'>in</span> <span
  m='1112130'>this</span> <span m='1112320'>context</span> <span
  m='1112870'>still.</span> <span m='1113900'>But</span> <span
  m='1114100'>you</span> <span m='1114170'>see</span> <span
  m='1114360'>the</span> <span m='1114450'>pattern.</span> <span
  m='1114850'>We've</span> <span m='1114950'>got</span> <span
  m='1115080'>powers</span> <span m='1115530'>of</span> <span
  m='1115640'>2.</span> <span m='1116760'>Pretty</span> <span
  m='1117020'>easy</span> <span m='1117240'>pattern.</span> <span
  m='1117690'>So</span> <span m='1117910'>you</span> <span
  m='1118040'>might</span> <span m='1118550'>say</span> <span
  m='1118800'>if</span> <span m='1118890'>I</span> <span m='1118970'>keep</span>
  <span m='1119250'>on</span> <span m='1119410'>doing</span> <span
  m='1119710'>this,</span> <span m='1119890'>I'm</span> <span
  m='1119970'>going</span> <span m='1120100'>to</span> <span
  m='1120160'>get</span> <span m='1120360'>1</span> <span
  m='1120680'>plus</span> <span m='1121380'>2</span> <span
  m='1121640'>plus</span> <span m='1121930'>4</span> <span
  m='1122740'>plus</span> <span m='1123170'>dot</span> <span
  m='1123470'>dot</span> <span m='1123700'>dot</span> <span
  m='1124440'>plus</span> <span m='1125320'>2</span> <span m='1125580'>to</span>
  <span m='1125670'>the</span> <span m='1125900'>i</span> <span
  m='1126630'>minus</span> <span m='1127010'>1</span> <span
  m='1128000'>plus</span> <span m='1128450'>2</span> <span m='1128690'>to</span>
  <span m='1128780'>the</span> <span m='1128980'>i</span> <span
  m='1129730'>tn</span> <span m='1130530'>minus</span> <span
  m='1130855'>i.</span> <span m='1132964'>Got</span> <span m='1133410'>2</span>
  <span m='1133610'>to</span> <span m='1133680'>the</span> <span
  m='1133770'>3</span> <span m='1134160'>tn</span> <span
  m='1134530'>minus</span> <span m='1134880'>3</span> <span
  m='1135160'>there.</span> </p><p><span m='1136930'>And</span> <span
  m='1137140'>then</span> <span m='1137330'>I</span> <span
  m='1137430'>take</span> <span m='1137710'>this</span> <span
  m='1137870'>all</span> <span m='1138130'>the</span> <span
  m='1138200'>way</span> <span m='1138380'>down</span> <span
  m='1138840'>to</span> <span m='1139910'>i</span> <span
  m='1140120'>equals</span> <span m='1140430'>n</span> <span
  m='1140570'>minus</span> <span m='1140880'>1,</span> <span
  m='1141430'>1</span> <span m='1141770'>plus</span> <span m='1142130'>2</span>
  <span m='1142950'>plus</span> <span m='1143130'>4</span> <span
  m='1145776'>plus</span> <span m='1146470'>2</span> <span m='1146760'>to</span>
  <span m='1146890'>the</span> <span m='1147910'>n</span> <span
  m='1148170'>minus</span> <span m='1148520'>2</span> <span
  m='1148930'>plus</span> <span m='1149970'>2</span> <span m='1150230'>to</span>
  <span m='1150350'>the</span> <span m='1150680'>n</span> <span
  m='1150960'>minus</span> <span m='1151340'>1</span> <span
  m='1152500'>t1.</span> <span m='1155570'>And</span> <span
  m='1155940'>t1</span> <span m='1156440'>is</span> <span
  m='1156580'>just</span> <span m='1156900'>1.</span> <span
  m='1161950'>So</span> <span m='1162360'>I'm</span> <span
  m='1162460'>just</span> <span m='1162660'>getting</span> <span
  m='1162890'>the</span> <span m='1162970'>sum</span> <span
  m='1163390'>of</span> <span m='1163450'>the</span> <span
  m='1163530'>powers</span> <span m='1163980'>of</span> <span
  m='1164100'>2</span> <span m='1164660'>up</span> <span m='1164790'>to</span>
  <span m='1165130'>the</span> <span m='1165240'>n</span> <span
  m='1165380'>minus</span> <span m='1165690'>1.</span> <span
  m='1166810'>And</span> <span m='1167420'>we</span> <span
  m='1167530'>know</span> <span m='1167660'>what</span> <span
  m='1167790'>that</span> <span m='1168010'>is</span> <span
  m='1168260'>from</span> <span m='1169210'>last</span> <span
  m='1169530'>time,</span> <span m='1169720'>for</span> <span
  m='1169810'>sure.</span> <span m='1170180'>That's</span> <span
  m='1170370'>just</span> <span m='1170560'>2 to</span> <span
  m='1170740'>the</span> <span m='1170840'>n</span> <span
  m='1170960'>minus</span> <span m='1171250'>1.</span> </p><p><span
  m='1174000'>So</span> <span m='1174320'>we've</span> <span
  m='1174440'>derived</span> <span m='1175070'>the</span> <span
  m='1175280'>answer</span> <span m='1175710'>with</span> <span
  m='1175890'>only</span> <span m='1176130'>a</span> <span
  m='1176200'>little</span> <span m='1176430'>bit</span> <span
  m='1176570'>of</span> <span m='1176670'>a--</span> <span m='1177060'>we</span>
  <span m='1177180'>had</span> <span m='1177280'>to</span> <span
  m='1177340'>observe</span> <span m='1177820'>the</span> <span
  m='1177890'>pattern</span> <span m='1178420'>here,</span> <span
  m='1178930'>which</span> <span m='1179140'>is</span> <span
  m='1179280'>often</span> <span m='1179570'>easy</span> <span
  m='1179790'>to</span> <span m='1179880'>do.</span> <span
  m='1180310'>But</span> <span m='1180450'>now</span> <span
  m='1180590'>we've</span> <span m='1180720'>derived</span> <span
  m='1181730'>the</span> <span m='1181900'>answer.</span> <span
  m='1182980'>Now</span> <span m='1183730'>to</span> <span m='1183830'>be</span>
  <span m='1183960'>really</span> <span m='1184200'>safe,</span> <span
  m='1184520'>we've</span> <span m='1184590'>got</span> <span
  m='1184720'>to</span> <span m='1184780'>go</span> <span
  m='1184890'>back</span> <span m='1185170'>and</span> <span
  m='1185260'>still</span> <span m='1185510'>do</span> <span
  m='1185640'>verify,</span> <span m='1186260'>just</span> <span
  m='1186460'>to</span> <span m='1186540'>make</span> <span
  m='1186740'>sure</span> <span m='1187390'>that</span> <span
  m='1187510'>we</span> <span m='1187590'>didn't</span> <span
  m='1187760'>make</span> <span m='1187940'>a</span> <span
  m='1187980'>mistake</span> <span m='1188540'>in</span> <span
  m='1188640'>how</span> <span m='1188850'>we</span> <span
  m='1190120'>did</span> <span m='1190300'>the</span> <span
  m='1190360'>derivation</span> <span m='1190990'>here.</span> <span
  m='1193580'>OK?</span> <span m='1195610'>Any</span> <span
  m='1195770'>questions</span> <span m='1198100'>about</span> <span
  m='1198370'>that</span> <span m='1198540'>approach?</span> <span
  m='1199210'>You</span> <span m='1199300'>just</span> <span
  m='1199450'>keep</span> <span m='1199640'>plugging</span> <span
  m='1199990'>it</span> <span m='1200110'>back</span> <span
  m='1200370'>into</span> <span m='1200540'>the</span> <span
  m='1200630'>recurrence,</span> <span m='1201580'>look</span> <span
  m='1201790'>at</span> <span m='1201860'>the</span> <span
  m='1201930'>pattern</span> <span m='1202300'>you</span> <span
  m='1202390'>get,</span> <span m='1203370'>and</span> <span
  m='1203520'>try</span> <span m='1203670'>to</span> <span
  m='1203770'>guess</span> <span m='1204080'>it</span> <span
  m='1204180'>from</span> <span m='1204860'>that</span> <span
  m='1205030'>point</span> <span m='1205330'>and then</span> <span
  m='1205420'>solve.</span> </p><p><span m='1208040'>All right, let's</span>
  <span m='1208400'>do</span> <span m='1208580'>a</span> <span
  m='1208860'>little</span> <span m='1209100'>more</span> <span
  m='1209300'>interesting</span> <span m='1210480'>recurrence.</span> <span
  m='1213690'>This</span> <span m='1213830'>is</span> <span m='1213910'>a</span>
  <span m='1213960'>fairly</span> <span m='1214330'>famous</span> <span
  m='1214830'>one</span> <span m='1215100'>that</span> <span
  m='1215210'>comes</span> <span m='1215490'>up</span> <span
  m='1215680'>in</span> <span m='1215750'>a</span> <span m='1216090'>well</span>
  <span m='1216510'>known</span> <span m='1216770'>algorithm</span> <span
  m='1217210'>for</span> <span m='1217330'>sorting</span> <span
  m='1217920'>called</span> <span m='1218190'>merge</span> <span
  m='1218520'>sort.</span> <span m='1219780'>This</span> <span
  m='1219970'>is</span> <span m='1220080'>an</span> <span
  m='1220120'>algorithm</span> <span m='1220550'>you'll</span> <span
  m='1220660'>look</span> <span m='1220940'>at</span> <span
  m='1221480'>in</span> <span m='1221880'>6046,</span> <span
  m='1222890'>one</span> <span m='1223000'>of</span> <span
  m='1223060'>the</span> <span m='1223120'>many</span> <span
  m='1223630'>sorting</span> <span m='1224070'>algorithms</span> <span
  m='1224380'>you'll</span> <span m='1224550'>study</span> <span
  m='1225810'>when</span> <span m='1225970'>you</span> <span
  m='1226100'>take</span> <span m='1226360'>an</span> <span
  m='1226460'>algorithms</span> <span m='1226910'>class.</span> </p><p><span
  m='1239310'>So</span> <span m='1240340'>you're</span> <span
  m='1240480'>given</span> <span m='1240830'>n</span> <span
  m='1241090'>numbers</span> <span m='1241990'>and</span> <span
  m='1242140'>your</span> <span m='1242240'>task</span> <span
  m='1242820'>is</span> <span m='1242920'>to</span> <span
  m='1243010'>sort</span> <span m='1243380'>them,</span> <span
  m='1243740'>put</span> <span m='1243950'>them</span> <span
  m='1244100'>in</span> <span m='1244190'>order.</span> <span
  m='1245140'>And</span> <span m='1245340'>you're</span> <span
  m='1245450'>allowed</span> <span m='1245730'>to</span> <span
  m='1245790'>do</span> <span m='1245930'>comparisons</span> <span
  m='1246890'>between</span> <span m='1247240'>the</span> <span
  m='1247310'>numbers.</span> <span m='1248120'>You</span> <span
  m='1248260'>can</span> <span m='1248410'>think</span> <span
  m='1248620'>of</span> <span m='1248720'>them</span> <span
  m='1249240'>as</span> <span m='1249570'>you've</span> <span
  m='1249690'>got</span> <span m='1250330'>a</span> <span
  m='1250430'>list</span> <span m='1250670'>of</span> <span
  m='1250750'>names,</span> <span m='1251240'>putting</span> <span
  m='1251460'>them</span> <span m='1251560'>in</span> <span
  m='1251630'>alphabetical</span> <span m='1252180'>order.</span> <span
  m='1253380'>How</span> <span m='1253660'>many</span> <span
  m='1253840'>comparisons</span> <span m='1254560'>do</span> <span
  m='1254640'>you</span> <span m='1254720'>have</span> <span
  m='1254930'>to</span> <span m='1255020'>do</span> <span m='1255160'>to</span>
  <span m='1255240'>make</span> <span m='1255450'>that</span> <span
  m='1255640'>happen?</span> <span m='1257260'>And</span> <span
  m='1257400'>this</span> <span m='1257550'>is</span> <span
  m='1257650'>one</span> <span m='1257950'>way</span> <span
  m='1258110'>to</span> <span m='1258190'>do</span> <span m='1258390'>it</span>
  <span m='1258480'>that's</span> <span m='1258640'>very</span> <span
  m='1259100'>efficient.</span> </p><p><span m='1261360'>So</span> <span
  m='1261640'>to</span> <span m='1261720'>sort</span> <span m='1262920'>n</span>
  <span m='1264110'>items.</span> <span m='1265250'>In</span> <span
  m='1265380'>fact,</span> <span m='1265660'>we're</span> <span
  m='1265760'>going</span> <span m='1265860'>to</span> <span
  m='1265960'>look</span> <span m='1266060'>at</span> <span m='1266160'>n</span>
  <span m='1266230'>being</span> <span m='1266390'>a</span> <span
  m='1266440'>power</span> <span m='1266780'>of</span> <span
  m='1266860'>2.</span> <span m='1267910'>Call</span> <span
  m='1268220'>the</span> <span m='1268310'>items</span> <span
  m='1268600'>x1,</span> <span m='1269130'>x2,</span> <span
  m='1270740'>xn.</span> <span m='1273270'>n's</span> <span
  m='1273550'>going</span> <span m='1273670'>to</span> <span
  m='1273730'>be</span> <span m='1273790'>a</span> <span
  m='1273830'>power</span> <span m='1274090'>of</span> <span
  m='1274190'>2</span> <span m='1274555'>to</span> <span m='1274920'>make</span>
  <span m='1275070'>it</span> <span m='1275160'>simple</span> <span
  m='1276770'>for</span> <span m='1276890'>now.</span> <span
  m='1280440'>The</span> <span m='1280550'>first</span> <span
  m='1280860'>thing</span> <span m='1280980'>we're</span> <span
  m='1281070'>going</span> <span m='1281190'>to</span> <span
  m='1281260'>do</span> <span m='1281560'>is</span> <span
  m='1281820'>recursively</span> <span m='1282530'>sort</span> <span
  m='1284020'>the</span> <span m='1284120'>first</span> <span
  m='1284460'>half</span> <span m='1284680'>of</span> <span
  m='1284740'>the</span> <span m='1284830'>items</span> <span
  m='1286340'>and</span> <span m='1286490'>the</span> <span
  m='1286550'>second</span> <span m='1286910'>half.</span> <span
  m='1289860'>So</span> <span m='1290080'>we</span> <span m='1290300'>use</span>
  <span m='1290590'>recursion</span> <span m='1291180'>to</span> <span
  m='1291270'>short</span> <span m='1291780'>the</span> <span
  m='1291840'>first</span> <span m='1292130'>n</span> <span
  m='1292260'>over</span> <span m='1292370'>2</span> <span
  m='1292570'>items</span> <span m='1293960'>and</span> <span
  m='1294260'>the</span> <span m='1294330'>last</span> <span
  m='1294810'>n</span> <span m='1294950'>over</span> <span m='1295080'>2</span>
  <span m='1295280'>items.</span> <span m='1306290'>And</span> <span
  m='1306520'>then</span> <span m='1306750'>we're</span> <span
  m='1306860'>going</span> <span m='1306990'>to</span> <span
  m='1307060'>merge</span> <span m='1307630'>those</span> <span
  m='1307900'>two</span> <span m='1308090'>sorted</span> <span
  m='1308470'>lists</span> <span m='1308700'>together.</span> <span
  m='1312910'>So</span> <span m='1312950'>we're</span> <span
  m='1313010'>going</span> <span m='1313130'>to</span> <span
  m='1313190'>merge</span> <span m='1313600'>this</span> <span
  m='1313850'>list</span> <span m='1314170'>and</span> <span
  m='1314300'>that</span> <span m='1314520'>list.</span> </p><p><span
  m='1314830'>So</span> <span m='1315020'>let's</span> <span
  m='1315210'>see</span> <span m='1315380'>how</span> <span
  m='1315560'>this</span> <span m='1315760'>works</span> <span
  m='1317130'>and</span> <span m='1317220'>figure</span> <span
  m='1317510'>out</span> <span m='1317970'>how</span> <span
  m='1318160'>many</span> <span m='1318380'>comparisons</span> <span
  m='1319170'>we</span> <span m='1319290'>have</span> <span
  m='1319500'>to</span> <span m='1319590'>do</span> <span m='1320730'>to</span>
  <span m='1320850'>sort</span> <span m='1321140'>the</span> <span
  m='1321220'>list.</span> <span m='1329580'>For</span> <span
  m='1329720'>example,</span> <span m='1331670'>let's</span> <span
  m='1331880'>say</span> <span m='1332110'>we're</span> <span
  m='1332300'>sorting</span> <span m='1335000'>this</span> <span
  m='1335320'>list.</span> <span m='1336140'>10,</span> <span
  m='1337105'>7,</span> <span m='1337600'>23,</span> <span m='1339600'>5,</span>
  <span m='1341100'>2,</span> <span m='1342100'>4,</span> <span
  m='1342943'>3,</span> <span m='1344030'>and</span> <span m='1344220'>9.</span>
  <span m='1345260'>So</span> <span m='1345410'>I've</span> <span
  m='1345450'>got</span> <span m='1345700'>eight</span> <span
  m='1345960'>numbers</span> <span m='1347050'>that</span> <span
  m='1347210'>I'm</span> <span m='1347280'>going</span> <span
  m='1347400'>to</span> <span m='1347480'>sort.</span> <span
  m='1349420'>So</span> <span m='1349610'>the</span> <span
  m='1349700'>first</span> <span m='1350070'>step</span> <span
  m='1351030'>is</span> <span m='1351310'>to</span> <span
  m='1351480'>recursively</span> <span m='1352150'>sort</span> <span
  m='1352670'>that</span> <span m='1353070'>list.</span> <span
  m='1355110'>And</span> <span m='1355260'>when</span> <span
  m='1355380'>I</span> <span m='1355480'>do</span> <span
  m='1355710'>that,</span> <span m='1357290'>I</span> <span
  m='1357440'>produce,</span> <span m='1357735'>so</span> <span
  m='1358030'>I'm</span> <span m='1358180'>sorting</span> <span
  m='1359295'>10,</span> <span m='1360226'>7,</span> <span
  m='1361138'>23,</span> <span m='1362420'>5.</span> <span
  m='1364380'>And</span> <span m='1364510'>that</span> <span
  m='1364690'>produces,</span> <span m='1365770'>let's</span> <span
  m='1365860'>see,</span> <span m='1366860'>I'm</span> <span
  m='1366950'>going</span> <span m='1367070'>to</span> <span
  m='1367130'>get</span> <span m='1367290'>5,</span> <span m='1367626'>7,</span>
  <span m='1367962'>10,</span> <span m='1368300'>23.</span> <span
  m='1375050'>And</span> <span m='1375300'>then</span> <span
  m='1375530'>I</span> <span m='1375820'>recursively</span> <span
  m='1376350'>sort</span> <span m='1377480'>these</span> <span
  m='1377750'>guys.</span> <span m='1379200'>And</span> <span
  m='1379370'>that</span> <span m='1379560'>produces</span> <span
  m='1382170'>2,</span> <span m='1383080'>3,</span> <span m='1383930'>4,</span>
  <span m='1384750'>and</span> <span m='1384940'>9.</span> </p><p><span
  m='1388500'>I've</span> <span m='1388960'>done</span> <span
  m='1389270'>comparisons,</span> <span m='1390020'>but</span> <span
  m='1390160'>haven't</span> <span m='1390390'>counted</span> <span
  m='1390760'>them</span> <span m='1390850'>because</span> <span
  m='1391020'>they're</span> <span m='1391140'>in</span> <span
  m='1391230'>the</span> <span m='1391300'>recursion.</span> <span
  m='1392640'>Now</span> <span m='1392850'>I'm</span> <span
  m='1392950'>going</span> <span m='1393080'>to</span> <span
  m='1393140'>use</span> <span m='1393380'>comparisons</span> <span
  m='1394180'>to</span> <span m='1394280'>merge</span> <span
  m='1394800'>the</span> <span m='1394880'>lists,</span> <span
  m='1396210'>And</span> <span m='1396330'>the</span> <span
  m='1396390'>way</span> <span m='1396530'>I'm</span> <span
  m='1396610'>going</span> <span m='1396730'>to</span> <span
  m='1396790'>do</span> <span m='1397020'>that</span> <span
  m='1401470'>is</span> <span m='1401740'>to</span> <span
  m='1403050'>look</span> <span m='1403280'>at</span> <span
  m='1403350'>the</span> <span m='1403420'>smallest</span> <span
  m='1404200'>item</span> <span m='1404510'>in</span> <span
  m='1404590'>each</span> <span m='1404810'>list</span> <span
  m='1405600'>and</span> <span m='1405750'>compare</span> <span
  m='1406100'>them.</span> <span m='1408150'>Because</span> <span
  m='1408310'>I</span> <span m='1408380'>know</span> <span
  m='1408610'>the</span> <span m='1408710'>smallest</span> <span
  m='1409220'>item</span> <span m='1409450'>overall</span> <span
  m='1410150'>is</span> <span m='1410430'>either</span> <span
  m='1410660'>this</span> <span m='1410900'>one</span> <span
  m='1411050'>or</span> <span m='1411120'>that</span> <span
  m='1411360'>one.</span> </p><p><span m='1412220'>And</span> <span
  m='1412370'>when</span> <span m='1412490'>I</span> <span
  m='1412600'>compare</span> <span m='1413170'>2</span> <span
  m='1413360'>to</span> <span m='1413450'>5,</span> <span m='1415150'>2's</span>
  <span m='1415520'>the</span> <span m='1415600'>smaller</span> <span
  m='1416000'>one,</span> <span m='1416870'>so</span> <span m='1417070'>I</span>
  <span m='1417150'>start</span> <span m='1417610'>with</span> <span
  m='1417760'>2.</span> <span m='1419150'>And</span> <span m='1419330'>I</span>
  <span m='1420120'>strike</span> <span m='1420530'>it.</span> <span
  m='1422520'>What</span> <span m='1422740'>two</span> <span
  m='1422940'>items</span> <span m='1423230'>do</span> <span
  m='1423360'>I</span> <span m='1423480'>compare</span> <span
  m='1423910'>next</span> <span m='1424320'>to</span> <span
  m='1424420'>get</span> <span m='1424560'>the</span> <span
  m='1424630'>next</span> <span m='1424900'>smallest</span> <span
  m='1425310'>item?</span> <span m='1427360'>5</span> <span
  m='1427720'>and</span> <span m='1427790'>3.</span> <span
  m='1428550'>Smallest</span> <span m='1429030'>remaining</span> <span
  m='1429210'>guys.</span> <span m='1429520'>I</span> <span
  m='1429650'>get</span> <span m='1429850'>3.</span> <span
  m='1431110'>Scratch</span> <span m='1431510'>that</span> <span
  m='1431730'>guy.</span> </p><p><span m='1432960'>And</span> <span
  m='1433140'>I</span> <span m='1433220'>compare</span> <span
  m='1433600'>5</span> <span m='1433990'>and</span> <span m='1434120'>4.</span>
  <span m='1435290'>Get</span> <span m='1435520'>4,</span> <span
  m='1435940'>scratch</span> <span m='1436370'>him.</span> <span
  m='1438310'>And</span> <span m='1438490'>5</span> <span m='1438910'>and</span>
  <span m='1439050'>9.</span> <span m='1440610'>5</span> <span
  m='1440950'>is</span> <span m='1441010'>the</span> <span
  m='1441070'>smallest.</span> <span m='1442720'>7</span> <span
  m='1443130'>and</span> <span m='1443240'>9.</span> <span m='1445048'>7.</span>
  <span m='1445952'>9</span> <span m='1446410'>and</span> <span
  m='1446550'>10.</span> <span m='1449700'>And</span> <span
  m='1449900'>actually</span> <span m='1450320'>now</span> <span
  m='1451110'>I</span> <span m='1451270'>don't</span> <span
  m='1451540'>really</span> <span m='1451810'>have</span> <span
  m='1451920'>to</span> <span m='1451990'>do</span> <span m='1452170'>any</span>
  <span m='1452290'>more</span> <span m='1452470'>comparisons.</span> <span
  m='1453230'>All</span> <span m='1453450'>I've</span> <span
  m='1453540'>got</span> <span m='1453730'>is</span> <span
  m='1453840'>one</span> <span m='1454090'>list</span> <span
  m='1454380'>left.</span> <span m='1455360'>So</span> <span
  m='1455560'>I</span> <span m='1455630'>can</span> <span
  m='1455800'>just</span> <span m='1457560'>send</span> <span
  m='1457840'>these</span> <span m='1458010'>guys</span> <span
  m='1458270'>down.</span> <span m='1461330'>And</span> <span
  m='1461520'>I</span> <span m='1461600'>produced</span> <span
  m='1462020'>a</span> <span m='1462060'>sorted</span> <span
  m='1462420'>list.</span> </p><p><span m='1467050'>Now,</span> <span
  m='1469120'>how</span> <span m='1469440'>many</span> <span
  m='1469630'>comparisons</span> <span m='1470570'>do</span> <span
  m='1470710'>I</span> <span m='1470830'>have</span> <span m='1471170'>to</span>
  <span m='1471280'>do</span> <span m='1471490'>in</span> <span
  m='1471570'>the</span> <span m='1471640'>worst</span> <span
  m='1472020'>case</span> <span m='1473410'>if</span> <span
  m='1473680'>this</span> <span m='1473920'>is</span> <span m='1474080'>n</span>
  <span m='1474270'>over</span> <span m='1474480'>2</span> <span
  m='1474860'>items</span> <span m='1475290'>here</span> <span
  m='1476550'>and</span> <span m='1476760'>this</span> <span
  m='1476940'>is</span> <span m='1477060'>n</span> <span m='1477200'>over</span>
  <span m='1477360'>2</span> <span m='1477660'>here?</span> <span
  m='1480620'>How</span> <span m='1480840'>many</span> <span
  m='1481000'>comparisons</span> <span m='1481850'>do</span> <span
  m='1481970'>I</span> <span m='1482060'>have</span> <span m='1482310'>to</span>
  <span m='1482470'>do</span> <span m='1483710'>to</span> <span
  m='1483860'>produce</span> <span m='1484310'>the</span> <span
  m='1484530'>n</span> <span m='1484710'>item</span> <span
  m='1484960'>sorted</span> <span m='1485310'>list</span> <span
  m='1485710'>after</span> <span m='1486020'>I</span> <span
  m='1486080'>have</span> <span m='1486260'>the</span> <span m='1486400'>sub
  list</span> <span m='1486790'>sorted?</span> <span m='1489260'>What</span>
  <span m='1489410'>is</span> <span m='1489530'>it?</span> <span
  m='1490920'>n.</span> <span m='1491360'>Very</span> <span
  m='1491820'>close.</span> <span m='1493340'>n</span> <span
  m='1493590'>minus</span> <span m='1493900'>1</span> <span
  m='1494130'>is</span> <span m='1494370'>right,</span> <span
  m='1496070'>because</span> <span m='1497830'>every</span> <span
  m='1498050'>time</span> <span m='1498200'>I</span> <span m='1498260'>do</span>
  <span m='1498380'>a</span> <span m='1498430'>comparison</span> <span
  m='1499150'>I</span> <span m='1499240'>pull</span> <span m='1499520'>an</span>
  <span m='1499610'>item</span> <span m='1499830'>and</span> <span
  m='1499920'>stick</span> <span m='1500160'>it</span> <span
  m='1500230'>in</span> <span m='1500290'>the</span> <span
  m='1500330'>list.</span> </p><p><span m='1502420'>But</span> <span
  m='1502630'>once</span> <span m='1502910'>I</span> <span
  m='1503010'>get</span> <span m='1503190'>down</span> <span
  m='1503510'>to</span> <span m='1503580'>the</span> <span
  m='1503660'>very</span> <span m='1504180'>last</span> <span
  m='1504590'>item,</span> <span m='1505020'>just</span> <span
  m='1505270'>one</span> <span m='1505480'>guy</span> <span
  m='1505680'>sitting</span> <span m='1506040'>there,</span> <span
  m='1506980'>I</span> <span m='1507070'>don't</span> <span
  m='1507190'>have</span> <span m='1507290'>to</span> <span
  m='1507360'>do</span> <span m='1507490'>a</span> <span
  m='1507550'>comparison.</span> <span m='1507820'>It was</span> <span
  m='1508090'>just</span> <span m='1508330'>the</span> <span
  m='1508390'>last</span> <span m='1508680'>guy.</span> <span
  m='1508930'>I</span> <span m='1509010'>know</span> <span
  m='1509190'>he's</span> <span m='1509330'>the</span> <span
  m='1509400'>largest.</span> <span m='1511060'>So</span> <span
  m='1511810'>it</span> <span m='1511960'>could</span> <span
  m='1512110'>go</span> <span m='1512310'>up</span> <span m='1512440'>to</span>
  <span m='1512530'>n</span> <span m='1512790'>minus</span> <span
  m='1513170'>1</span> <span m='1513800'>in</span> <span m='1513960'>the</span>
  <span m='1514040'>worst</span> <span m='1514330'>case.</span> <span
  m='1515290'>In</span> <span m='1515480'>this</span> <span
  m='1515660'>situation,</span> <span m='1516340'>I</span> <span
  m='1516480'>actually</span> <span m='1516810'>did</span> <span
  m='1516990'>n</span> <span m='1517120'>minus</span> <span m='1517450'>2</span>
  <span m='1518340'>because</span> <span m='1518740'>I</span> <span
  m='1518810'>was</span> <span m='1518990'>left</span> <span
  m='1519210'>with</span> <span m='1519330'>two</span> <span
  m='1519520'>guys</span> <span m='1519810'>at</span> <span
  m='1519900'>the</span> <span m='1520010'>end,</span> <span
  m='1520180'>I</span> <span m='1520230'>just</span> <span
  m='1520430'>bring</span> <span m='1520590'>them</span> <span
  m='1520710'>down.</span> <span m='1521350'>But</span> <span
  m='1521530'>it</span> <span m='1521650'>might</span> <span
  m='1521940'>have</span> <span m='1522080'>been</span> <span
  m='1522460'>that</span> <span m='1522580'>the</span> <span
  m='1522660'>next</span> <span m='1523180'>largest</span> <span
  m='1523620'>thing</span> <span m='1523780'>to</span> <span
  m='1523860'>23</span> <span m='1524480'>was</span> <span
  m='1525160'>here</span> <span m='1525620'>and</span> <span
  m='1525630'>then</span> <span m='1525750'>I</span> <span
  m='1525790'>would</span> <span m='1525930'>have</span> <span
  m='1526020'>done</span> <span m='1526330'>n</span> <span
  m='1526500'>minus</span> <span m='1526810'>1.</span> <span
  m='1529660'>Any</span> <span m='1529840'>questions?</span> <span
  m='1531740'>Yeah.</span> </p><p><span m='1532540'>AUDIENCE:
  [INAUDIBLE].</span> <span m='1535380'>Would</span> <span
  m='1535840'>that</span> <span m='1536300'>make it</span> <span
  m='1536370'>faster?</span> </p><p><span m='1537640'>TOM LEIGHTON: Well,</span>
  <span m='1538250'>that's</span> <span m='1538510'>what's going</span> <span
  m='1538770'>to</span> <span m='1538990'>happen</span> <span
  m='1539510'>with</span> <span m='1539700'>the</span> <span
  m='1539780'>recursion.</span> <span m='1541300'>Because</span> <span
  m='1541510'>the</span> <span m='1541580'>first</span> <span
  m='1541880'>thing</span> <span m='1542020'>we're</span> <span
  m='1542120'>going</span> <span m='1542240'>to</span> <span
  m='1542310'>do</span> <span m='1542580'>is</span> <span
  m='1542700'>when</span> <span m='1542840'>we</span> <span
  m='1542960'>unfold</span> <span m='1543320'>the</span> <span
  m='1543390'>recursion</span> <span m='1543880'>is</span> <span
  m='1543990'>you're</span> <span m='1544050'>going</span> <span
  m='1544170'>to</span> <span m='1544230'>take</span> <span
  m='1544470'>the</span> <span m='1544540'>first</span> <span
  m='1544850'>half,</span> <span m='1545810'>split</span> <span
  m='1546230'>it</span> <span m='1546410'>in</span> <span
  m='1546560'>half,</span> <span m='1547610'>recursively</span> <span
  m='1548190'>sort</span> <span m='1548450'>them</span> <span
  m='1548520'>and</span> <span m='1548650'>then</span> <span
  m='1548830'>merge</span> <span m='1549160'>them.</span> <span
  m='1550090'>So</span> <span m='1550950'>the</span> <span
  m='1551110'>answer</span> <span m='1551410'>is</span> <span
  m='1551560'>that's</span> <span m='1551800'>going</span> <span
  m='1551930'>to</span> <span m='1552000'>happen,</span> <span
  m='1553020'>but</span> <span m='1553190'>we're</span> <span
  m='1553290'>sort</span> <span m='1553560'>of</span> <span
  m='1553650'>going</span> <span m='1553770'>to</span> <span
  m='1553890'>hide</span> <span m='1554300'>it</span> <span
  m='1554410'>by</span> <span m='1554570'>the</span> <span
  m='1554670'>recursion.</span> <span m='1556150'>All</span> <span
  m='1556280'>right,</span> <span m='1556470'>you</span> <span
  m='1556560'>didn't</span> <span m='1556770'>see</span> <span
  m='1557140'>me</span> <span m='1558020'>produce</span> <span
  m='1558860'>that</span> <span m='1559160'>sorted</span> <span
  m='1559500'>list.</span> <span m='1560430'>But</span> <span
  m='1560630'>I</span> <span m='1560690'>would</span> <span
  m='1560860'>have</span> <span m='1560960'>done</span> <span
  m='1561190'>it</span> <span m='1561930'>by</span> <span
  m='1562140'>taking</span> <span m='1562510'>10</span> <span
  m='1562720'>and</span> <span m='1562830'>7</span> <span
  m='1563190'>sorting</span> <span m='1563530'>them,</span> <span
  m='1563970'>5</span> <span m='1564200'>and</span> <span m='1564300'>23</span>
  <span m='1564760'>and</span> <span m='1564860'>sorting</span> <span
  m='1565150'>them</span> <span m='1565240'>and</span> <span
  m='1565330'>then</span> <span m='1565460'>merging</span> <span
  m='1565840'>them.</span> <span m='1567680'>OK,</span> <span
  m='1568010'>any</span> <span m='1568180'>other</span> <span
  m='1568340'>questions?</span> </p><p><span m='1571470'>All right,</span> <span
  m='1571760'>well</span> <span m='1571890'>let's</span> <span
  m='1572050'>set</span> <span m='1572230'>up</span> <span
  m='1572330'>the</span> <span m='1572420'>recursion</span> <span
  m='1572980'>to</span> <span m='1573050'>count</span> <span
  m='1573940'>how</span> <span m='1574200'>many</span> <span
  m='1574440'>comparisons</span> <span m='1575350'>are</span> <span
  m='1575510'>needed</span> <span m='1576230'>for</span> <span
  m='1576360'>the</span> <span m='1576460'>whole</span> <span
  m='1576830'>thing,</span> <span m='1577490'>not</span> <span
  m='1577660'>just</span> <span m='1578030'>the</span> <span
  m='1578120'>last</span> <span m='1578510'>merge</span> <span
  m='1578840'>phase.</span> <span m='1594200'>All</span> <span
  m='1594390'>right,</span> <span m='1594560'>so</span> <span
  m='1595600'>let's</span> <span m='1595850'>define.</span> <span
  m='1599250'>And</span> <span m='1599370'>instead</span> <span
  m='1599450'>of</span> <span m='1599640'>t sub</span> <span
  m='1599730'>n,</span> <span m='1600510'>I'm</span> <span
  m='1600600'>going</span> <span m='1600730'>to</span> <span
  m='1600800'>write</span> <span m='1601170'>t of</span> <span m='1601480'>n
  as</span> <span m='1601790'>a</span> <span m='1601840'>function.</span> <span
  m='1602620'>Makes</span> <span m='1602910'>no</span> <span
  m='1603120'>difference,</span> <span m='1603730'>but</span> <span
  m='1603780'>you'll</span> <span m='1603890'>see</span> <span
  m='1604110'>people</span> <span m='1604420'>do</span> <span
  m='1604570'>recurrences</span> <span m='1605150'>both</span> <span
  m='1605450'>ways.</span> <span m='1606440'>t of</span> <span
  m='1606610'>n</span> <span m='1606760'>or</span> <span m='1606930'>t</span>
  <span m='1607170'>sub n.</span> <span m='1608840'>It's</span> <span
  m='1608960'>going</span> <span m='1609080'>to</span> <span
  m='1609140'>be</span> <span m='1609210'>the</span> <span
  m='1609290'>number</span> <span m='1609730'>of</span> <span
  m='1609820'>comparisons.</span> <span m='1616180'>Use</span> <span
  m='1616550'>my</span> <span m='1616670'>merge</span> <span
  m='1617160'>sort</span> <span m='1617540'>to</span> <span
  m='1617700'>sort</span> <span m='1619560'>n</span> <span
  m='1620150'>numbers.</span> <span m='1622770'>In</span> <span
  m='1622950'>the</span> <span m='1623030'>worst</span> <span
  m='1623330'>case,</span> <span m='1624280'>worst</span> <span
  m='1624460'>case.</span> </p><p><span m='1627650'>All</span> <span
  m='1627800'>right,</span> <span m='1627980'>so</span> <span
  m='1628090'>we</span> <span m='1628210'>already</span> <span
  m='1628430'>know</span> <span m='1628650'>that</span> <span
  m='1628810'>merging</span> <span m='1634270'>takes</span> <span
  m='1634900'>n</span> <span m='1635120'>minus</span> <span m='1635470'>1</span>
  <span m='1635950'>comparisons</span> <span m='1640980'>in</span> <span
  m='1641100'>the</span> <span m='1641180'>worst</span> <span
  m='1641570'>case.</span> <span m='1643810'>And</span> <span
  m='1643980'>you</span> <span m='1644300'>always</span> <span
  m='1644610'>want</span> <span m='1644760'>to</span> <span
  m='1644820'>prepare</span> <span m='1645300'>for</span> <span
  m='1645400'>the</span> <span m='1645480'>worst</span> <span
  m='1645730'>case.</span> <span m='1649860'>How</span> <span
  m='1650110'>many</span> <span m='1650340'>comparisons</span> <span
  m='1651290'>are</span> <span m='1651520'>used</span> <span
  m='1653970'>in</span> <span m='1654120'>the</span> <span
  m='1654210'>recursive</span> <span m='1655010'>steps</span> <span
  m='1655570'>to</span> <span m='1655710'>sort</span> <span
  m='1656770'>this</span> <span m='1657140'>list and</span> <span
  m='1657570'>to</span> <span m='1657630'>sort</span> <span
  m='1657990'>that</span> <span m='1658260'>list,</span> <span
  m='1658590'>in</span> <span m='1658740'>general.</span> <span
  m='1661030'>tn</span> <span m='1661400'>over</span> <span m='1661620'>2</span>
  <span m='1663468'>to</span> <span m='1663930'>do</span> <span
  m='1664650'>this</span> <span m='1665000'>list</span> <span
  m='1667440'>times</span> <span m='1667810'>2.</span> <span
  m='1668400'>Because</span> <span m='1668580'>you've</span> <span
  m='1668680'>got</span> <span m='1668870'>two</span> <span
  m='1669120'>lists</span> <span m='1669470'>of</span> <span
  m='1669550'>size</span> <span m='1669870'>n</span> <span
  m='1670000'>over</span> <span m='1670150'>2.</span> <span
  m='1670520'>Two</span> <span m='1670920'>sub</span> <span
  m='1671320'>problems</span> <span m='1671400'>besides</span> <span
  m='1671630'>n</span> <span m='1671740'>over</span> <span m='1671880'>2.</span>
  <span m='1672430'>Each</span> <span m='1672750'>takes</span> <span
  m='1673160'>t</span> <span m='1673540'>of n</span> <span
  m='1673810'>over</span> <span m='1674060'>2.</span> </p><p><span
  m='1675650'>All right,</span> <span m='1675830'>so you've</span> <span
  m='1676040'>got</span> <span m='1676280'>2</span> <span m='1676800'>tn</span>
  <span m='1677150'>over</span> <span m='1677320'>2</span> <span
  m='1679020'>comparisons</span> <span m='1684030'>for</span> <span
  m='1684420'>the</span> <span m='1684730'>recursive</span> <span
  m='1685360'>sorting.</span> <span m='1693010'>That</span> <span
  m='1693370'>means</span> <span m='1693990'>that</span> <span
  m='1695720'>t</span> <span m='1695970'>of</span> <span m='1696020'>n</span>
  <span m='1697820'>equals</span> <span m='1698380'>2</span> <span
  m='1698910'>t</span> <span m='1699160'>of</span> <span m='1699290'>n</span>
  <span m='1699410'>over</span> <span m='1699620'>2</span> <span
  m='1701270'>plus</span> <span m='1702180'>n</span> <span
  m='1702410'>minus</span> <span m='1702760'>1.</span> <span
  m='1704850'>And</span> <span m='1705350'>we</span> <span
  m='1705440'>should</span> <span m='1705700'>say</span> <span
  m='1706010'>what</span> <span m='1706190'>t</span> <span m='1706340'>of</span>
  <span m='1706440'>1</span> <span m='1706640'>is.</span> <span
  m='1706960'>What's</span> <span m='1707422'>that?</span> <span
  m='1708808'>What's</span> <span m='1709270'>the</span> <span
  m='1709350'>time</span> <span m='1709670'>to</span> <span
  m='1709740'>sort?</span> <span m='1711390'>0.</span> <span
  m='1711960'>You</span> <span m='1712080'>don't</span> <span
  m='1712250'>do</span> <span m='1712380'>any</span> <span
  m='1712520'>comparisons</span> <span m='1713130'>if</span> <span
  m='1713210'>there's</span> <span m='1713360'>one</span> <span
  m='1713550'>item.</span> <span m='1714430'>So</span> <span
  m='1714540'>we'll</span> <span m='1714600'>set</span> <span
  m='1714860'>that</span> <span m='1715030'>as</span> <span
  m='1715150'>our</span> <span m='1715260'>base</span> <span
  m='1715520'>case.</span> </p><p><span m='1722180'>All</span> <span
  m='1722360'>right,</span> <span m='1722560'>so</span> <span
  m='1722700'>let's</span> <span m='1723460'>find</span> <span
  m='1723730'>the</span> <span m='1723840'>answer.</span> <span
  m='1726710'>So</span> <span m='1726790'>the</span> <span
  m='1726870'>first</span> <span m='1727260'>thing</span> <span
  m='1727450'>to</span> <span m='1727530'>always</span> <span
  m='1727890'>do</span> <span m='1728120'>when</span> <span
  m='1728260'>you</span> <span m='1728360'>see</span> <span m='1728610'>a</span>
  <span m='1728680'>recurrence</span> <span m='1729892'>is</span> <span
  m='1730700'>to</span> <span m='1732490'>take</span> <span m='1732780'>a</span>
  <span m='1732830'>few</span> <span m='1733060'>values,</span> <span
  m='1733560'>compute</span> <span m='1733880'>a</span> <span
  m='1733930'>few</span> <span m='1734100'>values,</span> <span
  m='1734560'>and</span> <span m='1734660'>try</span> <span
  m='1734810'>to</span> <span m='1735040'>guess</span> <span
  m='1735330'>the</span> <span m='1735470'>answer.</span> <span
  m='1737560'>So</span> <span m='1738190'>what's</span> <span
  m='1738570'>t</span> <span m='1738630'>of</span> <span m='1738730'>2?</span>
  <span m='1743020'>1.</span> <span m='1743660'>Plug</span> <span
  m='1743940'>it</span> <span m='1744010'>in.</span> <span m='1744930'>I</span>
  <span m='1745070'>get</span> <span m='1745310'>2t</span> <span
  m='1745710'>of</span> <span m='1745830'>1,</span> <span m='1746200'>t</span>
  <span m='1746340'>of</span> <span m='1746430'>1's</span> <span
  m='1746610'>0,</span> <span m='1747280'>plus</span> <span m='1747600'>2</span>
  <span m='1747760'>minus</span> <span m='1748050'>1.</span> <span
  m='1748220'>That's</span> <span m='1748450'>1.</span> <span
  m='1751530'>And</span> <span m='1751660'>we're</span> <span
  m='1751760'>only</span> <span m='1751890'>doing</span> <span
  m='1752100'>powers</span> <span m='1752480'>of</span> <span
  m='1752550'>4</span> <span m='1752850'>here.</span> <span
  m='1753490'>Sorry,</span> <span m='1753660'>powers</span> <span
  m='1753930'>of</span> <span m='1754020'>2.</span> <span m='1754310'>So</span>
  <span m='1754440'>I</span> <span m='1754480'>go</span> <span m='1754620'>to
  t</span> <span m='1754900'>of</span> <span m='1754950'>4</span> <span
  m='1755190'>next.</span> <span m='1755720'>What's</span> <span m='1756040'>t
  of</span> <span m='1756230'>4?</span> <span m='1762420'>5.</span> <span
  m='1764280'>Right,</span> <span m='1764750'>because</span> <span
  m='1764930'>I</span> <span m='1765020'>got</span> <span
  m='1765510'>double</span> <span m='1765890'>this</span> <span
  m='1766190'>is</span> <span m='1766310'>2</span> <span m='1767350'>plus</span>
  <span m='1767810'>4</span> <span m='1768070'>minus</span> <span
  m='1768410'>1.</span> <span m='1768670'>That's</span> <span
  m='1768850'>adding</span> <span m='1769150'>3.</span> <span
  m='1770080'>So</span> <span m='1770220'>I</span> <span m='1770260'>get</span>
  <span m='1770420'>5.</span> </p><p><span m='1772630'>All right,</span> <span
  m='1773040'>let's</span> <span m='1773460'>look</span> <span
  m='1773650'>at</span> <span m='1773750'>t</span> <span m='1773960'>of</span>
  <span m='1774160'>8.</span> <span m='1776500'>That's</span> <span
  m='1776730'>twice</span> <span m='1777160'>5</span> <span
  m='1779020'>plus</span> <span m='1779800'>8</span> <span
  m='1780050'>minus</span> <span m='1780380'>1.</span> <span
  m='1783380'>17.</span> <span m='1788320'>Not</span> <span
  m='1788500'>so</span> <span m='1788660'>clear</span> <span
  m='1788910'>what</span> <span m='1789040'>to</span> <span
  m='1789130'>guess</span> <span m='1789520'>here.</span> <span m='1791360'>We
  can</span> <span m='1791650'>try</span> <span m='1791840'>one</span> <span
  m='1792160'>more.</span> <span m='1794370'>T</span> <span
  m='1794530'>of</span> <span m='1794680'>16</span> <span
  m='1795350'>equals</span> <span m='1796480'>2</span> <span
  m='1796710'>times</span> <span m='1797030'>17</span> <span
  m='1797820'>plus</span> <span m='1798170'>16</span> <span
  m='1798730'>minus</span> <span m='1799120'>1</span> <span
  m='1799480'>equals</span> <span m='1801300'>34</span> <span
  m='1803490'>and</span> <span m='1803710'>15</span> <span m='1805990'>is</span>
  <span m='1806160'>49.</span> <span m='1807280'>Is</span> <span
  m='1807370'>that</span> <span m='1807520'>right?</span> <span
  m='1809450'>34</span> <span m='1809970'>and</span> <span
  m='1810376'>15.</span> </p><p><span m='1813460'>Any</span> <span
  m='1814080'>guesses?</span> <span m='1818780'>You're</span> <span
  m='1819020'>not going</span> <span m='1819200'>to guess</span> <span
  m='1819390'>this.</span> <span m='1820770'>That's</span> <span
  m='1820970'>not</span> <span m='1821160'>going to</span> <span
  m='1821440'>work.</span> <span m='1821770'>That</span> <span
  m='1821940'>happens.</span> <span m='1823248'>And</span> <span
  m='1823393'>a</span> <span m='1823538'>miracle</span> <span
  m='1823684'>could</span> <span m='1824120'>happen,</span> <span
  m='1824250'>you</span> <span m='1824350'>get</span> <span m='1824480'>a</span>
  <span m='1824510'>divine</span> <span m='1824840'>insight</span> <span
  m='1825160'>and</span> <span m='1825270'>guess</span> <span
  m='1825560'>it,</span> <span m='1825660'>but</span> <span m='1825810'>I</span>
  <span m='1826010'>think</span> <span m='1826180'>it's</span> <span
  m='1826300'>not</span> <span m='1826520'>likely.</span> </p><p><span
  m='1828730'>All</span> <span m='1828910'>right,</span> <span
  m='1829140'>so</span> <span m='1829550'>let's</span> <span
  m='1829790'>go</span> <span m='1829930'>to</span> <span
  m='1830020'>plug</span> <span m='1830290'>and</span> <span
  m='1830390'>chug.</span> <span m='1833180'>See</span> <span
  m='1833290'>if</span> <span m='1833420'>that</span> <span
  m='1833660'>works.</span> <span m='1844370'>All</span> <span
  m='1844540'>right,</span> <span m='1844680'>so</span> <span
  m='1844790'>now</span> <span m='1845410'>plug</span> <span
  m='1845650'>and</span> <span m='1845760'>chug.</span> <span m='1851620'>All
  right,</span> <span m='1851940'>so we</span> <span m='1852070'>write</span>
  <span m='1852340'>down</span> <span m='1852620'>t</span> <span
  m='1852900'>of</span> <span m='1853000'>n</span> <span m='1854270'>is--</span>
  <span m='1854940'>and</span> <span m='1855080'>you</span> <span
  m='1855160'>always</span> <span m='1855430'>write</span> <span
  m='1855600'>their</span> <span m='1855720'>current</span> <span
  m='1856190'>part</span> <span m='1856510'>last</span> <span
  m='1856950'>for</span> <span m='1857070'>plug</span> <span
  m='1857310'>and</span> <span m='1857430'>chug</span> <span
  m='1857670'>to</span> <span m='1857740'>keep</span> <span
  m='1857990'>it</span> <span m='1858070'>simpler.</span> <span
  m='1859830'>2</span> <span m='1860260'>t of</span> <span m='1860585'>n</span>
  <span m='1861100'>over</span> <span m='1861300'>2.</span> <span
  m='1863790'>And</span> <span m='1864020'>then</span> <span
  m='1864200'>I</span> <span m='1864480'>substitute,</span> <span
  m='1865350'>I</span> <span m='1865410'>plug in</span> <span
  m='1866070'>for</span> <span m='1866200'>t of</span> <span
  m='1866500'>n</span> <span m='1866590'>over</span> <span m='1866730'>2.</span>
  <span m='1868310'>So</span> <span m='1868440'>I</span> <span
  m='1868470'>have</span> <span m='1868590'>n</span> <span
  m='1868740'>minus</span> <span m='1869120'>1</span> <span
  m='1869540'>plus</span> <span m='1869920'>2</span> <span m='1872080'>n</span>
  <span m='1872350'>over</span> <span m='1872580'>2</span> <span
  m='1873480'>minus</span> <span m='1873930'>1</span> <span
  m='1874290'>plus</span> <span m='1875030'>2</span> <span m='1875460'>t</span>
  <span m='1875905'>of</span> <span m='1876350'>n</span> <span
  m='1876560'>over</span> <span m='1876770'>4.</span> </p><p><span
  m='1879410'>Then</span> <span m='1879560'>I</span> <span
  m='1879740'>chug.</span> <span m='1882010'>So</span> <span m='1882150'>I
  have</span> <span m='1882230'>n</span> <span m='1882400'>minus</span> <span
  m='1882720'>1</span> <span m='1883110'>plus</span> <span
  m='1884670'>that's</span> <span m='1884970'>n</span> <span
  m='1886510'>minus</span> <span m='1886860'>2.</span> <span
  m='1888710'>Plus</span> <span m='1889000'>4</span> <span m='1889940'>tn</span>
  <span m='1890270'>over</span> <span m='1890420'>4.</span> <span
  m='1893950'>All</span> <span m='1894140'>right,</span> <span
  m='1894370'>then</span> <span m='1894520'>we'll</span> <span m='1894630'>plug
  in</span> <span m='1895110'>here.</span> <span m='1901630'>And</span> <span
  m='1901750'>I</span> <span m='1901800'>get</span> <span m='1902020'>n</span>
  <span m='1902210'>over</span> <span m='1902430'>4</span> <span
  m='1903190'>minus</span> <span m='1903610'>1</span> <span
  m='1904040'>plus</span> <span m='1905560'>4</span> <span m='1906440'>tn</span>
  <span m='1906940'>over</span> <span m='1907210'>8.</span> <span
  m='1910510'>And</span> <span m='1910730'>now</span> <span
  m='1910930'>we</span> <span m='1911070'>chug.</span> <span
  m='1917180'>That's</span> <span m='1917670'>an</span> <span
  m='1917880'>n</span> <span m='1918240'>here</span> <span
  m='1919230'>minus</span> <span m='1919630'>a</span> <span
  m='1919680'>4.</span> <span m='1923080'>I</span> <span m='1923330'>did</span>
  <span m='1923490'>something</span> <span m='1923830'>wrong.</span> <span
  m='1924580'>That</span> <span m='1924870'>should</span> <span
  m='1925050'>be</span> <span m='1925150'>2.</span> <span m='1926670'>4</span>
  <span m='1926850'>times</span> <span m='1927130'>2</span> <span
  m='1927330'>is</span> <span m='1927580'>8</span> <span m='1928890'>tn</span>
  <span m='1929090'>over</span> <span m='1929230'>8.</span> </p><p><span
  m='1932590'>All right,</span> <span m='1932880'>can</span> <span
  m='1933040'>you</span> <span m='1933120'>start</span> <span
  m='1933460'>to</span> <span m='1933560'>guess</span> <span
  m='1934060'>the</span> <span m='1934170'>pattern</span> <span
  m='1934730'>here</span> <span m='1935080'>maybe?</span> <span
  m='1937470'>We</span> <span m='1937860'>probably</span> <span
  m='1938200'>should</span> <span m='1938330'>do</span> <span
  m='1938450'>one</span> <span m='1938770'>more</span> <span
  m='1938960'>to</span> <span m='1939030'>be</span> <span
  m='1939120'>safe.</span> <span m='1939820'>But</span> <span
  m='1939990'>you</span> <span m='1940060'>got</span> <span
  m='1940230'>an</span> <span m='1940310'>n</span> <span
  m='1940460'>minus</span> <span m='1940810'>1</span> <span
  m='1942090'>plus</span> <span m='1942340'>an n</span> <span
  m='1942570'>minus</span> <span m='1942890'>2</span> <span
  m='1943710'>plus</span> <span m='1943910'>an n</span> <span
  m='1944160'>minus</span> <span m='1944490'>4.</span> <span
  m='1945850'>And</span> <span m='1945970'>if</span> <span m='1946060'>we</span>
  <span m='1946160'>do</span> <span m='1946300'>one</span> <span
  m='1946630'>more,</span> <span m='1947500'>what's</span> <span
  m='1947750'>the</span> <span m='1947820'>next</span> <span
  m='1948020'>term</span> <span m='1948220'>going</span> <span
  m='1948340'>to</span> <span m='1948410'>be?</span> <span m='1949820'>n</span>
  <span m='1950070'>minus</span> <span m='1950450'>8.</span> <span
  m='1951720'>And</span> <span m='1951870'>this</span> <span
  m='1952030'>is</span> <span m='1952120'>looking</span> <span
  m='1952400'>pretty</span> <span m='1952650'>simple.</span> <span
  m='1953530'>So</span> <span m='1953770'>we</span> <span
  m='1953880'>could</span> <span m='1954390'>guess</span> <span
  m='1954860'>now</span> <span m='1955140'>that</span> <span
  m='1955260'>the</span> <span m='1955340'>pattern</span> <span
  m='1955800'>is</span> <span m='1958840'>n</span> <span
  m='1959120'>minus</span> <span m='1959460'>1</span> <span
  m='1959830'>plus</span> <span m='1960130'>n</span> <span
  m='1960290'>minus</span> <span m='1960650'>2</span> <span
  m='1961110'>plus</span> <span m='1962370'>n</span> <span
  m='1962820'>minus</span> <span m='1963220'>4</span> <span
  m='1964650'>all</span> <span m='1964880'>the</span> <span
  m='1964950'>way</span> <span m='1965070'>out</span> <span
  m='1965190'>to</span> <span m='1965270'>plus</span> <span m='1965650'>n</span>
  <span m='1965930'>minus</span> <span m='1967000'>2</span> <span
  m='1967210'>to</span> <span m='1967300'>the</span> <span m='1967470'>i</span>
  <span m='1967710'>minus</span> <span m='1968060'>1</span> <span
  m='1969290'>plus</span> <span m='1969740'>2</span> <span m='1969970'>to</span>
  <span m='1970060'>the</span> <span m='1970270'>i</span> <span
  m='1971060'>t</span> <span m='1971980'>n</span> <span m='1972300'>over</span>
  <span m='1972640'>2</span> <span m='1972900'>to the</span> <span
  m='1973050'>i.</span> </p><p><span m='1975350'>And</span> <span
  m='1975520'>now</span> <span m='1975710'>we</span> <span m='1975810'>go</span>
  <span m='1975940'>all</span> <span m='1976220'>the</span> <span
  m='1976290'>way</span> <span m='1976450'>down</span> <span
  m='1976850'>where</span> <span m='1977160'>i</span> <span
  m='1977350'>equals</span> <span m='1977820'>log</span> <span
  m='1978120'>n,</span> <span m='1978760'>base</span> <span
  m='1979040'>2,</span> <span m='1981390'>and</span> <span
  m='1981750'>see</span> <span m='1981930'>what</span> <span
  m='1982060'>we</span> <span m='1982150'>get.</span> <span m='1985810'>1</span>
  <span m='1986430'>plus</span> <span m='1986670'>n</span> <span
  m='1986810'>minus</span> <span m='1987120'>2</span> <span
  m='1988310'>plus</span> <span m='1988750'>all</span> <span
  m='1988920'>the</span> <span m='1988990'>way</span> <span
  m='1989120'>down</span> <span m='1990170'>n</span> <span
  m='1990560'>minus</span> <span m='1991040'>2</span> <span
  m='1991390'>to</span> <span m='1991490'>the</span> <span
  m='1991640'>log</span> <span m='1992680'>n</span> <span
  m='1993060'>minus</span> <span m='1993490'>1</span> <span
  m='1994630'>plus</span> <span m='1996200'>2</span> <span m='1996520'>to</span>
  <span m='1996610'>the</span> <span m='1996700'>log</span> <span
  m='1997000'>n</span> <span m='1999400'>t</span> <span m='2000170'>of</span>
  <span m='2000290'>1.</span> <span m='2002270'>What's</span> <span
  m='2002530'>t</span> <span m='2002710'>of</span> <span m='2002820'>1?</span>
  <span m='2005070'>0.</span> <span m='2005780'>That's</span> <span
  m='2006090'>nice.</span> <span m='2006460'>That</span> <span
  m='2006640'>goes</span> <span m='2006870'>away.</span> <span
  m='2008680'>All</span> <span m='2008830'>right,</span> <span
  m='2009010'>so</span> <span m='2009110'>this</span> <span
  m='2009340'>is</span> <span m='2009420'>not</span> <span
  m='2009620'>looking</span> <span m='2009890'>so</span> <span
  m='2010240'>bad.</span> <span m='2011640'>This</span> <span
  m='2011940'>equals</span> <span m='2012360'>the</span> <span
  m='2012460'>sum</span> <span m='2014430'>i</span> <span
  m='2014790'>equals</span> <span m='2015250'>0</span> <span
  m='2016370'>to</span> <span m='2016550'>log</span> <span m='2017050'>n</span>
  <span m='2017750'>minus</span> <span m='2018160'>1</span> <span
  m='2020045'>of</span> <span m='2020310'>n</span> <span
  m='2020710'>minus</span> <span m='2021920'>2</span> <span
  m='2022120'>to</span> <span m='2022200'>the</span> <span m='2022360'>i.</span>
  <span m='2025420'>All</span> <span m='2025590'>right,</span> <span
  m='2025830'>and this</span> <span m='2025960'>will</span> <span
  m='2026050'>be</span> <span m='2026120'>good</span> <span
  m='2026310'>practice</span> <span m='2026810'>maybe</span> <span
  m='2027100'>for</span> <span m='2028470'>towards</span> <span
  m='2028770'>the</span> <span m='2028860'>test.</span> <span
  m='2029850'>Well,</span> <span m='2030000'>I</span> <span
  m='2030130'>can</span> <span m='2030270'>split</span> <span
  m='2030580'>that</span> <span m='2030790'>sum</span> <span
  m='2031080'>up.</span> <span m='2032346'>i</span> <span
  m='2033190'>equals</span> <span m='2033630'>0</span> <span
  m='2034180'>to</span> <span m='2034350'>log</span> <span m='2034740'>n</span>
  <span m='2034880'>minus</span> <span m='2035260'>1</span> <span
  m='2036230'>of</span> <span m='2036720'>n</span> <span
  m='2037960'>minus</span> <span m='2038590'>the</span> <span
  m='2039770'>i</span> <span m='2040080'>equals</span> <span
  m='2040560'>0</span> <span m='2041740'>log</span> <span m='2042160'>n</span>
  <span m='2042380'>minus</span> <span m='2042740'>1</span> <span
  m='2043050'>of</span> <span m='2043180'>2</span> <span m='2043430'>to
  the</span> <span m='2043600'>i.</span> </p><p><span m='2046841'>Well,</span>
  <span m='2047310'>this</span> <span m='2047490'>is</span> <span
  m='2047620'>easy.</span> <span m='2047940'>I'm</span> <span
  m='2048070'>just</span> <span m='2048310'>adding</span> <span
  m='2048760'>n</span> <span m='2049100'>up</span> <span m='2049920'>a</span>
  <span m='2050030'>total</span> <span m='2050440'>of</span> <span
  m='2050540'>log</span> <span m='2051020'>n times.</span> <span
  m='2052639'>So</span> <span m='2052780'>I</span> <span m='2052810'>have</span>
  <span m='2052920'>n log</span> <span m='2053320'>n.</span> <span
  m='2057150'>This</span> <span m='2057530'>is</span> <span
  m='2057659'>just</span> <span m='2057980'>something</span> <span
  m='2058260'>the</span> <span m='2058340'>powers</span> <span
  m='2058730'>of</span> <span m='2058830'>2</span> <span
  m='2059050'>which</span> <span m='2059239'>we</span> <span
  m='2059880'>know</span> <span m='2060040'>how</span> <span
  m='2060120'>to</span> <span m='2060219'>do.</span> <span m='2060460'>So</span>
  <span m='2060590'>that's</span> <span m='2060810'>going</span> <span
  m='2060929'>to</span> <span m='2061000'>be</span> <span m='2061969'>2</span>
  <span m='2062070'>to</span> <span m='2062260'>the</span> <span
  m='2062360'>log</span> <span m='2062630'>n</span> <span
  m='2064230'>minus</span> <span m='2064620'>1.</span> <span
  m='2066659'>And</span> <span m='2066820'>so</span> <span m='2066929'>we</span>
  <span m='2067030'>get</span> <span m='2067199'>our</span> <span
  m='2067350'>answer</span> <span m='2068980'>is</span> <span
  m='2069570'>n</span> <span m='2070340'>log</span> <span m='2070610'>n</span>
  <span m='2072389'>minus</span> <span m='2073520'>2</span> <span
  m='2073730'>the</span> <span m='2073810'>log</span> <span m='2074000'>n</span>
  <span m='2074260'>is</span> <span m='2074360'>just</span> <span
  m='2074600'>n</span> <span m='2076270'>minus</span> <span m='2076620'>1</span>
  <span m='2076750'>is</span> <span m='2076820'>a</span> <span
  m='2076870'>plus</span> <span m='2077100'>1.</span> </p><p><span
  m='2079710'>Well,</span> <span m='2079909'>we</span> <span
  m='2079989'>derived</span> <span m='2080520'>an</span> <span
  m='2080610'>answer.</span> <span m='2083670'>Let's</span> <span
  m='2083860'>just</span> <span m='2084030'>go</span> <span
  m='2084139'>back</span> <span m='2084389'>and</span> <span
  m='2084500'>check</span> <span m='2084820'>some</span> <span
  m='2084980'>of</span> <span m='2085050'>the</span> <span
  m='2085110'>values.</span> <span m='2087060'>n</span> <span
  m='2087239'>equals</span> <span m='2087570'>1.</span> <span
  m='2088870'>That's</span> <span m='2089139'>0</span> <span
  m='2089760'>and</span> <span m='2089880'>I</span> <span m='2089920'>get</span>
  <span m='2090080'>1</span> <span m='2090300'>minus</span> <span
  m='2090639'>1.</span> <span m='2090850'>It</span> <span
  m='2090940'>works.</span> <span m='2092630'>n</span> <span
  m='2092909'>equals</span> <span m='2093340'>2.</span> <span
  m='2095159'>2</span> <span m='2095420'>log</span> <span m='2095909'>2</span>
  <span m='2096440'>is</span> <span m='2096580'>2</span> <span
  m='2097380'>minus</span> <span m='2097830'>2</span> <span
  m='2098100'>plus</span> <span m='2098440'>1.</span> <span
  m='2100040'>Works.</span> <span m='2101360'>Plug in</span> <span
  m='2101810'>4,</span> <span m='2102360'>I</span> <span m='2102440'>get</span>
  <span m='2102630'>4</span> <span m='2103230'>log</span> <span
  m='2103590'>4</span> <span m='2103910'>is</span> <span m='2104130'>8</span>
  <span m='2104820'>minus</span> <span m='2105210'>4</span> <span
  m='2105850'>is</span> <span m='2106030'>4</span> <span m='2106340'>plus</span>
  <span m='2106600'>1</span> <span m='2106780'>is</span> <span
  m='2106910'>5.</span> <span m='2107900'>So</span> <span m='2108120'>it</span>
  <span m='2108220'>works</span> <span m='2109200'>for</span> <span
  m='2109300'>those</span> <span m='2109500'>examples.</span> </p><p><span
  m='2110060'>Now,</span> <span m='2110660'>to</span> <span
  m='2110770'>be</span> <span m='2110890'>really</span> <span
  m='2111200'>careful</span> <span m='2112520'>we</span> <span
  m='2112680'>should</span> <span m='2112870'>prove</span> <span
  m='2113090'>it</span> <span m='2113180'>by</span> <span
  m='2113390'>induction.</span> <span m='2114690'>Because</span> <span
  m='2115650'>when</span> <span m='2115830'>you</span> <span
  m='2115910'>do</span> <span m='2116090'>enough</span> <span
  m='2116330'>of</span> <span m='2116400'>these</span> <span
  m='2116640'>equations,</span> <span m='2117170'>you</span> <span
  m='2117240'>make</span> <span m='2117420'>mistakes</span> <span
  m='2117850'>like</span> <span m='2118140'>I</span> <span
  m='2118320'>invariably</span> <span m='2118830'>do</span> <span
  m='2118980'>even</span> <span m='2119270'>up</span> <span
  m='2119400'>here.</span> <span m='2119920'>And</span> <span
  m='2120050'>even</span> <span m='2120240'>though</span> <span
  m='2120350'>it's</span> <span m='2120470'>written</span> <span
  m='2120760'>down</span> <span m='2121020'>here,</span> <span
  m='2121590'>I'll</span> <span m='2121740'>make</span> <span
  m='2121930'>mistakes</span> <span m='2122600'>writing</span> <span
  m='2122960'>it on</span> <span m='2123050'>the</span> <span
  m='2123120'>board.</span> <span m='2123840'>And</span> <span
  m='2123970'>so</span> <span m='2124060'>you</span> <span
  m='2124140'>want</span> <span m='2124300'>to</span> <span
  m='2124360'>check</span> <span m='2125330'>by</span> <span
  m='2125980'>induction.</span> </p><p><span m='2130310'>OK,</span> <span
  m='2130670'>so</span> <span m='2131080'>this</span> <span
  m='2131290'>is</span> <span m='2131390'>the</span> <span
  m='2131510'>answer.</span> <span m='2131880'>This</span> <span
  m='2131970'>is</span> <span m='2132080'>how</span> <span
  m='2132290'>many</span> <span m='2132940'>comparisons</span> <span
  m='2133800'>are</span> <span m='2133870'>done</span> <span
  m='2134870'>in</span> <span m='2135050'>merge</span> <span
  m='2135360'>sort.</span> <span m='2136600'>And</span> <span
  m='2136770'>the</span> <span m='2136830'>nice</span> <span
  m='2137120'>thing</span> <span m='2137320'>is</span> <span
  m='2137720'>this</span> <span m='2137920'>is</span> <span
  m='2138050'>growing</span> <span m='2139250'>nearly</span> <span
  m='2139730'>linearly.</span> <span m='2140550'>It</span> <span
  m='2140710'>grows</span> <span m='2140980'>as</span> <span
  m='2141110'>n</span> <span m='2141240'>log</span> <span m='2141390'>n.</span>
  <span m='2141810'>And</span> <span m='2141940'>that's</span> <span
  m='2142210'>why</span> <span m='2142420'>this</span> <span
  m='2142610'>algorithm</span> <span m='2142990'>is</span> <span
  m='2143080'>used</span> <span m='2143310'>a</span> <span
  m='2143360'>lot</span> <span m='2143560'>in</span> <span
  m='2143630'>practice.</span> <span m='2144510'>Much</span> <span
  m='2144920'>better</span> <span m='2145250'>than</span> <span
  m='2145380'>comparing</span> <span m='2145880'>every</span> <span
  m='2146080'>item</span> <span m='2146330'>to</span> <span
  m='2146410'>every</span> <span m='2146620'>other</span> <span
  m='2146850'>item,</span> <span m='2147130'>which</span> <span
  m='2147290'>would</span> <span m='2147380'>be</span> <span
  m='2147450'>more</span> <span m='2147620'>like</span> <span
  m='2147850'>n</span> <span m='2148050'>squared</span> <span
  m='2148450'>steps.</span> <span m='2150000'>So</span> <span
  m='2150110'>much</span> <span m='2150320'>better</span> <span
  m='2150520'>than</span> <span m='2150640'>a</span> <span
  m='2150730'>naive</span> <span m='2151340'>sorting</span> <span
  m='2151720'>algorithm.</span> <span m='2154270'>Any</span> <span
  m='2154470'>questions</span> <span m='2156710'>about</span> <span
  m='2156980'>what</span> <span m='2157080'>we</span> <span
  m='2157180'>did</span> <span m='2157370'>there?</span> </p><p><span
  m='2159060'>Just</span> <span m='2159510'>one</span> <span
  m='2160520'>rule</span> <span m='2160810'>of</span> <span
  m='2160900'>thumb</span> <span m='2162240'>when</span> <span
  m='2162410'>you're</span> <span m='2162530'>doing</span> <span
  m='2162840'>the</span> <span m='2162920'>plug</span> <span
  m='2163230'>and</span> <span m='2163350'>chug.</span> <span
  m='2165240'>Notice</span> <span m='2165700'>that</span> <span
  m='2165820'>I</span> <span m='2165920'>didn't</span> <span
  m='2166310'>try</span> <span m='2166600'>to</span> <span
  m='2167730'>collapse</span> <span m='2168260'>terms</span> <span
  m='2168630'>along</span> <span m='2168970'>the</span> <span
  m='2169050'>way.</span> <span m='2170870'>It</span> <span
  m='2171000'>makes</span> <span m='2171230'>it</span> <span
  m='2171300'>easier</span> <span m='2171730'>sometimes</span> <span
  m='2172080'>to</span> <span m='2172160'>see</span> <span
  m='2172330'>the</span> <span m='2172440'>pattern.</span> <span
  m='2173470'>I</span> <span m='2173620'>left</span> <span m='2173960'>it</span>
  <span m='2174040'>as</span> <span m='2174180'>n</span> <span
  m='2174330'>minus</span> <span m='2174660'>1</span> <span
  m='2174860'>plus</span> <span m='2175100'>n</span> <span
  m='2175220'>minus</span> <span m='2175520'>2</span> <span
  m='2175830'>and</span> <span m='2175930'>then</span> <span
  m='2176060'>plus</span> <span m='2176400'>n</span> <span
  m='2176550'>minus</span> <span m='2176830'>4</span> <span
  m='2177570'>rather</span> <span m='2177900'>than</span> <span
  m='2178070'>saying,</span> <span m='2178530'>oh,</span> <span
  m='2178550'>this</span> <span m='2178770'>is</span> <span m='2178880'>3</span>
  <span m='2179210'>n</span> <span m='2179350'>minus</span> <span
  m='2179670'>7,</span> <span m='2181020'>which</span> <span
  m='2181280'>might</span> <span m='2181550'>have</span> <span
  m='2181640'>made</span> <span m='2181810'>it</span> <span
  m='2181880'>harder</span> <span m='2182150'>to</span> <span
  m='2182240'>guess</span> <span m='2182500'>the</span> <span
  m='2182570'>pattern.</span> <span m='2183560'>So</span> <span
  m='2183740'>you</span> <span m='2183800'>don't</span> <span
  m='2184040'>always,</span> <span m='2184520'>when</span> <span
  m='2184810'>you're doing the</span> <span m='2184870'>chugging,</span> <span
  m='2185670'>collapse</span> <span m='2186130'>everything</span> <span
  m='2186500'>down.</span> <span m='2186810'>You</span> <span
  m='2186890'>want</span> <span m='2187040'>to</span> <span
  m='2187100'>try</span> <span m='2187330'>and</span> <span
  m='2187440'>see</span> <span m='2187550'>if</span> <span
  m='2187610'>there</span> <span m='2187710'>are</span> <span
  m='2187740'>some.</span> <span m='2188440'>Because</span> <span
  m='2188600'>this</span> <span m='2188740'>is</span> <span
  m='2188800'>the</span> <span m='2188860'>amount</span> <span
  m='2189020'>of</span> <span m='2189110'>work</span> <span
  m='2189310'>done</span> <span m='2189440'>at</span> <span
  m='2189510'>each</span> <span m='2189660'>step,</span> <span m='2190050'>and
  you</span> <span m='2190150'>want</span> <span m='2190310'>to</span> <span
  m='2190370'>see</span> <span m='2190500'>if</span> <span
  m='2190590'>you</span> <span m='2190650'>can</span> <span
  m='2190770'>see</span> <span m='2190940'>a</span> <span
  m='2191010'>pattern</span> <span m='2191410'>in</span> <span
  m='2191520'>that.</span> </p><p><span m='2197070'>All</span> <span
  m='2197190'>right,</span> <span m='2197310'>so</span> <span
  m='2197410'>let's</span> <span m='2197650'>write</span> <span
  m='2197890'>down</span> <span m='2198130'>our</span> <span
  m='2198240'>two</span> <span m='2198500'>recurrences</span> <span
  m='2199250'>and</span> <span m='2200920'>sort</span> <span
  m='2201160'>of</span> <span m='2201220'>compare</span> <span
  m='2201600'>them.</span> <span m='2212870'>So</span> <span
  m='2213110'>first</span> <span m='2213610'>we</span> <span
  m='2213720'>did</span> <span m='2213970'>Towers</span> <span
  m='2214410'>of</span> <span m='2214540'>Hanoi,</span> <span
  m='2215680'>which</span> <span m='2215940'>was</span> <span
  m='2216120'>t</span> <span m='2216390'>of</span> <span m='2216450'>n</span>
  <span m='2217000'>equals</span> <span m='2217430'>2</span> <span
  m='2218600'>t</span> <span m='2218840'>of</span> <span m='2218950'>n</span>
  <span m='2219110'>minus</span> <span m='2219450'>1</span> <span
  m='2220520'>plus</span> <span m='2220870'>1.</span> <span
  m='2222380'>And</span> <span m='2222490'>the</span> <span
  m='2222610'>answer</span> <span m='2222970'>was</span> <span
  m='2224810'>t</span> <span m='2225030'>of n</span> <span m='2225880'>is</span>
  <span m='2226850'>tilde</span> <span m='2227760'>2 to</span> <span
  m='2228000'>the</span> <span m='2228140'>n.</span> <span m='2228455'>It</span>
  <span m='2228770'>was</span> <span m='2228890'>actually</span> <span
  m='2229230'>2</span> <span m='2229510'>to the</span> <span
  m='2229620'>n</span> <span m='2229750'>minus</span> <span
  m='2230080'>1.</span> <span m='2231680'>Then</span> <span
  m='2231910'>we</span> <span m='2232000'>did</span> <span
  m='2232150'>merge</span> <span m='2232520'>sort,</span> <span
  m='2232870'>which</span> <span m='2233060'>is</span> <span
  m='2233220'>t</span> <span m='2233460'>of</span> <span m='2233570'>n</span>
  <span m='2234430'>equals</span> <span m='2235730'>2</span> <span
  m='2236180'>t</span> <span m='2236920'>of</span> <span m='2237290'>n</span>
  <span m='2237730'>over</span> <span m='2238040'>2.</span> <span
  m='2239760'>Difference</span> <span m='2240280'>there.</span> <span
  m='2241240'>Plus</span> <span m='2241890'>n</span> <span
  m='2242090'>minus</span> <span m='2242430'>1.</span> <span
  m='2243990'>And</span> <span m='2244210'>now</span> <span
  m='2244460'>the</span> <span m='2244640'>answer</span> <span
  m='2244980'>was</span> <span m='2245200'>t of</span> <span
  m='2245420'>n.</span> </p><p><span m='2246970'>What's</span> <span
  m='2247190'>the</span> <span m='2247290'>tilde</span> <span
  m='2247620'>for</span> <span m='2247740'>this</span> <span
  m='2247920'>one?</span> <span m='2249540'>For</span> <span
  m='2249680'>merge</span> <span m='2250020'>sort.</span> <span
  m='2252600'>n</span> <span m='2252840'>log</span> <span m='2253030'>n.</span>
  <span m='2253600'>Yeah,</span> <span m='2254160'>I</span> <span
  m='2254230'>can</span> <span m='2254380'>forget</span> <span
  m='2254700'>the</span> <span m='2254790'>rest</span> <span m='2255120'>if
  I</span> <span m='2255200'>know</span> <span m='2255320'>the</span> <span
  m='2255430'>tilde,</span> <span m='2255670'>n</span> <span
  m='2255820'>log</span> <span m='2255970'>n.</span> <span
  m='2260140'>Wow.</span> <span m='2262360'>These</span> <span
  m='2262600'>are</span> <span m='2262660'>pretty</span> <span
  m='2262910'>different</span> <span m='2263250'>answers,</span> <span
  m='2263690'>right?</span> <span m='2265290'>This</span> <span
  m='2265510'>one's</span> <span m='2265750'>nearly</span> <span
  m='2266090'>linear,</span> <span m='2267240'>that</span> <span
  m='2267480'>one's</span> <span m='2267750'>exponential.</span> <span
  m='2270810'>The</span> <span m='2270920'>recurrences</span> <span
  m='2271630'>looks</span> <span m='2271960'>pretty</span> <span
  m='2272230'>similar,</span> <span m='2274320'>in</span> <span
  m='2274420'>fact,</span> <span m='2274780'>this</span> <span
  m='2274860'>one</span> <span m='2275000'>sort</span> <span
  m='2275210'>of</span> <span m='2275270'>looks</span> <span
  m='2275460'>worse</span> <span m='2275970'>because</span> <span
  m='2277220'>I'm</span> <span m='2277450'>adding</span> <span
  m='2277910'>in</span> <span m='2278130'>n</span> <span
  m='2278300'>minus</span> <span m='2278610'>1</span> <span
  m='2278830'>every</span> <span m='2279050'>time</span> <span
  m='2279380'>instead</span> <span m='2279690'>of</span> <span
  m='2279780'>1.</span> <span m='2280960'>But</span> <span
  m='2281140'>the</span> <span m='2281260'>answer's</span> <span
  m='2281620'>a</span> <span m='2281690'>lot</span> <span
  m='2282210'>better,</span> <span m='2282720'>a</span> <span
  m='2283100'>lot</span> <span m='2283320'>smaller.</span> <span
  m='2285060'>What's</span> <span m='2285320'>the</span> <span
  m='2285410'>critical</span> <span m='2285970'>difference</span> <span
  m='2286420'>between</span> <span m='2286810'>these</span> <span
  m='2287010'>recurrences?</span> <span m='2289180'>Yeah?</span>
  </p><p></p><p><span m='2292440'>AUDIENCE: You're</span> <span
  m='2292890'>dropping</span> <span m='2293690'>the</span> <span
  m='2294290'>argument</span> <span m='2294630'>of</span> <span
  m='2294980'>t</span> <span m='2296250'>a</span> <span m='2296340'>lot</span>
  <span m='2296540'>faster.</span> <span m='2297370'>You're</span> <span
  m='2297540'>cutting</span> <span m='2297900'>it</span> <span
  m='2297980'>in</span> <span m='2298070'>half</span> <span
  m='2298320'>every</span> <span m='2298470'>time</span> <span
  m='2298700'>instead</span> <span m='2298810'>of</span> <span
  m='2298910'>subtracting</span> <span m='2299430'>one.</span> </p><p><span
  m='2299990'>TOM LEIGHTON: Right.</span> </p><p><span m='2301010'>AUDIENCE: So
  it's going to</span> <span m='2301330'>go</span> <span m='2301730'>away</span>
  <span m='2301790'>faster.</span> </p><p><span m='2302430'>TOM LEIGHTON:
  That's</span> <span m='2302750'>right.</span> <span m='2303170'>Here</span>
  <span m='2303320'>I've</span> <span m='2303490'>got</span> <span
  m='2303710'>two</span> <span m='2304070'>problems</span> <span
  m='2304540'>of</span> <span m='2304610'>size</span> <span
  m='2305060'>one</span> <span m='2305510'>less.</span> <span
  m='2306560'>Here</span> <span m='2306800'>I've</span> <span
  m='2306870'>got</span> <span m='2307100'>two</span> <span
  m='2307240'>problems</span> <span m='2307690'>of</span> <span
  m='2307800'>half</span> <span m='2308170'>a</span> <span
  m='2308270'>size.</span> <span m='2310230'>And</span> <span
  m='2310400'>that</span> <span m='2310550'>makes</span> <span
  m='2310780'>an</span> <span m='2310860'>enormous</span> <span
  m='2311750'>difference</span> <span m='2312790'>in</span> <span
  m='2312930'>the</span> <span m='2313080'>answer.</span> <span
  m='2313450'>Even</span> <span m='2313700'>though</span> <span
  m='2313810'>I'm</span> <span m='2313910'>doing</span> <span
  m='2314150'>more</span> <span m='2314500'>work</span> <span
  m='2315500'>after</span> <span m='2316450'>did</span> <span
  m='2316610'>the</span> <span m='2316680'>recursive</span> <span
  m='2317080'>problems,</span> <span m='2318140'>much</span> <span
  m='2318660'>faster</span> <span m='2319390'>running</span> <span
  m='2319700'>time</span> <span m='2320080'>or</span> <span
  m='2320320'>answer</span> <span m='2321300'>if</span> <span
  m='2321440'>these</span> <span m='2321620'>are</span> <span
  m='2321720'>algorithms</span> <span m='2322130'>that I'm</span> <span
  m='2323310'>analyzing.</span> <span m='2325540'>All</span> <span
  m='2325710'>right?</span> </p><p><span m='2327520'>In</span> <span
  m='2327590'>fact,</span> <span m='2327950'>let's</span> <span
  m='2328500'>take</span> <span m='2328750'>a</span> <span
  m='2328810'>look</span> <span m='2329950'>at</span> <span
  m='2330150'>what</span> <span m='2330330'>happens</span> <span
  m='2330780'>if</span> <span m='2330910'>I</span> <span
  m='2332650'>didn't</span> <span m='2332940'>use</span> <span
  m='2333160'>that</span> <span m='2333340'>n</span> <span
  m='2333460'>minus</span> <span m='2333780'>1,</span> <span
  m='2334010'>I</span> <span m='2334070'>just</span> <span
  m='2334280'>put</span> <span m='2334430'>a</span> <span m='2334480'>1</span>
  <span m='2334840'>there.</span> <span m='2335050'>Let's</span> <span
  m='2335210'>see</span> <span m='2335340'>what</span> <span
  m='2335540'>impact</span> <span m='2336100'>that</span> <span
  m='2336420'>n</span> <span m='2336610'>minus</span> <span m='2337060'>1</span>
  <span m='2337380'>had.</span> <span m='2339590'>So</span> <span
  m='2339780'>let's</span> <span m='2340000'>do</span> <span
  m='2340170'>the</span> <span m='2340250'>following</span> <span
  m='2343070'>recurrence.</span> <span m='2345080'>This</span> <span
  m='2345260'>one</span> <span m='2345380'>is</span> <span
  m='2345440'>going</span> <span m='2345560'>to</span> <span
  m='2345630'>be</span> <span m='2345970'>a</span> <span
  m='2346060'>little</span> <span m='2346370'>bit</span> <span
  m='2346590'>different</span> <span m='2349150'>because</span> <span
  m='2349330'>I'm</span> <span m='2349450'>not</span> <span
  m='2349640'>going</span> <span m='2349760'>to</span> <span
  m='2349840'>stick</span> <span m='2350070'>to</span> <span
  m='2350160'>powers</span> <span m='2350550'>of</span> <span
  m='2350650'>2.</span> <span m='2350900'>I'm</span> <span
  m='2350980'>going</span> <span m='2351100'>to</span> <span
  m='2351170'>get</span> <span m='2351300'>a</span> <span
  m='2351340'>little</span> <span m='2351620'>messier,</span> <span
  m='2352480'>because</span> <span m='2352630'>that</span> <span
  m='2352800'>often</span> <span m='2353130'>happens</span> <span
  m='2353520'>in</span> <span m='2353620'>reality.</span> <span
  m='2355130'>And</span> <span m='2355280'>I'm</span> <span
  m='2355340'>going</span> <span m='2355460'>to</span> <span
  m='2355520'>define</span> <span m='2356510'>s</span> <span
  m='2356880'>of</span> <span m='2357910'>1</span> <span m='2358760'>is</span>
  <span m='2359020'>0.</span> <span m='2360690'>s</span> <span
  m='2360900'>of</span> <span m='2361020'>n</span> <span m='2362970'>is</span>
  <span m='2364430'>s</span> <span m='2364790'>of</span> <span
  m='2365070'>the</span> <span m='2365220'>floor</span> <span
  m='2366030'>function</span> <span m='2366560'>of</span> <span
  m='2366680'>n</span> <span m='2366800'>over</span> <span m='2367000'>2</span>
  <span m='2369600'>plus</span> <span m='2370070'>s</span> <span
  m='2370460'>of</span> <span m='2370650'>the</span> <span
  m='2370720'>ceiling</span> <span m='2371260'>function</span> <span
  m='2371750'>of n</span> <span m='2371980'>over</span> <span
  m='2372150'>2</span> <span m='2374740'>plus</span> <span m='2375080'>1.</span>
  </p><p><span m='2380120'>Now,</span> <span m='2381570'>the</span> <span
  m='2381730'>ceiling</span> <span m='2382300'>function</span> <span
  m='2383290'>means</span> <span m='2383760'>the</span> <span
  m='2383940'>smallest</span> <span m='2384920'>integer</span> <span
  m='2385460'>that's</span> <span m='2385680'>at</span> <span
  m='2385830'>least</span> <span m='2386230'>that</span> <span
  m='2386570'>big.</span> <span m='2387000'>So</span> <span
  m='2387190'>you're</span> <span m='2387330'>sort</span> <span
  m='2387500'>of</span> <span m='2387670'>rounding</span> <span
  m='2388200'>up</span> <span m='2388400'>to</span> <span m='2388490'>the</span>
  <span m='2388570'>next</span> <span m='2388880'>integer.</span> <span
  m='2400260'>And</span> <span m='2400750'>the</span> <span
  m='2400810'>floor</span> <span m='2401270'>function</span> <span
  m='2401740'>means</span> <span m='2402010'>you're</span> <span
  m='2402140'>rounding</span> <span m='2402560'>down</span> <span
  m='2402850'>to</span> <span m='2402910'>the</span> <span
  m='2402990'>next</span> <span m='2403210'>integer.</span> <span
  m='2404430'>So</span> <span m='2404660'>it's</span> <span
  m='2404800'>the</span> <span m='2404880'>biggest</span> <span
  m='2405330'>integer</span> <span m='2410690'>less</span> <span
  m='2411010'>than</span> <span m='2411090'>equal</span> <span
  m='2411290'>to</span> <span m='2411360'>n</span> <span m='2411480'>over</span>
  <span m='2411650'>2.</span> <span m='2413190'>All</span> <span
  m='2413360'>right.</span> </p><p><span m='2414010'>Now,</span> <span
  m='2415070'>if</span> <span m='2415260'>we</span> <span m='2415360'>had</span>
  <span m='2415520'>just</span> <span m='2415740'>powers</span> <span
  m='2416140'>of</span> <span m='2416260'>2,</span> <span
  m='2417310'>this</span> <span m='2417480'>would</span> <span
  m='2417570'>be</span> <span m='2417660'>much</span> <span
  m='2417960'>easier</span> <span m='2418270'>to</span> <span
  m='2418370'>write.</span> <span m='2419380'>It</span> <span
  m='2419570'>would</span> <span m='2419670'>just</span> <span
  m='2419860'>be</span> <span m='2419980'>sn</span> <span
  m='2420390'>equals</span> <span m='2420740'>2</span> <span
  m='2421680'>sn</span> <span m='2422050'>over</span> <span m='2422600'>2</span>
  <span m='2423560'>plus</span> <span m='2423830'>1.</span> <span
  m='2425400'>So</span> <span m='2425550'>it's</span> <span
  m='2425680'>analogous</span> <span m='2426280'>to</span> <span
  m='2426370'>what</span> <span m='2426510'>we're</span> <span
  m='2426610'>doing</span> <span m='2426860'>up</span> <span
  m='2426980'>there</span> <span m='2427190'>where</span> <span
  m='2427290'>we're</span> <span m='2427380'>just</span> <span
  m='2427610'>adding</span> <span m='2427910'>1</span> <span
  m='2428870'>instead</span> <span m='2429130'>of</span> <span
  m='2429210'>n</span> <span m='2429330'>minus</span> <span
  m='2429640'>1.</span> <span m='2429840'>But</span> <span
  m='2429960'>I'm</span> <span m='2430080'>being</span> <span
  m='2430300'>careful.</span> <span m='2430740'>now.</span> <span
  m='2430870'>I'm</span> <span m='2430970'>going</span> <span
  m='2431090'>to</span> <span m='2431160'>make</span> <span
  m='2431360'>this</span> <span m='2431560'>recurrence</span> <span
  m='2432000'>work</span> <span m='2432300'>for</span> <span
  m='2432460'>all</span> <span m='2434470'>natural</span> <span
  m='2434820'>numbers.</span> <span m='2435760'>Because</span> <span
  m='2435920'>sometimes</span> <span m='2436440'>in</span> <span
  m='2436520'>reality,</span> <span m='2436960'>you're</span> <span
  m='2437060'>dealing</span> <span m='2437300'>with</span> <span
  m='2438090'>non</span> <span m='2438390'>powers</span> <span
  m='2438740'>of</span> <span m='2438820'>2.</span> </p><p><span
  m='2443440'>All</span> <span m='2443610'>right,</span> <span
  m='2443830'>let's</span> <span m='2445030'>see</span> <span
  m='2445210'>if</span> <span m='2445300'>we</span> <span m='2445370'>can</span>
  <span m='2445490'>solve</span> <span m='2445860'>this.</span> <span
  m='2447580'>What's</span> <span m='2447710'>the</span> <span
  m='2447800'>first</span> <span m='2448070'>thing</span> <span
  m='2448200'>to</span> <span m='2448270'>try</span> <span m='2448440'>to</span>
  <span m='2448540'>solve</span> <span m='2448840'>this?</span> <span
  m='2450170'>What</span> <span m='2450290'>do</span> <span
  m='2450350'>you</span> <span m='2450420'>do?</span> <span
  m='2456520'>What's</span> <span m='2456610'>the</span> <span
  m='2456700'>first</span> <span m='2456990'>step</span> <span
  m='2457220'>when</span> <span m='2457310'>you</span> <span
  m='2457370'>get</span> <span m='2457520'>a</span> <span
  m='2457570'>recurrence?</span> <span m='2459060'>You</span> <span
  m='2459160'>try</span> <span m='2459310'>to</span> <span
  m='2459726'>solve.</span> <span m='2463300'>What</span> <span
  m='2463500'>method</span> <span m='2463880'>should</span> <span
  m='2464040'>you</span> <span m='2464110'>try?</span> <span
  m='2466420'>Guess.</span> <span m='2467470'>And</span> <span
  m='2467640'>to</span> <span m='2467720'>guess,</span> <span
  m='2468900'>well,</span> <span m='2469090'>you</span> <span
  m='2469180'>got</span> <span m='2469310'>to</span> <span
  m='2469370'>plug</span> <span m='2469610'>some</span> <span
  m='2469750'>values</span> <span m='2470180'>in.</span> <span
  m='2470840'>It's</span> <span m='2471270'>sort</span> <span
  m='2471510'>of</span> <span m='2471590'>hard</span> <span
  m='2471830'>to</span> <span m='2471890'>guess.</span> <span
  m='2472720'>I</span> <span m='2472820'>mean,</span> <span
  m='2473230'>looking</span> <span m='2473400'>at</span> <span
  m='2473530'>that,</span> <span m='2473810'>I</span> <span
  m='2474310'>guess</span> <span m='2474890'>nothing</span> <span
  m='2475180'>comes</span> <span m='2475400'>to</span> <span
  m='2475470'>mind</span> <span m='2475800'>other</span> <span
  m='2475940'>than</span> <span m='2476130'>panic</span> <span
  m='2476560'>looking</span> <span m='2476810'>at</span> <span
  m='2476910'>that.</span> <span m='2478820'>But</span> <span
  m='2479000'>if</span> <span m='2479090'>we</span> <span m='2479170'>plug
  in</span> <span m='2479550'>some</span> <span m='2479710'>values,</span> <span
  m='2480180'>then</span> <span m='2480340'>maybe</span> <span
  m='2480560'>it</span> <span m='2480640'>won't</span> <span
  m='2480790'>be</span> <span m='2480880'>so</span> <span
  m='2481060'>bad.</span> </p><p><span m='2481470'>So</span> <span
  m='2481550'>we've</span> <span m='2481690'>got</span> <span
  m='2482640'>s1</span> <span m='2483800'>equals</span> <span
  m='2484140'>0.</span> <span m='2485200'>What's</span> <span
  m='2485550'>s2?</span> <span m='2494040'>It's</span> <span
  m='2494370'>not</span> <span m='2494620'>3,</span> <span
  m='2495260'>because</span> <span m='2495430'>this</span> <span
  m='2495670'>is</span> <span m='2495870'>2</span> <span m='2496080'>over</span>
  <span m='2496280'>2</span> <span m='2496890'>is 1,</span> <span
  m='2497000'>floor</span> <span m='2497740'>of</span> <span
  m='2497830'>1</span> <span m='2498040'>is</span> <span m='2498150'>1.</span>
  <span m='2499380'>s</span> <span m='2499620'>of</span> <span
  m='2499700'>1</span> <span m='2499880'>is</span> <span m='2499970'>0.</span>
  <span m='2502590'>Ceiling</span> <span m='2503080'>of</span> <span
  m='2503180'>1</span> <span m='2503410'>is</span> <span m='2503540'>1</span>
  <span m='2503850'>because</span> <span m='2504000'>it's</span> <span
  m='2504120'>an</span> <span m='2504210'>integer.</span> <span
  m='2505460'>s</span> <span m='2505700'>of</span> <span m='2505790'>1</span>
  <span m='2505970'>is</span> <span m='2506050'>0</span> <span
  m='2507440'>plus</span> <span m='2507660'>1.</span> <span
  m='2508630'>So</span> <span m='2508780'>s</span> <span m='2508810'>of 2</span>
  <span m='2509280'>is</span> <span m='2509400'>1.</span> <span
  m='2511400'>What's</span> <span m='2511620'>s</span> <span
  m='2511850'>of</span> <span m='2512130'>3?</span> <span
  m='2513530'>Yikes,</span> <span m='2514130'>all</span> <span
  m='2514280'>right.</span> <span m='2515510'>3</span> <span
  m='2515950'>over</span> <span m='2516200'>2</span> <span m='2516540'>is</span>
  <span m='2516670'>1</span> <span m='2516950'>and</span> <span
  m='2517230'>1/2.</span> <span m='2517510'>What's</span> <span
  m='2517720'>the</span> <span m='2517790'>floor</span> <span
  m='2518130'>of</span> <span m='2518560'>1</span> <span m='2518760'>and</span>
  <span m='2518960'>1/2?</span> <span m='2519890'>1.</span> <span
  m='2520460'>s</span> <span m='2520680'>of</span> <span m='2520760'>1</span>
  <span m='2520940'>is</span> <span m='2521040'>0.</span> <span
  m='2521360'>That's</span> <span m='2521580'>gone.</span> <span
  m='2522530'>What's</span> <span m='2522800'>the</span> <span
  m='2522890'>ceiling</span> <span m='2523470'>of</span> <span
  m='2523550'>1</span> <span m='2523750'>and</span> <span
  m='2523950'>1/2?</span> <span m='2525090'>2.</span> <span m='2525780'>s</span>
  <span m='2526040'>of</span> <span m='2526170'>2</span> <span
  m='2526510'>is</span> <span m='2526670'>1</span> <span m='2528260'>plus</span>
  <span m='2528580'>1.</span> <span m='2529470'>What's</span> <span
  m='2529680'>the</span> <span m='2529830'>answer</span> <span
  m='2530100'>for</span> <span m='2530240'>s of</span> <span
  m='2530420'>3?</span> <span m='2534070'>2,</span> <span
  m='2534770'>because</span> <span m='2534920'>I've</span> <span
  m='2535040'>got</span> <span m='2536230'>0,</span> <span m='2537200'>1,</span>
  <span m='2537750'>and</span> <span m='2537910'>1.</span> </p><p><span
  m='2540120'>s</span> <span m='2540360'>of</span> <span m='2540460'>4.</span>
  <span m='2541710'>This</span> <span m='2541940'>one's</span> <span
  m='2542180'>easy</span> <span m='2542500'>because</span> <span
  m='2542720'>it's</span> <span m='2543130'>even.</span> <span
  m='2545540'>I</span> <span m='2545720'>get</span> <span m='2546000'>s</span>
  <span m='2546270'>of</span> <span m='2546410'>2,</span> <span
  m='2547150'>which</span> <span m='2547340'>is</span> <span
  m='2547460'>1</span> <span m='2548220'>plus</span> <span m='2548490'>s</span>
  <span m='2548710'>of</span> <span m='2548820'>two</span> <span
  m='2549060'>which</span> <span m='2549230'>is</span> <span
  m='2549350'>1</span> <span m='2549960'>plus</span> <span m='2550260'>1.</span>
  <span m='2551500'>So</span> <span m='2551640'>what's</span> <span
  m='2551810'>s</span> <span m='2551980'>of</span> <span m='2552070'>4?</span>
  <span m='2553500'>3.</span> </p><p><span m='2556040'>You</span> <span
  m='2556140'>might</span> <span m='2556320'>try</span> <span
  m='2556560'>a</span> <span m='2556630'>guess.</span> <span
  m='2558880'>What</span> <span m='2559010'>would</span> <span
  m='2559130'>you</span> <span m='2559210'>guess?</span> <span
  m='2562010'>Yeah,</span> <span m='2562290'>n</span> <span
  m='2562460'>minus</span> <span m='2562800'>1.</span> <span
  m='2563860'>So</span> <span m='2563990'>we're</span> <span
  m='2564050'>going</span> <span m='2564170'>to</span> <span
  m='2564240'>guess</span> <span m='2568750'>s</span> <span
  m='2569060'>of</span> <span m='2569110'>n</span> <span
  m='2570030'>equals</span> <span m='2570300'>n</span> <span
  m='2570470'>minus</span> <span m='2570830'>1.</span> <span
  m='2571540'>And</span> <span m='2571640'>that's</span> <span
  m='2571840'>not</span> <span m='2571990'>so</span> <span
  m='2572130'>bad,</span> <span m='2572360'>actually.</span> <span
  m='2572630'>It's</span> <span m='2572740'>pretty</span> <span
  m='2572950'>simple.</span> <span m='2573340'>Looking</span> <span
  m='2573600'>at</span> <span m='2573680'>that</span> <span
  m='2573860'>mess,</span> <span m='2574210'>you'd</span> <span
  m='2574330'>never</span> <span m='2575750'>think</span> <span
  m='2576010'>of</span> <span m='2576090'>that</span> <span
  m='2576470'>right</span> <span m='2576660'>away.</span> <span
  m='2576900'>But</span> <span m='2577040'>once</span> <span
  m='2577220'>you</span> <span m='2577300'>plug in</span> <span
  m='2577650'>some</span> <span m='2577780'>values</span> <span
  m='2578130'>it's</span> <span m='2578260'>not</span> <span
  m='2578420'>so</span> <span m='2578550'>bad.</span> </p><p><span
  m='2580250'>All</span> <span m='2580460'>right,</span> <span
  m='2580630'>let's</span> <span m='2580850'>verify</span> <span
  m='2581560'>it.</span> <span m='2585270'>And</span> <span
  m='2585400'>we're</span> <span m='2585460'>going</span> <span
  m='2585580'>to</span> <span m='2585640'>verify</span> <span
  m='2586250'>by</span> <span m='2586420'>strong</span> <span
  m='2586820'>induction.</span> <span m='2594790'>The</span> <span
  m='2594920'>induction</span> <span m='2595330'>hypothesis</span> <span
  m='2596130'>is</span> <span m='2596300'>our</span> <span
  m='2596420'>guess.</span> <span m='2606704'>The</span> <span
  m='2607190'>base</span> <span m='2607540'>case</span> <span
  m='2607980'>is</span> <span m='2608130'>easy.</span> <span
  m='2611870'>Because</span> <span m='2612040'>I've</span> <span
  m='2612160'>got</span> <span m='2612460'>s</span> <span m='2612650'>of</span>
  <span m='2612760'>1</span> <span m='2614260'>is</span> <span
  m='2615210'>0.</span> <span m='2616820'>And</span> <span
  m='2616960'>that</span> <span m='2617110'>equals</span> <span
  m='2617550'>1</span> <span m='2617850'>minus</span> <span
  m='2618220'>1.</span> <span m='2620160'>So</span> <span
  m='2620320'>that's</span> <span m='2620590'>good.</span> <span
  m='2621970'>So</span> <span m='2622310'>let's</span> <span
  m='2622540'>do</span> <span m='2622690'>the</span> <span
  m='2622810'>induction</span> <span m='2623660'>step.</span> </p><p><span
  m='2640530'>All</span> <span m='2640830'>right,</span> <span
  m='2641050'>so</span> <span m='2641310'>the</span> <span
  m='2641410'>induction</span> <span m='2641850'>step.</span> <span
  m='2647690'>We're</span> <span m='2647810'>going</span> <span
  m='2648040'>to</span> <span m='2648130'>assume</span> <span
  m='2651680'>that</span> <span m='2652370'>p1</span> <span
  m='2652920'>is</span> <span m='2653060'>true,</span> <span
  m='2653790'>p2</span> <span m='2654310'>is</span> <span
  m='2654480'>true,</span> <span m='2655850'>all</span> <span
  m='2656160'>the</span> <span m='2656240'>way</span> <span
  m='2656460'>up</span> <span m='2656660'>to</span> <span m='2657910'>pn,</span>
  <span m='2659940'>to</span> <span m='2660110'>prove</span> <span
  m='2661280'>pn</span> <span m='2661670'>plus</span> <span m='2661930'>1</span>
  <span m='2663530'>is</span> <span m='2663690'>true.</span> <span
  m='2666820'>For</span> <span m='2667010'>n</span> <span
  m='2667190'>better</span> <span m='2667273'>than</span> <span
  m='2667356'>or</span> <span m='2667540'>equal</span> <span
  m='2667650'>to</span> <span m='2667730'>1.</span> <span m='2668690'>And</span>
  <span m='2668840'>then</span> <span m='2668970'>we</span> <span
  m='2669070'>look</span> <span m='2669400'>at</span> <span
  m='2669870'>the</span> <span m='2669990'>n</span> <span
  m='2670140'>plus</span> <span m='2670390'>first</span> <span
  m='2670900'>term.</span> <span m='2672880'>That</span> <span
  m='2673110'>equals</span> <span m='2673530'>s</span> <span
  m='2674253'>of</span> <span m='2675060'>floor</span> <span
  m='2675860'>n</span> <span m='2676040'>plus</span> <span m='2676270'>1</span>
  <span m='2676450'>over</span> <span m='2676610'>2</span> <span
  m='2679490'>plus</span> <span m='2679880'>s</span> <span m='2680240'>of</span>
  <span m='2680550'>ceiling</span> <span m='2681760'>n</span> <span
  m='2681990'>plus</span> <span m='2682260'>1</span> <span
  m='2682440'>over</span> <span m='2682600'>2</span> <span
  m='2684740'>plus</span> <span m='2685090'>1.</span> </p><p><span
  m='2687710'>All</span> <span m='2687960'>right,</span> <span
  m='2688230'>now</span> <span m='2690490'>I</span> <span
  m='2690640'>don't</span> <span m='2690820'>know</span> <span
  m='2690920'>what</span> <span m='2691040'>these</span> <span
  m='2691230'>are</span> <span m='2691390'>exactly</span> <span
  m='2692030'>depending</span> <span m='2692400'>on</span> <span
  m='2692470'>whether</span> <span m='2692730'>n</span> <span
  m='2692920'>is</span> <span m='2693060'>even</span> <span m='2693280'>a</span>
  <span m='2693350'>rod.</span> <span m='2695820'>First let me</span> <span
  m='2696220'>plug in</span> <span m='2697300'>using</span> <span
  m='2698070'>the</span> <span m='2698160'>induction</span> <span
  m='2698510'>hypothesis.</span> <span m='2700070'>I</span> <span
  m='2700250'>know</span> <span m='2700570'>that</span> <span
  m='2700730'>this</span> <span m='2700990'>is</span> <span m='2702220'>n</span>
  <span m='2702450'>plus</span> <span m='2702770'>1</span> <span
  m='2702970'>over</span> <span m='2703200'>2</span> <span
  m='2704450'>minus</span> <span m='2704860'>1.</span> <span
  m='2706040'>This</span> <span m='2706320'>is</span> <span
  m='2706530'>ceiling</span> <span m='2708480'>n</span> <span
  m='2708710'>plus</span> <span m='2708980'>1</span> <span
  m='2709160'>over</span> <span m='2709370'>2</span> <span
  m='2710470'>minus</span> <span m='2710860'>1.</span> <span
  m='2711850'>And</span> <span m='2711960'>then</span> <span
  m='2712070'>I</span> <span m='2712140'>carry</span> <span
  m='2712430'>the</span> <span m='2712500'>plus 1</span> <span
  m='2712980'>down.</span> <span m='2713400'>That's</span> <span
  m='2713700'>by</span> <span m='2714535'>the</span> <span
  m='2714870'>induction</span> <span m='2715300'>hypothesis.</span> </p><p><span
  m='2720760'>All</span> <span m='2721040'>right,</span> <span
  m='2721330'>now</span> <span m='2722410'>I</span> <span
  m='2722540'>don't</span> <span m='2722790'>know</span> <span
  m='2722900'>exactly</span> <span m='2723450'>what</span> <span
  m='2723600'>either</span> <span m='2723860'>of</span> <span
  m='2723930'>these</span> <span m='2724120'>values</span> <span
  m='2724520'>is</span> <span m='2724770'>unless</span> <span
  m='2725210'>I</span> <span m='2725290'>know</span> <span
  m='2725470'>the</span> <span m='2725550'>parity</span> <span
  m='2726040'>of</span> <span m='2726150'>n.</span> <span m='2726640'>But</span>
  <span m='2726900'>I</span> <span m='2727000'>do</span> <span
  m='2727250'>know</span> <span m='2727450'>the</span> <span
  m='2727550'>sum</span> <span m='2728540'>of</span> <span
  m='2728720'>these</span> <span m='2728940'>two</span> <span
  m='2729080'>things.</span> <span m='2730680'>The</span> <span
  m='2730730'>floor</span> <span m='2731160'>of</span> <span
  m='2731270'>something</span> <span m='2731660'>plus</span> <span
  m='2731900'>the</span> <span m='2731980'>ceiling</span> <span
  m='2732410'>of</span> <span m='2732480'>that</span> <span
  m='2732690'>something</span> <span m='2734150'>is</span> <span
  m='2735230'>twice</span> <span m='2735800'>the</span> <span
  m='2735910'>something.</span> <span m='2737600'>All</span> <span
  m='2737770'>right,</span> <span m='2738010'>so</span> <span
  m='2738130'>this</span> <span m='2739100'>plus</span> <span
  m='2739390'>that</span> <span m='2739830'>equals</span> <span
  m='2740270'>n</span> <span m='2740410'>plus</span> <span m='2740680'>1.</span>
  <span m='2742940'>Minus</span> <span m='2743410'>1</span> <span
  m='2743630'>minus</span> <span m='2744050'>1</span> <span
  m='2744220'>plus</span> <span m='2744540'>1</span> <span m='2744730'>is</span>
  <span m='2744850'>minus</span> <span m='2745230'>1.</span> <span
  m='2746740'>And</span> <span m='2746930'>so</span> <span m='2747100'>in</span>
  <span m='2747180'>fact,</span> <span m='2747560'>we</span> <span
  m='2747670'>prove</span> <span m='2748240'>that</span> <span
  m='2748460'>s</span> <span m='2748730'>of</span> <span m='2748860'>n</span>
  <span m='2749000'>plus</span> <span m='2749290'>1</span> <span
  m='2749670'>equals</span> <span m='2750290'>n</span> <span
  m='2750500'>plus</span> <span m='2750760'>1</span> <span
  m='2751990'>minus</span> <span m='2752380'>1.</span> <span
  m='2754040'>So</span> <span m='2754170'>we</span> <span
  m='2754270'>verified</span> <span m='2755350'>the</span> <span
  m='2755510'>induction</span> <span m='2755880'>hypothesis.</span> <span
  m='2758680'>Yeah?</span> </p><p><span m='2760080'>AUDIENCE:
  [INAUDIBLE].</span> <span m='2768040'>Taking</span> <span m='2768180'>the
  n</span> <span m='2768665'>[INAUDIBLE].</span> </p><p><span m='2772675'>TOM
  LEIGHTON: Let's</span> <span m='2772737'>see,</span> <span
  m='2772800'>I'm</span> <span m='2772920'>not</span> <span
  m='2773110'>sure.</span> <span m='2773460'>So</span> <span
  m='2773960'>are</span> <span m='2774050'>you</span> <span
  m='2774190'>asking</span> <span m='2776150'>why</span> <span
  m='2776680'>I</span> <span m='2776760'>started</span> <span
  m='2777050'>sn</span> <span m='2777370'>plus</span> <span m='2777670'>1</span>
  <span m='2777830'>here?</span> </p><p><span m='2778742'>AUDIENCE:
  [INAUDIBLE].</span> </p><p><span m='2787730'>TOM LEIGHTON: Doesn't</span>
  <span m='2788040'>matter.</span> <span m='2788540'>But</span> <span
  m='2789950'>the</span> <span m='2790450'>expression</span> <span
  m='2791210'>is</span> <span m='2792020'>s</span> <span m='2792405'>of</span>
  <span m='2792790'>whatever</span> <span m='2793140'>this</span> <span
  m='2793400'>is,</span> <span m='2794310'>the</span> <span
  m='2794400'>induction</span> <span m='2794720'>hypothesis</span> <span
  m='2795420'>would</span> <span m='2795550'>be,</span> <span
  m='2796380'>s</span> <span m='2796660'>of</span> <span
  m='2796740'>whatever's</span> <span m='2797130'>inside</span> <span
  m='2797590'>there</span> <span m='2797790'>is</span> <span
  m='2798010'>what's</span> <span m='2798200'>inside</span> <span
  m='2798570'>there</span> <span m='2798700'>minus</span> <span
  m='2799050'>1.</span> <span m='2800240'>And</span> <span m='2800440'>so</span>
  <span m='2800880'>the</span> <span m='2800980'>induction</span> <span
  m='2801290'>hypothesis</span> <span m='2801880'>says</span> <span
  m='2802310'>s</span> <span m='2802570'>of</span> <span m='2802740'>this</span>
  <span m='2803170'>is</span> <span m='2803490'>that</span> <span
  m='2804380'>minus</span> <span m='2804740'>1.</span> <span
  m='2808480'>Any</span> <span m='2808680'>other</span> <span
  m='2808820'>questions?</span> </p><p><span m='2815260'>So</span> <span
  m='2815430'>let's</span> <span m='2815630'>write</span> <span
  m='2815830'>that</span> <span m='2815980'>on</span> <span
  m='2816070'>our</span> <span m='2816170'>table</span> <span
  m='2816540'>up</span> <span m='2816660'>here.</span> <span
  m='2821950'>So</span> <span m='2822250'>this</span> <span
  m='2822460'>is</span> <span m='2822650'>sn</span> <span
  m='2823460'>equals</span> <span m='2824020'>s</span> <span
  m='2824855'>of</span> <span m='2825240'>floor</span> <span
  m='2825595'>n</span> <span m='2825950'>over</span> <span m='2826150'>2</span>
  <span m='2827980'>plus</span> <span m='2828450'>s</span> <span
  m='2829160'>of</span> <span m='2829710'>ceiling</span> <span
  m='2830250'>n</span> <span m='2830390'>over</span> <span m='2830570'>2</span>
  <span m='2832640'>plus</span> <span m='2833060'>1.</span> <span
  m='2833926'>And</span> <span m='2834360'>the</span> <span
  m='2834490'>answer</span> <span m='2834890'>is,</span> <span
  m='2837080'>sn</span> <span m='2838140'>is</span> <span
  m='2838280'>tilde.</span> <span m='2839020'>What's</span> <span
  m='2839220'>the</span> <span m='2839280'>tilde</span> <span
  m='2839610'>of?</span> <span m='2843140'>n.</span> <span
  m='2843680'>The</span> <span m='2843800'>answer</span> <span
  m='2844000'>is</span> <span m='2844090'>n</span> <span
  m='2844220'>minus</span> <span m='2844490'>1.</span> <span
  m='2844640'>So</span> <span m='2844710'>it's</span> <span
  m='2844830'>tilde</span> <span m='2845090'>of</span> <span
  m='2845240'>n.</span> <span m='2847850'>Now,</span> <span
  m='2848290'>this</span> <span m='2848660'>is</span> <span
  m='2849130'>the</span> <span m='2849210'>same</span> <span
  m='2849610'>expression</span> <span m='2850110'>is</span> <span
  m='2850270'>this</span> <span m='2850650'>if</span> <span
  m='2850790'>n's</span> <span m='2851040'>a</span> <span
  m='2851100'>power</span> <span m='2851450'>of</span> <span
  m='2851560'>2.</span> <span m='2852310'>I'd</span> <span
  m='2852440'>have</span> <span m='2853160'>2</span> <span m='2853480'>sn</span>
  <span m='2853800'>over</span> <span m='2853940'>2</span> <span
  m='2854490'>plus</span> <span m='2855010'>1</span> <span
  m='2855730'>instead</span> <span m='2856050'>of</span> <span
  m='2856130'>n</span> <span m='2856260'>minus</span> <span
  m='2856620'>1.</span> <span m='2857440'>And</span> <span m='2858130'>by</span>
  <span m='2858270'>going</span> <span m='2858510'>from</span> <span
  m='2858620'>n</span> <span m='2858850'>minus</span> <span m='2859180'>1</span>
  <span m='2859440'>to</span> <span m='2859540'>1,</span> <span
  m='2861120'>I</span> <span m='2861240'>got</span> <span m='2861450'>rid</span>
  <span m='2861590'>of</span> <span m='2861670'>the</span> <span
  m='2861740'>log</span> <span m='2862080'>term.</span> <span
  m='2864450'>But</span> <span m='2864640'>it's</span> <span
  m='2864780'>still</span> <span m='2866340'>not</span> <span
  m='2866840'>exponential.</span> <span m='2868040'>And</span> <span
  m='2868180'>that's</span> <span m='2868370'>because</span> <span
  m='2868840'>I'm</span> <span m='2869000'>cutting</span> <span
  m='2869390'>down</span> <span m='2869680'>the</span> <span
  m='2869800'>insides</span> <span m='2870370'>here</span> <span
  m='2871640'>by</span> <span m='2872180'>a</span> <span
  m='2872230'>factor</span> <span m='2872640'>of</span> <span
  m='2872720'>2</span> <span m='2872950'>roughly.</span> </p><p><span
  m='2879260'>All</span> <span m='2879420'>right,</span> <span
  m='2879660'>so</span> <span m='2881610'>all</span> <span
  m='2881840'>the</span> <span m='2881980'>recurrences</span> <span
  m='2882480'>we've</span> <span m='2882620'>seen</span> <span
  m='2882840'>so</span> <span m='2883060'>far</span> <span
  m='2883300'>have</span> <span m='2883400'>been</span> <span
  m='2883460'>pretty</span> <span m='2883760'>simple.</span> <span
  m='2885540'>If</span> <span m='2885740'>guess</span> <span
  m='2886000'>and</span> <span m='2886090'>verify</span> <span
  m='2886570'>doesn't</span> <span m='2886870'>work</span> <span
  m='2887190'>after</span> <span m='2887380'>seeing</span> <span
  m='2887620'>a</span> <span m='2887680'>few</span> <span
  m='2887880'>terms,</span> <span m='2888330'>you</span> <span
  m='2888420'>can</span> <span m='2888570'>use</span> <span
  m='2888750'>plug</span> <span m='2889030'>and</span> <span
  m='2889160'>chug</span> <span m='2889960'>and</span> <span
  m='2890130'>you</span> <span m='2890210'>can</span> <span
  m='2890360'>figure</span> <span m='2890640'>it</span> <span
  m='2890720'>out.</span> <span m='2891750'>The</span> <span
  m='2891820'>good</span> <span m='2892000'>news</span> <span
  m='2892220'>is,</span> <span m='2892490'>that</span> <span
  m='2892680'>happens</span> <span m='2893370'>a</span> <span
  m='2893500'>lot</span> <span m='2893950'>in</span> <span
  m='2894050'>practice.</span> <span m='2895640'>The</span> <span
  m='2895800'>bad</span> <span m='2896070'>news</span> <span
  m='2896300'>is,</span> <span m='2896610'>sometimes</span> <span
  m='2897410'>it</span> <span m='2897510'>doesn't</span> <span
  m='2898070'>and</span> <span m='2898200'>you</span> <span
  m='2898300'>can</span> <span m='2898440'>get</span> <span
  m='2898610'>nasty</span> <span m='2899020'>recurrences.</span> </p><p><span
  m='2899630'>So</span> <span m='2899750'>let</span> <span m='2899870'>me</span>
  <span m='2899960'>show</span> <span m='2900230'>you</span> <span
  m='2900440'>a</span> <span m='2901870'>nasty</span> <span
  m='2902350'>one</span> <span m='2904190'>that</span> <span
  m='2904360'>actually</span> <span m='2904810'>was</span> <span
  m='2905140'>once</span> <span m='2907250'>asked</span> <span
  m='2907705'>in</span> <span m='2908160'>6046,</span> <span
  m='2908870'>I</span> <span m='2908930'>think,</span> <span
  m='2909980'>on</span> <span m='2910250'>a</span> <span m='2911750'>quiz</span>
  <span m='2915870'>with</span> <span m='2916230'>disastrous</span> <span
  m='2916930'>results.</span> <span m='2926340'>All</span> <span
  m='2926530'>right,</span> <span m='2926760'>so</span> <span
  m='2928920'>this</span> <span m='2929170'>one</span> <span
  m='2929300'>is</span> <span m='2929470'>t</span> <span m='2929740'>of</span>
  <span m='2929860'>x</span> <span m='2931380'>equals</span> <span
  m='2934050'>2</span> <span m='2934580'>t</span> <span m='2935040'>of</span>
  <span m='2935500'>x</span> <span m='2935890'>over</span> <span
  m='2936180'>2</span> <span m='2937960'>plus</span> <span
  m='2939150'>8/9</span> <span m='2941351'>t</span> <span m='2941850'>of</span>
  <span m='2942570'>3x</span> <span m='2943320'>over</span> <span
  m='2943590'>4</span> <span m='2945150'>plus</span> <span m='2946160'>x</span>
  <span m='2946450'>squared</span> <span m='2948260'>for</span> <span
  m='2948710'>x</span> <span m='2949540'>bigger</span> <span
  m='2949850'>and</span> <span m='2949950'>equal</span> <span
  m='2950140'>to</span> <span m='2950230'>1,</span> <span m='2950870'>and</span>
  <span m='2951020'>otherwise</span> <span m='2951590'>it's</span> <span
  m='2951720'>0</span> <span m='2953260'>when</span> <span m='2953420'>x</span>
  <span m='2953660'>is</span> <span m='2953790'>less</span> <span
  m='2954020'>than</span> <span m='2954140'>1.</span> </p><p><span
  m='2958230'>Now,</span> <span m='2958640'>this</span> <span
  m='2958880'>is</span> <span m='2959060'>nasty</span> <span
  m='2959640'>for</span> <span m='2959830'>a</span> <span m='2959890'>lot</span>
  <span m='2960120'>of</span> <span m='2960210'>reasons.</span> <span
  m='2961890'>First,</span> <span m='2962980'>it's</span> <span
  m='2963190'>not</span> <span m='2963460'>just</span> <span
  m='2963730'>a</span> <span m='2963770'>find</span> <span m='2964100'>on</span>
  <span m='2964200'>the</span> <span m='2964330'>integers.</span> <span
  m='2965610'>We</span> <span m='2965750'>can</span> <span
  m='2965910'>make</span> <span m='2966130'>an</span> <span
  m='2966240'>integer</span> <span m='2966670'>version</span> <span
  m='2967080'>by</span> <span m='2967210'>putting</span> <span
  m='2967510'>floors</span> <span m='2968100'>or</span> <span
  m='2968190'>ceilings</span> <span m='2968690'>here.</span> <span
  m='2969500'>But</span> <span m='2969740'>the</span> <span
  m='2969810'>way</span> <span m='2970010'>you</span> <span
  m='2970100'>set</span> <span m='2970310'>it</span> <span m='2970380'>up</span>
  <span m='2970500'>now,</span> <span m='2970840'>it's</span> <span
  m='2971020'>defined</span> <span m='2971420'>on</span> <span
  m='2972020'>real</span> <span m='2972230'>numbers.</span> <span
  m='2976650'>You</span> <span m='2976860'>can,</span> <span
  m='2978290'>in</span> <span m='2978480'>theory,</span> <span
  m='2979000'>solve</span> <span m='2979410'>it</span> <span
  m='2979490'>with</span> <span m='2979620'>plug</span> <span
  m='2979870'>and</span> <span m='2979980'>chug.</span> </p><p><span
  m='2981150'>The</span> <span m='2981270'>nasty</span> <span
  m='2981710'>part</span> <span m='2981970'>is,</span> <span
  m='2983210'>you've</span> <span m='2983350'>got</span> <span
  m='2983480'>a</span> <span m='2983510'>bunch</span> <span
  m='2983760'>of</span> <span m='2983830'>things</span> <span
  m='2984070'>going</span> <span m='2984300'>down</span> <span
  m='2984520'>by</span> <span m='2984630'>powers</span> <span
  m='2985030'>of</span> <span m='2985140'>2</span> <span m='2985610'>and</span>
  <span m='2985910'>a</span> <span m='2985950'>bunch</span> <span
  m='2986200'>of</span> <span m='2986280'>things</span> <span
  m='2986550'>going</span> <span m='2986830'>down</span> <span
  m='2987140'>by</span> <span m='2987310'>3/4</span> <span
  m='2988020'>here.</span> <span m='2989410'>And</span> <span
  m='2989460'>so</span> <span m='2989560'>you</span> <span
  m='2989660'>have</span> <span m='2989810'>to</span> <span
  m='2989890'>keep</span> <span m='2990130'>track</span> <span
  m='2990510'>of</span> <span m='2990640'>all</span> <span
  m='2990850'>the</span> <span m='2990940'>terms</span> <span m='2991400'>that
  are</span> <span m='2991480'>decreasing,</span> <span m='2991970'>and</span>
  <span m='2992060'>that's</span> <span m='2992310'>a</span> <span
  m='2992650'>nightmare</span> <span m='2993390'>plug</span> <span
  m='2993640'>and</span> <span m='2993760'>chug.</span> <span
  m='2994280'>Because</span> <span m='2994450'>it's</span> <span
  m='2994540'>not</span> <span m='2994730'>just</span> <span
  m='2994970'>one</span> <span m='2995230'>thing</span> <span
  m='2995530'>that's</span> <span m='2995690'>unfolding,</span> <span
  m='2996220'>it's</span> <span m='2996390'>two</span> <span
  m='2996570'>things</span> <span m='2996890'>that</span> <span
  m='2996990'>are</span> <span m='2997050'>unfolding.</span> <span
  m='2998890'>So</span> <span m='2999100'>very</span> <span
  m='2999390'>painful.</span> </p><p><span m='3001280'>Now,</span> <span
  m='3002800'>it</span> <span m='3002970'>used</span> <span
  m='3003210'>to</span> <span m='3003290'>be</span> <span
  m='3004320'>that</span> <span m='3004510'>was</span> <span
  m='3004630'>the</span> <span m='3004700'>state</span> <span
  m='3004940'>of</span> <span m='3005030'>life.</span> <span
  m='3005390'>20</span> <span m='3005750'>years</span> <span
  m='3005990'>ago,</span> <span m='3006875'>I</span> <span
  m='3007230'>think</span> <span m='3007350'>we</span> <span
  m='3007460'>started</span> <span m='3007720'>teaching</span> <span
  m='3008020'>this</span> <span m='3008160'>course</span> <span
  m='3008580'>sometime</span> <span m='3009080'>around</span> <span
  m='3009380'>then,</span> <span m='3010400'>there</span> <span
  m='3010530'>just</span> <span m='3010760'>was</span> <span
  m='3010910'>nothing</span> <span m='3011550'>else</span> <span
  m='3011700'>to</span> <span m='3011800'>say</span> <span
  m='3012490'>other</span> <span m='3012730'>than</span> <span
  m='3013160'>life's</span> <span m='3013370'>tough</span> <span
  m='3014180'>and</span> <span m='3014360'>sometimes</span> <span
  m='3014780'>you've</span> <span m='3014870'>got</span> <span
  m='3014980'>to</span> <span m='3015040'>do</span> <span
  m='3015190'>these</span> <span m='3015400'>things</span> <span
  m='3015680'>and</span> <span m='3015770'>it's</span> <span
  m='3016270'>a</span> <span m='3016330'>pain.</span> <span
  m='3018030'>Just</span> <span m='3018380'>had</span> <span
  m='3018580'>to</span> <span m='3018640'>make</span> <span
  m='3018820'>the</span> <span m='3018880'>best</span> <span
  m='3019160'>of</span> <span m='3019240'>it.</span> </p><p><span
  m='3020140'>And</span> <span m='3020300'>then</span> <span
  m='3020890'>in</span> <span m='3021030'>the</span> <span
  m='3021090'>mid-90s,</span> <span m='3021950'>one</span> <span
  m='3022180'>day</span> <span m='3023500'>two</span> <span
  m='3023880'>students</span> <span m='3024730'>at</span> <span
  m='3025070'>the</span> <span m='3025200'>American</span> <span
  m='3025620'>University</span> <span m='3026110'>in</span> <span
  m='3026220'>Beirut</span> <span m='3027010'>came</span> <span
  m='3027270'>by</span> <span m='3027390'>my</span> <span
  m='3027530'>office.</span> <span m='3028900'>They</span> <span
  m='3029030'>were</span> <span m='3029140'>named</span> <span
  m='3029790'>Akra</span> <span m='3030490'>and</span> <span
  m='3030700'>Bazzi.</span> <span m='3032590'>And</span> <span
  m='3032780'>they'd</span> <span m='3032910'>actually</span> <span
  m='3033220'>come</span> <span m='3033530'>to</span> <span
  m='3033600'>Boston</span> <span m='3034130'>to</span> <span
  m='3034250'>escape</span> <span m='3034620'>the</span> <span
  m='3034700'>daily</span> <span m='3035030'>bombings.</span> <span
  m='3035530'>This</span> <span m='3035690'>was</span> <span
  m='3035950'>when</span> <span m='3036100'>all</span> <span m='3036300'>heck
  was</span> <span m='3036860'>breaking</span> <span m='3037160'>loose</span>
  <span m='3037350'>in</span> <span m='3037460'>Beirut.</span> <span
  m='3037900'>It</span> <span m='3037970'>was</span> <span m='3038070'>a</span>
  <span m='3038120'>mess.</span> <span m='3039470'>And</span> <span
  m='3039630'>they</span> <span m='3039710'>come</span> <span
  m='3039910'>into</span> <span m='3040040'>my</span> <span
  m='3040150'>office</span> <span m='3040500'>and</span> <span
  m='3040590'>they</span> <span m='3040680'>claim</span> <span
  m='3041160'>to</span> <span m='3041250'>have</span> <span m='3041390'>a</span>
  <span m='3041430'>simple</span> <span m='3042160'>formula</span> <span
  m='3043450'>for</span> <span m='3043610'>solving</span> <span
  m='3044110'>any</span> <span m='3044460'>recurrence</span> <span
  m='3045190'>like</span> <span m='3045480'>this.</span> <span m='3046460'>In
  fact,</span> <span m='3046680'>you</span> <span m='3046760'>can</span> <span
  m='3046890'>even</span> <span m='3047090'>add</span> <span
  m='3047500'>a</span> <span m='3048886'>5</span> <span m='3049350'>t</span>
  <span m='3049630'>of</span> <span m='3049880'>x</span> <span
  m='3050100'>over</span> <span m='3050290'>7.</span> <span
  m='3051590'>They</span> <span m='3051760'>said</span> <span
  m='3051970'>no</span> <span m='3052170'>problem.</span> <span
  m='3052580'>Their</span> <span m='3052700'>simple</span> <span
  m='3053000'>formula</span> <span m='3053440'>just</span> <span
  m='3053800'>will</span> <span m='3053970'>always</span> <span
  m='3054350'>work.</span> </p><p><span m='3056490'>And</span> <span
  m='3056750'>the</span> <span m='3056810'>general</span> <span
  m='3057310'>form</span> <span m='3058500'>that</span> <span
  m='3058650'>they</span> <span m='3058780'>claim</span> <span
  m='3059150'>to</span> <span m='3059210'>solve</span> <span
  m='3060100'>was</span> <span m='3060280'>the</span> <span
  m='3060350'>following.</span> <span m='3062020'>It's</span> <span
  m='3062610'>the</span> <span m='3062720'>general</span> <span
  m='3063240'>class</span> <span m='3063800'>of</span> <span
  m='3063930'>divide</span> <span m='3064530'>and</span> <span
  m='3064710'>conquer</span> <span m='3065130'>recurrences.</span> <span
  m='3066490'>So</span> <span m='3066710'>any</span> <span
  m='3066960'>recurrence</span> <span m='3067470'>you</span> <span
  m='3067570'>get</span> <span m='3067740'>from</span> <span
  m='3067890'>an</span> <span m='3067980'>algorithm</span> <span
  m='3068460'>where</span> <span m='3068560'>you</span> <span
  m='3068700'>break</span> <span m='3069100'>it</span> <span
  m='3069180'>into</span> <span m='3069380'>smaller</span> <span
  m='3070050'>pieces</span> <span m='3070560'>by</span> <span
  m='3070720'>a</span> <span m='3070780'>constant</span> <span
  m='3071210'>factor,</span> <span m='3072130'>they</span> <span
  m='3072350'>claim</span> <span m='3072700'>to</span> <span
  m='3072780'>solve.</span> <span m='3074390'>So</span> <span
  m='3074560'>let</span> <span m='3074690'>me</span> <span
  m='3074780'>define</span> <span m='3076070'>this</span> <span
  m='3076310'>class.</span> <span m='3076810'>It's</span> <span
  m='3076930'>a</span> <span m='3076980'>little</span> <span
  m='3077820'>painful.</span> </p><p><span m='3088330'>So</span> <span
  m='3088460'>a</span> <span m='3088550'>divide</span> <span
  m='3088930'>and</span> <span m='3089050'>conquer</span> <span
  m='3089460'>recurrence</span> <span m='3093390'>has</span> <span
  m='3093680'>the</span> <span m='3093770'>form.</span> <span
  m='3098450'>There's</span> <span m='3098640'>a</span> <span
  m='3098690'>simple</span> <span m='3099190'>version</span> <span
  m='3099590'>and</span> <span m='3099670'>the</span> <span
  m='3099780'>hard</span> <span m='3100090'>version.</span> <span
  m='3101290'>The</span> <span m='3101430'>simple</span> <span
  m='3101750'>version</span> <span m='3102160'>is</span> <span
  m='3103070'>it</span> <span m='3103230'>looks</span> <span
  m='3103430'>like</span> <span m='3103650'>that.</span> <span
  m='3105080'>You</span> <span m='3105420'>got</span> <span m='3105600'>a</span>
  <span m='3105630'>bunch</span> <span m='3105890'>of</span> <span
  m='3105970'>terms.</span> <span m='3107210'>Inside</span> <span
  m='3107760'>each</span> <span m='3107940'>term,</span> <span
  m='3108300'>you</span> <span m='3108400'>cut</span> <span
  m='3108460'>it</span> <span m='3108530'>down</span> <span
  m='3108750'>by</span> <span m='3108870'>a</span> <span
  m='3108930'>constant</span> <span m='3109380'>factor</span> <span
  m='3110460'>and</span> <span m='3110530'>then</span> <span
  m='3110650'>you</span> <span m='3110790'>add</span> <span
  m='3111120'>something</span> <span m='3111480'>at</span> <span
  m='3111570'>the</span> <span m='3111700'>end.</span> <span
  m='3112290'>That's</span> <span m='3112590'>the</span> <span
  m='3112660'>simple</span> <span m='3113170'>version</span> <span
  m='3113640'>of</span> <span m='3113750'>what</span> <span m='3114260'>a</span>
  <span m='3114350'>divide</span> <span m='3114630'>and</span> <span
  m='3114720'>conquer</span> <span m='3115020'>recurrence</span> <span
  m='3115490'>is.</span> <span m='3116130'>And</span> <span
  m='3116380'>you</span> <span m='3116460'>can</span> <span
  m='3116600'>throw</span> <span m='3116930'>in</span> <span
  m='3117040'>floors</span> <span m='3117480'>and</span> <span
  m='3117600'>ceilings</span> <span m='3118060'>and</span> <span
  m='3118150'>other</span> <span m='3118300'>junk</span> <span
  m='3118560'>too.</span> </p><p><span m='3119920'>Now</span> <span
  m='3120060'>I'm</span> <span m='3120200'>going</span> <span
  m='3120320'>to</span> <span m='3120380'>give</span> <span
  m='3120510'>you</span> <span m='3120580'>the</span> <span
  m='3120660'>formal</span> <span m='3121460'>version.</span> <span
  m='3124950'>So</span> <span m='3125090'>it</span> <span m='3125160'>has</span>
  <span m='3125400'>the</span> <span m='3125480'>form</span> <span
  m='3125940'>t</span> <span m='3126170'>of</span> <span m='3126290'>x</span>
  <span m='3127290'>equals</span> <span m='3128250'>some</span> <span
  m='3128550'>constant</span> <span m='3129080'>a1</span> <span
  m='3130620'>times</span> <span m='3131120'>t</span> <span
  m='3131900'>of</span> <span m='3132650'>a</span> <span
  m='3132720'>constant</span> <span m='3133310'>less</span> <span
  m='3133590'>than</span> <span m='3134080'>b1</span> <span
  m='3134510'>of</span> <span m='3134620'>x,</span> <span
  m='3135430'>plus</span> <span m='3135910'>some</span> <span
  m='3136140'>slop</span> <span m='3137080'>you're</span> <span
  m='3137280'>allowed</span> <span m='3137580'>to</span> <span
  m='3137680'>have</span> <span m='3138780'>like</span> <span
  m='3139000'>floors</span> <span m='3139480'>and</span> <span
  m='3139610'>ceilings</span> <span m='3140170'>and</span> <span
  m='3140440'>who</span> <span m='3140540'>knows</span> <span
  m='3140770'>what</span> <span m='3140920'>else.</span> </p><p><span
  m='3142170'>And</span> <span m='3142300'>then</span> <span
  m='3142440'>you</span> <span m='3142510'>get</span> <span
  m='3142680'>more</span> <span m='3142960'>of</span> <span
  m='3143050'>these.</span> <span m='3143630'>You</span> <span
  m='3143740'>get</span> <span m='3144020'>a2,</span> <span m='3146180'>t</span>
  <span m='3146660'>of</span> <span m='3147140'>b2x</span> <span
  m='3148580'>plus</span> <span m='3149430'>epsilon</span> <span
  m='3149950'>2x</span> <span m='3152010'>and</span> <span m='3152810'>so</span>
  <span m='3153010'>forth.</span> <span m='3153450'>And</span> <span
  m='3153550'>you</span> <span m='3153650'>can have</span> <span
  m='3154260'>any</span> <span m='3154480'>number</span> <span
  m='3154720'>of</span> <span m='3154790'>these</span> <span
  m='3154950'>you</span> <span m='3155050'>want</span> <span
  m='3155530'>up</span> <span m='3155690'>to</span> <span m='3155780'>a</span>
  <span m='3155840'>constant.</span> <span m='3157120'>So</span> <span
  m='3157290'>maybe</span> <span m='3157530'>there's</span> <span
  m='3157890'>a</span> <span m='3158040'>sub</span> <span m='3158300'>k</span>
  <span m='3159520'>t</span> <span m='3160500'>b</span> <span
  m='3160810'>sub</span> <span m='3160900'>kx</span> <span
  m='3161850'>plus</span> <span m='3162230'>epsilon</span> <span
  m='3162960'>kx.</span> <span m='3165860'>Plus</span> <span
  m='3166440'>some</span> <span m='3166910'>function</span> <span
  m='3167330'>of</span> <span m='3167400'>x</span> <span
  m='3167990'>sitting</span> <span m='3168230'>out</span> <span
  m='3168430'>here,</span> <span m='3168780'>like</span> <span
  m='3168990'>the</span> <span m='3169090'>x</span> <span
  m='3169250'>squared.</span> <span m='3171330'>And</span> <span
  m='3171860'>this</span> <span m='3172080'>happens</span> <span
  m='3172540'>for</span> <span m='3172670'>x</span> <span
  m='3172930'>bigger</span> <span m='3173170'>than</span> <span
  m='3173310'>some</span> <span m='3174270'>fixed</span> <span
  m='3174690'>value,</span> <span m='3175520'>some</span> <span
  m='3175730'>constant.</span> </p><p><span m='3177690'>Now,</span> <span
  m='3177940'>the</span> <span m='3178030'>constraints</span> <span
  m='3178650'>are,</span> <span m='3181600'>well,</span> <span
  m='3181890'>the</span> <span m='3182020'>ai's</span> <span
  m='3182620'>are</span> <span m='3182680'>positive</span> <span
  m='3183210'>constants.</span> <span m='3186550'>The</span> <span
  m='3186630'>bi's</span> <span m='3187650'>are</span> <span
  m='3188520'>positive</span> <span m='3189220'>and</span> <span
  m='3189400'>less</span> <span m='3189640'>than</span> <span
  m='3189780'>1.</span> <span m='3192650'>You</span> <span
  m='3192810'>gotta</span> <span m='3193150'>cut</span> <span
  m='3193380'>it</span> <span m='3193470'>down</span> <span
  m='3193790'>by</span> <span m='3193940'>a</span> <span
  m='3194000'>constant</span> <span m='3194450'>factor</span> <span
  m='3194840'>to</span> <span m='3194960'>be</span> <span m='3195110'>a</span>
  <span m='3195200'>divide</span> <span m='3195570'>and</span> <span
  m='3195670'>conquer</span> <span m='3196030'>recurrence.</span> <span
  m='3196490'>That's</span> <span m='3196700'>critical.</span> <span
  m='3199740'>k</span> <span m='3200260'>is</span> <span
  m='3200440'>fixed.</span> <span m='3201660'>It's</span> <span
  m='3202050'>constant.</span> </p><p><span m='3205720'>And</span> <span
  m='3205980'>these</span> <span m='3206240'>epsilon</span> <span
  m='3206780'>functions</span> <span m='3207720'>can't</span> <span
  m='3208120'>be</span> <span m='3208240'>too</span> <span
  m='3208540'>big.</span> <span m='3209990'>They</span> <span
  m='3210110'>can't</span> <span m='3210510'>be</span> <span
  m='3210620'>bigger</span> <span m='3210950'>than</span> <span
  m='3211600'>0</span> <span m='3211890'>of</span> <span m='3212140'>x</span>
  <span m='3212460'>over</span> <span m='3212640'>log</span> <span
  m='3213040'>squared</span> <span m='3213340'>of</span> <span
  m='3213440'>x.</span> <span m='3214390'>Almost</span> <span
  m='3214900'>as</span> <span m='3215010'>big</span> <span m='3215180'>as</span>
  <span m='3215290'>x,</span> <span m='3215460'>but</span> <span
  m='3215910'>you</span> <span m='3216030'>can't</span> <span
  m='3216240'>let</span> <span m='3216330'>them</span> <span
  m='3216400'>be</span> <span m='3216500'>too</span> <span
  m='3216790'>big</span> <span m='3217100'>or</span> <span
  m='3217240'>you'll</span> <span m='3218540'>not</span> <span
  m='3218830'>be</span> <span m='3218910'>cutting</span> <span
  m='3219200'>things</span> <span m='3219420'>down</span> <span
  m='3219620'>by</span> <span m='3219750'>a</span> <span
  m='3219790'>constant</span> <span m='3220230'>factor.</span> <span
  m='3222390'>Now,</span> <span m='3222600'>you</span> <span
  m='3222760'>don't</span> <span m='3222930'>get</span> <span
  m='3223130'>too</span> <span m='3223440'>hung</span> <span
  m='3223650'>up</span> <span m='3223820'>over</span> <span
  m='3224000'>this</span> <span m='3224260'>because</span> <span
  m='3226090'>you</span> <span m='3226410'>don't</span> <span
  m='3226560'>get</span> <span m='3226710'>too</span> <span
  m='3226930'>deep</span> <span m='3227260'>in</span> <span
  m='3227320'>the</span> <span m='3227390'>details.</span> <span
  m='3228030'>But</span> <span m='3228150'>this</span> <span
  m='3228380'>is</span> <span m='3228480'>that</span> <span
  m='3228620'>most</span> <span m='3229170'>0</span> <span m='3230130'>of</span>
  <span m='3230680'>x</span> <span m='3231100'>over</span> <span
  m='3231960'>log</span> <span m='3232290'>squared</span> <span
  m='3232600'>of</span> <span m='3232710'>x.</span> </p><p><span
  m='3235840'>And</span> <span m='3236070'>finally,</span> <span
  m='3236870'>the</span> <span m='3236970'>g</span> <span
  m='3237360'>thing</span> <span m='3238840'>has</span> <span
  m='3238940'>got</span> <span m='3239080'>to</span> <span m='3239140'>be</span>
  <span m='3239230'>polynomial.</span> <span m='3240550'>It</span> <span
  m='3240700'>can't</span> <span m='3241000'>be</span> <span
  m='3241090'>an</span> <span m='3241170'>exponent.</span> <span
  m='3241560'>You</span> <span m='3241630'>can't</span> <span
  m='3241820'>put</span> <span m='3242000'>2</span> <span m='3242120'>to</span>
  <span m='3242230'>the</span> <span m='3242330'>x</span> <span
  m='3242540'>here.</span> <span m='3243720'>And</span> <span
  m='3243900'>the</span> <span m='3243960'>formal</span> <span
  m='3244500'>way</span> <span m='3244690'>that's</span> <span
  m='3244900'>expressed</span> <span m='3245510'>is</span> <span
  m='3245710'>the</span> <span m='3245790'>derivative</span> <span
  m='3246400'>of</span> <span m='3246520'>g</span> <span m='3249610'>of</span>
  <span m='3249790'>x</span> <span m='3250660'>is</span> <span
  m='3250990'>less</span> <span m='3251330'>than</span> <span
  m='3251510'>x</span> <span m='3251720'>to</span> <span m='3251810'>the</span>
  <span m='3251910'>c</span> <span m='3252690'>for</span> <span
  m='3252850'>some</span> <span m='3253100'>constant</span> <span
  m='3253460'>c.</span> </p><p><span m='3258450'>That's</span> <span
  m='3258790'>it.</span> <span m='3259020'>So</span> <span
  m='3259140'>this</span> <span m='3259340'>is</span> <span m='3259460'>a</span>
  <span m='3259510'>mouthful.</span> <span m='3260900'>But</span> <span
  m='3261080'>like</span> <span m='3261300'>I</span> <span
  m='3261350'>said</span> <span m='3261570'>before,</span> <span
  m='3262860'>anything</span> <span m='3263230'>that</span> <span
  m='3263350'>looks</span> <span m='3263560'>like</span> <span
  m='3263770'>that,</span> <span m='3265550'>basically.</span> <span
  m='3266620'>As</span> <span m='3266740'>long</span> <span
  m='3266930'>as</span> <span m='3266990'>you</span> <span
  m='3267060'>don't</span> <span m='3267210'>throw</span> <span
  m='3267470'>in</span> <span m='3267550'>exponentials</span> <span
  m='3268270'>or</span> <span m='3268360'>do</span> <span
  m='3268540'>something</span> <span m='3269130'>too</span> <span
  m='3269310'>wild</span> <span m='3269700'>to</span> <span
  m='3269860'>it,</span> <span m='3271350'>it</span> <span
  m='3271510'>works.</span> </p><p><span m='3272370'>So</span> <span
  m='3272570'>let's</span> <span m='3273590'>see</span> <span
  m='3274600'>which</span> <span m='3274960'>of</span> <span
  m='3275050'>our</span> <span m='3275170'>guys</span> <span
  m='3275500'>over</span> <span m='3275690'>here</span> <span
  m='3276240'>are</span> <span m='3276400'>divide</span> <span
  m='3276820'>and</span> <span m='3276930'>conquer</span> <span
  m='3277290'>recurrences.</span> <span m='3283390'>How</span> <span
  m='3283500'>about</span> <span m='3283780'>this</span> <span
  m='3284020'>one?</span> <span m='3284210'>Towers</span> <span
  m='3284590'>of</span> <span m='3284710'>Hanoi,</span> <span
  m='3285070'>is</span> <span m='3285180'>that</span> <span m='3285380'>a</span>
  <span m='3285460'>divide</span> <span m='3285880'>and</span> <span
  m='3285990'>conquer</span> <span m='3286350'>recurrence?</span> <span
  m='3289300'>Some</span> <span m='3289610'>yes,</span> <span
  m='3289860'>some</span> <span m='3290150'>no.</span> <span
  m='3292350'>Who</span> <span m='3292590'>thinks</span> <span
  m='3292930'>no</span> <span m='3293540'>can</span> <span
  m='3293640'>tell</span> <span m='3293770'>me</span> <span
  m='3293880'>why</span> <span m='3294100'>it's</span> <span
  m='3294260'>not?</span> <span m='3294540'>Why</span> <span
  m='3294780'>isn't</span> <span m='3295040'>that?</span> </p><p><span
  m='3295920'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='3299250'>TOM
  LEIGHTON: That's</span> <span m='3299670'>right.</span> <span
  m='3300060'>The</span> <span m='3300500'>recurrence</span> <span
  m='3300940'>problem</span> <span m='3301350'>is</span> <span
  m='3301500'>n</span> <span m='3301630'>minus</span> <span m='3302040'>1</span>
  <span m='3303290'>and</span> <span m='3303480'>we've</span> <span
  m='3303630'>got</span> <span m='3303820'>to</span> <span
  m='3303880'>make</span> <span m='3304140'>it</span> <span
  m='3305510'>down</span> <span m='3305950'>by</span> <span m='3306110'>a</span>
  <span m='3306180'>constant</span> <span m='3306680'>factor</span> <span
  m='3307080'>here.</span> <span m='3307300'>The</span> <span
  m='3307390'>b1</span> <span m='3308070'>is</span> <span
  m='3308230'>less</span> <span m='3308610'>than</span> <span
  m='3308740'>1.</span> <span m='3309080'>It</span> <span
  m='3309190'>can't</span> <span m='3309450'>be</span> <span
  m='3309570'>equal</span> <span m='3309820'>to</span> <span
  m='3309890'>1.</span> <span m='3310820'>And</span> <span
  m='3311050'>this</span> <span m='3311260'>is</span> <span
  m='3311370'>not</span> <span m='3311620'>big</span> <span
  m='3311830'>enough</span> <span m='3312080'>to</span> <span
  m='3312180'>make</span> <span m='3312450'>up</span> <span
  m='3312610'>for</span> <span m='3313210'>the</span> <span m='3313660'>x
  over</span> <span m='3314100'>2</span> <span m='3314330'>term or</span> <span
  m='3314650'>something</span> <span m='3314930'>we're</span> <span
  m='3315030'>missing.</span> </p><p><span m='3316600'>So</span> <span
  m='3316790'>whenever</span> <span m='3317090'>you</span> <span
  m='3317210'>have</span> <span m='3317380'>an</span> <span m='3317470'>n</span>
  <span m='3317650'>minus</span> <span m='3318030'>1</span> <span
  m='3318500'>and</span> <span m='3318640'>minus</span> <span
  m='3319010'>2,</span> <span m='3319690'>that</span> <span
  m='3319930'>is</span> <span m='3320070'>not</span> <span
  m='3320340'>divide</span> <span m='3320670'>and</span> <span
  m='3320770'>conquer.</span> <span m='3322690'>We'll</span> <span
  m='3322850'>discuss</span> <span m='3323280'>those</span> <span
  m='3323610'>next</span> <span m='3323930'>time,</span> <span
  m='3324280'>on</span> <span m='3324420'>Thursday,</span> <span
  m='3324860'>how</span> <span m='3324940'>to</span> <span
  m='3325050'>solve</span> <span m='3325330'>those.</span> <span
  m='3326510'>So</span> <span m='3326660'>that's</span> <span
  m='3326890'>not</span> <span m='3327210'>divide</span> <span
  m='3327510'>and</span> <span m='3327610'>conquer.</span> </p><p><span
  m='3330010'>What</span> <span m='3330150'>about</span> <span
  m='3330350'>this</span> <span m='3330560'>one?</span> <span
  m='3330790'>Is</span> <span m='3330900'>that</span> <span
  m='3331090'>divide</span> <span m='3331370'>and</span> <span
  m='3331460'>conquer</span> <span m='3331830'>here?</span> <span
  m='3335480'>Yes.</span> <span m='3336710'>You've</span> <span
  m='3336890'>got</span> <span m='3337230'>two</span> <span
  m='3337510'>problems</span> <span m='3338040'>of</span> <span
  m='3338130'>half</span> <span m='3338450'>the</span> <span
  m='3338540'>size</span> <span m='3339750'>and</span> <span
  m='3339910'>you're</span> <span m='3340040'>adding</span> <span
  m='3340380'>a</span> <span m='3340440'>linear</span> <span
  m='3340780'>function.</span> <span m='3342060'>It's</span> <span
  m='3342180'>not</span> <span m='3342380'>exponential.</span> <span
  m='3343310'>It's</span> <span m='3343660'>polynomial.</span> <span
  m='3345130'>That</span> <span m='3345380'>is</span> <span
  m='3345570'>divide</span> <span m='3345870'>and</span> <span
  m='3345960'>conquer.</span> </p><p><span m='3347710'>What</span> <span
  m='3347980'>about</span> <span m='3348220'>this</span> <span
  m='3348870'>nasty</span> <span m='3349240'>guy?</span> <span
  m='3350830'>Is</span> <span m='3350970'>that</span> <span m='3351458'>divide
  and conquer?</span> <span m='3354700'>Yeah.</span> <span
  m='3355940'>You've</span> <span m='3356110'>got</span> <span
  m='3356560'>basically</span> <span m='3357080'>n</span> <span
  m='3357270'>over</span> <span m='3357470'>2</span> <span
  m='3357800'>here.</span> <span m='3358400'>Two</span> <span
  m='3358680'>n</span> <span m='3358820'>over</span> <span m='3358990'>2</span>
  <span m='3359200'>terms</span> <span m='3359660'>now.</span> <span
  m='3360320'>This</span> <span m='3360480'>is</span> <span
  m='3360570'>where</span> <span m='3360710'>that</span> <span
  m='3360900'>epsilon</span> <span m='3361420'>thing</span> <span
  m='3361610'>comes</span> <span m='3361860'>in</span> <span
  m='3361970'>handy.</span> <span m='3363200'>Because</span> <span
  m='3363420'>epsilon</span> <span m='3363910'>1</span> <span
  m='3364310'>of</span> <span m='3364540'>n,</span> <span m='3364820'>in</span>
  <span m='3364910'>this</span> <span m='3365080'>case,</span> <span
  m='3365600'>is</span> <span m='3367230'>floor</span> <span
  m='3368340'>n</span> <span m='3368540'>over</span> <span m='3369070'>2</span>
  <span m='3370780'>minus</span> <span m='3372250'>n</span> <span
  m='3372430'>over</span> <span m='3372620'>2.</span> <span
  m='3373020'>And</span> <span m='3373150'>that's,</span> <span
  m='3374020'>at</span> <span m='3374190'>most,</span> <span
  m='3374490'>1.</span> </p><p><span m='3378180'>So</span> <span
  m='3379070'>maybe</span> <span m='3379310'>we're</span> <span
  m='3379480'>adding</span> <span m='3379790'>a</span> <span
  m='3379860'>half</span> <span m='3380250'>here</span> <span
  m='3380570'>or</span> <span m='3380640'>something</span> <span
  m='3380880'>like</span> <span m='3381070'>that.</span> <span
  m='3381660'>And</span> <span m='3381760'>we're</span> <span
  m='3381880'>allowed</span> <span m='3382200'>to</span> <span
  m='3382290'>add</span> <span m='3382570'>anything</span> <span
  m='3382950'>up</span> <span m='3383070'>to</span> <span m='3383390'>n</span>
  <span m='3383600'>over</span> <span m='3383980'>log squared</span> <span
  m='3384220'>of</span> <span m='3384310'>n</span> <span m='3385250'>to</span>
  <span m='3385360'>fit.</span> <span m='3387240'>So</span> <span
  m='3387350'>you</span> <span m='3388100'>can</span> <span
  m='3388280'>mess</span> <span m='3388530'>around</span> <span
  m='3388790'>with</span> <span m='3388890'>the</span> <span
  m='3388940'>low</span> <span m='3389170'>order</span> <span
  m='3389350'>terms</span> <span m='3389690'>in</span> <span
  m='3389800'>here.</span> <span m='3390580'>And</span> <span
  m='3390780'>adding</span> <span m='3391070'>1</span> <span
  m='3391310'>is</span> <span m='3391450'>fine</span> <span
  m='3391690'>as</span> <span m='3391830'>well.</span> <span
  m='3393560'>So</span> <span m='3393680'>that</span> <span
  m='3393970'>qualifies.</span> </p><p><span m='3397670'>Let's</span> <span
  m='3398200'>check</span> <span m='3398520'>that</span> <span
  m='3398630'>this</span> <span m='3398780'>thing</span> <span
  m='3398950'>qualifies.</span> <span m='3400830'>Let's</span> <span
  m='3401030'>check</span> <span m='3401448'>that.</span> <span
  m='3410570'>Well,</span> <span m='3410910'>yeah.</span> <span
  m='3411280'>I</span> <span m='3411350'>got</span> <span m='3413380'>2</span>
  <span m='3414060'>constant</span> <span m='3414590'>a1</span> <span
  m='3416150'>t</span> <span m='3416490'>of</span> <span m='3416690'>1/2</span>
  <span m='3417130'>x.</span> <span m='3417840'>That's</span> <span
  m='3418060'>OK.</span> <span m='3419050'>8/9</span> <span m='3419930'>t</span>
  <span m='3420200'>of</span> <span m='3420330'>3/4</span> <span
  m='3421100'>x.</span> <span m='3421450'>That's</span> <span
  m='3421690'>OK.</span> <span m='3422850'>My</span> <span m='3423020'>g</span>
  <span m='3423290'>function</span> <span m='3423770'>is</span> <span
  m='3423880'>a</span> <span m='3423940'>polynomial.</span> <span
  m='3424690'>The</span> <span m='3424780'>derivative</span> <span
  m='3425350'>is</span> <span m='3425530'>2x.</span> <span
  m='3426020'>That's</span> <span m='3426250'>less</span> <span
  m='3426490'>than</span> <span m='3427350'>x</span> <span m='3427560'>to
  a</span> <span m='3427940'>power</span> <span m='3428230'>or</span> <span
  m='3428450'>of x to a</span> <span m='3428810'>power.</span> <span
  m='3429800'>So</span> <span m='3429980'>this</span> <span
  m='3430190'>fits.</span> </p><p><span m='3434430'>Any</span> <span
  m='3434640'>questions</span> <span m='3435150'>about</span> <span
  m='3435420'>the</span> <span m='3435480'>definition</span> <span
  m='3436860'>of</span> <span m='3437000'>a</span> <span
  m='3437040'>divide</span> <span m='3437450'>and</span> <span
  m='3437550'>conquer</span> <span m='3438050'>recurrence?</span> <span
  m='3443980'>And</span> <span m='3444110'>you</span> <span
  m='3444170'>can</span> <span m='3444280'>see</span> <span
  m='3444530'>why</span> <span m='3444730'>sort</span> <span
  m='3444920'>of</span> <span m='3444980'>they</span> <span
  m='3445060'>come</span> <span m='3445280'>up,</span> <span
  m='3445430'>because</span> <span m='3445600'>whenever</span> <span
  m='3445910'>you're</span> <span m='3446210'>solving</span> <span
  m='3446640'>a</span> <span m='3446700'>problem</span> <span
  m='3447690'>with</span> <span m='3447880'>recursive</span> <span
  m='3448390'>pieces</span> <span m='3448800'>that</span> <span
  m='3448920'>are</span> <span m='3449000'>a</span> <span
  m='3449050'>constant</span> <span m='3449420'>factor</span> <span
  m='3449680'>smaller,</span> <span m='3450780'>you're</span> <span
  m='3450900'>going</span> <span m='3451020'>to</span> <span
  m='3451080'>have</span> <span m='3451370'>something</span> <span
  m='3451760'>that</span> <span m='3452060'>looks</span> <span
  m='3452390'>like</span> <span m='3452570'>that.</span> </p><p><span
  m='3454140'>OK,</span> <span m='3454450'>so</span> <span
  m='3454590'>getting</span> <span m='3454860'>back</span> <span
  m='3455120'>to</span> <span m='3455210'>Akra</span> <span
  m='3455630'>and</span> <span m='3455865'>Bazzi.</span> <span
  m='3456100'>B</span> <span m='3456650'>They</span> <span
  m='3457420'>show</span> <span m='3457670'>up</span> <span
  m='3457780'>in</span> <span m='3457850'>my</span> <span
  m='3457980'>office.</span> <span m='3458580'>They</span> <span
  m='3458740'>claim</span> <span m='3459120'>to</span> <span
  m='3459210'>have</span> <span m='3459310'>solved</span> <span
  m='3459900'>anything</span> <span m='3460400'>like</span> <span
  m='3460690'>this.</span> <span m='3461050'>Now</span> <span
  m='3462470'>needless</span> <span m='3462780'>to</span> <span
  m='3462860'>say,</span> <span m='3463040'>I'm</span> <span
  m='3463120'>a</span> <span m='3463160'>little</span> <span
  m='3463360'>skeptical.</span> <span m='3464870'>I</span> <span
  m='3464920'>got</span> <span m='3465050'>to</span> <span
  m='3465120'>tell</span> <span m='3465340'>you,</span> <span
  m='3465440'>you're</span> <span m='3465640'>a</span> <span
  m='3465680'>professor</span> <span m='3466130'>at</span> <span
  m='3466200'>MIT,</span> <span m='3466750'>especially</span> <span
  m='3467150'>mathematics,</span> <span m='3468380'>and</span> <span
  m='3469170'>people</span> <span m='3469430'>are</span> <span
  m='3469490'>always</span> <span m='3469790'>coming</span> <span
  m='3470030'>by</span> <span m='3470420'>with</span> <span
  m='3471310'>proofs</span> <span m='3471700'>of</span> <span
  m='3472720'>the</span> <span m='3472820'>Riemann</span> <span
  m='3473210'>hypothesis,</span> <span m='3474020'>p</span> <span
  m='3474280'>equals</span> <span m='3474580'>np,</span> <span
  m='3475130'>p</span> <span m='3475330'>doesn't</span> <span
  m='3475670'>equal</span> <span m='3475970'>np.</span> <span
  m='3477210'>And</span> <span m='3477310'>this</span> <span
  m='3477460'>was</span> <span m='3477620'>a</span> <span
  m='3477680'>classic</span> <span m='3478850'>problem.</span> </p><p><span
  m='3480020'>Hundreds</span> <span m='3480650'>of</span> <span
  m='3480770'>researchers</span> <span m='3481340'>had</span> <span
  m='3481460'>studied</span> <span m='3481960'>recurrences</span> <span
  m='3483340'>for</span> <span m='3483490'>decades.</span> <span
  m='3484960'>And</span> <span m='3485110'>not</span> <span
  m='3485320'>only,</span> <span m='3485730'>it</span> <span
  m='3485910'>wasn't</span> <span m='3486160'>even</span> <span
  m='3486380'>believed</span> <span m='3486670'>that</span> <span
  m='3486790'>there</span> <span m='3486880'>was</span> <span
  m='3487690'>possibly</span> <span m='3488390'>a</span> <span
  m='3488440'>solution.</span> <span m='3489230'>It's</span> <span
  m='3489450'>not</span> <span m='3489580'>like</span> <span
  m='3489700'>it's</span> <span m='3489820'>one</span> <span
  m='3489940'>of</span> <span m='3490000'>these</span> <span
  m='3490140'>open</span> <span m='3490380'>questions</span> <span
  m='3490800'>where</span> <span m='3490910'>we</span> <span
  m='3491010'>all</span> <span m='3491250'>believe</span> <span
  m='3491630'>p</span> <span m='3491770'>doesn't</span> <span
  m='3492030'>equal</span> <span m='3492280'>np</span> <span
  m='3492940'>and</span> <span m='3493050'>it's</span> <span
  m='3493140'>just</span> <span m='3493300'>a</span> <span
  m='3493340'>matter</span> <span m='3493550'>of</span> <span
  m='3493620'>proving</span> <span m='3493940'>it.</span> <span
  m='3494930'>People</span> <span m='3495240'>didn't</span> <span
  m='3495490'>think</span> <span m='3496420'>a</span> <span
  m='3496540'>solution</span> <span m='3497040'>existed</span> <span
  m='3497650'>that</span> <span m='3497740'>would</span> <span
  m='3497840'>be</span> <span m='3498010'>clean.</span> <span
  m='3498770'>I</span> <span m='3498840'>mean,</span> <span
  m='3498990'>look</span> <span m='3499130'>at</span> <span
  m='3499200'>just</span> <span m='3499360'>the</span> <span
  m='3499430'>definition's</span> <span m='3500010'>a</span> <span
  m='3500090'>mess.</span> <span m='3500970'>And</span> <span
  m='3501080'>how</span> <span m='3501270'>could</span> <span
  m='3501380'>there</span> <span m='3501480'>possibly</span> <span
  m='3501990'>be</span> <span m='3502210'>a</span> <span
  m='3502270'>clean</span> <span m='3502600'>solution</span> <span
  m='3503040'>to</span> <span m='3503100'>that?</span> </p><p><span
  m='3505060'>So</span> <span m='3505250'>it's</span> <span
  m='3505360'>sort</span> <span m='3505590'>of</span> <span
  m='3505650'>like</span> <span m='3506520'>the</span> <span
  m='3506650'>holy</span> <span m='3506970'>grail.</span> <span
  m='3508020'>It</span> <span m='3508100'>doesn't</span> <span
  m='3508350'>exist,</span> <span m='3508840'>but</span> <span
  m='3508850'>it's</span> <span m='3508970'>fun</span> <span
  m='3509200'>to</span> <span m='3509270'>think</span> <span
  m='3509520'>about,</span> <span m='3509940'>that</span> <span
  m='3510220'>fantasy,</span> <span m='3510780'>maybe</span> <span
  m='3511190'>there's</span> <span m='3511380'>a</span> <span
  m='3511430'>solution</span> <span m='3511950'>and</span> <span
  m='3512410'>you</span> <span m='3512560'>could</span> <span
  m='3512680'>find</span> <span m='3513020'>it.</span> <span
  m='3515370'>And</span> <span m='3515500'>much</span> <span
  m='3515720'>less,</span> <span m='3516590'>these</span> <span
  m='3516890'>aren't</span> <span m='3517300'>reputable</span> <span
  m='3517830'>researchers</span> <span m='3518380'>in</span> <span
  m='3518470'>my</span> <span m='3518620'>office.</span> <span
  m='3518980'>These</span> <span m='3519220'>are</span> <span
  m='3519320'>two</span> <span m='3519540'>students</span> <span
  m='3520360'>from</span> <span m='3520590'>Beirut</span> <span
  m='3521860'>named</span> <span m='3522190'>Akra</span> <span
  m='3522630'>and</span> <span m='3522835'>Bazzi</span> <span
  m='3523450'>claiming</span> <span m='3524080'>they've</span> <span
  m='3524340'>figured</span> <span m='3524610'>out</span> <span
  m='3524740'>this</span> <span m='3524910'>thing</span> <span
  m='3525130'>that</span> <span m='3525240'>all</span> <span
  m='3525440'>these</span> <span m='3525650'>professors</span> <span
  m='3526560'>been</span> <span m='3526690'>teaching</span> <span
  m='3527030'>this</span> <span m='3527160'>stuff</span> <span
  m='3527460'>in</span> <span m='3527540'>6046</span> <span
  m='3528190'>for</span> <span m='3528300'>years</span> <span
  m='3529030'>said</span> <span m='3530360'>you've</span> <span
  m='3530560'>got</span> <span m='3530680'>to</span> <span m='3530740'>do</span>
  <span m='3530830'>plug</span> <span m='3531050'>and</span> <span
  m='3531140'>chug.</span> </p><p><span m='3533350'>Anyway,</span> <span
  m='3534790'>they'd</span> <span m='3534950'>been</span> <span
  m='3535060'>kicked</span> <span m='3535320'>out</span> <span
  m='3535440'>of</span> <span m='3535510'>everybody</span> <span
  m='3535790'>else's</span> <span m='3536080'>office,</span> <span
  m='3536420'>so</span> <span m='3536490'>I</span> <span
  m='3536530'>said,</span> <span m='3536710'>OK,</span> <span
  m='3537080'>let's</span> <span m='3537530'>do</span> <span
  m='3537740'>it.</span> <span m='3538320'>Show</span> <span
  m='3538670'>me</span> <span m='3538910'>the</span> <span
  m='3539040'>solution.</span> <span m='3540650'>And</span> <span
  m='3540830'>they</span> <span m='3540930'>did.</span> <span
  m='3541930'>And</span> <span m='3542050'>I</span> <span m='3542080'>go,</span>
  <span m='3542710'>holy</span> <span m='3543000'>cow.</span> <span
  m='3544280'>It's</span> <span m='3544500'>right.</span> <span
  m='3545460'>It</span> <span m='3545530'>looks</span> <span
  m='3545700'>good.</span> <span m='3545880'>Now,</span> <span
  m='3545980'>they</span> <span m='3546100'>had</span> <span
  m='3546210'>a</span> <span m='3546240'>few</span> <span
  m='3546440'>details</span> <span m='3546900'>wrong,</span> <span
  m='3547110'>but</span> <span m='3547890'>my</span> <span
  m='3548040'>goodness,</span> <span m='3548470'>the</span> <span
  m='3548630'>answer</span> <span m='3548950'>was</span> <span
  m='3549130'>correct</span> <span m='3549560'>and</span> <span
  m='3549720'>it's</span> <span m='3549910'>amazingly</span> <span
  m='3550600'>simple.</span> <span m='3552680'>So</span> <span
  m='3553240'>now</span> <span m='3553470'>we</span> <span
  m='3553580'>teach</span> <span m='3553890'>it.</span> <span
  m='3555260'>And</span> <span m='3557360'>in</span> <span
  m='3557420'>fact,</span> <span m='3557620'>you</span> <span
  m='3557690'>can</span> <span m='3557810'>write</span> <span
  m='3558030'>the</span> <span m='3558110'>solution</span> <span
  m='3558610'>down</span> <span m='3558810'>easier</span> <span
  m='3559300'>than</span> <span m='3559510'>you</span> <span
  m='3559600'>can</span> <span m='3559770'>write</span> <span
  m='3560000'>the</span> <span m='3560070'>definition</span> <span
  m='3560670'>of</span> <span m='3561430'>divide</span> <span
  m='3561800'>and</span> <span m='3561890'>conquer</span> <span
  m='3562200'>recurrence.</span> <span m='3564870'>Really</span> <span
  m='3565330'>remarkable.</span> </p><p><span m='3568870'>So</span> <span
  m='3569140'>the</span> <span m='3569260'>theorem</span> <span
  m='3571000'>by</span> <span m='3571380'>Akra</span> <span
  m='3571530'>and</span> <span m='3571940'>Bazzi</span> <span
  m='3579220'>in</span> <span m='3579500'>'96.</span> <span
  m='3584290'>Set</span> <span m='3585310'>p,</span> <span
  m='3585970'>real</span> <span m='3586220'>number,</span> <span
  m='3587620'>So</span> <span m='3587870'>that</span> <span
  m='3590520'>the</span> <span m='3590640'>sum</span> <span m='3592140'>i</span>
  <span m='3592470'>equals</span> <span m='3592870'>1</span> <span
  m='3593130'>to k</span> <span m='3595240'>of</span> <span
  m='3595590'>ai</span> <span m='3596430'>times</span> <span
  m='3596800'>bi</span> <span m='3597730'>to</span> <span m='3597830'>the</span>
  <span m='3597930'>p</span> <span m='3598850'>equals</span> <span
  m='3599290'>1.</span> <span m='3600720'>So</span> <span m='3600890'>the</span>
  <span m='3601040'>ai's</span> <span m='3601800'>are</span> <span
  m='3601900'>these</span> <span m='3602170'>things</span> <span
  m='3602940'>here.</span> <span m='3604160'>The</span> <span
  m='3604250'>bi's</span> <span m='3604840'>are</span> <span
  m='3604890'>the</span> <span m='3604970'>fractions</span> <span
  m='3605540'>here.</span> <span m='3607720'>All</span> <span
  m='3607870'>right,</span> <span m='3608030'>find</span> <span m='3608360'>a
  p</span> <span m='3608910'>such</span> <span m='3609170'>that</span> <span
  m='3609350'>this</span> <span m='3611100'>sum</span> <span
  m='3611670'>is</span> <span m='3611820'>1.</span> <span
  m='3613540'>Then</span> <span m='3613920'>the</span> <span
  m='3614040'>answer</span> <span m='3614380'>is</span> <span
  m='3614470'>this.</span> <span m='3616920'>Then</span> <span
  m='3617340'>t</span> <span m='3617630'>of</span> <span m='3617760'>x</span>
  <span m='3619730'>equals</span> <span m='3621100'>theta.</span> <span
  m='3621740'>We're</span> <span m='3621830'>going</span> <span
  m='3621960'>to</span> <span m='3622020'>use</span> <span
  m='3622190'>our</span> <span m='3622250'>asymptotic</span> <span
  m='3622780'>notation.</span> <span m='3624030'>x</span> <span
  m='3624350'>to</span> <span m='3624440'>the</span> <span m='3624520'>p</span>
  <span m='3625360'>plus</span> <span m='3626490'>x</span> <span
  m='3626840'>to</span> <span m='3626920'>the</span> <span m='3626990'>p</span>
  <span m='3627500'>times</span> <span m='3627810'>the</span> <span
  m='3627940'>integral</span> <span m='3629180'>from</span> <span
  m='3629420'>1</span> <span m='3630730'>to</span> <span m='3630860'>x</span>
  <span m='3632140'>g</span> <span m='3632450'>of</span> <span
  m='3632560'>u.</span> <span m='3633060'>G</span> <span m='3633310'>is</span>
  <span m='3633480'>that</span> <span m='3634230'>polynomial</span> <span
  m='3634820'>thing,</span> <span m='3635060'>that</span> <span
  m='3635430'>thing</span> <span m='3635660'>at</span> <span
  m='3635750'>the</span> <span m='3635870'>end.</span> <span
  m='3637070'>Over</span> <span m='3637660'>u</span> <span m='3638020'>to</span>
  <span m='3638100'>the</span> <span m='3638210'>p</span> <span
  m='3638410'>minus</span> <span m='3638780'>1</span> <span
  m='3639880'>du.</span> </p><p><span m='3643050'>That's</span> <span
  m='3643320'>it.</span> <span m='3645460'>This</span> <span
  m='3645610'>is</span> <span m='3645720'>really</span> <span
  m='3646030'>great</span> <span m='3646360'>news</span> <span
  m='3646710'>for</span> <span m='3646840'>you</span> <span
  m='3646990'>guys,</span> <span m='3647910'>especially</span> <span
  m='3648070'>if</span> <span m='3648270'>you</span> <span m='3648370'>go</span>
  <span m='3648450'>on</span> <span m='3648530'>to</span> <span
  m='3648660'>algorithms,</span> <span m='3649940'>because</span> <span
  m='3650210'>you</span> <span m='3650270'>don't</span> <span
  m='3650370'>have</span> <span m='3650460'>to</span> <span
  m='3650540'>deal</span> <span m='3650770'>with</span> <span
  m='3650870'>plug</span> <span m='3651140'>and</span> <span
  m='3651270'>chug</span> <span m='3651640'>on</span> <span
  m='3651800'>nasty</span> <span m='3652180'>things.</span> <span
  m='3653460'>You</span> <span m='3653580'>just</span> <span
  m='3654380'>solve</span> <span m='3654830'>the</span> <span
  m='3655510'>answer.</span> </p><p><span m='3658790'>Now,</span> <span
  m='3659950'>the</span> <span m='3660070'>proof</span> <span
  m='3661140'>is</span> <span m='3661350'>by</span> <span
  m='3661550'>guess</span> <span m='3661890'>and</span> <span
  m='3662010'>verify.</span> <span m='3663300'>And</span> <span
  m='3663540'>they</span> <span m='3663650'>made</span> <span
  m='3663870'>a</span> <span m='3663940'>really</span> <span
  m='3664360'>good</span> <span m='3664580'>guess.</span> <span
  m='3667510'>You</span> <span m='3667810'>wouldn't</span> <span
  m='3668730'>think</span> <span m='3668980'>of</span> <span
  m='3669050'>looking</span> <span m='3669300'>at</span> <span
  m='3669390'>that,</span> <span m='3669650'>oh,</span> <span
  m='3670030'>I'm</span> <span m='3670140'>going</span> <span
  m='3670260'>to</span> <span m='3670330'>guess</span> <span
  m='3670580'>this.</span> <span m='3670950'>Probably</span> <span
  m='3672000'>not.</span> <span m='3673070'>And</span> <span
  m='3673480'>there's</span> <span m='3673630'>no</span> <span
  m='3673940'>real</span> <span m='3674220'>numbers</span> <span
  m='3674880'>to</span> <span m='3674990'>try</span> <span m='3675430'>to</span>
  <span m='3675530'>guess</span> <span m='3676050'>this.</span> <span
  m='3676310'>It's</span> <span m='3676460'>asymptotic</span> <span
  m='3677050'>notation.</span> <span m='3678850'>But</span> <span
  m='3679270'>it</span> <span m='3679430'>works.</span> <span
  m='3679860'>You</span> <span m='3680160'>can</span> <span
  m='3680460'>verify</span> <span m='3680960'>it</span> <span
  m='3681050'>by</span> <span m='3681220'>induction.</span> <span
  m='3681640'>It's</span> <span m='3681750'>a</span> <span
  m='3681800'>little</span> <span m='3682010'>painful</span> <span
  m='3682810'>to</span> <span m='3682940'>verify</span> <span
  m='3683350'>by</span> <span m='3683540'>induction,</span> <span
  m='3683920'>but</span> <span m='3684040'>you</span> <span
  m='3684130'>can</span> <span m='3684420'>do</span> <span
  m='3684600'>it.</span> <span m='3684880'>We</span> <span
  m='3685030'>won't</span> <span m='3685480'>do</span> <span
  m='3685740'>it</span> <span m='3685810'>in</span> <span
  m='3685890'>class.</span> <span m='3686580'>I</span> <span
  m='3686760'>did</span> <span m='3686950'>try</span> <span
  m='3687230'>one</span> <span m='3687450'>year,</span> <span
  m='3687650'>and</span> <span m='3687750'>it</span> <span
  m='3687840'>was</span> <span m='3688040'>a</span> <span
  m='3688100'>disaster,</span> <span m='3688660'>so</span> <span
  m='3688900'>we</span> <span m='3689010'>don't</span> <span
  m='3689570'>do</span> <span m='3689740'>it</span> <span m='3689810'>in</span>
  <span m='3689880'>class</span> <span m='3690250'>anymore.</span> </p><p><span
  m='3691400'>But</span> <span m='3691540'>let's</span> <span
  m='3691750'>see</span> <span m='3691890'>some</span> <span
  m='3692060'>examples</span> <span m='3692670'>of</span> <span
  m='3692770'>how</span> <span m='3692960'>to</span> <span
  m='3693200'>apply</span> <span m='3693610'>this.</span> <span
  m='3696750'>So</span> <span m='3696950'>let's</span> <span
  m='3697150'>start</span> <span m='3697580'>with</span> <span
  m='3698270'>merge</span> <span m='3698710'>sort,</span> <span
  m='3700610'>which</span> <span m='3700890'>is</span> <span
  m='3701120'>the</span> <span m='3701200'>second</span> <span
  m='3701600'>one</span> <span m='3701780'>here.</span> <span
  m='3702582'>Let's</span> <span m='3702742'>do</span> <span
  m='3702903'>that.</span> <span m='3713190'>All</span> <span
  m='3713370'>right,</span> <span m='3713550'>so</span> <span
  m='3714660'>you</span> <span m='3714740'>got</span> <span
  m='3714840'>an</span> <span m='3714910'>example</span> <span
  m='3715610'>here.</span> <span m='3716390'>t</span> <span
  m='3716660'>of</span> <span m='3716770'>x</span> <span
  m='3718000'>equals</span> <span m='3720470'>2</span> <span
  m='3720990'>t</span> <span m='3721210'>of</span> <span m='3721330'>x</span>
  <span m='3721540'>over</span> <span m='3721730'>2</span> <span
  m='3723320'>plus</span> <span m='3723990'>n</span> <span
  m='3724260'>minus</span> <span m='3724660'>1,</span> <span
  m='3725140'>or</span> <span m='3725390'>x</span> <span
  m='3725630'>minus</span> <span m='3725940'>1,</span> <span
  m='3726510'>x</span> <span m='3726760'>now.</span> <span
  m='3727860'>And</span> <span m='3728080'>I'm</span> <span
  m='3728180'>not</span> <span m='3728380'>even</span> <span
  m='3728520'>going</span> <span m='3728640'>to</span> <span
  m='3728700'>worry</span> <span m='3729030'>about</span> <span
  m='3729270'>powers</span> <span m='3729680'>of</span> <span
  m='3729780'>2</span> <span m='3729990'>anymore.</span> <span
  m='3730630'>I</span> <span m='3730710'>don't</span> <span
  m='3730850'>care.</span> <span m='3731210'>It's</span> <span
  m='3731300'>going</span> <span m='3731430'>to</span> <span
  m='3731500'>be</span> <span m='3731580'>fine.</span> </p><p><span
  m='3734210'>All</span> <span m='3734450'>right,</span> <span
  m='3734630'>what</span> <span m='3734950'>is</span> <span m='3735260'>p</span>
  <span m='3735770'>in</span> <span m='3735880'>this</span> <span
  m='3736080'>case?</span> <span m='3737670'>I've</span> <span
  m='3737830'>only</span> <span m='3738000'>got</span> <span
  m='3738170'>one</span> <span m='3738510'>term.</span> <span
  m='3738780'>I</span> <span m='3738810'>don't</span> <span
  m='3738970'>even</span> <span m='3739140'>need</span> <span
  m='3739280'>a</span> <span m='3739330'>sum</span> <span
  m='3739780'>from</span> <span m='3739930'>that</span> <span
  m='3740090'>definition</span> <span m='3740630'>over</span> <span
  m='3740800'>there.</span> <span m='3742260'>What's</span> <span
  m='3742560'>the</span> <span m='3742640'>value</span> <span
  m='3743080'>of</span> <span m='3743210'>p</span> <span m='3744870'>for</span>
  <span m='3745020'>this</span> <span m='3745230'>guy?</span> <span
  m='3747400'>So</span> <span m='3747590'>I've</span> <span
  m='3747690'>got</span> <span m='3747930'>a1</span> <span m='3748390'>is</span>
  <span m='3748550'>2.</span> <span m='3750760'>b1</span> <span
  m='3751410'>is</span> <span m='3751590'>1/2.</span> <span
  m='3753280'>Just</span> <span m='3753570'>one</span> <span
  m='3753770'>term.</span> <span m='3757320'>What's</span> <span
  m='3757600'>the</span> <span m='3757680'>value</span> <span
  m='3758070'>of</span> <span m='3758210'>p</span> <span m='3758660'>such</span>
  <span m='3758990'>that</span> <span m='3759240'>2</span> <span
  m='3759620'>times</span> <span m='3759960'>1/2</span> <span
  m='3760290'>to</span> <span m='3760390'>the</span> <span m='3760480'>p</span>
  <span m='3760800'>equals</span> <span m='3761120'>1?</span> <span
  m='3762900'>1.</span> <span m='3763410'>Doesn't</span> <span
  m='3763690'>get</span> <span m='3763830'>much</span> <span
  m='3764010'>simpler.</span> <span m='3766020'>So</span> <span
  m='3766580'>2</span> <span m='3766960'>times</span> <span
  m='3767390'>1/2</span> <span m='3768300'>to</span> <span
  m='3768500'>the</span> <span m='3768610'>p</span> <span
  m='3769030'>equals</span> <span m='3769400'>1</span> <span
  m='3769780'>implies</span> <span m='3770480'>p</span> <span
  m='3771470'>is</span> <span m='3771620'>1.</span> </p><p><span
  m='3773460'>All</span> <span m='3773580'>right,</span> <span
  m='3773760'>now</span> <span m='3774080'>I</span> <span
  m='3774180'>just</span> <span m='3774400'>plug</span> <span
  m='3774700'>into</span> <span m='3775050'>the</span> <span
  m='3775180'>integral</span> <span m='3775550'>over</span> <span
  m='3775720'>there.</span> <span m='3777370'>All</span> <span
  m='3777520'>right,</span> <span m='3777630'>let's</span> <span
  m='3777790'>do</span> <span m='3777980'>that.</span> <span
  m='3792370'>So</span> <span m='3792930'>t</span> <span m='3793180'>of</span>
  <span m='3793280'>x</span> <span m='3794980'>equals</span> <span
  m='3795420'>theta.</span> <span m='3797210'>Well,</span> <span m='3797470'>x
  to</span> <span m='3797760'>the</span> <span m='3797830'>p</span> <span
  m='3798080'>is</span> <span m='3798240'>x</span> <span m='3798500'>to
  the</span> <span m='3798570'>1</span> <span m='3799040'>plus</span> <span
  m='3800090'>just</span> <span m='3800280'>take</span> <span
  m='3800440'>off</span> <span m='3800620'>the</span> <span
  m='3800720'>1,</span> <span m='3801460'>plus</span> <span m='3801790'>x</span>
  <span m='3802090'>times</span> <span m='3802380'>the</span> <span
  m='3802500'>integral</span> <span m='3803520'>1</span> <span
  m='3803790'>to</span> <span m='3803880'>x.</span> <span
  m='3804960'>What's</span> <span m='3805460'>the</span> <span
  m='3805720'>g</span> <span m='3806260'>function?</span> <span
  m='3809220'>What's</span> <span m='3809550'>g</span> <span
  m='3809880'>of</span> <span m='3810000'>x</span> <span m='3810350'>in</span>
  <span m='3810440'>this</span> <span m='3810610'>case?</span> <span
  m='3814000'>x</span> <span m='3814320'>minus</span> <span
  m='3814710'>1.</span> <span m='3815950'>So</span> <span m='3816260'>I</span>
  <span m='3816330'>take</span> <span m='3816580'>the</span> <span
  m='3816730'>integral</span> <span m='3817780'>of</span> <span
  m='3818550'>g</span> <span m='3818940'>of</span> <span m='3819090'>u</span>
  <span m='3820250'>is</span> <span m='3820460'>just</span> <span
  m='3820820'>u</span> <span m='3821060'>minus</span> <span m='3821430'>1</span>
  <span m='3822730'>over</span> <span m='3825420'>u</span> <span
  m='3825870'>to</span> <span m='3825980'>the</span> <span m='3826510'>p</span>
  <span m='3826998'>plus 1</span> <span m='3830450'>p</span> <span
  m='3830860'>minus</span> <span m='3831410'>1.</span> </p><p><span
  m='3833770'>Did</span> <span m='3833910'>I</span> <span
  m='3834020'>write</span> <span m='3834270'>the</span> <span
  m='3834340'>formula</span> <span m='3834830'>right?</span> <span
  m='3836310'>Is it</span> <span m='3836740'>plus 1</span> <span
  m='3836990'>or</span> <span m='3837050'>minus</span> <span
  m='3837520'>1</span> <span m='3837910'>here?</span> <span m='3840840'>Did
  I</span> <span m='3840960'>get</span> <span m='3841090'>it?</span> <span
  m='3841640'>p</span> <span m='3841820'>plus</span> <span m='3842250'>1.</span>
  <span m='3842520'>Sorry,</span> <span m='3843850'>didn't</span> <span
  m='3844020'>write</span> <span m='3844270'>that</span> <span
  m='3844460'>right.</span> <span m='3844970'>p</span> <span
  m='3845180'>plus</span> <span m='3845660'>1</span> <span m='3846644'>over
  here.</span> <span m='3850670'>All</span> <span m='3850840'>right,</span>
  <span m='3851050'>so</span> <span m='3851200'>u</span> <span
  m='3851550'>to</span> <span m='3851620'>the</span> <span m='3851740'>p</span>
  <span m='3852000'>plus</span> <span m='3852360'>1</span> <span
  m='3852530'>is</span> <span m='3852670'>u</span> <span
  m='3852830'>squared</span> <span m='3854690'>du.</span> <span
  m='3858410'>This</span> <span m='3858680'>is</span> <span
  m='3860310'>theta</span> <span m='3860600'>of</span> <span
  m='3860820'>x</span> <span m='3861260'>plus</span> <span m='3861730'>x</span>
  <span m='3863140'>integral</span> <span m='3865040'>1</span> <span
  m='3865400'>over</span> <span m='3865650'>u</span> <span
  m='3866840'>minus</span> <span m='3867310'>1</span> <span
  m='3867580'>over</span> <span m='3867780'>u</span> <span
  m='3867980'>squared.</span> <span m='3880650'>The</span> <span
  m='3880790'>integral</span> <span m='3881070'>of</span> <span
  m='3881150'>1</span> <span m='3881440'>over</span> <span m='3881640'>u</span>
  <span m='3881910'>is</span> <span m='3882030'>the</span> <span
  m='3882110'>log</span> <span m='3882480'>of</span> <span m='3882580'>u.</span>
  <span m='3885500'>The</span> <span m='3885650'>integral</span> <span
  m='3886090'>of</span> <span m='3886200'>1</span> <span m='3886460'>over</span>
  <span m='3887470'>u</span> <span m='3887730'>squared</span> <span
  m='3888660'>is</span> <span m='3889900'>1</span> <span m='3890250'>over</span>
  <span m='3890460'>u,</span> <span m='3890640'>but</span> <span
  m='3890760'>I</span> <span m='3890820'>changed</span> <span
  m='3891160'>the</span> <span m='3891230'>sign</span> <span
  m='3891610'>there.</span> <span m='3893800'>1</span> <span
  m='3894060'>to</span> <span m='3894220'>x.</span> <span m='3899860'>All</span>
  <span m='3900070'>right,</span> <span m='3900280'>so</span> <span
  m='3900390'>I</span> <span m='3900460'>get</span> <span
  m='3900730'>theta</span> <span m='3901816'>of</span> <span
  m='3902180'>x</span> <span m='3902650'>plus</span> <span m='3903220'>x</span>
  <span m='3903630'>times</span> <span m='3905360'>log</span> <span
  m='3905680'>of</span> <span m='3905800'>x</span> <span m='3908030'>plus</span>
  <span m='3908450'>1</span> <span m='3908670'>over</span> <span
  m='3908910'>x</span> <span m='3911280'>minus</span> <span
  m='3911940'>log</span> <span m='3912260'>of</span> <span m='3912350'>0.</span>
  <span m='3912790'>That's</span> <span m='3913700'>log</span> <span
  m='3913900'>of</span> <span m='3913990'>1</span> <span m='3914200'>is</span>
  <span m='3914360'>nothing.</span> <span m='3915820'>Minus</span> <span
  m='3916310'>1.</span> </p><p><span m='3921160'>And</span> <span
  m='3922860'>I'm</span> <span m='3923010'>doing</span> <span
  m='3923260'>thetas</span> <span m='3923780'>here</span> <span
  m='3924150'>so</span> <span m='3924310'>I</span> <span m='3924360'>can</span>
  <span m='3924520'>forget</span> <span m='3924960'>the</span> <span
  m='3925030'>low</span> <span m='3925290'>order</span> <span
  m='3925480'>terms.</span> <span m='3927870'>So</span> <span
  m='3928010'>I</span> <span m='3928070'>get</span> <span m='3928510'>x</span>
  <span m='3928810'>log</span> <span m='3929120'>x</span> <span
  m='3929470'>plus</span> <span m='3929830'>1</span> <span
  m='3930270'>minus</span> <span m='3930740'>x.</span> <span
  m='3932430'>This</span> <span m='3932710'>is</span> <span
  m='3932810'>the</span> <span m='3932920'>only</span> <span
  m='3933100'>term</span> <span m='3933360'>that</span> <span
  m='3933480'>survives,</span> <span m='3934520'>x</span> <span
  m='3934820'>log</span> <span m='3935070'>x.</span> <span
  m='3940040'>And</span> <span m='3940430'>that's</span> <span
  m='3941100'>right.</span> <span m='3942860'>t</span> <span m='3943040'>of
  n</span> <span m='3943370'>is in</span> <span m='3943510'>fact</span> <span
  m='3943770'>tilde</span> <span m='3944020'>n</span> <span
  m='3944120'>log</span> <span m='3944500'>n,</span> <span m='3945330'>so</span>
  <span m='3945400'>in</span> <span m='3945470'>fact,</span> <span
  m='3945830'>it's</span> <span m='3945920'>theta</span> <span
  m='3947160'>n</span> <span m='3947350'>log</span> <span m='3947480'>n.</span>
  </p><p><span m='3953030'>Now,</span> <span m='3953690'>in</span> <span
  m='3953860'>this</span> <span m='3954050'>case,</span> <span
  m='3954530'>going</span> <span m='3954830'>through</span> <span
  m='3954970'>the</span> <span m='3955130'>integral</span> <span
  m='3955430'>and</span> <span m='3955660'>all</span> <span
  m='3955870'>that,</span> <span m='3956150'>maybe</span> <span
  m='3956410'>that</span> <span m='3956550'>was</span> <span
  m='3956690'>harder</span> <span m='3957000'>than</span> <span
  m='3957150'>just</span> <span m='3957410'>guessing</span> <span
  m='3957770'>and</span> <span m='3957890'>verifying.</span> <span
  m='3959420'>And</span> <span m='3959650'>by</span> <span m='3959790'>the
  way,</span> <span m='3959950'>guess</span> <span m='3960200'>and</span> <span
  m='3960290'>verify</span> <span m='3960740'>got</span> <span
  m='3961000'>it</span> <span m='3961130'>really</span> <span
  m='3961420'>the</span> <span m='3961520'>exact</span> <span
  m='3961970'>answer.</span> <span m='3964060'>The</span> <span
  m='3964080'>nice</span> <span m='3964340'>thing</span> <span
  m='3964500'>is</span> <span m='3966270'>this</span> <span
  m='3966580'>works</span> <span m='3966950'>for</span> <span
  m='3967450'>the</span> <span m='3967570'>nasty</span> <span
  m='3967910'>guys</span> <span m='3968220'>too.</span> <span
  m='3969730'>In</span> <span m='3969830'>fact,</span> <span
  m='3971920'>let's</span> <span m='3972140'>figure</span> <span
  m='3972550'>out</span> <span m='3973710'>the</span> <span
  m='3973830'>solution</span> <span m='3974390'>to</span> <span
  m='3974480'>this</span> <span m='3974810'>thing,</span> <span
  m='3976590'>which</span> <span m='3976820'>I</span> <span
  m='3976890'>guarantee</span> <span m='3977370'>you</span> <span
  m='3977490'>is</span> <span m='3977590'>a</span> <span m='3977650'>pain</span>
  <span m='3977950'>to</span> <span m='3978050'>do</span> <span
  m='3979890'>without</span> <span m='3980210'>this</span> <span
  m='3980626'>method.</span> </p><p><span m='3993520'>The</span> <span
  m='3993610'>first</span> <span m='3993940'>thing</span> <span
  m='3994080'>to</span> <span m='3994140'>do</span> <span m='3994390'>is</span>
  <span m='3994510'>compute</span> <span m='3994930'>p.</span> <span
  m='3997050'>So</span> <span m='3997350'>to</span> <span m='3997430'>do</span>
  <span m='3997680'>that,</span> <span m='3998240'>we</span> <span
  m='3998390'>need</span> <span m='3998600'>to</span> <span
  m='3998670'>find</span> <span m='3998930'>a</span> <span m='3998970'>p</span>
  <span m='3999390'>such</span> <span m='3999610'>that</span> <span
  m='3999820'>2</span> <span m='4001730'>times</span> <span
  m='4002070'>1/2</span> <span m='4002610'>to</span> <span
  m='4002720'>the</span> <span m='4002800'>p</span> <span
  m='4003360'>plus</span> <span m='4004940'>8/9</span> <span
  m='4009050'>times</span> <span m='4009340'>3/4</span> <span
  m='4010080'>to</span> <span m='4010200'>the</span> <span m='4010260'>p</span>
  <span m='4013450'>equals</span> <span m='4013890'>1.</span> <span
  m='4015270'>I</span> <span m='4015390'>gotta</span> <span
  m='4015600'>find</span> <span m='4015880'>a p</span> <span
  m='4016160'>for</span> <span m='4016290'>which</span> <span
  m='4016470'>that's</span> <span m='4016690'>true.</span> </p><p><span
  m='4019700'>Any</span> <span m='4019870'>guesses</span> <span
  m='4020970'>what</span> <span m='4021412'>p works?</span> <span
  m='4026140'>p</span> <span m='4026360'>equals</span> <span
  m='4026600'>1</span> <span m='4027360'>not</span> <span
  m='4027540'>going</span> <span m='4027660'>to</span> <span
  m='4027730'>do</span> <span m='4027990'>it.</span> <span m='4032170'>p</span>
  <span m='4032380'>equals</span> <span m='4032710'>2?</span> <span
  m='4034330'>Let's</span> <span m='4034460'>try</span> <span
  m='4034770'>that.</span> <span m='4037220'>I'd</span> <span
  m='4037410'>have</span> <span m='4037670'>2</span> <span
  m='4038200'>times</span> <span m='4038610'>1/4</span> <span
  m='4040150'>plus</span> <span m='4041170'>8/9</span> <span
  m='4042650'>times</span> <span m='4043170'>9/16.</span> <span
  m='4046000'>That</span> <span m='4046220'>looks</span> <span
  m='4046390'>pretty</span> <span m='4046590'>good.</span> <span
  m='4047800'>I</span> <span m='4047930'>get</span> <span m='4048100'>1/2</span>
  <span m='4048710'>plus</span> <span m='4048970'>1/2</span> <span
  m='4050230'>equals</span> <span m='4050640'>1.</span> <span m='4052310'>So
  p</span> <span m='4052610'>equals</span> <span m='4052980'>2</span> <span
  m='4053150'>works.</span> </p><p><span m='4057500'>All</span> <span
  m='4057770'>right,</span> <span m='4058010'>so</span> <span
  m='4058140'>let's</span> <span m='4058620'>do</span> <span
  m='4058800'>the</span> <span m='4058950'>integral.</span> <span
  m='4062190'>tx</span> <span m='4063970'>is</span> <span
  m='4064110'>theta</span> <span m='4064750'>of</span> <span
  m='4065175'>x</span> <span m='4065600'>to</span> <span m='4065680'>the</span>
  <span m='4065770'>p</span> <span m='4066720'>plus</span> <span
  m='4067080'>x</span> <span m='4067350'>to</span> <span m='4067440'>the</span>
  <span m='4067550'>p</span> <span m='4068050'>times</span> <span
  m='4068340'>the</span> <span m='4068480'>integral.</span> <span
  m='4069640'>All right,</span> <span m='4070140'>what</span> <span
  m='4070530'>is</span> <span m='4071060'>g</span> <span m='4071370'>of</span>
  <span m='4071500'>x</span> <span m='4072410'>in</span> <span
  m='4072550'>this</span> <span m='4072740'>thing?</span> <span
  m='4075170'>x</span> <span m='4075890'>squared.</span> <span
  m='4076670'>So</span> <span m='4077860'>the</span> <span
  m='4078040'>integral</span> <span m='4078730'>is</span> <span m='4079120'>1
  to</span> <span m='4079470'>x.</span> <span m='4079725'>g</span> <span
  m='4079980'>of</span> <span m='4080070'>u</span> <span m='4080240'>is</span>
  <span m='4080370'>u</span> <span m='4080580'>squared</span> <span
  m='4081730'>divided</span> <span m='4082310'>by</span> <span
  m='4083990'>u</span> <span m='4084270'>to</span> <span m='4084370'>the</span>
  <span m='4084460'>1</span> <span m='4084890'>plus</span> <span
  m='4085320'>p.</span> <span m='4087580'>u</span> <span m='4087930'>to</span>
  <span m='4088000'>the</span> <span m='4088110'>1</span> <span
  m='4088535'>plus</span> <span m='4088960'>2</span> <span m='4089290'>is</span>
  <span m='4089430'>just</span> <span m='4089620'>u</span> <span
  m='4089790'>cubed.</span> </p><p><span m='4095860'>This</span> <span
  m='4096140'>is</span> <span m='4096330'>theta</span> <span
  m='4097490'>x</span> <span m='4097740'>squared</span> <span
  m='4098310'>plus</span> <span m='4098720'>x</span> <span
  m='4098920'>squared</span> <span m='4099520'>times,</span> <span
  m='4100290'>well,</span> <span m='4100830'>the</span> <span
  m='4101020'>integral</span> <span m='4101399'>of</span> <span
  m='4101510'>1</span> <span m='4101710'>over</span> <span m='4101890'>u</span>
  <span m='4102170'>is</span> <span m='4102290'>just</span> <span
  m='4102569'>log</span> <span m='4102760'>of</span> <span
  m='4102850'>you.</span> <span m='4109069'>And</span> <span
  m='4109300'>that's</span> <span m='4109840'>just</span> <span
  m='4110140'>log</span> <span m='4110330'>of</span> <span m='4110399'>x.</span>
  <span m='4112529'>So</span> <span m='4112700'>the</span> <span
  m='4112819'>answer</span> <span m='4113149'>is,</span> <span
  m='4113270'>x</span> <span m='4113500'>square</span> <span
  m='4113680'>ln</span> <span m='4113979'>of</span> <span m='4114080'>x.</span>
  <span m='4115390'>Done.</span> <span m='4118020'>So</span> <span
  m='4118430'>that's</span> <span m='4118840'>pretty</span> <span
  m='4119060'>good</span> <span m='4119319'>what</span> <span
  m='4119430'>these</span> <span m='4119600'>guys</span> <span
  m='4119880'>did.</span> <span m='4122000'>In</span> <span
  m='4122120'>fact,</span> <span m='4124319'>that</span> <span
  m='4124490'>is</span> <span m='4124660'>the</span> <span
  m='4124729'>correct</span> <span m='4125050'>answer.</span> <span
  m='4127120'>So</span> <span m='4127330'>really</span> <span
  m='4127590'>easy</span> <span m='4127819'>to</span> <span m='4127899'>pug
  in.</span> <span m='4130029'>Any</span> <span m='4130210'>questions</span>
  <span m='4132920'>on</span> <span m='4133109'>that?</span> <span
  m='4135930'>Yeah.</span> </p><p><span m='4137274'>AUDIENCE: [INAUDIBLE]</span>
  <span m='4139608'>or</span> <span m='4140102'>does it</span> <span
  m='4140596'>give the</span> <span m='4141090'>actual</span> <span
  m='4141584'>number?</span> </p><p><span m='4143069'>TOM LEIGHTON: It</span>
  <span m='4143240'>doesn't</span> <span m='4143560'>give</span> <span
  m='4143740'>you</span> <span m='4143850'>the</span> <span
  m='4144010'>actual</span> <span m='4144510'>number.</span> <span
  m='4145380'>It</span> <span m='4145590'>just</span> <span
  m='4146069'>gives</span> <span m='4146340'>you</span> <span
  m='4146550'>the</span> <span m='4146899'>asymptotic</span> <span
  m='4147590'>growth.</span> <span m='4148870'>All you</span> <span
  m='4149250'>know</span> <span m='4150002'>is</span> <span
  m='4150380'>that</span> <span m='4150500'>the</span> <span
  m='4150580'>limit</span> <span m='4150960'>of</span> <span
  m='4151060'>tx</span> <span m='4151649'>over</span> <span m='4151910'>x</span>
  <span m='4152050'>squared</span> <span m='4152399'>ln</span> <span
  m='4152680'>of</span> <span m='4152790'>x</span> <span m='4153609'>is</span>
  <span m='4154470'>less</span> <span m='4154840'>than</span> <span
  m='4154950'>infinity</span> <span m='4155359'>and</span> <span
  m='4155460'>bigger</span> <span m='4155649'>than</span> <span
  m='4155770'>0.</span> <span m='4156779'>So</span> <span
  m='4157040'>it's</span> <span m='4157160'>growing</span> <span
  m='4158040'>as</span> <span m='4158460'>this.</span> <span
  m='4158760'>You</span> <span m='4158830'>don't</span> <span
  m='4159080'>know</span> <span m='4159260'>if</span> <span
  m='4159359'>it's</span> <span m='4159560'>10x</span> <span
  m='4159950'>squared</span> <span m='4160300'>lnx</span> <span
  m='4160710'>or</span> <span m='4160840'>a</span> <span
  m='4160890'>million</span> <span m='4161300'>squared</span> <span
  m='4161660'>lnx.</span> <span m='4163010'>On</span> <span
  m='4163160'>the</span> <span m='4163229'>other</span> <span
  m='4163399'>hand,</span> <span m='4163810'>for</span> <span
  m='4163870'>algorithms</span> <span m='4165500'>usually</span> <span
  m='4166050'>you're</span> <span m='4166180'>forgetting</span> <span
  m='4166550'>the</span> <span m='4166630'>constant</span> <span
  m='4167040'>factors</span> <span m='4167399'>anyway</span> <span
  m='4167750'>because</span> <span m='4167899'>they</span> <span
  m='4168020'>depend</span> <span m='4168410'>on</span> <span
  m='4168540'>things</span> <span m='4168810'>to</span> <span
  m='4168899'>do</span> <span m='4169130'>with</span> <span
  m='4169270'>the</span> <span m='4169350'>CPU</span> <span
  m='4169930'>you're</span> <span m='4170069'>using</span> <span
  m='4170470'>and</span> <span m='4170569'>stuff</span> <span
  m='4170800'>like</span> <span m='4170970'>that.</span> <span
  m='4171200'>What</span> <span m='4171319'>you</span> <span
  m='4171420'>really</span> <span m='4171729'>care</span> <span
  m='4172100'>about,</span> <span m='4172430'>often,</span> <span
  m='4173300'>when</span> <span m='4173439'>you're</span> <span
  m='4173550'>studying</span> <span m='4173920'>algorithms</span> <span
  m='4174939'>is</span> <span m='4175880'>the</span> <span
  m='4176010'>asymptotic</span> <span m='4176870'>growth,</span> <span
  m='4177590'>not</span> <span m='4177819'>the</span> <span
  m='4177930'>actual</span> <span m='4178250'>value.</span> <span
  m='4179460'>Yeah?</span> </p><p><span m='4180534'>AUDIENCE: [INAUDIBLE]</span>
  <span m='4182870'>log</span> <span m='4183149'>base</span> <span
  m='4183300'>e.</span> <span m='4183870'>And</span> <span
  m='4184233'>then</span> <span m='4184596'>above</span> <span
  m='4184960'>I</span> <span m='4185042'>see</span> <span m='4185125'>you</span>
  <span m='4185207'>using</span> <span m='4185290'>log,</span> <span
  m='4185620'>which I</span> <span m='4185859'>assume</span> <span
  m='4185996'>is</span> <span m='4186134'>base</span> <span
  m='4186410'>two?</span> <span m='4186825'>Does it</span> <span
  m='4187240'>matter?</span> </p><p><span m='4188529'>TOM LEIGHTON: It</span>
  <span m='4188670'>does</span> <span m='4188729'>up there</span> <span
  m='4190160'>because</span> <span m='4190479'>I've</span> <span m='4190550'>got
  a</span> <span m='4190840'>tilde.</span> <span m='4191560'>And in</span> <span
  m='4191720'>the</span> <span m='4191859'>tilde,</span> <span
  m='4192250'>the</span> <span m='4192319'>constant</span> <span
  m='4192819'>factor</span> <span m='4193210'>matters.</span> <span
  m='4194310'>It</span> <span m='4194570'>doesn't</span> <span
  m='4194940'>matter</span> <span m='4195280'>in</span> <span
  m='4195380'>here</span> <span m='4196200'>because</span> <span
  m='4196510'>log</span> <span m='4196810'>base</span> <span
  m='4197070'>two</span> <span m='4197390'>and</span> <span
  m='4197490'>log</span> <span m='4197760'>base</span> <span
  m='4198106'>E</span> <span m='4198800'>are</span> <span
  m='4198920'>within</span> <span m='4199120'>a</span> <span
  m='4199150'>constant</span> <span m='4199570'>factor,</span> <span
  m='4200530'>namely</span> <span m='4201110'>log</span> <span m='4201430'>of
  2,</span> <span m='4201890'>ln</span> <span m='4202145'>of 2</span> <span
  m='4202400'>is</span> <span m='4202500'>the</span> <span
  m='4202570'>constant</span> <span m='4202970'>factor.</span> <span
  m='4203860'>So</span> <span m='4204930'>logs</span> <span
  m='4205660'>don't</span> <span m='4205990'>matter</span> <span
  m='4206240'>what</span> <span m='4206380'>the</span> <span
  m='4206460'>base</span> <span m='4206800'>is</span> <span
  m='4206980'>once</span> <span m='4207260'>you're</span> <span
  m='4207380'>inside</span> <span m='4207760'>a</span> <span
  m='4207810'>theta</span> <span m='4208110'>or an</span> <span
  m='4208290'>O</span> <span m='4208750'>or</span> <span m='4208860'>that</span>
  <span m='4209030'>kind</span> <span m='4209190'>of</span> <span
  m='4209260'>thing.</span> <span m='4209910'>In</span> <span
  m='4210070'>a</span> <span m='4210120'>tilde,</span> <span
  m='4210970'>they</span> <span m='4211140'>matter</span> <span
  m='4211480'>because</span> <span m='4211650'>the</span> <span
  m='4211720'>constant</span> <span m='4212130'>factor</span> <span
  m='4212480'>matters.</span> <span m='4213660'>Yeah.</span> </p><p><span
  m='4215001'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='4222790'>TOM
  LEIGHTON: Yeah.</span> <span m='4223476'>Because</span> <span
  m='4223820'>x</span> <span m='4224040'>squared</span> <span
  m='4224550'>is</span> <span m='4224650'>small</span> <span
  m='4225080'>compared</span> <span m='4225460'>to</span> <span
  m='4225520'>x</span> <span m='4225780'>squared</span> <span
  m='4226580'>ln</span> <span m='4226920'>of</span> <span m='4227010'>x</span>
  <span m='4227220'>because</span> <span m='4227380'>it's</span> <span
  m='4227530'>all</span> <span m='4228120'>by</span> <span
  m='4228280'>the</span> <span m='4228490'>theta.</span> </p><p><span
  m='4229404'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='4231690'>TOM
  LEIGHTON: No.</span> <span m='4233040'>You</span> <span
  m='4233240'>could</span> <span m='4233450'>put</span> <span
  m='4233680'>all</span> <span m='4233880'>sorts</span> <span
  m='4234130'>of</span> <span m='4234220'>other</span> <span
  m='4234400'>stuff</span> <span m='4234740'>in</span> <span
  m='4234850'>here</span> <span m='4235840'>and</span> <span
  m='4236030'>it</span> <span m='4236270'>doesn't</span> <span
  m='4236680'>matter</span> <span m='4237130'>because</span> <span
  m='4237400'>it</span> <span m='4237500'>still</span> <span
  m='4237850'>equals</span> <span m='4238290'>theta</span> <span
  m='4238610'>of</span> <span m='4238740'>x</span> <span
  m='4238920'>squared</span> <span m='4239460'>ln</span> <span
  m='4239590'>of</span> <span m='4239690'>x.</span> <span
  m='4239910'>There's</span> <span m='4240130'>no</span> <span
  m='4240630'>hidden</span> <span m='4241050'>meanings</span> <span
  m='4241570'>by</span> <span m='4241800'>having</span> <span
  m='4242080'>extra</span> <span m='4242410'>stuff</span> <span
  m='4242660'>in</span> <span m='4242750'>here.</span> <span
  m='4244380'>That's</span> <span m='4245020'>important.</span> <span
  m='4245340'>In</span> <span m='4245430'>this</span> <span
  m='4245600'>case,</span> <span m='4246350'>when</span> <span
  m='4246500'>you</span> <span m='4246590'>put</span> <span
  m='4246810'>more</span> <span m='4247020'>stuff</span> <span
  m='4247250'>into</span> <span m='4247380'>theta,</span> <span
  m='4248260'>doesn't</span> <span m='4248560'>mean</span> <span
  m='4248710'>a</span> <span m='4248750'>thing.</span> <span
  m='4251430'>Any</span> <span m='4251600'>other</span> <span
  m='4251750'>questions?</span> <span m='4252380'>Yeah.</span> </p><p><span
  m='4253364'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='4256190'>TOM
  LEIGHTON: Ah,</span> <span m='4256445'>good</span> <span
  m='4256700'>question.</span> <span m='4259480'>Well,</span> <span
  m='4260390'>let's</span> <span m='4260590'>see.</span> <span
  m='4260915'>It</span> <span m='4261240'>goes</span> <span
  m='4261550'>back</span> <span m='4261930'>to</span> <span
  m='4262780'>over</span> <span m='4263110'>here.</span> <span
  m='4273340'>See,</span> <span m='4273500'>the</span> <span
  m='4273570'>b's</span> <span m='4274060'>are</span> <span
  m='4274180'>between</span> <span m='4274540'>0</span> <span
  m='4274900'>and</span> <span m='4275030'>1.</span> <span m='4275390'>By</span>
  <span m='4275490'>making</span> <span m='4275840'>p</span> <span
  m='4276130'>big</span> <span m='4276560'>enough,</span> <span
  m='4277250'>I</span> <span m='4277370'>drive</span> <span
  m='4277670'>the</span> <span m='4277740'>value</span> <span
  m='4278080'>down.</span> <span m='4279000'>By</span> <span
  m='4279130'>making</span> <span m='4279520'>p</span> <span
  m='4280020'>be</span> <span m='4280620'>large and</span> <span
  m='4281000'>negative,</span> <span m='4281380'>I</span> <span m='4281440'>drag
  the</span> <span m='4281790'>value</span> <span m='4282270'>up.</span> <span
  m='4282460'>So</span> <span m='4282580'>there</span> <span
  m='4282670'>is</span> <span m='4282740'>some</span> <span
  m='4283050'>value</span> <span m='4283350'>of</span> <span
  m='4283450'>p.</span> <span m='4283710'>But</span> <span
  m='4284090'>that's</span> <span m='4284350'>a</span> <span
  m='4284410'>good</span> <span m='4284610'>question.</span> <span
  m='4285040'>Let's</span> <span m='4285270'>see</span> <span
  m='4285960'>what</span> <span m='4286310'>happens</span> <span
  m='4286790'>when</span> <span m='4288150'>p</span> <span m='4288470'>is</span>
  <span m='4288690'>not</span> <span m='4288900'>so</span> <span
  m='4289090'>nice.</span> <span m='4290310'>Because</span> <span
  m='4290550'>the</span> <span m='4290620'>examples</span> <span
  m='4291020'>I</span> <span m='4291100'>gave</span> <span
  m='4291320'>you,</span> <span m='4291460'>in</span> <span
  m='4291530'>one</span> <span m='4291700'>case</span> <span
  m='4291960'>p</span> <span m='4292100'>was</span> <span m='4292260'>1</span>
  <span m='4292565'>and</span> <span m='4292870'>one p</span> <span
  m='4293050'>was</span> <span m='4293210'>2,</span> <span
  m='4293840'>sort</span> <span m='4294100'>of</span> <span
  m='4294220'>nice.</span> <span m='4295220'>Let's</span> <span
  m='4295490'>look</span> <span m='4295640'>at</span> <span m='4295710'>a</span>
  <span m='4295740'>bad</span> <span m='4296370'>case</span> <span
  m='4296710'>there.</span> </p><p><span m='4303130'>Let's</span> <span
  m='4303390'>look</span> <span m='4303570'>at</span> <span
  m='4303710'>this</span> <span m='4304040'>recurrence.</span> <span
  m='4310790'>3</span> <span m='4311050'>t</span> <span m='4311680'>of</span>
  <span m='4312050'>x</span> <span m='4312330'>over</span> <span
  m='4312530'>3</span> <span m='4313730'>plus</span> <span m='4314820'>4</span>
  <span m='4315350'>t</span> <span m='4315750'>of</span> <span
  m='4316150'>x</span> <span m='4316460'>over</span> <span m='4316670'>4</span>
  <span m='4318110'>plus</span> <span m='4319090'>x</span> <span
  m='4319290'>squared.</span> <span m='4321480'>All</span> <span
  m='4321510'>right,</span> <span m='4321630'>so</span> <span
  m='4321730'>that's</span> <span m='4321960'>the</span> <span
  m='4322050'>recurrence.</span> <span m='4322540'>And</span> <span
  m='4322970'>first</span> <span m='4323200'>step</span> <span
  m='4323420'>is</span> <span m='4323500'>to</span> <span
  m='4323590'>compute</span> <span m='4323940'>p.</span> <span
  m='4324210'>And</span> <span m='4324310'>this</span> <span
  m='4324470'>time</span> <span m='4324740'>it's</span> <span
  m='4324940'>not</span> <span m='4325180'>going</span> <span
  m='4325300'>to</span> <span m='4325370'>be</span> <span
  m='4325470'>nice.</span> <span m='4327420'>So</span> <span
  m='4327530'>I</span> <span m='4327590'>need</span> <span m='4327760'>to</span>
  <span m='4327820'>find</span> <span m='4328070'>a</span> <span
  m='4328120'>p</span> <span m='4328550'>such</span> <span
  m='4328840'>that</span> <span m='4329520'>3</span> <span
  m='4329790'>times</span> <span m='4330090'>1/3</span> <span
  m='4330450'>of</span> <span m='4330520'>the</span> <span m='4330590'>p</span>
  <span m='4331040'>plus</span> <span m='4331350'>4</span> <span
  m='4331890'>times</span> <span m='4332240'>1/4</span> <span
  m='4332820'>to</span> <span m='4332910'>the</span> <span m='4333010'>p</span>
  <span m='4334670'>equals</span> <span m='4335100'>1.</span> </p><p><span
  m='4337600'>And</span> <span m='4338220'>you</span> <span
  m='4338300'>might</span> <span m='4338500'>say,</span> <span
  m='4338790'>OK,</span> <span m='4339090'>let's</span> <span
  m='4339160'>try</span> <span m='4339390'>p</span> <span
  m='4339760'>equals</span> <span m='4339940'>1.</span> <span
  m='4344500'>I</span> <span m='4344670'>get</span> <span m='4345320'>1</span>
  <span m='4346060'>plus</span> <span m='4347070'>1</span> <span
  m='4347910'>is</span> <span m='4348160'>2.</span> <span
  m='4349540'>That's</span> <span m='4349800'>too</span> <span
  m='4349980'>big.</span> <span m='4351850'>So</span> <span
  m='4352060'>which</span> <span m='4352360'>way</span> <span
  m='4352610'>do</span> <span m='4352730'>I</span> <span m='4352850'>have</span>
  <span m='4353060'>to</span> <span m='4353160'>go</span> <span
  m='4353450'>on</span> <span m='4353640'>p?</span> <span m='4354010'>Do
  I</span> <span m='4354060'>need</span> <span m='4354210'>a</span> <span
  m='4354250'>bigger</span> <span m='4354560'>p</span> <span
  m='4354810'>or</span> <span m='4354880'>a</span> <span
  m='4354940'>smaller</span> <span m='4355310'>p?</span> <span
  m='4357370'>Bigger.</span> <span m='4358230'>Because</span> <span
  m='4358420'>I</span> <span m='4358510'>got</span> <span m='4358680'>to</span>
  <span m='4359370'>get</span> <span m='4359690'>from</span> <span
  m='4359870'>2</span> <span m='4360150'>down</span> <span m='4360400'>to</span>
  <span m='4360470'>1.</span> <span m='4360800'>So</span> <span
  m='4361200'>I</span> <span m='4361440'>know</span> <span
  m='4361770'>that</span> <span m='4361970'>p</span> <span m='4363080'>is</span>
  <span m='4363310'>bigger</span> <span m='4363580'>than</span> <span
  m='4363750'>1.</span> </p><p><span m='4367190'>All</span> <span
  m='4367340'>right,</span> <span m='4367600'>so</span> <span
  m='4367770'>the</span> <span m='4367860'>next</span> <span
  m='4368290'>thing</span> <span m='4368480'>to</span> <span
  m='4368550'>try</span> <span m='4369050'>would</span> <span
  m='4369200'>be</span> <span m='4370180'>hoping</span> <span
  m='4370550'>the</span> <span m='4370620'>world</span> <span
  m='4370910'>is</span> <span m='4371020'>nice,</span> <span
  m='4371450'>p</span> <span m='4371760'>equals</span> <span
  m='4371910'>2.</span> <span m='4374440'>Maybe</span> <span
  m='4374640'>I'll</span> <span m='4374740'>do</span> <span
  m='4374870'>that</span> <span m='4375060'>over</span> <span
  m='4375230'>here.</span> <span m='4375800'>Let's</span> <span m='4375940'>try
  p</span> <span m='4376330'>equals</span> <span m='4376660'>2.</span> <span
  m='4380250'>So</span> <span m='4380390'>I</span> <span m='4380450'>get</span>
  <span m='4380610'>three</span> <span m='4381170'>times</span> <span
  m='4382340'>1/9</span> <span m='4383650'>plus</span> <span
  m='4383970'>4</span> <span m='4384520'>times</span> <span
  m='4384980'>1/16</span> <span m='4387190'>and</span> <span
  m='4387420'>that</span> <span m='4387610'>equals</span> <span
  m='4388160'>a</span> <span m='4388200'>1/3</span> <span
  m='4389370'>plus</span> <span m='4389650'>1/4.</span> <span
  m='4392200'>That's</span> <span m='4392640'>less</span> <span
  m='4392920'>than</span> <span m='4393040'>1.</span> <span
  m='4395590'>That</span> <span m='4395790'>didn't</span> <span
  m='4395970'>work.</span> <span m='4396300'>What</span> <span
  m='4396430'>do</span> <span m='4396530'>I</span> <span m='4396560'>have</span>
  <span m='4396650'>to</span> <span m='4396730'>do</span> <span
  m='4396850'>now</span> <span m='4397150'>with</span> <span
  m='4397260'>p?</span> <span m='4397440'>Is</span> <span m='4397580'>it</span>
  <span m='4397780'>bigger</span> <span m='4398060'>than</span> <span
  m='4398240'>2</span> <span m='4398480'>or</span> <span m='4398550'>less</span>
  <span m='4398770'>than</span> <span m='4398900'>2?</span> <span
  m='4400700'>Less</span> <span m='4401020'>than</span> <span
  m='4401170'>2.</span> <span m='4404940'>That's</span> <span
  m='4405130'>sort</span> <span m='4405350'>of</span> <span m='4405410'>a</span>
  <span m='4405480'>pain.</span> <span m='4406690'>P</span> <span
  m='4406930'>is</span> <span m='4407040'>between</span> <span
  m='4407430'>one</span> <span m='4407650'>and</span> <span
  m='4407750'>two,</span> <span m='4407990'>so</span> <span
  m='4408140'>it's</span> <span m='4408260'>not</span> <span
  m='4408490'>an</span> <span m='4408560'>integer.</span> </p><p><span
  m='4410270'>Now,</span> <span m='4410420'>you</span> <span
  m='4410550'>can</span> <span m='4410680'>sort</span> <span
  m='4411010'>of</span> <span m='4411110'>do</span> <span
  m='4411290'>divide</span> <span m='4411700'>and</span> <span
  m='4411810'>conquer</span> <span m='4412200'>here.</span> <span
  m='4412400'>Next</span> <span m='4412670'>I'd</span> <span
  m='4412740'>try</span> <span m='4413080'>p</span> <span m='4413360'>is</span>
  <span m='4413510'>3/2,</span> <span m='4415050'>get</span> <span
  m='4415210'>my</span> <span m='4415320'>calculator</span> <span
  m='4416010'>out</span> <span m='4416300'>and</span> <span
  m='4416420'>see</span> <span m='4416590'>which</span> <span
  m='4416780'>way</span> <span m='4416950'>it</span> <span
  m='4417030'>goes.</span> <span m='4417870'>And</span> <span
  m='4418000'>you</span> <span m='4418060'>could</span> <span
  m='4418180'>sort</span> <span m='4418420'>of</span> <span
  m='4418530'>home</span> <span m='4418890'>in</span> <span
  m='4419050'>on</span> <span m='4419220'>it.</span> <span
  m='4419980'>But</span> <span m='4420160'>there's</span> <span
  m='4420290'>something</span> <span m='4420580'>really</span> <span
  m='4421020'>nice</span> <span m='4421360'>that</span> <span
  m='4421470'>happens</span> <span m='4422800'>with</span> <span
  m='4423610'>Akra</span> <span m='4423870'>Bazzi.</span> <span
  m='4425110'>And</span> <span m='4425290'>that</span> <span
  m='4425500'>is</span> <span m='4425690'>if</span> <span m='4425800'>you</span>
  <span m='4425950'>ever</span> <span m='4426250'>conclude</span> <span
  m='4427040'>that</span> <span m='4427260'>p</span> <span m='4428450'>is</span>
  <span m='4428790'>less</span> <span m='4429370'>than</span> <span
  m='4430210'>your</span> <span m='4430380'>exponent</span> <span
  m='4430920'>here,</span> <span m='4432530'>you</span> <span
  m='4432700'>don't</span> <span m='4432950'>even</span> <span
  m='4433130'>have</span> <span m='4433330'>to</span> <span
  m='4433420'>compute</span> <span m='4433780'>it.</span> </p><p><span
  m='4435610'>Let's</span> <span m='4435810'>see</span> <span
  m='4436140'>why.</span> <span m='4436940'>Let's</span> <span m='4437030'>do
  an</span> <span m='4437140'>example.</span> <span m='4442240'>This</span>
  <span m='4442490'>will</span> <span m='4442610'>happen</span> <span
  m='4442910'>a</span> <span m='4442980'>lot.</span> <span
  m='4445870'>There's</span> <span m='4446050'>some</span> <span
  m='4446380'>p,</span> <span m='4446700'>but</span> <span
  m='4447030'>it's</span> <span m='4447200'>just</span> <span
  m='4447360'>going</span> <span m='4447480'>to</span> <span
  m='4447540'>be</span> <span m='4447600'>a</span> <span m='4447660'>pain</span>
  <span m='4448010'>to</span> <span m='4448280'>evaluate.</span> <span
  m='4448810'>But</span> <span m='4448920'>let's</span> <span
  m='4449110'>see</span> <span m='4449290'>what</span> <span
  m='4449440'>happens</span> <span m='4449830'>here.</span> <span
  m='4454340'>So</span> <span m='4454520'>I'm</span> <span
  m='4454610'>just</span> <span m='4454770'>going</span> <span
  m='4454890'>to</span> <span m='4454950'>try</span> <span m='4455120'>to</span>
  <span m='4455230'>solve</span> <span m='4455600'>it,</span> <span
  m='4455960'>write</span> <span m='4456200'>the</span> <span
  m='4456290'>solution</span> <span m='4456740'>anyway.</span> <span
  m='4457090'>t</span> <span m='4457340'>of</span> <span m='4457460'>x</span>
  <span m='4457810'>equals</span> <span m='4458270'>theta</span> <span
  m='4459820'>x</span> <span m='4460110'>to</span> <span m='4460190'>the</span>
  <span m='4460300'>p</span> <span m='4461060'>plus</span> <span
  m='4461490'>x</span> <span m='4461740'>to</span> <span m='4461830'>the</span>
  <span m='4461930'>p</span> <span m='4463200'>integral</span> <span
  m='4463690'>1</span> <span m='4463960'>to</span> <span m='4464080'>x.</span>
  <span m='4465420'>What's</span> <span m='4465680'>g</span> <span
  m='4465920'>of</span> <span m='4466040'>x?</span> <span m='4467366'>x</span>
  <span m='4467810'>squared.</span> <span m='4468400'>So</span> <span
  m='4468500'>that's u</span> <span m='4468600'>squared</span> <span
  m='4470340'>over</span> <span m='4470930'>u</span> <span m='4471800'>1</span>
  <span m='4472090'>plus</span> <span m='4472420'>p.</span> <span
  m='4473570'>And</span> <span m='4473680'>I</span> <span
  m='4473720'>still</span> <span m='4473880'>don't</span> <span
  m='4474020'>know</span> <span m='4474140'>what</span> <span
  m='4474250'>it</span> <span m='4474340'>is,</span> <span
  m='4474770'>but</span> <span m='4475140'>I'm</span> <span
  m='4475780'>going</span> <span m='4475930'>to</span> <span
  m='4476120'>give</span> <span m='4476340'>it</span> <span m='4476400'>a</span>
  <span m='4476450'>try</span> <span m='4476840'>here.</span> <span
  m='4479020'>That's</span> <span m='4479310'>theta</span> <span
  m='4480626'>x</span> <span m='4481070'>to</span> <span m='4481150'>the</span>
  <span m='4481220'>p</span> <span m='4481690'>plus</span> <span
  m='4482050'>x</span> <span m='4482330'>to</span> <span m='4482420'>the</span>
  <span m='4482530'>p.</span> </p><p><span m='4484150'>Well,</span> <span
  m='4484500'>this</span> <span m='4484710'>is</span> <span
  m='4484810'>now</span> <span m='4484980'>the</span> <span
  m='4485140'>integral</span> <span m='4485800'>of</span> <span
  m='4486740'>u</span> <span m='4487370'>to</span> <span m='4487440'>the</span>
  <span m='4487540'>1</span> <span m='4487940'>minus</span> <span
  m='4488340'>p</span> <span m='4489224'>du.</span> <span m='4491466'>And</span>
  <span m='4491920'>p</span> <span m='4492160'>is</span> <span
  m='4492330'>bigger</span> <span m='4492660'>than</span> <span
  m='4492840'>1.</span> <span m='4493125'>I</span> <span m='4493410'>know</span>
  <span m='4493630'>that.</span> <span m='4495470'>This</span> <span
  m='4495780'>is</span> <span m='4496280'>theta</span> <span
  m='4497560'>x</span> <span m='4497880'>to</span> <span m='4497970'>the</span>
  <span m='4498080'>p</span> <span m='4498650'>plus</span> <span
  m='4499130'>x</span> <span m='4499430'>to</span> <span m='4499520'>the</span>
  <span m='4499630'>p.</span> <span m='4502020'>Well,</span> <span
  m='4502190'>the</span> <span m='4502330'>integral</span> <span
  m='4502720'>here</span> <span m='4503450'>is</span> <span m='4504580'>x</span>
  <span m='4504900'>to</span> <span m='4504990'>the</span> <span
  m='4505090'>2</span> <span m='4505400'>minus</span> <span
  m='4505760'>p.</span> <span m='4507880'>Up</span> <span m='4508080'>to</span>
  <span m='4508150'>constants.</span> <span m='4508730'>I</span> <span
  m='4508790'>don't</span> <span m='4508920'>even</span> <span
  m='4509080'>care</span> <span m='4509390'>about</span> <span
  m='4509610'>dividing</span> <span m='4510020'>by</span> <span
  m='4510130'>2</span> <span m='4510310'>minus</span> <span
  m='4510610'>p,</span> <span m='4510830'>because</span> <span
  m='4511240'>I</span> <span m='4511360'>got</span> <span m='4511570'>big</span>
  <span m='4511750'>theta.</span> <span m='4513090'>Just</span> <span
  m='4513190'>put</span> <span m='4513300'>that</span> <span
  m='4513460'>p</span> <span m='4513680'>up</span> <span
  m='4513790'>here.</span> <span m='4515920'>OK</span> </p><p><span
  m='4517250'>Well,</span> <span m='4517580'>this</span> <span
  m='4517800'>equals</span> <span m='4518800'>theta</span> <span
  m='4519940'>x</span> <span m='4520270'>to</span> <span m='4520360'>the</span>
  <span m='4520470'>p</span> <span m='4521290'>plus</span> <span
  m='4523320'>cancelled</span> <span m='4523830'>there,</span> <span
  m='4524270'>x</span> <span m='4524510'>squared.</span> <span
  m='4527340'>And</span> <span m='4527470'>what's</span> <span
  m='4527640'>the</span> <span m='4527770'>answer</span> <span
  m='4528010'>going</span> <span m='4528130'>to</span> <span
  m='4528200'>be?</span> <span m='4530280'>x</span> <span
  m='4530500'>squared,</span> <span m='4530880'>because</span> <span
  m='4531140'>p</span> <span m='4531410'>is</span> <span m='4531570'>less</span>
  <span m='4531800'>than</span> <span m='4531920'>2.</span> <span
  m='4533240'>So</span> <span m='4533410'>this</span> <span
  m='4533620'>is</span> <span m='4533700'>a</span> <span m='4533760'>small
  order</span> <span m='4534250'>term.</span> <span m='4536000'>So</span> <span
  m='4536250'>I</span> <span m='4536370'>didn't</span> <span
  m='4536540'>even</span> <span m='4536730'>know</span> <span
  m='4536860'>what</span> <span m='4537010'>p</span> <span
  m='4537220'>was,</span> <span m='4537690'>just</span> <span
  m='4537950'>that</span> <span m='4538050'>it</span> <span
  m='4538120'>was</span> <span m='4538480'>less</span> <span
  m='4538750'>than</span> <span m='4538880'>two.</span> <span
  m='4540020'>And</span> <span m='4540180'>I</span> <span m='4540220'>got</span>
  <span m='4540400'>the</span> <span m='4540540'>answer.</span> <span
  m='4541530'>And</span> <span m='4541700'>what</span> <span
  m='4541810'>do</span> <span m='4541870'>you</span> <span
  m='4541930'>know?</span> <span m='4542110'>The</span> <span
  m='4542280'>answer</span> <span m='4543430'>was</span> <span
  m='4543610'>just</span> <span m='4543840'>this</span> <span
  m='4544000'>thing.</span> <span m='4545440'>That's</span> <span
  m='4545690'>sort</span> <span m='4545910'>of</span> <span
  m='4546550'>nice</span> <span m='4546930'>and</span> <span
  m='4547030'>simple.</span> </p><p><span m='4548070'>And</span> <span
  m='4548200'>in</span> <span m='4548290'>fact,</span> <span
  m='4548800'>that's</span> <span m='4549080'>a</span> <span
  m='4549120'>theorem.</span> <span m='4551750'>Which</span> <span
  m='4552050'>will</span> <span m='4552150'>state,</span> <span
  m='4553150'>in</span> <span m='4553650'>general,</span> <span
  m='4564330'>if</span> <span m='4565380'>g</span> <span m='4565710'>of</span>
  <span m='4565830'>x</span> <span m='4567140'>equals</span> <span
  m='4568210'>theta</span> <span m='4569770'>x</span> <span
  m='4570080'>to</span> <span m='4570190'>the</span> <span m='4570310'>t,</span>
  <span m='4571900'>for</span> <span m='4572040'>some</span> <span
  m='4572270'>t</span> <span m='4572500'>bigger</span> <span
  m='4572730'>and</span> <span m='4572800'>equal</span> <span
  m='4572980'>to</span> <span m='4573060'>0.</span> <span m='4576320'>And</span>
  <span m='4576630'>when</span> <span m='4576740'>you</span> <span
  m='4576830'>plug</span> <span m='4577250'>that</span> <span
  m='4577450'>value</span> <span m='4577900'>in</span> <span
  m='4578360'>and</span> <span m='4578600'>take</span> <span
  m='4578840'>your</span> <span m='4578970'>sum.</span> <span
  m='4581710'>Trying</span> <span m='4581890'>to</span> <span
  m='4581960'>compute</span> <span m='4582270'>the</span> <span
  m='4582340'>p</span> <span m='4582550'>value.</span> <span
  m='4582860'>So</span> <span m='4582990'>I</span> <span m='4583030'>take</span>
  <span m='4583310'>ai</span> <span m='4584230'>times</span> <span
  m='4584530'>bi</span> <span m='4585160'>to</span> <span m='4585230'>the</span>
  <span m='4585310'>t.</span> </p><p><span m='4586320'>And</span> <span
  m='4586460'>that</span> <span m='4586620'>comes</span> <span
  m='4586830'>out</span> <span m='4586990'>to</span> <span m='4587060'>be</span>
  <span m='4587150'>less</span> <span m='4587450'>than</span> <span
  m='4587580'>1</span> <span m='4588500'>like</span> <span m='4588700'>it</span>
  <span m='4588780'>did</span> <span m='4588970'>here</span> <span
  m='4589550'>when</span> <span m='4589700'>I</span> <span
  m='4589750'>plugged</span> <span m='4590080'>in</span> <span
  m='4592300'>p</span> <span m='4592650'>equals</span> <span
  m='4592840'>2</span> <span m='4594280'>and</span> <span m='4594500'>I</span>
  <span m='4594560'>computed</span> <span m='4594845'>it and</span> <span
  m='4595130'>it</span> <span m='4595190'>was</span> <span
  m='4595360'>less</span> <span m='4595590'>than</span> <span
  m='4595720'>1.</span> <span m='4596970'>But</span> <span m='4597100'>if</span>
  <span m='4597180'>that</span> <span m='4597390'>happens</span> <span
  m='4597770'>in</span> <span m='4597870'>general,</span> <span
  m='4600660'>then</span> <span m='4602370'>the</span> <span
  m='4602520'>answer</span> <span m='4602940'>is</span> <span
  m='4606500'>theta</span> <span m='4607350'>g</span> <span
  m='4607540'>of</span> <span m='4607630'>x.</span> <span
  m='4610350'>Plain</span> <span m='4610550'>and</span> <span
  m='4610650'>simple.</span> <span m='4611900'>It</span> <span
  m='4612040'>just</span> <span m='4612360'>turns</span> <span
  m='4612610'>out</span> <span m='4612820'>to</span> <span m='4612920'>be</span>
  <span m='4613180'>the</span> <span m='4615030'>g</span> <span
  m='4615200'>of</span> <span m='4615300'>x term</span> <span
  m='4615670'>up</span> <span m='4615760'>to</span> <span
  m='4615840'>constant</span> <span m='4616200'>factors.</span> </p><p><span
  m='4618460'>So</span> <span m='4618570'>you</span> <span
  m='4618630'>don't</span> <span m='4618780'>even</span> <span
  m='4618920'>have</span> <span m='4619020'>to</span> <span
  m='4619090'>compute</span> <span m='4619430'>it.</span> <span
  m='4620430'>Just</span> <span m='4620710'>do</span> <span
  m='4620810'>that</span> <span m='4621070'>check</span> <span
  m='4621540'>on</span> <span m='4621680'>the</span> <span
  m='4621750'>power</span> <span m='4622520'>here</span> <span
  m='4622930'>to</span> <span m='4623010'>see</span> <span m='4623280'>is</span>
  <span m='4623430'>it</span> <span m='4623860'>smaller</span> <span
  m='4624310'>than</span> <span m='4624430'>that.</span> <span
  m='4625990'>I</span> <span m='4626130'>won't</span> <span
  m='4626360'>prove</span> <span m='4626640'>that</span> <span
  m='4626830'>there.</span> <span m='4627010'>It's</span> <span
  m='4627270'>actually</span> <span m='4627540'>not</span> <span
  m='4627720'>hard</span> <span m='4627890'>to</span> <span
  m='4627950'>do.</span> <span m='4628310'>The</span> <span
  m='4628380'>proof</span> <span m='4628720'>is</span> <span
  m='4629230'>pretty</span> <span m='4629430'>much</span> <span
  m='4629620'>what</span> <span m='4629740'>I</span> <span
  m='4629820'>did</span> <span m='4630130'>with</span> <span
  m='4630240'>this</span> <span m='4630420'>example,</span> <span
  m='4630980'>so</span> <span m='4631140'>it's</span> <span m='4631611'>not too
  hard.</span> <span m='4635820'>OK,</span> <span m='4636340'>any</span> <span
  m='4636490'>questions?</span> </p><p><span m='4639550'>I</span> <span
  m='4639710'>want</span> <span m='4639850'>to</span> <span
  m='4639910'>show</span> <span m='4640070'>you</span> <span
  m='4640160'>one</span> <span m='4640470'>more</span> <span
  m='4640660'>thing,</span> <span m='4641200'>but</span> <span
  m='4641390'>just</span> <span m='4641580'>make</span> <span
  m='4641700'>sure</span> <span m='4641840'>that's</span> <span
  m='4642390'>OK.</span> <span m='4644060'>And</span> <span
  m='4644170'>this</span> <span m='4644350'>is</span> <span
  m='4645450'>something</span> <span m='4645840'>never</span> <span
  m='4646150'>to</span> <span m='4646270'>do</span> <span
  m='4648940'>with</span> <span m='4649160'>an</span> <span
  m='4649460'>asymptotic</span> <span m='4649970'>notation,</span> <span
  m='4650530'>like</span> <span m='4650700'>we</span> <span
  m='4650770'>talked</span> <span m='4651080'>about</span> <span
  m='4651270'>last</span> <span m='4651520'>time.</span> <span
  m='4653860'>When</span> <span m='4653990'>you're</span> <span
  m='4654090'>using</span> <span m='4654470'>Akra</span> <span
  m='4654620'>Bazzi</span> <span m='4655030'>and</span> <span
  m='4655380'>when</span> <span m='4655510'>you're</span> <span
  m='4655670'>doing</span> <span m='4656260'>occurrences</span> <span
  m='4656840'>with</span> <span m='4656980'>algorithm,</span> <span
  m='4657550'>you</span> <span m='4657650'>always</span> <span
  m='4658170'>are</span> <span m='4658230'>using</span> <span
  m='4659110'>asymptotic</span> <span m='4659760'>notation.</span> <span
  m='4661630'>Your</span> <span m='4661850'>answer</span> <span
  m='4662280'>is</span> <span m='4662820'>theta of</span> <span
  m='4663240'>something.</span> </p><p><span m='4664490'>And</span> <span
  m='4664700'>in</span> <span m='4664790'>fact,</span> <span
  m='4665320'>what</span> <span m='4665330'>will</span> <span
  m='4665430'>start</span> <span m='4665740'>happening</span> <span
  m='4666240'>is</span> <span m='4666360'>you'll</span> <span
  m='4666450'>do</span> <span m='4666630'>this</span> <span
  m='4666800'>stuff</span> <span m='4668580'>because</span> <span
  m='4669290'>the</span> <span m='4669390'>constant</span> <span
  m='4669860'>factors</span> <span m='4670910'>don't</span> <span
  m='4671580'>matter.</span> <span m='4672470'>Because</span> <span
  m='4672630'>you're</span> <span m='4672720'>wiping</span> <span
  m='4673040'>them</span> <span m='4673160'>out</span> <span m='4673280'>in
  the</span> <span m='4673420'>theta</span> <span m='4673630'>notation,</span>
  <span m='4675320'>what</span> <span m='4675510'>you'll</span> <span
  m='4675640'>see</span> <span m='4675910'>is</span> <span
  m='4676070'>things</span> <span m='4676350'>like</span> <span
  m='4676550'>this.</span> <span m='4676860'>Your</span> <span
  m='4676990'>recurrence</span> <span m='4677470'>will</span> <span
  m='4677560'>be</span> <span m='4677640'>set</span> <span m='4677940'>up</span>
  <span m='4678090'>to</span> <span m='4678180'>be</span> <span
  m='4678590'>t</span> <span m='4678970'>of</span> <span m='4679070'>n</span>
  <span m='4679500'>is</span> <span m='4679680'>2</span> <span m='4680620'>t
  of</span> <span m='4680730'>n</span> <span m='4680990'>over</span> <span
  m='4681200'>2</span> <span m='4682300'>plus</span> <span m='4682610'>o</span>
  <span m='4682740'>of n</span> <span m='4684310'>or</span> <span
  m='4684580'>plus</span> <span m='4684910'>theta</span> <span m='4685360'>of
  n.</span> <span m='4687230'>And</span> <span m='4687420'>then</span> <span
  m='4687720'>you'll</span> <span m='4687890'>conclude</span> <span
  m='4689470'>that</span> <span m='4689850'>t of</span> <span
  m='4690310'>n</span> <span m='4691130'>is</span> <span
  m='4691530'>theta</span> <span m='4692080'>of n</span> <span
  m='4692270'>log</span> <span m='4692500'>n</span> <span
  m='4694390'>using</span> <span m='4694760'>Akra</span> <span
  m='4694920'>Bazzi</span> <span m='4695550'>or</span> <span
  m='4695690'>whatever</span> <span m='4695990'>method</span> <span
  m='4696320'>you</span> <span m='4696430'>want.</span> <span
  m='4698880'>Because</span> <span m='4699230'>it</span> <span
  m='4699310'>doesn't</span> <span m='4699570'>really</span> <span
  m='4699790'>matter</span> <span m='4700150'>what</span> <span
  m='4700310'>the</span> <span m='4700380'>constant</span> <span
  m='4700860'>is</span> <span m='4701050'>on</span> <span m='4701230'>g</span>
  <span m='4702750'>because</span> <span m='4704000'>the</span> <span
  m='4704080'>constants</span> <span m='4704540'>disappear.</span> <span
  m='4706330'>Doesn't</span> <span m='4706600'>matter.</span> <span
  m='4707410'>And</span> <span m='4707560'>so</span> <span
  m='4707680'>people</span> <span m='4708000'>stop</span> <span
  m='4708340'>worrying</span> <span m='4708750'>about</span> <span
  m='4709050'>it</span> <span m='4709170'>early</span> <span
  m='4709510'>on.</span> </p><p><span m='4711650'>All</span> <span
  m='4711820'>right,</span> <span m='4711980'>now</span> <span
  m='4713250'>here's</span> <span m='4713680'>the</span> <span
  m='4713950'>bad</span> <span m='4714370'>example.</span> <span m='4719394'>Let
  me</span> <span m='4719850'>show</span> <span m='4720150'>you</span> <span
  m='4720420'>a</span> <span m='4720500'>false</span> <span
  m='4721460'>proof</span> <span m='4721880'>like</span> <span
  m='4722080'>last</span> <span m='4722360'>time.</span> <span
  m='4724230'>And</span> <span m='4724410'>this</span> <span
  m='4724570'>time</span> <span m='4724750'>I</span> <span
  m='4724810'>think</span> <span m='4725070'>it'll</span> <span
  m='4725190'>be</span> <span m='4725820'>pretty</span> <span
  m='4726150'>easy</span> <span m='4726390'>to</span> <span
  m='4726460'>spot</span> <span m='4726901'>the flaw.</span> <span
  m='4741960'>Theorem</span> <span m='4742710'>not.</span> <span
  m='4748630'>If</span> <span m='4749545'>t of</span> <span m='4749890'>n</span>
  <span m='4751280'>equals</span> <span m='4751700'>2</span> <span m='4752093'>t
  of</span> <span m='4753110'>n</span> <span m='4753350'>over</span> <span
  m='4753600'>2</span> <span m='4754660'>plus</span> <span m='4755030'>n</span>
  <span m='4755180'>minus</span> <span m='4755510'>1,</span> <span
  m='4756050'>this</span> <span m='4756280'>is</span> <span
  m='4756390'>the</span> <span m='4756470'>recurrence</span> <span
  m='4757060'>we</span> <span m='4757180'>had</span> <span
  m='4757390'>for</span> <span m='4757500'>merge</span> <span
  m='4757780'>sort,</span> <span m='4759060'>and</span> <span
  m='4759480'>t</span> <span m='4759700'>of</span> <span m='4759810'>1</span>
  <span m='4760590'>equals</span> <span m='4760990'>0,</span> <span
  m='4762980'>then</span> <span m='4763630'>I'm</span> <span
  m='4763720'>going</span> <span m='4763840'>to</span> <span
  m='4763910'>prove</span> <span m='4766650'>that</span> <span
  m='4766950'>t</span> <span m='4767180'>of</span> <span m='4767300'>n</span>
  <span m='4768370'>is</span> <span m='4768560'>o</span> <span
  m='4768700'>event.</span> </p><p><span m='4772360'>Now,</span> <span
  m='4772510'>that</span> <span m='4772780'>can't</span> <span
  m='4773190'>be</span> <span m='4773340'>right</span> <span
  m='4775840'>because</span> <span m='4776070'>we've</span> <span
  m='4776750'>proved</span> <span m='4777190'>it's</span> <span
  m='4777770'>theta</span> <span m='4778150'>then</span> <span m='4778300'>log
  n,</span> <span m='4778720'>tilde</span> <span m='4779190'>then</span> <span
  m='4779420'>log</span> <span m='4779710'>n.</span> <span
  m='4780050'>And</span> <span m='4780170'>that</span> <span
  m='4780330'>is</span> <span m='4780480'>not</span> <span m='4780900'>o
  of</span> <span m='4781100'>n,</span> <span m='4781390'>right?</span> <span
  m='4782340'>n</span> <span m='4782510'>log n</span> <span
  m='4782920'>grows</span> <span m='4783190'>faster</span> <span
  m='4783750'>than</span> <span m='4783900'>n.</span> <span
  m='4786240'>But</span> <span m='4786360'>let's</span> <span
  m='4786530'>see</span> <span m='4786650'>the</span> <span
  m='4786730'>proof.</span> <span m='4792920'>By</span> <span
  m='4793070'>strong</span> <span m='4793440'>induction.</span> <span
  m='4800720'>The</span> <span m='4800850'>induction</span> <span
  m='4801330'>hypothesis</span> <span m='4804200'>is</span> <span
  m='4804520'>going</span> <span m='4804800'>to</span> <span
  m='4804920'>be</span> <span m='4806260'>what</span> <span
  m='4806390'>we're</span> <span m='4806470'>trying</span> <span
  m='4806720'>to</span> <span m='4806790'>prove.</span> <span
  m='4816770'>Base</span> <span m='4817070'>case.</span> <span
  m='4819830'>n</span> <span m='4820020'>equals</span> <span
  m='4820330'>1.</span> <span m='4821600'>t</span> <span m='4821850'>of</span>
  <span m='4821950'>1</span> <span m='4822420'>is</span> <span
  m='4822700'>0.</span> <span m='4823810'>0</span> <span m='4824340'>is</span>
  <span m='4824620'>surely</span> <span m='4825096'>o</span> <span
  m='4825334'>of</span> <span m='4825572'>1.</span> <span m='4829360'>The</span>
  <span m='4829800'>induction</span> <span m='4830430'>step.</span> <span
  m='4836370'>We're</span> <span m='4836510'>going</span> <span
  m='4836640'>to</span> <span m='4836720'>assume</span> <span
  m='4837640'>p1,</span> <span m='4838160'>p2,</span> <span
  m='4838660'>p3</span> <span m='4839740'>up</span> <span m='4839960'>to</span>
  <span m='4840060'>pn</span> <span m='4840380'>minus</span> <span
  m='4840670'>1</span> <span m='4840870'>to</span> <span
  m='4840950'>prove</span> <span m='4841260'>pn.</span> </p><p><span
  m='4855190'>And</span> <span m='4855320'>let's</span> <span
  m='4855560'>look</span> <span m='4855730'>at</span> <span m='4856220'>p</span>
  <span m='4856600'>of n.</span> <span m='4857190'>So I</span> <span
  m='4857260'>look</span> <span m='4857430'>at</span> <span
  m='4857530'>tn</span> <span m='4859360'>is</span> <span m='4859710'>2</span>
  <span m='4860210'>t</span> <span m='4860450'>of</span> <span
  m='4860560'>n</span> <span m='4860690'>over</span> <span m='4860880'>2</span>
  <span m='4862420'>plus</span> <span m='4862830'>n</span> <span
  m='4863060'>minus</span> <span m='4863430'>1.</span> <span
  m='4864820'>Induction</span> <span m='4865370'>hypothesis</span> <span
  m='4866200'>on</span> <span m='4866320'>n over</span> <span
  m='4866600'>2</span> <span m='4866940'>says</span> <span
  m='4867230'>this</span> <span m='4867430'>is</span> <span m='4867550'>2</span>
  <span m='4867860'>times</span> <span m='4868280'>o</span> <span
  m='4868600'>of</span> <span m='4868800'>n</span> <span m='4868950'>over</span>
  <span m='4869130'>2</span> <span m='4870600'>plus</span> <span
  m='4870930'>n</span> <span m='4871070'>minus</span> <span
  m='4871400'>1.</span> <span m='4872920'>Twice</span> <span
  m='4873790'>o</span> <span m='4874030'>of</span> <span m='4874090'>n</span>
  <span m='4874800'>over</span> <span m='4875040'>2</span> <span
  m='4875280'>is</span> <span m='4875420'>o</span> <span m='4875570'>of n</span>
  <span m='4875990'>plus</span> <span m='4876400'>n</span> <span
  m='4876650'>is</span> <span m='4876810'>o of</span> <span
  m='4877000'>n.</span> <span m='4878000'>This</span> <span
  m='4878210'>is</span> <span m='4878310'>o</span> <span m='4878480'>of</span>
  <span m='4878510'>n.</span> <span m='4879780'>And</span> <span
  m='4880030'>I'm</span> <span m='4880180'>done.</span> <span
  m='4882520'>I</span> <span m='4882690'>just</span> <span
  m='4883000'>proved</span> <span m='4884370'>that</span> <span m='4884510'>t
  of</span> <span m='4884760'>n is</span> <span m='4885025'>o of</span> <span
  m='4885290'>n.</span> </p><p><span m='4888890'>What's</span> <span
  m='4889670'>the</span> <span m='4889780'>bad</span> <span
  m='4890070'>step?</span> <span m='4890420'>What's</span> <span
  m='4890590'>the</span> <span m='4890680'>bug?</span> <span
  m='4893710'>See</span> <span m='4893920'>the</span> <span
  m='4893990'>bug?</span> <span m='4895150'>What</span> <span
  m='4895300'>is</span> <span m='4895420'>it?</span> </p><p><span
  m='4896626'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='4897430'>TOM
  LEIGHTON: Induction</span> <span m='4897980'>hypothesis.</span> <span
  m='4898890'>What's</span> <span m='4899160'>wrong</span> <span
  m='4899450'>with</span> <span m='4899570'>that?</span> </p><p><span
  m='4900958'>AUDIENCE: [INAUDIBLE].</span> </p><p><span m='4906450'>TOM
  LEIGHTON: Right.</span> <span m='4906850'>The</span> <span
  m='4906980'>end</span> <span m='4907270'>from</span> <span
  m='4907390'>the</span> <span m='4907460'>predicate</span> <span
  m='4908040'>cannot</span> <span m='4908510'>be</span> <span
  m='4908600'>in</span> <span m='4908680'>the</span> <span m='4908790'>o
  of</span> <span m='4909010'>n.</span> <span m='4910260'>Because</span> <span
  m='4910850'>remember,</span> <span m='4911600'>o of</span> <span
  m='4911920'>n</span> <span m='4912260'>means,</span> <span
  m='4913130'>this</span> <span m='4913400'>statement</span> <span
  m='4913910'>here</span> <span m='4914280'>by</span> <span
  m='4914460'>itself</span> <span m='4914930'>means</span> <span
  m='4915310'>the</span> <span m='4915390'>limit</span> <span
  m='4916600'>as</span> <span m='4916820'>n</span> <span m='4917020'>goes</span>
  <span m='4917290'>to</span> <span m='4917400'>infinity</span> <span
  m='4918480'>of</span> <span m='4918750'>t</span> <span m='4919010'>of</span>
  <span m='4919130'>n</span> <span m='4920110'>over</span> <span
  m='4920520'>n</span> <span m='4921240'>is</span> <span m='4921450'>less</span>
  <span m='4921690'>than</span> <span m='4921790'>infinity.</span> <span
  m='4924160'>But</span> <span m='4925520'>this</span> <span
  m='4925680'>makes</span> <span m='4925920'>no</span> <span
  m='4926190'>sense</span> <span m='4927550'>if</span> <span
  m='4927680'>I</span> <span m='4927780'>specified</span> <span
  m='4928370'>n</span> <span m='4928480'>in</span> <span m='4928550'>a</span>
  <span m='4928620'>predicate.</span> </p><p><span m='4930700'>So</span> <span
  m='4930800'>what's</span> <span m='4931020'>the</span> <span
  m='4931130'>rule?</span> <span m='4931710'>Same</span> <span m='4932040'>rule
  as</span> <span m='4932360'>last</span> <span m='4932640'>time.</span> <span
  m='4933290'>Same</span> <span m='4933680'>bug.</span> <span
  m='4934170'>What's</span> <span m='4934520'>the</span> <span
  m='4934630'>rule?</span> <span m='4938360'>Never</span> <span
  m='4939060'>do</span> <span m='4939300'>asymptotic</span> <span
  m='4939990'>notation</span> <span m='4940270'>in</span> <span
  m='4940550'>induction</span> <span m='4941000'>hypothesis.</span> <span
  m='4941730'>Never</span> <span m='4942340'>mix</span> <span
  m='4942840'>big</span> <span m='4943120'>o</span> <span m='4943470'>and</span>
  <span m='4943580'>a</span> <span m='4943630'>predicate.</span> <span
  m='4944430'>Never,</span> <span m='4944870'>ever.</span> <span
  m='4945930'>It</span> <span m='4946090'>looks</span> <span
  m='4946470'>so</span> <span m='4946890'>nice</span> <span
  m='4947280'>to</span> <span m='4947390'>do,</span> <span
  m='4948700'>but</span> <span m='4948900'>it</span> <span m='4948970'>is</span>
  <span m='4949420'>so</span> <span m='4949740'>wrong.</span> <span
  m='4950400'>It</span> <span m='4950510'>just</span> <span
  m='4950800'>makes</span> <span m='4951120'>nonsense.</span> </p><p><span
  m='4952910'>All</span> <span m='4953200'>right,</span> <span
  m='4953890'>very</span> <span m='4954180'>good.</span> <span
  m='4954430'>So</span> <span m='4955200'>remember</span> <span
  m='4955860'>ice</span> <span m='4956090'>cream</span> <span
  m='4956450'>tonight,</span> <span m='4957410'>recitation</span> <span
  m='4958220'>optional</span> <span m='4958960'>tomorrow.</span> <span
  m='4959650'>But</span> <span m='4959910'>study</span> <span
  m='4960250'>session</span> <span m='4960640'>is</span> <span
  m='4960750'>there.</span> </p>
embedded_media:
  - uid: ead8e99696d73cfbb04303db278b44a8
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: Kqf0uO0oV6s
  - uid: e27730fa2de811a77ab7ab42d3fe7724
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/Kqf0uO0oV6s/default.jpg'
  - uid: 7d2dbdbec0c7b727671210eecacdb567
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-14-divide-conquer/id503873536?i=110644962
  - uid: 0eb323b99fae0580ba8d70a0104a4eb9
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MIT6.042JF10/MIT6_042JF10_lec14_300k.mp4'
  - uid: 5f5ea7726e1082da99abcdf4f07c0cee
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: Kqf0uO0oV6s
  - uid: bf4a09c73e07f514cc2135413dbeb797
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Kqf0uO0oV6s.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-042j-mathematics-for-computer-science-fall-2010/bf4a09c73e07f514cc2135413dbeb797_Kqf0uO0oV6s.srt
  - uid: fa1c71923e2802c8415a16fadb541bb0
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Kqf0uO0oV6s.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-042j-mathematics-for-computer-science-fall-2010/fa1c71923e2802c8415a16fadb541bb0_Kqf0uO0oV6s.pdf
  - uid: 796d65a6d1ef2fa3932f061f2171ab03
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 74dab3432978ca9c880dd0fb9b4e9335
    parent_uid: 098ba0041cbb6df383f0decb5057952b
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: 6-042j-mathematics-for-computer-science-fall-2010
type: course
layout: video
---