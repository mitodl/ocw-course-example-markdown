---
order_index: null
title: 'Lecture 8: The Discrete Fourier Series'
template_type: Tabbed
uid: 95fe2f09600cdd292eb41e196c4d6888
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-8-the-discrete-fourier-series
short_url: lecture-8-the-discrete-fourier-series
inline_embed_id: '57267168lecture8:thediscretefourierseries88949940'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Fourier series representation for periodic
  sequences, determination of Fourier series coefficients, properties of Fourier
  series.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>The Discrete Fourier Series (<a
  href="./resolveuid/785b36fa522bbd2dea1e7834a7c26315">PDF</a>)</p>
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
  m='53220'>ALAN V. OPPENHEIM:</span> <span m='53445'>OK.</span> <span
  m='54450'>In</span> <span m='54540'>the</span> <span m='54630'>last</span>
  <span m='55260'>several</span> <span m='55710'>lectures,</span> <span
  m='56620'>we've</span> <span m='56820'>been</span> <span
  m='57300'>discussing</span> <span m='57970'>the</span> <span
  m='58170'>Fourier</span> <span m='58590'>and</span> <span
  m='60150'>Z-transforms.</span> <span m='61940'>And</span> <span
  m='62130'>we've</span> <span m='62250'>seen</span> <span m='62490'>in</span>
  <span m='62580'>particular</span> <span m='63240'>that</span> <span
  m='63420'>the</span> <span m='63640'>Fourier</span> <span m='63880'>and</span>
  <span m='63970'>Z-transforms</span> <span m='65610'>provide</span> <span
  m='66090'>us</span> <span m='66480'>with</span> <span m='66960'>a</span> <span
  m='67020'>set</span> <span m='67320'>of</span> <span
  m='67410'>important</span> <span m='68040'>analytical</span> <span
  m='68700'>tools</span> <span m='69810'>for</span> <span
  m='70350'>representing</span> <span m='71340'>discrete</span> <span
  m='71730'>time</span> <span m='72030'>signals,</span> <span
  m='73350'>and</span> <span m='73470'>also</span> <span m='74010'>for</span>
  <span m='74190'>dealing</span> <span m='74880'>with</span> <span
  m='75150'>discrete</span> <span m='75500'>time</span> <span
  m='75840'>systems.</span> <span m='77980'>We</span> <span
  m='78070'>saw,</span> <span m='78340'>for</span> <span
  m='78520'>example,</span> <span m='79390'>that</span> <span
  m='80320'>through</span> <span m='80620'>the</span> <span m='80770'>use</span>
  <span m='81010'>of</span> <span m='81100'>the</span> <span
  m='81230'>Fourier</span> <span m='81630'>transform</span> <span
  m='82360'>or</span> <span m='82570'>the</span> <span
  m='82690'>Z-transform,</span> <span m='84210'>we</span> <span
  m='84340'>could</span> <span m='84550'>convert</span> <span
  m='85270'>convolution</span> <span m='86410'>in</span> <span
  m='86530'>the</span> <span m='86620'>time</span> <span m='86920'>domain</span>
  <span m='88060'>to</span> <span m='88180'>multiplication</span> <span
  m='89260'>in</span> <span m='89650'>either</span> <span m='89890'>the</span>
  <span m='90010'>frequency</span> <span m='90520'>domain</span> <span
  m='90880'>in the</span> <span m='91240'>Fourier</span> <span
  m='91630'>transform</span> <span m='92260'>case,</span> <span
  m='93070'>or</span> <span m='93220'>more</span> <span
  m='93430'>generally,</span> <span m='94240'>in</span> <span
  m='94840'>the</span> <span m='94930'>Z</span> <span m='95170'>domain</span>
  <span m='95940'>in</span> <span m='96100'>the</span> <span
  m='96190'>Z-transform</span> <span m='97060'>case.</span> </p><p><span
  m='99740'>Now</span> <span m='100280'>one</span> <span m='100490'>of</span>
  <span m='100940'>the</span> <span m='101270'>things</span> <span
  m='101750'>that</span> <span m='101990'>it's</span> <span
  m='102200'>important</span> <span m='102620'>to</span> <span
  m='102740'>recognize</span> <span m='103790'>is</span> <span
  m='103970'>that</span> <span m='104420'>for</span> <span m='104510'>the</span>
  <span m='104600'>most</span> <span m='104900'>part,</span> <span
  m='105800'>the</span> <span m='106070'>Fourier</span> <span
  m='106550'>transform</span> <span m='107420'>and</span> <span
  m='107510'>the</span> <span m='107630'>Z-transform</span> <span
  m='109310'>are</span> <span m='109640'>primarily</span> <span
  m='110570'>analytical</span> <span m='111260'>tools.</span> <span
  m='112010'>That</span> <span m='112220'>is,</span> <span m='113540'>it</span>
  <span m='113630'>would</span> <span m='113810'>be</span> <span
  m='113960'>hard</span> <span m='114230'>to</span> <span
  m='114410'>imagine</span> <span m='115700'>implementing,</span> <span
  m='116660'>for</span> <span m='116840'>example,</span> <span
  m='117740'>a</span> <span m='117800'>discrete</span> <span
  m='118220'>time</span> <span m='118580'>system</span> <span
  m='120140'>by</span> <span m='120920'>first</span> <span
  m='121550'>computing</span> <span m='122140'>the</span> <span
  m='122210'>Fourier</span> <span m='122630'>transform</span> <span
  m='123560'>of</span> <span m='123650'>the</span> <span
  m='123740'>sequences,</span> <span m='125150'>multiplying</span> <span
  m='125810'>the</span> <span m='125910'>Fourier</span> <span
  m='126260'>transforms</span> <span m='126980'>together,</span> <span
  m='127850'>and</span> <span m='127970'>then</span> <span
  m='128300'>computing</span> <span m='128810'>the</span> <span
  m='128900'>inverse</span> <span m='129289'>transform.</span> </p><p><span
  m='130789'>One</span> <span m='130940'>of</span> <span m='131030'>the</span>
  <span m='131120'>reasons</span> <span m='131840'>that</span> <span
  m='132560'>that's</span> <span m='132800'>obviously</span> <span
  m='133430'>a</span> <span m='133490'>difficult</span> <span
  m='134000'>thing</span> <span m='134450'>to</span> <span m='134570'>do</span>
  <span m='134750'>computationally</span> <span m='136430'>is</span> <span
  m='136640'>that</span> <span m='137240'>we</span> <span m='137570'>saw,</span>
  <span m='138230'>as</span> <span m='138500'>we</span> <span
  m='138680'>discussed,</span> <span m='139670'>for</span> <span
  m='139850'>example,</span> <span m='140750'>the</span> <span
  m='140960'>Fourier</span> <span m='141380'>transform,</span> <span
  m='143240'>that</span> <span m='143390'>the</span> <span
  m='143480'>Fourier</span> <span m='143900'>transform</span> <span
  m='144740'>is</span> <span m='144920'>a</span> <span
  m='144980'>function</span> <span m='145790'>of</span> <span
  m='146600'>a</span> <span m='146750'>continuous</span> <span
  m='147380'>variable.</span> <span m='147980'>That</span> <span
  m='148160'>is,</span> <span m='148730'>omega</span> <span m='149960'>in</span>
  <span m='150050'>the</span> <span m='150270'>Fourier</span> <span
  m='150530'>transform</span> <span m='151340'>is</span> <span
  m='151490'>a</span> <span m='151580'>continuous</span> <span
  m='152180'>variable.</span> <span m='153600'>So</span> <span
  m='153700'>that,</span> <span m='153770'>in</span> <span
  m='153890'>fact,</span> <span m='154320'>if</span> <span m='154420'>we</span>
  <span m='154430'>wanted</span> <span m='154670'>to</span> <span
  m='154790'>compute</span> <span m='155180'>the</span> <span
  m='155300'>Fourier</span> <span m='155750'>transform</span> <span
  m='156530'>explicitly,</span> <span m='158030'>we</span> <span
  m='158150'>would</span> <span m='158300'>have</span> <span
  m='158540'>to</span> <span m='158630'>compute</span> <span
  m='159110'>it</span> <span m='159290'>at</span> <span m='159570'>an</span>
  <span m='159710'>infinite</span> <span m='160340'>number</span> <span
  m='160880'>of</span> <span m='160970'>frequencies.</span> <span
  m='162970'>Similarly,</span> <span m='163820'>we</span> <span
  m='163900'>have</span> <span m='164350'>a</span> <span
  m='164410'>situation</span> <span m='165340'>like</span> <span
  m='165610'>that</span> <span m='166120'>for</span> <span m='166480'>the</span>
  <span m='166600'>Z-transform.</span> </p><p><span m='168990'>Well,</span>
  <span m='169350'>today</span> <span m='169680'>I'd</span> <span
  m='169800'>like</span> <span m='169980'>to</span> <span
  m='170070'>introduce</span> <span m='171060'>a</span> <span
  m='171690'>third</span> <span m='171960'>transform,</span> <span
  m='173370'>which</span> <span m='174210'>I'll</span> <span
  m='174390'>refer</span> <span m='174780'>to</span> <span m='175170'>as</span>
  <span m='175890'>the</span> <span m='176010'>discrete</span> <span
  m='176870'>Fourier</span> <span m='177400'>transform.</span> <span
  m='179570'>The</span> <span m='179670'>discrete</span> <span
  m='179940'>Fourier</span> <span m='180360'>transform</span> <span
  m='181350'>is</span> <span m='181500'>similar</span> <span
  m='182760'>in</span> <span m='182880'>style</span> <span m='183930'>to</span>
  <span m='184030'>the</span> <span m='184210'>Fourier</span> <span
  m='184590'>transform</span> <span m='185580'>and</span> <span
  m='185700'>the</span> <span m='185760'>Z-transform,</span> <span
  m='186600'>as</span> <span m='186720'>we've</span> <span
  m='186930'>been</span> <span m='187050'>talking</span> <span
  m='187530'>about,</span> <span m='188430'>in</span> <span
  m='188520'>the</span> <span m='188580'>sense</span> <span
  m='189120'>that</span> <span m='189960'>more</span> <span m='190290'>or</span>
  <span m='190350'>less,</span> <span m='191010'>the</span> <span
  m='191130'>discrete</span> <span m='191560'>Fourier</span> <span
  m='191910'>transform</span> <span m='192570'>maps</span> <span
  m='193590'>convolution</span> <span m='194810'>to</span> <span
  m='194910'>multiplication.</span> <span m='197640'>Also,</span> <span
  m='198510'>there</span> <span m='198840'>are</span> <span
  m='198960'>properties</span> <span m='199570'>of</span> <span
  m='199660'>Fourier</span> <span m='200050'>transform--</span> <span
  m='200800'>the</span> <span m='201120'>discrete</span> <span
  m='201540'>Fourier</span> <span m='201930'>transform--</span> <span
  m='202620'>that</span> <span m='202740'>are</span> <span
  m='202800'>similar</span> <span m='203220'>to</span> <span
  m='203370'>the</span> <span m='203460'>properties</span> <span
  m='204270'>of</span> <span m='204870'>the</span> <span
  m='204960'>Fourier</span> <span m='205380'>transform</span> <span
  m='206000'>and</span> <span m='206260'>Z-transform,</span> <span
  m='207150'>as</span> <span m='207270'>we've</span> <span
  m='207450'>been</span> <span m='207600'>talking</span> <span
  m='208020'>about</span> <span m='208350'>them.</span> </p><p><span
  m='209820'>But</span> <span m='210270'>the</span> <span
  m='210550'>discrete</span> <span m='211260'>Fourier</span> <span
  m='211650'>transform</span> <span m='213330'>is</span> <span
  m='213570'>different</span> <span m='214650'>than</span> <span
  m='215310'>the</span> <span m='215460'>other</span> <span
  m='215670'>transforms</span> <span m='216600'>that</span> <span
  m='216720'>we've</span> <span m='216900'>been</span> <span
  m='217080'>discussing</span> <span m='218460'>in</span> <span
  m='219360'>a</span> <span m='219450'>number</span> <span m='219810'>of</span>
  <span m='219930'>important</span> <span m='220410'>respects.</span> <span
  m='221520'>One</span> <span m='221730'>of</span> <span m='221880'>the</span>
  <span m='222530'>respects,</span> <span m='223380'>one</span> <span
  m='223590'>of</span> <span m='223680'>the</span> <span
  m='224280'>reasons</span> <span m='226280'>that</span> <span
  m='226670'>it's</span> <span m='226880'>different</span> <span
  m='227930'>is</span> <span m='228200'>that</span> <span m='229070'>it</span>
  <span m='229250'>is</span> <span m='229430'>a</span> <span
  m='229520'>transform</span> <span m='230420'>that</span> <span
  m='230600'>can</span> <span m='230870'>be</span> <span
  m='231230'>explicitly</span> <span m='232430'>evaluated.</span> <span
  m='234380'>And</span> <span m='234500'>consequently,</span> <span
  m='235940'>it</span> <span m='236420'>is</span> <span
  m='236660'>important,</span> <span m='237890'>not</span> <span
  m='238100'>only</span> <span m='238520'>in</span> <span m='238610'>the</span>
  <span m='238730'>analysis</span> <span m='239690'>of</span> <span
  m='239840'>discrete</span> <span m='240230'>time</span> <span
  m='240560'>systems,</span> <span m='241580'>but</span> <span
  m='241790'>also,</span> <span m='242420'>as</span> <span
  m='242600'>we'll</span> <span m='242750'>see,</span> <span
  m='243710'>in</span> <span m='244130'>the</span> <span
  m='244280'>implementation</span> <span m='245360'>of</span> <span
  m='245510'>discrete</span> <span m='245900'>time</span> <span
  m='246200'>systems.</span> <span m='247130'>That</span> <span
  m='247370'>is,</span> <span m='248030'>many</span> <span
  m='248750'>digital</span> <span m='249110'>signal</span> <span
  m='249440'>processing</span> <span m='250070'>algorithms,</span> <span
  m='250970'>as</span> <span m='251180'>we'll</span> <span
  m='251300'>see,</span> <span m='252650'>actually</span> <span
  m='253220'>involve</span> <span m='254480'>the</span> <span
  m='254600'>explicit</span> <span m='255260'>computation</span> <span
  m='256339'>of</span> <span m='256910'>the</span> <span
  m='257000'>discrete</span> <span m='257690'>Fourier</span> <span
  m='258110'>transform,</span> <span m='259320'>which</span> <span
  m='259399'>is</span> <span m='259560'>the</span> <span
  m='260010'>Fourier</span> <span m='260390'>transform</span> <span
  m='261410'>that</span> <span m='261620'>we're</span> <span
  m='261800'>about</span> <span m='262070'>to</span> <span
  m='262190'>introduce.</span> </p><p><span m='263720'>Now</span> <span
  m='264410'>let</span> <span m='264590'>me</span> <span m='265100'>try</span>
  <span m='265370'>to</span> <span m='265490'>explain</span> <span
  m='266000'>a</span> <span m='266060'>little</span> <span
  m='266540'>about</span> <span m='267050'>what</span> <span
  m='267290'>the</span> <span m='267410'>discrete</span> <span
  m='267770'>Fourier</span> <span m='268160'>transform</span> <span
  m='268820'>is</span> <span m='269030'>before</span> <span m='269810'>we</span>
  <span m='270050'>look</span> <span m='270320'>at</span> <span
  m='270470'>it</span> <span m='270590'>in</span> <span
  m='270800'>detail.</span> <span m='273040'>Basically,</span> <span
  m='273970'>the</span> <span m='274270'>discrete</span> <span
  m='274690'>Fourier</span> <span m='275140'>transform</span> <span
  m='277060'>is</span> <span m='278380'>related</span> <span
  m='279220'>to</span> <span m='279310'>the</span> <span
  m='279430'>Fourier</span> <span m='279820'>transform</span> <span
  m='280480'>that</span> <span m='280570'>we've</span> <span
  m='280750'>been</span> <span m='280900'>discussing</span> <span
  m='282310'>in</span> <span m='282460'>the</span> <span m='282550'>sense</span>
  <span m='283000'>that</span> <span m='283330'>it</span> <span
  m='283450'>corresponds</span> <span m='284470'>to</span> <span
  m='285040'>samples</span> <span m='286120'>of</span> <span
  m='286280'>the</span> <span m='286360'>Fourier</span> <span
  m='286820'>transform,</span> <span m='287590'>or</span> <span
  m='288220'>more</span> <span m='288400'>generally,</span> <span
  m='288970'>samples</span> <span m='289600'>of</span> <span
  m='289690'>the</span> <span m='289770'>Z-transform.</span> <span
  m='292540'>Now</span> <span m='294070'>that</span> <span
  m='294280'>requires</span> <span m='295690'>that</span> <span
  m='296140'>we</span> <span m='296380'>impose</span> <span
  m='296800'>some</span> <span m='296980'>restrictions</span> <span
  m='298000'>on</span> <span m='298270'>the</span> <span
  m='298360'>sequences</span> <span m='299440'>that</span> <span
  m='299620'>we're</span> <span m='299770'>representing</span> <span
  m='300820'>through</span> <span m='301000'>that</span> <span
  m='301180'>transform.</span> <span m='302440'>And</span> <span
  m='302620'>as</span> <span m='302830'>we'll</span> <span
  m='302980'>see,</span> <span m='303490'>it</span> <span
  m='303580'>turns</span> <span m='303970'>out</span> <span
  m='304510'>that</span> <span m='305170'>we</span> <span m='305290'>can</span>
  <span m='305500'>represent</span> <span m='306550'>sequences</span> <span
  m='307420'>that</span> <span m='307570'>are</span> <span m='307690'>of</span>
  <span m='307750'>finite</span> <span m='308290'>length.</span> <span
  m='309730'>That</span> <span m='310000'>is,</span> <span
  m='310690'>only</span> <span m='310990'>have</span> <span m='311170'>a</span>
  <span m='311260'>finite</span> <span m='311710'>number</span> <span
  m='312070'>of</span> <span m='312160'>non-zero</span> <span
  m='312760'>samples.</span> <span m='314290'>We</span> <span
  m='314410'>can</span> <span m='314560'>represent</span> <span
  m='315100'>those</span> <span m='315310'>sequences</span> <span
  m='316210'>by</span> <span m='316390'>samples</span> <span
  m='317170'>of</span> <span m='317340'>their</span> <span
  m='317470'>Fourier</span> <span m='317920'>transform.</span> <span
  m='319120'>Those</span> <span m='319360'>samples</span> <span
  m='320230'>then</span> <span m='320440'>correspond</span> <span
  m='321130'>to</span> <span m='321250'>the</span> <span
  m='321370'>discrete</span> <span m='321940'>Fourier</span> <span
  m='322390'>transform.</span> </p><p><span m='324960'>Well,</span> <span
  m='326040'>there</span> <span m='326370'>are</span> <span
  m='326520'>some</span> <span m='326730'>issues</span> <span
  m='327450'>that</span> <span m='327600'>arise</span> <span
  m='328380'>in</span> <span m='328530'>looking</span> <span
  m='329040'>at</span> <span m='329190'>the</span> <span
  m='329280'>discrete</span> <span m='329670'>Fourier</span> <span
  m='330060'>transform,</span> <span m='330780'>or</span> <span
  m='331200'>DFT,</span> <span m='332340'>as</span> <span m='332520'>I'll</span>
  <span m='332640'>refer</span> <span m='333030'>to</span> <span
  m='333270'>it.</span> <span m='334830'>And</span> <span m='336360'>a</span>
  <span m='336420'>number</span> <span m='336870'>of</span> <span
  m='337020'>these</span> <span m='337260'>issues</span> <span
  m='338280'>relate</span> <span m='338640'>to</span> <span
  m='338790'>the</span> <span m='338910'>fact</span> <span
  m='339720'>that</span> <span m='340740'>the</span> <span
  m='341520'>discrete</span> <span m='342190'>Fourier</span> <span
  m='342660'>transform</span> <span m='344220'>has</span> <span
  m='344460'>properties</span> <span m='346420'>that</span> <span
  m='346660'>are</span> <span m='346810'>somewhat</span> <span
  m='347320'>different,</span> <span m='348940'>and</span> <span
  m='349060'>also</span> <span m='349360'>somewhat</span> <span
  m='349750'>similar,</span> <span m='350620'>to</span> <span
  m='350710'>the</span> <span m='350870'>Fourier</span> <span
  m='351200'>transform</span> <span m='351790'>properties</span> <span
  m='352570'>that</span> <span m='352690'>we've</span> <span
  m='352870'>been</span> <span m='353050'>discussing.</span> <span
  m='354820'>There</span> <span m='354910'>are</span> <span
  m='354970'>lots</span> <span m='355240'>of</span> <span m='355360'>ways</span>
  <span m='355750'>of</span> <span m='355870'>introducing</span> <span
  m='356890'>the</span> <span m='357250'>discrete</span> <span
  m='357670'>Fourier</span> <span m='358090'>transform.</span> <span
  m='359830'>And</span> <span m='361330'>the</span> <span m='361660'>one</span>
  <span m='362260'>that</span> <span m='362710'>I</span> <span
  m='362830'>guess</span> <span m='363100'>I</span> <span m='363280'>find</span>
  <span m='364030'>the</span> <span m='364150'>most</span> <span
  m='364450'>interesting,</span> <span m='364990'>and</span> <span
  m='365080'>the</span> <span m='365170'>most</span> <span
  m='365350'>satisfactory,</span> <span m='366910'>is</span> <span
  m='367390'>to</span> <span m='367540'>relate</span> <span
  m='368230'>the</span> <span m='368370'>discrete</span> <span
  m='368890'>Fourier</span> <span m='369190'>transform</span> <span
  m='370630'>to</span> <span m='371230'>the</span> <span
  m='371470'>discrete</span> <span m='372430'>Fourier</span> <span
  m='372850'>series</span> <span m='373810'>for</span> <span
  m='374140'>periodic</span> <span m='375130'>sequences.</span> <span
  m='376690'>And</span> <span m='376990'>in</span> <span
  m='377110'>particular,</span> <span m='378220'>relate</span> <span
  m='379000'>the</span> <span m='379270'>notion</span> <span
  m='379960'>of</span> <span m='380170'>finite</span> <span
  m='380620'>length</span> <span m='380860'>sequences</span> <span
  m='382150'>to</span> <span m='382780'>periodic</span> <span
  m='383380'>sequences.</span> </p><p><span m='385060'>Well,</span> <span
  m='385180'>let</span> <span m='385330'>me</span> <span
  m='385480'>explain</span> <span m='386120'>in</span> <span m='386260'>a</span>
  <span m='386290'>little</span> <span m='386470'>more</span> <span
  m='386650'>detail</span> <span m='387130'>what</span> <span
  m='387280'>I</span> <span m='387400'>mean</span> <span m='387640'>by</span>
  <span m='387850'>that.</span> <span m='390280'>Let's</span> <span
  m='390360'>consider,</span> <span m='390960'>first</span> <span
  m='391320'>of</span> <span m='391440'>all,</span> <span m='392880'>a</span>
  <span m='392980'>sequence</span> <span m='393720'>x</span> <span
  m='393990'>of</span> <span m='394140'>n,</span> <span m='395580'>which</span>
  <span m='396180'>I'll</span> <span m='396600'>restrict</span> <span
  m='397050'>to</span> <span m='397200'>be</span> <span m='397680'>a</span>
  <span m='397740'>finite</span> <span m='398220'>length</span> <span
  m='398460'>sequence.</span> <span m='400950'>The</span> <span
  m='401120'>sequence,</span> <span m='402150'>for</span> <span
  m='402330'>example,</span> <span m='403140'>one</span> <span
  m='403380'>example</span> <span m='403980'>indicated</span> <span
  m='404580'>here,</span> <span m='406090'>has</span> <span m='407590'>a</span>
  <span m='407650'>set</span> <span m='408100'>of</span> <span
  m='409300'>non-zero</span> <span m='409960'>values</span> <span
  m='411310'>only</span> <span m='411850'>over</span> <span m='412210'>a</span>
  <span m='412270'>finite</span> <span m='412750'>range</span> <span
  m='413290'>of</span> <span m='413440'>the</span> <span
  m='413590'>argument</span> <span m='414030'>n.</span> <span
  m='416010'>Here</span> <span m='416250'>is</span> <span m='416370'>a</span>
  <span m='416460'>sequence</span> <span m='417330'>that</span> <span
  m='417810'>is</span> <span m='418230'>of</span> <span m='418320'>finite</span>
  <span m='418830'>length.</span> <span m='419790'>And</span> <span
  m='420060'>I've</span> <span m='420210'>chosen</span> <span
  m='420720'>to</span> <span m='421050'>refer</span> <span m='421410'>to</span>
  <span m='421680'>it</span> <span m='421860'>as</span> <span
  m='422010'>a</span> <span m='422070'>sequence</span> <span
  m='422580'>of</span> <span m='422670'>finite</span> <span
  m='423090'>length</span> <span m='423370'>capital</span> <span
  m='423870'>N.</span> <span m='425150'>0</span> <span m='426320'>outside</span>
  <span m='426860'>the</span> <span m='426980'>range</span> <span
  m='427790'>from</span> <span m='428090'>little</span> <span
  m='428390'>n</span> <span m='428540'>equals</span> <span m='428830'>0</span>
  <span m='429770'>to</span> <span m='429890'>little</span> <span
  m='430190'>n</span> <span m='430520'>equals</span> <span
  m='430940'>capital</span> <span m='431420'>N</span> <span
  m='431570'>minus</span> <span m='431930'>1.</span> <span
  m='432260'>It's</span> <span m='432440'>0</span> <span
  m='433010'>outside</span> <span m='433490'>that</span> <span
  m='433730'>range.</span> </p><p><span m='435730'>It's</span> <span
  m='436120'>interesting,</span> <span m='437230'>just</span> <span
  m='437950'>as</span> <span m='438130'>an</span> <span m='438220'>aside,</span>
  <span m='439150'>to</span> <span m='439270'>note</span> <span
  m='439840'>that</span> <span m='440140'>for</span> <span
  m='440290'>this</span> <span m='440500'>particular</span> <span
  m='441040'>sequence,</span> <span m='442180'>it's</span> <span
  m='442360'>also</span> <span m='442870'>actually</span> <span
  m='443260'>0</span> <span m='443830'>outside</span> <span
  m='444370'>the</span> <span m='444460'>range</span> <span
  m='445000'>from</span> <span m='445270'>little</span> <span
  m='445540'>n</span> <span m='445690'>equals</span> <span m='446050'>1</span>
  <span m='446950'>to</span> <span m='447070'>capital</span> <span
  m='447550'>N</span> <span m='447700'>minus</span> <span m='448150'>1.</span>
  <span m='449410'>And</span> <span m='449830'>in</span> <span
  m='449950'>general,</span> <span m='450610'>obviously,</span> <span
  m='452050'>if</span> <span m='452230'>I</span> <span m='452320'>talk</span>
  <span m='452680'>about</span> <span m='452920'>a</span> <span
  m='452980'>finite</span> <span m='453700'>length</span> <span
  m='453970'>sequence</span> <span m='454960'>of</span> <span
  m='455110'>length</span> <span m='455410'>capital</span> <span
  m='456090'>N,</span> <span m='457120'>I</span> <span m='457210'>can</span>
  <span m='457390'>also</span> <span m='457780'>refer</span> <span
  m='458170'>to</span> <span m='458440'>it</span> <span m='458650'>as</span>
  <span m='459040'>a</span> <span m='459130'>finite</span> <span
  m='459550'>length</span> <span m='459790'>sequence</span> <span
  m='460360'>of</span> <span m='460540'>length</span> <span
  m='460810'>greater</span> <span m='461170'>than</span> <span
  m='461350'>capital</span> <span m='461605'>N.</span> <span
  m='462430'>That</span> <span m='462580'>is,</span> <span m='463000'>the</span>
  <span m='463120'>important</span> <span m='463570'>statement</span> <span
  m='464530'>about</span> <span m='464830'>the</span> <span
  m='464950'>sequence</span> <span m='465370'>being</span> <span
  m='465610'>finite</span> <span m='466060'>length,</span> <span
  m='466990'>of</span> <span m='467080'>finite</span> <span
  m='467530'>length</span> <span m='467760'>capital</span> <span
  m='468250'>N,</span> <span m='469060'>is</span> <span m='469300'>that</span>
  <span m='469810'>the</span> <span m='469900'>sequence</span> <span
  m='470410'>values</span> <span m='470890'>are</span> <span m='471010'>0</span>
  <span m='472360'>outside</span> <span m='472900'>the</span> <span
  m='473020'>range</span> <span m='473500'>0</span> <span m='474340'>to</span>
  <span m='474430'>capital</span> <span m='474940'>N</span> <span
  m='475090'>minus</span> <span m='475460'>1.</span> <span
  m='476740'>Although</span> <span m='477100'>obviously,</span> <span
  m='477700'>the</span> <span m='477800'>sequence</span> <span
  m='478660'>could</span> <span m='478870'>also</span> <span
  m='479200'>be</span> <span m='479410'>0</span> <span m='480250'>inside</span>
  <span m='480700'>that</span> <span m='480880'>range</span> <span
  m='481240'>for</span> <span m='481360'>some</span> <span m='481600'>of</span>
  <span m='481690'>the</span> <span m='481780'>values.</span> </p><p><span
  m='484630'>Now</span> <span m='485710'>the</span> <span
  m='486010'>basic</span> <span m='486520'>notion</span> <span
  m='487870'>that</span> <span m='488230'>leads</span> <span
  m='488830'>to</span> <span m='489280'>the</span> <span
  m='489550'>discrete</span> <span m='489970'>Fourier</span> <span
  m='490430'>transform,</span> <span m='491350'>or</span> <span
  m='491560'>one</span> <span m='491770'>way</span> <span m='492130'>of</span>
  <span m='492310'>looking</span> <span m='492640'>at</span> <span
  m='492730'>the</span> <span m='492820'>discrete</span> <span
  m='493210'>Fourier</span> <span m='493600'>transform,</span> <span
  m='495070'>is</span> <span m='495220'>to</span> <span
  m='495370'>recognize</span> <span m='496450'>that</span> <span
  m='496720'>if</span> <span m='496990'>I</span> <span m='497110'>have</span>
  <span m='497290'>a</span> <span m='497380'>finite</span> <span
  m='497800'>length</span> <span m='498040'>sequence,</span> <span
  m='498940'>as</span> <span m='499060'>I</span> <span m='499210'>have</span>
  <span m='499480'>here,</span> <span m='501210'>I</span> <span
  m='501330'>could</span> <span m='501510'>construct</span> <span
  m='502340'>from</span> <span m='502620'>that</span> <span
  m='502830'>sequence</span> <span m='503970'>a</span> <span
  m='504030'>periodic</span> <span m='504720'>sequence.</span> <span
  m='505950'>And</span> <span m='506430'>let</span> <span m='506610'>me</span>
  <span m='506760'>denote</span> <span m='507360'>the</span> <span
  m='507480'>periodic</span> <span m='508050'>sequence</span> <span
  m='508650'>by</span> <span m='508920'>x</span> <span m='509640'>tilde</span>
  <span m='509910'>of</span> <span m='510390'>n.</span> <span
  m='511200'>In</span> <span m='511320'>general,</span> <span
  m='512080'>by</span> <span m='512190'>the</span> <span m='512309'>way,</span>
  <span m='512580'>when</span> <span m='512820'>I</span> <span
  m='512909'>refer</span> <span m='513270'>to</span> <span m='513419'>a</span>
  <span m='513480'>sequence</span> <span m='514169'>with</span> <span
  m='514340'>a</span> <span m='514419'>tilde</span> <span m='514770'>on</span>
  <span m='515010'>it,</span> <span m='515400'>that</span> <span
  m='515549'>will</span> <span m='515700'>always</span> <span
  m='516030'>correspond</span> <span m='516720'>to</span> <span
  m='516840'>a</span> <span m='516900'>periodic</span> <span
  m='517500'>sequence.</span> </p><p><span m='518760'>And</span> <span
  m='519210'>let</span> <span m='519390'>me</span> <span
  m='519510'>construct</span> <span m='520080'>this</span> <span
  m='520289'>periodic</span> <span m='520890'>sequence</span> <span
  m='522030'>by</span> <span m='522179'>simply</span> <span
  m='522870'>taking</span> <span m='523289'>the</span> <span
  m='523380'>finite</span> <span m='523830'>length</span> <span
  m='524070'>sequence</span> <span m='525180'>and</span> <span
  m='525780'>repeating</span> <span m='526290'>it</span> <span
  m='526410'>over</span> <span m='526740'>and</span> <span
  m='526860'>over</span> <span m='527160'>again</span> <span
  m='528270'>with</span> <span m='528420'>a</span> <span
  m='528480'>period</span> <span m='529110'>of</span> <span
  m='529260'>capital</span> <span m='529770'>N.</span> <span
  m='530790'>In</span> <span m='530910'>other</span> <span
  m='531120'>words,</span> <span m='532120'>I</span> <span m='532140'>can</span>
  <span m='532350'>construct</span> <span m='532930'>the</span> <span
  m='533040'>periodic</span> <span m='533640'>sequence,</span> <span
  m='534420'>x</span> <span m='534690'>tilde</span> <span m='535020'>of</span>
  <span m='535170'>n</span> <span m='536340'>equal</span> <span
  m='536760'>to</span> <span m='537180'>x</span> <span m='537480'>of</span>
  <span m='537630'>n</span> <span m='538890'>plus</span> <span
  m='539400'>x</span> <span m='539670'>of</span> <span m='539790'>n</span> <span
  m='540270'>shifted</span> <span m='541140'>to</span> <span
  m='541230'>the</span> <span m='541350'>left</span> <span m='541620'>by</span>
  <span m='541830'>capital</span> <span m='542370'>N</span> <span
  m='543210'>and</span> <span m='543330'>x</span> <span m='543570'>of</span>
  <span m='543690'>n</span> <span m='544080'>shifted</span> <span
  m='544500'>to</span> <span m='544620'>the</span> <span m='544710'>right</span>
  <span m='544950'>by</span> <span m='545170'>capital</span> <span
  m='545690'>N</span> <span m='546420'>and</span> <span m='546630'>2n,</span>
  <span m='547380'>2</span> <span m='547560'>capital</span> <span
  m='548010'>N,</span> <span m='548150'>and</span> <span m='548220'>3</span>
  <span m='548430'>capital</span> <span m='548700'>N,</span> <span
  m='549310'>et</span> <span m='549560'>cetera.</span> <span
  m='550620'>In</span> <span m='550740'>other</span> <span
  m='550980'>words,</span> <span m='551800'>just</span> <span
  m='552000'>simply</span> <span m='552480'>taking</span> <span
  m='552900'>this</span> <span m='553080'>sequence</span> <span
  m='554370'>and</span> <span m='555030'>repeating</span> <span
  m='555570'>it</span> <span m='555870'>over</span> <span m='556260'>and</span>
  <span m='556350'>over</span> <span m='556710'>again</span> <span
  m='557580'>with</span> <span m='557730'>a</span> <span
  m='557790'>period</span> <span m='558450'>of</span> <span
  m='558570'>capital</span> <span m='559090'>N.</span> </p><p><span
  m='560100'>So</span> <span m='560400'>obviously</span> <span
  m='561690'>I</span> <span m='561870'>can</span> <span
  m='562890'>generate,</span> <span m='563700'>from</span> <span
  m='563910'>a</span> <span m='563970'>finite</span> <span
  m='564420'>length</span> <span m='564660'>sequence,</span> <span
  m='565860'>a</span> <span m='565950'>periodic</span> <span
  m='566640'>sequence.</span> <span m='569050'>And</span> <span
  m='569130'>in</span> <span m='569250'>fact,</span> <span m='570000'>I</span>
  <span m='570120'>could</span> <span m='570330'>get</span> <span
  m='570570'>the</span> <span m='570690'>finite</span> <span
  m='571040'>length</span> <span m='571370'>sequence</span> <span
  m='572160'>back</span> <span m='572490'>from</span> <span
  m='572670'>the</span> <span m='572760'>periodic</span> <span
  m='573390'>sequence</span> <span m='574830'>by</span> <span
  m='575040'>simply</span> <span m='575850'>extracting</span> <span
  m='577080'>one</span> <span m='577320'>period</span> <span
  m='578010'>of</span> <span m='578160'>this</span> <span
  m='578370'>periodic</span> <span m='578970'>sequence.</span> <span
  m='580140'>In</span> <span m='580260'>other</span> <span
  m='580470'>words,</span> <span m='581380'>I</span> <span m='581430'>can</span>
  <span m='581610'>get</span> <span m='581820'>x</span> <span
  m='582100'>of</span> <span m='582395'>n</span> <span m='583140'>back</span>
  <span m='583710'>from</span> <span m='584040'>x</span> <span
  m='584280'>tilde</span> <span m='584550'>of</span> <span m='584700'>n</span>
  <span m='585660'>simply</span> <span m='586680'>by</span> <span
  m='587370'>multiplying</span> <span m='588780'>by</span> <span
  m='588990'>unity</span> <span m='590580'>for</span> <span m='590790'>n</span>
  <span m='591030'>between</span> <span m='591720'>0</span> <span
  m='592350'>and</span> <span m='592470'>capital</span> <span
  m='592980'>N</span> <span m='593100'>minus</span> <span m='593490'>1,</span>
  <span m='596690'>and</span> <span m='596960'>0</span> <span
  m='597680'>outside</span> <span m='598220'>that</span> <span
  m='598460'>range.</span> </p><p><span m='600650'>Now</span> <span
  m='600790'>the</span> <span m='600880'>important</span> <span
  m='601300'>point</span> <span m='601660'>here--</span> <span
  m='602200'>there</span> <span m='602320'>are</span> <span m='602350'>a</span>
  <span m='602380'>couple</span> <span m='602650'>of</span> <span
  m='602770'>important</span> <span m='603220'>points.</span> <span
  m='604270'>One</span> <span m='604450'>of</span> <span m='604600'>them</span>
  <span m='604960'>is</span> <span m='605260'>that</span> <span
  m='606340'>if</span> <span m='606550'>I</span> <span m='606670'>have</span>
  <span m='606820'>a</span> <span m='606880'>finite</span> <span
  m='607330'>length</span> <span m='607540'>sequence,</span> <span
  m='608260'>I</span> <span m='608350'>can</span> <span m='608530'>turn</span>
  <span m='608770'>it</span> <span m='608860'>into</span> <span
  m='609070'>a</span> <span m='609130'>periodic</span> <span
  m='609730'>sequence.</span> <span m='611230'>If</span> <span
  m='611410'>I</span> <span m='611470'>have</span> <span m='611650'>a</span>
  <span m='611710'>periodic</span> <span m='612280'>sequence,</span> <span
  m='613240'>I</span> <span m='613360'>can</span> <span m='613540'>get</span>
  <span m='613750'>back</span> <span m='614020'>to</span> <span
  m='614140'>the</span> <span m='614260'>finite</span> <span
  m='614620'>length</span> <span m='614920'>sequence</span> <span
  m='615460'>simply</span> <span m='615820'>by</span> <span
  m='616030'>extracting</span> <span m='616630'>one</span> <span
  m='616840'>period.</span> <span m='618280'>Or</span> <span
  m='619210'>what</span> <span m='619420'>that</span> <span
  m='619690'>essentially</span> <span m='620350'>says</span> <span
  m='621130'>is</span> <span m='621370'>that</span> <span
  m='621910'>there</span> <span m='622060'>really</span> <span
  m='622450'>isn't</span> <span m='622690'>much</span> <span
  m='622960'>difference</span> <span m='623890'>between</span> <span
  m='624430'>a</span> <span m='624520'>finite</span> <span
  m='625000'>length</span> <span m='625210'>sequence</span> <span
  m='625900'>and</span> <span m='625990'>a</span> <span
  m='626050'>periodic</span> <span m='626650'>sequence.</span> <span
  m='628030'>That</span> <span m='628240'>is,</span> <span m='628900'>a</span>
  <span m='628960'>finite</span> <span m='629350'>length</span> <span
  m='629580'>sequence</span> <span m='630430'>is</span> <span
  m='630730'>defined</span> <span m='631270'>by</span> <span
  m='631450'>capital</span> <span m='631960'>N</span> <span
  m='632410'>values.</span> </p><p><span m='634440'>A</span> <span
  m='634530'>periodic</span> <span m='635100'>sequence</span> <span
  m='635360'>is</span> <span m='635670'>also</span> <span
  m='636000'>defined</span> <span m='636630'>by</span> <span
  m='636810'>capital</span> <span m='637290'>N</span> <span
  m='637440'>values</span> <span m='637950'>because</span> <span
  m='638280'>once</span> <span m='638550'>I</span> <span
  m='638670'>specify</span> <span m='639540'>a</span> <span
  m='639600'>single</span> <span m='639960'>period,</span> <span
  m='641490'>then</span> <span m='642330'>I</span> <span m='643050'>don't</span>
  <span m='643320'>have</span> <span m='643590'>any</span> <span
  m='643830'>more</span> <span m='644040'>degrees</span> <span
  m='644460'>of</span> <span m='644550'>freedom</span> <span
  m='645060'>in</span> <span m='645180'>specifying</span> <span
  m='645900'>the</span> <span m='645990'>rest</span> <span m='646230'>of</span>
  <span m='646320'>the</span> <span m='646440'>sequence.</span> <span
  m='648060'>And</span> <span m='648480'>that's</span> <span
  m='648720'>an</span> <span m='648810'>important</span> <span
  m='649260'>point</span> <span m='649530'>to</span> <span
  m='649650'>keep</span> <span m='649890'>in</span> <span
  m='650010'>mind,</span> <span m='650470'>particularly</span> <span
  m='651300'>as</span> <span m='651510'>we</span> <span m='651600'>go</span>
  <span m='651810'>through</span> <span m='651990'>the</span> <span
  m='652080'>next</span> <span m='652290'>several</span> <span
  m='652650'>lectures.</span> <span m='653440'>A</span> <span
  m='653610'>finite</span> <span m='654060'>length</span> <span
  m='654240'>sequence</span> <span m='655230'>is</span> <span
  m='655620'>very</span> <span m='656010'>similar</span> <span
  m='656460'>to</span> <span m='656610'>a</span> <span
  m='656670'>periodic</span> <span m='657570'>sequence</span> <span
  m='658610'>in</span> <span m='658750'>that</span> <span m='658930'>both</span>
  <span m='659250'>of</span> <span m='659370'>them</span> <span
  m='659700'>are</span> <span m='659850'>simply</span> <span
  m='660270'>defined</span> <span m='661350'>by</span> <span
  m='661710'>capital</span> <span m='662220'>N</span> <span
  m='662400'>values.</span> <span m='663690'>One</span> <span
  m='663870'>way</span> <span m='664020'>to</span> <span m='664140'>think</span>
  <span m='664410'>of</span> <span m='664500'>that,</span> <span
  m='664920'>by</span> <span m='665130'>the</span> <span m='665220'>way,</span>
  <span m='665670'>is</span> <span m='666600'>to</span> <span
  m='667200'>think</span> <span m='667620'>of</span> <span
  m='668250'>taking</span> <span m='668610'>a</span> <span
  m='668700'>finite</span> <span m='669120'>length</span> <span
  m='669360'>sequence</span> <span m='670410'>of</span> <span
  m='670530'>capital</span> <span m='671040'>N</span> <span
  m='671190'>values.</span> <span m='673040'>Instead</span> <span
  m='673340'>of</span> <span m='673460'>drawing</span> <span
  m='673970'>it</span> <span m='674390'>along</span> <span m='674720'>a</span>
  <span m='674780'>straight</span> <span m='675110'>line</span> <span
  m='675440'>as</span> <span m='675560'>I've</span> <span m='675710'>done</span>
  <span m='675980'>here,</span> <span m='677000'>imagine</span> <span
  m='677960'>taking</span> <span m='678380'>this</span> <span
  m='678530'>finite</span> <span m='678920'>length</span> <span
  m='679130'>sequence</span> <span m='679610'>and</span> <span
  m='679730'>wrapping</span> <span m='680180'>it</span> <span
  m='680390'>around</span> <span m='680690'>the</span> <span
  m='680780'>circumference</span> <span m='681440'>of</span> <span
  m='681530'>a</span> <span m='681590'>cylinder.</span> </p><p><span
  m='683380'>So</span> <span m='683680'>we</span> <span m='683830'>start</span>
  <span m='684160'>with</span> <span m='684290'>the</span> <span
  m='684370'>finite</span> <span m='684760'>length</span> <span
  m='684970'>sequence</span> <span m='686050'>and</span> <span
  m='686170'>just</span> <span m='686350'>simply</span> <span
  m='687400'>display</span> <span m='687940'>it</span> <span
  m='688120'>wrapped</span> <span m='688480'>around</span> <span
  m='688750'>the</span> <span m='688870'>circumference</span> <span
  m='689500'>of</span> <span m='689590'>a</span> <span
  m='689650'>cylinder.</span> <span m='691330'>As</span> <span
  m='691480'>we</span> <span m='691630'>run</span> <span
  m='691870'>around</span> <span m='692170'>the</span> <span
  m='692290'>cylinder,</span> <span m='693250'>over</span> <span
  m='693610'>and</span> <span m='693700'>over</span> <span
  m='694060'>again,</span> <span m='694990'>what</span> <span
  m='695170'>we</span> <span m='695320'>see</span> <span m='695950'>is</span>
  <span m='696610'>the</span> <span m='696700'>periodic</span> <span
  m='697330'>sequence</span> <span m='698060'>x</span> <span
  m='698310'>tilde</span> <span m='698680'>of</span> <span m='698950'>n.</span>
  <span m='700780'>So</span> <span m='702010'>in</span> <span
  m='702100'>a</span> <span m='702160'>sense,</span> <span m='702550'>the</span>
  <span m='702640'>periodic</span> <span m='703210'>sequence</span> <span
  m='703810'>is</span> <span m='703900'>just</span> <span
  m='704110'>simply</span> <span m='704500'>like</span> <span
  m='704740'>the</span> <span m='704860'>finite</span> <span
  m='705220'>length</span> <span m='705430'>sequence,</span> <span
  m='706240'>but</span> <span m='706570'>wrapped</span> <span
  m='706930'>on</span> <span m='707080'>a</span> <span
  m='707140'>cylinder</span> <span m='707740'>instead</span> <span
  m='708070'>of</span> <span m='708160'>laid</span> <span m='708400'>out</span>
  <span m='708730'>in</span> <span m='708850'>a</span> <span
  m='708910'>straight</span> <span m='709240'>line.</span> <span
  m='710260'>And</span> <span m='710680'>that's</span> <span
  m='710890'>also</span> <span m='711250'>a</span> <span
  m='711310'>picture</span> <span m='712240'>that</span> <span
  m='712540'>will</span> <span m='712810'>recur</span> <span
  m='713200'>several</span> <span m='713620'>times</span> <span
  m='714160'>as</span> <span m='714310'>we</span> <span m='714400'>go</span>
  <span m='714610'>through</span> <span m='714790'>the</span> <span
  m='714880'>next</span> <span m='715060'>several</span> <span
  m='715420'>lectures.</span> <span m='716530'>So</span> <span
  m='716920'>we</span> <span m='717040'>can</span> <span
  m='717190'>generate</span> <span m='717640'>the</span> <span
  m='717760'>periodic</span> <span m='718330'>sequence</span> <span
  m='719230'>from</span> <span m='719380'>the</span> <span
  m='719470'>finite</span> <span m='719890'>length</span> <span
  m='720130'>sequence.</span> </p><p><span m='721690'>We</span> <span
  m='721810'>can</span> <span m='721990'>also</span> <span
  m='722710'>recover</span> <span m='724910'>the</span> <span
  m='725450'>sequence</span> <span m='726020'>x</span> <span
  m='726320'>of</span> <span m='726470'>n</span> <span m='727700'>from</span>
  <span m='727910'>the</span> <span m='728000'>periodic</span> <span
  m='728600'>sequence</span> <span m='729500'>by</span> <span
  m='729770'>extracting</span> <span m='730910'>just</span> <span
  m='731150'>one</span> <span m='731390'>period,</span> <span
  m='732440'>as</span> <span m='732650'>I've</span> <span
  m='732800'>indicated</span> <span m='733370'>here,</span> <span
  m='735110'>x</span> <span m='735380'>of</span> <span m='735500'>n</span> <span
  m='735830'>is</span> <span m='736010'>x</span> <span m='736220'>tilde</span>
  <span m='736490'>of</span> <span m='736640'>n</span> <span
  m='737160'>in</span> <span m='737300'>the</span> <span
  m='737390'>range,</span> <span m='738020'>little</span> <span
  m='738260'>n</span> <span m='738470'>between</span> <span m='738860'>0</span>
  <span m='739400'>and</span> <span m='739520'>capital</span> <span
  m='740030'>N</span> <span m='740150'>minus</span> <span m='740540'>1.</span>
  <span m='741530'>And</span> <span m='741650'>it's</span> <span
  m='741770'>equal</span> <span m='742070'>to</span> <span m='742220'>0,</span>
  <span m='742670'>otherwise.</span> <span m='744200'>Or</span> <span
  m='744890'>what</span> <span m='745220'>we'll</span> <span
  m='745430'>use</span> <span m='745790'>as</span> <span m='745940'>a</span>
  <span m='746030'>convenient</span> <span m='746720'>form</span> <span
  m='747020'>of</span> <span m='747110'>notation</span> <span
  m='747770'>for</span> <span m='747950'>that</span> <span m='748730'>is</span>
  <span m='749360'>to</span> <span m='749510'>express</span> <span m='750050'>x
  of n,</span> <span m='751150'>the</span> <span m='751250'>finite</span> <span
  m='751700'>length</span> <span m='751910'>sequence,</span> <span
  m='753560'>as</span> <span m='753950'>the</span> <span
  m='754070'>periodic</span> <span m='754670'>sequence,</span> <span
  m='755260'>x</span> <span m='755540'>tilde</span> <span m='755770'>of</span>
  <span m='755930'>n</span> <span m='757130'>multiplied</span> <span
  m='758480'>by</span> <span m='758870'>another</span> <span
  m='759230'>sequence,</span> <span m='760010'>which</span> <span
  m='760330'>I'll</span> <span m='760490'>denote</span> <span
  m='761060'>as</span> <span m='761470'>R</span> <span m='761840'>sub</span>
  <span m='761990'>capital</span> <span m='762500'>N</span> <span
  m='762870'>of</span> <span m='763240'>n,</span> <span m='764750'>where</span>
  <span m='765170'>R sub</span> <span m='765560'>capital</span> <span
  m='766040'>N of n</span> <span m='766550'>is</span> <span
  m='766700'>just</span> <span m='766880'>simply</span> <span
  m='767300'>a</span> <span m='767360'>rectangular</span> <span
  m='768050'>sequence.</span> </p><p><span m='769810'>So R</span> <span
  m='770030'>sub</span> <span m='770250'>capital</span> <span
  m='770710'>N</span> <span m='771030'>of n</span> <span m='771650'>is</span>
  <span m='771830'>1</span> <span m='772750'>for</span> <span
  m='772880'>little</span> <span m='773180'>n</span> <span
  m='773600'>between</span> <span m='773990'>0</span> <span
  m='774530'>and</span> <span m='774680'>capital</span> <span
  m='775160'>N</span> <span m='775280'>minus</span> <span m='775670'>1,</span>
  <span m='776630'>and</span> <span m='777050'>it's</span> <span
  m='777230'>equal</span> <span m='777530'>to</span> <span m='777650'>0,</span>
  <span m='778210'>otherwise.</span> <span m='780200'>All</span> <span
  m='780260'>right.</span> <span m='780510'>So</span> <span
  m='780890'>it's</span> <span m='781100'>important</span> <span
  m='781580'>to</span> <span m='781730'>begin,</span> <span m='782090'>at</span>
  <span m='782180'>this</span> <span m='782420'>point,</span> <span
  m='783490'>to</span> <span m='784070'>think</span> <span m='784550'>of</span>
  <span m='784730'>finite</span> <span m='785270'>length</span> <span
  m='785910'>and</span> <span m='786050'>periodic</span> <span
  m='786890'>sequences</span> <span m='788150'>as</span> <span
  m='788330'>more</span> <span m='788600'>or</span> <span m='788630'>less</span>
  <span m='789200'>the</span> <span m='789320'>same</span> <span
  m='789620'>type</span> <span m='789950'>of</span> <span
  m='790040'>thing</span> <span m='790400'>in</span> <span m='790490'>the</span>
  <span m='790580'>sense</span> <span m='790940'>that</span> <span
  m='791060'>it's</span> <span m='791210'>easy</span> <span m='791510'>to</span>
  <span m='791630'>go</span> <span m='791810'>back</span> <span
  m='792080'>and</span> <span m='792170'>forth</span> <span
  m='792530'>from</span> <span m='792740'>one</span> <span m='792950'>to</span>
  <span m='793070'>the</span> <span m='793220'>other.</span> </p><p><span
  m='795010'>Now,</span> <span m='795180'>why</span> <span m='795480'>is</span>
  <span m='795870'>this</span> <span m='796230'>point</span> <span
  m='796500'>of</span> <span m='796560'>view</span> <span
  m='796770'>important?</span> <span m='798240'>Well,</span> <span
  m='799110'>we</span> <span m='799260'>know</span> <span
  m='799770'>certainly</span> <span m='800250'>in</span> <span
  m='800340'>the</span> <span m='800400'>continuous</span> <span
  m='801000'>time</span> <span m='801300'>case</span> <span
  m='802140'>that</span> <span m='802530'>a</span> <span
  m='802590'>periodic</span> <span m='803190'>time</span> <span
  m='803490'>function</span> <span m='804180'>can</span> <span
  m='804360'>be</span> <span m='804480'>represented</span> <span
  m='805380'>by</span> <span m='805740'>a</span> <span m='805830'>Fourier</span>
  <span m='806250'>series.</span> <span m='807730'>In</span> <span
  m='807830'>the</span> <span m='807910'>discrete</span> <span
  m='808360'>time</span> <span m='808720'>case,</span> <span m='809350'>a</span>
  <span m='809410'>periodic</span> <span m='809980'>sequence,</span> <span
  m='810760'>likewise,</span> <span m='811780'>can</span> <span
  m='811930'>be</span> <span m='812050'>represented</span> <span
  m='812890'>by</span> <span m='813070'>a</span> <span m='813130'>Fourier</span>
  <span m='813610'>series.</span> <span m='814960'>And</span> <span
  m='815530'>the</span> <span m='815680'>idea,</span> <span
  m='816550'>that</span> <span m='816730'>is,</span> <span m='817060'>the</span>
  <span m='817210'>key</span> <span m='818020'>point</span> <span
  m='818440'>behind</span> <span m='818830'>the</span> <span
  m='818920'>discrete</span> <span m='819340'>Fourier</span> <span
  m='819790'>transform</span> <span m='821410'>is</span> <span
  m='821680'>that</span> <span m='822460'>we</span> <span m='822580'>can</span>
  <span m='822790'>use</span> <span m='823390'>the</span> <span
  m='824070'>Fourier</span> <span m='824500'>series</span> <span
  m='825040'>representation</span> <span m='826450'>of</span> <span
  m='826570'>the</span> <span m='826690'>periodic</span> <span
  m='827320'>sequence</span> <span m='828430'>to</span> <span
  m='828550'>represent</span> <span m='829810'>the</span> <span
  m='829900'>finite</span> <span m='830380'>length</span> <span
  m='830590'>sequence.</span> <span m='831670'>That</span> <span
  m='831850'>is,</span> <span m='832120'>that,</span> <span m='832460'>in</span>
  <span m='832630'>essence,</span> <span m='833050'>provides</span> <span
  m='833960'>a</span> <span m='834110'>Fourier</span> <span
  m='834730'>kind</span> <span m='835000'>of</span> <span
  m='835120'>representation</span> <span m='836470'>for</span> <span
  m='836770'>a</span> <span m='836860'>finite</span> <span
  m='837310'>length</span> <span m='837520'>sequence.</span> </p><p><span
  m='838720'>So</span> <span m='839290'>we</span> <span m='839500'>have</span>
  <span m='839710'>the</span> <span m='839800'>notion</span> <span
  m='840350'>then</span> <span m='841630'>that</span> <span
  m='842650'>the</span> <span m='843250'>periodic</span> <span
  m='843910'>sequence</span> <span m='844680'>x</span> <span
  m='844930'>tilde</span> <span m='845250'>of</span> <span m='845430'>n</span>
  <span m='846460'>has</span> <span m='846900'>a</span> <span
  m='847000'>Fourier</span> <span m='847510'>series</span> <span
  m='848320'>representation.</span> <span m='850940'>We</span> <span
  m='851090'>can</span> <span m='851390'>compute</span> <span
  m='853230'>the</span> <span m='853440'>discrete</span> <span
  m='854220'>Fourier</span> <span m='854700'>series</span> <span
  m='855660'>of</span> <span m='856290'>this</span> <span
  m='856470'>periodic</span> <span m='857280'>sequence.</span> <span
  m='858780'>And</span> <span m='859140'>as</span> <span m='859380'>we'll</span>
  <span m='859560'>see--</span> <span m='860190'>not</span> <span
  m='860400'>in</span> <span m='860490'>this</span> <span
  m='860670'>lecture,</span> <span m='861120'>but</span> <span
  m='861480'>as</span> <span m='861690'>we'll</span> <span m='861840'>see</span>
  <span m='862320'>in</span> <span m='862500'>more</span> <span
  m='862650'>detail</span> <span m='863160'>in</span> <span
  m='863250'>the</span> <span m='863310'>next</span> <span
  m='863580'>lecture--</span> <span m='864690'>it</span> <span
  m='864960'>is</span> <span m='865410'>discrete</span> <span
  m='865960'>Fourier</span> <span m='866430'>series</span> <span
  m='867630'>representation</span> <span m='869160'>of</span> <span
  m='869340'>this</span> <span m='869940'>periodic</span> <span
  m='870780'>sequence</span> <span m='872520'>that</span> <span
  m='872910'>is</span> <span m='873120'>what</span> <span
  m='873330'>we'll</span> <span m='873540'>call</span> <span
  m='874470'>the</span> <span m='874560'>discrete</span> <span
  m='875040'>Fourier</span> <span m='875490'>transform</span> <span
  m='876390'>of</span> <span m='876630'>x</span> <span m='876900'>of</span>
  <span m='877000'>n.</span> </p><p><span m='878820'>So</span> <span
  m='879330'>let's</span> <span m='879600'>begin</span> <span
  m='880070'>then</span> <span m='880860'>with</span> <span m='881280'>a</span>
  <span m='881370'>discussion</span> <span m='882240'>of</span> <span
  m='882810'>the</span> <span m='882930'>discrete</span> <span
  m='883320'>Fourier</span> <span m='883740'>series</span> <span
  m='884490'>of</span> <span m='884640'>periodic</span> <span
  m='885240'>sequences</span> <span m='886740'>with</span> <span
  m='886950'>the</span> <span m='887100'>idea</span> <span
  m='887940'>that</span> <span m='888330'>we'll</span> <span
  m='888540'>be</span> <span m='888690'>applying</span> <span
  m='889620'>that</span> <span m='890010'>representation</span> <span
  m='891630'>to</span> <span m='892080'>the</span> <span
  m='892200'>representation</span> <span m='893190'>of</span> <span
  m='893280'>finite</span> <span m='893730'>length</span> <span
  m='893940'>sequence.</span> <span m='894810'>And</span> <span
  m='895500'>that</span> <span m='895710'>representation</span> <span
  m='896670'>is</span> <span m='896880'>what</span> <span m='897030'>will</span>
  <span m='897180'>correspond</span> <span m='898320'>to</span> <span
  m='898590'>the</span> <span m='898710'>discrete</span> <span
  m='899100'>Fourier</span> <span m='899550'>transform.</span> <span
  m='901490'>OK.</span> <span m='901990'>So</span> <span m='902380'>we</span>
  <span m='902560'>want</span> <span m='902740'>to</span> <span
  m='902800'>talk</span> <span m='903130'>about</span> <span
  m='903760'>the</span> <span m='904030'>discrete</span> <span
  m='904450'>Fourier</span> <span m='904900'>series.</span> <span
  m='906930'>We're</span> <span m='907080'>considering</span> <span
  m='908160'>a</span> <span m='908220'>sequence</span> <span m='909060'>x</span>
  <span m='909330'>tilde</span> <span m='909720'>of</span> <span
  m='909870'>n,</span> <span m='911440'>which</span> <span m='911620'>is</span>
  <span m='911740'>periodic,</span> <span m='913430'>and</span> <span
  m='914530'>it's</span> <span m='914750'>period</span> <span
  m='915470'>we'll</span> <span m='915620'>call</span> <span
  m='916320'>capital</span> <span m='916595'>N.</span> </p><p><span
  m='919160'>In</span> <span m='919370'>the</span> <span
  m='919880'>continuous</span> <span m='920480'>time</span> <span
  m='920810'>case,</span> <span m='921570'>we</span> <span
  m='921590'>know</span> <span m='921860'>that</span> <span m='922010'>if</span>
  <span m='922130'>we</span> <span m='922220'>have</span> <span
  m='922370'>a</span> <span m='922430'>periodic</span> <span
  m='923000'>time</span> <span m='923300'>function,</span> <span
  m='924470'>we</span> <span m='924590'>can</span> <span
  m='924770'>represent</span> <span m='925340'>it</span> <span
  m='925970'>as</span> <span m='926570'>a</span> <span m='926630'>linear</span>
  <span m='927020'>combination</span> <span m='927950'>of</span> <span
  m='928190'>harmonically</span> <span m='928910'>related</span> <span
  m='929630'>complex</span> <span m='930200'>exponentials.</span> <span
  m='931070'>That's</span> <span m='931820'>the</span> <span
  m='932210'>Fourier</span> <span m='932660'>series</span> <span
  m='933050'>representation</span> <span m='933920'>in</span> <span
  m='934010'>the</span> <span m='934100'>continuous</span> <span
  m='934670'>time</span> <span m='934970'>case.</span> <span
  m='936150'>And</span> <span m='936440'>I'll</span> <span
  m='936590'>just</span> <span m='936770'>simply</span> <span
  m='937220'>state</span> <span m='937820'>without</span> <span
  m='938540'>proof</span> <span m='939500'>that</span> <span
  m='940400'>the</span> <span m='940520'>same</span> <span
  m='940940'>kind</span> <span m='941210'>of</span> <span
  m='941300'>relationship</span> <span m='942500'>holds</span> <span
  m='942920'>in</span> <span m='943040'>the</span> <span
  m='943130'>discrete</span> <span m='943520'>time</span> <span
  m='943880'>case.</span> <span m='944750'>That</span> <span
  m='944990'>is,</span> <span m='945710'>we</span> <span m='945860'>can</span>
  <span m='946040'>represent</span> <span m='947030'>a</span> <span
  m='947090'>periodic</span> <span m='947750'>sequence</span> <span
  m='948650'>x</span> <span m='948890'>tilde</span> <span m='949190'>of</span>
  <span m='949370'>n</span> <span m='950900'>as</span> <span m='951050'>a</span>
  <span m='951110'>linear</span> <span m='951470'>combination</span> <span
  m='953180'>of</span> <span m='953870'>complex</span> <span
  m='954500'>exponentials,</span> <span m='956250'>which</span> <span
  m='956540'>are</span> <span m='956900'>harmonically</span> <span
  m='957680'>related</span> <span m='958730'>to</span> <span
  m='959300'>the</span> <span m='959420'>frequency.</span> </p><p><span
  m='960260'>Or</span> <span m='960470'>equivalently,</span> <span
  m='961610'>the</span> <span m='961700'>reciprocal</span> <span
  m='962570'>of</span> <span m='962990'>the</span> <span
  m='963080'>period,</span> <span m='964100'>so</span> <span
  m='964340'>that</span> <span m='965000'>this</span> <span
  m='965270'>forms</span> <span m='966110'>a</span> <span
  m='966410'>general</span> <span m='966830'>relationship</span> <span
  m='968360'>for</span> <span m='969470'>a</span> <span
  m='969770'>discrete</span> <span m='970250'>Fourier</span> <span
  m='970670'>series</span> <span m='971330'>of</span> <span m='971585'>a</span>
  <span m='971840'>periodic</span> <span m='972440'>sequence</span> <span
  m='973290'>x</span> <span m='973510'>tilde</span> <span m='973670'>of</span>
  <span m='973880'>n.</span> <span m='975440'>That</span> <span
  m='975620'>is,</span> <span m='975770'>these</span> <span
  m='976040'>are</span> <span m='976100'>the</span> <span
  m='976220'>harmonically</span> <span m='976790'>related</span> <span
  m='977510'>complex</span> <span m='978050'>exponentials,</span> <span
  m='979310'>just</span> <span m='979610'>as</span> <span m='980240'>we</span>
  <span m='980840'>form</span> <span m='981170'>linear</span> <span
  m='981440'>combinations</span> <span m='982310'>of</span> <span
  m='982460'>harmonically</span> <span m='983060'>related</span> <span
  m='983810'>complex</span> <span m='984350'>exponentials</span> <span
  m='984800'>for</span> <span m='985250'>the</span> <span
  m='985470'>Fourier</span> <span m='986120'>series</span> <span
  m='986690'>in</span> <span m='986810'>a</span> <span
  m='986870'>continuous</span> <span m='987470'>time</span> <span
  m='987740'>case.</span> <span m='989560'>What</span> <span
  m='989710'>are</span> <span m='989770'>the</span> <span
  m='989890'>Fourier</span> <span m='990250'>coefficients?</span> <span
  m='991190'>Well,</span> <span m='991870'>it's,</span> <span
  m='992080'>of</span> <span m='992200'>course,</span> <span
  m='992680'>these</span> <span m='993640'>capital</span> <span
  m='994050'>X</span> <span m='994240'>tildes</span> <span m='994840'>of</span>
  <span m='995050'>k,</span> <span m='995980'>which</span> <span
  m='997030'>we'll</span> <span m='997240'>have</span> <span m='997390'>a</span>
  <span m='997450'>little</span> <span m='997660'>more</span> <span
  m='998020'>to</span> <span m='998140'>say</span> <span m='998350'>about</span>
  <span m='998790'>in</span> <span m='998920'>a</span> <span
  m='998980'>minute.</span> </p><p><span m='1001030'>Well,</span> <span
  m='1002110'>notice</span> <span m='1002560'>that</span> <span
  m='1002770'>I</span> <span m='1002890'>haven't</span> <span
  m='1003550'>specified</span> <span m='1004480'>as</span> <span
  m='1004720'>of</span> <span m='1004870'>yet</span> <span
  m='1005650'>any</span> <span m='1005830'>limits</span> <span
  m='1006520'>on</span> <span m='1006700'>this</span> <span
  m='1006840'>summation.</span> <span m='1008560'>And</span> <span
  m='1009700'>in</span> <span m='1009820'>particular,</span> <span
  m='1010970'>what</span> <span m='1011140'>we</span> <span
  m='1011290'>need</span> <span m='1011470'>to</span> <span
  m='1011650'>examine</span> <span m='1012910'>is</span> <span
  m='1013690'>how</span> <span m='1013840'>many</span> <span
  m='1014110'>distinct</span> <span m='1015280'>periodically</span> <span
  m='1016330'>or</span> <span m='1016510'>harmonically</span> <span
  m='1017140'>related</span> <span m='1017980'>complex</span> <span
  m='1018580'>exponentials</span> <span m='1019690'>there</span> <span
  m='1019900'>are.</span> <span m='1021590'>Well,</span> <span
  m='1022070'>let's</span> <span m='1022370'>take</span> <span
  m='1022640'>a</span> <span m='1022730'>look</span> <span m='1023930'>at</span>
  <span m='1025130'>the</span> <span m='1025220'>complex</span> <span
  m='1025790'>exponential,</span> <span m='1026819'>the</span> <span
  m='1026930'>set</span> <span m='1027140'>of</span> <span
  m='1027230'>complex</span> <span m='1027770'>exponentials</span> <span
  m='1029030'>e to</span> <span m='1029329'>the</span> <span
  m='1029450'>j,</span> <span m='1029810'>2</span> <span m='1030020'>pi</span>
  <span m='1030470'>over</span> <span m='1030710'>capital</span> <span
  m='1031250'>N,</span> <span m='1031700'>little</span> <span
  m='1031970'>nk.</span> <span m='1033869'>And</span> <span
  m='1034020'>the</span> <span m='1034109'>statement</span> <span
  m='1034560'>that</span> <span m='1034680'>I</span> <span
  m='1034770'>want</span> <span m='1034980'>to</span> <span
  m='1035040'>make</span> <span m='1036000'>is</span> <span
  m='1036270'>that</span> <span m='1036780'>these</span> <span
  m='1037050'>complex</span> <span m='1037650'>exponentials</span> <span
  m='1039150'>are</span> <span m='1039270'>periodic.</span> <span
  m='1040290'>Of</span> <span m='1040349'>course,</span> <span
  m='1040560'>we</span> <span m='1040680'>know</span> <span
  m='1040859'>that</span> <span m='1040980'>they're</span> <span
  m='1041099'>periodic</span> <span m='1041730'>in</span> <span
  m='1041849'>n.</span> <span m='1043060'>But</span> <span
  m='1043500'>they're</span> <span m='1043630'>are</span> <span
  m='1043710'>also</span> <span m='1044190'>periodic</span> <span
  m='1044940'>in</span> <span m='1045079'>k.</span> </p><p><span
  m='1048300'>As</span> <span m='1048990'>we</span> <span
  m='1049200'>vary</span> <span m='1049740'>k</span> <span
  m='1050760'>from</span> <span m='1050970'>0</span> <span m='1051630'>to</span>
  <span m='1051810'>capital</span> <span m='1052350'>N</span> <span
  m='1052500'>minus</span> <span m='1052920'>1,</span> <span
  m='1054366'>we</span> <span m='1054850'>generate</span> <span
  m='1055750'>all</span> <span m='1056170'>of</span> <span
  m='1056350'>the</span> <span m='1056470'>possible</span> <span
  m='1057130'>harmonically</span> <span m='1057790'>related</span> <span
  m='1058240'>complex</span> <span m='1058840'>exponentials</span> <span
  m='1060130'>with</span> <span m='1060280'>this</span> <span
  m='1060490'>fundamental</span> <span m='1061060'>frequency,</span> <span
  m='1061660'>2</span> <span m='1061900'>pi</span> <span m='1062230'>over</span>
  <span m='1062440'>capital</span> <span m='1062890'>N.</span> <span
  m='1064010'>Well,</span> <span m='1064270'>we</span> <span
  m='1064420'>can</span> <span m='1064570'>see</span> <span
  m='1064810'>that</span> <span m='1065380'>very</span> <span
  m='1065740'>simply</span> <span m='1066490'>by</span> <span
  m='1066880'>substituting</span> <span m='1067720'>in</span> <span
  m='1067840'>for</span> <span m='1068020'>k,</span> <span m='1069550'>k</span>
  <span m='1070030'>plus</span> <span m='1070720'>capital</span> <span
  m='1071240'>N.</span> <span m='1072800'>And</span> <span
  m='1072920'>then</span> <span m='1073100'>recognizing</span> <span
  m='1075080'>that</span> <span m='1075470'>we</span> <span
  m='1075650'>can</span> <span m='1075830'>break</span> <span
  m='1076310'>this</span> <span m='1076490'>complex</span> <span
  m='1077060'>exponential</span> <span m='1077960'>into</span> <span
  m='1078200'>the</span> <span m='1078290'>product</span> <span
  m='1078800'>of</span> <span m='1078950'>two</span> <span
  m='1079430'>complex</span> <span m='1080000'>exponentials</span> <span
  m='1081650'>e</span> <span m='1081980'>to the</span> <span
  m='1082100'>j,</span> <span m='1082370'>2</span> <span m='1082580'>pi</span>
  <span m='1082940'>over</span> <span m='1083150'>capital</span> <span
  m='1083690'>N,</span> <span m='1084200'>nk,</span> <span
  m='1086420'>and</span> <span m='1087170'>e to</span> <span
  m='1087560'>the</span> <span m='1087680'>j,</span> <span m='1088370'>2</span>
  <span m='1088670'>pi</span> <span m='1089390'>over</span> <span
  m='1089990'>capital</span> <span m='1090590'>N</span> <span
  m='1091640'>times</span> <span m='1091970'>little</span> <span
  m='1092270'>n</span> <span m='1092960'>times</span> <span
  m='1093750'>capital</span> <span m='1094190'>N.</span> </p><p><span
  m='1095600'>Well,</span> <span m='1096250'>these</span> <span
  m='1096430'>capital</span> <span m='1096910'>N's</span> <span
  m='1097540'>cancel</span> <span m='1097960'>each</span> <span
  m='1098170'>other</span> <span m='1098440'>out.</span> <span
  m='1099370'>This</span> <span m='1099580'>factor</span> <span
  m='1100180'>is</span> <span m='1100390'>then</span> <span m='1100650'>e
  to</span> <span m='1100960'>the</span> <span m='1101080'>j,</span> <span
  m='1101330'>2</span> <span m='1101560'>pi</span> <span
  m='1101860'>times</span> <span m='1102220'>little</span> <span
  m='1102560'>n.</span> <span m='1103450'>Well,</span> <span
  m='1103870'>any</span> <span m='1104140'>integer</span> <span
  m='1104500'>multiple</span> <span m='1104950'>of</span> <span
  m='1105070'>2</span> <span m='1105250'>pi</span> <span m='1105880'>up</span>
  <span m='1106120'>here</span> <span m='1106960'>then</span> <span
  m='1107440'>just</span> <span m='1107650'>simply</span> <span
  m='1108250'>reduces</span> <span m='1108820'>this</span> <span
  m='1109750'>to</span> <span m='1109870'>unity.</span> <span
  m='1111250'>So</span> <span m='1111490'>that,</span> <span
  m='1111820'>in</span> <span m='1112000'>fact,</span> <span m='1113860'>e
  to</span> <span m='1114290'>the</span> <span m='1114440'>j,</span> <span
  m='1114680'>2</span> <span m='1114830'>pi</span> <span m='1115180'>over
  capital N,</span> <span m='1115740'>little</span> <span m='1116100'>n</span>
  <span m='1116790'>times</span> <span m='1117230'>k</span> <span
  m='1117530'>plus</span> <span m='1117800'>capital</span> <span
  m='1118310'>N</span> <span m='1119000'>is</span> <span m='1119180'>the</span>
  <span m='1119270'>same</span> <span m='1119840'>as</span> <span
  m='1120095'>e</span> <span m='1120350'>to the j,</span> <span
  m='1120620'>2</span> <span m='1120740'>pi</span> <span m='1121390'>over</span>
  <span m='1121580'>capital</span> <span m='1121835'>N,</span> <span
  m='1122540'>little</span> <span m='1122810'>n</span> <span
  m='1123230'>times</span> <span m='1123540'>k.</span> <span
  m='1125310'>Well,</span> <span m='1125430'>that</span> <span
  m='1125580'>shouldn't</span> <span m='1125820'>be</span> <span
  m='1125970'>surprising,</span> <span m='1126630'>actually,</span> <span
  m='1127620'>because</span> <span m='1128490'>that's</span> <span
  m='1128700'>a</span> <span m='1128790'>point</span> <span
  m='1129300'>that's</span> <span m='1129480'>come</span> <span
  m='1129780'>up</span> <span m='1130410'>time</span> <span
  m='1130740'>and</span> <span m='1130830'>again</span> <span
  m='1131100'>as</span> <span m='1131220'>we've</span> <span
  m='1131370'>been</span> <span m='1131520'>going</span> <span
  m='1131790'>through</span> <span m='1131970'>these</span> <span
  m='1132150'>lectures.</span> </p><p><span m='1133170'>The</span> <span
  m='1133260'>point</span> <span m='1133620'>being</span> <span
  m='1134400'>that</span> <span m='1135330'>sinusoids</span> <span
  m='1137310'>in</span> <span m='1138180'>the</span> <span
  m='1138420'>discrete</span> <span m='1138900'>time</span> <span
  m='1139950'>domain,</span> <span m='1141690'>as</span> <span
  m='1142140'>we</span> <span m='1142320'>vary</span> <span
  m='1142710'>sinusoids</span> <span m='1143400'>in</span> <span
  m='1143480'>frequency--</span> <span m='1144750'>we've</span> <span
  m='1144960'>seen</span> <span m='1145440'>time</span> <span
  m='1145740'>and</span> <span m='1145830'>again,</span> <span
  m='1146990'>in</span> <span m='1147600'>the</span> <span
  m='1147690'>range</span> <span m='1148170'>0</span> <span
  m='1148590'>to</span> <span m='1148740'>2</span> <span m='1148980'>pi--</span>
  <span m='1150400'>in</span> <span m='1150420'>fact,</span> <span
  m='1151090'>those</span> <span m='1151260'>are</span> <span
  m='1151380'>all</span> <span m='1151620'>the</span> <span
  m='1151710'>sinusoids</span> <span m='1152760'>that</span> <span
  m='1152880'>we</span> <span m='1153000'>can</span> <span
  m='1153180'>generate.</span> <span m='1154230'>And</span> <span
  m='1154380'>if</span> <span m='1154500'>we</span> <span
  m='1154620'>keep</span> <span m='1154860'>going</span> <span
  m='1155220'>in</span> <span m='1155310'>frequency,</span> <span
  m='1156180'>we</span> <span m='1156330'>just</span> <span
  m='1156510'>simply</span> <span m='1156870'>see</span> <span
  m='1157020'>the</span> <span m='1157140'>same</span> <span
  m='1157440'>ones</span> <span m='1157710'>over</span> <span
  m='1158010'>again.</span> <span m='1159070'>So</span> <span
  m='1159690'>this</span> <span m='1159990'>is</span> <span m='1160200'>a</span>
  <span m='1160260'>consequence</span> <span m='1161010'>of</span> <span
  m='1161130'>that.</span> </p><p><span m='1162210'>But</span> <span
  m='1162390'>for</span> <span m='1162570'>the</span> <span
  m='1162660'>discrete</span> <span m='1163050'>Fourier</span> <span
  m='1163470'>series,</span> <span m='1164420'>it</span> <span
  m='1164670'>says</span> <span m='1164820'>an</span> <span
  m='1164910'>important</span> <span m='1165360'>thing.</span> <span
  m='1165900'>It</span> <span m='1166050'>says</span> <span
  m='1166920'>that</span> <span m='1167520'>in</span> <span
  m='1168240'>forming</span> <span m='1168780'>the</span> <span
  m='1168900'>discrete</span> <span m='1169290'>Fourier</span> <span
  m='1169710'>series,</span> <span m='1171300'>once</span> <span
  m='1171600'>we've</span> <span m='1171810'>used</span> <span
  m='1172140'>the</span> <span m='1172260'>complex</span> <span
  m='1172830'>exponentials</span> <span m='1175120'>for</span> <span
  m='1175300'>k</span> <span m='1176410'>between</span> <span
  m='1176800'>0</span> <span m='1177400'>and</span> <span
  m='1177550'>capital</span> <span m='1178030'>N</span> <span
  m='1178150'>minus</span> <span m='1178550'>1,</span> <span
  m='1179680'>we've</span> <span m='1179890'>used</span> <span
  m='1180310'>all</span> <span m='1180610'>the</span> <span
  m='1180700'>complex</span> <span m='1181270'>exponentials</span> <span
  m='1182440'>with</span> <span m='1182590'>this</span> <span
  m='1182800'>fundamental</span> <span m='1183370'>frequency</span> <span
  m='1184180'>that</span> <span m='1184300'>we</span> <span
  m='1184480'>have.</span> <span m='1185680'>And</span> <span
  m='1185800'>if</span> <span m='1185890'>we</span> <span
  m='1186010'>keep</span> <span m='1186610'>going</span> <span
  m='1186970'>with</span> <span m='1187150'>k,</span> <span
  m='1187960'>we're</span> <span m='1188080'>just</span> <span
  m='1188290'>simply</span> <span m='1188710'>going</span> <span
  m='1188920'>to</span> <span m='1189010'>see</span> <span
  m='1189490'>the</span> <span m='1189610'>same</span> <span
  m='1189910'>complex</span> <span m='1190450'>exponentials</span> <span
  m='1191440'>over</span> <span m='1191800'>and</span> <span
  m='1191890'>over</span> <span m='1192190'>again.</span> </p><p><span
  m='1193900'>What</span> <span m='1194080'>does</span> <span
  m='1194200'>that</span> <span m='1194380'>say</span> <span
  m='1194620'>about</span> <span m='1194920'>the</span> <span
  m='1195010'>discrete</span> <span m='1195400'>Fourier</span> <span
  m='1195820'>series?</span> <span m='1196480'>It</span> <span
  m='1196630'>says</span> <span m='1197530'>that</span> <span
  m='1197950'>in</span> <span m='1198430'>the</span> <span
  m='1198520'>representation</span> <span m='1199900'>of</span> <span
  m='1200020'>the</span> <span m='1200110'>discrete</span> <span
  m='1200500'>Fourier</span> <span m='1200950'>series,</span> <span
  m='1202300'>the</span> <span m='1202390'>limits</span> <span
  m='1202780'>on</span> <span m='1202960'>this</span> <span
  m='1203120'>sum</span> <span m='1206590'>don't</span> <span
  m='1207310'>range</span> <span m='1207670'>from</span> <span
  m='1207820'>minus</span> <span m='1208210'>infinity</span> <span
  m='1208870'>to</span> <span m='1209020'>plus</span> <span
  m='1209320'>infinity.</span> <span m='1210400'>They</span> <span
  m='1210490'>run</span> <span m='1210790'>simply</span> <span
  m='1211600'>from</span> <span m='1211840'>0</span> <span m='1213100'>to</span>
  <span m='1213820'>capital</span> <span m='1214300'>N</span> <span
  m='1214450'>minus</span> <span m='1214810'>1.</span> <span
  m='1216265'>So</span> <span m='1216750'>once</span> <span
  m='1217200'>I've</span> <span m='1217410'>looked</span> <span
  m='1217890'>at</span> <span m='1219490'>these</span> <span
  m='1220540'>linear</span> <span m='1220900'>combination</span> <span
  m='1221500'>of</span> <span m='1221620'>these</span> <span
  m='1221830'>complex</span> <span m='1222370'>exponentials</span> <span
  m='1223180'>for</span> <span m='1223330'>k</span> <span
  m='1223630'>between</span> <span m='1224020'>0</span> <span
  m='1224500'>and</span> <span m='1224620'>capital</span> <span
  m='1225130'>N</span> <span m='1225250'>minus</span> <span
  m='1225610'>1,</span> <span m='1226390'>there</span> <span
  m='1226570'>are</span> <span m='1226630'>no</span> <span
  m='1226900'>new</span> <span m='1227140'>complex</span> <span
  m='1227680'>exponentials</span> <span m='1228880'>with</span> <span
  m='1229000'>that</span> <span m='1229210'>fundamental</span> <span
  m='1229720'>frequency</span> <span m='1230260'>that</span> <span
  m='1230410'>I'm</span> <span m='1230560'>able</span> <span
  m='1230800'>to</span> <span m='1230920'>find.</span> </p><p><span
  m='1232790'>So</span> <span m='1233000'>this</span> <span
  m='1233270'>then</span> <span m='1233690'>is</span> <span
  m='1234290'>the</span> <span m='1234410'>form</span> <span
  m='1234980'>of</span> <span m='1235580'>the</span> <span
  m='1235820'>discrete</span> <span m='1236240'>Fourier</span> <span
  m='1236690'>series.</span> <span m='1237980'>There's</span> <span
  m='1238490'>one</span> <span m='1238940'>additional</span> <span
  m='1240200'>insertion</span> <span m='1240770'>that</span> <span
  m='1240890'>I'd</span> <span m='1241040'>like</span> <span
  m='1241250'>to</span> <span m='1241370'>make.</span> <span
  m='1242150'>And</span> <span m='1242240'>this</span> <span
  m='1242450'>is</span> <span m='1242600'>just</span> <span
  m='1242990'>simply</span> <span m='1243710'>a</span> <span
  m='1244280'>normalization</span> <span m='1245150'>factor.</span> <span
  m='1247190'>I</span> <span m='1247310'>want</span> <span m='1247460'>to</span>
  <span m='1247550'>multiply</span> <span m='1248420'>this</span> <span
  m='1248690'>by</span> <span m='1248870'>1 over</span> <span
  m='1249330'>capital</span> <span m='1249820'>N.</span> <span
  m='1250310'>Obviously,</span> <span m='1250910'>that</span> <span
  m='1251090'>doesn't</span> <span m='1251360'>make</span> <span
  m='1251630'>any</span> <span m='1251840'>essential</span> <span
  m='1252320'>difference.</span> <span m='1253200'>It's</span> <span
  m='1253220'>just</span> <span m='1253460'>a</span> <span
  m='1253520'>factor</span> <span m='1254120'>for</span> <span
  m='1254340'>normalization.</span> <span m='1255770'>And</span> <span
  m='1256550'>it</span> <span m='1256790'>plays</span> <span
  m='1257180'>a</span> <span m='1257240'>role</span> <span
  m='1258590'>which</span> <span m='1258800'>is</span> <span
  m='1258920'>similar</span> <span m='1259550'>in</span> <span
  m='1259740'>the</span> <span m='1260060'>continuous</span> <span
  m='1260600'>time</span> <span m='1260900'>case</span> <span
  m='1261710'>to</span> <span m='1261950'>the</span> <span
  m='1262070'>role</span> <span m='1262400'>that</span> <span
  m='1262970'>2</span> <span m='1263150'>pi</span> <span m='1263510'>or</span>
  <span m='1263600'>1</span> <span m='1263810'>over</span> <span
  m='1264020'>2</span> <span m='1264230'>pi</span> <span
  m='1264830'>plays.</span> </p><p><span m='1267540'>All</span> <span
  m='1267600'>right.</span> <span m='1268050'>So</span> <span
  m='1268350'>here</span> <span m='1268560'>we</span> <span
  m='1268710'>have</span> <span m='1269070'>the</span> <span
  m='1269470'>discrete</span> <span m='1270120'>Fourier</span> <span
  m='1270300'>series.</span> <span m='1272470'>It's</span> <span
  m='1272980'>relatively</span> <span m='1273550'>straightforward</span> <span
  m='1274750'>to</span> <span m='1275290'>show</span> <span
  m='1276370'>that</span> <span m='1276880'>you</span> <span
  m='1277060'>can</span> <span m='1277240'>obtain</span> <span
  m='1277600'>the</span> <span m='1278400'>Fourier</span> <span
  m='1278870'>series</span> <span m='1279310'>coefficients</span> <span
  m='1280510'>x</span> <span m='1281110'>tilde</span> <span
  m='1281430'>of</span> <span m='1281650'>k</span> <span m='1282790'>from</span>
  <span m='1283000'>x</span> <span m='1283270'>tilde</span> <span
  m='1283510'>of</span> <span m='1283750'>n</span> <span
  m='1284860'>through</span> <span m='1285430'>an</span> <span
  m='1285610'>inverse</span> <span m='1286090'>relationship,</span> <span
  m='1287480'>which</span> <span m='1287620'>is</span> <span
  m='1288100'>the</span> <span m='1288220'>relationship</span> <span
  m='1289180'>that</span> <span m='1289450'>I've</span> <span
  m='1289660'>indicated</span> <span m='1290230'>here.</span> <span
  m='1291920'>So</span> <span m='1292370'>this</span> <span
  m='1292880'>is</span> <span m='1293210'>then,</span> <span
  m='1293960'>in</span> <span m='1294110'>essence,</span> <span
  m='1294800'>the</span> <span m='1295110'>inverse</span> <span
  m='1295700'>discrete</span> <span m='1296120'>Fourier</span> <span
  m='1296540'>series,</span> <span m='1297530'>or</span> <span
  m='1298040'>equivalently,</span> <span m='1298880'>the</span> <span
  m='1298970'>relationship</span> <span m='1300140'>for</span> <span
  m='1300290'>obtaining</span> <span m='1301340'>the</span> <span
  m='1301610'>discrete</span> <span m='1302930'>Fourier</span> <span
  m='1303320'>series</span> <span m='1303710'>coefficients</span> <span
  m='1304910'>from</span> <span m='1305060'>the</span> <span
  m='1305150'>periodic</span> <span m='1305720'>sequence</span> <span
  m='1306440'>x</span> <span m='1306700'>tilde</span> <span
  m='1307040'>of</span> <span m='1307370'>n.</span> </p><p><span
  m='1309160'>Now</span> <span m='1309520'>notice</span> <span
  m='1310000'>that</span> <span m='1310520'>I've</span> <span
  m='1311500'>happened</span> <span m='1311860'>to</span> <span
  m='1312040'>write</span> <span m='1312760'>the</span> <span
  m='1312970'>Fourier</span> <span m='1313360'>series</span> <span
  m='1313750'>coefficients</span> <span m='1315130'>with</span> <span
  m='1315500'>a tilde</span> <span m='1316240'>over</span> <span
  m='1316570'>them,</span> <span m='1317710'>implying</span> <span
  m='1318760'>that</span> <span m='1319690'>those</span> <span
  m='1320380'>coefficients</span> <span m='1321340'>are</span> <span
  m='1321490'>themselves</span> <span m='1322030'>periodic.</span> <span
  m='1324310'>Well,</span> <span m='1324540'>are</span> <span
  m='1324750'>they</span> <span m='1324900'>periodic,</span> <span
  m='1325710'>or</span> <span m='1325830'>aren't</span> <span
  m='1326130'>they</span> <span m='1326250'>periodic?</span> <span
  m='1328490'>What</span> <span m='1328610'>I've</span> <span
  m='1328730'>been</span> <span m='1328880'>saying</span> <span
  m='1329390'>here</span> <span m='1330200'>and</span> <span
  m='1330440'>what</span> <span m='1330590'>I've</span> <span
  m='1330710'>been</span> <span m='1330830'>saying</span> <span
  m='1331220'>here--</span> <span m='1331520'>and</span> <span
  m='1331640'>I've</span> <span m='1331730'>spent</span> <span
  m='1332000'>a</span> <span m='1332030'>long</span> <span
  m='1332330'>time</span> <span m='1332600'>saying</span> <span
  m='1333050'>this--</span> <span m='1334250'>that</span> <span
  m='1335000'>there</span> <span m='1335210'>are</span> <span
  m='1335420'>only</span> <span m='1335690'>a</span> <span
  m='1335780'>finite</span> <span m='1336170'>number</span> <span
  m='1336440'>of</span> <span m='1336530'>complex</span> <span
  m='1337070'>exponentials.</span> <span m='1338330'>Once</span> <span
  m='1338600'>I've</span> <span m='1338750'>looked</span> <span
  m='1338990'>at</span> <span m='1339200'>them</span> <span
  m='1339890'>in</span> <span m='1340040'>the</span> <span
  m='1340130'>range</span> <span m='1340430'>0</span> <span
  m='1340760'>to</span> <span m='1340850'>capital</span> <span
  m='1341270'>N</span> <span m='1341390'>minus</span> <span m='1341720'>1,
  I've</span> <span m='1342110'>seen</span> <span m='1342380'>all</span> <span
  m='1342620'>the</span> <span m='1342710'>ones</span> <span
  m='1343010'>I</span> <span m='1343100'>can</span> <span
  m='1343280'>see.</span> </p><p><span m='1344930'>And</span> <span
  m='1345050'>in</span> <span m='1345140'>that</span> <span
  m='1345350'>sense,</span> <span m='1346890'>the</span> <span
  m='1346990'>Fourier</span> <span m='1347330'>series</span> <span
  m='1347720'>coefficients,</span> <span m='1349080'>x</span> <span
  m='1349390'>tilde</span> <span m='1349610'>of</span> <span
  m='1349860'>k,</span> <span m='1352070'>are</span> <span
  m='1352190'>finite.</span> <span m='1352730'>That</span> <span
  m='1352880'>is,</span> <span m='1353060'>there</span> <span
  m='1353210'>are</span> <span m='1353270'>only</span> <span
  m='1353510'>a</span> <span m='1353570'>finite</span> <span
  m='1353930'>number</span> <span m='1354300'>of</span> <span
  m='1354430'>them.</span> <span m='1355930'>Well,</span> <span
  m='1356230'>the</span> <span m='1356320'>important</span> <span
  m='1356740'>point</span> <span m='1357070'>is</span> <span
  m='1357220'>that</span> <span m='1357340'>there</span> <span
  m='1357430'>are</span> <span m='1357490'>only</span> <span
  m='1357730'>a</span> <span m='1357790'>finite</span> <span
  m='1358930'>number</span> <span m='1359350'>of</span> <span
  m='1359500'>distinct</span> <span m='1360400'>coefficients.</span> <span
  m='1362530'>Also</span> <span m='1362980'>in</span> <span
  m='1363070'>this</span> <span m='1363250'>relationship,</span> <span
  m='1365080'>whether</span> <span m='1365380'>I</span> <span
  m='1365470'>consider</span> <span m='1366490'>these</span> <span
  m='1366760'>as</span> <span m='1366880'>periodic</span> <span
  m='1367600'>or</span> <span m='1367750'>not</span> <span
  m='1368020'>periodic,</span> <span m='1368995'>I</span> <span
  m='1369250'>still</span> <span m='1369730'>only</span> <span
  m='1370030'>use</span> <span m='1370330'>a</span> <span
  m='1370420'>finite</span> <span m='1370870'>number</span> <span
  m='1371230'>of</span> <span m='1371350'>them.</span> <span
  m='1371530'>That</span> <span m='1371710'>is,</span> <span
  m='1372070'>I</span> <span m='1372250'>only</span> <span
  m='1372490'>use</span> <span m='1372850'>them</span> <span
  m='1373720'>in</span> <span m='1373840'>the</span> <span
  m='1373930'>range</span> <span m='1374410'>k equals</span> <span
  m='1374950'>0</span> <span m='1375370'>to</span> <span
  m='1375520'>capital</span> <span m='1375970'>N</span> <span
  m='1376120'>minus</span> <span m='1376480'>1.</span> <span
  m='1377620'>And</span> <span m='1377740'>how</span> <span m='1378040'>I</span>
  <span m='1378160'>choose</span> <span m='1378520'>to</span> <span
  m='1378700'>interpret</span> <span m='1380230'>capital</span> <span
  m='1380680'>X</span> <span m='1380890'>tilde</span> <span
  m='1381190'>of</span> <span m='1381370'>k</span> <span
  m='1382390'>outside</span> <span m='1382930'>the</span> <span
  m='1383050'>range</span> <span m='1383320'>0</span> <span
  m='1383680'>to</span> <span m='1383800'>capital</span> <span
  m='1384280'>N</span> <span m='1384400'>minus</span> <span m='1384790'>1</span>
  <span m='1385720'>is</span> <span m='1385840'>going</span> <span
  m='1385990'>to</span> <span m='1386050'>have</span> <span
  m='1386350'>absolutely</span> <span m='1387010'>no</span> <span
  m='1387310'>effect</span> <span m='1388270'>on</span> <span
  m='1388420'>the</span> <span m='1388540'>evaluation</span> <span
  m='1389290'>of</span> <span m='1389350'>this</span> <span
  m='1389500'>summation.</span> </p><p><span m='1391850'>Well,</span> <span
  m='1392180'>it</span> <span m='1392300'>turns</span> <span
  m='1392630'>out</span> <span m='1392810'>to</span> <span m='1392930'>be</span>
  <span m='1393080'>convenient</span> <span m='1394400'>to</span> <span
  m='1394760'>interpret</span> <span m='1395970'>the</span> <span
  m='1396140'>Fourier</span> <span m='1396560'>series</span> <span
  m='1396950'>coefficients</span> <span m='1398330'>as</span> <span
  m='1398480'>being</span> <span m='1398750'>periodic</span> <span
  m='1399920'>in</span> <span m='1400070'>k.</span> <span
  m='1401690'>Well,</span> <span m='1401930'>in</span> <span
  m='1402050'>fact,</span> <span m='1402560'>the</span> <span
  m='1402650'>relationship</span> <span m='1403790'>as</span> <span
  m='1403940'>I've</span> <span m='1404090'>written</span> <span
  m='1404360'>it</span> <span m='1404510'>here</span> <span
  m='1405380'>makes</span> <span m='1405650'>it</span> <span
  m='1405770'>evident,</span> <span m='1407000'>in</span> <span
  m='1407090'>this</span> <span m='1407240'>particular</span> <span
  m='1407750'>relationship,</span> <span m='1408920'>that</span> <span
  m='1409070'>the</span> <span m='1409160'>coefficients</span> <span
  m='1409820'>are</span> <span m='1410000'>periodic.</span> <span
  m='1411170'>In</span> <span m='1411260'>other</span> <span
  m='1411470'>words,</span> <span m='1412620'>if</span> <span
  m='1413030'>I</span> <span m='1414050'>substitute</span> <span
  m='1414950'>in</span> <span m='1415670'>for</span> <span m='1415820'>k,</span>
  <span m='1416960'>k</span> <span m='1417410'>plus</span> <span
  m='1417710'>capital</span> <span m='1418260'>N,</span> <span
  m='1419940'>then</span> <span m='1420780'>I'll</span> <span
  m='1420990'>get</span> <span m='1421410'>back</span> <span
  m='1421800'>exactly</span> <span m='1422340'>the</span> <span
  m='1422430'>same</span> <span m='1422700'>relation</span> <span
  m='1423540'>that</span> <span m='1423720'>I</span> <span
  m='1423840'>have</span> <span m='1424140'>here.</span> <span
  m='1425130'>Because</span> <span m='1425520'>of</span> <span
  m='1425610'>the</span> <span m='1425760'>fact</span> <span
  m='1426540'>that</span> <span m='1426690'>e</span> <span m='1426830'>to</span>
  <span m='1426960'>the</span> <span m='1427080'>minus</span> <span
  m='1427440'>j</span> <span m='1427740'>2</span> <span m='1428040'>pi</span>
  <span m='1428640'>over</span> <span m='1428910'>capital</span> <span
  m='1429450'>N</span> <span m='1430530'>times</span> <span
  m='1430830'>little</span> <span m='1431130'>n</span> <span
  m='1431820'>times</span> <span m='1432120'>k</span> <span
  m='1432480'>plus</span> <span m='1433230'>capital</span> <span
  m='1433710'>N</span> <span m='1435130'>is</span> <span
  m='1435310'>equal</span> <span m='1436010'>to</span> <span
  m='1436360'>e</span> <span m='1436600'>the</span> <span
  m='1436690'>minus</span> <span m='1437140'>j</span> <span m='1438020'>2</span>
  <span m='1438460'>pi</span> <span m='1439570'>over</span> <span
  m='1440230'>capital</span> <span m='1440740'>N</span> <span
  m='1441610'>times</span> <span m='1442210'>little</span> <span
  m='1442510'>n</span> <span m='1442990'>times</span> <span
  m='1443290'>k.</span> </p><p><span m='1444490'>So</span> <span
  m='1444640'>that</span> <span m='1444790'>if</span> <span m='1444940'>I</span>
  <span m='1445060'>simply</span> <span m='1445450'>examined--</span> <span
  m='1446430'>I</span> <span m='1446650'>asked</span> <span
  m='1447580'>from</span> <span m='1447760'>this</span> <span
  m='1447940'>relationship--</span> <span m='1449330'>what</span> <span
  m='1449500'>does</span> <span m='1450310'>capital</span> <span
  m='1450730'>X</span> <span m='1450970'>tilde</span> <span
  m='1451350'>of</span> <span m='1451540'>k</span> <span m='1451950'>plus</span>
  <span m='1452315'>capital</span> <span m='1452680'>N come</span> <span
  m='1452890'>out</span> <span m='1453070'>to</span> <span
  m='1453220'>be?</span> <span m='1454000'>If</span> <span m='1454100'>I</span>
  <span m='1454210'>simply</span> <span m='1454540'>substitute</span> <span
  m='1455170'>that</span> <span m='1455470'>in,</span> <span
  m='1456340'>then</span> <span m='1456490'>because</span> <span
  m='1456880'>of</span> <span m='1457000'>the</span> <span
  m='1457090'>fact</span> <span m='1457450'>that</span> <span
  m='1457600'>these</span> <span m='1457870'>two</span> <span
  m='1458050'>complex</span> <span m='1458620'>exponentials</span> <span
  m='1459400'>are</span> <span m='1459490'>the</span> <span
  m='1459610'>same,</span> <span m='1460620'>I'll</span> <span
  m='1460840'>find</span> <span m='1461530'>that</span> <span
  m='1461710'>x--</span> <span m='1462370'>capital</span> <span
  m='1462790'>X</span> <span m='1463000'>tilde</span> <span
  m='1463320'>of</span> <span m='1463510'>k</span> <span m='1464380'>is</span>
  <span m='1464560'>equal</span> <span m='1464920'>to</span> <span
  m='1465700'>capital</span> <span m='1466180'>X</span> <span
  m='1466740'>tilde</span> <span m='1467130'>of</span> <span
  m='1467530'>k</span> <span m='1467770'>plus</span> <span
  m='1468040'>capital</span> <span m='1468295'>N,</span> <span
  m='1468910'>k</span> <span m='1469450'>plus</span> <span m='1469720'>2</span>
  <span m='1469900'>capital</span> <span m='1470350'>N,</span> <span
  m='1470480'>et cetera.</span> <span m='1470920'>That</span> <span
  m='1471100'>is,</span> <span m='1471330'>it's</span> <span
  m='1471550'>a</span> <span m='1471610'>periodic</span> <span
  m='1472180'>sequence,</span> <span m='1474290'>although</span> <span
  m='1474580'>I</span> <span m='1474730'>only</span> <span
  m='1475000'>use</span> <span m='1475540'>one</span> <span
  m='1475780'>period</span> <span m='1476260'>of</span> <span
  m='1476410'>it</span> <span m='1476890'>in</span> <span
  m='1477040'>reconstructing</span> <span m='1478300'>the</span> <span
  m='1478390'>periodic</span> <span m='1478960'>sequence</span> <span
  m='1479430'>x</span> <span m='1479650'>tilde</span> <span m='1480040'>of
  n.</span> </p><p><span m='1482130'>I</span> <span m='1482250'>choose</span>
  <span m='1482580'>to</span> <span m='1482700'>do</span> <span
  m='1482910'>that</span> <span m='1483510'>mainly</span> <span
  m='1484260'>because</span> <span m='1484650'>of</span> <span
  m='1484740'>duality.</span> <span m='1485880'>That</span> <span
  m='1486060'>is,</span> <span m='1486600'>mainly</span> <span
  m='1487110'>because</span> <span m='1488610'>it</span> <span
  m='1488790'>is</span> <span m='1488970'>convenient</span> <span
  m='1489540'>to</span> <span m='1489690'>think</span> <span
  m='1490080'>of</span> <span m='1490710'>these</span> <span
  m='1491100'>as</span> <span m='1491280'>a</span> <span
  m='1491340'>periodic</span> <span m='1491970'>sequence</span> <span
  m='1493170'>so</span> <span m='1493440'>that</span> <span m='1494280'>I</span>
  <span m='1494400'>have</span> <span m='1494820'>one</span> <span
  m='1495060'>periodic</span> <span m='1495630'>sequence</span> <span
  m='1496560'>representing</span> <span m='1497490'>another</span> <span
  m='1497850'>periodic</span> <span m='1498450'>sequence,</span> <span
  m='1499380'>this</span> <span m='1499560'>being</span> <span
  m='1499830'>a</span> <span m='1499890'>periodic</span> <span
  m='1500430'>sequence</span> <span m='1501810'>in</span> <span
  m='1501970'>k</span> <span m='1503460'>with</span> <span m='1503640'>a</span>
  <span m='1503700'>period</span> <span m='1506560'>of</span> <span
  m='1507310'>capital</span> <span m='1507820'>N,</span> <span
  m='1508990'>and</span> <span m='1509230'>this</span> <span
  m='1509560'>being</span> <span m='1510100'>a</span> <span
  m='1510160'>periodic</span> <span m='1510790'>sequence</span> <span
  m='1512080'>in</span> <span m='1512290'>n</span> <span m='1513100'>with</span>
  <span m='1513250'>a</span> <span m='1513310'>period</span> <span
  m='1514090'>also</span> <span m='1514660'>of</span> <span
  m='1514810'>capital</span> <span m='1515120'>N.</span> <span
  m='1516340'>So</span> <span m='1517180'>now</span> <span
  m='1517390'>with</span> <span m='1517570'>a</span> <span
  m='1517660'>discrete</span> <span m='1518080'>Fourier</span> <span
  m='1518470'>series,</span> <span m='1519040'>there's</span> <span
  m='1519250'>a</span> <span m='1519340'>duality</span> <span
  m='1520450'>in</span> <span m='1521260'>the,</span> <span
  m='1521920'>what</span> <span m='1522040'>we</span> <span
  m='1522160'>could</span> <span m='1522310'>call</span> <span
  m='1522550'>the</span> <span m='1522670'>time</span> <span
  m='1522970'>domain</span> <span m='1523450'>and</span> <span
  m='1523540'>the</span> <span m='1523630'>frequency</span> <span
  m='1524170'>domain.</span> </p><p><span m='1525280'>And</span> <span
  m='1525370'>the</span> <span m='1525460'>duality</span> <span
  m='1526090'>is</span> <span m='1526210'>there</span> <span
  m='1526450'>in</span> <span m='1526570'>part</span> <span
  m='1526900'>because</span> <span m='1527260'>we've</span> <span
  m='1527410'>chosen</span> <span m='1528340'>to</span> <span
  m='1528460'>represent,</span> <span m='1529270'>or</span> <span
  m='1529450'>think</span> <span m='1529780'>of</span> <span
  m='1530050'>the</span> <span m='1530170'>Fourier</span> <span
  m='1530460'>series</span> <span m='1530920'>coefficients</span> <span
  m='1532240'>as</span> <span m='1532900'>periodic,</span> <span
  m='1533650'>as</span> <span m='1533830'>a</span> <span
  m='1533890'>periodic</span> <span m='1534460'>sequence,</span> <span
  m='1535550'>although</span> <span m='1535810'>we</span> <span
  m='1536020'>only</span> <span m='1536350'>use</span> <span
  m='1536620'>a</span> <span m='1536680'>finite</span> <span
  m='1537130'>number</span> <span m='1537460'>of</span> <span
  m='1537580'>those</span> <span m='1537850'>values</span> <span
  m='1538930'>in</span> <span m='1539740'>actually</span> <span
  m='1540430'>explicitly</span> <span m='1542050'>evaluating</span> <span
  m='1543080'>the</span> <span m='1543190'>Fourier</span> <span
  m='1543640'>series</span> <span m='1544210'>for</span> <span
  m='1544390'>x</span> <span m='1544600'>tilde</span> <span m='1544960'>of
  n.</span> <span m='1546800'>Well,</span> <span m='1548110'>this</span> <span
  m='1548330'>then</span> <span m='1548540'>is</span> <span
  m='1548660'>the</span> <span m='1548770'>Fourier</span> <span
  m='1549230'>series.</span> <span m='1550040'>Let</span> <span
  m='1550250'>me</span> <span m='1550910'>finally</span> <span
  m='1551300'>rewrite</span> <span m='1551780'>it</span> <span
  m='1551930'>one</span> <span m='1552170'>other</span> <span
  m='1552410'>way,</span> <span m='1553400'>which</span> <span
  m='1554090'>just</span> <span m='1554600'>introduces</span> <span
  m='1555200'>some</span> <span m='1555410'>notation</span> <span
  m='1556280'>that's</span> <span m='1556490'>convenient.</span> </p><p><span
  m='1558050'>Let</span> <span m='1558230'>me</span> <span
  m='1558380'>define</span> <span m='1559670'>w</span> <span
  m='1560330'>sub</span> <span m='1560600'>capital</span> <span
  m='1561110'>N</span> <span m='1562420'>as</span> <span m='1562880'>e</span>
  <span m='1563130'>to</span> <span m='1563240'>the</span> <span
  m='1563360'>minus</span> <span m='1563780'>j</span> <span m='1564215'>2</span>
  <span m='1564650'>pi</span> <span m='1565250'>over</span> <span
  m='1565520'>capital</span> <span m='1566000'>N.</span> <span
  m='1567290'>In</span> <span m='1567380'>that</span> <span
  m='1567560'>case,</span> <span m='1568350'>then</span> <span
  m='1568610'>just</span> <span m='1568820'>simply</span> <span
  m='1569210'>rewriting</span> <span m='1570650'>the</span> <span
  m='1570890'>Fourier</span> <span m='1571370'>series,</span> <span
  m='1572510'>we</span> <span m='1572660'>have</span> <span m='1572960'>x</span>
  <span m='1573260'>tilde</span> <span m='1573560'>of</span> <span
  m='1573770'>n</span> <span m='1574310'>is</span> <span m='1574490'>1</span>
  <span m='1574700'>over</span> <span m='1574940'>capital</span> <span
  m='1575480'>N,</span> <span m='1576440'>the</span> <span
  m='1576530'>sum</span> <span m='1577580'>of</span> <span
  m='1577970'>capital</span> <span m='1578390'>X</span> <span
  m='1578600'>tilde</span> <span m='1578900'>of</span> <span
  m='1579150'>k,</span> <span m='1579700'>w</span> <span m='1580150'>sub</span>
  <span m='1580760'>capital</span> <span m='1581240'>N</span> <span
  m='1581510'>to</span> <span m='1581780'>the</span> <span
  m='1581900'>minus</span> <span m='1582260'>nk.</span> <span
  m='1584180'>And</span> <span m='1584830'>the</span> <span
  m='1585010'>Fourier</span> <span m='1585410'>series</span> <span
  m='1585860'>coefficients</span> <span m='1587240'>expressed</span> <span
  m='1587840'>in</span> <span m='1588020'>terms</span> <span
  m='1588530'>of</span> <span m='1588680'>capital</span> <span
  m='1589130'>W</span> <span m='1589530'>sub n</span> <span
  m='1591240'>is</span> <span m='1591530'>the</span> <span
  m='1591680'>sum</span> <span m='1592580'>of</span> <span m='1592790'>x</span>
  <span m='1593060'>tilde</span> <span m='1593510'>of</span> <span
  m='1593720'>n,</span> <span m='1594560'>w</span> <span m='1594930'>sub</span>
  <span m='1595160'>capital</span> <span m='1595415'>N</span> <span
  m='1596060'>to</span> <span m='1596330'>the</span> <span
  m='1596480'>nk.</span> </p><p><span m='1599110'>Well,</span> <span
  m='1600220'>the</span> <span m='1600490'>discrete</span> <span
  m='1600910'>Fourier</span> <span m='1601330'>series</span> <span
  m='1602740'>has</span> <span m='1603700'>properties,</span> <span
  m='1604930'>just</span> <span m='1605290'>as</span> <span
  m='1605860'>the</span> <span m='1605980'>Fourier</span> <span
  m='1606370'>transform</span> <span m='1607300'>and</span> <span
  m='1607420'>the</span> <span m='1607510'>Z-transform</span> <span
  m='1608410'>has</span> <span m='1608590'>had</span> <span m='1608890'>a</span>
  <span m='1608950'>number</span> <span m='1609280'>of</span> <span
  m='1609370'>properties.</span> <span m='1610730'>And</span> <span
  m='1611230'>again,</span> <span m='1613480'>as</span> <span
  m='1613660'>we've</span> <span m='1613780'>done</span> <span
  m='1613960'>with</span> <span m='1614110'>the</span> <span
  m='1614230'>other</span> <span m='1614410'>transforms,</span> <span
  m='1615850'>I</span> <span m='1615910'>won't</span> <span
  m='1616780'>spend</span> <span m='1617080'>a</span> <span
  m='1617140'>lot</span> <span m='1617380'>of</span> <span
  m='1617500'>time</span> <span m='1617950'>on</span> <span
  m='1618070'>the</span> <span m='1618160'>details</span> <span
  m='1618940'>of</span> <span m='1619960'>either</span> <span
  m='1620440'>enumerating</span> <span m='1621040'>the</span> <span
  m='1621130'>properties</span> <span m='1621790'>or</span> <span
  m='1621880'>proving</span> <span m='1622360'>them.</span> <span
  m='1623440'>But</span> <span m='1623860'>let</span> <span
  m='1624070'>me</span> <span m='1624190'>just</span> <span
  m='1624640'>illustrate</span> <span m='1625210'>one</span> <span
  m='1625390'>or</span> <span m='1625480'>two</span> <span m='1626320'>to</span>
  <span m='1626440'>give</span> <span m='1626680'>you</span> <span
  m='1626860'>some</span> <span m='1627160'>idea</span> <span
  m='1627730'>as</span> <span m='1628300'>to</span> <span
  m='1628420'>what</span> <span m='1628600'>these</span> <span
  m='1628780'>properties</span> <span m='1629380'>involve.</span> </p><p><span
  m='1631880'>Well,</span> <span m='1632390'>first</span> <span
  m='1632750'>of</span> <span m='1632870'>all,</span> <span
  m='1633390'>as</span> <span m='1633470'>we've</span> <span
  m='1633620'>talked</span> <span m='1633950'>about</span> <span
  m='1634580'>in</span> <span m='1634760'>the</span> <span
  m='1636200'>Fourier</span> <span m='1636560'>transform</span> <span
  m='1637170'>and</span> <span m='1637280'>Z-transform</span> <span
  m='1638060'>cases,</span> <span m='1639230'>there</span> <span
  m='1639530'>is</span> <span m='1639710'>a</span> <span
  m='1639770'>shifting</span> <span m='1640250'>property</span> <span
  m='1642140'>that</span> <span m='1642770'>tells</span> <span
  m='1643160'>us</span> <span m='1644060'>how</span> <span
  m='1644620'>the</span> <span m='1644810'>Fourier</span> <span
  m='1645230'>series</span> <span m='1645620'>coefficients</span> <span
  m='1646550'>of</span> <span m='1646700'>a</span> <span
  m='1646760'>periodic</span> <span m='1647330'>sequence</span> <span
  m='1648440'>are</span> <span m='1648560'>related</span> <span
  m='1649250'>to</span> <span m='1649580'>the</span> <span
  m='1649700'>Fourier</span> <span m='1650050'>series</span> <span
  m='1650420'>coefficients</span> <span m='1651260'>of</span> <span
  m='1651380'>that</span> <span m='1651560'>sequence</span> <span
  m='1652040'>shifted.</span> <span m='1653120'>And</span> <span
  m='1653270'>in</span> <span m='1653330'>particular,</span> <span
  m='1654290'>it</span> <span m='1654380'>turns</span> <span
  m='1654800'>out</span> <span m='1655640'>that</span> <span
  m='1656780'>if</span> <span m='1657620'>capital</span> <span
  m='1658040'>X</span> <span m='1658280'>of</span> <span m='1658400'>k,</span>
  <span m='1658850'>capital</span> <span m='1659240'>X</span> <span
  m='1659390'>tilde</span> <span m='1659660'>of</span> <span
  m='1659870'>k</span> <span m='1660710'>are</span> <span m='1660800'>the</span>
  <span m='1660920'>Fourier</span> <span m='1661310'>series</span> <span
  m='1661730'>coefficients</span> <span m='1662550'>for</span> <span
  m='1663420'>little</span> <span m='1663830'>x tilde</span> <span
  m='1664210'>of</span> <span m='1664370'>n,</span> <span
  m='1665420'>then</span> <span m='1665840'>the</span> <span
  m='1665930'>Fourier</span> <span m='1666320'>series</span> <span
  m='1666800'>coefficients</span> <span m='1667970'>for</span> <span
  m='1668240'>that</span> <span m='1668450'>sequence</span> <span
  m='1668930'>shifted,</span> <span m='1669890'>that</span> <span
  m='1670040'>is,</span> <span m='1670190'>little</span> <span
  m='1670430'>x</span> <span m='1670640'>tilde</span> <span
  m='1671030'>of</span> <span m='1671240'>n</span> <span m='1671420'>plus</span>
  <span m='1671780'>m,</span> <span m='1673590'>corresponds</span> <span
  m='1674520'>to</span> <span m='1674670'>multiplying</span> <span
  m='1675420'>the</span> <span m='1675510'>Fourier</span> <span
  m='1675870'>series</span> <span m='1676260'>coefficients</span> <span
  m='1677670'>by</span> <span m='1679900'>w</span> <span m='1680460'>sub</span>
  <span m='1680880'>capital</span> <span m='1681135'>N</span> <span
  m='1681940'>to</span> <span m='1682090'>the</span> <span
  m='1682180'>minus</span> <span m='1682600'>km.</span> </p><p><span
  m='1684940'>Shifting</span> <span m='1685450'>the</span> <span
  m='1685570'>sequence</span> <span m='1687160'>involves</span> <span
  m='1688390'>multiplying</span> <span m='1689550'>the</span> <span
  m='1689650'>Fourier</span> <span m='1690010'>series</span> <span
  m='1690430'>coefficients</span> <span m='1691720'>by</span> <span
  m='1692170'>a</span> <span m='1692260'>complex</span> <span
  m='1692860'>exponential,</span> <span m='1694070'>which</span> <span
  m='1694150'>is</span> <span m='1694240'>what</span> <span
  m='1694450'>this</span> <span m='1694690'>is.</span> <span
  m='1696170'>And</span> <span m='1696970'>that</span> <span
  m='1697270'>is</span> <span m='1697390'>similar</span> <span
  m='1698530'>to</span> <span m='1698830'>what</span> <span
  m='1699070'>we've</span> <span m='1699250'>seen</span> <span
  m='1699820'>with</span> <span m='1700450'>the</span> <span
  m='1700540'>Fourier</span> <span m='1700930'>transform,</span> <span
  m='1701710'>shifting</span> <span m='1702130'>a</span> <span
  m='1702190'>sequence,</span> <span m='1703150'>multiply</span> <span
  m='1704060'>the</span> <span m='1704200'>Fourier</span> <span
  m='1704590'>transform</span> <span m='1705490'>by</span> <span
  m='1706180'>a</span> <span m='1706240'>complex</span> <span
  m='1706810'>exponential.</span> <span m='1708060'>And</span> <span
  m='1708410'>the</span> <span m='1708490'>Z-transform,</span> <span
  m='1709360'>we</span> <span m='1709480'>had</span> <span
  m='1709660'>exactly</span> <span m='1710080'>the</span> <span
  m='1710170'>same</span> <span m='1710440'>situation.</span> <span
  m='1712520'>We</span> <span m='1712700'>have</span> <span m='1713120'>a</span>
  <span m='1713240'>dual</span> <span m='1713840'>relationship,</span> <span
  m='1715700'>which</span> <span m='1716480'>expresses</span> <span
  m='1717500'>the</span> <span m='1717590'>result</span> <span
  m='1718190'>of</span> <span m='1718340'>shifting</span> <span
  m='1719420'>the</span> <span m='1719510'>Fourier</span> <span
  m='1719950'>series</span> <span m='1720440'>coefficients.</span> <span
  m='1722130'>If</span> <span m='1722180'>we</span> <span
  m='1722300'>shift</span> <span m='1722930'>the</span> <span
  m='1723050'>Fourier</span> <span m='1723410'>series</span> <span
  m='1723860'>coefficients,</span> <span m='1725120'>the</span> <span
  m='1725210'>result</span> <span m='1725780'>is</span> <span
  m='1725930'>multiplication</span> <span m='1727010'>by</span> <span
  m='1727430'>a</span> <span m='1727490'>complex</span> <span
  m='1728060'>exponential</span> <span m='1729320'>of</span> <span
  m='1729800'>the</span> <span m='1729920'>original</span> <span
  m='1730310'>sequence,</span> <span m='1731120'>little</span> <span
  m='1731390'>x</span> <span m='1731810'>tilde</span> <span
  m='1731980'>of</span> <span m='1732440'>n.</span> </p><p><span
  m='1734310'>In</span> <span m='1734400'>fact,</span> <span
  m='1735190'>one</span> <span m='1735300'>of</span> <span
  m='1735420'>the</span> <span m='1735510'>things</span> <span
  m='1735840'>that's</span> <span m='1736020'>true</span> <span
  m='1736290'>with</span> <span m='1736420'>the</span> <span
  m='1736470'>discrete</span> <span m='1736890'>Fourier</span> <span
  m='1737340'>series</span> <span m='1738450'>that</span> <span
  m='1738600'>hasn't</span> <span m='1738960'>been</span> <span
  m='1739170'>true</span> <span m='1739650'>with the</span> <span
  m='1739980'>Fourier</span> <span m='1740400'>transform</span> <span
  m='1741000'>or</span> <span m='1741150'>the</span> <span
  m='1741270'>Z-transform</span> <span m='1742910'>is</span> <span
  m='1743120'>there</span> <span m='1743260'>is</span> <span
  m='1743480'>a</span> <span m='1743550'>strong</span> <span
  m='1744030'>duality</span> <span m='1745110'>between</span> <span
  m='1746310'>the</span> <span m='1747660'>time</span> <span
  m='1747990'>domain,</span> <span m='1749400'>the</span> <span
  m='1749580'>discrete</span> <span m='1749940'>time</span> <span
  m='1750240'>domain,</span> <span m='1751320'>and</span> <span
  m='1751980'>the</span> <span m='1752100'>Fourier</span> <span
  m='1752610'>or</span> <span m='1752730'>frequency</span> <span
  m='1753300'>domain.</span> <span m='1755370'>In</span> <span
  m='1755490'>particular,</span> <span m='1757230'>we</span> <span
  m='1757380'>begin</span> <span m='1757980'>with</span> <span
  m='1758550'>a</span> <span m='1758760'>discrete</span> <span
  m='1759660'>periodic</span> <span m='1760260'>sequence,</span> <span
  m='1761690'>and</span> <span m='1761790'>we</span> <span
  m='1761970'>end</span> <span m='1762180'>up</span> <span m='1762360'>in</span>
  <span m='1762420'>the</span> <span m='1762510'>Fourier</span> <span
  m='1762990'>domain</span> <span m='1763680'>with,</span> <span
  m='1764040'>again,</span> <span m='1764540'>a</span> <span
  m='1764600'>discrete</span> <span m='1765300'>periodic</span> <span
  m='1765870'>sequence.</span> </p><p><span m='1767310'>In</span> <span
  m='1767430'>fact,</span> <span m='1767700'>something</span> <span
  m='1768060'>to</span> <span m='1768180'>think</span> <span
  m='1768450'>about</span> <span m='1769590'>is</span> <span
  m='1771090'>the</span> <span m='1771180'>fact</span> <span
  m='1771540'>that</span> <span m='1771750'>the</span> <span
  m='1772380'>Fourier</span> <span m='1772830'>series</span> <span
  m='1773220'>coefficients</span> <span m='1774180'>we've</span> <span
  m='1774410'>said,</span> <span m='1774670'>or</span> <span
  m='1774930'>we've</span> <span m='1775290'>chosen</span> <span
  m='1775680'>to</span> <span m='1775830'>interpret</span> <span
  m='1776280'>them,</span> <span m='1777000'>as</span> <span
  m='1777240'>being</span> <span m='1777540'>periodic.</span> <span
  m='1778920'>That</span> <span m='1779100'>implies</span> <span
  m='1779820'>that</span> <span m='1780000'>they</span> <span
  m='1780510'>themselves</span> <span m='1781350'>have</span> <span
  m='1781560'>a</span> <span m='1781620'>Fourier</span> <span
  m='1782040'>series</span> <span m='1782430'>representation.</span> <span
  m='1783850'>And</span> <span m='1783960'>something</span> <span
  m='1784350'>to</span> <span m='1784470'>think</span> <span
  m='1784740'>about</span> <span m='1785160'>is,</span> <span
  m='1785850'>what</span> <span m='1786120'>are</span> <span
  m='1786240'>the</span> <span m='1786370'>Fourier</span> <span
  m='1786800'>series</span> <span m='1787230'>coefficients</span> <span
  m='1788730'>of</span> <span m='1788880'>that</span> <span
  m='1789150'>periodic</span> <span m='1789760'>sequence?</span> </p><p><span
  m='1794340'>All</span> <span m='1794430'>right.</span> <span
  m='1794910'>So</span> <span m='1796140'>one</span> <span
  m='1796350'>important</span> <span m='1796770'>point</span> <span
  m='1797100'>then</span> <span m='1797310'>is</span> <span
  m='1797430'>that</span> <span m='1797640'>we</span> <span
  m='1797820'>have</span> <span m='1798000'>this</span> <span
  m='1798180'>duality</span> <span m='1799110'>between</span> <span
  m='1799500'>the</span> <span m='1799590'>two</span> <span
  m='1799770'>domains.</span> <span m='1800820'>And</span> <span
  m='1801750'>essentially,</span> <span m='1802320'>any</span> <span
  m='1802530'>property</span> <span m='1803130'>that</span> <span
  m='1803280'>we</span> <span m='1803430'>have</span> <span
  m='1803760'>in</span> <span m='1803850'>the</span> <span
  m='1803940'>time</span> <span m='1804240'>domain</span> <span
  m='1805110'>will</span> <span m='1805260'>find</span> <span
  m='1805630'>the</span> <span m='1805710'>dual</span> <span
  m='1805980'>property</span> <span m='1806670'>in</span> <span
  m='1806790'>the</span> <span m='1806880'>frequency</span> <span
  m='1807420'>domain</span> <span m='1808170'>for</span> <span
  m='1808290'>the</span> <span m='1808410'>discrete</span> <span
  m='1808830'>Fourier</span> <span m='1809250'>series.</span> <span
  m='1810150'>And</span> <span m='1810570'>that</span> <span
  m='1810750'>will</span> <span m='1810900'>the</span> <span
  m='1811440'>hold</span> <span m='1811710'>true</span> <span
  m='1812490'>when,</span> <span m='1812910'>later</span> <span
  m='1813300'>on</span> <span m='1813900'>in</span> <span m='1813990'>the</span>
  <span m='1814080'>next</span> <span m='1814320'>lecture,</span> <span
  m='1814740'>we</span> <span m='1814890'>talk</span> <span
  m='1815220'>about</span> <span m='1815460'>the</span> <span
  m='1815550'>discrete</span> <span m='1815940'>Fourier</span> <span
  m='1816340'>transform.</span> </p><p><span m='1818470'>Another</span> <span
  m='1819640'>useful</span> <span m='1820060'>property,</span> <span
  m='1821240'>which</span> <span m='1821320'>we've</span> <span
  m='1821530'>also</span> <span m='1821890'>talked</span> <span
  m='1822280'>about</span> <span m='1822700'>for the</span> <span
  m='1823000'>Fourier</span> <span m='1823420'>transform,</span> <span
  m='1826780'>are</span> <span m='1826930'>the</span> <span
  m='1827050'>set</span> <span m='1827230'>of</span> <span
  m='1827320'>symmetry</span> <span m='1827830'>properties.</span> <span
  m='1829540'>And</span> <span m='1829990'>in</span> <span
  m='1830140'>particular,</span> <span m='1831110'>if</span> <span
  m='1831610'>we</span> <span m='1831910'>consider</span> <span
  m='1832840'>x</span> <span m='1833080'>tilde</span> <span m='1833530'>of
  n</span> <span m='1834160'>to</span> <span m='1834280'>be</span> <span
  m='1834660'>a</span> <span m='1834720'>real</span> <span m='1835210'>a</span>
  <span m='1835660'>periodic</span> <span m='1836230'>sequence,</span> <span
  m='1838260'>then</span> <span m='1838770'>there</span> <span
  m='1839010'>are</span> <span m='1839160'>symmetry</span> <span
  m='1839700'>relationships</span> <span m='1840960'>between</span> <span
  m='1841620'>the</span> <span m='1841770'>real</span> <span
  m='1842040'>part</span> <span m='1843960'>of</span> <span
  m='1844140'>the</span> <span m='1844350'>Fourier</span> <span
  m='1844770'>series,</span> <span m='1845430'>and</span> <span
  m='1846120'>symmetry</span> <span m='1846570'>relations</span> <span
  m='1847110'>for</span> <span m='1847200'>the</span> <span
  m='1847290'>imaginary</span> <span m='1847860'>part</span> <span
  m='1848310'>of</span> <span m='1848430'>the</span> <span
  m='1848550'>Fourier</span> <span m='1848940'>series.</span> </p><p><span
  m='1850080'>In</span> <span m='1850170'>particular,</span> <span
  m='1851110'>we</span> <span m='1851190'>can</span> <span
  m='1851370'>think</span> <span m='1851730'>of</span> <span
  m='1852480'>expressing</span> <span m='1853380'>the</span> <span
  m='1853550'>Fourier</span> <span m='1853910'>series</span> <span
  m='1854280'>coefficients</span> <span m='1855840'>in</span> <span
  m='1855960'>terms</span> <span m='1856470'>of</span> <span
  m='1857100'>their</span> <span m='1857250'>real</span> <span
  m='1857580'>part</span> <span m='1859090'>plus</span> <span
  m='1859510'>j</span> <span m='1859840'>times</span> <span
  m='1860640'>the</span> <span m='1860730'>imaginary</span> <span
  m='1861420'>part.</span> <span m='1863010'>And</span> <span
  m='1864120'>the</span> <span m='1864330'>symmetry</span> <span
  m='1864840'>relationships</span> <span m='1865740'>that</span> <span
  m='1865890'>result</span> <span m='1866940'>are</span> <span
  m='1867240'>that</span> <span m='1867690'>if</span> <span
  m='1868290'>the</span> <span m='1868410'>periodic</span> <span
  m='1868920'>sequence</span> <span m='1869370'>is</span> <span
  m='1869520'>real,</span> <span m='1870660'>then</span> <span
  m='1871290'>the</span> <span m='1871440'>real</span> <span
  m='1871920'>part</span> <span m='1872280'>of</span> <span
  m='1872370'>the</span> <span m='1872460'>Fourier</span> <span
  m='1872850'>series</span> <span m='1873270'>coefficients</span> <span
  m='1874530'>are</span> <span m='1874950'>even,</span> <span
  m='1876510'>x</span> <span m='1876850'>sub</span> <span m='1876990'>R
  of</span> <span m='1877250'>k</span> <span m='1877860'>is</span> <span
  m='1878070'>equal</span> <span m='1878430'>to</span> <span
  m='1878850'>x</span> <span m='1879145'>sub</span> <span m='1879440'>R
  of</span> <span m='1879840'>minus</span> <span m='1880300'>k.</span> <span
  m='1881490'>And</span> <span m='1883260'>that's</span> <span
  m='1883560'>what</span> <span m='1883710'>we</span> <span
  m='1883890'>refer</span> <span m='1884340'>to</span> <span
  m='1884790'>as</span> <span m='1885390'>the</span> <span
  m='1885510'>property</span> <span m='1886140'>of,</span> <span
  m='1886790'>in</span> <span m='1886890'>the</span> <span
  m='1886980'>case</span> <span m='1887250'>of</span> <span
  m='1887310'>the</span> <span m='1887400'>Fourier</span> <span
  m='1887700'>transform,</span> <span m='1888270'>the</span> <span
  m='1888330'>Fourier</span> <span m='1888690'>transform</span> <span
  m='1889290'>being</span> <span m='1889560'>even.</span> </p><p><span
  m='1891300'>We</span> <span m='1891420'>can</span> <span
  m='1891570'>also</span> <span m='1892050'>write</span> <span
  m='1892350'>this</span> <span m='1892650'>in</span> <span
  m='1892770'>another</span> <span m='1893130'>way</span> <span
  m='1894150'>that</span> <span m='1894270'>will</span> <span
  m='1894450'>become</span> <span m='1894810'>important</span> <span
  m='1895320'>when</span> <span m='1895500'>we</span> <span
  m='1895590'>talk</span> <span m='1895920'>about</span> <span
  m='1896190'>the</span> <span m='1896280'>discrete</span> <span
  m='1896670'>Fourier</span> <span m='1897090'>transform.</span> <span
  m='1898960'>In</span> <span m='1898980'>particular,</span> <span
  m='1899820'>since</span> <span m='1900270'>this</span> <span
  m='1900480'>is</span> <span m='1900630'>a</span> <span
  m='1900690'>periodic</span> <span m='1901320'>sequence,</span> <span
  m='1902490'>since</span> <span m='1902830'>s</span> <span
  m='1903176'>sub</span> <span m='1903522'>R</span> <span
  m='1903870'>of--</span> <span m='1904440'>since</span> <span
  m='1904680'>x</span> <span m='1904920'>of</span> <span m='1905220'>k</span>
  <span m='1905770'>is</span> <span m='1905910'>periodic,</span> <span
  m='1906570'>obviously</span> <span m='1907110'>it's</span> <span
  m='1907200'>real</span> <span m='1907470'>part</span> <span
  m='1907890'>is</span> <span m='1908040'>also</span> <span
  m='1908370'>periodic--</span> <span m='1909370'>we</span> <span
  m='1909870'>can</span> <span m='1910350'>replace</span> <span
  m='1910920'>k</span> <span m='1912000'>by</span> <span m='1912420'>k</span>
  <span m='1912720'>plus</span> <span m='1913020'>capital</span> <span
  m='1913530'>N,</span> <span m='1914040'>or</span> <span m='1914310'>k</span>
  <span m='1914760'>minus</span> <span m='1915150'>capital</span> <span
  m='1915410'>N.</span> <span m='1916650'>And</span> <span m='1917160'>we</span>
  <span m='1917370'>can</span> <span m='1917550'>rewrite</span> <span
  m='1918030'>this</span> <span m='1918630'>as</span> <span m='1920040'>a</span>
  <span m='1920100'>statement</span> <span m='1920760'>that</span> <span
  m='1920940'>says</span> <span m='1921690'>that</span> <span
  m='1922110'>x</span> <span m='1922410'>sub</span> <span m='1922530'>R</span>
  <span m='1922760'>tilde</span> <span m='1923100'>of</span> <span
  m='1923280'>k</span> <span m='1924750'>is</span> <span
  m='1924930'>equal</span> <span m='1925320'>to</span> <span
  m='1925710'>x</span> <span m='1926010'>sub</span> <span m='1926130'>R</span>
  <span m='1926430'>tilde</span> <span m='1927570'>of</span> <span
  m='1928230'>capital</span> <span m='1928770'>N</span> <span
  m='1930060'>minus</span> <span m='1930480'>k.</span> </p><p><span
  m='1932390'>It</span> <span m='1932480'>shouldn't</span> <span
  m='1932750'>be</span> <span m='1932900'>particularly</span> <span
  m='1933530'>evident</span> <span m='1934190'>why</span> <span
  m='1934430'>we</span> <span m='1934580'>want</span> <span
  m='1934760'>to</span> <span m='1934850'>do</span> <span
  m='1935030'>that</span> <span m='1936460'>here,</span> <span
  m='1937150'>although</span> <span m='1937870'>it</span> <span
  m='1938680'>becomes</span> <span m='1939100'>important</span> <span
  m='1940060'>when</span> <span m='1940240'>we</span> <span
  m='1940390'>apply</span> <span m='1940750'>some</span> <span
  m='1941020'>of</span> <span m='1941110'>these</span> <span
  m='1941290'>notions</span> <span m='1942340'>to</span> <span
  m='1942610'>the</span> <span m='1942730'>representation</span> <span
  m='1943570'>of</span> <span m='1943660'>finite</span> <span
  m='1944050'>length</span> <span m='1944260'>sequence</span> <span
  m='1944890'>and</span> <span m='1945280'>sequences</span> <span
  m='1945910'>in</span> <span m='1946060'>the</span> <span
  m='1946150'>discrete</span> <span m='1946540'>Fourier</span> <span
  m='1946930'>transform.</span> <span m='1948880'>Likewise,</span> <span
  m='1949480'>for</span> <span m='1949570'>the</span> <span
  m='1949690'>imaginary</span> <span m='1950680'>part</span> <span
  m='1950920'>of</span> <span m='1951040'>the</span> <span
  m='1951120'>Fourier</span> <span m='1951480'>series</span> <span
  m='1951910'>coefficients,</span> <span m='1953880'>we</span> <span
  m='1954450'>end</span> <span m='1954720'>up</span> <span
  m='1954870'>with</span> <span m='1954990'>a</span> <span
  m='1955050'>symmetry</span> <span m='1955500'>property</span> <span
  m='1956040'>that</span> <span m='1956190'>says</span> <span
  m='1956940'>that</span> <span m='1957900'>the</span> <span
  m='1958020'>imaginary</span> <span m='1958590'>part</span> <span
  m='1958800'>of the</span> <span m='1958860'>Fourier</span> <span
  m='1959060'>series</span> <span m='1959670'>coefficients</span> <span
  m='1960600'>are</span> <span m='1961020'>odd.</span> <span
  m='1964010'>And</span> <span m='1964160'>again,</span> <span
  m='1964940'>as</span> <span m='1965450'>we</span> <span m='1965630'>did</span>
  <span m='1965990'>with</span> <span m='1966230'>the</span> <span
  m='1966500'>real</span> <span m='1966740'>part</span> <span
  m='1967010'>of</span> <span m='1967070'>the</span> <span
  m='1967160'>Fourier</span> <span m='1967520'>series</span> <span
  m='1967940'>coefficients,</span> <span m='1969380'>we</span> <span
  m='1969530'>can</span> <span m='1969710'>rewrite</span> <span
  m='1970190'>this</span> <span m='1971000'>to</span> <span
  m='1971120'>say</span> <span m='1971810'>that</span> <span
  m='1972180'>x</span> <span m='1972525'>sub</span> <span m='1972870'>i</span>
  <span m='1973100'>tilde of</span> <span m='1973310'>k</span> <span
  m='1974240'>is</span> <span m='1974390'>equal</span> <span
  m='1974810'>to</span> <span m='1975260'>minus</span> <span
  m='1976580'>x</span> <span m='1976880'>sub</span> <span m='1976930'>i</span>
  <span m='1978690'>tilde</span> <span m='1978960'>of</span> <span
  m='1980644'>N</span> <span m='1982105'>minus</span> <span
  m='1983080'>k.</span> </p><p><span m='1986800'>Finally,</span> <span
  m='1987970'>we</span> <span m='1988180'>can,</span> <span
  m='1989320'>in</span> <span m='1989440'>a</span> <span
  m='1989500'>similar</span> <span m='1989890'>manner,</span> <span
  m='1990460'>look</span> <span m='1990790'>at</span> <span
  m='1991270'>the</span> <span m='1991390'>magnitude</span> <span
  m='1991960'>of</span> <span m='1992020'>the</span> <span
  m='1992110'>Fourier</span> <span m='1992550'>series</span> <span
  m='1992950'>coefficients</span> <span m='1994270'>and</span> <span
  m='1994780'>the</span> <span m='1994960'>angle</span> <span
  m='1995320'>of</span> <span m='1995410'>the</span> <span
  m='1995500'>Fourier</span> <span m='1995910'>series</span> <span
  m='1996280'>coefficients.</span> <span m='1997630'>And</span> <span
  m='1997930'>just</span> <span m='1998260'>as</span> <span
  m='1998410'>we've</span> <span m='1998560'>seen</span> <span
  m='1999310'>with</span> <span m='1999760'>the</span> <span
  m='1999890'>Fourier</span> <span m='2000330'>transform,</span> <span
  m='2001620'>the</span> <span m='2001710'>result</span> <span
  m='2002130'>that</span> <span m='2002250'>we'll</span> <span
  m='2002430'>find</span> <span m='2003360'>is</span> <span
  m='2003570'>that</span> <span m='2003990'>the</span> <span
  m='2004080'>magnitude</span> <span m='2004710'>of</span> <span
  m='2004830'>the</span> <span m='2004920'>Fourier</span> <span
  m='2005340'>series</span> <span m='2005730'>coefficients</span> <span
  m='2007350'>are</span> <span m='2007980'>even,</span> <span
  m='2008920'>an</span> <span m='2009390'>even</span> <span
  m='2009720'>function</span> <span m='2010170'>of</span> <span
  m='2010280'>k.</span> <span m='2011610'>And</span> <span
  m='2012240'>the</span> <span m='2012390'>angle</span> <span
  m='2012900'>of</span> <span m='2013380'>the</span> <span
  m='2013620'>Fourier</span> <span m='2014010'>series</span> <span
  m='2014430'>coefficients</span> <span m='2016080'>are</span> <span
  m='2016860'>an</span> <span m='2017010'>odd</span> <span
  m='2017730'>function</span> <span m='2018150'>of</span> <span
  m='2018240'>k.</span> <span m='2019880'>So</span> <span m='2020180'>we</span>
  <span m='2020360'>have</span> <span m='2020570'>symmetry</span> <span
  m='2021020'>properties</span> <span m='2021920'>like</span> <span
  m='2022220'>we</span> <span m='2022370'>had</span> <span
  m='2022790'>with</span> <span m='2022940'>the</span> <span
  m='2023160'>Fourier</span> <span m='2023450'>transform.</span> </p><p><span
  m='2024890'>An</span> <span m='2025010'>important</span> <span
  m='2025940'>thing</span> <span m='2026480'>to</span> <span
  m='2027620'>keep</span> <span m='2027920'>track</span> <span
  m='2028340'>of</span> <span m='2028910'>at</span> <span
  m='2029030'>this</span> <span m='2029270'>point,</span> <span
  m='2029570'>because</span> <span m='2029900'>we'll</span> <span
  m='2029990'>want</span> <span m='2030500'>to</span> <span
  m='2031340'>refer</span> <span m='2031700'>back</span> <span
  m='2032030'>to</span> <span m='2032180'>this</span> <span
  m='2032780'>when</span> <span m='2032990'>we</span> <span
  m='2033110'>talk</span> <span m='2033410'>about</span> <span
  m='2033650'>the</span> <span m='2033740'>discrete</span> <span
  m='2034100'>Fourier</span> <span m='2034520'>transform,</span> <span
  m='2035930'>is</span> <span m='2036080'>that</span> <span
  m='2036260'>in</span> <span m='2036380'>talking</span> <span
  m='2036860'>about</span> <span m='2037130'>the</span> <span
  m='2037220'>property</span> <span m='2037790'>of</span> <span
  m='2037940'>even</span> <span m='2038240'>or</span> <span
  m='2038360'>odd,</span> <span m='2039590'>we</span> <span
  m='2039770'>can</span> <span m='2040760'>either</span> <span
  m='2041090'>talk</span> <span m='2041420'>about</span> <span
  m='2041660'>it</span> <span m='2041780'>as</span> <span m='2041900'>we</span>
  <span m='2042050'>do</span> <span m='2042260'>here,</span> <span
  m='2043190'>or</span> <span m='2044480'>in</span> <span
  m='2044630'>terms</span> <span m='2045140'>of</span> <span
  m='2045320'>a</span> <span m='2045380'>shift--</span> <span
  m='2045890'>that</span> <span m='2046100'>is,</span> <span
  m='2046790'>in</span> <span m='2046880'>terms</span> <span
  m='2047210'>of</span> <span m='2047300'>a</span> <span
  m='2047360'>statement</span> <span m='2047650'>that</span> <span
  m='2048239'>x</span> <span m='2048340'>sub</span> <span m='2048440'>bar</span>
  <span m='2048449'>of</span> <span m='2048620'>k</span> <span
  m='2049070'>is</span> <span m='2049489'>x</span> <span m='2049790'>sub</span>
  <span m='2049900'>R of</span> <span m='2050300'>capital</span> <span
  m='2050880'>N</span> <span m='2050929'>minus</span> <span
  m='2051360'>k,</span> <span m='2052320'>which</span> <span
  m='2052429'>essentially</span> <span m='2053030'>relates</span> <span
  m='2053510'>the</span> <span m='2053690'>evenness</span> <span
  m='2055280'>of</span> <span m='2056330'>this</span> <span
  m='2056929'>periodic</span> <span m='2057530'>sequence</span> <span
  m='2058580'>to</span> <span m='2058940'>the</span> <span
  m='2059060'>relationship</span> <span m='2059870'>between</span> <span
  m='2060290'>values</span> <span m='2061370'>within</span> <span
  m='2061699'>one</span> <span m='2061940'>period.</span> </p><p><span
  m='2064770'>Finally,</span> <span m='2065090'>we</span> <span
  m='2065300'>have</span> <span m='2067060'>another</span> <span
  m='2067989'>very</span> <span m='2068260'>important</span> <span
  m='2068710'>property,</span> <span m='2070040'>which</span> <span
  m='2070120'>is</span> <span m='2070239'>the</span> <span
  m='2070330'>convolution</span> <span m='2071080'>property.</span> <span
  m='2072610'>This</span> <span m='2072820'>is</span> <span m='2072909'>a</span>
  <span m='2072969'>property</span> <span m='2073480'>that,</span> <span
  m='2073630'>again,</span> <span m='2073929'>we've</span> <span
  m='2074110'>had</span> <span m='2074290'>for</span> <span
  m='2074409'>the</span> <span m='2074500'>Fourier</span> <span
  m='2074920'>transform</span> <span m='2075659'>and</span> <span
  m='2075850'>for</span> <span m='2076000'>the</span> <span
  m='2076330'>Z-transform.</span> <span m='2078020'>It's</span> <span
  m='2078120'>a</span> <span m='2078190'>property</span> <span
  m='2078670'>that</span> <span m='2078820'>states,</span> <span
  m='2079179'>essentially,</span> <span m='2080530'>that</span> <span
  m='2081250'>the</span> <span m='2081370'>convolution</span> <span
  m='2082929'>of</span> <span m='2083620'>two</span> <span
  m='2083830'>periodic</span> <span m='2084489'>sequences</span> <span
  m='2085810'>results</span> <span m='2086440'>in</span> <span
  m='2086590'>the</span> <span m='2086679'>multiplication</span> <span
  m='2087850'>of</span> <span m='2088630'>the</span> <span
  m='2089380'>discrete</span> <span m='2089739'>Fourier</span> <span
  m='2090130'>series</span> <span m='2090550'>coefficients,</span> <span
  m='2091780'>with</span> <span m='2091960'>just</span> <span
  m='2092230'>one</span> <span m='2092530'>minor</span> <span
  m='2092889'>twist,</span> <span m='2093790'>which</span> <span
  m='2094120'>again</span> <span m='2094480'>will</span> <span
  m='2094570'>become</span> <span m='2094900'>important</span> <span
  m='2095409'>when</span> <span m='2095620'>we</span> <span
  m='2095770'>relate</span> <span m='2096070'>this</span> <span
  m='2096280'>to</span> <span m='2096400'>the</span> <span
  m='2097350'>discrete</span> <span m='2097750'>Fourier</span> <span
  m='2098140'>transform.</span> </p><p><span m='2099490'>In</span> <span
  m='2099580'>particular,</span> <span m='2101270'>we</span> <span
  m='2101350'>have</span> <span m='2102310'>a</span> <span
  m='2102370'>periodic</span> <span m='2103000'>sequence,</span> <span
  m='2103630'>x1</span> <span m='2104090'>tilde</span> <span
  m='2104380'>of</span> <span m='2104510'>n.</span> <span m='2105640'>And</span>
  <span m='2105760'>here</span> <span m='2106240'>its</span> <span
  m='2106700'>Fourier</span> <span m='2106810'>series</span> <span
  m='2107230'>coefficients.</span> <span m='2109120'>A</span> <span
  m='2109180'>second</span> <span m='2110350'>periodic</span> <span
  m='2110920'>sequence,</span> <span m='2111750'>x2</span> <span
  m='2112030'>tilde</span> <span m='2112390'>of</span> <span
  m='2112750'>n,</span> <span m='2113110'>with</span> <span
  m='2113260'>its</span> <span m='2113890'>Fourier</span> <span
  m='2114010'>series</span> <span m='2114430'>coefficients.</span> <span
  m='2116200'>And</span> <span m='2116650'>what</span> <span
  m='2116830'>we'd</span> <span m='2117010'>like</span> <span
  m='2117250'>to</span> <span m='2117370'>ask</span> <span
  m='2117970'>is,</span> <span m='2119890'>what</span> <span
  m='2120220'>is</span> <span m='2120820'>the</span> <span
  m='2121660'>periodic</span> <span m='2122290'>sequence,</span> <span
  m='2123470'>x3</span> <span m='2124150'>tilde</span> <span
  m='2124570'>of</span> <span m='2124720'>n,</span> <span
  m='2126010'>whose</span> <span m='2126250'>Fourier</span> <span
  m='2126730'>series</span> <span m='2127240'>coefficients</span> <span
  m='2128590'>are</span> <span m='2128740'>the</span> <span
  m='2128830'>product</span> <span m='2129850'>of</span> <span
  m='2130470'>x1</span> <span m='2131030'>tilde</span> <span
  m='2131360'>of</span> <span m='2131715'>k</span> <span m='2132070'>and</span>
  <span m='2132220'>x2</span> <span m='2132470'>tilde</span> <span
  m='2132830'>of</span> <span m='2133060'>k?</span> <span m='2134290'>In</span>
  <span m='2134380'>other</span> <span m='2134620'>words,</span> <span
  m='2135470'>if</span> <span m='2135570'>we</span> <span
  m='2135580'>multiply</span> <span m='2136150'>the</span> <span
  m='2136270'>Fourier</span> <span m='2136600'>series</span> <span
  m='2136990'>coefficients</span> <span m='2137680'>together,</span> <span
  m='2138640'>what</span> <span m='2138970'>is</span> <span
  m='2139150'>the</span> <span m='2139270'>sequence</span> <span
  m='2139810'>that</span> <span m='2139960'>that</span> <span
  m='2140170'>corresponds</span> <span m='2140980'>to?</span> <span
  m='2141910'>The</span> <span m='2142090'>answer,</span> <span
  m='2142700'>which</span> <span m='2143020'>involves</span> <span
  m='2143500'>just</span> <span m='2143650'>simply</span> <span
  m='2144310'>a</span> <span m='2144340'>little</span> <span
  m='2144580'>bit</span> <span m='2144730'>of</span> <span
  m='2144850'>algebra</span> <span m='2145390'>to</span> <span
  m='2145540'>verify,</span> <span m='2146860'>is</span> <span
  m='2147850'>that</span> <span m='2148450'>the</span> <span
  m='2148570'>resulting</span> <span m='2149110'>sequence</span> <span
  m='2150280'>is</span> <span m='2150480'>a</span> <span m='2150550'>sum</span>
  <span m='2151300'>of</span> <span m='2151600'>x1</span> <span
  m='2152320'>tilde</span> <span m='2152590'>of</span> <span
  m='2152770'>m,</span> <span m='2154290'>x2</span> <span
  m='2154970'>tilde</span> <span m='2155410'>of</span> <span
  m='2155800'>n</span> <span m='2156190'>minus</span> <span
  m='2156470'>m.</span> </p><p><span m='2157690'>Well,</span> <span
  m='2158560'>that</span> <span m='2158770'>looks</span> <span
  m='2159250'>exactly</span> <span m='2160000'>like</span> <span
  m='2160840'>a</span> <span m='2160900'>convolution</span> <span
  m='2163000'>with</span> <span m='2163240'>one</span> <span
  m='2163810'>important</span> <span m='2164380'>difference.</span> <span
  m='2165700'>And</span> <span m='2165820'>that</span> <span
  m='2166030'>is</span> <span m='2166600'>that</span> <span
  m='2166780'>the</span> <span m='2166900'>limits</span> <span
  m='2167350'>on</span> <span m='2167500'>the</span> <span
  m='2167590'>summation</span> <span m='2169150'>don't</span> <span
  m='2169420'>go</span> <span m='2169660'>from</span> <span
  m='2169870'>minus</span> <span m='2170230'>infinity</span> <span
  m='2170740'>to</span> <span m='2170860'>plus</span> <span
  m='2171160'>infinity</span> <span m='2172240'>as</span> <span
  m='2172450'>they</span> <span m='2172600'>did</span> <span
  m='2173290'>in</span> <span m='2173380'>the</span> <span
  m='2173470'>case</span> <span m='2173800'>of</span> <span
  m='2173860'>the</span> <span m='2174010'>Fourier</span> <span
  m='2174370'>transform</span> <span m='2174960'>and</span> <span
  m='2175090'>Z-transform.</span> <span m='2176770'>Ordinary</span> <span
  m='2177220'>linear</span> <span m='2177640'>convolution,</span> <span
  m='2178390'>as</span> <span m='2178540'>we've</span> <span
  m='2178720'>always</span> <span m='2179020'>been</span> <span
  m='2179170'>talking</span> <span m='2179620'>about</span> <span
  m='2179970'>it,</span> <span m='2180480'>involved</span> <span
  m='2180860'>the</span> <span m='2180970'>sum</span> <span
  m='2181300'>from</span> <span m='2181460'>minus</span> <span
  m='2181870'>infinity</span> <span m='2182350'>to</span> <span
  m='2182470'>plus</span> <span m='2182770'>infinity,</span> <span
  m='2183460'>of</span> <span m='2184090'>x1</span> <span m='2184380'>of</span>
  <span m='2184610'>m,</span> <span m='2185170'>x2</span> <span
  m='2185740'>of</span> <span m='2185890'>n</span> <span
  m='2186070'>minus</span> <span m='2186370'>m.</span> <span
  m='2187780'>Here</span> <span m='2187990'>we</span> <span
  m='2188170'>have,</span> <span m='2188910'>as</span> <span
  m='2189280'>the</span> <span m='2189370'>limits</span> <span
  m='2189730'>on</span> <span m='2189880'>the</span> <span
  m='2189970'>sum,</span> <span m='2190870'>0</span> <span m='2191780'>to</span>
  <span m='2191920'>capital</span> <span m='2192430'>N</span> <span
  m='2192580'>minus</span> <span m='2192970'>1.</span> <span
  m='2193960'>The</span> <span m='2194050'>summation</span> <span
  m='2194740'>is</span> <span m='2194920'>carried</span> <span
  m='2195310'>out</span> <span m='2195640'>only</span> <span
  m='2196120'>over</span> <span m='2196660'>one</span> <span
  m='2196960'>period.</span> </p><p><span m='2198670'>We</span> <span
  m='2198820'>have</span> <span m='2199060'>also</span> <span
  m='2199600'>a</span> <span m='2199690'>dual</span> <span
  m='2200020'>property,</span> <span m='2202260'>in</span> <span
  m='2202280'>other</span> <span m='2202490'>words,</span> <span
  m='2203160'>the</span> <span m='2203180'>property</span> <span
  m='2204650'>that</span> <span m='2205610'>relates</span> <span
  m='2205955'>the</span> <span m='2206300'>Fourier</span> <span
  m='2206760'>series</span> <span m='2207470'>coefficients</span> <span
  m='2209150'>of</span> <span m='2209960'>the</span> <span
  m='2210050'>product</span> <span m='2210710'>of</span> <span
  m='2210860'>two</span> <span m='2211040'>sequences</span> <span
  m='2212480'>to</span> <span m='2212630'>the</span> <span
  m='2212720'>Fourier</span> <span m='2212990'>series</span> <span
  m='2213530'>coefficients</span> <span m='2214310'>of</span> <span
  m='2214490'>the</span> <span m='2214610'>individual</span> <span
  m='2215240'>sequences.</span> <span m='2216620'>And</span> <span
  m='2217280'>because</span> <span m='2217670'>of</span> <span
  m='2217790'>the</span> <span m='2217880'>duality</span> <span
  m='2218510'>now</span> <span m='2218780'>that</span> <span
  m='2218900'>we</span> <span m='2219050'>have</span> <span
  m='2219290'>between</span> <span m='2220040'>the</span> <span
  m='2220160'>time</span> <span m='2220460'>domain</span> <span
  m='2220850'>and</span> <span m='2220940'>the</span> <span
  m='2221030'>frequency</span> <span m='2221540'>domain for the</span> <span
  m='2221990'>Fourier</span> <span m='2222620'>series,</span> <span
  m='2224280'>these</span> <span m='2224600'>Fourier</span> <span
  m='2225020'>series</span> <span m='2225410'>coefficients</span> <span
  m='2226850'>are,</span> <span m='2227660'>again,</span> <span
  m='2228050'>the</span> <span m='2228140'>convolution</span> <span
  m='2229580'>of</span> <span m='2230570'>the</span> <span
  m='2230840'>two</span> <span m='2231080'>Fourier</span> <span
  m='2231520'>series</span> <span m='2231890'>coefficients</span> <span
  m='2232160'>for</span> <span m='2232730'>x1</span> <span m='2232970'>of
  n</span> <span m='2233260'>and</span> <span m='2233780'>x2</span> <span
  m='2234230'>of n.</span> <span m='2235470'>There's</span> <span
  m='2235700'>a</span> <span m='2236150'>normalization</span> <span
  m='2236930'>factor,</span> <span m='2237380'>1</span> <span
  m='2237560'>over</span> <span m='2237770'>capital</span> <span
  m='2238280'>N.</span> <span m='2238880'>But</span> <span
  m='2239030'>again,</span> <span m='2239840'>the</span> <span
  m='2239930'>limits</span> <span m='2240290'>on</span> <span
  m='2240440'>the</span> <span m='2240530'>sum</span> <span
  m='2241760'>involve</span> <span m='2242300'>0</span> <span
  m='2242780'>to</span> <span m='2242950'>capital</span> <span
  m='2243410'>N</span> <span m='2243530'>minus</span> <span
  m='2243950'>1.</span> </p><p><span m='2245878'>So</span> <span
  m='2246360'>this</span> <span m='2246990'>is</span> <span
  m='2247920'>slightly</span> <span m='2248460'>different</span> <span
  m='2248940'>than</span> <span m='2249060'>the</span> <span
  m='2249150'>convolution</span> <span m='2249870'>as</span> <span
  m='2249990'>we've</span> <span m='2250170'>been</span> <span
  m='2250320'>talking</span> <span m='2250740'>about.</span> <span
  m='2251860'>It</span> <span m='2252140'>is</span> <span
  m='2252630'>referred</span> <span m='2253110'>to</span> <span
  m='2253410'>generally,</span> <span m='2254430'>and</span> <span
  m='2254670'>we'll</span> <span m='2254820'>be</span> <span
  m='2254970'>referring</span> <span m='2255420'>to</span> <span
  m='2255660'>it</span> <span m='2255930'>as</span> <span m='2256410'>a</span>
  <span m='2256470'>periodic</span> <span m='2257100'>convolution.</span> <span
  m='2258420'>The</span> <span m='2258540'>important</span> <span
  m='2259890'>distinction</span> <span m='2260580'>being</span> <span
  m='2261690'>that</span> <span m='2262140'>for</span> <span
  m='2262320'>this</span> <span m='2262530'>convolution,</span> <span
  m='2263850'>it</span> <span m='2263970'>involves</span> <span
  m='2264510'>a</span> <span m='2264570'>summation,</span> <span
  m='2265440'>not</span> <span m='2265680'>for</span> <span
  m='2265840'>minus</span> <span m='2266190'>infinity</span> <span
  m='2266670'>to</span> <span m='2266760'>plus</span> <span
  m='2267060'>infinity,</span> <span m='2268020'>but</span> <span
  m='2268170'>simply</span> <span m='2268680'>a</span> <span
  m='2268770'>summation</span> <span m='2269640'>over</span> <span
  m='2270090'>only</span> <span m='2270420'>one</span> <span
  m='2270690'>period</span> <span m='2271500'>of</span> <span
  m='2271650'>the</span> <span m='2271740'>periodic</span> <span
  m='2272310'>sequences.</span> <span m='2274270'>Well,</span> <span
  m='2274810'>to</span> <span m='2275260'>drive</span> <span
  m='2275620'>this</span> <span m='2275860'>home,</span> <span
  m='2276400'>let</span> <span m='2276640'>me</span> <span
  m='2277360'>just</span> <span m='2278050'>show</span> <span
  m='2278380'>you</span> <span m='2278770'>with</span> <span
  m='2279310'>a</span> <span m='2282080'>simple</span> <span
  m='2282460'>example</span> <span m='2283570'>what</span> <span
  m='2283810'>these</span> <span m='2283990'>sequences</span> <span
  m='2284620'>look</span> <span m='2284830'>like,</span> <span
  m='2285580'>and</span> <span m='2286210'>in</span> <span
  m='2286300'>particular,</span> <span m='2286810'>what</span> <span
  m='2287020'>the</span> <span m='2287140'>shifting</span> <span
  m='2287620'>involves,</span> <span m='2288610'>and</span> <span
  m='2288940'>apply</span> <span m='2289720'>an</span> <span
  m='2289870'>interpretation</span> <span m='2290650'>to</span> <span
  m='2290770'>that.</span> <span m='2291490'>And</span> <span
  m='2291700'>so</span> <span m='2291910'>let's</span> <span
  m='2292330'>return</span> <span m='2292810'>to</span> <span
  m='2293230'>the</span> <span m='2293350'>view</span> <span
  m='2293480'>graph.</span> </p><p><span m='2300860'>What</span> <span
  m='2301220'>I'm</span> <span m='2301970'>indicating</span> <span
  m='2302600'>here</span> <span m='2303890'>is</span> <span m='2304550'>a</span>
  <span m='2304610'>sequence</span> <span m='2305390'>x2</span> <span
  m='2306950'>tilde</span> <span m='2307350'>of</span> <span
  m='2307580'>m,</span> <span m='2308982'>a</span> <span
  m='2309470'>sequence</span> <span m='2310120'>x1</span> <span
  m='2311200'>tilde</span> <span m='2311620'>of</span> <span
  m='2311880'>m,</span> <span m='2313390'>and</span> <span m='2314410'>to</span>
  <span m='2314770'>form</span> <span m='2315220'>the</span> <span
  m='2315310'>convolution</span> <span m='2316390'>of</span> <span
  m='2316540'>these</span> <span m='2316780'>two</span> <span
  m='2316960'>sequences.</span> <span m='2318790'>What</span> <span
  m='2319060'>I</span> <span m='2319180'>would</span> <span
  m='2319330'>like</span> <span m='2319570'>to</span> <span
  m='2319720'>do</span> <span m='2320290'>is</span> <span
  m='2321900'>generate</span> <span m='2322620'>x2</span> <span
  m='2323710'>tilde,</span> <span m='2324070'>in</span> <span
  m='2324810'>general,</span> <span m='2325530'>of</span> <span
  m='2326310'>n</span> <span m='2326910'>minus</span> <span
  m='2327390'>m,</span> <span m='2329100'>multiply</span> <span
  m='2330150'>that</span> <span m='2331260'>by</span> <span
  m='2331530'>this,</span> <span m='2332340'>by</span> <span
  m='2332580'>x1</span> <span m='2333010'>tilde</span> <span
  m='2333360'>of</span> <span m='2333560'>m,</span> <span m='2334740'>and</span>
  <span m='2334920'>then</span> <span m='2335310'>sum</span> <span
  m='2335670'>up</span> <span m='2335850'>the</span> <span
  m='2335960'>result</span> <span m='2336480'>over</span> <span
  m='2336780'>one</span> <span m='2337020'>period.</span> <span
  m='2338860'>Well,</span> <span m='2339270'>I'm</span> <span
  m='2339690'>indicating,</span> <span m='2340740'>by</span> <span
  m='2340920'>the</span> <span m='2341040'>way,</span> <span
  m='2342200'>in</span> <span m='2342390'>blue,</span> <span
  m='2343140'>just</span> <span m='2343410'>one</span> <span
  m='2343680'>period</span> <span m='2344280'>of</span> <span
  m='2344460'>this</span> <span m='2344670'>periodic</span> <span
  m='2345240'>sequence.</span> <span m='2346320'>And</span> <span
  m='2346440'>similarly</span> <span m='2347220'>in</span> <span
  m='2347400'>blue,</span> <span m='2347820'>one</span> <span
  m='2348090'>period</span> <span m='2348660'>of</span> <span
  m='2348810'>this</span> <span m='2349020'>periodic</span> <span
  m='2349620'>sequence.</span> </p><p><span m='2350890'>So</span> <span
  m='2350940'>let's</span> <span m='2351210'>examine,</span> <span
  m='2351780'>first</span> <span m='2352170'>of</span> <span
  m='2352320'>all,</span> <span m='2353550'>the</span> <span
  m='2353640'>sequence</span> <span m='2354720'>which</span> <span
  m='2354930'>corresponds</span> <span m='2355890'>to</span> <span
  m='2356190'>replacing</span> <span m='2356820'>this</span> <span
  m='2357750'>by</span> <span m='2358290'>x2</span> <span
  m='2358920'>tilde</span> <span m='2359550'>of</span> <span
  m='2360210'>n</span> <span m='2360840'>minus</span> <span
  m='2361410'>m.</span> <span m='2362370'>And</span> <span
  m='2363000'>let's</span> <span m='2363810'>do</span> <span
  m='2364050'>it</span> <span m='2364170'>for</span> <span
  m='2364290'>the</span> <span m='2364400'>specific</span> <span
  m='2365190'>case</span> <span m='2365610'>where</span> <span
  m='2365780'>little</span> <span m='2366060'>n</span> <span
  m='2366190'>is</span> <span m='2366330'>equal</span> <span
  m='2366600'>to</span> <span m='2366750'>2.</span> <span m='2367710'>So</span>
  <span m='2368100'>I've</span> <span m='2368250'>illustrated</span> <span
  m='2368880'>here</span> <span m='2369540'>the</span> <span
  m='2369660'>sequence</span> <span m='2370680'>x2</span> <span
  m='2371600'>tilde</span> <span m='2371950'>of</span> <span
  m='2372600'>2</span> <span m='2373320'>minus</span> <span
  m='2373800'>m.</span> <span m='2375120'>And</span> <span m='2375240'>to</span>
  <span m='2375360'>generate</span> <span m='2375930'>this</span> <span
  m='2376140'>sequence</span> <span m='2377100'>from</span> <span
  m='2377310'>this</span> <span m='2377580'>one</span> <span
  m='2378870'>involves</span> <span m='2380280'>essentially</span> <span
  m='2380790'>two</span> <span m='2381000'>steps.</span> <span
  m='2382300'>The</span> <span m='2382400'>first</span> <span
  m='2382590'>step</span> <span m='2383040'>is</span> <span
  m='2383880'>to</span> <span m='2384270'>flip</span> <span
  m='2385020'>this</span> <span m='2385200'>sequence</span> <span
  m='2385740'>over,</span> <span m='2386550'>that's</span> <span
  m='2386790'>replacing</span> <span m='2387510'>m</span> <span
  m='2388170'>by</span> <span m='2388320'>minus</span> <span
  m='2388690'>m.</span> <span m='2390720'>And</span> <span
  m='2391440'>then</span> <span m='2391920'>the</span> <span
  m='2392040'>second</span> <span m='2392430'>step</span> <span
  m='2393120'>is</span> <span m='2393780'>to</span> <span
  m='2393900'>shift</span> <span m='2394230'>the</span> <span
  m='2394350'>sequence</span> <span m='2395190'>by</span> <span
  m='2395400'>an</span> <span m='2395490'>amount</span> <span
  m='2395790'>little</span> <span m='2396110'>n,</span> <span
  m='2396810'>depending</span> <span m='2397320'>on</span> <span
  m='2397470'>the</span> <span m='2397590'>argument</span> <span
  m='2398130'>that</span> <span m='2398490'>we</span> <span
  m='2398610'>want</span> <span m='2398790'>to</span> <span
  m='2398850'>stick</span> <span m='2399150'>in</span> <span
  m='2399300'>here.</span> </p><p><span m='2400440'>Now</span> <span
  m='2402510'>this</span> <span m='2402870'>is</span> <span
  m='2403020'>the</span> <span m='2403110'>result</span> <span
  m='2403500'>of</span> <span m='2403620'>doing</span> <span
  m='2403950'>that.</span> <span m='2404490'>We</span> <span
  m='2405060'>can</span> <span m='2405210'>think</span> <span
  m='2405480'>of</span> <span m='2405600'>this</span> <span
  m='2406050'>as</span> <span m='2406350'>having</span> <span
  m='2406710'>flipped</span> <span m='2407520'>this</span> <span
  m='2407700'>sequence</span> <span m='2408210'>over,</span> <span
  m='2409230'>and</span> <span m='2409380'>then</span> <span
  m='2410130'>shifted</span> <span m='2410670'>it</span> <span
  m='2411150'>by</span> <span m='2412740'>two</span> <span
  m='2413220'>points</span> <span m='2414240'>to</span> <span
  m='2414360'>the</span> <span m='2414480'>right.</span> <span
  m='2417020'>And</span> <span m='2417530'>the</span> <span
  m='2417650'>result</span> <span m='2418250'>is</span> <span
  m='2418430'>then</span> <span m='2418880'>this</span> <span
  m='2419120'>periodic</span> <span m='2419720'>sequence.</span> <span
  m='2422040'>An</span> <span m='2422150'>important</span> <span
  m='2423630'>thing</span> <span m='2424260'>to</span> <span
  m='2425840'>keep</span> <span m='2426110'>in</span> <span
  m='2426230'>mind,</span> <span m='2426860'>or</span> <span
  m='2427280'>to</span> <span m='2427430'>look</span> <span
  m='2427730'>at--</span> <span m='2428090'>and</span> <span
  m='2428420'>again,</span> <span m='2428820'>this</span> <span
  m='2428900'>is</span> <span m='2429170'>a</span> <span
  m='2429230'>point</span> <span m='2429530'>that</span> <span
  m='2429620'>we'll</span> <span m='2429770'>be</span> <span
  m='2429920'>emphasizing</span> <span m='2431240'>in</span> <span
  m='2431330'>much</span> <span m='2431570'>more</span> <span
  m='2431750'>detail</span> <span m='2432350'>in</span> <span
  m='2432470'>the</span> <span m='2432530'>next</span> <span
  m='2432800'>lecture--</span> <span m='2434090'>is</span> <span
  m='2434300'>that</span> <span m='2435560'>as</span> <span
  m='2435740'>we</span> <span m='2435890'>examine</span> <span
  m='2436400'>these</span> <span m='2436610'>blue</span> <span
  m='2436880'>points,</span> <span m='2438080'>we</span> <span
  m='2438200'>could</span> <span m='2438380'>think</span> <span
  m='2438710'>of</span> <span m='2438860'>having</span> <span
  m='2439190'>gotten</span> <span m='2439640'>those</span> <span
  m='2440510'>by</span> <span m='2440720'>simply</span> <span
  m='2441830'>flipping</span> <span m='2442550'>one</span> <span
  m='2442850'>period</span> <span m='2443390'>of</span> <span
  m='2443570'>this</span> <span m='2444740'>and</span> <span
  m='2444890'>circularly</span> <span m='2445670'>shifting</span> <span
  m='2446540'>that,</span> <span m='2447350'>circularly</span> <span
  m='2447950'>shifting</span> <span m='2448430'>those</span> <span
  m='2448700'>points,</span> <span m='2449540'>simply</span> <span
  m='2450050'>in</span> <span m='2450170'>the</span> <span
  m='2450260'>range</span> <span m='2450620'>0</span> <span
  m='2452000'>to</span> <span m='2452120'>capital</span> <span
  m='2452560'>N</span> <span m='2452690'>minus</span> <span
  m='2453080'>1.</span> <span m='2453820'>That's</span> <span
  m='2454190'>an</span> <span m='2454280'>interpretation</span> <span
  m='2455240'>that</span> <span m='2455360'>will</span> <span
  m='2455510'>become</span> <span m='2455840'>much</span> <span
  m='2456080'>more</span> <span m='2456320'>evident</span> <span
  m='2457160'>in</span> <span m='2457700'>the</span> <span
  m='2457790'>next</span> <span m='2458240'>lecture.</span> </p><p><span
  m='2460190'>But</span> <span m='2460670'>then</span> <span
  m='2460880'>to</span> <span m='2461000'>form</span> <span
  m='2461330'>the</span> <span m='2461450'>convolution</span> <span
  m='2462440'>of</span> <span m='2462620'>this</span> <span
  m='2462800'>sequence</span> <span m='2463580'>with</span> <span
  m='2463760'>this</span> <span m='2463910'>sequence,</span> <span
  m='2466070'>we</span> <span m='2466310'>then,</span> <span
  m='2467960'>after</span> <span m='2468290'>having</span> <span
  m='2468560'>constructed</span> <span m='2469420'>x2</span> <span
  m='2469880'>tilde</span> <span m='2470410'>of</span> <span
  m='2470810'>n</span> <span m='2471260'>minus</span> <span
  m='2471630'>m,</span> <span m='2472610'>carry</span> <span
  m='2472970'>out</span> <span m='2473120'>the</span> <span
  m='2473240'>multiplication</span> <span m='2474350'>of</span> <span
  m='2474830'>these</span> <span m='2475040'>two</span> <span
  m='2475220'>sequences.</span> <span m='2476810'>The</span> <span
  m='2476930'>result</span> <span m='2477320'>of</span> <span
  m='2477410'>that</span> <span m='2477560'>multiplication,</span> <span
  m='2478720'>I've</span> <span m='2479060'>indicated</span> <span
  m='2479690'>here,</span> <span m='2480650'>so</span> <span
  m='2480860'>that</span> <span m='2481190'>for</span> <span
  m='2481340'>this</span> <span m='2481520'>particular</span> <span
  m='2482060'>example,</span> <span m='2483440'>these</span> <span
  m='2483770'>three</span> <span m='2484040'>points</span> <span
  m='2484580'>get</span> <span m='2484730'>multiplied</span> <span
  m='2485720'>by</span> <span m='2485870'>these</span> <span
  m='2486140'>three.</span> <span m='2487650'>These</span> <span
  m='2489600'>four</span> <span m='2489900'>points,</span> <span
  m='2490290'>rather,</span> <span m='2490590'>get</span> <span
  m='2490770'>multiplied</span> <span m='2491340'>by</span> <span
  m='2491460'>these</span> <span m='2491700'>four</span> <span
  m='2491970'>values.</span> <span m='2492990'>The</span> <span
  m='2493080'>rest</span> <span m='2493350'>of</span> <span
  m='2493470'>the</span> <span m='2493560'>points</span> <span
  m='2494070'>in</span> <span m='2494190'>that</span> <span
  m='2494340'>one</span> <span m='2494580'>period</span> <span
  m='2494970'>get</span> <span m='2495150'>multiplied</span> <span
  m='2495720'>by</span> <span m='2495900'>0.</span> <span m='2497610'>And</span>
  <span m='2497880'>then</span> <span m='2498060'>finally,</span> <span
  m='2498570'>to</span> <span m='2498750'>evaluate</span> <span
  m='2499620'>the</span> <span m='2499740'>result</span> <span
  m='2500250'>of</span> <span m='2500430'>the</span> <span
  m='2500520'>periodic</span> <span m='2501060'>convolution</span> <span
  m='2502340'>for</span> <span m='2502500'>little</span> <span
  m='2502770'>n</span> <span m='2503160'>equal</span> <span
  m='2503490'>to</span> <span m='2503640'>2,</span> <span m='2504530'>we</span>
  <span m='2504660'>sum</span> <span m='2505020'>up</span> <span
  m='2505200'>those</span> <span m='2505500'>values</span> <span
  m='2506460'>in</span> <span m='2506550'>the</span> <span
  m='2506640'>range</span> <span m='2506970'>0</span> <span
  m='2507960'>to</span> <span m='2508080'>capital</span> <span
  m='2508560'>N</span> <span m='2508680'>minus</span> <span
  m='2509080'>1.</span> </p><p><span m='2510391'>So</span> <span
  m='2510830'>it</span> <span m='2510980'>operates</span> <span
  m='2511580'>very</span> <span m='2511940'>much</span> <span
  m='2512210'>like</span> <span m='2512750'>a</span> <span
  m='2512840'>linear</span> <span m='2513380'>or</span> <span
  m='2513540'>ordinary</span> <span m='2514040'>convolution,</span> <span
  m='2515480'>as</span> <span m='2515930'>we've</span> <span
  m='2516140'>been</span> <span m='2516260'>talking</span> <span
  m='2516710'>about</span> <span m='2517040'>over</span> <span
  m='2517280'>the</span> <span m='2517370'>last</span> <span
  m='2517640'>several</span> <span m='2517970'>lectures.</span> <span
  m='2519020'>The</span> <span m='2519110'>important</span> <span
  m='2519590'>difference</span> <span m='2520160'>is</span> <span
  m='2520370'>that</span> <span m='2520910'>the</span> <span
  m='2521000'>summation</span> <span m='2522740'>is</span> <span
  m='2522890'>carried</span> <span m='2523280'>out</span> <span
  m='2523640'>just</span> <span m='2523850'>simply</span> <span
  m='2524480'>over</span> <span m='2524780'>one</span> <span
  m='2525020'>period.</span> <span m='2527350'>All</span> <span
  m='2527440'>right.</span> <span m='2527740'>Well,</span> <span
  m='2528460'>that</span> <span m='2530650'>completes</span> <span
  m='2531430'>the</span> <span m='2531700'>discussion</span> <span
  m='2532780'>as</span> <span m='2533440'>we</span> <span
  m='2533590'>want</span> <span m='2534070'>to</span> <span
  m='2534370'>present</span> <span m='2534790'>it,</span> <span
  m='2535510'>of</span> <span m='2536110'>the</span> <span
  m='2536500'>discrete</span> <span m='2536950'>Fourier</span> <span
  m='2537370'>series.</span> <span m='2538540'>As</span> <span
  m='2538660'>I</span> <span m='2538810'>indicated</span> <span
  m='2539380'>at</span> <span m='2539470'>the</span> <span
  m='2539560'>beginning</span> <span m='2539950'>of</span> <span
  m='2540070'>the</span> <span m='2540160'>lecture,</span> <span
  m='2540850'>our</span> <span m='2541150'>objective</span> <span
  m='2542050'>was</span> <span m='2543340'>eventually</span> <span
  m='2544300'>to</span> <span m='2544660'>develop</span> <span
  m='2545380'>a</span> <span m='2546550'>Fourier</span> <span
  m='2547510'>representation</span> <span m='2548500'>for</span> <span
  m='2548680'>finite</span> <span m='2549130'>length</span> <span
  m='2549340'>sequences,</span> <span m='2550060'>that</span> <span
  m='2550240'>is,</span> <span m='2550390'>the</span> <span
  m='2550500'>discrete</span> <span m='2550900'>Fourier</span> <span
  m='2551290'>transform.</span> </p><p><span m='2552940'>And</span> <span
  m='2554350'>in</span> <span m='2554860'>the</span> <span
  m='2554980'>next</span> <span m='2555250'>lecture,</span> <span
  m='2556310'>what</span> <span m='2556480'>we'll</span> <span
  m='2556660'>want</span> <span m='2556900'>to</span> <span
  m='2556990'>do</span> <span m='2557530'>is</span> <span
  m='2558100'>take</span> <span m='2558370'>the</span> <span
  m='2558520'>ideas</span> <span m='2559390'>of</span> <span
  m='2559840'>the</span> <span m='2559960'>discrete</span> <span
  m='2560350'>Fourier</span> <span m='2560770'>series,</span> <span
  m='2562030'>as</span> <span m='2562210'>we've</span> <span
  m='2562360'>talked</span> <span m='2562690'>about</span> <span
  m='2562990'>them</span> <span m='2563140'>here,</span> <span
  m='2564070'>and</span> <span m='2564190'>apply</span> <span
  m='2564670'>them</span> <span m='2565450'>to</span> <span
  m='2566260'>the</span> <span m='2566410'>representation</span> <span
  m='2567640'>of</span> <span m='2567850'>finite</span> <span
  m='2568270'>length</span> <span m='2568510'>sequences,</span> <span
  m='2569680'>resulting</span> <span m='2570280'>in</span> <span
  m='2570730'>what</span> <span m='2570910'>we'll</span> <span
  m='2571060'>call</span> <span m='2571630'>the</span> <span
  m='2571720'>discrete</span> <span m='2572080'>Fourier</span> <span
  m='2572470'>transform.</span> </p>
