---
order_index: null
title: 'Lecture 16: Digital Butterworth Filters'
template_type: Tabbed
uid: f94b2ff2eccc3fa733244a112fecf56e
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-16-digital-butterworth-filters
short_url: lecture-16-digital-butterworth-filters
inline_embed_id: '15566195lecture16:digitalbutterworthfilters19066982'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Design of digital Butterworth filter using
  impulse invariance, design of digital Butterworth filter using the bilinear
  transformation, comparison of the resulting designs.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Digital Butterworth Filters (<img src="/images/inacessible.gif" alt="This
  resource may not render correctly in a screen reader." /><a
  href="./resolveuid/cf3af19ce73b9d4ffb66fcb7f8be5800">PDF</a>)</p>
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
  m='22976'>[MUSIC PLAYING]</span> </p><p></p><p><span m='55600'>ALAN
  OPPENHEIM:</span> <span m='55645'>In</span> <span m='55690'>the</span> <span
  m='55750'>last</span> <span m='56020'>several</span> <span
  m='56350'>lectures,</span> <span m='57270'>we've</span> <span
  m='57730'>considered</span> <span m='58840'>a</span> <span
  m='58900'>number</span> <span m='59440'>of</span> <span
  m='60040'>procedures</span> <span m='60970'>for</span> <span
  m='61300'>designing</span> <span m='61990'>digital</span> <span
  m='62380'>filters</span> <span m='66100'>for</span> <span m='66220'>the</span>
  <span m='66310'>class</span> <span m='66610'>of</span> <span
  m='66700'>infinite</span> <span m='67060'>impulse</span> <span
  m='67450'>response</span> <span m='68290'>filters.</span> <span
  m='69730'>And</span> <span m='70360'>the</span> <span m='70660'>two</span>
  <span m='71320'>primary</span> <span m='71830'>design</span> <span
  m='72220'>techniques</span> <span m='72880'>that</span> <span
  m='73000'>we</span> <span m='73120'>considered,</span> <span
  m='73630'>in</span> <span m='73720'>fact,</span> <span m='74530'>the</span>
  <span m='74830'>two</span> <span m='75070'>useful</span> <span
  m='75760'>design</span> <span m='76120'>techniques</span> <span
  m='76960'>that</span> <span m='77110'>we</span> <span
  m='77230'>developed,</span> <span m='78340'>were</span> <span
  m='78550'>the</span> <span m='78700'>techniques</span> <span
  m='79240'>which</span> <span m='79480'>we</span> <span m='79630'>refer</span>
  <span m='80050'>to</span> <span m='80500'>as</span> <span
  m='80920'>impulse</span> <span m='81400'>invariance,</span> <span
  m='82720'>and</span> <span m='83440'>also</span> <span m='84190'>the</span>
  <span m='84400'>bilinear</span> <span m='84940'>transformation.</span>
  </p><p><span m='87400'>You</span> <span m='87550'>recall,</span> <span
  m='88460'>hopefully,</span> <span m='89110'>that</span> <span
  m='89590'>both</span> <span m='89950'>of</span> <span m='90010'>these</span>
  <span m='90280'>techniques</span> <span m='91180'>are</span> <span
  m='92200'>techniques</span> <span m='92740'>that</span> <span
  m='92890'>correspond</span> <span m='93940'>to</span> <span
  m='94690'>mapping</span> <span m='95680'>a</span> <span
  m='96640'>continuous</span> <span m='97240'>time</span> <span
  m='97560'>or</span> <span m='97660'>analog</span> <span
  m='98470'>filter</span> <span m='99550'>to</span> <span m='99940'>a</span>
  <span m='100000'>digital</span> <span m='100420'>filter.</span> <span
  m='102120'>What</span> <span m='102250'>I'd</span> <span
  m='102340'>like</span> <span m='102520'>to</span> <span m='102640'>do</span>
  <span m='102790'>in</span> <span m='102880'>this</span> <span
  m='103060'>lecture</span> <span m='103660'>is</span> <span
  m='105010'>consider</span> <span m='105550'>an</span> <span
  m='105670'>example</span> <span m='106510'>of</span> <span
  m='107020'>the</span> <span m='107140'>design</span> <span
  m='107860'>of</span> <span m='108280'>a</span> <span m='108490'>digital</span>
  <span m='108820'>low-pass</span> <span m='109390'>filter</span> <span
  m='110410'>using</span> <span m='110980'>each</span> <span
  m='111220'>of</span> <span m='111310'>these</span> <span
  m='111520'>techniques,</span> <span m='112180'>using</span> <span
  m='112600'>impulse</span> <span m='113050'>invariance</span> <span
  m='113770'>and</span> <span m='113860'>the</span> <span
  m='114100'>bilinear</span> <span m='114430'>transformation.</span> <span
  m='115900'>And</span> <span m='116050'>hopefully</span> <span
  m='116830'>this</span> <span m='117100'>will</span> <span
  m='117460'>give</span> <span m='117730'>you</span> <span m='118210'>a</span>
  <span m='118270'>better</span> <span m='118570'>feeling</span> <span
  m='119110'>for</span> <span m='119440'>how</span> <span m='119740'>both</span>
  <span m='120040'>of</span> <span m='120130'>these</span> <span
  m='120340'>techniques</span> <span m='120880'>work.</span> </p><p><span
  m='123080'>The</span> <span m='123440'>class</span> <span m='124130'>of</span>
  <span m='124730'>analog</span> <span m='125960'>filters</span> <span
  m='126890'>that</span> <span m='127310'>I</span> <span m='127430'>would</span>
  <span m='127610'>like</span> <span m='127820'>to</span> <span
  m='127970'>use</span> <span m='129050'>are</span> <span m='129500'>the</span>
  <span m='129740'>class of</span> <span m='130220'>so-called</span> <span
  m='130880'>analog</span> <span m='131390'>Butterworth</span> <span
  m='132020'>filters,</span> <span m='133200'>which</span> <span
  m='133520'>are</span> <span m='133880'>a</span> <span m='133970'>useful</span>
  <span m='134360'>class</span> <span m='134960'>of</span> <span
  m='135410'>lowpass</span> <span m='136220'>analog</span> <span
  m='136970'>and</span> <span m='137120'>digital</span> <span
  m='137480'>filters,</span> <span m='138500'>and</span> <span
  m='138650'>also</span> <span m='139220'>a</span> <span
  m='139310'>relatively</span> <span m='139880'>simple</span> <span
  m='140240'>class.</span> <span m='143120'>To</span> <span
  m='143530'>first</span> <span m='143860'>of</span> <span
  m='143980'>all,</span> <span m='144580'>define</span> <span
  m='145150'>the</span> <span m='145450'>class</span> <span m='145930'>of</span>
  <span m='146380'>analog</span> <span m='147550'>filters</span> <span
  m='148360'>that</span> <span m='148510'>we're</span> <span
  m='148660'>considering,</span> <span m='150010'>they</span> <span
  m='150190'>are</span> <span m='150820'>the</span> <span
  m='150940'>class</span> <span m='151270'>of</span> <span
  m='151360'>analog</span> <span m='151780'>Butterworth</span> <span
  m='152320'>filters.</span> <span m='153550'>And</span> <span
  m='154750'>this</span> <span m='154990'>class</span> <span
  m='155350'>of</span> <span m='155410'>filters</span> <span
  m='156100'>is</span> <span m='156280'>defined</span> <span
  m='157330'>by</span> <span m='158470'>the</span> <span
  m='158770'>analog</span> <span m='159490'>system</span> <span
  m='159970'>function</span> <span m='161450'>H</span> <span
  m='161720'>sub</span> <span m='161960'>a</span> <span m='162150'>of j</span>
  <span m='162360'>omega</span> <span m='163000'>magnitude</span> <span
  m='163580'>squared</span> <span m='164830'>of</span> <span
  m='165010'>the</span> <span m='165130'>form</span> <span m='165820'>1</span>
  <span m='166120'>over</span> <span m='166360'>1</span> <span
  m='166630'>plus</span> <span m='167170'>j</span> <span m='167680'>omega</span>
  <span m='168160'>divided</span> <span m='168580'>by</span> <span
  m='168790'>j</span> <span m='169030'>omega</span> <span m='169420'>sub</span>
  <span m='169810'>c</span> <span m='170200'>to</span> <span
  m='170320'>the</span> <span m='170410'>2N.</span> </p><p><span
  m='171910'>Now,</span> <span m='172450'>there</span> <span
  m='172690'>are</span> <span m='172780'>two</span> <span
  m='172960'>parameters</span> <span m='174160'>in</span> <span
  m='174340'>this</span> <span m='174520'>expression.</span> <span
  m='175750'>One</span> <span m='176170'>is</span> <span
  m='177430'>what's</span> <span m='177610'>referred</span> <span
  m='178000'>to</span> <span m='178270'>often</span> <span m='178570'>as</span>
  <span m='178690'>the</span> <span m='178780'>cutoff</span> <span
  m='179170'>frequency,</span> <span m='179920'>omega</span> <span
  m='180370'>sub</span> <span m='180730'>c.</span> <span m='181720'>And</span>
  <span m='182320'>the</span> <span m='182440'>second</span> <span
  m='183010'>is</span> <span m='183190'>the</span> <span m='183340'>order</span>
  <span m='183670'>of</span> <span m='183760'>the</span> <span
  m='183880'>filter,</span> <span m='184600'>namely</span> <span
  m='185050'>N.</span> <span m='186010'>Let</span> <span m='186160'>me</span>
  <span m='186280'>remind</span> <span m='186790'>you</span> <span
  m='186970'>that</span> <span m='187600'>we're</span> <span
  m='187720'>looking</span> <span m='188110'>at</span> <span
  m='188260'>here</span> <span m='188530'>an</span> <span
  m='188620'>expression</span> <span m='189400'>for</span> <span
  m='189520'>the</span> <span m='189640'>squared</span> <span
  m='190030'>magnitude</span> <span m='190660'>function.</span> <span
  m='191970'>And</span> <span m='192970'>so</span> <span m='193570'>we</span>
  <span m='193780'>have</span> <span m='194120'>a</span> <span
  m='194170'>2N</span> <span m='195070'>here.</span> <span m='195910'>But</span>
  <span m='196180'>in</span> <span m='196330'>fact,</span> <span
  m='196660'>N</span> <span m='197260'>is</span> <span m='197710'>what</span>
  <span m='197890'>corresponds</span> <span m='198610'>to</span> <span
  m='198730'>the</span> <span m='198850'>order</span> <span m='199120'>of</span>
  <span m='199210'>the</span> <span m='199300'>filter.</span> </p><p><span
  m='201490'>Well,</span> <span m='201780'>if</span> <span m='201960'>we</span>
  <span m='202050'>look</span> <span m='202260'>at</span> <span
  m='202350'>this</span> <span m='202770'>frequency</span> <span
  m='203310'>response</span> <span m='204000'>characteristic,</span> <span
  m='205890'>we</span> <span m='206220'>observe</span> <span
  m='206820'>that</span> <span m='207090'>at</span> <span
  m='207300'>omega</span> <span m='208410'>equal</span> <span
  m='208710'>to</span> <span m='208860'>0,</span> <span m='210390'>the</span>
  <span m='210510'>gain</span> <span m='211110'>or</span> <span
  m='211230'>the</span> <span m='211320'>magnitude</span> <span
  m='211800'>squared</span> <span m='212520'>is</span> <span
  m='212730'>equal</span> <span m='213000'>to</span> <span
  m='213120'>unity.</span> <span m='215180'>At</span> <span
  m='215990'>omega</span> <span m='216710'>equal</span> <span
  m='217100'>to</span> <span m='217280'>omega</span> <span m='217700'>sub</span>
  <span m='218105'>c,</span> <span m='219680'>the</span> <span
  m='219800'>j's</span> <span m='220160'>of</span> <span
  m='220250'>course</span> <span m='220550'>cancel</span> <span
  m='221060'>out.</span> <span m='221810'>At</span> <span
  m='221930'>omega</span> <span m='222620'>equal</span> <span
  m='223070'>to</span> <span m='223250'>omega</span> <span m='223660'>sub</span>
  <span m='224025'>c,</span> <span m='225050'>this</span> <span
  m='225350'>term</span> <span m='225860'>then</span> <span m='226070'>is</span>
  <span m='226190'>equal</span> <span m='226460'>to 1,</span> <span
  m='226610'>and</span> <span m='227000'>we</span> <span m='227150'>have</span>
  <span m='227740'>for</span> <span m='227870'>the</span> <span
  m='227960'>magnitude</span> <span m='228500'>squared</span> <span
  m='228890'>function,</span> <span m='229550'>a</span> <span
  m='229640'>half.</span> <span m='230660'>Or</span> <span m='230930'>for</span>
  <span m='231080'>the</span> <span m='231170'>magnitude</span> <span
  m='231800'>function,</span> <span m='233100'>which</span> <span
  m='233210'>is</span> <span m='233330'>what</span> <span
  m='233540'>we're</span> <span m='233660'>looking</span> <span
  m='234020'>at</span> <span m='234200'>here,</span> <span m='235960'>1</span>
  <span m='236360'>divided</span> <span m='236810'>by</span> <span
  m='237020'>the</span> <span m='237140'>square</span> <span
  m='237470'>root</span> <span m='237650'>of</span> <span m='237770'>2.</span>
  </p><p><span m='238910'>So</span> <span m='239410'>at</span> <span
  m='239540'>omega</span> <span m='239930'>equal</span> <span
  m='240200'>to</span> <span m='240380'>omega</span> <span m='240760'>sub</span>
  <span m='241140'>c,</span> <span m='241820'>an</span> <span
  m='241940'>analog</span> <span m='242390'>Butterworth</span> <span
  m='242930'>filter</span> <span m='243530'>has</span> <span m='243800'>a</span>
  <span m='243860'>magnitude</span> <span m='244580'>which</span> <span
  m='244790'>is</span> <span m='244940'>down</span> <span m='245360'>by</span>
  <span m='246200'>1</span> <span m='246410'>over</span> <span
  m='246620'>the</span> <span m='246740'>square</span> <span
  m='247040'>root</span> <span m='247220'>of</span> <span m='247340'>2.</span>
  <span m='248570'>And</span> <span m='249290'>the</span> <span
  m='249470'>other</span> <span m='249860'>important</span> <span
  m='250370'>characteristic</span> <span m='251510'>is</span> <span
  m='251810'>that</span> <span m='252860'>the</span> <span
  m='253160'>frequency</span> <span m='253760'>response</span> <span
  m='255080'>is</span> <span m='255530'>a</span> <span
  m='255620'>monotonic</span> <span m='256370'>function</span> <span
  m='257000'>of</span> <span m='257149'>capital</span> <span
  m='257630'>Omega.</span> <span m='258589'>So</span> <span
  m='258769'>that</span> <span m='259130'>as</span> <span
  m='259459'>capital</span> <span m='259940'>Omega</span> <span
  m='260870'>increases</span> <span m='261500'>from</span> <span
  m='261680'>0</span> <span m='262340'>to</span> <span
  m='262490'>infinity,</span> <span m='263720'>the</span> <span
  m='263810'>magnitude</span> <span m='264710'>or</span> <span
  m='264920'>the</span> <span m='265010'>frequency</span> <span
  m='265520'>response</span> <span m='266180'>is</span> <span
  m='266330'>a</span> <span m='266400'>monotonic</span> <span
  m='267050'>function.</span> </p><p><span m='268990'>Well,</span> <span
  m='269250'>we</span> <span m='269430'>observed</span> <span
  m='269970'>that</span> <span m='270480'>the</span> <span
  m='270570'>cutoff</span> <span m='270990'>frequency,</span> <span
  m='271620'>the</span> <span m='271740'>parameter</span> <span
  m='272250'>omega</span> <span m='272660'>sub</span> <span m='273035'>c,</span>
  <span m='275540'>adjusts</span> <span m='276170'>in</span> <span
  m='276290'>a</span> <span m='276350'>sense</span> <span
  m='277430'>where</span> <span m='278180'>we</span> <span
  m='278540'>might</span> <span m='278990'>divide</span> <span
  m='279500'>the</span> <span m='279590'>frequency</span> <span
  m='280100'>characteristic</span> <span m='280970'>into</span> <span
  m='281180'>passband,</span> <span m='282410'>transition</span> <span
  m='282980'>band,</span> <span m='283480'>and</span> <span
  m='283580'>stopband.</span> <span m='285530'>We</span> <span
  m='285650'>have</span> <span m='285860'>another</span> <span
  m='286160'>parameter,</span> <span m='286760'>which</span> <span
  m='287030'>is</span> <span m='287450'>the</span> <span
  m='287540'>parameter</span> <span m='288090'>N,</span> <span
  m='288770'>the</span> <span m='288890'>order</span> <span m='289160'>of</span>
  <span m='289250'>the</span> <span m='289370'>filter.</span> <span
  m='290540'>And</span> <span m='291230'>basically</span> <span
  m='292160'>the</span> <span m='292310'>effect</span> <span
  m='292940'>that</span> <span m='293360'>the</span> <span
  m='293450'>parameter</span> <span m='294050'>N</span> <span
  m='294290'>has</span> <span m='295220'>is</span> <span m='295490'>to</span>
  <span m='295850'>affect</span> <span m='296660'>the</span> <span
  m='296780'>shape</span> <span m='297470'>of</span> <span
  m='297620'>this</span> <span m='297830'>frequency</span> <span
  m='298400'>response</span> <span m='299720'>in</span> <span
  m='299840'>the</span> <span m='299930'>sense</span> <span
  m='300500'>that</span> <span m='300740'>if</span> <span
  m='301220'>capital</span> <span m='301730'>N</span> <span m='302000'>is</span>
  <span m='302180'>larger,</span> <span m='304340'>the</span> <span
  m='304430'>frequency</span> <span m='304970'>response</span> <span
  m='306230'>tends</span> <span m='306590'>to</span> <span m='306770'>be</span>
  <span m='307040'>flatter</span> <span m='308120'>longer,</span> <span
  m='309530'>so</span> <span m='309740'>that</span> <span m='310580'>for</span>
  <span m='310760'>a</span> <span m='310820'>larger</span> <span
  m='311085'>N</span> <span m='311590'>than</span> <span m='312290'>what</span>
  <span m='312500'>I've</span> <span m='312650'>drawn</span> <span
  m='312920'>with</span> <span m='313040'>the</span> <span
  m='313130'>black</span> <span m='313430'>curve,</span> <span
  m='314270'>the</span> <span m='314360'>frequency</span> <span
  m='314840'>response</span> <span m='315350'>might</span> <span
  m='315590'>look</span> <span m='316370'>more</span> <span
  m='316550'>like</span> <span m='316850'>this</span> <span
  m='317300'>and</span> <span m='317450'>then</span> <span
  m='318650'>drop</span> <span m='319010'>off</span> <span
  m='319280'>sharper.</span> <span m='321150'>Whereas</span> <span
  m='322050'>if</span> <span m='323040'>capital</span> <span m='323550'>N</span>
  <span m='323820'>is</span> <span m='323970'>smaller,</span> <span
  m='325080'>then</span> <span m='325410'>it</span> <span m='325500'>will</span>
  <span m='325650'>be</span> <span m='325800'>less</span> <span
  m='326160'>flat</span> <span m='327060'>in</span> <span m='327210'>the</span>
  <span m='327300'>passband</span> <span m='328350'>and</span> <span
  m='328500'>drop</span> <span m='328830'>off</span> <span
  m='329070'>more</span> <span m='329250'>slowly.</span> </p><p><span
  m='330430'>So</span> <span m='330750'>in</span> <span m='330900'>fact,</span>
  <span m='331300'>the</span> <span m='331400'>way</span> <span
  m='331470'>that</span> <span m='331590'>I've</span> <span
  m='331740'>drawn</span> <span m='332070'>it</span> <span
  m='332160'>here,</span> <span m='334760'>this</span> <span
  m='335090'>is</span> <span m='335270'>the</span> <span
  m='335390'>behavior</span> <span m='336200'>of</span> <span
  m='336380'>the</span> <span m='336470'>frequency</span> <span
  m='336980'>response</span> <span m='337550'>curve</span> <span
  m='338480'>as</span> <span m='339170'>the</span> <span
  m='339290'>parameter</span> <span m='340520'>capital</span> <span
  m='341030'>N</span> <span m='343130'>increases.</span> <span
  m='344780'>So,</span> <span m='345560'>the</span> <span
  m='345680'>higher</span> <span m='345980'>the</span> <span
  m='346130'>order</span> <span m='346430'>of</span> <span m='346520'>the</span>
  <span m='346640'>filter,</span> <span m='347630'>the</span> <span
  m='347720'>sharper</span> <span m='348740'>the</span> <span
  m='349970'>drop</span> <span m='350630'>from</span> <span
  m='351680'>what</span> <span m='351890'>we</span> <span
  m='352040'>could</span> <span m='352190'>consider</span> <span
  m='352640'>as</span> <span m='352760'>a</span> <span
  m='352820'>passband</span> <span m='353450'>region</span> <span
  m='353990'>into</span> <span m='354260'>a</span> <span
  m='354320'>stopband</span> <span m='354920'>region.</span> <span
  m='356270'>And</span> <span m='356660'>obviously</span> <span
  m='357230'>then,</span> <span m='357950'>the</span> <span
  m='358040'>sharper</span> <span m='358460'>the</span> <span
  m='358580'>filter</span> <span m='358940'>we</span> <span
  m='359090'>want,</span> <span m='359870'>the</span> <span
  m='360080'>higher</span> <span m='360620'>order</span> <span
  m='361130'>filter</span> <span m='361520'>we</span> <span
  m='361670'>would</span> <span m='361820'>design.</span> </p><p><span
  m='364430'>Now,</span> <span m='365000'>to</span> <span m='365360'>look</span>
  <span m='365630'>at</span> <span m='365780'>the</span> <span
  m='366710'>pole</span> <span m='367010'>0</span> <span
  m='367400'>pattern</span> <span m='367880'>or</span> <span
  m='368300'>the</span> <span m='368390'>0</span> <span
  m='368720'>pattern</span> <span m='369410'>really</span> <span
  m='369920'>of</span> <span m='370580'>the</span> <span
  m='370970'>Butterworth</span> <span m='371510'>filter,</span> <span
  m='373470'>we</span> <span m='373520'>can</span> <span
  m='373730'>convert</span> <span m='374120'>this</span> <span
  m='374330'>expression</span> <span m='376010'>into</span> <span
  m='376670'>an</span> <span m='376790'>expression</span> <span
  m='377570'>relating</span> <span m='379070'>the</span> <span
  m='380180'>magnitude</span> <span m='380810'>squared</span> <span
  m='381140'>function</span> <span m='381560'>expressed</span> <span
  m='382160'>in</span> <span m='382310'>terms</span> <span m='382790'>of</span>
  <span m='382910'>the</span> <span m='383000'>Laplace</span> <span
  m='383450'>transform</span> <span m='384380'>variable</span> <span
  m='384950'>s.</span> <span m='386240'>And</span> <span m='387110'>so</span>
  <span m='387710'>this</span> <span m='387980'>expression</span> <span
  m='388730'>corresponds</span> <span m='389690'>to</span> <span
  m='390650'>the</span> <span m='390770'>product</span> <span
  m='391250'>H</span> <span m='391520'>sub</span> <span m='391610'>a</span>
  <span m='391810'>of</span> <span m='391970'>s</span> <span
  m='392360'>times</span> <span m='392660'>H</span> <span m='392870'>sub
  a</span> <span m='393200'>of</span> <span m='393290'>minus</span> <span
  m='393740'>s,</span> <span m='394730'>evaluated</span> <span
  m='395870'>at</span> <span m='396200'>s</span> <span m='396500'>equals</span>
  <span m='396860'>j</span> <span m='397510'>omega,</span> <span
  m='399230'>in</span> <span m='399320'>which</span> <span
  m='399560'>case</span> <span m='400850'>the</span> <span m='400970'>j</span>
  <span m='401240'>omega</span> <span m='401840'>is</span> <span
  m='402050'>what</span> <span m='402170'>corresponds</span> <span
  m='402890'>to</span> <span m='403040'>s,</span> <span m='404060'>and</span>
  <span m='404480'>so</span> <span m='404810'>H</span> <span m='405100'>sub
  a</span> <span m='405350'>of</span> <span m='405560'>s</span> <span
  m='406160'>times</span> <span m='406430'>H</span> <span m='406710'>sub
  a</span> <span m='406800'>of</span> <span m='407110'>minus</span> <span
  m='407490'>s</span> <span m='408670'>is</span> <span m='409040'>of</span>
  <span m='409190'>the</span> <span m='409280'>form</span> <span
  m='410120'>1</span> <span m='410360'>over</span> <span m='410720'>1</span>
  <span m='411020'>plus</span> <span m='411590'>s</span> <span
  m='412250'>divided</span> <span m='412730'>by</span> <span m='412940'>j</span>
  <span m='413330'>omega</span> <span m='413780'>sub</span> <span
  m='414155'>c</span> <span m='415480'>raised</span> <span m='416140'>to</span>
  <span m='416270'>the</span> <span m='416390'>2N</span> <span
  m='416810'>power.</span> </p><p><span m='418650'>Well,</span> <span
  m='419040'>what</span> <span m='419250'>we</span> <span
  m='419370'>recognize</span> <span m='420330'>is</span> <span
  m='420600'>that</span> <span m='421440'>this</span> <span
  m='422250'>expression</span> <span m='423930'>has</span> <span
  m='424200'>poles,</span> <span m='425040'>if</span> <span m='425220'>we</span>
  <span m='425340'>solve</span> <span m='425700'>this</span> <span
  m='425910'>equation.</span> <span m='427200'>This</span> <span
  m='427380'>expression</span> <span m='428070'>has</span> <span
  m='428340'>poles</span> <span m='429430'>at</span> <span m='429690'>of</span>
  <span m='429780'>course</span> <span m='430050'>the</span> <span
  m='430170'>roots</span> <span m='430470'>of</span> <span m='430560'>the</span>
  <span m='430680'>denominator</span> <span m='431310'>polynomial</span> <span
  m='432210'>or</span> <span m='432610'>at</span> <span m='433280'>s</span>
  <span m='433735'>sub</span> <span m='434190'>p</span> <span
  m='434460'>equal</span> <span m='434790'>to</span> <span
  m='434940'>minus</span> <span m='435360'>1</span> <span m='435690'>to</span>
  <span m='435850'>the</span> <span m='435930'>over</span> <span
  m='436350'>2N</span> <span m='437400'>times</span> <span m='438030'>j</span>
  <span m='438480'>omega</span> <span m='438920'>sub</span> <span
  m='439375'>c.</span> <span m='439830'>That's</span> <span
  m='440130'>simply</span> <span m='440670'>solving</span> <span
  m='441120'>the</span> <span m='441240'>equation</span> <span
  m='442110'>with</span> <span m='442290'>this</span> <span
  m='442440'>denominator</span> <span m='443040'>polynomial</span> <span
  m='444060'>equal</span> <span m='444360'>to</span> <span m='444510'>0.</span>
  <span m='446830'>Well,</span> <span m='447790'>we</span> <span
  m='447970'>can</span> <span m='448600'>see</span> <span m='449260'>more</span>
  <span m='449440'>specifically</span> <span m='450460'>where</span> <span
  m='450700'>these</span> <span m='450910'>poles</span> <span
  m='451450'>lie</span> <span m='452020'>in</span> <span m='452380'>the</span>
  <span m='453120'>s</span> <span m='453440'>plane</span> <span
  m='454990'>by</span> <span m='455170'>recognizing</span> <span
  m='456040'>that</span> <span m='456190'>these</span> <span
  m='456550'>are</span> <span m='456790'>the</span> <span m='456910'>2N</span>
  <span m='457780'>roots</span> <span m='458080'>of</span> <span
  m='458170'>minus</span> <span m='458560'>1.</span> <span m='460870'>And</span>
  <span m='461770'>then</span> <span m='462040'>we</span> <span
  m='462190'>have</span> <span m='462370'>a</span> <span m='462460'>j,</span>
  <span m='462820'>which</span> <span m='463030'>corresponds</span> <span
  m='464020'>to</span> <span m='466520'>e to</span> <span m='466930'>the</span>
  <span m='467020'>j</span> <span m='467230'>pi</span> <span
  m='467530'>over</span> <span m='467740'>2.</span> <span m='468700'>So</span>
  <span m='468940'>we</span> <span m='469090'>can</span> <span
  m='469300'>rewrite</span> <span m='470290'>this</span> <span
  m='470470'>expression</span> <span m='471220'>for</span> <span
  m='471370'>the</span> <span m='471460'>poles</span> <span m='472810'>as</span>
  <span m='473840'>s sub</span> <span m='474315'>p</span> <span
  m='475630'>equal</span> <span m='476050'>to</span> <span m='476260'>e</span>
  <span m='476500'>to</span> <span m='476560'>the</span> <span
  m='476680'>j</span> <span m='477910'>pi</span> <span m='478870'>over</span>
  <span m='479140'>2N.</span> <span m='483336'>That's</span> <span
  m='483810'>one</span> <span m='484050'>of</span> <span m='484140'>the</span>
  <span m='484590'>roots</span> <span m='485010'>of</span> <span
  m='485160'>minus</span> <span m='485580'>1,</span> <span
  m='486480'>plus</span> <span m='487620'>k</span> <span m='488100'>times</span>
  <span m='488520'>2</span> <span m='488760'>pi</span> <span
  m='489450'>where</span> <span m='489660'>k</span> <span m='489900'>is</span>
  <span m='490020'>an</span> <span m='490140'>integer.</span> </p><p><span
  m='491380'>This</span> <span m='491460'>generates</span> <span
  m='492330'>the</span> <span m='492480'>roots</span> <span m='492780'>of</span>
  <span m='492870'>minus</span> <span m='493290'>1.</span> <span
  m='494790'>We</span> <span m='494910'>need</span> <span m='495060'>to</span>
  <span m='495180'>multiply</span> <span m='495780'>by</span> <span
  m='495990'>j,</span> <span m='496500'>and</span> <span m='496620'>we</span>
  <span m='496740'>can</span> <span m='496920'>do</span> <span
  m='497070'>that</span> <span m='497310'>by</span> <span
  m='497460'>multiplying</span> <span m='498210'>by</span> <span m='498420'>e
  to</span> <span m='498750'>the</span> <span m='498870'>j</span> <span
  m='499080'>pi</span> <span m='499530'>over 2,</span> <span
  m='499980'>which</span> <span m='500220'>is</span> <span
  m='500490'>equal</span> <span m='500820'>to</span> <span m='500940'>j</span>
  <span m='502000'>times</span> <span m='502500'>omega</span> <span
  m='502920'>sub</span> <span m='503325'>c,</span> <span m='503730'>which</span>
  <span m='504000'>is</span> <span m='504540'>the</span> <span
  m='504750'>cutoff</span> <span m='505140'>frequency</span> <span
  m='505680'>parameter</span> <span m='506250'>for</span> <span
  m='506340'>the</span> <span m='506460'>Butterworth</span> <span
  m='506910'>filter.</span> <span m='508680'>So</span> <span
  m='509250'>this</span> <span m='509550'>then</span> <span
  m='509820'>specifies</span> <span m='510990'>where</span> <span
  m='511230'>the</span> <span m='511350'>pole</span> <span
  m='511620'>locations</span> <span m='512370'>are</span> <span
  m='512760'>for</span> <span m='512909'>the</span> <span
  m='513000'>Butterworth</span> <span m='513510'>filter.</span> <span
  m='514470'>For</span> <span m='514620'>example,</span> <span
  m='515620'>if</span> <span m='516000'>we</span> <span
  m='516990'>consider</span> <span m='518250'>the</span> <span
  m='518370'>case,</span> <span m='518940'>let's</span> <span
  m='519150'>say</span> <span m='519390'>with</span> <span m='519539'>n</span>
  <span m='519720'>equal</span> <span m='520020'>to</span> <span
  m='520190'>3,</span> <span m='521743'>k</span> <span m='522690'>let's</span>
  <span m='522929'>say</span> <span m='523200'>equal</span> <span
  m='523470'>to</span> <span m='523650'>0.</span> <span m='525570'>That</span>
  <span m='525780'>says</span> <span m='526140'>then</span> <span
  m='526680'>that</span> <span m='527370'>we</span> <span m='527520'>have</span>
  <span m='527700'>a</span> <span m='527790'>pole</span> <span
  m='528350'>at</span> <span m='528990'>e to</span> <span m='529220'>the</span>
  <span m='529410'>j</span> <span m='529740'>pi</span> <span
  m='530760'>divided</span> <span m='531210'>by</span> <span
  m='531420'>6,</span> <span m='532760'>e to</span> <span m='532940'>the</span>
  <span m='533040'>j</span> <span m='533280'>pi</span> <span
  m='533550'>over</span> <span m='533770'>6,</span> <span
  m='535880'>times</span> <span m='536300'>e</span> <span m='536440'>to</span>
  <span m='536540'>the</span> <span m='536660'>j</span> <span
  m='536900'>pi</span> <span m='537200'>over</span> <span m='537440'>2.</span>
  <span m='538320'>In</span> <span m='538340'>other</span> <span
  m='538580'>words,</span> <span m='539250'>we</span> <span
  m='539330'>have</span> <span m='539540'>a</span> <span m='539600'>pole</span>
  <span m='540170'>in</span> <span m='540320'>the</span> <span
  m='540440'>s</span> <span m='540650'>plane</span> <span m='541670'>at</span>
  <span m='541820'>an</span> <span m='541910'>angle</span> <span
  m='542600'>of</span> <span m='543110'>pi</span> <span m='543410'>over</span>
  <span m='543620'>6</span> <span m='543980'>plus</span> <span
  m='544250'>pi</span> <span m='544520'>over</span> <span m='544760'>2,</span>
  <span m='545570'>which</span> <span m='545750'>corresponds</span> <span
  m='546680'>to</span> <span m='546860'>this</span> <span
  m='547060'>location.</span> </p><p><span m='548870'>Then</span> <span
  m='549410'>we'll</span> <span m='549620'>have</span> <span
  m='550700'>poles</span> <span m='551660'>distributed</span> <span
  m='553460'>in</span> <span m='553650'>angle</span> <span
  m='554750'>around</span> <span m='555200'>a</span> <span
  m='555260'>circle</span> <span m='556160'>in</span> <span
  m='556550'>the</span> <span m='556730'>s</span> <span m='556940'>plane,</span>
  <span m='557830'>distributed</span> <span m='558410'>in</span> <span
  m='558500'>an</span> <span m='558650'>angle</span> <span
  m='559460'>where</span> <span m='559670'>the</span> <span
  m='559820'>angular</span> <span m='560180'>spacing</span> <span
  m='560870'>is</span> <span m='561050'>pi</span> <span m='561350'>over</span>
  <span m='561590'>3.</span> <span m='562400'>The</span> <span
  m='562700'>pi</span> <span m='562970'>over</span> <span m='563180'>3</span>
  <span m='563480'>arising</span> <span m='564530'>from</span> <span
  m='565040'>a</span> <span m='565100'>consideration</span> <span
  m='566120'>of</span> <span m='566480'>2</span> <span m='566930'>pi</span>
  <span m='567300'>k</span> <span m='568010'>divided</span> <span
  m='568430'>by</span> <span m='568640'>2N,</span> <span m='569510'>where</span>
  <span m='569630'>in</span> <span m='569720'>this</span> <span
  m='569870'>case,</span> <span m='570300'>N</span> <span m='570350'>is</span>
  <span m='570470'>equal</span> <span m='570710'>to</span> <span
  m='570830'>6.</span> <span m='572930'>So</span> <span m='573430'>these</span>
  <span m='573700'>poles</span> <span m='574870'>are</span> <span
  m='575020'>distributed</span> <span m='576730'>equally</span> <span
  m='577150'>spaced</span> <span m='577580'>in</span> <span
  m='577690'>angle</span> <span m='579100'>on</span> <span m='579250'>a</span>
  <span m='579280'>circle</span> <span m='580270'>in</span> <span
  m='580420'>the</span> <span m='580540'>s</span> <span m='580750'>plane.</span>
  <span m='582070'>For</span> <span m='582250'>N</span> <span
  m='582410'>equal</span> <span m='582590'>to</span> <span m='582780'>3,</span>
  <span m='583060'>the</span> <span m='583180'>angular</span> <span
  m='583540'>spacing</span> <span m='584050'>is</span> <span
  m='584140'>pi</span> <span m='584470'>over</span> <span m='584680'>3.</span>
  <span m='585810'>For</span> <span m='585970'>k</span> <span m='586420'>equal
  to</span> <span m='586540'>0</span> <span m='588040'>that</span> <span
  m='588190'>first</span> <span m='588490'>pole</span> <span
  m='589000'>corresponds</span> <span m='589720'>to</span> <span
  m='589870'>this</span> <span m='590110'>one,</span> <span
  m='590500'>and</span> <span m='590650'>then</span> <span m='590800'>we</span>
  <span m='590890'>continue</span> <span m='591430'>around.</span> </p><p><span
  m='593040'>Now</span> <span m='593490'>these</span> <span
  m='593730'>are</span> <span m='593790'>poles</span> <span
  m='594180'>distributed</span> <span m='594810'>on</span> <span
  m='594930'>a</span> <span m='594990'>circle,</span> <span
  m='596430'>which</span> <span m='596640'>tends</span> <span
  m='597000'>to</span> <span m='597120'>look</span> <span m='597360'>like</span>
  <span m='598740'>the</span> <span m='598860'>z</span> <span
  m='599070'>plane.</span> <span m='599910'>But</span> <span m='600210'>I</span>
  <span m='600330'>stress</span> <span m='600990'>that</span> <span
  m='601710'>what</span> <span m='601890'>we're</span> <span
  m='602010'>talking</span> <span m='602460'>about</span> <span
  m='602940'>here</span> <span m='603360'>is</span> <span m='603630'>the
  s</span> <span m='603960'>plane.</span> <span m='604410'>In</span> <span
  m='604500'>particular,</span> <span m='604920'>we're</span> <span
  m='605040'>talking</span> <span m='605460'>about</span> <span
  m='606330'>the</span> <span m='606600'>analog</span> <span
  m='607290'>frequency</span> <span m='607830'>response</span> <span
  m='609360'>design</span> <span m='609780'>as</span> <span
  m='609990'>the</span> <span m='610080'>class</span> <span m='610470'>of</span>
  <span m='610650'>analog</span> <span m='611220'>Butterworth</span> <span
  m='611760'>filters,</span> <span m='612730'>which</span> <span
  m='612810'>we're</span> <span m='612960'>then</span> <span
  m='613170'>going</span> <span m='613410'>to</span> <span m='613530'>map</span>
  <span m='614040'>to</span> <span m='614340'>digital</span> <span
  m='614730'>filters.</span> <span m='615630'>So</span> <span
  m='616200'>this</span> <span m='616530'>is</span> <span m='616740'>a</span>
  <span m='616800'>circle</span> <span m='617430'>in</span> <span m='617550'>the
  s</span> <span m='617850'>plane.</span> <span m='618840'>It's</span> <span
  m='619230'>often</span> <span m='619590'>referred</span> <span
  m='619950'>to</span> <span m='620130'>as</span> <span m='620250'>the</span>
  <span m='620340'>Butterworth</span> <span m='620910'>circle.</span> <span
  m='621870'>And</span> <span m='622110'>it</span> <span m='622200'>has</span>
  <span m='622410'>a</span> <span m='622470'>radius</span> <span
  m='623310'>which</span> <span m='623700'>is</span> <span
  m='624150'>equal</span> <span m='624570'>to</span> <span
  m='625320'>omega</span> <span m='625800'>sub</span> <span m='626055'>c.</span>
  </p><p><span m='628320'>In</span> <span m='628860'>designing</span> <span
  m='630470'>an</span> <span m='630780'>analog</span> <span
  m='631290'>Butterworth</span> <span m='631800'>filter</span> <span
  m='632550'>then,</span> <span m='633240'>the</span> <span
  m='633330'>procedure</span> <span m='634380'>is</span> <span
  m='635370'>to</span> <span m='636480'>appropriately</span> <span
  m='637830'>choose</span> <span m='638720'>the</span> <span
  m='638960'>parameters</span> <span m='639660'>omega</span> <span
  m='640080'>sub</span> <span m='640455'>c</span> <span m='640830'>and</span>
  <span m='640950'>capital</span> <span m='641490'>N.</span> <span
  m='642120'>Those</span> <span m='642360'>are</span> <span
  m='642420'>the</span> <span m='642510'>parameters</span> <span
  m='643050'>of</span> <span m='643110'>the</span> <span
  m='643260'>analog</span> <span m='643710'>Butterworth</span> <span
  m='644220'>filter.</span> <span m='645840'>And</span> <span
  m='646530'>then</span> <span m='647840'>from</span> <span
  m='649740'>the</span> <span m='650220'>poles</span> <span
  m='651000'>distributed</span> <span m='651750'>on</span> <span
  m='651900'>the</span> <span m='651990'>Butterworth</span> <span
  m='652530'>circle,</span> <span m='653760'>this</span> <span
  m='654180'>gives</span> <span m='654600'>us</span> <span m='655140'>the</span>
  <span m='655260'>pole</span> <span m='655530'>locations</span> <span
  m='656850'>for</span> <span m='657030'>the</span> <span
  m='657150'>product,</span> <span m='658240'>H</span> <span m='658630'>sub
  a</span> <span m='659040'>of</span> <span m='659160'>s</span> <span
  m='660180'>times</span> <span m='661030'>H</span> <span m='661320'>sub</span>
  <span m='661650'>a</span> <span m='662550'>of</span> <span
  m='662700'>minus</span> <span m='663200'>s.</span> </p><p><span
  m='664970'>We</span> <span m='665090'>can</span> <span m='665240'>then</span>
  <span m='665420'>simply</span> <span m='666230'>associate</span> <span
  m='667730'>with</span> <span m='668450'>the</span> <span
  m='668540'>transfer</span> <span m='669020'>function</span> <span
  m='669500'>H</span> <span m='669815'>sub a</span> <span m='670130'>of</span>
  <span m='670300'>s.</span> <span m='671180'>The</span> <span
  m='671300'>poles</span> <span m='671930'>in</span> <span m='672050'>the</span>
  <span m='672110'>left</span> <span m='672410'>half</span> <span
  m='672710'>plane,</span> <span m='673490'>to</span> <span
  m='673610'>generate</span> <span m='674060'>a</span> <span
  m='674120'>stable</span> <span m='674570'>filter,</span> <span
  m='675590'>and</span> <span m='676370'>then</span> <span m='676850'>the</span>
  <span m='677090'>ones</span> <span m='678020'>which</span> <span
  m='678200'>are</span> <span m='678290'>contributed</span> <span
  m='678920'>by</span> <span m='679130'>the</span> <span
  m='679220'>factor</span> <span m='679760'>H</span> <span m='680010'>sub</span>
  <span m='680480'>a of</span> <span m='680630'>minus</span> <span
  m='681060'>s</span> <span m='681740'>are</span> <span m='682190'>the</span>
  <span m='682310'>corresponding</span> <span m='683180'>image</span> <span
  m='683810'>poles</span> <span m='684380'>in</span> <span m='684500'>the</span>
  <span m='684590'>right</span> <span m='684800'>half</span> <span
  m='685040'>plane.</span> <span m='686200'>The</span> <span
  m='686630'>procedure</span> <span m='687140'>then</span> <span
  m='687440'>is</span> <span m='687650'>to</span> <span m='687770'>design</span>
  <span m='688160'>a</span> <span m='688220'>squared</span> <span
  m='688610'>magnitude</span> <span m='689210'>function.</span> <span
  m='691800'>Talking</span> <span m='692220'>about</span> <span
  m='692490'>a</span> <span m='692550'>Butterworth</span> <span
  m='693060'>filter,</span> <span m='693810'>we</span> <span
  m='694350'>choose</span> <span m='694680'>these</span> <span
  m='694860'>parameters</span> <span m='695400'>omega</span> <span
  m='695820'>sub</span> <span m='695940'>c</span> <span m='696375'>and N.</span>
  <span m='697230'>That</span> <span m='697410'>tells</span> <span
  m='697770'>us</span> <span m='697980'>where</span> <span m='698190'>the</span>
  <span m='698310'>poles</span> <span m='698670'>are</span> <span
  m='698760'>located</span> <span m='699300'>on</span> <span
  m='699420'>the</span> <span m='699510'>Butterworth</span> <span
  m='699990'>circle.</span> <span m='702150'>From</span> <span
  m='703050'>the</span> <span m='703350'>pole</span> <span
  m='703620'>locations</span> <span m='704310'>for</span> <span
  m='704430'>the</span> <span m='704520'>squared</span> <span
  m='704910'>magnitude</span> <span m='705480'>function,</span> <span
  m='706320'>then</span> <span m='706770'>we</span> <span m='706890'>can</span>
  <span m='707070'>factor</span> <span m='707550'>that</span> <span
  m='708270'>into</span> <span m='708690'>H</span> <span m='709020'>sub</span>
  <span m='709110'>a</span> <span m='709320'>of</span> <span m='709440'>s</span>
  <span m='710040'>times</span> <span m='710310'>H</span> <span m='710520'>sub
  a</span> <span m='710880'>of minus</span> <span m='711300'>s,</span> <span
  m='711960'>by</span> <span m='712110'>choosing</span> <span
  m='712740'>the</span> <span m='712860'>poles</span> <span
  m='713620'>that</span> <span m='713760'>fall</span> <span m='714270'>in</span>
  <span m='714390'>the</span> <span m='714450'>left</span> <span
  m='714690'>half</span> <span m='714960'>plane,</span> <span
  m='715680'>to</span> <span m='716400'>give</span> <span m='716580'>us</span>
  <span m='716820'>a</span> <span m='716880'>causal,</span> <span
  m='717430'>stable</span> <span m='718580'>analog</span> <span
  m='719010'>filter.</span> </p><p><span m='721860'>All</span> <span
  m='721920'>right.</span> <span m='722130'>Well,</span> <span
  m='722610'>that</span> <span m='722970'>is</span> <span m='724110'>an</span>
  <span m='724230'>analog</span> <span m='724740'>filter.</span> <span
  m='725970'>What</span> <span m='726180'>we</span> <span
  m='726330'>would</span> <span m='726450'>like</span> <span
  m='726660'>to</span> <span m='726750'>talk</span> <span
  m='727110'>about</span> <span m='727590'>is</span> <span m='727830'>the</span>
  <span m='727920'>design</span> <span m='728520'>of</span> <span
  m='728670'>a</span> <span m='728730'>digital</span> <span
  m='729120'>filter.</span> <span m='730500'>And</span> <span
  m='731040'>the</span> <span m='731160'>procedure</span> <span
  m='731670'>that</span> <span m='731820'>we're</span> <span
  m='731970'>going</span> <span m='732210'>to</span> <span m='732330'>go</span>
  <span m='732540'>through</span> <span m='733140'>is</span> <span
  m='733890'>to</span> <span m='734400'>choose</span> <span m='734670'>a</span>
  <span m='734730'>set</span> <span m='734940'>of</span> <span
  m='735000'>specs</span> <span m='735690'>for</span> <span
  m='735810'>the</span> <span m='735900'>digital</span> <span
  m='736290'>filter,</span> <span m='738600'>and</span> <span
  m='739140'>then</span> <span m='739380'>decide</span> <span
  m='739890'>on</span> <span m='739980'>what</span> <span m='740130'>the</span>
  <span m='740220'>corresponding</span> <span m='741060'>specifications</span>
  <span m='742230'>should</span> <span m='742440'>be</span> <span
  m='743040'>for</span> <span m='743190'>the</span> <span
  m='743340'>analog</span> <span m='743910'>filter,</span> <span
  m='744330'>depending</span> <span m='744720'>on</span> <span
  m='744810'>whether</span> <span m='745050'>we're</span> <span
  m='745170'>using</span> <span m='745470'>impulse</span> <span
  m='745920'>invariance</span> <span m='746580'>or</span> <span
  m='746640'>the</span> <span m='746760'>bilinear</span> <span
  m='747270'>transformation,</span> <span m='749130'>design</span> <span
  m='749970'>the</span> <span m='750180'>analog</span> <span
  m='750690'>filter,</span> <span m='751710'>and</span> <span
  m='751860'>then</span> <span m='752310'>map</span> <span m='752640'>the</span>
  <span m='752760'>result</span> <span m='754200'>to</span> <span
  m='754380'>a</span> <span m='754440'>digital</span> <span
  m='754830'>filter</span> <span m='755640'>using</span> <span
  m='756300'>one</span> <span m='756510'>of</span> <span m='756600'>those</span>
  <span m='756840'>two</span> <span m='757020'>techniques.</span> </p><p><span
  m='759300'>So</span> <span m='759480'>let's</span> <span
  m='759780'>choose</span> <span m='760560'>a</span> <span m='760650'>set</span>
  <span m='761130'>of</span> <span m='761580'>digital</span> <span
  m='761970'>filter</span> <span m='762360'>specifications</span> <span
  m='764070'>for</span> <span m='764760'>a</span> <span
  m='764820'>digital</span> <span m='765570'>lowpass</span> <span
  m='766170'>filter</span> <span m='767670'>with</span> <span
  m='768060'>a</span> <span m='768120'>passband</span> <span
  m='769890'>which</span> <span m='770490'>occurs</span> <span
  m='771900'>for</span> <span m='772170'>frequencies</span> <span
  m='773980'>now</span> <span m='774270'>in</span> <span m='774390'>the</span>
  <span m='774480'>digital</span> <span m='774870'>domain,</span> <span
  m='775710'>for</span> <span m='775830'>frequencies</span> <span
  m='776460'>below</span> <span m='777330'>0.2</span> <span
  m='778050'>pi,</span> <span m='780030'>and</span> <span m='780720'>a</span>
  <span m='780780'>stopband</span> <span m='781920'>region</span> <span
  m='782940'>that</span> <span m='783150'>occurs</span> <span
  m='783570'>for</span> <span m='783720'>frequencies</span> <span
  m='784410'>greater</span> <span m='784830'>than</span> <span
  m='785160'>0.3</span> <span m='785760'>pi,</span> <span m='787050'>and</span>
  <span m='787410'>the</span> <span m='787530'>transition</span> <span
  m='788130'>band</span> <span m='788520'>then,</span> <span
  m='788880'>of</span> <span m='789000'>course,</span> <span
  m='789450'>is</span> <span m='789600'>the</span> <span
  m='789720'>region</span> <span m='790110'>in</span> <span
  m='790230'>between</span> <span m='790800'>those.</span> </p><p><span
  m='793370'>So,</span> <span m='794690'>we</span> <span m='795260'>would</span>
  <span m='795440'>like</span> <span m='795680'>to</span> <span
  m='795800'>design</span> <span m='796640'>a</span> <span
  m='797540'>digital</span> <span m='798140'>filter,</span> <span
  m='799310'>which</span> <span m='800060'>stays</span> <span
  m='800480'>within</span> <span m='800810'>some</span> <span
  m='801080'>limits</span> <span m='801680'>in</span> <span
  m='802280'>this</span> <span m='802460'>passband</span> <span
  m='803090'>region,</span> <span m='804020'>drops</span> <span
  m='804380'>below</span> <span m='805070'>some</span> <span
  m='805430'>limit,</span> <span m='805910'>delta</span> <span m='806290'>sub
  s</span> <span m='806740'>in</span> <span m='806850'>the</span> <span
  m='806930'>stopband</span> <span m='807560'>region.</span> <span
  m='808670'>And</span> <span m='809180'>we'll</span> <span
  m='809360'>choose</span> <span m='809930'>as</span> <span
  m='810770'>the</span> <span m='810860'>limits</span> <span
  m='811370'>in</span> <span m='811490'>the</span> <span
  m='811550'>passband,</span> <span m='812810'>unity</span> <span
  m='813260'>for</span> <span m='813410'>the</span> <span
  m='813560'>upper</span> <span m='813800'>limit</span> <span
  m='814520'>and</span> <span m='814670'>1</span> <span m='814880'>minus</span>
  <span m='815300'>delta</span> <span m='815630'>sub</span> <span
  m='815975'>p</span> <span m='816560'>for</span> <span m='816710'>the</span>
  <span m='816830'>lower</span> <span m='817100'>limit.</span> <span
  m='818390'>Where</span> <span m='819110'>delta</span> <span
  m='820130'>1</span> <span m='820340'>minus</span> <span
  m='820670'>delta</span> <span m='820990'>sub p</span> <span
  m='822290'>might</span> <span m='822560'>not</span> <span
  m='822860'>and</span> <span m='823010'>in</span> <span m='823070'>fact</span>
  <span m='823400'>it</span> <span m='823490'>won't</span> <span
  m='824300'>turn</span> <span m='824570'>out</span> <span m='825020'>to</span>
  <span m='825170'>be</span> <span m='825350'>1</span> <span
  m='825530'>over</span> <span m='825740'>the</span> <span
  m='825830'>square</span> <span m='826160'>root</span> <span
  m='826370'>of</span> <span m='826460'>2,</span> <span m='827100'>in</span>
  <span m='827120'>other</span> <span m='827330'>words,</span> <span
  m='828300'>this</span> <span m='828770'>cutoff</span> <span
  m='829130'>frequency</span> <span m='830390'>will</span> <span
  m='830510'>not</span> <span m='830720'>necessarily</span> <span
  m='831710'>correspond</span> <span m='832520'>to</span> <span
  m='832640'>the</span> <span m='832760'>parameter</span> <span
  m='833860'>omega</span> <span m='834320'>sub</span> <span m='834725'>c</span>
  <span m='835130'>for</span> <span m='835280'>the</span> <span
  m='835400'>Butterworth</span> <span m='835850'>filter.</span> </p><p><span
  m='838110'>All</span> <span m='838170'>right.</span> <span
  m='838350'>Well,</span> <span m='838650'>so</span> <span
  m='838830'>let's</span> <span m='839100'>choose</span> <span
  m='839430'>a</span> <span m='839610'>set</span> <span m='839880'>of</span>
  <span m='839940'>specifications.</span> <span m='841950'>The</span> <span
  m='842040'>ones</span> <span m='842280'>that</span> <span
  m='842400'>I've</span> <span m='842550'>chosen</span> <span
  m='843240'>are</span> <span m='843780'>the</span> <span
  m='844200'>requirement</span> <span m='845250'>that</span> <span
  m='845820'>the</span> <span m='845910'>frequency</span> <span
  m='846420'>response</span> <span m='846930'>characteristic</span> <span
  m='848610'>be</span> <span m='849570'>within</span> <span
  m='850290'>1db</span> <span m='851970'>of</span> <span m='852150'>unity</span>
  <span m='852810'>in</span> <span m='852960'>the</span> <span
  m='853050'>passband.</span> <span m='854340'>In</span> <span
  m='854460'>other</span> <span m='854640'>words,</span> <span
  m='854980'>the</span> <span m='855000'>requirement</span> <span
  m='855690'>that</span> <span m='855810'>1</span> <span m='856080'>minus</span>
  <span m='856440'>deltas</span> <span m='856830'>sub</span> <span
  m='857160'>p</span> <span m='857880'>be</span> <span m='858000'>greater</span>
  <span m='858360'>than</span> <span m='858510'>or</span> <span
  m='858630'>equal</span> <span m='858900'>to</span> <span
  m='859020'>minus</span> <span m='859410'>1db.</span> <span
  m='860970'>So</span> <span m='861720'>this</span> <span
  m='862260'>deviation</span> <span m='863220'>must</span> <span
  m='863430'>be</span> <span m='863580'>less</span> <span m='863850'>than</span>
  <span m='864000'>1db.</span> <span m='866080'>And</span> <span
  m='866220'>then</span> <span m='866340'>the</span> <span
  m='866460'>requirement</span> <span m='867090'>that</span> <span
  m='867240'>in</span> <span m='867330'>the</span> <span
  m='867450'>stopband</span> <span m='868800'>the</span> <span
  m='868890'>frequency</span> <span m='869400'>response</span> <span
  m='869910'>characteristic</span> <span m='871260'>is</span> <span
  m='871440'>below</span> <span m='874200'>minus</span> <span
  m='874560'>15db.</span> <span m='875550'>In</span> <span
  m='875700'>other</span> <span m='875910'>words,</span> <span
  m='876710'>the</span> <span m='876810'>stopband</span> <span
  m='877320'>attenuation</span> <span m='878580'>for</span> <span
  m='878720'>frequencies</span> <span m='879300'>greater</span> <span
  m='879630'>than</span> <span m='879750'>0.3</span> <span m='880320'>pi</span>
  <span m='880800'>is</span> <span m='880980'>greater</span> <span
  m='881490'>than</span> <span m='882810'>minus</span> <span
  m='884040'>15db.</span> <span m='885090'>It's</span> <span
  m='885270'>further</span> <span m='885660'>down</span> <span
  m='886560'>than</span> <span m='886710'>minus</span> <span
  m='887040'>15db.</span> <span m='888270'>So</span> <span
  m='888430'>delta</span> <span m='888800'>sub s</span> <span
  m='889200'>is</span> <span m='889350'>less</span> <span m='889620'>than</span>
  <span m='889770'>or</span> <span m='889860'>equal</span> <span
  m='890130'>to</span> <span m='890250'>minus</span> <span
  m='890610'>15db.</span> </p><p><span m='892500'>The</span> <span
  m='892860'>one</span> <span m='893130'>other</span> <span
  m='893670'>specification</span> <span m='894630'>that</span> <span
  m='894750'>we'll</span> <span m='894930'>impose,</span> <span
  m='895980'>or</span> <span m='896400'>in</span> <span m='896490'>fact,</span>
  <span m='897100'>it's</span> <span m='897540'>really</span> <span
  m='898410'>a</span> <span m='898470'>consequence</span> <span
  m='899130'>that</span> <span m='899220'>will</span> <span
  m='899430'>result</span> <span m='900000'>from</span> <span
  m='900180'>using</span> <span m='900510'>a</span> <span
  m='900570'>Butterworth</span> <span m='901080'>filter,</span> <span
  m='902070'>is</span> <span m='902880'>the</span> <span m='903570'>fact</span>
  <span m='904110'>that</span> <span m='904260'>the</span> <span
  m='904350'>frequency</span> <span m='904800'>characteristic</span> <span
  m='905610'>is</span> <span m='905730'>monotonic.</span> <span
  m='907800'>So</span> <span m='908010'>we</span> <span m='908130'>have</span>
  <span m='908460'>the</span> <span m='908970'>passband</span> <span
  m='909600'>edge,</span> <span m='910350'>the</span> <span
  m='910470'>stopband</span> <span m='911130'>edge,</span> <span
  m='912030'>the</span> <span m='912150'>passband</span> <span
  m='912780'>ripple</span> <span m='913830'>or</span> <span
  m='914430'>deviation,</span> <span m='915330'>and</span> <span
  m='915840'>the</span> <span m='915960'>stopband</span> <span
  m='916730'>ripple</span> <span m='917020'>or</span> <span
  m='917190'>deviation.</span> <span m='918700'>And</span> <span
  m='919440'>we</span> <span m='919620'>can,</span> <span m='920260'>of</span>
  <span m='920280'>course,</span> <span m='921660'>rewrite</span> <span
  m='922200'>these</span> <span m='922370'>specifications</span> <span
  m='924240'>in</span> <span m='924360'>terms</span> <span m='924900'>of</span>
  <span m='925620'>requirements</span> <span m='926790'>on</span> <span
  m='927510'>the</span> <span m='928680'>transfer</span> <span
  m='929250'>function</span> <span m='929610'>or</span> <span
  m='929700'>frequency</span> <span m='930240'>response,</span> <span
  m='931050'>the</span> <span m='931320'>magnitude</span> <span
  m='932790'>of</span> <span m='933510'>the</span> <span
  m='934170'>frequency</span> <span m='934770'>response.</span> </p><p><span
  m='936420'>The</span> <span m='936690'>requirement</span> <span
  m='937680'>that</span> <span m='938190'>the</span> <span
  m='938310'>deviation</span> <span m='939300'>be</span> <span
  m='940440'>less</span> <span m='940770'>than</span> <span
  m='940920'>1db</span> <span m='941760'>in</span> <span m='941850'>the</span>
  <span m='941940'>passband</span> <span m='943800'>is</span> <span
  m='944010'>the</span> <span m='944100'>requirement</span> <span
  m='944790'>then</span> <span m='945510'>that</span> <span m='945630'>20</span>
  <span m='945930'>log</span> <span m='946230'>to</span> <span
  m='946350'>the</span> <span m='946440'>base</span> <span m='946740'>10</span>
  <span m='947670'>of</span> <span m='947790'>the</span> <span
  m='947910'>magnitude</span> <span m='948840'>of</span> <span
  m='949050'>the</span> <span m='949170'>frequency</span> <span
  m='949680'>response--</span> <span m='951030'>that's</span> <span
  m='951540'>the</span> <span m='951810'>deviation</span> <span
  m='952440'>db--</span> <span m='953270'>be</span> <span
  m='953580'>greater</span> <span m='953970'>than</span> <span
  m='954150'>or</span> <span m='954270'>equal</span> <span m='954570'>to</span>
  <span m='954690'>minus</span> <span m='955170'>1,</span> <span
  m='957160'>or</span> <span m='957610'>that</span> <span m='957870'>the</span>
  <span m='957960'>magnitude</span> <span m='958425'>be</span> <span
  m='958890'>greater</span> <span m='959220'>than</span> <span
  m='959350'>or</span> <span m='959450'>equal</span> <span m='959610'>to</span>
  <span m='959760'>10</span> <span m='960480'>to</span> <span
  m='960570'>the</span> <span m='960690'>minus</span> <span
  m='961320'>0.05.</span> <span m='963650'>And</span> <span m='963980'>of</span>
  <span m='964100'>course,</span> <span m='964820'>we</span> <span
  m='965030'>wanted</span> <span m='965330'>also</span> <span
  m='965660'>to</span> <span m='965750'>be</span> <span m='965870'>less</span>
  <span m='966140'>than</span> <span m='966290'>unity,</span> <span
  m='966960'>and</span> <span m='967010'>that's</span> <span
  m='967400'>an</span> <span m='967520'>implied</span> <span
  m='968060'>condition.</span> <span m='969110'>So</span> <span
  m='969620'>it</span> <span m='969740'>must</span> <span m='969980'>be</span>
  <span m='970100'>less</span> <span m='970370'>than</span> <span
  m='970520'>unity,</span> <span m='971090'>and it</span> <span
  m='971210'>must</span> <span m='971390'>be</span> <span
  m='971540'>greater</span> <span m='971900'>than</span> <span
  m='972050'>or</span> <span m='972140'>equal</span> <span m='972440'>to</span>
  <span m='972560'>10</span> <span m='972830'>to</span> <span
  m='972950'>the</span> <span m='973040'>minus</span> <span
  m='973370'>0.05</span> <span m='974740'>for</span> <span
  m='974870'>frequencies</span> <span m='975920'>from</span> <span
  m='976160'>0</span> <span m='977020'>to</span> <span m='977180'>0.2</span>
  <span m='977720'>pi.</span> </p><p><span m='979100'>So</span> <span
  m='979280'>in</span> <span m='979370'>particular,</span> <span
  m='979850'>since</span> <span m='980120'>it's</span> <span
  m='980240'>monotonic,</span> <span m='981560'>we'll</span> <span
  m='982310'>impose</span> <span m='983450'>that</span> <span
  m='984260'>condition</span> <span m='985340'>at</span> <span
  m='986270'>the</span> <span m='986360'>frequency</span> <span
  m='986930'>point</span> <span m='987200'>0.2</span> <span
  m='987410'>pi,</span> <span m='988280'>corresponding</span> <span
  m='989060'>to</span> <span m='989180'>the</span> <span m='989330'>end</span>
  <span m='989570'>of</span> <span m='989660'>the</span> <span
  m='989750'>stopband</span> <span m='990520'>and</span> <span
  m='990830'>the</span> <span m='990890'>beginning</span> <span
  m='991280'>of</span> <span m='991340'>the</span> <span
  m='991460'>transition</span> <span m='992030'>band.</span> <span
  m='993590'>The</span> <span m='993680'>second</span> <span
  m='994040'>condition</span> <span m='994880'>that</span> <span
  m='995390'>we</span> <span m='995570'>impose</span> <span m='996770'>is</span>
  <span m='997400'>the</span> <span m='997520'>condition</span> <span
  m='998330'>that</span> <span m='999780'>by</span> <span m='1000080'>the</span>
  <span m='1000230'>time</span> <span m='1000980'>we</span> <span
  m='1001160'>get</span> <span m='1001490'>to</span> <span
  m='1001820'>omega</span> <span m='1002300'>equal</span> <span
  m='1002630'>to</span> <span m='1002975'>0.3</span> <span
  m='1003320'>pi,</span> <span m='1005160'>we</span> <span
  m='1005340'>would</span> <span m='1005490'>like</span> <span
  m='1006060'>the</span> <span m='1006180'>frequency</span> <span
  m='1006750'>response</span> <span m='1007770'>to</span> <span
  m='1007890'>be</span> <span m='1008040'>down</span> <span
  m='1008790'>at</span> <span m='1008970'>least</span> <span
  m='1009270'>15</span> <span m='1009780'>db,</span> <span
  m='1010770'>and</span> <span m='1011370'>more</span> <span
  m='1011850'>if</span> <span m='1012120'>possible.</span> <span
  m='1012810'>But</span> <span m='1013380'>the</span> <span
  m='1013500'>condition</span> <span m='1014010'>is</span> <span
  m='1014610'>that</span> <span m='1015450'>the</span> <span
  m='1015780'>20</span> <span m='1016080'>log</span> <span m='1016300'>to</span>
  <span m='1016410'>the</span> <span m='1016470'>base</span> <span
  m='1016760'>10</span> <span m='1016860'>of</span> <span m='1016920'>the</span>
  <span m='1017010'>magnitude</span> <span m='1017670'>at</span> <span
  m='1017870'>omega</span> <span m='1018190'>equal</span> <span
  m='1018380'>to</span> <span m='1018480'>0.3</span> <span m='1019020'>pi</span>
  <span m='1019980'>must</span> <span m='1020190'>be</span> <span
  m='1020340'>less</span> <span m='1020670'>than</span> <span
  m='1020820'>or</span> <span m='1020910'>equal</span> <span
  m='1021270'>to</span> <span m='1022500'>minus</span> <span
  m='1022860'>15.</span> <span m='1024310'>So</span> <span
  m='1024420'>this</span> <span m='1024540'>says</span> <span
  m='1025050'>we</span> <span m='1025200'>must</span> <span
  m='1025440'>be</span> <span m='1025530'>further</span> <span
  m='1025890'>down</span> <span m='1026160'>than</span> <span
  m='1026280'>15</span> <span m='1026819'>db,</span> <span m='1027720'>or</span>
  <span m='1027960'>we</span> <span m='1028079'>can</span> <span
  m='1028230'>translate</span> <span m='1028800'>that</span> <span
  m='1029099'>into</span> <span m='1029400'>a</span> <span
  m='1029460'>condition</span> <span m='1030000'>on</span> <span
  m='1030150'>the</span> <span m='1030210'>magnitude,</span> <span
  m='1031480'>so</span> <span m='1031560'>that</span> <span
  m='1031740'>the</span> <span m='1031829'>magnitude</span> <span
  m='1032339'>of</span> <span m='1032400'>that</span> <span
  m='1032579'>frequency</span> <span m='1033089'>is</span> <span
  m='1033210'>less</span> <span m='1033450'>than</span> <span
  m='1033599'>or</span> <span m='1033660'>equal</span> <span
  m='1033900'>to</span> <span m='1034050'>10</span> <span m='1034349'>to</span>
  <span m='1034470'>the</span> <span m='1034560'>minus</span> <span
  m='1035250'>0.75.</span> </p><p><span m='1038790'>Well,</span> <span
  m='1039200'>let's</span> <span m='1039859'>consider</span> <span
  m='1041050'>two--</span> <span m='1042319'>we</span> <span
  m='1042560'>want</span> <span m='1042770'>to</span> <span
  m='1042829'>consider</span> <span m='1043490'>two</span> <span
  m='1043910'>design</span> <span m='1044359'>procedures.</span> <span
  m='1045589'>Let's</span> <span m='1046010'>first</span> <span
  m='1046310'>consider</span> <span m='1047569'>the</span> <span
  m='1047869'>impulse</span> <span m='1048319'>invariant</span> <span
  m='1048860'>design</span> <span m='1049280'>procedure,</span> <span
  m='1050360'>in</span> <span m='1050450'>which</span> <span
  m='1050690'>case</span> <span m='1051020'>we</span> <span
  m='1051170'>would</span> <span m='1051320'>like</span> <span
  m='1051560'>to</span> <span m='1051860'>convert</span> <span
  m='1052640'>these</span> <span m='1052790'>specifications</span> <span
  m='1054590'>on</span> <span m='1055190'>the</span> <span
  m='1055340'>digital</span> <span m='1055760'>filter</span> <span
  m='1057350'>to</span> <span m='1058880'>corresponding</span> <span
  m='1059660'>specifications</span> <span m='1060800'>on</span> <span
  m='1061490'>the</span> <span m='1061640'>analog</span> <span
  m='1062120'>filter.</span> <span m='1064050'>Now,</span> <span
  m='1064620'>we</span> <span m='1064800'>know</span> <span
  m='1065430'>that</span> <span m='1066390'>from</span> <span
  m='1066720'>discussions</span> <span m='1067500'>that</span> <span
  m='1067650'>we've</span> <span m='1067860'>had</span> <span
  m='1068040'>previously</span> <span m='1069540'>that</span> <span
  m='1069960'>if</span> <span m='1070200'>we</span> <span
  m='1070350'>have</span> <span m='1070560'>an</span> <span
  m='1070650'>analog</span> <span m='1071550'>frequency</span> <span
  m='1072120'>response</span> <span m='1073530'>and</span> <span
  m='1073650'>we</span> <span m='1073800'>apply</span> <span
  m='1074470'>impulse</span> <span m='1074900'>invariance</span> <span
  m='1076430'>to</span> <span m='1076560'>the</span> <span
  m='1076680'>impulse</span> <span m='1077130'>response,</span> <span
  m='1078540'>the</span> <span m='1078720'>digital</span> <span
  m='1079110'>frequency</span> <span m='1079680'>response</span> <span
  m='1080910'>consists</span> <span m='1081630'>of</span> <span
  m='1082200'>the</span> <span m='1082350'>analog</span> <span
  m='1082860'>frequency</span> <span m='1083340'>response</span> <span
  m='1083790'>scaled</span> <span m='1084300'>in</span> <span
  m='1084390'>frequency</span> <span m='1085680'>so</span> <span
  m='1085920'>that</span> <span m='1086550'>capital</span> <span
  m='1087000'>Omega</span> <span m='1087750'>is</span> <span
  m='1087900'>equal</span> <span m='1088230'>to</span> <span
  m='1088410'>little</span> <span m='1088710'>omega</span> <span
  m='1089520'>divided</span> <span m='1089940'>by</span> <span
  m='1090150'>capital</span> <span m='1090645'>T.</span> <span
  m='1092640'>And</span> <span m='1092820'>then</span> <span
  m='1093420'>that</span> <span m='1094560'>scaled</span> <span
  m='1095250'>replica</span> <span m='1096360'>of</span> <span m='1096560'>H
  sub</span> <span m='1096990'>a</span> <span m='1098070'>added</span> <span
  m='1098370'>to</span> <span m='1098580'>itself</span> <span
  m='1099840'>delayed</span> <span m='1100350'>by</span> <span
  m='1101520'>little</span> <span m='1101820'>omega</span> <span
  m='1102630'>equal</span> <span m='1102960'>to</span> <span
  m='1103170'>2</span> <span m='1103320'>pi,</span> <span m='1103650'>4</span>
  <span m='1103950'>pi,</span> <span m='1104250'>et cetera.</span> <span
  m='1104790'>That</span> <span m='1104940'>is</span> <span
  m='1105030'>multiples</span> <span m='1105780'>of</span> <span
  m='1105990'>2</span> <span m='1106170'>pi.</span> </p><p><span
  m='1108210'>So,</span> <span m='1108750'>that</span> <span
  m='1108990'>means</span> <span m='1109350'>then</span> <span
  m='1113550'>that</span> <span m='1113880'>the</span> <span
  m='1114030'>digital</span> <span m='1114420'>filter</span> <span
  m='1115230'>is</span> <span m='1115710'>scaled</span> <span
  m='1116220'>repeated</span> <span m='1116670'>replicas</span> <span
  m='1117390'>of</span> <span m='1117540'>the</span> <span
  m='1117690'>analog</span> <span m='1118200'>filter,</span> <span
  m='1119310'>and</span> <span m='1119700'>so</span> <span m='1120510'>we</span>
  <span m='1120720'>would</span> <span m='1120840'>choose</span> <span
  m='1122430'>the</span> <span m='1122580'>analog</span> <span
  m='1123180'>filter</span> <span m='1124380'>to</span> <span
  m='1124500'>have</span> <span m='1124740'>similar</span> <span
  m='1125220'>specifications</span> <span m='1126600'>to</span> <span
  m='1126750'>the</span> <span m='1126870'>digital</span> <span
  m='1127260'>filter,</span> <span m='1128760'>but</span> <span
  m='1129330'>with</span> <span m='1129810'>the</span> <span
  m='1129960'>corresponding</span> <span m='1130830'>frequency</span> <span
  m='1131460'>parameters</span> <span m='1132780'>dictated</span> <span
  m='1133830'>by</span> <span m='1134010'>this</span> <span
  m='1134220'>transformation,</span> <span m='1135120'>capital</span> <span
  m='1135600'>Omega</span> <span m='1136020'>equal</span> <span
  m='1136350'>to</span> <span m='1136470'>little</span> <span
  m='1136740'>omega,</span> <span m='1137610'>divided</span> <span
  m='1138030'>by</span> <span m='1138490'>capital</span> <span
  m='1138990'>T.</span> <span m='1140940'>Well,</span> <span
  m='1141450'>that</span> <span m='1141720'>of</span> <span
  m='1141810'>course</span> <span m='1142860'>neglects</span> <span
  m='1143970'>aliasing,</span> <span m='1145260'>and</span> <span
  m='1145440'>in</span> <span m='1145530'>fact</span> <span
  m='1146130'>as</span> <span m='1146310'>we</span> <span m='1146400'>go</span>
  <span m='1146610'>through</span> <span m='1146820'>the</span> <span
  m='1146970'>impulse</span> <span m='1147360'>invariant</span> <span
  m='1147870'>design,</span> <span m='1148980'>we'll</span> <span
  m='1149610'>initially</span> <span m='1150150'>neglect</span> <span
  m='1150600'>aliasing.</span> <span m='1151890'>And</span> <span
  m='1153420'>a</span> <span m='1153480'>rationale</span> <span
  m='1154620'>for</span> <span m='1154800'>doing</span> <span
  m='1155160'>this</span> <span m='1155400'>or</span> <span m='1155580'>a</span>
  <span m='1155640'>reason</span> <span m='1156240'>why,</span> <span
  m='1156720'>in</span> <span m='1156870'>fact,</span> <span
  m='1157720'>it's</span> <span m='1157800'>not</span> <span
  m='1158050'>unreasonable</span> <span m='1158700'>to</span> <span
  m='1158850'>do</span> <span m='1159030'>that,</span> <span
  m='1159800'>will</span> <span m='1160230'>emerge</span> <span
  m='1160770'>as</span> <span m='1160890'>we</span> <span m='1161010'>go</span>
  <span m='1161160'>through</span> <span m='1161400'>the</span> <span
  m='1161550'>example.</span> <span m='1162480'>So</span> <span
  m='1162660'>for</span> <span m='1162780'>the</span> <span
  m='1162900'>time</span> <span m='1163200'>being,</span> <span
  m='1163500'>in</span> <span m='1163590'>fact,</span> <span
  m='1163890'>we're</span> <span m='1163980'>going</span> <span
  m='1164220'>to</span> <span m='1164310'>neglect</span> <span
  m='1164760'>aliasing,</span> <span m='1166260'>so</span> <span
  m='1166500'>that</span> <span m='1167130'>we'll</span> <span
  m='1167310'>think</span> <span m='1167580'>of</span> <span
  m='1167700'>the</span> <span m='1167850'>analog</span> <span
  m='1168690'>and</span> <span m='1168810'>digital</span> <span
  m='1169200'>frequency</span> <span m='1169710'>responses</span> <span
  m='1171030'>as</span> <span m='1171120'>simply</span> <span
  m='1171540'>related</span> <span m='1172500'>by</span> <span
  m='1172770'>this</span> <span m='1172910'>substitution</span> <span
  m='1173850'>of</span> <span m='1173940'>frequency</span> <span
  m='1174450'>variable,</span> <span m='1174960'>capital</span> <span
  m='1175440'>Omega</span> <span m='1176280'>equal</span> <span
  m='1176520'>to</span> <span m='1176640'>little</span> <span
  m='1176850'>omega</span> <span m='1177210'>divided</span> <span
  m='1177630'>by</span> <span m='1178020'>capital</span> <span
  m='1178315'>T.</span> </p><p><span m='1180480'>Well,</span> <span
  m='1181020'>that</span> <span m='1181320'>leads</span> <span
  m='1181680'>us</span> <span m='1181920'>then</span> <span
  m='1183570'>to</span> <span m='1184650'>the</span> <span
  m='1185430'>analog</span> <span m='1187700'>frequency</span> <span
  m='1188300'>response</span> <span m='1189230'>which</span> <span
  m='1189860'>I've</span> <span m='1190070'>depicted</span> <span
  m='1190970'>here.</span> <span m='1192720'>We</span> <span
  m='1192900'>had</span> <span m='1193110'>a</span> <span
  m='1193170'>factor</span> <span m='1193650'>of</span> <span
  m='1193740'>1</span> <span m='1193920'>over</span> <span
  m='1194130'>capital</span> <span m='1194595'>T</span> <span
  m='1195060'>in</span> <span m='1195240'>the</span> <span
  m='1195360'>amplitude</span> <span m='1197220'>of</span> <span
  m='1198360'>this</span> <span m='1198570'>expression.</span> <span
  m='1200230'>So</span> <span m='1200820'>for</span> <span
  m='1200970'>the</span> <span m='1201090'>digital</span> <span
  m='1201480'>filter</span> <span m='1202380'>to</span> <span
  m='1202770'>result</span> <span m='1203340'>with</span> <span
  m='1203670'>an</span> <span m='1203820'>amplitude</span> <span
  m='1204330'>of</span> <span m='1204450'>unity</span> <span
  m='1205620'>at</span> <span m='1205770'>dc,</span> <span m='1206970'>we</span>
  <span m='1207120'>would</span> <span m='1207510'>scale</span> <span
  m='1208350'>the</span> <span m='1208620'>analog</span> <span
  m='1209280'>frequency</span> <span m='1209820'>response</span> <span
  m='1210720'>by</span> <span m='1210930'>capital</span> <span
  m='1211425'>T.</span> <span m='1213070'>So</span> <span m='1213610'>the</span>
  <span m='1213730'>important</span> <span m='1215590'>values</span> <span
  m='1216160'>then</span> <span m='1217150'>in</span> <span
  m='1217270'>capital</span> <span m='1217780'>Omega</span> <span
  m='1218620'>are</span> <span m='1218770'>the</span> <span
  m='1218890'>ones</span> <span m='1219460'>corresponding</span> <span
  m='1220150'>to</span> <span m='1220270'>little</span> <span
  m='1220540'>omega</span> <span m='1221110'>equal</span> <span
  m='1221470'>to</span> <span m='1221590'>0.2</span> <span
  m='1222130'>pi,</span> <span m='1223870'>or</span> <span
  m='1224140'>since</span> <span m='1224920'>capital</span> <span
  m='1225340'>Omega</span> <span m='1225680'>is</span> <span
  m='1225850'>equal</span> <span m='1226180'>to</span> <span
  m='1226330'>little</span> <span m='1226540'>omega</span> <span
  m='1226900'>divided</span> <span m='1227290'>by</span> <span
  m='1227470'>capital</span> <span m='1227830'>T.</span> <span
  m='1228850'>We</span> <span m='1229000'>have</span> <span m='1229480'>a</span>
  <span m='1229540'>passband</span> <span m='1230260'>edge</span> <span
  m='1230830'>occurring</span> <span m='1231400'>at</span> <span
  m='1232870'>capital</span> <span m='1233170'>Omega</span> <span
  m='1233620'>equal</span> <span m='1233890'>to</span> <span
  m='1234010'>0.2</span> <span m='1234490'>pi</span> <span
  m='1234760'>over</span> <span m='1234970'>capital</span> <span
  m='1235450'>T,</span> <span m='1236310'>and</span> <span m='1236460'>a</span>
  <span m='1236500'>stopband</span> <span m='1237190'>edge</span> <span
  m='1237640'>equal</span> <span m='1237990'>to</span> <span
  m='1238295'>0.3</span> <span m='1238600'>pi</span> <span
  m='1239290'>over</span> <span m='1239560'>capital</span> <span
  m='1239950'>T.</span> </p><p><span m='1242250'>At</span> <span
  m='1242700'>this</span> <span m='1242880'>passband</span> <span
  m='1243600'>edge,</span> <span m='1244170'>according</span> <span
  m='1244650'>to</span> <span m='1245340'>the</span> <span
  m='1245430'>specifications</span> <span m='1246660'>on</span> <span
  m='1246810'>the</span> <span m='1246900'>digital</span> <span
  m='1247260'>filter</span> <span m='1247920'>that</span> <span
  m='1248100'>we</span> <span m='1248280'>want,</span> <span
  m='1249600'>we</span> <span m='1249810'>would</span> <span
  m='1249990'>like</span> <span m='1250920'>the</span> <span
  m='1251280'>frequency</span> <span m='1251820'>response</span> <span
  m='1252720'>for</span> <span m='1252900'>frequencies</span> <span
  m='1253530'>below</span> <span m='1253950'>this--</span> <span
  m='1254500'>In</span> <span m='1254520'>other</span> <span
  m='1254700'>words,</span> <span m='1255040'>in</span> <span
  m='1255140'>the</span> <span m='1255240'>passband--</span> <span
  m='1256560'>to</span> <span m='1256680'>be</span> <span
  m='1256980'>between</span> <span m='1257460'>capital</span> <span
  m='1257840'>T</span> <span m='1258870'>and</span> <span
  m='1258990'>capital</span> <span m='1259320'>T</span> <span
  m='1259650'>times</span> <span m='1259950'>10</span> <span
  m='1260130'>to</span> <span m='1260220'>the</span> <span
  m='1260310'>minus</span> <span m='1260610'>0.05.</span> <span
  m='1262080'>That's</span> <span m='1262380'>the</span> <span
  m='1262470'>guarantee</span> <span m='1263130'>that</span> <span
  m='1263280'>we</span> <span m='1263430'>have</span> <span
  m='1263610'>less</span> <span m='1263880'>than</span> <span
  m='1264060'>1</span> <span m='1264270'>db</span> <span
  m='1264630'>ripple</span> <span m='1264990'>in</span> <span
  m='1265110'>the</span> <span m='1265200'>passband.</span> <span
  m='1266610'>And</span> <span m='1266760'>for</span> <span
  m='1266910'>frequencies</span> <span m='1267540'>greater</span> <span
  m='1267960'>than</span> <span m='1268560'>0.3</span> <span
  m='1269100'>pi,</span> <span m='1270000'>we</span> <span
  m='1270120'>would</span> <span m='1270240'>like</span> <span
  m='1270480'>to</span> <span m='1270600'>be</span> <span
  m='1270780'>below</span> <span m='1271170'>capital</span> <span
  m='1271665'>T</span> <span m='1272430'>times</span> <span
  m='1272730'>10</span> <span m='1272940'>to</span> <span m='1273060'>the</span>
  <span m='1273150'>minus</span> <span m='1273450'>0.75.</span> <span
  m='1274950'>That's</span> <span m='1275220'>the</span> <span
  m='1275310'>guarantee</span> <span m='1276180'>that</span> <span
  m='1276360'>we're</span> <span m='1276510'>down</span> <span
  m='1277560'>15</span> <span m='1278100'>db</span> <span m='1278610'>or</span>
  <span m='1278760'>more</span> <span m='1279330'>in</span> <span
  m='1279450'>the</span> <span m='1279540'>stopband.</span> </p><p><span
  m='1281880'>The</span> <span m='1281970'>way</span> <span
  m='1282180'>I've</span> <span m='1282600'>drawn</span> <span
  m='1282960'>it</span> <span m='1283080'>here,</span> <span
  m='1283980'>I've</span> <span m='1284460'>implied</span> <span
  m='1285000'>that</span> <span m='1285300'>I</span> <span
  m='1285480'>will</span> <span m='1285930'>exactly</span> <span
  m='1286620'>meet</span> <span m='1287370'>the</span> <span
  m='1287460'>specifications</span> <span m='1288410'>at</span> <span
  m='1288480'>the</span> <span m='1288600'>passband</span> <span
  m='1288960'>edge,</span> <span m='1289980'>and</span> <span
  m='1290100'>exactly</span> <span m='1290550'>meet</span> <span
  m='1290730'>the</span> <span m='1290820'>specifications</span> <span
  m='1291690'>at</span> <span m='1291770'>the</span> <span
  m='1291870'>stopband</span> <span m='1292560'>edge.</span> <span
  m='1293550'>You</span> <span m='1293670'>can</span> <span
  m='1293820'>imagine,</span> <span m='1294570'>of</span> <span
  m='1294720'>course,</span> <span m='1295140'>that</span> <span
  m='1296040'>if</span> <span m='1296610'>I</span> <span m='1297510'>did</span>
  <span m='1297750'>that</span> <span m='1299190'>and</span> <span
  m='1299340'>then</span> <span m='1299550'>converted</span> <span
  m='1300810'>to</span> <span m='1300930'>a</span> <span
  m='1300990'>digital</span> <span m='1301410'>filter</span> <span
  m='1302250'>using</span> <span m='1302580'>impulse</span> <span
  m='1303030'>invariance</span> <span m='1304350'>that</span> <span
  m='1305370'>there</span> <span m='1305550'>would</span> <span
  m='1305700'>be</span> <span m='1305970'>an</span> <span
  m='1306090'>effect</span> <span m='1306420'>due</span> <span
  m='1306600'>to</span> <span m='1306990'>aliasing,</span> <span
  m='1308200'>which</span> <span m='1308340'>in</span> <span
  m='1308430'>fact</span> <span m='1308790'>would</span> <span
  m='1309660'>result</span> <span m='1310230'>in</span> <span
  m='1310440'>my</span> <span m='1310650'>not</span> <span
  m='1311130'>meeting</span> <span m='1311610'>exactly</span> <span
  m='1312720'>the</span> <span m='1312810'>specifications</span> <span
  m='1313770'>at</span> <span m='1313860'>the</span> <span
  m='1313950'>stopband</span> <span m='1314580'>edge.</span> <span
  m='1315450'>And</span> <span m='1316200'>that's</span> <span
  m='1316410'>a</span> <span m='1316470'>point</span> <span
  m='1316770'>that</span> <span m='1316860'>we'll</span> <span
  m='1317010'>deal</span> <span m='1317280'>with</span> <span
  m='1317460'>in</span> <span m='1317550'>a</span> <span m='1317610'>few</span>
  <span m='1317820'>minutes.</span> </p><p><span m='1319870'>All</span> <span
  m='1319970'>right,</span> <span m='1320040'>well</span> <span
  m='1320310'>now</span> <span m='1320700'>we</span> <span
  m='1320850'>have</span> <span m='1321060'>our</span> <span
  m='1321150'>specifications.</span> <span m='1322740'>Let</span> <span
  m='1322950'>me</span> <span m='1323310'>incidentally</span> <span
  m='1323910'>point</span> <span m='1324240'>out</span> <span
  m='1325170'>that</span> <span m='1325980'>there's</span> <span
  m='1326220'>this</span> <span m='1326400'>parameter</span> <span
  m='1326970'>capital</span> <span m='1327340'>T</span> <span
  m='1328650'>that</span> <span m='1328800'>we're</span> <span
  m='1328920'>carrying</span> <span m='1329400'>around.</span> <span
  m='1330990'>And</span> <span m='1332040'>as</span> <span
  m='1332340'>I'll</span> <span m='1332460'>justify</span> <span
  m='1333390'>partly</span> <span m='1333810'>on</span> <span
  m='1333900'>the</span> <span m='1333990'>basis</span> <span
  m='1334380'>of</span> <span m='1334500'>this</span> <span
  m='1334710'>example,</span> <span m='1335730'>the</span> <span
  m='1335820'>parameter</span> <span m='1336330'>capital</span> <span
  m='1336825'>T</span> <span m='1337320'>is</span> <span m='1338370'>an</span>
  <span m='1338520'>irrelevant</span> <span m='1339270'>parameter.</span> <span
  m='1340510'>It's</span> <span m='1340590'>a</span> <span
  m='1340650'>parameter</span> <span m='1341310'>that</span> <span
  m='1341460'>will</span> <span m='1341580'>disappear.</span> <span
  m='1342810'>We'll</span> <span m='1342930'>carry</span> <span
  m='1343350'>it</span> <span m='1343410'>through</span> <span
  m='1344250'>with</span> <span m='1344460'>us</span> <span
  m='1345150'>for</span> <span m='1345270'>this</span> <span
  m='1345480'>one</span> <span m='1345690'>example.</span> <span
  m='1346800'>But</span> <span m='1347760'>for</span> <span
  m='1348000'>other</span> <span m='1348240'>examples</span> <span
  m='1349020'>and</span> <span m='1349140'>problems</span> <span
  m='1349800'>that</span> <span m='1350010'>you</span> <span
  m='1350100'>work</span> <span m='1350350'>through</span> <span
  m='1350520'>the</span> <span m='1350610'>study</span> <span
  m='1350940'>guide,</span> <span m='1353340'>you</span> <span
  m='1353700'>should</span> <span m='1354090'>have</span> <span
  m='1354450'>absorbed</span> <span m='1354870'>the</span> <span
  m='1354990'>fact</span> <span m='1355320'>that</span> <span
  m='1355410'>capital</span> <span m='1355770'>T</span> <span
  m='1356130'>is</span> <span m='1356250'>irrelevant,</span> <span
  m='1356910'>and</span> <span m='1357030'>in</span> <span
  m='1357150'>fact</span> <span m='1357780'>capital</span> <span
  m='1358080'>T</span> <span m='1358380'>can</span> <span m='1358530'>be</span>
  <span m='1358620'>chosen</span> <span m='1359010'>equal</span> <span
  m='1359250'>to</span> <span m='1359370'>unity.</span> <span
  m='1360720'>But</span> <span m='1360900'>let's</span> <span
  m='1361110'>carry</span> <span m='1361440'>it</span> <span
  m='1361500'>through</span> <span m='1361710'>in</span> <span
  m='1361800'>this</span> <span m='1361980'>example,</span> <span
  m='1363120'>and</span> <span m='1363660'>just</span> <span
  m='1363960'>see</span> <span m='1364290'>how</span> <span
  m='1364470'>it</span> <span m='1364560'>disappears.</span> </p><p><span
  m='1367490'>All</span> <span m='1367550'>right.</span> <span
  m='1367800'>Well,</span> <span m='1368210'>so</span> <span
  m='1368420'>we</span> <span m='1368570'>want</span> <span
  m='1369110'>the</span> <span m='1369440'>analog</span> <span
  m='1370640'>Butterworth</span> <span m='1371810'>filter</span> <span
  m='1373710'>meaning</span> <span m='1374040'>these</span> <span
  m='1374170'>specifications.</span> <span m='1376360'>And</span> <span
  m='1376980'>we</span> <span m='1377160'>want</span> <span
  m='1377310'>it</span> <span m='1377700'>at</span> <span
  m='1378240'>omega</span> <span m='1378600'>equal</span> <span
  m='1378870'>to</span> <span m='1379020'>0</span> <span m='1379830'>to</span>
  <span m='1379950'>have</span> <span m='1380160'>a</span> <span
  m='1380250'>gain</span> <span m='1381060'>magnitude</span> <span
  m='1381630'>squared</span> <span m='1381960'>function</span> <span
  m='1382440'>to</span> <span m='1382560'>be</span> <span m='1382710'>T</span>
  <span m='1382950'>squared,</span> <span m='1383460'>so</span> <span
  m='1383550'>that</span> <span m='1383690'>the</span> <span
  m='1383790'>magnitude</span> <span m='1384390'>is</span> <span
  m='1384510'>T.</span> <span m='1385470'>So</span> <span
  m='1385710'>here</span> <span m='1385950'>we</span> <span
  m='1386100'>have</span> <span m='1386370'>the</span> <span
  m='1386460'>form</span> <span m='1386850'>then</span> <span
  m='1387240'>of</span> <span m='1387720'>the</span> <span
  m='1388080'>analog</span> <span m='1389160'>Butterworth</span> <span
  m='1389910'>filter.</span> <span m='1391590'>And</span> <span m='1392010'>in
  order</span> <span m='1392430'>to</span> <span m='1392850'>meet</span> <span
  m='1393510'>these</span> <span m='1394080'>specifications</span> <span
  m='1395310'>at</span> <span m='1395400'>this</span> <span
  m='1395580'>frequency</span> <span m='1396150'>and</span> <span
  m='1396240'>this</span> <span m='1396480'>one,</span> <span
  m='1398190'>we</span> <span m='1398350'>then</span> <span
  m='1398560'>have</span> <span m='1398770'>two</span> <span
  m='1399010'>equations.</span> <span m='1400930'>One</span> <span
  m='1401140'>equation</span> <span m='1401650'>says</span> <span
  m='1402670'>that</span> <span m='1402790'>at</span> <span
  m='1402880'>capital</span> <span m='1403390'>Omega</span> <span
  m='1404650'>equal</span> <span m='1405010'>to</span> <span
  m='1405120'>0.2</span> <span m='1405640'>pi</span> <span
  m='1405940'>over</span> <span m='1406150'>capital</span> <span
  m='1406690'>T,</span> <span m='1408530'>we</span> <span
  m='1408680'>would</span> <span m='1408830'>like</span> <span
  m='1409820'>the</span> <span m='1409940'>value</span> <span
  m='1411790'>of</span> <span m='1414460'>the</span> <span
  m='1414550'>magnitude</span> <span m='1415060'>function</span> <span
  m='1415450'>to</span> <span m='1415540'>be</span> <span m='1415690'>T</span>
  <span m='1415960'>times</span> <span m='1416290'>10</span> <span
  m='1416470'>to</span> <span m='1416530'>the</span> <span
  m='1416620'>minus</span> <span m='1416920'>0.05,</span> <span
  m='1418480'>which</span> <span m='1418690'>implies</span> <span
  m='1419290'>that</span> <span m='1419770'>this</span> <span
  m='1420160'>denominator</span> <span m='1421270'>should</span> <span
  m='1421450'>be</span> <span m='1421600'>equal</span> <span
  m='1421900'>to</span> <span m='1422020'>10</span> <span m='1422620'>to</span>
  <span m='1422710'>the</span> <span m='1422830'>0.1.</span> </p><p><span
  m='1426438'>Second</span> <span m='1426890'>of</span> <span
  m='1426980'>all,</span> <span m='1427430'>at</span> <span
  m='1428060'>the</span> <span m='1428570'>stopband</span> <span
  m='1429290'>frequency,</span> <span m='1430160'>0.3</span> <span
  m='1430535'>pi</span> <span m='1430910'>divided</span> <span
  m='1431330'>by</span> <span m='1431510'>capital</span> <span
  m='1431950'>T,</span> <span m='1434090'>the</span> <span
  m='1434180'>fact</span> <span m='1434510'>that</span> <span
  m='1434600'>we</span> <span m='1434750'>want</span> <span
  m='1436520'>the</span> <span m='1436640'>magnitude</span> <span
  m='1437180'>to</span> <span m='1437270'>be</span> <span m='1437390'>T</span>
  <span m='1437690'>times</span> <span m='1438050'>10</span> <span
  m='1438260'>to</span> <span m='1438320'>the</span> <span
  m='1438410'>minus</span> <span m='1438710'>0.75</span> <span
  m='1440480'>implies</span> <span m='1441770'>the</span> <span
  m='1441860'>magnitude</span> <span m='1442400'>squared</span> <span
  m='1443240'>is</span> <span m='1443450'>of</span> <span
  m='1443540'>course</span> <span m='1443840'>the</span> <span
  m='1443960'>square</span> <span m='1444380'>of</span> <span
  m='1444470'>that.</span> <span m='1445410'>And</span> <span
  m='1446120'>we</span> <span m='1446270'>want</span> <span
  m='1446540'>then</span> <span m='1446840'>the</span> <span
  m='1446900'>denominator</span> <span m='1448190'>to</span> <span
  m='1448310'>be</span> <span m='1448580'>equal</span> <span
  m='1448970'>to</span> <span m='1449120'>10</span> <span m='1449750'>to</span>
  <span m='1449880'>the</span> <span m='1449970'>1.5.</span> <span
  m='1452300'>So</span> <span m='1452710'>we</span> <span
  m='1452890'>have</span> <span m='1453100'>two</span> <span
  m='1453310'>points</span> <span m='1453700'>that</span> <span
  m='1453790'>we're</span> <span m='1453910'>trying</span> <span
  m='1454240'>to</span> <span m='1454360'>nail</span> <span
  m='1454660'>down.</span> <span m='1455500'>We</span> <span
  m='1455620'>have</span> <span m='1455800'>two</span> <span
  m='1455980'>parameters,</span> <span m='1456700'>omega</span> <span
  m='1457120'>sub</span> <span m='1457240'>c</span> <span m='1457660'>and</span>
  <span m='1457780'>N.</span> <span m='1460020'>From</span> <span
  m='1460230'>these</span> <span m='1460440'>two</span> <span
  m='1460620'>points</span> <span m='1461100'>that</span> <span
  m='1461220'>we're</span> <span m='1461340'>trying</span> <span
  m='1461640'>to</span> <span m='1461760'>nail</span> <span
  m='1462000'>down,</span> <span m='1462330'>we</span> <span
  m='1462420'>get</span> <span m='1462570'>two</span> <span
  m='1462810'>equations.</span> <span m='1464520'>And</span> <span
  m='1464610'>we</span> <span m='1464760'>can</span> <span
  m='1464910'>now</span> <span m='1465510'>solve</span> <span
  m='1465960'>these</span> <span m='1466230'>equations</span> <span
  m='1467460'>for</span> <span m='1467640'>our</span> <span
  m='1467760'>parameters,</span> <span m='1468510'>omega</span> <span
  m='1468930'>sub</span> <span m='1469050'>c and</span> <span
  m='1469380'>capital</span> <span m='1469860'>N.</span> </p><p><span
  m='1471690'>Well,</span> <span m='1471930'>if</span> <span
  m='1472050'>we</span> <span m='1472140'>do</span> <span
  m='1472350'>that,</span> <span m='1472750'>and</span> <span
  m='1472770'>it's</span> <span m='1473430'>a</span> <span
  m='1473460'>little</span> <span m='1473700'>tedious</span> <span
  m='1474180'>to</span> <span m='1474330'>do</span> <span m='1474540'>it,</span>
  <span m='1475200'>let</span> <span m='1475530'>me</span> <span
  m='1475680'>point</span> <span m='1475950'>out</span> <span
  m='1476160'>incidentally</span> <span m='1476890'>since</span> <span
  m='1477030'>we're</span> <span m='1477150'>trying</span> <span
  m='1477450'>to</span> <span m='1477570'>keep</span> <span
  m='1477780'>track</span> <span m='1478110'>of</span> <span
  m='1478230'>this</span> <span m='1478350'>capital</span> <span
  m='1478820'>T,</span> <span m='1479940'>that</span> <span
  m='1480060'>capital</span> <span m='1480570'>T</span> <span
  m='1481710'>drops</span> <span m='1482130'>down</span> <span
  m='1482400'>into</span> <span m='1482640'>the</span> <span
  m='1482730'>numerator</span> <span m='1484080'>and</span> <span
  m='1484260'>so,</span> <span m='1485190'>in</span> <span
  m='1485340'>fact,</span> <span m='1485920'>we</span> <span
  m='1485940'>can</span> <span m='1486120'>solve</span> <span
  m='1486570'>for</span> <span m='1486780'>capital</span> <span
  m='1487320'>N</span> <span m='1488220'>and</span> <span
  m='1488650'>omega</span> <span m='1488970'>sub</span> <span
  m='1489300'>c</span> <span m='1489570'>times</span> <span
  m='1490020'>capital</span> <span m='1490530'>T.</span> <span m='1491450'>In
  other</span> <span m='1491700'>words,</span> <span m='1491910'>we</span> <span
  m='1492000'>can</span> <span m='1492150'>just</span> <span
  m='1492300'>move</span> <span m='1492630'>this</span> <span
  m='1492840'>down</span> <span m='1493170'>here</span> <span
  m='1494120'>algebraically.</span> <span m='1495570'>And</span> <span
  m='1495780'>so</span> <span m='1496350'>we</span> <span
  m='1496560'>have</span> <span m='1496830'>then</span> <span
  m='1497060'>instead</span> <span m='1497370'>of</span> <span
  m='1497490'>the</span> <span m='1497580'>parameter</span> <span
  m='1498030'>omega</span> <span m='1498420'>sub</span> <span
  m='1498840'>c,</span> <span m='1498990'>we have</span> <span
  m='1499170'>the</span> <span m='1499260'>parameter</span> <span
  m='1499920'>omega</span> <span m='1500310'>sub c</span> <span
  m='1500730'>times</span> <span m='1501050'>capital</span> <span
  m='1501345'>T.</span> <span m='1503730'>If</span> <span m='1503940'>you</span>
  <span m='1504030'>grind</span> <span m='1504360'>through</span> <span
  m='1505380'>these</span> <span m='1505590'>two</span> <span
  m='1505770'>equations,</span> <span m='1507090'>what</span> <span
  m='1507360'>results</span> <span m='1508020'>is</span> <span
  m='1508710'>a</span> <span m='1508770'>value</span> <span
  m='1509160'>for</span> <span m='1509410'>N</span> <span
  m='1509730'>equal</span> <span m='1510000'>to</span> <span
  m='1510150'>5.8858</span> <span m='1512040'>and</span> <span
  m='1512160'>probably</span> <span m='1512640'>some</span> <span
  m='1512820'>other</span> <span m='1513030'>digits.</span> <span
  m='1514170'>And</span> <span m='1514230'>omega</span> <span
  m='1514660'>sub</span> <span m='1514780'>c</span> <span
  m='1515200'>capital</span> <span m='1515630'>T</span> <span
  m='1516690'>equal</span> <span m='1516990'>to</span> <span
  m='1517110'>0.70474.</span> <span m='1520130'>And</span> <span
  m='1521030'>we</span> <span m='1521780'>could</span> <span
  m='1522050'>imagine</span> <span m='1523040'>that</span> <span
  m='1523190'>at</span> <span m='1523250'>this</span> <span
  m='1523460'>point</span> <span m='1524220'>we're</span> <span
  m='1524330'>done,</span> <span m='1524870'>except</span> <span
  m='1525740'>that</span> <span m='1528480'>the</span> <span
  m='1528600'>parameter</span> <span m='1529140'>N</span> <span
  m='1531130'>corresponding</span> <span m='1531820'>to</span> <span
  m='1531910'>the</span> <span m='1532060'>order</span> <span
  m='1532390'>of</span> <span m='1532480'>the</span> <span
  m='1532600'>filter,</span> <span m='1534840'>of</span> <span
  m='1534860'>course,</span> <span m='1535410'>has</span> <span
  m='1535520'>to</span> <span m='1535640'>be</span> <span m='1535790'>an</span>
  <span m='1535880'>integer.</span> </p><p><span m='1538000'>So,</span> <span
  m='1538740'>what</span> <span m='1538950'>that</span> <span
  m='1539160'>means</span> <span m='1539610'>is</span> <span
  m='1539760'>that</span> <span m='1540330'>we</span> <span
  m='1540480'>can't</span> <span m='1540840'>use</span> <span
  m='1541210'>the</span> <span m='1541290'>value</span> <span
  m='1541950'>of</span> <span m='1542100'>N</span> <span m='1543000'>as</span>
  <span m='1543180'>I've</span> <span m='1543300'>indicated</span> <span
  m='1543870'>here.</span> <span m='1544920'>We</span> <span
  m='1545040'>need</span> <span m='1545430'>an</span> <span
  m='1545580'>integer</span> <span m='1545940'>value.</span> <span
  m='1547790'>Also</span> <span m='1548680'>if</span> <span
  m='1549190'>we</span> <span m='1549400'>were</span> <span
  m='1549700'>to</span> <span m='1549880'>round</span> <span
  m='1550180'>this</span> <span m='1550570'>down</span> <span
  m='1551050'>or</span> <span m='1551170'>truncate</span> <span
  m='1551500'>it</span> <span m='1551830'>down</span> <span
  m='1552730'>to</span> <span m='1553090'>a</span> <span
  m='1553180'>choice</span> <span m='1553510'>of N</span> <span
  m='1553710'>equal</span> <span m='1553990'>to</span> <span
  m='1554140'>5,</span> <span m='1555860'>then</span> <span
  m='1556970'>since</span> <span m='1557300'>the</span> <span
  m='1557420'>order</span> <span m='1557750'>is</span> <span
  m='1557900'>lower</span> <span m='1558260'>you</span> <span
  m='1558410'>can</span> <span m='1558530'>imagine</span> <span
  m='1559040'>that</span> <span m='1559190'>the</span> <span
  m='1559280'>filter</span> <span m='1559670'>characteristics</span> <span
  m='1560480'>won't</span> <span m='1560750'>be</span> <span
  m='1561080'>as</span> <span m='1561260'>good.</span> <span
  m='1562200'>In</span> <span m='1562220'>other</span> <span
  m='1562460'>words,</span> <span m='1563220'>we're</span> <span
  m='1563270'>not</span> <span m='1563510'>going</span> <span
  m='1563750'>to</span> <span m='1563870'>meet</span> <span
  m='1564080'>these</span> <span m='1564220'>specifications.</span> <span
  m='1566540'>So</span> <span m='1567020'>the</span> <span
  m='1567200'>other</span> <span m='1567410'>choice</span> <span
  m='1568100'>then</span> <span m='1568640'>is</span> <span
  m='1569600'>to</span> <span m='1569840'>use</span> <span
  m='1570290'>instead</span> <span m='1570710'>of</span> <span
  m='1570830'>this</span> <span m='1571040'>value</span> <span m='1571520'>of
  N,</span> <span m='1572600'>use</span> <span m='1573070'>a</span> <span
  m='1573140'>value</span> <span m='1573860'>of</span> <span
  m='1574070'>N</span> <span m='1574400'>equal</span> <span
  m='1574700'>to</span> <span m='1574820'>6.</span> <span m='1575540'>In</span>
  <span m='1575720'>other</span> <span m='1575900'>words,</span> <span
  m='1576800'>round</span> <span m='1577220'>up</span> <span
  m='1578630'>to</span> <span m='1578750'>the</span> <span
  m='1579140'>next</span> <span m='1579470'>integer</span> <span
  m='1579860'>value.</span> <span m='1581190'>And</span> <span
  m='1581270'>if</span> <span m='1581480'>we</span> <span m='1581630'>do</span>
  <span m='1581870'>that</span> <span m='1582980'>then</span> <span
  m='1584540'>these</span> <span m='1584840'>two</span> <span
  m='1585080'>equations</span> <span m='1586550'>will</span> <span
  m='1587180'>no</span> <span m='1587390'>longer</span> <span
  m='1587810'>be</span> <span m='1587960'>satisfied.</span> <span
  m='1590010'>We're</span> <span m='1590160'>now</span> <span
  m='1590520'>using</span> <span m='1590880'>a</span> <span
  m='1590970'>higher</span> <span m='1591330'>order</span> <span
  m='1591600'>filter</span> <span m='1592590'>than</span> <span
  m='1592740'>these</span> <span m='1592950'>equations</span> <span
  m='1593520'>would</span> <span m='1593640'>dictate.</span> <span
  m='1595550'>Of</span> <span m='1595640'>course,</span> <span
  m='1596040'>we're</span> <span m='1596060'>using</span> <span
  m='1596390'>an</span> <span m='1596480'>integer</span> <span
  m='1596900'>order,</span> <span m='1597380'>because</span> <span
  m='1598280'>that's</span> <span m='1598520'>what</span> <span
  m='1598670'>we</span> <span m='1598790'>need.</span> <span
  m='1599120'>We're</span> <span m='1599210'>using</span> <span
  m='1602150'>a</span> <span m='1602210'>sixth</span> <span
  m='1602540'>order</span> <span m='1602750'>filter.</span> <span
  m='1604710'>And</span> <span m='1605240'>what</span> <span
  m='1605540'>that</span> <span m='1605780'>means</span> <span
  m='1606380'>is</span> <span m='1606620'>that</span> <span
  m='1607190'>if</span> <span m='1607430'>we</span> <span
  m='1607550'>choose</span> <span m='1608030'>N</span> <span
  m='1608240'>equal</span> <span m='1608510'>to</span> <span
  m='1608660'>6,</span> <span m='1611040'>we</span> <span m='1611060'>can</span>
  <span m='1611240'>satisfy</span> <span m='1611960'>this</span> <span
  m='1612170'>equation,</span> <span m='1613940'>or</span> <span
  m='1614150'>we</span> <span m='1614270'>can</span> <span
  m='1614420'>satisfy</span> <span m='1614960'>this</span> <span
  m='1615170'>equation,</span> <span m='1616130'>but</span> <span
  m='1616280'>we</span> <span m='1616430'>can't</span> <span
  m='1616670'>satisfy</span> <span m='1617270'>both</span> <span
  m='1617600'>of</span> <span m='1617720'>them.</span> </p><p><span
  m='1620480'>Well,</span> <span m='1620960'>which</span> <span
  m='1621260'>one</span> <span m='1621530'>should</span> <span
  m='1621710'>we</span> <span m='1622340'>try</span> <span m='1622700'>to</span>
  <span m='1622880'>meet</span> <span m='1623570'>and</span> <span
  m='1623720'>which</span> <span m='1623960'>one</span> <span
  m='1624350'>should</span> <span m='1624770'>we</span> <span
  m='1624980'>exceed?</span> <span m='1627440'>Well,</span> <span
  m='1627710'>we</span> <span m='1627860'>know</span> <span
  m='1628070'>that</span> <span m='1628220'>with</span> <span
  m='1628400'>impulse</span> <span m='1628830'>invariance</span> <span
  m='1629840'>there</span> <span m='1630380'>is</span> <span
  m='1631130'>the</span> <span m='1632780'>issue</span> <span
  m='1633080'>of</span> <span m='1633200'>aliasing.</span> <span
  m='1634460'>And</span> <span m='1634580'>so</span> <span m='1634790'>in</span>
  <span m='1634910'>fact,</span> <span m='1635600'>in</span> <span
  m='1635720'>impulse</span> <span m='1636170'>invariant</span> <span
  m='1636740'>design</span> <span m='1637850'>it</span> <span
  m='1637970'>will</span> <span m='1638150'>often</span> <span
  m='1638480'>happen</span> <span m='1639230'>that</span> <span
  m='1640250'>although</span> <span m='1640970'>we</span> <span
  m='1641450'>design</span> <span m='1641930'>exactly</span> <span
  m='1642530'>to</span> <span m='1642680'>meet</span> <span
  m='1642890'>the</span> <span m='1642980'>stopband</span> <span
  m='1643520'>specifications,</span> <span m='1645370'>the</span> <span
  m='1645470'>stopband</span> <span m='1645920'>specifications</span> <span
  m='1646760'>won't</span> <span m='1647030'>be</span> <span
  m='1647210'>met</span> <span m='1647690'>because</span> <span
  m='1648050'>of</span> <span m='1648140'>aliasing.</span> <span
  m='1649400'>Consequently,</span> <span m='1650720'>given</span> <span
  m='1651020'>the</span> <span m='1651140'>flexibility</span> <span
  m='1652280'>that</span> <span m='1652460'>we</span> <span
  m='1652640'>have,</span> <span m='1653500'>due to</span> <span
  m='1653930'>the</span> <span m='1654050'>fact</span> <span
  m='1654590'>that</span> <span m='1654860'>we</span> <span
  m='1655400'>can</span> <span m='1655580'>actually</span> <span
  m='1655910'>implement</span> <span m='1656480'>a</span> <span
  m='1656540'>higher</span> <span m='1656870'>order</span> <span
  m='1657140'>filter</span> <span m='1657680'>than</span> <span
  m='1657830'>these</span> <span m='1658010'>equations</span> <span
  m='1658610'>dictate,</span> <span m='1660230'>to</span> <span
  m='1660350'>compensate</span> <span m='1661040'>for</span> <span
  m='1661220'>aliasing</span> <span m='1662420'>we</span> <span
  m='1662570'>can</span> <span m='1663560'>exceed</span> <span
  m='1664940'>the</span> <span m='1665380'>stopband</span> <span
  m='1666080'>specifications</span> <span m='1667580'>and</span> <span
  m='1667700'>meet</span> <span m='1667940'>exactly</span> <span
  m='1668840'>the</span> <span m='1668930'>passband</span> <span
  m='1669470'>specifications.</span> <span m='1671840'>So</span> <span
  m='1672110'>if</span> <span m='1672590'>we</span> <span
  m='1672710'>substitute</span> <span m='1673820'>for</span> <span
  m='1674030'>N,</span> <span m='1675140'>N</span> <span
  m='1675390'>equals</span> <span m='1675660'>6</span> <span
  m='1676940'>into</span> <span m='1677270'>this</span> <span
  m='1677510'>equation</span> <span m='1680220'>that</span> <span
  m='1681180'>then</span> <span m='1682110'>requires</span> <span
  m='1683280'>that</span> <span m='1683460'>omega</span> <span
  m='1683880'>sub</span> <span m='1684240'>c</span> <span m='1684810'>T</span>
  <span m='1685590'>be</span> <span m='1685740'>such</span> <span
  m='1686340'>that</span> <span m='1686460'>we</span> <span
  m='1686640'>exactly</span> <span m='1687180'>meet</span> <span
  m='1687900'>the</span> <span m='1687990'>passband</span> <span
  m='1688740'>specifications,</span> <span m='1690450'>in</span> <span
  m='1690570'>which</span> <span m='1690810'>case</span> <span
  m='1691950'>this</span> <span m='1692280'>equation</span> <span
  m='1692820'>won't</span> <span m='1693060'>be</span> <span
  m='1693210'>met.</span> <span m='1693600'>In</span> <span
  m='1693750'>fact,</span> <span m='1694390'>what</span> <span
  m='1694440'>will</span> <span m='1694620'>happen</span> <span
  m='1695100'>at</span> <span m='1695220'>the</span> <span
  m='1695340'>stopband</span> <span m='1695970'>edge</span> <span
  m='1696630'>is</span> <span m='1696780'>that</span> <span
  m='1696930'>the</span> <span m='1697050'>stopband</span> <span
  m='1698280'>specifications</span> <span m='1699240'>will</span> <span
  m='1699360'>be</span> <span m='1699510'>exceeded.</span> </p><p><span
  m='1701490'>If</span> <span m='1701640'>we</span> <span m='1701760'>do</span>
  <span m='1701970'>this,</span> <span m='1702640'>then</span> <span
  m='1703140'>we</span> <span m='1704430'>have</span> <span
  m='1705510'>for</span> <span m='1706470'>the</span> <span
  m='1706740'>equation</span> <span m='1707580'>that</span> <span
  m='1707730'>we</span> <span m='1707880'>solve</span> <span
  m='1708180'>for</span> <span m='1708360'>omega sub</span> <span
  m='1708760'>c</span> <span m='1709350'>T</span> <span m='1709920'>from,</span>
  <span m='1711210'>the</span> <span m='1711300'>equation</span> <span
  m='1712210'>which</span> <span m='1712620'>specified</span> <span
  m='1713820'>the</span> <span m='1715020'>passband</span> <span
  m='1715360'>edge,</span> <span m='1716370'>which</span> <span
  m='1716580'>is</span> <span m='1716940'>where</span> <span
  m='1717150'>we're</span> <span m='1717240'>going</span> <span
  m='1717480'>to</span> <span m='1717600'>meet</span> <span
  m='1717780'>the</span> <span m='1717900'>specs.</span> <span
  m='1719310'>And</span> <span m='1719730'>what</span> <span
  m='1719940'>results</span> <span m='1720450'>then</span> <span
  m='1720900'>is</span> <span m='1721680'>for</span> <span
  m='1721980'>omega</span> <span m='1722430'>sub</span> <span
  m='1722560'>c</span> <span m='1722955'>T,</span> <span m='1724220'>this</span>
  <span m='1724530'>value,</span> <span m='1725370'>rather</span> <span
  m='1725700'>than</span> <span m='1725850'>the</span> <span
  m='1725940'>previous</span> <span m='1726390'>value</span> <span
  m='1727170'>that</span> <span m='1727500'>had</span> <span
  m='1727710'>been</span> <span m='1728070'>obtained</span> <span
  m='1728490'>from</span> <span m='1728640'>the</span> <span
  m='1728730'>two</span> <span m='1728940'>equations.</span> <span
  m='1731670'>Well,</span> <span m='1732020'>from</span> <span
  m='1732200'>these</span> <span m='1732410'>parameters</span> <span
  m='1733590'>then,</span> <span m='1735490'>we</span> <span
  m='1735650'>have</span> <span m='1735830'>that</span> <span
  m='1735950'>omega</span> <span m='1736300'>sub c</span> <span
  m='1736640'>is</span> <span m='1736760'>0.7032</span> <span
  m='1737840'>divided</span> <span m='1738260'>by</span> <span
  m='1738470'>capital</span> <span m='1738895'>T.</span> <span
  m='1740060'>We</span> <span m='1740240'>can</span> <span
  m='1741290'>substitute</span> <span m='1742340'>these</span> <span
  m='1742550'>parameters</span> <span m='1744260'>into</span> <span
  m='1744890'>the</span> <span m='1745040'>form</span> <span
  m='1745610'>for</span> <span m='1745880'>the</span> <span
  m='1745970'>squared</span> <span m='1746330'>magnitude</span> <span
  m='1746930'>function,</span> <span m='1747440'>H</span> <span m='1747620'>sub
  a</span> <span m='1747980'>of</span> <span m='1748100'>s</span> <span
  m='1748700'>times</span> <span m='1749120'>H sub</span> <span m='1749450'>a
  of</span> <span m='1749570'>minus</span> <span m='1749900'>s,</span> <span
  m='1751040'>and</span> <span m='1751730'>actually</span> <span
  m='1752420'>it's</span> <span m='1752660'>this</span> <span
  m='1753350'>raised</span> <span m='1753710'>to</span> <span
  m='1753980'>the</span> <span m='1754250'>2N,</span> <span
  m='1754550'>which</span> <span m='1754790'>is</span> <span
  m='1755840'>the</span> <span m='1756080'>2</span> <span
  m='1756320'>times</span> <span m='1756620'>sixth</span> <span
  m='1756960'>power,</span> <span m='1757710'>which</span> <span
  m='1757820'>is</span> <span m='1757970'>the</span> <span
  m='1758060'>12th</span> <span m='1758450'>power.</span> <span
  m='1759530'>So</span> <span m='1760100'>this</span> <span
  m='1760370'>then</span> <span m='1760700'>is</span> <span
  m='1760910'>the</span> <span m='1761030'>form</span> <span
  m='1761660'>for</span> <span m='1762140'>the</span> <span
  m='1762350'>analog</span> <span m='1763310'>squared</span> <span
  m='1763850'>magnitude</span> <span m='1764420'>function.</span> </p><p><span
  m='1767100'>Now</span> <span m='1767460'>notice</span> <span
  m='1768240'>that</span> <span m='1768750'>the</span> <span
  m='1768870'>parameter</span> <span m='1769350'>capital</span> <span
  m='1769690'>T</span> <span m='1770370'>still</span> <span
  m='1770700'>hasn't</span> <span m='1771030'>disappeared.</span> <span
  m='1772050'>We</span> <span m='1772140'>still</span> <span
  m='1772410'>have</span> <span m='1772680'>it.</span> <span
  m='1772770'>We</span> <span m='1772920'>have</span> <span
  m='1773070'>it</span> <span m='1773160'>there,</span> <span
  m='1773370'>and</span> <span m='1773490'>we</span> <span
  m='1773580'>have</span> <span m='1773790'>it</span> <span
  m='1773850'>here.</span> <span m='1775020'>But</span> <span
  m='1775380'>notice</span> <span m='1775980'>that</span> <span
  m='1776520'>when</span> <span m='1776700'>we</span> <span
  m='1776790'>substitute</span> <span m='1777510'>in</span> <span
  m='1777750'>for</span> <span m='1777900'>omega</span> <span m='1778320'>sub
  c,</span> <span m='1779270'>this</span> <span m='1779520'>number</span> <span
  m='1779820'>divided</span> <span m='1780210'>by</span> <span
  m='1780390'>capital</span> <span m='1780810'>T</span> <span
  m='1781230'>if</span> <span m='1781380'>you</span> <span
  m='1781590'>track</span> <span m='1781980'>through</span> <span
  m='1782190'>that</span> <span m='1782400'>algebra,</span> <span
  m='1784620'>capital</span> <span m='1784980'>T</span> <span
  m='1785340'>reappears</span> <span m='1786300'>in</span> <span
  m='1786460'>this</span> <span m='1786660'>expression</span> <span
  m='1788370'>as</span> <span m='1788670'>a</span> <span
  m='1788760'>multiplier</span> <span m='1789630'>on</span> <span
  m='1789870'>s.</span> <span m='1790200'>That</span> <span
  m='1790530'>is</span> <span m='1790680'>we</span> <span m='1790800'>had</span>
  <span m='1790920'>0.7032</span> <span m='1791940'>divided</span> <span
  m='1792420'>by</span> <span m='1792620'>capital</span> <span
  m='1793075'>T.</span> <span m='1793770'>That</span> <span
  m='1793920'>gets</span> <span m='1794130'>reflected</span> <span
  m='1794670'>back</span> <span m='1794970'>up</span> <span
  m='1795150'>into</span> <span m='1795390'>this</span> <span
  m='1795570'>numerator,</span> <span m='1796620'>so</span> <span
  m='1796830'>that</span> <span m='1796980'>we</span> <span
  m='1797100'>have</span> <span m='1797280'>s</span> <span
  m='1797535'>times</span> <span m='1797790'>capital</span> <span
  m='1798210'>T.</span> <span m='1799530'>Well,</span> <span
  m='1799650'>let's</span> <span m='1800250'>see</span> <span
  m='1800520'>what</span> <span m='1800670'>that</span> <span
  m='1800880'>means.</span> </p><p><span m='1802800'>Suppose</span> <span
  m='1803220'>that</span> <span m='1803310'>capital</span> <span
  m='1803655'>T</span> <span m='1804000'>were</span> <span
  m='1804150'>equal</span> <span m='1804390'>to</span> <span
  m='1804520'>1.</span> <span m='1806500'>And</span> <span m='1806680'>we</span>
  <span m='1806800'>got</span> <span m='1807460'>an</span> <span
  m='1807580'>analog</span> <span m='1808630'>impulse</span> <span
  m='1809080'>response,</span> <span m='1809740'>H</span> <span
  m='1810000'>sub</span> <span m='1810280'>a of</span> <span
  m='1810430'>T,</span> <span m='1812060'>or</span> <span m='1812630'>the</span>
  <span m='1812900'>system</span> <span m='1813320'>function</span> <span
  m='1813860'>H</span> <span m='1814070'>sub a</span> <span
  m='1814400'>of</span> <span m='1814520'>s.</span> <span m='1817470'>If</span>
  <span m='1817740'>instead</span> <span m='1819570'>we</span> <span
  m='1820170'>reinserted</span> <span m='1821090'>capital</span> <span
  m='1821525'>T</span> <span m='1821960'>and</span> <span
  m='1822090'>considered</span> <span m='1822840'>H</span> <span
  m='1823140'>sub</span> <span m='1823560'>a</span> <span m='1823980'>of</span>
  <span m='1824160'>s</span> <span m='1824460'>times</span> <span
  m='1824880'>capital</span> <span m='1825210'>T</span> <span
  m='1827590'>multiplied</span> <span m='1828490'>by</span> <span
  m='1828700'>capital</span> <span m='1829170'>T</span> <span
  m='1831610'>that</span> <span m='1831850'>impulse</span> <span
  m='1832330'>response</span> <span m='1832930'>would</span> <span
  m='1833080'>be</span> <span m='1833200'>related</span> <span
  m='1833620'>to</span> <span m='1833770'>this</span> <span
  m='1834040'>one</span> <span m='1834760'>by</span> <span
  m='1834940'>simply</span> <span m='1835360'>a</span> <span
  m='1835420'>time</span> <span m='1835770'>scaling.</span> <span
  m='1837140'>In</span> <span m='1837190'>other</span> <span
  m='1837340'>words,</span> <span m='1837740'>this</span> <span
  m='1837880'>one</span> <span m='1838120'>would</span> <span
  m='1838270'>be</span> <span m='1838420'>replaced</span> <span
  m='1839380'>by</span> <span m='1839590'>H sub</span> <span
  m='1839780'>a</span> <span m='1840340'>of</span> <span m='1840490'>t</span>
  <span m='1840770'>divided</span> <span m='1841240'>by</span> <span
  m='1841540'>capital</span> <span m='1841915'>T.</span> <span
  m='1844060'>Well,</span> <span m='1844660'>let's</span> <span
  m='1844990'>look</span> <span m='1845260'>at</span> <span
  m='1845380'>this</span> <span m='1846310'>and</span> <span
  m='1846460'>ask</span> <span m='1846850'>what</span> <span
  m='1847060'>happens</span> <span m='1847510'>when</span> <span
  m='1847660'>we</span> <span m='1847780'>sample</span> <span
  m='1848350'>it</span> <span m='1849280'>at</span> <span
  m='1849430'>samples</span> <span m='1850510'>spaced</span> <span
  m='1851050'>by</span> <span m='1851420'>capital</span> <span
  m='1851830'>T.</span> </p><p><span m='1852910'>So,</span> <span
  m='1853600'>we</span> <span m='1854170'>look</span> <span
  m='1854440'>at</span> <span m='1854560'>this</span> <span
  m='1854800'>impulse</span> <span m='1855250'>response</span> <span
  m='1855850'>with</span> <span m='1856030'>T</span> <span
  m='1856990'>replaced</span> <span m='1857590'>by</span> <span
  m='1857890'>n</span> <span m='1858310'>times</span> <span
  m='1858840'>capital</span> <span m='1859230'>T,</span> <span
  m='1860620'>as</span> <span m='1861190'>we've</span> <span
  m='1861340'>specified</span> <span m='1862030'>here.</span> <span
  m='1863080'>And</span> <span m='1863170'>we</span> <span
  m='1863260'>observe</span> <span m='1863560'>that</span> <span
  m='1863680'>no</span> <span m='1863800'>matter</span> <span
  m='1864100'>what</span> <span m='1864340'>we</span> <span
  m='1864490'>pick</span> <span m='1864670'>capital</span> <span
  m='1865015'>T</span> <span m='1865360'>to</span> <span m='1865480'>be</span>
  <span m='1866650'>that</span> <span m='1866890'>parameter</span> <span
  m='1867460'>disappears.</span> <span m='1868750'>Because</span> <span
  m='1870150'>little</span> <span m='1870430'>t</span> <span
  m='1870850'>equal</span> <span m='1871180'>to</span> <span
  m='1871290'>n</span> <span m='1871780'>times</span> <span
  m='1871990'>capital</span> <span m='1872395'>T</span> <span
  m='1873280'>gives</span> <span m='1873550'>us</span> <span
  m='1873640'>samples</span> <span m='1874850'>H</span> <span m='1875140'>sub a
  of</span> <span m='1875500'>n,</span> <span m='1876520'>which</span> <span
  m='1877180'>are</span> <span m='1877420'>exactly</span> <span
  m='1877990'>the</span> <span m='1878110'>same</span> <span
  m='1878350'>samples</span> <span m='1879280'>that</span> <span
  m='1879400'>we</span> <span m='1879580'>would</span> <span
  m='1879730'>get</span> <span m='1880870'>no</span> <span
  m='1881050'>matter</span> <span m='1881350'>how</span> <span
  m='1881590'>we</span> <span m='1881740'>chose</span> <span
  m='1882340'>the</span> <span m='1882460'>parameter</span> <span
  m='1882940'>capital</span> <span m='1883270'>T,</span> <span
  m='1883600'>or</span> <span m='1883720'>equivalently</span> <span
  m='1884590'>whether</span> <span m='1884950'>or</span> <span
  m='1885010'>not</span> <span m='1885280'>we</span> <span
  m='1885400'>chose</span> <span m='1885700'>the</span> <span
  m='1885820'>parameter</span> <span m='1886240'>capital</span> <span
  m='1886690'>T</span> <span m='1887140'>equal</span> <span
  m='1887470'>to</span> <span m='1887590'>unity.</span> </p><p><span
  m='1890020'>I</span> <span m='1890110'>think</span> <span m='1890320'>that
  it</span> <span m='1890530'>requires</span> <span m='1891100'>a</span> <span
  m='1891130'>little</span> <span m='1891490'>reflection</span> <span
  m='1892570'>to</span> <span m='1893320'>absorb</span> <span
  m='1893800'>this</span> <span m='1894040'>point.</span> <span
  m='1895240'>It's</span> <span m='1895600'>basically</span> <span
  m='1896170'>tied</span> <span m='1896500'>to</span> <span
  m='1896620'>the</span> <span m='1896710'>fact</span> <span
  m='1897370'>that</span> <span m='1897550'>the</span> <span
  m='1897670'>frequency</span> <span m='1898210'>response</span> <span
  m='1899980'>is</span> <span m='1900100'>specified</span> <span
  m='1900910'>for</span> <span m='1901030'>the</span> <span
  m='1901150'>digital</span> <span m='1901570'>filter,</span> <span
  m='1902440'>not</span> <span m='1902650'>for</span> <span
  m='1902800'>the</span> <span m='1902920'>analog</span> <span
  m='1903430'>filter.</span> <span m='1904420'>And</span> <span
  m='1904660'>specifying</span> <span m='1905350'>the</span> <span
  m='1905410'>frequency</span> <span m='1905860'>response</span> <span
  m='1906940'>for</span> <span m='1907060'>the</span> <span
  m='1907180'>digital</span> <span m='1907600'>filter,</span> <span
  m='1908230'>in</span> <span m='1908380'>effect,</span> <span
  m='1909160'>specifies</span> <span m='1912150'>capital</span> <span
  m='1912730'>Omega</span> <span m='1913180'>times</span> <span
  m='1913620'>capital</span> <span m='1913925'>T.</span> <span
  m='1914890'>Well,</span> <span m='1915340'>I</span> <span
  m='1915700'>leave</span> <span m='1915970'>it</span> <span
  m='1916030'>to</span> <span m='1916180'>you</span> <span m='1916420'>to</span>
  <span m='1917620'>think</span> <span m='1917890'>about</span> <span
  m='1918220'>this</span> <span m='1918640'>a</span> <span
  m='1918700'>little.</span> <span m='1919480'>But</span> <span
  m='1919930'>the</span> <span m='1920080'>important</span> <span
  m='1920530'>point</span> <span m='1921520'>is</span> <span
  m='1921790'>that,</span> <span m='1922690'>in</span> <span
  m='1922780'>fact</span> <span m='1923110'>this</span> <span
  m='1923230'>parameter</span> <span m='1923880'>T,</span> <span
  m='1924730'>if</span> <span m='1924940'>we</span> <span
  m='1925030'>specify</span> <span m='1925630'>the</span> <span
  m='1925750'>filter</span> <span m='1927580'>in</span> <span
  m='1927700'>terms</span> <span m='1927940'>of</span> <span
  m='1928030'>digital</span> <span m='1928420'>specifications,</span> <span
  m='1929930'>this</span> <span m='1929980'>parameter</span> <span
  m='1930460'>capital</span> <span m='1930865'>T</span> <span
  m='1931270'>is</span> <span m='1931420'>really</span> <span
  m='1931780'>irrelevant.</span> </p><p><span m='1934840'>All</span> <span
  m='1934960'>right.</span> <span m='1935260'>Well,</span> <span
  m='1935680'>so</span> <span m='1936340'>here</span> <span
  m='1936760'>is</span> <span m='1937210'>our</span> <span
  m='1937780'>analog</span> <span m='1938350'>design.</span> <span
  m='1940190'>And</span> <span m='1941180'>we</span> <span
  m='1943070'>can</span> <span m='1944000'>obtain</span> <span
  m='1944560'>H</span> <span m='1944810'>sub</span> <span m='1945140'>a
  of</span> <span m='1945260'>s</span> <span m='1945500'>from</span> <span
  m='1945710'>this,</span> <span m='1946190'>according</span> <span
  m='1946640'>to</span> <span m='1947150'>the</span> <span
  m='1947270'>method</span> <span m='1947600'>that</span> <span
  m='1947870'>we</span> <span m='1948020'>talked</span> <span
  m='1948320'>about</span> <span m='1948560'>previously</span> <span
  m='1949460'>taking</span> <span m='1949850'>the</span> <span
  m='1949940'>left</span> <span m='1950210'>half</span> <span
  m='1950420'>plane</span> <span m='1950720'>poles</span> <span
  m='1951260'>of</span> <span m='1951410'>this</span> <span
  m='1951590'>expression.</span> <span m='1953120'>Converting</span> <span
  m='1953600'>those</span> <span m='1954140'>to</span> <span
  m='1954320'>a</span> <span m='1954380'>digital</span> <span
  m='1954770'>filter</span> <span m='1955730'>by</span> <span
  m='1955880'>using</span> <span m='1956780'>the</span> <span
  m='1957110'>transformation</span> <span m='1958070'>that</span> <span
  m='1958190'>we</span> <span m='1958670'>discussed</span> <span
  m='1959300'>in</span> <span m='1959480'>the</span> <span
  m='1959690'>previous</span> <span m='1960170'>two</span> <span
  m='1960350'>lectures,</span> <span m='1961460'>expanding,</span> <span
  m='1962030'>for</span> <span m='1962180'>example,</span> <span
  m='1962690'>in</span> <span m='1962810'>terms</span> <span
  m='1963350'>of</span> <span m='1963620'>residues</span> <span
  m='1964190'>and</span> <span m='1964280'>poles,</span> <span
  m='1965300'>and</span> <span m='1965810'>then</span> <span
  m='1966050'>applying</span> <span m='1966440'>the</span> <span
  m='1966560'>impulse</span> <span m='1966950'>invariant</span> <span
  m='1967400'>transformation.</span> <span m='1969380'>And</span> <span
  m='1969740'>if</span> <span m='1969890'>we</span> <span m='1970010'>do</span>
  <span m='1970220'>that,</span> <span m='1971240'>what</span> <span
  m='1971450'>results</span> <span m='1972110'>is</span> <span
  m='1974720'>a</span> <span m='1974810'>digital</span> <span
  m='1977300'>lowpass</span> <span m='1977870'>filter,</span> <span
  m='1979160'>which</span> <span m='1979640'>was</span> <span
  m='1979940'>the</span> <span m='1980030'>lowpass</span> <span
  m='1980510'>filter</span> <span m='1980840'>that</span> <span
  m='1980960'>we</span> <span m='1981080'>set</span> <span
  m='1981320'>out</span> <span m='1981470'>to</span> <span
  m='1981620'>design.</span> <span m='1982280'>And</span> <span
  m='1982670'>let</span> <span m='1982850'>me</span> <span
  m='1983000'>just</span> <span m='1984050'>show</span> <span
  m='1984620'>how</span> <span m='1984890'>those</span> <span
  m='1985070'>specifications,</span> <span m='1986330'>or</span> <span
  m='1986480'>how</span> <span m='1986660'>that</span> <span
  m='1986870'>design</span> <span m='1987260'>comes</span> <span
  m='1987560'>out.</span> </p><p><span m='1989510'>So</span> <span
  m='1990830'>this,</span> <span m='1991220'>for</span> <span
  m='1991550'>the</span> <span m='1991880'>example</span> <span
  m='1992600'>that</span> <span m='1992750'>we've</span> <span
  m='1992930'>been</span> <span m='1993050'>talking</span> <span
  m='1993500'>about,</span> <span m='1994040'>is</span> <span
  m='1995390'>a</span> <span m='1996050'>graph</span> <span
  m='1996710'>of</span> <span m='1997340'>the</span> <span
  m='1997430'>frequency</span> <span m='1997940'>response</span> <span
  m='1998450'>characteristics.</span> <span m='2000220'>Here</span> <span
  m='2000580'>is</span> <span m='2000820'>the</span> <span
  m='2000940'>magnitude</span> <span m='2002080'>as</span> <span
  m='2002260'>a</span> <span m='2002320'>function</span> <span
  m='2002920'>of</span> <span m='2003310'>digital</span> <span
  m='2003670'>frequency</span> <span m='2004570'>omega.</span> <span
  m='2005920'>And</span> <span m='2006490'>here</span> <span
  m='2006910'>is</span> <span m='2007540'>the</span> <span
  m='2007630'>same</span> <span m='2007900'>frequency</span> <span
  m='2008440'>response</span> <span m='2009130'>plotted</span> <span
  m='2009760'>in</span> <span m='2009940'>terms</span> <span
  m='2010270'>of</span> <span m='2010360'>db.</span> <span
  m='2012180'>And</span> <span m='2012420'>we</span> <span
  m='2012570'>see</span> <span m='2012900'>that</span> <span
  m='2014220'>we</span> <span m='2014550'>had</span> <span m='2015850'>in</span>
  <span m='2015960'>the</span> <span m='2016080'>specifications</span> <span
  m='2017340'>a</span> <span m='2017940'>passband</span> <span
  m='2018540'>edge</span> <span m='2018960'>at</span> <span
  m='2019110'>0.2</span> <span m='2019500'>pi,</span> <span m='2020750'>a</span>
  <span m='2020820'>stopband</span> <span m='2021630'>edge</span> <span
  m='2022050'>at</span> <span m='2022620'>0.3</span> <span
  m='2023190'>pi.</span> <span m='2025400'>At</span> <span
  m='2025580'>0.2</span> <span m='2026030'>pi</span> <span m='2026480'>we</span>
  <span m='2026690'>asked</span> <span m='2027230'>that</span> <span
  m='2027650'>the</span> <span m='2027800'>gain</span> <span
  m='2028400'>be</span> <span m='2029030'>down</span> <span
  m='2029420'>by</span> <span m='2029650'>1db.</span> <span
  m='2031190'>And</span> <span m='2032900'>of</span> <span
  m='2032960'>course,</span> <span m='2033200'>it's</span> <span
  m='2033320'>hard</span> <span m='2033710'>to</span> <span
  m='2033890'>tell</span> <span m='2034190'>exactly</span> <span
  m='2034700'>that</span> <span m='2034820'>we're</span> <span
  m='2034970'>down</span> <span m='2035240'>1db,</span> <span
  m='2035840'>but</span> <span m='2035990'>in</span> <span
  m='2036080'>fact</span> <span m='2036380'>we</span> <span
  m='2036560'>are.</span> <span m='2037640'>At</span> <span
  m='2038630'>omega</span> <span m='2038900'>equal</span> <span
  m='2039170'>to</span> <span m='2039515'>0.3</span> <span
  m='2039860'>pi,</span> <span m='2040580'>our</span> <span
  m='2040700'>specification</span> <span m='2041930'>was</span> <span
  m='2043070'>that</span> <span m='2043340'>we</span> <span
  m='2043490'>wanted</span> <span m='2043760'>to</span> <span
  m='2043910'>be</span> <span m='2044030'>down</span> <span
  m='2044570'>by</span> <span m='2044810'>15</span> <span m='2045410'>db.</span>
  </p><p><span m='2047900'>In</span> <span m='2047990'>fact,</span> <span
  m='2048290'>we</span> <span m='2048409'>overcompensated,</span> <span
  m='2049909'>because</span> <span m='2050360'>of</span> <span
  m='2050420'>the</span> <span m='2050540'>fact</span> <span
  m='2050810'>that</span> <span m='2050900'>we</span> <span
  m='2051020'>had</span> <span m='2051170'>to</span> <span
  m='2051545'>round</span> <span m='2052280'>the</span> <span
  m='2053000'>order</span> <span m='2053270'>of</span> <span
  m='2053389'>the</span> <span m='2053480'>filter</span> <span
  m='2053870'>up</span> <span m='2054050'>to</span> <span m='2054230'>an</span>
  <span m='2054320'>integer</span> <span m='2054650'>value.</span> <span
  m='2055860'>And</span> <span m='2055880'>you</span> <span
  m='2056000'>can</span> <span m='2056150'>see,</span> <span
  m='2056520'>in</span> <span m='2056540'>fact,</span> <span
  m='2057330'>that</span> <span m='2058219'>if</span> <span
  m='2058400'>you</span> <span m='2058460'>look</span> <span
  m='2058670'>at</span> <span m='2058760'>this</span> <span
  m='2058940'>carefully,</span> <span m='2060360'>we</span> <span
  m='2060679'>exceed</span> <span m='2061940'>the</span> <span
  m='2062480'>specifications</span> <span m='2063350'>of</span> <span
  m='2063429'>0.3</span> <span m='2063882'>pi</span> <span m='2064790'>by</span>
  <span m='2065030'>a</span> <span m='2065090'>little</span> <span
  m='2065330'>bit.</span> <span m='2065929'>In</span> <span
  m='2065989'>other</span> <span m='2066139'>words,</span> <span
  m='2066510'>we're</span> <span m='2066530'>down</span> <span
  m='2066980'>by</span> <span m='2067880'>a</span> <span
  m='2067969'>little</span> <span m='2068300'>more</span> <span
  m='2068900'>than</span> <span m='2069050'>15</span> <span
  m='2069590'>db.</span> <span m='2070460'>In</span> <span
  m='2070550'>fact,</span> <span m='2071270'>for</span> <span
  m='2071420'>this</span> <span m='2071600'>particular</span> <span
  m='2072139'>filter</span> <span m='2072620'>you</span> <span
  m='2072770'>can</span> <span m='2072949'>imagine</span> <span
  m='2073520'>that</span> <span m='2073639'>the</span> <span
  m='2073760'>effective</span> <span m='2074210'>aliasing</span> <span
  m='2075440'>is,</span> <span m='2075590'>in</span> <span
  m='2075679'>fact,</span> <span m='2075980'>rather</span> <span
  m='2076280'>minimal.</span> <span m='2077239'>Because</span> <span
  m='2078500'>this</span> <span m='2078710'>frequency</span> <span
  m='2079250'>response,</span> <span m='2080060'>by</span> <span
  m='2080270'>the</span> <span m='2080389'>time</span> <span
  m='2080690'>we</span> <span m='2080780'>get</span> <span
  m='2080929'>out</span> <span m='2081080'>to</span> <span m='2081199'>pi</span>
  <span m='2082340'>is</span> <span m='2082790'>essentially</span> <span
  m='2083360'>0.</span> <span m='2083870'>Here</span> <span
  m='2084080'>we're</span> <span m='2084230'>down</span> <span
  m='2084770'>to</span> <span m='2086150'>minus</span> <span
  m='2086460'>75</span> <span m='2087210'>db.</span> <span
  m='2088100'>And</span> <span m='2088250'>that's,</span> <span
  m='2088550'>of</span> <span m='2088670'>course,</span> <span
  m='2088940'>the</span> <span m='2089060'>amount</span> <span
  m='2089389'>that</span> <span m='2089510'>would</span> <span
  m='2089659'>get</span> <span m='2089840'>aliased</span> <span
  m='2090260'>back</span> <span m='2090560'>in.</span> <span
  m='2092040'>So</span> <span m='2092150'>this</span> <span
  m='2092389'>is</span> <span m='2092510'>the</span> <span
  m='2092600'>resulting</span> <span m='2093679'>filter</span> <span
  m='2094040'>frequency</span> <span m='2094550'>characteristics</span> <span
  m='2095960'>for</span> <span m='2096560'>the</span> <span
  m='2096920'>impulse</span> <span m='2097400'>invariant</span> <span
  m='2097940'>design</span> <span m='2099020'>where</span> <span
  m='2099560'>we</span> <span m='2099890'>exceed</span> <span
  m='2100370'>slightly</span> <span m='2101450'>the</span> <span
  m='2102440'>stopband</span> <span m='2103340'>edge</span> <span
  m='2103880'>specifications.</span> </p><p><span m='2106840'>Now,</span> <span
  m='2107800'>the</span> <span m='2107920'>next</span> <span
  m='2108190'>thing</span> <span m='2108610'>that</span> <span
  m='2108820'>I'd</span> <span m='2108940'>like</span> <span
  m='2109120'>to</span> <span m='2109240'>go</span> <span
  m='2109420'>onto</span> <span m='2110050'>is</span> <span
  m='2110880'>the</span> <span m='2112520'>corresponding</span> <span
  m='2113290'>design,</span> <span m='2113980'>the</span> <span
  m='2114100'>design</span> <span m='2114430'>or</span> <span
  m='2114490'>the</span> <span m='2114580'>corresponding</span> <span
  m='2115270'>Butterworth</span> <span m='2115750'>filter,</span> <span
  m='2117100'>now</span> <span m='2117430'>using</span> <span
  m='2117940'>the</span> <span m='2118030'>bilinear</span> <span
  m='2118570'>transformation</span> <span m='2119770'>rather</span> <span
  m='2120130'>than</span> <span m='2120280'>using</span> <span
  m='2120610'>impulse</span> <span m='2121030'>invariance.</span> <span
  m='2123280'>I</span> <span m='2123400'>remind</span> <span
  m='2123880'>you</span> <span m='2124480'>that</span> <span
  m='2125860'>the</span> <span m='2126850'>basic</span> <span
  m='2127360'>idea</span> <span m='2128380'>with</span> <span
  m='2128530'>the</span> <span m='2128620'>bilinear</span> <span
  m='2129160'>transformation,</span> <span m='2130270'>as</span> <span
  m='2130870'>we've</span> <span m='2131650'>discussed</span> <span
  m='2132760'>in</span> <span m='2132850'>the</span> <span
  m='2132940'>last</span> <span m='2133300'>lectures,</span> <span
  m='2134770'>is</span> <span m='2135430'>that</span> <span
  m='2136180'>we</span> <span m='2136720'>basically</span> <span
  m='2138460'>choose</span> <span m='2141250'>the</span> <span
  m='2141400'>analog</span> <span m='2142900'>specifications</span> <span
  m='2144790'>by</span> <span m='2145060'>pre-warping</span> <span
  m='2146680'>the</span> <span m='2146800'>critical</span> <span
  m='2147250'>frequencies</span> <span m='2148330'>for</span> <span
  m='2148510'>the</span> <span m='2148630'>digital</span> <span
  m='2149650'>filter</span> <span m='2150700'>through</span> <span
  m='2151510'>the</span> <span m='2152020'>nonlinear</span> <span
  m='2152680'>distortion</span> <span m='2153730'>curve</span> <span
  m='2154660'>corresponding</span> <span m='2155380'>to</span> <span
  m='2155500'>the</span> <span m='2155590'>bilinear</span> <span
  m='2156100'>transformation.</span> </p><p><span m='2157970'>So,</span> <span
  m='2158980'>we</span> <span m='2159130'>would</span> <span
  m='2159250'>start</span> <span m='2159610'>here</span> <span
  m='2159940'>for</span> <span m='2160090'>the</span> <span
  m='2160180'>digital</span> <span m='2160570'>filter.</span> <span
  m='2162050'>Of</span> <span m='2162150'>course,</span> <span
  m='2162250'>here</span> <span m='2162400'>we're</span> <span
  m='2162490'>talking</span> <span m='2162760'>about</span> <span
  m='2162910'>a</span> <span m='2162970'>monotonic</span> <span
  m='2163630'>filter</span> <span m='2164020'>rather</span> <span
  m='2164380'>than</span> <span m='2164530'>one</span> <span
  m='2164740'>that</span> <span m='2164830'>ripples.</span> <span
  m='2165940'>But</span> <span m='2166240'>we</span> <span
  m='2166390'>have</span> <span m='2166540'>a</span> <span
  m='2166600'>passband</span> <span m='2167260'>edge</span> <span
  m='2167710'>at</span> <span m='2167860'>0.2</span> <span
  m='2168400'>pi,</span> <span m='2169420'>a</span> <span
  m='2169480'>stopband</span> <span m='2170080'>edge</span> <span
  m='2170260'>at</span> <span m='2170350'>0.3</span> <span
  m='2170920'>pi.</span> <span m='2172120'>We</span> <span
  m='2172240'>reflect</span> <span m='2172750'>those</span> <span
  m='2173050'>critical</span> <span m='2173500'>frequencies</span> <span
  m='2174850'>through</span> <span m='2175390'>the</span> <span
  m='2175650'>arctangent</span> <span m='2176290'>curve</span> <span
  m='2177250'>to</span> <span m='2177430'>obtain</span> <span
  m='2178090'>the</span> <span m='2178210'>corresponding</span> <span
  m='2179440'>critical</span> <span m='2179830'>frequencies</span> <span
  m='2181090'>for</span> <span m='2181900'>the</span> <span
  m='2182680'>analog</span> <span m='2183190'>Butterworth</span> <span
  m='2183700'>filter.</span> <span m='2185320'>When</span> <span
  m='2185440'>the</span> <span m='2185560'>analog</span> <span
  m='2185980'>Butterworth</span> <span m='2186430'>filter</span> <span
  m='2186820'>is</span> <span m='2186970'>designed,</span> <span
  m='2187990'>we</span> <span m='2188110'>then</span> <span
  m='2188470'>obtain</span> <span m='2189210'>the</span> <span
  m='2189310'>digital</span> <span m='2190300'>Butterworth</span> <span
  m='2190810'>filter</span> <span m='2191770'>by</span> <span
  m='2192310'>transforming</span> <span m='2193120'>this</span> <span
  m='2193360'>filter</span> <span m='2194560'>back</span> <span
  m='2194830'>through</span> <span m='2195070'>the</span> <span
  m='2195190'>bilinear</span> <span m='2195700'>transformation.</span>
  </p><p><span m='2198390'>So,</span> <span m='2199700'>let's</span> <span
  m='2200240'>look</span> <span m='2200630'>at</span> <span
  m='2202110'>how</span> <span m='2203340'>this</span> <span
  m='2203730'>design</span> <span m='2205140'>works</span> <span
  m='2205720'>then.</span> <span m='2207070'>We</span> <span
  m='2207220'>have,</span> <span m='2208690'>as</span> <span
  m='2209140'>we've</span> <span m='2209350'>just</span> <span
  m='2210700'>reflected</span> <span m='2211240'>on</span> <span
  m='2211390'>that</span> <span m='2211570'>curve,</span> <span
  m='2212590'>we</span> <span m='2212740'>begin</span> <span
  m='2213340'>with</span> <span m='2213910'>the</span> <span
  m='2214630'>digital</span> <span m='2215860'>frequency</span> <span
  m='2216520'>specifications,</span> <span m='2218680'>reflect</span> <span
  m='2219130'>those</span> <span m='2219730'>through</span> <span
  m='2220180'>the</span> <span m='2220300'>bilinear</span> <span
  m='2220840'>warping</span> <span m='2221290'>curve</span> <span
  m='2222310'>to</span> <span m='2223000'>the</span> <span
  m='2223420'>analog</span> <span m='2224620'>specifications,</span> <span
  m='2226570'>and</span> <span m='2226690'>consequently</span> <span
  m='2227590'>the</span> <span m='2227680'>critical</span> <span
  m='2228100'>frequencies--</span> <span m='2229840'>and</span> <span
  m='2230110'>let</span> <span m='2230470'>me</span> <span
  m='2230830'>emphasize</span> <span m='2231400'>first</span> <span
  m='2231700'>of</span> <span m='2231820'>all</span> <span
  m='2232360'>that</span> <span m='2233650'>just</span> <span
  m='2233980'>as</span> <span m='2234190'>with</span> <span
  m='2234310'>impulse</span> <span m='2234760'>invariance,</span> <span
  m='2236350'>you</span> <span m='2236500'>can</span> <span
  m='2236680'>show</span> <span m='2237100'>that</span> <span
  m='2237250'>the</span> <span m='2237370'>parameter</span> <span
  m='2238210'>capital</span> <span m='2238600'>T</span> <span
  m='2238990'>is</span> <span m='2239140'>an</span> <span
  m='2239260'>irrelevant</span> <span m='2239830'>parameter.</span> <span
  m='2241090'>We</span> <span m='2241240'>could,</span> <span
  m='2241630'>in</span> <span m='2241810'>fact,</span> <span
  m='2242950'>carry</span> <span m='2243400'>it</span> <span
  m='2243490'>all</span> <span m='2243640'>the</span> <span
  m='2243760'>way</span> <span m='2243940'>through.</span> <span
  m='2244690'>And</span> <span m='2245020'>what</span> <span
  m='2245200'>would</span> <span m='2245350'>happen</span> <span
  m='2245710'>is</span> <span m='2245860'>that</span> <span
  m='2247150'>we</span> <span m='2247480'>would</span> <span
  m='2247660'>find</span> <span m='2248140'>that</span> <span
  m='2248260'>no</span> <span m='2248380'>matter</span> <span
  m='2248680'>what</span> <span m='2248920'>we</span> <span
  m='2249070'>chose</span> <span m='2249400'>capital</span> <span
  m='2249895'>T</span> <span m='2250390'>to</span> <span m='2250510'>be,</span>
  <span m='2251560'>the</span> <span m='2252460'>digital</span> <span
  m='2252820'>filter</span> <span m='2253210'>design</span> <span
  m='2253600'>that</span> <span m='2253690'>resulted</span> <span
  m='2254170'>would</span> <span m='2254320'>be</span> <span
  m='2254470'>exactly</span> <span m='2254950'>the</span> <span
  m='2255040'>same.</span> <span m='2255920'>So</span> <span
  m='2255970'>in</span> <span m='2256090'>fact,</span> <span
  m='2256600'>for</span> <span m='2256750'>this</span> <span
  m='2256960'>example</span> <span m='2257710'>I'll</span> <span
  m='2257860'>work</span> <span m='2258130'>through</span> <span
  m='2258430'>it</span> <span m='2258850'>simply</span> <span
  m='2259330'>with</span> <span m='2259480'>capital</span> <span
  m='2259780'>T</span> <span m='2260080'>equal</span> <span
  m='2260380'>to</span> <span m='2260530'>1.</span> </p><p><span
  m='2262140'>All</span> <span m='2262250'>right.</span> <span
  m='2262400'>With</span> <span m='2262520'>capital</span> <span
  m='2262815'>T</span> <span m='2263110'>equal</span> <span
  m='2263360'>to</span> <span m='2263510'>1,</span> <span m='2264710'>we</span>
  <span m='2266260'>reflect</span> <span m='2267070'>these</span> <span
  m='2267520'>critical</span> <span m='2267940'>frequencies</span> <span
  m='2268810'>into</span> <span m='2269140'>this</span> <span
  m='2269320'>passband</span> <span m='2269950'>frequency</span> <span
  m='2271390'>edge</span> <span m='2271900'>and</span> <span
  m='2272030'>this</span> <span m='2272200'>stopband</span> <span
  m='2272860'>edge.</span> <span m='2274060'>And</span> <span
  m='2274180'>consequently,</span> <span m='2276060'>the</span> <span
  m='2276340'>analog</span> <span m='2276940'>filter--</span> <span
  m='2277900'>this</span> <span m='2278110'>is</span> <span
  m='2278470'>the</span> <span m='2278620'>analog</span> <span
  m='2279100'>filter--</span> <span m='2281290'>the</span> <span
  m='2281440'>analog</span> <span m='2281920'>filter</span> <span
  m='2282790'>that</span> <span m='2283360'>we</span> <span
  m='2283510'>design</span> <span m='2284200'>is</span> <span
  m='2284860'>one</span> <span m='2285370'>that</span> <span
  m='2285640'>meets</span> <span m='2286390'>these</span> <span
  m='2286600'>specifications.</span> <span m='2288340'>And</span> <span
  m='2288460'>consequently</span> <span m='2289890'>we</span> <span
  m='2291310'>have,</span> <span m='2291800'>again,</span> <span
  m='2292700'>the</span> <span m='2292800'>two</span> <span
  m='2292900'>equations</span> <span m='2294100'>that</span> <span
  m='2294250'>say</span> <span m='2294970'>that</span> <span
  m='2296440'>at</span> <span m='2297190'>the</span> <span
  m='2297370'>passband</span> <span m='2298210'>edge,</span> <span
  m='2299840'>we</span> <span m='2299960'>want</span> <span
  m='2300200'>the</span> <span m='2300320'>magnitude</span> <span
  m='2301640'>to</span> <span m='2301760'>be</span> <span
  m='2303420'>within</span> <span m='2303780'>1db</span> <span
  m='2304410'>of</span> <span m='2304530'>unity.</span> <span
  m='2305730'>And</span> <span m='2306210'>at</span> <span
  m='2306360'>the</span> <span m='2306480'>stopband</span> <span
  m='2307250'>edge,</span> <span m='2307830'>we</span> <span
  m='2307980'>want</span> <span m='2308280'>the</span> <span
  m='2308340'>magnitude</span> <span m='2308930'>to</span> <span
  m='2309240'>be</span> <span m='2310140'>less</span> <span
  m='2310530'>than,</span> <span m='2311790'>down</span> <span
  m='2312060'>by</span> <span m='2312210'>more</span> <span
  m='2312510'>than</span> <span m='2313350'>15</span> <span
  m='2313890'>db.</span> <span m='2314940'>And</span> <span
  m='2315300'>the</span> <span m='2315390'>two</span> <span
  m='2315570'>equations</span> <span m='2316110'>that</span> <span
  m='2316290'>result</span> <span m='2316830'>are</span> <span
  m='2316950'>these,</span> <span m='2317400'>exactly</span> <span
  m='2317880'>the</span> <span m='2318000'>same</span> <span
  m='2318870'>as</span> <span m='2319020'>we</span> <span m='2319170'>had</span>
  <span m='2319470'>in</span> <span m='2319560'>the</span> <span
  m='2319680'>impulse</span> <span m='2320040'>invariant</span> <span
  m='2320580'>case,</span> <span m='2321360'>except</span> <span
  m='2321810'>that</span> <span m='2321960'>the</span> <span
  m='2322050'>frequencies</span> <span m='2322710'>are</span> <span
  m='2322770'>different.</span> </p><p><span m='2325150'>So</span> <span
  m='2325590'>now</span> <span m='2326280'>substituting</span> <span
  m='2327090'>in</span> <span m='2327210'>for</span> <span
  m='2327360'>the</span> <span m='2327450'>form</span> <span
  m='2327990'>of</span> <span m='2328380'>the</span> <span
  m='2328530'>analog</span> <span m='2329310'>Butterworth</span> <span
  m='2329820'>filter</span> <span m='2330510'>into</span> <span
  m='2330750'>these</span> <span m='2331020'>expressions,</span> <span
  m='2332400'>and</span> <span m='2333240'>setting</span> <span
  m='2333720'>this</span> <span m='2333960'>up</span> <span
  m='2334710'>for</span> <span m='2334920'>equality</span> <span
  m='2336780'>in</span> <span m='2337500'>these</span> <span
  m='2337770'>expressions,</span> <span m='2339210'>what</span> <span
  m='2339390'>results</span> <span m='2339930'>then</span> <span
  m='2340440'>are</span> <span m='2341640'>the</span> <span
  m='2341730'>two</span> <span m='2342000'>equations</span> <span
  m='2343210'>which</span> <span m='2343650'>are</span> <span
  m='2345210'>identical</span> <span m='2346800'>to</span> <span
  m='2346950'>the</span> <span m='2347310'>two</span> <span
  m='2347790'>equations</span> <span m='2348390'>that</span> <span
  m='2348510'>we</span> <span m='2348690'>had</span> <span
  m='2349350'>for</span> <span m='2349440'>the</span> <span
  m='2349560'>impulse</span> <span m='2349950'>invariant</span> <span
  m='2350460'>design,</span> <span m='2351030'>except</span> <span
  m='2351780'>that</span> <span m='2352440'>the</span> <span
  m='2353010'>frequencies</span> <span m='2354480'>at</span> <span
  m='2354690'>which</span> <span m='2355680'>the</span> <span
  m='2356580'>passband</span> <span m='2357210'>and</span> <span
  m='2357330'>stopband</span> <span m='2357930'>edges</span> <span
  m='2359310'>of</span> <span m='2359730'>the</span> <span
  m='2359880'>analog</span> <span m='2360390'>Butterworth</span> <span
  m='2360900'>filter</span> <span m='2361320'>fall</span> <span
  m='2362100'>are</span> <span m='2362220'>different.</span> <span
  m='2363620'>They're</span> <span m='2363690'>different</span> <span
  m='2364020'>because</span> <span m='2364410'>of</span> <span
  m='2364500'>the</span> <span m='2365100'>warping</span> <span
  m='2365880'>of</span> <span m='2366090'>the</span> <span
  m='2366390'>bilinear</span> <span m='2366750'>curve,</span> <span
  m='2367050'>or</span> <span m='2367110'>the</span> <span
  m='2367350'>pre-warping</span> <span m='2367860'>that</span> <span
  m='2367950'>we</span> <span m='2368100'>have</span> <span
  m='2368280'>to</span> <span m='2368430'>apply.</span> </p><p><span
  m='2369670'>So,</span> <span m='2370080'>these</span> <span
  m='2370380'>are</span> <span m='2370440'>the</span> <span
  m='2370530'>two</span> <span m='2370710'>equations.</span> <span
  m='2372660'>And</span> <span m='2375270'>if</span> <span m='2375420'>we</span>
  <span m='2375630'>solve</span> <span m='2376020'>these</span> <span
  m='2376200'>two</span> <span m='2376380'>equations</span> <span
  m='2377580'>for</span> <span m='2377730'>capital</span> <span
  m='2378240'>N,</span> <span m='2380700'>the</span> <span
  m='2380820'>resulting</span> <span m='2381300'>value</span> <span
  m='2381720'>for</span> <span m='2381870'>capital</span> <span
  m='2382350'>N</span> <span m='2382740'>is</span> <span m='2383370'>5.3</span>
  <span m='2384510'>and</span> <span m='2384630'>some</span> <span
  m='2384810'>digits.</span> <span m='2385840'>Notice</span> <span
  m='2386100'>incidentally</span> <span m='2386970'>that</span> <span
  m='2387780'>it's</span> <span m='2387960'>less</span> <span
  m='2388350'>than</span> <span m='2388500'>it</span> <span
  m='2388560'>was</span> <span m='2388830'>for</span> <span
  m='2388950'>the</span> <span m='2389070'>impulse</span> <span
  m='2389460'>invariant</span> <span m='2389970'>design.</span> <span
  m='2391020'>And</span> <span m='2391680'>in</span> <span
  m='2391830'>general</span> <span m='2392220'>that's</span> <span
  m='2392430'>a</span> <span m='2392490'>characteristic</span> <span
  m='2393270'>of</span> <span m='2393330'>the</span> <span
  m='2393420'>bilinear</span> <span m='2393960'>transformation.</span> <span
  m='2395310'>But</span> <span m='2396630'>so</span> <span
  m='2396870'>it's</span> <span m='2397050'>less,</span> <span
  m='2397620'>but</span> <span m='2398040'>it</span> <span m='2398340'>is</span>
  <span m='2398580'>not an</span> <span m='2399075'>integer.</span> <span
  m='2400470'>So</span> <span m='2400620'>the</span> <span
  m='2400710'>first</span> <span m='2400980'>thing</span> <span
  m='2401100'>we</span> <span m='2401250'>can</span> <span
  m='2401370'>ask</span> <span m='2401640'>again</span> <span
  m='2401910'>is,</span> <span m='2402090'>could</span> <span
  m='2402300'>we</span> <span m='2402420'>just</span> <span
  m='2402600'>simply</span> <span m='2403260'>truncate</span> <span
  m='2403770'>this</span> <span m='2403950'>down</span> <span
  m='2404460'>or</span> <span m='2404550'>round it</span> <span
  m='2404940'>down</span> <span m='2405690'>to</span> <span
  m='2405780'>the</span> <span m='2405900'>nearest</span> <span
  m='2406300'>integer</span> <span m='2406770'>value,</span> <span
  m='2407250'>in</span> <span m='2407310'>other</span> <span
  m='2407490'>words,</span> <span m='2407850'>N</span> <span
  m='2408010'>equals</span> <span m='2408330'>5.</span> <span
  m='2409380'>But</span> <span m='2409560'>of</span> <span
  m='2409650'>course</span> <span m='2409920'>if</span> <span
  m='2410040'>we</span> <span m='2410160'>did</span> <span
  m='2410430'>that,</span> <span m='2411340'>then</span> <span
  m='2411750'>we</span> <span m='2411930'>wouldn't</span> <span
  m='2412200'>be</span> <span m='2412350'>able</span> <span
  m='2412590'>to</span> <span m='2412740'>pick</span> <span
  m='2412980'>omega</span> <span m='2413370'>sub c,</span> <span
  m='2414390'>so</span> <span m='2414570'>that</span> <span
  m='2414780'>these</span> <span m='2415200'>equations</span> <span
  m='2415980'>were</span> <span m='2416130'>satisfied</span> <span
  m='2417030'>or</span> <span m='2417300'>so</span> <span
  m='2417510'>that</span> <span m='2417930'>the</span> <span
  m='2418020'>specifications</span> <span m='2419010'>were</span> <span
  m='2419130'>met</span> <span m='2419400'>or</span> <span
  m='2419550'>exceeded.</span> </p><p><span m='2420970'>So</span> <span
  m='2421260'>in</span> <span m='2421380'>fact,</span> <span
  m='2422190'>we</span> <span m='2422310'>need</span> <span
  m='2422520'>to</span> <span m='2422670'>choose,</span> <span
  m='2423310'>we</span> <span m='2423360'>have</span> <span
  m='2423540'>to</span> <span m='2423630'>choose</span> <span
  m='2424440'>N</span> <span m='2424770'>equal</span> <span
  m='2425070'>to</span> <span m='2425220'>6.</span> <span m='2426510'>We</span>
  <span m='2426660'>have</span> <span m='2426900'>to</span> <span
  m='2427050'>choose</span> <span m='2427500'>the</span> <span
  m='2427650'>next</span> <span m='2427980'>highest</span> <span
  m='2428580'>integer</span> <span m='2428970'>value.</span> <span
  m='2430830'>Choosing</span> <span m='2431280'>N</span> <span
  m='2431400'>equal</span> <span m='2431640'>to</span> <span
  m='2431790'>6,</span> <span m='2433480'>we</span> <span
  m='2433500'>then</span> <span m='2433710'>have</span> <span
  m='2433860'>the</span> <span m='2433980'>choice</span> <span
  m='2434550'>of</span> <span m='2435990'>exactly</span> <span
  m='2436530'>satisfying</span> <span m='2437250'>this</span> <span
  m='2437430'>equation,</span> <span m='2438990'>or</span> <span
  m='2439230'>exactly</span> <span m='2439680'>satisfying</span> <span
  m='2440280'>this</span> <span m='2440490'>equation,</span> <span
  m='2441630'>or</span> <span m='2441780'>in</span> <span
  m='2441870'>fact</span> <span m='2442440'>not</span> <span
  m='2442830'>satisfying</span> <span m='2443460'>either</span> <span
  m='2443670'>one</span> <span m='2443880'>of</span> <span
  m='2443970'>them,</span> <span m='2444150'>but</span> <span
  m='2444300'>playing</span> <span m='2444660'>back</span> <span
  m='2444900'>and</span> <span m='2445020'>forth</span> <span
  m='2445350'>between</span> <span m='2445740'>the</span> <span
  m='2445830'>two.</span> <span m='2447780'>Well</span> <span
  m='2447960'>let's</span> <span m='2448260'>do</span> <span
  m='2448470'>it</span> <span m='2448560'>in</span> <span m='2448860'>a</span>
  <span m='2448920'>particular</span> <span m='2449490'>way.</span> <span
  m='2451050'>We</span> <span m='2451320'>can,</span> <span
  m='2451680'>for</span> <span m='2451890'>example,</span> <span
  m='2453990'>exactly</span> <span m='2454680'>meet</span> <span
  m='2455250'>the</span> <span m='2455550'>stopband</span> <span
  m='2456750'>specifications.</span> </p><p><span m='2457830'>In</span> <span
  m='2457950'>other</span> <span m='2458100'>words,</span> <span
  m='2458890'>we</span> <span m='2458990'>can</span> <span
  m='2459030'>use</span> <span m='2459270'>N</span> <span
  m='2459510'>equals</span> <span m='2459770'>6</span> <span
  m='2460200'>in</span> <span m='2460290'>this</span> <span
  m='2460500'>equation,</span> <span m='2461110'>and</span> <span
  m='2461210'>solve</span> <span m='2461400'>for</span> <span
  m='2461580'>omega</span> <span m='2462030'>sub</span> <span
  m='2462345'>c,</span> <span m='2463350'>in</span> <span
  m='2463440'>which</span> <span m='2463710'>case</span> <span
  m='2464400'>the</span> <span m='2464520'>passband</span> <span
  m='2465300'>specifications</span> <span m='2466260'>will</span> <span
  m='2466380'>be</span> <span m='2466530'>exceeded.</span> <span
  m='2468540'>Recall</span> <span m='2468990'>that</span> <span
  m='2469110'>in</span> <span m='2469230'>the</span> <span
  m='2469320'>impulse</span> <span m='2469680'>invariant</span> <span
  m='2470190'>design</span> <span m='2470770'>we</span> <span
  m='2470790'>did</span> <span m='2470940'>it</span> <span
  m='2471030'>the</span> <span m='2471150'>other</span> <span
  m='2471330'>way</span> <span m='2471510'>around.</span> <span
  m='2472630'>We</span> <span m='2472680'>met</span> <span
  m='2473310'>exactly</span> <span m='2473820'>the</span> <span
  m='2473910'>passband</span> <span m='2474480'>specifications,</span> <span
  m='2476050'>in</span> <span m='2476130'>which</span> <span
  m='2476340'>case</span> <span m='2476580'>the</span> <span
  m='2476700'>stopband</span> <span m='2477540'>specs</span> <span
  m='2477990'>were</span> <span m='2478110'>exceeded.</span> <span
  m='2479250'>But</span> <span m='2479460'>there</span> <span
  m='2479800'>we</span> <span m='2479850'>had</span> <span m='2479970'>a</span>
  <span m='2480030'>good</span> <span m='2480240'>reason</span> <span
  m='2480570'>for</span> <span m='2480720'>doing</span> <span
  m='2481050'>that.</span> <span m='2481380'>The</span> <span
  m='2481530'>reason</span> <span m='2481860'>that</span> <span
  m='2481950'>we</span> <span m='2482070'>did</span> <span
  m='2482280'>that</span> <span m='2482670'>is</span> <span
  m='2482820'>because</span> <span m='2483240'>we</span> <span
  m='2483360'>knew</span> <span m='2483570'>in</span> <span
  m='2483690'>advance</span> <span m='2484920'>that</span> <span
  m='2485130'>in</span> <span m='2485340'>any</span> <span
  m='2485550'>case</span> <span m='2486120'>the</span> <span
  m='2486240'>passband</span> <span m='2486780'>specs</span> <span
  m='2487560'>wouldn't</span> <span m='2487830'>be</span> <span
  m='2487950'>met</span> <span m='2488160'>exactly,</span> <span
  m='2489270'>because</span> <span m='2489630'>of</span> <span
  m='2489690'>the</span> <span m='2489810'>effect</span> <span
  m='2490080'>of</span> <span m='2490260'>aliasing.</span> <span
  m='2491340'>For</span> <span m='2491430'>the</span> <span
  m='2491520'>bilinear</span> <span m='2492030'>transformation,</span> <span
  m='2492930'>we</span> <span m='2493110'>don't</span> <span
  m='2493350'>have</span> <span m='2493560'>a</span> <span
  m='2493620'>problem</span> <span m='2494070'>with</span> <span
  m='2494190'>aliasing.</span> <span m='2495180'>So,</span> <span
  m='2495360'>in</span> <span m='2495480'>fact,</span> <span
  m='2495780'>we're</span> <span m='2495900'>free</span> <span
  m='2496320'>to</span> <span m='2496440'>play</span> <span
  m='2497340'>with</span> <span m='2497760'>this</span> <span
  m='2497970'>flexibility</span> <span m='2499350'>in</span> <span
  m='2499830'>a</span> <span m='2499890'>more</span> <span
  m='2500130'>general</span> <span m='2500520'>way.</span> </p><p><span
  m='2502110'>All</span> <span m='2502200'>right.</span> <span
  m='2502380'>Well,</span> <span m='2502740'>in</span> <span
  m='2502860'>any</span> <span m='2503070'>case</span> <span
  m='2503670'>then</span> <span m='2504660'>if</span> <span
  m='2504810'>we</span> <span m='2504930'>meet</span> <span
  m='2505440'>the</span> <span m='2505560'>stopband</span> <span
  m='2506260'>specs,</span> <span m='2506750'>substituting</span> <span
  m='2507740'>N</span> <span m='2507910'>equals</span> <span
  m='2508160'>6</span> <span m='2508500'>in</span> <span m='2508620'>this</span>
  <span m='2508800'>equation,</span> <span m='2509320'>and</span> <span
  m='2509400'>solving</span> <span m='2509820'>for</span> <span
  m='2509970'>omega</span> <span m='2510340'>sub c;</span> <span
  m='2511830'>we</span> <span m='2512310'>end</span> <span m='2512640'>up</span>
  <span m='2513030'>with</span> <span m='2513420'>a</span> <span
  m='2513480'>value</span> <span m='2514410'>for</span> <span
  m='2514590'>omega</span> <span m='2514990'>sub</span> <span
  m='2515255'>c,</span> <span m='2515520'>which</span> <span
  m='2515790'>is</span> <span m='2515910'>0.76622.</span> <span
  m='2518910'>And</span> <span m='2520380'>so</span> <span
  m='2520980'>this</span> <span m='2521280'>then</span> <span
  m='2521460'>gives</span> <span m='2521760'>us</span> <span
  m='2521910'>the</span> <span m='2522000'>parameters</span> <span
  m='2522630'>omega</span> <span m='2523070'>sub</span> <span
  m='2523170'>c</span> <span m='2523590'>and</span> <span m='2523720'>N</span>
  <span m='2524940'>for</span> <span m='2525660'>the</span> <span
  m='2525840'>analog</span> <span m='2526860'>Butterworth</span> <span
  m='2527400'>filter.</span> <span m='2529530'>We</span> <span
  m='2529610'>can</span> <span m='2530240'>then</span> <span
  m='2530510'>use</span> <span m='2530750'>those</span> <span
  m='2530960'>specifications,</span> <span m='2532770'>again</span> <span
  m='2533660'>to</span> <span m='2533960'>generate</span> <span
  m='2534710'>the</span> <span m='2534830'>pole</span> <span
  m='2535160'>pattern</span> <span m='2535790'>for</span> <span
  m='2536810'>the</span> <span m='2536930'>squared</span> <span
  m='2537290'>magnitude</span> <span m='2537980'>function</span> <span
  m='2539260'>H sub</span> <span m='2539660'>a</span> <span
  m='2540060'>of</span> <span m='2540160'>s</span> <span
  m='2541100'>times</span> <span m='2541580'>H</span> <span m='2541880'>sub
  a</span> <span m='2542540'>of</span> <span m='2542690'>minus</span> <span
  m='2543190'>s.</span> <span m='2546470'>Factor</span> <span
  m='2546980'>this</span> <span m='2547250'>by</span> <span
  m='2547410'>choosing</span> <span m='2547820'>the</span> <span
  m='2547910'>left</span> <span m='2548180'>half</span> <span
  m='2548420'>plane</span> <span m='2549140'>poles</span> <span
  m='2549590'>in</span> <span m='2549680'>s</span> <span
  m='2549980'>plane,</span> <span m='2550820'>and</span> <span
  m='2550940'>then</span> <span m='2551210'>mapping</span> <span
  m='2552050'>this</span> <span m='2552260'>function</span> <span
  m='2553160'>to</span> <span m='2553310'>a</span> <span
  m='2553370'>digital</span> <span m='2553760'>filter</span> <span
  m='2554450'>using</span> <span m='2554810'>the</span> <span
  m='2554900'>bilinear</span> <span m='2555410'>transformation.</span>
  </p><p><span m='2556760'>And</span> <span m='2557390'>let's</span> <span
  m='2557960'>now</span> <span m='2558530'>look</span> <span
  m='2558890'>at</span> <span m='2559550'>how</span> <span
  m='2559700'>this</span> <span m='2559970'>filter</span> <span
  m='2560330'>comes</span> <span m='2560660'>out</span> <span
  m='2561440'>as</span> <span m='2561620'>compared</span> <span
  m='2562340'>with</span> <span m='2562850'>the</span> <span
  m='2567500'>digital</span> <span m='2567770'>Butterworth</span> <span
  m='2568160'>filter</span> <span m='2568460'>that</span> <span
  m='2568580'>we</span> <span m='2568700'>obtained</span> <span
  m='2569060'>by</span> <span m='2569210'>using</span> <span
  m='2569540'>impulse</span> <span m='2569960'>invariance.</span> <span
  m='2572090'>Well</span> <span m='2572450'>again,</span> <span
  m='2573380'>I</span> <span m='2573800'>have</span> <span m='2574040'>a</span>
  <span m='2574100'>display</span> <span m='2574820'>of</span> <span
  m='2576050'>the</span> <span m='2576950'>magnitude</span> <span
  m='2578540'>of</span> <span m='2579080'>the</span> <span
  m='2579170'>frequency</span> <span m='2579710'>response</span> <span
  m='2580610'>and</span> <span m='2580820'>also</span> <span
  m='2581150'>the</span> <span m='2581270'>gain</span> <span
  m='2582440'>in</span> <span m='2582760'>db.</span> <span
  m='2585770'>From</span> <span m='2586220'>what</span> <span
  m='2586520'>you</span> <span m='2586640'>may</span> <span
  m='2586820'>recall</span> <span m='2587270'>from</span> <span
  m='2587510'>the</span> <span m='2587690'>curve</span> <span
  m='2588020'>that</span> <span m='2588140'>I</span> <span
  m='2588230'>showed</span> <span m='2588680'>previously,</span> <span
  m='2590300'>this</span> <span m='2590540'>looks</span> <span
  m='2590990'>roughly</span> <span m='2591440'>the</span> <span
  m='2591560'>same.</span> <span m='2592010'>It's</span> <span
  m='2592520'>a</span> <span m='2592580'>monotonic</span> <span
  m='2593240'>filter</span> <span m='2594560'>and</span> <span
  m='2595100'>drops</span> <span m='2595520'>off.</span> <span
  m='2596900'>It's</span> <span m='2597110'>down</span> <span
  m='2597380'>by</span> <span m='2597530'>some</span> <span
  m='2597770'>amount</span> <span m='2598190'>at 0.2</span> <span
  m='2598700'>pi,</span> <span m='2599780'>and</span> <span
  m='2600560'>the</span> <span m='2600890'>stopband</span> <span
  m='2601760'>is</span> <span m='2601940'>at</span> <span m='2602230'>0.3</span>
  <span m='2602780'>pi.</span> <span m='2604820'>In</span> <span
  m='2604880'>particular,</span> <span m='2605390'>according</span> <span
  m='2605750'>to</span> <span m='2605870'>the</span> <span
  m='2605960'>specifications,</span> <span m='2607250'>we</span> <span
  m='2607400'>wanted</span> <span m='2607730'>this</span> <span
  m='2607940'>to</span> <span m='2608060'>be</span> <span
  m='2608150'>down</span> <span m='2609170'>by</span> <span
  m='2610070'>no</span> <span m='2610310'>more</span> <span
  m='2610580'>than</span> <span m='2610760'>1db</span> <span
  m='2611530'>at</span> <span m='2611660'>0.2</span> <span
  m='2612170'>pi.</span> </p><p><span m='2612860'>Well,</span> <span
  m='2614240'>it's</span> <span m='2614420'>hard</span> <span
  m='2614940'>again</span> <span m='2615200'>to</span> <span
  m='2615350'>say</span> <span m='2615530'>that</span> <span
  m='2615680'>this</span> <span m='2615860'>is</span> <span
  m='2616940'>1db</span> <span m='2617630'>or</span> <span
  m='2617720'>less.</span> <span m='2618710'>But</span> <span
  m='2619220'>if</span> <span m='2619340'>we</span> <span
  m='2619430'>look</span> <span m='2619610'>at</span> <span
  m='2619670'>0.3</span> <span m='2620020'>pi,</span> <span
  m='2620720'>we</span> <span m='2620870'>can</span> <span
  m='2621020'>see</span> <span m='2621560'>that</span> <span
  m='2623030'>this</span> <span m='2623390'>is</span> <span
  m='2623750'>in</span> <span m='2623870'>fact</span> <span
  m='2624260'>exactly</span> <span m='2625610'>down</span> <span
  m='2626060'>by</span> <span m='2626420'>15</span> <span m='2627000'>db.</span>
  <span m='2628160'>And</span> <span m='2629840'>that's</span> <span
  m='2630050'>the</span> <span m='2630140'>way</span> <span
  m='2630320'>that</span> <span m='2630440'>we</span> <span
  m='2630590'>designed</span> <span m='2631100'>it.</span> <span
  m='2631700'>We</span> <span m='2631820'>designed</span> <span
  m='2632240'>it</span> <span m='2632330'>to</span> <span
  m='2632480'>exactly</span> <span m='2632990'>meet</span> <span
  m='2633200'>the</span> <span m='2633320'>stopband</span> <span
  m='2634510'>cutoff</span> <span m='2635750'>and</span> <span
  m='2635990'>exceed</span> <span m='2636680'>the</span> <span
  m='2636800'>passband</span> <span m='2637380'>cutoff.</span> <span
  m='2639280'>And</span> <span m='2639820'>then</span> <span
  m='2640330'>the</span> <span m='2640540'>frequency</span> <span
  m='2641020'>response</span> <span m='2641680'>continues</span> <span
  m='2642250'>on</span> <span m='2642460'>from</span> <span
  m='2642670'>there.</span> <span m='2643960'>It's</span> <span
  m='2644170'>interesting,</span> <span m='2644650'>in</span> <span
  m='2644740'>fact,</span> <span m='2645100'>to</span> <span
  m='2645220'>compare</span> <span m='2645970'>the</span> <span
  m='2646120'>design</span> <span m='2646570'>that</span> <span
  m='2646660'>we</span> <span m='2646840'>got</span> <span
  m='2647770'>from</span> <span m='2647950'>the</span> <span
  m='2648040'>bilinear</span> <span m='2648550'>transformation</span> <span
  m='2649930'>with</span> <span m='2650110'>the</span> <span
  m='2650200'>design</span> <span m='2651130'>that</span> <span
  m='2651490'>we</span> <span m='2651610'>got</span> <span
  m='2651820'>previously</span> <span m='2653020'>with</span> <span
  m='2653170'>impulse</span> <span m='2653590'>invariance.</span> <span
  m='2654860'>And</span> <span m='2655390'>let</span> <span
  m='2655600'>me</span> <span m='2655750'>do</span> <span
  m='2655990'>that</span> <span m='2656620'>by</span> <span
  m='2657790'>superimposing</span> <span m='2659020'>the</span> <span
  m='2659110'>two</span> <span m='2659380'>of</span> <span
  m='2659530'>them.</span> <span m='2660350'>So</span> <span
  m='2660400'>that</span> <span m='2660550'>the</span> <span
  m='2660670'>one</span> <span m='2660940'>that</span> <span
  m='2661120'>I'm</span> <span m='2661240'>putting</span> <span
  m='2661600'>on</span> <span m='2661780'>now</span> <span m='2662500'>is</span>
  <span m='2663400'>the</span> <span m='2663520'>impulse</span> <span
  m='2663970'>invariant</span> <span m='2664570'>design,</span> <span
  m='2665980'>and</span> <span m='2666250'>let</span> <span
  m='2666400'>me</span> <span m='2666520'>just</span> <span
  m='2666760'>lay</span> <span m='2667060'>them</span> <span
  m='2668920'>on</span> <span m='2669070'>top</span> <span m='2669390'>of
  each</span> <span m='2669881'>other.</span> </p><p><span
  m='2674300'>OK.</span> <span m='2677006'>You</span> <span
  m='2677480'>can</span> <span m='2677630'>see</span> <span
  m='2677870'>incidentally</span> <span m='2678590'>that</span> <span
  m='2678980'>looking</span> <span m='2679340'>at</span> <span
  m='2679430'>the</span> <span m='2679550'>frequency</span> <span
  m='2680030'>response</span> <span m='2680570'>on</span> <span
  m='2680660'>a</span> <span m='2680720'>magnitude</span> <span
  m='2681980'>plot</span> <span m='2682790'>there,</span> <span
  m='2683120'>in</span> <span m='2683210'>fact,</span> <span
  m='2683540'>are</span> <span m='2683690'>some</span> <span
  m='2683900'>differences.</span> <span m='2684830'>This</span> <span
  m='2685010'>line</span> <span m='2685310'>has</span> <span
  m='2685430'>gotten</span> <span m='2685670'>a</span> <span
  m='2685700'>little</span> <span m='2685970'>thicker.</span> <span
  m='2687170'>That</span> <span m='2687410'>is,</span> <span
  m='2687560'>the</span> <span m='2687650'>two</span> <span
  m='2687830'>don't</span> <span m='2688070'>exactly</span> <span
  m='2688520'>superimpose.</span> <span m='2690140'>But</span> <span
  m='2690620'>you</span> <span m='2690770'>can't</span> <span
  m='2691130'>really</span> <span m='2691820'>see</span> <span
  m='2692090'>the</span> <span m='2692180'>differences.</span> <span
  m='2693350'>Whereas</span> <span m='2693590'>you</span> <span
  m='2693710'>can</span> <span m='2694370'>when</span> <span
  m='2694550'>we</span> <span m='2694640'>look</span> <span
  m='2694880'>at</span> <span m='2694970'>this</span> <span
  m='2695300'>on</span> <span m='2695570'>a</span> <span
  m='2696440'>logarithmic</span> <span m='2697160'>plot.</span> <span
  m='2698060'>In</span> <span m='2698150'>particular,</span> <span
  m='2699410'>this</span> <span m='2699650'>is</span> <span
  m='2699770'>the</span> <span m='2699860'>frequency</span> <span
  m='2700430'>response</span> <span m='2701810'>that</span> <span
  m='2702020'>corresponded</span> <span m='2702890'>to</span> <span
  m='2703100'>the</span> <span m='2703340'>bilinear</span> <span
  m='2703880'>transformation.</span> <span m='2705720'>This</span> <span
  m='2705860'>is</span> <span m='2705980'>the</span> <span
  m='2706070'>frequency</span> <span m='2706580'>response</span> <span
  m='2707090'>that</span> <span m='2707210'>corresponded</span> <span
  m='2707960'>to</span> <span m='2708380'>impulse</span> <span
  m='2708890'>invariance.</span> <span m='2710270'>And</span> <span
  m='2710930'>this</span> <span m='2711710'>is,</span> <span
  m='2712160'>in</span> <span m='2712340'>general,</span> <span
  m='2712850'>a</span> <span m='2712910'>characteristic</span> <span
  m='2714050'>of</span> <span m='2714380'>the</span> <span
  m='2714500'>use</span> <span m='2714710'>of</span> <span
  m='2714770'>the</span> <span m='2714890'>bilinear</span> <span
  m='2715370'>transformation.</span> <span m='2717610'>It's</span> <span
  m='2717770'>a</span> <span m='2717860'>result</span> <span
  m='2718490'>essentially</span> <span m='2719270'>of</span> <span
  m='2719450'>the</span> <span m='2719540'>frequency</span> <span
  m='2720090'>distortion,</span> <span m='2721280'>because</span> <span
  m='2722150'>we've</span> <span m='2722360'>taken</span> <span
  m='2723710'>the</span> <span m='2724220'>frequency</span> <span
  m='2725360'>axis</span> <span m='2726150'>and</span> <span
  m='2726300'>the</span> <span m='2727040'>continuous</span> <span
  m='2727490'>time</span> <span m='2727730'>frequency</span> <span
  m='2728240'>axis.</span> <span m='2729590'>As</span> <span
  m='2729890'>you</span> <span m='2730010'>run</span> <span
  m='2730250'>along</span> <span m='2730670'>it</span> <span
  m='2731090'>at</span> <span m='2731270'>a</span> <span
  m='2731330'>constant</span> <span m='2732050'>rate,</span> <span
  m='2732470'>it</span> <span m='2732620'>gets</span> <span
  m='2732860'>compressed</span> <span m='2733370'>more</span> <span
  m='2733670'>and</span> <span m='2733760'>more</span> <span
  m='2738170'>along</span> <span m='2738440'>the</span> <span
  m='2738530'>digital</span> <span m='2738890'>frequency</span> <span
  m='2739400'>axis.</span> </p><p><span m='2740120'>That</span> <span
  m='2740240'>wasn't</span> <span m='2740510'>well</span> <span
  m='2740750'>said.</span> <span m='2741140'>But</span> <span
  m='2742320'>what</span> <span m='2742670'>I</span> <span
  m='2742760'>really</span> <span m='2743030'>mean</span> <span
  m='2743210'>to</span> <span m='2743330'>say</span> <span m='2743570'>is</span>
  <span m='2743720'>as</span> <span m='2743870'>we</span> <span
  m='2744020'>walk</span> <span m='2744350'>along</span> <span
  m='2744680'>here</span> <span m='2744920'>at</span> <span m='2744980'>a</span>
  <span m='2745040'>constant</span> <span m='2745580'>rate,</span> <span
  m='2746610'>the</span> <span m='2746630'>farther</span> <span
  m='2747020'>we</span> <span m='2747200'>walk,</span> <span
  m='2748070'>the</span> <span m='2748190'>faster</span> <span
  m='2748700'>we're</span> <span m='2748850'>running</span> <span
  m='2749210'>along</span> <span m='2749480'>the</span> <span
  m='2749780'>j</span> <span m='2749880'>omega</span> <span
  m='2750140'>axis.</span> <span m='2751200'>And</span> <span
  m='2751250'>that's</span> <span m='2751490'>why,</span> <span
  m='2752120'>in</span> <span m='2752240'>fact,</span> <span
  m='2755270'>the</span> <span m='2755690'>use</span> <span
  m='2755900'>of</span> <span m='2755960'>the</span> <span
  m='2756050'>bilinear</span> <span m='2756530'>transformation</span> <span
  m='2757970'>on</span> <span m='2758120'>a</span> <span
  m='2758150'>lowpass</span> <span m='2758690'>filter</span> <span
  m='2759710'>will</span> <span m='2760580'>give</span> <span
  m='2762710'>better</span> <span m='2763010'>attenuation</span> <span
  m='2763580'>at</span> <span m='2763670'>the</span> <span
  m='2763760'>higher</span> <span m='2763970'>frequencies</span> <span
  m='2765140'>than</span> <span m='2765290'>impulse</span> <span
  m='2765680'>invariance</span> <span m='2766240'>will.</span> <span
  m='2767030'>And</span> <span m='2767600'>I</span> <span
  m='2767720'>don't</span> <span m='2767960'>know</span> <span
  m='2768200'>if</span> <span m='2768320'>you</span> <span
  m='2768470'>can</span> <span m='2768770'>really</span> <span
  m='2769220'>see</span> <span m='2769580'>the</span> <span
  m='2769700'>fact</span> <span m='2770060'>that</span> <span
  m='2770270'>the</span> <span m='2771920'>passband</span> <span
  m='2772610'>specs</span> <span m='2773060'>were</span> <span
  m='2773240'>exceeded</span> <span m='2778400'>for</span> <span
  m='2778550'>the</span> <span m='2778820'>bilinear</span> <span
  m='2779420'>design.</span> <span m='2780990'>In</span> <span
  m='2781040'>fact,</span> <span m='2781560'>when</span> <span
  m='2781640'>you</span> <span m='2781760'>look</span> <span
  m='2781970'>at</span> <span m='2782030'>these</span> <span
  m='2782210'>view</span> <span m='2782390'>graphs</span> <span
  m='2783260'>in</span> <span m='2783410'>the</span> <span
  m='2783560'>study</span> <span m='2783890'>guide,</span> <span
  m='2784250'>I</span> <span m='2784310'>think</span> <span
  m='2784940'>you'll</span> <span m='2785090'>see</span> <span
  m='2785450'>that</span> <span m='2786080'>for</span> <span
  m='2786500'>impulse</span> <span m='2786980'>invariance</span> <span
  m='2788420'>the</span> <span m='2789860'>curve</span> <span
  m='2790280'>is</span> <span m='2790340'>slightly</span> <span
  m='2790760'>lower</span> <span m='2791300'>than</span> <span
  m='2791450'>it</span> <span m='2791570'>is</span> <span m='2791720'>for</span>
  <span m='2791840'>the</span> <span m='2791930'>bilinear</span> <span
  m='2792440'>transformation</span> </p><p><span m='2794810'>OK</span> <span
  m='2795110'>well,</span> <span m='2796160'>look.</span> <span
  m='2796400'>This</span> <span m='2796880'>is</span> <span m='2797540'>a</span>
  <span m='2798590'>simple</span> <span m='2799250'>example</span> <span
  m='2800870'>that</span> <span m='2801650'>hopefully</span> <span
  m='2802310'>at</span> <span m='2802400'>least</span> <span
  m='2803120'>illustrates</span> <span m='2803750'>for</span> <span
  m='2804020'>you</span> <span m='2804590'>the</span> <span
  m='2804800'>basic</span> <span m='2805430'>procedure</span> <span
  m='2806180'>involved</span> <span m='2806960'>in</span> <span
  m='2807680'>carrying</span> <span m='2808130'>through</span> <span
  m='2809000'>a</span> <span m='2809060'>design</span> <span
  m='2809660'>of</span> <span m='2809780'>an</span> <span
  m='2809870'>infinite</span> <span m='2810200'>impulse</span> <span
  m='2810560'>response</span> <span m='2811460'>filter</span> <span
  m='2812510'>using</span> <span m='2813650'>impulse</span> <span
  m='2814070'>invariance</span> <span m='2814940'>and</span> <span
  m='2815030'>the</span> <span m='2815120'>bilinear</span> <span
  m='2815600'>transformation.</span> <span m='2817610'>There</span> <span
  m='2817880'>are</span> <span m='2818300'>other</span> <span
  m='2818930'>examples</span> <span m='2819860'>that</span> <span
  m='2820130'>are</span> <span m='2820250'>considered</span> <span
  m='2820730'>in</span> <span m='2820820'>the</span> <span
  m='2820900'>text.</span> <span m='2821840'>There</span> <span
  m='2822170'>is</span> <span m='2822760'>a</span> <span
  m='2822830'>discussion</span> <span m='2823580'>of</span> <span
  m='2826830'>digital</span> <span m='2827820'>Chebyshev</span> <span
  m='2828360'>filters,</span> <span m='2828900'>in</span> <span
  m='2828990'>other</span> <span m='2829170'>words</span> <span
  m='2830010'>digital</span> <span m='2830370'>designs</span> <span
  m='2831240'>beginning</span> <span m='2831660'>from</span> <span
  m='2831840'>an</span> <span m='2831930'>analog</span> <span
  m='2832350'>Chebyshev</span> <span m='2832880'>filter.</span> <span
  m='2833850'>And</span> <span m='2833970'>you'll</span> <span
  m='2834120'>also</span> <span m='2834390'>have</span> <span
  m='2834540'>an</span> <span m='2834630'>opportunity</span> <span
  m='2835350'>to</span> <span m='2835440'>carry</span> <span
  m='2835950'>through</span> <span m='2836250'>some</span> <span
  m='2836490'>designs</span> <span m='2836940'>in</span> <span
  m='2837030'>the</span> <span m='2837120'>study</span> <span
  m='2837565'>guide.</span> </p><p><span m='2840235'>A</span> <span
  m='2840680'>point</span> <span m='2841100'>that</span> <span
  m='2841430'>I</span> <span m='2841700'>would</span> <span
  m='2841880'>like</span> <span m='2842630'>to</span> <span
  m='2843110'>mention</span> <span m='2843500'>briefly</span> <span
  m='2844040'>is</span> <span m='2844220'>that</span> <span
  m='2844970'>most</span> <span m='2845330'>of</span> <span
  m='2845450'>the</span> <span m='2845540'>discussion,</span> <span
  m='2846330'>in</span> <span m='2846430'>fact</span> <span
  m='2846540'>all</span> <span m='2846740'>of</span> <span
  m='2846830'>the</span> <span m='2846920'>discussion</span> <span
  m='2847820'>that</span> <span m='2847940'>we've</span> <span
  m='2848120'>gone</span> <span m='2848420'>through,</span> <span
  m='2849260'>has</span> <span m='2849440'>focused</span> <span
  m='2849950'>entirely</span> <span m='2850850'>on</span> <span
  m='2851300'>lowpass</span> <span m='2852140'>filters.</span> <span
  m='2853410'>In</span> <span m='2853430'>fact,</span> <span
  m='2854340'>the</span> <span m='2854600'>discussion</span> <span
  m='2855110'>generalizes</span> <span m='2856310'>in</span> <span
  m='2856460'>a</span> <span m='2856940'>fairly</span> <span
  m='2857270'>straightforward</span> <span m='2857930'>way</span> <span
  m='2858860'>to</span> <span m='2859100'>bandpass,</span> <span
  m='2860180'>bandstop,</span> <span m='2861030'>highpass,</span> <span
  m='2861710'>et cetera</span> <span m='2862040'>filters.</span> <span
  m='2863000'>In</span> <span m='2863090'>particular,</span> <span
  m='2863960'>as</span> <span m='2864550'>is</span> <span
  m='2864740'>discussed</span> <span m='2865250'>in</span> <span
  m='2865340'>some</span> <span m='2865550'>detail</span> <span
  m='2866030'>in</span> <span m='2866150'>the</span> <span
  m='2866240'>text,</span> <span m='2867530'>there</span> <span
  m='2868070'>are</span> <span m='2868790'>a</span> <span
  m='2868850'>class</span> <span m='2869270'>of</span> <span
  m='2869330'>frequency</span> <span m='2869870'>transformations</span> <span
  m='2871400'>that</span> <span m='2871790'>allow</span> <span
  m='2872600'>lowpass</span> <span m='2873230'>designs</span> <span
  m='2874010'>to</span> <span m='2874220'>get</span> <span
  m='2874430'>converted</span> <span m='2875420'>to</span> <span
  m='2875900'>bandstop,</span> <span m='2876680'>bandpass,</span> <span
  m='2877250'>highpass,</span> <span m='2877790'>et cetera</span> <span
  m='2878190'>designs.</span> </p><p><span m='2880010'>So</span> <span
  m='2880460'>this</span> <span m='2881450'>concludes</span> <span
  m='2882260'>our</span> <span m='2883160'>discussion</span> <span
  m='2884000'>of</span> <span m='2884540'>design</span> <span
  m='2884990'>procedures</span> <span m='2885980'>for</span> <span
  m='2887600'>recursive</span> <span m='2888470'>or</span> <span
  m='2888860'>infinite</span> <span m='2889250'>impulse</span> <span
  m='2889640'>response</span> <span m='2890380'>digital</span> <span
  m='2890750'>filters.</span> <span m='2891860'>In</span> <span
  m='2891980'>the</span> <span m='2892040'>next</span> <span
  m='2892310'>lecture</span> <span m='2893240'>I'll</span> <span
  m='2894800'>discuss</span> <span m='2895520'>the</span> <span
  m='2895760'>design</span> <span m='2896390'>of</span> <span
  m='2896660'>finite</span> <span m='2897080'>impulse</span> <span
  m='2897470'>response</span> <span m='2898130'>filters,</span> <span
  m='2898700'>and</span> <span m='2899150'>in</span> <span
  m='2900140'>particular</span> <span m='2900830'>introduce</span> <span
  m='2902000'>a</span> <span m='2902060'>number</span> <span
  m='2902390'>of</span> <span m='2902510'>designs,</span> <span
  m='2904640'>one</span> <span m='2904910'>of</span> <span
  m='2905030'>which</span> <span m='2905330'>corresponds</span> <span
  m='2905960'>to</span> <span m='2906080'>a</span> <span
  m='2906140'>class</span> <span m='2906500'>of</span> <span
  m='2906590'>algorithmic</span> <span m='2907160'>designs.</span> <span
  m='2908020'>Thank</span> <span m='2908100'>you.</span> </p><p><span
  m='2910500'>[MUSIC PLAYING]</span> </p><p></p>
