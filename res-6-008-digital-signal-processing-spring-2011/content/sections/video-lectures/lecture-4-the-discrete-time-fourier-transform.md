---
order_index: null
title: 'Lecture 4: The Discrete-Time Fourier Transform'
template_type: Tabbed
uid: 2d6c677c91944e7646cef1245ec7b8b5
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-4-the-discrete-time-fourier-transform
short_url: lecture-4-the-discrete-time-fourier-transform
inline_embed_id: '42444629lecture4:thediscrete-timefouriertransform8431911'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Generalization of the frequency response
  representation of sequences, inverse Fourier transform relation, symmetry
  properties of Fourier transforms, relationship between continuous-time and
  discrete-time Fourier transforms.</p><p><strong>Instructor:</strong> Prof.
  Alan V. Oppenheim</p>
related_resources_text: >-
  <p>The Discrete-Time Fourier Transform (<a
  href="./resolveuid/615aa34ef098a20abd5172767f2ee070">PDF</a>)</p>
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
  m='10980'>donation,</span> <span m='11730'>or</span> <span
  m='11940'>view</span> <span m='12390'>additional</span> <span
  m='12810'>materials</span> <span m='13320'>from</span> <span
  m='13500'>hundreds</span> <span m='13920'>of</span> <span m='14040'>MIT</span>
  <span m='14460'>courses,</span> <span m='15550'>visit</span> <span
  m='15780'>MIT</span> <span m='16200'>OpenCourseWare</span> <span
  m='17280'>at</span> <span m='17430'>ocw.mit.edu.</span> <span
  m='17670'>W</span> </p><p><span m='22988'>[MUSIC PLAYING]</span> </p><p><span
  m='51200'>PROFESSOR:</span> <span m='51430'>In</span> <span
  m='51660'>the</span> <span m='51780'>last</span> <span
  m='52200'>lecture,</span> <span m='53010'>we</span> <span
  m='53340'>considered</span> <span m='54060'>the</span> <span
  m='54390'>frequency</span> <span m='54990'>response</span> <span
  m='55710'>of</span> <span m='56010'>linear</span> <span m='56400'>shift</span>
  <span m='56760'>and</span> <span m='56920'>variance</span> <span
  m='57300'>systems.</span> <span m='59130'>In</span> <span
  m='59220'>this</span> <span m='59430'>lecture,</span> <span
  m='60190'>what</span> <span m='60240'>I</span> <span m='60330'>would</span>
  <span m='60480'>like</span> <span m='60690'>to</span> <span
  m='60840'>do</span> <span m='61350'>is</span> <span m='61920'>extend</span>
  <span m='62430'>some</span> <span m='62670'>of</span> <span
  m='62760'>those</span> <span m='63030'>ideas</span> <span m='64349'>to</span>
  <span m='64890'>the</span> <span m='65010'>notion</span> <span
  m='65760'>of</span> <span m='66420'>the</span> <span m='66510'>Fourier</span>
  <span m='66990'>transform,</span> <span m='68730'>which</span> <span
  m='69030'>I'll</span> <span m='69190'>refer</span> <span m='69570'>to</span>
  <span m='70020'>as</span> <span m='70560'>the</span> <span
  m='70890'>discrete</span> <span m='71370'>time</span> <span
  m='72000'>Fourier</span> <span m='72390'>transform.</span> </p><p><span
  m='74280'>So</span> <span m='74670'>let</span> <span m='74880'>me</span> <span
  m='75000'>begin</span> <span m='75630'>by</span> <span
  m='76380'>reminding</span> <span m='76950'>you</span> <span
  m='78210'>of</span> <span m='78810'>one</span> <span m='79020'>of</span> <span
  m='79110'>the</span> <span m='79210'>key</span> <span m='79440'>results</span>
  <span m='80250'>from</span> <span m='80460'>last</span> <span
  m='80790'>time,</span> <span m='82360'>namely,</span> <span
  m='83130'>the</span> <span m='83280'>notion</span> <span m='83940'>of</span>
  <span m='84060'>the</span> <span m='84180'>frequency</span> <span
  m='84720'>response</span> <span m='85620'>of</span> <span m='85860'>a</span>
  <span m='85920'>linear</span> <span m='86250'>shift</span> <span
  m='86740'>invariant</span> <span m='87110'>system.</span> <span
  m='88590'>For</span> <span m='88740'>a</span> <span m='88800'>linear</span>
  <span m='89250'>shift</span> <span m='89670'>invariant</span> <span
  m='90090'>system,</span> <span m='91440'>we</span> <span m='91590'>saw</span>
  <span m='92220'>last</span> <span m='92580'>time</span> <span
  m='93270'>that</span> <span m='93990'>one</span> <span m='94170'>of</span>
  <span m='94230'>the</span> <span m='94350'>key</span> <span
  m='94560'>properties</span> <span m='96090'>was</span> <span
  m='96360'>that</span> <span m='96870'>for</span> <span m='97530'>a</span>
  <span m='97590'>complex</span> <span m='98220'>exponential</span> <span
  m='98940'>input,</span> <span m='100290'>the</span> <span
  m='100440'>output</span> <span m='101070'>is</span> <span m='101220'>a</span>
  <span m='101280'>complex</span> <span m='101880'>exponential</span> <span
  m='102900'>sequence</span> <span m='104460'>with</span> <span
  m='104880'>the</span> <span m='105000'>same</span> <span
  m='105540'>complex</span> <span m='106170'>frequency,</span> <span
  m='107400'>but</span> <span m='107850'>with</span> <span m='108090'>a</span>
  <span m='108130'>change</span> <span m='108540'>in</span> <span
  m='108660'>amplitude.</span> <span m='110100'>And</span> <span
  m='110970'>the</span> <span m='111060'>change</span> <span
  m='111450'>in</span> <span m='111540'>amplitude,</span> <span
  m='112230'>that</span> <span m='112470'>is</span> <span m='112920'>the</span>
  <span m='113040'>function</span> <span m='113670'>h</span> <span
  m='114120'>of</span> <span m='114240'>e to</span> <span m='114450'>the</span>
  <span m='114570'>j</span> <span m='114780'>omega,</span> <span
  m='115890'>we</span> <span m='116130'>refer</span> <span m='116550'>to</span>
  <span m='117030'>as</span> <span m='117270'>the</span> <span
  m='117360'>frequency</span> <span m='117870'>response</span> <span
  m='118380'>of</span> <span m='118470'>the</span> <span
  m='118560'>system.</span> </p><p><span m='120740'>The</span> <span
  m='120830'>expression</span> <span m='121730'>that</span> <span
  m='121910'>we</span> <span m='122090'>had</span> <span m='122390'>for</span>
  <span m='122510'>the</span> <span m='122600'>frequency</span> <span
  m='123110'>response,</span> <span m='124070'>in</span> <span
  m='124190'>terms</span> <span m='124580'>of</span> <span m='124700'>the</span>
  <span m='124790'>unit</span> <span m='125060'>sample</span> <span
  m='125510'>response,</span> <span m='126890'>was</span> <span
  m='127580'>that</span> <span m='128120'>the</span> <span
  m='128210'>frequency</span> <span m='128750'>response</span> <span
  m='129185'>h</span> <span m='129620'>of e</span> <span m='130039'>to</span>
  <span m='130130'>the</span> <span m='130250'>j</span> <span
  m='130490'>omega,</span> <span m='131570'>is</span> <span
  m='131750'>given</span> <span m='132080'>by</span> <span m='132350'>the</span>
  <span m='132470'>sum</span> <span m='132770'>of</span> <span
  m='133070'>h</span> <span m='133490'>of</span> <span m='133910'>n,</span>
  <span m='134450'>the</span> <span m='134570'>unit</span> <span
  m='134840'>sample</span> <span m='135230'>response</span> <span
  m='136010'>of</span> <span m='136160'>the</span> <span
  m='136250'>system,</span> <span m='137420'>multiplied</span> <span
  m='138410'>by</span> <span m='138950'>e</span> <span m='139190'>to</span>
  <span m='139370'>the</span> <span m='139460'>minus</span> <span
  m='139880'>j</span> <span m='140355'>omega</span> <span m='140830'>n.</span>
  <span m='141290'>So</span> <span m='142070'>this</span> <span
  m='142280'>is</span> <span m='142430'>a</span> <span
  m='142490'>relationship</span> <span m='143840'>that</span> <span
  m='143960'>tells</span> <span m='144380'>us,</span> <span m='144800'>in</span>
  <span m='144980'>terms</span> <span m='145400'>of</span> <span
  m='145490'>the</span> <span m='145610'>unit</span> <span
  m='145880'>sample</span> <span m='146300'>response</span> <span
  m='146810'>of</span> <span m='146870'>the</span> <span
  m='146990'>system,</span> <span m='148040'>how</span> <span
  m='148160'>to</span> <span m='148250'>get</span> <span m='148460'>the</span>
  <span m='148580'>frequency</span> <span m='149090'>response.</span>
  </p><p><span m='151280'>There</span> <span m='151400'>were</span> <span
  m='152030'>two</span> <span m='152180'>properties</span> <span
  m='153200'>of</span> <span m='153350'>the</span> <span
  m='153440'>frequency</span> <span m='153980'>response</span> <span
  m='154970'>that</span> <span m='155360'>I</span> <span
  m='155480'>stressed</span> <span m='156230'>last</span> <span
  m='156560'>time.</span> <span m='157630'>One</span> <span m='157820'>of</span>
  <span m='157910'>them</span> <span m='158420'>was</span> <span
  m='159050'>the</span> <span m='159140'>fact</span> <span
  m='159800'>that</span> <span m='159950'>the</span> <span
  m='160040'>frequency</span> <span m='160580'>response</span> <span
  m='161810'>is</span> <span m='161960'>a</span> <span
  m='162020'>function</span> <span m='162740'>of</span> <span
  m='163160'>a</span> <span m='163250'>continuous</span> <span
  m='164330'>variable,</span> <span m='164930'>omega.</span> <span
  m='166070'>That</span> <span m='166280'>is,</span> <span
  m='167240'>complex</span> <span m='167810'>exponential</span> <span
  m='168530'>inputs</span> <span m='170300'>can</span> <span
  m='170510'>have</span> <span m='171290'>the</span> <span
  m='171500'>frequency</span> <span m='172070'>variable</span> <span
  m='172910'>omega,</span> <span m='173840'>vary</span> <span
  m='174530'>continuously.</span> <span m='175790'>Omega</span> <span
  m='176180'>is</span> <span m='176360'>a</span> <span
  m='176420'>continuous</span> <span m='177020'>variable,</span> <span
  m='178040'>whereas</span> <span m='178610'>n</span> <span m='179090'>is</span>
  <span m='179690'>the</span> <span m='179810'>discrete</span> <span
  m='180230'>variable.</span> <span m='182160'>So</span> <span
  m='182660'>this</span> <span m='182930'>was</span> <span m='183140'>one</span>
  <span m='183350'>important</span> <span m='184040'>property.</span>
  </p><p><span m='185840'>The</span> <span m='185930'>second</span> <span
  m='186680'>important</span> <span m='187160'>property</span> <span
  m='187910'>is</span> <span m='188120'>that</span> <span m='188270'>the</span>
  <span m='188360'>frequency</span> <span m='188930'>response</span> <span
  m='189770'>is</span> <span m='190220'>a</span> <span
  m='190280'>periodic</span> <span m='191360'>function</span> <span
  m='191810'>of</span> <span m='191900'>omega.</span> <span
  m='193290'>And</span> <span m='194060'>the</span> <span
  m='194150'>period</span> <span m='194900'>is</span> <span
  m='195080'>equal</span> <span m='195380'>2</span> <span m='195760'>pi.</span>
  <span m='197510'>H</span> <span m='197950'>of e</span> <span
  m='198460'>to</span> <span m='198580'>the</span> <span m='198700'>j</span>
  <span m='198970'>omega</span> <span m='200470'>is</span> <span
  m='200650'>equal</span> <span m='201040'>to</span> <span m='201460'>h of
  e</span> <span m='201730'>to</span> <span m='202050'>the</span> <span
  m='202150'>j</span> <span m='203050'>omega</span> <span m='203920'>plus</span>
  <span m='204340'>2</span> <span m='204550'>pi</span> <span
  m='204940'>k,</span> <span m='206000'>where</span> <span m='206080'>k</span>
  <span m='206740'>is</span> <span m='207160'>any</span> <span
  m='207430'>integer.</span> </p><p><span m='208810'>Now</span> <span
  m='209350'>one</span> <span m='209560'>of</span> <span m='209770'>the</span>
  <span m='210580'>sort</span> <span m='210850'>of</span> <span
  m='210970'>heuristic</span> <span m='211780'>explanations</span> <span
  m='212830'>or</span> <span m='212950'>justifications</span> <span
  m='214540'>for</span> <span m='214690'>why</span> <span m='214990'>the</span>
  <span m='215110'>frequency</span> <span m='215650'>response</span> <span
  m='216460'>is</span> <span m='216610'>periodic,</span> <span
  m='217780'>as</span> <span m='217960'>I've</span> <span
  m='218080'>tried</span> <span m='218350'>to</span> <span
  m='218470'>indicate</span> <span m='219190'>in</span> <span
  m='219310'>several</span> <span m='219700'>lectures,</span> <span
  m='220840'>is</span> <span m='220990'>basically</span> <span
  m='221620'>tied</span> <span m='221950'>to</span> <span m='222100'>the</span>
  <span m='222220'>fact</span> <span m='223510'>that</span> <span
  m='223660'>complex</span> <span m='224260'>exponentials</span> <span
  m='225670'>or</span> <span m='226030'>sinusoidal</span> <span
  m='226870'>inputs,</span> <span m='228130'>are</span> <span
  m='229870'>very</span> <span m='230380'>periodically</span> <span
  m='231370'>with</span> <span m='231550'>frequency</span> <span
  m='233170'>over</span> <span m='233980'>an</span> <span
  m='234130'>interval</span> <span m='234900'>0</span> <span
  m='235300'>to</span> <span m='235420'>2</span> <span m='235630'>pi.</span>
  <span m='236020'>That</span> <span m='236200'>is,</span> <span
  m='236800'>once</span> <span m='237070'>we've</span> <span
  m='237250'>looked</span> <span m='237520'>at</span> <span
  m='237730'>them</span> <span m='237880'>for</span> <span
  m='238060'>omega</span> <span m='238420'>between</span> <span
  m='238810'>0</span> <span m='239200'>and</span> <span m='239290'>2</span>
  <span m='239500'>pi,</span> <span m='240700'>if</span> <span
  m='240850'>we</span> <span m='240970'>go</span> <span
  m='241180'>further</span> <span m='241540'>than</span> <span
  m='241720'>that</span> <span m='241900'>in</span> <span
  m='242020'>frequency,</span> <span m='242395'>all</span> <span
  m='242770'>we</span> <span m='243180'>see</span> <span m='243610'>are</span>
  <span m='243850'>the</span> <span m='243970'>same</span> <span
  m='244270'>complex</span> <span m='244810'>exponentials</span> <span
  m='245710'>or</span> <span m='245830'>the</span> <span m='245920'>same</span>
  <span m='246220'>sinusoids</span> <span m='247090'>over</span> <span
  m='247420'>again.</span> <span m='249100'>So</span> <span
  m='249700'>that,</span> <span m='250070'>in</span> <span
  m='250180'>essence,</span> <span m='250690'>is</span> <span
  m='250870'>the</span> <span m='250960'>reason</span> <span
  m='251650'>why</span> <span m='251890'>the</span> <span
  m='252010'>frequency</span> <span m='252550'>response</span> <span
  m='253300'>is</span> <span m='253450'>a</span> <span
  m='253510'>periodic</span> <span m='254350'>function</span> <span
  m='254800'>of</span> <span m='254920'>omega.</span> </p><p><span
  m='256690'>Well,</span> <span m='256990'>one</span> <span m='257200'>of</span>
  <span m='257290'>the</span> <span m='257410'>things</span> <span
  m='258010'>we'd</span> <span m='258190'>like</span> <span m='258790'>to</span>
  <span m='258940'>do</span> <span m='259510'>is</span> <span
  m='259690'>develop</span> <span m='260680'>an</span> <span
  m='260800'>inverse</span> <span m='261310'>relationship,</span> <span
  m='262810'>which</span> <span m='263230'>permits</span> <span
  m='263770'>us</span> <span m='264280'>to</span> <span m='264820'>get</span>
  <span m='265420'>the</span> <span m='265630'>unit</span> <span
  m='265960'>sample</span> <span m='266410'>response</span> <span
  m='267190'>from</span> <span m='267400'>the</span> <span
  m='267490'>frequency</span> <span m='268030'>response.</span> <span
  m='269950'>One</span> <span m='270790'>heuristic</span> <span
  m='272140'>notion</span> <span m='273190'>or</span> <span
  m='273670'>style</span> <span m='274420'>of</span> <span
  m='275140'>developing</span> <span m='275920'>such</span> <span
  m='276280'>an</span> <span m='276370'>inverse</span> <span
  m='276760'>relationship,</span> <span m='278080'>we</span> <span
  m='278200'>can</span> <span m='278380'>get</span> <span m='278860'>by</span>
  <span m='279550'>observing</span> <span m='280960'>that</span> <span
  m='281530'>since</span> <span m='282220'>the</span> <span
  m='282310'>frequency</span> <span m='282880'>response</span> <span
  m='284770'>is</span> <span m='284980'>a</span> <span
  m='285040'>function</span> <span m='285460'>of</span> <span
  m='285550'>a</span> <span m='285580'>continuous</span> <span
  m='286210'>variable</span> <span m='286690'>omega,</span> <span
  m='287830'>and</span> <span m='287950'>in</span> <span m='288040'>fact,</span>
  <span m='288580'>it's</span> <span m='288760'>a</span> <span
  m='288820'>periodic</span> <span m='289480'>function</span> <span
  m='290260'>of</span> <span m='290410'>omega,</span> <span
  m='291890'>then</span> <span m='292240'>it</span> <span
  m='292390'>should</span> <span m='292570'>have</span> <span
  m='292780'>a</span> <span m='292840'>Fourier</span> <span
  m='293290'>series</span> <span m='293710'>representation.</span> <span
  m='294550'>That</span> <span m='294730'>is,</span> <span
  m='295300'>it's</span> <span m='295450'>a</span> <span
  m='295510'>continuous</span> <span m='296080'>periodic</span> <span
  m='296650'>function.</span> <span m='298050'>A</span> <span
  m='298120'>continuous</span> <span m='298660'>periodic</span> <span
  m='299200'>function</span> <span m='299620'>has</span> <span
  m='299800'>a</span> <span m='299860'>Fourier</span> <span
  m='300320'>series</span> <span m='300670'>representation.</span> </p><p><span
  m='302810'>Well</span> <span m='302860'>in</span> <span
  m='302950'>fact,</span> <span m='304130'>if</span> <span m='304210'>we</span>
  <span m='304300'>look</span> <span m='304780'>at</span> <span
  m='305530'>this</span> <span m='305770'>expression,</span> <span
  m='307640'>we</span> <span m='307690'>see</span> <span m='308200'>that</span>
  <span m='308500'>indeed</span> <span m='309250'>what</span> <span
  m='309490'>this</span> <span m='309760'>is</span> <span m='310180'>is</span>
  <span m='310450'>a</span> <span m='310510'>Fourier</span> <span
  m='310990'>series</span> <span m='311620'>expansion</span> <span
  m='312970'>of</span> <span m='313150'>this</span> <span
  m='313780'>periodic</span> <span m='314380'>function</span> <span
  m='316420'>in</span> <span m='316570'>terms</span> <span m='317140'>of</span>
  <span m='317500'>a</span> <span m='317560'>complex</span> <span
  m='318640'>Fourier</span> <span m='319120'>series.</span> <span
  m='319630'>The</span> <span m='320050'>Fourier</span> <span
  m='320470'>series</span> <span m='320950'>expressed</span> <span
  m='321460'>in</span> <span m='321550'>terms</span> <span m='321850'>of</span>
  <span m='321940'>complex</span> <span m='322480'>exponentials.</span>
  </p><p><span m='324460'>Well,</span> <span m='324850'>what</span> <span
  m='325030'>are</span> <span m='325120'>the</span> <span
  m='325210'>Fourier</span> <span m='325600'>series</span> <span
  m='325990'>coefficients?</span> <span m='326890'>The</span> <span
  m='327310'>Fourier</span> <span m='327880'>series</span> <span
  m='328300'>coefficients</span> <span m='329560'>are</span> <span
  m='330190'>the</span> <span m='330280'>values</span> <span
  m='331120'>of</span> <span m='331270'>the</span> <span m='331390'>unit</span>
  <span m='331660'>sample</span> <span m='332080'>response,</span> <span
  m='332890'>in</span> <span m='333040'>other</span> <span
  m='333250'>words,</span> <span m='333590'>the</span> <span
  m='333610'>values</span> <span m='334060'>h of</span> <span
  m='334300'>n.</span> <span m='335830'>So</span> <span m='336130'>in</span>
  <span m='336280'>fact,</span> <span m='337060'>this</span> <span
  m='337270'>has</span> <span m='337510'>the</span> <span m='337630'>form</span>
  <span m='337960'>of</span> <span m='338080'>a</span> <span
  m='338110'>Fourier</span> <span m='338620'>series.</span> <span
  m='339880'>That</span> <span m='340090'>means</span> <span
  m='340480'>that</span> <span m='340600'>these</span> <span
  m='340870'>are</span> <span m='340960'>the</span> <span
  m='341050'>Fourier</span> <span m='341470'>coefficients.</span> <span
  m='342790'>That</span> <span m='343060'>means</span> <span
  m='343720'>that</span> <span m='343930'>we</span> <span m='344110'>can</span>
  <span m='344350'>get</span> <span m='344590'>these</span> <span
  m='344850'>Fourier</span> <span m='345220'>coefficients</span> <span
  m='345960'>in</span> <span m='346330'>terms</span> <span m='346480'>of</span>
  <span m='346840'>h of</span> <span m='346960'>e</span> <span
  m='347350'>to</span> <span m='347440'>the</span> <span m='347530'>j</span>
  <span m='347770'>omega,</span> <span m='348670'>the</span> <span
  m='348790'>way</span> <span m='348970'>we</span> <span
  m='349180'>always</span> <span m='349630'>get</span> <span
  m='350040'>Fourier</span> <span m='350470'>series</span> <span
  m='350860'>coefficients</span> <span m='352000'>in</span> <span
  m='352120'>terms</span> <span m='352660'>of</span> <span m='353050'>a</span>
  <span m='353110'>periodic</span> <span m='354100'>continuous</span> <span
  m='354700'>function.</span> </p><p><span m='356510'>Well,</span> <span
  m='356980'>the</span> <span m='357250'>resulting</span> <span
  m='357790'>expression</span> <span m='358420'>then</span> <span
  m='359440'>is</span> <span m='359710'>that</span> <span m='360220'>the</span>
  <span m='360570'>Fourier</span> <span m='361090'>series</span> <span
  m='361540'>coefficients,</span> <span m='362500'>or</span> <span
  m='362920'>equivalently</span> <span m='363700'>the</span> <span
  m='363790'>unit</span> <span m='364090'>sample</span> <span
  m='364510'>response,</span> <span m='365830'>is</span> <span
  m='366010'>equal</span> <span m='366310'>to</span> <span m='366460'>1</span>
  <span m='366670'>over</span> <span m='366880'>2</span> <span
  m='367150'>pi</span> <span m='368080'>times</span> <span m='368380'>the</span>
  <span m='368530'>integral</span> <span m='368950'>over</span> <span
  m='369190'>a</span> <span m='369250'>period,</span> <span
  m='369910'>which</span> <span m='370390'>I've</span> <span
  m='370570'>taken</span> <span m='370930'>as</span> <span
  m='371050'>minus</span> <span m='371410'>pi</span> <span m='371695'>to</span>
  <span m='372080'>plus</span> <span m='372310'>pi,</span> <span
  m='373150'>of</span> <span m='373795'>h</span> <span m='374110'>of</span>
  <span m='374410'>e</span> <span m='374710'>to</span> <span
  m='374830'>the</span> <span m='374950'>j</span> <span m='375190'>omega,</span>
  <span m='375850'>e</span> <span m='376360'>to</span> <span
  m='376510'>the</span> <span m='376870'>omega</span> <span m='377260'>n,</span>
  <span m='377800'>d</span> <span m='377950'>omega.</span> <span
  m='379600'>This</span> <span m='379810'>is</span> <span m='379930'>just</span>
  <span m='380110'>simply</span> <span m='380560'>the</span> <span
  m='380680'>expression</span> <span m='381860'>for</span> <span
  m='382245'>Fourier</span> <span m='382630'>series</span> <span
  m='383050'>coefficients</span> <span m='384460'>in</span> <span
  m='384610'>terms</span> <span m='385270'>of</span> <span m='385990'>the</span>
  <span m='386380'>continuous</span> <span m='387280'>periodic</span> <span
  m='387880'>function</span> <span m='388510'>that</span> <span
  m='388660'>we're</span> <span m='388810'>dealing</span> <span
  m='389170'>with.</span> <span m='390250'>Well</span> <span
  m='391120'>that's,</span> <span m='391660'>in</span> <span m='391870'>a</span>
  <span m='391930'>sense,</span> <span m='392290'>a</span> <span
  m='392920'>heuristic</span> <span m='393670'>derivation.</span> </p><p><span
  m='394990'>We</span> <span m='395170'>can</span> <span m='395650'>in</span>
  <span m='395800'>fact</span> <span m='396220'>verify</span> <span
  m='397390'>that</span> <span m='398170'>this</span> <span
  m='398410'>expression</span> <span m='398980'>is</span> <span
  m='399100'>valid</span> <span m='400060'>simply</span> <span
  m='400720'>by</span> <span m='401410'>substituting</span> <span
  m='402670'>in</span> <span m='403170'>to</span> <span m='403300'>the</span>
  <span m='403450'>integral,</span> <span m='404760'>the</span> <span
  m='405700'>expression</span> <span m='406030'>for</span> <span m='406360'>h
  of</span> <span m='406540'>e</span> <span m='406795'>to</span> <span
  m='407050'>the</span> <span m='407170'>j</span> <span m='407380'>omega.</span>
  <span m='408950'>And</span> <span m='409330'>if</span> <span
  m='409450'>we</span> <span m='409570'>do</span> <span m='409810'>that,</span>
  <span m='410750'>we</span> <span m='410860'>end</span> <span
  m='411130'>up</span> <span m='411370'>with,</span> <span m='411910'>for</span>
  <span m='412210'>the</span> <span m='412360'>expression</span> <span
  m='412660'>for</span> <span m='412960'>h of</span> <span m='413140'>e</span>
  <span m='413530'>to</span> <span m='413620'>the</span> <span
  m='413710'>j</span> <span m='413980'>omega,</span> <span m='415060'>we</span>
  <span m='415240'>have</span> <span m='416350'>the</span> <span
  m='416440'>sum</span> <span m='416980'>of</span> <span m='417250'>h</span>
  <span m='417520'>of</span> <span m='417660'>k,</span> <span
  m='417950'>e</span> <span m='418240'>to</span> <span m='418440'>the</span>
  <span m='418540'>minus j</span> <span m='418930'>omega</span> <span
  m='419650'>k.</span> <span m='421420'>Substituting</span> <span
  m='422320'>in,</span> <span m='424000'>the</span> <span
  m='424450'>result</span> <span m='425200'>is</span> <span
  m='425980'>this</span> <span m='426220'>integral.</span> <span
  m='427810'>If</span> <span m='427960'>we</span> <span
  m='428080'>interchange</span> <span m='429220'>the</span> <span
  m='429370'>order</span> <span m='429850'>of</span> <span
  m='430330'>summation</span> <span m='431410'>and</span> <span
  m='431560'>integration,</span> <span m='433300'>then</span> <span
  m='434110'>the</span> <span m='434200'>resulting</span> <span
  m='434680'>expression</span> <span m='435460'>is</span> <span
  m='435580'>shown</span> <span m='435970'>here.</span> <span
  m='437480'>And</span> <span m='438070'>we</span> <span m='438220'>can</span>
  <span m='438400'>observe</span> <span m='439450'>that</span> <span
  m='439840'>this</span> <span m='440110'>integral--</span> </p><p><span
  m='442480'>First</span> <span m='442840'>of</span> <span
  m='442960'>all,</span> <span m='443810'>let's</span> <span
  m='444100'>consider</span> <span m='444580'>it</span> <span
  m='444790'>for</span> <span m='445300'>n</span> <span m='445570'>not</span>
  <span m='445810'>equal</span> <span m='446140'>to</span> <span
  m='446260'>k.</span> <span m='448540'>If</span> <span m='448750'>n</span>
  <span m='449140'>is</span> <span m='449320'>not</span> <span
  m='449590'>equal</span> <span m='449890'>to</span> <span m='450010'>k,</span>
  <span m='450880'>this</span> <span m='451120'>is</span> <span
  m='451240'>just</span> <span m='451420'>simply</span> <span
  m='451870'>the</span> <span m='452020'>integral</span> <span
  m='453130'>over</span> <span m='453550'>a</span> <span
  m='453610'>period</span> <span m='454030'>of</span> <span m='454150'>2</span>
  <span m='454360'>pi</span> <span m='455530'>of</span> <span
  m='455680'>a</span> <span m='455740'>complex</span> <span
  m='456310'>exponential</span> <span m='457150'>whose</span> <span
  m='457360'>period</span> <span m='457840'>is</span> <span m='457990'>2</span>
  <span m='458200'>pi.</span> <span m='460300'>The</span> <span
  m='460400'>integral</span> <span m='460680'>of</span> <span
  m='460740'>the</span> <span m='460860'>real</span> <span
  m='461130'>part</span> <span m='461460'>is</span> <span m='461580'>the</span>
  <span m='461700'>integral</span> <span m='462030'>of</span> <span
  m='462120'>a</span> <span m='462310'>cosine</span> <span
  m='462870'>over</span> <span m='463110'>an</span> <span
  m='463200'>integral</span> <span m='463860'>number</span> <span
  m='464190'>of</span> <span m='464310'>periods.</span> <span
  m='465780'>And</span> <span m='466020'>the</span> <span
  m='466080'>integral</span> <span m='466470'>of</span> <span
  m='466530'>the</span> <span m='466650'>imaginary</span> <span
  m='467220'>part</span> <span m='467700'>is</span> <span m='467880'>the</span>
  <span m='467970'>integral</span> <span m='468540'>of</span> <span
  m='468960'>the</span> <span m='469080'>sine</span> <span
  m='469650'>over</span> <span m='470100'>an</span> <span
  m='470220'>integral</span> <span m='470550'>number</span> <span
  m='470880'>of</span> <span m='470970'>periods.</span> <span
  m='472210'>Obviously</span> <span m='472860'>then,</span> <span
  m='473340'>this</span> <span m='473550'>integral,</span> <span
  m='474300'>if</span> <span m='474450'>n</span> <span m='474690'>is</span>
  <span m='474810'>not</span> <span m='475050'>equal</span> <span
  m='475350'>to</span> <span m='475470'>k</span> <span m='476550'>is</span>
  <span m='476670'>going</span> <span m='476820'>to</span> <span
  m='476910'>be</span> <span m='477030'>0.</span> </p><p><span
  m='477825'>So</span> <span m='478200'>for</span> <span m='478380'>n</span>
  <span m='478760'>not</span> <span m='478870'>equal</span> <span
  m='479280'>to</span> <span m='479680'>k,</span> <span m='481260'>the</span>
  <span m='481350'>value</span> <span m='481710'>of</span> <span
  m='481770'>this</span> <span m='481980'>integral</span> <span
  m='482640'>is</span> <span m='482760'>0,</span> <span
  m='484290'>whereas</span> <span m='485520'>for</span> <span
  m='485730'>n</span> <span m='486120'>equal</span> <span m='486570'>to</span>
  <span m='486780'>k,</span> <span m='490250'>this</span> <span
  m='490460'>exponent</span> <span m='491070'>is</span> <span
  m='491180'>0,</span> <span m='492140'>the</span> <span
  m='492260'>exponential</span> <span m='493010'>is</span> <span
  m='493130'>unity,</span> <span m='494210'>unity</span> <span
  m='494690'>integrated</span> <span m='495380'>from</span> <span
  m='495620'>minus</span> <span m='495980'>pi</span> <span m='496640'>to</span>
  <span m='496790'>pi</span> <span m='497360'>is</span> <span
  m='497510'>equal</span> <span m='497810'>to</span> <span m='497930'>2</span>
  <span m='498140'>pi.</span> <span m='498920'>So</span> <span
  m='499100'>for</span> <span m='499280'>n</span> <span m='499430'>equal</span>
  <span m='499790'>to</span> <span m='499940'>k,</span> <span
  m='500600'>the</span> <span m='500690'>value</span> <span m='501260'>of</span>
  <span m='501410'>the</span> <span m='501530'>integral</span> <span
  m='502190'>is</span> <span m='502310'>equal</span> <span m='502610'>to</span>
  <span m='502730'>2</span> <span m='502970'>pi.</span> <span
  m='504710'>Well</span> <span m='504920'>that</span> <span
  m='505130'>means</span> <span m='505580'>that</span> <span
  m='505820'>the</span> <span m='505970'>only</span> <span
  m='506270'>term</span> <span m='506630'>in</span> <span m='506750'>this</span>
  <span m='506930'>sum</span> <span m='508280'>that</span> <span
  m='508850'>is</span> <span m='509030'>going</span> <span m='509240'>to</span>
  <span m='509360'>contribute</span> <span m='509870'>to</span> <span
  m='510020'>the</span> <span m='510200'>answer</span> <span
  m='511220'>is</span> <span m='511850'>the</span> <span m='511940'>term</span>
  <span m='512360'>for</span> <span m='512539'>k</span> <span
  m='512990'>equal</span> <span m='513350'>to</span> <span m='513470'>n,</span>
  <span m='513919'>because</span> <span m='514280'>for</span> <span
  m='514460'>all</span> <span m='514610'>the</span> <span
  m='514730'>others</span> <span m='515000'>the</span> <span
  m='515120'>integral</span> <span m='515510'>is</span> <span
  m='515570'>0.</span> <span m='516514'>So</span> <span m='516860'>for</span>
  <span m='517340'>k</span> <span m='517520'>equal</span> <span
  m='518030'>to</span> <span m='518179'>n,</span> <span m='518780'>that's</span>
  <span m='519020'>the</span> <span m='519169'>only</span> <span
  m='519409'>non-zero</span> <span m='520070'>term,</span> <span
  m='520700'>for</span> <span m='521059'>k</span> <span m='521179'>equal</span>
  <span m='521690'>to</span> <span m='521809'>n,</span> <span
  m='522200'>the</span> <span m='522289'>value</span> <span m='522679'>of</span>
  <span m='522740'>this</span> <span m='522919'>integral</span> <span
  m='523280'>is</span> <span m='523429'>2</span> <span m='523669'>pi,</span>
  <span m='524700'>which</span> <span m='524780'>will</span> <span
  m='524900'>cancel</span> <span m='525380'>out</span> <span
  m='525530'>this</span> <span m='525710'>1</span> <span m='525890'>over</span>
  <span m='526130'>2</span> <span m='526370'>pi</span> <span
  m='527300'>and</span> <span m='527420'>consequently</span> <span
  m='528815'>we</span> <span m='529160'>get</span> <span m='529310'>h</span>
  <span m='529720'>of n.</span> </p><p><span m='530976'>All right,</span> <span
  m='531470'>so</span> <span m='532400'>this</span> <span m='532910'>is,</span>
  <span m='533360'>in</span> <span m='533510'>a</span> <span
  m='533540'>sense,</span> <span m='533900'>a</span> <span
  m='533990'>formal</span> <span m='535910'>justification</span> <span
  m='537200'>for</span> <span m='537380'>the</span> <span m='537500'>fact</span>
  <span m='538130'>that,</span> <span m='538530'>indeed</span> <span
  m='538910'>this</span> <span m='539150'>is</span> <span m='539570'>the</span>
  <span m='539810'>inverse</span> <span m='541280'>relationship</span> <span
  m='542330'>to</span> <span m='542720'>express</span> <span m='543260'>h</span>
  <span m='543530'>of</span> <span m='543650'>n</span> <span
  m='544160'>terms</span> <span m='544670'>of</span> <span m='544850'>the</span>
  <span m='544940'>frequency</span> <span m='545480'>response.</span> <span
  m='547280'>Although,</span> <span m='548060'>in</span> <span
  m='548210'>fact</span> <span m='548900'>it's</span> <span
  m='549080'>more</span> <span m='549290'>useful</span> <span
  m='549830'>in</span> <span m='549950'>terms</span> <span m='550280'>of</span>
  <span m='550370'>insight</span> <span m='551300'>to</span> <span
  m='551420'>think</span> <span m='551780'>of</span> <span m='551930'>it</span>
  <span m='552470'>as</span> <span m='553100'>the</span> <span
  m='553190'>Fourier</span> <span m='553670'>series</span> <span
  m='554090'>coefficients</span> <span m='555440'>of</span> <span
  m='555860'>a</span> <span m='555950'>function,</span> <span
  m='556700'>a</span> <span m='556760'>periodic</span> <span
  m='557420'>function,</span> <span m='558080'>of</span> <span
  m='558230'>the</span> <span m='558320'>continuous</span> <span
  m='559340'>variable</span> <span m='559850'>omega.</span> </p><p><span
  m='562280'>Now</span> <span m='563240'>this</span> <span m='563870'>in</span>
  <span m='564020'>essence,</span> <span m='564740'>is</span> <span
  m='565310'>a</span> <span m='565730'>Fourier</span> <span
  m='566840'>domain</span> <span m='568700'>representation</span> <span
  m='570410'>for</span> <span m='570920'>the</span> <span m='571070'>unit</span>
  <span m='571370'>sample</span> <span m='571790'>response</span> <span
  m='572390'>of</span> <span m='572510'>a</span> <span m='572540'>system.</span>
  <span m='573020'>And</span> <span m='573110'>in</span> <span
  m='573200'>fact,</span> <span m='573630'>we</span> <span m='573730'>can</span>
  <span m='573770'>think</span> <span m='574070'>of</span> <span
  m='574220'>this</span> <span m='575180'>as</span> <span m='575690'>a</span>
  <span m='575810'>Fourier</span> <span m='576200'>transform</span> <span
  m='577310'>or</span> <span m='577790'>a</span> <span m='579260'>time</span>
  <span m='579560'>domain,</span> <span m='580100'>Fourier</span> <span
  m='580610'>domain</span> <span m='581980'>transform</span> <span
  m='582780'>pair,</span> <span m='583760'>relating</span> <span
  m='584540'>the</span> <span m='584660'>unit</span> <span
  m='584960'>sample</span> <span m='585380'>response</span> <span
  m='586850'>of</span> <span m='586970'>a</span> <span m='587030'>system</span>
  <span m='587660'>and</span> <span m='587780'>the</span> <span
  m='587870'>frequency</span> <span m='588410'>response</span> <span
  m='588890'>of</span> <span m='589010'>the</span> <span
  m='589100'>system.</span> <span m='589490'>And</span> <span
  m='589580'>we</span> <span m='589700'>can</span> <span m='589850'>go</span>
  <span m='590030'>back</span> <span m='590300'>and</span> <span
  m='590420'>forth.</span> </p><p><span m='591840'>Now</span> <span
  m='592940'>one</span> <span m='593150'>of</span> <span m='593720'>the</span>
  <span m='594230'>obvious</span> <span m='595010'>facts</span> <span
  m='595580'>is</span> <span m='595820'>that</span> <span m='597770'>any</span>
  <span m='598040'>sequence,</span> <span m='599240'>if</span> <span
  m='599390'>we</span> <span m='599510'>wanted</span> <span
  m='599870'>to,</span> <span m='600860'>we</span> <span m='600980'>could</span>
  <span m='601160'>think</span> <span m='601490'>of</span> <span
  m='601910'>as</span> <span m='602480'>the</span> <span m='602600'>unit</span>
  <span m='602900'>sample</span> <span m='603320'>response</span> <span
  m='603860'>of</span> <span m='603950'>a</span> <span m='604010'>system.</span>
  <span m='605950'>Well,</span> <span m='606490'>that</span> <span
  m='606730'>suggests</span> <span m='607240'>then</span> <span
  m='607810'>that</span> <span m='608530'>this</span> <span
  m='609220'>transform</span> <span m='609970'>pair</span> <span
  m='611170'>isn't</span> <span m='611470'>restricted</span> <span
  m='612460'>to</span> <span m='612610'>just</span> <span
  m='612940'>sequences</span> <span m='613810'>that</span> <span
  m='613960'>we</span> <span m='614140'>explicitly</span> <span
  m='614950'>identify</span> <span m='616270'>as</span> <span
  m='616420'>the</span> <span m='616510'>unit</span> <span
  m='616780'>sample</span> <span m='617200'>response</span> <span
  m='617710'>of</span> <span m='617800'>a</span> <span m='617860'>system.</span>
  <span m='618490'>It</span> <span m='618900'>in</span> <span
  m='619150'>fact</span> <span m='619480'>permits</span> <span
  m='619900'>the</span> <span m='620020'>representation</span> <span
  m='621280'>of</span> <span m='622000'>an</span> <span
  m='622150'>arbitrary,</span> <span m='622930'>not</span> <span
  m='623140'>quite</span> <span m='623410'>arbitrary</span> <span
  m='624010'>as</span> <span m='624130'>we'll</span> <span m='624250'>see</span>
  <span m='624460'>in</span> <span m='624550'>a</span> <span
  m='624610'>while,</span> <span m='625120'>but</span> <span
  m='627070'>the</span> <span m='627190'>representation</span> <span
  m='628210'>of</span> <span m='628600'>a</span> <span m='628660'>more</span>
  <span m='628900'>general</span> <span m='629290'>class</span> <span
  m='630160'>of</span> <span m='630250'>sequences</span> <span
  m='631000'>than</span> <span m='631150'>just</span> <span
  m='631480'>the</span> <span m='631570'>ones</span> <span
  m='631840'>that</span> <span m='631930'>we</span> <span
  m='632470'>explicitly</span> <span m='633160'>identify</span> <span
  m='633990'>as</span> <span m='634150'>the</span> <span m='634240'>unit</span>
  <span m='634480'>sample</span> <span m='634870'>response</span> <span
  m='635320'>of</span> <span m='635410'>a</span> <span m='635470'>system.</span>
  </p><p><span m='636490'>That</span> <span m='636730'>is,</span> <span
  m='637390'>we</span> <span m='637480'>can</span> <span
  m='637660'>generalize</span> <span m='638350'>this</span> <span
  m='638470'>set</span> <span m='638710'>of</span> <span m='638860'>ideas</span>
  <span m='640030'>to</span> <span m='640660'>the</span> <span
  m='641640'>Fourier</span> <span m='642250'>transform,</span> <span
  m='644120'>which</span> <span m='644740'>is</span> <span m='644980'>a</span>
  <span m='645070'>frequency</span> <span m='645670'>domain</span> <span
  m='646480'>representation</span> <span m='648040'>of</span> <span
  m='648940'>an</span> <span m='649060'>arbitrary,</span> <span
  m='650140'>again</span> <span m='650620'>not</span> <span
  m='650770'>quite</span> <span m='651100'>arbitrary,</span> <span
  m='651760'>but</span> <span m='651910'>for</span> <span m='652030'>the</span>
  <span m='652120'>time</span> <span m='652420'>being</span> <span
  m='652660'>we'll</span> <span m='652810'>consider</span> <span
  m='653230'>arbitrary</span> <span m='654430'>sequence,</span> <span
  m='655270'>x</span> <span m='655540'>of n.</span> <span
  m='657160'>Well,</span> <span m='657670'>the</span> <span
  m='657790'>Fourier</span> <span m='658240'>transform</span> <span
  m='659320'>then</span> <span m='659800'>is</span> <span
  m='660010'>defined</span> <span m='660760'>as</span> <span m='662370'>x</span>
  <span m='662640'>of</span> <span m='662770'>e to</span> <span
  m='662950'>the</span> <span m='663070'>j</span> <span m='663310'>omega,</span>
  <span m='664700'>which</span> <span m='664810'>is</span> <span
  m='664990'>the</span> <span m='665080'>sum</span> <span m='666040'>of</span>
  <span m='666160'>x</span> <span m='666390'>of</span> <span m='666560'>n,
  e</span> <span m='666910'>to</span> <span m='667180'>the</span> <span
  m='667270'>minus j</span> <span m='667630'>omega</span> <span
  m='667975'>n,</span> <span m='669860'>the</span> <span
  m='670100'>Fourier</span> <span m='670560'>transform</span> <span
  m='671292'>x</span> <span m='671660'>of e</span> <span m='672110'>to</span>
  <span m='672210'>the</span> <span m='672300'>j</span> <span
  m='672510'>omega,</span> <span m='674310'>of</span> <span m='674940'>a</span>
  <span m='674970'>sequence,</span> <span m='676020'>x</span> <span
  m='676350'>of</span> <span m='676470'>n,</span> <span m='677760'>is</span>
  <span m='678090'>essentially</span> <span m='679050'>the</span> <span
  m='679170'>frequency</span> <span m='679680'>response</span> <span
  m='680520'>of</span> <span m='680670'>a</span> <span m='680730'>system</span>
  <span m='681630'>whose</span> <span m='681840'>unit</span> <span
  m='682110'>sample</span> <span m='682530'>response</span> <span
  m='683250'>would</span> <span m='683430'>be</span> <span m='683610'>x</span>
  <span m='683850'>of n.</span> </p><p><span m='684960'>So</span> <span
  m='685800'>then</span> <span m='685980'>obviously</span> <span
  m='686640'>from</span> <span m='686850'>what</span> <span m='687360'>we</span>
  <span m='688200'>just</span> <span m='688560'>finished</span> <span
  m='688950'>discussing,</span> <span m='690120'>we</span> <span
  m='690270'>have</span> <span m='690600'>an</span> <span
  m='690720'>inverse</span> <span m='691170'>relationship</span> <span
  m='692430'>that</span> <span m='692550'>tells</span> <span
  m='692970'>us</span> <span m='693390'>what</span> <span m='693600'>x</span>
  <span m='693840'>of n</span> <span m='694170'>is</span> <span
  m='694950'>in</span> <span m='695070'>terms</span> <span m='695430'>of</span>
  <span m='695550'>x</span> <span m='695760'>of</span> <span m='695880'>e
  to</span> <span m='696060'>the</span> <span m='696150'>j</span> <span
  m='696390'>omega.</span> <span m='697260'>And</span> <span
  m='697800'>that</span> <span m='698040'>then</span> <span m='698520'>is</span>
  <span m='698670'>this</span> <span m='698880'>relationship.</span>
  </p><p><span m='702420'>Well</span> <span m='703620'>this</span> <span
  m='704130'>then</span> <span m='704580'>provides</span> <span
  m='706290'>a</span> <span m='708100'>transform</span> <span
  m='708910'>pair,</span> <span m='710260'>or</span> <span m='710680'>a</span>
  <span m='710770'>frequency</span> <span m='711310'>domain,</span> <span
  m='711670'>time</span> <span m='712000'>domain</span> <span
  m='712360'>relationship</span> <span m='713650'>between</span> <span
  m='714010'>sequences</span> <span m='714850'>and</span> <span
  m='715000'>frequency</span> <span m='715540'>domain</span> <span
  m='715990'>functions.</span> <span m='717430'>And</span> <span
  m='717850'>it's</span> <span m='718060'>useful,</span> <span
  m='718810'>in</span> <span m='718960'>fact,</span> <span m='719950'>to</span>
  <span m='720130'>interpret</span> <span m='721360'>this</span> <span
  m='721750'>expression</span> <span m='723550'>somewhat</span> <span
  m='724270'>heuristically</span> <span m='724810'>again</span> <span
  m='726130'>as</span> <span m='726610'>basically</span> <span
  m='727270'>corresponding</span> <span m='728920'>to</span> <span
  m='729100'>a</span> <span m='729190'>decomposition</span> <span
  m='730840'>of</span> <span m='731020'>a</span> <span
  m='731080'>sequence,</span> <span m='732160'>x</span> <span
  m='732430'>of</span> <span m='732550'>n,</span> <span m='733630'>in</span>
  <span m='733750'>terms</span> <span m='734470'>of</span> <span
  m='735280'>complex</span> <span m='735910'>exponentials</span> <span
  m='738040'>with</span> <span m='738490'>incremental</span> <span
  m='739150'>amplitude.</span> </p><p><span m='740590'>This</span> <span
  m='740800'>is</span> <span m='740920'>basically</span> <span
  m='741580'>an</span> <span m='741670'>expression</span> <span
  m='743170'>that</span> <span m='743320'>says</span> <span
  m='743620'>that</span> <span m='743740'>x</span> <span m='744010'>of</span>
  <span m='744160'>n</span> <span m='744880'>is</span> <span m='745030'>a</span>
  <span m='745120'>sum,</span> <span m='745660'>except</span> <span
  m='746140'>that</span> <span m='746250'>it's</span> <span
  m='746410'>sum</span> <span m='747250'>sort</span> <span m='747490'>of</span>
  <span m='747580'>in</span> <span m='747670'>the</span> <span
  m='747760'>limit</span> <span m='748300'>which</span> <span
  m='748540'>corresponds</span> <span m='749200'>to</span> <span
  m='749380'>an</span> <span m='749470'>integral,</span> <span
  m='750730'>of</span> <span m='751810'>a</span> <span m='751870'>set</span>
  <span m='752140'>of</span> <span m='752230'>complex</span> <span
  m='752830'>exponentials</span> <span m='754060'>with</span> <span
  m='754240'>amplitudes</span> <span m='755290'>that</span> <span
  m='755560'>are</span> <span m='755740'>essentially</span> <span
  m='756340'>given</span> <span m='756730'>by</span> <span m='757660'>the</span>
  <span m='757750'>Fourier</span> <span m='758230'>transform</span> <span
  m='758585'>x</span> <span m='758940'>of e</span> <span m='759240'>to</span>
  <span m='759380'>the</span> <span m='759490'>j</span> <span
  m='759730'>omega.</span> <span m='760720'>Well</span> <span
  m='760990'>in</span> <span m='761080'>fact,</span> <span m='761510'>you</span>
  <span m='761610'>can</span> <span m='761650'>see</span> <span
  m='761860'>this</span> <span m='762100'>a</span> <span
  m='762130'>little</span> <span m='762370'>more</span> <span
  m='762580'>explicitly</span> <span m='763900'>if</span> <span
  m='764200'>we</span> <span m='764560'>consider</span> <span
  m='765070'>this</span> <span m='765310'>integral</span> <span
  m='766660'>as</span> <span m='766960'>the</span> <span
  m='767080'>limiting</span> <span m='767500'>form</span> <span
  m='767860'>of</span> <span m='767980'>a</span> <span m='768040'>sum,</span>
  <span m='769300'>the</span> <span m='769420'>limit,</span> <span
  m='770380'>as</span> <span m='770560'>delta</span> <span
  m='770890'>omega</span> <span m='771370'>goes</span> <span
  m='771700'>to</span> <span m='771820'>0,</span> <span m='772980'>of</span>
  <span m='773130'>the</span> <span m='773230'>sum</span> <span
  m='774205'>of</span> <span m='774520'>x</span> <span m='774700'>of</span>
  <span m='775030'>e</span> <span m='775320'>to</span> <span
  m='775430'>the</span> <span m='775540'>j</span> <span m='775870'>k</span>
  <span m='776230'>delta</span> <span m='776590'>omega,</span> <span
  m='777940'>times</span> <span m='778270'>delta</span> <span
  m='778660'>omega</span> <span m='779080'>over</span> <span m='779380'>2</span>
  <span m='779590'>pi,</span> <span m='780500'>e</span> <span
  m='780780'>to</span> <span m='780970'>the</span> <span m='781090'>j</span>
  <span m='781440'>k</span> <span m='782020'>delta</span> <span
  m='782380'>omega</span> <span m='782860'>n.</span> <span
  m='784630'>This</span> <span m='784900'>limit</span> <span
  m='785800'>is</span> <span m='786310'>by</span> <span
  m='786550'>definition,</span> <span m='787810'>what</span> <span
  m='788320'>this</span> <span m='788560'>integral</span> <span
  m='789010'>is.</span> </p><p><span m='790090'>So</span> <span
  m='790570'>an</span> <span m='790690'>important</span> <span
  m='791470'>point</span> <span m='792460'>to</span> <span
  m='792580'>keep</span> <span m='792850'>in</span> <span m='792940'>mind</span>
  <span m='793930'>is</span> <span m='794110'>that</span> <span
  m='794830'>basically</span> <span m='795430'>the</span> <span
  m='795550'>Fourier</span> <span m='795970'>transform</span> <span
  m='797680'>corresponds</span> <span m='798670'>to</span> <span
  m='798850'>a</span> <span m='798910'>decomposition</span> <span
  m='800380'>of</span> <span m='800500'>a</span> <span
  m='800560'>sequence</span> <span m='802000'>in</span> <span
  m='802150'>terms</span> <span m='802750'>of</span> <span m='803740'>a</span>
  <span m='803830'>linear</span> <span m='804220'>combination</span> <span
  m='805150'>of</span> <span m='805300'>complex</span> <span
  m='805870'>exponentials</span> <span m='807220'>with</span> <span
  m='807400'>incremental</span> <span m='807910'>amplitudes.</span> <span
  m='810730'>There</span> <span m='811210'>are</span> <span m='811840'>a</span>
  <span m='811900'>number</span> <span m='812230'>of</span> <span
  m='812350'>reasons</span> <span m='813250'>why</span> <span
  m='813820'>that's</span> <span m='814120'>an</span> <span
  m='814180'>important</span> <span m='814600'>point</span> <span
  m='814870'>of</span> <span m='814930'>view.</span> <span m='816130'>One</span>
  <span m='816400'>of</span> <span m='816910'>the</span> <span
  m='817030'>reasons</span> <span m='817780'>is</span> <span
  m='818050'>that</span> <span m='818440'>it</span> <span
  m='818590'>leads</span> <span m='819340'>to</span> <span m='819820'>a</span>
  <span m='819880'>very</span> <span m='820210'>important</span> <span
  m='820660'>property</span> <span m='821920'>of</span> <span
  m='822460'>linear</span> <span m='822820'>shift</span> <span
  m='823150'>invariance</span> <span m='823710'>systems,</span> <span
  m='825130'>which</span> <span m='825730'>I</span> <span
  m='826330'>refer</span> <span m='826810'>to</span> <span m='827350'>as</span>
  <span m='828280'>the</span> <span m='828370'>convolution</span> <span
  m='829180'>property,</span> <span m='831100'>and</span> <span
  m='832000'>which</span> <span m='832240'>states</span> <span
  m='833290'>that</span> <span m='834970'>if</span> <span m='835390'>I</span>
  <span m='835600'>have</span> <span m='837790'>the</span> <span
  m='838060'>convolution</span> <span m='840010'>of</span> <span
  m='840220'>two</span> <span m='840430'>sequences,</span> <span
  m='841900'>x</span> <span m='842200'>of n</span> <span m='843640'>and</span>
  <span m='844360'>y</span> <span m='844720'>of</span> <span
  m='844870'>n,</span> <span m='846490'>then</span> <span m='847060'>the</span>
  <span m='847210'>Fourier</span> <span m='847630'>transform</span> <span
  m='848410'>of</span> <span m='848560'>those</span> <span m='849670'>is</span>
  <span m='850360'>the</span> <span m='850480'>product</span> <span
  m='851440'>of</span> <span m='851710'>their</span> <span
  m='851870'>Fourier</span> <span m='852340'>transforms.</span> <span
  m='853780'>And</span> <span m='854050'>this</span> <span m='854230'>of</span>
  <span m='854350'>course,</span> <span m='854980'>shouldn't</span> <span
  m='855340'>be</span> <span m='855820'>an</span> <span m='855940'>h,</span>
  <span m='856450'>it</span> <span m='856540'>should</span> <span
  m='856780'>be</span> <span m='857970'>a</span> <span m='858070'>y.</span>
  <span m='859940'>Or</span> <span m='860710'>this</span> <span
  m='860810'>shouldn't</span> <span m='861110'>be</span> <span
  m='861260'>a</span> <span m='861320'>y,</span> <span m='861650'>it</span>
  <span m='861740'>should</span> <span m='861920'>be</span> <span
  m='862070'>an</span> <span m='862160'>h.</span> </p><p><span
  m='863270'>The</span> <span m='863390'>important</span> <span
  m='863840'>property</span> <span m='864470'>is</span> <span
  m='864890'>that</span> <span m='865580'>the</span> <span
  m='865670'>convolution</span> <span m='866630'>of</span> <span
  m='866780'>two</span> <span m='866960'>sequences</span> <span
  m='868190'>has,</span> <span m='868680'>as</span> <span m='868760'>its</span>
  <span m='868910'>Fourier</span> <span m='869360'>transform,</span> <span
  m='870620'>the</span> <span m='870710'>product</span> <span
  m='872000'>of</span> <span m='872480'>the</span> <span
  m='872580'>Fourier</span> <span m='872960'>transforms.</span> <span
  m='875000'>Well</span> <span m='875150'>let's</span> <span
  m='875600'>look</span> <span m='875990'>at</span> <span
  m='877100'>again,</span> <span m='877640'>somewhat</span> <span
  m='878120'>heuristically,</span> <span m='879800'>an</span> <span
  m='879920'>argument</span> <span m='880520'>that</span> <span
  m='880640'>at</span> <span m='880760'>least</span> <span
  m='881030'>justifies</span> <span m='881840'>this,</span> <span
  m='882830'>keeping</span> <span m='883280'>in</span> <span
  m='883370'>mind</span> <span m='884030'>that</span> <span m='884810'>we</span>
  <span m='884930'>could</span> <span m='885080'>go</span> <span
  m='885290'>through</span> <span m='885500'>this</span> <span
  m='885710'>more</span> <span m='885920'>formally,</span> <span
  m='886520'>plugging</span> <span m='886970'>sums</span> <span
  m='887360'>into</span> <span m='887600'>integrals</span> <span
  m='888110'>and</span> <span m='888230'>integrals</span> <span
  m='888650'>into</span> <span m='888890'>sums,</span> <span
  m='889940'>but</span> <span m='890420'>let's</span> <span
  m='890690'>not</span> <span m='890960'>do</span> <span m='891170'>that.</span>
  <span m='891570'>Let's</span> <span m='892130'>look</span> <span
  m='892460'>at</span> <span m='892610'>this</span> <span m='893180'>from</span>
  <span m='893930'>a</span> <span m='894950'>somewhat</span> <span
  m='895730'>heuristic</span> <span m='896630'>point</span> <span
  m='896870'>of</span> <span m='896960'>view.</span> </p><p><span
  m='898860'>First</span> <span m='899090'>of</span> <span
  m='899240'>all,</span> <span m='900000'>we</span> <span m='900080'>have</span>
  <span m='900740'>that</span> <span m='902570'>again,</span> <span
  m='903350'>a</span> <span m='903410'>property</span> <span
  m='903950'>that</span> <span m='904220'>we</span> <span
  m='904370'>began</span> <span m='904760'>the</span> <span
  m='904850'>lecture</span> <span m='905240'>with,</span> <span
  m='906320'>that</span> <span m='906950'>for</span> <span m='907130'>a</span>
  <span m='907160'>linear</span> <span m='907550'>shift</span> <span
  m='907990'>invariant</span> <span m='908460'>system,</span> <span
  m='910450'>a</span> <span m='910550'>complex</span> <span
  m='911150'>exponential</span> <span m='911840'>input</span> <span
  m='913130'>gives</span> <span m='913430'>us</span> <span m='913760'>at</span>
  <span m='913910'>the</span> <span m='914060'>output,</span> <span
  m='915660'>the</span> <span m='915760'>same</span> <span
  m='916640'>complex</span> <span m='917210'>exponential,</span> <span
  m='917990'>that</span> <span m='918140'>is</span> <span m='918350'>the</span>
  <span m='918470'>same</span> <span m='918770'>frequency,</span> <span
  m='919910'>and</span> <span m='920030'>only</span> <span m='920270'>one</span>
  <span m='920480'>of</span> <span m='920630'>them,</span> <span
  m='921530'>multiplied</span> <span m='922490'>by</span> <span m='922745'>h
  of</span> <span m='923000'>e</span> <span m='923285'>to</span> <span
  m='923570'>the</span> <span m='923690'>j</span> <span m='923900'>omega</span>
  <span m='924290'>0.</span> <span m='926150'>That's</span> <span
  m='926450'>a</span> <span m='926540'>consequence</span> <span
  m='927200'>of</span> <span m='927320'>linearity</span> <span
  m='928160'>and</span> <span m='928280'>shift</span> <span
  m='928610'>invariance.</span> <span m='930500'>We</span> <span
  m='930620'>know</span> <span m='930950'>also,</span> <span
  m='932090'>that</span> <span m='933200'>because</span> <span
  m='933860'>of</span> <span m='934040'>the</span> <span m='934130'>fact</span>
  <span m='934520'>that</span> <span m='934670'>the</span> <span
  m='934760'>system</span> <span m='935180'>is</span> <span
  m='935330'>linear,</span> <span m='937340'>if</span> <span
  m='937520'>we</span> <span m='937670'>have</span> <span m='938090'>a</span>
  <span m='938180'>linear</span> <span m='938570'>combination</span> <span
  m='940190'>of</span> <span m='940340'>complex</span> <span
  m='940970'>exponentials,</span> <span m='942980'>then</span> <span
  m='943580'>the</span> <span m='943790'>output</span> <span
  m='944210'>of</span> <span m='944330'>this</span> <span
  m='944440'>system</span> <span m='945530'>is</span> <span
  m='945680'>going</span> <span m='945950'>to</span> <span m='946100'>be</span>
  <span m='946760'>the</span> <span m='946850'>same</span> <span
  m='948020'>linear</span> <span m='948470'>combination</span> <span
  m='949790'>of</span> <span m='950330'>complex</span> <span
  m='950900'>exponentials,</span> <span m='952250'>with</span> <span
  m='952430'>the</span> <span m='952610'>amplitudes</span> <span
  m='953330'>multiplied</span> <span m='954260'>by</span> <span m='954560'>h
  of</span> <span m='955010'>e</span> <span m='955310'>to</span> <span
  m='955610'>the</span> <span m='955690'>j</span> <span m='955940'>omega</span>
  <span m='956630'>k.</span> <span m='957410'>In</span> <span
  m='957500'>other</span> <span m='957710'>words,</span> <span
  m='958650'>each</span> <span m='958790'>of</span> <span
  m='958880'>these</span> <span m='959120'>exponentials</span> <span
  m='960440'>has</span> <span m='960690'>as</span> <span m='960830'>an</span>
  <span m='960950'>output</span> <span m='961810'>ase</span> <span
  m='962140'>of</span> <span m='962390'>k</span> <span m='962840'>times</span>
  <span m='963170'>h</span> <span m='963410'>of</span> <span m='963500'>e to
  the</span> <span m='963690'>j</span> <span m='963890'>omegus</span> <span
  m='964370'>of</span> <span m='964490'>k,</span> <span m='965090'>e</span>
  <span m='965510'>to</span> <span m='965660'>the</span> <span
  m='965780'>j</span> <span m='966180'>omegus</span> <span m='966445'>of</span>
  <span m='966710'>k</span> <span m='966800'>n.</span> <span m='968900'>A</span>
  <span m='969190'>sum</span> <span m='969530'>of</span> <span
  m='969620'>those</span> <span m='969910'>at</span> <span m='969980'>the</span>
  <span m='970130'>input</span> <span m='970700'>gives</span> <span
  m='970940'>us</span> <span m='971090'>a</span> <span m='971180'>sum</span>
  <span m='971480'>at</span> <span m='971570'>the</span> <span
  m='971720'>output</span> <span m='972170'>because</span> <span
  m='972500'>of</span> <span m='972560'>the</span> <span m='972680'>fact</span>
  <span m='973340'>that</span> <span m='973460'>the</span> <span
  m='973580'>system</span> <span m='973940'>is</span> <span
  m='974060'>linear.</span> </p><p><span m='976010'>All</span> <span
  m='976100'>right,</span> <span m='976280'>so</span> <span
  m='976460'>let's</span> <span m='976730'>take</span> <span
  m='977480'>an</span> <span m='977570'>input,</span> <span
  m='978240'>which</span> <span m='978410'>is</span> <span m='978560'>an</span>
  <span m='978680'>arbitrary</span> <span m='979610'>input,</span> <span
  m='980660'>more</span> <span m='980900'>or</span> <span m='980930'>less</span>
  <span m='981230'>arbitrary,</span> <span m='983030'>an</span> <span
  m='983150'>input</span> <span m='983570'>x</span> <span m='983870'>of</span>
  <span m='983990'>n,</span> <span m='986830'>which</span> <span
  m='987430'>I</span> <span m='987640'>can</span> <span
  m='987850'>express</span> <span m='989380'>in</span> <span
  m='989530'>terms</span> <span m='990130'>of</span> <span m='990340'>its</span>
  <span m='990460'>Fourier</span> <span m='990940'>transform,</span> <span
  m='992590'>in</span> <span m='992740'>terms</span> <span m='993340'>of</span>
  <span m='994030'>this</span> <span m='994330'>inverse</span> <span
  m='994840'>Fourier</span> <span m='995290'>transform</span> <span
  m='995890'>relationship.</span> <span m='998620'>All</span> <span
  m='998710'>right,</span> <span m='999150'>now</span> <span
  m='1000120'>m</span> <span m='1000870'>as</span> <span m='1001050'>I</span>
  <span m='1002130'>emphasized</span> <span m='1002910'>just</span> <span
  m='1003180'>a</span> <span m='1003240'>minute</span> <span
  m='1003540'>ago,</span> <span m='1004500'>is</span> <span m='1004680'>a</span>
  <span m='1004740'>decomposition</span> <span m='1006780'>of</span> <span
  m='1007800'>x</span> <span m='1008190'>of n</span> <span m='1009810'>as</span>
  <span m='1010320'>a</span> <span m='1010380'>linear</span> <span
  m='1010800'>combination</span> <span m='1011760'>of</span> <span
  m='1011880'>complex</span> <span m='1012450'>exponentials.</span> <span
  m='1014190'>This</span> <span m='1014400'>is</span> <span m='1014520'>a</span>
  <span m='1014580'>linear</span> <span m='1014910'>combination</span> <span
  m='1015870'>of</span> <span m='1016020'>complex</span> <span
  m='1016560'>exponentials</span> <span m='1017430'>at</span> <span
  m='1017520'>the</span> <span m='1017670'>input,</span> <span
  m='1018600'>so</span> <span m='1018780'>what's</span> <span
  m='1018990'>the</span> <span m='1019140'>output?</span> <span
  m='1020140'>Well,</span> <span m='1020430'>the</span> <span
  m='1020580'>output</span> <span m='1021210'>is</span> <span
  m='1021510'>then</span> <span m='1021720'>going</span> <span
  m='1022020'>to</span> <span m='1022140'>be</span> <span m='1022530'>a</span>
  <span m='1022620'>linear</span> <span m='1023010'>combination</span> <span
  m='1024329'>of</span> <span m='1024780'>complex</span> <span
  m='1025319'>exponentials</span> <span m='1027270'>with</span> <span
  m='1027480'>the</span> <span m='1027660'>amplitude</span> <span
  m='1028560'>of</span> <span m='1028710'>each</span> <span
  m='1028890'>one</span> <span m='1029040'>of</span> <span
  m='1029130'>the</span> <span m='1029250'>input</span> <span
  m='1030180'>exponentials,</span> <span m='1031560'>multiplied</span> <span
  m='1032790'>by</span> <span m='1033630'>the</span> <span
  m='1033720'>frequency</span> <span m='1034319'>response</span> <span
  m='1034890'>of</span> <span m='1034980'>the</span> <span
  m='1035069'>system</span> <span m='1035670'>at</span> <span
  m='1036240'>that</span> <span m='1036420'>frequency.</span> <span
  m='1038050'>So</span> <span m='1038190'>the</span> <span
  m='1038280'>result</span> <span m='1038730'>is</span> <span
  m='1039660'>that</span> <span m='1039960'>with</span> <span
  m='1040170'>this</span> <span m='1040440'>as</span> <span
  m='1040589'>the</span> <span m='1040770'>input,</span> <span
  m='1042420'>what</span> <span m='1043020'>we</span> <span
  m='1043230'>have</span> <span m='1043500'>to</span> <span
  m='1043619'>get</span> <span m='1043950'>at</span> <span
  m='1044099'>the</span> <span m='1044250'>output</span> <span
  m='1048140'>is</span> <span m='1048920'>this,</span> <span
  m='1050780'>the</span> <span m='1050870'>same</span> <span
  m='1051470'>linear</span> <span m='1051860'>combination,</span> <span
  m='1053420'>the</span> <span m='1053540'>only</span> <span
  m='1053810'>change</span> <span m='1054260'>being</span> <span
  m='1054830'>that</span> <span m='1054980'>the</span> <span
  m='1055100'>complex</span> <span m='1055670'>amplitudes</span> <span
  m='1056330'>of</span> <span m='1056420'>the</span> <span
  m='1057110'>input</span> <span m='1058070'>are</span> <span
  m='1058400'>multiplied</span> <span m='1059570'>by</span> <span m='1059825'>h
  of</span> <span m='1060080'>e</span> <span m='1060365'>to</span> <span
  m='1060650'>the</span> <span m='1060740'>j</span> <span
  m='1061040'>omega.</span> </p><p><span m='1063050'>Well,</span> <span
  m='1064220'>this</span> <span m='1064460'>of</span> <span
  m='1064610'>course,</span> <span m='1065930'>is</span> <span
  m='1066770'>the</span> <span m='1066860'>expression</span> <span
  m='1067430'>for</span> <span m='1067580'>the</span> <span
  m='1067730'>output.</span> <span m='1068360'>We</span> <span
  m='1068840'>put</span> <span m='1068990'>in</span> <span m='1069230'>x
  of</span> <span m='1069650'>n,</span> <span m='1070820'>we</span> <span
  m='1070940'>know</span> <span m='1071210'>that</span> <span
  m='1071510'>we're</span> <span m='1071630'>getting</span> <span
  m='1071960'>out</span> <span m='1072170'>y of</span> <span
  m='1072500'>n.</span> <span m='1075430'>So</span> <span
  m='1075880'>obviously</span> <span m='1077260'>this</span> <span
  m='1077860'>then</span> <span m='1078580'>must</span> <span
  m='1078880'>be</span> <span m='1079060'>the</span> <span
  m='1079190'>Fourier</span> <span m='1079660'>transform</span> <span
  m='1081340'>of</span> <span m='1082150'>the</span> <span
  m='1082300'>output</span> <span m='1082690'>of</span> <span
  m='1082780'>the</span> <span m='1082900'>system.</span> <span
  m='1084140'>So</span> <span m='1084280'>what</span> <span
  m='1084460'>this</span> <span m='1084640'>says</span> <span
  m='1085270'>then</span> <span m='1085810'>is</span> <span
  m='1086020'>that</span> <span m='1086920'>the</span> <span
  m='1087010'>Fourier</span> <span m='1087460'>transform</span> <span
  m='1088090'>of</span> <span m='1088210'>the</span> <span
  m='1088360'>output</span> <span m='1088960'>y</span> <span m='1089200'>of
  e</span> <span m='1089630'>to</span> <span m='1089760'>the</span> <span
  m='1089860'>j</span> <span m='1090100'>omega,</span> <span
  m='1091150'>has</span> <span m='1091390'>to</span> <span m='1091540'>be</span>
  <span m='1091750'>this,</span> <span m='1093110'>it</span> <span
  m='1093550'>has</span> <span m='1093640'>to</span> <span m='1093910'>be</span>
  <span m='1094030'>x</span> <span m='1094270'>of e</span> <span
  m='1094780'>to</span> <span m='1094870'>the</span> <span m='1094990'>j</span>
  <span m='1095230'>omega</span> <span m='1096190'>times</span> <span
  m='1096505'>h</span> <span m='1096820'>of e</span> <span m='1097270'>to</span>
  <span m='1097360'>the</span> <span m='1097450'>j</span> <span
  m='1097660'>omega.</span> <span m='1100150'>And</span> <span
  m='1100660'>basically--</span> <span m='1101560'>well, and</span> <span
  m='1101860'>we</span> <span m='1102010'>know</span> <span
  m='1102250'>also</span> <span m='1102940'>that</span> <span
  m='1104920'>y</span> <span m='1105245'>of</span> <span m='1105570'>n</span>
  <span m='1106180'>is</span> <span m='1106390'>going</span> <span
  m='1106540'>to</span> <span m='1106810'>be</span> <span
  m='1106900'>equal</span> <span m='1107080'>to</span> <span m='1107320'>x
  of</span> <span m='1107440'>n</span> <span m='1108430'>convolved</span> <span
  m='1108685'>with</span> <span m='1108940'>h</span> <span m='1109070'>of
  n.</span> <span m='1110650'>So</span> <span m='1111160'>basically,</span>
  <span m='1112270'>this</span> <span m='1112980'>justifies</span> <span
  m='1114310'>the</span> <span m='1114430'>convolution</span> <span
  m='1115210'>property,</span> <span m='1116260'>that</span> <span
  m='1116470'>is</span> <span m='1117010'>the</span> <span
  m='1117100'>convolution</span> <span m='1118000'>of</span> <span
  m='1118120'>two</span> <span m='1118300'>sequences</span> <span
  m='1119500'>has</span> <span m='1119815'>as</span> <span
  m='1120130'>its</span> <span m='1120280'>Fourier</span> <span
  m='1120700'>transform,</span> <span m='1122080'>the</span> <span
  m='1122170'>product</span> <span m='1122800'>of</span> <span
  m='1122920'>the</span> <span m='1123050'>Fourier</span> <span
  m='1123430'>transform</span> <span m='1124330'>of</span> <span
  m='1124480'>each</span> <span m='1124690'>of</span> <span
  m='1124780'>the</span> <span m='1124900'>individual</span> <span
  m='1125440'>sequences.</span> <span m='1126700'>Very</span> <span
  m='1127000'>important</span> <span m='1127450'>property.</span> <span
  m='1128230'>And</span> <span m='1129040'>although</span> <span
  m='1129550'>we</span> <span m='1129700'>can</span> <span m='1129850'>go</span>
  <span m='1130030'>through</span> <span m='1130240'>a</span> <span
  m='1130330'>formal</span> <span m='1131260'>derivation</span> <span
  m='1131950'>of</span> <span m='1132100'>this,</span> <span
  m='1132790'>in</span> <span m='1132940'>fact</span> <span
  m='1134450'>the</span> <span m='1134750'>basic</span> <span
  m='1135290'>reason</span> <span m='1135740'>for</span> <span
  m='1136100'>it</span> <span m='1136610'>is</span> <span
  m='1136820'>tied</span> <span m='1137270'>to</span> <span
  m='1137420'>the</span> <span m='1137540'>arguments</span> <span
  m='1138380'>that</span> <span m='1138560'>I've</span> <span
  m='1138710'>outlined</span> <span m='1139250'>here.</span> <span
  m='1139670'>And</span> <span m='1139820'>in</span> <span
  m='1139910'>terms</span> <span m='1140210'>of</span> <span
  m='1140330'>insight,</span> <span m='1141560'>I</span> <span
  m='1141830'>feel</span> <span m='1142220'>that</span> <span
  m='1142310'>it's</span> <span m='1142430'>more</span> <span
  m='1142640'>important</span> <span m='1143150'>to</span> <span
  m='1143240'>understand</span> <span m='1144350'>this</span> <span
  m='1144560'>way</span> <span m='1144770'>of</span> <span
  m='1144860'>looking</span> <span m='1145190'>at</span> <span
  m='1145400'>it</span> <span m='1145760'>than</span> <span
  m='1146720'>to</span> <span m='1146840'>understand</span> <span
  m='1147440'>a</span> <span m='1147500'>formal</span> <span
  m='1147860'>derivation.</span> </p><p><span m='1150380'>Well,</span> <span
  m='1150860'>this</span> <span m='1151070'>is</span> <span
  m='1151220'>interesting,</span> <span m='1151950'>also</span> <span
  m='1152420'>important,</span> <span m='1153410'>and</span> <span
  m='1153770'>also</span> <span m='1154580'>should</span> <span
  m='1155000'>be</span> <span m='1155240'>familiar</span> <span
  m='1156110'>to</span> <span m='1156290'>you</span> <span m='1156530'>in</span>
  <span m='1156650'>terms</span> <span m='1157160'>of</span> <span
  m='1157850'>things</span> <span m='1158270'>that</span> <span
  m='1158450'>you're</span> <span m='1158570'>used</span> <span
  m='1158810'>to</span> <span m='1158930'>thinking</span> <span
  m='1159350'>about</span> <span m='1159930'>for</span> <span
  m='1160820'>continuous</span> <span m='1161360'>time</span> <span
  m='1161690'>systems.</span> <span m='1162740'>Obviously,</span> <span
  m='1163760'>in</span> <span m='1163880'>continuous</span> <span
  m='1164420'>time</span> <span m='1164720'>systems</span> <span
  m='1165290'>the</span> <span m='1165410'>same</span> <span
  m='1166040'>type</span> <span m='1166370'>of</span> <span
  m='1166430'>property</span> <span m='1166940'>holds.</span> <span
  m='1167930'>That</span> <span m='1168170'>is,</span> <span
  m='1168860'>that</span> <span m='1169010'>the</span> <span
  m='1169100'>Fourier</span> <span m='1169550'>transform</span> <span
  m='1170760'>changes</span> <span m='1172670'>convolution</span> <span
  m='1173410'>to</span> <span m='1173780'>multiplication.</span> <span
  m='1175400'>And</span> <span m='1175790'>in</span> <span
  m='1175970'>fact,</span> <span m='1176360'>it</span> <span
  m='1176450'>permits</span> <span m='1177710'>the</span> <span
  m='1177800'>description</span> <span m='1178820'>of</span> <span
  m='1178970'>a</span> <span m='1179030'>linear</span> <span
  m='1179330'>shift</span> <span m='1179690'>invariant</span> <span
  m='1180180'>system</span> <span m='1182180'>to</span> <span
  m='1182330'>be</span> <span m='1182690'>in</span> <span
  m='1182840'>terms</span> <span m='1183290'>of</span> <span
  m='1183410'>multiplication</span> <span m='1184640'>rather</span> <span
  m='1185030'>than</span> <span m='1185210'>in</span> <span
  m='1185300'>terms</span> <span m='1185630'>of</span> <span
  m='1185720'>convolution.</span> <span m='1187130'>And</span> <span
  m='1187340'>as</span> <span m='1187480'>we'll</span> <span
  m='1187600'>see</span> <span m='1187810'>in</span> <span m='1187910'>a</span>
  <span m='1187970'>number</span> <span m='1188240'>of</span> <span
  m='1188330'>lectures,</span> <span m='1188770'>that</span> <span
  m='1189010'>basically</span> <span m='1190340'>the</span> <span
  m='1190850'>basis</span> <span m='1191990'>for</span> <span
  m='1192740'>the</span> <span m='1192860'>notions</span> <span
  m='1193370'>of</span> <span m='1193460'>filtering</span> <span
  m='1195080'>and</span> <span m='1195560'>some</span> <span
  m='1195770'>other</span> <span m='1195980'>very</span> <span
  m='1196250'>important</span> <span m='1196670'>notions,</span> <span
  m='1197130'>and</span> <span m='1197210'>notions</span> <span
  m='1197570'>of</span> <span m='1197630'>modulation</span> <span
  m='1198350'>etc.</span> </p><p><span m='1199950'>OK,</span> <span
  m='1200540'>key</span> <span m='1200790'>property,</span> <span
  m='1201350'>this</span> <span m='1201590'>is</span> <span m='1201770'>a</span>
  <span m='1201830'>key</span> <span m='1202070'>property</span> <span
  m='1203150'>of</span> <span m='1204050'>linear</span> <span
  m='1204410'>shift</span> <span m='1204710'>invariant</span> <span
  m='1205220'>systems</span> <span m='1205850'>and</span> <span
  m='1206030'>the</span> <span m='1206120'>Fourier</span> <span
  m='1206540'>transform.</span> <span m='1208130'>There</span> <span
  m='1208760'>are,</span> <span m='1209340'>of</span> <span
  m='1209390'>course,</span> <span m='1210240'>lots</span> <span
  m='1210500'>of</span> <span m='1210650'>other</span> <span
  m='1210860'>properties</span> <span m='1211910'>of</span> <span
  m='1212480'>linear</span> <span m='1212840'>shift</span> <span
  m='1213170'>invariant</span> <span m='1213740'>systems--</span> <span
  m='1214910'>sorry,</span> <span m='1215420'>other</span> <span
  m='1215660'>properties,</span> <span m='1216680'>there</span> <span
  m='1216860'>are</span> <span m='1217040'>other</span> <span
  m='1217250'>properties,</span> <span m='1217760'>obviously,</span> <span
  m='1218015'>of</span> <span m='1218270'>linear</span> <span
  m='1218540'>shift</span> <span m='1218840'>invariant</span> <span
  m='1219300'>systems.</span> <span m='1220280'>There</span> <span
  m='1220460'>are</span> <span m='1220970'>other</span> <span
  m='1221210'>properties</span> <span m='1222170'>of</span> <span
  m='1222560'>Fourier</span> <span m='1222980'>transforms</span> <span
  m='1224450'>that</span> <span m='1224780'>are</span> <span
  m='1225230'>important,</span> <span m='1226890'>both</span> <span
  m='1227090'>in</span> <span m='1227210'>terms</span> <span
  m='1227510'>of</span> <span m='1227600'>interpreting</span> <span
  m='1228200'>Fourier</span> <span m='1228620'>transforms</span> <span
  m='1230000'>and</span> <span m='1230540'>in</span> <span
  m='1230750'>terms</span> <span m='1231500'>of</span> <span
  m='1231830'>computing</span> <span m='1233000'>Fourier</span> <span
  m='1233490'>transforms</span> <span m='1234500'>of</span> <span
  m='1235420'>a</span> <span m='1235520'>variety</span> <span
  m='1236060'>of</span> <span m='1236150'>sequences.</span> <span
  m='1237590'>A</span> <span m='1237650'>lot</span> <span m='1237890'>of</span>
  <span m='1237980'>these</span> <span m='1238190'>properties</span> <span
  m='1239240'>will</span> <span m='1239510'>be</span> <span
  m='1239960'>developed</span> <span m='1240860'>in</span> <span
  m='1241490'>the</span> <span m='1241580'>text</span> <span
  m='1242210'>and</span> <span m='1242330'>also</span> <span
  m='1242690'>in</span> <span m='1242750'>the</span> <span
  m='1242840'>study</span> <span m='1243200'>guide,</span> <span
  m='1244580'>so</span> <span m='1244820'>you'll</span> <span
  m='1245000'>have</span> <span m='1245180'>to</span> <span
  m='1245300'>do</span> <span m='1245450'>the</span> <span
  m='1245570'>work</span> <span m='1245810'>rather</span> <span
  m='1246110'>than</span> <span m='1246290'>me.</span> <span
  m='1247340'>But</span> <span m='1247790'>let</span> <span
  m='1248000'>me</span> <span m='1248330'>just</span> <span
  m='1248840'>indicate</span> <span m='1249650'>one</span> <span
  m='1249980'>class</span> <span m='1250430'>of</span> <span
  m='1250520'>properties</span> <span m='1251390'>that,</span> <span
  m='1251720'>again,</span> <span m='1252680'>should</span> <span
  m='1252890'>be</span> <span m='1253040'>very</span> <span
  m='1253310'>familiar</span> <span m='1253790'>to</span> <span
  m='1254000'>you</span> <span m='1255020'>if</span> <span
  m='1255410'>you</span> <span m='1256130'>relate</span> <span
  m='1256490'>your</span> <span m='1256610'>thinking</span> <span
  m='1257090'>back</span> <span m='1257540'>to</span> <span
  m='1257810'>continuous</span> <span m='1258410'>time</span> <span
  m='1259130'>Fourier</span> <span m='1259570'>transforms.</span> <span
  m='1260990'>And</span> <span m='1261080'>that</span> <span
  m='1261320'>is</span> <span m='1262250'>the</span> <span
  m='1262340'>class</span> <span m='1262880'>of</span> <span
  m='1263000'>symmetry</span> <span m='1263570'>properties</span> <span
  m='1264890'>for</span> <span m='1265550'>the</span> <span
  m='1265650'>special</span> <span m='1266150'>case</span> <span
  m='1266780'>in</span> <span m='1266930'>which</span> <span
  m='1267290'>the</span> <span m='1267410'>sequences</span> <span
  m='1268340'>that</span> <span m='1268490'>we're</span> <span
  m='1268610'>talking</span> <span m='1269090'>about</span> <span
  m='1269930'>are</span> <span m='1270380'>real</span> <span
  m='1270710'>sequences.</span> </p><p><span m='1273320'>Well</span> <span
  m='1274280'>the</span> <span m='1274370'>basic</span> <span
  m='1275120'>symmetry</span> <span m='1275660'>property</span> <span
  m='1276890'>is</span> <span m='1277100'>that</span> <span
  m='1278000'>for</span> <span m='1278420'>x</span> <span m='1278690'>of</span>
  <span m='1278840'>n</span> <span m='1279020'>real</span> <span
  m='1280220'>the</span> <span m='1280310'>Fourier</span> <span
  m='1280760'>transform</span> <span m='1281630'>is</span> <span
  m='1281810'>a</span> <span m='1281870'>conjugate</span> <span
  m='1282710'>symmetric</span> <span m='1283640'>function,</span> <span
  m='1285680'>x</span> <span m='1285980'>of</span> <span m='1286100'>e to</span>
  <span m='1286280'>the</span> <span m='1286400'>j</span> <span
  m='1286610'>omega</span> <span m='1287630'>is</span> <span
  m='1287810'>equal</span> <span m='1288170'>to</span> <span
  m='1288980'>x</span> <span m='1289250'>conjugate</span> <span
  m='1290180'>of</span> <span m='1290570'>e</span> <span m='1290930'>to</span>
  <span m='1291050'>the</span> <span m='1291170'>minus</span> <span
  m='1291710'>j</span> <span m='1291950'>omega.</span> <span
  m='1294410'>And</span> <span m='1295460'>we</span> <span
  m='1295670'>can</span> <span m='1296330'>see</span> <span
  m='1296630'>that,</span> <span m='1297320'>essentially</span> <span
  m='1298130'>in</span> <span m='1298220'>a</span> <span
  m='1298280'>straightforward</span> <span m='1299030'>way,</span> <span
  m='1299330'>that</span> <span m='1299510'>is</span> <span
  m='1299660'>the</span> <span m='1299750'>derivation</span> <span
  m='1300740'>is</span> <span m='1301760'>effectively</span> <span
  m='1302330'>straightforward.</span> <span m='1304000'>Here's</span> <span
  m='1304410'>x</span> <span m='1304580'>of e</span> <span m='1304990'>to</span>
  <span m='1305100'>the</span> <span m='1305180'>j</span> <span
  m='1305390'>omega,</span> <span m='1305990'>the</span> <span
  m='1306080'>sum</span> <span m='1306380'>of</span> <span m='1306470'>x</span>
  <span m='1306810'>of n,</span> <span m='1307490'>e</span> <span
  m='1307700'>to</span> <span m='1307760'>the</span> <span
  m='1307880'>minus</span> <span m='1308280'>j</span> <span
  m='1308420'>omega</span> <span m='1308900'>n.</span> <span
  m='1310730'>Here</span> <span m='1311120'>is</span> <span m='1311540'>x</span>
  <span m='1311840'>of</span> <span m='1311930'>e</span> <span
  m='1312030'>to</span> <span m='1312110'>the</span> <span m='1312200'>minus
  j</span> <span m='1312560'>omega.</span> <span m='1314150'>Well,</span> <span
  m='1314480'>the</span> <span m='1314570'>only</span> <span
  m='1314810'>difference</span> <span m='1315530'>between</span> <span
  m='1315950'>that</span> <span m='1316190'>and</span> <span
  m='1316280'>that</span> <span m='1316670'>is</span> <span
  m='1316970'>that</span> <span m='1317750'>we</span> <span
  m='1317900'>replace</span> <span m='1318320'>omega</span> <span
  m='1318700'>by</span> <span m='1318890'>minus</span> <span
  m='1319310'>omega,</span> <span m='1320000'>so</span> <span
  m='1320210'>this</span> <span m='1320390'>becomes</span> <span
  m='1320780'>a</span> <span m='1320840'>plus</span> <span
  m='1321110'>sign.</span> <span m='1322400'>Of</span> <span
  m='1322460'>course,</span> <span m='1322830'>it's</span> <span
  m='1322880'>not</span> <span m='1323110'>this</span> <span
  m='1323360'>that</span> <span m='1323510'>we</span> <span
  m='1323690'>want</span> <span m='1325290'>from</span> <span
  m='1325550'>this</span> <span m='1325730'>expression,</span> <span
  m='1327110'>it's</span> <span m='1327710'>the</span> <span
  m='1327830'>conjugate</span> <span m='1328430'>of</span> <span
  m='1328580'>that.</span> <span m='1329450'>So</span> <span
  m='1330200'>we</span> <span m='1330380'>want</span> <span
  m='1330560'>to</span> <span m='1331370'>complex</span> <span
  m='1331940'>conjugate</span> <span m='1333500'>this.</span> </p><p><span
  m='1335120'>Well,</span> <span m='1335600'>we</span> <span
  m='1335720'>will</span> <span m='1335840'>do</span> <span
  m='1335990'>the</span> <span m='1336110'>same</span> <span
  m='1336650'>on</span> <span m='1337640'>the</span> <span
  m='1337730'>left--hand</span> <span m='1338300'>side--</span> <span
  m='1338940'>on</span> <span m='1338960'>the</span> <span
  m='1339050'>right-hand</span> <span m='1339500'>side.</span> <span
  m='1341040'>And</span> <span m='1341510'>so</span> <span m='1342260'>we</span>
  <span m='1342440'>would</span> <span m='1342560'>conjugate</span> <span
  m='1343280'>that</span> <span m='1345020'>and</span> <span
  m='1345380'>conjugate</span> <span m='1346100'>this,</span> <span
  m='1346820'>which</span> <span m='1347270'>replaces</span> <span
  m='1348800'>this</span> <span m='1349790'>plus</span> <span
  m='1350060'>sign</span> <span m='1350900'>with</span> <span
  m='1351040'>a</span> <span m='1351080'>minus</span> <span
  m='1351470'>sign.</span> <span m='1353910'>But</span> <span
  m='1355250'>we're</span> <span m='1355370'>talking</span> <span
  m='1355850'>about</span> <span m='1356600'>a</span> <span
  m='1356690'>real</span> <span m='1356960'>sequence,</span> <span
  m='1357470'>x</span> <span m='1357740'>of</span> <span m='1357920'>n,</span>
  <span m='1359180'>so</span> <span m='1359555'>x</span> <span
  m='1359930'>conjugate</span> <span m='1360170'>of</span> <span
  m='1360425'>n</span> <span m='1360680'>is</span> <span m='1361010'>just</span>
  <span m='1361250'>x</span> <span m='1361490'>of n.</span> <span
  m='1361920'>In</span> <span m='1361970'>other</span> <span
  m='1362120'>words,</span> <span m='1363150'>this</span> <span
  m='1363350'>is</span> <span m='1364070'>just</span> <span
  m='1364390'>the</span> <span m='1364430'>x</span> <span m='1364680'>of</span>
  <span m='1364790'>an</span> <span m='1365180'>all</span> <span
  m='1365390'>over</span> <span m='1365720'>again.</span> <span
  m='1366870'>And</span> <span m='1367220'>so</span> <span m='1367490'>we</span>
  <span m='1367670'>have</span> <span m='1368060'>that</span> <span
  m='1368240'>x</span> <span m='1368480'>conjugate</span> <span
  m='1368865'>of</span> <span m='1369250'>e</span> <span m='1369500'>to</span>
  <span m='1369590'>the</span> <span m='1369680'>minus</span> <span
  m='1370040'>j omega</span> <span m='1371300'>is</span> <span
  m='1371480'>the</span> <span m='1371600'>sum</span> <span
  m='1372110'>of</span> <span m='1372320'>x</span> <span m='1372600'>of</span>
  <span m='1372740'>n,</span> <span m='1373220'>e</span> <span
  m='1373380'>to</span> <span m='1373520'>the</span> <span
  m='1373610'>minus</span> <span m='1373895'>j</span> <span
  m='1374180'>omega</span> <span m='1374960'>n,</span> <span
  m='1375530'>which</span> <span m='1375930'>is</span> <span
  m='1376010'>just</span> <span m='1376130'>what</span> <span
  m='1376610'>we</span> <span m='1376790'>have</span> <span
  m='1376910'>up</span> <span m='1377090'>here.</span> <span
  m='1377960'>So</span> <span m='1378530'>obviously</span> <span
  m='1379190'>then,</span> <span m='1379700'>these</span> <span
  m='1379940'>two</span> <span m='1380390'>are</span> <span
  m='1380540'>equal.</span> <span m='1381860'>So</span> <span
  m='1382760'>for</span> <span m='1383420'>a</span> <span
  m='1383780'>real</span> <span m='1384110'>sequence,</span> <span
  m='1386130'>the</span> <span m='1386450'>Fourier</span> <span
  m='1386940'>transform</span> <span m='1388070'>is</span> <span
  m='1388490'>a</span> <span m='1388580'>conjugate</span> <span
  m='1389150'>symmetric</span> <span m='1389630'>function.</span> <span
  m='1390660'>This</span> <span m='1390770'>is</span> <span
  m='1391040'>what</span> <span m='1391250'>we'll</span> <span
  m='1391400'>call</span> <span m='1391940'>conjugate</span> <span
  m='1392450'>symmetric.</span> </p><p><span m='1394430'>Well</span> <span
  m='1395360'>let's</span> <span m='1395600'>press</span> <span
  m='1395900'>that</span> <span m='1396080'>a</span> <span
  m='1396140'>little</span> <span m='1396320'>further.</span> <span
  m='1398390'>We</span> <span m='1398540'>have</span> <span m='1399170'>x</span>
  <span m='1399570'>of e</span> <span m='1400000'>to the</span> <span
  m='1400100'>j</span> <span m='1400340'>omega,</span> <span
  m='1401570'>which</span> <span m='1402290'>I</span> <span
  m='1402530'>can</span> <span m='1403460'>represent</span> <span
  m='1404360'>in</span> <span m='1404510'>terms</span> <span
  m='1404870'>of</span> <span m='1404990'>its</span> <span
  m='1405110'>real</span> <span m='1405410'>part</span> <span
  m='1406430'>and</span> <span m='1406520'>its</span> <span
  m='1406670'>imaginary</span> <span m='1407360'>part</span> <span
  m='1408230'>as</span> <span m='1408950'>obviously</span> <span
  m='1409850'>x</span> <span m='1410120'>real,</span> <span m='1410475'>x</span>
  <span m='1410830'>sub</span> <span m='1411000'>r</span> <span
  m='1411490'>of</span> <span m='1411630'>e</span> <span m='1411810'>to</span>
  <span m='1411920'>the</span> <span m='1412010'>j</span> <span
  m='1412340'>omega,</span> <span m='1413270'>plus</span> <span
  m='1413540'>j</span> <span m='1413900'>times</span> <span m='1414170'>x</span>
  <span m='1414440'>sub</span> <span m='1414800'>i</span> <span
  m='1415125'>of</span> <span m='1415450'>e</span> <span m='1415550'>to</span>
  <span m='1415750'>the</span> <span m='1415880'>j</span> <span
  m='1416240'>omega.</span> <span m='1418270'>And</span> <span
  m='1418610'>the</span> <span m='1418700'>conjugate</span> <span
  m='1419210'>symmetric</span> <span m='1421190'>counterpart</span> <span
  m='1422870'>is</span> <span m='1425200'>this</span> <span
  m='1426220'>with</span> <span m='1426610'>omega</span> <span
  m='1427000'>replaced</span> <span m='1427450'>by</span> <span
  m='1427600'>minus</span> <span m='1428020'>omega</span> <span
  m='1428950'>and</span> <span m='1429820'>the</span> <span
  m='1429880'>expression</span> <span m='1430420'>conjugated.</span> <span
  m='1431770'>So</span> <span m='1432160'>we</span> <span
  m='1432340'>have</span> <span m='1432640'>x</span> <span m='1432970'>sub
  r</span> <span m='1434020'>of</span> <span m='1434150'>e</span> <span
  m='1434340'>to</span> <span m='1434390'>the</span> <span m='1434500'>minus
  j</span> <span m='1434850'>omega,</span> <span m='1436390'>minus</span> <span
  m='1436960'>j</span> <span m='1437590'>times</span> <span m='1438040'>x</span>
  <span m='1438340'>sub</span> <span m='1438400'>i</span> <span
  m='1439540'>of</span> <span m='1439840'>e</span> <span m='1440080'>to</span>
  <span m='1440140'>the</span> <span m='1440230'>minus</span> <span
  m='1440560'>j</span> <span m='1440860'>omega.</span> <span
  m='1442090'>And</span> <span m='1442240'>we</span> <span
  m='1442360'>know</span> <span m='1442780'>that</span> <span
  m='1442960'>these</span> <span m='1443200'>two</span> <span
  m='1443440'>are</span> <span m='1443550'>equal.</span> <span
  m='1444910'>Well,</span> <span m='1445240'>if</span> <span
  m='1445390'>these</span> <span m='1445630'>two</span> <span
  m='1445840'>are</span> <span m='1445990'>equal,</span> <span
  m='1446900'>then</span> <span m='1446980'>these</span> <span
  m='1447220'>two</span> <span m='1447460'>are</span> <span
  m='1447610'>equal,</span> <span m='1448280'>and</span> <span
  m='1448600'>so</span> <span m='1448870'>are</span> <span
  m='1448960'>these.</span> <span m='1451430'>The</span> <span
  m='1451550'>real</span> <span m='1451850'>part</span> <span
  m='1452705'>of</span> <span m='1452990'>x of</span> <span m='1453140'>e
  to</span> <span m='1453620'>the</span> <span m='1453730'>j</span> <span
  m='1453980'>omega</span> <span m='1455510'>must</span> <span
  m='1455750'>be</span> <span m='1455930'>equal</span> <span
  m='1456320'>to</span> <span m='1457190'>the</span> <span
  m='1457310'>real</span> <span m='1457550'>part</span> <span
  m='1458030'>of</span> <span m='1458300'>x</span> <span m='1458600'>of</span>
  <span m='1458810'>e</span> <span m='1459130'>to</span> <span
  m='1459360'>the</span> <span m='1459440'>minus</span> <span
  m='1459530'>j</span> <span m='1459920'>omega.</span> </p><p><span
  m='1461300'>In</span> <span m='1461450'>other</span> <span
  m='1461660'>words,</span> <span m='1462510'>the</span> <span
  m='1462530'>real</span> <span m='1462830'>part</span> <span
  m='1463820'>has</span> <span m='1464150'>to</span> <span m='1464300'>be</span>
  <span m='1465290'>the</span> <span m='1465380'>same</span> <span
  m='1466430'>if</span> <span m='1466610'>omega</span> <span
  m='1467210'>is</span> <span m='1467420'>replaced</span> <span
  m='1467870'>by</span> <span m='1468050'>minus</span> <span
  m='1468470'>omega.</span> <span m='1470480'>That</span> <span
  m='1470690'>means</span> <span m='1471050'>then</span> <span
  m='1471590'>that</span> <span m='1472010'>the</span> <span
  m='1472160'>real</span> <span m='1472400'>part</span> <span
  m='1472670'>of</span> <span m='1472730'>the</span> <span
  m='1472820'>Fourier</span> <span m='1473270'>transform</span> <span
  m='1474380'>is</span> <span m='1475910'>an</span> <span
  m='1476090'>even</span> <span m='1476990'>function</span> <span
  m='1477500'>of</span> <span m='1477590'>omega.</span> <span
  m='1478790'>Meaning</span> <span m='1479510'>that</span> <span
  m='1479900'>if</span> <span m='1480140'>we</span> <span
  m='1480260'>replace</span> <span m='1480920'>omega</span> <span
  m='1481340'>by</span> <span m='1481520'>minus</span> <span
  m='1481940'>omega</span> <span m='1483230'>then</span> <span
  m='1484460'>the</span> <span m='1484580'>real</span> <span
  m='1484850'>part</span> <span m='1485270'>doesn't</span> <span
  m='1485570'>change.</span> <span m='1487760'>The</span> <span
  m='1487850'>imaginary</span> <span m='1488360'>part,</span> <span
  m='1488630'>on</span> <span m='1488720'>the</span> <span
  m='1488810'>other</span> <span m='1488990'>hand,</span> <span
  m='1489360'>does.</span> <span m='1490310'>In</span> <span
  m='1490460'>particular,</span> <span m='1492500'>on</span> <span
  m='1492620'>the</span> <span m='1492710'>basis</span> <span
  m='1493160'>of</span> <span m='1493310'>what</span> <span
  m='1493460'>we're</span> <span m='1493610'>saying</span> <span
  m='1494030'>here</span> <span m='1494960'>and</span> <span
  m='1495080'>the</span> <span m='1495170'>equality</span> <span
  m='1495770'>of</span> <span m='1495860'>these,</span> <span
  m='1496960'>the</span> <span m='1497060'>imaginary</span> <span
  m='1497810'>part</span> <span m='1498775'>x</span> <span m='1499140'>sub
  i</span> <span m='1499460'>of</span> <span m='1499780'>e</span> <span
  m='1499970'>to</span> <span m='1500120'>the</span> <span m='1500280'>j
  omega,</span> <span m='1501500'>must</span> <span m='1501740'>be</span> <span
  m='1501950'>equal</span> <span m='1502190'>to</span> <span
  m='1502340'>minus,</span> <span m='1503900'>don't</span> <span
  m='1504050'>forget</span> <span m='1504380'>the</span> <span
  m='1504470'>minus</span> <span m='1504830'>sign,</span> <span
  m='1505880'>minus</span> <span m='1506255'>x</span> <span
  m='1506630'>sub</span> <span m='1506890'>i</span> <span m='1507180'>of</span>
  <span m='1507390'>e</span> <span m='1507530'>to</span> <span
  m='1507630'>the</span> <span m='1507710'>minus</span> <span
  m='1507830'>j</span> <span m='1508190'>omega.</span> <span
  m='1509630'>And</span> <span m='1509750'>that</span> <span
  m='1509990'>says</span> <span m='1510650'>then,</span> <span
  m='1511280'>that</span> <span m='1512090'>if</span> <span
  m='1512270'>we</span> <span m='1512390'>replace</span> <span
  m='1513020'>omega</span> <span m='1513880'>by</span> <span
  m='1514070'>minus</span> <span m='1514520'>omega,</span> <span
  m='1515810'>then</span> <span m='1516350'>the</span> <span
  m='1516470'>sign</span> <span m='1517130'>of</span> <span
  m='1517310'>the</span> <span m='1517400'>imaginary</span> <span
  m='1518000'>part</span> <span m='1518300'>changes.</span> <span
  m='1519350'>So</span> <span m='1520220'>the</span> <span
  m='1520340'>imaginary</span> <span m='1520970'>part,</span> <span
  m='1521420'>in</span> <span m='1521570'>fact,</span> <span
  m='1522320'>is</span> <span m='1522770'>an</span> <span m='1522950'>odd</span>
  <span m='1523250'>function</span> <span m='1523670'>of</span> <span
  m='1523790'>omega.</span> <span m='1524720'>The</span> <span
  m='1524810'>real</span> <span m='1525050'>part</span> <span
  m='1525470'>is</span> <span m='1525620'>an</span> <span
  m='1525740'>even</span> <span m='1526010'>function</span> <span
  m='1526430'>of</span> <span m='1526550'>omega.</span> </p><p><span
  m='1528590'>Well,</span> <span m='1528890'>from</span> <span
  m='1529160'>this,</span> <span m='1529760'>or</span> <span
  m='1530420'>from</span> <span m='1531320'>this,</span> <span
  m='1532370'>we</span> <span m='1532550'>can</span> <span
  m='1532880'>also</span> <span m='1533360'>show</span> <span
  m='1534200'>that</span> <span m='1534860'>the</span> <span
  m='1534950'>magnitude</span> <span m='1535610'>of</span> <span
  m='1535700'>the</span> <span m='1535820'>Fourier</span> <span
  m='1536300'>transform</span> <span m='1537650'>is</span> <span
  m='1538580'>an</span> <span m='1538760'>even</span> <span
  m='1539660'>function</span> <span m='1540380'>of</span> <span
  m='1540530'>omega.</span> <span m='1542520'>And</span> <span
  m='1543110'>the</span> <span m='1543290'>angle</span> <span
  m='1544400'>of</span> <span m='1544580'>the</span> <span
  m='1544670'>Fourier</span> <span m='1545090'>transform</span> <span
  m='1547220'>is</span> <span m='1548990'>an</span> <span m='1549140'>odd</span>
  <span m='1549860'>function</span> <span m='1550310'>of</span> <span
  m='1550430'>omega.</span> <span m='1551610'>And</span> <span
  m='1552170'>those,</span> <span m='1552800'>of</span> <span
  m='1552950'>course,</span> <span m='1553490'>are</span> <span
  m='1553820'>identical</span> <span m='1555050'>to</span> <span
  m='1556100'>what</span> <span m='1556460'>we</span> <span
  m='1556640'>know</span> <span m='1557450'>is</span> <span
  m='1557630'>true</span> <span m='1558140'>for</span> <span
  m='1558290'>the</span> <span m='1558380'>continuous</span> <span
  m='1558950'>time</span> <span m='1559220'>Fourier</span> <span
  m='1559640'>transform.</span> <span m='1561230'>Remember</span> <span
  m='1561680'>however,</span> <span m='1562250'>again,</span> <span
  m='1562580'>that</span> <span m='1562700'>these</span> <span
  m='1562910'>are</span> <span m='1563000'>periodic</span> <span
  m='1563660'>functions,</span> <span m='1564530'>whereas</span> <span
  m='1564860'>in</span> <span m='1564950'>the</span> <span
  m='1565040'>continuous</span> <span m='1565610'>time</span> <span
  m='1565880'>case,</span> <span m='1566420'>they're</span> <span
  m='1566570'>not.</span> </p><p><span m='1569140'>All</span> <span
  m='1569340'>right</span> <span m='1569660'>well,</span> <span
  m='1570170'>this</span> <span m='1570470'>is</span> <span
  m='1571130'>an</span> <span m='1571250'>introduction</span> <span
  m='1572480'>to</span> <span m='1574010'>the</span> <span
  m='1574280'>Fourier</span> <span m='1574700'>transform.</span> <span
  m='1577820'>One</span> <span m='1578030'>of</span> <span
  m='1578450'>the</span> <span m='1579800'>things</span> <span
  m='1580190'>that</span> <span m='1580490'>we've</span> <span
  m='1581660'>refrained</span> <span m='1582230'>from</span> <span
  m='1582470'>doing</span> <span m='1583010'>in</span> <span
  m='1583160'>all</span> <span m='1583370'>of</span> <span
  m='1583460'>these</span> <span m='1583700'>lectures</span> <span
  m='1585020'>is</span> <span m='1586310'>tying</span> <span
  m='1587150'>our</span> <span m='1587840'>development</span> <span
  m='1588470'>too</span> <span m='1588710'>closely</span> <span
  m='1590000'>to</span> <span m='1590720'>the</span> <span
  m='1590840'>notion</span> <span m='1591410'>of</span> <span
  m='1591620'>continuous</span> <span m='1592220'>time</span> <span
  m='1592670'>signals,</span> <span m='1594530'>and</span> <span
  m='1595160'>in</span> <span m='1595310'>particular,</span> <span
  m='1595940'>avoiding</span> <span m='1597020'>to</span> <span
  m='1597110'>some</span> <span m='1597380'>extent,</span> <span
  m='1598040'>the</span> <span m='1598160'>notion</span> <span
  m='1598640'>of</span> <span m='1598760'>interpreting</span> <span
  m='1600200'>discrete</span> <span m='1600590'>time</span> <span
  m='1600890'>signals</span> <span m='1601670'>as</span> <span
  m='1602510'>just</span> <span m='1602750'>simply</span> <span
  m='1603200'>sampled</span> <span m='1603800'>replicas</span> <span
  m='1605060'>of</span> <span m='1605210'>continuous</span> <span
  m='1605780'>time</span> <span m='1606080'>signals.</span> <span
  m='1607100'>And</span> <span m='1607370'>we'll</span> <span
  m='1607520'>continue</span> <span m='1608120'>to</span> <span
  m='1608270'>do</span> <span m='1608480'>that</span> <span
  m='1608840'>throughout</span> <span m='1609260'>this</span> <span
  m='1609410'>set</span> <span m='1609650'>of</span> <span
  m='1609740'>lectures.</span> <span m='1611160'>But</span> <span
  m='1611810'>in</span> <span m='1612110'>particular</span> <span
  m='1612710'>Fourier</span> <span m='1613370'>transform,</span> <span
  m='1614960'>I</span> <span m='1615050'>think</span> <span
  m='1615320'>that</span> <span m='1615440'>it's</span> <span
  m='1615590'>instructive</span> <span m='1616970'>to</span> <span
  m='1617990'>tie</span> <span m='1620180'>together,</span> <span
  m='1621980'>at</span> <span m='1622070'>least</span> <span
  m='1622340'>in</span> <span m='1622430'>terms</span> <span
  m='1622880'>of</span> <span m='1623390'>some</span> <span
  m='1623720'>insight</span> <span m='1624170'>into</span> <span
  m='1624410'>the</span> <span m='1624500'>relationship,</span> <span
  m='1626120'>the</span> <span m='1626360'>continuous</span> <span
  m='1627050'>time</span> <span m='1627540'>Fourier</span> <span
  m='1627980'>transform</span> <span m='1629120'>of</span> <span
  m='1629540'>obviously</span> <span m='1630080'>continuous</span> <span
  m='1630650'>time</span> <span m='1630950'>signal,</span> <span
  m='1632090'>and</span> <span m='1632870'>the</span> <span
  m='1633230'>discrete</span> <span m='1633740'>time</span> <span
  m='1634070'>Fourier</span> <span m='1634550'>transform</span> <span
  m='1636050'>for</span> <span m='1636560'>a</span> <span
  m='1636620'>sequence</span> <span m='1637610'>that's</span> <span
  m='1637820'>obtained</span> <span m='1638840'>by</span> <span
  m='1639680'>periodic</span> <span m='1640310'>sampling.</span> <span
  m='1640970'>That</span> <span m='1641150'>is,</span> <span
  m='1641360'>equally</span> <span m='1641750'>spaced</span> <span
  m='1642080'>sampling</span> <span m='1643040'>of</span> <span
  m='1643190'>the</span> <span m='1643280'>continuous</span> <span
  m='1643850'>time</span> <span m='1644120'>signal.</span> </p><p><span
  m='1645150'>So</span> <span m='1645500'>what</span> <span
  m='1645650'>I'd</span> <span m='1645770'>like</span> <span
  m='1645980'>to</span> <span m='1646100'>do</span> <span m='1646280'>now</span>
  <span m='1646760'>is</span> <span m='1646970'>focus</span> <span
  m='1647420'>on</span> <span m='1647570'>that</span> <span
  m='1647750'>relationship,</span> <span m='1649460'>emphasizing</span> <span
  m='1650210'>again,</span> <span m='1651230'>that</span> <span
  m='1651380'>not</span> <span m='1651650'>all</span> <span
  m='1651890'>sequences</span> <span m='1653030'>arise</span> <span
  m='1653660'>by</span> <span m='1654140'>periodic</span> <span
  m='1654800'>sampling</span> <span m='1655430'>of</span> <span
  m='1655550'>continuous</span> <span m='1656150'>time</span> <span
  m='1656420'>signals.</span> <span m='1657560'>But</span> <span
  m='1658190'>for</span> <span m='1658340'>the</span> <span
  m='1658430'>cases</span> <span m='1658940'>in</span> <span
  m='1659030'>which</span> <span m='1659240'>they</span> <span
  m='1659420'>do,</span> <span m='1660200'>the</span> <span
  m='1660320'>relationship</span> <span m='1661520'>between</span> <span
  m='1662330'>the</span> <span m='1662480'>continuous</span> <span
  m='1663080'>time</span> <span m='1663440'>and</span> <span
  m='1663530'>discrete</span> <span m='1663890'>time</span> <span
  m='1664160'>Fourier</span> <span m='1664550'>transform</span> <span
  m='1665150'>is</span> <span m='1665270'>instructive.</span> <span
  m='1666690'>So</span> <span m='1667220'>let's</span> <span
  m='1669350'>take</span> <span m='1669620'>a</span> <span
  m='1669680'>look</span> <span m='1671360'>at</span> <span
  m='1672950'>the</span> <span m='1673280'>relationship</span> <span
  m='1675170'>between</span> <span m='1677420'>some</span> <span
  m='1678680'>continuous</span> <span m='1679340'>time</span> <span
  m='1679910'>and</span> <span m='1680390'>discrete</span> <span
  m='1680870'>time</span> <span m='1681830'>Fourier</span> <span
  m='1682280'>transforms</span> <span m='1683990'>when</span> <span
  m='1684560'>we</span> <span m='1684770'>obtain</span> <span
  m='1685460'>the</span> <span m='1686240'>discrete</span> <span
  m='1686690'>time</span> <span m='1687200'>signal</span> <span
  m='1687860'>by</span> <span m='1688040'>sampling</span> <span
  m='1688940'>a</span> <span m='1689180'>continuous</span> <span
  m='1689810'>time</span> <span m='1690110'>signal.</span> </p><p><span
  m='1691740'>Well,</span> <span m='1692060'>we</span> <span
  m='1692240'>begin</span> <span m='1692600'>of</span> <span
  m='1692720'>course,</span> <span m='1693440'>with</span> <span
  m='1694310'>a</span> <span m='1694550'>continuous</span> <span
  m='1695240'>time,</span> <span m='1697790'>time</span> <span
  m='1698090'>function</span> <span m='1699320'>which</span> <span
  m='1699620'>I</span> <span m='1699740'>denote</span> <span
  m='1700100'>by</span> <span m='1700290'>x</span> <span m='1700490'>sub</span>
  <span m='1700620'>a</span> <span m='1700910'>of</span> <span
  m='1701030'>t,</span> <span m='1701405'>a</span> <span m='1701780'>sort</span>
  <span m='1702050'>of</span> <span m='1702140'>meaning</span> <span
  m='1702470'>analog.</span> <span m='1704030'>And</span> <span
  m='1705140'>the</span> <span m='1705230'>steps</span> <span
  m='1705680'>that</span> <span m='1705800'>we</span> <span
  m='1705950'>would</span> <span m='1706100'>go</span> <span
  m='1706370'>through</span> <span m='1707030'>to</span> <span
  m='1707180'>convert</span> <span m='1707570'>that</span> <span
  m='1707810'>to</span> <span m='1707960'>a</span> <span
  m='1708020'>sequence</span> <span m='1709760'>are</span> <span
  m='1710240'>first</span> <span m='1710630'>of</span> <span
  m='1710750'>all,</span> <span m='1711590'>to</span> <span
  m='1711710'>go</span> <span m='1711950'>through</span> <span
  m='1712160'>a</span> <span m='1712220'>sampler,</span> <span
  m='1713870'>which</span> <span m='1714110'>I've</span> <span
  m='1714500'>indicated</span> <span m='1715130'>here.</span> <span
  m='1716550'>And</span> <span m='1717110'>the</span> <span
  m='1717320'>output</span> <span m='1717680'>of</span> <span
  m='1717770'>the</span> <span m='1717860'>sampler</span> <span
  m='1718970'>is</span> <span m='1719180'>then</span> <span m='1719670'>a</span>
  <span m='1719740'>sampled</span> <span m='1720710'>continuous</span> <span
  m='1721400'>time</span> <span m='1722510'>version</span> <span
  m='1723410'>of</span> <span m='1724160'>this</span> <span
  m='1724730'>signal.</span> <span m='1726500'>This</span> <span
  m='1726740'>essentially</span> <span m='1727580'>is</span> <span
  m='1728240'>the</span> <span m='1728390'>input</span> <span
  m='1728750'>signal</span> <span m='1729740'>multiplied</span> <span
  m='1730880'>by</span> <span m='1731090'>an</span> <span
  m='1731180'>impulse</span> <span m='1731630'>train.</span> </p><p><span
  m='1733810'>So</span> <span m='1734170'>I've</span> <span
  m='1734350'>indicated</span> <span m='1734860'>that</span> <span
  m='1735070'>here,</span> <span m='1736040'>here's</span> <span
  m='1736540'>the</span> <span m='1737200'>continuous</span> <span
  m='1737740'>time</span> <span m='1738070'>input.</span> <span
  m='1738970'>Here</span> <span m='1739330'>is</span> <span
  m='1739630'>the</span> <span m='1739870'>continuous</span> <span
  m='1740740'>time</span> <span m='1742240'>output</span> <span
  m='1742630'>of</span> <span m='1742750'>the</span> <span
  m='1742840'>sampler,</span> <span m='1743980'>which</span> <span
  m='1744280'>is</span> <span m='1744430'>an</span> <span
  m='1744520'>impulse</span> <span m='1745030'>train</span> <span
  m='1746050'>with</span> <span m='1746260'>the</span> <span
  m='1746410'>envelope</span> <span m='1747160'>of</span> <span
  m='1747340'>the</span> <span m='1747460'>impulse</span> <span
  m='1747940'>train</span> <span m='1749020'>being</span> <span
  m='1749830'>the</span> <span m='1750160'>continuous</span> <span
  m='1750760'>time</span> <span m='1751030'>function</span> <span
  m='1751300'>x</span> <span m='1751570'>sub</span> <span m='1751855'>a</span>
  <span m='1752140'>of</span> <span m='1752260'>t.</span> <span
  m='1754430'>All</span> <span m='1754530'>right,</span> <span
  m='1754600'>well</span> <span m='1755080'>this</span> <span
  m='1755350'>isn't</span> <span m='1755570'>the</span> <span
  m='1755680'>sequence.</span> <span m='1756460'>This</span> <span
  m='1756700'>is</span> <span m='1756820'>just</span> <span
  m='1757000'>simply</span> <span m='1757420'>an</span> <span
  m='1757510'>impulse</span> <span m='1757960'>train.</span> <span
  m='1759430'>To</span> <span m='1759610'>turn</span> <span
  m='1759940'>this</span> <span m='1760150'>into</span> <span
  m='1760420'>a</span> <span m='1760480'>sequence</span> <span
  m='1761260'>we</span> <span m='1761440'>need</span> <span
  m='1761980'>to</span> <span m='1762100'>go</span> <span
  m='1762460'>into</span> <span m='1762820'>a</span> <span
  m='1762910'>box,</span> <span m='1763870'>which</span> <span
  m='1764470'>I've</span> <span m='1764770'>labeled</span> <span
  m='1766350'>c</span> <span m='1766720'>slash</span> <span
  m='1766975'>d,</span> <span m='1767590'>meaning</span> <span
  m='1767980'>continuous</span> <span m='1768610'>time</span> <span
  m='1769090'>to</span> <span m='1769420'>discrete</span> <span
  m='1769870'>time</span> <span m='1770470'>converter.</span> <span
  m='1772180'>And</span> <span m='1772540'>the</span> <span
  m='1772660'>output</span> <span m='1773140'>then</span> <span
  m='1773740'>is</span> <span m='1774490'>a</span> <span
  m='1774550'>sequence</span> <span m='1775600'>x</span> <span m='1775890'>of
  n.</span> <span m='1777250'>The</span> <span m='1777340'>sequence</span> <span
  m='1777850'>values</span> <span m='1778780'>being</span> <span
  m='1779320'>samples</span> <span m='1780250'>of</span> <span
  m='1780580'>x</span> <span m='1780830'>sub a</span> <span
  m='1781180'>of</span> <span m='1781330'>t</span> <span m='1782290'>at</span>
  <span m='1783040'>the</span> <span m='1783130'>sampling</span> <span
  m='1784660'>instances</span> <span m='1785530'>n</span> <span
  m='1785830'>times</span> <span m='1786190'>capital</span> <span
  m='1786640'>T.</span> <span m='1787090'>In</span> <span
  m='1787210'>other</span> <span m='1787420'>words,</span> <span
  m='1788360'>it's</span> <span m='1788440'>converting</span> <span
  m='1790180'>the</span> <span m='1790360'>areas</span> <span
  m='1790840'>of</span> <span m='1790930'>these</span> <span
  m='1791170'>impulses</span> <span m='1792430'>into</span> <span
  m='1793090'>sequence</span> <span m='1793630'>values.</span> </p><p><span
  m='1795500'>Now</span> <span m='1796210'>I've</span> <span
  m='1796690'>illustrated</span> <span m='1797350'>it</span> <span
  m='1797470'>here</span> <span m='1798340'>for</span> <span
  m='1798490'>one</span> <span m='1799120'>choice</span> <span
  m='1800200'>for</span> <span m='1800890'>the</span> <span
  m='1801010'>sampling</span> <span m='1801520'>interval</span> <span
  m='1802120'>capital</span> <span m='1802460'>T.</span> <span
  m='1804610'>Let's,</span> <span m='1805180'>down</span> <span
  m='1805540'>here,</span> <span m='1806140'>illustrate</span> <span
  m='1806545'>it</span> <span m='1806950'>for</span> <span m='1807325'>a</span>
  <span m='1807700'>sampling</span> <span m='1808180'>interval</span> <span
  m='1808570'>that's</span> <span m='1808780'>twice</span> <span
  m='1809110'>as</span> <span m='1809260'>long.</span> <span
  m='1810250'>Well,</span> <span m='1810850'>of</span> <span
  m='1810940'>course</span> <span m='1811240'>we</span> <span
  m='1811360'>have</span> <span m='1811570'>the</span> <span
  m='1811660'>same</span> <span m='1812200'>continuous</span> <span
  m='1812890'>time</span> <span m='1813220'>input.</span> <span
  m='1814840'>The</span> <span m='1815320'>sampled</span> <span
  m='1815920'>output,</span> <span m='1816275'>x</span> <span
  m='1816630'>sub</span> <span m='1816960'>a,</span> <span
  m='1817720'>tilde</span> <span m='1818410'>of</span> <span
  m='1818560'>t,</span> <span m='1819610'>has</span> <span
  m='1820210'>the</span> <span m='1820330'>same</span> <span
  m='1820690'>envelope,</span> <span m='1821830'>but</span> <span
  m='1822550'>the</span> <span m='1822670'>spacing</span> <span
  m='1823150'>of</span> <span m='1823270'>the</span> <span
  m='1823390'>impulses</span> <span m='1824410'>is</span> <span
  m='1825160'>twice</span> <span m='1825790'>what</span> <span
  m='1826000'>it</span> <span m='1826090'>is</span> <span
  m='1826780'>here,</span> <span m='1827770'>and</span> <span
  m='1827980'>that</span> <span m='1828160'>I've</span> <span
  m='1828340'>indicated.</span> <span m='1828970'>The</span> <span
  m='1829120'>envelope,</span> <span m='1829630'>of</span> <span
  m='1829720'>course,</span> <span m='1830050'>is</span> <span
  m='1830200'>the</span> <span m='1830320'>same.</span> <span
  m='1832150'>But</span> <span m='1832380'>at</span> <span
  m='1832480'>the</span> <span m='1832660'>output</span> <span
  m='1833320'>of</span> <span m='1833590'>the</span> <span
  m='1833710'>continuous</span> <span m='1834340'>time</span> <span
  m='1834690'>to</span> <span m='1834790'>discrete</span> <span
  m='1835210'>time</span> <span m='1835570'>converter,</span> <span
  m='1836880'>what</span> <span m='1837010'>do</span> <span
  m='1837070'>we</span> <span m='1837250'>have?</span> </p><p><span
  m='1838190'>Well,</span> <span m='1839110'>we</span> <span
  m='1839290'>have</span> <span m='1840280'>the</span> <span
  m='1840490'>areas</span> <span m='1841150'>of</span> <span
  m='1841330'>these</span> <span m='1841570'>impulses</span> <span
  m='1842890'>lined</span> <span m='1843430'>up</span> <span
  m='1843970'>along</span> <span m='1844720'>this</span> <span
  m='1844990'>axis,</span> <span m='1846220'>again,</span> <span
  m='1846760'>at</span> <span m='1847000'>integer</span> <span
  m='1847450'>values</span> <span m='1848200'>of</span> <span
  m='1848400'>n.</span> <span m='1850090'>That</span> <span
  m='1850300'>is,</span> <span m='1850780'>the</span> <span
  m='1850900'>spacing</span> <span m='1851830'>of</span> <span
  m='1852520'>the</span> <span m='1852640'>lines,</span> <span
  m='1854020'>when</span> <span m='1854200'>we</span> <span
  m='1854290'>look</span> <span m='1854530'>at</span> <span
  m='1854620'>the</span> <span m='1854710'>sequence</span> <span
  m='1855430'>here,</span> <span m='1856210'>must</span> <span
  m='1856510'>be</span> <span m='1856870'>exactly</span> <span
  m='1857440'>the</span> <span m='1857530'>same</span> <span
  m='1857860'>as</span> <span m='1857950'>the</span> <span
  m='1858070'>spacing</span> <span m='1858580'>of</span> <span
  m='1858700'>the</span> <span m='1858790'>lines</span> <span
  m='1859210'>here,</span> <span m='1860290'>it's</span> <span
  m='1860440'>just</span> <span m='1860650'>that</span> <span
  m='1860800'>the</span> <span m='1860890'>values</span> <span
  m='1861400'>are</span> <span m='1861490'>different</span> <span
  m='1861910'>because</span> <span m='1862780'>we</span> <span
  m='1862910'>picked</span> <span m='1863260'>out</span> <span
  m='1863650'>samples</span> <span m='1864430'>at</span> <span
  m='1864580'>different</span> <span m='1864880'>instance.</span> <span
  m='1866150'>So</span> <span m='1866500'>in</span> <span
  m='1866620'>fact,</span> <span m='1867050'>the</span> <span
  m='1867130'>envelope</span> <span m='1867760'>here</span> <span
  m='1869350'>is</span> <span m='1870340'>indeed</span> <span
  m='1871420'>a</span> <span m='1871480'>compressed</span> <span
  m='1872020'>version</span> <span m='1872800'>of</span> <span
  m='1873250'>the</span> <span m='1873400'>envelope</span> <span
  m='1873880'>that</span> <span m='1874000'>we</span> <span
  m='1874150'>had</span> <span m='1874390'>here.</span> <span
  m='1875560'>Very</span> <span m='1875830'>important</span> <span
  m='1876250'>point.</span> </p><p><span m='1877670'>The</span> <span
  m='1877690'>point</span> <span m='1878080'>being</span> <span
  m='1878770'>that</span> <span m='1879730'>no</span> <span
  m='1879880'>matter</span> <span m='1880240'>what</span> <span
  m='1880540'>the</span> <span m='1880660'>sampling</span> <span
  m='1881200'>rate</span> <span m='1881500'>is</span> <span
  m='1882760'>the</span> <span m='1882850'>sequence</span> <span
  m='1883420'>values,</span> <span m='1884200'>when</span> <span
  m='1884440'>we</span> <span m='1884560'>line</span> <span
  m='1884950'>them</span> <span m='1885070'>up</span> <span
  m='1885250'>as</span> <span m='1885370'>a</span> <span
  m='1885430'>sequence,</span> <span m='1886600'>are</span> <span
  m='1886750'>going</span> <span m='1886990'>to</span> <span
  m='1887140'>fall</span> <span m='1887710'>at</span> <span
  m='1887980'>integer</span> <span m='1888400'>values</span> <span
  m='1889690'>along</span> <span m='1890590'>this</span> <span
  m='1891220'>argument,</span> <span m='1891760'>n,</span> <span
  m='1893020'>always</span> <span m='1893620'>at</span> <span
  m='1893950'>intervals</span> <span m='1894550'>that</span> <span
  m='1894670'>correspond</span> <span m='1895330'>to</span> <span
  m='1895480'>1.</span> <span m='1896450'>Whereas</span> <span
  m='1897490'>the</span> <span m='1897640'>output</span> <span
  m='1898000'>of</span> <span m='1898120'>the</span> <span
  m='1898350'>sampler</span> <span m='1899320'>had</span> <span
  m='1899560'>impulses</span> <span m='1900430'>occurring</span> <span
  m='1901090'>at</span> <span m='1901240'>a</span> <span
  m='1901300'>spacing</span> <span m='1901990'>of</span> <span
  m='1902170'>capital</span> <span m='1902680'>T,</span> <span
  m='1903520'>which</span> <span m='1903700'>in</span> <span
  m='1903820'>this</span> <span m='1904000'>case,</span> <span
  m='1904510'>was</span> <span m='1904690'>capital</span> <span
  m='1905030'>T</span> <span m='1905370'>1,</span> <span m='1906020'>and</span>
  <span m='1906040'>in</span> <span m='1906130'>this</span> <span
  m='1906310'>case</span> <span m='1906610'>is</span> <span
  m='1906700'>capital</span> <span m='1906970'>T</span> <span
  m='1907240'>2.</span> </p><p><span m='1909520'>All</span> <span
  m='1909610'>right</span> <span m='1909830'>well,</span> <span
  m='1910300'>this</span> <span m='1910600'>is</span> <span
  m='1910780'>essentially</span> <span m='1911380'>the</span> <span
  m='1911500'>sampling</span> <span m='1912370'>process</span> <span
  m='1913090'>plus</span> <span m='1913480'>the</span> <span
  m='1913600'>conversion</span> <span m='1914800'>to</span> <span
  m='1914950'>a</span> <span m='1915010'>discrete</span> <span
  m='1915460'>time</span> <span m='1916090'>signal.</span> <span
  m='1917540'>And</span> <span m='1918100'>now</span> <span
  m='1918670'>let's</span> <span m='1918940'>take</span> <span
  m='1919210'>a</span> <span m='1919270'>look</span> <span m='1919510'>at</span>
  <span m='1919600'>what</span> <span m='1919810'>this</span> <span
  m='1920050'>means</span> <span m='1921220'>in</span> <span
  m='1921370'>terms</span> <span m='1922030'>of</span> <span
  m='1922960'>the</span> <span m='1923110'>Fourier</span> <span
  m='1923560'>transform</span> <span m='1925090'>of</span> <span
  m='1925720'>the</span> <span m='1926320'>discrete</span> <span
  m='1926740'>time</span> <span m='1927430'>signal</span> <span
  m='1928510'>as</span> <span m='1928690'>compared</span> <span
  m='1929410'>with</span> <span m='1929740'>the</span> <span
  m='1929860'>Fourier</span> <span m='1930310'>transform</span> <span
  m='1931210'>of</span> <span m='1931870'>the</span> <span
  m='1931960'>continuous</span> <span m='1932560'>time</span> <span
  m='1932890'>signal.</span> <span m='1935090'>Let's</span> <span
  m='1935200'>do</span> <span m='1935380'>this</span> <span
  m='1935590'>in</span> <span m='1935680'>two</span> <span
  m='1935890'>steps.</span> </p><p><span m='1937820'>First</span> <span
  m='1938050'>of</span> <span m='1938200'>all,</span> <span
  m='1939260'>we</span> <span m='1939310'>have</span> <span
  m='1939520'>the</span> <span m='1939640'>sampler.</span> <span
  m='1940820'>Here</span> <span m='1941100'>is</span> <span
  m='1941350'>the</span> <span m='1941470'>input</span> <span
  m='1941740'>x</span> <span m='1942010'>sub</span> <span m='1942320'>a</span>
  <span m='1942580'>of</span> <span m='1942730'>t,</span> <span
  m='1943660'>continuous</span> <span m='1944200'>time</span> <span
  m='1944530'>function.</span> <span m='1945650'>Here is</span> <span
  m='1945820'>the</span> <span m='1945970'>output,</span> <span
  m='1946440'>x</span> <span m='1946630'>sub</span> <span m='1946690'>a</span>
  <span m='1946960'>tilde</span> <span m='1947350'>of</span> <span
  m='1947590'>t,</span> <span m='1948025'>a</span> <span
  m='1948460'>continuous</span> <span m='1949090'>time</span> <span
  m='1949390'>function.</span> <span m='1950800'>And</span> <span
  m='1951820'>the</span> <span m='1951970'>output</span> <span
  m='1952330'>of</span> <span m='1952420'>the</span> <span
  m='1952540'>sampler</span> <span m='1953680'>is</span> <span
  m='1954010'>the</span> <span m='1954160'>input</span> <span
  m='1954520'>to</span> <span m='1954640'>the</span> <span
  m='1954730'>sampler,</span> <span m='1955630'>multiplied</span> <span
  m='1956890'>by</span> <span m='1957640'>an</span> <span
  m='1957760'>impulse</span> <span m='1958240'>train.</span> <span
  m='1960220'>Or</span> <span m='1960850'>equivalently,</span> <span
  m='1962260'>it's</span> <span m='1962650'>an</span> <span
  m='1962800'>impulse</span> <span m='1963310'>train</span> <span
  m='1964990'>with</span> <span m='1965140'>the</span> <span
  m='1965320'>areas</span> <span m='1965770'>of</span> <span
  m='1965860'>the</span> <span m='1966010'>impulses</span> <span
  m='1967240'>given</span> <span m='1967660'>by</span> <span
  m='1968320'>the</span> <span m='1968440'>values</span> <span
  m='1969130'>of</span> <span m='1969250'>x</span> <span m='1969550'>sub
  a</span> <span m='1969780'>of</span> <span m='1969910'>t</span> <span
  m='1971020'>at</span> <span m='1971260'>the</span> <span
  m='1971380'>times</span> <span m='1972190'>that</span> <span
  m='1972610'>the</span> <span m='1972790'>impulses</span> <span
  m='1973330'>occur.</span> <span m='1974560'>Naught,</span> <span
  m='1974860'>by</span> <span m='1975070'>the</span> <span
  m='1975190'>way,</span> <span m='1975370'>is</span> <span
  m='1975520'>what</span> <span m='1975670'>I'm</span> <span
  m='1975760'>using</span> <span m='1976390'>as</span> <span
  m='1976570'>the</span> <span m='1976660'>notation</span> <span
  m='1977230'>to</span> <span m='1977350'>designate</span> <span
  m='1978190'>a</span> <span m='1978850'>unit</span> <span
  m='1979180'>impulse,</span> <span m='1979990'>unit</span> <span
  m='1980260'>continuous</span> <span m='1980860'>time</span> <span
  m='1981160'>impulse.</span> </p><p><span m='1982640'>Now</span> <span
  m='1983080'>in</span> <span m='1983170'>the</span> <span
  m='1983310'>Fourier</span> <span m='1983650'>transformed</span> <span
  m='1984370'>domain</span> <span m='1984850'>then,</span> <span
  m='1985810'>the</span> <span m='1985930'>continuous</span> <span
  m='1986620'>time</span> <span m='1986920'>Fourier</span> <span
  m='1987340'>transform,</span> <span m='1989500'>is</span> <span
  m='1990310'>the</span> <span m='1990430'>convolution</span> <span
  m='1992080'>of</span> <span m='1992890'>the</span> <span
  m='1993100'>continuous</span> <span m='1993700'>time</span> <span
  m='1993970'>Fourier</span> <span m='1994360'>transform</span> <span
  m='1995380'>of</span> <span m='1995770'>x</span> <span m='1996070'>sub
  a</span> <span m='1996370'>of</span> <span m='1996520'>t,</span> <span
  m='1997720'>convolved</span> <span m='1998440'>with</span> <span
  m='1999070'>the</span> <span m='1999290'>Fourier</span> <span
  m='1999610'>transform</span> <span m='2000390'>of</span> <span
  m='2000540'>the</span> <span m='2000690'>impulse</span> <span
  m='2001140'>train,</span> <span m='2001770'>which</span> <span
  m='2002040'>is</span> <span m='2002250'>an</span> <span
  m='2002370'>impulse</span> <span m='2002820'>train</span> <span
  m='2003420'>in</span> <span m='2003780'>the</span> <span
  m='2003900'>frequency</span> <span m='2004440'>domain.</span> <span
  m='2005370'>That's</span> <span m='2005550'>a</span> <span
  m='2005610'>result</span> <span m='2006000'>that</span> <span
  m='2006150'>you</span> <span m='2006240'>should</span> <span
  m='2006450'>be</span> <span m='2006600'>familiar</span> <span
  m='2007050'>with</span> <span m='2008310'>for</span> <span
  m='2008520'>continuous</span> <span m='2009090'>time</span> <span
  m='2009600'>signals.</span> <span m='2010830'>Or</span> <span
  m='2011040'>equivalently,</span> <span m='2012030'>it's</span> <span
  m='2012240'>given</span> <span m='2012570'>by</span> <span
  m='2012750'>1</span> <span m='2012990'>over</span> <span m='2013280'>t,</span>
  <span m='2014250'>times</span> <span m='2014550'>the</span> <span
  m='2014670'>sum</span> <span m='2015240'>of</span> <span m='2015360'>x</span>
  <span m='2015660'>sub a</span> <span m='2016170'>of</span> <span
  m='2016320'>j</span> <span m='2016650'>omega,</span> <span
  m='2017160'>plus</span> <span m='2017490'>j</span> <span m='2017850'>2</span>
  <span m='2018060'>pi</span> <span m='2018420'>r</span> <span
  m='2018840'>over</span> <span m='2019140'>capital</span> <span
  m='2019620'>T.</span> <span m='2020400'>Basically,</span> <span
  m='2020970'>what</span> <span m='2021090'>that</span> <span
  m='2021300'>means</span> <span m='2022650'>is</span> <span
  m='2022830'>that</span> <span m='2023010'>the</span> <span
  m='2023130'>Fourier</span> <span m='2023580'>transform</span> <span
  m='2024960'>of</span> <span m='2025110'>this</span> <span
  m='2025380'>continuous</span> <span m='2026010'>time</span> <span
  m='2026310'>signal</span> <span m='2028430'>is</span> <span
  m='2028580'>equal</span> <span m='2028910'>to</span> <span
  m='2029030'>the</span> <span m='2029150'>Fourier</span> <span
  m='2029510'>transform</span> <span m='2030590'>of</span> <span
  m='2030710'>this</span> <span m='2030890'>continuous</span> <span
  m='2031460'>time</span> <span m='2031760'>signal,</span> <span
  m='2033020'>but</span> <span m='2033350'>repeated</span> <span
  m='2034160'>over</span> <span m='2034550'>and</span> <span
  m='2034640'>over</span> <span m='2035000'>again</span> <span
  m='2035810'>in</span> <span m='2035930'>frequency</span> <span
  m='2037310'>at</span> <span m='2037490'>intervals</span> <span
  m='2038180'>of</span> <span m='2038330'>2</span> <span m='2038510'>pi</span>
  <span m='2038990'>over</span> <span m='2039260'>capital</span> <span
  m='2039585'>T.</span> <span m='2040610'>So</span> <span
  m='2041540'>this</span> <span m='2041840'>is</span> <span
  m='2042140'>sort</span> <span m='2042710'>of</span> <span m='2042830'>a</span>
  <span m='2042890'>standard</span> <span m='2043820'>sampling</span> <span
  m='2044420'>theorem</span> <span m='2044840'>kind</span> <span
  m='2045140'>of</span> <span m='2045560'>result</span> <span
  m='2046100'>in</span> <span m='2046220'>the</span> <span
  m='2046310'>continuous</span> <span m='2046880'>time</span> <span
  m='2047180'>case,</span> <span m='2048040'>and</span> <span
  m='2048139'>a</span> <span m='2048199'>result</span> <span
  m='2048650'>that</span> <span m='2048770'>you</span> <span
  m='2048889'>should</span> <span m='2049100'>be</span> <span
  m='2049219'>more</span> <span m='2049460'>or</span> <span
  m='2049520'>less</span> <span m='2049730'>familiar</span> <span
  m='2050210'>with.</span> <span m='2051770'>Let's</span> <span
  m='2052280'>look</span> <span m='2052580'>at</span> <span
  m='2052670'>this</span> <span m='2052909'>now</span> <span
  m='2053659'>from</span> <span m='2054830'>a</span> <span
  m='2055280'>different</span> <span m='2056239'>point</span> <span
  m='2056510'>of</span> <span m='2056570'>view.</span> <span
  m='2056929'>Again</span> <span m='2057290'>looking</span> <span
  m='2057679'>at</span> <span m='2058010'>x</span> <span m='2058409'>sub
  a</span> <span m='2059199'>tilde</span> <span m='2059639'>of</span> <span
  m='2059810'>j</span> <span m='2060080'>omega.</span> </p><p><span
  m='2061310'>Well</span> <span m='2061760'>x sub</span> <span
  m='2062074'>a</span> <span m='2062389'>tilde</span> <span
  m='2062880'>of</span> <span m='2063080'>j</span> <span
  m='2063320'>omega</span> <span m='2064639'>is</span> <span
  m='2064820'>the</span> <span m='2064969'>integral</span> <span
  m='2065600'>of</span> <span m='2065750'>x sub a</span> <span
  m='2066010'>tilde</span> <span m='2066830'>of</span> <span
  m='2067070'>t,</span> <span m='2067560'>e</span> <span m='2067825'>to
  the</span> <span m='2068090'>minus</span> <span m='2068510'>j</span> <span
  m='2068870'>omega</span> <span m='2069320'>t</span> <span m='2069770'>d</span>
  <span m='2070226'>t.</span> <span m='2072050'>Substitute</span> <span
  m='2072425'>in</span> <span m='2072800'>for</span> <span m='2073159'>x</span>
  <span m='2073429'>sub</span> <span m='2073650'>a</span> <span
  m='2073920'>tilde</span> <span m='2074330'>of</span> <span
  m='2074540'>t,</span> <span m='2075889'>the</span> <span
  m='2076010'>relationship</span> <span m='2076909'>in</span> <span
  m='2077090'>terms</span> <span m='2077659'>of</span> <span
  m='2077870'>an</span> <span m='2077929'>impulse</span> <span
  m='2078440'>train,</span> <span m='2078949'>and</span> <span
  m='2079159'>interchange</span> <span m='2079790'>summation</span> <span
  m='2080469'>and</span> <span m='2080630'>integration,</span> <span
  m='2082010'>and</span> <span m='2082400'>I</span> <span
  m='2082520'>think</span> <span m='2083000'>you</span> <span
  m='2083179'>could</span> <span m='2083330'>verify</span> <span
  m='2084290'>in</span> <span m='2084469'>a</span> <span m='2084530'>very</span>
  <span m='2084739'>straightforward</span> <span m='2085550'>way</span> <span
  m='2086659'>that</span> <span m='2087290'>what</span> <span
  m='2087560'>you</span> <span m='2087710'>end</span> <span
  m='2087920'>up</span> <span m='2088130'>with</span> <span
  m='2088610'>is</span> <span m='2088790'>an</span> <span
  m='2088880'>expression</span> <span m='2090125'>for</span> <span
  m='2090860'>the</span> <span m='2091340'>Fourier</span> <span
  m='2091820'>transform</span> <span m='2092870'>at</span> <span
  m='2092960'>the</span> <span m='2093139'>output</span> <span
  m='2093469'>of</span> <span m='2093560'>the</span> <span
  m='2093650'>sampler</span> <span m='2095600'>as</span> <span
  m='2095780'>given</span> <span m='2096139'>by</span> <span
  m='2097210'>the</span> <span m='2097310'>sampling</span> <span
  m='2097910'>values</span> <span m='2099140'>times</span> <span
  m='2099590'>e</span> <span m='2099890'>to</span> <span m='2099980'>the</span>
  <span m='2100070'>minus</span> <span m='2100490'>j</span> <span
  m='2100880'>n</span> <span m='2101270'>capital</span> <span
  m='2101720'>omega</span> <span m='2102140'>T.</span> <span
  m='2102740'>Capital</span> <span m='2103160'>omega</span> <span
  m='2103670'>is</span> <span m='2104150'>a</span> <span
  m='2104300'>continuous</span> <span m='2104930'>frequency</span> <span
  m='2105470'>variable.</span> </p><p><span m='2107490'>Now</span> <span
  m='2107760'>we</span> <span m='2107910'>want</span> <span
  m='2108060'>to</span> <span m='2108150'>look</span> <span
  m='2108510'>at</span> <span m='2109290'>the</span> <span
  m='2109410'>relationship</span> <span m='2110580'>between</span> <span
  m='2111660'>the</span> <span m='2111750'>Fourier</span> <span
  m='2112200'>transform,</span> <span m='2113100'>continuous</span> <span
  m='2113730'>time</span> <span m='2114270'>of</span> <span m='2114390'>x</span>
  <span m='2114580'>sub a</span> <span m='2114930'>of</span> <span
  m='2115050'>t</span> <span m='2115890'>and</span> <span m='2116010'>the</span>
  <span m='2116100'>discrete</span> <span m='2116550'>time</span> <span
  m='2116850'>Fourier</span> <span m='2117270'>transform</span> <span
  m='2118200'>of</span> <span m='2118350'>x</span> <span m='2118590'>of</span>
  <span m='2118690'>n.</span> <span m='2120150'>So</span> <span
  m='2120390'>we</span> <span m='2120540'>have</span> <span
  m='2120750'>the</span> <span m='2120840'>next</span> <span
  m='2121110'>step,</span> <span m='2122440'>which</span> <span
  m='2122760'>is</span> <span m='2123420'>to</span> <span m='2123540'>put</span>
  <span m='2124110'>this</span> <span m='2124830'>impulse</span> <span
  m='2125400'>train</span> <span m='2126390'>into</span> <span
  m='2126660'>the</span> <span m='2126780'>continuous</span> <span
  m='2127290'>to</span> <span m='2127500'>discrete</span> <span
  m='2127920'>time</span> <span m='2128280'>converter.</span> <span
  m='2130240'>And</span> <span m='2130450'>I</span> <span
  m='2130540'>remind</span> <span m='2131020'>you</span> <span
  m='2131140'>that</span> <span m='2131260'>we</span> <span
  m='2131410'>just</span> <span m='2131700'>developed</span> <span
  m='2132160'>two</span> <span m='2132370'>results.</span> <span
  m='2133510'>One</span> <span m='2133750'>result</span> <span
  m='2134320'>was</span> <span m='2134620'>that</span> <span m='2134770'>x
  sub</span> <span m='2135050'>a</span> <span m='2135330'>tilde</span> <span
  m='2135780'>of j</span> <span m='2136060'>omega</span> <span
  m='2137020'>was</span> <span m='2137170'>given</span> <span
  m='2137470'>by</span> <span m='2137650'>this</span> <span
  m='2137890'>expression.</span> <span m='2139450'>Also</span> <span
  m='2139960'>we</span> <span m='2140110'>developed</span> <span
  m='2140860'>that</span> <span m='2141190'>it</span> <span
  m='2141310'>was</span> <span m='2141490'>given</span> <span
  m='2141790'>by</span> <span m='2141940'>this</span> <span
  m='2142150'>expression.</span> </p><p><span m='2144410'>Well</span> <span
  m='2144640'>what's</span> <span m='2145330'>the</span> <span
  m='2145450'>Fourier</span> <span m='2145900'>transform</span> <span
  m='2146800'>of</span> <span m='2146980'>the</span> <span
  m='2147100'>output</span> <span m='2148060'>of</span> <span
  m='2148180'>the</span> <span m='2148300'>continuous</span> <span
  m='2148900'>to</span> <span m='2149020'>discrete</span> <span
  m='2149440'>time</span> <span m='2149710'>converter?</span> <span
  m='2150820'>Well,</span> <span m='2151900'>it's</span> <span
  m='2152050'>just</span> <span m='2152260'>simply</span> <span
  m='2153400'>x</span> <span m='2153665'>of</span> <span m='2153930'>e</span>
  <span m='2154170'>to</span> <span m='2154360'>the</span> <span
  m='2154450'>j</span> <span m='2154750'>omega,</span> <span
  m='2155850'>our</span> <span m='2156010'>discrete</span> <span
  m='2156400'>time</span> <span m='2156700'>Fourier</span> <span
  m='2157180'>transform,</span> <span m='2159380'>which</span> <span
  m='2159520'>is</span> <span m='2159670'>equal</span> <span
  m='2160120'>to</span> <span m='2161020'>the</span> <span
  m='2161140'>sum</span> <span m='2162160'>on</span> <span m='2162400'>n</span>
  <span m='2164020'>of</span> <span m='2164380'>x</span> <span
  m='2164740'>of</span> <span m='2164870'>n.</span> <span m='2165880'>But</span>
  <span m='2166090'>x</span> <span m='2166420'>of</span> <span
  m='2166540'>n</span> <span m='2167050'>is</span> <span m='2167360'>x sub
  a</span> <span m='2167830'>of</span> <span m='2167950'>n</span> <span
  m='2168310'>capital</span> <span m='2168820'>T.</span> <span
  m='2169630'>So</span> <span m='2170230'>we</span> <span
  m='2170410'>have</span> <span m='2170620'>x</span> <span
  m='2171010'>sub</span> <span m='2171390'>a</span> <span m='2171770'>of</span>
  <span m='2172150'>n</span> <span m='2172850'>capital</span> <span
  m='2173325'>T,</span> <span m='2174550'>times</span> <span
  m='2175540'>e</span> <span m='2175810'>to</span> <span m='2175930'>the</span>
  <span m='2176020'>minus</span> <span m='2176470'>j</span> <span
  m='2176920'>omega</span> <span m='2178160'>n.</span> </p><p><span
  m='2180850'>Well</span> <span m='2181150'>let's</span> <span
  m='2181390'>compare</span> <span m='2182170'>this</span> <span
  m='2183010'>with</span> <span m='2183220'>this.</span> <span
  m='2184810'>We</span> <span m='2184930'>see</span> <span
  m='2185170'>that</span> <span m='2185320'>they're</span> <span
  m='2185620'>exactly</span> <span m='2186190'>the</span> <span
  m='2186310'>same</span> <span m='2187300'>except</span> <span
  m='2187930'>that</span> <span m='2188440'>for</span> <span
  m='2188710'>omega,</span> <span m='2189520'>little</span> <span
  m='2189820'>omega</span> <span m='2190270'>here</span> <span
  m='2191290'>we</span> <span m='2191470'>have</span> <span
  m='2192040'>capital</span> <span m='2192490'>omega</span> <span
  m='2192940'>times</span> <span m='2193270'>capital</span> <span
  m='2193645'>T</span> <span m='2194020'>there.</span> <span
  m='2195700'>Consequently,</span> <span m='2196540'>we</span> <span
  m='2196690'>can</span> <span m='2196870'>say</span> <span
  m='2197950'>that</span> <span m='2198640'>the</span> <span
  m='2198880'>discrete</span> <span m='2199320'>time</span> <span
  m='2199630'>Fourier</span> <span m='2200080'>transform</span> <span
  m='2201730'>is</span> <span m='2201910'>equal</span> <span
  m='2202420'>to</span> <span m='2203320'>the</span> <span
  m='2203440'>Fourier</span> <span m='2203920'>transform</span> <span
  m='2204760'>of</span> <span m='2204940'>the</span> <span
  m='2205090'>impulse</span> <span m='2205570'>train,</span> <span
  m='2206710'>the</span> <span m='2206800'>continuous</span> <span
  m='2207340'>time</span> <span m='2207550'>Fourier</span> <span
  m='2207910'>transform</span> <span m='2208450'>of</span> <span
  m='2208510'>the</span> <span m='2208630'>impulse</span> <span
  m='2209080'>train,</span> <span m='2210190'>with</span> <span
  m='2210580'>omega</span> <span m='2211300'>times</span> <span
  m='2211670'>capital</span> <span m='2212130'>T</span> <span
  m='2212590'>equal</span> <span m='2212950'>to</span> <span
  m='2213070'>little</span> <span m='2213310'>omega.</span> </p><p><span
  m='2216380'>And</span> <span m='2217490'>we</span> <span
  m='2217670'>had</span> <span m='2217910'>another</span> <span
  m='2218300'>expression</span> <span m='2219230'>for</span> <span
  m='2219980'>the</span> <span m='2220190'>Fourier</span> <span
  m='2220670'>transform</span> <span m='2221540'>of</span> <span
  m='2221690'>the</span> <span m='2221840'>impulse</span> <span
  m='2222290'>train,</span> <span m='2223430'>which</span> <span
  m='2223640'>we</span> <span m='2223780'>derived</span> <span
  m='2224270'>here.</span> <span m='2225380'>Consequently,</span> <span
  m='2226370'>the</span> <span m='2226490'>final</span> <span
  m='2226880'>result</span> <span m='2227270'>that</span> <span
  m='2227390'>we</span> <span m='2227570'>end</span> <span m='2227780'>up</span>
  <span m='2227990'>with</span> <span m='2228770'>is</span> <span
  m='2229010'>that</span> <span m='2229820'>the</span> <span
  m='2229910'>Fourier</span> <span m='2230390'>transform</span> <span
  m='2231260'>of</span> <span m='2231440'>the</span> <span
  m='2231530'>discrete</span> <span m='2232070'>time</span> <span
  m='2233510'>sequence</span> <span m='2234980'>is</span> <span
  m='2235190'>equal</span> <span m='2235520'>to</span> <span
  m='2235700'>1</span> <span m='2235910'>over</span> <span m='2236140'>t</span>
  <span m='2236930'>times</span> <span m='2237230'>the</span> <span
  m='2237320'>sum</span> <span m='2237860'>of</span> <span m='2238080'>x</span>
  <span m='2238400'>sub a</span> <span m='2239480'>of</span> <span
  m='2239690'>j</span> <span m='2240260'>omega,</span> <span
  m='2241490'>plus</span> <span m='2241820'>j</span> <span m='2242420'>2</span>
  <span m='2242630'>pi</span> <span m='2242990'>r</span> <span
  m='2243290'>over</span> <span m='2243740'>capital</span> <span
  m='2244220'>T,</span> <span m='2245120'>with</span> <span
  m='2245570'>omega</span> <span m='2247670'>replaced</span> <span
  m='2248360'>by</span> <span m='2249560'>little</span> <span
  m='2249890'>omega,</span> <span m='2250880'>divided</span> <span
  m='2251360'>by</span> <span m='2251600'>capital</span> <span
  m='2252110'>T.</span> <span m='2253190'>In</span> <span
  m='2253280'>other</span> <span m='2253490'>words,</span> <span
  m='2254550'>we</span> <span m='2254600'>had</span> <span
  m='2254810'>the</span> <span m='2254900'>expression</span> <span
  m='2255500'>that</span> <span m='2255620'>capital</span> <span
  m='2256100'>omega</span> <span m='2256940'>times</span> <span
  m='2257330'>capital</span> <span m='2257720'>T</span> <span
  m='2258110'>is</span> <span m='2258500'>equal</span> <span
  m='2258830'>to</span> <span m='2258950'>little</span> <span
  m='2259220'>omega.</span> <span m='2260180'>And</span> <span
  m='2260330'>this</span> <span m='2260570'>then</span> <span
  m='2260810'>tells</span> <span m='2261260'>us</span> <span
  m='2261950'>what</span> <span m='2262130'>the</span> <span
  m='2262220'>Fourier</span> <span m='2262700'>transform</span> <span
  m='2264470'>of</span> <span m='2264650'>the</span> <span
  m='2264740'>sequence</span> <span m='2265090'>is</span> <span
  m='2266300'>in</span> <span m='2266420'>terms</span> <span
  m='2267020'>of</span> <span m='2267380'>the</span> <span
  m='2267500'>Fourier</span> <span m='2267890'>transform</span> <span
  m='2269000'>of</span> <span m='2269180'>the</span> <span
  m='2269300'>output.</span> </p><p><span m='2271080'>Well,</span> <span
  m='2271760'>this</span> <span m='2272030'>is</span> <span
  m='2272150'>just</span> <span m='2272390'>the</span> <span
  m='2272450'>equations.</span> <span m='2273510'>Let's</span> <span
  m='2274130'>take</span> <span m='2274400'>a</span> <span
  m='2274460'>look</span> <span m='2274790'>at</span> <span
  m='2275090'>what</span> <span m='2275600'>this</span> <span
  m='2275870'>looks</span> <span m='2276170'>like</span> <span
  m='2276860'>graphically.</span> <span m='2286760'>I've</span> <span
  m='2287990'>depicted</span> <span m='2290000'>here</span> <span
  m='2291710'>the</span> <span m='2292670'>continuous</span> <span
  m='2293330'>time</span> <span m='2293960'>Fourier</span> <span
  m='2294470'>transform</span> <span m='2296030'>of</span> <span
  m='2298490'>some</span> <span m='2299090'>time</span> <span
  m='2299390'>function,</span> <span m='2300380'>and</span> <span
  m='2300740'>I</span> <span m='2300830'>picked</span> <span
  m='2301070'>the</span> <span m='2301160'>Fourier</span> <span
  m='2301610'>transform</span> <span m='2302480'>that</span> <span
  m='2303920'>looks</span> <span m='2304220'>like</span> <span
  m='2304430'>a</span> <span m='2304490'>triangle.</span> <span
  m='2306500'>Well,</span> <span m='2307220'>first</span> <span
  m='2307610'>of</span> <span m='2307730'>all</span> <span m='2308000'>we</span>
  <span m='2308150'>derived</span> <span m='2308630'>the</span> <span
  m='2308750'>fact</span> <span m='2309440'>that</span> <span
  m='2309710'>the</span> <span m='2309890'>impulse</span> <span
  m='2310910'>train</span> <span m='2312260'>that</span> <span
  m='2312470'>results</span> <span m='2313040'>from</span> <span
  m='2313250'>sampling</span> <span m='2314060'>little</span> <span
  m='2314300'>x</span> <span m='2314520'>sub a</span> <span
  m='2314870'>of</span> <span m='2314990'>t</span> <span m='2315980'>has</span>
  <span m='2316190'>a</span> <span m='2316250'>Fourier</span> <span
  m='2316700'>transform,</span> <span m='2317910'>which</span> <span
  m='2318020'>is</span> <span m='2318230'>this,</span> <span
  m='2319220'>periodically</span> <span m='2320420'>repeated</span> <span
  m='2321110'>in</span> <span m='2321280'>frequency</span> <span
  m='2322850'>with</span> <span m='2323480'>a</span> <span
  m='2323930'>period</span> <span m='2324980'>in</span> <span
  m='2325130'>frequency</span> <span m='2326000'>equal</span> <span
  m='2326330'>to</span> <span m='2326490'>2</span> <span m='2326720'>pi</span>
  <span m='2327380'>divided</span> <span m='2327830'>by</span> <span
  m='2328010'>capital</span> <span m='2328490'>1,</span> <span
  m='2329360'>where</span> <span m='2329510'>capital</span> <span
  m='2330020'>1</span> <span m='2330590'>is</span> <span m='2331070'>the</span>
  <span m='2331190'>sampling</span> <span m='2331730'>rate.</span> </p><p><span
  m='2333990'>And</span> <span m='2335160'>on</span> <span
  m='2335310'>the</span> <span m='2335400'>basis</span> <span
  m='2335970'>of</span> <span m='2336150'>the</span> <span
  m='2336240'>expression</span> <span m='2337110'>that</span> <span
  m='2337260'>we</span> <span m='2337440'>derived</span> <span
  m='2338250'>relating</span> <span m='2338730'>the</span> <span
  m='2338820'>discrete</span> <span m='2339330'>time</span> <span
  m='2340080'>Fourier</span> <span m='2340570'>transform</span> <span
  m='2342060'>and</span> <span m='2342210'>the</span> <span
  m='2342300'>continuous</span> <span m='2342960'>time</span> <span
  m='2343290'>Fourier</span> <span m='2343740'>transform,</span> <span
  m='2345430'>the</span> <span m='2345510'>discrete</span> <span
  m='2345990'>time</span> <span m='2346290'>Fourier</span> <span
  m='2346710'>transform</span> <span m='2347970'>looks</span> <span
  m='2348300'>exactly</span> <span m='2349020'>like</span> <span
  m='2349410'>this,</span> <span m='2350415'>but</span> <span
  m='2350760'>with</span> <span m='2351210'>a</span> <span
  m='2351420'>re-normalization</span> <span m='2352830'>of</span> <span
  m='2352980'>the</span> <span m='2353100'>frequency</span> <span
  m='2353700'>axis,</span> <span m='2354180'>because</span> <span
  m='2355050'>capital</span> <span m='2355560'>omega</span> <span
  m='2356550'>times</span> <span m='2357390'>capital</span> <span
  m='2357870'>T</span> <span m='2358650'>is</span> <span
  m='2358860'>equal</span> <span m='2359250'>to</span> <span
  m='2359700'>little</span> <span m='2360000'>omega.</span> <span
  m='2361540'>Yes,</span> <span m='2361860'>capital</span> <span
  m='2362210'>omega</span> <span m='2362640'>times</span> <span
  m='2362880'>capital</span> <span m='2363300'>T</span> <span
  m='2363720'>is</span> <span m='2363870'>equal</span> <span
  m='2364170'>to</span> <span m='2364290'>little</span> <span
  m='2364560'>omega.</span> <span m='2365730'>So</span> <span
  m='2365970'>where</span> <span m='2366150'>capital</span> <span
  m='2366690'>omega</span> <span m='2367800'>is</span> <span
  m='2367980'>equal</span> <span m='2368430'>to</span> <span
  m='2369900'>2</span> <span m='2370080'>pi</span> <span m='2370590'>over</span>
  <span m='2371020'>capital</span> <span m='2371356'>T,</span> <span
  m='2373170'>little</span> <span m='2373470'>omega</span> <span
  m='2374010'>is</span> <span m='2374220'>equal</span> <span
  m='2374520'>to</span> <span m='2374640'>2</span> <span m='2374880'>pi.</span>
  <span m='2375870'>So</span> <span m='2376500'>this</span> <span
  m='2376800'>point,</span> <span m='2377460'>which</span> <span
  m='2377970'>was</span> <span m='2378210'>at</span> <span m='2378690'>pi</span>
  <span m='2379050'>over</span> <span m='2379320'>capital</span> <span
  m='2379670'>T</span> <span m='2380760'>ends</span> <span m='2381090'>up</span>
  <span m='2381330'>on</span> <span m='2381480'>the</span> <span
  m='2381600'>omega,</span> <span m='2382140'>little</span> <span
  m='2382440'>omega</span> <span m='2382890'>axis</span> <span
  m='2383640'>at</span> <span m='2383790'>pi.</span> <span m='2384930'>So</span>
  <span m='2385470'>this</span> <span m='2385740'>picture</span> <span
  m='2386640'>just</span> <span m='2386880'>simply</span> <span
  m='2387300'>gets</span> <span m='2387510'>scaled</span> <span
  m='2389430'>according</span> <span m='2390180'>to</span> <span
  m='2390330'>the</span> <span m='2390420'>relationship</span> <span
  m='2391320'>that</span> <span m='2391440'>capital</span> <span
  m='2391920'>omega</span> <span m='2392340'>times</span> <span
  m='2392660'>capital</span> <span m='2393003'>T</span> <span
  m='2393690'>is</span> <span m='2393840'>equal</span> <span
  m='2394110'>to</span> <span m='2394230'>little</span> <span
  m='2394500'>omega.</span> </p><p><span m='2396630'>Well,</span> <span
  m='2398170'>this</span> <span m='2398560'>is,</span> <span
  m='2398950'>for</span> <span m='2399130'>one</span> <span
  m='2399460'>choice</span> <span m='2400180'>of</span> <span
  m='2400720'>the</span> <span m='2400810'>sampling</span> <span
  m='2401350'>period.</span> <span m='2402310'>Obviously,</span> <span
  m='2403210'>if</span> <span m='2403390'>capital</span> <span
  m='2403930'>T</span> <span m='2404650'>was</span> <span
  m='2405730'>large</span> <span m='2406210'>enough</span> <span
  m='2407260'>so</span> <span m='2407440'>that</span> <span m='2407590'>2</span>
  <span m='2407800'>pi</span> <span m='2408160'>over</span> <span m='2408370'>t
  1</span> <span m='2408550'>was</span> <span m='2409000'>small</span> <span
  m='2409420'>enough,</span> <span m='2410420'>then</span> <span
  m='2410500'>each</span> <span m='2410830'>of</span> <span
  m='2410950'>these</span> <span m='2411220'>individual</span> <span
  m='2411880'>replicas</span> <span m='2412720'>of</span> <span
  m='2412870'>the</span> <span m='2412960'>frequency</span> <span
  m='2413530'>response</span> <span m='2414430'>would</span> <span
  m='2414610'>interact.</span> <span m='2416200'>And</span> <span
  m='2416950'>we</span> <span m='2417160'>wouldn't</span> <span
  m='2417490'>have</span> <span m='2417880'>just</span> <span
  m='2418080'>the</span> <span m='2418180'>simple</span> <span
  m='2418510'>separation</span> <span m='2419860'>of</span> <span
  m='2420130'>the</span> <span m='2420250'>spectra</span> <span
  m='2420970'>as</span> <span m='2421120'>we</span> <span
  m='2421270'>have</span> <span m='2421570'>here.</span> <span
  m='2422380'>We'd</span> <span m='2422530'>have</span> <span
  m='2422980'>an</span> <span m='2423100'>interaction,</span> <span
  m='2424660'>which</span> <span m='2425230'>of</span> <span
  m='2425380'>course,</span> <span m='2426190'>is</span> <span
  m='2426940'>the</span> <span m='2427060'>interaction</span> <span
  m='2428290'>and</span> <span m='2428410'>the</span> <span
  m='2428530'>relationship</span> <span m='2429730'>between</span> <span
  m='2430750'>when</span> <span m='2430960'>that</span> <span
  m='2431110'>interaction</span> <span m='2431710'>occurs</span> <span
  m='2432340'>and</span> <span m='2432510'>capital</span> <span
  m='2432965'>T,</span> <span m='2433690'>is</span> <span m='2433810'>the</span>
  <span m='2433900'>basis</span> <span m='2434830'>for</span> <span
  m='2434980'>the</span> <span m='2435070'>well-known,</span> <span
  m='2436090'>and</span> <span m='2436180'>hopefully,</span> <span
  m='2437380'>theorem</span> <span m='2437740'>that</span> <span
  m='2437890'>you're</span> <span m='2438010'>familiar</span> <span
  m='2438460'>with</span> <span m='2439120'>namely,</span> <span
  m='2439450'>the</span> <span m='2439570'>sampling</span> <span
  m='2440080'>theorem.</span> </p><p><span m='2441550'>Well,</span> <span
  m='2441730'>to</span> <span m='2441850'>illustrate</span> <span
  m='2442450'>that</span> <span m='2443500'>if</span> <span
  m='2443890'>we</span> <span m='2444070'>had</span> <span m='2444730'>a</span>
  <span m='2445060'>different</span> <span m='2445480'>sampling</span> <span
  m='2446320'>rate,</span> <span m='2446830'>say</span> <span
  m='2447370'>twice</span> <span m='2448390'>the</span> <span
  m='2448480'>sampling</span> <span m='2448990'>rate</span> <span
  m='2449380'>that</span> <span m='2449560'>we</span> <span
  m='2449680'>have</span> <span m='2449980'>over</span> <span
  m='2450220'>here,</span> <span m='2450580'>so</span> <span
  m='2450760'>that</span> <span m='2450910'>capital</span> <span
  m='2451255'>T</span> <span m='2451600'>is</span> <span
  m='2451720'>equal</span> <span m='2451990'>to</span> <span
  m='2452140'>2</span> <span m='2452620'>times</span> <span
  m='2453340'>capital</span> <span m='2453700'>T</span> <span
  m='2454060'>1,</span> <span m='2456140'>then</span> <span
  m='2456800'>starting</span> <span m='2457310'>with</span> <span
  m='2457460'>the</span> <span m='2457550'>same</span> <span
  m='2458480'>continuous</span> <span m='2459080'>time</span> <span
  m='2459440'>spectrum,</span> <span m='2460910'>what</span> <span
  m='2461060'>we</span> <span m='2461240'>have</span> <span
  m='2461570'>now</span> <span m='2462200'>is</span> <span
  m='2462890'>the</span> <span m='2463110'>spectra,</span> <span
  m='2464630'>again</span> <span m='2465080'>periodically</span> <span
  m='2465860'>repeated,</span> <span m='2467030'>with</span> <span
  m='2467210'>a</span> <span m='2467270'>period</span> <span
  m='2467840'>again,</span> <span m='2468360'>which</span> <span
  m='2468440'>is</span> <span m='2468560'>2</span> <span m='2468740'>pi</span>
  <span m='2469070'>over</span> <span m='2469310'>capital</span> <span
  m='2469790'>T,</span> <span m='2470270'>which</span> <span
  m='2470450'>in</span> <span m='2470540'>this</span> <span
  m='2470720'>case</span> <span m='2471290'>is</span> <span m='2472070'>2</span>
  <span m='2472220'>pi</span> <span m='2472670'>over</span> <span
  m='2472970'>capital</span> <span m='2473330'>T</span> <span
  m='2473690'>2,</span> <span m='2475310'>but</span> <span
  m='2475520'>now</span> <span m='2475820'>they</span> <span
  m='2475970'>interact</span> <span m='2477140'>and</span> <span
  m='2477290'>of</span> <span m='2477380'>course,</span> <span
  m='2477650'>we</span> <span m='2477740'>have</span> <span
  m='2477950'>to</span> <span m='2478040'>add</span> <span
  m='2478310'>these</span> <span m='2478580'>up.</span> <span
  m='2478850'>That</span> <span m='2479000'>was</span> <span
  m='2479180'>the</span> <span m='2479270'>expression</span> <span
  m='2480080'>that</span> <span m='2480200'>we</span> <span
  m='2480350'>just</span> <span m='2480640'>derived.</span> </p><p><span
  m='2481730'>So</span> <span m='2482570'>in</span> <span
  m='2482690'>that</span> <span m='2482870'>case,</span> <span
  m='2483390'>we</span> <span m='2483410'>get</span> <span
  m='2483620'>some</span> <span m='2483830'>interaction</span> <span
  m='2484760'>or</span> <span m='2485090'>aliasing,</span> <span
  m='2486110'>as</span> <span m='2486290'>it's</span> <span
  m='2486470'>referred</span> <span m='2486890'>to.</span> <span
  m='2488160'>And</span> <span m='2488540'>due</span> <span
  m='2488780'>to</span> <span m='2488930'>this</span> <span
  m='2489140'>aliasing,</span> <span m='2490400'>the</span> <span
  m='2491240'>periodic,</span> <span m='2492320'>one</span> <span
  m='2492590'>period</span> <span m='2493250'>of</span> <span
  m='2493460'>this</span> <span m='2493670'>periodic</span> <span
  m='2494300'>spectrum</span> <span m='2495410'>no</span> <span
  m='2495620'>longer</span> <span m='2496340'>resembles</span> <span
  m='2497300'>the</span> <span m='2497420'>original</span> <span
  m='2497840'>spectrum.</span> <span m='2499780'>This</span> <span
  m='2500200'>is</span> <span m='2500980'>the</span> <span
  m='2501070'>Fourier</span> <span m='2501550'>transform</span> <span
  m='2503050'>for</span> <span m='2503830'>the</span> <span
  m='2504550'>sampled</span> <span m='2505330'>continuous</span> <span
  m='2505990'>time</span> <span m='2506320'>function.</span> <span
  m='2506980'>That</span> <span m='2507160'>is,</span> <span
  m='2507730'>this</span> <span m='2507940'>is</span> <span
  m='2508060'>the</span> <span m='2508190'>Fourier</span> <span
  m='2508540'>transform</span> <span m='2509230'>for</span> <span
  m='2509380'>the</span> <span m='2509530'>impulse</span> <span
  m='2510010'>train.</span> <span m='2510970'>And</span> <span
  m='2511090'>now</span> <span m='2511480'>if</span> <span m='2511660'>we</span>
  <span m='2511810'>renormalizing</span> <span m='2512650'>the</span> <span
  m='2512770'>frequency</span> <span m='2513340'>axis</span> <span
  m='2514330'>so</span> <span m='2514510'>that</span> <span
  m='2514660'>we</span> <span m='2514810'>express</span> <span
  m='2515350'>this</span> <span m='2515650'>in</span> <span
  m='2515800'>terms</span> <span m='2516310'>of</span> <span
  m='2516490'>the</span> <span m='2516580'>discrete</span> <span
  m='2517090'>time</span> <span m='2517480'>frequency</span> <span
  m='2518050'>variable,</span> <span m='2519400'>little</span> <span
  m='2519670'>omega,</span> <span m='2520870'>then</span> <span
  m='2521710'>we</span> <span m='2521860'>simply</span> <span
  m='2522430'>scale</span> <span m='2523390'>this</span> <span
  m='2523600'>picture</span> <span m='2524560'>so</span> <span
  m='2524800'>that</span> <span m='2525100'>we</span> <span
  m='2525310'>end</span> <span m='2525580'>up</span> <span
  m='2526030'>with</span> <span m='2526720'>2</span> <span m='2526900'>pi</span>
  <span m='2527260'>over</span> <span m='2527610'>capital</span> <span
  m='2528095'>T,</span> <span m='2529390'>corresponding</span> <span
  m='2530350'>to</span> <span m='2531250'>2</span> <span m='2531460'>pi</span>
  <span m='2532450'>in</span> <span m='2532840'>little</span> <span
  m='2533080'>omega.</span> <span m='2534760'>Pi</span> <span
  m='2535300'>over</span> <span m='2536330'>capital</span> <span
  m='2536760'>T</span> <span m='2537460'>corresponding</span> <span
  m='2538210'>to</span> <span m='2538360'>pi.</span> </p><p><span
  m='2539080'>And</span> <span m='2539170'>we</span> <span
  m='2539320'>see</span> <span m='2539560'>in</span> <span
  m='2539680'>fact,</span> <span m='2540130'>as--</span> <span
  m='2540910'>we</span> <span m='2541030'>better</span> <span
  m='2541360'>see,</span> <span m='2541750'>that</span> <span
  m='2541960'>is,</span> <span m='2542110'>it</span> <span
  m='2542200'>better</span> <span m='2542440'>turn</span> <span
  m='2542710'>out</span> <span m='2542950'>this</span> <span
  m='2543190'>way,</span> <span m='2544240'>that</span> <span
  m='2545080'>the</span> <span m='2545200'>spectrum</span> <span
  m='2546100'>in</span> <span m='2546250'>the</span> <span
  m='2546340'>discrete</span> <span m='2546730'>time</span> <span
  m='2547060'>case</span> <span m='2548080'>is</span> <span m='2548260'>a</span>
  <span m='2548290'>periodic</span> <span m='2548950'>function</span> <span
  m='2549700'>of</span> <span m='2550330'>omega.</span> <span
  m='2551110'>In</span> <span m='2551230'>other</span> <span
  m='2551440'>words,</span> <span m='2551770'>it's</span> <span
  m='2551860'>periodic.</span> <span m='2552940'>Furthermore,</span> <span
  m='2553660'>the</span> <span m='2553780'>period</span> <span
  m='2554500'>is</span> <span m='2555400'>given</span> <span
  m='2555760'>by</span> <span m='2556510'>2</span> <span m='2556720'>pi,</span>
  <span m='2557500'>whereas</span> <span m='2557860'>here</span> <span
  m='2558760'>the</span> <span m='2558880'>period</span> <span
  m='2559360'>was</span> <span m='2559570'>2</span> <span m='2559780'>pi</span>
  <span m='2560140'>divided</span> <span m='2560590'>by</span> <span
  m='2561560'>capital</span> <span m='2561870'>T.</span> </p><p><span
  m='2563440'>All</span> <span m='2563580'>right,</span> <span
  m='2563980'>this</span> <span m='2564250'>perhaps</span> <span
  m='2564940'>takes</span> <span m='2565240'>a</span> <span
  m='2565300'>little</span> <span m='2565510'>digesting.</span> <span
  m='2566290'>And</span> <span m='2566680'>you'll</span> <span
  m='2566860'>have</span> <span m='2567040'>some</span> <span
  m='2567220'>chance</span> <span m='2567580'>to</span> <span
  m='2567700'>do</span> <span m='2567880'>that</span> <span
  m='2568660'>as</span> <span m='2569440'>we</span> <span
  m='2571930'>work</span> <span m='2572140'>some</span> <span
  m='2572320'>problems.</span> <span m='2573040'>We,</span> <span
  m='2573250'>meaning</span> <span m='2573520'>you,</span> <span
  m='2574160'>as</span> <span m='2574660'>you</span> <span
  m='2574750'>work</span> <span m='2574990'>some</span> <span
  m='2575140'>problems</span> <span m='2575980'>in</span> <span
  m='2576430'>the</span> <span m='2576520'>study</span> <span
  m='2576880'>guide</span> <span m='2577420'>and</span> <span
  m='2578500'>digest</span> <span m='2579040'>this</span> <span
  m='2579250'>a</span> <span m='2579310'>little</span> <span
  m='2579580'>while</span> <span m='2580120'>you're</span> <span
  m='2580270'>reading</span> <span m='2580570'>the</span> <span
  m='2580690'>text.</span> <span m='2581540'>But</span> <span
  m='2581710'>it's</span> <span m='2581950'>an</span> <span
  m='2582040'>important</span> <span m='2582490'>relationship</span> <span
  m='2584310'>and</span> <span m='2584500'>it's</span> <span
  m='2584620'>important</span> <span m='2585190'>to</span> <span
  m='2585370'>understand</span> <span m='2585970'>it.</span> </p><p><span
  m='2587940'>Now,</span> <span m='2589570'>this</span> <span
  m='2590290'>is</span> <span m='2591400'>basically</span> <span
  m='2592150'>the</span> <span m='2592270'>Fourier</span> <span
  m='2592690'>transform,</span> <span m='2593440'>the</span> <span
  m='2593530'>relationship</span> <span m='2594310'>between</span> <span
  m='2594790'>the</span> <span m='2595270'>discrete</span> <span
  m='2595660'>time</span> <span m='2595990'>and</span> <span
  m='2596080'>continuous</span> <span m='2596650'>time</span> <span
  m='2596920'>Fourier</span> <span m='2597360'>transform.</span> <span
  m='2598990'>One</span> <span m='2599140'>of</span> <span
  m='2599230'>the</span> <span m='2599380'>difficulties</span> <span
  m='2600640'>with</span> <span m='2600850'>the</span> <span
  m='2600940'>Fourier</span> <span m='2601390'>transform,</span> <span
  m='2603370'>which</span> <span m='2603850'>I've</span> <span
  m='2604000'>avoided</span> <span m='2605140'>illustrating</span> <span
  m='2605770'>explicitly</span> <span m='2606790'>in</span> <span
  m='2606910'>this</span> <span m='2607090'>lecture,</span> <span
  m='2608440'>is</span> <span m='2608590'>that</span> <span
  m='2608740'>the</span> <span m='2608830'>Fourier</span> <span
  m='2609190'>transform</span> <span m='2609730'>doesn't</span> <span
  m='2610030'>exist</span> <span m='2610420'>for</span> <span
  m='2610600'>all</span> <span m='2610750'>sequences.</span> <span
  m='2612040'>In</span> <span m='2612160'>particular,</span> <span
  m='2612760'>it</span> <span m='2612850'>doesn't</span> <span
  m='2613120'>converge</span> <span m='2614110'>for</span> <span
  m='2614320'>all</span> <span m='2614470'>sequences.</span> <span
  m='2615950'>And</span> <span m='2616570'>this</span> <span
  m='2616990'>is</span> <span m='2617290'>a</span> <span
  m='2617350'>problem</span> <span m='2618610'>which</span> <span
  m='2619690'>we</span> <span m='2619840'>can</span> <span
  m='2620020'>get</span> <span m='2620260'>around</span> <span
  m='2620920'>by</span> <span m='2621190'>generalizing</span> <span
  m='2622570'>the</span> <span m='2622660'>notion</span> <span
  m='2623290'>of</span> <span m='2623980'>the</span> <span
  m='2624070'>Fourier</span> <span m='2624520'>transform</span> <span
  m='2625930'>to</span> <span m='2626530'>what</span> <span
  m='2626740'>we'll</span> <span m='2626920'>call</span> <span
  m='2627580'>the</span> <span m='2627700'>z</span> <span
  m='2627910'>transform.</span> <span m='2629260'>And</span> <span
  m='2630340'>the</span> <span m='2630490'>z</span> <span
  m='2630670'>transform,</span> <span m='2631360'>as</span> <span
  m='2631750'>you'll</span> <span m='2631960'>observe,</span> <span
  m='2633010'>is</span> <span m='2633250'>like,</span> <span
  m='2634180'>in</span> <span m='2634270'>the</span> <span
  m='2634360'>continuous</span> <span m='2634900'>time</span> <span
  m='2635200'>case,</span> <span m='2635830'>the</span> <span
  m='2635920'>Laplace</span> <span m='2636400'>transform.</span> <span
  m='2637660'>And</span> <span m='2638050'>this</span> <span
  m='2638260'>is</span> <span m='2638380'>what</span> <span
  m='2638680'>we'll</span> <span m='2639040'>go</span> <span m='2639250'>on
  to</span> <span m='2639620'>in</span> <span m='2639730'>the</span> <span
  m='2639820'>next</span> <span m='2640030'>lecture.</span> </p><p><span
  m='2641000'>Thanks</span> </p><p><span m='2642500'>[MUSIC PLAYING]</span> </p>
