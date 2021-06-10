---
order_index: null
title: 'Lecture 17: Design of FIR Digital Filters'
template_type: Tabbed
uid: 968adeab1291c57fe0e67ac385b514d9
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-17-design-of-fir-digital-filters
short_url: lecture-17-design-of-fir-digital-filters
inline_embed_id: '92661256lecture17:designoffirdigitalfilters60555058'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Design of FIR filters using windows,
  comparison of rectangular, Bartlett, and Hamming windows, frequency sampling
  method of filter design, optimum equi-ripple FIR filters.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Design of FIR Digital Filters (<img src="/images/inacessible.gif" alt="This
  resource may not render correctly in a screen reader." /><a
  href="./resolveuid/7be1f7fe5548602705110ab04ca05d83">PDF</a>)</p>
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
  m='56010'>ALAN V. OPPENHEIM:</span> <span m='56145'>During</span> <span
  m='56280'>the</span> <span m='56730'>last</span> <span m='57060'>three</span>
  <span m='57270'>lectures,</span> <span m='57880'>we</span> <span
  m='57930'>considered</span> <span m='58470'>the</span> <span
  m='58740'>design</span> <span m='59460'>of</span> <span
  m='59790'>infinite</span> <span m='60210'>impulse</span> <span
  m='60660'>response</span> <span m='61230'>digital</span> <span
  m='61590'>filters.</span> <span m='63150'>The</span> <span
  m='63240'>two</span> <span m='63870'>main</span> <span
  m='64230'>classes</span> <span m='64980'>of</span> <span
  m='65129'>design</span> <span m='65550'>procedures</span> <span
  m='66330'>that</span> <span m='66420'>we</span> <span
  m='66570'>discussed</span> <span m='67860'>involved</span> <span
  m='68760'>mapping</span> <span m='69180'>continuous</span> <span
  m='69780'>time</span> <span m='70080'>designs</span> <span m='70620'>to</span>
  <span m='70770'>discrete</span> <span m='71190'>time</span> <span
  m='71460'>designs.</span> <span m='72240'>That</span> <span
  m='72420'>was</span> <span m='72540'>the</span> <span m='72660'>first</span>
  <span m='72930'>class.</span> <span m='73920'>And</span> <span
  m='74100'>the</span> <span m='74190'>second</span> <span
  m='74550'>class</span> <span m='74970'>was</span> <span m='75150'>the</span>
  <span m='75240'>use</span> <span m='75600'>of</span> <span
  m='75720'>algorithmic</span> <span m='76350'>design</span> <span
  m='76740'>procedures.</span> <span m='78760'>In</span> <span
  m='79050'>this</span> <span m='79260'>lecture,</span> <span m='79960'>I</span>
  <span m='80040'>would</span> <span m='80190'>like</span> <span
  m='80460'>to</span> <span m='80910'>discuss</span> <span m='81600'>the</span>
  <span m='81810'>design</span> <span m='82230'>of</span> <span
  m='82290'>finite</span> <span m='82830'>impulse</span> <span
  m='83310'>response</span> <span m='84060'>digital</span> <span
  m='84420'>filters.</span> </p><p><span m='85890'>And</span> <span
  m='86610'>I</span> <span m='86730'>remind</span> <span m='87240'>you</span>
  <span m='87750'>that</span> <span m='88380'>as</span> <span
  m='88950'>we've</span> <span m='89310'>stressed</span> <span
  m='89760'>in</span> <span m='89850'>a</span> <span m='89910'>number</span>
  <span m='90240'>of</span> <span m='90330'>the</span> <span
  m='90420'>lectures,</span> <span m='91590'>one</span> <span
  m='92010'>of</span> <span m='92190'>the</span> <span m='92490'>very</span>
  <span m='92820'>important</span> <span m='93270'>aspects</span> <span
  m='93840'>of</span> <span m='93900'>finite</span> <span
  m='94290'>impulse</span> <span m='94710'>response</span> <span
  m='95190'>digital</span> <span m='95550'>filters</span> <span
  m='96570'>is</span> <span m='96720'>the</span> <span m='96840'>fact</span>
  <span m='97560'>that</span> <span m='98070'>they</span> <span
  m='98250'>can</span> <span m='98430'>be</span> <span
  m='98580'>implemented</span> <span m='99450'>to</span> <span
  m='99600'>have</span> <span m='99900'>exactly</span> <span
  m='100410'>linear</span> <span m='100770'>phase.</span> <span
  m='102090'>So</span> <span m='102810'>finite</span> <span
  m='103230'>impulse</span> <span m='103650'>response</span> <span
  m='104160'>filters,</span> <span m='104730'>as</span> <span
  m='104880'>opposed</span> <span m='105210'>to</span> <span
  m='105300'>infinite</span> <span m='105840'>impulse</span> <span
  m='106290'>response</span> <span m='106770'>filters,</span> <span
  m='107790'>are</span> <span m='108450'>useful</span> <span
  m='109320'>for</span> <span m='109650'>problems</span> <span
  m='110550'>where</span> <span m='110760'>linear</span> <span
  m='111120'>phase</span> <span m='111570'>is</span> <span m='111720'>an</span>
  <span m='111810'>important</span> <span m='112230'>constraint.</span>
  </p><p><span m='114120'>It</span> <span m='114210'>turns</span> <span
  m='114540'>out</span> <span m='114750'>also--</span> <span
  m='115330'>and</span> <span m='115430'>this</span> <span
  m='115710'>isn't</span> <span m='115990'>a</span> <span
  m='116070'>point</span> <span m='116400'>that</span> <span
  m='116490'>we'll</span> <span m='116640'>be</span> <span
  m='116760'>touching</span> <span m='117180'>on</span> <span
  m='117360'>in</span> <span m='117450'>these</span> <span
  m='117630'>lectures--</span> <span m='118590'>but</span> <span
  m='118740'>it</span> <span m='118830'>turns</span> <span m='119160'>out</span>
  <span m='119370'>also</span> <span m='120150'>that</span> <span
  m='120810'>finite</span> <span m='121230'>impulse</span> <span
  m='121650'>response</span> <span m='122130'>digital</span> <span
  m='122490'>filters</span> <span m='123510'>have</span> <span
  m='123990'>some</span> <span m='124380'>important</span> <span
  m='124890'>advantages</span> <span m='125730'>over</span> <span
  m='125970'>infinite</span> <span m='126360'>impulse</span> <span
  m='126750'>response</span> <span m='127260'>filters</span> <span
  m='128130'>with</span> <span m='128310'>regard</span> <span
  m='128669'>to</span> <span m='128789'>round</span> <span m='129089'>off</span>
  <span m='129389'>noise,</span> <span m='129840'>that</span> <span
  m='129990'>is,</span> <span m='130500'>with</span> <span
  m='130650'>regard</span> <span m='131100'>to</span> <span
  m='131250'>the</span> <span m='131340'>effects</span> <span
  m='131820'>of</span> <span m='131940'>finite</span> <span
  m='132300'>register</span> <span m='132810'>length.</span> </p><p><span
  m='135470'>Now</span> <span m='135960'>in</span> <span
  m='136140'>general,</span> <span m='136980'>the</span> <span
  m='137100'>implementation</span> <span m='138150'>of</span> <span
  m='138360'>finite</span> <span m='138810'>impulse</span> <span
  m='139230'>response</span> <span m='140220'>filters</span> <span
  m='141120'>is</span> <span m='141450'>considerably</span> <span
  m='142140'>simpler</span> <span m='143250'>for</span> <span
  m='143580'>discrete</span> <span m='144000'>time</span> <span
  m='144330'>systems</span> <span m='145230'>than</span> <span
  m='145410'>it</span> <span m='145530'>is</span> <span m='145860'>for</span>
  <span m='146040'>continuous</span> <span m='146640'>time</span> <span
  m='146970'>systems.</span> <span m='149070'>Consequently,</span> <span
  m='149910'>it</span> <span m='149970'>turns</span> <span m='150360'>out</span>
  <span m='150810'>that</span> <span m='151260'>there</span> <span
  m='151620'>are</span> <span m='151770'>not</span> <span
  m='152190'>really</span> <span m='152550'>available,</span> <span
  m='153840'>or</span> <span m='154010'>a</span> <span m='154230'>wide</span>
  <span m='154530'>variety</span> <span m='155250'>of</span> <span
  m='155400'>continuous</span> <span m='156030'>time</span> <span
  m='156510'>design</span> <span m='156960'>procedures</span> <span
  m='157770'>for</span> <span m='157950'>finite</span> <span
  m='158370'>impulse</span> <span m='158760'>response</span> <span
  m='159270'>filters</span> <span m='160140'>as</span> <span
  m='160380'>there</span> <span m='160560'>were</span> <span
  m='160890'>for</span> <span m='161250'>infinite</span> <span
  m='161670'>impulse</span> <span m='162090'>response.</span> </p><p><span
  m='163350'>And</span> <span m='163440'>consequently,</span> <span
  m='164940'>the</span> <span m='165480'>continuous</span> <span
  m='166170'>time</span> <span m='166610'>to</span> <span
  m='166740'>discrete</span> <span m='167190'>time</span> <span
  m='167820'>mapping,</span> <span m='168540'>as</span> <span
  m='168780'>a</span> <span m='168840'>design</span> <span
  m='169290'>procedure,</span> <span m='171060'>is</span> <span
  m='171450'>not</span> <span m='171750'>particularly</span> <span
  m='172410'>applicable</span> <span m='173340'>to</span> <span
  m='173460'>the</span> <span m='173580'>design</span> <span
  m='174240'>of</span> <span m='174450'>finite</span> <span
  m='174900'>impulse</span> <span m='175290'>response</span> <span
  m='175810'>digital</span> <span m='176160'>filters.</span> <span
  m='177060'>So</span> <span m='177600'>this</span> <span
  m='177810'>includes,</span> <span m='178450'>for</span> <span
  m='178560'>example,</span> <span m='180190'>the</span> <span
  m='180690'>impulse</span> <span m='181130'>and</span> <span
  m='181270'>variant</span> <span m='181890'>technique,</span> <span
  m='182910'>and</span> <span m='183210'>the</span> <span m='183300'>use</span>
  <span m='183570'>of</span> <span m='183660'>the</span> <span
  m='183750'>bilinear</span> <span m='184260'>transformation.</span> <span
  m='185580'>That</span> <span m='185790'>is,</span> <span
  m='186390'>those</span> <span m='186660'>techniques</span> <span
  m='187440'>are</span> <span m='187590'>not</span> <span
  m='187800'>particularly</span> <span m='188430'>useful</span> <span
  m='189390'>when</span> <span m='190050'>we</span> <span m='190350'>are</span>
  <span m='190560'>talking</span> <span m='191010'>about</span> <span
  m='191370'>the</span> <span m='191460'>design</span> <span
  m='192120'>of</span> <span m='192360'>finite</span> <span
  m='192810'>impulse</span> <span m='193230'>response</span> <span
  m='193950'>filters.</span> </p><p><span m='195480'>As</span> <span
  m='195630'>an</span> <span m='195690'>additional</span> <span
  m='196560'>interesting</span> <span m='197070'>side</span> <span
  m='197440'>point,</span> <span m='198810'>if</span> <span m='199230'>we</span>
  <span m='199740'>were</span> <span m='199980'>to</span> <span
  m='200130'>begin</span> <span m='200880'>with</span> <span m='201300'>a</span>
  <span m='201510'>finite</span> <span m='202110'>impulse</span> <span
  m='202620'>response</span> <span m='204030'>analog</span> <span
  m='204660'>or</span> <span m='204780'>continuous</span> <span
  m='205380'>time</span> <span m='205710'>filter,</span> <span
  m='206640'>and</span> <span m='206790'>map</span> <span m='207070'>it</span>
  <span m='207180'>to</span> <span m='207360'>a</span> <span
  m='207420'>digital</span> <span m='207810'>filter</span> <span
  m='208380'>using</span> <span m='208740'>the</span> <span
  m='208830'>bilinear</span> <span m='209340'>transformation,</span> <span
  m='210750'>then</span> <span m='210870'>in</span> <span m='210960'>fact</span>
  <span m='211290'>the</span> <span m='211380'>resulting</span> <span
  m='211890'>filter</span> <span m='212580'>would</span> <span
  m='213540'>not</span> <span m='213840'>be</span> <span m='214230'>a</span>
  <span m='214380'>finite</span> <span m='214800'>impulse</span> <span
  m='215190'>response</span> <span m='215700'>filter.</span> <span
  m='217560'>The</span> <span m='217710'>algorithmic</span> <span
  m='218310'>procedures</span> <span m='219150'>that</span> <span
  m='219360'>we</span> <span m='219480'>talked</span> <span
  m='219810'>about</span> <span m='220710'>in</span> <span m='221280'>the</span>
  <span m='221400'>previous</span> <span m='221850'>lectures,</span> <span
  m='222390'>of</span> <span m='222510'>course,</span> <span
  m='222840'>still</span> <span m='223110'>do</span> <span
  m='223320'>apply</span> <span m='224400'>to</span> <span m='224790'>the</span>
  <span m='224910'>design</span> <span m='225360'>of</span> <span
  m='225420'>finite</span> <span m='225810'>impulse</span> <span
  m='226230'>response</span> <span m='226860'>filters.</span> <span
  m='227850'>And</span> <span m='228150'>there</span> <span
  m='228360'>also</span> <span m='228750'>are</span> <span
  m='228840'>some</span> <span m='229050'>other</span> <span
  m='229380'>algorithmic</span> <span m='230010'>procedures</span> <span
  m='231150'>that</span> <span m='231390'>are</span> <span
  m='231510'>discussed</span> <span m='231990'>in</span> <span
  m='232080'>the</span> <span m='232170'>text,</span> <span
  m='232620'>and</span> <span m='232740'>that</span> <span m='232980'>I</span>
  <span m='233160'>will</span> <span m='233820'>touch</span> <span
  m='234150'>on</span> <span m='234360'>just</span> <span m='234600'>very</span>
  <span m='234870'>briefly</span> <span m='235530'>in</span> <span
  m='235680'>today's</span> <span m='236040'>lecture.</span> </p><p><span
  m='238800'>Now</span> <span m='239400'>for</span> <span m='240240'>the</span>
  <span m='240540'>design</span> <span m='241290'>of</span> <span
  m='241740'>finite</span> <span m='242250'>impulse</span> <span
  m='242670'>response</span> <span m='243930'>filters,</span> <span
  m='245460'>there</span> <span m='246210'>are</span> <span
  m='246870'>basically</span> <span m='248160'>three</span> <span
  m='248490'>classes,</span> <span m='249600'>or</span> <span
  m='250020'>three</span> <span m='250350'>types</span> <span
  m='251070'>of</span> <span m='251820'>design</span> <span
  m='252450'>techniques</span> <span m='253140'>that</span> <span
  m='253290'>we'll</span> <span m='253470'>be</span> <span
  m='253590'>discussing.</span> <span m='255810'>And</span> <span
  m='256410'>in</span> <span m='256589'>this</span> <span
  m='256800'>lecture,</span> <span m='257529'>what</span> <span
  m='257670'>I</span> <span m='257790'>intend</span> <span m='258149'>to</span>
  <span m='258269'>do</span> <span m='258750'>is</span> <span
  m='259140'>present</span> <span m='259980'>the</span> <span
  m='260100'>three</span> <span m='260399'>of</span> <span
  m='260519'>these,</span> <span m='261390'>primarily</span> <span
  m='262380'>with</span> <span m='262590'>an</span> <span m='262710'>eye</span>
  <span m='263040'>toward</span> <span m='263520'>giving</span> <span
  m='263820'>you</span> <span m='263970'>an</span> <span
  m='264060'>appreciation</span> <span m='265050'>for</span> <span
  m='266040'>what</span> <span m='266550'>the</span> <span
  m='266730'>style</span> <span m='267420'>of</span> <span m='267600'>the</span>
  <span m='267690'>design</span> <span m='268110'>techniques</span> <span
  m='268830'>is.</span> <span m='269550'>That</span> <span m='269700'>is,</span>
  <span m='269880'>to</span> <span m='270000'>give</span> <span
  m='270180'>you</span> <span m='270330'>an</span> <span
  m='270450'>overview</span> <span m='271260'>of</span> <span
  m='271380'>these</span> <span m='271920'>design</span> <span
  m='272340'>techniques.</span> <span m='273520'>But</span> <span
  m='273810'>I</span> <span m='273960'>won't</span> <span
  m='274410'>dwell</span> <span m='274950'>on</span> <span
  m='275550'>many</span> <span m='275850'>of</span> <span m='275970'>the</span>
  <span m='276060'>details.</span> </p><p><span m='278470'>So</span> <span
  m='278910'>in</span> <span m='279480'>the</span> <span
  m='279750'>design</span> <span m='280590'>of</span> <span
  m='280770'>finite</span> <span m='281220'>impulse</span> <span
  m='281640'>response</span> <span m='282540'>digital</span> <span
  m='282900'>filters,</span> <span m='283540'>then,</span> <span
  m='285150'>we</span> <span m='285480'>of</span> <span m='285630'>course</span>
  <span m='286110'>are</span> <span m='286230'>talking</span> <span
  m='286950'>about</span> <span m='287550'>a</span> <span m='287580'>unit</span>
  <span m='287910'>sample</span> <span m='288360'>response</span> <span
  m='289350'>that</span> <span m='289740'>is</span> <span m='289920'>a</span>
  <span m='290010'>finite</span> <span m='290520'>length.</span> <span
  m='291570'>And</span> <span m='292230'>we'll</span> <span
  m='292800'>choose</span> <span m='293160'>the</span> <span
  m='293280'>length,</span> <span m='294060'>the</span> <span
  m='294210'>interval</span> <span m='294780'>over</span> <span
  m='295080'>which</span> <span m='295770'>the</span> <span
  m='295890'>unit</span> <span m='296130'>sample</span> <span
  m='296520'>response</span> <span m='297120'>is</span> <span
  m='297270'>non-zero</span> <span m='298890'>to</span> <span
  m='299010'>be</span> <span m='299460'>in</span> <span m='299610'>the</span>
  <span m='299700'>range</span> <span m='300180'>from</span> <span
  m='300390'>0</span> <span m='301170'>to</span> <span m='301290'>capital</span>
  <span m='301800'>N</span> <span m='301950'>minus</span> <span
  m='302340'>1.</span> <span m='303550'>So</span> <span m='304320'>the</span>
  <span m='304440'>Z-transform</span> <span m='305610'>of</span> <span
  m='306120'>the</span> <span m='306360'>finite</span> <span
  m='306750'>impulse</span> <span m='307170'>response</span> <span
  m='307680'>filter</span> <span m='308610'>is</span> <span
  m='308790'>then</span> <span m='309120'>given</span> <span
  m='309420'>by</span> <span m='309630'>the</span> <span m='309750'>sum</span>
  <span m='310140'>from</span> <span m='310320'>0</span> <span
  m='311100'>to</span> <span m='311220'>capital</span> <span m='311700'>N</span>
  <span m='311820'>minus</span> <span m='312240'>1</span> <span
  m='312525'>of</span> <span m='312810'>h</span> <span m='313070'>of</span>
  <span m='313200'>n,</span> <span m='313860'>z</span> <span
  m='314190'>to</span> <span m='314340'>the</span> <span m='314430'>minus</span>
  <span m='314850'>n,</span> <span m='315880'>which</span> <span
  m='315990'>of</span> <span m='316110'>course</span> <span m='316430'>is</span>
  <span m='316530'>a</span> <span m='316590'>polynomial</span> <span
  m='317520'>in</span> <span m='317670'>z</span> <span m='317880'>to</span>
  <span m='318030'>the</span> <span m='318120'>minus</span> <span
  m='318600'>1.</span> </p><p><span m='319390'>And</span> <span
  m='319440'>we</span> <span m='319560'>know</span> <span
  m='320010'>that,</span> <span m='320580'>for</span> <span
  m='320730'>this</span> <span m='320910'>class</span> <span
  m='321300'>of</span> <span m='321390'>systems,</span> <span
  m='322350'>h</span> <span m='322630'>of</span> <span m='322830'>z</span> <span
  m='323250'>has</span> <span m='323520'>only</span> <span
  m='323820'>zeros,</span> <span m='324990'>except</span> <span
  m='325740'>at</span> <span m='326220'>z equal</span> <span
  m='326710'>0.</span> <span m='327240'>That</span> <span m='327420'>is,</span>
  <span m='327840'>the</span> <span m='327960'>poles</span> <span
  m='328440'>of</span> <span m='328560'>h</span> <span m='328770'>of</span>
  <span m='328860'>z</span> <span m='329160'>can</span> <span
  m='329280'>only</span> <span m='329550'>fall</span> <span m='330090'>at</span>
  <span m='330630'>z</span> <span m='330780'>equals</span> <span
  m='331110'>0,</span> <span m='331620'>or z</span> <span
  m='331860'>equals</span> <span m='332250'>infinity.</span> <span
  m='333930'>And</span> <span m='334080'>I</span> <span m='334200'>remind</span>
  <span m='334620'>you</span> <span m='334770'>also</span> <span
  m='335400'>that</span> <span m='336180'>for</span> <span
  m='336510'>linear</span> <span m='336900'>phase</span> <span
  m='338640'>finite</span> <span m='339030'>impulse</span> <span
  m='339420'>response</span> <span m='339960'>filters,</span> <span
  m='341040'>the</span> <span m='341250'>constraint</span> <span
  m='341850'>on</span> <span m='341970'>the</span> <span m='342060'>unit</span>
  <span m='342360'>sample</span> <span m='342780'>response</span> <span
  m='343950'>is</span> <span m='344160'>that</span> <span m='344580'>it</span>
  <span m='345240'>basically</span> <span m='345990'>is</span> <span
  m='346110'>symmetrical</span> <span m='347010'>about</span> <span
  m='347370'>its</span> <span m='347520'>midpoint.</span> <span
  m='348570'>In</span> <span m='348690'>other</span> <span
  m='348900'>words,</span> <span m='349450'>as</span> <span m='349560'>we</span>
  <span m='349650'>look</span> <span m='349860'>at</span> <span
  m='349950'>the</span> <span m='350040'>unit</span> <span
  m='350310'>sample</span> <span m='350730'>response</span> <span
  m='351720'>starting</span> <span m='352170'>from</span> <span
  m='352350'>the</span> <span m='352440'>left</span> <span
  m='352710'>hand</span> <span m='353000'>end</span> <span m='353740'>and</span>
  <span m='353880'>starting</span> <span m='354300'>from</span> <span
  m='354450'>the</span> <span m='354540'>right</span> <span
  m='354780'>hand</span> <span m='355080'>end,</span> <span
  m='355760'>approaching</span> <span m='356390'>toward</span> <span
  m='357140'>the</span> <span m='357230'>middle,</span> <span
  m='358010'>then</span> <span m='358340'>we</span> <span m='358520'>see</span>
  <span m='358730'>the</span> <span m='358850'>same</span> <span
  m='359510'>values.</span> <span m='360420'>In</span> <span
  m='360440'>other</span> <span m='360650'>words,</span> <span
  m='361080'>there's</span> <span m='361160'>a</span> <span
  m='361220'>symmetry</span> <span m='362210'>that's</span> <span
  m='362390'>required</span> <span m='363080'>for</span> <span
  m='363230'>linear</span> <span m='363560'>phase.</span> </p><p><span
  m='366290'>The</span> <span m='367370'>three</span> <span
  m='367670'>basic</span> <span m='368120'>design</span> <span
  m='369230'>procedures</span> <span m='370340'>that</span> <span
  m='370670'>I'd</span> <span m='370820'>like</span> <span m='371030'>to</span>
  <span m='371120'>talk</span> <span m='371450'>about</span> <span
  m='371900'>in</span> <span m='372020'>this</span> <span
  m='372230'>lecture,</span> <span m='372650'>basically</span> <span
  m='373190'>introduce</span> <span m='373660'>in</span> <span
  m='373790'>the</span> <span m='373880'>lecture,</span> <span
  m='375110'>are</span> <span m='375660'>first</span> <span m='376040'>of</span>
  <span m='376190'>all,</span> <span m='376740'>a</span> <span
  m='376790'>design</span> <span m='377210'>technique</span> <span
  m='377900'>which</span> <span m='378230'>is</span> <span
  m='378350'>referred</span> <span m='378710'>to</span> <span
  m='379130'>as</span> <span m='379280'>the</span> <span
  m='379400'>window</span> <span m='379790'>method.</span> <span
  m='381890'>The</span> <span m='381950'>second</span> <span
  m='382730'>design</span> <span m='383150'>technique</span> <span
  m='383840'>that</span> <span m='384170'>is</span> <span
  m='384350'>commonly</span> <span m='384830'>referred</span> <span
  m='385250'>to</span> <span m='385700'>as</span> <span m='386390'>the</span>
  <span m='386510'>frequency</span> <span m='387050'>sampling</span> <span
  m='387590'>method.</span> <span m='388780'>And</span> <span
  m='389410'>a</span> <span m='389480'>third</span> <span
  m='389810'>designed</span> <span m='390260'>technique,</span> <span
  m='391040'>which</span> <span m='391490'>is</span> <span m='391880'>an</span>
  <span m='392000'>algorithmic</span> <span m='393020'>design</span> <span
  m='393440'>procedure</span> <span m='394580'>which</span> <span
  m='395000'>results</span> <span m='395750'>in</span> <span
  m='396140'>equiripple</span> <span m='397370'>filters,</span> <span
  m='398550'>which</span> <span m='399020'>as</span> <span
  m='399500'>I'll</span> <span m='400010'>comment</span> <span
  m='400520'>on</span> <span m='400700'>again</span> <span
  m='401030'>when</span> <span m='401180'>we</span> <span m='401270'>get</span>
  <span m='401450'>to</span> <span m='401570'>this</span> <span
  m='401750'>point</span> <span m='402020'>in</span> <span m='402080'>the</span>
  <span m='402170'>lecture,</span> <span m='403460'>turn</span> <span
  m='403770'>out</span> <span m='403940'>to</span> <span m='404060'>be</span>
  <span m='404210'>important</span> <span m='404870'>because</span> <span
  m='405620'>they</span> <span m='405800'>have</span> <span
  m='406280'>some</span> <span m='406610'>optimality</span> <span
  m='407300'>properties.</span> <span m='408570'>So</span> <span
  m='408980'>these</span> <span m='409250'>are</span> <span
  m='409340'>the</span> <span m='409460'>three</span> <span
  m='409940'>basic</span> <span m='410390'>design</span> <span
  m='411110'>techniques,</span> <span m='411710'>then,</span> <span
  m='412220'>that</span> <span m='412520'>I'd</span> <span
  m='412700'>like</span> <span m='413120'>to</span> <span
  m='413420'>discuss</span> <span m='413930'>in</span> <span
  m='414020'>this</span> <span m='414200'>lecture.</span> </p><p><span
  m='416370'>Well,</span> <span m='416690'>to</span> <span
  m='416810'>begin</span> <span m='417170'>with,</span> <span
  m='417740'>the</span> <span m='418730'>window</span> <span
  m='419150'>method</span> <span m='420800'>is</span> <span
  m='421760'>basically</span> <span m='424850'>a</span> <span
  m='424940'>method</span> <span m='425720'>based</span> <span
  m='426140'>on</span> <span m='426710'>the</span> <span
  m='426830'>following</span> <span m='427280'>strategy.</span> <span
  m='429190'>Let's</span> <span m='429430'>suppose</span> <span
  m='430420'>that</span> <span m='430960'>we</span> <span
  m='431110'>begin</span> <span m='431830'>the</span> <span
  m='432070'>design</span> <span m='432790'>of</span> <span
  m='433690'>the</span> <span m='433870'>finite</span> <span
  m='434260'>impulse</span> <span m='434650'>response</span> <span
  m='435190'>filter</span> <span m='436270'>with</span> <span
  m='436720'>a</span> <span m='436930'>desired</span> <span
  m='437740'>unit</span> <span m='438070'>sample</span> <span
  m='438490'>response,</span> <span m='439450'>h</span> <span
  m='439570'>sub</span> <span m='439750'>d of</span> <span m='440140'>n.</span>
  <span m='440590'>For</span> <span m='440770'>example,</span> <span
  m='441410'>suppose</span> <span m='441760'>that</span> <span
  m='441880'>we</span> <span m='442000'>wanted</span> <span m='442270'>to</span>
  <span m='442420'>design</span> <span m='443260'>a</span> <span
  m='444400'>low</span> <span m='444640'>pass</span> <span
  m='445030'>filter.</span> <span m='446290'>We</span> <span
  m='446470'>could</span> <span m='446830'>begin</span> <span
  m='447460'>with</span> <span m='447880'>a</span> <span
  m='448030'>desired</span> <span m='448600'>unit</span> <span
  m='448840'>sample</span> <span m='449260'>response</span> <span
  m='450010'>which</span> <span m='450280'>was</span> <span
  m='450520'>the</span> <span m='450610'>unit</span> <span
  m='450880'>sample</span> <span m='451270'>response</span> <span
  m='451840'>of</span> <span m='451990'>an</span> <span m='452080'>ideal</span>
  <span m='452620'>low</span> <span m='452800'>pass</span> <span
  m='453160'>filter.</span> </p><p><span m='454400'>Now</span> <span
  m='454720'>as</span> <span m='455410'>you</span> <span m='455560'>know,</span>
  <span m='456490'>the</span> <span m='457120'>unit</span> <span
  m='457420'>sample</span> <span m='457840'>response</span> <span
  m='458440'>of</span> <span m='458530'>an</span> <span m='458620'>ideal</span>
  <span m='458980'>low</span> <span m='459160'>pass</span> <span
  m='459550'>filter</span> <span m='461630'>basically</span> <span
  m='462550'>has</span> <span m='463030'>a</span> <span m='463240'>sin</span>
  <span m='463630'>x</span> <span m='464200'>over</span> <span
  m='464490'>x</span> <span m='464800'>type</span> <span m='465070'>of</span>
  <span m='465190'>envelope.</span> <span m='466180'>In</span> <span
  m='466300'>particular,</span> <span m='467110'>the</span> <span
  m='467260'>important</span> <span m='467680'>characteristic</span> <span
  m='468610'>is</span> <span m='468820'>that</span> <span m='468970'>it</span>
  <span m='469060'>extends</span> <span m='469570'>from</span> <span
  m='469720'>minus</span> <span m='470140'>infinity</span> <span
  m='470800'>to</span> <span m='470950'>plus</span> <span
  m='471250'>infinity.</span> <span m='472400'>So</span> <span
  m='472690'>in</span> <span m='472810'>fact,</span> <span m='474040'>it</span>
  <span m='474220'>doesn't</span> <span m='474610'>correspond</span> <span
  m='475390'>to</span> <span m='475540'>a</span> <span m='475600'>finite</span>
  <span m='476020'>impulse</span> <span m='476410'>response</span> <span
  m='476920'>filter.</span> <span m='477940'>But</span> <span
  m='478300'>we</span> <span m='478480'>could</span> <span
  m='478690'>imagine</span> <span m='480220'>obtaining</span> <span
  m='481000'>the</span> <span m='481090'>unit</span> <span
  m='481390'>sample</span> <span m='481780'>response</span> <span
  m='482590'>of</span> <span m='483580'>an</span> <span m='483700'>FIR</span>
  <span m='484330'>filter</span> <span m='485590'>by</span> <span
  m='487090'>perhaps</span> <span m='487930'>truncating</span> <span
  m='489220'>this</span> <span m='489460'>infinitely</span> <span
  m='490090'>long</span> <span m='490360'>unit</span> <span
  m='490630'>sample</span> <span m='491080'>response</span> <span
  m='492880'>so</span> <span m='493120'>that</span> <span m='493390'>we</span>
  <span m='493540'>retain</span> <span m='494020'>only</span> <span
  m='494350'>the</span> <span m='494470'>values</span> <span
  m='495190'>in</span> <span m='495340'>the</span> <span
  m='495460'>interval</span> <span m='495940'>from</span> <span
  m='496120'>0</span> <span m='496480'>to</span> <span m='496630'>capital</span>
  <span m='497110'>N</span> <span m='497230'>minus</span> <span
  m='497650'>1.</span> </p><p><span m='498650'>Or</span> <span
  m='499150'>more</span> <span m='499390'>generally,</span> <span
  m='500560'>we</span> <span m='500710'>can</span> <span
  m='500890'>imagine</span> <span m='502000'>multiplying</span> <span
  m='503170'>the</span> <span m='503290'>desired</span> <span
  m='503890'>unit</span> <span m='504160'>sample</span> <span
  m='504550'>response</span> <span m='505780'>by</span> <span
  m='505990'>a</span> <span m='506080'>window,</span> <span
  m='508100'>the</span> <span m='508120'>window</span> <span
  m='508690'>being</span> <span m='509020'>0</span> <span
  m='509710'>outside</span> <span m='510190'>the</span> <span
  m='510340'>interval</span> <span m='510730'>from</span> <span
  m='510910'>0</span> <span m='511270'>to</span> <span m='511420'>capital</span>
  <span m='511870'>N</span> <span m='512020'>minus</span> <span
  m='512409'>1.</span> <span m='513559'>So</span> <span m='513700'>the</span>
  <span m='513789'>window</span> <span m='514120'>method</span> <span
  m='514990'>basically</span> <span m='515530'>consists</span> <span
  m='516370'>of</span> <span m='516490'>beginning</span> <span
  m='517150'>with</span> <span m='517340'>a</span> <span
  m='517419'>desired</span> <span m='517929'>unit</span> <span
  m='518230'>sample</span> <span m='518620'>response,</span> <span
  m='519760'>which</span> <span m='520059'>in</span> <span
  m='520179'>general</span> <span m='520600'>will</span> <span
  m='520750'>be</span> <span m='521020'>infinitely</span> <span
  m='521559'>long,</span> <span m='522000'>or</span> <span m='522100'>at</span>
  <span m='522159'>least</span> <span m='522400'>longer</span> <span
  m='522789'>than</span> <span m='522940'>the</span> <span
  m='523030'>filter</span> <span m='523360'>that</span> <span
  m='523510'>we</span> <span m='523659'>want</span> <span m='523830'>to</span>
  <span m='523929'>design.</span> <span m='525280'>We</span> <span
  m='525460'>apply</span> <span m='525850'>to</span> <span
  m='526000'>that</span> <span m='526330'>a</span> <span
  m='526440'>window,</span> <span m='527590'>which</span> <span
  m='527800'>is</span> <span m='527920'>0</span> <span m='528640'>outside</span>
  <span m='529180'>the</span> <span m='529300'>range</span> <span
  m='529720'>0</span> <span m='530630'>to</span> <span m='530790'>capital</span>
  <span m='531280'>N</span> <span m='531400'>minus</span> <span
  m='531760'>1.</span> <span m='533041'>And</span> <span m='533470'>the</span>
  <span m='533560'>result</span> <span m='533950'>then</span> <span
  m='534280'>is</span> <span m='534490'>the</span> <span m='534610'>unit</span>
  <span m='534880'>sample</span> <span m='535270'>response</span> <span
  m='536050'>of</span> <span m='536500'>the</span> <span
  m='536620'>finite</span> <span m='537010'>impulse</span> <span
  m='537400'>response</span> <span m='537880'>filter.</span> </p><p><span
  m='540020'>Well,</span> <span m='540640'>what</span> <span
  m='540850'>is</span> <span m='540970'>the</span> <span
  m='541120'>effect</span> <span m='541510'>of</span> <span
  m='541630'>this</span> <span m='542140'>in</span> <span m='542260'>the</span>
  <span m='542350'>frequency</span> <span m='542890'>domain?</span> <span
  m='544310'>We</span> <span m='544330'>know</span> <span m='544930'>that</span>
  <span m='545200'>multiplication</span> <span m='546250'>in</span> <span
  m='546370'>the</span> <span m='546460'>time</span> <span
  m='546790'>domain</span> <span m='547570'>corresponds</span> <span
  m='548590'>to</span> <span m='548890'>convolution</span> <span
  m='549670'>in</span> <span m='549760'>the</span> <span
  m='549820'>frequency</span> <span m='550360'>domain.</span> <span
  m='551570'>And</span> <span m='551670'>consequently,</span> <span
  m='552970'>the</span> <span m='553060'>frequency</span> <span
  m='553690'>response</span> <span m='555520'>of</span> <span
  m='555670'>the</span> <span m='555790'>finite</span> <span
  m='556180'>impulse</span> <span m='556600'>response</span> <span
  m='557080'>filter</span> <span m='557800'>that</span> <span
  m='557980'>results,</span> <span m='559420'>is</span> <span
  m='560140'>the</span> <span m='560260'>periodic</span> <span
  m='560830'>convolution</span> <span m='562510'>of</span> <span
  m='563170'>the</span> <span m='563440'>desired</span> <span
  m='564760'>frequency</span> <span m='565300'>response.</span> <span
  m='566440'>That</span> <span m='566680'>is,</span> <span m='566860'>the</span>
  <span m='567030'>Fourier</span> <span m='567370'>transform</span> <span
  m='568270'>of</span> <span m='568450'>the</span> <span
  m='568570'>desired</span> <span m='569080'>unit</span> <span
  m='569350'>sample</span> <span m='569740'>response,</span> <span
  m='570940'>that</span> <span m='571360'>convolved</span> <span
  m='572440'>with</span> <span m='573010'>the</span> <span
  m='573110'>Fourier</span> <span m='573580'>transform</span> <span
  m='574450'>of</span> <span m='574630'>the</span> <span
  m='574750'>window,</span> <span m='575650'>w</span> <span m='576070'>of
  n</span> </p><p><span m='578090'>For</span> <span m='578170'>example,</span>
  <span m='579770'>if</span> <span m='580060'>we</span> <span
  m='580270'>were</span> <span m='580390'>talking</span> <span
  m='580810'>about</span> <span m='581080'>a</span> <span
  m='581140'>rectangular</span> <span m='581860'>window,</span> <span
  m='582460'>and</span> <span m='582610'>in</span> <span m='582730'>a</span>
  <span m='582790'>rectangular</span> <span m='583450'>window,</span> <span
  m='584290'>w</span> <span m='584680'>of</span> <span m='584980'>n is</span>
  <span m='585070'>simply</span> <span m='585460'>constant</span> <span
  m='586750'>over</span> <span m='587380'>the</span> <span
  m='587530'>range</span> <span m='587830'>0</span> <span m='588160'>to</span>
  <span m='588310'>capital</span> <span m='588790'>N</span> <span
  m='588910'>minus</span> <span m='589330'>1,</span> <span m='591650'>the</span>
  <span m='592420'>magnitude</span> <span m='593320'>of</span> <span
  m='593500'>the</span> <span m='593610'>Fourier</span> <span
  m='594040'>transform</span> <span m='594970'>of</span> <span
  m='595150'>the</span> <span m='595270'>window</span> <span
  m='596200'>has</span> <span m='596740'>a</span> <span m='596830'>form</span>
  <span m='597850'>roughly</span> <span m='598480'>as</span> <span
  m='598750'>I've</span> <span m='598900'>indicated</span> <span
  m='599470'>here.</span> <span m='600100'>This</span> <span
  m='600310'>is</span> <span m='600400'>drawn</span> <span m='600970'>for</span>
  <span m='601090'>the</span> <span m='601180'>case,</span> <span
  m='601520'>N</span> <span m='601660'>equals</span> <span m='602070'>8.</span>
  <span m='602710'>And</span> <span m='603220'>it's</span> <span
  m='603460'>the</span> <span m='603580'>magnitude</span> <span
  m='604420'>of</span> <span m='604690'>h of e</span> <span m='605140'>to</span>
  <span m='605240'>the</span> <span m='605350'>j</span> <span
  m='605560'>omega--</span> <span m='606370'>I'm</span> <span
  m='606640'>sorry,</span> <span m='606920'>of</span> <span m='607000'>w</span>
  <span m='607350'>of</span> <span m='607420'>e</span> <span
  m='607580'>to</span> <span m='607720'>the</span> <span m='607810'>j</span>
  <span m='608020'>omega.</span> <span m='609400'>If</span> <span
  m='609580'>we</span> <span m='609670'>were</span> <span m='609850'>to</span>
  <span m='610000'>remove</span> <span m='610420'>the</span> <span
  m='610540'>magnitude</span> <span m='611160'>sines,</span> <span
  m='611980'>then</span> <span m='613360'>every</span> <span
  m='613780'>alternate</span> <span m='614320'>lobe</span> <span
  m='615010'>would</span> <span m='615250'>be</span> <span
  m='615400'>flipped</span> <span m='615730'>over</span> <span
  m='616030'>in</span> <span m='616120'>sine.</span> <span m='616620'>So</span>
  <span m='616870'>in</span> <span m='616930'>fact,</span> <span
  m='617260'>this</span> <span m='617470'>is</span> <span m='617650'>a</span>
  <span m='618220'>sin</span> <span m='618920'>nx</span> <span
  m='619740'>over</span> <span m='620000'>sin</span> <span m='620380'>x</span>
  <span m='620620'>curve.</span> </p><p><span m='622550'>So</span> <span
  m='623320'>for</span> <span m='623680'>the</span> <span
  m='623770'>particular</span> <span m='624310'>case</span> <span
  m='624820'>of</span> <span m='624970'>a</span> <span
  m='625030'>rectangular</span> <span m='625690'>window,</span> <span
  m='627130'>we</span> <span m='627310'>would</span> <span
  m='627760'>have</span> <span m='628420'>not</span> <span m='629110'>the</span>
  <span m='629470'>ideal</span> <span m='629950'>low</span> <span
  m='630190'>pass</span> <span m='630580'>filter</span> <span
  m='631540'>that</span> <span m='632290'>we</span> <span
  m='632410'>began</span> <span m='632920'>with,</span> <span
  m='633640'>but</span> <span m='634150'>the</span> <span
  m='634300'>ideal</span> <span m='634870'>lowpass</span> <span
  m='635230'>filter</span> <span m='635590'>frequency</span> <span
  m='636130'>characteristic</span> <span m='637420'>convolved</span> <span
  m='638470'>with</span> <span m='639070'>the</span> <span
  m='639190'>Fourier</span> <span m='639640'>transform</span> <span
  m='640570'>of</span> <span m='640750'>the</span> <span
  m='640840'>window.</span> <span m='642430'>So</span> <span
  m='642940'>that's</span> <span m='643240'>depicted</span> <span
  m='643720'>here</span> <span m='644350'>where</span> <span
  m='645340'>we</span> <span m='645520'>have</span> <span m='647260'>the</span>
  <span m='647710'>ideal</span> <span m='648180'>low</span> <span
  m='648370'>pass</span> <span m='648790'>filter.</span> <span
  m='650980'>Superimposed</span> <span m='652420'>on</span> <span
  m='652600'>top</span> <span m='652960'>of</span> <span m='653110'>it</span>
  <span m='653590'>is</span> <span m='654250'>the</span> <span
  m='654370'>Fourier</span> <span m='654820'>transform</span> <span
  m='655720'>of,</span> <span m='656590'>in</span> <span m='656710'>this</span>
  <span m='656860'>case,</span> <span m='657280'>a</span> <span
  m='657340'>rectangular</span> <span m='658030'>window.</span> </p><p><span
  m='659380'>And</span> <span m='660430'>then</span> <span m='661300'>to</span>
  <span m='661690'>obtain</span> <span m='662350'>the</span> <span
  m='662620'>resulting</span> <span m='663340'>overall</span> <span
  m='663850'>frequency</span> <span m='664390'>response</span> <span
  m='665140'>of</span> <span m='665380'>the</span> <span
  m='665470'>finite</span> <span m='665860'>impulse</span> <span
  m='666250'>response</span> <span m='666760'>filter,</span> <span
  m='667750'>that</span> <span m='667930'>would</span> <span
  m='668080'>be</span> <span m='668230'>obtained</span> <span
  m='669220'>by</span> <span m='669650'>convolving</span> <span
  m='670660'>these</span> <span m='670960'>two</span> <span
  m='671470'>together.</span> <span m='673240'>And</span> <span
  m='673390'>we</span> <span m='673540'>can</span> <span m='673720'>see</span>
  <span m='673990'>that</span> <span m='674140'>the</span> <span
  m='674260'>result</span> <span m='674680'>of</span> <span
  m='674800'>that,</span> <span m='675340'>very</span> <span
  m='675640'>roughly,</span> <span m='676780'>is</span> <span
  m='677860'>to,</span> <span m='678670'>in</span> <span m='678760'>fact,</span>
  <span m='679130'>at</span> <span m='679360'>the</span> <span
  m='679490'>discontinuity,</span> <span m='680650'>the</span> <span
  m='681010'>almost</span> <span m='681430'>exact</span> <span
  m='681850'>effect</span> <span m='682330'>is</span> <span m='682990'>to</span>
  <span m='683350'>integrate</span> <span m='684250'>the</span> <span
  m='684460'>window</span> <span m='685060'>frequency</span> <span
  m='685630'>response,</span> <span m='686260'>the</span> <span
  m='686380'>frequency</span> <span m='687040'>response</span> <span
  m='687520'>of</span> <span m='687640'>the</span> <span
  m='687730'>window.</span> <span m='688900'>And</span> <span
  m='689680'>the</span> <span m='689920'>resulting</span> <span
  m='691240'>frequency</span> <span m='691780'>response</span> <span
  m='692410'>for</span> <span m='692530'>the</span> <span
  m='692620'>finite</span> <span m='693010'>impulse</span> <span
  m='693400'>response</span> <span m='693910'>filter</span> <span
  m='694870'>then,</span> <span m='695410'>as</span> <span
  m='695680'>opposed</span> <span m='696700'>to</span> <span
  m='696820'>being</span> <span m='697420'>the</span> <span
  m='697600'>ideal</span> <span m='698080'>characteristic</span> <span
  m='699040'>that</span> <span m='699160'>we</span> <span
  m='699310'>desired,</span> <span m='700900'>in</span> <span
  m='701020'>fact</span> <span m='701770'>has</span> <span
  m='702430'>some</span> <span m='702700'>ripples</span> <span
  m='703150'>in</span> <span m='703300'>it.</span> </p><p><span
  m='704770'>Generally,</span> <span m='705700'>then,</span> <span
  m='706900'>it</span> <span m='707350'>has</span> <span m='708040'>some</span>
  <span m='708340'>deviation</span> <span m='709250'>in</span> <span
  m='709390'>the</span> <span m='709480'>pass</span> <span
  m='709580'>band.</span> <span m='710800'>It</span> <span m='710920'>has</span>
  <span m='711160'>some</span> <span m='711310'>deviation</span> <span
  m='712000'>in</span> <span m='712090'>the</span> <span m='712180'>stop</span>
  <span m='712570'>band.</span> <span m='713470'>And</span> <span
  m='713920'>it</span> <span m='714100'>has</span> <span m='714520'>a</span>
  <span m='714610'>transition</span> <span m='715240'>region</span> <span
  m='715630'>from</span> <span m='715810'>pass band</span> <span
  m='716380'>to</span> <span m='716500'>stop band.</span> <span
  m='717940'>And</span> <span m='718060'>that's</span> <span
  m='718330'>introduced</span> <span m='719470'>because</span> <span
  m='720190'>of</span> <span m='720340'>the</span> <span
  m='720460'>convolution</span> <span m='721810'>of</span> <span
  m='721960'>this</span> <span m='722200'>window</span> <span
  m='722890'>frequency</span> <span m='723430'>response</span> <span
  m='724480'>with</span> <span m='724930'>the</span> <span
  m='725050'>desired</span> <span m='725800'>or</span> <span
  m='726010'>ideal</span> <span m='726460'>frequency</span> <span
  m='727000'>response.</span> </p><p><span m='729380'>Now</span> <span
  m='729830'>ideally,</span> <span m='730850'>what</span> <span
  m='731450'>would</span> <span m='731900'>we</span> <span
  m='732080'>like</span> <span m='732890'>as</span> <span m='733580'>the</span>
  <span m='733850'>frequency</span> <span m='734420'>response</span> <span
  m='735380'>of</span> <span m='735590'>the</span> <span
  m='735680'>window?</span> <span m='736730'>Well,</span> <span
  m='737030'>ideally</span> <span m='737570'>what</span> <span
  m='737720'>we</span> <span m='737870'>would</span> <span
  m='738020'>like,</span> <span m='738260'>of</span> <span
  m='738380'>course,</span> <span m='739400'>is</span> <span
  m='739940'>we</span> <span m='740120'>would</span> <span
  m='740270'>like</span> <span m='740840'>this</span> <span
  m='741110'>function</span> <span m='742850'>to</span> <span
  m='743000'>be</span> <span m='743630'>an</span> <span
  m='743750'>impulse.</span> <span m='745430'>Because</span> <span
  m='745820'>if</span> <span m='745970'>it's</span> <span m='746090'>an</span>
  <span m='746180'>impulse,</span> <span m='746720'>then</span> <span
  m='746870'>we</span> <span m='746990'>convolve</span> <span
  m='747440'>it</span> <span m='747560'>with</span> <span m='747710'>the</span>
  <span m='747800'>desired</span> <span m='748370'>frequency</span> <span
  m='748910'>response,</span> <span m='749600'>and</span> <span
  m='749720'>the</span> <span m='749810'>result</span> <span
  m='750560'>will</span> <span m='750890'>again</span> <span
  m='751220'>be</span> <span m='751400'>the</span> <span
  m='751490'>desired</span> <span m='751970'>frequency</span> <span
  m='752510'>response.</span> <span m='754640'>The</span> <span
  m='754820'>overshoot</span> <span m='755630'>that</span> <span
  m='755840'>we</span> <span m='755990'>have</span> <span m='756200'>in</span>
  <span m='756290'>the</span> <span m='756380'>pass</span> <span
  m='756730'>band</span> <span m='757280'>and</span> <span m='757500'>the</span>
  <span m='757580'>stop</span> <span m='757940'>band</span> <span
  m='759230'>has</span> <span m='759440'>arisen</span> <span
  m='760130'>because</span> <span m='761060'>of</span> <span
  m='761630'>the</span> <span m='761810'>side</span> <span
  m='762260'>lobe</span> <span m='762530'>structure</span> <span
  m='763490'>of</span> <span m='764060'>the</span> <span
  m='764300'>frequency</span> <span m='764870'>response</span> <span
  m='765500'>of</span> <span m='765650'>the</span> <span
  m='765770'>window.</span> <span m='767840'>And</span> <span
  m='767990'>the</span> <span m='768080'>transition</span> <span
  m='768770'>region</span> <span m='769790'>has</span> <span
  m='770000'>arisen</span> <span m='770660'>because,</span> <span
  m='772190'>primarily</span> <span m='773090'>because</span> <span
  m='773810'>of</span> <span m='774020'>the</span> <span m='774110'>width</span>
  <span m='774590'>of</span> <span m='774740'>this</span> <span
  m='774900'>central</span> <span m='775310'>lobe.</span> </p><p><span
  m='776600'>So,</span> <span m='777200'>in</span> <span m='777320'>fact,</span>
  <span m='777960'>if</span> <span m='778220'>we</span> <span
  m='778400'>want</span> <span m='778670'>to</span> <span m='778790'>keep</span>
  <span m='779570'>the</span> <span m='780290'>deviation</span> <span
  m='781010'>in</span> <span m='781100'>the</span> <span m='781190'>pass</span>
  <span m='781520'>band</span> <span m='781850'>and</span> <span
  m='781940'>stop</span> <span m='782390'>band</span> <span
  m='782630'>small,</span> <span m='783830'>then</span> <span
  m='784430'>that</span> <span m='784670'>implies</span> <span
  m='785300'>that</span> <span m='785420'>we</span> <span
  m='785570'>would</span> <span m='785690'>like</span> <span
  m='785900'>to</span> <span m='786020'>keep</span> <span m='786290'>the</span>
  <span m='786380'>side</span> <span m='786695'>lobe</span> <span
  m='787010'>structure</span> <span m='788060'>of</span> <span
  m='788660'>the</span> <span m='788780'>window</span> <span
  m='790100'>small,</span> <span m='790970'>the</span> <span
  m='791090'>window</span> <span m='791360'>frequency</span> <span
  m='791870'>response</span> <span m='792380'>small.</span> <span
  m='794090'>And</span> <span m='794240'>if</span> <span m='794390'>we</span>
  <span m='794480'>would</span> <span m='794600'>like</span> <span
  m='794810'>to</span> <span m='794930'>keep</span> <span m='795170'>the</span>
  <span m='795260'>transition</span> <span m='795890'>band</span> <span
  m='796160'>narrow,</span> <span m='797180'>that</span> <span
  m='797360'>implies</span> <span m='798080'>that</span> <span
  m='798200'>we</span> <span m='798380'>would</span> <span
  m='798530'>like</span> <span m='798800'>to</span> <span m='799100'>keep</span>
  <span m='799640'>this</span> <span m='800030'>main</span> <span
  m='800330'>lobe</span> <span m='800960'>narrow.</span> <span
  m='802970'>And</span> <span m='804020'>as</span> <span m='805010'>I</span>
  <span m='805130'>think</span> <span m='805460'>that</span> <span
  m='805940'>your</span> <span m='806150'>intuition</span> <span
  m='806960'>should</span> <span m='807170'>agree</span> <span
  m='807470'>with</span> <span m='807920'>by</span> <span m='808160'>now,</span>
  <span m='809090'>generally,</span> <span m='809900'>an</span> <span
  m='810020'>attempt</span> <span m='810710'>to</span> <span
  m='810830'>make</span> <span m='811730'>this</span> <span
  m='812300'>function</span> <span m='813380'>narrower</span> <span
  m='814160'>in</span> <span m='814310'>frequency</span> <span
  m='815960'>will</span> <span m='816320'>have</span> <span
  m='816830'>the</span> <span m='816950'>general</span> <span
  m='817460'>effect</span> <span m='818420'>of</span> <span
  m='818870'>making</span> <span m='819410'>the</span> <span
  m='819530'>window</span> <span m='820340'>longer</span> <span
  m='820760'>in</span> <span m='820880'>time.</span> </p><p><span
  m='821780'>So</span> <span m='821960'>that,</span> <span m='822290'>in</span>
  <span m='822410'>fact,</span> <span m='825200'>as</span> <span
  m='825440'>we</span> <span m='825620'>try</span> <span m='825950'>to</span>
  <span m='826130'>make</span> <span m='826850'>the</span> <span
  m='827000'>time</span> <span m='827450'>window,</span> <span
  m='828250'>w</span> <span m='828640'>of</span> <span m='828740'>n,</span>
  <span m='829010'>or</span> <span m='829190'>equivalently,</span> <span
  m='829790'>the</span> <span m='829940'>order</span> <span m='830450'>of</span>
  <span m='830600'>the</span> <span m='830720'>finite</span> <span
  m='831050'>impulse</span> <span m='831410'>response</span> <span
  m='831890'>filter</span> <span m='832580'>smaller,</span> <span
  m='834560'>the</span> <span m='834920'>tendency</span> <span
  m='835850'>will</span> <span m='836030'>be</span> <span
  m='836300'>toward</span> <span m='836780'>a</span> <span
  m='836900'>widening</span> <span m='837440'>transition</span> <span
  m='838100'>band</span> <span m='839090'>in</span> <span m='839750'>the</span>
  <span m='840410'>frequency</span> <span m='840950'>response</span> <span
  m='841430'>of</span> <span m='841520'>the</span> <span
  m='841610'>filter.</span> <span m='843110'>Likewise,</span> <span
  m='843830'>as</span> <span m='844430'>we</span> <span m='844610'>allow</span>
  <span m='844880'>the</span> <span m='845000'>order</span> <span
  m='845240'>of</span> <span m='845330'>the</span> <span
  m='845420'>filter</span> <span m='845750'>to</span> <span
  m='845870'>get</span> <span m='846020'>longer,</span> <span
  m='846920'>we</span> <span m='847100'>have</span> <span m='847580'>more</span>
  <span m='847820'>flexibility</span> <span m='848630'>in</span> <span
  m='848720'>the</span> <span m='848780'>filter.</span> <span
  m='849350'>And</span> <span m='849500'>consequently,</span> <span
  m='850730'>we're</span> <span m='850910'>able</span> <span
  m='851180'>to</span> <span m='851300'>control</span> <span
  m='851840'>better</span> <span m='852590'>the</span> <span
  m='852680'>transition</span> <span m='853250'>band</span> <span
  m='853830'>and</span> <span m='854000'>the</span> <span
  m='854120'>overshoot</span> <span m='854750'>in</span> <span
  m='854870'>both</span> <span m='855110'>the</span> <span m='855200'>pass
  band</span> <span m='855830'>and</span> <span m='855970'>in</span> <span
  m='856080'>the</span> <span m='856130'>stop band.</span> </p><p><span
  m='860200'>Well,</span> <span m='861310'>in</span> <span
  m='861460'>particular,</span> <span m='862690'>again</span> <span
  m='863050'>continuing</span> <span m='863620'>with</span> <span
  m='863770'>the</span> <span m='863890'>example</span> <span
  m='864670'>of</span> <span m='865270'>a</span> <span
  m='865870'>rectangular</span> <span m='866590'>window,</span> <span
  m='868240'>if</span> <span m='868420'>we</span> <span m='868540'>look</span>
  <span m='868720'>at</span> <span m='868810'>the</span> <span
  m='868900'>frequency--</span> <span m='869920'>the</span> <span
  m='870310'>unit</span> <span m='870640'>sample</span> <span
  m='871060'>response</span> <span m='871930'>for</span> <span
  m='872770'>the</span> <span m='873850'>case</span> <span m='874360'>of</span>
  <span m='875080'>an</span> <span m='876970'>ideal</span> <span
  m='878380'>low</span> <span m='878590'>pass</span> <span
  m='878980'>filter</span> <span m='880150'>multiplied</span> <span
  m='881350'>by</span> <span m='881950'>a</span> <span m='882250'>51</span>
  <span m='883180'>point</span> <span m='884170'>rectangular</span> <span
  m='884860'>window,</span> <span m='886180'>then</span> <span
  m='886960'>the</span> <span m='887110'>unit</span> <span
  m='887380'>sample</span> <span m='887770'>response</span> <span
  m='888520'>we</span> <span m='888700'>obtain</span> <span m='889270'>is</span>
  <span m='889460'>as</span> <span m='889600'>indicated</span> <span
  m='890200'>here.</span> <span m='890630'>Actually,</span> <span
  m='891010'>I've</span> <span m='891130'>marked</span> <span
  m='891460'>this</span> <span m='891760'>as</span> <span m='892480'>the</span>
  <span m='892570'>desired</span> <span m='893320'>unit</span> <span
  m='893590'>sample</span> <span m='893980'>response.</span> <span
  m='895060'>It's</span> <span m='895240'>only</span> <span
  m='895840'>equal</span> <span m='896170'>to</span> <span m='896290'>the</span>
  <span m='896410'>desired</span> <span m='896860'>unit</span> <span
  m='897070'>sample</span> <span m='897460'>response</span> <span
  m='898090'>in</span> <span m='898210'>the</span> <span
  m='898330'>interval</span> <span m='899140'>from</span> <span
  m='899320'>0</span> <span m='900370'>to</span> <span m='900760'>50.</span>
  <span m='901840'>And</span> <span m='902140'>the</span> <span
  m='902230'>desired</span> <span m='902710'>unit</span> <span
  m='902980'>sample</span> <span m='903310'>response,</span> <span
  m='903760'>of</span> <span m='903850'>course,</span> <span
  m='904220'>continues</span> <span m='904750'>to</span> <span
  m='904840'>be</span> <span m='904960'>non-zero</span> <span
  m='905740'>outside</span> <span m='906250'>that</span> <span
  m='906460'>range.</span> <span m='907330'>Whereas</span> <span
  m='907630'>multiplying</span> <span m='908290'>by</span> <span
  m='908470'>a</span> <span m='908530'>rectangular</span> <span
  m='909160'>window</span> <span m='909910'>truncates</span> <span
  m='910540'>it</span> <span m='910960'>to</span> <span m='911080'>be</span>
  <span m='911230'>0</span> <span m='911980'>outside</span> <span
  m='912460'>this</span> <span m='912670'>range.</span> </p><p><span
  m='914530'>The</span> <span m='914620'>resulting</span> <span
  m='916480'>frequency</span> <span m='917050'>response</span> <span
  m='917740'>for</span> <span m='917920'>this</span> <span
  m='918340'>particular</span> <span m='918910'>example</span> <span
  m='920230'>I've</span> <span m='920410'>indicated</span> <span
  m='920980'>here.</span> <span m='922070'>And</span> <span m='922870'>as</span>
  <span m='923290'>opposed</span> <span m='924160'>to</span> <span
  m='925390'>the</span> <span m='926020'>previous</span> <span
  m='927910'>frequency</span> <span m='928390'>response</span> <span
  m='928930'>that</span> <span m='929050'>I</span> <span
  m='929140'>depicted,</span> <span m='930160'>this</span> <span
  m='930400'>is</span> <span m='930490'>shown</span> <span m='930970'>on</span>
  <span m='931150'>a</span> <span m='931210'>logarithmic</span> <span
  m='931840'>frequency</span> <span m='932380'>scale.</span> <span
  m='933310'>There,</span> <span m='933490'>in</span> <span
  m='933580'>fact,</span> <span m='933890'>is</span> <span
  m='934020'>some</span> <span m='934240'>ripple</span> <span
  m='934540'>in</span> <span m='934600'>the</span> <span m='934720'>pass</span>
  <span m='935050'>band,</span> <span m='935380'>although</span> <span
  m='935680'>it's</span> <span m='935800'>not</span> <span
  m='935980'>evident</span> <span m='936670'>on</span> <span m='936850'>a</span>
  <span m='936910'>logarithmic</span> <span m='937480'>frequency</span> <span
  m='937990'>scale.</span> <span m='938920'>But</span> <span
  m='939880'>generally,</span> <span m='940420'>you</span> <span
  m='940570'>can</span> <span m='940720'>see</span> <span m='941140'>the</span>
  <span m='941290'>effect</span> <span m='941890'>of</span> <span
  m='942580'>a</span> <span m='942760'>transition</span> <span
  m='943450'>band,</span> <span m='944890'>and</span> <span
  m='945640'>then</span> <span m='946360'>a</span> <span m='947260'>side</span>
  <span m='947650'>lobe</span> <span m='947930'>structure</span> <span
  m='948820'>in</span> <span m='948970'>the</span> <span m='949030'>stop</span>
  <span m='949420'>band.</span> <span m='950650'>And</span> <span
  m='951190'>you</span> <span m='951400'>can</span> <span m='952030'>see</span>
  <span m='952360'>also</span> <span m='952900'>that</span> <span
  m='953590'>the</span> <span m='953800'>asymptotic</span> <span
  m='954760'>behavior</span> <span m='955360'>of</span> <span
  m='955480'>this</span> <span m='956260'>is--</span> <span m='957220'>in</span>
  <span m='957340'>the</span> <span m='957430'>vicinity</span> <span
  m='958300'>for</span> <span m='958450'>this</span> <span
  m='958600'>particular</span> <span m='959110'>example--</span> <span
  m='960190'>is</span> <span m='960640'>in</span> <span m='960760'>the</span>
  <span m='960850'>vicinity</span> <span m='961570'>of</span> <span
  m='961840'>minus</span> <span m='962200'>20</span> <span m='962500'>dB</span>
  <span m='963460'>attenuation</span> <span m='964210'>in</span> <span
  m='964300'>the</span> <span m='964390'>stop</span> <span
  m='964750'>band.</span> </p><p><span m='966880'>So</span> <span
  m='967510'>this</span> <span m='967780'>then</span> <span m='968230'>is</span>
  <span m='969190'>an</span> <span m='969280'>example</span> <span
  m='970030'>of</span> <span m='970270'>a</span> <span m='970330'>low</span>
  <span m='970510'>pass</span> <span m='970870'>filter</span> <span
  m='971740'>that</span> <span m='971920'>could</span> <span
  m='972070'>be</span> <span m='972250'>obtained</span> <span
  m='973000'>by</span> <span m='973510'>applying</span> <span
  m='973930'>a</span> <span m='973990'>rectangular</span> <span
  m='974650'>window</span> <span m='975640'>to</span> <span
  m='976180'>the</span> <span m='976390'>ideal</span> <span
  m='977980'>low</span> <span m='978190'>pass</span> <span
  m='978550'>filter.</span> <span m='979640'>There</span> <span
  m='979750'>are</span> <span m='980620'>other</span> <span
  m='981160'>possible</span> <span m='981640'>choices</span> <span
  m='982840'>for</span> <span m='983860'>windows.</span> <span
  m='984940'>In</span> <span m='985060'>particular,</span> <span
  m='986020'>two</span> <span m='987250'>other</span> <span
  m='987490'>choices</span> <span m='988060'>that</span> <span
  m='988210'>I'd</span> <span m='988330'>like</span> <span m='988540'>to</span>
  <span m='988660'>mention</span> <span m='990460'>are</span> <span
  m='991060'>what</span> <span m='991270'>are</span> <span
  m='991510'>referred</span> <span m='991960'>to</span> <span
  m='992350'>as</span> <span m='992710'>the</span> <span
  m='992830'>Hamming</span> <span m='993280'>window</span> <span
  m='994570'>and</span> <span m='995590'>the</span> <span
  m='995890'>Bartlett</span> <span m='996370'>window.</span> <span
  m='999530'>As</span> <span m='999680'>opposed</span> <span
  m='1000130'>to</span> <span m='1000610'>the</span> <span
  m='1000730'>rectangular</span> <span m='1001390'>window,</span> <span
  m='1002170'>the</span> <span m='1002260'>Bartlett</span> <span
  m='1002710'>window</span> <span m='1003400'>is</span> <span
  m='1004000'>a</span> <span m='1004210'>triangular</span> <span
  m='1004960'>window,</span> <span m='1006140'>which</span> <span
  m='1006250'>has</span> <span m='1006460'>the</span> <span
  m='1006580'>effect</span> <span m='1006940'>basically</span> <span
  m='1007870'>of</span> <span m='1008050'>making</span> <span
  m='1008470'>the</span> <span m='1008560'>transition</span> <span
  m='1009460'>at</span> <span m='1010120'>the</span> <span
  m='1010300'>ends</span> <span m='1010660'>of</span> <span
  m='1010750'>the</span> <span m='1010840'>unit</span> <span
  m='1011110'>sample</span> <span m='1011530'>response</span> <span
  m='1012610'>less</span> <span m='1013300'>abrupt</span> <span
  m='1014050'>than</span> <span m='1014200'>they</span> <span
  m='1014380'>are</span> <span m='1014710'>in</span> <span
  m='1014830'>the</span> <span m='1014890'>case</span> <span
  m='1015190'>of</span> <span m='1015280'>a</span> <span
  m='1015340'>rectangular</span> <span m='1016000'>window.</span> </p><p><span
  m='1017920'>The</span> <span m='1018040'>Hamming</span> <span
  m='1018460'>window</span> <span m='1019210'>is</span> <span
  m='1020920'>a</span> <span m='1021700'>window</span> <span
  m='1022330'>which</span> <span m='1022870'>corresponds</span> <span
  m='1023680'>essentially</span> <span m='1024849'>to</span> <span
  m='1025300'>a</span> <span m='1025599'>cosine</span> <span
  m='1026770'>bell</span> <span m='1027849'>sitting</span> <span
  m='1028540'>on</span> <span m='1028720'>a</span> <span
  m='1028780'>small</span> <span m='1029140'>pedestal.</span> <span
  m='1031099'>So</span> <span m='1031359'>for</span> <span
  m='1031510'>this</span> <span m='1031690'>particular</span> <span
  m='1032470'>example,</span> <span m='1033280'>again,</span> <span
  m='1033910'>the</span> <span m='1034660'>low</span> <span
  m='1034869'>pass</span> <span m='1035230'>filter,</span> <span
  m='1035650'>the</span> <span m='1035829'>ideal</span> <span
  m='1036190'>low</span> <span m='1036369'>pass</span> <span
  m='1036700'>filter</span> <span m='1037060'>windowed,</span> <span
  m='1038079'>we</span> <span m='1038230'>can</span> <span
  m='1038470'>compare</span> <span m='1039010'>the</span> <span
  m='1039160'>frequency</span> <span m='1039730'>response</span> <span
  m='1040480'>obtained</span> <span m='1041470'>with</span> <span
  m='1041619'>the</span> <span m='1041710'>Bartlett</span> <span
  m='1042190'>window</span> <span m='1043230'>to</span> <span
  m='1043480'>that</span> <span m='1043690'>obtained</span> <span
  m='1044020'>with</span> <span m='1044170'>the</span> <span
  m='1044230'>rectangular</span> <span m='1044859'>window,</span> <span
  m='1045430'>and</span> <span m='1045579'>also</span> <span
  m='1046270'>with</span> <span m='1046420'>the</span> <span
  m='1046510'>Hamming</span> <span m='1046900'>window.</span> <span
  m='1047869'>So</span> <span m='1048460'>let's</span> <span
  m='1049030'>take</span> <span m='1049270'>a</span> <span
  m='1049330'>look</span> <span m='1049540'>at</span> <span
  m='1049630'>that.</span> </p><p><span m='1052130'>Here</span> <span
  m='1052600'>we</span> <span m='1052810'>have</span> <span
  m='1053470'>the</span> <span m='1054160'>frequency</span> <span
  m='1054700'>response</span> <span m='1055480'>of</span> <span
  m='1056020'>the</span> <span m='1056140'>Bartlett</span> <span
  m='1056590'>window.</span> <span m='1057760'>And</span> <span
  m='1058810'>you</span> <span m='1058960'>can</span> <span
  m='1059110'>see</span> <span m='1059620'>generally</span> <span
  m='1060340'>that</span> <span m='1060730'>the</span> <span
  m='1060850'>ripples</span> <span m='1061510'>aren't</span> <span
  m='1061870'>as</span> <span m='1062020'>severe</span> <span
  m='1063260'>in</span> <span m='1063490'>the</span> <span
  m='1063660'>stop</span> <span m='1064050'>band</span> <span
  m='1064450'>as</span> <span m='1064660'>they</span> <span
  m='1064810'>were</span> <span m='1065200'>in</span> <span
  m='1065320'>the</span> <span m='1065410'>case</span> <span
  m='1065740'>of</span> <span m='1065830'>the</span> <span
  m='1065920'>rectangular</span> <span m='1066580'>window.</span> <span
  m='1067600'>And</span> <span m='1067750'>in</span> <span
  m='1067840'>fact,</span> <span m='1068570'>we</span> <span
  m='1068650'>can</span> <span m='1069070'>compare</span> <span
  m='1069550'>these</span> <span m='1070540'>simply</span> <span
  m='1071350'>by</span> <span m='1072010'>referring</span> <span
  m='1072550'>back</span> <span m='1072940'>to</span> <span
  m='1073660'>the</span> <span m='1077830'>rectangular</span> <span
  m='1078730'>window</span> <span m='1079060'>frequency</span> <span
  m='1079600'>response</span> <span m='1080170'>that</span> <span
  m='1080290'>we</span> <span m='1080440'>had</span> <span
  m='1080620'>previously.</span> <span m='1082430'>So</span> <span
  m='1082510'>the</span> <span m='1082600'>rectangular</span> <span
  m='1083530'>window</span> <span m='1085000'>lies</span> <span
  m='1085900'>slightly</span> <span m='1086560'>under,</span> <span
  m='1087610'>or</span> <span m='1087820'>actually</span> <span
  m='1088330'>asymptotically</span> <span m='1089170'>touches</span> <span
  m='1090160'>the</span> <span m='1090250'>frequency</span> <span
  m='1090760'>response</span> <span m='1091240'>obtained</span> <span
  m='1091630'>from</span> <span m='1091810'>the</span> <span
  m='1091900'>Bartlett</span> <span m='1092320'>window.</span> <span
  m='1093370'>But</span> <span m='1093820'>for</span> <span
  m='1093970'>the</span> <span m='1094090'>Bartlett</span> <span
  m='1094570'>window,</span> <span m='1095410'>the</span> <span
  m='1095680'>ripples</span> <span m='1096460'>in</span> <span
  m='1096580'>the</span> <span m='1096670'>stop</span> <span
  m='1097060'>band</span> <span m='1097810'>aren't</span> <span
  m='1098170'>as</span> <span m='1098320'>severe</span> <span
  m='1098980'>as</span> <span m='1099610'>they</span> <span
  m='1099820'>are</span> <span m='1100270'>for</span> <span
  m='1100930'>the</span> <span m='1101050'>rectangular</span> <span
  m='1101680'>window.</span> </p><p><span m='1103690'>Now</span> <span
  m='1103930'>to</span> <span m='1104080'>compare</span> <span
  m='1104680'>both</span> <span m='1105040'>of</span> <span
  m='1105100'>these</span> <span m='1105730'>to</span> <span
  m='1106240'>the</span> <span m='1106480'>Hamming</span> <span
  m='1106930'>window,</span> <span m='1109150'>we</span> <span
  m='1109330'>can</span> <span m='1110710'>put</span> <span
  m='1110890'>on</span> <span m='1111040'>top</span> <span m='1111430'>of</span>
  <span m='1111580'>this</span> <span m='1112180'>the</span> <span
  m='1112480'>frequency</span> <span m='1113050'>response</span> <span
  m='1114460'>for</span> <span m='1114820'>the</span> <span
  m='1115870'>Hamming</span> <span m='1116290'>window.</span> <span
  m='1120400'>And</span> <span m='1122190'>in</span> <span
  m='1122310'>this</span> <span m='1122520'>case,</span> <span
  m='1123250'>you</span> <span m='1123330'>can</span> <span
  m='1123510'>see</span> <span m='1124110'>that</span> <span
  m='1124890'>the</span> <span m='1124980'>frequency</span> <span
  m='1125490'>response</span> <span m='1126030'>obtained</span> <span
  m='1126600'>with</span> <span m='1126780'>the</span> <span
  m='1126900'>Hamming</span> <span m='1127290'>window</span> <span
  m='1127830'>applied</span> <span m='1128250'>to</span> <span
  m='1128400'>a</span> <span m='1128460'>low</span> <span
  m='1128640'>pass</span> <span m='1129030'>filter</span> <span
  m='1130410'>has</span> <span m='1130830'>considerably</span> <span
  m='1131550'>better</span> <span m='1132510'>stop</span> <span
  m='1133020'>band</span> <span m='1133230'>attenuation</span> <span
  m='1134670'>than</span> <span m='1134820'>either</span> <span
  m='1135090'>the</span> <span m='1135210'>rectangular</span> <span
  m='1136080'>or</span> <span m='1136290'>the</span> <span
  m='1136410'>Bartlett</span> <span m='1136830'>window.</span> <span
  m='1137490'>In</span> <span m='1137610'>particular,</span> <span
  m='1138150'>it</span> <span m='1138210'>comes</span> <span
  m='1138510'>down</span> <span m='1138840'>to</span> <span
  m='1138990'>about</span> <span m='1140010'>minus</span> <span
  m='1140430'>30</span> <span m='1140850'>or</span> <span
  m='1140940'>minus</span> <span m='1141300'>32</span> <span
  m='1141840'>or</span> <span m='1141960'>so</span> <span m='1142220'>dB.</span>
  </p><p><span m='1144300'>There</span> <span m='1144570'>is</span> <span
  m='1144750'>a</span> <span m='1144810'>slight</span> <span
  m='1145170'>price</span> <span m='1145530'>paid</span> <span
  m='1145830'>for</span> <span m='1146010'>this.</span> <span
  m='1146550'>And</span> <span m='1146730'>the</span> <span
  m='1147030'>price</span> <span m='1147345'>is,</span> <span
  m='1147660'>as</span> <span m='1147870'>you</span> <span
  m='1147960'>notice,</span> <span m='1149010'>that</span> <span
  m='1149520'>the</span> <span m='1149790'>transition</span> <span
  m='1150510'>band</span> <span m='1151320'>is</span> <span
  m='1151440'>slightly</span> <span m='1151920'>wider</span> <span
  m='1152970'>than</span> <span m='1153120'>it</span> <span
  m='1153240'>is</span> <span m='1153840'>for</span> <span
  m='1154080'>either</span> <span m='1154620'>of</span> <span
  m='1154770'>the</span> <span m='1154890'>other</span> <span
  m='1155100'>two</span> <span m='1155340'>windows.</span> <span
  m='1156900'>And</span> <span m='1157350'>in</span> <span
  m='1157530'>general,</span> <span m='1158770'>this</span> <span
  m='1159090'>is</span> <span m='1159690'>a</span> <span m='1160470'>type</span>
  <span m='1160800'>of</span> <span m='1160890'>trade</span> <span
  m='1161180'>off</span> <span m='1161970'>that</span> <span
  m='1162720'>arises</span> <span m='1163410'>again</span> <span
  m='1163770'>and</span> <span m='1163860'>again</span> <span
  m='1164850'>in</span> <span m='1165780'>the</span> <span
  m='1165870'>design</span> <span m='1166440'>of--</span> <span
  m='1166680'>actually,</span> <span m='1167250'>always</span> <span
  m='1167640'>in</span> <span m='1167730'>the</span> <span
  m='1167850'>design</span> <span m='1168510'>of</span> <span
  m='1168660'>digital</span> <span m='1169200'>or</span> <span
  m='1169440'>analog</span> <span m='1169890'>filters.</span> <span
  m='1170970'>In</span> <span m='1171060'>particular,</span> <span
  m='1171840'>in</span> <span m='1171990'>using</span> <span
  m='1172350'>windows,</span> <span m='1173370'>there</span> <span
  m='1173760'>is</span> <span m='1173970'>always</span> <span
  m='1174900'>this</span> <span m='1175080'>trade</span> <span
  m='1175180'>off</span> <span m='1176130'>between</span> <span
  m='1177510'>improved</span> <span m='1178290'>stop</span> <span
  m='1178740'>band</span> <span m='1178950'>attenuation</span> <span
  m='1180420'>and</span> <span m='1181110'>a</span> <span
  m='1181740'>narrower--</span> <span m='1182670'>or</span> <span
  m='1182820'>wider,</span> <span m='1183420'>rather--</span> <span
  m='1183750'>transition</span> <span m='1184320'>band.</span> <span
  m='1185070'>As</span> <span m='1186540'>you</span> <span
  m='1186900'>are</span> <span m='1187020'>willing</span> <span
  m='1187350'>to</span> <span m='1187500'>allow</span> <span
  m='1187800'>the</span> <span m='1187920'>transition</span> <span
  m='1188490'>band</span> <span m='1188790'>to</span> <span
  m='1188910'>become</span> <span m='1189630'>wider,</span> <span
  m='1190740'>you</span> <span m='1190920'>can</span> <span
  m='1191400'>generally</span> <span m='1191970'>obtain</span> <span
  m='1192360'>some</span> <span m='1192600'>advantage</span> <span
  m='1193260'>in</span> <span m='1193410'>terms</span> <span
  m='1193740'>of</span> <span m='1193800'>stop</span> <span
  m='1194190'>band</span> <span m='1194400'>attenuation.</span> </p><p><span
  m='1196720'>All</span> <span m='1196830'>right.</span> <span
  m='1197040'>So</span> <span m='1197610'>this</span> <span
  m='1198090'>is</span> <span m='1199170'>a</span> <span
  m='1199920'>quick</span> <span m='1200610'>view</span> <span
  m='1201120'>into</span> <span m='1201690'>the</span> <span
  m='1201810'>use</span> <span m='1202050'>of</span> <span
  m='1202200'>windows.</span> <span m='1203400'>In</span> <span
  m='1203490'>the</span> <span m='1203580'>text,</span> <span
  m='1204060'>in</span> <span m='1204180'>fact,</span> <span
  m='1204690'>there</span> <span m='1205050'>are</span> <span
  m='1205620'>quite</span> <span m='1205860'>a</span> <span
  m='1205890'>large</span> <span m='1206400'>number</span> <span
  m='1206760'>of</span> <span m='1206850'>windows</span> <span
  m='1207450'>that</span> <span m='1207600'>are</span> <span
  m='1207660'>discussed,</span> <span m='1208230'>besides</span> <span
  m='1208710'>the</span> <span m='1208800'>rectangular,</span> <span
  m='1210290'>the</span> <span m='1210390'>Bartlett,</span> <span
  m='1210990'>and</span> <span m='1211140'>the</span> <span
  m='1211230'>Hamming</span> <span m='1211620'>window.</span> <span
  m='1212580'>And</span> <span m='1213270'>similar</span> <span
  m='1215100'>frequency</span> <span m='1215670'>responses</span> <span
  m='1216630'>for</span> <span m='1217710'>filters</span> <span
  m='1218550'>designed</span> <span m='1219510'>using</span> <span
  m='1220170'>a</span> <span m='1220260'>variety</span> <span
  m='1220830'>of</span> <span m='1220950'>these</span> <span
  m='1221160'>windows</span> <span m='1221780'>is</span> <span
  m='1221880'>presented</span> <span m='1222360'>in</span> <span
  m='1222450'>the</span> <span m='1222540'>text.</span> </p><p><span
  m='1225740'>The</span> <span m='1226220'>next</span> <span
  m='1226820'>design</span> <span m='1227240'>procedure</span> <span
  m='1228230'>that</span> <span m='1228620'>I</span> <span
  m='1228740'>would</span> <span m='1228890'>like</span> <span
  m='1229130'>to</span> <span m='1229250'>discuss</span> <span
  m='1231140'>is</span> <span m='1231920'>the</span> <span
  m='1232430'>design</span> <span m='1232910'>procedure</span> <span
  m='1233810'>that</span> <span m='1234170'>is</span> <span
  m='1234410'>referred</span> <span m='1234830'>to</span> <span
  m='1235340'>as</span> <span m='1236390'>the</span> <span
  m='1236630'>frequency</span> <span m='1237200'>sampling</span> <span
  m='1238100'>design</span> <span m='1238520'>procedure.</span> <span
  m='1239720'>And</span> <span m='1239870'>basically,</span> <span
  m='1240950'>the</span> <span m='1241280'>idea</span> <span
  m='1242420'>behind</span> <span m='1242930'>that</span> <span
  m='1243140'>procedure</span> <span m='1244670'>is</span> <span
  m='1245180'>to</span> <span m='1245330'>argue</span> <span
  m='1247010'>that</span> <span m='1247430'>if</span> <span
  m='1247880'>we</span> <span m='1248090'>have</span> <span m='1249350'>a</span>
  <span m='1249500'>desired</span> <span m='1250400'>frequency</span> <span
  m='1251000'>response,</span> <span m='1251930'>which</span> <span
  m='1252170'>I've</span> <span m='1252290'>indicated</span> <span
  m='1253010'>by</span> <span m='1253730'>the</span> <span
  m='1253970'>continuous</span> <span m='1254600'>line--</span> <span
  m='1255620'>a</span> <span m='1255680'>desired</span> <span
  m='1256190'>frequency</span> <span m='1256730'>response--</span> <span
  m='1258260'>then</span> <span m='1259010'>we</span> <span
  m='1259220'>could</span> <span m='1259760'>think</span> <span
  m='1260090'>of</span> <span m='1260210'>designing</span> <span
  m='1260780'>a</span> <span m='1260840'>digital</span> <span
  m='1261230'>filter</span> <span m='1262430'>by</span> <span
  m='1263390'>specifying</span> <span m='1265430'>samples</span> <span
  m='1266540'>of</span> <span m='1267350'>the</span> <span
  m='1267830'>desired</span> <span m='1268400'>frequency</span> <span
  m='1268940'>response</span> <span m='1269980'>at</span> <span
  m='1270170'>equally</span> <span m='1270620'>spaced</span> <span
  m='1271010'>points</span> <span m='1271550'>along</span> <span
  m='1271880'>the</span> <span m='1271940'>frequency</span> <span
  m='1272480'>axis.</span> </p><p><span m='1273620'>Now</span> <span
  m='1274070'>we</span> <span m='1274250'>know</span> <span
  m='1274490'>that</span> <span m='1274610'>for</span> <span
  m='1274790'>a</span> <span m='1274850'>finite</span> <span
  m='1275240'>impulse</span> <span m='1275630'>response</span> <span
  m='1276110'>digital</span> <span m='1276470'>filter--</span> <span
  m='1277400'>in</span> <span m='1277490'>general,</span> <span
  m='1277850'>for</span> <span m='1278000'>any</span> <span
  m='1278150'>finite</span> <span m='1278570'>length</span> <span
  m='1278780'>sequence--</span> <span m='1279950'>we</span> <span
  m='1280070'>can</span> <span m='1280220'>represent</span> <span
  m='1280850'>it</span> <span m='1281540'>in</span> <span
  m='1281660'>terms</span> <span m='1282020'>of</span> <span
  m='1282110'>samples</span> <span m='1282950'>of</span> <span
  m='1283130'>its</span> <span m='1283520'>Fourier</span> <span
  m='1283700'>transform.</span> <span m='1284930'>That,</span> <span
  m='1285140'>in</span> <span m='1285230'>fact,</span> <span
  m='1285560'>is</span> <span m='1285710'>the</span> <span
  m='1285800'>discrete</span> <span m='1286190'>Fourier</span> <span
  m='1286610'>transform.</span> <span m='1288060'>So</span> <span
  m='1288170'>basically</span> <span m='1289040'>what</span> <span
  m='1289250'>we're</span> <span m='1289400'>saying</span> <span
  m='1290660'>is</span> <span m='1290810'>that</span> <span
  m='1290960'>we</span> <span m='1291170'>can</span> <span
  m='1291350'>begin</span> <span m='1291980'>with</span> <span
  m='1292460'>a</span> <span m='1292640'>desired</span> <span
  m='1293540'>frequency</span> <span m='1294290'>response</span> <span
  m='1296150'>and</span> <span m='1296300'>specify</span> <span
  m='1297530'>the</span> <span m='1297770'>discrete</span> <span
  m='1298220'>Fourier</span> <span m='1298610'>transform</span> <span
  m='1299660'>of</span> <span m='1299870'>the</span> <span
  m='1299990'>finite</span> <span m='1300380'>impulse</span> <span
  m='1300770'>response</span> <span m='1301250'>filter</span> <span
  m='1302060'>by</span> <span m='1302240'>specifying</span> <span
  m='1303260'>equally</span> <span m='1303650'>spaced</span> <span
  m='1304070'>samples</span> <span m='1305810'>of</span> <span
  m='1306410'>the</span> <span m='1306650'>desired</span> <span
  m='1307190'>frequency</span> <span m='1307700'>response.</span> <span
  m='1308780'>So</span> <span m='1309710'>we</span> <span
  m='1309860'>have</span> <span m='1310160'>then</span> <span
  m='1311510'>that</span> <span m='1311660'>the</span> <span
  m='1311810'>actual</span> <span m='1312290'>frequency</span> <span
  m='1312830'>response</span> <span m='1313880'>will</span> <span
  m='1314000'>correspond</span> <span m='1314840'>to</span> <span
  m='1315740'>capital</span> <span m='1316220'>N</span> <span
  m='1316770'>samples,</span> <span m='1317570'>equally</span> <span
  m='1317990'>spaced</span> <span m='1318440'>in</span> <span
  m='1318530'>frequency,</span> <span m='1319700'>of</span> <span
  m='1320300'>the</span> <span m='1320540'>desired</span> <span
  m='1321050'>frequency</span> <span m='1321560'>response</span> <span
  m='1322040'>characteristic.</span> </p><p><span m='1324690'>Now</span> <span
  m='1325610'>one</span> <span m='1326150'>could</span> <span
  m='1326810'>say</span> <span m='1328400'>that,</span> <span
  m='1329480'>or</span> <span m='1329630'>one</span> <span
  m='1329840'>could</span> <span m='1329990'>inquire</span> <span
  m='1330650'>as</span> <span m='1330890'>to</span> <span
  m='1331040'>whether,</span> <span m='1331400'>in</span> <span
  m='1331520'>fact,</span> <span m='1332370'>if</span> <span
  m='1332450'>we</span> <span m='1332570'>do</span> <span
  m='1332810'>that,</span> <span m='1333890'>what</span> <span
  m='1334100'>we're</span> <span m='1334310'>able</span> <span
  m='1334550'>to</span> <span m='1334700'>implement</span> <span
  m='1335540'>is</span> <span m='1336140'>the</span> <span
  m='1336320'>desired</span> <span m='1337820'>digital</span> <span
  m='1338180'>filter</span> <span m='1338570'>frequency</span> <span
  m='1339080'>response.</span> <span m='1340610'>In</span> <span
  m='1340700'>other</span> <span m='1340880'>words,</span> <span
  m='1341790'>we</span> <span m='1341810'>know</span> <span
  m='1342080'>that</span> <span m='1342230'>we</span> <span
  m='1342350'>can</span> <span m='1342500'>implement</span> <span
  m='1343250'>a</span> <span m='1343310'>finite</span> <span
  m='1343730'>impulse</span> <span m='1344120'>response</span> <span
  m='1344630'>filter</span> <span m='1346580'>by</span> <span
  m='1347360'>using</span> <span m='1348110'>only</span> <span
  m='1349820'>the</span> <span m='1350270'>values</span> <span
  m='1350900'>specified</span> <span m='1351860'>in</span> <span
  m='1352040'>the</span> <span m='1352130'>discrete</span> <span
  m='1352520'>Fourier</span> <span m='1352940'>transform.</span> <span
  m='1354440'>And</span> <span m='1354770'>here</span> <span
  m='1355250'>we've</span> <span m='1355430'>specified</span> <span
  m='1356350'>a</span> <span m='1356420'>discrete</span> <span
  m='1356840'>Fourier</span> <span m='1357360'>transform</span> <span
  m='1358450'>that's</span> <span m='1358670'>unity</span> <span
  m='1359120'>in</span> <span m='1359210'>the</span> <span
  m='1359300'>pass</span> <span m='1359710'>band</span> <span
  m='1360650'>and</span> <span m='1360800'>it's</span> <span
  m='1360920'>zero</span> <span m='1361370'>in</span> <span
  m='1361460'>the</span> <span m='1361550'>stop</span> <span
  m='1361940'>band.</span> </p><p><span m='1362990'>And</span> <span
  m='1363110'>one</span> <span m='1363320'>can</span> <span
  m='1363500'>ask,</span> <span m='1363770'>well,</span> <span
  m='1364610'>in</span> <span m='1364760'>fact,</span> <span
  m='1365390'>is</span> <span m='1365660'>that</span> <span
  m='1366260'>an</span> <span m='1366410'>ideal</span> <span
  m='1367640'>digital</span> <span m='1368030'>low</span> <span
  m='1368210'>pass</span> <span m='1368540'>filter?</span> <span
  m='1370440'>Well,</span> <span m='1370550'>the</span> <span
  m='1370730'>answer</span> <span m='1371000'>to</span> <span
  m='1371120'>that</span> <span m='1371600'>is</span> <span
  m='1371780'>no.</span> <span m='1373020'>And</span> <span
  m='1373040'>the</span> <span m='1373160'>reason</span> <span
  m='1373610'>is</span> <span m='1374420'>that</span> <span
  m='1375410'>it</span> <span m='1375650'>is</span> <span
  m='1376040'>important,</span> <span m='1377090'>very</span> <span
  m='1377360'>important</span> <span m='1377930'>to</span> <span
  m='1378080'>keep</span> <span m='1378350'>track</span> <span
  m='1378710'>of</span> <span m='1378800'>the</span> <span
  m='1378920'>fact</span> <span m='1379850'>that</span> <span
  m='1381110'>just</span> <span m='1381470'>because</span> <span
  m='1382670'>we</span> <span m='1382820'>specify</span> <span
  m='1384350'>the</span> <span m='1384560'>frequency</span> <span
  m='1385160'>response</span> <span m='1386350'>at</span> <span
  m='1386600'>equally</span> <span m='1387050'>spaced</span> <span
  m='1387440'>points</span> <span m='1388310'>along</span> <span
  m='1388610'>the</span> <span m='1388700'>frequency</span> <span
  m='1389270'>axis</span> <span m='1391040'>doesn't</span> <span
  m='1391430'>mean</span> <span m='1392390'>that,</span> <span
  m='1393050'>in</span> <span m='1393250'>between</span> <span
  m='1393740'>those</span> <span m='1394010'>points,</span> <span
  m='1394970'>the</span> <span m='1395210'>frequency</span> <span
  m='1395750'>characteristic</span> <span m='1396500'>has</span> <span
  m='1396770'>to</span> <span m='1396890'>be</span> <span
  m='1397040'>particularly</span> <span m='1397700'>well-behaved.</span>
  </p><p><span m='1398900'>That</span> <span m='1399110'>is,</span> <span
  m='1400130'>the</span> <span m='1401240'>Fourier</span> <span
  m='1401860'>transform</span> <span m='1402650'>of</span> <span
  m='1402740'>the</span> <span m='1402830'>unit</span> <span
  m='1403130'>sample</span> <span m='1403520'>response</span> <span
  m='1404840'>is</span> <span m='1404990'>a</span> <span
  m='1405080'>continuous</span> <span m='1405740'>function</span> <span
  m='1406160'>of</span> <span m='1406220'>frequency.</span> <span
  m='1407720'>We're</span> <span m='1407910'>specifying</span> <span
  m='1408680'>samples</span> <span m='1409580'>of</span> <span
  m='1409700'>that</span> <span m='1409910'>continuous</span> <span
  m='1410480'>function</span> <span m='1410870'>of</span> <span
  m='1410930'>frequency.</span> <span m='1412290'>And</span> <span
  m='1413390'>there</span> <span m='1414050'>is</span> <span
  m='1414260'>implied</span> <span m='1415070'>an</span> <span
  m='1415250'>interpolation</span> <span m='1416390'>in</span> <span
  m='1416705'>between</span> <span m='1417020'>those</span> <span
  m='1417200'>samples.</span> <span m='1419620'>Well,</span> <span
  m='1420250'>in</span> <span m='1420370'>fact,</span> <span
  m='1420980'>if</span> <span m='1421300'>we</span> <span
  m='1421570'>were</span> <span m='1421900'>to</span> <span
  m='1422080'>look</span> <span m='1422410'>at</span> <span m='1422860'>a</span>
  <span m='1423010'>unit</span> <span m='1423340'>sample</span> <span
  m='1423730'>response</span> <span m='1424840'>whose</span> <span
  m='1427610'>discrete</span> <span m='1428300'>Fourier</span> <span
  m='1428420'>transform</span> <span m='1429020'>magnitude</span> <span
  m='1430700'>is</span> <span m='1431300'>unity</span> <span
  m='1431810'>in</span> <span m='1431900'>the</span> <span
  m='1431990'>pass</span> <span m='1432380'>band</span> <span
  m='1433220'>and</span> <span m='1433370'>zero</span> <span
  m='1433760'>in</span> <span m='1433850'>the</span> <span
  m='1433940'>stop</span> <span m='1434380'>band,</span> <span
  m='1435540'>one</span> <span m='1435770'>possible</span> <span
  m='1436340'>choice,</span> <span m='1436980'>in</span> <span
  m='1437030'>fact,</span> <span m='1438530'>is</span> <span
  m='1439550'>the</span> <span m='1440870'>unit</span> <span
  m='1441170'>sample</span> <span m='1441590'>response</span> <span
  m='1442340'>and</span> <span m='1442460'>frequency</span> <span
  m='1443000'>response</span> <span m='1443510'>that</span> <span
  m='1443600'>I've</span> <span m='1443750'>indicated</span> <span
  m='1444290'>here.</span> </p><p><span m='1445790'>This</span> <span
  m='1446000'>is</span> <span m='1446120'>the</span> <span
  m='1446240'>unit</span> <span m='1446480'>sample</span> <span
  m='1446900'>response.</span> <span m='1449310'>This</span> <span
  m='1449480'>is</span> <span m='1450050'>the</span> <span
  m='1450200'>corresponding</span> <span m='1450920'>frequency</span> <span
  m='1451460'>response.</span> <span m='1452770'>The</span> <span
  m='1452970'>discrete</span> <span m='1453410'>Fourier</span> <span
  m='1453810'>transform</span> <span m='1454730'>of</span> <span
  m='1454880'>h</span> <span m='1455120'>of</span> <span m='1455230'>n,</span>
  <span m='1456640'>in</span> <span m='1456800'>fact,</span> <span
  m='1457400'>is</span> <span m='1457610'>exactly</span> <span
  m='1458150'>unity</span> <span m='1458600'>in</span> <span
  m='1458690'>the</span> <span m='1458780'>pass</span> <span
  m='1459140'>band</span> <span m='1459580'>and</span> <span
  m='1459800'>zero</span> <span m='1460190'>in</span> <span
  m='1460280'>the</span> <span m='1460370'>stop</span> <span
  m='1460730'>band.</span> <span m='1461720'>But</span> <span
  m='1462590'>the</span> <span m='1462800'>interpolation</span> <span
  m='1463610'>in</span> <span m='1463780'>between</span> <span
  m='1464180'>those</span> <span m='1464420'>points</span> <span
  m='1464960'>is</span> <span m='1465140'>not</span> <span
  m='1465350'>unity</span> <span m='1465800'>in</span> <span
  m='1465890'>the</span> <span m='1465980'>pass</span> <span
  m='1466310'>band</span> <span m='1466840'>and</span> <span
  m='1466970'>zero</span> <span m='1467330'>in</span> <span
  m='1467420'>the</span> <span m='1467510'>stop</span> <span
  m='1467840'>band.</span> <span m='1468710'>In</span> <span
  m='1468830'>fact,</span> <span m='1469640'>by</span> <span
  m='1470540'>simply</span> <span m='1471080'>putting</span> <span
  m='1471920'>the</span> <span m='1472040'>previous</span> <span
  m='1472550'>view</span> <span m='1472760'>graph</span> <span
  m='1473840'>on</span> <span m='1473990'>top</span> <span m='1474350'>of</span>
  <span m='1474470'>this</span> <span m='1474710'>one,</span> <span
  m='1479640'>we</span> <span m='1479690'>can</span> <span
  m='1479870'>see</span> <span m='1480740'>that</span> <span
  m='1482060'>this</span> <span m='1482690'>frequency</span> <span
  m='1483290'>response</span> <span m='1483800'>characteristic</span> <span
  m='1485180'>indeed</span> <span m='1486170'>goes</span> <span
  m='1486680'>through</span> <span m='1487850'>the</span> <span
  m='1487970'>specified</span> <span m='1489980'>frequency</span> <span
  m='1490580'>points.</span> </p><p><span m='1492050'>But</span> <span
  m='1492770'>it</span> <span m='1493190'>is</span> <span m='1494180'>not</span>
  <span m='1494480'>particularly</span> <span m='1495650'>well</span> <span
  m='1495920'>constrained</span> <span m='1496760'>in</span> <span
  m='1496930'>between</span> <span m='1497360'>those</span> <span
  m='1497630'>points.</span> <span m='1499020'>So,</span> <span
  m='1499850'>in</span> <span m='1499940'>fact,</span> <span
  m='1500560'>for</span> <span m='1501500'>one</span> <span
  m='1501710'>example,</span> <span m='1502530'>if</span> <span
  m='1502610'>we</span> <span m='1502700'>chose</span> <span
  m='1503120'>this</span> <span m='1503390'>as</span> <span
  m='1503510'>the</span> <span m='1503600'>unit</span> <span
  m='1503870'>sample</span> <span m='1504260'>response</span> <span
  m='1505460'>corresponding</span> <span m='1506180'>to</span> <span
  m='1506300'>this</span> <span m='1506480'>set</span> <span
  m='1506690'>of</span> <span m='1506780'>frequency</span> <span
  m='1507350'>samples,</span> <span m='1508580'>the</span> <span
  m='1508910'>resulting</span> <span m='1509480'>frequency</span> <span
  m='1509990'>response</span> <span m='1510770'>of</span> <span
  m='1511220'>the</span> <span m='1511310'>finite</span> <span
  m='1511700'>impulse</span> <span m='1512060'>response</span> <span
  m='1512540'>low</span> <span m='1512720'>pass</span> <span
  m='1513080'>filter</span> <span m='1514010'>would</span> <span
  m='1514160'>be</span> <span m='1514610'>as</span> <span
  m='1515690'>we've</span> <span m='1516050'>indicated</span> <span
  m='1516920'>with</span> <span m='1517490'>this</span> <span
  m='1517670'>continuous</span> <span m='1518270'>curve.</span> </p><p><span
  m='1520770'>Well,</span> <span m='1521600'>we</span> <span
  m='1521750'>know</span> <span m='1522080'>that</span> <span
  m='1522470'>there</span> <span m='1522710'>are</span> <span
  m='1522800'>other</span> <span m='1523010'>unit</span> <span
  m='1523310'>sample</span> <span m='1523730'>responses</span> <span
  m='1525500'>whose</span> <span m='1525710'>discrete</span> <span
  m='1526150'>Fourier</span> <span m='1526550'>transforms</span> <span
  m='1527420'>are</span> <span m='1527630'>exactly</span> <span
  m='1528170'>the</span> <span m='1528260'>same.</span> <span
  m='1529430'>The</span> <span m='1529550'>magnitude</span> <span
  m='1530060'>of</span> <span m='1530120'>the</span> <span
  m='1530210'>discrete</span> <span m='1530540'>Fourier</span> <span
  m='1530810'>transform</span> <span m='1531290'>is</span> <span
  m='1531410'>exactly</span> <span m='1531830'>the</span> <span
  m='1531950'>same</span> <span m='1532400'>as</span> <span
  m='1532580'>this</span> <span m='1532820'>one.</span> <span
  m='1533960'>In</span> <span m='1534050'>particular,</span> <span
  m='1534690'>we</span> <span m='1534740'>know</span> <span
  m='1535070'>that</span> <span m='1535250'>if</span> <span
  m='1535400'>we</span> <span m='1535520'>were</span> <span
  m='1535670'>to</span> <span m='1535820'>circularly</span> <span
  m='1536510'>rotate</span> <span m='1537840'>h of n,</span> <span
  m='1539750'>circularly</span> <span m='1540290'>shift</span> <span
  m='1540760'>h</span> <span m='1541155'>of</span> <span m='1541550'>n,</span>
  <span m='1542540'>the</span> <span m='1542630'>magnitude</span> <span
  m='1543470'>of</span> <span m='1543620'>the</span> <span
  m='1543710'>discrete</span> <span m='1544100'>Fourier</span> <span
  m='1544490'>transform</span> <span m='1545690'>would</span> <span
  m='1545840'>remain</span> <span m='1546200'>exactly</span> <span
  m='1546680'>the</span> <span m='1546770'>same.</span> </p><p><span
  m='1547920'>So</span> <span m='1548270'>in</span> <span
  m='1548390'>fact,</span> <span m='1548930'>another</span> <span
  m='1549290'>unit</span> <span m='1549590'>sample</span> <span
  m='1549980'>response</span> <span m='1551420'>that</span> <span
  m='1551840'>would</span> <span m='1552050'>correspond</span> <span
  m='1552950'>to</span> <span m='1553970'>a</span> <span
  m='1554600'>frequency</span> <span m='1555110'>response,</span> <span
  m='1555950'>which</span> <span m='1556370'>likewise</span> <span
  m='1557060'>goes</span> <span m='1557330'>through</span> <span
  m='1557540'>the</span> <span m='1557690'>same</span> <span
  m='1558350'>frequency</span> <span m='1558890'>samples,</span> <span
  m='1560690'>is</span> <span m='1561710'>the</span> <span
  m='1561830'>one</span> <span m='1562910'>that</span> <span
  m='1563930'>we</span> <span m='1564110'>have</span> <span
  m='1564740'>here.</span> <span m='1567580'>This</span> <span
  m='1567790'>unit</span> <span m='1568060'>sample</span> <span
  m='1568480'>response</span> <span m='1569080'>is</span> <span
  m='1569140'>simply</span> <span m='1569530'>the</span> <span
  m='1569620'>previous</span> <span m='1570160'>one,</span> <span
  m='1570880'>circularly</span> <span m='1571960'>shifted</span> <span
  m='1572860'>by</span> <span m='1573460'>approximately</span> <span
  m='1574300'>n</span> <span m='1574420'>over</span> <span m='1574690'>2,</span>
  <span m='1575170'>or</span> <span m='1575500'>n minus</span> <span
  m='1575860'>1</span> <span m='1576040'>over</span> <span m='1576310'>2.</span>
  <span m='1577330'>And</span> <span m='1577480'>in</span> <span
  m='1577570'>this</span> <span m='1577780'>case,</span> <span
  m='1578600'>the</span> <span m='1578890'>frequency</span> <span
  m='1579400'>response</span> <span m='1579880'>characteristic</span> <span
  m='1580780'>is</span> <span m='1581020'>even</span> <span
  m='1581350'>worse</span> <span m='1581920'>than</span> <span
  m='1582070'>it</span> <span m='1582160'>was</span> <span m='1582700'>in</span>
  <span m='1582820'>the</span> <span m='1582910'>previous</span> <span
  m='1583420'>example.</span> </p><p><span m='1584750'>So</span> <span
  m='1585310'>here</span> <span m='1585610'>we</span> <span
  m='1585790'>have</span> <span m='1586000'>a</span> <span
  m='1586060'>frequency</span> <span m='1586540'>response</span> <span
  m='1587290'>that</span> <span m='1587530'>has</span> <span
  m='1587800'>very</span> <span m='1588070'>wild,</span> <span
  m='1589150'>large</span> <span m='1589480'>fluctuations</span> <span
  m='1590380'>in</span> <span m='1590470'>the</span> <span
  m='1590530'>pass</span> <span m='1590870'>band,</span> <span
  m='1591790'>and</span> <span m='1592000'>even</span> <span
  m='1592300'>in</span> <span m='1592390'>the</span> <span
  m='1592480'>stop</span> <span m='1592870'>band,</span> <span
  m='1594850'>but</span> <span m='1595450'>still</span> <span
  m='1595960'>goes</span> <span m='1596350'>through</span> <span
  m='1596920'>the</span> <span m='1597070'>same</span> <span
  m='1597910'>frequency</span> <span m='1598450'>samples</span> <span
  m='1599410'>that</span> <span m='1599770'>we</span> <span
  m='1599950'>had</span> <span m='1600070'>specified</span> <span
  m='1600730'>previously.</span> <span m='1602210'>And</span> <span
  m='1602830'>we</span> <span m='1602980'>can</span> <span
  m='1603130'>see</span> <span m='1603400'>that</span> <span
  m='1603970'>by,</span> <span m='1604870'>again,</span> <span
  m='1605830'>putting</span> <span m='1606160'>these</span> <span
  m='1606410'>two</span> <span m='1606940'>on</span> <span
  m='1607090'>top</span> <span m='1607420'>of</span> <span
  m='1607540'>each</span> <span m='1607750'>other.</span> <span
  m='1614240'>And</span> <span m='1614830'>you</span> <span
  m='1615010'>can</span> <span m='1615160'>see,</span> <span
  m='1615670'>in</span> <span m='1615790'>this</span> <span
  m='1615970'>case</span> <span m='1616420'>again,</span> <span
  m='1617560'>that</span> <span m='1618100'>this</span> <span
  m='1618310'>frequency</span> <span m='1619450'>characteristic</span> <span
  m='1620770'>goes</span> <span m='1621130'>through</span> <span
  m='1622180'>the</span> <span m='1622300'>specified</span> <span
  m='1623470'>frequency</span> <span m='1624070'>samples.</span> <span
  m='1625330'>But</span> <span m='1625750'>it</span> <span
  m='1625900'>has</span> <span m='1626450'>a</span> <span
  m='1626530'>very</span> <span m='1626860'>wild</span> <span
  m='1627370'>behavior</span> <span m='1628240'>in</span> <span
  m='1628410'>between.</span> </p><p><span m='1630400'>All</span> <span
  m='1630490'>right.</span> <span m='1630670'>So</span> <span
  m='1631180'>the</span> <span m='1631270'>frequency</span> <span
  m='1631750'>sampling</span> <span m='1632560'>method,</span> <span
  m='1632920'>then,</span> <span m='1633640'>is</span> <span
  m='1633940'>basically</span> <span m='1634750'>a</span> <span
  m='1634840'>method</span> <span m='1635800'>that</span> <span
  m='1636520'>consists</span> <span m='1637120'>of</span> <span
  m='1637570'>specifying</span> <span m='1638800'>samples</span> <span
  m='1639550'>of</span> <span m='1639730'>the</span> <span
  m='1639820'>frequency</span> <span m='1640330'>response,</span> <span
  m='1642460'>and</span> <span m='1643360'>then</span> <span
  m='1644650'>accepting</span> <span m='1645640'>the</span> <span
  m='1645790'>interpolation</span> <span m='1646860'>in</span> <span
  m='1646980'>between</span> <span m='1647500'>those</span> <span
  m='1647710'>samples</span> <span m='1648850'>that</span> <span
  m='1649240'>is</span> <span m='1649420'>dictated</span> <span
  m='1650290'>by</span> <span m='1651220'>the</span> <span
  m='1651430'>form</span> <span m='1652090'>of</span> <span
  m='1652270'>the</span> <span m='1652390'>unit</span> <span
  m='1652630'>sample</span> <span m='1653020'>response.</span> <span
  m='1654040'>And</span> <span m='1654250'>I</span> <span
  m='1654340'>stress</span> <span m='1655000'>that</span> <span
  m='1655660'>one</span> <span m='1655870'>has</span> <span
  m='1656110'>to</span> <span m='1656230'>be</span> <span
  m='1656320'>careful</span> <span m='1657070'>in</span> <span
  m='1657700'>the</span> <span m='1657820'>phase</span> <span
  m='1658570'>that's</span> <span m='1658780'>applied</span> <span
  m='1659230'>to</span> <span m='1659380'>this,</span> <span
  m='1659740'>or</span> <span m='1659920'>equivalently,</span> <span
  m='1660550'>the</span> <span m='1660670'>circular</span> <span
  m='1661120'>shift</span> <span m='1661960'>that's</span> <span
  m='1662140'>applied</span> <span m='1662530'>to</span> <span
  m='1662650'>the</span> <span m='1662740'>unit</span> <span
  m='1663010'>sample</span> <span m='1663400'>response,</span> <span
  m='1664390'>since</span> <span m='1664690'>as</span> <span
  m='1664840'>we've</span> <span m='1664960'>seen</span> <span
  m='1665290'>in</span> <span m='1665380'>the</span> <span
  m='1665470'>last</span> <span m='1666310'>several</span> <span
  m='1666610'>view</span> <span m='1666910'>graphs,</span> <span
  m='1667750'>that</span> <span m='1668080'>very</span> <span
  m='1668350'>seriously</span> <span m='1669160'>affects</span> <span
  m='1669940'>the</span> <span m='1670030'>interpolation</span> <span
  m='1670386'>in</span> <span m='1671100'>between</span> <span
  m='1672040'>these</span> <span m='1672250'>frequency</span> <span
  m='1672760'>points.</span> </p><p><span m='1673810'>Furthermore,</span> <span
  m='1674320'>an</span> <span m='1674410'>additional</span> <span
  m='1674830'>point</span> <span m='1675970'>has</span> <span
  m='1676150'>been</span> <span m='1676330'>made,</span> <span
  m='1677170'>and</span> <span m='1677290'>that</span> <span
  m='1677530'>is</span> <span m='1678220'>that</span> <span
  m='1679600'>it</span> <span m='1679930'>is</span> <span
  m='1680170'>not--</span> <span m='1680620'>even</span> <span
  m='1680950'>though</span> <span m='1681190'>we</span> <span
  m='1681310'>can</span> <span m='1681490'>implement</span> <span
  m='1683110'>a</span> <span m='1683200'>finite</span> <span
  m='1683650'>impulse</span> <span m='1684040'>response</span> <span
  m='1684520'>filter</span> <span m='1685540'>using</span> <span
  m='1686080'>the</span> <span m='1686170'>discrete</span> <span
  m='1686590'>Fourier</span> <span m='1687010'>transform,</span> <span
  m='1688870'>specifying</span> <span m='1690340'>the</span> <span
  m='1690580'>discrete</span> <span m='1690970'>Fourier</span> <span
  m='1691440'>transform</span> <span m='1691990'>to</span> <span
  m='1692110'>be</span> <span m='1692200'>unity</span> <span
  m='1692620'>in</span> <span m='1692710'>the</span> <span
  m='1692800'>pass</span> <span m='1693160'>band</span> <span
  m='1694000'>and</span> <span m='1694150'>zero</span> <span
  m='1694540'>in</span> <span m='1694620'>the</span> <span
  m='1694720'>stop</span> <span m='1695140'>band</span> <span
  m='1696550'>does</span> <span m='1696760'>not</span> <span
  m='1697060'>mean</span> <span m='1697810'>that</span> <span
  m='1698110'>we've</span> <span m='1698320'>implemented</span> <span
  m='1699190'>an</span> <span m='1699340'>ideal</span> <span
  m='1699790'>low</span> <span m='1699970'>pass</span> <span
  m='1700330'>filter.</span> </p><p><span m='1702820'>All</span> <span
  m='1702910'>right.</span> <span m='1703190'>Well,</span> <span
  m='1703930'>we</span> <span m='1704140'>had--</span> <span
  m='1704950'>this,</span> <span m='1705190'>of</span> <span
  m='1705280'>course,</span> <span m='1705640'>is</span> <span
  m='1705760'>not</span> <span m='1705970'>a</span> <span
  m='1706030'>unit</span> <span m='1706330'>sample</span> <span
  m='1706720'>response</span> <span m='1707290'>that</span> <span
  m='1707410'>we</span> <span m='1707620'>would</span> <span
  m='1707800'>be</span> <span m='1708190'>particularly</span> <span
  m='1709000'>anxious</span> <span m='1709450'>to</span> <span
  m='1709600'>use.</span> <span m='1710920'>Clearly,</span> <span
  m='1711400'>the</span> <span m='1711520'>behavior</span> <span
  m='1711970'>in</span> <span m='1712030'>the</span> <span
  m='1712120'>pass</span> <span m='1712450'>band</span> <span
  m='1712660'>and</span> <span m='1712750'>stop</span> <span
  m='1713140'>band</span> <span m='1713980'>is</span> <span
  m='1714130'>very</span> <span m='1714370'>severe,</span> <span
  m='1715030'>and</span> <span m='1715150'>in</span> <span
  m='1715210'>fact,</span> <span m='1715480'>too</span> <span
  m='1715660'>severe.</span> <span m='1716830'>So</span> <span
  m='1717550'>we</span> <span m='1717730'>could</span> <span
  m='1718330'>at</span> <span m='1718450'>least</span> <span
  m='1718720'>consider</span> <span m='1719200'>as</span> <span
  m='1719280'>somewhat</span> <span m='1719740'>reasonable</span> <span
  m='1721210'>the</span> <span m='1721410'>unit</span> <span
  m='1721690'>sample</span> <span m='1722080'>response</span> <span
  m='1723190'>and</span> <span m='1723280'>frequency</span> <span
  m='1723790'>response</span> <span m='1724690'>that</span> <span
  m='1725110'>we</span> <span m='1725380'>had</span> <span
  m='1725770'>previously,</span> <span m='1726730'>in</span> <span
  m='1726850'>this</span> <span m='1727060'>case,</span> <span
  m='1728560'>relatively</span> <span m='1729160'>well-behaved.</span> <span
  m='1729910'>That</span> <span m='1730090'>is,</span> <span
  m='1730690'>it</span> <span m='1730840'>ripples</span> <span
  m='1731170'>somewhat</span> <span m='1731590'>in</span> <span
  m='1731680'>the</span> <span m='1731740'>pass</span> <span
  m='1732100'>band</span> <span m='1732400'>and</span> <span
  m='1732685'>in</span> <span m='1732970'>the</span> <span
  m='1733060'>stop</span> <span m='1733420'>band.</span> <span
  m='1735130'>But</span> <span m='1735310'>now</span> <span
  m='1735580'>we</span> <span m='1735760'>could</span> <span
  m='1736120'>inquire</span> <span m='1736840'>as</span> <span
  m='1737050'>to</span> <span m='1737200'>whether</span> <span
  m='1737920'>there</span> <span m='1738340'>is</span> <span
  m='1738460'>some</span> <span m='1738760'>way</span> <span
  m='1739180'>of</span> <span m='1739660'>improving</span> <span
  m='1741130'>the</span> <span m='1741370'>pass</span> <span
  m='1741790'>band</span> <span m='1742480'>ripple</span> <span
  m='1743500'>and</span> <span m='1744190'>the</span> <span
  m='1744310'>stop</span> <span m='1744700'>band</span> <span
  m='1744940'>ripple.</span> </p><p><span m='1746320'>We</span> <span
  m='1746470'>know,</span> <span m='1746980'>or</span> <span
  m='1747190'>we</span> <span m='1747340'>anticipate,</span> <span
  m='1748540'>that</span> <span m='1748660'>there's</span> <span
  m='1748840'>a</span> <span m='1748930'>price</span> <span
  m='1749260'>that</span> <span m='1749380'>we</span> <span
  m='1749500'>would</span> <span m='1749650'>have</span> <span
  m='1749830'>to</span> <span m='1749950'>pay</span> <span
  m='1750160'>for</span> <span m='1750340'>that.</span> <span
  m='1751240'>Probably</span> <span m='1752260'>the</span> <span
  m='1752380'>price,</span> <span m='1753070'>and</span> <span
  m='1753250'>indeed</span> <span m='1753700'>it</span> <span
  m='1753790'>turns</span> <span m='1754060'>out</span> <span
  m='1754450'>that</span> <span m='1754720'>the</span> <span
  m='1754810'>price</span> <span m='1755110'>we</span> <span
  m='1755260'>have</span> <span m='1755470'>to</span> <span
  m='1755590'>pay</span> <span m='1756400'>is</span> <span
  m='1757000'>the</span> <span m='1757120'>price</span> <span
  m='1757660'>of</span> <span m='1758080'>widening</span> <span
  m='1759010'>the</span> <span m='1759100'>transition</span> <span
  m='1759700'>band.</span> <span m='1760780'>Well,</span> <span
  m='1761170'>how</span> <span m='1761350'>could</span> <span
  m='1761530'>we</span> <span m='1761680'>widen</span> <span
  m='1762010'>the</span> <span m='1762100'>transition</span> <span
  m='1762700'>band?</span> <span m='1763480'>We</span> <span
  m='1763630'>could</span> <span m='1763840'>imagine</span> <span
  m='1764500'>beginning</span> <span m='1765220'>with</span> <span
  m='1765430'>this</span> <span m='1765640'>particular</span> <span
  m='1766210'>design,</span> <span m='1768080'>taking</span> <span
  m='1768520'>as</span> <span m='1769120'>one</span> <span
  m='1769510'>possibility</span> <span m='1771010'>one</span> <span
  m='1771430'>of</span> <span m='1771760'>the</span> <span
  m='1772060'>stop</span> <span m='1772600'>band</span> <span
  m='1773890'>constrained</span> <span m='1774460'>points.</span> <span
  m='1775660'>And</span> <span m='1776380'>allow</span> <span
  m='1776860'>it</span> <span m='1777250'>to</span> <span
  m='1777400'>move</span> <span m='1777700'>into</span> <span
  m='1777970'>the</span> <span m='1778090'>transition</span> <span
  m='1778720'>band</span> <span m='1779620'>so</span> <span
  m='1779830'>that,</span> <span m='1780220'>in</span> <span
  m='1780340'>fact,</span> <span m='1780790'>we</span> <span
  m='1781030'>have</span> <span m='1781450'>a</span> <span
  m='1781570'>wider</span> <span m='1782440'>frequency</span> <span
  m='1782980'>range</span> <span m='1783670'>that</span> <span
  m='1783880'>we're</span> <span m='1784060'>permitting</span> <span
  m='1784510'>the</span> <span m='1784600'>transition</span> <span
  m='1785350'>from</span> <span m='1785940'>pass</span> <span
  m='1786260'>band</span> <span m='1787210'>to</span> <span
  m='1787300'>stop</span> <span m='1787750'>band</span> <span
  m='1788370'>to</span> <span m='1788490'>go</span> <span m='1788710'>to.</span>
  </p><p><span m='1790360'>And</span> <span m='1791530'>let</span> <span
  m='1791680'>me</span> <span m='1791980'>illustrate</span> <span
  m='1792550'>that</span> <span m='1795730'>here,</span> <span
  m='1797500'>where</span> <span m='1798220'>now</span> <span
  m='1798940'>what</span> <span m='1799270'>we've</span> <span
  m='1799510'>done</span> <span m='1800800'>is</span> <span
  m='1801610'>to</span> <span m='1801760'>take</span> <span
  m='1811460'>one</span> <span m='1812000'>of</span> <span
  m='1812570'>the</span> <span m='1812870'>frequency</span> <span
  m='1813470'>samples</span> <span m='1815030'>in</span> <span
  m='1815180'>the</span> <span m='1815280'>stop</span> <span
  m='1815710'>band,</span> <span m='1817400'>move</span> <span
  m='1817730'>it</span> <span m='1817850'>up</span> <span
  m='1818090'>into</span> <span m='1818420'>the</span> <span
  m='1818540'>transition</span> <span m='1819170'>band.</span> <span
  m='1820790'>And</span> <span m='1821240'>as</span> <span m='1821510'>we</span>
  <span m='1821660'>do</span> <span m='1821900'>that,</span> <span
  m='1822510'>you</span> <span m='1822560'>can</span> <span
  m='1822740'>see</span> <span m='1823250'>for</span> <span
  m='1823400'>this</span> <span m='1823760'>particular</span> <span
  m='1824270'>example,</span> <span m='1825410'>the</span> <span
  m='1826490'>pass band</span> <span m='1827090'>ripple</span> <span
  m='1827390'>hasn't</span> <span m='1827720'>changed</span> <span
  m='1828320'>too</span> <span m='1828500'>much.</span> <span
  m='1829550'>But</span> <span m='1830030'>in</span> <span
  m='1830150'>fact,</span> <span m='1830450'>the</span> <span
  m='1830570'>stop</span> <span m='1830960'>band</span> <span
  m='1831140'>ripple</span> <span m='1831590'>has</span> <span
  m='1831800'>changed</span> <span m='1832340'>somewhat</span> <span
  m='1832760'>dramatically.</span> </p><p><span m='1834380'>As</span> <span
  m='1835070'>we</span> <span m='1835460'>allow</span> <span
  m='1835790'>this</span> <span m='1835940'>transition</span> <span
  m='1836570'>point</span> <span m='1837440'>to</span> <span
  m='1837560'>move</span> <span m='1837770'>farther</span> <span
  m='1838310'>up</span> <span m='1838490'>into</span> <span
  m='1838700'>the</span> <span m='1838790'>transition</span> <span
  m='1839420'>band,</span> <span m='1839750'>basically</span> <span
  m='1840320'>widening</span> <span m='1841430'>the</span> <span
  m='1841610'>general</span> <span m='1842000'>pass band</span> <span
  m='1842630'>region,</span> <span m='1843590'>what</span> <span
  m='1843740'>we'll</span> <span m='1843890'>see</span> <span
  m='1844370'>is</span> <span m='1844640'>that</span> <span
  m='1845330'>the</span> <span m='1845690'>pass band</span> <span
  m='1846105'>ripple</span> <span m='1847190'>become</span> <span
  m='1847550'>somewhat</span> <span m='1848000'>smaller.</span> <span
  m='1848990'>And</span> <span m='1849350'>there,</span> <span
  m='1849650'>in</span> <span m='1849770'>fact,</span> <span
  m='1850130'>is</span> <span m='1850280'>a</span> <span
  m='1850370'>trade</span> <span m='1850745'>off</span> <span
  m='1851420'>that</span> <span m='1851810'>is</span> <span
  m='1851990'>introduced</span> <span m='1852620'>between</span> <span
  m='1853430'>the</span> <span m='1853610'>pass band</span> <span
  m='1854240'>ripple</span> <span m='1854840'>and</span> <span
  m='1855170'>the</span> <span m='1855290'>stop</span> <span
  m='1855680'>band</span> <span m='1855890'>ripple.</span> <span
  m='1856760'>And</span> <span m='1857270'>let</span> <span
  m='1857450'>me</span> <span m='1857600'>illustrate</span> <span
  m='1858110'>that</span> <span m='1860570'>with</span> <span
  m='1861110'>this</span> <span m='1861410'>next</span> <span
  m='1862010'>example,</span> <span m='1864140'>where</span> <span
  m='1864620'>in</span> <span m='1864800'>this</span> <span
  m='1864980'>case,</span> <span m='1866210'>we</span> <span
  m='1866540'>have</span> <span m='1866840'>moved</span> <span
  m='1867110'>the</span> <span m='1867410'>transition</span> <span
  m='1868070'>point</span> <span m='1868640'>up</span> <span
  m='1869870'>somewhat</span> <span m='1870290'>further.</span> </p><p><span
  m='1876920'>So</span> <span m='1877160'>that</span> <span
  m='1877880'>whereas</span> <span m='1878360'>in</span> <span
  m='1878450'>the</span> <span m='1878510'>previous</span> <span
  m='1878990'>case</span> <span m='1879590'>the</span> <span
  m='1879770'>transition</span> <span m='1880340'>point</span> <span
  m='1880640'>was</span> <span m='1880760'>someplace</span> <span
  m='1881270'>down</span> <span m='1881600'>here,</span> <span
  m='1882470'>we've</span> <span m='1882620'>now</span> <span
  m='1882830'>moved</span> <span m='1883130'>it</span> <span
  m='1883220'>farther</span> <span m='1883700'>up</span> <span
  m='1884030'>into</span> <span m='1884270'>the</span> <span
  m='1884390'>transition</span> <span m='1884960'>region,</span> <span
  m='1885380'>closer</span> <span m='1886430'>to</span> <span
  m='1886550'>the</span> <span m='1886680'>pass</span> <span
  m='1887125'>band.</span> <span m='1887870'>And</span> <span
  m='1888200'>the</span> <span m='1888290'>pass band</span> <span
  m='1888830'>ripple</span> <span m='1889340'>has</span> <span
  m='1889730'>become</span> <span m='1890660'>correspondingly</span> <span
  m='1891500'>smaller.</span> <span m='1892820'>So</span> <span
  m='1893390'>this,</span> <span m='1893630'>in</span> <span
  m='1893750'>fact,</span> <span m='1894260'>is</span> <span
  m='1895010'>a</span> <span m='1895460'>design</span> <span
  m='1895940'>technique</span> <span m='1897080'>that</span> <span
  m='1897860'>can</span> <span m='1898070'>be</span> <span
  m='1898190'>used</span> <span m='1898580'>for</span> <span
  m='1898790'>the</span> <span m='1898880'>design</span> <span
  m='1899630'>of,</span> <span m='1901910'>generally,</span> <span
  m='1902930'>band</span> <span m='1903440'>frequency</span> <span
  m='1904010'>selective</span> <span m='1904760'>filters,</span> <span
  m='1905900'>where</span> <span m='1906650'>we</span> <span
  m='1907070'>first</span> <span m='1907430'>of</span> <span
  m='1907550'>all</span> <span m='1907700'>specify</span> <span
  m='1909350'>frequency</span> <span m='1909890'>samples.</span> </p><p><span
  m='1910970'>In</span> <span m='1911060'>fact,</span> <span
  m='1911400'>this</span> <span m='1911450'>can</span> <span
  m='1911600'>be</span> <span m='1911690'>used,</span> <span
  m='1912200'>really,</span> <span m='1912500'>for</span> <span
  m='1912620'>the</span> <span m='1912710'>design</span> <span
  m='1913310'>of</span> <span m='1914030'>any</span> <span
  m='1914750'>digital</span> <span m='1915080'>filter</span> <span
  m='1915410'>characteristic</span> <span m='1916190'>with</span> <span
  m='1916430'>transition</span> <span m='1917510'>regions.</span> <span
  m='1918800'>And</span> <span m='1919520'>then,</span> <span
  m='1919820'>perhaps,</span> <span m='1920450'>[AUDIO OUT]</span> <span
  m='1922610'>reducing</span> <span m='1923240'>the</span> <span
  m='1923330'>ripple</span> <span m='1923900'>in</span> <span
  m='1924050'>the</span> <span m='1924140'>pass</span> <span
  m='1924500'>band</span> <span m='1924855'>and/or</span> <span
  m='1925310'>the</span> <span m='1925460'>stop</span> <span
  m='1925910'>band,</span> <span m='1926190'>or in</span> <span
  m='1926270'>the</span> <span m='1926360'>various</span> <span
  m='1926780'>bands,</span> <span m='1927650'>by</span> <span
  m='1928100'>allowing</span> <span m='1928910'>an</span> <span
  m='1929750'>additional</span> <span m='1930260'>point</span> <span
  m='1931250'>to</span> <span m='1931970'>be</span> <span
  m='1932120'>used</span> <span m='1932540'>to</span> <span
  m='1932690'>widen</span> <span m='1933050'>the</span> <span
  m='1933140'>transition</span> <span m='1933770'>band.</span> <span
  m='1934640'>And</span> <span m='1935120'>as</span> <span m='1935390'>we</span>
  <span m='1935540'>move</span> <span m='1935810'>this</span> <span
  m='1936020'>point</span> <span m='1936320'>up</span> <span
  m='1936470'>or</span> <span m='1936530'>down,</span> <span
  m='1937370'>then,</span> <span m='1937850'>we</span> <span
  m='1938060'>will</span> <span m='1938240'>reduce</span> <span
  m='1938900'>the</span> <span m='1939020'>pass band</span> <span
  m='1939620'>and</span> <span m='1939710'>the</span> <span
  m='1939800'>stop</span> <span m='1940160'>band</span> <span
  m='1940370'>ripple.</span> </p><p><span m='1941320'>We</span> <span
  m='1941750'>can</span> <span m='1941900'>also,</span> <span
  m='1942170'>of</span> <span m='1942260'>course,</span> <span
  m='1942560'>consider</span> <span m='1943670'>moving</span> <span
  m='1943970'>not</span> <span m='1944180'>just</span> <span
  m='1944450'>one</span> <span m='1944750'>point</span> <span
  m='1945230'>into</span> <span m='1945560'>the</span> <span
  m='1945980'>transition</span> <span m='1946520'>region,</span> <span
  m='1947000'>but</span> <span m='1947240'>two</span> <span
  m='1947450'>points</span> <span m='1947840'>or</span> <span
  m='1947930'>three</span> <span m='1948170'>points</span> <span
  m='1948560'>or</span> <span m='1948650'>more</span> <span
  m='1948890'>points.</span> <span m='1949760'>Obviously,</span> <span
  m='1950330'>as</span> <span m='1950450'>we</span> <span m='1950600'>do</span>
  <span m='1950810'>that,</span> <span m='1951770'>we</span> <span
  m='1952400'>will</span> <span m='1952880'>widen</span> <span
  m='1953270'>the</span> <span m='1953390'>transition</span> <span
  m='1953990'>band</span> <span m='1954260'>further.</span> <span
  m='1955250'>And</span> <span m='1956090'>at</span> <span
  m='1956180'>the</span> <span m='1956300'>same</span> <span
  m='1956600'>time,</span> <span m='1957170'>that</span> <span
  m='1957980'>offers</span> <span m='1958670'>some</span> <span
  m='1959330'>additional</span> <span m='1959780'>flexibility,</span> <span
  m='1961230'>which</span> <span m='1961430'>permits</span> <span
  m='1961850'>us</span> <span m='1962120'>to</span> <span
  m='1962480'>reduce</span> <span m='1962930'>the</span> <span m='1963060'>pass
  band</span> <span m='1963830'>and</span> <span m='1963950'>stop</span> <span
  m='1964340'>band</span> <span m='1964520'>ripple.</span> <span
  m='1965300'>So</span> <span m='1965780'>this</span> <span
  m='1966080'>then</span> <span m='1966440'>is</span> <span
  m='1966650'>basically</span> <span m='1967580'>the</span> <span
  m='1968810'>strategy</span> <span m='1969800'>in</span> <span
  m='1970460'>the</span> <span m='1971870'>frequency</span> <span
  m='1972380'>sampling</span> <span m='1973250'>method</span> <span
  m='1973850'>of</span> <span m='1974630'>digital</span> <span
  m='1974930'>filter</span> <span m='1975290'>design.</span> </p><p><span
  m='1977060'>The</span> <span m='1977390'>final</span> <span
  m='1977780'>method</span> <span m='1978530'>that</span> <span
  m='1978860'>I</span> <span m='1979010'>would</span> <span
  m='1979160'>like</span> <span m='1979460'>to</span> <span
  m='1979880'>touch</span> <span m='1980270'>on</span> <span
  m='1980900'>just</span> <span m='1981170'>very</span> <span
  m='1981440'>briefly</span> <span m='1983120'>is</span> <span
  m='1983630'>a</span> <span m='1983690'>method</span> <span
  m='1984510'>which</span> <span m='1985880'>I</span> <span
  m='1986390'>referred</span> <span m='1986840'>to</span> <span
  m='1987440'>at</span> <span m='1987620'>the</span> <span
  m='1987740'>beginning</span> <span m='1988070'>of</span> <span
  m='1988160'>this</span> <span m='1988370'>lecture</span> <span
  m='1988970'>as</span> <span m='1989570'>an</span> <span
  m='1989690'>equiripple</span> <span m='1990620'>design</span> <span
  m='1991070'>method.</span> <span m='1992300'>And</span> <span
  m='1992630'>basically,</span> <span m='1993560'>the</span> <span
  m='1993650'>notion</span> <span m='1994100'>here</span> <span
  m='1995450'>is</span> <span m='1995690'>that</span> <span
  m='1997220'>we've</span> <span m='1997400'>seen</span> <span
  m='1998330'>that</span> <span m='1998900'>there</span> <span
  m='1999350'>is</span> <span m='2000070'>a</span> <span
  m='2000170'>trade</span> <span m='2000270'>off</span> <span
  m='2001330'>between</span> <span m='2002290'>the</span> <span
  m='2002500'>transition</span> <span m='2003190'>region</span> <span
  m='2003820'>on</span> <span m='2003940'>the</span> <span
  m='2004060'>one</span> <span m='2004270'>hand,</span> <span
  m='2004820'>and</span> <span m='2004960'>pass band</span> <span
  m='2005620'>and</span> <span m='2005710'>stop</span> <span
  m='2006130'>band</span> <span m='2006310'>ripple</span> <span
  m='2006880'>on</span> <span m='2007000'>the</span> <span
  m='2007150'>other</span> <span m='2007360'>hand.</span> </p><p><span
  m='2008350'>Well,</span> <span m='2008710'>one</span> <span
  m='2008950'>could</span> <span m='2009070'>inquire</span> <span
  m='2009760'>as</span> <span m='2010030'>to</span> <span
  m='2010180'>whether,</span> <span m='2011050'>in</span> <span
  m='2011590'>at</span> <span m='2011680'>least</span> <span
  m='2011920'>in</span> <span m='2012040'>some</span> <span
  m='2012310'>sense,</span> <span m='2013400'>we</span> <span
  m='2013450'>could</span> <span m='2013600'>design</span> <span
  m='2014050'>for</span> <span m='2014230'>ourselves</span> <span
  m='2015070'>an</span> <span m='2015220'>optimum</span> <span
  m='2016000'>class</span> <span m='2016540'>of</span> <span
  m='2016630'>filters.</span> <span m='2017890'>And</span> <span
  m='2018370'>indeed,</span> <span m='2019120'>you</span> <span
  m='2019270'>can.</span> <span m='2020710'>And</span> <span
  m='2021580'>in</span> <span m='2021700'>fact,</span> <span
  m='2022050'>it's</span> <span m='2022180'>possible</span> <span
  m='2022720'>to</span> <span m='2022870'>show</span> <span
  m='2024010'>that</span> <span m='2024430'>the</span> <span
  m='2024610'>optimum</span> <span m='2025060'>strategy</span> <span
  m='2026080'>in</span> <span m='2026230'>terms</span> <span
  m='2026890'>of</span> <span m='2028240'>minimizing</span> <span
  m='2029380'>pass band</span> <span m='2029980'>or</span> <span
  m='2030040'>stop</span> <span m='2030460'>band</span> <span
  m='2030670'>ripple,</span> <span m='2031150'>or</span> <span
  m='2031540'>in</span> <span m='2031660'>terms</span> <span
  m='2031960'>of</span> <span m='2032050'>minimizing</span> <span
  m='2032620'>a</span> <span m='2032680'>transition</span> <span
  m='2033250'>band,</span> <span m='2034450'>is</span> <span
  m='2035320'>to</span> <span m='2035440'>design</span> <span
  m='2035950'>the</span> <span m='2036040'>filter</span> <span
  m='2036970'>to</span> <span m='2037090'>have</span> <span
  m='2037630'>an</span> <span m='2037810'>equiripple</span> <span
  m='2038800'>frequency</span> <span m='2039340'>response</span> <span
  m='2039850'>characteristic.</span> <span m='2042070'>Well,</span> <span
  m='2042760'>one</span> <span m='2043270'>way</span> <span
  m='2043750'>of</span> <span m='2044380'>setting</span> <span
  m='2044830'>up</span> <span m='2045310'>the</span> <span
  m='2045640'>optimal</span> <span m='2046240'>condition--</span> <span
  m='2046830'>and</span> <span m='2047080'>it</span> <span
  m='2047200'>turns</span> <span m='2047530'>out</span> <span
  m='2047710'>that</span> <span m='2047830'>there</span> <span
  m='2047980'>are</span> <span m='2048010'>a</span> <span
  m='2048040'>variety</span> <span m='2048639'>of</span> <span
  m='2048760'>ways,</span> <span m='2049659'>and</span> <span
  m='2050110'>these</span> <span m='2050350'>are</span> <span
  m='2050440'>discussed</span> <span m='2050920'>in</span> <span
  m='2051010'>quite</span> <span m='2051219'>a</span> <span
  m='2051280'>bit</span> <span m='2051429'>more</span> <span
  m='2051610'>detail</span> <span m='2052120'>in</span> <span
  m='2052239'>the</span> <span m='2052300'>text.</span> </p><p><span
  m='2053870'>But</span> <span m='2054010'>for</span> <span
  m='2054250'>example,</span> <span m='2055670'>if</span> <span
  m='2056020'>we</span> <span m='2056230'>pick</span> <span m='2057070'>a</span>
  <span m='2057340'>pass band</span> <span m='2058000'>cutoff</span> <span
  m='2058360'>frequency</span> <span m='2059610'>and</span> <span
  m='2059739'>a</span> <span m='2059790'>stop</span> <span
  m='2060250'>band</span> <span m='2060429'>cutoff</span> <span
  m='2060790'>frequency.</span> <span m='2062469'>Furthermore,</span> <span
  m='2063429'>if</span> <span m='2063850'>we,</span> <span m='2065380'>of</span>
  <span m='2065469'>course,</span> <span m='2065770'>are</span> <span
  m='2065860'>going</span> <span m='2066010'>to</span> <span
  m='2066130'>allow</span> <span m='2066400'>some</span> <span
  m='2066610'>deviation</span> <span m='2067239'>in</span> <span
  m='2067330'>the</span> <span m='2067420'>pass</span> <span
  m='2067780'>band</span> <span m='2068230'>and</span> <span
  m='2068350'>some</span> <span m='2068530'>deviation</span> <span
  m='2069310'>in</span> <span m='2069429'>the</span> <span
  m='2069520'>stop</span> <span m='2069880'>band,</span> <span
  m='2071050'>if</span> <span m='2071230'>in</span> <span
  m='2071350'>addition,</span> <span m='2072260'>we</span> <span
  m='2072310'>fix</span> <span m='2072670'>the</span> <span
  m='2072790'>ratio</span> <span m='2074050'>of</span> <span
  m='2074739'>stop</span> <span m='2075270'>band</span> <span
  m='2075575'>to</span> <span m='2076000'>pass</span> <span
  m='2076329'>band</span> <span m='2076659'>ripple,</span> <span
  m='2079030'>and</span> <span m='2079540'>if</span> <span m='2079750'>we</span>
  <span m='2079870'>then</span> <span m='2080080'>inquire</span> <span
  m='2080800'>as</span> <span m='2081219'>to</span> <span
  m='2081580'>what</span> <span m='2081820'>sort</span> <span
  m='2082030'>of</span> <span m='2082150'>characteristic</span> <span
  m='2082989'>should</span> <span m='2083199'>result</span> <span
  m='2084340'>if</span> <span m='2085090'>delta</span> <span
  m='2085510'>1,</span> <span m='2086350'>the</span> <span
  m='2086530'>pass</span> <span m='2086844'>band</span> <span
  m='2087159'>ripple,</span> <span m='2087610'>or</span> <span
  m='2087790'>equivalently,</span> <span m='2088929'>delta</span> <span
  m='2089290'>2,</span> <span m='2089949'>the</span> <span
  m='2090070'>stop</span> <span m='2090460'>band</span> <span
  m='2090670'>ripple</span> <span m='2091630'>is</span> <span
  m='2091780'>minimized--</span> <span m='2092949'>this</span> <span
  m='2093340'>should</span> <span m='2093550'>be</span> <span
  m='2093790'>delta</span> <span m='2094179'>2--</span> <span
  m='2095889'>so</span> <span m='2096219'>if</span> <span
  m='2096520'>delta</span> <span m='2096820'>1 and</span> <span
  m='2097060'>delta</span> <span m='2097390'>2</span> <span
  m='2097960'>are</span> <span m='2098560'>minimized,</span> <span
  m='2100240'>it</span> <span m='2100360'>turns</span> <span
  m='2100750'>out</span> <span m='2101020'>it</span> <span
  m='2101080'>can</span> <span m='2101230'>be</span> <span
  m='2101350'>shown</span> <span m='2102370'>that</span> <span
  m='2102820'>that</span> <span m='2103210'>implies</span> <span
  m='2104110'>an</span> <span m='2104260'>equiripple</span> <span
  m='2105055'>characteristic</span> <span m='2105655'>in</span> <span
  m='2105910'>the</span> <span m='2106225'>pass</span> <span
  m='2106540'>band,</span> <span m='2108190'>and</span> <span
  m='2108445'>an</span> <span m='2108700'>equiripple</span> <span
  m='2109690'>characteristic</span> <span m='2110500'>in</span> <span
  m='2110590'>the</span> <span m='2110650'>stop</span> <span
  m='2111050'>band.</span> <span m='2111790'>That</span> <span
  m='2111970'>is,</span> <span m='2112300'>the</span> <span
  m='2112420'>ripples</span> <span m='2112810'>in</span> <span
  m='2112900'>the</span> <span m='2112960'>pass</span> <span
  m='2113320'>band</span> <span m='2114130'>should</span> <span
  m='2114370'>alternate</span> <span m='2115360'>between</span> <span
  m='2116020'>the</span> <span m='2116170'>upper</span> <span
  m='2116410'>and</span> <span m='2116500'>lower</span> <span
  m='2117490'>limits.</span> <span m='2118660'>And</span> <span
  m='2119350'>the</span> <span m='2119440'>ripples</span> <span
  m='2119800'>in</span> <span m='2119890'>a</span> <span m='2119950'>stop</span>
  <span m='2120370'>band</span> <span m='2120820'>should</span> <span
  m='2121030'>alternate</span> <span m='2121570'>between</span> <span
  m='2122200'>the</span> <span m='2122350'>upper</span> <span
  m='2122770'>and</span> <span m='2122890'>lower</span> <span
  m='2123190'>limits.</span> </p><p><span m='2124890'>In</span> <span
  m='2125020'>the</span> <span m='2125110'>text,</span> <span
  m='2125710'>there</span> <span m='2126160'>are</span> <span
  m='2126370'>discussed</span> <span m='2127300'>several</span> <span
  m='2127900'>algorithmic</span> <span m='2128500'>procedures</span> <span
  m='2129580'>for</span> <span m='2129760'>actually</span> <span
  m='2130180'>designing</span> <span m='2130870'>equiripple</span> <span
  m='2131470'>filters.</span> <span m='2132040'>We</span> <span
  m='2132190'>won't</span> <span m='2132430'>go</span> <span
  m='2132610'>through</span> <span m='2132850'>those</span> <span
  m='2133090'>details</span> <span m='2134140'>in</span> <span
  m='2134260'>this</span> <span m='2134470'>lecture.</span> <span
  m='2135190'>Mainly,</span> <span m='2135700'>I</span> <span
  m='2135820'>want</span> <span m='2136030'>to</span> <span
  m='2136090'>emphasize</span> <span m='2136690'>the</span> <span
  m='2136780'>point</span> <span m='2137230'>that</span> <span
  m='2138100'>there</span> <span m='2138400'>are</span> <span
  m='2138670'>procedures</span> <span m='2139630'>that</span> <span
  m='2139900'>allow</span> <span m='2140230'>you</span> <span
  m='2140560'>to</span> <span m='2140770'>implement</span> <span
  m='2141250'>designs</span> <span m='2141700'>of</span> <span
  m='2141820'>this</span> <span m='2142030'>type.</span> <span
  m='2142840'>And</span> <span m='2143650'>that</span> <span
  m='2144460'>designs</span> <span m='2144940'>of</span> <span
  m='2145060'>this</span> <span m='2145240'>type</span> <span
  m='2145660'>are</span> <span m='2145840'>optimum.</span> <span
  m='2147010'>Let</span> <span m='2147190'>me</span> <span
  m='2147370'>just</span> <span m='2148180'>show</span> <span
  m='2148540'>you</span> <span m='2150010'>one</span> <span
  m='2150340'>example</span> <span m='2151150'>of</span> <span
  m='2152080'>an</span> <span m='2152200'>optimum</span> <span
  m='2152980'>equiripple</span> <span m='2153760'>finite</span> <span
  m='2154240'>impulse</span> <span m='2154630'>response</span> <span
  m='2155290'>filter</span> <span m='2156340'>that</span> <span
  m='2156460'>was</span> <span m='2156670'>designed</span> <span
  m='2157600'>when</span> <span m='2158170'>our</span> <span
  m='2158950'>computer</span> <span m='2159400'>budget</span> <span
  m='2159820'>was</span> <span m='2160210'>particularly</span> <span
  m='2161230'>big.</span> </p><p><span m='2162880'>This</span> <span
  m='2163090'>is</span> <span m='2163240'>an</span> <span
  m='2163330'>example</span> <span m='2164140'>of</span> <span
  m='2164890'>a</span> <span m='2165130'>length</span> <span
  m='2166010'>251</span> <span m='2167350'>point</span> <span
  m='2167800'>finite</span> <span m='2168220'>impulse</span> <span
  m='2168640'>response</span> <span m='2169420'>digital</span> <span
  m='2169780'>filter,</span> <span m='2171610'>designed</span> <span
  m='2172450'>using</span> <span m='2173080'>one</span> <span
  m='2173290'>of</span> <span m='2173350'>the</span> <span
  m='2173500'>algorithms</span> <span m='2174340'>that</span> <span
  m='2174670'>is</span> <span m='2175150'>discussed</span> <span
  m='2175690'>in</span> <span m='2175780'>the</span> <span
  m='2175890'>text.</span> <span m='2176950'>And</span> <span
  m='2177610'>you</span> <span m='2177820'>can</span> <span
  m='2177970'>see</span> <span m='2178870'>that,</span> <span
  m='2179350'>indeed,</span> <span m='2180310'>the</span> <span
  m='2180700'>equiripple</span> <span m='2181300'>characteristics</span> <span
  m='2182440'>are</span> <span m='2182890'>evident</span> <span
  m='2183370'>in</span> <span m='2183460'>the</span> <span
  m='2183550'>pass</span> <span m='2183910'>band.</span> <span
  m='2186130'>This</span> <span m='2186400'>curve</span> <span
  m='2186760'>corresponds</span> <span m='2187600'>to</span> <span
  m='2187900'>the</span> <span m='2188020'>frequency</span> <span
  m='2188470'>characteristics</span> <span m='2189850'>plotted</span> <span
  m='2190510'>in</span> <span m='2190975'>dB.</span> <span m='2192430'>So</span>
  <span m='2192700'>the</span> <span m='2192820'>pass band</span> <span
  m='2193390'>ripple</span> <span m='2193660'>doesn't</span> <span
  m='2193990'>show</span> <span m='2194290'>up.</span> <span
  m='2195160'>So</span> <span m='2195640'>with</span> <span
  m='2195850'>that</span> <span m='2196060'>scale</span> <span
  m='2196480'>expanded,</span> <span m='2197110'>we</span> <span
  m='2197200'>can</span> <span m='2197350'>see</span> <span
  m='2197560'>the</span> <span m='2197680'>ripple.</span> <span
  m='2198520'>And</span> <span m='2198670'>then</span> <span
  m='2199240'>we</span> <span m='2199420'>have</span> <span
  m='2200050'>the</span> <span m='2200320'>ripple</span> <span
  m='2201010'>in</span> <span m='2201580'>the</span> <span
  m='2201790'>stop</span> <span m='2202300'>band.</span> <span
  m='2203260'>There</span> <span m='2203410'>should</span> <span
  m='2203620'>be</span> <span m='2204040'>125</span> <span
  m='2205090'>ripples</span> <span m='2206060'>all</span> <span
  m='2206320'>together.</span> </p><p><span m='2207230'>And</span> <span
  m='2207250'>in</span> <span m='2207310'>fact,</span> <span
  m='2208000'>we</span> <span m='2208120'>could</span> <span
  m='2208420'>see</span> <span m='2208720'>if</span> <span
  m='2208870'>that</span> <span m='2209050'>was</span> <span
  m='2209290'>true.</span> <span m='2209620'>We</span> <span
  m='2209690'>could</span> <span m='2209790'>[AUDIO OUT]</span> <span
  m='2210490'>one,</span> <span m='2210700'>two,</span> <span
  m='2210880'>three.</span> <span m='2211150'>But</span> <span
  m='2211270'>let's</span> <span m='2211480'>not</span> <span
  m='2211690'>do</span> <span m='2211870'>that.</span> <span
  m='2213700'>Obviously,</span> <span m='2214360'>there's</span> <span
  m='2214570'>a</span> <span m='2214600'>very</span> <span
  m='2214870'>sharp</span> <span m='2215500'>transition</span> <span
  m='2216130'>band.</span> <span m='2217030'>And</span> <span
  m='2218020'>what</span> <span m='2218170'>turns</span> <span
  m='2218530'>out</span> <span m='2218740'>to</span> <span m='2218890'>be</span>
  <span m='2220000'>minus</span> <span m='2220660'>approximately</span> <span
  m='2221470'>80--</span> <span m='2222130'>approximately</span> <span
  m='2222670'>minus</span> <span m='2223030'>85</span> <span
  m='2224260'>dB</span> <span m='2224950'>attenuation</span> <span
  m='2225700'>in</span> <span m='2225790'>the</span> <span
  m='2225880'>stop</span> <span m='2226220'>band.</span> <span
  m='2227230'>So</span> <span m='2228070'>this</span> <span
  m='2228280'>is</span> <span m='2228370'>an</span> <span
  m='2228490'>example</span> <span m='2229180'>of</span> <span
  m='2229600'>a</span> <span m='2229660'>very</span> <span
  m='2230020'>high</span> <span m='2230260'>order</span> <span
  m='2231060'>equiripple</span> <span m='2231910'>optimum</span> <span
  m='2233230'>finite</span> <span m='2233650'>impulse</span> <span
  m='2234040'>response</span> <span m='2234940'>digital</span> <span
  m='2235270'>filter</span> <span m='2235960'>that</span> <span
  m='2236620'>was</span> <span m='2237010'>designed</span> <span
  m='2237520'>using</span> <span m='2238270'>one</span> <span
  m='2238450'>of</span> <span m='2238540'>the</span> <span
  m='2238690'>algorithms</span> <span m='2239290'>discussed</span> <span
  m='2239740'>in</span> <span m='2239830'>the</span> <span
  m='2239920'>text.</span> </p><p><span m='2243730'>OK.</span> <span
  m='2244090'>Well,</span> <span m='2245380'>this,</span> <span
  m='2246100'>as</span> <span m='2246490'>I</span> <span
  m='2246670'>indicated</span> <span m='2247540'>at</span> <span
  m='2248140'>the</span> <span m='2248260'>beginning</span> <span
  m='2248650'>of</span> <span m='2248770'>the</span> <span
  m='2248860'>lecture,</span> <span m='2249880'>was</span> <span
  m='2250060'>intended</span> <span m='2250660'>primarily</span> <span
  m='2251590'>as</span> <span m='2252370'>a</span> <span m='2252820'>very</span>
  <span m='2254470'>brief</span> <span m='2255370'>overview</span> <span
  m='2256390'>of</span> <span m='2256810'>finite</span> <span
  m='2257260'>impulse</span> <span m='2257680'>response</span> <span
  m='2258520'>digital</span> <span m='2258850'>filter</span> <span
  m='2259210'>design.</span> <span m='2260500'>Hopefully,</span> <span
  m='2261280'>it</span> <span m='2261790'>gives</span> <span
  m='2262120'>you</span> <span m='2262720'>some</span> <span
  m='2263290'>appreciation</span> <span m='2264850'>for</span> <span
  m='2265300'>the</span> <span m='2265450'>style</span> <span
  m='2266080'>of</span> <span m='2266200'>the</span> <span
  m='2266320'>design</span> <span m='2266740'>techniques.</span> <span
  m='2267880'>There</span> <span m='2268090'>are,</span> <span
  m='2268330'>of</span> <span m='2268420'>course,</span> <span
  m='2269180'>a</span> <span m='2269620'>large</span> <span
  m='2269950'>number</span> <span m='2270250'>of</span> <span
  m='2270310'>details,</span> <span m='2271450'>some</span> <span
  m='2271720'>of</span> <span m='2271840'>which</span> <span
  m='2272080'>are</span> <span m='2272170'>discussed</span> <span
  m='2272680'>in</span> <span m='2272770'>the</span> <span
  m='2272860'>text</span> <span m='2273370'>and</span> <span
  m='2273520'>some</span> <span m='2273760'>of</span> <span
  m='2273910'>which</span> <span m='2274450'>aren't.</span> <span
  m='2275800'>But</span> <span m='2277120'>in</span> <span
  m='2277270'>any</span> <span m='2277450'>case,</span> <span
  m='2278360'>this,</span> <span m='2278830'>then,</span> <span
  m='2279190'>concludes</span> <span m='2279730'>our</span> <span
  m='2279850'>discussion</span> <span m='2280660'>of</span> <span
  m='2281770'>the</span> <span m='2281920'>design</span> <span
  m='2282460'>of</span> <span m='2282640'>infinite</span> <span
  m='2283000'>impulse</span> <span m='2283390'>response</span> <span
  m='2284110'>and</span> <span m='2284230'>finite</span> <span
  m='2284650'>impulse</span> <span m='2285010'>response</span> <span
  m='2285580'>digital</span> <span m='2285910'>filters.</span> </p><p><span
  m='2287500'>In</span> <span m='2287590'>the</span> <span
  m='2287680'>next</span> <span m='2287920'>lecture,</span> <span
  m='2288860'>we</span> <span m='2289240'>will</span> <span
  m='2289570'>begin</span> <span m='2289870'>a</span> <span
  m='2289930'>new</span> <span m='2290080'>topic,</span> <span
  m='2291010'>specifically</span> <span m='2292300'>the</span> <span
  m='2292810'>topic</span> <span m='2293350'>involving</span> <span
  m='2293890'>the</span> <span m='2293950'>computation</span> <span
  m='2294940'>of</span> <span m='2295090'>the</span> <span
  m='2295210'>discrete</span> <span m='2295570'>Fourier</span> <span
  m='2295930'>transform.</span> <span m='2297050'>Thank</span> <span
  m='2297260'>you.</span> </p>
