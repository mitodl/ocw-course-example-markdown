---
order_index: null
title: 'Lecture 12: Filtering'
template_type: Tabbed
uid: ca8df82ff8cdcc584aa80af112b53b96
parent_uid: a781d5ac598bc6063ba6ac8138e446cf
technical_location: >-
  https://ocw.mit.edu/resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-12-filtering
short_url: lecture-12-filtering
inline_embed_id: '37036974lecture12:filtering69558988'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Relation to the convolution property of
  Fourier transform; Ideal and non ideal frequency-selective filters:
  frequency-domain and time-domain characteristics; Continuous-time
  frequency-selective filters described by differential equations; RC low-pass
  and high-pass filters; Discrete-time frequency-selective filters described by
  difference equations; Moving average filters; Recursive discrete-time filters;
  Demonstration: a look at filtering in a commercial audio control room.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Filtering (<img alt="This resource may not render correctly in a screen
  reader." src="/images/inacessible.gif" /><a
  href="./resolveuid/1f4cdcf7436ec40c146750e827671697"
  target="_blank">PDF</a>)</p>
transcript: >-
  <p><span m='40'>The</span> <span m='150'>following</span> <span
  m='600'>content</span> <span m='1190'>is</span> <span m='1310'>provided</span>
  <span m='1750'>under</span> <span m='2040'>a</span> <span
  m='2060'>Creative</span> <span m='2470'>Commons</span> <span
  m='2870'>license.</span> <span m='3880'>Your</span> <span
  m='4160'>support</span> <span m='4670'>will</span> <span m='4840'>help</span>
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
  m='17220'>at</span> <span m='17400'>ocw.mit.edu.</span> </p><p><span
  m='55619'>PROFESSOR:</span> <span m='56140'>In</span> <span
  m='56380'>discussing</span> <span m='56920'>the</span> <span
  m='57200'>continuous-time</span> <span m='57950'>and</span> <span
  m='58000'>discrete-time</span> <span m='58690'>Fourier</span> <span
  m='59100'>transforms,</span> <span m='59840'>we</span> <span
  m='60420'>developed</span> <span m='61470'>a</span> <span
  m='61540'>number</span> <span m='62010'>of</span> <span
  m='62170'>important</span> <span m='62610'>properties.</span> <span
  m='64050'>Two</span> <span m='64319'>particularly</span> <span
  m='65260'>significant</span> <span m='65890'>ones,</span> <span
  m='66170'>as</span> <span m='66310'>I</span> <span m='66370'>mentioned</span>
  <span m='66950'>at</span> <span m='67120'>the</span> <span
  m='67230'>time,</span> <span m='67950'>are</span> <span m='68620'>the</span>
  <span m='68990'>modulation</span> <span m='69720'>property</span> <span
  m='70400'>and</span> <span m='70490'>the</span> <span
  m='70560'>convolution</span> <span m='71260'>property.</span> </p><p><span
  m='72860'>Starting</span> <span m='73730'>with</span> <span
  m='74230'>the</span> <span m='74350'>next</span> <span
  m='74620'>lecture,</span> <span m='74950'>the</span> <span
  m='75060'>one</span> <span m='75230'>after</span> <span m='75520'>this</span>
  <span m='75760'>one,</span> <span m='76250'>we'll</span> <span
  m='76560'>be</span> <span m='77280'>developing</span> <span
  m='78040'>and</span> <span m='78180'>exploiting</span> <span
  m='78800'>some</span> <span m='79000'>of</span> <span m='79100'>the</span>
  <span m='79190'>consequences</span> <span m='80240'>of</span> <span
  m='80350'>the</span> <span m='80440'>modulation</span> <span
  m='81100'>property.</span> <span m='82260'>In</span> <span
  m='82390'>today's</span> <span m='82770'>lecture</span> <span
  m='83170'>though,</span> <span m='83570'>I'd</span> <span
  m='83780'>like</span> <span m='84150'>to</span> <span m='84750'>review</span>
  <span m='85490'>and</span> <span m='85850'>expand</span> <span
  m='86560'>on</span> <span m='87620'>the</span> <span m='87840'>notion</span>
  <span m='88290'>of</span> <span m='88390'>filtering,</span> <span
  m='89190'>which,</span> <span m='89640'>as</span> <span m='89910'>I</span>
  <span m='90060'>had</span> <span m='90250'>mentioned,</span> <span
  m='91100'>flows</span> <span m='91850'>more</span> <span m='92080'>or</span>
  <span m='92120'>less</span> <span m='92400'>directly</span> <span
  m='93000'>from</span> <span m='93870'>the</span> <span
  m='94170'>convolution</span> <span m='94900'>property.</span> </p><p><span
  m='96700'>To</span> <span m='96790'>begin,</span> <span m='97130'>let</span>
  <span m='97320'>me</span> <span m='97470'>just</span> <span
  m='97840'>quickly</span> <span m='98180'>review</span> <span
  m='98790'>what</span> <span m='99030'>the</span> <span
  m='99140'>convolution</span> <span m='99820'>property</span> <span
  m='100340'>is.</span> <span m='101260'>Both</span> <span m='101660'>for</span>
  <span m='102050'>continuous-time</span> <span m='103420'>and</span> <span
  m='103900'>for</span> <span m='104190'>discrete-time,</span> <span
  m='105670'>the</span> <span m='105780'>convolution</span> <span
  m='106500'>property</span> <span m='106980'>tells</span> <span
  m='107390'>us</span> <span m='108170'>that</span> <span m='109030'>the</span>
  <span m='109320'>Fourier</span> <span m='109890'>transform</span> <span
  m='110900'>of</span> <span m='111400'>the</span> <span
  m='111590'>convolution</span> <span m='112620'>of</span> <span
  m='112900'>two</span> <span m='113070'>time</span> <span
  m='113420'>functions</span> <span m='114630'>is</span> <span
  m='115310'>the</span> <span m='115580'>product</span> <span
  m='116240'>of</span> <span m='116400'>the</span> <span
  m='116490'>Fourier</span> <span m='116950'>transforms.</span> </p><p><span
  m='119190'>Now,</span> <span m='120020'>what</span> <span
  m='120280'>this</span> <span m='120510'>means</span> <span
  m='121100'>in</span> <span m='121660'>terms</span> <span m='122250'>of</span>
  <span m='122850'>linear</span> <span m='123540'>time-invariant</span> <span
  m='124450'>filters,</span> <span m='125530'>since</span> <span
  m='125890'>we</span> <span m='126010'>know</span> <span m='126340'>that</span>
  <span m='127340'>in</span> <span m='127440'>the</span> <span
  m='127550'>time</span> <span m='127830'>domain</span> <span
  m='128340'>the</span> <span m='128479'>output</span> <span
  m='128830'>of</span> <span m='128889'>a</span> <span m='128970'>linear</span>
  <span m='129330'>time-invariant</span> <span m='130130'>filter</span> <span
  m='130669'>is</span> <span m='130880'>the</span> <span
  m='130960'>convolution</span> <span m='132250'>of</span> <span
  m='132750'>the</span> <span m='132890'>input</span> <span
  m='133450'>and</span> <span m='133660'>the</span> <span
  m='133760'>impulse</span> <span m='134220'>response,</span> <span
  m='135720'>it</span> <span m='135890'>says</span> <span
  m='136430'>essentially</span> <span m='137080'>then</span> <span
  m='137530'>in</span> <span m='137660'>the</span> <span
  m='137740'>frequency</span> <span m='138290'>domain</span> <span
  m='139310'>that</span> <span m='139510'>the</span> <span
  m='139590'>Fourier</span> <span m='140040'>transform</span> <span
  m='140700'>of</span> <span m='140790'>the</span> <span
  m='140950'>output</span> <span m='141590'>is</span> <span
  m='141780'>the</span> <span m='141870'>product</span> <span
  m='142920'>the</span> <span m='143220'>Fourier</span> <span
  m='143670'>transform</span> <span m='144520'>of</span> <span
  m='144630'>the</span> <span m='144740'>impulse</span> <span
  m='145210'>response,</span> <span m='146140'>namely</span> <span
  m='146450'>the</span> <span m='146540'>frequency</span> <span
  m='147070'>response,</span> <span m='148150'>and</span> <span
  m='148430'>the</span> <span m='148500'>Fourier</span> <span
  m='148950'>transform</span> <span m='150140'>of</span> <span
  m='150570'>the</span> <span m='150710'>input.</span> <span
  m='151850'>So</span> <span m='152630'>the</span> <span
  m='152770'>output</span> <span m='153240'>is</span> <span
  m='153420'>described</span> <span m='154460'>through</span> <span
  m='154660'>that</span> <span m='154920'>product.</span> </p><p><span
  m='156370'>Now,</span> <span m='157620'>recall</span> <span
  m='158090'>also</span> <span m='158880'>that</span> <span m='159590'>in</span>
  <span m='159730'>developing</span> <span m='160230'>the</span> <span
  m='160310'>Fourier</span> <span m='160760'>transform,</span> <span
  m='162110'>I</span> <span m='162330'>interpreted</span> <span
  m='163480'>the</span> <span m='163590'>Fourier</span> <span
  m='164000'>transform</span> <span m='164790'>as</span> <span
  m='165150'>the</span> <span m='165250'>complex</span> <span
  m='165840'>amplitude</span> <span m='166990'>of</span> <span
  m='167100'>a</span> <span m='167190'>decomposition</span> <span
  m='168070'>of</span> <span m='168150'>the</span> <span
  m='168230'>signal</span> <span m='169170'>in</span> <span
  m='169320'>terms</span> <span m='169690'>of</span> <span m='169770'>a</span>
  <span m='169810'>set</span> <span m='170030'>of</span> <span
  m='170120'>complex</span> <span m='170670'>exponentials.</span> <span
  m='172120'>And</span> <span m='172360'>the</span> <span
  m='172430'>frequency</span> <span m='172980'>response</span> <span
  m='173560'>or</span> <span m='173640'>the</span> <span
  m='173740'>convolution</span> <span m='174460'>property,</span> <span
  m='175110'>in</span> <span m='175230'>effect,</span> <span
  m='176300'>tells</span> <span m='176720'>us</span> <span m='179130'>how</span>
  <span m='179270'>to</span> <span m='179350'>modify</span> <span
  m='179880'>the</span> <span m='180040'>amplitudes</span> <span
  m='181170'>of</span> <span m='181320'>each</span> <span m='181510'>of</span>
  <span m='181560'>those</span> <span m='181810'>complex</span> <span
  m='182340'>exponentials</span> <span m='183210'>as</span> <span
  m='183460'>they</span> <span m='183550'>go</span> <span
  m='183760'>through</span> <span m='183960'>the</span> <span
  m='184060'>system.</span> </p><p><span m='185320'>Now,</span> <span
  m='185820'>this</span> <span m='186060'>led</span> <span m='186310'>to</span>
  <span m='186410'>the</span> <span m='186510'>notion</span> <span
  m='186860'>of</span> <span m='186950'>filtering,</span> <span
  m='187990'>where</span> <span m='188660'>the</span> <span
  m='188760'>basic</span> <span m='189190'>concept</span> <span
  m='189980'>was</span> <span m='191000'>that</span> <span
  m='191390'>since</span> <span m='191680'>we</span> <span m='191830'>can</span>
  <span m='192030'>modify</span> <span m='193040'>the</span> <span
  m='193270'>amplitudes</span> <span m='194160'>of</span> <span
  m='194400'>each</span> <span m='194780'>of</span> <span m='194950'>the</span>
  <span m='196330'>complex</span> <span m='196790'>exponential</span> <span
  m='197360'>components</span> <span m='197980'>separately,</span> <span
  m='199100'>we</span> <span m='199260'>can,</span> <span m='199530'>for</span>
  <span m='199710'>example,</span> <span m='200820'>retain</span> <span
  m='201600'>some</span> <span m='201930'>of</span> <span m='202070'>them</span>
  <span m='202800'>and</span> <span m='203370'>totally</span> <span
  m='203790'>eliminate</span> <span m='204270'>others.</span> <span
  m='205040'>And</span> <span m='205300'>this</span> <span m='205530'>is</span>
  <span m='205900'>the</span> <span m='206000'>basic</span> <span
  m='206430'>notion</span> <span m='206770'>of</span> <span
  m='206860'>filtering.</span> </p><p><span m='207810'>So</span> <span
  m='208450'>we</span> <span m='208580'>have,</span> <span m='209160'>as</span>
  <span m='209700'>you</span> <span m='209820'>recall,</span> <span
  m='210790'>first</span> <span m='211110'>of</span> <span m='211220'>all</span>
  <span m='211700'>the</span> <span m='211790'>notion</span> <span
  m='212420'>in</span> <span m='213000'>continuous-time</span> <span
  m='214880'>of</span> <span m='215270'>an</span> <span m='215420'>ideal</span>
  <span m='215860'>filter,</span> <span m='216890'>for</span> <span
  m='217070'>example,</span> <span m='217900'>I</span> <span
  m='218190'>illustrate</span> <span m='218850'>here</span> <span
  m='219820'>an</span> <span m='220010'>ideal</span> <span
  m='220820'>lowpass</span> <span m='221480'>filter</span> <span
  m='222440'>where</span> <span m='223130'>we</span> <span
  m='223310'>pass</span> <span m='223730'>exactly</span> <span
  m='224740'>frequency</span> <span m='225220'>components</span> <span
  m='225900'>in</span> <span m='225990'>one</span> <span m='226240'>band</span>
  <span m='227160'>and</span> <span m='227320'>reject</span> <span
  m='228110'>totally</span> <span m='229280'>frequency</span> <span
  m='229790'>components</span> <span m='230550'>in</span> <span
  m='230690'>another</span> <span m='231030'>band.</span> <span
  m='231940'>The</span> <span m='232030'>band</span> <span
  m='232390'>being</span> <span m='232620'>passed,</span> <span
  m='233060'>of</span> <span m='233160'>course,</span> <span
  m='233870'>referred</span> <span m='234290'>to</span> <span
  m='234430'>as</span> <span m='234550'>the</span> <span
  m='234620'>passband,</span> <span m='235850'>and</span> <span
  m='236370'>the</span> <span m='236470'>band</span> <span
  m='236740'>rejected</span> <span m='237280'>as</span> <span
  m='237400'>the</span> <span m='237470'>stopband.</span> </p><p><span
  m='240030'>I</span> <span m='240430'>illustrated</span> <span
  m='240880'>here</span> <span m='241070'>a</span> <span
  m='241140'>lowpass</span> <span m='241780'>filter.</span> <span
  m='242220'>We</span> <span m='242410'>can,</span> <span m='242650'>of</span>
  <span m='242780'>course,</span> <span m='243720'>reject</span> <span
  m='244390'>the</span> <span m='244580'>low</span> <span
  m='244820'>frequencies</span> <span m='246190'>and</span> <span
  m='246350'>retain</span> <span m='247210'>the</span> <span
  m='247310'>high</span> <span m='247550'>frequencies.</span> <span
  m='248930'>And</span> <span m='249590'>that</span> <span
  m='249980'>then</span> <span m='250250'>corresponds</span> <span
  m='251230'>to</span> <span m='251810'>an</span> <span m='251970'>ideal</span>
  <span m='252520'>highpass</span> <span m='253170'>filter.</span> <span
  m='254150'>Or</span> <span m='254810'>we</span> <span m='255060'>can</span>
  <span m='255250'>just</span> <span m='255510'>retain</span> <span
  m='255870'>frequencies</span> <span m='256540'>within</span> <span
  m='256790'>a</span> <span m='256839'>band.</span> <span m='257810'>And</span>
  <span m='258019'>so</span> <span m='258220'>I</span> <span
  m='258310'>show</span> <span m='258600'>below</span> <span
  m='259570'>what</span> <span m='260269'>is</span> <span
  m='260480'>referred</span> <span m='260899'>to</span> <span
  m='261040'>commonly</span> <span m='261740'>as</span> <span
  m='262540'>a</span> <span m='262640'>bandpass</span> <span
  m='263320'>filter.</span> </p><p><span m='265240'>Now,</span> <span
  m='266200'>this</span> <span m='266480'>is</span> <span m='266900'>what</span>
  <span m='267340'>the</span> <span m='267720'>ideal</span> <span
  m='268140'>filters</span> <span m='268670'>looked</span> <span
  m='268880'>like</span> <span m='269410'>for</span> <span
  m='269560'>continuous-time.</span> <span m='271070'>For</span> <span
  m='271200'>discrete-time,</span> <span m='271960'>we</span> <span
  m='272060'>have</span> <span m='272480'>exactly</span> <span
  m='273440'>the</span> <span m='273530'>same</span> <span
  m='273850'>situation.</span> <span m='275200'>Namely,</span> <span
  m='276000'>we</span> <span m='276180'>have</span> <span m='276680'>an</span>
  <span m='276840'>ideal</span> <span m='277540'>discrete-time</span> <span
  m='278240'>lowpass</span> <span m='278830'>filter,</span> <span
  m='279870'>which</span> <span m='280560'>passes</span> <span
  m='281070'>exactly</span> <span m='282370'>frequencies</span> <span
  m='283220'>which</span> <span m='283440'>are</span> <span
  m='283500'>the</span> <span m='283620'>low</span> <span
  m='283820'>frequencies.</span> <span m='285120'>Low</span> <span
  m='285310'>frequencies,</span> <span m='285860'>of</span> <span
  m='285970'>course,</span> <span m='286300'>being</span> <span
  m='286570'>around</span> <span m='286920'>0,</span> <span
  m='287500'>and</span> <span m='287690'>because</span> <span
  m='288030'>of</span> <span m='288080'>the</span> <span
  m='288160'>periodicity,</span> <span m='289090'>also</span> <span
  m='289570'>around</span> <span m='289850'>2pi.</span> </p><p><span
  m='292260'>We</span> <span m='292390'>show</span> <span m='292800'>also</span>
  <span m='293630'>an</span> <span m='293800'>ideal</span> <span
  m='294690'>highpass</span> <span m='295380'>filter.</span> <span
  m='296630'>And</span> <span m='296950'>a</span> <span
  m='297000'>highpass</span> <span m='297580'>filter,</span> <span
  m='298140'>as</span> <span m='298510'>I</span> <span
  m='298610'>indicated</span> <span m='299140'>last</span> <span
  m='299470'>time,</span> <span m='299700'>passes</span> <span
  m='300180'>frequencies</span> <span m='301110'>around</span> <span
  m='301460'>pi.</span> <span m='302740'>And</span> <span
  m='303380'>finally,</span> <span m='303910'>below</span> <span
  m='304310'>that,</span> <span m='304750'>I</span> <span m='304930'>show</span>
  <span m='305590'>an</span> <span m='305740'>ideal</span> <span
  m='306680'>bandpass</span> <span m='307460'>filter</span> <span
  m='310280'>passing</span> <span m='310710'>frequencies</span> <span
  m='311870'>someplace</span> <span m='312500'>in</span> <span
  m='312590'>the</span> <span m='312670'>range</span> <span
  m='313270'>between</span> <span m='313660'>0</span> <span
  m='314190'>and</span> <span m='314380'>pi.</span> <span m='316210'>And</span>
  <span m='316760'>recall</span> <span m='317210'>also</span> <span
  m='318050'>that</span> <span m='318490'>the</span> <span
  m='318570'>basic</span> <span m='319130'>difference</span> <span
  m='319700'>between</span> <span m='320330'>continuous-time</span> <span
  m='321180'>a</span> <span m='321220'>discrete-time</span> <span
  m='322190'>for</span> <span m='322360'>these</span> <span
  m='322610'>filters</span> <span m='323300'>is</span> <span
  m='323530'>that</span> <span m='324020'>the</span> <span
  m='324100'>discrete-time</span> <span m='324790'>versions</span> <span
  m='325800'>are,</span> <span m='326130'>of</span> <span
  m='326240'>course,</span> <span m='326860'>periodic</span> <span
  m='327640'>in</span> <span m='327780'>frequency.</span> </p><p><span
  m='329960'>Now,</span> <span m='330420'>let's</span> <span
  m='330700'>look</span> <span m='330970'>at</span> <span
  m='332240'>these</span> <span m='332550'>ideal</span> <span
  m='332980'>filters,</span> <span m='333560'>and</span> <span
  m='333640'>in</span> <span m='333730'>particular</span> <span
  m='334450'>the</span> <span m='334600'>ideal</span> <span
  m='334940'>lowpass</span> <span m='335550'>filter</span> <span
  m='336580'>in</span> <span m='336700'>the</span> <span m='336810'>time</span>
  <span m='337140'>domain.</span> <span m='339320'>We</span> <span
  m='339520'>have</span> <span m='340340'>the</span> <span
  m='340710'>frequency</span> <span m='341260'>response</span> <span
  m='342090'>of</span> <span m='342650'>the</span> <span m='342840'>ideal</span>
  <span m='343220'>lowpass</span> <span m='343800'>filter.</span> <span
  m='345290'>And</span> <span m='345960'>shown</span> <span
  m='346290'>below</span> <span m='346610'>it</span> <span m='347480'>is</span>
  <span m='348210'>the</span> <span m='348590'>impulse</span> <span
  m='349040'>response.</span> <span m='349580'>So</span> <span
  m='349700'>here</span> <span m='350090'>is</span> <span m='350270'>the</span>
  <span m='350350'>frequency</span> <span m='350910'>response</span> <span
  m='352120'>and</span> <span m='352780'>below</span> <span m='353190'>it</span>
  <span m='353480'>the</span> <span m='354270'>impulse</span> <span
  m='354780'>response</span> <span m='355640'>of</span> <span
  m='356250'>the</span> <span m='356640'>ideal</span> <span
  m='357500'>lowpass</span> <span m='358090'>filter.</span> <span
  m='359020'>And</span> <span m='359210'>this,</span> <span m='359390'>of</span>
  <span m='359500'>course,</span> <span m='360000'>is</span> <span
  m='360610'>a</span> <span m='360780'>sine</span> <span m='361120'>x</span>
  <span m='361340'>over</span> <span m='361690'>x</span> <span
  m='362270'>form</span> <span m='362580'>of</span> <span
  m='362690'>impulse</span> <span m='363150'>response.</span> </p><p><span
  m='364270'>And</span> <span m='364420'>recognize</span> <span
  m='365190'>also</span> <span m='365520'>or</span> <span
  m='365850'>recall</span> <span m='366195'>that</span> <span
  m='367140'>since</span> <span m='367810'>this</span> <span
  m='368340'>frequency</span> <span m='368820'>response</span> <span
  m='369700'>is</span> <span m='370690'>real-valued,</span> <span
  m='372930'>the</span> <span m='373530'>impulse</span> <span
  m='374060'>response,</span> <span m='374650'>in</span> <span
  m='374730'>other</span> <span m='374890'>words,</span> <span
  m='375120'>the</span> <span m='375220'>inverse</span> <span
  m='375590'>transform</span> <span m='376470'>is</span> <span
  m='376940'>an</span> <span m='377090'>even</span> <span
  m='377390'>function</span> <span m='377830'>of</span> <span
  m='377950'>time.</span> <span m='379150'>And</span> <span
  m='379840'>notice</span> <span m='380810'>also,</span> <span
  m='381970'>since</span> <span m='382310'>I</span> <span m='382350'>want</span>
  <span m='382550'>to</span> <span m='382590'>refer</span> <span
  m='382950'>back</span> <span m='383260'>to</span> <span
  m='383390'>this,</span> <span m='384170'>that</span> <span
  m='384840'>the</span> <span m='385120'>impulse</span> <span
  m='385550'>response</span> <span m='386010'>of</span> <span
  m='386070'>an</span> <span m='386170'>ideal</span> <span
  m='386620'>lowpass</span> <span m='387170'>filter,</span> <span
  m='388280'>in</span> <span m='388450'>fact,</span> <span m='389270'>is</span>
  <span m='389480'>non-causal.</span> <span m='390530'>That</span> <span
  m='390900'>follows,</span> <span m='391430'>from</span> <span
  m='391650'>among</span> <span m='391890'>other</span> <span
  m='392090'>things,</span> <span m='392490'>from</span> <span
  m='392620'>the</span> <span m='392700'>fact</span> <span
  m='393220'>that</span> <span m='393420'>it's</span> <span m='393560'>an</span>
  <span m='393660'>even</span> <span m='393920'>function.</span> </p><p><span
  m='394940'>But</span> <span m='395260'>keep</span> <span m='395490'>in</span>
  <span m='395600'>mind,</span> <span m='396060'>in</span> <span
  m='396190'>fact,</span> <span m='396730'>that</span> <span m='397070'>a</span>
  <span m='397150'>sine</span> <span m='397470'>x</span> <span
  m='397660'>over</span> <span m='397930'>x</span> <span
  m='398140'>function</span> <span m='399160'>goes</span> <span
  m='399440'>off</span> <span m='399620'>to</span> <span
  m='399770'>infinity</span> <span m='400250'>in</span> <span
  m='400350'>both</span> <span m='400650'>directions.</span> <span
  m='401680'>So</span> <span m='402470'>the</span> <span
  m='402600'>impulse</span> <span m='403000'>response</span> <span
  m='403510'>of</span> <span m='403600'>the</span> <span m='403730'>ideal</span>
  <span m='404130'>lowpass</span> <span m='404660'>filter</span> <span
  m='405570'>is</span> <span m='405720'>symmetric</span> <span
  m='406760'>and</span> <span m='407640'>continues</span> <span
  m='408250'>to</span> <span m='408350'>have</span> <span
  m='408620'>tails</span> <span m='409210'>off</span> <span m='409470'>to</span>
  <span m='409590'>plus</span> <span m='409900'>and</span> <span
  m='409920'>minus</span> <span m='410340'>infinity.</span> </p><p><span
  m='412680'>Now,</span> <span m='413500'>the</span> <span
  m='413760'>situation</span> <span m='414360'>is</span> <span
  m='414470'>basically</span> <span m='415200'>the</span> <span
  m='415330'>same</span> <span m='415890'>in</span> <span m='416650'>the</span>
  <span m='416850'>discrete-time</span> <span m='417640'>case.</span> <span
  m='419610'>Let's</span> <span m='419930'>look</span> <span
  m='420250'>at</span> <span m='420600'>the</span> <span
  m='421410'>frequency</span> <span m='421870'>response</span> <span
  m='422600'>and</span> <span m='422720'>associated</span> <span
  m='423340'>impulse</span> <span m='423770'>response</span> <span
  m='424520'>for</span> <span m='424710'>an</span> <span m='424790'>ideal</span>
  <span m='425530'>discrete-time</span> <span m='426610'>lowpass</span> <span
  m='427190'>filter.</span> <span m='428200'>So</span> <span
  m='428730'>once</span> <span m='428990'>again,</span> <span
  m='429840'>here</span> <span m='430350'>is</span> <span m='430950'>the</span>
  <span m='432430'>frequency</span> <span m='432970'>response</span> <span
  m='433660'>of</span> <span m='433790'>the</span> <span m='433940'>ideal</span>
  <span m='434300'>lowpass</span> <span m='434860'>filter.</span> <span
  m='436230'>And</span> <span m='436570'>below</span> <span
  m='436880'>what</span> <span m='437190'>I</span> <span m='437320'>show</span>
  <span m='438290'>the</span> <span m='438410'>impulse</span> <span
  m='438890'>response.</span> </p><p><span m='440000'>Again,</span> <span
  m='440630'>it's</span> <span m='441320'>a</span> <span m='441510'>sine</span>
  <span m='441850'>x</span> <span m='442070'>over</span> <span
  m='442390'>x</span> <span m='442600'>type</span> <span m='442850'>of</span>
  <span m='442970'>impulse</span> <span m='443440'>response.</span> <span
  m='444690'>And</span> <span m='446320'>again,</span> <span
  m='446770'>we</span> <span m='446900'>recognize</span> <span
  m='447890'>that</span> <span m='448310'>since</span> <span
  m='448620'>in</span> <span m='448680'>the</span> <span
  m='448760'>frequency</span> <span m='449300'>domain,</span> <span
  m='450290'>this</span> <span m='450480'>frequency</span> <span
  m='450980'>response</span> <span m='451760'>is</span> <span
  m='453050'>real-valued.</span> <span m='454760'>That</span> <span
  m='455040'>means,</span> <span m='455570'>as</span> <span m='455730'>a</span>
  <span m='455800'>consequence</span> <span m='456920'>of</span> <span
  m='457070'>the</span> <span m='457300'>properties</span> <span
  m='458270'>of</span> <span m='458960'>the</span> <span
  m='459060'>Fourier</span> <span m='459500'>transform</span> <span
  m='460140'>and</span> <span m='460200'>inverse</span> <span
  m='460620'>Fourier</span> <span m='461000'>transform,</span> <span
  m='462320'>that</span> <span m='463100'>the</span> <span
  m='463240'>impulse</span> <span m='463700'>response</span> <span
  m='464340'>is</span> <span m='464540'>an</span> <span m='464660'>even</span>
  <span m='465010'>function</span> <span m='465970'>in</span> <span
  m='466090'>the</span> <span m='466200'>time</span> <span
  m='466500'>domain.</span> <span m='467800'>And</span> <span
  m='468010'>also,</span> <span m='468560'>incidentally,</span> <span
  m='469500'>the</span> <span m='469800'>sine</span> <span m='470120'>x</span>
  <span m='470330'>over</span> <span m='470610'>x</span> <span
  m='470820'>function</span> <span m='471820'>goes</span> <span
  m='472180'>off</span> <span m='472390'>to</span> <span
  m='472530'>infinity,</span> <span m='473220'>again,</span> <span
  m='473560'>in</span> <span m='473630'>both</span> <span
  m='473880'>directions.</span> </p><p><span m='476790'>Now,</span> <span
  m='478290'>we've</span> <span m='478490'>talked</span> <span
  m='478790'>about</span> <span m='479040'>ideal</span> <span
  m='479460'>filters</span> <span m='480580'>in</span> <span
  m='480710'>this</span> <span m='480890'>discussion.</span> <span
  m='481650'>And</span> <span m='482550'>ideal</span> <span
  m='482920'>filters</span> <span m='483500'>all</span> <span
  m='483680'>are,</span> <span m='484160'>in</span> <span
  m='484290'>fact,</span> <span m='484640'>ideal</span> <span
  m='485150'>in</span> <span m='485240'>a</span> <span m='485280'>certain</span>
  <span m='485630'>sense.</span> <span m='486960'>What</span> <span
  m='487260'>they</span> <span m='487540'>do</span> <span
  m='487890'>ideally</span> <span m='488700'>is</span> <span
  m='489020'>they</span> <span m='489410'>pass</span> <span m='489760'>a</span>
  <span m='489820'>certain</span> <span m='490160'>band</span> <span
  m='490470'>of</span> <span m='490550'>frequencies</span> <span
  m='491570'>exactly</span> <span m='492790'>and</span> <span
  m='493640'>they</span> <span m='494310'>reject</span> <span
  m='495690'>a</span> <span m='495770'>band</span> <span m='496060'>of</span>
  <span m='496140'>frequencies</span> <span m='496770'>exactly.</span>
  </p><p><span m='499010'>On</span> <span m='499120'>the</span> <span
  m='499230'>other</span> <span m='499390'>hand,</span> <span
  m='499900'>there</span> <span m='500080'>are</span> <span
  m='500110'>many</span> <span m='500350'>filtering</span> <span
  m='500850'>problems</span> <span m='501700'>in</span> <span
  m='501900'>which,</span> <span m='503330'>generally,</span> <span
  m='504260'>we</span> <span m='504450'>don't</span> <span
  m='504780'>have</span> <span m='505280'>a</span> <span m='505330'>sharp</span>
  <span m='505700'>distinction</span> <span m='506330'>between</span> <span
  m='506680'>the</span> <span m='506750'>frequencies</span> <span
  m='507380'>we</span> <span m='507490'>want</span> <span m='507720'>to</span>
  <span m='508080'>pass</span> <span m='508530'>and</span> <span
  m='508590'>the</span> <span m='508670'>frequencies</span> <span
  m='509260'>we</span> <span m='509900'>want</span> <span m='510170'>to</span>
  <span m='510380'>reject.</span> <span m='511260'>One</span> <span
  m='511510'>example</span> <span m='511990'>of</span> <span
  m='512100'>this</span> <span m='512409'>that's</span> <span
  m='512620'>elaborated</span> <span m='513230'>on</span> <span
  m='513440'>in</span> <span m='513510'>the</span> <span m='513630'>text</span>
  <span m='514150'>is</span> <span m='514990'>the</span> <span
  m='515090'>design</span> <span m='515610'>of</span> <span m='515700'>an</span>
  <span m='515789'>automotive</span> <span m='516280'>suspension</span> <span
  m='516860'>system,</span> <span m='517320'>which,</span> <span
  m='517520'>in</span> <span m='517610'>fact,</span> <span m='518179'>is</span>
  <span m='518490'>the</span> <span m='518580'>design</span> <span
  m='519309'>of</span> <span m='520460'>a</span> <span m='520539'>lowpass</span>
  <span m='521140'>filter.</span> </p><p><span m='522490'>And</span> <span
  m='522830'>basically</span> <span m='523370'>what</span> <span
  m='523549'>you</span> <span m='523640'>want</span> <span m='523820'>to</span>
  <span m='523890'>do</span> <span m='524049'>in</span> <span
  m='524140'>a</span> <span m='524200'>case</span> <span m='524520'>like</span>
  <span m='524780'>that</span> <span m='525540'>is</span> <span
  m='526550'>filter</span> <span m='527120'>out</span> <span
  m='527610'>or</span> <span m='527810'>attenuate</span> <span
  m='528960'>very</span> <span m='529230'>rapid</span> <span
  m='529620'>road</span> <span m='529900'>variations</span> <span
  m='531230'>and</span> <span m='531480'>keep</span> <span m='531920'>the</span>
  <span m='532320'>lower</span> <span m='533460'>variations</span> <span
  m='534430'>in,</span> <span m='534850'>of</span> <span
  m='534980'>course,</span> <span m='535300'>elevation</span> <span
  m='535880'>of</span> <span m='535940'>the</span> <span
  m='536020'>highway</span> <span m='536620'>or</span> <span
  m='537290'>road.</span> <span m='538350'>And</span> <span
  m='538760'>what</span> <span m='538990'>you</span> <span m='539100'>can</span>
  <span m='539230'>see</span> <span m='540270'>intuitively</span> <span
  m='541170'>is</span> <span m='541450'>that</span> <span
  m='542030'>there</span> <span m='542250'>isn't</span> <span
  m='542490'>really</span> <span m='542880'>a</span> <span
  m='542920'>very</span> <span m='543180'>sharp</span> <span
  m='543950'>distinction</span> <span m='544530'>or</span> <span
  m='544600'>sharp</span> <span m='544960'>cut-off</span> <span
  m='545910'>between</span> <span m='546600'>what</span> <span
  m='546940'>you</span> <span m='547070'>would</span> <span
  m='547190'>logically</span> <span m='547680'>call</span> <span
  m='548380'>the</span> <span m='548470'>low</span> <span
  m='548670'>frequencies</span> <span m='549640'>and</span> <span
  m='549910'>what</span> <span m='550110'>you</span> <span
  m='550210'>would</span> <span m='550330'>call</span> <span
  m='550930'>the</span> <span m='551020'>high</span> <span
  m='551200'>frequencies.</span> </p><p><span m='553220'>Now,</span> <span
  m='553450'>also</span> <span m='553790'>somewhat</span> <span
  m='554180'>related</span> <span m='554670'>to</span> <span
  m='554800'>this</span> <span m='555180'>is</span> <span m='555330'>the</span>
  <span m='555410'>fact</span> <span m='555990'>that</span> <span
  m='557660'>as</span> <span m='557850'>we've</span> <span
  m='558000'>seen</span> <span m='558960'>in</span> <span m='559080'>the</span>
  <span m='559190'>time</span> <span m='559550'>domain,</span> <span
  m='560020'>these</span> <span m='560210'>ideal</span> <span
  m='560620'>filters</span> <span m='561170'>have</span> <span
  m='561700'>a</span> <span m='561790'>very</span> <span
  m='562350'>particular</span> <span m='562920'>kind</span> <span
  m='563160'>of</span> <span m='563250'>character.</span> <span
  m='564300'>For</span> <span m='564420'>example,</span> <span
  m='564900'>let's</span> <span m='565150'>look</span> <span
  m='565350'>back</span> <span m='565770'>at</span> <span m='566240'>the</span>
  <span m='567850'>ideal</span> <span m='568660'>lowpass</span> <span
  m='569340'>filter.</span> <span m='569900'>And</span> <span
  m='570940'>we</span> <span m='571100'>saw</span> <span m='571670'>the</span>
  <span m='571950'>impulse</span> <span m='572440'>response.</span> <span
  m='574190'>The</span> <span m='574270'>impulse</span> <span
  m='574690'>response</span> <span m='575260'>is</span> <span
  m='575440'>what</span> <span m='575720'>we had</span> <span
  m='575920'>shown</span> <span m='576250'>here.</span> </p><p><span
  m='577090'>Let's</span> <span m='577340'>now</span> <span
  m='577540'>look</span> <span m='577940'>at</span> <span m='578340'>the</span>
  <span m='578770'>step</span> <span m='579280'>response</span> <span
  m='580070'>of</span> <span m='580230'>the</span> <span
  m='580320'>discrete-time</span> <span m='581860'>ideal</span> <span
  m='582620'>lowpass</span> <span m='583230'>filter.</span> <span
  m='584110'>And</span> <span m='584260'>notice</span> <span
  m='584670'>the</span> <span m='584750'>fact</span> <span
  m='585270'>that</span> <span m='585580'>it</span> <span m='585680'>has</span>
  <span m='585910'>a</span> <span m='586000'>tail</span> <span
  m='586410'>that</span> <span m='586490'>oscillates.</span> <span
  m='587590'>And</span> <span m='587790'>when</span> <span m='587940'>the</span>
  <span m='588030'>step</span> <span m='588460'>hits,</span> <span
  m='589180'>in</span> <span m='589310'>fact,</span> <span m='589760'>it</span>
  <span m='589880'>has</span> <span m='590300'>an</span> <span
  m='590470'>oscillatory</span> <span m='591220'>behavior.</span> </p><p><span
  m='592720'>Now,</span> <span m='593610'>exactly</span> <span
  m='594530'>the</span> <span m='594630'>same</span> <span
  m='595260'>situation</span> <span m='596050'>occurs</span> <span
  m='597450'>in</span> <span m='597670'>continuous-time.</span> <span
  m='599100'>Let's</span> <span m='599390'>look</span> <span
  m='599670'>at</span> <span m='600370'>the</span> <span m='601060'>step</span>
  <span m='601460'>response</span> <span m='602310'>of</span> <span
  m='603310'>the</span> <span m='603650'>continuous-time</span> <span
  m='604900'>ideal</span> <span m='605330'>lowpass</span> <span
  m='605900'>filter.</span> <span m='607310'>And</span> <span
  m='608210'>what</span> <span m='608370'>we</span> <span m='608520'>see</span>
  <span m='608990'>is</span> <span m='609190'>that</span> <span
  m='609670'>when</span> <span m='609850'>a</span> <span m='609900'>step</span>
  <span m='610360'>hits</span> <span m='611350'>then,</span> <span
  m='611610'>in</span> <span m='611710'>fact,</span> <span m='612370'>we</span>
  <span m='612540'>get</span> <span m='612950'>an</span> <span
  m='613090'>oscillation.</span> </p><p><span m='614480'>And</span> <span
  m='615530'>very</span> <span m='615830'>often,</span> <span
  m='616680'>that</span> <span m='616890'>oscillation</span> <span
  m='617820'>is</span> <span m='618310'>something</span> <span
  m='618740'>that's</span> <span m='618930'>undesirable.</span> <span
  m='619670'>For</span> <span m='619830'>example,</span> <span
  m='620750'>if</span> <span m='620900'>you</span> <span m='621010'>were</span>
  <span m='621110'>designing</span> <span m='621840'>an</span> <span
  m='621970'>automotive</span> <span m='622460'>suspension</span> <span
  m='623040'>system</span> <span m='624200'>and</span> <span
  m='624600'>you</span> <span m='624730'>hit</span> <span m='624890'>a</span>
  <span m='624990'>curve,</span> <span m='625500'>which</span> <span
  m='625730'>is</span> <span m='626320'>a</span> <span m='626400'>step</span>
  <span m='627100'>input,</span> <span m='628140'>in</span> <span
  m='628280'>fact,</span> <span m='628850'>you</span> <span
  m='629010'>probably</span> <span m='629560'>would</span> <span
  m='629770'>not</span> <span m='630020'>like</span> <span m='630660'>to</span>
  <span m='630780'>have</span> <span m='631280'>the</span> <span
  m='631740'>automobile</span> <span m='632910'>oscillating,</span> <span
  m='634660'>dying</span> <span m='634970'>down</span> <span
  m='635420'>in</span> <span m='635630'>oscillation.</span> </p><p><span
  m='638260'>Now</span> <span m='638800'>there's</span> <span
  m='638980'>another</span> <span m='639410'>very</span> <span
  m='639740'>important</span> <span m='640210'>point,</span> <span
  m='640800'>which</span> <span m='641230'>again,</span> <span
  m='641790'>we</span> <span m='641930'>can</span> <span m='642080'>see</span>
  <span m='642510'>either</span> <span m='642690'>in</span> <span
  m='642740'>continuous-time</span> <span m='643540'>or</span> <span
  m='643620'>discrete-time,</span> <span m='644960'>which</span> <span
  m='645270'>is</span> <span m='645560'>that</span> <span m='646150'>even</span>
  <span m='646640'>if</span> <span m='647570'>we</span> <span m='647770'>want
  it</span> <span m='648220'>to</span> <span m='648310'>have</span> <span
  m='649010'>an</span> <span m='649200'>ideal</span> <span
  m='649600'>filter,</span> <span m='651240'>the</span> <span
  m='651380'>ideal</span> <span m='651770'>filter</span> <span
  m='652390'>has</span> <span m='652640'>another</span> <span
  m='652990'>problem</span> <span m='653680'>if</span> <span
  m='654180'>we</span> <span m='654390'>want</span> <span m='654880'>to</span>
  <span m='655150'>attempt</span> <span m='655630'>to</span> <span
  m='655910'>implement</span> <span m='656400'>it</span> <span
  m='656490'>in</span> <span m='656620'>real</span> <span
  m='656880'>time.</span> </p><p><span m='657960'>What's</span> <span
  m='658210'>the</span> <span m='658290'>problem?</span> <span
  m='659180'>The</span> <span m='659280'>problem</span> <span
  m='660150'>is</span> <span m='661420'>that</span> <span
  m='661960'>since</span> <span m='662420'>the</span> <span
  m='662590'>impulse</span> <span m='663070'>response</span> <span
  m='663590'>is</span> <span m='663740'>even</span> <span m='664080'>and,</span>
  <span m='664420'>in</span> <span m='664540'>fact,</span> <span
  m='665180'>has</span> <span m='665420'>tails</span> <span
  m='665950'>that</span> <span m='666100'>go</span> <span m='666290'>off</span>
  <span m='666510'>to</span> <span m='666600'>plus</span> <span
  m='666900'>and</span> <span m='666980'>minus</span> <span
  m='667320'>infinity,</span> <span m='668410'>it's</span> <span
  m='668650'>non-causal.</span> <span m='670190'>So</span> <span
  m='671370'>if,</span> <span m='671670'>in</span> <span m='671800'>fact,</span>
  <span m='672430'>we</span> <span m='672580'>want</span> <span
  m='672770'>to</span> <span m='672820'>build</span> <span m='673290'>a</span>
  <span m='673350'>filter</span> <span m='674580'>and</span> <span
  m='674720'>the</span> <span m='674790'>filter</span> <span
  m='675320'>is</span> <span m='675460'>restricted</span> <span
  m='676050'>to</span> <span m='676140'>operate</span> <span
  m='676620'>in</span> <span m='676720'>real</span> <span
  m='677000'>time,</span> <span m='678020'>then,</span> <span
  m='679230'>in</span> <span m='679410'>fact,</span> <span m='680070'>we</span>
  <span m='680290'>can't</span> <span m='680960'>build</span> <span
  m='681450'>an</span> <span m='681640'>ideal</span> <span
  m='681980'>filter.</span> </p><p><span m='683920'>So</span> <span
  m='684450'>what</span> <span m='684670'>that</span> <span
  m='684930'>says</span> <span m='685300'>is</span> <span
  m='685460'>that,</span> <span m='686390'>in</span> <span
  m='686580'>practice,</span> <span m='687280'>although</span> <span
  m='687670'>ideal</span> <span m='688080'>filters</span> <span
  m='688870'>are</span> <span m='689590'>nice</span> <span m='689970'>to</span>
  <span m='690160'>think</span> <span m='690490'>about</span> <span
  m='691040'>and</span> <span m='691420'>perhaps</span> <span
  m='691810'>relate</span> <span m='692180'>to</span> <span
  m='692260'>practical</span> <span m='692800'>problems,</span> <span
  m='694040'>more</span> <span m='694280'>typically</span> <span
  m='695710'>what</span> <span m='696180'>we</span> <span
  m='696350'>consider</span> <span m='697040'>are</span> <span
  m='697780'>nonideal</span> <span m='698600'>filters</span> <span
  m='699830'>and</span> <span m='700550'>in</span> <span m='701130'>the</span>
  <span m='701720'>discrete-time</span> <span m='702430'>case,</span> <span
  m='703000'>a</span> <span m='703130'>nonideal</span> <span
  m='703780'>filter</span> <span m='704790'>then</span> <span
  m='705620'>we</span> <span m='705680'>would</span> <span
  m='706140'>have</span> <span m='706700'>a</span> <span
  m='706810'>characteristic</span> <span m='707730'>somewhat</span> <span
  m='708480'>like</span> <span m='708850'>I've</span> <span
  m='708980'>indicated</span> <span m='709520'>here.</span> <span
  m='710430'>Where</span> <span m='711000'>instead</span> <span
  m='711420'>of</span> <span m='711800'>a</span> <span m='711910'>very</span>
  <span m='712220'>rapid</span> <span m='712710'>transition</span> <span
  m='713730'>from</span> <span m='714570'>passband</span> <span
  m='715210'>to</span> <span m='715300'>stopband,</span> <span
  m='716580'>there</span> <span m='716670'>would</span> <span
  m='716850'>be</span> <span m='717270'>a</span> <span m='717350'>more</span>
  <span m='717590'>gradual</span> <span m='718170'>transition</span> <span
  m='719780'>with</span> <span m='720250'>a</span> <span
  m='720330'>passband</span> <span m='720980'>cutoff</span> <span
  m='721360'>frequency</span> <span m='722670'>and</span> <span
  m='723750'>a</span> <span m='724260'>stopband</span> <span
  m='725260'>cutoff</span> <span m='725670'>frequency.</span> <span
  m='726960'>And</span> <span m='727610'>perhaps</span> <span
  m='728100'>also</span> <span m='728520'>instead</span> <span
  m='728890'>of</span> <span m='728980'>having</span> <span m='729500'>an</span>
  <span m='729620'>exactly</span> <span m='730230'>flat</span> <span
  m='731170'>characteristic</span> <span m='732080'>in</span> <span
  m='732320'>the</span> <span m='732380'>stopband</span> <span
  m='733500'>in</span> <span m='733580'>the</span> <span
  m='733660'>passband,</span> <span m='734930'>we</span> <span
  m='735080'>would</span> <span m='735210'>allow</span> <span
  m='735810'>a</span> <span m='735890'>certain</span> <span
  m='736240'>amount</span> <span m='736530'>of</span> <span
  m='736640'>ripple.</span> </p><p><span m='738180'>We</span> <span
  m='738320'>also</span> <span m='738690'>have</span> <span
  m='739130'>exactly</span> <span m='740260'>the</span> <span
  m='740350'>same</span> <span m='740640'>situation</span> <span
  m='741600'>in</span> <span m='741760'>continuous-time,</span> <span
  m='743350'>where</span> <span m='743580'>here</span> <span
  m='744060'>we'll</span> <span m='744270'>just</span> <span
  m='744460'>simply</span> <span m='744790'>change</span> <span
  m='745170'>our</span> <span m='745250'>frequency</span> <span
  m='745840'>axis</span> <span m='746850'>to</span> <span m='747360'>a</span>
  <span m='747560'>continuous</span> <span m='748180'>frequency</span> <span
  m='748690'>axis</span> <span m='749330'>instead</span> <span
  m='749730'>of</span> <span m='749980'>the</span> <span
  m='750080'>discrete</span> <span m='750480'>frequency</span> <span
  m='750990'>axis.</span> <span m='751920'>Again,</span> <span
  m='752500'>we</span> <span m='752650'>would</span> <span
  m='752840'>think</span> <span m='753110'>in</span> <span
  m='753230'>terms</span> <span m='753650'>of</span> <span m='754100'>an</span>
  <span m='754260'>allowable</span> <span m='754850'>passband</span> <span
  m='755460'>ripple,</span> <span m='756340'>a</span> <span
  m='756440'>transition</span> <span m='758880'>from</span> <span
  m='759040'>passband</span> <span m='759710'>to</span> <span
  m='759800'>stopband</span> <span m='761000'>with</span> <span
  m='761400'>a</span> <span m='761910'>passband</span> <span
  m='762480'>cutoff</span> <span m='762860'>frequency</span> <span
  m='763660'>and</span> <span m='763820'>a</span> <span
  m='763860'>stopband</span> <span m='764690'>cutoff</span> <span
  m='765000'>frequency.</span> </p><p><span m='766940'>So</span> <span
  m='768050'>the</span> <span m='768140'>notion</span> <span
  m='768540'>here</span> <span m='769010'>is</span> <span
  m='769330'>that,</span> <span m='770110'>again,</span> <span
  m='770570'>ideal</span> <span m='771010'>filters</span> <span
  m='771550'>are</span> <span m='771740'>ideal</span> <span m='772120'>in</span>
  <span m='772200'>some</span> <span m='772480'>respects,</span> <span
  m='773220'>not</span> <span m='773420'>ideal</span> <span m='774100'>in</span>
  <span m='774240'>other</span> <span m='774450'>respects.</span> <span
  m='775100'>And</span> <span m='775270'>for</span> <span m='775380'>many</span>
  <span m='776380'>practical</span> <span m='776910'>problems,</span> <span
  m='777680'>we</span> <span m='777850'>may</span> <span m='778030'>not</span>
  <span m='778320'>want</span> <span m='778660'>them.</span> <span
  m='779360'>And</span> <span m='779520'>even</span> <span m='779730'>if</span>
  <span m='779860'>we</span> <span m='779960'>did</span> <span
  m='780190'>want</span> <span m='780540'>them,</span> <span
  m='781040'>we</span> <span m='781180'>may</span> <span m='781320'>not</span>
  <span m='781580'>be</span> <span m='781790'>able</span> <span
  m='781990'>to</span> <span m='782090'>get</span> <span m='782400'>them,</span>
  <span m='783330'>perhaps</span> <span m='783790'>because</span> <span
  m='784260'>of</span> <span m='784360'>this</span> <span
  m='784560'>issue</span> <span m='784820'>of</span> <span
  m='784930'>causality.</span> </p><p><span m='786280'>Even</span> <span
  m='786560'>if</span> <span m='786660'>causality</span> <span
  m='787360'>is</span> <span m='787510'>not</span> <span m='787720'>an</span>
  <span m='787810'>issue,</span> <span m='789170'>what</span> <span
  m='789340'>happens</span> <span m='790020'>in</span> <span
  m='790660'>filter</span> <span m='791050'>design</span> <span
  m='791660'>and</span> <span m='791800'>implementation,</span> <span
  m='792620'>in</span> <span m='792740'>fact,</span> <span m='793690'>is</span>
  <span m='794130'>that</span> <span m='794940'>the</span> <span
  m='795080'>sharper</span> <span m='796430'>you</span> <span
  m='796660'>attempt</span> <span m='797080'>to</span> <span
  m='797190'>make</span> <span m='797420'>the</span> <span
  m='797530'>cutoff,</span> <span m='799380'>the</span> <span
  m='799510'>more</span> <span m='799780'>expensive,</span> <span
  m='800380'>in</span> <span m='800470'>some</span> <span
  m='800720'>sense,</span> <span m='801050'>the</span> <span
  m='801140'>filter</span> <span m='801500'>becomes,</span> <span
  m='802570'>either</span> <span m='802880'>in</span> <span
  m='802950'>terms</span> <span m='803330'>of</span> <span
  m='803430'>components,</span> <span m='804460'>in</span> <span
  m='804670'>continuous-time,</span> <span m='805650'>or</span> <span
  m='805870'>in</span> <span m='805940'>terms</span> <span m='806220'>of</span>
  <span m='806310'>computation</span> <span m='807810'>in</span> <span
  m='807960'>discrete-time.</span> <span m='809130'>And</span> <span
  m='809280'>so</span> <span m='809760'>there</span> <span m='810370'>are</span>
  <span m='810920'>these</span> <span m='811390'>whole</span> <span
  m='811765'>variety</span> <span m='812330'>of</span> <span
  m='812410'>issues</span> <span m='813360'>that</span> <span
  m='813870'>really</span> <span m='814970'>make</span> <span
  m='815250'>it</span> <span m='815320'>important</span> <span
  m='815970'>to</span> <span m='816350'>understand</span> <span
  m='817590'>the</span> <span m='817990'>notion</span> <span
  m='819220'>nonideal</span> <span m='819860'>filters.</span> </p><p><span
  m='821790'>Now,</span> <span m='822290'>just</span> <span m='822600'>to</span>
  <span m='822950'>illustrate</span> <span m='823650'>as</span> <span
  m='823860'>an</span> <span m='823940'>example,</span> <span
  m='825280'>let</span> <span m='825460'>me</span> <span
  m='825880'>remind</span> <span m='826350'>you</span> <span
  m='826720'>of</span> <span m='827520'>one</span> <span
  m='828150'>example</span> <span m='828890'>of</span> <span
  m='829620'>what,</span> <span m='829960'>in</span> <span
  m='830110'>fact,</span> <span m='830510'>is</span> <span m='830650'>a</span>
  <span m='830710'>nonideal</span> <span m='832010'>lowpass</span> <span
  m='832630'>filter.</span> <span m='833640'>And</span> <span
  m='834580'>we</span> <span m='834960'>have</span> <span
  m='835160'>looked</span> <span m='835390'>previously</span> <span
  m='836570'>at</span> <span m='837040'>the</span> <span
  m='837190'>associated</span> <span m='837820'>differential</span> <span
  m='838390'>equation.</span> </p><p><span m='839660'>Let</span> <span
  m='839870'>me</span> <span m='840030'>now,</span> <span m='840410'>in</span>
  <span m='840560'>fact,</span> <span m='840950'>relate</span> <span
  m='841260'>it</span> <span m='841610'>to</span> <span m='841810'>a</span>
  <span m='841860'>circuit,</span> <span m='843930'>and</span> <span
  m='844160'>in</span> <span m='844270'>particular</span> <span
  m='845070'>an</span> <span m='845190'>RC</span> <span
  m='845590'>circuit,</span> <span m='847050'>where</span> <span
  m='847630'>the</span> <span m='847800'>output</span> <span
  m='848320'>could</span> <span m='848480'>either</span> <span
  m='848730'>be</span> <span m='849620'>across</span> <span
  m='850050'>the</span> <span m='850140'>capacitor</span> <span
  m='850930'>or</span> <span m='851240'>the</span> <span
  m='851400'>output</span> <span m='852020'>can</span> <span
  m='852120'>be</span> <span m='852280'>across</span> <span
  m='852670'>the</span> <span m='852750'>resistor.</span> <span
  m='853840'>So</span> <span m='854600'>in</span> <span
  m='854730'>effect,</span> <span m='855070'>we</span> <span
  m='855160'>have</span> <span m='855320'>two</span> <span
  m='855510'>systems</span> <span m='856060'>here.</span> <span
  m='856340'>We</span> <span m='856470'>have</span> <span m='857280'>a</span>
  <span m='857350'>system,</span> <span m='858140'>which</span> <span
  m='858570'>is</span> <span m='858980'>the</span> <span
  m='859170'>system</span> <span m='859560'>function</span> <span
  m='860090'>from</span> <span m='860470'>the</span> <span
  m='860540'>voltage</span> <span m='860910'>source</span> <span
  m='861260'>input</span> <span m='861740'>to</span> <span m='861830'>the</span>
  <span m='861930'>capacitor</span> <span m='862570'>output,</span> <span
  m='863530'>the</span> <span m='863650'>system</span> <span
  m='864490'>from</span> <span m='865130'>the</span> <span
  m='865390'>voltage</span> <span m='865790'>source</span> <span
  m='866160'>input</span> <span m='866870'>to</span> <span m='867770'>the</span>
  <span m='868320'>resistor</span> <span m='868470'>output.</span> </p><p><span
  m='869450'>And,</span> <span m='869600'>in</span> <span
  m='869690'>fact,</span> <span m='870380'>just</span> <span
  m='870730'>applying</span> <span m='871090'>Kirchhoff's</span> <span
  m='871680'>Voltage</span> <span m='872110'>Law</span> <span
  m='872520'>to</span> <span m='872630'>this,</span> <span m='872890'>we</span>
  <span m='873000'>can</span> <span m='873150'>relate</span> <span
  m='873500'>those</span> <span m='873910'>in</span> <span m='874020'>a</span>
  <span m='874060'>very</span> <span m='874280'>straightforward</span> <span
  m='875080'>way.</span> <span m='875840'>It's</span> <span
  m='876010'>very</span> <span m='876200'>straightforward</span> <span
  m='876900'>to</span> <span m='876970'>verify</span> <span
  m='878230'>that</span> <span m='879460'>the</span> <span
  m='880300'>system</span> <span m='881010'>from</span> <span
  m='881540'>input</span> <span m='882110'>to</span> <span
  m='882610'>resistor</span> <span m='882740'>output</span> <span
  m='883740'>is</span> <span m='884050'>simply</span> <span
  m='884660'>the</span> <span m='884820'>identity</span> <span
  m='885370'>system</span> <span m='886430'>with</span> <span
  m='887010'>the</span> <span m='887140'>capacitor</span> <span
  m='887970'>output</span> <span m='888480'>subtracted</span> <span
  m='889100'>from</span> <span m='889430'>it.</span> </p><p><span
  m='891480'>Now,</span> <span m='892180'>we</span> <span m='892340'>can</span>
  <span m='892480'>write</span> <span m='892860'>the</span> <span
  m='893090'>differential</span> <span m='893670'>equation</span> <span
  m='894420'>for</span> <span m='894850'>either</span> <span
  m='895170'>of</span> <span m='895230'>these</span> <span
  m='895430'>systems</span> <span m='896230'>and,</span> <span
  m='897150'>as</span> <span m='897430'>we</span> <span m='897540'>talked</span>
  <span m='897840'>about</span> <span m='898060'>last</span> <span
  m='898430'>time</span> <span m='899360'>in</span> <span m='899530'>the</span>
  <span m='899600'>last</span> <span m='899810'>several</span> <span
  m='900120'>lectures,</span> <span m='901350'>solve</span> <span
  m='901840'>that</span> <span m='902030'>equation</span> <span
  m='902580'>using</span> <span m='903400'>and</span> <span
  m='903860'>exploiting</span> <span m='904420'>the</span> <span
  m='904500'>properties</span> <span m='905040'>of</span> <span
  m='905090'>the</span> <span m='905160'>Fourier</span> <span
  m='905600'>transform.</span> <span m='906730'>And</span> <span
  m='906880'>in</span> <span m='906960'>fact,</span> <span m='908110'>if</span>
  <span m='908310'>we</span> <span m='908410'>look</span> <span
  m='908640'>at</span> <span m='908810'>the</span> <span
  m='909020'>differential</span> <span m='909650'>equation</span> <span
  m='911000'>relating</span> <span m='911790'>the</span> <span
  m='912050'>capacitor</span> <span m='912750'>output</span> <span
  m='913730'>to</span> <span m='914280'>the</span> <span
  m='914400'>voltage</span> <span m='914770'>source</span> <span
  m='915130'>input,</span> <span m='916700'>we</span> <span
  m='916830'>recognize</span> <span m='917550'>that</span> <span
  m='917680'>this</span> <span m='917900'>is</span> <span m='918050'>an</span>
  <span m='918140'>example</span> <span m='918980'>that,</span> <span
  m='919290'>in</span> <span m='919430'>effect,</span> <span
  m='919840'>we've</span> <span m='920000'>solved</span> <span
  m='920390'>previously.</span> </p><p><span m='921740'>And</span> <span
  m='922220'>so</span> <span m='922910'>just</span> <span
  m='923150'>working</span> <span m='923490'>our</span> <span
  m='923630'>way</span> <span m='923980'>down,</span> <span
  m='924940'>applying</span> <span m='925520'>the</span> <span
  m='925810'>Fourier</span> <span m='926290'>transform</span> <span
  m='927030'>to</span> <span m='927130'>the</span> <span
  m='927220'>differential</span> <span m='927820'>equation</span> <span
  m='929000'>and</span> <span m='929400'>generating</span> <span
  m='930030'>the</span> <span m='930110'>system</span> <span
  m='930540'>function</span> <span m='931100'>by</span> <span
  m='931260'>taking</span> <span m='931700'>the</span> <span
  m='931800'>ratio</span> <span m='932530'>of</span> <span m='932640'>the</span>
  <span m='932710'>capacitor</span> <span m='933300'>voltage</span> <span
  m='934500'>or</span> <span m='934660'>its</span> <span
  m='934940'>Fourier</span> <span m='935280'>transform</span> <span
  m='936030'>to</span> <span m='936210'>the</span> <span
  m='936310'>Fourier</span> <span m='936650'>transform</span> <span
  m='936960'>of</span> <span m='937270'>the</span> <span
  m='937360'>source,</span> <span m='938360'>we</span> <span
  m='938540'>then</span> <span m='938770'>have</span> <span
  m='939490'>the</span> <span m='939570'>system</span> <span
  m='940020'>function</span> <span m='940690'>associated</span> <span
  m='942030'>with</span> <span m='942220'>the</span> <span
  m='942290'>system</span> <span m='942830'>for</span> <span
  m='942950'>which</span> <span m='943230'>the</span> <span
  m='943410'>output</span> <span m='944070'>is</span> <span
  m='944650'>the</span> <span m='944760'>capacitor</span> <span
  m='945370'>voltage.</span> <span m='946550'>Or</span> <span
  m='947030'>if</span> <span m='947350'>we</span> <span m='947490'>solve</span>
  <span m='947940'>instead</span> <span m='948600'>for</span> <span
  m='948670'>the</span> <span m='948760'>system</span> <span
  m='949130'>function</span> <span m='949770'>associated</span> <span
  m='950710'>with</span> <span m='951520'>the</span> <span
  m='952180'>resistor</span> <span m='952320'>output,</span> <span
  m='953630'>we</span> <span m='953880'>can</span> <span
  m='954050'>simply</span> <span m='954450'>subtract</span> <span
  m='955655'>H1</span> <span m='956090'>from</span> <span
  m='956300'>unity.</span> <span m='957390'>And</span> <span
  m='957820'>the</span> <span m='957890'>system</span> <span
  m='958290'>function</span> <span m='958750'>that</span> <span
  m='958860'>we</span> <span m='958980'>get</span> <span m='959210'>in</span>
  <span m='959290'>that</span> <span m='959530'>case</span> <span
  m='960080'>is</span> <span m='960430'>the</span> <span
  m='960510'>system</span> <span m='960900'>function</span> <span
  m='961650'>that</span> <span m='961780'>I</span> <span m='961850'>show</span>
  <span m='962190'>here.</span> </p><p><span m='963040'>So</span> <span
  m='963740'>we</span> <span m='963900'>have,</span> <span
  m='964770'>now,</span> <span m='965690'>two</span> <span
  m='966050'>system</span> <span m='966490'>functions,</span> <span
  m='967110'>one</span> <span m='967320'>for</span> <span m='967420'>the</span>
  <span m='967510'>capacitor</span> <span m='968170'>output,</span> <span
  m='968980'>the</span> <span m='969120'>other</span> <span
  m='969380'>for</span> <span m='969520'>the</span> <span
  m='970050'>resistor</span> <span m='970190'>output.</span> <span
  m='971480'>And</span> <span m='972610'>one,</span> <span m='973260'>the</span>
  <span m='973370'>first,</span> <span m='973940'>corresponding</span> <span
  m='974700'>to</span> <span m='974820'>the</span> <span
  m='974910'>capacitor</span> <span m='975540'>output,</span> <span
  m='976470'>in</span> <span m='976610'>fact,</span> <span m='977130'>if</span>
  <span m='977350'>we</span> <span m='977490'>plot</span> <span
  m='977890'>it</span> <span m='978150'>on</span> <span m='978290'>a</span>
  <span m='978360'>linear</span> <span m='978760'>amplitude</span> <span
  m='979260'>scale,</span> <span m='980520'>looks</span> <span
  m='980830'>like</span> <span m='981100'>this.</span> <span
  m='981430'>And</span> <span m='981520'>as</span> <span m='981650'>you</span>
  <span m='981810'>can</span> <span m='981970'>see,</span> <span
  m='982490'>and</span> <span m='982590'>as</span> <span m='982730'>we</span>
  <span m='982840'>saw</span> <span m='983080'>last</span> <span
  m='983450'>time,</span> <span m='983840'>is</span> <span m='984680'>an</span>
  <span m='984760'>approximation</span> <span m='986100'>to</span> <span
  m='986250'>a</span> <span m='986340'>lowpass</span> <span
  m='986960'>filter.</span> <span m='987630'>It</span> <span
  m='987790'>is,</span> <span m='987970'>in</span> <span m='988080'>fact,</span>
  <span m='988490'>and</span> <span m='988640'>nonideal</span> <span
  m='989280'>lowpass</span> <span m='989860'>filter,</span> <span
  m='990890'>whereas</span> <span m='991820'>the</span> <span
  m='993000'>resistor</span> <span m='993120'>output</span> <span
  m='993770'>is</span> <span m='995400'>an</span> <span
  m='995520'>approximation</span> <span m='997010'>to</span> <span
  m='997210'>a</span> <span m='997290'>highpass</span> <span
  m='997920'>filter,</span> <span m='998440'>or</span> <span
  m='998990'>in</span> <span m='999150'>effect,</span> <span m='999950'>a</span>
  <span m='1000050'>nonideal</span> <span m='1000760'>highpass</span> <span
  m='1001320'>filter.</span> </p><p><span m='1002200'>So</span> <span
  m='1002720'>in</span> <span m='1002890'>one</span> <span
  m='1003140'>case,</span> <span m='1003470'>just</span> <span
  m='1003670'>comparing</span> <span m='1004200'>the</span> <span
  m='1004300'>two,</span> <span m='1004600'>we</span> <span
  m='1004750'>have</span> <span m='1005530'>a</span> <span
  m='1005640'>lowpass</span> <span m='1006230'>filter</span> <span
  m='1006860'>as</span> <span m='1007700'>the</span> <span
  m='1007900'>capacitor</span> <span m='1008540'>output</span> <span
  m='1009030'>associated</span> <span m='1009450'>with</span> <span
  m='1009540'>the</span> <span m='1009630'>capacitor</span> <span
  m='1010210'>output,</span> <span m='1011090'>and</span> <span
  m='1011250'>a</span> <span m='1011290'>highpass</span> <span
  m='1011910'>filter</span> <span m='1012550'>associated</span> <span
  m='1013440'>with</span> <span m='1013700'>the</span> <span
  m='1014130'>resistor</span> <span m='1014660'>output.</span> </p><p><span
  m='1016100'>Let's</span> <span m='1016300'>just</span> <span
  m='1016550'>quickly</span> <span m='1017560'>look</span> <span
  m='1017860'>at</span> <span m='1017930'>that</span> <span
  m='1018140'>example</span> <span m='1018710'>now,</span> <span
  m='1019400'>looking</span> <span m='1019920'>on</span> <span
  m='1020070'>a</span> <span m='1020110'>Bode</span> <span
  m='1020390'>plot,</span> <span m='1021450'>instead</span> <span
  m='1021870'>of</span> <span m='1022250'>on</span> <span m='1023030'>the</span>
  <span m='1024030'>linear</span> <span m='1024609'>scale</span> <span
  m='1025069'>that</span> <span m='1025109'>we</span> <span
  m='1025240'>showed</span> <span m='1025560'>before.</span> <span
  m='1026640'>And</span> <span m='1027109'>recall</span> <span
  m='1027710'>incidentally,</span> <span m='1029450'>and</span> <span
  m='1029790'>be</span> <span m='1029980'>aware</span> <span
  m='1030450'>incidentally,</span> <span m='1030950'>of</span> <span
  m='1031030'>the</span> <span m='1031119'>fact</span> <span
  m='1032060'>that</span> <span m='1032510'>we</span> <span
  m='1032740'>can,</span> <span m='1033119'>of</span> <span
  m='1033260'>course,</span> <span m='1033589'>cascade</span> <span
  m='1035339'>several</span> <span m='1035839'>filters</span> <span
  m='1036290'>of</span> <span m='1036380'>this</span> <span
  m='1036630'>type</span> <span m='1037020'>and</span> <span
  m='1037220'>improve</span> <span m='1037560'>the</span> <span
  m='1037650'>characteristics.</span> </p><p><span m='1038940'>So</span> <span
  m='1039569'>I</span> <span m='1039770'>have</span> <span
  m='1040359'>shown</span> <span m='1040940'>at</span> <span
  m='1041109'>the</span> <span m='1041230'>top</span> <span m='1042740'>a</span>
  <span m='1043480'>Bode</span> <span m='1043859'>plot</span> <span
  m='1044319'>of</span> <span m='1045220'>the</span> <span
  m='1047710'>system</span> <span m='1048040'>function</span> <span
  m='1048339'>associated</span> <span m='1048890'>with</span> <span
  m='1048990'>the</span> <span m='1049060'>capacitor</span> <span
  m='1049720'>output.</span> <span m='1050940'>It's</span> <span
  m='1051250'>flat</span> <span m='1052140'>out</span> <span
  m='1052360'>to</span> <span m='1052490'>a</span> <span
  m='1052570'>frequency</span> <span m='1053340'>corresponding</span> <span
  m='1054150'>to</span> <span m='1054280'>1</span> <span m='1054740'>over</span>
  <span m='1055690'>the</span> <span m='1055810'>time</span> <span
  m='1056150'>constant,</span> <span m='1057380'>RC.</span> <span
  m='1058590'>And</span> <span m='1058750'>then</span> <span
  m='1059190'>it</span> <span m='1059540'>falls</span> <span
  m='1059910'>off</span> <span m='1060340'>at</span> <span m='1060760'>10
  dB</span> <span m='1061720'>per</span> <span m='1062040'>decade,</span> <span
  m='1062980'>a</span> <span m='1063070'>decade</span> <span
  m='1063510'>being</span> <span m='1063780'>a</span> <span
  m='1063820'>factor</span> <span m='1064300'>of</span> <span
  m='1064380'>10.</span> </p><p><span m='1065640'>Or</span> <span
  m='1066170'>if</span> <span m='1066430'>instead</span> <span
  m='1066930'>we</span> <span m='1067080'>look</span> <span
  m='1067440'>at</span> <span m='1067910'>the</span> <span
  m='1068030'>system</span> <span m='1068390'>function</span> <span
  m='1068770'>associated</span> <span m='1069390'>with</span> <span
  m='1069530'>the</span> <span m='1069620'>resistor</span> <span
  m='1070420'>output,</span> <span m='1071420'>that</span> <span
  m='1071660'>corresponds</span> <span m='1072670'>to</span> <span
  m='1073140'>a</span> <span m='1073500'>10 dB</span> <span
  m='1074150'>per</span> <span m='1074300'>decade</span> <span
  m='1075610'>increase</span> <span m='1076170'>in</span> <span
  m='1076280'>frequency</span> <span m='1077500'>up</span> <span
  m='1077700'>to</span> <span m='1077810'>approximately</span> <span
  m='1078940'>the</span> <span m='1079020'>reciprocal</span> <span
  m='1079570'>of</span> <span m='1079670'>the</span> <span
  m='1079770'>time</span> <span m='1080080'>constant,</span> <span
  m='1081130'>and</span> <span m='1081700'>then</span> <span
  m='1081880'>approaching</span> <span m='1082510'>a</span> <span
  m='1082580'>flat</span> <span m='1083100'>characteristic</span> <span
  m='1083870'>after</span> <span m='1084190'>that.</span> </p><p><span
  m='1085550'>And</span> <span m='1086170'>if</span> <span m='1086990'>we</span>
  <span m='1087920'>consider</span> <span m='1088440'>either</span> <span
  m='1088730'>one</span> <span m='1088940'>of</span> <span
  m='1089090'>these,</span> <span m='1089920'>looking</span> <span
  m='1090660'>back</span> <span m='1090920'>again</span> <span
  m='1091400'>at</span> <span m='1091740'>the</span> <span
  m='1091960'>lowpass</span> <span m='1092810'>filter,</span> <span
  m='1093790'>if</span> <span m='1094020'>we</span> <span
  m='1094130'>were</span> <span m='1094260'>to</span> <span
  m='1094350'>cascade</span> <span m='1095420'>several</span> <span
  m='1095980'>filters</span> <span m='1097020'>with</span> <span
  m='1097220'>this</span> <span m='1097410'>frequency</span> <span
  m='1097930'>response,</span> <span m='1099100'>then</span> <span
  m='1099980'>because</span> <span m='1100340'>we</span> <span
  m='1100450'>have</span> <span m='1100660'>things</span> <span
  m='1100920'>plotted</span> <span m='1101250'>on</span> <span
  m='1101400'>a</span> <span m='1101440'>Bode</span> <span
  m='1101810'>plot,</span> <span m='1102550'>the</span> <span
  m='1102650'>Bode</span> <span m='1103010'>plot</span> <span
  m='1103380'>for</span> <span m='1103460'>the</span> <span
  m='1103570'>cascade</span> <span m='1104330'>would</span> <span
  m='1104490'>simply</span> <span m='1104890'>be</span> <span
  m='1105090'>summing</span> <span m='1105530'>these.</span> <span
  m='1106010'>And</span> <span m='1106200'>so</span> <span m='1107010'>if</span>
  <span m='1107180'>we</span> <span m='1107300'>cascaded,</span> <span
  m='1107950'>for</span> <span m='1108080'>example,</span> <span
  m='1108580'>two</span> <span m='1108770'>stages</span> <span
  m='1109900'>instead</span> <span m='1110250'>of</span> <span
  m='1110330'>a</span> <span m='1110440'>roll-off</span> <span
  m='1111070'>at</span> <span m='1111270'>10 dB</span> <span
  m='1111780'>per</span> <span m='1111910'>decade,</span> <span
  m='1112530'>it</span> <span m='1112650'>would</span> <span
  m='1113120'>roll</span> <span m='1113400'>off</span> <span
  m='1113750'>at</span> <span m='1114210'>20 dB</span> <span
  m='1114820'>per</span> <span m='1114980'>decade.</span> </p><p><span
  m='1117780'>Now,</span> <span m='1118360'>filters</span> <span
  m='1118810'>in</span> <span m='1118900'>this</span> <span
  m='1119140'>type,</span> <span m='1119550'>RC</span> <span
  m='1120010'>filters,</span> <span m='1121230'>perhaps</span> <span
  m='1121650'>several</span> <span m='1122010'>of</span> <span
  m='1122100'>them</span> <span m='1122260'>in</span> <span
  m='1122360'>cascade,</span> <span m='1123560'>are</span> <span
  m='1124050'>in</span> <span m='1124260'>fact</span> <span
  m='1125150'>very</span> <span m='1125480'>prevalent.</span> <span
  m='1127360'>And</span> <span m='1128520'>in</span> <span
  m='1128660'>fact,</span> <span m='1129500'>in</span> <span
  m='1130300'>an</span> <span m='1130440'>environment</span> <span
  m='1131570'>like</span> <span m='1131840'>this,</span> <span
  m='1132380'>where</span> <span m='1133060'>we're,</span> <span m='1133330'>in
  fact,</span> <span m='1133600'>doing</span> <span
  m='1134410'>recording,</span> <span m='1135970'>we</span> <span
  m='1136130'>see</span> <span m='1137840'>there</span> <span
  m='1138120'>are</span> <span m='1138630'>filters</span> <span
  m='1139210'>of</span> <span m='1139310'>that</span> <span
  m='1139590'>type</span> <span m='1140150'>that</span> <span
  m='1140740'>show</span> <span m='1140870'>up</span> <span
  m='1141020'>very</span> <span m='1141250'>commonly</span> <span
  m='1141810'>both</span> <span m='1142210'>in</span> <span
  m='1142370'>the</span> <span m='1142500'>audio</span> <span
  m='1143150'>and</span> <span m='1143700'>the</span> <span
  m='1143790'>video</span> <span m='1144870'>portion</span> <span
  m='1145480'>of</span> <span m='1145680'>the</span> <span
  m='1145750'>signal</span> <span m='1146090'>processing</span> <span
  m='1146720'>that's</span> <span m='1146900'>associated</span> <span
  m='1148140'>with</span> <span m='1148310'>making</span> <span
  m='1148600'>this</span> <span m='1148700'>set</span> <span
  m='1148940'>of</span> <span m='1149030'>tapes.</span> </p><p><span
  m='1150470'>In</span> <span m='1150670'>fact,</span> <span
  m='1151680'>let's</span> <span m='1152150'>take</span> <span
  m='1152440'>a</span> <span m='1152610'>look</span> <span m='1152960'>in</span>
  <span m='1153210'>the</span> <span m='1153490'>control</span> <span
  m='1153940'>room.</span> <span m='1154350'>And</span> <span
  m='1154740'>what</span> <span m='1154880'>I'll</span> <span
  m='1154980'>be</span> <span m='1155170'>able</span> <span
  m='1155310'>to</span> <span m='1155360'>show</span> <span
  m='1155620'>you</span> <span m='1156090'>in</span> <span
  m='1156200'>the</span> <span m='1156290'>control</span> <span
  m='1156780'>room</span> <span m='1157630'>is</span> <span
  m='1158680'>the</span> <span m='1159070'>audio</span> <span
  m='1159480'>portion</span> <span m='1160250'>of</span> <span
  m='1160910'>the</span> <span m='1161170'>processing</span> <span
  m='1161870'>that's</span> <span m='1162120'>done</span> <span
  m='1162620'>and</span> <span m='1163070'>the</span> <span
  m='1163200'>kinds</span> <span m='1163730'>of</span> <span
  m='1163850'>filters,</span> <span m='1164550'>very</span> <span
  m='1164740'>much</span> <span m='1165000'>of</span> <span
  m='1165080'>the</span> <span m='1165180'>type</span> <span
  m='1165480'>we</span> <span m='1165580'>just</span> <span
  m='1165800'>talked</span> <span m='1166120'>about,</span> <span
  m='1166890'>that</span> <span m='1167000'>are</span> <span
  m='1167080'>associated</span> <span m='1168100'>with</span> <span
  m='1168790'>the</span> <span m='1168880'>signal</span> <span
  m='1169240'>processing</span> <span m='1169890'>that's</span> <span
  m='1170100'>done</span> <span m='1170560'>in</span> <span
  m='1170780'>preparing</span> <span m='1171290'>the</span> <span
  m='1171450'>audio</span> <span m='1172190'>for</span> <span
  m='1172280'>the</span> <span m='1172400'>tapes.</span> <span
  m='1173140'>So</span> <span m='1173580'>let's</span> <span
  m='1174120'>just</span> <span m='1174460'>take</span> <span
  m='1174650'>a</span> <span m='1174710'>walk</span> <span
  m='1174980'>into</span> <span m='1175220'>the</span> <span
  m='1175310'>control</span> <span m='1175760'>room</span> <span
  m='1176120'>and</span> <span m='1176380'>see</span> <span
  m='1176580'>what</span> <span m='1176730'>we</span> <span
  m='1176850'>see.</span> </p><p><span m='1180110'>This</span> <span
  m='1180370'>is</span> <span m='1180660'>the</span> <span
  m='1181370'>control</span> <span m='1181800'>room</span> <span
  m='1182140'>that's</span> <span m='1182280'>used</span> <span
  m='1182770'>for</span> <span m='1183270'>camera</span> <span
  m='1183630'>switching.</span> <span m='1184260'>It's</span> <span
  m='1184700'>used</span> <span m='1184990'>for</span> <span
  m='1185110'>computer</span> <span m='1185580'>editing</span> <span
  m='1185930'>and</span> <span m='1186000'>also</span> <span
  m='1186750'>audio</span> <span m='1187150'>control.</span> <span
  m='1188210'>You</span> <span m='1188350'>can</span> <span
  m='1188470'>see</span> <span m='1189040'>the</span> <span
  m='1189560'>monitors,</span> <span m='1190220'>and</span> <span
  m='1190510'>these</span> <span m='1190790'>are</span> <span
  m='1190820'>used</span> <span m='1191150'>for</span> <span
  m='1191280'>the</span> <span m='1191680'>camera</span> <span
  m='1192040'>switching.</span> <span m='1193090'>And</span> <span
  m='1193880'>this</span> <span m='1194150'>is</span> <span
  m='1194340'>the</span> <span m='1194670'>computer</span> <span
  m='1195080'>editing</span> <span m='1195780'>console</span> <span
  m='1196400'>that's</span> <span m='1196560'>used</span> <span
  m='1196870'>for</span> <span m='1197390'>online</span> <span
  m='1197870'>and</span> <span m='1197970'>offline</span> <span
  m='1198430'>computer</span> <span m='1198870'>editing.</span> </p><p><span
  m='1199890'>What</span> <span m='1200030'>I</span> <span
  m='1200340'>really</span> <span m='1200550'>want</span> <span
  m='1200720'>to</span> <span m='1200780'>demonstrate</span> <span
  m='1201820'>though,</span> <span m='1202330'>in</span> <span
  m='1202440'>the</span> <span m='1202520'>context</span> <span
  m='1203060'>of</span> <span m='1203110'>the</span> <span
  m='1203190'>lecture</span> <span m='1203730'>is</span> <span
  m='1204120'>the</span> <span m='1204390'>audio</span> <span
  m='1204760'>control</span> <span m='1205220'>panel,</span> <span
  m='1206150'>which</span> <span m='1206760'>contains,</span> <span
  m='1207680'>among</span> <span m='1207960'>other</span> <span
  m='1208160'>things,</span> <span m='1208970'>a</span> <span
  m='1209090'>variety</span> <span m='1209640'>of</span> <span
  m='1209720'>filters</span> <span m='1210300'>for</span> <span
  m='1210500'>high</span> <span m='1210680'>frequency,</span> <span
  m='1211270'>low</span> <span m='1211450'>frequencies,</span> <span
  m='1211770'>et</span> <span m='1212090'>cetera,</span> <span
  m='1212480'>basically</span> <span m='1213280'>equalization</span> <span
  m='1213970'>filters.</span> <span m='1215280'>And</span> <span
  m='1216160'>what</span> <span m='1216360'>we</span> <span
  m='1216490'>have</span> <span m='1216850'>in</span> <span
  m='1216940'>the</span> <span m='1217000'>way</span> <span
  m='1217170'>of</span> <span m='1217270'>filtering</span> <span
  m='1217960'>is,</span> <span m='1218980'>first</span> <span
  m='1219260'>of</span> <span m='1219330'>all,</span> <span
  m='1220380'>what's</span> <span m='1220560'>referred</span> <span
  m='1220860'>to</span> <span m='1221060'>as a</span> <span
  m='1221130'>graphic</span> <span m='1221590'>equalizer,</span> <span
  m='1223110'>which</span> <span m='1223390'>consists</span> <span
  m='1223790'>of</span> <span m='1223860'>a</span> <span m='1224130'>set</span>
  <span m='1224320'>of</span> <span m='1224440'>bandpass</span> <span
  m='1225090'>filters,</span> <span m='1225510'>which</span> <span
  m='1225700'>I'll</span> <span m='1225830'>describe</span> <span
  m='1226450'>a</span> <span m='1226500'>little</span> <span
  m='1226640'>more</span> <span m='1226860'>carefully</span> <span
  m='1227260'>in</span> <span m='1227360'>a</span> <span
  m='1227410'>minute.</span> <span m='1228340'>And</span> <span
  m='1228490'>then</span> <span m='1228900'>also,</span> <span
  m='1229790'>an</span> <span m='1229950'>audio</span> <span
  m='1230590'>control</span> <span m='1231050'>panel,</span> <span
  m='1231750'>which</span> <span m='1232250'>is</span> <span
  m='1232520'>down</span> <span m='1232820'>here</span> <span
  m='1233810'>and</span> <span m='1234150'>which</span> <span
  m='1234380'>contains</span> <span m='1234860'>separate</span> <span
  m='1235250'>equalizer</span> <span m='1235820'>circuits</span> <span
  m='1236350'>for</span> <span m='1236530'>each</span> <span
  m='1236890'>of</span> <span m='1237040'>a</span> <span
  m='1237160'>whole</span> <span m='1237500'>set</span> <span
  m='1237800'>of</span> <span m='1237890'>channels</span> <span
  m='1238870'>and</span> <span m='1239010'>also</span> <span
  m='1239480'>lots</span> <span m='1239790'>of</span> <span
  m='1239860'>controls</span> <span m='1240400'>on</span> <span
  m='1240600'>them.</span> </p><p><span m='1241170'>Well,</span> <span
  m='1242040'>let</span> <span m='1242200'>me</span> <span
  m='1242320'>begin</span> <span m='1243080'>in</span> <span
  m='1243230'>the</span> <span m='1243310'>demonstration</span> <span
  m='1244270'>by</span> <span m='1245410'>demonstrating</span> <span
  m='1246690'>a</span> <span m='1246770'>little</span> <span
  m='1247060'>bit</span> <span m='1247400'>of</span> <span
  m='1247690'>what</span> <span m='1247970'>the</span> <span
  m='1248200'>graphic</span> <span m='1248660'>equalizer</span> <span
  m='1249300'>does.</span> <span m='1251380'>Well,</span> <span
  m='1251720'>what</span> <span m='1251920'>we</span> <span
  m='1252060'>have</span> <span m='1252600'>is</span> <span m='1253180'>a</span>
  <span m='1253780'>set</span> <span m='1254240'>of</span> <span
  m='1254490'>bandpass</span> <span m='1255160'>filters.</span> <span
  m='1255780'>And</span> <span m='1256290'>what's</span> <span
  m='1256500'>indicated</span> <span m='1257030'>up</span> <span
  m='1257190'>here</span> <span m='1257620'>are</span> <span
  m='1257690'>the</span> <span m='1257800'>center</span> <span
  m='1258100'>frequencies</span> <span m='1258780'>of</span> <span
  m='1258880'>the</span> <span m='1258970'>filters,</span> <span
  m='1260040'>and</span> <span m='1260170'>then</span> <span
  m='1260340'>a</span> <span m='1260390'>slider</span> <span
  m='1260840'>switch</span> <span m='1261160'>for</span> <span
  m='1261290'>each</span> <span m='1261480'>one</span> <span
  m='1261840'>that</span> <span m='1262110'>lets</span> <span
  m='1262430'>us</span> <span m='1262580'>attenuate</span> <span
  m='1263190'>or</span> <span m='1263310'>amplify.</span> <span
  m='1264570'>And</span> <span m='1264830'>this</span> <span
  m='1264990'>is</span> <span m='1265130'>a</span> <span m='1265190'>dB</span>
  <span m='1265560'>scale.</span> </p><p><span m='1266550'>So</span> <span
  m='1267910'>essentially,</span> <span m='1268860'>if</span> <span
  m='1269170'>you</span> <span m='1269340'>look</span> <span
  m='1269560'>across</span> <span m='1270620'>this</span> <span
  m='1270850'>bank</span> <span m='1271150'>of</span> <span
  m='1271250'>filters</span> <span m='1272460'>with</span> <span
  m='1272960'>the</span> <span m='1273670'>total</span> <span
  m='1273960'>output</span> <span m='1274230'>of</span> <span
  m='1274270'>the</span> <span m='1274380'>equalizer</span> <span
  m='1274980'>just</span> <span m='1275200'>being</span> <span
  m='1275420'>the</span> <span m='1275510'>sum</span> <span
  m='1275800'>of</span> <span m='1275850'>the</span> <span
  m='1275970'>outputs</span> <span m='1276470'>from</span> <span
  m='1276840'>each</span> <span m='1277080'>of</span> <span
  m='1277140'>these</span> <span m='1277380'>filters,</span> <span
  m='1278540'>interestingly</span> <span m='1279550'>the</span> <span
  m='1279800'>position</span> <span m='1280290'>of the</span> <span
  m='1280370'>slider</span> <span m='1280830'>switches</span> <span
  m='1281440'>as</span> <span m='1281560'>you</span> <span
  m='1281680'>move</span> <span m='1281860'>across</span> <span
  m='1282320'>here,</span> <span m='1283060'>in</span> <span
  m='1283190'>effect,</span> <span m='1283620'>shows</span> <span
  m='1284020'>you</span> <span m='1284270'>what</span> <span
  m='1284450'>the</span> <span m='1284530'>frequency</span> <span
  m='1285040'>response</span> <span m='1285590'>of</span> <span
  m='1285680'>the</span> <span m='1285790'>equalizer</span> <span
  m='1286460'>is.</span> <span m='1287090'>So</span> <span
  m='1287360'>you</span> <span m='1287550'>can</span> <span
  m='1287670'>change</span> <span m='1288080'>the</span> <span
  m='1288330'>overall</span> <span m='1289180'>shaping</span> <span
  m='1289950'>of</span> <span m='1290690'>the</span> <span
  m='1290790'>filter</span> <span m='1291280'>by</span> <span
  m='1291460'>moving</span> <span m='1291830'>the</span> <span
  m='1291910'>switches</span> <span m='1292360'>up</span> <span
  m='1292520'>and</span> <span m='1292650'>down.</span> </p><p><span
  m='1293870'>Right</span> <span m='1294090'>now</span> <span
  m='1294390'>the</span> <span m='1294550'>equalizer</span> <span
  m='1295360'>is</span> <span m='1295510'>out.</span> <span
  m='1295780'>Let's</span> <span m='1296260'>put</span> <span
  m='1296450'>the</span> <span m='1296550'>equalizer</span> <span
  m='1297440'>into</span> <span m='1297750'>the</span> <span
  m='1298040'>circuit.</span> <span m='1298480'>And</span> <span
  m='1298580'>now</span> <span m='1298780'>I</span> <span m='1299640'>put</span>
  <span m='1299850'>in</span> <span m='1299970'>this</span> <span
  m='1300170'>filtering</span> <span m='1300600'>characteristic.</span> <span
  m='1302000'>And</span> <span m='1302260'>what</span> <span
  m='1302400'>I'd</span> <span m='1302500'>like</span> <span
  m='1302690'>to</span> <span m='1302790'>demonstrate</span> <span
  m='1303610'>is</span> <span m='1304850'>filtering</span> <span
  m='1305640'>with</span> <span m='1305910'>this,</span> <span
  m='1306300'>when</span> <span m='1306510'>we</span> <span
  m='1306650'>do</span> <span m='1306890'>things</span> <span
  m='1307300'>that</span> <span m='1307470'>are</span> <span
  m='1308110'>a</span> <span m='1308210'>little</span> <span
  m='1308420'>more</span> <span m='1308660'>dramatic</span> <span
  m='1309240'>than</span> <span m='1309470'>what</span> <span
  m='1309660'>would</span> <span m='1309810'>normally</span> <span
  m='1310200'>be</span> <span m='1310350'>done</span> <span
  m='1310630'>in</span> <span m='1310730'>a</span> <span
  m='1310830'>typical</span> <span m='1311260'>audio</span> <span
  m='1311560'>recording</span> <span m='1312080'>setting.</span> <span
  m='1313250'>And</span> <span m='1313630'>to</span> <span m='1313730'>do</span>
  <span m='1313900'>this,</span> <span m='1314690'>let's</span> <span
  m='1315730'>add</span> <span m='1316000'>to</span> <span m='1316100'>my</span>
  <span m='1316250'>voice</span> <span m='1316650'>some</span> <span
  m='1316730'>music</span> <span m='1317210'>to</span> <span
  m='1317700'>make</span> <span m='1317950'>it</span> <span
  m='1318130'>more</span> <span m='1318340'>interesting.</span> <span
  m='1320120'>Not</span> <span m='1320410'>that</span> <span
  m='1320500'>my</span> <span m='1320600'>voice</span> <span
  m='1320910'>isn't</span> <span m='1321130'>interesting</span> <span
  m='1321620'>as</span> <span m='1321980'>it is.</span> <span
  m='1322340'>But</span> <span m='1323030'>in</span> <span
  m='1323150'>any</span> <span m='1323340'>case,</span> <span
  m='1323620'>let's</span> <span m='1323850'>bring</span> <span
  m='1324060'>some</span> <span m='1324240'>music</span> <span
  m='1324640'>up.</span> </p><p><span m='1324980'>[MUSIC PLAYING]</span>
  </p><p><span m='1325660'>And</span> <span m='1326710'>now</span> <span
  m='1326930'>what</span> <span m='1327050'>I'll</span> <span
  m='1327230'>do</span> <span m='1327840'>is</span> <span m='1329440'>set</span>
  <span m='1330100'>the</span> <span m='1330350'>low</span> <span
  m='1330590'>frequencies</span> <span m='1331340'>flat.</span> <span
  m='1332900'>And</span> <span m='1333310'>let</span> <span
  m='1333500'>me</span> <span m='1333660'>take</span> <span
  m='1334000'>out</span> <span m='1334220'>the</span> <span
  m='1334310'>high</span> <span m='1334530'>frequencies</span> <span
  m='1336020'>above</span> <span m='1336430'>800</span> <span
  m='1336920'>cycles.</span> <span m='1338430'>And</span> <span
  m='1338990'>so</span> <span m='1339180'>now</span> <span m='1339580'>what
  we</span> <span m='1339730'>have,</span> <span m='1340220'>effectively,</span>
  <span m='1341160'>is</span> <span m='1341410'>a</span> <span
  m='1341480'>lowpass</span> <span m='1342090'>filter.</span> <span
  m='1343940'>And</span> <span m='1344630'>now</span> <span
  m='1345000'>with</span> <span m='1345370'>the</span> <span
  m='1345480'>lowpass</span> <span m='1345990'>filter,</span> <span
  m='1346760'>let</span> <span m='1346990'>me</span> <span
  m='1347130'>now</span> <span m='1347740'>bring</span> <span
  m='1348000'>the</span> <span m='1348470'>highs</span> <span
  m='1349410'>back</span> <span m='1349730'>up.</span> <span
  m='1351180'>And</span> <span m='1351460'>so</span> <span
  m='1351620'>I'm</span> <span m='1351770'>bringing</span> <span
  m='1352120'>up</span> <span m='1352270'>those</span> <span
  m='1352980'>bandpass</span> <span m='1353640'>filters.</span> </p><p><span
  m='1355310'>And</span> <span m='1355490'>now</span> <span
  m='1356150'>let</span> <span m='1356430'>me</span> <span
  m='1357230'>cut</span> <span m='1357480'>out</span> <span
  m='1358050'>the</span> <span m='1358160'>lows.</span> <span
  m='1359490'>And</span> <span m='1359940'>you'll</span> <span
  m='1360100'>hear</span> <span m='1360280'>the</span> <span
  m='1360390'>lows</span> <span m='1360690'>disappearing</span> <span
  m='1361550'>and,</span> <span m='1362300'>in</span> <span
  m='1362430'>effect,</span> <span m='1363230'>keeping</span> <span
  m='1363570'>the</span> <span m='1363670'>highs</span> <span
  m='1364190'>in</span> <span m='1365190'>effectively</span> <span
  m='1365990'>crispens</span> <span m='1366880'>the</span> <span
  m='1367200'>sound,</span> <span m='1367750'>either</span> <span
  m='1367850'>my</span> <span m='1367990'>voice</span> <span
  m='1368300'>or</span> <span m='1368610'>the</span> <span
  m='1368840'>music.</span> <span m='1370050'>And</span> <span
  m='1371380'>finally,</span> <span m='1371760'>let</span> <span
  m='1371910'>me</span> <span m='1372010'>go</span> <span
  m='1372170'>back</span> <span m='1372600'>to</span> <span m='1373000'>0
  dB</span> <span m='1373610'>equalization</span> <span m='1374790'>on</span>
  <span m='1375020'>each</span> <span m='1375200'>of</span> <span
  m='1375250'>the</span> <span m='1375320'>filters.</span> <span
  m='1376770'>And</span> <span m='1377690'>what</span> <span m='1378090'>I'll
  also</span> <span m='1378640'>do</span> <span m='1379170'>now</span> <span
  m='1379700'>is</span> <span m='1380350'>take</span> <span
  m='1380560'>the</span> <span m='1380680'>equalizer</span> <span
  m='1381390'>out</span> <span m='1381500'>of</span> <span
  m='1381590'>the</span> <span m='1381660'>circuit</span> <span
  m='1382090'>totally.</span> </p><p><span m='1385860'>Now,</span> <span
  m='1386150'>let's</span> <span m='1386860'>take</span> <span
  m='1387040'>a</span> <span m='1387090'>look</span> <span m='1387340'>at</span>
  <span m='1387550'>the</span> <span m='1387910'>audio</span> <span
  m='1388640'>master</span> <span m='1389050'>control</span> <span
  m='1389490'>panel.</span> <span m='1390490'>And</span> <span
  m='1391370'>this</span> <span m='1391610'>panel</span> <span
  m='1392200'>has,</span> <span m='1392760'>of</span> <span
  m='1392890'>course,</span> <span m='1393500'>for</span> <span
  m='1393690'>each</span> <span m='1393920'>channel</span> <span
  m='1394410'>and,</span> <span m='1394820'>for</span> <span
  m='1395000'>example,</span> <span m='1395450'>the channel</span> <span
  m='1395790'>that</span> <span m='1395870'>we're</span> <span
  m='1396050'>working</span> <span m='1396460'>on,</span> <span m='1397510'>of
  a</span> <span m='1397570'>volume</span> <span m='1398010'>control.</span>
  <span m='1398580'>I</span> <span m='1398640'>can</span> <span
  m='1398950'>turn</span> <span m='1399170'>the</span> <span
  m='1399230'>volume</span> <span m='1399650'>down,</span> <span
  m='1400790'>and</span> <span m='1401230'>I</span> <span m='1401290'>can</span>
  <span m='1401450'>turn</span> <span m='1401680'>the</span> <span
  m='1401750'>volume</span> <span m='1402180'>up.</span> <span m='1403990'>And
  it</span> <span m='1404400'>also</span> <span m='1404870'>has,</span> <span
  m='1406820'>for</span> <span m='1406930'>this</span> <span
  m='1407240'>particular</span> <span m='1407690'>equalizer</span> <span
  m='1408260'>circuit,</span> <span m='1409100'>it</span> <span
  m='1409220'>has</span> <span m='1409460'>a</span> <span m='1409520'>set</span>
  <span m='1409940'>of</span> <span m='1410740'>three</span> <span
  m='1411190'>bandpass</span> <span m='1412000'>filters</span> <span
  m='1413090'>and</span> <span m='1414020'>knobs</span> <span
  m='1414630'>which</span> <span m='1414910'>let</span> <span
  m='1415150'>us</span> <span m='1415930'>either</span> <span
  m='1416410'>put</span> <span m='1416670'>in</span> <span m='1416950'>up</span>
  <span m='1417210'>to</span> <span m='1417400'>12 dB</span> <span
  m='1418830'>gain</span> <span m='1419410'>or</span> <span m='1419710'>12
  dB</span> <span m='1420280'>attenuation</span> <span m='1421110'>in</span>
  <span m='1421280'>each</span> <span m='1421480'>of</span> <span
  m='1421530'>the</span> <span m='1421600'>bands,</span> <span
  m='1422480'>and</span> <span m='1422640'>also</span> <span
  m='1423390'>a</span> <span m='1423580'>selector</span> <span
  m='1424030'>switch</span> <span m='1424390'>that</span> <span
  m='1424490'>lets</span> <span m='1424780'>us</span> <span
  m='1424990'>select</span> <span m='1425340'>the</span> <span
  m='1425530'>center</span> <span m='1425880'>the</span> <span
  m='1425980'>band.</span> </p><p><span m='1426780'>So</span> <span
  m='1427100'>let</span> <span m='1427260'>me</span> <span
  m='1427720'>just</span> <span m='1428770'>again</span> <span
  m='1429090'>demonstrate</span> <span m='1429580'>a</span> <span
  m='1429630'>little</span> <span m='1429880'>bit</span> <span
  m='1430150'>with</span> <span m='1430450'>this.</span> <span
  m='1430810'>And</span> <span m='1431330'>let's</span> <span
  m='1431540'>get</span> <span m='1431650'>a</span> <span
  m='1431710'>close</span> <span m='1432050'>up</span> <span
  m='1432270'>of</span> <span m='1432420'>this</span> <span
  m='1432620'>panel.</span> <span m='1434100'>So</span> <span
  m='1434530'>what</span> <span m='1434700'>we</span> <span
  m='1434820'>have,</span> <span m='1435150'>as</span> <span
  m='1435290'>I</span> <span m='1435390'>indicated,</span> <span
  m='1436420'>is</span> <span m='1437450'>three</span> <span
  m='1437930'>bandpass</span> <span m='1438660'>filters.</span> <span
  m='1439310'>And</span> <span m='1439720'>these</span> <span
  m='1439950'>knobs</span> <span m='1440540'>that</span> <span
  m='1440670'>I'm</span> <span m='1440780'>pointing</span> <span
  m='1441150'>to</span> <span m='1441330'>here</span> <span
  m='1441860'>are</span> <span m='1442790'>controls</span> <span
  m='1443460'>that</span> <span m='1443960'>allow us</span> <span
  m='1444450'>for</span> <span m='1444570'>each</span> <span
  m='1444730'>of</span> <span m='1444780'>the</span> <span
  m='1444850'>filters</span> <span m='1445400'>to</span> <span
  m='1445520'>put</span> <span m='1445730'>in</span> <span m='1446070'>up</span>
  <span m='1446250'>to</span> <span m='1446380'>12 dB</span> <span
  m='1447200'>gain</span> <span m='1447770'>or</span> <span m='1448140'>12
  dB</span> <span m='1448750'>attenuation.</span> </p><p><span
  m='1450310'>There</span> <span m='1450700'>are</span> <span
  m='1450890'>also</span> <span m='1451200'>with</span> <span
  m='1451370'>each</span> <span m='1451540'>of</span> <span
  m='1451580'>the</span> <span m='1451660'>filters</span> <span
  m='1452480'>a</span> <span m='1452690'>selector</span> <span
  m='1453240'>switch</span> <span m='1454510'>that</span> <span
  m='1454980'>lets</span> <span m='1455370'>us</span> <span
  m='1455790'>adjust</span> <span m='1456420'>the</span> <span
  m='1456630'>center</span> <span m='1456940'>frequency</span> <span
  m='1457220'>of</span> <span m='1457500'>the</span> <span
  m='1457590'>filter.</span> <span m='1458000'>Basically</span> <span
  m='1458560'>it's</span> <span m='1458790'>a</span> <span
  m='1459210'>two-position</span> <span m='1459840'>switch.</span> <span
  m='1461660'>There</span> <span m='1462000'>also,</span> <span
  m='1462630'>as</span> <span m='1463000'>you</span> <span
  m='1463140'>can</span> <span m='1463280'>see,</span> <span
  m='1463790'>is</span> <span m='1464380'>a</span> <span
  m='1464550'>button</span> <span m='1465060'>that</span> <span
  m='1466080'>let's</span> <span m='1466390'>us</span> <span
  m='1466940'>either</span> <span m='1467200'>put</span> <span
  m='1467390'>the</span> <span m='1467490'>equalization</span> <span
  m='1468140'>in</span> <span m='1468280'>or</span> <span
  m='1468430'>out.</span> </p><p><span m='1468830'>Currently</span> <span
  m='1469210'>the</span> <span m='1469590'>equalization</span> <span
  m='1470440'>is</span> <span m='1470610'>out.</span> <span
  m='1471290'>Let's</span> <span m='1471470'>put</span> <span
  m='1471640'>the</span> <span m='1471730'>equalization</span> <span
  m='1472410'>in.</span> <span m='1472820'>We</span> <span
  m='1472960'>won't</span> <span m='1473320'>hear</span> <span
  m='1473790'>any</span> <span m='1474020'>effect</span> <span
  m='1474430'>from</span> <span m='1474620'>that,</span> <span
  m='1474910'>because</span> <span m='1475430'>the</span> <span
  m='1475510'>gain</span> <span m='1475770'>controls</span> <span
  m='1476250'>are</span> <span m='1476340'>all</span> <span
  m='1476480'>set</span> <span m='1476760'>at</span> <span m='1476880'>0
  dB.</span> <span m='1478420'>And</span> <span m='1478710'>I'll</span> <span
  m='1478770'>want</span> <span m='1479040'>to</span> <span
  m='1479860'>illustrate</span> <span m='1480360'>shortly</span> <span
  m='1480880'>the</span> <span m='1481070'>effect</span> <span
  m='1481470'>of</span> <span m='1481550'>these.</span> <span
  m='1481820'>But</span> <span m='1482130'>before</span> <span
  m='1482490'>I</span> <span m='1482590'>do,</span> <span m='1482900'>let</span>
  <span m='1483050'>me</span> <span m='1483160'>draw</span> <span
  m='1483350'>your</span> <span m='1483530'>attention</span> <span
  m='1484700'>to</span> <span m='1485160'>one</span> <span
  m='1485390'>other</span> <span m='1485630'>filter,</span> <span
  m='1486980'>which</span> <span m='1487490'>is</span> <span
  m='1488050'>this</span> <span m='1488310'>white</span> <span
  m='1488620'>switch.</span> <span m='1489660'>And</span> <span
  m='1490900'>this</span> <span m='1491240'>switch</span> <span
  m='1491680'>is</span> <span m='1492150'>a</span> <span
  m='1492320'>highpass</span> <span m='1492970'>filter</span> <span
  m='1494060'>that</span> <span m='1494200'>essentially</span> <span
  m='1495510'>cuts</span> <span m='1495870'>out</span> <span
  m='1496140'>frequencies</span> <span m='1496880'>below</span> <span
  m='1497560'>about</span> <span m='1497910'>100</span> <span
  m='1498250'>cycles.</span> </p><p><span m='1498740'>So</span> <span
  m='1498930'>what</span> <span m='1499090'>it</span> <span
  m='1499190'>means</span> <span m='1499590'>is</span> <span
  m='1499790'>that</span> <span m='1500440'>if I</span> <span
  m='1500540'>put</span> <span m='1500800'>this</span> <span
  m='1501000'>switch</span> <span m='1501370'>in,</span> <span
  m='1502070'>everything</span> <span m='1502510'>is</span> <span
  m='1502640'>more</span> <span m='1502840'>or</span> <span
  m='1502860'>less</span> <span m='1503150'>flat</span> <span
  m='1503410'>above</span> <span m='1503670'>100</span> <span
  m='1504020'>cycles.</span> <span m='1505080'>And</span> <span
  m='1505650'>what</span> <span m='1505850'>that's</span> <span
  m='1506100'>used</span> <span m='1506420'>for,</span> <span
  m='1507730'>basically,</span> <span m='1508380'>is</span> <span
  m='1508540'>to</span> <span m='1508680'>eliminate</span> <span
  m='1509960'>perhaps</span> <span m='1510450'>60</span> <span
  m='1510820'>cycle</span> <span m='1511430'>noise,</span> <span
  m='1511860'>if</span> <span m='1511960'>that's</span> <span
  m='1512230'>present,</span> <span m='1512870'>or</span> <span
  m='1513290'>some</span> <span m='1513800'>low</span> <span
  m='1513990'>frequency</span> <span m='1514680'>hum</span> <span
  m='1515190'>or</span> <span m='1515350'>whatever.</span> <span
  m='1516100'>Well,</span> <span m='1516350'>we</span> <span
  m='1516450'>won't</span> <span m='1517230'>really</span> <span
  m='1517910'>demonstrate</span> <span m='1518370'>anything</span> <span
  m='1518770'>with</span> <span m='1518940'>that.</span> </p><p><span
  m='1519780'>Let's</span> <span m='1520045'>[? go ?]</span> <span
  m='1520310'>now</span> <span m='1520590'>with the</span> <span
  m='1520790'>equalization</span> <span m='1521610'>in,</span> <span
  m='1522890'>demonstrate</span> <span m='1524130'>the</span> <span
  m='1524260'>effect</span> <span m='1524870'>of</span> <span
  m='1525900'>boosting</span> <span m='1526430'>or</span> <span
  m='1526570'>attenuating</span> <span m='1527500'>the</span> <span
  m='1527740'>low and</span> <span m='1528060'>high</span> <span
  m='1528250'>frequencies.</span> <span m='1529250'>And</span> <span
  m='1529390'>again,</span> <span m='1530000'>I</span> <span
  m='1530310'>think</span> <span m='1530910'>to</span> <span
  m='1531170'>demonstrate</span> <span m='1531840'>this,</span> <span
  m='1532680'>it</span> <span m='1533030'>illustrates</span> <span
  m='1533540'>the</span> <span m='1533620'>point</span> <span
  m='1533880'>the</span> <span m='1533970'>best</span> <span
  m='1535510'>if</span> <span m='1535650'>we</span> <span
  m='1535760'>have</span> <span m='1535980'>a</span> <span
  m='1536020'>little</span> <span m='1536210'>background</span> <span
  m='1536720'>music.</span> <span m='1537110'>So</span> <span
  m='1537370'>maestro,</span> <span m='1537960'>if</span> <span
  m='1538070'>you</span> <span m='1538250'>can</span> <span
  m='1538820'>bring</span> <span m='1539000'>that</span> <span
  m='1539250'>up.</span> </p><p><span m='1539750'>[MUSIC PLAYING]</span>
  </p><p><span m='1541050'>And</span> <span m='1541640'>so</span> <span
  m='1541860'>now</span> <span m='1542050'>what</span> <span
  m='1542150'>I'm</span> <span m='1542250'>going</span> <span
  m='1542340'>to</span> <span m='1542430'>do</span> <span m='1542920'>is</span>
  <span m='1543710'>first</span> <span m='1544440'>boost</span> <span
  m='1544870'>the</span> <span m='1545100'>low</span> <span
  m='1545330'>frequencies.</span> <span m='1546760'>And</span> <span
  m='1546990'>that's</span> <span m='1547240'>what</span> <span
  m='1547400'>this</span> <span m='1547810'>potentiometer</span> <span
  m='1548620'>knob</span> <span m='1548860'>will</span> <span
  m='1549300'>do.</span> <span m='1550040'>So</span> <span
  m='1550220'>now,</span> <span m='1551180'>increasing</span> <span
  m='1552270'>the</span> <span m='1552650'>low</span> <span
  m='1552900'>frequency</span> <span m='1553450'>gain</span> <span
  m='1554290'>and,</span> <span m='1554670'>in fact,</span> <span
  m='1554980'>all</span> <span m='1555240'>the</span> <span
  m='1555300'>way</span> <span m='1555510'>up</span> <span m='1555720'>to</span>
  <span m='1555980'>12 dB</span> <span m='1556860'>when</span> <span
  m='1557010'>I</span> <span m='1557380'>have</span> <span
  m='1557550'>the</span> <span m='1557640'>knob</span> <span
  m='1557895'>over</span> <span m='1558150'>as</span> <span m='1558370'>far
  as</span> <span m='1558720'>I've</span> <span m='1558930'>gone</span> <span
  m='1559240'>here.</span> <span m='1560200'>And</span> <span
  m='1560740'>so</span> <span m='1560970'>that</span> <span
  m='1561250'>has</span> <span m='1561480'>a</span> <span
  m='1561520'>very</span> <span m='1561720'>bassy</span> <span
  m='1562330'>sound.</span> <span m='1562610'>And</span> <span m='1562870'>in
  fact,</span> <span m='1563160'>we</span> <span m='1563480'>can</span> <span
  m='1564030'>make it</span> <span m='1564460'>even</span> <span
  m='1564720'>bassier</span> <span m='1565290'>by</span> <span
  m='1565480'>taking</span> <span m='1565920'>the</span> <span
  m='1566370'>high</span> <span m='1566740'>frequencies</span> <span
  m='1568170'>and</span> <span m='1568930'>attenuating</span> <span
  m='1569450'>those</span> <span m='1570140'>by</span> <span m='1570760'>12
  dB.</span> </p><p><span m='1575930'>OK</span> <span m='1576330'>well,</span>
  <span m='1577020'>let's</span> <span m='1577460'>put</span> <span
  m='1577870'>some</span> <span m='1578040'>of</span> <span
  m='1578080'>the</span> <span m='1578160'>high</span> <span
  m='1578330'>frequencies</span> <span m='1579830'>back</span> <span
  m='1580296'>in.</span> <span m='1581230'>And</span> <span
  m='1581810'>now</span> <span m='1582500'>let's</span> <span
  m='1583040'>turn</span> <span m='1583350'>the</span> <span
  m='1583430'>low-frequency</span> <span m='1584600'>gain</span> <span
  m='1585970'>first</span> <span m='1586300'>back</span> <span
  m='1586790'>down</span> <span m='1587490'>to</span> <span
  m='1587590'>0.</span> <span m='1590080'>And</span> <span
  m='1590240'>now</span> <span m='1590460'>we're</span> <span
  m='1590560'>back</span> <span m='1590830'>to</span> <span
  m='1591040'>flat</span> <span m='1591420'>equalization.</span> <span
  m='1592560'>And</span> <span m='1592670'>now</span> <span m='1592910'>I</span>
  <span m='1593010'>can</span> <span m='1593210'>turn</span> <span
  m='1593420'>the</span> <span m='1593490'>low</span> <span
  m='1593660'>frequency</span> <span m='1594190'>gain</span> <span
  m='1595320'>down</span> <span m='1596010'>so</span> <span
  m='1596340'>that</span> <span m='1597030'>I</span> <span
  m='1597180'>attenuate</span> <span m='1597810'>the</span> <span
  m='1597890'>low</span> <span m='1598020'>frequencies</span> <span
  m='1598780'>by</span> <span m='1598910'>much</span> <span
  m='1599170'>as</span> <span m='1599390'>12 dB.</span> <span
  m='1601090'>And</span> <span m='1601490'>that's</span> <span
  m='1601720'>where</span> <span m='1601910'>we</span> <span
  m='1602060'>are</span> <span m='1602240'>now.</span> <span
  m='1602540'>And</span> <span m='1602650'>so</span> <span
  m='1602760'>this</span> <span m='1602980'>has,</span> <span m='1603580'>of
  course,</span> <span m='1603870'>a</span> <span m='1604010'>much</span> <span
  m='1604370'>crisper</span> <span m='1604836'>sound.</span> </p><p><span
  m='1607170'>And</span> <span m='1608030'>to</span> <span
  m='1608450'>enhance</span> <span m='1608940'>the</span> <span
  m='1609020'>highs</span> <span m='1609410'>even</span> <span
  m='1609650'>more,</span> <span m='1610200'>I</span> <span
  m='1610350'>can,</span> <span m='1611020'>in</span> <span m='1611502'>addition
  to</span> <span m='1611984'>cutting out</span> <span m='1612466'>the</span>
  <span m='1612950'>lows,</span> <span m='1613600'>boost</span> <span
  m='1614250'>the</span> <span m='1614340'>highs</span> <span
  m='1614980'>by</span> <span m='1615520'>putting</span> <span
  m='1615790'>in,</span> <span m='1615890'>again,</span> <span
  m='1616220'>as</span> <span m='1616360'>much</span> <span
  m='1616590'>as</span> <span m='1616810'>12 dB.</span> <span
  m='1620410'>OK</span> <span m='1620740'>well,</span> <span
  m='1621290'>let's</span> <span m='1622620'>turn</span> <span
  m='1623010'>down</span> <span m='1623260'>the</span> <span
  m='1623320'>music</span> <span m='1623790'>now</span> <span
  m='1624380'>and</span> <span m='1625340'>go</span> <span
  m='1625480'>back</span> <span m='1625820'>to</span> <span
  m='1626760'>no</span> <span m='1627050'>equalization</span> <span
  m='1627880'>by</span> <span m='1628140'>setting</span> <span
  m='1628540'>these</span> <span m='1628800'>knobs</span> <span
  m='1629240'>to</span> <span m='1629410'>0 dB.</span> <span
  m='1630210'>And</span> <span m='1630300'>in</span> <span
  m='1630390'>fact,</span> <span m='1630790'>we</span> <span
  m='1630900'>can</span> <span m='1631040'>take</span> <span
  m='1631310'>the</span> <span m='1631440'>equalizer</span> <span
  m='1631960'>out.</span> <span m='1633200'>Well,</span> <span
  m='1633505'>that's</span> <span m='1634320'>a</span> <span
  m='1635060'>quick</span> <span m='1635300'>look</span> <span
  m='1635540'>at</span> <span m='1635720'>some</span> <span
  m='1635910'>real-world</span> <span m='1636420'>filters.</span> <span
  m='1637580'>Now</span> <span m='1637910'>let's</span> <span
  m='1638890'>stop</span> <span m='1639240'>having</span> <span
  m='1639500'>so</span> <span m='1639680'>much</span> <span
  m='1639930'>fun,</span> <span m='1640200'>and</span> <span
  m='1640910'>let's</span> <span m='1641160'>go</span> <span
  m='1641280'>back</span> <span m='1641570'>to</span> <span
  m='1641670'>the</span> <span m='1641750'>lecture.</span> </p><p><span
  m='1649150'>OK</span> <span m='1649480'>well,</span> <span
  m='1650000'>that's</span> <span m='1650970'>a</span> <span
  m='1651020'>little</span> <span m='1651340'>behind-the-scenes</span> <span
  m='1652190'>look.</span> <span m='1653010'>What</span> <span
  m='1653120'>I'd</span> <span m='1653630'>like</span> <span
  m='1653890'>to</span> <span m='1653990'>do</span> <span m='1654160'>now</span>
  <span m='1654690'>is</span> <span m='1655410'>turn</span> <span
  m='1655780'>our</span> <span m='1655980'>attention</span> <span
  m='1656590'>to</span> <span m='1657070'>discrete-time</span> <span
  m='1657810'>filters.</span> <span m='1659130'>And</span> <span
  m='1660070'>as</span> <span m='1660540'>I've</span> <span
  m='1660700'>meant</span> <span m='1661030'>in</span> <span
  m='1661200'>previous</span> <span m='1661690'>lectures,</span> <span
  m='1662400'>there</span> <span m='1662920'>are</span> <span
  m='1664450'>basically</span> <span m='1665720'>two</span> <span
  m='1665990'>classes</span> <span m='1667300'>of</span> <span
  m='1667780'>discrete-time</span> <span m='1668910'>filters</span> <span
  m='1669630'>or</span> <span m='1669940'>discrete-time</span> <span
  m='1670810'>difference</span> <span m='1671200'>equations.</span> </p><p><span
  m='1673280'>One</span> <span m='1673550'>class</span> <span
  m='1674090'>is</span> <span m='1674340'>referred</span> <span
  m='1674780'>to</span> <span m='1675690'>a</span> <span
  m='1676250'>non-recursive</span> <span m='1677370'>or</span> <span
  m='1678030'>moving</span> <span m='1678390'>average</span> <span
  m='1679150'>filter.</span> <span m='1680930'>And</span> <span
  m='1681940'>the</span> <span m='1682190'>basic</span> <span
  m='1682650'>idea</span> <span m='1683280'>with</span> <span
  m='1683450'>a</span> <span m='1683560'>moving</span> <span
  m='1683880'>average</span> <span m='1684260'>filter</span> <span
  m='1684670'>is</span> <span m='1684740'>something</span> <span
  m='1685120'>that</span> <span m='1685380'>perhaps</span> <span
  m='1685850'>you're</span> <span m='1686440'>somewhat</span> <span
  m='1687200'>familiar</span> <span m='1687650'>with</span> <span
  m='1687840'>intuitively.</span> </p><p><span m='1689490'>Think</span> <span
  m='1689750'>of</span> <span m='1689840'>the</span> <span
  m='1689950'>notion</span> <span m='1691070'>of</span> <span
  m='1691340'>taking</span> <span m='1691750'>a</span> <span
  m='1691810'>data</span> <span m='1692180'>sequence,</span> <span
  m='1693560'>and</span> <span m='1694190'>let's</span> <span
  m='1694520'>suppose</span> <span m='1695030'>that</span> <span
  m='1695130'>what</span> <span m='1695310'>we</span> <span
  m='1695420'>wanted</span> <span m='1695730'>to</span> <span
  m='1695860'>do</span> <span m='1696120'>was</span> <span
  m='1696340'>apply</span> <span m='1696960'>some</span> <span
  m='1697160'>smoothing</span> <span m='1697690'>to</span> <span
  m='1697810'>the</span> <span m='1697920'>data</span> <span
  m='1698210'>sequence.</span> <span m='1699290'>We</span> <span
  m='1699420'>could,</span> <span m='1699640'>for</span> <span
  m='1699780'>example,</span> <span m='1700680'>think</span> <span
  m='1701070'>of</span> <span m='1701210'>taking</span> <span
  m='1701600'>adjacent</span> <span m='1702160'>points,</span> <span
  m='1703220'>averaging</span> <span m='1703760'>them</span> <span
  m='1703890'>together,</span> <span m='1704850'>and</span> <span
  m='1705000'>then</span> <span m='1705370'>moving</span> <span
  m='1705830'>that</span> <span m='1706050'>average</span> <span
  m='1706830'>along</span> <span m='1707600'>the</span> <span
  m='1707700'>data</span> <span m='1708020'>sequence.</span> <span
  m='1708960'>And what</span> <span m='1709170'>you</span> <span
  m='1709280'>can</span> <span m='1709430'>kind</span> <span
  m='1709630'>of</span> <span m='1709700'>see</span> <span
  m='1709910'>intuitively</span> <span m='1710760'>is</span> <span
  m='1710960'>that</span> <span m='1711500'>that</span> <span
  m='1711710'>would</span> <span m='1712000'>apply</span> <span
  m='1712760'>some</span> <span m='1712950'>smoothing.</span> </p><p><span
  m='1714020'>So</span> <span m='1714450'>in</span> <span
  m='1714570'>fact,</span> <span m='1715120'>the</span> <span
  m='1715220'>difference</span> <span m='1715580'>equation,</span> <span
  m='1716080'>let's</span> <span m='1716300'>say,</span> <span
  m='1716490'>for</span> <span m='1716720'>three-point</span> <span
  m='1717330'>moving</span> <span m='1717680'>average</span> <span
  m='1718690'>would</span> <span m='1718900'>be</span> <span
  m='1719290'>the</span> <span m='1719390'>difference</span> <span
  m='1719730'>equation</span> <span m='1720280'>that</span> <span
  m='1720390'>I</span> <span m='1720490'>indicate</span> <span
  m='1721020'>here,</span> <span m='1722310'>just</span> <span
  m='1722550'>simply</span> <span m='1723490'>taking</span> <span
  m='1723860'>a</span> <span m='1723930'>data</span> <span
  m='1724240'>point</span> <span m='1725260'>and</span> <span
  m='1725960'>the</span> <span m='1726070'>two</span> <span
  m='1726310'>data</span> <span m='1726600'>points</span> <span
  m='1726910'>adjacent</span> <span m='1727450'>to</span> <span
  m='1727680'>it</span> <span m='1728190'>and</span> <span
  m='1728490'>forming</span> <span m='1729180'>an</span> <span
  m='1729340'>average</span> <span m='1730180'>of</span> <span
  m='1730330'>those</span> <span m='1730680'>three.</span> <span
  m='1731540'>So</span> <span m='1732020'>if</span> <span m='1732190'>we</span>
  <span m='1732300'>thought</span> <span m='1732590'>of</span> <span
  m='1732710'>the</span> <span m='1733270'>processing</span> <span
  m='1733910'>involved,</span> <span m='1735060'>if we're</span> <span
  m='1735260'>forming</span> <span m='1736100'>an</span> <span
  m='1736240'>output</span> <span m='1737120'>sequence</span> <span
  m='1737720'>value,</span> <span m='1738910'>we</span> <span
  m='1739110'>would</span> <span m='1739720'>take</span> <span
  m='1740260'>three</span> <span m='1740530'>adjacent</span> <span
  m='1741050'>points</span> <span m='1741410'>and</span> <span
  m='1741500'>average</span> <span m='1741940'>them.</span> <span
  m='1742240'>That</span> <span m='1742440'>would</span> <span
  m='1742600'>give</span> <span m='1742790'>us</span> <span
  m='1743220'>the</span> <span m='1743380'>output</span> <span
  m='1743940'>add</span> <span m='1744570'>the</span> <span
  m='1744770'>associated</span> <span m='1745500'>time.</span> </p><p><span
  m='1746440'>And</span> <span m='1746580'>then</span> <span
  m='1746740'>to</span> <span m='1746870'>compute</span> <span
  m='1747680'>the</span> <span m='1747790'>next</span> <span
  m='1748150'>output</span> <span m='1748610'>point,</span> <span
  m='1749120'>we</span> <span m='1749290'>would</span> <span
  m='1749460'>just</span> <span m='1749630'>simply</span> <span
  m='1749970'>slide</span> <span m='1750450'>this</span> <span
  m='1751200'>by</span> <span m='1751710'>one</span> <span
  m='1751950'>point,</span> <span m='1752860'>average</span> <span
  m='1753640'>these</span> <span m='1753980'>together,</span> <span
  m='1754590'>and</span> <span m='1754770'>that</span> <span
  m='1754920'>would</span> <span m='1755050'>give</span> <span
  m='1755230'>us</span> <span m='1755370'>the</span> <span
  m='1755460'>next</span> <span m='1755750'>output</span> <span
  m='1756180'>point.</span> <span m='1757070'>And</span> <span m='1757220'>we
  would</span> <span m='1757470'>continue</span> <span m='1757970'>along,</span>
  <span m='1758790'>just</span> <span m='1759010'>simply</span> <span
  m='1759870'>sliding</span> <span m='1760750'>and</span> <span
  m='1760900'>averaging</span> <span m='1761730'>to</span> <span
  m='1761820'>form</span> <span m='1762470'>the</span> <span
  m='1762650'>output</span> <span m='1763060'>data</span> <span
  m='1763320'>sequence.</span> </p><p><span m='1765110'>Now,</span> <span
  m='1765670'>that's</span> <span m='1765950'>an</span> <span
  m='1766010'>example</span> <span m='1766760'>of</span> <span
  m='1767790'>what's</span> <span m='1768360'>commonly</span> <span
  m='1768750'>referred</span> <span m='1769130'>to</span> <span
  m='1769430'>a</span> <span m='1769490'>three-point</span> <span
  m='1770030'>moving</span> <span m='1770380'>average.</span> <span
  m='1771370'>In</span> <span m='1771520'>fact,</span> <span
  m='1772070'>we</span> <span m='1772240'>can</span> <span
  m='1772410'>generalize</span> <span m='1773080'>that</span> <span
  m='1773300'>notion</span> <span m='1774770'>in</span> <span
  m='1774900'>a</span> <span m='1774970'>number</span> <span
  m='1775300'>of</span> <span m='1775410'>ways.</span> <span
  m='1776110'>One</span> <span m='1776400'>way</span> <span
  m='1776880'>of</span> <span m='1777020'>generalizing</span> <span
  m='1778130'>the</span> <span m='1778240'>notion</span> <span
  m='1778820'>of</span> <span m='1778980'>a</span> <span
  m='1779040'>moving</span> <span m='1779390'>average</span> <span
  m='1779920'>from</span> <span m='1780110'>the</span> <span
  m='1780460'>three-point</span> <span m='1780980'>moving</span> <span
  m='1781340'>average,</span> <span m='1781780'>which</span> <span
  m='1782040'>I</span> <span m='1782400'>summarize</span> <span
  m='1783030'>again</span> <span m='1783320'>here,</span> <span
  m='1784230'>is</span> <span m='1784400'>to</span> <span
  m='1784530'>think</span> <span m='1784940'>of</span> <span
  m='1785360'>extending</span> <span m='1785990'>that</span> <span
  m='1786460'>to</span> <span m='1786610'>a</span> <span
  m='1786690'>larger</span> <span m='1787110'>number</span> <span
  m='1787480'>of</span> <span m='1787570'>points,</span> <span
  m='1789030'>and</span> <span m='1789290'>in</span> <span
  m='1789390'>fact</span> <span m='1790180'>applying</span> <span
  m='1790710'>weights</span> <span m='1791130'>to</span> <span
  m='1791270'>that</span> <span m='1791810'>as</span> <span m='1792050'>I</span>
  <span m='1792150'>indicated</span> <span m='1792670'>here,</span> <span
  m='1793540'>so</span> <span m='1793810'>that,</span> <span
  m='1794170'>in</span> <span m='1794320'>addition</span> <span
  m='1795100'>to</span> <span m='1795360'>just</span> <span
  m='1795590'>summing</span> <span m='1795950'>up</span> <span
  m='1796090'>the</span> <span m='1796180'>points</span> <span
  m='1796690'>and</span> <span m='1796810'>dividing</span> <span
  m='1797240'>by</span> <span m='1797410'>the</span> <span
  m='1797520'>number</span> <span m='1797850'>of</span> <span
  m='1797930'>points</span> <span m='1798450'>summed,</span> <span
  m='1799300'>we</span> <span m='1799590'>can,</span> <span
  m='1799840'>in</span> <span m='1799940'>fact,</span> <span
  m='1800410'>apply</span> <span m='1801010'>individual</span> <span
  m='1801730'>weights</span> <span m='1802210'>to</span> <span
  m='1802320'>the</span> <span m='1802410'>points</span> <span
  m='1803290'>so</span> <span m='1803600'>that</span> <span
  m='1803870'>it's</span> <span m='1804310'>what</span> <span
  m='1804590'>is</span> <span m='1804890'>often</span> <span
  m='1805190'>referred</span> <span m='1805610'>to</span> <span m='1806050'>as
  a</span> <span m='1806110'>weighting</span> <span m='1807190'>moving</span>
  <span m='1807540'>average.</span> </p><p><span m='1808590'>And</span> <span
  m='1809030'>I</span> <span m='1809100'>show</span> <span
  m='1810010'>below</span> <span m='1811160'>one</span> <span
  m='1811620'>possible</span> <span m='1812560'>curve</span> <span
  m='1813150'>that</span> <span m='1813430'>might</span> <span
  m='1813680'>result,</span> <span m='1814610'>where</span> <span
  m='1815130'>these</span> <span m='1815590'>would</span> <span
  m='1815780'>be</span> <span m='1816360'>essentially</span> <span
  m='1817000'>the</span> <span m='1817110'>weights</span> <span
  m='1817650'>associated</span> <span m='1819010'>with</span> <span
  m='1819250'>this</span> <span m='1819450'>weighted</span> <span
  m='1820100'>moving</span> <span m='1820480'>average.</span> <span
  m='1821410'>And</span> <span m='1821590'>in</span> <span
  m='1821710'>fact,</span> <span m='1822550'>it's</span> <span
  m='1823360'>easy</span> <span m='1823680'>to</span> <span
  m='1823770'>verify</span> <span m='1824680'>that</span> <span
  m='1824980'>this</span> <span m='1825250'>indeed</span> <span
  m='1825670'>corresponds</span> <span m='1826690'>to</span> <span
  m='1827060'>the</span> <span m='1827240'>impulse</span> <span
  m='1827690'>response</span> <span m='1828420'>of</span> <span
  m='1828550'>the</span> <span m='1828630'>filter.</span> </p><p><span
  m='1830890'>Well,</span> <span m='1831350'>just</span> <span
  m='1831590'>to</span> <span m='1831860'>cement</span> <span
  m='1832280'>this</span> <span m='1832490'>notion,</span> <span
  m='1833120'>let</span> <span m='1833310'>me</span> <span
  m='1834350'>show</span> <span m='1834610'>you</span> <span
  m='1834830'>an</span> <span m='1834910'>example</span> <span
  m='1835450'>or</span> <span m='1835590'>two.</span> <span
  m='1836580'>Here</span> <span m='1836950'>is</span> <span
  m='1837180'>an</span> <span m='1837260'>example</span> <span
  m='1838470'>of</span> <span m='1839000'>a</span> <span
  m='1839730'>five-point</span> <span m='1840590'>moving</span> <span
  m='1840960'>average.</span> <span m='1841410'>A</span> <span
  m='1841490'>five-point</span> <span m='1842010'>moving</span> <span
  m='1842340'>average</span> <span m='1843190'>would</span> <span
  m='1843330'>have</span> <span m='1843790'>an</span> <span
  m='1843930'>impulse</span> <span m='1844400'>response</span> <span
  m='1845610'>that</span> <span m='1846170'>just</span> <span
  m='1846490'>consists</span> <span m='1847030'>of</span> <span
  m='1847160'>a</span> <span m='1847230'>rectangle</span> <span
  m='1847902'>of</span> <span m='1848290'>length</span> <span
  m='1848600'>five.</span> <span m='1850510'>And</span> <span
  m='1850980'>if</span> <span m='1851180'>this</span> <span
  m='1851390'>is</span> <span m='1851540'>convolved</span> <span
  m='1852240'>with</span> <span m='1852380'>a</span> <span
  m='1852460'>data</span> <span m='1852750'>sequence,</span> <span
  m='1853320'>that</span> <span m='1853470'>would</span> <span
  m='1854510'>correspond</span> <span m='1855240'>to</span> <span
  m='1855340'>taking</span> <span m='1855680'>five</span> <span
  m='1856040'>adjacent</span> <span m='1856540'>points</span> <span
  m='1857540'>and,</span> <span m='1857760'>in</span> <span
  m='1857880'>effect,</span> <span m='1858270'>averaging</span> <span
  m='1858595'>them.</span> </p><p><span m='1859870'>We've</span> <span
  m='1860070'>looked</span> <span m='1860350'>previously</span> <span
  m='1861200'>at</span> <span m='1861330'>the</span> <span
  m='1861410'>Fourier</span> <span m='1861920'>transform</span> <span
  m='1862580'>of</span> <span m='1862700'>this</span> <span
  m='1862890'>rectangular</span> <span m='1863540'>sequence.</span> <span
  m='1864240'>And</span> <span m='1864500'>the</span> <span
  m='1864570'>Fourier</span> <span m='1864990'>transform</span> <span
  m='1865630'>of</span> <span m='1865740'>that,</span> <span
  m='1866120'>in</span> <span m='1866250'>fact,</span> <span
  m='1867120'>is</span> <span m='1867750'>of the</span> <span
  m='1867990'>form</span> <span m='1868490'>of</span> <span m='1868600'>a</span>
  <span m='1868660'>sine n x</span> <span m='1870090'>over</span> <span
  m='1870740'>sine x</span> <span m='1871420'>curve.</span> <span
  m='1872300'>And</span> <span m='1872950'>as</span> <span
  m='1873170'>you</span> <span m='1873320'>can</span> <span
  m='1873460'>see,</span> <span m='1874030'>that</span> <span
  m='1874370'>is</span> <span m='1874850'>some</span> <span
  m='1875130'>approximation</span> <span m='1876330'>to</span> <span
  m='1877630'>a</span> <span m='1877720'>lowpass</span> <span
  m='1878330'>filter.</span> <span m='1878860'>And</span> <span
  m='1878990'>so</span> <span m='1879160'>this,</span> <span
  m='1879420'>again,</span> <span m='1879990'>is</span> <span
  m='1881390'>the</span> <span m='1881560'>impulse</span> <span
  m='1881990'>response</span> <span m='1882640'>and</span> <span
  m='1882780'>frequency</span> <span m='1883320'>response</span> <span
  m='1884660'>of</span> <span m='1884820'>a</span> <span
  m='1884910'>nonideal</span> <span m='1885990'>lowpass</span> <span
  m='1886550'>filter.</span> </p><p><span m='1888430'>Now,</span> <span
  m='1889180'>there</span> <span m='1889660'>are</span> <span
  m='1889880'>a</span> <span m='1889920'>variety</span> <span
  m='1890570'>of</span> <span m='1891700'>algorithms</span> <span
  m='1892570'>that,</span> <span m='1893170'>in</span> <span
  m='1893300'>fact,</span> <span m='1893620'>tell</span> <span
  m='1893770'>you</span> <span m='1894030'>how</span> <span
  m='1894360'>to</span> <span m='1894570'>choose</span> <span
  m='1894980'>the</span> <span m='1895070'>weights</span> <span
  m='1895680'>associated</span> <span m='1896720'>with</span> <span
  m='1896870'>a</span> <span m='1897470'>weighted</span> <span
  m='1897840'>moving</span> <span m='1898160'>average</span> <span
  m='1899170'>to,</span> <span m='1899380'>in</span> <span
  m='1899510'>some</span> <span m='1899780'>sense,</span> <span
  m='1900160'>design</span> <span m='1900750'>better</span> <span
  m='1901080'>approximations</span> <span m='1902530'>and</span> <span
  m='1902660'>without</span> <span m='1903130'>going</span> <span
  m='1903400'>into</span> <span m='1903570'>the</span> <span
  m='1903660'>details</span> <span m='1904500'>of</span> <span
  m='1904860'>any</span> <span m='1905060'>of</span> <span
  m='1905140'>those</span> <span m='1905390'>algorithms.</span> </p><p><span
  m='1906510'>Let</span> <span m='1906670'>me</span> <span
  m='1906790'>just</span> <span m='1907290'>show</span> <span
  m='1907600'>the</span> <span m='1907700'>result</span> <span
  m='1909000'>of</span> <span m='1909240'>choosing</span> <span
  m='1909730'>the</span> <span m='1909820'>weights</span> <span
  m='1911330'>for</span> <span m='1911770'>the</span> <span
  m='1911920'>design</span> <span m='1912500'>of</span> <span
  m='1912580'>a</span> <span m='1914280'>251-point</span> <span
  m='1915990'>moving</span> <span m='1916390'>average</span> <span
  m='1916840'>filter,</span> <span m='1917790'>where</span> <span
  m='1918510'>the</span> <span m='1918610'>weights</span> <span
  m='1919090'>are</span> <span m='1919230'>chosen</span> <span
  m='1919820'>using</span> <span m='1920140'>an</span> <span
  m='1920220'>optimum</span> <span m='1920530'>algorithm</span> <span
  m='1921760'>to</span> <span m='1921870'>generate</span> <span
  m='1922430'>as</span> <span m='1922540'>sharp</span> <span
  m='1922910'>a</span> <span m='1923020'>cutoff</span> <span
  m='1923680'>as</span> <span m='1924190'>can</span> <span
  m='1924340'>possibly</span> <span m='1924840'>be</span> <span
  m='1924980'>generated.</span> <span m='1926070'>And</span> <span
  m='1926290'>so</span> <span m='1926450'>what</span> <span m='1926580'>I</span>
  <span m='1926650'>show</span> <span m='1926980'>here</span> <span
  m='1927600'>is</span> <span m='1928110'>the</span> <span
  m='1928700'>frequency</span> <span m='1929220'>response</span> <span
  m='1930580'>of</span> <span m='1931640'>the</span> <span
  m='1931750'>resulting</span> <span m='1932250'>filter</span> <span
  m='1932880'>on</span> <span m='1933040'>a</span> <span
  m='1933100'>logarithmic</span> <span m='1933800'>amplitude</span> <span
  m='1934310'>scale</span> <span m='1934990'>and</span> <span
  m='1935100'>a</span> <span m='1935170'>linear</span> <span
  m='1935520'>frequency</span> <span m='1936070'>scale.</span> <span
  m='1937560'>Notice</span> <span m='1938160'>that</span> <span
  m='1938400'>on</span> <span m='1938520'>this</span> <span
  m='1938700'>scale,</span> <span m='1939060'>the</span> <span
  m='1939140'>passband</span> <span m='1939820'>is</span> <span
  m='1939930'>very</span> <span m='1940150'>flat.</span> <span
  m='1940860'>Although</span> <span m='1941220'>here</span> <span
  m='1941670'>is</span> <span m='1941850'>an</span> <span
  m='1941940'>expanded</span> <span m='1942940'>view</span> <span
  m='1943230'>of</span> <span m='1943400'>it.</span> <span
  m='1943500'>And</span> <span m='1943830'>in</span> <span
  m='1943980'>fact,</span> <span m='1944410'>it</span> <span
  m='1944990'>has</span> <span m='1945240'>what's</span> <span
  m='1945460'>referred</span> <span m='1945850'>to</span> <span
  m='1946080'>as</span> <span m='1946220'>an</span> <span
  m='1946300'>equal-ripple</span> <span m='1947240'>characteristic.</span>
  </p><p><span m='1949350'>And</span> <span m='1949980'>then</span> <span
  m='1950280'>here</span> <span m='1950580'>is</span> <span
  m='1950670'>the</span> <span m='1950760'>transition</span> <span
  m='1951400'>band.</span> <span m='1951970'>And</span> <span
  m='1952130'>here</span> <span m='1952340'>we</span> <span
  m='1952450'>have</span> <span m='1952650'>to</span> <span
  m='1952740'>stopband,</span> <span m='1953940'>which</span> <span
  m='1954370'>in</span> <span m='1954460'>fact</span> <span
  m='1954860'>is</span> <span m='1955010'>down</span> <span
  m='1955340'>somewhat</span> <span m='1955750'>more</span> <span
  m='1956090'>than</span> <span m='1956520'>80 dB</span> <span
  m='1957810'>and,</span> <span m='1957950'>again,</span> <span
  m='1958270'>has</span> <span m='1958760'>what's</span> <span
  m='1959000'>referred</span> <span m='1959420'>to</span> <span
  m='1959780'>as</span> <span m='1960070'>an</span> <span
  m='1960150'>equal-ripple</span> <span m='1960680'>characteristic.</span>
  </p><p><span m='1963770'>Now,</span> <span m='1964820'>the</span> <span
  m='1965890'>notion</span> <span m='1966240'>of</span> <span
  m='1966340'>a</span> <span m='1966400'>moving</span> <span
  m='1966720'>average</span> <span m='1967550'>for</span> <span
  m='1967780'>filtering</span> <span m='1968390'>is</span> <span
  m='1968470'>something</span> <span m='1969210'>that</span> <span
  m='1969550'>is</span> <span m='1969920'>very</span> <span
  m='1970430'>commonly</span> <span m='1971550'>used.</span> <span
  m='1973010'>I</span> <span m='1973450'>had</span> <span
  m='1973790'>shown</span> <span m='1974120'>last</span> <span
  m='1974430'>time</span> <span m='1974640'>actually</span> <span
  m='1975140'>the</span> <span m='1975250'>result</span> <span
  m='1975760'>of</span> <span m='1975930'>some</span> <span
  m='1976100'>filtering</span> <span m='1976780'>on</span> <span
  m='1977070'>a</span> <span m='1977120'>particular</span> <span
  m='1977570'>data</span> <span m='1977860'>sequence,</span> <span
  m='1978820'>the</span> <span m='1979020'>Dow</span> <span
  m='1979250'>Jones</span> <span m='1979610'>Industrial</span> <span
  m='1980200'>Average.</span> <span m='1981260'>And</span> <span
  m='1982280'>very</span> <span m='1982600'>often,</span> <span
  m='1984180'>in</span> <span m='1984710'>looking</span> <span
  m='1985270'>at</span> <span m='1985850'>various</span> <span
  m='1986410'>kinds</span> <span m='1986850'>of</span> <span
  m='1987420'>stock</span> <span m='1987850'>market</span> <span
  m='1988180'>publications,</span> <span m='1989450'>what</span> <span
  m='1989860'>you</span> <span m='1990010'>will</span> <span
  m='1990160'>see</span> <span m='1990870'>is</span> <span
  m='1991840'>the</span> <span m='1992070'>Dow</span> <span
  m='1992320'>Jones</span> <span m='1992710'>average</span> <span
  m='1993810'>shown</span> <span m='1994250'>in</span> <span
  m='1994390'>its</span> <span m='1994530'>raw</span> <span
  m='1994790'>form</span> <span m='1995450'>as</span> <span m='1995620'>a</span>
  <span m='1995690'>data</span> <span m='1995980'>sequence.</span> </p><p><span
  m='1996630'>And</span> <span m='1996730'>then</span> <span
  m='1996870'>very</span> <span m='1997100'>typically,</span> <span
  m='1998670'>you'll</span> <span m='1998920'>see</span> <span
  m='1999240'>also</span> <span m='2000110'>the</span> <span
  m='2000240'>result</span> <span m='2001340'>of</span> <span
  m='2001780'>a</span> <span m='2001860'>moving</span> <span
  m='2002260'>average,</span> <span m='2002820'>where</span> <span
  m='2003180'>the</span> <span m='2003310'>moving</span> <span
  m='2003650'>average</span> <span m='2004180'>might</span> <span m='2004990'>be
  on</span> <span m='2005420'>the</span> <span m='2005520'>order</span> <span
  m='2006030'>of</span> <span m='2006530'>day,</span> <span
  m='2006990'>or</span> <span m='2007120'>it</span> <span
  m='2007170'>might</span> <span m='2007390'>be</span> <span
  m='2007530'>on</span> <span m='2007620'>the</span> <span
  m='2007720'>order</span> <span m='2008060'>of</span> <span
  m='2008160'>months.</span> <span m='2008930'>The</span> <span
  m='2009040'>whole</span> <span m='2009300'>notion</span> <span
  m='2009780'>being</span> <span m='2010640'>to</span> <span
  m='2010800'>take</span> <span m='2011350'>some</span> <span
  m='2011650'>of</span> <span m='2011740'>the</span> <span
  m='2011830'>random</span> <span m='2012710'>high</span> <span
  m='2012950'>frequency</span> <span m='2013510'>fluctuations</span> <span
  m='2014640'>out</span> <span m='2014820'>of</span> <span
  m='2014910'>the</span> <span m='2015070'>average</span> <span
  m='2015920'>and</span> <span m='2016100'>show</span> <span
  m='2016530'>the</span> <span m='2016650'>low</span> <span
  m='2016900'>frequency,</span> <span m='2017820'>or</span> <span
  m='2018510'>trends,</span> <span m='2019940'>over</span> <span
  m='2021110'>some</span> <span m='2021410'>period</span> <span
  m='2021820'>of</span> <span m='2021930'>time.</span> </p><p><span
  m='2023060'>So</span> <span m='2023930'>let's,</span> <span
  m='2024400'>in</span> <span m='2024550'>fact,</span> <span
  m='2024900'>go</span> <span m='2025030'>back</span> <span
  m='2025330'>to</span> <span m='2025430'>the</span> <span
  m='2025510'>Dow</span> <span m='2025750'>Jones</span> <span
  m='2026330'>average.</span> <span m='2026940'>And</span> <span
  m='2027570'>let</span> <span m='2027810'>me</span> <span
  m='2028250'>now</span> <span m='2028450'>show</span> <span
  m='2028720'>you</span> <span m='2029020'>what</span> <span
  m='2029390'>the</span> <span m='2029470'>result</span> <span
  m='2029990'>of</span> <span m='2030200'>filtering</span> <span
  m='2031340'>with</span> <span m='2031880'>a</span> <span
  m='2032450'>moving</span> <span m='2032800'>average</span> <span
  m='2033260'>filter</span> <span m='2033870'>would</span> <span
  m='2034030'>look</span> <span m='2034270'>like</span> <span
  m='2035010'>on</span> <span m='2035790'>the</span> <span
  m='2035850'>same</span> <span m='2036130'>Dow</span> <span
  m='2036330'>Jones</span> <span m='2036690'>industrial</span> <span
  m='2037170'>average</span> <span m='2037420'>sequence</span> <span
  m='2037940'>that</span> <span m='2038040'>I</span> <span
  m='2038080'>showed</span> <span m='2038390'>last</span> <span
  m='2038730'>time.</span> </p><p><span m='2040580'>So</span> <span
  m='2040890'>once</span> <span m='2041170'>again,</span> <span
  m='2041650'>we</span> <span m='2041830'>have</span> <span
  m='2042350'>the</span> <span m='2042520'>Dow</span> <span
  m='2042770'>Jones</span> <span m='2043170'>average</span> <span
  m='2043790'>from</span> <span m='2044010'>1927</span> <span
  m='2045170'>to</span> <span m='2045340'>roughly</span> <span
  m='2045690'>1932.</span> <span m='2047380'>At</span> <span
  m='2047550'>the</span> <span m='2047680'>top,</span> <span
  m='2048280'>we</span> <span m='2048690'>see</span> <span
  m='2049120'>the</span> <span m='2049310'>impulse</span> <span
  m='2049790'>response</span> <span m='2050460'>for</span> <span
  m='2050570'>the</span> <span m='2050670'>moving</span> <span
  m='2051020'>average.</span> <span m='2052080'>Again,</span> <span
  m='2052590'>I</span> <span m='2052699'>remind</span> <span
  m='2053130'>you</span> <span m='2053389'>on</span> <span m='2053590'>an</span>
  <span m='2053690'>expanded</span> <span m='2054250'>time</span> <span
  m='2054530'>scale,</span> <span m='2055469'>and</span> <span
  m='2055790'>what's</span> <span m='2055980'>shown</span> <span
  m='2056300'>here</span> <span m='2056659'>is</span> <span
  m='2056780'>the</span> <span m='2056870'>moving</span> <span
  m='2057190'>average</span> <span m='2058030'>with</span> <span
  m='2058300'>just</span> <span m='2058600'>one</span> <span
  m='2058840'>point.</span> <span m='2059630'>So</span> <span
  m='2059889'>the</span> <span m='2060050'>output</span> <span
  m='2060900'>on</span> <span m='2061270'>the</span> <span
  m='2061380'>bottom</span> <span m='2061739'>trace</span> <span
  m='2062320'>is</span> <span m='2063070'>just</span> <span
  m='2063280'>simply</span> <span m='2063800'>identical</span> <span
  m='2064340'>to</span> <span m='2064449'>the</span> <span
  m='2064580'>input.</span> </p><p><span m='2065790'>Now,</span> <span
  m='2066090'>let's</span> <span m='2066530'>increase</span> <span
  m='2067130'>the</span> <span m='2067280'>length</span> <span
  m='2067530'>of</span> <span m='2067600'>the</span> <span
  m='2067670'>moving</span> <span m='2068000'>average</span> <span
  m='2068440'>to</span> <span m='2068600'>two</span> <span
  m='2068800'>points.</span> <span m='2069389'>And</span> <span
  m='2069610'>we</span> <span m='2069760'>see</span> <span
  m='2070110'>that</span> <span m='2070330'>there</span> <span
  m='2070550'>is</span> <span m='2070659'>a</span> <span
  m='2070719'>small</span> <span m='2071110'>amount</span> <span
  m='2071389'>of</span> <span m='2071469'>smoothing,</span> <span
  m='2072889'>three</span> <span m='2073159'>points</span> <span
  m='2073750'>and</span> <span m='2073960'>just</span> <span
  m='2074170'>a</span> <span m='2074230'>little</span> <span
  m='2074440'>more</span> <span m='2074690'>smoothing,</span> <span
  m='2074995'>that</span> <span m='2075300'>gets</span> <span
  m='2075699'>inserted.</span> <span m='2077489'>Now</span> <span
  m='2078000'>a</span> <span m='2078110'>four-point</span> <span
  m='2078850'>moving</span> <span m='2079230'>average,</span> <span
  m='2081179'>and</span> <span m='2082080'>next</span> <span
  m='2083280'>the</span> <span m='2083590'>five-point</span> <span
  m='2084300'>moving</span> <span m='2084670'>average,</span> <span
  m='2086159'>and</span> <span m='2087000'>a</span> <span
  m='2087110'>six-point</span> <span m='2087710'>moving</span> <span
  m='2088050'>average</span> <span m='2088940'>next.</span> <span
  m='2089320'>And</span> <span m='2089400'>we</span> <span
  m='2089530'>see</span> <span m='2089800'>that</span> <span
  m='2089969'>the</span> <span m='2090050'>smoothing</span> <span
  m='2090570'>increases.</span> </p><p><span m='2091690'>Now,</span> <span
  m='2092120'>let's</span> <span m='2092460'>increase</span> <span
  m='2093120'>the</span> <span m='2093219'>length</span> <span
  m='2093469'>of</span> <span m='2093550'>the</span> <span
  m='2093630'>moving</span> <span m='2093920'>average</span> <span
  m='2094310'>filter</span> <span m='2094639'>much</span> <span
  m='2094889'>more</span> <span m='2095150'>rapidly</span> <span
  m='2096199'>and</span> <span m='2096340'>watch</span> <span
  m='2096820'>how</span> <span m='2097700'>the</span> <span
  m='2097950'>output</span> <span m='2099200'>is</span> <span
  m='2099770'>more</span> <span m='2100210'>and</span> <span
  m='2100310'>more</span> <span m='2100540'>smooth</span> <span
  m='2101150'>in</span> <span m='2101310'>relation</span> <span
  m='2101840'>to</span> <span m='2101970'>the</span> <span
  m='2102100'>input.</span> <span m='2103340'>Again,</span> <span
  m='2103660'>I</span> <span m='2103760'>emphasize</span> <span
  m='2104600'>that</span> <span m='2105290'>the</span> <span
  m='2105510'>time</span> <span m='2105850'>scale</span> <span
  m='2106730'>for</span> <span m='2106980'>the</span> <span
  m='2107160'>impulse</span> <span m='2107620'>response</span> <span
  m='2108680'>is</span> <span m='2108880'>significantly</span> <span
  m='2109670'>expanded</span> <span m='2110500'>in</span> <span
  m='2110650'>relationship</span> <span m='2111780'>to</span> <span
  m='2111890'>the</span> <span m='2112010'>time</span> <span
  m='2112290'>scale</span> <span m='2112720'>for</span> <span
  m='2112850'>both</span> <span m='2113280'>the</span> <span
  m='2113410'>input</span> <span m='2113940'>and</span> <span
  m='2114080'>the</span> <span m='2114210'>output.</span> <span
  m='2116450'>And</span> <span m='2117230'>once</span> <span
  m='2117500'>again,</span> <span m='2118120'>through</span> <span
  m='2118340'>the</span> <span m='2118460'>magic</span> <span
  m='2118860'>of</span> <span m='2118960'>filtering,</span> <span
  m='2119650'>we've</span> <span m='2119840'>been</span> <span
  m='2120000'>able</span> <span m='2120270'>to</span> <span
  m='2120420'>eliminate</span> <span m='2120930'>the</span> <span
  m='2121020'>1929</span> <span m='2122000'>Stock</span> <span
  m='2122390'>Market</span> <span m='2122750'>Crash.</span> </p><p><span
  m='2126530'>All</span> <span m='2126600'>right,</span> <span
  m='2126830'>so</span> <span m='2127330'>we've</span> <span
  m='2127510'>seen</span> <span m='2128020'>moving</span> <span
  m='2128350'>average</span> <span m='2128780'>filters,</span> <span
  m='2130180'>or</span> <span m='2130490'>what</span> <span
  m='2130700'>are</span> <span m='2130780'>sometimes</span> <span
  m='2131270'>referred</span> <span m='2131660'>to</span> <span
  m='2132010'>as</span> <span m='2133040'>non-recursive</span> <span
  m='2134070'>filters.</span> <span m='2135520'>And</span> <span
  m='2136390'>they</span> <span m='2136810'>are,</span> <span
  m='2137110'>as</span> <span m='2137260'>I</span> <span
  m='2137350'>stressed,</span> <span m='2137980'>a</span> <span
  m='2138100'>very</span> <span m='2138410'>important</span> <span
  m='2138860'>class</span> <span m='2139420'>of</span> <span
  m='2139580'>discrete-time</span> <span m='2140240'>filters.</span>
  </p><p><span m='2141880'>Another</span> <span m='2142560'>very</span> <span
  m='2142840'>important</span> <span m='2143250'>class</span> <span
  m='2143630'>of</span> <span m='2143700'>discrete-time</span> <span
  m='2144360'>filters</span> <span m='2145060'>are</span> <span
  m='2145550'>what</span> <span m='2145700'>are</span> <span
  m='2145720'>referred</span> <span m='2146150'>to</span> <span
  m='2146620'>as</span> <span m='2147510'>recursive</span> <span
  m='2148510'>filters.</span> <span m='2149530'>Recursive</span> <span
  m='2150030'>filters</span> <span m='2150580'>are</span> <span
  m='2150640'>filters</span> <span m='2152450'>for</span> <span
  m='2152570'>which</span> <span m='2152810'>the</span> <span
  m='2152910'>difference</span> <span m='2153320'>equation</span> <span
  m='2154400'>has</span> <span m='2154750'>feedback</span> <span
  m='2155870'>from</span> <span m='2156350'>the</span> <span
  m='2156530'>output</span> <span m='2157410'>back</span> <span
  m='2157960'>into</span> <span m='2158270'>the</span> <span
  m='2158400'>input.</span> <span m='2158850'>In</span> <span
  m='2158990'>other</span> <span m='2159140'>words,</span> <span
  m='2159890'>the</span> <span m='2160050'>output</span> <span
  m='2161090'>depends</span> <span m='2162060'>not</span> <span
  m='2162230'>only</span> <span m='2162510'>on</span> <span
  m='2162570'>the</span> <span m='2162690'>input,</span> <span
  m='2163320'>but</span> <span m='2163460'>also</span> <span
  m='2164030'>on</span> <span m='2164190'>previous</span> <span
  m='2164670'>values</span> <span m='2165110'>of</span> <span
  m='2165190'>the</span> <span m='2165330'>output.</span> </p><p><span
  m='2166910'>So</span> <span m='2167260'>for</span> <span
  m='2167430'>example,</span> <span m='2168180'>as</span> <span
  m='2168380'>I've</span> <span m='2168500'>stressed</span> <span
  m='2169120'>previously,</span> <span m='2170040'>a</span> <span
  m='2170300'>recursive</span> <span m='2170870'>difference</span> <span
  m='2171230'>equation</span> <span m='2172390'>has</span> <span
  m='2173090'>the</span> <span m='2173260'>general</span> <span
  m='2173700'>form</span> <span m='2174410'>that</span> <span
  m='2174770'>I</span> <span m='2174930'>indicate</span> <span
  m='2175510'>here,</span> <span m='2176560'>a</span> <span
  m='2176640'>linear</span> <span m='2176980'>combination</span> <span
  m='2177890'>of</span> <span m='2178280'>weighted</span> <span
  m='2178710'>outputs</span> <span m='2179440'>on</span> <span
  m='2179550'>the</span> <span m='2179630'>left-hand</span> <span
  m='2180140'>side</span> <span m='2180700'>and</span> <span
  m='2180830'>linear</span> <span m='2181150'>combination</span> <span
  m='2181760'>of</span> <span m='2181950'>weighted</span> <span
  m='2182420'>inputs</span> <span m='2182950'>on</span> <span
  m='2183040'>the</span> <span m='2183110'>right-hand</span> <span
  m='2183630'>side.</span> <span m='2184720'>And</span> <span
  m='2186490'>as</span> <span m='2186730'>we've</span> <span
  m='2186900'>talked</span> <span m='2187240'>about,</span> <span
  m='2188060'>we</span> <span m='2188280'>can</span> <span
  m='2188620'>solve</span> <span m='2189030'>this</span> <span
  m='2189220'>equation</span> <span m='2189880'>for</span> <span
  m='2190370'>the</span> <span m='2190500'>current</span> <span
  m='2190820'>output</span> <span m='2191230'>y of n</span> <span
  m='2192580'>in</span> <span m='2192770'>terms</span> <span
  m='2193240'>of</span> <span m='2193900'>current</span> <span
  m='2194300'>and</span> <span m='2194410'>past</span> <span
  m='2194790'>inputs</span> <span m='2195480'>and</span> <span
  m='2196140'>past</span> <span m='2196530'>outputs.</span> </p><p><span
  m='2198610'>For</span> <span m='2198790'>example,</span> <span
  m='2199800'>just</span> <span m='2200140'>to</span> <span
  m='2200640'>interpret</span> <span m='2201430'>this,</span> <span
  m='2201980'>focus</span> <span m='2202360'>on</span> <span
  m='2202460'>the</span> <span m='2202550'>interpretation</span> <span
  m='2203290'>of</span> <span m='2203380'>this</span> <span
  m='2203600'>as</span> <span m='2203740'>a</span> <span
  m='2203790'>filter,</span> <span m='2204950'>let's</span> <span
  m='2205480'>look</span> <span m='2205940'>at</span> <span m='2206510'>a</span>
  <span m='2206670'>first</span> <span m='2207050'>order</span> <span
  m='2207280'>difference</span> <span m='2207650'>equation,</span> <span
  m='2208240'>which</span> <span m='2208650'>we've</span> <span
  m='2209200'>talked</span> <span m='2209530'>about</span> <span
  m='2210040'>and</span> <span m='2210280'>generated</span> <span
  m='2210740'>the</span> <span m='2210810'>solution</span> <span
  m='2211320'>to</span> <span m='2211490'>previously.</span> <span
  m='2212770'>So</span> <span m='2212950'>the</span> <span
  m='2213780'>first</span> <span m='2214110'>order</span> <span
  m='2214430'>difference</span> <span m='2214770'>equation</span> <span
  m='2215880'>would</span> <span m='2216340'>be</span> <span
  m='2216560'>as</span> <span m='2216700'>I</span> <span
  m='2216810'>indicated</span> <span m='2217400'>here.</span> <span
  m='2219220'>And</span> <span m='2219930'>imposing</span> <span
  m='2220460'>causality</span> <span m='2221300'>on</span> <span
  m='2221440'>this,</span> <span m='2222230'>so</span> <span
  m='2222490'>that</span> <span m='2222680'>we</span> <span
  m='2222830'>assume</span> <span m='2223470'>that</span> <span
  m='2224150'>we</span> <span m='2224550'>are</span> <span
  m='2224790'>running</span> <span m='2225070'>this</span> <span
  m='2225300'>as</span> <span m='2225430'>a</span> <span
  m='2225500'>recursive</span> <span m='2226080'>forward</span> <span
  m='2226500'>in</span> <span m='2226640'>time,</span> <span
  m='2227730'>we</span> <span m='2228090'>can</span> <span
  m='2228230'>solve</span> <span m='2228600'>this</span> <span
  m='2228830'>for</span> <span m='2228960'>y of n</span> <span
  m='2229690'>in</span> <span m='2229800'>terms</span> <span
  m='2230130'>of</span> <span m='2230220'>x of n</span> <span
  m='2231120'>and</span> <span m='2232290'>y of n</span> <span
  m='2233020'>minus</span> <span m='2233420'>1</span> <span
  m='2233870'>weighted</span> <span m='2234410'>by</span> <span
  m='2234720'>the</span> <span m='2234840'>factor</span> <span
  m='2235370'>a.</span> <span m='2236520'>And</span> <span m='2236990'>I</span>
  <span m='2237090'>simply</span> <span m='2237440'>indicate</span> <span
  m='2238420'>the</span> <span m='2238620'>block</span> <span
  m='2238980'>diagram</span> <span m='2239990'>for</span> <span
  m='2240200'>this.</span> </p><p><span m='2240970'>But</span> <span
  m='2241340'>what</span> <span m='2241520'>we</span> <span
  m='2241640'>want</span> <span m='2241840'>to</span> <span
  m='2241960'>examine</span> <span m='2242480'>now</span> <span
  m='2243140'>for</span> <span m='2243330'>this</span> <span
  m='2243560'>first</span> <span m='2243890'>order</span> <span
  m='2244120'>recursion</span> <span m='2245320'>is</span> <span
  m='2246040'>the</span> <span m='2246410'>frequency</span> <span
  m='2247040'>response</span> <span m='2247830'>and</span> <span
  m='2248040'>see</span> <span m='2248230'>its</span> <span
  m='2248400'>interpretation</span> <span m='2249520'>as</span> <span
  m='2249690'>a</span> <span m='2249730'>filter.</span> <span
  m='2250840'>Well</span> <span m='2251350'>in</span> <span
  m='2251510'>fact,</span> <span m='2252220'>again,</span> <span
  m='2252880'>the</span> <span m='2253010'>mathematics</span> <span
  m='2253740'>for</span> <span m='2253840'>this</span> <span
  m='2254160'>we've</span> <span m='2254330'>gone</span> <span
  m='2254610'>through</span> <span m='2255590'>in</span> <span
  m='2255700'>the</span> <span m='2255790'>last</span> <span
  m='2256140'>lecture.</span> <span m='2257540'>And</span> <span
  m='2258130'>so</span> <span m='2258520'>interpreting</span> <span
  m='2259250'>the</span> <span m='2259430'>first</span> <span
  m='2259690'>order</span> <span m='2259990'>difference</span> <span
  m='2260290'>equation</span> <span m='2260970'>as</span> <span
  m='2261160'>a</span> <span m='2261210'>system,</span> <span
  m='2264490'>what</span> <span m='2264850'>we're</span> <span
  m='2265020'>attempting</span> <span m='2265510'>to</span> <span
  m='2266320'>generate</span> <span m='2267020'>is</span> <span
  m='2267360'>the</span> <span m='2267530'>frequency</span> <span
  m='2268130'>response,</span> <span m='2269340'>which</span> <span
  m='2269540'>is</span> <span m='2269640'>the</span> <span
  m='2269710'>Fourier</span> <span m='2270130'>transform</span> <span
  m='2270730'>of</span> <span m='2270810'>the</span> <span
  m='2270930'>impulse</span> <span m='2271400'>response.</span> <span
  m='2272760'>And</span> <span m='2274030'>from</span> <span
  m='2274330'>the</span> <span m='2274410'>difference</span> <span
  m='2274800'>equation,</span> <span m='2275380'>we</span> <span
  m='2275520'>can,</span> <span m='2275680'>of</span> <span
  m='2275780'>course,</span> <span m='2276080'>solve</span> <span
  m='2276670'>for</span> <span m='2276880'>either</span> <span
  m='2277060'>one</span> <span m='2277260'>of</span> <span
  m='2277380'>those</span> <span m='2278330'>by</span> <span
  m='2279220'>using</span> <span m='2279940'>the</span> <span
  m='2280040'>properties,</span> <span m='2280790'>exploiting</span> <span
  m='2281270'>the</span> <span m='2281350'>properties,</span> <span
  m='2281930'>of</span> <span m='2282050'>Fourier</span> <span
  m='2282530'>transform.</span> </p><p><span m='2283770'>Applying</span> <span
  m='2284150'>the</span> <span m='2284220'>Fourier</span> <span
  m='2284630'>transform</span> <span m='2285300'>to</span> <span
  m='2285410'>the</span> <span m='2285510'>difference</span> <span
  m='2285890'>equation,</span> <span m='2287360'>we</span> <span
  m='2287760'>will</span> <span m='2287990'>end</span> <span
  m='2288180'>up</span> <span m='2288430'>with</span> <span
  m='2288870'>the</span> <span m='2289100'>Fourier</span> <span
  m='2289570'>transform</span> <span m='2290300'>of</span> <span
  m='2290380'>the</span> <span m='2290520'>output</span> <span
  m='2291550'>equal</span> <span m='2292060'>to</span> <span
  m='2292210'>the</span> <span m='2292300'>Fourier</span> <span
  m='2292650'>transform</span> <span m='2292980'>of</span> <span
  m='2293310'>the</span> <span m='2293410'>input</span> <span
  m='2294270'>times</span> <span m='2294650'>this</span> <span
  m='2294920'>factor,</span> <span m='2295530'>which</span> <span
  m='2296040'>we</span> <span m='2296190'>know</span> <span
  m='2296430'>from</span> <span m='2296630'>the</span> <span
  m='2296720'>convolution</span> <span m='2297430'>property,</span> <span
  m='2298200'>in</span> <span m='2298340'>fact,</span> <span
  m='2299160'>is</span> <span m='2300340'>the</span> <span
  m='2300990'>frequency</span> <span m='2301550'>response</span> <span
  m='2302910'>of</span> <span m='2303140'>the</span> <span
  m='2303240'>system.</span> <span m='2304980'>So</span> <span
  m='2305320'>this</span> <span m='2305520'>is</span> <span
  m='2305660'>the</span> <span m='2305750'>frequency</span> <span
  m='2306310'>response.</span> <span m='2307440'>And</span> <span
  m='2307600'>of</span> <span m='2307700'>course,</span> <span
  m='2308270'>the</span> <span m='2308600'>inverse</span> <span
  m='2309070'>Fourier</span> <span m='2309460'>transform</span> <span
  m='2310140'>of</span> <span m='2310240'>that,</span> <span
  m='2311290'>which</span> <span m='2311670'>I</span> <span
  m='2313090'>indicate</span> <span m='2313630'>below,</span> <span
  m='2314270'>is</span> <span m='2314890'>the</span> <span
  m='2315320'>system</span> <span m='2316060'>impulse</span> <span
  m='2316530'>response.</span> </p><p><span m='2317910'>So</span> <span
  m='2318370'>we</span> <span m='2318510'>have</span> <span
  m='2318920'>the</span> <span m='2319010'>frequency</span> <span
  m='2319550'>response</span> <span m='2320130'>obtained</span> <span
  m='2320600'>by</span> <span m='2321060'>applying</span> <span
  m='2321430'>the</span> <span m='2321510'>Fourier</span> <span
  m='2321900'>transform</span> <span m='2322440'>to</span> <span
  m='2322550'>the</span> <span m='2322630'>difference</span> <span
  m='2322980'>equation,</span> <span m='2324020'>the</span> <span
  m='2324150'>impulse</span> <span m='2324600'>response.</span> <span
  m='2326190'>And,</span> <span m='2326940'>as</span> <span
  m='2327240'>we</span> <span m='2327350'>did</span> <span
  m='2327550'>last</span> <span m='2327930'>time,</span> <span
  m='2329210'>we</span> <span m='2329470'>can</span> <span
  m='2330290'>look</span> <span m='2330750'>at</span> <span
  m='2331640'>that</span> <span m='2332180'>in</span> <span
  m='2332360'>terms</span> <span m='2332920'>of</span> <span
  m='2333960'>a</span> <span m='2334200'>frequency</span> <span
  m='2334730'>response</span> <span m='2335650'>characteristic.</span> <span
  m='2336990'>And</span> <span m='2337280'>recall</span> <span
  m='2338090'>that,</span> <span m='2338830'>depending</span> <span
  m='2339270'>on</span> <span m='2339440'>whether</span> <span
  m='2340290'>the</span> <span m='2340440'>factor</span> <span
  m='2340910'>a</span> <span m='2341240'>is</span> <span
  m='2341470'>positive</span> <span m='2341990'>or</span> <span
  m='2342060'>negative,</span> <span m='2343040'>we</span> <span
  m='2343210'>either</span> <span m='2343450'>get</span> <span
  m='2344160'>a</span> <span m='2344250'>lowpass</span> <span
  m='2344820'>filter</span> <span m='2345370'>or</span> <span
  m='2345560'>a</span> <span m='2345600'>highpass</span> <span
  m='2346210'>filter.</span> </p><p><span m='2347840'>And</span> <span
  m='2349280'>if,</span> <span m='2349660'>in</span> <span
  m='2349830'>fact,</span> <span m='2350210'>we</span> <span
  m='2350310'>look</span> <span m='2350600'>at</span> <span
  m='2351000'>the</span> <span m='2351150'>frequency</span> <span
  m='2351660'>response</span> <span m='2352890'>for</span> <span
  m='2353070'>the</span> <span m='2353170'>factor</span> <span
  m='2353690'>a</span> <span m='2353870'>being</span> <span
  m='2354160'>positive,</span> <span m='2355430'>then</span> <span
  m='2355680'>we</span> <span m='2355800'>see</span> <span
  m='2356090'>that</span> <span m='2356270'>this</span> <span
  m='2356450'>is</span> <span m='2356580'>an</span> <span
  m='2356640'>approximation</span> <span m='2357840'>to</span> <span
  m='2358840'>a</span> <span m='2358930'>lowpass</span> <span
  m='2359560'>filter,</span> <span m='2360750'>whereas</span> <span
  m='2361200'>below</span> <span m='2361660'>it</span> <span
  m='2361930'>I</span> <span m='2362080'>show</span> <span
  m='2362670'>the</span> <span m='2362910'>frequency</span> <span
  m='2363460'>response</span> <span m='2364640'>for</span> <span
  m='2364800'>a</span> <span m='2365350'>negative.</span> <span
  m='2366390'>And</span> <span m='2366600'>there</span> <span
  m='2369210'>this</span> <span m='2369480'>corresponds</span> <span
  m='2370110'>to</span> <span m='2370280'>a</span> <span
  m='2370740'>highpass</span> <span m='2371380'>filter,</span> <span
  m='2371810'>because</span> <span m='2372300'>we're</span> <span
  m='2372460'>attenuating</span> <span m='2373460'>low</span> <span
  m='2373680'>frequencies</span> <span m='2375100'>and</span> <span
  m='2375740'>retaining</span> <span m='2376730'>the</span> <span
  m='2376820'>high</span> <span m='2377040'>frequencies.</span> </p><p><span
  m='2379350'>And</span> <span m='2379940'>recall</span> <span
  m='2380370'>also</span> <span m='2381210'>that</span> <span
  m='2382220'>we</span> <span m='2382580'>illustrated</span> <span
  m='2384830'>this</span> <span m='2385110'>characteristic</span> <span
  m='2385850'>as</span> <span m='2385990'>a</span> <span
  m='2386050'>lowpass</span> <span m='2386540'>or</span> <span
  m='2386610'>highpass</span> <span m='2387140'>filter</span> <span
  m='2388680'>for</span> <span m='2388780'>the</span> <span
  m='2388860'>first</span> <span m='2389170'>order</span> <span
  m='2389860'>recursion</span> <span m='2391010'>by</span> <span
  m='2391400'>looking</span> <span m='2391940'>at</span> <span
  m='2392540'>how</span> <span m='2393760'>it</span> <span
  m='2394250'>worked</span> <span m='2394610'>as</span> <span
  m='2394860'>a</span> <span m='2394910'>filter</span> <span
  m='2395500'>in</span> <span m='2395660'>both</span> <span
  m='2395910'>cases</span> <span m='2396970'>when</span> <span
  m='2397150'>the</span> <span m='2397300'>input</span> <span
  m='2397700'>was</span> <span m='2398020'>the</span> <span
  m='2398090'>Dow</span> <span m='2398300'>Jones</span> <span
  m='2398660'>average.</span> <span m='2399030'>And</span> <span
  m='2399110'>indeed,</span> <span m='2399450'>we</span> <span
  m='2399580'>saw</span> <span m='2399920'>that</span> <span
  m='2400560'>it</span> <span m='2401120'>generated</span> <span
  m='2401750'>both</span> <span m='2402090'>lowpass</span> <span
  m='2402260'>and</span> <span m='2402630'>highpass</span> <span
  m='2403160'>filtering</span> <span m='2403820'>in</span> <span
  m='2404220'>the</span> <span m='2404320'>appropriate</span> <span
  m='2404830'>cases.</span> </p><p><span m='2406380'>So</span> <span
  m='2406550'>for</span> <span m='2406680'>discrete-time,</span> <span
  m='2408030'>we</span> <span m='2408160'>have</span> <span
  m='2408730'>the</span> <span m='2408840'>two</span> <span
  m='2409040'>classes,</span> <span m='2409550'>moving</span> <span
  m='2409880'>average</span> <span m='2410570'>and</span> <span
  m='2411400'>recursive</span> <span m='2413000'>filters.</span> <span
  m='2414210'>And</span> <span m='2415060'>there</span> <span
  m='2415250'>are</span> <span m='2415300'>a</span> <span
  m='2415330'>variety</span> <span m='2415820'>of</span> <span
  m='2415900'>issues</span> <span m='2416260'>discussed</span> <span
  m='2416730'>in</span> <span m='2416800'>the</span> <span
  m='2416900'>text</span> <span m='2417270'>about</span> <span
  m='2417590'>why,</span> <span m='2418070'>in</span> <span
  m='2418340'>certain</span> <span m='2418630'>contexts,</span> <span
  m='2419220'>one</span> <span m='2419470'>might</span> <span
  m='2419760'>want</span> <span m='2419920'>to</span> <span
  m='2419960'>use</span> <span m='2420700'>one</span> <span
  m='2420970'>of</span> <span m='2421020'>the</span> <span
  m='2421180'>other.</span> <span m='2421390'>Basically,</span> <span
  m='2421920'>what</span> <span m='2422070'>happens</span> <span
  m='2422760'>is</span> <span m='2423080'>that</span> <span
  m='2423920'>for</span> <span m='2424020'>the</span> <span
  m='2424110'>moving</span> <span m='2424430'>average</span> <span
  m='2424870'>filter,</span> <span m='2426360'>for</span> <span
  m='2426550'>a</span> <span m='2426580'>given</span> <span
  m='2426910'>set</span> <span m='2427140'>a</span> <span
  m='2427180'>filter</span> <span m='2427540'>specifications,</span> <span
  m='2428540'>there</span> <span m='2428660'>are</span> <span
  m='2428690'>many</span> <span m='2428900'>more</span> <span
  m='2429080'>multiplications</span> <span m='2430240'>required</span> <span
  m='2431040'>than</span> <span m='2431440'>for</span> <span
  m='2431680'>a</span> <span m='2431710'>recursive</span> <span
  m='2432260'>filter.</span> <span m='2433190'>But</span> <span
  m='2433660'>there</span> <span m='2434030'>are,</span> <span
  m='2434300'>in</span> <span m='2434380'>certain</span> <span
  m='2434710'>contexts,</span> <span m='2435310'>some</span> <span
  m='2435670'>very</span> <span m='2435870'>important</span> <span
  m='2436250'>compensating</span> <span m='2436930'>benefits</span> <span
  m='2437780'>for</span> <span m='2437930'>the</span> <span
  m='2438000'>moving</span> <span m='2438320'>average</span> <span
  m='2438700'>filter.</span> </p><p><span m='2441450'>Now,</span> <span
  m='2442660'>this</span> <span m='2442880'>concludes,</span> <span
  m='2444010'>pretty</span> <span m='2444240'>much,</span> <span
  m='2444760'>what</span> <span m='2445570'>I</span> <span
  m='2446460'>want</span> <span m='2446810'>to</span> <span
  m='2446900'>say</span> <span m='2447200'>in</span> <span
  m='2447320'>detail</span> <span m='2448170'>about</span> <span
  m='2448820'>filtering,</span> <span m='2449840'>the</span> <span
  m='2449930'>concept</span> <span m='2450430'>of</span> <span
  m='2450520'>filtering,</span> <span m='2451040'>in</span> <span
  m='2451110'>the</span> <span m='2451200'>set</span> <span
  m='2451470'>of</span> <span m='2451560'>lectures.</span> <span
  m='2452880'>This</span> <span m='2453100'>is</span> <span
  m='2453480'>only</span> <span m='2453820'>a</span> <span
  m='2453910'>very</span> <span m='2454900'>quick</span> <span
  m='2455390'>glimpse</span> <span m='2455990'>into</span> <span
  m='2456660'>a</span> <span m='2456780'>very</span> <span
  m='2457100'>important</span> <span m='2457830'>and</span> <span
  m='2458200'>very</span> <span m='2458440'>rich</span> <span
  m='2458720'>topic,</span> <span m='2459240'>and</span> <span
  m='2459340'>one,</span> <span m='2459570'>of</span> <span
  m='2459680'>course,</span> <span m='2460070'>that</span> <span
  m='2460650'>can</span> <span m='2460760'>be</span> <span
  m='2460880'>studied</span> <span m='2461440'>on</span> <span
  m='2461590'>its</span> <span m='2461730'>own</span> <span m='2461960'>in
  an</span> <span m='2462130'>considerable</span> <span
  m='2462770'>amount</span> <span m='2463030'>of</span> <span
  m='2463120'>detail.</span> </p><p><span m='2465250'>As</span> <span
  m='2465930'>the</span> <span m='2466020'>lectures</span> <span
  m='2466710'>go</span> <span m='2466880'>on,</span> <span
  m='2467450'>what</span> <span m='2467640'>we'll</span> <span
  m='2467820'>find</span> <span m='2468380'>is</span> <span
  m='2468690'>that</span> <span m='2469210'>the</span> <span
  m='2469350'>basic</span> <span m='2469760'>concept</span> <span
  m='2470370'>of</span> <span m='2470450'>filtering,</span> <span
  m='2471030'>both</span> <span m='2471780'>ideal</span> <span
  m='2472045'>and</span> <span m='2472310'>nonideal</span> <span
  m='2473010'>filtering,</span> <span m='2474570'>will</span> <span
  m='2475380'>be</span> <span m='2475750'>a</span> <span m='2475840'>very</span>
  <span m='2476120'>important</span> <span m='2476660'>part</span> <span
  m='2477150'>of</span> <span m='2477740'>what</span> <span
  m='2477950'>we</span> <span m='2478080'>do.</span> <span
  m='2479180'>And</span> <span m='2480240'>in</span> <span
  m='2480420'>particular,</span> <span m='2482240'>beginning</span> <span
  m='2482650'>with</span> <span m='2482810'>the</span> <span
  m='2482890'>next</span> <span m='2483210'>lecture,</span> <span
  m='2484090'>we'll</span> <span m='2484370'>turn</span> <span
  m='2484930'>to</span> <span m='2485320'>a</span> <span
  m='2485400'>discussion</span> <span m='2485920'>of</span> <span
  m='2486000'>modulation,</span> <span m='2487800'>exploiting</span> <span
  m='2489500'>the</span> <span m='2489930'>property</span> <span
  m='2491010'>of</span> <span m='2491140'>modulation</span> <span
  m='2492140'>as</span> <span m='2492640'>it</span> <span
  m='2492770'>relates</span> <span m='2493270'>to</span> <span
  m='2493490'>some</span> <span m='2493680'>practical</span> <span
  m='2494200'>problems.</span> <span m='2495340'>And</span> <span
  m='2495550'>what</span> <span m='2495740'>we'll</span> <span
  m='2495910'>find</span> <span m='2496740'>when</span> <span
  m='2496890'>we</span> <span m='2497010'>do</span> <span
  m='2497260'>that</span> <span m='2497780'>is</span> <span
  m='2498120'>that</span> <span m='2498360'>a</span> <span
  m='2498480'>very</span> <span m='2498830'>important</span> <span
  m='2499280'>part</span> <span m='2499520'>of</span> <span
  m='2499590'>that</span> <span m='2499800'>discussion</span> <span
  m='2500900'>and,</span> <span m='2501030'>in</span> <span
  m='2501120'>fact,</span> <span m='2501440'>a</span> <span
  m='2501470'>very</span> <span m='2501680'>important</span> <span
  m='2502210'>part</span> <span m='2502660'>of</span> <span
  m='2503640'>the</span> <span m='2503730'>use</span> <span
  m='2504040'>of</span> <span m='2504120'>modulation</span> <span
  m='2505130'>also</span> <span m='2505900'>just</span> <span
  m='2506370'>naturally</span> <span m='2506920'>incorporates</span> <span
  m='2508120'>the</span> <span m='2508250'>concept</span> <span
  m='2509100'>and</span> <span m='2509770'>properties</span> <span
  m='2510380'>of</span> <span m='2510460'>filtering.</span> <span
  m='2511270'>Thank</span> <span m='2511490'>you.</span> </p>
