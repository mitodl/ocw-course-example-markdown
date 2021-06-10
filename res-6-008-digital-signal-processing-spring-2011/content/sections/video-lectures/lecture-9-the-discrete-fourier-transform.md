---
order_index: null
title: 'Lecture 9: The Discrete Fourier Transform'
template_type: Tabbed
uid: d4534d465dd769973625f4b9450efcf6
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-9-the-discrete-fourier-transform
short_url: lecture-9-the-discrete-fourier-transform
inline_embed_id: '40493288lecture9:thediscretefouriertransform72839193'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Sampling and aliasing with a sinusoidal
  signal, sinusoidal response of a digital filter, dependence of frequency
  response on sampling period, periodic nature of the frequency response of a
  digital filter.</p> <p><strong>Instructor:</strong> Prof. Alan V.
  Oppenheim</p>
related_resources_text: >-
  <p>The Discrete Fourier Transform (<a
  href="./resolveuid/bc8229ecb3a6d43e355279a65ee917b0">PDF</a>)</p>
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
  <span m='15550'>visit</span> <span m='15780'>MITOpenCourseWare</span> <span
  m='16920'>at</span> <span m='17280'>ocw.mit.edu.</span> </p><p><span
  m='23080'>[MUSIC PLAYING]</span> </p><p></p><p><span m='55790'>ALAN
  OPPENHEIM:</span> <span m='55955'>Hi.</span> <span m='57410'>So it</span>
  <span m='57620'>turns</span> <span m='57920'>out</span> <span
  m='58160'>that</span> <span m='58490'>you</span> <span m='58640'>guys</span>
  <span m='58940'>missed</span> <span m='59180'>out</span> <span
  m='59420'>on</span> <span m='60020'>some</span> <span m='60230'>of</span>
  <span m='60290'>the</span> <span m='60380'>best</span> <span
  m='60590'>parts</span> <span m='61010'>of</span> <span m='61340'>these</span>
  <span m='61520'>lectures,</span> <span m='62100'>which</span> <span
  m='62210'>is</span> <span m='62300'>all</span> <span m='62450'>the</span>
  <span m='62540'>kibitzing</span> <span m='63020'>that</span> <span
  m='63140'>goes</span> <span m='63410'>on</span> <span m='63590'>in</span>
  <span m='63710'>back</span> <span m='64010'>of the</span> <span
  m='64140'>cameras</span> <span m='64940'>just</span> <span
  m='65120'>before</span> <span m='65420'>they</span> <span m='65570'>get</span>
  <span m='65720'>started.</span> <span m='68090'>Well,</span> <span
  m='69370'>in</span> <span m='69800'>the</span> <span m='69860'>last</span>
  <span m='70310'>lecture,</span> <span m='71900'>we</span> <span
  m='72170'>stressed</span> <span m='72590'>the</span> <span
  m='72740'>equivalence</span> <span m='73490'>of</span> <span
  m='73760'>finite</span> <span m='74210'>length</span> <span
  m='74750'>and</span> <span m='74990'>periodic</span> <span
  m='75560'>sequences.</span> <span m='77060'>In</span> <span
  m='77180'>particular,</span> <span m='78230'>as</span> <span
  m='78680'>hopefully</span> <span m='79490'>you</span> <span
  m='79620'>recall,</span> <span m='82790'>we</span> <span
  m='83540'>talked</span> <span m='83900'>about</span> <span m='84560'>a</span>
  <span m='85160'>finite</span> <span m='85610'>length</span> <span
  m='85850'>sequence,</span> <span m='86522'>x of</span> <span
  m='86860'>n,</span> <span m='88400'>which</span> <span m='88910'>was of</span>
  <span m='89300'>length</span> <span m='89930'>capital</span> <span
  m='90440'>N.</span> <span m='90980'>In</span> <span m='91100'>other</span>
  <span m='91310'>words,</span> <span m='92040'>it's</span> <span
  m='92150'>equal</span> <span m='92450'>to</span> <span m='92600'>0,</span>
  <span m='93710'>except</span> <span m='94250'>in</span> <span
  m='94370'>the</span> <span m='94460'>range</span> <span m='95180'>0</span>
  <span m='95980'>to</span> <span m='96110'>capital</span> <span
  m='96560'>N</span> <span m='96710'>minus</span> <span m='97100'>1.</span>
  </p><p><span m='99380'>We</span> <span m='99650'>stressed</span> <span
  m='100130'>also</span> <span m='100850'>the</span> <span
  m='100940'>fact</span> <span m='101570'>that</span> <span m='102200'>if</span>
  <span m='102500'>the</span> <span m='102620'>sequence</span> <span
  m='103340'>is</span> <span m='103490'>considered</span> <span
  m='104240'>a</span> <span m='104330'>finite</span> <span
  m='104780'>length</span> <span m='105170'>capital</span> <span
  m='105680'>N,</span> <span m='106826'>then</span> <span m='107210'>it</span>
  <span m='107360'>can</span> <span m='107510'>also</span> <span
  m='108080'>be</span> <span m='108230'>considered</span> <span
  m='108890'>of</span> <span m='109070'>longer</span> <span
  m='109760'>length</span> <span m='110070'>than</span> <span
  m='110220'>that,</span> <span m='110990'>or</span> <span
  m='111500'>equivalently</span> <span m='112190'>the</span> <span
  m='112310'>statement</span> <span m='112820'>that</span> <span
  m='112970'>it's</span> <span m='113090'>a</span> <span
  m='113180'>finite</span> <span m='113660'>length</span> <span
  m='114530'>doesn't</span> <span m='114860'>imply</span> <span
  m='115610'>that</span> <span m='115790'>some</span> <span m='116060'>of</span>
  <span m='116180'>the</span> <span m='116270'>values</span> <span
  m='116930'>in</span> <span m='117050'>the</span> <span
  m='117170'>interval</span> <span m='117560'>0</span> <span
  m='117950'>to</span> <span m='118070'>N</span> <span m='118220'>minus</span>
  <span m='118610'>1</span> <span m='119180'>can't</span> <span
  m='119510'>also</span> <span m='119810'>be</span> <span m='119960'>0.</span>
  </p><p><span m='122720'>In</span> <span m='122870'>relating</span> <span
  m='123380'>a</span> <span m='123440'>finite</span> <span
  m='123860'>length</span> <span m='124070'>sequence</span> <span
  m='124910'>to</span> <span m='125030'>a</span> <span
  m='125090'>periodic</span> <span m='125720'>sequence,</span> <span
  m='127130'>we</span> <span m='127580'>generated</span> <span
  m='128240'>a</span> <span m='128300'>periodic</span> <span
  m='128930'>sequence,</span> <span m='129740'>x</span> <span
  m='130009'>tilde</span> <span m='130400'>of</span> <span m='130550'>n,</span>
  <span m='131780'>by</span> <span m='131960'>simply</span> <span
  m='132440'>repeating</span> <span m='133310'>the</span> <span
  m='133400'>finite</span> <span m='133880'>length</span> <span
  m='134090'>sequence</span> <span m='135320'>over</span> <span
  m='135680'>and</span> <span m='135770'>over</span> <span
  m='136130'>again</span> <span m='137120'>with</span> <span m='137270'>a</span>
  <span m='137330'>period</span> <span m='138080'>of</span> <span
  m='138230'>capital</span> <span m='138770'>N.</span> <span
  m='139010'>That</span> <span m='139190'>is</span> <span m='139790'>x</span>
  <span m='140060'>of</span> <span m='140180'>n</span> <span
  m='140840'>was</span> <span m='141650'>added</span> <span m='141920'>to</span>
  <span m='142130'>itself,</span> <span m='142760'>shifted</span> <span
  m='143240'>by</span> <span m='143420'>capital</span> <span
  m='143960'>N,</span> <span m='144500'>shifted</span> <span
  m='144890'>by</span> <span m='145070'>2</span> <span m='145280'>capital</span>
  <span m='145550'>N,</span> <span m='146030'>shifted</span> <span
  m='146420'>by</span> <span m='146600'>3</span> <span m='146840'>capital</span>
  <span m='147380'>N.</span> <span m='148190'>And</span> <span
  m='148280'>because</span> <span m='148640'>of</span> <span
  m='148730'>the</span> <span m='148850'>fact</span> <span
  m='149210'>that</span> <span m='149330'>it's</span> <span m='149480'>a</span>
  <span m='149570'>finite</span> <span m='150050'>length,</span> <span
  m='151960'>there</span> <span m='152290'>is</span> <span m='152500'>no</span>
  <span m='152680'>interference</span> <span m='153370'>between</span> <span
  m='153880'>each</span> <span m='154120'>of</span> <span
  m='154240'>these</span> <span m='154540'>individual</span> <span
  m='155170'>replicas</span> <span m='155860'>of</span> <span
  m='156010'>x</span> <span m='156250'>of n.</span> <span m='157450'>The</span>
  <span m='157540'>result</span> <span m='158170'>then</span> <span
  m='158560'>is</span> <span m='158740'>a</span> <span
  m='158800'>periodic</span> <span m='159400'>sequence,</span> <span
  m='160330'>one</span> <span m='160600'>period</span> <span
  m='161020'>of</span> <span m='161170'>which</span> <span
  m='161740'>corresponds</span> <span m='162460'>to</span> <span
  m='162550'>the</span> <span m='162670'>finite</span> <span
  m='163090'>length</span> <span m='163330'>sequence.</span> </p><p><span
  m='165770'>Well,</span> <span m='166270'>we'll</span> <span
  m='166540'>have</span> <span m='166750'>occasion</span> <span
  m='167290'>frequently</span> <span m='168190'>to</span> <span
  m='168550'>refer</span> <span m='168970'>to</span> <span
  m='169510'>this</span> <span m='169690'>periodic</span> <span
  m='170290'>sequence</span> <span m='171430'>in</span> <span
  m='171580'>describing</span> <span m='172240'>the</span> <span
  m='172330'>finite</span> <span m='172780'>length</span> <span
  m='173020'>sequence.</span> <span m='174420'>And</span> <span
  m='174550'>consequently</span> <span m='175570'>it's</span> <span
  m='175750'>convenient</span> <span m='176620'>to</span> <span
  m='176770'>use</span> <span m='177130'>a</span> <span
  m='177190'>slightly</span> <span m='177640'>different</span> <span
  m='178210'>notation</span> <span m='179230'>than</span> <span
  m='179680'>the</span> <span m='179770'>summation</span> <span
  m='180640'>that</span> <span m='180760'>we've</span> <span
  m='180970'>been</span> <span m='181150'>using.</span> <span
  m='182440'>In</span> <span m='182560'>particular,</span> <span
  m='183400'>we</span> <span m='183550'>can</span> <span
  m='183730'>rewrite</span> <span m='184570'>this</span> <span
  m='185590'>as</span> <span m='186520'>the</span> <span
  m='186610'>periodic</span> <span m='187270'>sequence,</span> <span
  m='187990'>x</span> <span m='188260'>tilde</span> <span m='188600'>of</span>
  <span m='188860'>n,</span> <span m='190180'>equal</span> <span
  m='190600'>to</span> <span m='191470'>x</span> <span m='191890'>of</span>
  <span m='192490'>n</span> <span m='193210'>modulo</span> <span
  m='194050'>capital</span> <span m='194560'>N.</span> <span
  m='195370'>That</span> <span m='195580'>is</span> <span m='196330'>x</span>
  <span m='196780'>of</span> <span m='198180'>n</span> <span
  m='199680'>modulo</span> <span m='200160'>capital</span> <span
  m='200700'>N,</span> <span m='200970'>in</span> <span m='201150'>other</span>
  <span m='201360'>words,</span> <span m='201850'>the</span> <span
  m='201900'>argument</span> <span m='202410'>of</span> <span
  m='202500'>x</span> <span m='202770'>of</span> <span m='202890'>n</span> <span
  m='203310'>is</span> <span m='204120'>little</span> <span m='204490'>n</span>
  <span m='204960'>taken</span> <span m='205560'>modulo</span> <span
  m='206190'>capital</span> <span m='206700'>N.</span> <span
  m='208350'>Another</span> <span m='208650'>way</span> <span
  m='208860'>of</span> <span m='208980'>writing</span> <span
  m='209340'>that</span> <span m='209730'>notationally</span> <span
  m='210810'>which</span> <span m='211290'>is</span> <span
  m='211650'>convenient,</span> <span m='212760'>is</span> <span
  m='212940'>just</span> <span m='213210'>to</span> <span
  m='213330'>simply</span> <span m='214020'>express</span> <span
  m='214590'>that</span> <span m='215280'>as</span> <span m='215730'>a</span>
  <span m='215790'>double</span> <span m='216150'>parentheses</span> <span
  m='217230'>with</span> <span m='217380'>a</span> <span
  m='217440'>subscript</span> <span m='217980'>capital</span> <span
  m='218520'>N,</span> <span m='219360'>so</span> <span m='219540'>that</span>
  <span m='219990'>this</span> <span m='220260'>means</span> <span
  m='220950'>x</span> <span m='221280'>of</span> <span m='221880'>n,</span>
  <span m='222980'>the</span> <span m='223170'>argument</span> <span
  m='223680'>n,</span> <span m='224130'>taken</span> <span
  m='224520'>modulo</span> <span m='225000'>capital</span> <span
  m='225260'>N.</span> </p><p><span m='226530'>So,</span> <span
  m='226860'>you</span> <span m='227040'>can</span> <span m='227190'>see</span>
  <span m='227430'>then</span> <span m='228180'>that</span> <span
  m='228390'>as</span> <span m='229140'>little</span> <span m='229470'>n</span>
  <span m='230250'>varies</span> <span m='231570'>over</span> <span
  m='231930'>the</span> <span m='232080'>interval</span> <span
  m='232470'>0</span> <span m='232890'>to</span> <span m='233010'>capital</span>
  <span m='233490'>N</span> <span m='233640'>minus</span> <span
  m='234030'>1,</span> <span m='235260'>we</span> <span m='235380'>see</span>
  <span m='236040'>the</span> <span m='236160'>finite</span> <span
  m='236610'>length</span> <span m='236880'>sequence</span> <span
  m='237780'>x</span> <span m='238050'>of</span> <span m='238170'>n</span> <span
  m='240090'>as</span> <span m='240330'>little</span> <span m='240660'>n</span>
  <span m='241650'>is</span> <span m='241830'>equal</span> <span
  m='242580'>to</span> <span m='243570'>capital</span> <span
  m='244080'>N.</span> <span m='245100'>Capital</span> <span m='245550'>N</span>
  <span m='245730'>taken</span> <span m='246090'>modulo,</span> <span
  m='246720'>capital</span> <span m='247200'>N</span> <span m='247350'>is</span>
  <span m='247440'>0.</span> <span m='248340'>So</span> <span
  m='248520'>we'll</span> <span m='248700'>see</span> <span m='249330'>x</span>
  <span m='249570'>of</span> <span m='249690'>0</span> <span
  m='250380'>back</span> <span m='250710'>again.</span> <span
  m='251760'>And</span> <span m='252120'>as</span> <span
  m='252330'>little</span> <span m='252630'>n</span> <span
  m='252930'>varies</span> <span m='253470'>in</span> <span
  m='253620'>the</span> <span m='253710'>range</span> <span
  m='254310'>capital</span> <span m='254575'>N</span> <span m='254840'>to</span>
  <span m='255140'>2</span> <span m='255630'>capital</span> <span
  m='256140'>N</span> <span m='256589'>minus</span> <span m='256980'>1.</span>
  <span m='257850'>That</span> <span m='258060'>argument</span> <span
  m='258570'>taken</span> <span m='258990'>modulo</span> <span
  m='259440'>N</span> <span m='260160'>again</span> <span
  m='260730'>repeats</span> <span m='261209'>the</span> <span
  m='261329'>values</span> <span m='262620'>of</span> <span m='262860'>x</span>
  <span m='263160'>of n</span> <span m='263790'>the</span> <span
  m='263880'>range</span> <span m='264750'>n</span> <span
  m='265080'>equals</span> <span m='265380'>0</span> <span m='265830'>to</span>
  <span m='265980'>capital</span> <span m='266430'>N</span> <span
  m='266550'>minus</span> <span m='266940'>1.</span> </p><p><span
  m='268410'>Expressing</span> <span m='268980'>it</span> <span
  m='269100'>this</span> <span m='269340'>way</span> <span m='269820'>or</span>
  <span m='270300'>equivalently</span> <span m='270990'>expressing</span> <span
  m='271560'>it</span> <span m='271680'>this</span> <span m='271920'>way,</span>
  <span m='272400'>as</span> <span m='272550'>I</span> <span
  m='272640'>stressed</span> <span m='273030'>before</span> <span
  m='273750'>in</span> <span m='273870'>the</span> <span
  m='273990'>previous</span> <span m='274470'>lecture,</span> <span
  m='275910'>corresponds</span> <span m='277170'>to</span> <span
  m='277320'>taking</span> <span m='278010'>the</span> <span
  m='278130'>finite</span> <span m='278550'>length</span> <span
  m='278760'>sequence,</span> <span m='279420'>x</span> <span
  m='279690'>of</span> <span m='279810'>n,</span> <span m='280610'>and</span>
  <span m='280710'>simply</span> <span m='281100'>wrapping</span> <span
  m='281520'>it</span> <span m='281610'>around</span> <span
  m='281880'>the</span> <span m='282000'>circumference</span> <span
  m='282660'>of</span> <span m='282750'>a</span> <span
  m='282810'>cylinder.</span> <span m='284310'>As</span> <span
  m='284460'>we</span> <span m='284610'>run</span> <span
  m='284820'>around</span> <span m='285090'>the</span> <span
  m='285180'>circumference</span> <span m='285840'>of</span> <span
  m='285930'>the</span> <span m='286020'>cylinder,</span> <span
  m='287230'>we</span> <span m='287280'>see</span> <span m='287640'>x</span>
  <span m='287940'>of</span> <span m='288100'>n</span> <span
  m='288690'>repeated</span> <span m='289320'>over</span> <span
  m='289650'>and</span> <span m='289740'>over</span> <span
  m='290040'>again.</span> <span m='292610'>Likewise,</span> <span
  m='293630'>we</span> <span m='293810'>were</span> <span m='293960'>able</span>
  <span m='294290'>to</span> <span m='294440'>get</span> <span
  m='294800'>back</span> <span m='295310'>to</span> <span m='295850'>the</span>
  <span m='295970'>finite</span> <span m='296390'>length</span> <span
  m='296660'>sequence</span> <span m='297620'>from</span> <span
  m='297830'>the</span> <span m='297950'>periodic</span> <span
  m='298550'>sequence</span> <span m='299930'>by</span> <span
  m='300620'>simply</span> <span m='301040'>multiplying</span> <span
  m='301760'>by</span> <span m='302000'>a</span> <span
  m='302060'>rectangular</span> <span m='302750'>sequence,</span> <span
  m='303410'>in</span> <span m='303560'>other</span> <span
  m='303770'>words</span> <span m='304250'>extracting</span> <span
  m='305000'>a</span> <span m='305030'>single</span> <span
  m='305390'>period.</span> <span m='306860'>A</span> <span
  m='306920'>single</span> <span m='307310'>period</span> <span
  m='307880'>of</span> <span m='308030'>the</span> <span
  m='308120'>periodic</span> <span m='308720'>sequence</span> <span
  m='309740'>corresponds</span> <span m='310850'>to</span> <span
  m='310970'>the</span> <span m='311060'>finite</span> <span
  m='311480'>length</span> <span m='311690'>sequence</span> <span
  m='312230'>that</span> <span m='312350'>we</span> <span
  m='312500'>began</span> <span m='312920'>with.</span> </p><p><span
  m='314610'>In</span> <span m='314700'>the</span> <span m='314760'>last</span>
  <span m='315090'>lecture</span> <span m='315450'>we</span> <span
  m='315540'>then</span> <span m='316020'>introduced</span> <span
  m='316650'>the</span> <span m='316890'>discrete</span> <span
  m='317280'>Fourier</span> <span m='317730'>series</span> <span
  m='318540'>of</span> <span m='319320'>x</span> <span m='319860'>tilde</span>
  <span m='320290'>of n,</span> <span m='321390'>and</span> <span
  m='322030'>the</span> <span m='322130'>discrete</span> <span
  m='322500'>Fourier</span> <span m='322890'>series</span> <span
  m='323280'>coefficients</span> <span m='324150'>we</span> <span
  m='324300'>denoted</span> <span m='324870'>as</span> <span
  m='325140'>capital</span> <span m='325590'>X</span> <span
  m='325800'>tilde</span> <span m='326130'>of</span> <span m='326380'>k,</span>
  <span m='327360'>and</span> <span m='327480'>chose</span> <span
  m='327840'>to</span> <span m='327960'>interpret</span> <span
  m='328470'>them,</span> <span m='328810'>as</span> <span m='328950'>you</span>
  <span m='329040'>recall,</span> <span m='330090'>as</span> <span
  m='330750'>a</span> <span m='331140'>periodic</span> <span
  m='331800'>sequence,</span> <span m='333210'>periodic</span> <span
  m='334020'>in</span> <span m='334170'>k</span> <span m='335190'>with</span>
  <span m='335310'>a</span> <span m='335370'>period</span> <span
  m='335850'>of</span> <span m='335940'>capital</span> <span
  m='336420'>N.</span> <span m='338430'>The</span> <span
  m='338700'>discrete</span> <span m='339090'>Fourier</span> <span
  m='339510'>series</span> <span m='339930'>representation,</span> <span
  m='341220'>just</span> <span m='341760'>to</span> <span
  m='342390'>summarize</span> <span m='342990'>it</span> <span
  m='343050'>again</span> <span m='343350'>for</span> <span
  m='343650'>you,</span> <span m='344760'>we've</span> <span
  m='345210'>rewritten</span> <span m='345720'>here</span> <span
  m='346530'>that</span> <span m='346710'>is</span> <span m='347070'>a</span>
  <span m='347160'>sum</span> <span m='347670'>of</span> <span
  m='348030'>complex</span> <span m='348600'>exponentials</span> <span
  m='349530'>harmonically</span> <span m='350130'>related</span> <span
  m='351930'>generate</span> <span m='352500'>x</span> <span
  m='352770'>tilde</span> <span m='353220'>of n.</span> <span m='354000'>And
  the</span> <span m='354320'>Fourier</span> <span m='354780'>series</span>
  <span m='355170'>coefficients,</span> <span m='355990'>capital</span> <span
  m='356340'>X</span> <span m='356520'>tilde</span> <span m='356840'>of</span>
  <span m='357030'>k</span> <span m='357930'>were</span> <span
  m='358170'>given</span> <span m='358740'>by</span> <span
  m='359100'>this</span> <span m='359340'>expression.</span> <span
  m='361450'>And</span> <span m='362070'>I</span> <span m='362190'>stress</span>
  <span m='362580'>again</span> <span m='363240'>the</span> <span
  m='363360'>fact</span> <span m='363990'>that</span> <span m='364350'>we</span>
  <span m='364500'>chose</span> <span m='364980'>to</span> <span
  m='365130'>interpret</span> <span m='366480'>the</span> <span
  m='366660'>Fourier</span> <span m='367140'>series</span> <span
  m='367590'>coefficients</span> <span m='368760'>as</span> <span
  m='368970'>a</span> <span m='369030'>periodic</span> <span
  m='369630'>sequence.</span> <span m='370620'>And</span> <span
  m='370740'>it</span> <span m='370830'>didn't</span> <span
  m='371130'>particularly</span> <span m='371790'>matter,</span> <span
  m='372990'>because</span> <span m='373560'>in</span> <span
  m='373740'>any</span> <span m='373980'>case</span> <span m='374890'>we</span>
  <span m='374970'>only</span> <span m='375270'>use</span> <span
  m='375840'>a</span> <span m='375900'>single</span> <span
  m='376290'>period</span> <span m='376770'>of</span> <span
  m='376920'>that</span> <span m='377670'>in</span> <span
  m='378060'>constructing</span> <span m='379470'>the</span> <span
  m='379650'>periodic</span> <span m='380220'>sequence,</span> <span
  m='380790'>x</span> <span m='381050'>tilde</span> <span m='381250'>of</span>
  <span m='381400'>n.</span> </p><p><span m='383370'>Now</span> <span
  m='383700'>in</span> <span m='383820'>this</span> <span
  m='384030'>lecture,</span> <span m='384540'>what</span> <span
  m='384750'>we'd</span> <span m='384900'>like</span> <span m='385110'>to</span>
  <span m='385260'>do</span> <span m='385650'>is</span> <span
  m='385890'>apply</span> <span m='387090'>the</span> <span
  m='387390'>idea</span> <span m='388530'>of</span> <span m='388710'>the</span>
  <span m='388800'>discrete</span> <span m='389190'>Fourier</span> <span
  m='389640'>series</span> <span m='390930'>and</span> <span
  m='391080'>the</span> <span m='391170'>similarity</span> <span
  m='392130'>or</span> <span m='392400'>basically</span> <span
  m='393030'>the</span> <span m='393150'>equivalence</span> <span
  m='393960'>of</span> <span m='394110'>finite</span> <span
  m='394560'>length</span> <span m='394820'>and</span> <span
  m='394920'>periodic</span> <span m='395520'>sequences</span> <span
  m='396930'>to</span> <span m='397350'>a</span> <span m='397530'>Fourier</span>
  <span m='398040'>series</span> <span m='398790'>representation</span> <span
  m='400620'>of</span> <span m='401460'>finite</span> <span
  m='401970'>length</span> <span m='402240'>sequences.</span> <span
  m='403800'>And</span> <span m='404280'>basically</span> <span
  m='404880'>the</span> <span m='405030'>idea</span> <span m='405900'>is</span>
  <span m='406950'>that</span> <span m='408240'>we</span> <span
  m='408450'>can</span> <span m='409440'>convert</span> <span
  m='409890'>the</span> <span m='410010'>finite</span> <span
  m='410400'>length</span> <span m='410640'>sequence</span> <span
  m='411120'>to</span> <span m='411240'>a</span> <span
  m='411300'>periodic</span> <span m='411900'>sequence.</span> <span
  m='412560'>We've</span> <span m='412710'>seen</span> <span
  m='413010'>how</span> <span m='413100'>to</span> <span m='413220'>do</span>
  <span m='413370'>that,</span> <span m='413550'>and</span> <span
  m='413640'>go</span> <span m='413790'>back</span> <span m='414090'>and</span>
  <span m='414180'>forth.</span> <span m='415340'>Generate</span> <span
  m='415870'>a</span> <span m='415980'>Fourier</span> <span
  m='416400'>series</span> <span m='417000'>representation</span> <span
  m='418350'>for</span> <span m='418500'>that,</span> <span
  m='419730'>and</span> <span m='419940'>then</span> <span
  m='420120'>simply</span> <span m='420480'>interpret</span> <span
  m='421020'>the</span> <span m='421140'>Fourier</span> <span
  m='421540'>series</span> <span m='421950'>coefficients</span> <span
  m='423210'>as</span> <span m='423810'>what</span> <span
  m='424050'>we'll</span> <span m='424230'>call</span> <span
  m='424950'>the</span> <span m='425070'>discrete</span> <span
  m='425580'>Fourier</span> <span m='426030'>transform</span> <span
  m='426870'>of</span> <span m='427020'>the</span> <span
  m='427110'>finite</span> <span m='427560'>length</span> <span
  m='427770'>sequence.</span> </p><p><span m='429780'>So,</span> <span
  m='430380'>the</span> <span m='430500'>discrete</span> <span
  m='430920'>Fourier</span> <span m='431340'>transform</span> <span
  m='432090'>then</span> <span m='433590'>is</span> <span
  m='434340'>given</span> <span m='434730'>by</span> <span m='435840'>the</span>
  <span m='435940'>sum</span> <span m='436600'>from n</span> <span
  m='437010'>equals</span> <span m='437310'>0</span> <span m='438080'>to</span>
  <span m='438190'>capital</span> <span m='438690'>N</span> <span
  m='438810'>minus</span> <span m='439230'>1</span> <span m='440490'>of</span>
  <span m='440910'>x</span> <span m='441180'>of n</span> <span
  m='441810'>times</span> <span m='442140'>w</span> <span m='442590'>sub</span>
  <span m='442710'>capital</span> <span m='443220'>N</span> <span
  m='443790'>to</span> <span m='443910'>the</span> <span m='444090'>nk,</span>
  <span m='446130'>corresponding</span> <span m='447000'>to</span> <span
  m='447120'>the</span> <span m='447240'>fact</span> <span
  m='448260'>that</span> <span m='449220'>if</span> <span m='449760'>we</span>
  <span m='451110'>generate</span> <span m='451980'>a</span> <span
  m='452040'>periodic</span> <span m='452670'>sequence</span> <span
  m='453570'>from</span> <span m='453810'>x</span> <span m='454050'>of</span>
  <span m='454150'>n,</span> <span m='456060'>we</span> <span
  m='456210'>can</span> <span m='456360'>recognize</span> <span
  m='457380'>that</span> <span m='457710'>in</span> <span m='458340'>this</span>
  <span m='458520'>summation</span> <span m='459570'>for</span> <span
  m='459930'>the Fourier</span> <span m='460290'>series</span> <span
  m='460860'>coefficients,</span> <span m='462210'>in</span> <span
  m='462330'>fact,</span> <span m='463060'>we</span> <span
  m='463140'>only</span> <span m='463410'>use</span> <span m='464130'>one</span>
  <span m='464370'>period</span> <span m='465570'>of</span> <span
  m='465870'>x</span> <span m='466140'>tilde</span> <span m='466450'>of</span>
  <span m='466630'>n</span> <span m='467010'>anyway.</span> <span
  m='467940'>So</span> <span m='468180'>that</span> <span m='468810'>we</span>
  <span m='468990'>could</span> <span m='469320'>simply</span> <span
  m='469740'>replace</span> <span m='470220'>in</span> <span
  m='470370'>here</span> <span m='471110'>x</span> <span m='471330'>tilde</span>
  <span m='471680'>of</span> <span m='471840'>n</span> <span
  m='472080'>by</span> <span m='472290'>x</span> <span m='472580'>of</span>
  <span m='472855'>n.</span> <span m='473530'>And</span> <span
  m='473550'>of</span> <span m='473640'>course,</span> <span
  m='474070'>since</span> <span m='474210'>the</span> <span
  m='474330'>summation</span> <span m='474900'>runs</span> <span
  m='475200'>from</span> <span m='475350'>0</span> <span m='475800'>to</span>
  <span m='475950'>capital</span> <span m='476400'>N</span> <span
  m='476550'>minus</span> <span m='476910'>1,</span> <span m='477570'>we</span>
  <span m='477690'>can't</span> <span m='477930'>tell</span> <span
  m='478170'>the</span> <span m='478290'>difference.</span> </p><p><span
  m='480610'>This</span> <span m='480780'>then</span> <span m='481200'>is</span>
  <span m='482400'>by</span> <span m='482610'>definition</span> <span
  m='483960'>the</span> <span m='484230'>discrete</span> <span
  m='484970'>Fourier</span> <span m='485490'>transform</span> <span
  m='487080'>of</span> <span m='487710'>the</span> <span
  m='487800'>finite</span> <span m='488280'>length</span> <span
  m='488520'>sequence,</span> <span m='489600'>x</span> <span
  m='489900'>of</span> <span m='490020'>n.</span> <span m='492030'>And</span>
  <span m='493320'>it</span> <span m='493710'>is</span> <span
  m='494820'>denoted</span> <span m='495510'>by</span> <span m='495810'>x</span>
  <span m='496140'>of</span> <span m='496290'>k.</span> <span
  m='498220'>It</span> <span m='498340'>corresponds</span> <span
  m='499300'>to</span> <span m='499600'>the</span> <span
  m='499720'>Fourier</span> <span m='500140'>series</span> <span
  m='500530'>coefficients</span> <span m='501460'>of</span> <span
  m='501640'>the</span> <span m='501730'>periodic</span> <span
  m='502780'>equivalent</span> <span m='503650'>sequence</span> <span
  m='504520'>for</span> <span m='504760'>x of</span> <span m='505040'>n,</span>
  <span m='506170'>except</span> <span m='506680'>that</span> <span
  m='507820'>it</span> <span m='508090'>is</span> <span m='508300'>useful</span>
  <span m='508930'>to</span> <span m='509080'>maintain</span> <span
  m='509530'>the</span> <span m='509650'>duality</span> <span
  m='510550'>between</span> <span m='510940'>the</span> <span
  m='511030'>time</span> <span m='511420'>domain</span> <span
  m='511780'>and</span> <span m='511900'>frequency</span> <span
  m='512440'>domain</span> <span m='513580'>by</span> <span
  m='514059'>interpreting</span> <span m='515159'>the</span> <span
  m='515289'>Fourier</span> <span m='516370'>transform,</span> <span
  m='517169'>the</span> <span m='517270'>discrete</span> <span
  m='517539'>Fourier</span> <span m='517929'>transform</span> <span
  m='519190'>to</span> <span m='519309'>be</span> <span m='519669'>a</span>
  <span m='519760'>finite</span> <span m='520299'>length</span> <span
  m='520510'>sequence,</span> <span m='521950'>since</span> <span
  m='522700'>the</span> <span m='522880'>sequence</span> <span
  m='523690'>that</span> <span m='523840'>we're</span> <span
  m='523990'>computing</span> <span m='524275'>the</span> <span
  m='524560'>Fourier</span> <span m='524950'>transform</span> <span
  m='525940'>from</span> <span m='526630'>likewise</span> <span
  m='527500'>starts</span> <span m='528010'>as</span> <span m='528160'>a</span>
  <span m='528220'>finite</span> <span m='528640'>length</span> <span
  m='528850'>sequence.</span> </p><p><span m='530630'>Well,</span> <span
  m='530860'>that's</span> <span m='531100'>straightforward.</span> <span
  m='532490'>It</span> <span m='532510'>just</span> <span
  m='532720'>simply</span> <span m='533260'>involves</span> <span
  m='534010'>taking</span> <span m='534370'>the</span> <span
  m='534490'>Fourier</span> <span m='534880'>series</span> <span
  m='535270'>coefficients</span> <span m='537700'>for</span> <span
  m='538150'>k</span> <span m='538690'>in</span> <span m='538840'>the</span>
  <span m='538900'>range</span> <span m='539290'>0</span> <span
  m='540190'>to</span> <span m='540280'>capital</span> <span m='540760'>N</span>
  <span m='540910'>minus</span> <span m='541300'>1,</span> <span
  m='543210'>and</span> <span m='543540'>simply</span> <span
  m='543930'>setting</span> <span m='544290'>them</span> <span
  m='544440'>to</span> <span m='544590'>0</span> <span m='545430'>outside</span>
  <span m='545940'>that</span> <span m='546150'>range.</span> <span
  m='548450'>In</span> <span m='548600'>other</span> <span
  m='548810'>words,</span> <span m='549660'>the</span> <span
  m='549820'>discrete</span> <span m='550430'>Fourier</span> <span
  m='550790'>transform,</span> <span m='552320'>x</span> <span
  m='552610'>of</span> <span m='552740'>k</span> <span m='554210'>of</span>
  <span m='554330'>a</span> <span m='554390'>finite</span> <span
  m='554840'>length</span> <span m='555050'>sequence</span> <span
  m='555890'>x</span> <span m='556130'>of</span> <span m='556250'>n,</span>
  <span m='558020'>is</span> <span m='558170'>equal</span> <span
  m='558620'>to</span> <span m='559670'>the</span> <span
  m='560170'>Fourier</span> <span m='560690'>series</span> <span
  m='561110'>coefficients</span> <span m='563500'>of</span> <span
  m='564180'>the</span> <span m='564330'>periodic</span> <span
  m='565050'>equivalent</span> <span m='566670'>of</span> <span
  m='566850'>x</span> <span m='567100'>of</span> <span m='567320'>n</span> <span
  m='568950'>multiplied</span> <span m='569970'>by</span> <span
  m='570570'>a</span> <span m='570660'>rectangular</span> <span
  m='571380'>sequence</span> <span m='572400'>to</span> <span
  m='572760'>extract</span> <span m='573330'>a</span> <span
  m='573390'>single</span> <span m='573750'>period.</span> </p><p><span
  m='576780'>We</span> <span m='576970'>can</span> <span
  m='577170'>likewise</span> <span m='577800'>then</span> <span
  m='578220'>get</span> <span m='578460'>the</span> <span
  m='578580'>Fourier</span> <span m='579000'>series</span> <span
  m='579450'>coefficients</span> <span m='580800'>from</span> <span
  m='581460'>the</span> <span m='581700'>discrete</span> <span
  m='582150'>Fourier</span> <span m='582600'>transform,</span> <span
  m='583350'>x</span> <span m='583620'>of</span> <span m='583740'>k,</span>
  <span m='584910'>by</span> <span m='585690'>simply</span> <span
  m='586170'>periodically</span> <span m='587250'>repeating</span> <span
  m='587940'>x</span> <span m='588240'>of</span> <span m='588370'>k</span> <span
  m='589260'>with</span> <span m='589410'>a</span> <span
  m='589470'>period</span> <span m='589830'>of</span> <span
  m='589950'>capital</span> <span m='590460'>N.</span> <span
  m='591330'>Or</span> <span m='591660'>equivalently,</span> <span
  m='593070'>we</span> <span m='593220'>can</span> <span m='593430'>write</span>
  <span m='595080'>that</span> <span m='595560'>the</span> <span
  m='595920'>Fourier</span> <span m='596370'>series</span> <span
  m='596760'>coefficients,</span> <span m='597840'>x</span> <span
  m='598080'>tilde</span> <span m='598410'>of</span> <span m='598620'>k,</span>
  <span m='599520'>are</span> <span m='599700'>equal</span> <span
  m='600120'>to</span> <span m='600840'>the</span> <span
  m='601050'>discrete</span> <span m='601440'>Fourier</span> <span
  m='601860'>transform</span> <span m='602610'>values</span> <span
  m='604110'>with</span> <span m='604680'>the</span> <span
  m='604830'>argument</span> <span m='605970'>taken</span> <span
  m='607020'>modulo</span> <span m='607800'>capital</span> <span
  m='608340'>N.</span> <span m='609240'>This</span> <span
  m='610020'>corresponds</span> <span m='610890'>to</span> <span
  m='611040'>simply</span> <span m='611700'>periodically</span> <span
  m='612450'>repeating</span> <span m='613380'>capital</span> <span
  m='613800'>X</span> <span m='614010'>of</span> <span m='614130'>k,</span>
  <span m='615150'>like</span> <span m='616170'>wrapping</span> <span
  m='616800'>capital</span> <span m='617220'>X</span> <span m='617430'>of</span>
  <span m='617550'>k</span> <span m='618030'>around</span> <span
  m='618300'>the</span> <span m='618390'>circumference</span> <span
  m='619020'>of</span> <span m='619140'>a</span> <span
  m='619170'>cylinder,</span> <span m='620550'>running</span> <span
  m='620880'>around</span> <span m='621150'>the</span> <span
  m='621270'>circumference</span> <span m='622020'>again</span> <span
  m='622290'>and</span> <span m='622410'>again.</span> <span
  m='623590'>And</span> <span m='623850'>what</span> <span m='624060'>we</span>
  <span m='624210'>see</span> <span m='624750'>are</span> <span
  m='625070'>the</span> <span m='625200'>Fourier</span> <span
  m='625590'>series</span> <span m='625980'>coefficients.</span> </p><p><span
  m='628200'>Now</span> <span m='628650'>perhaps</span> <span
  m='629010'>this</span> <span m='629160'>sounds</span> <span
  m='629670'>a</span> <span m='629730'>little</span> <span
  m='630000'>involved</span> <span m='630810'>or</span> <span
  m='631380'>intricate.</span> <span m='632640'>The</span> <span
  m='632970'>idea</span> <span m='633480'>is</span> <span
  m='633660'>really</span> <span m='633900'>very</span> <span
  m='634170'>simple.</span> <span m='635290'>It</span> <span
  m='635340'>just</span> <span m='635670'>simply</span> <span
  m='636240'>is</span> <span m='636930'>that</span> <span m='637200'>the</span>
  <span m='637320'>discrete</span> <span m='637800'>Fourier</span> <span
  m='638220'>transform</span> <span m='640590'>corresponds</span> <span
  m='641580'>to</span> <span m='642390'>the</span> <span
  m='642510'>Fourier</span> <span m='642900'>series</span> <span
  m='643380'>coefficients</span> <span m='644670'>for</span> <span
  m='645240'>the</span> <span m='646050'>periodic</span> <span
  m='646680'>equivalent</span> <span m='647370'>of</span> <span
  m='647500'>the</span> <span m='647610'>finite</span> <span
  m='648030'>length</span> <span m='648270'>sequence.</span> <span
  m='649530'>And</span> <span m='649650'>to</span> <span
  m='649770'>maintain</span> <span m='650250'>the</span> <span
  m='650340'>duality,</span> <span m='651450'>in</span> <span
  m='651570'>this</span> <span m='651780'>case,</span> <span
  m='652450'>we</span> <span m='652470'>choose</span> <span m='652860'>to</span>
  <span m='652980'>simply</span> <span m='653370'>extract</span> <span
  m='653820'>one</span> <span m='654030'>period</span> <span
  m='654680'>of</span> <span m='654850'>the</span> <span
  m='654930'>Fourier</span> <span m='655320'>series</span> <span
  m='655710'>coefficients</span> <span m='656930'>so</span> <span
  m='657120'>that</span> <span m='657300'>now</span> <span m='657570'>we</span>
  <span m='657750'>have</span> <span m='658890'>a</span> <span
  m='658980'>finite</span> <span m='659400'>length</span> <span
  m='659640'>sequence.</span> <span m='660840'>Its</span> <span
  m='661020'>discrete</span> <span m='661410'>Fourier</span> <span
  m='661830'>transform</span> <span m='662760'>is</span> <span
  m='662940'>likewise</span> <span m='663810'>a</span> <span
  m='663870'>finite</span> <span m='664320'>length</span> <span
  m='664530'>sequence.</span> </p><p><span m='667770'>And</span> <span
  m='668340'>the</span> <span m='668460'>properties</span> <span
  m='669480'>of</span> <span m='669990'>the</span> <span
  m='670140'>discrete</span> <span m='670530'>Fourier</span> <span
  m='670950'>transform,</span> <span m='671930'>as</span> <span
  m='672120'>we'll</span> <span m='672240'>see,</span> <span
  m='673800'>the</span> <span m='674010'>differences</span> <span
  m='674550'>in</span> <span m='674640'>the</span> <span
  m='674730'>properties</span> <span m='675420'>between</span> <span
  m='675870'>this</span> <span m='676170'>and</span> <span m='676320'>the</span>
  <span m='676510'>Fourier</span> <span m='676830'>transforms</span> <span
  m='677430'>we've</span> <span m='677550'>talked</span> <span
  m='677850'>about</span> <span m='678060'>in</span> <span
  m='678120'>previous</span> <span m='678600'>lectures</span> <span
  m='679890'>are</span> <span m='680460'>related</span> <span
  m='681300'>very</span> <span m='681690'>closely</span> <span
  m='682830'>to</span> <span m='683160'>the</span> <span
  m='683310'>implied</span> <span m='684060'>periodicity</span> <span
  m='685170'>in</span> <span m='685320'>the</span> <span
  m='685410'>sequence</span> <span m='686100'>or</span> <span
  m='687450'>in</span> <span m='687750'>the</span> <span
  m='687840'>discrete</span> <span m='688200'>Fourier</span> <span
  m='688690'>transform.</span> <span m='690690'>Before</span> <span
  m='691050'>discussing</span> <span m='691590'>the</span> <span
  m='691680'>properties,</span> <span m='692250'>however,</span> <span
  m='692850'>it's</span> <span m='693090'>useful</span> <span
  m='694170'>to</span> <span m='694680'>relate</span> <span
  m='695400'>the</span> <span m='695610'>discrete</span> <span
  m='696000'>Fourier</span> <span m='696420'>transform</span> <span
  m='697800'>to</span> <span m='698220'>the</span> <span m='698340'>Z</span>
  <span m='698580'>transform,</span> <span m='699390'>as</span> <span
  m='699540'>we've</span> <span m='699750'>talked</span> <span m='700080'>about
  it</span> <span m='700440'>previously.</span> </p><p><span
  m='701820'>In</span> <span m='701940'>particular,</span> <span
  m='703110'>here</span> <span m='703770'>we</span> <span m='703950'>have</span>
  <span m='704640'>the</span> <span m='705200'>Fourier</span> <span
  m='706050'>transform,</span> <span m='707740'>the</span> <span
  m='707880'>discrete</span> <span m='708390'>Fourier</span> <span
  m='708810'>transform</span> <span m='709770'>relationship,</span> <span
  m='712170'>capital</span> <span m='712620'>X</span> <span m='712830'>of</span>
  <span m='712950'>k</span> <span m='714330'>is</span> <span
  m='714480'>the</span> <span m='714600'>sum</span> <span m='714930'>from</span>
  <span m='715140'>n equals</span> <span m='716520'>capital</span> <span
  m='716910'>N</span> <span m='717030'>minus 1</span> <span m='717420'>of</span>
  <span m='717780'>x</span> <span m='717990'>of</span> <span
  m='718140'>n,</span> <span m='718650'>w</span> <span m='719100'>sub</span>
  <span m='719550'>N</span> <span m='719700'>to the</span> <span
  m='719850'>nk.</span> <span m='721290'>Although</span> <span
  m='722040'>that</span> <span m='722310'>has</span> <span m='722550'>to</span>
  <span m='722670'>be</span> <span m='722790'>multiplied</span> <span
  m='724200'>by</span> <span m='724770'>R</span> <span m='725880'>sub n</span>
  <span m='726830'>of</span> <span m='727060'>k</span> <span
  m='728610'>to</span> <span m='728760'>extract</span> <span m='729250'>a</span>
  <span m='729330'>single</span> <span m='729690'>period.</span> <span
  m='731490'>The</span> <span m='731670'>inverse</span> <span
  m='732390'>discrete</span> <span m='732780'>Fourier</span> <span
  m='733200'>transform</span> <span m='733890'>relationship</span> <span
  m='735400'>then</span> <span m='735850'>is</span> <span m='736830'>the</span>
  <span m='736980'>inverse</span> <span m='737820'>Fourier</span> <span
  m='738240'>series</span> <span m='739230'>relationship</span> <span
  m='740660'>1</span> <span m='740880'>over</span> <span
  m='741090'>capital</span> <span m='741630'>N</span> <span
  m='742410'>the</span> <span m='742500'>sum</span> <span m='743070'>x</span>
  <span m='743310'>sub</span> <span m='743430'>k</span> <span
  m='743940'>w</span> <span m='744240'>sub</span> <span m='744540'>of</span>
  <span m='745050'>capital</span> <span m='745500'>N</span> <span m='745630'>to
  the</span> <span m='745830'>minus</span> <span m='746220'>nk.</span> <span
  m='747930'>And</span> <span m='748440'>again,</span> <span
  m='749520'>since</span> <span m='750120'>we're</span> <span
  m='750300'>no</span> <span m='750510'>longer</span> <span
  m='750900'>talking</span> <span m='751500'>about</span> <span
  m='751800'>a</span> <span m='751860'>periodic</span> <span
  m='752490'>sequence,</span> <span m='753630'>it's</span> <span
  m='753810'>necessary</span> <span m='754500'>to</span> <span
  m='754680'>extract</span> <span m='755280'>one</span> <span
  m='755520'>period,</span> <span m='757530'>this</span> <span
  m='757830'>multiplied</span> <span m='758610'>by R</span> <span
  m='758820'>sub</span> <span m='759240'>capital</span> <span
  m='759780'>N</span> <span m='761140'>of</span> <span m='761460'>n.</span>
  </p><p><span m='764190'>On</span> <span m='764310'>the</span> <span
  m='764400'>other</span> <span m='764610'>hand,</span> <span
  m='765010'>the</span> <span m='765110'>Z</span> <span
  m='765240'>transform</span> <span m='766470'>of</span> <span
  m='766620'>the</span> <span m='766740'>finite</span> <span
  m='767190'>length</span> <span m='767400'>sequence</span> <span
  m='768270'>is</span> <span m='768570'>the</span> <span m='768660'>sum</span>
  <span m='769440'>of</span> <span m='769830'>x</span> <span m='770240'>of
  n</span> <span m='771240'>times</span> <span m='771580'>z</span> <span
  m='771870'>to</span> <span m='772020'>the</span> <span m='772110'>minus</span>
  <span m='772530'>n.</span> <span m='774090'>In</span> <span
  m='774210'>general,</span> <span m='774660'>of</span> <span
  m='774780'>course,</span> <span m='775320'>the</span> <span
  m='775410'>sum</span> <span m='775740'>running</span> <span
  m='776010'>from</span> <span m='776190'>minus</span> <span
  m='776550'>infinity</span> <span m='777000'>to</span> <span
  m='777120'>plus</span> <span m='777420'>infinity,</span> <span
  m='778560'>but</span> <span m='778770'>because</span> <span
  m='779550'>this</span> <span m='779760'>is</span> <span m='779880'>a</span>
  <span m='779940'>finite</span> <span m='780360'>length</span> <span
  m='780630'>sequence,</span> <span m='781680'>this</span> <span
  m='781890'>is</span> <span m='782040'>a</span> <span m='782100'>sum</span>
  <span m='782910'>from</span> <span m='783210'>n</span> <span
  m='783660'>equals</span> <span m='784020'>0</span> <span m='785550'>to</span>
  <span m='785670'>capital</span> <span m='786210'>N</span> <span
  m='786330'>minus</span> <span m='786780'>1,</span> <span
  m='788175'>because</span> <span m='788640'>of</span> <span
  m='788730'>the</span> <span m='788850'>fact</span> <span
  m='789810'>that</span> <span m='790020'>the</span> <span
  m='790140'>sequence</span> <span m='790590'>x</span> <span m='790860'>of
  n</span> <span m='791430'>is</span> <span m='791580'>0</span> <span
  m='792630'>outside</span> <span m='793170'>the</span> <span
  m='793290'>range</span> <span m='793800'>n</span> <span
  m='793950'>equals</span> <span m='794200'>zero</span> <span
  m='794550'>to</span> <span m='794640'>capital</span> <span m='795120'>N</span>
  <span m='795240'>minus</span> <span m='795600'>1.</span> </p><p><span
  m='797530'>Well,</span> <span m='797970'>to</span> <span
  m='798090'>relate</span> <span m='798510'>the</span> <span m='798600'>Z</span>
  <span m='798810'>transform</span> <span m='800430'>to</span> <span
  m='801480'>the</span> <span m='801840'>discrete</span> <span
  m='802140'>Fourier</span> <span m='802710'>transform,</span> <span
  m='804300'>we</span> <span m='804450'>simply</span> <span
  m='805260'>need</span> <span m='805830'>to</span> <span
  m='806730'>compare</span> <span m='807390'>this</span> <span
  m='807660'>expression</span> <span m='809100'>with</span> <span
  m='809280'>this</span> <span m='809520'>expression.</span> <span
  m='811360'>And</span> <span m='811860'>what</span> <span m='812070'>we</span>
  <span m='812250'>see,</span> <span m='813360'>ignoring</span> <span
  m='813900'>for</span> <span m='814080'>a</span> <span m='814110'>moment</span>
  <span m='814530'>the</span> <span m='814890'>capital</span> <span
  m='815310'>R</span> <span m='815580'>sub</span> <span m='815850'>N</span>
  <span m='816420'>of</span> <span m='816570'>k,</span> <span
  m='818460'>that</span> <span m='819120'>these</span> <span
  m='819390'>two</span> <span m='819600'>expressions</span> <span
  m='820290'>are</span> <span m='820440'>equal</span> <span m='821580'>if</span>
  <span m='821760'>we</span> <span m='821880'>pick</span> <span
  m='822420'>z</span> <span m='823620'>equal</span> <span m='824130'>to</span>
  <span m='824810'>w</span> <span m='825630'>sub</span> <span
  m='825940'>capital</span> <span m='826440'>N</span> <span m='826860'>to</span>
  <span m='827220'>the</span> <span m='827340'>minus</span> <span
  m='827730'>k.</span> <span m='828900'>So</span> <span m='829800'>the</span>
  <span m='830280'>discrete</span> <span m='830670'>Fourier</span> <span
  m='831090'>transform</span> <span m='832650'>coefficients</span> <span
  m='834120'>are</span> <span m='834300'>equal</span> <span m='835020'>to</span>
  <span m='835140'>the</span> <span m='835260'>Z</span> <span
  m='835530'>transform,</span> <span m='838050'>if</span> <span
  m='838350'>we</span> <span m='838500'>choose</span> <span m='838860'>z</span>
  <span m='839700'>equal</span> <span m='840120'>to</span> <span
  m='841360'>w</span> <span m='843010'>sub</span> <span
  m='843360'>capital</span> <span m='843920'>N</span> <span m='845410'>to</span>
  <span m='845850'>the</span> <span m='845940'>minus</span> <span
  m='846390'>k,</span> <span m='848100'>and</span> <span m='848250'>look</span>
  <span m='848490'>at</span> <span m='848610'>this</span> <span
  m='849330'>for</span> <span m='849480'>values</span> <span
  m='849990'>of</span> <span m='850110'>k</span> <span m='851930'>equal</span>
  <span m='852320'>to</span> <span m='852500'>0,</span> <span
  m='853340'>1,</span> <span m='854150'>up</span> <span
  m='854360'>through</span> <span m='855710'>capital</span> <span
  m='856160'>N</span> <span m='856310'>minus</span> <span m='856700'>1.</span>
  </p><p><span m='858116'>What</span> <span m='858590'>that</span> <span
  m='858830'>says</span> <span m='859130'>then,</span> <span
  m='859520'>is</span> <span m='859700'>that</span> <span m='859850'>the</span>
  <span m='860010'>discrete</span> <span m='860460'>Fourier</span> <span
  m='860720'>transform</span> <span m='862970'>corresponds</span> <span
  m='863810'>to</span> <span m='863930'>samples</span> <span
  m='864560'>of</span> <span m='864680'>the</span> <span m='864980'>Z</span>
  <span m='865460'>transform;</span> <span m='866270'>and</span> <span
  m='866390'>where</span> <span m='866630'>are</span> <span
  m='866780'>those</span> <span m='866990'>samples?</span> <span
  m='867740'>Well,</span> <span m='868490'>those</span> <span
  m='868670'>samples</span> <span m='869480'>are</span> <span
  m='869840'>on</span> <span m='870050'>the</span> <span m='870170'>unit</span>
  <span m='870470'>circle.</span> <span m='870950'>Because</span> <span
  m='871610'>the</span> <span m='871730'>magnitude</span> <span
  m='872570'>of</span> <span m='872750'>w</span> <span m='873410'>is</span>
  <span m='873590'>equal</span> <span m='873890'>to</span> <span
  m='874040'>1.</span> <span m='875930'>And</span> <span m='876170'>for</span>
  <span m='876380'>example,</span> <span m='877230'>if</span> <span
  m='877580'>we</span> <span m='877760'>chose</span> <span m='878180'>the</span>
  <span m='878300'>case</span> <span m='878660'>were</span> <span
  m='878810'>capital</span> <span m='879260'>N</span> <span
  m='879650'>was</span> <span m='879830'>equal</span> <span m='880130'>to</span>
  <span m='880280'>8,</span> <span m='881550'>then</span> <span
  m='881840'>we</span> <span m='882050'>would</span> <span
  m='882200'>find</span> <span m='882830'>that</span> <span
  m='883100'>the</span> <span m='883220'>discrete</span> <span
  m='884270'>Fourier</span> <span m='884660'>transform</span> <span
  m='885290'>coefficients</span> <span m='886640'>fall</span> <span
  m='887180'>at</span> <span m='887300'>points</span> <span m='887690'>on</span>
  <span m='887810'>the</span> <span m='887900'>unit</span> <span
  m='888170'>circle,</span> <span m='889370'>equally</span> <span
  m='889760'>spaced</span> <span m='890230'>in</span> <span
  m='890360'>angle</span> <span m='892250'>with</span> <span
  m='892700'>eight</span> <span m='893210'>points</span> <span
  m='894860'>around</span> <span m='895190'>the</span> <span
  m='895310'>unit</span> <span m='895550'>circle;</span> <span
  m='899070'>1,</span> <span m='899250'>2,</span> <span m='899490'>3,</span>
  <span m='899730'>4,</span> <span m='900000'>5,</span> <span
  m='900270'>6,</span> <span m='900510'>7,</span> <span m='900810'>8.</span>
  <span m='901080'>I</span> <span m='901140'>did</span> <span
  m='901320'>it</span> <span m='901380'>right.</span> </p><p><span
  m='902430'>So</span> <span m='903390'>these</span> <span m='903810'>are</span>
  <span m='903990'>equally-spaced</span> <span m='905160'>points</span> <span
  m='905670'>around</span> <span m='906000'>the</span> <span
  m='906090'>unit</span> <span m='906360'>circle.</span> <span
  m='907560'>For</span> <span m='907710'>capital</span> <span
  m='908190'>N</span> <span m='908430'>equal</span> <span m='908760'>to</span>
  <span m='908910'>8,</span> <span m='909740'>then</span> <span
  m='910300'>the</span> <span m='910440'>discrete</span> <span
  m='910860'>Fourier</span> <span m='911280'>transform</span> <span
  m='912540'>corresponds</span> <span m='913290'>to</span> <span
  m='913410'>sampling</span> <span m='914310'>the</span> <span
  m='914430'>Z</span> <span m='914640'>transform</span> <span
  m='916140'>at</span> <span m='916530'>these</span> <span
  m='916800'>eight</span> <span m='917040'>points.</span> <span
  m='918960'>And</span> <span m='919080'>then</span> <span m='919530'>the</span>
  <span m='919740'>only</span> <span m='920210'>effect</span> <span
  m='920550'>that</span> <span m='920760'>this</span> <span
  m='920940'>capital</span> <span m='921390'>R</span> <span
  m='921540'>sub</span> <span m='921820'>N</span> <span m='922170'>of</span>
  <span m='922320'>k</span> <span m='922650'>has</span> <span
  m='923640'>is</span> <span m='923910'>that</span> <span m='924210'>it</span>
  <span m='924330'>requires</span> <span m='925170'>that</span> <span
  m='925890'>we</span> <span m='926160'>interpret</span> <span
  m='926730'>this</span> <span m='927090'>as</span> <span m='927270'>a</span>
  <span m='927360'>finite</span> <span m='927840'>length</span> <span
  m='928620'>sequence,</span> <span m='929400'>the</span> <span
  m='929520'>set</span> <span m='929760'>of</span> <span m='930060'>eight</span>
  <span m='930270'>values,</span> <span m='931200'>rather</span> <span
  m='931560'>than</span> <span m='931710'>running</span> <span
  m='932010'>around,</span> <span m='932370'>and</span> <span
  m='932460'>around,</span> <span m='932820'>and</span> <span
  m='932910'>around</span> <span m='933180'>the</span> <span
  m='933270'>unit</span> <span m='933510'>circle</span> <span
  m='934020'>over</span> <span m='934320'>and</span> <span
  m='934410'>over</span> <span m='934710'>again.</span> </p><p><span
  m='937100'>So,</span> <span m='938110'>we</span> <span m='938260'>have</span>
  <span m='938470'>then</span> <span m='938680'>the</span> <span
  m='938770'>discrete</span> <span m='939025'>Fourier</span> <span
  m='939580'>transform.</span> <span m='941260'>We</span> <span
  m='941380'>have</span> <span m='941590'>the</span> <span
  m='941680'>notion</span> <span m='942430'>that</span> <span
  m='942610'>the</span> <span m='942700'>discrete</span> <span
  m='943090'>Fourier</span> <span m='943510'>transform</span> <span
  m='944830'>really</span> <span m='945190'>is</span> <span
  m='945310'>nothing</span> <span m='945670'>different.</span> <span
  m='946720'>It's</span> <span m='946930'>exactly</span> <span
  m='947320'>the</span> <span m='947410'>same</span> <span m='947770'>as</span>
  <span m='947860'>the</span> <span m='947950'>discrete</span> <span
  m='948340'>Fourier</span> <span m='948730'>series,</span> <span
  m='950020'>except</span> <span m='950410'>that</span> <span
  m='950530'>it's</span> <span m='950620'>one</span> <span
  m='950860'>period</span> <span m='951220'>of a</span> <span
  m='951370'>discrete</span> <span m='951760'>Fourier</span> <span
  m='952180'>series</span> <span m='952810'>extracted.</span> <span
  m='954220'>And</span> <span m='954370'>furthermore,</span> <span
  m='955180'>it</span> <span m='955300'>corresponds</span> <span
  m='956740'>to</span> <span m='956860'>sampling</span> <span
  m='958240'>the</span> <span m='958510'>Z</span> <span
  m='958780'>transform</span> <span m='960160'>at</span> <span
  m='960400'>equally-spaced</span> <span m='961150'>points</span> <span
  m='961810'>around</span> <span m='962110'>the</span> <span
  m='962200'>unit</span> <span m='962470'>circle.</span> <span
  m='964000'>Apparently</span> <span m='964630'>because</span> <span
  m='965050'>of</span> <span m='965140'>the</span> <span m='965230'>fact</span>
  <span m='965560'>that</span> <span m='965680'>the</span> <span
  m='965800'>sequence</span> <span m='966220'>is</span> <span
  m='966340'>finite</span> <span m='966760'>length,</span> <span
  m='967660'>from</span> <span m='967870'>that</span> <span
  m='968080'>set</span> <span m='968290'>of</span> <span
  m='968380'>samples</span> <span m='969580'>we're</span> <span
  m='969770'>able</span> <span m='970120'>to</span> <span m='970270'>get</span>
  <span m='970480'>back</span> <span m='971050'>exactly</span> <span
  m='972220'>the</span> <span m='972340'>sequence</span> <span
  m='972880'>x</span> <span m='973150'>of n.</span> </p><p><span
  m='974350'>That</span> <span m='974500'>isn't</span> <span
  m='975280'>obviously</span> <span m='975760'>true,</span> <span
  m='976030'>in</span> <span m='976150'>general.</span> <span
  m='976780'>If</span> <span m='976900'>we</span> <span m='977020'>had</span>
  <span m='977170'>an</span> <span m='977260'>arbitrary</span> <span
  m='977950'>x</span> <span m='978190'>of</span> <span m='978340'>n,</span>
  <span m='979150'>and</span> <span m='979270'>we</span> <span
  m='979390'>sampled</span> <span m='979900'>a</span> <span m='980020'>Z</span>
  <span m='980200'>transform</span> <span m='980830'>around</span> <span
  m='981100'>the</span> <span m='981190'>unit</span> <span
  m='981460'>circle,</span> <span m='982420'>in</span> <span
  m='982540'>general</span> <span m='982990'>we</span> <span
  m='983140'>wouldn't</span> <span m='983410'>be</span> <span
  m='983560'>able</span> <span m='983800'>to</span> <span m='983920'>get</span>
  <span m='984160'>x</span> <span m='984460'>of n</span> <span
  m='984700'>back</span> <span m='985000'>again.</span> <span
  m='986530'>But</span> <span m='986680'>if</span> <span m='986830'>x</span>
  <span m='987040'>of</span> <span m='987160'>n</span> <span
  m='987280'>is</span> <span m='987400'>a</span> <span m='987490'>finite</span>
  <span m='987910'>length,</span> <span m='988840'>then</span> <span
  m='989590'>we</span> <span m='989770'>are</span> <span m='990040'>able</span>
  <span m='990640'>to</span> <span m='990820'>obtain</span> <span
  m='991240'>x</span> <span m='991550'>of n</span> <span m='992500'>from</span>
  <span m='993100'>the</span> <span m='993190'>samples</span> <span
  m='994000'>of its</span> <span m='994290'>Z</span> <span
  m='994510'>transform.</span> </p><p><span m='997030'>OK.</span> <span
  m='997390'>Well,</span> <span m='997750'>I'd</span> <span
  m='997870'>like</span> <span m='998290'>now</span> <span m='998680'>to</span>
  <span m='999130'>look</span> <span m='999460'>at</span> <span
  m='999730'>some</span> <span m='1000000'>of</span> <span
  m='1000090'>the</span> <span m='1000180'>properties</span> <span
  m='1001020'>of</span> <span m='1001680'>the</span> <span
  m='1001780'>discrete</span> <span m='1002055'>Fourier</span> <span
  m='1002580'>transform.</span> <span m='1004190'>Again,</span> <span
  m='1005250'>there</span> <span m='1005580'>are</span> <span
  m='1005790'>lots</span> <span m='1006090'>of</span> <span
  m='1006180'>properties</span> <span m='1006870'>that</span> <span
  m='1006990'>we</span> <span m='1007110'>can</span> <span
  m='1007260'>talk</span> <span m='1007590'>about.</span> <span
  m='1008020'>I'll</span> <span m='1008190'>focus</span> <span
  m='1008610'>on</span> <span m='1008760'>a</span> <span m='1008850'>few,</span>
  <span m='1009900'>and</span> <span m='1010230'>primarily</span> <span
  m='1010860'>what</span> <span m='1011010'>I</span> <span
  m='1011100'>want</span> <span m='1011250'>to</span> <span
  m='1011340'>focus</span> <span m='1011820'>on</span> <span
  m='1012300'>is</span> <span m='1012810'>the</span> <span
  m='1012930'>difference</span> <span m='1014070'>between</span> <span
  m='1014460'>the</span> <span m='1014550'>properties</span> <span
  m='1015290'>for</span> <span m='1015390'>the</span> <span
  m='1015480'>discrete</span> <span m='1015870'>Fourier</span> <span
  m='1016290'>transform</span> <span m='1018000'>and</span> <span
  m='1018180'>the</span> <span m='1018270'>properties</span> <span
  m='1019350'>for</span> <span m='1019500'>the</span> <span
  m='1019620'>Fourier</span> <span m='1020040'>transform</span> <span
  m='1020940'>or</span> <span m='1021180'>the</span> <span m='1021300'>Z</span>
  <span m='1021480'>transform</span> <span m='1022680'>as</span> <span
  m='1023400'>we</span> <span m='1023670'>have</span> <span
  m='1023880'>been</span> <span m='1024000'>talking</span> <span
  m='1024420'>about</span> <span m='1024750'>them</span> <span
  m='1025079'>over</span> <span m='1025560'>the</span> <span
  m='1025650'>last</span> <span m='1025920'>several</span> <span
  m='1026250'>lectures.</span> </p><p><span m='1027660'>Well,</span> <span
  m='1028079'>let's</span> <span m='1028380'>look</span> <span
  m='1028720'>first</span> <span m='1028950'>of</span> <span
  m='1029099'>all</span> <span m='1029619'>at</span> <span
  m='1030510'>the</span> <span m='1031440'>shifting</span> <span
  m='1031950'>property.</span> <span m='1034560'>And</span> <span
  m='1035819'>let</span> <span m='1036000'>me</span> <span
  m='1036150'>stress</span> <span m='1036990'>that</span> <span
  m='1037319'>all</span> <span m='1037560'>of</span> <span
  m='1037650'>the</span> <span m='1037740'>properties,</span> <span
  m='1039119'>as</span> <span m='1039270'>we</span> <span m='1039390'>go</span>
  <span m='1039569'>through</span> <span m='1039869'>them,</span> <span
  m='1041069'>as</span> <span m='1041250'>we</span> <span
  m='1041369'>present</span> <span m='1041760'>them</span> <span
  m='1041880'>for</span> <span m='1042030'>the</span> <span
  m='1042119'>discrete</span> <span m='1042480'>Fourier</span> <span
  m='1042869'>transform,</span> <span m='1044220'>will</span> <span
  m='1044430'>relate</span> <span m='1045390'>to</span> <span
  m='1046470'>the</span> <span m='1047579'>corresponding</span> <span
  m='1048450'>property</span> <span m='1049440'>for</span> <span
  m='1049560'>the</span> <span m='1049680'>periodic</span> <span
  m='1050340'>equivalent</span> <span m='1051180'>of</span> <span
  m='1051330'>the</span> <span m='1051450'>finite</span> <span
  m='1051870'>length</span> <span m='1052080'>sequence.</span> <span
  m='1053100'>So</span> <span m='1053370'>when</span> <span
  m='1053600'>we</span> <span m='1053700'>want</span> <span
  m='1053880'>to</span> <span m='1053940'>ask</span> <span
  m='1054420'>what</span> <span m='1054690'>happens</span> <span
  m='1055080'>to</span> <span m='1055170'>the</span> <span
  m='1055920'>discrete</span> <span m='1056340'>Fourier</span> <span
  m='1056700'>transform</span> <span m='1057690'>when</span> <span
  m='1057910'>we</span> <span m='1058110'>do</span> <span
  m='1058230'>such</span> <span m='1058530'>and</span> <span
  m='1058620'>such</span> <span m='1058890'>to</span> <span
  m='1059010'>the</span> <span m='1059100'>sequence,</span> <span
  m='1060780'>the</span> <span m='1060900'>basic</span> <span
  m='1061380'>idea</span> <span m='1062250'>that</span> <span
  m='1062790'>basically</span> <span m='1063450'>what</span> <span
  m='1063600'>we</span> <span m='1063690'>want</span> <span
  m='1063870'>to</span> <span m='1063960'>ask</span> <span m='1064440'>is</span>
  <span m='1064620'>what</span> <span m='1064860'>happens</span> <span
  m='1065370'>to</span> <span m='1065460'>the</span> <span
  m='1065580'>Fourier</span> <span m='1065940'>series</span> <span
  m='1066330'>coefficients</span> <span m='1067740'>for</span> <span
  m='1068100'>the</span> <span m='1068220'>periodic</span> <span
  m='1068850'>equivalent</span> <span m='1069540'>of</span> <span
  m='1069690'>that</span> <span m='1069840'>finite</span> <span
  m='1070260'>length</span> <span m='1070470'>sequence.</span> </p><p><span
  m='1072390'>All</span> <span m='1072450'>right.</span> <span
  m='1072810'>Let's</span> <span m='1073530'>talk</span> <span
  m='1073830'>about</span> <span m='1074100'>the</span> <span
  m='1074190'>shifting</span> <span m='1074640'>property.</span> <span
  m='1076500'>We</span> <span m='1076650'>have</span> <span m='1077280'>a</span>
  <span m='1077340'>sequence,</span> <span m='1077820'>x</span> <span
  m='1078060'>of</span> <span m='1078210'>n.</span> <span m='1079560'>It</span>
  <span m='1079680'>has</span> <span m='1080160'>a</span> <span
  m='1080370'>discrete</span> <span m='1080790'>Fourier</span> <span
  m='1081180'>transform</span> <span m='1082080'>capital</span> <span
  m='1082560'>X</span> <span m='1082770'>of</span> <span m='1082910'>k.</span>
  <span m='1085020'>And</span> <span m='1085620'>then</span> <span
  m='1086100'>we</span> <span m='1086250'>have</span> <span
  m='1086430'>the</span> <span m='1086520'>periodic</span> <span
  m='1087090'>equivalent</span> <span m='1087960'>of</span> <span
  m='1088140'>x</span> <span m='1088380'>of</span> <span m='1088500'>n,</span>
  <span m='1088830'>x</span> <span m='1089100'>tilde</span> <span m='1089580'>of
  n.</span> <span m='1090630'>And</span> <span m='1090750'>it</span> <span
  m='1090900'>has</span> <span m='1091470'>a</span> <span
  m='1091770'>discrete</span> <span m='1092220'>Fourier</span> <span
  m='1092610'>series</span> <span m='1093360'>coefficients,</span> <span
  m='1095070'>which</span> <span m='1095490'>are</span> <span
  m='1095940'>the</span> <span m='1096060'>periodic</span> <span
  m='1097170'>extension</span> <span m='1098190'>of</span> <span
  m='1098940'>the</span> <span m='1099060'>discrete</span> <span
  m='1099450'>Fourier</span> <span m='1099870'>transform.</span> <span
  m='1102780'>Well,</span> <span m='1103320'>the</span> <span
  m='1103410'>shifting</span> <span m='1103890'>property</span> <span
  m='1104370'>that</span> <span m='1104490'>we</span> <span
  m='1104640'>want</span> <span m='1104820'>to</span> <span
  m='1104880'>introduce</span> <span m='1105450'>then</span> <span
  m='1106140'>corresponds</span> <span m='1107130'>to</span> <span
  m='1107250'>the</span> <span m='1107370'>finite</span> <span
  m='1107820'>length</span> <span m='1108030'>sequence</span> <span
  m='1109350'>which</span> <span m='1109530'>is</span> <span
  m='1109680'>implied</span> <span m='1110550'>by</span> <span
  m='1110760'>shifting</span> <span m='1111750'>the</span> <span
  m='1111870'>periodic</span> <span m='1112530'>sequence,</span> <span
  m='1113630'>x</span> <span m='1114220'>tilde</span> <span
  m='1114460'>of</span> <span m='1114640'>n.</span> </p><p><span
  m='1116770'>We</span> <span m='1116820'>know</span> <span
  m='1117390'>that</span> <span m='1117630'>if</span> <span
  m='1117810'>we</span> <span m='1117960'>shift</span> <span
  m='1119540'>the</span> <span m='1119630'>periodic</span> <span
  m='1120230'>sequence,</span> <span m='1120920'>x</span> <span
  m='1121190'>tilde</span> <span m='1121650'>of</span> <span
  m='1121910'>n</span> <span m='1122570'>plus</span> <span m='1122900'>m,</span>
  <span m='1124970'>the</span> <span m='1125330'>Fourier</span> <span
  m='1126620'>series</span> <span m='1127130'>coefficients</span> <span
  m='1127850'>that</span> <span m='1127970'>we</span> <span
  m='1128150'>get</span> <span m='1129020'>are</span> <span m='1129680'>x</span>
  <span m='1130040'>tilde</span> <span m='1130370'>of</span> <span
  m='1130610'>k</span> <span m='1131720'>multiplied</span> <span
  m='1132680'>by</span> <span m='1132900'>a</span> <span
  m='1132920'>complex</span> <span m='1133520'>exponential</span> <span
  m='1134390'>w</span> <span m='1135000'>sub</span> <span
  m='1135170'>capital</span> <span m='1135680'>N</span> <span
  m='1136010'>to</span> <span m='1136370'>the</span> <span
  m='1136490'>minus</span> <span m='1136970'>km.</span> <span
  m='1140270'>So</span> <span m='1140870'>the</span> <span
  m='1140960'>shifting</span> <span m='1141440'>property</span> <span
  m='1142010'>that</span> <span m='1142130'>we</span> <span
  m='1142280'>want</span> <span m='1142460'>to</span> <span
  m='1142520'>introduce</span> <span m='1143120'>then</span> <span
  m='1143720'>for</span> <span m='1143930'>the</span> <span
  m='1144020'>discrete</span> <span m='1144380'>Fourier</span> <span
  m='1144800'>transform,</span> <span m='1147410'>corresponds</span> <span
  m='1148760'>to</span> <span m='1149090'>extracting</span> <span
  m='1150440'>shifting</span> <span m='1151050'>x of</span> <span
  m='1151345'>n</span> <span m='1151640'>in</span> <span m='1151760'>such</span>
  <span m='1152060'>a</span> <span m='1152150'>way</span> <span
  m='1152450'>that</span> <span m='1152570'>it</span> <span
  m='1152630'>corresponds</span> <span m='1153440'>to</span> <span
  m='1153590'>extracting</span> <span m='1154820'>one</span> <span
  m='1155120'>period</span> <span m='1156170'>of</span> <span
  m='1156740'>the</span> <span m='1156860'>shifted</span> <span
  m='1158090'>periodic</span> <span m='1158720'>sequence,</span> <span
  m='1159620'>x</span> <span m='1159890'>tilde</span> <span
  m='1160140'>of</span> <span m='1160310'>n.</span> </p><p><span
  m='1161780'>If</span> <span m='1161960'>we</span> <span m='1162110'>do</span>
  <span m='1162320'>that,</span> <span m='1163490'>if</span> <span
  m='1163730'>we</span> <span m='1165020'>extract</span> <span
  m='1165500'>one</span> <span m='1165740'>period</span> <span
  m='1166490'>of</span> <span m='1166850'>x1</span> <span
  m='1167330'>tilde</span> <span m='1167590'>of</span> <span
  m='1167820'>n</span> <span m='1168140'>to</span> <span m='1168290'>get</span>
  <span m='1168440'>a</span> <span m='1168500'>finite</span> <span
  m='1168890'>length</span> <span m='1169100'>sequence</span> <span
  m='1169640'>back,</span> <span m='1170960'>then</span> <span
  m='1172220'>we</span> <span m='1172370'>get</span> <span m='1173540'>a</span>
  <span m='1173690'>discrete</span> <span m='1174050'>Fourier</span> <span
  m='1174800'>transform,</span> <span m='1176130'>which</span> <span
  m='1176210'>corresponds</span> <span m='1176840'>to</span> <span
  m='1176990'>extracting</span> <span m='1177590'>one</span> <span
  m='1177830'>period</span> <span m='1178370'>of</span> <span
  m='1178550'>this</span> <span m='1178790'>periodic</span> <span
  m='1179420'>sequence.</span> <span m='1180930'>And</span> <span
  m='1181100'>that</span> <span m='1181400'>then</span> <span
  m='1181730'>is</span> <span m='1181880'>simply</span> <span
  m='1182960'>the</span> <span m='1183620'>original</span> <span
  m='1184160'>discrete</span> <span m='1184520'>Fourier</span> <span
  m='1184880'>transform</span> <span m='1185660'>capital</span> <span
  m='1186140'>X</span> <span m='1186350'>of</span> <span m='1186440'>k</span>
  <span m='1187310'>multiplied</span> <span m='1187910'>again</span> <span
  m='1188330'>by</span> <span m='1188600'>w</span> <span m='1189380'>sub</span>
  <span m='1189560'>capital</span> <span m='1190040'>N</span> <span
  m='1190460'>to</span> <span m='1190580'>the</span> <span
  m='1190700'>minus</span> <span m='1191030'>km.</span> </p><p><span
  m='1192800'>Now</span> <span m='1192950'>this</span> <span
  m='1193100'>shifting</span> <span m='1193910'>that</span> <span
  m='1194060'>we're</span> <span m='1194210'>talking</span> <span
  m='1194660'>about</span> <span m='1195080'>is</span> <span
  m='1195230'>a</span> <span m='1195260'>little</span> <span
  m='1195500'>different</span> <span m='1196700'>than</span> <span
  m='1197300'>the</span> <span m='1197420'>kind</span> <span
  m='1197660'>of</span> <span m='1197750'>shifting</span> <span
  m='1198200'>that</span> <span m='1198290'>we've</span> <span
  m='1198500'>been</span> <span m='1198650'>doing</span> <span
  m='1199670'>normally</span> <span m='1200450'>in</span> <span
  m='1200990'>the</span> <span m='1201080'>Fourier</span> <span
  m='1201530'>transform</span> <span m='1202160'>and</span> <span
  m='1202280'>Z</span> <span m='1202460'>transform.</span> <span
  m='1203540'>And</span> <span m='1203640'>it</span> <span
  m='1203750'>has</span> <span m='1204020'>to</span> <span
  m='1204170'>be.</span> <span m='1204890'>Because</span> <span
  m='1205250'>we're</span> <span m='1205370'>talking</span> <span
  m='1205790'>about</span> <span m='1206510'>a</span> <span
  m='1206570'>sequence</span> <span m='1207140'>that's</span> <span
  m='1207320'>a</span> <span m='1207380'>finite</span> <span
  m='1207860'>length.</span> <span m='1209330'>That</span> <span
  m='1209510'>is</span> <span m='1209750'>it's</span> <span m='1209870'>0</span>
  <span m='1210260'>outside</span> <span m='1210650'>the</span> <span
  m='1210770'>range,</span> <span m='1210980'>0</span> <span
  m='1211340'>to</span> <span m='1211430'>capital</span> <span
  m='1211880'>N</span> <span m='1212000'>minus</span> <span
  m='1212390'>1.</span> <span m='1214050'>And</span> <span m='1214940'>if</span>
  <span m='1215150'>we</span> <span m='1215420'>just</span> <span
  m='1215660'>simply</span> <span m='1216080'>shift</span> <span
  m='1216680'>that</span> <span m='1216860'>sequence</span> <span
  m='1217370'>linearly,</span> <span m='1218780'>then</span> <span
  m='1219020'>we're</span> <span m='1219170'>going</span> <span
  m='1219290'>to</span> <span m='1219350'>end</span> <span m='1219590'>up</span>
  <span m='1219740'>with</span> <span m='1219860'>a</span> <span
  m='1219920'>sequence</span> <span m='1220520'>that</span> <span
  m='1220850'>no</span> <span m='1221060'>longer</span> <span
  m='1221570'>is</span> <span m='1221720'>0</span> <span
  m='1222800'>outside</span> <span m='1223280'>the</span> <span
  m='1223370'>range</span> <span m='1223610'>0</span> <span
  m='1223940'>to</span> <span m='1224060'>capital</span> <span
  m='1224510'>N</span> <span m='1224630'>minus</span> <span
  m='1225020'>1.</span> <span m='1225780'>So</span> <span
  m='1226040'>there's</span> <span m='1226250'>a</span> <span
  m='1226310'>slightly</span> <span m='1226790'>different</span> <span
  m='1227150'>kind</span> <span m='1227420'>of</span> <span
  m='1227510'>shifting</span> <span m='1228230'>that</span> <span
  m='1228380'>we're</span> <span m='1228500'>talking</span> <span
  m='1228980'>about.</span> <span m='1229910'>It's</span> <span
  m='1230060'>referred</span> <span m='1230450'>to</span> <span
  m='1230780'>as</span> <span m='1230960'>a</span> <span
  m='1231050'>circular</span> <span m='1231590'>shift.</span> <span
  m='1232710'>and</span> <span m='1233150'>I'd</span> <span
  m='1233360'>like</span> <span m='1233870'>to</span> <span
  m='1234290'>illustrate</span> <span m='1235130'>what</span> <span
  m='1235610'>that</span> <span m='1235790'>shifting</span> <span
  m='1236270'>corresponds</span> <span m='1237110'>to</span> <span
  m='1237800'>by</span> <span m='1237980'>referring</span> <span
  m='1238460'>to</span> <span m='1238610'>one</span> <span m='1238760'>of</span>
  <span m='1238820'>the</span> <span m='1238980'>view</span> <span
  m='1239190'>graphs.</span> </p><p><span m='1245900'>Here</span> <span
  m='1246380'>I</span> <span m='1246560'>have</span> <span m='1247190'>a</span>
  <span m='1247250'>sequence,</span> <span m='1248180'>x</span> <span
  m='1248420'>of</span> <span m='1248540'>n,</span> <span
  m='1249140'>which</span> <span m='1249320'>is</span> <span
  m='1249440'>a</span> <span m='1249530'>finite</span> <span
  m='1249980'>length.</span> <span m='1251240'>So</span> <span
  m='1251750'>it's</span> <span m='1251960'>nonzero</span> <span
  m='1252740'>only</span> <span m='1253040'>in</span> <span
  m='1253130'>the</span> <span m='1253220'>region</span> <span
  m='1254180'>of</span> <span m='1254750'>the</span> <span
  m='1255200'>blue</span> <span m='1255830'>values.</span> <span
  m='1257870'>And</span> <span m='1259220'>to</span> <span
  m='1259610'>generate</span> <span m='1260150'>the</span> <span
  m='1260240'>shifted,</span> <span m='1261090'>quote,</span> <span
  m='1261470'>"shifted"</span> <span m='1262220'>version</span> <span
  m='1262760'>of</span> <span m='1262940'>x</span> <span m='1263180'>of
  n,</span> <span m='1264470'>we</span> <span m='1264620'>first</span> <span
  m='1265250'>generated</span> <span m='1265850'>the</span> <span
  m='1265940'>periodic</span> <span m='1266570'>sequence,</span> <span
  m='1267410'>x</span> <span m='1267640'>tilde</span> <span
  m='1267940'>of</span> <span m='1268190'>n.</span> <span m='1269750'>So</span>
  <span m='1269960'>this</span> <span m='1270170'>is</span> <span
  m='1270260'>the</span> <span m='1270380'>periodic</span> <span
  m='1271460'>replica</span> <span m='1272120'>or</span> <span
  m='1272300'>equivalent</span> <span m='1272990'>of</span> <span
  m='1273260'>this</span> <span m='1273440'>finite</span> <span
  m='1273860'>length</span> <span m='1274070'>sequence.</span> <span
  m='1275270'>So</span> <span m='1275450'>we</span> <span
  m='1275540'>simply</span> <span m='1275930'>have</span> <span
  m='1276110'>this</span> <span m='1276320'>period</span> <span
  m='1276800'>repeated</span> <span m='1277250'>over</span> <span
  m='1277520'>here,</span> <span m='1277820'>repeated</span> <span
  m='1278270'>here,</span> <span m='1278570'>repeated</span> <span
  m='1279020'>there,</span> <span m='1279260'>et</span> <span
  m='1279535'>cetera.</span> <span m='1280700'>It</span> <span
  m='1280880'>was</span> <span m='1281180'>this</span> <span
  m='1281420'>sequence</span> <span m='1282560'>that</span> <span
  m='1282740'>we</span> <span m='1282920'>shift.</span> <span
  m='1284540'>So</span> <span m='1284840'>for</span> <span
  m='1285020'>example,</span> <span m='1285810'>if</span> <span
  m='1285980'>we</span> <span m='1286250'>shifted</span> <span
  m='1286700'>to</span> <span m='1286820'>the</span> <span
  m='1286940'>left</span> <span m='1288080'>by</span> <span
  m='1288560'>two</span> <span m='1288860'>values,</span> <span
  m='1291000'>we</span> <span m='1291020'>then</span> <span
  m='1291260'>have</span> <span m='1291950'>this</span> <span
  m='1292490'>periodic</span> <span m='1293030'>sequence</span> <span
  m='1294170'>shifted</span> <span m='1294710'>to</span> <span
  m='1294830'>the</span> <span m='1294950'>left</span> <span
  m='1295370'>by</span> <span m='1295550'>two</span> <span
  m='1295790'>values.</span> <span m='1297530'>But</span> <span
  m='1298250'>to</span> <span m='1298820'>recover,</span> <span
  m='1300200'>to</span> <span m='1300350'>extract</span> <span
  m='1300860'>one</span> <span m='1301070'>period</span> <span
  m='1301790'>again</span> <span m='1302210'>in</span> <span
  m='1302330'>the</span> <span m='1302420'>range</span> <span
  m='1302720'>0</span> <span m='1303230'>to</span> <span
  m='1303410'>capital</span> <span m='1303860'>N</span> <span
  m='1304010'>minus</span> <span m='1304400'>1,</span> <span
  m='1305480'>we</span> <span m='1305630'>want</span> <span
  m='1305900'>to</span> <span m='1306080'>extract</span> <span
  m='1307430'>this</span> <span m='1308060'>period</span> <span
  m='1309200'>of</span> <span m='1309830'>this</span> <span
  m='1310070'>periodic</span> <span m='1310700'>sequence.</span> <span
  m='1311570'>That's</span> <span m='1311810'>what</span> <span
  m='1311990'>the</span> <span m='1312080'>function</span> <span
  m='1313400'>capital</span> <span m='1313880'>R</span> <span
  m='1314120'>sub</span> <span m='1314900'>capital</span> <span
  m='1315350'>N</span> <span m='1315500'>of n</span> <span
  m='1316220'>does</span> <span m='1316490'>for</span> <span
  m='1316720'>us.</span> <span m='1317480'>And</span> <span
  m='1317960'>the</span> <span m='1318080'>result</span> <span
  m='1318500'>then</span> <span m='1319880'>is</span> <span
  m='1320870'>this</span> <span m='1321380'>one</span> <span
  m='1321680'>period</span> <span m='1322280'>extracted,</span> <span
  m='1323640'>and</span> <span m='1324020'>the</span> <span
  m='1324110'>rest</span> <span m='1324410'>of</span> <span
  m='1324500'>the</span> <span m='1324620'>sequence,</span> <span
  m='1325070'>0.</span> </p><p><span m='1326550'>Now,</span> <span
  m='1327200'>we</span> <span m='1327350'>could</span> <span
  m='1327560'>of</span> <span m='1327680'>course,</span> <span
  m='1328250'>when</span> <span m='1328430'>we</span> <span
  m='1328520'>go</span> <span m='1328700'>through</span> <span
  m='1328970'>this</span> <span m='1329090'>shifting,</span> <span
  m='1330350'>carry</span> <span m='1330740'>ourselves</span> <span
  m='1331580'>through</span> <span m='1331820'>all</span> <span
  m='1332000'>of</span> <span m='1332090'>these</span> <span
  m='1332240'>steps.</span> <span m='1333350'>But</span> <span
  m='1333860'>there's</span> <span m='1334340'>a</span> <span
  m='1334430'>more</span> <span m='1334610'>straightforward</span> <span
  m='1335480'>way</span> <span m='1336020'>to</span> <span
  m='1336170'>look</span> <span m='1336500'>at</span> <span
  m='1336680'>how</span> <span m='1336890'>you</span> <span
  m='1337100'>get</span> <span m='1337370'>this</span> <span
  m='1337550'>sequence</span> <span m='1338570'>directly</span> <span
  m='1339080'>from</span> <span m='1339290'>this</span> <span
  m='1339500'>one.</span> <span m='1341030'>You</span> <span
  m='1341150'>can</span> <span m='1341330'>see</span> <span
  m='1342290'>that</span> <span m='1343250'>we</span> <span
  m='1343430'>could</span> <span m='1343700'>have</span> <span
  m='1343910'>interpreted</span> <span m='1345620'>the</span> <span
  m='1345890'>change</span> <span m='1346370'>from</span> <span
  m='1346550'>here</span> <span m='1347090'>to</span> <span
  m='1347240'>here,</span> <span m='1349220'>either</span> <span
  m='1349820'>by</span> <span m='1350030'>linearly</span> <span
  m='1350630'>shifting</span> <span m='1351140'>this</span> <span
  m='1351320'>sequence</span> <span m='1352850'>or</span> <span
  m='1353360'>by</span> <span m='1353570'>taking</span> <span
  m='1354080'>each</span> <span m='1354380'>one</span> <span
  m='1354560'>of</span> <span m='1354620'>the</span> <span
  m='1354740'>periods</span> <span m='1355610'>in</span> <span
  m='1355730'>this</span> <span m='1355850'>sequence</span> <span
  m='1357080'>and</span> <span m='1357200'>circularly</span> <span
  m='1357920'>shifting.</span> <span m='1359600'>As</span> <span
  m='1359990'>this</span> <span m='1360140'>shifts</span> <span
  m='1360530'>to</span> <span m='1360650'>the</span> <span
  m='1360770'>left,</span> <span m='1361610'>taking</span> <span
  m='1362000'>points</span> <span m='1362450'>as</span> <span
  m='1362600'>they</span> <span m='1362750'>drop</span> <span
  m='1363140'>out</span> <span m='1363290'>of</span> <span
  m='1363380'>this</span> <span m='1363590'>period</span> <span
  m='1364490'>and</span> <span m='1364610'>recirculating</span> <span
  m='1365510'>them</span> <span m='1365900'>around</span> <span
  m='1366260'>to</span> <span m='1366380'>the</span> <span
  m='1366470'>beginning</span> <span m='1366860'>of</span> <span
  m='1366950'>the</span> <span m='1367040'>period,</span> <span
  m='1367790'>or</span> <span m='1368150'>to the</span> <span
  m='1368320'>side</span> <span m='1368660'>of</span> <span
  m='1368750'>the</span> <span m='1368840'>period.</span> </p><p><span
  m='1370170'>Well,</span> <span m='1370460'>you</span> <span
  m='1370610'>can</span> <span m='1370760'>see</span> <span
  m='1371120'>that</span> <span m='1371570'>that's</span> <span
  m='1371900'>in</span> <span m='1372200'>essence,</span> <span
  m='1372930'>what</span> <span m='1373010'>we</span> <span
  m='1373110'>got</span> <span m='1373400'>here.</span> <span
  m='1374780'>And</span> <span m='1374930'>in</span> <span
  m='1374990'>fact,</span> <span m='1375300'>it's</span> <span
  m='1375470'>in</span> <span m='1375590'>essence,</span> <span
  m='1376020'>what</span> <span m='1376070'>we</span> <span
  m='1376190'>get</span> <span m='1376430'>here.</span> <span
  m='1377550'>This</span> <span m='1378020'>corresponds</span> <span
  m='1379490'>not</span> <span m='1379700'>to</span> <span m='1379880'>a</span>
  <span m='1379970'>linear</span> <span m='1380390'>shift</span> <span
  m='1381230'>of</span> <span m='1381410'>x</span> <span m='1381670'>of</span>
  <span m='1381930'>n,</span> <span m='1383450'>but</span> <span
  m='1384110'>to</span> <span m='1384710'>a</span> <span
  m='1385370'>circular</span> <span m='1386000'>shift</span> <span
  m='1386600'>of</span> <span m='1386750'>x</span> <span m='1387080'>of
  n.</span> <span m='1388670'>As</span> <span m='1388910'>we</span> <span
  m='1389060'>shift</span> <span m='1389750'>this</span> <span
  m='1389960'>sequence</span> <span m='1390680'>to</span> <span
  m='1390860'>the</span> <span m='1390980'>left</span> <span
  m='1391580'>by</span> <span m='1391760'>two</span> <span
  m='1391970'>values,</span> <span m='1393350'>instead</span> <span
  m='1393770'>of</span> <span m='1394400'>just</span> <span
  m='1394580'>simply</span> <span m='1394940'>having</span> <span
  m='1395510'>these</span> <span m='1395690'>points</span> <span
  m='1396650'>drop</span> <span m='1397010'>off</span> <span
  m='1397970'>the</span> <span m='1398150'>end</span> <span
  m='1398810'>of</span> <span m='1399230'>this</span> <span
  m='1399410'>period</span> <span m='1399860'>from</span> <span
  m='1400010'>0</span> <span m='1400370'>to</span> <span m='1400490'>n</span>
  <span m='1400640'>minus</span> <span m='1401060'>1,</span> <span
  m='1401930'>we</span> <span m='1402080'>wrap</span> <span
  m='1402410'>them</span> <span m='1402560'>around</span> <span
  m='1403280'>to</span> <span m='1403400'>the</span> <span
  m='1403550'>other</span> <span m='1403730'>side</span> <span
  m='1404670'>so</span> <span m='1404780'>that</span> <span
  m='1405380'>they</span> <span m='1405530'>come</span> <span
  m='1405800'>in</span> <span m='1406460'>over</span> <span
  m='1406760'>here</span> <span m='1407570'>instead</span> <span
  m='1407960'>of</span> <span m='1408230'>wrapping</span> <span
  m='1408620'>around</span> <span m='1409280'>there.</span> </p><p><span
  m='1410840'>Now</span> <span m='1410990'>one</span> <span
  m='1411200'>way</span> <span m='1411320'>to</span> <span
  m='1411410'>look</span> <span m='1411680'>at</span> <span
  m='1411800'>this</span> <span m='1412760'>is</span> <span
  m='1413390'>to</span> <span m='1413540'>think</span> <span
  m='1413840'>of</span> <span m='1413930'>x</span> <span m='1414150'>of</span>
  <span m='1414290'>n,</span> <span m='1415490'>again</span> <span
  m='1415910'>as</span> <span m='1416060'>we've</span> <span
  m='1416210'>been</span> <span m='1416300'>trying</span> <span
  m='1416660'>to</span> <span m='1416780'>do,</span> <span
  m='1417530'>wrapped</span> <span m='1417890'>around</span> <span
  m='1418160'>the</span> <span m='1418250'>circumference</span> <span
  m='1418970'>of</span> <span m='1419060'>a</span> <span
  m='1419120'>cylinder.</span> <span m='1421280'>And</span> <span
  m='1421760'>what</span> <span m='1421970'>we've</span> <span
  m='1422180'>done</span> <span m='1422750'>in</span> <span
  m='1422930'>the</span> <span m='1423020'>kind</span> <span
  m='1423260'>of</span> <span m='1423350'>shift</span> <span
  m='1423650'>that</span> <span m='1423770'>we're</span> <span
  m='1423890'>talking</span> <span m='1424340'>about</span> <span
  m='1424640'>here,</span> <span m='1425870'>is</span> <span
  m='1426260'>just</span> <span m='1426470'>simply</span> <span
  m='1427400'>rotated</span> <span m='1428000'>the</span> <span
  m='1428120'>cylinder</span> <span m='1428870'>by</span> <span
  m='1429080'>two</span> <span m='1429320'>points,</span> <span
  m='1430550'>rather</span> <span m='1430880'>than</span> <span
  m='1431060'>the</span> <span m='1431180'>usual</span> <span
  m='1431690'>kind</span> <span m='1431930'>of</span> <span
  m='1432020'>linear</span> <span m='1432380'>shift</span> <span
  m='1433100'>where</span> <span m='1433280'>we</span> <span
  m='1433400'>have</span> <span m='1433580'>the</span> <span
  m='1433670'>sequence</span> <span m='1434090'>stretched</span> <span
  m='1434570'>out</span> <span m='1434840'>in</span> <span m='1434960'>a</span>
  <span m='1435020'>straight</span> <span m='1435380'>line</span> <span
  m='1436220'>and</span> <span m='1436370'>we</span> <span
  m='1436490'>shift</span> <span m='1436790'>the</span> <span
  m='1436880'>sequence</span> <span m='1437660'>linearly.</span> <span
  m='1438980'>Here</span> <span m='1439220'>we</span> <span
  m='1439370'>have</span> <span m='1439520'>a</span> <span
  m='1439580'>circular</span> <span m='1440090'>shift.</span> <span
  m='1440960'>Think</span> <span m='1441200'>of</span> <span
  m='1441290'>the</span> <span m='1441380'>sequence</span> <span
  m='1441950'>wrapped</span> <span m='1442310'>around</span> <span
  m='1442590'>the</span> <span m='1442670'>circumference</span> <span
  m='1443360'>of</span> <span m='1443450'>a</span> <span
  m='1443510'>cylinder,</span> <span m='1444680'>and</span> <span
  m='1444830'>the</span> <span m='1444920'>cylinder</span> <span
  m='1445460'>just</span> <span m='1445670'>rotated</span> <span
  m='1446780'>by</span> <span m='1446930'>two</span> <span
  m='1447140'>points</span> <span m='1448100'>so</span> <span
  m='1448310'>that</span> <span m='1448730'>the</span> <span
  m='1448850'>result</span> <span m='1449330'>is</span> <span
  m='1449960'>that</span> <span m='1451040'>the</span> <span
  m='1451130'>two</span> <span m='1451310'>points</span> <span
  m='1451820'>that</span> <span m='1451940'>are</span> <span
  m='1452030'>shifted</span> <span m='1452660'>out</span> <span
  m='1453290'>of</span> <span m='1453470'>this</span> <span
  m='1453650'>window</span> <span m='1454040'>between</span> <span
  m='1454430'>0</span> <span m='1454790'>and</span> <span m='1454930'>n</span>
  <span m='1455090'>minus</span> <span m='1455450'>1</span> <span
  m='1455855'>get</span> <span m='1456260'>shifted</span> <span
  m='1456710'>in</span> <span m='1457070'>from</span> <span
  m='1457280'>the</span> <span m='1457400'>other</span> <span
  m='1457580'>side.</span> </p><p><span m='1459290'>Notationally</span> <span
  m='1460040'>a</span> <span m='1460120'>way</span> <span m='1460250'>to</span>
  <span m='1460370'>say</span> <span m='1460640'>that</span> <span
  m='1461510'>is</span> <span m='1462020'>as</span> <span
  m='1462500'>I've</span> <span m='1462680'>done</span> <span
  m='1462950'>here,</span> <span m='1463880'>really</span> <span
  m='1464480'>what</span> <span m='1465230'>this</span> <span
  m='1465410'>expression</span> <span m='1465950'>corresponds</span> <span
  m='1466730'>to</span> <span m='1467120'>is</span> <span
  m='1467450'>that</span> <span m='1469010'>we</span> <span
  m='1469130'>started</span> <span m='1469550'>with</span> <span
  m='1469700'>x</span> <span m='1469910'>of</span> <span m='1470050'>n.</span>
  <span m='1471500'>We</span> <span m='1471650'>formed</span> <span
  m='1471920'>the</span> <span m='1472010'>periodic</span> <span
  m='1472880'>replica</span> <span m='1473450'>of</span> <span
  m='1473570'>that</span> <span m='1473960'>using</span> <span
  m='1474380'>the</span> <span m='1474470'>modular</span> <span
  m='1474920'>notation</span> <span m='1475520'>that</span> <span
  m='1475640'>we</span> <span m='1475790'>introduced</span> <span
  m='1476270'>at</span> <span m='1476360'>the</span> <span
  m='1476450'>beginning</span> <span m='1476810'>of</span> <span
  m='1476900'>the</span> <span m='1476990'>lecture.</span> <span
  m='1478400'>Shift</span> <span m='1478850'>that</span> <span
  m='1479450'>by</span> <span m='1479630'>two</span> <span
  m='1479840'>points,</span> <span m='1480980'>and</span> <span
  m='1481160'>then</span> <span m='1481520'>extract</span> <span
  m='1482510'>a</span> <span m='1482570'>single</span> <span
  m='1482930'>period.</span> <span m='1483960'>So</span> <span
  m='1484070'>this</span> <span m='1484250'>is</span> <span m='1484370'>a</span>
  <span m='1484460'>long</span> <span m='1485510'>way--</span> <span
  m='1486020'>well</span> <span m='1486290'>I</span> <span
  m='1486350'>guess</span> <span m='1486560'>it's</span> <span
  m='1486710'>really</span> <span m='1486950'>a</span> <span
  m='1487010'>short</span> <span m='1487340'>way</span> <span
  m='1487760'>of</span> <span m='1487880'>going</span> <span
  m='1488180'>through</span> <span m='1488390'>all</span> <span
  m='1488540'>these</span> <span m='1488720'>steps.</span> <span
  m='1489860'>But</span> <span m='1490340'>it's</span> <span
  m='1490730'>the</span> <span m='1490880'>idea</span> <span
  m='1491510'>and</span> <span m='1491690'>not</span> <span
  m='1492440'>the</span> <span m='1493880'>mathematical</span> <span
  m='1494600'>formalism</span> <span m='1495290'>that's</span> <span
  m='1495470'>important.</span> <span m='1496940'>Think</span> <span
  m='1497240'>of</span> <span m='1497360'>this</span> <span
  m='1498020'>as</span> <span m='1498470'>a</span> <span
  m='1498680'>circular</span> <span m='1499310'>shift</span> <span
  m='1500180'>of</span> <span m='1500720'>this</span> <span
  m='1500900'>finite</span> <span m='1501320'>length</span> <span
  m='1501560'>sequence</span> <span m='1502220'>inside</span> <span
  m='1502670'>the</span> <span m='1502820'>interval</span> <span
  m='1503540'>0</span> <span m='1503990'>to</span> <span
  m='1504110'>capital</span> <span m='1504560'>N</span> <span
  m='1504680'>minus</span> <span m='1505070'>1.</span> </p><p><span
  m='1507470'>OK.</span> <span m='1507890'>So</span> <span
  m='1508670'>this</span> <span m='1508970'>then</span> <span
  m='1509480'>is</span> <span m='1511300'>our</span> <span
  m='1511430'>shifting</span> <span m='1512180'>property.</span> <span
  m='1515000'>I've</span> <span m='1515520'>rewritten</span> <span
  m='1516060'>it</span> <span m='1517170'>in</span> <span m='1518820'>a</span>
  <span m='1518910'>slightly</span> <span m='1519330'>different</span> <span
  m='1519660'>way</span> <span m='1519930'>here,</span> <span
  m='1520740'>corresponding</span> <span m='1521460'>to</span> <span
  m='1521580'>using</span> <span m='1521910'>the</span> <span
  m='1522030'>modular</span> <span m='1522990'>sort</span> <span
  m='1523230'>of</span> <span m='1523320'>notation.</span> <span
  m='1524490'>That</span> <span m='1524670'>is</span> <span
  m='1525060'>the</span> <span m='1525210'>statement</span> <span
  m='1525720'>is</span> <span m='1526380'>that</span> <span m='1526500'>a</span>
  <span m='1526560'>circular</span> <span m='1527040'>shift</span> <span
  m='1528180'>of</span> <span m='1528330'>x</span> <span m='1528600'>of</span>
  <span m='1528720'>n--</span> <span m='1528960'>and</span> <span
  m='1529080'>that's</span> <span m='1529260'>what</span> <span
  m='1529380'>all</span> <span m='1529560'>this</span> <span
  m='1529800'>means</span> <span m='1530160'>is</span> <span
  m='1530250'>just</span> <span m='1530430'>simply</span> <span
  m='1530760'>a</span> <span m='1530790'>circular</span> <span
  m='1531240'>shift--</span> <span m='1533130'>has</span> <span
  m='1534120'>as</span> <span m='1534720'>its</span> <span
  m='1534930'>discrete</span> <span m='1535350'>Fourier</span> <span
  m='1535770'>transform</span> <span m='1536910'>the</span> <span
  m='1537030'>original</span> <span m='1537480'>discrete</span> <span
  m='1537870'>Fourier</span> <span m='1538290'>transform</span> <span
  m='1539430'>multiplied</span> <span m='1540390'>by</span> <span
  m='1540600'>this</span> <span m='1540750'>complex</span> <span
  m='1541320'>exponential.</span> <span m='1543390'>Because</span> <span
  m='1543750'>of</span> <span m='1543840'>the</span> <span
  m='1543930'>fact</span> <span m='1544500'>that</span> <span
  m='1544650'>we've</span> <span m='1544830'>interpreted</span> <span
  m='1545430'>the</span> <span m='1545520'>discrete</span> <span
  m='1545910'>Fourier</span> <span m='1546300'>transform</span> <span
  m='1547770'>as</span> <span m='1548280'>a</span> <span
  m='1548370'>finite</span> <span m='1548820'>length</span> <span
  m='1549060'>sequence,</span> <span m='1550770'>we</span> <span
  m='1550920'>have</span> <span m='1551130'>again</span> <span
  m='1551430'>a</span> <span m='1551490'>duality</span> <span
  m='1552120'>between</span> <span m='1552510'>the</span> <span
  m='1552600'>time</span> <span m='1552900'>domain</span> <span
  m='1553440'>and</span> <span m='1553560'>the</span> <span
  m='1553650'>frequency</span> <span m='1554160'>domain.</span> <span
  m='1555330'>In</span> <span m='1555450'>particular,</span> <span
  m='1556690'>if</span> <span m='1556770'>we</span> <span
  m='1556920'>apply</span> <span m='1557670'>a</span> <span
  m='1557730'>circular</span> <span m='1558300'>shift</span> <span
  m='1559260'>to</span> <span m='1559740'>the</span> <span
  m='1559860'>discrete</span> <span m='1560250'>Fourier</span> <span
  m='1560640'>transform</span> <span m='1561690'>values,</span> <span
  m='1563930'>the</span> <span m='1564320'>resulting</span> <span
  m='1564890'>finite</span> <span m='1565310'>length</span> <span
  m='1565550'>sequence</span> <span m='1566240'>is</span> <span
  m='1566480'>the</span> <span m='1566630'>original</span> <span
  m='1567230'>finite</span> <span m='1567650'>length</span> <span
  m='1567860'>sequence</span> <span m='1568790'>multiplied</span> <span
  m='1569540'>by</span> <span m='1569750'>a</span> <span
  m='1569780'>complex</span> <span m='1570350'>exponential.</span> </p><p><span
  m='1572310'>Well,</span> <span m='1572600'>the</span> <span
  m='1572690'>details</span> <span m='1573230'>of</span> <span
  m='1573320'>the</span> <span m='1573470'>algebra</span> <span
  m='1574310'>involved</span> <span m='1574760'>in</span> <span
  m='1574850'>working</span> <span m='1575210'>this</span> <span
  m='1575420'>out</span> <span m='1576140'>aren't</span> <span
  m='1576500'>important</span> <span m='1577100'>right</span> <span
  m='1577370'>now.</span> <span m='1577760'>You'll</span> <span
  m='1577940'>have</span> <span m='1578300'>plenty</span> <span
  m='1578600'>of</span> <span m='1578720'>opportunity</span> <span
  m='1579950'>to</span> <span m='1581210'>look</span> <span
  m='1581480'>at</span> <span m='1581600'>those</span> <span
  m='1582470'>at</span> <span m='1582650'>your</span> <span
  m='1582770'>leisure</span> <span m='1583790'>in</span> <span
  m='1583900'>the</span> <span m='1584070'>text,</span> <span
  m='1584780'>also</span> <span m='1585260'>to</span> <span
  m='1585410'>work</span> <span m='1585680'>some</span> <span
  m='1585920'>of</span> <span m='1586100'>this</span> <span
  m='1586810'>in</span> <span m='1586900'>the</span> <span
  m='1587000'>study</span> <span m='1587360'>guide.</span> <span
  m='1588300'>The</span> <span m='1588400'>important</span> <span
  m='1589100'>concept</span> <span m='1590030'>right</span> <span
  m='1590300'>now,</span> <span m='1590750'>the</span> <span
  m='1590930'>important</span> <span m='1591380'>thing</span> <span
  m='1591650'>to</span> <span m='1591950'>cement,</span> <span
  m='1593180'>is</span> <span m='1593360'>the</span> <span
  m='1593510'>notion</span> <span m='1594260'>of</span> <span
  m='1594740'>a</span> <span m='1594800'>circular</span> <span
  m='1595370'>shift</span> <span m='1596420'>of</span> <span
  m='1596780'>a</span> <span m='1596870'>finite</span> <span
  m='1597320'>length</span> <span m='1597530'>sequence.</span> <span
  m='1598910'>And</span> <span m='1599060'>think</span> <span
  m='1599330'>of</span> <span m='1599420'>it</span> <span m='1599630'>as</span>
  <span m='1600290'>the</span> <span m='1600380'>finite</span> <span
  m='1600740'>length</span> <span m='1600950'>sequence</span> <span
  m='1601640'>as</span> <span m='1601850'>it</span> <span
  m='1601940'>shifts,</span> <span m='1603170'>points</span> <span
  m='1603590'>that</span> <span m='1603710'>come</span> <span
  m='1603980'>outside</span> <span m='1604730'>the</span> <span
  m='1604910'>interval</span> <span m='1605270'>0</span> <span
  m='1605570'>to</span> <span m='1605660'>capital</span> <span
  m='1606110'>N</span> <span m='1606230'>minus</span> <span
  m='1606560'>1,</span> <span m='1607170'>wrap</span> <span
  m='1607470'>around</span> <span m='1608030'>and</span> <span
  m='1608180'>come</span> <span m='1608420'>in</span> <span
  m='1608540'>on</span> <span m='1608660'>the</span> <span
  m='1608780'>other</span> <span m='1608990'>side.</span> </p><p><span
  m='1611990'>Now</span> <span m='1612350'>we</span> <span
  m='1612530'>also</span> <span m='1612890'>have</span> <span
  m='1613490'>symmetry</span> <span m='1614060'>properties</span> <span
  m='1615080'>for</span> <span m='1615860'>the</span> <span
  m='1616370'>discrete</span> <span m='1616760'>Fourier</span> <span
  m='1617150'>transform,</span> <span m='1618030'>which</span> <span
  m='1618170'>are</span> <span m='1618230'>basically</span> <span
  m='1618830'>a</span> <span m='1618890'>consequence</span> <span
  m='1620240'>of</span> <span m='1620360'>the</span> <span
  m='1620450'>symmetry</span> <span m='1620900'>properties</span> <span
  m='1621800'>for</span> <span m='1622190'>the</span> <span
  m='1622310'>discrete</span> <span m='1622700'>Fourier</span> <span
  m='1623090'>series.</span> <span m='1625100'>I'll</span> <span
  m='1625190'>remind</span> <span m='1625640'>you</span> <span
  m='1625790'>that</span> <span m='1626180'>for</span> <span
  m='1626330'>the</span> <span m='1626450'>discrete</span> <span
  m='1626810'>Fourier</span> <span m='1627230'>series,</span> <span
  m='1629150'>for</span> <span m='1629810'>a</span> <span
  m='1629870'>periodic</span> <span m='1630470'>sequence</span> <span
  m='1630980'>that's</span> <span m='1631160'>real,</span> <span
  m='1632570'>we</span> <span m='1632690'>had</span> <span
  m='1633890'>the</span> <span m='1634160'>symmetry</span> <span
  m='1634700'>property</span> <span m='1635240'>that</span> <span
  m='1635390'>said</span> <span m='1636020'>that</span> <span
  m='1636140'>the</span> <span m='1636260'>real</span> <span
  m='1636530'>part</span> <span m='1636980'>of</span> <span
  m='1637100'>the</span> <span m='1637190'>Fourier</span> <span
  m='1637580'>series</span> <span m='1638000'>coefficients</span> <span
  m='1638840'>are</span> <span m='1639020'>even.</span> <span
  m='1640280'>And</span> <span m='1640850'>we</span> <span
  m='1641030'>wrote</span> <span m='1641240'>that</span> <span
  m='1641480'>in</span> <span m='1641570'>a</span> <span
  m='1641630'>couple</span> <span m='1641960'>of</span> <span
  m='1642080'>ways.</span> <span m='1642540'>One</span> <span
  m='1642650'>of</span> <span m='1642770'>which</span> <span
  m='1643220'>was</span> <span m='1644090'>to</span> <span
  m='1644210'>state</span> <span m='1644750'>that</span> <span
  m='1644930'>x</span> <span m='1645140'>sub</span> <span m='1645260'>R</span>
  <span m='1645500'>of</span> <span m='1645590'>k</span> <span
  m='1646070'>is</span> <span m='1646280'>equal</span> <span
  m='1646700'>to</span> <span m='1647170'>x sub</span> <span
  m='1647360'>R</span> <span m='1647840'>of</span> <span
  m='1648530'>capital</span> <span m='1648980'>N</span> <span
  m='1649100'>minus</span> <span m='1649520'>k.</span> <span
  m='1651320'>And</span> <span m='1651800'>the</span> <span
  m='1651920'>imaginary</span> <span m='1652550'>part</span> <span
  m='1653030'>of</span> <span m='1653180'>the</span> <span
  m='1653270'>Fourier</span> <span m='1653600'>series</span> <span
  m='1653990'>coefficients</span> <span m='1655370'>are</span> <span
  m='1655580'>odd.</span> <span m='1656300'>That</span> <span
  m='1656480'>is</span> <span m='1657110'>they're</span> <span m='1657350'>equal
  to</span> <span m='1657830'>minus</span> <span m='1659060'>x</span> <span
  m='1659330'>sub</span> <span m='1659600'>I</span> <span m='1659870'>of</span>
  <span m='1660020'>capital</span> <span m='1660500'>N</span> <span
  m='1660620'>minus</span> <span m='1661010'>k.</span> </p><p><span
  m='1662780'>Well,</span> <span m='1663380'>the</span> <span
  m='1664160'>discrete</span> <span m='1664550'>Fourier</span> <span
  m='1664940'>transform</span> <span m='1668265'>is</span> <span
  m='1668710'>one</span> <span m='1668930'>period</span> <span
  m='1669530'>of</span> <span m='1669680'>the</span> <span
  m='1669770'>discrete</span> <span m='1670100'>Fourier</span> <span
  m='1670520'>series.</span> <span m='1671240'>And</span> <span
  m='1671390'>consequently,</span> <span m='1672650'>this</span> <span
  m='1672890'>implies</span> <span m='1673460'>the</span> <span
  m='1673550'>same</span> <span m='1673880'>type</span> <span
  m='1674210'>of</span> <span m='1674300'>symmetry</span> <span
  m='1674780'>properties</span> <span m='1675920'>for</span> <span
  m='1676520'>the</span> <span m='1676610'>discrete</span> <span
  m='1677000'>Fourier</span> <span m='1677420'>transform,</span> <span
  m='1678740'>keeping</span> <span m='1679070'>in</span> <span
  m='1679190'>mind</span> <span m='1679460'>again</span> <span
  m='1680090'>that</span> <span m='1680240'>we</span> <span
  m='1680390'>want</span> <span m='1680570'>to</span> <span
  m='1680630'>relate</span> <span m='1680990'>these</span> <span
  m='1681200'>properties</span> <span m='1681790'>just</span> <span
  m='1682040'>to</span> <span m='1682160'>a</span> <span
  m='1682220'>single</span> <span m='1682580'>period.</span> <span
  m='1684510'>So</span> <span m='1685130'>we</span> <span
  m='1685280'>have</span> <span m='1685470'>the</span> <span
  m='1685550'>discrete</span> <span m='1685940'>Fourier</span> <span
  m='1686300'>transform.</span> <span m='1687320'>Again,</span> <span
  m='1687680'>we'll</span> <span m='1687830'>assume</span> <span
  m='1688160'>that</span> <span m='1688280'>x of</span> <span
  m='1688520'>n</span> <span m='1688760'>is</span> <span
  m='1688880'>real.</span> <span m='1691050'>And</span> <span
  m='1691200'>the</span> <span m='1691290'>statement</span> <span
  m='1691890'>then,</span> <span m='1693000'>implied</span> <span
  m='1693720'>by</span> <span m='1693990'>simply</span> <span
  m='1694530'>extracting</span> <span m='1695220'>one</span> <span
  m='1695520'>period</span> <span m='1696090'>out</span> <span
  m='1696240'>of</span> <span m='1696330'>the</span> <span
  m='1696420'>discrete</span> <span m='1696810'>Fourier</span> <span
  m='1697230'>series,</span> <span m='1698640'>is</span> <span
  m='1699060'>that</span> <span m='1699720'>the</span> <span
  m='1700410'>real</span> <span m='1700710'>part</span> <span
  m='1701130'>of</span> <span m='1701250'>the</span> <span
  m='1701340'>discrete</span> <span m='1701700'>Fourier</span> <span
  m='1702030'>transform</span> <span m='1702660'>coefficients</span> <span
  m='1704280'>are</span> <span m='1704490'>equal</span> <span
  m='1704970'>to</span> <span m='1706200'>one</span> <span
  m='1706500'>period</span> <span m='1707400'>extracted</span> <span
  m='1708180'>out</span> <span m='1708420'>of</span> <span
  m='1709350'>the</span> <span m='1709920'>periodic</span> <span
  m='1711030'>sequence,</span> <span m='1711690'>which</span> <span
  m='1711960'>is</span> <span m='1712230'>x</span> <span m='1712530'>sub</span>
  <span m='1712620'>R</span> <span m='1713640'>of</span> <span
  m='1714210'>N</span> <span m='1714420'>minus</span> <span
  m='1714840'>k,</span> <span m='1715860'>repeated</span> <span
  m='1716580'>over</span> <span m='1716880'>and</span> <span
  m='1716970'>over</span> <span m='1717270'>again.</span> <span
  m='1718170'>Periodically</span> <span m='1718950'>that's</span> <span
  m='1719190'>what</span> <span m='1719310'>the</span> <span
  m='1719430'>modular</span> <span m='1719850'>notation</span> <span
  m='1720480'>did</span> <span m='1720630'>for</span> <span
  m='1720930'>us,</span> <span m='1721410'>one</span> <span
  m='1721620'>period</span> <span m='1722040'>extracted</span> <span
  m='1722640'>out</span> <span m='1722820'>of</span> <span
  m='1722910'>that</span> <span m='1723300'>that's</span> <span
  m='1723510'>what</span> <span m='1723660'>this</span> <span
  m='1723840'>rectangular</span> <span m='1724440'>window</span> <span
  m='1724800'>does</span> <span m='1725070'>for</span> <span
  m='1725310'>us.</span> </p><p><span m='1726750'>And</span> <span
  m='1727110'>we</span> <span m='1727260'>have</span> <span m='1727410'>a</span>
  <span m='1727470'>similar</span> <span m='1728520'>type</span> <span
  m='1728940'>of</span> <span m='1729060'>statement</span> <span
  m='1729840'>about</span> <span m='1730290'>the</span> <span
  m='1730410'>imaginary</span> <span m='1731040'>part.</span> <span
  m='1731880'>This</span> <span m='1732090'>is</span> <span
  m='1732210'>basically</span> <span m='1732780'>a</span> <span
  m='1732840'>statement</span> <span m='1733320'>that</span> <span
  m='1733470'>says</span> <span m='1734160'>that</span> <span
  m='1735180'>the</span> <span m='1736230'>real</span> <span
  m='1736530'>part</span> <span m='1736980'>is</span> <span
  m='1737190'>even,</span> <span m='1737940'>if</span> <span
  m='1738090'>we</span> <span m='1738210'>interpret</span> <span
  m='1738630'>even</span> <span m='1738960'>correctly.</span> <span
  m='1740640'>And</span> <span m='1741270'>the</span> <span
  m='1741390'>imaginary</span> <span m='1742020'>part</span> <span
  m='1742440'>is</span> <span m='1742680'>odd,</span> <span
  m='1745420'>if</span> <span m='1745630'>we</span> <span
  m='1745750'>interpret</span> <span m='1746290'>odd</span> <span
  m='1746560'>correctly.</span> <span m='1747850'>And</span> <span
  m='1749260'>in</span> <span m='1749380'>particular,</span> <span
  m='1749950'>the</span> <span m='1750070'>interpretation</span> <span
  m='1750880'>is</span> <span m='1750970'>a</span> <span
  m='1751060'>little</span> <span m='1751360'>different</span> <span
  m='1752200'>than</span> <span m='1752710'>the</span> <span
  m='1752830'>way</span> <span m='1753040'>we've</span> <span
  m='1753250'>been</span> <span m='1753370'>talking</span> <span
  m='1753790'>about</span> <span m='1754210'>even</span> <span
  m='1754510'>and</span> <span m='1754660'>odd</span> <span
  m='1755230'>sequences.</span> <span m='1756850'>Well,</span> <span
  m='1757540'>to</span> <span m='1757780'>see</span> <span
  m='1758230'>what</span> <span m='1758470'>this</span> <span
  m='1758710'>expression</span> <span m='1759310'>means,</span> <span
  m='1759730'>it</span> <span m='1759940'>looks</span> <span
  m='1760180'>a</span> <span m='1760240'>little</span> <span
  m='1760540'>involved.</span> <span m='1761050'>It's</span> <span
  m='1761170'>got</span> <span m='1761380'>some</span> <span
  m='1761500'>modular</span> <span m='1762190'>things</span> <span
  m='1762610'>in</span> <span m='1762730'>it,</span> <span
  m='1762940'>and</span> <span m='1763180'>multiplying</span> <span
  m='1763810'>by</span> <span m='1763960'>a</span> <span
  m='1764020'>rectangular</span> <span m='1764650'>window.</span> <span
  m='1765790'>But</span> <span m='1766360'>that's</span> <span
  m='1766840'>mainly</span> <span m='1767710'>notational</span> <span
  m='1768340'>formalism.</span> <span m='1769570'>And</span> <span
  m='1769840'>what</span> <span m='1770050'>these</span> <span
  m='1770260'>two</span> <span m='1770470'>expressions</span> <span
  m='1771040'>are</span> <span m='1771100'>saying</span> <span
  m='1771670'>are</span> <span m='1771970'>very</span> <span
  m='1772270'>straightforward.</span> </p><p><span m='1774570'>Let's</span>
  <span m='1774710'>look,</span> <span m='1775140'>for</span> <span
  m='1775250'>example,</span> <span m='1776190'>at</span> <span
  m='1776990'>what</span> <span m='1777530'>this</span> <span
  m='1777770'>implies</span> <span m='1779460'>for</span> <span
  m='1779840'>k</span> <span m='1780290'>equal</span> <span
  m='1780590'>to</span> <span m='1780710'>0</span> <span m='1781760'>or</span>
  <span m='1782330'>for</span> <span m='1782690'>k</span> <span
  m='1783260'>equal</span> <span m='1783740'>to</span> <span
  m='1783920'>1.</span> <span m='1785930'>For</span> <span m='1786080'>k</span>
  <span m='1786335'>equal</span> <span m='1786590'>to</span> <span
  m='1786720'>0,</span> <span m='1787880'>we</span> <span
  m='1788060'>have</span> <span m='1788540'>x</span> <span
  m='1788740'>sub</span> <span m='1788930'>R</span> <span m='1789410'>of</span>
  <span m='1790280'>capital</span> <span m='1790760'>N</span> <span
  m='1791330'>modulo</span> <span m='1791900'>capital</span> <span
  m='1792390'>N,</span> <span m='1793580'>or</span> <span
  m='1794150'>equivalently</span> <span m='1794810'>up</span> <span
  m='1794960'>here</span> <span m='1795140'>we</span> <span
  m='1795290'>have</span> <span m='1795980'>capital</span> <span
  m='1796370'>X</span> <span m='1796520'>sub</span> <span m='1796880'>R
  of</span> <span m='1796970'>0</span> <span m='1798140'>is</span> <span
  m='1798850'>X</span> <span m='1799260'>sub</span> <span m='1799670'>R
  of</span> <span m='1800090'>N</span> <span m='1800330'>minus</span> <span
  m='1800630'>0</span> <span m='1800960'>modulo</span> <span
  m='1801500'>capital</span> <span m='1802040'>N</span> <span
  m='1803690'>times</span> <span m='1804110'>R</span> <span
  m='1804350'>sub</span> <span m='1804740'>N of</span> <span
  m='1804830'>0.</span> <span m='1806310'>Well,</span> <span
  m='1806630'>R</span> <span m='1806870'>sub N</span> <span
  m='1807200'>of</span> <span m='1807370'>0,</span> <span
  m='1809000'>according</span> <span m='1809330'>to</span> <span
  m='1809450'>the</span> <span m='1809540'>way</span> <span
  m='1809720'>that</span> <span m='1809840'>we've</span> <span
  m='1810050'>defined</span> <span m='1810860'>this</span> <span
  m='1811040'>rectangular</span> <span m='1811640'>window,</span> <span
  m='1812840'>is</span> <span m='1812990'>unity.</span> <span
  m='1814490'>And</span> <span m='1815000'>what</span> <span
  m='1815180'>is</span> <span m='1815330'>all</span> <span
  m='1815510'>this</span> <span m='1815720'>equal</span> <span
  m='1816050'>to?</span> </p><p><span m='1818400'>Well,</span> <span
  m='1818730'>it's</span> <span m='1818940'>capital</span> <span
  m='1819450'>N</span> <span m='1820220'>modulo</span> <span
  m='1821880'>capital</span> <span m='1822360'>N,</span> <span
  m='1823110'>which</span> <span m='1823290'>is</span> <span
  m='1823350'>0.</span> <span m='1824470'>In</span> <span
  m='1824570'>other</span> <span m='1824670'>words,</span> <span
  m='1824830'>this</span> <span m='1824910'>argument</span> <span
  m='1825420'>at</span> <span m='1825480'>0,</span> <span
  m='1826530'>this</span> <span m='1827040'>simply</span> <span
  m='1828240'>is</span> <span m='1828360'>a</span> <span
  m='1828450'>trivial</span> <span m='1828870'>statement</span> <span
  m='1829680'>that</span> <span m='1829860'>says</span> <span
  m='1830220'>that</span> <span m='1830370'>X</span> <span
  m='1830520'>Sub</span> <span m='1830910'>R of</span> <span
  m='1831000'>0</span> <span m='1831660'>is</span> <span
  m='1831810'>equal</span> <span m='1832140'>to</span> <span
  m='1832470'>X</span> <span m='1832710'>sub</span> <span m='1832800'>R
  of</span> <span m='1833130'>0.</span> <span m='1834180'>And</span> <span
  m='1834840'>that</span> <span m='1835020'>really</span> <span
  m='1835320'>doesn't</span> <span m='1836070'>tell</span> <span
  m='1836250'>us</span> <span m='1836400'>too</span> <span
  m='1836580'>much.</span> <span m='1838770'>For</span> <span m='1838950'>k
  equal</span> <span m='1839400'>to</span> <span m='1839550'>1,</span> <span
  m='1839880'>we</span> <span m='1840020'>add</span> <span
  m='1840140'>that</span> <span m='1840240'>X</span> <span
  m='1840460'>sub</span> <span m='1840600'>R of</span> <span
  m='1840870'>1</span> <span m='1841500'>is</span> <span m='1841920'>X</span>
  <span m='1842190'>sub</span> <span m='1842280'>R</span> <span
  m='1842790'>of</span> <span m='1843540'>capital</span> <span
  m='1843960'>N</span> <span m='1844080'>minus</span> <span m='1844530'>1</span>
  <span m='1845100'>modulo</span> <span m='1845550'>capital</span> <span
  m='1845810'>N</span> <span m='1846480'>times</span> <span m='1846840'>R</span>
  <span m='1847170'>sub</span> <span m='1847320'>capital</span> <span
  m='1847770'>N</span> <span m='1847890'>of</span> <span m='1848010'>1.</span>
  <span m='1849340'>This</span> <span m='1849450'>again</span> <span
  m='1850140'>is</span> <span m='1850830'>unity.</span> <span
  m='1853200'>And</span> <span m='1853470'>since</span> <span
  m='1853740'>capital</span> <span m='1854190'>N</span> <span
  m='1854310'>minus</span> <span m='1854700'>1</span> <span
  m='1855030'>is</span> <span m='1855210'>in</span> <span m='1855330'>the</span>
  <span m='1855420'>range</span> <span m='1855810'>0</span> <span
  m='1856200'>to</span> <span m='1856350'>capital</span> <span
  m='1856830'>N</span> <span m='1856980'>minus</span> <span m='1857400'>1</span>
  <span m='1858120'>that</span> <span m='1858360'>taken,</span> <span
  m='1858750'>modulo</span> <span m='1859320'>N</span> <span
  m='1860220'>is</span> <span m='1860490'>just</span> <span
  m='1860700'>simply</span> <span m='1861180'>X</span> <span
  m='1861440'>sub</span> <span m='1861790'>R</span> <span m='1862710'>of</span>
  <span m='1865050'>capital</span> <span m='1865530'>N</span> <span
  m='1866100'>minus</span> <span m='1866490'>1.</span> </p><p><span
  m='1868480'>So</span> <span m='1868680'>what</span> <span
  m='1868890'>this</span> <span m='1869040'>says</span> <span
  m='1869430'>is</span> <span m='1869640'>X</span> <span m='1869930'>sub</span>
  <span m='1869980'>R</span> <span m='1870130'>of</span> <span
  m='1870320'>0</span> <span m='1871200'>is</span> <span
  m='1871380'>equal</span> <span m='1871590'>to</span> <span
  m='1871650'>X</span> <span m='1871860'>sub R</span> <span
  m='1872190'>of</span> <span m='1872280'>0.</span> <span m='1873350'>So
  as</span> <span m='1873560'>X</span> <span m='1873780'>sub</span> <span
  m='1873860'>R of</span> <span m='1874150'>1</span> <span m='1874440'>is</span>
  <span m='1874560'>equal</span> <span m='1874860'>to</span> <span
  m='1875070'>X</span> <span m='1875330'>sub</span> <span m='1875440'>R</span>
  <span m='1875730'>of</span> <span m='1875910'>N</span> <span
  m='1876160'>minus</span> <span m='1876630'>1.</span> <span
  m='1877780'>And</span> <span m='1877800'>if</span> <span m='1877890'>we</span>
  <span m='1878400'>repeated</span> <span m='1878880'>this,</span> <span
  m='1879150'>we'd</span> <span m='1879270'>find</span> <span
  m='1879660'>X</span> <span m='1879880'>sub</span> <span m='1879930'>R</span>
  <span m='1880180'>of</span> <span m='1880260'>2</span> <span
  m='1880500'>equal</span> <span m='1880770'>to</span> <span
  m='1880860'>X</span> <span m='1881160'>sub</span> <span m='1881445'>R</span>
  <span m='1881730'>of N</span> <span m='1881880'>minus</span> <span
  m='1882360'>2.</span> <span m='1883140'>And</span> <span
  m='1883290'>that's</span> <span m='1883830'>in</span> <span
  m='1883950'>the</span> <span m='1884040'>context</span> <span
  m='1884670'>of</span> <span m='1884760'>the</span> <span
  m='1884880'>discrete</span> <span m='1885240'>Fourier</span> <span
  m='1885630'>transform,</span> <span m='1886890'>what</span> <span
  m='1887100'>we</span> <span m='1887280'>mean</span> <span
  m='1887730'>by</span> <span m='1888720'>the</span> <span
  m='1888990'>Fourier</span> <span m='1889380'>transform</span> <span
  m='1890070'>being</span> <span m='1890360'>even.</span> <span
  m='1891750'>So</span> <span m='1892530'>as</span> <span m='1892710'>an</span>
  <span m='1892830'>example,</span> <span m='1893770'>here</span> <span
  m='1893850'>we</span> <span m='1894030'>have</span> <span
  m='1894300'>what</span> <span m='1894480'>can</span> <span
  m='1894690'>correspond</span> <span m='1895740'>to</span> <span
  m='1896280'>a</span> <span m='1896850'>real</span> <span
  m='1897150'>part.</span> <span m='1899250'>And</span> <span
  m='1900150'>we</span> <span m='1900360'>have</span> <span m='1901470'>X</span>
  <span m='1901700'>sub</span> <span m='1902100'>R of</span> <span
  m='1902230'>k.</span> <span m='1904400'>We</span> <span
  m='1904560'>have</span> <span m='1904770'>X</span> <span
  m='1904980'>sub</span> <span m='1905170'>R of</span> <span
  m='1905370'>1</span> <span m='1905820'>equal</span> <span
  m='1906270'>to</span> <span m='1906620'>X</span> <span m='1906920'>sub</span>
  <span m='1907020'>R</span> <span m='1907470'>of</span> <span
  m='1908130'>capital</span> <span m='1908610'>N</span> <span
  m='1908730'>minus</span> <span m='1909180'>1.</span> <span
  m='1910665'>Well,</span> <span m='1911160'>that</span> <span
  m='1911310'>says</span> <span m='1911640'>that</span> <span
  m='1912390'>this</span> <span m='1912630'>value</span> <span
  m='1913890'>is</span> <span m='1914100'>equal</span> <span
  m='1914670'>to</span> <span m='1917220'>that</span> <span
  m='1917850'>value.</span> <span m='1919110'>X sub</span> <span
  m='1919485'>R</span> <span m='1919860'>of</span> <span m='1920040'>2</span>
  <span m='1920430'>equal</span> <span m='1920820'>to</span> <span m='1921060'>X
  sub</span> <span m='1921350'>R</span> <span m='1921610'>of</span> <span
  m='1921700'>N</span> <span m='1921870'>minus</span> <span
  m='1922320'>2.</span> <span m='1923280'>That</span> <span
  m='1923460'>says</span> <span m='1923760'>that</span> <span
  m='1923940'>this</span> <span m='1924180'>value</span> <span
  m='1925440'>is</span> <span m='1925620'>equal</span> <span
  m='1926100'>to</span> <span m='1927750'>that</span> <span
  m='1927990'>value.</span> <span m='1931090'>And</span> <span
  m='1931660'>likewise</span> <span m='1932920'>this</span> <span
  m='1933130'>value</span> <span m='1933580'>is</span> <span
  m='1933700'>equal</span> <span m='1933940'>to</span> <span
  m='1934060'>this</span> <span m='1934300'>one.</span> <span
  m='1934480'>This</span> <span m='1934660'>one</span> <span
  m='1934780'>is</span> <span m='1934900'>equal</span> <span
  m='1935110'>to</span> <span m='1935230'>that</span> <span
  m='1935440'>one,</span> <span m='1935620'>et</span> <span
  m='1936010'>cetera.</span> </p><p><span m='1937720'>In</span> <span
  m='1937810'>a</span> <span m='1937870'>similar</span> <span
  m='1938290'>way,</span> <span m='1938700'>we</span> <span
  m='1938890'>have</span> <span m='1939070'>a</span> <span
  m='1939100'>statement</span> <span m='1940000'>that</span> <span
  m='1940930'>tells</span> <span m='1941290'>us</span> <span
  m='1941680'>that</span> <span m='1942850'>the</span> <span
  m='1943330'>imaginary</span> <span m='1944020'>part</span> <span
  m='1944740'>is</span> <span m='1944950'>odd</span> <span m='1945640'>in</span>
  <span m='1945760'>exactly</span> <span m='1946270'>the</span> <span
  m='1946360'>same</span> <span m='1946660'>sense.</span> <span
  m='1947390'>In</span> <span m='1947440'>other</span> <span
  m='1947620'>words</span> <span m='1948480'>that</span> <span
  m='1948670'>there's</span> <span m='1948880'>a</span> <span
  m='1948970'>symmetry</span> <span m='1950140'>as</span> <span
  m='1950590'>we</span> <span m='1950800'>look</span> <span
  m='1952240'>at</span> <span m='1952390'>the</span> <span
  m='1952480'>imaginary</span> <span m='1953050'>part</span> <span
  m='1953800'>coming</span> <span m='1954130'>in</span> <span
  m='1954460'>from</span> <span m='1954670'>both</span> <span
  m='1954880'>sides</span> <span m='1955330'>of</span> <span
  m='1955420'>the</span> <span m='1955510'>sequence.</span> <span
  m='1956770'>Incidentally,</span> <span m='1957340'>I've</span> <span
  m='1957490'>indicated</span> <span m='1958060'>here</span> <span
  m='1958600'>by</span> <span m='1958840'>a</span> <span
  m='1958900'>dotted</span> <span m='1959290'>line</span> <span
  m='1960970'>what</span> <span m='1961420'>would</span> <span
  m='1961570'>correspond</span> <span m='1962950'>to</span> <span
  m='1963310'>the</span> <span m='1963430'>periodic</span> <span
  m='1964120'>extension</span> <span m='1965530'>of</span> <span
  m='1966070'>this</span> <span m='1966210'>set</span> <span
  m='1966460'>of</span> <span m='1966580'>DFT</span> <span
  m='1967150'>values.</span> <span m='1968360'>In</span> <span
  m='1968460'>other</span> <span m='1968500'>words,</span> <span
  m='1968960'>this</span> <span m='1969400'>would</span> <span
  m='1969580'>be</span> <span m='1969730'>this</span> <span
  m='1969970'>one</span> <span m='1970150'>repeated</span> <span
  m='1970600'>over</span> <span m='1970960'>again.</span> <span
  m='1971500'>And</span> <span m='1972280'>if</span> <span m='1972430'>we</span>
  <span m='1972520'>were</span> <span m='1972640'>thinking</span> <span
  m='1972910'>of</span> <span m='1973000'>the</span> <span
  m='1973090'>discrete</span> <span m='1973420'>Fourier</span> <span
  m='1973840'>series,</span> <span m='1974710'>this</span> <span
  m='1974920'>would</span> <span m='1975040'>just</span> <span
  m='1975430'>be</span> <span m='1976630'>periodic</span> <span
  m='1977260'>replicas.</span> <span m='1978280'>Although</span> <span
  m='1978580'>in</span> <span m='1978700'>fact,</span> <span
  m='1979060'>the</span> <span m='1979150'>discrete</span> <span
  m='1979540'>Fourier</span> <span m='1979930'>transform,</span> <span
  m='1981220'>since</span> <span m='1981520'>we've</span> <span
  m='1981820'>interpreted</span> <span m='1982360'>it</span> <span
  m='1982570'>as</span> <span m='1982750'>a</span> <span
  m='1982810'>finite</span> <span m='1983230'>length</span> <span
  m='1983440'>sequence,</span> <span m='1984520'>the</span> <span
  m='1984610'>discrete</span> <span m='1984940'>Fourier</span> <span
  m='1985300'>transform</span> <span m='1986530'>would</span> <span
  m='1986680'>have</span> <span m='1986860'>0</span> <span
  m='1987670'>values</span> <span m='1988300'>on</span> <span
  m='1988450'>both</span> <span m='1988750'>ends</span> <span
  m='1988990'>of</span> <span m='1989080'>this.</span> </p><p><span
  m='1991210'>All</span> <span m='1991300'>right.</span> <span
  m='1991510'>So</span> <span m='1991840'>the</span> <span
  m='1991990'>corresponding</span> <span m='1992680'>symmetry</span> <span
  m='1993550'>for</span> <span m='1993850'>the</span> <span
  m='1993970'>imaginary</span> <span m='1994600'>part</span> <span
  m='1995440'>says</span> <span m='1996280'>that</span> <span
  m='1998170'>if</span> <span m='1998560'>we</span> <span
  m='1998770'>look</span> <span m='1999070'>at</span> <span
  m='2001080'>the</span> <span m='2001170'>imaginary</span> <span
  m='2001710'>part</span> <span m='2002040'>at</span> <span m='2002130'>n</span>
  <span m='2002476'>equals</span> <span m='2002822'>1,</span> <span
  m='2005180'>then</span> <span m='2005720'>that's</span> <span
  m='2005990'>equal</span> <span m='2006230'>to</span> <span
  m='2006350'>minus</span> <span m='2007010'>the</span> <span
  m='2007100'>imaginary</span> <span m='2007700'>part</span> <span
  m='2008180'>at</span> <span m='2008690'>capital</span> <span
  m='2009170'>N</span> <span m='2009290'>minus</span> <span
  m='2009740'>1.</span> <span m='2011480'>If</span> <span m='2011580'>we</span>
  <span m='2011680'>look</span> <span m='2011720'>at</span> <span
  m='2011780'>the</span> <span m='2011870'>imaginary</span> <span
  m='2012350'>part at</span> <span m='2012660'>n</span> <span
  m='2012810'>equals</span> <span m='2013170'>2,</span> <span
  m='2014810'>then</span> <span m='2015650'>that's</span> <span
  m='2015920'>equal</span> <span m='2016160'>to</span> <span
  m='2016280'>minus</span> <span m='2016940'>the</span> <span
  m='2017030'>imaginary</span> <span m='2017570'>part</span> <span
  m='2018170'>at</span> <span m='2019700'>capital</span> <span
  m='2020150'>N</span> <span m='2020270'>minus</span> <span
  m='2020690'>2.</span> <span m='2021600'>In</span> <span
  m='2021620'>other</span> <span m='2021830'>words,</span> <span
  m='2022680'>there</span> <span m='2022970'>is</span> <span
  m='2023300'>an</span> <span m='2023460'>antisymmetry</span> <span
  m='2025130'>as</span> <span m='2025730'>we</span> <span
  m='2025850'>look</span> <span m='2026090'>at</span> <span
  m='2026150'>the</span> <span m='2026240'>imaginary</span> <span
  m='2026840'>part</span> <span m='2027290'>coming</span> <span
  m='2027680'>in</span> <span m='2027800'>from</span> <span
  m='2027980'>both</span> <span m='2028250'>ends</span> <span
  m='2028460'>of</span> <span m='2028520'>the</span> <span
  m='2028610'>period.</span> <span m='2029510'>So</span> <span
  m='2029720'>that's</span> <span m='2029990'>the</span> <span
  m='2030080'>kind</span> <span m='2030290'>of</span> <span
  m='2030410'>evenness</span> <span m='2031070'>and</span> <span
  m='2031280'>oddness</span> <span m='2032510'>that</span> <span
  m='2032870'>we're</span> <span m='2033020'>talking</span> <span
  m='2033500'>about</span> <span m='2034400'>when</span> <span
  m='2034760'>we</span> <span m='2034940'>talk</span> <span
  m='2035240'>about</span> <span m='2035450'>the</span> <span
  m='2035540'>symmetry</span> <span m='2036050'>properties</span> <span
  m='2037070'>for</span> <span m='2037400'>the</span> <span
  m='2037520'>discrete</span> <span m='2038010'>Fourier</span> <span
  m='2038270'>transform.</span> </p><p><span m='2039950'>In</span> <span
  m='2040070'>other</span> <span m='2040250'>words,</span> <span
  m='2040680'>it's</span> <span m='2040700'>an</span> <span
  m='2040790'>even</span> <span m='2041060'>function</span> <span
  m='2042290'>in</span> <span m='2042410'>the</span> <span
  m='2042470'>sense</span> <span m='2042920'>that</span> <span
  m='2043190'>as</span> <span m='2043370'>we</span> <span
  m='2043490'>come</span> <span m='2043760'>in</span> <span
  m='2044240'>from</span> <span m='2045290'>the</span> <span
  m='2045380'>two</span> <span m='2045680'>ends,</span> <span
  m='2046280'>we</span> <span m='2046460'>see</span> <span m='2046640'>a</span>
  <span m='2046700'>symmetry.</span> <span m='2048110'>The</span> <span
  m='2048199'>real</span> <span m='2048409'>part</span> <span
  m='2048679'>is</span> <span m='2048800'>even.</span> <span
  m='2049100'>The</span> <span m='2049190'>imaginary</span> <span
  m='2049670'>part</span> <span m='2049940'>is</span> <span
  m='2050060'>odd,</span> <span m='2050330'>in</span> <span
  m='2050420'>the</span> <span m='2050510'>sense</span> <span
  m='2050810'>that</span> <span m='2050900'>we</span> <span
  m='2051020'>see</span> <span m='2051170'>an</span> <span
  m='2051290'>antisymmetry.</span> <span m='2052670'>As</span> <span
  m='2052850'>we</span> <span m='2052940'>come</span> <span
  m='2053179'>in</span> <span m='2053449'>from</span> <span
  m='2053659'>the</span> <span m='2053750'>two</span> <span
  m='2053960'>ends</span> <span m='2054170'>of</span> <span
  m='2054230'>the</span> <span m='2054350'>period.</span> </p><p><span
  m='2058270'>OK.</span> <span m='2059949'>That</span> <span
  m='2060340'>is</span> <span m='2061090'>just</span> <span m='2061360'>a</span>
  <span m='2061420'>simple</span> <span m='2062080'>introduction</span> <span
  m='2063190'>to</span> <span m='2063880'>the</span> <span
  m='2064659'>symmetry</span> <span m='2065170'>properties.</span> <span
  m='2067550'>We</span> <span m='2067699'>have</span> <span
  m='2068630'>also</span> <span m='2069199'>as</span> <span
  m='2069380'>we've</span> <span m='2069500'>talked</span> <span
  m='2069860'>about</span> <span m='2070880'>with</span> <span
  m='2071060'>our</span> <span m='2071179'>other</span> <span
  m='2071360'>transforms,</span> <span m='2072770'>the</span> <span
  m='2072889'>convolution</span> <span m='2073610'>property.</span> <span
  m='2075080'>And</span> <span m='2075710'>the</span> <span
  m='2075830'>convolution</span> <span m='2076550'>property</span> <span
  m='2077870'>relates</span> <span m='2078679'>very</span> <span
  m='2079040'>heavily</span> <span m='2080150'>to</span> <span
  m='2080750'>the</span> <span m='2082800'>type</span> <span
  m='2083130'>of</span> <span m='2083219'>convolution</span> <span
  m='2084300'>that</span> <span m='2084510'>we</span> <span
  m='2084690'>were</span> <span m='2084810'>talking</span> <span
  m='2085260'>about</span> <span m='2085770'>for</span> <span
  m='2086389'>the</span> <span m='2086489'>discrete</span> <span
  m='2086909'>Fourier</span> <span m='2087300'>series.</span> <span
  m='2089380'>What</span> <span m='2089489'>we</span> <span
  m='2089610'>want</span> <span m='2089790'>to</span> <span
  m='2089880'>ask</span> <span m='2091080'>is,</span> <span
  m='2092590'>what</span> <span m='2093150'>is</span> <span
  m='2093810'>the</span> <span m='2094770'>sequence,</span> <span
  m='2095820'>finite</span> <span m='2096210'>length</span> <span
  m='2096449'>sequence</span> <span m='2097290'>x3</span> <span
  m='2097800'>of</span> <span m='2097970'>n,</span> <span
  m='2099380'>whose</span> <span m='2099850'>discrete</span> <span
  m='2100320'>Fourier</span> <span m='2100770'>transform</span> <span
  m='2102240'>is</span> <span m='2102840'>the</span> <span
  m='2102960'>product</span> <span m='2103770'>of</span> <span
  m='2104550'>the</span> <span m='2104640'>discrete</span> <span
  m='2105000'>Fourier</span> <span m='2105390'>transform</span> <span
  m='2106200'>of</span> <span m='2106320'>x1</span> <span m='2106770'>of</span>
  <span m='2106890'>n,</span> <span m='2107790'>and</span> <span
  m='2108410'>the</span> <span m='2108510'>discrete</span> <span
  m='2108900'>Fourier</span> <span m='2109290'>transform</span> <span
  m='2110160'>of</span> <span m='2110310'>x2</span> <span m='2110760'>of
  n.</span> </p><p><span m='2113110'>Well,</span> <span m='2113590'>we</span>
  <span m='2113800'>know</span> <span m='2114460'>what</span> <span
  m='2115120'>the</span> <span m='2116000'>sequence</span> <span
  m='2116620'>is,</span> <span m='2117250'>the</span> <span
  m='2117550'>periodic</span> <span m='2118120'>sequence</span> <span
  m='2118585'>is,</span> <span m='2119350'>whose</span> <span
  m='2119530'>discrete</span> <span m='2119890'>Fourier</span> <span
  m='2120340'>series</span> <span m='2121480'>is</span> <span
  m='2121660'>the</span> <span m='2121780'>product</span> <span
  m='2122380'>of</span> <span m='2122590'>the</span> <span
  m='2122680'>discrete</span> <span m='2123040'>Fourier</span> <span
  m='2123430'>series</span> <span m='2124120'>of</span> <span
  m='2124750'>the</span> <span m='2124840'>periodic</span> <span
  m='2125440'>equivalent</span> <span m='2126010'>of</span> <span
  m='2126130'>x1</span> <span m='2126580'>of n</span> <span
  m='2127290'>and</span> <span m='2127510'>the</span> <span
  m='2127600'>periodic</span> <span m='2128200'>equivalent</span> <span
  m='2128950'>of</span> <span m='2129100'>x2</span> <span m='2129570'>of</span>
  <span m='2129760'>n.</span> <span m='2131820'>And</span> <span
  m='2132240'>this</span> <span m='2132450'>sequence</span> <span
  m='2133260'>must</span> <span m='2133530'>just</span> <span
  m='2134010'>simply</span> <span m='2134520'>be</span> <span
  m='2135180'>one</span> <span m='2135450'>period</span> <span
  m='2136620'>extracted</span> <span m='2137640'>from</span> <span
  m='2138060'>x3</span> <span m='2138400'>tilde</span> <span
  m='2138850'>of</span> <span m='2139300'>n.</span> <span m='2140280'>In</span>
  <span m='2140370'>other</span> <span m='2140550'>words,</span> <span
  m='2141340'>x3</span> <span m='2141750'>of</span> <span m='2141870'>n</span>
  <span m='2142710'>is</span> <span m='2142860'>equal</span> <span
  m='2143130'>to</span> <span m='2143250'>x3</span> <span
  m='2143730'>tilde</span> <span m='2144250'>of n</span> <span
  m='2144930'>multiplied</span> <span m='2145740'>by</span> <span
  m='2146220'>a</span> <span m='2146280'>rectangular</span> <span
  m='2146910'>sequence.</span> </p><p><span m='2149530'>Well,</span> <span
  m='2151800'>we</span> <span m='2151950'>know</span> <span
  m='2152250'>how</span> <span m='2152400'>to</span> <span
  m='2152520'>form</span> <span m='2153150'>from</span> <span
  m='2153360'>the</span> <span m='2153420'>last</span> <span
  m='2153780'>lecture,</span> <span m='2155760'>the</span> <span
  m='2156570'>convolution</span> <span m='2157800'>that</span> <span
  m='2157950'>corresponds</span> <span m='2158790'>to</span> <span
  m='2158940'>multiplying</span> <span m='2159660'>the</span> <span
  m='2159750'>discrete</span> <span m='2160110'>Fourier</span> <span
  m='2160530'>series</span> <span m='2161160'>together.</span> <span
  m='2162180'>And</span> <span m='2162270'>that</span> <span
  m='2162420'>convolution</span> <span m='2163860'>was</span> <span
  m='2164580'>the</span> <span m='2164940'>periodic</span> <span
  m='2165540'>sequences</span> <span m='2166790'>x1</span> <span
  m='2167250'>tilde</span> <span m='2167560'>of</span> <span
  m='2167770'>m</span> <span m='2168540'>and</span> <span m='2168690'>x2</span>
  <span m='2169110'>tilde</span> <span m='2169370'>of</span> <span
  m='2169750'>n</span> <span m='2170220'>minus</span> <span
  m='2170580'>m,</span> <span m='2172920'>summed</span> <span
  m='2173640'>over</span> <span m='2173940'>one</span> <span
  m='2174180'>period</span> <span m='2174780'>that</span> <span
  m='2175020'>is</span> <span m='2175290'>from</span> <span m='2175500'>m</span>
  <span m='2175710'>equals</span> <span m='2176000'>0</span> <span
  m='2176460'>to</span> <span m='2176640'>capital</span> <span
  m='2177090'>N</span> <span m='2177240'>minus</span> <span
  m='2177690'>1.</span> <span m='2179915'>Well,</span> <span
  m='2180360'>the</span> <span m='2180480'>finite</span> <span
  m='2180960'>length</span> <span m='2181230'>sequence,</span> <span
  m='2182380'>x3</span> <span m='2182930'>of</span> <span m='2183040'>n</span>
  <span m='2183390'>that</span> <span m='2183480'>corresponds</span> <span
  m='2184200'>to</span> <span m='2184320'>the</span> <span
  m='2184410'>product</span> <span m='2184860'>of</span> <span
  m='2185010'>these</span> <span m='2185310'>two</span> <span
  m='2185520'>discrete</span> <span m='2185920'>Fourier</span> <span
  m='2186360'>transforms,</span> <span m='2188190'>corresponds</span> <span
  m='2189030'>then</span> <span m='2190020'>to</span> <span
  m='2190410'>extracting</span> <span m='2191610'>a</span> <span
  m='2191700'>single</span> <span m='2192120'>period</span> <span
  m='2193440'>from</span> <span m='2194340'>this</span> <span
  m='2195000'>periodic</span> <span m='2195600'>sequence,</span> <span
  m='2196470'>in</span> <span m='2196590'>other</span> <span
  m='2196770'>words,</span> <span m='2197730'>multiplying</span> <span
  m='2198450'>this</span> <span m='2198840'>by</span> <span m='2199080'>R</span>
  <span m='2199350'>sub</span> <span m='2199560'>capital</span> <span
  m='2200070'>N</span> <span m='2201530'>of</span> <span m='2201870'>n.</span>
  </p><p><span m='2204930'>So</span> <span m='2205380'>this</span> <span
  m='2205740'>then</span> <span m='2206070'>is</span> <span
  m='2206280'>the</span> <span m='2206370'>kind</span> <span
  m='2206700'>of</span> <span m='2206790'>convolution</span> <span
  m='2208140'>that</span> <span m='2208290'>results</span> <span
  m='2209520'>from</span> <span m='2210060'>multiplying</span> <span
  m='2210810'>the</span> <span m='2210930'>discrete</span> <span
  m='2211290'>Fourier</span> <span m='2211710'>transforms</span> <span
  m='2212460'>together,</span> <span m='2213960'>or</span> <span
  m='2214320'>we</span> <span m='2214500'>could</span> <span
  m='2214650'>write</span> <span m='2214890'>this</span> <span
  m='2215100'>in</span> <span m='2215190'>a</span> <span
  m='2215250'>different</span> <span m='2215610'>way.</span> <span
  m='2216720'>We</span> <span m='2216900'>can</span> <span
  m='2218010'>express</span> <span m='2218550'>this</span> <span
  m='2218790'>periodic</span> <span m='2219390'>sequence</span> <span
  m='2220320'>using</span> <span m='2220680'>our</span> <span
  m='2220770'>modular</span> <span m='2221220'>notation</span> <span
  m='2222450'>in</span> <span m='2222570'>terms</span> <span
  m='2222870'>of</span> <span m='2222960'>x1</span> <span m='2223410'>of</span>
  <span m='2223520'>m,</span> <span m='2224790'>as</span> <span
  m='2225180'>x1</span> <span m='2225960'>of</span> <span m='2226340'>m</span>
  <span m='2227460'>taken</span> <span m='2227790'>modulo</span> <span
  m='2228600'>capital</span> <span m='2229140'>N.</span> <span
  m='2230760'>And</span> <span m='2230910'>this</span> <span
  m='2231120'>periodic</span> <span m='2231720'>sequence</span> <span
  m='2232770'>is</span> <span m='2233070'>x2</span> <span m='2233970'>of</span>
  <span m='2234240'>n</span> <span m='2234600'>minus</span> <span
  m='2234970'>m</span> <span m='2235800'>that</span> <span
  m='2236010'>argument</span> <span m='2236720'>taken</span> <span
  m='2237060'>modulo</span> <span m='2237540'>capital</span> <span
  m='2238080'>N.</span> <span m='2239550'>Well,</span> <span
  m='2240270'>we</span> <span m='2240420'>can</span> <span
  m='2241230'>take</span> <span m='2241500'>one</span> <span
  m='2242010'>additional</span> <span m='2242520'>step</span> <span
  m='2242910'>here,</span> <span m='2243490'>which</span> <span
  m='2244530'>may</span> <span m='2244740'>or</span> <span
  m='2244830'>may</span> <span m='2244980'>not</span> <span
  m='2245190'>be</span> <span m='2245340'>useful.</span> <span
  m='2246330'>Observe</span> <span m='2246840'>that</span> <span
  m='2247710'>we</span> <span m='2247890'>only</span> <span
  m='2248190'>use</span> <span m='2248460'>values</span> <span
  m='2248970'>of</span> <span m='2249090'>m</span> <span m='2249900'>in</span>
  <span m='2250050'>this</span> <span m='2250230'>expression</span> <span
  m='2251880'>in</span> <span m='2251970'>the</span> <span
  m='2252090'>interval</span> <span m='2252510'>from</span> <span
  m='2252720'>0</span> <span m='2253290'>to</span> <span
  m='2253440'>capital</span> <span m='2253920'>N</span> <span
  m='2254040'>minus</span> <span m='2254430'>1.</span> <span
  m='2255550'>So</span> <span m='2255660'>in</span> <span
  m='2255780'>fact,</span> <span m='2256300'>although</span> <span
  m='2256500'>this</span> <span m='2256740'>is</span> <span m='2256860'>a</span>
  <span m='2256920'>periodic</span> <span m='2257490'>sequence,</span> <span
  m='2258330'>we're</span> <span m='2258510'>only</span> <span
  m='2258750'>using</span> <span m='2259140'>one</span> <span
  m='2259350'>period</span> <span m='2259800'>of</span> <span
  m='2259980'>it.</span> <span m='2260580'>So</span> <span
  m='2261420'>this</span> <span m='2261660'>piece</span> <span
  m='2262710'>is</span> <span m='2262890'>equivalently</span> <span
  m='2265370'>x1</span> <span m='2267510'>of</span> <span m='2267690'>m.</span>
  <span m='2269970'>And</span> <span m='2270450'>what</span> <span
  m='2270720'>is</span> <span m='2270900'>this?</span> <span
  m='2271530'>Well,</span> <span m='2272160'>think</span> <span
  m='2272460'>back</span> <span m='2272970'>to</span> <span
  m='2273600'>the</span> <span m='2273780'>kind</span> <span
  m='2274140'>of</span> <span m='2274380'>circular</span> <span
  m='2274980'>shifting</span> <span m='2276000'>that</span> <span
  m='2276120'>we</span> <span m='2276270'>were</span> <span
  m='2276390'>talking</span> <span m='2276810'>about</span> <span
  m='2277020'>doing</span> <span m='2277350'>with</span> <span
  m='2277500'>finite</span> <span m='2277920'>length</span> <span
  m='2278130'>sequences.</span> </p><p><span m='2279630'>What</span> <span
  m='2279900'>this</span> <span m='2280320'>basically</span> <span
  m='2280920'>corresponds</span> <span m='2281640'>to</span> <span
  m='2281760'>doing</span> <span m='2282750'>is</span> <span
  m='2283140'>applying</span> <span m='2284040'>not</span> <span
  m='2284270'>a</span> <span m='2284330'>linear</span> <span
  m='2284760'>shift</span> <span m='2285390'>to</span> <span
  m='2285480'>x2</span> <span m='2285990'>of</span> <span m='2286150'>n,</span>
  <span m='2287250'>but</span> <span m='2287610'>a</span> <span
  m='2287670'>circular</span> <span m='2288240'>shift,</span> <span
  m='2288630'>flipping</span> <span m='2289110'>x2</span> <span
  m='2290100'>and</span> <span m='2290220'>applying</span> <span
  m='2290610'>a</span> <span m='2290670'>circular</span> <span
  m='2291180'>shift</span> <span m='2291930'>to</span> <span
  m='2292230'>x2</span> <span m='2292530'>of</span> <span m='2292760'>n.</span>
  <span m='2294180'>And then</span> <span m='2294360'>of</span> <span
  m='2294450'>course,</span> <span m='2295270'>this</span> <span
  m='2295380'>is</span> <span m='2295470'>just</span> <span
  m='2295770'>in</span> <span m='2295920'>here</span> <span
  m='2296190'>to</span> <span m='2296370'>allow</span> <span
  m='2296670'>us</span> <span m='2296820'>to</span> <span
  m='2296970'>extract</span> <span m='2297420'>a</span> <span
  m='2297480'>single</span> <span m='2297810'>period.</span> <span
  m='2299670'>This</span> <span m='2300180'>then</span> <span
  m='2300510'>corresponds</span> <span m='2301470'>to</span> <span
  m='2302160'>what</span> <span m='2302430'>we'll</span> <span
  m='2302670'>refer</span> <span m='2303060'>to</span> <span
  m='2304050'>as</span> <span m='2304440'>a</span> <span
  m='2304500'>circular</span> <span m='2305040'>convolution</span> <span
  m='2306390'>of</span> <span m='2307050'>this</span> <span
  m='2307620'>sequence,</span> <span m='2308670'>or</span> <span
  m='2308910'>rather</span> <span m='2309300'>the</span> <span
  m='2309450'>sequence</span> <span m='2309840'>x1</span> <span
  m='2310290'>of</span> <span m='2311910'>n,</span> <span m='2312225'>and</span>
  <span m='2312540'>the</span> <span m='2312630'>finite</span> <span
  m='2312990'>length</span> <span m='2313200'>sequence</span> <span
  m='2313710'>x2</span> <span m='2314170'>of</span> <span m='2314290'>n.</span>
  <span m='2315860'>It's</span> <span m='2316020'>a</span> <span
  m='2316080'>circular</span> <span m='2317610'>convolution.</span> <span
  m='2319110'>And</span> <span m='2319410'>notationally</span> <span
  m='2320550'>we'll</span> <span m='2320880'>denote</span> <span
  m='2321300'>that</span> <span m='2322020'>as</span> <span
  m='2322470'>x1</span> <span m='2322960'>of</span> <span m='2323120'>n,</span>
  <span m='2323820'>circularly</span> <span m='2324550'>convolved,</span> <span
  m='2325230'>keeping</span> <span m='2325590'>track</span> <span
  m='2326160'>of</span> <span m='2326970'>what</span> <span
  m='2327390'>the</span> <span m='2327510'>circumference</span> <span
  m='2328230'>of</span> <span m='2328350'>this</span> <span
  m='2328480'>cylinder</span> <span m='2329100'>is</span> <span
  m='2329370'>that</span> <span m='2329550'>we're</span> <span
  m='2329700'>wrapping</span> <span m='2330660'>the</span> <span
  m='2330810'>finite-length</span> <span m='2331350'>sequences</span> <span
  m='2331980'>around,</span> <span m='2333270'>circularly</span> <span
  m='2333890'>convolved,</span> <span m='2334770'>an</span> <span
  m='2334890'>endpoint</span> <span m='2335400'>circular</span> <span
  m='2335760'>convolution</span> <span m='2336660'>with</span> <span
  m='2336840'>x2</span> <span m='2337080'>of</span> <span m='2337290'>n.</span>
  </p><p><span m='2339300'>Now,</span> <span m='2339780'>I</span> <span
  m='2339930'>wouldn't</span> <span m='2340230'>expect</span> <span
  m='2341100'>at</span> <span m='2341220'>this</span> <span
  m='2341430'>point</span> <span m='2342180'>that</span> <span
  m='2342990'>what</span> <span m='2343230'>this</span> <span
  m='2343380'>circular</span> <span m='2343800'>convolution</span> <span
  m='2345330'>is</span> <span m='2345700'>in</span> <span
  m='2345870'>detail,</span> <span m='2346440'>I</span> <span
  m='2346530'>wouldn't</span> <span m='2346740'>expect</span> <span
  m='2347130'>that</span> <span m='2347640'>to</span> <span
  m='2347760'>be</span> <span m='2347910'>very</span> <span
  m='2348150'>clear.</span> <span m='2349170'>We</span> <span
  m='2349290'>have</span> <span m='2350130'>some</span> <span
  m='2350310'>modular</span> <span m='2350820'>notation</span> <span
  m='2351450'>in</span> <span m='2351600'>there,</span> <span
  m='2351930'>and</span> <span m='2352050'>we're</span> <span
  m='2352200'>multiplying</span> <span m='2352860'>by</span> <span
  m='2353040'>this.</span> <span m='2353500'>And</span> <span
  m='2353600'>there</span> <span m='2353700'>was</span> <span
  m='2353800'>some</span> <span m='2353850'>periodic</span> <span
  m='2354600'>something</span> <span m='2355080'>somewhere,</span> <span
  m='2355830'>and</span> <span m='2356220'>where</span> <span
  m='2356400'>did</span> <span m='2356520'>we</span> <span
  m='2356700'>extract</span> <span m='2357130'>the</span> <span
  m='2357210'>period.</span> <span m='2359550'>A</span> <span
  m='2359640'>lot</span> <span m='2359850'>of</span> <span
  m='2359970'>our</span> <span m='2360060'>attention</span> <span
  m='2360900'>at</span> <span m='2361020'>this</span> <span
  m='2361260'>point,</span> <span m='2361750'>and</span> <span
  m='2361760'>in</span> <span m='2361830'>fact</span> <span
  m='2362130'>through</span> <span m='2362280'>most</span> <span
  m='2362820'>of</span> <span m='2362970'>the</span> <span
  m='2363060'>next</span> <span m='2363330'>lecture,</span> <span
  m='2364710'>is</span> <span m='2364830'>going</span> <span
  m='2365010'>to</span> <span m='2365100'>be</span> <span
  m='2365190'>focused</span> <span m='2365970'>on</span> <span
  m='2367000'>interpreting</span> <span m='2368580'>and</span> <span
  m='2368670'>getting</span> <span m='2368940'>a</span> <span
  m='2369000'>feeling</span> <span m='2369660'>for</span> <span
  m='2370290'>what</span> <span m='2370560'>the</span> <span
  m='2370680'>circular</span> <span m='2371130'>convolution</span> <span
  m='2371850'>means.</span> <span m='2373290'>There</span> <span
  m='2373770'>are</span> <span m='2373980'>lots</span> <span
  m='2374280'>of</span> <span m='2374370'>pictures</span> <span
  m='2375060'>that</span> <span m='2375420'>I'll</span> <span
  m='2375990'>try</span> <span m='2376380'>to</span> <span
  m='2376530'>suggest</span> <span m='2377310'>to</span> <span
  m='2378060'>help</span> <span m='2378570'>in</span> <span
  m='2379020'>forming</span> <span m='2379800'>an</span> <span
  m='2379920'>idea</span> <span m='2380430'>of</span> <span
  m='2381030'>circular</span> <span m='2381450'>convolution.</span> </p><p><span
  m='2382980'>Let</span> <span m='2383160'>me</span> <span
  m='2383340'>just</span> <span m='2384330'>offer</span> <span
  m='2384690'>one</span> <span m='2384960'>now</span> <span
  m='2385650'>and</span> <span m='2386130'>show</span> <span
  m='2386430'>you</span> <span m='2386790'>a</span> <span
  m='2386880'>simple</span> <span m='2387690'>example</span> <span
  m='2388440'>of</span> <span m='2389280'>circular</span> <span
  m='2389700'>convolution,</span> <span m='2391200'>with</span> <span
  m='2391410'>the</span> <span m='2391500'>notion</span> <span
  m='2392280'>that</span> <span m='2392820'>in</span> <span
  m='2392940'>the</span> <span m='2393030'>next</span> <span
  m='2393300'>lecture</span> <span m='2393820'>we'll</span> <span
  m='2393900'>be</span> <span m='2394050'>focusing</span> <span
  m='2394560'>almost</span> <span m='2394860'>entirely</span> <span
  m='2395580'>on</span> <span m='2395730'>what</span> <span
  m='2395940'>circular</span> <span m='2396360'>convolution</span> <span
  m='2397080'>means</span> <span m='2397410'>in</span> <span
  m='2397500'>relation</span> <span m='2398490'>to</span> <span
  m='2398610'>linear</span> <span m='2398970'>convolution,</span> <span
  m='2399700'>et</span> <span m='2400060'>cetera.</span> <span
  m='2401250'>But</span> <span m='2401400'>look.</span> <span
  m='2401640'>Here's</span> <span m='2401880'>what</span> <span
  m='2402030'>this</span> <span m='2402240'>means.</span> <span
  m='2403800'>First</span> <span m='2404040'>of</span> <span
  m='2404130'>all,</span> <span m='2404220'>linear</span> <span
  m='2404580'>convolution,</span> <span m='2405330'>what</span> <span
  m='2405450'>do</span> <span m='2405510'>we</span> <span m='2405630'>do?</span>
  <span m='2405870'>We</span> <span m='2406050'>have</span> <span
  m='2406380'>two</span> <span m='2406560'>sequences.</span> <span
  m='2407970'>They're</span> <span m='2408090'>laid</span> <span
  m='2408360'>out</span> <span m='2408540'>flat.</span> <span
  m='2409890'>We</span> <span m='2409980'>do</span> <span m='2410160'>a</span>
  <span m='2410220'>linear</span> <span m='2410520'>convolution</span> <span
  m='2411360'>by</span> <span m='2411930'>flipping</span> <span
  m='2412380'>one</span> <span m='2412560'>of</span> <span
  m='2412620'>the</span> <span m='2412740'>sequences,</span> <span
  m='2414120'>and</span> <span m='2414240'>then</span> <span
  m='2414360'>shifting</span> <span m='2414900'>the</span> <span
  m='2415020'>two</span> <span m='2415200'>sequences</span> <span
  m='2415830'>linearly</span> <span m='2416820'>with</span> <span
  m='2417000'>relation</span> <span m='2417480'>to</span> <span
  m='2417630'>each</span> <span m='2417840'>other,</span> <span
  m='2418440'>multiplying</span> <span m='2419820'>and</span> <span
  m='2420240'>adding</span> <span m='2420660'>up</span> <span
  m='2421110'>the</span> <span m='2421230'>values</span> <span
  m='2421740'>from</span> <span m='2421890'>minus</span> <span
  m='2422250'>infinity</span> <span m='2422700'>to</span> <span
  m='2422820'>plus</span> <span m='2423090'>infinity.</span> </p><p><span
  m='2425100'>The</span> <span m='2425220'>circular</span> <span
  m='2425670'>convolution</span> <span m='2426990'>basically</span> <span
  m='2427500'>corresponds</span> <span m='2428850'>to</span> <span
  m='2429660'>wrapping</span> <span m='2430710'>one</span> <span
  m='2430920'>of</span> <span m='2431010'>the</span> <span
  m='2431100'>sequences</span> <span m='2432180'>around</span> <span
  m='2432510'>the</span> <span m='2432600'>circumference</span> <span
  m='2433290'>of</span> <span m='2433410'>a</span> <span
  m='2433440'>cylinder,</span> <span m='2435180'>taking</span> <span
  m='2435540'>the</span> <span m='2435660'>other</span> <span
  m='2435840'>sequence,</span> <span m='2436680'>flipping</span> <span
  m='2437190'>it,</span> <span m='2437970'>wrapping</span> <span
  m='2438360'>that</span> <span m='2438690'>around</span> <span
  m='2438970'>the</span> <span m='2439050'>circumference</span> <span
  m='2439740'>of</span> <span m='2439830'>another</span> <span
  m='2440160'>cylinder,</span> <span m='2442050'>putting</span> <span
  m='2442320'>the</span> <span m='2442410'>two</span> <span
  m='2442590'>cylinders</span> <span m='2443190'>inside</span> <span
  m='2443610'>each</span> <span m='2443850'>other,</span> <span
  m='2445020'>and</span> <span m='2445170'>then</span> <span
  m='2445700'>the</span> <span m='2445830'>shifting</span> <span
  m='2447030'>as</span> <span m='2447180'>we</span> <span
  m='2447270'>change</span> <span m='2447600'>the</span> <span
  m='2447690'>value</span> <span m='2448050'>of</span> <span
  m='2448170'>n</span> <span m='2448920'>can</span> <span m='2449070'>be</span>
  <span m='2449190'>thought</span> <span m='2449520'>of</span> <span
  m='2449850'>as</span> <span m='2450060'>rotating</span> <span
  m='2450930'>one</span> <span m='2451140'>of</span> <span
  m='2451230'>the</span> <span m='2451320'>cylinders</span> <span
  m='2451980'>inside</span> <span m='2452430'>the</span> <span
  m='2452610'>other,</span> <span m='2454180'>multiplying</span> <span
  m='2455230'>the</span> <span m='2455550'>sequence</span> <span
  m='2456030'>values</span> <span m='2456510'>together,</span> <span
  m='2457590'>and</span> <span m='2457680'>then</span> <span
  m='2457890'>adding</span> <span m='2458790'>that</span> <span
  m='2459270'>product</span> <span m='2459900'>around</span> <span
  m='2460230'>the</span> <span m='2460350'>cylinder.</span> <span
  m='2460860'>That</span> <span m='2461070'>is</span> <span
  m='2461400'>adding</span> <span m='2461760'>from m</span> <span
  m='2462070'>equals</span> <span m='2462330'>0</span> <span
  m='2462930'>to</span> <span m='2463050'>capital</span> <span
  m='2463500'>N</span> <span m='2463620'>minus</span> <span
  m='2464010'>1.</span> <span m='2465850'>And</span> <span
  m='2465870'>what</span> <span m='2466080'>this</span> <span
  m='2466350'>thing</span> <span m='2466920'>does</span> <span
  m='2467280'>basically,</span> <span m='2468480'>since</span> <span
  m='2468750'>it</span> <span m='2468840'>extracts</span> <span
  m='2469260'>one</span> <span m='2469470'>period</span> <span
  m='2470040'>of</span> <span m='2470160'>a</span> <span
  m='2470220'>periodic</span> <span m='2470760'>sequence,</span> <span
  m='2471840'>it</span> <span m='2471930'>corresponds</span> <span
  m='2472680'>essentially</span> <span m='2473790'>to</span> <span
  m='2473910'>just</span> <span m='2474090'>simply</span> <span
  m='2474990'>cutting</span> <span m='2475980'>the</span> <span
  m='2476070'>cylinder</span> <span m='2477030'>and</span> <span
  m='2477150'>laying</span> <span m='2477480'>the</span> <span
  m='2477630'>answer</span> <span m='2477890'>around</span> <span
  m='2478110'>flat</span> <span m='2478430'>again.</span> <span
  m='2479550'>That's</span> <span m='2479850'>the</span> <span
  m='2479970'>notion</span> <span m='2480570'>of</span> <span
  m='2480690'>circular</span> <span m='2481170'>convolution,</span> <span
  m='2482130'>and</span> <span m='2482550'>it</span> <span
  m='2483120'>results</span> <span m='2483510'>from</span> <span
  m='2483690'>the</span> <span m='2483780'>fact</span> <span
  m='2484260'>that</span> <span m='2484350'>we're</span> <span
  m='2484590'>thinking</span> <span m='2485100'>of</span> <span
  m='2485670'>the</span> <span m='2485850'>arguments</span> <span
  m='2486630'>in</span> <span m='2486720'>the</span> <span
  m='2486810'>convolution</span> <span m='2487890'>taken</span> <span
  m='2488550'>modulo</span> <span m='2489270'>capital</span> <span
  m='2489800'>N.</span> </p><p><span m='2491130'>Well,</span> <span
  m='2491490'>let's</span> <span m='2491790'>just</span> <span
  m='2492120'>look</span> <span m='2492390'>at</span> <span m='2492510'>a</span>
  <span m='2492570'>simple</span> <span m='2492960'>example</span> <span
  m='2494010'>with</span> <span m='2494580'>the</span> <span
  m='2494700'>idea</span> <span m='2495360'>that</span> <span
  m='2495660'>as</span> <span m='2496290'>we</span> <span m='2497220'>go</span>
  <span m='2497460'>on</span> <span m='2498240'>to</span> <span
  m='2498330'>the</span> <span m='2498420'>next</span> <span
  m='2498690'>lecture,</span> <span m='2499540'>we'll</span> <span
  m='2499920'>be</span> <span m='2500070'>concentrating</span> <span
  m='2500950'>some</span> <span m='2501150'>more</span> <span
  m='2501690'>on</span> <span m='2502200'>the</span> <span
  m='2502320'>interpretation</span> <span m='2503190'>of</span> <span
  m='2503310'>what</span> <span m='2503460'>circular</span> <span
  m='2503850'>convolution</span> <span m='2504540'>means.</span> </p><p><span
  m='2510880'>All</span> <span m='2510970'>right.</span> <span
  m='2511480'>Here</span> <span m='2511720'>we</span> <span
  m='2511930'>have</span> <span m='2513220'>a</span> <span
  m='2513310'>sequence</span> <span m='2514060'>x1</span> <span
  m='2514810'>of</span> <span m='2514960'>m.</span> <span
  m='2516340'>Remember</span> <span m='2516880'>that</span> <span
  m='2517480'>in</span> <span m='2518140'>the</span> <span
  m='2518920'>circular</span> <span m='2519400'>convolution,</span> <span
  m='2520900'>we're</span> <span m='2521170'>summing</span> <span
  m='2522310'>over</span> <span m='2522670'>an</span> <span
  m='2522790'>index</span> <span m='2523320'>m.</span> <span
  m='2524320'>So</span> <span m='2524590'>here</span> <span
  m='2524800'>we</span> <span m='2524920'>have</span> <span
  m='2525100'>x1</span> <span m='2525550'>of</span> <span m='2525640'>m.</span>
  <span m='2527680'>Here</span> <span m='2527890'>we</span> <span
  m='2528040'>have</span> <span m='2528310'>x2</span> <span
  m='2528910'>of</span> <span m='2529000'>m.</span> <span m='2530230'>And</span>
  <span m='2530410'>what</span> <span m='2530560'>we</span> <span
  m='2530710'>want</span> <span m='2530920'>to</span> <span
  m='2530980'>form</span> <span m='2532030'>is</span> <span
  m='2533140'>x2</span> <span m='2534130'>of</span> <span m='2535940'>n</span>
  <span m='2536600'>minus</span> <span m='2537170'>m</span> <span
  m='2538070'>taken</span> <span m='2538430'>modulo</span> <span
  m='2539030'>capital</span> <span m='2539600'>N.</span> <span
  m='2541370'>So</span> <span m='2541550'>first</span> <span
  m='2541880'>of</span> <span m='2542030'>all,</span> <span
  m='2543110'>here</span> <span m='2543680'>we</span> <span
  m='2543860'>have</span> <span m='2544190'>x2</span> <span
  m='2544900'>of</span> <span m='2545120'>minus</span> <span
  m='2545640'>m,</span> <span m='2547610'>modulo</span> <span
  m='2548600'>capital</span> <span m='2549130'>N.</span> <span
  m='2550090'>And</span> <span m='2550180'>what</span> <span
  m='2550370'>that</span> <span m='2550850'>corresponds</span> <span
  m='2551660'>to</span> <span m='2551960'>is</span> <span
  m='2552140'>flipping</span> <span m='2552740'>x2</span> <span
  m='2553250'>of</span> <span m='2553340'>m,</span> <span
  m='2553970'>flipping</span> <span m='2554360'>it</span> <span
  m='2554420'>over,</span> <span m='2555500'>and</span> <span
  m='2555650'>then</span> <span m='2556400'>repeating</span> <span
  m='2557000'>it</span> <span m='2558170'>periodically.</span> <span
  m='2560690'>And</span> <span m='2561410'>the</span> <span
  m='2561950'>periodic</span> <span m='2562540'>replicas</span> <span
  m='2563290'>I've</span> <span m='2563570'>designated</span> <span
  m='2564230'>here</span> <span m='2564740'>with</span> <span
  m='2564920'>dashed</span> <span m='2565340'>lines,</span> <span
  m='2566030'>so</span> <span m='2566210'>that</span> <span
  m='2566450'>we</span> <span m='2566600'>focus</span> <span
  m='2567050'>completely</span> <span m='2568130'>on</span> <span
  m='2568700'>the</span> <span m='2568850'>interval</span> <span
  m='2569240'>0</span> <span m='2570080'>to</span> <span
  m='2570200'>capital</span> <span m='2570650'>N</span> <span
  m='2570770'>minus</span> <span m='2571190'>1.</span> </p><p><span
  m='2573240'>So</span> <span m='2573440'>in</span> <span
  m='2573560'>fact,</span> <span m='2574350'>notice</span> <span
  m='2574910'>that</span> <span m='2575090'>we</span> <span
  m='2575240'>could</span> <span m='2575450'>have</span> <span
  m='2575600'>thought</span> <span m='2576050'>of</span> <span
  m='2576500'>flipping</span> <span m='2577040'>this</span> <span
  m='2577970'>modulo</span> <span m='2578480'>capital</span> <span
  m='2579020'>N</span> <span m='2580340'>by</span> <span
  m='2581450'>first</span> <span m='2581780'>flipping</span> <span
  m='2582230'>it,</span> <span m='2582600'>and</span> <span
  m='2582650'>then</span> <span m='2582830'>taking</span> <span
  m='2583250'>the</span> <span m='2583340'>values</span> <span
  m='2583910'>over</span> <span m='2584180'>here,</span> <span
  m='2584600'>and</span> <span m='2584750'>just</span> <span
  m='2584930'>simply</span> <span m='2585290'>replacing</span> <span
  m='2585950'>them</span> <span m='2586640'>on</span> <span
  m='2586790'>the</span> <span m='2586880'>right-hand</span> <span
  m='2587360'>side.</span> <span m='2588300'>In</span> <span
  m='2588400'>other</span> <span m='2588440'>words,</span> <span
  m='2589440'>it's</span> <span m='2589550'>these</span> <span
  m='2589820'>values</span> <span m='2590690'>that</span> <span
  m='2590960'>ended</span> <span m='2591290'>up</span> <span
  m='2591470'>over</span> <span m='2591740'>here.</span> <span
  m='2592610'>When</span> <span m='2592760'>we</span> <span
  m='2592880'>flip</span> <span m='2593180'>this</span> <span
  m='2593360'>sequence,</span> <span m='2593840'>of</span> <span
  m='2593960'>course,</span> <span m='2594330'>the</span> <span
  m='2594350'>value</span> <span m='2594740'>at</span> <span
  m='2594830'>0</span> <span m='2595310'>stays</span> <span
  m='2595730'>where</span> <span m='2595940'>it</span> <span
  m='2596030'>is,</span> <span m='2597620'>and</span> <span
  m='2598370'>the</span> <span m='2598490'>rest</span> <span
  m='2598790'>of</span> <span m='2598910'>those</span> <span
  m='2599390'>values</span> <span m='2600260'>end</span> <span
  m='2600560'>up</span> <span m='2601280'>again</span> <span
  m='2601640'>in</span> <span m='2601760'>the</span> <span
  m='2601820'>range</span> <span m='2602090'>0</span> <span
  m='2602420'>to</span> <span m='2602540'>capital</span> <span
  m='2602990'>N</span> <span m='2603110'>minus</span> <span
  m='2603520'>1,</span> <span m='2603905'>but</span> <span
  m='2604290'>flipped</span> <span m='2604560'>over.</span> <span
  m='2606800'>If</span> <span m='2606950'>we</span> <span
  m='2607070'>shift</span> <span m='2607850'>this</span> <span
  m='2608030'>periodic</span> <span m='2608660'>sequence</span> <span
  m='2609590'>by</span> <span m='2610100'>one</span> <span
  m='2610370'>value</span> <span m='2611270'>to</span> <span
  m='2611420'>the</span> <span m='2611510'>left,</span> <span
  m='2614490'>then</span> <span m='2615330'>what</span> <span
  m='2615540'>we</span> <span m='2615720'>have</span> <span
  m='2616230'>is--</span> <span m='2619290'>sorry,</span> <span
  m='2619770'>shift it</span> <span m='2620250'>by</span> <span
  m='2620400'>one</span> <span m='2620640'>value</span> <span
  m='2620940'>to</span> <span m='2621060'>the</span> <span
  m='2621180'>right,</span> <span m='2622230'>then</span> <span
  m='2622950'>we</span> <span m='2623790'>end</span> <span m='2624030'>up</span>
  <span m='2624180'>with</span> <span m='2624360'>this</span> <span
  m='2624570'>periodic</span> <span m='2625200'>sequence.</span> <span
  m='2626460'>Again,</span> <span m='2626940'>concentrate</span> <span
  m='2627870'>on</span> <span m='2628140'>the</span> <span
  m='2628230'>range</span> <span m='2628560'>0</span> <span
  m='2628950'>to</span> <span m='2629100'>capital</span> <span
  m='2629550'>N</span> <span m='2629700'>minus</span> <span
  m='2630160'>1,</span> <span m='2631032'>and</span> <span
  m='2631470'>you</span> <span m='2631590'>can</span> <span
  m='2631740'>see</span> <span m='2632010'>that</span> <span
  m='2632190'>that</span> <span m='2633090'>is</span> <span m='2633690'>a</span>
  <span m='2633750'>circular</span> <span m='2634320'>shift</span> <span
  m='2635580'>of</span> <span m='2636036'>one</span> <span
  m='2636492'>point</span> <span m='2637404'>of</span> <span
  m='2638100'>one</span> <span m='2638370'>period</span> <span
  m='2639270'>of</span> <span m='2639870'>this</span> <span
  m='2640080'>periodic</span> <span m='2640650'>sequence.</span> </p><p><span
  m='2642180'>In</span> <span m='2642240'>other</span> <span
  m='2642390'>words,</span> <span m='2643170'>if</span> <span
  m='2643340'>you</span> <span m='2643460'>circularly</span> <span
  m='2644010'>shift</span> <span m='2644370'>this</span> <span
  m='2644670'>to</span> <span m='2644820'>the</span> <span
  m='2644940'>right,</span> <span m='2645960'>that</span> <span
  m='2646230'>point</span> <span m='2647100'>comes</span> <span
  m='2647370'>back</span> <span m='2647700'>in</span> <span
  m='2647880'>on</span> <span m='2648000'>the</span> <span
  m='2648120'>other</span> <span m='2648300'>side.</span> <span
  m='2650460'>Here</span> <span m='2650790'>is</span> <span
  m='2650970'>the</span> <span m='2651030'>same</span> <span
  m='2651330'>thing</span> <span m='2651900'>shifted.</span> <span
  m='2653490'>Again,</span> <span m='2654120'>another</span> <span
  m='2654480'>point,</span> <span m='2655650'>so</span> <span
  m='2655860'>we</span> <span m='2655980'>can</span> <span
  m='2656130'>think</span> <span m='2656400'>of</span> <span
  m='2656520'>having</span> <span m='2656790'>taken</span> <span
  m='2657180'>this</span> <span m='2657420'>one</span> <span
  m='2657690'>period,</span> <span m='2658800'>shifting</span> <span
  m='2659280'>it</span> <span m='2659370'>to</span> <span m='2659490'>the</span>
  <span m='2659580'>right,</span> <span m='2659970'>and</span> <span
  m='2660120'>this</span> <span m='2660300'>point</span> <span
  m='2660900'>comes</span> <span m='2661170'>back</span> <span
  m='2661530'>in</span> <span m='2661890'>again</span> <span
  m='2662220'>on</span> <span m='2662310'>the</span> <span
  m='2662430'>other</span> <span m='2662610'>side.</span> <span
  m='2663390'>Of</span> <span m='2663450'>course,</span> <span
  m='2663780'>the</span> <span m='2663900'>way</span> <span
  m='2664050'>we're</span> <span m='2664200'>really</span> <span
  m='2664500'>getting</span> <span m='2664830'>it</span> <span
  m='2665040'>is--</span> <span m='2666120'>or</span> <span
  m='2666300'>another</span> <span m='2666570'>way</span> <span
  m='2666720'>to</span> <span m='2666810'>think</span> <span
  m='2667080'>of</span> <span m='2667170'>it</span> <span
  m='2667320'>is--</span> <span m='2667680'>it's</span> <span
  m='2667950'>the</span> <span m='2668370'>corresponding</span> <span
  m='2669120'>value</span> <span m='2669540'>from</span> <span
  m='2669720'>the</span> <span m='2669810'>next</span> <span
  m='2670050'>period</span> <span m='2670470'>over</span> <span
  m='2671280'>that</span> <span m='2671400'>gets</span> <span
  m='2671580'>shifted</span> <span m='2672030'>in.</span> <span
  m='2672720'>But</span> <span m='2673050'>I'd</span> <span
  m='2673230'>prefer</span> <span m='2674100'>now</span> <span
  m='2674610'>that</span> <span m='2674790'>you</span> <span
  m='2674880'>begin</span> <span m='2675210'>thinking</span> <span
  m='2675630'>of</span> <span m='2675810'>it</span> <span m='2676350'>as</span>
  <span m='2676680'>a</span> <span m='2676740'>circular</span> <span
  m='2677280'>shift</span> <span m='2677850'>of</span> <span
  m='2678030'>just</span> <span m='2678270'>that</span> <span
  m='2678510'>one</span> <span m='2678750'>period.</span> </p><p><span
  m='2680500'>So,</span> <span m='2681270'>you</span> <span
  m='2681390'>can</span> <span m='2681540'>see</span> <span
  m='2681780'>that</span> <span m='2682080'>as</span> <span
  m='2682380'>we</span> <span m='2682530'>continue</span> <span
  m='2683040'>changing</span> <span m='2683520'>the</span> <span
  m='2683580'>value</span> <span m='2684000'>of</span> <span
  m='2684120'>n,</span> <span m='2685020'>then</span> <span
  m='2686010'>this</span> <span m='2686850'>one</span> <span
  m='2687090'>period</span> <span m='2687990'>gets</span> <span
  m='2688200'>circularly</span> <span m='2688920'>shifted.</span> <span
  m='2689910'>This</span> <span m='2690120'>value</span> <span
  m='2690510'>will</span> <span m='2690660'>end</span> <span
  m='2690840'>up</span> <span m='2691020'>over</span> <span
  m='2691290'>here,</span> <span m='2691590'>then</span> <span
  m='2691770'>this</span> <span m='2691980'>value</span> <span
  m='2692310'>will</span> <span m='2692460'>end</span> <span
  m='2692610'>up</span> <span m='2692790'>over</span> <span
  m='2693030'>here,</span> <span m='2693240'>et</span> <span
  m='2693650'>cetera.</span> <span m='2695070'>Well,</span> <span
  m='2695730'>if</span> <span m='2695880'>we</span> <span
  m='2696000'>carry</span> <span m='2696360'>out</span> <span
  m='2696510'>the</span> <span m='2696600'>convolution</span> <span
  m='2697650'>of</span> <span m='2698040'>x1</span> <span m='2698520'>of</span>
  <span m='2698610'>m</span> <span m='2699000'>and</span> <span
  m='2699150'>x2</span> <span m='2699570'>of</span> <span m='2699690'>m,</span>
  <span m='2700980'>for</span> <span m='2701220'>example</span> <span
  m='2701700'>for</span> <span m='2701880'>little</span> <span m='2702200'>n
  equals</span> <span m='2702600'>1,</span> <span m='2703340'>we</span> <span
  m='2703710'>take</span> <span m='2704040'>this,</span> <span
  m='2705060'>multiply</span> <span m='2705660'>it</span> <span
  m='2705750'>by</span> <span m='2705960'>that,</span> <span
  m='2706830'>and</span> <span m='2706950'>sum</span> <span
  m='2707250'>up</span> <span m='2707400'>the</span> <span
  m='2707520'>values</span> <span m='2707970'>in</span> <span
  m='2708030'>the</span> <span m='2708120'>range</span> <span
  m='2708420'>0</span> <span m='2709380'>to</span> <span
  m='2709620'>capital</span> <span m='2710100'>N</span> <span
  m='2710250'>minus</span> <span m='2710610'>1.</span> <span
  m='2712390'>Similarly</span> <span m='2712890'>for</span> <span
  m='2713070'>little</span> <span m='2713100'>n</span> <span
  m='2713280'>equals</span> <span m='2713700'>2,</span> <span
  m='2714350'>we</span> <span m='2714480'>take</span> <span
  m='2715200'>this</span> <span m='2716190'>and</span> <span
  m='2716550'>multiply</span> <span m='2717090'>it</span> <span
  m='2717180'>by</span> <span m='2717330'>that,</span> <span
  m='2717810'>sum</span> <span m='2718140'>up</span> <span
  m='2718290'>the</span> <span m='2718380'>values</span> <span
  m='2718920'>in</span> <span m='2719010'>the</span> <span
  m='2719100'>product</span> <span m='2719670'>in</span> <span
  m='2719760'>the</span> <span m='2719850'>range</span> <span
  m='2720120'>0</span> <span m='2720510'>to</span> <span
  m='2720660'>capital</span> <span m='2721140'>N</span> <span
  m='2721260'>minus</span> <span m='2721650'>1.</span> </p><p><span
  m='2723594'>One thing</span> <span m='2724080'>that</span> <span
  m='2724320'>you</span> <span m='2724470'>should</span> <span
  m='2724680'>be</span> <span m='2724830'>able</span> <span
  m='2725070'>to</span> <span m='2725190'>see</span> <span m='2725730'>in</span>
  <span m='2725850'>this</span> <span m='2726060'>example</span> <span
  m='2727320'>is</span> <span m='2727530'>that</span> <span
  m='2728880'>the</span> <span m='2729030'>answer</span> <span
  m='2729630'>will</span> <span m='2729840'>look</span> <span
  m='2730470'>quite</span> <span m='2730680'>a</span> <span
  m='2730740'>bit</span> <span m='2730920'>different</span> <span
  m='2731610'>than</span> <span m='2731760'>a</span> <span
  m='2731820'>linear</span> <span m='2732180'>convolution</span> <span
  m='2732900'>of</span> <span m='2733020'>these</span> <span
  m='2733300'>two,</span> <span m='2734550'>because</span> <span
  m='2735240'>in</span> <span m='2735390'>fact,</span> <span
  m='2736300'>notice</span> <span m='2736830'>that</span> <span
  m='2737340'>we're</span> <span m='2737520'>multiplying</span> <span
  m='2738150'>always</span> <span m='2739050'>by--</span> <span
  m='2740640'>let's</span> <span m='2740850'>call</span> <span
  m='2741060'>this</span> <span m='2741240'>amplitude</span> <span
  m='2741750'>1.</span> <span m='2742260'>We're</span> <span
  m='2742410'>multiplying</span> <span m='2742980'>always</span> <span
  m='2743370'>by</span> <span m='2743580'>1.</span> <span m='2744930'>And</span>
  <span m='2745080'>no</span> <span m='2745200'>matter</span> <span
  m='2745920'>how</span> <span m='2746340'>we</span> <span
  m='2746520'>circularly</span> <span m='2747150'>shifted</span> <span
  m='2748020'>this</span> <span m='2748200'>one</span> <span
  m='2748440'>period,</span> <span m='2749820'>each</span> <span
  m='2750090'>value</span> <span m='2750810'>would</span> <span
  m='2750990'>still</span> <span m='2751230'>get</span> <span
  m='2751410'>multiplied</span> <span m='2752010'>by</span> <span
  m='2752160'>the</span> <span m='2752280'>same</span> <span
  m='2752580'>amount.</span> <span m='2753820'>And</span> <span
  m='2753870'>consequently,</span> <span m='2754980'>the</span> <span
  m='2755100'>resulting</span> <span m='2755610'>values</span> <span
  m='2756060'>in</span> <span m='2756150'>the</span> <span
  m='2756240'>convolution</span> <span m='2757440'>will</span> <span
  m='2757590'>be</span> <span m='2758010'>the</span> <span
  m='2758130'>sum</span> <span m='2758670'>of</span> <span
  m='2758880'>these</span> <span m='2759120'>values</span> <span
  m='2760350'>no</span> <span m='2760500'>matter</span> <span
  m='2760770'>how</span> <span m='2760980'>much</span> <span
  m='2761190'>circular</span> <span m='2761940'>shifting</span> <span
  m='2762390'>that</span> <span m='2762480'>we</span> <span
  m='2762630'>do.</span> </p><p><span m='2763710'>So</span> <span
  m='2763920'>that</span> <span m='2764100'>for</span> <span
  m='2764220'>this</span> <span m='2764400'>particular</span> <span
  m='2764970'>example,</span> <span m='2766200'>the</span> <span
  m='2766320'>convolution</span> <span m='2767670'>comes</span> <span
  m='2768030'>out</span> <span m='2768780'>to</span> <span
  m='2768900'>look</span> <span m='2769410'>like</span> <span
  m='2769710'>this.</span> <span m='2770460'>That</span> <span
  m='2770670'>is</span> <span m='2771330'>the</span> <span
  m='2771420'>values</span> <span m='2771930'>in</span> <span
  m='2771990'>the</span> <span m='2772080'>convolution</span> <span
  m='2772950'>are</span> <span m='2773070'>constant</span> <span
  m='2774330'>over</span> <span m='2774570'>the</span> <span
  m='2774660'>range</span> <span m='2774930'>0</span> <span
  m='2775530'>to</span> <span m='2775650'>capital</span> <span
  m='2776100'>N</span> <span m='2776220'>minus</span> <span
  m='2776640'>1.</span> <span m='2777580'>Then</span> <span
  m='2777700'>of</span> <span m='2777800'>course,</span> <span
  m='2778090'>we</span> <span m='2778140'>had</span> <span
  m='2778590'>this</span> <span m='2779400'>either</span> <span
  m='2779640'>cutting</span> <span m='2779970'>the</span> <span
  m='2780110'>cylinder,</span> <span m='2780630'>if</span> <span
  m='2780720'>you</span> <span m='2780810'>want</span> <span
  m='2780990'>to</span> <span m='2781050'>look</span> <span
  m='2781230'>at</span> <span m='2781380'>it</span> <span
  m='2781500'>that</span> <span m='2781710'>way,</span> <span
  m='2782520'>or</span> <span m='2783180'>multiplying</span> <span
  m='2783510'>it</span> <span m='2783840'>by</span> <span m='2784050'>R</span>
  <span m='2784360'>sub</span> <span m='2784530'>capital</span> <span
  m='2785010'>N of</span> <span m='2785305'>n,</span> <span
  m='2786390'>and</span> <span m='2787320'>consequently</span> <span
  m='2788040'>we</span> <span m='2788130'>get</span> <span m='2788520'>0</span>
  <span m='2789030'>outside</span> <span m='2789510'>that</span> <span
  m='2789690'>range.</span> </p><p><span m='2791130'>All</span> <span
  m='2791220'>right.</span> <span m='2791430'>Well,</span> <span
  m='2791970'>what</span> <span m='2792180'>I</span> <span
  m='2792300'>would</span> <span m='2792450'>hope</span> <span
  m='2792840'>at</span> <span m='2792960'>this</span> <span
  m='2793170'>point,</span> <span m='2794330'>I</span> <span
  m='2794390'>would</span> <span m='2794550'>certainly</span> <span
  m='2794940'>expect</span> <span m='2795810'>that</span> <span
  m='2796830'>the</span> <span m='2797220'>idea</span> <span
  m='2797790'>of</span> <span m='2797910'>circular</span> <span
  m='2798330'>convolution</span> <span m='2799620'>isn't</span> <span
  m='2799890'>totally</span> <span m='2800310'>clear.</span> <span
  m='2801420'>I</span> <span m='2801480'>would</span> <span
  m='2801660'>expect</span> <span m='2802260'>that</span> <span
  m='2802560'>a</span> <span m='2802620'>little</span> <span
  m='2802950'>bit</span> <span m='2803100'>of</span> <span
  m='2803160'>the</span> <span m='2803280'>notion</span> <span
  m='2804090'>is</span> <span m='2804270'>coming</span> <span
  m='2804630'>out</span> <span m='2804780'>of</span> <span
  m='2804870'>the</span> <span m='2804990'>haze.</span> <span
  m='2805590'>That</span> <span m='2805800'>is</span> <span
  m='2806940'>the</span> <span m='2807090'>notion</span> <span
  m='2807900'>that</span> <span m='2808560'>things</span> <span
  m='2808860'>are</span> <span m='2808950'>being</span> <span
  m='2809190'>shifted</span> <span m='2809640'>circularly</span> <span
  m='2810840'>to</span> <span m='2810960'>implement</span> <span
  m='2811440'>the</span> <span m='2811560'>convolution.</span> <span
  m='2812760'>That's</span> <span m='2813000'>the</span> <span
  m='2813090'>kind</span> <span m='2813360'>of</span> <span
  m='2813450'>idea</span> <span m='2814080'>that</span> <span
  m='2814230'>I</span> <span m='2814320'>would</span> <span
  m='2814470'>hope</span> <span m='2815190'>is</span> <span
  m='2815460'>becoming</span> <span m='2815880'>somewhat</span> <span
  m='2816420'>clearer.</span> <span m='2817920'>And</span> <span
  m='2819330'>in</span> <span m='2819810'>the</span> <span
  m='2819930'>next</span> <span m='2820200'>lecture,</span> <span
  m='2821350'>what</span> <span m='2821700'>I</span> <span
  m='2822090'>intend</span> <span m='2822420'>to</span> <span
  m='2822540'>focus</span> <span m='2823020'>on</span> <span
  m='2823620'>entirely</span> <span m='2825270'>is</span> <span
  m='2825870'>the</span> <span m='2826500'>additional</span> <span
  m='2827040'>interpretation</span> <span m='2828090'>of</span> <span
  m='2828240'>circular</span> <span m='2828690'>convolution,</span> <span
  m='2829980'>with</span> <span m='2830160'>the</span> <span
  m='2830250'>hope</span> <span m='2831690'>that</span> <span
  m='2832080'>by</span> <span m='2832260'>the</span> <span
  m='2832440'>end</span> <span m='2832590'>of</span> <span
  m='2832680'>the</span> <span m='2832770'>next</span> <span
  m='2833070'>lecture</span> <span m='2833910'>the</span> <span
  m='2834360'>notions</span> <span m='2834870'>of</span> <span
  m='2834960'>the</span> <span m='2835080'>circular</span> <span
  m='2835530'>shifting</span> <span m='2836580'>and</span> <span
  m='2836700'>the</span> <span m='2836790'>difference</span> <span
  m='2837900'>between</span> <span m='2838650'>circular</span> <span
  m='2839190'>convolution</span> <span m='2840060'>and</span> <span
  m='2840240'>linear</span> <span m='2840570'>convolution</span> <span
  m='2841770'>will</span> <span m='2841860'>be</span> <span
  m='2841980'>clear.</span> <span m='2842680'>Thank</span> <span
  m='2842850'>you.</span> </p>
