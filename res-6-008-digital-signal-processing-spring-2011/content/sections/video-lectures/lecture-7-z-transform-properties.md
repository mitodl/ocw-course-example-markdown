---
order_index: null
title: 'Lecture 7: z-Transform Properties'
template_type: Tabbed
uid: e942e4e281ec1133760bc5a48de2d8eb
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-7-z-transform-properties
short_url: lecture-7-z-transform-properties
inline_embed_id: '25384573lecture7:z-transformproperties10768770'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Geometric determination of frequency
  response from pole-zero patterns in the z-plane, properties of z-transforms:
  Scaling, differentiation, shifting, and convolution, examples of proof of
  properties of z-transforms.</p> <p><strong>Instructor:</strong> Prof. Alan V.
  Oppenheim</p>
related_resources_text: >-
  <p>z-Transform Properties (<img src="/images/inacessible.gif" alt="This
  resource may not render correctly in a screen reader." /><a
  href="./resolveuid/f210dca6daf177fd71b4dcd2dba8b7a6">PDF</a>)</p>
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
  m='25516'>[MUSIC PLAYING]</span> </p><p></p><p><span m='55772'>ALAN
  OPPENHEIM:</span> <span m='56020'>Hi.</span> <span m='57770'>In</span> <span
  m='57860'>this</span> <span m='58070'>lecture,</span> <span
  m='58970'>there</span> <span m='59420'>are</span> <span m='60200'>two</span>
  <span m='60380'>sets</span> <span m='60680'>of</span> <span
  m='60800'>ideas</span> <span m='61670'>that</span> <span m='62000'>I'd</span>
  <span m='62150'>like</span> <span m='62330'>to</span> <span
  m='62450'>discuss,</span> <span m='63470'>both</span> <span
  m='63770'>of</span> <span m='63890'>which</span> <span m='64790'>are</span>
  <span m='65030'>related</span> <span m='65870'>to</span> <span
  m='66860'>our</span> <span m='66980'>topic</span> <span m='67490'>of</span>
  <span m='67580'>the</span> <span m='67670'>last</span> <span
  m='67970'>several</span> <span m='68300'>lectures,</span> <span
  m='68810'>namely,</span> <span m='69200'>the</span> <span
  m='69320'>Z-transform.</span> <span m='71540'>The</span> <span
  m='71630'>first</span> <span m='71900'>topic</span> <span
  m='72680'>that</span> <span m='73910'>we</span> <span m='74060'>will</span>
  <span m='74210'>focus</span> <span m='74690'>on</span> <span
  m='75290'>is</span> <span m='76340'>what</span> <span m='76580'>I'll</span>
  <span m='76670'>referred</span> <span m='77090'>to</span> <span
  m='77630'>as</span> <span m='78440'>the</span> <span
  m='78860'>geometric</span> <span m='79640'>interpretation</span> <span
  m='80840'>of</span> <span m='81230'>the</span> <span
  m='81320'>frequency</span> <span m='81860'>response.</span> <span
  m='83330'>Now,</span> <span m='84620'>you</span> <span m='84750'>recall</span>
  <span m='85520'>that</span> <span m='86000'>in</span> <span
  m='86150'>lecture</span> <span m='86480'>5</span> <span m='87260'>when</span>
  <span m='87650'>I</span> <span m='87800'>introduced</span> <span
  m='88320'>the</span> <span m='88430'>Z-transform,</span> <span
  m='90920'>we</span> <span m='91670'>observed</span> <span m='92210'>the</span>
  <span m='92300'>relationship</span> <span m='93350'>between</span> <span
  m='94070'>the</span> <span m='94220'>Z-transform</span> <span
  m='95480'>and</span> <span m='95630'>the</span> <span m='95720'>Fourier</span>
  <span m='96140'>transform.</span> <span m='97760'>The</span> <span
  m='97850'>notion</span> <span m='98390'>behind</span> <span
  m='98870'>the</span> <span m='99020'>geometric</span> <span
  m='99590'>interpretation</span> <span m='100550'>of</span> <span
  m='100700'>the</span> <span m='100790'>frequency</span> <span
  m='101330'>response</span> <span m='102710'>is</span> <span
  m='103340'>to</span> <span m='103760'>relate,</span> <span
  m='105140'>in</span> <span m='105290'>terms</span> <span m='105830'>of</span>
  <span m='106010'>a</span> <span m='106040'>geometric</span> <span
  m='106670'>picture,</span> <span m='107870'>the</span> <span
  m='108830'>rough</span> <span m='109130'>characteristics</span> <span
  m='110330'>of</span> <span m='110660'>the</span> <span
  m='110750'>frequency</span> <span m='111290'>response</span> <span
  m='111980'>of</span> <span m='112100'>a</span> <span m='112160'>system</span>
  <span m='113300'>and</span> <span m='113870'>the</span> <span
  m='113990'>pole-zero</span> <span m='114680'>pattern</span> <span
  m='115280'>for</span> <span m='115610'>the</span> <span
  m='115730'>system</span> <span m='116120'>function</span> <span
  m='116720'>for</span> <span m='116870'>the</span> <span
  m='116990'>system.</span> </p><p><span m='118650'>The</span> <span
  m='118670'>second</span> <span m='119450'>topic</span> <span
  m='120080'>that</span> <span m='120410'>we'll</span> <span
  m='120590'>focus</span> <span m='121070'>on</span> <span m='121580'>and</span>
  <span m='122030'>eventually</span> <span m='122570'>tie</span> <span
  m='122870'>back</span> <span m='123320'>into</span> <span
  m='123590'>this</span> <span m='123770'>geometric</span> <span
  m='124340'>interpretation</span> <span m='125870'>is</span> <span
  m='126680'>the</span> <span m='127310'>general</span> <span
  m='128419'>issue</span> <span m='129020'>of</span> <span
  m='131110'>some</span> <span m='131420'>of</span> <span m='131510'>the</span>
  <span m='131630'>properties</span> <span m='132410'>of</span> <span
  m='132860'>the Z-transform.</span> <span m='134420'>And</span> <span
  m='134720'>we'll</span> <span m='134900'>illustrate</span> <span
  m='135650'>some</span> <span m='135920'>of</span> <span
  m='136010'>these</span> <span m='136220'>properties</span> <span
  m='136850'>with</span> <span m='136970'>some</span> <span
  m='137180'>examples.</span> <span m='139010'>But</span> <span
  m='139490'>first</span> <span m='139850'>of</span> <span
  m='139970'>all,</span> <span m='140580'>let's</span> <span
  m='140930'>turn</span> <span m='141200'>our</span> <span
  m='141320'>attention</span> <span m='142160'>to</span> <span
  m='142760'>the</span> <span m='142880'>subject</span> <span
  m='143510'>of</span> <span m='143990'>the</span> <span
  m='144230'>geometric</span> <span m='145250'>interpretation</span> <span
  m='146240'>of</span> <span m='146360'>the</span> <span
  m='146450'>frequency</span> <span m='146990'>response.</span> <span
  m='148880'>And</span> <span m='149510'>let</span> <span m='149720'>me</span>
  <span m='149870'>begin</span> <span m='151220'>by</span> <span
  m='151910'>reminding</span> <span m='152540'>you</span> <span
  m='153680'>of</span> <span m='154430'>one</span> <span m='155030'>of</span>
  <span m='155390'>the</span> <span m='155480'>important</span> <span
  m='156080'>properties</span> <span m='157130'>of</span> <span
  m='158120'>the</span> <span m='158600'>Z-transform</span> <span
  m='160280'>for</span> <span m='160670'>a</span> <span m='160730'>linear</span>
  <span m='161120'>shift</span> <span m='161700'>invariant</span> <span
  m='162020'>system,</span> <span m='163380'>namely</span> <span
  m='163910'>the</span> <span m='164030'>fact</span> <span
  m='164870'>that</span> <span m='165440'>if</span> <span m='165680'>we</span>
  <span m='165830'>have</span> <span m='166010'>a</span> <span
  m='166070'>linear</span> <span m='166730'>shift</span> <span
  m='167150'>invariant</span> <span m='167600'>system</span> <span
  m='169310'>with</span> <span m='169850'>a</span> <span m='169910'>unit</span>
  <span m='170240'>sample</span> <span m='170690'>response,</span> <span
  m='171320'>H</span> <span m='171590'>of</span> <span m='171710'>n,</span>
  <span m='172700'>input</span> <span m='173360'>x</span> <span
  m='173690'>of</span> <span m='173840'>n,</span> <span m='174290'>and</span>
  <span m='174950'>output</span> <span m='175400'>y</span> <span
  m='175730'>of</span> <span m='175890'>n,</span> <span m='177020'>then</span>
  <span m='177380'>of</span> <span m='177530'>course,</span> <span
  m='178100'>y</span> <span m='178390'>of</span> <span m='178500'>n</span> <span
  m='178700'>is</span> <span m='178790'>the</span> <span
  m='178910'>convolution</span> <span m='179900'>of</span> <span
  m='180020'>H</span> <span m='180260'>of</span> <span m='180380'>n</span> <span
  m='180560'>with</span> <span m='180680'>x</span> <span m='181000'>of</span>
  <span m='181500'>n.</span> <span m='182120'>And</span> <span
  m='182990'>the</span> <span m='183140'>Z-transform</span> <span
  m='184220'>of</span> <span m='184310'>the</span> <span
  m='184490'>output</span> <span m='185420'>is</span> <span
  m='185630'>the</span> <span m='185750'>product</span> <span
  m='186350'>of</span> <span m='186530'>the Z-transform</span> <span
  m='187610'>of</span> <span m='187760'>the</span> <span m='187910'>input</span>
  <span m='188720'>and</span> <span m='188990'>H</span> <span
  m='189320'>of</span> <span m='189440'>Z,</span> <span m='190240'>the</span>
  <span m='190340'>Z-transform</span> <span m='191390'>of</span> <span
  m='191540'>the</span> <span m='191630'>unit</span> <span
  m='191930'>sample</span> <span m='192320'>response,</span> <span
  m='193500'>which</span> <span m='193730'>is</span> <span
  m='194210'>what</span> <span m='194420'>we've</span> <span
  m='194630'>been</span> <span m='194780'>referring</span> <span
  m='195260'>to</span> <span m='195410'>as</span> <span m='195530'>the</span>
  <span m='195620'>system</span> <span m='196010'>function.</span> </p><p><span
  m='198090'>And</span> <span m='199050'>in</span> <span m='200780'>first</span>
  <span m='201090'>developing</span> <span m='201720'>the</span> <span
  m='201810'>Z-transform,</span> <span m='203070'>we</span> <span
  m='203340'>tie</span> <span m='203670'>together</span> <span
  m='204870'>the</span> <span m='205110'>notion</span> <span
  m='205620'>of</span> <span m='205710'>the Z-transform</span> <span
  m='206740'>and</span> <span m='206850'>the</span> <span
  m='206950'>Fourier</span> <span m='207420'>transform,</span> <span
  m='208750'>in</span> <span m='208770'>particular,</span> <span
  m='209580'>the</span> <span m='209850'>important</span> <span
  m='210360'>interpretation</span> <span m='211920'>that</span> <span
  m='212460'>the</span> <span m='212580'>Fourier</span> <span
  m='213090'>transform</span> <span m='214050'>is</span> <span
  m='214740'>the</span> <span m='214860'>Z-transform</span> <span
  m='216360'>evaluated</span> <span m='217200'>on</span> <span
  m='217380'>the</span> <span m='217470'>unit</span> <span
  m='217770'>circle.</span> <span m='218740'>So</span> <span
  m='220080'>in</span> <span m='220230'>terms</span> <span m='220770'>of</span>
  <span m='221280'>the</span> <span m='221400'>system</span> <span
  m='221820'>function</span> <span m='222390'>H</span> <span
  m='222690'>of</span> <span m='222780'>z,</span> <span m='224070'>if</span>
  <span m='224250'>we</span> <span m='224400'>evaluate</span> <span
  m='225090'>that</span> <span m='225540'>on</span> <span m='225720'>the</span>
  <span m='225840'>unit</span> <span m='226140'>circle</span> <span
  m='228160'>for</span> <span m='229030'>z</span> <span m='230230'>equal</span>
  <span m='230590'>to</span> <span m='230910'>e</span> <span
  m='231010'>to</span> <span m='231160'>the</span> <span m='231280'>j</span>
  <span m='231550'>omega,</span> <span m='232960'>the</span> <span
  m='233050'>result</span> <span m='233800'>is</span> <span
  m='234040'>the</span> <span m='234160'>frequency</span> <span
  m='234730'>response</span> <span m='235300'>of</span> <span
  m='235390'>the</span> <span m='235480'>system,</span> <span m='237430'>H of
  e</span> <span m='237715'>to</span> <span m='238000'>the</span> <span
  m='238090'>j</span> <span m='238330'>omega.</span> <span
  m='239530'>Simply</span> <span m='239950'>a</span> <span
  m='240010'>statement</span> <span m='240490'>that</span> <span
  m='240610'>the</span> <span m='240700'>Z-transform</span> <span
  m='241720'>evaluated</span> <span m='242470'>on</span> <span
  m='242590'>the</span> <span m='242650'>unit</span> <span
  m='242950'>circle</span> <span m='243820'>is</span> <span
  m='243940'>the</span> <span m='244060'>frequency</span> <span
  m='244540'>response</span> <span m='245050'>of</span> <span
  m='245140'>the</span> <span m='245200'>system.</span> </p><p><span
  m='247130'>Well,</span> <span m='247550'>in</span> <span
  m='247700'>terms</span> <span m='248330'>of</span> <span m='249460'>a</span>
  <span m='249530'>simple</span> <span m='249920'>example,</span> <span
  m='251090'>we</span> <span m='251240'>drag</span> <span m='251630'>out</span>
  <span m='252020'>our</span> <span m='252200'>usual</span> <span
  m='252830'>simple</span> <span m='253220'>example.</span> <span
  m='255270'>The</span> <span m='255370'>system</span> <span
  m='255650'>function</span> <span m='256339'>is</span> <span
  m='256820'>1</span> <span m='257120'>over</span> <span m='257360'>1</span>
  <span m='257570'>minus</span> <span m='257990'>az</span> <span
  m='258709'>to</span> <span m='258860'>the</span> <span m='258950'>minus</span>
  <span m='259370'>1</span> <span m='260269'>or</span> <span m='261019'>z</span>
  <span m='261620'>divided</span> <span m='262130'>by</span> <span
  m='262340'>z</span> <span m='262550'>minus</span> <span m='262890'>a.</span>
  <span m='264880'>And</span> <span m='265370'>in</span> <span
  m='265580'>terms</span> <span m='266270'>of</span> <span m='267080'>the</span>
  <span m='267740'>z</span> <span m='268010'>plane</span> <span
  m='268430'>representation,</span> <span m='270110'>or</span> <span
  m='270320'>pole-zero</span> <span m='270980'>representation</span> <span
  m='272010'>in</span> <span m='272150'>the</span> <span
  m='272240'>z-plane,</span> <span m='273800'>we</span> <span
  m='273920'>then</span> <span m='274190'>have</span> <span m='275330'>a</span>
  <span m='275390'>representation</span> <span m='276530'>of</span> <span
  m='276680'>this</span> <span m='276890'>rational</span> <span
  m='277340'>function</span> <span m='278780'>in</span> <span
  m='278930'>terms</span> <span m='279380'>of</span> <span m='279530'>one</span>
  <span m='279770'>pole--</span> <span m='280820'>the</span> <span
  m='280910'>pole at</span> <span m='281230'>z</span> <span
  m='281400'>equals</span> <span m='281780'>a--</span> <span
  m='282485'>and</span> <span m='282770'>one</span> <span
  m='283040'>zero,</span> <span m='283910'>that</span> <span
  m='284120'>is</span> <span m='284580'>the</span> <span m='284710'>zero</span>
  <span m='285320'>at</span> <span m='285540'>z</span> <span
  m='285610'>equals</span> <span m='285980'>0.</span> </p><p><span
  m='287910'>Well,</span> <span m='288390'>to</span> <span m='288510'>get</span>
  <span m='288720'>the</span> <span m='288840'>frequency</span> <span
  m='289410'>response</span> <span m='290250'>associated</span> <span
  m='291300'>with</span> <span m='291480'>that</span> <span
  m='291690'>system</span> <span m='292110'>function,</span> <span
  m='293250'>we</span> <span m='293400'>want</span> <span m='293700'>to</span>
  <span m='293850'>look</span> <span m='294150'>at</span> <span
  m='294270'>the</span> <span m='294360'>Z-transform</span> <span
  m='295920'>evaluated</span> <span m='297150'>on</span> <span
  m='297330'>the</span> <span m='297420'>unit</span> <span
  m='297720'>circle.</span> <span m='299780'>We</span> <span
  m='299900'>can</span> <span m='300080'>do</span> <span m='300260'>that</span>
  <span m='300800'>geometrically</span> <span m='302390'>by</span> <span
  m='302990'>interpreting</span> <span m='304700'>this</span> <span
  m='305270'>complex</span> <span m='305870'>number</span> <span
  m='306500'>as</span> <span m='306680'>a</span> <span m='306740'>vector</span>
  <span m='307400'>in</span> <span m='307520'>the</span> <span
  m='307610'>z</span> <span m='307820'>plane</span> <span m='309140'>and</span>
  <span m='309320'>this</span> <span m='309560'>complex</span> <span
  m='310160'>number</span> <span m='310820'>as</span> <span m='311000'>a</span>
  <span m='311060'>vector</span> <span m='311660'>in</span> <span
  m='311810'>the</span> <span m='311900'>z</span> <span m='312110'>plane,</span>
  <span m='313860'>in</span> <span m='313960'>which</span> <span
  m='314090'>case</span> <span m='314810'>the</span> <span
  m='314930'>magnitude</span> <span m='315980'>of</span> <span
  m='316400'>H</span> <span m='316670'>of</span> <span m='316790'>z</span> <span
  m='317810'>will</span> <span m='318020'>be</span> <span m='318620'>the</span>
  <span m='318740'>ratio</span> <span m='319430'>of</span> <span
  m='319580'>the</span> <span m='319700'>magnitudes</span> <span
  m='320390'>of</span> <span m='320510'>those</span> <span
  m='320810'>vectors.</span> <span m='322280'>And</span> <span
  m='322790'>the</span> <span m='323000'>angle</span> <span m='323360'>of</span>
  <span m='323480'>H</span> <span m='323720'>of</span> <span m='323840'>z</span>
  <span m='324470'>will</span> <span m='324710'>be</span> <span
  m='325340'>the</span> <span m='325520'>angle</span> <span m='326150'>of</span>
  <span m='326330'>this</span> <span m='326540'>vector</span> <span
  m='327620'>minus</span> <span m='328400'>the</span> <span
  m='328550'>angle</span> <span m='328880'>of</span> <span
  m='328970'>this</span> <span m='329180'>vector.</span> </p><p><span
  m='330240'>In</span> <span m='330340'>other</span> <span
  m='330440'>words,</span> <span m='331100'>suppose</span> <span
  m='331580'>that</span> <span m='331670'>we</span> <span m='331820'>want</span>
  <span m='332060'>to</span> <span m='332120'>look</span> <span
  m='332480'>at</span> <span m='332630'>H</span> <span m='332900'>of</span>
  <span m='332990'>z,</span> <span m='334270'>at</span> <span
  m='334430'>some</span> <span m='334730'>value</span> <span
  m='335180'>of</span> <span m='335300'>z.</span> <span m='335780'>And</span>
  <span m='336590'>let's</span> <span m='336800'>say,</span> <span
  m='338000'>for</span> <span m='338150'>the</span> <span
  m='338240'>moment,</span> <span m='338940'>not</span> <span
  m='339050'>on</span> <span m='339170'>the</span> <span m='339260'>unit</span>
  <span m='339560'>circle,</span> <span m='340130'>or</span> <span
  m='340310'>it</span> <span m='340400'>could</span> <span m='340610'>be</span>
  <span m='340760'>on</span> <span m='340910'>the</span> <span
  m='341000'>unit</span> <span m='341270'>circle.</span> <span
  m='342110'>Let's</span> <span m='342260'>just</span> <span
  m='342470'>pick</span> <span m='342710'>a</span> <span
  m='342770'>general</span> <span m='343220'>value</span> <span
  m='344750'>z</span> <span m='345200'>equals</span> <span m='345530'>z1.</span>
  <span m='347630'>We</span> <span m='347780'>have</span> <span
  m='348350'>a</span> <span m='348410'>vector</span> <span
  m='349820'>corresponding</span> <span m='350540'>to</span> <span
  m='350660'>this</span> <span m='350840'>complex</span> <span
  m='351470'>number,</span> <span m='352430'>which</span> <span
  m='352730'>is</span> <span m='353690'>the</span> <span
  m='353810'>vector,</span> <span m='354350'>or</span> <span
  m='354530'>complex</span> <span m='355130'>number,</span> <span
  m='355820'>z.</span> <span m='357170'>And</span> <span
  m='357980'>that's</span> <span m='358280'>a</span> <span
  m='358340'>vector</span> <span m='359300'>going</span> <span
  m='359600'>from</span> <span m='359780'>the</span> <span
  m='359900'>origin</span> <span m='360890'>out</span> <span
  m='361130'>to</span> <span m='361280'>this</span> <span
  m='361490'>point.</span> <span m='363170'>We</span> <span
  m='363290'>have</span> <span m='363530'>one</span> <span
  m='363800'>vector,</span> <span m='366500'>which</span> <span
  m='366610'>is</span> <span m='367420'>the</span> <span
  m='367510'>vector</span> <span m='368740'>z</span> <span m='369460'>or</span>
  <span m='369580'>z1</span> <span m='370750'>because</span> <span
  m='371130'>we're</span> <span m='371380'>evaluating</span> <span
  m='372070'>this</span> <span m='372280'>at</span> <span m='372460'>z</span>
  <span m='372760'>equals</span> <span m='373240'>z1.</span> <span
  m='374320'>So</span> <span m='374830'>this</span> <span m='375070'>is</span>
  <span m='375220'>a</span> <span m='375280'>vector</span> <span
  m='375730'>z1.</span> <span m='377830'>And</span> <span m='378790'>the</span>
  <span m='378910'>vector</span> <span m='379840'>z</span> <span
  m='381040'>corresponding</span> <span m='381670'>to</span> <span
  m='381730'>the</span> <span m='381850'>complex</span> <span
  m='382330'>number</span> <span m='382670'>z</span> <span
  m='382930'>minus</span> <span m='383260'>a</span> <span m='384440'>is</span>
  <span m='384610'>the</span> <span m='384730'>vector</span> <span
  m='385780'>z</span> <span m='386080'>or</span> <span m='386380'>z1</span>
  <span m='388090'>minus</span> <span m='388720'>the</span> <span
  m='388840'>vector</span> <span m='389320'>a.</span> <span
  m='390840'>The</span> <span m='391330'>vector</span> <span
  m='392030'>z1</span> <span m='392630'>is</span> <span m='392840'>this</span>
  <span m='393080'>vector.</span> <span m='394900'>The</span> <span
  m='395030'>vector</span> <span m='396200'>minus</span> <span
  m='396530'>a</span> <span m='397160'>is</span> <span m='397700'>this</span>
  <span m='397940'>vector.</span> <span m='399390'>And</span> <span
  m='399440'>the</span> <span m='399530'>sum</span> <span m='399830'>of</span>
  <span m='399950'>those</span> <span m='400280'>two,</span> <span
  m='401180'>the</span> <span m='401440'>vector</span> <span
  m='401900'>that</span> <span m='402020'>corresponds</span> <span
  m='402770'>to</span> <span m='402890'>the</span> <span
  m='403010'>complex</span> <span m='403550'>number</span> <span
  m='404300'>z</span> <span m='404510'>minus</span> <span m='404960'>a,</span>
  <span m='405800'>is</span> <span m='405920'>the</span> <span
  m='406010'>vector</span> <span m='407060'>whose</span> <span
  m='407300'>tail</span> <span m='407930'>is</span> <span m='408110'>at</span>
  <span m='408230'>this</span> <span m='408410'>pole</span> <span
  m='409460'>and</span> <span m='409610'>whose</span> <span
  m='409820'>head</span> <span m='410330'>is</span> <span m='410510'>at</span>
  <span m='410600'>the</span> <span m='410720'>value</span> <span
  m='411200'>of</span> <span m='411290'>z,</span> <span m='411860'>at</span>
  <span m='412010'>which</span> <span m='412250'>we</span> <span
  m='412370'>want</span> <span m='412520'>to</span> <span
  m='412610'>evaluate</span> <span m='413630'>H</span> <span
  m='413890'>of</span> <span m='413960'>z.</span> </p><p><span
  m='415280'>And</span> <span m='417300'>so</span> <span m='418140'>we</span>
  <span m='418350'>end</span> <span m='418590'>up</span> <span
  m='418800'>then</span> <span m='420180'>with</span> <span m='421440'>an</span>
  <span m='421530'>interpretation</span> <span m='422610'>of</span> <span
  m='422790'>the</span> <span m='422880'>value</span> <span m='423360'>of</span>
  <span m='423480'>H</span> <span m='423720'>of</span> <span m='423810'>z</span>
  <span m='425380'>in</span> <span m='425500'>polar</span> <span
  m='425890'>form</span> <span m='427390'>with</span> <span
  m='427720'>its</span> <span m='427930'>magnitude</span> <span
  m='429250'>equal</span> <span m='429640'>to</span> <span m='430240'>the</span>
  <span m='430360'>magnitude</span> <span m='430990'>of</span> <span
  m='431080'>this</span> <span m='431320'>vector</span> <span
  m='433000'>divided</span> <span m='433450'>by</span> <span
  m='434020'>the</span> <span m='434140'>magnitude</span> <span
  m='434860'>or</span> <span m='434980'>length</span> <span m='435670'>of</span>
  <span m='436240'>the</span> <span m='436330'>pole</span> <span
  m='436630'>vector.</span> <span m='438070'>And</span> <span
  m='438220'>the</span> <span m='438370'>angle</span> <span m='439510'>of</span>
  <span m='439660'>this</span> <span m='439840'>complex</span> <span
  m='440410'>number,</span> <span m='440830'>H</span> <span m='441100'>of</span>
  <span m='441220'>z</span> <span m='441580'>at</span> <span m='442015'>z
  equals</span> <span m='442450'>z1</span> <span m='443410'>is</span> <span
  m='444010'>the</span> <span m='444250'>angle</span> <span m='444820'>of</span>
  <span m='445000'>the</span> <span m='445090'>0</span> <span
  m='445450'>vector</span> <span m='446410'>minus</span> <span
  m='447220'>the</span> <span m='447400'>angle</span> <span m='448000'>of</span>
  <span m='448150'>the</span> <span m='448240'>pole</span> <span
  m='448540'>vector.</span> <span m='450010'>That's</span> <span
  m='450250'>a</span> <span m='450310'>general</span> <span
  m='450940'>statement.</span> <span m='452430'>And</span> <span
  m='452630'>z1</span> <span m='453670'>can</span> <span m='453850'>be</span>
  <span m='454010'>any</span> <span m='454160'>place</span> <span
  m='454540'>in</span> <span m='454630'>the</span> <span m='454720'>z</span>
  <span m='454900'>plane.</span> </p><p><span m='456500'>So</span> <span
  m='457090'>we</span> <span m='457360'>have</span> <span m='457660'>then</span>
  <span m='458470'>the</span> <span m='458560'>statement</span> <span
  m='459670'>as</span> <span m='460240'>I've</span> <span m='460420'>just</span>
  <span m='460690'>made</span> <span m='460990'>it,</span> <span
  m='462310'>which</span> <span m='462820'>we</span> <span
  m='463000'>would</span> <span m='463150'>now</span> <span
  m='463810'>like</span> <span m='464290'>to</span> <span
  m='464650'>apply</span> <span m='466420'>to</span> <span m='467440'>the</span>
  <span m='467890'>interpretation</span> <span m='469030'>or</span> <span
  m='469780'>the</span> <span m='469870'>generation</span> <span
  m='471190'>of</span> <span m='471970'>the</span> <span
  m='472180'>frequency</span> <span m='472810'>response</span> <span
  m='474010'>of</span> <span m='474130'>a</span> <span m='474190'>system.</span>
  <span m='476060'>So</span> <span m='476570'>we</span> <span
  m='476750'>have,</span> <span m='477020'>then,</span> <span
  m='477500'>our</span> <span m='478640'>example</span> <span
  m='479690'>that</span> <span m='479870'>is</span> <span m='480380'>one</span>
  <span m='480660'>pole</span> <span m='481170'>at</span> <span
  m='481400'>equals a</span> <span m='481880'>and</span> <span
  m='483410'>0</span> <span m='484220'>at</span> <span m='484610'>z</span> <span
  m='485110'>equals</span> <span m='485620'>0.</span> <span m='486920'>We</span>
  <span m='487070'>have</span> <span m='487790'>the</span> <span
  m='487880'>0</span> <span m='488270'>vector</span> <span m='489770'>and</span>
  <span m='489920'>the</span> <span m='490010'>pole</span> <span
  m='490370'>vector.</span> <span m='491930'>And</span> <span
  m='492410'>as</span> <span m='492740'>we</span> <span
  m='492920'>generate</span> <span m='493970'>the</span> <span
  m='494090'>frequency</span> <span m='494630'>response</span> <span
  m='495680'>for</span> <span m='495840'>z1</span> <span m='496460'>equal</span>
  <span m='496910'>to</span> <span m='497240'>e</span> <span
  m='497470'>to</span> <span m='497510'>the</span> <span m='497630'>j</span>
  <span m='497870'>omega,</span> <span m='499550'>we</span> <span
  m='499850'>have</span> <span m='500630'>the</span> <span
  m='500900'>point</span> <span m='501860'>on</span> <span m='502400'>the</span>
  <span m='502520'>unit</span> <span m='502820'>circle</span> <span
  m='504590'>at</span> <span m='504770'>which</span> <span
  m='505040'>we're</span> <span m='505250'>evaluating</span> <span
  m='506000'>the</span> <span m='506090'>Z-transform</span> <span
  m='507290'>changing.</span> <span m='509240'>If</span> <span
  m='509570'>we</span> <span m='509750'>think</span> <span m='510200'>of</span>
  <span m='510950'>angular</span> <span m='511400'>distance</span> <span
  m='512120'>around</span> <span m='512419'>the</span> <span
  m='512539'>unit</span> <span m='512809'>circle</span> <span
  m='513350'>as</span> <span m='513500'>omega,</span> <span
  m='515000'>then</span> <span m='515450'>as</span> <span
  m='515659'>omega</span> <span m='516110'>varies</span> <span
  m='517549'>and</span> <span m='517820'>we</span> <span
  m='517940'>consider</span> <span m='518990'>the</span> <span
  m='521150'>relative</span> <span m='521659'>behavior</span> <span
  m='522770'>of</span> <span m='522890'>these</span> <span m='523100'>two</span>
  <span m='523280'>vectors,</span> <span m='524330'>what</span> <span
  m='524570'>we</span> <span m='524960'>essentially</span> <span
  m='525530'>trace</span> <span m='525920'>out</span> <span m='526310'>is</span>
  <span m='526460'>the</span> <span m='526580'>frequency</span> <span
  m='527090'>response</span> <span m='527840'>of</span> <span
  m='527930'>the</span> <span m='528050'>system.</span> </p><p><span
  m='530430'>So</span> <span m='531020'>let's</span> <span
  m='532400'>look</span> <span m='532670'>at</span> <span m='532820'>this</span>
  <span m='533300'>and</span> <span m='533990'>for</span> <span
  m='534140'>this</span> <span m='534350'>example</span> <span
  m='535160'>see</span> <span m='535730'>if</span> <span m='536390'>we</span>
  <span m='536540'>can</span> <span m='536750'>get,</span> <span
  m='537510'>for</span> <span m='537680'>this</span> <span
  m='537890'>example,</span> <span m='538970'>a</span> <span
  m='539060'>rough</span> <span m='539420'>idea</span> <span
  m='540620'>of</span> <span m='540980'>what</span> <span m='541220'>the</span>
  <span m='541310'>frequency</span> <span m='541850'>response</span> <span
  m='542300'>should</span> <span m='542480'>look</span> <span
  m='542690'>like.</span> <span m='544540'>Well,</span> <span
  m='545280'>first</span> <span m='545970'>of</span> <span m='546090'>all</span>
  <span m='546270'>we</span> <span m='546420'>observe.</span> <span
  m='547000'>And</span> <span m='547100'>this</span> <span m='547170'>is</span>
  <span m='547290'>an</span> <span m='547410'>important</span> <span
  m='547800'>observation,</span> <span m='549060'>since</span> <span
  m='549720'>it's</span> <span m='550140'>a</span> <span m='550200'>point</span>
  <span m='550530'>that</span> <span m='550830'>comes</span> <span
  m='551160'>up</span> <span m='551250'>frequently,</span> <span
  m='553230'>is</span> <span m='553410'>that</span> <span m='554310'>as</span>
  <span m='554910'>we</span> <span m='555060'>travel</span> <span
  m='556350'>around</span> <span m='556740'>the</span> <span
  m='556860'>unit</span> <span m='557160'>circle,</span> <span
  m='559330'>the</span> <span m='559450'>vector</span> <span
  m='560290'>from</span> <span m='560560'>the</span> <span m='560650'>0</span>
  <span m='562060'>to</span> <span m='562180'>the</span> <span
  m='562300'>unit</span> <span m='562600'>circle</span> <span
  m='564190'>changes</span> <span m='564970'>in</span> <span
  m='565150'>angle,</span> <span m='566410'>of</span> <span
  m='566530'>course.</span> <span m='567670'>But</span> <span
  m='567850'>it</span> <span m='567940'>doesn't</span> <span
  m='568270'>change</span> <span m='568630'>in</span> <span
  m='568720'>length.</span> <span m='570250'>The</span> <span
  m='570340'>0</span> <span m='571090'>vector</span> <span m='571510'>for</span>
  <span m='571660'>this</span> <span m='571870'>example,</span> <span
  m='572440'>or</span> <span m='572620'>in</span> <span m='572710'>fact</span>
  <span m='573040'>any</span> <span m='573280'>vector</span> <span
  m='573670'>from</span> <span m='573850'>the</span> <span
  m='573970'>origin</span> <span m='574270'>out</span> <span
  m='574570'>to</span> <span m='574720'>the</span> <span m='574810'>unit</span>
  <span m='575080'>circle,</span> <span m='576220'>as</span> <span
  m='577030'>we</span> <span m='577180'>vary</span> <span
  m='577570'>omega</span> <span m='578500'>and,</span> <span
  m='578620'>therefore,</span> <span m='578980'>trace</span> <span
  m='579340'>around</span> <span m='579640'>the</span> <span
  m='579730'>unit</span> <span m='580000'>circle,</span> <span
  m='581210'>this</span> <span m='581350'>vector</span> <span
  m='581710'>doesn't</span> <span m='582040'>change</span> <span
  m='582370'>in</span> <span m='582490'>length.</span> </p><p><span
  m='583520'>So</span> <span m='583750'>if</span> <span m='584260'>we're</span>
  <span m='584470'>interested</span> <span m='585190'>in,</span> <span
  m='585760'>say,</span> <span m='586060'>the</span> <span
  m='586180'>magnitude</span> <span m='586720'>of</span> <span
  m='586810'>the</span> <span m='586930'>frequency</span> <span
  m='587470'>response,</span> <span m='588970'>any</span> <span
  m='589210'>poles</span> <span m='589570'>or</span> <span
  m='589630'>zeros</span> <span m='590110'>at</span> <span m='590230'>the</span>
  <span m='590380'>origin,</span> <span m='591100'>of</span> <span
  m='591220'>course,</span> <span m='591880'>have</span> <span
  m='592060'>no</span> <span m='592240'>effect</span> <span m='592600'>on</span>
  <span m='592720'>the</span> <span m='592810'>magnitude.</span> <span
  m='594430'>The</span> <span m='594580'>only</span> <span
  m='595000'>effect</span> <span m='595360'>that</span> <span
  m='595480'>they</span> <span m='595630'>have</span> <span m='596440'>is</span>
  <span m='596590'>on</span> <span m='596740'>the</span> <span
  m='596830'>phase</span> <span m='598150'>of</span> <span m='598240'>the</span>
  <span m='598360'>frequency</span> <span m='598870'>response</span> <span
  m='599800'>that</span> <span m='600010'>is</span> <span m='600340'>on</span>
  <span m='600520'>the</span> <span m='600640'>angle</span> <span
  m='601270'>of</span> <span m='601450'>H</span> <span m='601660'>of</span>
  <span m='602090'>z.</span> <span m='602950'>And</span> <span
  m='603070'>in</span> <span m='603190'>fact,</span> <span m='603970'>as</span>
  <span m='604300'>we</span> <span m='604420'>sweep</span> <span
  m='604780'>around</span> <span m='605110'>the</span> <span
  m='605200'>unit</span> <span m='605500'>circle,</span> <span
  m='606640'>what</span> <span m='606820'>happens</span> <span
  m='607330'>to</span> <span m='607450'>this</span> <span
  m='607660'>angle?</span> <span m='608470'>Well,</span> <span
  m='608800'>that</span> <span m='609010'>angle</span> <span
  m='609340'>is</span> <span m='609460'>just</span> <span
  m='609610'>simply</span> <span m='610000'>equal</span> <span
  m='610330'>to</span> <span m='611050'>the</span> <span m='611140'>value</span>
  <span m='611680'>omega</span> <span m='612760'>that</span> <span
  m='612910'>we're</span> <span m='613060'>looking</span> <span
  m='613420'>at</span> <span m='613630'>that</span> <span m='613780'>is</span>
  <span m='613870'>the</span> <span m='613960'>frequency</span> <span
  m='615100'>value</span> <span m='615610'>omega.</span> </p><p><span
  m='616660'>So</span> <span m='616810'>then,</span> <span m='616990'>in</span>
  <span m='617110'>fact,</span> <span m='617650'>poles or</span> <span
  m='618080'>zeros</span> <span m='618550'>at</span> <span m='618640'>the</span>
  <span m='618790'>origin</span> <span m='619600'>as,</span> <span
  m='619810'>of</span> <span m='619900'>course,</span> <span
  m='620270'>we</span> <span m='620290'>could</span> <span m='620470'>see</span>
  <span m='620920'>from</span> <span m='621960'>a</span> <span
  m='622110'>strictly</span> <span m='622540'>algebraic</span> <span
  m='623170'>argument.</span> <span m='624610'>But</span> <span
  m='624790'>from</span> <span m='624970'>a</span> <span
  m='625000'>geometric</span> <span m='625600'>argument,</span> <span
  m='626140'>it</span> <span m='626240'>should</span> <span m='626320'>be</span>
  <span m='626440'>clear</span> <span m='627370'>that</span> <span
  m='627610'>poles</span> <span m='627980'>or</span> <span
  m='628060'>zeros</span> <span m='628480'>at</span> <span m='628630'>the</span>
  <span m='628780'>origin</span> <span m='630280'>introduce,</span> <span
  m='630630'>in</span> <span m='631330'>the</span> <span
  m='631420'>frequency</span> <span m='631960'>response,</span> <span
  m='633030'>a</span> <span m='633100'>linear</span> <span
  m='633490'>phase</span> <span m='633910'>term.</span> <span
  m='635020'>And</span> <span m='635590'>they</span> <span
  m='635710'>have</span> <span m='635920'>no</span> <span
  m='636130'>effect</span> <span m='636520'>on</span> <span
  m='636640'>the</span> <span m='636730'>magnitude</span> <span
  m='637510'>since</span> <span m='638630'>the</span> <span
  m='638680'>length</span> <span m='639010'>of</span> <span m='639100'>a</span>
  <span m='639160'>vector</span> <span m='639490'>from</span> <span
  m='639640'>the</span> <span m='639730'>origin</span> <span
  m='640120'>to</span> <span m='640210'>the</span> <span m='640270'>unit</span>
  <span m='640540'>circle</span> <span m='641320'>is</span> <span
  m='641470'>obviously</span> <span m='642050'>1.</span> <span
  m='643690'>As</span> <span m='643810'>a</span> <span
  m='643870'>consequence</span> <span m='644500'>of</span> <span
  m='644590'>that,</span> <span m='644770'>by</span> <span m='644980'>the</span>
  <span m='645100'>way,</span> <span m='645530'>often</span> <span
  m='646960'>when</span> <span m='647440'>talking</span> <span
  m='647890'>about</span> <span m='648160'>the</span> <span
  m='648250'>frequency</span> <span m='648790'>response</span> <span
  m='649390'>or</span> <span m='649480'>equivalently</span> <span
  m='650410'>when</span> <span m='652540'>looking</span> <span
  m='652870'>at</span> <span m='652960'>pole-zero</span> <span
  m='653920'>patterns,</span> <span m='655050'>it's</span> <span
  m='655210'>common</span> <span m='656140'>to</span> <span
  m='656740'>minimize</span> <span m='657520'>or</span> <span
  m='657640'>ignore</span> <span m='659050'>the</span> <span
  m='659410'>presence</span> <span m='660040'>of</span> <span
  m='660160'>zeros</span> <span m='660580'>or</span> <span
  m='660640'>poles</span> <span m='661030'>at</span> <span m='661120'>the</span>
  <span m='661270'>origin</span> <span m='661970'>since</span> <span
  m='662410'>they</span> <span m='662590'>just</span> <span
  m='662800'>correspond</span> <span m='663610'>to</span> <span
  m='664000'>a</span> <span m='664090'>linear</span> <span
  m='664450'>phase</span> <span m='664840'>term.</span> </p><p><span
  m='666460'>Now,</span> <span m='667000'>let's</span> <span
  m='667240'>look</span> <span m='667480'>at</span> <span m='667720'>what</span>
  <span m='667900'>the</span> <span m='667990'>behavior</span> <span
  m='668470'>of</span> <span m='668530'>the</span> <span m='668650'>pole</span>
  <span m='668950'>vector</span> <span m='669400'>is.</span> <span
  m='670540'>The</span> <span m='670630'>pole</span> <span
  m='670990'>vector</span> <span m='672670'>as</span> <span m='673570'>we</span>
  <span m='673840'>start,</span> <span m='674320'>say,</span> <span
  m='674590'>at</span> <span m='674680'>omega</span> <span
  m='675040'>equals</span> <span m='675370'>0,</span> <span m='676750'>we</span>
  <span m='676900'>have</span> <span m='677140'>a</span> <span
  m='677200'>vector</span> <span m='678370'>going</span> <span
  m='678670'>from</span> <span m='678850'>the</span> <span
  m='678940'>pole</span> <span m='679720'>to</span> <span m='681400'>this</span>
  <span m='681610'>point</span> <span m='682120'>on</span> <span
  m='682240'>the</span> <span m='682330'>unit</span> <span
  m='682600'>circle.</span> <span m='684620'>And</span> <span
  m='685120'>as</span> <span m='685420'>we</span> <span m='685570'>sweep</span>
  <span m='685960'>around</span> <span m='687340'>in</span> <span
  m='687460'>frequency</span> <span m='689050'>until</span> <span
  m='689350'>we</span> <span m='689500'>get</span> <span m='689680'>to</span>
  <span m='689860'>omega</span> <span m='690210'>equals</span> <span
  m='690550'>pi</span> <span m='691600'>halfway</span> <span
  m='692020'>around</span> <span m='692290'>the</span> <span
  m='692380'>unit</span> <span m='692650'>circle,</span> <span
  m='693970'>the</span> <span m='694060'>length</span> <span
  m='694420'>of</span> <span m='694540'>this</span> <span
  m='694750'>vector</span> <span m='695980'>is</span> <span
  m='696130'>monotonically</span> <span m='697120'>increasing.</span> <span
  m='698830'>Well,</span> <span m='699280'>what</span> <span
  m='699430'>does</span> <span m='699550'>that</span> <span
  m='699730'>mean</span> <span m='700540'>about</span> <span
  m='700840'>the</span> <span m='700930'>magnitude</span> <span
  m='702160'>of</span> <span m='702280'>the</span> <span
  m='702370'>frequency</span> <span m='702880'>response?</span> <span
  m='704050'>It</span> <span m='704170'>means</span> <span
  m='704740'>that</span> <span m='705340'>the</span> <span
  m='705430'>magnitude</span> <span m='706090'>of</span> <span
  m='706180'>the</span> <span m='706270'>frequency</span> <span
  m='706840'>response,</span> <span m='707710'>which</span> <span
  m='708260'>should</span> <span m='708460'>be</span> <span
  m='708970'>the</span> <span m='709060'>magnitude</span> <span
  m='709630'>of</span> <span m='709720'>that</span> <span
  m='709910'>vector--</span> <span m='710890'>the</span> <span
  m='710980'>magnitude</span> <span m='711520'>of</span> <span
  m='711580'>the</span> <span m='711700'>frequency</span> <span
  m='712210'>response</span> <span m='713350'>is</span> <span
  m='713560'>monotonically</span> <span m='714430'>decreasing</span> <span
  m='715420'>as</span> <span m='715600'>we</span> <span m='715720'>sweep</span>
  <span m='716440'>from</span> <span m='717010'>omega</span> <span
  m='717460'>equals</span> <span m='717750'>zero</span> <span
  m='718690'>around</span> <span m='719440'>to</span> <span
  m='719830'>omega</span> <span m='720220'>equals</span> <span
  m='720580'>pi.</span> </p><p><span m='722810'>At</span> <span
  m='722910'>omega</span> <span m='723100'>equal</span> <span
  m='723370'>to</span> <span m='723520'>pi,</span> <span m='724780'>we</span>
  <span m='724930'>have</span> <span m='725140'>exactly</span> <span
  m='725620'>the</span> <span m='725740'>reverse</span> <span
  m='726100'>situation.</span> <span m='728430'>The</span> <span
  m='728520'>length</span> <span m='728820'>of</span> <span
  m='728910'>the</span> <span m='729030'>vector</span> <span
  m='729630'>from</span> <span m='729840'>the</span> <span
  m='729930'>pole--</span> <span m='730325'>and</span> <span
  m='730720'>let</span> <span m='730860'>me</span> <span m='730980'>draw</span>
  <span m='731250'>that</span> <span m='731460'>vector--</span> <span
  m='732600'>from</span> <span m='732810'>the</span> <span
  m='732900'>pole</span> <span m='733740'>to</span> <span
  m='733920'>omega</span> <span m='734220'>equals</span> <span
  m='734580'>pi</span> <span m='735690'>as</span> <span m='735870'>we</span>
  <span m='735990'>sweep</span> <span m='736380'>around</span> <span
  m='736800'>back</span> <span m='737100'>to</span> <span
  m='737240'>omega</span> <span m='737560'>equals</span> <span
  m='737880'>0,</span> <span m='738510'>the</span> <span
  m='738600'>length</span> <span m='738900'>of</span> <span
  m='738960'>that</span> <span m='739350'>vector</span> <span
  m='739770'>decreases.</span> <span m='740970'>So</span> <span
  m='741600'>the</span> <span m='741720'>magnitude</span> <span
  m='742320'>of</span> <span m='742380'>the</span> <span
  m='742500'>frequency</span> <span m='743010'>response</span> <span
  m='743520'>increases.</span> </p><p><span m='745390'>So</span> <span
  m='745470'>for</span> <span m='745590'>this</span> <span
  m='745770'>particular</span> <span m='746310'>example,</span> <span
  m='747420'>by</span> <span m='747660'>just</span> <span
  m='748140'>observing</span> <span m='749220'>what</span> <span
  m='749850'>happens</span> <span m='750360'>to</span> <span
  m='750480'>the</span> <span m='750600'>length</span> <span
  m='751080'>of</span> <span m='751200'>this</span> <span m='751380'>pole</span>
  <span m='751710'>vector</span> <span m='752340'>as</span> <span
  m='752550'>we</span> <span m='752640'>trace</span> <span
  m='753030'>around</span> <span m='753360'>the</span> <span
  m='753480'>unit</span> <span m='753720'>circle,</span> <span
  m='754920'>we</span> <span m='755040'>can</span> <span m='755220'>see</span>
  <span m='755490'>that</span> <span m='756150'>the</span> <span
  m='756240'>frequency</span> <span m='756810'>response</span> <span
  m='757710'>starts</span> <span m='758190'>at</span> <span
  m='758280'>some</span> <span m='758550'>value.</span> <span
  m='759240'>That's</span> <span m='759450'>obvious.</span> <span
  m='761150'>And</span> <span m='761900'>as</span> <span m='762110'>it</span>
  <span m='762200'>sweeps</span> <span m='762530'>around</span> <span
  m='762870'>to</span> <span m='762950'>pi,</span> <span m='764780'>it</span>
  <span m='764960'>monotonically</span> <span m='766970'>decreases.</span> <span
  m='769470'>And</span> <span m='770360'>when</span> <span m='770660'>we</span>
  <span m='770750'>come</span> <span m='770990'>back</span> <span
  m='771320'>from</span> <span m='771530'>pi</span> <span
  m='772580'>around</span> <span m='772940'>to</span> <span m='773060'>0,</span>
  <span m='774110'>the</span> <span m='774200'>frequency</span> <span
  m='774680'>response</span> <span m='776300'>increases</span> <span
  m='776960'>again.</span> <span m='779160'>And</span> <span m='780530'>I</span>
  <span m='780620'>don't</span> <span m='780800'>know</span> <span
  m='781010'>if</span> <span m='781160'>I've</span> <span
  m='781280'>drawn</span> <span m='781550'>it</span> <span m='781640'>so</span>
  <span m='781820'>that</span> <span m='781970'>it</span> <span
  m='782720'>looks</span> <span m='783020'>clearly</span> <span
  m='783870'>this</span> <span m='784110'>way.</span> <span
  m='784910'>But</span> <span m='785330'>in</span> <span m='785480'>fact,</span>
  <span m='786320'>this</span> <span m='786560'>piece</span> <span
  m='787490'>is</span> <span m='787640'>just</span> <span m='788120'>this</span>
  <span m='788420'>piece</span> <span m='789140'>reflected</span> <span
  m='789710'>over.</span> </p><p><span m='791990'>There's</span> <span
  m='792170'>another</span> <span m='792830'>important</span> <span
  m='793880'>point</span> <span m='794540'>that</span> <span
  m='795920'>we</span> <span m='796160'>can</span> <span
  m='796340'>observe</span> <span m='796970'>geometrically.</span> <span
  m='797870'>It's</span> <span m='798410'>a</span> <span m='798470'>point</span>
  <span m='798860'>about</span> <span m='799160'>the</span> <span
  m='799280'>frequency</span> <span m='799760'>response</span> <span
  m='800810'>that,</span> <span m='800930'>of</span> <span
  m='801020'>course,</span> <span m='801290'>we've</span> <span
  m='801710'>emphasized</span> <span m='802580'>several</span> <span
  m='803000'>times</span> <span m='803360'>in</span> <span
  m='803480'>several</span> <span m='803870'>ways.</span> <span
  m='804860'>This</span> <span m='805040'>just</span> <span
  m='805310'>offers</span> <span m='805640'>an</span> <span
  m='805760'>opportunity</span> <span m='806810'>to</span> <span
  m='806930'>re-emphasise</span> <span m='807800'>it</span> <span
  m='807950'>in</span> <span m='808070'>yet</span> <span
  m='808250'>another</span> <span m='808580'>way.</span> </p><p><span
  m='810380'>As</span> <span m='810530'>the</span> <span
  m='810620'>frequency</span> <span m='811580'>variable</span> <span
  m='813380'>goes</span> <span m='813680'>from</span> <span m='813860'>0</span>
  <span m='815630'>around</span> <span m='816110'>to</span> <span
  m='816280'>2pi,</span> <span m='818270'>we</span> <span
  m='818990'>trace</span> <span m='819350'>out</span> <span m='819710'>a</span>
  <span m='819770'>magnitude</span> <span m='820610'>and</span> <span
  m='820760'>then,</span> <span m='821000'>of</span> <span
  m='821120'>course,</span> <span m='821420'>also</span> <span
  m='821750'>a</span> <span m='821810'>phase</span> <span m='822380'>for</span>
  <span m='822500'>the</span> <span m='822620'>frequency</span> <span
  m='823100'>response.</span> <span m='824420'>When</span> <span
  m='824600'>we</span> <span m='824690'>get</span> <span m='824900'>back</span>
  <span m='825170'>to</span> <span m='825290'>0</span> <span
  m='825890'>or</span> <span m='826040'>2pi,</span> <span m='827540'>if</span>
  <span m='827690'>we</span> <span m='827810'>go</span> <span
  m='827990'>from</span> <span m='828170'>2pi</span> <span
  m='829370'>around</span> <span m='829700'>to</span> <span
  m='829850'>4pi,</span> <span m='831710'>what</span> <span
  m='831950'>should</span> <span m='832130'>we</span> <span
  m='832250'>see</span> <span m='832460'>for</span> <span m='832580'>the</span>
  <span m='832670'>frequency</span> <span m='833180'>response?</span> <span
  m='834200'>Well,</span> <span m='834410'>we</span> <span
  m='834530'>should</span> <span m='834710'>see</span> <span
  m='834920'>exactly</span> <span m='835370'>the</span> <span
  m='835460'>same</span> <span m='835760'>thing</span> <span
  m='836570'>that</span> <span m='836690'>we</span> <span m='836840'>saw</span>
  <span m='837110'>before</span> <span m='838130'>because</span> <span
  m='838670'>what</span> <span m='838820'>we're</span> <span
  m='838970'>doing</span> <span m='839570'>literally,</span> <span
  m='840140'>actually,</span> <span m='840740'>is</span> <span
  m='840920'>going</span> <span m='841220'>around</span> <span
  m='841460'>in</span> <span m='841550'>circles.</span> </p><p><span
  m='843020'>We</span> <span m='843110'>started</span> <span
  m='843530'>here,</span> <span m='844580'>went</span> <span
  m='844760'>around</span> <span m='845210'>there</span> <span
  m='845690'>to</span> <span m='845780'>get</span> <span m='845960'>the</span>
  <span m='846050'>2pi,</span> <span m='846730'>omega</span> <span
  m='847040'>equals</span> <span m='847370'>2pi.</span> <span
  m='848600'>For</span> <span m='848750'>omega</span> <span
  m='849130'>from</span> <span m='849320'>2pi</span> <span m='849680'>to</span>
  <span m='849790'>4pi,</span> <span m='850730'>we</span> <span
  m='850850'>go</span> <span m='851060'>around</span> <span
  m='851390'>again.</span> <span m='851860'>For</span> <span
  m='852180'>4pi</span> <span m='852460'>to</span> <span m='852740'>6pi,</span>
  <span m='852980'>we</span> <span m='853100'>go</span> <span
  m='853280'>around</span> <span m='853580'>again,</span> <span m='853880'>et
  cetera.</span> <span m='854780'>So</span> <span m='855230'>just</span> <span
  m='855470'>geometrically</span> <span m='856310'>by</span> <span
  m='856490'>looking</span> <span m='857570'>at</span> <span
  m='858500'>this</span> <span m='858740'>geometric</span> <span
  m='859340'>interpretation</span> <span m='860150'>of</span> <span
  m='860240'>the</span> <span m='860330'>frequency</span> <span
  m='860870'>response,</span> <span m='862460'>it</span> <span
  m='862580'>gives</span> <span m='862820'>us</span> <span m='862970'>an</span>
  <span m='863060'>opportunity</span> <span m='863720'>to</span> <span
  m='863840'>emphasize</span> <span m='864440'>once</span> <span
  m='864740'>again</span> <span m='865400'>that</span> <span
  m='865520'>the</span> <span m='865610'>frequency</span> <span
  m='866150'>response</span> <span m='866780'>is</span> <span
  m='866930'>a</span> <span m='866990'>periodic</span> <span
  m='867650'>function</span> <span m='868040'>of</span> <span
  m='868100'>frequency.</span> </p><p><span m='870690'>Now,</span> <span
  m='871260'>this</span> <span m='871500'>is</span> <span m='871980'>for</span>
  <span m='872490'>one</span> <span m='872790'>specific</span> <span
  m='873390'>example.</span> <span m='875200'>The</span> <span
  m='875710'>more</span> <span m='875920'>general</span> <span
  m='876340'>statement,</span> <span m='877240'>then,</span> <span
  m='877750'>is</span> <span m='878050'>that</span> <span m='878740'>the</span>
  <span m='882280'>magnitude</span> <span m='882820'>of</span> <span
  m='882910'>the</span> <span m='883000'>frequency</span> <span
  m='883540'>response</span> <span m='885310'>is</span> <span
  m='885490'>equal</span> <span m='885910'>to</span> <span m='887050'>the</span>
  <span m='887140'>product</span> <span m='889130'>of</span> <span
  m='889910'>the</span> <span m='890030'>length</span> <span
  m='890660'>of</span> <span m='891230'>the</span> <span m='891650'>0</span>
  <span m='892190'>vectors--</span> <span m='893180'>the</span> <span
  m='893300'>vectors</span> <span m='894260'>from</span> <span
  m='894500'>the</span> <span m='894590'>zeros</span> <span m='895700'>to</span>
  <span m='896270'>the</span> <span m='896390'>unit</span> <span
  m='896690'>circle--</span> <span m='897890'>divided</span> <span
  m='898400'>by</span> <span m='898970'>the</span> <span
  m='899090'>product</span> <span m='899690'>of</span> <span
  m='899870'>the</span> <span m='899990'>length</span> <span
  m='900350'>of</span> <span m='900500'>the</span> <span m='900590'>pole</span>
  <span m='900950'>vectors--</span> <span m='902330'>the</span> <span
  m='902420'>vectors</span> <span m='903290'>from</span> <span
  m='903470'>the</span> <span m='903560'>poles</span> <span m='904460'>to</span>
  <span m='904580'>the</span> <span m='904670'>unit</span> <span
  m='904940'>circle.</span> <span m='906380'>And</span> <span
  m='907070'>the</span> <span m='907250'>angle</span> <span m='907970'>of</span>
  <span m='908240'>the</span> <span m='908330'>frequency</span> <span
  m='908870'>response</span> <span m='909740'>is</span> <span
  m='910760'>the</span> <span m='911150'>sum</span> <span m='911690'>of</span>
  <span m='911870'>the</span> <span m='911990'>angles</span> <span
  m='912620'>of</span> <span m='912770'>the</span> <span m='912860'>0</span>
  <span m='913190'>vectors</span> <span m='914150'>minus</span> <span
  m='914780'>the</span> <span m='914900'>sum</span> <span m='915320'>of</span>
  <span m='915440'>the</span> <span m='915590'>angles</span> <span
  m='915950'>of</span> <span m='916010'>the</span> <span m='916100'>pole</span>
  <span m='916400'>vectors.</span> <span m='918050'>Incidentally,</span> <span
  m='918740'>it</span> <span m='918860'>usually</span> <span
  m='919970'>is</span> <span m='920090'>the</span> <span
  m='920210'>case--</span> <span m='920540'>or</span> <span m='920630'>it</span>
  <span m='920720'>is</span> <span m='920870'>for</span> <span
  m='921020'>me,</span> <span m='921230'>anyway--</span> <span
  m='922280'>that</span> <span m='923930'>often,</span> <span
  m='924890'>it's</span> <span m='925790'>possible</span> <span
  m='926330'>to</span> <span m='926480'>get</span> <span m='926810'>a</span>
  <span m='926900'>rough</span> <span m='927530'>picture</span> <span
  m='928580'>of</span> <span m='928790'>what</span> <span m='929270'>the</span>
  <span m='929720'>magnitude</span> <span m='930320'>of</span> <span
  m='930410'>the</span> <span m='930500'>frequency</span> <span
  m='931010'>response</span> <span m='931730'>is</span> <span
  m='931910'>like</span> <span m='932330'>by</span> <span
  m='932540'>looking</span> <span m='932870'>at</span> <span
  m='932960'>this</span> <span m='933110'>geometric</span> <span
  m='933680'>picture.</span> <span m='934790'>It's</span> <span
  m='935420'>usually</span> <span m='935840'>somewhat</span> <span
  m='936290'>more</span> <span m='936500'>difficult</span> <span
  m='937310'>except,</span> <span m='938180'>perhaps,</span> <span
  m='938570'>for</span> <span m='938720'>linear</span> <span
  m='939050'>phase</span> <span m='939410'>terms,</span> <span
  m='939830'>et</span> <span m='940115'>cetera,</span> <span
  m='940820'>to</span> <span m='941450'>get</span> <span m='942050'>a</span>
  <span m='942650'>very</span> <span m='942950'>clear</span> <span
  m='943190'>picture</span> <span m='943790'>of</span> <span
  m='943940'>what</span> <span m='944090'>the</span> <span
  m='944180'>phase</span> <span m='944540'>looks</span> <span
  m='944810'>like.</span> </p><p><span m='947450'>Well</span> <span
  m='947930'>let's</span> <span m='948470'>just</span> <span
  m='948800'>look</span> <span m='949100'>at</span> <span m='949670'>one</span>
  <span m='949940'>more</span> <span m='950180'>example,</span> <span
  m='951200'>which</span> <span m='951770'>is</span> <span m='951950'>a</span>
  <span m='952010'>kind</span> <span m='952280'>of</span> <span
  m='952400'>example</span> <span m='953390'>that</span> <span
  m='953900'>we</span> <span m='954680'>haven't</span> <span
  m='955460'>discussed</span> <span m='956090'>explicitly</span> <span
  m='956990'>up</span> <span m='957140'>to</span> <span m='957260'>this</span>
  <span m='957470'>point.</span> <span m='957980'>And</span> <span
  m='958220'>this</span> <span m='958430'>also</span> <span
  m='959390'>provides</span> <span m='959780'>us</span> <span
  m='959930'>with</span> <span m='960080'>an</span> <span
  m='960170'>opportunity</span> <span m='960950'>to</span> <span
  m='961490'>introduce</span> <span m='962330'>this</span> <span
  m='962510'>idea.</span> <span m='964580'>Let's</span> <span
  m='964820'>consider</span> <span m='965570'>the</span> <span
  m='965690'>case</span> <span m='966290'>of</span> <span m='966800'>a</span>
  <span m='966890'>Z-transform</span> <span m='969050'>which</span> <span
  m='970550'>has</span> <span m='970940'>a</span> <span
  m='971000'>pole-zero</span> <span m='971690'>pattern</span> <span
  m='972320'>consisting</span> <span m='973220'>of</span> <span
  m='974120'>a</span> <span m='974180'>pair</span> <span m='974570'>of</span>
  <span m='974630'>complex</span> <span m='975170'>conjugate</span> <span
  m='975710'>poles</span> <span m='976430'>in</span> <span m='976550'>the</span>
  <span m='976610'>z-plane.</span> <span m='977240'>These</span> <span
  m='977420'>are</span> <span m='977480'>complex</span> <span
  m='977960'>conjugate</span> <span m='978470'>poles</span> <span
  m='980090'>with</span> <span m='980270'>a</span> <span
  m='980390'>radius</span> <span m='981200'>equal</span> <span
  m='981530'>to</span> <span m='981650'>some</span> <span
  m='981920'>value,</span> <span m='982940'>say</span> <span
  m='983240'>r,</span> <span m='984500'>and</span> <span m='984830'>an</span>
  <span m='985160'>angular</span> <span m='985700'>spacing</span> <span
  m='986450'>equal</span> <span m='986810'>to</span> <span
  m='986990'>omega</span> <span m='987390'>0.</span> <span m='988440'>So</span>
  <span m='988520'>this</span> <span m='988730'>pole</span> <span
  m='989330'>is</span> <span m='989840'>at</span> <span m='990230'>omega</span>
  <span m='990630'>0.</span> <span m='991520'>This</span> <span
  m='991700'>pole</span> <span m='992300'>is</span> <span m='992480'>at</span>
  <span m='992630'>an</span> <span m='992720'>angle</span> <span
  m='993290'>of</span> <span m='993770'>minus</span> <span
  m='994200'>omega</span> <span m='994690'>0.</span> <span m='996410'>And</span>
  <span m='997010'>using</span> <span m='997670'>this</span> <span
  m='997910'>notion</span> <span m='998510'>of</span> <span
  m='998660'>interpreting</span> <span m='999230'>the</span> <span
  m='999320'>frequency</span> <span m='999830'>response</span> <span
  m='1000660'>geometrically,</span> <span m='1002200'>let's</span> <span
  m='1002680'>just</span> <span m='1003250'>sketch</span> <span
  m='1003730'>out</span> <span m='1004780'>roughly</span> <span
  m='1005620'>what</span> <span m='1006010'>we</span> <span
  m='1006160'>would</span> <span m='1006280'>expect</span> <span
  m='1007000'>the</span> <span m='1007090'>frequency</span> <span
  m='1007630'>response</span> <span m='1008290'>to</span> <span
  m='1008440'>look</span> <span m='1008650'>like.</span> </p><p><span
  m='1011370'>Well,</span> <span m='1011690'>let's</span> <span
  m='1011930'>see.</span> <span m='1012980'>If</span> <span
  m='1013460'>we</span> <span m='1013670'>start</span> <span
  m='1014270'>at</span> <span m='1015050'>omega</span> <span
  m='1015610'>equals</span> <span m='1015980'>zero,</span> <span
  m='1017540'>then</span> <span m='1018320'>we</span> <span
  m='1018500'>have</span> <span m='1019100'>a</span> <span
  m='1019160'>vector</span> <span m='1020180'>from</span> <span
  m='1020390'>this</span> <span m='1020570'>pole</span> <span
  m='1022550'>and</span> <span m='1023170'>a</span> <span
  m='1023260'>vector</span> <span m='1023900'>from</span> <span
  m='1024109'>this</span> <span m='1024319'>pole.</span> <span
  m='1026119'>The</span> <span m='1026359'>resulting</span> <span
  m='1026900'>value</span> <span m='1027260'>of</span> <span
  m='1027349'>the</span> <span m='1027470'>frequency</span> <span
  m='1027980'>response</span> <span m='1028670'>is</span> <span
  m='1028880'>1</span> <span m='1029750'>over</span> <span
  m='1030230'>the</span> <span m='1030380'>product</span> <span
  m='1031160'>of</span> <span m='1031310'>those</span> <span
  m='1031550'>two</span> <span m='1031760'>vectors.</span> <span
  m='1034660'>As</span> <span m='1035470'>we</span> <span
  m='1035650'>move</span> <span m='1036400'>around</span> <span
  m='1037329'>the</span> <span m='1037450'>unit</span> <span
  m='1037750'>circle</span> <span m='1038500'>from</span> <span
  m='1038740'>omega</span> <span m='1039160'>equals</span> <span
  m='1039490'>0,</span> <span m='1042010'>let's</span> <span
  m='1042220'>say,</span> <span m='1042609'>to</span> <span
  m='1042910'>some</span> <span m='1043210'>point</span> <span
  m='1043560'>that's</span> <span m='1043720'>closer</span> <span
  m='1045339'>to</span> <span m='1045880'>omega</span> <span
  m='1046359'>0,</span> <span m='1048580'>then</span> <span
  m='1049230'>this</span> <span m='1049500'>vector</span> <span
  m='1050460'>gets</span> <span m='1050670'>changed</span> <span
  m='1051540'>to</span> <span m='1051690'>that</span> <span
  m='1051990'>one.</span> <span m='1053670'>And</span> <span
  m='1053820'>this</span> <span m='1054030'>vector</span> <span
  m='1055350'>gets</span> <span m='1055590'>changed</span> <span
  m='1056800'>to</span> <span m='1056820'>this</span> <span
  m='1057090'>one.</span> </p><p><span m='1058590'>Well,</span> <span
  m='1059460'>we</span> <span m='1059580'>can</span> <span
  m='1059730'>see</span> <span m='1059940'>what's</span> <span
  m='1060150'>happening</span> <span m='1061050'>to</span> <span
  m='1061440'>the</span> <span m='1061560'>vector</span> <span
  m='1061980'>lengths.</span> <span m='1063210'>This</span> <span
  m='1063480'>vector</span> <span m='1064770'>is</span> <span
  m='1064980'>getting</span> <span m='1065640'>shorter</span> <span
  m='1066630'>as</span> <span m='1067200'>we</span> <span
  m='1067380'>approach</span> <span m='1068490'>omega</span> <span
  m='1068970'>equal</span> <span m='1069360'>to</span> <span m='1069540'>omega
  0.</span> <span m='1071160'>This</span> <span m='1071370'>vector</span> <span
  m='1071940'>is</span> <span m='1072120'>getting</span> <span
  m='1072420'>longer.</span> <span m='1073680'>But</span> <span
  m='1074010'>you</span> <span m='1074160'>can</span> <span
  m='1074310'>imagine--</span> <span m='1074880'>and</span> <span
  m='1075030'>I</span> <span m='1075120'>think</span> <span
  m='1075360'>it</span> <span m='1075450'>should</span> <span
  m='1075660'>be</span> <span m='1075750'>relatively</span> <span
  m='1076320'>clear</span> <span m='1076590'>from</span> <span
  m='1076740'>the</span> <span m='1076830'>picture--</span> <span
  m='1077880'>that</span> <span m='1078240'>this</span> <span
  m='1078480'>vector</span> <span m='1078900'>is</span> <span
  m='1079020'>getting</span> <span m='1079320'>shorter</span> <span
  m='1079770'>faster</span> <span m='1080340'>than</span> <span
  m='1080490'>this</span> <span m='1080670'>one</span> <span
  m='1080880'>is</span> <span m='1080970'>getting</span> <span
  m='1081270'>longer.</span> <span m='1084010'>It</span> <span
  m='1084820'>seems</span> <span m='1085390'>relatively</span> <span
  m='1086020'>clear</span> <span m='1086350'>from</span> <span
  m='1086560'>a</span> <span m='1086620'>geometric</span> <span
  m='1087160'>picture</span> <span m='1088570'>that</span> <span
  m='1088720'>the</span> <span m='1088840'>product</span> <span
  m='1089890'>of</span> <span m='1090010'>the</span> <span
  m='1090100'>lengths</span> <span m='1090430'>of</span> <span
  m='1090520'>these</span> <span m='1090760'>two</span> <span
  m='1091000'>vectors</span> <span m='1092440'>is</span> <span
  m='1092590'>smaller</span> <span m='1093940'>when</span> <span
  m='1094240'>omega</span> <span m='1094660'>is</span> <span
  m='1094780'>closer</span> <span m='1095260'>to</span> <span m='1095470'>omega
  0</span> <span m='1096790'>than,</span> <span m='1097270'>let's</span> <span
  m='1097510'>say,</span> <span m='1098170'>when</span> <span
  m='1098980'>omega</span> <span m='1099910'>is</span> <span
  m='1100060'>equal</span> <span m='1100330'>to</span> <span
  m='1100450'>0.</span> </p><p><span m='1101710'>So</span> <span
  m='1102280'>consequently,</span> <span m='1103090'>we</span> <span
  m='1103240'>would</span> <span m='1103360'>expect</span> <span
  m='1105010'>the</span> <span m='1105100'>magnitude</span> <span
  m='1105580'>of</span> <span m='1105640'>the</span> <span
  m='1105730'>frequency</span> <span m='1106240'>response</span> <span
  m='1107440'>to</span> <span m='1107530'>start</span> <span
  m='1107900'>at</span> <span m='1108010'>some</span> <span
  m='1108250'>value.</span> <span m='1110200'>As</span> <span
  m='1110380'>we</span> <span m='1110500'>get</span> <span m='1110800'>in</span>
  <span m='1110950'>the</span> <span m='1111040'>vicinity</span> <span
  m='1111880'>of</span> <span m='1112120'>omega</span> <span
  m='1112480'>equal</span> <span m='1112750'>to</span> <span m='1112930'>omega
  0,</span> <span m='1114160'>we</span> <span m='1114280'>would</span> <span
  m='1114400'>expect</span> <span m='1114760'>that</span> <span
  m='1114910'>frequency</span> <span m='1115420'>response</span> <span
  m='1115960'>to</span> <span m='1116080'>peak.</span> <span
  m='1117640'>As</span> <span m='1118270'>we</span> <span
  m='1118420'>pass</span> <span m='1118840'>that</span> <span
  m='1119080'>pole,</span> <span m='1119980'>the</span> <span
  m='1120070'>frequency</span> <span m='1120550'>response</span> <span
  m='1121090'>will</span> <span m='1121210'>now</span> <span
  m='1121660'>begin</span> <span m='1121990'>to</span> <span
  m='1122110'>decrease.</span> <span m='1123640'>And</span> <span
  m='1124210'>clearly,</span> <span m='1125530'>when</span> <span
  m='1126400'>we</span> <span m='1126820'>are</span> <span m='1127150'>at</span>
  <span m='1127540'>omega</span> <span m='1128500'>equal</span> <span
  m='1128890'>to</span> <span m='1129040'>pi,</span> <span
  m='1133160'>the</span> <span m='1133280'>product</span> <span
  m='1133940'>of</span> <span m='1134570'>the</span> <span
  m='1134690'>lengths</span> <span m='1135320'>of</span> <span
  m='1135470'>these</span> <span m='1135710'>two</span> <span
  m='1135920'>vectors</span> <span m='1137030'>is</span> <span
  m='1137150'>considerably</span> <span m='1137810'>longer</span> <span
  m='1138860'>than</span> <span m='1139070'>the</span> <span
  m='1139190'>products</span> <span m='1139610'>of</span> <span
  m='1139670'>the</span> <span m='1139790'>lengths</span> <span
  m='1140240'>of</span> <span m='1140390'>the</span> <span
  m='1140510'>vectors</span> <span m='1141140'>at</span> <span
  m='1141260'>omega</span> <span m='1141590'>equals</span> <span
  m='1141890'>0.</span> </p><p><span m='1142970'>So</span> <span
  m='1143600'>on</span> <span m='1143720'>the</span> <span
  m='1143810'>basis</span> <span m='1144290'>of</span> <span
  m='1144380'>that</span> <span m='1144590'>argument,</span> <span
  m='1145460'>we</span> <span m='1145640'>can</span> <span
  m='1145820'>see</span> <span m='1146270'>that</span> <span
  m='1146450'>roughly</span> <span m='1147470'>what</span> <span
  m='1148160'>we</span> <span m='1148310'>expect</span> <span
  m='1148670'>the</span> <span m='1148760'>frequency</span> <span
  m='1149240'>response</span> <span m='1150020'>to</span> <span
  m='1150200'>do</span> <span m='1151500'>is</span> <span
  m='1151880'>begin</span> <span m='1152170'>at</span> <span
  m='1152270'>some</span> <span m='1152510'>value,</span> <span
  m='1153950'>increase</span> <span m='1154790'>as</span> <span
  m='1155090'>we</span> <span m='1155240'>approach</span> <span
  m='1155870'>the</span> <span m='1155960'>pole</span> <span
  m='1156440'>at</span> <span m='1156530'>omega</span> <span
  m='1156890'>equals</span> <span m='1157220'>omega 0,</span> <span
  m='1159170'>decrease</span> <span m='1160970'>as</span> <span
  m='1161600'>we</span> <span m='1161750'>pass</span> <span
  m='1162140'>the</span> <span m='1162260'>pole</span> <span
  m='1163220'>heading</span> <span m='1163550'>toward</span> <span
  m='1163880'>pi.</span> <span m='1165740'>And</span> <span
  m='1165860'>then</span> <span m='1166370'>from</span> <span
  m='1166610'>pi</span> <span m='1167240'>around</span> <span
  m='1167570'>to</span> <span m='1167900'>pi,</span> <span m='1168740'>or</span>
  <span m='1168890'>equivalently</span> <span m='1169490'>from</span> <span
  m='1169670'>0</span> <span m='1170270'>around</span> <span
  m='1170630'>to</span> <span m='1170750'>minus</span> <span
  m='1171170'>pi,</span> <span m='1172370'>we</span> <span
  m='1172520'>would</span> <span m='1172640'>expect</span> <span
  m='1173300'>the</span> <span m='1173420'>reciprocal</span> <span
  m='1173960'>behavior.</span> <span m='1174530'>That</span> <span
  m='1174740'>is,</span> <span m='1175430'>the</span> <span
  m='1175520'>frequency</span> <span m='1176000'>response</span> <span
  m='1176930'>would</span> <span m='1177080'>increase,</span> <span
  m='1178130'>peak</span> <span m='1179000'>in</span> <span
  m='1179090'>the</span> <span m='1179180'>vicinity</span> <span
  m='1179930'>of</span> <span m='1180740'>this</span> <span
  m='1180950'>pole</span> <span m='1181370'>in</span> <span
  m='1181460'>the</span> <span m='1181520'>lower</span> <span
  m='1181850'>half</span> <span m='1182120'>of</span> <span
  m='1182210'>the</span> <span m='1182300'>z-plane,</span> <span
  m='1183470'>and</span> <span m='1183620'>then</span> <span
  m='1184310'>return</span> <span m='1184940'>to</span> <span
  m='1185120'>the</span> <span m='1185210'>same</span> <span
  m='1185540'>value</span> <span m='1186260'>that</span> <span
  m='1186380'>it</span> <span m='1186470'>started</span> <span
  m='1186890'>from.</span> <span m='1187610'>And</span> <span
  m='1187730'>of</span> <span m='1187820'>course,</span> <span
  m='1188310'>it'll</span> <span m='1188690'>be</span> <span
  m='1188900'>periodic</span> <span m='1189680'>as</span> <span
  m='1190100'>we</span> <span m='1190280'>run</span> <span
  m='1190490'>around</span> <span m='1190730'>the</span> <span
  m='1190820'>unit</span> <span m='1191090'>circle.</span> </p><p><span
  m='1193070'>Well,</span> <span m='1193910'>this</span> <span
  m='1194150'>is</span> <span m='1194270'>a</span> <span
  m='1194360'>resonant</span> <span m='1195530'>characteristic,</span> <span
  m='1197180'>reminiscent</span> <span m='1198110'>in</span> <span
  m='1198530'>the</span> <span m='1198650'>analog</span> <span
  m='1199100'>case</span> <span m='1199700'>of</span> <span
  m='1200390'>what</span> <span m='1200540'>we</span> <span
  m='1200690'>would</span> <span m='1200840'>expect</span> <span
  m='1201410'>from</span> <span m='1202010'>a</span> <span
  m='1202070'>complex</span> <span m='1202600'>conjugate</span> <span
  m='1203060'>pole</span> <span m='1203400'>pair</span> <span
  m='1204290'>close</span> <span m='1204710'>to</span> <span
  m='1205490'>the</span> <span m='1205580'>j omega</span> <span
  m='1206180'>axis</span> <span m='1206990'>that's</span> <span
  m='1207200'>in</span> <span m='1207320'>the</span> <span
  m='1207620'>s-plane.</span> <span m='1208760'>And</span> <span
  m='1208880'>in</span> <span m='1209000'>fact,</span> <span
  m='1209390'>of</span> <span m='1209480'>course,</span> <span
  m='1209840'>in</span> <span m='1209930'>the</span> <span
  m='1210050'>s-plane,</span> <span m='1211130'>we</span> <span
  m='1211280'>have</span> <span m='1211520'>exactly</span> <span
  m='1211970'>the</span> <span m='1212090'>same</span> <span
  m='1212330'>kinds</span> <span m='1212720'>of</span> <span
  m='1212810'>geometrical</span> <span m='1213500'>arguments</span> <span
  m='1214490'>to</span> <span m='1214640'>allow</span> <span
  m='1214970'>us</span> <span m='1215180'>to</span> <span
  m='1215330'>roughly</span> <span m='1215720'>sketch</span> <span
  m='1216140'>out</span> <span m='1216740'>the</span> <span
  m='1216980'>frequency</span> <span m='1217520'>response.</span> <span
  m='1218570'>The</span> <span m='1219020'>only</span> <span
  m='1219440'>real</span> <span m='1219710'>important</span> <span
  m='1220190'>difference</span> <span m='1220880'>is</span> <span
  m='1221090'>that</span> <span m='1221420'>in</span> <span
  m='1221540'>the</span> <span m='1221630'>discrete</span> <span
  m='1222080'>time</span> <span m='1222410'>case,</span> <span
  m='1223220'>it's</span> <span m='1223370'>the</span> <span
  m='1223490'>unit</span> <span m='1223760'>circle,</span> <span
  m='1225270'>which</span> <span m='1225350'>is</span> <span
  m='1225440'>the</span> <span m='1225560'>locus</span> <span
  m='1226010'>in</span> <span m='1226100'>the</span> <span
  m='1226190'>z-plane</span> <span m='1226760'>that</span> <span
  m='1226880'>we're</span> <span m='1227000'>looking</span> <span
  m='1227360'>at.</span> <span m='1228020'>In</span> <span
  m='1228110'>the</span> <span m='1228200'>continuous</span> <span
  m='1228740'>time</span> <span m='1229010'>case,</span> <span
  m='1229550'>it's</span> <span m='1230090'>the</span> <span
  m='1230270'>vertical,</span> <span m='1230930'>or</span> <span m='1231120'>j
  omega</span> <span m='1231590'>axis</span> <span m='1232090'>in</span> <span
  m='1232190'>the</span> <span m='1232460'>s-plane</span> <span
  m='1233120'>that</span> <span m='1233270'>we're</span> <span
  m='1233360'>looking</span> <span m='1233720'>at.</span> </p><p><span
  m='1235230'>Well,</span> <span m='1236150'>this</span> <span
  m='1236660'>shouldn't</span> <span m='1236930'>be</span> <span
  m='1237080'>particularly</span> <span m='1237680'>evident</span> <span
  m='1238070'>from</span> <span m='1238280'>what</span> <span
  m='1238400'>we've</span> <span m='1238610'>done</span> <span
  m='1238850'>here.</span> <span m='1239270'>But</span> <span
  m='1240380'>by</span> <span m='1240590'>inference</span> <span
  m='1241610'>or</span> <span m='1242210'>by</span> <span
  m='1242750'>carrying</span> <span m='1243200'>your</span> <span
  m='1243350'>intuition</span> <span m='1245120'>from</span> <span
  m='1245300'>the</span> <span m='1245390'>continuous</span> <span
  m='1245900'>time</span> <span m='1246200'>to</span> <span
  m='1246320'>the</span> <span m='1246440'>discrete</span> <span
  m='1246860'>time,</span> <span m='1248670'>can</span> <span
  m='1249270'>you</span> <span m='1249450'>guess</span> <span
  m='1249990'>at</span> <span m='1250440'>what</span> <span
  m='1251040'>you</span> <span m='1251160'>would</span> <span
  m='1251310'>expect</span> <span m='1252600'>the</span> <span
  m='1252720'>unit</span> <span m='1253020'>sample</span> <span
  m='1253770'>response</span> <span m='1254550'>of</span> <span
  m='1254680'>a</span> <span m='1254760'>system</span> <span
  m='1255750'>with</span> <span m='1255930'>this</span> <span
  m='1256490'>pole-zero</span> <span m='1257160'>pattern</span> <span
  m='1257820'>to</span> <span m='1257940'>look</span> <span
  m='1258150'>like?</span> <span m='1260460'>Well,</span> <span
  m='1261350'>it</span> <span m='1261440'>would</span> <span
  m='1261590'>look</span> <span m='1262130'>like</span> <span
  m='1262700'>the</span> <span m='1262820'>discrete</span> <span
  m='1263210'>time</span> <span m='1263510'>counterpart</span> <span
  m='1264320'>of</span> <span m='1264500'>what</span> <span
  m='1264650'>happens</span> <span m='1265040'>in</span> <span
  m='1265170'>the</span> <span m='1265370'>continuous</span> <span
  m='1266000'>time</span> <span m='1266270'>case.</span> <span
  m='1267110'>That</span> <span m='1267320'>is,</span> <span
  m='1267890'>it</span> <span m='1268010'>would</span> <span
  m='1268190'>look</span> <span m='1268760'>like</span> <span
  m='1269360'>a</span> <span m='1269660'>damped</span> <span
  m='1270440'>sinusoidal</span> <span m='1271460'>sequence</span> <span
  m='1272810'>with</span> <span m='1272970'>the</span> <span
  m='1273080'>damping</span> <span m='1274220'>influenced</span> <span
  m='1275120'>by</span> <span m='1275600'>the</span> <span
  m='1275750'>distance</span> <span m='1276380'>of</span> <span
  m='1276530'>these</span> <span m='1276740'>poles</span> <span
  m='1277640'>from</span> <span m='1277850'>the</span> <span
  m='1277940'>unit</span> <span m='1278220'>circle.</span> <span
  m='1279230'>The</span> <span m='1279350'>closer</span> <span
  m='1279800'>the</span> <span m='1279890'>pole</span> <span
  m='1280220'>is</span> <span m='1280430'>to</span> <span m='1280550'>the</span>
  <span m='1280640'>unit</span> <span m='1280940'>circle,</span> <span
  m='1281990'>the</span> <span m='1282110'>sharper</span> <span
  m='1282590'>this</span> <span m='1282800'>resonant</span> <span
  m='1283220'>peak</span> <span m='1283490'>will</span> <span
  m='1283700'>be</span> <span m='1284570'>and</span> <span
  m='1285170'>the</span> <span m='1285260'>less</span> <span
  m='1285590'>damping</span> <span m='1286190'>on</span> <span
  m='1286340'>the</span> <span m='1286430'>sinusoid.</span> </p><p><span
  m='1289710'>One</span> <span m='1290190'>additional</span> <span
  m='1291000'>point</span> <span m='1291660'>to</span> <span
  m='1292170'>remind</span> <span m='1292710'>you</span> <span
  m='1292890'>of--</span> <span m='1295200'>I</span> <span
  m='1295590'>made</span> <span m='1295800'>reference</span> <span
  m='1296250'>to</span> <span m='1296340'>this</span> <span
  m='1296580'>in</span> <span m='1296700'>an</span> <span
  m='1296820'>earlier</span> <span m='1297150'>lecture.</span> <span
  m='1298350'>But</span> <span m='1300050'>notice</span> <span
  m='1300620'>that</span> <span m='1301100'>in</span> <span
  m='1301430'>talking</span> <span m='1301880'>about</span> <span
  m='1302180'>the</span> <span m='1302270'>Z-transform</span> <span
  m='1303140'>poles</span> <span m='1303500'>and</span> <span
  m='1303590'>zeros,</span> <span m='1304030'>et</span> <span
  m='1304160'>cetera</span> <span m='1304550'>here,</span> <span
  m='1305690'>I</span> <span m='1305810'>didn't</span> <span
  m='1306680'>say</span> <span m='1307310'>what</span> <span
  m='1307520'>the</span> <span m='1307610'>region</span> <span
  m='1307910'>of</span> <span m='1308000'>convergence</span> <span
  m='1308600'>was.</span> <span m='1309650'>Or</span> <span
  m='1309770'>at</span> <span m='1309830'>least,</span> <span
  m='1310010'>I</span> <span m='1310070'>didn't</span> <span
  m='1310250'>say</span> <span m='1310430'>explicitly</span> <span
  m='1311060'>what</span> <span m='1311180'>the</span> <span
  m='1311270'>region</span> <span m='1311570'>of</span> <span
  m='1311660'>convergence</span> <span m='1312260'>was.</span> <span
  m='1313220'>But</span> <span m='1313790'>did</span> <span m='1314090'>I</span>
  <span m='1314270'>say</span> <span m='1315140'>implicitly</span> <span
  m='1315770'>what</span> <span m='1315950'>it</span> <span
  m='1316070'>is?</span> </p><p><span m='1317060'>Well,</span> <span
  m='1317450'>sure</span> <span m='1317720'>I</span> <span
  m='1317840'>did</span> <span m='1318060'>because</span> <span
  m='1319130'>what</span> <span m='1319370'>I</span> <span
  m='1319490'>said</span> <span m='1319910'>or</span> <span
  m='1320000'>what</span> <span m='1320210'>I've</span> <span
  m='1320300'>been</span> <span m='1320450'>assuming</span> <span
  m='1321800'>is</span> <span m='1321980'>that</span> <span
  m='1322160'>the</span> <span m='1322250'>systems</span> <span
  m='1322760'>that</span> <span m='1322850'>we've</span> <span
  m='1323030'>been</span> <span m='1323150'>talking</span> <span
  m='1323600'>about</span> <span m='1325100'>can</span> <span
  m='1325250'>be</span> <span m='1325370'>described</span> <span
  m='1326030'>in</span> <span m='1326120'>terms</span> <span
  m='1326480'>of</span> <span m='1326570'>a</span> <span
  m='1326630'>frequency</span> <span m='1327200'>response.</span> <span
  m='1328640'>In</span> <span m='1328760'>other</span> <span
  m='1328940'>words,</span> <span m='1329430'>the</span> <span
  m='1329450'>unit</span> <span m='1329720'>sample</span> <span
  m='1330140'>response</span> <span m='1330740'>has</span> <span
  m='1330920'>a</span> <span m='1330980'>Fourier</span> <span
  m='1331400'>transform.</span> <span m='1333190'>Well</span> <span
  m='1333380'>for</span> <span m='1333530'>that</span> <span
  m='1333740'>to</span> <span m='1333860'>be</span> <span m='1333980'>the</span>
  <span m='1334100'>case,</span> <span m='1335060'>the</span> <span
  m='1335150'>region</span> <span m='1335480'>of</span> <span
  m='1335570'>convergence</span> <span m='1336200'>has</span> <span
  m='1336440'>to</span> <span m='1336560'>include</span> <span
  m='1337310'>the</span> <span m='1337400'>unit</span> <span
  m='1337670'>circle.</span> <span m='1338850'>And</span> <span
  m='1338950'>then,</span> <span m='1339020'>we</span> <span
  m='1339110'>can</span> <span m='1339290'>use</span> <span
  m='1339560'>all</span> <span m='1339710'>those</span> <span
  m='1339950'>other</span> <span m='1340160'>rules</span> <span
  m='1340700'>of</span> <span m='1340850'>regions</span> <span
  m='1341240'>of</span> <span m='1341360'>convergences</span> <span
  m='1343100'>to</span> <span m='1343490'>allow</span> <span
  m='1343910'>us</span> <span m='1344420'>to</span> <span
  m='1344540'>figure</span> <span m='1344930'>out</span> <span
  m='1345170'>from</span> <span m='1345410'>there</span> <span
  m='1346820'>how</span> <span m='1347030'>far</span> <span
  m='1347990'>on</span> <span m='1348110'>both</span> <span
  m='1348350'>sides</span> <span m='1348980'>of</span> <span
  m='1349100'>the</span> <span m='1349190'>unit</span> <span
  m='1349460'>circle</span> <span m='1350150'>the</span> <span
  m='1350270'>region</span> <span m='1350570'>of</span> <span
  m='1350660'>convergence</span> <span m='1351230'>extends.</span> </p><p><span
  m='1354390'>All</span> <span m='1354450'>right,</span> <span
  m='1354660'>well</span> <span m='1355050'>this</span> <span
  m='1355290'>is,</span> <span m='1355440'>then,</span> <span
  m='1355950'>a</span> <span m='1356130'>geometrical</span> <span
  m='1358260'>interpretation</span> <span m='1359370'>of</span> <span
  m='1359520'>the</span> <span m='1359610'>frequency</span> <span
  m='1360150'>response.</span> <span m='1361320'>It's</span> <span
  m='1361500'>often</span> <span m='1361830'>useful</span> <span
  m='1362790'>as</span> <span m='1363000'>a</span> <span
  m='1363060'>rough</span> <span m='1363360'>guide</span> <span
  m='1363930'>in</span> <span m='1365130'>getting</span> <span
  m='1365670'>a</span> <span m='1365820'>general</span> <span
  m='1366270'>picture</span> <span m='1366750'>of</span> <span
  m='1366900'>what</span> <span m='1367050'>the</span> <span
  m='1367140'>frequency</span> <span m='1367590'>response</span> <span
  m='1368400'>might</span> <span m='1368610'>look</span> <span
  m='1368820'>like.</span> <span m='1369240'>Although,</span> <span
  m='1370440'>for</span> <span m='1370650'>complicated</span> <span
  m='1371310'>cases,</span> <span m='1372120'>it's</span> <span
  m='1372420'>often</span> <span m='1372720'>difficult</span> <span
  m='1373680'>to</span> <span m='1373800'>get</span> <span
  m='1374070'>precise</span> <span m='1374550'>details</span> <span
  m='1375120'>about</span> <span m='1375390'>the</span> <span
  m='1375480'>frequency</span> <span m='1375930'>response,</span> <span
  m='1376380'>which</span> <span m='1376560'>of</span> <span
  m='1376650'>course,</span> <span m='1377020'>we</span> <span
  m='1377040'>could</span> <span m='1377700'>also</span> <span
  m='1378060'>get</span> <span m='1378270'>algebraically.</span> </p><p><span
  m='1381210'>Well</span> <span m='1381560'>now,</span> <span
  m='1382070'>I'd</span> <span m='1382790'>like</span> <span
  m='1383210'>to,</span> <span m='1384320'>at</span> <span
  m='1384410'>least</span> <span m='1384650'>temporarily,</span> <span
  m='1386300'>change</span> <span m='1386690'>gears</span> <span
  m='1387380'>or</span> <span m='1387800'>topics</span> <span
  m='1389180'>and</span> <span m='1390140'>talk</span> <span
  m='1390770'>about</span> <span m='1392480'>the</span> <span
  m='1393290'>issue</span> <span m='1393890'>of</span> <span
  m='1394580'>properties</span> <span m='1395390'>of</span> <span
  m='1395540'>the Z-transform</span> <span m='1397730'>in</span> <span
  m='1398360'>talking</span> <span m='1398720'>about</span> <span
  m='1398930'>the</span> <span m='1399050'>properties</span> <span
  m='1399920'>and</span> <span m='1400070'>working</span> <span
  m='1400430'>some</span> <span m='1400610'>examples</span> <span
  m='1402170'>to</span> <span m='1402440'>illustrate</span> <span
  m='1402950'>the</span> <span m='1403040'>use</span> <span
  m='1403250'>of</span> <span m='1403340'>the</span> <span
  m='1403430'>properties</span> <span m='1403970'>of</span> <span
  m='1404030'>the Z-transform.</span> <span m='1405620'>In</span> <span
  m='1405740'>fact,</span> <span m='1406250'>I'll</span> <span
  m='1406610'>have</span> <span m='1406850'>occasion</span> <span
  m='1407600'>to</span> <span m='1407750'>make</span> <span
  m='1407960'>reference</span> <span m='1408560'>back</span> <span
  m='1409400'>to</span> <span m='1409880'>this</span> <span
  m='1410060'>geometric</span> <span m='1411230'>interpretation</span> <span
  m='1411980'>of</span> <span m='1412040'>the</span> <span
  m='1412160'>frequency</span> <span m='1412640'>response</span> <span
  m='1413600'>to</span> <span m='1413720'>help</span> <span
  m='1414110'>with</span> <span m='1414470'>at</span> <span
  m='1414590'>least</span> <span m='1414860'>one</span> <span
  m='1415010'>of</span> <span m='1415100'>the</span> <span
  m='1415220'>examples.</span> <span m='1417180'>So</span> <span
  m='1417650'>now</span> <span m='1418070'>I'd</span> <span
  m='1418220'>like</span> <span m='1418520'>to</span> <span
  m='1419450'>turn</span> <span m='1419690'>our</span> <span
  m='1419840'>attention,</span> <span m='1420570'>then,</span> <span
  m='1421490'>to</span> <span m='1422270'>the</span> <span
  m='1422690'>question</span> <span m='1423920'>or</span> <span
  m='1424340'>the</span> <span m='1424460'>topic</span> <span
  m='1425570'>of</span> <span m='1426290'>the</span> <span
  m='1426380'>properties</span> <span m='1427310'>of</span> <span
  m='1427460'>the</span> <span m='1427560'>Z-transform.</span> </p><p><span
  m='1427760'>Well,</span> <span m='1430570'>first</span> <span
  m='1430870'>of</span> <span m='1430990'>all,</span> <span
  m='1431530'>why</span> <span m='1431650'>do</span> <span m='1431740'>we</span>
  <span m='1431860'>want</span> <span m='1432070'>properties</span> <span
  m='1432940'>of</span> <span m='1433090'>the Z-transform?</span> <span
  m='1433360'>The</span> <span m='1433820'>Z-transform</span> <span
  m='1434530'>has</span> <span m='1434770'>properties.</span> <span
  m='1435680'>Why</span> <span m='1435790'>do</span> <span m='1435880'>we</span>
  <span m='1436000'>want</span> <span m='1436240'>these</span> <span
  m='1436420'>properties?</span> <span m='1437780'>One</span> <span
  m='1437860'>of</span> <span m='1437980'>the</span> <span
  m='1438100'>reasons--</span> <span m='1438830'>it's</span> <span
  m='1438970'>a</span> <span m='1439000'>very</span> <span
  m='1439180'>practical</span> <span m='1439750'>reason--</span> <span
  m='1441100'>is</span> <span m='1441340'>that</span> <span
  m='1442060'>the</span> <span m='1442180'>properties</span> <span
  m='1442810'>of</span> <span m='1442930'>the Z-transform</span> <span
  m='1444760'>help</span> <span m='1445090'>us</span> <span
  m='1445510'>in</span> <span m='1445660'>calculating</span> <span
  m='1446980'>Z-transforms</span> <span m='1448510'>and</span> <span
  m='1448910'>inverse</span> <span m='1449290'>Z-transforms.</span> <span
  m='1451210'>And</span> <span m='1451690'>they</span> <span
  m='1451870'>also,</span> <span m='1452470'>obviously,</span> <span
  m='1454180'>provide</span> <span m='1454750'>a</span> <span
  m='1454810'>certain</span> <span m='1455140'>amount</span> <span
  m='1455590'>of</span> <span m='1455770'>intuition</span> <span
  m='1456380'>and</span> <span m='1456520'>insight</span> <span
  m='1457600'>with</span> <span m='1457840'>regard</span> <span
  m='1458260'>to</span> <span m='1458410'>generally</span> <span
  m='1459010'>dealing</span> <span m='1459910'>with</span> <span
  m='1460480'>Z-transforms</span> <span m='1461500'>and</span> <span
  m='1461650'>their</span> <span m='1461830'>inverses.</span> </p><p><span
  m='1464500'>Well,</span> <span m='1465010'>there</span> <span
  m='1465130'>are</span> <span m='1465160'>a</span> <span m='1465220'>lot</span>
  <span m='1465430'>of</span> <span m='1465520'>properties.</span> <span
  m='1466670'>In</span> <span m='1466690'>fact,</span> <span
  m='1467590'>there</span> <span m='1467800'>are</span> <span
  m='1467830'>trivial</span> <span m='1468250'>properties.</span> <span
  m='1468820'>There are</span> <span m='1468910'>very</span> <span
  m='1469120'>complicated</span> <span m='1469840'>properties.</span> <span
  m='1471370'>There</span> <span m='1471820'>are</span> <span
  m='1472060'>properties</span> <span m='1472690'>that</span> <span
  m='1473410'>we</span> <span m='1473590'>more</span> <span
  m='1473800'>commonly</span> <span m='1474850'>tend</span> <span
  m='1475060'>to</span> <span m='1475180'>carry</span> <span
  m='1475570'>around.</span> <span m='1476650'>And</span> <span
  m='1477760'>I've</span> <span m='1478030'>listed</span> <span
  m='1478870'>a</span> <span m='1478930'>few</span> <span
  m='1479830'>that</span> <span m='1480820'>shouldn't</span> <span
  m='1481210'>be</span> <span m='1481390'>considered</span> <span
  m='1481900'>to</span> <span m='1482020'>be</span> <span
  m='1482170'>exhaustive</span> <span m='1483430'>but</span> <span
  m='1483880'>generally</span> <span m='1484660'>tend</span> <span
  m='1484930'>to</span> <span m='1485050'>be</span> <span m='1485200'>the</span>
  <span m='1485320'>properties</span> <span m='1486310'>that</span> <span
  m='1487600'>turn</span> <span m='1487870'>out</span> <span
  m='1488320'>to</span> <span m='1488470'>be</span> <span m='1488620'>the</span>
  <span m='1488710'>handiest.</span> <span m='1489280'>That</span> <span
  m='1489460'>is,</span> <span m='1490150'>these</span> <span
  m='1490390'>are</span> <span m='1490450'>the</span> <span
  m='1490540'>properties,</span> <span m='1491170'>at</span> <span
  m='1491260'>a</span> <span m='1491320'>minimum,</span> <span
  m='1492280'>that</span> <span m='1492730'>you</span> <span
  m='1492910'>should</span> <span m='1493060'>carry</span> <span
  m='1493450'>around</span> <span m='1493780'>in</span> <span
  m='1493840'>your</span> <span m='1493960'>back</span> <span
  m='1494200'>pocket.</span> </p><p><span m='1496820'>Well,</span> <span
  m='1497210'>let's</span> <span m='1497420'>see.</span> <span
  m='1498380'>We're</span> <span m='1498500'>talking</span> <span
  m='1498920'>about</span> <span m='1499190'>a</span> <span
  m='1499250'>sequence,</span> <span m='1499730'>x</span> <span
  m='1500000'>of</span> <span m='1500120'>n</span> <span m='1501590'>with</span>
  <span m='1501770'>a</span> <span m='1501800'>Z-transform,</span> <span
  m='1502700'>x</span> <span m='1502910'>of</span> <span m='1503030'>z.</span>
  <span m='1504580'>One</span> <span m='1504770'>of</span> <span
  m='1504860'>the</span> <span m='1504950'>properties</span> <span
  m='1505910'>that</span> <span m='1506510'>we've</span> <span
  m='1506990'>taken</span> <span m='1507320'>advantage</span> <span
  m='1507860'>of</span> <span m='1508130'>already</span> <span
  m='1509150'>throughout</span> <span m='1509450'>the</span> <span
  m='1509540'>entire</span> <span m='1509900'>discussion</span> <span
  m='1510410'>of</span> <span m='1510500'>the Z-transform</span> <span
  m='1512120'>is</span> <span m='1512240'>the</span> <span
  m='1512360'>fact</span> <span m='1512720'>that</span> <span
  m='1512870'>the</span> <span m='1512960'>Z-transform</span> <span
  m='1514310'>maps</span> <span m='1515060'>convolution</span> <span
  m='1516530'>to</span> <span m='1516760'>multiplication.</span> <span
  m='1519310'>If</span> <span m='1519550'>I</span> <span m='1519670'>have</span>
  <span m='1519880'>the</span> <span m='1519970'>convolution</span> <span
  m='1520960'>of</span> <span m='1521110'>two</span> <span
  m='1521260'>sequences,</span> <span m='1523390'>then</span> <span
  m='1524530'>the</span> <span m='1524830'>resulting</span> <span
  m='1525400'>Z-transform</span> <span m='1526660'>is</span> <span
  m='1527500'>the</span> <span m='1527620'>product</span> <span
  m='1528610'>of</span> <span m='1529300'>the</span> <span
  m='1529390'>Z-transforms.</span> </p><p><span m='1531650'>The</span> <span
  m='1531710'>second</span> <span m='1532100'>property,</span> <span
  m='1533460'>which</span> <span m='1533870'>is</span> <span
  m='1534200'>often</span> <span m='1534560'>very</span> <span
  m='1534770'>useful,</span> <span m='1535640'>is</span> <span
  m='1535760'>referred</span> <span m='1536090'>to</span> <span
  m='1536300'>as</span> <span m='1536420'>the</span> <span
  m='1536510'>shifting</span> <span m='1536990'>property,</span> <span
  m='1538320'>which</span> <span m='1538400'>says</span> <span
  m='1539030'>that</span> <span m='1540050'>if</span> <span m='1540320'>I</span>
  <span m='1540500'>shift</span> <span m='1541190'>x</span> <span
  m='1541460'>of</span> <span m='1541580'>n</span> <span m='1543040'>by</span>
  <span m='1543250'>an</span> <span m='1543370'>amount</span> <span
  m='1543820'>n0--</span> <span m='1546800'>and</span> <span
  m='1547250'>you</span> <span m='1547400'>should</span> <span
  m='1547580'>think,</span> <span m='1547850'>by</span> <span
  m='1548000'>the</span> <span m='1548120'>way,</span> <span
  m='1548390'>of</span> <span m='1548630'>if</span> <span m='1548810'>n0</span>
  <span m='1549260'>is</span> <span m='1549350'>positive,</span> <span
  m='1549980'>does</span> <span m='1550130'>that</span> <span
  m='1550280'>mean</span> <span m='1550490'>shifting</span> <span
  m='1550940'>to</span> <span m='1551060'>the</span> <span
  m='1551150'>right</span> <span m='1551420'>or</span> <span
  m='1551480'>shifting</span> <span m='1551900'>to</span> <span
  m='1551990'>the</span> <span m='1552110'>left?</span> <span
  m='1553500'>Well,</span> <span m='1553790'>I'll</span> <span
  m='1553880'>let</span> <span m='1554030'>you</span> <span
  m='1554120'>think</span> <span m='1554360'>about</span> <span
  m='1554690'>that.</span> <span m='1555080'>It's</span> <span
  m='1555230'>something</span> <span m='1555560'>that</span> <span
  m='1555710'>you</span> <span m='1555800'>should</span> <span
  m='1556280'>nail</span> <span m='1556580'>down.</span> <span
  m='1557990'>If</span> <span m='1558200'>I</span> <span
  m='1558320'>shift</span> <span m='1558710'>the</span> <span
  m='1558830'>sequence</span> <span m='1559280'>x</span> <span
  m='1559510'>of</span> <span m='1559580'>n</span> <span m='1560570'>by</span>
  <span m='1560900'>replacing</span> <span m='1561470'>the</span> <span
  m='1561590'>argument</span> <span m='1562040'>by</span> <span
  m='1562250'>n</span> <span m='1562400'>plus</span> <span
  m='1562700'>n0,</span> <span m='1564650'>then</span> <span
  m='1564800'>the</span> <span m='1564890'>resulting</span> <span
  m='1565400'>Z-transform</span> <span m='1566480'>is</span> <span
  m='1566660'>z</span> <span m='1566900'>to</span> <span m='1567080'>the</span>
  <span m='1567230'>n0</span> <span m='1568700'>times</span> <span
  m='1569120'>x</span> <span m='1569360'>of</span> <span m='1569450'>z.</span>
  <span m='1569750'>That</span> <span m='1569930'>is,</span> <span
  m='1570020'>shifting</span> <span m='1571010'>corresponds</span> <span
  m='1571680'>to</span> <span m='1571820'>multiplying</span> <span
  m='1572660'>by</span> <span m='1572990'>z</span> <span m='1573230'>to</span>
  <span m='1573380'>the</span> <span m='1573710'>n0.</span> </p><p><span
  m='1576690'>Another</span> <span m='1576980'>useful</span> <span
  m='1577340'>property</span> <span m='1579240'>has</span> <span
  m='1579510'>to</span> <span m='1579660'>do</span> <span
  m='1580140'>with</span> <span m='1580560'>taking</span> <span
  m='1580950'>a</span> <span m='1581010'>sequence</span> <span
  m='1581700'>and</span> <span m='1581820'>turning</span> <span
  m='1582180'>it</span> <span m='1582270'>around</span> <span
  m='1582900'>in</span> <span m='1583100'>n.</span> <span
  m='1584100'>That</span> <span m='1584310'>is,</span> <span
  m='1585000'>replacing</span> <span m='1585630'>n</span> <span
  m='1586140'>by</span> <span m='1586320'>minus</span> <span
  m='1586800'>n.</span> <span m='1588060'>The</span> <span
  m='1588150'>resulting</span> <span m='1588660'>effect</span> <span
  m='1589140'>on</span> <span m='1589320'>the</span> <span
  m='1589410'>Z-transform</span> <span m='1590640'>is</span> <span
  m='1591390'>to</span> <span m='1591510'>replace</span> <span
  m='1592140'>z</span> <span m='1593040'>by</span> <span m='1593610'>1</span>
  <span m='1593850'>over</span> <span m='1594130'>z.</span> <span
  m='1596140'>Another</span> <span m='1596470'>useful</span> <span
  m='1596830'>property</span> <span m='1597550'>is</span> <span
  m='1598600'>the</span> <span m='1598720'>result</span> <span
  m='1599500'>of</span> <span m='1599980'>multiplying</span> <span
  m='1600700'>a</span> <span m='1600760'>sequence</span> <span
  m='1601180'>x</span> <span m='1601460'>of n</span> <span m='1602290'>by</span>
  <span m='1602500'>an</span> <span m='1602590'>exponential,</span> <span
  m='1603640'>a</span> <span m='1603820'>to</span> <span m='1603970'>the</span>
  <span m='1604150'>n.</span> <span m='1604570'>a</span> <span
  m='1604720'>might</span> <span m='1604960'>be</span> <span
  m='1605080'>complex.</span> <span m='1605740'>Or it</span> <span
  m='1605870'>might</span> <span m='1606070'>be</span> <span
  m='1606220'>real.</span> <span m='1607360'>And</span> <span
  m='1607960'>the</span> <span m='1608080'>result</span> <span
  m='1608500'>there</span> <span m='1609010'>is</span> <span
  m='1609670'>that</span> <span m='1610150'>the</span> <span
  m='1610540'>z</span> <span m='1610750'>transform</span> <span
  m='1611620'>is</span> <span m='1611920'>x</span> <span m='1612340'>of</span>
  <span m='1612640'>8</span> <span m='1612850'>to</span> <span
  m='1612970'>the</span> <span m='1613060'>minus</span> <span
  m='1613420'>1</span> <span m='1613690'>times</span> <span
  m='1614060'>z.</span> </p><p><span m='1615610'>Another</span> <span
  m='1616000'>one</span> <span m='1616480'>which</span> <span
  m='1616690'>is</span> <span m='1616810'>useful</span> <span
  m='1617620'>is</span> <span m='1618370'>multiplication</span> <span
  m='1619180'>of</span> <span m='1619240'>a</span> <span
  m='1619300'>sequence</span> <span m='1619780'>by</span> <span
  m='1620050'>n</span> <span m='1621790'>which</span> <span
  m='1622090'>results</span> <span m='1622510'>in</span> <span
  m='1622600'>a</span> <span m='1622660'>z</span> <span
  m='1622840'>transform,</span> <span m='1623930'>which</span> <span
  m='1624040'>is</span> <span m='1624160'>minus</span> <span
  m='1624620'>z</span> <span m='1625500'>times</span> <span
  m='1625840'>the</span> <span m='1625930'>derivative</span> <span
  m='1626800'>of</span> <span m='1626950'>x</span> <span m='1627190'>of</span>
  <span m='1627310'>z.</span> <span m='1628690'>And</span> <span
  m='1629140'>then</span> <span m='1629350'>I've</span> <span
  m='1629500'>indicated--</span> <span m='1630940'>tried</span> <span
  m='1631170'>to</span> <span m='1631300'>be</span> <span
  m='1631450'>somewhat</span> <span m='1631810'>explicit--</span> <span
  m='1632890'>that</span> <span m='1633460'>that's</span> <span
  m='1633700'>not</span> <span m='1633940'>the</span> <span
  m='1634060'>end</span> <span m='1634210'>of</span> <span
  m='1634270'>the</span> <span m='1634390'>list.</span> <span
  m='1635170'>There</span> <span m='1635470'>are</span> <span
  m='1635620'>lots</span> <span m='1635950'>of</span> <span
  m='1636040'>other</span> <span m='1636250'>properties--</span> <span
  m='1637360'>a</span> <span m='1637420'>number</span> <span
  m='1638020'>of</span> <span m='1638200'>others</span> <span
  m='1638500'>that</span> <span m='1638620'>are</span> <span
  m='1638770'>presented</span> <span m='1639250'>in</span> <span
  m='1639370'>the</span> <span m='1639460'>text,</span> <span
  m='1640490'>others</span> <span m='1640720'>besides</span> <span
  m='1641200'>that</span> <span m='1641440'>that</span> <span
  m='1641560'>aren't</span> <span m='1641770'>presented</span> <span
  m='1642190'>in</span> <span m='1642310'>the</span> <span
  m='1642400'>text,</span> <span m='1642850'>ones</span> <span
  m='1643150'>that</span> <span m='1643300'>you</span> <span
  m='1643390'>can</span> <span m='1643540'>dream</span> <span
  m='1643810'>up</span> <span m='1643960'>yourself,</span> <span
  m='1644860'>ones</span> <span m='1645100'>that</span> <span
  m='1645190'>your</span> <span m='1645310'>friends</span> <span
  m='1645640'>know</span> <span m='1645850'>that</span> <span
  m='1646000'>you</span> <span m='1646090'>don't,</span> <span m='1646390'>et
  cetera.</span> </p><p><span m='1649040'>Now,</span> <span
  m='1650150'>we</span> <span m='1650300'>could,</span> <span
  m='1650480'>of</span> <span m='1650570'>course,</span> <span
  m='1650870'>go</span> <span m='1651050'>through</span> <span
  m='1651290'>the</span> <span m='1651380'>proof</span> <span
  m='1651710'>of</span> <span m='1651830'>all</span> <span
  m='1652040'>these.</span> <span m='1653930'>The</span> <span
  m='1654830'>proofs</span> <span m='1655520'>of</span> <span
  m='1655880'>properties</span> <span m='1657500'>tend</span> <span
  m='1658160'>to</span> <span m='1659030'>all</span> <span m='1659300'>be</span>
  <span m='1659720'>in</span> <span m='1659900'>somewhat</span> <span
  m='1660260'>of</span> <span m='1660350'>a</span> <span
  m='1660410'>similar</span> <span m='1660860'>vein,</span> <span
  m='1661370'>as</span> <span m='1661490'>a</span> <span
  m='1661550'>matter</span> <span m='1661820'>of</span> <span
  m='1661880'>fact.</span> <span m='1663200'>And</span> <span
  m='1664100'>the</span> <span m='1664250'>style,</span> <span
  m='1664760'>once</span> <span m='1665150'>you</span> <span
  m='1665900'>see</span> <span m='1666110'>what</span> <span
  m='1666260'>the</span> <span m='1666380'>trick</span> <span
  m='1666710'>is</span> <span m='1666980'>or</span> <span
  m='1667340'>roughly</span> <span m='1667790'>how</span> <span
  m='1667880'>you</span> <span m='1668000'>go</span> <span
  m='1668180'>about</span> <span m='1668390'>proving</span> <span
  m='1668780'>properties,</span> <span m='1669380'>then</span> <span
  m='1669740'>you</span> <span m='1669890'>can</span> <span
  m='1669980'>just</span> <span m='1670220'>prove</span> <span
  m='1670520'>properties</span> <span m='1670790'>and</span> <span
  m='1671060'>prove</span> <span m='1671420'>properties.</span> <span
  m='1672740'>And</span> <span m='1674180'>we</span> <span
  m='1674300'>won't</span> <span m='1674720'>do</span> <span
  m='1674930'>that</span> <span m='1675170'>in</span> <span
  m='1675260'>this</span> <span m='1675440'>lecture,</span> <span
  m='1676070'>with</span> <span m='1676250'>the</span> <span
  m='1676370'>exception</span> <span m='1677210'>of</span> <span
  m='1678290'>illustrating</span> <span m='1679430'>the</span> <span
  m='1679550'>style</span> <span m='1680270'>of</span> <span
  m='1680420'>proving</span> <span m='1680810'>properties</span> <span
  m='1682130'>with</span> <span m='1682730'>a</span> <span
  m='1682790'>couple</span> <span m='1683150'>of</span> <span
  m='1683240'>examples.</span> </p><p><span m='1684480'>And</span> <span
  m='1684770'>the</span> <span m='1684860'>two</span> <span
  m='1685040'>examples</span> <span m='1686030'>that</span> <span
  m='1686180'>I've</span> <span m='1686330'>picked,</span> <span
  m='1687170'>somewhat</span> <span m='1687590'>arbitrarily</span> <span
  m='1688340'>as</span> <span m='1688460'>a</span> <span
  m='1688520'>matter</span> <span m='1688790'>of</span> <span
  m='1688850'>fact,</span> <span m='1689960'>is</span> <span
  m='1690620'>the</span> <span m='1690740'>Shifting</span> <span
  m='1691190'>Property,</span> <span m='1691940'>that</span> <span
  m='1692240'>is</span> <span m='1692360'>Property</span> <span
  m='1692960'>2,</span> <span m='1694010'>and</span> <span
  m='1694610'>the</span> <span m='1694910'>result</span> <span
  m='1695360'>of</span> <span m='1695420'>multiplication</span> <span
  m='1696260'>by</span> <span m='1696470'>an</span> <span
  m='1696560'>exponential,</span> <span m='1698070'>which is</span> <span
  m='1698210'>Property</span> <span m='1699500'>4.</span> <span
  m='1701420'>But</span> <span m='1701630'>this</span> <span
  m='1701840'>is</span> <span m='1701990'>only</span> <span
  m='1703610'>to</span> <span m='1703790'>illustrate</span> <span
  m='1704360'>the</span> <span m='1704450'>style</span> <span
  m='1705230'>of</span> <span m='1705500'>proving</span> <span
  m='1705920'>properties.</span> <span m='1707090'>And</span> <span
  m='1707990'>you</span> <span m='1708140'>can</span> <span
  m='1708290'>guess</span> <span m='1708560'>where,</span> <span
  m='1709070'>actually,</span> <span m='1709910'>you</span> <span
  m='1710060'>get</span> <span m='1710210'>a</span> <span
  m='1710270'>chance</span> <span m='1710570'>to</span> <span
  m='1710720'>see</span> <span m='1711530'>the</span> <span
  m='1711620'>proof</span> <span m='1711920'>of</span> <span
  m='1711980'>some</span> <span m='1712250'>of</span> <span
  m='1712310'>the</span> <span m='1712460'>others.</span> </p><p><span
  m='1714030'>All</span> <span m='1714120'>right,</span> <span
  m='1714390'>let's</span> <span m='1714750'>take</span> <span
  m='1715020'>a</span> <span m='1715080'>look</span> <span m='1715350'>at</span>
  <span m='1715890'>Property</span> <span m='1716370'>2,</span> <span
  m='1716820'>that</span> <span m='1717030'>is</span> <span
  m='1717180'>the</span> <span m='1717300'>Shifting</span> <span
  m='1717720'>Property.</span> <span m='1719960'>Well,</span> <span
  m='1722060'>to</span> <span m='1722150'>prove</span> <span
  m='1722690'>that</span> <span m='1723770'>replacing</span> <span
  m='1724340'>n</span> <span m='1724490'>by</span> <span m='1724700'>n
  plus</span> <span m='1725100'>n0</span> <span m='1726110'>results</span> <span
  m='1726560'>in</span> <span m='1726680'>z</span> <span m='1726920'>to</span>
  <span m='1727070'>the</span> <span m='1727220'>n0</span> <span
  m='1727760'>times</span> <span m='1728090'>x</span> <span
  m='1728360'>of</span> <span m='1728450'>z,</span> <span m='1729830'>we</span>
  <span m='1729950'>want</span> <span m='1730130'>to</span> <span
  m='1730190'>consider</span> <span m='1730640'>a</span> <span
  m='1730700'>sequence,</span> <span m='1731210'>x1</span> <span
  m='1731630'>of</span> <span m='1731750'>n</span> <span m='1733410'>equal
  to</span> <span m='1733740'>x</span> <span m='1733860'>of</span> <span
  m='1734170'>n</span> <span m='1734430'>plus</span> <span m='1734730'>n0</span>
  <span m='1737150'>so</span> <span m='1737230'>that</span> <span
  m='1737410'>its</span> <span m='1737530'>Z-transform,</span> <span
  m='1739030'>x1</span> <span m='1739390'>of</span> <span m='1739540'>z,</span>
  <span m='1740500'>is</span> <span m='1740650'>the</span> <span
  m='1740770'>sum</span> <span m='1741160'>of</span> <span m='1741280'>x</span>
  <span m='1741520'>of</span> <span m='1741610'>n</span> <span
  m='1741760'>plus</span> <span m='1742020'>n0</span> <span
  m='1742660'>times</span> <span m='1742960'>z</span> <span
  m='1743200'>to</span> <span m='1743350'>the</span> <span
  m='1743470'>minus</span> <span m='1743785'>n.</span> <span
  m='1745990'>Well,</span> <span m='1746230'>a</span> <span
  m='1746290'>simple</span> <span m='1746920'>idea</span> <span
  m='1747340'>here</span> <span m='1747880'>is</span> <span m='1748480'>a</span>
  <span m='1748540'>substitution</span> <span m='1749290'>of</span> <span
  m='1749350'>variables.</span> <span m='1751030'>Let's</span> <span
  m='1751300'>replace</span> <span m='1753010'>n</span> <span
  m='1753280'>plus</span> <span m='1753610'>n0</span> <span
  m='1755200'>by</span> <span m='1755380'>a</span> <span m='1755410'>new</span>
  <span m='1755620'>variable,</span> <span m='1756160'>m,</span> <span
  m='1757540'>or</span> <span m='1758110'>n</span> <span m='1758560'>is</span>
  <span m='1758740'>equal</span> <span m='1759130'>to</span> <span
  m='1759370'>m</span> <span m='1760030'>minus</span> <span
  m='1760450'>n0,</span> <span m='1762190'>in</span> <span
  m='1762280'>which</span> <span m='1762490'>case,</span> <span
  m='1762890'>we</span> <span m='1762940'>can</span> <span
  m='1763090'>rewrite</span> <span m='1764320'>this</span> <span
  m='1764530'>expression</span> <span m='1766300'>as</span> <span
  m='1766660'>x1</span> <span m='1767020'>of</span> <span m='1767230'>z</span>
  <span m='1768430'>is</span> <span m='1768550'>the</span> <span
  m='1768670'>sum</span> <span m='1769120'>on</span> <span m='1769330'>m</span>
  <span m='1770740'>of</span> <span m='1771210'>x</span> <span
  m='1771510'>of</span> <span m='1771660'>m,</span> <span
  m='1772260'>because</span> <span m='1772680'>this</span> <span
  m='1772890'>is</span> <span m='1773010'>now</span> <span m='1773290'>m.</span>
  <span m='1775300'>n</span> <span m='1775840'>is</span> <span
  m='1776020'>replaced</span> <span m='1776470'>by</span> <span
  m='1776740'>m</span> <span m='1776920'>minus</span> <span
  m='1777360'>n0.</span> <span m='1778570'>So</span> <span m='1779260'>we</span>
  <span m='1779410'>have</span> <span m='1779650'>z</span> <span
  m='1779920'>to</span> <span m='1780070'>the</span> <span m='1780220'>n0</span>
  <span m='1781420'>times</span> <span m='1782320'>z</span> <span
  m='1783010'>to</span> <span m='1783130'>the</span> <span
  m='1783250'>minus</span> <span m='1783660'>m.</span> </p><p><span
  m='1785590'>Well,</span> <span m='1786670'>the</span> <span
  m='1786790'>z</span> <span m='1787510'>to</span> <span m='1787630'>the</span>
  <span m='1787780'>n0</span> <span m='1790320'>can</span> <span
  m='1790470'>come</span> <span m='1791040'>outside</span> <span
  m='1792940'>the</span> <span m='1793170'>sum.</span> <span
  m='1794750'>The</span> <span m='1795000'>limits</span> <span
  m='1795400'>on</span> <span m='1795550'>the</span> <span
  m='1795640'>sum,</span> <span m='1795920'>incidentally,</span> <span
  m='1796540'>are</span> <span m='1796990'>m</span> <span
  m='1797260'>equals</span> <span m='1797530'>minus</span> <span
  m='1797860'>infinity</span> <span m='1798460'>to</span> <span
  m='1798560'>plus</span> <span m='1798760'>infinity</span> <span
  m='1799370'>because</span> <span m='1800410'>if</span> <span
  m='1800830'>n0</span> <span m='1801250'>is</span> <span
  m='1801400'>finite,</span> <span m='1802450'>as</span> <span
  m='1802900'>n</span> <span m='1803440'>runs</span> <span
  m='1803950'>from</span> <span m='1804130'>minus</span> <span
  m='1804460'>infinity</span> <span m='1804910'>to</span> <span
  m='1805000'>plus</span> <span m='1805300'>infinity,</span> <span
  m='1806180'>so</span> <span m='1806290'>does</span> <span
  m='1806470'>m.</span> <span m='1808510'>That</span> <span
  m='1808990'>comes</span> <span m='1809230'>outside</span> <span
  m='1809740'>the</span> <span m='1809830'>sum.</span> <span
  m='1811150'>And</span> <span m='1811240'>what's</span> <span
  m='1811510'>left,</span> <span m='1811870'>then,</span> <span
  m='1812680'>is</span> <span m='1812830'>the</span> <span
  m='1812950'>sum</span> <span m='1813310'>of</span> <span m='1813430'>x</span>
  <span m='1813700'>of</span> <span m='1813760'>m</span> <span
  m='1814420'>z</span> <span m='1814630'>to</span> <span m='1814780'>the</span>
  <span m='1814870'>minus</span> <span m='1815260'>m,</span> <span
  m='1816040'>which</span> <span m='1816220'>is</span> <span
  m='1816340'>just</span> <span m='1816700'>x of</span> <span
  m='1816970'>z.</span> <span m='1817930'>So</span> <span
  m='1818560'>consequently,</span> <span m='1819370'>then,</span> <span
  m='1820000'>what</span> <span m='1820110'>we</span> <span
  m='1820300'>end</span> <span m='1820510'>up</span> <span
  m='1820690'>with</span> <span m='1821080'>is</span> <span
  m='1821350'>that</span> <span m='1821590'>x</span> <span m='1821830'>of</span>
  <span m='1821950'>z</span> <span m='1822910'>is</span> <span
  m='1823720'>z</span> <span m='1824050'>to</span> <span m='1824200'>the</span>
  <span m='1824380'>n0</span> <span m='1825910'>times</span> <span
  m='1828100'>x</span> <span m='1828380'>of z.</span> <span
  m='1830030'>x1</span> <span m='1830200'>of z</span> <span
  m='1830455'>is</span> <span m='1830710'>z</span> <span m='1831160'>to</span>
  <span m='1831280'>the</span> <span m='1831430'>n0</span> <span
  m='1831910'>times</span> <span m='1832240'>x</span> <span
  m='1832450'>of</span> <span m='1832540'>z,</span> <span
  m='1833630'>which</span> <span m='1833770'>is,</span> <span
  m='1834130'>of</span> <span m='1834250'>course,</span> <span
  m='1834490'>the</span> <span m='1834610'>way</span> <span m='1834790'>I</span>
  <span m='1834910'>advertised.</span> </p><p><span m='1837650'>Well,</span>
  <span m='1838040'>there</span> <span m='1838190'>are</span> <span
  m='1838220'>lots</span> <span m='1838550'>of</span> <span
  m='1839240'>times</span> <span m='1839840'>when,</span> <span
  m='1840050'>in</span> <span m='1840140'>fact,</span> <span
  m='1840470'>the</span> <span m='1840560'>Shifting</span> <span
  m='1841010'>Property</span> <span m='1841880'>comes</span> <span
  m='1842180'>into</span> <span m='1842420'>play.</span> <span
  m='1844770'>One</span> <span m='1844880'>thing</span> <span
  m='1845120'>that</span> <span m='1845240'>we</span> <span
  m='1845450'>can</span> <span m='1845960'>use</span> <span
  m='1846230'>it</span> <span m='1846320'>for</span> <span
  m='1846560'>immediately</span> <span m='1847430'>is</span> <span
  m='1848540'>to</span> <span m='1849350'>tie</span> <span
  m='1849680'>together</span> <span m='1850430'>a</span> <span
  m='1850490'>couple</span> <span m='1850820'>of</span> <span
  m='1850940'>things</span> <span m='1851390'>that</span> <span
  m='1851720'>have</span> <span m='1852020'>been</span> <span
  m='1852170'>floating,</span> <span m='1852950'>more</span> <span
  m='1853130'>or</span> <span m='1853160'>less,</span> <span
  m='1853400'>in</span> <span m='1853490'>the</span> <span
  m='1853580'>background.</span> <span m='1857090'>I</span> <span
  m='1857690'>have</span> <span m='1857870'>alluded</span> <span
  m='1858590'>several</span> <span m='1859070'>times</span> <span
  m='1859880'>to</span> <span m='1860000'>the</span> <span
  m='1860120'>fact</span> <span m='1861850'>that</span> <span
  m='1863170'>systems</span> <span m='1864520'>whose</span> <span
  m='1864760'>system</span> <span m='1865240'>function</span> <span
  m='1867260'>is</span> <span m='1867620'>rational</span> <span
  m='1869330'>correspond</span> <span m='1870260'>to</span> <span
  m='1870440'>systems</span> <span m='1871580'>that</span> <span
  m='1871730'>are</span> <span m='1871820'>characterized</span> <span
  m='1873230'>by</span> <span m='1873380'>linear</span> <span
  m='1873770'>constant</span> <span m='1874160'>coefficient</span> <span
  m='1874760'>difference</span> <span m='1875090'>equations.</span> <span
  m='1876140'>That</span> <span m='1876290'>is,</span> <span
  m='1877070'>linear</span> <span m='1877340'>constant</span> <span
  m='1877730'>coefficient</span> <span m='1878240'>difference</span> <span
  m='1878600'>equations,</span> <span m='1879410'>those</span> <span
  m='1879710'>are</span> <span m='1879770'>the</span> <span
  m='1880280'>systems</span> <span m='1881450'>that</span> <span
  m='1881690'>end</span> <span m='1882020'>up</span> <span
  m='1882500'>with</span> <span m='1882620'>system</span> <span
  m='1883040'>functions</span> <span m='1883910'>that</span> <span
  m='1884060'>are</span> <span m='1884120'>rational</span> <span
  m='1884570'>functions.</span> <span m='1885770'>And</span> <span
  m='1885980'>in</span> <span m='1886070'>fact,</span> <span
  m='1886740'>we</span> <span m='1886820'>can</span> <span
  m='1887330'>see</span> <span m='1887630'>that</span> <span
  m='1888050'>in</span> <span m='1888170'>a</span> <span
  m='1888500'>straightforward</span> <span m='1889310'>way</span> <span
  m='1890360'>by</span> <span m='1891350'>just</span> <span
  m='1891560'>simply</span> <span m='1891950'>applying</span> <span
  m='1892460'>the</span> <span m='1892550'>Shifting</span> <span
  m='1893000'>Property.</span> </p><p><span m='1894950'>Well,</span> <span
  m='1895430'>let's</span> <span m='1895700'>consider</span> <span
  m='1898660'>a</span> <span m='1898930'>linear</span> <span
  m='1899980'>constant</span> <span m='1900460'>coefficient</span> <span
  m='1901930'>difference</span> <span m='1902320'>equation</span> <span
  m='1903640'>of</span> <span m='1903760'>the</span> <span
  m='1903850'>general</span> <span m='1904300'>form</span> <span
  m='1905050'>is</span> <span m='1905230'>the</span> <span
  m='1905350'>sum</span> <span m='1905650'>from</span> <span m='1905830'>k
  equals</span> <span m='1906220'>0</span> <span m='1906610'>to</span> <span
  m='1906760'>n.</span> <span m='1908190'>a</span> <span m='1908600'>sub</span>
  <span m='1908770'>k</span> <span m='1909940'>y</span> <span m='1910270'>of
  n</span> <span m='1910600'>minus k</span> <span m='1911590'>is</span> <span
  m='1911710'>equal</span> <span m='1912040'>to</span> <span
  m='1912220'>a</span> <span m='1912280'>sum</span> <span m='1912800'>of</span>
  <span m='1912920'>b sub</span> <span m='1913330'>k</span> <span
  m='1914200'>times</span> <span m='1914590'>x</span> <span
  m='1914860'>of</span> <span m='1914960'>n</span> <span
  m='1915130'>minus</span> <span m='1915520'>k.</span> <span
  m='1919250'>If</span> <span m='1919910'>we</span> <span
  m='1920960'>take</span> <span m='1921200'>the</span> <span
  m='1921320'>Z-transform</span> <span m='1922340'>of</span> <span
  m='1922400'>both</span> <span m='1922670'>sides</span> <span
  m='1923030'>of</span> <span m='1923120'>this</span> <span
  m='1923330'>equation</span> <span m='1925640'>and</span> <span
  m='1926090'>use</span> <span m='1926360'>the</span> <span
  m='1926450'>fact--</span> <span m='1926810'>incidentally,</span> <span
  m='1927260'>this</span> <span m='1927410'>is</span> <span
  m='1927560'>another</span> <span m='1927860'>property</span> <span
  m='1928430'>that</span> <span m='1928670'>I've</span> <span
  m='1929450'>more</span> <span m='1929750'>or</span> <span
  m='1929810'>less</span> <span m='1930830'>been</span> <span
  m='1931490'>using,</span> <span m='1932000'>although</span> <span
  m='1932360'>I've</span> <span m='1932480'>never</span> <span
  m='1932720'>stated</span> <span m='1933080'>explicitly--</span> <span
  m='1933710'>that</span> <span m='1933890'>the</span> <span
  m='1933980'>Z-transform</span> <span m='1934730'>of</span> <span
  m='1934820'>a</span> <span m='1934880'>sum</span> <span m='1935240'>is</span>
  <span m='1935330'>the</span> <span m='1935420'>sum</span> <span
  m='1935690'>of</span> <span m='1935750'>the</span> <span
  m='1935870'>Z-transforms.</span> <span m='1937430'>Taking,</span> <span
  m='1937790'>then,</span> <span m='1937970'>the</span> <span
  m='1938060'>Z-transform</span> <span m='1938900'>of</span> <span
  m='1938960'>this</span> <span m='1939140'>equation,</span> <span
  m='1941480'>y</span> <span m='1942080'>of n</span> <span
  m='1942495'>minus</span> <span m='1942910'>k</span> <span
  m='1944640'>using</span> <span m='1945000'>the</span> <span
  m='1945060'>Shifting</span> <span m='1945510'>Property</span> <span
  m='1946590'>will</span> <span m='1946800'>give</span> <span
  m='1947100'>us</span> <span m='1948120'>z</span> <span m='1948450'>to</span>
  <span m='1948600'>the</span> <span m='1948720'>minus</span> <span
  m='1949140'>k</span> <span m='1950250'>times</span> <span m='1951330'>y</span>
  <span m='1951630'>of z.</span> <span m='1954170'>And</span> <span
  m='1954380'>x</span> <span m='1954710'>of</span> <span m='1954800'>n</span>
  <span m='1954980'>minus</span> <span m='1955450'>k</span> <span
  m='1957510'>will</span> <span m='1957690'>give</span> <span
  m='1957960'>us</span> <span m='1958680'>z</span> <span m='1959270'>to</span>
  <span m='1959400'>the</span> <span m='1959520'>minus</span> <span
  m='1959930'>k</span> <span m='1961560'>times</span> <span m='1962190'>x</span>
  <span m='1962520'>of</span> <span m='1962610'>z.</span> </p><p><span
  m='1964770'>Consequently,</span> <span m='1966040'>the</span> <span
  m='1966150'>sum</span> <span m='1966480'>of</span> <span m='1966610'>a sub
  k</span> <span m='1966980'>z</span> <span m='1967730'>to</span> <span
  m='1967920'>the</span> <span m='1968010'>minus</span> <span
  m='1968370'>k</span> <span m='1968610'>y</span> <span m='1969037'>of z</span>
  <span m='1970320'>is</span> <span m='1970440'>equal</span> <span
  m='1970800'>to</span> <span m='1970950'>the</span> <span
  m='1971040'>sum</span> <span m='1971550'>of</span> <span m='1971690'>b
  sub</span> <span m='1972120'>k</span> <span m='1972630'>z</span> <span
  m='1972930'>to</span> <span m='1973080'>the</span> <span
  m='1973170'>minus</span> <span m='1973500'>k</span> <span m='1973920'>x</span>
  <span m='1974250'>of</span> <span m='1974370'>z.</span> <span
  m='1975960'>If</span> <span m='1976110'>we</span> <span
  m='1976230'>solve</span> <span m='1976650'>that</span> <span
  m='1976860'>equation</span> <span m='1978000'>for</span> <span m='1978210'>y
  of</span> <span m='1978570'>z</span> <span m='1979170'>over</span> <span
  m='1979470'>x</span> <span m='1979680'>of</span> <span m='1979800'>z,</span>
  <span m='1980380'>which</span> <span m='1980550'>is</span> <span
  m='1981030'>the</span> <span m='1981120'>system</span> <span
  m='1981540'>function,</span> <span m='1983730'>then</span> <span
  m='1984420'>we</span> <span m='1984630'>end</span> <span m='1984870'>up</span>
  <span m='1985050'>with</span> <span m='1985260'>the</span> <span
  m='1985350'>sum</span> <span m='1986400'>of</span> <span m='1986550'>b</span>
  <span m='1986860'>sub</span> <span m='1986970'>k</span> <span
  m='1987270'>z</span> <span m='1987570'>to</span> <span m='1987730'>the</span>
  <span m='1987840'>minus</span> <span m='1988220'>k</span> <span
  m='1989340'>divided</span> <span m='1989850'>by</span> <span
  m='1990630'>the</span> <span m='1990750'>sum</span> <span
  m='1991260'>of</span> <span m='1991580'>a</span> <span m='1991850'>sub</span>
  <span m='1992020'>k</span> <span m='1992640'>times</span> <span
  m='1992890'>z</span> <span m='1993090'>to</span> <span m='1993240'>the</span>
  <span m='1993330'>minus</span> <span m='1993690'>k.</span> </p><p><span
  m='1994770'>And</span> <span m='1995280'>there</span> <span
  m='1995460'>are</span> <span m='1995520'>a</span> <span
  m='1995550'>couple</span> <span m='1995850'>of</span> <span
  m='1995970'>important</span> <span m='1996360'>observations.</span> <span
  m='1997210'>One</span> <span m='1997380'>is</span> <span m='1998340'>we</span>
  <span m='1998520'>ended</span> <span m='1998760'>up</span> <span
  m='1999120'>with</span> <span m='1999270'>a</span> <span
  m='1999330'>rational</span> <span m='1999810'>function,</span> <span
  m='2000840'>which</span> <span m='2001130'>is</span> <span
  m='2001310'>what</span> <span m='2001520'>we</span> <span
  m='2001670'>expected,</span> <span m='2002360'>or</span> <span
  m='2002480'>what</span> <span m='2002630'>I</span> <span
  m='2002690'>said</span> <span m='2002900'>we</span> <span
  m='2003050'>were</span> <span m='2003170'>going</span> <span
  m='2003290'>to</span> <span m='2003380'>get.</span> <span
  m='2006090'>And</span> <span m='2006800'>a</span> <span
  m='2006900'>second</span> <span m='2008040'>is</span> <span
  m='2008310'>that</span> <span m='2009210'>the</span> <span
  m='2010910'>coefficients</span> <span m='2011900'>in</span> <span
  m='2012020'>the</span> <span m='2012110'>numerator</span> <span
  m='2012680'>polynomial</span> <span m='2014630'>are</span> <span
  m='2014990'>exactly</span> <span m='2015680'>the</span> <span
  m='2015800'>same</span> <span m='2016460'>as</span> <span
  m='2016670'>the</span> <span m='2016760'>coefficients</span> <span
  m='2017540'>on</span> <span m='2017660'>the</span> <span
  m='2017750'>right</span> <span m='2017990'>hand</span> <span
  m='2018230'>side</span> <span m='2018530'>of</span> <span
  m='2018650'>the</span> <span m='2018740'>difference</span> <span
  m='2019130'>equation.</span> <span m='2021230'>And</span> <span
  m='2021380'>the</span> <span m='2021440'>coefficients</span> <span
  m='2022250'>in</span> <span m='2022370'>the</span> <span
  m='2022460'>denominator</span> <span m='2023150'>polynomial</span> <span
  m='2024530'>are</span> <span m='2024680'>exactly</span> <span
  m='2025160'>the</span> <span m='2025250'>same</span> <span
  m='2025760'>as</span> <span m='2026300'>the</span> <span
  m='2026450'>coefficients</span> <span m='2027350'>on</span> <span
  m='2027980'>the</span> <span m='2028040'>left</span> <span
  m='2028370'>hand</span> <span m='2028580'>side</span> <span
  m='2029330'>of</span> <span m='2029480'>the</span> <span
  m='2029570'>difference</span> <span m='2029930'>equation.</span> <span
  m='2031070'>This</span> <span m='2031250'>by</span> <span
  m='2031460'>the</span> <span m='2031580'>way,</span> <span
  m='2032010'>is</span> <span m='2032060'>exactly</span> <span
  m='2032600'>consistent,</span> <span m='2033320'>or</span> <span
  m='2033410'>analogous,</span> <span m='2034730'>with</span> <span
  m='2035360'>what</span> <span m='2035630'>happens</span> <span
  m='2036650'>when</span> <span m='2037010'>we</span> <span
  m='2037190'>apply</span> <span m='2037550'>the</span> <span
  m='2037640'>Laplace</span> <span m='2038120'>transform</span> <span
  m='2039800'>to</span> <span m='2039920'>linear</span> <span
  m='2040280'>constant</span> <span m='2040690'>coefficient</span> <span
  m='2041240'>differential</span> <span m='2041840'>equation.</span> <span
  m='2042620'>Exactly</span> <span m='2043130'>the</span> <span
  m='2043250'>same</span> <span m='2043520'>thing</span> <span
  m='2043700'>happens.</span> </p><p><span m='2045530'>It</span> <span
  m='2045590'>should</span> <span m='2045800'>be</span> <span
  m='2045920'>clear</span> <span m='2046280'>then,</span> <span
  m='2046640'>incidentally,</span> <span m='2047950'>that</span> <span
  m='2048199'>if</span> <span m='2048469'>I</span> <span m='2048620'>give</span>
  <span m='2048889'>you</span> <span m='2049219'>a</span> <span
  m='2049280'>system</span> <span m='2049730'>function</span> <span
  m='2050239'>that's</span> <span m='2050420'>a</span> <span
  m='2050510'>rational</span> <span m='2050960'>function</span> <span
  m='2051380'>of</span> <span m='2051500'>z,</span> <span
  m='2052480'>that</span> <span m='2052670'>you</span> <span
  m='2052820'>could</span> <span m='2053000'>construct,</span> <span
  m='2054260'>in</span> <span m='2054380'>a</span> <span
  m='2054409'>straightforward</span> <span m='2055159'>way,</span> <span
  m='2056030'>the</span> <span m='2056150'>difference</span> <span
  m='2056570'>equation</span> <span m='2057050'>that</span> <span
  m='2057139'>characterizes</span> <span m='2057920'>that</span> <span
  m='2058100'>system</span> <span m='2058489'>because</span> <span
  m='2059270'>you</span> <span m='2059389'>can</span> <span
  m='2059540'>pick</span> <span m='2059810'>the</span> <span
  m='2059900'>coefficients</span> <span m='2060590'>off</span> <span
  m='2061040'>from</span> <span m='2061250'>the</span> <span
  m='2061340'>numerator.</span> <span m='2062420'>Those</span> <span
  m='2062690'>are</span> <span m='2062750'>on</span> <span
  m='2062870'>the</span> <span m='2062960'>right</span> <span
  m='2063170'>hand</span> <span m='2063440'>side.</span> <span
  m='2064500'>And</span> <span m='2064520'>you</span> <span
  m='2064639'>can</span> <span m='2064760'>pick</span> <span
  m='2064969'>the</span> <span m='2065060'>coefficients</span> <span
  m='2065750'>off</span> <span m='2066380'>from</span> <span
  m='2066580'>the</span> <span m='2066659'>denominator.</span> <span
  m='2067730'>Those</span> <span m='2067969'>are</span> <span
  m='2068090'>on</span> <span m='2068600'>the</span> <span
  m='2068690'>left</span> <span m='2068960'>hand</span> <span
  m='2069170'>side</span> <span m='2069469'>of</span> <span
  m='2069560'>the</span> <span m='2069650'>difference</span> <span
  m='2070010'>equation.</span> </p><p><span m='2072980'>The</span> <span
  m='2073070'>Shifting</span> <span m='2073489'>Property</span> <span
  m='2074030'>is</span> <span m='2074150'>a</span> <span
  m='2074210'>property</span> <span m='2075320'>that</span> <span
  m='2075710'>arises</span> <span m='2076730'>very</span> <span
  m='2077150'>often</span> <span m='2077750'>and,</span> <span
  m='2078080'>in</span> <span m='2078139'>fact,</span> <span
  m='2078389'>is</span> <span m='2078530'>a</span> <span
  m='2078590'>very,</span> <span m='2079050'>very</span> <span
  m='2079130'>useful</span> <span m='2079520'>property.</span> <span
  m='2082690'>Now,</span> <span m='2085139'>the</span> <span
  m='2085230'>second</span> <span m='2085530'>property</span> <span
  m='2086280'>that</span> <span m='2086730'>I</span> <span
  m='2086850'>want</span> <span m='2087239'>to</span> <span
  m='2087570'>outline</span> <span m='2088050'>the</span> <span
  m='2088110'>proof</span> <span m='2088380'>for</span> <span
  m='2090360'>is</span> <span m='2091170'>the</span> <span
  m='2092340'>property</span> <span m='2093000'>related</span> <span
  m='2093929'>to</span> <span m='2094800'>multiplication</span> <span
  m='2096150'>of</span> <span m='2096989'>the</span> <span
  m='2097080'>sequence</span> <span m='2098490'>by</span> <span
  m='2099660'>an</span> <span m='2099810'>exponential</span> <span
  m='2101030'>a</span> <span m='2101220'>to</span> <span m='2101400'>the</span>
  <span m='2101580'>n.</span> <span m='2103890'>I</span> <span
  m='2104490'>am</span> <span m='2104610'>forming</span> <span
  m='2105030'>a</span> <span m='2105090'>new</span> <span
  m='2105240'>sequence</span> <span m='2105780'>x1</span> <span m='2106220'>of
  n,</span> <span m='2107550'>which</span> <span m='2107850'>is</span> <span
  m='2108060'>a</span> <span m='2108240'>to</span> <span m='2108390'>the</span>
  <span m='2108540'>n</span> <span m='2108900'>times</span> <span
  m='2109230'>x</span> <span m='2109470'>of</span> <span m='2109620'>n.</span>
  <span m='2111530'>And</span> <span m='2113660'>to</span> <span
  m='2113780'>derive</span> <span m='2114170'>the</span> <span
  m='2114260'>relationship</span> <span m='2114950'>between</span> <span
  m='2115310'>x1 of</span> <span m='2115520'>z</span> <span
  m='2115940'>and</span> <span m='2116060'>x</span> <span m='2116380'>of
  n,</span> <span m='2117440'>again,</span> <span m='2118160'>we</span> <span
  m='2118340'>can</span> <span m='2118550'>look</span> <span
  m='2118880'>at</span> <span m='2120110'>the</span> <span
  m='2120230'>Z-transform,</span> <span m='2120440'>x1</span> <span
  m='2120755'>of</span> <span m='2121070'>z,</span> <span
  m='2122750'>which</span> <span m='2122930'>is</span> <span
  m='2123080'>the</span> <span m='2123200'>sum</span> <span
  m='2123710'>of</span> <span m='2123830'>a</span> <span m='2123980'>to</span>
  <span m='2124130'>the</span> <span m='2124280'>n,</span> <span
  m='2124610'>x</span> <span m='2124900'>of</span> <span m='2125090'>n,</span>
  <span m='2125480'>times</span> <span m='2125780'>z</span> <span
  m='2125990'>to</span> <span m='2126140'>the</span> <span
  m='2126230'>minus</span> <span m='2126620'>n.</span> </p><p><span
  m='2128330'>Well,</span> <span m='2128750'>it's</span> <span
  m='2128870'>straightforward</span> <span m='2129620'>to</span> <span
  m='2129770'>rewrite</span> <span m='2130640'>what's</span> <span
  m='2130880'>inside</span> <span m='2131300'>the</span> <span
  m='2131460'>sum</span> <span m='2133170'>as</span> <span m='2133920'>x
  of</span> <span m='2134310'>n</span> <span m='2137330'>times</span> <span
  m='2138980'>a</span> <span m='2139250'>to</span> <span m='2139400'>the</span>
  <span m='2139520'>minus 1</span> <span m='2139970'>times</span> <span
  m='2141590'>z</span> <span m='2143460'>to</span> <span m='2143580'>the</span>
  <span m='2143720'>minus</span> <span m='2144140'>n.</span> <span
  m='2147340'>x1 of</span> <span m='2147520'>z</span> <span
  m='2148030'>is</span> <span m='2148270'>the</span> <span
  m='2148360'>sum</span> <span m='2149320'>of</span> <span m='2149470'>x
  of</span> <span m='2149860'>n</span> <span m='2150730'>times</span> <span
  m='2151030'>a</span> <span m='2151210'>to</span> <span m='2151330'>the</span>
  <span m='2151420'>minus</span> <span m='2151810'>1z--</span> <span
  m='2153070'>all</span> <span m='2153280'>that</span> <span
  m='2153520'>raised</span> <span m='2153850'>to</span> <span
  m='2153940'>the</span> <span m='2154060'>minus</span> <span
  m='2154430'>n.</span> <span m='2156180'>Well,</span> <span
  m='2156420'>that</span> <span m='2156600'>looks</span> <span
  m='2156900'>just</span> <span m='2157200'>like</span> <span
  m='2157440'>the</span> <span m='2157530'>Z-transform</span> <span
  m='2158280'>of</span> <span m='2158400'>x</span> <span m='2158610'>of</span>
  <span m='2158860'>n</span> <span m='2159390'>but</span> <span
  m='2159570'>with</span> <span m='2159750'>z</span> <span
  m='2160020'>replaced</span> <span m='2160530'>by</span> <span
  m='2161010'>a</span> <span m='2161250'>to</span> <span m='2161340'>the</span>
  <span m='2161430'>minus 1</span> <span m='2161760'>times</span> <span
  m='2162270'>z.</span> <span m='2163200'>So</span> <span
  m='2164070'>this</span> <span m='2164250'>says,</span> <span
  m='2165030'>consequently,</span> <span m='2167010'>that</span> <span
  m='2167700'>the</span> <span m='2167790'>Z-transform</span> <span
  m='2169380'>of</span> <span m='2169530'>x1</span> <span m='2169950'>of</span>
  <span m='2170070'>n</span> <span m='2171270'>is</span> <span
  m='2171420'>equal</span> <span m='2171810'>to</span> <span
  m='2172890'>the</span> <span m='2172980'>Z-transform</span> <span
  m='2174300'>of</span> <span m='2175200'>x</span> <span m='2175500'>of</span>
  <span m='2175610'>n</span> <span m='2176700'>but</span> <span
  m='2176910'>with</span> <span m='2177090'>z</span> <span
  m='2177780'>replaced</span> <span m='2178380'>by</span> <span
  m='2179010'>a</span> <span m='2179220'>to</span> <span m='2179340'>the</span>
  <span m='2179430'>minus</span> <span m='2179820'>1</span> <span
  m='2180540'>times</span> <span m='2180830'>z.</span> <span
  m='2181800'>So</span> <span m='2182700'>we</span> <span
  m='2182790'>stick</span> <span m='2183090'>in</span> <span
  m='2183210'>here</span> <span m='2183590'>a</span> <span m='2183800'>to</span>
  <span m='2183900'>the</span> <span m='2184020'>minus</span> <span
  m='2184380'>1</span> <span m='2184590'>times</span> <span
  m='2184920'>z.</span> <span m='2185850'>And</span> <span
  m='2186510'>that</span> <span m='2186750'>then</span> <span
  m='2186960'>relates</span> <span m='2187410'>the</span> <span
  m='2187530'>Z-transform</span> <span m='2188250'>of</span> <span
  m='2188310'>the</span> <span m='2188430'>original</span> <span
  m='2188820'>sequence</span> <span m='2189880'>and</span> <span
  m='2189900'>the</span> <span m='2189990'>Z-transform</span> <span
  m='2190650'>of</span> <span m='2190710'>the</span> <span
  m='2190830'>sequence</span> <span m='2191520'>multiplied</span> <span
  m='2192150'>by</span> <span m='2192450'>a</span> <span
  m='2192600'>decaying</span> <span m='2192960'>exponential.</span> </p><p><span
  m='2195740'>Well,</span> <span m='2196810'>it's</span> <span
  m='2196960'>interesting</span> <span m='2197740'>to</span> <span
  m='2199300'>look</span> <span m='2199630'>at</span> <span
  m='2200200'>what</span> <span m='2201010'>this</span> <span
  m='2201250'>property</span> <span m='2202720'>implies</span> <span
  m='2203590'>in</span> <span m='2203770'>terms</span> <span
  m='2204430'>of</span> <span m='2205450'>the</span> <span
  m='2206350'>movement</span> <span m='2206950'>of</span> <span
  m='2207130'>the</span> <span m='2207220'>poles</span> <span
  m='2207550'>and</span> <span m='2207670'>zeros</span> <span
  m='2208090'>in</span> <span m='2208210'>the</span> <span
  m='2208270'>z-plane.</span> <span m='2209290'>That</span> <span
  m='2209470'>is,</span> <span m='2210160'>a</span> <span
  m='2210220'>useful</span> <span m='2211120'>notion</span> <span
  m='2211750'>or</span> <span m='2212080'>a</span> <span
  m='2212110'>useful</span> <span m='2213730'>fact</span> <span
  m='2214120'>to</span> <span m='2214270'>have,</span> <span
  m='2214680'>again,</span> <span m='2215010'>stored</span> <span
  m='2215350'>away</span> <span m='2215980'>in</span> <span
  m='2216130'>your</span> <span m='2216250'>hip</span> <span
  m='2216380'>pocket</span> <span m='2217900'>is</span> <span
  m='2219640'>the</span> <span m='2219880'>effect</span> <span
  m='2220510'>on</span> <span m='2220630'>the</span> <span
  m='2220720'>poles</span> <span m='2221080'>and</span> <span
  m='2221200'>zeros</span> <span m='2222310'>of</span> <span
  m='2222430'>a</span> <span m='2222490'>system</span> <span
  m='2222880'>function</span> <span m='2223240'>or</span> <span
  m='2223340'>a</span> <span m='2223480'>Z-transform</span> <span
  m='2225250'>of</span> <span m='2226450'>multiplying</span> <span
  m='2227590'>the</span> <span m='2227680'>sequence</span> <span
  m='2228580'>by</span> <span m='2229360'>an</span> <span
  m='2229480'>exponential--</span> <span m='2230140'>maybe</span> <span
  m='2230410'>a</span> <span m='2230470'>complex</span> <span
  m='2230980'>exponential,</span> <span m='2231670'>maybe</span> <span
  m='2231970'>a</span> <span m='2232030'>real</span> <span
  m='2232300'>exponential.</span> <span m='2234530'>Well,</span> <span
  m='2234730'>let's</span> <span m='2234790'>focus</span> <span
  m='2235570'>on</span> <span m='2236980'>a</span> <span m='2237040'>pole</span>
  <span m='2237390'>or a</span> <span m='2237530'>0.</span> <span
  m='2239520'>And</span> <span m='2240600'>the</span> <span
  m='2240720'>result</span> <span m='2241050'>that</span> <span
  m='2241170'>we</span> <span m='2241290'>get</span> <span m='2241530'>by</span>
  <span m='2242190'>considering</span> <span m='2242670'>just</span> <span
  m='2243210'>a</span> <span m='2243270'>simple</span> <span m='2243960'>pole
  or</span> <span m='2244380'>0</span> <span m='2245270'>will,</span> <span
  m='2245460'>of</span> <span m='2245550'>course,</span> <span
  m='2245790'>generalize</span> <span m='2246450'>to</span> <span
  m='2246570'>all</span> <span m='2246810'>the</span> <span
  m='2246900'>poles</span> <span m='2247260'>and</span> <span
  m='2247350'>zeros.</span> </p><p><span m='2248580'>So</span> <span
  m='2249060'>let's</span> <span m='2249330'>consider</span> <span
  m='2249810'>x</span> <span m='2250080'>of</span> <span m='2250200'>z</span>
  <span m='2251400'>to</span> <span m='2251520'>have</span> <span
  m='2251760'>a</span> <span m='2251820'>factor</span> <span
  m='2252390'>either</span> <span m='2252600'>in</span> <span
  m='2252720'>the</span> <span m='2252780'>numerator</span> <span
  m='2253380'>and</span> <span m='2253470'>denominator</span> <span
  m='2254760'>of</span> <span m='2254880'>the</span> <span
  m='2254970'>form</span> <span m='2255390'>z</span> <span
  m='2255960'>minus</span> <span m='2256300'>z0.</span> <span
  m='2258500'>Well,</span> <span m='2258800'>x1 of</span> <span
  m='2259100'>z</span> <span m='2260650'>will</span> <span
  m='2260810'>then</span> <span m='2261050'>have</span> <span
  m='2261260'>a</span> <span m='2261350'>factor</span> <span
  m='2262880'>derived</span> <span m='2263450'>from</span> <span
  m='2263660'>that</span> <span m='2263900'>one,</span> <span
  m='2264770'>but</span> <span m='2264980'>for</span> <span
  m='2265160'>which</span> <span m='2265730'>z</span> <span
  m='2266270'>is</span> <span m='2266420'>replaced</span> <span
  m='2267140'>by</span> <span m='2268130'>8</span> <span m='2268340'>to</span>
  <span m='2268430'>the</span> <span m='2268550'>minus</span> <span
  m='2268880'>1</span> <span m='2269120'>times</span> <span
  m='2269480'>z.</span> <span m='2271220'>And</span> <span
  m='2271320'>then</span> <span m='2271440'>we</span> <span
  m='2271560'>have</span> <span m='2271740'>the</span> <span
  m='2271830'>minus</span> <span m='2272360'>z0.</span> <span
  m='2273630'>Or</span> <span m='2273990'>if</span> <span m='2274170'>we</span>
  <span m='2274290'>pull</span> <span m='2275310'>the</span> <span
  m='2275490'>a</span> <span m='2275670'>to</span> <span m='2275730'>the</span>
  <span m='2275820'>minus</span> <span m='2276180'>outside,</span> <span
  m='2277440'>we</span> <span m='2277530'>have</span> <span m='2277710'>a</span>
  <span m='2277920'>to</span> <span m='2277980'>the</span> <span
  m='2278070'>minus</span> <span m='2278460'>1</span> <span
  m='2280290'>times</span> <span m='2281130'>z</span> <span
  m='2281760'>minus</span> <span m='2282270'>a</span> <span
  m='2282510'>times</span> <span m='2282870'>z0.</span> </p><p><span
  m='2284950'>So</span> <span m='2285070'>there</span> <span
  m='2285220'>are</span> <span m='2285280'>two</span> <span
  m='2285490'>effects</span> <span m='2285940'>here.</span> <span
  m='2286780'>One</span> <span m='2287000'>effect--</span> <span
  m='2287800'>if</span> <span m='2287980'>we</span> <span
  m='2288100'>think</span> <span m='2288430'>of</span> <span
  m='2288670'>x</span> <span m='2288910'>of</span> <span m='2289000'>z</span>
  <span m='2289390'>as</span> <span m='2289570'>a</span> <span
  m='2289630'>product</span> <span m='2290110'>of</span> <span
  m='2290170'>zeros</span> <span m='2290650'>divided</span> <span
  m='2291040'>by</span> <span m='2291220'>a</span> <span
  m='2291280'>product</span> <span m='2291700'>of</span> <span
  m='2291790'>poles--</span> <span m='2292930'>one</span> <span
  m='2293170'>effect</span> <span m='2293860'>is</span> <span
  m='2294430'>that</span> <span m='2294640'>there</span> <span
  m='2294710'>is</span> <span m='2294850'>a</span> <span
  m='2294910'>constant</span> <span m='2295870'>that,</span> <span
  m='2296200'>perhaps,</span> <span m='2296590'>collects</span> <span
  m='2297040'>out</span> <span m='2297250'>in</span> <span
  m='2297370'>front.</span> <span m='2299380'>But</span> <span
  m='2299830'>we</span> <span m='2299950'>never</span> <span
  m='2300160'>see</span> <span m='2300400'>that</span> <span
  m='2300580'>constant</span> <span m='2301290'>anyway</span> <span
  m='2301720'>in</span> <span m='2301810'>the</span> <span
  m='2301900'>pole-0</span> <span m='2302500'>pattern.</span> <span
  m='2303730'>The</span> <span m='2303820'>more</span> <span
  m='2304030'>important</span> <span m='2304660'>point</span> <span
  m='2305590'>is</span> <span m='2305830'>that</span> <span
  m='2307030'>whereas</span> <span m='2307390'>here</span> <span
  m='2307660'>we</span> <span m='2307840'>had,</span> <span
  m='2308080'>say,</span> <span m='2308470'>0</span> <span m='2308890'>at</span>
  <span m='2309310'>z</span> <span m='2309710'>equals</span> <span
  m='2310090'>z0,</span> <span m='2311470'>that</span> <span
  m='2311710'>0</span> <span m='2312250'>is</span> <span m='2312430'>now</span>
  <span m='2312640'>shifted</span> <span m='2314170'>to</span> <span
  m='2314590'>a</span> <span m='2314800'>times</span> <span
  m='2315070'>z0.</span> <span m='2316210'>So</span> <span
  m='2316780'>the</span> <span m='2316990'>0</span> <span m='2317480'>at</span>
  <span m='2317800'>z0</span> <span m='2318190'>gets</span> <span
  m='2318400'>replaced</span> <span m='2318910'>by</span> <span
  m='2319410'>a</span> <span m='2319480'>0</span> <span m='2319960'>at</span>
  <span m='2320140'>eight</span> <span m='2320320'>times</span> <span
  m='2320860'>z0.</span> <span m='2321910'>A pole</span> <span
  m='2322510'>at</span> <span m='2322960'>z0</span> <span
  m='2324010'>gets</span> <span m='2324160'>replaced</span> <span
  m='2324610'>by</span> <span m='2324820'>a</span> <span m='2324880'>pole</span>
  <span m='2325380'>at</span> <span m='2325660'>a</span> <span
  m='2325840'>times</span> <span m='2326330'>z0.</span> </p><p><span
  m='2332230'>Well,</span> <span m='2334180'>more</span> <span
  m='2334330'>specifically,</span> <span m='2336190'>then,</span> <span
  m='2337090'>here's</span> <span m='2337330'>our</span> <span
  m='2337450'>polar</span> <span m='2337980'>0</span> <span
  m='2338830'>which</span> <span m='2339070'>gets</span> <span
  m='2339280'>converted</span> <span m='2340300'>to</span> <span
  m='2340420'>that</span> <span m='2340600'>polar</span> <span
  m='2340990'>0</span> <span m='2341290'>multiplied</span> <span
  m='2341920'>by</span> <span m='2342240'>a.</span> <span m='2344915'>And</span>
  <span m='2347380'>if</span> <span m='2347770'>we</span> <span
  m='2348280'>write</span> <span m='2348970'>this</span> <span
  m='2349570'>or</span> <span m='2349720'>think</span> <span
  m='2349990'>of</span> <span m='2350140'>it</span> <span m='2350860'>in</span>
  <span m='2350980'>polar</span> <span m='2351400'>form,</span> <span
  m='2352600'>as</span> <span m='2352870'>r0</span> <span m='2353950'>e</span>
  <span m='2354070'>to the</span> <span m='2354190'>j theta 0,</span> <span
  m='2355930'>then</span> <span m='2356410'>the</span> <span
  m='2356530'>result</span> <span m='2356980'>is</span> <span
  m='2357180'>a</span> <span m='2357430'>times</span> <span
  m='2357730'>r0</span> <span m='2358870'>times</span> <span
  m='2359220'>e</span> <span m='2359420'>to</span> <span m='2359560'>the</span>
  <span m='2359650'>j theta 0.</span> <span m='2361930'>Well</span> <span
  m='2362080'>obviously</span> <span m='2362740'>then,</span> <span
  m='2363730'>if</span> <span m='2364870'>this</span> <span
  m='2365080'>number</span> <span m='2365530'>a</span> <span
  m='2366040'>is</span> <span m='2366220'>a</span> <span m='2366310'>real</span>
  <span m='2366580'>number,</span> <span m='2368090'>then</span> <span
  m='2368500'>the</span> <span m='2368680'>only</span> <span
  m='2368980'>effect</span> <span m='2370750'>on</span> <span
  m='2371710'>the</span> <span m='2371800'>location</span> <span
  m='2372370'>of</span> <span m='2372460'>the</span> <span
  m='2372580'>pole</span> <span m='2373750'>is</span> <span
  m='2373900'>to</span> <span m='2374020'>change</span> <span
  m='2374410'>its</span> <span m='2374560'>radial</span> <span
  m='2374980'>value</span> <span m='2376150'>and</span> <span
  m='2376300'>not</span> <span m='2376540'>change</span> <span
  m='2376930'>its</span> <span m='2377080'>angle.</span> <span
  m='2378990'>More</span> <span m='2379170'>generally,</span> <span
  m='2379990'>if</span> <span m='2380130'>a</span> <span m='2380340'>is</span>
  <span m='2380490'>complex,</span> <span m='2382090'>then</span> <span
  m='2383100'>to</span> <span m='2383400'>write</span> <span
  m='2383850'>the</span> <span m='2384000'>resulting</span> <span
  m='2384540'>polar</span> <span m='2384900'>zero</span> <span
  m='2386130'>in</span> <span m='2386880'>polar</span> <span
  m='2387240'>form,</span> <span m='2388680'>we</span> <span
  m='2388830'>would</span> <span m='2388980'>replace</span> <span
  m='2389430'>this</span> <span m='2389670'>by</span> <span
  m='2389880'>its</span> <span m='2390060'>magnitude</span> <span
  m='2391650'>and</span> <span m='2392070'>add</span> <span
  m='2392460'>to</span> <span m='2392610'>the</span> <span
  m='2392730'>phase--</span> <span m='2394560'>the</span> <span
  m='2394650'>phase</span> <span m='2395340'>that</span> <span
  m='2395490'>corresponds</span> <span m='2396690'>to</span> <span
  m='2396810'>that</span> <span m='2397020'>number</span> <span
  m='2397410'>a.</span> </p><p><span m='2400270'>Well</span> <span
  m='2400450'>consequently,</span> <span m='2401380'>first</span> <span
  m='2401740'>of</span> <span m='2401860'>all,</span> <span
  m='2402040'>if</span> <span m='2402160'>a</span> <span m='2402280'>is</span>
  <span m='2402460'>real</span> <span m='2404030'>and</span> <span
  m='2404160'>positive,</span> <span m='2404880'>actually,</span> <span
  m='2406030'>if a is</span> <span m='2406380'>real</span> <span
  m='2406680'>and</span> <span m='2406800'>positive,</span> <span
  m='2408250'>then</span> <span m='2408450'>if</span> <span
  m='2408720'>we</span> <span m='2408900'>had</span> <span m='2409050'>a</span>
  <span m='2409110'>pole</span> <span m='2410160'>of</span> <span
  m='2410340'>x</span> <span m='2410590'>of</span> <span m='2410870'>n</span>
  <span m='2411150'>say</span> <span m='2411500'>here,</span> <span
  m='2412380'>here</span> <span m='2412590'>being</span> <span
  m='2412830'>any</span> <span m='2413190'>place,</span> <span
  m='2414420'>then</span> <span m='2415050'>if</span> <span m='2415260'>a</span>
  <span m='2415710'>is</span> <span m='2415860'>real,</span> <span
  m='2417460'>what</span> <span m='2417640'>happens</span> <span
  m='2418090'>to</span> <span m='2418210'>that</span> <span
  m='2418420'>pole</span> <span m='2419620'>is</span> <span
  m='2419830'>that</span> <span m='2420790'>it</span> <span
  m='2420940'>moves</span> <span m='2421930'>either</span> <span
  m='2422260'>in</span> <span m='2423370'>or</span> <span
  m='2423580'>out.</span> <span m='2425080'>But</span> <span
  m='2425320'>it</span> <span m='2425470'>moves</span> <span
  m='2425800'>radially</span> <span m='2427120'>as</span> <span
  m='2427660'>we</span> <span m='2427870'>vary</span> <span
  m='2428230'>the</span> <span m='2428350'>value</span> <span
  m='2428740'>of</span> <span m='2428860'>a.</span> <span m='2430180'>So</span>
  <span m='2431560'>that's</span> <span m='2432160'>for</span> <span
  m='2432580'>a</span> <span m='2433330'>real.</span> </p><p><span
  m='2436900'>What's</span> <span m='2437170'>the</span> <span
  m='2437290'>movement</span> <span m='2437740'>of</span> <span
  m='2437800'>the</span> <span m='2437920'>pole</span> <span
  m='2438430'>if</span> <span m='2438610'>a</span> <span m='2439000'>is</span>
  <span m='2439180'>pure</span> <span m='2439450'>imaginary?</span> <span
  m='2441890'>Well,</span> <span m='2442110'>if</span> <span
  m='2442180'>a</span> <span m='2442400'>is</span> <span m='2442520'>pure</span>
  <span m='2442790'>imaginary,</span> <span m='2444270'>then</span> <span
  m='2444290'>the</span> <span m='2444380'>magnitude</span> <span
  m='2445220'>of</span> <span m='2445370'>a</span> <span m='2446420'>is--</span>
  <span m='2448840'>I'm</span> <span m='2448930'>sorry.</span> <span
  m='2450490'>Not</span> <span m='2450730'>if</span> <span m='2450860'>a</span>
  <span m='2451000'>is</span> <span m='2451150'>pure</span> <span
  m='2451480'>imaginary,</span> <span m='2452380'>but</span> <span
  m='2452740'>if</span> <span m='2452890'>the</span> <span
  m='2452980'>magnitude</span> <span m='2453550'>of</span> <span
  m='2453700'>a</span> <span m='2454120'>is</span> <span
  m='2454300'>equal</span> <span m='2454570'>to</span> <span
  m='2454780'>1</span> <span m='2455120'>and</span> <span m='2455800'>it</span>
  <span m='2455890'>has</span> <span m='2456220'>only</span> <span
  m='2456520'>a</span> <span m='2456580'>phase</span> <span
  m='2456940'>component,</span> <span m='2458200'>in</span> <span
  m='2458320'>that</span> <span m='2458530'>case</span> <span
  m='2458920'>there's</span> <span m='2459100'>no</span> <span
  m='2459280'>effect</span> <span m='2459670'>on</span> <span
  m='2459790'>the</span> <span m='2459880'>radial</span> <span
  m='2460270'>value.</span> <span m='2461290'>There's</span> <span
  m='2461470'>only</span> <span m='2461740'>an</span> <span
  m='2461800'>effect</span> <span m='2462190'>on</span> <span
  m='2462340'>the</span> <span m='2462460'>angle.</span> <span
  m='2463660'>And</span> <span m='2463810'>in</span> <span
  m='2463900'>that</span> <span m='2464140'>case,</span> <span
  m='2464950'>the</span> <span m='2465070'>movement</span> <span
  m='2465760'>of</span> <span m='2465940'>the</span> <span
  m='2466060'>pole</span> <span m='2466990'>is</span> <span
  m='2469270'>such</span> <span m='2469780'>that</span> <span
  m='2469990'>the</span> <span m='2470080'>radial</span> <span
  m='2470560'>value</span> <span m='2471010'>stays</span> <span
  m='2471400'>the</span> <span m='2471520'>same.</span> <span
  m='2472660'>But</span> <span m='2473530'>the</span> <span
  m='2473710'>angle</span> <span m='2474460'>of</span> <span
  m='2474670'>the</span> <span m='2474760'>pole</span> <span
  m='2475120'>changes.</span> </p><p><span m='2476420'>So</span> <span
  m='2476830'>in</span> <span m='2476980'>general,</span> <span
  m='2477460'>of</span> <span m='2477550'>course,</span> <span
  m='2478100'>if</span> <span m='2478110'>a</span> <span m='2478270'>is</span>
  <span m='2478390'>complex,</span> <span m='2479470'>the</span> <span
  m='2479560'>poles</span> <span m='2479860'>can</span> <span
  m='2480040'>have</span> <span m='2480190'>a</span> <span
  m='2480250'>little</span> <span m='2480430'>movement</span> <span
  m='2480850'>that</span> <span m='2481090'>way</span> <span
  m='2481330'>and</span> <span m='2481420'>also</span> <span
  m='2481720'>a</span> <span m='2481750'>little</span> <span
  m='2481930'>movement</span> <span m='2482320'>that</span> <span
  m='2482590'>way.</span> <span m='2484150'>In</span> <span
  m='2484270'>some</span> <span m='2484810'>cases,</span> <span
  m='2488440'>if</span> <span m='2488650'>a</span> <span m='2488950'>is</span>
  <span m='2489100'>pure</span> <span m='2489370'>real,</span> <span
  m='2490090'>the</span> <span m='2490180'>movement</span> <span
  m='2490540'>will</span> <span m='2490690'>just</span> <span
  m='2490900'>be</span> <span m='2491080'>this</span> <span
  m='2491320'>way.</span> <span m='2492470'>And</span> <span
  m='2492700'>if</span> <span m='2492790'>the</span> <span
  m='2492880'>magnitude</span> <span m='2493420'>of</span> <span
  m='2493510'>a</span> <span m='2493660'>is</span> <span
  m='2493780'>equal</span> <span m='2494050'>to</span> <span
  m='2494200'>1,</span> <span m='2495580'>the</span> <span
  m='2495700'>movement</span> <span m='2496060'>of</span> <span
  m='2496180'>the</span> <span m='2496270'>pole</span> <span
  m='2496840'>will</span> <span m='2496960'>just</span> <span
  m='2497200'>be</span> <span m='2497380'>that</span> <span
  m='2497620'>way.</span> </p><p><span m='2499700'>All</span> <span
  m='2499760'>right,</span> <span m='2500030'>so</span> <span
  m='2501200'>we</span> <span m='2501320'>have</span> <span
  m='2501530'>first</span> <span m='2501890'>of</span> <span
  m='2502010'>all,</span> <span m='2502350'>a</span> <span
  m='2502450'>list</span> <span m='2502610'>of</span> <span
  m='2502700'>properties.</span> <span m='2503420'>But</span> <span
  m='2503840'>in</span> <span m='2503960'>particular,</span> <span
  m='2504630'>there</span> <span m='2504740'>are</span> <span
  m='2504770'>two</span> <span m='2505640'>that</span> <span
  m='2505790'>we've</span> <span m='2505940'>spent</span> <span
  m='2506270'>a</span> <span m='2506330'>little</span> <span
  m='2506570'>time</span> <span m='2506930'>on.</span> <span
  m='2509080'>Finally,</span> <span m='2509960'>let's</span> <span
  m='2510980'>look</span> <span m='2511370'>at,</span> <span
  m='2512270'>actually,</span> <span m='2512690'>one</span> <span
  m='2512930'>example</span> <span m='2513530'>or</span> <span
  m='2513740'>one</span> <span m='2513970'>and</span> <span m='2514200'>a
  half</span> <span m='2514430'>examples</span> <span m='2516880'>to</span>
  <span m='2517570'>see</span> <span m='2518020'>how</span> <span
  m='2518410'>some</span> <span m='2518710'>of</span> <span
  m='2518770'>the</span> <span m='2518860'>properties</span> <span
  m='2519460'>might</span> <span m='2519700'>be</span> <span
  m='2519820'>useful</span> <span m='2520720'>in</span> <span
  m='2521590'>obtaining</span> <span m='2522460'>the</span> <span
  m='2524700'>frequency</span> <span m='2525300'>response,</span> <span
  m='2525900'>or</span> <span m='2525990'>the</span> <span
  m='2526080'>Z-transform</span> <span m='2527160'>of</span> <span
  m='2527310'>a</span> <span m='2527340'>system.</span> </p><p><span
  m='2529050'>And</span> <span m='2529800'>the</span> <span
  m='2530100'>sequence</span> <span m='2530850'>that</span> <span
  m='2531030'>I</span> <span m='2531120'>want</span> <span m='2531270'>to</span>
  <span m='2531330'>focus</span> <span m='2531810'>on</span> <span
  m='2532740'>is</span> <span m='2532980'>a</span> <span
  m='2533040'>sequence</span> <span m='2533820'>that</span> <span
  m='2534840'>will</span> <span m='2535080'>play</span> <span
  m='2535770'>an</span> <span m='2535830'>important</span> <span
  m='2536310'>role</span> <span m='2537810'>throughout</span> <span
  m='2538290'>digital</span> <span m='2538620'>signal</span> <span
  m='2538950'>processing</span> <span m='2539940'>and</span> <span
  m='2540090'>in</span> <span m='2540150'>particular,</span> <span
  m='2540660'>in</span> <span m='2540750'>some</span> <span
  m='2540960'>lectures</span> <span m='2541320'>coming</span> <span
  m='2541680'>up,</span> <span m='2542440'>which</span> <span
  m='2542520'>is</span> <span m='2542640'>a</span> <span
  m='2542700'>sequence</span> <span m='2543780'>that</span> <span
  m='2544020'>I'll</span> <span m='2544140'>refer</span> <span
  m='2544500'>to</span> <span m='2544860'>as</span> <span m='2545010'>a</span>
  <span m='2545070'>boxcar</span> <span m='2545670'>sequence.</span> <span
  m='2546920'>It's</span> <span m='2547110'>the</span> <span
  m='2547230'>sequence</span> <span m='2548040'>which</span> <span
  m='2548250'>is</span> <span m='2548400'>equal</span> <span
  m='2548640'>to</span> <span m='2548760'>unity</span> <span
  m='2550680'>for</span> <span m='2550890'>n</span> <span
  m='2551100'>between</span> <span m='2551490'>0</span> <span
  m='2552000'>and</span> <span m='2552120'>capital</span> <span
  m='2552600'>N</span> <span m='2552720'>minus</span> <span
  m='2553140'>1.</span> <span m='2554160'>And</span> <span
  m='2554280'>it's</span> <span m='2554400'>equal</span> <span
  m='2554670'>to</span> <span m='2554820'>0</span> <span
  m='2555510'>otherwise.</span> <span m='2557250'>It's</span> <span
  m='2557400'>basically</span> <span m='2558240'>a</span> <span
  m='2558330'>rectangular</span> <span m='2559050'>sequence.</span> <span
  m='2561300'>0</span> <span m='2561820'>for</span> <span m='2562000'>n</span>
  <span m='2562150'>negative,</span> <span m='2563230'>0</span> <span
  m='2563770'>for</span> <span m='2564010'>n</span> <span
  m='2564310'>greater</span> <span m='2564640'>than</span> <span
  m='2564790'>or</span> <span m='2564910'>equal</span> <span
  m='2565150'>to</span> <span m='2565270'>capital</span> <span
  m='2565550'>N</span> <span m='2565830'>and</span> <span
  m='2566380'>unity</span> <span m='2566840'>otherwise.</span> <span
  m='2567820'>It's</span> <span m='2568300'>the</span> <span
  m='2568940'>counterpart</span> <span m='2569830'>of</span> <span
  m='2570070'>the</span> <span m='2570190'>rectangular</span> <span
  m='2570790'>time</span> <span m='2571120'>function.</span> </p><p><span
  m='2573980'>Well,</span> <span m='2574720'>there</span> <span
  m='2575080'>are</span> <span m='2575260'>a</span> <span
  m='2575290'>couple</span> <span m='2575620'>of</span> <span
  m='2575710'>ways</span> <span m='2576010'>of</span> <span
  m='2576130'>getting</span> <span m='2576400'>at</span> <span
  m='2576490'>Z-transform.</span> <span m='2577660'>Since</span> <span
  m='2577960'>we</span> <span m='2578080'>had</span> <span
  m='2578290'>some</span> <span m='2578440'>properties,</span> <span
  m='2579430'>let's</span> <span m='2579700'>use</span> <span
  m='2580810'>one</span> <span m='2581020'>of</span> <span
  m='2581140'>them,</span> <span m='2581560'>in</span> <span
  m='2581650'>particular,</span> <span m='2582130'>the</span> <span
  m='2582250'>Shifting</span> <span m='2582670'>Property.</span> <span
  m='2584320'>We</span> <span m='2584470'>can</span> <span
  m='2584620'>think</span> <span m='2584950'>of</span> <span
  m='2585040'>a</span> <span m='2585110'>boxcar</span> <span
  m='2585730'>sequence</span> <span m='2588000'>as</span> <span
  m='2588180'>the</span> <span m='2588270'>sum</span> <span
  m='2588600'>of</span> <span m='2588690'>two</span> <span
  m='2588900'>sequences.</span> <span m='2590310'>One</span> <span
  m='2590880'>is</span> <span m='2591390'>a</span> <span m='2591450'>unit</span>
  <span m='2591810'>step.</span> <span m='2593580'>And</span> <span
  m='2593700'>the</span> <span m='2593790'>second</span> <span
  m='2594630'>is</span> <span m='2595590'>the</span> <span
  m='2595710'>negative</span> <span m='2596130'>of</span> <span
  m='2596250'>a</span> <span m='2596270'>unit</span> <span
  m='2596580'>step</span> <span m='2597090'>starting</span> <span
  m='2597830'>at</span> <span m='2598040'>n</span> <span
  m='2598230'>equals</span> <span m='2598530'>capital</span> <span
  m='2599030'>N</span> <span m='2599610'>to</span> <span
  m='2599730'>subtract</span> <span m='2600300'>off</span> <span
  m='2600540'>these</span> <span m='2600750'>other</span> <span
  m='2600960'>values.</span> <span m='2603420'>We</span> <span
  m='2603630'>can</span> <span m='2604200'>express</span> <span
  m='2605130'>x</span> <span m='2605610'>of n,</span> <span
  m='2606090'>the</span> <span m='2606210'>boxcar</span> <span
  m='2606720'>sequence,</span> <span m='2608010'>as</span> <span
  m='2608160'>a</span> <span m='2608220'>unit</span> <span
  m='2608550'>step</span> <span m='2610240'>minus</span> <span
  m='2610860'>a</span> <span m='2610920'>unit</span> <span
  m='2611250'>step</span> <span m='2611910'>delayed</span> <span
  m='2612240'>by</span> <span m='2612420'>capital</span> <span
  m='2612675'>N.</span> </p><p><span m='2614460'>Well,</span> <span
  m='2615390'>if</span> <span m='2615600'>you</span> <span
  m='2615690'>don't</span> <span m='2615990'>see</span> <span
  m='2616320'>this</span> <span m='2616620'>graphical</span> <span
  m='2617190'>picture</span> <span m='2617610'>exactly,</span> <span
  m='2618750'>you</span> <span m='2618840'>can</span> <span
  m='2618960'>just</span> <span m='2619140'>see</span> <span
  m='2619320'>quickly</span> <span m='2620100'>that</span> <span
  m='2620430'>this</span> <span m='2620670'>is</span> <span
  m='2620790'>true</span> <span m='2621120'>since</span> <span
  m='2622050'>for</span> <span m='2622350'>n</span> <span
  m='2622620'>greater</span> <span m='2623040'>than</span> <span
  m='2623790'>or</span> <span m='2623940'>equal</span> <span
  m='2624210'>to</span> <span m='2624330'>capital</span> <span
  m='2624870'>N,</span> <span m='2625740'>both</span> <span
  m='2626010'>of</span> <span m='2626130'>these</span> <span
  m='2626340'>arguments</span> <span m='2627060'>are</span> <span
  m='2627210'>non-negative.</span> <span m='2628530'>So</span> <span
  m='2628920'>the</span> <span m='2629040'>value</span> <span
  m='2629430'>of</span> <span m='2629490'>both</span> <span
  m='2629760'>of</span> <span m='2629850'>these</span> <span
  m='2630060'>units</span> <span m='2630320'>steps</span> <span
  m='2630660'>is</span> <span m='2630780'>unity.</span> <span
  m='2631380'>And</span> <span m='2631530'>they</span> <span
  m='2631650'>subtract</span> <span m='2632160'>off</span> <span
  m='2632340'>to</span> <span m='2632490'>zero.</span> </p><p><span
  m='2635320'>All</span> <span m='2635380'>right,</span> <span
  m='2635890'>then</span> <span m='2636040'>to</span> <span
  m='2636160'>get</span> <span m='2636340'>the</span> <span
  m='2636460'>Z-transform,</span> <span m='2638140'>we</span> <span
  m='2638290'>can</span> <span m='2638440'>add</span> <span
  m='2638620'>the</span> <span m='2638710'>Z-transform</span> <span
  m='2639150'>or</span> <span m='2639410'>this</span> <span
  m='2639640'>piece</span> <span m='2640120'>and</span> <span
  m='2640240'>this</span> <span m='2640450'>piece.</span> <span
  m='2642390'>The</span> <span m='2642510'>Z-transform</span> <span
  m='2643260'>of</span> <span m='2643330'>a</span> <span m='2643380'>unit</span>
  <span m='2643710'>step,</span> <span m='2644340'>well</span> <span
  m='2644610'>that's</span> <span m='2644790'>our</span> <span
  m='2644910'>old</span> <span m='2645090'>friend</span> <span
  m='2645420'>a</span> <span m='2645750'>to</span> <span m='2646000'>the</span>
  <span m='2646470'>n</span> <span m='2646710'>times</span> <span
  m='2647040'>a</span> <span m='2647100'>unit</span> <span
  m='2647400'>step,</span> <span m='2647760'>except</span> <span
  m='2648120'>in</span> <span m='2648210'>this</span> <span
  m='2648360'>case,</span> <span m='2648630'>a</span> <span
  m='2648720'>equals</span> <span m='2649110'>1.</span> <span
  m='2650340'>So</span> <span m='2650610'>the</span> <span
  m='2650700'>Z-transform</span> <span m='2651570'>of</span> <span
  m='2651630'>this</span> <span m='2651900'>piece</span> <span
  m='2652320'>is</span> <span m='2652470'>1</span> <span m='2652830'>over</span>
  <span m='2653160'>1</span> <span m='2653400'>minus</span> <span m='2654030'>z
  to the</span> <span m='2654480'>minus</span> <span m='2654870'>1.</span>
  </p><p><span m='2657550'>This</span> <span m='2657820'>one</span> <span
  m='2658480'>is</span> <span m='2658630'>this</span> <span
  m='2658870'>one</span> <span m='2659110'>shifted.</span> <span
  m='2660610'>So</span> <span m='2660910'>we</span> <span m='2661060'>can</span>
  <span m='2661180'>apply</span> <span m='2661570'>our</span> <span
  m='2661660'>Shifting</span> <span m='2662140'>Property</span> <span
  m='2663130'>to</span> <span m='2663250'>multiply</span> <span
  m='2663940'>this</span> <span m='2664480'>by</span> <span m='2664750'>z</span>
  <span m='2665110'>to</span> <span m='2665260'>the</span> <span
  m='2665380'>minus</span> <span m='2666010'>capital</span> <span
  m='2666530'>N,</span> <span m='2667030'>since</span> <span
  m='2667630'>that's</span> <span m='2667870'>the</span> <span
  m='2667990'>amount</span> <span m='2668230'>of</span> <span
  m='2668320'>our</span> <span m='2668440'>shift,</span> <span
  m='2669960'>so</span> <span m='2670200'>that</span> <span
  m='2670770'>this</span> <span m='2671010'>piece,</span> <span
  m='2671400'>then,</span> <span m='2671880'>has</span> <span
  m='2672150'>a</span> <span m='2672210'>Z-transform</span> <span
  m='2672840'>z</span> <span m='2673230'>to</span> <span m='2673380'>the</span>
  <span m='2673470'>minus</span> <span m='2673890'>n</span> <span
  m='2674190'>over</span> <span m='2674460'>1</span> <span
  m='2674670'>minus</span> <span m='2674980'>z</span> <span
  m='2675180'>to</span> <span m='2675330'>the</span> <span
  m='2675420'>minus</span> <span m='2675840'>1.</span> <span
  m='2677810'>Or</span> <span m='2678810'>if</span> <span m='2679260'>we</span>
  <span m='2682370'>add</span> <span m='2682610'>these</span> <span
  m='2682820'>two</span> <span m='2683000'>together,</span> <span
  m='2684230'>we</span> <span m='2684380'>have</span> <span m='2684830'>1</span>
  <span m='2685250'>minus</span> <span m='2685640'>z to</span> <span
  m='2686080'>the</span> <span m='2686180'>minus</span> <span
  m='2686510'>capital</span> <span m='2687050'>N</span> <span
  m='2688190'>divided</span> <span m='2688700'>by</span> <span
  m='2689420'>1</span> <span m='2689660'>minus</span> <span m='2690330'>z</span>
  <span m='2690500'>to</span> <span m='2690650'>the</span> <span
  m='2690740'>minus</span> <span m='2691130'>1.</span> <span
  m='2693110'>Or</span> <span m='2693320'>we</span> <span m='2693470'>can</span>
  <span m='2693620'>rewrite</span> <span m='2694070'>that,</span> <span
  m='2695060'>just</span> <span m='2695450'>to</span> <span
  m='2695690'>focus</span> <span m='2696110'>on</span> <span
  m='2696200'>something</span> <span m='2696500'>a</span> <span
  m='2696530'>little</span> <span m='2696680'>more</span> <span
  m='2696860'>clearly,</span> <span m='2698760'>multiplying</span> <span
  m='2700440'>top</span> <span m='2700710'>and</span> <span
  m='2700830'>bottom</span> <span m='2702120'>by</span> <span
  m='2702540'>z</span> <span m='2702750'>to</span> <span m='2702930'>the</span>
  <span m='2703200'>n</span> <span m='2703380'>minus</span> <span
  m='2703800'>1.</span> <span m='2704620'>We</span> <span m='2704720'>can</span>
  <span m='2704790'>rewrite</span> <span m='2705210'>that</span> <span
  m='2705540'>in</span> <span m='2705690'>this</span> <span
  m='2705900'>form</span> <span m='2706990'>so</span> <span
  m='2707010'>that</span> <span m='2707220'>we</span> <span
  m='2707370'>have</span> <span m='2707640'>in</span> <span
  m='2707730'>the</span> <span m='2707820'>numerator</span> <span m='2708390'>z
  to</span> <span m='2708750'>the</span> <span m='2708840'>capital</span> <span
  m='2709260'>N</span> <span m='2709410'>minus</span> <span
  m='2709780'>1,</span> <span m='2710640'>in</span> <span m='2710730'>the</span>
  <span m='2710790'>denominator,</span> <span m='2711900'>this</span> <span
  m='2712140'>factor</span> <span m='2712800'>times</span> <span m='2713180'>z
  to</span> <span m='2713460'>the</span> <span m='2713550'>minus</span> <span
  m='2713960'>1.</span> </p><p><span m='2717030'>Well,</span> <span
  m='2717590'>let's</span> <span m='2718040'>look</span> <span
  m='2718250'>at</span> <span m='2718310'>the</span> <span
  m='2718400'>pole-zero</span> <span m='2719000'>pattern.</span> <span
  m='2722860'>First</span> <span m='2723060'>of</span> <span
  m='2723210'>all,</span> <span m='2724650'>at</span> <span m='2727680'>z</span>
  <span m='2727830'>equals</span> <span m='2728250'>1,</span> <span
  m='2730120'>we</span> <span m='2730140'>have</span> <span m='2730320'>a</span>
  <span m='2730360'>pole.</span> <span m='2733180'>So</span> <span
  m='2733360'>there's</span> <span m='2733570'>that</span> <span
  m='2733840'>pole.</span> <span m='2735190'>Second</span> <span
  m='2735640'>of</span> <span m='2735730'>all,</span> <span
  m='2736300'>at</span> <span m='2736870'>z</span> <span
  m='2737140'>equals</span> <span m='2737410'>0,</span> <span
  m='2738580'>we</span> <span m='2738730'>have</span> <span m='2739120'>n</span>
  <span m='2739330'>minus1</span> <span m='2739720'>poles.</span> <span
  m='2739990'>Well,</span> <span m='2741670'>let's</span> <span
  m='2741880'>stick</span> <span m='2742180'>in</span> <span
  m='2742300'>the</span> <span m='2742420'>n</span> <span m='2742570'>minus
  1</span> <span m='2742900'>poles.</span> <span m='2743710'>And</span> <span
  m='2743830'>let</span> <span m='2743980'>me</span> <span
  m='2744760'>just</span> <span m='2745210'>draw</span> <span
  m='2745480'>that</span> <span m='2745690'>with</span> <span
  m='2745840'>an</span> <span m='2745930'>asterisk</span> <span
  m='2746620'>and</span> <span m='2746710'>an</span> <span
  m='2746800'>indication</span> <span m='2747430'>that</span> <span
  m='2747580'>that's</span> <span m='2747960'>n</span> <span m='2748180'>minus
  1</span> <span m='2748570'>poles.</span> <span m='2751330'>That's</span> <span
  m='2751550'>from</span> <span m='2751730'>that</span> <span
  m='2751970'>term.</span> </p><p><span m='2753820'>And</span> <span
  m='2754060'>the</span> <span m='2754150'>zeros,</span> <span
  m='2755170'>well,</span> <span m='2755740'>where</span> <span m='2755950'>are
  the</span> <span m='2756070'>zeros?</span> <span m='2756510'>They're</span>
  <span m='2756610'>the</span> <span m='2756730'>roots</span> <span
  m='2757000'>of</span> <span m='2757060'>the</span> <span
  m='2757150'>numerator,</span> <span m='2758150'>which</span> <span
  m='2758320'>are</span> <span m='2758890'>at</span> <span
  m='2759190'>the</span> <span m='2759370'>N</span> <span
  m='2760840'>roots</span> <span m='2761290'>of</span> <span
  m='2761380'>unity.</span> <span m='2763680'>Where</span> <span
  m='2763950'>are</span> <span m='2764040'>they?</span> <span
  m='2764750'>They're</span> <span m='2764970'>distributed.</span> <span
  m='2765630'>The N</span> <span m='2765960'>roots</span> <span
  m='2766200'>of</span> <span m='2766290'>unity</span> <span
  m='2766770'>are</span> <span m='2766890'>distributed</span> <span
  m='2767790'>around</span> <span m='2768210'>the</span> <span
  m='2768300'>unit</span> <span m='2768600'>circle</span> <span
  m='2769650'>equally</span> <span m='2770130'>spaced</span> <span
  m='2770850'>in</span> <span m='2771030'>angle</span> <span
  m='2772800'>starting</span> <span m='2773520'>at z</span> <span
  m='2773950'>equals</span> <span m='2774410'>1.</span> <span
  m='2776070'>So</span> <span m='2776790'>there's</span> <span
  m='2777010'>a</span> <span m='2777060'>zero</span> <span m='2777540'>at
  z</span> <span m='2777690'>equals</span> <span m='2778110'>1.</span> <span
  m='2778515'>But</span> <span m='2778920'>there's</span> <span
  m='2779100'>also</span> <span m='2779400'>a</span> <span
  m='2779460'>pole</span> <span m='2779840'>it</span> <span
  m='2780000'>equals</span> <span m='2780480'>1.</span> <span
  m='2781170'>So</span> <span m='2781320'>in</span> <span
  m='2781410'>fact</span> <span m='2781740'>at z</span> <span
  m='2781890'>equals</span> <span m='2782310'>1,</span> <span
  m='2782850'>there's</span> <span m='2783060'>neither</span> <span
  m='2783420'>0</span> <span m='2783750'>nor</span> <span m='2783990'>a</span>
  <span m='2784050'>pole</span> <span m='2784500'>because</span> <span
  m='2784800'>the</span> <span m='2784920'>two</span> <span
  m='2785100'>cancel</span> <span m='2785580'>out.</span> </p><p><span
  m='2787570'>If</span> <span m='2787720'>we</span> <span
  m='2787810'>look</span> <span m='2787990'>at</span> <span
  m='2788080'>the</span> <span m='2788200'>other</span> <span
  m='2788450'>zeros,</span> <span m='2789400'>then</span> <span
  m='2790330'>let's</span> <span m='2791110'>take</span> <span
  m='2791290'>a</span> <span m='2791350'>specific</span> <span
  m='2791830'>case,</span> <span m='2792280'>that</span> <span
  m='2792430'>is</span> <span m='2792580'>n equals</span> <span
  m='2792980'>8.</span> <span m='2793900'>We'd</span> <span
  m='2794050'>expect</span> <span m='2794440'>to</span> <span
  m='2794560'>see</span> <span m='2795610'>eight</span> <span
  m='2795880'>zeros,</span> <span m='2796780'>except</span> <span
  m='2797140'>for</span> <span m='2797290'>the</span> <span m='2797380'>1</span>
  <span m='2797740'>at z</span> <span m='2797980'>equals</span> <span
  m='2798310'>1 that</span> <span m='2798580'>got</span> <span
  m='2798730'>canceled</span> <span m='2799240'>out.</span> <span
  m='2800080'>So</span> <span m='2800380'>there</span> <span
  m='2800460'>are</span> <span m='2800560'>seven</span> <span
  m='2800950'>left--</span> <span m='2802820'>one</span> <span
  m='2803100'>there,</span> <span m='2804016'>there,</span> <span
  m='2805390'>there,</span> <span m='2806850'>there,</span> <span
  m='2808500'>here,</span> <span m='2809880'>here,</span> <span
  m='2810690'>and</span> <span m='2810840'>here.</span> <span
  m='2812160'>Then,</span> <span m='2812820'>there</span> <span
  m='2813180'>was</span> <span m='2813420'>the</span> <span
  m='2813540'>one</span> <span m='2813750'>at</span> <span
  m='2813840'>the</span> <span m='2813990'>origin.</span> <span
  m='2814740'>Let</span> <span m='2814890'>me</span> <span
  m='2815070'>just</span> <span m='2817900'>indicate</span> <span
  m='2818530'>that</span> <span m='2819220'>and</span> <span
  m='2819370'>the</span> <span m='2819460'>fact</span> <span
  m='2820240'>that</span> <span m='2820360'>it</span> <span
  m='2820420'>got</span> <span m='2820600'>canceled</span> <span
  m='2821110'>out</span> <span m='2821320'>by</span> <span m='2821500'>a</span>
  <span m='2821560'>pole.</span> <span m='2822940'>So</span> <span
  m='2823090'>in</span> <span m='2823180'>fact,</span> <span
  m='2823450'>that</span> <span m='2823690'>one</span> <span
  m='2823870'>isn't</span> <span m='2824080'>there.</span> <span
  m='2826330'>So</span> <span m='2826780'>the</span> <span
  m='2826900'>pole-zero</span> <span m='2827510'>pattern</span> <span
  m='2828130'>for</span> <span m='2828250'>the</span> <span
  m='2828340'>boxcar</span> <span m='2828910'>sequence,</span> <span
  m='2829480'>then,</span> <span m='2830290'>is</span> <span
  m='2830850'>n</span> <span m='2831070'>minus</span> <span m='2831400'>1
  poles</span> <span m='2831970'>at</span> <span m='2832060'>the</span> <span
  m='2832210'>origin</span> <span m='2833830'>plus</span> <span
  m='2834730'>zeros</span> <span m='2836290'>equally</span> <span
  m='2836710'>spaced</span> <span m='2837120'>in</span> <span
  m='2837250'>angle,</span> <span m='2837940'>but</span> <span
  m='2838090'>with</span> <span m='2838270'>the</span> <span
  m='2838390'>1</span> <span m='2838570'>at z</span> <span m='2838730'>equals
  1</span> <span m='2839140'>missing.</span> </p><p><span
  m='2841650'>Now,</span> <span m='2842100'>what</span> <span
  m='2842280'>does</span> <span m='2842430'>this</span> <span
  m='2842640'>mean</span> <span m='2844050'>in</span> <span
  m='2844170'>terms</span> <span m='2844470'>of</span> <span
  m='2844530'>the</span> <span m='2844620'>frequency</span> <span
  m='2845130'>response?</span> <span m='2846630'>Well,</span> <span
  m='2847170'>we</span> <span m='2847380'>can</span> <span
  m='2847830'>very</span> <span m='2848130'>quickly</span> <span
  m='2848790'>generate</span> <span m='2849660'>the</span> <span
  m='2850020'>frequency</span> <span m='2850620'>response,</span> <span
  m='2851850'>or</span> <span m='2852090'>a</span> <span
  m='2852210'>rough</span> <span m='2852540'>idea</span> <span
  m='2852930'>of</span> <span m='2853050'>the</span> <span
  m='2853140'>frequency</span> <span m='2853650'>response,</span> <span
  m='2854760'>geometrically</span> <span m='2855810'>by</span> <span
  m='2856440'>referring</span> <span m='2856950'>back</span> <span
  m='2857580'>to</span> <span m='2857700'>the</span> <span
  m='2857820'>set</span> <span m='2858030'>of</span> <span
  m='2858150'>ideas</span> <span m='2859290'>that</span> <span
  m='2859590'>we</span> <span m='2859770'>introduced</span> <span
  m='2860250'>at</span> <span m='2860340'>the</span> <span
  m='2860430'>beginning</span> <span m='2860820'>of</span> <span
  m='2860910'>the</span> <span m='2861000'>lecture</span> <span
  m='2862740'>and</span> <span m='2862950'>ask</span> <span
  m='2863430'>what</span> <span m='2863670'>the</span> <span
  m='2863790'>behavior</span> <span m='2865050'>of</span> <span
  m='2865740'>the</span> <span m='2866580'>pole-zero</span> <span
  m='2867570'>vectors</span> <span m='2868110'>are</span> <span
  m='2868830'>as</span> <span m='2869010'>we</span> <span m='2869100'>go</span>
  <span m='2869310'>around</span> <span m='2869760'>the</span> <span
  m='2869880'>unit</span> <span m='2870150'>circle.</span> <span
  m='2871860'>The</span> <span m='2871950'>pole</span> <span
  m='2872250'>vectors,</span> <span m='2873090'>first</span> <span
  m='2873420'>of</span> <span m='2873570'>all,</span> <span
  m='2874230'>introduce</span> <span m='2874740'>only</span> <span
  m='2874980'>a</span> <span m='2875040'>linear</span> <span
  m='2875370'>phase</span> <span m='2875760'>term</span> <span
  m='2876240'>and</span> <span m='2876390'>have</span> <span
  m='2876570'>no</span> <span m='2876780'>effect</span> <span
  m='2877140'>on</span> <span m='2877230'>the</span> <span
  m='2877320'>magnitude.</span> <span m='2878160'>We</span> <span
  m='2878280'>had</span> <span m='2878370'>agreed</span> <span
  m='2878700'>on</span> <span m='2878820'>that</span> <span
  m='2879000'>before.</span> <span m='2881520'>And</span> <span
  m='2882530'>so</span> <span m='2882770'>for</span> <span
  m='2882920'>the</span> <span m='2883010'>magnitude,</span> <span
  m='2883880'>we</span> <span m='2884060'>only</span> <span
  m='2884330'>need</span> <span m='2884540'>focus</span> <span
  m='2885380'>on</span> <span m='2885530'>the</span> <span
  m='2885660'>zeros.</span> </p><p><span m='2888260'>Well,</span> <span
  m='2889280'>one</span> <span m='2889490'>thing</span> <span
  m='2889850'>is</span> <span m='2890000'>obvious</span> <span
  m='2890750'>and</span> <span m='2890870'>that</span> <span
  m='2891110'>is</span> <span m='2891770'>that</span> <span
  m='2892970'>as</span> <span m='2896590'>we</span> <span m='2896740'>go</span>
  <span m='2896920'>around</span> <span m='2897280'>the</span> <span
  m='2897370'>unit</span> <span m='2897640'>circle,</span> <span
  m='2898810'>the</span> <span m='2898900'>frequency</span> <span
  m='2899410'>response</span> <span m='2899920'>is</span> <span
  m='2900100'>obviously</span> <span m='2900820'>0</span> <span
  m='2902170'>when</span> <span m='2902500'>we</span> <span
  m='2902650'>hit</span> <span m='2902920'>each</span> <span
  m='2903190'>one</span> <span m='2903340'>of</span> <span
  m='2903430'>these</span> <span m='2903570'>zeros.</span> <span
  m='2905110'>That</span> <span m='2905320'>corresponds</span> <span
  m='2906550'>to</span> <span m='2907630'>pi</span> <span
  m='2907870'>over</span> <span m='2908110'>4,</span> <span
  m='2908670'>pi</span> <span m='2908950'>over</span> <span
  m='2909190'>2,</span> <span m='2910600'>pi</span> <span
  m='2910840'>over</span> <span m='2911020'>2</span> <span
  m='2911200'>plus</span> <span m='2911470'>pi</span> <span
  m='2911750'>over</span> <span m='2911980'>4--</span> <span
  m='2912310'>whatever</span> <span m='2912580'>that</span> <span
  m='2912820'>is,</span> <span m='2913480'>pi,</span> <span
  m='2915010'>and</span> <span m='2915280'>the</span> <span
  m='2915370'>next</span> <span m='2915640'>increment</span> <span
  m='2916030'>of</span> <span m='2916120'>pi over 4,</span> <span m='2916360'>et
  cetera.</span> <span m='2918640'>Furthermore,</span> <span
  m='2919180'>you</span> <span m='2919300'>can</span> <span
  m='2919450'>see</span> <span m='2919690'>that</span> <span
  m='2920110'>at</span> <span m='2920230'>least,</span> <span
  m='2920500'>it's</span> <span m='2920650'>not</span> <span
  m='2920920'>implausible.</span> <span m='2921970'>Actually,</span> <span
  m='2922690'>we</span> <span m='2922960'>really</span> <span
  m='2923560'>could</span> <span m='2923740'>argue</span> <span
  m='2924040'>this</span> <span m='2924220'>somewhat</span> <span
  m='2924550'>precisely,</span> <span m='2926200'>that</span> <span
  m='2926410'>at</span> <span m='2927070'>omega</span> <span
  m='2927490'>equals</span> <span m='2927790'>0,</span> <span
  m='2929410'>that's</span> <span m='2930760'>the</span> <span
  m='2930880'>place</span> <span m='2931780'>where</span> <span
  m='2932080'>we're</span> <span m='2932380'>the</span> <span
  m='2932620'>farthest</span> <span m='2933190'>away</span> <span
  m='2934090'>from</span> <span m='2934330'>all</span> <span
  m='2934510'>the</span> <span m='2934620'>zeros.</span> <span
  m='2936280'>As</span> <span m='2936460'>we</span> <span
  m='2936580'>start</span> <span m='2936880'>moving</span> <span
  m='2937270'>around</span> <span m='2937540'>the</span> <span
  m='2937660'>unit</span> <span m='2937930'>circle,</span> <span
  m='2939040'>if</span> <span m='2939190'>we're</span> <span
  m='2939350'>in-between</span> <span m='2939970'>two</span> <span
  m='2940180'>of</span> <span m='2940270'>these</span> <span
  m='2940440'>zeros,</span> <span m='2941440'>maybe</span> <span
  m='2941710'>we're</span> <span m='2941890'>a</span> <span
  m='2941920'>little</span> <span m='2942130'>farther</span> <span
  m='2942550'>away</span> <span m='2942790'>from</span> <span
  m='2943000'>one</span> <span m='2943150'>of</span> <span
  m='2943240'>them,</span> <span m='2943390'>but</span> <span
  m='2943540'>we're</span> <span m='2943690'>closer</span> <span
  m='2944110'>to</span> <span m='2944290'>another</span> <span
  m='2944620'>one.</span> <span m='2945530'>And</span> <span
  m='2945580'>in</span> <span m='2945670'>terms</span> <span
  m='2945970'>of</span> <span m='2946060'>the</span> <span
  m='2946180'>product</span> <span m='2946660'>of</span> <span
  m='2946750'>the</span> <span m='2946840'>length</span> <span
  m='2947110'>of</span> <span m='2947230'>the</span> <span
  m='2947360'>zero</span> <span m='2947800'>vectors,</span> <span
  m='2948850'>that</span> <span m='2949120'>will</span> <span
  m='2949270'>tend</span> <span m='2949570'>to</span> <span
  m='2949720'>stay</span> <span m='2949990'>smaller</span> <span
  m='2951100'>than</span> <span m='2951250'>the</span> <span
  m='2951340'>product</span> <span m='2951790'>of</span> <span
  m='2951880'>the</span> <span m='2952000'>lengths</span> <span
  m='2952270'>of</span> <span m='2952360'>the</span> <span
  m='2952450'>zero</span> <span m='2952780'>vectors</span> <span
  m='2953470'>at</span> <span m='2953620'>z</span> <span
  m='2954050'>equals</span> <span m='2954190'>1.</span> </p><p><span
  m='2956020'>Consequently,</span> <span m='2957100'>the</span> <span
  m='2957220'>frequency</span> <span m='2957700'>response</span> <span
  m='2958180'>starts</span> <span m='2958600'>at</span> <span
  m='2958690'>some</span> <span m='2958930'>value</span> <span
  m='2961030'>and</span> <span m='2962710'>of</span> <span
  m='2962770'>course,</span> <span m='2963070'>goes</span> <span
  m='2963280'>down</span> <span m='2963550'>to</span> <span m='2963670'>0</span>
  <span m='2964120'>at</span> <span m='2964210'>pi</span> <span
  m='2964510'>over</span> <span m='2964750'>4.</span> <span
  m='2966160'>That's</span> <span m='2966520'>because of</span> <span
  m='2967020'>this</span> <span m='2967280'>0.</span> <span
  m='2969870'>Then,</span> <span m='2970440'>it</span> <span
  m='2970560'>comes</span> <span m='2970830'>back</span> <span
  m='2971130'>up</span> <span m='2971310'>again,</span> <span
  m='2972610'>but</span> <span m='2972660'>not</span> <span
  m='2972870'>quite</span> <span m='2973170'>as</span> <span
  m='2973290'>far,</span> <span m='2974610'>and</span> <span
  m='2974800'>then</span> <span m='2974940'>goes</span> <span
  m='2975150'>back</span> <span m='2975390'>down</span> <span
  m='2975600'>to</span> <span m='2975690'>0 at</span> <span
  m='2976080'>pi</span> <span m='2976390'>over</span> <span
  m='2976620'>2.</span> <span m='2978780'>Then</span> <span
  m='2978960'>it</span> <span m='2979020'>goes</span> <span
  m='2979290'>up</span> <span m='2979470'>again</span> <span
  m='2980130'>and</span> <span m='2980850'>comes</span> <span
  m='2981120'>down</span> <span m='2981360'>again.</span> <span
  m='2982610'>It</span> <span m='2982830'>goes</span> <span
  m='2983100'>up</span> <span m='2983260'>not</span> <span
  m='2983460'>quite</span> <span m='2983730'>as</span> <span
  m='2983850'>far.</span> <span m='2984450'>And</span> <span
  m='2984510'>that's</span> <span m='2984750'>not</span> <span
  m='2985020'>particularly</span> <span m='2985620'>obvious</span> <span
  m='2985980'>geometrically.</span> <span m='2987720'>And</span> <span
  m='2988440'>then,</span> <span m='2989070'>the</span> <span
  m='2989160'>same</span> <span m='2989490'>thing</span> <span
  m='2989700'>again</span> <span m='2990270'>going</span> <span
  m='2990510'>to</span> <span m='2990600'>0</span> <span m='2991380'>at</span>
  <span m='2991530'>pi.</span> <span m='2992850'>And</span> <span
  m='2992970'>then</span> <span m='2993120'>of</span> <span
  m='2993240'>course</span> <span m='2993570'>as</span> <span
  m='2993720'>we</span> <span m='2993810'>come</span> <span
  m='2994020'>back</span> <span m='2994350'>around</span> <span
  m='2994620'>the</span> <span m='2994710'>unit</span> <span
  m='2994980'>circle,</span> <span m='2995370'>we</span> <span
  m='2995520'>see</span> <span m='2996210'>the</span> <span
  m='2996300'>same</span> <span m='2996630'>thing,</span> <span
  m='2997380'>the</span> <span m='2997470'>same</span> <span
  m='2997710'>type</span> <span m='2998010'>of</span> <span
  m='2998100'>behavior,</span> <span m='2998450'>repeated again.</span> <span
  m='3004220'>So</span> <span m='3004880'>roughly,</span> <span
  m='3006790'>we</span> <span m='3006970'>can</span> <span
  m='3007120'>get</span> <span m='3007330'>a</span> <span
  m='3007570'>geometric</span> <span m='3008170'>picture</span> <span
  m='3008740'>of</span> <span m='3008920'>the</span> <span
  m='3009010'>frequency</span> <span m='3009520'>response</span> <span
  m='3010630'>for</span> <span m='3011140'>a</span> <span
  m='3011260'>boxcar</span> <span m='3011890'>sequence</span> <span
  m='3013090'>by</span> <span m='3014320'>looking</span> <span
  m='3014950'>at</span> <span m='3015550'>the</span> <span
  m='3015760'>location</span> <span m='3016570'>of</span> <span
  m='3016990'>the</span> <span m='3017110'>poles</span> <span
  m='3017410'>and</span> <span m='3017500'>zeros</span> <span
  m='3017860'>in</span> <span m='3017950'>the</span> <span
  m='3018040'>z-plane</span> <span m='3019510'>and</span> <span
  m='3019630'>the</span> <span m='3019720'>behavior</span> <span
  m='3020350'>of</span> <span m='3020500'>the</span> <span
  m='3020620'>vectors</span> <span m='3021640'>as</span> <span
  m='3021940'>we</span> <span m='3022060'>travel</span> <span
  m='3022450'>around</span> <span m='3022720'>the</span> <span
  m='3022810'>unit</span> <span m='3023110'>circle.</span> </p><p><span
  m='3025230'>Well</span> <span m='3025810'>finally,</span> <span
  m='3026220'>let's</span> <span m='3026490'>just</span> <span
  m='3027270'>look</span> <span m='3027510'>at</span> <span
  m='3027600'>the</span> <span m='3029600'>Fourier</span> <span
  m='3029970'>transform</span> <span m='3031500'>of</span> <span
  m='3032250'>the</span> <span m='3032670'>boxcar</span> <span
  m='3033420'>somewhat</span> <span m='3033900'>more</span> <span
  m='3034110'>formally</span> <span m='3034650'>because</span> <span
  m='3035040'>in</span> <span m='3035160'>fact,</span> <span
  m='3035490'>it's</span> <span m='3035640'>an</span> <span
  m='3035700'>important</span> <span m='3036150'>sequence.</span> <span
  m='3037200'>And</span> <span m='3037620'>it's</span> <span
  m='3037740'>important</span> <span m='3038850'>to</span> <span
  m='3039720'>have</span> <span m='3040740'>a</span> <span
  m='3040950'>fairly</span> <span m='3042000'>complete</span> <span
  m='3042720'>precise</span> <span m='3043110'>statement</span> <span
  m='3043980'>of</span> <span m='3044100'>the</span> <span
  m='3044190'>Fourier</span> <span m='3044610'>transform</span> <span
  m='3045510'>and</span> <span m='3045860'>a</span> <span
  m='3045930'>complete</span> <span m='3046290'>picture</span> <span
  m='3046740'>of</span> <span m='3046830'>what</span> <span
  m='3046980'>it</span> <span m='3047070'>looks</span> <span
  m='3047310'>like.</span> <span m='3049360'>Well,</span> <span
  m='3049990'>let's</span> <span m='3050130'>see.</span> </p><p><span
  m='3051060'>We</span> <span m='3051270'>had</span> <span
  m='3052110'>the</span> <span m='3052470'>Z-transform</span> <span
  m='3053850'>as</span> <span m='3054210'>1</span> <span
  m='3054510'>minus</span> <span m='3055020'>z</span> <span
  m='3055120'>to</span> <span m='3055220'>the</span> <span
  m='3055320'>minus</span> <span m='3055450'>n</span> <span
  m='3055740'>over</span> <span m='3055980'>1</span> <span
  m='3056400'>minus</span> <span m='3056550'>z</span> <span
  m='3056700'>to</span> <span m='3056850'>the</span> <span
  m='3056970'>minus</span> <span m='3057360'>1.</span> <span
  m='3059192'>Substituting</span> <span m='3059650'>in</span> <span
  m='3059890'>z equals</span> <span m='3060280'>z</span> <span
  m='3060510'>to</span> <span m='3060660'>the</span> <span m='3060750'>j
  omega,</span> <span m='3061890'>then</span> <span m='3062370'>we</span> <span
  m='3062520'>have</span> <span m='3062730'>x of e</span> <span
  m='3063100'>to</span> <span m='3063180'>the</span> <span m='3063270'>j
  omega</span> <span m='3064170'>as</span> <span m='3065490'>this.</span> <span
  m='3067600'>We</span> <span m='3067750'>can</span> <span
  m='3067900'>factor</span> <span m='3068410'>out</span> <span
  m='3068920'>a</span> <span m='3069010'>factor</span> <span
  m='3069590'>e</span> <span m='3069790'>to</span> <span m='3069850'>the</span>
  <span m='3069970'>minus</span> <span m='3070360'>j omega</span> <span
  m='3071050'>capital</span> <span m='3071560'>N</span> <span
  m='3071680'>over</span> <span m='3071940'>2,</span> <span
  m='3074450'>leaving</span> <span m='3074930'>e</span> <span
  m='3075090'>to</span> <span m='3075200'>the</span> <span m='3075290'>j
  omega</span> <span m='3075890'>capital</span> <span m='3076310'>N</span> <span
  m='3076400'>over</span> <span m='3076610'>2</span> <span
  m='3076880'>minus</span> <span m='3077220'>e</span> <span
  m='3077390'>to</span> <span m='3077510'>the</span> <span
  m='3077600'>minus</span> <span m='3077990'>j omega</span> <span
  m='3078650'>capital</span> <span m='3079160'>N</span> <span
  m='3079280'>over</span> <span m='3079520'>2,</span> <span
  m='3080870'>and</span> <span m='3081020'>a</span> <span
  m='3081080'>denominator</span> <span m='3082010'>factor</span> <span
  m='3082430'>e</span> <span m='3082630'>to</span> <span m='3082700'>the</span>
  <span m='3082790'>minus</span> <span m='3083150'>j omega</span> <span
  m='3083810'>over</span> <span m='3084140'>2</span> <span
  m='3085310'>times</span> <span m='3085790'>e</span> <span
  m='3086060'>to</span> <span m='3086120'>the</span> <span m='3086210'>j
  omega--</span> <span m='3086840'>over</span> <span m='3087080'>2</span> <span
  m='3087350'>minus</span> <span m='3087800'>e</span> <span
  m='3087960'>to</span> <span m='3088030'>the</span> <span
  m='3088130'>minus</span> <span m='3088490'>j omega</span> <span
  m='3089270'>over</span> <span m='3089600'>2.</span> </p><p><span
  m='3091490'>This</span> <span m='3091730'>piece</span> <span
  m='3092540'>we</span> <span m='3092720'>recognize</span> <span
  m='3093680'>as</span> <span m='3094520'>2j</span> <span
  m='3096290'>sine</span> <span m='3097220'>omega</span> <span
  m='3097700'>capital</span> <span m='3098270'>N</span> <span
  m='3098690'>over</span> <span m='3099000'>to</span> <span
  m='3099380'>2.</span> <span m='3100890'>And</span> <span
  m='3101460'>this</span> <span m='3101730'>piece</span> <span
  m='3102780'>we</span> <span m='3102930'>recognize</span> <span
  m='3103920'>as</span> <span m='3104190'>2-j</span> <span
  m='3105630'>times</span> <span m='3106000'>sine</span> <span
  m='3107550'>omega</span> <span m='3108090'>over</span> <span
  m='3108420'>2.</span> <span m='3110430'>And</span> <span
  m='3110550'>consequently,</span> <span m='3111870'>putting</span> <span
  m='3112200'>these</span> <span m='3112410'>two</span> <span
  m='3112590'>terms</span> <span m='3112980'>together</span> <span
  m='3113910'>and</span> <span m='3114060'>inserting</span> <span
  m='3115310'>this</span> <span m='3115530'>substitution,</span> <span
  m='3116760'>the</span> <span m='3117190'>Fourier</span> <span
  m='3117660'>transform</span> <span m='3118440'>is</span> <span
  m='3118560'>e</span> <span m='3118750'>to</span> <span m='3118830'>the</span>
  <span m='3118950'>minus</span> <span m='3119280'>j omega</span> <span
  m='3120510'>capital</span> <span m='3120930'>N</span> <span
  m='3121050'>minus</span> <span m='3121380'>1</span> <span
  m='3121590'>over</span> <span m='3121800'>2--</span> <span
  m='3123210'>that's</span> <span m='3123420'>a</span> <span
  m='3123480'>linear</span> <span m='3123840'>phase</span> <span
  m='3124200'>term,</span> <span m='3124450'>by</span> <span
  m='3124650'>the</span> <span m='3124770'>way--</span> <span
  m='3126780'>times</span> <span m='3128250'>sine</span> <span
  m='3128730'>omega</span> <span m='3129190'>capital</span> <span
  m='3129690'>N</span> <span m='3129810'>over</span> <span m='3130020'>2</span>
  <span m='3130680'>divided</span> <span m='3131160'>by</span> <span
  m='3131400'>sine</span> <span m='3131910'>omega</span> <span
  m='3132360'>over</span> <span m='3132630'>2.</span> </p><p><span
  m='3133980'>And</span> <span m='3135270'>this</span> <span
  m='3135750'>function,</span> <span m='3137160'>sine</span> <span
  m='3137550'>omega</span> <span m='3137910'>capital</span> <span
  m='3138390'>N</span> <span m='3138510'>over</span> <span m='3138750'>2</span>
  <span m='3139170'>divided</span> <span m='3139680'>by</span> <span
  m='3139860'>sine</span> <span m='3140340'>omega</span> <span
  m='3140790'>over</span> <span m='3141090'>2,</span> <span
  m='3142290'>is</span> <span m='3142920'>the</span> <span
  m='3143040'>discrete</span> <span m='3143600'>time</span> <span
  m='3144030'>counterpart</span> <span m='3146030'>of</span> <span
  m='3146600'>what</span> <span m='3147200'>we</span> <span
  m='3147380'>usually</span> <span m='3147830'>find</span> <span
  m='3148310'>in</span> <span m='3148400'>the</span> <span
  m='3148490'>continuous</span> <span m='3149060'>time</span> <span
  m='3149390'>case</span> <span m='3150200'>as</span> <span
  m='3150380'>sine</span> <span m='3151490'>x</span> <span
  m='3151970'>over</span> <span m='3152300'>x.</span> <span
  m='3153320'>That</span> <span m='3153470'>is,</span> <span
  m='3153620'>this</span> <span m='3153800'>is</span> <span m='3153950'>a</span>
  <span m='3154010'>sine</span> <span m='3154325'>nx</span> <span
  m='3155030'>over</span> <span m='3155300'>sine</span> <span
  m='3155720'>x</span> <span m='3156260'>kind</span> <span m='3156500'>of</span>
  <span m='3156590'>function.</span> <span m='3157910'>And</span> <span
  m='3158010'>it</span> <span m='3158110'>plays</span> <span
  m='3158390'>exactly</span> <span m='3158930'>the</span> <span
  m='3159020'>same</span> <span m='3159320'>role</span> <span
  m='3159710'>in</span> <span m='3159800'>the</span> <span
  m='3159890'>discrete</span> <span m='3160310'>time</span> <span
  m='3160640'>case</span> <span m='3161690'>that</span> <span
  m='3161840'>the</span> <span m='3161930'>sine</span> <span
  m='3162380'>x</span> <span m='3162710'>over</span> <span m='3163040'>x</span>
  <span m='3163280'>function</span> <span m='3164030'>plays</span> <span
  m='3164630'>in</span> <span m='3164780'>the</span> <span
  m='3164870'>continuous</span> <span m='3165470'>time</span> <span
  m='3165800'>case.</span> </p><p><span m='3167610'>And</span> <span
  m='3167630'>that's</span> <span m='3167900'>not</span> <span
  m='3168170'>unreasonable,</span> <span m='3168920'>actually,</span> <span
  m='3169880'>because</span> <span m='3170390'>this</span> <span
  m='3171080'>arose</span> <span m='3173400'>by</span> <span
  m='3173730'>looking</span> <span m='3174150'>at</span> <span
  m='3174240'>the</span> <span m='3174330'>Fourier</span> <span
  m='3174810'>transform</span> <span m='3175770'>of</span> <span
  m='3175950'>a</span> <span m='3176010'>rectangular</span> <span
  m='3176730'>sequence,</span> <span m='3178530'>whereas</span> <span
  m='3179880'>the</span> <span m='3180030'>sine</span> <span
  m='3180420'>x</span> <span m='3180600'>over</span> <span m='3180870'>x</span>
  <span m='3181080'>function</span> <span m='3181830'>arises</span> <span
  m='3182940'>by</span> <span m='3183090'>looking</span> <span
  m='3183450'>at</span> <span m='3183510'>the</span> <span
  m='3183650'>Fourier</span> <span m='3184030'>transform</span> <span
  m='3184860'>of</span> <span m='3185010'>a</span> <span
  m='3185070'>continuous</span> <span m='3185700'>time</span> <span
  m='3185970'>rectangle.</span> <span m='3188020'>So</span> <span
  m='3188490'>the</span> <span m='3188610'>sine</span> <span
  m='3189990'>nx</span> <span m='3190260'>over</span> <span
  m='3190470'>sine</span> <span m='3190830'>x</span> <span
  m='3191160'>function,</span> <span m='3192550'>which</span> <span
  m='3192990'>is</span> <span m='3193680'>what</span> <span
  m='3193950'>we</span> <span m='3194130'>have</span> <span
  m='3194370'>here,</span> <span m='3195630'>is</span> <span
  m='3195780'>an</span> <span m='3195870'>extremely</span> <span
  m='3196410'>important</span> <span m='3197280'>function--</span> <span
  m='3197790'>as</span> <span m='3198030'>important</span> <span
  m='3198660'>as</span> <span m='3198810'>sine</span> <span m='3199170'>x</span>
  <span m='3199410'>over</span> <span m='3199680'>x</span> <span
  m='3200460'>in</span> <span m='3200550'>the</span> <span
  m='3200640'>continuous</span> <span m='3201210'>time</span> <span
  m='3201540'>case.</span> <span m='3202780'>And</span> <span
  m='3202950'>consequently,</span> <span m='3203970'>let</span> <span
  m='3204180'>me</span> <span m='3204360'>just</span> <span
  m='3205110'>show</span> <span m='3205440'>you</span> <span
  m='3205590'>this</span> <span m='3205800'>function</span> <span
  m='3206610'>plotted</span> <span m='3207060'>out</span> <span
  m='3207720'>a</span> <span m='3207780'>little</span> <span
  m='3207990'>more</span> <span m='3208200'>precisely</span> <span
  m='3209160'>than</span> <span m='3209520'>I</span> <span
  m='3209610'>would</span> <span m='3209820'>be</span> <span
  m='3210000'>able</span> <span m='3210270'>to</span> <span
  m='3210390'>do</span> <span m='3210570'>at</span> <span m='3210660'>the</span>
  <span m='3210780'>board.</span> <span m='3211170'>In</span> <span
  m='3211560'>particular,</span> <span m='3212010'>let</span> <span
  m='3212190'>me</span> <span m='3213090'>show</span> <span
  m='3213360'>you</span> <span m='3213570'>a</span> <span
  m='3213680'>viewgraph</span> <span m='3216860'>which</span> <span
  m='3217340'>illustrates</span> <span m='3220220'>the</span> <span
  m='3220340'>function</span> <span m='3221360'>sine</span> <span
  m='3221780'>omega</span> <span m='3222230'>capital</span> <span
  m='3222500'>N</span> <span m='3222890'>over</span> <span m='3223130'>2</span>
  <span m='3224030'>divided</span> <span m='3224480'>by</span> <span
  m='3224660'>sine</span> <span m='3225050'>omega</span> <span
  m='3225470'>over</span> <span m='3225800'>2.</span> <span
  m='3227150'>And</span> <span m='3227270'>I've</span> <span
  m='3227390'>sketched</span> <span m='3227840'>this</span> <span
  m='3228140'>now</span> <span m='3229400'>over</span> <span
  m='3229730'>more</span> <span m='3230030'>than</span> <span
  m='3230210'>just</span> <span m='3230660'>a</span> <span m='3230870'>0</span>
  <span m='3231530'>to</span> <span m='3231620'>2</span> <span
  m='3231860'>pi</span> <span m='3232160'>interval</span> <span
  m='3233180'>to,</span> <span m='3233330'>again,</span> <span
  m='3233870'>stress</span> <span m='3234620'>the</span> <span
  m='3234740'>fact</span> <span m='3235580'>that</span> <span
  m='3236090'>this</span> <span m='3236300'>is</span> <span
  m='3236420'>periodic--</span> <span m='3238040'>as</span> <span
  m='3238220'>all</span> <span m='3238430'>Fourier</span> <span
  m='3238820'>transforms</span> <span m='3239540'>are--</span> <span
  m='3240320'>periodic</span> <span m='3241190'>with</span> <span
  m='3241370'>a</span> <span m='3241430'>period</span> <span
  m='3242150'>of</span> <span m='3242300'>2</span> <span m='3242510'>pi.</span>
  </p><p><span m='3244460'>The</span> <span m='3244580'>important</span> <span
  m='3245090'>characteristics</span> <span m='3246020'>of</span> <span
  m='3246200'>it--</span> <span m='3246770'>some</span> <span
  m='3247070'>important</span> <span m='3247490'>characteristics.</span> <span
  m='3248190'>There are</span> <span m='3248270'>a</span> <span
  m='3248330'>lot.</span> <span m='3248810'>But</span> <span
  m='3248960'>some</span> <span m='3249200'>important</span> <span
  m='3249620'>characteristics</span> <span m='3250490'>of</span> <span
  m='3250670'>it</span> <span m='3251600'>are</span> <span
  m='3251900'>that</span> <span m='3252860'>it</span> <span
  m='3252980'>has</span> <span m='3253760'>an</span> <span
  m='3253910'>envelope.</span> <span m='3255270'>It's</span> <span
  m='3255320'>basically</span> <span m='3255860'>a</span> <span
  m='3255920'>sinusoidal</span> <span m='3257390'>function</span> <span
  m='3258620'>with</span> <span m='3258800'>an</span> <span
  m='3258890'>envelope</span> <span m='3259790'>that</span> <span
  m='3260030'>is</span> <span m='3260810'>the</span> <span
  m='3260900'>reciprocal</span> <span m='3261770'>of</span> <span
  m='3261920'>a</span> <span m='3261980'>sinusoid.</span> <span
  m='3264920'>The</span> <span m='3265040'>period</span> <span
  m='3265910'>of</span> <span m='3266030'>this</span> <span
  m='3266240'>sinusoid</span> <span m='3267620'>is</span> <span
  m='3268520'>from</span> <span m='3269150'>0</span> <span m='3270320'>to</span>
  <span m='3271070'>2pi,</span> <span m='3272330'>whereas</span> <span
  m='3272630'>this</span> <span m='3272870'>one</span> <span
  m='3273140'>wiggles</span> <span m='3273500'>faster,</span> <span
  m='3274310'>depending</span> <span m='3274790'>on</span> <span
  m='3274910'>the</span> <span m='3275000'>value</span> <span
  m='3275390'>of</span> <span m='3275480'>capital</span> <span
  m='3275990'>N.</span> <span m='3277430'>I've</span> <span
  m='3277550'>sketched</span> <span m='3277910'>it</span> <span
  m='3278030'>here</span> <span m='3278180'>for</span> <span
  m='3278390'>n</span> <span m='3278600'>equals</span> <span
  m='3278840'>15.</span> </p><p><span m='3280370'>But</span> <span
  m='3281600'>in</span> <span m='3281780'>fact,</span> <span
  m='3282240'>it</span> <span m='3282340'>has</span> <span m='3282620'>a</span>
  <span m='3282680'>lot</span> <span m='3282920'>of</span> <span
  m='3283010'>the</span> <span m='3283130'>character</span> <span
  m='3284120'>of</span> <span m='3285110'>a</span> <span m='3286730'>sine</span>
  <span m='3287120'>x</span> <span m='3287360'>over</span> <span m='3287840'>x
  function.</span> <span m='3288950'>That</span> <span m='3289160'>is,</span>
  <span m='3290240'>it</span> <span m='3290360'>has</span> <span
  m='3290960'>a</span> <span m='3291020'>big</span> <span
  m='3291290'>central</span> <span m='3291710'>lobe,</span> <span
  m='3292880'>decays</span> <span m='3293090'>down</span> <span
  m='3293540'>and</span> <span m='3293630'>wiggles</span> <span
  m='3294140'>and</span> <span m='3294260'>gets</span> <span
  m='3294410'>smaller</span> <span m='3295100'>as</span> <span
  m='3295280'>it's</span> <span m='3295430'>decaying.</span> <span
  m='3296330'>But</span> <span m='3296480'>then,</span> <span
  m='3296690'>of</span> <span m='3296780'>course,</span> <span
  m='3297080'>the</span> <span m='3297200'>fact</span> <span
  m='3297470'>that</span> <span m='3297560'>it</span> <span
  m='3297650'>has</span> <span m='3297830'>to</span> <span m='3297950'>be</span>
  <span m='3298070'>periodic</span> <span m='3299180'>is</span> <span
  m='3299330'>what</span> <span m='3299540'>distinguishes</span> <span
  m='3300440'>it</span> <span m='3301010'>in</span> <span m='3301130'>the</span>
  <span m='3301250'>discrete</span> <span m='3301670'>time</span> <span
  m='3301970'>case</span> <span m='3302780'>from</span> <span
  m='3303470'>the</span> <span m='3303560'>sine</span> <span
  m='3303890'>x</span> <span m='3304100'>over</span> <span m='3304240'>x</span>
  <span m='3304520'>function</span> <span m='3305180'>in</span> <span
  m='3305300'>the</span> <span m='3305390'>continuous</span> <span
  m='3305960'>time</span> <span m='3306230'>case.</span> </p><p><span
  m='3313470'>OK.</span> <span m='3313880'>Well,</span> <span
  m='3314930'>this</span> <span m='3315650'>concludes</span> <span
  m='3316490'>our</span> <span m='3316880'>discussion</span> <span
  m='3317750'>of</span> <span m='3318530'>the Z-transform.</span> <span
  m='3320450'>We've</span> <span m='3320630'>now</span> <span
  m='3320810'>talked</span> <span m='3321170'>about</span> <span
  m='3321940'>two</span> <span m='3322490'>transforms.</span> <span
  m='3323150'>We've</span> <span m='3323240'>talked</span> <span
  m='3323540'>about</span> <span m='3323720'>the</span> <span
  m='3323840'>Fourier</span> <span m='3324170'>transform</span> <span
  m='3324760'>and</span> <span m='3324830'>the</span> <span
  m='3324920'>Z-transform</span> <span m='3326270'>spread</span> <span
  m='3326660'>out</span> <span m='3326870'>over</span> <span
  m='3328430'>about</span> <span m='3328640'>five</span> <span
  m='3328970'>lectures.</span> <span m='3330710'>And</span> <span
  m='3331700'>in</span> <span m='3331820'>the</span> <span
  m='3331910'>next</span> <span m='3332180'>lecture,</span> <span
  m='3332600'>the</span> <span m='3332690'>next</span> <span
  m='3333320'>set</span> <span m='3333590'>of</span> <span
  m='3333980'>two</span> <span m='3334160'>or</span> <span
  m='3334250'>three</span> <span m='3334490'>lectures,</span> <span
  m='3335480'>we'll</span> <span m='3335600'>be</span> <span
  m='3335720'>talking</span> <span m='3336140'>about</span> <span
  m='3336800'>yet</span> <span m='3337010'>another</span> <span
  m='3337340'>transform,</span> <span m='3339240'>which</span> <span
  m='3339740'>is</span> <span m='3339920'>a</span> <span
  m='3339980'>transform</span> <span m='3340490'>that's</span> <span
  m='3340700'>really</span> <span m='3341300'>somewhat</span> <span
  m='3341750'>special</span> <span m='3342980'>and</span> <span
  m='3343490'>linked</span> <span m='3344060'>very</span> <span
  m='3344300'>closely</span> <span m='3344990'>to</span> <span
  m='3345140'>the</span> <span m='3345260'>notion</span> <span
  m='3345830'>of</span> <span m='3346550'>discrete</span> <span
  m='3347000'>time</span> <span m='3347570'>signals</span> <span
  m='3348200'>and</span> <span m='3348290'>discrete</span> <span
  m='3348650'>time</span> <span m='3348890'>signal</span> <span
  m='3349250'>processing.</span> <span m='3350420'>That</span> <span
  m='3350600'>transform</span> <span m='3351350'>is</span> <span
  m='3351540'>the</span> <span m='3351660'>Discrete</span> <span
  m='3352190'>Fourier</span> <span m='3352530'>transform.</span> <span
  m='3354260'>And</span> <span m='3355790'>besides</span> <span
  m='3356510'>being</span> <span m='3356960'>a</span> <span
  m='3357050'>mathematical</span> <span m='3357890'>tool,</span> <span
  m='3358520'>as</span> <span m='3358640'>the</span> <span
  m='3358760'>Fourier</span> <span m='3359180'>transform</span> <span
  m='3359810'>and</span> <span m='3359870'>the</span> <span
  m='3359960'>Z-transform</span> <span m='3360800'>have</span> <span
  m='3360940'>been,</span> <span m='3362230'>Discrete</span> <span
  m='3362750'>Fourier</span> <span m='3363170'>transform</span> <span
  m='3364070'>has</span> <span m='3364640'>some</span> <span
  m='3364850'>important</span> <span m='3365930'>computational</span> <span
  m='3367970'>realizations</span> <span m='3369020'>and</span> <span
  m='3369140'>computational</span> <span m='3370520'>implications</span> <span
  m='3371930'>that</span> <span m='3372440'>will</span> <span
  m='3372650'>be</span> <span m='3373010'>one</span> <span m='3373310'>of</span>
  <span m='3373430'>the</span> <span m='3373520'>important</span> <span
  m='3374030'>things</span> <span m='3374870'>that</span> <span
  m='3374990'>will</span> <span m='3375090'>want</span> <span
  m='3375290'>to</span> <span m='3375350'>capitalize</span> <span
  m='3376160'>on</span> <span m='3376850'>in</span> <span
  m='3376970'>applying</span> <span m='3377450'>digital</span> <span
  m='3377780'>signal</span> <span m='3378110'>processing</span> <span
  m='3379040'>to</span> <span m='3379160'>real</span> <span
  m='3379400'>problems.</span> <span m='3380650'>Thank</span> <span
  m='3380740'>you.</span> </p><p><span m='3382540'>[MUSIC PLAYING]</span>
  </p><p></p>
