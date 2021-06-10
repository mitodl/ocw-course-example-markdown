---
order_index: null
title: 'Lecture 8: Constraints: Search, Domain Reduction'
template_type: Tabbed
uid: ee1eaf7d3728b0c47e7f2c98261083f4
parent_uid: 28d36d6426366698bf1ded18c6190be7
technical_location: >-
  https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-034-artificial-intelligence-fall-2010/lecture-videos/lecture-8-constraints-search-domain-reduction
short_url: lecture-8-constraints-search-domain-reduction
inline_embed_id: '33593032lecture8:constraints:search,domainreduction85942943'
about_this_resource_text: >-
  <p><strong>Description:</strong> This lecture covers map coloring and related
  scheduling problems.  We develop pseudocode for the domain reduction algorithm
  and consider how much constraint propagation is most efficient, and whether to
  start with the most or least constrained variables.</p>
  <p><strong>Instructor:</strong> Patrick H. Winston</p>
related_resources_text: ''
transcript: >-
  <p><span m='9409'>PATRICK</span> <span m='9573'>WINSTON:</span> <span
  m='9737'>It's</span> <span m='9901'>too</span> <span m='10065'>bad,</span>
  <span m='10229'>in</span> <span m='10393'>a</span> <span m='10557'>way,</span>
  <span m='10721'>that</span> <span m='10885'>we</span> <span
  m='11049'>can't</span> <span m='11213'>paint</span> <span
  m='11378'>everything</span> <span m='11732'>black,</span> <span
  m='12087'>because</span> <span m='12441'>this</span> <span
  m='12796'>map</span> <span m='13150'>coloring</span> <span
  m='13505'>problem</span> <span m='13859'>sure</span> <span
  m='14214'>would</span> <span m='14847'>be</span> <span m='15481'>a</span>
  <span m='16115'>lot</span> <span m='16749'>easier.</span> </p><p><span
  m='17383'>So</span> <span m='17792'>I</span> <span m='18202'>don't</span>
  <span m='18611'>know</span> <span m='19021'>what</span> <span
  m='19430'>we're</span> <span m='19840'>going</span> <span m='20249'>to</span>
  <span m='20659'>do</span> <span m='21068'>about</span> <span
  m='21478'>that.</span> </p><p><span m='21888'>How</span> <span
  m='22174'>long</span> <span m='22460'>is</span> <span m='22746'>this</span>
  <span m='23032'>going</span> <span m='23318'>to</span> <span
  m='23604'>take?</span> </p><p><span m='23890'>Here's</span> <span
  m='24029'>what</span> <span m='24168'>we're</span> <span
  m='24307'>going</span> <span m='24446'>to</span> <span m='24585'>do.</span>
  </p><p><span m='24724'>We're</span> <span m='24897'>going</span> <span
  m='25071'>to</span> <span m='25244'>wait</span> <span m='25418'>till</span>
  <span m='25591'>either</span> <span m='25765'>all</span> <span
  m='25938'>the</span> <span m='26112'>laptops</span> <span m='26285'>are</span>
  <span m='26459'>closed,</span> <span m='26946'>or</span> <span
  m='27433'>this</span> <span m='27920'>program</span> <span
  m='28407'>terminates,</span> <span m='28895'>whichever</span> <span
  m='29306'>comes</span> <span m='29718'>first.</span> </p><p><span
  m='32499'>So</span> <span m='32770'>how</span> <span m='33041'>long</span>
  <span m='33312'>is</span> <span m='33583'>this</span> <span
  m='33854'>going</span> <span m='34125'>to</span> <span m='34396'>take?</span>
  </p><p><span m='34667'>I</span> <span m='35142'>actually</span> <span
  m='35618'>don't</span> <span m='36093'>know.</span> </p><p><span
  m='36569'>I</span> <span m='36744'>think</span> <span m='36919'>it'll</span>
  <span m='37094'>take</span> <span m='37269'>more</span> <span
  m='37444'>than</span> <span m='37620'>the</span> <span m='37795'>life</span>
  <span m='37970'>time</span> <span m='38145'>of</span> <span
  m='38320'>the</span> <span m='38495'>universe,</span> <span
  m='38671'>but</span> <span m='38929'>I'm</span> <span m='39188'>not</span>
  <span m='39447'>sure.</span> </p><p><span m='39706'>So</span> <span
  m='40039'>let's</span> <span m='40373'>take</span> <span m='40707'>a</span>
  <span m='41040'>look</span> <span m='41374'>at</span> <span m='41708'>a</span>
  <span m='42041'>slightly</span> <span m='42375'>easier</span> <span
  m='42709'>map</span> <span m='43309'>coloring</span> <span
  m='43910'>problem.</span> </p><p><span m='44511'>We'll</span> <span
  m='44739'>stop</span> <span m='44967'>this</span> <span m='45195'>one</span>
  <span m='45423'>and</span> <span m='45651'>change</span> <span
  m='45879'>the</span> <span m='46107'>map</span> <span m='46335'>to</span>
  <span m='46563'>something</span> <span m='46791'>I</span> <span
  m='47019'>call</span> <span m='47247'>[?</span> <span
  m='47936'>simplicia.</span> <span m='48625'>?]</span> </p><p><span
  m='49315'>There's</span> <span m='49758'>26</span> <span
  m='50202'>states,</span> <span m='50646'>one</span> <span m='51090'>for</span>
  <span m='51534'>each</span> <span m='51977'>letter</span> <span
  m='52421'>in</span> <span m='52865'>the</span> <span
  m='53309'>alphabet.</span> </p><p><span m='53753'>And</span> <span
  m='53917'>what</span> <span m='54081'>we're</span> <span
  m='54245'>going</span> <span m='54410'>to</span> <span m='54574'>do</span>
  <span m='54738'>is</span> <span m='54903'>we're</span> <span
  m='55067'>going</span> <span m='55231'>to</span> <span m='55396'>do</span>
  <span m='55560'>a</span> <span m='55724'>depth</span> <span
  m='55889'>first</span> <span m='56493'>search</span> <span
  m='57097'>for</span> <span m='57701'>a</span> <span m='58305'>suitable</span>
  <span m='58910'>coloring</span> <span m='59514'>of</span> <span
  m='60118'>this</span> <span m='60722'>map.</span> </p><p><span
  m='61327'>We're</span> <span m='61541'>going</span> <span m='61756'>to</span>
  <span m='61970'>go</span> <span m='62185'>in</span> <span
  m='62399'>order,</span> <span m='62614'>A,</span> <span m='62828'>B,</span>
  <span m='63043'>C,</span> <span m='63257'>D,</span> <span m='63472'>E.</span>
  <span m='63686'>And</span> <span m='63901'>as</span> <span
  m='64115'>I've</span> <span m='64330'>suggested</span> <span
  m='64710'>here,</span> <span m='65090'>at</span> <span m='65471'>each</span>
  <span m='65851'>level</span> <span m='66232'>we're</span> <span
  m='66612'>going</span> <span m='66992'>to</span> <span m='67373'>rotate</span>
  <span m='67753'>the</span> <span m='68134'>color</span> <span
  m='68507'>choices</span> <span m='68881'>so</span> <span m='69255'>we</span>
  <span m='69628'>don't</span> <span m='70002'>over</span> <span
  m='70376'>use</span> <span m='70749'>any</span> <span m='71123'>one</span>
  <span m='71497'>color.</span> </p><p><span m='71871'>So</span> <span
  m='72197'>if</span> <span m='72523'>we</span> <span m='72849'>launch</span>
  <span m='73175'>this</span> <span m='73502'>particular</span> <span
  m='73828'>search,</span> <span m='74154'>this</span> <span
  m='74480'>depth</span> <span m='74807'>first</span> <span
  m='75302'>attempt</span> <span m='75797'>to</span> <span
  m='76292'>color</span> <span m='76787'>this</span> <span m='77282'>map.</span>
  </p><p><span m='77777'>There</span> <span m='78010'>it</span> <span
  m='78244'>goes.</span> </p><p><span m='78478'>And</span> <span
  m='78840'>maybe</span> <span m='79203'>we</span> <span m='79566'>should</span>
  <span m='79929'>wait</span> <span m='80292'>until</span> <span
  m='80655'>it</span> <span m='81018'>terminates.</span> </p><p><span
  m='81381'>Or</span> <span m='81726'>maybe</span> <span m='82072'>we</span>
  <span m='82418'>should</span> <span m='82763'>just</span> <span
  m='83109'>let</span> <span m='83455'>it</span> <span m='83801'>run</span>
  <span m='84146'>and</span> <span m='84492'>it'll</span> <span
  m='84838'>terminate,</span> <span m='85184'>perhaps,</span> <span
  m='85611'>sometime</span> <span m='86038'>within</span> <span
  m='86465'>the</span> <span m='86892'>lecture.</span> </p><p><span
  m='87320'>Or</span> <span m='87647'>maybe</span> <span m='87975'>we</span>
  <span m='88302'>should</span> <span m='88630'>just</span> <span
  m='88957'>let</span> <span m='89285'>it</span> <span m='89612'>run</span>
  <span m='89940'>over</span> <span m='90267'>the</span> <span
  m='90595'>weekend.</span> </p><p><span m='90923'>Or</span> <span
  m='91139'>how</span> <span m='91356'>long</span> <span m='91573'>do</span>
  <span m='91790'>you</span> <span m='92007'>think</span> <span
  m='92224'>we</span> <span m='92441'>would</span> <span m='92658'>have</span>
  <span m='92875'>to</span> <span m='93092'>wait,</span> <span
  m='93309'>if</span> <span m='93526'>we</span> <span m='93743'>want</span>
  <span m='93960'>to</span> <span m='94422'>come</span> <span
  m='94884'>back</span> <span m='95346'>and</span> <span m='95809'>watch</span>
  <span m='96271'>it</span> <span m='96733'>terminate?</span> </p><p><span
  m='97196'>At</span> <span m='97535'>roughly</span> <span m='97874'>30</span>
  <span m='98214'>frames</span> <span m='98553'>a</span> <span
  m='98892'>second--</span> <span m='99232'>I'm</span> <span
  m='99439'>calculating</span> <span m='99647'>it</span> <span
  m='99855'>all</span> <span m='100063'>in</span> <span m='100271'>my</span>
  <span m='100479'>head,</span> <span m='100686'>I</span> <span
  m='100894'>don't</span> <span m='101102'>want</span> <span
  m='101310'>to</span> <span m='101518'>bet</span> <span m='101726'>my</span>
  <span m='101934'>life</span> <span m='102442'>on</span> <span
  m='102950'>it--</span> <span m='103458'>but</span> <span m='103966'>I</span>
  <span m='104474'>think</span> <span m='104982'>about</span> <span
  m='105490'>5,000</span> <span m='105998'>years.</span> </p><p><span
  m='106506'>And</span> <span m='106775'>if</span> <span m='107044'>we</span>
  <span m='107313'>want</span> <span m='107583'>to</span> <span
  m='107852'>use</span> <span m='108121'>as</span> <span m='108391'>many</span>
  <span m='108660'>states</span> <span m='108929'>as</span> <span
  m='109198'>there</span> <span m='109468'>are</span> <span m='109737'>in</span>
  <span m='110006'>the</span> <span m='110276'>United</span> <span
  m='110683'>States,</span> <span m='111091'>in</span> <span
  m='111499'>this</span> <span m='111907'>demonstration,</span> <span
  m='112314'>you</span> <span m='112722'>get</span> <span m='113130'>up</span>
  <span m='113538'>to</span> <span m='113946'>numbers</span> <span
  m='114656'>like</span> <span m='115366'>10</span> <span m='116076'>to</span>
  <span m='116787'>the</span> <span m='117497'>17th</span> <span
  m='118207'>years--</span> <span m='118918'>17th,</span> <span
  m='119251'>18th,</span> <span m='119585'>16th,</span> <span
  m='119919'>I'm</span> <span m='120252'>not</span> <span
  m='120586'>exactly</span> <span m='120920'>sure.</span> </p><p><span
  m='121254'>I</span> <span m='121734'>did</span> <span m='122214'>a</span>
  <span m='122695'>rough</span> <span m='123175'>calculation.</span>
  </p><p><span m='123656'>And,</span> <span m='123877'>of</span> <span
  m='124098'>course,</span> <span m='124320'>you</span> <span
  m='124541'>could</span> <span m='124763'>do</span> <span
  m='124984'>some</span> <span m='125206'>parallels</span> <span
  m='125427'>into</span> <span m='125649'>that,</span> <span
  m='125870'>and</span> <span m='126092'>it's</span> <span m='126250'>not</span>
  <span m='126409'>as</span> <span m='126567'>bad</span> <span
  m='126726'>as</span> <span m='126884'>chess,</span> <span
  m='127043'>where</span> <span m='127201'>you</span> <span
  m='127360'>need</span> <span m='127518'>all</span> <span m='127677'>the</span>
  <span m='127835'>atoms</span> <span m='127994'>in</span> <span
  m='128142'>the</span> <span m='128290'>universe</span> <span
  m='128438'>and</span> <span m='128586'>you</span> <span
  m='128735'>still</span> <span m='128883'>can't</span> <span
  m='129031'>do</span> <span m='129179'>it,</span> <span m='129328'>and</span>
  <span m='129636'>things</span> <span m='129945'>like</span> <span
  m='130253'>that.</span> </p><p><span m='130562'>Acting</span> <span
  m='130873'>as</span> <span m='131185'>computers.</span> </p><p><span
  m='131497'>But</span> <span m='132077'>still,</span> <span
  m='132658'>it's</span> <span m='133238'>pretty</span> <span
  m='133819'>horrendous.</span> </p><p><span m='134400'>The</span> <span
  m='135017'>problem</span> <span m='135634'>is,</span> <span
  m='136251'>well</span> <span m='136869'>the</span> <span
  m='137486'>problem</span> <span m='138103'>is</span> <span
  m='138721'>illustrated</span> <span m='139338'>by</span> <span
  m='139955'>this</span> <span m='140573'>diagram</span> <span
  m='140892'>I</span> <span m='141211'>put</span> <span m='141531'>in</span>
  <span m='141850'>back</span> <span m='142170'>of</span> <span
  m='142489'>me.</span> </p><p><span m='142809'>If</span> <span
  m='143273'>you</span> <span m='143737'>do</span> <span m='144201'>a</span>
  <span m='144665'>depth</span> <span m='145129'>first</span> <span
  m='145593'>search</span> <span m='146057'>and</span> <span
  m='146521'>you</span> <span m='146985'>have</span> <span m='147449'>a</span>
  <span m='147914'>problem</span> <span m='149115'>like</span> <span
  m='150316'>Texas.</span> </p><p><span m='151517'>If</span> <span
  m='151984'>you</span> <span m='152451'>label...</span> <span
  m='152918'>if</span> <span m='153385'>you</span> <span
  m='153853'>assign</span> <span m='154320'>a</span> <span
  m='154787'>color</span> <span m='155254'>to</span> <span
  m='155721'>Arizona,</span> <span m='156189'>Oklahoma,</span> <span
  m='156777'>Arkansas,</span> <span m='157365'>and</span> <span
  m='157953'>Louisiana</span> <span m='158541'>first,</span> <span
  m='159129'>and</span> <span m='159717'>then</span> <span
  m='160305'>wait</span> <span m='160893'>around</span> <span
  m='161463'>to</span> <span m='162033'>Texas</span> <span
  m='162603'>last,</span> <span m='163173'>then</span> <span
  m='163743'>you</span> <span m='164313'>get</span> <span
  m='164883'>yourself</span> <span m='165453'>into</span> <span
  m='166023'>a</span> <span m='166593'>bind</span> <span m='167163'>by</span>
  <span m='167733'>your</span> <span m='168074'>fourth</span> <span
  m='168415'>choice,</span> <span m='168756'>that</span> <span
  m='169097'>you</span> <span m='169438'>don't</span> <span
  m='169779'>discover</span> <span m='170120'>until</span> <span
  m='170461'>you're</span> <span m='170803'>48th</span> <span
  m='171887'>choice.</span> </p><p><span m='172972'>So</span> <span
  m='173251'>what</span> <span m='173530'>happens</span> <span
  m='173809'>then,</span> <span m='174088'>is</span> <span
  m='174367'>that</span> <span m='174646'>you</span> <span
  m='174925'>start</span> <span m='175204'>developing</span> <span
  m='175483'>this</span> <span m='175762'>tree</span> <span
  m='176042'>like</span> <span m='176583'>this,</span> <span
  m='177124'>you</span> <span m='177665'>get</span> <span m='178206'>to</span>
  <span m='178748'>those</span> <span m='179289'>states</span> <span
  m='179830'>surrounding</span> <span m='180371'>Texas.</span> </p><p><span
  m='180913'>Texas</span> <span m='181272'>is</span> <span
  m='181632'>last</span> <span m='181992'>state</span> <span
  m='182351'>assigned</span> <span m='182711'>a</span> <span
  m='183071'>color</span> <span m='183430'>and</span> <span
  m='183790'>there's</span> <span m='184150'>nothing</span> <span
  m='184542'>left</span> <span m='184934'>for</span> <span m='185326'>it.</span>
  </p><p><span m='185718'>And</span> <span m='185972'>that</span> <span
  m='186227'>problem</span> <span m='186482'>was</span> <span
  m='186737'>there</span> <span m='186992'>on</span> <span m='187246'>the</span>
  <span m='187501'>fourth</span> <span m='187756'>choice,</span> <span
  m='188011'>and</span> <span m='188266'>you</span> <span
  m='188521'>don't</span> <span m='188864'>discover</span> <span
  m='189207'>it</span> <span m='189550'>until</span> <span
  m='189893'>your</span> <span m='190236'>50th</span> <span
  m='190579'>choice.</span> </p><p><span m='190923'>So</span> <span
  m='191461'>you</span> <span m='191999'>develop</span> <span
  m='192537'>a</span> <span m='193075'>horrendous,</span> <span
  m='193613'>impossible,</span> <span m='194151'>impossible</span> <span
  m='194689'>search.</span> </p><p><span m='195227'>So</span> <span
  m='195731'>you</span> <span m='196236'>simply</span> <span
  m='196741'>can't</span> <span m='197246'>do</span> <span m='197750'>it</span>
  <span m='198255'>that</span> <span m='198760'>way.</span> </p><p><span
  m='199265'>But</span> <span m='199905'>now,</span> <span m='200546'>not</span>
  <span m='201186'>to</span> <span m='201827'>worry.</span> </p><p><span
  m='202468'>I've</span> <span m='202734'>come</span> <span
  m='203001'>equipped</span> <span m='203268'>with</span> <span
  m='203535'>the</span> <span m='203802'>idea</span> <span m='204069'>of</span>
  <span m='204336'>constraint</span> <span m='204603'>propagation.</span>
  </p><p><span m='206605'>So</span> <span m='206801'>we</span> <span
  m='206998'>could</span> <span m='207194'>just</span> <span
  m='207391'>take</span> <span m='207587'>a</span> <span
  m='207784'>country</span> <span m='207980'>with</span> <span
  m='208177'>four</span> <span m='208374'>states,</span> <span
  m='208930'>like</span> <span m='209486'>this.</span> </p><p><span
  m='210042'>Each</span> <span m='210524'>can</span> <span m='211006'>be</span>
  <span m='211488'>labeled</span> <span m='211970'>red,</span> <span
  m='212452'>green,</span> <span m='212934'>blue</span> <span
  m='213416'>and</span> <span m='213898'>yellow.</span> </p><p><span
  m='214380'>So</span> <span m='214603'>just</span> <span m='214826'>like</span>
  <span m='215049'>in</span> <span m='215273'>a</span> <span
  m='215496'>case</span> <span m='215719'>of</span> <span m='215943'>line</span>
  <span m='216166'>drawings,</span> <span m='216389'>we'll</span> <span
  m='216613'>pile</span> <span m='216836'>up</span> <span m='217059'>all</span>
  <span m='217283'>the</span> <span m='217703'>possible</span> <span
  m='218123'>things</span> <span m='218544'>that</span> <span
  m='218964'>the</span> <span m='219385'>value</span> <span
  m='219805'>can</span> <span m='220225'>be--</span> <span
  m='220646'>red,</span> <span m='221066'>green,</span> <span
  m='221487'>blue</span> <span m='221976'>and</span> <span
  m='222465'>yellow.</span> </p><p><span m='222954'>Red,</span> <span
  m='224088'>green,</span> <span m='225223'>blue</span> <span
  m='226357'>and</span> <span m='227492'>yellow.</span> </p><p><span
  m='228627'>And</span> <span m='229105'>we</span> <span m='229583'>start</span>
  <span m='230062'>up</span> <span m='230540'>constraint</span> <span
  m='231018'>propagation.</span> </p><p><span m='231497'>So</span> <span
  m='231822'>we</span> <span m='232147'>say</span> <span m='232473'>for</span>
  <span m='232798'>the</span> <span m='233123'>upper</span> <span
  m='233449'>left</span> <span m='233774'>hand</span> <span
  m='234099'>corner</span> <span m='234425'>state,</span> <span
  m='234750'>is</span> <span m='235075'>there</span> <span m='235401'>any</span>
  <span m='235788'>reason</span> <span m='236176'>to</span> <span
  m='236564'>believe</span> <span m='236952'>that</span> <span
  m='237340'>R</span> <span m='237728'>is</span> <span
  m='238116'>impossible?</span> </p><p><span m='238504'>Well</span> <span
  m='238673'>we</span> <span m='238843'>look</span> <span m='239013'>at</span>
  <span m='239183'>our</span> <span m='239353'>neighbors</span> <span
  m='239522'>and</span> <span m='239692'>see</span> <span m='239862'>what</span>
  <span m='240032'>kind</span> <span m='240202'>of</span> <span
  m='240372'>constraint</span> <span m='240799'>flows</span> <span
  m='241226'>in</span> <span m='241653'>from</span> <span
  m='242080'>them.</span> </p><p><span m='242508'>And</span> <span
  m='242704'>sure,</span> <span m='242900'>this</span> <span
  m='243097'>guy</span> <span m='243293'>could</span> <span m='243490'>be</span>
  <span m='243686'>green,</span> <span m='243883'>and</span> <span
  m='244079'>this</span> <span m='244276'>guy</span> <span
  m='244584'>could</span> <span m='244893'>be</span> <span
  m='245202'>blue.</span> </p><p><span m='245511'>They</span> <span
  m='245926'>don't</span> <span m='246341'>have</span> <span
  m='246756'>to</span> <span m='247171'>be</span> <span m='247587'>red,</span>
  <span m='248002'>so</span> <span m='248417'>there's</span> <span
  m='248832'>nothing</span> <span m='249248'>that</span> <span
  m='249932'>rules</span> <span m='250616'>out</span> <span
  m='251300'>red.</span> </p><p><span m='251984'>And</span> <span
  m='252203'>there's</span> <span m='252422'>nothing</span> <span
  m='252641'>the</span> <span m='252861'>rules</span> <span
  m='253080'>out</span> <span m='253299'>blue.</span> </p><p><span
  m='253519'>And</span> <span m='253938'>there's</span> <span
  m='254357'>nothing</span> <span m='254776'>that</span> <span
  m='255196'>rules</span> <span m='255615'>out</span> <span
  m='256034'>yellow.</span> </p><p><span m='256454'>And</span> <span
  m='256764'>there's</span> <span m='257074'>nothing</span> <span
  m='257384'>that</span> <span m='257694'>rules</span> <span
  m='258004'>out</span> <span m='258314'>green.</span> </p><p><span
  m='258624'>So</span> <span m='259021'>constraint</span> <span
  m='259418'>propagation</span> <span m='259815'>just</span> <span
  m='260212'>sits</span> <span m='260609'>there</span> <span
  m='261006'>with</span> <span m='261403'>its</span> <span
  m='261800'>finger</span> <span m='262197'>up</span> <span
  m='262595'>its</span> <span m='263337'>nose,</span> <span
  m='264079'>doing</span> <span m='264821'>nothing.</span> </p><p><span
  m='265564'>So</span> <span m='266084'>it</span> <span
  m='266604'>doesn't</span> <span m='267124'>look</span> <span
  m='267644'>like</span> <span m='268164'>we</span> <span m='268684'>can</span>
  <span m='269204'>use</span> <span m='269724'>either</span> <span
  m='270244'>depth</span> <span m='270764'>first</span> <span
  m='271284'>search,</span> <span m='271804'>or</span> <span
  m='272760'>constraint</span> <span m='273716'>propagation.</span> </p><p><span
  m='274673'>So</span> <span m='275069'>we</span> <span m='275465'>could</span>
  <span m='275861'>just</span> <span m='276258'>give</span> <span
  m='276654'>up</span> <span m='277050'>and</span> <span m='277446'>cry.</span>
  </p><p><span m='277843'>But</span> <span m='278273'>maybe</span> <span
  m='278703'>there's</span> <span m='279133'>some</span> <span
  m='279563'>other</span> <span m='279993'>approach</span> <span
  m='280423'>that</span> <span m='280853'>will</span> <span
  m='281283'>help.</span> </p><p><span m='281714'>So</span> <span
  m='282126'>let</span> <span m='282539'>me</span> <span
  m='282952'>actually</span> <span m='283365'>work</span> <span
  m='283778'>the</span> <span m='284191'>Texas</span> <span
  m='284604'>problem.</span> </p><p><span m='285017'>So</span> <span
  m='285856'>with</span> <span m='286695'>apologies</span> <span
  m='287534'>to</span> <span m='288373'>Houston</span> <span
  m='289212'>and</span> <span m='290051'>Tyler,</span> <span
  m='290890'>here's</span> <span m='291143'>a</span> <span m='291396'>map</span>
  <span m='291650'>of</span> <span m='291903'>Texas.</span> </p><p><span
  m='297863'>There</span> <span m='298163'>we</span> <span
  m='298463'>are.</span> </p><p><span m='298764'>And</span> <span
  m='299378'>here's,</span> <span m='299992'>roughly</span> <span
  m='300606'>speaking,</span> <span m='301220'>Arizona</span> <span
  m='301834'>is</span> <span m='302301'>over</span> <span m='302768'>here</span>
  <span m='303235'>somewhere.</span> </p><p><span m='303702'>And</span> <span
  m='303985'>we've</span> <span m='304269'>got</span> <span
  m='304553'>Oklahoma</span> <span m='304836'>in</span> <span
  m='305120'>there.</span> </p><p><span m='305404'>And</span> <span
  m='306110'>old</span> <span m='306816'>Bill</span> <span
  m='307523'>Clinton's</span> <span m='308229'>state,</span> <span
  m='308935'>Arkansas.</span> </p><p><span m='309642'>And</span> <span
  m='309971'>then</span> <span m='310301'>Louisiana</span> <span
  m='310631'>sticks</span> <span m='310961'>out</span> <span
  m='311291'>there</span> <span m='311621'>a</span> <span
  m='311951'>little</span> <span m='312281'>bit.</span> </p><p><span
  m='312611'>So</span> <span m='313161'>there's</span> <span
  m='313712'>our</span> <span m='314262'>map</span> <span m='314813'>of</span>
  <span m='315363'>that</span> <span m='315914'>particular</span> <span
  m='316408'>part</span> <span m='316902'>of</span> <span m='317396'>the</span>
  <span m='317890'>country.</span> </p><p><span m='318384'>So</span> <span
  m='319177'>we've</span> <span m='319970'>got</span> <span
  m='320764'>Arizona</span> <span m='321557'>here,</span> <span
  m='322350'>Oklahoma</span> <span m='323144'>here,</span> <span
  m='323937'>Arkansas</span> <span m='324730'>here,</span> <span
  m='325524'>and</span> <span m='326191'>Louisiana</span> <span
  m='326858'>here,</span> <span m='327526'>and</span> <span
  m='328193'>Texas</span> <span m='328860'>here.</span> </p><p><span
  m='329528'>And</span> <span m='329955'>we</span> <span m='330383'>have</span>
  <span m='330811'>elected</span> <span m='331238'>to</span> <span
  m='331666'>assign</span> <span m='332094'>colors</span> <span
  m='332522'>to</span> <span m='332949'>these</span> <span
  m='333377'>states,</span> <span m='333805'>in</span> <span
  m='334233'>that</span> <span m='334666'>order.</span> </p><p><span
  m='335100'>So</span> <span m='335695'>this</span> <span m='336291'>is</span>
  <span m='336887'>one,</span> <span m='337483'>two,</span> <span
  m='338079'>three,</span> <span m='338675'>four.</span> </p><p><span
  m='342174'>And</span> <span m='342596'>we're</span> <span
  m='343019'>going</span> <span m='343442'>to</span> <span m='343864'>do</span>
  <span m='344287'>that.</span> </p><p><span m='344710'>We're</span> <span
  m='344930'>going</span> <span m='345150'>to</span> <span
  m='345370'>rotate</span> <span m='345590'>our</span> <span
  m='345811'>color</span> <span m='346031'>choices,</span> <span
  m='346251'>just</span> <span m='346471'>so</span> <span m='346691'>we</span>
  <span m='346912'>don't</span> <span m='347534'>over</span> <span
  m='348157'>use</span> <span m='348780'>any</span> <span m='349403'>one</span>
  <span m='350026'>color.</span> </p><p><span m='350649'>But</span> <span
  m='350875'>we're</span> <span m='351101'>going</span> <span
  m='351328'>to</span> <span m='351554'>also</span> <span m='351781'>have</span>
  <span m='352007'>a</span> <span m='352234'>look</span> <span
  m='352460'>at</span> <span m='352686'>Texas</span> <span m='352913'>as</span>
  <span m='353139'>we</span> <span m='353366'>go</span> <span
  m='353592'>around.</span> </p><p><span m='353819'>Because</span> <span
  m='354119'>Texas</span> <span m='354419'>is</span> <span m='354719'>a</span>
  <span m='355020'>state</span> <span m='355320'>that</span> <span
  m='355620'>borders</span> <span m='355920'>on</span> <span
  m='356221'>the</span> <span m='356521'>States</span> <span
  m='356821'>they</span> <span m='357122'>were</span> <span
  m='358073'>choosing</span> <span m='359024'>colors</span> <span
  m='359975'>for.</span> </p><p><span m='360926'>So</span> <span
  m='361317'>the</span> <span m='361708'>only</span> <span
  m='362099'>possible</span> <span m='362491'>colors</span> <span
  m='362882'>that</span> <span m='363273'>Texas</span> <span
  m='363664'>could</span> <span m='364056'>be</span> <span m='364447'>are</span>
  <span m='364838'>red,</span> <span m='365230'>green,</span> <span
  m='366598'>blue,</span> <span m='367966'>and</span> <span
  m='369334'>yellow.</span> </p><p><span m='370702'>So</span> <span
  m='371157'>as</span> <span m='371612'>we</span> <span m='372067'>make</span>
  <span m='372522'>our</span> <span m='372977'>choices</span> <span
  m='373432'>around</span> <span m='373887'>here,</span> <span
  m='374342'>we'll</span> <span m='374797'>say</span> <span
  m='375252'>that--</span> <span m='375707'>we</span> <span
  m='375960'>don't</span> <span m='376213'>have</span> <span
  m='376466'>to</span> <span m='376719'>adhere</span> <span m='376972'>to</span>
  <span m='377225'>any</span> <span m='377478'>particular</span> <span
  m='377731'>style--</span> <span m='377984'>we</span> <span
  m='378237'>can</span> <span m='378490'>say</span> <span m='378744'>that</span>
  <span m='379405'>Arizona</span> <span m='380066'>is</span> <span
  m='380727'>going</span> <span m='381389'>to</span> <span m='382050'>get</span>
  <span m='382711'>the</span> <span m='383372'>colored</span> <span
  m='384034'>red,</span> <span m='384695'>R.</span> <span
  m='385356'>That's</span> <span m='386018'>going</span> <span
  m='386304'>to</span> <span m='386590'>rule</span> <span m='386877'>out</span>
  <span m='387163'>R</span> <span m='387449'>over</span> <span
  m='387736'>here</span> <span m='388022'>for</span> <span
  m='388308'>Texas,</span> <span m='388595'>because</span> <span
  m='388881'>no</span> <span m='389167'>adjacent</span> <span
  m='389454'>states</span> <span m='390032'>can</span> <span
  m='390611'>have</span> <span m='391189'>the</span> <span
  m='391768'>same</span> <span m='392346'>color.</span> </p><p><span
  m='392925'>Then</span> <span m='393131'>we</span> <span m='393337'>go</span>
  <span m='393543'>over</span> <span m='393750'>to</span> <span
  m='393956'>Oklahoma,</span> <span m='394162'>and</span> <span
  m='394368'>we're</span> <span m='394575'>rotating</span> <span
  m='394781'>our</span> <span m='394987'>color</span> <span
  m='395194'>choices,</span> <span m='395652'>so</span> <span
  m='396111'>we'll</span> <span m='396570'>say</span> <span
  m='397029'>that</span> <span m='397487'>can</span> <span m='397946'>be</span>
  <span m='398405'>green.</span> </p><p><span m='398864'>And</span> <span
  m='399157'>that's</span> <span m='399451'>fine,</span> <span
  m='399744'>because</span> <span m='400038'>it's</span> <span
  m='400332'>consistent</span> <span m='400625'>with</span> <span
  m='400919'>the</span> <span m='401212'>red</span> <span
  m='401506'>here,</span> <span m='401800'>but</span> <span m='402024'>it</span>
  <span m='402248'>rules</span> <span m='402472'>out</span> <span
  m='402696'>the</span> <span m='402920'>possibility</span> <span
  m='403144'>that</span> <span m='403368'>Texas</span> <span
  m='404027'>could</span> <span m='404686'>be</span> <span
  m='405345'>green.</span> </p><p><span m='406004'>And</span> <span
  m='406583'>then</span> <span m='407162'>we</span> <span m='407742'>go</span>
  <span m='408321'>over</span> <span m='408900'>here</span> <span
  m='409480'>to</span> <span m='410059'>Arkansas,</span> <span
  m='410638'>red,</span> <span m='411218'>green,</span> <span
  m='411797'>blue.</span> </p><p><span m='412377'>That's</span> <span
  m='412740'>fine,</span> <span m='413103'>that's</span> <span
  m='413467'>consistent</span> <span m='413830'>with</span> <span
  m='414193'>the</span> <span m='414557'>green</span> <span m='414920'>on</span>
  <span m='415283'>Oklahoma,</span> <span m='415647'>but</span> <span
  m='415904'>if</span> <span m='416162'>we</span> <span m='416420'>look</span>
  <span m='416678'>at</span> <span m='416936'>its</span> <span
  m='417193'>neighbors</span> <span m='417451'>we</span> <span
  m='417709'>know</span> <span m='417967'>that</span> <span
  m='418225'>Texas</span> <span m='418483'>is</span> <span
  m='419098'>forever</span> <span m='419713'>forbidden</span> <span
  m='420328'>to</span> <span m='420943'>be</span> <span m='421558'>blue,</span>
  <span m='422173'>now.</span> </p><p><span m='422788'>So</span> <span
  m='423041'>now</span> <span m='423295'>we</span> <span m='423548'>go</span>
  <span m='423802'>over</span> <span m='424056'>to</span> <span
  m='424309'>Louisiana,</span> <span m='424563'>and</span> <span
  m='424816'>remember,</span> <span m='425070'>we're</span> <span
  m='425324'>rotating</span> <span m='425561'>our</span> <span
  m='425798'>color</span> <span m='426035'>choices</span> <span
  m='426272'>because</span> <span m='426510'>we</span> <span
  m='426747'>don't</span> <span m='426984'>want</span> <span
  m='427221'>to</span> <span m='427459'>overuse</span> <span
  m='428443'>them.</span> </p><p><span m='429428'>So</span> <span
  m='429591'>this</span> <span m='429755'>means</span> <span
  m='429919'>that</span> <span m='430082'>the</span> <span
  m='430246'>first</span> <span m='430410'>choice</span> <span
  m='430574'>we're</span> <span m='430737'>going</span> <span
  m='430901'>to</span> <span m='431065'>make</span> <span
  m='431229'>here,</span> <span m='431556'>for</span> <span
  m='431883'>Louisiana,</span> <span m='432210'>is</span> <span
  m='432537'>yellow.</span> </p><p><span m='435600'>And</span> <span
  m='435930'>that's</span> <span m='436260'>fine</span> <span
  m='436590'>because</span> <span m='436920'>it's</span> <span
  m='437250'>consistent</span> <span m='437580'>with</span> <span
  m='437910'>Arkansas,</span> <span m='438240'>but</span> <span
  m='438570'>it's</span> <span m='438909'>not</span> <span m='439249'>so</span>
  <span m='439589'>fine</span> <span m='439928'>because</span> <span
  m='440268'>it's</span> <span m='440608'>now</span> <span
  m='440948'>ruled</span> <span m='441287'>out</span> <span
  m='441627'>the</span> <span m='441967'>last</span> <span
  m='442307'>possibility</span> <span m='443341'>for</span> <span
  m='444375'>Texas.</span> </p><p><span m='445410'>So</span> <span
  m='445782'>even</span> <span m='446154'>though</span> <span
  m='446526'>Texas</span> <span m='446898'>is</span> <span
  m='447270'>going</span> <span m='447642'>to</span> <span m='448015'>be</span>
  <span m='448387'>the</span> <span m='448759'>48th</span> <span
  m='449131'>state</span> <span m='449503'>that</span> <span
  m='449875'>we</span> <span m='450248'>color,</span> <span
  m='450621'>we're</span> <span m='450995'>going</span> <span
  m='451369'>to</span> <span m='451742'>say,</span> <span m='452116'>at</span>
  <span m='452490'>this</span> <span m='452863'>point,</span> <span
  m='453237'>there's</span> <span m='453611'>no</span> <span
  m='453985'>need</span> <span m='454243'>in</span> <span
  m='454502'>going</span> <span m='454761'>on.</span> </p><p><span
  m='455020'>We'd</span> <span m='455487'>better</span> <span
  m='455954'>back</span> <span m='456421'>up.</span> </p><p><span
  m='456888'>Because</span> <span m='457111'>there's</span> <span
  m='457335'>nothing</span> <span m='457558'>left</span> <span
  m='457782'>for</span> <span m='458006'>Texas</span> <span
  m='458229'>when</span> <span m='458453'>we</span> <span m='458676'>get</span>
  <span m='458900'>around</span> <span m='459124'>to</span> <span
  m='459646'>coloring</span> <span m='460169'>it.</span> </p><p><span
  m='460692'>So</span> <span m='461139'>that</span> <span
  m='461586'>means</span> <span m='462033'>that</span> <span
  m='462480'>this</span> <span m='462927'>yellow</span> <span
  m='463374'>is</span> <span m='463821'>ruled</span> <span m='464268'>out</span>
  <span m='464715'>here.</span> </p><p><span m='465163'>This</span> <span
  m='466019'>yellow</span> <span m='466875'>reappears.</span> </p><p><span
  m='467732'>We</span> <span m='468114'>select</span> <span
  m='468496'>the</span> <span m='468878'>next</span> <span
  m='469261'>color</span> <span m='469643'>in</span> <span m='470025'>my</span>
  <span m='470407'>line</span> <span m='470790'>for</span> <span
  m='471172'>Louisiana,</span> <span m='471554'>which</span> <span
  m='471937'>happens</span> <span m='472412'>to</span> <span
  m='472888'>be</span> <span m='473363'>red.</span> </p><p><span
  m='473839'>And</span> <span m='474297'>now</span> <span
  m='474756'>that's</span> <span m='475215'>consistent</span> <span
  m='475674'>with</span> <span m='476132'>this</span> <span
  m='476591'>yellow</span> <span m='477050'>that's</span> <span
  m='477509'>still</span> <span m='477884'>left</span> <span
  m='478259'>for</span> <span m='478634'>Texas.</span> </p><p><span
  m='479010'>And</span> <span m='479215'>it's</span> <span
  m='479420'>also</span> <span m='479625'>consistent</span> <span
  m='479830'>with</span> <span m='480035'>the</span> <span
  m='480240'>blue</span> <span m='480445'>that's</span> <span
  m='481052'>up</span> <span m='481659'>here</span> <span m='482267'>for</span>
  <span m='482874'>Arkansas.</span> </p><p><span m='483482'>So</span> <span
  m='483793'>that's</span> <span m='484104'>cool.</span> </p><p><span
  m='484416'>I</span> <span m='484696'>wonder</span> <span m='484977'>if</span>
  <span m='485258'>maybe</span> <span m='485539'>we</span> <span
  m='485820'>could</span> <span m='486101'>make</span> <span
  m='486381'>an</span> <span m='486662'>algorithm</span> <span
  m='486943'>out</span> <span m='487224'>of</span> <span m='487505'>that,</span>
  <span m='487786'>and</span> <span m='488066'>solve</span> <span
  m='488346'>problems</span> <span m='488626'>like</span> <span
  m='488906'>this.</span> </p><p><span m='489187'>Do</span> <span
  m='489447'>you</span> <span m='489708'>see,</span> <span
  m='489969'>sort</span> <span m='490230'>of,</span> <span m='490491'>the</span>
  <span m='490752'>intuition</span> <span m='491013'>of</span> <span
  m='491274'>what</span> <span m='491535'>we're</span> <span
  m='491796'>doing?</span> </p><p><span m='492057'>We're</span> <span
  m='492319'>actually</span> <span m='492582'>using</span> <span
  m='492845'>the</span> <span m='493108'>martial</span> <span
  m='493370'>arts</span> <span m='493633'>principle,</span> <span
  m='493896'>again.</span> </p><p><span m='494159'>Because</span> <span
  m='494601'>the</span> <span m='495043'>whole</span> <span
  m='495485'>problem</span> <span m='495927'>is</span> <span
  m='496369'>that</span> <span m='496811'>local</span> <span
  m='497253'>constraints,</span> <span m='497696'>undiscovered</span> <span
  m='498116'>local</span> <span m='498536'>constraints,</span> <span
  m='498957'>are</span> <span m='499377'>causing</span> <span
  m='499798'>downstream</span> <span m='500849'>problems.</span> </p><p><span
  m='501900'>So</span> <span m='502207'>we're</span> <span
  m='502514'>going</span> <span m='502821'>to</span> <span m='503128'>use</span>
  <span m='503435'>the</span> <span m='503742'>enemy's</span> <span
  m='504049'>powers</span> <span m='504356'>against</span> <span
  m='504663'>him,</span> <span m='504970'>and</span> <span
  m='505148'>we're</span> <span m='505327'>going</span> <span
  m='505506'>to</span> <span m='505685'>look</span> <span m='505864'>at</span>
  <span m='506043'>those</span> <span m='506222'>local</span> <span
  m='506401'>constraints</span> <span m='506580'>as</span> <span
  m='506759'>we</span> <span m='506938'>go</span> <span m='507226'>and</span>
  <span m='507514'>make</span> <span m='507802'>sure</span> <span
  m='508090'>they're</span> <span m='508378'>not</span> <span
  m='508667'>going</span> <span m='508955'>downstream,</span> <span
  m='509243'>not</span> <span m='509531'>going</span> <span m='509819'>to</span>
  <span m='510108'>get</span> <span m='510625'>us</span> <span
  m='511142'>later</span> <span m='511659'>on.</span> </p><p><span
  m='512177'>So</span> <span m='512599'>now</span> <span m='513022'>I'm</span>
  <span m='513445'>going</span> <span m='513867'>to</span> <span
  m='514290'>look</span> <span m='514713'>like</span> <span
  m='515135'>I'm</span> <span m='515558'>getting</span> <span
  m='515981'>a</span> <span m='516403'>little</span> <span
  m='516826'>formal,</span> <span m='517249'>but</span> <span
  m='517452'>I'm</span> <span m='517656'>just</span> <span
  m='517860'>getting</span> <span m='518064'>a</span> <span
  m='518268'>little</span> <span m='518472'>bit</span> <span
  m='518676'>more</span> <span m='518880'>formal.</span> </p><p><span
  m='519084'>Because</span> <span m='519517'>I</span> <span
  m='519951'>want</span> <span m='520385'>to</span> <span m='520819'>have</span>
  <span m='521252'>some</span> <span m='521686'>language</span> <span
  m='522120'>that</span> <span m='522554'>I</span> <span m='522987'>can</span>
  <span m='523421'>use</span> <span m='523855'>to</span> <span
  m='524289'>describe</span> <span m='524492'>what's</span> <span
  m='524696'>going</span> <span m='524899'>on,</span> <span m='525103'>so</span>
  <span m='525306'>that</span> <span m='525510'>it's</span> <span
  m='525713'>clear</span> <span m='525917'>what</span> <span
  m='526120'>the</span> <span m='526324'>choices</span> <span
  m='527342'>are.</span> </p><p><span m='528360'>So</span> <span
  m='528560'>to</span> <span m='528760'>start</span> <span m='528960'>off</span>
  <span m='529160'>with,</span> <span m='529360'>we're</span> <span
  m='529561'>going</span> <span m='529761'>to</span> <span
  m='529961'>have</span> <span m='530161'>to</span> <span m='530361'>have</span>
  <span m='530561'>some</span> <span m='530762'>vocabulary.</span> </p><p><span
  m='532497'>So</span> <span m='532978'>let's</span> <span
  m='533459'>start</span> <span m='533941'>up</span> <span m='534422'>our</span>
  <span m='534904'>vocabulary</span> <span m='535385'>here.</span> </p><p><span
  m='535867'>We're</span> <span m='536562'>going</span> <span
  m='537257'>to</span> <span m='537952'>have</span> <span m='538647'>a</span>
  <span m='539342'>notion</span> <span m='540038'>of</span> <span
  m='540733'>a</span> <span m='541428'>variable</span> <span
  m='542123'>v.</span> <span m='542818'>And</span> <span
  m='543513'>that's</span> <span m='544209'>something</span> <span
  m='544414'>that</span> <span m='544620'>can</span> <span
  m='544826'>have</span> <span m='545031'>an</span> <span
  m='545237'>assignment.</span> </p><p><span m='564029'>There's</span> <span
  m='564315'>nothing</span> <span m='564602'>complicated</span> <span
  m='564889'>about</span> <span m='565176'>that.</span> </p><p><span
  m='565463'>And</span> <span m='565885'>a</span> <span m='566308'>value.</span>
  </p><p><span m='570902'>A</span> <span m='571435'>value</span> <span
  m='571969'>x</span> <span m='572503'>is</span> <span
  m='573037'>something</span> <span m='573571'>that</span> <span
  m='574105'>can</span> <span m='574639'>be</span> <span m='575173'>in</span>
  <span m='575707'>assignment.</span> </p><p><span m='579544'>It's</span> <span
  m='579697'>a</span> <span m='579851'>little</span> <span m='580004'>bit</span>
  <span m='580158'>circular,</span> <span m='580311'>but</span> <span
  m='580465'>we're</span> <span m='580618'>all</span> <span m='580772'>in</span>
  <span m='580925'>computer</span> <span m='581079'>science</span> <span
  m='581427'>so</span> <span m='581775'>you</span> <span m='582123'>know</span>
  <span m='582471'>what</span> <span m='582819'>I</span> <span
  m='583167'>mean.</span> </p><p><span m='583515'>So</span> <span
  m='583921'>the</span> <span m='584327'>next</span> <span
  m='584734'>thing</span> <span m='585140'>is</span> <span m='585547'>a</span>
  <span m='585953'>little</span> <span m='586360'>slightly</span> <span
  m='586766'>less</span> <span m='587173'>obvious,</span> <span
  m='587579'>and</span> <span m='587986'>that's</span> <span
  m='588853'>the</span> <span m='589720'>notion</span> <span
  m='590588'>of</span> <span m='591455'>a</span> <span m='592323'>domain,</span>
  <span m='593190'>d.</span> </p><p><span m='594058'>And</span> <span
  m='594432'>that's</span> <span m='594806'>going</span> <span
  m='595181'>to</span> <span m='595555'>be</span> <span m='595930'>a</span>
  <span m='596304'>bag</span> <span m='596679'>of</span> <span
  m='597053'>values.</span> </p><p><span m='601366'>OK.</span> </p><p><span
  m='601699'>So</span> <span m='602107'>one</span> <span m='602516'>more</span>
  <span m='602925'>thing.</span> </p><p><span m='603334'>A</span> <span
  m='603968'>constraint.</span> </p><p><span m='610008'>That's</span> <span
  m='611042'>a</span> <span m='612076'>constraint</span> <span
  m='613111'>c,</span> <span m='614145'>is</span> <span m='615179'>a</span>
  <span m='616214'>limit</span> <span m='617248'>on--</span> <span
  m='618283'>in</span> <span m='618543'>our</span> <span
  m='618803'>examples</span> <span m='619063'>it's</span> <span
  m='619323'>mostly</span> <span m='619584'>going</span> <span
  m='619844'>to</span> <span m='620104'>be</span> <span m='620364'>pairs</span>
  <span m='620624'>of</span> <span m='620885'>variables,</span> <span
  m='621332'>pairs</span> <span m='621779'>of</span> <span
  m='622226'>variable</span> <span m='622673'>values.</span> </p><p><span
  m='623121'>But</span> <span m='623379'>in</span> <span
  m='623638'>general,</span> <span m='623896'>it</span> <span
  m='624155'>could</span> <span m='624413'>be</span> <span
  m='624672'>variable</span> <span m='624930'>values.</span> </p><p><span
  m='633765'>So</span> <span m='633996'>if</span> <span m='634227'>we</span>
  <span m='634459'>go</span> <span m='634690'>back</span> <span
  m='634921'>here</span> <span m='635153'>to</span> <span
  m='635384'>Texas</span> <span m='635615'>we</span> <span
  m='635847'>could</span> <span m='636078'>say,</span> <span
  m='636309'>OK,</span> <span m='636541'>how</span> <span m='636772'>does</span>
  <span m='637003'>our</span> <span m='637235'>vocabulary</span> <span
  m='637757'>drape</span> <span m='638280'>itself</span> <span
  m='638803'>over</span> <span m='639325'>that</span> <span
  m='639848'>configuration?</span> </p><p><span m='640371'>And</span> <span
  m='640847'>the</span> <span m='641323'>answer</span> <span
  m='641799'>is,</span> <span m='642276'>the</span> <span
  m='642752'>states</span> <span m='643228'>have</span> <span
  m='643704'>the</span> <span m='644181'>role</span> <span m='644657'>of</span>
  <span m='645133'>variables,</span> <span m='645610'>the</span> <span
  m='646363'>colors</span> <span m='647116'>have</span> <span
  m='647869'>the</span> <span m='648622'>role</span> <span m='649375'>of</span>
  <span m='650128'>values.</span> </p><p><span m='650882'>And</span> <span
  m='651269'>the</span> <span m='651657'>domains</span> <span
  m='652045'>are</span> <span m='652433'>the</span> <span
  m='652821'>remaining</span> <span m='653209'>color</span> <span
  m='653597'>possibilities</span> <span m='653985'>that</span> <span
  m='654289'>we</span> <span m='654593'>can</span> <span m='654897'>still</span>
  <span m='655201'>use</span> <span m='655505'>on</span> <span
  m='655809'>a</span> <span m='656113'>particular</span> <span
  m='656417'>state.</span> </p><p><span m='656721'>And</span> <span
  m='656947'>the</span> <span m='657174'>constraint,</span> <span
  m='657401'>in</span> <span m='657628'>this</span> <span
  m='657855'>case,</span> <span m='658082'>is</span> <span m='658309'>the</span>
  <span m='658536'>simple</span> <span m='658763'>map</span> <span
  m='658990'>coloring</span> <span m='659431'>constraint</span> <span
  m='659872'>that</span> <span m='660313'>no</span> <span
  m='660754'>states</span> <span m='661195'>that</span> <span
  m='661636'>share</span> <span m='662077'>a</span> <span
  m='662518'>boundary</span> <span m='662960'>can</span> <span
  m='663427'>have</span> <span m='663894'>the</span> <span
  m='664361'>same</span> <span m='664828'>color.</span> </p><p><span
  m='665296'>So</span> <span m='665711'>states</span> <span
  m='666126'>are</span> <span m='666541'>variables,</span> <span
  m='666956'>colors</span> <span m='667372'>are</span> <span
  m='667787'>values,</span> <span m='668202'>domains</span> <span
  m='668617'>are</span> <span m='669033'>bags</span> <span m='669613'>of</span>
  <span m='670194'>colors,</span> <span m='670774'>and</span> <span
  m='671355'>constraints--</span> <span m='671936'>there's</span> <span
  m='672458'>only</span> <span m='672981'>one--</span> <span
  m='673504'>adjacent</span> <span m='673933'>states</span> <span
  m='674362'>can't</span> <span m='674791'>have</span> <span
  m='675220'>the</span> <span m='675649'>same</span> <span
  m='676078'>color.</span> </p><p><span m='676507'>So</span> <span
  m='676899'>that's</span> <span m='677291'>how</span> <span
  m='677683'>it</span> <span m='678075'>fits</span> <span m='678467'>with</span>
  <span m='678859'>this</span> <span m='679251'>vocabulary.</span> </p><p><span
  m='679644'>So</span> <span m='679940'>now,</span> <span m='680236'>what</span>
  <span m='680532'>did</span> <span m='680828'>I</span> <span
  m='681124'>actually</span> <span m='681420'>do</span> <span
  m='681716'>here?</span> </p><p><span m='682013'>Well</span> <span
  m='682274'>what</span> <span m='682535'>I</span> <span
  m='682797'>actually</span> <span m='683058'>did</span> <span
  m='683319'>here,</span> <span m='683581'>I'm</span> <span
  m='683842'>going</span> <span m='684103'>to</span> <span m='684365'>now</span>
  <span m='684626'>formalize</span> <span m='684887'>a</span> <span
  m='685149'>little</span> <span m='685720'>by</span> <span
  m='686291'>writing</span> <span m='686863'>it</span> <span
  m='687434'>down</span> <span m='688005'>in</span> <span
  m='688577'>pseudo</span> <span m='689148'>code.</span> </p><p><span
  m='689720'>So</span> <span m='689977'>here</span> <span m='690234'>we</span>
  <span m='690492'>are,</span> <span m='690749'>we're</span> <span
  m='691007'>going</span> <span m='691264'>to</span> <span
  m='691522'>have</span> <span m='691779'>a</span> <span m='692036'>look</span>
  <span m='692294'>at</span> <span m='692551'>what</span> <span
  m='692809'>we</span> <span m='693066'>did</span> <span m='693324'>here</span>
  <span m='693632'>with</span> <span m='693941'>our</span> <span
  m='694249'>intuition,</span> <span m='694558'>and</span> <span
  m='694867'>we're</span> <span m='695175'>going</span> <span
  m='695484'>to</span> <span m='695793'>reduce</span> <span m='696213'>it</span>
  <span m='696633'>to</span> <span m='697054'>a</span> <span
  m='697474'>procedure.</span> </p><p><span m='697895'>And</span> <span
  m='698203'>here's</span> <span m='698512'>the</span> <span
  m='698821'>procedure.</span> </p><p><span m='702900'>Remember,</span> <span
  m='703137'>we're</span> <span m='703374'>doing</span> <span
  m='703612'>depth</span> <span m='703849'>first</span> <span
  m='704086'>search</span> <span m='704324'>on</span> <span
  m='704561'>this</span> <span m='704798'>stuff.</span> </p><p><span
  m='705036'>I</span> <span m='705336'>did</span> <span m='705636'>a</span>
  <span m='705937'>depth</span> <span m='706237'>first</span> <span
  m='706537'>search.</span> </p><p><span m='706838'>We're</span> <span
  m='707344'>going</span> <span m='707851'>to</span> <span m='708357'>do</span>
  <span m='708864'>a</span> <span m='709370'>depth</span> <span
  m='709877'>first</span> <span m='710383'>search,</span> <span
  m='710890'>and</span> <span m='711396'>for</span> <span m='711903'>each</span>
  <span m='712410'>depth</span> <span m='713252'>first</span> <span
  m='714095'>search</span> <span m='714937'>assignment--</span> <span
  m='721385'>OK,</span> <span m='721788'>so</span> <span m='722191'>here</span>
  <span m='722595'>I</span> <span m='722998'>am,</span> <span
  m='723402'>I'm</span> <span m='723805'>labeling</span> <span
  m='724209'>Arizona,</span> <span m='724612'>and</span> <span
  m='725016'>then</span> <span m='725419'>Oklahoma,</span> <span
  m='725823'>and</span> <span m='726256'>then</span> <span
  m='726690'>Arkansas,</span> <span m='727124'>and</span> <span
  m='727558'>then</span> <span m='727992'>Louisiana.</span> </p><p><span
  m='728426'>When</span> <span m='728731'>I</span> <span m='729036'>give</span>
  <span m='729341'>each</span> <span m='729646'>one</span> <span
  m='729951'>of</span> <span m='730256'>those</span> <span m='730561'>a</span>
  <span m='730866'>label,</span> <span m='731171'>a</span> <span
  m='731476'>color,</span> <span m='731781'>I'm</span> <span
  m='732086'>going</span> <span m='732391'>to</span> <span m='732697'>do</span>
  <span m='733264'>this</span> <span m='733831'>procedure.</span> </p><p><span
  m='734398'>Every</span> <span m='734556'>time</span> <span m='734715'>I</span>
  <span m='734873'>make</span> <span m='735032'>one</span> <span
  m='735190'>of</span> <span m='735349'>those</span> <span
  m='735507'>assignments.</span> </p><p><span m='735666'>The</span> <span
  m='736118'>last</span> <span m='736571'>one</span> <span
  m='737024'>that</span> <span m='737477'>caused</span> <span
  m='737930'>trouble</span> <span m='738383'>was</span> <span
  m='738836'>coloring</span> <span m='739358'>Louisiana</span> <span
  m='739881'>yellow.</span> </p><p><span m='740404'>Each</span> <span
  m='740658'>time</span> <span m='740912'>I</span> <span m='741166'>put</span>
  <span m='741420'>one</span> <span m='741674'>of</span> <span
  m='741928'>those</span> <span m='742183'>colors</span> <span
  m='742437'>down,</span> <span m='742691'>each</span> <span
  m='742945'>time</span> <span m='743199'>I</span> <span m='743453'>make</span>
  <span m='743708'>an</span> <span m='743904'>assignment,</span> <span
  m='744100'>I'm</span> <span m='744296'>going</span> <span m='744492'>to</span>
  <span m='744688'>do</span> <span m='744884'>this</span> <span
  m='745080'>procedure.</span> </p><p><span m='745276'>So</span> <span
  m='746637'>for</span> <span m='747998'>each</span> <span
  m='749359'>depth</span> <span m='750721'>first</span> <span
  m='752082'>search</span> <span m='753443'>assignment,</span> <span
  m='754805'>for</span> <span m='756166'>each</span> <span
  m='757527'>variable</span> <span m='758889'>v,</span> <span
  m='759589'>considered.</span> </p><p><span m='765896'>Now</span> <span
  m='766192'>you</span> <span m='766489'>don't</span> <span
  m='766786'>know</span> <span m='767082'>what</span> <span m='767379'>I</span>
  <span m='767676'>mean</span> <span m='767972'>by</span> <span
  m='768269'>considered.</span> </p><p><span m='768566'>But</span> <span
  m='768990'>when</span> <span m='769414'>I</span> <span m='769838'>put</span>
  <span m='770262'>a</span> <span m='770687'>label,</span> <span
  m='771111'>when</span> <span m='771535'>I</span> <span m='771959'>put</span>
  <span m='772383'>up</span> <span m='772808'>a</span> <span
  m='773232'>value,</span> <span m='773656'>show</span> <span
  m='774080'>something</span> <span m='774505'>as</span> <span
  m='775064'>a</span> <span m='775624'>color</span> <span m='776184'>for</span>
  <span m='776744'>Louisiana,</span> <span m='777303'>I</span> <span
  m='777863'>thought</span> <span m='778423'>about</span> <span
  m='778983'>Texas.</span> </p><p><span m='779543'>So</span> <span
  m='779843'>I</span> <span m='780143'>was</span> <span
  m='780443'>considering</span> <span m='780744'>the</span> <span
  m='781044'>variable,</span> <span m='781344'>Texas,</span> <span
  m='781645'>when</span> <span m='781945'>I</span> <span m='782245'>made</span>
  <span m='782546'>the</span> <span m='783121'>assignment</span> <span
  m='783697'>for</span> <span m='784273'>Louisiana.</span> </p><p><span
  m='784849'>Now</span> <span m='785008'>I'm</span> <span
  m='785168'>going</span> <span m='785327'>to</span> <span m='785487'>be</span>
  <span m='785647'>a</span> <span m='785806'>little</span> <span
  m='785966'>bit</span> <span m='786126'>vague</span> <span
  m='786285'>about</span> <span m='786445'>what</span> <span m='786605'>I</span>
  <span m='786764'>mean</span> <span m='786924'>by</span> <span
  m='787084'>considered,</span> <span m='787362'>right</span> <span
  m='787640'>now.</span> </p><p><span m='787918'>Because</span> <span
  m='788098'>there</span> <span m='788278'>are</span> <span
  m='788458'>lots</span> <span m='788638'>of</span> <span
  m='788819'>choices</span> <span m='788999'>about</span> <span
  m='789179'>how</span> <span m='789359'>much</span> <span
  m='789539'>stuff</span> <span m='789720'>you</span> <span
  m='790298'>actually</span> <span m='790876'>consider.</span> </p><p><span
  m='791455'>So</span> <span m='791633'>let</span> <span m='791811'>me</span>
  <span m='791989'>just</span> <span m='792167'>say</span> <span
  m='792345'>consider,</span> <span m='792523'>and</span> <span
  m='792701'>then</span> <span m='792879'>we'll</span> <span
  m='793057'>open</span> <span m='793235'>that</span> <span m='793413'>up</span>
  <span m='793591'>and</span> <span m='793966'>talk</span> <span
  m='794341'>about</span> <span m='794717'>the</span> <span
  m='795092'>options</span> <span m='795467'>in</span> <span m='795843'>a</span>
  <span m='796218'>moment,</span> <span m='796593'>so</span> <span
  m='796969'>for</span> <span m='797344'>each</span> <span
  m='797719'>variable</span> <span m='798095'>v</span> <span
  m='799641'>considered</span> <span m='801187'>for--</span> <span
  m='802733'>let's</span> <span m='803233'>call</span> <span
  m='803734'>that</span> <span m='804234'>variable</span> <span
  m='804735'>v</span> <span m='805235'>sub</span> <span m='805736'>i--</span>
  <span m='806237'>for</span> <span m='806953'>each</span> <span
  m='807669'>x</span> <span m='808385'>sub</span> <span m='809101'>i,</span>
  <span m='809817'>for</span> <span m='810533'>each</span> <span
  m='811249'>value</span> <span m='811965'>in</span> <span m='812681'>the</span>
  <span m='813397'>domain</span> <span m='814113'>of</span> <span
  m='814829'>that</span> <span m='815546'>variable,</span> <span
  m='816146'>consider</span> <span m='816747'>each</span> <span
  m='817347'>of</span> <span m='817948'>the</span> <span
  m='818548'>things</span> <span m='819149'>that</span> <span
  m='819749'>still</span> <span m='820350'>surviving.</span> </p><p><span
  m='820951'>For</span> <span m='822291'>each</span> <span m='823632'>of</span>
  <span m='824973'>those,</span> <span m='826313'>for</span> <span
  m='827654'>each</span> <span m='828995'>constraint</span> <span
  m='830336'>c,</span> <span m='831676'>that's</span> <span
  m='833017'>between</span> <span m='834358'>x</span> <span
  m='835699'>sub</span> <span m='836504'>i,</span> <span m='837309'>and</span>
  <span m='838114'>some</span> <span m='838919'>x</span> <span
  m='839724'>sub</span> <span m='840529'>j,</span> <span m='841334'>where</span>
  <span m='842139'>x</span> <span m='842944'>sub</span> <span
  m='843749'>j</span> <span m='844554'>is</span> <span m='845359'>an</span>
  <span m='846164'>element</span> <span m='846969'>of</span> <span
  m='847774'>the</span> <span m='848579'>domain</span> <span
  m='849468'>of</span> <span m='850358'>j.</span> </p><p><span
  m='851248'>Now</span> <span m='851518'>that</span> <span
  m='851788'>sounds</span> <span m='852058'>awfully</span> <span
  m='852328'>fancy,</span> <span m='852598'>but</span> <span
  m='852868'>this</span> <span m='853138'>just</span> <span
  m='853408'>says,</span> <span m='853678'>in</span> <span m='853948'>the</span>
  <span m='854218'>case</span> <span m='854575'>of</span> <span
  m='854933'>Texas</span> <span m='855291'>up</span> <span
  m='855649'>there,</span> <span m='856007'>whenever</span> <span
  m='856365'>I</span> <span m='856723'>consider</span> <span
  m='857081'>one</span> <span m='857439'>of</span> <span m='857797'>the</span>
  <span m='858155'>values</span> <span m='858537'>that's</span> <span
  m='858919'>still</span> <span m='859301'>remaining</span> <span
  m='859683'>as</span> <span m='860065'>a</span> <span m='860448'>choice</span>
  <span m='860830'>for</span> <span m='861212'>Texas,</span> <span
  m='861594'>I</span> <span m='861976'>want</span> <span m='862359'>to</span>
  <span m='862676'>consider</span> <span m='862993'>all</span> <span
  m='863310'>of</span> <span m='863627'>the</span> <span
  m='863944'>constraints</span> <span m='864261'>between</span> <span
  m='864578'>that</span> <span m='864895'>variable</span> <span
  m='865862'>and</span> <span m='866830'>the</span> <span
  m='867797'>adjacent</span> <span m='868765'>states.</span> </p><p><span
  m='869733'>And</span> <span m='870123'>I</span> <span m='870513'>want</span>
  <span m='870903'>to</span> <span m='871293'>be</span> <span
  m='871683'>sure</span> <span m='872073'>that</span> <span
  m='872464'>anything</span> <span m='872854'>I</span> <span
  m='873244'>leave</span> <span m='873634'>in</span> <span m='874024'>the</span>
  <span m='874414'>domain</span> <span m='874805'>is</span> <span
  m='875178'>OK</span> <span m='875552'>for</span> <span m='875926'>some</span>
  <span m='876299'>selection</span> <span m='876673'>in</span> <span
  m='877047'>the</span> <span m='877420'>other</span> <span
  m='877794'>states,</span> <span m='878168'>some</span> <span
  m='878542'>remaining</span> <span m='878975'>choices</span> <span
  m='879409'>in</span> <span m='879843'>the</span> <span m='880277'>other</span>
  <span m='880711'>states.</span> </p><p><span m='881145'>So</span> <span
  m='881411'>that's</span> <span m='881678'>why</span> <span
  m='881945'>we're</span> <span m='882212'>getting</span> <span
  m='882479'>pretty</span> <span m='882746'>nested</span> <span
  m='883013'>here.</span> </p><p><span m='883280'>But</span> <span
  m='883858'>we're</span> <span m='884436'>doing</span> <span
  m='885015'>depth</span> <span m='885593'>first</span> <span
  m='886171'>search.</span> </p><p><span m='886750'>We</span> <span
  m='887150'>are</span> <span m='887550'>considering</span> <span
  m='887951'>the</span> <span m='888351'>variables</span> <span
  m='888751'>in</span> <span m='889152'>a</span> <span m='889552'>certain</span>
  <span m='889953'>collection</span> <span m='891577'>of</span> <span
  m='893201'>variables.</span> </p><p><span m='894825'>For</span> <span
  m='895075'>each</span> <span m='895325'>one</span> <span m='895575'>of</span>
  <span m='895825'>those</span> <span m='896076'>where</span> <span
  m='896326'>considering</span> <span m='896576'>all</span> <span
  m='896826'>the</span> <span m='897076'>values</span> <span
  m='897327'>that</span> <span m='897683'>still</span> <span
  m='898039'>remain</span> <span m='898395'>in</span> <span
  m='898751'>the</span> <span m='899107'>domains</span> <span
  m='899463'>of</span> <span m='899819'>those</span> <span
  m='900175'>variables.</span> </p><p><span m='900531'>And</span> <span
  m='900767'>then</span> <span m='901004'>for</span> <span
  m='901240'>each</span> <span m='901477'>of</span> <span
  m='901713'>those</span> <span m='901950'>values,</span> <span
  m='902186'>we're</span> <span m='902423'>checking</span> <span
  m='902659'>to</span> <span m='902896'>see</span> <span m='903133'>if</span>
  <span m='903516'>it</span> <span m='903900'>satisfies</span> <span
  m='904284'>this</span> <span m='904668'>some</span> <span
  m='905051'>constraint,</span> <span m='905435'>satisfies</span> <span
  m='905819'>the</span> <span m='906203'>constraint</span> <span
  m='906748'>that</span> <span m='907293'>are</span> <span
  m='907838'>placed</span> <span m='908383'>upon</span> <span
  m='908928'>it.</span> </p><p><span m='909473'>So</span> <span
  m='910003'>for</span> <span m='910534'>each</span> <span m='911064'>of</span>
  <span m='911595'>these</span> <span m='912125'>constraints</span> <span
  m='912656'>if</span> <span m='913186'>there</span> <span
  m='913717'>does</span> <span m='914247'>not</span> <span
  m='914778'>exist</span> <span m='915419'>an</span> <span m='916061'>x</span>
  <span m='916703'>sub</span> <span m='917344'>j,</span> <span
  m='917986'>such</span> <span m='918628'>that,</span> <span
  m='919269'>the</span> <span m='919911'>constraint</span> <span
  m='920553'>between</span> <span m='921194'>x</span> <span
  m='921836'>sub</span> <span m='922478'>i</span> <span m='923120'>and</span>
  <span m='923965'>x</span> <span m='924810'>sub</span> <span
  m='925655'>j</span> <span m='926501'>is</span> <span
  m='927346'>satisfied,</span> <span m='928191'>well</span> <span
  m='929036'>if</span> <span m='929882'>in</span> <span m='930727'>that</span>
  <span m='931572'>adjacent</span> <span m='932417'>place</span> <span
  m='933263'>there's</span> <span m='933674'>nothing</span> <span
  m='934086'>that</span> <span m='934497'>is</span> <span
  m='934909'>consistent</span> <span m='935320'>with</span> <span
  m='935732'>a</span> <span m='936143'>value,</span> <span
  m='936555'>then</span> <span m='936967'>we've</span> <span
  m='937338'>got</span> <span m='937710'>to</span> <span m='938082'>get</span>
  <span m='938454'>rid</span> <span m='938826'>of</span> <span
  m='939198'>it.</span> </p><p><span m='939570'>If</span> <span
  m='939892'>that's</span> <span m='940214'>true.</span> </p><p><span
  m='940537'>If</span> <span m='941034'>there</span> <span
  m='941531'>does</span> <span m='942029'>not</span> <span
  m='942526'>exist</span> <span m='943024'>some</span> <span
  m='943521'>value</span> <span m='944019'>in</span> <span m='944516'>an</span>
  <span m='945014'>adjacent</span> <span m='945511'>variable</span> <span
  m='946009'>such</span> <span m='946330'>that</span> <span
  m='946651'>that</span> <span m='946972'>constraint</span> <span
  m='947294'>is</span> <span m='947615'>satisfied,</span> <span
  m='947936'>we're</span> <span m='948257'>hosed.</span> </p><p><span
  m='948579'>We've</span> <span m='948879'>got</span> <span m='949179'>to</span>
  <span m='949479'>get</span> <span m='949780'>rid</span> <span
  m='950080'>of</span> <span m='950380'>that</span> <span
  m='950680'>value.</span> </p><p><span m='950981'>So</span> <span
  m='951862'>we're</span> <span m='952743'>going</span> <span
  m='953625'>to</span> <span m='954506'>remove</span> <span m='955388'>x</span>
  <span m='956269'>sub</span> <span m='957150'>i</span> <span
  m='958032'>from</span> <span m='958913'>d</span> <span m='959795'>sub</span>
  <span m='960676'>i.</span> </p><p><span m='965162'>OK.</span> </p><p><span
  m='965429'>Now,</span> <span m='966040'>that's</span> <span
  m='966652'>fine.</span> </p><p><span m='967264'>That's</span> <span
  m='967593'>sort</span> <span m='967923'>of</span> <span m='968252'>what</span>
  <span m='968582'>I</span> <span m='968911'>did</span> <span
  m='969241'>with</span> <span m='969570'>Texas.</span> </p><p><span
  m='969900'>As</span> <span m='970225'>soon</span> <span m='970550'>as</span>
  <span m='970876'>I</span> <span m='971201'>plopped</span> <span
  m='971526'>down</span> <span m='971852'>a</span> <span m='972177'>value</span>
  <span m='972502'>for</span> <span m='972828'>Louisiana</span> <span
  m='973153'>I</span> <span m='973478'>said,</span> <span m='973804'>well</span>
  <span m='974075'>what</span> <span m='974346'>are</span> <span
  m='974617'>the</span> <span m='974888'>possible</span> <span
  m='975159'>values</span> <span m='975430'>in</span> <span
  m='975701'>Texas?</span> </p><p><span m='975973'>Red,</span> <span
  m='976340'>green,</span> <span m='976707'>blue</span> <span
  m='977074'>and</span> <span m='977441'>yellow.</span> </p><p><span
  m='977808'>Let's</span> <span m='978475'>consider</span> <span
  m='979142'>red.</span> </p><p><span m='979810'>Let's</span> <span
  m='980076'>consider</span> <span m='980343'>the</span> <span
  m='980610'>constraints</span> <span m='980877'>between</span> <span
  m='981144'>Texas</span> <span m='981411'>and</span> <span
  m='981678'>all</span> <span m='982234'>adjacent</span> <span
  m='982790'>states.</span> </p><p><span m='983347'>One</span> <span
  m='983513'>of</span> <span m='983680'>those</span> <span
  m='983847'>constraints</span> <span m='984014'>says</span> <span
  m='984180'>it</span> <span m='984347'>can't</span> <span m='984514'>be</span>
  <span m='984681'>the</span> <span m='984848'>same</span> <span
  m='985348'>color</span> <span m='985849'>as</span> <span
  m='986349'>Arizona.</span> </p><p><span m='986850'>The</span> <span
  m='987076'>only</span> <span m='987302'>color</span> <span
  m='987528'>I've</span> <span m='987754'>got</span> <span
  m='987980'>available</span> <span m='988206'>for</span> <span
  m='988432'>Arizona,</span> <span m='988658'>since</span> <span
  m='988885'>I've</span> <span m='989199'>already</span> <span
  m='989514'>made</span> <span m='989829'>the</span> <span
  m='990143'>assignment</span> <span m='990458'>is</span> <span
  m='990773'>red.</span> </p><p><span m='991088'>Red</span> <span
  m='991277'>is</span> <span m='991466'>not</span> <span
  m='991655'>consistent</span> <span m='991844'>with</span> <span
  m='992033'>red,</span> <span m='992222'>so</span> <span m='992411'>I've</span>
  <span m='992600'>got</span> <span m='992789'>to</span> <span
  m='993282'>get</span> <span m='993776'>rid</span> <span m='994270'>of</span>
  <span m='994764'>it.</span> </p><p><span m='995258'>So</span> <span
  m='995758'>it</span> <span m='996259'>looks</span> <span
  m='996759'>complicated,</span> <span m='997260'>but</span> <span
  m='997760'>it's</span> <span m='998261'>just</span> <span
  m='998761'>intuition.</span> </p><p><span m='999262'>So</span> <span
  m='999487'>what</span> <span m='999712'>do</span> <span m='999937'>we</span>
  <span m='1000163'>do</span> <span m='1000388'>if</span> <span
  m='1000613'>we</span> <span m='1000838'>get</span> <span m='1001064'>to</span>
  <span m='1001289'>a</span> <span m='1001514'>situation</span> <span
  m='1001739'>where</span> <span m='1001965'>the</span> <span
  m='1002448'>domain</span> <span m='1002932'>is</span> <span
  m='1003416'>empty?</span> </p><p><span m='1003900'>That</span> <span
  m='1004126'>means</span> <span m='1004353'>whenever</span> <span
  m='1004580'>we</span> <span m='1004807'>get</span> <span
  m='1005034'>around</span> <span m='1005261'>to</span> <span
  m='1005488'>making</span> <span m='1005715'>assignment</span> <span
  m='1005942'>to</span> <span m='1006169'>it,</span> <span
  m='1006597'>there</span> <span m='1007025'>won't</span> <span
  m='1007454'>be</span> <span m='1007882'>anything</span> <span
  m='1008310'>left.</span> </p><p><span m='1008739'>So</span> <span
  m='1010082'>if</span> <span m='1011426'>that</span> <span
  m='1012770'>ever</span> <span m='1014113'>happens,</span> <span
  m='1015457'>if</span> <span m='1016801'>the</span> <span
  m='1018145'>domain</span> <span m='1019488'>ever</span> <span
  m='1020832'>becomes</span> <span m='1022176'>empty,</span> <span
  m='1023520'>then</span> <span m='1023806'>what</span> <span
  m='1024093'>do</span> <span m='1024380'>we</span> <span m='1024667'>do?</span>
  </p><p><span m='1024954'>We've</span> <span m='1025201'>got</span> <span
  m='1025448'>to</span> <span m='1025695'>back</span> <span
  m='1025942'>up.</span> </p><p><span m='1033195'>So</span> <span
  m='1033415'>the</span> <span m='1033635'>intuition</span> <span
  m='1033856'>is</span> <span m='1034076'>clear.</span> </p><p><span
  m='1034297'>This</span> <span m='1034539'>is</span> <span
  m='1034781'>the</span> <span m='1035023'>algorithm.</span> </p><p><span
  m='1035265'>The</span> <span m='1035583'>algorithm</span> <span
  m='1035902'>when</span> <span m='1036221'>you</span> <span
  m='1036540'>work</span> <span m='1036859'>through</span> <span
  m='1037178'>it,</span> <span m='1037497'>think</span> <span
  m='1037816'>about</span> <span m='1038135'>whether</span> <span
  m='1038335'>it</span> <span m='1038535'>makes</span> <span
  m='1038735'>sense</span> <span m='1038935'>and</span> <span
  m='1039135'>what</span> <span m='1039335'>not.</span> </p><p><span
  m='1039536'>How</span> <span m='1039742'>it</span> <span
  m='1039949'>fits</span> <span m='1040155'>with</span> <span
  m='1040362'>Texas.</span> </p><p><span m='1040569'>Yeah,</span> <span
  m='1040769'>it</span> <span m='1040970'>sure</span> <span
  m='1041170'>does.</span> </p><p><span m='1041371'>All</span> <span
  m='1041700'>we're</span> <span m='1042030'>doing</span> <span
  m='1042360'>is</span> <span m='1042690'>we're</span> <span
  m='1043020'>making</span> <span m='1043350'>these</span> <span
  m='1043680'>death</span> <span m='1044010'>first</span> <span
  m='1044340'>assignments.</span> </p><p><span m='1044907'>And</span> <span
  m='1045192'>in</span> <span m='1045478'>the</span> <span
  m='1045763'>neighborhood</span> <span m='1046049'>of</span> <span
  m='1046334'>those</span> <span m='1046620'>depth</span> <span
  m='1046905'>first</span> <span m='1047191'>assignments</span> <span
  m='1047477'>we're</span> <span m='1047813'>looking</span> <span
  m='1048150'>around</span> <span m='1048487'>to</span> <span
  m='1048823'>see</span> <span m='1049160'>if</span> <span
  m='1049497'>the</span> <span m='1049834'>values</span> <span
  m='1050170'>that</span> <span m='1050507'>are</span> <span
  m='1050844'>possible</span> <span m='1051181'>include</span> <span
  m='1051664'>something.</span> </p><p><span m='1052148'>And</span> <span
  m='1052442'>if</span> <span m='1052736'>they</span> <span
  m='1053030'>don't</span> <span m='1053325'>include</span> <span
  m='1053619'>anything,</span> <span m='1053913'>we</span> <span
  m='1054207'>know</span> <span m='1054502'>we</span> <span
  m='1054796'>made</span> <span m='1055090'>and</span> <span
  m='1055385'>irrevocable</span> <span m='1055910'>blunder,</span> <span
  m='1056436'>and</span> <span m='1056961'>we</span> <span
  m='1057487'>have</span> <span m='1058012'>to</span> <span
  m='1058538'>back</span> <span m='1059063'>up.</span> </p><p><span
  m='1059589'>So</span> <span m='1060108'>that's</span> <span
  m='1060628'>the</span> <span m='1061147'>essence</span> <span
  m='1061667'>of</span> <span m='1062186'>the</span> <span
  m='1062706'>idea.</span> </p><p><span m='1063226'>Now,</span> <span
  m='1063726'>how</span> <span m='1064227'>well</span> <span
  m='1064727'>does</span> <span m='1065228'>it</span> <span
  m='1065728'>work?</span> </p><p><span m='1066229'>Well</span> <span
  m='1066914'>a</span> <span m='1067600'>little</span> <span
  m='1068285'>bit</span> <span m='1068971'>depends</span> <span
  m='1069656'>on</span> <span m='1070342'>what</span> <span
  m='1071027'>we</span> <span m='1071713'>choose</span> <span
  m='1072398'>for</span> <span m='1073084'>considered.</span> </p><p><span
  m='1073770'>There</span> <span m='1073988'>are</span> <span
  m='1074207'>lots</span> <span m='1074426'>of</span> <span
  m='1074645'>choices</span> <span m='1074863'>for</span> <span
  m='1075082'>what</span> <span m='1075301'>we</span> <span
  m='1075520'>consider.</span> </p><p><span m='1078708'>So</span> <span
  m='1079056'>let</span> <span m='1079405'>me</span> <span
  m='1079754'>enumerate</span> <span m='1080103'>some</span> <span
  m='1080452'>of</span> <span m='1080800'>those</span> <span
  m='1081149'>choices</span> <span m='1081498'>and</span> <span
  m='1081847'>then</span> <span m='1082196'>we'll</span> <span
  m='1082545'>have</span> <span m='1082716'>a</span> <span
  m='1082887'>look</span> <span m='1083058'>and</span> <span
  m='1083229'>see</span> <span m='1083400'>what</span> <span
  m='1083571'>they</span> <span m='1083742'>do.</span> </p><p><span
  m='1098128'>Oh</span> <span m='1098546'>I</span> <span
  m='1098965'>guess</span> <span m='1099384'>one</span> <span
  m='1099803'>possibility</span> <span m='1100222'>is</span> <span
  m='1100641'>to</span> <span m='1101060'>consider</span> <span
  m='1101479'>nothing.</span> </p><p><span m='1112275'>Let's</span> <span
  m='1112583'>try</span> <span m='1112892'>it</span> <span
  m='1113201'>out.</span> </p><p><span m='1119115'>So</span> <span
  m='1119439'>our</span> <span m='1119764'>type</span> <span
  m='1120088'>of</span> <span m='1120413'>search</span> <span
  m='1120737'>is</span> <span m='1121062'>going</span> <span
  m='1121386'>to</span> <span m='1121711'>be</span> <span m='1122035'>no</span>
  <span m='1122360'>checks.</span> </p><p><span m='1122685'>What</span> <span
  m='1122860'>do</span> <span m='1123035'>you</span> <span
  m='1123210'>think</span> <span m='1123386'>is</span> <span
  m='1123561'>going</span> <span m='1123736'>to</span> <span
  m='1123911'>happen?</span> </p><p><span m='1126790'>We're</span> <span
  m='1127340'>not</span> <span m='1127891'>even</span> <span
  m='1128441'>checking</span> <span m='1128992'>the</span> <span
  m='1129542'>assignment.</span> </p><p><span m='1130093'>That's</span> <span
  m='1130582'>pretty</span> <span m='1131071'>fast.</span> </p><p><span
  m='1131561'>Unfortunately,</span> <span m='1131832'>since</span> <span
  m='1132103'>we</span> <span m='1132374'>haven't</span> <span
  m='1132645'>even</span> <span m='1132916'>check</span> <span
  m='1133187'>the</span> <span m='1133458'>most</span> <span
  m='1133730'>recent</span> <span m='1134023'>assignment,</span> <span
  m='1134317'>we</span> <span m='1134610'>get</span> <span
  m='1134904'>lots</span> <span m='1135198'>of</span> <span
  m='1135491'>places</span> <span m='1135785'>where</span> <span
  m='1136078'>there</span> <span m='1136372'>are</span> <span
  m='1136666'>states</span> <span m='1136916'>that</span> <span
  m='1137166'>are</span> <span m='1137416'>adjacent</span> <span
  m='1137667'>to</span> <span m='1137917'>each</span> <span
  m='1138167'>other</span> <span m='1138417'>that</span> <span
  m='1138668'>have</span> <span m='1139076'>the</span> <span
  m='1139485'>same</span> <span m='1139894'>color.</span> </p><p><span
  m='1140303'>That's</span> <span m='1140725'>no</span> <span
  m='1141148'>good.</span> </p><p><span m='1145141'>So</span> <span
  m='1145641'>another</span> <span m='1146142'>thing</span> <span
  m='1146642'>we</span> <span m='1147143'>can</span> <span m='1147643'>do</span>
  <span m='1148144'>is</span> <span m='1148644'>consider</span> <span
  m='1149145'>everything</span> <span m='1149646'>everything.</span>
  </p><p><span m='1158254'>That's</span> <span m='1158468'>no</span> <span
  m='1158682'>good,</span> <span m='1158896'>because</span> <span
  m='1159110'>that</span> <span m='1159324'>would</span> <span
  m='1159539'>say,</span> <span m='1159753'>as</span> <span
  m='1159967'>soon</span> <span m='1160181'>as</span> <span
  m='1160395'>we</span> <span m='1160609'>color</span> <span
  m='1160824'>our</span> <span m='1161188'>first</span> <span
  m='1161552'>state,</span> <span m='1161916'>we</span> <span
  m='1162281'>check</span> <span m='1162645'>to</span> <span
  m='1163009'>make</span> <span m='1163373'>sure</span> <span
  m='1163738'>that</span> <span m='1164102'>all</span> <span
  m='1164466'>47</span> <span m='1164830'>other</span> <span
  m='1165195'>states</span> <span m='1165762'>can</span> <span
  m='1166329'>be</span> <span m='1166896'>colored.</span> </p><p><span
  m='1167463'>That</span> <span m='1167843'>seems</span> <span
  m='1168223'>like</span> <span m='1168604'>it</span> <span
  m='1168984'>over</span> <span m='1169365'>doing</span> <span
  m='1169745'>it</span> <span m='1170125'>a</span> <span
  m='1170506'>little</span> <span m='1170886'>bit.</span> </p><p><span
  m='1171267'>But</span> <span m='1171575'>in</span> <span
  m='1171884'>any</span> <span m='1172193'>case,</span> <span
  m='1172501'>at</span> <span m='1172810'>least</span> <span
  m='1173119'>we</span> <span m='1173427'>want</span> <span
  m='1173736'>to</span> <span m='1174045'>check</span> <span
  m='1174353'>the</span> <span m='1174662'>assignment.</span> </p><p><span
  m='1183413'>So</span> <span m='1183777'>if</span> <span m='1184141'>we</span>
  <span m='1184505'>go</span> <span m='1184869'>back</span> <span
  m='1185233'>here</span> <span m='1185597'>and</span> <span
  m='1185961'>check</span> <span m='1186325'>the</span> <span
  m='1186689'>assignment,</span> <span m='1187053'>let's</span> <span
  m='1187417'>see</span> <span m='1187839'>what</span> <span
  m='1188262'>happens.</span> </p><p><span m='1194190'>Type</span> <span
  m='1194924'>assignments,</span> <span m='1195658'>assignments</span> <span
  m='1196392'>only.</span> </p><p><span m='1197126'>Boom.</span> </p><p><span
  m='1197827'>Aw,</span> <span m='1198153'>gees,</span> <span
  m='1198479'>that's</span> <span m='1198805'>where</span> <span
  m='1199131'>I</span> <span m='1199458'>got</span> <span m='1199784'>in</span>
  <span m='1200110'>trouble</span> <span m='1200436'>before.</span> </p><p><span
  m='1200763'>This</span> <span m='1201345'>is</span> <span
  m='1201928'>the</span> <span m='1202511'>thing</span> <span
  m='1203093'>is</span> <span m='1203676'>going</span> <span
  m='1204259'>to</span> <span m='1204841'>run</span> <span
  m='1205424'>for</span> <span m='1206007'>17</span> <span
  m='1206589'>billion</span> <span m='1207172'>years</span> <span
  m='1207755'>at</span> <span m='1208338'>nanosecond</span> <span
  m='1208771'>or</span> <span m='1209205'>something</span> <span
  m='1209638'>like</span> <span m='1210072'>that.</span> </p><p><span
  m='1210506'>It's</span> <span m='1210715'>only</span> <span
  m='1210924'>a</span> <span m='1211134'>billion</span> <span
  m='1211343'>years</span> <span m='1211552'>if</span> <span
  m='1211762'>you</span> <span m='1211971'>run</span> <span
  m='1212180'>it</span> <span m='1212390'>at</span> <span
  m='1212599'>nanosecond</span> <span m='1212809'>speed,</span> <span
  m='1213157'>so</span> <span m='1213505'>I</span> <span
  m='1213854'>guess</span> <span m='1214202'>maybe</span> <span
  m='1214551'>you</span> <span m='1214899'>could</span> <span
  m='1215248'>do</span> <span m='1215596'>that.</span> </p><p><span
  m='1215945'>Have</span> <span m='1216287'>a</span> <span
  m='1216629'>fast</span> <span m='1216971'>computer.</span> </p><p><span
  m='1217313'>But</span> <span m='1217536'>this</span> <span
  m='1217760'>isn't</span> <span m='1217983'>going</span> <span
  m='1218207'>to</span> <span m='1218431'>work</span> <span
  m='1218654'>because</span> <span m='1218878'>of</span> <span
  m='1219101'>our</span> <span m='1219325'>unfortunate</span> <span
  m='1219549'>choice</span> <span m='1220058'>of</span> <span
  m='1220568'>Texas</span> <span m='1221077'>as</span> <span
  m='1221587'>the</span> <span m='1222096'>last</span> <span
  m='1222606'>state</span> <span m='1223115'>to</span> <span
  m='1223625'>be</span> <span m='1224134'>considered,</span> <span
  m='1224644'>and</span> <span m='1225154'>the</span> <span
  m='1225496'>unfortunate</span> <span m='1225838'>coloring</span> <span
  m='1226180'>of</span> <span m='1226522'>the</span> <span
  m='1226864'>four</span> <span m='1227206'>surrounding</span> <span
  m='1227548'>states</span> <span m='1227890'>right</span> <span
  m='1228413'>up</span> <span m='1228936'>front.</span> </p><p><span
  m='1229459'>And</span> <span m='1229716'>our</span> <span
  m='1229974'>unfortunate</span> <span m='1230232'>decision</span> <span
  m='1230490'>to</span> <span m='1230748'>rotate</span> <span
  m='1231005'>the</span> <span m='1231263'>color</span> <span
  m='1231521'>so</span> <span m='1231779'>as</span> <span m='1232037'>to</span>
  <span m='1232295'>avoid</span> <span m='1233135'>overdoing</span> <span
  m='1233976'>any</span> <span m='1234817'>one</span> <span
  m='1235658'>color.</span> </p><p><span m='1236499'>So</span> <span
  m='1236724'>this</span> <span m='1236949'>doesn't</span> <span
  m='1237174'>work.</span> </p><p><span m='1237400'>We</span> <span
  m='1237694'>know</span> <span m='1237989'>we</span> <span
  m='1238284'>went</span> <span m='1238579'>to</span> <span
  m='1238873'>the</span> <span m='1239168'>trouble</span> <span
  m='1239463'>of</span> <span m='1239758'>working</span> <span
  m='1240052'>out</span> <span m='1240347'>the</span> <span
  m='1240642'>business</span> <span m='1240937'>with</span> <span
  m='1241515'>Texas</span> <span m='1242093'>by</span> <span
  m='1242672'>hand,</span> <span m='1243250'>using</span> <span
  m='1243828'>the</span> <span m='1244407'>domain</span> <span
  m='1244985'>reduction</span> <span m='1245563'>algorithm.</span> </p><p><span
  m='1246142'>Better</span> <span m='1246333'>make</span> <span
  m='1246525'>a</span> <span m='1246717'>note</span> <span
  m='1246909'>that</span> <span m='1247101'>this</span> <span
  m='1247293'>is</span> <span m='1247485'>the</span> <span
  m='1247677'>domain</span> <span m='1248099'>reduction</span> <span
  m='1248522'>algorithm.</span> </p><p><span m='1258554'>And</span> <span
  m='1258712'>what</span> <span m='1258871'>we're</span> <span
  m='1259029'>going</span> <span m='1259188'>to</span> <span
  m='1259346'>do</span> <span m='1259505'>is</span> <span
  m='1259663'>we're</span> <span m='1259822'>going</span> <span
  m='1259980'>to</span> <span m='1260139'>check</span> <span
  m='1260297'>the</span> <span m='1260456'>neighbors</span> <span
  m='1261165'>of</span> <span m='1261874'>the</span> <span
  m='1262583'>assignments.</span> </p><p><span m='1263292'>Just</span> <span
  m='1263465'>like</span> <span m='1263639'>we</span> <span
  m='1263812'>did</span> <span m='1263986'>here.</span> </p><p><span
  m='1264160'>We</span> <span m='1264375'>checked</span> <span
  m='1264590'>Texas</span> <span m='1264806'>each</span> <span
  m='1265021'>time</span> <span m='1265236'>we</span> <span
  m='1265452'>made</span> <span m='1265667'>one</span> <span
  m='1265882'>of</span> <span m='1266098'>those</span> <span
  m='1266313'>four</span> <span m='1266529'>choices,</span> <span
  m='1266899'>because</span> <span m='1267269'>it's</span> <span
  m='1267640'>a</span> <span m='1268010'>neighbor</span> <span
  m='1268381'>of</span> <span m='1268751'>all</span> <span m='1269121'>of</span>
  <span m='1269492'>the</span> <span m='1269862'>choices</span> <span
  m='1270233'>of</span> <span m='1270638'>the</span> <span
  m='1271044'>states</span> <span m='1271450'>that</span> <span
  m='1271856'>we</span> <span m='1272262'>made.</span> </p><p><span
  m='1272668'>So</span> <span m='1272909'>one</span> <span
  m='1273150'>thing</span> <span m='1273391'>to</span> <span
  m='1273632'>do</span> <span m='1273873'>is</span> <span m='1274114'>to</span>
  <span m='1274355'>check</span> <span m='1274596'>neighbors.</span>
  </p><p><span m='1280109'>This</span> <span m='1280469'>is</span> <span
  m='1280829'>one,</span> <span m='1281190'>two,</span> <span
  m='1281550'>three,</span> <span m='1281911'>now</span> <span
  m='1282271'>let's</span> <span m='1282631'>see</span> <span
  m='1282992'>what</span> <span m='1283352'>happens.</span> </p><p><span
  m='1292455'>Check</span> <span m='1293097'>neighbors</span> <span
  m='1293739'>only,</span> <span m='1294381'>go.</span> </p><p><span
  m='1313643'>Shoot,</span> <span m='1313876'>I</span> <span
  m='1314110'>don't</span> <span m='1314343'>know.</span> </p><p><span
  m='1314577'>It's</span> <span m='1315211'>OK</span> <span
  m='1315845'>with</span> <span m='1316479'>Texas,</span> <span
  m='1317113'>right?</span> </p><p><span m='1317747'>Because</span> <span
  m='1318244'>it</span> <span m='1318741'>didn't</span> <span
  m='1319238'>color</span> <span m='1319735'>the</span> <span
  m='1320232'>states</span> <span m='1320729'>around</span> <span
  m='1321226'>Texas</span> <span m='1321723'>with</span> <span
  m='1322220'>all</span> <span m='1322718'>of</span> <span
  m='1323165'>the</span> <span m='1323612'>four</span> <span
  m='1324059'>color</span> <span m='1324506'>choices.</span> </p><p><span
  m='1324954'>But</span> <span m='1325291'>it's</span> <span
  m='1325628'>still</span> <span m='1325966'>getting</span> <span
  m='1326303'>into</span> <span m='1326640'>trouble</span> <span
  m='1326978'>in</span> <span m='1327315'>other</span> <span
  m='1327652'>places.</span> </p><p><span m='1330660'>Like</span> <span
  m='1331214'>the</span> <span m='1331769'>states</span> <span
  m='1332323'>like</span> <span m='1332878'>Missouri,</span> <span
  m='1333433'>Kentucky,</span> <span m='1333987'>Virginia,</span> <span
  m='1334542'>Tennessee,</span> <span m='1335097'>states</span> <span
  m='1335530'>with</span> <span m='1335964'>lots</span> <span
  m='1336398'>of</span> <span m='1336832'>boundaries.</span> </p><p><span
  m='1339869'>So</span> <span m='1340135'>I</span> <span
  m='1340402'>don't</span> <span m='1340669'>know</span> <span
  m='1340936'>whether</span> <span m='1341203'>this</span> <span
  m='1341470'>is</span> <span m='1341737'>going</span> <span
  m='1342004'>to--</span> <span m='1342271'>oh,</span> <span
  m='1342925'>there</span> <span m='1343579'>it</span> <span
  m='1344233'>finally</span> <span m='1344887'>worked.</span> </p><p><span
  m='1345541'>It</span> <span m='1345874'>went</span> <span
  m='1346208'>through</span> <span m='1346541'>a</span> <span
  m='1346875'>lot</span> <span m='1347209'>of</span> <span
  m='1347542'>effort,</span> <span m='1347876'>though.</span> </p><p><span
  m='1348210'>For</span> <span m='1348405'>the</span> <span
  m='1348600'>sake</span> <span m='1348795'>of</span> <span
  m='1348990'>comparison,</span> <span m='1349185'>we</span> <span
  m='1349380'>might</span> <span m='1349575'>make</span> <span
  m='1349770'>a</span> <span m='1349965'>note</span> <span
  m='1350160'>that</span> <span m='1350355'>it</span> <span
  m='1350550'>ran</span> <span m='1350746'>into</span> <span
  m='1353916'>9,139</span> <span m='1357086'>dead</span> <span
  m='1360256'>ends.</span> </p><p><span m='1363426'>But</span> <span
  m='1363670'>it</span> <span m='1363915'>did</span> <span m='1364160'>do</span>
  <span m='1364404'>some</span> <span m='1364649'>good.</span> </p><p><span
  m='1364894'>It</span> <span m='1365303'>didn't</span> <span
  m='1365712'>take</span> <span m='1366122'>a</span> <span
  m='1366531'>length</span> <span m='1366941'>of</span> <span
  m='1367350'>time</span> <span m='1367760'>longer</span> <span
  m='1368169'>than</span> <span m='1368579'>the</span> <span
  m='1368988'>remaining</span> <span m='1369398'>part</span> <span
  m='1369998'>of</span> <span m='1370599'>the</span> <span
  m='1371200'>universe.</span> </p><p><span m='1371801'>But</span> <span
  m='1372095'>if</span> <span m='1372390'>it's</span> <span m='1372685'>a</span>
  <span m='1372979'>good</span> <span m='1373274'>idea</span> <span
  m='1373569'>to</span> <span m='1373863'>check</span> <span
  m='1374158'>the</span> <span m='1374453'>neighbors,</span> <span
  m='1374747'>if</span> <span m='1375042'>we</span> <span
  m='1375337'>make</span> <span m='1375718'>a</span> <span
  m='1376100'>change</span> <span m='1376482'>to</span> <span
  m='1376864'>the</span> <span m='1377246'>neighbors,</span> <span
  m='1377628'>what</span> <span m='1378010'>might</span> <span
  m='1378392'>that</span> <span m='1378774'>suggests</span> <span
  m='1379502'>that</span> <span m='1380231'>we</span> <span
  m='1380959'>do</span> <span m='1381688'>in</span> <span
  m='1382416'>addition?</span> </p><p><span m='1383145'>Well</span> <span
  m='1383289'>it</span> <span m='1383434'>might</span> <span
  m='1383578'>suggest</span> <span m='1383723'>that</span> <span
  m='1383867'>if</span> <span m='1384012'>we</span> <span
  m='1384157'>make</span> <span m='1384301'>a</span> <span
  m='1384446'>change</span> <span m='1384590'>to</span> <span
  m='1384735'>a</span> <span m='1384880'>neighbor,</span> <span
  m='1385336'>that</span> <span m='1385792'>we</span> <span
  m='1386248'>check</span> <span m='1386704'>its</span> <span
  m='1387160'>neighbors,</span> <span m='1387616'>too,</span> <span
  m='1388072'>make</span> <span m='1388528'>sure</span> <span
  m='1388984'>they're</span> <span m='1389740'>all</span> <span
  m='1390496'>right.</span> </p><p><span m='1391253'>So</span> <span
  m='1391992'>another</span> <span m='1392732'>choice</span> <span
  m='1393472'>is</span> <span m='1394211'>to</span> <span
  m='1394951'>propagate.</span> </p><p><span m='1425654'>So</span> <span
  m='1426354'>propagate</span> <span m='1427055'>through</span> <span
  m='1427756'>variables</span> <span m='1428456'>with</span> <span
  m='1429157'>reduced</span> <span m='1429858'>domains.</span> </p><p><span
  m='1430559'>Let's</span> <span m='1430839'>see</span> <span
  m='1431119'>how</span> <span m='1431400'>that</span> <span
  m='1431680'>works.</span> </p><p><span m='1443706'>Wait</span> <span
  m='1444117'>a</span> <span m='1444528'>minute.</span> </p><p><span
  m='1446775'>I</span> <span m='1447047'>must</span> <span
  m='1447320'>have</span> <span m='1447592'>made</span> <span
  m='1447865'>a</span> <span m='1448137'>mistake.</span> </p><p><span
  m='1448410'>Let's</span> <span m='1448977'>try</span> <span
  m='1449544'>that</span> <span m='1450111'>again.</span> </p><p><span
  m='1450679'>Oh,</span> <span m='1451027'>maybe</span> <span
  m='1451375'>we</span> <span m='1451723'>better</span> <span
  m='1452071'>slow</span> <span m='1452419'>it</span> <span
  m='1452767'>down.</span> </p><p><span m='1457953'>All</span> <span
  m='1458229'>that</span> <span m='1458505'>grey</span> <span
  m='1458781'>stuff</span> <span m='1459057'>is</span> <span
  m='1459333'>showing</span> <span m='1459609'>the</span> <span
  m='1459885'>limit</span> <span m='1460161'>of</span> <span
  m='1460437'>the</span> <span m='1460713'>propagation.</span> </p><p><span
  m='1467463'>Man</span> <span m='1467963'>it's,</span> <span
  m='1468463'>let's</span> <span m='1468964'>see</span> <span
  m='1469464'>at</span> <span m='1469965'>four</span> <span
  m='1470465'>second</span> <span m='1470966'>of</span> <span
  m='1471466'>40,</span> <span m='1471967'>that's</span> <span
  m='1473401'>about</span> <span m='1474836'>10</span> <span
  m='1476271'>seconds.</span> </p><p><span m='1477706'>Boom.</span> </p><p><span
  m='1479374'>Not</span> <span m='1479958'>bad.</span> </p><p><span
  m='1480542'>Zero</span> <span m='1481131'>dead</span> <span
  m='1481721'>ends.</span> </p><p><span m='1482311'>And</span> <span
  m='1482472'>it</span> <span m='1482633'>was</span> <span m='1482794'>a</span>
  <span m='1482955'>lot</span> <span m='1483116'>faster.</span> </p><p><span
  m='1483278'>I</span> <span m='1483454'>didn't</span> <span
  m='1483631'>happen</span> <span m='1483808'>to</span> <span
  m='1483985'>notice</span> <span m='1484162'>how</span> <span
  m='1484339'>many</span> <span m='1484516'>constraints</span> <span
  m='1484693'>were</span> <span m='1484870'>checked</span> <span
  m='1485047'>on</span> <span m='1485319'>that</span> <span
  m='1485592'>other</span> <span m='1485864'>thing,</span> <span
  m='1486137'>I</span> <span m='1486409'>think</span> <span
  m='1486682'>it</span> <span m='1486954'>was</span> <span
  m='1487227'>around</span> <span m='1487499'>20,000</span> <span
  m='1487772'>or</span> <span m='1488044'>so.</span> </p><p><span
  m='1488317'>This</span> <span m='1488837'>is</span> <span m='1489357'>a</span>
  <span m='1489878'>lot</span> <span m='1490398'>less.</span> </p><p><span
  m='1490919'>So</span> <span m='1491290'>this</span> <span
  m='1491662'>looks</span> <span m='1492034'>like</span> <span
  m='1492406'>a</span> <span m='1492778'>good</span> <span
  m='1493150'>idea.</span> </p><p><span m='1493522'>But</span> <span
  m='1493884'>why</span> <span m='1494247'>did</span> <span m='1494610'>I</span>
  <span m='1494973'>label</span> <span m='1495336'>it</span> <span
  m='1495699'>number</span> <span m='1496062'>five?</span> </p><p><span
  m='1496425'>Well</span> <span m='1496836'>because</span> <span
  m='1497247'>there's</span> <span m='1497659'>something</span> <span
  m='1498070'>between</span> <span m='1498482'>this</span> <span
  m='1498893'>and</span> <span m='1499305'>number</span> <span
  m='1499716'>three.</span> </p><p><span m='1500128'>So</span> <span
  m='1501326'>number</span> <span m='1502524'>four</span> <span
  m='1503723'>is,</span> <span m='1504921'>through</span> <span
  m='1506120'>v</span> <span m='1507318'>with</span> <span m='1508516'>d</span>
  <span m='1509715'>reduced</span> <span m='1510913'>to</span> <span
  m='1512112'>one</span> <span m='1513310'>value.</span> </p><p><span
  m='1518213'>So</span> <span m='1518483'>we're</span> <span
  m='1518753'>not</span> <span m='1519023'>going</span> <span
  m='1519294'>to</span> <span m='1519564'>propagate</span> <span
  m='1519834'>through</span> <span m='1520105'>all</span> <span
  m='1520375'>of</span> <span m='1520645'>the</span> <span
  m='1520916'>variables</span> <span m='1521364'>which</span> <span
  m='1521813'>have</span> <span m='1522261'>their</span> <span
  m='1522710'>domains</span> <span m='1523158'>shrunk</span> <span
  m='1523607'>a</span> <span m='1524055'>little</span> <span
  m='1524504'>bit.</span> </p><p><span m='1524953'>We're</span> <span
  m='1525139'>only</span> <span m='1525326'>going</span> <span
  m='1525513'>to</span> <span m='1525700'>propagate</span> <span
  m='1525887'>through</span> <span m='1526074'>those</span> <span
  m='1526261'>that</span> <span m='1526448'>have</span> <span
  m='1526635'>the</span> <span m='1526822'>greater</span> <span
  m='1527309'>shrinkage,</span> <span m='1527796'>all</span> <span
  m='1528283'>the</span> <span m='1528770'>way</span> <span
  m='1529257'>down</span> <span m='1529744'>to</span> <span m='1530231'>a</span>
  <span m='1530718'>single</span> <span m='1531205'>value.</span> </p><p><span
  m='1531693'>So</span> <span m='1531936'>let's</span> <span
  m='1532179'>see</span> <span m='1532422'>how</span> <span
  m='1532665'>that</span> <span m='1532908'>might</span> <span
  m='1533151'>work.</span> </p><p><span m='1544773'>Anybody</span> <span
  m='1545136'>want</span> <span m='1545499'>to</span> <span
  m='1545863'>place</span> <span m='1546226'>any</span> <span
  m='1546589'>bets</span> <span m='1546953'>on</span> <span
  m='1547316'>this</span> <span m='1547679'>one?</span> </p><p><span
  m='1548043'>Let's</span> <span m='1548260'>see.</span> </p><p><span
  m='1548477'>We</span> <span m='1549177'>checked</span> <span
  m='1549878'>2,623</span> <span m='1550579'>constraints</span> <span
  m='1551279'>last</span> <span m='1551980'>time.</span> </p><p><span
  m='1552681'>Let's</span> <span m='1552892'>see</span> <span
  m='1553103'>what</span> <span m='1553315'>happens</span> <span
  m='1553526'>this</span> <span m='1553737'>time.</span> </p><p><span
  m='1556785'>You</span> <span m='1557041'>can</span> <span
  m='1557298'>see</span> <span m='1557555'>that</span> <span
  m='1557811'>the</span> <span m='1558068'>extent</span> <span
  m='1558325'>of</span> <span m='1558581'>the</span> <span
  m='1558838'>gray</span> <span m='1559095'>is</span> <span
  m='1559351'>less,</span> <span m='1559608'>because</span> <span
  m='1559865'>it's</span> <span m='1560122'>not</span> <span
  m='1560505'>propagating</span> <span m='1560889'>so</span> <span
  m='1561272'>far.</span> </p><p><span m='1570799'>And</span> <span
  m='1571897'>as</span> <span m='1572995'>we</span> <span
  m='1574093'>breathily</span> <span m='1575191'>await</span> <span
  m='1576289'>the</span> <span m='1577387'>answer,</span> <span
  m='1578485'>I'd</span> <span m='1579583'>say</span> <span
  m='1580681'>we've</span> <span m='1581779'>found</span> <span
  m='1582878'>our</span> <span m='1583295'>winner.</span> </p><p><span
  m='1583712'>As</span> <span m='1584003'>this</span> <span
  m='1584295'>does</span> <span m='1584587'>a</span> <span
  m='1584879'>couple</span> <span m='1585171'>of</span> <span
  m='1585463'>dead</span> <span m='1585755'>ends,</span> <span
  m='1586047'>but</span> <span m='1586339'>the</span> <span
  m='1586631'>number</span> <span m='1586923'>of</span> <span
  m='1587215'>constraint</span> <span m='1587882'>checked</span> <span
  m='1588549'>is</span> <span m='1589217'>less</span> <span
  m='1589884'>than</span> <span m='1590551'>1,000.</span> </p><p><span
  m='1591219'>So</span> <span m='1591431'>in</span> <span
  m='1591643'>general,</span> <span m='1591856'>with</span> <span
  m='1592068'>problems</span> <span m='1592280'>this,</span> <span
  m='1592493'>you</span> <span m='1592705'>have</span> <span
  m='1592917'>all</span> <span m='1593130'>of</span> <span
  m='1593342'>these</span> <span m='1593555'>choices</span> <span
  m='1594022'>for</span> <span m='1594489'>what</span> <span
  m='1594956'>you</span> <span m='1595423'>consider.</span> </p><p><span
  m='1595891'>You</span> <span m='1596068'>don't</span> <span
  m='1596246'>want</span> <span m='1596424'>to</span> <span
  m='1596602'>consider</span> <span m='1596780'>nothing,</span> <span
  m='1596958'>because</span> <span m='1597136'>then</span> <span
  m='1597314'>you're</span> <span m='1597492'>not</span> <span
  m='1598026'>honoring</span> <span m='1598560'>your</span> <span
  m='1599094'>constraints.</span> </p><p><span m='1599628'>You'll</span> <span
  m='1599835'>certainly</span> <span m='1600043'>want</span> <span
  m='1600250'>to</span> <span m='1600458'>consider</span> <span
  m='1600665'>the</span> <span m='1600873'>things</span> <span
  m='1601080'>you</span> <span m='1601288'>just</span> <span
  m='1601496'>made</span> <span m='1602292'>assignments</span> <span
  m='1603089'>for,</span> <span m='1603885'>because</span> <span
  m='1604682'>otherwise</span> <span m='1605479'>you'll</span> <span
  m='1606275'>construct</span> <span m='1607072'>a</span> <span
  m='1607869'>solution</span> <span m='1608516'>that</span> <span
  m='1609163'>violates</span> <span m='1609811'>a</span> <span
  m='1610458'>constraint.</span> </p><p><span m='1611106'>You</span> <span
  m='1611514'>don't</span> <span m='1611923'>want</span> <span
  m='1612332'>to</span> <span m='1612741'>do</span> <span
  m='1613149'>everything,</span> <span m='1613558'>because</span> <span
  m='1613967'>that's</span> <span m='1614376'>excessive</span> <span
  m='1615310'>work.</span> </p><p><span m='1616244'>And</span> <span
  m='1616859'>so</span> <span m='1617475'>checking</span> <span
  m='1618091'>the</span> <span m='1618707'>neighbors</span> <span
  m='1619323'>is</span> <span m='1619938'>a</span> <span m='1620554'>good</span>
  <span m='1621170'>idea,</span> <span m='1621786'>but</span> <span
  m='1622402'>it's</span> <span m='1623018'>always</span> <span
  m='1623643'>better</span> <span m='1624269'>in</span> <span
  m='1624894'>practice.</span> </p><p><span m='1625520'>In</span> <span
  m='1625803'>practice,</span> <span m='1626087'>inevitably</span> <span
  m='1626370'>it's</span> <span m='1626654'>the</span> <span
  m='1626938'>case</span> <span m='1627221'>that</span> <span
  m='1627505'>it's</span> <span m='1627788'>better</span> <span
  m='1628072'>to</span> <span m='1628356'>do</span> <span
  m='1628616'>some</span> <span m='1628876'>propagation</span> <span
  m='1629137'>through</span> <span m='1629397'>the</span> <span
  m='1629658'>things</span> <span m='1630041'>that</span> <span
  m='1630425'>you've</span> <span m='1630808'>changed.</span> </p><p><span
  m='1631192'>How</span> <span m='1631692'>much</span> <span
  m='1632193'>propagation?</span> </p><p><span m='1632694'>It</span> <span
  m='1632897'>doesn't</span> <span m='1633101'>seem</span> <span
  m='1633304'>to</span> <span m='1633508'>do</span> <span
  m='1633711'>much</span> <span m='1633915'>good</span> <span
  m='1634118'>to</span> <span m='1634322'>propagate</span> <span
  m='1634525'>through</span> <span m='1634729'>things</span> <span
  m='1635112'>are</span> <span m='1635496'>just</span> <span
  m='1635880'>changed.</span> </p><p><span m='1636264'>But</span> <span
  m='1636475'>it</span> <span m='1636686'>does</span> <span
  m='1636898'>seem</span> <span m='1637109'>to</span> <span
  m='1637320'>do</span> <span m='1637532'>some</span> <span
  m='1637743'>good</span> <span m='1637954'>to</span> <span
  m='1638166'>propagate</span> <span m='1638377'>through</span> <span
  m='1638588'>the</span> <span m='1638800'>things</span> <span
  m='1638983'>that</span> <span m='1639167'>have</span> <span
  m='1639350'>changed</span> <span m='1639534'>and</span> <span
  m='1639717'>been</span> <span m='1639901'>reduced</span> <span
  m='1640475'>to</span> <span m='1641049'>a</span> <span
  m='1641623'>single</span> <span m='1642197'>value.</span> </p><p><span
  m='1642771'>So</span> <span m='1643028'>as</span> <span
  m='1643286'>soon</span> <span m='1643544'>as</span> <span
  m='1643802'>you</span> <span m='1644060'>get</span> <span m='1644317'>a</span>
  <span m='1644575'>neighbor</span> <span m='1644833'>of</span> <span
  m='1645091'>some</span> <span m='1645349'>assignment</span> <span
  m='1645607'>you</span> <span m='1645867'>just</span> <span
  m='1646128'>made</span> <span m='1646389'>that</span> <span
  m='1646650'>has</span> <span m='1646911'>its</span> <span
  m='1647171'>domain</span> <span m='1647432'>reduced</span> <span
  m='1647693'>to</span> <span m='1647954'>a</span> <span
  m='1648215'>single</span> <span m='1648476'>value,</span> <span
  m='1648824'>then</span> <span m='1649172'>you</span> <span
  m='1649520'>check</span> <span m='1649868'>its</span> <span
  m='1650216'>neighbors,</span> <span m='1650564'>too.</span> </p><p><span
  m='1650912'>So</span> <span m='1651082'>you</span> <span
  m='1651252'>check</span> <span m='1651422'>the</span> <span
  m='1651592'>neighbors,</span> <span m='1651763'>of</span> <span
  m='1651933'>the</span> <span m='1652103'>neighbors,</span> <span
  m='1652273'>of</span> <span m='1652443'>the</span> <span
  m='1652614'>neighbors,</span> <span m='1652936'>of</span> <span
  m='1653259'>the</span> <span m='1653581'>neighbors,</span> <span
  m='1653904'>on</span> <span m='1654226'>and</span> <span m='1654549'>on</span>
  <span m='1654871'>and</span> <span m='1655194'>on,</span> <span
  m='1655516'>as</span> <span m='1655839'>long</span> <span
  m='1656161'>as</span> <span m='1656484'>you've</span> <span
  m='1657095'>found</span> <span m='1657707'>a</span> <span
  m='1658319'>domain</span> <span m='1658931'>being</span> <span
  m='1659543'>reduced.</span> </p><p><span m='1660155'>And</span> <span
  m='1660446'>not</span> <span m='1660737'>only</span> <span
  m='1661028'>being</span> <span m='1661319'>reduced,</span> <span
  m='1661610'>but</span> <span m='1661902'>reduced</span> <span
  m='1662193'>to</span> <span m='1662484'>a</span> <span
  m='1662775'>signal</span> <span m='1663066'>value.</span> </p><p><span
  m='1663358'>All</span> <span m='1663558'>right?</span> </p><p><span
  m='1663758'>So</span> <span m='1664030'>that's</span> <span
  m='1664303'>the</span> <span m='1664575'>demand</span> <span
  m='1664848'>reduction</span> <span m='1665120'>algorithm.</span> </p><p><span
  m='1665393'>And</span> <span m='1665847'>I</span> <span
  m='1666302'>guarantee</span> <span m='1666756'>you</span> <span
  m='1667211'>a</span> <span m='1667666'>problem</span> <span
  m='1668120'>like</span> <span m='1668575'>that.</span> </p><p><span
  m='1669030'>And</span> <span m='1669319'>I</span> <span
  m='1669608'>know</span> <span m='1669897'>you</span> <span
  m='1670186'>don't</span> <span m='1670475'>know</span> <span
  m='1670765'>how</span> <span m='1671054'>to</span> <span
  m='1671343'>work</span> <span m='1671632'>those</span> <span
  m='1671921'>problems</span> <span m='1672210'>yet,</span> <span
  m='1672500'>because</span> <span m='1672747'>this</span> <span
  m='1672995'>is</span> <span m='1673243'>a</span> <span
  m='1673491'>little</span> <span m='1673739'>bit</span> <span
  m='1673987'>abstract.</span> </p><p><span m='1674235'>And</span> <span
  m='1674593'>to</span> <span m='1674952'>work</span> <span
  m='1675311'>these</span> <span m='1675670'>problems</span> <span
  m='1676028'>in</span> <span m='1676387'>the</span> <span
  m='1676746'>exam</span> <span m='1677105'>setting</span> <span
  m='1677463'>you</span> <span m='1677822'>need</span> <span
  m='1678181'>to</span> <span m='1678540'>know</span> <span m='1678781'>a</span>
  <span m='1679023'>little</span> <span m='1679265'>bit</span> <span
  m='1679507'>about</span> <span m='1679749'>how</span> <span
  m='1679991'>to</span> <span m='1680233'>keep</span> <span
  m='1680475'>track</span> <span m='1680717'>of</span> <span
  m='1680959'>the</span> <span m='1681201'>variable</span> <span
  m='1681443'>values</span> <span m='1681790'>that</span> <span
  m='1682138'>remain</span> <span m='1682486'>in</span> <span
  m='1682834'>the</span> <span m='1683182'>domain,</span> <span
  m='1683530'>and</span> <span m='1683878'>that</span> <span
  m='1684036'>sort</span> <span m='1684195'>of</span> <span
  m='1684353'>thing.</span> </p><p><span m='1684512'>And</span> <span
  m='1684762'>you'll</span> <span m='1685012'>learn</span> <span
  m='1685262'>more</span> <span m='1685513'>about</span> <span
  m='1685763'>that</span> <span m='1686013'>in</span> <span
  m='1686264'>your</span> <span m='1686514'>recitations,</span> <span
  m='1686764'>and</span> <span m='1687015'>in</span> <span
  m='1687511'>this</span> <span m='1688007'>mega</span> <span
  m='1688503'>recitation,</span> <span m='1689000'>and</span> <span
  m='1689496'>in</span> <span m='1689992'>the</span> <span
  m='1690488'>tutorials.</span> </p><p><span m='1690985'>So</span> <span
  m='1691209'>we</span> <span m='1691434'>could</span> <span
  m='1691658'>go</span> <span m='1691883'>home</span> <span
  m='1692107'>except</span> <span m='1692332'>that</span> <span
  m='1692556'>there</span> <span m='1692781'>are</span> <span
  m='1693005'>few</span> <span m='1693230'>little</span> <span
  m='1693455'>flourishes</span> <span m='1693975'>to</span> <span
  m='1694495'>deal</span> <span m='1695016'>with</span> <span
  m='1695536'>here.</span> </p><p><span m='1696057'>And</span> <span
  m='1697614'>those</span> <span m='1699171'>flourishes,</span> <span
  m='1700728'>include</span> <span m='1702285'>some</span> <span
  m='1703842'>dirty,</span> <span m='1705400'>filthy</span> <span
  m='1706167'>little</span> <span m='1706934'>secrets.</span> </p><p><span
  m='1707702'>For</span> <span m='1708173'>example,</span> <span
  m='1708645'>I've</span> <span m='1709117'>chosen,</span> <span
  m='1709589'>as</span> <span m='1710061'>my</span> <span
  m='1710533'>classroom</span> <span m='1711005'>example,</span> <span
  m='1711519'>to</span> <span m='1712033'>pick</span> <span
  m='1712547'>on</span> <span m='1713061'>Texas.</span> </p><p><span
  m='1713575'>And</span> <span m='1713947'>arranged</span> <span
  m='1714320'>for</span> <span m='1714692'>this</span> <span
  m='1715065'>situation</span> <span m='1715437'>to</span> <span
  m='1715810'>be</span> <span m='1716644'>especially</span> <span
  m='1717478'>ugly.</span> </p><p><span m='1718313'>So</span> <span
  m='1718810'>I</span> <span m='1719307'>could</span> <span
  m='1719804'>arrange</span> <span m='1720301'>the</span> <span
  m='1720798'>states</span> <span m='1721295'>in</span> <span
  m='1721792'>a</span> <span m='1722289'>different</span> <span
  m='1722786'>way.</span> </p><p><span m='1723284'>We</span> <span
  m='1723517'>have</span> <span m='1723751'>highly</span> <span
  m='1723984'>constrained</span> <span m='1724218'>states,</span> <span
  m='1724452'>that</span> <span m='1724685'>have</span> <span
  m='1724919'>a</span> <span m='1725152'>lot</span> <span m='1725386'>of</span>
  <span m='1725620'>bordering</span> <span m='1726329'>states</span> <span
  m='1727038'>around</span> <span m='1727747'>them.</span> </p><p><span
  m='1728456'>And</span> <span m='1728971'>we</span> <span
  m='1729487'>have</span> <span m='1730002'>other</span> <span
  m='1730518'>states,</span> <span m='1731034'>like</span> <span
  m='1731549'>Maine,</span> <span m='1732065'>up</span> <span
  m='1732581'>there,</span> <span m='1733096'>that</span> <span
  m='1733612'>only</span> <span m='1734128'>borders</span> <span
  m='1734668'>on</span> <span m='1735209'>one</span> <span
  m='1735749'>other</span> <span m='1736290'>state.</span> </p><p><span
  m='1736831'>So</span> <span m='1737556'>I</span> <span
  m='1738282'>don't</span> <span m='1739008'>know.</span> </p><p><span
  m='1739734'>Will,</span> <span m='1740161'>what</span> <span
  m='1740588'>do</span> <span m='1741015'>you</span> <span
  m='1741442'>think?</span> </p><p><span m='1745173'>Should</span> <span
  m='1745524'>we</span> <span m='1745876'>arrange</span> <span
  m='1746228'>the</span> <span m='1746580'>states</span> <span
  m='1746932'>for</span> <span m='1747283'>our</span> <span
  m='1747635'>death</span> <span m='1747987'>first</span> <span
  m='1748339'>search</span> <span m='1748691'>in</span> <span
  m='1749043'>the</span> <span m='1749406'>order</span> <span
  m='1749770'>of</span> <span m='1750134'>least</span> <span
  m='1750497'>constrained</span> <span m='1750861'>to</span> <span
  m='1751225'>most</span> <span m='1751588'>constrained,</span> <span
  m='1751952'>or</span> <span m='1752316'>most</span> <span
  m='1752680'>constrained</span> <span m='1752997'>to</span> <span
  m='1753314'>least</span> <span m='1753631'>constrained?</span> </p><p><span
  m='1757885'>In</span> <span m='1758263'>other</span> <span
  m='1758641'>words,</span> <span m='1759019'>should</span> <span
  m='1759397'>we</span> <span m='1759776'>start</span> <span
  m='1760154'>with</span> <span m='1760532'>Missouri,</span> <span
  m='1760910'>or</span> <span m='1761289'>Tennessee,</span> <span
  m='1761660'>or</span> <span m='1762032'>Kentucky,</span> <span
  m='1762404'>or</span> <span m='1762775'>something</span> <span
  m='1763147'>like</span> <span m='1763519'>that?</span> </p><p><span
  m='1763891'>Or</span> <span m='1764313'>should</span> <span
  m='1764736'>we</span> <span m='1765159'>start</span> <span
  m='1765581'>with</span> <span m='1766004'>Maine?</span> </p><p><span
  m='1766427'>What</span> <span m='1766919'>do</span> <span
  m='1767411'>you</span> <span m='1767903'>think?</span> </p><p><span
  m='1768396'>You</span> <span m='1768662'>have</span> <span
  m='1768929'>a</span> <span m='1769196'>50%</span> <span
  m='1769463'>chance</span> <span m='1769730'>of</span> <span
  m='1769997'>getting</span> <span m='1770264'>it</span> <span
  m='1770531'>right,</span> <span m='1770798'>just</span> <span
  m='1771065'>by</span> <span m='1771332'>[?</span> <span
  m='1771832'>looking</span> <span m='1772333'>?]</span> <span
  m='1772833'>at</span> <span m='1773334'>points.</span> </p><p><span
  m='1773835'>WILL:</span> <span m='1774218'>Start</span> <span
  m='1774602'>with</span> <span m='1774986'>the</span> <span
  m='1775369'>most</span> <span m='1775753'>first.</span> </p><p><span
  m='1776137'>PROF.</span> </p><p><span m='1776170'>PATRICK</span> <span
  m='1776263'>WINSTON:</span> <span m='1776357'>He</span> <span
  m='1776450'>thinks</span> <span m='1776544'>we</span> <span
  m='1776637'>should</span> <span m='1776731'>start</span> <span
  m='1776824'>with</span> <span m='1776918'>the</span> <span
  m='1777011'>most</span> <span m='1777105'>constraint</span> <span
  m='1777955'>first.</span> </p><p><span m='1778806'>Do</span> <span
  m='1779045'>we</span> <span m='1779284'>have</span> <span m='1779523'>a</span>
  <span m='1779762'>volunteer</span> <span m='1780001'>who</span> <span
  m='1780241'>wants</span> <span m='1780480'>to</span> <span
  m='1780719'>suggest</span> <span m='1780958'>that</span> <span
  m='1781197'>we</span> <span m='1781436'>start</span> <span
  m='1781676'>with</span> <span m='1782223'>the</span> <span
  m='1782770'>least</span> <span m='1783317'>constraint</span> <span
  m='1783864'>first?</span> </p><p><span m='1784412'>That's</span> <span
  m='1784833'>the</span> <span m='1785254'>way</span> <span m='1785675'>I</span>
  <span m='1786097'>always</span> <span m='1786518'>work</span> <span
  m='1786939'>on</span> <span m='1787360'>stuff.</span> </p><p><span
  m='1787782'>I'm</span> <span m='1788097'>working</span> <span
  m='1788412'>on</span> <span m='1788728'>a</span> <span m='1789043'>book</span>
  <span m='1789359'>or</span> <span m='1789674'>something,</span> <span
  m='1789990'>I</span> <span m='1790305'>have</span> <span
  m='1790621'>500</span> <span m='1790936'>things</span> <span
  m='1791252'>to</span> <span m='1791512'>fix,</span> <span
  m='1791773'>I'll</span> <span m='1792034'>always</span> <span
  m='1792295'>choose</span> <span m='1792556'>to</span> <span
  m='1792817'>work</span> <span m='1793078'>on</span> <span
  m='1793339'>the</span> <span m='1793600'>easiest</span> <span
  m='1793861'>stuff</span> <span m='1794122'>first,</span> <span
  m='1794432'>so</span> <span m='1794743'>that</span> <span m='1795053'>I</span>
  <span m='1795364'>feel</span> <span m='1795674'>like</span> <span
  m='1795985'>I'm</span> <span m='1796295'>making</span> <span
  m='1796606'>the</span> <span m='1796916'>list</span> <span
  m='1797227'>a</span> <span m='1797537'>lot</span> <span
  m='1797848'>smaller.</span> </p><p><span m='1798159'>Leave</span> <span
  m='1798565'>the</span> <span m='1798971'>hardest</span> <span
  m='1799377'>things</span> <span m='1799783'>to</span> <span
  m='1800189'>last.</span> </p><p><span m='1800595'>But</span> <span
  m='1800913'>we</span> <span m='1801231'>don't</span> <span
  m='1801550'>have</span> <span m='1801868'>any</span> <span
  m='1802187'>volunteers</span> <span m='1802505'>who</span> <span
  m='1802824'>want</span> <span m='1803142'>to</span> <span
  m='1803461'>bet</span> <span m='1803779'>on</span> <span
  m='1804098'>that</span> <span m='1804620'>idea</span> <span
  m='1805143'>of</span> <span m='1805666'>least</span> <span
  m='1806189'>constraint</span> <span m='1806712'>first?</span> </p><p><span
  m='1807235'>OK.</span> </p><p><span m='1808903'>Jason</span> <span
  m='1809133'>wants</span> <span m='1809363'>to</span> <span
  m='1809593'>suggest</span> <span m='1809823'>that</span> <span
  m='1810054'>we</span> <span m='1810284'>should</span> <span
  m='1810514'>work</span> <span m='1810744'>on</span> <span
  m='1810974'>least</span> <span m='1811205'>constraint</span> <span
  m='1811722'>first.</span> </p><p><span m='1812240'>Well</span> <span
  m='1812430'>we</span> <span m='1812621'>have</span> <span
  m='1812811'>ground</span> <span m='1813002'>truth,</span> <span
  m='1813192'>because</span> <span m='1813383'>we</span> <span
  m='1813574'>can</span> <span m='1813821'>just</span> <span
  m='1814068'>try</span> <span m='1814315'>it</span> <span
  m='1814562'>out.</span> </p><p><span m='1819514'>I</span> <span
  m='1819703'>guess</span> <span m='1819892'>we'll</span> <span
  m='1820081'>stick</span> <span m='1820270'>with</span> <span
  m='1820459'>our</span> <span m='1820648'>shrinking</span> <span
  m='1820837'>to</span> <span m='1821026'>one</span> <span
  m='1821215'>value</span> <span m='1822194'>thing,</span> <span
  m='1823173'>here.</span> </p><p><span m='1824152'>But</span> <span
  m='1824600'>we</span> <span m='1825049'>will</span> <span
  m='1825498'>reorder</span> <span m='1825947'>things</span> <span
  m='1826396'>so</span> <span m='1826845'>that</span> <span
  m='1827294'>we</span> <span m='1827743'>have</span> <span
  m='1828192'>the</span> <span m='1828641'>least</span> <span
  m='1829090'>constrained</span> <span m='1829707'>first.</span> </p><p><span
  m='1834128'>So</span> <span m='1834458'>right</span> <span
  m='1834788'>away,</span> <span m='1835118'>we</span> <span
  m='1835448'>got</span> <span m='1835778'>a</span> <span
  m='1836108'>color</span> <span m='1836438'>for</span> <span
  m='1836768'>Maine.</span> </p><p><span m='1840334'>Maybe</span> <span
  m='1840460'>we</span> <span m='1840587'>ought</span> <span
  m='1840714'>to</span> <span m='1840841'>speed</span> <span
  m='1840968'>this</span> <span m='1841094'>up</span> <span m='1841221'>a</span>
  <span m='1841348'>little</span> <span m='1841475'>bit.</span> </p><p><span
  m='1846741'>Well,</span> <span m='1847121'>that's</span> <span
  m='1847501'>a</span> <span m='1847882'>good</span> <span
  m='1848262'>idea.</span> </p><p><span m='1848643'>Jason</span> <span
  m='1849200'>suggested</span> <span m='1849757'>this</span> <span
  m='1850314'>and</span> <span m='1850871'>we</span> <span
  m='1851429'>only</span> <span m='1851986'>1,732</span> <span
  m='1852543'>constraints</span> <span m='1853100'>and</span> <span
  m='1853657'>we</span> <span m='1854215'>had</span> <span m='1854465'>59</span>
  <span m='1854715'>dead</span> <span m='1854965'>ends.</span> </p><p><span
  m='1855216'>So</span> <span m='1855708'>let's</span> <span
  m='1856200'>try</span> <span m='1856692'>the</span> <span
  m='1857184'>other</span> <span m='1857676'>way</span> <span
  m='1858169'>around,</span> <span m='1858661'>and</span> <span
  m='1859153'>we'll</span> <span m='1859645'>go</span> <span
  m='1860137'>back</span> <span m='1860629'>to</span> <span
  m='1861122'>four</span> <span m='1861430'>frames</span> <span
  m='1861739'>a</span> <span m='1862047'>second.</span> </p><p><span
  m='1875069'>So</span> <span m='1875241'>we're</span> <span
  m='1875413'>working,</span> <span m='1875586'>kind</span> <span
  m='1875758'>of</span> <span m='1875931'>from</span> <span
  m='1876103'>the</span> <span m='1876275'>middle</span> <span
  m='1876448'>of</span> <span m='1876620'>the</span> <span
  m='1876793'>country</span> <span m='1876965'>out,</span> <span
  m='1877138'>with</span> <span m='1877594'>this</span> <span
  m='1878050'>one.</span> </p><p><span m='1878506'>We're</span> <span
  m='1878676'>going</span> <span m='1878847'>to</span> <span
  m='1879017'>deal</span> <span m='1879188'>with</span> <span
  m='1879358'>Maine,</span> <span m='1879529'>I</span> <span
  m='1879699'>guess,</span> <span m='1879870'>last.</span> </p><p><span
  m='1886080'>Which</span> <span m='1886958'>is</span> <span
  m='1887837'>better.</span> </p><p><span m='1888716'>Too</span> <span
  m='1889029'>bad,</span> <span m='1889343'>I</span> <span
  m='1889656'>think</span> <span m='1889970'>it</span> <span
  m='1890284'>looks</span> <span m='1890597'>like</span> <span
  m='1890911'>this</span> <span m='1891224'>is</span> <span
  m='1891538'>better.</span> </p><p><span m='1891852'>In</span> <span
  m='1892143'>fact,</span> <span m='1892434'>let's</span> <span
  m='1892725'>not</span> <span m='1893017'>be</span> <span m='1893308'>so</span>
  <span m='1893599'>aggressive</span> <span m='1893890'>with</span> <span
  m='1894182'>the</span> <span m='1894473'>use</span> <span
  m='1894764'>of</span> <span m='1895056'>constraint</span> <span
  m='1895606'>propagation.</span> </p><p><span m='1896157'>Let's</span> <span
  m='1896613'>just</span> <span m='1897069'>check</span> <span
  m='1897525'>the</span> <span m='1897981'>assignments</span> <span
  m='1898437'>only.</span> </p><p><span m='1898893'>If</span> <span
  m='1899126'>we</span> <span m='1899360'>go</span> <span
  m='1899593'>back</span> <span m='1899827'>to</span> <span
  m='1900060'>an</span> <span m='1900294'>arrangement</span> <span
  m='1900527'>where</span> <span m='1900761'>we</span> <span
  m='1900994'>have</span> <span m='1901228'>least</span> <span
  m='1901665'>constrained</span> <span m='1902103'>first,</span> <span
  m='1902540'>and</span> <span m='1902978'>we'll</span> <span
  m='1903415'>crank</span> <span m='1903853'>up</span> <span
  m='1904290'>the</span> <span m='1904728'>speed.</span> </p><p><span
  m='1908335'>Well</span> <span m='1908520'>actually,</span> <span
  m='1908705'>we</span> <span m='1908890'>would</span> <span
  m='1909075'>have</span> <span m='1909260'>to</span> <span
  m='1909445'>crank</span> <span m='1909630'>it</span> <span
  m='1909815'>up</span> <span m='1910000'>pretty</span> <span
  m='1910185'>big,</span> <span m='1910371'>because</span> <span
  m='1911019'>the</span> <span m='1911667'>states</span> <span
  m='1912315'>like</span> <span m='1912964'>Missouri,</span> <span
  m='1913612'>Tennessee,</span> <span m='1914260'>Kentucky,</span> <span
  m='1914909'>they're</span> <span m='1915498'>going</span> <span
  m='1916088'>to</span> <span m='1916677'>be</span> <span
  m='1917267'>like</span> <span m='1917856'>Texas.</span> </p><p><span
  m='1918446'>And</span> <span m='1918651'>so</span> <span
  m='1918857'>were</span> <span m='1919063'>kind</span> <span
  m='1919269'>of</span> <span m='1919474'>back</span> <span
  m='1919680'>to</span> <span m='1919886'>the</span> <span
  m='1920092'>length</span> <span m='1920297'>of</span> <span
  m='1920503'>the</span> <span m='1920709'>universe</span> <span
  m='1920915'>type</span> <span m='1921148'>problem,</span> <span
  m='1921381'>here.</span> </p><p><span m='1921615'>With</span> <span
  m='1921974'>the</span> <span m='1922334'>least</span> <span
  m='1922694'>constraint</span> <span m='1923053'>first,</span> <span
  m='1923413'>and</span> <span m='1923773'>no</span> <span
  m='1924132'>use</span> <span m='1924492'>of</span> <span
  m='1924852'>constraints,</span> <span m='1925531'>other</span> <span
  m='1926211'>than</span> <span m='1926891'>to</span> <span
  m='1927571'>check</span> <span m='1928251'>the</span> <span
  m='1928931'>current</span> <span m='1929611'>assignment.</span> </p><p><span
  m='1930291'>So</span> <span m='1930724'>let's</span> <span
  m='1931158'>stop</span> <span m='1931592'>that,</span> <span
  m='1932025'>though,</span> <span m='1932459'>and</span> <span
  m='1932893'>check</span> <span m='1933326'>the</span> <span
  m='1933760'>most</span> <span m='1934194'>constrained</span> <span
  m='1934628'>first,</span> <span m='1935740'>assignments</span> <span
  m='1936852'>only.</span> </p><p><span m='1937965'>I</span> <span
  m='1938135'>don't</span> <span m='1938306'>know</span> <span
  m='1938476'>how</span> <span m='1938647'>long's</span> <span
  m='1938817'>this</span> <span m='1938988'>going</span> <span
  m='1939158'>to</span> <span m='1939329'>take.</span> </p><p><span
  m='1942069'>That's</span> <span m='1942522'>the</span> <span
  m='1942976'>dirty</span> <span m='1943430'>little</span> <span
  m='1943884'>secret.</span> </p><p><span m='1944338'>If</span> <span
  m='1944689'>we</span> <span m='1945041'>had</span> <span
  m='1945393'>arranged</span> <span m='1945745'>our</span> <span
  m='1946097'>states</span> <span m='1946449'>from</span> <span
  m='1946801'>most</span> <span m='1947153'>constrained</span> <span
  m='1947505'>to</span> <span m='1947857'>least</span> <span
  m='1948209'>constrained,</span> <span m='1948479'>ordinary</span> <span
  m='1948750'>depth</span> <span m='1949020'>first</span> <span
  m='1949291'>search</span> <span m='1949561'>with</span> <span
  m='1949832'>none</span> <span m='1950102'>of</span> <span
  m='1950373'>this</span> <span m='1950644'>stuff</span> <span
  m='1951022'>we</span> <span m='1951400'>talked</span> <span
  m='1951778'>about</span> <span m='1952156'>today</span> <span
  m='1952535'>would</span> <span m='1952913'>work</span> <span
  m='1953291'>just</span> <span m='1953669'>fine.</span> </p><p><span
  m='1954048'>All</span> <span m='1954665'>right.</span> </p><p><span
  m='1958919'>So</span> <span m='1959452'>it's</span> <span m='1959986'>a</span>
  <span m='1960520'>little</span> <span m='1961054'>bit</span> <span
  m='1961588'>like</span> <span m='1962122'>games.</span> </p><p><span
  m='1962656'>Do</span> <span m='1962908'>you</span> <span
  m='1963161'>use</span> <span m='1963414'>progressive</span> <span
  m='1963666'>deepening,</span> <span m='1963919'>or</span> <span
  m='1964172'>do</span> <span m='1964425'>you</span> <span
  m='1964742'>use</span> <span m='1965059'>alpha</span> <span
  m='1965376'>beta?</span> </p><p><span m='1965693'>And</span> <span
  m='1965966'>the</span> <span m='1966240'>answer</span> <span
  m='1966513'>is</span> <span m='1966787'>both.</span> </p><p><span
  m='1967061'>You</span> <span m='1967544'>use</span> <span
  m='1968028'>everything</span> <span m='1968512'>you've</span> <span
  m='1968996'>got</span> <span m='1969480'>to</span> <span
  m='1969963'>deal</span> <span m='1970447'>with</span> <span
  m='1970931'>the</span> <span m='1971415'>problems.</span> </p><p><span
  m='1971899'>And</span> <span m='1972326'>depending</span> <span
  m='1972754'>on</span> <span m='1973182'>the</span> <span
  m='1973609'>problem,</span> <span m='1974037'>one</span> <span
  m='1974465'>or</span> <span m='1974893'>another</span> <span
  m='1975320'>of</span> <span m='1975748'>the</span> <span
  m='1976176'>things</span> <span m='1976604'>you</span> <span
  m='1976919'>incorporate</span> <span m='1977234'>into</span> <span
  m='1977549'>your</span> <span m='1977864'>approach</span> <span
  m='1978179'>will</span> <span m='1978494'>work</span> <span
  m='1978809'>just</span> <span m='1979124'>great,</span> <span
  m='1979440'>if</span> <span m='1980374'>you're</span> <span
  m='1981308'>lucky.</span> </p><p><span m='1982242'>So</span> <span
  m='1982550'>now,</span> <span m='1982858'>I</span> <span
  m='1983166'>promise</span> <span m='1983474'>that</span> <span
  m='1983782'>this</span> <span m='1984090'>is</span> <span
  m='1984398'>useful</span> <span m='1984706'>not</span> <span
  m='1985014'>only</span> <span m='1985322'>for</span> <span
  m='1985630'>people</span> <span m='1985938'>who</span> <span
  m='1986246'>want</span> <span m='1986421'>to</span> <span
  m='1986596'>color</span> <span m='1986771'>maps.</span> </p><p><span
  m='1986947'>God,</span> <span m='1987125'>who</span> <span
  m='1987303'>wants</span> <span m='1987481'>to</span> <span
  m='1987659'>do</span> <span m='1987837'>that?</span> </p><p><span
  m='1988015'>We</span> <span m='1988259'>know</span> <span
  m='1988504'>it</span> <span m='1988749'>can</span> <span m='1988993'>be</span>
  <span m='1989238'>done</span> <span m='1989483'>with</span> <span
  m='1989727'>four</span> <span m='1989972'>colors.</span> </p><p><span
  m='1990217'>But</span> <span m='1990535'>it's</span> <span
  m='1990854'>also</span> <span m='1991173'>useful</span> <span
  m='1991492'>for</span> <span m='1991811'>doing</span> <span
  m='1992130'>all</span> <span m='1992449'>kinds</span> <span
  m='1992768'>of</span> <span m='1993087'>resource</span> <span
  m='1993965'>planning</span> <span m='1994844'>problems.</span> </p><p><span
  m='1995723'>So</span> <span m='1995938'>I</span> <span m='1996153'>want</span>
  <span m='1996369'>to</span> <span m='1996584'>show</span> <span
  m='1996799'>you</span> <span m='1997015'>a</span> <span
  m='1997230'>resource</span> <span m='1997445'>planning</span> <span
  m='1997661'>problem,</span> <span m='1997876'>and</span> <span
  m='1998092'>I</span> <span m='1998303'>want</span> <span
  m='1998514'>you</span> <span m='1998726'>think</span> <span
  m='1998937'>about--</span> <span m='1999148'>while</span> <span
  m='1999360'>I'm</span> <span m='1999571'>doing</span> <span
  m='1999782'>it--</span> <span m='1999994'>think</span> <span
  m='2000227'>about</span> <span m='2000461'>whether</span> <span
  m='2000694'>it's</span> <span m='2000928'>actually</span> <span
  m='2001161'>analogous</span> <span m='2001395'>to</span> <span
  m='2001628'>the</span> <span m='2001862'>map</span> <span
  m='2002096'>coloring</span> <span m='2002496'>problem.</span> </p><p><span
  m='2002896'>All</span> <span m='2003680'>right?</span> </p><p><span
  m='2004465'>So</span> <span m='2004690'>here's</span> <span
  m='2004915'>the</span> <span m='2005140'>deal.</span> </p><p><span
  m='2005366'>You</span> <span m='2005743'>have</span> <span
  m='2006120'>just</span> <span m='2006497'>landed</span> <span
  m='2006874'>a</span> <span m='2007251'>summer</span> <span
  m='2007628'>job</span> <span m='2008005'>with</span> <span
  m='2008382'>the</span> <span m='2008759'>Jet</span> <span
  m='2009136'>Green,</span> <span m='2009953'>a</span> <span
  m='2010771'>new</span> <span m='2011588'>airline.</span> </p><p><span
  m='2012406'>And</span> <span m='2013164'>Jet</span> <span
  m='2013922'>Green</span> <span m='2014681'>is</span> <span
  m='2015439'>a</span> <span m='2016197'>low</span> <span
  m='2016956'>cost,</span> <span m='2017714'>no</span> <span
  m='2018472'>frills,</span> <span m='2019231'>hardly</span> <span
  m='2019989'>any</span> <span m='2020748'>maintenance</span> <span
  m='2021473'>type</span> <span m='2022199'>of</span> <span
  m='2022924'>airline.</span> </p><p><span m='2023650'>And</span> <span
  m='2024038'>they</span> <span m='2024426'>want</span> <span
  m='2024814'>to</span> <span m='2025203'>fly</span> <span
  m='2025591'>mostly</span> <span m='2025979'>between</span> <span
  m='2026367'>Boston</span> <span m='2026756'>and</span> <span
  m='2027144'>New</span> <span m='2027532'>York.</span> </p><p><span
  m='2027921'>Occasionally</span> <span m='2028267'>they</span> <span
  m='2028613'>want</span> <span m='2028959'>to</span> <span
  m='2029306'>fly</span> <span m='2029652'>to</span> <span
  m='2029998'>Los</span> <span m='2030344'>Angeles.</span> </p><p><span
  m='2030691'>And</span> <span m='2030862'>they're</span> <span
  m='2031033'>trying</span> <span m='2031204'>to</span> <span
  m='2031375'>get</span> <span m='2031546'>by</span> <span
  m='2031717'>with</span> <span m='2031888'>the</span> <span
  m='2032059'>smallest</span> <span m='2032559'>number</span> <span
  m='2033060'>of</span> <span m='2033560'>airplanes.</span> </p><p><span
  m='2034061'>So</span> <span m='2034376'>that's</span> <span
  m='2034691'>why</span> <span m='2035007'>we</span> <span
  m='2035322'>have</span> <span m='2035638'>a</span> <span
  m='2035953'>kind</span> <span m='2036269'>of</span> <span
  m='2036584'>resource</span> <span m='2036900'>allocation</span> <span
  m='2037215'>problem</span> <span m='2037531'>with</span> <span
  m='2038254'>Jet</span> <span m='2038977'>Green.</span> </p><p><span
  m='2039700'>So</span> <span m='2039996'>I'm</span> <span
  m='2040292'>going</span> <span m='2040588'>to</span> <span
  m='2040884'>write</span> <span m='2041180'>down</span> <span
  m='2041476'>what</span> <span m='2041772'>their</span> <span
  m='2042069'>schedule</span> <span m='2042224'>looks</span> <span
  m='2042380'>like.</span> </p><p><span m='2042536'>They</span> <span
  m='2043229'>have</span> <span m='2043922'>one</span> <span
  m='2044615'>flight,</span> <span m='2045308'>F1,</span> <span
  m='2046002'>that</span> <span m='2046695'>goes</span> <span
  m='2047388'>from</span> <span m='2048081'>Boston</span> <span
  m='2048775'>to</span> <span m='2050234'>JFK,</span> <span
  m='2051694'>like</span> <span m='2053154'>so.</span> </p><p><span
  m='2054614'>It's</span> <span m='2055090'>an</span> <span
  m='2055567'>early</span> <span m='2056044'>in</span> <span
  m='2056520'>the</span> <span m='2056997'>day</span> <span
  m='2057474'>flight.</span> </p><p><span m='2057951'>Then</span> <span
  m='2058314'>they</span> <span m='2058677'>want</span> <span
  m='2059041'>to</span> <span m='2059404'>have</span> <span
  m='2059767'>another</span> <span m='2060131'>one,</span> <span
  m='2060494'>F2,</span> <span m='2060857'>that</span> <span
  m='2061221'>flies</span> <span m='2061875'>from</span> <span
  m='2062529'>JFK</span> <span m='2063183'>to</span> <span
  m='2063837'>Boston.</span> </p><p><span m='2069563'>And</span> <span
  m='2069845'>then</span> <span m='2070127'>they</span> <span
  m='2070409'>want</span> <span m='2070691'>to</span> <span
  m='2070973'>have</span> <span m='2071255'>another</span> <span
  m='2071537'>flight</span> <span m='2071819'>a</span> <span
  m='2072101'>little</span> <span m='2072383'>later</span> <span
  m='2072666'>in</span> <span m='2073125'>the</span> <span
  m='2073585'>day</span> <span m='2074045'>that</span> <span
  m='2074504'>flies</span> <span m='2074964'>from</span> <span
  m='2075424'>Boston</span> <span m='2075883'>to</span> <span
  m='2076343'>JFK.</span> </p><p><span m='2079606'>And</span> <span
  m='2079781'>a</span> <span m='2079957'>little</span> <span
  m='2080133'>later</span> <span m='2080309'>than</span> <span
  m='2080485'>that,</span> <span m='2080661'>they</span> <span
  m='2080837'>want</span> <span m='2081013'>to</span> <span
  m='2081189'>have</span> <span m='2081365'>another</span> <span
  m='2081541'>flight</span> <span m='2082289'>that</span> <span
  m='2083037'>goes</span> <span m='2083786'>from</span> <span
  m='2084534'>JFK</span> <span m='2085283'>to</span> <span
  m='2086031'>Boston.</span> </p><p><span m='2086780'>They're</span> <span
  m='2087019'>going</span> <span m='2087259'>to</span> <span
  m='2087498'>start</span> <span m='2087738'>off</span> <span
  m='2087978'>mostly</span> <span m='2088217'>as</span> <span
  m='2088457'>a</span> <span m='2088697'>shuttle</span> <span
  m='2088936'>airline</span> <span m='2089176'>in</span> <span
  m='2089416'>the</span> <span m='2089649'>beginning.</span> </p><p><span
  m='2089882'>So</span> <span m='2090701'>that's</span> <span
  m='2091521'>F1,</span> <span m='2092341'>F2,</span> <span
  m='2093161'>F3,</span> <span m='2093981'>and</span> <span
  m='2094801'>F4.</span> </p><p><span m='2095621'>And</span> <span
  m='2096038'>they</span> <span m='2096455'>have</span> <span
  m='2096872'>a</span> <span m='2097289'>fifth</span> <span
  m='2097706'>flight,</span> <span m='2098124'>F5,</span> <span
  m='2098541'>that</span> <span m='2098958'>goes</span> <span
  m='2099375'>from</span> <span m='2099792'>Boston</span> <span
  m='2100209'>to</span> <span m='2100627'>Los</span> <span
  m='2101079'>Angeles,</span> <span m='2101532'>that</span> <span
  m='2101985'>takes</span> <span m='2102438'>a</span> <span
  m='2102891'>long</span> <span m='2103344'>time.</span> </p><p><span
  m='2103797'>So</span> <span m='2104151'>it</span> <span
  m='2104506'>looks</span> <span m='2104860'>like</span> <span
  m='2105215'>this</span> <span m='2105569'>on</span> <span
  m='2105924'>the</span> <span m='2106278'>schedule.</span> </p><p><span
  m='2106633'>Of</span> <span m='2106945'>course</span> <span
  m='2107258'>we</span> <span m='2107571'>have</span> <span
  m='2107884'>time</span> <span m='2108197'>going</span> <span
  m='2108510'>that</span> <span m='2108823'>way.</span> </p><p><span
  m='2109136'>So</span> <span m='2109810'>that's</span> <span
  m='2110484'>Boston</span> <span m='2111158'>to</span> <span
  m='2111832'>LAX.</span> </p><p><span m='2116043'>Now</span> <span
  m='2116546'>your</span> <span m='2117049'>job</span> <span
  m='2117552'>is</span> <span m='2118056'>to</span> <span
  m='2118559'>determine</span> <span m='2119062'>if</span> <span
  m='2119565'>they</span> <span m='2120069'>can</span> <span
  m='2120572'>fly</span> <span m='2121075'>this</span> <span
  m='2121578'>schedule</span> <span m='2122082'>with</span> <span
  m='2122994'>four</span> <span m='2123906'>aircraft?</span> </p><p><span
  m='2124818'>And</span> <span m='2125039'>naturally</span> <span
  m='2125260'>you</span> <span m='2125482'>don't</span> <span
  m='2125703'>want</span> <span m='2125925'>to</span> <span
  m='2126146'>over</span> <span m='2126368'>use</span> <span
  m='2126589'>any</span> <span m='2126811'>one</span> <span
  m='2127032'>aircraft,</span> <span m='2127254'>because</span> <span
  m='2127557'>you</span> <span m='2127861'>would</span> <span
  m='2128164'>like</span> <span m='2128468'>to</span> <span
  m='2128772'>have</span> <span m='2129075'>even</span> <span
  m='2129379'>wear</span> <span m='2129682'>on</span> <span
  m='2129986'>them.</span> </p><p><span m='2130290'>Right?</span> </p><p><span
  m='2131058'>So</span> <span m='2131478'>as</span> <span m='2131898'>you</span>
  <span m='2132319'>make</span> <span m='2132739'>your</span> <span
  m='2133160'>choices,</span> <span m='2133580'>you'll</span> <span
  m='2134000'>rotate</span> <span m='2134421'>the</span> <span
  m='2134841'>aircraft.</span> </p><p><span m='2135262'>So</span> <span
  m='2135723'>you'll</span> <span m='2136184'>assign</span> <span
  m='2136645'>to</span> <span m='2137106'>this</span> <span
  m='2137567'>one</span> <span m='2138028'>to</span> <span
  m='2138489'>A1,</span> <span m='2138950'>aircraft</span> <span
  m='2139411'>number</span> <span m='2139872'>one.</span> </p><p><span
  m='2140333'>This</span> <span m='2140733'>one</span> <span
  m='2141133'>will</span> <span m='2141534'>be</span> <span
  m='2141934'>A2.</span> </p><p><span m='2142335'>This</span> <span
  m='2142782'>one</span> <span m='2143229'>will</span> <span
  m='2143676'>be</span> <span m='2144123'>A3.</span> </p><p><span
  m='2144571'>And</span> <span m='2145032'>this</span> <span
  m='2145494'>one</span> <span m='2145955'>will</span> <span
  m='2146417'>be</span> <span m='2146878'>A4.</span> </p><p><span
  m='2147340'>And,</span> <span m='2147725'>oops,</span> <span
  m='2148110'>there's</span> <span m='2148495'>no</span> <span
  m='2148881'>aircraft</span> <span m='2149266'>left</span> <span
  m='2149651'>for</span> <span m='2150036'>the</span> <span
  m='2150422'>flight</span> <span m='2150807'>to</span> <span
  m='2151192'>Los</span> <span m='2151578'>Angeles,</span> <span
  m='2152056'>because</span> <span m='2152534'>you</span> <span
  m='2153012'>only</span> <span m='2153490'>have</span> <span
  m='2153968'>four.</span> </p><p><span m='2154447'>So,</span> <span
  m='2154739'>it's</span> <span m='2155031'>obvious,</span> <span
  m='2155323'>right?</span> </p><p><span m='2155615'>This</span> <span
  m='2156073'>is</span> <span m='2156531'>100%,</span> <span
  m='2156989'>exactly,</span> <span m='2157447'>the</span> <span
  m='2157905'>map</span> <span m='2158363'>coloring</span> <span
  m='2158821'>problem,</span> <span m='2159279'>even</span> <span
  m='2159737'>down</span> <span m='2160195'>to</span> <span
  m='2160654'>the</span> <span m='2161299'>four</span> <span
  m='2161944'>choices.</span> </p><p><span m='2162589'>Because,</span> <span
  m='2163043'>you</span> <span m='2163498'>have</span> <span
  m='2163952'>the</span> <span m='2164407'>constraint,</span> <span
  m='2164862'>the</span> <span m='2165316'>no</span> <span
  m='2165771'>single</span> <span m='2166226'>physical</span> <span
  m='2166753'>aircraft</span> <span m='2167280'>can</span> <span
  m='2167807'>fly</span> <span m='2168334'>two</span> <span
  m='2168862'>flights</span> <span m='2169389'>at</span> <span
  m='2169916'>the</span> <span m='2170443'>same</span> <span
  m='2170970'>time.</span> </p><p><span m='2171498'>Just</span> <span
  m='2171726'>like</span> <span m='2171955'>no</span> <span
  m='2172184'>two</span> <span m='2172412'>adjacent</span> <span
  m='2172641'>states</span> <span m='2172870'>can</span> <span
  m='2173099'>be</span> <span m='2173574'>colored</span> <span
  m='2174050'>the</span> <span m='2174525'>same.</span> </p><p><span
  m='2175001'>So</span> <span m='2175579'>there's</span> <span
  m='2176157'>a</span> <span m='2176736'>no</span> <span m='2177314'>same</span>
  <span m='2177893'>time</span> <span m='2178471'>constraint,</span> <span
  m='2179050'>like</span> <span m='2179628'>so.</span> </p><p><span
  m='2187380'>So</span> <span m='2187823'>if</span> <span m='2188267'>you</span>
  <span m='2188711'>were</span> <span m='2189155'>assigning</span> <span
  m='2189599'>aircraft</span> <span m='2190042'>to</span> <span
  m='2190486'>these</span> <span m='2190930'>flights,</span> <span
  m='2191374'>you</span> <span m='2191818'>would</span> <span
  m='2192130'>get</span> <span m='2192442'>down</span> <span
  m='2192755'>to</span> <span m='2193067'>F4,</span> <span
  m='2193380'>the</span> <span m='2193692'>fourth</span> <span
  m='2194005'>flight,</span> <span m='2194317'>and</span> <span
  m='2194630'>you</span> <span m='2194942'>would</span> <span
  m='2195255'>say,</span> <span m='2195878'>well,</span> <span
  m='2196502'>let's</span> <span m='2197126'>see,</span> <span
  m='2197750'>this</span> <span m='2198374'>guy</span> <span
  m='2198998'>down</span> <span m='2199622'>here</span> <span
  m='2200246'>can</span> <span m='2200870'>be</span> <span
  m='2201494'>A1,</span> <span m='2201747'>A2,</span> <span
  m='2202001'>A3,</span> <span m='2202254'>or</span> <span
  m='2202508'>A4.</span> </p><p><span m='2202762'>But</span> <span
  m='2203047'>if</span> <span m='2203332'>I</span> <span
  m='2203617'>choose</span> <span m='2203902'>A4</span> <span
  m='2204187'>for</span> <span m='2204473'>that</span> <span
  m='2204758'>fourth</span> <span m='2205043'>flight,</span> <span
  m='2205328'>then</span> <span m='2205613'>there</span> <span
  m='2205899'>would</span> <span m='2206447'>be</span> <span
  m='2206995'>nothing</span> <span m='2207543'>left</span> <span
  m='2208091'>in</span> <span m='2208639'>its</span> <span
  m='2209187'>domain.</span> </p><p><span m='2209736'>So</span> <span
  m='2210282'>you've</span> <span m='2210829'>thus</span> <span
  m='2211376'>set</span> <span m='2211922'>the</span> <span
  m='2212469'>problem</span> <span m='2213016'>up</span> <span
  m='2213562'>to</span> <span m='2214109'>be</span> <span
  m='2214656'>identical</span> <span m='2215202'>to</span> <span
  m='2215749'>the</span> <span m='2216296'>map</span> <span
  m='2216843'>coloring</span> <span m='2217293'>problem.</span> </p><p><span
  m='2217744'>And,</span> <span m='2217977'>of</span> <span
  m='2218211'>course,</span> <span m='2218444'>you</span> <span
  m='2218678'>can</span> <span m='2218911'>enrich</span> <span
  m='2219145'>it</span> <span m='2219378'>with</span> <span
  m='2219612'>other</span> <span m='2219845'>kinds</span> <span
  m='2220079'>of</span> <span m='2220313'>constraints.</span> </p><p><span
  m='2221581'>So,</span> <span m='2221881'>for</span> <span
  m='2222181'>example,</span> <span m='2222482'>you</span> <span
  m='2222782'>might</span> <span m='2223082'>have--</span> <span
  m='2223383'>this</span> <span m='2223640'>is</span> <span m='2223897'>a</span>
  <span m='2224155'>not</span> <span m='2224412'>same</span> <span
  m='2224670'>time</span> <span m='2224927'>constraint--</span> <span
  m='2233226'>and</span> <span m='2233847'>these,</span> <span
  m='2234469'>I</span> <span m='2235090'>mean,</span> <span
  m='2235712'>this</span> <span m='2236333'>is</span> <span
  m='2236955'>at</span> <span m='2237576'>JFK.</span> </p><p><span
  m='2238198'>And</span> <span m='2238549'>it</span> <span
  m='2238901'>flies</span> <span m='2239252'>out</span> <span
  m='2239604'>of</span> <span m='2239956'>JFK,</span> <span
  m='2240307'>so</span> <span m='2240659'>maybe</span> <span
  m='2241010'>you</span> <span m='2241362'>can</span> <span
  m='2241714'>use</span> <span m='2242065'>the</span> <span
  m='2242417'>same</span> <span m='2242769'>aircraft</span> <span
  m='2243136'>for</span> <span m='2243503'>those.</span> </p><p><span
  m='2243870'>But</span> <span m='2244056'>not</span> <span
  m='2244243'>if</span> <span m='2244430'>they're</span> <span
  m='2244617'>right</span> <span m='2244804'>up</span> <span
  m='2244991'>against</span> <span m='2245178'>each</span> <span
  m='2245365'>other,</span> <span m='2245552'>because</span> <span
  m='2245739'>you</span> <span m='2246106'>have</span> <span
  m='2246473'>a</span> <span m='2246840'>minimum</span> <span
  m='2247207'>ground</span> <span m='2247574'>time</span> <span
  m='2247941'>rule.</span> </p><p><span m='2248308'>So</span> <span
  m='2248545'>there's</span> <span m='2248783'>a</span> <span
  m='2249021'>minimum</span> <span m='2249259'>ground</span> <span
  m='2249496'>time</span> <span m='2249734'>constraint</span> <span
  m='2249972'>here.</span> </p><p><span m='2252846'>And</span> <span
  m='2253075'>there's</span> <span m='2253304'>a</span> <span
  m='2253534'>minimum</span> <span m='2253763'>ground</span> <span
  m='2253992'>time</span> <span m='2254222'>constraint</span> <span
  m='2254451'>here.</span> </p><p><span m='2257617'>There's</span> <span
  m='2257874'>a</span> <span m='2258131'>minimum</span> <span
  m='2258389'>ground</span> <span m='2258646'>time</span> <span
  m='2258904'>constraint</span> <span m='2259161'>here.</span> </p><p><span
  m='2264224'>And</span> <span m='2264475'>if</span> <span
  m='2264727'>these</span> <span m='2264978'>are</span> <span
  m='2265230'>at</span> <span m='2265481'>the</span> <span
  m='2265733'>same</span> <span m='2265984'>city,</span> <span
  m='2266236'>then</span> <span m='2266487'>you've</span> <span
  m='2266739'>got</span> <span m='2266990'>to</span> <span
  m='2267242'>allow</span> <span m='2267494'>enough</span> <span
  m='2267694'>time</span> <span m='2267894'>for</span> <span
  m='2268094'>them</span> <span m='2268294'>to</span> <span
  m='2268494'>fly</span> <span m='2268695'>between</span> <span
  m='2268895'>the</span> <span m='2269095'>two</span> <span
  m='2269295'>cities</span> <span m='2269495'>that</span> <span
  m='2269696'>are</span> <span m='2270346'>involved.</span> </p><p><span
  m='2270997'>So</span> <span m='2271197'>the</span> <span
  m='2271397'>constraints</span> <span m='2271597'>can</span> <span
  m='2271797'>get</span> <span m='2271998'>a</span> <span
  m='2272198'>little</span> <span m='2272398'>bit</span> <span
  m='2272598'>more</span> <span m='2272798'>complicated,</span> <span
  m='2272999'>but</span> <span m='2273432'>the</span> <span
  m='2273866'>idea</span> <span m='2274300'>is</span> <span
  m='2274734'>the</span> <span m='2275168'>same.</span> </p><p><span
  m='2275602'>So</span> <span m='2275899'>you</span> <span
  m='2276196'>say</span> <span m='2276493'>to</span> <span
  m='2276791'>me,</span> <span m='2277088'>I</span> <span
  m='2277385'>don't</span> <span m='2277682'>trust</span> <span
  m='2277980'>you,</span> <span m='2278277'>show</span> <span
  m='2278574'>me.</span> </p><p><span m='2278872'>OK.</span> </p><p><span
  m='2279839'>So</span> <span m='2280433'>let</span> <span m='2281027'>me</span>
  <span m='2281621'>show</span> <span m='2282215'>you.</span> </p><p><span
  m='2282809'>Oh,</span> <span m='2282981'>by</span> <span
  m='2283153'>the</span> <span m='2283326'>way,</span> <span
  m='2283498'>there's</span> <span m='2283671'>one</span> <span
  m='2283843'>more</span> <span m='2284015'>way</span> <span
  m='2284188'>to</span> <span m='2284360'>make</span> <span
  m='2284533'>this</span> <span m='2284705'>map</span> <span
  m='2284878'>coloring</span> <span m='2285186'>problem</span> <span
  m='2285495'>easier,</span> <span m='2285803'>right?</span> </p><p><span
  m='2289616'>Let's</span> <span m='2290066'>see.</span> </p><p><span
  m='2290516'>The</span> <span m='2290863'>arrangement</span> <span
  m='2291210'>is</span> <span m='2291557'>going</span> <span
  m='2291904'>to</span> <span m='2292251'>be</span> <span
  m='2292598'>alphabetical,</span> <span m='2292945'>the</span> <span
  m='2293292'>type</span> <span m='2293639'>is</span> <span
  m='2293987'>going</span> <span m='2294460'>to</span> <span
  m='2294933'>be</span> <span m='2295406'>assignments</span> <span
  m='2295879'>only,</span> <span m='2296352'>and</span> <span
  m='2296826'>we</span> <span m='2297299'>know</span> <span
  m='2297772'>that's</span> <span m='2298245'>a</span> <span
  m='2298718'>loser.</span> </p><p><span m='2299192'>But</span> <span
  m='2299755'>not</span> <span m='2300319'>if</span> <span m='2300883'>we</span>
  <span m='2301447'>use</span> <span m='2302011'>a</span> <span
  m='2302575'>whole</span> <span m='2303139'>lot</span> <span
  m='2303703'>of</span> <span m='2304267'>colors.</span> </p><p><span
  m='2304831'>So</span> <span m='2305153'>it's</span> <span
  m='2305476'>the</span> <span m='2305798'>use</span> <span
  m='2306121'>of</span> <span m='2306443'>four</span> <span
  m='2306766'>colors</span> <span m='2307088'>that</span> <span
  m='2307411'>got</span> <span m='2307733'>us</span> <span
  m='2308056'>into</span> <span m='2308378'>trouble.</span> </p><p><span
  m='2308701'>Now</span> <span m='2308927'>that's</span> <span
  m='2309153'>an</span> <span m='2309379'>aside,</span> <span
  m='2309605'>but</span> <span m='2309832'>it'll</span> <span
  m='2310058'>be</span> <span m='2310284'>coming</span> <span
  m='2310510'>back</span> <span m='2310737'>in</span> <span m='2310930'>a</span>
  <span m='2311123'>moment</span> <span m='2311317'>or</span> <span
  m='2311510'>two.</span> </p><p><span m='2311704'>Scheduling,</span> <span
  m='2312563'>here's</span> <span m='2313422'>that</span> <span
  m='2314281'>problem.</span> </p><p><span m='2315141'>Boom.</span> </p><p><span
  m='2317310'>You</span> <span m='2317510'>can</span> <span
  m='2317710'>almost</span> <span m='2317910'>see</span> <span
  m='2318110'>it</span> <span m='2318311'>working</span> <span
  m='2318511'>just</span> <span m='2318711'>like</span> <span
  m='2318911'>the</span> <span m='2319112'>map</span> <span
  m='2319679'>coloring</span> <span m='2320246'>thing.</span> </p><p><span
  m='2320813'>But</span> <span m='2321480'>that's</span> <span
  m='2322147'>maybe</span> <span m='2322815'>too</span> <span
  m='2323482'>easy.</span> </p><p><span m='2324150'>Let's</span> <span
  m='2324458'>do</span> <span m='2324767'>this</span> <span
  m='2325076'>one.</span> </p><p><span m='2329055'>See</span> <span
  m='2329447'>this</span> <span m='2329839'>is</span> <span
  m='2330231'>just</span> <span m='2330623'>like</span> <span
  m='2331015'>[?</span> <span m='2331407'>simplicia.</span> <span
  m='2331799'>?]</span> </p><p><span m='2332191'>We've</span> <span
  m='2332580'>kind</span> <span m='2332969'>of</span> <span
  m='2333359'>got</span> <span m='2333748'>a</span> <span
  m='2334137'>goofy</span> <span m='2334527'>arrangement</span> <span
  m='2334916'>here</span> <span m='2335305'>that's</span> <span
  m='2335695'>guaranteed</span> <span m='2336022'>to</span> <span
  m='2336349'>lose</span> <span m='2336676'>at</span> <span
  m='2337003'>the</span> <span m='2337330'>bottom</span> <span
  m='2337657'>because</span> <span m='2337984'>of</span> <span
  m='2338311'>choices</span> <span m='2338638'>made</span> <span
  m='2338965'>at</span> <span m='2339610'>the</span> <span
  m='2340255'>top.</span> </p><p><span m='2340900'>But</span> <span
  m='2341244'>that's</span> <span m='2341589'>OK.</span> </p><p><span
  m='2341934'>We</span> <span m='2342367'>can</span> <span
  m='2342801'>that</span> <span m='2343235'>we</span> <span
  m='2343669'>can</span> <span m='2344102'>stop</span> <span
  m='2344536'>this,</span> <span m='2344970'>and</span> <span
  m='2345404'>we</span> <span m='2345837'>can</span> <span
  m='2346271'>change</span> <span m='2346705'>to</span> <span
  m='2347139'>check</span> <span m='2347573'>neighbors</span> <span
  m='2348607'>only.</span> </p><p><span m='2349642'>And</span> <span
  m='2349889'>boom,</span> <span m='2350136'>there</span> <span
  m='2350383'>it</span> <span m='2350630'>goes.</span> </p><p><span
  m='2354013'>Or</span> <span m='2354213'>alternatively,</span> <span
  m='2354413'>let</span> <span m='2354613'>me</span> <span
  m='2354814'>see</span> <span m='2355014'>if</span> <span m='2355214'>I</span>
  <span m='2355414'>can</span> <span m='2355615'>do</span> <span
  m='2355815'>it</span> <span m='2356015'>this</span> <span
  m='2356215'>way.</span> </p><p><span m='2356416'>Most</span> <span
  m='2356983'>constrained</span> <span m='2357550'>first,</span> <span
  m='2358117'>type</span> <span m='2358684'>will</span> <span
  m='2359251'>be</span> <span m='2359818'>assignments</span> <span
  m='2360385'>only.</span> </p><p><span m='2360953'>Boom.</span> </p><p><span
  m='2363423'>That</span> <span m='2363731'>worked</span> <span
  m='2364040'>fine,</span> <span m='2364348'>too.</span> </p><p><span
  m='2366959'>So</span> <span m='2367233'>you</span> <span
  m='2367507'>might</span> <span m='2367782'>choose</span> <span
  m='2368056'>to</span> <span m='2368330'>have</span> <span m='2368605'>a</span>
  <span m='2368879'>slightly</span> <span m='2369153'>harder</span> <span
  m='2369428'>problem,</span> <span m='2370651'>like</span> <span
  m='2371875'>this.</span> </p><p><span m='2373099'>And</span> <span
  m='2373632'>we</span> <span m='2374166'>can</span> <span
  m='2374700'>search</span> <span m='2375234'>away.</span> </p><p><span
  m='2380573'>Actually</span> <span m='2380776'>I</span> <span
  m='2380980'>don't</span> <span m='2381183'>know</span> <span
  m='2381387'>if</span> <span m='2381590'>this</span> <span
  m='2381794'>will</span> <span m='2381997'>complete</span> <span
  m='2382201'>or</span> <span m='2382404'>not.</span> </p><p><span
  m='2382608'>This</span> <span m='2383203'>is</span> <span m='2383798'>a</span>
  <span m='2384393'>randomly</span> <span m='2384988'>generated</span> <span
  m='2385583'>example.</span> </p><p><span m='2386179'>But</span> <span
  m='2386434'>you're</span> <span m='2386690'>going</span> <span
  m='2386946'>to</span> <span m='2387202'>lose</span> <span
  m='2387457'>your</span> <span m='2387713'>summer</span> <span
  m='2387969'>job</span> <span m='2388225'>if</span> <span
  m='2388480'>you</span> <span m='2388736'>can't</span> <span
  m='2388992'>figure</span> <span m='2389248'>out</span> <span
  m='2389485'>whether</span> <span m='2389723'>you</span> <span
  m='2389961'>can</span> <span m='2390199'>do</span> <span
  m='2390436'>this,</span> <span m='2390674'>or</span> <span
  m='2390912'>not.</span> </p><p><span m='2391150'>So</span> <span
  m='2391331'>what</span> <span m='2391512'>are</span> <span
  m='2391693'>you</span> <span m='2391874'>going</span> <span
  m='2392055'>to</span> <span m='2392236'>do?</span> </p><p><span
  m='2395388'>[?</span> <span m='2395574'>Elliott,</span> <span
  m='2395761'>?]</span> <span m='2395948'>you</span> <span
  m='2396135'>got</span> <span m='2396322'>any</span> <span
  m='2396508'>thoughts</span> <span m='2396695'>about</span> <span
  m='2396882'>how</span> <span m='2397069'>you're</span> <span
  m='2397256'>going</span> <span m='2397890'>to</span> <span
  m='2398524'>save</span> <span m='2399158'>your</span> <span
  m='2399792'>job?</span> </p><p><span m='2400426'>So</span> <span
  m='2400797'>here's</span> <span m='2401169'>the</span> <span
  m='2401541'>question</span> <span m='2401913'>you've</span> <span
  m='2402285'>been</span> <span m='2402657'>asked.</span> </p><p><span
  m='2403029'>How</span> <span m='2403820'>many</span> <span
  m='2404611'>airplanes</span> <span m='2405402'>does</span> <span
  m='2406194'>Jet</span> <span m='2406985'>Green</span> <span
  m='2407776'>need?</span> </p><p><span m='2408568'>And</span> <span
  m='2408931'>you</span> <span m='2409295'>decide,</span> <span
  m='2409658'>well,</span> <span m='2410022'>four</span> <span
  m='2410386'>seemed</span> <span m='2410749'>to</span> <span
  m='2411113'>work</span> <span m='2411476'>before,</span> <span
  m='2411840'>so</span> <span m='2412204'>we'll</span> <span
  m='2412704'>try</span> <span m='2413205'>four</span> <span
  m='2413705'>here.</span> </p><p><span m='2414206'>You're</span> <span
  m='2414453'>not</span> <span m='2414701'>sure</span> <span
  m='2414948'>if</span> <span m='2415196'>it's</span> <span
  m='2415443'>going</span> <span m='2415691'>to</span> <span
  m='2415938'>terminate</span> <span m='2416186'>or</span> <span
  m='2416433'>not,</span> <span m='2416681'>I</span> <span
  m='2416928'>mean,</span> <span m='2417176'>in</span> <span
  m='2417531'>your</span> <span m='2417887'>lifetime,</span> <span
  m='2418243'>let</span> <span m='2418599'>alone</span> <span
  m='2418955'>in</span> <span m='2419311'>your</span> <span
  m='2419667'>summer</span> <span m='2420023'>job.</span> </p><p><span
  m='2424951'>[?</span> <span m='2425188'>Elliott,</span> <span
  m='2425425'>?]</span> <span m='2425662'>let</span> <span m='2425899'>me</span>
  <span m='2426137'>give</span> <span m='2426374'>you</span> <span
  m='2426611'>a</span> <span m='2426848'>hint.</span> </p><p><span
  m='2427086'>Look</span> <span m='2427403'>at</span> <span
  m='2427720'>the</span> <span m='2428037'>outline.</span> </p><p><span
  m='2430323'>The</span> <span m='2430673'>outline</span> <span
  m='2431023'>up</span> <span m='2431373'>here,</span> <span
  m='2431724'>on</span> <span m='2432074'>the</span> <span
  m='2432424'>board,</span> <span m='2432775'>the</span> <span
  m='2433125'>last</span> <span m='2433475'>item.</span> </p><p><span
  m='2433826'>[?</span> <span m='2434068'>ELLIOTT:</span> <span
  m='2434310'>[INAUDIBLE]</span> <span m='2434552'>?]</span> </p><p><span
  m='2434794'>PROF.</span> </p><p><span m='2434860'>PATRICK</span> <span
  m='2435071'>WINSTON:</span> <span m='2435282'>Yeah,</span> <span
  m='2435494'>what's</span> <span m='2435705'>that</span> <span
  m='2435916'>mean?</span> </p><p><span m='2439198'>What's</span> <span
  m='2439535'>the</span> <span m='2439872'>maximum</span> <span
  m='2440209'>number</span> <span m='2440546'>of</span> <span
  m='2440883'>airplanes</span> <span m='2441220'>we're</span> <span
  m='2441557'>going</span> <span m='2441894'>to</span> <span
  m='2442231'>need?</span> </p><p><span m='2442568'>Suppose</span> <span
  m='2443143'>we've</span> <span m='2443719'>got</span> <span
  m='2444294'>five</span> <span m='2444870'>flights,</span> <span
  m='2445446'>what's</span> <span m='2446021'>the</span> <span
  m='2446597'>maximum</span> <span m='2447173'>number</span> <span
  m='2447468'>of</span> <span m='2447763'>airplanes</span> <span
  m='2448059'>we</span> <span m='2448354'>would</span> <span
  m='2448650'>ever</span> <span m='2448945'>need?</span> </p><p><span
  m='2449241'>Five.</span> </p><p><span m='2450543'>What's</span> <span
  m='2450876'>the</span> <span m='2451210'>minimum</span> <span
  m='2451543'>number</span> <span m='2451877'>of</span> <span
  m='2452211'>airplanes</span> <span m='2452544'>we'll</span> <span
  m='2452878'>need?</span> </p><p><span m='2453212'>One.</span> </p><p><span
  m='2454947'>So</span> <span m='2455344'>let's</span> <span
  m='2455742'>try</span> <span m='2456140'>it</span> <span
  m='2456537'>with</span> <span m='2456935'>a</span> <span
  m='2457333'>small</span> <span m='2457730'>number</span> <span
  m='2458128'>of</span> <span m='2458526'>airplanes</span> <span
  m='2458923'>and</span> <span m='2459321'>a</span> <span
  m='2459719'>large</span> <span m='2460027'>number</span> <span
  m='2460336'>of</span> <span m='2460644'>airplanes.</span> </p><p><span
  m='2467593'>So</span> <span m='2468011'>that</span> <span
  m='2468430'>showed</span> <span m='2468849'>us</span> <span
  m='2469268'>very</span> <span m='2469687'>fast</span> <span
  m='2470106'>that</span> <span m='2470525'>we</span> <span
  m='2470944'>can't</span> <span m='2471363'>do</span> <span
  m='2471616'>it</span> <span m='2471870'>with</span> <span
  m='2472123'>one</span> <span m='2472377'>airplane.</span> </p><p><span
  m='2481407'>That</span> <span m='2481793'>showed</span> <span
  m='2482180'>us</span> <span m='2482566'>very</span> <span
  m='2482953'>fast</span> <span m='2483339'>we</span> <span
  m='2483726'>can</span> <span m='2484112'>do</span> <span m='2484499'>it</span>
  <span m='2484885'>with</span> <span m='2485272'>ten</span> <span
  m='2485658'>airplanes.</span> </p><p><span m='2486045'>SPEAKER</span> <span
  m='2487023'>1:</span> <span m='2488002'>[INAUDIBLE]</span> </p><p><span
  m='2488981'>amount</span> <span m='2489798'>of</span> <span
  m='2490616'>overlappage</span> <span m='2491433'>from</span> <span
  m='2492251'>up</span> <span m='2493068'>[INAUDIBLE].</span> </p><p><span
  m='2493886'>PROF.</span> </p><p><span m='2493953'>PATRICK</span> <span
  m='2494364'>WINSTON:</span> <span m='2494775'>Volunteer?</span> </p><p><span
  m='2497323'>What</span> <span m='2497573'>are</span> <span
  m='2497823'>we</span> <span m='2498073'>going</span> <span
  m='2498324'>to</span> <span m='2498574'>do</span> <span m='2498824'>to</span>
  <span m='2499074'>find</span> <span m='2499325'>the</span> <span
  m='2499575'>actual</span> <span m='2499825'>number,</span> <span
  m='2500075'>as</span> <span m='2500326'>fast</span> <span
  m='2500637'>as</span> <span m='2500948'>possible.</span> </p><p><span
  m='2501260'>And</span> <span m='2501596'>at</span> <span
  m='2501932'>least</span> <span m='2502269'>give</span> <span
  m='2502605'>our</span> <span m='2502942'>boss</span> <span
  m='2503278'>a</span> <span m='2503614'>reasonable</span> <span
  m='2503951'>answer,</span> <span m='2504287'>even</span> <span
  m='2504624'>if</span> <span m='2504960'>not</span> <span
  m='2505297'>necessarily</span> <span m='2505647'>the</span> <span
  m='2505997'>exact</span> <span m='2506348'>number</span> <span
  m='2506698'>very</span> <span m='2507048'>fast?</span> </p><p><span
  m='2510135'>It's</span> <span m='2510357'>easy,</span> <span
  m='2510580'>right?</span> </p><p><span m='2510803'>We're</span> <span
  m='2511097'>going</span> <span m='2511391'>to</span> <span
  m='2511685'>start</span> <span m='2511979'>up</span> <span
  m='2512273'>here</span> <span m='2512568'>with</span> <span
  m='2512862'>one</span> <span m='2513156'>computer,</span> <span
  m='2513450'>and</span> <span m='2513744'>we're</span> <span
  m='2514039'>going</span> <span m='2514414'>to</span> <span
  m='2514789'>start</span> <span m='2515165'>down</span> <span
  m='2515540'>here</span> <span m='2515915'>with</span> <span
  m='2516291'>another</span> <span m='2516666'>computer,</span> <span
  m='2517042'>and</span> <span m='2517559'>see</span> <span
  m='2518076'>what</span> <span m='2518593'>happens.</span> </p><p><span
  m='2519111'>So</span> <span m='2519347'>let's</span> <span
  m='2519584'>see</span> <span m='2519821'>if</span> <span m='2520058'>we</span>
  <span m='2520295'>can</span> <span m='2520532'>do</span> <span
  m='2520769'>it</span> <span m='2521006'>with</span> <span
  m='2521243'>nine.</span> </p><p><span m='2526452'>Let's</span> <span
  m='2526781'>see</span> <span m='2527111'>if</span> <span m='2527441'>we</span>
  <span m='2527771'>can</span> <span m='2528101'>do</span> <span
  m='2528431'>it</span> <span m='2528761'>with</span> <span
  m='2529091'>eight.</span> </p><p><span m='2533292'>Let's</span> <span
  m='2533625'>see</span> <span m='2533959'>if</span> <span m='2534293'>we</span>
  <span m='2534626'>can</span> <span m='2534960'>do</span> <span
  m='2535294'>it</span> <span m='2535627'>with</span> <span
  m='2535961'>seven.</span> </p><p><span m='2536295'>These</span> <span
  m='2536545'>take</span> <span m='2536795'>almost</span> <span
  m='2537045'>zero</span> <span m='2537295'>time,</span> <span
  m='2537545'>right?</span> </p><p><span m='2537796'>Because</span> <span
  m='2538104'>they're</span> <span m='2538413'>under</span> <span
  m='2538722'>constraint.</span> </p><p><span m='2542901'>Wow,</span> <span
  m='2543251'>that's</span> <span m='2543602'>good,</span> <span
  m='2543952'>seven.</span> </p><p><span m='2544303'>Let's</span> <span
  m='2544870'>try</span> <span m='2545437'>six.</span> </p><p><span
  m='2546005'>Actually</span> <span m='2546313'>let's</span> <span
  m='2546622'>try</span> <span m='2546930'>two.</span> </p><p><span
  m='2550976'>It</span> <span m='2551576'>loses</span> <span
  m='2552177'>fast.</span> </p><p><span m='2552778'>Let's</span> <span
  m='2553189'>try</span> <span m='2553601'>three.</span> </p><p><span
  m='2564056'>I</span> <span m='2564145'>don't</span> <span
  m='2564234'>know.</span> </p><p><span m='2564323'>Maybe</span> <span
  m='2564598'>if</span> <span m='2564873'>you</span> <span
  m='2565148'>let</span> <span m='2565424'>it</span> <span
  m='2565699'>run</span> <span m='2565974'>one</span> <span
  m='2566249'>long</span> <span m='2566525'>enough</span> <span
  m='2566800'>three</span> <span m='2567075'>will</span> <span
  m='2567350'>work.</span> </p><p><span m='2567626'>I</span> <span
  m='2568182'>doubt</span> <span m='2568738'>it.</span> </p><p><span
  m='2569294'>While</span> <span m='2569448'>we're</span> <span
  m='2569602'>at</span> <span m='2569756'>it</span> <span
  m='2569910'>though,</span> <span m='2570064'>we</span> <span
  m='2570218'>might</span> <span m='2570372'>as</span> <span
  m='2570526'>well</span> <span m='2570680'>go</span> <span
  m='2570834'>back</span> <span m='2570988'>here</span> <span
  m='2571142'>and</span> <span m='2571296'>try</span> <span
  m='2571463'>it</span> <span m='2571630'>with</span> <span
  m='2571797'>six.</span> </p><p><span m='2571964'>Remember</span> <span
  m='2572217'>seven</span> <span m='2572471'>worked</span> <span
  m='2572724'>real</span> <span m='2572978'>fast.</span> </p><p><span
  m='2577202'>Gees,</span> <span m='2577619'>six,</span> <span
  m='2578036'>that</span> <span m='2578453'>was</span> <span
  m='2578870'>six,</span> <span m='2579287'>right?</span> </p><p><span
  m='2579705'>Yeah.</span> </p><p><span m='2580072'>So</span> <span
  m='2580277'>let's</span> <span m='2580483'>try</span> <span
  m='2580689'>it</span> <span m='2580894'>with</span> <span
  m='2581100'>five.</span> </p><p><span m='2584843'>OK.</span> </p><p><span
  m='2585144'>So</span> <span m='2585396'>it</span> <span
  m='2585649'>runs</span> <span m='2585901'>real</span> <span
  m='2586154'>fast</span> <span m='2586406'>with</span> <span
  m='2586659'>five.</span> </p><p><span m='2586912'>It</span> <span
  m='2587238'>terminates</span> <span m='2587564'>real</span> <span
  m='2587890'>quick</span> <span m='2588216'>with</span> <span
  m='2588543'>two,</span> <span m='2588869'>so</span> <span
  m='2589195'>we</span> <span m='2589521'>got</span> <span
  m='2589848'>three</span> <span m='2590365'>and</span> <span
  m='2590882'>four</span> <span m='2591399'>left.</span> </p><p><span
  m='2591917'>So</span> <span m='2592270'>we</span> <span
  m='2592623'>could</span> <span m='2592976'>tell</span> <span
  m='2593329'>our</span> <span m='2593682'>boss,</span> <span
  m='2594036'>a</span> <span m='2594389'>la</span> <span m='2594742'>any</span>
  <span m='2595095'>time</span> <span m='2595448'>algorithm,</span> <span
  m='2595801'>that</span> <span m='2596155'>you're</span> <span
  m='2596316'>not</span> <span m='2596477'>real</span> <span
  m='2596638'>sure,</span> <span m='2596800'>but</span> <span
  m='2596961'>you</span> <span m='2597122'>know</span> <span
  m='2597283'>it's</span> <span m='2597445'>going</span> <span
  m='2597606'>to</span> <span m='2597767'>be</span> <span
  m='2597928'>either</span> <span m='2598090'>three</span> <span
  m='2598546'>or</span> <span m='2599002'>four.</span> </p><p><span
  m='2599458'>And</span> <span m='2599791'>then,</span> <span
  m='2600125'>you</span> <span m='2600459'>got</span> <span
  m='2600792'>two</span> <span m='2601126'>computers.</span> </p><p><span
  m='2601460'>You</span> <span m='2601808'>can</span> <span
  m='2602157'>let</span> <span m='2602506'>both</span> <span
  m='2602855'>run</span> <span m='2603204'>and</span> <span
  m='2603552'>see</span> <span m='2603901'>if</span> <span
  m='2604250'>either</span> <span m='2604599'>one</span> <span
  m='2604948'>terminate.</span> </p><p><span m='2605297'>So</span> <span
  m='2605564'>you</span> <span m='2605831'>have</span> <span
  m='2606098'>three</span> <span m='2606365'>and</span> <span
  m='2606632'>four.</span> </p><p><span m='2606899'>My</span> <span
  m='2607392'>guess</span> <span m='2607885'>is</span> <span
  m='2608378'>that</span> <span m='2608871'>three</span> <span
  m='2609364'>will</span> <span m='2609857'>eventually</span> <span
  m='2610350'>give</span> <span m='2610843'>up.</span> </p><p><span
  m='2611336'>But</span> <span m='2611573'>of</span> <span
  m='2611811'>course,</span> <span m='2612049'>there's</span> <span
  m='2612287'>another</span> <span m='2612524'>little</span> <span
  m='2612762'>problem</span> <span m='2613000'>here.</span> </p><p><span
  m='2613238'>We</span> <span m='2613619'>haven't</span> <span
  m='2614000'>used</span> <span m='2614382'>the</span> <span
  m='2614763'>most</span> <span m='2615145'>constraint</span> <span
  m='2615526'>first.</span> </p><p><span m='2615908'>If</span> <span
  m='2616123'>we</span> <span m='2616339'>did</span> <span
  m='2616554'>that,</span> <span m='2616770'>we</span> <span
  m='2616985'>might</span> <span m='2617201'>be</span> <span
  m='2617416'>able</span> <span m='2617632'>to</span> <span
  m='2617847'>do</span> <span m='2618063'>it</span> <span
  m='2618278'>even</span> <span m='2618494'>faster.</span> </p><p><span
  m='2618710'>Actually,</span> <span m='2619020'>I</span> <span
  m='2619330'>don't</span> <span m='2619640'>think</span> <span
  m='2619951'>I</span> <span m='2620261'>can</span> <span
  m='2620571'>make</span> <span m='2620882'>that</span> <span
  m='2621192'>switch</span> <span m='2621502'>without</span> <span
  m='2621813'>getting</span> <span m='2622253'>another</span> <span
  m='2622694'>random</span> <span m='2623134'>assignment,</span> <span
  m='2623575'>but</span> <span m='2624016'>let's</span> <span
  m='2624641'>see</span> <span m='2625267'>what</span> <span
  m='2625892'>happens.</span> </p><p><span m='2626518'>Maybe</span> <span
  m='2627335'>so.</span> </p><p><span m='2628153'>SPEAKER</span> <span
  m='2628575'>2:</span> <span m='2628998'>[INAUDIBLE]</span> </p><p><span
  m='2632391'>PROF.</span> </p><p><span m='2632457'>PATRICK</span> <span
  m='2632649'>WINSTON:</span> <span m='2632842'>Oh,</span> <span
  m='2633035'>I</span> <span m='2633228'>already</span> <span
  m='2633420'>had</span> <span m='2633613'>most</span> <span
  m='2633806'>constraint</span> <span m='2633999'>first?</span> </p><p><span
  m='2634192'>OK.</span> </p><p><span m='2635561'>So</span> <span
  m='2635885'>it</span> <span m='2636209'>didn't</span> <span
  m='2636533'>help</span> <span m='2636857'>to</span> <span
  m='2637181'>actually</span> <span m='2637505'>switch.</span> </p><p><span
  m='2637829'>And</span> <span m='2638111'>I</span> <span
  m='2638393'>think</span> <span m='2638675'>I've</span> <span
  m='2638957'>got</span> <span m='2639239'>a</span> <span m='2639522'>new</span>
  <span m='2639804'>schedule</span> <span m='2640086'>to</span> <span
  m='2640368'>work</span> <span m='2640650'>here.</span> </p><p><span
  m='2640933'>So</span> <span m='2641280'>that's</span> <span
  m='2641628'>the</span> <span m='2641976'>end</span> <span
  m='2642324'>of</span> <span m='2642672'>the</span> <span
  m='2643020'>story.</span> </p><p><span m='2643368'>You</span> <span
  m='2643775'>can</span> <span m='2644182'>do</span> <span
  m='2644589'>good</span> <span m='2644996'>resource</span> <span
  m='2645403'>allocation</span> <span m='2645810'>if</span> <span
  m='2646217'>you</span> <span m='2646624'>do</span> <span
  m='2647031'>several</span> <span m='2647439'>things</span> <span
  m='2647861'>are</span> <span m='2648284'>once.</span> </p><p><span
  m='2648707'>Number</span> <span m='2649000'>one,</span> <span
  m='2649294'>you</span> <span m='2649587'>always</span> <span
  m='2649881'>want</span> <span m='2650175'>to</span> <span
  m='2650468'>use</span> <span m='2650762'>most</span> <span
  m='2651055'>constraint</span> <span m='2651349'>first.</span> </p><p><span
  m='2651643'>Number</span> <span m='2651880'>two</span> <span
  m='2652118'>you</span> <span m='2652356'>want</span> <span
  m='2652594'>to</span> <span m='2652831'>propagate</span> <span
  m='2653069'>through</span> <span m='2653307'>domains</span> <span
  m='2653545'>produced</span> <span m='2653885'>to</span> <span
  m='2654225'>a</span> <span m='2654566'>single</span> <span
  m='2654906'>algorithm.</span> </p><p><span m='2655247'>And</span> <span
  m='2655459'>number</span> <span m='2655671'>three,</span> <span
  m='2655883'>if</span> <span m='2656096'>you</span> <span
  m='2656308'>really</span> <span m='2656520'>try</span> <span
  m='2656732'>to</span> <span m='2656945'>figure</span> <span
  m='2657157'>out</span> <span m='2657369'>what</span> <span
  m='2657582'>the</span> <span m='2657993'>minimum</span> <span
  m='2658405'>number</span> <span m='2658816'>of</span> <span
  m='2659228'>resources</span> <span m='2659639'>needed</span> <span
  m='2660051'>is,</span> <span m='2660462'>you</span> <span
  m='2660874'>do</span> <span m='2661286'>this</span> <span
  m='2661586'>under</span> <span m='2661886'>over</span> <span
  m='2662186'>business</span> <span m='2662487'>and</span> <span
  m='2662787'>you</span> <span m='2663087'>can</span> <span
  m='2663387'>quickly</span> <span m='2663688'>converge</span> <span
  m='2663988'>on</span> <span m='2664288'>a</span> <span
  m='2664589'>narrow</span> <span m='2664850'>range</span> <span
  m='2665111'>where</span> <span m='2665373'>the</span> <span
  m='2665634'>search</span> <span m='2665896'>is</span> <span
  m='2666157'>taking</span> <span m='2666418'>a</span> <span
  m='2666680'>long</span> <span m='2666941'>time,</span> <span
  m='2667203'>and</span> <span m='2667464'>be</span> <span
  m='2667726'>sure</span> <span m='2668197'>that</span> <span
  m='2668668'>it</span> <span m='2669139'>lies</span> <span
  m='2669611'>within</span> <span m='2670082'>that</span> <span
  m='2670553'>narrow</span> <span m='2671024'>range.</span> </p><p><span
  m='2671496'>Because</span> <span m='2671871'>when</span> <span
  m='2672246'>you</span> <span m='2672622'>over</span> <span
  m='2672997'>resource,</span> <span m='2673372'>it's</span> <span
  m='2673748'>fast</span> <span m='2674123'>to</span> <span
  m='2674499'>complete,</span> <span m='2674893'>and</span> <span
  m='2675288'>when</span> <span m='2675683'>you</span> <span
  m='2676078'>under</span> <span m='2676473'>resource,</span> <span
  m='2676868'>it's</span> <span m='2677493'>fast</span> <span
  m='2678119'>to</span> <span m='2678745'>terminate.</span> </p><p><span
  m='2679371'>So</span> <span m='2679593'>you</span> <span
  m='2679815'>can</span> <span m='2680038'>just</span> <span
  m='2680260'>squeeze</span> <span m='2680483'>it</span> <span
  m='2680705'>right</span> <span m='2680928'>down</span> <span
  m='2681150'>into</span> <span m='2681373'>a</span> <span
  m='2681731'>very</span> <span m='2682090'>small</span> <span
  m='2682449'>range.</span> </p><p><span m='2682808'>And</span> <span
  m='2683016'>that</span> <span m='2683225'>is</span> <span
  m='2683433'>the</span> <span m='2683642'>end</span> <span
  m='2683850'>of</span> <span m='2684059'>the</span> <span
  m='2684267'>story.</span> </p><p><span m='2684476'>Enjoy</span> <span
  m='2684763'>your</span> <span m='2685050'>holiday</span> <span
  m='2685337'>on</span> <span m='2685624'>Monday.</span> </p><p><span
  m='2685911'>We'll</span> <span m='2686404'>have</span> <span
  m='2686898'>two</span> <span m='2687392'>classes</span> <span
  m='2687886'>next</span> <span m='2688380'>week</span> <span
  m='2688873'>on</span> <span m='2689367'>Wednesday</span> <span
  m='2689861'>and</span> <span m='2690355'>Friday,</span> <span
  m='2690849'>as</span> <span m='2691483'>advertised.</span> </p>
