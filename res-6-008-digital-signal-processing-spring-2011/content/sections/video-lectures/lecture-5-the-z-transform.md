---
order_index: null
title: 'Lecture 5: The z-Transform'
template_type: Tabbed
uid: e0411f9dab21ab2d69898c1ab5fab0c2
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-5-the-z-transform
short_url: lecture-5-the-z-transform
inline_embed_id: '33699898lecture5:thez-transform94109200'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Generalization of Fourier transform to
  z-transform, relationship of Fourier transform to z-transform, region of
  convergence of z transforms, characteristics of region of convergence in
  relation to poles, zeros, stability, and causality.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>The z-Transform (<a
  href="./resolveuid/c7f87d4cb052de4f4881ee8c3c90b8e8">PDF</a>)</p>
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
  m='17430'>ocw.mit.edu.</span> </p><p><span m='22940'>[MUSIC PLAYING]</span>
  </p><p></p><p><span m='50180'>ALAN OPPENHEIM:</span> <span
  m='50360'>Hi.</span> <span m='51300'>As</span> <span m='51480'>you</span>
  <span m='51570'>recall,</span> <span m='52180'>last</span> <span
  m='52410'>time</span> <span m='53070'>we</span> <span
  m='53220'>developed</span> <span m='54510'>the</span> <span
  m='54780'>discrete-time</span> <span m='55620'>Fourier</span> <span
  m='56060'>transform.</span> <span m='57810'>And</span> <span
  m='58800'>one</span> <span m='59100'>of</span> <span m='59310'>the</span>
  <span m='60120'>issues</span> <span m='60540'>that</span> <span
  m='60690'>I</span> <span m='60810'>alluded</span> <span m='61230'>to,</span>
  <span m='61830'>although</span> <span m='62190'>I</span> <span
  m='62250'>didn't</span> <span m='62610'>say</span> <span m='62910'>it</span>
  <span m='62970'>explicitly,</span> <span m='64379'>is</span> <span
  m='64620'>that</span> <span m='65310'>the</span> <span
  m='65519'>Fourier</span> <span m='65910'>transform</span> <span
  m='66960'>doesn't</span> <span m='67680'>exist</span> <span
  m='68130'>for</span> <span m='68310'>all</span> <span
  m='68490'>sequences.</span> <span m='69720'>In</span> <span
  m='69810'>fact,</span> <span m='70630'>as</span> <span m='70890'>we'll</span>
  <span m='71010'>see</span> <span m='71220'>today,</span> <span
  m='71850'>one</span> <span m='72060'>of</span> <span m='72150'>the</span>
  <span m='72240'>difficulties</span> <span m='73710'>is</span> <span
  m='74400'>the</span> <span m='74580'>issue</span> <span m='75060'>of</span>
  <span m='75210'>convergence.</span> <span m='75930'>That</span> <span
  m='76110'>is,</span> <span m='76260'>the</span> <span m='76350'>Fourier</span>
  <span m='76750'>transform</span> <span m='78030'>doesn't</span> <span
  m='78300'>converge</span> <span m='79080'>for</span> <span
  m='79290'>all</span> <span m='79440'>sequences.</span> <span
  m='80910'>And</span> <span m='81030'>to</span> <span m='81150'>get</span>
  <span m='81300'>around</span> <span m='81690'>this,</span> <span
  m='82350'>we'll</span> <span m='83070'>generalize</span> <span
  m='84360'>the</span> <span m='84720'>notion</span> <span m='85200'>of</span>
  <span m='85290'>the</span> <span m='85380'>Fourier</span> <span
  m='85770'>transform</span> <span m='86520'>as</span> <span m='86640'>we</span>
  <span m='86760'>introduced</span> <span m='87300'>it</span> <span
  m='87390'>last</span> <span m='87750'>time</span> <span m='89010'>to</span>
  <span m='89610'>what's</span> <span m='89850'>called</span> <span
  m='90120'>the</span> <span m='90240'>Z-transform,</span> <span
  m='92080'>the</span> <span m='92220'>Z-transform</span> <span
  m='93750'>being</span> <span m='94140'>the</span> <span
  m='94410'>discrete</span> <span m='94860'>time</span> <span
  m='95160'>counterpart</span> <span m='96390'>of</span> <span
  m='96570'>the</span> <span m='96690'>Laplace</span> <span
  m='97170'>transform</span> <span m='98220'>for</span> <span
  m='98670'>continuous</span> <span m='99270'>time</span> <span
  m='99570'>systems.</span> </p><p><span m='101050'>Well,</span> <span
  m='102000'>let</span> <span m='102180'>me</span> <span m='102300'>begin</span>
  <span m='102810'>by</span> <span m='103410'>examining</span> <span
  m='105360'>just</span> <span m='105660'>a</span> <span
  m='105690'>little</span> <span m='106320'>this</span> <span
  m='106530'>issue</span> <span m='107160'>of</span> <span
  m='107580'>convergence.</span> <span m='110550'>We</span> <span
  m='110670'>have</span> <span m='111180'>here</span> <span
  m='111630'>the</span> <span m='112170'>Fourier</span> <span
  m='112600'>transform</span> <span m='113280'>relationship</span> <span
  m='114240'>as</span> <span m='114720'>we</span> <span
  m='114900'>developed</span> <span m='115350'>it</span> <span
  m='115440'>last</span> <span m='115800'>time,</span> <span m='117070'>x</span>
  <span m='117630'>of e</span> <span m='117730'>to the</span> <span
  m='117840'>j</span> <span m='118170'>omega</span> <span
  m='119100'>given</span> <span m='119430'>by</span> <span m='119820'>the</span>
  <span m='119950'>sum</span> <span m='120540'>of</span> <span
  m='120920'>x</span> <span m='121150'>of</span> <span m='121350'>10</span>
  <span m='122160'>times</span> <span m='122640'>e</span> <span
  m='122850'>to</span> <span m='122910'>the</span> <span m='123030'>minus</span>
  <span m='123360'>j</span> <span m='123790'>omega</span> <span
  m='124290'>n.</span> <span m='124890'>And</span> <span m='125040'>as</span>
  <span m='125160'>we</span> <span m='125280'>discussed</span> <span
  m='125790'>the</span> <span m='125890'>Fourier</span> <span
  m='126270'>transform</span> <span m='126900'>last</span> <span
  m='127230'>time,</span> <span m='128190'>we</span> <span
  m='128610'>assumed</span> <span m='129180'>that</span> <span
  m='129840'>the</span> <span m='130500'>sum</span> <span m='131160'>was</span>
  <span m='132210'>convergent,</span> <span m='133800'>and--</span> <span
  m='134280'>or</span> <span m='134490'>at</span> <span m='134550'>least</span>
  <span m='134790'>we</span> <span m='134910'>didn't</span> <span
  m='135090'>particularly</span> <span m='135690'>raise</span> <span
  m='136020'>the</span> <span m='136140'>issue</span> <span m='136530'>as</span>
  <span m='136680'>to</span> <span m='136800'>whether</span> <span
  m='137100'>it</span> <span m='137220'>is</span> <span m='137380'>or</span>
  <span m='137540'>isn't.</span> </p><p><span m='138840'>Well,</span> <span
  m='140340'>we</span> <span m='140430'>can</span> <span m='140610'>look</span>
  <span m='140970'>at</span> <span m='141570'>the</span> <span
  m='141690'>magnitude</span> <span m='142890'>of</span> <span
  m='143070'>x,</span> <span m='144210'>or</span> <span
  m='144810'>equivalently</span> <span m='145800'>the</span> <span
  m='145890'>magnitude</span> <span m='146550'>of</span> <span
  m='146670'>this</span> <span m='146830'>sum,</span> <span
  m='147960'>and</span> <span m='148140'>ask</span> <span
  m='149310'>under</span> <span m='149580'>what</span> <span
  m='149850'>conditions</span> <span m='151320'>this</span> <span
  m='151590'>sum</span> <span m='152370'>will</span> <span
  m='152910'>converge.</span> <span m='153840'>That</span> <span
  m='154110'>is,</span> <span m='154860'>under</span> <span
  m='155100'>what</span> <span m='155280'>conditions</span> <span
  m='156000'>will</span> <span m='156150'>this</span> <span
  m='156470'>sum</span> <span m='156840'>be</span> <span
  m='157050'>finite.</span> </p><p><span m='159240'>Well,</span> <span
  m='159960'>here</span> <span m='160200'>we</span> <span m='160380'>have</span>
  <span m='160920'>the</span> <span m='161250'>magnitude</span> <span
  m='162270'>of</span> <span m='162420'>a</span> <span m='162480'>sum</span>
  <span m='162840'>of</span> <span m='162960'>things</span> <span
  m='164220'>from</span> <span m='165000'>what's</span> <span
  m='165300'>called</span> <span m='166050'>the</span> <span
  m='166140'>triangle</span> <span m='166650'>inequality,</span> <span
  m='167580'>or</span> <span m='168720'>you</span> <span m='168930'>can</span>
  <span m='169080'>just</span> <span m='169320'>kind of</span> <span
  m='169725'>imagine</span> <span m='170130'>that</span> <span
  m='170250'>this</span> <span m='170430'>is</span> <span m='170550'>true</span>
  <span m='171130'>from</span> <span m='171330'>common</span> <span
  m='171720'>sense,</span> <span m='172800'>is</span> <span
  m='173040'>that</span> <span m='173490'>the</span> <span
  m='173610'>magnitude</span> <span m='174240'>of</span> <span
  m='174340'>a</span> <span m='174390'>sum</span> <span m='175740'>has</span>
  <span m='176040'>to</span> <span m='176160'>be</span> <span
  m='176310'>less</span> <span m='176670'>than</span> <span m='176850'>or</span>
  <span m='176970'>equal</span> <span m='177390'>to</span> <span
  m='178230'>the</span> <span m='178320'>sum</span> <span m='178890'>of</span>
  <span m='179040'>the</span> <span m='179130'>magnitudes.</span> <span
  m='180600'>So</span> <span m='181440'>the</span> <span
  m='181560'>magnitude</span> <span m='182190'>of</span> <span
  m='182310'>this</span> <span m='182490'>sum</span> <span m='183870'>has</span>
  <span m='184170'>to</span> <span m='184290'>be</span> <span
  m='184410'>less</span> <span m='184770'>than</span> <span m='184920'>or</span>
  <span m='185070'>equal</span> <span m='185460'>to</span> <span
  m='186600'>the</span> <span m='186690'>sum</span> <span m='187410'>of</span>
  <span m='188100'>the</span> <span m='188190'>magnitude</span> <span
  m='189180'>of</span> <span m='189360'>x</span> <span m='189660'>of</span>
  <span m='189780'>n</span> <span m='190080'>e</span> <span m='190320'>to</span>
  <span m='190470'>the</span> <span m='190560'>minus</span> <span
  m='190950'>j</span> <span m='191310'>omega</span> <span m='191670'>n.</span>
  </p><p><span m='192720'>The</span> <span m='192840'>magnitude</span> <span
  m='193440'>of</span> <span m='193530'>a</span> <span m='193590'>product</span>
  <span m='194640'>is</span> <span m='194760'>the</span> <span
  m='194880'>product</span> <span m='195270'>of</span> <span
  m='195330'>the</span> <span m='195420'>magnitudes,</span> <span
  m='196110'>of</span> <span m='196230'>course.</span> <span
  m='197190'>So</span> <span m='198120'>this</span> <span m='198300'>says</span>
  <span m='199050'>that</span> <span m='199620'>the</span> <span
  m='199740'>magnitude</span> <span m='200370'>of</span> <span
  m='200430'>the</span> <span m='200550'>Fourier</span> <span
  m='201000'>transform</span> <span m='202650'>has</span> <span
  m='202950'>to</span> <span m='203100'>be</span> <span m='203220'>less</span>
  <span m='203520'>than</span> <span m='203670'>or</span> <span
  m='203760'>equal</span> <span m='204120'>to</span> <span m='205110'>the</span>
  <span m='205230'>sum</span> <span m='205890'>of</span> <span
  m='206040'>the</span> <span m='206160'>magnitude</span> <span
  m='206760'>of</span> <span m='206880'>x</span> <span m='207060'>of n</span>
  <span m='207990'>times</span> <span m='208530'>the</span> <span
  m='208650'>magnitude</span> <span m='209430'>of</span> <span
  m='210000'>the</span> <span m='210120'>complex</span> <span
  m='210690'>exponential,</span> <span m='211180'>e</span> <span
  m='211670'>to</span> <span m='211890'>the</span> <span m='211980'>minus</span>
  <span m='212340'>j</span> <span m='212660'>omega</span> <span
  m='212980'>n.</span> </p><p><span m='214450'>Well,</span> <span
  m='215080'>this</span> <span m='215320'>of</span> <span
  m='215440'>course</span> <span m='216280'>we</span> <span
  m='216610'>can't</span> <span m='216970'>say</span> <span m='217180'>a</span>
  <span m='217240'>lot</span> <span m='217480'>about.</span> <span
  m='218530'>This</span> <span m='219340'>we</span> <span m='219550'>can</span>
  <span m='219730'>recognize</span> <span m='220750'>as</span> <span
  m='222160'>unity.</span> <span m='224170'>It's</span> <span
  m='224350'>a</span> <span m='224410'>complex</span> <span
  m='224950'>exponential.</span> <span m='225670'>The</span> <span
  m='225760'>magnitude</span> <span m='226360'>of</span> <span
  m='226450'>a</span> <span m='226510'>complex</span> <span
  m='227080'>exponential</span> <span m='227800'>is</span> <span
  m='227950'>one.</span> <span m='229600'>So</span> <span
  m='230140'>consequently,</span> <span m='231880'>the</span> <span
  m='231970'>magnitude</span> <span m='232600'>of</span> <span
  m='232690'>the</span> <span m='232780'>Fourier</span> <span
  m='233230'>transform</span> <span m='234550'>is</span> <span
  m='234730'>less</span> <span m='235090'>than</span> <span m='235270'>or</span>
  <span m='235390'>equal</span> <span m='235810'>to</span> <span
  m='237130'>the</span> <span m='237280'>sum</span> <span m='237910'>of</span>
  <span m='238150'>the</span> <span m='238240'>magnitudes</span> <span
  m='239500'>of</span> <span m='239710'>x</span> <span m='239950'>of</span>
  <span m='240050'>n</span> <span m='240460'>summed</span> <span
  m='241060'>over</span> <span m='241750'>minus</span> <span
  m='242200'>infinity--</span> <span m='242800'>n</span> <span
  m='243010'>equals</span> <span m='243280'>minus</span> <span
  m='243670'>infinity</span> <span m='244810'>to</span> <span
  m='244910'>plus</span> <span m='245110'>infinity.</span> </p><p><span
  m='247060'>Well,</span> <span m='247660'>that</span> <span
  m='247900'>tells</span> <span m='248290'>us</span> <span
  m='248530'>then</span> <span m='249100'>that</span> <span
  m='249280'>the</span> <span m='249400'>Fourier</span> <span
  m='249850'>transform</span> <span m='251290'>will</span> <span
  m='251440'>converge,</span> <span m='253000'>converge</span> <span
  m='253510'>meaning</span> <span m='253870'>that</span> <span
  m='253990'>the</span> <span m='254110'>sum</span> <span m='254710'>ends</span>
  <span m='254860'>up</span> <span m='254950'>finite,</span> <span
  m='256360'>if</span> <span m='257110'>this</span> <span
  m='257589'>converges.</span> <span m='258670'>That</span> <span
  m='258850'>is,</span> <span m='258970'>certainly</span> <span
  m='259390'>if</span> <span m='259510'>this</span> <span m='259720'>sum</span>
  <span m='259959'>is</span> <span m='260110'>finite,</span> <span
  m='261200'>then</span> <span m='261940'>the</span> <span
  m='262150'>magnitude</span> <span m='262660'>of</span> <span
  m='262750'>x</span> <span m='262930'>of</span> <span m='263020'>e</span> <span
  m='263260'>to the</span> <span m='263350'>j</span> <span
  m='263560'>omega</span> <span m='263980'>is</span> <span
  m='264160'>finite.</span> <span m='265310'>So</span> <span
  m='265540'>we</span> <span m='265690'>can</span> <span m='265900'>say</span>
  <span m='266620'>that</span> <span m='267400'>x</span> <span
  m='267610'>of</span> <span m='267770'>e</span> <span m='267980'>to</span>
  <span m='268090'>the</span> <span m='268210'>j</span> <span
  m='268450'>omega,</span> <span m='269170'>the</span> <span
  m='269290'>Fourier</span> <span m='269710'>transform,</span> <span
  m='271430'>converges</span> <span m='272830'>if</span> <span
  m='273670'>the</span> <span m='273790'>sum</span> <span m='274660'>of</span>
  <span m='275170'>the</span> <span m='275260'>magnitude</span> <span
  m='276070'>of</span> <span m='276190'>x</span> <span m='276460'>of</span>
  <span m='276610'>n</span> <span m='277210'>is</span> <span
  m='277390'>less</span> <span m='277630'>than</span> <span
  m='277780'>infinity.</span> </p><p><span m='280040'>Well,</span> <span
  m='281150'>this</span> <span m='281780'>is</span> <span m='281960'>a</span>
  <span m='282050'>condition</span> <span m='282860'>that's</span> <span
  m='283730'>commonly</span> <span m='284240'>referred</span> <span
  m='284690'>to</span> <span m='285050'>as</span> <span
  m='285260'>absolutely</span> <span m='285980'>summable.</span> <span
  m='287390'>The</span> <span m='287480'>condition</span> <span
  m='287990'>is</span> <span m='288290'>that</span> <span m='288440'>the</span>
  <span m='288530'>sequence</span> <span m='289010'>x</span> <span m='289330'>of
  n</span> <span m='289700'>be</span> <span m='290000'>absolutely</span> <span
  m='290600'>summable.</span> <span m='292070'>The</span> <span
  m='292190'>way</span> <span m='292760'>we've</span> <span
  m='292970'>gone</span> <span m='293240'>through</span> <span
  m='293540'>this,</span> <span m='294260'>the</span> <span
  m='294530'>statement</span> <span m='295070'>is</span> <span
  m='295790'>that,</span> <span m='295970'>if</span> <span m='296720'>x</span>
  <span m='296990'>of</span> <span m='297110'>n</span> <span
  m='297290'>is</span> <span m='297410'>absolutely</span> <span
  m='298010'>summable,</span> <span m='299190'>then</span> <span
  m='299360'>the</span> <span m='299450'>Fourier</span> <span
  m='299870'>transform</span> <span m='300900'>converges</span> <span
  m='302900'>under</span> <span m='303500'>some</span> <span
  m='304220'>sorts</span> <span m='304610'>of</span> <span
  m='304700'>conditions.</span> <span m='305540'>And</span> <span
  m='305780'>depending</span> <span m='306230'>on</span> <span
  m='306350'>how</span> <span m='306530'>you</span> <span
  m='306710'>interpret</span> <span m='307190'>convergence,</span> <span
  m='308390'>this</span> <span m='308570'>can</span> <span m='308750'>be</span>
  <span m='308870'>modified</span> <span m='309560'>somewhat.</span> <span
  m='310520'>But</span> <span m='310730'>basically--</span> <span
  m='311720'>and</span> <span m='312050'>that,</span> <span m='312320'>in</span>
  <span m='312410'>fact,</span> <span m='312770'>is</span> <span
  m='312890'>discussed</span> <span m='313790'>in</span> <span
  m='313910'>some</span> <span m='314120'>detail</span> <span
  m='315170'>in</span> <span m='315290'>the</span> <span m='315380'>text.</span>
  <span m='316980'>But</span> <span m='317780'>basically,</span> <span
  m='318650'>the</span> <span m='318770'>condition</span> <span
  m='319310'>for</span> <span m='319490'>convergence</span> <span
  m='321170'>of</span> <span m='321440'>the</span> <span
  m='321620'>Fourier</span> <span m='322020'>transform</span> <span
  m='323270'>is</span> <span m='323570'>that</span> <span m='324290'>the</span>
  <span m='324560'>sequence</span> <span m='325890'>whose</span> <span
  m='326060'>Fourier</span> <span m='326510'>transform</span> <span
  m='327170'>we're</span> <span m='327260'>talking</span> <span
  m='327740'>about</span> <span m='328420'>be</span> <span
  m='328670'>absolutely</span> <span m='329270'>summable.</span> </p><p><span
  m='331980'>Now,</span> <span m='332590'>we've</span> <span
  m='332890'>seen</span> <span m='333320'>a</span> <span m='333750'>sum</span>
  <span m='334120'>like</span> <span m='334390'>this</span> <span
  m='334570'>someplace</span> <span m='335150'>else.</span> <span
  m='335840'>In</span> <span m='335860'>fact,</span> <span m='336290'>a</span>
  <span m='336390'>couple</span> <span m='336700'>lectures</span> <span
  m='337180'>ago,</span> <span m='338420'>we</span> <span
  m='338470'>talked</span> <span m='338890'>about</span> <span
  m='339490'>stability</span> <span m='340390'>of</span> <span
  m='340540'>discrete</span> <span m='340930'>time</span> <span
  m='341260'>systems.</span> <span m='342490'>And</span> <span
  m='343240'>the</span> <span m='343330'>statement</span> <span
  m='344050'>about</span> <span m='345040'>stability</span> <span
  m='346300'>was</span> <span m='346690'>that</span> <span m='347260'>the</span>
  <span m='347410'>unit</span> <span m='347680'>sample</span> <span
  m='348100'>response</span> <span m='348610'>of</span> <span
  m='348700'>the</span> <span m='348790'>system</span> <span
  m='349210'>be</span> <span m='349360'>absolutely</span> <span
  m='349900'>summable.</span> <span m='351040'>That</span> <span
  m='351280'>is,</span> <span m='351580'>or</span> <span m='351760'>was,</span>
  <span m='352690'>that,</span> <span m='353200'>if</span> <span
  m='353380'>the</span> <span m='353470'>unit</span> <span
  m='353770'>sample</span> <span m='354160'>response</span> <span
  m='355000'>is</span> <span m='355150'>absolutely</span> <span
  m='355720'>summable,</span> <span m='356890'>then</span> <span
  m='357040'>the</span> <span m='357100'>system</span> <span
  m='357520'>is</span> <span m='357580'>stable.</span> <span
  m='358660'>So</span> <span m='359350'>one</span> <span
  m='360070'>conclusion,</span> <span m='361150'>which</span> <span
  m='361450'>you</span> <span m='361570'>should</span> <span
  m='361720'>tuck</span> <span m='361990'>away</span> <span
  m='362830'>for</span> <span m='363040'>now</span> <span m='363580'>and</span>
  <span m='364150'>we'll</span> <span m='364330'>be</span> <span
  m='364450'>bringing</span> <span m='364870'>into</span> <span
  m='365110'>play</span> <span m='365620'>later</span> <span
  m='366010'>on</span> <span m='366160'>in</span> <span m='366250'>this</span>
  <span m='366430'>lecture,</span> <span m='367720'>is</span> <span
  m='367990'>that</span> <span m='369760'>a</span> <span
  m='369820'>stable</span> <span m='370360'>system</span> <span
  m='372630'>implies</span> <span m='374040'>that</span> <span
  m='374940'>the</span> <span m='375390'>system--</span> <span
  m='376310'>that</span> <span m='376590'>the</span> <span
  m='377490'>frequency</span> <span m='378060'>response,</span> <span
  m='379320'>or</span> <span m='379500'>the</span> <span
  m='379590'>Fourier</span> <span m='379990'>transform</span> <span
  m='380820'>of</span> <span m='380910'>the</span> <span m='381000'>unit</span>
  <span m='381240'>sample</span> <span m='381660'>response,</span> <span
  m='382680'>converges.</span> </p><p><span m='384330'>So</span> <span
  m='385050'>this</span> <span m='385260'>is</span> <span
  m='385410'>convergence,</span> <span m='386420'>then.</span> <span
  m='388070'>And</span> <span m='389660'>we</span> <span m='389810'>can</span>
  <span m='390350'>look</span> <span m='390560'>at</span> <span
  m='390620'>a</span> <span m='390680'>couple</span> <span m='391010'>of</span>
  <span m='391100'>examples</span> <span m='391760'>just</span> <span
  m='392120'>to</span> <span m='392600'>see</span> <span m='393830'>how</span>
  <span m='394040'>this</span> <span m='394250'>looks</span> <span
  m='395270'>in</span> <span m='395510'>some</span> <span
  m='395690'>specific</span> <span m='396230'>cases.</span> <span
  m='397910'>Let's</span> <span m='398600'>first</span> <span
  m='398960'>of</span> <span m='399080'>all</span> <span m='399710'>take</span>
  <span m='399980'>the</span> <span m='400130'>example</span> <span
  m='401030'>of</span> <span m='401300'>the</span> <span
  m='401390'>sequence</span> <span m='402230'>x</span> <span m='402540'>of
  n</span> <span m='402860'>is</span> <span m='403190'>1/2</span> <span
  m='403580'>to</span> <span m='403700'>the</span> <span m='403870'>n</span>
  <span m='404420'>u</span> <span m='404690'>of n</span> <span
  m='405390'>as</span> <span m='405720'>an</span> <span
  m='406130'>exponential</span> <span m='406760'>sequence</span> <span
  m='407960'>which</span> <span m='409010'>is</span> <span
  m='409130'>zero</span> <span m='409550'>for</span> <span m='409760'>n</span>
  <span m='409910'>less</span> <span m='410150'>than</span> <span
  m='410330'>zero</span> <span m='410690'>because</span> <span
  m='411050'>of</span> <span m='411130'>the</span> <span m='411260'>unit</span>
  <span m='411590'>step.</span> <span m='412400'>It's</span> <span
  m='412580'>exponentially</span> <span m='413330'>decaying</span> <span
  m='416370'>for</span> <span m='416700'>n</span> <span
  m='416910'>greater</span> <span m='417310'>than</span> <span
  m='417490'>zero.</span> </p><p><span m='419420'>If</span> <span
  m='419600'>we</span> <span m='419760'>sum</span> <span m='421220'>the</span>
  <span m='421310'>magnitude</span> <span m='421940'>of</span> <span
  m='422030'>x</span> <span m='422290'>of</span> <span m='422620'>n</span> <span
  m='422960'>from</span> <span m='423170'>minus</span> <span
  m='423530'>infinity</span> <span m='424040'>to</span> <span
  m='424130'>plus</span> <span m='424430'>infinity,</span> <span
  m='425575'>we</span> <span m='425940'>get</span> <span m='426440'>that</span>
  <span m='427740'>the</span> <span m='428140'>magnitude,</span> <span
  m='429080'>the</span> <span m='429170'>sum</span> <span m='429470'>of</span>
  <span m='429560'>the</span> <span m='429650'>magnitude</span> <span
  m='430280'>of</span> <span m='430370'>x</span> <span m='430640'>of</span>
  <span m='430760'>n</span> <span m='431510'>is</span> <span
  m='431630'>equal</span> <span m='431930'>to</span> <span
  m='432080'>two.</span> <span m='433290'>Well,</span> <span
  m='434360'>this</span> <span m='434570'>is</span> <span
  m='434660'>something,</span> <span m='435665'>a</span> <span
  m='435980'>type</span> <span m='436310'>of</span> <span m='436430'>sum</span>
  <span m='436790'>that</span> <span m='437270'>hopefully</span> <span
  m='437750'>you're</span> <span m='437870'>familiar</span> <span
  m='438320'>with</span> <span m='438470'>carrying</span> <span
  m='438950'>out.</span> <span m='440210'>In</span> <span m='440360'>any</span>
  <span m='440570'>case,</span> <span m='442020'>what</span> <span
  m='442100'>we're</span> <span m='442220'>summing</span> <span
  m='442610'>here</span> <span m='443150'>is</span> <span m='443930'>the</span>
  <span m='444020'>series</span> <span m='445090'>1,</span> <span
  m='445690'>1/2,</span> <span m='446510'>1/4,</span> <span
  m='447110'>1/8,</span> <span m='447320'>et</span> <span
  m='447620'>cetera.</span> <span m='448220'>That</span> <span
  m='448410'>sums</span> <span m='449160'>to</span> <span m='449310'>two.</span>
  <span m='450470'>So</span> <span m='451100'>we</span> <span
  m='451310'>can</span> <span m='451460'>say</span> <span
  m='452120'>that,</span> <span m='452560'>for</span> <span
  m='452750'>this</span> <span m='452930'>sequence,</span> <span
  m='453500'>certainly,</span> <span m='454640'>the</span> <span
  m='454760'>Fourier</span> <span m='455210'>transform</span> <span
  m='455870'>converges.</span> <span m='457025'>It's a</span> <span
  m='457460'>perfectly</span> <span m='458570'>well-behaved</span> <span
  m='459200'>sequence.</span> <span m='459800'>A</span> <span
  m='459860'>Fourier</span> <span m='460250'>transform</span> <span
  m='460820'>converges,</span> <span m='461420'>we</span> <span
  m='461510'>can</span> <span m='461660'>compute</span> <span
  m='462040'>the</span> <span m='462140'>Fourier</span> <span
  m='462500'>transform,</span> <span m='462800'>et</span> <span
  m='463100'>cetera.</span> </p><p><span m='465850'>Well,</span> <span
  m='466540'>another</span> <span m='466870'>sequence</span> <span
  m='467650'>we</span> <span m='467800'>can</span> <span m='467980'>try</span>
  <span m='468610'>is</span> <span m='468820'>the</span> <span
  m='468910'>sequence</span> <span m='469630'>x</span> <span
  m='469960'>of</span> <span m='470110'>n</span> <span m='470560'>equals</span>
  <span m='471250'>2</span> <span m='471520'>to</span> <span
  m='471700'>the</span> <span m='471880'>n</span> <span m='472840'>times</span>
  <span m='473460'>a</span> <span m='473590'>unit</span> <span
  m='473890'>step.</span> <span m='476160'>Well,</span> <span
  m='477150'>if</span> <span m='477330'>we</span> <span m='477420'>just</span>
  <span m='477600'>think</span> <span m='477840'>about</span> <span
  m='478110'>the</span> <span m='478200'>values</span> <span
  m='478710'>that</span> <span m='478830'>we</span> <span
  m='479040'>have,</span> <span m='479580'>at</span> <span m='479720'>n</span>
  <span m='479820'>equals</span> <span m='480090'>zero</span> <span
  m='480480'>we</span> <span m='480630'>have</span> <span m='480870'>1,</span>
  <span m='481140'>at</span> <span m='481410'>n</span> <span
  m='481800'>equals</span> <span m='482100'>1,</span> <span m='482440'>we</span>
  <span m='482460'>have</span> <span m='482700'>2,</span> <span m='483090'>at
  n</span> <span m='483300'>equals</span> <span m='483600'>2,</span> <span
  m='483870'>we</span> <span m='483990'>have</span> <span m='484140'>4,</span>
  <span m='484590'>at</span> <span m='484680'>n</span> <span
  m='484770'>equals</span> <span m='485070'>3,</span> <span m='485320'>we</span>
  <span m='485460'>have</span> <span m='486330'>8.</span> <span
  m='487600'>And</span> <span m='488020'>obviously,</span> <span
  m='488740'>then,</span> <span m='489370'>the</span> <span
  m='489460'>sum</span> <span m='489970'>of</span> <span m='490150'>the</span>
  <span m='490270'>absolute</span> <span m='490690'>values</span> <span
  m='491740'>of</span> <span m='491890'>x</span> <span m='492130'>of</span>
  <span m='492230'>n</span> <span m='492880'>for</span> <span
  m='493030'>that</span> <span m='493240'>particular</span> <span
  m='493780'>sequence</span> <span m='497240'>diverges.</span> <span
  m='498470'>That</span> <span m='498710'>is,</span> <span m='499280'>the</span>
  <span m='499400'>sum</span> <span m='499670'>is</span> <span
  m='499790'>infinite.</span> </p><p><span m='500900'>So</span> <span
  m='501470'>here's</span> <span m='501770'>an</span> <span
  m='501860'>example</span> <span m='502370'>of</span> <span m='502490'>a</span>
  <span m='502550'>sequence</span> <span m='504750'>for</span> <span
  m='505220'>which</span> <span m='505700'>the</span> <span
  m='505790'>Fourier</span> <span m='506240'>transform</span> <span
  m='506930'>doesn't</span> <span m='507290'>converge.</span> <span
  m='508070'>In</span> <span m='508190'>other</span> <span
  m='508370'>words,</span> <span m='508760'>the</span> <span
  m='508860'>Fourier</span> <span m='509150'>transform</span> <span
  m='509750'>for</span> <span m='509900'>this</span> <span
  m='510080'>sequence</span> <span m='510830'>doesn't</span> <span
  m='511130'>exist.</span> <span m='512090'>And</span> <span
  m='512210'>you</span> <span m='512330'>can</span> <span
  m='512480'>imagine</span> <span m='512960'>the</span> <span
  m='513049'>generalization</span> <span m='513950'>here</span> <span
  m='514750'>that,</span> <span m='515640'>if</span> <span m='516169'>we</span>
  <span m='516289'>talk</span> <span m='516590'>about</span> <span
  m='516830'>a</span> <span m='516890'>sequence</span> <span
  m='518179'>which</span> <span m='518450'>decays</span> <span
  m='519020'>exponentially--</span> <span m='519980'>by</span> <span
  m='520190'>the</span> <span m='520309'>way,</span> <span m='520490'>in</span>
  <span m='520610'>either</span> <span m='520850'>direction,</span> <span
  m='521480'>negative</span> <span m='521750'>n</span> <span
  m='522020'>or</span> <span m='522110'>positive</span> <span
  m='522679'>n--</span> <span m='523039'>then</span> <span m='523419'>the</span>
  <span m='523799'>Fourier</span> <span m='524059'>transform</span> <span
  m='524810'>will</span> <span m='524970'>exist,</span> <span
  m='526160'>whereas</span> <span m='527930'>if</span> <span
  m='528110'>it's</span> <span m='528230'>an</span> <span
  m='528320'>exponential</span> <span m='528950'>sequence</span> <span
  m='529610'>that</span> <span m='529760'>grows</span> <span
  m='530210'>exponentially,</span> <span m='531740'>then</span> <span
  m='532430'>the</span> <span m='532550'>Fourier</span> <span
  m='532970'>transform</span> <span m='533720'>is</span> <span
  m='533900'>not</span> <span m='534110'>going</span> <span m='534320'>to</span>
  <span m='534440'>exist,</span> <span m='534890'>or</span> <span
  m='534980'>is</span> <span m='535100'>not</span> <span m='535310'>going</span>
  <span m='535550'>to</span> <span m='535640'>converge.</span> </p><p><span
  m='538040'>Well,</span> <span m='538340'>what</span> <span
  m='538490'>do</span> <span m='538550'>we</span> <span m='538670'>do</span>
  <span m='538880'>about</span> <span m='539210'>that?</span> <span
  m='541200'>There</span> <span m='541680'>is</span> <span m='542190'>a</span>
  <span m='542310'>way</span> <span m='542550'>around</span> <span
  m='543060'>it</span> <span m='543690'>by</span> <span
  m='544530'>essentially</span> <span m='546600'>using</span> <span
  m='547410'>the</span> <span m='548370'>artifice</span> <span
  m='549300'>of</span> <span m='550410'>multiplying</span> <span
  m='552180'>a</span> <span m='552240'>sequence</span> <span
  m='553260'>that</span> <span m='553830'>doesn't</span> <span
  m='554190'>converge,</span> <span m='555000'>or</span> <span
  m='555390'>say</span> <span m='555630'>that</span> <span
  m='555750'>grows</span> <span m='556170'>exponentially</span> <span
  m='557880'>by</span> <span m='558210'>a</span> <span
  m='558540'>decaying</span> <span m='559170'>exponential,</span> <span
  m='560610'>and</span> <span m='561090'>making</span> <span
  m='561510'>the</span> <span m='561630'>decay</span> <span m='562110'>on</span>
  <span m='562230'>the</span> <span m='562350'>exponential</span> <span
  m='563010'>fast</span> <span m='563490'>enough</span> <span
  m='564210'>so</span> <span m='564390'>that</span> <span m='564570'>the</span>
  <span m='564660'>product</span> <span m='565230'>has</span> <span
  m='565410'>a</span> <span m='565470'>Fourier</span> <span
  m='565920'>transform.</span> <span m='567660'>That</span> <span
  m='567870'>is,</span> <span m='568800'>we</span> <span m='568950'>can</span>
  <span m='569100'>talk</span> <span m='569460'>about</span> <span
  m='569910'>the</span> <span m='570030'>Fourier</span> <span
  m='570450'>transform</span> <span m='571380'>in</span> <span
  m='571530'>general,</span> <span m='572680'>not</span> <span
  m='572910'>of</span> <span m='573120'>x</span> <span m='573390'>of</span>
  <span m='573510'>n,</span> <span m='574710'>but</span> <span
  m='575460'>of</span> <span m='576090'>x</span> <span m='576390'>of</span>
  <span m='576540'>n</span> <span m='577590'>multiplied</span> <span
  m='579030'>by</span> <span m='580560'>a</span> <span
  m='580620'>sequence</span> <span m='582320'>r</span> <span
  m='582630'>to</span> <span m='582780'>the</span> <span m='582900'>minus</span>
  <span m='583360'>n,</span> <span m='586080'>for</span> <span
  m='586260'>which</span> <span m='586500'>we</span> <span
  m='586620'>pick</span> <span m='587060'>r</span> <span m='587940'>so</span>
  <span m='588240'>that</span> <span m='588480'>the</span> <span
  m='588600'>product</span> <span m='589440'>of</span> <span
  m='589590'>these</span> <span m='589890'>two</span> <span m='590730'>is</span>
  <span m='590880'>absolutely</span> <span m='591480'>summable.</span>
  </p><p><span m='592950'>And</span> <span m='593700'>since</span> <span
  m='593940'>we've</span> <span m='594090'>introduced</span> <span
  m='594630'>another</span> <span m='594930'>parameter</span> <span
  m='595530'>r,</span> <span m='596730'>then</span> <span m='597240'>the</span>
  <span m='597370'>Fourier</span> <span m='597780'>transform</span> <span
  m='598740'>of</span> <span m='599010'>x</span> <span m='599310'>of</span>
  <span m='599430'>n</span> <span m='599730'>times</span> <span
  m='600030'>r</span> <span m='600240'>to</span> <span m='600390'>the</span>
  <span m='600480'>minus</span> <span m='600930'>n,</span> <span
  m='601830'>we</span> <span m='601950'>don't</span> <span
  m='602160'>want</span> <span m='602340'>to</span> <span m='602400'>call</span>
  <span m='602970'>x</span> <span m='603240'>of</span> <span m='603360'>e</span>
  <span m='603510'>to the</span> <span m='603600'>j</span> <span
  m='603840'>omega.</span> <span m='604880'>Let's</span> <span
  m='605430'>for</span> <span m='605730'>now</span> <span
  m='606700'>think</span> <span m='606870'>of</span> <span m='606990'>it</span>
  <span m='607200'>as</span> <span m='607950'>x</span> <span
  m='608250'>of</span> <span m='608400'>r</span> <span m='609150'>times</span>
  <span m='609690'>e</span> <span m='609790'>to</span> <span
  m='609930'>the</span> <span m='610020'>j</span> <span m='610230'>omega,</span>
  <span m='611070'>the</span> <span m='611220'>r</span> <span
  m='611940'>denoting</span> <span m='612870'>the</span> <span
  m='612960'>complex</span> <span m='613620'>exponential</span> <span
  m='614880'>that</span> <span m='615060'>we're</span> <span
  m='615210'>multiplying</span> <span m='615990'>by.</span> <span
  m='617790'>And</span> <span m='618330'>then,</span> <span m='618570'>of</span>
  <span m='618690'>course,</span> <span m='618990'>for</span> <span
  m='619140'>some</span> <span m='619410'>values</span> <span
  m='619920'>of</span> <span m='620040'>r,</span> <span m='620940'>this</span>
  <span m='621150'>sum</span> <span m='621810'>is</span> <span
  m='621960'>going</span> <span m='622200'>to</span> <span
  m='622320'>converge.</span> <span m='623640'>For</span> <span
  m='623850'>other</span> <span m='624060'>values</span> <span
  m='624540'>of</span> <span m='624690'>r,</span> <span m='625380'>this</span>
  <span m='625530'>sum</span> <span m='625950'>is</span> <span
  m='626130'>not</span> <span m='626370'>going</span> <span m='626490'>to</span>
  <span m='626580'>converge.</span> </p><p><span m='628110'>For</span> <span
  m='628260'>example,</span> <span m='629490'>if</span> <span
  m='629590'>we</span> <span m='629690'>look</span> <span m='629790'>at</span>
  <span m='629880'>our</span> <span m='630030'>example</span> <span
  m='630540'>two</span> <span m='630900'>here,</span> <span m='632490'>if</span>
  <span m='632670'>I</span> <span m='632760'>multiply</span> <span
  m='634740'>this</span> <span m='634980'>sequence</span> <span
  m='636840'>by</span> <span m='637080'>a</span> <span
  m='637140'>decaying</span> <span m='637800'>exponential</span> <span
  m='639360'>that</span> <span m='639510'>decays</span> <span
  m='640560'>fast</span> <span m='641130'>enough</span> <span
  m='642090'>so</span> <span m='642270'>that</span> <span m='642750'>the</span>
  <span m='642870'>product</span> <span m='643740'>decays--</span> <span
  m='645120'>and</span> <span m='645390'>what</span> <span m='645510'>do</span>
  <span m='645630'>I</span> <span m='645690'>have</span> <span
  m='645870'>to</span> <span m='645960'>multiply</span> <span
  m='646530'>it</span> <span m='646620'>by?</span> <span m='646990'>I</span>
  <span m='647070'>have</span> <span m='647280'>to</span> <span
  m='647400'>multiply</span> <span m='647940'>it</span> <span
  m='648060'>by</span> <span m='648240'>something</span> <span
  m='648660'>that</span> <span m='648770'>decays</span> <span
  m='649320'>faster</span> <span m='650520'>than</span> <span
  m='651210'>1/2</span> <span m='652290'>to</span> <span m='652410'>the</span>
  <span m='652590'>n.</span> <span m='653710'>So</span> <span
  m='654660'>if</span> <span m='654990'>I</span> <span m='655140'>stick</span>
  <span m='655500'>in</span> <span m='655680'>here</span> <span
  m='656430'>an</span> <span m='656610'>r</span> <span m='658440'>that</span>
  <span m='658710'>is</span> <span m='659460'>greater</span> <span
  m='659910'>than</span> <span m='660090'>2--</span> <span m='661560'>2</span>
  <span m='661800'>because</span> <span m='662310'>there's</span> <span
  m='662490'>a</span> <span m='662550'>minus</span> <span m='662910'>sign</span>
  <span m='663210'>here,</span> <span m='663420'>r</span> <span
  m='663700'>to</span> <span m='663750'>the</span> <span m='663840'>minus</span>
  <span m='664260'>n--</span> <span m='665520'>then</span> <span
  m='666030'>I'll</span> <span m='666270'>end</span> <span m='666570'>up</span>
  <span m='667200'>with,</span> <span m='668770'>for</span> <span
  m='669010'>this</span> <span m='669250'>sequence,</span> <span
  m='670360'>with</span> <span m='670710'>a</span> <span m='670790'>sum</span>
  <span m='671390'>here</span> <span m='671800'>that</span> <span
  m='671920'>converges.</span> </p><p><span m='673190'>So</span> <span
  m='673300'>for</span> <span m='673420'>this</span> <span
  m='673660'>example,</span> <span m='674690'>if</span> <span
  m='674770'>r--</span> <span m='675450'>any</span> <span
  m='675700'>choice</span> <span m='676060'>of</span> <span m='676160'>r</span>
  <span m='676840'>greater</span> <span m='677230'>than</span> <span
  m='677410'>two,</span> <span m='678520'>this</span> <span
  m='678700'>sum</span> <span m='679120'>is</span> <span m='679270'>going</span>
  <span m='679390'>to</span> <span m='679480'>converge.</span> <span
  m='680170'>And</span> <span m='680320'>I</span> <span m='680380'>can</span>
  <span m='680560'>talk</span> <span m='680920'>about</span> <span
  m='681250'>x</span> <span m='681560'>of</span> <span m='681840'>r</span> <span
  m='681980'>of e</span> <span m='682240'>to the</span> <span
  m='682330'>j</span> <span m='682540'>omega.</span> <span m='683300'>So</span>
  <span m='683350'>that's</span> <span m='683620'>the</span> <span
  m='683740'>idea.</span> <span m='684250'>The</span> <span
  m='684370'>idea</span> <span m='684760'>is</span> <span m='684940'>to</span>
  <span m='685060'>multiply</span> <span m='685600'>by</span> <span
  m='685810'>an</span> <span m='685900'>exponential</span> <span
  m='687220'>that</span> <span m='688150'>decays</span> <span
  m='688630'>fast</span> <span m='689020'>enough</span> <span
  m='689440'>or</span> <span m='689590'>doesn't</span> <span
  m='689920'>grow</span> <span m='690220'>so</span> <span m='690520'>fast</span>
  <span m='691570'>that</span> <span m='692440'>the</span> <span
  m='692530'>product</span> <span m='693140'>x</span> <span m='693400'>of</span>
  <span m='693580'>n</span> <span m='693880'>times</span> <span
  m='694180'>r</span> <span m='694370'>to</span> <span m='694450'>the</span>
  <span m='694540'>minus</span> <span m='694930'>n</span> <span
  m='695140'>converges.</span> </p><p><span m='697150'>Well,</span> <span
  m='697390'>we</span> <span m='697510'>can</span> <span
  m='697690'>rewrite</span> <span m='698170'>this</span> <span
  m='698620'>a</span> <span m='698650'>little</span> <span
  m='698890'>differently.</span> <span m='700030'>We</span> <span
  m='700150'>can</span> <span m='700330'>combine</span> <span
  m='701170'>the</span> <span m='701380'>r</span> <span m='701620'>to</span>
  <span m='701770'>the</span> <span m='701890'>minus</span> <span
  m='702340'>n</span> <span m='702820'>and</span> <span m='703100'>the e</span>
  <span m='703600'>to</span> <span m='703720'>the</span> <span
  m='703840'>minus</span> <span m='704200'>j</span> <span
  m='704575'>omega</span> <span m='704950'>n.</span> <span m='706240'>And</span>
  <span m='706690'>what</span> <span m='706930'>results</span> <span
  m='707590'>is</span> <span m='707770'>the</span> <span m='707890'>sum,</span>
  <span m='708610'>minus</span> <span m='708940'>infinity</span> <span
  m='709420'>to</span> <span m='709540'>plus</span> <span
  m='709810'>infinity,</span> <span m='710980'>of</span> <span
  m='711310'>x</span> <span m='711600'>of</span> <span m='711990'>n</span> <span
  m='712630'>times</span> <span m='713590'>re</span> <span m='714460'>to</span>
  <span m='714520'>the</span> <span m='714640'>j</span> <span
  m='714880'>omega</span> <span m='715300'>to</span> <span m='715420'>the</span>
  <span m='715540'>minus</span> <span m='715940'>n,</span> <span
  m='716500'>just</span> <span m='716680'>simply</span> <span
  m='717040'>combining</span> <span m='717580'>these</span> <span
  m='717790'>two</span> <span m='717970'>terms</span> <span
  m='718390'>together.</span> <span m='720490'>And</span> <span
  m='721240'>it's</span> <span m='721450'>convenient</span> <span
  m='722020'>to</span> <span m='722170'>think</span> <span m='722470'>of</span>
  <span m='722590'>this</span> <span m='724090'>as</span> <span
  m='724720'>a</span> <span m='724810'>new</span> <span
  m='725020'>complex</span> <span m='725650'>variable,</span> <span
  m='727210'>magnitude</span> <span m='727900'>r</span> <span
  m='728470'>and</span> <span m='728700'>angle</span> <span
  m='729130'>omega,</span> <span m='730640'>which</span> <span
  m='731050'>we'll</span> <span m='731740'>denote</span> <span
  m='732490'>by</span> <span m='732700'>z,</span> <span m='734290'>z</span>
  <span m='734680'>as</span> <span m='735040'>in</span> <span
  m='735790'>the</span> <span m='735880'>Z-transform.</span> </p><p><span
  m='738050'>The</span> <span m='738150'>Z-transform.</span> <span
  m='740140'>So,</span> <span m='740830'>this</span> <span
  m='741490'>essentially</span> <span m='742060'>leads</span> <span
  m='742450'>us</span> <span m='743140'>to</span> <span m='743560'>the</span>
  <span m='743710'>notion</span> <span m='744370'>of</span> <span
  m='744550'>the</span> <span m='744880'>Z-transform,</span> <span
  m='746560'>where</span> <span m='747490'>the</span> <span
  m='747610'>Z-transform</span> <span m='749140'>of</span> <span
  m='749290'>a</span> <span m='749350'>sequence</span> <span m='750070'>x</span>
  <span m='750400'>of</span> <span m='750520'>n</span> <span
  m='751870'>is</span> <span m='752530'>defined</span> <span
  m='753160'>as</span> <span m='753640'>x</span> <span m='754000'>of</span>
  <span m='754120'>z</span> <span m='755140'>is</span> <span
  m='755290'>equal</span> <span m='755590'>to</span> <span m='755740'>the</span>
  <span m='755860'>sum</span> <span m='756430'>of</span> <span
  m='756700'>x</span> <span m='757120'>of</span> <span m='757390'>n</span> <span
  m='757870'>times</span> <span m='758260'>z</span> <span m='758950'>to</span>
  <span m='759070'>the</span> <span m='759190'>minus</span> <span
  m='759650'>n,</span> <span m='761950'>where</span> <span m='762190'>z</span>
  <span m='762760'>is</span> <span m='762970'>equal</span> <span
  m='763450'>to</span> <span m='763870'>r</span> <span m='764250'>times</span>
  <span m='764620'>e</span> <span m='764720'>to</span> <span
  m='764830'>the</span> <span m='764950'>j</span> <span m='765190'>omega.</span>
  <span m='766120'>In</span> <span m='766180'>other</span> <span
  m='766390'>words,</span> <span m='767210'>x</span> <span m='767410'>of</span>
  <span m='767530'>z</span> <span m='768430'>is</span> <span
  m='768580'>just</span> <span m='768790'>simply</span> <span
  m='769390'>the</span> <span m='769720'>x</span> <span m='770170'>sub</span>
  <span m='770540'>r</span> <span m='771280'>of</span> <span m='771430'>e</span>
  <span m='771610'>to the</span> <span m='771730'>j</span> <span
  m='771940'>omega</span> <span m='772390'>that</span> <span
  m='772510'>we</span> <span m='772630'>finished</span> <span
  m='772960'>talking</span> <span m='773410'>about.</span> </p><p><span
  m='775110'>Well,</span> <span m='776070'>how</span> <span m='776310'>is</span>
  <span m='776430'>the</span> <span m='776520'>Z-transform</span> <span
  m='778110'>related</span> <span m='778710'>to</span> <span
  m='778830'>the</span> <span m='778930'>Fourier</span> <span
  m='779400'>transform</span> <span m='780380'>if</span> <span
  m='780470'>the</span> <span m='780660'>Fourier</span> <span
  m='780990'>transform</span> <span m='781620'>exists?</span> <span
  m='783540'>Obviously,</span> <span m='784680'>from</span> <span
  m='784860'>what</span> <span m='784980'>we</span> <span m='785130'>just</span>
  <span m='785340'>finished</span> <span m='785700'>saying,</span> <span
  m='787420'>the</span> <span m='787540'>Z-transform</span> <span
  m='788680'>is</span> <span m='788830'>the</span> <span
  m='788930'>Fourier</span> <span m='789370'>transform</span> <span
  m='790270'>for</span> <span m='790420'>this</span> <span
  m='790600'>weighting</span> <span m='791320'>factor</span> <span
  m='791950'>r</span> <span m='792760'>equal</span> <span m='793060'>to</span>
  <span m='793180'>unity.</span> <span m='793660'>That</span> <span
  m='793900'>is,</span> <span m='795220'>x</span> <span m='796750'>of</span>
  <span m='797170'>e</span> <span m='797575'>to</span> <span
  m='797980'>the</span> <span m='798100'>j</span> <span m='798690'>omega</span>
  <span m='801220'>is</span> <span m='801430'>equal</span> <span
  m='801880'>to</span> <span m='803080'>x</span> <span m='803380'>of</span>
  <span m='803530'>z</span> <span m='806730'>where?</span> <span
  m='807600'>Well,</span> <span m='809160'>for</span> <span m='809310'>z</span>
  <span m='810380'>equal</span> <span m='810880'>to</span> <span
  m='811440'>e</span> <span m='811910'>to</span> <span m='812160'>the</span>
  <span m='812250'>j</span> <span m='812730'>omega--</span> <span
  m='814410'>or</span> <span m='814800'>another</span> <span
  m='815130'>way</span> <span m='815310'>of</span> <span
  m='815400'>saying</span> <span m='815820'>that</span> <span
  m='816390'>is</span> <span m='817060'>for</span> <span m='817260'>the</span>
  <span m='817380'>magnitude</span> <span m='818040'>of</span> <span
  m='818130'>z</span> <span m='819150'>equal</span> <span m='819480'>to</span>
  <span m='819630'>unity.</span> <span m='820470'>With</span> <span
  m='820620'>z</span> <span m='820820'>equal</span> <span m='821040'>to</span>
  <span m='821160'>e</span> <span m='821260'>to</span> <span
  m='821350'>the</span> <span m='821460'>j</span> <span m='821670'>omega,</span>
  <span m='822600'>the</span> <span m='822690'>magnitude</span> <span
  m='823200'>of</span> <span m='823260'>z</span> <span
  m='823530'>obviously</span> <span m='824280'>is</span> <span
  m='824430'>equal</span> <span m='824700'>to</span> <span
  m='824820'>unity.</span> </p><p><span m='826170'>So</span> <span
  m='827700'>we</span> <span m='827850'>have</span> <span m='828300'>now</span>
  <span m='828570'>the</span> <span m='828660'>Z-transform.</span> <span
  m='830310'>It's</span> <span m='830460'>a</span> <span
  m='830520'>function</span> <span m='831450'>of</span> <span
  m='832020'>a</span> <span m='832110'>complex</span> <span
  m='832680'>variable</span> <span m='833190'>z,</span> <span
  m='834400'>which</span> <span m='834480'>has</span> <span m='834720'>a</span>
  <span m='834780'>magnitude</span> <span m='835530'>r</span> <span
  m='837090'>and</span> <span m='837750'>an</span> <span m='837870'>angle</span>
  <span m='838320'>omega.</span> <span m='840240'>And</span> <span
  m='841200'>it's</span> <span m='841380'>just</span> <span
  m='841560'>simply</span> <span m='841980'>a</span> <span
  m='842040'>generalization</span> <span m='843120'>of</span> <span
  m='843270'>the</span> <span m='843390'>Fourier</span> <span
  m='843840'>transform.</span> <span m='844860'>It,</span> <span
  m='845260'>in</span> <span m='845390'>fact,</span> <span m='845730'>is</span>
  <span m='845880'>equal</span> <span m='846210'>to</span> <span
  m='846330'>the</span> <span m='846420'>Fourier</span> <span
  m='846870'>transform</span> <span m='848070'>for</span> <span
  m='848160'>the</span> <span m='848250'>magnitude</span> <span
  m='848850'>of</span> <span m='848940'>z</span> <span m='849120'>equal</span>
  <span m='849420'>to</span> <span m='849570'>1.</span> <span
  m='850690'>And</span> <span m='851405'>it,</span> <span m='851730'>in</span>
  <span m='851910'>effect,</span> <span m='852690'>corresponds</span> <span
  m='853800'>to</span> <span m='853920'>the</span> <span
  m='854040'>Fourier</span> <span m='854520'>transform</span> <span
  m='855450'>of</span> <span m='855600'>the</span> <span
  m='855690'>sequence</span> <span m='856650'>multiplied</span> <span
  m='857970'>by</span> <span m='859410'>an</span> <span
  m='859530'>exponential</span> <span m='860280'>sequence</span> <span
  m='860870'>r</span> <span m='861090'>to</span> <span m='861240'>the</span>
  <span m='861330'>minus</span> <span m='861730'>n.</span> </p><p><span
  m='864360'>When</span> <span m='864540'>does</span> <span
  m='864690'>the</span> <span m='864750'>Z-transform</span> <span
  m='865620'>converge?</span> <span m='867450'>Well,</span> <span
  m='867990'>the</span> <span m='868080'>Z-transform</span> <span
  m='869340'>converges</span> <span m='870450'>when</span> <span
  m='871110'>this</span> <span m='871380'>x</span> <span m='871700'>sub</span>
  <span m='871880'>r</span> <span m='872460'>of</span> <span m='872640'>e</span>
  <span m='872820'>to the</span> <span m='872910'>j</span> <span
  m='873180'>omega</span> <span m='873900'>that</span> <span
  m='874020'>we</span> <span m='874170'>were</span> <span
  m='874290'>talking</span> <span m='874770'>about</span> <span
  m='875370'>converges.</span> <span m='876660'>And</span> <span
  m='876780'>that</span> <span m='876990'>converges</span> <span
  m='877830'>when</span> <span m='878070'>the</span> <span
  m='878160'>sequence</span> <span m='878730'>x</span> <span
  m='879030'>of</span> <span m='879150'>n</span> <span m='879420'>r</span> <span
  m='879660'>to</span> <span m='879780'>the</span> <span m='879900'>minus</span>
  <span m='880320'>n</span> <span m='880770'>is</span> <span
  m='880950'>absolutely</span> <span m='881550'>summable.</span> <span
  m='882870'>So</span> <span m='883530'>the</span> <span
  m='883620'>Z-transform</span> <span m='884550'>converges</span> <span
  m='886020'>if</span> <span m='886770'>the</span> <span m='886860'>sum</span>
  <span m='887610'>of</span> <span m='887790'>x</span> <span
  m='888120'>of</span> <span m='888240'>n</span> <span m='888630'>times</span>
  <span m='888990'>r</span> <span m='889200'>to</span> <span
  m='889320'>the</span> <span m='889440'>minus</span> <span m='889830'>n</span>
  <span m='890460'>is</span> <span m='890940'>finite.</span> <span
  m='892920'>And</span> <span m='893340'>for</span> <span m='893520'>some</span>
  <span m='893790'>values</span> <span m='894270'>of</span> <span
  m='894390'>r,</span> <span m='895290'>given</span> <span m='895560'>a</span>
  <span m='895620'>certain</span> <span m='895950'>sequence,</span> <span
  m='896490'>for</span> <span m='896610'>some</span> <span
  m='896880'>values</span> <span m='897330'>of</span> <span m='897450'>r</span>
  <span m='899610'>the</span> <span m='899740'>Z-transform</span> <span
  m='900820'>will</span> <span m='901000'>converge,</span> <span
  m='901930'>for</span> <span m='902050'>some</span> <span
  m='902320'>values</span> <span m='902770'>of</span> <span m='902890'>r</span>
  <span m='903350'>the</span> <span m='903480'>Z-transform</span> <span
  m='904300'>won't</span> <span m='904480'>converge.</span> </p><p><span
  m='906720'>Well</span> <span m='907380'>let's</span> <span
  m='908010'>look</span> <span m='908250'>at</span> <span m='908310'>an</span>
  <span m='908430'>example.</span> <span m='909390'>And</span> <span
  m='910560'>it's</span> <span m='910680'>an</span> <span
  m='910770'>example,</span> <span m='911580'>I</span> <span
  m='911700'>guess,</span> <span m='912090'>that</span> <span
  m='913590'>you're</span> <span m='913740'>seeing</span> <span
  m='914220'>fairly</span> <span m='914670'>frequently.</span> <span
  m='915270'>In</span> <span m='915390'>fact,</span> <span
  m='915820'>it'll</span> <span m='915930'>keep</span> <span
  m='916650'>cropping</span> <span m='917130'>up</span> <span
  m='917280'>in</span> <span m='917400'>a</span> <span m='917430'>variety</span>
  <span m='918000'>of</span> <span m='918090'>ways.</span> <span
  m='919880'>It's</span> <span m='920040'>kind</span> <span m='920280'>of</span>
  <span m='920370'>a</span> <span m='920460'>simple</span> <span
  m='920850'>one,</span> <span m='921090'>and</span> <span
  m='921180'>nice</span> <span m='921450'>to</span> <span m='921570'>use.</span>
  <span m='922710'>That</span> <span m='922890'>is</span> <span
  m='923190'>the</span> <span m='923310'>sequence--</span> <span
  m='923880'>our</span> <span m='924030'>old</span> <span
  m='924180'>friend</span> <span m='924540'>again--</span> <span
  m='925470'>x</span> <span m='925800'>of</span> <span m='926145'>n</span> <span
  m='926490'>is</span> <span m='926880'>1/2</span> <span m='927180'>to</span>
  <span m='927300'>the</span> <span m='927480'>n</span> <span
  m='927990'>times</span> <span m='928680'>u</span> <span m='928860'>of
  n.</span> <span m='931530'>Well,</span> <span m='932160'>the</span> <span
  m='932280'>Z-transform</span> <span m='933960'>of</span> <span
  m='934380'>x</span> <span m='934710'>of</span> <span m='934830'>n,</span>
  <span m='935940'>x of</span> <span m='936200'>z</span> <span
  m='936840'>is</span> <span m='937080'>the</span> <span m='937200'>sum</span>
  <span m='938250'>of</span> <span m='939270'>x</span> <span
  m='939660'>of</span> <span m='939870'>n</span> <span m='940110'>z</span> <span
  m='940185'>to</span> <span m='940260'>the</span> <span m='940350'>minus</span>
  <span m='940800'>n.</span> <span m='942360'>Since</span> <span
  m='942720'>this</span> <span m='942930'>is</span> <span
  m='943020'>multiplied</span> <span m='943350'>by</span> <span
  m='943680'>a</span> <span m='943900'>unit</span> <span m='944270'>step,</span>
  <span m='945060'>the</span> <span m='945150'>limits</span> <span
  m='945510'>on</span> <span m='945660'>the</span> <span m='945750'>sum</span>
  <span m='946230'>are</span> <span m='946380'>from</span> <span
  m='946590'>zero</span> <span m='946980'>to</span> <span
  m='947160'>infinity.</span> <span m='948640'>So</span> <span
  m='949380'>this</span> <span m='949620'>is</span> <span m='949710'>the</span>
  <span m='949830'>sum</span> <span m='950220'>from</span> <span
  m='950400'>zero</span> <span m='950730'>to</span> <span
  m='950880'>infinity</span> <span m='951600'>of</span> <span
  m='952020'>1/2</span> <span m='952440'>to</span> <span m='952560'>the</span>
  <span m='952740'>n</span> <span m='953130'>z</span> <span m='953580'>to</span>
  <span m='953770'>the</span> <span m='953850'>minus</span> <span
  m='954360'>n.</span> <span m='955940'>And</span> <span
  m='956330'>that's</span> <span m='956630'>equal</span> <span
  m='957020'>to</span> <span m='957830'>the</span> <span m='957920'>sum</span>
  <span m='958220'>from</span> <span m='958370'>n equals</span> <span
  m='958640'>0</span> <span m='958850'>to</span> <span
  m='958970'>infinity</span> <span m='960050'>of</span> <span
  m='960170'>1/2</span> <span m='960230'>times</span> <span m='960870'>z</span>
  <span m='961130'>to</span> <span m='961260'>the</span> <span
  m='961370'>minus</span> <span m='961760'>1--</span> <span
  m='962135'>just</span> <span m='962510'>combining</span> <span
  m='963050'>these</span> <span m='963290'>together--</span> <span
  m='964550'>to</span> <span m='964670'>the</span> <span m='964850'>n.</span>
  </p><p><span m='966130'>Now,</span> <span m='966710'>let</span> <span
  m='966950'>me</span> <span m='967070'>point</span> <span
  m='967340'>out,</span> <span m='967550'>incidentally--</span> <span
  m='968040'>and</span> <span m='968210'>I</span> <span m='968360'>think</span>
  <span m='968630'>that</span> <span m='968780'>by</span> <span
  m='968990'>now</span> <span m='970130'>you've</span> <span
  m='970340'>seen</span> <span m='970670'>this--</span> <span
  m='972350'>this</span> <span m='972770'>is</span> <span m='973190'>a</span>
  <span m='973280'>kind</span> <span m='973580'>of</span> <span
  m='973700'>sum,</span> <span m='974380'>this</span> <span
  m='974540'>geometric</span> <span m='975110'>series</span> <span
  m='975650'>is</span> <span m='975800'>a</span> <span m='975860'>kind</span>
  <span m='976130'>of</span> <span m='976190'>sum</span> <span
  m='977060'>that</span> <span m='977810'>comes</span> <span
  m='978050'>up</span> <span m='978200'>over</span> <span m='978560'>and</span>
  <span m='978650'>over</span> <span m='978890'>and</span> <span
  m='978980'>over</span> <span m='979280'>again</span> <span
  m='979860'>in</span> <span m='979970'>dealing</span> <span
  m='980510'>with</span> <span m='980630'>sequences.</span> <span
  m='981920'>And</span> <span m='982610'>it's</span> <span m='983060'>the</span>
  <span m='983180'>kind</span> <span m='983360'>of</span> <span
  m='983450'>summation</span> <span m='984170'>that</span> <span
  m='984830'>you</span> <span m='984980'>should</span> <span
  m='985310'>carry</span> <span m='985700'>around</span> <span
  m='985970'>in</span> <span m='986060'>your</span> <span m='986180'>hip</span>
  <span m='986360'>pocket.</span> <span m='987290'>That</span> <span
  m='987440'>is,</span> <span m='988160'>you</span> <span
  m='988280'>should</span> <span m='988790'>keep</span> <span
  m='989030'>in</span> <span m='989150'>mind,</span> <span
  m='989550'>because</span> <span m='989780'>it</span> <span
  m='989840'>keeps</span> <span m='990140'>coming</span> <span
  m='990500'>up</span> <span m='990620'>like</span> <span
  m='990830'>standard</span> <span m='991250'>integrals</span> <span
  m='991730'>do</span> <span m='992050'>in</span> <span m='992150'>the</span>
  <span m='992240'>continuous</span> <span m='992780'>time</span> <span
  m='993080'>case,</span> <span m='994070'>that</span> <span
  m='994210'>the</span> <span m='994310'>sum</span> <span m='994640'>from</span>
  <span m='994820'>0</span> <span m='995150'>to</span> <span
  m='995270'>infinity</span> <span m='995900'>of</span> <span
  m='996020'>a</span> <span m='996230'>to</span> <span m='996410'>the</span>
  <span m='996560'>n--</span> <span m='997410'>a</span> <span
  m='997840'>has</span> <span m='998270'>to</span> <span m='998390'>be</span>
  <span m='998450'>less</span> <span m='998690'>than</span> <span
  m='998840'>1</span> <span m='999020'>for</span> <span
  m='999200'>convergence--</span> <span m='1000190'>of</span> <span
  m='1000310'>a</span> <span m='1000520'>to</span> <span m='1000640'>the</span>
  <span m='1000820'>n</span> <span m='1001510'>is</span> <span
  m='1001660'>equal</span> <span m='1001960'>to</span> <span
  m='1002080'>1</span> <span m='1002395'>over 1</span> <span
  m='1002710'>minus</span> <span m='1003080'>a.</span> <span
  m='1004060'>Just</span> <span m='1004510'>store</span> <span
  m='1004870'>that</span> <span m='1005050'>away.</span> </p><p><span
  m='1006330'>Anyway,</span> <span m='1007530'>summing</span> <span
  m='1008040'>this,</span> <span m='1008980'>then,</span> <span
  m='1010090'>we</span> <span m='1010240'>end</span> <span m='1010480'>up</span>
  <span m='1010930'>with</span> <span m='1011710'>1</span> <span
  m='1011980'>over</span> <span m='1012220'>1</span> <span
  m='1012490'>minus</span> <span m='1012910'>this</span> <span
  m='1013180'>thing.</span> <span m='1014960'>So</span> <span
  m='1015670'>the</span> <span m='1015760'>Z-transform</span> <span
  m='1016690'>is</span> <span m='1016810'>1</span> <span m='1017080'>over</span>
  <span m='1017290'>1</span> <span m='1017500'>minus</span> <span
  m='1017860'>1/2</span> <span m='1018760'>times</span> <span
  m='1019190'>z</span> <span m='1019390'>to</span> <span m='1019540'>the</span>
  <span m='1019630'>minus</span> <span m='1020050'>1,</span> <span
  m='1021590'>which</span> <span m='1021760'>we</span> <span
  m='1021940'>can</span> <span m='1022090'>leave</span> <span
  m='1022330'>in</span> <span m='1022420'>this</span> <span
  m='1022630'>form.</span> <span m='1023020'>And</span> <span
  m='1023110'>sometimes,</span> <span m='1023680'>we</span> <span
  m='1023830'>will.</span> <span m='1024640'>Or,</span> <span
  m='1024940'>we</span> <span m='1025060'>can</span> <span
  m='1025210'>multiply</span> <span m='1026589'>numerator</span> <span
  m='1027130'>and</span> <span m='1027220'>denominator</span> <span
  m='1028270'>by</span> <span m='1028480'>z,</span> <span m='1029740'>in</span>
  <span m='1029829'>which</span> <span m='1030069'>case</span> <span
  m='1030400'>we</span> <span m='1030550'>have</span> <span m='1030790'>z</span>
  <span m='1031569'>divided</span> <span m='1032079'>by</span> <span
  m='1032770'>z</span> <span m='1033040'>minus</span> <span
  m='1033430'>1/2.</span> </p><p><span m='1037290'>Well,</span> <span
  m='1037680'>when</span> <span m='1037920'>does</span> <span
  m='1038099'>this</span> <span m='1038250'>converge?</span> <span
  m='1039690'>It</span> <span m='1039810'>converges</span> <span
  m='1041010'>when</span> <span m='1042210'>the</span> <span
  m='1042300'>magnitude</span> <span m='1043109'>of</span> <span
  m='1043200'>1/2</span> <span m='1043650'>times</span> <span
  m='1043940'>z</span> <span m='1044069'>to</span> <span m='1044160'>the</span>
  <span m='1044250'>minus</span> <span m='1044670'>1</span> <span
  m='1046020'>raised</span> <span m='1046349'>to</span> <span
  m='1046500'>the</span> <span m='1046680'>n</span> <span m='1047700'>is</span>
  <span m='1047910'>finite.</span> <span m='1049780'>And</span> <span
  m='1049930'>that</span> <span m='1050110'>requires</span> <span
  m='1051190'>that</span> <span m='1051400'>this</span> <span
  m='1051610'>thing</span> <span m='1051850'>that</span> <span
  m='1051970'>we're</span> <span m='1052090'>taking</span> <span
  m='1052750'>the</span> <span m='1052930'>absolute</span> <span
  m='1053410'>magnitude</span> <span m='1054070'>of</span> <span
  m='1055150'>be--</span> <span m='1056710'>raised</span> <span
  m='1057070'>to</span> <span m='1057190'>the</span> <span
  m='1057340'>n--</span> <span m='1058030'>be</span> <span
  m='1058630'>less</span> <span m='1059200'>than</span> <span
  m='1059440'>unity,</span> <span m='1060670'>or</span> <span
  m='1061240'>that</span> <span m='1061450'>implies</span> <span
  m='1062460'>that</span> <span m='1062650'>z,</span> <span
  m='1063400'>the</span> <span m='1063490'>magnitude</span> <span
  m='1064090'>of</span> <span m='1064180'>z,</span> <span
  m='1065020'>must</span> <span m='1065230'>be</span> <span
  m='1065410'>greater</span> <span m='1066250'>than</span> <span
  m='1066400'>1/2.</span> <span m='1068010'>The</span> <span
  m='1068100'>magnitude</span> <span m='1068670'>of</span> <span
  m='1068760'>z</span> <span m='1069930'>must</span> <span m='1070140'>be</span>
  <span m='1070320'>greater</span> <span m='1070680'>than</span> <span
  m='1070830'>1/2,</span> <span m='1071850'>or</span> <span
  m='1072690'>the</span> <span m='1072780'>magnitude</span> <span
  m='1073320'>of</span> <span m='1073410'>z</span> <span
  m='1073590'>minus</span> <span m='1074010'>z</span> <span
  m='1074130'>to</span> <span m='1074200'>the</span> <span
  m='1074280'>minus</span> <span m='1074610'>1</span> <span m='1075000'>must
  be</span> <span m='1075120'>less</span> <span m='1075390'>than</span> <span
  m='1075540'>two.</span> <span m='1076590'>Magnitude</span> <span
  m='1076845'>z</span> <span m='1077100'>to</span> <span m='1077190'>the</span>
  <span m='1077520'>minus</span> <span m='1077850'>1</span> <span
  m='1078300'>less than</span> <span m='1078450'>two,</span> <span
  m='1078840'>or</span> <span m='1079650'>the</span> <span
  m='1079740'>magnitude</span> <span m='1080310'>of</span> <span
  m='1080400'>z</span> <span m='1081060'>greater</span> <span
  m='1081390'>than</span> <span m='1081570'>1/2.</span> <span
  m='1082530'>And</span> <span m='1082770'>under</span> <span
  m='1082980'>those</span> <span m='1083250'>conditions,</span> <span
  m='1083715'>the</span> <span m='1084180'>Z-transform</span> <span
  m='1085200'>will</span> <span m='1085320'>converge.</span> </p><p><span
  m='1088020'>Now,</span> <span m='1088500'>for</span> <span
  m='1088650'>this</span> <span m='1088860'>example,</span> <span
  m='1089880'>does</span> <span m='1090600'>the</span> <span
  m='1090720'>Fourier</span> <span m='1091200'>transform</span> <span
  m='1092490'>exist?</span> <span m='1093270'>Does</span> <span
  m='1093420'>the</span> <span m='1093510'>Fourier</span> <span
  m='1093810'>transform</span> <span m='1094440'>converge?</span> <span
  m='1095700'>How</span> <span m='1095790'>do</span> <span m='1095880'>we</span>
  <span m='1096060'>answer</span> <span m='1096390'>that?</span> <span
  m='1096940'>Well,</span> <span m='1097560'>the</span> <span
  m='1097750'>Fourier</span> <span m='1098010'>transform</span> <span
  m='1098670'>converges</span> <span m='1099990'>if</span> <span
  m='1101070'>the</span> <span m='1101370'>convergence</span> <span
  m='1102120'>of</span> <span m='1102210'>the</span> <span
  m='1102600'>Z-transform</span> <span m='1103680'>includes</span> <span
  m='1104640'>the</span> <span m='1104760'>magnitude</span> <span
  m='1105330'>of</span> <span m='1105420'>z</span> <span
  m='1105870'>equal</span> <span m='1106230'>to</span> <span
  m='1106390'>1.</span> <span m='1107820'>Does</span> <span
  m='1108060'>it?</span> <span m='1108870'>Sure</span> <span
  m='1109140'>it</span> <span m='1109260'>does.</span> <span
  m='1109980'>The</span> <span m='1110070'>magnitude</span> <span
  m='1110640'>of</span> <span m='1110730'>z</span> <span m='1111240'>must</span>
  <span m='1111450'>be</span> <span m='1111570'>greater</span> <span
  m='1111900'>than</span> <span m='1112080'>1/2</span> <span
  m='1112620'>for</span> <span m='1112770'>convergence</span> <span
  m='1113340'>of</span> <span m='1113430'>the</span> <span
  m='1113730'>Z-transform.</span> <span m='1114830'>That</span> <span
  m='1114990'>includes</span> <span m='1115500'>the</span> <span
  m='1115590'>magnitude</span> <span m='1116130'>of</span> <span
  m='1116250'>z</span> <span m='1116640'>equal</span> <span
  m='1116940'>to</span> <span m='1117090'>1.</span> <span
  m='1117940'>Therefore,</span> <span m='1118410'>for</span> <span
  m='1118560'>this</span> <span m='1118740'>sequence,</span> <span
  m='1119370'>the</span> <span m='1119890'>Fourier</span> <span
  m='1119990'>transform</span> <span m='1121170'>converges.</span> </p><p><span
  m='1122430'>We</span> <span m='1122520'>had</span> <span
  m='1122640'>already</span> <span m='1122910'>decided</span> <span
  m='1123390'>that</span> <span m='1123570'>before,</span> <span
  m='1123960'>of</span> <span m='1124050'>course.</span> <span
  m='1124470'>That</span> <span m='1124620'>is</span> <span
  m='1125970'>obviously</span> <span m='1126450'>a</span> <span
  m='1126480'>better</span> <span m='1126720'>turnout</span> <span
  m='1127140'>that</span> <span m='1127320'>way</span> <span
  m='1127800'>this</span> <span m='1127980'>time</span> <span
  m='1128280'>also.</span> <span m='1129480'>But</span> <span
  m='1130470'>an</span> <span m='1130590'>important</span> <span
  m='1131160'>notion,</span> <span m='1131780'>then,</span> <span
  m='1131970'>is</span> <span m='1132150'>interpreting</span> <span
  m='1133320'>the</span> <span m='1133440'>existence</span> <span
  m='1134040'>of</span> <span m='1134100'>the</span> <span
  m='1134220'>Fourier</span> <span m='1134670'>transform</span> <span
  m='1135480'>in</span> <span m='1135630'>terms</span> <span
  m='1136140'>of</span> <span m='1136950'>the</span> <span
  m='1137070'>region</span> <span m='1137490'>of</span> <span
  m='1137610'>convergence</span> <span m='1139140'>of</span> <span
  m='1139620'>the</span> <span m='1139830'>Z-transform.</span> <span
  m='1141900'>This</span> <span m='1142320'>then</span> <span
  m='1142560'>defines</span> <span m='1143100'>the</span> <span
  m='1143220'>region</span> <span m='1143550'>of</span> <span
  m='1143670'>convergence,</span> <span m='1144630'>the</span> <span
  m='1144750'>set</span> <span m='1145020'>of</span> <span
  m='1145080'>values</span> <span m='1145590'>of</span> <span
  m='1145680'>z</span> <span m='1146580'>for</span> <span
  m='1146730'>which</span> <span m='1147270'>the</span> <span
  m='1147390'>Z-transform</span> <span m='1148590'>converges.</span>
  </p><p><span m='1151330'>Another</span> <span m='1152420'>interesting</span>
  <span m='1152960'>observation</span> <span m='1153740'>about</span> <span
  m='1154040'>this</span> <span m='1154250'>example</span> <span
  m='1155690'>is</span> <span m='1156560'>that</span> <span
  m='1157040'>we</span> <span m='1157250'>ended</span> <span
  m='1157580'>up</span> <span m='1158030'>with</span> <span m='1158470'>a</span>
  <span m='1158560'>Z-transform</span> <span m='1160190'>that</span> <span
  m='1160490'>is</span> <span m='1160670'>a</span> <span
  m='1160760'>ratio</span> <span m='1161240'>of</span> <span
  m='1161300'>polynomials.</span> <span m='1163545'>In</span> <span
  m='1163860'>this</span> <span m='1164090'>case,</span> <span
  m='1164420'>z</span> <span m='1164570'>to</span> <span m='1164690'>the</span>
  <span m='1164790'>minus</span> <span m='1165190'>1</span> <span
  m='1165510'>or,</span> <span m='1165830'>If</span> <span m='1165950'>we</span>
  <span m='1166100'>rewrite</span> <span m='1166580'>it,</span> <span
  m='1167110'>a</span> <span m='1167180'>ratio</span> <span
  m='1167600'>of</span> <span m='1167660'>polynomials</span> <span
  m='1168830'>in</span> <span m='1169010'>z.</span> <span m='1169970'>And</span>
  <span m='1170600'>that's</span> <span m='1170810'>an</span> <span
  m='1170900'>important</span> <span m='1171320'>observation.</span> <span
  m='1172580'>In</span> <span m='1172730'>fact,</span> <span
  m='1174680'>it</span> <span m='1175040'>is</span> <span m='1175220'>a</span>
  <span m='1175280'>consequence</span> <span m='1175970'>of</span> <span
  m='1176030'>the</span> <span m='1176150'>fact</span> <span
  m='1176510'>that</span> <span m='1176600'>we're</span> <span
  m='1176750'>talking</span> <span m='1177170'>about</span> <span
  m='1177440'>the</span> <span m='1177530'>Z-transform</span> <span
  m='1178610'>of</span> <span m='1178730'>an</span> <span
  m='1178820'>exponential</span> <span m='1179810'>sequence.</span> <span
  m='1181330'>Any</span> <span m='1181550'>exponential</span> <span
  m='1182210'>sequence</span> <span m='1183140'>will</span> <span
  m='1183320'>have</span> <span m='1183550'>a</span> <span
  m='1183590'>Z-transform</span> <span m='1184560'>that's</span> <span
  m='1184730'>a</span> <span m='1184790'>ratio</span> <span
  m='1185180'>of</span> <span m='1185270'>polynomials</span> <span
  m='1186080'>in</span> <span m='1186200'>z.</span> </p><p><span
  m='1187550'>Furthermore,</span> <span m='1188390'>any</span> <span
  m='1188600'>sequence</span> <span m='1189170'>that's</span> <span
  m='1189380'>a</span> <span m='1189440'>sum</span> <span m='1189770'>of</span>
  <span m='1189860'>exponentials</span> <span m='1192260'>will</span> <span
  m='1192440'>have</span> <span m='1192650'>a</span> <span
  m='1192680'>Z-transform</span> <span m='1193850'>that's</span> <span
  m='1194030'>a</span> <span m='1194090'>ratio</span> <span
  m='1194480'>of</span> <span m='1194540'>polynomials</span> <span
  m='1195350'>in</span> <span m='1195470'>z,</span> <span
  m='1196250'>since</span> <span m='1196490'>the</span> <span
  m='1196580'>Z-transform</span> <span m='1197340'>of</span> <span
  m='1197390'>a</span> <span m='1197450'>sum</span> <span m='1197750'>is</span>
  <span m='1197870'>the</span> <span m='1197960'>sum</span> <span
  m='1198170'>of</span> <span m='1198230'>the</span> <span
  m='1198320'>Z-transforms,</span> <span m='1199340'>and</span> <span
  m='1199430'>the</span> <span m='1199490'>sum</span> <span
  m='1199790'>of</span> <span m='1199940'>a</span> <span
  m='1200030'>ratio</span> <span m='1200420'>of</span> <span
  m='1200480'>polynomials</span> <span m='1201290'>is</span> <span
  m='1201410'>a</span> <span m='1201470'>ratio</span> <span
  m='1201860'>of</span> <span m='1201920'>polynomials</span> <span
  m='1202670'>and</span> <span m='1202760'>all</span> <span
  m='1202910'>that.</span> <span m='1203670'>But</span> <span
  m='1203750'>basically,</span> <span m='1204290'>the</span> <span
  m='1204380'>point</span> <span m='1204680'>to</span> <span
  m='1204800'>remember</span> <span m='1206180'>is</span> <span
  m='1206390'>that</span> <span m='1207070'>sums</span> <span
  m='1207530'>of</span> <span m='1207650'>exponentials</span> <span
  m='1208536'>as</span> <span m='1208980'>sequences</span> <span
  m='1210410'>result</span> <span m='1211070'>in</span> <span
  m='1211550'>Z-transforms</span> <span m='1213050'>that</span> <span
  m='1213200'>are</span> <span m='1213290'>ratios</span> <span
  m='1213860'>of</span> <span m='1213920'>polynomials</span> <span
  m='1214880'>in</span> <span m='1215060'>z,</span> <span m='1215780'>or</span>
  <span m='1216080'>in</span> <span m='1216170'>z</span> <span
  m='1216380'>to</span> <span m='1216470'>the</span> <span
  m='1216560'>minus</span> <span m='1216950'>1.</span> </p><p><span
  m='1219200'>Well,</span> <span m='1220100'>for</span> <span
  m='1221000'>those</span> <span m='1221270'>class</span> <span
  m='1222050'>of</span> <span m='1222800'>sequences,</span> <span
  m='1223640'>which,</span> <span m='1223850'>in</span> <span
  m='1223940'>fact,</span> <span m='1224240'>are</span> <span
  m='1224300'>most</span> <span m='1224600'>of</span> <span
  m='1224660'>the</span> <span m='1224750'>sequences</span> <span
  m='1225410'>we're</span> <span m='1225530'>going</span> <span
  m='1225740'>to</span> <span m='1225830'>be</span> <span
  m='1225950'>talking</span> <span m='1226400'>about</span> <span
  m='1226670'>in</span> <span m='1226760'>these</span> <span
  m='1226970'>lectures,</span> <span m='1228470'>it's</span> <span
  m='1228620'>convenient</span> <span m='1229850'>to</span> <span
  m='1231790'>look</span> <span m='1232180'>at</span> <span
  m='1233050'>the</span> <span m='1233170'>Z-transform</span> <span
  m='1234940'>graphically,</span> <span m='1236380'>in</span> <span
  m='1236500'>terms</span> <span m='1237010'>of</span> <span
  m='1237160'>a</span> <span m='1237250'>plot</span> <span m='1237760'>in</span>
  <span m='1237850'>the</span> <span m='1239650'>z-plane.</span> <span
  m='1241750'>So</span> <span m='1242290'>I've</span> <span
  m='1242440'>indicated</span> <span m='1243040'>here</span> <span
  m='1244060'>the</span> <span m='1244180'>z-plane.</span> <span
  m='1247480'>This</span> <span m='1247740'>is</span> <span
  m='1248340'>the</span> <span m='1248460'>real</span> <span
  m='1248700'>part</span> <span m='1249000'>of</span> <span
  m='1249120'>z,</span> <span m='1249720'>this</span> <span
  m='1249930'>axis.</span> <span m='1251370'>This</span> <span
  m='1251580'>axis</span> <span m='1252030'>is</span> <span
  m='1252150'>the</span> <span m='1252270'>imaginary</span> <span
  m='1252900'>part</span> <span m='1253200'>of</span> <span
  m='1253320'>z.</span> <span m='1254580'>And</span> <span
  m='1255030'>I've</span> <span m='1255210'>drawn</span> <span
  m='1255540'>a</span> <span m='1255600'>circle,</span> <span
  m='1256860'>which</span> <span m='1257130'>I've</span> <span
  m='1257250'>called</span> <span m='1257970'>the</span> <span
  m='1258090'>unit</span> <span m='1258420'>circle,</span> <span
  m='1259800'>which</span> <span m='1260340'>is</span> <span
  m='1260910'>convenient</span> <span m='1261480'>to</span> <span
  m='1261600'>focus</span> <span m='1262110'>on.</span> <span
  m='1262680'>It's</span> <span m='1263340'>the</span> <span
  m='1263430'>circle</span> <span m='1263880'>in</span> <span
  m='1264000'>the</span> <span m='1264090'>z-plane</span> <span
  m='1264720'>for</span> <span m='1264870'>which</span> <span
  m='1265080'>the</span> <span m='1265200'>magnitude</span> <span
  m='1265740'>of</span> <span m='1265860'>z</span> <span m='1266310'>is</span>
  <span m='1266490'>equal</span> <span m='1266760'>to</span> <span
  m='1266880'>1.</span> </p><p><span m='1268200'>What's</span> <span
  m='1268440'>important</span> <span m='1268860'>about</span> <span
  m='1269100'>the</span> <span m='1269190'>magnitude</span> <span
  m='1269455'>of</span> <span m='1269720'>z</span> <span
  m='1269880'>equal</span> <span m='1270180'>to</span> <span
  m='1270330'>1?</span> <span m='1271110'>Well,</span> <span
  m='1271530'>it's</span> <span m='1271710'>on</span> <span
  m='1271980'>that</span> <span m='1272220'>circle,</span> <span
  m='1273490'>when</span> <span m='1273510'>we</span> <span
  m='1273600'>look</span> <span m='1273780'>at</span> <span
  m='1273870'>the</span> <span m='1273960'>Z-transform</span> <span
  m='1274710'>on</span> <span m='1274950'>that</span> <span
  m='1275130'>circle,</span> <span m='1275670'>that</span> <span
  m='1275790'>we</span> <span m='1275940'>see</span> <span
  m='1276150'>the</span> <span m='1276240'>Fourier</span> <span
  m='1276690'>transform.</span> <span m='1277770'>So</span> <span
  m='1278220'>it's</span> <span m='1278430'>often</span> <span
  m='1278760'>convenient</span> <span m='1280410'>to</span> <span
  m='1280530'>make</span> <span m='1280770'>reference</span> <span
  m='1281790'>to</span> <span m='1281910'>the</span> <span
  m='1282030'>unit</span> <span m='1282330'>circle</span> <span
  m='1282930'>in</span> <span m='1283050'>the</span> <span
  m='1283110'>z-plane</span> <span m='1284160'>corresponding</span> <span
  m='1284970'>to</span> <span m='1285090'>the</span> <span
  m='1285660'>place</span> <span m='1285990'>in</span> <span
  m='1286080'>the</span> <span m='1286170'>z-plane</span> <span
  m='1287340'>where</span> <span m='1287850'>the</span> <span
  m='1288000'>Z-transform</span> <span m='1288870'>is</span> <span
  m='1288960'>equal</span> <span m='1289230'>to</span> <span
  m='1289350'>the</span> <span m='1289420'>Fourier</span> <span
  m='1289960'>transform.</span> </p><p><span m='1292580'>When</span> <span
  m='1292760'>we</span> <span m='1292880'>have</span> <span m='1293570'>a</span>
  <span m='1293660'>Z-transform</span> <span m='1295550'>that</span> <span
  m='1295850'>is</span> <span m='1296540'>a</span> <span
  m='1296600'>ratio</span> <span m='1297110'>of</span> <span
  m='1297200'>polynomials</span> <span m='1298100'>in</span> <span
  m='1298250'>z,</span> <span m='1299750'>it's</span> <span
  m='1299930'>convenient</span> <span m='1301190'>to</span> <span
  m='1302270'>represent</span> <span m='1302930'>it</span> <span
  m='1303290'>in</span> <span m='1303440'>terms</span> <span
  m='1304070'>of</span> <span m='1304700'>the</span> <span
  m='1304850'>roots</span> <span m='1305360'>of</span> <span
  m='1305480'>the</span> <span m='1305570'>numerator</span> <span
  m='1306110'>polynomial</span> <span m='1308080'>and</span> <span
  m='1308350'>the</span> <span m='1308440'>roots</span> <span
  m='1308710'>of</span> <span m='1308770'>the</span> <span
  m='1308920'>denominator</span> <span m='1309580'>polynomial.</span> <span
  m='1311320'>The</span> <span m='1311410'>roots</span> <span
  m='1311680'>of</span> <span m='1311740'>the</span> <span
  m='1311860'>numerator</span> <span m='1312340'>polynomial</span> <span
  m='1313930'>we'll</span> <span m='1314620'>refer</span> <span
  m='1315040'>to</span> <span m='1315880'>as</span> <span m='1316270'>the</span>
  <span m='1316420'>zeros</span> <span m='1317320'>of</span> <span
  m='1317440'>the</span> <span m='1317770'>Z-transform.</span> <span
  m='1318910'>They're</span> <span m='1319300'>those</span> <span
  m='1319600'>values</span> <span m='1320140'>of</span> <span
  m='1320260'>z</span> <span m='1321250'>for</span> <span
  m='1321430'>which</span> <span m='1321940'>the</span> <span
  m='1322060'>Z-transform</span> <span m='1322900'>is</span> <span
  m='1322990'>going</span> <span m='1323260'>to</span> <span
  m='1323350'>be</span> <span m='1323470'>zero.</span> <span
  m='1325570'>And</span> <span m='1325710'>the</span> <span
  m='1325800'>roots</span> <span m='1326070'>of</span> <span
  m='1326130'>the</span> <span m='1326250'>denominator</span> <span
  m='1326940'>polynomial</span> <span m='1328100'>we'll</span> <span
  m='1328230'>refer</span> <span m='1328590'>to</span> <span
  m='1328770'>as</span> <span m='1328890'>the</span> <span
  m='1329010'>poles</span> <span m='1329400'>of</span> <span
  m='1329490'>the</span> <span m='1329820'>Z-transform.</span> <span
  m='1331320'>Those</span> <span m='1331590'>are</span> <span
  m='1331650'>the</span> <span m='1331770'>values</span> <span
  m='1332280'>of</span> <span m='1332400'>z</span> <span m='1332940'>at</span>
  <span m='1333060'>which</span> <span m='1333480'>the</span> <span
  m='1333600'>Z-transform</span> <span m='1334470'>blows</span> <span
  m='1334830'>up,</span> <span m='1336000'>just</span> <span
  m='1336270'>like</span> <span m='1336510'>poles</span> <span
  m='1336840'>and</span> <span m='1336960'>zeros</span> <span
  m='1337870'>of</span> <span m='1338040'>the</span> <span
  m='1338130'>Laplace</span> <span m='1338580'>transform</span> <span
  m='1339840'>in</span> <span m='1339930'>the</span> <span
  m='1339990'>continuous</span> <span m='1340590'>time</span> <span
  m='1340890'>case.</span> </p><p><span m='1342180'>We'll</span> <span
  m='1342330'>denote</span> <span m='1342840'>in</span> <span
  m='1342990'>the</span> <span m='1343080'>z-plane</span> <span
  m='1344180'>roots,</span> <span m='1345120'>the</span> <span
  m='1345450'>zeros,</span> <span m='1346860'>by</span> <span
  m='1348330'>a</span> <span m='1348390'>circle,</span> <span
  m='1350710'>and</span> <span m='1351330'>we'll</span> <span
  m='1351570'>denote</span> <span m='1352290'>the</span> <span
  m='1352410'>poles</span> <span m='1353820'>by</span> <span
  m='1354780'>a</span> <span m='1354840'>cross.</span> <span
  m='1356680'>So</span> <span m='1357360'>we</span> <span
  m='1357510'>have,</span> <span m='1357750'>for</span> <span
  m='1357900'>that</span> <span m='1358110'>particular</span> <span
  m='1358650'>example,</span> <span m='1359400'>a</span> <span
  m='1359490'>zero</span> <span m='1359910'>at</span> <span
  m='1360000'>the</span> <span m='1360150'>origin,</span> <span
  m='1361360'>since</span> <span m='1361590'>the</span> <span
  m='1361680'>numerator</span> <span m='1362130'>polynomial</span> <span
  m='1362880'>was</span> <span m='1363000'>simply</span> <span
  m='1363420'>z,</span> <span m='1364740'>and</span> <span m='1365280'>we</span>
  <span m='1365460'>have</span> <span m='1365640'>a</span> <span
  m='1365700'>pole</span> <span m='1366450'>at</span> <span m='1366960'>z</span>
  <span m='1367230'>equal</span> <span m='1367530'>to</span> <span
  m='1367710'>1/2.</span> <span m='1370610'>Well,</span> <span
  m='1371030'>what</span> <span m='1371240'>else</span> <span
  m='1371480'>do</span> <span m='1371600'>we</span> <span
  m='1371690'>know</span> <span m='1371900'>about</span> <span
  m='1372170'>this</span> <span m='1372340'>Z-transform?</span> <span
  m='1373610'>We</span> <span m='1373790'>know</span> <span
  m='1374330'>that</span> <span m='1375290'>the</span> <span
  m='1375410'>Z-transform</span> <span m='1376220'>doesn't</span> <span
  m='1376700'>exist</span> <span m='1377630'>for</span> <span
  m='1377840'>all</span> <span m='1378020'>values</span> <span
  m='1378530'>of</span> <span m='1378620'>z.</span> </p><p><span
  m='1379580'>In</span> <span m='1379700'>particular,</span> <span
  m='1380990'>for</span> <span m='1381140'>convergence</span> <span
  m='1381980'>we</span> <span m='1382190'>require</span> <span
  m='1382730'>that</span> <span m='1382880'>the</span> <span
  m='1382970'>magnitude</span> <span m='1383540'>of</span> <span
  m='1383630'>z</span> <span m='1384140'>is</span> <span
  m='1384320'>greater</span> <span m='1384650'>than</span> <span
  m='1384800'>1/2.</span> <span m='1386480'>So</span> <span
  m='1386930'>I've</span> <span m='1387140'>indicated</span> <span
  m='1388640'>that</span> <span m='1388880'>region</span> <span
  m='1389960'>in</span> <span m='1390110'>the</span> <span
  m='1390200'>z-plane,</span> <span m='1391760'>with</span> <span
  m='1392090'>these</span> <span m='1392240'>slanted</span> <span
  m='1392780'>lines,</span> <span m='1395280'>the</span> <span
  m='1395400'>region</span> <span m='1395790'>of</span> <span
  m='1395880'>convergence</span> <span m='1396570'>for</span> <span
  m='1396690'>this</span> <span m='1396840'>particular</span> <span
  m='1397350'>example</span> <span m='1398810'>are</span> <span
  m='1398970'>those</span> <span m='1399300'>values</span> <span
  m='1399810'>of</span> <span m='1399900'>z</span> <span m='1400800'>that</span>
  <span m='1400920'>lie</span> <span m='1401310'>outside</span> <span
  m='1401910'>the</span> <span m='1402030'>circle</span> <span
  m='1402780'>that's</span> <span m='1403380'>bounded</span> <span
  m='1404040'>by</span> <span m='1404250'>the</span> <span
  m='1404370'>pole</span> <span m='1404760'>at z</span> <span
  m='1404940'>equal</span> <span m='1405300'>to</span> <span
  m='1405450'>1/2.</span> <span m='1406020'>And</span> <span
  m='1406110'>we'll</span> <span m='1406230'>see</span> <span
  m='1406440'>that</span> <span m='1406590'>that</span> <span
  m='1407310'>is,</span> <span m='1407490'>in</span> <span
  m='1407580'>fact,</span> <span m='1408040'>the</span> <span
  m='1408140'>way</span> <span m='1408330'>regions</span> <span
  m='1408810'>of</span> <span m='1408900'>convergences</span> <span
  m='1410490'>tend</span> <span m='1410730'>to</span> <span
  m='1410850'>go.</span> <span m='1412320'>They'll</span> <span
  m='1412500'>tend</span> <span m='1412770'>to</span> <span
  m='1412890'>be</span> <span m='1413070'>outside</span> <span
  m='1413610'>and</span> <span m='1413700'>inside</span> <span
  m='1414510'>poles.</span> </p><p><span m='1415620'>So</span> <span
  m='1416610'>the</span> <span m='1416700'>important</span> <span
  m='1417360'>aspects</span> <span m='1417930'>of</span> <span
  m='1417990'>this</span> <span m='1418170'>picture,</span> <span
  m='1418860'>there</span> <span m='1419250'>are</span> <span
  m='1419430'>the</span> <span m='1419550'>zeroes</span> <span
  m='1420150'>and</span> <span m='1420240'>the</span> <span
  m='1420330'>poles,</span> <span m='1422280'>there's</span> <span
  m='1422490'>the</span> <span m='1422610'>unit</span> <span
  m='1422910'>circle</span> <span m='1424140'>where</span> <span
  m='1424350'>the</span> <span m='1424470'>Z-transform</span> <span
  m='1425310'>is</span> <span m='1425430'>equal</span> <span
  m='1425670'>to</span> <span m='1425790'>the</span> <span
  m='1425930'>Fourier</span> <span m='1426330'>transform,</span> <span
  m='1427700'>and</span> <span m='1427900'>there's</span> <span
  m='1428190'>the</span> <span m='1428310'>region</span> <span
  m='1428640'>of</span> <span m='1428760'>convergence,</span> <span
  m='1429900'>which</span> <span m='1430110'>tells</span> <span
  m='1430410'>us</span> <span m='1430560'>where</span> <span
  m='1431040'>in</span> <span m='1431160'>the</span> <span
  m='1431250'>z-plane</span> <span m='1432450'>the</span> <span
  m='1432540'>Z-transform</span> <span m='1433740'>makes</span> <span
  m='1433980'>sense.</span> <span m='1436880'>All</span> <span
  m='1437000'>right.</span> <span m='1437350'>Let's</span> <span
  m='1438330'>try</span> <span m='1438570'>another</span> <span
  m='1438840'>example.</span> </p><p><span m='1440850'>Let's</span> <span
  m='1441390'>take</span> <span m='1441810'>the</span> <span
  m='1441960'>example</span> <span m='1442830'>of</span> <span
  m='1444330'>x</span> <span m='1444600'>of</span> <span m='1444750'>n</span>
  <span m='1445170'>equal</span> <span m='1445500'>to</span> <span
  m='1445620'>minus</span> <span m='1446100'>1/2</span> <span
  m='1446490'>to</span> <span m='1446640'>the</span> <span m='1446820'>n</span>
  <span m='1447615'>u</span> <span m='1447990'>of</span> <span
  m='1448620'>minus</span> <span m='1449100'>n</span> <span
  m='1449340'>minus</span> <span m='1449790'>1.</span> <span
  m='1451000'>Now,</span> <span m='1451350'>you</span> <span
  m='1451500'>saw</span> <span m='1451740'>that</span> <span
  m='1451950'>sequence</span> <span m='1452520'>a</span> <span
  m='1452580'>couple</span> <span m='1452880'>of</span> <span
  m='1452970'>lectures</span> <span m='1453420'>ago.</span> <span
  m='1455470'>It's</span> <span m='1455650'>a</span> <span
  m='1455710'>sequence</span> <span m='1456790'>that</span> <span
  m='1457720'>is</span> <span m='1458230'>like</span> <span
  m='1458500'>1/2</span> <span m='1458890'>to</span> <span
  m='1459040'>the</span> <span m='1459220'>n,</span> <span
  m='1460120'>but</span> <span m='1460300'>not</span> <span
  m='1460810'>for</span> <span m='1461200'>positive</span> <span
  m='1461830'>values</span> <span m='1462310'>of</span> <span
  m='1462450'>n,</span> <span m='1463180'>but</span> <span
  m='1463330'>for</span> <span m='1463480'>negative</span> <span
  m='1463870'>values</span> <span m='1464320'>of</span> <span
  m='1464440'>n.</span> <span m='1464650'>In</span> <span
  m='1464740'>other</span> <span m='1464920'>words,</span> <span
  m='1465260'>it's</span> <span m='1465360'>zero</span> <span
  m='1465790'>for</span> <span m='1465940'>positive</span> <span
  m='1466420'>values</span> <span m='1466870'>of</span> <span
  m='1467010'>n,</span> <span m='1467770'>and</span> <span m='1467950'>it</span>
  <span m='1468040'>does</span> <span m='1468250'>something</span> <span
  m='1468640'>exponentially</span> <span m='1469630'>for</span> <span
  m='1469810'>negative</span> <span m='1470140'>values</span> <span
  m='1470620'>of</span> <span m='1470710'>n.</span> </p><p><span
  m='1473940'>If</span> <span m='1474690'>you</span> <span
  m='1475350'>evaluate</span> <span m='1476490'>the</span> <span
  m='1476580'>Z-transform</span> <span m='1477480'>sum--</span> <span
  m='1478230'>and</span> <span m='1478680'>I'll</span> <span
  m='1478800'>leave</span> <span m='1479040'>it</span> <span
  m='1479340'>to</span> <span m='1479460'>you</span> <span m='1479580'>to</span>
  <span m='1479700'>do</span> <span m='1479880'>this--</span> <span
  m='1480910'>then</span> <span m='1481230'>we</span> <span
  m='1481470'>end</span> <span m='1481680'>up</span> <span
  m='1481920'>with</span> <span m='1482220'>x</span> <span m='1482520'>of</span>
  <span m='1482640'>z,</span> <span m='1483090'>the Z-transform,</span> <span
  m='1484500'>is</span> <span m='1484650'>1</span> <span m='1484950'>over</span>
  <span m='1485520'>1</span> <span m='1485760'>minus</span> <span
  m='1486120'>1/2</span> <span m='1486810'>z</span> <span m='1486990'>to</span>
  <span m='1487090'>the</span> <span m='1487170'>minus</span> <span
  m='1487530'>1,</span> <span m='1488820'>just</span> <span
  m='1489000'>like</span> <span m='1489210'>we</span> <span
  m='1489300'>saw</span> <span m='1489570'>before.</span> <span
  m='1490150'>In</span> <span m='1490170'>fact,</span> <span
  m='1491110'>that's</span> <span m='1491220'>exactly</span> <span
  m='1491820'>the</span> <span m='1491910'>same</span> <span
  m='1492360'>expression</span> <span m='1493290'>as</span> <span
  m='1493470'>a</span> <span m='1493530'>ratio</span> <span
  m='1493920'>of</span> <span m='1493980'>polynomials</span> <span
  m='1495450'>that</span> <span m='1495570'>we</span> <span
  m='1495690'>saw</span> <span m='1495960'>before,</span> <span
  m='1497960'>which,</span> <span m='1498260'>of</span> <span
  m='1498320'>course,</span> <span m='1498590'>we</span> <span
  m='1498710'>can</span> <span m='1498890'>rewrite,</span> <span
  m='1500450'>as</span> <span m='1500630'>we</span> <span m='1500750'>did</span>
  <span m='1500930'>before,</span> <span m='1501590'>as</span> <span
  m='1501855'>z</span> <span m='1502120'>divided</span> <span
  m='1502610'>by</span> <span m='1504440'>z</span> <span
  m='1504650'>minus</span> <span m='1505040'>1/2.</span> </p><p><span
  m='1508050'>All</span> <span m='1508140'>right.</span> <span
  m='1508320'>Do</span> <span m='1508410'>you</span> <span
  m='1508530'>think</span> <span m='1508830'>that</span> <span
  m='1508980'>the</span> <span m='1509100'>Fourier</span> <span
  m='1509510'>transform</span> <span m='1510180'>of</span> <span
  m='1510270'>this</span> <span m='1510420'>sequence</span> <span
  m='1510900'>exists?</span> <span m='1513780'>Well,</span> <span
  m='1515750'>it's</span> <span m='1515950'>1/2</span> <span
  m='1516790'>to</span> <span m='1516940'>the</span> <span m='1517090'>n,</span>
  <span m='1518420'>which</span> <span m='1519070'>dies</span> <span
  m='1519430'>out</span> <span m='1519640'>for</span> <span
  m='1519790'>negative</span> <span m='1520210'>n--</span> <span
  m='1520680'>for</span> <span m='1520890'>positive</span> <span
  m='1521440'>n.</span> <span m='1521890'>But</span> <span
  m='1522070'>for</span> <span m='1522220'>negative</span> <span
  m='1522670'>n,</span> <span m='1522820'>that's</span> <span
  m='1523000'>a</span> <span m='1523060'>sequence</span> <span
  m='1523600'>that</span> <span m='1523690'>grows</span> <span
  m='1524080'>exponentially.</span> <span m='1525530'>So</span> <span
  m='1525700'>in</span> <span m='1525820'>fact,</span> <span
  m='1526400'>if</span> <span m='1526480'>you</span> <span
  m='1526630'>examine</span> <span m='1527110'>convergence</span> <span
  m='1527800'>of</span> <span m='1527920'>this,</span> <span
  m='1528840'>this</span> <span m='1529300'>sequence</span> <span
  m='1530020'>is</span> <span m='1530200'>not</span> <span
  m='1530440'>absolutely</span> <span m='1531040'>summable.</span> <span
  m='1531910'>The</span> <span m='1532030'>Fourier</span> <span
  m='1532360'>transform</span> <span m='1533020'>does</span> <span
  m='1533200'>not</span> <span m='1533440'>exist.</span> </p><p><span
  m='1536370'>What's</span> <span m='1537000'>the</span> <span
  m='1537360'>region</span> <span m='1537780'>of</span> <span
  m='1537870'>convergence</span> <span m='1538680'>of</span> <span
  m='1538770'>the</span> <span m='1538890'>Z-transform?</span> <span
  m='1540300'>Well,</span> <span m='1540720'>to</span> <span
  m='1540840'>decide</span> <span m='1541320'>that,</span> <span
  m='1542610'>we</span> <span m='1542790'>need</span> <span
  m='1543090'>to</span> <span m='1543240'>look</span> <span
  m='1543570'>at</span> <span m='1544500'>the</span> <span
  m='1544740'>sum</span> <span m='1545970'>of</span> <span
  m='1546270'>1/2</span> <span m='1546750'>times</span> <span
  m='1547070'>e</span> <span m='1547160'>to</span> <span m='1547230'>the</span>
  <span m='1547320'>minus</span> <span m='1547710'>1</span> <span
  m='1548250'>to</span> <span m='1548400'>the</span> <span m='1548590'>n,</span>
  <span m='1549390'>and</span> <span m='1549540'>ask</span> <span
  m='1549930'>for</span> <span m='1550170'>what</span> <span
  m='1550440'>values</span> <span m='1550980'>of</span> <span
  m='1551100'>z</span> <span m='1552330'>this</span> <span
  m='1553110'>sum</span> <span m='1554190'>is</span> <span
  m='1554430'>less</span> <span m='1554700'>than</span> <span
  m='1554850'>infinity.</span> <span m='1555490'>In</span> <span
  m='1555590'>other</span> <span m='1555630'>words,</span> <span
  m='1555810'>for</span> <span m='1555930'>what</span> <span
  m='1556110'>values</span> <span m='1556530'>of</span> <span
  m='1556650'>z</span> <span m='1556860'>that</span> <span
  m='1557040'>sum</span> <span m='1557310'>converges.</span> <span
  m='1558960'>And</span> <span m='1559530'>to</span> <span m='1559710'>do</span>
  <span m='1559950'>that,</span> <span m='1560910'>if</span> <span
  m='1561060'>this</span> <span m='1561240'>was</span> <span
  m='1561420'>a</span> <span m='1561480'>sum</span> <span
  m='1561900'>over</span> <span m='1562200'>positive</span> <span
  m='1562740'>values</span> <span m='1563250'>of</span> <span
  m='1563370'>n,</span> <span m='1564210'>then</span> <span
  m='1564390'>we</span> <span m='1564540'>would</span> <span
  m='1564690'>want</span> <span m='1564960'>the</span> <span
  m='1565080'>magnitude</span> <span m='1565680'>of</span> <span
  m='1565770'>this</span> <span m='1566820'>to</span> <span
  m='1566910'>be</span> <span m='1567840'>less</span> <span
  m='1568170'>than</span> <span m='1568350'>1.</span> <span
  m='1569440'>Since</span> <span m='1569580'>we're</span> <span
  m='1569700'>looking</span> <span m='1569970'>at</span> <span
  m='1570060'>this</span> <span m='1570240'>for</span> <span
  m='1570360'>negative</span> <span m='1570750'>values</span> <span
  m='1571230'>of</span> <span m='1571485'>n,</span> <span m='1572010'>we</span>
  <span m='1572100'>want</span> <span m='1572310'>the</span> <span
  m='1572430'>magnitude</span> <span m='1573000'>of</span> <span
  m='1573120'>this</span> <span m='1573690'>to</span> <span
  m='1573810'>be</span> <span m='1573930'>greater</span> <span
  m='1574350'>than</span> <span m='1574530'>1.</span> </p><p><span
  m='1576400'>And</span> <span m='1577020'>the</span> <span
  m='1577290'>conclusion</span> <span m='1578010'>is--</span> <span
  m='1578860'>and</span> <span m='1579270'>if</span> <span
  m='1579420'>you</span> <span m='1579480'>don't</span> <span
  m='1579690'>see</span> <span m='1579870'>this</span> <span
  m='1580050'>right</span> <span m='1580290'>away,</span> <span
  m='1580590'>you</span> <span m='1580710'>can</span> <span
  m='1580830'>just</span> <span m='1581070'>fiddle</span> <span
  m='1581340'>with</span> <span m='1581550'>it</span> <span
  m='1581640'>on</span> <span m='1581760'>the</span> <span
  m='1581850'>back</span> <span m='1582120'>of</span> <span
  m='1582210'>an</span> <span m='1582270'>envelope--</span> <span
  m='1583650'>that</span> <span m='1584550'>this</span> <span
  m='1584770'>converges</span> <span m='1586080'>provided</span> <span
  m='1586800'>that</span> <span m='1587880'>the</span> <span
  m='1587970'>magnitude</span> <span m='1588930'>of</span> <span
  m='1589110'>z</span> <span m='1590040'>is</span> <span m='1593628'>less</span>
  <span m='1594106'>than</span> <span m='1594584'>1/2.</span> <span
  m='1597930'>So</span> <span m='1598470'>we</span> <span m='1598620'>can</span>
  <span m='1598770'>look</span> <span m='1598950'>at</span> <span
  m='1599040'>this</span> <span m='1599220'>example</span> <span
  m='1600240'>in</span> <span m='1600360'>the</span> <span
  m='1600450'>z-plane,</span> <span m='1601530'>just</span> <span
  m='1601800'>as</span> <span m='1601920'>we</span> <span
  m='1602250'>looked</span> <span m='1602490'>at</span> <span
  m='1602550'>the</span> <span m='1602670'>previous</span> <span
  m='1603120'>example</span> <span m='1603990'>in</span> <span
  m='1604110'>the</span> <span m='1604170'>z-plane.</span> <span
  m='1605800'>We</span> <span m='1605940'>first</span> <span
  m='1606270'>of</span> <span m='1606420'>all</span> <span
  m='1606960'>have</span> <span m='1607560'>poles</span> <span
  m='1608010'>and</span> <span m='1608130'>zeroes.</span> <span
  m='1608970'>We</span> <span m='1609150'>have--</span> <span
  m='1610410'>well,</span> <span m='1610620'>where</span> <span
  m='1610800'>do</span> <span m='1610860'>we</span> <span
  m='1611010'>have</span> <span m='1611190'>a</span> <span
  m='1611250'>zero?</span> </p><p><span m='1611580'>We</span> <span
  m='1611730'>have</span> <span m='1611890'>a</span> <span
  m='1611930'>zero</span> <span m='1612910'>at</span> <span m='1613170'>z</span>
  <span m='1613440'>equals</span> <span m='1613750'>0.</span> <span
  m='1615490'>So</span> <span m='1615700'>that's</span> <span
  m='1616000'>here.</span> <span m='1618120'>We</span> <span
  m='1618270'>have</span> <span m='1618450'>a</span> <span
  m='1618780'>pole</span> <span m='1619230'>at z</span> <span
  m='1619440'>equal</span> <span m='1619800'>to</span> <span
  m='1619950'>1/2.</span> <span m='1621640'>And</span> <span
  m='1621760'>that's</span> <span m='1622030'>here.</span> <span
  m='1625040'>Just</span> <span m='1625670'>like</span> <span
  m='1626930'>in</span> <span m='1627050'>the</span> <span
  m='1627140'>previous</span> <span m='1627650'>example,</span> <span
  m='1629000'>the</span> <span m='1629120'>zero</span> <span
  m='1629450'>and</span> <span m='1629510'>the</span> <span
  m='1629600'>pole</span> <span m='1630020'>fall in</span> <span
  m='1630350'>exactly</span> <span m='1630800'>the</span> <span
  m='1630920'>same</span> <span m='1631190'>place.</span> <span
  m='1633030'>What's</span> <span m='1633260'>the</span> <span
  m='1633330'>region</span> <span m='1633660'>of</span> <span
  m='1633750'>convergence?</span> <span m='1634990'>Well,</span> <span
  m='1635370'>the</span> <span m='1635490'>region</span> <span
  m='1635790'>of</span> <span m='1635880'>convergence</span> <span
  m='1636750'>is</span> <span m='1636870'>for</span> <span
  m='1636990'>the</span> <span m='1637080'>magnitude</span> <span
  m='1637650'>of</span> <span m='1637750'>z</span> <span m='1638520'>less</span>
  <span m='1638790'>than</span> <span m='1638940'>1/2.</span> <span
  m='1640440'>And</span> <span m='1641220'>now,</span> <span
  m='1641580'>in</span> <span m='1641730'>this</span> <span
  m='1641970'>case,</span> <span m='1642870'>that's</span> <span
  m='1643440'>inside</span> <span m='1644940'>this</span> <span
  m='1645090'>circle,</span> <span m='1646110'>rather</span> <span
  m='1646500'>than</span> <span m='1646830'>in</span> <span
  m='1646980'>the</span> <span m='1647040'>previous</span> <span
  m='1647520'>case,</span> <span m='1648000'>where</span> <span
  m='1648210'>it</span> <span m='1648270'>was</span> <span
  m='1648450'>outside</span> <span m='1648930'>that</span> <span
  m='1649110'>circle.</span> <span m='1649980'>So</span> <span
  m='1650160'>the</span> <span m='1650250'>region</span> <span
  m='1650580'>of</span> <span m='1650670'>convergence</span> <span
  m='1651430'>now</span> <span m='1652740'>is</span> <span
  m='1653400'>the</span> <span m='1653520'>region</span> <span
  m='1655320'>that</span> <span m='1655710'>is</span> <span
  m='1656130'>inside</span> <span m='1657300'>the</span> <span
  m='1657390'>circle,</span> <span m='1658510'>which</span> <span
  m='1658620'>is</span> <span m='1658740'>bounded</span> <span
  m='1659550'>by</span> <span m='1659700'>that</span> <span
  m='1659900'>pole.</span> </p><p><span m='1664320'>All</span> <span
  m='1664380'>right.</span> <span m='1664630'>This</span> <span
  m='1664810'>raises</span> <span m='1665590'>an</span> <span
  m='1665710'>important</span> <span m='1666100'>point.</span> <span
  m='1668170'>Here</span> <span m='1668350'>we</span> <span
  m='1668500'>had</span> <span m='1668650'>an</span> <span
  m='1668740'>example</span> <span m='1669670'>where</span> <span
  m='1669850'>we</span> <span m='1669970'>got</span> <span m='1670360'>a</span>
  <span m='1670420'>Z-transform</span> <span m='1671230'>ratio</span> <span
  m='1671590'>of</span> <span m='1671650'>polynomials.</span> <span
  m='1673870'>The</span> <span m='1673990'>previous</span> <span
  m='1674530'>example,</span> <span m='1676100'>we</span> <span
  m='1676150'>got</span> <span m='1676750'>exactly</span> <span
  m='1677500'>the</span> <span m='1677620'>same</span> <span
  m='1678310'>ratio</span> <span m='1678820'>of</span> <span
  m='1678910'>polynomials.</span> <span m='1680980'>How</span> <span
  m='1681130'>did</span> <span m='1681250'>these</span> <span
  m='1681520'>two</span> <span m='1681730'>examples</span> <span
  m='1682330'>differ</span> <span m='1682750'>in</span> <span
  m='1682840'>terms</span> <span m='1683170'>of</span> <span
  m='1683260'>the</span> <span m='1683350'>Z-transform?</span> <span
  m='1684670'>They</span> <span m='1684850'>differed</span> <span
  m='1685630'>in</span> <span m='1685780'>terms</span> <span
  m='1686290'>of</span> <span m='1686530'>the</span> <span
  m='1686650'>region</span> <span m='1687010'>of</span> <span
  m='1687100'>convergence</span> <span m='1688270'>that</span> <span
  m='1688420'>we</span> <span m='1688570'>associate</span> <span
  m='1689230'>with</span> <span m='1689380'>the</span> <span
  m='1689470'>Z-transform.</span> <span m='1690760'>The</span> <span
  m='1690880'>other</span> <span m='1691060'>case,</span> <span
  m='1692000'>the</span> <span m='1692100'>region</span> <span
  m='1692260'>of</span> <span m='1692350'>convergence</span> <span
  m='1692890'>was</span> <span m='1693070'>outside</span> <span
  m='1693550'>this</span> <span m='1693700'>circle.</span> <span
  m='1694480'>In</span> <span m='1694600'>this</span> <span
  m='1694810'>case,</span> <span m='1695200'>the</span> <span
  m='1695290'>region</span> <span m='1695590'>of</span> <span
  m='1695650'>convergence</span> <span m='1696250'>is</span> <span
  m='1696370'>inside</span> <span m='1696760'>this</span> <span
  m='1696930'>circle.</span> </p><p><span m='1698260'>The</span> <span
  m='1698350'>ratio</span> <span m='1698800'>of</span> <span
  m='1698890'>polynomials</span> <span m='1699730'>for</span> <span
  m='1699820'>the</span> <span m='1699940'>Z-transforms</span> <span
  m='1700900'>is</span> <span m='1701080'>the</span> <span
  m='1701140'>same</span> <span m='1701500'>in</span> <span
  m='1701590'>both</span> <span m='1701860'>cases.</span> <span
  m='1702860'>It's</span> <span m='1702910'>the</span> <span
  m='1703000'>region</span> <span m='1703330'>of</span> <span
  m='1703420'>convergence</span> <span m='1704050'>that's</span> <span
  m='1704200'>different.</span> <span m='1705430'>So</span> <span
  m='1706090'>an</span> <span m='1706210'>important</span> <span
  m='1707080'>point</span> <span m='1707440'>to</span> <span
  m='1707560'>keep</span> <span m='1707860'>in</span> <span
  m='1707950'>mind</span> <span m='1708910'>is</span> <span
  m='1709060'>that</span> <span m='1709210'>the</span> <span
  m='1709330'>Z-transform</span> <span m='1710890'>is</span> <span
  m='1711040'>not</span> <span m='1711310'>specified</span> <span
  m='1712300'>just</span> <span m='1712690'>by</span> <span
  m='1712960'>the</span> <span m='1713050'>function</span> <span
  m='1713500'>of</span> <span m='1713620'>z,</span> <span
  m='1714790'>it's</span> <span m='1714970'>also</span> <span
  m='1715570'>specified--</span> <span m='1715975'>it</span> <span
  m='1716380'>has</span> <span m='1716590'>to</span> <span
  m='1716710'>have</span> <span m='1716920'>attached</span> <span
  m='1717370'>to</span> <span m='1717550'>it</span> <span m='1717610'>a</span>
  <span m='1717640'>little</span> <span m='1717880'>tag</span> <span
  m='1718930'>that</span> <span m='1719080'>tells</span> <span
  m='1719530'>you</span> <span m='1720100'>for</span> <span
  m='1720280'>what</span> <span m='1720550'>values</span> <span
  m='1721090'>of</span> <span m='1721180'>z</span> <span m='1721780'>it's</span>
  <span m='1721960'>legitimate</span> <span m='1722500'>to</span> <span
  m='1722620'>look</span> <span m='1722830'>at</span> <span
  m='1722890'>that</span> <span m='1723070'>expression.</span> </p><p><span
  m='1725050'>So</span> <span m='1725260'>it's</span> <span
  m='1725370'>specified</span> <span m='1726310'>by</span> <span
  m='1726610'>the</span> <span m='1726730'>ratio</span> <span
  m='1727060'>of</span> <span m='1727120'>polynomials,</span> <span
  m='1728260'>and</span> <span m='1728440'>also</span> <span
  m='1729520'>by</span> <span m='1730210'>the</span> <span
  m='1730330'>region</span> <span m='1730690'>of</span> <span
  m='1730780'>convergence</span> <span m='1731560'>of</span> <span
  m='1731680'>the</span> <span m='1732010'>Z-transform.</span> <span
  m='1733480'>So</span> <span m='1733840'>here,</span> <span
  m='1734110'>for</span> <span m='1734320'>example,</span> <span
  m='1735040'>that's</span> <span m='1735310'>the</span> <span
  m='1735400'>ratio</span> <span m='1735790'>of</span> <span
  m='1735850'>polynomials,</span> <span m='1736810'>and</span> <span
  m='1736930'>that's</span> <span m='1737170'>the</span> <span
  m='1737290'>Z-transform.</span> <span m='1739060'>That's</span> <span
  m='1739390'>the</span> <span m='1739450'>ratio</span> <span
  m='1739780'>of</span> <span m='1739840'>polynomials,</span> <span
  m='1740560'>and</span> <span m='1740670'>that's</span> <span
  m='1740860'>the</span> <span m='1740950'>region</span> <span
  m='1741250'>of</span> <span m='1741340'>convergence.</span> <span
  m='1742180'>And</span> <span m='1742270'>the</span> <span
  m='1742360'>two</span> <span m='1742510'>together</span> <span
  m='1743160'>are</span> <span m='1743230'>the</span> <span
  m='1743350'>Z-transform.</span> </p><p><span m='1745870'>Now,</span> <span
  m='1747010'>it</span> <span m='1747130'>often</span> <span
  m='1747490'>happens</span> <span m='1748330'>that</span> <span
  m='1749440'>the</span> <span m='1749890'>region</span> <span
  m='1750250'>of</span> <span m='1750370'>convergence</span> <span
  m='1750850'>of</span> <span m='1751330'>the</span> <span
  m='1751510'>Z-transform</span> <span m='1752620'>is</span> <span
  m='1752740'>specified</span> <span m='1753640'>in</span> <span
  m='1753760'>a</span> <span m='1753820'>somewhat</span> <span
  m='1754420'>indirect</span> <span m='1754990'>way,</span> <span
  m='1756460'>by</span> <span m='1757330'>saying</span> <span
  m='1757720'>something</span> <span m='1758140'>about</span> <span
  m='1758430'>the</span> <span m='1758500'>sequence</span> <span
  m='1759040'>that</span> <span m='1759160'>basically</span> <span
  m='1760030'>implies</span> <span m='1761050'>what</span> <span
  m='1761290'>the</span> <span m='1761380'>region</span> <span
  m='1761680'>of</span> <span m='1761800'>convergence</span> <span
  m='1762370'>has</span> <span m='1762580'>to</span> <span
  m='1762730'>be.</span> <span m='1763720'>And</span> <span
  m='1764350'>we</span> <span m='1764530'>can</span> <span
  m='1765130'>lead</span> <span m='1765400'>into</span> <span
  m='1765700'>that</span> <span m='1766750'>by</span> <span
  m='1767980'>stating</span> <span m='1769180'>what</span> <span
  m='1769450'>some</span> <span m='1769690'>of</span> <span
  m='1769750'>the</span> <span m='1769870'>properties</span> <span
  m='1770530'>are</span> <span m='1771070'>that</span> <span
  m='1771220'>the</span> <span m='1771340'>region</span> <span
  m='1771640'>of</span> <span m='1771730'>convergence</span> <span
  m='1772390'>has.</span> <span m='1773500'>And</span> <span
  m='1773920'>I'll</span> <span m='1774240'>always</span> <span
  m='1774640'>be</span> <span m='1774760'>talking</span> <span
  m='1775180'>now</span> <span m='1775600'>about</span> <span
  m='1775960'>sequences</span> <span m='1776800'>that</span> <span
  m='1776950'>are</span> <span m='1777040'>sums</span> <span
  m='1777430'>of</span> <span m='1777520'>exponentials,</span> <span
  m='1778480'>or</span> <span m='1778630'>Z-transforms</span> <span
  m='1779530'>that</span> <span m='1779620'>are</span> <span
  m='1779680'>ratios</span> <span m='1780210'>of</span> <span
  m='1780280'>polynomials,</span> <span m='1781600'>and</span> <span
  m='1781690'>consequently</span> <span m='1782470'>that</span> <span
  m='1782560'>can</span> <span m='1782710'>be</span> <span
  m='1782860'>described</span> <span m='1783490'>by</span> <span
  m='1783670'>poles</span> <span m='1784000'>and</span> <span
  m='1784120'>zeroes</span> <span m='1784540'>in</span> <span
  m='1784630'>the</span> <span m='1784720'>z-plane.</span> </p><p><span
  m='1786730'>OK,</span> <span m='1787090'>well,</span> <span
  m='1788770'>I</span> <span m='1788860'>have</span> <span
  m='1789130'>here</span> <span m='1789440'>the</span> <span
  m='1789460'>first</span> <span m='1789790'>thing</span> <span
  m='1790030'>you</span> <span m='1790120'>can</span> <span
  m='1790270'>say.</span> <span m='1790840'>Actually,</span> <span
  m='1791290'>there's</span> <span m='1791500'>a</span> <span
  m='1791560'>0</span> <span m='1791950'>thing</span> <span
  m='1792250'>you</span> <span m='1792370'>can</span> <span
  m='1792550'>say</span> <span m='1793660'>that</span> <span
  m='1795980'>follows</span> <span m='1797000'>fairly</span> <span
  m='1797430'>straightforwardly,</span> <span m='1798410'>and</span> <span
  m='1798500'>that</span> <span m='1798680'>is,</span> <span
  m='1798890'>obviously,</span> <span m='1801000'>there</span> <span
  m='1801120'>can't</span> <span m='1801420'>be</span> <span
  m='1801540'>any</span> <span m='1801690'>poles</span> <span
  m='1802080'>in</span> <span m='1802170'>the</span> <span
  m='1802230'>region</span> <span m='1802530'>of</span> <span
  m='1802590'>convergence</span> <span m='1803190'>because,</span> <span
  m='1804620'>at</span> <span m='1804720'>a</span> <span m='1804780'>pole</span>
  <span m='1805110'>of the</span> <span m='1805200'>Z-transform,</span> <span
  m='1807060'>that's</span> <span m='1807360'>where</span> <span
  m='1807570'>the</span> <span m='1807690'>Z-transform</span> <span
  m='1808410'>blows</span> <span m='1808770'>up.</span> <span
  m='1809310'>And</span> <span m='1809430'>we</span> <span
  m='1809550'>know</span> <span m='1809730'>that</span> <span
  m='1809850'>the</span> <span m='1809940'>region</span> <span
  m='1810210'>of</span> <span m='1810300'>convergence</span> <span
  m='1811140'>is</span> <span m='1811320'>where</span> <span
  m='1812130'>the</span> <span m='1812220'>Z-transform</span> <span
  m='1812970'>converges.</span> <span m='1813990'>So</span> <span
  m='1814170'>obviously,</span> <span m='1814680'>there</span> <span
  m='1814770'>are</span> <span m='1814830'>no</span> <span
  m='1814980'>poles</span> <span m='1815520'>in</span> <span
  m='1815640'>the</span> <span m='1815700'>region</span> <span
  m='1815970'>of</span> <span m='1816030'>convergence.</span> </p><p><span
  m='1817810'>However,</span> <span m='1818140'>we</span> <span
  m='1818260'>can</span> <span m='1818410'>make</span> <span
  m='1818590'>another</span> <span m='1818860'>statement,</span> <span
  m='1819610'>which</span> <span m='1819910'>is</span> <span
  m='1822520'>justified</span> <span m='1824290'>in</span> <span
  m='1824410'>some</span> <span m='1824620'>detail</span> <span
  m='1825100'>in</span> <span m='1825190'>the</span> <span
  m='1825280'>text,</span> <span m='1826920'>that</span> <span
  m='1827100'>the</span> <span m='1827190'>region</span> <span
  m='1827520'>of</span> <span m='1827610'>convergence</span> <span
  m='1828960'>will</span> <span m='1829140'>always</span> <span
  m='1829530'>be</span> <span m='1829710'>bounded</span> <span
  m='1831000'>by</span> <span m='1831990'>either</span> <span
  m='1832290'>poles</span> <span m='1833460'>or</span> <span
  m='1834240'>zero</span> <span m='1834930'>or</span> <span
  m='1835140'>infinity.</span> <span m='1836740'>For</span> <span
  m='1836820'>example,</span> <span m='1838000'>in</span> <span
  m='1838100'>this</span> <span m='1838170'>example</span> <span
  m='1838465'>that</span> <span m='1838760'>we</span> <span
  m='1838860'>worked</span> <span m='1839160'>out</span> <span
  m='1839370'>here,</span> <span m='1840300'>the</span> <span
  m='1840390'>region</span> <span m='1840720'>of</span> <span
  m='1840840'>convergence</span> <span m='1842310'>goes</span> <span
  m='1842610'>to</span> <span m='1842760'>zero--</span> <span
  m='1843330'>I</span> <span m='1843390'>mean,</span> <span
  m='1843550'>it</span> <span m='1843660'>includes</span> <span
  m='1844140'>zero--</span> <span m='1845160'>and</span> <span
  m='1845280'>it's</span> <span m='1845430'>bounded</span> <span
  m='1846750'>at</span> <span m='1846900'>the</span> <span
  m='1847050'>outside,</span> <span m='1847590'>in</span> <span
  m='1847680'>this</span> <span m='1847830'>particular</span> <span
  m='1848280'>case,</span> <span m='1848610'>by</span> <span
  m='1848820'>a</span> <span m='1848880'>pole.</span> </p><p><span
  m='1851150'>In</span> <span m='1851330'>the</span> <span
  m='1851660'>example</span> <span m='1852230'>that</span> <span
  m='1852320'>we</span> <span m='1852470'>had</span> <span
  m='1852680'>previously,</span> <span m='1853880'>if</span> <span
  m='1854030'>we</span> <span m='1854120'>look</span> <span
  m='1854330'>at</span> <span m='1854420'>this</span> <span
  m='1854630'>example,</span> <span m='1856770'>the</span> <span
  m='1856890'>region</span> <span m='1857190'>of</span> <span
  m='1857280'>convergence</span> <span m='1858180'>is</span> <span
  m='1858600'>bounded</span> <span m='1859080'>on</span> <span
  m='1859200'>the</span> <span m='1859320'>inside</span> <span
  m='1860220'>by</span> <span m='1860430'>a</span> <span
  m='1860490'>pole,</span> <span m='1862110'>and</span> <span
  m='1862230'>it's</span> <span m='1862350'>bounded</span> <span
  m='1862740'>on</span> <span m='1862860'>the</span> <span
  m='1862980'>outside</span> <span m='1863820'>by</span> <span
  m='1864000'>infinity.</span> <span m='1865170'>And</span> <span
  m='1865560'>that's</span> <span m='1865830'>a</span> <span
  m='1865890'>statement</span> <span m='1866670'>that</span> <span
  m='1866880'>we</span> <span m='1867000'>can</span> <span
  m='1867150'>generally</span> <span m='1867600'>make.</span> <span
  m='1867900'>I</span> <span m='1867960'>won't</span> <span
  m='1868140'>try</span> <span m='1868380'>to</span> <span
  m='1868470'>justify</span> <span m='1869100'>that</span> <span
  m='1869310'>right</span> <span m='1869580'>now,</span> <span
  m='1870390'>but</span> <span m='1870990'>the</span> <span
  m='1871080'>region</span> <span m='1871410'>of</span> <span
  m='1871500'>convergence</span> <span m='1872340'>is</span> <span
  m='1872490'>bounded</span> <span m='1872970'>by</span> <span
  m='1873180'>poles,</span> <span m='1874410'>and</span> <span
  m='1874890'>in</span> <span m='1875070'>fact</span> <span
  m='1875520'>is</span> <span m='1875670'>bounded</span> <span
  m='1876030'>by</span> <span m='1876210'>a</span> <span
  m='1876270'>circle</span> <span m='1876780'>that</span> <span
  m='1877200'>goes</span> <span m='1877470'>through</span> <span
  m='1878040'>a</span> <span m='1878100'>pole.</span> </p><p><span
  m='1880210'>All</span> <span m='1880280'>right.</span> <span
  m='1880460'>That's</span> <span m='1880760'>one</span> <span
  m='1881030'>statement</span> <span m='1881480'>we</span> <span
  m='1881630'>can</span> <span m='1881810'>make.</span> <span
  m='1882590'>Now</span> <span m='1882800'>some</span> <span
  m='1882980'>other</span> <span m='1883340'>statements</span> <span
  m='1883940'>that</span> <span m='1884060'>we</span> <span
  m='1884210'>can</span> <span m='1884390'>make,</span> <span
  m='1885230'>which</span> <span m='1886250'>are</span> <span
  m='1886640'>all</span> <span m='1886940'>developed</span> <span
  m='1887780'>in</span> <span m='1887870'>the</span> <span
  m='1887990'>text.</span> <span m='1889130'>That</span> <span
  m='1889250'>is,</span> <span m='1889340'>the</span> <span
  m='1889460'>proof</span> <span m='1889730'>of</span> <span
  m='1889790'>them</span> <span m='1889970'>is</span> <span
  m='1890090'>worked</span> <span m='1890420'>out.</span> <span
  m='1891380'>First</span> <span m='1891710'>of</span> <span
  m='1891860'>all,</span> <span m='1892980'>let's</span> <span
  m='1893270'>consider</span> <span m='1893750'>finite</span> <span
  m='1894200'>length</span> <span m='1894440'>sequences.</span> <span
  m='1895790'>A</span> <span m='1895880'>finite</span> <span
  m='1896300'>length</span> <span m='1896570'>sequence,</span> <span
  m='1898700'>sequenced</span> <span m='1899210'>at</span> <span
  m='1899360'>0,</span> <span m='1899870'>except</span> <span
  m='1901310'>for</span> <span m='1901490'>a</span> <span
  m='1901550'>finite</span> <span m='1902270'>number</span> <span
  m='1902630'>of</span> <span m='1902690'>values</span> <span
  m='1903200'>of</span> <span m='1903320'>n,</span> <span m='1904910'>has</span>
  <span m='1905120'>a</span> <span m='1905210'>region</span> <span
  m='1905570'>of</span> <span m='1905660'>convergence</span> <span
  m='1907130'>that</span> <span m='1908090'>is</span> <span
  m='1908690'>the</span> <span m='1908840'>entire</span> <span
  m='1909380'>z-plane,</span> <span m='1910730'>perhaps</span> <span
  m='1911240'>with</span> <span m='1911420'>the</span> <span
  m='1911570'>exception</span> <span m='1912380'>of</span> <span
  m='1912620'>the</span> <span m='1912710'>point</span> <span m='1913205'>z
  equals</span> <span m='1913700'>0,</span> <span m='1914960'>or</span> <span
  m='1915170'>perhaps</span> <span m='1915590'>with</span> <span
  m='1915680'>the</span> <span m='1915800'>exception</span> <span
  m='1916220'>of</span> <span m='1916280'>the</span> <span m='1916370'>point
  z</span> <span m='1916730'>equals</span> <span m='1917120'>infinity.</span>
  <span m='1918260'>And</span> <span m='1918740'>that</span> <span
  m='1918950'>follows</span> <span m='1919370'>in</span> <span
  m='1919430'>a</span> <span m='1919490'>pretty</span> <span
  m='1919730'>straightforward</span> <span m='1920420'>way,</span> <span
  m='1920730'>basically</span> <span m='1921320'>because</span> <span
  m='1922280'>the</span> <span m='1922370'>sum,</span> <span
  m='1923480'>in</span> <span m='1923600'>examining</span> <span
  m='1924110'>absolute</span> <span m='1924530'>convergence,</span> <span
  m='1925580'>the</span> <span m='1925670'>sum</span> <span
  m='1926120'>just</span> <span m='1926330'>includes</span> <span
  m='1926750'>finite</span> <span m='1927170'>limits.</span> <span
  m='1927980'>So</span> <span m='1928490'>as</span> <span
  m='1928640'>long</span> <span m='1928910'>as</span> <span
  m='1929060'>each</span> <span m='1929240'>of</span> <span
  m='1929300'>the</span> <span m='1929390'>sequence</span> <span
  m='1929780'>values</span> <span m='1930230'>is</span> <span
  m='1930350'>finite,</span> <span m='1930890'>the</span> <span
  m='1931010'>sum</span> <span m='1931250'>has</span> <span
  m='1931430'>to</span> <span m='1931520'>be</span> <span
  m='1931640'>finite.</span> </p><p><span m='1934450'>A</span> <span
  m='1934480'>little</span> <span m='1934660'>more</span> <span
  m='1934930'>involved,</span> <span m='1935770'>we</span> <span
  m='1935920'>have</span> <span m='1936640'>right-sided</span> <span
  m='1937660'>sequences.</span> <span m='1938980'>What</span> <span
  m='1939100'>I</span> <span m='1939190'>mean</span> <span m='1939430'>by</span>
  <span m='1939610'>a</span> <span m='1939700'>right-sided</span> <span
  m='1940360'>sequence</span> <span m='1940990'>is</span> <span
  m='1941140'>a</span> <span m='1941200'>sequence</span> <span
  m='1941860'>which</span> <span m='1942070'>is</span> <span
  m='1942160'>0</span> <span m='1943850'>for</span> <span m='1944080'>n</span>
  <span m='1944560'>less</span> <span m='1944950'>than</span> <span
  m='1945100'>some</span> <span m='1945400'>value</span> <span
  m='1945870'>of</span> <span m='1946210'>n.</span> <span m='1946900'>And</span>
  <span m='1947080'>then</span> <span m='1947650'>goes</span> <span
  m='1947980'>on</span> <span m='1949550'>up</span> <span m='1949840'>to</span>
  <span m='1950370'>n</span> <span m='1950520'>equals</span> <span
  m='1950830'>plus</span> <span m='1951160'>infinity.</span> <span
  m='1952820'>And</span> <span m='1953290'>what</span> <span
  m='1953500'>you</span> <span m='1953620'>can</span> <span
  m='1953770'>say</span> <span m='1953980'>about</span> <span
  m='1954220'>right-sided</span> <span m='1954880'>sequences,</span> <span
  m='1956200'>as</span> <span m='1956350'>it</span> <span
  m='1956440'>turns</span> <span m='1956800'>out,</span> <span
  m='1958070'>is</span> <span m='1958120'>that</span> <span
  m='1958270'>the</span> <span m='1958390'>region</span> <span
  m='1958750'>of</span> <span m='1958840'>convergence</span> <span
  m='1960550'>is</span> <span m='1960880'>outside</span> <span
  m='1962350'>some</span> <span m='1962680'>value,</span> <span
  m='1964280'>which</span> <span m='1964390'>I've</span> <span
  m='1964540'>denoted</span> <span m='1964930'>by</span> <span
  m='1965110'>r</span> <span m='1965290'>sub x</span> <span
  m='1965740'>minus,</span> <span m='1966910'>and</span> <span
  m='1967030'>goes</span> <span m='1967390'>to</span> <span
  m='1967540'>infinity.</span> <span m='1968480'>It</span> <span
  m='1968500'>may</span> <span m='1968740'>include</span> <span
  m='1969100'>infinity</span> <span m='1969640'>or</span> <span
  m='1969730'>it</span> <span m='1969820'>may</span> <span
  m='1969970'>not</span> <span m='1970240'>include</span> <span
  m='1970600'>infinity,</span> <span m='1971590'>but</span> <span
  m='1972010'>it</span> <span m='1972190'>goes</span> <span
  m='1972640'>at</span> <span m='1972790'>least</span> <span
  m='1973180'>up</span> <span m='1973360'>to</span> <span
  m='1973510'>infinity.</span> </p><p><span m='1975350'>So</span> <span
  m='1975730'>it</span> <span m='1975880'>begins</span> <span
  m='1976330'>at</span> <span m='1976420'>some</span> <span
  m='1976660'>finite</span> <span m='1977140'>value</span> <span
  m='1977530'>in</span> <span m='1977620'>the</span> <span
  m='1977680'>z-plane,</span> <span m='1978850'>bounded</span> <span
  m='1979270'>by</span> <span m='1979570'>some</span> <span
  m='1979810'>circle</span> <span m='1980260'>with</span> <span
  m='1980440'>radius</span> <span m='1980890'>r</span> <span m='1981100'>sub
  x</span> <span m='1981550'>minus,</span> <span m='1982480'>and</span> <span
  m='1982600'>goes</span> <span m='1982870'>up</span> <span
  m='1983020'>to</span> <span m='1983170'>infinity.</span> <span
  m='1985170'>Well,</span> <span m='1985540'>look,</span> <span
  m='1985780'>if</span> <span m='1985930'>we</span> <span m='1986050'>had</span>
  <span m='1986200'>a</span> <span m='1986260'>right-sided</span> <span
  m='1986890'>sequence,</span> <span m='1988090'>how</span> <span
  m='1988270'>are</span> <span m='1988330'>you</span> <span
  m='1988420'>going</span> <span m='1988540'>to</span> <span
  m='1988600'>find</span> <span m='1989590'>what</span> <span m='1989770'>r
  sub</span> <span m='1989970'>x</span> <span m='1990310'>minus</span> <span
  m='1990730'>is?</span> <span m='1992080'>Just</span> <span
  m='1992290'>by</span> <span m='1992470'>looking</span> <span
  m='1992770'>at</span> <span m='1992860'>the</span> <span
  m='1992950'>pole-zero</span> <span m='1993430'>pattern,</span> <span
  m='1994540'>because</span> <span m='1995440'>we</span> <span
  m='1995560'>know</span> <span m='1996340'>that</span> <span
  m='1997570'>the</span> <span m='1997780'>region</span> <span
  m='1998110'>of</span> <span m='1998170'>convergence</span> <span
  m='1998710'>is</span> <span m='1998830'>bounded</span> <span
  m='1999190'>by</span> <span m='1999370'>poles.</span> <span
  m='2000870'>We</span> <span m='2001020'>know</span> <span
  m='2001230'>also</span> <span m='2002130'>that</span> <span
  m='2002940'>the</span> <span m='2003000'>region</span> <span
  m='2003270'>of</span> <span m='2003360'>convergence</span> <span
  m='2003870'>can't</span> <span m='2004140'>have</span> <span
  m='2004350'>any</span> <span m='2004530'>poles,</span> <span
  m='2005670'>so</span> <span m='2005940'>r</span> <span m='2006210'>sub</span>
  <span m='2006520'>x</span> <span m='2006840'>minus</span> <span
  m='2007680'>has</span> <span m='2007950'>to</span> <span m='2008100'>be</span>
  <span m='2008850'>the</span> <span m='2008940'>circle</span> <span
  m='2010050'>that</span> <span m='2010230'>goes</span> <span
  m='2010620'>through</span> <span m='2011310'>the</span> <span
  m='2011490'>outermost</span> <span m='2012090'>pole</span> <span
  m='2012570'>in</span> <span m='2012660'>the</span> <span
  m='2012760'>z-plane.</span> </p><p><span m='2014140'>So</span> <span
  m='2015060'>if</span> <span m='2015210'>we</span> <span
  m='2015330'>have</span> <span m='2015450'>a</span> <span
  m='2015510'>right-sided</span> <span m='2016140'>sequence,</span> <span
  m='2017250'>that</span> <span m='2017430'>implies</span> <span
  m='2018150'>a</span> <span m='2018210'>region</span> <span
  m='2018540'>of</span> <span m='2018630'>convergence,</span> <span
  m='2019330'>it</span> <span m='2019440'>implies</span> <span
  m='2020190'>that</span> <span m='2020310'>the</span> <span
  m='2020430'>region</span> <span m='2020760'>of</span> <span
  m='2020850'>convergence</span> <span m='2022050'>is</span> <span
  m='2022320'>outside</span> <span m='2023460'>the</span> <span
  m='2023640'>outermost</span> <span m='2024210'>pole</span> <span
  m='2024870'>in</span> <span m='2024990'>the</span> <span
  m='2025080'>z-plane.</span> <span m='2027220'>We</span> <span
  m='2027340'>can</span> <span m='2027490'>talk</span> <span
  m='2027880'>also</span> <span m='2028540'>about</span> <span
  m='2028890'>left-sided</span> <span m='2029530'>sequences.</span> <span
  m='2031540'>Left-sided</span> <span m='2032140'>sequences</span> <span
  m='2032830'>are</span> <span m='2032920'>ones</span> <span
  m='2033460'>for</span> <span m='2033670'>which</span> <span
  m='2034180'>the</span> <span m='2034300'>sequence</span> <span
  m='2034840'>is</span> <span m='2034900'>zero</span> <span
  m='2035440'>for</span> <span m='2035650'>n</span> <span
  m='2035860'>greater</span> <span m='2036280'>than</span> <span
  m='2036430'>some</span> <span m='2036700'>value</span> <span
  m='2037300'>n1.</span> <span m='2037630'>One</span> <span
  m='2039280'>And</span> <span m='2040540'>here,</span> <span
  m='2041470'>the</span> <span m='2042070'>region</span> <span
  m='2042430'>of</span> <span m='2042520'>convergence</span> <span
  m='2044410'>begins</span> <span m='2044860'>at</span> <span
  m='2044980'>zero--</span> <span m='2045610'>may</span> <span
  m='2045850'>or</span> <span m='2045940'>may</span> <span
  m='2046090'>not</span> <span m='2046330'>include</span> <span
  m='2046720'>zero,</span> <span m='2047140'>depending</span> <span
  m='2047920'>on</span> <span m='2049570'>some</span> <span
  m='2049840'>issues</span> <span m='2050230'>about</span> <span
  m='2050500'>the</span> <span m='2050590'>left-sided</span> <span
  m='2051159'>sequence,</span> <span m='2052179'>but</span> <span
  m='2053350'>at</span> <span m='2053440'>least</span> <span
  m='2053679'>goes</span> <span m='2054010'>up</span> <span
  m='2054190'>to</span> <span m='2054330'>zero--</span> <span
  m='2055690'>and</span> <span m='2055810'>then</span> <span
  m='2055960'>goes</span> <span m='2056260'>out</span> <span
  m='2056500'>to</span> <span m='2056650'>some</span> <span
  m='2057370'>value</span> <span m='2058070'>r</span> <span m='2058250'>sub
  x</span> <span m='2058750'>plus.</span> </p><p><span m='2060600'>How</span>
  <span m='2060699'>do</span> <span m='2060790'>we</span> <span
  m='2060909'>find</span> <span m='2061270'>r sub</span> <span
  m='2061389'>x</span> <span m='2061780'>plus?</span> <span
  m='2062920'>We</span> <span m='2063010'>do</span> <span m='2063159'>it</span>
  <span m='2063250'>the</span> <span m='2063340'>same</span> <span
  m='2063580'>way.</span> <span m='2064540'>That</span> <span
  m='2064750'>is,</span> <span m='2065440'>we</span> <span
  m='2065560'>know</span> <span m='2065889'>that</span> <span
  m='2066070'>the</span> <span m='2066190'>region</span> <span
  m='2066460'>of</span> <span m='2066520'>convergence</span> <span
  m='2067090'>is</span> <span m='2067210'>bounded</span> <span
  m='2067600'>by</span> <span m='2067810'>poles</span> <span
  m='2068380'>and</span> <span m='2068500'>doesn't</span> <span
  m='2068830'>contain</span> <span m='2069250'>any</span> <span
  m='2069460'>poles,</span> <span m='2070659'>so</span> <span
  m='2071230'>this</span> <span m='2071590'>must</span> <span
  m='2071830'>be</span> <span m='2072040'>a</span> <span
  m='2072100'>circle</span> <span m='2072820'>whose</span> <span
  m='2073030'>radius</span> <span m='2074290'>is</span> <span
  m='2074800'>equal--</span> <span m='2075940'>who's</span> <span
  m='2076409'>a</span> <span m='2076540'>circle</span> <span
  m='2077409'>that</span> <span m='2077530'>goes</span> <span
  m='2077920'>through</span> <span m='2078489'>the</span> <span
  m='2078699'>innermost</span> <span m='2079239'>pole,</span> <span
  m='2079810'>other</span> <span m='2080020'>than</span> <span
  m='2080199'>the</span> <span m='2080290'>one at z</span> <span
  m='2080590'>equals</span> <span m='2080980'>0</span> <span
  m='2081429'>in</span> <span m='2081550'>the</span> <span m='2081610'>z</span>
  <span m='2081790'>plane.</span> <span m='2083090'>So</span> <span
  m='2083199'>if</span> <span m='2083350'>I</span> <span m='2083409'>have</span>
  <span m='2083560'>a</span> <span m='2083590'>left-sided</span> <span
  m='2084190'>sequence,</span> <span m='2085139'>if</span> <span
  m='2085270'>I</span> <span m='2085360'>know</span> <span
  m='2085570'>it's</span> <span m='2085690'>a</span> <span
  m='2085750'>left-sided</span> <span m='2086230'>sequence,</span> <span
  m='2086739'>then</span> <span m='2086830'>by</span> <span
  m='2086980'>looking</span> <span m='2087550'>at</span> <span
  m='2088239'>the</span> <span m='2088330'>pole-zero</span> <span
  m='2088929'>pattern</span> <span m='2089500'>I</span> <span
  m='2089620'>can</span> <span m='2089800'>immediately</span> <span
  m='2090370'>infer</span> <span m='2090699'>what</span> <span
  m='2090880'>the</span> <span m='2090969'>region</span> <span
  m='2091270'>of</span> <span m='2091330'>convergence</span> <span
  m='2092050'>is.</span> </p><p><span m='2093699'>Finally,</span> <span
  m='2094179'>we</span> <span m='2094360'>have</span> <span
  m='2094630'>two-sided</span> <span m='2095230'>sequences,</span> <span
  m='2096889'>sequences</span> <span m='2097480'>that</span> <span
  m='2098200'>go</span> <span m='2098800'>on</span> <span m='2099430'>to</span>
  <span m='2099550'>minus</span> <span m='2099910'>infinity</span> <span
  m='2100390'>and</span> <span m='2100480'>they</span> <span
  m='2100570'>go</span> <span m='2100750'>on</span> <span m='2100930'>the</span>
  <span m='2101020'>plus</span> <span m='2101320'>infinity.</span> <span
  m='2102490'>In</span> <span m='2102610'>that</span> <span
  m='2102820'>case,</span> <span m='2103630'>the</span> <span
  m='2103720'>region</span> <span m='2104050'>of</span> <span
  m='2104140'>convergence</span> <span m='2105280'>lies</span> <span
  m='2106930'>between</span> <span m='2108100'>two</span> <span
  m='2108310'>circles,</span> <span m='2110020'>which</span> <span
  m='2110470'>go</span> <span m='2110740'>through</span> <span
  m='2110980'>two</span> <span m='2111220'>poles.</span> <span
  m='2112090'>And</span> <span m='2112240'>obviously,</span> <span
  m='2113020'>again,</span> <span m='2113470'>they</span> <span
  m='2113590'>have</span> <span m='2113800'>to</span> <span
  m='2113920'>be</span> <span m='2114070'>two</span> <span
  m='2114460'>poles</span> <span m='2115360'>that</span> <span
  m='2115540'>are</span> <span m='2115690'>adjacent</span> <span
  m='2117100'>in</span> <span m='2117220'>the</span> <span
  m='2117280'>z-plane.</span> <span m='2118100'>In</span> <span
  m='2118200'>other</span> <span m='2118300'>words,</span> <span
  m='2118670'>again,</span> <span m='2119350'>to</span> <span
  m='2119470'>avoid</span> <span m='2119890'>having</span> <span
  m='2120460'>poles</span> <span m='2121510'>that</span> <span
  m='2121870'>are</span> <span m='2122140'>inside</span> <span
  m='2122590'>the</span> <span m='2122680'>region</span> <span
  m='2123010'>of</span> <span m='2123100'>convergence.</span> </p><p><span
  m='2126220'>And</span> <span m='2127700'>out</span> <span
  m='2127860'>of</span> <span m='2128110'>all</span> <span
  m='2128350'>this,</span> <span m='2129280'>incidentally,</span> <span
  m='2130330'>if</span> <span m='2130540'>I</span> <span m='2130690'>tell</span>
  <span m='2130990'>you</span> <span m='2132460'>that</span> <span
  m='2132700'>I</span> <span m='2132790'>have</span> <span m='2132970'>a</span>
  <span m='2133030'>sequence</span> <span m='2134110'>whose</span> <span
  m='2134290'>Fourier</span> <span m='2134710'>transform</span> <span
  m='2135400'>exists,</span> <span m='2136360'>and</span> <span
  m='2136480'>I</span> <span m='2136540'>don't</span> <span
  m='2136690'>tell</span> <span m='2136870'>you</span> <span
  m='2137020'>anything</span> <span m='2137320'>else</span> <span
  m='2137500'>about</span> <span m='2137770'>the</span> <span
  m='2137890'>sequence,</span> <span m='2139670'>can</span> <span
  m='2139850'>you</span> <span m='2140060'>infer</span> <span
  m='2140810'>what</span> <span m='2141050'>the</span> <span
  m='2141140'>region</span> <span m='2141440'>of</span> <span
  m='2141530'>convergence</span> <span m='2141890'>is?</span> <span
  m='2143210'>Well,</span> <span m='2143510'>sure</span> <span
  m='2143720'>you</span> <span m='2143840'>can,</span> <span
  m='2144500'>because</span> <span m='2144860'>you</span> <span
  m='2144980'>know</span> <span m='2145190'>that</span> <span
  m='2145340'>the</span> <span m='2145430'>region</span> <span
  m='2145700'>of</span> <span m='2145760'>convergence</span> <span
  m='2146330'>includes</span> <span m='2146810'>the</span> <span
  m='2146900'>unit</span> <span m='2147170'>circle.</span> <span
  m='2148380'>And</span> <span m='2148430'>then</span> <span
  m='2148670'>where</span> <span m='2148880'>it's</span> <span
  m='2149000'>got</span> <span m='2149180'>to</span> <span m='2149270'>go</span>
  <span m='2149480'>from</span> <span m='2149720'>there</span> <span
  m='2150500'>is</span> <span m='2150800'>to</span> <span m='2151670'>the</span>
  <span m='2151790'>first</span> <span m='2152150'>pole</span> <span
  m='2153020'>that</span> <span m='2153260'>you</span> <span
  m='2153410'>run</span> <span m='2153620'>into</span> <span
  m='2154400'>heading</span> <span m='2154670'>toward</span> <span
  m='2154910'>the</span> <span m='2155060'>origin,</span> <span
  m='2156060'>and</span> <span m='2156420'>to</span> <span
  m='2156560'>the</span> <span m='2156650'>first</span> <span
  m='2156920'>pole</span> <span m='2157640'>that</span> <span
  m='2157760'>you</span> <span m='2157850'>run</span> <span
  m='2158090'>into</span> <span m='2158510'>heading</span> <span
  m='2158810'>out</span> <span m='2158960'>toward</span> <span
  m='2159200'>infinity.</span> <span m='2160230'>So</span> <span
  m='2160490'>in</span> <span m='2160610'>fact,</span> <span
  m='2160910'>if</span> <span m='2161030'>I</span> <span m='2161150'>tell</span>
  <span m='2161360'>you</span> <span m='2161480'>that</span> <span
  m='2161630'>the</span> <span m='2161720'>sequence</span> <span
  m='2163250'>is</span> <span m='2163400'>absolutely</span> <span
  m='2163910'>summable,</span> <span m='2164480'>or</span> <span
  m='2164630'>that</span> <span m='2164750'>the</span> <span
  m='2164870'>Fourier</span> <span m='2165200'>transform</span> <span
  m='2165800'>exists,</span> <span m='2166520'>that</span> <span
  m='2166760'>also,</span> <span m='2168230'>in</span> <span
  m='2168410'>effect,</span> <span m='2169460'>lets</span> <span
  m='2169730'>you</span> <span m='2169850'>construct</span> <span
  m='2170450'>the</span> <span m='2170540'>region</span> <span
  m='2170870'>of</span> <span m='2170930'>convergence</span> <span
  m='2171530'>in</span> <span m='2171590'>the</span> <span
  m='2171680'>z-plane.</span> </p><p><span m='2173600'>Well,</span> <span
  m='2173870'>let's</span> <span m='2174290'>just</span> <span
  m='2175130'>cement</span> <span m='2175640'>this</span> <span
  m='2175940'>with</span> <span m='2176630'>an</span> <span
  m='2176750'>example.</span> <span m='2178780'>Let's</span> <span
  m='2178860'>say</span> <span m='2179190'>that</span> <span
  m='2179730'>I</span> <span m='2179910'>have</span> <span m='2181090'>a</span>
  <span m='2181200'>Z-transform</span> <span m='2183210'>which</span> <span
  m='2183720'>has</span> <span m='2183930'>a</span> <span
  m='2183990'>pole-zero</span> <span m='2184710'>pattern</span> <span
  m='2185910'>that</span> <span m='2186060'>has</span> <span
  m='2188930'>a</span> <span m='2188990'>pole</span> <span m='2189680'>at</span>
  <span m='2190880'>z</span> <span m='2191240'>equal</span> <span
  m='2191450'>a</span> <span m='2192420'>and</span> <span m='2192880'>a</span>
  <span m='2193340'>pole</span> <span m='2194000'>at</span> <span
  m='2194130'>z</span> <span m='2194500'>equal</span> <span
  m='2194650'>b.</span> <span m='2196000'>So</span> <span
  m='2197080'>this</span> <span m='2197320'>is</span> <span
  m='2197500'>a,</span> <span m='2198400'>and</span> <span
  m='2198730'>this</span> <span m='2198940'>is</span> <span
  m='2199090'>b.</span> <span m='2201760'>And</span> <span
  m='2202120'>let's</span> <span m='2202390'>consider</span> <span
  m='2203680'>what</span> <span m='2204040'>turn</span> <span
  m='2204320'>out</span> <span m='2204460'>to</span> <span m='2204580'>be</span>
  <span m='2204780'>the</span> <span m='2205240'>only</span> <span
  m='2205510'>three</span> <span m='2205720'>possible</span> <span
  m='2206200'>choices</span> <span m='2206770'>for</span> <span
  m='2206920'>the</span> <span m='2207010'>region</span> <span
  m='2207340'>of</span> <span m='2207430'>convergence,</span> <span
  m='2208990'>given</span> <span m='2209680'>this</span> <span
  m='2210160'>pole-zero</span> <span m='2210760'>pattern.</span> <span
  m='2211380'>No</span> <span m='2211540'>zeroes,</span> <span
  m='2212250'>to</span> <span m='2212380'>make</span> <span
  m='2212560'>the</span> <span m='2212650'>example</span> <span
  m='2213130'>easy.</span> </p><p><span m='2214420'>Well</span> <span
  m='2214870'>first</span> <span m='2215230'>of</span> <span
  m='2215350'>all,</span> <span m='2216620'>let's</span> <span
  m='2216790'>suppose</span> <span m='2217780'>that</span> <span
  m='2218050'>we</span> <span m='2218230'>picked</span> <span
  m='2218500'>the</span> <span m='2218590'>region</span> <span
  m='2218920'>of</span> <span m='2219010'>convergence</span> <span
  m='2220330'>to</span> <span m='2220450'>be</span> <span
  m='2220900'>less</span> <span m='2221230'>than</span> <span
  m='2221410'>a.</span> <span m='2221740'>So</span> <span m='2221980'>the</span>
  <span m='2222100'>region</span> <span m='2222400'>of</span> <span
  m='2222490'>convergence</span> <span m='2223960'>for</span> <span
  m='2224110'>this</span> <span m='2224290'>first</span> <span
  m='2224590'>case</span> <span m='2225460'>is</span> <span
  m='2226150'>inside</span> <span m='2226690'>a</span> <span
  m='2226750'>circle</span> <span m='2227590'>bounded</span> <span
  m='2228010'>by</span> <span m='2228190'>that</span> <span
  m='2228400'>pole.</span> <span m='2230840'>Well,</span> <span
  m='2231110'>let's</span> <span m='2231290'>see.</span> <span
  m='2231450'>Let's</span> <span m='2231710'>answer</span> <span
  m='2232610'>the</span> <span m='2232790'>easy</span> <span
  m='2233570'>question</span> <span m='2234080'>first.</span> <span
  m='2235190'>Does</span> <span m='2235340'>the</span> <span
  m='2235460'>Fourier</span> <span m='2235880'>transform</span> <span
  m='2236570'>exist?</span> <span m='2238030'>To</span> <span
  m='2238130'>answer</span> <span m='2238340'>that,</span> <span
  m='2238670'>we</span> <span m='2238880'>ask,</span> <span
  m='2239720'>is</span> <span m='2239960'>the</span> <span
  m='2240050'>unit</span> <span m='2240320'>circle</span> <span
  m='2240740'>inside</span> <span m='2241100'>the</span> <span
  m='2241220'>region</span> <span m='2241490'>of</span> <span
  m='2241580'>convergence?</span> <span m='2242480'>Well,</span> <span
  m='2242660'>it's</span> <span m='2242810'>not</span> <span
  m='2243140'>if</span> <span m='2243260'>the</span> <span
  m='2243350'>region</span> <span m='2243650'>of</span> <span
  m='2243710'>convergence</span> <span m='2244340'>is</span> <span
  m='2244460'>inside</span> <span m='2244850'>that</span> <span
  m='2245060'>pole.</span> <span m='2246050'>So</span> <span
  m='2246800'>for</span> <span m='2246980'>this</span> <span
  m='2247220'>case,</span> <span m='2248880'>the</span> <span
  m='2249000'>Fourier</span> <span m='2249430'>transform</span> <span
  m='2250910'>doesn't</span> <span m='2251150'>exist.</span> <span
  m='2252410'>That</span> <span m='2252590'>is,</span> <span
  m='2252740'>it</span> <span m='2252830'>doesn't</span> <span
  m='2253070'>converge.</span> </p><p><span m='2255010'>How</span> <span
  m='2255130'>about</span> <span m='2255580'>which</span> <span
  m='2255850'>sided?</span> <span m='2256330'>Left-sided,</span> <span
  m='2256870'>right-sided,</span> <span m='2257500'>two-sided?</span> <span
  m='2259310'>Well,</span> <span m='2261020'>we</span> <span
  m='2261200'>can</span> <span m='2261380'>answer</span> <span
  m='2261710'>that,</span> <span m='2262190'>again,</span> <span
  m='2262700'>because</span> <span m='2263900'>we</span> <span
  m='2265160'>know,</span> <span m='2265640'>from</span> <span
  m='2265880'>what</span> <span m='2266000'>we</span> <span
  m='2266120'>said</span> <span m='2266330'>previously,</span> <span
  m='2267860'>that</span> <span m='2269030'>a</span> <span
  m='2270320'>left-sided</span> <span m='2271160'>sequence</span> <span
  m='2273090'>has</span> <span m='2273330'>a</span> <span
  m='2273390'>region</span> <span m='2273690'>of</span> <span
  m='2273810'>convergence</span> <span m='2274890'>that</span> <span
  m='2275460'>starts</span> <span m='2275970'>at</span> <span
  m='2276090'>zero</span> <span m='2276720'>and</span> <span
  m='2276870'>goes</span> <span m='2277140'>out</span> <span
  m='2277380'>to</span> <span m='2277470'>some</span> <span
  m='2277770'>value</span> <span m='2278370'>r</span> <span m='2278550'>sub
  x</span> <span m='2279000'>plus.</span> <span m='2279960'>Well,</span> <span
  m='2280350'>that's</span> <span m='2280590'>the</span> <span
  m='2280710'>region</span> <span m='2281010'>of</span> <span
  m='2281070'>convergence</span> <span m='2281640'>that</span> <span
  m='2281760'>we're</span> <span m='2281880'>talking</span> <span
  m='2282300'>about</span> <span m='2282630'>here.</span> <span
  m='2283630'>So</span> <span m='2283680'>this</span> <span
  m='2283890'>particular</span> <span m='2284490'>example</span> <span
  m='2285630'>is</span> <span m='2286080'>a</span> <span
  m='2286140'>sequence</span> <span m='2287130'>for</span> <span
  m='2287310'>a</span> <span m='2287340'>sequence</span> <span
  m='2288260'>that's</span> <span m='2288450'>left-sided.</span> </p><p><span
  m='2291020'>How</span> <span m='2291270'>about</span> <span
  m='2291730'>the</span> <span m='2291850'>region</span> <span
  m='2292150'>of</span> <span m='2292240'>convergence</span> <span
  m='2292840'>between</span> <span m='2293320'>a and</span> <span
  m='2293680'>b?</span> <span m='2295360'>Think</span> <span
  m='2295600'>of</span> <span m='2295690'>two</span> <span
  m='2295870'>circles</span> <span m='2297580'>with</span> <span
  m='2297760'>radii</span> <span m='2298240'>a and</span> <span
  m='2298600'>b.</span> <span m='2299080'>And</span> <span
  m='2299230'>now</span> <span m='2299410'>the</span> <span
  m='2299500'>region</span> <span m='2299770'>of</span> <span
  m='2299860'>convergence</span> <span m='2300460'>is</span> <span
  m='2300610'>between</span> <span m='2301090'>them.</span> <span
  m='2301810'>Does</span> <span m='2301990'>that</span> <span
  m='2302170'>include</span> <span m='2302500'>the</span> <span
  m='2302590'>unit</span> <span m='2302890'>circle?</span> <span
  m='2303630'>Yeah, it</span> <span m='2303940'>includes</span> <span
  m='2304360'>the</span> <span m='2304420'>unit</span> <span
  m='2304690'>circle.</span> <span m='2305720'>So</span> <span
  m='2306370'>for</span> <span m='2306490'>that</span> <span
  m='2306730'>case,</span> <span m='2307630'>the</span> <span
  m='2307720'>Fourier</span> <span m='2308140'>transform</span> <span
  m='2308920'>exists.</span> <span m='2311500'>Is</span> <span
  m='2311650'>it</span> <span m='2311740'>left-sided,</span> <span
  m='2312340'>right-sided,</span> <span m='2312940'>or</span> <span
  m='2313030'>two-sided?</span> <span m='2313780'>Well,</span> <span
  m='2313990'>it's</span> <span m='2314140'>two-sided,</span> <span
  m='2314770'>because</span> <span m='2315100'>the</span> <span
  m='2315160'>region</span> <span m='2315460'>of</span> <span
  m='2315550'>convergence</span> <span m='2316120'>doesn't</span> <span
  m='2316390'>make</span> <span m='2316630'>it</span> <span
  m='2316720'>to</span> <span m='2316840'>zero,</span> <span
  m='2317740'>and</span> <span m='2317830'>it</span> <span
  m='2317890'>doesn't</span> <span m='2318190'>make</span> <span
  m='2318430'>it</span> <span m='2318490'>to</span> <span
  m='2318640'>infinity.</span> <span m='2319790'>So</span> <span
  m='2321100'>this</span> <span m='2321790'>is</span> <span m='2322210'>a</span>
  <span m='2322270'>two-sided</span> <span m='2322900'>sequence.</span>
  </p><p><span m='2324500'>The</span> <span m='2324620'>final</span> <span
  m='2325010'>example,</span> <span m='2325790'>or</span> <span
  m='2325880'>the</span> <span m='2326000'>final</span> <span
  m='2326330'>choice</span> <span m='2326660'>for</span> <span
  m='2326750'>the</span> <span m='2326870'>region</span> <span
  m='2327170'>of</span> <span m='2327260'>convergence,</span> <span
  m='2327860'>the</span> <span m='2327950'>magnitude</span> <span
  m='2328460'>of</span> <span m='2328550'>z</span> <span
  m='2328740'>greater</span> <span m='2329120'>than</span> <span
  m='2329300'>b.</span> <span m='2331150'>Does</span> <span
  m='2331300'>the</span> <span m='2331390'>Fourier</span> <span
  m='2331750'>transform</span> <span m='2332350'>exist?</span> <span
  m='2334540'>No,</span> <span m='2335050'>because</span> <span
  m='2336130'>the</span> <span m='2336250'>region</span> <span
  m='2336580'>of</span> <span m='2336670'>convergence</span> <span
  m='2337420'>is</span> <span m='2337600'>outside</span> <span
  m='2338170'>this</span> <span m='2338350'>pole.</span> <span
  m='2339430'>It</span> <span m='2339520'>doesn't</span> <span
  m='2339850'>include</span> <span m='2340180'>the</span> <span
  m='2340300'>unit</span> <span m='2340600'>circle,</span> <span
  m='2341660'>so</span> <span m='2343180'>the</span> <span
  m='2343300'>Fourier</span> <span m='2343690'>transform</span> <span
  m='2344290'>doesn't</span> <span m='2344650'>exist.</span> <span
  m='2346130'>Well,</span> <span m='2347800'>we</span> <span
  m='2347920'>can</span> <span m='2348040'>figure</span> <span
  m='2348430'>out</span> <span m='2350110'>which</span> <span
  m='2350290'>sided</span> <span m='2350630'>it</span> <span
  m='2350925'>is,</span> <span m='2351220'>either</span> <span
  m='2352150'>by</span> <span m='2352390'>using</span> <span
  m='2352780'>what</span> <span m='2352900'>we</span> <span
  m='2353050'>know,</span> <span m='2353300'>or</span> <span
  m='2353410'>using</span> <span m='2353740'>quizmanship.</span> <span
  m='2355240'>Here,</span> <span m='2355420'>we</span> <span
  m='2355560'>had</span> <span m='2355660'>left,</span> <span
  m='2355960'>here</span> <span m='2356100'>we</span> <span
  m='2356230'>had</span> <span m='2356380'>two-sided,</span> <span
  m='2357070'>so</span> <span m='2357250'>obviously</span> <span
  m='2357790'>it's</span> <span m='2357910'>right-sided.</span> <span
  m='2358900'>In</span> <span m='2358990'>fact,</span> <span
  m='2359290'>it</span> <span m='2359350'>is</span> <span
  m='2359500'>right-sided,</span> <span m='2360220'>because</span> <span
  m='2360730'>the</span> <span m='2360850'>region</span> <span
  m='2361120'>of</span> <span m='2361240'>convergence</span> <span
  m='2363130'>starts</span> <span m='2363670'>at</span> <span
  m='2363940'>some</span> <span m='2364180'>value</span> <span
  m='2364600'>r</span> <span m='2364780'>sub x</span> <span
  m='2365200'>minus,</span> <span m='2365860'>and</span> <span
  m='2365950'>goes</span> <span m='2366180'>out</span> <span
  m='2366360'>to</span> <span m='2366490'>infinity.</span> <span
  m='2367520'>So</span> <span m='2368740'>this</span> <span
  m='2368950'>case,</span> <span m='2369760'>then,</span> <span
  m='2371020'>is</span> <span m='2371140'>a</span> <span
  m='2371200'>right-sided</span> <span m='2371800'>sequence.</span> <span
  m='2373390'>This</span> <span m='2373570'>stresses,</span> <span
  m='2374050'>again,</span> <span m='2374720'>the</span> <span
  m='2374820'>point</span> <span m='2375760'>that,</span> <span
  m='2376540'>if</span> <span m='2377680'>I</span> <span m='2377950'>just</span>
  <span m='2378190'>specify</span> <span m='2378790'>the</span> <span
  m='2378910'>pole-zero</span> <span m='2379540'>pattern,</span> <span
  m='2380380'>that</span> <span m='2380710'>doesn't</span> <span
  m='2381070'>specify</span> <span m='2382240'>the</span> <span
  m='2382360'>Z-transform</span> <span m='2383350'>or</span> <span
  m='2383470'>the</span> <span m='2383590'>sequence</span> <span
  m='2384080'>uniquely.</span> </p><p><span m='2387730'>Now,</span> <span
  m='2388150'>one</span> <span m='2388390'>of</span> <span
  m='2388450'>the</span> <span m='2388540'>properties</span> <span
  m='2389530'>of</span> <span m='2390040'>the</span> <span
  m='2390250'>Z-transform,</span> <span m='2391990'>which</span> <span
  m='2392590'>follows</span> <span m='2393130'>essentially</span> <span
  m='2393610'>directly</span> <span m='2394270'>from</span> <span
  m='2394450'>the</span> <span m='2394570'>fact</span> <span
  m='2394900'>that</span> <span m='2395020'>the</span> <span
  m='2395110'>Z-transform</span> <span m='2396160'>is</span> <span
  m='2396310'>interpretable</span> <span m='2397630'>in</span> <span
  m='2397750'>terms</span> <span m='2398080'>of</span> <span
  m='2398140'>the</span> <span m='2398320'>Fourier</span> <span
  m='2398710'>transform--</span> <span m='2399430'>or</span> <span
  m='2399700'>this</span> <span m='2399880'>could</span> <span
  m='2400060'>be</span> <span m='2400180'>developed</span> <span
  m='2400570'>more</span> <span m='2400780'>formally,</span> <span
  m='2402700'>and</span> <span m='2402910'>we</span> <span
  m='2403030'>won't</span> <span m='2403240'>do</span> <span
  m='2403360'>that</span> <span m='2403600'>here--</span> <span
  m='2405040'>is</span> <span m='2405220'>the</span> <span
  m='2405340'>convolution</span> <span m='2406090'>property.</span> <span
  m='2406900'>Namely,</span> <span m='2407950'>if</span> <span
  m='2408100'>y</span> <span m='2408380'>of</span> <span m='2408560'>n</span>
  <span m='2408690'>is</span> <span m='2408820'>the</span> <span
  m='2408940'>convolution</span> <span m='2409600'>of</span> <span
  m='2409690'>x</span> <span m='2409930'>of</span> <span m='2410080'>n</span>
  <span m='2410500'>with h</span> <span m='2410965'>of</span> <span
  m='2411430'>n,</span> <span m='2412360'>then</span> <span
  m='2412990'>the</span> <span m='2413110'>Z-transform</span> <span
  m='2414430'>of</span> <span m='2414580'>y</span> <span m='2414880'>of</span>
  <span m='2415030'>n</span> <span m='2416700'>is</span> <span
  m='2416850'>equal</span> <span m='2417180'>to</span> <span
  m='2417300'>the</span> <span m='2417390'>product</span> <span
  m='2418560'>of</span> <span m='2418815'>the</span> <span
  m='2419070'>Z-transform</span> <span m='2420240'>of</span> <span
  m='2420360'>x</span> <span m='2420600'>of</span> <span m='2420750'>n</span>
  <span m='2421770'>and</span> <span m='2422310'>the</span> <span
  m='2422610'>Z-transform</span> <span m='2423540'>of</span> <span
  m='2423630'>h</span> <span m='2423870'>of n.</span> <span
  m='2424650'>That</span> <span m='2424860'>is,</span> <span
  m='2425940'>z</span> <span m='2426180'>transformation,</span> <span
  m='2427410'>or</span> <span m='2427560'>the</span> <span
  m='2427650'>Z-transform,</span> <span m='2429030'>maps</span> <span
  m='2429750'>convolution</span> <span m='2431190'>into</span> <span
  m='2431430'>multiplication,</span> <span m='2432900'>just</span> <span
  m='2433230'>like</span> <span m='2433530'>the</span> <span
  m='2433620'>Fourier</span> <span m='2434070'>transform</span> <span
  m='2434730'>did.</span> <span m='2435160'>And</span> <span
  m='2435180'>that's</span> <span m='2435390'>not</span> <span
  m='2435580'>surprising.</span> </p><p><span m='2437930'>We</span> <span
  m='2438260'>typically</span> <span m='2439430'>refer</span> <span
  m='2440240'>to</span> <span m='2441530'>h</span> <span m='2441840'>of</span>
  <span m='2442000'>z,</span> <span m='2442325'>the</span> <span
  m='2443080'>Z-transform</span> <span m='2444500'>of</span> <span
  m='2444770'>the</span> <span m='2444890'>unit</span> <span
  m='2445130'>sample</span> <span m='2445550'>response</span> <span
  m='2446060'>of</span> <span m='2446120'>the</span> <span
  m='2446240'>system,</span> <span m='2447320'>as</span> <span
  m='2448280'>the</span> <span m='2448370'>system</span> <span
  m='2448790'>function.</span> <span m='2451260'>Well,</span> <span
  m='2451490'>on</span> <span m='2451610'>the</span> <span
  m='2451700'>basis</span> <span m='2452150'>of</span> <span
  m='2452240'>the</span> <span m='2452360'>discussion</span> <span
  m='2452930'>that</span> <span m='2453020'>we</span> <span
  m='2453140'>just</span> <span m='2453380'>finished,</span> <span
  m='2454550'>there</span> <span m='2454940'>are</span> <span
  m='2455120'>some</span> <span m='2455330'>things</span> <span
  m='2455630'>that</span> <span m='2455750'>we</span> <span
  m='2455870'>can</span> <span m='2456050'>say</span> <span
  m='2456860'>about</span> <span m='2457280'>the</span> <span
  m='2457370'>system</span> <span m='2457790'>function</span> <span
  m='2458450'>and</span> <span m='2458570'>the</span> <span
  m='2458660'>unit</span> <span m='2458930'>sample</span> <span
  m='2459350'>response</span> <span m='2460040'>and</span> <span
  m='2460130'>regions</span> <span m='2460550'>of</span> <span
  m='2460640'>convergence,</span> <span m='2461045'>et</span> <span
  m='2461450'>cetera.</span> <span m='2463830'>First</span> <span
  m='2464160'>of</span> <span m='2464310'>all,</span> <span
  m='2465330'>suppose</span> <span m='2466080'>that</span> <span
  m='2466890'>we're</span> <span m='2467040'>talking</span> <span
  m='2467550'>about</span> <span m='2468180'>a</span> <span
  m='2468240'>stable</span> <span m='2468690'>system.</span> <span
  m='2470380'>Stable</span> <span m='2470830'>system,</span> <span
  m='2472060'>the</span> <span m='2472510'>unit</span> <span
  m='2472840'>sample</span> <span m='2473200'>response</span> <span
  m='2473710'>is</span> <span m='2473830'>absolutely</span> <span
  m='2474370'>summable.</span> </p><p><span m='2475660'>What</span> <span
  m='2475840'>does</span> <span m='2475960'>that</span> <span
  m='2476170'>imply</span> <span m='2476590'>about</span> <span
  m='2476860'>the</span> <span m='2476950'>Z-transform?</span> <span
  m='2478450'>Well,</span> <span m='2479230'>it</span> <span
  m='2479380'>implies</span> <span m='2480430'>that</span> <span
  m='2480790'>the</span> <span m='2480880'>Z-transform,</span> <span
  m='2484410'>the</span> <span m='2484560'>region</span> <span
  m='2484800'>of</span> <span m='2484890'>convergence</span> <span
  m='2485175'>of</span> <span m='2485460'>the</span> <span
  m='2485520'>Z-transform</span> <span m='2486690'>includes</span> <span
  m='2487350'>the</span> <span m='2487470'>unit</span> <span
  m='2487740'>circle.</span> <span m='2488490'>That</span> <span
  m='2488610'>is,</span> <span m='2488730'>it</span> <span
  m='2488820'>implies</span> <span m='2489210'>the</span> <span
  m='2489630'>Fourier</span> <span m='2489730'>transform</span> <span
  m='2490230'>exists,</span> <span m='2490650'>or,</span> <span
  m='2490800'>equivalently,</span> <span m='2492030'>that</span> <span
  m='2492150'>the</span> <span m='2492270'>Z-transform</span> <span
  m='2493650'>region</span> <span m='2493980'>of</span> <span
  m='2494070'>convergence</span> <span m='2494760'>includes</span> <span
  m='2495210'>the</span> <span m='2495300'>unit</span> <span
  m='2495600'>circle.</span> <span m='2496660'>So</span> <span
  m='2497130'>this</span> <span m='2497340'>is</span> <span m='2497460'>a</span>
  <span m='2497520'>statement</span> <span m='2498000'>that</span> <span
  m='2498120'>we</span> <span m='2498270'>can</span> <span
  m='2498420'>make.</span> </p><p><span m='2500610'>Suppose</span> <span
  m='2501240'>that</span> <span m='2501360'>we</span> <span
  m='2501540'>were</span> <span m='2501660'>talking</span> <span
  m='2502140'>about</span> <span m='2502410'>a</span> <span
  m='2502440'>stable</span> <span m='2502950'>system.</span> <span
  m='2504360'>Sorry,</span> <span m='2504690'>suppose</span> <span
  m='2505000'>that</span> <span m='2505060'>we</span> <span
  m='2505140'>were</span> <span m='2505230'>talking</span> <span
  m='2505500'>about</span> <span m='2505620'>a</span> <span
  m='2505680'>causal</span> <span m='2506100'>system.</span> <span
  m='2507510'>If</span> <span m='2507660'>the</span> <span
  m='2507750'>system</span> <span m='2508170'>is</span> <span
  m='2508290'>causal,</span> <span m='2510280'>well,</span> <span
  m='2510550'>what</span> <span m='2510700'>does</span> <span
  m='2510820'>causal</span> <span m='2511210'>mean?</span> <span
  m='2511640'>It</span> <span m='2511740'>means</span> <span
  m='2512740'>that</span> <span m='2513730'>the</span> <span
  m='2513850'>unit</span> <span m='2514120'>sample</span> <span
  m='2514510'>response</span> <span m='2515470'>is</span> <span
  m='2515590'>zero</span> <span m='2516040'>for</span> <span
  m='2516250'>n</span> <span m='2516400'>less</span> <span
  m='2516640'>than</span> <span m='2516820'>zero.</span> <span
  m='2517720'>In</span> <span m='2517840'>particular,</span> <span
  m='2518740'>the</span> <span m='2518860'>unit</span> <span
  m='2519130'>sample</span> <span m='2519550'>response</span> <span
  m='2520390'>is</span> <span m='2520540'>right-sided.</span> <span
  m='2522400'>If</span> <span m='2522550'>it's</span> <span
  m='2522700'>right-sided,</span> <span m='2524200'>then</span> <span
  m='2524710'>the</span> <span m='2524830'>region</span> <span
  m='2525160'>of</span> <span m='2525250'>convergence</span> <span
  m='2526480'>must</span> <span m='2526690'>be</span> <span
  m='2526930'>outside</span> <span m='2527980'>the</span> <span
  m='2528130'>outermost</span> <span m='2528700'>pole,</span> <span
  m='2529990'>because</span> <span m='2530920'>that's</span> <span
  m='2531370'>what</span> <span m='2531550'>we</span> <span
  m='2531670'>said</span> <span m='2531940'>about</span> <span
  m='2532510'>what</span> <span m='2532720'>happens</span> <span
  m='2533200'>with</span> <span m='2533350'>a</span> <span
  m='2533380'>right-sided</span> <span m='2533980'>sequence.</span> <span
  m='2534490'>The</span> <span m='2534610'>region</span> <span
  m='2534880'>of</span> <span m='2534970'>convergence</span> <span
  m='2535930'>has</span> <span m='2536170'>to</span> <span m='2536320'>be</span>
  <span m='2536950'>outside</span> <span m='2537430'>the</span> <span
  m='2537610'>outermost</span> <span m='2538090'>pole.</span> <span
  m='2539080'>So</span> <span m='2540070'>you</span> <span
  m='2540190'>can</span> <span m='2540400'>get</span> <span
  m='2540610'>the</span> <span m='2540730'>notion,</span> <span
  m='2541125'>then,</span> <span m='2541870'>that</span> <span
  m='2542440'>when</span> <span m='2542590'>we</span> <span
  m='2542680'>talk</span> <span m='2543010'>about</span> <span
  m='2543250'>the</span> <span m='2543340'>Z-transform</span> <span
  m='2544150'>of</span> <span m='2544220'>a</span> <span
  m='2544330'>system,</span> <span m='2545290'>in</span> <span
  m='2545440'>essence</span> <span m='2545960'>we</span> <span
  m='2546010'>can</span> <span m='2546280'>imply</span> <span
  m='2547030'>the</span> <span m='2547150'>region</span> <span
  m='2547480'>of</span> <span m='2547570'>convergence</span> <span
  m='2548920'>by</span> <span m='2549310'>making</span> <span
  m='2549700'>some</span> <span m='2549880'>statements</span> <span
  m='2550390'>about</span> <span m='2550690'>stability</span> <span
  m='2551320'>or</span> <span m='2551410'>causality.</span> </p><p><span
  m='2553760'>All</span> <span m='2553860'>right.</span> <span
  m='2553950'>Let's</span> <span m='2555190'>try</span> <span
  m='2555430'>this</span> <span m='2555640'>out</span> <span
  m='2555880'>on</span> <span m='2556030'>an</span> <span
  m='2556150'>example.</span> <span m='2557380'>Let's</span> <span
  m='2557680'>take</span> <span m='2557920'>an</span> <span
  m='2558010'>example</span> <span m='2558520'>which,</span> <span
  m='2558760'>in</span> <span m='2558880'>fact,</span> <span
  m='2560230'>we've</span> <span m='2560530'>talked</span> <span
  m='2560950'>about</span> <span m='2561490'>in</span> <span
  m='2561640'>some</span> <span m='2561850'>lectures--</span> <span
  m='2562480'>in</span> <span m='2562600'>a</span> <span
  m='2562630'>lecture</span> <span m='2562960'>previously.</span> <span
  m='2565040'>Let's</span> <span m='2565180'>take</span> <span
  m='2565450'>the</span> <span m='2565570'>example</span> <span
  m='2566020'>of</span> <span m='2566110'>a</span> <span
  m='2566140'>system</span> <span m='2567700'>that</span> <span
  m='2568150'>is</span> <span m='2569860'>represented</span> <span
  m='2570850'>by</span> <span m='2571300'>a</span> <span
  m='2571390'>linear</span> <span m='2571720'>constant</span> <span
  m='2572140'>coefficient</span> <span m='2572740'>difference</span> <span
  m='2573130'>equation,</span> <span m='2574360'>y</span> <span m='2574620'>of
  n</span> <span m='2575020'>minus</span> <span m='2575380'>1/2,</span> <span
  m='2575850'>y</span> <span m='2576100'>of n</span> <span
  m='2576340'>minus</span> <span m='2576730'>1</span> <span
  m='2577180'>equals</span> <span m='2577510'>x</span> <span m='2577780'>of
  n.</span> <span m='2579600'>To</span> <span m='2579780'>get</span> <span
  m='2580330'>the</span> <span m='2580930'>system</span> <span
  m='2581350'>function</span> <span m='2582010'>for</span> <span
  m='2582220'>this,</span> <span m='2583150'>we'll</span> <span
  m='2583300'>take</span> <span m='2583510'>a</span> <span
  m='2583580'>shortcut.</span> <span m='2585156'>And</span> <span
  m='2585610'>in</span> <span m='2585750'>particular,</span> <span
  m='2587110'>we'll</span> <span m='2587260'>use</span> <span
  m='2587530'>a</span> <span m='2587590'>property</span> <span
  m='2588370'>that</span> <span m='2589030'>we</span> <span
  m='2589150'>haven't</span> <span m='2589690'>derived,</span> <span
  m='2591040'>at</span> <span m='2591130'>least</span> <span
  m='2591340'>not</span> <span m='2591580'>yet,</span> <span
  m='2593350'>but</span> <span m='2593800'>in</span> <span
  m='2593920'>fact</span> <span m='2594290'>you'll</span> <span
  m='2594310'>be</span> <span m='2594460'>deriving</span> <span
  m='2595090'>in</span> <span m='2595210'>the</span> <span
  m='2595600'>study</span> <span m='2595990'>guide.</span> <span
  m='2597500'>Notice</span> <span m='2597670'>how</span> <span
  m='2597790'>I</span> <span m='2597850'>put</span> <span
  m='2598000'>everything</span> <span m='2598300'>off</span> <span
  m='2598480'>to</span> <span m='2598600'>the</span> <span
  m='2598690'>study</span> <span m='2599020'>guide.</span> <span
  m='2600940'>When</span> <span m='2601030'>we</span> <span
  m='2601120'>get</span> <span m='2601270'>the</span> <span
  m='2601410'>study</span> <span m='2601690'>guide,</span> <span
  m='2601900'>I'll</span> <span m='2601990'>tell</span> <span
  m='2602140'>you</span> <span m='2602260'>we</span> <span
  m='2602380'>did</span> <span m='2602530'>it</span> <span m='2602590'>in</span>
  <span m='2602720'>lecture.</span> </p><p><span m='2604840'>Well,</span> <span
  m='2605440'>the</span> <span m='2605530'>property</span> <span
  m='2606070'>is</span> <span m='2606850'>that</span> <span
  m='2607630'>if</span> <span m='2608140'>the</span> <span
  m='2608260'>Z-transform</span> <span m='2609130'>of</span> <span
  m='2609250'>y</span> <span m='2609520'>of</span> <span m='2609660'>n</span>
  <span m='2610240'>is</span> <span m='2610390'>y</span> <span
  m='2610690'>of</span> <span m='2610810'>z,</span> <span
  m='2612160'>then</span> <span m='2612760'>the</span> <span
  m='2612880'>Z-transform</span> <span m='2613780'>of</span> <span
  m='2613840'>y</span> <span m='2614110'>of</span> <span m='2614230'>n</span>
  <span m='2614380'>plus</span> <span m='2614680'>n0</span> <span
  m='2615850'>is</span> <span m='2616070'>z</span> <span m='2616330'>to</span>
  <span m='2616480'>the</span> <span m='2616660'>n0</span> <span
  m='2617590'>times</span> <span m='2617920'>y</span> <span
  m='2618190'>and</span> <span m='2618280'>z.</span> <span m='2620090'>So</span>
  <span m='2620450'>if</span> <span m='2620600'>we</span> <span
  m='2620720'>take</span> <span m='2620990'>the</span> <span
  m='2621080'>Z-transform</span> <span m='2622310'>of</span> <span
  m='2622430'>this</span> <span m='2622610'>difference</span> <span
  m='2623000'>equation,</span> <span m='2624290'>we</span> <span
  m='2624470'>have,</span> <span m='2625520'>then,</span> <span
  m='2625850'>y</span> <span m='2626180'>of</span> <span m='2626540'>z,</span>
  <span m='2626930'>the</span> <span m='2627320'>Z-transform</span> <span
  m='2628010'>of</span> <span m='2628310'>that</span> <span
  m='2629180'>minus</span> <span m='2629630'>1/2</span> <span
  m='2630470'>z</span> <span m='2630740'>to</span> <span m='2630890'>the</span>
  <span m='2630980'>minus</span> <span m='2631400'>1,</span> <span
  m='2631820'>since</span> <span m='2632060'>we</span> <span
  m='2632150'>have</span> <span m='2632270'>y</span> <span m='2632510'>of
  n</span> <span m='2632720'>minus</span> <span m='2633110'>1,</span> <span
  m='2633500'>z</span> <span m='2633820'>to</span> <span m='2634260'>the</span>
  <span m='2634400'>minus</span> <span m='2634790'>1</span> <span
  m='2635240'>y</span> <span m='2635555'>of</span> <span m='2635870'>z</span>
  <span m='2636800'>is</span> <span m='2636980'>equal</span> <span
  m='2637280'>to</span> <span m='2637430'>the</span> <span
  m='2637520'>Z-transform</span> <span m='2638210'>of</span> <span
  m='2638270'>the</span> <span m='2638360'>right</span> <span
  m='2638630'>side</span> <span m='2638900'>of</span> <span
  m='2638960'>the</span> <span m='2639080'>equation,</span> <span
  m='2639660'>which</span> <span m='2639710'>is</span> <span
  m='2639830'>x</span> <span m='2640060'>of</span> <span m='2640180'>z.</span>
  </p><p><span m='2642230'>Well,</span> <span m='2644030'>the</span> <span
  m='2644330'>system</span> <span m='2644840'>function</span> <span
  m='2645710'>is</span> <span m='2645860'>equal</span> <span
  m='2646130'>to</span> <span m='2646280'>y</span> <span m='2646610'>of</span>
  <span m='2646730'>z</span> <span m='2646970'>divided</span> <span
  m='2647390'>by</span> <span m='2647600'>x</span> <span m='2647870'>of</span>
  <span m='2647990'>z.</span> <span m='2649670'>And</span> <span
  m='2650440'>so</span> <span m='2650710'>we</span> <span m='2650830'>can</span>
  <span m='2650980'>simply</span> <span m='2651340'>solve</span> <span
  m='2652030'>this</span> <span m='2652270'>equation</span> <span
  m='2653350'>for</span> <span m='2653530'>y of</span> <span
  m='2653830'>z</span> <span m='2654370'>over</span> <span m='2654700'>x</span>
  <span m='2654940'>of z.</span> <span m='2655900'>And</span> <span
  m='2656020'>what</span> <span m='2656140'>we</span> <span
  m='2656320'>get</span> <span m='2656680'>is</span> <span m='2657410'>1</span>
  <span m='2657700'>over</span> <span m='2658240'>1</span> <span
  m='2658480'>minus</span> <span m='2658870'>1/2</span> <span
  m='2659590'>times</span> <span m='2660030'>z</span> <span
  m='2660160'>to</span> <span m='2660280'>the</span> <span
  m='2660370'>minus</span> <span m='2660760'>1.</span> <span
  m='2662510'>So</span> <span m='2663100'>that's</span> <span
  m='2663400'>the</span> <span m='2663490'>system</span> <span
  m='2663910'>function</span> <span m='2664810'>for</span> <span
  m='2664930'>that</span> <span m='2665200'>system.</span> <span
  m='2668950'>Well,</span> <span m='2669520'>what's</span> <span
  m='2669790'>the</span> <span m='2669880'>region</span> <span
  m='2670180'>of</span> <span m='2670240'>convergence?</span> </p><p><span
  m='2673050'>We</span> <span m='2673150'>don't</span> <span
  m='2673190'>know</span> <span m='2673370'>what</span> <span
  m='2673520'>the</span> <span m='2673640'>region</span> <span
  m='2673940'>of</span> <span m='2674030'>convergence</span> <span
  m='2674690'>is.</span> <span m='2676010'>In</span> <span
  m='2676130'>fact,</span> <span m='2676520'>we're</span> <span
  m='2676670'>going</span> <span m='2676790'>to</span> <span
  m='2676850'>have</span> <span m='2677120'>to--</span> <span
  m='2677930'>in</span> <span m='2678050'>fact,</span> <span
  m='2678290'>there</span> <span m='2678380'>might</span> <span
  m='2678650'>be</span> <span m='2679130'>several</span> <span
  m='2679550'>choices</span> <span m='2680030'>for</span> <span
  m='2680150'>the</span> <span m='2680240'>region</span> <span
  m='2680540'>of</span> <span m='2680630'>convergence.</span> <span
  m='2682400'>But</span> <span m='2682730'>that's</span> <span
  m='2682940'>not</span> <span m='2683150'>too</span> <span
  m='2683300'>surprising,</span> <span m='2684060'>because</span> <span
  m='2684770'>remember</span> <span m='2685160'>when</span> <span
  m='2685340'>we</span> <span m='2685490'>talked</span> <span
  m='2685820'>about</span> <span m='2686090'>this</span> <span
  m='2686270'>equation</span> <span m='2686780'>a</span> <span
  m='2686840'>couple</span> <span m='2687140'>of</span> <span
  m='2687230'>lectures</span> <span m='2687650'>ago</span> <span
  m='2688760'>and</span> <span m='2689240'>we</span> <span
  m='2689420'>showed</span> <span m='2689770'>that,</span> <span
  m='2689930'>in</span> <span m='2690050'>fact,</span> <span
  m='2691640'>there</span> <span m='2692090'>is</span> <span
  m='2692300'>more</span> <span m='2692630'>than</span> <span
  m='2692780'>one</span> <span m='2693020'>choice</span> <span
  m='2693470'>for</span> <span m='2693620'>the</span> <span
  m='2693710'>unit</span> <span m='2693980'>sample</span> <span
  m='2694370'>response</span> <span m='2695050'>of</span> <span
  m='2695160'>this</span> <span m='2695400'>system.</span> <span
  m='2697280'>And</span> <span m='2697880'>that</span> <span
  m='2699280'>is</span> <span m='2699730'>related</span> <span
  m='2700300'>to</span> <span m='2700450'>the</span> <span
  m='2700570'>fact</span> <span m='2701350'>that</span> <span
  m='2701530'>all</span> <span m='2701800'>we</span> <span
  m='2701920'>got</span> <span m='2702190'>out</span> <span
  m='2702370'>of</span> <span m='2702520'>here</span> <span
  m='2703090'>so</span> <span m='2703360'>far</span> <span
  m='2704560'>was</span> <span m='2705040'>the</span> <span
  m='2705160'>ratio</span> <span m='2705580'>of</span> <span
  m='2705670'>polynomials</span> <span m='2706600'>that</span> <span
  m='2706750'>h</span> <span m='2706990'>of</span> <span m='2707080'>z</span>
  <span m='2707440'>is,</span> <span m='2708550'>and</span> <span
  m='2708730'>not</span> <span m='2709060'>what</span> <span
  m='2709240'>the</span> <span m='2709330'>region</span> <span
  m='2709690'>of</span> <span m='2709780'>convergence</span> <span
  m='2710120'>is.</span> </p><p><span m='2712135'>All</span> <span
  m='2712580'>right,</span> <span m='2712830'>so</span> <span
  m='2712950'>this</span> <span m='2713160'>ratio</span> <span
  m='2713580'>of</span> <span m='2713670'>polynomials</span> <span
  m='2714690'>is</span> <span m='2714870'>1</span> <span m='2715140'>over</span>
  <span m='2715410'>1</span> <span m='2715620'>minus</span> <span
  m='2715980'>1/2</span> <span m='2716600'>times</span> <span
  m='2716880'>z</span> <span m='2717090'>to</span> <span m='2717180'>the</span>
  <span m='2717270'>minus</span> <span m='2717660'>1.</span> <span
  m='2717960'>We've</span> <span m='2718080'>been</span> <span
  m='2718260'>staring</span> <span m='2718830'>at</span> <span
  m='2718920'>that</span> <span m='2719130'>ratio</span> <span
  m='2719520'>of</span> <span m='2719580'>polynomials</span> <span
  m='2720390'>through</span> <span m='2720600'>a</span> <span
  m='2720660'>couple</span> <span m='2720960'>of</span> <span
  m='2721050'>previous</span> <span m='2721500'>examples.</span> <span
  m='2723030'>It</span> <span m='2723150'>has</span> <span m='2723390'>a</span>
  <span m='2723450'>zero</span> <span m='2724050'>at</span> <span
  m='2724590'>z</span> <span m='2725040'>equals</span> <span
  m='2725340'>0,</span> <span m='2725640'>and</span> <span m='2725760'>a</span>
  <span m='2725810'>pole</span> <span m='2726420'>at</span> <span
  m='2726900'>z</span> <span m='2727170'>equals</span> <span
  m='2727500'>1/2.</span> <span m='2728640'>So</span> <span
  m='2728820'>let's</span> <span m='2729180'>take</span> <span
  m='2729420'>a</span> <span m='2729480'>look</span> <span m='2729720'>at</span>
  <span m='2729840'>that</span> <span m='2730380'>in</span> <span
  m='2731040'>the</span> <span m='2731835'>z-plane.</span> </p><p><span
  m='2737650'>We</span> <span m='2737800'>have</span> <span
  m='2738550'>then</span> <span m='2739360'>the</span> <span
  m='2739450'>z-plane</span> <span m='2741530'>here,</span> <span
  m='2742420'>the</span> <span m='2742540'>unit</span> <span
  m='2742840'>circle.</span> <span m='2744730'>We</span> <span
  m='2744880'>have,</span> <span m='2745215'>for</span> <span
  m='2745550'>the</span> <span m='2745690'>example</span> <span
  m='2746170'>we're</span> <span m='2746290'>talking</span> <span
  m='2746800'>about,</span> <span m='2747740'>a</span> <span
  m='2747990'>zero</span> <span m='2749050'>there,</span> <span
  m='2750460'>and</span> <span m='2750670'>a</span> <span
  m='2750800'>pole</span> <span m='2751900'>there.</span> <span
  m='2753640'>And</span> <span m='2753730'>what's</span> <span
  m='2753940'>the</span> <span m='2754030'>region</span> <span
  m='2754330'>of</span> <span m='2754390'>convergence?</span> <span
  m='2755930'>Well,</span> <span m='2756220'>it</span> <span
  m='2756340'>seems</span> <span m='2756700'>like</span> <span
  m='2757120'>we</span> <span m='2757300'>can</span> <span
  m='2757450'>take</span> <span m='2757690'>the</span> <span
  m='2757780'>region</span> <span m='2758080'>of</span> <span
  m='2758170'>convergence</span> <span m='2758980'>to</span> <span
  m='2759130'>be</span> <span m='2759490'>whatever</span> <span
  m='2759880'>we</span> <span m='2760030'>want</span> <span
  m='2760300'>to</span> <span m='2760490'>consistent</span> <span
  m='2761560'>with</span> <span m='2762000'>what</span> <span
  m='2762250'>regions</span> <span m='2762670'>of</span> <span
  m='2762760'>convergences</span> <span m='2763810'>tend</span> <span
  m='2764080'>to</span> <span m='2764230'>do.</span> <span m='2765460'>So</span>
  <span m='2765820'>let's</span> <span m='2766090'>say,</span> <span
  m='2766460'>for</span> <span m='2766570'>example,</span> <span
  m='2767810'>that</span> <span m='2768250'>the</span> <span
  m='2768370'>region</span> <span m='2768700'>of</span> <span
  m='2768790'>convergence</span> <span m='2769660'>was</span> <span
  m='2769870'>outside</span> <span m='2770380'>that</span> <span
  m='2770560'>pole.</span> <span m='2771610'>So</span> <span
  m='2772270'>let's</span> <span m='2772600'>take</span> <span
  m='2773410'>a</span> <span m='2773470'>region</span> <span
  m='2773830'>of</span> <span m='2773920'>convergence</span> <span
  m='2776210'>first</span> <span m='2776900'>that</span> <span
  m='2777020'>looks</span> <span m='2777290'>like</span> <span
  m='2777752'>that.</span> </p><p><span m='2780530'>Well,</span> <span
  m='2781610'>for</span> <span m='2781790'>that</span> <span
  m='2782030'>case,</span> <span m='2782930'>if</span> <span
  m='2783080'>that's</span> <span m='2783320'>the</span> <span
  m='2783410'>region</span> <span m='2783710'>of</span> <span
  m='2783800'>convergence,</span> <span m='2784520'>there</span> <span
  m='2784670'>are</span> <span m='2784700'>some</span> <span
  m='2784910'>things</span> <span m='2785240'>that</span> <span
  m='2785360'>we</span> <span m='2785480'>could</span> <span
  m='2785660'>say</span> <span m='2786440'>about</span> <span
  m='2787610'>the</span> <span m='2787700'>system.</span> <span
  m='2788250'>For</span> <span m='2788300'>example,</span> <span
  m='2788780'>is</span> <span m='2788930'>the</span> <span
  m='2789020'>system</span> <span m='2789440'>stable?</span> <span
  m='2791120'>Is</span> <span m='2791185'>the</span> <span
  m='2791250'>system</span> <span m='2791660'>stable</span> <span
  m='2792170'>if</span> <span m='2792290'>the</span> <span
  m='2792380'>unit</span> <span m='2792650'>sample</span> <span
  m='2793100'>response</span> <span m='2795350'>has</span> <span
  m='2795500'>a</span> <span m='2795560'>Fourier</span> <span
  m='2795980'>transform?</span> <span m='2796790'>And</span> <span
  m='2796970'>it</span> <span m='2797420'>has</span> <span
  m='2797720'>that</span> <span m='2798170'>if</span> <span
  m='2798830'>the</span> <span m='2799610'>region</span> <span
  m='2799970'>of</span> <span m='2800060'>convergence</span> <span
  m='2800660'>includes</span> <span m='2801320'>the</span> <span
  m='2801410'>unit</span> <span m='2801680'>circle,</span> <span
  m='2802610'>which</span> <span m='2802790'>it</span> <span
  m='2802880'>does</span> <span m='2803180'>here.</span> <span
  m='2804280'>So</span> <span m='2805250'>this</span> <span
  m='2805460'>particular</span> <span m='2806000'>system</span> <span
  m='2807650'>is</span> <span m='2807770'>stable.</span> </p><p><span
  m='2810300'>And</span> <span m='2811110'>is</span> <span m='2811260'>it</span>
  <span m='2811350'>causal?</span> <span m='2813100'>Well,</span> <span
  m='2813790'>what</span> <span m='2814120'>we</span> <span
  m='2814240'>want</span> <span m='2814450'>to</span> <span
  m='2814540'>examine</span> <span m='2815080'>for</span> <span
  m='2815200'>that</span> <span m='2815380'>region</span> <span
  m='2815680'>of</span> <span m='2815770'>convergence</span> <span
  m='2816580'>is</span> <span m='2817360'>does</span> <span
  m='2817810'>it</span> <span m='2817930'>imply</span> <span
  m='2818650'>a</span> <span m='2819070'>right-sided</span> <span
  m='2819730'>sequence.</span> <span m='2820790'>Well,</span> <span
  m='2820930'>it</span> <span m='2821080'>does,</span> <span
  m='2821380'>because</span> <span m='2821680'>the</span> <span
  m='2821770'>region</span> <span m='2822070'>of</span> <span
  m='2822160'>convergence</span> <span m='2822760'>is</span> <span
  m='2822910'>outside</span> <span m='2823360'>this</span> <span
  m='2823540'>pole.</span> <span m='2824530'>So</span> <span
  m='2824740'>in</span> <span m='2824860'>fact,</span> <span
  m='2825760'>for</span> <span m='2825880'>this</span> <span
  m='2826120'>example,</span> <span m='2828700'>the</span> <span
  m='2829420'>system</span> <span m='2829990'>is</span> <span
  m='2830200'>also</span> <span m='2830560'>causal.</span> <span
  m='2831820'>And</span> <span m='2831910'>in</span> <span
  m='2832000'>fact,</span> <span m='2832540'>look,</span> <span
  m='2832750'>we</span> <span m='2832900'>know</span> <span
  m='2833110'>what</span> <span m='2833260'>the</span> <span
  m='2833350'>unit</span> <span m='2833590'>sample</span> <span
  m='2833980'>response</span> <span m='2834490'>is</span> <span
  m='2834670'>because</span> <span m='2835300'>we've</span> <span
  m='2835480'>been</span> <span m='2835600'>working</span> <span
  m='2835960'>with</span> <span m='2836080'>that</span> <span
  m='2836290'>example</span> <span m='2836770'>previously.</span> <span
  m='2838060'>The</span> <span m='2838150'>unit</span> <span
  m='2838450'>sample</span> <span m='2838870'>response</span> <span
  m='2839500'>here,</span> <span m='2840050'>in</span> <span
  m='2840100'>fact,</span> <span m='2841090'>is</span> <span
  m='2841330'>h</span> <span m='2841680'>of n</span> <span m='2842700'>is</span>
  <span m='2842950'>1/2</span> <span m='2843950'>to</span> <span
  m='2844120'>the</span> <span m='2844300'>n</span> <span
  m='2845140'>times</span> <span m='2846200'>a</span> <span
  m='2846330'>unit</span> <span m='2846690'>step.</span> </p><p><span
  m='2849890'>But</span> <span m='2850070'>that's</span> <span
  m='2850310'>not</span> <span m='2850520'>the</span> <span
  m='2850640'>only</span> <span m='2850880'>choice</span> <span
  m='2851270'>for</span> <span m='2851390'>the</span> <span
  m='2851480'>region</span> <span m='2851810'>of</span> <span
  m='2851900'>convergence.</span> <span m='2853560'>We</span> <span
  m='2853610'>could,</span> <span m='2854000'>alternatively,</span> <span
  m='2855770'>pick</span> <span m='2856100'>a</span> <span
  m='2856190'>region</span> <span m='2856520'>of</span> <span
  m='2856610'>convergence</span> <span m='2857330'>which</span> <span
  m='2857540'>is</span> <span m='2857660'>inside</span> <span
  m='2858140'>that</span> <span m='2858350'>pole.</span> <span
  m='2859070'>That</span> <span m='2859220'>is--</span> <span
  m='2859850'>let's</span> <span m='2860090'>look</span> <span
  m='2860300'>at</span> <span m='2860390'>this</span> <span
  m='2860600'>again.</span> <span m='2862690'>Zero</span> <span
  m='2863080'>at</span> <span m='2863200'>the</span> <span
  m='2863350'>origin,</span> <span m='2864040'>a</span> <span
  m='2864450'>pole</span> <span m='2864860'>at</span> <span
  m='2865270'>equals</span> <span m='2865660'>z</span> <span
  m='2865925'>equals</span> <span m='2866190'>1/2.</span> <span
  m='2867830'>But</span> <span m='2868010'>now</span> <span
  m='2868310'>let's</span> <span m='2868580'>take</span> <span
  m='2868820'>the</span> <span m='2868940'>region</span> <span
  m='2869300'>of</span> <span m='2869420'>convergence</span> <span
  m='2870980'>to</span> <span m='2871100'>be</span> <span
  m='2871670'>inside</span> <span m='2872180'>that</span> <span
  m='2872390'>pole.</span> <span m='2874740'>If</span> <span
  m='2874890'>it's</span> <span m='2875040'>inside</span> <span
  m='2875490'>that</span> <span m='2875740'>pole,</span> <span
  m='2876840'>then,</span> <span m='2877860'>first</span> <span
  m='2878160'>of</span> <span m='2878250'>all,</span> <span
  m='2878340'>is</span> <span m='2878460'>the</span> <span
  m='2878520'>system</span> <span m='2878940'>stable?</span> <span
  m='2879840'>No,</span> <span m='2880050'>it's</span> <span
  m='2880170'>not</span> <span m='2880410'>stable,</span> <span
  m='2880860'>because</span> <span m='2881310'>the</span> <span
  m='2881400'>region</span> <span m='2881670'>of</span> <span
  m='2881760'>convergence</span> <span m='2882420'>didn't</span> <span
  m='2882630'>include</span> <span m='2882990'>the</span> <span
  m='2883110'>unit</span> <span m='2883380'>circle.</span> </p><p><span
  m='2884440'>So</span> <span m='2884790'>it's</span> <span
  m='2884970'>not</span> <span m='2885240'>stable.</span> <span
  m='2888550'>And</span> <span m='2888850'>furthermore,</span> <span
  m='2889450'>it's</span> <span m='2889600'>not</span> <span
  m='2889840'>causal.</span> <span m='2890500'>In</span> <span
  m='2890590'>fact,</span> <span m='2890890'>it's</span> <span
  m='2891010'>just</span> <span m='2891220'>the</span> <span
  m='2891340'>reverse.</span> <span m='2891730'>It's</span> <span
  m='2891880'>anti-causal.</span> <span m='2893950'>It's</span> <span
  m='2894160'>not</span> <span m='2894790'>causal.</span> <span
  m='2897470'>And</span> <span m='2897490'>in</span> <span
  m='2897610'>fact,</span> <span m='2898900'>we</span> <span
  m='2899050'>know,</span> <span m='2899530'>again,</span> <span
  m='2899830'>what</span> <span m='2899980'>the</span> <span
  m='2900070'>unit</span> <span m='2900310'>sample</span> <span
  m='2900700'>response</span> <span m='2901060'>is</span> <span
  m='2901690'>for</span> <span m='2901840'>that</span> <span
  m='2902050'>case</span> <span m='2902410'>because</span> <span
  m='2902770'>we</span> <span m='2902860'>worked</span> <span
  m='2903160'>it</span> <span m='2903250'>out</span> <span
  m='2903400'>previously,</span> <span m='2904750'>namely</span> <span
  m='2905970'>h</span> <span m='2906245'>of</span> <span m='2906520'>n</span>
  <span m='2907300'>is</span> <span m='2907480'>equal</span> <span
  m='2907780'>to</span> <span m='2907930'>minus</span> <span
  m='2909900'>1/2</span> <span m='2910390'>to</span> <span
  m='2910540'>the</span> <span m='2910710'>n,</span> <span
  m='2911800'>but</span> <span m='2911980'>for</span> <span m='2912160'>n</span>
  <span m='2912370'>negative,</span> <span m='2912940'>not</span> <span
  m='2913150'>for</span> <span m='2913330'>n</span> <span
  m='2913480'>positive.</span> <span m='2914710'>That</span> <span
  m='2914890'>is,</span> <span m='2915100'>multiplied</span> <span
  m='2915850'>by</span> <span m='2916060'>u</span> <span m='2916510'>of</span>
  <span m='2917950'>minus</span> <span m='2918370'>n</span> <span
  m='2918580'>minus</span> <span m='2919000'>1.</span> </p><p><span
  m='2921820'>And</span> <span m='2921970'>this,</span> <span
  m='2922150'>by</span> <span m='2922390'>the</span> <span
  m='2922510'>way,</span> <span m='2922720'>if</span> <span
  m='2922810'>you</span> <span m='2922930'>refer</span> <span
  m='2923290'>back</span> <span m='2923950'>several</span> <span
  m='2924340'>lectures</span> <span m='2924790'>ago,</span> <span
  m='2925630'>is</span> <span m='2925750'>consistent</span> <span
  m='2926350'>with</span> <span m='2926530'>the</span> <span
  m='2926620'>two</span> <span m='2926830'>solutions</span> <span
  m='2927460'>that</span> <span m='2927580'>we</span> <span
  m='2927730'>got</span> <span m='2928450'>for</span> <span m='2928810'>a</span>
  <span m='2928900'>linear</span> <span m='2929320'>constant</span> <span
  m='2929740'>coefficient</span> <span m='2930310'>difference</span> <span
  m='2930730'>equation.</span> <span m='2932140'>And</span> <span
  m='2932860'>now</span> <span m='2933100'>you</span> <span
  m='2933280'>can</span> <span m='2933430'>see</span> <span
  m='2933730'>that,</span> <span m='2933950'>for</span> <span
  m='2934000'>example,</span> <span m='2935000'>if</span> <span
  m='2935050'>I</span> <span m='2935140'>specified</span> <span
  m='2936100'>the</span> <span m='2936220'>difference</span> <span
  m='2936610'>equation,</span> <span m='2938860'>and</span> <span
  m='2939040'>I</span> <span m='2939190'>said</span> <span
  m='2940000'>that,</span> <span m='2940240'>in</span> <span
  m='2940390'>addition,</span> <span m='2940810'>what</span> <span
  m='2940960'>we're</span> <span m='2941080'>talking</span> <span
  m='2941440'>about</span> <span m='2941710'>is,</span> <span
  m='2941830'>say,</span> <span m='2942550'>a</span> <span
  m='2942580'>stable</span> <span m='2943030'>system,</span> <span
  m='2944230'>then</span> <span m='2944380'>you</span> <span
  m='2944500'>could</span> <span m='2944650'>construct</span> <span
  m='2945290'>the</span> <span m='2945370'>region</span> <span
  m='2945730'>of</span> <span m='2945820'>convergence</span> <span
  m='2946510'>by</span> <span m='2946870'>saying,</span> <span
  m='2947330'>all</span> <span m='2947430'>right,</span> <span
  m='2947590'>the</span> <span m='2947650'>unit</span> <span
  m='2947950'>circle</span> <span m='2948340'>has</span> <span
  m='2948490'>to</span> <span m='2948640'>be</span> <span m='2948760'>in</span>
  <span m='2948850'>the</span> <span m='2948940'>region</span> <span
  m='2949240'>of</span> <span m='2949300'>convergence,</span> <span
  m='2950470'>and</span> <span m='2950650'>now</span> <span
  m='2950900'>I'll</span> <span m='2950980'>take</span> <span
  m='2951190'>the</span> <span m='2951310'>region</span> <span
  m='2951610'>of</span> <span m='2951700'>convergence</span> <span
  m='2952270'>to</span> <span m='2953310'>go</span> <span m='2953590'>in</span>
  <span m='2953840'>toward</span> <span m='2954160'>a</span> <span
  m='2954220'>pole</span> <span m='2954700'>and</span> <span
  m='2954880'>out</span> <span m='2955090'>toward</span> <span
  m='2955330'>a</span> <span m='2955390'>pole.</span> <span
  m='2956170'>Or</span> <span m='2956350'>if</span> <span m='2956470'>I</span>
  <span m='2956560'>said,</span> <span m='2956870'>the</span> <span
  m='2956890'>system</span> <span m='2957250'>was</span> <span
  m='2957400'>causal,</span> <span m='2958390'>then</span> <span
  m='2958540'>you</span> <span m='2958660'>could</span> <span
  m='2958810'>construct</span> <span m='2959280'>the</span> <span
  m='2959380'>region</span> <span m='2959680'>of</span> <span
  m='2959770'>convergence.</span> </p><p><span m='2960830'>So</span> <span
  m='2960880'>sometimes,</span> <span m='2961810'>in</span> <span
  m='2962440'>stating</span> <span m='2962980'>a</span> <span
  m='2963010'>linear</span> <span m='2963340'>constant</span> <span
  m='2963730'>coefficient</span> <span m='2964270'>difference</span> <span
  m='2964630'>equation,</span> <span m='2965530'>we'll</span> <span
  m='2965650'>basically</span> <span m='2966400'>[AUDIO OUT]</span> <span
  m='2967390'>convergence</span> <span m='2968530'>by</span> <span
  m='2970210'>making</span> <span m='2970720'>an</span> <span
  m='2970840'>additional</span> <span m='2971230'>statement</span> <span
  m='2971620'>about</span> <span m='2971920'>the</span> <span
  m='2972010'>system.</span> <span m='2972860'>For</span> <span
  m='2972910'>[AUDIO OUT]</span> <span m='2973610'>system</span> <span
  m='2973960'>is</span> <span m='2974080'>causal,</span> <span
  m='2974710'>or</span> <span m='2974890'>the</span> <span
  m='2974980'>system</span> <span m='2975370'>is</span> <span
  m='2975430'>stable,</span> <span m='2975910'>or</span> <span
  m='2976600'>both</span> <span m='2976970'>if</span> <span
  m='2977080'>it</span> <span m='2977170'>can</span> <span m='2977320'>be</span>
  <span m='2977440'>both.</span> </p><p><span m='2979330'>[AUDIO OUT]</span>
  <span m='2980330'>So</span> <span m='2980500'>this</span> <span
  m='2980980'>is</span> <span m='2981760'>the</span> <span
  m='2982450'>Z-transform.</span> <span m='2984130'>Just</span> <span
  m='2984640'>to</span> <span m='2984970'>summarize</span> <span
  m='2985570'>the</span> <span m='2985660'>key</span> <span
  m='2985900'>points</span> <span m='2986720'>first,</span> <span
  m='2987910'>the</span> <span m='2988000'>Z-transform</span> <span
  m='2988720'>was</span> <span m='2988870'>introduced</span> <span
  m='2990130'>to</span> <span m='2990940'>get</span> <span
  m='2991120'>around</span> <span m='2991540'>the</span> <span
  m='2991630'>convergence</span> <span m='2992230'>problem</span> <span
  m='2992710'>with</span> <span m='2992770'>the</span> <span
  m='2992890'>Fourier</span> <span m='2993370'>transform.</span> <span
  m='2995360'>The</span> <span m='2995460'>Z-transform</span> <span
  m='2996520'>of</span> <span m='2996610'>sequences</span> <span
  m='2997570'>that</span> <span m='2997750'>are</span> <span
  m='2997840'>exponentials</span> <span m='2999760'>are</span> <span
  m='2999910'>ratios</span> <span m='3000480'>of</span> <span
  m='3000570'>polynomials.</span> <span m='3001530'>That</span> <span
  m='3001680'>is,</span> <span m='3001860'>they</span> <span
  m='3002010'>can</span> <span m='3002130'>be</span> <span
  m='3002250'>described</span> <span m='3002760'>in</span> <span
  m='3002850'>terms</span> <span m='3003180'>of</span> <span
  m='3003240'>poles</span> <span m='3003630'>and</span> <span
  m='3003750'>zeros.</span> <span m='3005460'>But</span> <span
  m='3006390'>the</span> <span m='3006570'>Z-transform</span> <span
  m='3007470'>is</span> <span m='3007680'>not</span> <span
  m='3007950'>specified</span> <span m='3008820'>just</span> <span
  m='3009150'>by</span> <span m='3009390'>the</span> <span
  m='3009510'>ratio</span> <span m='3009900'>of</span> <span
  m='3009990'>polynomials.</span> <span m='3011220'>You</span> <span
  m='3011370'>also</span> <span m='3011730'>need</span> <span
  m='3011940'>to</span> <span m='3012060'>know</span> <span
  m='3012630'>what</span> <span m='3012810'>the</span> <span
  m='3012900'>region</span> <span m='3013200'>of</span> <span
  m='3013320'>convergence</span> <span m='3014000'>is</span> <span
  m='3014970'>of</span> <span m='3015390'>the</span> <span
  m='3015780'>Z-transform</span> <span m='3017430'>so</span> <span
  m='3017580'>that,</span> <span m='3017790'>in</span> <span
  m='3017940'>fact,</span> <span m='3018630'>for</span> <span
  m='3019350'>several</span> <span m='3024230'>different</span> <span
  m='3024560'>sequences,</span> <span m='3025250'>you</span> <span
  m='3025370'>can</span> <span m='3025520'>end</span> <span
  m='3025730'>up</span> <span m='3025880'>with</span> <span
  m='3026000'>the</span> <span m='3026090'>same</span> <span
  m='3026420'>ratio</span> <span m='3026840'>of</span> <span
  m='3026900'>polynomials,</span> <span m='3027920'>but</span> <span
  m='3028130'>of</span> <span m='3028220'>course</span> <span
  m='3028490'>you'll</span> <span m='3028580'>get</span> <span
  m='3028760'>different</span> <span m='3029060'>regions</span> <span
  m='3029450'>of</span> <span m='3029540'>convergence.</span> </p><p><span
  m='3030650'>Finally,</span> <span m='3031220'>the</span> <span
  m='3031340'>region</span> <span m='3031640'>of</span> <span
  m='3031730'>convergence</span> <span m='3032390'>includes</span> <span
  m='3032780'>the</span> <span m='3032870'>unit</span> <span
  m='3033140'>circle.</span> <span m='3033950'>That</span> <span
  m='3034130'>tells</span> <span m='3034550'>us</span> <span
  m='3035210'>that</span> <span m='3035720'>the</span> <span
  m='3035820'>Fourier</span> <span m='3036200'>transform</span> <span
  m='3037070'>converges.</span> <span m='3038240'>And</span> <span
  m='3038690'>also,</span> <span m='3039110'>we're</span> <span
  m='3039290'>able</span> <span m='3039590'>to</span> <span
  m='3039710'>make</span> <span m='3040100'>statements</span> <span
  m='3040820'>about</span> <span m='3041880'>a</span> <span
  m='3041960'>region</span> <span m='3042350'>of</span> <span
  m='3042440'>convergence</span> <span m='3043100'>as</span> <span
  m='3043250'>it</span> <span m='3043340'>relates</span> <span
  m='3043730'>to</span> <span m='3043850'>right-sided,</span> <span
  m='3044510'>left-sided,</span> <span m='3045150'>and</span> <span
  m='3045260'>two-sided</span> <span m='3045830'>sequences.</span> <span
  m='3047540'>Next</span> <span m='3047780'>time,</span> <span
  m='3048320'>we'll</span> <span m='3048500'>continue</span> <span
  m='3049700'>the</span> <span m='3049790'>discussion</span> <span
  m='3050600'>of</span> <span m='3050750'>the</span> <span
  m='3051050'>Z-transform,</span> <span m='3051950'>and</span> <span
  m='3052100'>in</span> <span m='3052190'>particular</span> <span
  m='3053300'>develop</span> <span m='3053930'>the</span> <span
  m='3054110'>inverse</span> <span m='3054365'>Z-transform.</span> <span
  m='3055750'>Thank</span> <span m='3055960'>you.</span> </p><p><span
  m='3056980'>[MUSIC PLAYING]</span> </p><p></p>
