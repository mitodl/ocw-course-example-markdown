---
order_index: null
title: 'Lecture 10: Circular Convolution'
template_type: Tabbed
uid: beb398bc1fe767e77ddd11c3f1e945a1
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-10-circular-convolution
short_url: lecture-10-circular-convolution
inline_embed_id: '3375377lecture10:circularconvolution80037508'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Circular convolution of finite length
  sequences, interpretation of circular convolution as linear convolution
  followed by aliasing, implementing linear convolution by means of circular
  convolution.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Circular Convolution (<a
  href="./resolveuid/b65341ff1254d6ceec7b122ed2c32295">PDF</a>)</p>
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
  m='25494'>[MUSIC PLAYING]</span> </p><p></p><p><span
  m='55630'>PROFESSOR:</span> <span m='55870'>When</span> <span
  m='56110'>we</span> <span m='56500'>introduced</span> <span
  m='57080'>the</span> <span m='57360'>discrete</span> <span
  m='57790'>Fourier</span> <span m='58150'>transform,</span> <span
  m='59320'>one</span> <span m='59560'>of</span> <span m='59800'>the</span>
  <span m='60340'>important</span> <span m='61300'>aspects</span> <span
  m='61990'>of</span> <span m='62080'>that</span> <span
  m='62230'>transform</span> <span m='62920'>that</span> <span
  m='63040'>I</span> <span m='63130'>stressed</span> <span m='64390'>was</span>
  <span m='65080'>the</span> <span m='65170'>fact</span> <span
  m='65770'>that</span> <span m='66790'>the</span> <span
  m='66970'>discrete</span> <span m='67360'>Fourier</span> <span
  m='67660'>transform,</span> <span m='68260'>as</span> <span
  m='68350'>opposed</span> <span m='68890'>to</span> <span m='69250'>the</span>
  <span m='69400'>Fourier</span> <span m='70000'>or</span> <span
  m='70120'>z</span> <span m='70330'>transform,</span> <span
  m='71800'>actually</span> <span m='72430'>has</span> <span
  m='72910'>implications</span> <span m='73930'>in</span> <span
  m='74080'>terms</span> <span m='74650'>of</span> <span
  m='75010'>implementing</span> <span m='76180'>discrete</span> <span
  m='76600'>time</span> <span m='76900'>linear</span> <span
  m='77200'>systems.</span> <span m='79330'>I</span> <span
  m='79570'>commented,</span> <span m='80350'>or</span> <span
  m='80650'>suggested,</span> <span m='81940'>that</span> <span
  m='82360'>in</span> <span m='82510'>fact,</span> <span m='83410'>a</span>
  <span m='84670'>linear</span> <span m='85030'>system,</span> <span
  m='85540'>or</span> <span m='85670'>a</span> <span m='85720'>digital</span>
  <span m='86110'>filter</span> <span m='87310'>could</span> <span
  m='88270'>be</span> <span m='88900'>implemented</span> <span
  m='89590'>explicitly</span> <span m='91000'>by</span> <span
  m='91750'>computing</span> <span m='92730'>the</span> <span
  m='92820'>discrete</span> <span m='93230'>Fourier</span> <span
  m='93640'>transform</span> <span m='94630'>of</span> <span m='94750'>a</span>
  <span m='94810'>unit</span> <span m='95110'>sample</span> <span
  m='95530'>response</span> <span m='96700'>and</span> <span m='96880'>an</span>
  <span m='96970'>input</span> <span m='97390'>sequence,</span> <span
  m='98560'>multiplying</span> <span m='99250'>these</span> <span
  m='99430'>transforms</span> <span m='100120'>together,</span> <span
  m='101050'>and</span> <span m='101200'>then</span> <span
  m='101410'>computing</span> <span m='101920'>the</span> <span
  m='102070'>inverse</span> <span m='102670'>discrete</span> <span
  m='103060'>Fourier</span> <span m='103450'>transform.</span> </p><p><span
  m='106300'>There</span> <span m='107350'>is</span> <span m='108220'>a</span>
  <span m='108730'>very</span> <span m='109060'>efficient</span> <span
  m='109510'>algorithm,</span> <span m='110110'>in</span> <span
  m='110230'>fact,</span> <span m='110980'>for</span> <span
  m='111670'>computing</span> <span m='112300'>the</span> <span
  m='112390'>discrete</span> <span m='112780'>Fourier</span> <span
  m='113220'>transform.</span> <span m='114710'>And</span> <span
  m='115060'>so</span> <span m='115450'>it</span> <span m='115570'>will</span>
  <span m='115750'>turn</span> <span m='116050'>out,</span> <span
  m='116350'>and</span> <span m='116470'>we</span> <span m='116650'>won't</span>
  <span m='116890'>see</span> <span m='117100'>this</span> <span
  m='117520'>right</span> <span m='117760'>away,</span> <span
  m='118060'>but</span> <span m='118270'>we'll</span> <span
  m='118450'>see</span> <span m='118630'>it</span> <span
  m='118720'>toward</span> <span m='118990'>the</span> <span
  m='119110'>end</span> <span m='119260'>of</span> <span m='119350'>this</span>
  <span m='119470'>set</span> <span m='119710'>of</span> <span
  m='119800'>lectures,</span> <span m='120970'>it</span> <span
  m='121030'>will</span> <span m='121180'>turn</span> <span
  m='121480'>out</span> <span m='121900'>that,</span> <span m='122200'>in</span>
  <span m='122320'>fact,</span> <span m='122650'>that's</span> <span
  m='122830'>a</span> <span m='122890'>very</span> <span
  m='123370'>efficient</span> <span m='123910'>way,</span> <span
  m='124570'>often</span> <span m='125580'>of</span> <span
  m='126280'>implementing</span> <span m='127120'>a</span> <span
  m='127180'>convolution</span> <span m='128110'>or</span> <span
  m='128530'>implementing</span> <span m='129160'>a</span> <span
  m='129220'>digital</span> <span m='129580'>filter.</span> </p><p><span
  m='131660'>Well,</span> <span m='131860'>in</span> <span m='131980'>the</span>
  <span m='132070'>last</span> <span m='132400'>lecture,</span> <span
  m='133460'>we</span> <span m='133840'>saw</span> <span m='134590'>that</span>
  <span m='135490'>computing</span> <span m='136060'>discrete</span> <span
  m='136470'>Fourier</span> <span m='136880'>transforms,</span> <span
  m='138070'>multiplying</span> <span m='138730'>those</span> <span
  m='139000'>together,</span> <span m='140020'>and</span> <span
  m='140140'>then</span> <span m='140290'>computing</span> <span
  m='140770'>the</span> <span m='140920'>inverse</span> <span
  m='141550'>discrete</span> <span m='141970'>Fourier</span> <span
  m='142420'>transform</span> <span m='143800'>doesn't</span> <span
  m='144550'>give</span> <span m='144760'>us</span> <span m='145150'>a</span>
  <span m='145210'>convolution</span> <span m='146740'>in</span> <span
  m='146830'>the</span> <span m='146920'>usual</span> <span
  m='147400'>sense.</span> <span m='148010'>In</span> <span
  m='148110'>other</span> <span m='148210'>words,</span> <span
  m='148490'>it</span> <span m='148590'>doesn't</span> <span
  m='148750'>give</span> <span m='148930'>us</span> <span m='149020'>a</span>
  <span m='149080'>linear</span> <span m='149500'>convolution,</span> <span
  m='151000'>it</span> <span m='151120'>gives</span> <span m='151390'>us</span>
  <span m='151630'>a</span> <span m='151690'>circular</span> <span
  m='152230'>convolution.</span> <span m='153990'>And</span> <span
  m='154120'>one</span> <span m='154300'>of</span> <span m='154390'>the</span>
  <span m='154480'>important</span> <span m='154930'>considerations</span> <span
  m='156370'>in</span> <span m='156490'>using</span> <span m='156880'>the</span>
  <span m='156970'>discrete</span> <span m='157360'>Fourier</span> <span
  m='157760'>transform</span> <span m='158560'>to</span> <span
  m='158710'>implement</span> <span m='159190'>a</span> <span
  m='159280'>digital</span> <span m='159640'>filter</span> <span
  m='160210'>or</span> <span m='160420'>a</span> <span
  m='160450'>discrete</span> <span m='160870'>time</span> <span
  m='161170'>system</span> <span m='162310'>is</span> <span m='163000'>to</span>
  <span m='163180'>account</span> <span m='163600'>for</span> <span
  m='163750'>this</span> <span m='163930'>circularity,</span> <span
  m='165340'>or</span> <span m='166030'>to</span> <span m='167170'>modify</span>
  <span m='168190'>the</span> <span m='168280'>circular</span> <span
  m='168760'>convolution</span> <span m='169600'>so</span> <span
  m='169720'>that</span> <span m='169900'>it</span> <span
  m='169990'>looks</span> <span m='170260'>like</span> <span m='170440'>a</span>
  <span m='170500'>linear</span> <span m='170860'>convolution.</span>
  </p><p><span m='172840'>So</span> <span m='173200'>in</span> <span
  m='173290'>this</span> <span m='173500'>lecture,</span> <span
  m='174290'>what</span> <span m='174550'>I</span> <span m='174700'>would</span>
  <span m='174910'>like</span> <span m='175150'>to</span> <span
  m='175270'>concentrate</span> <span m='175990'>on,</span> <span
  m='176230'>in</span> <span m='176320'>fact</span> <span
  m='176590'>entirely</span> <span m='177220'>for</span> <span
  m='177340'>the</span> <span m='177430'>whole</span> <span
  m='177610'>lecture,</span> <span m='178720'>is</span> <span
  m='179590'>a</span> <span m='179920'>discussion</span> <span
  m='180730'>of</span> <span m='180850'>circular</span> <span
  m='181330'>convolution,</span> <span m='182350'>with</span> <span
  m='182560'>the</span> <span m='182650'>hope</span> <span
  m='183310'>that</span> <span m='183610'>at</span> <span m='183700'>the</span>
  <span m='183850'>end</span> <span m='184000'>of</span> <span
  m='184120'>this</span> <span m='184360'>lecture</span> <span
  m='185170'>there</span> <span m='185470'>will</span> <span
  m='185710'>be</span> <span m='186160'>a</span> <span m='186700'>very</span>
  <span m='187030'>intuitive</span> <span m='187480'>feeling</span> <span
  m='188470'>for</span> <span m='188620'>what</span> <span
  m='188830'>circular</span> <span m='189310'>convolution</span> <span
  m='190090'>means.</span> <span m='191200'>And</span> <span
  m='191320'>then</span> <span m='191530'>also,</span> <span
  m='192190'>how</span> <span m='192430'>you</span> <span m='192580'>can</span>
  <span m='192790'>use</span> <span m='193060'>circular</span> <span
  m='193570'>convolution</span> <span m='194920'>to</span> <span
  m='195310'>implement</span> <span m='196000'>a</span> <span
  m='196060'>linear</span> <span m='196420'>convolution,</span> <span
  m='197380'>and</span> <span m='197500'>consequently,</span> <span
  m='198820'>to</span> <span m='199090'>implement</span> <span
  m='199690'>a</span> <span m='199750'>discrete</span> <span
  m='200200'>time</span> <span m='200530'>linear</span> <span
  m='200860'>system,</span> <span m='201950'>for</span> <span
  m='202030'>example,</span> <span m='202510'>to</span> <span
  m='202630'>implement</span> <span m='203080'>a</span> <span
  m='203140'>digital</span> <span m='203530'>filter.</span> </p><p><span
  m='205250'>Well,</span> <span m='205450'>first</span> <span
  m='205780'>of</span> <span m='205900'>all,</span> <span m='206200'>to</span>
  <span m='206620'>remind</span> <span m='207130'>you</span> <span
  m='207610'>of</span> <span m='208510'>the</span> <span
  m='209500'>convolution</span> <span m='210250'>property</span> <span
  m='211300'>that</span> <span m='211450'>we</span> <span
  m='211630'>derived</span> <span m='212110'>last</span> <span
  m='212440'>time,</span> <span m='214300'>we</span> <span
  m='214360'>found</span> <span m='214810'>that</span> <span
  m='214990'>multiplying</span> <span m='215680'>discrete</span> <span
  m='216090'>Fourier</span> <span m='216490'>transforms</span> <span
  m='217840'>leads</span> <span m='218290'>to</span> <span m='218560'>a</span>
  <span m='218650'>circular</span> <span m='219130'>convolution,</span> <span
  m='219940'>which</span> <span m='220150'>we</span> <span
  m='220300'>denoted</span> <span m='221410'>with</span> <span
  m='222240'>an</span> <span m='222470'>n</span> <span m='222850'>and</span>
  <span m='223060'>a</span> <span m='223120'>circle</span> <span
  m='223540'>around</span> <span m='223930'>it,</span> <span
  m='224530'>meaning</span> <span m='225010'>an</span> <span m='225160'>N
  point</span> <span m='225790'>circular</span> <span
  m='226270'>convolution.</span> <span m='228130'>And</span> <span
  m='228790'>what</span> <span m='229030'>that</span> <span
  m='229690'>basically</span> <span m='230320'>corresponded</span> <span
  m='231130'>to</span> <span m='232480'>was</span> <span m='232960'>a</span>
  <span m='233050'>periodic</span> <span m='233710'>convolution</span> <span
  m='235240'>of</span> <span m='235390'>two</span> <span
  m='235600'>periodic</span> <span m='236290'>sequences,</span> <span
  m='237700'>which</span> <span m='237910'>are</span> <span
  m='238000'>generated</span> <span m='239140'>from</span> <span
  m='239350'>these</span> <span m='240100'>finite</span> <span
  m='240550'>length</span> <span m='240850'>sequences,</span> <span
  m='242170'>by</span> <span m='242410'>periodically</span> <span
  m='243520'>repeating</span> <span m='244060'>them</span> <span
  m='244690'>with</span> <span m='244840'>a</span> <span
  m='244900'>period</span> <span m='245590'>of</span> <span
  m='245740'>capital</span> <span m='246310'>N.</span> <span
  m='247630'>And</span> <span m='247750'>then</span> <span
  m='247960'>finally,</span> <span m='248980'>extracting</span> <span
  m='250150'>one</span> <span m='250600'>N point</span> <span
  m='251200'>period</span> <span m='251920'>from</span> <span
  m='252160'>that.</span> <span m='252880'>The</span> <span
  m='253000'>result</span> <span m='253720'>being</span> <span
  m='254520'>the</span> <span m='254650'>circular</span> <span
  m='255100'>convolution</span> <span m='256060'>of</span> <span
  m='256630'>x1</span> <span m='256910'>of</span> <span m='257170'>n</span>
  <span m='257890'>with</span> <span m='258040'>x2</span> <span m='258490'>of
  n.</span> </p><p><span m='260649'>Notationally,</span> <span
  m='261670'>also</span> <span m='262930'>sometimes</span> <span
  m='263560'>we</span> <span m='263680'>wrote</span> <span
  m='263980'>this</span> <span m='264220'>in</span> <span m='264310'>a</span>
  <span m='264370'>slightly</span> <span m='264760'>different</span> <span
  m='265180'>way</span> <span m='266710'>where</span> <span
  m='267370'>the</span> <span m='267610'>periodic</span> <span
  m='268570'>sequence,</span> <span m='269290'>x1</span> <span
  m='269720'>tilde</span> <span m='270340'>of</span> <span m='270580'>m</span>
  <span m='270940'>or</span> <span m='271150'>n</span> <span
  m='271960'>could</span> <span m='272290'>also</span> <span
  m='272740'>be</span> <span m='272890'>written</span> <span
  m='273490'>with</span> <span m='273670'>a</span> <span
  m='273700'>modular</span> <span m='274210'>notation,</span> <span
  m='274675'>a</span> <span m='275140'>double</span> <span
  m='275470'>parentheses,</span> <span m='276220'>and</span> <span
  m='276310'>a</span> <span m='276370'>subscript</span> <span
  m='277420'>capital</span> <span m='277930'>N,</span> <span
  m='278680'>indicating</span> <span m='279610'>that</span> <span
  m='280240'>x1</span> <span m='280800'>of</span> <span m='280930'>n</span>
  <span m='281320'>or</span> <span m='281530'>m--</span> <span
  m='283396'>x1</span> <span m='284110'>tilde</span> <span m='284570'>of</span>
  <span m='284720'>m</span> <span m='285110'>is</span> <span
  m='285260'>generated</span> <span m='285830'>from</span> <span
  m='286030'>x1</span> <span m='286490'>of</span> <span m='286580'>m</span>
  <span m='287270'>by</span> <span m='287420'>simply</span> <span
  m='287810'>taking</span> <span m='288230'>this</span> <span
  m='288440'>argument,</span> <span m='289280'>modulo</span> <span
  m='289595'>capital</span> <span m='289910'>M--</span> <span
  m='290790'>capital</span> <span m='291260'>N.</span> </p><p><span
  m='292610'>So</span> <span m='292790'>this</span> <span m='293000'>is</span>
  <span m='293150'>an</span> <span m='293240'>alternative</span> <span
  m='294110'>way</span> <span m='294590'>of</span> <span
  m='294770'>writing</span> <span m='295190'>this.</span> <span
  m='296090'>And</span> <span m='296210'>finally,</span> <span
  m='296810'>I</span> <span m='296930'>pointed</span> <span
  m='297380'>out</span> <span m='297710'>in</span> <span m='297830'>the</span>
  <span m='297890'>last</span> <span m='298250'>lecture,</span> <span
  m='299360'>that</span> <span m='299840'>if</span> <span m='300020'>we</span>
  <span m='300230'>just</span> <span m='300650'>look</span> <span
  m='300950'>at</span> <span m='301040'>this</span> <span
  m='301250'>expression,</span> <span m='303030'>we</span> <span
  m='303080'>see</span> <span m='303440'>that</span> <span m='303650'>x1</span>
  <span m='304190'>tilde</span> <span m='304570'>of</span> <span
  m='304750'>m,</span> <span m='305240'>or</span> <span
  m='305450'>equivalently</span> <span m='306710'>x1</span> <span
  m='308090'>of</span> <span m='308350'>m,</span> <span m='308870'>modulo</span>
  <span m='309440'>capital</span> <span m='310010'>N,</span> <span
  m='311720'>only</span> <span m='312080'>involves</span> <span
  m='312710'>values</span> <span m='313250'>of</span> <span
  m='313340'>this</span> <span m='313580'>argument</span> <span
  m='314540'>from</span> <span m='314750'>0</span> <span m='315350'>to</span>
  <span m='315500'>capital</span> <span m='315980'>N</span> <span
  m='316160'>minus</span> <span m='316580'>1</span> <span m='317280'>and</span>
  <span m='317630'>consequently</span> <span m='318440'>as</span> <span
  m='318560'>an</span> <span m='318650'>alternative,</span> <span
  m='319890'>we</span> <span m='319940'>can</span> <span
  m='320510'>replace</span> <span m='321400'>here</span> <span
  m='322400'>x1</span> <span m='323120'>of</span> <span m='323280'>m.</span>
  <span m='324710'>So</span> <span m='324890'>this</span> <span
  m='325310'>was</span> <span m='325850'>an</span> <span
  m='325970'>expression</span> <span m='327170'>for</span> <span
  m='327800'>circular</span> <span m='328340'>convolution</span> <span
  m='329810'>of</span> <span m='330440'>the</span> <span m='330560'>two</span>
  <span m='330800'>finite</span> <span m='331250'>length</span> <span
  m='331490'>sequences</span> <span m='332300'>x1</span> <span
  m='332590'>of</span> <span m='332880'>n</span> <span m='333290'>and</span>
  <span m='333440'>x2</span> <span m='333650'>of</span> <span
  m='333890'>n.</span> </p><p><span m='335370'>To</span> <span
  m='335490'>remind</span> <span m='335940'>you</span> <span
  m='336300'>of</span> <span m='337470'>how</span> <span m='338040'>the</span>
  <span m='338160'>mechanics</span> <span m='338940'>of</span> <span
  m='339570'>the</span> <span m='339690'>circular</span> <span
  m='340140'>convolution</span> <span m='341190'>are</span> <span
  m='341310'>carried</span> <span m='341730'>out,</span> <span
  m='343080'>I</span> <span m='343200'>showed</span> <span m='343530'>you</span>
  <span m='343650'>last</span> <span m='343980'>time</span> <span
  m='344970'>the</span> <span m='345090'>circular</span> <span
  m='345510'>convolution</span> <span m='346980'>of</span> <span
  m='347640'>one</span> <span m='347880'>finite</span> <span
  m='348330'>length</span> <span m='348540'>sequence,</span> <span
  m='349110'>x1</span> <span m='349590'>of</span> <span m='349710'>m</span>
  <span m='350610'>and</span> <span m='350760'>x2</span> <span
  m='351270'>of</span> <span m='351400'>m.</span> <span m='352470'>And</span>
  <span m='353070'>let</span> <span m='353280'>me</span> <span
  m='353460'>re-stress</span> <span m='354300'>a</span> <span
  m='354360'>couple</span> <span m='354720'>of</span> <span
  m='354810'>important</span> <span m='355290'>points.</span> <span
  m='356830'>First</span> <span m='357060'>of</span> <span
  m='357180'>all,</span> <span m='357960'>we</span> <span m='358080'>form</span>
  <span m='358620'>from</span> <span m='358830'>x1</span> <span
  m='359280'>of</span> <span m='359380'>m,</span> <span m='360660'>rather</span>
  <span m='360960'>from</span> <span m='361140'>x2</span> <span
  m='361350'>two</span> <span m='361590'>of</span> <span m='361700'>m,</span>
  <span m='362610'>x2</span> <span m='363330'>of</span> <span
  m='363840'>n</span> <span m='364290'>minus</span> <span m='364800'>m</span>
  <span m='365310'>modulo</span> <span m='365850'>capital</span> <span
  m='366390'>N.</span> <span m='367500'>And</span> <span m='367650'>for</span>
  <span m='367860'>example,</span> <span m='368740'>if</span> <span
  m='368820'>little</span> <span m='369120'>n</span> <span
  m='369240'>equals</span> <span m='369540'>0,</span> <span m='369990'>so</span>
  <span m='370200'>that</span> <span m='370350'>we're</span> <span
  m='370470'>looking</span> <span m='370830'>at</span> <span
  m='370950'>x2</span> <span m='371580'>of</span> <span m='371760'>minus</span>
  <span m='372210'>m</span> <span m='372430'>modulo</span> <span
  m='372930'>capital</span> <span m='373470'>N,</span> <span
  m='374580'>that</span> <span m='374790'>corresponds</span> <span
  m='375510'>to</span> <span m='375660'>flipping</span> <span
  m='376170'>this</span> <span m='376380'>over</span> <span
  m='377550'>and</span> <span m='377730'>then</span> <span
  m='378390'>taking</span> <span m='378810'>the</span> <span
  m='378900'>values,</span> <span m='379920'>module</span> <span
  m='380580'>capital</span> <span m='381150'>N,</span> <span
  m='382140'>which</span> <span m='382620'>basically</span> <span
  m='383730'>corresponds</span> <span m='384510'>to</span> <span
  m='384630'>flipping</span> <span m='385090'>this</span> <span
  m='385290'>over,</span> <span m='386100'>the</span> <span
  m='386220'>points</span> <span m='386580'>that</span> <span
  m='386700'>come</span> <span m='386940'>off</span> <span m='387180'>the</span>
  <span m='387360'>end</span> <span m='388110'>get</span> <span
  m='388260'>wrapped</span> <span m='388620'>around</span> <span
  m='389370'>back</span> <span m='389650'>onto</span> <span
  m='389940'>this</span> <span m='390150'>side,</span> <span
  m='391080'>as</span> <span m='391260'>I've</span> <span
  m='391410'>illustrated</span> <span m='392040'>here.</span> <span
  m='393690'>Then</span> <span m='394080'>if</span> <span m='394320'>we</span>
  <span m='394440'>shift,</span> <span m='395040'>and</span> <span
  m='395520'>I've</span> <span m='395850'>indicated</span> <span
  m='396420'>with</span> <span m='396540'>these</span> <span
  m='396780'>dashed</span> <span m='397200'>lines</span> <span
  m='398100'>what</span> <span m='398280'>would</span> <span
  m='398460'>correspond</span> <span m='399180'>to</span> <span
  m='399300'>the</span> <span m='399390'>periodic</span> <span
  m='400170'>extension</span> <span m='401010'>of</span> <span
  m='401190'>this,</span> <span m='401980'>although</span> <span
  m='402450'>it's</span> <span m='402660'>the</span> <span
  m='402810'>interval</span> <span m='403260'>from</span> <span
  m='403470'>0</span> <span m='404460'>to</span> <span m='404550'>capital</span>
  <span m='405030'>N</span> <span m='405180'>minus</span> <span
  m='405600'>1,</span> <span m='406660'>which</span> <span m='406800'>is</span>
  <span m='406920'>the</span> <span m='407040'>interval</span> <span
  m='407460'>that</span> <span m='407580'>I</span> <span m='407640'>want</span>
  <span m='407820'>to</span> <span m='407880'>focus</span> <span
  m='408330'>on.</span> </p><p><span m='409230'>All</span> <span
  m='409320'>right.</span> <span m='409620'>Well,</span> <span
  m='410070'>now</span> <span m='410340'>as</span> <span m='410460'>we</span>
  <span m='410550'>change</span> <span m='411030'>n,</span> <span
  m='411480'>if</span> <span m='411660'>this</span> <span m='411870'>is</span>
  <span m='412080'>generally</span> <span m='412590'>n</span> <span
  m='412830'>minus</span> <span m='413220'>m,</span> <span
  m='414390'>that</span> <span m='414570'>corresponds</span> <span
  m='415290'>to</span> <span m='415440'>a</span> <span m='415500'>shift</span>
  <span m='416040'>left</span> <span m='416400'>or</span> <span
  m='416490'>right</span> <span m='416760'>of</span> <span
  m='416880'>this</span> <span m='417060'>sequence.</span> <span
  m='418560'>And</span> <span m='418860'>if,</span> <span
  m='419630'>let's</span> <span m='419880'>say</span> <span m='420210'>we</span>
  <span m='420360'>look</span> <span m='420600'>at</span> <span
  m='420780'>x2</span> <span m='421620'>of</span> <span m='422130'>1</span>
  <span m='422400'>minus</span> <span m='422820'>m,</span> <span
  m='423440'>modulo</span> <span m='423960'>capital</span> <span
  m='424500'>N.</span> <span m='425790'>That</span> <span
  m='425970'>corresponds</span> <span m='426840'>to</span> <span
  m='426960'>shifting</span> <span m='427530'>this</span> <span
  m='427710'>sequence</span> <span m='428610'>to</span> <span
  m='428730'>the</span> <span m='428880'>right</span> <span m='429480'>by</span>
  <span m='429660'>one</span> <span m='429930'>point.</span> <span
  m='431040'>And</span> <span m='431190'>as</span> <span m='431400'>this</span>
  <span m='431670'>point</span> <span m='432330'>falls</span> <span
  m='432780'>off</span> <span m='432990'>the</span> <span m='433170'>end,</span>
  <span m='433950'>it</span> <span m='434070'>wraps</span> <span
  m='434430'>around</span> <span m='435200'>to</span> <span
  m='435330'>the</span> <span m='435480'>other</span> <span
  m='435690'>side,</span> <span m='436660'>which</span> <span
  m='436770'>is</span> <span m='436890'>what</span> <span m='437100'>I've</span>
  <span m='437160'>illustrated</span> <span m='437820'>here.</span> <span
  m='438810'>And</span> <span m='438900'>then</span> <span m='439110'>if</span>
  <span m='439230'>we</span> <span m='439350'>shift</span> <span
  m='440670'>so</span> <span m='440880'>that</span> <span
  m='441090'>little</span> <span m='441390'>n</span> <span m='441570'>is</span>
  <span m='441720'>equal</span> <span m='441990'>to</span> <span
  m='442170'>2,</span> <span m='443100'>another</span> <span
  m='443460'>point</span> <span m='443940'>wraps</span> <span
  m='444330'>around</span> <span m='445710'>the</span> <span
  m='445860'>end,</span> <span m='446280'>as</span> <span m='446520'>I've</span>
  <span m='446700'>indicated,</span> <span m='447380'>et</span> <span
  m='447690'>cetera.</span> <span m='448320'>And</span> <span
  m='448440'>that's</span> <span m='448710'>the</span> <span
  m='448830'>kind</span> <span m='449070'>of</span> <span
  m='449160'>shifting</span> <span m='450060'>that</span> <span
  m='450180'>gets</span> <span m='450450'>carried</span> <span
  m='450870'>out.</span> <span m='451540'>In</span> <span
  m='451640'>other</span> <span m='451650'>words,</span> <span
  m='451990'>it's</span> <span m='452010'>a</span> <span
  m='452100'>circular</span> <span m='452640'>shift</span> <span
  m='453210'>that's</span> <span m='453420'>implemented.</span> </p><p><span
  m='454510'>To</span> <span m='454650'>form</span> <span m='454950'>the</span>
  <span m='455040'>convolution,</span> <span m='455930'>then</span> <span
  m='456900'>for</span> <span m='457110'>example,</span> <span
  m='457365'>for</span> <span m='457620'>little</span> <span m='457770'>n</span>
  <span m='458010'>equals</span> <span m='458460'>1,</span> <span
  m='459420'>we</span> <span m='459570'>multiply</span> <span
  m='460500'>this</span> <span m='460740'>set</span> <span m='460980'>of</span>
  <span m='461070'>values</span> <span m='462420'>by</span> <span
  m='462600'>this</span> <span m='462780'>set</span> <span m='463020'>of</span>
  <span m='463110'>values</span> <span m='464670'>and</span> <span
  m='465030'>carry</span> <span m='465510'>out</span> <span
  m='465690'>the</span> <span m='465780'>sum.</span> <span m='466740'>And</span>
  <span m='467010'>as</span> <span m='467190'>I</span> <span
  m='467310'>indicated</span> <span m='467850'>last</span> <span
  m='468180'>time,</span> <span m='468690'>it's</span> <span
  m='468870'>straightforward</span> <span m='469530'>to</span> <span
  m='469650'>see</span> <span m='470040'>that</span> <span m='470190'>the</span>
  <span m='470310'>answer</span> <span m='470610'>comes</span> <span
  m='470910'>out</span> <span m='471240'>to</span> <span m='471360'>be</span>
  <span m='471510'>unity</span> <span m='472680'>over</span> <span
  m='472920'>the</span> <span m='473070'>interval</span> <span
  m='473490'>0</span> <span m='474090'>to</span> <span m='474210'>capital</span>
  <span m='474690'>N</span> <span m='474810'>minus</span> <span
  m='475200'>1.</span> <span m='476220'>But</span> <span m='476400'>the</span>
  <span m='476490'>important</span> <span m='476970'>point,</span> <span
  m='477390'>and</span> <span m='477480'>the</span> <span
  m='477720'>important</span> <span m='478320'>picture</span> <span
  m='478710'>that</span> <span m='478830'>I</span> <span m='478950'>tried</span>
  <span m='479250'>to</span> <span m='479370'>stress</span> <span
  m='479730'>last</span> <span m='480090'>time,</span> <span
  m='481080'>was</span> <span m='481290'>the</span> <span
  m='481410'>notion</span> <span m='482310'>of</span> <span
  m='482700'>thinking</span> <span m='483300'>of</span> <span
  m='483450'>the</span> <span m='483570'>sequences</span> <span
  m='484950'>as</span> <span m='485070'>being</span> <span
  m='485310'>wrapped</span> <span m='485700'>around</span> <span
  m='486030'>a</span> <span m='486090'>cylinder,</span> <span
  m='486450'>x1</span> <span m='487080'>of</span> <span m='487350'>n</span>
  <span m='487530'>wrapped</span> <span m='487860'>around</span> <span
  m='488160'>a</span> <span m='488220'>cylinder,</span> <span
  m='489290'>x2</span> <span m='490090'>of</span> <span m='490290'>minus</span>
  <span m='490770'>n</span> <span m='491280'>wrapped</span> <span
  m='491610'>around</span> <span m='491940'>a</span> <span
  m='492000'>cylinder,</span> <span m='493110'>one</span> <span
  m='493320'>cylinder</span> <span m='493800'>put</span> <span
  m='494040'>inside</span> <span m='494460'>the</span> <span
  m='494640'>other,</span> <span m='495330'>and</span> <span
  m='495420'>then</span> <span m='495570'>as</span> <span m='495690'>we</span>
  <span m='495810'>form</span> <span m='496140'>the</span> <span
  m='496230'>convolution,</span> <span m='497520'>the</span> <span
  m='497610'>cylinders</span> <span m='498150'>are</span> <span
  m='498630'>turned</span> <span m='499080'>with</span> <span
  m='499230'>respect</span> <span m='499650'>to</span> <span
  m='499770'>each</span> <span m='499980'>other,</span> <span
  m='500700'>and</span> <span m='501420'>the</span> <span
  m='501510'>values</span> <span m='501960'>multiplied--</span> <span
  m='503640'>successive</span> <span m='504180'>values</span> <span
  m='504540'>multiplied</span> <span m='505740'>and</span> <span
  m='505890'>then</span> <span m='506250'>added</span> <span
  m='506880'>around</span> <span m='507210'>the</span> <span
  m='507300'>cylinder.</span> <span m='507810'>And</span> <span
  m='507960'>that's</span> <span m='508320'>the</span> <span
  m='508440'>picture</span> <span m='509130'>of</span> <span
  m='509280'>circular</span> <span m='509730'>convolution.</span> </p><p><span
  m='512630'>Now</span> <span m='512980'>there</span> <span
  m='513400'>are</span> <span m='513669'>other</span> <span
  m='513909'>ways</span> <span m='514480'>of</span> <span
  m='515080'>looking</span> <span m='515679'>at</span> <span
  m='515830'>circular</span> <span m='516280'>convolution.</span> <span
  m='517780'>And</span> <span m='518440'>one</span> <span m='518679'>of</span>
  <span m='518740'>them</span> <span m='519100'>can</span> <span
  m='519280'>be</span> <span m='519429'>suggested</span> <span
  m='521140'>by</span> <span m='522340'>referring</span> <span
  m='522850'>back</span> <span m='523600'>to</span> <span m='524140'>this</span>
  <span m='524410'>view</span> <span m='524620'>graph.</span> <span
  m='526310'>We</span> <span m='526910'>saw</span> <span m='527240'>that</span>
  <span m='527390'>we</span> <span m='527570'>could</span> <span
  m='527720'>express</span> <span m='528530'>the</span> <span
  m='528890'>circular</span> <span m='529430'>convolution</span> <span
  m='531440'>in</span> <span m='531590'>this</span> <span
  m='531830'>form,</span> <span m='533420'>or</span> <span
  m='534020'>equivalently,</span> <span m='535640'>what</span> <span
  m='535880'>this</span> <span m='536150'>means,</span> <span
  m='536900'>what</span> <span m='537050'>this</span> <span
  m='537230'>equation</span> <span m='537830'>means,</span> <span
  m='540110'>or</span> <span m='540260'>can</span> <span m='540440'>be</span>
  <span m='540500'>interpreted</span> <span m='541070'>as,</span> <span
  m='541970'>is</span> <span m='542150'>as</span> <span m='542710'>the</span>
  <span m='542820'>linear</span> <span m='543290'>convolution</span> <span
  m='545240'>of</span> <span m='545390'>x1</span> <span m='545705'>of</span>
  <span m='546020'>n</span> <span m='547310'>and</span> <span
  m='547620'>x2</span> <span m='548700'>tilde</span> <span m='549160'>of</span>
  <span m='549370'>n,</span> <span m='549760'>or</span> <span
  m='549950'>equivalently,</span> <span m='550730'>x2</span> <span
  m='551060'>to</span> <span m='551510'>of</span> <span m='551690'>n</span>
  <span m='552410'>modulo</span> <span m='552920'>capital</span> <span
  m='553460'>N,</span> <span m='554600'>and</span> <span m='554750'>then</span>
  <span m='555320'>one</span> <span m='555590'>period</span> <span
  m='556250'>extracted</span> <span m='556910'>from</span> <span
  m='557150'>that.</span> <span m='558740'>So</span> <span m='559220'>in</span>
  <span m='559340'>fact,</span> <span m='559770'>another</span> <span
  m='559970'>way</span> <span m='560150'>of</span> <span
  m='560270'>looking</span> <span m='560600'>at</span> <span
  m='560690'>circular</span> <span m='561140'>convolution</span> <span
  m='562460'>would</span> <span m='562610'>be</span> <span m='563120'>to</span>
  <span m='563270'>form</span> <span m='563570'>the</span> <span
  m='563660'>linear</span> <span m='564050'>convolution</span> <span
  m='564950'>of</span> <span m='565100'>x1</span> <span m='565590'>of n</span>
  <span m='566810'>with</span> <span m='567410'>the</span> <span
  m='567650'>periodic</span> <span m='569210'>counterpart</span> <span
  m='570050'>of</span> <span m='570230'>x2</span> <span m='570720'>of n,</span>
  <span m='571580'>carry</span> <span m='571940'>out</span> <span
  m='572210'>that</span> <span m='572390'>linear</span> <span
  m='572810'>convolution</span> <span m='574130'>and</span> <span
  m='574310'>then</span> <span m='575480'>extract</span> <span
  m='576020'>one</span> <span m='576230'>period,</span> <span
  m='576840'>which</span> <span m='576950'>is</span> <span
  m='577070'>what</span> <span m='577220'>this</span> <span
  m='577430'>function</span> <span m='577880'>r sub</span> <span
  m='578260'>capital</span> <span m='578720'>N</span> <span m='578840'>of
  n</span> <span m='579110'>is</span> <span m='579260'>doing.</span>
  </p><p><span m='581520'>How</span> <span m='581600'>can</span> <span
  m='581780'>we</span> <span m='581900'>get</span> <span m='582380'>the</span>
  <span m='582710'>periodic</span> <span m='583460'>sequence</span> <span
  m='584300'>from</span> <span m='584690'>x2</span> <span m='584960'>of</span>
  <span m='585200'>n?</span> <span m='585710'>Well,</span> <span
  m='585890'>we</span> <span m='586010'>could</span> <span m='586160'>do</span>
  <span m='586370'>that,</span> <span m='586910'>for</span> <span
  m='587090'>example,</span> <span m='588230'>by</span> <span
  m='588610'>convolving</span> <span m='589490'>x2</span> <span
  m='590060'>of</span> <span m='590210'>n</span> <span m='591620'>with</span>
  <span m='592070'>a</span> <span m='592130'>pulse</span> <span
  m='592550'>train</span> <span m='593510'>where</span> <span
  m='593960'>the</span> <span m='594080'>spacing</span> <span
  m='594830'>of</span> <span m='594980'>the</span> <span
  m='595070'>pulses</span> <span m='595790'>is</span> <span
  m='595910'>capital</span> <span m='596420'>N.</span> <span
  m='597260'>And</span> <span m='597950'>that's</span> <span
  m='598220'>illustrated</span> <span m='599150'>on</span> <span
  m='600290'>the</span> <span m='600380'>next</span> <span
  m='600770'>view</span> <span m='601220'>graph.</span> <span
  m='604140'>So</span> <span m='604410'>that</span> <span m='604890'>from</span>
  <span m='605130'>the</span> <span m='605250'>equation</span> <span
  m='606210'>that</span> <span m='606420'>we</span> <span m='606540'>just</span>
  <span m='606840'>saw,</span> <span m='608190'>one</span> <span
  m='608880'>possible</span> <span m='610560'>way</span> <span
  m='611160'>of</span> <span m='611490'>thinking</span> <span
  m='612090'>of</span> <span m='612210'>circular</span> <span
  m='612690'>convolution</span> <span m='614310'>is</span> <span
  m='614820'>as</span> <span m='616980'>the</span> <span
  m='617250'>generation</span> <span m='618420'>of</span> <span
  m='619140'>the</span> <span m='619230'>periodic</span> <span
  m='619920'>function</span> <span m='620400'>x2</span> <span
  m='620700'>of</span> <span m='621010'>n.</span> <span m='622410'>By</span>
  <span m='622710'>convolving</span> <span m='623280'>x2</span> <span
  m='623490'>of</span> <span m='623730'>n</span> <span m='624570'>with</span>
  <span m='624720'>a</span> <span m='624780'>pulse</span> <span
  m='625170'>train,</span> <span m='626370'>then</span> <span
  m='626730'>a</span> <span m='626820'>linear</span> <span
  m='627180'>convolution</span> <span m='628080'>of</span> <span
  m='628290'>that</span> <span m='628800'>with</span> <span m='628980'>x1</span>
  <span m='629265'>of</span> <span m='629550'>n,</span> <span
  m='630490'>and</span> <span m='630540'>then</span> <span
  m='630720'>finally,</span> <span m='631650'>extracting</span> <span
  m='632340'>one</span> <span m='632550'>period,</span> <span
  m='633220'>which</span> <span m='633330'>is</span> <span
  m='633480'>what</span> <span m='633960'>this</span> <span
  m='634170'>function,</span> <span m='634860'>multiplying</span> <span
  m='635550'>x3</span> <span m='636000'>tilde</span> <span m='636300'>of</span>
  <span m='636620'>n</span> <span m='636870'>does.</span> </p><p><span
  m='637990'>So</span> <span m='638700'>we</span> <span m='638850'>could</span>
  <span m='638970'>generate</span> <span m='639630'>a</span> <span
  m='639720'>pulse</span> <span m='640080'>train</span> <span
  m='641130'>by</span> <span m='642720'>taking</span> <span m='643110'>a</span>
  <span m='643170'>system</span> <span m='644670'>whose</span> <span
  m='644880'>unit</span> <span m='645180'>sample</span> <span
  m='645630'>response</span> <span m='646860'>is</span> <span
  m='647040'>1</span> <span m='648060'>at</span> <span m='648180'>a</span> <span
  m='648240'>spacing</span> <span m='648780'>of</span> <span
  m='648900'>capital</span> <span m='649410'>N,</span> <span
  m='650580'>and</span> <span m='650700'>it's</span> <span m='650820'>0</span>
  <span m='651330'>otherwise.</span> <span m='653610'>Kicking</span> <span
  m='654000'>that</span> <span m='654210'>system</span> <span
  m='654990'>with</span> <span m='655140'>the</span> <span
  m='655200'>unit</span> <span m='655500'>sample,</span> <span
  m='656460'>in</span> <span m='656520'>which</span> <span
  m='656760'>case,</span> <span m='657190'>we</span> <span m='657210'>get</span>
  <span m='657390'>this</span> <span m='657570'>pulse</span> <span
  m='657960'>train</span> <span m='658680'>out.</span> <span
  m='660900'>Using</span> <span m='661320'>that</span> <span
  m='661680'>as</span> <span m='661830'>the</span> <span
  m='661980'>excitation</span> <span m='663120'>to</span> <span
  m='664100'>a</span> <span m='664180'>system</span> <span
  m='664680'>whose</span> <span m='664890'>unit</span> <span
  m='665160'>sample</span> <span m='665580'>response</span> <span
  m='666270'>is</span> <span m='666420'>x2</span> <span m='666950'>of</span>
  <span m='667060'>n,</span> <span m='668160'>and</span> <span
  m='668280'>what</span> <span m='668430'>we'll</span> <span
  m='668640'>get</span> <span m='668940'>then</span> <span m='669450'>is</span>
  <span m='670110'>x2</span> <span m='670710'>of</span> <span
  m='670830'>n</span> <span m='671760'>convolved</span> <span
  m='672330'>with</span> <span m='672480'>this</span> <span
  m='672660'>pulse</span> <span m='673020'>train,</span> <span
  m='674040'>or</span> <span m='674520'>x2</span> <span m='675060'>of</span>
  <span m='675180'>n</span> <span m='675660'>repeated</span> <span
  m='676970'>at</span> <span m='677220'>intervals</span> <span
  m='677910'>of</span> <span m='678060'>capital</span> <span
  m='678600'>N,</span> <span m='679710'>but</span> <span
  m='679920'>that's</span> <span m='680160'>x2</span> <span
  m='680400'>tilde</span> <span m='680590'>of</span> <span m='681000'>n,</span>
  <span m='681330'>that's</span> <span m='681510'>the</span> <span
  m='681630'>periodic</span> <span m='682620'>sequence</span> <span
  m='683520'>that</span> <span m='683670'>we</span> <span
  m='683850'>want.</span> <span m='684210'>That's</span> <span
  m='684390'>the</span> <span m='684480'>periodic</span> <span
  m='684990'>counterpart</span> <span m='685770'>of</span> <span
  m='685920'>x2</span> <span m='686370'>of</span> <span m='686580'>n.</span>
  <span m='687480'>And</span> <span m='687690'>so</span> <span
  m='688590'>that</span> <span m='688890'>is</span> <span m='689190'>what</span>
  <span m='689340'>we</span> <span m='689520'>have</span> <span
  m='689820'>here.</span> </p><p><span m='691650'>Using</span> <span
  m='692070'>that</span> <span m='692400'>as</span> <span m='692580'>the</span>
  <span m='692730'>input</span> <span m='693300'>to</span> <span
  m='693480'>a</span> <span m='693540'>system</span> <span
  m='694080'>whose</span> <span m='694290'>unit</span> <span
  m='694560'>sample</span> <span m='694950'>response</span> <span
  m='695580'>is</span> <span m='695790'>x1</span> <span m='696030'>of</span>
  <span m='696270'>n,</span> <span m='697590'>and</span> <span
  m='697740'>then</span> <span m='698220'>the</span> <span
  m='698430'>output</span> <span m='699150'>is</span> <span
  m='700020'>the</span> <span m='700230'>periodic</span> <span
  m='700890'>convolution</span> <span m='702300'>of</span> <span
  m='702450'>x1</span> <span m='702900'>of n</span> <span m='703410'>with</span>
  <span m='703560'>x2</span> <span m='703800'>of</span> <span
  m='704070'>n.</span> <span m='704850'>We</span> <span
  m='704970'>extract</span> <span m='705510'>one</span> <span
  m='705720'>period</span> <span m='706680'>and</span> <span
  m='706770'>we</span> <span m='706920'>get</span> <span
  m='707100'>finally,</span> <span m='707550'>the</span> <span
  m='707670'>circular</span> <span m='708150'>convolution</span> <span
  m='709410'>of</span> <span m='709560'>the</span> <span
  m='709650'>finite</span> <span m='710070'>length</span> <span
  m='710280'>sequences</span> <span m='711030'>x1</span> <span m='711530'>of
  n</span> <span m='712090'>an</span> <span m='712490'>x2</span> <span
  m='712950'>of</span> <span m='713060'>n.</span> </p><p><span
  m='714900'>Well,</span> <span m='715610'>the</span> <span
  m='715700'>fact</span> <span m='716000'>that</span> <span m='716090'>we</span>
  <span m='716210'>could</span> <span m='716420'>view</span> <span
  m='717140'>the</span> <span m='717410'>circular</span> <span
  m='717890'>convolution</span> <span m='718880'>in</span> <span
  m='719030'>terms</span> <span m='719300'>of</span> <span m='719390'>a</span>
  <span m='719450'>cascade</span> <span m='720200'>of</span> <span
  m='720320'>systems</span> <span m='721010'>of</span> <span
  m='721130'>this</span> <span m='721340'>type</span> <span
  m='722390'>leads</span> <span m='722810'>to</span> <span m='723440'>a</span>
  <span m='723740'>very</span> <span m='724100'>important</span> <span
  m='724820'>and</span> <span m='724970'>interesting</span> <span
  m='725780'>interpretation</span> <span m='726950'>of</span> <span
  m='727040'>circular</span> <span m='727490'>convolution.</span> <span
  m='730060'>In</span> <span m='730180'>particular,</span> <span
  m='731870'>let's</span> <span m='735270'>look</span> <span
  m='735600'>at</span> <span m='737780'>these</span> <span
  m='738530'>systems,</span> <span m='740660'>cascaded</span> <span
  m='741950'>as</span> <span m='742160'>they</span> <span m='742310'>are</span>
  <span m='742520'>here.</span> <span m='743720'>So</span> <span
  m='744380'>we</span> <span m='744590'>have</span> <span
  m='744890'>then,</span> <span m='745520'>the</span> <span
  m='745640'>cascade</span> <span m='746390'>of</span> <span
  m='746600'>these</span> <span m='746870'>three</span> <span
  m='747170'>systems</span> <span m='748910'>to</span> <span
  m='749030'>generate</span> <span m='750140'>the</span> <span
  m='750230'>circular</span> <span m='750710'>convolution,</span> <span
  m='751760'>which</span> <span m='751970'>is</span> <span m='752090'>x3</span>
  <span m='752570'>of n,</span> <span m='752960'>the</span> <span
  m='753080'>circular</span> <span m='753500'>convolution</span> <span
  m='754820'>of</span> <span m='754940'>x1</span> <span m='755235'>of</span>
  <span m='755530'>n</span> <span m='756050'>and</span> <span
  m='756200'>x2</span> <span m='756650'>of n.</span> <span m='757820'>So</span>
  <span m='758330'>this</span> <span m='758570'>then</span> <span
  m='759110'>is</span> <span m='759650'>three</span> <span
  m='760280'>systems</span> <span m='761120'>linear</span> <span
  m='761480'>shift</span> <span m='761780'>invariant</span> <span
  m='762260'>systems</span> <span m='762740'>and</span> <span
  m='762830'>cascade.</span> </p><p><span m='764900'>And</span> <span
  m='765020'>one</span> <span m='765200'>of</span> <span m='765290'>the</span>
  <span m='765410'>important</span> <span m='765890'>things</span> <span
  m='766640'>that</span> <span m='766790'>we</span> <span m='766940'>know</span>
  <span m='767450'>about</span> <span m='768410'>linear</span> <span
  m='769160'>shift</span> <span m='769550'>invariant</span> <span
  m='770090'>systems</span> <span m='771290'>which</span> <span
  m='771470'>are</span> <span m='771560'>cascaded</span> <span
  m='773090'>is</span> <span m='773330'>that</span> <span m='774020'>the</span>
  <span m='774200'>order</span> <span m='774920'>in</span> <span
  m='775070'>which</span> <span m='775310'>they're</span> <span
  m='775490'>cascaded</span> <span m='776630'>is</span> <span
  m='776810'>irrelevant.</span> <span m='777800'>That's</span> <span
  m='777980'>something</span> <span m='778310'>we</span> <span
  m='778430'>showed</span> <span m='778850'>in</span> <span
  m='779000'>one</span> <span m='779150'>of</span> <span m='779240'>the</span>
  <span m='779360'>early</span> <span m='779630'>lectures.</span> <span
  m='780590'>So</span> <span m='780770'>in</span> <span m='780890'>fact,</span>
  <span m='781320'>we</span> <span m='781340'>can</span> <span
  m='781520'>interchange</span> <span m='782570'>the</span> <span
  m='782690'>order</span> <span m='782990'>of</span> <span
  m='783080'>these</span> <span m='783260'>systems</span> <span
  m='784370'>any</span> <span m='784580'>way</span> <span m='785270'>that</span>
  <span m='785390'>we</span> <span m='785540'>want</span> <span
  m='785840'>to.</span> <span m='787430'>And</span> <span m='787550'>in</span>
  <span m='787640'>particular,</span> <span m='788430'>let's</span> <span
  m='788990'>interchange</span> <span m='789740'>the</span> <span
  m='789890'>order</span> <span m='790130'>of</span> <span
  m='790220'>these</span> <span m='790370'>systems</span> <span
  m='791480'>by</span> <span m='791630'>taking</span> <span
  m='792140'>this</span> <span m='792380'>system</span> <span
  m='793160'>which</span> <span m='793370'>generates</span> <span
  m='794120'>the</span> <span m='794240'>pulse</span> <span
  m='794600'>train,</span> <span m='795800'>putting</span> <span
  m='796070'>that</span> <span m='796370'>at</span> <span m='796490'>the</span>
  <span m='796670'>end</span> <span m='796880'>of</span> <span
  m='796970'>this</span> <span m='797180'>cascade</span> <span
  m='797780'>chain</span> <span m='799460'>so</span> <span
  m='799700'>that</span> <span m='800300'>instead</span> <span
  m='800660'>of</span> <span m='800780'>this</span> <span
  m='801530'>cascade</span> <span m='802190'>then,</span> <span
  m='802880'>we</span> <span m='803030'>have</span> <span m='803240'>x2</span>
  <span m='803810'>of</span> <span m='803950'>n</span> <span
  m='804950'>cascaded</span> <span m='805610'>with</span> <span
  m='805850'>x1</span> <span m='806330'>of n,</span> <span
  m='807170'>cascaded</span> <span m='807890'>with</span> <span
  m='808140'>p</span> <span m='808610'>sub</span> <span
  m='808970'>capital</span> <span m='809240'>N</span> <span m='809510'>of</span>
  <span m='809900'>n.</span> <span m='810590'>And</span> <span
  m='810710'>then</span> <span m='810860'>of</span> <span
  m='810950'>course,</span> <span m='811670'>r</span> <span m='811900'>sub
  n</span> <span m='812510'>to</span> <span m='812690'>extract</span> <span
  m='813120'>the</span> <span m='813230'>single</span> <span
  m='813530'>period.</span> </p><p><span m='815430'>Well,</span> <span
  m='815660'>what</span> <span m='815840'>does</span> <span
  m='815960'>this</span> <span m='816200'>mean?</span> <span
  m='817980'>This</span> <span m='818150'>means</span> <span
  m='818900'>that</span> <span m='819320'>I</span> <span m='819560'>can</span>
  <span m='819920'>equivalently</span> <span m='821390'>form</span> <span
  m='821930'>the</span> <span m='822020'>circular</span> <span
  m='822470'>convolution</span> <span m='823880'>of</span> <span
  m='824030'>x1</span> <span m='824290'>of</span> <span m='824550'>n</span>
  <span m='824880'>and</span> <span m='825080'>x2</span> <span
  m='825335'>of</span> <span m='825590'>n</span> <span m='826910'>by</span>
  <span m='827150'>first</span> <span m='827990'>forming</span> <span
  m='828380'>the</span> <span m='828500'>linear</span> <span
  m='828860'>convolution</span> <span m='829820'>of</span> <span
  m='829970'>x1</span> <span m='830420'>and</span> <span m='830510'>x2.</span>
  <span m='831650'>That's</span> <span m='831890'>of</span> <span
  m='832010'>course,</span> <span m='832400'>what</span> <span
  m='832580'>the</span> <span m='832700'>impulse</span> <span
  m='833090'>response</span> <span m='833570'>of</span> <span
  m='833660'>these</span> <span m='833870'>two</span> <span
  m='834050'>systems</span> <span m='834740'>and</span> <span
  m='834860'>cascade</span> <span m='835520'>is.</span> <span
  m='837470'>And</span> <span m='837590'>then</span> <span
  m='837920'>using</span> <span m='838400'>that</span> <span
  m='838790'>as</span> <span m='838970'>the</span> <span
  m='839120'>excitation</span> <span m='840170'>to</span> <span
  m='840560'>a</span> <span m='840620'>system</span> <span
  m='841670'>whose</span> <span m='841970'>unit</span> <span
  m='842270'>sample</span> <span m='842690'>response</span> <span
  m='843620'>is</span> <span m='844040'>a</span> <span m='844100'>pulse</span>
  <span m='844490'>train.</span> <span m='845480'>So</span> <span
  m='846410'>I</span> <span m='846530'>can</span> <span m='846740'>think</span>
  <span m='846980'>of</span> <span m='847100'>this</span> <span
  m='847340'>then</span> <span m='847730'>as</span> <span m='848000'>the</span>
  <span m='848120'>linear</span> <span m='848540'>convolution.</span> <span
  m='850740'>That</span> <span m='851310'>convolved</span> <span
  m='852360'>with</span> <span m='853050'>a</span> <span m='854250'>pulse</span>
  <span m='854610'>train,</span> <span m='856350'>one</span> <span
  m='856590'>period</span> <span m='856980'>extracted,</span> <span
  m='857920'>and</span> <span m='857970'>the</span> <span
  m='858060'>result</span> <span m='858630'>is</span> <span m='858990'>a</span>
  <span m='859050'>circular</span> <span m='859530'>convolution.</span> <span
  m='861450'>That's</span> <span m='861680'>a</span> <span
  m='861780'>very</span> <span m='862080'>useful</span> <span
  m='862800'>and</span> <span m='862920'>important</span> <span
  m='863400'>interpretation</span> <span m='864420'>of</span> <span
  m='864540'>circular</span> <span m='864990'>convolution.</span> <span
  m='866460'>And</span> <span m='867180'>the</span> <span m='867330'>way</span>
  <span m='867570'>to</span> <span m='867690'>sort</span> <span
  m='867960'>of</span> <span m='868020'>say</span> <span m='868290'>it</span>
  <span m='868410'>in</span> <span m='868530'>words,</span> <span
  m='868860'>this</span> <span m='869040'>isn't</span> <span
  m='869280'>exactly</span> <span m='870060'>correct,</span> <span
  m='871080'>but</span> <span m='871860'>more</span> <span m='872160'>or</span>
  <span m='872190'>less</span> <span m='872490'>the</span> <span
  m='872610'>way</span> <span m='872760'>to</span> <span m='872880'>say</span>
  <span m='873120'>it</span> <span m='873240'>in</span> <span
  m='873360'>words</span> <span m='874380'>is</span> <span
  m='874530'>that</span> <span m='874680'>the</span> <span
  m='874800'>circular</span> <span m='875310'>convolution</span> <span
  m='876930'>can</span> <span m='877140'>be</span> <span
  m='877290'>formed</span> <span m='878310'>from</span> <span
  m='878610'>a</span> <span m='878670'>linear</span> <span
  m='879060'>convolution</span> <span m='880410'>plus</span> <span
  m='880890'>aliasing.</span> </p><p><span m='882900'>You</span> <span
  m='882960'>see</span> <span m='883470'>this</span> <span
  m='883800'>linear</span> <span m='884160'>convolution</span> <span
  m='885630'>in</span> <span m='885750'>general,</span> <span
  m='886320'>is</span> <span m='886470'>going</span> <span m='886710'>to</span>
  <span m='886830'>be</span> <span m='886920'>longer</span> <span
  m='887430'>than</span> <span m='887580'>capital</span> <span
  m='888120'>N.</span> <span m='889320'>The</span> <span
  m='889470'>output</span> <span m='889830'>of</span> <span
  m='889950'>this</span> <span m='890160'>system</span> <span
  m='890820'>is</span> <span m='891000'>this</span> <span
  m='891180'>linear</span> <span m='891540'>convolution</span> <span
  m='892800'>repeated</span> <span m='893370'>over</span> <span
  m='893700'>and</span> <span m='893790'>over</span> <span
  m='894060'>again,</span> <span m='894390'>added</span> <span
  m='894780'>up</span> <span m='895110'>over</span> <span m='895440'>and</span>
  <span m='895530'>over</span> <span m='895830'>again</span> <span
  m='896610'>with</span> <span m='896750'>a</span> <span
  m='896820'>spacing</span> <span m='897075'>of</span> <span
  m='897330'>capital</span> <span m='897420'>N.</span> <span
  m='898270'>So</span> <span m='898320'>there</span> <span m='898650'>is</span>
  <span m='898980'>an</span> <span m='899100'>interference,</span> <span
  m='899940'>if</span> <span m='900060'>you</span> <span m='900150'>want</span>
  <span m='900300'>to</span> <span m='900360'>call</span> <span
  m='900660'>it</span> <span m='900750'>that,</span> <span
  m='901560'>between</span> <span m='902250'>the</span> <span
  m='902430'>successive</span> <span m='903030'>replicas</span> <span
  m='904200'>of</span> <span m='904350'>this</span> <span
  m='904530'>linear</span> <span m='904860'>convolution</span> <span
  m='905700'>as</span> <span m='905820'>they</span> <span m='905940'>come</span>
  <span m='906180'>out</span> <span m='906330'>of</span> <span
  m='906420'>this</span> <span m='906570'>system.</span> <span
  m='907890'>That's</span> <span m='908130'>the</span> <span
  m='908310'>aliasing,</span> <span m='909240'>that's</span> <span
  m='909480'>why</span> <span m='909720'>aliasing</span> <span
  m='910320'>is</span> <span m='910410'>stuck</span> <span
  m='910740'>into</span> <span m='911010'>that</span> <span
  m='911880'>phrase.</span> <span m='913140'>But</span> <span
  m='914220'>the</span> <span m='914650'>way</span> <span m='915170'>to</span>
  <span m='915690'>summarize</span> <span m='916430'>it</span> <span
  m='916500'>or</span> <span m='916620'>think</span> <span
  m='916890'>about</span> <span m='917250'>it</span> <span m='917760'>is</span>
  <span m='918120'>as</span> <span m='918450'>circular</span> <span
  m='918960'>convolution</span> <span m='920310'>corresponding</span> <span
  m='921240'>to</span> <span m='921960'>linear</span> <span
  m='922320'>convolution</span> <span m='923520'>plus</span> <span
  m='923790'>aliasing.</span> </p><p><span m='925980'>So</span> <span
  m='926250'>here</span> <span m='926460'>it</span> <span m='926550'>is</span>
  <span m='927030'>said</span> <span m='927330'>again,</span> <span
  m='928260'>circular</span> <span m='928710'>convolution</span> <span
  m='930150'>equals</span> <span m='930870'>linear</span> <span
  m='931230'>convolution</span> <span m='932130'>plus</span> <span
  m='932460'>aliasing.</span> <span m='933900'>What</span> <span
  m='934050'>I</span> <span m='934170'>mean</span> <span m='934530'>by</span>
  <span m='934740'>that</span> <span m='935580'>is</span> <span
  m='935820'>that</span> <span m='937350'>if</span> <span m='937710'>I</span>
  <span m='937920'>have</span> <span m='938370'>the</span> <span
  m='938460'>linear</span> <span m='938790'>convolution</span> <span
  m='939780'>of</span> <span m='939930'>x1</span> <span m='940205'>of</span>
  <span m='940480'>n</span> <span m='941140'>and</span> <span
  m='941310'>x2</span> <span m='941790'>of</span> <span m='942080'>n,</span>
  <span m='943440'>which</span> <span m='943680'>I'm</span> <span
  m='943860'>denoting</span> <span m='944340'>by</span> <span
  m='944580'>x3</span> <span m='945390'>hat</span> <span m='945630'>of</span>
  <span m='945750'>n,</span> <span m='947040'>and</span> <span
  m='947160'>I</span> <span m='947280'>want</span> <span m='947940'>the</span>
  <span m='948060'>circular</span> <span m='948570'>convolution,</span> <span
  m='949410'>the</span> <span m='949590'>N point</span> <span
  m='950490'>circular</span> <span m='951000'>convolution</span> <span
  m='952470'>of</span> <span m='952950'>x1</span> <span m='953440'>of n</span>
  <span m='954230'>with</span> <span m='954510'>x2</span> <span
  m='954720'>of</span> <span m='955010'>n,</span> <span m='956820'>I</span>
  <span m='956910'>can</span> <span m='957120'>get</span> <span
  m='957330'>the</span> <span m='957450'>circular</span> <span
  m='957930'>convolution</span> <span m='959190'>from</span> <span
  m='959400'>the</span> <span m='959490'>linear</span> <span
  m='959880'>convolution</span> <span m='961380'>by</span> <span
  m='962250'>taking</span> <span m='962610'>the</span> <span
  m='962730'>linear</span> <span m='963060'>convolution</span> <span
  m='964110'>and</span> <span m='964920'>convolving</span> <span
  m='965520'>it</span> <span m='965640'>with</span> <span m='965790'>a</span>
  <span m='965850'>pulse</span> <span m='966180'>train</span> <span
  m='966840'>with</span> <span m='966990'>a</span> <span
  m='967050'>spacing</span> <span m='967560'>of</span> <span
  m='967680'>capital</span> <span m='968190'>N,</span> <span
  m='969060'>or</span> <span m='969270'>equivalently</span> <span
  m='970710'>adding</span> <span m='971100'>it</span> <span m='971160'>to</span>
  <span m='971340'>itself,</span> <span m='972600'>delayed</span> <span
  m='973080'>by</span> <span m='973320'>capital</span> <span
  m='973860'>N,</span> <span m='974130'>2</span> <span m='974310'>capital</span>
  <span m='974820'>N</span> <span m='975000'>minus</span> <span
  m='975420'>capital</span> <span m='975900'>N,</span> <span
  m='976050'>minus</span> <span m='976380'>2</span> <span
  m='976530'>capital</span> <span m='976790'>N,</span> <span
  m='977050'>et</span> <span m='977450'>cetera,</span> <span
  m='978540'>and</span> <span m='978660'>then</span> <span
  m='979050'>extracting</span> <span m='979980'>a</span> <span
  m='980040'>single</span> <span m='980400'>period.</span> </p><p><span
  m='981780'>And</span> <span m='981930'>often</span> <span
  m='983010'>when</span> <span m='983385'>you</span> <span
  m='983760'>carry</span> <span m='984150'>out</span> <span m='984540'>a</span>
  <span m='984930'>circular</span> <span m='985350'>convolution</span> <span
  m='986040'>of</span> <span m='986130'>two</span> <span
  m='986310'>sequences</span> <span m='987660'>or</span> <span
  m='987810'>want</span> <span m='988020'>to</span> <span
  m='988140'>examine</span> <span m='988620'>properties</span> <span
  m='989310'>of</span> <span m='989400'>circular</span> <span
  m='989820'>convolution,</span> <span m='991200'>the</span> <span
  m='991290'>notion</span> <span m='992850'>or</span> <span
  m='993060'>interpretation</span> <span m='994530'>of</span> <span
  m='994650'>circular</span> <span m='995100'>convolution</span> <span
  m='996420'>as</span> <span m='996990'>linear</span> <span
  m='997350'>convolution</span> <span m='998130'>plus</span> <span
  m='998910'>aliasing</span> <span m='1000170'>is</span> <span
  m='1000620'>an</span> <span m='1000740'>extremely</span> <span
  m='1001400'>useful</span> <span m='1002540'>sort</span> <span
  m='1002810'>of</span> <span m='1002900'>picture</span> <span
  m='1003650'>to</span> <span m='1003770'>have.</span> <span
  m='1005540'>So</span> <span m='1005870'>it's</span> <span
  m='1005990'>the</span> <span m='1006080'>kind</span> <span
  m='1006290'>of</span> <span m='1006380'>phrase</span> <span
  m='1006770'>that</span> <span m='1007670'>you</span> <span
  m='1007850'>should</span> <span m='1008210'>repeat</span> <span
  m='1008540'>to</span> <span m='1008660'>yourself</span> <span
  m='1009590'>two</span> <span m='1009770'>or</span> <span
  m='1009830'>three</span> <span m='1010070'>times</span> <span
  m='1010340'>for</span> <span m='1010610'>a</span> <span
  m='1010640'>week</span> <span m='1010880'>before</span> <span
  m='1011210'>you</span> <span m='1011330'>go</span> <span m='1011420'>to</span>
  <span m='1011540'>bed.</span> <span m='1012410'>And</span> <span
  m='1013890'>in</span> <span m='1014030'>a</span> <span
  m='1014090'>short</span> <span m='1014360'>time,</span> <span
  m='1014660'>you'll</span> <span m='1014840'>understand</span> <span
  m='1015560'>the</span> <span m='1015680'>relationship</span> <span
  m='1016340'>between</span> <span m='1016730'>circular</span> <span
  m='1017120'>convolution</span> <span m='1017750'>and</span> <span
  m='1017840'>linear</span> <span m='1018170'>convolution</span> <span
  m='1018800'>very</span> <span m='1019040'>well.</span> </p><p><span
  m='1020120'>Well,</span> <span m='1020270'>let's</span> <span
  m='1020810'>look</span> <span m='1021080'>at</span> <span m='1021650'>a</span>
  <span m='1021710'>couple</span> <span m='1022070'>of</span> <span
  m='1022160'>examples</span> <span m='1023000'>of</span> <span
  m='1023180'>this.</span> <span m='1025780'>Here</span> <span
  m='1026440'>is</span> <span m='1027490'>a</span> <span
  m='1027670'>sequence,</span> <span m='1028930'>x1</span> <span
  m='1029410'>of</span> <span m='1029500'>n,</span> <span
  m='1029770'>it's</span> <span m='1029920'>a</span> <span
  m='1029980'>six-point</span> <span m='1030609'>sequence.</span> <span
  m='1032280'>And</span> <span m='1033190'>let's</span> <span
  m='1034060'>carry</span> <span m='1034510'>out</span> <span
  m='1034780'>the</span> <span m='1034900'>circular</span> <span
  m='1035349'>convolution</span> <span m='1036430'>of</span> <span
  m='1037450'>this</span> <span m='1037660'>sequence</span> <span
  m='1038290'>with</span> <span m='1038470'>itself,</span> <span
  m='1039310'>that</span> <span m='1039700'>makes</span> <span
  m='1040000'>it</span> <span m='1040089'>a</span> <span
  m='1040240'>relatively</span> <span m='1040930'>straightforward</span> <span
  m='1041650'>example.</span> <span m='1043480'>And</span> <span
  m='1043569'>let's</span> <span m='1043869'>do</span> <span
  m='1044140'>that</span> <span m='1044680'>by</span> <span
  m='1045280'>using</span> <span m='1045760'>the</span> <span
  m='1045849'>notion</span> <span m='1046900'>that</span> <span
  m='1047079'>circular</span> <span m='1047560'>convolution</span> <span
  m='1048339'>is</span> <span m='1048520'>linear</span> <span
  m='1048850'>convolution</span> <span m='1049570'>plus</span> <span
  m='1049810'>aliasing.</span> </p><p><span m='1051790'>So</span> <span
  m='1052810'>we</span> <span m='1052930'>want</span> <span
  m='1053170'>first</span> <span m='1053530'>of</span> <span
  m='1053650'>all,</span> <span m='1054160'>to</span> <span
  m='1054310'>form</span> <span m='1055060'>the</span> <span
  m='1055300'>linear</span> <span m='1055720'>convolution</span> <span
  m='1056650'>of</span> <span m='1057430'>x1</span> <span m='1057730'>of</span>
  <span m='1058030'>n</span> <span m='1058285'>and</span> <span
  m='1058540'>x2</span> <span m='1059050'>of</span> <span m='1059170'>n.</span>
  <span m='1060280'>And</span> <span m='1060850'>as</span> <span
  m='1061360'>you</span> <span m='1061480'>should</span> <span
  m='1061720'>recall</span> <span m='1062170'>from</span> <span
  m='1062350'>similar</span> <span m='1062800'>examples</span> <span
  m='1063640'>in</span> <span m='1063880'>the</span> <span
  m='1064000'>earlier</span> <span m='1064360'>lectures,</span> <span
  m='1065410'>and</span> <span m='1065500'>examples</span> <span
  m='1066010'>that</span> <span m='1066160'>you've</span> <span
  m='1066280'>worked</span> <span m='1066550'>in</span> <span
  m='1066640'>the</span> <span m='1066730'>study</span> <span
  m='1067090'>guide,</span> <span m='1068270'>the</span> <span
  m='1068370'>linear</span> <span m='1068650'>convolution</span> <span
  m='1069670'>of</span> <span m='1069850'>this</span> <span
  m='1070030'>sequence</span> <span m='1070570'>with</span> <span
  m='1070720'>itself</span> <span m='1071770'>is</span> <span
  m='1072370'>a</span> <span m='1072670'>triangular</span> <span
  m='1073780'>sequence.</span> <span m='1075160'>We</span> <span
  m='1075280'>of</span> <span m='1075370'>course,</span> <span
  m='1075730'>take</span> <span m='1075970'>this</span> <span
  m='1076150'>sequence,</span> <span m='1076720'>flip</span> <span
  m='1076990'>it</span> <span m='1077080'>over,</span> <span
  m='1077860'>and</span> <span m='1077950'>slide</span> <span
  m='1078340'>it</span> <span m='1078460'>past</span> <span
  m='1078880'>itself.</span> <span m='1079870'>And</span> <span
  m='1080290'>as</span> <span m='1080440'>we</span> <span
  m='1080530'>slide</span> <span m='1080920'>along,</span> <span
  m='1081280'>we</span> <span m='1081370'>accumulate</span> <span
  m='1082000'>more</span> <span m='1082240'>and</span> <span
  m='1082330'>more</span> <span m='1082540'>points.</span> <span
  m='1084460'>And</span> <span m='1085000'>so,</span> <span
  m='1086320'>the</span> <span m='1086650'>linear</span> <span
  m='1087070'>convolution</span> <span m='1088180'>of</span> <span
  m='1088580'>x1</span> <span m='1088855'>of</span> <span m='1089130'>n</span>
  <span m='1089290'>with</span> <span m='1089410'>x2</span> <span
  m='1089890'>of</span> <span m='1090060'>n</span> <span m='1090820'>is</span>
  <span m='1091240'>a</span> <span m='1091330'>triangular</span> <span
  m='1091960'>sequence,</span> <span m='1092800'>as</span> <span
  m='1092980'>I've</span> <span m='1093130'>indicated</span> <span
  m='1093670'>here.</span> </p><p><span m='1096130'>Well,</span> <span
  m='1096790'>now</span> <span m='1097090'>to</span> <span
  m='1097270'>form</span> <span m='1097570'>the</span> <span
  m='1097660'>circular</span> <span m='1098140'>convolution</span> <span
  m='1099100'>of</span> <span m='1099520'>x</span> <span m='1099900'>of</span>
  <span m='1100110'>n and</span> <span m='1100580'>x2</span> <span
  m='1100880'>of</span> <span m='1101270'>n.</span> <span
  m='1103030'>What</span> <span m='1103300'>we</span> <span
  m='1103450'>need</span> <span m='1103690'>to</span> <span
  m='1103840'>do</span> <span m='1104440'>is</span> <span
  m='1104800'>repeat</span> <span m='1105880'>this</span> <span
  m='1106060'>triangular</span> <span m='1106720'>sequence</span> <span
  m='1108430'>over</span> <span m='1108820'>and</span> <span
  m='1108910'>over</span> <span m='1109240'>again,</span> <span
  m='1109620'>add</span> <span m='1109780'>it</span> <span m='1110020'>to</span>
  <span m='1110230'>itself</span> <span m='1111490'>with</span> <span
  m='1112090'>a</span> <span m='1112450'>delay</span> <span
  m='1113380'>of</span> <span m='1114460'>capital</span> <span
  m='1115000'>N.</span> <span m='1115630'>And</span> <span
  m='1115780'>capital</span> <span m='1116310'>N</span> <span
  m='1116630'>in</span> <span m='1116830'>this</span> <span
  m='1117010'>case</span> <span m='1117760'>is</span> <span
  m='1117940'>6.</span> <span m='1119030'>So</span> <span m='1119440'>we</span>
  <span m='1119650'>want</span> <span m='1120880'>this</span> <span
  m='1121090'>sequence</span> <span m='1121780'>repeated</span> <span
  m='1122260'>over</span> <span m='1122590'>and</span> <span
  m='1122680'>over</span> <span m='1122950'>again</span> <span
  m='1123310'>and</span> <span m='1123620'>added</span> <span
  m='1123970'>to</span> <span m='1124150'>itself</span> <span
  m='1125140'>with</span> <span m='1125470'>a</span> <span
  m='1125530'>spacing</span> <span m='1126340'>of</span> <span
  m='1126490'>six</span> <span m='1126940'>and</span> <span
  m='1127030'>then</span> <span m='1127180'>12</span> <span
  m='1127540'>and</span> <span m='1127630'>then</span> <span
  m='1127750'>18,</span> <span m='1128170'>et cetera.</span> <span
  m='1130030'>Or</span> <span m='1130510'>equivalently,</span> <span
  m='1131710'>we</span> <span m='1131830'>want</span> <span
  m='1132040'>the</span> <span m='1132130'>linear</span> <span
  m='1132490'>convolution</span> <span m='1134410'>convolved</span> <span
  m='1135160'>with</span> <span m='1136180'>a</span> <span
  m='1136510'>pulse</span> <span m='1136960'>train</span> <span
  m='1137980'>where</span> <span m='1138070'>the</span> <span
  m='1138190'>spacing</span> <span m='1138700'>of</span> <span
  m='1138790'>the</span> <span m='1138910'>pulses</span> <span
  m='1139960'>is</span> <span m='1140170'>capital</span> <span
  m='1140430'>N,</span> <span m='1140920'>which</span> <span
  m='1141130'>in</span> <span m='1141220'>this</span> <span
  m='1141370'>case</span> <span m='1141700'>is</span> <span
  m='1141790'>6.</span> </p><p><span m='1143020'>So</span> <span
  m='1143530'>I've</span> <span m='1143710'>indicated</span> <span
  m='1144310'>here,</span> <span m='1144970'>the</span> <span
  m='1145240'>envelope</span> <span m='1146170'>of</span> <span
  m='1146890'>the</span> <span m='1147220'>triangular</span> <span
  m='1147880'>sequence,</span> <span m='1148480'>that's</span> <span
  m='1148690'>the</span> <span m='1148900'>envelope</span> <span
  m='1149920'>here,</span> <span m='1151180'>the</span> <span
  m='1151630'>envelope</span> <span m='1152230'>of</span> <span
  m='1152470'>the</span> <span m='1152590'>triangular</span> <span
  m='1153250'>sequence.</span> <span m='1155080'>And</span> <span
  m='1155230'>you</span> <span m='1155350'>can</span> <span
  m='1155530'>see</span> <span m='1156010'>that</span> <span
  m='1157240'>if</span> <span m='1157780'>we</span> <span
  m='1157990'>overlap</span> <span m='1158980'>these</span> <span
  m='1159160'>triangles</span> <span m='1160330'>by</span> <span
  m='1160600'>a</span> <span m='1160870'>spacing</span> <span
  m='1161440'>of</span> <span m='1161530'>six,</span> <span
  m='1163090'>then</span> <span m='1163600'>in</span> <span
  m='1163750'>fact,</span> <span m='1164860'>these</span> <span
  m='1165220'>points</span> <span m='1166480'>will</span> <span
  m='1166600'>get</span> <span m='1166780'>added</span> <span
  m='1167110'>to</span> <span m='1167290'>these</span> <span
  m='1167590'>points.</span> <span m='1168460'>Or</span> <span
  m='1169030'>when</span> <span m='1169210'>we</span> <span
  m='1169420'>add</span> <span m='1169660'>up</span> <span
  m='1170230'>the</span> <span m='1170470'>triangles,</span> <span
  m='1171400'>they'll</span> <span m='1171970'>always</span> <span
  m='1172420'>add</span> <span m='1172600'>up</span> <span m='1172750'>to</span>
  <span m='1172900'>1.</span> </p><p><span m='1175460'>So</span> <span
  m='1176830'>when</span> <span m='1177040'>we</span> <span
  m='1177130'>carry</span> <span m='1177580'>out</span> <span
  m='1178150'>this</span> <span m='1178360'>convolution,</span> <span
  m='1179770'>what</span> <span m='1179920'>we</span> <span
  m='1180100'>end</span> <span m='1180370'>up</span> <span
  m='1180580'>with</span> <span m='1181000'>are</span> <span
  m='1181180'>values</span> <span m='1183070'>that</span> <span
  m='1183280'>are</span> <span m='1183790'>constant</span> <span
  m='1184750'>from</span> <span m='1184960'>minus</span> <span
  m='1185320'>infinity</span> <span m='1185800'>to</span> <span
  m='1185890'>plus</span> <span m='1186190'>infinity,</span> <span
  m='1187270'>that's</span> <span m='1187660'>due</span> <span
  m='1187870'>to</span> <span m='1187930'>the</span> <span
  m='1188020'>convolution</span> <span m='1188710'>with</span> <span
  m='1188830'>this</span> <span m='1189070'>term.</span> <span
  m='1190840'>Finally,</span> <span m='1191490'>to</span> <span
  m='1191650'>form</span> <span m='1192070'>the</span> <span m='1192360'>N
  point,</span> <span m='1193060'>or</span> <span m='1193240'>six-point</span>
  <span m='1193840'>in</span> <span m='1193930'>this</span> <span
  m='1194110'>case,</span> <span m='1194350'>circular</span> <span
  m='1194830'>convolution,</span> <span m='1196750'>what</span> <span
  m='1196930'>we</span> <span m='1197080'>want</span> <span
  m='1197290'>to</span> <span m='1197410'>extract</span> <span
  m='1198550'>are</span> <span m='1199360'>the</span> <span
  m='1199600'>six</span> <span m='1199960'>points</span> <span
  m='1201160'>of</span> <span m='1201460'>this</span> <span
  m='1201670'>sequence</span> <span m='1202360'>one,</span> <span
  m='1202690'>two,</span> <span m='1202960'>three,</span> <span
  m='1203320'>four,</span> <span m='1203650'>five,</span> <span
  m='1203980'>six,</span> <span m='1205150'>those</span> <span
  m='1205390'>six</span> <span m='1205720'>points,</span> <span
  m='1206620'>set</span> <span m='1206920'>the</span> <span
  m='1207010'>rest</span> <span m='1207280'>to</span> <span
  m='1207570'>0,</span> <span m='1208360'>and</span> <span
  m='1208450'>the</span> <span m='1208570'>result</span> <span
  m='1209110'>is,</span> <span m='1209560'>as</span> <span
  m='1209740'>I've</span> <span m='1209890'>indicated</span> <span
  m='1210430'>here.</span> <span m='1211360'>So</span> <span
  m='1211960'>this</span> <span m='1212230'>then</span> <span
  m='1212560'>is</span> <span m='1212830'>the</span> <span m='1213040'>N</span>
  <span m='1213330'>point</span> <span m='1213620'>circular</span> <span
  m='1214060'>convolution</span> <span m='1215110'>of</span> <span
  m='1215350'>x1</span> <span m='1215605'>of</span> <span m='1215860'>n</span>
  <span m='1216430'>with</span> <span m='1216550'>x2</span> <span
  m='1217000'>of</span> <span m='1217120'>n.</span> <span
  m='1217960'>This</span> <span m='1218230'>is</span> <span
  m='1219100'>the</span> <span m='1219910'>linear</span> <span
  m='1220300'>convolution</span> <span m='1221110'>of</span> <span
  m='1221290'>x1</span> <span m='1221740'>of n</span> <span
  m='1222210'>with</span> <span m='1222370'>x2</span> <span
  m='1222580'>of</span> <span m='1222860'>n.</span> </p><p><span
  m='1224500'>It</span> <span m='1224620'>should</span> <span
  m='1224860'>be</span> <span m='1225280'>clear</span> <span
  m='1225890'>that,</span> <span m='1226530'>or</span> <span
  m='1226690'>relatively</span> <span m='1227290'>clear</span> <span
  m='1228220'>that</span> <span m='1229180'>this</span> <span
  m='1229450'>is,</span> <span m='1229730'>in</span> <span
  m='1229750'>fact,</span> <span m='1230210'>the</span> <span
  m='1230310'>way</span> <span m='1230380'>the</span> <span
  m='1230470'>circular</span> <span m='1230920'>convolution</span> <span
  m='1231670'>comes</span> <span m='1231970'>out,</span> <span
  m='1232870'>because</span> <span m='1233650'>if</span> <span
  m='1233830'>you</span> <span m='1233980'>imagine</span> <span
  m='1235540'>flipping</span> <span m='1235990'>this</span> <span
  m='1236530'>and</span> <span m='1236680'>sliding</span> <span
  m='1237310'>it,</span> <span m='1237740'>modulo</span> <span
  m='1238810'>capital</span> <span m='1239320'>N,</span> <span
  m='1239980'>or</span> <span m='1240100'>equivalently</span> <span
  m='1240700'>taking</span> <span m='1241120'>this</span> <span
  m='1241330'>sequence</span> <span m='1242050'>and</span> <span
  m='1242200'>wrapping</span> <span m='1242620'>it</span> <span
  m='1242710'>around</span> <span m='1242990'>the</span> <span
  m='1243100'>cylinder,</span> <span m='1244330'>no</span> <span
  m='1244450'>matter</span> <span m='1244720'>how</span> <span
  m='1244930'>you</span> <span m='1245080'>twist</span> <span
  m='1245410'>the</span> <span m='1245530'>cylinder</span> <span
  m='1246220'>you</span> <span m='1246370'>always</span> <span
  m='1246610'>see</span> <span m='1246820'>the</span> <span
  m='1246940'>same</span> <span m='1247240'>points.</span> <span
  m='1248140'>So</span> <span m='1248710'>in</span> <span
  m='1248830'>fact,</span> <span m='1249580'>by</span> <span
  m='1251020'>evaluating</span> <span m='1251650'>the</span> <span
  m='1251740'>circular</span> <span m='1252130'>convolution</span> <span
  m='1252790'>using</span> <span m='1253210'>modulus</span> <span
  m='1253750'>arguments,</span> <span m='1254950'>you</span> <span
  m='1255070'>would</span> <span m='1255220'>of</span> <span
  m='1255310'>course,</span> <span m='1255580'>come</span> <span
  m='1255790'>up</span> <span m='1255940'>with</span> <span
  m='1256060'>the</span> <span m='1256160'>same</span> <span
  m='1256480'>result.</span> <span m='1257200'>But</span> <span
  m='1257380'>we</span> <span m='1257530'>see</span> <span
  m='1257800'>here,</span> <span m='1258220'>how</span> <span
  m='1258610'>it</span> <span m='1258730'>comes</span> <span
  m='1259150'>out</span> <span m='1259330'>of</span> <span
  m='1259420'>this</span> <span m='1259630'>notion</span> <span
  m='1260560'>of</span> <span m='1261070'>linear</span> <span
  m='1261460'>convolution</span> <span m='1262240'>plus</span> <span
  m='1262510'>aliasing.</span> </p><p><span m='1264730'>All</span> <span
  m='1264960'>right,</span> <span m='1265180'>well</span> <span
  m='1265510'>let's</span> <span m='1266080'>look</span> <span
  m='1266470'>at</span> <span m='1266920'>another</span> <span
  m='1267340'>example.</span> <span m='1270490'>Actually,</span> <span
  m='1270940'>it's</span> <span m='1271060'>the</span> <span
  m='1271150'>same</span> <span m='1271480'>example,</span> <span
  m='1272380'>but</span> <span m='1272980'>with</span> <span
  m='1273430'>one</span> <span m='1273940'>slight</span> <span
  m='1274360'>change</span> <span m='1274810'>to</span> <span
  m='1275050'>it.</span> <span m='1276010'>Here</span> <span
  m='1276520'>again,</span> <span m='1277060'>I</span> <span
  m='1277240'>have</span> <span m='1277750'>the</span> <span
  m='1277900'>example</span> <span m='1278350'>of</span> <span
  m='1278470'>x1</span> <span m='1278920'>of</span> <span m='1279010'>n</span>
  <span m='1279460'>equal</span> <span m='1279790'>to</span> <span
  m='1279910'>x2</span> <span m='1280210'>of</span> <span m='1280510'>n.</span>
  <span m='1281530'>And</span> <span m='1281980'>again,</span> <span
  m='1282250'>we</span> <span m='1282400'>take</span> <span
  m='1282640'>both</span> <span m='1282970'>of</span> <span
  m='1283090'>them</span> <span m='1283420'>as</span> <span m='1284140'>a</span>
  <span m='1284200'>boxcar</span> <span m='1284830'>sequence.</span> <span
  m='1285910'>In</span> <span m='1286000'>other</span> <span
  m='1286150'>words,</span> <span m='1286360'>rectangular</span> <span
  m='1287540'>or</span> <span m='1287670'>constant</span> <span
  m='1288160'>value</span> <span m='1288550'>in</span> <span
  m='1288640'>the</span> <span m='1288730'>interval</span> <span
  m='1289060'>0</span> <span m='1289420'>to n</span> <span
  m='1289720'>minus</span> <span m='1290140'>1,</span> <span
  m='1291100'>and</span> <span m='1291220'>0</span> <span
  m='1291670'>outside</span> <span m='1292150'>that</span> <span
  m='1292360'>interval.</span> <span m='1294290'>Again</span> <span
  m='1294590'>of</span> <span m='1294710'>course,</span> <span
  m='1295440'>then</span> <span m='1295640'>we</span> <span
  m='1295790'>have</span> <span m='1296720'>the</span> <span
  m='1296810'>linear</span> <span m='1297200'>convolution</span> <span
  m='1298190'>of</span> <span m='1298340'>these</span> <span
  m='1298610'>two</span> <span m='1300250'>as</span> <span m='1301480'>a</span>
  <span m='1301540'>triangle,</span> <span m='1303200'>which</span> <span
  m='1303400'>is</span> <span m='1303910'>what</span> <span
  m='1304300'>I've</span> <span m='1304480'>denoted</span> <span
  m='1304930'>here.</span> </p><p><span m='1306890'>And</span> <span
  m='1307010'>now</span> <span m='1307310'>let's</span> <span
  m='1307610'>look,</span> <span m='1308090'>not</span> <span
  m='1308570'>at</span> <span m='1309110'>the</span> <span m='1309290'>N</span>
  <span m='1309590'>point</span> <span m='1309940'>circular</span> <span
  m='1310430'>convolution,</span> <span m='1311960'>but</span> <span
  m='1312200'>at</span> <span m='1312770'>the</span> <span m='1313550'>2n</span>
  <span m='1314540'>point</span> <span m='1315020'>circular</span> <span
  m='1315530'>convolution</span> <span m='1316820'>of</span> <span
  m='1317430'>x1</span> <span m='1317900'>of</span> <span
  m='1318530'>with</span> <span m='1318710'>x2</span> <span
  m='1319190'>of</span> <span m='1319320'>n.</span> <span m='1320990'>In</span>
  <span m='1321110'>that</span> <span m='1321320'>case,</span> <span
  m='1321920'>we</span> <span m='1322070'>want</span> <span
  m='1322310'>this</span> <span m='1322490'>triangular</span> <span
  m='1323150'>sequence</span> <span m='1325280'>repeated</span> <span
  m='1326030'>and</span> <span m='1326210'>added</span> <span
  m='1326510'>to</span> <span m='1326690'>itself,</span> <span
  m='1327720'>not</span> <span m='1327890'>with</span> <span
  m='1328040'>a</span> <span m='1328100'>spacing</span> <span
  m='1328730'>of</span> <span m='1328880'>capital</span> <span
  m='1329420'>N</span> <span m='1329780'>as</span> <span m='1329990'>in</span>
  <span m='1330050'>the</span> <span m='1330140'>previous</span> <span
  m='1330590'>example,</span> <span m='1331880'>but</span> <span
  m='1332480'>with</span> <span m='1332900'>a</span> <span
  m='1333200'>spacing</span> <span m='1334160'>of</span> <span
  m='1334880'>2</span> <span m='1335090'>capital</span> <span
  m='1335365'>N</span> <span m='1337010'>because</span> <span
  m='1337940'>we're</span> <span m='1338060'>doing</span> <span
  m='1338420'>a</span> <span m='1338510'>2</span> <span
  m='1338720'>capital</span> <span m='1339200'>N</span> <span
  m='1339475'>point</span> <span m='1339750'>circular</span> <span
  m='1340220'>convolution.</span> <span m='1341450'>Well</span> <span
  m='1341630'>if</span> <span m='1341750'>we</span> <span m='1341870'>do</span>
  <span m='1342050'>that,</span> <span m='1342830'>then</span> <span
  m='1342950'>we</span> <span m='1343100'>end</span> <span m='1343280'>up</span>
  <span m='1343430'>with</span> <span m='1343550'>this</span> <span
  m='1343670'>triangular</span> <span m='1344210'>sequence</span> <span
  m='1345230'>added</span> <span m='1345500'>to</span> <span
  m='1345680'>itself</span> <span m='1346040'>starting</span> <span
  m='1346490'>here,</span> <span m='1347750'>finishing</span> <span
  m='1348200'>over</span> <span m='1348410'>there.</span> <span
  m='1348920'>Or</span> <span m='1349870'>in</span> <span
  m='1350000'>general,</span> <span m='1350730'>if</span> <span
  m='1350810'>we</span> <span m='1350930'>convolve</span> <span
  m='1351470'>it</span> <span m='1351950'>with</span> <span
  m='1352130'>this</span> <span m='1352340'>pulse</span> <span
  m='1352730'>train,</span> <span m='1353900'>then</span> <span
  m='1354860'>the</span> <span m='1355340'>resulting</span> <span
  m='1355910'>periodic</span> <span m='1356540'>sequence</span> <span
  m='1357320'>that</span> <span m='1357470'>we</span> <span
  m='1357650'>end</span> <span m='1357860'>up</span> <span
  m='1358070'>with</span> <span m='1359700'>has</span> <span
  m='1360110'>triangular</span> <span m='1360740'>periods</span> <span
  m='1361340'>to</span> <span m='1361580'>it</span> <span
  m='1362300'>with</span> <span m='1362540'>a</span> <span
  m='1362600'>period</span> <span m='1363110'>now,</span> <span
  m='1363920'>not</span> <span m='1364110'>have</span> <span
  m='1364220'>capital</span> <span m='1364730'>N</span> <span
  m='1365000'>as</span> <span m='1365120'>we</span> <span m='1365270'>had</span>
  <span m='1365420'>in</span> <span m='1365510'>the</span> <span
  m='1365570'>previous</span> <span m='1366020'>example,</span> <span
  m='1367030'>but</span> <span m='1367190'>of</span> <span m='1367310'>2</span>
  <span m='1367490'>capital</span> <span m='1367750'>N.</span> </p><p><span
  m='1370020'>Finally,</span> <span m='1370530'>to</span> <span
  m='1370680'>get</span> <span m='1370860'>the</span> <span
  m='1370950'>circular</span> <span m='1371400'>convolution,</span> <span
  m='1373060'>we</span> <span m='1373080'>see</span> <span
  m='1373680'>that,</span> <span m='1374820'>or</span> <span
  m='1374970'>we</span> <span m='1375150'>recall</span> <span
  m='1375930'>that</span> <span m='1376380'>we</span> <span
  m='1376560'>want</span> <span m='1376830'>to</span> <span
  m='1377070'>extract</span> <span m='1378030'>one</span> <span
  m='1378240'>period</span> <span m='1378750'>of</span> <span
  m='1378900'>this.</span> <span m='1379890'>So</span> <span
  m='1380370'>we</span> <span m='1380550'>extract</span> <span
  m='1381020'>a</span> <span m='1381100'>period</span> <span
  m='1381900'>from</span> <span m='1382110'>0</span> <span m='1383460'>to</span>
  <span m='1384120'>2</span> <span m='1384300'>capital</span> <span
  m='1384810'>N</span> <span m='1384930'>minus</span> <span
  m='1385350'>1.</span> <span m='1386680'>So</span> <span m='1386730'>we</span>
  <span m='1386850'>have</span> <span m='1386970'>0</span> <span
  m='1387900'>to</span> <span m='1388020'>2</span> <span
  m='1388230'>capital</span> <span m='1388740'>N</span> <span
  m='1388860'>minus</span> <span m='1389330'>1.</span> <span
  m='1390210'>And</span> <span m='1390330'>this</span> <span
  m='1390570'>result</span> <span m='1391020'>then</span> <span
  m='1391410'>is</span> <span m='1391740'>the</span> <span m='1391920'>2</span>
  <span m='1392310'>N point</span> <span m='1392970'>circular</span> <span
  m='1393420'>convolution</span> <span m='1394830'>of</span> <span
  m='1395350'>x1</span> <span m='1395610'>of</span> <span m='1395870'>n</span>
  <span m='1396630'>with</span> <span m='1396780'>x2</span> <span
  m='1396990'>two</span> <span m='1397230'>of</span> <span m='1397320'>n.</span>
  </p><p><span m='1399370'>It's</span> <span m='1399390'>interesting</span>
  <span m='1400170'>to</span> <span m='1400410'>note</span> <span
  m='1401130'>that</span> <span m='1401820'>in</span> <span
  m='1401970'>this</span> <span m='1402210'>case,</span> <span
  m='1403080'>the</span> <span m='1403200'>circular</span> <span
  m='1403650'>convolution</span> <span m='1405390'>in</span> <span
  m='1405510'>fact,</span> <span m='1406320'>came</span> <span
  m='1406650'>out</span> <span m='1406860'>looking</span> <span
  m='1407280'>like</span> <span m='1407460'>the</span> <span
  m='1407550'>linear</span> <span m='1407970'>convolution</span> <span
  m='1408900'>of</span> <span m='1409050'>x</span> <span m='1409250'>of</span>
  <span m='1409480'>n</span> <span m='1410040'>and</span> <span
  m='1410220'>x2</span> <span m='1410660'>of n.</span> <span
  m='1412230'>And</span> <span m='1412380'>the</span> <span
  m='1412470'>reason</span> <span m='1412860'>for</span> <span
  m='1413040'>that</span> <span m='1413430'>we</span> <span
  m='1413610'>see,</span> <span m='1414570'>is</span> <span
  m='1414810'>that</span> <span m='1415620'>when</span> <span
  m='1415860'>we</span> <span m='1415980'>did</span> <span
  m='1416130'>the</span> <span m='1416250'>convolution</span> <span
  m='1417360'>with</span> <span m='1417510'>this</span> <span
  m='1417690'>pulse</span> <span m='1418110'>train,</span> <span
  m='1419460'>we</span> <span m='1419580'>chose</span> <span
  m='1420030'>the</span> <span m='1420120'>spacing</span> <span
  m='1420870'>of</span> <span m='1421020'>the</span> <span
  m='1421140'>pulse</span> <span m='1421500'>train</span> <span
  m='1422580'>large</span> <span m='1423000'>enough</span> <span
  m='1424020'>so</span> <span m='1424290'>that</span> <span
  m='1424800'>there</span> <span m='1424950'>was</span> <span
  m='1425130'>no</span> <span m='1425520'>interference</span> <span
  m='1426780'>from</span> <span m='1427080'>successive</span> <span
  m='1427680'>replicas</span> <span m='1428790'>of</span> <span
  m='1428940'>this</span> <span m='1429120'>linear</span> <span
  m='1429480'>convolution.</span> </p><p><span m='1431810'>Well,</span> <span
  m='1432500'>that</span> <span m='1432710'>suggests</span> <span
  m='1433190'>an</span> <span m='1433310'>interesting</span> <span
  m='1433790'>thing.</span> <span m='1434360'>It</span> <span
  m='1434480'>suggests</span> <span m='1435620'>that</span> <span
  m='1436490'>we</span> <span m='1436670'>could</span> <span
  m='1436970'>in</span> <span m='1437150'>fact,</span> <span
  m='1438230'>implement</span> <span m='1439850'>a</span> <span
  m='1440000'>linear</span> <span m='1440390'>convolution</span> <span
  m='1441830'>from</span> <span m='1442040'>a</span> <span
  m='1442100'>circular</span> <span m='1442550'>convolution</span> <span
  m='1444140'>if</span> <span m='1444680'>we're</span> <span
  m='1444860'>careful</span> <span m='1445400'>enough</span> <span
  m='1446300'>to</span> <span m='1446450'>pick</span> <span
  m='1447230'>the</span> <span m='1447350'>length</span> <span
  m='1447740'>of</span> <span m='1447830'>the</span> <span
  m='1447920'>circular</span> <span m='1448370'>convolution</span> <span
  m='1449690'>long</span> <span m='1450050'>enough.</span> <span
  m='1451250'>Now</span> <span m='1451370'>what</span> <span
  m='1451490'>does</span> <span m='1451610'>long</span> <span
  m='1451880'>enough</span> <span m='1452120'>mean?</span> <span
  m='1452900'>Well,</span> <span m='1453050'>long</span> <span
  m='1453380'>enough</span> <span m='1454160'>means</span> <span
  m='1455030'>that</span> <span m='1455750'>the</span> <span
  m='1455840'>length</span> <span m='1456170'>of</span> <span
  m='1456260'>the</span> <span m='1456380'>circular</span> <span
  m='1456830'>convolution</span> <span m='1458330'>has</span> <span
  m='1458630'>to</span> <span m='1458780'>be</span> <span
  m='1459530'>longer</span> <span m='1460790'>than</span> <span
  m='1461420'>the</span> <span m='1461540'>length</span> <span
  m='1462080'>of</span> <span m='1462290'>the</span> <span
  m='1462410'>linear</span> <span m='1462740'>convolution.</span> </p><p><span
  m='1464870'>You</span> <span m='1465020'>can</span> <span
  m='1465170'>show</span> <span m='1465620'>incidentally,</span> <span
  m='1466340'>and</span> <span m='1466580'>you'll</span> <span
  m='1466760'>see</span> <span m='1467270'>this</span> <span
  m='1467480'>in</span> <span m='1467600'>more</span> <span
  m='1467750'>detail</span> <span m='1468260'>in</span> <span
  m='1468350'>the</span> <span m='1468440'>text,</span> <span
  m='1469460'>that</span> <span m='1469730'>if</span> <span
  m='1469940'>you</span> <span m='1470090'>have</span> <span
  m='1471350'>sequence</span> <span m='1471890'>of</span> <span
  m='1471980'>length</span> <span m='1472250'>capital</span> <span
  m='1472790'>N</span> <span m='1473690'>and</span> <span
  m='1473810'>another</span> <span m='1474110'>sequence</span> <span
  m='1474620'>of</span> <span m='1474710'>length</span> <span
  m='1474980'>capital</span> <span m='1475490'>M,</span> <span
  m='1476930'>then</span> <span m='1477110'>the</span> <span
  m='1477200'>linear</span> <span m='1477530'>convolution</span> <span
  m='1478250'>of</span> <span m='1478340'>the</span> <span
  m='1478430'>two</span> <span m='1479060'>is</span> <span
  m='1479240'>always</span> <span m='1479660'>going</span> <span
  m='1479960'>to</span> <span m='1480110'>be</span> <span
  m='1481640'>shorter</span> <span m='1482090'>than</span> <span
  m='1482270'>or</span> <span m='1482390'>equal</span> <span
  m='1482780'>to</span> <span m='1483230'>n</span> <span m='1483500'>plus</span>
  <span m='1483830'>m</span> <span m='1484250'>minus</span> <span
  m='1484640'>one points.</span> <span m='1486020'>So</span> <span
  m='1486200'>if</span> <span m='1486350'>we</span> <span m='1486440'>do</span>
  <span m='1486620'>the</span> <span m='1486740'>circular</span> <span
  m='1487220'>convolution</span> <span m='1487850'>on</span> <span
  m='1487970'>the</span> <span m='1488060'>basis</span> <span
  m='1488510'>of</span> <span m='1488630'>n</span> <span m='1488780'>plus</span>
  <span m='1489110'>m</span> <span m='1489545'>minus</span> <span
  m='1489980'>1,</span> <span m='1490490'>or</span> <span m='1490670'>n</span>
  <span m='1490840'>plus</span> <span m='1491150'>m--</span> <span
  m='1491930'>well,</span> <span m='1492260'>take</span> <span
  m='1492710'>n</span> <span m='1493100'>plus</span> <span m='1493380'>m,</span>
  <span m='1493610'>that</span> <span m='1493760'>will</span> <span
  m='1493880'>certainly</span> <span m='1494270'>work,</span> <span
  m='1495080'>then</span> <span m='1495710'>the</span> <span
  m='1495800'>circular</span> <span m='1496280'>convolution</span> <span
  m='1497600'>will</span> <span m='1497960'>end</span> <span
  m='1498260'>up</span> <span m='1498830'>corresponding</span> <span
  m='1500060'>to</span> <span m='1500210'>a</span> <span
  m='1500240'>linear</span> <span m='1500600'>convolution.</span> <span
  m='1502190'>And</span> <span m='1502310'>this</span> <span
  m='1502550'>is</span> <span m='1502670'>the</span> <span
  m='1502790'>way</span> <span m='1503780'>that</span> <span
  m='1504290'>we</span> <span m='1504500'>can</span> <span
  m='1504770'>carry</span> <span m='1505250'>out</span> <span
  m='1506210'>a</span> <span m='1507290'>linear</span> <span
  m='1507620'>convolution</span> <span m='1508820'>using</span> <span
  m='1509120'>circular</span> <span m='1509600'>convolution.</span> </p><p><span
  m='1511220'>This</span> <span m='1511430'>is</span> <span
  m='1511520'>commonly</span> <span m='1512060'>referred</span> <span
  m='1512510'>to</span> <span m='1513230'>as</span> <span
  m='1514310'>padding</span> <span m='1515120'>with</span> <span
  m='1515300'>zeros.</span> <span m='1516530'>And</span> <span
  m='1516650'>what</span> <span m='1516890'>that</span> <span
  m='1517130'>means</span> <span m='1517910'>is</span> <span
  m='1518720'>treating</span> <span m='1519590'>this</span> <span m='1519830'>N
  point</span> <span m='1520490'>sequence</span> <span m='1522050'>not</span>
  <span m='1522290'>as</span> <span m='1522440'>an</span> <span m='1522560'>N
  point</span> <span m='1523040'>sequence</span> <span m='1523460'>when</span>
  <span m='1523580'>we</span> <span m='1523700'>compute</span> <span
  m='1524060'>the</span> <span m='1524150'>DFT,</span> <span
  m='1525920'>but</span> <span m='1526640'>as</span> <span m='1526790'>a</span>
  <span m='1526850'>sequence</span> <span m='1527540'>of</span> <span
  m='1527750'>length</span> <span m='1528500'>2</span> <span
  m='1528680'>capital</span> <span m='1529210'>N,</span> <span
  m='1530240'>so</span> <span m='1530480'>that</span> <span
  m='1530900'>if</span> <span m='1531380'>we</span> <span
  m='1531590'>computed</span> <span m='1532550'>a</span> <span
  m='1532760'>2</span> <span m='1533000'>capital</span> <span m='1533510'>N
  point</span> <span m='1533930'>DFT</span> <span m='1534650'>of</span> <span
  m='1534770'>this</span> <span m='1534950'>sequence,</span> <span
  m='1535970'>padding</span> <span m='1536360'>out</span> <span
  m='1536690'>with</span> <span m='1537200'>capital</span> <span
  m='1537650'>N</span> <span m='1537860'>zeroes,</span> <span
  m='1540050'>multiplied</span> <span m='1541190'>that</span> <span
  m='1541460'>DFT</span> <span m='1542540'>together</span> <span
  m='1542960'>with</span> <span m='1543140'>itself</span> <span
  m='1544010'>and</span> <span m='1544160'>then</span> <span
  m='1544310'>computed</span> <span m='1544760'>the</span> <span
  m='1544910'>inverse</span> <span m='1545360'>DFT,</span> <span
  m='1546950'>what</span> <span m='1547130'>we</span> <span
  m='1547280'>would</span> <span m='1547430'>get,</span> <span
  m='1547790'>in</span> <span m='1547940'>fact,</span> <span
  m='1548480'>because</span> <span m='1548900'>of</span> <span
  m='1548960'>the</span> <span m='1549080'>fact</span> <span
  m='1549380'>that</span> <span m='1549470'>we</span> <span
  m='1549590'>padded</span> <span m='1549980'>out</span> <span
  m='1550160'>with</span> <span m='1550310'>zeroes</span> <span
  m='1551600'>is</span> <span m='1552200'>a</span> <span m='1552470'>2</span>
  <span m='1553480'>N point</span> <span m='1553990'>circular</span> <span
  m='1554450'>convolution,</span> <span m='1555680'>which</span> <span
  m='1555890'>would</span> <span m='1556040'>correspond</span> <span
  m='1556760'>to</span> <span m='1556880'>the</span> <span
  m='1556970'>linear</span> <span m='1557300'>convolution.</span> </p><p><span
  m='1559340'>So</span> <span m='1559910'>this</span> <span
  m='1560150'>is</span> <span m='1560300'>the</span> <span
  m='1560420'>way,</span> <span m='1560930'>then</span> <span
  m='1561530'>that</span> <span m='1562190'>we</span> <span
  m='1562310'>can</span> <span m='1563360'>modify</span> <span
  m='1563930'>a</span> <span m='1564020'>circular</span> <span
  m='1564470'>convolution</span> <span m='1565430'>so</span> <span
  m='1565760'>that</span> <span m='1566090'>it</span> <span
  m='1566250'>implements</span> <span m='1566870'>for</span> <span
  m='1567200'>us</span> <span m='1567590'>a</span> <span
  m='1567650'>linear</span> <span m='1568040'>convolution.</span> <span
  m='1569510'>And</span> <span m='1570470'>when</span> <span
  m='1571010'>we</span> <span m='1571310'>actually</span> <span
  m='1571850'>implement</span> <span m='1573080'>a</span> <span
  m='1573890'>digital</span> <span m='1574280'>filter,</span> <span
  m='1574880'>or</span> <span m='1575060'>a</span> <span
  m='1575090'>discrete</span> <span m='1575480'>time</span> <span
  m='1575780'>system</span> <span m='1576890'>using</span> <span
  m='1577190'>an</span> <span m='1577280'>explicit</span> <span
  m='1577820'>computation</span> <span m='1578630'>of</span> <span
  m='1578720'>the</span> <span m='1578810'>discrete</span> <span
  m='1579200'>Fourier</span> <span m='1579650'>transform,</span> <span
  m='1580880'>then</span> <span m='1581210'>of</span> <span
  m='1581330'>course,</span> <span m='1581690'>this</span> <span
  m='1581930'>is</span> <span m='1582050'>what</span> <span
  m='1582230'>we</span> <span m='1582380'>have</span> <span
  m='1582620'>to</span> <span m='1582740'>do</span> <span m='1583520'>to</span>
  <span m='1583670'>avoid</span> <span m='1584540'>the</span> <span
  m='1584660'>circular</span> <span m='1585170'>convolution</span> <span
  m='1586190'>since</span> <span m='1586460'>what</span> <span
  m='1586610'>we</span> <span m='1586760'>want</span> <span
  m='1587000'>in</span> <span m='1587090'>that</span> <span
  m='1587270'>case</span> <span m='1587690'>is</span> <span m='1587810'>a</span>
  <span m='1587870'>linear</span> <span m='1588230'>convolution.</span>
  </p><p><span m='1590210'>Well,</span> <span m='1590570'>it's</span> <span
  m='1590750'>important,</span> <span m='1591530'>very</span> <span
  m='1591800'>important</span> <span m='1593090'>to</span> <span
  m='1593570'>keep</span> <span m='1593900'>straight</span> <span
  m='1594470'>first</span> <span m='1594830'>of</span> <span
  m='1594950'>all,</span> <span m='1595310'>the</span> <span
  m='1595430'>properties</span> <span m='1596000'>of</span> <span
  m='1596090'>circular</span> <span m='1596510'>convolution.</span> <span
  m='1597650'>Sometimes</span> <span m='1598670'>in</span> <span
  m='1598760'>fact,</span> <span m='1599030'>circular</span> <span
  m='1599450'>convolution</span> <span m='1599980'>is</span> <span
  m='1600100'>what</span> <span m='1600230'>you</span> <span
  m='1600320'>would</span> <span m='1600410'>like</span> <span
  m='1600650'>to</span> <span m='1600770'>get.</span> <span
  m='1602420'>The</span> <span m='1602510'>notion,</span> <span
  m='1603260'>the</span> <span m='1603380'>relationship</span> <span
  m='1604100'>between</span> <span m='1604400'>circular</span> <span
  m='1604880'>and</span> <span m='1604970'>linear</span> <span
  m='1605300'>convolution,</span> <span m='1606060'>mainly</span> <span
  m='1606530'>this</span> <span m='1606740'>notion</span> <span
  m='1607370'>of</span> <span m='1607610'>circular</span> <span
  m='1608090'>convolution</span> <span m='1609080'>being</span> <span
  m='1609320'>equal</span> <span m='1609590'>to</span> <span
  m='1609710'>linear</span> <span m='1610040'>convolution</span> <span
  m='1610700'>plus</span> <span m='1610970'>aliasing.</span> <span
  m='1612230'>And</span> <span m='1612320'>then</span> <span
  m='1612440'>finally</span> <span m='1612920'>the</span> <span
  m='1613040'>way</span> <span m='1613460'>in</span> <span
  m='1613610'>which</span> <span m='1614120'>you</span> <span
  m='1614270'>can</span> <span m='1614450'>use</span> <span m='1614720'>a</span>
  <span m='1614810'>circular</span> <span m='1615260'>convolution</span> <span
  m='1616550'>to</span> <span m='1617240'>actually</span> <span
  m='1617750'>implement</span> <span m='1618470'>a</span> <span
  m='1618530'>linear</span> <span m='1618860'>convolution.</span> </p><p><span
  m='1621570'>Now</span> <span m='1621680'>what</span> <span
  m='1621800'>I'd</span> <span m='1621920'>like</span> <span
  m='1622130'>to</span> <span m='1622280'>do</span> <span m='1622760'>is</span>
  <span m='1623630'>really</span> <span m='1623930'>cement</span> <span
  m='1624440'>this</span> <span m='1625160'>by</span> <span
  m='1626360'>illustrating</span> <span m='1627710'>these</span> <span
  m='1628040'>notions,</span> <span m='1629090'>finally,</span> <span
  m='1630200'>with</span> <span m='1630620'>a</span> <span
  m='1630710'>film</span> <span m='1631850'>which</span> <span
  m='1632300'>will</span> <span m='1632600'>depict</span> <span
  m='1633110'>a</span> <span m='1633170'>number</span> <span
  m='1633470'>of</span> <span m='1633590'>things.</span> <span
  m='1634140'>It's</span> <span m='1634700'>actually</span> <span
  m='1635240'>the</span> <span m='1635360'>continuation</span> <span
  m='1636110'>of</span> <span m='1636200'>a</span> <span m='1636260'>film</span>
  <span m='1636830'>that</span> <span m='1637100'>you</span> <span
  m='1637250'>saw</span> <span m='1637730'>in</span> <span
  m='1638750'>the</span> <span m='1638930'>first</span> <span
  m='1639230'>lecture</span> <span m='1639560'>that</span> <span
  m='1639650'>we</span> <span m='1639800'>had</span> <span m='1640040'>on</span>
  <span m='1640370'>discrete</span> <span m='1640760'>time</span> <span
  m='1641060'>convolution.</span> <span m='1642810'>We'll</span> <span
  m='1643250'>show</span> <span m='1643490'>first</span> <span
  m='1643820'>of</span> <span m='1643940'>all,</span> <span
  m='1644900'>linear</span> <span m='1645260'>convolution</span> <span
  m='1647450'>just</span> <span m='1647780'>exactly</span> <span
  m='1648230'>as</span> <span m='1648350'>you had</span> <span
  m='1648560'>seen</span> <span m='1648830'>before.</span> <span
  m='1650450'>Second</span> <span m='1650930'>of</span> <span
  m='1651050'>all,</span> <span m='1651830'>periodic</span> <span
  m='1652430'>or</span> <span m='1652520'>circular</span> <span
  m='1653000'>convolution</span> <span m='1654140'>and</span> <span
  m='1654290'>the</span> <span m='1654380'>difference</span> <span
  m='1654830'>between</span> <span m='1655280'>them.</span> <span
  m='1656580'>The</span> <span m='1656600'>third</span> <span
  m='1656870'>thing</span> <span m='1657410'>that</span> <span
  m='1657590'>the</span> <span m='1657680'>film</span> <span
  m='1657920'>will</span> <span m='1658100'>illustrate</span> <span
  m='1658940'>is</span> <span m='1659900'>the</span> <span
  m='1660230'>relationship</span> <span m='1661100'>between</span> <span
  m='1661550'>linear</span> <span m='1661880'>convolution</span> <span
  m='1662720'>and</span> <span m='1662900'>periodic</span> <span
  m='1663500'>or</span> <span m='1663590'>circular</span> <span
  m='1664010'>convolution,</span> <span m='1665180'>namely,</span> <span
  m='1665720'>the</span> <span m='1665810'>notion</span> <span
  m='1666350'>of</span> <span m='1666470'>circular</span> <span
  m='1666920'>convolution</span> <span m='1667730'>as</span> <span
  m='1667910'>linear</span> <span m='1668240'>convolution</span> <span
  m='1669380'>plus</span> <span m='1669650'>aliasing.</span> <span
  m='1671840'>And</span> <span m='1672260'>finally,</span> <span
  m='1673170'>the</span> <span m='1673370'>fourth</span> <span
  m='1673790'>thing</span> <span m='1674420'>that</span> <span
  m='1674870'>it</span> <span m='1674990'>will</span> <span
  m='1675170'>illustrate</span> <span m='1676340'>is</span> <span
  m='1677180'>this</span> <span m='1677390'>notion</span> <span
  m='1678080'>of</span> <span m='1678260'>padding</span> <span
  m='1679160'>with</span> <span m='1679410'>zeros</span> <span
  m='1680720'>so</span> <span m='1681020'>that</span> <span m='1681380'>a</span>
  <span m='1681470'>circular</span> <span m='1681980'>convolution</span> <span
  m='1683510'>can</span> <span m='1683750'>be</span> <span
  m='1683870'>used</span> <span m='1684590'>to</span> <span
  m='1684950'>implement</span> <span m='1685420'>a</span> <span
  m='1685490'>linear</span> <span m='1685790'>convolution.</span> </p><p><span
  m='1687060'>So</span> <span m='1687470'>let's</span> <span
  m='1687710'>go</span> <span m='1687860'>to</span> <span m='1687950'>the</span>
  <span m='1688070'>film</span> <span m='1688400'>now</span> <span
  m='1688850'>and</span> <span m='1689120'>go</span> <span
  m='1689330'>through</span> <span m='1689600'>these</span> <span
  m='1689810'>various</span> <span m='1690260'>examples</span> <span
  m='1691520'>with</span> <span m='1691730'>the</span> <span
  m='1691820'>hope</span> <span m='1692300'>that</span> <span
  m='1693770'>at</span> <span m='1693920'>the</span> <span
  m='1694040'>end</span> <span m='1694250'>of</span> <span
  m='1694370'>this,</span> <span m='1695060'>the</span> <span
  m='1695330'>notion</span> <span m='1695930'>and</span> <span
  m='1696020'>relationships</span> <span m='1696860'>will</span> <span
  m='1697580'>really</span> <span m='1697880'>be</span> <span
  m='1698090'>very,</span> <span m='1698410'>vivid.</span> </p><p><span
  m='1709680'>OK</span> <span m='1709980'>the</span> <span
  m='1710070'>convolutions</span> <span m='1710750'>sum</span> <span
  m='1711070'>then,</span> <span m='1711540'>we</span> <span
  m='1711720'>have</span> <span m='1712050'>is</span> <span
  m='1712200'>the</span> <span m='1712320'>sum</span> <span
  m='1712590'>of</span> <span m='1712710'>x</span> <span m='1712920'>of</span>
  <span m='1713040'>k,</span> <span m='1713490'>h</span> <span m='1713760'>of
  n</span> <span m='1714075'>minus</span> <span m='1714390'>k.</span> <span
  m='1715560'>And</span> <span m='1716250'>so</span> <span
  m='1716760'>what</span> <span m='1716940'>we</span> <span
  m='1717090'>would</span> <span m='1717210'>like</span> <span
  m='1717390'>to</span> <span m='1717480'>illustrate</span> <span
  m='1718200'>is</span> <span m='1718680'>the</span> <span
  m='1718830'>operation</span> <span m='1719670'>of</span> <span
  m='1719880'>evaluating</span> <span m='1721140'>this</span> <span
  m='1721280'>sum.</span> <span m='1722460'>On</span> <span
  m='1722550'>the</span> <span m='1722640'>top</span> <span
  m='1723000'>we</span> <span m='1723150'>have</span> <span m='1723750'>x</span>
  <span m='1724020'>of</span> <span m='1724150'>k,</span> <span
  m='1724860'>on</span> <span m='1724980'>the</span> <span
  m='1725070'>bottom</span> <span m='1725490'>we</span> <span
  m='1725640'>have</span> <span m='1725880'>h</span> <span m='1726120'>of</span>
  <span m='1726240'>k,</span> <span m='1726750'>h of</span> <span
  m='1727170'>k</span> <span m='1727590'>being</span> <span
  m='1727830'>an</span> <span m='1727950'>exponential.</span> <span
  m='1729390'>And</span> <span m='1729570'>now</span> <span
  m='1730230'>we</span> <span m='1730380'>see</span> <span m='1730680'>h</span>
  <span m='1731030'>of</span> <span m='1731280'>minus</span> <span
  m='1731640'>k,</span> <span m='1732360'>namely</span> <span
  m='1732780'>h</span> <span m='1733050'>of</span> <span m='1733140'>k</span>
  <span m='1733440'>flipped</span> <span m='1733830'>over.</span> <span
  m='1735030'>As</span> <span m='1735180'>we</span> <span
  m='1735300'>shift</span> <span m='1735750'>h</span> <span
  m='1736020'>of</span> <span m='1736110'>k</span> <span m='1736350'>to</span>
  <span m='1736500'>the</span> <span m='1736620'>left,</span> <span
  m='1737820'>corresponding</span> <span m='1738420'>to</span> <span
  m='1738500'>n</span> <span m='1738600'>equals</span> <span
  m='1738900'>minus</span> <span m='1739320'>1,</span> <span
  m='1739800'>then</span> <span m='1740250'>back</span> <span
  m='1740490'>to</span> <span m='1740640'>0,</span> <span m='1742340'>and</span>
  <span m='1742460'>now</span> <span m='1742820'>to</span> <span
  m='1742970'>the</span> <span m='1743090'>right.</span> <span
  m='1746050'>So</span> <span m='1746400'>we</span> <span
  m='1746580'>have</span> <span m='1746790'>h</span> <span m='1747030'>of</span>
  <span m='1747150'>1</span> <span m='1747390'>minus</span> <span
  m='1747860'>k.</span> <span m='1749010'>And</span> <span
  m='1750030'>then</span> <span m='1750300'>to</span> <span
  m='1750450'>form</span> <span m='1750720'>y</span> <span m='1750840'>of</span>
  <span m='1751110'>n,</span> <span m='1751830'>we</span> <span
  m='1751980'>want</span> <span m='1752190'>the</span> <span
  m='1752280'>product</span> <span m='1753000'>of</span> <span
  m='1753240'>h</span> <span m='1753630'>of</span> <span
  m='1753930'>minus</span> <span m='1754305'>k</span> <span
  m='1754680'>shifted</span> <span m='1755700'>with</span> <span
  m='1756030'>x</span> <span m='1756330'>of</span> <span m='1756450'>k,</span>
  <span m='1757200'>that</span> <span m='1757410'>product</span> <span
  m='1757830'>summed</span> <span m='1758220'>from</span> <span
  m='1758460'>minus</span> <span m='1758820'>infinity</span> <span
  m='1759330'>to</span> <span m='1759450'>plus</span> <span
  m='1759720'>infinity.</span> </p><p><span m='1761440'>"</span> <span
  m='1761490'>here</span> <span m='1761670'>we</span> <span
  m='1761820'>see</span> <span m='1762150'>x</span> <span m='1762390'>of</span>
  <span m='1762510'>k</span> <span m='1762930'>times</span> <span
  m='1763740'>h</span> <span m='1764160'>of</span> <span m='1764730'>1</span>
  <span m='1764940'>minus</span> <span m='1765300'>k,</span> <span
  m='1765750'>2</span> <span m='1765990'>minus</span> <span
  m='1766230'>k,</span> <span m='1767010'>3</span> <span
  m='1767325'>minus</span> <span m='1767640'>k,</span> <span
  m='1768000'>et</span> <span m='1768330'>cetera,</span> <span
  m='1769410'>those</span> <span m='1769650'>multiplied</span> <span
  m='1770340'>and</span> <span m='1770430'>then</span> <span
  m='1770610'>summed</span> <span m='1770970'>from</span> <span
  m='1771170'>minus</span> <span m='1771540'>infinity</span> <span
  m='1772080'>to</span> <span m='1772180'>plus</span> <span
  m='1772380'>infinity.</span> <span m='1773480'>We</span> <span
  m='1773580'>see</span> <span m='1773940'>during</span> <span
  m='1774240'>this</span> <span m='1774450'>portion</span> <span
  m='1775260'>that</span> <span m='1775770'>more</span> <span
  m='1776040'>and</span> <span m='1776130'>more</span> <span
  m='1776340'>values</span> <span m='1776820'>of</span> <span
  m='1776940'>h</span> <span m='1777330'>are</span> <span
  m='1777510'>engaged</span> <span m='1778020'>with</span> <span
  m='1778170'>non-zero</span> <span m='1778770'>values</span> <span
  m='1779250'>of</span> <span m='1779370'>x.</span> <span m='1779880'>And</span>
  <span m='1780030'>so</span> <span m='1780240'>y</span> <span
  m='1780510'>of</span> <span m='1780660'>n</span> <span
  m='1780820'>grows</span> <span m='1781860'>until</span> <span
  m='1782460'>we</span> <span m='1782670'>reach</span> <span
  m='1783060'>the</span> <span m='1783180'>point</span> <span
  m='1783570'>where</span> <span m='1783810'>values</span> <span
  m='1784320'>fall</span> <span m='1784650'>off</span> <span
  m='1784830'>the</span> <span m='1784980'>end</span> <span
  m='1785820'>of</span> <span m='1786420'>the</span> <span
  m='1786660'>non-zero</span> <span m='1787230'>values</span> <span
  m='1787710'>of</span> <span m='1787830'>x,</span> <span
  m='1788580'>where</span> <span m='1789000'>y</span> <span m='1789410'>of
  n</span> <span m='1789780'>decays.</span> <span m='1791400'>So</span> <span
  m='1791730'>this</span> <span m='1792000'>then</span> <span
  m='1792450'>is</span> <span m='1793350'>an</span> <span
  m='1793470'>illustration</span> <span m='1794520'>of</span> <span
  m='1795300'>the</span> <span m='1795390'>linear</span> <span
  m='1795780'>convolution</span> <span m='1796890'>of</span> <span
  m='1797700'>x</span> <span m='1798000'>of</span> <span m='1798120'>k</span>
  <span m='1798495'>with</span> <span m='1798870'>h of</span> <span
  m='1799080'>k.</span> </p><p><span m='1807760'>Now</span> <span
  m='1808120'>what</span> <span m='1808330'>we'd</span> <span
  m='1808510'>like</span> <span m='1808720'>to</span> <span
  m='1809020'>compare</span> <span m='1809470'>this</span> <span
  m='1809710'>with</span> <span m='1810100'>is</span> <span
  m='1810370'>periodic</span> <span m='1811450'>convolution</span> <span
  m='1812800'>where</span> <span m='1813280'>the</span> <span
  m='1813430'>sum</span> <span m='1813820'>is</span> <span m='1813970'>of</span>
  <span m='1814090'>a</span> <span m='1814150'>similar</span> <span
  m='1814570'>form,</span> <span m='1815110'>but</span> <span
  m='1815290'>the</span> <span m='1815440'>arguments</span> <span
  m='1816130'>are</span> <span m='1816250'>taken</span> <span
  m='1816720'>modulo</span> <span m='1817590'>capital</span> <span
  m='1818050'>M.</span> <span m='1820310'>And</span> <span m='1820820'>in</span>
  <span m='1820970'>this</span> <span m='1821150'>case</span> <span
  m='1821550'>then,</span> <span m='1821810'>the</span> <span
  m='1821900'>shifting</span> <span m='1822380'>is</span> <span
  m='1822500'>a</span> <span m='1822560'>circular</span> <span
  m='1823100'>shifting</span> <span m='1823640'>rather</span> <span
  m='1823940'>than</span> <span m='1824120'>a</span> <span
  m='1824150'>linear</span> <span m='1824510'>shifting.</span> <span
  m='1825470'>On</span> <span m='1825590'>the</span> <span
  m='1825650'>top</span> <span m='1826050'>again,</span> <span
  m='1826310'>we</span> <span m='1826490'>have</span> <span m='1826760'>x</span>
  <span m='1827240'>of</span> <span m='1827420'>k,</span> <span
  m='1828290'>modulo</span> <span m='1828800'>M.</span> <span
  m='1829100'>On</span> <span m='1829190'>the</span> <span
  m='1829280'>bottom,</span> <span m='1829820'>h</span> <span
  m='1830090'>of</span> <span m='1830210'>k,</span> <span
  m='1830480'>modulo</span> <span m='1831020'>m.</span> <span
  m='1831830'>Now</span> <span m='1832100'>h</span> <span
  m='1832400'>minus</span> <span m='1832820'>k,</span> <span
  m='1833060'>modulo</span> <span m='1833630'>m,</span> <span
  m='1833870'>and</span> <span m='1833990'>we</span> <span
  m='1834140'>see</span> <span m='1835040'>that</span> <span
  m='1836030'>as</span> <span m='1836690'>we</span> <span
  m='1836900'>shift,</span> <span m='1838340'>the</span> <span
  m='1838550'>shift</span> <span m='1839090'>is</span> <span
  m='1839300'>circular</span> <span m='1839900'>modulo</span> <span
  m='1840950'>capital</span> <span m='1841460'>M.</span> </p><p><span
  m='1841820'>So</span> <span m='1842570'>there's</span> <span
  m='1842840'>0,</span> <span m='1843560'>h</span> <span m='1843845'>of</span>
  <span m='1844130'>0</span> <span m='1844490'>minus</span> <span
  m='1844850'>k,</span> <span m='1845210'>modulo</span> <span
  m='1845630'>capital</span> <span m='1846140'>M,</span> <span
  m='1847766'>h</span> <span m='1848180'>of</span> <span m='1848270'>1</span>
  <span m='1848540'>minus</span> <span m='1848870'>k,</span> <span
  m='1849290'>modulo</span> <span m='1849980'>capital</span> <span
  m='1850490'>M</span> <span m='1850700'>that</span> <span
  m='1850880'>was</span> <span m='1851180'>shifted</span> <span
  m='1851630'>to</span> <span m='1851750'>the</span> <span
  m='1851870'>right</span> <span m='1852140'>circularly</span> <span
  m='1852800'>by</span> <span m='1853010'>1.</span> <span m='1854810'>And</span>
  <span m='1854830'>now</span> <span m='1855280'>we</span> <span
  m='1855430'>want</span> <span m='1855610'>to</span> <span
  m='1855670'>look</span> <span m='1856000'>at</span> <span
  m='1856540'>the</span> <span m='1856660'>sum</span> <span
  m='1857320'>from</span> <span m='1857530'>0</span> <span m='1858280'>to</span>
  <span m='1858400'>m</span> <span m='1858670'>minus</span> <span
  m='1858940'>1</span> <span m='1859360'>of</span> <span m='1860380'>the</span>
  <span m='1860470'>product</span> <span m='1860980'>of</span> <span
  m='1861100'>those.</span> <span m='1862060'>And</span> <span
  m='1862660'>the</span> <span m='1862780'>thing</span> <span
  m='1863050'>to</span> <span m='1863200'>notice</span> <span
  m='1863860'>is</span> <span m='1864160'>that</span> <span
  m='1865360'>since</span> <span m='1865840'>x</span> <span
  m='1866170'>of</span> <span m='1866290'>k</span> <span m='1866800'>is</span>
  <span m='1867010'>of</span> <span m='1867130'>length</span> <span
  m='1867700'>capital</span> <span m='1868240'>M,</span> <span
  m='1869320'>as</span> <span m='1869530'>we</span> <span
  m='1869860'>implement</span> <span m='1870380'>the</span> <span
  m='1870460'>circular</span> <span m='1870970'>shift</span> <span
  m='1871330'>of</span> <span m='1871690'>h</span> <span m='1872050'>of</span>
  <span m='1872350'>minus</span> <span m='1872720'>k,</span> <span
  m='1874510'>the</span> <span m='1874690'>values</span> <span
  m='1875290'>of</span> <span m='1875410'>h</span> <span m='1875650'>of</span>
  <span m='1875890'>k,</span> <span m='1876220'>or h</span> <span
  m='1876310'>if</span> <span m='1876490'>minus</span> <span
  m='1876880'>k</span> <span m='1877270'>are</span> <span
  m='1877450'>always</span> <span m='1877840'>engaged</span> <span
  m='1878560'>with</span> <span m='1878860'>unity</span> <span
  m='1879310'>values</span> <span m='1879940'>of</span> <span
  m='1880090'>x,</span> <span m='1880930'>and</span> <span
  m='1881080'>consequently,</span> <span m='1882220'>y</span> <span
  m='1882850'>always</span> <span m='1883270'>comes</span> <span
  m='1883570'>out</span> <span m='1883780'>to</span> <span
  m='1883930'>have</span> <span m='1884140'>the</span> <span
  m='1884230'>same</span> <span m='1884560'>value.</span> </p><p><span
  m='1886240'>To</span> <span m='1886360'>see</span> <span
  m='1886510'>the</span> <span m='1886630'>relationship</span> <span
  m='1887440'>between</span> <span m='1888010'>the</span> <span
  m='1888130'>periodic</span> <span m='1888475'>and</span> <span
  m='1888820'>aperiodic</span> <span m='1889720'>convolution,</span> <span
  m='1891240'>namely</span> <span m='1891970'>the</span> <span
  m='1892240'>aliasing</span> <span m='1892900'>relationship,</span> <span
  m='1894280'>we</span> <span m='1894430'>can</span> <span
  m='1894640'>simply</span> <span m='1895540'>look</span> <span
  m='1895930'>at</span> <span m='1896560'>the</span> <span
  m='1898060'>aperiodic</span> <span m='1899260'>convolution,</span> <span
  m='1899720'>or</span> <span m='1900030'>linear</span> <span
  m='1900400'>convolution,</span> <span m='1901750'>take</span> <span
  m='1902350'>the</span> <span m='1902680'>second</span> <span
  m='1903010'>m</span> <span m='1903350'>values,</span> <span
  m='1904000'>added</span> <span m='1904330'>to</span> <span
  m='1904450'>the</span> <span m='1904540'>first</span> <span
  m='1904840'>m</span> <span m='1905110'>values,</span> <span
  m='1906700'>and</span> <span m='1907360'>when</span> <span
  m='1907600'>we</span> <span m='1907720'>carry</span> <span
  m='1908140'>out</span> <span m='1908320'>that</span> <span
  m='1908650'>sum,</span> <span m='1909160'>what</span> <span
  m='1909340'>we</span> <span m='1909490'>get</span> <span m='1909820'>is</span>
  <span m='1910060'>a</span> <span m='1910120'>constant.</span> <span
  m='1911230'>In</span> <span m='1911350'>general,</span> <span
  m='1911740'>the</span> <span m='1911830'>relationship</span> <span
  m='1912610'>is</span> <span m='1913120'>that</span> <span
  m='1914220'>the</span> <span m='1914420'>circular</span> <span
  m='1914860'>convolution</span> <span m='1915790'>is</span> <span
  m='1916180'>y</span> <span m='1916420'>of n</span> <span
  m='1916770'>plus</span> <span m='1917060'>y</span> <span m='1917320'>of
  n</span> <span m='1917500'>plus</span> <span m='1917770'>capital</span> <span
  m='1918130'>M,</span> <span m='1918490'>y</span> <span m='1918850'>of n</span>
  <span m='1919100'>plus</span> <span m='1919360'>2</span> <span
  m='1919580'>capital</span> <span m='1919750'>M,</span> <span
  m='1920200'>et</span> <span m='1920320'>cetera.</span> </p><p><span
  m='1921850'>Next,</span> <span m='1922390'>what</span> <span
  m='1922660'>we</span> <span m='1922840'>would</span> <span
  m='1922960'>like</span> <span m='1923560'>to</span> <span
  m='1924280'>illustrate</span> <span m='1925060'>is</span> <span
  m='1925240'>the</span> <span m='1925360'>fact</span> <span
  m='1925930'>that</span> <span m='1927010'>the</span> <span
  m='1927910'>linear</span> <span m='1928330'>convolution</span> <span
  m='1929320'>can</span> <span m='1929530'>be</span> <span
  m='1929650'>obtained</span> <span m='1930010'>from</span> <span
  m='1930190'>a</span> <span m='1930250'>circular</span> <span
  m='1930700'>convolution</span> <span m='1931690'>if</span> <span
  m='1932020'>we</span> <span m='1932230'>pad</span> <span
  m='1932590'>out</span> <span m='1932770'>with</span> <span
  m='1932920'>zeros.</span> <span m='1933940'>So</span> <span
  m='1934120'>now</span> <span m='1934570'>we're</span> <span
  m='1934750'>going</span> <span m='1934990'>to</span> <span
  m='1935080'>implement</span> <span m='1935650'>the</span> <span
  m='1935740'>circular</span> <span m='1936220'>convolution,</span> <span
  m='1937960'>but</span> <span m='1938620'>notice</span> <span
  m='1939160'>that</span> <span m='1939310'>we've</span> <span
  m='1939550'>padded</span> <span m='1940750'>x</span> <span
  m='1941040'>of</span> <span m='1941220'>k</span> <span m='1941920'>out</span>
  <span m='1942520'>with</span> <span m='1943480'>a</span> <span
  m='1943540'>number</span> <span m='1943930'>of</span> <span
  m='1944020'>zeros.</span> <span m='1945130'>In</span> <span
  m='1945250'>that</span> <span m='1945460'>case,</span> <span
  m='1946030'>as</span> <span m='1946420'>we</span> <span m='1946540'>do</span>
  <span m='1946750'>the</span> <span m='1946870'>circular</span> <span
  m='1947290'>shifting</span> <span m='1947920'>of</span> <span
  m='1948070'>h,</span> <span m='1949240'>the</span> <span
  m='1950230'>values</span> <span m='1951190'>on</span> <span
  m='1951370'>the</span> <span m='1951490'>right</span> <span
  m='1952060'>are</span> <span m='1952420'>multiplied</span> <span
  m='1953110'>only</span> <span m='1953440'>by</span> <span
  m='1953650'>the</span> <span m='1953770'>zero</span> <span
  m='1954280'>values</span> <span m='1954970'>that</span> <span
  m='1955090'>we</span> <span m='1955270'>appended</span> <span
  m='1955720'>x</span> <span m='1955990'>with,</span> <span
  m='1956710'>and</span> <span m='1956860'>so</span> <span
  m='1957100'>this</span> <span m='1957310'>looks</span> <span
  m='1957580'>exactly</span> <span m='1958150'>the</span> <span
  m='1958240'>same</span> <span m='1958690'>as</span> <span
  m='1958900'>if</span> <span m='1959080'>we</span> <span
  m='1959230'>were</span> <span m='1959350'>sliding</span> <span
  m='1960190'>h</span> <span m='1960790'>in</span> <span m='1961540'>from</span>
  <span m='1961780'>the</span> <span m='1961900'>left-hand</span> <span
  m='1962460'>end.</span> <span m='1963230'>And</span> <span
  m='1963700'>so</span> <span m='1964180'>what</span> <span
  m='1964510'>results</span> <span m='1965230'>then</span> <span
  m='1965710'>is</span> <span m='1966610'>the</span> <span
  m='1967630'>linear</span> <span m='1968050'>convolution.</span> <span
  m='1968890'>Although</span> <span m='1969190'>we're</span> <span
  m='1969790'>implementing</span> <span m='1970330'>a</span> <span
  m='1970390'>circular</span> <span m='1970840'>convolution,</span> <span
  m='1972700'>because</span> <span m='1973090'>of</span> <span
  m='1973180'>the</span> <span m='1973300'>fact</span> <span
  m='1973930'>that</span> <span m='1974050'>we've</span> <span
  m='1974290'>augmented</span> <span m='1974860'>with</span> <span
  m='1975010'>zeros,</span> <span m='1976150'>the</span> <span
  m='1976540'>resulting</span> <span m='1977440'>answer</span> <span
  m='1978070'>is</span> <span m='1978640'>exactly</span> <span
  m='1979300'>the</span> <span m='1979420'>same</span> <span
  m='1979900'>as</span> <span m='1980710'>the</span> <span
  m='1981100'>linear</span> <span m='1981490'>convolution</span> <span
  m='1982510'>of</span> <span m='1983170'>x</span> <span m='1983440'>of n</span>
  <span m='1984070'>with</span> <span m='1984220'>h</span> <span m='1984460'>of
  n.</span> </p><p><span m='1990420'>All</span> <span m='1990480'>right,</span>
  <span m='1990630'>well</span> <span m='1990840'>hopefully,</span> <span
  m='1993050'>through</span> <span m='1993390'>the</span> <span
  m='1993510'>film</span> <span m='1995730'>you</span> <span
  m='1995920'>got</span> <span m='1996150'>to</span> <span
  m='1996270'>see</span> <span m='1996600'>the</span> <span
  m='1996780'>dynamics</span> <span m='1997680'>of</span> <span
  m='1998130'>convolution</span> <span m='1999000'>in</span> <span
  m='1999090'>these</span> <span m='1999270'>relationships</span> <span
  m='2000200'>that</span> <span m='2000920'>I've</span> <span
  m='2001100'>been</span> <span m='2002000'>trying</span> <span
  m='2002360'>so</span> <span m='2002600'>hard</span> <span
  m='2002900'>to</span> <span m='2003020'>stress.</span> <span
  m='2004760'>And</span> <span m='2006260'>now</span> <span
  m='2006770'>if</span> <span m='2007040'>we</span> <span
  m='2007190'>return</span> <span m='2007700'>to</span> <span
  m='2008180'>the</span> <span m='2008360'>example</span> <span
  m='2009440'>that</span> <span m='2010100'>we</span> <span
  m='2010280'>were</span> <span m='2010790'>talking</span> <span
  m='2011210'>about</span> <span m='2011540'>before</span> <span
  m='2011930'>the</span> <span m='2012050'>film,</span> <span
  m='2013910'>it</span> <span m='2014030'>should</span> <span
  m='2014270'>be</span> <span m='2014420'>clear</span> <span
  m='2015410'>that</span> <span m='2016100'>through</span> <span
  m='2016340'>this</span> <span m='2016580'>notion</span> <span
  m='2017270'>of</span> <span m='2017870'>padding</span> <span
  m='2018230'>with</span> <span m='2018410'>zeros,</span> <span
  m='2019610'>we</span> <span m='2019730'>can</span> <span
  m='2019910'>implement</span> <span m='2020390'>a</span> <span
  m='2020450'>linear</span> <span m='2020780'>convolution,</span> <span
  m='2021830'>and</span> <span m='2022430'>thereby</span> <span
  m='2023120'>implement</span> <span m='2023810'>a</span> <span
  m='2024080'>discrete</span> <span m='2024530'>time</span> <span
  m='2025850'>linear</span> <span m='2026240'>shift</span> <span
  m='2026570'>invariant</span> <span m='2027080'>system</span> <span
  m='2028280'>using</span> <span m='2028790'>circular</span> <span
  m='2029240'>convolution,</span> <span m='2029900'>or</span> <span
  m='2029990'>equivalently,</span> <span m='2030800'>computing</span> <span
  m='2031085'>DFTs,</span> <span m='2032120'>multiplying</span> <span
  m='2033080'>and</span> <span m='2033230'>computing</span> <span
  m='2034160'>the</span> <span m='2034310'>inverse</span> <span
  m='2034700'>DFT.</span> </p><p><span m='2037650'>Well</span> <span
  m='2038050'>there's</span> <span m='2038370'>only</span> <span
  m='2038820'>one</span> <span m='2039390'>hitch</span> <span
  m='2039690'>to</span> <span m='2039840'>that,</span> <span
  m='2041350'>and</span> <span m='2041500'>that's</span> <span
  m='2041710'>the</span> <span m='2041830'>following,</span> <span
  m='2042530'>suppose</span> <span m='2043150'>that</span> <span
  m='2043720'>what</span> <span m='2043930'>I</span> <span
  m='2044020'>wanted</span> <span m='2044350'>to</span> <span
  m='2044470'>implement</span> <span m='2047320'>was</span> <span
  m='2048040'>a</span> <span m='2048219'>discrete</span> <span
  m='2048639'>time</span> <span m='2049120'>system.</span> <span
  m='2050530'>Let's</span> <span m='2050770'>take</span> <span
  m='2051159'>the</span> <span m='2051280'>impulse</span> <span
  m='2051699'>response</span> <span m='2052389'>as</span> <span
  m='2052600'>this</span> <span m='2052780'>sequence</span> <span
  m='2053440'>x1</span> <span m='2053679'>of</span> <span m='2053980'>n.</span>
  <span m='2055480'>And</span> <span m='2055600'>let's</span> <span
  m='2055810'>say</span> <span m='2056230'>that</span> <span
  m='2056980'>the</span> <span m='2058570'>input</span> <span
  m='2059170'>to</span> <span m='2059260'>the</span> <span
  m='2059380'>filter</span> <span m='2060130'>was</span> <span
  m='2060670'>also</span> <span m='2061210'>a</span> <span
  m='2061270'>sequence</span> <span m='2061780'>of</span> <span
  m='2061900'>length</span> <span m='2062270'>capital</span> <span
  m='2062525'>N,</span> <span m='2063090'>or</span> <span
  m='2063250'>capital</span> <span m='2063585'>M.</span> <span
  m='2064780'>Then,</span> <span m='2065230'>on</span> <span
  m='2065350'>the</span> <span m='2065440'>basis</span> <span
  m='2065860'>of</span> <span m='2065980'>everything</span> <span
  m='2066400'>we've</span> <span m='2066550'>been</span> <span
  m='2066699'>saying</span> <span m='2067060'>in</span> <span
  m='2067150'>this</span> <span m='2067330'>lecture,</span> <span
  m='2068290'>clearly</span> <span m='2068710'>we</span> <span
  m='2068860'>could</span> <span m='2069010'>do</span> <span
  m='2069219'>the</span> <span m='2069340'>convolution</span> <span
  m='2071080'>by</span> <span m='2071560'>padding</span> <span
  m='2072040'>out</span> <span m='2072190'>with</span> <span
  m='2072340'>enough</span> <span m='2072550'>zeros,</span> <span
  m='2073900'>computing</span> <span m='2074409'>the</span> <span
  m='2074469'>discrete</span> <span m='2074960'>Fourier</span> <span
  m='2075250'>transform,</span> <span m='2075880'>multiplying</span> <span
  m='2076750'>and</span> <span m='2076870'>inverse</span> <span
  m='2077260'>transforming.</span> </p><p><span m='2079250'>However,</span>
  <span m='2080170'>in</span> <span m='2080290'>order</span> <span
  m='2080560'>to</span> <span m='2080710'>do</span> <span
  m='2080920'>that,</span> <span m='2081400'>obviously</span> <span
  m='2082750'>for</span> <span m='2082870'>the</span> <span
  m='2083020'>input,</span> <span m='2084820'>before</span> <span
  m='2085179'>we</span> <span m='2085300'>compute</span> <span
  m='2085719'>the</span> <span m='2085810'>discrete</span> <span
  m='2086170'>Fourier</span> <span m='2086500'>transform,</span> <span
  m='2087610'>we</span> <span m='2087730'>have</span> <span
  m='2087969'>to</span> <span m='2088090'>wait</span> <span
  m='2088360'>until</span> <span m='2088630'>the</span> <span
  m='2088750'>entire</span> <span m='2089199'>input</span> <span
  m='2089530'>comes</span> <span m='2089830'>in.</span> <span
  m='2090250'>In</span> <span m='2090670'>other</span> <span
  m='2090820'>words,</span> <span m='2091159'>we</span> <span
  m='2091179'>need</span> <span m='2091330'>a</span> <span
  m='2091420'>buffer</span> <span m='2092469'>that's</span> <span
  m='2092679'>long</span> <span m='2092980'>enough</span> <span
  m='2093820'>to</span> <span m='2093940'>hold</span> <span
  m='2094179'>the</span> <span m='2094300'>entire</span> <span
  m='2094780'>input.</span> <span m='2095929'>Furthermore</span> <span
  m='2096850'>what</span> <span m='2097300'>we</span> <span
  m='2098020'>need</span> <span m='2098620'>to</span> <span
  m='2098770'>do</span> <span m='2099250'>is</span> <span
  m='2099490'>compute</span> <span m='2100510'>a</span> <span
  m='2100740'>Fourier</span> <span m='2101170'>transform,</span> <span
  m='2101920'>discrete</span> <span m='2102250'>Fourier</span> <span
  m='2102640'>transform,</span> <span m='2104020'>that</span> <span
  m='2104350'>is</span> <span m='2105040'>at</span> <span
  m='2105190'>least</span> <span m='2105610'>as</span> <span
  m='2105760'>long</span> <span m='2107320'>as</span> <span
  m='2107470'>the</span> <span m='2107620'>input</span> <span
  m='2108160'>data.</span> <span m='2109340'>In</span> <span
  m='2109440'>fact,</span> <span m='2109820'>as</span> <span
  m='2109900'>long</span> <span m='2110050'>as</span> <span
  m='2110140'>the</span> <span m='2110260'>input</span> <span
  m='2110590'>data,</span> <span m='2111610'>plus</span> <span
  m='2112180'>the</span> <span m='2112300'>length</span> <span
  m='2112780'>of</span> <span m='2113110'>the</span> <span
  m='2113200'>unit</span> <span m='2113470'>sample</span> <span
  m='2113890'>response.</span> </p><p><span m='2115390'>Now</span> <span
  m='2115630'>obviously,</span> <span m='2116530'>if</span> <span
  m='2117220'>we</span> <span m='2117340'>want</span> <span
  m='2117520'>to</span> <span m='2117610'>filter</span> <span
  m='2118630'>some</span> <span m='2120070'>signal</span> <span
  m='2120550'>like,</span> <span m='2120940'>let's</span> <span
  m='2121210'>say,</span> <span m='2121960'>one</span> <span
  m='2122300'>of</span> <span m='2122600'>Beethoven's</span> <span
  m='2122700'>symphonies,</span> <span m='2124510'>clearly</span> <span
  m='2125170'>we're</span> <span m='2125350'>not</span> <span
  m='2125530'>first</span> <span m='2125830'>of</span> <span
  m='2125950'>all,</span> <span m='2126330'>going</span> <span
  m='2126490'>to</span> <span m='2126580'>want</span> <span
  m='2126760'>to</span> <span m='2127210'>buffer</span> <span
  m='2127600'>the</span> <span m='2127720'>entire</span> <span
  m='2128170'>input</span> <span m='2128530'>signal.</span> <span
  m='2130180'>Second</span> <span m='2130540'>of</span> <span
  m='2130660'>all,</span> <span m='2130780'>you</span> <span
  m='2130900'>can</span> <span m='2131050'>imagine</span> <span
  m='2131500'>computationally</span> <span m='2133090'>that</span> <span
  m='2133340'>at,</span> <span m='2133480'>say</span> <span m='2133690'>a</span>
  <span m='2133750'>10</span> <span m='2133990'>kilohertz</span> <span
  m='2134530'>or</span> <span m='2134590'>20</span> <span
  m='2134890'>kilohertz</span> <span m='2135340'>sampling</span> <span
  m='2135850'>rate,</span> <span m='2136540'>we'd</span> <span
  m='2136690'>be</span> <span m='2136810'>talking</span> <span m='2137230'>about
  a</span> <span m='2137710'>discrete</span> <span m='2138130'>Fourier</span>
  <span m='2138490'>transform</span> <span m='2139180'>that's</span> <span
  m='2139900'>astronomical</span> <span m='2141460'>in</span> <span
  m='2141580'>length.</span> </p><p><span m='2142640'>So</span> <span
  m='2143620'>if</span> <span m='2143980'>we</span> <span
  m='2144130'>want</span> <span m='2144670'>to</span> <span
  m='2145060'>implement</span> <span m='2146050'>a</span> <span
  m='2147520'>digital</span> <span m='2147910'>filter,</span> <span
  m='2148870'>or</span> <span m='2149020'>a</span> <span
  m='2149050'>discrete</span> <span m='2149410'>time</span> <span
  m='2149740'>system</span> <span m='2151240'>using</span> <span
  m='2152050'>this</span> <span m='2153550'>kind</span> <span
  m='2153790'>of</span> <span m='2153880'>approach,</span> <span
  m='2155080'>then</span> <span m='2155800'>we</span> <span
  m='2155950'>would</span> <span m='2156130'>like</span> <span
  m='2156460'>to</span> <span m='2156640'>have</span> <span
  m='2157000'>some</span> <span m='2157210'>strategy</span> <span
  m='2158770'>that</span> <span m='2159460'>avoids</span> <span
  m='2159910'>the</span> <span m='2160030'>problem</span> <span
  m='2160600'>of</span> <span m='2160750'>having</span> <span
  m='2161050'>to</span> <span m='2161170'>buffer</span> <span
  m='2161500'>the</span> <span m='2161620'>entire</span> <span
  m='2162070'>input.</span> <span m='2163060'>And</span> <span
  m='2163240'>one</span> <span m='2163450'>way</span> <span
  m='2163600'>of</span> <span m='2163720'>doing</span> <span
  m='2164050'>that</span> <span m='2164380'>is</span> <span
  m='2164620'>by</span> <span m='2164860'>sectioning</span> <span
  m='2165940'>the</span> <span m='2166390'>input</span> <span
  m='2166780'>signal.</span> </p><p><span m='2168970'>So</span> <span
  m='2169180'>that,</span> <span m='2170470'>suppose</span> <span
  m='2171880'>we</span> <span m='2172060'>had</span> <span m='2172450'>as</span>
  <span m='2172660'>an</span> <span m='2172750'>example,</span> <span
  m='2175360'>a</span> <span m='2175450'>unit</span> <span
  m='2175750'>sample</span> <span m='2176200'>response</span> <span
  m='2177220'>which</span> <span m='2177490'>was</span> <span
  m='2177970'>of</span> <span m='2178180'>length</span> <span
  m='2178840'>capital</span> <span m='2179260'>M,</span> <span
  m='2180340'>so</span> <span m='2180520'>it</span> <span
  m='2180610'>runs</span> <span m='2180910'>from</span> <span
  m='2181060'>0</span> <span m='2181480'>to</span> <span
  m='2181630'>capital</span> <span m='2182080'>M</span> <span
  m='2182200'>minus</span> <span m='2182650'>1.</span> <span
  m='2183970'>We</span> <span m='2184090'>have</span> <span
  m='2184270'>an</span> <span m='2184360'>input</span> <span
  m='2184750'>signal</span> <span m='2185530'>that's</span> <span
  m='2185770'>arbitrarily</span> <span m='2186580'>long,</span> <span
  m='2187810'>starts</span> <span m='2188290'>at</span> <span
  m='2188380'>0,</span> <span m='2188760'>let's</span> <span
  m='2188980'>say,</span> <span m='2189400'>and</span> <span
  m='2189550'>runs</span> <span m='2189910'>on</span> <span
  m='2191230'>for</span> <span m='2191680'>an</span> <span
  m='2191830'>indefinite</span> <span m='2192370'>length.</span> <span
  m='2193900'>We</span> <span m='2194050'>can</span> <span
  m='2194200'>imagine</span> <span m='2195220'>sectioning</span> <span
  m='2196270'>the</span> <span m='2196450'>input,</span> <span
  m='2197200'>sectioning</span> <span m='2197950'>x</span> <span m='2198220'>of
  n</span> <span m='2199330'>into</span> <span m='2199870'>sections</span> <span
  m='2200770'>of</span> <span m='2201010'>some</span> <span
  m='2201310'>length,</span> <span m='2201670'>and</span> <span
  m='2201760'>let's</span> <span m='2201940'>call</span> <span
  m='2202210'>the</span> <span m='2202330'>length</span> <span
  m='2202660'>capital</span> <span m='2203230'>L,</span> <span
  m='2204940'>so</span> <span m='2205210'>that</span> <span
  m='2205840'>we</span> <span m='2205990'>have</span> <span m='2206440'>a</span>
  <span m='2206500'>number</span> <span m='2206890'>of</span> <span
  m='2206980'>sections</span> <span m='2207820'>of</span> <span
  m='2208120'>length</span> <span m='2208300'>capital</span> <span
  m='2208600'>L.</span> </p><p><span m='2211120'>Now</span> <span
  m='2211600'>we</span> <span m='2211810'>know,</span> <span
  m='2212200'>and</span> <span m='2212290'>you</span> <span
  m='2212380'>should</span> <span m='2212590'>recall</span> <span
  m='2213040'>from</span> <span m='2213220'>when</span> <span
  m='2213400'>we</span> <span m='2213520'>discussed</span> <span
  m='2214000'>convolution,</span> <span m='2215560'>that</span> <span
  m='2216130'>the</span> <span m='2216220'>convolution</span> <span
  m='2216880'>of</span> <span m='2216970'>a</span> <span m='2217030'>sum,</span>
  <span m='2218410'>the</span> <span m='2218500'>convolution</span> <span
  m='2218800'>of</span> <span m='2219100'>h</span> <span m='2219190'>of</span>
  <span m='2219400'>n</span> <span m='2219730'>with</span> <span
  m='2219860'>the</span> <span m='2219910'>sum</span> <span
  m='2220210'>of</span> <span m='2220360'>things</span> <span
  m='2221380'>is</span> <span m='2221500'>equal</span> <span
  m='2221770'>to</span> <span m='2221890'>the</span> <span
  m='2221980'>sum</span> <span m='2222250'>of</span> <span
  m='2222340'>the</span> <span m='2222430'>convolutions.</span> <span
  m='2223930'>So</span> <span m='2224170'>that</span> <span
  m='2224650'>if</span> <span m='2224860'>we</span> <span
  m='2225100'>generated</span> <span m='2226150'>a</span> <span
  m='2226210'>set</span> <span m='2226510'>of</span> <span
  m='2226600'>sequences,</span> <span m='2228280'>each</span> <span
  m='2228550'>one</span> <span m='2228850'>corresponding</span> <span
  m='2229690'>to</span> <span m='2229840'>a</span> <span
  m='2229900'>different</span> <span m='2230230'>section</span> <span
  m='2231520'>of</span> <span m='2231700'>the</span> <span
  m='2231850'>input,</span> <span m='2233680'>we</span> <span
  m='2233830'>could</span> <span m='2234040'>convolve</span> <span
  m='2234430'>each</span> <span m='2234820'>of</span> <span
  m='2235090'>those</span> <span m='2235180'>with</span> <span
  m='2235510'>h</span> <span m='2235660'>of</span> <span m='2235900'>n,</span>
  <span m='2237460'>and</span> <span m='2237640'>then</span> <span
  m='2238180'>add</span> <span m='2239050'>the</span> <span
  m='2239320'>resulting</span> <span m='2239860'>convolutions</span> <span
  m='2240700'>together</span> <span m='2241780'>to</span> <span
  m='2241900'>form</span> <span m='2242530'>the</span> <span
  m='2242710'>output</span> <span m='2243130'>y</span> <span
  m='2243400'>of</span> <span m='2243470'>n.</span> </p><p><span
  m='2244390'>So</span> <span m='2244960'>if</span> <span m='2245140'>we</span>
  <span m='2245230'>section</span> <span m='2245740'>the</span> <span
  m='2245890'>input,</span> <span m='2246670'>x</span> <span
  m='2246940'>of</span> <span m='2247060'>n,</span> <span m='2248600'>we</span>
  <span m='2248720'>can</span> <span m='2248900'>then</span> <span
  m='2249110'>form</span> <span m='2249650'>a</span> <span
  m='2249740'>set</span> <span m='2250010'>of</span> <span
  m='2250070'>sequences,</span> <span m='2251000'>each</span> <span
  m='2251240'>one</span> <span m='2251450'>of</span> <span
  m='2251540'>which</span> <span m='2251750'>corresponds</span> <span
  m='2252410'>to</span> <span m='2252560'>one</span> <span m='2252740'>of</span>
  <span m='2252830'>these</span> <span m='2253010'>sections</span> <span
  m='2254210'>and</span> <span m='2254570'>is</span> <span m='2254820'>0</span>
  <span m='2256010'>outside</span> <span m='2256490'>the</span> <span
  m='2256640'>interval</span> <span m='2257750'>that</span> <span
  m='2258170'>I've</span> <span m='2258350'>indicated</span> <span
  m='2259130'>for</span> <span m='2259310'>each</span> <span
  m='2259490'>one</span> <span m='2259640'>of</span> <span
  m='2259730'>these</span> <span m='2259910'>colored</span> <span
  m='2260270'>sections.</span> <span m='2261650'>And</span> <span
  m='2261770'>we</span> <span m='2261920'>would</span> <span
  m='2262070'>end</span> <span m='2262310'>up</span> <span
  m='2262790'>with</span> <span m='2263240'>a</span> <span
  m='2263300'>set</span> <span m='2264080'>of</span> <span
  m='2265580'>sub</span> <span m='2265940'>sequences</span> <span
  m='2267680'>which</span> <span m='2268400'>would,</span> <span
  m='2269250'>for</span> <span m='2269360'>example,</span> <span
  m='2269840'>look</span> <span m='2270050'>like</span> <span
  m='2270320'>this,</span> <span m='2270720'>x</span> <span m='2270970'>0</span>
  <span m='2271400'>of</span> <span m='2271520'>n,</span> <span
  m='2272300'>corresponding</span> <span m='2273080'>to</span> <span
  m='2273170'>the</span> <span m='2273260'>first</span> <span
  m='2273590'>l</span> <span m='2273860'>points,</span> <span
  m='2275090'>and</span> <span m='2275240'>0</span> <span
  m='2275870'>afterwards.</span> <span m='2277960'>X1</span> <span
  m='2278410'>of</span> <span m='2278540'>n</span> <span
  m='2278870'>corresponding</span> <span m='2279590'>to</span> <span
  m='2279710'>the</span> <span m='2279800'>second</span> <span
  m='2280580'>l</span> <span m='2280820'>points,</span> <span
  m='2281990'>and</span> <span m='2282110'>0</span> <span
  m='2282530'>afterwards</span> <span m='2283290'>and</span> <span
  m='2283460'>before.</span> <span m='2284620'>X</span> <span
  m='2284900'>two</span> <span m='2285080'>of</span> <span m='2285250'>n,</span>
  <span m='2285650'>the</span> <span m='2285740'>next</span> <span
  m='2285980'>set</span> <span m='2286400'>of</span> <span m='2286550'>l</span>
  <span m='2286720'>points.</span> <span m='2287270'>X3</span> <span
  m='2287720'>of</span> <span m='2287810'>n,</span> <span m='2287960'>the</span>
  <span m='2288050'>next</span> <span m='2288260'>set</span> <span
  m='2288470'>of</span> <span m='2288590'>l</span> <span
  m='2288720'>points.</span> <span m='2289220'>And</span> <span
  m='2289310'>we</span> <span m='2289400'>could</span> <span
  m='2289540'>continue</span> <span m='2290000'>on</span> <span
  m='2290180'>like</span> <span m='2290420'>that.</span> </p><p><span
  m='2292250'>Implement</span> <span m='2292820'>the</span> <span
  m='2292910'>convolution</span> <span m='2294590'>of</span> <span
  m='2294740'>each</span> <span m='2294980'>one</span> <span
  m='2295460'>of</span> <span m='2295640'>these</span> <span
  m='2295850'>sections</span> <span m='2297200'>with</span> <span
  m='2297380'>the</span> <span m='2297470'>unit</span> <span
  m='2297740'>sample</span> <span m='2298160'>response.</span> <span
  m='2300180'>And</span> <span m='2300330'>then</span> <span
  m='2301140'>add</span> <span m='2301740'>the</span> <span
  m='2301830'>resulting</span> <span m='2302340'>outputs</span> <span
  m='2302790'>together.</span> <span m='2303780'>In</span> <span
  m='2303870'>that</span> <span m='2304110'>case,</span> <span
  m='2304920'>the</span> <span m='2305010'>length</span> <span
  m='2305670'>transform</span> <span m='2306390'>that</span> <span
  m='2306510'>we</span> <span m='2306690'>would</span> <span
  m='2306840'>need</span> <span m='2307320'>to</span> <span
  m='2307440'>compute</span> <span m='2308660'>the</span> <span
  m='2309030'>linear</span> <span m='2309390'>convolution</span> <span
  m='2310680'>of</span> <span m='2310830'>this</span> <span m='2311070'>l</span>
  <span m='2311320'>point</span> <span m='2311690'>section</span> <span
  m='2312810'>with</span> <span m='2313170'>the</span> <span
  m='2313350'>input</span> <span m='2313890'>h</span> <span
  m='2314300'>of</span> <span m='2314725'>n,</span> <span
  m='2315900'>would</span> <span m='2316080'>be</span> <span
  m='2316530'>where</span> <span m='2316770'>h</span> <span m='2316950'>of
  n</span> <span m='2317190'>was</span> <span m='2317340'>of</span> <span
  m='2317430'>length</span> <span m='2317730'>m,</span> <span
  m='2318450'>would</span> <span m='2318630'>be</span> <span
  m='2318960'>a</span> <span m='2319050'>DFT</span> <span m='2319860'>of</span>
  <span m='2319980'>length</span> <span m='2320310'>l</span> <span
  m='2320580'>plus</span> <span m='2320870'>m</span> <span
  m='2321360'>minus</span> <span m='2321720'>1.</span> <span
  m='2321990'>L</span> <span m='2322230'>plus</span> <span m='2322500'>m</span>
  <span m='2322650'>certainly</span> <span m='2323040'>works,</span> <span
  m='2323350'>but</span> <span m='2323490'>it</span> <span
  m='2323550'>turns</span> <span m='2323850'>out</span> <span
  m='2323970'>l</span> <span m='2324240'>plus</span> <span m='2324510'>m</span>
  <span m='2324660'>minus</span> <span m='2325020'>1</span> <span
  m='2325440'>is</span> <span m='2325590'>enough.</span> </p><p><span
  m='2327790'>Now</span> <span m='2329190'>obviously</span> <span
  m='2329790'>we</span> <span m='2329910'>have</span> <span
  m='2330090'>to</span> <span m='2330210'>make</span> <span
  m='2330390'>sure</span> <span m='2330630'>that</span> <span
  m='2330750'>we</span> <span m='2330900'>line</span> <span
  m='2331260'>up.</span> <span m='2331560'>If</span> <span m='2331920'>we</span>
  <span m='2332070'>have</span> <span m='2332250'>the</span> <span
  m='2332370'>input</span> <span m='2332700'>sections</span> <span
  m='2333450'>delayed</span> <span m='2334080'>by</span> <span
  m='2334260'>a</span> <span m='2334350'>certain</span> <span
  m='2334710'>amount,</span> <span m='2335100'>we</span> <span
  m='2335280'>have</span> <span m='2335430'>to</span> <span
  m='2335550'>make</span> <span m='2335700'>sure</span> <span
  m='2335910'>that</span> <span m='2336030'>we</span> <span
  m='2336150'>line</span> <span m='2336450'>up</span> <span
  m='2336990'>the</span> <span m='2337170'>output</span> <span
  m='2337560'>sections.</span> <span m='2339060'>And</span> <span
  m='2340020'>what</span> <span m='2340530'>we</span> <span
  m='2341040'>end</span> <span m='2341340'>up</span> <span
  m='2341550'>with</span> <span m='2342150'>then</span> <span
  m='2344780'>is</span> <span m='2345590'>a</span> <span m='2346280'>set</span>
  <span m='2347270'>of</span> <span m='2348050'>output</span> <span
  m='2348770'>sub</span> <span m='2349160'>sequences</span> <span
  m='2351170'>which</span> <span m='2351380'>correspond</span> <span
  m='2352220'>to</span> <span m='2352340'>the</span> <span
  m='2352460'>convolution</span> <span m='2354050'>of</span> <span
  m='2354800'>each</span> <span m='2355040'>one</span> <span
  m='2355190'>of</span> <span m='2355280'>the</span> <span
  m='2355400'>input</span> <span m='2355760'>sections</span> <span
  m='2356810'>with</span> <span m='2357230'>h of</span> <span
  m='2357510'>n.</span> </p><p><span m='2359240'>Now</span> <span
  m='2360410'>we</span> <span m='2360530'>started</span> <span
  m='2360950'>out</span> <span m='2361430'>with</span> <span
  m='2361700'>sections</span> <span m='2362570'>of</span> <span
  m='2362720'>length</span> <span m='2363070'>L.</span> <span
  m='2364520'>We</span> <span m='2364670'>convolved</span> <span
  m='2365240'>those</span> <span m='2366020'>with</span> <span
  m='2367780'>a</span> <span m='2367930'>unit</span> <span
  m='2368260'>sample</span> <span m='2368680'>response</span> <span
  m='2369580'>of</span> <span m='2369730'>length</span> <span
  m='2370090'>m.</span> <span m='2371860'>The</span> <span
  m='2372250'>resulting</span> <span m='2372910'>length</span> <span
  m='2373450'>of</span> <span m='2373600'>the</span> <span
  m='2373690'>convolution</span> <span m='2374980'>will</span> <span
  m='2375190'>be</span> <span m='2376030'>L</span> <span m='2376330'>plus</span>
  <span m='2376690'>m</span> <span m='2376930'>minus 1.</span> <span
  m='2377290'>We've</span> <span m='2377740'>seen</span> <span
  m='2378040'>that</span> <span m='2378280'>in</span> <span m='2378370'>a</span>
  <span m='2378430'>variety</span> <span m='2378970'>of</span> <span
  m='2379060'>ways.</span> <span m='2381010'>And</span> <span
  m='2381220'>consequently,</span> <span m='2382690'>when</span> <span
  m='2383380'>we</span> <span m='2383620'>consider</span> <span
  m='2384160'>adding</span> <span m='2384610'>up</span> <span
  m='2385450'>the</span> <span m='2385630'>outputs</span> <span
  m='2386590'>from</span> <span m='2386800'>the</span> <span
  m='2386920'>convolution</span> <span m='2388450'>with</span> <span
  m='2388720'>each</span> <span m='2388990'>one</span> <span
  m='2389140'>of</span> <span m='2389230'>the</span> <span
  m='2389320'>subsections,</span> <span m='2391960'>if</span> <span
  m='2392530'>this</span> <span m='2392800'>is</span> <span
  m='2392890'>the</span> <span m='2393010'>point</span> <span
  m='2393280'>that</span> <span m='2393400'>corresponds</span> <span
  m='2394300'>to</span> <span m='2394450'>l,</span> <span
  m='2394960'>this</span> <span m='2395200'>is</span> <span
  m='2395455'>just</span> <span m='2395710'>exactly</span> <span
  m='2396040'>the</span> <span m='2396520'>right</span> <span
  m='2396640'>delay,</span> <span m='2398800'>we</span> <span
  m='2398920'>notice</span> <span m='2399280'>that</span> <span
  m='2399400'>there's</span> <span m='2399610'>a</span> <span
  m='2399700'>tail</span> <span m='2400680'>out</span> <span
  m='2400840'>of</span> <span m='2400930'>the</span> <span
  m='2401020'>convolution</span> <span m='2401740'>in</span> <span
  m='2401830'>this</span> <span m='2402010'>section</span> <span
  m='2403180'>that</span> <span m='2403360'>overlaps</span> <span
  m='2404320'>into</span> <span m='2405520'>the</span> <span
  m='2405820'>first</span> <span m='2406330'>m</span> <span
  m='2406830'>minus</span> <span m='2407330'>1,</span> <span
  m='2407830'>or</span> <span m='2408020'>N points</span> <span
  m='2409230'>of</span> <span m='2409830'>it's</span> <span m='2410210'>m</span>
  <span m='2410540'>minus 1</span> <span m='2410890'>points,</span> <span
  m='2411270'>actually,</span> <span m='2412450'>of</span> <span
  m='2413140'>this</span> <span m='2413360'>section.</span> </p><p><span
  m='2414970'>Likewise,</span> <span m='2415840'>there</span> <span
  m='2416140'>are</span> <span m='2416470'>m</span> <span
  m='2416800'>minus</span> <span m='2416970'>1</span> <span
  m='2417400'>points</span> <span m='2417790'>at</span> <span
  m='2418180'>the</span> <span m='2418300'>tail</span> <span
  m='2418600'>of</span> <span m='2418690'>this</span> <span
  m='2418960'>one</span> <span m='2419770'>that</span> <span
  m='2419890'>overlap</span> <span m='2420490'>into</span> <span
  m='2420730'>the</span> <span m='2420850'>first</span> <span
  m='2421210'>m</span> <span m='2421430'>points</span> <span
  m='2421960'>here.</span> <span m='2423100'>So</span> <span
  m='2423370'>that</span> <span m='2424030'>when</span> <span
  m='2424690'>we</span> <span m='2425320'>add</span> <span m='2425710'>up</span>
  <span m='2426280'>the</span> <span m='2426460'>output</span> <span
  m='2427010'>sub sequences,</span> <span m='2428350'>what</span> <span
  m='2428560'>we</span> <span m='2428740'>have</span> <span
  m='2429490'>is</span> <span m='2429970'>an</span> <span
  m='2430090'>overlap</span> <span m='2432040'>between</span> <span
  m='2432460'>the</span> <span m='2432550'>tail</span> <span
  m='2432910'>of</span> <span m='2433000'>this</span> <span
  m='2433150'>section</span> <span m='2433780'>and</span> <span
  m='2433900'>the</span> <span m='2433990'>beginning</span> <span
  m='2434380'>of</span> <span m='2434470'>this</span> <span
  m='2434710'>one,</span> <span m='2434990'>since</span> <span
  m='2435220'>this</span> <span m='2435370'>starts</span> <span
  m='2435760'>at</span> <span m='2435900'>l</span> <span m='2436660'>and</span>
  <span m='2436750'>this</span> <span m='2436960'>runs</span> <span
  m='2437260'>longer</span> <span m='2437650'>than</span> <span
  m='2437780'>l.</span> </p><p><span m='2439210'>Similarly,</span> <span
  m='2439960'>an</span> <span m='2440080'>overlap</span> <span
  m='2441250'>from</span> <span m='2441400'>the</span> <span
  m='2441490'>tail</span> <span m='2441790'>of</span> <span
  m='2441910'>this</span> <span m='2442240'>into</span> <span
  m='2442480'>the</span> <span m='2442570'>beginning</span> <span
  m='2443110'>of</span> <span m='2443260'>this</span> <span
  m='2443500'>one.</span> <span m='2444070'>And</span> <span
  m='2444190'>that</span> <span m='2444340'>continues</span> <span
  m='2444940'>on.</span> <span m='2445990'>Because</span> <span
  m='2446380'>of</span> <span m='2446470'>that,</span> <span
  m='2446950'>this</span> <span m='2447160'>technique</span> <span
  m='2447910'>for</span> <span m='2448090'>suctioning</span> <span
  m='2448880'>and</span> <span m='2448990'>then</span> <span
  m='2449170'>adding</span> <span m='2449470'>the</span> <span
  m='2449530'>results</span> <span m='2449920'>together</span> <span
  m='2451030'>is</span> <span m='2451180'>often</span> <span
  m='2451510'>referred</span> <span m='2451900'>to</span> <span
  m='2452290'>as</span> <span m='2452620'>the</span> <span
  m='2452800'>overlap</span> <span m='2453490'>add</span> <span
  m='2453790'>method</span> <span m='2455200'>because</span> <span
  m='2456130'>we</span> <span m='2456310'>overlap</span> <span
  m='2457630'>the</span> <span m='2457750'>outputs</span> <span
  m='2458500'>and</span> <span m='2458650'>then</span> <span
  m='2458860'>add</span> <span m='2459130'>these</span> <span
  m='2459370'>together.</span> <span m='2459850'>These</span> <span
  m='2460600'>pieces</span> <span m='2461110'>will</span> <span
  m='2461320'>add.</span> <span m='2461980'>These</span> <span
  m='2462190'>blue</span> <span m='2462850'>pieces</span> <span
  m='2463420'>will</span> <span m='2463630'>add,</span> <span
  m='2464470'>et</span> <span m='2464690'>cetera,</span> <span
  m='2465070'>down</span> <span m='2465310'>the</span> <span
  m='2465400'>line.</span> </p><p><span m='2467330'>There's</span> <span
  m='2467410'>also</span> <span m='2467740'>another</span> <span
  m='2468040'>method</span> <span m='2468700'>for</span> <span
  m='2469870'>sectioning</span> <span m='2470920'>using</span> <span
  m='2471280'>circular</span> <span m='2471730'>convolution</span> <span
  m='2472870'>and</span> <span m='2473050'>fitting</span> <span
  m='2473410'>the</span> <span m='2473530'>outputs</span> <span
  m='2473980'>together,</span> <span m='2475130'>which</span> <span
  m='2475420'>is</span> <span m='2475600'>a</span> <span
  m='2475660'>method</span> <span m='2476140'>that</span> <span
  m='2476560'>is</span> <span m='2477520'>referred</span> <span
  m='2477970'>to</span> <span m='2478420'>as</span> <span m='2479170'>the</span>
  <span m='2479290'>overlap</span> <span m='2479770'>save</span> <span
  m='2480130'>method.</span> <span m='2481090'>And</span> <span
  m='2481540'>that</span> <span m='2481810'>method</span> <span
  m='2482380'>is</span> <span m='2482950'>discussed</span> <span
  m='2483580'>in</span> <span m='2483700'>some</span> <span
  m='2483910'>detail</span> <span m='2484720'>in</span> <span
  m='2485800'>the</span> <span m='2485930'>text,</span> <span
  m='2486910'>and</span> <span m='2487090'>corresponds</span> <span
  m='2487750'>basically,</span> <span m='2488620'>to</span> <span
  m='2488920'>implementing</span> <span m='2489490'>a</span> <span
  m='2489550'>circular</span> <span m='2489970'>convolution</span> <span
  m='2490930'>of</span> <span m='2491050'>the</span> <span
  m='2491140'>sections</span> <span m='2492190'>rather</span> <span
  m='2492490'>than</span> <span m='2492640'>a</span> <span
  m='2492700'>linear</span> <span m='2493060'>convolution</span> <span
  m='2493960'>as</span> <span m='2494140'>we</span> <span m='2494230'>did</span>
  <span m='2494440'>here.</span> <span m='2495560'>The</span> <span
  m='2495660'>linear</span> <span m='2495820'>convolution,</span> <span
  m='2496580'>we</span> <span m='2496680'>could</span> <span
  m='2496720'>get</span> <span m='2496900'>from</span> <span
  m='2497080'>a</span> <span m='2497110'>circular</span> <span
  m='2497530'>convolution</span> <span m='2498130'>by</span> <span
  m='2498280'>padding</span> <span m='2498670'>with</span> <span
  m='2498790'>zeros.</span> <span m='2499930'>Alternatively,</span> <span
  m='2500930'>we</span> <span m='2501100'>can</span> <span
  m='2501250'>take</span> <span m='2501520'>the</span> <span
  m='2501640'>circular</span> <span m='2502060'>convolution</span> <span
  m='2503500'>and</span> <span m='2503650'>discard</span> <span
  m='2504250'>the</span> <span m='2504340'>points</span> <span
  m='2504790'>that</span> <span m='2504910'>don't</span> <span
  m='2505210'>correspond</span> <span m='2506050'>to</span> <span
  m='2506230'>a</span> <span m='2506260'>linear</span> <span
  m='2506620'>convolution.</span> </p><p><span m='2508120'>Well,</span> <span
  m='2508480'>there</span> <span m='2508840'>are</span> <span
  m='2509080'>a</span> <span m='2509110'>variety</span> <span
  m='2509650'>of</span> <span m='2509770'>techniques</span> <span
  m='2510280'>of</span> <span m='2510400'>this</span> <span
  m='2510610'>type.</span> <span m='2512120'>The</span> <span
  m='2512260'>important</span> <span m='2512800'>point</span> <span
  m='2513130'>though,</span> <span m='2513610'>is</span> <span
  m='2513850'>that</span> <span m='2514690'>circular</span> <span
  m='2515470'>convolution</span> <span m='2516940'>can,</span> <span
  m='2517280'>in</span> <span m='2517300'>fact,</span> <span
  m='2518120'>be</span> <span m='2518170'>used</span> <span
  m='2518860'>to</span> <span m='2519250'>implement</span> <span
  m='2520120'>linear</span> <span m='2520480'>convolution.</span> <span
  m='2522010'>It</span> <span m='2522130'>can</span> <span m='2522400'>be</span>
  <span m='2522550'>used</span> <span m='2523300'>to</span> <span
  m='2524230'>implement</span> <span m='2524770'>digital</span> <span
  m='2525160'>filters</span> <span m='2526440'>or</span> <span
  m='2526630'>discrete</span> <span m='2527020'>time</span> <span
  m='2527320'>linear</span> <span m='2527650'>systems.</span> <span
  m='2528790'>And</span> <span m='2528910'>in</span> <span
  m='2529030'>fact,</span> <span m='2529790'>although</span> <span
  m='2530680'>this--</span> <span m='2531400'>there's</span> <span
  m='2531700'>nothing</span> <span m='2532090'>that</span> <span
  m='2532210'>we've</span> <span m='2532360'>said</span> <span
  m='2532570'>that</span> <span m='2532690'>clearly</span> <span
  m='2533560'>makes</span> <span m='2533830'>this</span> <span
  m='2534010'>obvious,</span> <span m='2535090'>in</span> <span
  m='2535210'>fact,</span> <span m='2535970'>there</span> <span
  m='2536100'>are</span> <span m='2536230'>very</span> <span
  m='2536560'>efficient</span> <span m='2536950'>ways</span> <span
  m='2537670'>of</span> <span m='2538420'>computing</span> <span
  m='2538940'>the</span> <span m='2539030'>discrete</span> <span
  m='2539440'>Fourier</span> <span m='2539860'>transform,</span> <span
  m='2541520'>which</span> <span m='2542050'>in</span> <span
  m='2542140'>fact</span> <span m='2542440'>make</span> <span
  m='2542710'>this</span> <span m='2542890'>notion</span> <span
  m='2543430'>of</span> <span m='2543550'>computing</span> <span
  m='2544060'>the</span> <span m='2544250'>transform,</span> <span
  m='2544750'>multiplying</span> <span m='2545440'>and</span> <span
  m='2545530'>inverse</span> <span m='2545950'>transforming,</span> <span
  m='2548950'>an</span> <span m='2549090'>efficient</span> <span
  m='2549550'>method</span> <span m='2550360'>for</span> <span
  m='2550720'>implementing</span> <span m='2551350'>a</span> <span
  m='2551410'>digital</span> <span m='2551770'>filter.</span> </p><p><span
  m='2554260'>All</span> <span m='2554350'>right,</span> <span
  m='2554530'>well</span> <span m='2555010'>this</span> <span
  m='2555460'>concludes</span> <span m='2556180'>our</span> <span
  m='2556750'>discussion</span> <span m='2557500'>of</span> <span
  m='2557650'>the</span> <span m='2557770'>discrete</span> <span
  m='2558130'>Fourier</span> <span m='2558550'>transform.</span> <span
  m='2560350'>Toward</span> <span m='2560650'>the</span> <span
  m='2560770'>end</span> <span m='2560950'>of</span> <span
  m='2561040'>this</span> <span m='2561160'>set</span> <span
  m='2561400'>of</span> <span m='2561520'>lectures,</span> <span
  m='2562660'>we'll</span> <span m='2563290'>return</span> <span
  m='2563710'>actually,</span> <span m='2564370'>to</span> <span
  m='2564700'>the</span> <span m='2564820'>discrete</span> <span
  m='2565180'>Fourier</span> <span m='2565540'>transform</span> <span
  m='2566200'>again,</span> <span m='2567250'>where</span> <span
  m='2568000'>at</span> <span m='2568150'>that</span> <span
  m='2568390'>time,</span> <span m='2569020'>what</span> <span
  m='2569210'>we'll</span> <span m='2569330'>want</span> <span
  m='2569530'>to</span> <span m='2569590'>talk</span> <span
  m='2569950'>about</span> <span m='2570850'>is</span> <span
  m='2571030'>specifically</span> <span m='2571870'>the</span> <span
  m='2572080'>computation</span> <span m='2573130'>of</span> <span
  m='2573280'>the</span> <span m='2573370'>discrete</span> <span
  m='2573760'>Fourier</span> <span m='2574210'>transform,</span> <span
  m='2575630'>which</span> <span m='2575740'>leads</span> <span
  m='2576130'>to</span> <span m='2576430'>notions</span> <span
  m='2576880'>such</span> <span m='2577150'>as</span> <span
  m='2577300'>the</span> <span m='2577390'>fast</span> <span
  m='2577720'>Fourier</span> <span m='2578110'>transform</span> <span
  m='2578740'>algorithm.</span> <span m='2580060'>It's</span> <span
  m='2580330'>that</span> <span m='2580480'>computational</span> <span
  m='2581350'>efficiency</span> <span m='2582280'>that</span> <span
  m='2582430'>makes</span> <span m='2582670'>some</span> <span
  m='2582970'>of</span> <span m='2583060'>these</span> <span
  m='2583420'>ideas</span> <span m='2583990'>that</span> <span
  m='2584110'>we've</span> <span m='2584290'>talked</span> <span
  m='2584620'>about</span> <span m='2585010'>in</span> <span
  m='2585100'>the</span> <span m='2585160'>last</span> <span
  m='2585460'>few</span> <span m='2585670'>lectures</span> <span
  m='2586720'>so</span> <span m='2587110'>important</span> <span
  m='2587740'>in</span> <span m='2587860'>terms</span> <span
  m='2588250'>of</span> <span m='2588370'>implementing</span> <span
  m='2588880'>digital</span> <span m='2589210'>filters.</span> </p><p><span
  m='2590290'>Thank</span> <span m='2590530'>you.</span> </p><p><span
  m='2592930'>[MUSIC PLAYING]</span> </p>