embedded_media:
  - uid: aa12abb5e2c8feb03dc4e42fbf5f1e78
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: dARl_gGrS4o
  - uid: 7ad9bdf3b7a74a70cc81f7fcda1898b4
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      https://podcasts.apple.com/us/podcast/lecture-8-constraints-search-domain-reduction/id765641080?i=1000194470752
  - uid: 2a60201f4eaee49d452116ca6b748e5f
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MIT6.034F10/MIT6_034F10_lec08_300k.mp4'
  - uid: 891c3d9e5d12816d252ddd55b26614af
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: dARl_gGrS4o
  - uid: 77cbe7affb7d3ec4a3e05e307c771f6e
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/dARl_gGrS4o/default.jpg'
  - uid: 075f0b54d551705535879060e839c321
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: dARl_gGrS4o.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-034-artificial-intelligence-fall-2010/075f0b54d551705535879060e839c321_dARl_gGrS4o.srt
  - uid: d12314b2344fb2bd8c0e139ae1374726
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: dARl_gGrS4o.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-034-artificial-intelligence-fall-2010/d12314b2344fb2bd8c0e139ae1374726_dARl_gGrS4o.pdf
  - uid: b94c061ee0a80709033576ca3b144641
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Caption-3Play YouTube id-SRT_1
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 74cdc3a1cc0181300a7b31fe01c18a99
    parent_uid: ee1eaf7d3728b0c47e7f2c98261083f4
    id: Transcript-3Play YouTube id-PDF_1
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: 6-034-artificial-intelligence-fall-2010
type: course
layout: video
---