embedded_media:
  - uid: cf3af19ce73b9d4ffb66fcb7f8be5800
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: MITRES_6_008S11_lec16.pdf
    title: MITRES_6_008S11_lec16.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-16-digital-butterworth-filters/MITRES_6_008S11_lec16.pdf
  - uid: 652d38bbbc6145c90554ce6aaaca284f
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: JtJ3v__Rx7E
  - uid: 68528e1f1bde648911ff6852db412862
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-16-digital-butterworth/id481803782?i=108362009
  - uid: c094d93bd8c553983b8fc42f3988c006
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec16_300k.mp4'
  - uid: f649e0816fc67431d79985c86cbd0550
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/JtJ3v__Rx7E/default.jpg'
  - uid: c265ccd0c20425ba3ab82d3240adfce1
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: JtJ3v__Rx7E
  - uid: e76f5ca495ac30409d48625b61419678
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: JtJ3v__Rx7E.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-16-digital-butterworth-filters/JtJ3v__Rx7E.srt
  - uid: db508ceb9cd89ae472accb8bf4d4f687
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: JtJ3v__Rx7E.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-16-digital-butterworth-filters/JtJ3v__Rx7E.pdf
  - uid: f2643185b9a780f5b1c3187727bcd08c
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: ac809d09df8e36f986b8e67990cd8945
    parent_uid: f94b2ff2eccc3fa733244a112fecf56e
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