embedded_media:
  - uid: c7f87d4cb052de4f4881ee8c3c90b8e8
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: MITRES_6_008S11_lec05.pdf
    title: MITRES_6_008S11_lec05.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-5-the-z-transform/MITRES_6_008S11_lec05.pdf
  - uid: 74ceb354af8ade8bd1396d3f16438402
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: I9u15zdgJvI
  - uid: 7b79e9501c1ec421eaec8fc8d779c50a
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-5-the-z-transform/id481803782?i=108362005
  - uid: 7264e0f586326a921f8ba771510132f4
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec05_300k.mp4'
  - uid: f42fb195e43b05e9b50789d9211fb098
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/I9u15zdgJvI/default.jpg'
  - uid: 28af5f76576d36627269be741a4af8ed
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: I9u15zdgJvI
  - uid: af82ea40cde4413259f6b27cac9e2790
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: I9u15zdgJvI.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-5-the-z-transform/I9u15zdgJvI.srt
  - uid: d56ec08992fa129e9f121a434e54708d
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: I9u15zdgJvI.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-5-the-z-transform/I9u15zdgJvI.pdf
  - uid: dab49c45a22b760f40c88239f116234e
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: f57bb88b4a5d973762a673539f28d4e9
    parent_uid: e0411f9dab21ab2d69898c1ab5fab0c2
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
