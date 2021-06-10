---
order_index: null
title: 'Demonstration 1: Sampling, Aliasing, and Frequency Response, Part 1'
template_type: Tabbed
uid: a8e2f3dbd8cbb59df512763287828b6a
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-1-sampling-aliasing-and-frequency-response-part-1
short_url: demonstration-1-sampling-aliasing-and-frequency-response-part-1
inline_embed_id: '57969437demonstration1:sampling,aliasing,andfrequencyresponse,part177697911'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Sampling and aliasing with a sinusoidal
  signal, sinusoidal response of a digital filter, dependence of frequency
  response on sampling period, periodic nature of the frequency response of a
  digital filter.</p> <p><strong>Instructor:</strong> Prof. Alan V.
  Oppenheim</p>
related_resources_text: ''
transcript: >-
  <p><span m='90'>The</span> <span m='180'>following</span> <span
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
  <span m='15550'>visit</span> <span m='15780'>MIT</span> <span
  m='16200'>OpenCourseWare</span> <span m='17280'>at</span> <span
  m='17430'>ocw.mit.edu.</span> </p><p><span m='24416'>[MUSIC PLAYING]</span>
  </p><p></p><p><span m='51240'>ALAN OPPENHEIM:</span> <span m='51285'>In</span>
  <span m='51330'>This</span> <span m='51510'>lecture,</span> <span
  m='52040'>I</span> <span m='52140'>would</span> <span m='52170'>like</span>
  <span m='52440'>to</span> <span m='52710'>demonstrate</span> <span
  m='53490'>the</span> <span m='54090'>effects</span> <span m='54510'>of</span>
  <span m='54600'>sampling</span> <span m='55080'>and</span> <span
  m='55170'>aliasing,</span> <span m='56310'>and</span> <span
  m='56430'>also,</span> <span m='56910'>some</span> <span m='57150'>of</span>
  <span m='57210'>the</span> <span m='57330'>properties</span> <span
  m='57990'>of</span> <span m='58080'>discrete</span> <span
  m='58440'>time</span> <span m='58740'>linear</span> <span
  m='59040'>systems.</span> <span m='60630'>What</span> <span
  m='60780'>we'll</span> <span m='60930'>be</span> <span m='61050'>using</span>
  <span m='61890'>to</span> <span m='62130'>demonstrate</span> <span
  m='62850'>this</span> <span m='63330'>is</span> <span m='63540'>a</span> <span
  m='63750'>programmable</span> <span m='64739'>digital</span> <span
  m='65129'>filter,</span> <span m='66120'>which</span> <span
  m='66360'>is</span> <span m='66600'>contained</span> <span m='67110'>in</span>
  <span m='67230'>this</span> <span m='67380'>box,</span> <span
  m='68770'>programmable</span> <span m='69690'>in</span> <span
  m='69840'>the</span> <span m='69930'>sense</span> <span m='70470'>that</span>
  <span m='71280'>many</span> <span m='71520'>of</span> <span
  m='71610'>the</span> <span m='71700'>parameters</span> <span
  m='72330'>of</span> <span m='72420'>the</span> <span m='72540'>filter--</span>
  <span m='72960'>for</span> <span m='73170'>example,</span> <span
  m='73650'>the</span> <span m='73740'>filter</span> <span
  m='74070'>coefficients,</span> <span m='75250'>the</span> <span
  m='75360'>coefficient</span> <span m='76170'>and</span> <span
  m='76320'>arithmetic</span> <span m='76920'>word</span> <span
  m='77190'>length,</span> <span m='77940'>the</span> <span
  m='78030'>sampling</span> <span m='78510'>rate</span> <span
  m='78720'>etc,</span> <span m='79410'>are</span> <span m='79560'>easily</span>
  <span m='79920'>changed.</span> <span m='80440'>In</span> <span
  m='80540'>other</span> <span m='80610'>words,</span> <span
  m='80850'>programmable.</span> </p><p><span m='82080'>So</span> <span
  m='82740'>this</span> <span m='82980'>is</span> <span m='83100'>the</span>
  <span m='83190'>basic</span> <span m='83610'>digital</span> <span
  m='83970'>filter.</span> <span m='84390'>And</span> <span
  m='84480'>then,</span> <span m='84700'>of</span> <span
  m='84800'>course,</span> <span m='85090'>we</span> <span m='85110'>have</span>
  <span m='85290'>some</span> <span m='85470'>associated</span> <span
  m='86160'>equipment</span> <span m='86850'>to</span> <span
  m='87090'>help</span> <span m='87330'>us</span> <span m='87450'>with</span>
  <span m='87550'>the</span> <span m='87660'>demonstration.</span> <span
  m='89730'>Well,</span> <span m='90030'>we'll</span> <span m='90210'>be</span>
  <span m='90630'>returning</span> <span m='91260'>to</span> <span
  m='92400'>this</span> <span m='92700'>filter</span> <span m='93420'>in</span>
  <span m='93540'>a</span> <span m='93600'>few</span> <span
  m='93810'>minutes,</span> <span m='94620'>when,</span> <span
  m='94950'>together</span> <span m='95460'>with</span> <span
  m='95760'>my</span> <span m='95940'>colleagues,</span> <span
  m='96540'>Mike</span> <span m='96810'>Portnoff</span> <span
  m='97140'>and</span> <span m='97470'>Dave</span> <span
  m='97740'>Harris,</span> <span m='98640'>I'll</span> <span m='98790'>be</span>
  <span m='98940'>demonstrating</span> <span m='99870'>several</span> <span
  m='100350'>of</span> <span m='100440'>the</span> <span m='100560'>ideas</span>
  <span m='101040'>that</span> <span m='101190'>we're</span> <span
  m='101370'>about</span> <span m='101610'>to</span> <span
  m='101730'>talk</span> <span m='102060'>about.</span> </p><p><span
  m='103030'>But</span> <span m='103320'>first</span> <span m='103650'>of</span>
  <span m='103770'>all,</span> <span m='104350'>let</span> <span
  m='104460'>me</span> <span m='104850'>explain</span> <span
  m='105630'>what</span> <span m='105870'>the</span> <span
  m='106140'>basic</span> <span m='106800'>setup</span> <span
  m='107340'>is.</span> <span m='109170'>The</span> <span
  m='110220'>programmable</span> <span m='110940'>digital</span> <span
  m='111330'>filter</span> <span m='112530'>consists,</span> <span
  m='113040'>essentially</span> <span m='113910'>of</span> <span
  m='114420'>a</span> <span m='114480'>system</span> <span
  m='115350'>which</span> <span m='115920'>is</span> <span m='116490'>a</span>
  <span m='116550'>sampler,</span> <span m='118410'>a</span> <span
  m='118650'>continuous</span> <span m='119280'>time,</span> <span
  m='119760'>or</span> <span m='121470'>C</span> <span m='121860'>to</span>
  <span m='121950'>D</span> <span m='122170'>converter,</span> <span
  m='123660'>which</span> <span m='124230'>converts</span> <span
  m='125160'>an</span> <span m='125970'>impulse</span> <span
  m='126480'>train</span> <span m='127320'>to</span> <span m='127740'>a</span>
  <span m='127800'>sequence,</span> <span m='129630'>a</span> <span
  m='129720'>digital</span> <span m='130139'>filter</span> <span
  m='131520'>to</span> <span m='131820'>obtain</span> <span m='132300'>a</span>
  <span m='132360'>filtered</span> <span m='132780'>output</span> <span
  m='133200'>sequence,</span> <span m='134520'>a</span> <span
  m='134670'>"discrete</span> <span m='135090'>time</span> <span
  m='135630'>to</span> <span m='136200'>time"</span> <span
  m='136800'>converter</span> <span m='137790'>to</span> <span
  m='137910'>convert</span> <span m='138270'>the</span> <span
  m='138360'>sequence</span> <span m='139200'>back</span> <span
  m='139530'>to</span> <span m='139650'>an</span> <span
  m='139740'>impulse</span> <span m='140190'>train,</span> <span
  m='141090'>and</span> <span m='141210'>finally</span> <span
  m='141870'>a</span> <span m='141960'>D-sampling</span> <span
  m='142830'>or</span> <span m='142950'>smoothing</span> <span
  m='143400'>low-pass</span> <span m='143940'>filter.</span> </p><p><span
  m='144780'>So</span> <span m='145260'>at</span> <span m='145410'>this</span>
  <span m='145620'>point,</span> <span m='146130'>we</span> <span
  m='146280'>have</span> <span m='146730'>a</span> <span
  m='146910'>continuous</span> <span m='147480'>time</span> <span
  m='147780'>input.</span> <span m='148770'>At</span> <span
  m='148890'>this</span> <span m='149100'>point,</span> <span
  m='149520'>we</span> <span m='149700'>have</span> <span m='150270'>a</span>
  <span m='150480'>continuous</span> <span m='151050'>time</span> <span
  m='151320'>impulse</span> <span m='151800'>train,</span> <span
  m='152610'>at</span> <span m='152760'>this</span> <span
  m='152970'>point,</span> <span m='153240'>a</span> <span
  m='153300'>sequence,</span> <span m='154380'>then</span> <span
  m='154560'>a</span> <span m='154620'>sequence</span> <span
  m='155190'>here,</span> <span m='156090'>an</span> <span
  m='156210'>impulse</span> <span m='156690'>train,</span> <span
  m='157350'>and</span> <span m='157830'>back</span> <span m='158130'>to</span>
  <span m='158280'>a</span> <span m='158340'>smooth,</span> <span
  m='158700'>continuous</span> <span m='159270'>time</span> <span
  m='159540'>function.</span> <span m='161490'>For</span> <span
  m='161580'>the</span> <span m='161670'>first</span> <span
  m='161910'>part</span> <span m='162150'>of</span> <span m='162210'>the</span>
  <span m='162270'>demonstration,</span> <span m='163710'>what</span> <span
  m='164070'>I</span> <span m='164190'>would</span> <span m='164370'>like</span>
  <span m='164790'>to</span> <span m='165060'>focus</span> <span
  m='165600'>on</span> <span m='165960'>is</span> <span m='166230'>just</span>
  <span m='166410'>simply</span> <span m='166950'>the</span> <span
  m='167250'>effects</span> <span m='167700'>of</span> <span
  m='167790'>sampling</span> <span m='168930'>and</span> <span
  m='169260'>aliasing.</span> <span m='170490'>And</span> <span
  m='170880'>so</span> <span m='171390'>for</span> <span m='171510'>the</span>
  <span m='171600'>first</span> <span m='171900'>part,</span> <span
  m='172380'>I'll</span> <span m='172560'>just</span> <span
  m='172740'>simply</span> <span m='173130'>choose</span> <span
  m='173790'>this</span> <span m='174060'>digital</span> <span
  m='174480'>filter</span> <span m='175050'>to</span> <span m='175230'>be</span>
  <span m='175530'>an</span> <span m='175650'>identity</span> <span
  m='176160'>system.</span> <span m='177220'>In</span> <span
  m='177240'>other</span> <span m='177420'>words,</span> <span
  m='178090'>the</span> <span m='178140'>impulse</span> <span
  m='178560'>response</span> <span m='179040'>of</span> <span
  m='179130'>this</span> <span m='179310'>system</span> <span
  m='179730'>is</span> <span m='179820'>just</span> <span
  m='180000'>simply</span> <span m='180360'>an</span> <span
  m='180450'>impulse.</span> </p><p><span m='181440'>In</span> <span
  m='181530'>that</span> <span m='181710'>case,</span> <span
  m='182460'>this</span> <span m='182640'>overall</span> <span
  m='183150'>system</span> <span m='183900'>collapses</span> <span
  m='184800'>to</span> <span m='185340'>a</span> <span
  m='185550'>somewhat</span> <span m='185970'>simpler</span> <span
  m='186390'>system,</span> <span m='187080'>as</span> <span m='188040'>I</span>
  <span m='188160'>have</span> <span m='188480'>on</span> <span
  m='188600'>this</span> <span m='188790'>next</span> <span
  m='189060'>viewgraph</span> <span m='190290'>where</span> <span
  m='191010'>we</span> <span m='191850'>convert</span> <span
  m='192600'>from</span> <span m='193320'>a</span> <span
  m='193470'>continuous</span> <span m='194100'>time</span> <span
  m='194400'>input</span> <span m='195450'>to</span> <span m='195690'>a</span>
  <span m='195750'>sequence</span> <span m='196590'>and</span> <span
  m='196830'>then</span> <span m='197640'>back</span> <span m='198330'>to</span>
  <span m='198810'>the</span> <span m='199380'>continuous</span> <span
  m='199950'>time</span> <span m='200250'>input.</span> <span
  m='201540'>And,</span> <span m='201720'>in</span> <span
  m='201810'>fact,</span> <span m='202200'>we</span> <span
  m='202350'>could</span> <span m='202650'>really</span> <span
  m='203400'>collapse</span> <span m='203940'>the</span> <span m='204240'>A
  to</span> <span m='204540'>D</span> <span m='204930'>or</span> <span
  m='205110'>C</span> <span m='205320'>to</span> <span m='205410'>D</span> <span
  m='205620'>converter</span> <span m='206250'>and</span> <span
  m='207090'>D</span> <span m='207240'>to</span> <span m='207330'>A</span> <span
  m='207510'>converter</span> <span m='208170'>together</span> <span
  m='209850'>since</span> <span m='210360'>we're</span> <span
  m='210540'>simply</span> <span m='210930'>converting</span> <span
  m='211350'>from</span> <span m='211500'>an</span> <span
  m='211560'>impulse</span> <span m='211980'>train</span> <span
  m='212280'>to</span> <span m='212430'>a</span> <span
  m='212460'>sequence</span> <span m='213120'>and</span> <span
  m='213300'>then</span> <span m='213480'>back</span> <span m='213780'>to</span>
  <span m='213900'>the</span> <span m='213990'>same</span> <span
  m='214260'>impulse</span> <span m='214680'>train.</span> <span
  m='216420'>To</span> <span m='216510'>see</span> <span m='216840'>what</span>
  <span m='217320'>the</span> <span m='217440'>effect</span> <span
  m='217830'>of</span> <span m='217920'>this</span> <span
  m='218100'>system</span> <span m='218550'>is</span> <span m='219240'>in</span>
  <span m='219360'>both</span> <span m='219600'>the</span> <span
  m='219690'>time</span> <span m='220020'>domain</span> <span
  m='220710'>and</span> <span m='220800'>frequency</span> <span
  m='221370'>domain,</span> <span m='222600'>we</span> <span
  m='222870'>can</span> <span m='223440'>look</span> <span m='223830'>at</span>
  <span m='224430'>the</span> <span m='225960'>associated</span> <span
  m='226710'>time</span> <span m='227210'>waveforms</span> <span
  m='227970'>and</span> <span m='228120'>spectra.</span> </p><p><span
  m='229920'>On</span> <span m='230730'>the</span> <span
  m='231240'>left-hand</span> <span m='231810'>side,</span> <span
  m='232530'>we</span> <span m='232710'>have</span> <span m='233220'>the</span>
  <span m='233670'>associated</span> <span m='234750'>time</span> <span
  m='235460'>wave</span> <span m='235710'>forms</span> <span
  m='236340'>and</span> <span m='236430'>sequences.</span> <span
  m='237270'>On</span> <span m='237390'>the</span> <span
  m='237450'>right-hand</span> <span m='237900'>side,</span> <span
  m='238530'>the</span> <span m='238650'>associated</span> <span
  m='239280'>Fourier</span> <span m='239670'>transforms.</span> <span
  m='241170'>So</span> <span m='241800'>we</span> <span m='241980'>can</span>
  <span m='242460'>think</span> <span m='242760'>of</span> <span
  m='242880'>an</span> <span m='242970'>input</span> <span
  m='243450'>continuous</span> <span m='244020'>time</span> <span
  m='244290'>function,</span> <span m='244980'>which</span> <span
  m='245340'>is</span> <span m='245670'>of</span> <span m='245820'>some</span>
  <span m='246060'>general</span> <span m='246450'>form,</span> <span
  m='247620'>with</span> <span m='248040'>a</span> <span
  m='248280'>band-limited</span> <span m='249000'>spectrum--</span> <span
  m='249750'>band-limited</span> <span m='250440'>from</span> <span
  m='250620'>minus</span> <span m='251010'>omega</span> <span
  m='251420'>c</span> <span m='251780'>to</span> <span m='251940'>plus</span>
  <span m='252240'>omega</span> <span m='252670'>c.</span> <span
  m='254430'>When</span> <span m='255030'>we</span> <span
  m='255180'>sample</span> <span m='255690'>this</span> <span
  m='256140'>to</span> <span m='256589'>obtain</span> <span
  m='256950'>the</span> <span m='257070'>impulse</span> <span
  m='257550'>train</span> <span m='258180'>with</span> <span m='258329'>a</span>
  <span m='258390'>sampling</span> <span m='258899'>period</span> <span
  m='259290'>of</span> <span m='259470'>capital</span> <span m='259950'>T</span>
  <span m='261000'>the</span> <span m='261329'>associated</span> <span
  m='262380'>spectrum</span> <span m='263400'>is</span> <span
  m='264060'>then</span> <span m='264450'>a</span> <span
  m='264630'>periodic</span> <span m='265920'>replication</span> <span
  m='267000'>of</span> <span m='267420'>this</span> <span
  m='267600'>band-limited</span> <span m='268290'>spectrum.</span> <span
  m='269440'>So</span> <span m='269910'>we</span> <span m='270090'>have</span>
  <span m='270540'>the</span> <span m='270720'>Fourier</span> <span
  m='271140'>transform</span> <span m='271710'>of</span> <span
  m='271800'>x</span> <span m='272020'>of</span> <span m='272120'>a</span> <span
  m='272310'>of</span> <span m='272430'>t.</span> <span m='273480'>Then</span>
  <span m='273930'>the</span> <span m='274020'>same</span> <span
  m='274320'>thing</span> <span m='274560'>reproduce</span> <span
  m='275250'>that</span> <span m='275370'>multiples</span> <span
  m='276090'>of</span> <span m='276180'>2</span> <span m='276390'>pi</span>
  <span m='276900'>over</span> <span m='277170'>capital</span> <span
  m='277565'>T</span> </p><p><span m='278910'>When</span> <span
  m='279120'>we</span> <span m='279240'>then</span> <span
  m='280110'>convert</span> <span m='280500'>this</span> <span
  m='282660'>to</span> <span m='282810'>a</span> <span
  m='282870'>sequence,</span> <span m='284040'>that</span> <span
  m='284580'>implies</span> <span m='285390'>a</span> <span
  m='285630'>frequency</span> <span m='286170'>normalization,</span> <span
  m='287150'>a</span> <span m='287200'>normalization</span> <span
  m='287940'>of</span> <span m='288000'>the</span> <span
  m='288090'>frequency</span> <span m='288660'>axis,</span> <span
  m='289560'>so</span> <span m='289710'>that</span> <span m='289890'>this</span>
  <span m='290130'>periodicity</span> <span m='291120'>gets</span> <span
  m='291360'>converted</span> <span m='291900'>to</span> <span
  m='292320'>a</span> <span m='292560'>periodicity</span> <span
  m='293550'>with</span> <span m='293730'>a</span> <span
  m='293790'>period</span> <span m='294210'>of</span> <span m='294330'>2</span>
  <span m='294570'>pi</span> <span m='295500'>in</span> <span
  m='295680'>the</span> <span m='295770'>digital</span> <span
  m='296100'>frequency</span> <span m='296640'>variable</span> <span
  m='297420'>small</span> <span m='297810'>omega.</span> <span
  m='298920'>Otherwise,</span> <span m='300040'>the</span> <span
  m='300120'>general</span> <span m='300510'>shape</span> <span
  m='300840'>of</span> <span m='300900'>the</span> <span
  m='301020'>Fourier</span> <span m='301380'>transform</span> <span
  m='302010'>stays</span> <span m='302370'>the</span> <span
  m='302460'>same.</span> <span m='303480'>We</span> <span
  m='303600'>then</span> <span m='304320'>go</span> <span m='304470'>back</span>
  <span m='304770'>through</span> <span m='304950'>the</span> <span
  m='305070'>system,</span> <span m='305550'>converting.</span> <span
  m='305970'>Back</span> <span m='306270'>to</span> <span m='306390'>an</span>
  <span m='306480'>impulse</span> <span m='306930'>train</span> <span
  m='308310'>and</span> <span m='309300'>then</span> <span
  m='309540'>finally,</span> <span m='309960'>by</span> <span
  m='310170'>low-pass</span> <span m='310770'>filtering,</span> <span
  m='311610'>we</span> <span m='311760'>extract</span> <span
  m='312690'>just</span> <span m='313260'>the</span> <span m='313950'>one</span>
  <span m='314490'>replication</span> <span m='315450'>of</span> <span
  m='315870'>the</span> <span m='315990'>original</span> <span
  m='316350'>Fourier</span> <span m='316800'>transform.</span> <span
  m='317970'>And</span> <span m='318240'>what</span> <span m='318390'>we</span>
  <span m='318570'>would</span> <span m='318720'>recover</span> <span
  m='319290'>is</span> <span m='319710'>x of</span> <span m='320090'>a</span>
  <span m='320470'>of</span> <span m='320610'>j</span> <span
  m='320850'>omega.</span> <span m='322140'>We</span> <span
  m='322290'>would</span> <span m='322440'>recover</span> <span
  m='322890'>this</span> <span m='323100'>exactly</span> <span
  m='324330'>provided</span> <span m='324930'>that</span> <span
  m='325530'>the</span> <span m='326070'>bandwidth</span> <span
  m='327690'>is</span> <span m='327960'>small</span> <span
  m='328380'>enough</span> <span m='329160'>compared</span> <span
  m='329970'>with</span> <span m='330450'>the</span> <span
  m='330810'>sampling</span> <span m='331410'>frequency.</span> </p><p><span
  m='333030'>If,</span> <span m='333300'>on</span> <span m='333450'>the</span>
  <span m='333570'>other</span> <span m='333750'>hand,</span> <span
  m='334230'>omega</span> <span m='334680'>sub</span> <span m='334965'>c</span>
  <span m='335250'>is</span> <span m='335430'>too</span> <span
  m='335640'>large</span> <span m='336120'>in</span> <span
  m='336210'>relation</span> <span m='336660'>to</span> <span
  m='336750'>the</span> <span m='336870'>sampling</span> <span
  m='337320'>frequency,</span> <span m='338550'>then</span> <span
  m='339150'>what</span> <span m='339360'>we</span> <span m='339750'>end</span>
  <span m='339960'>up</span> <span m='340170'>with</span> <span
  m='340470'>is</span> <span m='340650'>an</span> <span
  m='341280'>interaction</span> <span m='342300'>between</span> <span
  m='342840'>these</span> <span m='343140'>two</span> <span
  m='343380'>pieces</span> <span m='343830'>of</span> <span
  m='343920'>the</span> <span m='344010'>Fourier</span> <span
  m='344460'>transform.</span> <span m='345660'>And</span> <span
  m='345780'>that</span> <span m='346020'>interaction</span> <span
  m='346860'>is</span> <span m='347100'>what's</span> <span
  m='347340'>referred</span> <span m='347700'>to</span> <span
  m='347910'>as</span> <span m='348030'>aliasing.</span> </p><p><span
  m='350100'>The</span> <span m='350190'>effect</span> <span
  m='350640'>aliasing</span> <span m='351510'>is</span> <span
  m='352050'>most</span> <span m='352380'>easily</span> <span
  m='352980'>understood</span> <span m='353700'>in</span> <span
  m='353820'>terms</span> <span m='354360'>of</span> <span m='354870'>a</span>
  <span m='355110'>simple</span> <span m='355500'>example,</span> <span
  m='356310'>namely</span> <span m='356910'>a</span> <span
  m='356970'>sinusoidal</span> <span m='357900'>input.</span> <span
  m='358870'>So</span> <span m='359400'>let's</span> <span
  m='359640'>consider,</span> <span m='360700'>specifically,</span> <span
  m='361380'>what</span> <span m='361560'>happens</span> <span
  m='362220'>with</span> <span m='362460'>the</span> <span
  m='362550'>spectra</span> <span m='363210'>in</span> <span
  m='363390'>the</span> <span m='363480'>case</span> <span m='363990'>of</span>
  <span m='364470'>a</span> <span m='364710'>sinusoidal</span> <span
  m='365490'>input.</span> <span m='367260'>Here,</span> <span
  m='367500'>we</span> <span m='367680'>have</span> <span m='368760'>an</span>
  <span m='368880'>input</span> <span m='369360'>cosine</span> <span
  m='369870'>omega</span> <span m='370250'>0t,</span> <span m='371680'>an</span>
  <span m='371840'>assumed</span> <span m='372240'>sampling</span> <span
  m='372810'>rate</span> <span m='373380'>of</span> <span m='373850'>2</span>
  <span m='374040'>pi</span> <span m='374370'>over</span> <span
  m='374610'>capital</span> <span m='375120'>T.</span> <span
  m='376260'>This</span> <span m='376470'>then</span> <span m='376680'>is</span>
  <span m='376800'>the</span> <span m='376890'>Fourier</span> <span
  m='377340'>transform</span> <span m='378270'>of</span> <span
  m='379260'>this</span> <span m='379710'>sinusoid</span> <span
  m='380760'>or</span> <span m='380880'>cosine.</span> <span
  m='382620'>After</span> <span m='382980'>sampling,</span> <span
  m='384060'>that</span> <span m='384330'>is</span> <span m='384450'>just</span>
  <span m='384630'>simply</span> <span m='384990'>periodically</span> <span
  m='385740'>repeated</span> <span m='386670'>with</span> <span
  m='386790'>a</span> <span m='386850'>period</span> <span
  m='387450'>equal</span> <span m='387810'>to</span> <span m='387990'>the</span>
  <span m='388110'>sampling</span> <span m='388620'>frequency.</span>
  </p><p><span m='390010'>And</span> <span m='390110'>we</span> <span
  m='390180'>see</span> <span m='390930'>that</span> <span m='392700'>if</span>
  <span m='393450'>omega</span> <span m='393950'>0,</span> <span
  m='394800'>the</span> <span m='394950'>input</span> <span
  m='395310'>frequency</span> <span m='396240'>is</span> <span
  m='396480'>low</span> <span m='396780'>enough,</span> <span
  m='398470'>then</span> <span m='399750'>the</span> <span
  m='401970'>original</span> <span m='403380'>spectrum,</span> <span
  m='404430'>or</span> <span m='404550'>Fourier</span> <span
  m='404970'>transform,</span> <span m='406230'>falls</span> <span
  m='406680'>within</span> <span m='407790'>the</span> <span
  m='407880'>passband</span> <span m='408960'>of</span> <span
  m='409260'>the</span> <span m='409350'>low-pass</span> <span
  m='409890'>filter.</span> <span m='410640'>This</span> <span
  m='411090'>dashed</span> <span m='411450'>line</span> <span
  m='411810'>corresponds</span> <span m='412620'>to</span> <span
  m='412770'>the</span> <span m='412860'>frequency</span> <span
  m='413370'>response,</span> <span m='414120'>an</span> <span
  m='414210'>ideal</span> <span m='414630'>frequency</span> <span
  m='415110'>response,</span> <span m='416130'>associated</span> <span
  m='416880'>with</span> <span m='417000'>the D-sampling</span> <span
  m='417810'>low-pass</span> <span m='418350'>filter.</span> <span
  m='419320'>And,</span> <span m='419370'>of</span> <span
  m='419460'>course,</span> <span m='420210'>if</span> <span
  m='421290'>the</span> <span m='421620'>spectral</span> <span
  m='422300'>fall,</span> <span m='422790'>as</span> <span
  m='422970'>I've</span> <span m='423330'>shown</span> <span
  m='423690'>in</span> <span m='423810'>here,</span> <span
  m='424650'>then</span> <span m='425160'>there</span> <span
  m='425370'>is</span> <span m='425520'>no</span> <span
  m='425730'>aliasing.</span> <span m='426440'>In</span> <span
  m='426540'>other</span> <span m='426720'>words,</span> <span
  m='427150'>what</span> <span m='427230'>we</span> <span
  m='427350'>recover</span> <span m='427740'>at</span> <span
  m='427860'>the</span> <span m='427980'>output</span> <span
  m='428340'>of</span> <span m='428430'>the</span> <span
  m='428490'>low-pass</span> <span m='429030'>filter</span> <span
  m='429900'>is</span> <span m='430050'>just</span> <span
  m='430260'>simply</span> <span m='430860'>the</span> <span
  m='431880'>original</span> <span m='432450'>Fourier</span> <span
  m='432900'>transform,</span> <span m='433650'>or</span> <span
  m='433830'>equivalently,</span> <span m='434460'>the</span> <span
  m='434580'>original</span> <span m='435000'>signal.</span> </p><p><span
  m='436470'>Now,</span> <span m='437070'>let's</span> <span
  m='437340'>consider,</span> <span m='438060'>on</span> <span
  m='438210'>the</span> <span m='438330'>other</span> <span
  m='438570'>hand,</span> <span m='440140'>the</span> <span
  m='440190'>effect</span> <span m='440970'>of</span> <span
  m='441330'>increasing</span> <span m='442500'>omega</span> <span
  m='442850'>0,</span> <span m='443670'>the</span> <span m='443940'>input</span>
  <span m='444330'>frequency,</span> <span m='445830'>and</span> <span
  m='446370'>we</span> <span m='446550'>can</span> <span m='446700'>think</span>
  <span m='447120'>in</span> <span m='447270'>particular</span> <span
  m='447750'>of</span> <span m='448230'>what</span> <span m='450180'>the</span>
  <span m='450330'>effect</span> <span m='450780'>is</span> <span
  m='451380'>on</span> <span m='451950'>each</span> <span m='452250'>one</span>
  <span m='452490'>of</span> <span m='452580'>these</span> <span
  m='452820'>impulses</span> <span m='454110'>in</span> <span
  m='454290'>the</span> <span m='454390'>Fourier</span> <span
  m='454800'>transform.</span> <span m='456150'>As</span> <span
  m='456330'>omega</span> <span m='456740'>0</span> <span
  m='457110'>increases,</span> <span m='458280'>this</span> <span
  m='458520'>impulse</span> <span m='458970'>moves</span> <span
  m='459300'>to</span> <span m='459390'>the</span> <span
  m='459510'>right,</span> <span m='460350'>this</span> <span
  m='460560'>impulse</span> <span m='461040'>moves</span> <span
  m='461310'>to</span> <span m='461400'>the</span> <span m='461520'>left.</span>
  <span m='463000'>And</span> <span m='463080'>likewise,</span> <span
  m='463650'>in</span> <span m='463740'>the</span> <span
  m='463830'>periodic</span> <span m='464970'>replications,</span> <span
  m='466230'>this</span> <span m='466440'>impulse</span> <span
  m='466920'>moves</span> <span m='467220'>down</span> <span
  m='467550'>in</span> <span m='467640'>frequency.</span> <span
  m='468750'>This</span> <span m='468930'>impulse</span> <span
  m='469380'>moves</span> <span m='469620'>up</span> <span m='469770'>in</span>
  <span m='469890'>frequency,</span> <span m='470430'>etc.</span> </p><p><span
  m='471960'>Now,</span> <span m='472830'>if</span> <span
  m='473280'>omega</span> <span m='473760'>sub</span> <span m='474150'>s</span>
  <span m='474540'>minus</span> <span m='474960'>omega</span> <span
  m='475360'>0</span> <span m='476610'>is</span> <span m='476760'>greater</span>
  <span m='477210'>than</span> <span m='477360'>omega</span> <span
  m='477750'>0,</span> <span m='478740'>then</span> <span
  m='478920'>these</span> <span m='479130'>two</span> <span
  m='479310'>impulses</span> <span m='479970'>haven't</span> <span
  m='480270'>crossed.</span> <span m='481530'>However,</span> <span
  m='482610'>if</span> <span m='483960'>omega</span> <span m='484320'>sub
  s</span> <span m='484680'>minus</span> <span m='485100'>omega</span> <span
  m='485460'>0</span> <span m='485970'>is</span> <span m='486180'>less</span>
  <span m='486600'>than</span> <span m='486750'>omega</span> <span
  m='487140'>0,</span> <span m='488190'>then</span> <span m='488310'>the</span>
  <span m='488400'>situation</span> <span m='489090'>that</span> <span
  m='489210'>we</span> <span m='489390'>have</span> <span m='489990'>is</span>
  <span m='490500'>what</span> <span m='491040'>I've</span> <span
  m='491280'>illustrated</span> <span m='491880'>here,</span> <span
  m='493250'>where</span> <span m='493430'>now,</span> <span
  m='494340'>the</span> <span m='494520'>impulses</span> <span
  m='495300'>that</span> <span m='495480'>lie</span> <span m='495930'>in</span>
  <span m='496080'>the</span> <span m='496140'>passband</span> <span
  m='496800'>of</span> <span m='496890'>the</span> <span
  m='496980'>filter</span> <span m='498120'>are</span> <span
  m='498540'>at</span> <span m='498780'>the</span> <span
  m='498900'>frequency</span> <span m='499710'>omega</span> <span
  m='500130'>sub</span> <span m='500475'>s</span> <span m='500820'>minus</span>
  <span m='501240'>omega</span> <span m='501640'>0</span> <span
  m='502620'>rather</span> <span m='503070'>than</span> <span
  m='503400'>at</span> <span m='503580'>the</span> <span
  m='503670'>frequency</span> <span m='504210'>omega</span> <span
  m='504530'>0.</span> <span m='505380'>So</span> <span m='505620'>as</span>
  <span m='505830'>we</span> <span m='505950'>think</span> <span
  m='506280'>of</span> <span m='506400'>increasing</span> <span
  m='507000'>the</span> <span m='507150'>input</span> <span
  m='507480'>frequency,</span> <span m='509130'>what</span> <span
  m='509310'>happens</span> <span m='510060'>for</span> <span
  m='510270'>a</span> <span m='510330'>while,</span> <span m='510930'>is</span>
  <span m='511080'>that</span> <span m='511230'>the</span> <span
  m='511380'>output</span> <span m='511770'>frequency</span> <span
  m='512280'>will</span> <span m='512400'>correspondingly</span> <span
  m='513330'>increase.</span> </p><p><span m='514409'>But</span> <span
  m='515130'>after</span> <span m='515490'>we've</span> <span
  m='515669'>increased</span> <span m='516150'>omega</span> <span
  m='516520'>0</span> <span m='516929'>past</span> <span m='517380'>this</span>
  <span m='517620'>point,</span> <span m='518490'>then</span> <span
  m='518700'>the</span> <span m='518850'>output</span> <span
  m='519750'>of</span> <span m='520140'>the</span> <span
  m='520230'>low-pass</span> <span m='520799'>filter</span> <span
  m='521760'>will</span> <span m='522240'>decrease</span> <span
  m='522870'>in</span> <span m='522960'>frequency</span> <span
  m='524039'>because</span> <span m='524460'>it's</span> <span
  m='524640'>taken</span> <span m='525000'>on</span> <span m='525150'>the</span>
  <span m='525300'>alias</span> <span m='526560'>of</span> <span
  m='526860'>a</span> <span m='527160'>new</span> <span
  m='527460'>frequency</span> <span m='528160'>or</span> <span
  m='528330'>a</span> <span m='528390'>new</span> <span
  m='528540'>sinusoid.</span> <span m='529560'>And</span> <span
  m='530010'>so</span> <span m='530220'>the</span> <span
  m='530370'>output,</span> <span m='530730'>in,</span> <span
  m='530820'>that</span> <span m='531030'>case</span> <span m='531450'>is</span>
  <span m='531570'>cosine</span> <span m='532110'>omega</span> <span
  m='532510'>sub s</span> <span m='532890'>minus</span> <span
  m='533220'>omega</span> <span m='533590'>0.</span> <span m='534510'>And</span>
  <span m='534630'>there's</span> <span m='534840'>a</span> <span
  m='534870'>little</span> <span m='535210'>t</span> <span
  m='535800'>over</span> <span m='536070'>here.</span> </p><p><span
  m='537960'>There</span> <span m='538140'>is--</span> <span m='538590'>I</span>
  <span m='539080'>want</span> <span m='539340'>to</span> <span
  m='539400'>demonstrate</span> <span m='539970'>this</span> <span
  m='540180'>effect.</span> <span m='540600'>There</span> <span
  m='540990'>is</span> <span m='541200'>another</span> <span
  m='541560'>effect</span> <span m='542130'>that</span> <span
  m='542520'>we'll</span> <span m='542760'>observe</span> <span
  m='544550'>in</span> <span m='544740'>the</span> <span
  m='544830'>process</span> <span m='545310'>of</span> <span
  m='545400'>demonstrating</span> <span m='546150'>this,</span> <span
  m='546690'>because</span> <span m='547080'>of</span> <span
  m='547170'>the</span> <span m='547290'>fact</span> <span
  m='547860'>that</span> <span m='548280'>in</span> <span m='548520'>any</span>
  <span m='549030'>real-world</span> <span m='549630'>situation,</span> <span
  m='550500'>in</span> <span m='550620'>fact,</span> <span
  m='550950'>this</span> <span m='551100'>low-pass</span> <span
  m='551640'>filter</span> <span m='552150'>is</span> <span
  m='552330'>not</span> <span m='552540'>going</span> <span m='552810'>to</span>
  <span m='552930'>be</span> <span m='553350'>an</span> <span
  m='553470'>ideal</span> <span m='553920'>low-pass</span> <span
  m='554460'>filter,</span> <span m='555030'>as</span> <span
  m='555180'>I've</span> <span m='555330'>shown</span> <span
  m='555660'>here</span> <span m='556660'>but</span> <span m='556710'>in</span>
  <span m='556830'>fact,</span> <span m='557220'>is</span> <span
  m='557400'>going</span> <span m='557670'>to</span> <span
  m='557790'>have</span> <span m='558600'>some</span> <span
  m='559380'>transition</span> <span m='560340'>with</span> <span
  m='560610'>associated</span> <span m='561390'>with</span> <span
  m='561600'>it.</span> <span m='562220'>And</span> <span m='562320'>so</span>
  <span m='562680'>as</span> <span m='562980'>omega</span> <span
  m='563380'>0</span> <span m='564350'>and</span> <span m='564480'>omega</span>
  <span m='564830'>sub s</span> <span m='565170'>minus</span> <span
  m='565560'>omega</span> <span m='565930'>0</span> <span m='566940'>get</span>
  <span m='567120'>very</span> <span m='567450'>close</span> <span
  m='567870'>in</span> <span m='567960'>frequency,</span> <span
  m='569160'>in</span> <span m='569310'>essence,</span> <span
  m='569910'>both</span> <span m='570330'>of</span> <span m='570480'>them</span>
  <span m='570990'>are</span> <span m='571170'>having</span> <span
  m='571530'>some</span> <span m='571890'>influence</span> <span
  m='572460'>on</span> <span m='572580'>the</span> <span
  m='572730'>output</span> <span m='573480'>because</span> <span
  m='573900'>of</span> <span m='574650'>the</span> <span m='574770'>fact</span>
  <span m='575550'>that</span> <span m='576030'>there</span> <span
  m='576240'>isn't</span> <span m='576690'>infinite</span> <span
  m='577140'>attenuation</span> <span m='578160'>of</span> <span
  m='578640'>one</span> <span m='578850'>of</span> <span m='578940'>the</span>
  <span m='579090'>impulses</span> <span m='579940'>an</span> <span
  m='580050'>exact</span> <span m='580740'>replication</span> <span
  m='581460'>of</span> <span m='581550'>the</span> <span
  m='581700'>other.</span> <span m='582390'>So</span> <span
  m='582630'>what</span> <span m='582780'>we'll</span> <span
  m='582870'>see</span> <span m='583080'>in</span> <span m='583170'>that</span>
  <span m='583350'>case,</span> <span m='583860'>as</span> <span
  m='584070'>we</span> <span m='584220'>get</span> <span m='584970'>an</span>
  <span m='585090'>input</span> <span m='585420'>frequency</span> <span
  m='586110'>which</span> <span m='586290'>is</span> <span
  m='586410'>close</span> <span m='586710'>to</span> <span
  m='586830'>half</span> <span m='587160'>the</span> <span
  m='587280'>sampling</span> <span m='587730'>frequency,</span> <span
  m='588800'>will</span> <span m='589010'>see,</span> <span m='589410'>in</span>
  <span m='589530'>addition</span> <span m='590370'>to</span> <span
  m='590940'>the</span> <span m='591090'>effective</span> <span
  m='591540'>aliasing</span> <span m='592020'>that</span> <span
  m='592110'>we</span> <span m='592260'>want</span> <span m='592440'>to</span>
  <span m='592500'>demonstrate,</span> <span m='593640'>we'll</span> <span
  m='593760'>see</span> <span m='594390'>an</span> <span
  m='594510'>effect</span> <span m='594990'>which,</span> <span
  m='595320'>essentially,</span> <span m='595920'>is</span> <span
  m='596040'>a</span> <span m='596100'>beating</span> <span
  m='596430'>phenomenon.</span> </p><p><span m='597630'>So</span> <span
  m='598080'>let's</span> <span m='599040'>move</span> <span
  m='599280'>over</span> <span m='599520'>to</span> <span m='599670'>the</span>
  <span m='599760'>digital</span> <span m='600150'>filter</span> <span
  m='600810'>and</span> <span m='601260'>demonstrate</span> <span
  m='602100'>these</span> <span m='602340'>effects,</span> <span
  m='603510'>where</span> <span m='603990'>I</span> <span
  m='604110'>remind</span> <span m='604590'>you</span> <span
  m='605070'>now</span> <span m='605640'>that</span> <span
  m='606390'>this</span> <span m='606630'>filter,</span> <span
  m='607770'>the</span> <span m='608190'>digital</span> <span
  m='608700'>filter</span> <span m='609870'>aspect</span> <span
  m='610470'>of</span> <span m='610620'>it,</span> <span m='611160'>is</span>
  <span m='611310'>just</span> <span m='611490'>simply</span> <span
  m='611880'>an</span> <span m='612000'>identity</span> <span
  m='612510'>system</span> <span m='613110'>so</span> <span
  m='613320'>that</span> <span m='613590'>it</span> <span
  m='613680'>corresponds</span> <span m='614610'>to</span> <span
  m='615090'>sampling,</span> <span m='616410'>and</span> <span
  m='616560'>then</span> <span m='616860'>simply</span> <span
  m='617370'>sampling</span> <span m='617880'>and</span> <span
  m='617970'>low-pass</span> <span m='618450'>filtering.</span> <span
  m='620580'>What</span> <span m='621390'>we</span> <span m='621570'>have</span>
  <span m='622050'>as</span> <span m='622230'>an</span> <span
  m='622350'>input,</span> <span m='623220'>if</span> <span m='623520'>we</span>
  <span m='623760'>look</span> <span m='624090'>at</span> <span
  m='624900'>the</span> <span m='625220'>oscilloscope,</span> <span
  m='626580'>is</span> <span m='627090'>on</span> <span m='627660'>the</span>
  <span m='627810'>upper</span> <span m='628080'>trace,</span> <span
  m='628800'>the</span> <span m='629130'>input</span> <span
  m='629550'>sinusoid,</span> <span m='630570'>on</span> <span
  m='630690'>the</span> <span m='630780'>lower</span> <span
  m='631050'>trace,</span> <span m='631470'>the</span> <span
  m='631620'>output</span> <span m='631990'>sinusoid.</span> <span
  m='633180'>And</span> <span m='633630'>as</span> <span m='633870'>we</span>
  <span m='633990'>see</span> <span m='634230'>it</span> <span
  m='634320'>right</span> <span m='634560'>now,</span> <span
  m='635130'>the</span> <span m='635670'>input</span> <span
  m='636030'>sinusoid</span> <span m='636420'>has</span> <span
  m='636810'>chosen</span> <span m='637260'>to</span> <span m='637380'>be</span>
  <span m='637500'>low</span> <span m='637860'>enough</span> <span
  m='637960'>frequency</span> <span m='638670'>so</span> <span
  m='638850'>that,</span> <span m='639000'>in</span> <span
  m='639090'>fact,</span> <span m='639520'>there</span> <span
  m='639540'>is</span> <span m='639690'>no</span> <span
  m='639840'>aliasing.</span> </p><p><span m='641310'>Well,</span> <span
  m='642210'>let's</span> <span m='642720'>now</span> <span
  m='643200'>increase</span> <span m='643740'>the</span> <span
  m='643860'>input</span> <span m='644220'>frequency.</span> <span
  m='646330'>And</span> <span m='647520'>what</span> <span
  m='647760'>we'll</span> <span m='647940'>observe</span> <span
  m='648450'>is</span> <span m='648570'>that</span> <span m='648690'>the</span>
  <span m='648840'>output</span> <span m='649200'>frequency</span> <span
  m='650010'>increases</span> <span m='651180'>likewise.</span> <span
  m='652380'>The</span> <span m='652500'>output</span> <span
  m='652800'>frequency</span> <span m='653280'>is</span> <span
  m='653340'>still</span> <span m='653790'>equal</span> <span
  m='654120'>to</span> <span m='654240'>the</span> <span m='654360'>input</span>
  <span m='654690'>frequency.</span> </p><p><span m='656370'>We're</span> <span
  m='656850'>now</span> <span m='657180'>getting</span> <span
  m='657660'>into</span> <span m='657990'>the</span> <span
  m='658110'>vicinity</span> <span m='658890'>of</span> <span
  m='659130'>half</span> <span m='659400'>the</span> <span
  m='659490'>sampling</span> <span m='660000'>frequency</span> <span
  m='660790'>so</span> <span m='660900'>that</span> <span m='661440'>what</span>
  <span m='661650'>we're</span> <span m='661800'>beginning</span> <span
  m='662190'>to</span> <span m='662310'>see</span> <span m='662580'>now</span>
  <span m='662910'>in</span> <span m='663000'>the</span> <span
  m='663120'>output</span> <span m='663660'>is</span> <span
  m='663840'>not</span> <span m='664110'>just</span> <span m='664360'>a</span>
  <span m='664440'>sinusoidal</span> <span m='665190'>output.</span> <span
  m='666090'>But</span> <span m='666390'>in</span> <span m='666540'>fact,</span>
  <span m='667270'>what</span> <span m='667470'>we</span> <span
  m='667620'>see</span> <span m='668280'>are</span> <span m='668640'>the</span>
  <span m='668790'>two</span> <span m='669000'>components.</span> <span
  m='669910'>In</span> <span m='670010'>other</span> <span
  m='670080'>words,</span> <span m='670420'>we</span> <span
  m='670440'>see</span> <span m='670640'>the</span> <span
  m='670790'>beating</span> <span m='671170'>effect</span> <span
  m='672300'>due</span> <span m='672510'>to</span> <span m='672660'>the</span>
  <span m='672780'>fact</span> <span m='673530'>that</span> <span
  m='674100'>the</span> <span m='674310'>low-pass</span> <span
  m='674850'>filter</span> <span m='675420'>is</span> <span
  m='675570'>not</span> <span m='675900'>an</span> <span m='676020'>ideal</span>
  <span m='676410'>low-pass</span> <span m='676950'>filter.</span> </p><p><span
  m='678490'>Now</span> <span m='678810'>what</span> <span m='679020'>we</span>
  <span m='679140'>want</span> <span m='679320'>to</span> <span
  m='679440'>observe</span> <span m='680160'>as</span> <span
  m='681180'>we</span> <span m='681750'>sweep</span> <span
  m='682830'>past</span> <span m='683370'>half</span> <span
  m='683670'>the</span> <span m='683760'>sampling</span> <span
  m='684270'>frequency</span> <span m='685590'>is</span> <span
  m='686340'>the</span> <span m='686550'>aliasing</span> <span
  m='687120'>effect--</span> <span m='687610'>in</span> <span
  m='687710'>other</span> <span m='687780'>words,</span> <span
  m='688090'>the</span> <span m='688110'>fact</span> <span
  m='688440'>that</span> <span m='688650'>the</span> <span
  m='689220'>output</span> <span m='689610'>sinusoid</span> <span
  m='690240'>will</span> <span m='690360'>decrease</span> <span
  m='690870'>in</span> <span m='690990'>frequency.</span> <span
  m='692070'>Let's</span> <span m='692310'>first</span> <span
  m='692670'>sweep</span> <span m='693420'>back</span> <span
  m='693710'>down</span> <span m='693990'>to</span> <span m='694140'>DC.</span>
  <span m='695850'>So</span> <span m='696390'>the</span> <span
  m='696540'>output</span> <span m='696900'>sinusoid</span> <span
  m='697440'>follows</span> <span m='697860'>the</span> <span
  m='697980'>input</span> <span m='698310'>sinusoid.</span> <span
  m='699810'>And</span> <span m='699930'>then</span> <span
  m='700620'>we'll</span> <span m='700890'>sweep</span> <span
  m='701580'>automatically</span> <span m='702930'>from</span> <span
  m='703200'>0</span> <span m='703900'>up</span> <span m='704250'>to</span>
  <span m='704730'>the</span> <span m='704820'>sampling</span> <span
  m='705330'>frequency.</span> <span m='706660'>And</span> <span
  m='707070'>let's</span> <span m='707310'>see</span> <span
  m='707520'>that.</span> </p><p><span m='708740'>So</span> <span
  m='709150'>on</span> <span m='709320'>the</span> <span
  m='709410'>bottom</span> <span m='709710'>trace</span> <span
  m='710060'>is</span> <span m='710190'>the</span> <span
  m='710340'>output</span> <span m='710700'>sinusoid.</span> <span
  m='711390'>The</span> <span m='711510'>top</span> <span m='711780'>trace
  is</span> <span m='712230'>the</span> <span m='712320'>input</span> <span
  m='712680'>sinusoid.</span> <span m='713450'>Were</span> <span
  m='713580'>now</span> <span m='713850'>in</span> <span m='713910'>the</span>
  <span m='714000'>vicinity</span> <span m='714480'>of</span> <span
  m='714570'>half</span> <span m='714840'>the</span> <span
  m='714930'>sampling</span> <span m='715410'>frequency.</span> <span
  m='716190'>We're</span> <span m='716310'>now</span> <span
  m='716490'>past</span> <span m='716910'>half</span> <span
  m='717150'>the</span> <span m='717240'>sampling</span> <span
  m='717720'>frequency.</span> <span m='718800'>And</span> <span
  m='718890'>you</span> <span m='718980'>see</span> <span m='719250'>that</span>
  <span m='719430'>the</span> <span m='719580'>output</span> <span
  m='720450'>is</span> <span m='720600'>decreasing</span> <span
  m='721230'>in</span> <span m='721320'>frequency</span> <span
  m='721830'>while</span> <span m='722010'>the</span> <span
  m='722130'>input</span> <span m='722460'>was</span> <span
  m='722640'>increasing.</span> </p><p><span m='724390'>Let's</span> <span
  m='724860'>finally</span> <span m='725910'>look</span> <span
  m='726120'>at</span> <span m='726210'>that</span> <span
  m='726420'>again.</span> <span m='727330'>But</span> <span
  m='727680'>this</span> <span m='727920'>time,</span> <span
  m='728730'>let's</span> <span m='728880'>also</span> <span
  m='729240'>listen</span> <span m='729630'>to</span> <span
  m='729750'>the</span> <span m='729900'>output</span> <span
  m='730260'>sinusoid.</span> <span m='731430'>And</span> <span
  m='731880'>what</span> <span m='732120'>you'll</span> <span
  m='732360'>hear,</span> <span m='732720'>in</span> <span
  m='732810'>addition</span> <span m='733200'>to</span> <span
  m='733320'>observing</span> <span m='733800'>this</span> <span
  m='734010'>on</span> <span m='734130'>the</span> <span
  m='734220'>bottom</span> <span m='734520'>trace</span> <span
  m='734850'>of</span> <span m='734940'>the</span> <span
  m='735030'>scope,</span> <span m='735870'>is</span> <span
  m='736320'>the</span> <span m='736440'>fact</span> <span
  m='737040'>that</span> <span m='737490'>the</span> <span
  m='737970'>output</span> <span m='738360'>frequency</span> <span
  m='739110'>first</span> <span m='739500'>increases,</span> <span
  m='740310'>and</span> <span m='740460'>then</span> <span
  m='740640'>decreases,</span> <span m='741720'>even</span> <span
  m='741990'>though</span> <span m='742200'>the</span> <span
  m='742320'>input</span> <span m='742700'>frequency</span> <span
  m='743670'>is</span> <span m='743850'>continuing</span> <span
  m='744480'>to</span> <span m='744570'>increase.</span> <span
  m='745570'>So</span> <span m='745620'>let's</span> <span m='745860'>do</span>
  <span m='745950'>that</span> <span m='746160'>again.</span> <span
  m='746430'>But</span> <span m='746550'>now,</span> <span m='746940'>in</span>
  <span m='747030'>this</span> <span m='747180'>case,</span> <span
  m='747480'>let's</span> <span m='747690'>listen</span> <span
  m='748020'>to</span> <span m='748140'>the</span> <span
  m='748260'>output.</span> </p><p><span m='748650'>[SOUND WAVES RISE AND
  LOWER]</span> </p><p></p><p><span m='761610'>OK,</span> <span
  m='762210'>now</span> <span m='763170'>what</span> <span m='763350'>we</span>
  <span m='763920'>would</span> <span m='764370'>now</span> <span
  m='764610'>like</span> <span m='764850'>to</span> <span
  m='764970'>consider</span> <span m='765690'>is</span> <span
  m='766380'>the</span> <span m='766530'>effect</span> <span
  m='767070'>of</span> <span m='768090'>actually</span> <span
  m='768630'>carrying</span> <span m='769050'>out</span> <span
  m='769200'>some</span> <span m='769350'>digital</span> <span
  m='769740'>filtering</span> <span m='770120'>in-between</span> <span
  m='771360'>the</span> <span m='771660'>sampling</span> <span
  m='772410'>and</span> <span m='772590'>D-sampling.</span> <span
  m='774430'>And</span> <span m='775350'>so</span> <span m='776160'>let</span>
  <span m='776340'>me</span> <span m='776790'>return</span> <span
  m='777360'>to</span> <span m='778440'>the</span> <span m='779250'>basic</span>
  <span m='779670'>system</span> <span m='780510'>again</span> <span
  m='786470'>where</span> <span m='787520'>we</span> <span m='787700'>had</span>
  <span m='787820'>previously</span> <span m='789260'>removed</span> <span
  m='790040'>this</span> <span m='790220'>digital</span> <span
  m='790640'>filter.</span> <span m='791750'>And</span> <span
  m='791900'>now,</span> <span m='792150'>what</span> <span m='792320'>we</span>
  <span m='792440'>want</span> <span m='792620'>to</span> <span
  m='792680'>consider</span> <span m='793400'>is</span> <span
  m='794270'>the</span> <span m='794390'>effect</span> <span
  m='795320'>of</span> <span m='795530'>the</span> <span
  m='795680'>overall</span> <span m='796160'>system,</span> <span
  m='796910'>when</span> <span m='797210'>we,</span> <span m='797330'>in</span>
  <span m='797450'>fact,</span> <span m='798080'>insert</span> <span
  m='798710'>an</span> <span m='798860'>interesting,</span> <span
  m='799460'>or</span> <span m='799800'>a</span> <span m='799850'>more</span>
  <span m='800150'>interesting,</span> <span m='800660'>digital</span> <span
  m='801020'>filter</span> <span m='801380'>in</span> <span
  m='801470'>the</span> <span m='801560'>middle.</span> </p><p><span
  m='802610'>The</span> <span m='802700'>digital</span> <span
  m='803060'>filter</span> <span m='803810'>that</span> <span
  m='804260'>we're</span> <span m='804440'>going</span> <span
  m='804710'>to</span> <span m='804860'>insert</span> <span m='806390'>is</span>
  <span m='807860'>a</span> <span m='808190'>low-pass</span> <span
  m='808850'>filter.</span> <span m='810680'>And</span> <span
  m='811370'>the</span> <span m='811550'>impulse</span> <span
  m='812000'>response</span> <span m='812540'>of</span> <span
  m='812630'>the</span> <span m='812720'>low-pass</span> <span
  m='813290'>filter,</span> <span m='813740'>or</span> <span
  m='813860'>the</span> <span m='813950'>unit</span> <span
  m='814190'>sample</span> <span m='814610'>response</span> <span
  m='815090'>of</span> <span m='815170'>the</span> <span
  m='815240'>low-pass</span> <span m='815750'>filter,</span> <span
  m='816290'>is,</span> <span m='816680'>as</span> <span m='816860'>I've</span>
  <span m='817010'>shown</span> <span m='817490'>up</span> <span
  m='817730'>here.</span> <span m='818660'>And</span> <span
  m='819260'>it's</span> <span m='819470'>a</span> <span
  m='819530'>symmetric</span> <span m='820550'>unit</span> <span
  m='820820'>sample</span> <span m='821240'>response.</span> <span
  m='822380'>And</span> <span m='822500'>consequently,</span> <span
  m='823370'>it</span> <span m='823460'>corresponds</span> <span
  m='824150'>to</span> <span m='824270'>a</span> <span m='824330'>linear</span>
  <span m='824660'>phase</span> <span m='825050'>filter.</span> </p><p><span
  m='826730'>The</span> <span m='826820'>associated</span> <span
  m='827480'>frequency</span> <span m='828020'>response</span> <span
  m='828740'>I</span> <span m='828890'>show</span> <span m='829200'>down</span>
  <span m='829490'>here,</span> <span m='830420'>where</span> <span
  m='830990'>this</span> <span m='831260'>is</span> <span m='831410'>now</span>
  <span m='831620'>the</span> <span m='831710'>filter</span> <span
  m='832070'>passband.</span> <span m='833420'>This</span> <span
  m='833660'>is</span> <span m='833750'>the</span> <span
  m='833870'>filter</span> <span m='834230'>stop</span> <span
  m='834640'>band.</span> <span m='835010'>And,</span> <span
  m='835100'>of</span> <span m='835190'>course,</span> <span
  m='835580'>there</span> <span m='835760'>is</span> <span
  m='835880'>some</span> <span m='836720'>ripple.</span> <span
  m='837170'>There</span> <span m='837350'>is</span> <span m='837460'>an</span>
  <span m='837560'>infinite</span> <span m='838010'>attenuation</span> <span
  m='838700'>in</span> <span m='838790'>the</span> <span
  m='838880'>stopband.</span> </p><p><span m='840320'>And</span> <span
  m='841100'>I</span> <span m='841310'>remind</span> <span m='841730'>you</span>
  <span m='841820'>of</span> <span m='841880'>the</span> <span
  m='842000'>fact</span> <span m='842540'>that,</span> <span
  m='842810'>of</span> <span m='842900'>course,</span> <span
  m='843290'>the</span> <span m='843890'>digital</span> <span
  m='844250'>filter</span> <span m='844610'>frequency</span> <span
  m='845150'>response</span> <span m='845750'>must,</span> <span
  m='846440'>by</span> <span m='846620'>necessity,</span> <span
  m='847220'>be</span> <span m='847370'>periodic</span> <span
  m='848480'>with</span> <span m='848630'>a</span> <span
  m='848690'>period</span> <span m='849350'>of</span> <span m='849860'>2</span>
  <span m='850070'>pi.</span> <span m='851720'>The</span> <span
  m='852080'>cutoff</span> <span m='853100'>frequency</span> <span
  m='853760'>associated</span> <span m='854480'>with</span> <span
  m='854810'>the</span> <span m='854930'>particular</span> <span
  m='855410'>filter</span> <span m='855800'>that</span> <span
  m='855920'>we</span> <span m='856070'>want</span> <span m='856250'>to</span>
  <span m='856310'>demonstrate</span> <span m='857480'>is</span> <span
  m='857660'>pi</span> <span m='858230'>over</span> <span m='858560'>5,</span>
  <span m='859610'>or</span> <span m='860180'>one</span> <span
  m='860660'>tenth</span> <span m='861140'>of</span> <span m='861680'>2</span>
  <span m='861870'>pi.</span> <span m='862650'>And</span> <span
  m='863210'>the</span> <span m='863300'>factor</span> <span
  m='863690'>one</span> <span m='864065'>tenth</span> <span m='864440'>is</span>
  <span m='864620'>a</span> <span m='864680'>factor</span> <span
  m='865100'>that</span> <span m='865380'>I'll</span> <span
  m='865550'>want</span> <span m='865760'>to</span> <span
  m='866000'>refer</span> <span m='866390'>to</span> <span
  m='866780'>again</span> <span m='867110'>shortly.</span> </p><p><span
  m='869010'>Now,</span> <span m='869870'>the</span> <span
  m='870020'>overall</span> <span m='870470'>system,</span> <span
  m='871740'>of</span> <span m='871790'>course,</span> <span
  m='872550'>is</span> <span m='872960'>a</span> <span
  m='873110'>continuous</span> <span m='873710'>time</span> <span
  m='874010'>system.</span> <span m='874590'>In</span> <span
  m='874690'>other</span> <span m='874790'>words,</span> <span
  m='875580'>we</span> <span m='875680'>have</span> <span m='875690'>a</span>
  <span m='875750'>continuous</span> <span m='876290'>time</span> <span
  m='876560'>input.</span> <span m='876920'>We</span> <span
  m='877040'>have</span> <span m='877160'>a</span> <span
  m='877190'>continuous</span> <span m='877730'>time</span> <span
  m='878030'>output.</span> <span m='879540'>And</span> <span
  m='880250'>the</span> <span m='880370'>question</span> <span
  m='881090'>then</span> <span m='881360'>is,</span> <span
  m='881940'>what</span> <span m='882080'>is</span> <span m='882320'>the</span>
  <span m='882680'>equivalent</span> <span m='883340'>continuous</span> <span
  m='884030'>time</span> <span m='884480'>system</span> <span
  m='885260'>in</span> <span m='885380'>relation</span> <span
  m='886490'>to</span> <span m='887060'>the</span> <span
  m='887270'>digital</span> <span m='887720'>filter</span> <span
  m='888740'>frequency</span> <span m='889250'>response</span> <span
  m='889820'>that</span> <span m='889910'>we</span> <span m='890030'>have</span>
  <span m='890210'>illustrated</span> <span m='890810'>here?</span> <span
  m='891240'>In</span> <span m='891260'>other</span> <span
  m='891440'>words,</span> <span m='892170'>what</span> <span
  m='892250'>is</span> <span m='892460'>the</span> <span
  m='892670'>equivalent</span> <span m='893150'>frequency</span> <span
  m='893720'>response</span> <span m='894470'>of</span> <span
  m='895250'>the</span> <span m='895940'>corresponding</span> <span
  m='896750'>continuous</span> <span m='897290'>time</span> <span
  m='897560'>system?</span> </p><p><span m='899450'>We</span> <span
  m='899570'>can</span> <span m='899750'>answer</span> <span
  m='900110'>that</span> <span m='900740'>by</span> <span
  m='901790'>simply</span> <span m='902270'>referring</span> <span
  m='903320'>to</span> <span m='903770'>the</span> <span m='903890'>basic</span>
  <span m='904310'>definition</span> <span m='905240'>of</span> <span
  m='905390'>frequency</span> <span m='905960'>response</span> <span
  m='907040'>for</span> <span m='907160'>the</span> <span
  m='907280'>continuous</span> <span m='907820'>time</span> <span
  m='908150'>case</span> <span m='908700'>and</span> <span
  m='908800'>frequency</span> <span m='909170'>response</span> <span
  m='909710'>for</span> <span m='909830'>the</span> <span
  m='909920'>discrete</span> <span m='910310'>time</span> <span
  m='910670'>case.</span> <span m='913070'>In</span> <span m='913160'>the</span>
  <span m='913250'>continuous</span> <span m='913850'>time</span> <span
  m='914180'>case,</span> <span m='916100'>for</span> <span m='916280'>a</span>
  <span m='916310'>linear</span> <span m='916640'>time</span> <span
  m='916970'>invariant</span> <span m='917450'>filter,</span> <span
  m='918290'>the</span> <span m='918380'>frequency</span> <span
  m='918950'>response</span> <span m='920180'>is</span> <span
  m='920360'>defined</span> <span m='921170'>as</span> <span
  m='922220'>the</span> <span m='922550'>gain</span> <span
  m='922940'>change</span> <span m='923720'>applied</span> <span
  m='924230'>to</span> <span m='924410'>a</span> <span m='924470'>complex</span>
  <span m='925040'>exponential.</span> <span m='926210'>So</span> <span
  m='926420'>if</span> <span m='926510'>we</span> <span
  m='926630'>consider</span> <span m='927020'>a</span> <span
  m='927080'>complex</span> <span m='927650'>exponential</span> <span
  m='928310'>as</span> <span m='928430'>the</span> <span
  m='928550'>input,</span> <span m='930300'>then</span> <span
  m='930890'>the</span> <span m='931070'>output</span> <span
  m='931460'>of</span> <span m='931550'>the</span> <span
  m='931640'>system</span> <span m='932330'>is</span> <span m='932480'>a</span>
  <span m='932540'>complex</span> <span m='933110'>exponential</span> <span
  m='933980'>at</span> <span m='934100'>the</span> <span m='934220'>same</span>
  <span m='934490'>complex</span> <span m='935030'>frequency,</span> <span
  m='936530'>but</span> <span m='937010'>with</span> <span m='937580'>an</span>
  <span m='937700'>amplitude,</span> <span m='939000'>which</span> <span
  m='939380'>is</span> <span m='939920'>equal</span> <span m='940280'>to</span>
  <span m='940430'>the</span> <span m='940520'>frequency</span> <span
  m='941090'>response</span> <span m='941570'>of</span> <span
  m='941660'>the</span> <span m='941750'>system</span> <span
  m='942440'>at</span> <span m='942650'>that</span> <span
  m='942890'>frequency.</span> </p><p><span m='944960'>Likewise,</span> <span
  m='945590'>for</span> <span m='945770'>a</span> <span
  m='945800'>discrete</span> <span m='946250'>time</span> <span
  m='946910'>system,</span> <span m='948350'>we</span> <span
  m='948500'>can</span> <span m='948710'>consider</span> <span
  m='949370'>a</span> <span m='949490'>complex</span> <span
  m='950060'>exponential</span> <span m='950750'>input</span> <span
  m='951170'>at</span> <span m='951290'>a</span> <span
  m='951350'>frequency</span> <span m='952010'>small</span> <span
  m='952430'>omega.</span> <span m='953600'>And</span> <span
  m='953750'>the</span> <span m='953870'>output</span> <span
  m='954500'>is</span> <span m='955520'>a</span> <span m='955670'>complex</span>
  <span m='956210'>exponential</span> <span m='957080'>at</span> <span
  m='957230'>the</span> <span m='957320'>same</span> <span
  m='957650'>complex</span> <span m='958190'>frequency,</span> <span
  m='959290'>with</span> <span m='959930'>an</span> <span
  m='960020'>amplitude</span> <span m='960590'>change,</span> <span
  m='961220'>which</span> <span m='961580'>is</span> <span m='962390'>the</span>
  <span m='962750'>frequency</span> <span m='963350'>response</span> <span
  m='964280'>of</span> <span m='964430'>the</span> <span
  m='964520'>digital</span> <span m='964970'>filter,</span> <span
  m='965480'>or</span> <span m='965600'>discrete</span> <span
  m='965980'>time</span> <span m='966290'>filter,</span> <span
  m='967130'>again</span> <span m='967670'>evaluated</span> <span
  m='968450'>at</span> <span m='968510'>that</span> <span
  m='968720'>frequency.</span> <span m='970620'>Well,</span> <span
  m='971000'>simply</span> <span m='971450'>from</span> <span
  m='971690'>these</span> <span m='971900'>definitions,</span> <span
  m='973340'>we</span> <span m='973460'>can</span> <span m='973610'>trace</span>
  <span m='973970'>our</span> <span m='974090'>way</span> <span
  m='974330'>through</span> <span m='974570'>the</span> <span
  m='974690'>system</span> <span m='975500'>and</span> <span
  m='976280'>see</span> <span m='976610'>fairly</span> <span
  m='977000'>easily</span> <span m='977810'>what</span> <span
  m='978320'>the</span> <span m='978710'>equivalent</span> <span
  m='980090'>analog,</span> <span m='980810'>or</span> <span
  m='980930'>continuous</span> <span m='981560'>time</span> <span
  m='982160'>filter</span> <span m='982550'>frequency,</span> <span
  m='983090'>response</span> <span m='983660'>is.</span> </p><p><span
  m='985910'>Let's</span> <span m='986120'>consider</span> <span
  m='986960'>the</span> <span m='987080'>overall</span> <span
  m='987530'>system.</span> <span m='989240'>And</span> <span
  m='989390'>let's</span> <span m='989600'>choose</span> <span
  m='990170'>an</span> <span m='990290'>input,</span> <span
  m='990990'>which</span> <span m='991100'>is</span> <span m='991190'>a</span>
  <span m='991250'>complex</span> <span m='991820'>exponential.</span> <span
  m='993590'>And</span> <span m='994220'>we'll</span> <span
  m='994520'>choose</span> <span m='994820'>the</span> <span
  m='994910'>complex</span> <span m='995450'>exponential</span> <span
  m='996140'>carefully</span> <span m='996800'>to</span> <span
  m='996980'>avoid</span> <span m='997340'>aliasing.</span> </p><p><span
  m='999620'>We then</span> <span m='1000220'>sample</span> <span
  m='1001090'>this</span> <span m='1001270'>complex</span> <span
  m='1001810'>exponential</span> <span m='1002770'>and</span> <span
  m='1002890'>convert</span> <span m='1003280'>that</span> <span
  m='1003490'>to</span> <span m='1003640'>a</span> <span
  m='1003700'>sequence.</span> <span m='1004870'>And</span> <span
  m='1004960'>the</span> <span m='1005050'>sequence</span> <span
  m='1005530'>values</span> <span m='1006250'>are</span> <span
  m='1006640'>there</span> <span m='1006810'>for</span> <span
  m='1007180'>e</span> <span m='1007420'>to</span> <span m='1007480'>the</span>
  <span m='1007570'>j</span> <span m='1007810'>omega</span> <span
  m='1008260'>and</span> <span m='1008720'>capital</span> <span
  m='1009095'>T.</span> <span m='1010180'>Well,</span> <span
  m='1010630'>this</span> <span m='1010840'>is</span> <span
  m='1010990'>just</span> <span m='1011230'>the</span> <span
  m='1011350'>discrete</span> <span m='1011770'>time</span> <span
  m='1012100'>complex</span> <span m='1012730'>exponential</span> <span
  m='1014200'>with</span> <span m='1014350'>a</span> <span
  m='1014410'>frequency</span> <span m='1015040'>of</span> <span
  m='1015160'>capital</span> <span m='1015640'>omega</span> <span
  m='1016180'>times</span> <span m='1016510'>capital</span> <span
  m='1016950'>T.</span> <span m='1018190'>So</span> <span m='1019000'>the</span>
  <span m='1019180'>output</span> <span m='1019690'>of</span> <span
  m='1019780'>the</span> <span m='1019870'>digital</span> <span
  m='1020290'>filter</span> <span m='1021400'>is</span> <span
  m='1021640'>a</span> <span m='1021700'>complex</span> <span
  m='1022270'>exponential</span> <span m='1022990'>with</span> <span
  m='1023140'>the</span> <span m='1023230'>same</span> <span
  m='1023650'>complex</span> <span m='1024250'>frequency,</span> <span
  m='1024880'>capital</span> <span m='1025329'>omega</span> <span
  m='1025780'>times</span> <span m='1026050'>capital</span> <span
  m='1026410'>T,</span> <span m='1027609'>with</span> <span
  m='1027760'>an</span> <span m='1027849'>amplitude,</span> <span
  m='1028910'>which</span> <span m='1029170'>is</span> <span
  m='1029829'>the</span> <span m='1029950'>frequency</span> <span
  m='1030520'>response</span> <span m='1031089'>of</span> <span
  m='1031180'>this</span> <span m='1031359'>filter</span> <span
  m='1032410'>evaluated</span> <span m='1033400'>at</span> <span
  m='1033609'>the</span> <span m='1033700'>frequency</span> <span
  m='1034569'>of</span> <span m='1034750'>the</span> <span
  m='1034900'>input--</span> <span m='1035780'>In</span> <span
  m='1035800'>other</span> <span m='1036010'>words,</span> <span
  m='1036310'>evaluated</span> <span m='1037000'>at</span> <span
  m='1037060'>capital</span> <span m='1037510'>omega</span> <span
  m='1037869'>times</span> <span m='1038200'>capital</span> <span
  m='1038599'>T.</span> </p><p><span m='1040450'>Then</span> <span
  m='1040869'>we</span> <span m='1041050'>convert</span> <span
  m='1041440'>that</span> <span m='1041710'>back</span> <span
  m='1041980'>to</span> <span m='1042099'>an</span> <span
  m='1042190'>impulse</span> <span m='1042640'>train,</span> <span
  m='1043300'>and</span> <span m='1043420'>finally,</span> <span
  m='1044349'>low-pass</span> <span m='1044920'>filter.</span> <span
  m='1045550'>And</span> <span m='1045730'>the</span> <span
  m='1045849'>output</span> <span m='1046180'>of</span> <span
  m='1046270'>the</span> <span m='1046329'>low-pass</span> <span
  m='1046869'>filter</span> <span m='1047990'>then</span> <span
  m='1048220'>has</span> <span m='1048520'>the</span> <span
  m='1048650'>same</span> <span m='1049060'>amplitude,</span> <span
  m='1050380'>but</span> <span m='1053530'>now</span> <span
  m='1054070'>multiplying</span> <span m='1055000'>a</span> <span
  m='1055150'>continuous</span> <span m='1055750'>time</span> <span
  m='1056440'>complex</span> <span m='1056980'>exponential</span> <span
  m='1057820'>at</span> <span m='1057970'>the</span> <span
  m='1058060'>original</span> <span m='1058480'>input</span> <span
  m='1058780'>frequency.</span> <span m='1059890'>So</span> <span
  m='1060250'>simply</span> <span m='1060670'>from</span> <span
  m='1060880'>the</span> <span m='1060970'>definition</span> <span
  m='1061750'>comparing</span> <span m='1062320'>this</span> <span
  m='1063160'>to</span> <span m='1063280'>the</span> <span
  m='1063460'>input</span> <span m='1064480'>from</span> <span
  m='1064720'>the</span> <span m='1064810'>definition</span> <span
  m='1065680'>of</span> <span m='1065980'>the</span> <span
  m='1066100'>continuous</span> <span m='1066670'>time</span> <span
  m='1066940'>frequency</span> <span m='1067510'>response,</span> <span
  m='1068800'>the</span> <span m='1069160'>continuous</span> <span
  m='1069760'>time</span> <span m='1070000'>frequency</span> <span
  m='1070570'>response</span> <span m='1071320'>is</span> <span
  m='1071500'>equal</span> <span m='1071770'>to</span> <span
  m='1071920'>this</span> <span m='1072190'>term.</span> <span
  m='1073180'>In</span> <span m='1073300'>other</span> <span
  m='1073510'>words,</span> <span m='1074210'>it's</span> <span
  m='1074530'>the</span> <span m='1074830'>frequency</span> <span
  m='1075430'>response</span> <span m='1076060'>of</span> <span
  m='1076180'>the</span> <span m='1076300'>digital</span> <span
  m='1076690'>filter,</span> <span m='1077860'>but</span> <span
  m='1078610'>with</span> <span m='1079030'>a</span> <span
  m='1079480'>rescaling</span> <span m='1080260'>of</span> <span
  m='1080380'>the</span> <span m='1080470'>frequency</span> <span
  m='1081040'>axis--</span> <span m='1082010'>in</span> <span
  m='1082060'>other</span> <span m='1082270'>words,</span> <span
  m='1082940'>with</span> <span m='1083320'>the</span> <span
  m='1083560'>digital</span> <span m='1083950'>frequency</span> <span
  m='1084490'>variable</span> <span m='1084970'>small</span> <span
  m='1085400'>omega</span> <span m='1086360'>replaced</span> <span
  m='1086810'>by</span> <span m='1086990'>capital</span> <span
  m='1087500'>omega</span> <span m='1087950'>times</span> <span
  m='1088370'>capital</span> <span m='1088800'>T.</span> </p><p><span
  m='1090920'>The</span> <span m='1091040'>consequence</span> <span
  m='1091760'>of</span> <span m='1091880'>that</span> <span
  m='1092450'>for</span> <span m='1092570'>the</span> <span
  m='1093230'>particular</span> <span m='1093800'>digital</span> <span
  m='1094220'>filter</span> <span m='1094760'>that</span> <span
  m='1094880'>we're</span> <span m='1095030'>talking</span> <span
  m='1095480'>about--</span> <span m='1095870'>or,</span> <span
  m='1095960'>in</span> <span m='1096020'>fact,</span> <span
  m='1096720'>for</span> <span m='1097130'>any</span> <span
  m='1097340'>digital</span> <span m='1097730'>filter--</span> <span
  m='1098720'>is</span> <span m='1098930'>that</span> <span
  m='1099560'>the</span> <span m='1099950'>continuous</span> <span
  m='1100640'>time</span> <span m='1101780'>filter</span> <span
  m='1102320'>frequency</span> <span m='1102980'>response</span> <span
  m='1104210'>has</span> <span m='1104390'>the</span> <span
  m='1104510'>same</span> <span m='1104840'>shape</span> <span
  m='1105560'>as</span> <span m='1105800'>the</span> <span
  m='1105920'>digital</span> <span m='1106280'>filter</span> <span
  m='1106640'>frequency</span> <span m='1107210'>response,</span> <span
  m='1108350'>but</span> <span m='1108800'>has</span> <span m='1109250'>a</span>
  <span m='1109430'>rescaled</span> <span m='1110540'>frequency</span> <span
  m='1111110'>axis--</span> <span m='1111980'>rescaled</span> <span
  m='1112640'>according</span> <span m='1113300'>to</span> <span
  m='1113780'>this</span> <span m='1113930'>scaling.</span> <span
  m='1115550'>And</span> <span m='1115700'>in</span> <span
  m='1115820'>essence,</span> <span m='1116550'>what</span> <span
  m='1116630'>the</span> <span m='1116750'>rescaling</span> <span
  m='1117410'>corresponds</span> <span m='1118190'>to--</span> <span
  m='1118430'>and</span> <span m='1118520'>I</span> <span
  m='1119070'>think</span> <span m='1119300'>you</span> <span
  m='1119420'>can</span> <span m='1119600'>verify</span> <span
  m='1120170'>this</span> <span m='1120590'>on</span> <span
  m='1120740'>your</span> <span m='1120920'>own--</span> <span
  m='1122060'>is</span> <span m='1123050'>to</span> <span
  m='1123680'>reconvert</span> <span m='1124760'>or</span> <span
  m='1124940'>rescale</span> <span m='1126320'>the</span> <span
  m='1126410'>frequency</span> <span m='1127010'>2</span> <span
  m='1127310'>pi</span> <span m='1128450'>in</span> <span
  m='1128570'>small</span> <span m='1129020'>omega</span> <span
  m='1130220'>to</span> <span m='1130940'>the</span> <span
  m='1131210'>sampling</span> <span m='1131840'>frequency</span> <span
  m='1132740'>in</span> <span m='1132890'>large</span> <span
  m='1133250'>omega.</span> <span m='1134510'>And</span> <span
  m='1135620'>the</span> <span m='1136010'>upshot</span> <span
  m='1136550'>of</span> <span m='1136670'>all</span> <span m='1136880'>of</span>
  <span m='1136970'>this,</span> <span m='1137420'>is</span> <span
  m='1137630'>that</span> <span m='1137780'>this</span> <span
  m='1137960'>cutoff</span> <span m='1138440'>frequency,</span> <span
  m='1139470'>which</span> <span m='1139610'>in</span> <span
  m='1139700'>a</span> <span m='1139760'>digital</span> <span
  m='1140120'>filter</span> <span m='1140540'>is</span> <span
  m='1140660'>a</span> <span m='1140720'>pi</span> <span m='1141080'>over</span>
  <span m='1141290'>5,</span> <span m='1142760'>is</span> <span
  m='1142970'>now</span> <span m='1143450'>rescaled</span> <span
  m='1144560'>to</span> <span m='1144710'>pi</span> <span
  m='1145190'>over</span> <span m='1145490'>5</span> <span
  m='1145910'>capital</span> <span m='1146400'>T.</span> </p><p><span
  m='1147320'>And</span> <span m='1147500'>what</span> <span
  m='1147650'>we</span> <span m='1147800'>would</span> <span
  m='1147920'>observe</span> <span m='1148550'>is</span> <span
  m='1148850'>that</span> <span m='1149150'>as</span> <span
  m='1149900'>capital</span> <span m='1150305'>T,</span> <span
  m='1150710'>the</span> <span m='1150800'>sampling</span> <span
  m='1151280'>period</span> <span m='1151670'>changes,</span> <span
  m='1152810'>then</span> <span m='1153410'>the</span> <span
  m='1153620'>bandwidth,</span> <span m='1154640'>or</span> <span
  m='1154790'>the</span> <span m='1154880'>cutoff</span> <span
  m='1155300'>frequency,</span> <span m='1156110'>of</span> <span
  m='1156290'>the</span> <span m='1156380'>continuous</span> <span
  m='1156950'>time</span> <span m='1157430'>filter</span> <span
  m='1158090'>changes</span> <span m='1158570'>also.</span> <span
  m='1159830'>So</span> <span m='1160220'>let</span> <span m='1160400'>me</span>
  <span m='1160520'>remind</span> <span m='1160970'>you</span> <span
  m='1161060'>of</span> <span m='1161150'>the</span> <span
  m='1161270'>fact</span> <span m='1161990'>that</span> <span
  m='1163190'>the</span> <span m='1163310'>digital</span> <span
  m='1163730'>filter</span> <span m='1164630'>had</span> <span
  m='1164780'>a</span> <span m='1164840'>cutoff</span> <span
  m='1165320'>frequency</span> <span m='1166610'>which</span> <span
  m='1166790'>was</span> <span m='1166970'>1/10</span> <span
  m='1167870'>of</span> <span m='1168020'>2</span> <span m='1168260'>pi.</span>
  <span m='1170060'>2</span> <span m='1170370'>pi</span> <span
  m='1170770'>gets</span> <span m='1172070'>rescaled</span> <span
  m='1173150'>to</span> <span m='1173360'>the</span> <span
  m='1173480'>sampling</span> <span m='1173990'>frequency</span> <span
  m='1174860'>in</span> <span m='1175070'>the</span> <span
  m='1175310'>continuous</span> <span m='1175910'>time</span> <span
  m='1176450'>domain.</span> <span m='1177680'>And</span> <span
  m='1178280'>the</span> <span m='1178400'>filter</span> <span
  m='1178760'>cutoff</span> <span m='1179180'>frequency</span> <span
  m='1180110'>will</span> <span m='1180290'>then</span> <span
  m='1180530'>get</span> <span m='1180830'>rescaled</span> <span
  m='1181610'>to</span> <span m='1182240'>one</span> <span
  m='1182645'>tenth</span> <span m='1183050'>of</span> <span
  m='1183440'>the</span> <span m='1183650'>filter</span> <span
  m='1184040'>sampling</span> <span m='1184520'>frequency.</span> </p><p><span
  m='1186960'>Let's</span> <span m='1187380'>illustrate</span> <span
  m='1187920'>some</span> <span m='1188160'>of</span> <span
  m='1188220'>these</span> <span m='1188460'>effects</span> <span
  m='1189120'>with</span> <span m='1189720'>the</span> <span
  m='1190230'>digital</span> <span m='1190590'>filter.</span> <span
  m='1191730'>What</span> <span m='1191970'>we</span> <span
  m='1192120'>have,</span> <span m='1192450'>as</span> <span
  m='1192600'>I</span> <span m='1193200'>said</span> <span
  m='1193720'>was,</span> <span m='1194160'>is</span> <span m='1194460'>a</span>
  <span m='1194730'>low</span> <span m='1194940'>pass</span> <span
  m='1195270'>filter</span> <span m='1196170'>impulse</span> <span
  m='1196590'>response</span> <span m='1197070'>and</span> <span
  m='1197160'>frequency</span> <span m='1197670'>response.</span> <span
  m='1198840'>First</span> <span m='1199320'>let's</span> <span
  m='1199770'>look</span> <span m='1200100'>at</span> <span
  m='1200370'>the</span> <span m='1200640'>impulse</span> <span
  m='1201120'>response</span> <span m='1201690'>of</span> <span
  m='1201810'>the</span> <span m='1201900'>filter</span> <span
  m='1203130'>of</span> <span m='1203280'>the</span> <span
  m='1203400'>overall</span> <span m='1203970'>system--</span> <span
  m='1204420'>in</span> <span m='1204510'>other</span> <span
  m='1204720'>words,</span> <span m='1205180'>after</span> <span
  m='1205920'>the</span> <span m='1206340'>D-sampling</span> <span
  m='1207150'>low-pass</span> <span m='1207660'>filter.</span> <span
  m='1210480'>What</span> <span m='1210600'>we</span> <span
  m='1210690'>see</span> <span m='1210960'>here</span> <span
  m='1211350'>is</span> <span m='1211740'>the</span> <span
  m='1212310'>impulse</span> <span m='1212790'>response</span> <span
  m='1213630'>of</span> <span m='1214110'>the</span> <span
  m='1214230'>overall</span> <span m='1214680'>system.</span> <span
  m='1216510'>And</span> <span m='1217530'>we</span> <span
  m='1218040'>observe,</span> <span m='1218400'>for</span> <span
  m='1218550'>one</span> <span m='1218730'>thing,</span> <span
  m='1219000'>that</span> <span m='1219180'>it's</span> <span
  m='1219360'>a</span> <span m='1219420'>symmetrical</span> <span
  m='1220020'>impulse</span> <span m='1220440'>response--</span> <span
  m='1221070'>in</span> <span m='1221160'>other</span> <span
  m='1221370'>words,</span> <span m='1221670'>corresponds</span> <span
  m='1222450'>to</span> <span m='1222690'>a</span> <span
  m='1222900'>linear</span> <span m='1223260'>phase</span> <span
  m='1223620'>filter.</span> </p><p><span m='1224710'>We</span> <span
  m='1224730'>can</span> <span m='1224880'>also</span> <span
  m='1225210'>look</span> <span m='1225420'>at</span> <span
  m='1225510'>the</span> <span m='1225630'>impulse</span> <span
  m='1226050'>response</span> <span m='1226860'>before</span> <span
  m='1227340'>the D-sampling</span> <span m='1228390'>low-pass</span> <span
  m='1228930'>filter.</span> <span m='1229340'>Lets</span> <span
  m='1229650'>take</span> <span m='1229950'>out</span> <span
  m='1230130'>that</span> <span m='1230190'>the D-sampling</span> <span
  m='1230790'>low-pass</span> <span m='1231270'>filter</span> <span
  m='1231810'>slowly.</span> <span m='1233520'>And</span> <span
  m='1234330'>what</span> <span m='1234900'>we</span> <span
  m='1235110'>observe</span> <span m='1235770'>is</span> <span
  m='1236160'>basically</span> <span m='1236790'>the</span> <span
  m='1236940'>output</span> <span m='1237540'>of</span> <span
  m='1237900'>the</span> <span m='1238170'>digital-to-analog</span> <span
  m='1239190'>converter,</span> <span m='1240030'>which,</span> <span
  m='1240840'>of</span> <span m='1240960'>course,</span> <span
  m='1241290'>is</span> <span m='1241410'>a</span> <span
  m='1241500'>staircase</span> <span m='1242220'>or</span> <span
  m='1242430'>boxcar</span> <span m='1242880'>function,</span> <span
  m='1243690'>not</span> <span m='1243960'>an</span> <span
  m='1244050'>impulse</span> <span m='1244470'>train.</span> </p><p><span
  m='1245280'>In</span> <span m='1245340'>the</span> <span
  m='1245430'>real</span> <span m='1245670'>world,</span> <span
  m='1246360'>the</span> <span m='1246690'>output</span> <span
  m='1247080'>of</span> <span m='1247170'>a</span> <span m='1247230'>[? D-day
  ?]</span> <span m='1247590'>converter</span> <span
  m='1248130'>generally</span> <span m='1248670'>is</span> <span
  m='1248790'>a</span> <span m='1248970'>boxcar</span> <span
  m='1249630'>type</span> <span m='1249930'>of</span> <span
  m='1249990'>function.</span> <span m='1251070'>We</span> <span
  m='1251280'>can</span> <span m='1251430'>put</span> <span m='1251850'>the
  D</span> <span m='1252180'>sampling</span> <span m='1252630'>filter</span>
  <span m='1252990'>back</span> <span m='1253320'>in</span> <span
  m='1253470'>now.</span> <span m='1254010'>And</span> <span
  m='1254910'>notice</span> <span m='1255420'>that</span> <span
  m='1255750'>the</span> <span m='1255900'>effect</span> <span
  m='1256270'>of</span> <span m='1256330'>the D-sampling</span> <span
  m='1257100'>filter</span> <span m='1257610'>is</span> <span
  m='1257760'>basically</span> <span m='1258960'>to</span> <span
  m='1259080'>smooth</span> <span m='1259590'>out</span> <span
  m='1260190'>the</span> <span m='1260700'>rough</span> <span
  m='1261030'>edges</span> <span m='1261660'>in</span> <span
  m='1262230'>the</span> <span m='1262470'>boxcar</span> <span
  m='1263670'>output</span> <span m='1264120'>from</span> <span
  m='1264300'>the</span> <span m='1264360'>[? D-day ?]</span> <span
  m='1264780'>converter.</span> </p><p><span m='1266526'>All</span> <span
  m='1266940'>right,</span> <span m='1267150'>now</span> <span
  m='1267600'>what</span> <span m='1267800'>we'd</span> <span
  m='1267960'>like</span> <span m='1268140'>to</span> <span
  m='1268230'>demonstrate</span> <span m='1269010'>is</span> <span
  m='1269640'>the</span> <span m='1270510'>actual</span> <span
  m='1271170'>frequency</span> <span m='1271800'>response</span> <span
  m='1272550'>of</span> <span m='1272730'>the</span> <span
  m='1272850'>overall</span> <span m='1273270'>continuous</span> <span
  m='1273840'>time</span> <span m='1274140'>filter.</span> <span
  m='1275130'>And</span> <span m='1275250'>we</span> <span
  m='1275340'>can</span> <span m='1275520'>do</span> <span
  m='1275700'>that</span> <span m='1276210'>by</span> <span
  m='1277260'>sweeping</span> <span m='1278340'>the</span> <span
  m='1278700'>system</span> <span m='1279570'>with</span> <span
  m='1279780'>a</span> <span m='1279810'>sinusoidal</span> <span
  m='1280530'>input.</span> <span m='1281430'>And</span> <span
  m='1281580'>what</span> <span m='1281700'>we</span> <span
  m='1281850'>expect</span> <span m='1282210'>to</span> <span
  m='1282330'>see,</span> <span m='1282640'>of</span> <span
  m='1282660'>course,</span> <span m='1283150'>is</span> <span
  m='1283230'>as</span> <span m='1283560'>the</span> <span
  m='1284100'>sinusoidal</span> <span m='1284760'>input</span> <span
  m='1285090'>frequency</span> <span m='1285810'>gets</span> <span
  m='1286080'>past</span> <span m='1286590'>the</span> <span
  m='1287250'>effective</span> <span m='1287760'>cutoff</span> <span
  m='1288240'>frequency,</span> <span m='1289440'>then</span> <span
  m='1289830'>the</span> <span m='1289980'>output</span> <span
  m='1290370'>sinusoid</span> <span m='1291270'>is</span> <span
  m='1291450'>greatly</span> <span m='1291810'>attenuated.</span> <span
  m='1294150'>Let's</span> <span m='1294510'>now</span> <span
  m='1294930'>sweep</span> <span m='1295320'>the</span> <span
  m='1295410'>filter</span> <span m='1295920'>frequency</span> <span
  m='1296520'>response.</span> <span m='1302140'>And</span> <span
  m='1303730'>there</span> <span m='1304120'>is</span> <span
  m='1304360'>the</span> <span m='1304600'>filter</span> <span
  m='1305170'>cutoff</span> <span m='1305530'>frequency.</span> </p><p><span
  m='1311250'>We</span> <span m='1311400'>can</span> <span
  m='1311550'>demonstrate</span> <span m='1312420'>the</span> <span
  m='1313500'>filter</span> <span m='1314100'>characteristics</span> <span
  m='1315270'>in</span> <span m='1315450'>several</span> <span
  m='1315870'>other</span> <span m='1316080'>ways.</span> <span
  m='1317320'>One</span> <span m='1317460'>way</span> <span
  m='1317910'>is</span> <span m='1318540'>to</span> <span
  m='1318960'>choose,</span> <span m='1320160'>as</span> <span
  m='1320340'>a</span> <span m='1320400'>display,</span> <span
  m='1321360'>instead</span> <span m='1321810'>of</span> <span
  m='1322320'>the</span> <span m='1322470'>output</span> <span
  m='1322890'>as</span> <span m='1323010'>a</span> <span
  m='1323070'>function</span> <span m='1323520'>of</span> <span
  m='1323610'>time,</span> <span m='1324540'>we</span> <span
  m='1324630'>can</span> <span m='1324780'>display</span> <span
  m='1325380'>the</span> <span m='1325530'>output</span> <span
  m='1325860'>sinusoid</span> <span m='1326760'>as</span> <span
  m='1326940'>a</span> <span m='1327000'>function</span> <span
  m='1327390'>of</span> <span m='1327450'>frequency.</span> <span
  m='1328690'>And</span> <span m='1328950'>so</span> <span
  m='1329160'>we'll</span> <span m='1329310'>observe</span> <span
  m='1329760'>that</span> <span m='1330120'>on</span> <span
  m='1330300'>the</span> <span m='1330470'>left-hand</span> <span
  m='1331230'>scope,</span> <span m='1332130'>while</span> <span
  m='1332370'>on</span> <span m='1332490'>the</span> <span
  m='1332580'>right-hand</span> <span m='1333030'>scope,</span> <span
  m='1333420'>we'll</span> <span m='1333540'>have</span> <span
  m='1333720'>the</span> <span m='1333810'>same</span> <span
  m='1334110'>trace</span> <span m='1334500'>that</span> <span
  m='1334890'>we</span> <span m='1335010'>just</span> <span
  m='1335310'>saw,</span> <span m='1336150'>namely</span> <span
  m='1336540'>two</span> <span m='1336760'>traces</span> <span
  m='1337350'>the</span> <span m='1337470'>upper</span> <span m='1337680'>trace
  as</span> <span m='1338160'>the</span> <span m='1338280'>input</span> <span
  m='1338610'>sinusoid,</span> <span m='1339750'>the</span> <span
  m='1339840'>lower</span> <span m='1340110'>trace as</span> <span
  m='1340590'>the</span> <span m='1340710'>output</span> <span
  m='1341070'>sinusoid.</span> <span m='1342420'>And</span> <span
  m='1342780'>in</span> <span m='1342960'>addition</span> <span
  m='1343380'>to</span> <span m='1343560'>observing</span> <span
  m='1344430'>the</span> <span m='1344520'>frequency</span> <span
  m='1345060'>response,</span> <span m='1346050'>let's</span> <span
  m='1346290'>also</span> <span m='1346680'>listen</span> <span
  m='1347310'>to</span> <span m='1347490'>the</span> <span
  m='1347610'>output</span> <span m='1348000'>sinusoid</span> <span
  m='1349200'>and</span> <span m='1350220'>observe</span> <span
  m='1350880'>the</span> <span m='1351000'>attenuation</span> <span
  m='1351940'>in</span> <span m='1352080'>the</span> <span
  m='1352200'>output</span> <span m='1352710'>as</span> <span
  m='1353010'>we</span> <span m='1353130'>go</span> <span
  m='1353340'>from</span> <span m='1353520'>the</span> <span
  m='1353610'>filter</span> <span m='1353910'>passband</span> <span
  m='1354510'>to</span> <span m='1354630'>the</span> <span
  m='1354720'>filter</span> <span m='1355050'>stopband.</span> <span
  m='1356100'>Again,</span> <span m='1356400'>a</span> <span
  m='1356460'>20-kilohertz</span> <span m='1357210'>sampling</span> <span
  m='1357690'>rate</span> <span m='1358350'>and</span> <span
  m='1358500'>a</span> <span m='1358560'>sweep</span> <span
  m='1359160'>range</span> <span m='1359610'>from</span> <span
  m='1359790'>0</span> <span m='1360150'>to</span> <span m='1360300'>10</span>
  <span m='1360540'>kilohertz.</span> </p><p><span m='1360900'>[SOUND WAVES
  RISE]</span> </p><p></p><p><span m='1368970'>Now,</span> <span
  m='1369140'>of</span> <span m='1369230'>course</span> <span
  m='1369530'>we're</span> <span m='1369680'>in</span> <span
  m='1369740'>the</span> <span m='1369830'>filter</span> <span
  m='1370420'>stopband.</span> <span m='1373780'>Now,</span> <span
  m='1374960'>if</span> <span m='1375470'>we</span> <span
  m='1375920'>increase</span> <span m='1376520'>the</span> <span
  m='1376640'>sweep</span> <span m='1377000'>range</span> <span
  m='1377720'>from</span> <span m='1378650'>10 kilohertz</span> <span
  m='1379430'>to</span> <span m='1379550'>20</span> <span
  m='1379930'>kilohertz</span> <span m='1381110'>so</span> <span
  m='1381270'>that</span> <span m='1381440'>the</span> <span
  m='1381560'>sweep</span> <span m='1381890'>range</span> <span
  m='1382250'>is</span> <span m='1382370'>equal</span> <span
  m='1382670'>to</span> <span m='1382790'>the</span> <span
  m='1382910'>sampling</span> <span m='1383420'>frequency,</span> <span
  m='1384620'>in</span> <span m='1384770'>essence,</span> <span
  m='1385250'>that</span> <span m='1385430'>corresponds</span> <span
  m='1386210'>to</span> <span m='1386330'>sweeping</span> <span
  m='1386750'>out</span> <span m='1386900'>the</span> <span
  m='1386990'>digital</span> <span m='1387350'>filter</span> <span
  m='1388310'>from</span> <span m='1388820'>0</span> <span m='1389330'>to</span>
  <span m='1389510'>2</span> <span m='1389750'>pi.</span> <span
  m='1390710'>And</span> <span m='1390860'>in</span> <span
  m='1390950'>that</span> <span m='1391130'>case,</span> <span
  m='1391490'>we'll</span> <span m='1391640'>begin</span> <span
  m='1392030'>to</span> <span m='1392180'>see</span> <span
  m='1392930'>some</span> <span m='1393200'>of</span> <span
  m='1393290'>the</span> <span m='1393410'>periodicity</span> <span
  m='1394400'>in</span> <span m='1394550'>the</span> <span
  m='1394640'>digital</span> <span m='1395000'>filter</span> <span
  m='1395330'>frequency</span> <span m='1395840'>response.</span> <span
  m='1396930'>So</span> <span m='1397430'>let's</span> <span
  m='1397940'>do</span> <span m='1398150'>that</span> <span
  m='1398450'>now</span> <span m='1398960'>with</span> <span
  m='1399140'>a</span> <span m='1399200'>20-kilohertz</span> <span
  m='1399980'>sampling</span> <span m='1400490'>rate</span> <span
  m='1401180'>and</span> <span m='1401300'>a</span> <span
  m='1401330'>sweep</span> <span m='1401720'>range</span> <span
  m='1402170'>of</span> <span m='1402260'>0</span> <span m='1402620'>to</span>
  <span m='1402770'>20</span> <span m='1403070'>kilohertz.</span> </p><p><span
  m='1403445'>[SOUND WAVES RISE AND FALL]</span> </p><p></p><p><span
  m='1408460'>Now</span> <span m='1408700'>we</span> <span
  m='1408820'>come</span> <span m='1409200'>near</span> <span
  m='1409430'>2</span> <span m='1409690'>pi,</span> <span m='1413110'>we</span>
  <span m='1413290'>get</span> <span m='1413530'>back</span> <span
  m='1413890'>into</span> <span m='1414160'>the</span> <span
  m='1414260'>passband,</span> <span m='1416770'>and</span> <span
  m='1417400'>finally,</span> <span m='1417850'>back</span> <span
  m='1418270'>to</span> <span m='1418750'>a</span> <span m='1419050'>0-</span>
  <span m='1419410'>to</span> <span m='1419530'>10-kilohertz</span> <span
  m='1420340'>sweep</span> <span m='1421060'>so</span> <span
  m='1421210'>they</span> <span m='1421420'>were</span> <span
  m='1421600'>again,</span> <span m='1421900'>sweeping</span> <span
  m='1422470'>only</span> <span m='1422920'>from</span> <span
  m='1423250'>0</span> <span m='1423640'>to</span> <span m='1423790'>pi</span>
  <span m='1424840'>with</span> <span m='1425110'>regard</span> <span
  m='1425500'>to</span> <span m='1425620'>the</span> <span
  m='1425740'>digital</span> <span m='1426070'>filter.</span> </p><p><span
  m='1427863'>[SOUND WAVES RISE]</span> </p><p></p><p><span
  m='1438670'>OK,</span> <span m='1439220'>now,</span> <span
  m='1439730'>what</span> <span m='1439970'>we</span> <span
  m='1440120'>would</span> <span m='1440270'>like</span> <span
  m='1440540'>to</span> <span m='1440810'>demonstrate</span> <span
  m='1441560'>is</span> <span m='1441740'>the</span> <span
  m='1441860'>effect</span> <span m='1442220'>of</span> <span
  m='1442340'>changing</span> <span m='1442820'>the</span> <span
  m='1442910'>sampling</span> <span m='1443420'>frequency.</span> <span
  m='1444840'>And</span> <span m='1445430'>we</span> <span
  m='1445580'>know</span> <span m='1446150'>that</span> <span
  m='1446780'>the</span> <span m='1446990'>sampling--</span> <span
  m='1447770'>that</span> <span m='1447920'>the</span> <span
  m='1448010'>effective</span> <span m='1448430'>filter</span> <span
  m='1448790'>cutoff</span> <span m='1449120'>frequency</span> <span
  m='1449990'>is</span> <span m='1450170'>tied</span> <span
  m='1450710'>to</span> <span m='1451190'>the</span> <span
  m='1451760'>sampling</span> <span m='1452300'>frequency,</span> <span
  m='1453440'>and</span> <span m='1453560'>for</span> <span
  m='1453710'>this</span> <span m='1453860'>particular</span> <span
  m='1454400'>filter,</span> <span m='1455300'>corresponds</span> <span
  m='1456050'>to</span> <span m='1456230'>a</span> <span
  m='1456320'>tenth</span> <span m='1456800'>of</span> <span
  m='1457130'>the</span> <span m='1457340'>sampling</span> <span
  m='1457880'>frequency.</span> <span m='1458990'>Consequently,</span> <span
  m='1459770'>if</span> <span m='1459890'>we</span> <span
  m='1460010'>double</span> <span m='1460340'>the</span> <span
  m='1460430'>sampling</span> <span m='1460910'>frequency,</span> <span
  m='1461570'>we</span> <span m='1461720'>should</span> <span
  m='1461900'>double</span> <span m='1462350'>the</span> <span
  m='1463130'>effective</span> <span m='1463760'>filter</span> <span
  m='1464210'>passband</span> <span m='1464710'>width</span> <span
  m='1465770'>or</span> <span m='1466310'>double</span> <span
  m='1466760'>the</span> <span m='1466940'>filter</span> <span
  m='1467300'>cutoff</span> <span m='1467720'>frequency.</span> <span
  m='1469010'>And</span> <span m='1469550'>so</span> <span
  m='1469910'>let's</span> <span m='1470330'>do</span> <span
  m='1470540'>that</span> <span m='1470780'>now.</span> <span
  m='1471380'>Again,</span> <span m='1471720'>a</span> <span
  m='1471770'>0</span> <span m='1472160'>to</span> <span m='1472350'>10</span>
  <span m='1472520'>kilohertz</span> <span m='1472880'>sweep</span> <span
  m='1473270'>range,</span> <span m='1474140'>but</span> <span
  m='1474440'>a</span> <span m='1474680'>40-kilohertz</span> <span
  m='1475850'>sampling</span> <span m='1476360'>frequency.</span> </p><p><span
  m='1478307'>[SOUND WAVES RISE]</span> </p><p><span m='1480602'>And</span>
  <span m='1481980'>we</span> <span m='1482130'>should</span> <span
  m='1482310'>observe</span> <span m='1482790'>that</span> <span
  m='1482940'>the</span> <span m='1483090'>filter</span> <span
  m='1483630'>cutoff</span> <span m='1484080'>frequency</span> <span
  m='1484680'>has</span> <span m='1484830'>now</span> <span
  m='1485040'>doubled</span> <span m='1485650'>out</span> <span
  m='1485880'>to</span> <span m='1486030'>4</span> <span
  m='1486450'>kilohertz.</span> <span m='1489850'>Now</span> <span
  m='1490380'>let's</span> <span m='1490800'>begin</span> <span
  m='1491160'>to</span> <span m='1491280'>decrease</span> <span
  m='1491820'>the</span> <span m='1491910'>filter</span> <span
  m='1492270'>sampling</span> <span m='1492750'>frequency.</span> <span
  m='1494260'>So</span> <span m='1494430'>from</span> <span
  m='1494580'>40,</span> <span m='1494970'>let's</span> <span
  m='1495240'>change</span> <span m='1495660'>the</span> <span
  m='1495930'>sampling</span> <span m='1496410'>frequency</span> <span
  m='1496890'>to</span> <span m='1497010'>20</span> <span
  m='1497310'>kilohertz.</span> <span m='1498620'>And</span> <span
  m='1499120'>we</span> <span m='1499200'>should</span> <span
  m='1499380'>see</span> <span m='1499650'>the</span> <span
  m='1499860'>cutoff</span> <span m='1500280'>frequency</span> <span
  m='1501000'>cut</span> <span m='1501240'>in</span> <span
  m='1501330'>half.</span> </p><p><span m='1503354'>[SOUND WAVES RISE]</span>
  </p><p></p><p><span m='1512330'>Now</span> <span m='1512440'>we</span> <span
  m='1512560'>can</span> <span m='1512710'>go</span> <span
  m='1513190'>even</span> <span m='1513520'>further.</span> <span
  m='1513970'>We</span> <span m='1514150'>can</span> <span
  m='1514330'>cut</span> <span m='1514540'>the</span> <span
  m='1514630'>sampling</span> <span m='1515080'>frequency</span> <span
  m='1515620'>down</span> <span m='1515860'>to</span> <span
  m='1515950'>10</span> <span m='1516310'>kilohertz.</span> <span
  m='1516910'>And</span> <span m='1517000'>remember</span> <span
  m='1517420'>that</span> <span m='1517660'>the</span> <span
  m='1517930'>sweep</span> <span m='1518320'>range</span> <span
  m='1518650'>is</span> <span m='1518710'>0</span> <span m='1519070'>to</span>
  <span m='1519190'>10</span> <span m='1519430'>kilohertz.</span> <span
  m='1520160'>So</span> <span m='1520180'>now</span> <span
  m='1520390'>we'll</span> <span m='1520540'>be</span> <span
  m='1520690'>sweeping</span> <span m='1521170'>from</span> <span
  m='1521350'>0</span> <span m='1521710'>to</span> <span m='1521830'>2</span>
  <span m='1522070'>pi.</span> </p><p><span m='1524506'>[SOUND WAVES
  RISE]</span> </p><p></p><p><span m='1530200'>So</span> <span
  m='1530310'>as</span> <span m='1530430'>we</span> <span m='1530520'>get</span>
  <span m='1530670'>close</span> <span m='1531210'>to</span> <span
  m='1531450'>2</span> <span m='1531690'>pi,</span> <span
  m='1531990'>we'll</span> <span m='1532140'>see</span> <span
  m='1532320'>the</span> <span m='1532440'>passband</span> <span
  m='1533040'>again.</span> </p><p><span m='1533490'>[SOUND WAVES FALL]</span>
  </p><p><span m='1535560'>And</span> <span m='1536430'>now,</span> <span
  m='1536940'>let's</span> <span m='1537240'>cut</span> <span
  m='1537510'>down</span> <span m='1537720'>the</span> <span
  m='1537810'>sampling</span> <span m='1538230'>frequency</span> <span
  m='1538990'>even</span> <span m='1539310'>further</span> <span
  m='1540200'>to</span> <span m='1540450'>5</span> <span
  m='1540780'>kilohertz.</span> </p><p><span m='1543965'>[SOUND WAVES
  RISE]</span> </p><p></p><p><span m='1547250'>Here</span> <span
  m='1547400'>we</span> <span m='1547550'>are</span> <span m='1547760'>at</span>
  <span m='1547830'>2</span> <span m='1548070'>pi.</span> </p><p><span
  m='1548928'>[SOUND WAVES RISE]</span> </p><p><span m='1551320'>And</span>
  <span m='1551500'>then</span> <span m='1552100'>at</span> <span
  m='1552470'>4</span> <span m='1552735'>pi.</span> </p><p><span
  m='1553000'>[SOUND WAVES FALL]</span> </p><p><span m='1554590'>Now</span>
  <span m='1555010'>finally,</span> <span m='1555760'>let's</span> <span
  m='1556330'>demonstrate</span> <span m='1557680'>this</span> <span
  m='1558100'>effect</span> <span m='1558640'>of</span> <span
  m='1559150'>changing</span> <span m='1560290'>the</span> <span
  m='1560950'>effective</span> <span m='1561820'>filter</span> <span
  m='1562180'>cutoff</span> <span m='1562570'>frequency</span> <span
  m='1563200'>by</span> <span m='1563350'>changing</span> <span
  m='1563800'>the</span> <span m='1563890'>sampling</span> <span
  m='1564400'>rate</span> <span m='1565120'>by</span> <span
  m='1565540'>carrying</span> <span m='1566050'>out</span> <span
  m='1566200'>some</span> <span m='1566380'>low-pass</span> <span
  m='1566860'>filtering</span> <span m='1567520'>on</span> <span
  m='1567670'>some</span> <span m='1567850'>live</span> <span
  m='1568180'>audio.</span> <span m='1569380'>And</span> <span
  m='1569680'>we'll</span> <span m='1569860'>demonstrate</span> <span
  m='1570520'>this</span> <span m='1571090'>by</span> <span
  m='1572110'>listening</span> <span m='1572590'>to</span> <span
  m='1572710'>the</span> <span m='1572890'>audio,</span> <span
  m='1573520'>and</span> <span m='1573670'>also,</span> <span
  m='1574420'>observing</span> <span m='1574990'>the</span> <span
  m='1575110'>audio</span> <span m='1575710'>on</span> <span
  m='1578620'>on</span> <span m='1578740'>a</span> <span
  m='1578800'>single</span> <span m='1579220'>trace,</span> <span
  m='1580180'>namely,</span> <span m='1580750'>the</span> <span
  m='1580870'>time</span> <span m='1581200'>waveform.</span> <span
  m='1582430'>And</span> <span m='1582910'>we'll</span> <span
  m='1583270'>begin</span> <span m='1583640'>it</span> <span
  m='1584020'>with</span> <span m='1584230'>a</span> <span
  m='1585130'>sampling</span> <span m='1585610'>frequency</span> <span
  m='1586120'>of</span> <span m='1586180'>40</span> <span
  m='1586680'>kilohertz,</span> <span m='1587830'>change</span> <span
  m='1588250'>that</span> <span m='1588700'>then</span> <span
  m='1588940'>to</span> <span m='1589060'>20</span> <span
  m='1589390'>kilohertz,</span> <span m='1590020'>10</span> <span
  m='1590290'>kilohertz,</span> <span m='1590890'>5,</span> <span
  m='1591550'>and</span> <span m='1591670'>then</span> <span
  m='1591790'>2</span> <span m='1592050'>and</span> <span
  m='1592310'>1/2,</span> <span m='1593170'>corresponding</span> <span
  m='1593980'>to</span> <span m='1594160'>a</span> <span
  m='1594190'>filter</span> <span m='1594580'>cutoff</span> <span
  m='1594970'>frequency</span> <span m='1595660'>then</span> <span
  m='1596040'>of</span> <span m='1596170'>4</span> <span
  m='1596830'>kilohertz,</span> <span m='1597190'>then</span> <span
  m='1597340'>2</span> <span m='1597560'>kilohertz,</span> <span
  m='1598570'>then</span> <span m='1598720'>1</span> <span
  m='1598990'>kilohertz,</span> <span m='1600190'>then</span> <span
  m='1600850'>500,</span> <span m='1601195'>,</span> <span
  m='1601540'>250</span> <span m='1602320'>etc.</span> </p><p><span
  m='1603520'>So</span> <span m='1603700'>let's</span> <span
  m='1603970'>begin</span> <span m='1605070'>40</span> <span
  m='1605500'>kilohertz.</span> <span m='1606250'>And</span> <span
  m='1606460'>then</span> <span m='1606880'>we'll</span> <span
  m='1607150'>work</span> <span m='1607450'>our</span> <span
  m='1607540'>way</span> <span m='1607750'>down.</span> </p><p><span
  m='1609916'>[MUSIC PLAYING]</span> </p><p></p><p><span m='1614660'>Now,</span>
  <span m='1615290'>let's</span> <span m='1615530'>reduce</span> <span
  m='1615890'>that</span> <span m='1616130'>to a</span> <span
  m='1616370'>20-kilohertz</span> <span m='1617690'>frequency</span> <span
  m='1618470'>or a</span> <span m='1618710'>2-kilohertz</span> <span
  m='1619220'>filter.</span> </p><p><span m='1620220'>[MUSIC PLAYING]</span>
  </p><p></p><p><span m='1625550'>And</span> <span m='1625690'>10</span> <span
  m='1625990'>kilohertz</span> <span m='1626500'>sampling</span> <span
  m='1626980'>frequency.</span> </p><p><span m='1627760'>[MUSIC PLAYING]</span>
  </p><p><span m='1633130'>And</span> <span m='1633280'>finally,</span> <span
  m='1633790'>a</span> <span m='1633880'>5-kilohertz</span> <span
  m='1634690'>sampling</span> <span m='1635220'>frequency</span> <span
  m='1635850'>corresponding</span> <span m='1636610'>to</span> <span
  m='1636970'>make</span> <span m='1637630'>500-cycle</span> <span
  m='1638750'>equivalent</span> <span m='1639580'>analog</span> <span
  m='1640060'>filter.</span> </p><p><span m='1640480'>[MUSIC PLAYING]</span>
  </p><p></p><p><span m='1645620'>All</span> <span m='1645680'>right,</span>
  <span m='1645820'>now</span> <span m='1646260'>let's</span> <span
  m='1646470'>finally</span> <span m='1646830'>conclude</span> <span
  m='1647370'>by</span> <span m='1648000'>returning</span> <span
  m='1648540'>to</span> <span m='1649380'>a</span> <span
  m='1649410'>little</span> <span m='1649680'>higher</span> <span
  m='1649980'>quality</span> <span m='1650500'>ragtime</span> <span
  m='1651020'>by</span> <span m='1651510'>changing</span> <span
  m='1651750'>the</span> <span m='1652010'>sampling</span> <span
  m='1652460'>rates</span> <span m='1652900'>back</span> <span
  m='1653680'>to</span> <span m='1653980'>40</span> <span
  m='1654280'>kilohertz.</span> </p><p><span m='1654580'>[MUSIC PLAYING]</span>
  </p><p></p>
embedded_media:
  - uid: 736e99051b46c0b8f975aa655e28f76e
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: zBJMh-m9b1E
  - uid: 2201df301b7ed13e13f81f5b3e656e11
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_demo1_300k.mp4'
  - uid: 5de4eb0a59b65b4edcd28a38f477fba4
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/demonstration-1-sampling-aliasing/id481803782?i=108362002
  - uid: a437a42ea2bcad0b49564a3e93be3d12
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/zBJMh-m9b1E/default.jpg'
  - uid: 8e844acfe0d6d17e56e6f2459f5bb22b
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: zBJMh-m9b1E
  - uid: 03f59a5f7f61c0b8d61ccd898963e135
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: zBJMh-m9b1E.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-1-sampling-aliasing-and-frequency-response-part-1/zBJMh-m9b1E.srt
  - uid: 6f66338f79aa177bf0f65f6a10c0330f
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: zBJMh-m9b1E.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-1-sampling-aliasing-and-frequency-response-part-1/zBJMh-m9b1E.pdf
  - uid: 4901d7b40abc56e040c63f4f31946592
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 5b8506d08dcaedb06af0044fd10e435a
    parent_uid: a8e2f3dbd8cbb59df512763287828b6a
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