embedded_media:
  - uid: 615aa34ef098a20abd5172767f2ee070
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: MITRES_6_008S11_lec04.pdf
    title: MITRES_6_008S11_lec04.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-4-the-discrete-time-fourier-transform/MITRES_6_008S11_lec04.pdf
  - uid: 502913cf6fc8e80675e7c11e22fba7c4
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: dHveJh0UbY8
  - uid: 501ff6f35f05b549ed6fe0decf742d75
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-4-the-discrete-time/id481803782?i=108362007
  - uid: e47f1bbad5dfe23a7a7f4dbef57b923b
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec04_300k.mp4'
  - uid: ca6b5cfe8e3020763262d005305790b0
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/dHveJh0UbY8/default.jpg'
  - uid: 49978ed7f8446fc768f9391a47a71f75
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: dHveJh0UbY8
  - uid: e7bbaab79fca55c3b52d86d019d7d71f
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: dHveJh0UbY8.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-4-the-discrete-time-fourier-transform/dHveJh0UbY8.srt
  - uid: 4f98c4942b694a42230624f0a57dcec5
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: dHveJh0UbY8.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-4-the-discrete-time-fourier-transform/dHveJh0UbY8.pdf
  - uid: f81eb5c8c230502ca1fe7cb01b6e9414
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 79cfb8223b4202854f22368dcf4ee28b
    parent_uid: 2d6c677c91944e7646cef1245ec7b8b5
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
