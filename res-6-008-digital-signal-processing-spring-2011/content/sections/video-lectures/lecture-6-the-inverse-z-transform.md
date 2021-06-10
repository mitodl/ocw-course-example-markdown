---
order_index: null
title: 'Lecture 6: The Inverse z-Transform'
template_type: Tabbed
uid: fe999adf052e1c0f941148cf68772257
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-6-the-inverse-z-transform
short_url: lecture-6-the-inverse-z-transform
inline_embed_id: '98510029lecture6:theinversez-transform91196722'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Methods of implementing the inverse
  z-transforms: Inspection method, power series, partial fraction expansion, and
  contour integration.</p> <p><strong>Instructor:</strong> Prof. Alan V.
  Oppenheim</p>
related_resources_text: >-
  <p>The Inverse z-Transform (<a
  href="./resolveuid/c3f2bf603f1237d558cce514fd28a21d">PDF</a>)</p>
transcript: >-
  <p><span m='90'>The</span> <span m='180'>following</span> <span
  m='630'>content</span> <span m='1200'>is</span> <span m='1320'>provided</span>
  <span m='1770'>under</span> <span m='2009'>a</span> <span
  m='2070'>Creative</span> <span m='2490'>Commons</span> <span
  m='2910'>license.</span> <span m='4030'>Your</span> <span
  m='4200'>support</span> <span m='4710'>will</span> <span m='4860'>help</span>
  <span m='5100'>MIT</span> <span m='5550'>OpenCourseWare</span> <span
  m='6330'>continue</span> <span m='6850'>to</span> <span m='6960'>offer</span>
  <span m='7380'>high</span> <span m='7590'>quality</span> <span
  m='8100'>educational</span> <span m='8730'>resources</span> <span
  m='9330'>for</span> <span m='9510'>free.</span> <span m='10720'>To</span>
  <span m='10740'>make</span> <span m='10920'>a</span> <span
  m='10980'>donation</span> <span m='11730'>or</span> <span
  m='11910'>view</span> <span m='12390'>additional</span> <span
  m='12810'>materials</span> <span m='13320'>from</span> <span
  m='13500'>hundreds</span> <span m='13920'>of</span> <span m='14040'>MIT</span>
  <span m='14460'>courses,</span> <span m='15550'>visit</span> <span
  m='15780'>MIT</span> <span m='16200'>OpenCourseWare</span> <span
  m='17280'>at</span> <span m='17430'>ocw.mit.edu.</span> </p><p><span
  m='52530'>ALAN OPPENHEIM:</span> <span m='52695'>Well,</span> <span
  m='52860'>in</span> <span m='52980'>the</span> <span m='53070'>last</span>
  <span m='53400'>lecture</span> <span m='54240'>we</span> <span
  m='54780'>introduced</span> <span m='55590'>the</span> <span
  m='55920'>z</span> <span m='56160'>transform.</span> <span m='58130'>In</span>
  <span m='58250'>this</span> <span m='58460'>lecture,</span> <span
  m='59370'>I'd</span> <span m='59450'>like</span> <span m='59660'>to</span>
  <span m='59780'>go</span> <span m='59930'>backwards.</span> <span
  m='60860'>That</span> <span m='61070'>is,</span> <span m='61580'>I'd</span>
  <span m='61790'>like</span> <span m='62240'>to</span> <span
  m='62600'>introduce</span> <span m='63440'>the</span> <span
  m='63590'>inverse</span> <span m='63890'>z</span> <span
  m='64190'>transform</span> <span m='65630'>and</span> <span
  m='66320'>demonstrate</span> <span m='67460'>some</span> <span
  m='67760'>of</span> <span m='67850'>its</span> <span
  m='68000'>properties</span> <span m='68870'>with</span> <span
  m='69080'>a</span> <span m='69140'>few</span> <span m='69380'>examples.</span>
  </p><p><span m='71510'>To</span> <span m='71630'>begin</span> <span
  m='71960'>with,</span> <span m='72410'>let</span> <span m='72620'>me</span>
  <span m='73100'>remind</span> <span m='73580'>you</span> <span
  m='74660'>of</span> <span m='75140'>the z</span> <span
  m='75470'>transform</span> <span m='76130'>relationship</span> <span
  m='77210'>as</span> <span m='77570'>we</span> <span m='77690'>talked</span>
  <span m='78050'>about</span> <span m='78380'>it</span> <span
  m='78470'>in</span> <span m='78560'>the</span> <span m='78650'>last</span>
  <span m='78980'>lecture.</span> <span m='80970'>The</span> <span
  m='81070'>z</span> <span m='81170'>transform</span> <span m='82130'>X</span>
  <span m='82400'>of</span> <span m='82520'>z</span> <span m='83750'>of</span>
  <span m='83870'>a</span> <span m='83930'>sequence</span> <span
  m='84500'>x</span> <span m='84800'>of</span> <span m='84920'>n</span> <span
  m='85970'>is</span> <span m='86150'>given</span> <span m='86480'>by</span>
  <span m='87140'>the</span> <span m='87260'>sum</span> <span
  m='87890'>of</span> <span m='88340'>x</span> <span m='88640'>of</span> <span
  m='88760'>n</span> <span m='89450'>times</span> <span m='90110'>z</span> <span
  m='90380'>to</span> <span m='90530'>the</span> <span m='90680'>minus</span>
  <span m='90980'>n.</span> </p><p><span m='93130'>The</span> <span
  m='93280'>inverse</span> <span m='93700'>z</span> <span
  m='93850'>transform,</span> <span m='94840'>of</span> <span
  m='94960'>course,</span> <span m='95710'>is</span> <span m='96400'>the</span>
  <span m='96520'>relationship,</span> <span m='97510'>or</span> <span
  m='98320'>the</span> <span m='98710'>set</span> <span m='98980'>of</span>
  <span m='99100'>rules,</span> <span m='100120'>that</span> <span
  m='100450'>allow</span> <span m='100930'>us</span> <span m='101500'>to</span>
  <span m='101950'>obtain</span> <span m='102970'>x of n</span> <span
  m='104320'>the</span> <span m='104410'>original</span> <span
  m='104770'>sequence</span> <span m='105970'>from</span> <span
  m='106390'>its</span> <span m='106600'>z</span> <span
  m='106810'>transform,</span> <span m='107770'>x</span> <span
  m='108040'>of</span> <span m='108130'>z.</span> <span m='110850'>There</span>
  <span m='111510'>are</span> <span m='112380'>a</span> <span
  m='112440'>variety</span> <span m='113130'>of</span> <span
  m='113220'>methods</span> <span m='114120'>that</span> <span
  m='114570'>can</span> <span m='114750'>be</span> <span m='114900'>used</span>
  <span m='115620'>for</span> <span m='116160'>implementing</span> <span
  m='116760'>the</span> <span m='116910'>inverse</span> <span
  m='117195'>z</span> <span m='117480'>transform.</span> <span
  m='119130'>Some</span> <span m='119430'>of</span> <span m='119580'>them</span>
  <span m='120060'>are</span> <span m='120540'>somewhat</span> <span
  m='120990'>informal</span> <span m='121530'>methods.</span> <span
  m='122610'>And</span> <span m='123300'>others,</span> <span
  m='124230'>one</span> <span m='124500'>in</span> <span
  m='124590'>particular</span> <span m='125220'>which</span> <span
  m='125460'>we'll</span> <span m='125580'>talk</span> <span
  m='125910'>about,</span> <span m='126660'>is</span> <span m='126840'>a</span>
  <span m='126900'>somewhat</span> <span m='127290'>formal</span> <span
  m='127740'>method.</span> </p><p><span m='130229'>To</span> <span
  m='130320'>begin</span> <span m='130680'>with,</span> <span
  m='131850'>an</span> <span m='131970'>informal</span> <span
  m='132540'>method</span> <span m='133350'>and</span> <span m='133770'>a</span>
  <span m='133830'>method</span> <span m='134220'>that,</span> <span
  m='134370'>in</span> <span m='134490'>fact,</span> <span
  m='135340'>most</span> <span m='135600'>of</span> <span m='135720'>us</span>
  <span m='136020'>tend</span> <span m='136290'>to</span> <span
  m='136380'>use</span> <span m='136800'>the</span> <span m='136920'>most</span>
  <span m='137250'>often</span> <span m='138360'>is</span> <span
  m='138480'>a</span> <span m='138540'>method</span> <span
  m='139290'>that</span> <span m='140100'>we</span> <span
  m='140310'>could</span> <span m='140880'>refer</span> <span
  m='141330'>to</span> <span m='141900'>as</span> <span m='142650'>the</span>
  <span m='142740'>inspection</span> <span m='143400'>method</span> <span
  m='144210'>for</span> <span m='144570'>computing</span> <span
  m='145350'>the</span> <span m='145500'>inverse</span> <span
  m='145800'>z</span> <span m='146100'>transform.</span> <span
  m='148350'>Basically,</span> <span m='148980'>the</span> <span
  m='149100'>inspection</span> <span m='149670'>method</span> <span
  m='150540'>says</span> <span m='151770'>if</span> <span
  m='152010'>we've</span> <span m='152220'>computed</span> <span
  m='153210'>a</span> <span m='153310'>z</span> <span
  m='153570'>transform</span> <span m='155820'>from</span> <span
  m='156060'>a</span> <span m='156120'>sequence,</span> <span
  m='157230'>then</span> <span m='157410'>by</span> <span
  m='157560'>looking</span> <span m='157920'>at</span> <span
  m='158010'>that</span> <span m='158250'>z</span> <span
  m='158460'>transform,</span> <span m='159630'>we</span> <span
  m='159750'>can</span> <span m='159930'>recognize</span> <span
  m='160920'>more</span> <span m='161190'>or</span> <span m='161250'>less</span>
  <span m='161520'>by</span> <span m='161730'>inspection</span> <span
  m='162900'>the</span> <span m='162990'>sequence</span> <span
  m='164130'>that</span> <span m='165000'>that</span> <span m='165360'>z</span>
  <span m='165630'>transform</span> <span m='166290'>came</span> <span
  m='166620'>from.</span> </p><p><span m='167400'>For</span> <span
  m='167580'>example,</span> <span m='169330'>we</span> <span
  m='169530'>have</span> <span m='169740'>worked</span> <span
  m='170340'>several</span> <span m='170850'>times</span> <span
  m='171600'>now</span> <span m='173360'>the</span> <span
  m='173600'>computation</span> <span m='174710'>of</span> <span m='174920'>the
  z</span> <span m='175220'>transform</span> <span m='176300'>of</span> <span
  m='176450'>an</span> <span m='176540'>exponential</span> <span
  m='177230'>sequence,</span> <span m='178400'>which</span> <span
  m='178640'>is</span> <span m='179180'>a</span> <span m='179450'>right</span>
  <span m='179750'>sided</span> <span m='180170'>sequence,</span> <span
  m='181550'>and</span> <span m='181730'>gotten</span> <span
  m='182120'>is</span> <span m='182270'>the</span> <span
  m='182450'>answer,</span> <span m='183290'>or</span> <span
  m='183590'>the</span> <span m='183890'>z</span> <span
  m='184130'>transform,</span> <span m='185330'>1</span> <span
  m='185720'>over</span> <span m='186110'>1</span> <span m='186320'>minus</span>
  <span m='186740'>a</span> <span m='187010'>z</span> <span m='187220'>to</span>
  <span m='187310'>the</span> <span m='187430'>minus</span> <span
  m='187850'>one,</span> <span m='188550'>with</span> <span m='188900'>a</span>
  <span m='188960'>region</span> <span m='189320'>of</span> <span
  m='189410'>convergence</span> <span m='190240'>for</span> <span
  m='190400'>the</span> <span m='190520'>magnitude</span> <span
  m='191090'>of</span> <span m='191180'>z</span> <span m='191510'>greater</span>
  <span m='191870'>than</span> <span m='192020'>the</span> <span
  m='192110'>magnitude</span> <span m='192680'>of</span> <span
  m='192780'>a.</span> <span m='194790'>Consequently,</span> <span
  m='196560'>having</span> <span m='196860'>worked</span> <span
  m='197130'>that</span> <span m='197340'>example,</span> <span
  m='198910'>if</span> <span m='199200'>I</span> <span m='199380'>now</span>
  <span m='199620'>present</span> <span m='200190'>you</span> <span
  m='200730'>with</span> <span m='200940'>this</span> <span m='201210'>z</span>
  <span m='201450'>transform</span> <span m='202950'>and</span> <span
  m='203070'>ask</span> <span m='203430'>you</span> <span m='203550'>what</span>
  <span m='203760'>sequence</span> <span m='204880'>generated</span> <span
  m='205170'>it.</span> <span m='206280'>One</span> <span m='206550'>way</span>
  <span m='207000'>of</span> <span m='207150'>doing</span> <span
  m='207540'>that,</span> <span m='207970'>obviously,</span> <span
  m='208620'>is</span> <span m='209520'>by</span> <span
  m='209700'>inspection.</span> <span m='211470'>By</span> <span
  m='211620'>recognizing</span> <span m='212730'>that</span> <span
  m='213510'>this</span> <span m='213690'>sequence</span> <span
  m='214680'>generates</span> <span m='215850'>that</span> <span
  m='216040'>z</span> <span m='216140'>transform.</span> </p><p><span
  m='219230'>Another</span> <span m='219710'>example</span> <span
  m='220250'>that</span> <span m='220370'>we've</span> <span
  m='220580'>worked</span> <span m='220820'>several</span> <span
  m='221240'>times</span> <span m='222050'>now</span> <span m='223040'>is</span>
  <span m='223880'>the</span> <span m='224240'>exponential</span> <span
  m='224960'>sequence,</span> <span m='225890'>which</span> <span
  m='226070'>is</span> <span m='226190'>left</span> <span
  m='226490'>sided.</span> <span m='227630'>That</span> <span
  m='227810'>is</span> <span m='227930'>0</span> <span m='228560'>for</span>
  <span m='228770'>n</span> <span m='228920'>greater</span> <span
  m='229280'>than</span> <span m='229460'>zero,</span> <span
  m='230630'>generating</span> <span m='231590'>the</span> <span
  m='231680'>same</span> <span m='232010'>ratio</span> <span
  m='232460'>of</span> <span m='232550'>polynomials</span> <span
  m='233990'>as</span> <span m='234680'>in</span> <span m='235130'>the</span>
  <span m='235250'>right</span> <span m='235490'>sided</span> <span
  m='235880'>exponential,</span> <span m='237170'>but</span> <span
  m='237500'>with</span> <span m='237710'>a</span> <span
  m='237740'>region</span> <span m='238100'>of</span> <span
  m='238190'>convergence</span> <span m='239150'>which</span> <span
  m='239390'>is</span> <span m='239810'>the</span> <span
  m='240020'>interior</span> <span m='240650'>of</span> <span
  m='240770'>a</span> <span m='240800'>circle</span> <span
  m='241730'>rather</span> <span m='242090'>than</span> <span
  m='242330'>in</span> <span m='242420'>this</span> <span m='242630'>case</span>
  <span m='242990'>where</span> <span m='243140'>the</span> <span
  m='243230'>region</span> <span m='243530'>of</span> <span
  m='243620'>convergence</span> <span m='244310'>is</span> <span
  m='245360'>the</span> <span m='245510'>exterior</span> <span
  m='246260'>of</span> <span m='246350'>a</span> <span m='246410'>circle.</span>
  <span m='247430'>And</span> <span m='247550'>in</span> <span
  m='247670'>fact,</span> <span m='248060'>it</span> <span m='248150'>was</span>
  <span m='250250'>the</span> <span m='250370'>comparison</span> <span
  m='251090'>between</span> <span m='251450'>these two</span> <span
  m='251630'>z</span> <span m='252050'>transforms</span> <span
  m='253460'>that</span> <span m='253580'>caused</span> <span
  m='253940'>us</span> <span m='254150'>to</span> <span m='254270'>focus</span>
  <span m='254870'>in</span> <span m='254990'>the</span> <span
  m='255080'>last</span> <span m='255380'>lecture</span> <span
  m='255980'>on</span> <span m='256190'>the</span> <span
  m='256279'>importance</span> <span m='257000'>of</span> <span
  m='257149'>the</span> <span m='257240'>region</span> <span
  m='257570'>of</span> <span m='257660'>convergence.</span> </p><p><span
  m='259200'>So</span> <span m='259700'>this</span> <span m='259910'>is</span>
  <span m='260029'>one</span> <span m='260269'>method,</span> <span
  m='261000'>which</span> <span m='261410'>I</span> <span
  m='261560'>emphasize</span> <span m='262130'>again</span> <span
  m='262640'>is</span> <span m='263930'>in</span> <span m='264080'>fact,</span>
  <span m='264660'>one</span> <span m='264770'>of</span> <span
  m='264830'>the</span> <span m='264920'>most</span> <span
  m='265190'>common</span> <span m='265610'>methods.</span> <span
  m='266480'>That</span> <span m='266720'>is,</span> <span
  m='267170'>just</span> <span m='267380'>simply</span> <span
  m='267800'>recognizing</span> <span m='268880'>the</span> <span
  m='268970'>z</span> <span m='269180'>transform</span> <span
  m='269990'>as</span> <span m='270110'>something</span> <span
  m='270500'>that</span> <span m='270590'>we've</span> <span
  m='270800'>computed</span> <span m='271310'>previously</span> <span
  m='272030'>from</span> <span m='272240'>a</span> <span
  m='272270'>sequence.</span> <span m='273560'>And</span> <span
  m='273690'>that</span> <span m='274100'>obviously</span> <span
  m='274700'>also</span> <span m='275120'>as</span> <span m='275270'>you</span>
  <span m='275390'>work</span> <span m='275630'>more</span> <span
  m='275870'>examples,</span> <span m='277640'>you</span> <span
  m='278000'>build</span> <span m='278330'>up</span> <span m='278510'>a</span>
  <span m='278570'>larger</span> <span m='280070'>list</span> <span
  m='280670'>of</span> <span m='281510'>sequences</span> <span
  m='282290'>and</span> <span m='282380'>z</span> <span
  m='282590'>transforms</span> <span m='283400'>which</span> <span
  m='283730'>pairs</span> <span m='284150'>what</span> <span
  m='284330'>you</span> <span m='284450'>can</span> <span
  m='284600'>recognize.</span> </p><p><span m='287140'>The</span> <span
  m='287200'>second</span> <span m='287590'>method</span> <span
  m='288310'>for</span> <span m='288820'>computing</span> <span
  m='289750'>the</span> <span m='290470'>inverse</span> <span
  m='290910'>z</span> <span m='291200'>transform</span> <span
  m='295520'>is</span> <span m='295690'>based</span> <span m='296050'>on</span>
  <span m='296170'>the</span> <span m='296290'>fact</span> <span
  m='297400'>that</span> <span m='298850'>the</span> <span m='299360'>z</span>
  <span m='299660'>transform</span> <span m='300770'>relationship</span> <span
  m='302900'>is</span> <span m='303200'>basically</span> <span
  m='304340'>a</span> <span m='304520'>power</span> <span
  m='304940'>series</span> <span m='306320'>in</span> <span m='306530'>z.</span>
  <span m='307340'>That</span> <span m='307580'>is,</span> <span
  m='308570'>if</span> <span m='308720'>we</span> <span m='308840'>look</span>
  <span m='309050'>back</span> <span m='309620'>here</span> <span
  m='310760'>at</span> <span m='311210'>the</span> <span m='311300'>z</span>
  <span m='311510'>transform</span> <span m='312170'>expression,</span> <span
  m='313710'>this</span> <span m='313970'>is</span> <span
  m='314570'>essentially</span> <span m='315230'>a</span> <span
  m='315290'>power</span> <span m='315680'>series</span> <span
  m='316100'>relationship</span> <span m='317750'>which</span> <span
  m='318470'>expands</span> <span m='319190'>x</span> <span m='319520'>of</span>
  <span m='319640'>z</span> <span m='320510'>in</span> <span
  m='320630'>powers</span> <span m='321110'>of</span> <span m='321230'>z.</span>
  <span m='322880'>Consequently,</span> <span m='324230'>given</span> <span
  m='324770'>a</span> <span m='324830'>z</span> <span
  m='325070'>transform,</span> <span m='326990'>if</span> <span
  m='327200'>we</span> <span m='327350'>can</span> <span
  m='327530'>expand</span> <span m='328150'>it</span> <span m='328970'>in</span>
  <span m='329120'>terms</span> <span m='329450'>of</span> <span
  m='329540'>powers</span> <span m='330020'>of</span> <span m='330110'>z,</span>
  <span m='331250'>then</span> <span m='331670'>we</span> <span
  m='331850'>can</span> <span m='332030'>pick</span> <span m='332330'>off</span>
  <span m='332930'>the</span> <span m='333050'>coefficients</span> <span
  m='333800'>in</span> <span m='333890'>that</span> <span
  m='334070'>expansion</span> <span m='335330'>as</span> <span
  m='336080'>values</span> <span m='336830'>of</span> <span
  m='336980'>the</span> <span m='337070'>sequence</span> <span
  m='337670'>x</span> <span m='337940'>of n.</span> </p><p><span
  m='339530'>For</span> <span m='339710'>example,</span> <span
  m='341430'>let's</span> <span m='341820'>take</span> <span
  m='342120'>the</span> <span m='342210'>sequence,</span> <span
  m='343470'>sorry</span> <span m='343800'>the</span> <span m='343920'>z</span>
  <span m='344100'>transform</span> <span m='344910'>x</span> <span
  m='345210'>of</span> <span m='345330'>z,</span> <span m='346510'>which</span>
  <span m='346620'>is</span> <span m='346770'>1</span> <span
  m='346980'>over</span> <span m='347490'>1</span> <span m='347760'>minus</span>
  <span m='348150'>a</span> <span m='348465'>z to</span> <span m='348780'>the
  minus</span> <span m='349250'>1.</span> <span m='350830'>Or</span> <span
  m='351310'>we</span> <span m='351430'>can</span> <span
  m='351610'>rewrite</span> <span m='352000'>it</span> <span m='352180'>as
  z</span> <span m='352590'>over</span> <span m='352790'>z</span> <span
  m='353050'>minus</span> <span m='353350'>a.</span> <span m='354700'>Now</span>
  <span m='355330'>this</span> <span m='355930'>of</span> <span
  m='356050'>course</span> <span m='356470'>is</span> <span m='356590'>a</span>
  <span m='356680'>z</span> <span m='356890'>transform</span> <span
  m='360400'>whose</span> <span m='360580'>inverse</span> <span
  m='361300'>we</span> <span m='361450'>know</span> <span m='361780'>how</span>
  <span m='361930'>to</span> <span m='362020'>compute</span> <span
  m='362650'>by</span> <span m='362860'>inspection.</span> <span
  m='364690'>However,</span> <span m='365580'>we</span> <span
  m='365700'>can</span> <span m='365880'>also</span> <span
  m='366300'>compute</span> <span m='366750'>the</span> <span
  m='366870'>inverse</span> <span m='367230'>z</span> <span
  m='367470'>transform</span> <span m='368760'>by</span> <span
  m='369090'>expanding</span> <span m='369870'>this</span> <span
  m='370080'>expression</span> <span m='371400'>in</span> <span
  m='371520'>a</span> <span m='371580'>power</span> <span
  m='371940'>series.</span> <span m='374040'>Let's</span> <span
  m='374400'>divide</span> <span m='375180'>1</span> <span m='376350'>by</span>
  <span m='376980'>1</span> <span m='377280'>minus</span> <span
  m='377670'>a</span> <span m='377970'>z to the</span> <span
  m='378270'>minus</span> <span m='378740'>1,</span> <span m='379500'>and</span>
  <span m='379620'>then</span> <span m='379770'>recognize</span> <span
  m='380520'>the</span> <span m='380640'>coefficients</span> <span
  m='381390'>in</span> <span m='381480'>that</span> <span
  m='381630'>expansion</span> <span m='382800'>as</span> <span
  m='382950'>values</span> <span m='383700'>of</span> <span
  m='383880'>the</span> <span m='383970'>sequence</span> <span
  m='384840'>X</span> <span m='385080'>of n.</span> </p><p><span
  m='386530'>So</span> <span m='387070'>carrying</span> <span
  m='387490'>that</span> <span m='387730'>out.</span> <span m='388540'>We</span>
  <span m='388690'>have</span> <span m='388870'>1</span> <span
  m='389110'>divided</span> <span m='389650'>into</span> <span
  m='389920'>1</span> <span m='391090'>is</span> <span m='391240'>1.</span>
  <span m='393180'>Multiplying</span> <span m='393770'>back</span> <span
  m='394160'>we</span> <span m='394310'>have</span> <span m='394460'>1</span>
  <span m='394940'>minus</span> <span m='395420'>a</span> <span
  m='395890'>z</span> <span m='396360'>to the</span> <span
  m='396830'>minus</span> <span m='397250'>1.</span> <span
  m='398730'>Subtracting</span> <span m='400130'>we</span> <span
  m='400220'>then</span> <span m='400430'>have</span> <span m='400730'>a
  z</span> <span m='401210'>to</span> <span m='401360'>the</span> <span
  m='401480'>minus</span> <span m='401950'>1.</span> <span
  m='403780'>Dividing</span> <span m='404260'>by</span> <span
  m='404500'>1</span> <span m='405550'>we</span> <span m='405640'>then</span>
  <span m='405880'>have</span> <span m='406660'>a</span> <span
  m='406960'>times</span> <span m='407380'>z</span> <span m='407710'>to</span>
  <span m='407870'>the</span> <span m='407980'>minus</span> <span
  m='408410'>1.</span> <span m='410122'>Multiplying</span> <span
  m='410980'>down</span> <span m='411300'>again,</span> <span
  m='411960'>we</span> <span m='412110'>have</span> <span m='412410'>a</span>
  <span m='412800'>z to the</span> <span m='413190'>minus</span> <span
  m='413660'>1</span> <span m='415380'>minus</span> <span m='416040'>a</span>
  <span m='416240'>squared</span> <span m='417300'>z</span> <span
  m='417590'>to</span> <span m='417750'>the</span> <span m='417870'>minus</span>
  <span m='418320'>2.</span> <span m='420130'>Subtracting</span> <span
  m='421390'>we</span> <span m='421540'>have</span> <span m='422080'>a</span>
  <span m='422290'>squared</span> <span m='423370'>z</span> <span m='423910'>to
  the</span> <span m='424330'>minus</span> <span m='424750'>2.</span> <span
  m='425740'>Dividing</span> <span m='426220'>by</span> <span
  m='426430'>1</span> <span m='427030'>we</span> <span m='427240'>have</span>
  <span m='427690'>a</span> <span m='427870'>squared</span> <span
  m='429400'>z</span> <span m='430000'>to</span> <span m='430120'>the</span>
  <span m='430240'>minus</span> <span m='430630'>2.</span> <span
  m='431650'>And</span> <span m='431800'>if</span> <span m='431920'>we</span>
  <span m='432010'>continue</span> <span m='432550'>this,</span> <span
  m='433360'>we'll</span> <span m='433480'>generate</span> <span
  m='434440'>terms</span> <span m='435070'>1,</span> <span m='435565'>a</span>
  <span m='436060'>times</span> <span m='436360'>z</span> <span
  m='436540'>to</span> <span m='436630'>the</span> <span m='436720'>minus</span>
  <span m='437140'>1,</span> <span m='438370'>a squared</span> <span
  m='439000'>times</span> <span m='439270'>z</span> <span m='439450'>to</span>
  <span m='439570'>the</span> <span m='439660'>minus</span> <span
  m='440050'>2,</span> <span m='441500'>a cubed</span> <span
  m='441866'>times</span> <span m='442600'>z</span> <span m='443290'>to</span>
  <span m='443410'>the</span> <span m='443500'>minus</span> <span
  m='443920'>3,</span> <span m='445690'>et</span> <span
  m='446010'>cetera.</span> </p><p><span m='448670'>This</span> <span
  m='448860'>series</span> <span m='449440'>will</span> <span
  m='449590'>continue</span> <span m='450280'>with</span> <span
  m='450490'>an</span> <span m='450580'>infinite</span> <span
  m='450910'>number</span> <span m='451240'>of</span> <span
  m='451330'>terms.</span> <span m='452800'>And</span> <span
  m='453370'>we</span> <span m='453520'>can</span> <span
  m='453700'>recognize</span> <span m='454900'>then</span> <span
  m='455890'>this</span> <span m='456280'>as</span> <span m='457000'>the</span>
  <span m='457150'>expansion</span> <span m='458530'>of</span> <span
  m='458710'>x</span> <span m='458980'>of</span> <span m='459070'>z</span> <span
  m='460180'>in</span> <span m='460330'>the</span> <span m='460420'>form</span>
  <span m='461140'>the</span> <span m='461290'>sum</span> <span
  m='461710'>of</span> <span m='461830'>x</span> <span m='462220'>n</span> <span
  m='462880'>times</span> <span m='463150'>z</span> <span m='463390'>to</span>
  <span m='463510'>the</span> <span m='463630'>minus</span> <span
  m='463970'>n.</span> <span m='464770'>Consequently,</span> <span
  m='466090'>we</span> <span m='466210'>can</span> <span
  m='466390'>recognize</span> <span m='467560'>that</span> <span
  m='468790'>apparently</span> <span m='470320'>x</span> <span
  m='470590'>of</span> <span m='470740'>n</span> <span m='471550'>is</span>
  <span m='471760'>1</span> <span m='472470'>at</span> <span m='472640'>n</span>
  <span m='472750'>equal</span> <span m='473020'>zero,</span> <span
  m='473740'>a</span> <span m='474100'>at n</span> <span
  m='474460'>equals</span> <span m='474760'>1,</span> <span m='475450'>a</span>
  <span m='475600'>squared</span> <span m='476020'>at n</span> <span
  m='476290'>equals</span> <span m='476650'>2,</span> <span m='477280'>a</span>
  <span m='477440'>cubed</span> <span m='477790'>at</span> <span
  m='477880'>n</span> <span m='478030'>equals</span> <span m='478360'>3,</span>
  <span m='478860'>etc.</span> </p><p><span m='481070'>Of</span> <span
  m='481130'>course,</span> <span m='483120'>there</span> <span
  m='483380'>are</span> <span m='483530'>lots</span> <span m='483860'>of</span>
  <span m='484010'>ways</span> <span m='484730'>of</span> <span
  m='485120'>expanding</span> <span m='486860'>a</span> <span
  m='486950'>function</span> <span m='487430'>like</span> <span
  m='487700'>this</span> <span m='488270'>in</span> <span m='488390'>a</span>
  <span m='488450'>power</span> <span m='488810'>series.</span> <span
  m='490070'>For</span> <span m='490280'>example,</span> <span
  m='491490'>if</span> <span m='491600'>I</span> <span m='491720'>simply</span>
  <span m='492110'>reverse</span> <span m='492860'>the</span> <span
  m='493010'>order</span> <span m='493340'>of</span> <span
  m='493460'>these</span> <span m='493670'>two</span> <span
  m='493880'>terms</span> <span m='495200'>and</span> <span
  m='495320'>carried</span> <span m='495740'>out</span> <span
  m='495890'>the</span> <span m='496010'>division,</span> <span
  m='497540'>this</span> <span m='497810'>isn't</span> <span
  m='498050'>the</span> <span m='498170'>series</span> <span
  m='498650'>I'd</span> <span m='498820'>get.</span> <span
  m='499850'>What</span> <span m='500060'>I'd</span> <span m='500150'>get</span>
  <span m='500450'>instead</span> <span m='501710'>is</span> <span
  m='502370'>the</span> <span m='502490'>series,</span> <span
  m='503640'>which</span> <span m='503750'>is</span> <span
  m='503900'>minus</span> <span m='504620'>a</span> <span m='504800'>to</span>
  <span m='504920'>the</span> <span m='505010'>minus</span> <span
  m='505340'>1</span> <span m='505580'>times</span> <span m='505930'>z,</span>
  <span m='507200'>minus</span> <span m='507680'>a</span> <span
  m='507890'>to</span> <span m='507980'>the</span> <span m='508100'>minus</span>
  <span m='508430'>2</span> <span m='508640'>times</span> <span
  m='508970'>z</span> <span m='509150'>squared,</span> <span
  m='510350'>minus</span> <span m='510710'>a</span> <span m='510890'>to</span>
  <span m='510980'>the</span> <span m='511070'>minus</span> <span
  m='511430'>3</span> <span m='511700'>times</span> <span m='512010'>z</span>
  <span m='512220'>cubed,</span> <span m='512919'>etc.</span> </p><p><span
  m='514710'>In</span> <span m='514860'>that</span> <span
  m='515070'>case,</span> <span m='515789'>if</span> <span
  m='515970'>this</span> <span m='516179'>was</span> <span m='516360'>the</span>
  <span m='516510'>expansion,</span> <span m='518640'>then</span> <span
  m='518850'>what</span> <span m='519000'>I</span> <span m='519120'>would</span>
  <span m='519270'>have</span> <span m='519510'>to</span> <span
  m='519630'>recognize</span> <span m='520500'>as</span> <span
  m='520679'>the</span> <span m='520799'>sequence</span> <span
  m='521640'>corresponding</span> <span m='522419'>to</span> <span
  m='522570'>this</span> <span m='524179'>is</span> <span m='524720'>the</span>
  <span m='524840'>sequence</span> <span m='525620'>which</span> <span
  m='525890'>is</span> <span m='526010'>0</span> <span m='526490'>at</span>
  <span m='526640'>n equals</span> <span m='526940'>zero.</span> <span
  m='528560'>It</span> <span m='528650'>has</span> <span m='528950'>no</span>
  <span m='529310'>terms</span> <span m='529880'>of</span> <span
  m='530030'>the</span> <span m='530150'>form</span> <span m='530550'>z</span>
  <span m='530810'>to</span> <span m='530960'>the</span> <span
  m='531080'>minus</span> <span m='531490'>a</span> <span
  m='531560'>positive</span> <span m='532100'>power.</span> <span
  m='533240'>So</span> <span m='533570'>apparently,</span> <span
  m='534770'>it's</span> <span m='534950'>all</span> <span m='535250'>0</span>
  <span m='535730'>for</span> <span m='535940'>n</span> <span
  m='536110'>greater</span> <span m='536480'>than</span> <span
  m='536660'>zero.</span> <span m='537890'>And</span> <span
  m='538160'>it's</span> <span m='538520'>minus</span> <span m='538940'>a</span>
  <span m='539090'>to</span> <span m='539210'>the</span> <span
  m='539300'>minus</span> <span m='539690'>1</span> <span m='540080'>at</span>
  <span m='540260'>n</span> <span m='540650'>equals minus</span> <span
  m='541100'>1,</span> <span m='542240'>minus</span> <span m='542630'>a</span>
  <span m='542810'>to</span> <span m='542900'>the</span> <span
  m='543020'>minus</span> <span m='543380'>2</span> <span m='543680'>at</span>
  <span m='543770'>n</span> <span m='544160'>equals minus</span> <span
  m='544550'>2,</span> <span m='545000'>etc.</span> </p><p><span
  m='546260'>So</span> <span m='546800'>in</span> <span m='546980'>fact,</span>
  <span m='547550'>for</span> <span m='547700'>this</span> <span
  m='547910'>example,</span> <span m='549170'>I</span> <span
  m='549290'>could</span> <span m='549530'>expand</span> <span
  m='550400'>this</span> <span m='551510'>either</span> <span
  m='552140'>in</span> <span m='552290'>this</span> <span
  m='552860'>power</span> <span m='553190'>series,</span> <span
  m='554420'>or</span> <span m='555110'>I</span> <span m='555230'>could</span>
  <span m='555380'>expand</span> <span m='555850'>it</span> <span
  m='556010'>in</span> <span m='556160'>this</span> <span
  m='556340'>power</span> <span m='556670'>series.</span> <span
  m='558550'>Well,</span> <span m='558880'>which</span> <span
  m='559120'>power</span> <span m='559460'>series</span> <span
  m='559930'>is</span> <span m='560020'>the</span> <span m='560140'>right</span>
  <span m='560320'>power</span> <span m='560650'>series?</span> <span
  m='563410'>We</span> <span m='563560'>know</span> <span m='563830'>in</span>
  <span m='563950'>fact</span> <span m='564790'>that</span> <span
  m='565000'>given</span> <span m='565390'>just</span> <span
  m='565600'>this</span> <span m='565810'>ratio</span> <span
  m='566260'>of</span> <span m='566350'>polynomials,</span> <span
  m='567620'>there</span> <span m='567730'>are</span> <span
  m='567760'>several</span> <span m='568270'>choices</span> <span
  m='569890'>for</span> <span m='570520'>the</span> <span
  m='570640'>sequence</span> <span m='571150'>that</span> <span
  m='571240'>it</span> <span m='571330'>corresponds</span> <span
  m='572140'>to</span> <span m='572410'>depending</span> <span
  m='572980'>on</span> <span m='573100'>the</span> <span
  m='573190'>region</span> <span m='573520'>of</span> <span
  m='573610'>convergence.</span> <span m='575550'>If</span> <span
  m='576030'>I</span> <span m='576180'>associate</span> <span
  m='578010'>as</span> <span m='578220'>the</span> <span
  m='578310'>region</span> <span m='578670'>of</span> <span
  m='578790'>convergence</span> <span m='580620'>the</span> <span
  m='580740'>magnitude</span> <span m='581400'>of</span> <span
  m='581520'>z</span> <span m='582300'>greater</span> <span
  m='582810'>than</span> <span m='582990'>the</span> <span
  m='583080'>magnitude</span> <span m='583650'>of</span> <span
  m='583770'>a,</span> <span m='585240'>then</span> <span m='585620'>it's</span>
  <span m='585900'>this</span> <span m='586200'>power</span> <span
  m='586560'>series</span> <span m='587790'>that</span> <span
  m='587930'>converges.</span> <span m='589940'>And</span> <span
  m='590120'>this</span> <span m='590330'>power</span> <span
  m='590690'>series</span> <span m='591170'>diverges.</span> </p><p><span
  m='592740'>So</span> <span m='592820'>for</span> <span m='593000'>that</span>
  <span m='593240'>region</span> <span m='593600'>of</span> <span
  m='593690'>convergence,</span> <span m='594620'>that</span> <span
  m='594860'>is</span> <span m='595520'>with</span> <span m='595700'>the</span>
  <span m='595820'>magnitude</span> <span m='596450'>of</span> <span
  m='596540'>z</span> <span m='597740'>greater</span> <span
  m='598220'>than</span> <span m='598400'>the</span> <span
  m='598490'>magnitude</span> <span m='599060'>of</span> <span
  m='599190'>a</span> <span m='599660'>as</span> <span m='599870'>the</span>
  <span m='599960'>region</span> <span m='600290'>of</span> <span
  m='600380'>convergence,</span> <span m='601730'>this</span> <span
  m='602030'>is</span> <span m='602150'>the</span> <span m='602270'>power</span>
  <span m='602630'>series.</span> <span m='603590'>And</span> <span
  m='603710'>consequently,</span> <span m='605060'>the</span> <span
  m='605240'>answer</span> <span m='605960'>is</span> <span m='607270'>a</span>
  <span m='607570'>to</span> <span m='607730'>the</span> <span
  m='607910'>n</span> <span m='608240'>times</span> <span m='608600'>u</span>
  <span m='608810'>of n,</span> <span m='609590'>which</span> <span
  m='609770'>of</span> <span m='609860'>course</span> <span m='610160'>is</span>
  <span m='610280'>consistent</span> <span m='611000'>with</span> <span
  m='611690'>what</span> <span m='611840'>we</span> <span m='611990'>know</span>
  <span m='612200'>already</span> <span m='612740'>or</span> <span
  m='612890'>equivalently</span> <span m='613430'>consistent</span> <span
  m='614060'>with</span> <span m='614210'>the</span> <span
  m='614330'>inspection</span> <span m='614900'>method.</span> </p><p><span
  m='616380'>On</span> <span m='616500'>the</span> <span m='616620'>other</span>
  <span m='616860'>hand,</span> <span m='617440'>if</span> <span
  m='617550'>the</span> <span m='617640'>region</span> <span
  m='618000'>of</span> <span m='618120'>convergence</span> <span
  m='619380'>was</span> <span m='620550'>the</span> <span
  m='620670'>magnitude</span> <span m='621300'>of</span> <span
  m='621420'>z</span> <span m='621720'>less</span> <span m='622050'>than</span>
  <span m='622200'>the</span> <span m='622290'>magnitude</span> <span
  m='622890'>of</span> <span m='623010'>a,</span> <span m='624810'>then</span>
  <span m='625530'>it's</span> <span m='626070'>this</span> <span
  m='626370'>power</span> <span m='626730'>series</span> <span
  m='627210'>that</span> <span m='627330'>converges.</span> <span
  m='628620'>And</span> <span m='628740'>consequently</span> <span
  m='629730'>in</span> <span m='629910'>that</span> <span
  m='630090'>case,</span> <span m='630550'>we</span> <span m='630570'>get</span>
  <span m='631200'>a</span> <span m='631260'>left</span> <span
  m='631560'>sided</span> <span m='631950'>sequence,</span> <span
  m='632580'>which</span> <span m='632820'>again</span> <span
  m='633120'>is</span> <span m='633210'>consistent</span> <span
  m='634230'>with</span> <span m='634830'>what</span> <span m='635040'>we</span>
  <span m='635190'>know</span> <span m='635820'>either</span> <span
  m='636090'>from</span> <span m='636300'>the</span> <span
  m='636390'>inspection</span> <span m='636990'>method</span> <span
  m='637350'>or</span> <span m='637710'>equivalently</span> <span
  m='638340'>from</span> <span m='638520'>the</span> <span
  m='638640'>examples</span> <span m='639180'>that</span> <span
  m='639300'>we've</span> <span m='639480'>worked</span> <span
  m='639720'>before.</span> </p><p><span m='642150'>One</span> <span
  m='642570'>obvious</span> <span m='643050'>drawback</span> <span
  m='643860'>to</span> <span m='644190'>the</span> <span m='644790'>power</span>
  <span m='645150'>series</span> <span m='646680'>is</span> <span
  m='647280'>the</span> <span m='647400'>fact</span> <span
  m='648030'>that</span> <span m='648570'>when</span> <span m='648780'>we</span>
  <span m='648900'>generate</span> <span m='649440'>the</span> <span
  m='649560'>inverse</span> <span m='649930'>z</span> <span
  m='650130'>transform</span> <span m='650850'>this</span> <span
  m='651060'>way,</span> <span m='652590'>we</span> <span m='652770'>get</span>
  <span m='653820'>the</span> <span m='654120'>values</span> <span
  m='654840'>in</span> <span m='654960'>the</span> <span
  m='655050'>sequence</span> <span m='655950'>as</span> <span
  m='656130'>individual</span> <span m='656790'>terms.</span> <span
  m='657360'>That</span> <span m='657540'>is,</span> <span m='659210'>we</span>
  <span m='659690'>generate</span> <span m='660440'>x</span> <span
  m='660770'>of</span> <span m='660890'>n</span> <span m='661880'>not in</span>
  <span m='662240'>closed</span> <span m='662600'>form.</span> <span
  m='663210'>We</span> <span m='663330'>generate</span> <span
  m='663660'>it</span> <span m='663920'>as</span> <span m='664070'>a</span>
  <span m='664130'>sequence.</span> <span m='665450'>For</span> <span
  m='665630'>simple</span> <span m='666020'>sequences</span> <span
  m='666650'>of</span> <span m='666740'>course,</span> <span
  m='667040'>we</span> <span m='667160'>can</span> <span
  m='667340'>recognize</span> <span m='667970'>a</span> <span
  m='668030'>closed</span> <span m='668390'>form</span> <span
  m='669080'>form</span> <span m='669500'>for</span> <span
  m='669680'>that.</span> <span m='670610'>But</span> <span m='670880'>in</span>
  <span m='671000'>more</span> <span m='671180'>complicated</span> <span
  m='671930'>cases,</span> <span m='672380'>we</span> <span
  m='672550'>can't.</span> </p><p><span m='676730'>All</span> <span
  m='676820'>right.</span> <span m='677200'>A</span> <span
  m='677270'>third</span> <span m='677630'>method</span> <span
  m='678560'>for</span> <span m='679370'>generating</span> <span
  m='680480'>the</span> <span m='680660'>inverse</span> <span
  m='680960'>z</span> <span m='681260'>transform</span> <span
  m='683090'>is</span> <span m='683630'>basically</span> <span
  m='685100'>an</span> <span m='685190'>extension</span> <span
  m='686090'>of</span> <span m='686270'>the</span> <span
  m='686360'>inspection</span> <span m='686990'>method,</span> <span
  m='688100'>which</span> <span m='688520'>allows</span> <span
  m='688970'>us</span> <span m='689150'>to</span> <span m='689300'>take</span>
  <span m='689660'>a</span> <span m='689720'>more</span> <span
  m='689930'>complicated</span> <span m='691220'>z</span> <span
  m='691460'>transform</span> <span m='692660'>expression</span> <span
  m='694010'>and</span> <span m='694130'>expand</span> <span
  m='694700'>it</span> <span m='694820'>out</span> <span m='695390'>in</span>
  <span m='695540'>terms</span> <span m='697715'>of</span> <span
  m='698150'>terms</span> <span m='698630'>that</span> <span
  m='699020'>we</span> <span m='699170'>can</span> <span
  m='699380'>recognize</span> <span m='700460'>by</span> <span
  m='700670'>inspection.</span> <span m='702390'>And</span> <span
  m='702800'>this</span> <span m='703040'>method</span> <span
  m='704160'>I'll</span> <span m='704360'>refer</span> <span
  m='704760'>to</span> <span m='705230'>as</span> <span m='705890'>the</span>
  <span m='706010'>method</span> <span m='706490'>based</span> <span
  m='707000'>on</span> <span m='707600'>the</span> <span
  m='707720'>partial</span> <span m='708110'>fraction</span> <span
  m='708590'>expansion.</span> </p><p><span m='710700'>I</span> <span
  m='710820'>assume</span> <span m='711270'>that</span> <span
  m='711630'>some</span> <span m='711930'>of</span> <span m='712050'>you</span>
  <span m='712830'>are</span> <span m='713130'>familiar</span> <span
  m='713910'>with</span> <span m='714420'>the</span> <span
  m='714510'>partial</span> <span m='714900'>fraction</span> <span
  m='715380'>expansion</span> <span m='716100'>in</span> <span
  m='716280'>general</span> <span m='717480'>for</span> <span
  m='717960'>a</span> <span m='718050'>rational</span> <span
  m='718560'>function.</span> <span m='719700'>But</span> <span
  m='720360'>in</span> <span m='720510'>case</span> <span
  m='720810'>you're</span> <span m='720960'>not</span> <span
  m='721410'>or</span> <span m='721770'>in</span> <span m='721860'>case</span>
  <span m='722100'>you're</span> <span m='722220'>rusty</span> <span
  m='722670'>on</span> <span m='722850'>it,</span> <span m='722970'>let</span>
  <span m='723150'>me</span> <span m='723270'>just</span> <span
  m='723780'>quickly</span> <span m='724620'>review</span> <span
  m='725190'>what</span> <span m='725400'>the</span> <span
  m='725490'>partial</span> <span m='726210'>fraction</span> <span
  m='726690'>expansion</span> <span m='727260'>consists</span> <span
  m='727800'>of.</span> <span m='730670'>Let's</span> <span
  m='731210'>consider</span> <span m='732430'>the</span> <span
  m='732500'>general</span> <span m='733160'>function</span> <span
  m='734900'>of</span> <span m='736040'>a</span> <span
  m='736580'>variable,</span> <span m='737330'>I'll</span> <span
  m='737450'>take</span> <span m='737690'>as</span> <span m='737780'>a</span>
  <span m='737840'>complex</span> <span m='738440'>variable</span> <span
  m='739010'>x,</span> <span m='740370'>which</span> <span m='740540'>is</span>
  <span m='740960'>a</span> <span m='741050'>rational</span> <span
  m='741620'>function</span> <span m='742250'>in</span> <span
  m='742460'>x.</span> <span m='744200'>It is</span> <span m='745310'>one</span>
  <span m='745550'>polynomial</span> <span m='746600'>in</span> <span
  m='746720'>the</span> <span m='746810'>numerator</span> <span
  m='747800'>divided</span> <span m='748280'>by</span> <span m='749030'>a</span>
  <span m='749120'>denominator</span> <span m='749780'>polynomial.</span> <span
  m='751370'>And</span> <span m='751640'>let</span> <span m='751760'>me</span>
  <span m='752480'>remark</span> <span m='752900'>incidentally</span> <span
  m='753620'>that</span> <span m='754340'>you</span> <span
  m='754430'>shouldn't</span> <span m='754700'>confuse</span> <span
  m='755210'>this</span> <span m='755480'>x</span> <span m='756020'>with</span>
  <span m='756710'>the</span> <span m='756830'>sequence</span> <span
  m='757670'>values</span> <span m='758300'>x</span> <span m='758550'>of
  n</span> <span m='758810'>that</span> <span m='758900'>we've</span> <span
  m='759290'>been</span> <span m='759440'>referring</span> <span
  m='759860'>to.</span> <span m='760520'>This</span> <span m='760700'>is</span>
  <span m='760820'>simply</span> <span m='761210'>some</span> <span
  m='761450'>arbitrary</span> <span m='762080'>complex</span> <span
  m='763220'>number,</span> <span m='765490'>or</span> <span
  m='765640'>complex</span> <span m='766150'>variable.</span> </p><p><span
  m='768570'>Now</span> <span m='770650'>I</span> <span m='770830'>can</span>
  <span m='771460'>in</span> <span m='771610'>general</span> <span
  m='772660'>expand</span> <span m='773240'>the</span> <span
  m='773320'>rational</span> <span m='773830'>function</span> <span
  m='775650'>in</span> <span m='775770'>terms</span> <span m='776370'>of</span>
  <span m='776880'>an</span> <span m='777000'>expansion</span> <span
  m='778890'>of</span> <span m='779490'>a</span> <span m='779580'>form</span>
  <span m='780870'>which,</span> <span m='783000'>at</span> <span
  m='783090'>least</span> <span m='783390'>under</span> <span
  m='783840'>certain</span> <span m='784230'>simple</span> <span
  m='784590'>conditions,</span> <span m='786490'>is</span> <span
  m='787330'>a</span> <span m='787480'>sum</span> <span m='788740'>of</span>
  <span m='788950'>terms</span> <span m='789760'>of</span> <span
  m='789940'>the</span> <span m='790030'>form</span> <span m='790990'>of</span>
  <span m='791320'>a</span> <span m='791380'>constant,</span> <span
  m='792520'>Rk</span> <span m='794800'>divided</span> <span
  m='795340'>by</span> <span m='795850'>x</span> <span m='796180'>minus</span>
  <span m='796600'>xk,</span> <span m='798440'>where</span> <span
  m='799030'>the</span> <span m='799220'>x</span> <span m='799490'>minus</span>
  <span m='799850'>xk</span> <span m='801380'>are</span> <span
  m='802040'>the</span> <span m='802160'>roots</span> <span m='802760'>of</span>
  <span m='803330'>the</span> <span m='803450'>denominator</span> <span
  m='804110'>polynomial</span> <span m='805160'>q</span> <span
  m='805430'>of</span> <span m='805550'>x.</span> <span m='806690'>And</span>
  <span m='807530'>these</span> <span m='807770'>coefficients</span> <span
  m='808940'>are</span> <span m='809150'>referred</span> <span
  m='809570'>to</span> <span m='810110'>as</span> <span m='810770'>the</span>
  <span m='810890'>residues.</span> </p><p><span m='812860'>Now</span> <span
  m='813820'>to</span> <span m='813940'>expand</span> <span
  m='815020'>this</span> <span m='815230'>rational</span> <span
  m='815710'>function</span> <span m='816610'>in</span> <span
  m='816760'>this</span> <span m='816970'>form</span> <span
  m='820290'>without</span> <span m='820770'>additional</span> <span
  m='821280'>terms,</span> <span m='822570'>I</span> <span
  m='822660'>need</span> <span m='823050'>to</span> <span
  m='823410'>apply</span> <span m='824160'>the</span> <span
  m='824250'>restriction,</span> <span m='825180'>which</span> <span
  m='825420'>I'll</span> <span m='825540'>do</span> <span m='826080'>for</span>
  <span m='826200'>the</span> <span m='826290'>purposes</span> <span
  m='826860'>of</span> <span m='826950'>this</span> <span
  m='827160'>lecture,</span> <span m='828910'>that</span> <span
  m='829660'>the</span> <span m='829960'>order</span> <span m='830440'>of</span>
  <span m='830530'>the</span> <span m='830620'>numerator</span> <span
  m='831130'>polynomial</span> <span m='832570'>is</span> <span
  m='832720'>less</span> <span m='833080'>than</span> <span
  m='833230'>the</span> <span m='833350'>order</span> <span m='833650'>of</span>
  <span m='833770'>the</span> <span m='833860'>denominator</span> <span
  m='834550'>polynomial,</span> <span m='836330'>and</span> <span
  m='836380'>that</span> <span m='836780'>in</span> <span
  m='836860'>addition,</span> <span m='838160'>there</span> <span
  m='838450'>are</span> <span m='838600'>no</span> <span
  m='839290'>multiple</span> <span m='839890'>order</span> <span
  m='840490'>roots</span> <span m='841120'>of</span> <span m='841240'>the</span>
  <span m='841360'>denominator</span> <span m='841960'>polynomial.</span>
  </p><p><span m='842890'>In</span> <span m='843010'>other</span> <span
  m='843220'>words,</span> <span m='844250'>the</span> <span
  m='844270'>denominator</span> <span m='844870'>polynomial</span> <span
  m='845680'>is</span> <span m='845890'>n-th</span> <span
  m='846250'>order,</span> <span m='847510'>then</span> <span
  m='848200'>the</span> <span m='848440'>n</span> <span m='848920'>roots</span>
  <span m='849520'>of</span> <span m='849670'>the</span> <span
  m='849790'>denominator</span> <span m='850390'>polynomial</span> <span
  m='851290'>are</span> <span m='851410'>distinct.</span> <span
  m='853570'>In</span> <span m='854680'>the</span> <span m='854770'>text,</span>
  <span m='855640'>there</span> <span m='856030'>is</span> <span
  m='856240'>the</span> <span m='856330'>more</span> <span
  m='856510'>general</span> <span m='857200'>discussion</span> <span
  m='857980'>of</span> <span m='858130'>the</span> <span
  m='858220'>partial</span> <span m='858580'>fraction</span> <span
  m='859030'>expansion</span> <span m='860380'>when</span> <span
  m='861100'>the</span> <span m='861460'>order</span> <span m='861790'>of</span>
  <span m='861910'>the</span> <span m='861970'>numerator</span> <span
  m='862630'>is</span> <span m='862810'>greater</span> <span
  m='863350'>than</span> <span m='863590'>or</span> <span
  m='863680'>equal</span> <span m='863950'>to</span> <span m='864100'>the</span>
  <span m='864220'>order</span> <span m='864460'>of</span> <span
  m='864550'>the</span> <span m='864670'>denominator</span> <span
  m='865720'>or</span> <span m='866050'>if</span> <span m='866230'>there</span>
  <span m='866440'>are</span> <span m='866500'>multiple</span> <span
  m='866950'>order</span> <span m='867220'>roots.</span> <span
  m='868000'>The</span> <span m='868120'>essential</span> <span
  m='868570'>ideas</span> <span m='869080'>of</span> <span
  m='869200'>course</span> <span m='869530'>don't</span> <span
  m='869770'>change.</span> <span m='870530'>It's</span> <span
  m='871000'>just</span> <span m='871240'>the</span> <span
  m='871330'>mechanics</span> <span m='872140'>of</span> <span
  m='872920'>implementing</span> <span m='873550'>the</span> <span
  m='873670'>expansion</span> <span m='874480'>in</span> <span
  m='874570'>the</span> <span m='874660'>form</span> <span m='874990'>of</span>
  <span m='875050'>the</span> <span m='875170'>expansion.</span> </p><p><span
  m='876100'>So</span> <span m='876310'>for</span> <span m='876430'>this</span>
  <span m='876640'>lecture</span> <span m='877060'>we'll</span> <span
  m='877210'>assume</span> <span m='877780'>that</span> <span
  m='877930'>the</span> <span m='878050'>expansion</span> <span
  m='878660'>simply</span> <span m='879580'>has</span> <span
  m='879790'>terms</span> <span m='880420'>of</span> <span
  m='880600'>this</span> <span m='880840'>form.</span> <span m='884370'>And
  this</span> <span m='884790'>then</span> <span m='885240'>is</span> <span
  m='885450'>referred</span> <span m='885840'>to</span> <span
  m='886200'>as</span> <span m='886440'>the</span> <span
  m='886530'>partial</span> <span m='886920'>fraction</span> <span
  m='887430'>expansion</span> <span m='888510'>of</span> <span
  m='888930'>f</span> <span m='889140'>of</span> <span m='889260'>x.</span>
  <span m='891560'>Now</span> <span m='892010'>how</span> <span
  m='892130'>do</span> <span m='892250'>we</span> <span m='892430'>get</span>
  <span m='893180'>the</span> <span m='893480'>coefficients</span> <span
  m='894530'>Rk</span> <span m='895640'>in</span> <span m='895820'>the</span>
  <span m='895940'>expansion?</span> <span m='897950'>Well</span> <span
  m='898370'>essentially</span> <span m='899090'>by</span> <span
  m='899270'>recognizing</span> <span m='901380'>that</span> <span
  m='902790'>if</span> <span m='903270'>we</span> <span
  m='903450'>multiply</span> <span m='904860'>f</span> <span
  m='905100'>of</span> <span m='905220'>x</span> <span m='906690'>by</span>
  <span m='907380'>one</span> <span m='907680'>of</span> <span
  m='907920'>the</span> <span m='908730'>denominator</span> <span
  m='909450'>factors,</span> <span m='910680'>say</span> <span
  m='911460'>x</span> <span m='911730'>minus</span> <span m='912090'>xr,</span>
  <span m='914170'>and</span> <span m='914290'>evaluate</span> <span
  m='915040'>that</span> <span m='915280'>product</span> <span
  m='916230'>of</span> <span m='916570'>x</span> <span m='916930'>equals</span>
  <span m='917680'>xr.</span> <span m='919870'>Then</span> <span
  m='920800'>relating</span> <span m='921400'>that</span> <span
  m='921880'>to</span> <span m='922030'>this</span> <span m='922270'>sum,</span>
  <span m='923290'>as</span> <span m='923710'>I've</span> <span
  m='923890'>indicated</span> <span m='924490'>here,</span> <span
  m='927070'>when</span> <span m='927250'>k</span> <span m='927730'>is</span>
  <span m='927940'>equal</span> <span m='928330'>to</span> <span
  m='928720'>r,</span> <span m='930430'>these</span> <span m='930700'>two</span>
  <span m='930910'>factors</span> <span m='931510'>cancel</span> <span
  m='931990'>out.</span> </p><p><span m='934460'>When</span> <span
  m='934910'>k</span> <span m='935390'>is</span> <span m='935600'>not</span>
  <span m='935870'>equal</span> <span m='936200'>to</span> <span
  m='936350'>r,</span> <span m='937430'>then</span> <span m='937580'>when</span>
  <span m='937730'>I</span> <span m='937820'>substitute</span> <span
  m='938600'>x</span> <span m='939050'>equals</span> <span m='939410'>xr</span>
  <span m='940670'>in</span> <span m='940850'>here,</span> <span
  m='941870'>then</span> <span m='942440'>this</span> <span
  m='942680'>term</span> <span m='943010'>vanishes.</span> <span
  m='945060'>So</span> <span m='945560'>basically</span> <span
  m='946220'>then,</span> <span m='946790'>what</span> <span
  m='947000'>happens</span> <span m='947630'>inside</span> <span
  m='948170'>this</span> <span m='948350'>sum</span> <span m='950380'>is</span>
  <span m='950620'>that</span> <span m='952670'>the</span> <span
  m='952790'>term</span> <span m='953120'>inside</span> <span
  m='953540'>this</span> <span m='953690'>sum</span> <span m='954710'>is</span>
  <span m='954860'>equal</span> <span m='955190'>to</span> <span
  m='955340'>0</span> <span m='956720'>for</span> <span m='956870'>k</span>
  <span m='957710'>not</span> <span m='957980'>equal</span> <span
  m='958310'>to</span> <span m='958490'>r,</span> <span m='960470'>and</span>
  <span m='961010'>it's</span> <span m='961220'>equal</span> <span
  m='961610'>to</span> <span m='961760'>capital</span> <span
  m='962300'>Rr,</span> <span m='963740'>that</span> <span m='963950'>is</span>
  <span m='964190'>the</span> <span m='964310'>residue</span> <span
  m='965480'>at</span> <span m='966950'>the</span> <span m='967070'>pole,</span>
  <span m='967610'>x</span> <span m='968510'>equals</span> <span
  m='968870'>xr</span> <span m='970250'>when</span> <span m='970580'>k</span>
  <span m='971630'>is</span> <span m='971810'>equal</span> <span
  m='972110'>to</span> <span m='972330'>r.</span> </p><p><span
  m='974090'>So</span> <span m='974960'>consequently,</span> <span
  m='976060'>there's</span> <span m='976250'>only</span> <span
  m='976520'>one</span> <span m='976790'>term</span> <span
  m='977120'>left</span> <span m='977390'>in</span> <span m='977510'>this</span>
  <span m='977660'>sum,</span> <span m='978110'>which</span> <span
  m='978350'>is</span> <span m='979010'>capital</span> <span
  m='979460'>Rr.</span> <span m='980960'>And</span> <span
  m='981080'>therefore</span> <span m='982490'>the</span> <span
  m='982610'>residues,</span> <span m='983420'>that</span> <span
  m='983630'>is</span> <span m='984050'>capital</span> <span
  m='984560'>Rr,</span> <span m='985910'>can</span> <span m='986060'>be</span>
  <span m='986240'>obtained</span> <span m='987950'>by</span> <span
  m='989360'>multiplying</span> <span m='990290'>f</span> <span
  m='990530'>of</span> <span m='990650'>x</span> <span m='991520'>by</span>
  <span m='992030'>x</span> <span m='992330'>minus</span> <span
  m='992720'>xr,</span> <span m='994900'>evaluating</span> <span
  m='995620'>the</span> <span m='995710'>result</span> <span
  m='996160'>at</span> <span m='996310'>x</span> <span m='996550'>equals</span>
  <span m='997000'>xr.</span> <span m='998960'>And</span> <span
  m='999110'>the</span> <span m='999200'>resulting</span> <span
  m='999740'>number</span> <span m='1000460'>is</span> <span
  m='1000640'>the</span> <span m='1000760'>residue</span> <span
  m='1001480'>of</span> <span m='1001660'>f</span> <span m='1001840'>of</span>
  <span m='1001990'>x</span> <span m='1002830'>at</span> <span
  m='1003340'>the</span> <span m='1003460'>pole</span> <span
  m='1004120'>x</span> <span m='1004390'>equals</span> <span
  m='1004720'>xr.</span> <span m='1006550'>That's</span> <span
  m='1007000'>for</span> <span m='1008140'>the</span> <span
  m='1008230'>case</span> <span m='1008740'>of</span> <span
  m='1010000'>simple</span> <span m='1010720'>order</span> <span
  m='1011020'>poles,</span> <span m='1011470'>that</span> <span
  m='1011590'>is</span> <span m='1011740'>first</span> <span
  m='1012100'>order</span> <span m='1012520'>roots</span> <span
  m='1013000'>of</span> <span m='1013150'>the</span> <span
  m='1013240'>denominator</span> <span m='1013900'>polynomial.</span> <span
  m='1015430'>And</span> <span m='1015820'>also</span> <span
  m='1016240'>for</span> <span m='1016390'>the</span> <span
  m='1016480'>case</span> <span m='1016900'>when</span> <span
  m='1017050'>the</span> <span m='1017140'>order</span> <span
  m='1017410'>of</span> <span m='1017500'>the</span> <span
  m='1017590'>numerator</span> <span m='1018040'>polynomial</span> <span
  m='1019330'>is</span> <span m='1019690'>less</span> <span
  m='1019990'>than</span> <span m='1020110'>or</span> <span
  m='1020230'>equal</span> <span m='1020470'>to</span> <span
  m='1020590'>the</span> <span m='1020710'>order</span> <span
  m='1021020'>of</span> <span m='1021070'>the</span> <span
  m='1021190'>denominator</span> <span m='1021820'>polynomial.</span>
  </p><p><span m='1023470'>And</span> <span m='1024069'>just</span> <span
  m='1024250'>store</span> <span m='1024640'>away</span> <span
  m='1025510'>for</span> <span m='1025690'>later,</span> <span
  m='1026079'>because</span> <span m='1026560'>I</span> <span
  m='1026650'>want</span> <span m='1026829'>to</span> <span
  m='1026920'>refer</span> <span m='1027250'>back</span> <span
  m='1027520'>to</span> <span m='1027640'>this</span> <span
  m='1027849'>point,</span> <span m='1028810'>that</span> <span
  m='1029210'>in</span> <span m='1029260'>particular,</span> <span
  m='1030260'>when</span> <span m='1030310'>there</span> <span
  m='1030460'>are</span> <span m='1030490'>multiple</span> <span
  m='1031060'>order</span> <span m='1031300'>poles,</span> <span
  m='1032440'>the</span> <span m='1032560'>evaluation</span> <span
  m='1033280'>of</span> <span m='1033369'>the</span> <span
  m='1033460'>residue</span> <span m='1034060'>is</span> <span
  m='1034180'>somewhat</span> <span m='1034599'>more</span> <span
  m='1034810'>complicated.</span> <span m='1036010'>In</span> <span
  m='1036130'>particular</span> <span m='1036770'>it</span> <span
  m='1036849'>involves</span> <span m='1037420'>computing</span> <span
  m='1037930'>some</span> <span m='1038109'>derivatives,</span> <span
  m='1039099'>et</span> <span m='1039240'>cetera.</span> <span
  m='1039760'>And</span> <span m='1040480'>the</span> <span
  m='1040569'>more</span> <span m='1040930'>the</span> <span
  m='1041050'>higher</span> <span m='1041349'>the</span> <span
  m='1041440'>multiplicity</span> <span m='1042130'>of</span> <span
  m='1042190'>the</span> <span m='1042310'>pole,</span> <span
  m='1043069'>the</span> <span m='1043170'>more</span> <span
  m='1043300'>complicated</span> <span m='1044079'>it</span> <span
  m='1044200'>is.</span> <span m='1045260'>And</span> <span
  m='1045670'>that's</span> <span m='1045910'>a</span> <span
  m='1046000'>point</span> <span m='1046390'>that</span> <span
  m='1046540'>will</span> <span m='1046869'>sneak</span> <span
  m='1047200'>back</span> <span m='1047560'>at</span> <span
  m='1047800'>us</span> <span m='1048099'>toward</span> <span
  m='1048369'>the</span> <span m='1048520'>end</span> <span
  m='1048670'>of</span> <span m='1048790'>the</span> <span
  m='1048880'>lecture.</span> </p><p><span m='1050590'>Now</span> <span
  m='1051250'>this</span> <span m='1051490'>of</span> <span
  m='1051580'>course</span> <span m='1051970'>is</span> <span
  m='1052210'>for</span> <span m='1052750'>a</span> <span
  m='1053050'>general</span> <span m='1053740'>rational</span> <span
  m='1054250'>function.</span> <span m='1055640'>Let's</span> <span
  m='1055900'>apply</span> <span m='1056440'>this</span> <span
  m='1057130'>now</span> <span m='1057640'>to</span> <span
  m='1057790'>the</span> <span m='1057970'>inverse</span> <span
  m='1058340'>z</span> <span m='1058570'>transform.</span> <span
  m='1060890'>Well,</span> <span m='1061730'>we</span> <span
  m='1061880'>know</span> <span m='1062270'>that</span> <span
  m='1062930'>the</span> <span m='1063080'>z</span> <span
  m='1063320'>transform--</span> <span m='1065370'>well</span> <span
  m='1065960'>let's</span> <span m='1066200'>restrict</span> <span
  m='1066650'>ourselves</span> <span m='1067340'>to</span> <span
  m='1067490'>the</span> <span m='1067580'>case</span> <span
  m='1067940'>where</span> <span m='1068060'>the</span> <span
  m='1068150'>z</span> <span m='1068360'>transform</span> <span
  m='1069350'>is</span> <span m='1069770'>a</span> <span
  m='1069860'>rational</span> <span m='1070370'>function</span> <span
  m='1071420'>of</span> <span m='1071600'>z</span> <span m='1072260'>or</span>
  <span m='1072530'>z</span> <span m='1072740'>to</span> <span
  m='1072890'>the</span> <span m='1072980'>minus</span> <span
  m='1073390'>1.</span> <span m='1075030'>And</span> <span
  m='1075440'>consequently</span> <span m='1076700'>we</span> <span
  m='1076940'>can,</span> <span m='1078840'>referring</span> <span
  m='1079350'>back</span> <span m='1080130'>to</span> <span
  m='1080640'>the</span> <span m='1080760'>general</span> <span
  m='1081150'>notion</span> <span m='1081720'>of</span> <span
  m='1081870'>the</span> <span m='1081990'>partial</span> <span
  m='1082350'>fraction</span> <span m='1082860'>expansion,</span> <span
  m='1084390'>either</span> <span m='1084780'>think</span> <span
  m='1085230'>of</span> <span m='1085410'>the</span> <span
  m='1085530'>variable</span> <span m='1086340'>z</span> <span
  m='1087720'>as</span> <span m='1088140'>what</span> <span
  m='1088330'>we're</span> <span m='1088590'>calling</span> <span
  m='1089010'>x</span> <span m='1089310'>over</span> <span
  m='1089580'>there,</span> <span m='1091390'>in</span> <span
  m='1091410'>which</span> <span m='1091650'>case</span> <span
  m='1092100'>we</span> <span m='1092310'>have</span> <span
  m='1092490'>an</span> <span m='1092610'>expansion</span> <span
  m='1093630'>of</span> <span m='1094230'>the z</span> <span
  m='1094560'>transform</span> <span m='1096180'>in</span> <span
  m='1096330'>the</span> <span m='1096450'>form</span> <span
  m='1097170'>of</span> <span m='1097860'>the</span> <span
  m='1097950'>sum</span> <span m='1098400'>on</span> <span m='1098580'>k</span>
  <span m='1099150'>of</span> <span m='1099360'>ak</span> <span
  m='1100710'>divided</span> <span m='1101250'>by</span> <span
  m='1101850'>z</span> <span m='1102180'>minus</span> <span
  m='1102660'>little</span> <span m='1102910'>ak,</span> <span
  m='1104130'>where</span> <span m='1104340'>the</span> <span
  m='1104460'>little</span> <span m='1104670'>ak's</span> <span
  m='1105550'>are</span> <span m='1105720'>the</span> <span
  m='1105890'>poles,</span> <span m='1106860'>and</span> <span
  m='1106950'>the</span> <span m='1107040'>capital</span> <span
  m='1107520'>Ak's</span> <span m='1108210'>are</span> <span
  m='1108270'>the</span> <span m='1108410'>residues.</span> </p><p><span
  m='1110550'>Alternatively,</span> <span m='1111780'>if</span> <span
  m='1112830'>we</span> <span m='1113040'>interpret</span> <span
  m='1113550'>z</span> <span m='1113820'>to</span> <span m='1113980'>the</span>
  <span m='1114060'>minus</span> <span m='1114420'>1</span> <span
  m='1114720'>as</span> <span m='1114940'>x,</span> <span
  m='1116610'>then</span> <span m='1117360'>we</span> <span
  m='1117480'>can</span> <span m='1117810'>expand</span> <span
  m='1118470'>x</span> <span m='1118800'>of</span> <span m='1118920'>z</span>
  <span m='1119460'>in</span> <span m='1119640'>the</span> <span
  m='1119730'>form</span> <span m='1120390'>of</span> <span
  m='1121290'>some</span> <span m='1121530'>other</span> <span
  m='1121800'>residues</span> <span m='1123070'>Bk</span> <span
  m='1125030'>divided</span> <span m='1125570'>by</span> <span
  m='1127010'>z</span> <span m='1127280'>to</span> <span m='1127400'>the</span>
  <span m='1127520'>minus</span> <span m='1127920'>1</span> <span
  m='1128360'>minus</span> <span m='1129500'>some</span> <span
  m='1130900'>coefficient,</span> <span m='1131810'>little</span> <span
  m='1132050'>bk.</span> <span m='1132950'>Or</span> <span m='1133190'>we</span>
  <span m='1133340'>can</span> <span m='1133490'>rewrite</span> <span
  m='1133970'>that</span> <span m='1134660'>as</span> <span
  m='1134900'>capital</span> <span m='1135350'>Bk</span> <span
  m='1136520'>divided</span> <span m='1137000'>by</span> <span
  m='1137210'>1</span> <span m='1137510'>minus</span> <span
  m='1137960'>ak</span> <span m='1138860'>z</span> <span m='1139250'>to</span>
  <span m='1139370'>the</span> <span m='1139490'>minus</span> <span
  m='1139880'>1.</span> <span m='1140940'>So</span> <span
  m='1141080'>here</span> <span m='1141410'>we're</span> <span
  m='1141950'>expanding</span> <span m='1142910'>in</span> <span
  m='1143030'>terms</span> <span m='1143630'>of--</span> <span
  m='1145280'>we're</span> <span m='1145500'>treating</span> <span
  m='1146060'>the</span> <span m='1146150'>z</span> <span
  m='1146330'>transform</span> <span m='1146780'>as</span> <span
  m='1146870'>a</span> <span m='1146930'>rational</span> <span
  m='1147320'>function</span> <span m='1147680'>in</span> <span
  m='1147770'>z.</span> <span m='1148880'>Here</span> <span
  m='1149090'>we're</span> <span m='1149240'>treating</span> <span
  m='1149600'>the</span> <span m='1149690'>z</span> <span
  m='1149870'>transform</span> <span m='1150590'>as</span> <span
  m='1150740'>a</span> <span m='1150800'>rational</span> <span
  m='1151250'>function</span> <span m='1151970'>in</span> <span
  m='1152030'>z</span> <span m='1152240'>to</span> <span m='1152390'>the</span>
  <span m='1152480'>minus</span> <span m='1152860'>1.</span> </p><p><span
  m='1155090'>So</span> <span m='1156560'>what</span> <span
  m='1156800'>does</span> <span m='1156950'>the</span> <span
  m='1157070'>method</span> <span m='1157400'>consist</span> <span
  m='1157910'>of?</span> <span m='1158150'>Well</span> <span
  m='1158330'>the</span> <span m='1158420'>method</span> <span
  m='1158750'>consists</span> <span m='1159500'>of</span> <span
  m='1160190'>expanding</span> <span m='1160970'>x</span> <span
  m='1161210'>of</span> <span m='1161330'>z</span> <span m='1162920'>in</span>
  <span m='1163070'>terms</span> <span m='1163520'>of</span> <span
  m='1163640'>simple</span> <span m='1164090'>terms</span> <span
  m='1164510'>like</span> <span m='1164810'>this,</span> <span
  m='1166190'>and</span> <span m='1166340'>then</span> <span
  m='1166520'>using</span> <span m='1166910'>the</span> <span
  m='1167030'>inspection</span> <span m='1167690'>method</span> <span
  m='1168650'>to</span> <span m='1168800'>recognize</span> <span
  m='1169910'>what</span> <span m='1170120'>the</span> <span
  m='1170270'>inverse</span> <span m='1170930'>transform</span> <span
  m='1171710'>is</span> <span m='1172880'>for</span> <span
  m='1173330'>each</span> <span m='1173600'>of</span> <span
  m='1173690'>the</span> <span m='1173840'>individual</span> <span
  m='1174470'>terms.</span> <span m='1175670'>To</span> <span
  m='1175760'>get</span> <span m='1176330'>the</span> <span
  m='1176420'>final</span> <span m='1176780'>sequence</span> <span
  m='1177320'>then,</span> <span m='1177710'>we</span> <span
  m='1177950'>add</span> <span m='1178190'>those</span> <span
  m='1178490'>up.</span> <span m='1178730'>That</span> <span
  m='1178940'>is,</span> <span m='1179480'>we've</span> <span
  m='1179630'>expressed</span> <span m='1180080'>the</span> <span
  m='1180200'>z</span> <span m='1180380'>transform</span> <span
  m='1181040'>as</span> <span m='1181160'>a</span> <span m='1181220'>sum</span>
  <span m='1181610'>of</span> <span m='1181700'>simple</span> <span
  m='1182360'>factors.</span> <span m='1183990'>So</span> <span
  m='1184250'>the</span> <span m='1184370'>sequence,</span> <span
  m='1185780'>the</span> <span m='1185900'>original</span> <span
  m='1186200'>sequence,</span> <span m='1186910'>we</span> <span
  m='1187070'>can</span> <span m='1187220'>express</span> <span
  m='1187760'>as</span> <span m='1187970'>the</span> <span
  m='1188060'>sum</span> <span m='1188660'>of</span> <span
  m='1189380'>the</span> <span m='1189590'>inverse</span> <span
  m='1190060'>z</span> <span m='1190220'>transform</span> <span
  m='1191180'>obtained</span> <span m='1191540'>by</span> <span
  m='1191690'>the</span> <span m='1191810'>expect</span> <span
  m='1192320'>inspection</span> <span m='1193130'>method</span> <span
  m='1193850'>of</span> <span m='1194060'>each</span> <span
  m='1194270'>of</span> <span m='1194330'>the</span> <span
  m='1194480'>individual</span> <span m='1195020'>factors.</span> </p><p><span
  m='1196900'>All</span> <span m='1197000'>right.</span> <span
  m='1197100'>Let's</span> <span m='1197150'>just</span> <span
  m='1197360'>work</span> <span m='1197690'>a</span> <span
  m='1197900'>simple</span> <span m='1198320'>example</span> <span
  m='1199430'>to</span> <span m='1199910'>show</span> <span
  m='1200180'>you</span> <span m='1200330'>what</span> <span
  m='1200480'>the</span> <span m='1200540'>mechanics</span> <span
  m='1201140'>are</span> <span m='1201380'>of</span> <span
  m='1201500'>this</span> <span m='1201980'>and</span> <span
  m='1202220'>how</span> <span m='1202430'>it</span> <span
  m='1202520'>works</span> <span m='1202880'>out.</span> <span
  m='1203960'>Let's</span> <span m='1204170'>take</span> <span
  m='1204560'>an</span> <span m='1204650'>example</span> <span
  m='1205490'>where</span> <span m='1206030'>x</span> <span
  m='1206330'>of</span> <span m='1206450'>z</span> <span m='1207950'>is</span>
  <span m='1208550'>1</span> <span m='1208820'>over</span> <span
  m='1209720'>1</span> <span m='1209930'>minus</span> <span
  m='1210320'>1/2</span> <span m='1210980'>z</span> <span m='1211220'>to</span>
  <span m='1211370'>the</span> <span m='1211460'>minus</span> <span
  m='1211880'>1</span> <span m='1212780'>times</span> <span m='1213170'>1</span>
  <span m='1213410'>minus</span> <span m='1213740'>1/4</span> <span
  m='1214250'>z</span> <span m='1214490'>to</span> <span m='1214610'>the</span>
  <span m='1214730'>minus</span> <span m='1215210'>1</span> <span
  m='1216470'>with</span> <span m='1216890'>a</span> <span
  m='1216950'>region</span> <span m='1217310'>of</span> <span
  m='1217430'>convergence</span> <span m='1218630'>which</span> <span
  m='1219050'>I'll</span> <span m='1219230'>take</span> <span
  m='1219770'>as</span> <span m='1220400'>the</span> <span
  m='1220490'>magnitude</span> <span m='1221060'>of</span> <span
  m='1221180'>z</span> <span m='1221690'>greater</span> <span
  m='1222110'>than</span> <span m='1222290'>a</span> <span
  m='1222350'>half.</span> <span m='1223990'>This</span> <span
  m='1224200'>has</span> <span m='1224410'>two</span> <span
  m='1224620'>poles</span> <span m='1225070'>of</span> <span
  m='1225160'>course.</span> <span m='1225610'>One at z</span> <span
  m='1226000'>equals</span> <span m='1226390'>1/2,</span> <span
  m='1227260'>the</span> <span m='1227380'>other</span> <span m='1227800'>at z
  equals</span> <span m='1228280'>1/4.</span> <span m='1229360'>And</span> <span
  m='1229690'>the</span> <span m='1229780'>region</span> <span
  m='1230080'>of</span> <span m='1230170'>convergence</span> <span
  m='1230890'>is</span> <span m='1231040'>outside</span> <span
  m='1231460'>the</span> <span m='1231610'>outermost</span> <span
  m='1232090'>pole.</span> <span m='1232940'>So</span> <span
  m='1233020'>what</span> <span m='1233140'>we</span> <span
  m='1233290'>expect</span> <span m='1233650'>to</span> <span
  m='1233770'>get</span> <span m='1233950'>is</span> <span m='1234070'>a</span>
  <span m='1234160'>right</span> <span m='1234360'>sided</span> <span
  m='1234730'>sequence.</span> </p><p><span m='1236590'>And</span> <span
  m='1236690'>let's</span> <span m='1236930'>work</span> <span
  m='1237230'>this</span> <span m='1237500'>one</span> <span
  m='1238430'>by</span> <span m='1239510'>treating</span> <span
  m='1240350'>the</span> <span m='1240500'>variable</span> <span
  m='1241100'>x</span> <span m='1242180'>in</span> <span m='1242270'>our</span>
  <span m='1242390'>previous</span> <span m='1242900'>discussion</span> <span
  m='1244040'>as</span> <span m='1244720'>z</span> <span m='1245060'>to</span>
  <span m='1245210'>the</span> <span m='1245330'>minus</span> <span
  m='1245690'>1.</span> <span m='1246110'>And obviously,</span> <span
  m='1246620'>it</span> <span m='1246710'>doesn't</span> <span
  m='1247040'>matter</span> <span m='1247850'>which</span> <span
  m='1248060'>one</span> <span m='1248270'>we</span> <span
  m='1248390'>use.</span> <span m='1248900'>Although</span> <span
  m='1249590'>it</span> <span m='1249710'>turns</span> <span
  m='1250070'>out</span> <span m='1250700'>actually</span> <span
  m='1251240'>that</span> <span m='1251750'>depending</span> <span
  m='1252110'>on</span> <span m='1252230'>how</span> <span
  m='1252410'>you</span> <span m='1252560'>pick</span> <span
  m='1252840'>it,</span> <span m='1253370'>you</span> <span
  m='1253490'>either</span> <span m='1253850'>end</span> <span
  m='1254150'>up</span> <span m='1254450'>with</span> <span m='1255080'>a</span>
  <span m='1255140'>numerator</span> <span m='1255650'>polynomial</span> <span
  m='1256310'>whose</span> <span m='1256520'>order</span> <span
  m='1256790'>is</span> <span m='1256910'>greater</span> <span
  m='1257240'>than</span> <span m='1257420'>the</span> <span
  m='1257510'>denominator</span> <span m='1258110'>polynomial,</span> <span
  m='1258950'>or</span> <span m='1259130'>the</span> <span
  m='1259250'>other</span> <span m='1259430'>way</span> <span
  m='1259610'>around.</span> </p><p><span m='1262690'>OK.</span> <span
  m='1263150'>Well,</span> <span m='1263890'>so</span> <span
  m='1265200'>we</span> <span m='1265350'>want</span> <span
  m='1265830'>then</span> <span m='1266490'>to</span> <span
  m='1266640'>expand</span> <span m='1267780'>this</span> <span
  m='1268080'>z</span> <span m='1268290'>transform</span> <span
  m='1269880'>in</span> <span m='1270030'>terms</span> <span
  m='1270660'>of</span> <span m='1272420'>a</span> <span m='1273140'>sum</span>
  <span m='1273710'>of</span> <span m='1273920'>factors.</span> <span
  m='1274700'>And</span> <span m='1274850'>let's</span> <span
  m='1275090'>just</span> <span m='1276080'>rewrite</span> <span
  m='1276680'>this</span> <span m='1277820'>to</span> <span
  m='1277940'>make</span> <span m='1278180'>things</span> <span
  m='1278510'>a</span> <span m='1278570'>little</span> <span
  m='1278810'>clearer</span> <span m='1281140'>by</span> <span
  m='1281680'>multiplying</span> <span m='1282590'>denominator</span> <span
  m='1283960'>and</span> <span m='1284110'>numerator</span> <span
  m='1285250'>by</span> <span m='1285700'>2,</span> <span m='1286930'>by</span>
  <span m='1287080'>minus</span> <span m='1287500'>2</span> <span
  m='1287740'>rather,</span> <span m='1288620'>and</span> <span
  m='1288730'>then</span> <span m='1288880'>also</span> <span
  m='1289300'>by</span> <span m='1289510'>minus</span> <span
  m='1289990'>4.</span> <span m='1290830'>We</span> <span m='1290950'>can</span>
  <span m='1291100'>simply</span> <span m='1291490'>rewrite</span> <span
  m='1291970'>this</span> <span m='1292270'>as</span> <span m='1292510'>8</span>
  <span m='1293020'>divided</span> <span m='1293500'>by</span> <span
  m='1293770'>z</span> <span m='1293980'>to</span> <span
  m='1294190'>minus</span> <span m='1294520'>1</span> <span
  m='1294760'>minus</span> <span m='1295150'>2</span> <span
  m='1296260'>times</span> <span m='1296890'>z</span> <span
  m='1297100'>to</span> <span m='1297220'>the</span> <span
  m='1297310'>minus</span> <span m='1297670'>1</span> <span
  m='1297880'>minus</span> <span m='1298240'>4.</span> <span
  m='1299110'>So</span> <span m='1299440'>that it's</span> <span
  m='1299620'>more</span> <span m='1299890'>in</span> <span
  m='1299980'>the</span> <span m='1300070'>form</span> <span
  m='1300610'>of</span> <span m='1301030'>x</span> <span
  m='1301630'>minus</span> <span m='1302390'>a</span> <span
  m='1302530'>constant</span> <span m='1303520'>times</span> <span
  m='1304240'>x</span> <span m='1304540'>minus</span> <span
  m='1304930'>another</span> <span m='1305230'>constant.</span> </p><p><span
  m='1307960'>All</span> <span m='1308050'>right.</span> <span
  m='1308560'>Well,</span> <span m='1309220'>so</span> <span
  m='1310330'>here</span> <span m='1310600'>then</span> <span
  m='1311020'>we</span> <span m='1311230'>have</span> <span
  m='1311410'>the</span> <span m='1311500'>z</span> <span
  m='1311740'>transform</span> <span m='1313480'>that</span> <span
  m='1313690'>we</span> <span m='1313840'>want</span> <span
  m='1314050'>to</span> <span m='1314140'>expand</span> <span
  m='1314630'>in</span> <span m='1314710'>a</span> <span
  m='1314740'>partial</span> <span m='1315160'>fraction</span> <span
  m='1315640'>expansion</span> <span m='1317780'>in</span> <span
  m='1317930'>terms</span> <span m='1318560'>of</span> <span
  m='1319370'>treating</span> <span m='1320150'>z</span> <span
  m='1320390'>to</span> <span m='1320510'>the</span> <span
  m='1320600'>minus</span> <span m='1321000'>1</span> <span
  m='1321310'>as</span> <span m='1321620'>the</span> <span
  m='1321710'>complex</span> <span m='1322430'>variable</span> <span
  m='1323030'>x</span> <span m='1323300'>in</span> <span m='1323390'>the</span>
  <span m='1323480'>expansion.</span> <span m='1326210'>We</span> <span
  m='1326330'>have</span> <span m='1326900'>two</span> <span
  m='1327110'>poles,</span> <span m='1327980'>two</span> <span
  m='1328190'>roots</span> <span m='1328520'>of</span> <span
  m='1328640'>the</span> <span m='1328730'>denominator</span> <span
  m='1329360'>polynomial,</span> <span m='1330460'>one</span> <span
  m='1330720'>at</span> <span m='1330860'>z</span> <span m='1331070'>to</span>
  <span m='1331190'>the</span> <span m='1331310'>minus</span> <span
  m='1331640'>1</span> <span m='1331820'>equals</span> <span
  m='1332180'>2,</span> <span m='1333260'>the</span> <span
  m='1333410'>other</span> <span m='1333680'>at</span> <span
  m='1333760'>z</span> <span m='1333920'>the</span> <span
  m='1334150'>minus</span> <span m='1334490'>1</span> <span
  m='1334670'>equals</span> <span m='1335000'>4.</span> <span
  m='1336260'>So</span> <span m='1336710'>we</span> <span
  m='1336860'>need</span> <span m='1337070'>to</span> <span
  m='1337190'>calculate</span> <span m='1337790'>the</span> <span
  m='1337910'>residues</span> <span m='1338660'>at</span> <span
  m='1338780'>each</span> <span m='1338960'>of</span> <span
  m='1339020'>those</span> <span m='1339320'>roots.</span> <span
  m='1340930'>To</span> <span m='1341050'>calculate</span> <span
  m='1341650'>the</span> <span m='1341770'>residue</span> <span
  m='1342850'>at</span> <span m='1343510'>z</span> <span m='1343810'>to</span>
  <span m='1343900'>the</span> <span m='1343990'>minus</span> <span
  m='1344440'>1</span> <span m='1344770'>equals</span> <span
  m='1345250'>2,</span> <span m='1346510'>what</span> <span
  m='1346690'>are</span> <span m='1346750'>the</span> <span
  m='1346870'>steps?</span> </p><p><span m='1347650'>Well,</span> <span
  m='1349470'>we</span> <span m='1350190'>multiply</span> <span
  m='1351450'>this</span> <span m='1352170'>by</span> <span m='1352500'>z</span>
  <span m='1352660'>to</span> <span m='1352860'>the</span> <span
  m='1352950'>minus</span> <span m='1353340'>1</span> <span
  m='1353580'>minus</span> <span m='1353950'>2.</span> <span
  m='1354810'>That</span> <span m='1354990'>is,</span> <span
  m='1355260'>x</span> <span m='1355560'>minus</span> <span m='1355980'>2</span>
  <span m='1356430'>where</span> <span m='1356910'>x</span> <span
  m='1357690'>we're</span> <span m='1357990'>interpreting</span> <span
  m='1358320'>as</span> <span m='1358650'>z</span> <span m='1358890'>to</span>
  <span m='1359010'>the</span> <span m='1359130'>minus</span> <span
  m='1359520'>1.</span> <span m='1360960'>And</span> <span
  m='1361080'>then</span> <span m='1361530'>evaluate</span> <span
  m='1362820'>the</span> <span m='1362910'>result</span> <span
  m='1364260'>at</span> <span m='1364760'>z</span> <span m='1365030'>to</span>
  <span m='1365160'>the</span> <span m='1365280'>minus</span> <span
  m='1365700'>1</span> <span m='1367020'>equals</span> <span
  m='1367440'>2.</span> <span m='1369700'>Well</span> <span
  m='1370060'>obviously</span> <span m='1370840'>of</span> <span
  m='1370930'>course,</span> <span m='1372650'>this</span> <span
  m='1372950'>term</span> <span m='1374120'>cancels</span> <span
  m='1374630'>out</span> <span m='1374840'>that</span> <span
  m='1375110'>term.</span> <span m='1377550'>And</span> <span
  m='1377730'>we</span> <span m='1377820'>want</span> <span
  m='1378000'>to</span> <span m='1378060'>do</span> <span
  m='1378210'>that</span> <span m='1378480'>before</span> <span
  m='1378900'>we</span> <span m='1379050'>substitute</span> <span
  m='1379590'>z</span> <span m='1379780'>to</span> <span m='1379870'>the</span>
  <span m='1379980'>minus</span> <span m='1380310'>1</span> <span
  m='1380490'>equals</span> <span m='1380820'>2.</span> <span
  m='1382260'>And</span> <span m='1382380'>then</span> <span
  m='1382800'>substituting</span> <span m='1383460'>z</span> <span
  m='1383700'>to</span> <span m='1383740'>the</span> <span
  m='1383820'>minus</span> <span m='1384180'>1</span> <span
  m='1384360'>equals</span> <span m='1384690'>2,</span> <span
  m='1385620'>we</span> <span m='1385770'>get</span> <span
  m='1386370'>minus</span> <span m='1386850'>2</span> <span
  m='1387970'>left</span> <span m='1388330'>over</span> <span
  m='1388650'>in</span> <span m='1388740'>the</span> <span
  m='1388810'>denominator</span> <span m='1389910'>divided</span> <span
  m='1390390'>into</span> <span m='1390630'>eight.</span> <span
  m='1391500'>And</span> <span m='1392340'>that's</span> <span m='1392610'>equal
  to</span> <span m='1393030'>minus</span> <span m='1395760'>4.</span> <span
  m='1397480'>So</span> <span m='1397870'>the</span> <span
  m='1398020'>residue</span> <span m='1398590'>then</span> <span
  m='1399880'>at</span> <span m='1400330'>z</span> <span m='1400570'>to</span>
  <span m='1400690'>the</span> <span m='1400780'>minus</span> <span
  m='1401140'>1</span> <span m='1401320'>equals</span> <span
  m='1401710'>2</span> <span m='1402910'>is</span> <span
  m='1403090'>equal</span> <span m='1403420'>to</span> <span
  m='1404020'>minus</span> <span m='1404350'>4.</span> </p><p><span
  m='1406650'>Similarly,</span> <span m='1407110'>to</span> <span
  m='1407620'>calculate</span> <span m='1408220'>the</span> <span
  m='1408340'>residue</span> <span m='1409150'>at</span> <span
  m='1409960'>the</span> <span m='1410080'>root</span> <span
  m='1410320'>z</span> <span m='1410530'>to</span> <span m='1410680'>the</span>
  <span m='1410770'>minus</span> <span m='1411130'>1</span> <span
  m='1411310'>equals</span> <span m='1411640'>4,</span> <span
  m='1413140'>we</span> <span m='1413260'>multiply</span> <span
  m='1414040'>by</span> <span m='1414880'>z to the</span> <span
  m='1415300'>minus</span> <span m='1415630'>1</span> <span
  m='1415870'>minus</span> <span m='1416260'>4.</span> <span
  m='1417470'>Then</span> <span m='1417910'>these</span> <span
  m='1418180'>two</span> <span m='1418330'>terms</span> <span
  m='1418720'>will</span> <span m='1418840'>cancel</span> <span
  m='1419350'>out.</span> <span m='1421440'>Evaluate</span> <span
  m='1422160'>the</span> <span m='1422250'>resulting</span> <span
  m='1422790'>expression</span> <span m='1423390'>at</span> <span
  m='1423480'>z</span> <span m='1423660'>to</span> <span m='1423780'>the</span>
  <span m='1423870'>minus</span> <span m='1424230'>1</span> <span
  m='1424410'>equals</span> <span m='1424740'>4.</span> <span
  m='1426060'>So</span> <span m='1426690'>we</span> <span
  m='1426900'>have</span> <span m='1427020'>4</span> <span
  m='1427320'>minus</span> <span m='1427680'>2</span> <span
  m='1427920'>is</span> <span m='1428070'>2</span> <span m='1428370'>and</span>
  <span m='1428460'>to</span> <span m='1428610'>8</span> <span
  m='1429030'>is</span> <span m='1429180'>4.</span> <span m='1430350'>And</span>
  <span m='1430500'>the</span> <span m='1430590'>residue</span> <span
  m='1431100'>then</span> <span m='1431720'>at</span> <span m='1431900'>z</span>
  <span m='1432150'>to</span> <span m='1432270'>the</span> <span
  m='1432360'>minus</span> <span m='1432660'>1</span> <span
  m='1432780'>equals</span> <span m='1433080'>4,</span> <span
  m='1433800'>the</span> <span m='1433920'>residue</span> <span
  m='1434520'>is</span> <span m='1434910'>equal</span> <span
  m='1435210'>to</span> <span m='1435360'>4.</span> <span
  m='1437010'>Consequently,</span> <span m='1438690'>the</span> <span
  m='1438870'>partial</span> <span m='1439350'>fraction</span> <span
  m='1439800'>expansion</span> <span m='1440880'>for</span> <span
  m='1441270'>x</span> <span m='1441600'>of</span> <span m='1441720'>z,</span>
  <span m='1442080'>for</span> <span m='1442200'>this</span> <span
  m='1442410'>x</span> <span m='1442710'>of</span> <span m='1442790'>z,</span>
  <span m='1444090'>is</span> <span m='1445410'>minus</span> <span
  m='1445910'>4,</span> <span m='1447540'>minus</span> <span
  m='1447930'>4,</span> <span m='1449230'>over</span> <span m='1449620'>z</span>
  <span m='1449850'>to</span> <span m='1450000'>the</span> <span
  m='1450090'>minus</span> <span m='1450420'>1</span> <span
  m='1450900'>minus</span> <span m='1451320'>2</span> <span
  m='1452850'>plus</span> <span m='1453510'>4</span> <span
  m='1454500'>over</span> <span m='1455020'>z</span> <span m='1455190'>to</span>
  <span m='1455430'>the</span> <span m='1455520'>minus</span> <span
  m='1455910'>1</span> <span m='1456570'>minus</span> <span
  m='1456930'>4.</span> </p><p><span m='1458500'>Well</span> <span
  m='1458850'>finally,</span> <span m='1459270'>let's</span> <span
  m='1459540'>just</span> <span m='1459960'>put</span> <span
  m='1460140'>this</span> <span m='1460350'>back</span> <span
  m='1460710'>in</span> <span m='1460800'>a</span> <span m='1460860'>form</span>
  <span m='1461760'>that</span> <span m='1463050'>is</span> <span
  m='1463290'>more</span> <span m='1463590'>the</span> <span
  m='1463710'>form</span> <span m='1464040'>that</span> <span
  m='1464190'>we're</span> <span m='1464610'>used</span> <span
  m='1464910'>to</span> <span m='1465300'>looking</span> <span
  m='1465630'>at</span> <span m='1465690'>the</span> <span m='1465810'>z</span>
  <span m='1465990'>transform</span> <span m='1466870'>in.</span> <span
  m='1468106'>In</span> <span m='1468580'>particular</span> <span
  m='1469450'>multiplying</span> <span m='1471220'>this</span> <span
  m='1471490'>piece,</span> <span m='1471970'>numerator</span> <span
  m='1472450'>and</span> <span m='1472540'>denominator,</span> <span
  m='1473170'>by</span> <span m='1473350'>minus</span> <span
  m='1473800'>1/2,</span> <span m='1474880'>we</span> <span
  m='1475120'>get</span> <span m='1475720'>2 over</span> <span
  m='1476350'>1</span> <span m='1476560'>minus</span> <span
  m='1476890'>1/2</span> <span m='1477250'>z</span> <span m='1477430'>to</span>
  <span m='1477590'>the</span> <span m='1477700'>minus</span> <span
  m='1478120'>1.</span> <span m='1479960'>Here,</span> <span
  m='1480650'>multiplying</span> <span m='1481270'>numerator</span> <span
  m='1481790'>and</span> <span m='1481880'>denominator</span> <span
  m='1482600'>by</span> <span m='1482780'>minus</span> <span
  m='1483200'>1/4,</span> <span m='1484280'>we</span> <span
  m='1484400'>get</span> <span m='1484700'>minus</span> <span
  m='1485120'>1</span> <span m='1485570'>over</span> <span m='1485900'>1</span>
  <span m='1486110'>minus</span> <span m='1486440'>1/4</span> <span
  m='1487220'>z</span> <span m='1487460'>to</span> <span m='1487610'>the</span>
  <span m='1487730'>minus</span> <span m='1488090'>1.</span> <span
  m='1490320'>And</span> <span m='1490370'>now</span> <span
  m='1490970'>we've</span> <span m='1491180'>broken</span> <span
  m='1491630'>x</span> <span m='1491870'>of</span> <span m='1491960'>z</span>
  <span m='1492440'>into</span> <span m='1492770'>a</span> <span
  m='1492830'>form</span> <span m='1493670'>that</span> <span
  m='1493910'>allows</span> <span m='1494360'>us</span> <span
  m='1494540'>to</span> <span m='1494660'>use</span> <span
  m='1494930'>the</span> <span m='1495020'>inspection</span> <span
  m='1495650'>method.</span> <span m='1497420'>That</span> <span
  m='1497660'>is,</span> <span m='1498740'>we</span> <span
  m='1498860'>can</span> <span m='1499040'>recognize</span> <span
  m='1499670'>from</span> <span m='1499910'>this--</span> <span
  m='1500510'>remember</span> <span m='1501320'>that</span> <span
  m='1501440'>the</span> <span m='1501530'>region</span> <span
  m='1501860'>of</span> <span m='1501950'>convergence</span> <span
  m='1503360'>was</span> <span m='1503750'>outside</span> <span
  m='1504560'>a</span> <span m='1504650'>circle.</span> <span
  m='1506250'>So</span> <span m='1506750'>we</span> <span
  m='1506930'>want</span> <span m='1507320'>to</span> <span
  m='1507620'>interpret</span> <span m='1508070'>the</span> <span
  m='1508160'>region</span> <span m='1508430'>of</span> <span
  m='1508520'>convergence</span> <span m='1509090'>to</span> <span
  m='1509240'>be</span> <span m='1509360'>the</span> <span
  m='1509480'>same</span> <span m='1510170'>here.</span> </p><p><span
  m='1511430'>So</span> <span m='1511850'>consequently</span> <span
  m='1512660'>for</span> <span m='1512840'>this</span> <span
  m='1513110'>piece</span> <span m='1513800'>we</span> <span
  m='1513980'>end</span> <span m='1514220'>up</span> <span
  m='1514430'>with</span> <span m='1516660'>2</span> <span
  m='1517890'>times</span> <span m='1518760'>1/2</span> <span
  m='1519830'>to</span> <span m='1520080'>the</span> <span m='1520260'>n</span>
  <span m='1521400'>times</span> <span m='1521790'>u</span> <span m='1522030'>of
  n.</span> <span m='1524810'>That's an</span> <span m='1525300'>n.</span> <span
  m='1527760'>And</span> <span m='1528210'>for</span> <span
  m='1528360'>this</span> <span m='1528600'>piece</span> <span
  m='1529530'>we</span> <span m='1529710'>end</span> <span m='1529950'>up</span>
  <span m='1530310'>with</span> <span m='1530610'>minus</span> <span
  m='1531180'>1</span> <span m='1533310'>times</span> <span m='1534930'>a</span>
  <span m='1535020'>quarter</span> <span m='1536370'>to</span> <span
  m='1536490'>the</span> <span m='1536700'>n</span> <span
  m='1537780'>times</span> <span m='1538650'>u</span> <span m='1538860'>of
  n.</span> <span m='1540490'>So</span> <span m='1540930'>by</span> <span
  m='1541140'>breaking</span> <span m='1541650'>x</span> <span
  m='1541890'>of</span> <span m='1541980'>z</span> <span m='1543150'>into</span>
  <span m='1543780'>a</span> <span m='1543870'>sum</span> <span
  m='1544500'>of</span> <span m='1544680'>components,</span> <span
  m='1546480'>simple</span> <span m='1546990'>terms,</span> <span
  m='1548380'>we</span> <span m='1548480'>were</span> <span
  m='1548490'>then</span> <span m='1548790'>able</span> <span
  m='1549450'>to</span> <span m='1549900'>apply</span> <span
  m='1550380'>the</span> <span m='1550500'>inspection</span> <span
  m='1551100'>method</span> <span m='1551910'>to</span> <span
  m='1552030'>each</span> <span m='1552270'>one</span> <span
  m='1552480'>of</span> <span m='1552570'>those</span> <span
  m='1553590'>to</span> <span m='1554520'>get</span> <span
  m='1555000'>the</span> <span m='1555330'>resulting</span> <span
  m='1556290'>z</span> <span m='1556530'>transform</span> <span
  m='1558090'>in</span> <span m='1558510'>a</span> <span
  m='1558690'>closed</span> <span m='1559110'>form</span> <span
  m='1559470'>expression,</span> <span m='1560970'>or</span> <span
  m='1561330'>at</span> <span m='1561450'>least</span> <span
  m='1561690'>the</span> <span m='1561810'>sum</span> <span
  m='1562110'>of</span> <span m='1562200'>some</span> <span
  m='1562410'>closed</span> <span m='1562770'>form</span> <span
  m='1563070'>expression.</span> </p><p><span m='1566650'>All</span> <span
  m='1566710'>right.</span> <span m='1566980'>So</span> <span
  m='1567970'>that</span> <span m='1568450'>then</span> <span
  m='1568870'>is</span> <span m='1569200'>basically</span> <span
  m='1569830'>an</span> <span m='1569920'>extension</span> <span
  m='1570910'>of</span> <span m='1571240'>the</span> <span
  m='1571330'>inspection</span> <span m='1571960'>method.</span> <span
  m='1573010'>When</span> <span m='1573190'>the</span> <span
  m='1573280'>inspection</span> <span m='1573820'>method</span> <span
  m='1574270'>by</span> <span m='1574510'>itself</span> <span
  m='1575230'>doesn't</span> <span m='1575560'>work,</span> <span
  m='1577260'>it's</span> <span m='1577440'>usually</span> <span
  m='1578700'>the</span> <span m='1579000'>partial</span> <span
  m='1579420'>fraction</span> <span m='1579840'>expansion</span> <span
  m='1580470'>method</span> <span m='1581340'>that</span> <span
  m='1581760'>one</span> <span m='1582030'>uses,</span> <span
  m='1583020'>perhaps</span> <span m='1583500'>also</span> <span
  m='1584370'>in</span> <span m='1584730'>conjunction</span> <span
  m='1585780'>with</span> <span m='1586440'>some</span> <span
  m='1586620'>properties</span> <span m='1587400'>of</span> <span
  m='1587490'>the z</span> <span m='1587790'>transform,</span> <span
  m='1588720'>which</span> <span m='1588960'>is</span> <span
  m='1589020'>something</span> <span m='1589350'>that</span> <span
  m='1589440'>will</span> <span m='1589590'>be</span> <span
  m='1589740'>going</span> <span m='1590250'>into</span> <span
  m='1591210'>more</span> <span m='1591720'>in</span> <span
  m='1591840'>the</span> <span m='1591930'>next</span> <span
  m='1592200'>lecture.</span> </p><p><span m='1594640'>Now</span> <span
  m='1594850'>finally,</span> <span m='1595820'>there</span> <span
  m='1596260'>is</span> <span m='1597280'>a</span> <span
  m='1597970'>somewhat</span> <span m='1598480'>more</span> <span
  m='1598690'>formal</span> <span m='1599770'>way</span> <span
  m='1600340'>of</span> <span m='1601390'>evaluating</span> <span
  m='1602110'>the</span> <span m='1602230'>inverse</span> <span
  m='1602515'>z</span> <span m='1602800'>transform.</span> <span
  m='1604360'>And</span> <span m='1604810'>in</span> <span
  m='1604960'>some</span> <span m='1605230'>cases,</span> <span
  m='1606110'>it's</span> <span m='1606190'>important</span> <span
  m='1607180'>to</span> <span m='1607480'>actually</span> <span
  m='1608050'>use</span> <span m='1608410'>this</span> <span
  m='1608620'>to</span> <span m='1608740'>explicitly</span> <span
  m='1609460'>evaluate</span> <span m='1610510'>the</span> <span
  m='1610660'>inverse</span> <span m='1610930'>z</span> <span
  m='1611200'>transform.</span> <span m='1612520'>In</span> <span
  m='1612640'>other</span> <span m='1612880'>cases,</span> <span
  m='1613820'>it's</span> <span m='1613930'>important</span> <span
  m='1615010'>to</span> <span m='1615130'>make</span> <span
  m='1615340'>reference</span> <span m='1616420'>to</span> <span
  m='1616780'>the</span> <span m='1616900'>more</span> <span
  m='1617110'>formal</span> <span m='1617710'>inverse</span> <span
  m='1618370'>transform</span> <span m='1619570'>relationship</span> <span
  m='1620920'>to</span> <span m='1621940'>discuss</span> <span
  m='1622420'>properties</span> <span m='1623050'>of</span> <span
  m='1623170'>the</span> <span m='1623300'>inverse z</span> <span
  m='1623800'>transform.</span> <span m='1624400'>So</span> <span
  m='1624550'>sometimes</span> <span m='1625330'>the</span> <span
  m='1625900'>formal</span> <span m='1627040'>inverse</span> <span
  m='1627610'>transform</span> <span m='1628570'>is</span> <span
  m='1629410'>computationally</span> <span m='1630280'>useful.</span> <span
  m='1631270'>In</span> <span m='1631420'>other</span> <span
  m='1631990'>cases,</span> <span m='1632780'>it's</span> <span
  m='1633430'>useful</span> <span m='1634330'>in</span> <span
  m='1634450'>proving</span> <span m='1634840'>theorems</span> <span
  m='1635410'>or</span> <span m='1635560'>developing</span> <span
  m='1636100'>properties</span> <span m='1636970'>or</span> <span
  m='1637240'>something</span> <span m='1637660'>of</span> <span
  m='1637750'>the</span> <span m='1637840'>sort.</span> </p><p><span
  m='1639360'>Well</span> <span m='1639630'>this</span> <span
  m='1639870'>method,</span> <span m='1640980'>the</span> <span
  m='1641250'>final</span> <span m='1641850'>method</span> <span
  m='1642390'>and</span> <span m='1642690'>the</span> <span
  m='1642750'>most</span> <span m='1642990'>formal</span> <span
  m='1643410'>method,</span> <span m='1644580'>is</span> <span
  m='1645420'>the</span> <span m='1645540'>method</span> <span
  m='1646230'>that</span> <span m='1647160'>I</span> <span
  m='1647280'>refer</span> <span m='1647670'>to</span> <span
  m='1647910'>here</span> <span m='1648360'>as</span> <span
  m='1649410'>contour</span> <span m='1650010'>integration.</span> <span
  m='1652330'>And</span> <span m='1653110'>let</span> <span
  m='1653380'>me</span> <span m='1653680'>basically</span> <span
  m='1654890'>hand</span> <span m='1655260'>it</span> <span
  m='1655480'>to</span> <span m='1655660'>you.</span> <span
  m='1656170'>That</span> <span m='1656320'>is,</span> <span
  m='1658180'>rather</span> <span m='1658510'>than</span> <span
  m='1658690'>go</span> <span m='1658870'>through</span> <span
  m='1659080'>a</span> <span m='1659110'>derivation,</span> <span
  m='1659830'>let</span> <span m='1659980'>me</span> <span
  m='1660130'>just</span> <span m='1660910'>simply</span> <span
  m='1661270'>state</span> <span m='1662230'>what</span> <span
  m='1662860'>the</span> <span m='1663040'>inverse</span> <span
  m='1663295'>z</span> <span m='1663550'>transform</span> <span
  m='1664180'>relationship</span> <span m='1664930'>is.</span> <span
  m='1666190'>In</span> <span m='1666340'>the</span> <span
  m='1666430'>text</span> <span m='1666930'>there</span> <span
  m='1667330'>is</span> <span m='1667960'>a</span> <span
  m='1668050'>derivation</span> <span m='1668890'>of</span> <span
  m='1669130'>this.</span> <span m='1670640'>And</span> <span
  m='1671930'>so</span> <span m='1672290'>for</span> <span
  m='1672830'>the</span> <span m='1672920'>purposes</span> <span
  m='1673400'>of</span> <span m='1673460'>the</span> <span
  m='1673580'>lecture</span> <span m='1673940'>itself,</span> <span
  m='1674460'>let</span> <span m='1674510'>me</span> <span
  m='1674630'>just</span> <span m='1674870'>presented.</span> <span
  m='1676040'>Any</span> <span m='1676220'>objections?</span> <span
  m='1677580'>No.</span> </p><p><span m='1679480'>So</span> <span
  m='1681700'>and</span> <span m='1682180'>then</span> <span
  m='1682450'>also</span> <span m='1683140'>work</span> <span
  m='1683480'>through</span> <span m='1684040'>at</span> <span
  m='1684160'>least</span> <span m='1684400'>one</span> <span
  m='1684580'>example</span> <span m='1686020'>to</span> <span
  m='1686140'>show</span> <span m='1686350'>you</span> <span
  m='1686500'>what</span> <span m='1686650'>the</span> <span
  m='1686740'>mechanics</span> <span m='1687340'>are.</span> <span
  m='1689230'>It's</span> <span m='1689320'>another</span> <span
  m='1689590'>nice</span> <span m='1689830'>thing</span> <span
  m='1690010'>about</span> <span m='1690250'>videotape</span> <span
  m='1690840'>lectures,</span> <span m='1691240'>there</span> <span
  m='1691340'>are</span> <span m='1691390'>never</span> <span
  m='1691630'>any</span> <span m='1691820'>objection.</span> <span
  m='1695580'>OK.</span> <span m='1695900'>Well,</span> <span
  m='1696320'>here</span> <span m='1696560'>it</span> <span
  m='1696650'>is.</span> <span m='1697160'>This</span> <span
  m='1697370'>is</span> <span m='1697490'>the</span> <span
  m='1697610'>inverse</span> <span m='1698050'>z</span> <span
  m='1698210'>transform.</span> <span m='1699020'>What</span> <span
  m='1699170'>does</span> <span m='1699320'>it</span> <span
  m='1699440'>say?</span> <span m='1699950'>It</span> <span
  m='1700040'>says</span> <span m='1700750'>the</span> <span
  m='1700850'>sequence</span> <span m='1701600'>x</span> <span
  m='1701860'>of</span> <span m='1702020'>n</span> <span m='1703740'>is</span>
  <span m='1704340'>1</span> <span m='1704550'>over</span> <span
  m='1704760'>2</span> <span m='1704970'>pi</span> <span m='1705350'>j</span>
  <span m='1706560'>times</span> <span m='1707880'>a</span> <span
  m='1707940'>contour</span> <span m='1708540'>integral,</span> <span
  m='1709870'>which</span> <span m='1709980'>I'll</span> <span
  m='1710130'>return</span> <span m='1710520'>to</span> <span
  m='1710640'>in</span> <span m='1710730'>a</span> <span
  m='1710790'>second,</span> <span m='1711960'>of</span> <span
  m='1712350'>x</span> <span m='1712680'>of z</span> <span
  m='1713160'>times</span> <span m='1713460'>z</span> <span
  m='1713730'>to</span> <span m='1713880'>the</span> <span m='1714060'>n</span>
  <span m='1714270'>minus</span> <span m='1714630'>1</span> <span
  m='1715080'>dz.</span> </p><p><span m='1717530'>If</span> <span
  m='1717650'>you're</span> <span m='1717770'>not</span> <span
  m='1717950'>used</span> <span m='1718190'>to</span> <span
  m='1718280'>looking</span> <span m='1718670'>at</span> <span
  m='1719060'>an</span> <span m='1719180'>inverse</span> <span
  m='1719660'>transform</span> <span m='1720260'>relationship</span> <span
  m='1720980'>like</span> <span m='1721250'>this,</span> <span
  m='1721640'>let</span> <span m='1721820'>me</span> <span
  m='1721940'>just</span> <span m='1722180'>indicate</span> <span
  m='1722630'>that</span> <span m='1722750'>it's</span> <span
  m='1726440'>surprising</span> <span m='1727070'>how</span> <span
  m='1727250'>easy</span> <span m='1727580'>it</span> <span
  m='1727700'>is</span> <span m='1728030'>to</span> <span
  m='1728150'>verify</span> <span m='1728810'>that,</span> <span
  m='1729030'>in</span> <span m='1729050'>fact,</span> <span
  m='1729450'>this</span> <span m='1729560'>is</span> <span
  m='1729770'>the</span> <span m='1729880'>inverse</span> <span
  m='1730290'>z</span> <span m='1730400'>transform</span> <span
  m='1731000'>relationship,</span> <span m='1732170'>basically</span> <span
  m='1733340'>using</span> <span m='1733700'>the</span> <span
  m='1733790'>Cauchy</span> <span m='1734180'>residue</span> <span
  m='1734630'>theorem.</span> <span m='1736270'>But</span> <span
  m='1736660'>this</span> <span m='1736870'>is</span> <span
  m='1737020'>it.</span> <span m='1738620'>This</span> <span
  m='1739040'>is,</span> <span m='1739370'>of</span> <span
  m='1739490'>course,</span> <span m='1739790'>a</span> <span
  m='1739850'>complex</span> <span m='1740450'>function.</span> <span
  m='1742170'>This</span> <span m='1742350'>is</span> <span m='1742470'>a</span>
  <span m='1742530'>complex</span> <span m='1743130'>integral.</span>
  </p><p><span m='1744540'>And</span> <span m='1745260'>the</span> <span
  m='1745350'>important</span> <span m='1745860'>thing</span> <span
  m='1746670'>to</span> <span m='1746790'>straighten</span> <span
  m='1747330'>out</span> <span m='1748290'>is</span> <span
  m='1749130'>this</span> <span m='1749340'>contour</span> <span
  m='1750330'>c.</span> <span m='1751680'>The</span> <span
  m='1751800'>contours</span> <span m='1752330'>c</span> <span
  m='1753510'>is</span> <span m='1754110'>a</span> <span
  m='1754650'>closed</span> <span m='1756030'>contour</span> <span
  m='1757320'>in</span> <span m='1757440'>the</span> <span m='1757500'>z</span>
  <span m='1757710'>plane</span> <span m='1759210'>which</span> <span
  m='1759660'>encircles</span> <span m='1760350'>the</span> <span
  m='1760500'>origin.</span> <span m='1761970'>So</span> <span
  m='1762120'>it's</span> <span m='1762270'>a</span> <span
  m='1762300'>closed</span> <span m='1762690'>contour.</span> <span
  m='1763700'>It</span> <span m='1763800'>encircles</span> <span
  m='1764220'>the</span> <span m='1764350'>origin.</span> <span
  m='1764780'>It's</span> <span m='1764940'>like</span> <span
  m='1765150'>a</span> <span m='1765210'>circle</span> <span
  m='1765990'>that</span> <span m='1766200'>goes</span> <span
  m='1766500'>around</span> <span m='1766770'>the</span> <span
  m='1766920'>origin,</span> <span m='1768840'>with</span> <span
  m='1769050'>another</span> <span m='1769410'>very</span> <span
  m='1769710'>important</span> <span m='1770130'>condition</span> <span
  m='1770670'>on</span> <span m='1770880'>it.</span> <span
  m='1771180'>Which</span> <span m='1771450'>is</span> <span
  m='1771630'>that</span> <span m='1772020'>it</span> <span
  m='1772230'>lies</span> <span m='1773070'>inside</span> <span
  m='1773640'>the</span> <span m='1773760'>region</span> <span
  m='1774090'>of</span> <span m='1774180'>convergence</span> <span
  m='1775050'>of</span> <span m='1775200'>x</span> <span m='1775440'>of</span>
  <span m='1775530'>z.</span> </p><p><span m='1776520'>Well,</span> <span
  m='1776640'>that's</span> <span m='1776880'>not</span> <span
  m='1777060'>surprising,</span> <span m='1777930'>because</span> <span
  m='1779100'>the</span> <span m='1779190'>region</span> <span
  m='1779490'>of</span> <span m='1779580'>convergence</span> <span
  m='1780630'>for</span> <span m='1780840'>x</span> <span m='1781020'>of</span>
  <span m='1781140'>z</span> <span m='1781950'>is</span> <span
  m='1782070'>the</span> <span m='1782190'>only</span> <span
  m='1782430'>place</span> <span m='1782820'>where</span> <span
  m='1782970'>we're</span> <span m='1783180'>allowed</span> <span
  m='1783480'>to</span> <span m='1783600'>stick</span> <span
  m='1783930'>in</span> <span m='1784050'>values</span> <span
  m='1784560'>for</span> <span m='1784710'>z.</span> <span m='1785670'>So</span>
  <span m='1785910'>obviously</span> <span m='1786810'>quote,</span> <span
  m='1788840'>we're</span> <span m='1789320'>not</span> <span
  m='1789560'>allowed</span> <span m='1789980'>to</span> <span
  m='1790130'>look</span> <span m='1790430'>at</span> <span
  m='1791030'>values</span> <span m='1791450'>of</span> <span
  m='1791510'>this</span> <span m='1791750'>integrand</span> <span
  m='1793160'>except</span> <span m='1793970'>where</span> <span
  m='1794390'>x</span> <span m='1794660'>of</span> <span m='1794750'>z</span>
  <span m='1794930'>makes</span> <span m='1795170'>sense,</span> <span
  m='1795530'>that</span> <span m='1795680'>is</span> <span
  m='1795830'>except</span> <span m='1796220'>in</span> <span
  m='1796310'>the</span> <span m='1796400'>region</span> <span
  m='1796670'>of</span> <span m='1796760'>convergence.</span> <span
  m='1797970'>So</span> <span m='1798410'>obviously</span> <span
  m='1799070'>then,</span> <span m='1799310'>we</span> <span
  m='1799460'>have</span> <span m='1799670'>to</span> <span
  m='1799850'>evaluate</span> <span m='1800420'>this</span> <span
  m='1800630'>integral</span> <span m='1801020'>considering</span> <span
  m='1801620'>only</span> <span m='1801890'>values</span> <span
  m='1802340'>of</span> <span m='1802430'>z</span> <span
  m='1802880'>inside</span> <span m='1803330'>the</span> <span
  m='1803450'>region</span> <span m='1803750'>of</span> <span
  m='1803840'>convergence.</span> </p><p><span m='1806660'>So</span> <span
  m='1807530'>contour</span> <span m='1807970'>c</span> <span
  m='1808240'>is</span> <span m='1808360'>a</span> <span
  m='1808420'>closed</span> <span m='1808870'>contour</span> <span
  m='1809590'>in</span> <span m='1809680'>the</span> <span m='1809770'>z</span>
  <span m='1809980'>plane,</span> <span m='1810490'>encircles</span> <span
  m='1811000'>the</span> <span m='1811120'>origin,</span> <span
  m='1812260'>and</span> <span m='1812710'>it</span> <span
  m='1812860'>lies</span> <span m='1813280'>inside</span> <span
  m='1813670'>the</span> <span m='1813760'>region</span> <span
  m='1814060'>of</span> <span m='1814150'>convergence.</span> <span
  m='1816360'>Now</span> <span m='1816860'>for</span> <span m='1817340'>x</span>
  <span m='1817760'>of z,</span> <span m='1818390'>a</span> <span
  m='1818480'>rational</span> <span m='1819320'>function</span> <span
  m='1819770'>of</span> <span m='1819860'>z,</span> <span
  m='1820440'>which</span> <span m='1820820'>are</span> <span
  m='1820940'>the</span> <span m='1821030'>cases</span> <span
  m='1821450'>we've</span> <span m='1821630'>been</span> <span
  m='1821750'>talking</span> <span m='1822200'>about,</span> <span
  m='1823610'>this</span> <span m='1823820'>entire</span> <span
  m='1824300'>integrand</span> <span m='1825080'>is</span> <span
  m='1825260'>a</span> <span m='1825320'>rational</span> <span
  m='1825800'>function.</span> <span m='1828400'>And</span> <span
  m='1829870'>consequently,</span> <span m='1831010'>a</span> <span
  m='1831280'>contour</span> <span m='1831820'>integral</span> <span
  m='1832240'>of</span> <span m='1832330'>this</span> <span
  m='1832540'>type</span> <span m='1834010'>can</span> <span
  m='1835030'>be</span> <span m='1835420'>simply</span> <span
  m='1835990'>evaluated</span> <span m='1837430'>using</span> <span
  m='1838780'>the</span> <span m='1838870'>notion</span> <span
  m='1839710'>of</span> <span m='1840400'>residues.</span> </p><p><span
  m='1841830'>I'll</span> <span m='1842050'>state,</span> <span
  m='1843130'>and</span> <span m='1843280'>hopefully</span> <span
  m='1843760'>this</span> <span m='1843970'>is</span> <span m='1844360'>a</span>
  <span m='1844420'>property</span> <span m='1845380'>of</span> <span
  m='1846430'>complex</span> <span m='1846880'>contour</span> <span
  m='1847300'>integrals</span> <span m='1847840'>that</span> <span
  m='1847990'>you're</span> <span m='1848110'>familiar</span> <span
  m='1848560'>with,</span> <span m='1849400'>that</span> <span
  m='1850990'>the</span> <span m='1851140'>integral</span> <span
  m='1851800'>of</span> <span m='1852460'>a</span> <span
  m='1852640'>rational</span> <span m='1853150'>function</span> <span
  m='1853990'>of</span> <span m='1854140'>that</span> <span
  m='1854320'>type,</span> <span m='1856130'>the</span> <span
  m='1856250'>integral</span> <span m='1856610'>itself</span> <span
  m='1857180'>is</span> <span m='1857360'>2 pi</span> <span m='1857570'>j</span>
  <span m='1858230'>times</span> <span m='1858560'>the</span> <span
  m='1858650'>sum</span> <span m='1858890'>of</span> <span
  m='1858980'>the</span> <span m='1859100'>residues</span> <span
  m='1859880'>inside</span> <span m='1860330'>the</span> <span
  m='1860420'>contour.</span> <span m='1862900'>And</span> <span
  m='1863770'>that</span> <span m='1864010'>2</span> <span m='1864190'>pi</span>
  <span m='1864490'>j</span> <span m='1865360'>cancels</span> <span
  m='1865810'>out</span> <span m='1866000'>as</span> <span m='1866200'>1</span>
  <span m='1866410'>over</span> <span m='1866650'>2 pi</span> <span
  m='1867270'>j.</span> <span m='1867640'>And</span> <span
  m='1868090'>consequently,</span> <span m='1868930'>x</span> <span
  m='1869170'>of</span> <span m='1869320'>n</span> <span m='1869650'>is</span>
  <span m='1869770'>simply</span> <span m='1870250'>the</span> <span
  m='1870370'>sum</span> <span m='1870760'>of</span> <span
  m='1870850'>the</span> <span m='1870970'>residues</span> <span
  m='1871690'>of</span> <span m='1871900'>x</span> <span m='1872170'>of</span>
  <span m='1872290'>z</span> <span m='1873145'>times z</span> <span
  m='1873490'>to</span> <span m='1873640'>the</span> <span m='1873760'>n</span>
  <span m='1873940'>minus</span> <span m='1874330'>1</span> <span
  m='1875740'>at</span> <span m='1875920'>the</span> <span
  m='1876010'>poles</span> <span m='1877150'>inside</span> <span
  m='1877660'>the</span> <span m='1877780'>contour</span> <span
  m='1878330'>c.</span> </p><p><span m='1879950'>The</span> <span
  m='1880040'>poles</span> <span m='1880430'>of</span> <span
  m='1880580'>what?</span> <span m='1881540'>The</span> <span
  m='1881660'>poles</span> <span m='1882410'>not</span> <span
  m='1882800'>of</span> <span m='1883040'>x</span> <span m='1883340'>and</span>
  <span m='1883430'>z</span> <span m='1884030'>only,</span> <span
  m='1885110'>but</span> <span m='1885710'>the</span> <span
  m='1885800'>poles</span> <span m='1886610'>of</span> <span
  m='1887030'>the</span> <span m='1887120'>entire</span> <span
  m='1887640'>integrand.</span> <span m='1888680'>That</span> <span
  m='1888890'>is,</span> <span m='1889640'>x</span> <span m='1889910'>of</span>
  <span m='1890030'>z</span> <span m='1890480'>multiplied</span> <span
  m='1891200'>by</span> <span m='1891380'>z</span> <span m='1891590'>to</span>
  <span m='1891740'>the</span> <span m='1891890'>n</span> <span
  m='1892010'>minus 1.</span> <span m='1892400'>Important</span> <span
  m='1893180'>point,</span> <span m='1894550'>which</span> <span
  m='1894970'>it's</span> <span m='1895210'>important</span> <span
  m='1895660'>to</span> <span m='1895780'>keep</span> <span
  m='1896020'>in</span> <span m='1896110'>mind.</span> <span
  m='1897100'>The</span> <span m='1897220'>integral</span> <span
  m='1898180'>or</span> <span m='1898450'>the</span> <span
  m='1898570'>residues</span> <span m='1899170'>that</span> <span
  m='1899290'>we're</span> <span m='1899410'>looking</span> <span
  m='1899770'>at</span> <span m='1899950'>are</span> <span
  m='1900100'>the</span> <span m='1900190'>residues,</span> <span
  m='1901300'>not</span> <span m='1901510'>just</span> <span
  m='1901720'>of</span> <span m='1901800'>x</span> <span m='1902080'>of</span>
  <span m='1902200'>z,</span> <span m='1903160'>but</span> <span
  m='1903400'>x</span> <span m='1903670'>of</span> <span m='1903790'>z</span>
  <span m='1903970'>multiplied</span> <span m='1904600'>by</span> <span
  m='1904780'>z</span> <span m='1904990'>to</span> <span m='1905140'>the</span>
  <span m='1905290'>n</span> <span m='1905420'>minus</span> <span
  m='1905800'>1.</span> </p><p><span m='1909160'>Another</span> <span
  m='1909640'>statement,</span> <span m='1910580'>just</span> <span
  m='1910760'>tuck</span> <span m='1911010'>it</span> <span
  m='1911100'>away,</span> <span m='1912920'>is</span> <span
  m='1913160'>that</span> <span m='1914030'>this</span> <span
  m='1914600'>is</span> <span m='1914930'>valid</span> <span
  m='1916720'>for</span> <span m='1916900'>both</span> <span
  m='1917230'>n</span> <span m='1917470'>greater</span> <span
  m='1917830'>than</span> <span m='1918010'>zero</span> <span
  m='1918850'>and</span> <span m='1919060'>equal</span> <span
  m='1919420'>to</span> <span m='1919570'>zero</span> <span m='1920230'>and
  n</span> <span m='1920590'>less</span> <span m='1920890'>than</span> <span
  m='1921040'>0.</span> <span m='1922860'>We'll</span> <span
  m='1923010'>see</span> <span m='1923250'>in</span> <span m='1923310'>a</span>
  <span m='1923370'>minute</span> <span m='1923850'>that</span> <span
  m='1925050'>for</span> <span m='1925260'>n</span> <span
  m='1925410'>greater</span> <span m='1925770'>than</span> <span
  m='1925920'>zero,</span> <span m='1926460'>it</span> <span
  m='1926550'>might</span> <span m='1926790'>be</span> <span
  m='1927000'>easier</span> <span m='1927360'>to</span> <span
  m='1927540'>evaluate</span> <span m='1928200'>than</span> <span
  m='1928350'>for</span> <span m='1928530'>n</span> <span
  m='1928650'>less</span> <span m='1928920'>than</span> <span
  m='1929070'>0,</span> <span m='1929490'>depending</span> <span
  m='1929970'>on</span> <span m='1930090'>the</span> <span
  m='1930210'>example.</span> <span m='1931290'>But</span> <span
  m='1932070'>tuck</span> <span m='1932310'>away</span> <span
  m='1932550'>the</span> <span m='1932670'>fact</span> <span
  m='1933420'>that</span> <span m='1933630'>this</span> <span
  m='1933840'>expression</span> <span m='1934500'>is</span> <span
  m='1934710'>a</span> <span m='1934770'>valid</span> <span
  m='1935190'>expression,</span> <span m='1936510'>no</span> <span
  m='1936630'>matter</span> <span m='1936930'>whether</span> <span
  m='1937230'>n</span> <span m='1937590'>is</span> <span
  m='1937770'>positive</span> <span m='1938520'>or</span> <span
  m='1938670'>negative</span> <span m='1939270'>or</span> <span
  m='1939420'>of</span> <span m='1939510'>course</span> <span
  m='1939780'>zero.</span> </p><p><span m='1942000'>All</span> <span
  m='1942090'>right.</span> <span m='1942480'>Let's</span> <span
  m='1942960'>look</span> <span m='1943170'>at</span> <span
  m='1943260'>the</span> <span m='1943350'>mechanics</span> <span
  m='1944130'>of</span> <span m='1944790'>evaluating</span> <span
  m='1945510'>the</span> <span m='1945630'>inverse</span> <span
  m='1945900'>z</span> <span m='1946170'>transform</span> <span
  m='1946830'>this</span> <span m='1947040'>way.</span> <span
  m='1948360'>Let's</span> <span m='1948600'>return</span> <span
  m='1949110'>to</span> <span m='1950070'>the</span> <span
  m='1950190'>example</span> <span m='1951540'>x</span> <span
  m='1951810'>of</span> <span m='1951930'>z</span> <span
  m='1952410'>equals</span> <span m='1952860'>1</span> <span
  m='1953130'>over</span> <span m='1953700'>1</span> <span
  m='1953940'>minus</span> <span m='1954300'>1/2</span> <span
  m='1955200'>z</span> <span m='1955410'>to</span> <span m='1955560'>the</span>
  <span m='1955650'>minus</span> <span m='1956070'>1</span> <span
  m='1957441'>with</span> <span m='1957900'>a</span> <span
  m='1957990'>region</span> <span m='1958350'>of</span> <span
  m='1958440'>convergence</span> <span m='1959160'>the</span> <span
  m='1959250'>magnitude</span> <span m='1959790'>of</span> <span
  m='1959880'>z</span> <span m='1960540'>greater</span> <span
  m='1960870'>than</span> <span m='1961020'>1/2.</span> <span
  m='1962810'>And</span> <span m='1963200'>by</span> <span
  m='1963410'>the</span> <span m='1963500'>way,</span> <span
  m='1963680'>by</span> <span m='1963890'>now</span> <span m='1964670'>if</span>
  <span m='1966500'>there's</span> <span m='1966680'>one</span> <span
  m='1966890'>thing</span> <span m='1967100'>you</span> <span
  m='1967190'>should</span> <span m='1967370'>have</span> <span
  m='1967460'>gotten</span> <span m='1967820'>out</span> <span
  m='1967970'>of</span> <span m='1968360'>these</span> <span
  m='1968570'>lectures,</span> <span m='1969260'>it</span> <span
  m='1969440'>certainly</span> <span m='1969890'>should</span> <span
  m='1970100'>be</span> <span m='1970750'>to</span> <span m='1970820'>be</span>
  <span m='1970970'>able</span> <span m='1971180'>to</span> <span
  m='1971300'>recognize</span> <span m='1971990'>what</span> <span
  m='1972140'>the</span> <span m='1972230'>inverse</span> <span
  m='1972640'>z</span> <span m='1972870'>transform</span> <span
  m='1973950'>of</span> <span m='1974090'>this</span> <span
  m='1974330'>is.</span> <span m='1974540'>It's</span> <span
  m='1974690'>an</span> <span m='1974780'>example</span> <span
  m='1975350'>that</span> <span m='1975680'>I</span> <span
  m='1975740'>guess</span> <span m='1975950'>we</span> <span
  m='1976070'>bounced</span> <span m='1976460'>around</span> <span
  m='1976790'>so</span> <span m='1976970'>many</span> <span
  m='1977210'>times.</span> </p><p><span m='1979310'>All</span> <span
  m='1979400'>right.</span> <span m='1979880'>Let's</span> <span
  m='1981080'>look</span> <span m='1981440'>at</span> <span
  m='1981770'>this</span> <span m='1982280'>z</span> <span
  m='1982550'>transform.</span> <span m='1985240'>First,</span> <span
  m='1986470'>let's</span> <span m='1986800'>just</span> <span
  m='1987040'>look</span> <span m='1987250'>at</span> <span m='1987340'>x</span>
  <span m='1987580'>of</span> <span m='1987700'>z</span> <span
  m='1988780'>in</span> <span m='1989590'>the</span> <span m='1989680'>z</span>
  <span m='1989920'>plane.</span> <span m='1991280'>Here's</span> <span
  m='1991690'>the</span> <span m='1991780'>z</span> <span
  m='1991990'>plane.</span> <span m='1993280'>We</span> <span
  m='1993430'>have</span> <span m='1994450'>a</span> <span
  m='1995140'>pole</span> <span m='1996380'>at</span> <span m='1996490'>z</span>
  <span m='1996670'>equals</span> <span m='1997090'>1/2.</span> <span
  m='1998750'>And</span> <span m='1999410'>we</span> <span
  m='1999560'>have</span> <span m='1999800'>a</span> <span m='1999860'>0</span>
  <span m='2000880'>at</span> <span m='2001390'>z</span> <span
  m='2001960'>equals</span> <span m='2002350'>zero.</span> <span
  m='2003700'>Here's</span> <span m='2003970'>the</span> <span
  m='2004090'>unit</span> <span m='2004360'>circle.</span> <span
  m='2005380'>And</span> <span m='2005830'>in</span> <span
  m='2006220'>green,</span> <span m='2006700'>what</span> <span
  m='2006850'>I've</span> <span m='2007000'>indicated</span> <span
  m='2007840'>is</span> <span m='2008020'>the</span> <span
  m='2008110'>region</span> <span m='2008440'>of</span> <span
  m='2008530'>convergence.</span> </p><p><span m='2011430'>Now</span> <span
  m='2011510'>to</span> <span m='2011600'>do</span> <span m='2011750'>the</span>
  <span m='2011840'>contour</span> <span m='2012320'>integration,</span> <span
  m='2013340'>it's</span> <span m='2013550'>not</span> <span
  m='2013760'>just</span> <span m='2014030'>x</span> <span m='2014270'>of</span>
  <span m='2014360'>z</span> <span m='2014570'>that</span> <span
  m='2014690'>we're</span> <span m='2014840'>looking</span> <span
  m='2015230'>at.</span> <span m='2015710'>It's</span> <span
  m='2015920'>x</span> <span m='2016220'>of</span> <span m='2016310'>z</span>
  <span m='2016640'>times</span> <span m='2017300'>z</span> <span
  m='2017540'>to</span> <span m='2017690'>the</span> <span m='2017840'>n</span>
  <span m='2017990'>minus</span> <span m='2018410'>1</span> <span
  m='2019700'>equals</span> <span m='2020390'>z</span> <span
  m='2020630'>to</span> <span m='2020810'>the</span> <span m='2020990'>n</span>
  <span m='2021860'>over</span> <span m='2022520'>z</span> <span
  m='2022760'>minus</span> <span m='2023150'>1/2.</span> <span
  m='2025070'>Incidentally,</span> <span m='2028200'>what</span> <span
  m='2028380'>is</span> <span m='2028500'>the</span> <span
  m='2028590'>contour</span> <span m='2029070'>of</span> <span
  m='2029160'>integration</span> <span m='2030090'>look</span> <span
  m='2030360'>like</span> <span m='2031020'>then</span> <span
  m='2032160'>the</span> <span m='2032250'>z</span> <span
  m='2032490'>plane</span> <span m='2033000'>for</span> <span
  m='2033150'>this</span> <span m='2033330'>example?</span> <span
  m='2034770'>It's</span> <span m='2034920'>a</span> <span
  m='2034980'>closed</span> <span m='2035340'>contour</span> <span
  m='2036300'>inside</span> <span m='2037410'>the</span> <span
  m='2037530'>region</span> <span m='2037830'>of</span> <span
  m='2037920'>convergence</span> <span m='2038820'>and</span> <span
  m='2038940'>encircling</span> <span m='2039510'>the</span> <span
  m='2039630'>origin.</span> <span m='2040590'>So</span> <span
  m='2040980'>for</span> <span m='2041220'>example,</span> <span
  m='2043800'>it's</span> <span m='2043980'>a</span> <span
  m='2044040'>contour</span> <span m='2045540'>that</span> <span
  m='2045930'>looks</span> <span m='2046230'>like</span> <span
  m='2046530'>this.</span> <span m='2048989'>And</span> <span
  m='2049500'>incidentally,</span> <span m='2050639'>it</span> <span
  m='2051030'>is</span> <span m='2051570'>and</span> <span m='2051690'>I</span>
  <span m='2052500'>don't</span> <span m='2052679'>think</span> <span
  m='2052860'>I</span> <span m='2053460'>stress</span> <span
  m='2053909'>this</span> <span m='2054120'>before,</span> <span
  m='2055199'>it's</span> <span m='2055440'>a</span> <span
  m='2055590'>counter-clockwise</span> <span m='2056760'>contour.</span> <span
  m='2058020'>So</span> <span m='2058800'>this</span> <span
  m='2059040'>is</span> <span m='2059159'>the</span> <span
  m='2059280'>contour</span> <span m='2059850'>c.</span> <span
  m='2061600'>It's</span> <span m='2062020'>a</span> <span
  m='2062230'>counterclockwise</span> <span m='2063219'>contour.</span> <span
  m='2064480'>As</span> <span m='2064630'>I've</span> <span
  m='2064780'>drawn</span> <span m='2065139'>it,</span> <span
  m='2065590'>I</span> <span m='2065650'>didn't</span> <span
  m='2065860'>draw</span> <span m='2066130'>a</span> <span
  m='2066159'>very</span> <span m='2066429'>good</span> <span
  m='2066639'>circle,</span> <span m='2067900'>partly</span> <span
  m='2068260'>because</span> <span m='2068560'>I</span> <span
  m='2068650'>can't.</span> <span m='2069730'>But</span> <span
  m='2070870'>in</span> <span m='2070989'>fact,</span> <span
  m='2071560'>it</span> <span m='2071679'>also</span> <span
  m='2072040'>emphasizes</span> <span m='2072730'>the</span> <span
  m='2072820'>fact</span> <span m='2073090'>that</span> <span
  m='2073179'>it</span> <span m='2073270'>doesn't</span> <span
  m='2073510'>have</span> <span m='2073719'>to</span> <span
  m='2073840'>be</span> <span m='2073989'>a</span> <span
  m='2074020'>circle.</span> <span m='2074530'>It</span> <span
  m='2074650'>just</span> <span m='2074860'>has</span> <span
  m='2075070'>to</span> <span m='2075219'>be</span> <span
  m='2075310'>closed,</span> <span m='2076210'>inside</span> <span
  m='2076630'>the</span> <span m='2076750'>region</span> <span
  m='2077050'>of</span> <span m='2077139'>convergence,</span> <span
  m='2077889'>and</span> <span m='2077960'>circling</span> <span
  m='2078489'>the</span> <span m='2078610'>origin.</span> <span
  m='2079630'>And</span> <span m='2080199'>a</span> <span
  m='2080380'>counterclockwise</span> <span m='2081280'>contour.</span>
  </p><p><span m='2083150'>All</span> <span m='2083210'>right.</span> <span
  m='2083750'>How</span> <span m='2083900'>many</span> <span
  m='2084199'>poles</span> <span m='2085580'>of</span> <span
  m='2086179'>x</span> <span m='2086449'>of</span> <span m='2086540'>z</span>
  <span m='2086870'>times</span> <span m='2087110'>z</span> <span
  m='2087320'>to</span> <span m='2087440'>the</span> <span m='2087560'>n</span>
  <span m='2087710'>minus</span> <span m='2088070'>1</span> <span
  m='2088370'>are</span> <span m='2088610'>there?</span> <span
  m='2088940'>That</span> <span m='2089150'>is,</span> <span
  m='2089719'>how</span> <span m='2089870'>many</span> <span
  m='2090050'>places</span> <span m='2090530'>are</span> <span
  m='2090710'>there</span> <span m='2090889'>that</span> <span
  m='2091010'>we</span> <span m='2091159'>have</span> <span
  m='2091340'>to</span> <span m='2091460'>evaluate</span> <span
  m='2091969'>residues?</span> <span m='2093590'>Well</span> <span
  m='2093800'>let's</span> <span m='2094040'>look,</span> <span
  m='2094350'>first</span> <span m='2094580'>of</span> <span
  m='2094699'>all,</span> <span m='2095310'>at</span> <span m='2095449'>n</span>
  <span m='2095750'>greater</span> <span m='2096110'>than</span> <span
  m='2096290'>or</span> <span m='2096409'>equal</span> <span
  m='2096739'>to</span> <span m='2096860'>0.</span> <span
  m='2099550'>This</span> <span m='2099790'>doesn't</span> <span
  m='2100090'>introduce</span> <span m='2100570'>any</span> <span
  m='2100780'>poles.</span> <span m='2102070'>This</span> <span
  m='2102310'>introduces</span> <span m='2103060'>one</span> <span
  m='2103360'>pole</span> <span m='2104110'>equals</span> <span
  m='2104530'>1/2.</span> <span m='2106750'>So</span> <span
  m='2107200'>we</span> <span m='2107410'>only</span> <span
  m='2107710'>need</span> <span m='2108010'>to</span> <span
  m='2108220'>evaluate</span> <span m='2108850'>the</span> <span
  m='2108970'>residue</span> <span m='2109510'>of</span> <span
  m='2109660'>this</span> <span m='2110710'>at</span> <span
  m='2110890'>this</span> <span m='2111100'>one</span> <span
  m='2111410'>pole</span> <span m='2112060'>that</span> <span
  m='2112270'>is</span> <span m='2112590'>at z</span> <span
  m='2113010'>equals</span> <span m='2113290'>1/2.</span> </p><p><span
  m='2115270'>So</span> <span m='2115840'>we</span> <span
  m='2116020'>want</span> <span m='2116200'>to</span> <span
  m='2116290'>compute</span> <span m='2116920'>the</span> <span
  m='2117070'>residue</span> <span m='2118210'>then</span> <span
  m='2118630'>of</span> <span m='2118990'>x</span> <span m='2119290'>of</span>
  <span m='2119380'>z</span> <span m='2119740'>times</span> <span
  m='2120010'>z</span> <span m='2120220'>to</span> <span m='2120370'>the</span>
  <span m='2120520'>n</span> <span m='2120670'>minus</span> <span
  m='2121060'>1</span> <span m='2122140'>at</span> <span m='2122620'>z</span>
  <span m='2123040'>equals</span> <span m='2123460'>1/2.</span> <span
  m='2125630'>So</span> <span m='2125810'>that</span> <span m='2126020'>z</span>
  <span m='2126290'>to</span> <span m='2126440'>the</span> <span
  m='2126620'>n</span> <span m='2127400'>over</span> <span m='2127685'>z</span>
  <span m='2127970'>minus</span> <span m='2128360'>1/2</span> <span
  m='2129500'>multiplied</span> <span m='2130190'>by</span> <span
  m='2130400'>z</span> <span m='2130610'>minus</span> <span
  m='2131000'>1/2</span> <span m='2131770'>evaluated</span> <span
  m='2132610'>and</span> <span m='2132890'>z</span> <span
  m='2133190'>equals</span> <span m='2133610'>1/2.</span> <span
  m='2135310'>These</span> <span m='2135690'>two</span> <span
  m='2136710'>cancel</span> <span m='2137160'>out.</span> <span
  m='2138690'>And</span> <span m='2139590'>we</span> <span
  m='2140070'>end</span> <span m='2140370'>up</span> <span
  m='2140550'>with</span> <span m='2140820'>simply</span> <span
  m='2141840'>1/2</span> <span m='2142260'>to</span> <span
  m='2142380'>the</span> <span m='2142560'>n.</span> <span m='2144110'>So</span>
  <span m='2144320'>for</span> <span m='2144490'>n</span> <span
  m='2144710'>greater</span> <span m='2145040'>than</span> <span
  m='2145220'>or</span> <span m='2145340'>equal</span> <span
  m='2145580'>to</span> <span m='2145730'>0,</span> <span m='2147370'>the</span>
  <span m='2147470'>sequence</span> <span m='2148130'>x</span> <span
  m='2148430'>of n</span> <span m='2149420'>is</span> <span
  m='2150440'>just</span> <span m='2150860'>a</span> <span
  m='2150950'>half</span> <span m='2151340'>to</span> <span
  m='2151460'>the</span> <span m='2151640'>n.</span> </p><p><span
  m='2153600'>So</span> <span m='2154440'>that's</span> <span
  m='2155310'>part</span> <span m='2155550'>of</span> <span
  m='2155640'>the</span> <span m='2155760'>result.</span> <span
  m='2157210'>Now</span> <span m='2157320'>we</span> <span
  m='2157470'>have</span> <span m='2157770'>to</span> <span
  m='2157920'>get</span> <span m='2158310'>the</span> <span
  m='2158490'>inverse</span> <span m='2158790'>z</span> <span
  m='2159090'>transform</span> <span m='2159960'>for</span> <span
  m='2160150'>n</span> <span m='2161400'>less</span> <span
  m='2161700'>than</span> <span m='2161850'>zero.</span> <span
  m='2164030'>Well</span> <span m='2164080'>for</span> <span
  m='2164260'>n</span> <span m='2164380'>less</span> <span
  m='2164650'>than</span> <span m='2164800'>0,</span> <span
  m='2165430'>again</span> <span m='2165760'>of</span> <span
  m='2165880'>course</span> <span m='2166510'>we</span> <span
  m='2166720'>have</span> <span m='2167230'>1</span> <span
  m='2167470'>pole</span> <span m='2167960'>and</span> <span
  m='2168220'>z</span> <span m='2168470'>equal</span> <span
  m='2168850'>to</span> <span m='2169000'>1/2.</span> <span
  m='2170830'>But</span> <span m='2170970'>now,</span> <span
  m='2171690'>remember</span> <span m='2172140'>that</span> <span
  m='2172290'>we</span> <span m='2172440'>had</span> <span
  m='2172680'>this</span> <span m='2172920'>factor,</span> <span
  m='2175140'>which</span> <span m='2175550'>was</span> <span
  m='2175850'>z</span> <span m='2176120'>to</span> <span m='2176300'>the</span>
  <span m='2176480'>n.</span> <span m='2178080'>And</span> <span
  m='2178230'>for</span> <span m='2178570'>n negative</span> <span
  m='2179580'>that</span> <span m='2179820'>introduces</span> <span
  m='2181260'>poles</span> <span m='2181920'>at</span> <span
  m='2182130'>the</span> <span m='2182280'>origin.</span> <span
  m='2183660'>And</span> <span m='2183780'>in</span> <span
  m='2183870'>fact</span> <span m='2184320'>it,</span> <span
  m='2184500'>introduces</span> <span m='2185460'>n</span> <span
  m='2185780'>poles.</span> </p><p><span m='2187120'>So</span> <span
  m='2187890'>for</span> <span m='2188340'>n</span> <span
  m='2188580'>less</span> <span m='2188850'>than</span> <span
  m='2189030'>0,</span> <span m='2190590'>we</span> <span
  m='2190770'>have</span> <span m='2191190'>not</span> <span
  m='2191400'>only</span> <span m='2191670'>this</span> <span
  m='2191880'>pole,</span> <span m='2192600'>but</span> <span
  m='2192750'>we</span> <span m='2192900'>have</span> <span m='2193180'>n</span>
  <span m='2193470'>poles</span> <span m='2194100'>at</span> <span m='2194280'>z
  equals</span> <span m='2194720'>0.</span> <span m='2196530'>That's</span>
  <span m='2196680'>a</span> <span m='2196740'>problem.</span> <span
  m='2198000'>Because</span> <span m='2198390'>now</span> <span
  m='2198720'>we're</span> <span m='2198840'>going</span> <span
  m='2198960'>to</span> <span m='2199020'>have</span> <span
  m='2199200'>to</span> <span m='2199350'>evaluate</span> <span
  m='2199920'>the</span> <span m='2200040'>residues</span> <span
  m='2201270'>and</span> <span m='2202890'>each</span> <span
  m='2203100'>of</span> <span m='2203220'>these</span> <span
  m='2203430'>poles.</span> <span m='2204420'>And</span> <span
  m='2204530'>the</span> <span m='2204630'>more</span> <span
  m='2204810'>negative</span> <span m='2205350'>value</span> <span
  m='2205770'>of</span> <span m='2205890'>n</span> <span
  m='2206070'>we're</span> <span m='2206190'>trying</span> <span
  m='2206490'>to</span> <span m='2206580'>get</span> <span m='2206760'>x</span>
  <span m='2207040'>of</span> <span m='2207270'>n for,</span> <span
  m='2208650'>the</span> <span m='2209370'>worse</span> <span
  m='2209760'>it</span> <span m='2209880'>gets,</span> <span
  m='2210300'>because</span> <span m='2210690'>the</span> <span
  m='2210780'>higher</span> <span m='2211110'>the</span> <span
  m='2211200'>multiplicity</span> <span m='2211950'>of</span> <span
  m='2212040'>the</span> <span m='2212160'>pole.</span> </p><p><span
  m='2214380'>All</span> <span m='2214450'>right.</span> <span
  m='2214600'>But</span> <span m='2214720'>look,</span> <span
  m='2215290'>we've</span> <span m='2215440'>seen</span> <span
  m='2215680'>this</span> <span m='2215860'>example</span> <span
  m='2216400'>before.</span> <span m='2218030'>We</span> <span
  m='2218180'>know</span> <span m='2220100'>that</span> <span
  m='2221210'>x</span> <span m='2221530'>of n</span> <span m='2221800'>is</span>
  <span m='2221900'>1/2</span> <span m='2222230'>to</span> <span
  m='2222380'>the</span> <span m='2222530'>n</span> <span m='2222830'>for</span>
  <span m='2223040'>n</span> <span m='2223190'>greater</span> <span
  m='2223520'>than</span> <span m='2223910'>or</span> <span
  m='2224060'>equal</span> <span m='2224300'>to</span> <span
  m='2224420'>0</span> <span m='2225080'>and it's</span> <span
  m='2225320'>0</span> <span m='2225670'>for</span> <span m='2225800'>n</span>
  <span m='2225960'>less</span> <span m='2226180'>than</span> <span
  m='2226340'>0.</span> <span m='2226540'>As</span> <span m='2226760'>we</span>
  <span m='2226850'>knew</span> <span m='2227030'>that</span> <span
  m='2227270'>from</span> <span m='2227450'>other</span> <span
  m='2227810'>times</span> <span m='2228170'>that</span> <span
  m='2228260'>we've</span> <span m='2228410'>worked</span> <span
  m='2228650'>this</span> <span m='2228830'>example.</span> <span
  m='2230000'>So</span> <span m='2230450'>obviously,</span> <span
  m='2230990'>there</span> <span m='2231140'>must</span> <span
  m='2231350'>be</span> <span m='2231500'>some</span> <span
  m='2231710'>easy</span> <span m='2232130'>way</span> <span
  m='2233000'>to</span> <span m='2233120'>get</span> <span
  m='2233690'>the</span> <span m='2233780'>fact</span> <span
  m='2234560'>that</span> <span m='2234860'>x of n,</span> <span
  m='2235280'>in</span> <span m='2235700'>fact</span> <span
  m='2236030'>for</span> <span m='2236150'>this</span> <span
  m='2236330'>example,</span> <span m='2237260'>is</span> <span
  m='2237350'>0</span> <span m='2237920'>for</span> <span m='2238100'>n</span>
  <span m='2238280'>less</span> <span m='2238520'>than</span> <span
  m='2238670'>0.</span> <span m='2240500'>All</span> <span
  m='2240620'>right.</span> </p><p><span m='2240890'>Let's</span> <span
  m='2241100'>take</span> <span m='2241280'>a</span> <span
  m='2241310'>look</span> <span m='2241520'>at</span> <span m='2241580'>a</span>
  <span m='2241640'>way,</span> <span m='2242480'>an</span> <span
  m='2242570'>easy</span> <span m='2242870'>way.</span> <span
  m='2244960'>Here</span> <span m='2245200'>we</span> <span
  m='2245410'>have,</span> <span m='2246050'>again,</span> <span
  m='2246920'>the</span> <span m='2246970'>inverse</span> <span
  m='2247270'>z</span> <span m='2247570'>transform.</span> <span
  m='2248380'>x</span> <span m='2248590'>of</span> <span m='2248680'>n</span>
  <span m='2248830'>is</span> <span m='2248950'>1</span> <span
  m='2249130'>over</span> <span m='2249340'>2</span> <span m='2249530'>pi</span>
  <span m='2249810'>j</span> <span m='2250660'>times</span> <span
  m='2250950'>this</span> <span m='2251080'>contour</span> <span
  m='2251590'>integral.</span> <span m='2253330'>And</span> <span
  m='2253420'>let's</span> <span m='2253600'>simply</span> <span
  m='2253990'>make</span> <span m='2254230'>a</span> <span
  m='2254290'>substitution</span> <span m='2255070'>of</span> <span
  m='2255130'>variables.</span> <span m='2257620'>Let's</span> <span
  m='2257890'>make</span> <span m='2258130'>the</span> <span
  m='2258250'>substitution</span> <span m='2259000'>of</span> <span
  m='2259060'>variables</span> <span m='2260470'>z</span> <span
  m='2260980'>equal</span> <span m='2261310'>to</span> <span
  m='2261520'>p</span> <span m='2262000'>to</span> <span m='2262150'>the</span>
  <span m='2262270'>minus</span> <span m='2262660'>1,</span> <span
  m='2263965'>in</span> <span m='2264400'>which</span> <span
  m='2264610'>case</span> <span m='2264910'>z</span> <span m='2265200'>to</span>
  <span m='2265360'>the</span> <span m='2265540'>n</span> <span
  m='2265720'>minus</span> <span m='2266110'>1</span> <span
  m='2266590'>is</span> <span m='2266800'>equal</span> <span
  m='2267100'>to</span> <span m='2267250'>p</span> <span m='2268000'>to</span>
  <span m='2268090'>the</span> <span m='2268180'>minus</span> <span
  m='2268540'>n</span> <span m='2268720'>plus</span> <span m='2269110'>1.</span>
  <span m='2271800'>Which</span> <span m='2271880'>means</span> <span
  m='2272240'>incidentally</span> <span m='2274040'>that</span> <span
  m='2275090'>with</span> <span m='2275300'>z</span> <span
  m='2275990'>equal</span> <span m='2276380'>to</span> <span
  m='2276680'>r</span> <span m='2277120'>e to</span> <span m='2277330'>of</span>
  <span m='2277430'>the</span> <span m='2277550'>j</span> <span
  m='2277820'>theta,</span> <span m='2279630'>p,</span> <span
  m='2280740'>this</span> <span m='2280920'>new</span> <span
  m='2281130'>variable,</span> <span m='2282180'>is</span> <span
  m='2282330'>1</span> <span m='2282600'>over</span> <span m='2282930'>r</span>
  <span m='2283560'>times</span> <span m='2283890'>e</span> <span
  m='2284110'>to</span> <span m='2284190'>the</span> <span m='2284280'>minus
  j</span> <span m='2284630'>theta.</span> </p><p><span m='2287170'>So</span>
  <span m='2287190'>now</span> <span m='2287370'>we</span> <span
  m='2287520'>want</span> <span m='2287700'>to</span> <span
  m='2287910'>make</span> <span m='2288150'>the</span> <span
  m='2288280'>substitution</span> <span m='2289020'>of</span> <span
  m='2289080'>variables</span> <span m='2290070'>in</span> <span
  m='2290190'>this</span> <span m='2290910'>contour</span> <span
  m='2291420'>integral.</span> <span m='2293080'>Well,</span> <span
  m='2293450'>let's</span> <span m='2293590'>see--</span> <span
  m='2293810'>dz</span> <span m='2294790'>is</span> <span
  m='2295060'>minus</span> <span m='2295660'>p</span> <span
  m='2296630'>to</span> <span m='2296710'>the</span> <span
  m='2297040'>minus</span> <span m='2297460'>2,</span> <span
  m='2298280'>just</span> <span m='2298480'>differentiating</span> <span
  m='2299470'>this.</span> <span m='2301120'>Well,</span> <span
  m='2301360'>I'll</span> <span m='2301420'>let</span> <span
  m='2301600'>you</span> <span m='2301660'>go</span> <span
  m='2301840'>through</span> <span m='2302050'>the</span> <span
  m='2302200'>algebra</span> <span m='2303370'>on</span> <span
  m='2303490'>your</span> <span m='2303700'>own.</span> <span
  m='2303940'>But</span> <span m='2304090'>if</span> <span
  m='2304180'>you</span> <span m='2304300'>take</span> <span
  m='2304570'>this</span> <span m='2305650'>substitution</span> <span
  m='2306400'>of</span> <span m='2306460'>variables,</span> <span
  m='2307090'>stuff</span> <span m='2307560'>it</span> <span
  m='2307630'>into</span> <span m='2307840'>that</span> <span
  m='2308380'>contour</span> <span m='2308890'>integral,</span> <span
  m='2310660'>then</span> <span m='2311320'>the</span> <span
  m='2311440'>result</span> <span m='2311860'>that</span> <span
  m='2311980'>we</span> <span m='2312130'>end</span> <span m='2312370'>up</span>
  <span m='2312550'>with</span> <span m='2313360'>is</span> <span
  m='2313720'>that</span> <span m='2314690'>x</span> <span m='2314970'>of</span>
  <span m='2315100'>n</span> <span m='2316920'>is</span> <span
  m='2317070'>equal</span> <span m='2317340'>to</span> <span
  m='2317490'>minus</span> <span m='2317940'>1</span> <span
  m='2318120'>over</span> <span m='2318330'>2</span> <span m='2318480'>pi</span>
  <span m='2318780'>j,</span> <span m='2319050'>the</span> <span
  m='2319320'>minus</span> <span m='2319680'>coming</span> <span
  m='2320070'>from</span> <span m='2320970'>the</span> <span
  m='2321060'>fact</span> <span m='2321450'>that</span> <span
  m='2321800'>dz</span> <span m='2322110'>is</span> <span
  m='2322230'>minus</span> <span m='2323590'>p</span> <span
  m='2323790'>to</span> <span m='2323950'>the</span> <span
  m='2324090'>minus</span> <span m='2324420'>2</span> <span
  m='2324720'>times</span> <span m='2325050'>dp.</span> <span m='2326250'>That's
  that</span> <span m='2326430'>minus</span> <span m='2326820'>sign.</span>
  <span m='2328200'>x</span> <span m='2328440'>of</span> <span
  m='2328560'>1</span> <span m='2328770'>over</span> <span m='2329040'>p</span>
  <span m='2329370'>times</span> <span m='2329730'>p</span> <span
  m='2329970'>to</span> <span m='2330120'>the</span> <span
  m='2330210'>minus</span> <span m='2330600'>n</span> <span
  m='2330750'>minus</span> <span m='2331170'>1</span> <span
  m='2331800'>dp.</span> </p><p><span m='2333930'>And</span> <span
  m='2334020'>what</span> <span m='2334230'>happens</span> <span
  m='2334590'>to</span> <span m='2334710'>the</span> <span
  m='2334800'>contour?</span> <span m='2336420'>Well</span> <span
  m='2336750'>the</span> <span m='2336900'>contour</span> <span
  m='2337440'>previously</span> <span m='2339090'>was,</span> <span
  m='2340050'>let's</span> <span m='2340290'>say</span> <span
  m='2340740'>r</span> <span m='2341040'>e</span> <span m='2341340'>to</span>
  <span m='2341490'>the</span> <span m='2341580'>j</span> <span
  m='2341860'>theta.</span> <span m='2342400'>Let's</span> <span
  m='2342540'>take</span> <span m='2342750'>it</span> <span
  m='2342810'>as</span> <span m='2342900'>a</span> <span
  m='2342960'>circular</span> <span m='2343440'>contour.</span> <span
  m='2344700'>So</span> <span m='2344910'>the</span> <span
  m='2345000'>contour</span> <span m='2345510'>now</span> <span
  m='2346080'>is</span> <span m='2346260'>1</span> <span m='2346560'>over</span>
  <span m='2346960'>r</span> <span m='2347320'>e to</span> <span
  m='2347520'>the</span> <span m='2347640'>minus j</span> <span
  m='2348030'>theta.</span> <span m='2350190'>That</span> <span
  m='2350400'>means</span> <span m='2350910'>as</span> <span
  m='2351090'>one</span> <span m='2351300'>consequence</span> <span
  m='2352380'>that</span> <span m='2353070'>our</span> <span
  m='2353250'>old</span> <span m='2353520'>counter-clockwise</span> <span
  m='2354420'>contour</span> <span m='2354960'>turns</span> <span
  m='2355290'>into</span> <span m='2355530'>a</span> <span
  m='2355620'>clockwise</span> <span m='2356250'>contour.</span> <span
  m='2357900'>So</span> <span m='2358110'>that's</span> <span
  m='2358350'>what</span> <span m='2358440'>I've</span> <span
  m='2358590'>indicated</span> <span m='2359130'>here.</span> <span
  m='2360630'>But</span> <span m='2360780'>we</span> <span
  m='2360960'>also</span> <span m='2361290'>have</span> <span
  m='2361470'>this</span> <span m='2361650'>minus</span> <span
  m='2362070'>sign.</span> <span m='2363720'>And</span> <span
  m='2364500'>we</span> <span m='2364620'>can</span> <span
  m='2364770'>use</span> <span m='2364980'>that</span> <span
  m='2365160'>minus</span> <span m='2365520'>sign</span> <span
  m='2366270'>to</span> <span m='2367080'>change</span> <span
  m='2367470'>the</span> <span m='2367560'>direction</span> <span
  m='2368100'>of</span> <span m='2368190'>the</span> <span
  m='2368280'>contour.</span> <span m='2369490'>So</span> <span
  m='2369870'>if</span> <span m='2370110'>we</span> <span
  m='2370230'>change</span> <span m='2370680'>the</span> <span
  m='2370770'>contour</span> <span m='2371850'>back</span> <span
  m='2372150'>to</span> <span m='2372300'>a</span> <span
  m='2372480'>counterclockwise</span> <span m='2373410'>contour,</span> <span
  m='2374610'>get</span> <span m='2374760'>rid</span> <span
  m='2374970'>of</span> <span m='2375060'>the</span> <span
  m='2375180'>minus</span> <span m='2375540'>sign.</span> <span
  m='2376860'>Then</span> <span m='2377040'>finally</span> <span
  m='2377430'>we</span> <span m='2377610'>have</span> <span
  m='2377820'>the</span> <span m='2377910'>expression</span> <span
  m='2379050'>x</span> <span m='2379320'>of</span> <span m='2379440'>n</span>
  <span m='2379740'>is</span> <span m='2379920'>1</span> <span
  m='2380100'>over</span> <span m='2380310'>2</span> <span m='2380490'>pi</span>
  <span m='2380820'>j</span> <span m='2381710'>times</span> <span
  m='2382020'>the</span> <span m='2382110'>contour</span> <span
  m='2382620'>integral</span> <span m='2383340'>of</span> <span
  m='2383550'>capital</span> <span m='2384030'>X</span> <span
  m='2384330'>of</span> <span m='2384480'>1</span> <span m='2384660'>over</span>
  <span m='2384930'>p</span> <span m='2385725'>p</span> <span
  m='2386010'>to</span> <span m='2386130'>the</span> <span
  m='2386220'>minus</span> <span m='2386610'>n</span> <span
  m='2386790'>minus</span> <span m='2387180'>1</span> <span
  m='2387920'>dp.</span> </p><p><span m='2389070'>And</span> <span
  m='2389220'>what</span> <span m='2389400'>is</span> <span
  m='2389970'>this</span> <span m='2390180'>contour</span> <span
  m='2390750'>now?</span> <span m='2391680'>Well</span> <span
  m='2392310'>if</span> <span m='2392850'>the</span> <span
  m='2392970'>old</span> <span m='2393240'>contour</span> <span
  m='2393900'>C</span> <span m='2395100'>was</span> <span
  m='2395250'>circular</span> <span m='2395760'>with</span> <span
  m='2395910'>a</span> <span m='2395970'>radius</span> <span
  m='2396450'>of</span> <span m='2396570'>r,</span> <span
  m='2397560'>this</span> <span m='2397830'>contour</span> <span
  m='2398640'>c</span> <span m='2398970'>prime</span> <span
  m='2399960'>is</span> <span m='2400110'>a</span> <span
  m='2400170'>circle</span> <span m='2400770'>with</span> <span
  m='2400920'>a</span> <span m='2400980'>radius</span> <span
  m='2401580'>of</span> <span m='2401760'>1</span> <span m='2401970'>over</span>
  <span m='2402270'>r.</span> <span m='2404350'>Well</span> <span
  m='2404450'>let's</span> <span m='2404630'>just</span> <span
  m='2404900'>look</span> <span m='2405320'>at</span> <span
  m='2405800'>what</span> <span m='2406700'>this</span> <span
  m='2406880'>substitution</span> <span m='2407630'>of</span> <span
  m='2407690'>variable</span> <span m='2408240'>z</span> <span m='2408595'>to
  1</span> <span m='2408950'>over</span> <span m='2409220'>p</span> <span
  m='2410290'>did</span> <span m='2411110'>as</span> <span m='2411290'>a</span>
  <span m='2411350'>matter</span> <span m='2411680'>of</span> <span
  m='2411740'>fact.</span> <span m='2413280'>Here</span> <span
  m='2414300'>I've</span> <span m='2414450'>illustrated</span> <span
  m='2415050'>the</span> <span m='2415140'>z</span> <span
  m='2415380'>plane.</span> <span m='2417450'>Here</span> <span
  m='2418080'>I've</span> <span m='2418260'>illustrated</span> <span
  m='2419280'>the</span> <span m='2419610'>p plane.</span> </p><p><span
  m='2421726'>The</span> <span m='2422160'>unit</span> <span
  m='2422530'>circle</span> <span m='2423220'>in</span> <span
  m='2423370'>the</span> <span m='2423460'>z</span> <span
  m='2423670'>plane,</span> <span m='2424600'>when</span> <span
  m='2424720'>I</span> <span m='2424810'>replace</span> <span
  m='2425170'>z</span> <span m='2425410'>by</span> <span m='2425590'>1</span>
  <span m='2425800'>over</span> <span m='2426040'>p,</span> <span
  m='2427150'>turns</span> <span m='2427570'>again</span> <span
  m='2427900'>into</span> <span m='2428140'>the</span> <span
  m='2428260'>unit</span> <span m='2428560'>circle</span> <span
  m='2429370'>in</span> <span m='2429490'>the</span> <span m='2429580'>p</span>
  <span m='2429790'>plane,</span> <span m='2430840'>because</span> <span
  m='2431440'>the</span> <span m='2431530'>unit</span> <span
  m='2431770'>circle</span> <span m='2432130'>is</span> <span
  m='2432220'>where</span> <span m='2432370'>the</span> <span
  m='2432490'>magnitude</span> <span m='2433000'>of</span> <span
  m='2433060'>z</span> <span m='2433330'>is</span> <span m='2433750'>1.</span>
  <span m='2434610'>And</span> <span m='2434710'>if</span> <span
  m='2434860'>I</span> <span m='2435010'>take</span> <span
  m='2435220'>the</span> <span m='2435310'>reciprocal</span> <span
  m='2435850'>of</span> <span m='2435970'>that,</span> <span
  m='2436240'>the</span> <span m='2436330'>magnitude</span> <span
  m='2436840'>is</span> <span m='2436930'>still</span> <span
  m='2437230'>1.</span> <span m='2438760'>The</span> <span
  m='2438850'>important</span> <span m='2439330'>thing</span> <span
  m='2439690'>is</span> <span m='2439840'>what</span> <span
  m='2440020'>happened</span> <span m='2440380'>to</span> <span
  m='2440500'>this</span> <span m='2440680'>contour.</span> <span
  m='2441970'>Well</span> <span m='2442120'>this</span> <span
  m='2442360'>contour</span> <span m='2443620'>got</span> <span
  m='2443860'>converted</span> <span m='2445000'>if</span> <span
  m='2445150'>it</span> <span m='2445210'>was</span> <span
  m='2445420'>outside</span> <span m='2445930'>the</span> <span
  m='2446020'>unit</span> <span m='2446290'>circle</span> <span
  m='2447370'>into</span> <span m='2448000'>a</span> <span
  m='2448060'>new</span> <span m='2448240'>contour</span> <span
  m='2449140'>which</span> <span m='2449320'>is</span> <span
  m='2449470'>inside</span> <span m='2449890'>the</span> <span
  m='2449980'>unit</span> <span m='2450280'>circle.</span> <span
  m='2451720'>And</span> <span m='2451810'>in</span> <span
  m='2451930'>fact,</span> <span m='2453170'>in</span> <span
  m='2453190'>general,</span> <span m='2454120'>stuff</span> <span
  m='2454540'>that</span> <span m='2454690'>was</span> <span
  m='2454900'>in</span> <span m='2455080'>here,</span> <span
  m='2456400'>the</span> <span m='2456610'>inside</span> <span
  m='2457030'>of</span> <span m='2457150'>the</span> <span
  m='2457240'>unit</span> <span m='2457510'>circle,</span> <span
  m='2458650'>is</span> <span m='2458800'>going</span> <span
  m='2458920'>to</span> <span m='2458980'>end</span> <span m='2459250'>up</span>
  <span m='2459700'>outside</span> <span m='2460180'>the</span> <span
  m='2460300'>unit</span> <span m='2460540'>circle</span> <span
  m='2461530'>in</span> <span m='2462400'>the p</span> <span
  m='2462500'>plane.</span> <span m='2463960'>And</span> <span
  m='2465190'>things</span> <span m='2465970'>that</span> <span
  m='2466150'>were</span> <span m='2466630'>outside</span> <span
  m='2467230'>the</span> <span m='2467320'>unit</span> <span
  m='2467620'>circle</span> <span m='2468310'>in</span> <span
  m='2468430'>the</span> <span m='2468520'>z</span> <span
  m='2468760'>plane</span> <span m='2469750'>are</span> <span
  m='2469870'>going</span> <span m='2470170'>to</span> <span
  m='2470260'>end</span> <span m='2470560'>up</span> <span
  m='2471040'>inside</span> <span m='2471520'>the</span> <span
  m='2471610'>unit</span> <span m='2471880'>circle</span> <span
  m='2472660'>in</span> <span m='2472780'>the</span> <span m='2472870'>p</span>
  <span m='2473080'>plane.</span> </p><p><span m='2474310'>This</span> <span
  m='2474460'>transformation</span> <span m='2475300'>simply</span> <span
  m='2475780'>takes</span> <span m='2476560'>stuff</span> <span
  m='2476950'>outside</span> <span m='2477490'>the</span> <span
  m='2477580'>unit</span> <span m='2477820'>circle</span> <span
  m='2478270'>and</span> <span m='2478390'>folds</span> <span
  m='2478720'>it</span> <span m='2478810'>inside</span> <span
  m='2479200'>the</span> <span m='2479320'>unit</span> <span
  m='2479560'>circle,</span> <span m='2481000'>takes</span> <span
  m='2481270'>things</span> <span m='2481540'>inside</span> <span
  m='2481960'>the</span> <span m='2482060'>unit</span> <span
  m='2482260'>circle</span> <span m='2482890'>and</span> <span
  m='2483070'>folds</span> <span m='2483430'>them</span> <span
  m='2483550'>outside</span> <span m='2483970'>the</span> <span
  m='2484030'>unit</span> <span m='2484350'>circle.</span> <span
  m='2485080'>And</span> <span m='2485200'>it's</span> <span
  m='2485290'>just</span> <span m='2485470'>simply</span> <span
  m='2486280'>a</span> <span m='2486340'>substitution</span> <span
  m='2487090'>of</span> <span m='2487180'>variables.</span> </p><p><span
  m='2489110'>All</span> <span m='2489370'>right.</span> <span
  m='2489510'>Now</span> <span m='2489680'>with</span> <span
  m='2489920'>this</span> <span m='2490060'>substitution</span> <span
  m='2490790'>of</span> <span m='2490850'>variables,</span> <span
  m='2491660'>let's</span> <span m='2492350'>return</span> <span
  m='2493400'>to</span> <span m='2494450'>the</span> <span
  m='2494600'>example</span> <span m='2495650'>that</span> <span
  m='2496220'>we've</span> <span m='2496430'>been</span> <span
  m='2496610'>working.</span> <span m='2500350'>We</span> <span
  m='2500440'>have</span> <span m='2500870'>our</span> <span
  m='2501050'>example.</span> <span m='2505220'>x</span> <span
  m='2505490'>of</span> <span m='2505610'>z</span> <span m='2506060'>is</span>
  <span m='2506570'>1</span> <span m='2506810'>over</span> <span
  m='2507020'>1</span> <span m='2507260'>minus</span> <span
  m='2507590'>1/2</span> <span m='2507920'>z</span> <span m='2508100'>to</span>
  <span m='2508190'>the</span> <span m='2508280'>minus</span> <span
  m='2508670'>1,</span> <span m='2509430'>the</span> <span
  m='2509530'>magnitude</span> <span m='2509990'>of</span> <span
  m='2510080'>z</span> <span m='2510710'>greater</span> <span
  m='2511040'>than</span> <span m='2511190'>1/2.</span> <span
  m='2512950'>We</span> <span m='2513040'>want</span> <span
  m='2513220'>to</span> <span m='2513310'>replace</span> <span
  m='2513670'>z</span> <span m='2514000'>by</span> <span m='2514210'>1</span>
  <span m='2514420'>over</span> <span m='2514690'>p.</span> <span
  m='2515890'>So</span> <span m='2516520'>we</span> <span
  m='2516670'>want</span> <span m='2516970'>x</span> <span m='2517240'>of</span>
  <span m='2517360'>1</span> <span m='2517540'>over</span> <span
  m='2517820'>p.</span> <span m='2520020'>x of</span> <span m='2520080'>1</span>
  <span m='2520290'>over</span> <span m='2520530'>p,</span> <span
  m='2521100'>then</span> <span m='2521460'>simply</span> <span
  m='2521820'>replacing</span> <span m='2522690'>z</span> <span
  m='2522870'>to</span> <span m='2522920'>the</span> <span
  m='2523010'>minus</span> <span m='2523350'>1</span> <span
  m='2523590'>by</span> <span m='2523830'>p,</span> <span m='2525240'>is</span>
  <span m='2525510'>1</span> <span m='2525690'>over</span> <span
  m='2525960'>1</span> <span m='2526170'>minus</span> <span
  m='2526470'>1/2</span> <span m='2526860'>times</span> <span
  m='2527270'>p.</span> <span m='2529040'>If</span> <span
  m='2529220'>this</span> <span m='2529460'>was</span> <span
  m='2529670'>true</span> <span m='2530270'>for</span> <span
  m='2530390'>the</span> <span m='2530480'>magnitude</span> <span
  m='2530930'>of</span> <span m='2531110'>z</span> <span
  m='2531350'>greater</span> <span m='2531740'>than</span> <span
  m='2531890'>1/2,</span> <span m='2533240'>then</span> <span
  m='2533810'>this</span> <span m='2534080'>is</span> <span
  m='2534230'>true</span> <span m='2534620'>for</span> <span
  m='2534740'>the</span> <span m='2534830'>magnitude</span> <span
  m='2535340'>of</span> <span m='2535430'>p</span> <span m='2535610'>less</span>
  <span m='2535880'>than</span> <span m='2536000'>1/2.</span> <span
  m='2537530'>So</span> <span m='2537770'>we</span> <span m='2537890'>get</span>
  <span m='2538130'>minus</span> <span m='2538580'>2</span> <span
  m='2539150'>divided</span> <span m='2539660'>by</span> <span
  m='2540380'>p</span> <span m='2540890'>minus</span> <span
  m='2541320'>2.</span> </p><p><span m='2543090'>If</span> <span
  m='2543240'>we</span> <span m='2543330'>look</span> <span
  m='2543570'>at</span> <span m='2543690'>this</span> <span
  m='2544260'>in</span> <span m='2544830'>the</span> <span m='2544950'>p</span>
  <span m='2545160'>plane,</span> <span m='2547640'>we</span> <span
  m='2547790'>have</span> <span m='2548600'>then</span> <span
  m='2549380'>a</span> <span m='2549470'>pole</span> <span m='2550310'>in</span>
  <span m='2550430'>the</span> <span m='2550520'>p</span> <span
  m='2550760'>plane.</span> <span m='2551690'>The</span> <span
  m='2551780'>pole</span> <span m='2552050'>in</span> <span
  m='2552140'>the</span> <span m='2552200'>z</span> <span
  m='2552410'>plane</span> <span m='2552710'>was</span> <span m='2552940'>at
  z</span> <span m='2553040'>equals</span> <span m='2553700'>1/2.</span> <span
  m='2554660'>So</span> <span m='2554810'>the</span> <span
  m='2554930'>pole</span> <span m='2555530'>in</span> <span
  m='2555680'>the</span> <span m='2555770'>p</span> <span
  m='2555980'>plane</span> <span m='2556520'>is</span> <span
  m='2556940'>at</span> <span m='2557570'>p</span> <span
  m='2558050'>equals</span> <span m='2558530'>2.</span> <span
  m='2560470'>That's</span> <span m='2560740'>now</span> <span
  m='2561010'>outside</span> <span m='2561550'>the</span> <span
  m='2561670'>unit</span> <span m='2561940'>circle.</span> <span
  m='2563610'>The</span> <span m='2563700'>region</span> <span
  m='2564090'>of</span> <span m='2564180'>convergence,</span> <span
  m='2565240'>now,</span> <span m='2565620'>is</span> <span
  m='2565910'>inside</span> <span m='2566520'>the</span> <span
  m='2566610'>circle</span> <span m='2567210'>of</span> <span
  m='2567360'>radius</span> <span m='2567870'>2.</span> <span
  m='2569220'>And</span> <span m='2569340'>where</span> <span
  m='2569670'>is</span> <span m='2569790'>the</span> <span
  m='2569880'>contour</span> <span m='2570390'>of</span> <span
  m='2570480'>integration</span> <span m='2571080'>c</span> <span
  m='2571330'>prime?</span> <span m='2572550'>Well</span> <span
  m='2572580'>that</span> <span m='2572910'>now</span> <span
  m='2573780'>is</span> <span m='2574080'>inside</span> <span
  m='2574980'>the</span> <span m='2575070'>circle</span> <span
  m='2575490'>of</span> <span m='2575580'>radius</span> <span
  m='2576060'>2.</span> <span m='2576960'>For</span> <span
  m='2577170'>example,</span> <span m='2578100'>let's</span> <span
  m='2578610'>draw</span> <span m='2578920'>it</span> <span
  m='2579000'>here.</span> <span m='2580440'>So</span> <span
  m='2580830'>this</span> <span m='2581070'>is</span> <span
  m='2581220'>now</span> <span m='2581790'>the</span> <span
  m='2581910'>contour</span> <span m='2582690'>c</span> <span
  m='2582990'>prime.</span> <span m='2584900'>All</span> <span
  m='2584990'>right.</span> </p><p><span m='2586220'>We</span> <span
  m='2586340'>want</span> <span m='2586550'>finally</span> <span
  m='2587300'>to</span> <span m='2587900'>evaluate</span> <span
  m='2588650'>the</span> <span m='2588770'>inverse</span> <span
  m='2589070'>z</span> <span m='2589370'>transform,</span> <span
  m='2591710'>or</span> <span m='2591860'>the</span> <span
  m='2591950'>inverse</span> <span m='2592250'>p</span> <span
  m='2592490'>transform,</span> <span m='2594600'>by</span> <span
  m='2596920'>looking</span> <span m='2597340'>at</span> <span
  m='2597490'>the</span> <span m='2597610'>residues</span> <span
  m='2598480'>of</span> <span m='2598900'>x</span> <span m='2599230'>of</span>
  <span m='2599410'>1</span> <span m='2599620'>over</span> <span
  m='2599860'>p</span> <span m='2600820'>times</span> <span m='2601120'>p</span>
  <span m='2601410'>to</span> <span m='2601530'>the</span> <span
  m='2601660'>minus</span> <span m='2602050'>n</span> <span
  m='2602230'>minus</span> <span m='2602660'>1.</span> <span
  m='2604091'>The</span> <span m='2604570'>residues</span> <span
  m='2605740'>of</span> <span m='2605920'>that</span> <span
  m='2607150'>at</span> <span m='2607510'>its</span> <span
  m='2607900'>roots,</span> <span m='2609280'>at</span> <span
  m='2609400'>its</span> <span m='2609550'>poles,</span> <span
  m='2610900'>that</span> <span m='2611200'>are</span> <span
  m='2612010'>inside</span> <span m='2612580'>the</span> <span
  m='2612700'>contour</span> <span m='2613660'>of</span> <span
  m='2613780'>integration</span> <span m='2614470'>c</span> <span
  m='2614750'>prime.</span> <span m='2616610'>Well,</span> <span
  m='2617320'>for</span> <span m='2617500'>n</span> <span
  m='2617680'>less</span> <span m='2617920'>than</span> <span
  m='2618070'>0,</span> <span m='2619660'>we</span> <span
  m='2619810'>have</span> <span m='2620680'>one</span> <span
  m='2620980'>pole</span> <span m='2621700'>at</span> <span m='2621820'>p</span>
  <span m='2622120'>equals</span> <span m='2622390'>2.</span> <span
  m='2623770'>And</span> <span m='2624310'>for</span> <span m='2624580'>n</span>
  <span m='2625060'>negative,</span> <span m='2626110'>this</span> <span
  m='2626320'>will</span> <span m='2626440'>contribute</span> <span
  m='2627010'>no</span> <span m='2627230'>poles.</span> <span
  m='2629470'>Therefore,</span> <span m='2630820'>there</span> <span
  m='2631210'>are</span> <span m='2631420'>no</span> <span
  m='2631720'>roots</span> <span m='2633190'>of</span> <span
  m='2633460'>this</span> <span m='2634900'>inside</span> <span
  m='2635470'>this</span> <span m='2635650'>contour.</span> <span
  m='2636610'>And</span> <span m='2636700'>consequently,</span> <span
  m='2637690'>the</span> <span m='2637810'>contour</span> <span
  m='2638290'>integral</span> <span m='2639040'>is</span> <span
  m='2639340'>obviously</span> <span m='2639880'>zero.</span> </p><p><span
  m='2641970'>So</span> <span m='2642720'>x</span> <span m='2642960'>of</span>
  <span m='2643080'>n</span> <span m='2643290'>is</span> <span
  m='2643440'>equal</span> <span m='2643680'>to</span> <span
  m='2643800'>zero</span> <span m='2644680'>for n</span> <span
  m='2644880'>less</span> <span m='2645120'>than</span> <span
  m='2645270'>0.</span> <span m='2647090'>Now</span> <span
  m='2647960'>for</span> <span m='2648350'>greater</span> <span
  m='2648680'>than</span> <span m='2648830'>or</span> <span
  m='2648920'>equal</span> <span m='2649220'>to</span> <span
  m='2649370'>0,</span> <span m='2651080'>we</span> <span
  m='2651230'>have</span> <span m='2651800'>one</span> <span
  m='2652070'>pole</span> <span m='2652610'>at</span> <span m='2652760'>p</span>
  <span m='2653330'>equals 2.</span> <span m='2655500'>But</span> <span
  m='2655710'>then</span> <span m='2656130'>because</span> <span
  m='2656490'>of</span> <span m='2656550'>this</span> <span
  m='2656760'>factor,</span> <span m='2657270'>p to</span> <span
  m='2657600'>the</span> <span m='2657690'>minus</span> <span
  m='2658050'>n</span> <span m='2658230'>minus</span> <span
  m='2658650'>1,</span> <span m='2660240'>we have</span> <span
  m='2660600'>n</span> <span m='2660810'>plus</span> <span m='2661110'>1</span>
  <span m='2661410'>poles</span> <span m='2662640'>at</span> <span m='2662820'>p
  equals</span> <span m='2663290'>0.</span> <span m='2665680'>So</span> <span
  m='2665790'>now</span> <span m='2666120'>it</span> <span
  m='2666240'>seems</span> <span m='2666900'>like</span> <span m='2667410'>for
  n</span> <span m='2667760'>greater</span> <span m='2668100'>than</span> <span
  m='2668280'>or</span> <span m='2668370'>equal</span> <span
  m='2668610'>to</span> <span m='2668730'>0,</span> <span
  m='2669210'>we're</span> <span m='2669390'>back</span> <span
  m='2669720'>where</span> <span m='2669870'>we</span> <span
  m='2669990'>started</span> <span m='2670440'>from.</span> <span
  m='2670710'>Because</span> <span m='2671310'>now</span> <span
  m='2671550'>we</span> <span m='2671730'>have</span> <span
  m='2671910'>these</span> <span m='2672090'>multiple</span> <span
  m='2672570'>order</span> <span m='2672810'>poles</span> <span
  m='2673830'>at</span> <span m='2674400'>p equals 0.</span> <span
  m='2675980'>What</span> <span m='2676070'>do</span> <span
  m='2676130'>we</span> <span m='2676250'>do</span> <span
  m='2676400'>about</span> <span m='2676700'>that?</span> </p><p><span
  m='2678230'>Well,</span> <span m='2678430'>we</span> <span
  m='2678530'>don't</span> <span m='2678580'>have</span> <span
  m='2678700'>to</span> <span m='2678820'>do</span> <span
  m='2678970'>anything</span> <span m='2679360'>about</span> <span
  m='2679660'>it.</span> <span m='2679750'>Because</span> <span
  m='2680350'>we</span> <span m='2680530'>already</span> <span
  m='2681070'>considered</span> <span m='2682060'>the</span> <span
  m='2682150'>case</span> <span m='2683110'>for</span> <span
  m='2683290'>n</span> <span m='2683500'>greater</span> <span
  m='2683860'>than</span> <span m='2684010'>or</span> <span
  m='2684130'>equal</span> <span m='2684400'>to</span> <span
  m='2684520'>0.</span> <span m='2686250'>In</span> <span
  m='2686400'>that</span> <span m='2686610'>case,</span> <span
  m='2687390'>we</span> <span m='2687570'>didn't</span> <span
  m='2687960'>run</span> <span m='2688230'>into</span> <span
  m='2688500'>multiple</span> <span m='2688950'>order</span> <span
  m='2689160'>poles</span> <span m='2689550'>at</span> <span
  m='2689620'>the</span> <span m='2689760'>origin.</span> <span
  m='2690690'>We</span> <span m='2690750'>used</span> <span
  m='2691080'>the</span> <span m='2691210'>substitution</span> <span
  m='2692010'>of</span> <span m='2692070'>variables,</span> <span m='2692700'>z
  equals</span> <span m='2693090'>1</span> <span m='2693270'>over</span> <span
  m='2693510'>p</span> <span m='2694230'>to</span> <span
  m='2694320'>basically</span> <span m='2694890'>avoid</span> <span
  m='2695310'>that</span> <span m='2695520'>problem</span> <span
  m='2696600'>and</span> <span m='2697080'>to</span> <span
  m='2697200'>get</span> <span m='2697410'>the</span> <span
  m='2697560'>answer</span> <span m='2698350'>for n</span> <span
  m='2698460'>less</span> <span m='2698700'>than</span> <span
  m='2698820'>0.</span> </p><p><span m='2699870'>So</span> <span
  m='2700050'>consequently,</span> <span m='2700860'>the</span> <span
  m='2701010'>answer</span> <span m='2701310'>that</span> <span
  m='2701430'>we</span> <span m='2701580'>get,</span> <span
  m='2702700'>which</span> <span m='2703110'>we</span> <span
  m='2703800'>finally</span> <span m='2704310'>know</span> <span
  m='2705480'>to</span> <span m='2705600'>be</span> <span m='2705780'>the</span>
  <span m='2705900'>right</span> <span m='2706140'>answer</span> <span
  m='2706630'>in</span> <span m='2706650'>fact,</span> <span
  m='2707580'>is</span> <span m='2707850'>that</span> <span m='2708780'>x</span>
  <span m='2709020'>of</span> <span m='2709170'>n</span> <span
  m='2709710'>is</span> <span m='2709890'>equal</span> <span
  m='2710130'>to</span> <span m='2710250'>0</span> <span m='2711000'>for
  n</span> <span m='2711390'>less</span> <span m='2711630'>than</span> <span
  m='2711780'>zero.</span> <span m='2712890'>And</span> <span
  m='2713430'>as</span> <span m='2713580'>we</span> <span
  m='2713700'>worked</span> <span m='2714000'>out</span> <span
  m='2714180'>before,</span> <span m='2715170'>x</span> <span
  m='2715440'>of</span> <span m='2715560'>n</span> <span m='2715980'>is</span>
  <span m='2716160'>equal</span> <span m='2716520'>to</span> <span
  m='2716940'>1/2</span> <span m='2717330'>to</span> <span
  m='2717480'>the</span> <span m='2717660'>n</span> <span m='2718830'>for</span>
  <span m='2719080'>n</span> <span m='2719610'>greater</span> <span
  m='2719940'>than</span> <span m='2720120'>or</span> <span
  m='2720210'>equal</span> <span m='2720480'>to</span> <span
  m='2720600'>0.</span> <span m='2721260'>Or</span> <span
  m='2722190'>finally,</span> <span m='2723300'>x</span> <span
  m='2723600'>of</span> <span m='2723750'>n</span> <span m='2725610'>is</span>
  <span m='2725790'>equal</span> <span m='2726180'>to</span> <span
  m='2727350'>1/2</span> <span m='2728310'>to</span> <span
  m='2728580'>the</span> <span m='2728760'>n</span> <span
  m='2729690'>times</span> <span m='2731610'>u of n.</span> </p><p><span
  m='2733610'>All</span> <span m='2733690'>right.</span> <span
  m='2733800'>That's</span> <span m='2734030'>an</span> <span
  m='2734090'>example</span> <span m='2734570'>we've</span> <span
  m='2734750'>worked</span> <span m='2735020'>out</span> <span
  m='2735300'>now</span> <span m='2735650'>three</span> <span
  m='2735920'>times.</span> <span m='2736370'>And</span> <span
  m='2736460'>three</span> <span m='2736670'>times</span> <span
  m='2736970'>we</span> <span m='2737070'>got</span> <span
  m='2737270'>the</span> <span m='2737360'>same</span> <span
  m='2737870'>answer,</span> <span m='2738390'>so</span> <span
  m='2738500'>it</span> <span m='2738590'>must</span> <span
  m='2738800'>be</span> <span m='2738950'>right.</span> <span
  m='2740800'>All</span> <span m='2740860'>right.</span> <span
  m='2741080'>Well</span> <span m='2741790'>this</span> <span
  m='2742630'>roughs</span> <span m='2742990'>out</span> <span
  m='2743830'>the</span> <span m='2744610'>inverse</span> <span
  m='2745510'>z</span> <span m='2745720'>transform,</span> <span
  m='2747370'>several</span> <span m='2747820'>methods</span> <span
  m='2748510'>for</span> <span m='2748840'>getting</span> <span
  m='2749140'>the</span> <span m='2749290'>inverse</span> <span
  m='2749620'>z</span> <span m='2749830'>transform.</span> <span
  m='2751730'>Obviously,</span> <span m='2752540'>to</span> <span
  m='2752690'>become</span> <span m='2753050'>fluent</span> <span
  m='2753710'>with</span> <span m='2754280'>the</span> <span
  m='2754430'>inverse</span> <span m='2754720'>z</span> <span
  m='2755010'>transform</span> <span m='2755900'>requires</span> <span
  m='2756890'>working</span> <span m='2757550'>a</span> <span
  m='2757640'>lot</span> <span m='2757880'>of</span> <span
  m='2758000'>examples.</span> <span m='2759410'>And</span> <span
  m='2760760'>you</span> <span m='2761000'>know</span> <span
  m='2761420'>where</span> <span m='2761570'>you</span> <span
  m='2761720'>going</span> <span m='2761840'>to</span> <span
  m='2761900'>have</span> <span m='2762230'>all</span> <span
  m='2762380'>those</span> <span m='2762590'>examples</span> <span
  m='2763130'>to</span> <span m='2763280'>work.</span> <span
  m='2763790'>That</span> <span m='2763940'>is,</span> <span
  m='2764090'>in</span> <span m='2764150'>the</span> <span
  m='2764240'>study</span> <span m='2764570'>guide.</span> </p><p><span
  m='2766100'>And</span> <span m='2766610'>you'll</span> <span
  m='2766820'>find</span> <span m='2767290'>as</span> <span m='2767450'>I</span>
  <span m='2768200'>stressed</span> <span m='2768590'>previously,</span> <span
  m='2769940'>that</span> <span m='2770780'>as</span> <span
  m='2771170'>you</span> <span m='2771350'>work</span> <span
  m='2771830'>more</span> <span m='2772070'>and</span> <span
  m='2772160'>more</span> <span m='2772370'>examples,</span> <span
  m='2773540'>what</span> <span m='2773720'>you</span> <span
  m='2773840'>find</span> <span m='2774530'>in</span> <span
  m='2774740'>computing</span> <span m='2775240'>inverse</span> <span
  m='2775340'>z</span> <span m='2775760'>transforms</span> <span
  m='2776690'>is</span> <span m='2776960'>that</span> <span
  m='2777800'>more</span> <span m='2778040'>and</span> <span
  m='2778130'>more</span> <span m='2778340'>frequently,</span> <span
  m='2779330'>you're</span> <span m='2779510'>able</span> <span
  m='2779810'>to</span> <span m='2779960'>recognize</span> <span
  m='2780560'>the</span> <span m='2780710'>answer.</span> </p><p><span
  m='2782970'>Well,</span> <span m='2783360'>in</span> <span
  m='2783510'>the</span> <span m='2784080'>next</span> <span
  m='2784350'>lecture,</span> <span m='2785790'>we'll</span> <span
  m='2786570'>complete</span> <span m='2787020'>the</span> <span
  m='2787110'>discussion</span> <span m='2787920'>of</span> <span
  m='2788070'>the z</span> <span m='2788160'>transform.</span> <span
  m='2789630'>In</span> <span m='2789720'>particular,</span> <span
  m='2790740'>we'll</span> <span m='2791440'>among</span> <span
  m='2791610'>other</span> <span m='2791850'>things</span> <span
  m='2792270'>present</span> <span m='2792660'>some</span> <span
  m='2792810'>properties</span> <span m='2793440'>of</span> <span
  m='2793530'>the z</span> <span m='2793800'>transform,</span> <span
  m='2795030'>which</span> <span m='2795240'>also</span> <span
  m='2795810'>by</span> <span m='2796050'>the</span> <span
  m='2796170'>way,</span> <span m='2796560'>help</span> <span
  m='2796920'>us</span> <span m='2797220'>in</span> <span
  m='2797400'>computing</span> <span m='2798060'>inverse</span> <span
  m='2798210'>z</span> <span m='2798660'>transforms.</span> <span
  m='2800010'>And</span> <span m='2800520'>so</span> <span m='2800880'>in</span>
  <span m='2801000'>the</span> <span m='2801090'>next</span> <span
  m='2801330'>lecture,</span> <span m='2802510'>we'll</span> <span
  m='2802620'>be</span> <span m='2802770'>continuing</span> <span
  m='2804300'>the</span> <span m='2804630'>topic</span> <span
  m='2805110'>of</span> <span m='2805260'>the z</span> <span
  m='2805350'>transform,</span> <span m='2806280'>and</span> <span
  m='2806400'>in</span> <span m='2806490'>fact</span> <span
  m='2806850'>concluding</span> <span m='2807270'>the</span> <span
  m='2807360'>topic.</span> <span m='2807960'>Thank</span> <span
  m='2808260'>you.</span> </p>
