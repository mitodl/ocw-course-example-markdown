---
order_index: null
title: 'Lecture 4: Convolution'
template_type: Tabbed
uid: 433f0f569c6adfed0f8fc61a4e336e07
parent_uid: a781d5ac598bc6063ba6ac8138e446cf
technical_location: >-
  https://ocw.mit.edu/resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-4-convolution
short_url: lecture-4-convolution
inline_embed_id: '55881213lecture4:convolution11373292'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Representation of signals in terms of
  impulses; Convolution sum representation for discrete-time linear,
  time-invariant (LTI) systems: convolution integral representation for
  continuous-time LTI systems; Properties: commutative, associative, and
  distributive.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Convolution (<img alt="This resource may not render correctly in a screen
  reader." src="/images/inacessible.gif" /><a
  href="./resolveuid/0400ba59406d52d94c079d99928156ee"
  target="_blank">PDF</a>)</p>
transcript: >-
  <p><span m='40'>The</span> <span m='160'>following</span> <span
  m='600'>content</span> <span m='1190'>is</span> <span m='1310'>provided</span>
  <span m='1750'>under</span> <span m='2040'>a</span> <span
  m='2060'>Creative</span> <span m='2470'>Commons</span> <span
  m='2870'>license.</span> <span m='3880'>Your</span> <span
  m='4160'>support</span> <span m='4670'>will</span> <span m='4830'>help</span>
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
  m='20750'>[MUSIC PLAYING]</span> </p><p><span m='56781'>PROFESSOR:</span>
  <span m='57270'>In</span> <span m='57330'>the</span> <span
  m='57400'>last</span> <span m='57700'>lecture,</span> <span
  m='58340'>we</span> <span m='58710'>discussed</span> <span m='59130'>a</span>
  <span m='59210'>number</span> <span m='59630'>of</span> <span
  m='60490'>general</span> <span m='60830'>properties</span> <span
  m='61440'>for</span> <span m='61540'>systems,</span> <span
  m='62920'>which,</span> <span m='63520'>as</span> <span m='63730'>you</span>
  <span m='63850'>recall,</span> <span m='64610'>applied</span> <span
  m='65140'>both</span> <span m='65580'>to</span> <span
  m='65960'>continuous-time</span> <span m='67680'>and</span> <span
  m='68490'>to</span> <span m='68710'>discrete-time</span> <span
  m='69690'>systems.</span> <span m='72060'>These</span> <span
  m='72260'>properties</span> <span m='73030'>were</span> <span
  m='73330'>the</span> <span m='73480'>properties</span> <span
  m='74610'>associated</span> <span m='75410'>with</span> <span
  m='75530'>a</span> <span m='75590'>system</span> <span m='75980'>having</span>
  <span m='76400'>memory.</span> <span m='77810'>The</span> <span
  m='77950'>issue</span> <span m='78560'>of</span> <span
  m='79220'>whether</span> <span m='79500'>a</span> <span
  m='79550'>system</span> <span m='80160'>is</span> <span m='80480'>or</span>
  <span m='80630'>isn't</span> <span m='80840'>invertible,</span> <span
  m='82240'>we</span> <span m='82390'>talked</span> <span m='82720'>about</span>
  <span m='82990'>causality</span> <span m='84270'>and</span> <span
  m='84410'>stability,</span> <span m='86080'>and</span> <span
  m='86500'>finally</span> <span m='87020'>we</span> <span
  m='87180'>talked</span> <span m='87510'>about</span> <span
  m='87970'>when</span> <span m='88120'>linearity</span> <span
  m='88780'>and</span> <span m='88930'>time</span> <span
  m='89190'>invariance.</span> <span m='91170'>In</span> <span
  m='91290'>today's</span> <span m='91670'>lecture,</span> <span
  m='92350'>what</span> <span m='92500'>I'd</span> <span m='92600'>like</span>
  <span m='92810'>to</span> <span m='92920'>do</span> <span m='93360'>is</span>
  <span m='94030'>focus</span> <span m='94710'>specifically</span> <span
  m='95660'>on</span> <span m='95900'>linearity</span> <span
  m='96200'>and</span> <span m='96610'>time</span> <span
  m='96890'>invariance,</span> <span m='98170'>and</span> <span
  m='98330'>show</span> <span m='98820'>how</span> <span m='99210'>for</span>
  <span m='99390'>systems</span> <span m='99970'>that</span> <span
  m='100090'>have</span> <span m='100330'>those</span> <span
  m='100580'>properties,</span> <span m='101910'>we</span> <span
  m='102190'>can</span> <span m='102760'>exploit</span> <span
  m='103420'>them</span> <span m='104130'>to</span> <span
  m='104410'>generate</span> <span m='105100'>a</span> <span
  m='105200'>general</span> <span m='105620'>representation.</span> </p><p><span
  m='107840'>Let</span> <span m='107940'>me</span> <span m='108070'>begin</span>
  <span m='108410'>by</span> <span m='108880'>just</span> <span
  m='109140'>reviewing</span> <span m='110340'>the</span> <span
  m='110440'>two</span> <span m='110610'>properties</span> <span
  m='111200'>again</span> <span m='111500'>quickly.</span> <span
  m='112700'>Time</span> <span m='112970'>invariance,</span> <span
  m='114370'>as</span> <span m='115050'>you</span> <span
  m='115220'>recall,</span> <span m='116480'>is</span> <span m='116630'>a</span>
  <span m='116680'>property</span> <span m='117280'>that</span> <span
  m='117480'>applied</span> <span m='118000'>both</span> <span
  m='118280'>to</span> <span m='118390'>continuous-time</span> <span
  m='119370'>and</span> <span m='119430'>discrete-time</span> <span
  m='120130'>systems,</span> <span m='121330'>and</span> <span
  m='121530'>in</span> <span m='121650'>essence</span> <span
  m='122740'>stated</span> <span m='123570'>that</span> <span
  m='124640'>for</span> <span m='125030'>any</span> <span
  m='125280'>given</span> <span m='126060'>input</span> <span
  m='126580'>and</span> <span m='126750'>output</span> <span
  m='127390'>relationship</span> <span m='128810'>if</span> <span
  m='129060'>we</span> <span m='129570'>simply</span> <span
  m='130070'>shift</span> <span m='130490'>the</span> <span
  m='130630'>input,</span> <span m='131850'>then</span> <span
  m='132510'>the</span> <span m='132700'>output</span> <span
  m='133470'>shifts</span> <span m='133930'>by</span> <span
  m='134090'>the</span> <span m='134190'>same</span> <span
  m='134520'>amount.</span> <span m='135800'>And</span> <span
  m='135970'>of</span> <span m='136070'>course,</span> <span
  m='136490'>exactly</span> <span m='137640'>the</span> <span
  m='137750'>same</span> <span m='138080'>kind</span> <span m='138370'>of</span>
  <span m='138470'>statement</span> <span m='139530'>applied</span> <span
  m='140320'>in</span> <span m='141050'>discrete</span> <span
  m='141520'>time.</span> <span m='142590'>So</span> <span
  m='142840'>time</span> <span m='143110'>invariance</span> <span
  m='143690'>was</span> <span m='143830'>a</span> <span
  m='143880'>property</span> <span m='144840'>that</span> <span
  m='145010'>said</span> <span m='145290'>that</span> <span
  m='145440'>the</span> <span m='145510'>system</span> <span
  m='146330'>didn't</span> <span m='146610'>care</span> <span
  m='147140'>about</span> <span m='147560'>what</span> <span
  m='147740'>the</span> <span m='147840'>time</span> <span
  m='148190'>origin</span> <span m='148850'>of</span> <span
  m='148990'>the</span> <span m='149080'>signal</span> <span
  m='149490'>is.</span> </p><p><span m='151540'>Linearity</span> <span
  m='152550'>was</span> <span m='152700'>a</span> <span
  m='152760'>property</span> <span m='153660'>related</span> <span
  m='154140'>to</span> <span m='154260'>the</span> <span m='154350'>fact</span>
  <span m='154920'>that</span> <span m='155420'>if</span> <span
  m='155670'>we</span> <span m='155810'>have</span> <span m='157260'>a</span>
  <span m='157340'>set</span> <span m='157600'>of</span> <span
  m='157660'>outputs</span> <span m='158520'>associated</span> <span
  m='159220'>with</span> <span m='159330'>a</span> <span m='159390'>given</span>
  <span m='159670'>set</span> <span m='159920'>of</span> <span
  m='160000'>inputs--</span> <span m='162040'>as</span> <span
  m='162340'>I've</span> <span m='162480'>indicated</span> <span
  m='163070'>here</span> <span m='163700'>with</span> <span
  m='163890'>the</span> <span m='164010'>inputs</span> <span
  m='164950'>as</span> <span m='165230'>phi_k</span> <span m='166650'>and</span>
  <span m='166800'>the</span> <span m='166910'>outputs</span> <span
  m='167360'>psi_k,</span> <span m='169720'>then</span> <span
  m='170480'>the</span> <span m='170570'>property</span> <span
  m='171080'>of</span> <span m='171180'>linearity</span> <span
  m='172150'>states</span> <span m='173160'>that</span> <span
  m='174030'>if</span> <span m='174550'>we</span> <span m='174710'>have</span>
  <span m='174960'>an</span> <span m='175060'>input</span> <span
  m='175760'>which</span> <span m='176090'>is</span> <span m='176550'>a</span>
  <span m='176640'>linear</span> <span m='177060'>combination</span> <span
  m='178090'>of</span> <span m='178250'>those</span> <span
  m='178550'>inputs,</span> <span m='180130'>then</span> <span
  m='181000'>the</span> <span m='181160'>output</span> <span
  m='182270'>is</span> <span m='182860'>a</span> <span m='182960'>linear</span>
  <span m='183330'>combination</span> <span m='184190'>of</span> <span
  m='184350'>the</span> <span m='184470'>associated</span> <span
  m='185230'>outputs.</span> <span m='186250'>So</span> <span
  m='187340'>that</span> <span m='187870'>linear</span> <span
  m='188200'>combination</span> <span m='188860'>of</span> <span
  m='188940'>inputs</span> <span m='190070'>generates,</span> <span
  m='190920'>for</span> <span m='191160'>a</span> <span m='191190'>linear</span>
  <span m='191590'>system,</span> <span m='193530'>an</span> <span
  m='193770'>output</span> <span m='194390'>which</span> <span
  m='194680'>is</span> <span m='194980'>a</span> <span m='195070'>linear</span>
  <span m='195420'>combination</span> <span m='196330'>of</span> <span
  m='196500'>the</span> <span m='196600'>associated</span> <span
  m='197280'>outputs.</span> </p><p><span m='199600'>Now</span> <span
  m='200690'>the</span> <span m='200780'>question</span> <span
  m='201180'>is,</span> <span m='201740'>how</span> <span m='202110'>can</span>
  <span m='202280'>we</span> <span m='202650'>exploit</span> <span
  m='203150'>the</span> <span m='203230'>properties</span> <span
  m='203860'>of</span> <span m='203940'>linearity</span> <span
  m='204800'>and</span> <span m='204950'>time</span> <span
  m='205230'>invariance?</span> <span m='207530'>There's</span> <span
  m='207730'>a</span> <span m='207780'>basic</span> <span
  m='208190'>strategy</span> <span m='209160'>which</span> <span
  m='209480'>will</span> <span m='209710'>flow</span> <span
  m='210490'>more</span> <span m='210740'>or</span> <span m='210780'>less</span>
  <span m='211220'>through</span> <span m='211420'>most</span> <span
  m='211740'>of</span> <span m='211800'>this</span> <span
  m='212020'>course.</span> <span m='213720'>The</span> <span
  m='213810'>strategy</span> <span m='214690'>is</span> <span
  m='215940'>to</span> <span m='216890'>attempt</span> <span
  m='217670'>to</span> <span m='217800'>decompose</span> <span
  m='218770'>a</span> <span m='218840'>signal,</span> <span
  m='219430'>either</span> <span m='219660'>continuous-time</span> <span
  m='220445'>or</span> <span m='220640'>discrete-time,</span> <span
  m='223000'>into</span> <span m='223210'>a</span> <span m='223270'>set</span>
  <span m='223520'>of</span> <span m='223590'>basic</span> <span
  m='224050'>signals.</span> <span m='226630'>I've</span> <span
  m='227210'>indicated</span> <span m='227820'>that</span> <span
  m='228450'>here.</span> </p><p><span m='230410'>And</span> <span
  m='231180'>the</span> <span m='231300'>question</span> <span
  m='231750'>then</span> <span m='232150'>is,</span> <span
  m='232820'>what</span> <span m='233380'>basic</span> <span
  m='233860'>signal</span> <span m='234240'>should</span> <span
  m='234440'>we</span> <span m='234590'>pick?</span> <span
  m='236000'>Well,</span> <span m='236600'>the</span> <span
  m='236770'>answer,</span> <span m='237370'>kind</span> <span
  m='237630'>of,</span> <span m='237880'>is</span> <span m='238140'>we</span>
  <span m='238300'>should</span> <span m='238520'>pick</span> <span
  m='238860'>a</span> <span m='238960'>set</span> <span m='239180'>of</span>
  <span m='239240'>basic</span> <span m='239670'>signals</span> <span
  m='240740'>that</span> <span m='240880'>provide</span> <span
  m='241540'>a</span> <span m='241600'>certain</span> <span
  m='241940'>degree</span> <span m='242500'>of</span> <span
  m='242630'>analytical</span> <span m='243210'>convenience.</span> <span
  m='244180'>So</span> <span m='244500'>we</span> <span m='244680'>choose</span>
  <span m='244950'>a</span> <span m='245020'>set</span> <span
  m='245240'>of</span> <span m='245310'>inputs</span> <span
  m='245750'>for</span> <span m='245830'>the</span> <span
  m='245930'>decomposition</span> <span m='247450'>that</span> <span
  m='248200'>provide</span> <span m='249590'>outputs</span> <span
  m='250350'>that</span> <span m='250710'>we</span> <span m='250860'>can</span>
  <span m='251030'>easily</span> <span m='251390'>generate.</span> </p><p><span
  m='253810'>Now,</span> <span m='253920'>as</span> <span
  m='254160'>we'll</span> <span m='254300'>see,</span> <span
  m='254970'>when</span> <span m='255140'>we</span> <span m='255270'>do</span>
  <span m='255510'>this,</span> <span m='256660'>there</span> <span
  m='257149'>are</span> <span m='258050'>two</span> <span
  m='258649'>classes</span> <span m='259859'>of</span> <span
  m='260279'>inputs</span> <span m='261089'>that</span> <span
  m='261300'>are</span> <span m='261380'>particularly</span> <span
  m='262240'>suited</span> <span m='262880'>to</span> <span
  m='263010'>that</span> <span m='263240'>strategy.</span> <span
  m='264890'>One</span> <span m='265150'>class</span> <span m='265770'>is</span>
  <span m='266780'>the</span> <span m='266870'>set</span> <span
  m='267320'>of</span> <span m='267920'>delayed</span> <span
  m='268360'>impulses,</span> <span m='270610'>namely</span> <span
  m='271170'>decomposing</span> <span m='271980'>a</span> <span
  m='272040'>signal</span> <span m='272660'>into</span> <span
  m='272900'>a</span> <span m='272970'>linear</span> <span
  m='273310'>combination</span> <span m='274030'>of</span> <span
  m='274140'>these.</span> <span m='275300'>And</span> <span
  m='275450'>as</span> <span m='275670'>we'll</span> <span
  m='275840'>see,</span> <span m='276510'>that</span> <span
  m='276830'>leads</span> <span m='277250'>to</span> <span m='277390'>a</span>
  <span m='277450'>representation</span> <span m='278890'>for</span> <span
  m='279030'>linear</span> <span m='279390'>time-invariant</span> <span
  m='280190'>systems,</span> <span m='281240'>which</span> <span
  m='281450'>is</span> <span m='281580'>referred</span> <span m='282010'>to
  as</span> <span m='283080'>convolution.</span> </p><p><span
  m='285840'>The</span> <span m='285920'>second</span> <span
  m='286740'>is</span> <span m='287380'>a</span> <span
  m='287980'>decomposition</span> <span m='289070'>of</span> <span
  m='289260'>inputs</span> <span m='289840'>into</span> <span
  m='290110'>complex</span> <span m='290650'>exponentials--</span> <span
  m='292380'>a</span> <span m='292480'>linear</span> <span
  m='292740'>combination</span> <span m='293350'>of</span> <span
  m='293440'>complex</span> <span m='293960'>exponentials--</span> <span
  m='295450'>and</span> <span m='296240'>that</span> <span
  m='296750'>leads</span> <span m='297270'>to</span> <span m='297710'>a</span>
  <span m='297790'>representation</span> <span m='298960'>of</span> <span
  m='299560'>signals</span> <span m='300130'>and</span> <span
  m='300220'>systems</span> <span m='301190'>through</span> <span
  m='301370'>what</span> <span m='301570'>we'll</span> <span
  m='301780'>refer</span> <span m='302130'>to</span> <span m='302480'>as</span>
  <span m='303200'>Fourier</span> <span m='303650'>analysis.</span> <span
  m='306560'>Now, Fourier</span> <span m='307020'>analysis</span> <span
  m='307870'>will</span> <span m='308040'>be</span> <span m='308440'>a</span>
  <span m='308550'>topic</span> <span m='309500'>for</span> <span
  m='310190'>a</span> <span m='310290'>set</span> <span m='310520'>of</span>
  <span m='310610'>later</span> <span m='310920'>lectures.</span> <span
  m='312030'>What</span> <span m='312170'>I'd</span> <span
  m='312270'>like</span> <span m='312470'>to</span> <span
  m='312560'>begin</span> <span m='312910'>with</span> <span
  m='313250'>is</span> <span m='313580'>the</span> <span
  m='313670'>representation</span> <span m='314660'>in</span> <span
  m='314760'>terms</span> <span m='315060'>of</span> <span
  m='315150'>impulses</span> <span m='316280'>and</span> <span
  m='316500'>the</span> <span m='316600'>associated</span> <span
  m='317330'>description</span> <span m='318050'>of</span> <span
  m='318190'>linear</span> <span m='318520'>time-invariant</span> <span
  m='319330'>systems</span> <span m='320140'>using</span> <span
  m='320450'>convolution.</span> </p><p><span m='322520'>So</span> <span
  m='322720'>let's</span> <span m='323260'>begin</span> <span
  m='324130'>with</span> <span m='325110'>a</span> <span
  m='325220'>discussion</span> <span m='326010'>of</span> <span
  m='326350'>discrete-time</span> <span m='327040'>signals,</span> <span
  m='328190'>and</span> <span m='328370'>in</span> <span
  m='328470'>particular</span> <span m='329420'>the</span> <span
  m='329550'>issue</span> <span m='330230'>of</span> <span m='330390'>how</span>
  <span m='330690'>discrete-time</span> <span m='331410'>signals</span> <span
  m='332560'>can</span> <span m='332850'>be</span> <span
  m='332990'>decomposed</span> <span m='333920'>as</span> <span
  m='334360'>a</span> <span m='334430'>linear</span> <span
  m='334770'>combination</span> <span m='335740'>of</span> <span
  m='336670'>delayed</span> <span m='337500'>impulses.</span> <span
  m='339740'>Well,</span> <span m='340210'>in</span> <span
  m='340330'>fact,</span> <span m='340710'>it's</span> <span
  m='340840'>relatively</span> <span m='341710'>straightforward.</span> <span
  m='343560'>What</span> <span m='343800'>I've</span> <span
  m='343920'>shown</span> <span m='344260'>here</span> <span
  m='344900'>is</span> <span m='346100'>a</span> <span m='346220'>general</span>
  <span m='346990'>sequence</span> <span m='348080'>with</span> <span
  m='348640'>values</span> <span m='349140'>which</span> <span
  m='349320'>I've</span> <span m='349470'>indicated</span> <span
  m='350450'>at</span> <span m='351060'>the</span> <span m='351180'>top.</span>
  </p><p><span m='352640'>And</span> <span m='353300'>more</span> <span
  m='353790'>or</span> <span m='353840'>less</span> <span m='354260'>as</span>
  <span m='354610'>we</span> <span m='354750'>did</span> <span
  m='355050'>when</span> <span m='355180'>we</span> <span
  m='355330'>talked</span> <span m='355700'>about</span> <span
  m='357100'>representing</span> <span m='358020'>a</span> <span
  m='358090'>unit</span> <span m='358450'>step</span> <span m='359440'>in</span>
  <span m='359570'>terms</span> <span m='359930'>of</span> <span
  m='360030'>impulses,</span> <span m='361390'>we</span> <span
  m='361510'>can</span> <span m='361660'>think</span> <span m='361910'>of</span>
  <span m='362020'>this</span> <span m='362240'>general</span> <span
  m='362610'>sequence</span> <span m='363860'>as</span> <span
  m='364270'>a</span> <span m='364360'>sequence</span> <span
  m='365340'>of</span> <span m='366160'>impulses--</span> <span
  m='368170'>delayed,</span> <span m='368980'>namely,</span> <span
  m='369520'>occurring</span> <span m='370070'>at</span> <span
  m='370660'>the</span> <span m='370780'>appropriate</span> <span
  m='371970'>time</span> <span m='372320'>instant,</span> <span
  m='374060'>and</span> <span m='374630'>with</span> <span m='374800'>the</span>
  <span m='374900'>appropriate</span> <span m='375430'>amplitude.</span> <span
  m='376950'>So</span> <span m='377900'>we</span> <span m='378010'>can</span>
  <span m='378170'>think</span> <span m='378560'>of</span> <span
  m='378860'>this</span> <span m='379130'>general</span> <span
  m='379490'>sequence</span> <span m='380720'>and</span> <span
  m='381810'>an</span> <span m='381950'>impulse</span> <span
  m='382630'>occurring</span> <span m='383300'>at</span> <span
  m='383420'>n</span> <span m='383570'>=</span> <span m='383920'>0</span> <span
  m='385200'>and</span> <span m='385390'>with</span> <span m='385530'>a</span>
  <span m='385580'>height</span> <span m='385850'>of</span> <span
  m='385930'>x[0],</span> <span m='387990'>plus</span> <span
  m='388670'>an</span> <span m='388780'>impulse</span> <span
  m='390220'>of</span> <span m='390370'>height</span> <span
  m='390770'>x[1]</span> <span m='391960'>occurring</span> <span
  m='392560'>at</span> <span m='392760'>time</span> <span m='393080'>n</span>
  <span m='393240'>=</span> <span m='393610'>1, and</span> <span
  m='394430'>so</span> <span m='394590'>that's</span> <span
  m='394840'>x[1]</span> <span m='395830'>delta[n-1],</span> <span
  m='398450'>an</span> <span m='398560'>impulse</span> <span
  m='399180'>at</span> <span m='399960'>-1</span> <span m='400580'>with</span>
  <span m='400750'>an</span> <span m='400850'>amplitude</span> <span
  m='401620'>of</span> <span m='401990'>x[-1], etc.</span> </p><p><span
  m='405030'>So</span> <span m='405830'>if</span> <span m='406280'>we</span>
  <span m='406640'>continued</span> <span m='408000'>to</span> <span
  m='408130'>generate</span> <span m='408630'>a</span> <span
  m='408680'>set</span> <span m='408930'>of</span> <span
  m='409740'>weighted,</span> <span m='410110'>delayed</span> <span
  m='410500'>unit</span> <span m='410810'>samples</span> <span
  m='411320'>like</span> <span m='411580'>that,</span> <span
  m='412500'>and</span> <span m='412790'>if</span> <span m='412920'>we</span>
  <span m='413090'>added</span> <span m='413290'>all</span> <span
  m='413520'>these</span> <span m='414130'>together,</span> <span
  m='415600'>then</span> <span m='416340'>that</span> <span
  m='416550'>will</span> <span m='416730'>generate</span> <span
  m='417700'>the</span> <span m='417820'>total</span> <span
  m='418130'>sequence.</span> <span m='420120'>Algebraically,</span> <span
  m='421510'>then,</span> <span m='422110'>what</span> <span
  m='422280'>that</span> <span m='422500'>corresponds</span> <span
  m='423280'>to</span> <span m='423740'>is</span> <span
  m='423930'>representing</span> <span m='424610'>the</span> <span
  m='424690'>sequence</span> <span m='426620'>as</span> <span
  m='426990'>a</span> <span m='427080'>sum</span> <span m='427590'>of</span>
  <span m='427740'>individual</span> <span m='428380'>terms</span> <span
  m='429170'>as</span> <span m='429360'>I've</span> <span
  m='429500'>indicated</span> <span m='430070'>here</span> <span
  m='431020'>or</span> <span m='432190'>in</span> <span m='432330'>terms</span>
  <span m='432850'>of</span> <span m='433010'>a</span> <span
  m='433070'>general</span> <span m='433500'>sum,</span> <span
  m='434410'>the</span> <span m='434510'>sum</span> <span m='435030'>of</span>
  <span m='435350'>x[k]</span> <span m='436490'>delta[n-k].</span> </p><p><span
  m='438820'>So</span> <span m='438990'>that's</span> <span
  m='439250'>our</span> <span m='439350'>strategy--</span> <span
  m='439950'>the</span> <span m='440040'>strategy</span> <span
  m='440760'>is</span> <span m='441150'>to</span> <span
  m='441490'>decompose</span> <span m='443540'>an</span> <span
  m='443650'>arbitrary</span> <span m='444130'>sequence</span> <span
  m='444760'>into</span> <span m='445370'>a</span> <span
  m='445400'>linear</span> <span m='445770'>combination</span> <span
  m='446620'>of</span> <span m='447290'>weighted,</span> <span
  m='447570'>delayed</span> <span m='448040'>impulses.</span> <span
  m='449540'>And</span> <span m='450050'>here</span> <span
  m='450580'>again</span> <span m='451080'>is</span> <span m='451400'>the</span>
  <span m='451900'>representation,</span> <span m='453280'>which</span> <span
  m='453530'>we</span> <span m='453640'>just</span> <span
  m='454150'>finished</span> <span m='455000'>generating.</span> </p><p><span
  m='457160'>Now,</span> <span m='458090'>why</span> <span m='458590'>is</span>
  <span m='459290'>this</span> <span m='459540'>representation</span> <span
  m='460360'>useful?</span> <span m='461370'>It's</span> <span
  m='461540'>useful</span> <span m='462100'>because</span> <span
  m='462700'>we</span> <span m='462890'>now</span> <span m='463250'>have</span>
  <span m='464150'>a</span> <span m='464260'>decomposition</span> <span
  m='465210'>of</span> <span m='465290'>the</span> <span
  m='465380'>sequence</span> <span m='466160'>as</span> <span
  m='466330'>a</span> <span m='466380'>linear</span> <span
  m='466790'>combination</span> <span m='468640'>of</span> <span
  m='468990'>basic</span> <span m='469790'>sequences,</span> <span
  m='470530'>namely</span> <span m='470900'>the</span> <span
  m='471160'>delayed</span> <span m='471400'>impulses.</span> <span
  m='473080'>And</span> <span m='473930'>if</span> <span m='474440'>we</span>
  <span m='474660'>are</span> <span m='474760'>talking</span> <span
  m='475400'>about</span> <span m='475970'>a</span> <span
  m='476060'>linear</span> <span m='476460'>system,</span> <span
  m='478090'>the</span> <span m='478180'>response</span> <span
  m='478820'>to</span> <span m='478920'>that</span> <span
  m='479100'>linear</span> <span m='479460'>combination</span> <span
  m='480400'>is</span> <span m='480930'>a</span> <span m='481040'>linear</span>
  <span m='481390'>combination</span> <span m='482070'>of</span> <span
  m='482150'>the</span> <span m='482240'>responses.</span> <span
  m='484270'>So</span> <span m='485280'>if</span> <span m='485550'>we</span>
  <span m='486180'>denote</span> <span m='486730'>the</span> <span
  m='486890'>response</span> <span m='488370'>to</span> <span
  m='488550'>a</span> <span m='488600'>delayed</span> <span
  m='489000'>impulse</span> <span m='490360'>as</span> <span
  m='490830'>h_k[n],</span> <span m='493030'>then</span> <span
  m='493770'>the</span> <span m='493870'>response</span> <span
  m='495210'>to</span> <span m='496010'>this</span> <span
  m='496350'>general</span> <span m='496790'>input</span> <span
  m='497810'>is</span> <span m='498830'>what</span> <span m='499020'>I've</span>
  <span m='499160'>indicated</span> <span m='499710'>here,</span> <span
  m='500740'>where</span> <span m='502450'>y[n],</span> <span
  m='503030'>of</span> <span m='503130'>course,</span> <span
  m='503640'>is</span> <span m='503800'>the</span> <span
  m='503940'>output</span> <span m='504720'>due</span> <span
  m='504950'>to</span> <span m='505090'>the</span> <span
  m='505190'>general</span> <span m='505630'>input</span> <span
  m='505910'>x[n].</span> <span m='507900'>h_k[n]</span> <span
  m='508720'>in</span> <span m='509170'>is</span> <span m='509380'>the</span>
  <span m='509530'>output</span> <span m='510530'>due</span> <span
  m='510960'>to</span> <span m='511550'>the</span> <span
  m='511650'>delayed</span> <span m='512020'>impulse,</span> <span
  m='513190'>and</span> <span m='513820'>these</span> <span
  m='514080'>are</span> <span m='514169'>simply</span> <span
  m='515169'>the</span> <span m='515280'>coefficients</span> <span
  m='516809'>in</span> <span m='516960'>the</span> <span
  m='517049'>weighting.</span> </p><p><span m='520169'>So</span> <span
  m='521010'>for</span> <span m='521140'>a</span> <span m='521210'>linear</span>
  <span m='521539'>system,</span> <span m='522429'>we</span> <span
  m='522580'>have</span> <span m='523280'>this</span> <span
  m='523520'>representation.</span> <span m='525340'>And</span> <span
  m='526320'>if</span> <span m='526750'>now,</span> <span m='527070'>in</span>
  <span m='527230'>addition,</span> <span m='528000'>the</span> <span
  m='528100'>system</span> <span m='528500'>is</span> <span
  m='528620'>time-invariant,</span> <span m='530610'>we</span> <span
  m='530830'>can,</span> <span m='531440'>in</span> <span
  m='531590'>fact,</span> <span m='532150'>relate</span> <span
  m='532800'>the</span> <span m='533000'>outputs</span> <span
  m='534130'>due</span> <span m='534370'>to</span> <span m='534530'>these</span>
  <span m='534810'>individual</span> <span m='535520'>delayed</span> <span
  m='535880'>impulses.</span> <span m='537240'>Specifically,</span> <span
  m='538170'>if</span> <span m='538300'>the</span> <span
  m='538390'>system</span> <span m='538770'>is</span> <span
  m='538880'>time-invariant,</span> <span m='540390'>then</span> <span
  m='541120'>the</span> <span m='541220'>response</span> <span
  m='541940'>to</span> <span m='542060'>an</span> <span
  m='542160'>impulse</span> <span m='543240'>at</span> <span
  m='543450'>time</span> <span m='544530'>k</span> <span m='546320'>is</span>
  <span m='546760'>exactly</span> <span m='547320'>the</span> <span
  m='547430'>same</span> <span m='547940'>as</span> <span m='548250'>the</span>
  <span m='548330'>response</span> <span m='548830'>to</span> <span
  m='548950'>an</span> <span m='549040'>impulse</span> <span
  m='549590'>at</span> <span m='549770'>time</span> <span m='550100'>0,</span>
  <span m='551350'>shifted</span> <span m='552170'>over</span> <span
  m='552480'>to</span> <span m='552620'>time</span> <span m='552960'>k.</span>
  <span m='553470'>Said</span> <span m='553740'>another</span> <span
  m='554060'>way,</span> <span m='555100'>h_k[n]</span> <span
  m='556890'>is</span> <span m='557030'>simply</span> <span
  m='558180'>h_0[n-k],</span> <span m='560520'>where</span> <span
  m='560780'>h_0</span> <span m='562530'>is</span> <span m='562740'>the</span>
  <span m='562830'>response</span> <span m='563360'>of</span> <span
  m='563420'>the</span> <span m='563510'>system</span> <span
  m='564450'>to</span> <span m='564590'>an</span> <span
  m='564700'>impulse</span> <span m='565360'>at</span> <span m='565650'>n</span>
  <span m='565840'>=</span> <span m='566160'>0.</span> <span
  m='567140'>And</span> <span m='568050'>it's</span> <span
  m='568290'>generally</span> <span m='568720'>useful</span> <span
  m='570030'>to,</span> <span m='570570'>rather</span> <span
  m='570960'>than</span> <span m='571230'>carrying</span> <span
  m='571750'>around</span> <span m='572060'>h_0[n],</span> <span
  m='573700'>just</span> <span m='573920'>simply</span> <span
  m='574870'>define</span> <span m='575450'>h_0[n]</span> <span
  m='576800'>as</span> <span m='577220'>h[n],</span> <span
  m='579220'>which</span> <span m='579490'>is</span> <span m='580110'>the</span>
  <span m='580770'>unit</span> <span m='581170'>sample</span> <span
  m='581830'>or</span> <span m='581980'>unit</span> <span
  m='582280'>impulse</span> <span m='582700'>response</span> <span
  m='583220'>of</span> <span m='583300'>the</span> <span
  m='583380'>system.</span> </p><p><span m='585070'>And</span> <span
  m='585290'>so</span> <span m='586010'>the</span> <span
  m='586120'>consequence,</span> <span m='586890'>then,</span> <span
  m='587290'>is</span> <span m='587680'>for</span> <span m='588070'>a</span>
  <span m='588560'>linear</span> <span m='588870'>time-invariant</span> <span
  m='589440'>system,</span> <span m='591340'>the</span> <span
  m='591510'>output</span> <span m='592680'>can</span> <span
  m='592880'>be</span> <span m='593060'>expressed</span> <span
  m='594280'>as</span> <span m='594520'>this</span> <span m='594850'>sum</span>
  <span m='596150'>where</span> <span m='597000'>h[n-k]</span> <span
  m='598510'>is</span> <span m='598730'>the</span> <span
  m='598820'>response</span> <span m='599660'>to</span> <span
  m='599790'>an</span> <span m='599870'>impulse</span> <span
  m='600400'>occurring</span> <span m='600970'>at</span> <span
  m='601120'>time</span> <span m='601400'>n</span> <span m='601520'>=</span>
  <span m='601870'>k.</span> <span m='603600'>And</span> <span
  m='604480'>this</span> <span m='604920'>is</span> <span
  m='605780'>referred</span> <span m='606240'>to</span> <span
  m='606720'>as</span> <span m='607230'>the</span> <span
  m='607320'>convolution</span> <span m='608020'>sum.</span> </p><p><span
  m='610780'>Now,</span> <span m='611070'>we</span> <span
  m='611250'>can--</span> <span m='612450'>just</span> <span
  m='612930'>to</span> <span m='613600'>emphasize</span> <span
  m='614740'>how</span> <span m='614940'>we've</span> <span
  m='615380'>gone</span> <span m='615620'>about</span> <span
  m='615990'>this,</span> <span m='616770'>let</span> <span m='616960'>me</span>
  <span m='617280'>show</span> <span m='617570'>it</span> <span
  m='617680'>from</span> <span m='617860'>another</span> <span
  m='618160'>perspective.</span> <span m='622040'>We</span> <span
  m='622540'>of</span> <span m='622670'>course</span> <span
  m='623040'>have</span> <span m='623210'>taken</span> <span
  m='623950'>the</span> <span m='624050'>sequence</span> <span
  m='624840'>x[n],</span> <span m='627030'>we</span> <span
  m='627420'>have</span> <span m='628080'>decomposed</span> <span
  m='628900'>it</span> <span m='629300'>as</span> <span m='630130'>a</span>
  <span m='630720'>linear</span> <span m='631090'>combination</span> <span
  m='631990'>of</span> <span m='632230'>these</span> <span
  m='632810'>weighted,</span> <span m='633180'>delayed</span> <span
  m='633560'>impulses.</span> <span m='636010'>When</span> <span
  m='636170'>these</span> <span m='636600'>are</span> <span
  m='636790'>added</span> <span m='637070'>together,</span> <span
  m='637800'>those</span> <span m='638060'>correspond</span> <span
  m='639140'>to</span> <span m='639280'>the</span> <span
  m='639400'>original</span> <span m='639770'>sequence</span> <span
  m='640290'>x[n].</span> <span m='642810'>If</span> <span
  m='643690'>this</span> <span m='643940'>impulse,</span> <span
  m='644860'>for</span> <span m='645060'>example,</span> <span
  m='646300'>generates</span> <span m='648120'>a</span> <span
  m='648200'>response</span> <span m='649450'>which</span> <span
  m='649840'>is</span> <span m='650320'>x[0]</span> <span
  m='651990'>h[n],</span> <span m='652570'>where</span> <span
  m='652770'>h[n]</span> <span m='653290'>is</span> <span m='653330'>the</span>
  <span m='653370'>response</span> <span m='654030'>to</span> <span
  m='654100'>a</span> <span m='654170'>unit</span> <span
  m='654540'>impulse</span> <span m='655170'>at</span> <span m='655800'>n</span>
  <span m='655950'>=</span> <span m='656270'>0,</span> <span
  m='657670'>and</span> <span m='658410'>the</span> <span
  m='658750'>second</span> <span m='659170'>one</span> <span
  m='659620'>generates</span> <span m='660780'>a</span> <span
  m='660860'>delayed</span> <span m='661620'>weighted</span> <span
  m='662010'>response,</span> <span m='662810'>and</span> <span
  m='663080'>the</span> <span m='663150'>third</span> <span
  m='663530'>one</span> <span m='664250'>similarly,</span> <span
  m='665680'>and</span> <span m='666230'>we</span> <span
  m='666410'>generate</span> <span m='666890'>these</span> <span
  m='667150'>individual</span> <span m='667770'>responses,</span> <span
  m='669020'>these</span> <span m='669220'>are</span> <span
  m='669360'>all</span> <span m='669630'>added</span> <span
  m='669930'>together,</span> <span m='670920'>and</span> <span
  m='671360'>it's</span> <span m='671500'>that</span> <span
  m='671700'>linear</span> <span m='672050'>combination</span> <span
  m='673340'>that</span> <span m='673670'>forms</span> <span
  m='674100'>the</span> <span m='674190'>final</span> <span
  m='674600'>output.</span> </p><p><span m='676180'>So</span> <span
  m='676350'>that's</span> <span m='676600'>really</span> <span
  m='676920'>kind</span> <span m='677160'>of</span> <span m='677230'>the</span>
  <span m='677320'>way</span> <span m='677480'>we're</span> <span
  m='677600'>thinking</span> <span m='677990'>about</span> <span
  m='678370'>it.</span> <span m='678450'>We</span> <span m='678570'>have</span>
  <span m='678750'>a</span> <span m='678810'>general</span> <span
  m='679160'>sequence,</span> <span m='680610'>we're</span> <span
  m='680770'>thinking</span> <span m='681600'>of</span> <span
  m='682130'>each</span> <span m='682870'>individual</span> <span
  m='683450'>sample</span> <span m='684160'>individually,</span> <span
  m='685650'>each</span> <span m='685900'>one</span> <span m='686100'>of</span>
  <span m='686160'>those</span> <span m='686530'>pops</span> <span
  m='686950'>the</span> <span m='687040'>system,</span> <span
  m='688230'>and</span> <span m='688410'>because</span> <span
  m='688780'>of</span> <span m='688870'>linearity,</span> <span
  m='689790'>the</span> <span m='689890'>response</span> <span
  m='690640'>is</span> <span m='690830'>the</span> <span m='690900'>sum</span>
  <span m='691640'>of</span> <span m='691740'>those</span> <span
  m='691930'>individual</span> <span m='692490'>responses.</span> </p><p><span
  m='694930'>That's</span> <span m='695670'>what</span> <span
  m='695800'>happens</span> <span m='696210'>in</span> <span
  m='696310'>discrete</span> <span m='696770'>time,</span> <span
  m='697650'>and</span> <span m='698190'>pretty</span> <span
  m='698480'>much</span> <span m='698720'>the</span> <span
  m='698810'>same</span> <span m='699190'>strategy</span> <span
  m='700190'>works</span> <span m='700520'>in</span> <span
  m='700630'>continuous</span> <span m='701260'>time.</span> <span
  m='703050'>In</span> <span m='703200'>particular,</span> <span
  m='706350'>we</span> <span m='706550'>can</span> <span m='707210'>begin</span>
  <span m='707890'>in</span> <span m='708140'>continuous</span> <span
  m='708790'>time</span> <span m='709900'>with</span> <span
  m='711270'>the</span> <span m='711380'>notion</span> <span
  m='711970'>of</span> <span m='712640'>decomposing</span> <span
  m='714040'>a</span> <span m='714120'>continuous-time</span> <span
  m='714940'>signal</span> <span m='716120'>into</span> <span
  m='717540'>a</span> <span m='717600'>succession</span> <span
  m='718710'>of</span> <span m='719290'>arbitrarily</span> <span
  m='720030'>narrow</span> <span m='720420'>rectangles.</span> <span
  m='722060'>And</span> <span m='724030'>as</span> <span m='724220'>the</span>
  <span m='724300'>width</span> <span m='724490'>of</span> <span
  m='724550'>the</span> <span m='724640'>rectangles</span> <span
  m='725300'>goes</span> <span m='725550'>to</span> <span m='725650'>0,</span>
  <span m='726580'>the</span> <span m='726670'>approximation</span> <span
  m='727490'>gets</span> <span m='727770'>better.</span> <span
  m='729080'>Essentially</span> <span m='729640'>what's</span> <span
  m='729850'>going</span> <span m='730060'>to</span> <span
  m='730130'>happen</span> <span m='730570'>is</span> <span
  m='730720'>that</span> <span m='730870'>each</span> <span m='731140'>of</span>
  <span m='731200'>those</span> <span m='731410'>individual</span> <span
  m='732020'>rectangles,</span> <span m='733210'>as</span> <span
  m='733410'>they</span> <span m='733520'>get</span> <span
  m='733720'>narrower</span> <span m='734320'>and</span> <span
  m='734400'>narrower,</span> <span m='735510'>correspond</span> <span
  m='736480'>more</span> <span m='736810'>and</span> <span
  m='736900'>more</span> <span m='737320'>to</span> <span m='737470'>an</span>
  <span m='737570'>impulse.</span> </p><p><span m='738770'>Let</span> <span
  m='738860'>me</span> <span m='739010'>show</span> <span m='739250'>you</span>
  <span m='739720'>what</span> <span m='739880'>I</span> <span
  m='739940'>mean.</span> <span m='741970'>Here</span> <span
  m='742160'>we</span> <span m='742320'>have</span> <span m='743580'>a</span>
  <span m='744170'>continuous-time</span> <span m='745040'>signal,</span> <span
  m='746960'>and</span> <span m='748250'>I've</span> <span
  m='748690'>approximated</span> <span m='749540'>it</span> <span
  m='750040'>by</span> <span m='750670'>a</span> <span
  m='750750'>staircase.</span> <span m='753530'>So</span> <span
  m='754400'>in</span> <span m='754590'>essence</span> <span m='755440'>I</span>
  <span m='755570'>can</span> <span m='755770'>think</span> <span
  m='756070'>of</span> <span m='756200'>this</span> <span m='757070'>as</span>
  <span m='757500'>individual</span> <span m='758930'>rectangles</span> <span
  m='759970'>of</span> <span m='760110'>heights</span> <span
  m='760470'>associated</span> <span m='761220'>with</span> <span
  m='761410'>the</span> <span m='761470'>height</span> <span
  m='761850'>of</span> <span m='761960'>the</span> <span
  m='762060'>continuous</span> <span m='762710'>curve,</span> <span
  m='763780'>and</span> <span m='763970'>so</span> <span m='764650'>I've</span>
  <span m='764850'>indicated</span> <span m='765390'>that</span> <span
  m='765610'>down</span> <span m='765870'>below.</span> <span
  m='766220'>Here,</span> <span m='766480'>for</span> <span
  m='766660'>example,</span> <span m='767450'>is</span> <span
  m='768210'>the</span> <span m='768320'>impulse</span> <span
  m='769120'>corresponding</span> <span m='769910'>to</span> <span
  m='770030'>the</span> <span m='770120'>rectangle</span> <span
  m='770860'>between</span> <span m='771970'>t</span> <span m='772180'>=</span>
  <span m='772890'>-2</span> <span m='773070'>Delta</span> <span
  m='773330'>and</span> <span m='773590'>t</span> <span m='773760'>=</span>
  <span m='774440'>-Delta.</span> <span m='776110'>Here's</span> <span
  m='776390'>the</span> <span m='776480'>one</span> <span m='777130'>from</span>
  <span m='777670'>-Delta</span> <span m='778090'>to</span> <span
  m='778220'>0,</span> <span m='779370'>and</span> <span m='779610'>as</span>
  <span m='779750'>we</span> <span m='779870'>continue</span> <span
  m='780370'>on</span> <span m='780570'>down,</span> <span m='781830'>we</span>
  <span m='782020'>get</span> <span m='783190'>impulses,</span> <span
  m='784070'>or</span> <span m='784220'>rather</span> <span
  m='784480'>rectangles,</span> <span m='785650'>from</span> <span
  m='785840'>successive</span> <span m='786410'>parts</span> <span
  m='786770'>of</span> <span m='786830'>the</span> <span m='786910'>wave</span>
  <span m='787120'>form.</span> </p><p><span m='788810'>Now</span> <span
  m='788990'>let's</span> <span m='789410'>look</span> <span
  m='790160'>specifically</span> <span m='791060'>at</span> <span
  m='791650'>the</span> <span m='792320'>rectangle,</span> <span
  m='793010'>for</span> <span m='793190'>example,</span> <span
  m='794270'>starting</span> <span m='794730'>at</span> <span
  m='794830'>0</span> <span m='795085'>and</span> <span m='795340'>ending</span>
  <span m='795810'>at</span> <span m='795967'>Delta,</span> <span
  m='797720'>and</span> <span m='798270'>the</span> <span
  m='798430'>amplitude</span> <span m='799010'>of</span> <span
  m='799190'>it</span> <span m='799410'>is</span> <span
  m='799900'>x(Delta).</span> <span m='804730'>So</span> <span
  m='805310'>what</span> <span m='805510'>we</span> <span
  m='805660'>have--</span> <span m='806760'>actually,</span> <span
  m='807260'>this</span> <span m='807380'>should</span> <span
  m='807560'>be</span> <span m='807800'>x(0),</span> <span m='809580'>and</span>
  <span m='810530'>so</span> <span m='811700'>let</span> <span
  m='811745'>me</span> <span m='811790'>just</span> <span
  m='812040'>correct</span> <span m='812390'>that</span> <span
  m='812980'>here.</span> <span m='813480'>That's</span> <span
  m='813700'>x(0).</span> <span m='815280'>And</span> <span m='815540'>so</span>
  <span m='816170'>we</span> <span m='816330'>have</span> <span
  m='817020'>a</span> <span m='817110'>rectangle</span> <span
  m='818090'>height</span> <span m='818380'>x(0),</span> <span
  m='820020'>and</span> <span m='820150'>recall</span> <span
  m='820580'>the</span> <span m='820660'>function</span> <span
  m='821670'>that</span> <span m='821850'>I</span> <span
  m='821940'>defined</span> <span m='822350'>last</span> <span
  m='822710'>time</span> <span m='823090'>as</span> <span
  m='823400'>delta_Delta(t),</span> <span m='826500'>which</span> <span
  m='826740'>had</span> <span m='826860'>height</span> <span m='827140'>1</span>
  <span m='827380'>/</span> <span m='827620'>delta</span> <span
  m='828240'>and</span> <span m='828440'>width</span> <span
  m='828970'>delta.</span> <span m='830010'>So</span> <span
  m='830640'>multiplying</span> <span m='831260'>finally</span> <span
  m='831630'>by</span> <span m='831830'>this</span> <span m='832250'>last</span>
  <span m='832660'>little</span> <span m='832920'>Delta,</span> <span
  m='834110'>then,</span> <span m='834690'>this</span> <span
  m='835060'>is</span> <span m='835260'>a</span> <span
  m='835320'>representation</span> <span m='836870'>for</span> <span
  m='837330'>the</span> <span m='837490'>rectangle</span> <span
  m='838580'>that</span> <span m='838730'>I've</span> <span
  m='838840'>shown</span> <span m='839170'>there.</span> </p><p><span
  m='840110'>Now</span> <span m='840490'>there's</span> <span
  m='840710'>a</span> <span m='840760'>little</span> <span m='840960'>bit</span>
  <span m='841130'>of</span> <span m='841230'>algebra</span> <span
  m='841660'>there</span> <span m='842000'>to</span> <span
  m='842400'>kind</span> <span m='842590'>of</span> <span
  m='842670'>track</span> <span m='843010'>through,</span> <span
  m='844200'>but</span> <span m='844950'>what</span> <span
  m='845120'>we're</span> <span m='845280'>really</span> <span
  m='845530'>doing</span> <span m='846160'>is</span> <span
  m='846970'>just</span> <span m='847150'>simply</span> <span
  m='847510'>representing</span> <span m='848250'>this</span> <span
  m='848660'>in</span> <span m='848770'>terms</span> <span m='849080'>of</span>
  <span m='849200'>rectangles.</span> <span m='850490'>What</span> <span
  m='850650'>I</span> <span m='850700'>want</span> <span m='850940'>to</span>
  <span m='851030'>do</span> <span m='851470'>is</span> <span
  m='851660'>describe</span> <span m='852230'>each</span> <span
  m='852400'>rectangle</span> <span m='853820'>as</span> <span
  m='854860'>in</span> <span m='855000'>terms</span> <span m='855350'>of</span>
  <span m='855390'>that</span> <span m='855590'>function</span> <span
  m='856590'>delta_Delta(t),</span> <span m='858450'>which</span> <span
  m='858640'>in</span> <span m='858710'>the</span> <span
  m='858810'>limit,</span> <span m='859190'>then,</span> <span
  m='859360'>becomes</span> <span m='859800'>an</span> <span
  m='859890'>impulse.</span> </p><p><span m='861330'>So</span> <span
  m='861470'>let's</span> <span m='861710'>track</span> <span
  m='862030'>that</span> <span m='862500'>through</span> <span
  m='862760'>a</span> <span m='862820'>little</span> <span
  m='863010'>further.</span> <span m='865800'>When</span> <span
  m='865940'>we</span> <span m='866050'>have</span> <span m='866280'>that</span>
  <span m='866440'>linear</span> <span m='866790'>combination,</span> <span
  m='868800'>then,</span> <span m='869370'>we're</span> <span
  m='869490'>saying</span> <span m='869970'>that</span> <span
  m='870240'>x(t)</span> <span m='871420'>can</span> <span m='871630'>be</span>
  <span m='871770'>represented</span> <span m='872660'>by</span> <span
  m='873650'>a</span> <span m='873730'>sum</span> <span m='874070'>as</span>
  <span m='874200'>I</span> <span m='874300'>indicate</span> <span
  m='874810'>here,</span> <span m='876130'>which</span> <span
  m='877200'>I</span> <span m='878640'>can</span> <span m='878830'>then</span>
  <span m='879310'>write</span> <span m='880610'>more</span> <span
  m='880840'>generally</span> <span m='882020'>in</span> <span
  m='882180'>this</span> <span m='882440'>form,</span> <span
  m='882830'>just</span> <span m='883070'>indicating</span> <span
  m='883640'>that</span> <span m='883790'>this</span> <span m='883950'>is</span>
  <span m='884090'>an</span> <span m='884190'>infinite</span> <span
  m='884570'>sum.</span> <span m='886650'>We</span> <span m='886770'>now</span>
  <span m='887320'>want</span> <span m='887490'>to</span> <span
  m='887570'>take</span> <span m='887840'>the</span> <span
  m='887950'>limit</span> <span m='888490'>as</span> <span
  m='888740'>Delta</span> <span m='889060'>goes</span> <span
  m='889360'>to</span> <span m='889480'>0,</span> <span m='890750'>and</span>
  <span m='890960'>as</span> <span m='891110'>Delta</span> <span
  m='891430'>goes</span> <span m='891710'>to</span> <span m='891820'>0,</span>
  <span m='893680'>notice</span> <span m='894480'>that</span> <span
  m='895040'>this</span> <span m='895340'>term</span> <span
  m='896110'>becomes</span> <span m='897200'>arbitrarily</span> <span
  m='897880'>narrow.</span> <span m='899370'>This</span> <span
  m='899760'>goes</span> <span m='900090'>to</span> <span m='900250'>our</span>
  <span m='900440'>impulse</span> <span m='900940'>function,</span> <span
  m='901670'>and</span> <span m='901860'>this,</span> <span m='902070'>of</span>
  <span m='902190'>course,</span> <span m='902820'>goes</span> <span
  m='903200'>to</span> <span m='903530'>x</span> <span m='903820'>of</span>
  <span m='903930'>tau.</span> <span m='905150'>And</span> <span
  m='905390'>in</span> <span m='905500'>fact,</span> <span m='906390'>in</span>
  <span m='906510'>the</span> <span m='906600'>limit,</span> <span
  m='907430'>a</span> <span m='907530'>sum</span> <span m='908060'>of</span>
  <span m='908210'>this</span> <span m='908470'>form</span> <span
  m='909440'>is</span> <span m='909910'>exactly</span> <span
  m='910840'>the</span> <span m='910950'>way</span> <span m='911460'>an</span>
  <span m='911620'>integral</span> <span m='912060'>is</span> <span
  m='912210'>defined.</span> <span m='913270'>So</span> <span
  m='913770'>we</span> <span m='913880'>have</span> <span m='914080'>an</span>
  <span m='914140'>expression</span> <span m='914820'>for</span> <span
  m='914960'>y(t)</span> <span m='916580'>in</span> <span
  m='916720'>terms</span> <span m='917040'>of</span> <span m='917130'>an</span>
  <span m='917210'>impulse</span> <span m='917700'>function.</span> <span
  m='918800'>There,</span> <span m='919360'>I</span> <span
  m='919540'>have</span> <span m='919760'>to</span> <span
  m='919950'>admit,</span> <span m='920350'>is</span> <span m='920940'>a</span>
  <span m='921050'>little</span> <span m='921270'>bit</span> <span
  m='921440'>of</span> <span m='921540'>detail</span> <span m='922160'>to</span>
  <span m='922270'>kind</span> <span m='922460'>of</span> <span
  m='922540'>focus</span> <span m='923020'>on</span> <span m='923530'>at</span>
  <span m='923690'>your</span> <span m='923830'>leisure,</span> <span
  m='924820'>but</span> <span m='925160'>this</span> <span m='925420'>is</span>
  <span m='925660'>the</span> <span m='925760'>general</span> <span
  m='926350'>flow</span> <span m='926700'>of</span> <span m='926770'>the</span>
  <span m='926850'>strategy.</span> </p><p><span m='928300'>So</span> <span
  m='928640'>what</span> <span m='928770'>we</span> <span m='928920'>have</span>
  <span m='929070'>now</span> <span m='929540'>is</span> <span
  m='930690'>an</span> <span m='930940'>integral</span> <span
  m='931820'>that</span> <span m='932010'>tells</span> <span
  m='932250'>us</span> <span m='932290'>that</span> <span
  m='932500'>tells</span> <span m='932840'>us</span> <span m='933060'>how</span>
  <span m='933260'>x(t)</span> <span m='934800'>can</span> <span
  m='935010'>be</span> <span m='935180'>described</span> <span
  m='936630'>as</span> <span m='937310'>a</span> <span m='937410'>sum</span>
  <span m='938050'>or</span> <span m='938250'>linear</span> <span
  m='938640'>combination</span> <span m='939730'>involving</span> <span
  m='940540'>impulses.</span> <span m='943120'>This</span> <span
  m='943320'>bottom</span> <span m='943610'>equation,</span> <span
  m='944120'>by</span> <span m='944300'>the</span> <span m='944400'>way,</span>
  <span m='944900'>is</span> <span m='945130'>often</span> <span
  m='945410'>referred</span> <span m='945870'>to</span> <span
  m='946240'>as</span> <span m='946430'>the</span> <span
  m='946510'>sifting</span> <span m='946970'>integral.</span> <span
  m='948170'>In</span> <span m='948400'>essence,</span> <span
  m='948750'>what</span> <span m='948900'>it</span> <span m='949010'>says</span>
  <span m='949540'>is</span> <span m='949840'>that</span> <span
  m='950200'>if</span> <span m='950430'>I</span> <span m='951070'>take</span>
  <span m='951320'>a</span> <span m='951400'>time</span> <span
  m='951670'>function</span> <span m='952130'>x(t)</span> <span
  m='952820'>and</span> <span m='952940'>put</span> <span m='953090'>it</span>
  <span m='953170'>through</span> <span m='953340'>that</span> <span
  m='953580'>integral,</span> <span m='954700'>the</span> <span
  m='954860'>impulse</span> <span m='955570'>as</span> <span
  m='955860'>it</span> <span m='956720'>zips</span> <span m='957110'>by</span>
  <span m='957990'>generates</span> <span m='958580'>x(t)</span> <span
  m='959140'>all</span> <span m='959330'>over</span> <span
  m='959610'>again.</span> </p><p><span m='962070'>Now,</span> <span
  m='963030'>at</span> <span m='963160'>first</span> <span
  m='963430'>glance,</span> <span m='963790'>what</span> <span
  m='963950'>it</span> <span m='964060'>could</span> <span
  m='964200'>look</span> <span m='964450'>like</span> <span m='965050'>is</span>
  <span m='965350'>that</span> <span m='965830'>we've</span> <span
  m='966000'>taken</span> <span m='966340'>a</span> <span m='966410'>time</span>
  <span m='966690'>function</span> <span m='967150'>x(t)</span> <span
  m='968350'>and</span> <span m='968490'>proceeded</span> <span
  m='969410'>to</span> <span m='969570'>represent</span> <span
  m='970120'>it</span> <span m='970400'>in</span> <span m='970550'>a</span>
  <span m='970610'>very</span> <span m='971240'>complicated</span> <span
  m='972000'>way,</span> <span m='972440'>in</span> <span
  m='972560'>terms</span> <span m='972890'>of</span> <span
  m='972990'>itself,</span> <span m='973930'>and</span> <span
  m='974080'>one</span> <span m='974270'>could</span> <span
  m='974440'>ask,</span> <span m='974780'>why</span> <span
  m='975010'>bother</span> <span m='975380'>doing</span> <span
  m='975700'>that?</span> <span m='976720'>And</span> <span
  m='976850'>the</span> <span m='976930'>reason,</span> <span
  m='978020'>going</span> <span m='978330'>back</span> <span
  m='978820'>to</span> <span m='978940'>what</span> <span m='979140'>our</span>
  <span m='979740'>strategy</span> <span m='980350'>was,</span> <span
  m='981850'>is</span> <span m='982430'>that</span> <span m='982940'>what</span>
  <span m='983510'>we</span> <span m='983670'>want</span> <span
  m='983910'>to</span> <span m='984010'>do</span> <span m='985050'>is</span>
  <span m='985770'>exploit</span> <span m='986710'>the</span> <span
  m='986810'>property</span> <span m='987610'>of</span> <span
  m='987740'>linearity.</span> <span m='989240'>So</span> <span
  m='990030'>by</span> <span m='990630'>describing</span> <span
  m='991840'>a</span> <span m='991960'>time</span> <span
  m='992260'>function</span> <span m='993990'>as</span> <span
  m='994170'>a</span> <span m='994230'>linear</span> <span
  m='994630'>combination</span> <span m='995530'>of</span> <span
  m='995710'>weighted,</span> <span m='996070'>delayed</span> <span
  m='996420'>impulses,</span> <span m='997900'>as</span> <span
  m='998350'>in</span> <span m='998560'>effect</span> <span
  m='999370'>we've</span> <span m='999630'>done</span> <span
  m='1000540'>through</span> <span m='1001320'>this</span> <span
  m='1002150'>summation</span> <span m='1003260'>that</span> <span
  m='1003540'>corresponds</span> <span m='1004240'>to</span> <span
  m='1004350'>a</span> <span m='1004410'>decomposition</span> <span
  m='1005330'>in</span> <span m='1005420'>terms</span> <span
  m='1005740'>of</span> <span m='1005840'>impulses,</span> <span
  m='1007240'>we</span> <span m='1007410'>can</span> <span
  m='1007640'>now</span> <span m='1008190'>exploit</span> <span
  m='1009580'>linearity,</span> <span m='1010990'>specifically</span> <span
  m='1012090'>recognizing</span> <span m='1013200'>that</span> <span
  m='1013390'>the</span> <span m='1013550'>output</span> <span
  m='1014240'>of</span> <span m='1014350'>a</span> <span
  m='1014410'>linear</span> <span m='1014820'>system</span> <span
  m='1016640'>is</span> <span m='1016990'>the</span> <span
  m='1017090'>sum</span> <span m='1017630'>of</span> <span
  m='1018730'>the</span> <span m='1018820'>responses</span> <span
  m='1020060'>to</span> <span m='1020190'>these</span> <span
  m='1020440'>individual</span> <span m='1021090'>inputs.</span> </p><p><span
  m='1022120'>So</span> <span m='1023390'>with</span> <span
  m='1023680'>h_kDelta(t)</span> <span m='1027579'>corresponding</span> <span
  m='1028410'>to</span> <span m='1028530'>the</span> <span
  m='1028619'>response</span> <span m='1029750'>to</span> <span
  m='1030450'>delta_Delta(t-kDelta)</span> <span m='1033950'>and</span> <span
  m='1034150'>the</span> <span m='1034220'>rest</span> <span
  m='1034520'>of</span> <span m='1034589'>this</span> <span
  m='1034839'>stuff,</span> <span m='1035359'>the</span> <span
  m='1035770'>x(kDelta)</span> <span m='1036910'>and</span> <span
  m='1037060'>this</span> <span m='1037230'>little</span> <span
  m='1037490'>Delta</span> <span m='1038250'>are</span> <span
  m='1038700'>basically</span> <span m='1039150'>scale</span> <span
  m='1039530'>factors--</span> <span m='1041140'>for</span> <span
  m='1041290'>a</span> <span m='1041359'>linear</span> <span
  m='1041710'>system,</span> <span m='1042540'>then,</span> <span
  m='1043119'>if</span> <span m='1043260'>the</span> <span
  m='1043390'>input</span> <span m='1043819'>is</span> <span
  m='1044000'>expressed</span> <span m='1044530'>in</span> <span
  m='1044609'>this</span> <span m='1044839'>form,</span> <span
  m='1045630'>the</span> <span m='1045760'>output</span> <span
  m='1046119'>is</span> <span m='1046240'>expressed</span> <span
  m='1046760'>in</span> <span m='1046839'>this</span> <span
  m='1047079'>form,</span> <span m='1048446'>and</span> <span
  m='1048810'>again</span> <span m='1049230'>taking</span> <span
  m='1049610'>the</span> <span m='1049700'>limit</span> <span
  m='1049990'>as</span> <span m='1050140'>Delta</span> <span
  m='1050460'>goes</span> <span m='1050730'>to</span> <span
  m='1050850'>0,</span> <span m='1051930'>by</span> <span
  m='1052090'>definition,</span> <span m='1053220'>this</span> <span
  m='1053460'>corresponds</span> <span m='1054180'>to</span> <span
  m='1054310'>an</span> <span m='1054440'>integral.</span> <span
  m='1055710'>It's</span> <span m='1055870'>the</span> <span
  m='1055980'>integral</span> <span m='1056410'>that</span> <span
  m='1057680'>I</span> <span m='1057760'>indicate</span> <span
  m='1058190'>here</span> <span m='1058900'>with</span> <span
  m='1059170'>h_tau(t)</span> <span m='1060380'>corresponding</span> <span
  m='1061810'>to</span> <span m='1062430'>the</span> <span
  m='1062790'>impulse</span> <span m='1063260'>response</span> <span
  m='1065540'>due</span> <span m='1065760'>to</span> <span m='1066130'>an</span>
  <span m='1066260'>impulse</span> <span m='1067500'>occurring</span> <span
  m='1068120'>at</span> <span m='1068600'>time</span> <span
  m='1068960'>tau.</span> </p><p><span m='1070360'>Now,</span> <span
  m='1070540'>again,</span> <span m='1070850'>we</span> <span
  m='1070970'>can</span> <span m='1071140'>do</span> <span
  m='1072720'>the</span> <span m='1072800'>same</span> <span
  m='1073120'>thing.</span> <span m='1074580'>In</span> <span
  m='1074760'>particular,</span> <span m='1075990'>if</span> <span
  m='1076270'>the</span> <span m='1076370'>system</span> <span
  m='1076790'>is</span> <span m='1076900'>time-invariant,</span> <span
  m='1078490'>then</span> <span m='1078670'>the</span> <span
  m='1078760'>response</span> <span m='1079390'>to</span> <span
  m='1079500'>each</span> <span m='1079770'>of</span> <span
  m='1079860'>these</span> <span m='1080100'>delayed</span> <span
  m='1080440'>impulses</span> <span m='1082110'>is</span> <span
  m='1082250'>simply</span> <span m='1082840'>a</span> <span
  m='1082920'>delayed</span> <span m='1083370'>version</span> <span
  m='1084000'>of</span> <span m='1084140'>the</span> <span
  m='1084260'>impulse</span> <span m='1084700'>response,</span> <span
  m='1085970'>and</span> <span m='1086200'>so</span> <span m='1086710'>we</span>
  <span m='1086860'>can</span> <span m='1087030'>relate</span> <span
  m='1087870'>these</span> <span m='1088620'>individual</span> <span
  m='1089290'>terms.</span> <span m='1090160'>And</span> <span
  m='1090360'>in</span> <span m='1090470'>particular,</span> <span
  m='1091060'>then,</span> <span m='1091890'>the</span> <span
  m='1092000'>response</span> <span m='1092670'>to</span> <span
  m='1092810'>an</span> <span m='1092880'>impulse</span> <span
  m='1093500'>occurring</span> <span m='1094130'>at</span> <span
  m='1094370'>time</span> <span m='1094700'>t</span> <span m='1094900'>=</span>
  <span m='1095260'>tau</span> <span m='1096480'>is</span> <span
  m='1096640'>simply</span> <span m='1097040'>the</span> <span
  m='1097140'>response</span> <span m='1098470'>to</span> <span
  m='1098730'>an</span> <span m='1098850'>impulse</span> <span
  m='1099350'>occurring</span> <span m='1099750'>at</span> <span
  m='1099880'>time</span> <span m='1100160'>0</span> <span
  m='1101050'>shifted</span> <span m='1101590'>over</span> <span
  m='1102440'>to</span> <span m='1102560'>the</span> <span
  m='1102680'>time</span> <span m='1103020'>origin</span> <span
  m='1103640'>tau.</span> <span m='1104840'>Again,</span> <span
  m='1105370'>as</span> <span m='1105560'>we</span> <span m='1105660'>did</span>
  <span m='1105860'>before,</span> <span m='1107110'>we'll</span> <span
  m='1107280'>drop</span> <span m='1107580'>this</span> <span
  m='1107690'>subscript</span> <span m='1108300'>h_0,</span> <span
  m='1109600'>so</span> <span m='1110020'>h_0(t)</span> <span
  m='1112650'>we'll</span> <span m='1113010'>simply</span> <span
  m='1113410'>define</span> <span m='1114110'>as</span> <span
  m='1114700'>h(t).</span> <span m='1117090'>What</span> <span
  m='1117320'>we're</span> <span m='1117450'>left</span> <span
  m='1117790'>with</span> <span m='1118330'>when</span> <span
  m='1118480'>we</span> <span m='1118590'>do</span> <span
  m='1118820'>that</span> <span m='1119740'>is</span> <span
  m='1121000'>the</span> <span m='1121170'>description</span> <span
  m='1121960'>of</span> <span m='1122110'>a</span> <span
  m='1122150'>linear</span> <span m='1122550'>time-invariant</span> <span
  m='1123390'>system</span> <span m='1124450'>through</span> <span
  m='1124640'>this</span> <span m='1124890'>integral,</span> <span
  m='1126440'>which</span> <span m='1126690'>tells</span> <span
  m='1127100'>us</span> <span m='1127860'>how</span> <span
  m='1128070'>the</span> <span m='1128270'>output</span> <span
  m='1129390'>is</span> <span m='1129610'>related</span> <span
  m='1130530'>to</span> <span m='1131100'>the</span> <span
  m='1131270'>input</span> <span m='1132200'>and</span> <span
  m='1132560'>to</span> <span m='1133240'>the</span> <span
  m='1133370'>impulse</span> <span m='1133810'>response.</span> </p><p><span
  m='1134990'>Again,</span> <span m='1135540'>let's</span> <span
  m='1135850'>just</span> <span m='1136570'>quickly</span> <span
  m='1137590'>look</span> <span m='1137840'>at</span> <span
  m='1137950'>this</span> <span m='1138320'>from</span> <span
  m='1138600'>another</span> <span m='1138910'>perspective</span> <span
  m='1139570'>as</span> <span m='1139720'>we</span> <span m='1139830'>did</span>
  <span m='1140230'>in</span> <span m='1140380'>discrete</span> <span
  m='1140830'>time.</span> <span m='1143840'>Recall</span> <span
  m='1144260'>that</span> <span m='1144360'>what</span> <span
  m='1144530'>we've</span> <span m='1144730'>done</span> <span
  m='1145180'>is</span> <span m='1145490'>to</span> <span
  m='1146020'>take</span> <span m='1146680'>the</span> <span
  m='1147080'>continuous</span> <span m='1147740'>function,</span> <span
  m='1149650'>decompose</span> <span m='1150360'>it</span> <span
  m='1150570'>in</span> <span m='1150740'>terms</span> <span
  m='1151260'>of</span> <span m='1151540'>rectangles,</span> <span
  m='1153220'>and</span> <span m='1153430'>then</span> <span
  m='1154510'>each</span> <span m='1154800'>of</span> <span
  m='1154900'>these</span> <span m='1155120'>rectangles</span> <span
  m='1156620'>generates</span> <span m='1158010'>its</span> <span
  m='1158540'>individual</span> <span m='1159970'>response,</span> <span
  m='1162000'>and</span> <span m='1162230'>then</span> <span
  m='1162810'>these</span> <span m='1163030'>individual</span> <span
  m='1163600'>responses</span> <span m='1164510'>are</span> <span
  m='1164720'>added</span> <span m='1164970'>together.</span> <span
  m='1167930'>And as</span> <span m='1168120'>we</span> <span
  m='1168210'>go</span> <span m='1168380'>through</span> <span
  m='1168620'>that</span> <span m='1168870'>process,</span> <span
  m='1170170'>of</span> <span m='1170290'>course,</span> <span
  m='1171130'>there's</span> <span m='1171420'>a</span> <span
  m='1171480'>process</span> <span m='1172290'>whereby</span> <span
  m='1173550'>we</span> <span m='1174170'>let</span> <span
  m='1174350'>the</span> <span m='1174440'>approximation</span> <span
  m='1175610'>go</span> <span m='1175990'>to</span> <span m='1176380'>the</span>
  <span m='1177260'>representation</span> <span m='1178390'>of</span> <span
  m='1178470'>a</span> <span m='1178520'>smooth</span> <span
  m='1178900'>curve.</span> </p><p><span m='1180920'>Now,</span> <span
  m='1181940'>again,</span> <span m='1182510'>I</span> <span
  m='1182620'>stress</span> <span m='1183030'>if</span> <span
  m='1183160'>there</span> <span m='1183890'>is</span> <span
  m='1184050'>certainly</span> <span m='1184880'>a</span> <span
  m='1184940'>fair</span> <span m='1185200'>amount</span> <span
  m='1185550'>to</span> <span m='1185890'>kind</span> <span
  m='1186140'>of</span> <span m='1186450'>examine</span> <span
  m='1186950'>carefully</span> <span m='1187570'>there,</span> <span
  m='1188730'>but</span> <span m='1188950'>it's</span> <span
  m='1189080'>important</span> <span m='1189770'>to</span> <span
  m='1190050'>also</span> <span m='1190350'>reflect</span> <span
  m='1190920'>on</span> <span m='1191160'>what</span> <span
  m='1191340'>we've</span> <span m='1191530'>done,</span> <span
  m='1191850'>which</span> <span m='1193300'>is</span> <span
  m='1193440'>really</span> <span m='1193730'>pretty</span> <span
  m='1193980'>significant.</span> <span m='1195240'>What</span> <span
  m='1195390'>we've</span> <span m='1195590'>managed</span> <span
  m='1195970'>to</span> <span m='1196070'>accomplish</span> <span
  m='1197510'>is</span> <span m='1197800'>to</span> <span
  m='1198140'>exploit</span> <span m='1198710'>the</span> <span
  m='1198790'>properties</span> <span m='1199560'>of</span> <span
  m='1200040'>linearity</span> <span m='1200290'>and</span> <span
  m='1200420'>time</span> <span m='1200710'>invariance,</span> <span
  m='1202610'>so</span> <span m='1202930'>that</span> <span
  m='1203620'>the</span> <span m='1203720'>system</span> <span
  m='1204550'>could</span> <span m='1204700'>be</span> <span
  m='1204840'>represented</span> <span m='1206380'>in</span> <span
  m='1206580'>terms</span> <span m='1207090'>only</span> <span
  m='1207670'>of</span> <span m='1207860'>its</span> <span
  m='1208000'>response</span> <span m='1209250'>to</span> <span
  m='1209840'>an</span> <span m='1209980'>impulse</span> <span
  m='1210930'>at</span> <span m='1211130'>time</span> <span
  m='1211420'>0.</span> <span m='1212380'>So</span> <span m='1212590'>for</span>
  <span m='1212720'>a</span> <span m='1212790'>linear</span> <span
  m='1213170'>time-invariant</span> <span m='1213980'>system--</span> <span
  m='1214410'>quite</span> <span m='1214650'>amazingly,</span> <span
  m='1215260'>actually--</span> <span m='1216410'>if</span> <span
  m='1216560'>you</span> <span m='1216900'>know</span> <span
  m='1216985'>its</span> <span m='1217070'>response</span> <span
  m='1217580'>to</span> <span m='1217720'>an</span> <span
  m='1217780'>impulse</span> <span m='1218450'>at</span> <span
  m='1218630'>t</span> <span m='1218780'>=</span> <span m='1219120'>0</span>
  <span m='1219580'>or</span> <span m='1219800'>n</span> <span
  m='1219970'>=</span> <span m='1220280'>0,</span> <span
  m='1220670'>depending</span> <span m='1221100'>on</span> <span
  m='1221370'>discrete</span> <span m='1221780'>or</span> <span
  m='1221850'>continuous</span> <span m='1222470'>time,</span> <span
  m='1223480'>then</span> <span m='1223670'>in</span> <span
  m='1223780'>fact,</span> <span m='1224490'>through</span> <span
  m='1224740'>the</span> <span m='1224850'>convolution</span> <span
  m='1225580'>sum</span> <span m='1226130'>in</span> <span
  m='1226280'>discrete</span> <span m='1226730'>time</span> <span
  m='1227150'>or</span> <span m='1227270'>the</span> <span
  m='1227380'>convolution</span> <span m='1228040'>integral</span> <span
  m='1228500'>in</span> <span m='1228620'>continuous</span> <span
  m='1229200'>time,</span> <span m='1229990'>you</span> <span
  m='1230100'>can</span> <span m='1230260'>generate</span> <span
  m='1231130'>the</span> <span m='1231230'>response</span> <span
  m='1232000'>to</span> <span m='1232140'>an</span> <span
  m='1232230'>arbitrary</span> <span m='1232780'>input.</span> </p><p><span
  m='1236130'>Let</span> <span m='1236290'>me</span> <span
  m='1236440'>just</span> <span m='1236970'>introduce</span> <span
  m='1238130'>a</span> <span m='1238760'>small</span> <span
  m='1239110'>amount</span> <span m='1239440'>of</span> <span
  m='1239860'>notation.</span> <span m='1241560'>Again,</span> <span
  m='1242160'>reminding</span> <span m='1242720'>you</span> <span
  m='1244040'>of</span> <span m='1244610'>the</span> <span
  m='1245240'>convolution</span> <span m='1245950'>sum</span> <span
  m='1246440'>in</span> <span m='1246580'>the</span> <span
  m='1246660'>discrete-time</span> <span m='1247410'>case,</span> <span
  m='1248450'>which</span> <span m='1248930'>looks</span> <span
  m='1249420'>as</span> <span m='1249920'>I've</span> <span
  m='1250100'>indicated</span> <span m='1250680'>here--</span> <span
  m='1251080'>the</span> <span m='1251220'>sum</span> <span
  m='1251580'>of</span> <span m='1251730'>x[k]</span> <span
  m='1252510'>h[n-k]</span> <span m='1254980'>will</span> <span
  m='1255360'>have</span> <span m='1257390'>the</span> <span
  m='1257490'>requirement</span> <span m='1258070'>of</span> <span
  m='1258120'>making</span> <span m='1258430'>such</span> <span
  m='1258790'>frequent</span> <span m='1259160'>reference</span> <span
  m='1259990'>to</span> <span m='1260220'>convolution</span> <span
  m='1261300'>that</span> <span m='1262200'>it's</span> <span
  m='1262380'>convenient</span> <span m='1263300'>to</span> <span
  m='1263500'>notationally</span> <span m='1264190'>represent</span> <span
  m='1264750'>it</span> <span m='1264930'>as</span> <span m='1265170'>I</span>
  <span m='1265260'>have</span> <span m='1265530'>here</span> <span
  m='1265770'>with</span> <span m='1265890'>an</span> <span
  m='1265990'>asterisk.</span> <span m='1267380'>So</span> <span
  m='1267740'>x[n]</span> <span m='1269350'>*</span> <span
  m='1270350'>h[n]</span> <span m='1272200'>means</span> <span
  m='1272720'>or</span> <span m='1272820'>denotes</span> <span
  m='1273460'>the</span> <span m='1273560'>convolution</span> <span
  m='1274370'>of</span> <span m='1274550'>x[n]</span> <span
  m='1275060'>with</span> <span m='1275200'>h[n].</span> </p><p><span
  m='1277060'>And</span> <span m='1277260'>correspondingly</span> <span
  m='1278570'>in</span> <span m='1279310'>the</span> <span
  m='1279460'>continuous-time</span> <span m='1280330'>case,</span> <span
  m='1281260'>we</span> <span m='1281380'>have</span> <span
  m='1281590'>the</span> <span m='1281680'>convolution</span> <span
  m='1282400'>integral,</span> <span m='1284200'>which</span> <span
  m='1285140'>here</span> <span m='1285460'>is</span> <span
  m='1285700'>the</span> <span m='1285780'>sifting</span> <span
  m='1286230'>integral</span> </p><p><span m='1286670'>as</span> <span
  m='1286790'>we</span> <span m='1286900'>talked</span> <span
  m='1287250'>about,</span> <span m='1287670'>representing</span> <span
  m='1288330'>x(t)</span> <span m='1289210'>in</span> <span
  m='1289370'>terms</span> <span m='1290190'>of</span> <span
  m='1290660'>itself</span> <span m='1291730'>as</span> <span
  m='1291870'>a</span> <span m='1291930'>linear</span> <span
  m='1292240'>combination</span> <span m='1292930'>of</span> <span
  m='1293020'>delayed</span> <span m='1293350'>impulses.</span> <span
  m='1294800'>Here</span> <span m='1295330'>we</span> <span
  m='1295510'>have</span> <span m='1295740'>the</span> <span
  m='1295820'>convolution</span> <span m='1296510'>integral,</span> <span
  m='1297110'>and</span> <span m='1297220'>again</span> <span
  m='1298080'>we'll</span> <span m='1298200'>use</span> <span
  m='1298580'>the</span> <span m='1298750'>asterisk</span> <span
  m='1299490'>to</span> <span m='1299930'>denote</span> <span
  m='1300280'>convolution.</span> </p><p><span m='1303040'>Now,</span> <span
  m='1304450'>there's</span> <span m='1304690'>a</span> <span
  m='1304760'>lot</span> <span m='1304970'>about</span> <span
  m='1305300'>convolution</span> <span m='1306350'>that</span> <span
  m='1306520'>we'll</span> <span m='1306700'>want</span> <span
  m='1306880'>to</span> <span m='1306950'>talk</span> <span
  m='1307260'>about.</span> <span m='1307750'>There</span> <span
  m='1307830'>are</span> <span m='1307910'>properties</span> <span
  m='1308670'>of</span> <span m='1308780'>convolution</span> <span
  m='1309650'>which</span> <span m='1309910'>tell</span> <span
  m='1310110'>us</span> <span m='1310240'>about</span> <span
  m='1310490'>properties</span> <span m='1311040'>of</span> <span
  m='1311130'>linear</span> <span m='1311440'>time-invariant</span> <span
  m='1312230'>systems.</span> <span m='1313540'>Also,</span> <span
  m='1314390'>it's</span> <span m='1314580'>important</span> <span
  m='1315070'>to</span> <span m='1315160'>focus</span> <span
  m='1315860'>on</span> <span m='1316540'>the</span> <span
  m='1316640'>mechanics</span> <span m='1317560'>of</span> <span
  m='1317920'>implementing</span> <span m='1318500'>a</span> <span
  m='1318590'>convolution--</span> <span m='1319370'>in</span> <span
  m='1319510'>other</span> <span m='1319700'>words,</span> <span
  m='1320460'>understanding</span> <span m='1321260'>and</span> <span
  m='1321390'>generating</span> <span m='1321890'>some</span> <span
  m='1322050'>fluency</span> <span m='1322690'>and</span> <span
  m='1322780'>insight</span> <span m='1323810'>into</span> <span
  m='1324620'>what</span> <span m='1325250'>these</span> <span
  m='1326910'>particular</span> <span m='1327560'>sum</span> <span
  m='1328310'>and</span> <span m='1328460'>integral</span> <span
  m='1328860'>expressions</span> <span m='1329470'>mean.</span> </p><p><span
  m='1331080'>So</span> <span m='1331280'>let's</span> <span
  m='1331540'>first</span> <span m='1331870'>look</span> <span
  m='1332180'>at</span> <span m='1332900'>discrete-time</span> <span
  m='1333530'>convolution</span> <span m='1334590'>and</span> <span
  m='1335410'>examine</span> <span m='1335870'>more</span> <span
  m='1336060'>specifically</span> <span m='1337230'>what</span> <span
  m='1338450'>in</span> <span m='1338650'>essence</span> <span
  m='1339190'>the</span> <span m='1339270'>sum</span> <span
  m='1339900'>tells</span> <span m='1340330'>us</span> <span
  m='1340540'>to</span> <span m='1340680'>do</span> <span m='1341190'>in</span>
  <span m='1341320'>terms</span> <span m='1341680'>of</span> <span
  m='1341780'>manipulating</span> <span m='1342480'>the</span> <span
  m='1342550'>sequences.</span> <span m='1345960'>So</span> <span
  m='1346880'>returning</span> <span m='1347840'>to</span> <span
  m='1348790'>the</span> <span m='1349850'>expression</span> <span
  m='1350620'>for</span> <span m='1351930'>the</span> <span
  m='1352580'>convolution</span> <span m='1353320'>sum,</span> <span
  m='1354410'>as</span> <span m='1354890'>I</span> <span m='1355040'>show</span>
  <span m='1355420'>here,</span> <span m='1356780'>the</span> <span
  m='1356870'>sum</span> <span m='1357420'>of</span> <span
  m='1357910'>x[k]</span> <span m='1359960'>h[n-k]--</span> <span
  m='1362430'>let's</span> <span m='1363010'>focus</span> <span
  m='1363500'>in</span> <span m='1363650'>on</span> <span m='1363780'>an</span>
  <span m='1363890'>example</span> <span m='1364780'>where</span> <span
  m='1365440'>we</span> <span m='1365600'>choose</span> <span
  m='1366340'>x[n]</span> <span m='1367080'>as</span> <span m='1367280'>a</span>
  <span m='1367330'>unit</span> <span m='1367670'>step</span> <span
  m='1368750'>and</span> <span m='1369120'>h[n]</span> <span
  m='1369950'>as</span> <span m='1370640'>a</span> <span m='1370710'>real</span>
  <span m='1371000'>exponential</span> <span m='1371940'>times</span> <span
  m='1372280'>the</span> <span m='1372330'>a</span> <span
  m='1372510'>unit</span> <span m='1372690'>step.</span> <span
  m='1373900'>So</span> <span m='1374520'>the</span> <span
  m='1374620'>sequence</span> <span m='1375070'>x[n]</span> <span
  m='1376090'>is</span> <span m='1376880'>as</span> <span m='1377100'>I</span>
  <span m='1377190'>indicate</span> <span m='1377770'>here,</span> <span
  m='1378643'>and</span> <span m='1379510'>the</span> <span
  m='1379590'>sequence</span> <span m='1380090'>h[n]</span> <span
  m='1380950'>is</span> <span m='1381670'>an</span> <span
  m='1381790'>exponential</span> <span m='1382450'>for</span> <span
  m='1382560'>positive</span> <span m='1383080'>time</span> <span
  m='1383440'>and</span> <span m='1383530'>0</span> <span m='1383870'>for</span>
  <span m='1384030'>negative</span> <span m='1384480'>time.</span> <span
  m='1385760'>So</span> <span m='1385960'>we</span> <span
  m='1386090'>have</span> <span m='1386510'>x[n]</span> <span
  m='1387105'>and</span> <span m='1387350'>h[n],</span> <span
  m='1389020'>but</span> <span m='1389130'>now</span> <span
  m='1389320'>let's</span> <span m='1389580'>look</span> <span
  m='1389840'>back</span> <span m='1390140'>at</span> <span
  m='1390210'>the</span> <span m='1390340'>equation</span> <span
  m='1391260'>and</span> <span m='1392660'>let</span> <span
  m='1392840'>me</span> <span m='1392980'>stress</span> <span
  m='1393680'>that</span> <span m='1394660'>what</span> <span
  m='1394850'>we</span> <span m='1394980'>want</span> <span
  m='1395340'>is</span> <span m='1395550'>not</span> <span
  m='1395980'>x[n]</span> <span m='1396960'>and</span> <span
  m='1397170'>h[n]--</span> <span m='1398340'>we</span> <span
  m='1398490'>want</span> <span m='1398850'>x[k],</span> <span
  m='1400340'>because</span> <span m='1400690'>we're</span> <span
  m='1400820'>going</span> <span m='1401020'>to</span> <span
  m='1401120'>sum</span> <span m='1401440'>over</span> <span
  m='1401700'>k,</span> <span m='1402750'>and</span> <span
  m='1403030'>not</span> <span m='1403490'>h[k]</span> <span
  m='1404660'>but</span> <span m='1405000'>h[n-k].</span> </p><p><span
  m='1407970'>So</span> <span m='1408930'>we</span> <span
  m='1409080'>have</span> <span m='1409790'>then</span> <span
  m='1411230'>from</span> <span m='1411600'>x[n],</span> <span
  m='1412710'>it's</span> <span m='1413100'>straightforward</span> <span
  m='1413880'>to</span> <span m='1413970'>generate</span> <span
  m='1414550'>x[k].</span> <span m='1415220'>It's</span> <span
  m='1415490'>simply</span> <span m='1416050'>changing</span> <span
  m='1417000'>the</span> <span m='1417170'>index</span> <span
  m='1417620'>of</span> <span m='1417710'>summation.</span> <span
  m='1419580'>And</span> <span m='1419720'>what's</span> <span
  m='1420170'>h[n-k]?</span> <span m='1422310'>Well</span> <span
  m='1422590'>what's</span> <span m='1422840'>h[-k]?</span> <span
  m='1424740'>h[-k]</span> <span m='1426100'>is</span> <span
  m='1426330'>h[k]</span> <span m='1427640'>flipped</span> <span
  m='1427940'>over.</span> </p><p><span m='1429120'>So</span> <span
  m='1429750'>if</span> <span m='1430900'>this</span> <span
  m='1431360'>is</span> <span m='1431670'>what</span> <span
  m='1432850'>h[k]</span> <span m='1433550'>looks</span> <span
  m='1433910'>like,</span> <span m='1435400'>then</span> <span
  m='1437170'>this</span> <span m='1437790'>is</span> <span
  m='1438080'>what</span> <span m='1438660'>h[n-k]</span> <span
  m='1440140'>looks</span> <span m='1440440'>like.</span> <span
  m='1441690'>In</span> <span m='1441890'>essence,</span> <span
  m='1442690'>what</span> <span m='1443760'>the</span> <span
  m='1443920'>operation</span> <span m='1444620'>of</span> <span
  m='1444720'>convolution</span> <span m='1445670'>or</span> <span
  m='1445820'>the</span> <span m='1445920'>mechanics</span> <span
  m='1446480'>of</span> <span m='1446560'>convolution</span> <span
  m='1447300'>tells</span> <span m='1447640'>us</span> <span
  m='1447780'>to</span> <span m='1447910'>do</span> <span m='1449690'>is</span>
  <span m='1450530'>to</span> <span m='1450700'>take</span> <span
  m='1451290'>the</span> <span m='1451390'>sequence</span> <span
  m='1452260'>h[n-k],</span> <span m='1455080'>which</span> <span
  m='1455340'>is</span> <span m='1455540'>h[-k]</span> <span
  m='1456710'>positioned</span> <span m='1457310'>with</span> <span
  m='1457490'>its</span> <span m='1457650'>origin</span> <span
  m='1458310'>at</span> <span m='1458480'>k</span> <span m='1458730'>=</span>
  <span m='1459110'>n,</span> <span m='1460380'>and</span> <span
  m='1460900'>multiply</span> <span m='1461630'>this</span> <span
  m='1461870'>sequence</span> <span m='1462790'>by</span> <span
  m='1463100'>this</span> <span m='1463300'>sequence</span> <span
  m='1464300'>and</span> <span m='1464470'>sum</span> <span
  m='1464790'>the</span> <span m='1464880'>product</span> <span
  m='1465730'>from</span> <span m='1466570'>k</span> <span m='1466980'>=</span>
  <span m='1467700'>-infinity</span> <span m='1468170'>to</span> <span
  m='1468570'>+infinity.</span> <span m='1469780'>So</span> <span
  m='1470230'>if</span> <span m='1470440'>we</span> <span
  m='1470570'>were</span> <span m='1470760'>to</span> <span
  m='1471170'>compute,</span> <span m='1472370'>for</span> <span
  m='1472550'>example,</span> <span m='1475030'>the</span> <span
  m='1475200'>output</span> <span m='1475720'>at</span> <span
  m='1475910'>n</span> <span m='1476060'>=</span> <span m='1476410'>0--</span>
  <span m='1478080'>as</span> <span m='1478310'>I</span> <span
  m='1478410'>positioned</span> <span m='1479870'>this</span> <span
  m='1480100'>sequence</span> <span m='1480620'>here,</span> <span
  m='1480890'>this</span> <span m='1481100'>is</span> <span
  m='1481240'>at</span> <span m='1481480'>n</span> <span m='1481680'>=</span>
  <span m='1482000'>0--</span> <span m='1483000'>I</span> <span
  m='1483110'>would</span> <span m='1483290'>take</span> <span
  m='1483550'>this</span> <span m='1483810'>and</span> <span
  m='1483900'>multiply</span> <span m='1484460'>it</span> <span
  m='1484580'>by</span> <span m='1484770'>this</span> <span
  m='1485180'>and</span> <span m='1485380'>sum</span> <span
  m='1486280'>from</span> <span m='1486820'>-infinity</span> <span
  m='1487290'>to</span> <span m='1487700'>+infinity.</span> <span
  m='1489020'>Or,</span> <span m='1489630'>for</span> <span m='1489830'>n</span>
  <span m='1489960'>=</span> <span m='1490300'>1,</span> <span
  m='1490710'>I</span> <span m='1490820'>would</span> <span
  m='1490980'>position</span> <span m='1491450'>it</span> <span
  m='1491540'>here,</span> <span m='1491940'>for</span> <span
  m='1492130'>n</span> <span m='1492220'>=</span> <span m='1492500'>2,</span>
  <span m='1492740'>I</span> <span m='1492900'>would</span> <span
  m='1493080'>position</span> <span m='1493550'>it</span> <span
  m='1493620'>here.</span> </p><p><span m='1495470'>Well,</span> <span
  m='1495900'>you</span> <span m='1496060'>can</span> <span
  m='1496530'>kind</span> <span m='1496740'>of</span> <span
  m='1496840'>see</span> <span m='1497110'>what</span> <span
  m='1497290'>the</span> <span m='1497430'>idea</span> <span
  m='1497850'>is.</span> <span m='1498780'>Let's</span> <span
  m='1499160'>look</span> <span m='1499480'>at</span> <span
  m='1499600'>this</span> <span m='1500210'>a</span> <span
  m='1500310'>little</span> <span m='1500510'>more</span> <span
  m='1500750'>dynamically</span> <span m='1501650'>and</span> <span
  m='1501800'>see,</span> <span m='1502650'>in</span> <span
  m='1502770'>fact,</span> <span m='1503180'>how</span> <span
  m='1503510'>one</span> <span m='1503720'>sequence</span> <span
  m='1504260'>slides</span> <span m='1504680'>past</span> <span
  m='1505020'>the</span> <span m='1505190'>other,</span> <span
  m='1505990'>and</span> <span m='1506210'>how</span> <span
  m='1507030'>the</span> <span m='1507180'>output</span> <span
  m='1507610'>y[n]</span> <span m='1508590'>builds</span> <span
  m='1509040'>up</span> <span m='1509400'>to</span> <span m='1510760'>the</span>
  <span m='1511130'>correct</span> <span m='1511520'>answer.</span> </p><p><span
  m='1514950'>So</span> <span m='1515410'>the</span> <span
  m='1515540'>input</span> <span m='1516080'>that</span> <span
  m='1516240'>we're</span> <span m='1516390'>considering</span> <span
  m='1517030'>is</span> <span m='1517150'>a</span> <span m='1517230'>step</span>
  <span m='1517550'>input,</span> <span m='1518100'>which</span> <span
  m='1518410'>I</span> <span m='1518810'>show</span> <span
  m='1519130'>here,</span> <span m='1519920'>and</span> <span
  m='1520470'>the</span> <span m='1520620'>impulse</span> <span
  m='1521080'>response</span> <span m='1521780'>that</span> <span
  m='1522010'>we</span> <span m='1522400'>will</span> <span
  m='1522680'>convolve</span> <span m='1523050'>this</span> <span
  m='1523300'>with</span> <span m='1524020'>is</span> <span m='1524810'>a</span>
  <span m='1525060'>decaying</span> <span m='1525570'>exponential.</span> <span
  m='1526830'>Now,</span> <span m='1527160'>to</span> <span
  m='1527330'>form</span> <span m='1527600'>the</span> <span
  m='1527690'>convolution,</span> <span m='1528640'>we</span> <span
  m='1528730'>want</span> <span m='1528930'>the</span> <span
  m='1529010'>product</span> <span m='1529770'>of</span> <span
  m='1530080'>x[k]--</span> <span m='1531340'>not</span> <span
  m='1531580'>with</span> <span m='1531720'>h[k],</span> <span
  m='1532450'>but</span> <span m='1532760'>with</span> <span
  m='1532940'>h[n-k],</span> <span m='1534890'>corresponding</span> <span
  m='1535790'>to</span> <span m='1535990'>taking</span> <span
  m='1536430'>h[k]</span> <span m='1537330'>and</span> <span
  m='1537920'>reflecting</span> <span m='1538510'>it</span> <span
  m='1538600'>about</span> <span m='1539140'>the</span> <span
  m='1539260'>origin</span> <span m='1540190'>and</span> <span
  m='1540340'>then</span> <span m='1540490'>shifting</span> <span
  m='1540940'>it</span> <span m='1541020'>appropriately.</span> <span
  m='1542130'>So</span> <span m='1542340'>here</span> <span
  m='1542620'>we</span> <span m='1542750'>see</span> <span
  m='1543180'>h[n-k]</span> <span m='1544320'>for</span> <span
  m='1544550'>n</span> <span m='1544660'>=</span> <span m='1545050'>0,</span>
  <span m='1546280'>namely</span> <span m='1546860'>h[-k],</span> <span
  m='1548930'>and</span> <span m='1549440'>now</span> <span
  m='1549770'>h[1-k],</span> <span m='1551440'>which</span> <span
  m='1551660'>we'll</span> <span m='1551770'>show</span> <span
  m='1552050'>next,</span> <span m='1552570'>is</span> <span
  m='1553040'>this</span> <span m='1553520'>shifted</span> <span
  m='1553990'>to</span> <span m='1554090'>the</span> <span
  m='1554180'>right</span> <span m='1554540'>by</span> <span
  m='1554680'>one</span> <span m='1554950'>point.</span> <span
  m='1557670'>Here</span> <span m='1557830'>we</span> <span
  m='1557950'>have</span> <span m='1558180'>h[1-k]--</span> <span
  m='1560720'>shifting</span> <span m='1561150'>to</span> <span
  m='1561260'>the</span> <span m='1561350'>right</span> <span
  m='1561660'>by</span> <span m='1561790'>one</span> <span
  m='1562040'>more</span> <span m='1562280'>point</span> <span
  m='1562770'>is</span> <span m='1563300'>h[2-k],</span> <span
  m='1566990'>and</span> <span m='1567420'>shifting</span> <span
  m='1567870'>again</span> <span m='1568170'>to</span> <span
  m='1568360'>the</span> <span m='1568390'>right</span> <span
  m='1569320'>we'll</span> <span m='1569610'>have</span> <span
  m='1570090'>h[3-k].</span> </p><p><span m='1572880'>Now</span> <span
  m='1573450'>let's</span> <span m='1574180'>shift</span> <span
  m='1574980'>back</span> <span m='1575330'>to</span> <span
  m='1575460'>the</span> <span m='1575570'>left</span> <span
  m='1576710'>until</span> <span m='1578410'>n</span> <span
  m='1578630'>is</span> <span m='1578800'>negative,</span> <span
  m='1579530'>and</span> <span m='1580480'>then</span> <span
  m='1580930'>we'll</span> <span m='1581090'>begin</span> <span
  m='1581380'>the</span> <span m='1581470'>convolution.</span> <span
  m='1582210'>So</span> <span m='1582430'>here's</span> <span m='1582710'>n
  =</span> <span m='1583080'>0,</span> <span m='1585470'>n</span> <span
  m='1585610'>=</span> <span m='1586310'>-1,</span> <span m='1588060'>n</span>
  <span m='1588200'>=</span> <span m='1588900'>-2,</span> <span
  m='1590790'>and</span> <span m='1591160'>n</span> <span m='1591320'>=</span>
  <span m='1591980'>-3.</span> </p><p><span m='1592890'>Now,</span> <span
  m='1593310'>to</span> <span m='1593420'>form</span> <span
  m='1593710'>the</span> <span m='1593810'>convolution,</span> <span
  m='1594590'>we</span> <span m='1594720'>want</span> <span
  m='1594950'>the</span> <span m='1595030'>product</span> <span
  m='1595640'>of</span> <span m='1595790'>x[k]</span> <span
  m='1596530'>with</span> <span m='1596780'>h[n-k]</span> <span
  m='1598470'>summed</span> <span m='1598970'>from</span> <span
  m='1600010'>-infinity</span> <span m='1600520'>to</span> <span
  m='1600910'>+infinity.</span> <span m='1603090'>For</span> <span
  m='1603510'>n</span> <span m='1603740'>negative,</span> <span
  m='1604700'>that</span> <span m='1605120'>product</span> <span
  m='1605610'>is</span> <span m='1605730'>0,</span> <span m='1606280'>and</span>
  <span m='1606460'>therefore</span> <span m='1606870'>the result</span> <span
  m='1607360'>of</span> <span m='1607410'>the</span> <span
  m='1607490'>convolution</span> <span m='1608170'>is</span> <span
  m='1608280'>0.</span> <span m='1609440'>As</span> <span m='1610080'>we</span>
  <span m='1610530'>shift</span> <span m='1610840'>to</span> <span
  m='1610940'>the</span> <span m='1611040'>right,</span> <span
  m='1611380'>we'll</span> <span m='1611570'>build</span> <span
  m='1611890'>up</span> <span m='1612030'>the</span> <span
  m='1612130'>convolution,</span> <span m='1613000'>and</span> <span
  m='1613540'>the</span> <span m='1613650'>result</span> <span
  m='1614060'>of</span> <span m='1614120'>the</span> <span
  m='1614220'>convolution</span> <span m='1614900'>will</span> <span
  m='1615010'>be</span> <span m='1615110'>shown</span> <span
  m='1615510'>on</span> <span m='1615590'>the</span> <span
  m='1615660'>bottom</span> <span m='1615980'>trace.</span> </p><p><span
  m='1617330'>So</span> <span m='1618260'>we</span> <span
  m='1618370'>begin</span> <span m='1618670'>the</span> <span
  m='1618750'>process</span> <span m='1620100'>with</span> <span
  m='1620410'>n</span> <span m='1620640'>negative,</span> <span
  m='1621640'>and</span> <span m='1621780'>here</span> <span
  m='1621950'>we</span> <span m='1622040'>have</span> <span m='1622200'>n</span>
  <span m='1622320'>=</span> <span m='1623090'>-1.</span> <span
  m='1623730'>At</span> <span m='1624030'>n</span> <span m='1624210'>=</span>
  <span m='1624550'>0,</span> <span m='1625500'>we</span> <span
  m='1625630'>get</span> <span m='1625980'>our</span> <span
  m='1626120'>first</span> <span m='1626500'>non-zero</span> <span
  m='1627100'>contribution.</span> <span m='1629210'>Now</span> <span
  m='1629800'>as</span> <span m='1630460'>we</span> <span
  m='1630610'>shift</span> <span m='1631180'>further</span> <span
  m='1631920'>to</span> <span m='1632040'>the</span> <span
  m='1632120'>right</span> <span m='1632510'>corresponding</span> <span
  m='1633150'>to</span> <span m='1633310'>increasing</span> <span
  m='1634000'>n,</span> <span m='1634840'>we</span> <span
  m='1635010'>will</span> <span m='1635490'>accumulate</span> <span
  m='1636480'>more</span> <span m='1636810'>and</span> <span
  m='1636880'>more</span> <span m='1638020'>terms</span> <span
  m='1638820'>in</span> <span m='1639020'>the</span> <span
  m='1639110'>sum,</span> <span m='1639970'>and</span> <span
  m='1640250'>the</span> <span m='1640340'>convolution</span> <span
  m='1641430'>will</span> <span m='1641600'>build</span> <span
  m='1641940'>up.</span> <span m='1642960'>In</span> <span
  m='1643090'>particular</span> <span m='1643630'>for</span> <span
  m='1643750'>this</span> <span m='1643970'>example,</span> <span
  m='1645040'>the</span> <span m='1645130'>result</span> <span
  m='1645540'>of</span> <span m='1645590'>the</span> <span
  m='1645670'>convolution</span> <span m='1646870'>increases</span> <span
  m='1649160'>monotonically,</span> <span m='1649900'>asymptotically</span>
  <span m='1650040'>approaching</span> <span m='1650550'>a</span> <span
  m='1650640'>constant,</span> <span m='1651790'>and</span> <span
  m='1652170'>that</span> <span m='1652380'>constant,</span> <span
  m='1653080'>in</span> <span m='1653230'>fact,</span> <span
  m='1654130'>is</span> <span m='1654790'>just</span> <span
  m='1654990'>simply</span> <span m='1655430'>the</span> <span
  m='1655560'>accumulation</span> <span m='1656890'>of</span> <span
  m='1657280'>the</span> <span m='1657390'>values</span> <span
  m='1658150'>under</span> <span m='1658460'>the</span> <span
  m='1658630'>exponential.</span> </p><p><span m='1668780'>Now</span> <span
  m='1669000'>let's</span> <span m='1669440'>carry</span> <span
  m='1669740'>out</span> <span m='1669910'>the</span> <span
  m='1669990'>convolution</span> <span m='1670750'>this</span> <span
  m='1670950'>time</span> <span m='1671490'>with</span> <span
  m='1671645'>an</span> <span m='1671800'>input</span> <span
  m='1672690'>which</span> <span m='1672970'>is</span> <span
  m='1673140'>a</span> <span m='1673200'>rectangular</span> <span
  m='1673880'>pulse</span> <span m='1674260'>instead</span> <span
  m='1674550'>of</span> <span m='1674620'>a</span> <span m='1674680'>step</span>
  <span m='1675020'>input.</span> <span m='1675870'>Again,</span> <span
  m='1676220'>the</span> <span m='1676300'>same</span> <span
  m='1676630'>impulse</span> <span m='1677090'>response,</span> <span
  m='1677690'>namely</span> <span m='1678000'>a</span> <span
  m='1678040'>decaying</span> <span m='1678510'>exponential,</span> <span
  m='1679780'>and</span> <span m='1680300'>so</span> <span m='1680890'>we</span>
  <span m='1681010'>want</span> <span m='1681210'>to</span> <span
  m='1681270'>begin</span> <span m='1681900'>with</span> <span
  m='1682150'>h[n-k]</span> <span m='1683370'>and</span> <span
  m='1683630'>again</span> <span m='1684370'>with</span> <span
  m='1684650'>n</span> <span m='1684870'>negative</span> <span
  m='1685500'>shown</span> <span m='1685870'>here.</span> <span
  m='1686750'>Again,</span> <span m='1687060'>with</span> <span
  m='1687160'>n</span> <span m='1687380'>negative,</span> <span
  m='1688040'>there</span> <span m='1688410'>are</span> <span
  m='1689130'>no</span> <span m='1689450'>non-zero</span> <span
  m='1690110'>terms</span> <span m='1690570'>in</span> <span
  m='1690630'>the</span> <span m='1690710'>product,</span> <span
  m='1691700'>and</span> <span m='1691910'>so</span> <span
  m='1692340'>the</span> <span m='1692440'>convolution</span> <span
  m='1693280'>for</span> <span m='1693490'>n</span> <span
  m='1693670'>negative</span> <span m='1694510'>will</span> <span
  m='1694630'>be</span> <span m='1694810'>0</span> <span m='1695400'>as</span>
  <span m='1695600'>it</span> <span m='1695690'>was</span> <span
  m='1695960'>in</span> <span m='1696020'>the</span> <span
  m='1696080'>previous</span> <span m='1696600'>case.</span> <span
  m='1697390'>Again,</span> <span m='1697910'>on</span> <span
  m='1698020'>the</span> <span m='1698100'>bottom</span> <span
  m='1698430'>trace</span> <span m='1699080'>we'll</span> <span
  m='1699770'>show</span> <span m='1700250'>the</span> <span
  m='1700360'>result</span> <span m='1700820'>of</span> <span
  m='1700970'>the</span> <span m='1701230'>convolution</span> <span
  m='1702070'>as</span> <span m='1702320'>the</span> <span
  m='1702420'>impulse</span> <span m='1702840'>response</span> <span
  m='1703500'>slides</span> <span m='1703860'>along.</span> </p><p><span
  m='1705470'>At</span> <span m='1705600'>n</span> <span m='1705730'>=</span>
  <span m='1706020'>0,</span> <span m='1706380'>we</span> <span
  m='1706510'>get</span> <span m='1706690'>our</span> <span
  m='1706800'>first</span> <span m='1707130'>non-zero</span> <span
  m='1707700'>term.</span> <span m='1710040'>As</span> <span
  m='1710330'>n</span> <span m='1710810'>increases</span> <span
  m='1711450'>past</span> <span m='1712020'>0,</span> <span
  m='1712930'>we</span> <span m='1713120'>will</span> <span
  m='1713630'>begin</span> <span m='1714030'>to</span> <span
  m='1714150'>generate</span> <span m='1714650'>an</span> <span
  m='1714760'>output,</span> <span m='1715860'>basically</span> <span
  m='1716400'>the</span> <span m='1716500'>same</span> <span
  m='1716980'>as</span> <span m='1717540'>the</span> <span
  m='1717710'>output</span> <span m='1718350'>that</span> <span
  m='1718510'>we</span> <span m='1718630'>generated</span> <span
  m='1719220'>with</span> <span m='1719350'>a</span> <span
  m='1719390'>step</span> <span m='1719770'>input,</span> <span
  m='1721630'>until</span> <span m='1722600'>the</span> <span
  m='1723380'>impulse</span> <span m='1723900'>response</span> <span
  m='1724580'>reaches</span> <span m='1725040'>a</span> <span
  m='1725100'>point</span> <span m='1726150'>where</span> <span
  m='1727420'>as</span> <span m='1727690'>we</span> <span
  m='1727810'>slide</span> <span m='1728230'>further,</span> <span
  m='1728940'>we</span> <span m='1729070'>slide</span> <span
  m='1729590'>outside</span> <span m='1730160'>the</span> <span
  m='1730280'>interval</span> <span m='1730990'>where</span> <span
  m='1731550'>the</span> <span m='1731660'>rectangle</span> <span
  m='1732360'>is</span> <span m='1732480'>non-zero.</span> <span
  m='1733490'>So</span> <span m='1734570'>when</span> <span
  m='1735050'>we</span> <span m='1735560'>slide</span> <span
  m='1736070'>one</span> <span m='1736290'>point</span> <span
  m='1736630'>further</span> <span m='1736990'>from</span> <span
  m='1737160'>what's</span> <span m='1737300'>shown</span> <span
  m='1737690'>here,</span> <span m='1738870'>the</span> <span
  m='1739490'>output</span> <span m='1740140'>will</span> <span
  m='1740360'>now</span> <span m='1740990'>decay,</span> <span
  m='1742340'>corresponding</span> <span m='1743150'>to</span> <span
  m='1743270'>the</span> <span m='1743370'>fact</span> <span
  m='1744170'>that</span> <span m='1744850'>the</span> <span
  m='1746100'>impulse</span> <span m='1746580'>response</span> <span
  m='1747150'>is</span> <span m='1747270'>sliding</span> <span
  m='1747790'>outside</span> <span m='1748920'>the</span> <span
  m='1749100'>interval</span> <span m='1749810'>in</span> <span
  m='1749990'>which</span> <span m='1750520'>the</span> <span
  m='1750770'>input</span> <span m='1751290'>is</span> <span
  m='1751490'>non-zero.</span> <span m='1752790'>So,</span> <span
  m='1753140'>on</span> <span m='1753300'>the</span> <span
  m='1753370'>bottom</span> <span m='1753700'>trace</span> <span
  m='1754070'>we</span> <span m='1754170'>now</span> <span
  m='1754390'>see</span> <span m='1754790'>the</span> <span
  m='1754910'>result</span> <span m='1755310'>of</span> <span
  m='1755380'>the</span> <span m='1755480'>convolution.</span> </p><p><span
  m='1760470'>OK.</span> <span m='1761010'>So</span> <span
  m='1762490'>what</span> <span m='1763660'>you've</span> <span
  m='1763790'>seen,</span> <span m='1764100'>then,</span> <span
  m='1764560'>is</span> <span m='1765290'>an</span> <span
  m='1765380'>example</span> <span m='1766120'>of</span> <span
  m='1766740'>discrete-time</span> <span m='1767450'>convolution.</span> <span
  m='1769010'>Let's</span> <span m='1769350'>now</span> <span
  m='1770010'>look</span> <span m='1770460'>at</span> <span
  m='1770880'>an</span> <span m='1771010'>example</span> <span
  m='1771840'>of</span> <span m='1772580'>continuous-time</span> <span
  m='1773470'>convolution.</span> <span m='1775340'>As</span> <span
  m='1775540'>you</span> <span m='1775650'>might</span> <span
  m='1775860'>expect,</span> <span m='1776640'>continuous-time</span> <span
  m='1777430'>convolution</span> <span m='1778140'>operates</span> <span
  m='1778790'>in</span> <span m='1779230'>exactly</span> <span
  m='1779730'>the</span> <span m='1779810'>same</span> <span
  m='1780120'>way.</span> <span m='1782030'>Continuous-time</span> <span
  m='1782820'>convolution--</span> <span m='1784530'>we</span> <span
  m='1784690'>have</span> <span m='1785290'>the</span> <span
  m='1785780'>expression</span> <span m='1786370'>again</span> <span
  m='1787250'>y(t)</span> <span m='1788190'>is</span> <span
  m='1788660'>an</span> <span m='1788800'>integral</span> <span
  m='1789740'>with</span> <span m='1790650'>now</span> <span
  m='1791750'>x(tau)</span> <span m='1792810'>and</span> <span
  m='1792970'>h(t-tau).</span> <span m='1795270'>It</span> <span
  m='1795390'>has</span> <span m='1795930'>exactly</span> <span
  m='1796550'>the</span> <span m='1796640'>same</span> <span
  m='1796950'>kind</span> <span m='1797200'>of</span> <span
  m='1797290'>form</span> <span m='1798560'>as</span> <span
  m='1799570'>we</span> <span m='1799730'>had</span> <span
  m='1800010'>previously</span> <span m='1801450'>for</span> <span
  m='1802210'>discrete-time</span> <span m='1802900'>convolution--</span> <span
  m='1805190'>and in</span> <span m='1805350'>fact,</span> <span
  m='1805680'>the</span> <span m='1805750'>mechanics</span> <span
  m='1806610'>of</span> <span m='1807190'>the</span> <span
  m='1807480'>continuous-time</span> <span m='1808190'>convolution</span> <span
  m='1808870'>are</span> <span m='1808990'>identical.</span> </p><p><span
  m='1810930'>So</span> <span m='1811840'>here</span> <span
  m='1812590'>is</span> <span m='1812740'>our</span> <span
  m='1812910'>example</span> <span m='1813510'>with</span> <span
  m='1813670'>x(t)</span> <span m='1814440'>equal</span> <span
  m='1814760'>to</span> <span m='1814900'>a</span> <span m='1815115'>unit</span>
  <span m='1815330'>step</span> <span m='1816190'>and</span> <span
  m='1816440'>h(t)</span> <span m='1817240'>now</span> <span
  m='1818250'>a</span> <span m='1818340'>real</span> <span
  m='1818670'>exponential</span> <span m='1819380'>times</span> <span
  m='1819680'>a</span> <span m='1819790'>unit</span> <span
  m='1820260'>step.</span> <span m='1822280'>I</span> <span
  m='1822370'>show</span> <span m='1823170'>here</span> <span
  m='1823980'>x(t),</span> <span m='1825220'>which</span> <span
  m='1825440'>is</span> <span m='1825590'>the</span> <span
  m='1825690'>unit</span> <span m='1825990'>step</span> <span
  m='1826620'>function.</span> <span m='1828330'>Here</span> <span
  m='1828600'>we</span> <span m='1828780'>have</span> <span
  m='1829790'>h(t),</span> <span m='1832120'>which</span> <span
  m='1832400'>is</span> <span m='1832680'>an</span> <span
  m='1832770'>exponential</span> <span m='1833400'>for</span> <span
  m='1833530'>positive</span> <span m='1834060'>time</span> <span
  m='1834590'>and</span> <span m='1835580'>0</span> <span m='1836340'>for</span>
  <span m='1836470'>negative</span> <span m='1836910'>time.</span> </p><p><span
  m='1838670'>Again,</span> <span m='1839430'>looking</span> <span
  m='1839820'>back</span> <span m='1840450'>at</span> <span
  m='1840990'>the</span> <span m='1841130'>expression</span> <span
  m='1841930'>for</span> <span m='1842120'>convolution,</span> <span
  m='1843960'>it's</span> <span m='1844180'>not</span> <span
  m='1844620'>x(t)</span> <span m='1845320'>that</span> <span
  m='1845440'>we</span> <span m='1845600'>want,</span> <span
  m='1846340'>it</span> <span m='1846560'>x(tau)</span> <span
  m='1847280'>that</span> <span m='1847430'>we</span> <span
  m='1847580'>want.</span> <span m='1848770'>And</span> <span
  m='1848940'>it's</span> <span m='1849110'>not</span> <span
  m='1850780'>h(t)</span> <span m='1852320'>or</span> <span
  m='1852560'>h(tau)</span> <span m='1853250'>that</span> <span
  m='1853370'>we</span> <span m='1853520'>want,</span> <span
  m='1853990'>it's</span> <span m='1854220'>h(t-tau).</span> <span
  m='1857310'>We</span> <span m='1857460'>plan</span> <span
  m='1857860'>to</span> <span m='1857960'>multiply</span> <span
  m='1858620'>these</span> <span m='1858880'>together</span> <span
  m='1860650'>and</span> <span m='1860860'>integrate</span> <span
  m='1861610'>over</span> <span m='1861880'>the</span> <span
  m='1862000'>variable</span> <span m='1862760'>tau,</span> <span
  m='1864140'>and</span> <span m='1864310'>that</span> <span
  m='1864570'>gives</span> <span m='1864840'>us</span> <span
  m='1864980'>the</span> <span m='1865140'>output</span> <span
  m='1865730'>at</span> <span m='1866040'>any</span> <span
  m='1866270'>given</span> <span m='1866600'>time.</span> <span
  m='1867700'>If</span> <span m='1867870'>we</span> <span
  m='1867960'>want</span> <span m='1868210'>it</span> <span
  m='1868430'>at</span> <span m='1868550'>another</span> <span
  m='1868870'>time,</span> <span m='1869410'>we</span> <span
  m='1869570'>change</span> <span m='1869890'>the</span> <span
  m='1869980'>value</span> <span m='1870390'>of</span> <span
  m='1870520'>t</span> <span m='1871550'>as</span> <span m='1872120'>an</span>
  <span m='1872260'>argument</span> <span m='1872770'>inside</span> <span
  m='1873180'>this</span> <span m='1873380'>integral.</span> </p><p><span
  m='1874580'>So</span> <span m='1875540'>here</span> <span
  m='1875770'>we</span> <span m='1875900'>have</span> <span
  m='1876520'>x(t),</span> <span m='1878876'>and</span> <span
  m='1879360'>here</span> <span m='1879650'>we</span> <span
  m='1879810'>have</span> <span m='1880230'>h(t),</span> <span
  m='1880930'>which</span> <span m='1881110'>isn't</span> <span
  m='1881340'>quite</span> <span m='1881560'>what</span> <span
  m='1881740'>we</span> <span m='1881860'>wanted.</span> <span
  m='1883210'>Here</span> <span m='1883520'>we</span> <span
  m='1883650'>have</span> <span m='1883870'>x(tau),</span> <span
  m='1884485'>and</span> <span m='1884720'>that's</span> <span
  m='1885040'>fine--</span> <span m='1885410'>it's</span> <span
  m='1885550'>just</span> <span m='1885830'>x(t)</span> <span
  m='1886430'>with</span> <span m='1886580'>t</span> <span
  m='1887180'>relabeled</span> <span m='1887670'>as</span> <span
  m='1887890'>tau.</span> <span m='1889410'>Now,</span> <span
  m='1890310'>what</span> <span m='1890590'>is</span> <span
  m='1892170'>h(t-tau)?</span> <span m='1893800'>Well,</span> <span
  m='1894210'>here's</span> <span m='1895720'>h(tau),</span> <span
  m='1898150'>and</span> <span m='1898440'>if</span> <span m='1898560'>we</span>
  <span m='1898670'>simply</span> <span m='1899100'>turn</span> <span
  m='1899370'>that</span> <span m='1899590'>over,</span> <span
  m='1900720'>here</span> <span m='1901260'>is</span> <span
  m='1901810'>h(t-tau).</span> <span m='1903820'>And</span> <span
  m='1904410'>h(t-tau)</span> <span m='1906460'>is</span> <span
  m='1907450'>positioned,</span> <span m='1908040'>then,</span> <span
  m='1908470'>at</span> <span m='1908930'>tau</span> <span m='1909610'>equal
  to</span> <span m='1910140'>t.</span> </p><p><span m='1912470'>As</span> <span
  m='1912620'>we</span> <span m='1912750'>change</span> <span
  m='1913140'>the</span> <span m='1913240'>value</span> <span
  m='1913660'>of</span> <span m='1913800'>t</span> <span m='1914670'>that</span>
  <span m='1914830'>change</span> <span m='1915250'>the</span> <span
  m='1915340'>position</span> <span m='1916180'>of</span> <span
  m='1916320'>this</span> <span m='1916450'>signal,</span> <span
  m='1919750'>now</span> <span m='1919970'>we</span> <span
  m='1920090'>multiply</span> <span m='1921120'>these</span> <span
  m='1921370'>two</span> <span m='1921590'>together</span> <span
  m='1922600'>and</span> <span m='1923020'>integrate</span> <span
  m='1923890'>from</span> <span m='1924430'>-infinity</span> <span
  m='1924910'>to</span> <span m='1925290'>+infinity</span> <span
  m='1926750'>with</span> <span m='1927560'>h(t-tau)</span> <span
  m='1928970'>positioned</span> <span m='1929680'>at</span> <span
  m='1929870'>the</span> <span m='1929960'>appropriate</span> <span
  m='1930490'>value</span> <span m='1930890'>of</span> <span
  m='1931040'>t.</span> <span m='1934600'>Again,</span> <span
  m='1936320'>it's</span> <span m='1936550'>best</span> <span
  m='1936880'>really</span> <span m='1937250'>to</span> <span
  m='1937380'>see</span> <span m='1937620'>this</span> <span
  m='1937810'>example</span> <span m='1938330'>and</span> <span
  m='1938430'>get</span> <span m='1938600'>the</span> <span
  m='1938700'>notion</span> <span m='1939950'>of</span> <span
  m='1940370'>the</span> <span m='1940440'>signal</span> <span
  m='1940790'>being</span> <span m='1941020'>flipped</span> <span
  m='1941590'>and</span> <span m='1942370'>the</span> <span
  m='1942470'>two</span> <span m='1942660'>signals</span> <span
  m='1943080'>sliding</span> <span m='1943510'>past</span> <span
  m='1943900'>each</span> <span m='1944110'>other,</span> <span
  m='1944780'>multiplying</span> <span m='1945780'>and</span> <span
  m='1945960'>integrating</span> <span m='1947120'>by</span> <span
  m='1948020'>looking</span> <span m='1948380'>at</span> <span
  m='1948530'>it</span> <span m='1948640'>dynamically</span> <span
  m='1949550'>and</span> <span m='1950320'>observing</span> <span
  m='1950910'>how</span> <span m='1951100'>the</span> <span
  m='1951260'>answer</span> <span m='1951560'>builds</span> <span
  m='1951890'>up.</span> </p><p><span m='1953970'>Again,</span> <span
  m='1954270'>the</span> <span m='1954400'>input</span> <span
  m='1954980'>that</span> <span m='1955480'>we</span> <span
  m='1955720'>consider</span> <span m='1956290'>is</span> <span
  m='1956520'>a</span> <span m='1956590'>step</span> <span
  m='1956930'>input.</span> <span m='1958300'>And again, we</span> <span
  m='1958440'>use</span> <span m='1958860'>an</span> <span
  m='1958980'>impulse</span> <span m='1959440'>response</span> <span
  m='1960190'>which</span> <span m='1960480'>is</span> <span
  m='1960880'>a</span> <span m='1961280'>decaying</span> <span
  m='1961800'>exponential.</span> <span m='1964250'>To</span> <span
  m='1964400'>form</span> <span m='1964680'>the</span> <span
  m='1964780'>convolution,</span> <span m='1965600'>we</span> <span
  m='1965810'>want</span> <span m='1966550'>the</span> <span
  m='1966640'>product</span> <span m='1967220'>of</span> <span
  m='1967800'>x(tau)--</span> <span m='1968840'>not</span> <span
  m='1969110'>with</span> <span m='1969260'>h(tau),</span> <span
  m='1970000'>but</span> <span m='1970250'>with</span> <span
  m='1970380'>h(t-tau).</span> <span m='1972040'>So</span> <span
  m='1972280'>we</span> <span m='1972400'>want</span> <span
  m='1972610'>h(t)</span> <span m='1973530'>time-reversed,</span> <span
  m='1974950'>and</span> <span m='1975530'>then</span> <span
  m='1975750'>shifted</span> <span m='1976180'>appropriately</span> <span
  m='1976890'>depending</span> <span m='1977380'>on</span> <span
  m='1977490'>the</span> <span m='1977570'>value</span> <span
  m='1978000'>of</span> <span m='1978110'>t.</span> </p><p><span
  m='1979190'>Let's</span> <span m='1979660'>first</span> <span
  m='1980360'>just</span> <span m='1980640'>look</span> <span
  m='1980870'>at</span> <span m='1980940'>h(t-tau)</span> <span
  m='1982820'>for</span> <span m='1983510'>t</span> <span
  m='1983750'>positive</span> <span m='1984480'>corresponding</span> <span
  m='1985140'>to</span> <span m='1985300'>shifting</span> <span
  m='1986300'>h(-tau)</span> <span m='1987190'>out</span> <span
  m='1987590'>to</span> <span m='1987760'>the</span> <span
  m='1987840'>right,</span> <span m='1989260'>and</span> <span
  m='1989510'>here</span> <span m='1989740'>we</span> <span
  m='1989880'>have</span> <span m='1990890'>t</span> <span
  m='1991710'>increasing.</span> <span m='1995810'>Here</span> <span
  m='1996170'>is</span> <span m='1996760'>t</span> <span
  m='1997570'>decreasing,</span> <span m='1998770'>and</span> <span
  m='1998990'>we'll</span> <span m='1999700'>want</span> <span
  m='1999880'>to</span> <span m='1999920'>begin</span> <span
  m='2000230'>the</span> <span m='2000310'>convolution</span> <span
  m='2001650'>with</span> <span m='2002290'>t</span> <span
  m='2002580'>negative,</span> <span m='2003890'>corresponding</span> <span
  m='2004650'>to</span> <span m='2004770'>shifting</span> <span
  m='2005430'>h(-tau)</span> <span m='2007420'>to</span> <span
  m='2007550'>the</span> <span m='2007630'>left.</span> </p><p><span
  m='2009030'>Now</span> <span m='2009210'>to</span> <span
  m='2009280'>form</span> <span m='2009540'>the</span> <span
  m='2009620'>convolution,</span> <span m='2010280'>we</span> <span
  m='2010390'>want</span> <span m='2010580'>the</span> <span
  m='2010660'>product</span> <span m='2011140'>of</span> <span
  m='2011230'>these</span> <span m='2011510'>two.</span> <span
  m='2012290'>For</span> <span m='2012420'>t</span> <span
  m='2012630'>negative,</span> <span m='2013650'>there</span> <span
  m='2014070'>are</span> <span m='2014300'>no</span> <span
  m='2014850'>non-zero</span> <span m='2016100'>contributions</span> <span
  m='2017750'>to</span> <span m='2018340'>the</span> <span
  m='2018820'>integral,</span> <span m='2019830'>and</span> <span
  m='2020030'>so</span> <span m='2020550'>the</span> <span
  m='2020630'>convolution</span> <span m='2021280'>will</span> <span
  m='2021430'>be</span> <span m='2021580'>0</span> <span m='2022200'>for</span>
  <span m='2022400'>t</span> <span m='2022580'>less</span> <span
  m='2022850'>than</span> <span m='2022960'>0.</span> <span
  m='2024090'>On</span> <span m='2024210'>the</span> <span
  m='2024280'>bottom</span> <span m='2024600'>trace,</span> <span
  m='2025480'>we</span> <span m='2025590'>show</span> <span
  m='2026150'>the</span> <span m='2026230'>result</span> <span
  m='2026640'>of</span> <span m='2026690'>the</span> <span
  m='2026780'>convolution,</span> <span m='2028090'>here</span> <span
  m='2029120'>for</span> <span m='2029300'>t</span> <span
  m='2030120'>negative,</span> <span m='2031470'>and</span> <span
  m='2032290'>for</span> <span m='2032450'>t</span> <span
  m='2033160'>less</span> <span m='2033470'>than</span> <span
  m='2033590'>0,</span> <span m='2034200'>we</span> <span
  m='2034390'>will</span> <span m='2034540'>continue</span> <span
  m='2035030'>to</span> <span m='2035130'>have</span> <span m='2035380'>0</span>
  <span m='2035880'>in</span> <span m='2035940'>the</span> <span
  m='2036030'>convolution.</span> </p><p><span m='2038490'>Now</span> <span
  m='2038910'>as</span> <span m='2039130'>t</span> <span
  m='2039620'>increases</span> <span m='2041340'>past</span> <span
  m='2042020'>0,</span> <span m='2042610'>we</span> <span
  m='2042790'>begin</span> <span m='2043420'>to</span> <span
  m='2043550'>get</span> <span m='2043910'>some</span> <span
  m='2044140'>non-zero</span> <span m='2044910'>contribution</span> <span
  m='2045910'>in</span> <span m='2046030'>the</span> <span
  m='2046100'>product,</span> <span m='2047620'>indicated</span> <span
  m='2048219'>by</span> <span m='2048360'>the</span> <span
  m='2048469'>fact</span> <span m='2048820'>that</span> <span
  m='2048949'>the</span> <span m='2049040'>convolution--</span> <span
  m='2049989'>the</span> <span m='2050110'>result</span> <span
  m='2050460'>of</span> <span m='2050520'>the</span> <span
  m='2050600'>convolution--</span> <span m='2051270'>starts</span> <span
  m='2051780'>to</span> <span m='2052290'>build</span> <span
  m='2052600'>up.</span> <span m='2054370'>As</span> <span m='2055120'>t</span>
  <span m='2055560'>increases</span> <span m='2056590'>further,</span> <span
  m='2057780'>we</span> <span m='2057969'>will</span> <span
  m='2058620'>get</span> <span m='2059110'>more</span> <span
  m='2059460'>and</span> <span m='2059540'>more</span> <span
  m='2059780'>non-zero</span> <span m='2060330'>contribution</span> <span
  m='2061350'>in</span> <span m='2061790'>the</span> <span
  m='2061989'>integrand.</span> <span m='2063540'>So,</span> <span
  m='2064440'>the</span> <span m='2064889'>result</span> <span
  m='2065330'>of</span> <span m='2065400'>the</span> <span
  m='2065480'>convolution</span> <span m='2066780'>will</span> <span
  m='2067030'>be</span> <span m='2067780'>a</span> <span
  m='2068270'>monotonically</span> <span m='2069159'>increasing</span> <span
  m='2070230'>function</span> <span m='2070679'>for</span> <span
  m='2070780'>this</span> <span m='2070980'>particular</span> <span
  m='2071469'>example,</span> <span m='2072530'>which</span> <span
  m='2073620'>asymptotically</span> <span m='2074139'>approaches</span> <span
  m='2074699'>a</span> <span m='2074770'>constant.</span> <span
  m='2076100'>That</span> <span m='2076330'>constant</span> <span
  m='2077030'>will</span> <span m='2077179'>be</span> <span
  m='2077420'>proportional</span> <span m='2078889'>to</span> <span
  m='2079400'>the</span> <span m='2079590'>area</span> <span
  m='2080080'>under</span> <span m='2080320'>the</span> <span
  m='2080469'>impulse</span> <span m='2080920'>response,</span> <span
  m='2081810'>because</span> <span m='2082210'>of</span> <span
  m='2082300'>the</span> <span m='2082389'>fact</span> <span
  m='2082909'>that</span> <span m='2083130'>we're</span> <span
  m='2083360'>convolving</span> <span m='2084190'>with</span> <span
  m='2084520'>a</span> <span m='2084600'>step</span> <span
  m='2084949'>input.</span> </p><p><span m='2099270'>Now</span> <span
  m='2099430'>let's</span> <span m='2099690'>carry</span> <span
  m='2100040'>out</span> <span m='2100180'>the</span> <span
  m='2100260'>convolution</span> <span m='2101480'>with</span> <span
  m='2101600'>an</span> <span m='2101720'>input</span> <span
  m='2102160'>which</span> <span m='2102460'>is</span> <span
  m='2102850'>a</span> <span m='2103030'>rectangular</span> <span
  m='2104210'>pulse--</span> <span m='2105110'>again,</span> <span
  m='2105430'>an</span> <span m='2105510'>impulse</span> <span
  m='2105930'>response</span> <span m='2106450'>which</span> <span
  m='2106640'>is</span> <span m='2106760'>an</span> <span
  m='2106850'>exponential.</span> <span m='2108420'>So</span> <span
  m='2108600'>to</span> <span m='2108690'>form</span> <span
  m='2108990'>the</span> <span m='2109090'>convolution,</span> <span
  m='2109790'>we</span> <span m='2109910'>want</span> <span
  m='2110520'>x(tau)</span> <span m='2111230'>with</span> <span
  m='2111430'>h(t-tau)--</span> <span m='2113710'>h(t-tau)</span> <span
  m='2114700'>shown</span> <span m='2115050'>here</span> <span
  m='2115350'>for</span> <span m='2115530'>t</span> <span
  m='2116170'>negative.</span> <span m='2118010'>To</span> <span
  m='2118070'>form</span> <span m='2118340'>the</span> <span
  m='2118430'>convolution,</span> <span m='2119170'>we</span> <span
  m='2119340'>take</span> <span m='2119990'>the</span> <span
  m='2120210'>integral</span> <span m='2120980'>of</span> <span
  m='2121780'>the</span> <span m='2121880'>product</span> <span
  m='2122400'>of</span> <span m='2122490'>these</span> <span
  m='2122790'>two,</span> <span m='2123550'>which</span> <span
  m='2123800'>again</span> <span m='2124510'>will</span> <span
  m='2124670'>be</span> <span m='2124860'>0</span> <span m='2125920'>for</span>
  <span m='2126710'>t</span> <span m='2126940'>less</span> <span
  m='2127230'>than</span> <span m='2127350'>0.</span> <span
  m='2128360'>The</span> <span m='2128440'>bottom</span> <span
  m='2128760'>trace</span> <span m='2129110'>shows</span> <span
  m='2129400'>the</span> <span m='2129480'>result</span> <span
  m='2129890'>of</span> <span m='2129950'>the</span> <span
  m='2130040'>convolution</span> <span m='2131360'>here,</span> <span
  m='2132150'>shown</span> <span m='2132500'>as</span> <span
  m='2132620'>0,</span> <span m='2133520'>and</span> <span m='2133700'>it</span>
  <span m='2133770'>will</span> <span m='2133940'>continue</span> <span
  m='2134380'>to</span> <span m='2134460'>be</span> <span m='2134620'>0</span>
  <span m='2135550'>until</span> <span m='2136370'>t</span> <span
  m='2136630'>becomes</span> <span m='2137130'>positive,</span> <span
  m='2138140'>at</span> <span m='2138260'>which</span> <span
  m='2138530'>point</span> <span m='2139000'>we</span> <span
  m='2139140'>build</span> <span m='2139510'>up</span> <span
  m='2140210'>some</span> <span m='2140990'>non-zero</span> <span
  m='2143210'>term</span> <span m='2143970'>in</span> <span
  m='2144610'>the</span> <span m='2145250'>integrand.</span> </p><p><span
  m='2147040'>Now</span> <span m='2147400'>as</span> <span m='2147590'>we</span>
  <span m='2147690'>slide</span> <span m='2148100'>further,</span> <span
  m='2149230'>until</span> <span m='2150390'>the</span> <span
  m='2151660'>impulse</span> <span m='2152150'>response</span> <span
  m='2153090'>shifts</span> <span m='2153540'>outside</span> <span
  m='2154150'>the</span> <span m='2154330'>interval</span> <span
  m='2155520'>in</span> <span m='2155690'>which</span> <span
  m='2156070'>the</span> <span m='2156180'>pulse</span> <span
  m='2156690'>is</span> <span m='2157370'>non-zero,</span> <span
  m='2158730'>the</span> <span m='2158870'>output</span> <span
  m='2159270'>will</span> <span m='2159430'>build</span> <span
  m='2159780'>up.</span> <span m='2160670'>But</span> <span
  m='2161070'>here</span> <span m='2161610'>we've</span> <span
  m='2161800'>now</span> <span m='2162760'>begun</span> <span
  m='2163190'>to</span> <span m='2163340'>leave</span> <span
  m='2163580'>that</span> <span m='2163810'>interval,</span> <span
  m='2164690'>and</span> <span m='2164890'>so</span> <span
  m='2165530'>the</span> <span m='2165700'>output</span> <span
  m='2166220'>will</span> <span m='2166360'>start</span> <span
  m='2166710'>to</span> <span m='2166790'>decay</span> <span
  m='2167270'>exponentially.</span> <span m='2169700'>As</span> <span
  m='2170200'>the</span> <span m='2170300'>impulse</span> <span
  m='2170800'>response</span> <span m='2171920'>slides</span> <span
  m='2172700'>further</span> <span m='2173110'>and</span> <span
  m='2173200'>further</span> <span m='2173680'>corresponding</span> <span
  m='2174490'>to</span> <span m='2174990'>increasing</span> <span
  m='2175690'>t,</span> <span m='2176990'>then</span> <span
  m='2178170'>the</span> <span m='2178370'>output</span> <span
  m='2179100'>will</span> <span m='2179720'>decay</span> <span
  m='2180410'>exponentially,</span> <span m='2181810'>representing</span> <span
  m='2182460'>the</span> <span m='2182550'>fact</span> <span
  m='2183390'>that</span> <span m='2183800'>there</span> <span
  m='2184140'>is</span> <span m='2184640'>less</span> <span
  m='2184980'>and</span> <span m='2185080'>less</span> <span
  m='2185890'>area</span> <span m='2186910'>in</span> <span
  m='2187460'>the</span> <span m='2187560'>product</span> <span
  m='2189510'>of</span> <span m='2189765'>x(tau)</span> <span
  m='2190450'>and</span> <span m='2190920'>h(t-tau).</span> <span
  m='2194580'>Asymptotically,</span> <span m='2195240'>this</span> <span
  m='2195450'>output</span> <span m='2196090'>will</span> <span
  m='2196690'>then</span> <span m='2196870'>approach</span> <span
  m='2197300'>0.</span> </p><p><span m='2200830'>OK.</span> <span
  m='2201140'>So</span> <span m='2201610'>you've</span> <span
  m='2201790'>seen</span> <span m='2202480'>convolution,</span> <span
  m='2204280'>you've</span> <span m='2204420'>seen</span> <span
  m='2204580'>the</span> <span m='2204650'>derivation</span> <span
  m='2205280'>of</span> <span m='2205360'>convolution,</span> <span
  m='2206260'>and</span> <span m='2206490'>kind</span> <span
  m='2206700'>of</span> <span m='2206770'>the</span> <span
  m='2206850'>graphical</span> <span m='2207870'>representation</span> <span
  m='2209000'>of</span> <span m='2209120'>convolution.</span> <span
  m='2210820'>Finally,</span> <span m='2211620'>let's</span> <span
  m='2212340'>work</span> <span m='2213200'>again</span> <span
  m='2213970'>with</span> <span m='2214170'>these</span> <span
  m='2214400'>two</span> <span m='2214600'>examples,</span> <span
  m='2215960'>and</span> <span m='2216550'>let's</span> <span
  m='2216880'>go</span> <span m='2217030'>through</span> <span
  m='2217430'>those</span> <span m='2217690'>two</span> <span
  m='2217860'>examples</span> <span m='2218410'>analytically</span> <span
  m='2219750'>so</span> <span m='2220020'>that</span> <span
  m='2220710'>we</span> <span m='2220870'>finally</span> <span
  m='2221300'>see</span> <span m='2221670'>how,</span> <span
  m='2222040'>analytically,</span> <span m='2223560'>the</span> <span
  m='2224000'>result</span> <span m='2224700'>develops</span> <span
  m='2225650'>for</span> <span m='2225770'>those</span> <span
  m='2225980'>same</span> <span m='2226260'>examples.</span> </p><p><span
  m='2230450'>Well, we</span> <span m='2230600'>have</span> <span
  m='2231090'>first</span> <span m='2231460'>the</span> <span
  m='2231550'>discrete-time</span> <span m='2232270'>case,</span> <span
  m='2233030'>and</span> <span m='2233190'>let's</span> <span
  m='2233400'>take</span> <span m='2233650'>our</span> <span
  m='2234060'>discrete-time</span> <span m='2234720'>example.</span> <span
  m='2236960'>In</span> <span m='2237130'>general,</span> <span
  m='2238020'>the</span> <span m='2238540'>convolution</span> <span
  m='2239280'>sum</span> <span m='2239820'>is</span> <span m='2240280'>as</span>
  <span m='2240810'>I've</span> <span m='2241210'>indicated</span> <span
  m='2241800'>here.</span> <span m='2243490'>This</span> <span
  m='2243880'>is</span> <span m='2244730'>just</span> <span
  m='2245130'>our</span> <span m='2245450'>expression</span> <span
  m='2246040'>from</span> <span m='2246230'>before,</span> <span
  m='2246790'>which</span> <span m='2247030'>is</span> <span
  m='2247770'>the</span> <span m='2247860'>convolution</span> <span
  m='2248590'>sum.</span> <span m='2251140'>If</span> <span
  m='2251270'>we</span> <span m='2251400'>take</span> <span
  m='2251670'>our</span> <span m='2251820'>two</span> <span
  m='2251980'>examples--</span> <span m='2253080'>the</span> <span
  m='2253420'>example</span> <span m='2254130'>of</span> <span
  m='2255030'>an</span> <span m='2255120'>input</span> <span
  m='2255650'>which</span> <span m='2255970'>is</span> <span
  m='2256680'>a</span> <span m='2256760'>unit</span> <span
  m='2257140'>step,</span> <span m='2258250'>and</span> <span
  m='2259200'>an</span> <span m='2259330'>impulse</span> <span
  m='2259760'>response,</span> <span m='2260580'>which</span> <span
  m='2260900'>is</span> <span m='2262190'>a</span> <span m='2262290'>real</span>
  <span m='2262590'>exponential</span> <span m='2263340'>multiplied</span> <span
  m='2263960'>by</span> <span m='2264170'>a</span> <span m='2264220'>unit</span>
  <span m='2264610'>step--</span> <span m='2266110'>we</span> <span
  m='2266270'>have</span> <span m='2267630'>then</span> <span
  m='2268490'>replacing</span> <span m='2269740'>x[k]</span> <span
  m='2270990'>by</span> <span m='2271860'>what</span> <span
  m='2272030'>we</span> <span m='2272140'>know</span> <span
  m='2272590'>the</span> <span m='2272720'>input</span> <span
  m='2273100'>to</span> <span m='2273200'>be,</span> <span
  m='2274220'>and</span> <span m='2274350'>h[n-k]</span> <span
  m='2276230'>by</span> <span m='2276360'>what</span> <span
  m='2276560'>we</span> <span m='2276690'>know</span> <span
  m='2277210'>the</span> <span m='2277310'>impulse</span> <span
  m='2277720'>response</span> <span m='2278240'>to</span> <span
  m='2278330'>be,</span> <span m='2279260'>the</span> <span
  m='2279410'>output</span> <span m='2280050'>is</span> <span
  m='2280700'>the</span> <span m='2280870'>expression</span> <span
  m='2281430'>that</span> <span m='2281550'>we</span> <span
  m='2281670'>have</span> <span m='2281940'>here.</span> </p><p><span
  m='2285020'>Now,</span> <span m='2285880'>in</span> <span
  m='2286060'>this</span> <span m='2286270'>expression--</span> <span
  m='2287240'>and</span> <span m='2287880'>you'll</span> <span
  m='2288040'>see</span> <span m='2288310'>this</span> <span
  m='2289480'>very</span> <span m='2289710'>generally</span> <span
  m='2290650'>and</span> <span m='2290950'>with</span> <span
  m='2291120'>some</span> <span m='2291250'>more</span> <span
  m='2291430'>complicated</span> <span m='2292080'>examples</span> <span
  m='2293270'>when</span> <span m='2294120'>you</span> <span
  m='2294300'>look</span> <span m='2294490'>at</span> <span
  m='2294660'>the</span> <span m='2295120'>text--</span> <span
  m='2297210'>as</span> <span m='2298570'>you</span> <span m='2298800'>go</span>
  <span m='2299060'>to</span> <span m='2299230'>evaluate</span> <span
  m='2299820'>these</span> <span m='2300050'>expressions,</span> <span
  m='2301620'>generally</span> <span m='2302530'>what</span> <span
  m='2302720'>happens</span> <span m='2303260'>is</span> <span
  m='2303450'>that</span> <span m='2303950'>the</span> <span
  m='2304040'>signals</span> <span m='2304690'>have</span> <span
  m='2304990'>different</span> <span m='2305430'>analytical</span> <span
  m='2306050'>forms</span> <span m='2306760'>in</span> <span
  m='2306900'>different</span> <span m='2307210'>regions.</span> <span
  m='2308380'>That's,</span> <span m='2308630'>in</span> <span
  m='2308720'>fact,</span> <span m='2309220'>what</span> <span
  m='2309420'>we</span> <span m='2309540'>have</span> <span
  m='2309800'>here.</span> </p><p><span m='2311100'>In</span> <span
  m='2311200'>particular,</span> <span m='2311840'>let's</span> <span
  m='2312310'>look</span> <span m='2312540'>at</span> <span
  m='2312620'>the</span> <span m='2312710'>sum,</span> <span
  m='2314400'>and</span> <span m='2315530'>what</span> <span
  m='2315850'>we</span> <span m='2316000'>observe</span> <span
  m='2316670'>first</span> <span m='2317150'>of</span> <span
  m='2317270'>all</span> <span m='2317810'>is</span> <span
  m='2318210'>that</span> <span m='2320480'>the</span> <span
  m='2320900'>limits</span> <span m='2321420'>on</span> <span
  m='2321570'>this</span> <span m='2321820'>sum</span> <span
  m='2322290'>are</span> <span m='2322410'>going</span> <span
  m='2322660'>to</span> <span m='2322750'>be</span> <span
  m='2322890'>modified,</span> <span m='2324630'>depending</span> <span
  m='2325330'>on</span> <span m='2325930'>where</span> <span
  m='2326650'>this</span> <span m='2326860'>unit</span> <span
  m='2327200'>step</span> <span m='2327650'>is</span> <span m='2327930'>0</span>
  <span m='2328350'>and</span> <span m='2328410'>non-zero.</span> <span
  m='2330390'>In</span> <span m='2330550'>particular,</span> <span
  m='2332190'>if</span> <span m='2332400'>we</span> <span
  m='2332530'>first</span> <span m='2332880'>consider</span> <span
  m='2333700'>what</span> <span m='2334270'>will</span> <span
  m='2334420'>turn</span> <span m='2334640'>out</span> <span
  m='2334760'>to</span> <span m='2334820'>be</span> <span m='2334940'>the</span>
  <span m='2335020'>simple</span> <span m='2335420'>case--</span> <span
  m='2335980'>namely,</span> <span m='2336380'>n</span> <span
  m='2336520'>less</span> <span m='2336810'>than</span> <span
  m='2336940'>0--</span> <span m='2339030'>for</span> <span m='2339230'>n</span>
  <span m='2339370'>less</span> <span m='2339620'>than</span> <span
  m='2339770'>0,</span> <span m='2341720'>this</span> <span
  m='2342120'>unit</span> <span m='2342530'>step</span> <span
  m='2344440'>is</span> <span m='2344690'>0</span> <span m='2346860'>for</span>
  <span m='2347990'>k</span> <span m='2348790'>greater</span> <span
  m='2349210'>than</span> <span m='2349400'>n.</span> <span
  m='2350640'>With</span> <span m='2350820'>n</span> <span
  m='2351000'>less</span> <span m='2351340'>than</span> <span
  m='2351700'>0,</span> <span m='2352610'>that</span> <span
  m='2352890'>means</span> <span m='2353480'>that</span> <span
  m='2353980'>this</span> <span m='2354190'>unit</span> <span
  m='2354570'>step</span> <span m='2355340'>never</span> <span
  m='2356820'>is</span> <span m='2357460'>non-zero</span> <span
  m='2358970'>for</span> <span m='2359140'>k</span> <span
  m='2359660'>positive.</span> </p><p><span m='2361480'>On</span> <span
  m='2361590'>the</span> <span m='2361710'>other</span> <span
  m='2361900'>hand,</span> <span m='2362840'>this</span> <span
  m='2363070'>unit</span> <span m='2363430'>step</span> <span
  m='2365290'>is</span> <span m='2365740'>never</span> <span
  m='2366040'>non-zero</span> <span m='2367230'>or</span> <span
  m='2367360'>always</span> <span m='2367730'>0</span> <span
  m='2368160'>for</span> <span m='2368350'>k</span> <span
  m='2368580'>negative.</span> <span m='2371350'>Let</span> <span
  m='2371540'>me</span> <span m='2371660'>just</span> <span
  m='2372190'>stress</span> <span m='2372580'>that</span> <span
  m='2372880'>by</span> <span m='2373410'>looking</span> <span
  m='2373740'>at</span> <span m='2373820'>the</span> <span
  m='2373910'>particular</span> <span m='2374480'>graphs,</span> <span
  m='2375590'>here</span> <span m='2376090'>is</span> <span
  m='2377820'>the</span> <span m='2377930'>unit</span> <span
  m='2378240'>step</span> <span m='2378550'>u[k].</span> <span
  m='2380840'>Here</span> <span m='2381260'>is</span> <span
  m='2382190'>the</span> <span m='2382290'>unit</span> <span
  m='2382520'>step</span> <span m='2382970'>u[n-k],</span> <span
  m='2385010'>and</span> <span m='2385790'>for</span> <span m='2386220'>n</span>
  <span m='2386970'>less</span> <span m='2387340'>than</span> <span
  m='2387500'>0,</span> <span m='2388080'>so</span> <span
  m='2388230'>that</span> <span m='2388420'>this</span> <span
  m='2388620'>point</span> <span m='2388920'>comes</span> <span
  m='2389210'>before</span> <span m='2389600'>this</span> <span
  m='2389850'>point,</span> <span m='2391280'>the</span> <span
  m='2391380'>product</span> <span m='2392120'>of</span> <span
  m='2392270'>these</span> <span m='2392550'>two</span> <span
  m='2393000'>is</span> <span m='2393190'>equal</span> <span
  m='2393540'>to</span> <span m='2393640'>0.</span> <span
  m='2394960'>That</span> <span m='2395180'>means</span> <span
  m='2395480'>there</span> <span m='2395615'>is</span> <span
  m='2395750'>no</span> <span m='2395980'>overlap</span> <span
  m='2396550'>between</span> <span m='2396950'>these</span> <span
  m='2397180'>two</span> <span m='2397390'>terms,</span> <span
  m='2398460'>and</span> <span m='2398730'>so</span> <span m='2399140'>it</span>
  <span m='2399940'>says</span> <span m='2400135'>that</span> <span
  m='2400330'>y[n],</span> <span m='2401520'>the</span> <span
  m='2401700'>output,</span> <span m='2402330'>is</span> <span
  m='2402530'>0</span> <span m='2403380'>for</span> <span m='2403580'>n</span>
  <span m='2403730'>less</span> <span m='2404030'>than</span> <span
  m='2404150'>0.</span> </p><p><span m='2405940'>Well,</span> <span
  m='2406170'>that</span> <span m='2406300'>was</span> <span
  m='2406470'>an</span> <span m='2406540'>easy</span> <span
  m='2406810'>one.</span> <span m='2408980'>For</span> <span
  m='2409125'>n</span> <span m='2409270'>greater</span> <span
  m='2409580'>than</span> <span m='2409740'>0,</span> <span
  m='2410410'>it's</span> <span m='2410660'>not</span> <span
  m='2411460'>quite</span> <span m='2411710'>as</span> <span
  m='2411800'>straightforward</span> <span m='2412770'>as</span> <span
  m='2413320'>coming</span> <span m='2413630'>out</span> <span
  m='2413790'>with</span> <span m='2413940'>the</span> <span
  m='2414080'>answer</span> <span m='2414370'>0.</span> <span
  m='2415520'>So</span> <span m='2415720'>now</span> <span
  m='2416290'>let's</span> <span m='2416570'>look</span> <span
  m='2416810'>at</span> <span m='2417090'>what</span> <span
  m='2417250'>happens</span> <span m='2418050'>when</span> <span
  m='2418540'>the</span> <span m='2418670'>two</span> <span
  m='2418830'>unit</span> <span m='2419270'>steps</span> <span
  m='2419610'>overlap,</span> <span m='2421180'>and</span> <span
  m='2421760'>this</span> <span m='2421980'>would</span> <span
  m='2422150'>correspond</span> <span m='2423580'>to</span> <span
  m='2425090'>what</span> <span m='2425280'>I've</span> <span
  m='2425430'>labeled</span> <span m='2425840'>here</span> <span
  m='2426240'>as</span> <span m='2426490'>interval</span> <span
  m='2426950'>2,</span> <span m='2427700'>namely</span> <span
  m='2428060'>for</span> <span m='2428260'>n</span> <span
  m='2428450'>greater</span> <span m='2428840'>than</span> <span
  m='2429050'>0.</span> <span m='2430470'>If</span> <span m='2430620'>we</span>
  <span m='2430720'>just</span> <span m='2431520'>look</span> <span
  m='2431810'>back</span> <span m='2432240'>at</span> <span
  m='2433100'>the</span> <span m='2433970'>summation</span> <span
  m='2435030'>that</span> <span m='2435190'>we</span> <span
  m='2435360'>had,</span> <span m='2436740'>the</span> <span
  m='2436840'>summation</span> <span m='2437510'>now</span> <span
  m='2439130'>corresponds</span> <span m='2440730'>to</span> <span
  m='2441330'>this</span> <span m='2441600'>unit</span> <span
  m='2441970'>step</span> <span m='2442990'>and</span> <span
  m='2443800'>this</span> <span m='2444070'>unit</span> <span
  m='2444430'>step,</span> <span m='2445180'>having</span> <span
  m='2445810'>some</span> <span m='2446060'>overlap.</span> </p><p><span
  m='2448260'>So</span> <span m='2449200'>for</span> <span
  m='2449400'>interval</span> <span m='2449820'>2,</span> <span
  m='2452490'>corresponding</span> <span m='2453280'>to</span> <span
  m='2453410'>n</span> <span m='2453640'>greater</span> <span
  m='2453960'>than</span> <span m='2454130'>0,</span> <span
  m='2455480'>we</span> <span m='2455620'>have</span> <span
  m='2456490'>u[k],</span> <span m='2458310'>the</span> <span
  m='2458400'>unit</span> <span m='2458850'>step.</span> <span
  m='2460150'>We</span> <span m='2460320'>have</span> <span
  m='2461610'>u[n-k],</span> <span m='2463570'>which</span> <span
  m='2463860'>is</span> <span m='2464340'>a</span> <span m='2464575'>unit</span>
  <span m='2464810'>step</span> <span m='2465100'>going</span> <span
  m='2465350'>backward</span> <span m='2465840'>in</span> <span
  m='2465980'>time,</span> <span m='2467170'>but</span> <span
  m='2468790'>which</span> <span m='2469520'>extends</span> <span
  m='2470470'>for</span> <span m='2470690'>positive</span> <span
  m='2471220'>values</span> <span m='2471720'>of</span> <span
  m='2471840'>n.</span> <span m='2473870'>If</span> <span m='2474040'>we</span>
  <span m='2474160'>think</span> <span m='2474410'>about</span> <span
  m='2474850'>multiplying</span> <span m='2475540'>these</span> <span
  m='2475780'>two</span> <span m='2475990'>together,</span> <span
  m='2477470'>we</span> <span m='2477760'>will</span> <span
  m='2477970'>get</span> <span m='2478240'>in</span> <span
  m='2478390'>the</span> <span m='2478470'>product</span> <span
  m='2480260'>unity</span> <span m='2481720'>for</span> <span
  m='2481830'>what</span> <span m='2482100'>values</span> <span
  m='2482530'>of</span> <span m='2482630'>k?</span> <span
  m='2484320'>Well,</span> <span m='2484760'>for</span> <span
  m='2484920'>k</span> <span m='2485840'>starting</span> <span
  m='2486340'>at</span> <span m='2486450'>0</span> <span
  m='2486890'>corresponding</span> <span m='2487470'>to</span> <span
  m='2487590'>one</span> <span m='2487760'>of</span> <span
  m='2487820'>the</span> <span m='2487900'>unit</span> <span
  m='2488330'>steps</span> <span m='2489040'>and</span> <span
  m='2489200'>ending</span> <span m='2489730'>at</span> <span
  m='2489927'>n</span> <span m='2490520'>corresponding</span> <span
  m='2491190'>to</span> <span m='2491320'>the</span> <span
  m='2491500'>other</span> <span m='2491640'>unit</span> <span
  m='2492110'>step.</span> <span m='2493270'>So</span> <span
  m='2494310'>we</span> <span m='2494430'>have</span> <span
  m='2494650'>an</span> <span m='2494740'>overlap</span> <span
  m='2495560'>between</span> <span m='2496040'>these</span> <span
  m='2496910'>for</span> <span m='2497040'>k</span> <span
  m='2497660'>equal</span> <span m='2498210'>to</span> <span m='2499070'>0, et
  cetera,</span> <span m='2500440'>up</span> <span m='2500670'>through</span>
  <span m='2500850'>the</span> <span m='2500950'>value</span> <span
  m='2501370'>n.</span> </p><p><span m='2504630'>Now,</span> <span
  m='2505240'>that</span> <span m='2505480'>means</span> <span
  m='2506060'>that</span> <span m='2506420'>in</span> <span
  m='2506590'>terms</span> <span m='2507170'>of</span> <span
  m='2507310'>the</span> <span m='2507440'>original</span> <span
  m='2507880'>sum,</span> <span m='2509650'>we</span> <span
  m='2509800'>can</span> <span m='2509990'>get</span> <span
  m='2510160'>rid</span> <span m='2510370'>of</span> <span
  m='2510460'>the</span> <span m='2510550'>unit</span> <span
  m='2510960'>steps</span> <span m='2511300'>involved</span> <span
  m='2512170'>by</span> <span m='2512310'>simply</span> <span
  m='2512700'>changing</span> <span m='2513170'>the</span> <span
  m='2513270'>limits</span> <span m='2513650'>on</span> <span
  m='2513800'>the</span> <span m='2513890'>sum.</span> <span
  m='2516210'>The</span> <span m='2516300'>limits</span> <span
  m='2516830'>now</span> <span m='2517650'>are</span> <span
  m='2517910'>from</span> <span m='2518110'>0</span> <span m='2519430'>to</span>
  <span m='2519610'>n,</span> <span m='2521600'>of</span> <span
  m='2521700'>the</span> <span m='2521820'>term</span> <span
  m='2522410'>alpha^(n-k).</span> <span m='2525680'>We</span> <span
  m='2525810'>had</span> <span m='2526020'>before</span> <span
  m='2526500'>a</span> <span m='2526620'>u[k]</span> <span
  m='2527250'>and</span> <span m='2527335'>u[n-k],</span> <span
  m='2528460'>and</span> <span m='2528590'>that</span> <span
  m='2528790'>disappeared</span> <span m='2530570'>because</span> <span
  m='2530990'>we</span> <span m='2531110'>dealt</span> <span
  m='2531360'>with</span> <span m='2531520'>that</span> <span
  m='2531760'>simply</span> <span m='2532050'>by</span> <span
  m='2532180'>modifying</span> <span m='2532810'>the</span> <span
  m='2532910'>limits.</span> <span m='2534740'>We</span> <span
  m='2534880'>now</span> <span m='2535090'>pull</span> <span
  m='2535490'>out</span> <span m='2535910'>the</span> <span
  m='2536020'>term</span> <span m='2536320'>alpha^n,</span> <span
  m='2538160'>because</span> <span m='2538970'>the</span> <span
  m='2539060'>summation</span> <span m='2539590'>is</span> <span
  m='2539750'>on</span> <span m='2539910'>k,</span> <span m='2540180'>not</span>
  <span m='2540460'>on</span> <span m='2540640'>n,</span> <span
  m='2540880'>so</span> <span m='2541050'>we</span> <span m='2541230'>can</span>
  <span m='2542060'>simply</span> <span m='2543950'>pull</span> <span
  m='2544350'>that</span> <span m='2544590'>term</span> <span
  m='2545240'>of</span> <span m='2545350'>the</span> <span
  m='2545440'>sum.</span> <span m='2549190'>We</span> <span
  m='2549360'>now</span> <span m='2549610'>have</span> <span
  m='2549820'>alpha^(-k),</span> <span m='2551630'>which</span> <span
  m='2551850'>we</span> <span m='2552000'>can</span> <span
  m='2552490'>rewrite</span> <span m='2553040'>as</span> <span
  m='2553810'>(alpha^(-1))^k.</span> </p><p><span m='2556480'>The</span> <span
  m='2556610'>upshot</span> <span m='2557030'>of</span> <span
  m='2557120'>all</span> <span m='2557340'>of</span> <span
  m='2557470'>this</span> <span m='2558300'>is</span> <span
  m='2558580'>that</span> <span m='2559110'>y[n]</span> <span
  m='2560100'>now</span> <span m='2560370'>we</span> <span
  m='2560480'>can</span> <span m='2560650'>reexpress</span> <span
  m='2562020'>as</span> <span m='2562500'>alpha^n,</span> <span
  m='2563960'>the</span> <span m='2564060'>sum</span> <span
  m='2564330'>from</span> <span m='2564520'>0</span> <span m='2564890'>to</span>
  <span m='2565040'>n</span> <span m='2565600'>of</span> <span
  m='2565785'>(alpha^(-1)^k.</span> <span m='2569460'>The</span> <span
  m='2569780'>question</span> <span m='2570130'>is,</span> <span
  m='2570260'>how</span> <span m='2570380'>do</span> <span m='2570490'>we</span>
  <span m='2571840'>evaluate</span> <span m='2572520'>that?</span> <span
  m='2574850'>It</span> <span m='2575030'>essentially</span> <span
  m='2575760'>corresponds</span> <span m='2576960'>to</span> <span
  m='2577330'>a</span> <span m='2577410'>finite</span> <span
  m='2577880'>number</span> <span m='2578180'>of</span> <span
  m='2578260'>terms</span> <span m='2578800'>in</span> <span
  m='2578880'>a</span> <span m='2578960'>geometric</span> <span
  m='2579570'>series.</span> <span m='2581060'>That,</span> <span
  m='2581720'>by</span> <span m='2581900'>the</span> <span
  m='2582000'>way,</span> <span m='2582540'>is</span> <span m='2583110'>a</span>
  <span m='2583170'>summation</span> <span m='2583970'>that</span> <span
  m='2584160'>will</span> <span m='2584410'>recur</span> <span
  m='2584770'>over</span> <span m='2585140'>and</span> <span
  m='2585210'>over</span> <span m='2585500'>and</span> <span
  m='2585560'>over</span> <span m='2585840'>and</span> <span
  m='2585900'>over</span> <span m='2586230'>again,</span> <span
  m='2587180'>and</span> <span m='2587430'>it's</span> <span
  m='2587570'>one</span> <span m='2588110'>that</span> <span
  m='2588710'>you</span> <span m='2588900'>should</span> <span
  m='2589700'>write</span> <span m='2589990'>down,</span> <span
  m='2590360'>write</span> <span m='2590590'>on</span> <span
  m='2590690'>your</span> <span m='2590800'>back</span> <span
  m='2591110'>pocket,</span> <span m='2591520'>write</span> <span
  m='2591730'>on</span> <span m='2591800'>the</span> <span
  m='2591870'>palm</span> <span m='2592210'>of</span> <span
  m='2592310'>your</span> <span m='2592460'>hand,</span> <span
  m='2593360'>or</span> <span m='2593450'>whatever</span> <span
  m='2593820'>it</span> <span m='2593910'>takes</span> <span
  m='2594190'>to</span> <span m='2594310'>remember</span> <span
  m='2594580'>it.</span> <span m='2595650'>What</span> <span
  m='2595910'>you'll</span> <span m='2596050'>see</span> <span
  m='2596410'>is</span> <span m='2596600'>it</span> <span
  m='2596750'>that</span> <span m='2596950'>will</span> <span
  m='2597170'>recur</span> <span m='2598630'>more</span> <span
  m='2598960'>or</span> <span m='2599000'>less</span> <span
  m='2600700'>throughout</span> <span m='2601100'>the</span> <span
  m='2601190'>course,</span> <span m='2602410'>and</span> <span
  m='2602900'>so</span> <span m='2603270'>it's</span> <span
  m='2603440'>one</span> <span m='2603630'>worth</span> <span
  m='2603910'>remembering.</span> </p><p><span m='2604970'>In</span> <span
  m='2605080'>particular,</span> <span m='2605980'>what</span> <span
  m='2606170'>the</span> <span m='2606250'>sum</span> <span
  m='2606790'>of</span> <span m='2606990'>a</span> <span
  m='2607240'>geometric</span> <span m='2609490'>series</span> <span
  m='2610090'>is, is</span> <span m='2611400'>what</span> <span
  m='2611520'>I've</span> <span m='2611660'>indicated</span> <span
  m='2612240'>here.</span> <span m='2612950'>We</span> <span
  m='2613090'>have</span> <span m='2613290'>the</span> <span
  m='2613380'>sum</span> <span m='2613940'>from</span> <span
  m='2614120'>0</span> <span m='2614490'>to</span> <span m='2614650'>r,</span>
  <span m='2615600'>of beta^k.</span> <span m='2618830'>It's</span> <span
  m='2619060'>1</span> <span m='2619320'>-</span> <span
  m='2619750'>beta^(r+1)--</span> <span m='2622430'>this</span> <span
  m='2622610'>is</span> <span m='2622740'>one</span> <span
  m='2623020'>more</span> <span m='2623480'>than</span> <span
  m='2624430'>the</span> <span m='2625980'>upper</span> <span
  m='2626220'>limit</span> <span m='2626680'>on</span> <span
  m='2627220'>the</span> <span m='2627340'>summation--</span> <span
  m='2628460'>and</span> <span m='2628670'>in</span> <span
  m='2628780'>the</span> <span m='2628870'>denominator</span> <span
  m='2629750'>is</span> <span m='2629990'>1</span> <span m='2630200'>-</span>
  <span m='2630580'>beta.</span> <span m='2631640'>So,</span> <span
  m='2632160'>this</span> <span m='2632340'>equation</span> <span
  m='2632860'>is</span> <span m='2632970'>important.</span> <span
  m='2635100'>There's</span> <span m='2635250'>no</span> <span
  m='2635420'>point</span> <span m='2635920'>in</span> <span
  m='2636310'>attempting</span> <span m='2636780'>to</span> <span
  m='2636920'>derive</span> <span m='2637420'>it.</span> <span
  m='2637720'>However</span> <span m='2638130'>you</span> <span
  m='2638280'>get</span> <span m='2638540'>to</span> <span
  m='2638750'>it,</span> <span m='2638950'>it's</span> <span
  m='2639130'>important</span> <span m='2640000'>to</span> <span
  m='2640520'>retain</span> <span m='2641010'>it.</span> </p><p><span
  m='2643460'>We</span> <span m='2643590'>can</span> <span
  m='2643740'>now</span> <span m='2644790'>use</span> <span
  m='2645230'>that</span> <span m='2646350'>summation</span> <span
  m='2647470'>in</span> <span m='2648210'>the</span> <span
  m='2648310'>expression</span> <span m='2648595'>that</span> <span
  m='2648880'>we</span> <span m='2649070'>just</span> <span
  m='2649330'>developed.</span> <span m='2651170'>So</span> <span
  m='2651380'>let's</span> <span m='2651600'>proceed</span> <span
  m='2652360'>to</span> <span m='2653360'>evaluate</span> <span
  m='2653970'>that</span> <span m='2654190'>sum</span> <span
  m='2654380'>in</span> <span m='2654570'>closed</span> <span
  m='2654980'>form.</span> <span m='2656930'>We</span> <span
  m='2657040'>now</span> <span m='2657970'>go</span> <span
  m='2658130'>back</span> <span m='2658820'>to</span> <span
  m='2659500'>the</span> <span m='2659660'>expression</span> <span
  m='2660920'>that</span> <span m='2661090'>we</span> <span
  m='2661220'>just</span> <span m='2661520'>worked</span> <span
  m='2661870'>out--</span> <span m='2662320'>y[n]</span> <span
  m='2662910'>is</span> <span m='2663040'>alpha^n,</span> <span
  m='2664750'>the</span> <span m='2664930'>sum</span> <span
  m='2665200'>from</span> <span m='2665370'>0</span> <span m='2665760'>to</span>
  <span m='2665920'>n,</span> <span m='2666850'>(alpha^(-1))^k.</span> <span
  m='2671950'>This</span> <span m='2672480'>plays</span> <span
  m='2672750'>the</span> <span m='2672840'>role</span> <span
  m='2673150'>of</span> <span m='2673240'>beta</span> <span
  m='2673850'>in</span> <span m='2673970'>the</span> <span
  m='2674090'>term</span> <span m='2674390'>that</span> <span
  m='2674520'>I</span> <span m='2674600'>just--</span> <span
  m='2675280'>in</span> <span m='2675400'>the</span> <span
  m='2675500'>expression</span> <span m='2675970'>then</span> <span
  m='2676120'>I</span> <span m='2676210'>just</span> <span
  m='2677040'>presented.</span> <span m='2679120'>So,</span> <span
  m='2680670'>using</span> <span m='2681610'>that</span> <span
  m='2682720'>result,</span> <span m='2683310'>we</span> <span
  m='2683500'>can</span> <span m='2683650'>rewrite</span> <span
  m='2684180'>this</span> <span m='2684410'>summation</span> <span
  m='2684940'>as</span> <span m='2685080'>I</span> <span
  m='2685170'>indicate</span> <span m='2685740'>here.</span> </p><p><span
  m='2689000'>The</span> <span m='2689270'>final</span> <span
  m='2689640'>result</span> <span m='2690070'>that</span> <span
  m='2690140'>we</span> <span m='2690300'>end</span> <span m='2690510'>up</span>
  <span m='2690700'>with</span> <span m='2691120'>after</span> <span
  m='2691830'>a</span> <span m='2691890'>certain</span> <span
  m='2692210'>amount</span> <span m='2692550'>of</span> <span
  m='2692640'>algebra</span> <span m='2693660'>is</span> <span
  m='2694260'>y[n]</span> <span m='2695180'>equal</span> <span
  m='2695630'>to</span> <span m='2696370'>(1</span> <span m='2696630'>-</span>
  <span m='2697000'>alpha^(n+1))</span> <span m='2699010'>/</span> <span
  m='2700120'>(1</span> <span m='2700350'>-</span> <span
  m='2700720'>alpha).</span> <span m='2702230'>Let</span> <span
  m='2702340'>me</span> <span m='2702440'>just</span> <span
  m='2702660'>kind</span> <span m='2702850'>of</span> <span
  m='2702940'>indicate</span> <span m='2704190'>with</span> <span
  m='2704340'>a</span> <span m='2704380'>few</span> <span
  m='2704610'>dots</span> <span m='2705050'>here</span> <span
  m='2707600'>that</span> <span m='2709560'>there</span> <span
  m='2709980'>is</span> <span m='2710170'>a</span> <span
  m='2710230'>certain</span> <span m='2710530'>amount</span> <span
  m='2710790'>of</span> <span m='2710870'>algebra</span> <span
  m='2711460'>required</span> <span m='2712170'>in</span> <span
  m='2712370'>going</span> <span m='2712880'>from</span> <span
  m='2713970'>this</span> <span m='2714190'>step</span> <span
  m='2714740'>to</span> <span m='2714870'>this</span> <span
  m='2715100'>step,</span> <span m='2715630'>and</span> <span
  m='2717330'>I'd</span> <span m='2717520'>like</span> <span
  m='2717690'>to</span> <span m='2717810'>leave</span> <span
  m='2718030'>you</span> <span m='2718170'>with</span> <span
  m='2718400'>the</span> <span m='2718470'>fun</span> <span
  m='2718710'>and</span> <span m='2718820'>opportunity</span> <span
  m='2719510'>of</span> <span m='2719620'>doing</span> <span
  m='2719910'>that</span> <span m='2720045'>at</span> <span
  m='2720180'>your</span> <span m='2720320'>leisure.</span> </p><p><span
  m='2723860'>The</span> <span m='2723950'>expression</span> <span
  m='2724440'>we</span> <span m='2724570'>have</span> <span
  m='2724860'>now</span> <span m='2725250'>for</span> <span
  m='2725420'>y[n],</span> <span m='2727020'>is</span> <span
  m='2727900'>y[n]</span> <span m='2728770'>=</span> <span m='2729510'>(1</span>
  <span m='2729720'>-</span> <span m='2730210'>alpha^(n+1))</span> <span
  m='2731350'>/</span> <span m='2731870'>(1</span> <span m='2732140'>-</span>
  <span m='2732500'>alpha).</span> <span m='2733560'>That's</span> <span
  m='2733850'>for</span> <span m='2734005'>n</span> <span
  m='2734160'>greater</span> <span m='2734530'>than</span> <span
  m='2734720'>0.</span> <span m='2735900'>We had</span> <span
  m='2736110'>found</span> <span m='2736250'>out</span> <span
  m='2736610'>previously</span> <span m='2737200'>there</span> <span
  m='2737370'>it</span> <span m='2737465'>was</span> <span m='2737560'>0</span>
  <span m='2737980'>for</span> <span m='2738210'>n</span> <span
  m='2738330'>less</span> <span m='2738630'>than</span> <span
  m='2738790'>0.</span> <span m='2740070'>Finally,</span> <span
  m='2740830'>if</span> <span m='2741070'>we</span> <span
  m='2741190'>were</span> <span m='2741370'>to</span> <span
  m='2741490'>plot</span> <span m='2741890'>this,</span> <span
  m='2742740'>what</span> <span m='2742960'>we</span> <span
  m='2743130'>would</span> <span m='2743670'>get</span> <span
  m='2744010'>is</span> <span m='2744750'>the</span> <span
  m='2745000'>graph</span> <span m='2745540'>that</span> <span
  m='2745940'>I</span> <span m='2746120'>indicate</span> <span
  m='2746630'>here.</span> <span m='2748310'>The</span> <span
  m='2748410'>first</span> <span m='2748720'>non-zero</span> <span
  m='2749120'>value</span> <span m='2749920'>occurs</span> <span
  m='2750510'>at</span> <span m='2750810'>n</span> <span m='2751000'>=</span>
  <span m='2751360'>0,</span> <span m='2752710'>and</span> <span
  m='2752950'>it</span> <span m='2753030'>has</span> <span m='2753300'>a</span>
  <span m='2753350'>height</span> <span m='2753770'>of</span> <span
  m='2753930'>1,</span> <span m='2755770'>and</span> <span
  m='2755950'>then</span> <span m='2756410'>the</span> <span
  m='2756500'>next</span> <span m='2756770'>non-zero</span> <span
  m='2757320'>value</span> <span m='2757880'>at</span> <span
  m='2757950'>1,</span> <span m='2758550'>and</span> <span
  m='2759530'>this</span> <span m='2759750'>has</span> <span
  m='2760000'>a</span> <span m='2760060'>height</span> <span
  m='2760450'>of</span> <span m='2760620'>1</span> <span m='2760840'>+</span>
  <span m='2761170'>alpha,</span> <span m='2762330'>and</span> <span
  m='2763050'>this</span> <span m='2763270'>is</span> <span m='2763410'>1</span>
  <span m='2763630'>+</span> <span m='2763940'>alpha</span> <span
  m='2764890'>+</span> <span m='2765110'>alpha^2.</span> <span
  m='2768760'>The</span> <span m='2769250'>sequence</span> <span
  m='2769750'>continues</span> <span m='2770310'>on</span> <span
  m='2771680'>like</span> <span m='2771990'>that</span> <span
  m='2772810'>and</span> <span m='2773810'>asymptotically</span> <span
  m='2773960'>approaches,</span> <span m='2774810'>as</span> <span
  m='2774990'>n</span> <span m='2775170'>goes</span> <span m='2775440'>to</span>
  <span m='2775550'>infinity,</span> <span m='2777730'>asymptotically</span>
  <span m='2777980'>approaches</span> <span m='2778500'>1</span> <span
  m='2778720'>/</span> <span m='2778950'>(1</span> <span m='2779200'>-</span>
  <span m='2779610'>alpha),</span> <span m='2780700'>which</span> <span
  m='2781130'>is</span> <span m='2781430'>consistent</span> <span
  m='2782300'>with</span> <span m='2782500'>the</span> <span
  m='2782630'>algebraic</span> <span m='2783300'>expression</span> <span
  m='2784180'>that</span> <span m='2784330'>we</span> <span
  m='2784480'>have,</span> <span m='2785670'>that</span> <span
  m='2785800'>we</span> <span m='2785950'>developed,</span> <span
  m='2787290'>and</span> <span m='2787780'>obviously</span> <span
  m='2788350'>of</span> <span m='2788460'>course</span> <span
  m='2788990'>is</span> <span m='2789160'>also</span> <span
  m='2789510'>consistent</span> <span m='2790020'>with</span> <span
  m='2790180'>the</span> <span m='2790250'>movie.</span> </p><p><span
  m='2792370'>That's</span> <span m='2792740'>our</span> <span
  m='2793640'>discrete-time</span> <span m='2794280'>example,</span> <span
  m='2794910'>which</span> <span m='2795130'>we</span> <span
  m='2795290'>kind</span> <span m='2795480'>of</span> <span
  m='2795560'>went</span> <span m='2795760'>through</span> <span
  m='2795930'>graphically</span> <span m='2797730'>with</span> <span
  m='2798050'>the</span> <span m='2798150'>transparencies,</span> <span
  m='2799270'>and</span> <span m='2799340'>we</span> <span
  m='2799490'>went</span> <span m='2799720'>through</span> <span
  m='2799980'>graphically</span> <span m='2800610'>with</span> <span
  m='2800760'>the</span> <span m='2800850'>movie,</span> <span
  m='2801200'>and</span> <span m='2801355'>now</span> <span
  m='2801510'>we've</span> <span m='2801640'>gone</span> <span
  m='2801870'>through</span> <span m='2802090'>analytically.</span> <span
  m='2803500'>Now</span> <span m='2803720'>let's</span> <span
  m='2804700'>look</span> <span m='2805160'>analytically</span> <span
  m='2806070'>at</span> <span m='2806670'>the</span> <span
  m='2807300'>continuous-time</span> <span m='2808150'>example,</span> <span
  m='2808690'>which</span> <span m='2809450'>pretty</span> <span
  m='2809640'>much</span> <span m='2809910'>flows</span> <span
  m='2810570'>in</span> <span m='2810690'>the</span> <span
  m='2810760'>same</span> <span m='2811110'>way</span> <span
  m='2811550'>as</span> <span m='2812090'>we've</span> <span
  m='2812250'>just</span> <span m='2812500'>gone</span> <span
  m='2812750'>through.</span> </p><p><span m='2815010'>Again,</span> <span
  m='2815690'>we</span> <span m='2815880'>have</span> <span
  m='2817050'>the</span> <span m='2817170'>convolution</span> <span
  m='2817910'>integral,</span> <span m='2818800'>which</span> <span
  m='2819110'>is</span> <span m='2819700'>the</span> <span
  m='2819820'>integral</span> <span m='2820910'>indicated</span> <span
  m='2821700'>at</span> <span m='2821910'>the</span> <span
  m='2822020'>top.</span> <span m='2825070'>Our</span> <span
  m='2825280'>example,</span> <span m='2825880'>you</span> <span
  m='2826030'>recall,</span> <span m='2826830'>was</span> <span
  m='2827240'>with</span> <span m='2827540'>x(t)</span> <span
  m='2828170'>as</span> <span m='2828320'>a</span> <span m='2828360'>unit</span>
  <span m='2828710'>step,</span> <span m='2830470'>and</span> <span
  m='2831250'>h(t)</span> <span m='2832650'>as</span> <span
  m='2832900'>an</span> <span m='2833040'>exponential</span> <span
  m='2834100'>times</span> <span m='2834450'>a</span> <span
  m='2834540'>unit</span> <span m='2834890'>step.</span> <span
  m='2835850'>So</span> <span m='2836550'>when</span> <span
  m='2836730'>we</span> <span m='2836850'>substitute</span> <span
  m='2837610'>those</span> <span m='2837930'>in,</span> <span
  m='2839090'>this</span> <span m='2839370'>then</span> <span
  m='2839650'>corresponds</span> <span m='2840450'>to</span> <span
  m='2840830'>x(t)</span> <span m='2841780'>and</span> <span
  m='2842030'>this</span> <span m='2842230'>corresponds</span> <span
  m='2843160'>to</span> <span m='2844470'>h(t-tau).</span> <span
  m='2847600'>Again,</span> <span m='2847990'>we</span> <span
  m='2848130'>have</span> <span m='2849630'>the</span> <span
  m='2849740'>same</span> <span m='2850990'>issue</span> <span
  m='2851340'>more</span> <span m='2851580'>or</span> <span
  m='2851640'>less,</span> <span m='2852080'>which</span> <span
  m='2852370'>is</span> <span m='2852620'>that</span> <span
  m='2853230'>inside</span> <span m='2853760'>that</span> <span
  m='2853960'>integral,</span> <span m='2854720'>there</span> <span
  m='2855220'>are</span> <span m='2855400'>two</span> <span
  m='2855610'>steps,</span> <span m='2856240'>one</span> <span
  m='2856450'>of</span> <span m='2856540'>them</span> <span
  m='2856690'>going</span> <span m='2856980'>forward</span> <span
  m='2857360'>in</span> <span m='2857460'>time</span> <span
  m='2857800'>and</span> <span m='2857920'>one</span> <span
  m='2858070'>of</span> <span m='2858130'>them</span> <span
  m='2858250'>going</span> <span m='2858920'>backward</span> <span
  m='2859360'>in</span> <span m='2859480'>time,</span> <span
  m='2860620'>and</span> <span m='2861210'>we</span> <span
  m='2861320'>need</span> <span m='2861520'>to</span> <span
  m='2861670'>examine</span> <span m='2863150'>when</span> <span
  m='2863390'>they</span> <span m='2863540'>overlap</span> <span
  m='2864060'>and</span> <span m='2864180'>when</span> <span
  m='2864340'>they</span> <span m='2864450'>don't.</span> <span
  m='2864810'>When</span> <span m='2864940'>they</span> <span
  m='2865040'>don't</span> <span m='2865300'>overlap,</span> <span
  m='2865940'>the</span> <span m='2866020'>product,</span> <span
  m='2866470'>of</span> <span m='2866570'>course,</span> <span
  m='2866880'>is</span> <span m='2867000'>0,</span> <span m='2868070'>and</span>
  <span m='2868310'>there's</span> <span m='2868460'>no</span> <span
  m='2868570'>point</span> <span m='2868890'>doing</span> <span
  m='2869150'>any</span> <span m='2869340'>integration</span> <span
  m='2870000'>because</span> <span m='2870790'>the</span> <span
  m='2870920'>integrand</span> <span m='2871400'>is</span> <span
  m='2871500'>0.</span> </p><p><span m='2872720'>So</span> <span
  m='2873060'>if</span> <span m='2873150'>we</span> <span
  m='2873270'>track</span> <span m='2873590'>it</span> <span
  m='2873690'>through,</span> <span m='2875070'>we</span> <span m='2875190'>have
  again</span> <span m='2876580'>Interval</span> <span m='2877010'>1,</span>
  <span m='2877950'>which</span> <span m='2878160'>is</span> <span
  m='2878290'>t</span> <span m='2878490'>less</span> <span
  m='2878780'>than</span> <span m='2878920'>0.</span> <span
  m='2880300'>For</span> <span m='2880390'>t</span> <span
  m='2880590'>less</span> <span m='2880850'>than</span> <span
  m='2880990'>0,</span> <span m='2881800'>this</span> <span
  m='2882290'>unit</span> <span m='2882545'>step,</span> <span
  m='2884020'>which</span> <span m='2884630'>only</span> <span
  m='2884920'>begins</span> <span m='2885430'>at</span> <span
  m='2886560'>tau</span> <span m='2886940'>=</span> <span m='2887210'>0,</span>
  <span m='2888380'>and</span> <span m='2888550'>this</span> <span
  m='2888770'>unit</span> <span m='2889140'>step</span> <span
  m='2890050'>which</span> <span m='2890370'>is</span> <span
  m='2890510'>0,</span> <span m='2892060'>by</span> <span m='2892220'>the</span>
  <span m='2892350'>time</span> <span m='2893250'>tau</span> <span
  m='2893600'>gets</span> <span m='2893810'>up</span> <span
  m='2893990'>to</span> <span m='2894130'>t</span> <span m='2894660'>and</span>
  <span m='2894820'>beyond.</span> <span m='2896170'>For</span> <span
  m='2896330'>t</span> <span m='2896560'>less</span> <span
  m='2896850'>than</span> <span m='2896980'>0,</span> <span
  m='2898060'>there's</span> <span m='2898290'>no</span> <span
  m='2898570'>overlap</span> <span m='2900240'>between</span> <span
  m='2901430'>the</span> <span m='2902240'>unit</span> <span
  m='2902590'>step</span> <span m='2902860'>going</span> <span
  m='2903120'>forward</span> <span m='2903560'>in</span> <span
  m='2903700'>time</span> <span m='2904240'>and</span> <span
  m='2904410'>the</span> <span m='2904480'>unit</span> <span
  m='2904780'>step</span> <span m='2905040'>going</span> <span
  m='2905280'>backward</span> <span m='2905730'>in</span> <span
  m='2905870'>time.</span> <span m='2907210'>Consequently,</span> <span
  m='2908350'>the</span> <span m='2908530'>integrand</span> <span
  m='2909070'>is</span> <span m='2909180'>equal</span> <span
  m='2909500'>to</span> <span m='2909590'>0,</span> <span m='2910540'>and</span>
  <span m='2910700'>consequently,</span> <span m='2911940'>the</span> <span
  m='2912090'>output</span> <span m='2912520'>is</span> <span
  m='2912640'>equal</span> <span m='2912930'>to</span> <span
  m='2913020'>0.</span> </p><p><span m='2920190'>We</span> <span
  m='2920400'>can</span> <span m='2921110'>likewise</span> <span
  m='2921820'>look</span> <span m='2922160'>at</span> <span
  m='2922640'>the</span> <span m='2922800'>interval</span> <span
  m='2923540'>where</span> <span m='2924160'>the</span> <span
  m='2924950'>two</span> <span m='2925140'>unit</span> <span
  m='2925520'>steps</span> <span m='2925970'>do</span> <span
  m='2926150'>overlap.</span> <span m='2928070'>In</span> <span
  m='2928210'>that</span> <span m='2928470'>case</span> <span
  m='2928840'>what</span> <span m='2928980'>happens</span> <span
  m='2929370'>again</span> <span m='2929810'>is</span> <span
  m='2930110'>that</span> <span m='2930280'>the</span> <span
  m='2930420'>overlap,</span> <span m='2931190'>in</span> <span
  m='2931380'>essence</span> <span m='2932200'>of</span> <span
  m='2932300'>the</span> <span m='2932390'>unit</span> <span
  m='2932710'>step,</span> <span m='2933040'>tells</span> <span
  m='2933470'>us,</span> <span m='2934690'>gives</span> <span
  m='2934930'>us</span> <span m='2935080'>a</span> <span
  m='2935120'>range</span> <span m='2935680'>on</span> <span
  m='2935940'>the</span> <span m='2936460'>integration--</span> <span
  m='2939320'>in</span> <span m='2939460'>particular,</span> <span
  m='2940670'>the</span> <span m='2940860'>two</span> <span
  m='2941090'>steps</span> <span m='2941690'>overlap</span> <span
  m='2942600'>when</span> <span m='2942770'>t</span> <span m='2942950'>is</span>
  <span m='2943090'>greater</span> <span m='2943400'>than</span> <span
  m='2943600'>0</span> <span m='2945530'>from</span> <span
  m='2946590'>tau</span> <span m='2946840'>=</span> <span m='2947170'>0</span>
  <span m='2947980'>to</span> <span m='2948110'>tau</span> <span
  m='2948580'>=</span> <span m='2948810'>t.</span> <span m='2950840'>For</span>
  <span m='2951150'>Interval</span> <span m='2951690'>2,</span> <span
  m='2952730'>for</span> <span m='2953190'>t</span> <span
  m='2953540'>greater</span> <span m='2953900'>than</span> <span
  m='2954080'>0--</span> <span m='2955140'>again,</span> <span
  m='2955790'>of</span> <span m='2955890'>course,</span> <span
  m='2956190'>we</span> <span m='2956310'>have</span> <span
  m='2957320'>this</span> <span m='2957530'>expression.</span> <span
  m='2959370'>This</span> <span m='2959590'>product</span> <span
  m='2960730'>of</span> <span m='2961430'>this</span> <span
  m='2961650'>unit</span> <span m='2961980'>step</span> <span
  m='2962510'>and</span> <span m='2962680'>this</span> <span
  m='2962850'>unit</span> <span m='2963220'>step</span> <span
  m='2964570'>is</span> <span m='2964740'>equal</span> <span
  m='2965090'>to</span> <span m='2965200'>1</span> <span m='2966360'>in</span>
  <span m='2967220'>this</span> <span m='2968770'>range,</span> <span
  m='2970810'>and</span> <span m='2971160'>so</span> <span
  m='2971350'>that</span> <span m='2971590'>allows</span> <span
  m='2972060'>us,</span> <span m='2972260'>then,</span> <span
  m='2973060'>to</span> <span m='2973710'>change</span> <span
  m='2974200'>the</span> <span m='2974310'>limits</span> <span
  m='2975130'>on</span> <span m='2975320'>the</span> <span
  m='2975440'>integral--</span> <span m='2976800'>instead</span> <span
  m='2977070'>of</span> <span m='2977180'>from</span> <span
  m='2977710'>-infinity</span> <span m='2978170'>to</span> <span
  m='2978570'>+infinity,</span> <span m='2979670'>we</span> <span
  m='2979800'>know</span> <span m='2980010'>that</span> <span
  m='2980160'>the</span> <span m='2980290'>integrand</span> <span
  m='2981060'>is</span> <span m='2981290'>non-zero</span> <span
  m='2982130'>only</span> <span m='2982460'>over</span> <span
  m='2982660'>this</span> <span m='2982920'>range.</span> </p><p><span
  m='2985590'>Looking</span> <span m='2985940'>at</span> <span
  m='2986090'>this</span> <span m='2986790'>integral,</span> <span
  m='2987380'>we</span> <span m='2987530'>can</span> <span
  m='2987710'>now</span> <span m='2987900'>pull</span> <span
  m='2988260'>out</span> <span m='2988400'>the</span> <span
  m='2988520'>term</span> <span m='2988990'>which</span> <span
  m='2989210'>corresponds</span> <span m='2990050'>to</span> <span
  m='2990920'>e^-at,</span> <span m='2993340'>just</span> <span
  m='2993610'>as</span> <span m='2993740'>we</span> <span
  m='2993860'>pulled</span> <span m='2994180'>out</span> <span
  m='2994540'>a</span> <span m='2994660'>term</span> <span m='2995240'>in</span>
  <span m='2995670'>the</span> <span m='2995750'>discrete-time</span> <span
  m='2996460'>case.</span> <span m='2999310'>We</span> <span
  m='2999500'>notice</span> <span m='2999870'>in</span> <span
  m='2999970'>the</span> <span m='3000060'>integral</span> <span
  m='3000350'>that</span> <span m='3000640'>we</span> <span
  m='3000730'>have</span> <span m='3000960'>e^(-a*-tau),</span> <span
  m='3004640'>so</span> <span m='3004980'>that</span> <span
  m='3005190'>gives</span> <span m='3005440'>us</span> <span
  m='3005570'>the</span> <span m='3005680'>integral</span> <span
  m='3006100'>from</span> <span m='3006240'>0</span> <span m='3006520'>to</span>
  <span m='3006640'>t</span> <span m='3007100'>of</span> <span
  m='3007190'>e^(a*tau).</span> <span m='3009740'>If</span> <span
  m='3009910'>we</span> <span m='3010010'>perform</span> <span
  m='3010460'>that</span> <span m='3010660'>integration,</span> <span
  m='3011610'>we</span> <span m='3011800'>end</span> <span m='3012040'>up</span>
  <span m='3012720'>with</span> <span m='3013600'>this</span> <span
  m='3013830'>expression.</span> <span m='3015220'>Finally,</span> <span
  m='3016270'>multiplying</span> <span m='3017070'>this</span> <span
  m='3017660'>by</span> <span m='3017970'>e^-at,</span> <span
  m='3019900'>we</span> <span m='3020040'>have</span> <span
  m='3020800'>for</span> <span m='3021220'>y(t),</span> <span
  m='3022120'>for</span> <span m='3022290'>t</span> <span
  m='3022500'>greater</span> <span m='3022820'>than</span> <span
  m='3022980'>0,</span> <span m='3024100'>the</span> <span
  m='3024490'>algebraic</span> <span m='3025180'>expression</span> <span
  m='3026490'>that</span> <span m='3026890'>I've</span> <span
  m='3027630'>indicated</span> <span m='3028270'>on</span> <span
  m='3028370'>the</span> <span m='3028440'>bottom.</span> </p><p><span
  m='3033540'>So</span> <span m='3033810'>we</span> <span m='3033875'>had</span>
  <span m='3033940'>worked</span> <span m='3034270'>out</span> <span
  m='3035120'>t</span> <span m='3035180'>less</span> <span
  m='3035430'>than</span> <span m='3035560'>0,</span> <span
  m='3036230'>and</span> <span m='3036400'>we</span> <span
  m='3036500'>come</span> <span m='3036700'>out</span> <span
  m='3036810'>with</span> <span m='3036960'>0.</span> <span
  m='3038170'>We</span> <span m='3038280'>work</span> <span
  m='3038590'>out</span> <span m='3039210'>t</span> <span
  m='3039310'>greater</span> <span m='3039680'>than</span> <span
  m='3039870'>0,</span> <span m='3040550'>and</span> <span m='3040880'>we</span>
  <span m='3041010'>come</span> <span m='3041260'>out</span> <span
  m='3041680'>with</span> <span m='3042810'>this</span> <span
  m='3043630'>algebraic</span> <span m='3044330'>expression.</span> <span
  m='3047250'>If</span> <span m='3047610'>we</span> <span
  m='3048010'>plot</span> <span m='3048420'>this</span> <span
  m='3048630'>algebraic</span> <span m='3049240'>expression</span> <span
  m='3049870'>as</span> <span m='3049990'>a</span> <span
  m='3050050'>function</span> <span m='3050460'>of</span> <span
  m='3050560'>time,</span> <span m='3051480'>we</span> <span
  m='3051610'>find</span> <span m='3052000'>that</span> <span
  m='3052050'>what</span> <span m='3052240'>it</span> <span
  m='3052350'>corresponds</span> <span m='3053120'>to</span> <span
  m='3053550'>is</span> <span m='3054560'>an</span> <span
  m='3054690'>exponential</span> <span m='3055380'>behavior</span> <span
  m='3056550'>starting</span> <span m='3057080'>at</span> <span
  m='3057190'>zero</span> <span m='3057960'>and</span> <span
  m='3058870'>exponentially</span> <span m='3060210'>heading</span> <span
  m='3060810'>asymptotically</span> <span m='3062430'>toward</span> <span
  m='3063180'>the</span> <span m='3063290'>value</span> <span
  m='3064110'>1</span> <span m='3064340'>/</span> <span m='3064690'>a.</span>
  </p><p><span m='3069980'>We've</span> <span m='3070180'>gone</span> <span
  m='3070410'>through</span> <span m='3070590'>these</span> <span
  m='3070790'>examples</span> <span m='3071430'>several</span> <span
  m='3071790'>ways,</span> <span m='3072170'>and</span> <span
  m='3072240'>one</span> <span m='3072430'>is</span> <span
  m='3072550'>analytically.</span> <span m='3074470'>In</span> <span
  m='3074610'>order</span> <span m='3074980'>to</span> <span
  m='3075410'>develop</span> <span m='3075910'>a</span> <span
  m='3076630'>feel</span> <span m='3076970'>and</span> <span
  m='3077310'>fluency</span> <span m='3077940'>for</span> <span
  m='3078100'>convolution,</span> <span m='3079590'>it's</span> <span
  m='3079780'>absolutely</span> <span m='3080360'>essential</span> <span
  m='3081310'>to</span> <span m='3081440'>work</span> <span
  m='3081780'>through</span> <span m='3082010'>a</span> <span
  m='3082110'>variety</span> <span m='3082730'>of</span> <span
  m='3082810'>examples,</span> <span m='3084000'>both</span> <span
  m='3084330'>understanding</span> <span m='3085100'>them</span> <span
  m='3085230'>graphically</span> <span m='3086540'>and</span> <span
  m='3086750'>understanding</span> <span m='3087410'>them</span> <span
  m='3087600'>as</span> <span m='3087740'>we</span> <span m='3087850'>did</span>
  <span m='3088080'>here</span> <span m='3089010'>analytically.</span> <span
  m='3091790'>You'll</span> <span m='3092130'>have</span> <span
  m='3092330'>an</span> <span m='3092400'>opportunity</span> <span
  m='3093140'>to</span> <span m='3093280'>do</span> <span
  m='3093490'>that</span> <span m='3094030'>through</span> <span
  m='3094230'>the</span> <span m='3094320'>problems</span> <span
  m='3094860'>that</span> <span m='3094960'>I've</span> <span
  m='3095040'>suggested</span> <span m='3095880'>in</span> <span
  m='3096330'>the</span> <span m='3096420'>video</span> <span
  m='3096780'>course</span> <span m='3097090'>manual.</span> </p><p><span
  m='3098950'>In</span> <span m='3099060'>the</span> <span
  m='3099140'>next</span> <span m='3099420'>lecture,</span> <span
  m='3100720'>what</span> <span m='3101410'>we'll</span> <span
  m='3101840'>turn</span> <span m='3102150'>to</span> <span
  m='3102730'>are</span> <span m='3103340'>some</span> <span
  m='3103560'>general</span> <span m='3103980'>properties</span> <span
  m='3104560'>of</span> <span m='3104670'>convolution,</span> <span
  m='3106070'>and</span> <span m='3106220'>show</span> <span
  m='3106570'>how</span> <span m='3106830'>this</span> <span
  m='3107370'>rather</span> <span m='3107720'>amazing</span> <span
  m='3108210'>representation</span> <span m='3109390'>of</span> <span
  m='3109560'>linear</span> <span m='3109870'>time-invariant</span> <span
  m='3110740'>systems</span> <span m='3111890'>in</span> <span
  m='3112000'>fact</span> <span m='3112310'>leads</span> <span
  m='3112640'>to</span> <span m='3112830'>a</span> <span
  m='3112950'>variety</span> <span m='3113820'>of</span> <span
  m='3114130'>properties</span> <span m='3115100'>of</span> <span
  m='3115240'>linear</span> <span m='3115580'>time-invariant</span> <span
  m='3116440'>systems.</span> <span m='3117620'>We'll</span> <span
  m='3117800'>find</span> <span m='3118500'>that</span> <span
  m='3119180'>convolution</span> <span m='3120270'>is</span> <span
  m='3120560'>fairly</span> <span m='3120970'>rich</span> <span
  m='3121260'>in</span> <span m='3121350'>its</span> <span
  m='3121510'>properties,</span> <span m='3122690'>and</span> <span
  m='3123320'>what</span> <span m='3123530'>this</span> <span
  m='3123740'>leads</span> <span m='3124070'>to</span> <span
  m='3124420'>are</span> <span m='3124605'>some</span> <span
  m='3125670'>very</span> <span m='3125960'>nice</span> <span
  m='3126450'>and</span> <span m='3127520'>desirable</span> <span
  m='3129180'>and</span> <span m='3129340'>exploitable</span> <span
  m='3130010'>properties</span> <span m='3130740'>of</span> <span
  m='3130860'>linear</span> <span m='3131150'>time-invariant</span> <span
  m='3131900'>systems.</span> <span m='3132680'>Thank</span> <span
  m='3132890'>you.</span> </p>
embedded_media:
  - uid: 72d7da8c5d8593a4dba021b0e09fa81a
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: _vyke3vF4Nk
  - uid: 8f80a8fc35d4ead4333bd4a96a648f08
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/_vyke3vF4Nk/default.jpg'
  - uid: 3fa7a6e2d2be747782a65029f28fa98b
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: >-
      http://www.archive.org/download/MITRES.6.007S11/MITRES_6-007S11lec04_300k.mp4
  - uid: d4fd5a79c90f865b2629d06f40586a47
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/podcast/lecture-4-convolution/id458320213?i=96641907
  - uid: 0400ba59406d52d94c079d99928156ee
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: MITRES_6_007S11_lec04.pdf
    title: MITRES_6_007S11_lec04.pdf
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-4-convolution/MITRES_6_007S11_lec04.pdf
  - uid: 2d74e0675a2da4ed03d86ff792476c7a
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: _vyke3vF4Nk
  - uid: b28e1a8eb1bae10afacf3a566e7f23fa
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: vyke3vF4Nk.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-4-convolution/vyke3vF4Nk.srt
  - uid: 5e5e87d50ad1e1bfef082524e90ffb08
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: vyke3vF4Nk.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-4-convolution/vyke3vF4Nk.pdf
  - uid: 72ef9e231387a1da0ef9e76662ae2e7b
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: f9ce7f41014297a102d3e913bb1c0361
    parent_uid: 433f0f569c6adfed0f8fc61a4e336e07
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-007-signals-and-systems-spring-2011
type: course
layout: video
---