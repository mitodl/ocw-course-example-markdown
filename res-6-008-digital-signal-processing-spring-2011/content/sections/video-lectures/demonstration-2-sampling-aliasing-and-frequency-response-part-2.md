---
order_index: null
title: 'Demonstration 2: Sampling, Aliasing, and Frequency Response, Part 2'
template_type: Tabbed
uid: fccc67d08ddad9de3e4b638b220338b6
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-2-sampling-aliasing-and-frequency-response-part-2
short_url: demonstration-2-sampling-aliasing-and-frequency-response-part-2
inline_embed_id: '56682341demonstration2:sampling,aliasing,andfrequencyresponse,part261625532'
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
  m='23462'>[MUSIC PLAYING]</span> </p><p></p><p><span m='50060'>ALAN
  OPPENHEIM:</span> <span m='50150'>Here</span> <span m='50240'>we</span> <span
  m='50360'>demonstrate</span> <span m='51020'>the</span> <span
  m='51140'>effects</span> <span m='51500'>of</span> <span
  m='51590'>sampling</span> <span m='52100'>and</span> <span
  m='52190'>aliasing</span> <span m='52760'>by</span> <span
  m='52940'>using</span> <span m='53390'>this</span> <span
  m='53570'>non-recursive</span> <span m='54320'>digital</span> <span
  m='54680'>filter.</span> <span m='55430'>Where</span> <span
  m='55790'>as</span> <span m='55970'>a</span> <span m='56030'>digital</span>
  <span m='56390'>filter,</span> <span m='56990'>it's</span> <span
  m='57160'>simply</span> <span m='57500'>set</span> <span m='57770'>up</span>
  <span m='58070'>as</span> <span m='58250'>an</span> <span
  m='58370'>identity</span> <span m='58910'>system.</span> <span
  m='60020'>But</span> <span m='60650'>we</span> <span m='60800'>take</span>
  <span m='61040'>advantage</span> <span m='61490'>of</span> <span
  m='61580'>the</span> <span m='61700'>fact</span> <span m='62060'>that</span>
  <span m='62180'>it</span> <span m='62270'>has</span> <span m='62480'>a</span>
  <span m='62540'>sampler</span> <span m='64010'>for</span> <span
  m='64160'>the</span> <span m='64310'>input</span> <span m='64849'>and</span>
  <span m='65150'>a</span> <span m='65540'>de-sampler</span> <span
  m='66350'>for</span> <span m='66500'>the</span> <span m='66650'>output.</span>
  </p><p><span m='68620'>To</span> <span m='68800'>demonstrate</span> <span
  m='70180'>the</span> <span m='71200'>sampling</span> <span
  m='71650'>and</span> <span m='71760'>aliasing</span> <span
  m='72310'>effect,</span> <span m='73090'>we'll</span> <span
  m='73190'>use</span> <span m='73420'>a</span> <span
  m='73480'>sinusoidal</span> <span m='74200'>input.</span> <span
  m='74770'>And</span> <span m='75040'>so</span> <span m='75460'>on</span> <span
  m='75580'>the</span> <span m='75700'>oscilloscope,</span> <span
  m='76970'>what</span> <span m='77120'>we</span> <span m='77290'>have</span>
  <span m='77800'>are</span> <span m='78490'>two</span> <span
  m='78670'>traces.</span> <span m='79330'>The</span> <span m='79450'>top</span>
  <span m='79750'>trace</span> <span m='80200'>is</span> <span
  m='80380'>the</span> <span m='80500'>input</span> <span
  m='80830'>sinusoid.</span> <span m='82090'>And</span> <span
  m='82180'>the</span> <span m='82270'>bottom</span> <span
  m='82600'>trace</span> <span m='83170'>is</span> <span m='83440'>the</span>
  <span m='83590'>output</span> <span m='83980'>sinusoid.</span> </p><p><span
  m='85360'>And</span> <span m='85480'>we</span> <span m='85630'>know</span>
  <span m='85990'>that</span> <span m='87520'>we</span> <span
  m='88120'>expect</span> <span m='88900'>that</span> <span m='89260'>as</span>
  <span m='89830'>the</span> <span m='90130'>input</span> <span
  m='90550'>sinusoidal</span> <span m='91180'>frequency</span> <span
  m='91780'>is</span> <span m='91930'>increased,</span> <span
  m='92890'>the</span> <span m='93040'>output</span> <span
  m='93370'>sinusoidal</span> <span m='93970'>frequency</span> <span
  m='94900'>will</span> <span m='95080'>likewise</span> <span
  m='96010'>increase</span> <span m='97600'>until</span> <span
  m='97960'>we</span> <span m='98140'>get</span> <span m='98620'>into</span>
  <span m='98860'>the</span> <span m='98950'>vicinity</span> <span
  m='99490'>of</span> <span m='99580'>half</span> <span m='99820'>the</span>
  <span m='99910'>sampling</span> <span m='100390'>frequency.</span> <span
  m='101880'>In</span> <span m='101950'>the</span> <span
  m='102010'>vicinity</span> <span m='102370'>of</span> <span
  m='102460'>half</span> <span m='102700'>the</span> <span
  m='102790'>sampling</span> <span m='103300'>frequency,</span> <span
  m='104920'>because</span> <span m='105310'>of</span> <span
  m='105400'>the</span> <span m='105520'>fact</span> <span
  m='106030'>that</span> <span m='106240'>the</span> <span m='106300'>low</span>
  <span m='106510'>pass</span> <span m='106870'>filter</span> <span
  m='107410'>is</span> <span m='107590'>not</span> <span m='107830'>an</span>
  <span m='107950'>ideal</span> <span m='108350'>low</span> <span
  m='108550'>pass</span> <span m='108910'>filter,</span> <span
  m='109510'>we</span> <span m='109690'>have</span> <span m='110110'>a</span>
  <span m='110170'>beating</span> <span m='110560'>effect.</span> <span
  m='112000'>And</span> <span m='112180'>we</span> <span m='112300'>see</span>
  <span m='112510'>the</span> <span m='112630'>beating</span> <span
  m='112900'>effect</span> <span m='113290'>evident</span> <span
  m='113650'>here.</span> </p><p><span m='114640'>Now</span> <span
  m='116020'>if</span> <span m='116230'>we</span> <span m='116350'>were</span>
  <span m='116560'>to</span> <span m='116920'>increase</span> <span
  m='117520'>the</span> <span m='118180'>input</span> <span
  m='118510'>frequency</span> <span m='119110'>past</span> <span
  m='119500'>the</span> <span m='119830'>half</span> <span m='120100'>the</span>
  <span m='120190'>sampling</span> <span m='120700'>frequency,</span> <span
  m='122080'>even</span> <span m='122380'>though</span> <span
  m='122560'>the</span> <span m='122710'>input</span> <span
  m='123070'>frequency</span> <span m='124030'>would</span> <span
  m='124390'>increase,</span> <span m='125470'>the</span> <span
  m='125620'>output</span> <span m='126010'>frequency</span> <span
  m='126610'>would</span> <span m='126760'>decrease</span> <span
  m='127330'>due</span> <span m='127510'>to</span> <span
  m='127600'>aliasing.</span> <span m='128710'>And</span> <span
  m='128830'>let's</span> <span m='129039'>illustrate</span> <span
  m='129550'>that</span> <span m='130000'>by</span> <span
  m='130479'>first</span> <span m='131440'>moving</span> <span
  m='131800'>back</span> <span m='132100'>down</span> <span
  m='132400'>toward</span> <span m='132640'>DC.</span> <span
  m='134380'>And</span> <span m='134560'>then</span> <span
  m='135160'>using</span> <span m='135490'>an</span> <span
  m='135580'>automatic</span> <span m='136090'>sweep,</span> <span
  m='137080'>to</span> <span m='137200'>sweep</span> <span m='137590'>us</span>
  <span m='138070'>from</span> <span m='138340'>DC</span> <span
  m='139450'>through</span> <span m='139780'>half</span> <span
  m='140050'>the</span> <span m='140140'>sampling</span> <span
  m='140620'>frequency</span> <span m='141460'>up</span> <span
  m='141700'>to</span> <span m='141940'>the</span> <span
  m='142060'>sampling</span> <span m='142510'>frequency.</span> </p><p><span
  m='147000'>And</span> <span m='147420'>so</span> <span m='147660'>here</span>
  <span m='147900'>we</span> <span m='148380'>get</span> <span
  m='148620'>in</span> <span m='148740'>the</span> <span
  m='148800'>vicinity</span> <span m='149310'>of</span> <span
  m='149400'>half</span> <span m='149670'>the</span> <span
  m='149760'>sampling</span> <span m='150210'>frequency.</span> <span
  m='150800'>We</span> <span m='150930'>see</span> <span m='151110'>the</span>
  <span m='151200'>beating</span> <span m='151560'>effect.</span> <span
  m='152510'>Past</span> <span m='152880'>that,</span> <span
  m='153180'>the</span> <span m='153330'>output</span> <span
  m='153690'>frequency</span> <span m='154200'>decreases,</span> <span
  m='154950'>even</span> <span m='155190'>though</span> <span
  m='155340'>the</span> <span m='155490'>input</span> <span
  m='155790'>frequency</span> <span m='156360'>is</span> <span
  m='156480'>increasing.</span> </p><p><span m='158130'>And</span> <span
  m='158280'>now,</span> <span m='159580'>let's</span> <span
  m='159960'>illustrate</span> <span m='160500'>that</span> <span
  m='160830'>once</span> <span m='161160'>more.</span> <span
  m='161520'>But</span> <span m='161700'>in</span> <span m='161820'>this</span>
  <span m='162000'>case,</span> <span m='162810'>let's</span> <span
  m='163440'>listen</span> <span m='163980'>to</span> <span
  m='164130'>the</span> <span m='164280'>output</span> <span
  m='164820'>as</span> <span m='164970'>well</span> <span m='165210'>as</span>
  <span m='165360'>watching</span> <span m='165780'>the</span> <span
  m='165900'>output.</span> </p><p><span m='167306'>[HIGH PITCH
  FREQUENCY]</span> </p><p><span m='168740'>We hear it</span> <span
  m='169218'>increase.</span> <span m='173050'>And</span> <span
  m='173140'>then</span> <span m='173290'>we</span> <span m='173440'>hear</span>
  <span m='173620'>the</span> <span m='173800'>output</span> <span
  m='174270'>frequency</span> <span m='174757'>decrease.</span> </p><p><span
  m='176218'>[FREQUENCY STOPS]</span> </p><p></p><p><span m='187910'>What</span>
  <span m='188060'>we</span> <span m='188150'>see</span> <span
  m='188420'>here</span> <span m='188810'>is</span> <span m='189200'>the</span>
  <span m='189770'>impulse</span> <span m='190250'>response</span> <span
  m='191090'>of</span> <span m='191540'>the</span> <span
  m='191690'>overall</span> <span m='192110'>system.</span> <span
  m='193970'>And</span> <span m='194990'>we</span> <span
  m='195500'>observe,</span> <span m='195830'>for</span> <span
  m='195980'>one</span> <span m='196190'>thing,</span> <span
  m='196430'>that</span> <span m='196640'>it's</span> <span m='196820'>a</span>
  <span m='196880'>symmetrical</span> <span m='197480'>impulse</span> <span
  m='197900'>response.</span> <span m='198530'>In</span> <span
  m='198620'>other</span> <span m='198830'>words,</span> <span
  m='199130'>corresponds</span> <span m='199880'>to</span> <span
  m='200150'>a</span> <span m='200360'>linear</span> <span
  m='200720'>phase</span> <span m='201080'>filter.</span> </p><p><span
  m='202170'>We</span> <span m='202190'>can</span> <span m='202340'>also</span>
  <span m='202640'>look</span> <span m='202880'>at</span> <span
  m='202970'>the</span> <span m='203090'>impulse</span> <span
  m='203480'>response</span> <span m='204320'>before</span> <span m='204800'>the
  de-sampling</span> <span m='205820'>low</span> <span m='206030'>pass</span>
  <span m='206390'>filter.</span> <span m='206820'>Lets</span> <span
  m='207110'>take</span> <span m='207410'>out</span> <span m='207590'>the</span>
  <span m='207680'>de-sampling</span> <span m='208250'>low</span> <span
  m='208400'>pass</span> <span m='208730'>filter</span> <span
  m='209270'>slowly.</span> <span m='210980'>And</span> <span
  m='211790'>what</span> <span m='212360'>we</span> <span
  m='212570'>observe</span> <span m='213230'>is</span> <span
  m='213620'>basically</span> <span m='214250'>the</span> <span
  m='214400'>output</span> <span m='215000'>of</span> <span
  m='215360'>the</span> <span m='215600'>digital</span> <span
  m='215990'>to</span> <span m='216110'>analog</span> <span
  m='216650'>converter.</span> <span m='217490'>Which</span> <span
  m='218300'>of</span> <span m='218420'>course,</span> <span
  m='218750'>is</span> <span m='218870'>a</span> <span
  m='218930'>staircase</span> <span m='219650'>or</span> <span
  m='219820'>boxcar</span> <span m='220340'>function,</span> <span
  m='221120'>not</span> <span m='221390'>an</span> <span
  m='221480'>impulse</span> <span m='221930'>train.</span> </p><p><span
  m='222740'>In</span> <span m='222800'>the</span> <span m='222890'>real</span>
  <span m='223100'>world,</span> <span m='223820'>the</span> <span
  m='224120'>output</span> <span m='224510'>of</span> <span m='224630'>a</span>
  <span m='224660'>D to A</span> <span m='225050'>converter</span> <span
  m='225560'>generally</span> <span m='226130'>is</span> <span
  m='226250'>a</span> <span m='226330'>boxcar</span> <span
  m='227090'>type</span> <span m='227360'>of</span> <span
  m='227420'>function.</span> <span m='228510'>We</span> <span
  m='228710'>can</span> <span m='228890'>put</span> <span m='229280'>the
  de-sampling</span> <span m='230060'>filter</span> <span m='230420'>back</span>
  <span m='230750'>in</span> <span m='230900'>now.</span> <span
  m='231440'>And</span> <span m='232340'>notice</span> <span
  m='232880'>that</span> <span m='233210'>the</span> <span
  m='233360'>effect</span> <span m='233730'>of</span> <span m='233820'>the
  de-sampling</span> <span m='234560'>filter</span> <span m='235070'>is</span>
  <span m='235220'>basically</span> <span m='236420'>to</span> <span
  m='236510'>smooth</span> <span m='237050'>out</span> <span
  m='237650'>the</span> <span m='238130'>rough</span> <span
  m='238490'>edges</span> <span m='239120'>in</span> <span m='239690'>the</span>
  <span m='239900'>boxcar</span> <span m='241130'>output</span> <span
  m='241580'>from</span> <span m='241730'>D to A</span> <span
  m='241820'>converter.</span> </p><p><span m='258640'>Now</span> <span
  m='258860'>what</span> <span m='258940'>we'd</span> <span
  m='259100'>like</span> <span m='259300'>to</span> <span
  m='259390'>illustrate</span> <span m='260079'>is</span> <span
  m='260320'>the</span> <span m='260560'>frequency</span> <span
  m='261130'>response</span> <span m='261910'>of</span> <span
  m='262480'>the</span> <span m='262960'>equivalent</span> <span
  m='263470'>continuous</span> <span m='264040'>time</span> <span
  m='264310'>filter.</span> <span m='265280'>And</span> <span
  m='265420'>we</span> <span m='265540'>can</span> <span m='265690'>do</span>
  <span m='265870'>that</span> <span m='266290'>by</span> <span
  m='266740'>sweeping</span> <span m='267220'>the</span> <span
  m='267310'>filter</span> <span m='267730'>with</span> <span
  m='267870'>a</span> <span m='267910'>sinusoidal</span> <span
  m='268600'>input.</span> <span m='269590'>So</span> <span
  m='270250'>what</span> <span m='270430'>we'll</span> <span
  m='270580'>see</span> <span m='270820'>in</span> <span m='270910'>this</span>
  <span m='271090'>demonstration</span> <span m='272110'>is</span> <span
  m='273070'>on</span> <span m='273250'>the</span> <span m='273340'>upper</span>
  <span m='273580'>trace,</span> <span m='274180'>the</span> <span
  m='274300'>input</span> <span m='274660'>sinusoid,</span> <span
  m='275530'>on</span> <span m='275650'>the</span> <span m='275710'>lower</span>
  <span m='275980'>trace,</span> <span m='276320'>the</span> <span
  m='276460'>output</span> <span m='276850'>sinusoid.</span> <span
  m='278500'>Using</span> <span m='278860'>a</span> <span m='278920'>20</span>
  <span m='279220'>kilohertz</span> <span m='279700'>sampling</span> <span
  m='280240'>rate</span> <span m='280660'>and</span> <span m='280810'>a</span>
  <span m='280870'>sweep</span> <span m='281500'>from</span> <span
  m='281770'>0</span> <span m='282100'>to</span> <span m='282220'>10</span>
  <span m='282490'>kilohertz,</span> <span m='283120'>in</span> <span
  m='283210'>other</span> <span m='283420'>words,</span> <span
  m='283900'>a</span> <span m='283960'>sweep</span> <span m='284350'>from</span>
  <span m='284560'>0</span> <span m='285160'>to</span> <span
  m='285580'>effectively</span> <span m='286240'>pi</span> <span
  m='287320'>in</span> <span m='287440'>terms</span> <span m='287790'>of</span>
  <span m='287900'>the</span> <span m='287950'>digital</span> <span
  m='288310'>filter.</span> </p><p><span m='290150'>So</span> <span
  m='290990'>what</span> <span m='291340'>we'll</span> <span
  m='291670'>observe</span> <span m='292210'>as</span> <span
  m='292510'>the</span> <span m='292630'>input</span> <span
  m='292930'>frequency</span> <span m='293560'>increases</span> <span
  m='294790'>is</span> <span m='295120'>that</span> <span m='295270'>the</span>
  <span m='295420'>output</span> <span m='295780'>sinusoid</span> <span
  m='296620'>will</span> <span m='296800'>have</span> <span
  m='297250'>essentially</span> <span m='297700'>constant</span> <span
  m='298180'>amplitude</span> <span m='299470'>up</span> <span
  m='299680'>to</span> <span m='299800'>the</span> <span
  m='299920'>cutoff</span> <span m='300310'>frequency</span> <span
  m='300790'>of</span> <span m='300880'>the</span> <span
  m='300970'>filter,</span> <span m='301540'>and</span> <span
  m='301690'>then</span> <span m='302380'>approximately</span> <span
  m='303130'>zero</span> <span m='303520'>amplitude</span> <span
  m='304030'>past.</span> <span m='304900'>So</span> <span
  m='305440'>let's</span> <span m='305740'>now</span> <span
  m='306190'>sweep</span> <span m='306550'>the</span> <span
  m='306670'>filter</span> <span m='307180'>frequency</span> <span
  m='307750'>response.</span> <span m='313040'>And</span> <span
  m='315000'>there</span> <span m='315360'>is</span> <span m='315600'>the</span>
  <span m='315870'>filter</span> <span m='316410'>cutoff</span> <span
  m='316770'>frequency.</span> </p><p><span m='322160'>Now</span> <span
  m='322480'>we</span> <span m='322630'>can</span> <span m='322780'>also</span>
  <span m='323410'>observe</span> <span m='324040'>the</span> <span
  m='324220'>filter</span> <span m='324610'>frequency</span> <span
  m='325120'>responds</span> <span m='325660'>in</span> <span
  m='326020'>several</span> <span m='326470'>other</span> <span
  m='326680'>ways.</span> <span m='327650'>One</span> <span
  m='327760'>way</span> <span m='327940'>in</span> <span m='328030'>which</span>
  <span m='328240'>we</span> <span m='328360'>can</span> <span
  m='328540'>observe</span> <span m='328930'>it</span> <span
  m='329110'>is</span> <span m='329380'>by</span> <span
  m='330490'>looking</span> <span m='330910'>also</span> <span
  m='331630'>at</span> <span m='332260'>the</span> <span
  m='332590'>amplitude</span> <span m='333220'>of</span> <span
  m='333310'>the</span> <span m='333460'>output</span> <span
  m='333820'>sinusoid</span> <span m='334630'>as</span> <span
  m='335350'>a</span> <span m='336190'>function</span> <span
  m='336580'>of</span> <span m='336640'>frequency</span> <span
  m='337420'>rather</span> <span m='337780'>than</span> <span
  m='337930'>as</span> <span m='338050'>a</span> <span
  m='338110'>function</span> <span m='338530'>of</span> <span
  m='338650'>time.</span> <span m='339800'>And</span> <span m='340060'>so</span>
  <span m='340270'>we'll</span> <span m='340420'>observe</span> <span
  m='340870'>that</span> <span m='341230'>on</span> <span m='341410'>the</span>
  <span m='341500'>left</span> <span m='341770'>hand</span> <span
  m='342340'>scope.</span> </p><p><span m='343240'>While</span> <span
  m='343480'>on</span> <span m='343600'>the</span> <span m='343690'>right</span>
  <span m='343900'>hand</span> <span m='344170'>scope,</span> <span
  m='344530'>we'll</span> <span m='344680'>have</span> <span
  m='344830'>the</span> <span m='344920'>same</span> <span
  m='345220'>trace</span> <span m='345610'>that</span> <span
  m='346000'>we</span> <span m='346120'>just</span> <span m='346420'>saw,</span>
  <span m='347290'>namely</span> <span m='347680'>two</span> <span
  m='347910'>traces.</span> <span m='348460'>The</span> <span
  m='348580'>upper</span> <span m='348810'>trace</span> <span m='349270'>is
  the</span> <span m='349390'>input</span> <span m='349750'>sinusoid.</span>
  <span m='350860'>The</span> <span m='350950'>lower</span> <span
  m='351220'>trace is</span> <span m='351700'>the</span> <span
  m='351820'>output</span> <span m='352180'>sinusoid.</span> </p><p><span
  m='353530'>And</span> <span m='353890'>in</span> <span
  m='354070'>addition</span> <span m='354490'>to</span> <span
  m='354670'>observing</span> <span m='355540'>the</span> <span
  m='355660'>frequency</span> <span m='356200'>response,</span> <span
  m='357160'>let's</span> <span m='357430'>also</span> <span
  m='357790'>listen</span> <span m='358420'>to</span> <span
  m='358600'>the</span> <span m='358750'>output</span> <span
  m='359110'>sinusoid</span> <span m='360310'>and</span> <span
  m='361360'>observe</span> <span m='361990'>the</span> <span
  m='362110'>attenuation</span> <span m='363040'>in</span> <span
  m='363190'>the</span> <span m='363310'>output</span> <span
  m='363820'>as</span> <span m='364120'>we</span> <span m='364240'>go</span>
  <span m='364450'>from</span> <span m='364630'>the</span> <span
  m='364720'>filter</span> <span m='365020'>passband</span> <span
  m='365650'>to</span> <span m='365740'>the</span> <span
  m='365830'>filter</span> <span m='366160'>stopband.</span> <span
  m='367240'>Again,</span> <span m='367510'>a</span> <span m='367570'>20</span>
  <span m='367870'>kilohertz</span> <span m='368320'>sampling</span> <span
  m='368800'>rate.</span> <span m='369490'>And</span> <span m='369610'>a</span>
  <span m='369670'>sweep</span> <span m='370270'>range</span> <span
  m='370720'>from</span> <span m='370900'>0</span> <span m='371260'>to</span>
  <span m='371410'>10</span> <span m='371650'>kilohertz.</span> </p><p><span
  m='372852'>[HIGH PITCH FREQUENCY]</span> </p><p></p><p><span
  m='380090'>Now</span> <span m='380260'>of</span> <span
  m='380350'>course,</span> <span m='380650'>we're</span> <span
  m='380800'>in</span> <span m='380860'>the</span> <span
  m='380950'>filter</span> <span m='381580'>stopband.</span> </p><p><span
  m='385060'>Now</span> <span m='386080'>if</span> <span m='386590'>we</span>
  <span m='387040'>increase</span> <span m='387640'>the</span> <span
  m='387730'>sweep</span> <span m='388120'>range</span> <span
  m='388870'>from</span> <span m='389770'>10</span> <span
  m='389980'>kilohertz</span> <span m='390550'>to</span> <span
  m='390670'>20</span> <span m='391000'>kilohertz</span> <span
  m='392200'>so</span> <span m='392360'>that</span> <span m='392560'>the</span>
  <span m='392650'>sweep</span> <span m='393010'>range</span> <span
  m='393370'>is</span> <span m='393490'>equal</span> <span m='393790'>to</span>
  <span m='393910'>the</span> <span m='394030'>sampling</span> <span
  m='394540'>frequency,</span> <span m='395740'>in</span> <span
  m='395890'>essence</span> <span m='396370'>that</span> <span
  m='396550'>corresponds</span> <span m='397330'>to</span> <span
  m='397450'>sweeping</span> <span m='397870'>out</span> <span
  m='398020'>the</span> <span m='398080'>digital</span> <span
  m='398470'>filter</span> <span m='399430'>from</span> <span
  m='399940'>0</span> <span m='400450'>to</span> <span m='400600'>2</span> <span
  m='400870'>pi.</span> <span m='401830'>And</span> <span m='401980'>in</span>
  <span m='402070'>that</span> <span m='402250'>case,</span> <span
  m='402610'>we'll</span> <span m='402730'>begin</span> <span
  m='403120'>to</span> <span m='403270'>see</span> <span m='404050'>some</span>
  <span m='404320'>of</span> <span m='404410'>the</span> <span
  m='404500'>periodicity</span> <span m='405520'>in</span> <span
  m='405670'>the</span> <span m='405760'>digital</span> <span
  m='406090'>filter</span> <span m='406450'>frequency</span> <span
  m='406960'>response.</span> <span m='408020'>So</span> <span
  m='408550'>let's</span> <span m='409060'>do</span> <span
  m='409270'>that</span> <span m='409540'>now</span> <span
  m='410080'>with</span> <span m='410260'>a</span> <span m='410320'>20</span>
  <span m='410620'>kilohertz</span> <span m='411100'>sampling</span> <span
  m='411610'>rate</span> <span m='412300'>and</span> <span m='412390'>a</span>
  <span m='412450'>sweep</span> <span m='412840'>range</span> <span
  m='413290'>of</span> <span m='413350'>0</span> <span m='413740'>to</span>
  <span m='413890'>20</span> <span m='414190'>kilohertz.</span> </p><p><span
  m='416338'>[HIGH PITCH FREQUENCY]</span> </p><p><span m='419134'>And</span>
  <span m='419600'>now</span> <span m='419830'>we</span> <span
  m='419950'>come</span> <span m='420340'>near</span> <span m='420550'>2</span>
  <span m='420820'>pi</span> <span m='424220'>we</span> <span
  m='424400'>get</span> <span m='424670'>back</span> <span
  m='425000'>into</span> <span m='425270'>the</span> <span
  m='425360'>passband.</span> <span m='427860'>And</span> <span
  m='428490'>finally</span> <span m='428970'>back</span> <span
  m='429390'>to</span> <span m='429870'>a</span> <span m='430170'>0</span> <span
  m='430530'>to</span> <span m='430650'>10</span> <span
  m='430920'>kilohertz</span> <span m='431460'>sweep,</span> <span
  m='432180'>so</span> <span m='432330'>that</span> <span
  m='432540'>we're</span> <span m='432720'>again</span> <span
  m='432990'>sweeping</span> <span m='433590'>only</span> <span
  m='434040'>from</span> <span m='434370'>0</span> <span m='434760'>to</span>
  <span m='434930'>pi</span> <span m='435960'>with</span> <span
  m='436230'>regard</span> <span m='436620'>to</span> <span
  m='436740'>the</span> <span m='436830'>digital</span> <span
  m='437190'>filter.</span> </p><p><span m='438518'>[HIGH PITCH
  FREQUENCY]</span> </p><p></p><p><span m='449780'>OK,</span> <span
  m='450330'>now</span> <span m='450870'>what</span> <span m='451080'>we</span>
  <span m='451230'>would</span> <span m='451380'>like</span> <span
  m='451650'>to</span> <span m='451920'>demonstrate</span> <span
  m='452670'>is</span> <span m='452880'>the</span> <span
  m='452970'>effect</span> <span m='453330'>of</span> <span
  m='453450'>changing</span> <span m='453930'>the</span> <span
  m='454020'>sampling</span> <span m='454530'>frequency.</span> <span
  m='455950'>And</span> <span m='456540'>we</span> <span m='456690'>know</span>
  <span m='457260'>that</span> <span m='459030'>the</span> <span
  m='459120'>effective</span> <span m='459540'>filter</span> <span
  m='459900'>cutoff</span> <span m='460230'>frequency</span> <span
  m='461100'>is</span> <span m='461280'>tied</span> <span m='461820'>to</span>
  <span m='462300'>the</span> <span m='462870'>sampling</span> <span
  m='463410'>frequency.</span> <span m='464550'>And</span> <span
  m='464670'>for</span> <span m='464820'>this</span> <span
  m='464970'>particular</span> <span m='465510'>filter,</span> <span
  m='466410'>corresponds</span> <span m='467190'>to</span> <span
  m='467340'>a</span> <span m='467430'>tenth</span> <span m='467910'>of</span>
  <span m='468240'>the</span> <span m='468480'>sampling</span> <span
  m='468990'>frequency.</span> </p><p><span m='470100'>Consequently,</span>
  <span m='470880'>if</span> <span m='471000'>we</span> <span
  m='471120'>double</span> <span m='471450'>the</span> <span
  m='471540'>sampling</span> <span m='472050'>frequency,</span> <span
  m='472680'>we</span> <span m='472830'>should</span> <span
  m='473010'>double</span> <span m='473460'>the</span> <span
  m='474240'>effective</span> <span m='474870'>filter</span> <span
  m='475320'>passband</span> <span m='475730'>width</span> <span
  m='476880'>or</span> <span m='477420'>double</span> <span
  m='477870'>the</span> <span m='478050'>filter</span> <span
  m='478410'>cutoff</span> <span m='478830'>frequency.</span> <span
  m='480120'>And</span> <span m='480660'>so</span> <span m='481020'>let's</span>
  <span m='481440'>do</span> <span m='481650'>that</span> <span
  m='481890'>now.</span> <span m='482460'>Again,</span> <span
  m='482770'>a</span> <span m='482870'>0</span> <span m='483220'>to</span> <span
  m='483400'>10</span> <span m='483590'>kilohertz</span> <span
  m='483990'>sweep</span> <span m='484380'>range,</span> <span
  m='485250'>but</span> <span m='485550'>a</span> <span m='485790'>40</span>
  <span m='486450'>kilohertz</span> <span m='486960'>sampling</span> <span
  m='487470'>frequency.</span> </p><p><span m='489870'>[HIGH PITCH
  FREQUENCY]</span> </p><p></p><p><span m='492630'>And</span> <span
  m='493100'>we</span> <span m='493220'>should</span> <span
  m='493430'>observe</span> <span m='493910'>that</span> <span
  m='494060'>the</span> <span m='494350'>filter</span> <span
  m='494750'>cutoff</span> <span m='495170'>frequency</span> <span
  m='495800'>has</span> <span m='495950'>now</span> <span
  m='496160'>doubled</span> <span m='496970'>to</span> <span m='497150'>4</span>
  <span m='497570'>kilohertz.</span> </p><p><span m='500940'>Now</span> <span
  m='501470'>let's</span> <span m='501920'>begin</span> <span
  m='502280'>to</span> <span m='502400'>decrease</span> <span
  m='502910'>the</span> <span m='503030'>filter</span> <span
  m='503360'>sampling</span> <span m='503870'>frequency.</span> <span
  m='505380'>So</span> <span m='505520'>from</span> <span m='505700'>40,</span>
  <span m='506090'>let's</span> <span m='506360'>change</span> <span
  m='506780'>the</span> <span m='507050'>sampling</span> <span
  m='507500'>frequency</span> <span m='508010'>to</span> <span
  m='508130'>20</span> <span m='508430'>kilohertz.</span> <span
  m='510240'>We</span> <span m='510290'>should</span> <span
  m='510500'>see</span> <span m='510740'>the</span> <span
  m='510980'>cutoff</span> <span m='511370'>frequency</span> <span
  m='512090'>cut</span> <span m='512330'>in</span> <span m='512450'>half.</span>
  </p><p><span m='514929'>[HIGH PITCH FREQUENCY]</span> </p><p></p><p><span
  m='523429'>Now</span> <span m='523539'>we</span> <span m='523659'>can</span>
  <span m='523809'>go</span> <span m='524320'>even</span> <span
  m='524620'>further.</span> <span m='525070'>We</span> <span
  m='525250'>can</span> <span m='525430'>cut</span> <span m='525640'>the</span>
  <span m='525730'>sampling</span> <span m='526180'>frequency</span> <span
  m='526720'>down</span> <span m='526960'>to</span> <span m='527050'>10</span>
  <span m='527410'>kilohertz.</span> <span m='528010'>And</span> <span
  m='528130'>remember</span> <span m='528520'>that</span> <span
  m='528760'>the</span> <span m='529030'>sweep</span> <span
  m='529420'>range</span> <span m='529780'>is</span> <span
  m='529850'>zero</span> <span m='530180'>to</span> <span m='530300'>10</span>
  <span m='530620'>kilohertz.</span> <span m='531150'>So</span> <span
  m='531280'>now</span> <span m='531490'>we'll</span> <span m='531640'>be</span>
  <span m='531790'>sweeping</span> <span m='532270'>from</span> <span
  m='532450'>0</span> <span m='532840'>to</span> <span m='532960'>2</span> <span
  m='533170'>pi.</span> </p><p><span m='534660'>[HIGH PITCH FREQUENCY]</span>
  </p><p></p><p><span m='541310'>So</span> <span m='541420'>as</span> <span
  m='541540'>we</span> <span m='541630'>get</span> <span m='541780'>close</span>
  <span m='542290'>to</span> <span m='542530'>2</span> <span
  m='542770'>pi</span> <span m='543100'>we'll</span> <span m='543250'>see</span>
  <span m='543430'>the</span> <span m='543550'>passband</span> <span
  m='544150'>again.</span> </p><p><span m='546650'>And</span> <span
  m='547550'>now</span> <span m='548030'>let's</span> <span
  m='548330'>cut</span> <span m='548600'>down</span> <span m='548810'>the</span>
  <span m='548900'>sampling</span> <span m='549320'>frequency</span> <span
  m='550100'>even</span> <span m='550430'>further</span> <span
  m='551330'>to</span> <span m='551570'>5</span> <span
  m='551900'>kilohertz.</span> </p><p><span m='554147'>[SHORT HIGH PITCH
  FREQUENCY]</span> </p><p></p><p><span m='558370'>Here</span> <span
  m='558520'>we</span> <span m='558670'>are</span> <span m='558860'>at</span>
  <span m='558970'>2</span> <span m='559180'>pi.</span> </p><p><span
  m='560210'>[HIGH PITCH FREQUENCY]</span> </p><p><span m='562410'>And</span>
  <span m='562620'>then</span> <span m='563220'>at</span> <span
  m='563520'>4</span> <span m='563900'>pi.</span> </p><p><span
  m='566780'>All</span> <span m='566840'>right,</span> <span
  m='567090'>so</span> <span m='567680'>that</span> <span
  m='568280'>illustrates</span> <span m='568910'>the</span> <span
  m='569030'>effect</span> <span m='569390'>of</span> <span
  m='569480'>changing</span> <span m='569960'>the</span> <span
  m='570050'>sampling</span> <span m='570530'>frequency.</span> <span
  m='571970'>Now</span> <span m='572420'>let's</span> <span
  m='573020'>conclude</span> <span m='573440'>this</span> <span
  m='573620'>demonstration</span> <span m='574460'>of</span> <span
  m='574550'>the</span> <span m='574640'>effect</span> <span
  m='575120'>of</span> <span m='575300'>the</span> <span
  m='575390'>sampling</span> <span m='575840'>frequency</span> <span
  m='576350'>on</span> <span m='576440'>the</span> <span
  m='576530'>filter</span> <span m='576860'>cutoff</span> <span
  m='577280'>frequency</span> <span m='578420'>by</span> <span
  m='578570'>carrying</span> <span m='578990'>out</span> <span
  m='579140'>some</span> <span m='579320'>filtering</span> <span
  m='580010'>on</span> <span m='580280'>some</span> <span m='580490'>live</span>
  <span m='580820'>audio.</span> </p><p><span m='582200'>What</span> <span
  m='582500'>we'll</span> <span m='583160'>watch,</span> <span
  m='583610'>in</span> <span m='583700'>this</span> <span
  m='583880'>case,</span> <span m='584510'>is</span> <span m='585140'>the</span>
  <span m='585590'>output</span> <span m='586460'>audio</span> <span
  m='587250'>waveform</span> <span m='588530'>as</span> <span
  m='588740'>a</span> <span m='588800'>function</span> <span
  m='589220'>of</span> <span m='589340'>time</span> <span m='590030'>on</span>
  <span m='590540'>the</span> <span m='590750'>single</span> <span
  m='591140'>trace</span> <span m='591450'>scope.</span> <span
  m='592370'>And</span> <span m='592580'>also,</span> <span
  m='593300'>we'll</span> <span m='593900'>listen</span> <span
  m='594260'>to</span> <span m='594380'>the</span> <span
  m='594530'>output.</span> <span m='595610'>We'll</span> <span
  m='595790'>begin</span> <span m='596150'>it</span> <span
  m='596270'>with</span> <span m='596450'>a</span> <span m='596510'>40</span>
  <span m='596810'>kilohertz</span> <span m='597530'>sampling</span> <span
  m='598070'>rate,</span> <span m='598850'>then</span> <span
  m='599240'>reduce</span> <span m='599630'>that</span> <span
  m='599870'>to</span> <span m='599990'>20</span> <span
  m='600320'>kilohertz,</span> <span m='600940'>10</span> <span
  m='601220'>kilohertz,</span> <span m='601790'>and</span> <span
  m='601880'>then</span> <span m='602030'>5</span> <span
  m='602360'>kilohertz.</span> <span m='603500'>And</span> <span
  m='603710'>in</span> <span m='603800'>each</span> <span m='604010'>of</span>
  <span m='604070'>those</span> <span m='604310'>cases,</span> <span
  m='605030'>the</span> <span m='605180'>effective</span> <span
  m='605630'>filter</span> <span m='605990'>cutoff</span> <span
  m='606380'>frequency</span> <span m='607520'>then</span> <span
  m='607820'>is</span> <span m='607970'>cut</span> <span m='608180'>in</span>
  <span m='608300'>half</span> <span m='608980'>from</span> <span
  m='609150'>4</span> <span m='609450'>kilohertz</span> <span
  m='610170'>to</span> <span m='610460'>2</span> <span
  m='610710'>kilohertz</span> <span m='611480'>to</span> <span
  m='611660'>1</span> <span m='611970'>kilohertz</span> <span
  m='612650'>and</span> <span m='612800'>then</span> <span m='612950'>to</span>
  <span m='613070'>500</span> <span m='613610'>cycles.</span> </p><p><span
  m='614580'>So</span> <span m='614660'>let's</span> <span
  m='614900'>begin</span> <span m='615290'>with</span> <span m='615410'>a</span>
  <span m='615470'>40</span> <span m='615800'>kilohertz</span> <span
  m='616280'>sampling</span> <span m='616730'>frequency,</span> <span
  m='617480'>or</span> <span m='617660'>an</span> <span
  m='617720'>effective</span> <span m='618140'>filter</span> <span
  m='618770'>cutoff</span> <span m='619160'>frequency</span> <span
  m='619910'>of</span> <span m='620000'>4</span> <span
  m='620330'>kilohertz.</span> </p><p><span m='622559'>[MUSIC - SCOTT JOPLIN,
  "MAPLE LEAF RAG"]</span> </p><p><span m='627390'>Now</span> <span
  m='627920'>let's</span> <span m='628160'>reduce</span> <span
  m='628520'>that</span> <span m='628790'>to</span> <span m='629030'>20</span>
  <span m='629360'>kilohertz</span> <span m='629625'>sampling</span> <span
  m='630350'>frequency</span> <span m='631130'>or</span> <span m='631340'>a
  2</span> <span m='631580'>kilohertz</span> <span m='632150'>filter.</span>
  <span m='638080'>Then</span> <span m='638260'>a</span> <span
  m='638330'>10</span> <span m='638630'>kilohertz</span> <span
  m='639140'>sampling</span> <span m='639620'>frequency.</span> <span
  m='645740'>And</span> <span m='645920'>finally,</span> <span
  m='646410'>a</span> <span m='646520'>5</span> <span
  m='646850'>kilohertz</span> <span m='647330'>sampling</span> <span
  m='647840'>frequency</span> <span m='648410'>corresponding</span> <span
  m='649250'>to</span> <span m='649730'>a</span> <span m='650300'>500</span>
  <span m='650900'>cycle</span> <span m='651390'>equivalent</span> <span
  m='652250'>analog</span> <span m='652800'>filter.</span> </p><p><span
  m='658220'>All</span> <span m='658280'>right,</span> <span
  m='658490'>now</span> <span m='658930'>let's</span> <span
  m='659140'>finally</span> <span m='659500'>conclude</span> <span
  m='660040'>by</span> <span m='660700'>returning</span> <span
  m='661240'>to</span> <span m='662080'>a</span> <span m='662140'>little</span>
  <span m='662380'>higher</span> <span m='662680'>quality</span> <span
  m='663230'>ragtime</span> <span m='663850'>by</span> <span
  m='664190'>changing</span> <span m='664550'>the</span> <span
  m='664660'>sampling</span> <span m='665120'>frequency</span> <span
  m='665610'>back</span> <span m='666370'>to</span> <span m='666670'>40
  kilohertz.</span> </p>
embedded_media:
  - uid: 65ccff455f402caaebb4ee8e66f09d9b
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: OQNR099y8mM
  - uid: 565dfa42e5621e1579949e83fe128ea6
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_demo2_300k.mp4'
  - uid: bb65156a0340b03253b16a56427b0b43
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/demonstration-2-sampling-aliasing/id481803782?i=108361995
  - uid: 4b08637bf6b62561a19138a99af24e1b
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/OQNR099y8mM/default.jpg'
  - uid: f18a72fec15df267d2b1a52d64b58c67
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: OQNR099y8mM
  - uid: 8ab109bf3ec91f8f5228ec6d1e3b1f9d
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: OQNR099y8mM.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-2-sampling-aliasing-and-frequency-response-part-2/OQNR099y8mM.srt
  - uid: 5a4b4f372953908ddede0af604b0fbbe
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: OQNR099y8mM.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/demonstration-2-sampling-aliasing-and-frequency-response-part-2/OQNR099y8mM.pdf
  - uid: 94ec5b0d3f100a330d51fb3649d057ab
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 9b29ff685e98ce46d790a95105457e85
    parent_uid: fccc67d08ddad9de3e4b638b220338b6
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