embedded_media:
  - uid: bc8229ecb3a6d43e355279a65ee917b0
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: MITRES_6_008S11_lec09.pdf
    title: MITRES_6_008S11_lec09.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-9-the-discrete-fourier-transform/MITRES_6_008S11_lec09.pdf
  - uid: 2109c10f2552ccacb9a9900909626352
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: rF5sEfhttwo
  - uid: 2d7656589549953c8b32c2ad027d2402
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-9-the-discrete-fourier/id481803782?i=108361991
  - uid: ad1277f24eba9eedee20648a6d3514e3
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec09_300k.mp4'
  - uid: a5784bf17a293e3776c1e6fc8bb420d2
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/rF5sEfhttwo/default.jpg'
  - uid: df12b2d5cf3d107fa148a4bcf1242a0a
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: rF5sEfhttwo
  - uid: 3aee0ddf252e676ea3239cc66b14979c
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: rF5sEfhttwo.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-9-the-discrete-fourier-transform/rF5sEfhttwo.srt
  - uid: d745859c68f45d7156bba93a065ae9b4
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: rF5sEfhttwo.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-9-the-discrete-fourier-transform/rF5sEfhttwo.pdf
  - uid: 3d1d210f92d05a2b616ffacd959a4fd2
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 4e4d2db989d0bf6c19100c714837423d
    parent_uid: d4534d465dd769973625f4b9450efcf6
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