embedded_media:
  - uid: 7be1f7fe5548602705110ab04ca05d83
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: MITRES_6_008S11_lec17.pdf
    title: MITRES_6_008S11_lec17.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-17-design-of-fir-digital-filters/MITRES_6_008S11_lec17.pdf
  - uid: 68dac7f6fee738df0c3029d98eaaa53e
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: oJv4dsUID0Q
  - uid: 1f0e50226480f787dc7e7fa7f5ca4c8d
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-17-design-fir-digital/id481803782?i=108361998
  - uid: c208195c35aa0d894287c639caa39625
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec17_300k.mp4'
  - uid: e61bec85057b03e2b4a4617f9887a4c3
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/oJv4dsUID0Q/default.jpg'
  - uid: c33116958aedec9df1a5d71eec298dc5
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: oJv4dsUID0Q
  - uid: e20732ec12cccd677e37ca245f45ea63
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: oJv4dsUID0Q.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-17-design-of-fir-digital-filters/oJv4dsUID0Q.srt
  - uid: 472eccab072313657550c9ca82c113f9
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: oJv4dsUID0Q.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-17-design-of-fir-digital-filters/oJv4dsUID0Q.pdf
  - uid: b7bf258f5ddb6f7d6d98ce43dbd519e7
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 4ecfb1a765580391911ca83a80440ee7
    parent_uid: 968adeab1291c57fe0e67ac385b514d9
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