embedded_media:
  - uid: 785b36fa522bbd2dea1e7834a7c26315
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: MITRES_6_008S11_lec08.pdf
    title: MITRES_6_008S11_lec08.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-8-the-discrete-fourier-series/MITRES_6_008S11_lec08.pdf
  - uid: 2c8f9134ca429a830580ea751c88c2a1
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: n9u9Vy_peHM
  - uid: e8094ad5a9a292df61b5a49c47083c05
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-8-the-discrete-fourier/id481803782?i=108362010
  - uid: 11bab36ef05ffeca7db9ad5164e38f95
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec08_300k.mp4'
  - uid: a1dd74c7b7a17aaed2c72ceab56c85ad
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/n9u9Vy_peHM/default.jpg'
  - uid: e95c12e00a90011d6768ccf66affe7d6
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: n9u9Vy_peHM
  - uid: 6f3860ebc5297179686c7b785b08f958
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: n9u9Vy_peHM.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-8-the-discrete-fourier-series/n9u9Vy_peHM.srt
  - uid: d3b263800b03ae81288e2636144cc71a
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: n9u9Vy_peHM.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-8-the-discrete-fourier-series/n9u9Vy_peHM.pdf
  - uid: 190281714a11b4f4ae98c30c8ee156fb
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 182c19681f4b5ed12f56bffe6fec3ae3
    parent_uid: 95fe2f09600cdd292eb41e196c4d6888
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