embedded_media:
  - uid: f210dca6daf177fd71b4dcd2dba8b7a6
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: MITRES_6_008S11_lec07.pdf
    title: MITRES_6_008S11_lec07.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-7-z-transform-properties/MITRES_6_008S11_lec07.pdf
  - uid: 695a28516f5cd2a2d2871c8b1ff7820c
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: LrNXtw0E7Dk
  - uid: bf89b83a4f5a05a1ebd9cd0eaa3b1420
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-7-z-transform-properties/id481803782?i=108361993
  - uid: 99da280a3a8237122b4d1566f7cc3c51
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec07_300k.mp4'
  - uid: d588658bef6aeab7fca39b6525f5f178
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/LrNXtw0E7Dk/default.jpg'
  - uid: 5c05dc5b31d05308a0b13900d97fcd4f
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: LrNXtw0E7Dk
  - uid: 541cb552e4969d501e291a1625229527
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: LrNXtw0E7Dk.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-7-z-transform-properties/LrNXtw0E7Dk.srt
  - uid: ab98db61605303ad70feff000eb34662
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: LrNXtw0E7Dk.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-7-z-transform-properties/LrNXtw0E7Dk.pdf
  - uid: c9c79b9e8b7ebb6538d2083a7268c559
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: acd826783d4b630e32e71c661e36de19
    parent_uid: e942e4e281ec1133760bc5a48de2d8eb
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