embedded_media:
  - uid: b65341ff1254d6ceec7b122ed2c32295
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: MITRES_6_008S11_lec10.pdf
    title: MITRES_6_008S11_lec10.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-10-circular-convolution/MITRES_6_008S11_lec10.pdf
  - uid: 7ba3b3910c6e939d1d9065571164daf6
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: _KbfL3lVgag
  - uid: a79b72c1ff690c0c5ac05a71d5e10c63
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-10-circular-convolution/id481803782?i=108362004
  - uid: 8c00bf600d4644c0312ba52c3cf5ae5e
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec10_300k.mp4'
  - uid: 8a4b6342aa47455715eb6decf03d840e
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/_KbfL3lVgag/default.jpg'
  - uid: 8bb8a7e12d7a2d556c46b1df798478d8
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: _KbfL3lVgag
  - uid: add63c1c3ccb77b4bac4c5fb63aed662
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: KbfL3lVgag.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-10-circular-convolution/KbfL3lVgag.srt
  - uid: 74da8b6376d86b814939ec8ac479ab45
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: KbfL3lVgag.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-10-circular-convolution/KbfL3lVgag.pdf
  - uid: f6b5aaf296a9d82fc35b5bc67bcb4fa6
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: e622338e67b0d8d6335dc9fb457b66f7
    parent_uid: beb398bc1fe767e77ddd11c3f1e945a1
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