embedded_media:
  - uid: 0ae5e1f48068122eb5043d3ef9e13834
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: P5Ce9tbK86M
  - uid: c707ad6486900151ea55a527bd1e3064
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/P5Ce9tbK86M/default.jpg'
  - uid: 40c62187c3dcc9731dd24d172ad3fe2d
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: >-
      http://www.archive.org/download/MITRES.6.007S11/MITRES_6-007S11lec12_300k.mp4
  - uid: ccfdc36a89317db4e94f9114f2a5e46b
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/podcast/lecture-12-filtering/id458320213?i=96547360
  - uid: 1f4cdcf7436ec40c146750e827671697
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: MITRES_6_007S11_lec12.pdf
    title: MITRES_6_007S11_lec12.pdf
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-12-filtering/MITRES_6_007S11_lec12.pdf
  - uid: eed1409ef1d6c757febd22358234916b
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: P5Ce9tbK86M
  - uid: dc1d349982294d27c89fd71b02996357
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: P5Ce9tbK86M.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-12-filtering/P5Ce9tbK86M.srt
  - uid: 1aa03c3fed59f6b55d994d766a94771a
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: P5Ce9tbK86M.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-007-signals-and-systems-spring-2011/video-lectures/lecture-12-filtering/P5Ce9tbK86M.pdf
  - uid: e8d914e62bf522bb84c341fcf0d423b8
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 1b2454ed7d56d8a186f40433f7891273
    parent_uid: ca8df82ff8cdcc584aa80af112b53b96
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-007-signals-and-systems-spring-2011
type: course
layout: video
---