embedded_media:
  - uid: c3f2bf603f1237d558cce514fd28a21d
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: MITRES_6_008S11_lec06.pdf
    title: MITRES_6_008S11_lec06.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-6-the-inverse-z-transform/MITRES_6_008S11_lec06.pdf
  - uid: d939b4e5a9706148084eeab1f330bb31
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: SMnPZzlgtXU
  - uid: def1d3ad85d71c38b7a54f4c54bf6135
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-6-the-inverse-z-transform/id481803782?i=108362012
  - uid: 3e13f4377958eafb9190cb8268d09245
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec06_300k.mp4'
  - uid: e6bbdfcb10ff3292402bea7ef435ed68
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/SMnPZzlgtXU/default.jpg'
  - uid: 09f45c0cb7b8d0c4d707c528f5796231
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: SMnPZzlgtXU
  - uid: 2184f79b37c137b2f258441ee26e5b81
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: SMnPZzlgtXU.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-6-the-inverse-z-transform/SMnPZzlgtXU.srt
  - uid: 2ad78299ac2f06152203852880e9d697
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: SMnPZzlgtXU.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-6-the-inverse-z-transform/SMnPZzlgtXU.pdf
  - uid: 1f5dd55c95c75b2511ddbb15f51b9dc8
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 7486a204e900be9590c35c40e3080e5c
    parent_uid: fe999adf052e1c0f941148cf68772257
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
