---
order_index: null
title: 'Lecture 20: Computation of the Discrete Fourier Transform, Part 3'
template_type: Tabbed
uid: 040463c7a951ba8c31ecca7c0a08d9ac
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-20-computation-of-the-discrete-fourier-transform-part-3
short_url: lecture-20-computation-of-the-discrete-fourier-transform-part-3
inline_embed_id: '50377476lecture20:computationofthediscretefouriertransform,part311316374'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Rearrangements of the basic
  decimation-in-frequency algorithm, relation between decimation-in-time and
  decimation-in-frequency through the transposition theorem, arbitrary radix FFT
  algorithms.</p> <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Computation of the Discrete Fourier Transform, Part 3 (<a
  href="./resolveuid/fd93ff783243d4c0ee1b5959a57b5c0e">PDF</a>)</p>
transcript: >-
  <p><span m='90'>The</span> <span m='180'>following</span> <span
  m='600'>content</span> <span m='1170'>is</span> <span m='1320'>provided</span>
  <span m='1770'>under</span> <span m='2009'>a</span> <span
  m='2070'>Creative</span> <span m='2490'>Commons</span> <span
  m='2880'>license.</span> <span m='4030'>Your</span> <span
  m='4170'>support</span> <span m='4680'>will</span> <span m='4860'>help</span>
  <span m='5100'>MIT</span> <span m='5550'>OpenCourseWare</span> <span
  m='6330'>continue</span> <span m='6840'>to</span> <span m='6960'>offer</span>
  <span m='7350'>high</span> <span m='7590'>quality</span> <span
  m='8100'>educational</span> <span m='8700'>resources</span> <span
  m='9330'>for</span> <span m='9510'>free.</span> <span m='10720'>To</span>
  <span m='10820'>make</span> <span m='10920'>a</span> <span
  m='10980'>donation</span> <span m='11730'>or</span> <span
  m='11910'>view</span> <span m='12390'>additional</span> <span
  m='12780'>materials</span> <span m='13320'>from</span> <span
  m='13500'>hundreds</span> <span m='13920'>of</span> <span m='14010'>MIT</span>
  <span m='14430'>courses,</span> <span m='15550'>visit</span> <span
  m='15750'>MIT</span> <span m='16200'>OpenCourseWare</span> <span
  m='17280'>at</span> <span m='17400'>ocw.mit.edu.</span> </p><p><span
  m='22330'>[MUSIC PLAYING]</span> </p><p><span m='48345'>PROFESSOR:</span>
  <span m='48850'>In</span> <span m='49000'>the</span> <span
  m='49080'>last</span> <span m='49410'>lecture,</span> <span
  m='49950'>we</span> <span m='50340'>introduced</span> <span
  m='51270'>an</span> <span m='51360'>alternative</span> <span
  m='52410'>set</span> <span m='52770'>of</span> <span
  m='53070'>algorithms</span> <span m='53820'>for</span> <span
  m='54210'>computation</span> <span m='55140'>of</span> <span
  m='55260'>the</span> <span m='55380'>fast</span> <span
  m='55680'>Fourier</span> <span m='56010'>transform</span> <span
  m='57690'>or</span> <span m='58290'>rather,</span> <span
  m='58590'>computation</span> <span m='59220'>of</span> <span
  m='59280'>the</span> <span m='59370'>discrete</span> <span
  m='59700'>Fourier</span> <span m='60100'>transform.</span> <span
  m='60930'>And</span> <span m='61770'>we</span> <span m='61950'>refer</span>
  <span m='62340'>to</span> <span m='62490'>these</span> <span
  m='62880'>as</span> <span m='63240'>the</span> <span
  m='63390'>decimation</span> <span m='64170'>in</span> <span
  m='64319'>frequency</span> <span m='65040'>form</span> <span
  m='65400'>of</span> <span m='65489'>the</span> <span
  m='65640'>algorithm.</span> <span m='66990'>As</span> <span
  m='67140'>you</span> <span m='67230'>recall,</span> <span m='67950'>we</span>
  <span m='69240'>developed</span> <span m='69810'>the</span> <span
  m='70050'>decimation</span> <span m='70900'>in</span> <span
  m='71050'>frequency</span> <span m='71610'>form</span> <span
  m='71910'>of</span> <span m='72000'>the</span> <span
  m='72180'>algorithm</span> <span m='73380'>by</span> <span
  m='74160'>essentially</span> <span m='74820'>organizing</span> <span
  m='75690'>the</span> <span m='75990'>computation</span> <span
  m='77010'>of</span> <span m='77250'>the</span> <span m='77400'>even</span>
  <span m='77730'>numbered</span> <span m='78390'>DFT</span> <span
  m='78960'>points</span> <span m='80070'>and</span> <span m='80370'>the</span>
  <span m='80550'>odd</span> <span m='80790'>numbered</span> <span
  m='81510'>DFT</span> <span m='82050'>points</span> <span
  m='82470'>separately</span> <span m='84390'>and</span> <span
  m='84930'>then</span> <span m='85320'>proceeded</span> <span
  m='85920'>in</span> <span m='86040'>a</span> <span m='86100'>similar</span>
  <span m='86490'>manner.</span> </p><p><span m='87820'>This</span> <span
  m='88170'>corresponded</span> <span m='88770'>to</span> <span
  m='89100'>breaking</span> <span m='89490'>the</span> <span
  m='89580'>computation</span> <span m='90660'>into</span> <span
  m='90900'>two</span> <span m='91290'>and</span> <span m='91470'>over</span>
  <span m='91740'>two</span> <span m='92095'>point</span> <span
  m='92450'>DFT's</span> <span m='93420'>proceeded</span> <span
  m='93930'>in</span> <span m='94110'>a</span> <span m='94170'>similar</span>
  <span m='94560'>manner</span> <span m='95400'>to</span> <span
  m='95520'>decompose</span> <span m='96330'>the</span> <span
  m='96450'>computation</span> <span m='97290'>of</span> <span
  m='97470'>these</span> <span m='98190'>separately</span> <span
  m='98910'>into</span> <span m='99180'>their</span> <span m='99480'>even</span>
  <span m='99780'>numbered</span> <span m='100080'>points</span> <span
  m='100530'>and</span> <span m='100650'>odd</span> <span
  m='100830'>numbered</span> <span m='101170'>points,</span> <span m='101530'>et
  cetera.</span> <span m='102660'>And</span> <span m='103410'>the</span> <span
  m='104040'>flow</span> <span m='104310'>graph</span> <span
  m='104940'>that</span> <span m='105120'>resulted</span> <span
  m='106320'>from</span> <span m='106530'>this</span> <span
  m='106680'>procedure</span> <span m='107880'>was--</span> <span
  m='108690'>as</span> <span m='109230'>I've</span> <span
  m='109680'>shown</span> <span m='110040'>here--</span> <span
  m='111460'>which</span> <span m='111870'>is</span> <span m='112770'>one</span>
  <span m='113010'>form,</span> <span m='113760'>then,</span> <span
  m='114240'>of</span> <span m='114570'>the</span> <span
  m='114750'>decimation</span> <span m='115540'>in</span> <span
  m='115650'>frequency</span> <span m='116490'>form</span> <span
  m='117090'>of</span> <span m='117450'>the</span> <span m='117570'>fast</span>
  <span m='117900'>Fourier</span> <span m='118230'>transform</span> <span
  m='118830'>algorithm.</span> <span m='121890'>It</span> <span
  m='123600'>begins</span> <span m='124260'>with</span> <span
  m='124470'>the</span> <span m='124560'>data</span> <span
  m='125130'>sorted</span> <span m='125730'>in</span> <span
  m='125910'>normal</span> <span m='126300'>order</span> <span
  m='127290'>and</span> <span m='127980'>proceeds</span> <span
  m='128699'>to</span> <span m='129120'>the</span> <span m='129240'>data</span>
  <span m='129810'>sorted</span> <span m='130350'>in</span> <span
  m='130500'>big</span> <span m='130710'>reversed</span> <span
  m='131190'>order.</span> </p><p><span m='132090'>And</span> <span
  m='132450'>as</span> <span m='132660'>I</span> <span
  m='132750'>stressed</span> <span m='133170'>last</span> <span
  m='133500'>time,</span> <span m='134310'>it</span> <span
  m='134490'>also</span> <span m='134940'>corresponds</span> <span
  m='135900'>to</span> <span m='136230'>an</span> <span
  m='136340'>in-place</span> <span m='136800'>computation</span> <span
  m='138180'>because</span> <span m='138750'>of</span> <span
  m='138900'>the</span> <span m='139020'>way</span> <span m='139560'>in</span>
  <span m='139740'>which</span> <span m='140220'>the</span> <span
  m='140340'>butterflies</span> <span m='141300'>are</span> <span
  m='141480'>laid</span> <span m='141780'>out.</span> <span m='142410'>In</span>
  <span m='142530'>particular,</span> <span m='143340'>the</span> <span
  m='143550'>output</span> <span m='143970'>nodes</span> <span
  m='144630'>for</span> <span m='144810'>each</span> <span
  m='145020'>butterfly</span> <span m='146190'>are</span> <span
  m='146400'>horizontally</span> <span m='147330'>adjacent</span> <span
  m='148290'>to</span> <span m='148410'>the</span> <span m='148560'>input</span>
  <span m='148890'>nodes.</span> <span m='150300'>Now</span> <span
  m='150930'>this</span> <span m='151350'>is</span> <span
  m='151590'>similar</span> <span m='152310'>in</span> <span m='153600'>a</span>
  <span m='153660'>number</span> <span m='154080'>of</span> <span
  m='154230'>respects</span> <span m='155160'>to</span> <span
  m='156570'>one</span> <span m='156930'>of</span> <span m='157170'>the</span>
  <span m='157320'>decimation</span> <span m='158040'>in</span> <span
  m='158130'>time</span> <span m='158760'>forms</span> <span
  m='159210'>of</span> <span m='159330'>the</span> <span m='159510'>FFT</span>
  <span m='160050'>algorithm.</span> </p><p><span m='161070'>Although,</span>
  <span m='161640'>as</span> <span m='161880'>I</span> <span
  m='162000'>also</span> <span m='162540'>indicated</span> <span
  m='163140'>last</span> <span m='163470'>time,</span> <span
  m='164440'>the</span> <span m='164540'>basic</span> <span
  m='164910'>structure</span> <span m='165570'>of</span> <span
  m='165690'>the</span> <span m='165810'>butterfly</span> <span
  m='166320'>computation</span> <span m='167280'>is</span> <span
  m='167400'>somewhat</span> <span m='167820'>different.</span> <span
  m='168570'>In</span> <span m='168690'>particular,</span> <span
  m='169950'>for</span> <span m='170640'>this</span> <span m='171480'>set</span>
  <span m='171990'>of</span> <span m='172290'>algorithms,</span> <span
  m='173510'>the</span> <span m='173610'>multiplication</span> <span
  m='174510'>by</span> <span m='174720'>powers</span> <span m='175200'>of</span>
  <span m='175290'>W</span> <span m='176520'>is</span> <span
  m='176910'>implemented</span> <span m='177630'>at</span> <span
  m='177840'>the</span> <span m='178350'>output</span> <span
  m='178830'>of</span> <span m='178920'>the</span> <span
  m='179040'>butterfly,</span> <span m='179850'>as</span> <span
  m='180060'>opposed</span> <span m='180510'>to</span> <span
  m='180630'>the</span> <span m='180750'>decimation</span> <span
  m='181530'>in</span> <span m='181650'>time</span> <span
  m='181980'>forms,</span> <span m='182970'>where</span> <span
  m='183240'>the</span> <span m='183360'>multiplication</span> <span
  m='184170'>by</span> <span m='184320'>powers</span> <span m='184770'>of</span>
  <span m='184890'>W</span> <span m='185430'>are</span> <span
  m='185580'>implemented</span> <span m='186240'>at</span> <span
  m='186390'>the</span> <span m='186540'>input</span> <span m='186900'>to</span>
  <span m='187020'>the</span> <span m='187110'>butterfly.</span> <span
  m='189300'>However,</span> <span m='190170'>there</span> <span
  m='190710'>is</span> <span m='191190'>a</span> <span m='191280'>very</span>
  <span m='191580'>close</span> <span m='191910'>relationship</span> <span
  m='192900'>between</span> <span m='194070'>this</span> <span
  m='194310'>flow</span> <span m='194580'>graph</span> <span
  m='195690'>and</span> <span m='196320'>the</span> <span
  m='196500'>original</span> <span m='196920'>flow</span> <span
  m='197190'>graph</span> <span m='197850'>that</span> <span
  m='198210'>we</span> <span m='198810'>implemented</span> <span
  m='199530'>for</span> <span m='200640'>the</span> <span
  m='200880'>decimation</span> <span m='201590'>in</span> <span
  m='201660'>time</span> <span m='202020'>algorithm.</span> </p><p><span
  m='203160'>In</span> <span m='203280'>particular,</span> <span
  m='204520'>the</span> <span m='204540'>two</span> <span m='204750'>flow</span>
  <span m='205050'>graphs</span> <span m='205620'>are</span> <span
  m='205830'>transposes</span> <span m='206790'>of</span> <span
  m='206910'>each</span> <span m='207090'>other.</span> <span
  m='208630'>Now</span> <span m='208860'>I</span> <span m='208950'>remind</span>
  <span m='209430'>you</span> <span m='209610'>that</span> <span
  m='210090'>in</span> <span m='210420'>one</span> <span m='210600'>of</span>
  <span m='210690'>the</span> <span m='210810'>early</span> <span
  m='211080'>lectures,</span> <span m='212280'>when</span> <span
  m='212580'>we</span> <span m='212730'>introduced</span> <span
  m='214050'>the</span> <span m='214590'>notation</span> <span
  m='215190'>of</span> <span m='215250'>flow</span> <span
  m='215520'>graphs</span> <span m='216030'>and</span> <span
  m='216150'>some</span> <span m='216360'>of</span> <span m='216420'>the</span>
  <span m='217070'>properties</span> <span m='217650'>of</span> <span
  m='217740'>flow</span> <span m='218010'>graphs,</span> <span
  m='219090'>one</span> <span m='219270'>of</span> <span m='219360'>the</span>
  <span m='219450'>properties</span> <span m='220110'>of</span> <span
  m='220170'>flow</span> <span m='220440'>graphs</span> <span
  m='221160'>that</span> <span m='221700'>I</span> <span
  m='222210'>mentioned--</span> <span m='222780'>although</span> <span
  m='223050'>we</span> <span m='223170'>didn't</span> <span
  m='223410'>derive</span> <span m='223860'>it--</span> <span
  m='224400'>was</span> <span m='224610'>the</span> <span m='224730'>fact</span>
  <span m='225390'>that</span> <span m='225810'>transposition</span> <span
  m='226680'>of</span> <span m='226800'>a</span> <span m='226860'>flow</span>
  <span m='227190'>graph</span> <span m='228120'>doesn't</span> <span
  m='228450'>change</span> <span m='228900'>the</span> <span
  m='229050'>input</span> <span m='229380'>output</span> <span
  m='229740'>characteristics.</span> <span m='231670'>So</span> <span
  m='231780'>then</span> <span m='231960'>in</span> <span
  m='232080'>fact,</span> <span m='233200'>if</span> <span m='233370'>we</span>
  <span m='233490'>took</span> <span m='233760'>this</span> <span
  m='233970'>flow</span> <span m='234240'>graph,</span> <span
  m='235920'>changed</span> <span m='236550'>the</span> <span
  m='236760'>direction</span> <span m='237330'>of</span> <span
  m='237480'>all</span> <span m='237660'>of</span> <span m='237750'>the</span>
  <span m='237900'>arrows,</span> <span m='239550'>treated</span> <span
  m='240450'>this</span> <span m='240660'>set</span> <span m='240900'>of</span>
  <span m='241020'>nodes</span> <span m='241440'>as</span> <span
  m='241560'>the</span> <span m='241680'>input</span> <span
  m='242040'>nodes</span> <span m='242640'>and</span> <span
  m='242790'>this</span> <span m='242940'>set</span> <span m='243150'>of</span>
  <span m='243270'>nodes</span> <span m='243870'>as</span> <span
  m='244080'>the</span> <span m='244230'>output</span> <span
  m='244650'>nodes,</span> <span m='245820'>then</span> <span
  m='246270'>since</span> <span m='246930'>the</span> <span
  m='247020'>flow</span> <span m='247320'>graph,</span> <span
  m='247710'>as</span> <span m='247870'>it's</span> <span
  m='248010'>indicated</span> <span m='248610'>here,</span> <span
  m='249660'>computes</span> <span m='250380'>the</span> <span
  m='250500'>discrete</span> <span m='250860'>Fourier</span> <span
  m='251310'>transform,</span> <span m='252510'>the</span> <span
  m='252630'>transposed</span> <span m='253590'>flow</span> <span
  m='253860'>graph</span> <span m='254580'>would</span> <span
  m='254730'>also</span> <span m='255120'>compute</span> <span
  m='255510'>the</span> <span m='255630'>discrete</span> <span
  m='255990'>Fourier</span> <span m='256440'>transform.</span> </p><p><span
  m='257709'>And</span> <span m='257730'>in</span> <span m='257850'>fact,</span>
  <span m='258540'>the</span> <span m='258630'>transposition</span> <span
  m='259709'>of</span> <span m='259860'>this</span> <span m='260100'>flow</span>
  <span m='260370'>graph</span> <span m='261269'>is</span> <span
  m='262260'>identical</span> <span m='263280'>to</span> <span
  m='263640'>the</span> <span m='263820'>first</span> <span
  m='264540'>flow</span> <span m='264780'>graph--</span> <span
  m='265820'>FFT</span> <span m='266370'>flow</span> <span
  m='266640'>graph--</span> <span m='267000'>that</span> <span
  m='267120'>we</span> <span m='267300'>introduced,</span> <span
  m='268260'>which</span> <span m='268470'>was</span> <span
  m='268980'>the</span> <span m='269430'>initial</span> <span
  m='269970'>decimation</span> <span m='270660'>in</span> <span
  m='270750'>time</span> <span m='271260'>form.</span> <span
  m='272070'>And</span> <span m='272970'>that</span> <span m='273360'>I</span>
  <span m='274290'>refer</span> <span m='274650'>you</span> <span
  m='274800'>to</span> <span m='275310'>again,</span> <span
  m='275700'>here.</span> <span m='277410'>So</span> <span
  m='278070'>this</span> <span m='278490'>is</span> <span m='278940'>the</span>
  <span m='279120'>decimation</span> <span m='279900'>in</span> <span
  m='280080'>time</span> <span m='281310'>form</span> <span m='281670'>of</span>
  <span m='281760'>the</span> <span m='281910'>algorithm</span> <span
  m='283020'>with</span> <span m='283140'>the</span> <span
  m='283290'>input</span> <span m='283650'>bit</span> <span
  m='283890'>reversed</span> <span m='284490'>and</span> <span
  m='284670'>the</span> <span m='284790'>output</span> <span
  m='285270'>in</span> <span m='285420'>normal</span> <span
  m='285780'>order.</span> </p><p><span m='287220'>This</span> <span
  m='287760'>is</span> <span m='288480'>the</span> <span
  m='288780'>transposition</span> <span m='291150'>of</span> <span
  m='292440'>this</span> <span m='293010'>flow</span> <span
  m='293340'>graph,</span> <span m='295150'>which</span> <span
  m='295710'>is</span> <span m='296160'>the</span> <span
  m='296280'>decimation</span> <span m='296970'>in</span> <span
  m='297060'>frequency</span> <span m='297630'>form</span> <span
  m='297990'>of</span> <span m='298080'>the</span> <span
  m='298260'>algorithm</span> <span m='299340'>with</span> <span
  m='299790'>the</span> <span m='299970'>input</span> <span m='300450'>in</span>
  <span m='300600'>normal</span> <span m='300960'>order</span> <span
  m='301440'>and</span> <span m='301980'>the</span> <span
  m='302130'>output</span> <span m='302550'>in</span> <span
  m='302700'>bit</span> <span m='302880'>reversed</span> <span
  m='303300'>order.</span> <span m='304830'>The</span> <span
  m='304920'>fact</span> <span m='305220'>that</span> <span
  m='305340'>these</span> <span m='305550'>are</span> <span
  m='305640'>related</span> <span m='306150'>through</span> <span
  m='307770'>transposition</span> <span m='308430'>of</span> <span
  m='308520'>the</span> <span m='308640'>flow</span> <span
  m='308910'>graph</span> <span m='309780'>isn't</span> <span
  m='310170'>a</span> <span m='310230'>particularly</span> <span
  m='311160'>important</span> <span m='311700'>point</span> <span
  m='312420'>from</span> <span m='312600'>a</span> <span
  m='312660'>practical</span> <span m='313200'>point</span> <span
  m='313500'>of</span> <span m='313560'>view.</span> <span m='314310'>But</span>
  <span m='314670'>it</span> <span m='314880'>is</span> <span
  m='315330'>a</span> <span m='315840'>useful</span> <span
  m='316740'>piece</span> <span m='316980'>of</span> <span
  m='317100'>insight</span> <span m='317700'>into</span> <span
  m='318000'>the</span> <span m='318120'>relationship</span> <span
  m='319230'>between</span> <span m='319620'>these</span> <span
  m='319800'>various</span> <span m='320250'>algorithms.</span> </p><p><span
  m='322321'>All</span> <span m='322760'>right,</span> <span
  m='323070'>now</span> <span m='323730'>just</span> <span m='324210'>as</span>
  <span m='324630'>we</span> <span m='324780'>did</span> <span
  m='325020'>with</span> <span m='325170'>the</span> <span
  m='325230'>decimation</span> <span m='325860'>in</span> <span
  m='325950'>time</span> <span m='327120'>forms</span> <span
  m='327810'>of</span> <span m='328140'>the</span> <span
  m='328290'>algorithm,</span> <span m='329430'>we</span> <span
  m='329580'>can</span> <span m='329760'>rearrange</span> <span
  m='330510'>the</span> <span m='330690'>decimation</span> <span
  m='331380'>in</span> <span m='331470'>frequency</span> <span
  m='332010'>form</span> <span m='332970'>of</span> <span m='333210'>the</span>
  <span m='333360'>algorithm</span> <span m='334590'>to</span> <span
  m='335490'>either</span> <span m='337020'>arrange</span> <span
  m='337620'>the</span> <span m='337830'>output</span> <span
  m='338670'>to</span> <span m='338790'>be</span> <span m='339000'>in</span>
  <span m='339120'>normal</span> <span m='339480'>order,</span> <span
  m='341250'>as</span> <span m='341400'>opposed</span> <span
  m='341790'>to</span> <span m='342090'>having</span> <span
  m='342390'>the</span> <span m='342510'>input</span> <span m='342840'>in</span>
  <span m='342960'>normal</span> <span m='343320'>order,</span> <span
  m='344040'>or</span> <span m='344280'>rearrange</span> <span
  m='344880'>it</span> <span m='345000'>so</span> <span m='345150'>that</span>
  <span m='345330'>both</span> <span m='345570'>the</span> <span
  m='345720'>input</span> <span m='346050'>and</span> <span
  m='346260'>output</span> <span m='346830'>are</span> <span
  m='347010'>in</span> <span m='347100'>normal</span> <span
  m='347460'>order</span> <span m='348240'>or</span> <span
  m='348750'>rearrange</span> <span m='349440'>it</span> <span
  m='349620'>as</span> <span m='350040'>we</span> <span m='350220'>will,</span>
  <span m='350910'>so</span> <span m='351180'>that</span> <span
  m='351780'>we</span> <span m='351960'>can</span> <span
  m='352290'>utilize</span> <span m='352770'>sequential</span> <span
  m='353340'>memory</span> <span m='353790'>rather</span> <span
  m='354090'>than</span> <span m='354270'>random</span> <span
  m='354600'>access</span> <span m='355080'>memory.</span> <span
  m='356880'>To</span> <span m='357000'>rearrange</span> <span
  m='357690'>the</span> <span m='357840'>flow</span> <span
  m='358110'>graph</span> <span m='358740'>so</span> <span
  m='358980'>that</span> <span m='359190'>the</span> <span
  m='359370'>output</span> <span m='359970'>is</span> <span m='360210'>in</span>
  <span m='360360'>normal</span> <span m='360750'>order,</span> <span
  m='361770'>we</span> <span m='362250'>would,</span> <span
  m='362490'>again,</span> <span m='362850'>simply</span> <span
  m='363330'>take</span> <span m='363930'>horizontal</span> <span
  m='364560'>lines</span> <span m='365820'>and</span> <span
  m='366610'>re-sort</span> <span m='367320'>them</span> <span
  m='367920'>so</span> <span m='368250'>that</span> <span m='369390'>the</span>
  <span m='369690'>output</span> <span m='370200'>nodes</span> <span
  m='370770'>are</span> <span m='370950'>sorted</span> <span
  m='371640'>in</span> <span m='372110'>a</span> <span m='372180'>normal</span>
  <span m='372600'>order.</span> <span m='373680'>And</span> <span
  m='374370'>the</span> <span m='374490'>flow</span> <span
  m='374760'>graph</span> <span m='375120'>that</span> <span
  m='375270'>results</span> <span m='377640'>is</span> <span m='378150'>a</span>
  <span m='378870'>decimation</span> <span m='379830'>in</span> <span
  m='379980'>frequency</span> <span m='381330'>form</span> <span
  m='381750'>of</span> <span m='381840'>the</span> <span
  m='381990'>algorithm,</span> <span m='384120'>for</span> <span
  m='384300'>which</span> <span m='385080'>the</span> <span
  m='385260'>outputs</span> <span m='386700'>are</span> <span
  m='387240'>in</span> <span m='387840'>normal</span> <span
  m='388260'>order.</span> </p><p><span m='390030'>But</span> <span
  m='390630'>the</span> <span m='390840'>inputs</span> <span
  m='391830'>are</span> <span m='392280'>in</span> <span m='392520'>bit</span>
  <span m='392730'>reversed</span> <span m='393180'>order.</span> <span
  m='395520'>Again,</span> <span m='396090'>as</span> <span
  m='396960'>this</span> <span m='397260'>flow</span> <span
  m='397500'>graph</span> <span m='397830'>has</span> <span
  m='398010'>been</span> <span m='398190'>sorted,</span> <span
  m='398880'>it</span> <span m='399180'>is</span> <span m='400140'>an</span>
  <span m='400260'>in-place</span> <span m='400800'>computation.</span> <span
  m='402180'>In-place,</span> <span m='402690'>again,</span> <span
  m='403050'>because</span> <span m='404040'>the</span> <span
  m='404130'>butterflies</span> <span m='404910'>are</span> <span
  m='404970'>laid</span> <span m='405240'>out</span> <span m='405450'>in</span>
  <span m='405540'>such</span> <span m='405840'>a</span> <span
  m='405900'>way</span> <span m='406290'>that</span> <span
  m='406950'>they</span> <span m='407400'>involve</span> <span
  m='407910'>horizontally</span> <span m='408870'>adjacent</span> <span
  m='409380'>nodes.</span> <span m='410280'>So</span> <span
  m='410580'>this</span> <span m='410790'>is</span> <span m='410940'>an</span>
  <span m='411030'>in-place</span> <span m='411540'>computation</span> <span
  m='412950'>with</span> <span m='413130'>the</span> <span
  m='413310'>input</span> <span m='414030'>in</span> <span m='414360'>bit</span>
  <span m='414570'>reversed</span> <span m='415020'>order</span> <span
  m='415860'>and</span> <span m='416490'>the</span> <span
  m='416670'>output</span> <span m='417240'>in</span> <span
  m='417390'>normal</span> <span m='417750'>order.</span> </p><p><span
  m='419730'>Again</span> <span m='420360'>this</span> <span
  m='420690'>is</span> <span m='421230'>a</span> <span
  m='421980'>transposition</span> <span m='425640'>of</span> <span
  m='426030'>one</span> <span m='426210'>of</span> <span m='426330'>the</span>
  <span m='426420'>flow</span> <span m='426660'>graphs</span> <span
  m='430170'>that</span> <span m='430320'>we</span> <span
  m='430440'>discussed</span> <span m='430980'>in</span> <span
  m='431070'>the</span> <span m='431130'>previous</span> <span
  m='431610'>lecture.</span> <span m='432480'>In</span> <span
  m='432600'>particular,</span> <span m='433410'>it</span> <span
  m='433700'>is</span> <span m='433890'>a</span> <span
  m='433950'>transposition</span> <span m='435420'>of</span> <span
  m='435570'>the</span> <span m='435660'>flow</span> <span
  m='435960'>graph</span> <span m='436860'>for</span> <span
  m='437010'>which,</span> <span m='437760'>if</span> <span
  m='438060'>you</span> <span m='438270'>imagine</span> <span
  m='438690'>this</span> <span m='438900'>flow</span> <span
  m='439140'>graph</span> <span m='439860'>being</span> <span
  m='440100'>transposed</span> <span m='440880'>so</span> <span
  m='441030'>that</span> <span m='441690'>the</span> <span
  m='441780'>direction</span> <span m='442200'>of</span> <span
  m='442290'>the</span> <span m='442440'>arrows</span> <span
  m='442800'>are</span> <span m='442890'>reversed</span> <span
  m='443430'>and</span> <span m='443550'>this</span> <span m='443730'>is</span>
  <span m='443850'>the</span> <span m='444000'>input,</span> <span
  m='444960'>then</span> <span m='445350'>it</span> <span
  m='445530'>corresponds</span> <span m='446400'>to</span> <span
  m='446520'>the</span> <span m='446640'>decimation</span> <span
  m='447300'>in</span> <span m='447420'>time</span> <span m='447780'>form</span>
  <span m='448080'>of</span> <span m='448170'>the</span> <span
  m='448320'>algorithm</span> <span m='449430'>for</span> <span
  m='449580'>which</span> <span m='449880'>the</span> <span
  m='450060'>input</span> <span m='450690'>is</span> <span m='450900'>in</span>
  <span m='451020'>normal</span> <span m='451440'>order</span> <span
  m='452370'>and</span> <span m='452730'>the</span> <span
  m='452940'>output</span> <span m='453750'>comes</span> <span
  m='454050'>out</span> <span m='454410'>in</span> <span m='454620'>bit</span>
  <span m='454830'>reversed</span> <span m='455310'>order.</span> <span
  m='456280'>And</span> <span m='457110'>that</span> <span m='457440'>is</span>
  <span m='457920'>the</span> <span m='458280'>flow</span> <span
  m='458580'>graph</span> <span m='459180'>that</span> <span m='460560'>I</span>
  <span m='460710'>have</span> <span m='461130'>indicated</span> <span
  m='461760'>here.</span> <span m='462720'>So</span> <span
  m='463230'>this</span> <span m='463560'>is</span> <span m='464010'>a</span>
  <span m='464190'>decimation</span> <span m='464850'>in</span> <span
  m='464940'>time</span> <span m='465300'>form</span> <span m='465630'>of</span>
  <span m='465720'>the</span> <span m='465870'>algorithm,</span> <span
  m='467320'>which</span> <span m='467550'>is</span> <span m='467730'>the</span>
  <span m='467850'>transposition</span> <span m='469050'>of</span> <span
  m='469770'>the</span> <span m='470490'>decimation</span> <span
  m='471340'>in</span> <span m='471540'>frequency</span> <span
  m='472710'>form</span> <span m='473070'>of</span> <span m='473160'>the</span>
  <span m='473340'>algorithm</span> <span m='474480'>that</span> <span
  m='474840'>we</span> <span m='474990'>just</span> <span
  m='475240'>looked</span> <span m='475510'>at.</span> </p><p><span
  m='478230'>All</span> <span m='478360'>right,</span> <span
  m='479130'>that</span> <span m='479460'>corresponds</span> <span
  m='480300'>then</span> <span m='480900'>to</span> <span m='482010'>two</span>
  <span m='482970'>possible</span> <span m='484470'>decimation</span> <span
  m='485320'>in</span> <span m='485500'>frequency</span> <span
  m='486210'>algorithms.</span> <span m='487560'>One</span> <span
  m='487980'>in</span> <span m='488160'>which</span> <span m='488700'>the</span>
  <span m='488880'>input</span> <span m='489180'>is</span> <span
  m='489300'>in</span> <span m='489390'>normal</span> <span
  m='489750'>order,</span> <span m='490060'>the</span> <span
  m='490110'>output</span> <span m='490450'>is</span> <span
  m='490550'>bit</span> <span m='490770'>reversed.</span> <span
  m='491850'>This</span> <span m='492090'>one</span> <span m='492300'>in</span>
  <span m='492420'>which</span> <span m='492720'>the</span> <span
  m='492870'>input</span> <span m='493160'>is</span> <span m='493290'>bit</span>
  <span m='493470'>reversed</span> <span m='494070'>and</span> <span
  m='494310'>the</span> <span m='494430'>output</span> <span
  m='494970'>is</span> <span m='495150'>in</span> <span m='495270'>normal</span>
  <span m='495630'>order.</span> <span m='497190'>We</span> <span
  m='497340'>can</span> <span m='497520'>also</span> <span
  m='497910'>rearrange</span> <span m='498540'>this</span> <span
  m='499020'>so</span> <span m='499260'>that</span> <span m='499770'>the</span>
  <span m='499950'>input</span> <span m='500520'>is</span> <span
  m='501000'>in</span> <span m='501150'>normal</span> <span
  m='501540'>order</span> <span m='502020'>and</span> <span
  m='502170'>the</span> <span m='502290'>output</span> <span
  m='502860'>is</span> <span m='503070'>in</span> <span m='503190'>normal</span>
  <span m='503550'>order.</span> </p><p><span m='504300'>And</span> <span
  m='504510'>the</span> <span m='504600'>flow</span> <span
  m='504870'>graph</span> <span m='505260'>that</span> <span
  m='505410'>results</span> <span m='506610'>when</span> <span
  m='506790'>we</span> <span m='506940'>implement</span> <span
  m='507420'>that</span> <span m='508110'>is</span> <span
  m='509220'>similar</span> <span m='510030'>to</span> <span
  m='510390'>the</span> <span m='510570'>corresponding</span> <span
  m='511350'>decimation</span> <span m='512220'>in</span> <span
  m='512370'>time</span> <span m='513570'>flow</span> <span
  m='513840'>graph.</span> <span m='515500'>In</span> <span
  m='515520'>fact,</span> <span m='516400'>it</span> <span m='516570'>is</span>
  <span m='517140'>a</span> <span m='517320'>transposition</span> <span
  m='518460'>of</span> <span m='518610'>that</span> <span m='518789'>flow</span>
  <span m='519059'>graph.</span> <span m='520530'>And</span> <span
  m='520860'>just</span> <span m='521250'>as</span> <span m='521640'>we</span>
  <span m='521789'>found</span> <span m='522120'>in</span> <span
  m='522179'>the</span> <span m='522270'>decimation</span> <span
  m='522929'>in</span> <span m='523020'>time</span> <span
  m='523710'>algorithm,</span> <span m='525300'>for</span> <span
  m='525480'>this</span> <span m='525720'>case,</span> <span
  m='526390'>although</span> <span m='526710'>the</span> <span
  m='526860'>input</span> <span m='527340'>is</span> <span
  m='527490'>sorted</span> <span m='528120'>in</span> <span
  m='528270'>normal</span> <span m='528660'>order</span> <span
  m='529440'>and</span> <span m='529560'>the</span> <span
  m='529680'>output</span> <span m='530340'>comes</span> <span
  m='530610'>out</span> <span m='530850'>in</span> <span
  m='530970'>normal</span> <span m='531330'>order,</span> <span
  m='532390'>the</span> <span m='532530'>indexing</span> <span
  m='533310'>is</span> <span m='533520'>generally</span> <span
  m='535230'>complicated</span> <span m='536190'>as</span> <span
  m='536400'>we</span> <span m='536520'>proceed</span> <span
  m='536970'>from</span> <span m='537150'>stage</span> <span
  m='537570'>to</span> <span m='537690'>stage.</span> </p><p><span
  m='538920'>And</span> <span m='539070'>furthermore,</span> <span
  m='540060'>it</span> <span m='540570'>does</span> <span m='540780'>not</span>
  <span m='541050'>correspond</span> <span m='541980'>to</span> <span
  m='542370'>an</span> <span m='542520'>in-place</span> <span
  m='542970'>computation,</span> <span m='544440'>because</span> <span
  m='544830'>of</span> <span m='544920'>the</span> <span m='545040'>fact</span>
  <span m='545820'>that</span> <span m='546390'>the</span> <span
  m='546870'>outputs</span> <span m='547650'>of</span> <span
  m='547920'>the</span> <span m='548040'>butterflies</span> <span
  m='549990'>are</span> <span m='550140'>no</span> <span
  m='550350'>longer</span> <span m='550830'>horizontally</span> <span
  m='551670'>adjacent</span> <span m='552600'>to</span> <span
  m='553290'>the</span> <span m='553560'>inputs</span> <span
  m='554040'>to</span> <span m='554160'>the</span> <span
  m='554280'>butterfly.</span> <span m='555810'>So</span> <span
  m='556080'>generally,</span> <span m='557160'>this</span> <span
  m='557370'>flow</span> <span m='557640'>graph</span> <span
  m='558120'>and</span> <span m='558300'>its</span> <span
  m='558450'>decimation</span> <span m='559050'>in</span> <span
  m='559170'>time</span> <span m='559500'>counterpart</span> <span
  m='560760'>are</span> <span m='561030'>not</span> <span
  m='562710'>practically</span> <span m='563700'>very</span> <span
  m='564060'>important.</span> <span m='566500'>A</span> <span
  m='566580'>final</span> <span m='567270'>rearrangement</span> <span
  m='568260'>of</span> <span m='568830'>the</span> <span m='569190'>flow</span>
  <span m='569550'>graph</span> <span m='570180'>is</span> <span
  m='570900'>the</span> <span m='572760'>rearrangement</span> <span
  m='574290'>which</span> <span m='574860'>permits</span> <span
  m='576390'>the</span> <span m='576960'>use</span> <span m='577530'>of</span>
  <span m='578040'>sequential</span> <span m='578730'>memory</span> <span
  m='579660'>rather</span> <span m='580080'>than</span> <span
  m='580590'>random</span> <span m='580980'>access</span> <span
  m='581490'>memory.</span> </p><p><span m='582570'>And</span> <span
  m='583170'>this,</span> <span m='583500'>then,</span> <span
  m='583980'>is</span> <span m='584730'>the</span> <span m='585030'>flow</span>
  <span m='585360'>graph</span> <span m='586350'>that</span> <span
  m='586560'>is</span> <span m='586740'>the</span> <span
  m='586830'>counterpart</span> <span m='587910'>to</span> <span
  m='588300'>the</span> <span m='588420'>flow</span> <span
  m='588690'>graph</span> <span m='589020'>that</span> <span
  m='589110'>we</span> <span m='589260'>discussed</span> <span
  m='589710'>last</span> <span m='590010'>time,</span> <span
  m='590410'>which</span> <span m='590490'>I</span> <span
  m='590590'>referred</span> <span m='591000'>to</span> <span
  m='591390'>as</span> <span m='592530'>the</span> <span
  m='592800'>Singleton</span> <span m='593430'>algorithm,</span> <span
  m='594150'>or</span> <span m='594390'>I</span> <span
  m='594510'>attributed</span> <span m='595260'>to</span> <span
  m='595380'>Singleton.</span> <span m='596460'>This</span> <span
  m='596700'>is</span> <span m='597240'>a</span> <span
  m='598410'>variation</span> <span m='599280'>of</span> <span
  m='599970'>that</span> <span m='600600'>type</span> <span m='600870'>of</span>
  <span m='600990'>algorithm,</span> <span m='602210'>in</span> <span
  m='602370'>which</span> <span m='602910'>now,</span> <span
  m='603360'>again,</span> <span m='603930'>we</span> <span
  m='604110'>recognize</span> <span m='605100'>that</span> <span
  m='605370'>the</span> <span m='605550'>indexing</span> <span
  m='607170'>is</span> <span m='607350'>identical</span> <span
  m='608460'>from</span> <span m='608670'>stage</span> <span
  m='609480'>to</span> <span m='609600'>stage.</span> <span
  m='612120'>The</span> <span m='612270'>input</span> <span m='612780'>is</span>
  <span m='613020'>in</span> <span m='613110'>normal</span> <span
  m='613560'>order.</span> </p><p><span m='614370'>And</span> <span
  m='614940'>the</span> <span m='615120'>output</span> <span
  m='615630'>comes</span> <span m='615930'>out</span> <span m='616200'>in</span>
  <span m='616350'>bit</span> <span m='616560'>reversed</span> <span
  m='617040'>order.</span> <span m='617950'>And</span> <span
  m='618060'>let</span> <span m='618240'>me</span> <span m='618390'>just</span>
  <span m='618960'>compare</span> <span m='619440'>this</span> <span
  m='620100'>for</span> <span m='620430'>you</span> <span m='621270'>with</span>
  <span m='621780'>the</span> <span m='621990'>corresponding</span> <span
  m='622800'>flow</span> <span m='623100'>graph</span> <span
  m='623700'>that</span> <span m='624180'>we</span> <span m='624450'>had</span>
  <span m='625470'>last</span> <span m='625860'>time,</span> <span
  m='627040'>which</span> <span m='627330'>I've</span> <span
  m='627510'>indicated</span> <span m='628110'>here.</span> <span
  m='629370'>That</span> <span m='629730'>has</span> <span m='630630'>the</span>
  <span m='630780'>input</span> <span m='631260'>in</span> <span
  m='631440'>bit</span> <span m='631620'>reversed</span> <span
  m='632040'>order,</span> <span m='632280'>the</span> <span
  m='632430'>output</span> <span m='632790'>in</span> <span
  m='632910'>normal</span> <span m='633300'>order.</span> <span
  m='634200'>In</span> <span m='634320'>fact,</span> <span m='634680'>the</span>
  <span m='634770'>transposition</span> <span m='635850'>of</span> <span
  m='636000'>this</span> <span m='636210'>flow</span> <span
  m='636480'>graph</span> <span m='637440'>is</span> <span m='638070'>the</span>
  <span m='638250'>decimation</span> <span m='638910'>in</span> <span
  m='639000'>frequency</span> <span m='640050'>form</span> <span
  m='640410'>of</span> <span m='640500'>the</span> <span
  m='640680'>algorithm,</span> <span m='641790'>for</span> <span
  m='641970'>which</span> <span m='642600'>the</span> <span
  m='642810'>input</span> <span m='643260'>is</span> <span m='643500'>in</span>
  <span m='643590'>normal</span> <span m='643980'>order,</span> <span
  m='644400'>and</span> <span m='644550'>the</span> <span
  m='644670'>output</span> <span m='645030'>is</span> <span m='645150'>in</span>
  <span m='645240'>bit</span> <span m='645420'>reversed</span> <span
  m='645870'>order.</span> </p><p><span m='647790'>All</span> <span
  m='647880'>right,</span> <span m='648060'>so</span> <span
  m='648240'>the</span> <span m='648360'>indexing</span> <span
  m='648990'>is</span> <span m='649200'>identical</span> <span
  m='649740'>from</span> <span m='649920'>stage</span> <span
  m='650340'>to</span> <span m='650460'>stage.</span> <span
  m='652020'>And</span> <span m='652830'>just</span> <span m='653190'>as</span>
  <span m='653340'>we</span> <span m='653490'>had</span> <span
  m='653730'>previously,</span> <span m='654930'>we</span> <span
  m='655200'>can</span> <span m='655620'>implement</span> <span
  m='656580'>this</span> <span m='656820'>algorithm</span> <span
  m='657960'>by</span> <span m='658260'>utilizing</span> <span
  m='659010'>sequential</span> <span m='659610'>memory</span> <span
  m='660270'>as</span> <span m='660450'>opposed</span> <span
  m='660810'>to</span> <span m='660930'>random</span> <span
  m='661290'>access</span> <span m='661740'>memory.</span> <span
  m='662610'>Although</span> <span m='663270'>the</span> <span
  m='663420'>organization</span> <span m='664200'>of</span> <span
  m='664290'>the</span> <span m='664410'>memory</span> <span
  m='665340'>for</span> <span m='665760'>the</span> <span
  m='665910'>decimation</span> <span m='666570'>in</span> <span
  m='666660'>frequency</span> <span m='667230'>form</span> <span
  m='667890'>of</span> <span m='668010'>the</span> <span
  m='668130'>Singleton</span> <span m='668610'>algorithm</span> <span
  m='670020'>is</span> <span m='670890'>somewhat</span> <span
  m='671400'>different</span> <span m='672060'>than</span> <span
  m='672210'>the</span> <span m='672330'>organization</span> <span
  m='673230'>of</span> <span m='673380'>the</span> <span
  m='673470'>memory</span> <span m='674220'>for</span> <span
  m='674340'>the</span> <span m='674460'>decimation</span> <span
  m='675120'>in</span> <span m='675240'>time</span> <span m='675630'>form</span>
  <span m='676100'>of</span> <span m='676200'>the</span> <span
  m='676320'>Singleton</span> <span m='676800'>algorithm.</span> </p><p><span
  m='678420'>In</span> <span m='678510'>particular,</span> <span
  m='679050'>last</span> <span m='679440'>time</span> <span
  m='680700'>when</span> <span m='680910'>we</span> <span
  m='681030'>discussed</span> <span m='681450'>the</span> <span
  m='681540'>decimation</span> <span m='682170'>in</span> <span
  m='682260'>time</span> <span m='682620'>algorithm,</span> <span
  m='683760'>we</span> <span m='684000'>had</span> <span m='684780'>four</span>
  <span m='685110'>memories,</span> <span m='685620'>as</span> <span
  m='685800'>we</span> <span m='685920'>will</span> <span m='686430'>this</span>
  <span m='686670'>time.</span> <span m='688680'>The</span> <span
  m='688800'>first</span> <span m='689130'>half</span> <span
  m='689400'>of</span> <span m='689490'>the</span> <span m='689580'>data</span>
  <span m='689910'>in</span> <span m='690030'>memory</span> <span
  m='690365'>A,</span> <span m='690700'>the</span> <span
  m='690720'>second</span> <span m='691050'>half</span> <span
  m='691320'>of</span> <span m='691380'>the</span> <span
  m='691500'>memory</span> <span m='691890'>in</span> <span
  m='692340'>memory</span> <span m='692740'>B.</span> <span m='693840'>We</span>
  <span m='694290'>went,</span> <span m='694740'>first</span> <span
  m='695040'>of</span> <span m='695160'>all,</span> <span
  m='695410'>through</span> <span m='695580'>all</span> <span
  m='695760'>of</span> <span m='695850'>memory</span> <span m='696420'>A,</span>
  <span m='697170'>then</span> <span m='697380'>through</span> <span
  m='697650'>all</span> <span m='697830'>of</span> <span
  m='697920'>memory</span> <span m='698310'>B,</span> <span
  m='699000'>storing</span> <span m='699480'>results</span> <span
  m='700980'>alternatively</span> <span m='701640'>in</span> <span
  m='702330'>memories</span> <span m='702750'>C</span> <span
  m='703050'>and</span> <span m='703200'>D.</span> </p><p><span
  m='704430'>In</span> <span m='704550'>this</span> <span
  m='704760'>case,</span> <span m='705400'>the</span> <span
  m='705420'>strategy</span> <span m='706710'>in</span> <span
  m='706950'>utilizing</span> <span m='707520'>the</span> <span
  m='707610'>memory</span> <span m='708180'>is</span> <span
  m='708270'>somewhat</span> <span m='708720'>different.</span> <span
  m='710440'>In</span> <span m='710530'>this</span> <span
  m='710740'>case,</span> <span m='711760'>we</span> <span
  m='712330'>store</span> <span m='713410'>the</span> <span
  m='714640'>first</span> <span m='715000'>half</span> <span
  m='715600'>of</span> <span m='716320'>the</span> <span m='716740'>data</span>
  <span m='717070'>points,</span> <span m='717580'>again,</span> <span
  m='717910'>in</span> <span m='718030'>memory</span> <span m='718540'>A,</span>
  <span m='719450'>the</span> <span m='719590'>second</span> <span
  m='719950'>half</span> <span m='720220'>of</span> <span m='720310'>the</span>
  <span m='720490'>data</span> <span m='720790'>points,</span> <span
  m='721150'>again,</span> <span m='721420'>in</span> <span
  m='721540'>memory</span> <span m='721960'>B.</span> <span
  m='722980'>But</span> <span m='723160'>notice</span> <span
  m='724030'>that</span> <span m='724240'>now</span> <span m='724810'>in</span>
  <span m='724930'>the</span> <span m='725020'>computation</span> <span
  m='727960'>utilizing</span> <span m='729490'>the</span> <span
  m='729610'>computation</span> <span m='730330'>for</span> <span
  m='730480'>this</span> <span m='730690'>point,</span> <span
  m='731470'>for</span> <span m='731680'>example,</span> <span
  m='732880'>we</span> <span m='733030'>use</span> <span m='733810'>the</span>
  <span m='733900'>first</span> <span m='734710'>output</span> <span
  m='735160'>point</span> <span m='735490'>from</span> <span
  m='735660'>memory</span> <span m='735965'>A</span> <span m='736930'>and</span>
  <span m='737230'>the</span> <span m='737350'>first</span> <span
  m='737680'>output</span> <span m='738040'>point</span> <span
  m='738340'>from</span> <span m='738490'>memory</span> <span
  m='738850'>b.</span> </p><p><span m='740140'>We</span> <span
  m='740260'>store</span> <span m='741280'>the</span> <span
  m='741370'>result</span> <span m='742030'>in</span> <span
  m='742930'>the</span> <span m='743020'>first</span> <span
  m='743950'>register</span> <span m='744520'>in</span> <span
  m='744640'>memory</span> <span m='745080'>C</span> <span m='746230'>and</span>
  <span m='746800'>in</span> <span m='746950'>the</span> <span
  m='747040'>second</span> <span m='747430'>register</span> <span
  m='747940'>in</span> <span m='748030'>memory</span> <span m='748390'>C.</span>
  <span m='750100'>Then,</span> <span m='750670'>to</span> <span
  m='750820'>compute</span> <span m='751480'>the</span> <span
  m='751600'>next</span> <span m='751870'>two</span> <span
  m='752050'>points,</span> <span m='752710'>we</span> <span
  m='753040'>take</span> <span m='753580'>the</span> <span
  m='753670'>next</span> <span m='754660'>point</span> <span
  m='754930'>from</span> <span m='755110'>memory</span> <span
  m='755550'>A</span> <span m='756386'>and</span> <span m='757180'>the</span>
  <span m='757270'>next</span> <span m='757540'>point</span> <span
  m='758350'>from</span> <span m='759190'>memory</span> <span
  m='759640'>B,</span> <span m='762550'>do</span> <span m='762730'>the</span>
  <span m='762850'>appropriate</span> <span m='763360'>addition</span> <span
  m='763720'>and</span> <span m='763840'>subtraction,</span> <span
  m='764570'>multiplication</span> <span m='765340'>by</span> <span
  m='765730'>powers</span> <span m='766180'>of</span> <span m='766270'>W,</span>
  <span m='767290'>and</span> <span m='767800'>store</span> <span
  m='768250'>those</span> <span m='768820'>in</span> <span m='769630'>the</span>
  <span m='770110'>next</span> <span m='770530'>two</span> <span
  m='771520'>registers</span> <span m='772360'>in</span> <span
  m='772510'>memory</span> <span m='772970'>C.</span> <span
  m='774130'>For</span> <span m='774310'>this</span> <span
  m='774490'>particular</span> <span m='774970'>example,</span> <span
  m='775420'>namely</span> <span m='775780'>n</span> <span
  m='776010'>equals</span> <span m='776270'>eight,</span> <span
  m='776680'>that</span> <span m='776860'>fills</span> <span
  m='777220'>up</span> <span m='777340'>memory</span> <span m='777760'>C.</span>
  </p><p><span m='778300'>And</span> <span m='778960'>we</span> <span
  m='779080'>proceed,</span> <span m='779470'>likewise,</span> <span
  m='780130'>accessing</span> <span m='780820'>the</span> <span
  m='780940'>input</span> <span m='781330'>data,</span> <span
  m='782500'>alternating</span> <span m='783190'>between</span> <span
  m='783850'>the</span> <span m='784030'>two</span> <span
  m='784300'>input</span> <span m='784660'>memories</span> <span
  m='785650'>and</span> <span m='785770'>storing</span> <span
  m='786310'>data</span> <span m='786850'>first</span> <span
  m='787390'>in</span> <span m='788320'>all</span> <span m='788710'>of</span>
  <span m='789160'>one</span> <span m='789340'>of</span> <span
  m='789430'>the</span> <span m='789580'>output</span> <span
  m='789940'>memories</span> <span m='790570'>and</span> <span
  m='790750'>then</span> <span m='791220'>in</span> <span m='791440'>all</span>
  <span m='791690'>of</span> <span m='791770'>the</span> <span
  m='791860'>second</span> <span m='792310'>of</span> <span
  m='792430'>the</span> <span m='792580'>output</span> <span
  m='792910'>memories.</span> <span m='794230'>And</span> <span
  m='794860'>then</span> <span m='795040'>we</span> <span
  m='795190'>proceed</span> <span m='796180'>in</span> <span
  m='796300'>that</span> <span m='796660'>fashion</span> <span
  m='797140'>from</span> <span m='797320'>stage</span> <span
  m='797710'>to</span> <span m='797830'>stage.</span> <span
  m='798670'>But</span> <span m='798940'>again,</span> <span
  m='799630'>one</span> <span m='799840'>of</span> <span m='799930'>the</span>
  <span m='800050'>important</span> <span m='800470'>aspects</span> <span
  m='801040'>is</span> <span m='801220'>that</span> <span m='801370'>it</span>
  <span m='801460'>utilizes</span> <span m='802150'>sequential</span> <span
  m='802750'>memory,</span> <span m='803770'>for</span> <span
  m='803980'>example,</span> <span m='804550'>disk</span> <span
  m='804910'>or</span> <span m='805030'>drum</span> <span m='805570'>or</span>
  <span m='805750'>tape</span> <span m='806740'>or</span> <span
  m='807100'>shift</span> <span m='807400'>register</span> <span
  m='807820'>memory.</span> </p><p><span m='812340'>OK,</span> <span
  m='813930'>so</span> <span m='815220'>this</span> <span m='815760'>then</span>
  <span m='816540'>is</span> <span m='816900'>essentially</span> <span
  m='819150'>a</span> <span m='821460'>picture</span> <span m='822090'>of</span>
  <span m='822780'>a</span> <span m='823230'>variety</span> <span
  m='824010'>of</span> <span m='824250'>the</span> <span
  m='824490'>algorithms,</span> <span m='825340'>which</span> <span
  m='825510'>can</span> <span m='825720'>be</span> <span m='825840'>used</span>
  <span m='826260'>for</span> <span m='826530'>the</span> <span
  m='826650'>computation</span> <span m='827670'>of</span> <span
  m='828690'>the</span> <span m='828810'>discrete</span> <span
  m='829230'>Fourier</span> <span m='829620'>transform,</span> <span
  m='830910'>some</span> <span m='831210'>of</span> <span
  m='831360'>which</span> <span m='831810'>were</span> <span
  m='832920'>derived</span> <span m='833430'>on</span> <span
  m='833550'>the</span> <span m='833640'>basis</span> <span m='834090'>of</span>
  <span m='834210'>a</span> <span m='834270'>decimation</span> <span
  m='834900'>in</span> <span m='834990'>time</span> <span
  m='835350'>argument.</span> <span m='836250'>Some</span> <span
  m='836510'>were</span> <span m='836640'>derived</span> <span
  m='837300'>on</span> <span m='837510'>the</span> <span m='837600'>basis</span>
  <span m='838170'>of</span> <span m='838620'>a</span> <span
  m='838860'>decimation</span> <span m='839840'>in</span> <span
  m='839950'>frequency</span> <span m='840720'>argument.</span> <span
  m='841740'>But</span> <span m='841950'>we</span> <span m='842130'>saw,</span>
  <span m='842490'>in</span> <span m='842640'>fact,</span> <span
  m='843420'>that</span> <span m='843660'>the</span> <span
  m='843780'>decimation</span> <span m='844390'>in</span> <span
  m='844440'>frequency</span> <span m='844950'>forms</span> <span
  m='845310'>of</span> <span m='845370'>the</span> <span
  m='845550'>algorithm</span> <span m='846540'>are,</span> <span
  m='846960'>in</span> <span m='847110'>terms</span> <span m='847530'>of</span>
  <span m='847770'>flow</span> <span m='848070'>graph</span> <span
  m='848580'>notation</span> <span m='849210'>or</span> <span
  m='849330'>interpretation,</span> <span m='850500'>transposes</span> <span
  m='851610'>of</span> <span m='852300'>the</span> <span
  m='852540'>decimation</span> <span m='853440'>in</span> <span
  m='853560'>time</span> <span m='853920'>form.</span> </p><p><span
  m='855750'>What</span> <span m='856050'>I</span> <span m='856170'>would</span>
  <span m='856320'>like</span> <span m='856890'>to</span> <span
  m='857640'>discuss</span> <span m='858510'>now</span> <span
  m='859680'>are</span> <span m='860340'>a</span> <span m='860730'>few</span>
  <span m='861270'>of</span> <span m='861600'>the</span> <span
  m='861810'>computational</span> <span m='862710'>issues</span> <span
  m='863490'>that</span> <span m='863820'>are</span> <span
  m='864060'>involved</span> <span m='864810'>in</span> <span
  m='865950'>the</span> <span m='866490'>implementing</span> <span
  m='867420'>the</span> <span m='867690'>fast</span> <span
  m='868020'>Fourier</span> <span m='868350'>transform</span> <span
  m='868980'>algorithm</span> <span m='870210'>and</span> <span
  m='871020'>return,</span> <span m='871590'>also,</span> <span
  m='872490'>to</span> <span m='873180'>a</span> <span m='873420'>brief</span>
  <span m='873750'>discussion</span> <span m='874620'>of</span> <span
  m='875490'>at</span> <span m='875580'>least</span> <span m='875850'>one</span>
  <span m='876060'>situation</span> <span m='876930'>in</span> <span
  m='877140'>which</span> <span m='877830'>there</span> <span
  m='878070'>is</span> <span m='878220'>a</span> <span
  m='878280'>preference</span> <span m='879120'>for</span> <span
  m='879870'>using</span> <span m='880830'>decimation</span> <span
  m='881520'>in</span> <span m='881640'>time</span> <span m='882120'>or</span>
  <span m='882390'>using</span> <span m='882750'>decimation</span> <span
  m='883350'>in</span> <span m='883440'>frequency.</span> <span
  m='885660'>After</span> <span m='886020'>we've</span> <span
  m='886230'>discussed</span> <span m='886740'>some</span> <span
  m='886980'>of</span> <span m='887040'>the</span> <span
  m='887130'>computational</span> <span m='887910'>considerations,</span> <span
  m='889080'>I</span> <span m='889770'>will</span> <span m='890460'>then</span>
  <span m='891060'>just</span> <span m='891330'>very</span> <span
  m='891630'>briefly</span> <span m='892770'>discuss</span> <span
  m='893520'>the</span> <span m='893610'>generalization</span> <span
  m='894840'>of</span> <span m='895730'>the</span> <span m='895830'>fast</span>
  <span m='896160'>Fourier</span> <span m='896490'>transform</span> <span
  m='897150'>algorithm</span> <span m='898310'>to</span> <span
  m='898500'>situations</span> <span m='899460'>in</span> <span
  m='899640'>which</span> <span m='900120'>the</span> <span
  m='900240'>number</span> <span m='900540'>of</span> <span
  m='900630'>data</span> <span m='900900'>points</span> <span
  m='901350'>is</span> <span m='901500'>not</span> <span m='901710'>a</span>
  <span m='901770'>power</span> <span m='902190'>of</span> <span
  m='902290'>two,</span> <span m='903120'>but</span> <span m='903480'>is</span>
  <span m='903960'>a</span> <span m='904230'>more</span> <span
  m='904530'>arbitrary</span> <span m='905220'>composite</span> <span
  m='905760'>number.</span> <span m='907260'>Well</span> <span
  m='907500'>first</span> <span m='907860'>of</span> <span
  m='907950'>all,</span> <span m='908370'>then,</span> <span
  m='908670'>let</span> <span m='908880'>me</span> <span
  m='909960'>introduce</span> <span m='911220'>a</span> <span
  m='911310'>few</span> <span m='911700'>of</span> <span m='911940'>the</span>
  <span m='912180'>computational</span> <span m='913200'>issues</span> <span
  m='914280'>that</span> <span m='914580'>I</span> <span m='914700'>would</span>
  <span m='914850'>like</span> <span m='915030'>to</span> <span
  m='915150'>draw</span> <span m='915390'>your</span> <span
  m='915570'>attention</span> <span m='916080'>to.</span> </p><p><span
  m='918280'>The</span> <span m='918380'>first</span> <span
  m='918690'>is--</span> <span m='919260'>and</span> <span
  m='919650'>it's</span> <span m='919830'>a</span> <span m='919890'>point</span>
  <span m='920280'>that</span> <span m='920820'>I</span> <span
  m='921210'>raised</span> <span m='921960'>in</span> <span
  m='923700'>the</span> <span m='923970'>first</span> <span
  m='924450'>lecture,</span> <span m='925140'>in</span> <span
  m='925260'>which</span> <span m='925470'>I</span> <span
  m='925890'>introduced</span> <span m='926370'>the</span> <span
  m='926460'>fast</span> <span m='926760'>Fourier</span> <span
  m='927060'>transform</span> <span m='927630'>algorithm--</span> <span
  m='928920'>that</span> <span m='929400'>whereas</span> <span
  m='930000'>our</span> <span m='930180'>discussion</span> <span
  m='930840'>has</span> <span m='931080'>been</span> <span
  m='931230'>directed</span> <span m='931710'>entirely</span> <span
  m='932730'>toward</span> <span m='933780'>the</span> <span
  m='933900'>computation</span> <span m='934980'>of</span> <span
  m='935190'>the</span> <span m='935280'>DFT,</span> <span m='936930'>it</span>
  <span m='937080'>applies</span> <span m='937740'>also,</span> <span
  m='938430'>in</span> <span m='938550'>a</span> <span m='938610'>very</span>
  <span m='938850'>straightforward</span> <span m='939630'>way,</span> <span
  m='940470'>to</span> <span m='940590'>a</span> <span
  m='940650'>computation</span> <span m='941700'>of</span> <span
  m='942480'>the</span> <span m='942660'>inverse</span> <span
  m='943140'>DFT.</span> <span m='945120'>In</span> <span
  m='945240'>particular,</span> <span m='946180'>we</span> <span
  m='946230'>know</span> <span m='946860'>that</span> <span
  m='947610'>the</span> <span m='947790'>inverse</span> <span
  m='948330'>discrete</span> <span m='948720'>Fourier</span> <span
  m='949110'>transform</span> <span m='949800'>relationship</span> <span
  m='951270'>is</span> <span m='951870'>given</span> <span m='952170'>by</span>
  <span m='952380'>1</span> <span m='952620'>over</span> <span
  m='952950'>N</span> <span m='953460'>times</span> <span m='953850'>the</span>
  <span m='953970'>sum</span> <span m='954420'>of</span> <span
  m='954510'>x</span> <span m='954750'>of</span> <span m='954870'>k</span> <span
  m='955185'>W</span> <span m='955500'>sub-N</span> <span m='955950'>to</span>
  <span m='956070'>the</span> <span m='956190'>minus</span> <span
  m='956610'>NK.</span> <span m='958200'>In</span> <span
  m='958320'>contrast</span> <span m='959490'>to</span> <span
  m='959640'>the</span> <span m='959730'>discrete</span> <span
  m='960150'>Fourier</span> <span m='960540'>transform--</span> <span
  m='962130'>that</span> <span m='962280'>is</span> <span m='962400'>the</span>
  <span m='962490'>forward</span> <span m='962910'>transform--</span> <span
  m='964240'>which</span> <span m='964560'>does</span> <span
  m='964770'>not</span> <span m='965010'>have</span> <span m='965220'>the</span>
  <span m='965340'>factor</span> <span m='965760'>of</span> <span
  m='965880'>1</span> <span m='966060'>over</span> <span m='966350'>N</span>
  <span m='967200'>and</span> <span m='967650'>involves</span> <span
  m='969840'>multiplication</span> <span m='970740'>by</span> <span
  m='970920'>W</span> <span m='971385'>sub-N</span> <span m='972100'>to</span>
  <span m='972210'>the</span> <span m='972300'>plus</span> <span
  m='972750'>NK,</span> <span m='973830'>rather</span> <span
  m='974080'>than</span> <span m='974310'>W</span> <span m='974670'>sub-N</span>
  <span m='975540'>to</span> <span m='975630'>the</span> <span
  m='975750'>minus</span> <span m='976170'>NK.</span> </p><p><span
  m='978630'>To</span> <span m='978780'>use</span> <span m='979470'>the</span>
  <span m='980970'>algorithms</span> <span m='982080'>that</span> <span
  m='982650'>we</span> <span m='982830'>have</span> <span m='983040'>just</span>
  <span m='983280'>been</span> <span m='983520'>discussing</span> <span
  m='985410'>for</span> <span m='985920'>the</span> <span
  m='986040'>computation</span> <span m='987090'>of</span> <span
  m='987690'>the</span> <span m='987840'>inverse</span> <span
  m='988470'>discrete</span> <span m='988890'>Fourier</span> <span
  m='989310'>transform,</span> <span m='990690'>the</span> <span
  m='990810'>modification</span> <span m='991800'>is</span> <span
  m='992160'>relatively</span> <span m='992700'>straightforward.</span> <span
  m='994150'>First</span> <span m='994350'>of</span> <span
  m='994470'>all,</span> <span m='994830'>it</span> <span
  m='994950'>involves</span> <span m='995400'>a</span> <span
  m='995460'>factor</span> <span m='995910'>of</span> <span m='996000'>1</span>
  <span m='996180'>over</span> <span m='996510'>N,</span> <span
  m='996930'>which</span> <span m='997260'>we</span> <span m='997380'>can</span>
  <span m='997530'>accommodate</span> <span m='998250'>in</span> <span
  m='998370'>a</span> <span m='998460'>number</span> <span m='998820'>of</span>
  <span m='998940'>ways.</span> <span m='1000420'>One</span> <span
  m='1000770'>is,</span> <span m='1001070'>of</span> <span
  m='1001160'>course,</span> <span m='1001490'>by</span> <span
  m='1001730'>shifting</span> <span m='1002930'>the</span> <span
  m='1003230'>output</span> <span m='1003920'>or</span> <span
  m='1004580'>by</span> <span m='1005210'>applying</span> <span
  m='1005720'>scaling</span> <span m='1006440'>at</span> <span
  m='1006590'>each</span> <span m='1006770'>stage</span> <span
  m='1007370'>of</span> <span m='1007520'>the</span> <span
  m='1007700'>FFT,</span> <span m='1008210'>for</span> <span
  m='1008390'>example.</span> </p><p><span m='1010190'>So</span> <span
  m='1011090'>this</span> <span m='1011690'>factor</span> <span
  m='1012080'>of</span> <span m='1012170'>1</span> <span m='1012340'>over</span>
  <span m='1012610'>N</span> <span m='1012860'>is</span> <span
  m='1013070'>easily</span> <span m='1013430'>accommodated.</span> <span
  m='1014930'>And</span> <span m='1015680'>the</span> <span
  m='1015860'>other</span> <span m='1018440'>difference</span> <span
  m='1019280'>is</span> <span m='1020300'>the</span> <span
  m='1020660'>inclusion</span> <span m='1021140'>of</span> <span
  m='1021230'>a</span> <span m='1021290'>minus</span> <span
  m='1021740'>sign</span> <span m='1022460'>in</span> <span
  m='1022850'>the</span> <span m='1023030'>exponent</span> <span
  m='1024000'>in</span> <span m='1024079'>powers</span> <span
  m='1024500'>of</span> <span m='1024560'>W</span> <span
  m='1025550'>rather</span> <span m='1025849'>than</span> <span
  m='1026030'>a</span> <span m='1026089'>plus</span> <span
  m='1026359'>sign</span> <span m='1026720'>for</span> <span
  m='1026839'>the</span> <span m='1026930'>forward</span> <span
  m='1027349'>transform.</span> <span m='1029060'>That</span> <span
  m='1029569'>means,</span> <span m='1030319'>in</span> <span
  m='1030470'>essence,</span> <span m='1031369'>that</span> <span
  m='1031700'>these</span> <span m='1032000'>coefficients</span> <span
  m='1034099'>are</span> <span m='1034250'>the</span> <span
  m='1034369'>complex</span> <span m='1034910'>conjugate</span> <span
  m='1036260'>of</span> <span m='1036920'>these</span> <span
  m='1037160'>coefficients.</span> </p><p><span m='1038450'>Because</span> <span
  m='1040834'>W</span> <span m='1041246'>sub-capital</span> <span
  m='1042170'>N</span> <span m='1042920'>is</span> <span m='1043280'>e</span>
  <span m='1043630'>of</span> <span m='1043700'>the</span> <span
  m='1043819'>J</span> <span m='1044680'>two</span> <span m='1044900'>pi</span>
  <span m='1045500'>over</span> <span m='1045770'>capital</span> <span
  m='1046310'>N.</span> <span m='1047720'>This</span> <span
  m='1047960'>minus</span> <span m='1048349'>sign</span> <span
  m='1048770'>represents</span> <span m='1049370'>a</span> <span
  m='1049430'>conjugation</span> <span m='1050930'>of</span> <span
  m='1051080'>W.</span> <span m='1052340'>And</span> <span m='1052850'>so</span>
  <span m='1053390'>one</span> <span m='1054140'>procedure</span> <span
  m='1054710'>that</span> <span m='1054860'>we</span> <span
  m='1055010'>can</span> <span m='1055160'>follow</span> <span
  m='1055730'>for</span> <span m='1056120'>implementing</span> <span
  m='1056870'>the</span> <span m='1057050'>inverse</span> <span
  m='1057560'>discrete</span> <span m='1057950'>Fourier</span> <span
  m='1058340'>transform</span> <span m='1059810'>using</span> <span
  m='1060320'>all</span> <span m='1060590'>of</span> <span
  m='1060710'>the</span> <span m='1060800'>flow</span> <span
  m='1061100'>graphs</span> <span m='1061640'>that</span> <span
  m='1061760'>we've</span> <span m='1061970'>talked</span> <span
  m='1062300'>about</span> <span m='1063220'>is</span> <span
  m='1063350'>simply</span> <span m='1064400'>conjugate</span> <span
  m='1066650'>the</span> <span m='1067250'>powers</span> <span
  m='1067700'>of</span> <span m='1067820'>W</span> <span m='1068660'>that</span>
  <span m='1068810'>are</span> <span m='1068960'>involved</span> <span
  m='1069380'>in</span> <span m='1069470'>the</span> <span
  m='1069560'>computation.</span> </p><p><span m='1071960'>An</span> <span
  m='1072050'>alternative</span> <span m='1073190'>procedure,</span> <span
  m='1073820'>which</span> <span m='1074090'>is</span> <span
  m='1074240'>basically</span> <span m='1074780'>equivalent,</span> <span
  m='1075860'>is</span> <span m='1076490'>to</span> <span m='1076610'>use</span>
  <span m='1078440'>the</span> <span m='1078590'>flow</span> <span
  m='1078830'>graphs</span> <span m='1079190'>as</span> <span
  m='1079460'>they</span> <span m='1079610'>stand,</span> <span
  m='1080990'>in</span> <span m='1081080'>which</span> <span
  m='1081350'>case</span> <span m='1082070'>the</span> <span
  m='1082250'>output</span> <span m='1082700'>data,</span> <span
  m='1084890'>which</span> <span m='1085100'>is</span> <span
  m='1085250'>obtained,</span> <span m='1086120'>is</span> <span
  m='1086780'>the</span> <span m='1086900'>desired</span> <span
  m='1087560'>result</span> <span m='1090290'>with</span> <span
  m='1090770'>little</span> <span m='1091070'>n</span> <span
  m='1091190'>replaced</span> <span m='1091640'>by</span> <span
  m='1091850'>minus</span> <span m='1092290'>n.</span> <span
  m='1093110'>So</span> <span m='1094160'>we</span> <span m='1094310'>can</span>
  <span m='1094580'>either</span> <span m='1095390'>compute</span> <span
  m='1095750'>the</span> <span m='1095870'>inverse</span> <span
  m='1096290'>DFT</span> <span m='1097910'>from</span> <span
  m='1098360'>an</span> <span m='1098510'>algorithm,</span> <span
  m='1099180'>which</span> <span m='1099410'>is</span> <span
  m='1099980'>aimed</span> <span m='1100340'>at</span> <span
  m='1100820'>the</span> <span m='1100940'>forward</span> <span
  m='1101420'>DFT,</span> <span m='1102650'>by</span> <span
  m='1102800'>conjugating</span> <span m='1103490'>the</span> <span
  m='1103580'>coefficients</span> <span m='1104840'>or</span> <span
  m='1105080'>equivalently</span> <span m='1106130'>by</span> <span
  m='1106790'>essentially</span> <span m='1107480'>flipping</span> <span
  m='1107960'>the</span> <span m='1108110'>output,</span> <span
  m='1109040'>modulo</span> <span m='1109730'>capital</span> <span
  m='1110270'>N.</span> <span m='1112100'>So</span> <span m='1113360'>all</span>
  <span m='1113570'>of</span> <span m='1113660'>the</span> <span
  m='1113810'>algorithms</span> <span m='1114410'>that</span> <span
  m='1114710'>we</span> <span m='1115340'>have</span> <span
  m='1115520'>talked</span> <span m='1115850'>about,</span> <span
  m='1116420'>then,</span> <span m='1117140'>relate</span> <span
  m='1117560'>in</span> <span m='1117680'>a</span> <span m='1117740'>very</span>
  <span m='1117980'>straightforward</span> <span m='1118670'>manner</span> <span
  m='1119390'>to</span> <span m='1119480'>the</span> <span
  m='1119570'>computation</span> <span m='1120470'>of</span> <span
  m='1120800'>the</span> <span m='1120950'>inverse</span> <span
  m='1121550'>discrete</span> <span m='1121940'>Fourier</span> <span
  m='1122360'>transform.</span> </p><p><span m='1124940'>The</span> <span
  m='1125030'>second</span> <span m='1125480'>issue</span> <span
  m='1126020'>is</span> <span m='1126470'>that</span> <span
  m='1126680'>as</span> <span m='1126860'>we've</span> <span
  m='1127040'>seen</span> <span m='1127850'>in</span> <span
  m='1128600'>essentially</span> <span m='1129200'>all</span> <span
  m='1129470'>of</span> <span m='1129590'>the</span> <span
  m='1129770'>algorithms</span> <span m='1130640'>of</span> <span
  m='1130790'>practical</span> <span m='1131390'>interest,</span> <span
  m='1133500'>they</span> <span m='1134100'>involve</span> <span
  m='1134940'>either</span> <span m='1135270'>bit</span> <span
  m='1135510'>reversal</span> <span m='1136500'>at</span> <span
  m='1136680'>the</span> <span m='1136860'>input</span> <span
  m='1137730'>to</span> <span m='1137820'>the</span> <span
  m='1137940'>flow</span> <span m='1138210'>graph</span> <span
  m='1138780'>or</span> <span m='1139110'>a</span> <span m='1139140'>bit</span>
  <span m='1139380'>reversal</span> <span m='1140130'>at</span> <span
  m='1140550'>the</span> <span m='1140730'>output</span> <span
  m='1141300'>of</span> <span m='1141420'>the</span> <span
  m='1141510'>flow</span> <span m='1141750'>graph.</span> <span
  m='1143496'>Bit</span> <span m='1143980'>reversal,</span> <span
  m='1144730'>again,</span> <span m='1145300'>is</span> <span
  m='1146140'>a</span> <span m='1146290'>relatively</span> <span
  m='1147100'>straightforward</span> <span m='1149490'>thing</span> <span
  m='1149820'>to</span> <span m='1150000'>implement.</span> <span
  m='1152120'>First</span> <span m='1152450'>of</span> <span
  m='1152600'>all,</span> <span m='1153780'>it</span> <span
  m='1154010'>is</span> <span m='1154460'>important</span> <span
  m='1154880'>to</span> <span m='1155030'>recognize</span> <span
  m='1156050'>that</span> <span m='1156200'>bit</span> <span
  m='1156410'>reversal</span> <span m='1157250'>is</span> <span
  m='1157880'>an</span> <span m='1158030'>in-place</span> <span
  m='1159140'>computation,</span> <span m='1160190'>if</span> <span
  m='1160520'>we</span> <span m='1160640'>think</span> <span
  m='1160850'>of</span> <span m='1160940'>it</span> <span m='1161000'>as</span>
  <span m='1161120'>a</span> <span m='1161180'>computation.</span> </p><p><span
  m='1162590'>In</span> <span m='1162710'>particular,</span> <span
  m='1164070'>suppose</span> <span m='1164750'>that</span> <span
  m='1165140'>we</span> <span m='1165350'>had</span> <span
  m='1166130'>the</span> <span m='1166490'>seven</span> <span
  m='1168020'>data</span> <span m='1168380'>indices</span> <span
  m='1169310'>zero</span> <span m='1169760'>through</span> <span
  m='1169970'>seven.</span> <span m='1171690'>And</span> <span
  m='1172220'>we</span> <span m='1172460'>want</span> <span
  m='1172970'>to</span> <span m='1173210'>rearrange</span> <span
  m='1173930'>this</span> <span m='1174170'>data</span> <span
  m='1175250'>so</span> <span m='1175550'>that</span> <span
  m='1176030'>the</span> <span m='1176180'>data</span> <span
  m='1176750'>is</span> <span m='1176990'>arranged</span> <span
  m='1177680'>in</span> <span m='1178070'>bit</span> <span
  m='1178310'>reversed</span> <span m='1178790'>order.</span> <span
  m='1180200'>Well</span> <span m='1181070'>that</span> <span
  m='1181280'>means</span> <span m='1181790'>that,</span> <span
  m='1183030'>of</span> <span m='1183260'>course,</span> <span
  m='1183500'>zero</span> <span m='1183800'>bit</span> <span
  m='1184100'>reversed</span> <span m='1184590'>is</span> <span
  m='1184710'>zero,</span> <span m='1185990'>one</span> <span
  m='1186320'>bit</span> <span m='1186530'>reversed</span> <span
  m='1186980'>is</span> <span m='1187190'>four.</span> <span
  m='1188300'>But</span> <span m='1188540'>of</span> <span
  m='1188660'>course,</span> <span m='1188990'>four</span> <span
  m='1189290'>bit</span> <span m='1189590'>reversed</span> <span
  m='1190040'>is</span> <span m='1190220'>one.</span> </p><p><span
  m='1192210'>So</span> <span m='1192890'>in</span> <span
  m='1193040'>fact,</span> <span m='1194180'>we</span> <span
  m='1194360'>would</span> <span m='1194600'>want</span> <span
  m='1194900'>to</span> <span m='1195050'>store</span> <span
  m='1196400'>data</span> <span m='1197480'>with</span> <span
  m='1198920'>whose</span> <span m='1199190'>index</span> <span
  m='1199790'>is</span> <span m='1199970'>one</span> <span m='1201140'>in</span>
  <span m='1201260'>storage</span> <span m='1201770'>location</span> <span
  m='1202430'>four.</span> <span m='1204350'>But</span> <span
  m='1204530'>we</span> <span m='1204710'>will</span> <span
  m='1204860'>also</span> <span m='1205220'>want</span> <span
  m='1205610'>to</span> <span m='1205760'>store</span> <span
  m='1206090'>data</span> <span m='1206630'>whose</span> <span
  m='1207230'>data</span> <span m='1207590'>index</span> <span
  m='1207920'>is</span> <span m='1208250'>four</span> <span
  m='1208880'>in</span> <span m='1209360'>storage</span> <span
  m='1209840'>location</span> <span m='1210440'>one.</span> <span
  m='1211700'>So</span> <span m='1212120'>in</span> <span
  m='1212300'>fact,</span> <span m='1213230'>implementing</span> <span
  m='1213830'>the</span> <span m='1213920'>bit</span> <span
  m='1214100'>reversal</span> <span m='1215240'>can</span> <span
  m='1216170'>be</span> <span m='1216440'>accomplished</span> <span
  m='1217280'>in</span> <span m='1217490'>place</span> <span
  m='1218480'>by</span> <span m='1219170'>essentially</span> <span
  m='1220220'>swapping</span> <span m='1221210'>these</span> <span
  m='1221480'>two</span> <span m='1221660'>pieces</span> <span
  m='1222110'>of</span> <span m='1222200'>data.</span> </p><p><span
  m='1223260'>Similarly</span> <span m='1223910'>of</span> <span
  m='1224030'>course,</span> <span m='1224810'>two</span> <span
  m='1225380'>bit</span> <span m='1225620'>reverses</span> <span
  m='1226130'>two.</span> <span m='1226440'>And</span> <span
  m='1226550'>so</span> <span m='1226700'>that</span> <span
  m='1226910'>wouldn't</span> <span m='1227180'>move.</span> <span
  m='1228080'>Three</span> <span m='1228350'>bit</span> <span
  m='1228560'>reversed</span> <span m='1229560'>is</span> <span
  m='1229780'>six.</span> <span m='1230310'>But</span> <span
  m='1230530'>six</span> <span m='1230830'>bit</span> <span
  m='1231050'>reversed</span> <span m='1231530'>is</span> <span
  m='1231710'>three.</span> </p><p><span m='1232760'>And</span> <span
  m='1232880'>so</span> <span m='1233270'>again,</span> <span
  m='1233870'>we</span> <span m='1234080'>can</span> <span
  m='1235010'>carry</span> <span m='1235400'>out</span> <span
  m='1235580'>that</span> <span m='1235760'>interchange</span> <span
  m='1236660'>as</span> <span m='1236840'>an</span> <span
  m='1236930'>in-place</span> <span m='1237380'>computation.</span> <span
  m='1238700'>So</span> <span m='1239210'>bit</span> <span
  m='1239420'>reversal,</span> <span m='1239990'>then,</span> <span
  m='1240950'>can</span> <span m='1241160'>be</span> <span
  m='1241340'>implemented</span> <span m='1242000'>in</span> <span
  m='1242210'>place.</span> <span m='1243140'>And</span> <span
  m='1243260'>consequently,</span> <span m='1245360'>as</span> <span
  m='1245810'>we</span> <span m='1246470'>restore</span> <span
  m='1247160'>the</span> <span m='1247280'>data</span> <span
  m='1247760'>in</span> <span m='1247940'>a</span> <span m='1248000'>bit</span>
  <span m='1248210'>reversed</span> <span m='1248660'>order,</span> <span
  m='1250220'>we</span> <span m='1250430'>don't</span> <span
  m='1250670'>require</span> <span m='1251180'>double</span> <span
  m='1251830'>the</span> <span m='1251930'>storage,</span> <span
  m='1252980'>since</span> <span m='1253430'>we</span> <span
  m='1253670'>can</span> <span m='1254030'>carry</span> <span
  m='1254420'>that</span> <span m='1254660'>out</span> <span
  m='1255050'>as</span> <span m='1255260'>an</span> <span
  m='1255350'>in-place</span> <span m='1255980'>operation.</span> <span
  m='1258080'>Second</span> <span m='1258440'>of</span> <span
  m='1258560'>all,</span> <span m='1259160'>to</span> <span
  m='1259550'>implement</span> <span m='1260260'>bit</span> <span
  m='1260480'>reversal,</span> <span m='1261350'>of</span> <span
  m='1261470'>course,</span> <span m='1262100'>to</span> <span
  m='1262340'>implement</span> <span m='1262625'>bit</span> <span
  m='1262910'>reversal</span> <span m='1263570'>in</span> <span
  m='1263720'>hardware,</span> <span m='1265250'>to</span> <span
  m='1265730'>obtain</span> <span m='1266030'>a</span> <span
  m='1266090'>bit</span> <span m='1266240'>reversed</span> <span
  m='1266630'>index</span> <span m='1267030'>and</span> <span
  m='1267140'>hardware</span> <span m='1267740'>is</span> <span
  m='1268340'>very</span> <span m='1268520'>simple.</span> </p><p><span
  m='1268910'>We</span> <span m='1269090'>just</span> <span
  m='1269270'>simply</span> <span m='1270410'>rearrange</span> <span
  m='1270920'>the</span> <span m='1271070'>order</span> <span
  m='1271550'>of</span> <span m='1271700'>the</span> <span
  m='1271860'>wires.</span> <span m='1273560'>To</span> <span
  m='1274370'>implement</span> <span m='1276090'>a</span> <span
  m='1276420'>bit</span> <span m='1276630'>reversed</span> <span
  m='1277170'>index</span> <span m='1277590'>register</span> <span
  m='1278430'>or</span> <span m='1278610'>an</span> <span
  m='1278700'>index</span> <span m='1280620'>algorithmically</span> <span
  m='1281940'>is</span> <span m='1282450'>a</span> <span
  m='1282510'>little</span> <span m='1282750'>more</span> <span
  m='1282960'>difficult.</span> <span m='1284190'>But</span> <span
  m='1284400'>in</span> <span m='1284550'>fact--</span> <span
  m='1285130'>and</span> <span m='1285290'>this</span> <span
  m='1285480'>is</span> <span m='1285600'>discussed</span> <span
  m='1286110'>in</span> <span m='1286200'>some</span> <span
  m='1286350'>more</span> <span m='1286530'>detail</span> <span
  m='1287130'>in</span> <span m='1287250'>the</span> <span
  m='1287340'>text--</span> <span m='1288570'>one</span> <span
  m='1288810'>of</span> <span m='1289110'>the</span> <span
  m='1289290'>most</span> <span m='1289980'>straightforward</span> <span
  m='1290700'>procedures,</span> <span m='1291450'>normally,</span> <span
  m='1292230'>is</span> <span m='1293190'>to</span> <span
  m='1294990'>implement</span> <span m='1295890'>a</span> <span
  m='1296160'>bit</span> <span m='1296370'>reversed</span> <span
  m='1296790'>counter</span> <span m='1298300'>so</span> <span
  m='1298440'>that</span> <span m='1299250'>as</span> <span
  m='1299430'>we</span> <span m='1299550'>proceed</span> <span
  m='1299940'>along</span> <span m='1301710'>with</span> <span
  m='1302370'>an</span> <span m='1302520'>index</span> <span
  m='1302910'>register</span> <span m='1303960'>accessing</span> <span
  m='1304620'>through</span> <span m='1305010'>an</span> <span
  m='1305130'>index</span> <span m='1305880'>in</span> <span
  m='1306000'>normal</span> <span m='1306390'>order,</span> <span
  m='1307170'>we</span> <span m='1307320'>can</span> <span
  m='1307500'>also</span> <span m='1308400'>run</span> <span
  m='1308970'>a</span> <span m='1309090'>counter</span> <span
  m='1309690'>that</span> <span m='1309870'>runs</span> <span
  m='1310170'>in</span> <span m='1310260'>bit</span> <span
  m='1310440'>reversed</span> <span m='1310920'>order</span> <span
  m='1311730'>and</span> <span m='1312090'>use,</span> <span
  m='1312510'>essentially,</span> <span m='1313110'>those</span> <span
  m='1313440'>two</span> <span m='1313800'>as</span> <span
  m='1313980'>index</span> <span m='1314370'>registers</span> <span
  m='1315510'>to</span> <span m='1315720'>tell</span> <span
  m='1315960'>us</span> <span m='1316110'>how</span> <span m='1316260'>to</span>
  <span m='1316350'>swap</span> <span m='1316740'>the</span> <span
  m='1316830'>data.</span> </p><p><span m='1317910'>So</span> <span
  m='1318130'>a</span> <span m='1318190'>bit</span> <span
  m='1318360'>reversal,</span> <span m='1319080'>in</span> <span
  m='1319230'>fact,</span> <span m='1319860'>algorithmically</span> <span
  m='1320760'>is</span> <span m='1320880'>relatively</span> <span
  m='1321390'>straightforward.</span> <span m='1323160'>It's</span> <span
  m='1323520'>an</span> <span m='1323610'>interesting</span> <span
  m='1324090'>point</span> <span m='1324450'>that</span> <span
  m='1325640'>it</span> <span m='1325890'>is</span> <span m='1326370'>a</span>
  <span m='1326430'>somewhat</span> <span m='1326910'>inefficient</span> <span
  m='1327600'>procedure,</span> <span m='1328290'>as</span> <span
  m='1328860'>you'll</span> <span m='1329040'>see</span> <span
  m='1330930'>if</span> <span m='1331620'>you</span> <span
  m='1332250'>try</span> <span m='1332670'>to</span> <span
  m='1332910'>program</span> <span m='1333630'>bit</span> <span
  m='1333840'>reversal.</span> <span m='1334860'>But</span> <span
  m='1335160'>algorithmically</span> <span m='1335640'>and</span> <span
  m='1336120'>conceptually,</span> <span m='1337020'>it's</span> <span
  m='1337320'>a</span> <span m='1337680'>fairly</span> <span
  m='1338010'>straightforward</span> <span m='1339120'>procedure</span> <span
  m='1339600'>to</span> <span m='1339750'>implement.</span> </p><p><span
  m='1341920'>A</span> <span m='1342020'>third</span> <span
  m='1343010'>computational</span> <span m='1343820'>issue,</span> <span
  m='1344420'>which</span> <span m='1344750'>I</span> <span
  m='1344840'>would</span> <span m='1344990'>like</span> <span
  m='1345230'>to</span> <span m='1345530'>draw</span> <span
  m='1345800'>your</span> <span m='1345950'>attention</span> <span
  m='1346460'>to</span> <span m='1346970'>is</span> <span m='1348110'>the</span>
  <span m='1349520'>question</span> <span m='1350390'>of</span> <span
  m='1351170'>obtaining</span> <span m='1351890'>the</span> <span
  m='1351980'>coefficients</span> <span m='1353480'>to</span> <span
  m='1353600'>use</span> <span m='1354050'>in</span> <span
  m='1354200'>the</span> <span m='1354380'>FFT</span> <span
  m='1354830'>computation.</span> <span m='1356360'>And</span> <span
  m='1356540'>there</span> <span m='1356720'>are</span> <span
  m='1356780'>basically</span> <span m='1357410'>two</span> <span
  m='1357980'>procedures</span> <span m='1359360'>that</span> <span
  m='1360080'>are</span> <span m='1360350'>commonly</span> <span
  m='1361550'>used.</span> <span m='1362600'>One,</span> <span
  m='1362810'>of</span> <span m='1362900'>course,</span> <span
  m='1363500'>is</span> <span m='1364160'>to</span> <span
  m='1364760'>store</span> <span m='1365720'>the</span> <span
  m='1366020'>coefficients</span> <span m='1367010'>in</span> <span
  m='1367100'>a</span> <span m='1367190'>table</span> <span
  m='1368270'>and</span> <span m='1368990'>then</span> <span
  m='1369170'>simply</span> <span m='1369560'>access</span> <span
  m='1370160'>them</span> <span m='1370730'>as</span> <span
  m='1371120'>they're</span> <span m='1371300'>needed.</span> </p><p><span
  m='1373220'>A</span> <span m='1373280'>second,</span> <span
  m='1373880'>which</span> <span m='1374270'>saves</span> <span
  m='1374660'>storage</span> <span m='1375290'>but</span> <span
  m='1375620'>requires</span> <span m='1376490'>some</span> <span
  m='1376730'>computational</span> <span m='1377540'>time,</span> <span
  m='1378560'>is</span> <span m='1379010'>to</span> <span
  m='1379250'>generate</span> <span m='1380090'>the</span> <span
  m='1380180'>coefficients</span> <span m='1381590'>recursively.</span> <span
  m='1383090'>That</span> <span m='1383270'>is</span> <span
  m='1383420'>essentially</span> <span m='1383930'>using</span> <span
  m='1384290'>an</span> <span m='1384380'>oscillator--</span> <span
  m='1384950'>programming</span> <span m='1385580'>an</span> <span
  m='1385670'>oscillator--</span> <span m='1386780'>and</span> <span
  m='1386900'>generating</span> <span m='1387530'>the</span> <span
  m='1387620'>coefficients</span> <span m='1388490'>as</span> <span
  m='1388760'>they're</span> <span m='1388900'>needed.</span> <span
  m='1390020'>Along</span> <span m='1390350'>those</span> <span
  m='1390590'>lines,</span> <span m='1391160'>it's</span> <span
  m='1391520'>interesting</span> <span m='1392030'>to</span> <span
  m='1392180'>observe</span> <span m='1392810'>that</span> <span
  m='1393650'>in</span> <span m='1393830'>both</span> <span
  m='1394190'>the</span> <span m='1394580'>decimation</span> <span
  m='1395420'>in</span> <span m='1395570'>time</span> <span
  m='1395870'>and</span> <span m='1395960'>decimation</span> <span
  m='1396600'>in</span> <span m='1396680'>frequency</span> <span
  m='1397190'>forms</span> <span m='1397580'>of</span> <span
  m='1397670'>the</span> <span m='1397820'>algorithm,</span> <span
  m='1399110'>as</span> <span m='1399350'>you</span> <span
  m='1399470'>proceed</span> <span m='1399980'>from</span> <span
  m='1400160'>stage</span> <span m='1400610'>to</span> <span
  m='1400730'>stage,</span> <span m='1402560'>the</span> <span
  m='1403040'>powers</span> <span m='1403760'>of</span> <span
  m='1403910'>W</span> <span m='1404780'>that</span> <span
  m='1404990'>are</span> <span m='1405140'>involved</span> <span
  m='1405950'>in</span> <span m='1406070'>the</span> <span
  m='1406160'>computation</span> <span m='1408170'>are</span> <span
  m='1409280'>powers</span> <span m='1410060'>of</span> <span
  m='1410650'>a</span> <span m='1410750'>basic</span> <span
  m='1411260'>power</span> <span m='1411650'>of</span> <span
  m='1411740'>W</span> <span m='1412780'>that</span> <span
  m='1412960'>doubles--</span> <span m='1414380'>or</span> <span
  m='1414740'>at</span> <span m='1414830'>least</span> <span
  m='1415040'>that</span> <span m='1415130'>changes--</span> <span
  m='1415970'>in</span> <span m='1416390'>each</span> <span
  m='1416780'>stage</span> <span m='1417510'>as</span> <span
  m='1417590'>you</span> <span m='1417680'>go</span> <span
  m='1417830'>through</span> <span m='1418010'>the</span> <span
  m='1418130'>computation.</span> </p><p><span m='1419300'>And</span> <span
  m='1419630'>this</span> <span m='1419870'>has</span> <span
  m='1420080'>implications</span> <span m='1420980'>as</span> <span
  m='1421880'>you</span> <span m='1422930'>think</span> <span
  m='1423380'>of</span> <span m='1424160'>either</span> <span
  m='1424460'>storing</span> <span m='1425060'>a</span> <span
  m='1425120'>table</span> <span m='1425450'>of</span> <span
  m='1425540'>coefficients</span> <span m='1426290'>and</span> <span
  m='1426440'>accessing</span> <span m='1427070'>them</span> <span
  m='1428360'>or</span> <span m='1429020'>as</span> <span m='1429470'>you</span>
  <span m='1429650'>think</span> <span m='1430010'>of</span> <span
  m='1430160'>generating</span> <span m='1430970'>the</span> <span
  m='1431090'>coefficients</span> <span m='1431870'>recursively.</span> <span
  m='1433850'>The</span> <span m='1433970'>fact</span> <span
  m='1434540'>that</span> <span m='1435410'>the</span> <span
  m='1435710'>powers</span> <span m='1436190'>of</span> <span
  m='1436280'>W</span> <span m='1436850'>are</span> <span
  m='1437000'>related</span> <span m='1437480'>from</span> <span
  m='1437660'>stage</span> <span m='1438080'>to</span> <span
  m='1438170'>stage</span> <span m='1439010'>suggests</span> <span
  m='1439610'>some</span> <span m='1440090'>fairly</span> <span
  m='1440480'>efficient</span> <span m='1440900'>procedures</span> <span
  m='1441500'>for</span> <span m='1441650'>doing</span> <span
  m='1441980'>this.</span> <span m='1444140'>One</span> <span
  m='1444680'>additional</span> <span m='1445280'>consideration,</span> <span
  m='1446510'>though,</span> <span m='1450850'>in</span> <span
  m='1451490'>obtaining</span> <span m='1451970'>the</span> <span
  m='1452060'>coefficients</span> <span m='1453590'>is</span> <span
  m='1453860'>that</span> <span m='1458950'>in</span> <span
  m='1459080'>some</span> <span m='1459260'>of</span> <span
  m='1459320'>the</span> <span m='1459410'>forms</span> <span
  m='1459740'>of</span> <span m='1459800'>the</span> <span
  m='1460010'>FFT</span> <span m='1460490'>algorithm,</span> <span
  m='1461900'>the</span> <span m='1462290'>coefficients</span> <span
  m='1464300'>are</span> <span m='1464930'>naturally</span> <span
  m='1465620'>accessed</span> <span m='1467360'>in</span> <span
  m='1467770'>a</span> <span m='1467840'>normal</span> <span
  m='1468290'>order,</span> <span m='1469040'>whereas</span> <span
  m='1469700'>in</span> <span m='1469850'>some</span> <span
  m='1470090'>other</span> <span m='1470330'>forms,</span> <span
  m='1471380'>they</span> <span m='1471710'>are</span> <span
  m='1471900'>naturally</span> <span m='1472400'>accessed</span> <span
  m='1473030'>in</span> <span m='1473150'>a</span> <span m='1473210'>bit</span>
  <span m='1473420'>reversed</span> <span m='1473900'>order.</span> </p><p><span
  m='1475320'>For</span> <span m='1475430'>example,</span> <span
  m='1476880'>if</span> <span m='1477320'>we</span> <span
  m='1477740'>think</span> <span m='1478190'>of</span> <span
  m='1479360'>the</span> <span m='1479570'>decimation</span> <span
  m='1480320'>in</span> <span m='1480430'>frequency</span> <span
  m='1481250'>form</span> <span m='1481790'>of</span> <span
  m='1481940'>the</span> <span m='1482090'>algorithm,</span> <span
  m='1484560'>here</span> <span m='1484880'>is</span> <span
  m='1485060'>the</span> <span m='1485150'>decimation</span> <span
  m='1485750'>in</span> <span m='1485840'>frequency</span> <span
  m='1486380'>form</span> <span m='1486740'>of</span> <span
  m='1486830'>the</span> <span m='1486980'>algorithm</span> <span
  m='1487910'>with</span> <span m='1488090'>the</span> <span
  m='1488210'>input</span> <span m='1488570'>in</span> <span
  m='1488660'>normal</span> <span m='1489050'>order</span> <span
  m='1489380'>and</span> <span m='1489500'>the</span> <span
  m='1489620'>output</span> <span m='1489950'>in</span> <span
  m='1490040'>bit</span> <span m='1490250'>reversed</span> <span
  m='1490730'>order.</span> <span m='1492480'>Notice</span> <span
  m='1493160'>that</span> <span m='1493970'>the</span> <span
  m='1494210'>powers</span> <span m='1494690'>of</span> <span
  m='1494780'>W</span> <span m='1495650'>that</span> <span m='1495830'>we</span>
  <span m='1496010'>have</span> <span m='1496370'>here</span> <span
  m='1497540'>occur</span> <span m='1498410'>in</span> <span
  m='1499160'>what</span> <span m='1499430'>looks</span> <span
  m='1499790'>like</span> <span m='1500570'>normal</span> <span
  m='1500960'>order.</span> <span m='1501440'>At</span> <span
  m='1501500'>least</span> <span m='1501740'>these</span> <span
  m='1501920'>powers</span> <span m='1502580'>are</span> <span
  m='1502760'>in</span> <span m='1502880'>normal</span> <span
  m='1503240'>order.</span> </p><p><span m='1507830'>And</span> <span
  m='1507950'>this</span> <span m='1508160'>is</span> <span
  m='1509000'>normal</span> <span m='1509600'>input</span> <span
  m='1510410'>order,</span> <span m='1511040'>bit</span> <span
  m='1511280'>reversed</span> <span m='1511700'>output</span> <span
  m='1512120'>order.</span> <span m='1513440'>Whereas</span> <span
  m='1514340'>if</span> <span m='1514910'>we</span> <span
  m='1515600'>took,</span> <span m='1516060'>let's</span> <span
  m='1516230'>say,</span> <span m='1516590'>the</span> <span
  m='1516770'>decimation</span> <span m='1517690'>in</span> <span
  m='1517850'>time</span> <span m='1518630'>form</span> <span
  m='1518960'>of</span> <span m='1519050'>the</span> <span
  m='1519200'>algorithm--</span> <span m='1520910'>where</span> <span
  m='1522170'>we</span> <span m='1522410'>have</span> <span
  m='1523430'>normally</span> <span m='1523940'>ordered</span> <span
  m='1524480'>input</span> <span m='1525470'>and</span> <span
  m='1525650'>bit</span> <span m='1525860'>reversed</span> <span
  m='1526310'>output--</span> <span m='1527240'>in</span> <span
  m='1527330'>that</span> <span m='1527570'>case,</span> <span
  m='1528170'>if</span> <span m='1528410'>you</span> <span
  m='1528530'>look</span> <span m='1528950'>at</span> <span
  m='1530060'>these</span> <span m='1530810'>powers</span> <span
  m='1531350'>of</span> <span m='1531500'>W,</span> <span
  m='1532460'>they're</span> <span m='1532640'>not</span> <span
  m='1533000'>in</span> <span m='1533180'>normal</span> <span
  m='1533540'>order.</span> <span m='1533960'>In</span> <span
  m='1534080'>fact,</span> <span m='1534710'>what</span> <span
  m='1534890'>they're</span> <span m='1535100'>in</span> <span
  m='1535340'>is</span> <span m='1535520'>bit</span> <span
  m='1535700'>reversed</span> <span m='1536150'>order.</span> </p><p><span
  m='1537860'>So</span> <span m='1538310'>in</span> <span
  m='1538460'>fact,</span> <span m='1539000'>in</span> <span
  m='1539120'>addition</span> <span m='1539990'>to</span> <span
  m='1540380'>the</span> <span m='1540530'>consideration</span> <span
  m='1541490'>as</span> <span m='1541760'>to</span> <span
  m='1541910'>whether</span> <span m='1542840'>the</span> <span
  m='1543290'>input</span> <span m='1543920'>is</span> <span
  m='1544070'>bit</span> <span m='1544280'>reversed</span> <span
  m='1544850'>or</span> <span m='1545000'>the</span> <span
  m='1545150'>output</span> <span m='1545510'>is</span> <span
  m='1545630'>bit</span> <span m='1545840'>reversed,</span> <span
  m='1546980'>in</span> <span m='1547070'>some</span> <span
  m='1547340'>forms</span> <span m='1547730'>of</span> <span
  m='1547850'>the</span> <span m='1548000'>algorithm,</span> <span
  m='1549020'>the</span> <span m='1549230'>coefficients</span> <span
  m='1550850'>would</span> <span m='1551090'>tend</span> <span
  m='1551420'>to</span> <span m='1551570'>be</span> <span
  m='1551720'>stored</span> <span m='1552530'>in</span> <span
  m='1553250'>normal</span> <span m='1553670'>order,</span> <span
  m='1554300'>whereas</span> <span m='1554750'>in</span> <span
  m='1555020'>some</span> <span m='1555260'>other</span> <span
  m='1555470'>forms</span> <span m='1555860'>of</span> <span
  m='1555920'>the</span> <span m='1556100'>algorithm,</span> <span
  m='1557090'>the</span> <span m='1557180'>coefficients</span> <span
  m='1557990'>would</span> <span m='1558200'>tend</span> <span
  m='1558500'>to</span> <span m='1558620'>be</span> <span
  m='1558770'>stored</span> <span m='1559400'>in</span> <span
  m='1559880'>a</span> <span m='1560090'>bit</span> <span
  m='1560300'>reversed</span> <span m='1560780'>order.</span> <span
  m='1561620'>Or</span> <span m='1562220'>if</span> <span m='1562400'>we</span>
  <span m='1562520'>think</span> <span m='1562730'>about</span> <span
  m='1562940'>generating</span> <span m='1563540'>the</span> <span
  m='1563630'>coefficients,</span> <span m='1564860'>clearly</span> <span
  m='1565790'>it</span> <span m='1566510'>is</span> <span
  m='1567230'>simpler</span> <span m='1568400'>to</span> <span
  m='1568520'>think</span> <span m='1568850'>of</span> <span
  m='1568970'>generating</span> <span m='1570140'>coefficients</span> <span
  m='1571100'>in</span> <span m='1571250'>normal</span> <span
  m='1571640'>order</span> <span m='1572390'>than</span> <span
  m='1572540'>it</span> <span m='1572630'>is</span> <span m='1572840'>to</span>
  <span m='1572960'>think</span> <span m='1573200'>of</span> <span
  m='1573320'>them</span> <span m='1574130'>as</span> <span
  m='1574280'>being</span> <span m='1574520'>generated</span> <span
  m='1575090'>in bit</span> <span m='1575390'>reversed</span> <span
  m='1575870'>order.</span> <span m='1577740'>Now</span> <span
  m='1578790'>with</span> <span m='1579300'>regard</span> <span
  m='1579960'>to</span> <span m='1580470'>the</span> <span
  m='1580590'>question</span> <span m='1581280'>of</span> <span
  m='1582210'>the</span> <span m='1582630'>input</span> <span
  m='1583080'>and</span> <span m='1583200'>output</span> <span
  m='1583920'>being</span> <span m='1584220'>bit</span> <span
  m='1584400'>reversed,</span> <span m='1585870'>one</span> <span
  m='1586650'>important</span> <span m='1587610'>area</span> <span
  m='1588480'>in</span> <span m='1588660'>which</span> <span
  m='1589590'>the</span> <span m='1589830'>computation</span> <span
  m='1590940'>of</span> <span m='1591270'>the</span> <span
  m='1591360'>DFT--</span> <span m='1591960'>in</span> <span
  m='1592050'>other</span> <span m='1592200'>words,</span> <span
  m='1592480'>the</span> <span m='1592590'>FFT</span> <span
  m='1593070'>algorithms--</span> <span m='1594300'>play</span> <span
  m='1594510'>a</span> <span m='1594570'>role</span> <span m='1595760'>is</span>
  <span m='1596190'>in</span> <span m='1596500'>implementing</span> <span
  m='1597240'>convolution</span> <span m='1598380'>or</span> <span
  m='1598740'>correlation.</span> </p><p><span m='1600540'>In</span> <span
  m='1600630'>that</span> <span m='1600840'>case,</span> <span
  m='1601830'>we</span> <span m='1602190'>compute</span> <span
  m='1602620'>a</span> <span m='1602700'>transform,</span> <span
  m='1604150'>multiply</span> <span m='1604830'>by</span> <span
  m='1605250'>something--</span> <span m='1605950'>in</span> <span
  m='1606050'>the</span> <span m='1606150'>case</span> <span
  m='1606390'>of</span> <span m='1606780'>a</span> <span
  m='1606840'>convolution,</span> <span m='1607660'>we</span> <span
  m='1607680'>multiply</span> <span m='1608580'>by</span> <span
  m='1609600'>the</span> <span m='1610780'>transform</span> <span
  m='1611610'>of</span> <span m='1612240'>the</span> <span
  m='1612390'>impulse</span> <span m='1612810'>response--</span> <span
  m='1614080'>and</span> <span m='1614180'>then</span> <span
  m='1614220'>implement</span> <span m='1614700'>an</span> <span
  m='1614820'>inverse</span> <span m='1615240'>transform.</span> <span
  m='1616680'>Well</span> <span m='1617100'>the</span> <span
  m='1617220'>fact</span> <span m='1617550'>that</span> <span
  m='1617700'>there</span> <span m='1617880'>are</span> <span
  m='1617910'>two</span> <span m='1618120'>transforms</span> <span
  m='1618900'>involved</span> <span m='1620010'>suggests</span> <span
  m='1620580'>the</span> <span m='1620700'>possibility</span> <span
  m='1621840'>that</span> <span m='1622170'>we</span> <span
  m='1622410'>can</span> <span m='1622830'>organize</span> <span
  m='1623490'>the</span> <span m='1623580'>computation</span> <span
  m='1625110'>in</span> <span m='1625230'>such</span> <span m='1625530'>a</span>
  <span m='1625620'>way</span> <span m='1626190'>that</span> <span
  m='1626340'>we</span> <span m='1626490'>completely</span> <span
  m='1627060'>avoid</span> <span m='1627420'>bit</span> <span
  m='1627630'>reversal.</span> <span m='1628980'>For</span> <span
  m='1629190'>example,</span> <span m='1630240'>we</span> <span
  m='1630390'>can</span> <span m='1630540'>choose</span> <span
  m='1630840'>an</span> <span m='1630930'>algorithm</span> <span
  m='1632370'>for</span> <span m='1632640'>the</span> <span
  m='1632760'>direct</span> <span m='1633120'>transform,</span> <span
  m='1634770'>which</span> <span m='1635040'>utilizes</span> <span
  m='1635730'>the</span> <span m='1635880'>input</span> <span
  m='1636270'>in</span> <span m='1636420'>normal</span> <span
  m='1636840'>order</span> <span m='1637650'>and</span> <span
  m='1637800'>generates</span> <span m='1638700'>the</span> <span
  m='1638890'>transform</span> <span m='1639660'>in bit</span> <span
  m='1640020'>reversed</span> <span m='1640530'>order.</span> </p><p><span
  m='1641730'>We</span> <span m='1641850'>then</span> <span
  m='1642270'>simply</span> <span m='1642750'>have</span> <span
  m='1643290'>the</span> <span m='1643480'>transform</span> <span
  m='1644070'>of</span> <span m='1644160'>the</span> <span
  m='1644280'>impulse</span> <span m='1644700'>response</span> <span
  m='1645270'>stored</span> <span m='1645840'>in</span> <span
  m='1646020'>bit</span> <span m='1646230'>reversed</span> <span
  m='1646680'>order,</span> <span m='1647490'>carry</span> <span
  m='1647880'>out</span> <span m='1648030'>the</span> <span
  m='1648150'>multiplication,</span> <span m='1650490'>and</span> <span
  m='1650610'>then</span> <span m='1650850'>choose</span> <span
  m='1651210'>a</span> <span m='1651270'>form</span> <span m='1651660'>of</span>
  <span m='1651750'>the</span> <span m='1651900'>algorithm</span> <span
  m='1652560'>for</span> <span m='1652710'>the</span> <span
  m='1652890'>inverse</span> <span m='1653340'>transform,</span> <span
  m='1654990'>which</span> <span m='1655410'>has</span> <span
  m='1656130'>bit</span> <span m='1656310'>reversed</span> <span
  m='1656840'>input</span> <span m='1657900'>and</span> <span
  m='1658590'>results</span> <span m='1659190'>in</span> <span
  m='1659610'>a</span> <span m='1659670'>normally</span> <span
  m='1660150'>ordered</span> <span m='1660450'>output.</span> <span
  m='1662200'>So</span> <span m='1662520'>in</span> <span
  m='1662640'>that</span> <span m='1662850'>case,</span> <span
  m='1663170'>what</span> <span m='1663490'>we</span> <span
  m='1663540'>would</span> <span m='1663690'>have</span> <span
  m='1663990'>is</span> <span m='1664080'>the</span> <span
  m='1664200'>forward</span> <span m='1664560'>transform,</span> <span
  m='1665550'>normally</span> <span m='1666030'>ordered</span> <span
  m='1666300'>data</span> <span m='1667230'>being</span> <span
  m='1667470'>transformed</span> <span m='1668080'>to</span> <span
  m='1668230'>bit</span> <span m='1668430'>reversed</span> <span
  m='1668850'>data.</span> <span m='1669990'>And</span> <span
  m='1670170'>then</span> <span m='1670470'>as</span> <span
  m='1670650'>the</span> <span m='1670770'>inverse</span> <span
  m='1671130'>transform,</span> <span m='1671730'>bit</span> <span
  m='1671970'>reversed</span> <span m='1672490'>input</span> <span
  m='1672930'>and</span> <span m='1673230'>normally</span> <span
  m='1673620'>ordered</span> <span m='1673920'>output.</span> </p><p><span
  m='1675280'>Well</span> <span m='1675660'>even</span> <span
  m='1675960'>given</span> <span m='1676290'>that,</span> <span
  m='1676800'>there</span> <span m='1677030'>are</span> <span
  m='1677070'>a</span> <span m='1677100'>number</span> <span
  m='1677430'>of</span> <span m='1677550'>options</span> <span
  m='1677970'>available.</span> <span m='1679510'>For</span> <span
  m='1679620'>example,</span> <span m='1681220'>we</span> <span
  m='1681300'>have</span> <span m='1682080'>an</span> <span
  m='1682200'>algorithm--</span> <span m='1683190'>the</span> <span
  m='1683310'>decimation</span> <span m='1683970'>in</span> <span
  m='1684060'>time</span> <span m='1684450'>algorithm--</span> <span
  m='1686590'>which</span> <span m='1687120'>is</span> <span
  m='1687900'>normally</span> <span m='1688440'>ordered</span> <span
  m='1689100'>input.</span> <span m='1692070'>I'm</span> <span
  m='1692250'>sorry,</span> <span m='1694740'>normally</span> <span
  m='1695220'>ordered</span> <span m='1695550'>input</span> <span
  m='1696570'>and</span> <span m='1697170'>bit</span> <span
  m='1697410'>reversed</span> <span m='1698550'>output,</span> <span
  m='1699330'>which</span> <span m='1699540'>we</span> <span
  m='1699690'>could</span> <span m='1699870'>use</span> <span
  m='1700140'>as</span> <span m='1700260'>our</span> <span
  m='1700380'>forward</span> <span m='1700830'>transform.</span> <span
  m='1702330'>Although</span> <span m='1702930'>as</span> <span
  m='1703590'>we</span> <span m='1703800'>just</span> <span
  m='1704340'>illustrated,</span> <span m='1705690'>it</span> <span
  m='1706230'>involves</span> <span m='1707200'>bit</span> <span
  m='1707460'>reversed</span> <span m='1708390'>coefficients.</span>
  </p><p><span m='1709660'>Well</span> <span m='1709860'>we</span> <span
  m='1710010'>could</span> <span m='1710130'>think</span> <span
  m='1710520'>of</span> <span m='1710940'>storing</span> <span
  m='1711420'>the</span> <span m='1711540'>coefficients</span> <span
  m='1712350'>in</span> <span m='1712470'>bit</span> <span
  m='1712680'>reversed</span> <span m='1713130'>order</span> <span
  m='1714280'>and</span> <span m='1714300'>then</span> <span
  m='1714750'>using</span> <span m='1715230'>the</span> <span
  m='1715320'>companion</span> <span m='1716370'>decimation</span> <span
  m='1717210'>in</span> <span m='1717330'>time</span> <span
  m='1718290'>form</span> <span m='1718680'>of</span> <span
  m='1718770'>the</span> <span m='1718950'>algorithm,</span> <span
  m='1720540'>which</span> <span m='1720780'>has</span> <span
  m='1722540'>bit</span> <span m='1722820'>reversed</span> <span
  m='1723720'>input</span> <span m='1725010'>and</span> <span
  m='1725160'>normally</span> <span m='1725640'>ordered</span> <span
  m='1725970'>output,</span> <span m='1728580'>to</span> <span
  m='1729360'>achieve</span> <span m='1730020'>the</span> <span
  m='1730230'>inverse</span> <span m='1730710'>transform.</span> <span
  m='1731790'>However,</span> <span m='1732210'>in</span> <span
  m='1732300'>this</span> <span m='1732510'>case</span> <span
  m='1733140'>the</span> <span m='1733260'>coefficients</span> <span
  m='1734250'>are</span> <span m='1734640'>in</span> <span
  m='1734790'>normal</span> <span m='1735180'>order.</span> <span
  m='1736480'>So</span> <span m='1736770'>if</span> <span m='1736980'>we</span>
  <span m='1737130'>match</span> <span m='1737520'>up</span> <span
  m='1737670'>the</span> <span m='1737850'>algorithms</span> <span
  m='1738630'>that</span> <span m='1738930'>way,</span> <span
  m='1739920'>then</span> <span m='1740400'>we're</span> <span
  m='1740580'>faced</span> <span m='1740940'>with</span> <span
  m='1741060'>the</span> <span m='1741180'>problem</span> <span
  m='1741690'>that</span> <span m='1741840'>in</span> <span
  m='1741970'>the</span> <span m='1742050'>direct</span> <span
  m='1742410'>transform,</span> <span m='1743460'>the</span> <span
  m='1743550'>coefficients</span> <span m='1744540'>would</span> <span
  m='1744750'>be</span> <span m='1744870'>stored</span> <span
  m='1745830'>in</span> <span m='1745980'>bit</span> <span
  m='1746190'>reversed</span> <span m='1746670'>order,</span> <span
  m='1747450'>whereas</span> <span m='1747870'>in</span> <span
  m='1747990'>the</span> <span m='1748110'>inverse</span> <span
  m='1748500'>transform</span> <span m='1749520'>they</span> <span
  m='1749640'>would</span> <span m='1749820'>be</span> <span
  m='1749940'>stored</span> <span m='1750600'>in</span> <span
  m='1751320'>normal</span> <span m='1751710'>order.</span> </p><p><span
  m='1753030'>Well</span> <span m='1753270'>you</span> <span
  m='1753390'>can</span> <span m='1753570'>ask</span> <span
  m='1754290'>whether</span> <span m='1754950'>for</span> <span
  m='1755190'>the</span> <span m='1755310'>decimation</span> <span
  m='1755960'>of</span> <span m='1756030'>frequency</span> <span
  m='1756750'>form</span> <span m='1757110'>of</span> <span
  m='1757200'>the</span> <span m='1757350'>algorithm,</span> <span
  m='1759750'>we</span> <span m='1760440'>can</span> <span
  m='1760890'>avoid</span> <span m='1761340'>that.</span> <span
  m='1762360'>But</span> <span m='1762690'>in</span> <span
  m='1762810'>fact,</span> <span m='1763110'>the</span> <span
  m='1763200'>same</span> <span m='1763500'>problem</span> <span
  m='1763980'>arises</span> <span m='1764520'>there.</span> <span
  m='1764910'>If</span> <span m='1765120'>we</span> <span
  m='1765240'>have</span> <span m='1765420'>the</span> <span
  m='1765510'>decimation</span> <span m='1766320'>in</span> <span
  m='1766500'>time</span> <span m='1767010'>in</span> <span
  m='1767160'>frequency</span> <span m='1767670'>form</span> <span
  m='1767970'>of</span> <span m='1768040'>the</span> <span
  m='1768210'>algorithm</span> <span m='1768780'>with</span> <span
  m='1768960'>normal</span> <span m='1769350'>input,</span> <span
  m='1770270'>bit</span> <span m='1770530'>reversed</span> <span
  m='1771000'>output,</span> <span m='1772240'>then</span> <span
  m='1772680'>the</span> <span m='1772800'>coefficients</span> <span
  m='1774390'>are</span> <span m='1774570'>stored</span> <span
  m='1775140'>in</span> <span m='1775320'>normal</span> <span
  m='1775740'>order.</span> </p><p><span m='1777360'>But</span> <span
  m='1777990'>for</span> <span m='1778320'>the</span> <span
  m='1778500'>inverse</span> <span m='1780210'>decimation</span> <span
  m='1780880'>in</span> <span m='1780960'>frequency</span> <span
  m='1781950'>transform</span> <span m='1783390'>with</span> <span
  m='1783900'>bit</span> <span m='1784170'>reversed</span> <span
  m='1784660'>input</span> <span m='1785640'>and</span> <span
  m='1785790'>normally</span> <span m='1786210'>ordered</span> <span
  m='1786560'>output,</span> <span m='1787440'>the</span> <span
  m='1787560'>coefficients</span> <span m='1788340'>would</span> <span
  m='1788490'>be</span> <span m='1788610'>stored</span> <span
  m='1789150'>in</span> <span m='1789300'>bit</span> <span
  m='1789510'>reversed</span> <span m='1789960'>order.</span> <span
  m='1792060'>The</span> <span m='1792150'>solution</span> <span
  m='1792930'>is</span> <span m='1793230'>to</span> <span
  m='1793380'>match</span> <span m='1793800'>up</span> <span
  m='1794460'>a</span> <span m='1794670'>decimation</span> <span
  m='1795550'>in</span> <span m='1795690'>time</span> <span
  m='1796050'>form</span> <span m='1796410'>of</span> <span
  m='1796500'>the</span> <span m='1796650'>algorithm</span> <span
  m='1797730'>with a</span> <span m='1798220'>decimation</span> <span
  m='1799090'>in</span> <span m='1799260'>frequency</span> <span
  m='1799800'>form</span> <span m='1800160'>of</span> <span
  m='1800250'>the</span> <span m='1800400'>algorithm</span> <span
  m='1801720'>so</span> <span m='1801990'>that,</span> <span
  m='1802650'>for</span> <span m='1802950'>example,</span> <span
  m='1805620'>we</span> <span m='1805800'>can</span> <span
  m='1806010'>choose</span> <span m='1806700'>as</span> <span
  m='1807660'>the</span> <span m='1807780'>forward</span> <span
  m='1808290'>transform</span> <span m='1811200'>the</span> <span
  m='1811770'>decimation</span> <span m='1815040'>in</span> <span
  m='1815220'>frequency</span> <span m='1815910'>form</span> <span
  m='1816270'>of</span> <span m='1816360'>the</span> <span
  m='1816510'>algorithm</span> <span m='1817350'>with</span> <span
  m='1817590'>the</span> <span m='1817740'>input</span> <span
  m='1818220'>in</span> <span m='1818400'>normal</span> <span
  m='1818790'>order,</span> <span m='1820060'>the</span> <span
  m='1820110'>output</span> <span m='1820530'>in bit</span> <span
  m='1820830'>reversed</span> <span m='1821310'>order,</span> <span
  m='1821880'>and</span> <span m='1821970'>the</span> <span
  m='1822060'>coefficients</span> <span m='1822810'>normally</span> <span
  m='1823320'>ordered,</span> <span m='1823980'>which</span> <span
  m='1824490'>is</span> <span m='1824700'>generally</span> <span
  m='1825180'>more</span> <span m='1825390'>convenient.</span> <span
  m='1827340'>And</span> <span m='1827490'>then</span> <span
  m='1827730'>choose</span> <span m='1828540'>for</span> <span
  m='1829320'>the</span> <span m='1829500'>inverse</span> <span
  m='1830010'>transform</span> <span m='1831630'>not</span> <span
  m='1831930'>the</span> <span m='1832050'>decimation</span> <span
  m='1832650'>in</span> <span m='1832740'>frequency</span> <span
  m='1833340'>algorithm,</span> <span m='1834360'>but</span> <span
  m='1834930'>the</span> <span m='1835080'>decimation</span> <span
  m='1835920'>in</span> <span m='1836100'>time</span> <span
  m='1836520'>algorithm,</span> <span m='1837690'>for</span> <span
  m='1837930'>which</span> <span m='1838440'>the</span> <span
  m='1838680'>input</span> <span m='1839400'>is</span> <span
  m='1839610'>now</span> <span m='1840420'>bit</span> <span
  m='1840630'>reversed,</span> <span m='1841980'>the</span> <span
  m='1842160'>output</span> <span m='1842820'>is</span> <span
  m='1843240'>in</span> <span m='1843450'>normal</span> <span
  m='1843870'>order,</span> <span m='1845310'>and</span> <span
  m='1845880'>the</span> <span m='1846000'>coefficients</span> <span
  m='1847050'>are</span> <span m='1847380'>also</span> <span
  m='1848010'>in</span> <span m='1848160'>normal</span> <span
  m='1848520'>order.</span> </p><p><span m='1849930'>So</span> <span
  m='1850530'>in</span> <span m='1850680'>fact,</span> <span
  m='1851010'>this</span> <span m='1851160'>suggests</span> <span
  m='1852480'>that</span> <span m='1852750'>if</span> <span
  m='1853320'>we</span> <span m='1853770'>are</span> <span
  m='1854280'>implementing</span> <span m='1855930'>a</span> <span
  m='1856860'>forward</span> <span m='1857220'>transform</span> <span
  m='1857970'>and</span> <span m='1858090'>an</span> <span
  m='1858210'>inverse</span> <span m='1858600'>transform,</span> <span
  m='1860070'>generally</span> <span m='1861030'>there</span> <span
  m='1861390'>are</span> <span m='1861660'>advantages</span> <span
  m='1862830'>to</span> <span m='1862980'>matching</span> <span
  m='1863460'>up</span> <span m='1864300'>the</span> <span
  m='1864480'>decimation</span> <span m='1865140'>in</span> <span
  m='1865260'>time</span> <span m='1866070'>form</span> <span
  m='1866550'>and</span> <span m='1866760'>the</span> <span
  m='1866850'>decimation</span> <span m='1867470'>in</span> <span
  m='1867570'>frequency</span> <span m='1868080'>form</span> <span
  m='1868890'>so</span> <span m='1869100'>that</span> <span
  m='1869520'>we</span> <span m='1869670'>have</span> <span
  m='1870060'>similarly</span> <span m='1870750'>accessed</span> <span
  m='1871260'>coefficients</span> <span m='1872190'>in</span> <span
  m='1872340'>both</span> <span m='1872580'>cases.</span> <span
  m='1874200'>Well</span> <span m='1874680'>there</span> <span
  m='1875100'>are,</span> <span m='1875460'>of</span> <span
  m='1875580'>course,</span> <span m='1876340'>a</span> <span
  m='1876900'>large</span> <span m='1877290'>variety</span> <span
  m='1878130'>of</span> <span m='1878460'>other</span> <span
  m='1878730'>computational</span> <span m='1879570'>issues</span> <span
  m='1880080'>to</span> <span m='1880200'>be</span> <span
  m='1880350'>considered</span> <span m='1881370'>in</span> <span
  m='1881670'>implementing</span> <span m='1882360'>the</span> <span
  m='1882930'>fast</span> <span m='1883230'>Fourier</span> <span
  m='1883590'>transform</span> <span m='1884190'>algorithms.</span> <span
  m='1885390'>Some of</span> <span m='1885720'>these</span> <span
  m='1886110'>are</span> <span m='1886410'>discussed</span> <span
  m='1887220'>in</span> <span m='1887340'>the</span> <span
  m='1887430'>text.</span> </p><p><span m='1888240'>Many</span> <span
  m='1888540'>of</span> <span m='1888720'>them</span> <span
  m='1889590'>you</span> <span m='1890040'>will</span> <span
  m='1890520'>discover</span> <span m='1891060'>for</span> <span
  m='1891510'>yourselves</span> <span m='1892290'>as</span> <span
  m='1892770'>you</span> <span m='1892950'>try</span> <span
  m='1893190'>to</span> <span m='1893310'>program</span> <span
  m='1894180'>the</span> <span m='1894360'>algorithm.</span> <span
  m='1895450'>But</span> <span m='1895500'>hopefully,</span> <span
  m='1896340'>this</span> <span m='1896550'>discussion</span> <span
  m='1898770'>provides</span> <span m='1899400'>at</span> <span
  m='1899520'>least</span> <span m='1900030'>some</span> <span
  m='1900420'>indication</span> <span m='1901470'>of</span> <span
  m='1902340'>what</span> <span m='1902730'>some</span> <span
  m='1903030'>of</span> <span m='1903120'>the</span> <span
  m='1903210'>strategies</span> <span m='1904050'>are</span> <span
  m='1904320'>and</span> <span m='1904440'>some</span> <span
  m='1904620'>of</span> <span m='1904680'>the</span> <span
  m='1904830'>issues</span> <span m='1905760'>are</span> <span
  m='1906480'>that</span> <span m='1906840'>are</span> <span
  m='1906960'>involved</span> <span m='1907560'>in</span> <span
  m='1907680'>computation</span> <span m='1908640'>of</span> <span
  m='1908940'>the</span> <span m='1909150'>FFT</span> <span
  m='1910470'>of</span> <span m='1910890'>the</span> <span
  m='1911010'>forms</span> <span m='1911370'>that</span> <span
  m='1911490'>we've</span> <span m='1911670'>been</span> <span
  m='1911790'>talking</span> <span m='1912240'>about.</span> <span
  m='1913790'>Now</span> <span m='1915670'>all</span> <span
  m='1915910'>of</span> <span m='1916000'>this</span> <span
  m='1916180'>discussion</span> <span m='1917440'>has</span> <span
  m='1917650'>been</span> <span m='1917830'>related</span> <span
  m='1918730'>to</span> <span m='1919540'>the</span> <span
  m='1919660'>computation</span> <span m='1920710'>of</span> <span
  m='1921610'>the</span> <span m='1921730'>discrete</span> <span
  m='1922090'>Fourier</span> <span m='1922490'>transform</span> <span
  m='1923530'>when</span> <span m='1923680'>the</span> <span
  m='1923770'>number</span> <span m='1924040'>of</span> <span
  m='1924130'>data</span> <span m='1924430'>points</span> <span
  m='1925180'>is</span> <span m='1925330'>a</span> <span
  m='1925360'>power</span> <span m='1925780'>of</span> <span
  m='1925870'>two.</span> </p><p><span m='1926770'>And</span> <span
  m='1927490'>these</span> <span m='1927850'>algorithms</span> <span
  m='1928510'>are</span> <span m='1928600'>referred</span> <span
  m='1928990'>to</span> <span m='1929440'>as</span> <span m='1929770'>the</span>
  <span m='1929910'>radix</span> <span m='1930330'>two</span> <span
  m='1930640'>forms</span> <span m='1931420'>of</span> <span
  m='1931690'>the</span> <span m='1931890'>FFT</span> <span
  m='1932370'>algorithm.</span> <span m='1933850'>As</span> <span
  m='1934000'>I</span> <span m='1934120'>indicated</span> <span
  m='1934810'>in</span> <span m='1934960'>the</span> <span
  m='1935050'>first</span> <span m='1935380'>lecture,</span> <span
  m='1935980'>in</span> <span m='1936130'>which</span> <span
  m='1936400'>we</span> <span m='1936670'>discussed</span> <span
  m='1937150'>the</span> <span m='1937390'>FFT,</span> <span
  m='1938900'>the</span> <span m='1939190'>FFT,</span> <span
  m='1939700'>in</span> <span m='1939790'>fact,</span> <span
  m='1940750'>is</span> <span m='1940900'>more</span> <span
  m='1941140'>general</span> <span m='1941860'>in</span> <span
  m='1942100'>that</span> <span m='1943300'>it</span> <span
  m='1943930'>generally</span> <span m='1944530'>applies</span> <span
  m='1945520'>when</span> <span m='1945940'>N</span> <span m='1946390'>is</span>
  <span m='1947710'>a</span> <span m='1947950'>highly</span> <span
  m='1948310'>composite</span> <span m='1948970'>number.</span> <span
  m='1949360'>We</span> <span m='1949540'>chose</span> <span
  m='1950340'>it</span> <span m='1950530'>to</span> <span m='1950680'>be</span>
  <span m='1950860'>composed</span> <span m='1951370'>of</span> <span
  m='1951430'>powers</span> <span m='1951910'>of</span> <span
  m='1952000'>two.</span> </p><p><span m='1952780'>But</span> <span
  m='1952960'>in</span> <span m='1953050'>fact,</span> <span
  m='1953410'>there</span> <span m='1953710'>are</span> <span
  m='1953890'>a</span> <span m='1953920'>variety</span> <span
  m='1954550'>of</span> <span m='1954670'>other</span> <span
  m='1955840'>forms</span> <span m='1956500'>of</span> <span
  m='1957010'>the</span> <span m='1957415'>FFT</span> <span
  m='1957700'>algorithm</span> <span m='1958360'>for</span> <span
  m='1958690'>different</span> <span m='1959080'>radices.</span> <span
  m='1960350'>And</span> <span m='1960580'>in</span> <span
  m='1960700'>some</span> <span m='1960970'>cases,</span> <span
  m='1961840'>there</span> <span m='1962260'>are</span> <span
  m='1962500'>some</span> <span m='1962740'>advantages</span> <span
  m='1963730'>to</span> <span m='1963880'>be</span> <span
  m='1964030'>found</span> <span m='1965020'>in</span> <span
  m='1965620'>using</span> <span m='1966010'>not</span> <span
  m='1966220'>a</span> <span m='1966280'>power</span> <span
  m='1966640'>of</span> <span m='1966730'>two</span> <span
  m='1966970'>algorithm,</span> <span m='1967690'>but</span> <span
  m='1968500'>a</span> <span m='1968920'>different</span> <span
  m='1969340'>algorithm.</span> <span m='1971290'>On</span> <span
  m='1971410'>the</span> <span m='1971530'>other</span> <span
  m='1971740'>hand,</span> <span m='1972260'>in</span> <span
  m='1972340'>many</span> <span m='1972580'>situations,</span> <span
  m='1973390'>the</span> <span m='1973510'>disadvantages</span> <span
  m='1974410'>of</span> <span m='1974500'>that</span> <span
  m='1974920'>outweigh</span> <span m='1975340'>the</span> <span
  m='1975490'>advantages.</span> </p><p><span m='1976810'>However,</span> <span
  m='1977350'>what</span> <span m='1977530'>I</span> <span
  m='1977620'>would</span> <span m='1977740'>like</span> <span
  m='1977980'>to</span> <span m='1978100'>do</span> <span m='1978580'>is</span>
  <span m='1978940'>conclude</span> <span m='1979420'>the</span> <span
  m='1979540'>discussion</span> <span m='1980380'>of</span> <span
  m='1980770'>the</span> <span m='1980860'>fast</span> <span
  m='1981190'>Fourier</span> <span m='1981550'>transform</span> <span
  m='1982180'>algorithm</span> <span m='1983370'>by</span> <span
  m='1983560'>just</span> <span m='1983860'>very</span> <span
  m='1984160'>briefly</span> <span m='1987310'>outlining</span> <span
  m='1988600'>what</span> <span m='1989170'>the</span> <span
  m='1989890'>structure</span> <span m='1990970'>of</span> <span
  m='1991330'>the</span> <span m='1991510'>FFT</span> <span
  m='1992320'>algorithm</span> <span m='1993100'>is</span> <span
  m='1993400'>more</span> <span m='1993640'>generally.</span> <span
  m='1994900'>And</span> <span m='1995140'>again,</span> <span
  m='1995470'>in</span> <span m='1995590'>the</span> <span
  m='1995690'>text</span> <span m='1999040'>there</span> <span
  m='1999250'>are</span> <span m='1999460'>a</span> <span
  m='1999490'>number</span> <span m='1999940'>of</span> <span
  m='2000060'>examples</span> <span m='2001020'>of</span> <span
  m='2002560'>FFT</span> <span m='2003150'>algorithms</span> <span
  m='2004080'>for</span> <span m='2004350'>radices</span> <span
  m='2004920'>other</span> <span m='2005160'>than</span> <span
  m='2005340'>a</span> <span m='2005370'>power</span> <span
  m='2005790'>of</span> <span m='2005910'>two</span> <span
  m='2006390'>and</span> <span m='2006600'>a</span> <span
  m='2006630'>more</span> <span m='2006870'>complete</span> <span
  m='2007260'>discussion</span> <span m='2008350'>than</span> <span
  m='2009150'>I</span> <span m='2009300'>feel</span> <span
  m='2009630'>that</span> <span m='2010020'>is</span> <span
  m='2010200'>appropriate</span> <span m='2010710'>to</span> <span
  m='2010830'>go</span> <span m='2011040'>through</span> <span
  m='2011250'>right</span> <span m='2011490'>now.</span> <span
  m='2012400'>However,</span> <span m='2012660'>let</span> <span
  m='2012840'>me</span> <span m='2012990'>just</span> <span
  m='2013380'>outline</span> <span m='2014310'>what</span> <span
  m='2015000'>some</span> <span m='2015480'>of</span> <span
  m='2016200'>the</span> <span m='2016950'>issues</span> <span
  m='2017400'>are</span> <span m='2017940'>in</span> <span
  m='2018750'>discussing</span> <span m='2019740'>a</span> <span
  m='2020070'>more</span> <span m='2020280'>general</span> <span
  m='2021270'>radix</span> <span m='2022010'>FFT</span> <span
  m='2022530'>algorithm.</span> </p><p><span m='2024930'>Generally</span> <span
  m='2025830'>the</span> <span m='2026190'>computation</span> <span
  m='2027300'>of</span> <span m='2027840'>the</span> <span
  m='2027930'>discrete</span> <span m='2028290'>Fourier</span> <span
  m='2028620'>transform</span> <span m='2029310'>using</span> <span
  m='2029670'>this</span> <span m='2029820'>class</span> <span
  m='2030150'>of</span> <span m='2030270'>algorithms</span> <span
  m='2031830'>is</span> <span m='2032130'>directed</span> <span
  m='2032670'>toward</span> <span m='2032940'>capitalizing</span> <span
  m='2034080'>on</span> <span m='2034290'>the</span> <span
  m='2034380'>fact</span> <span m='2035430'>that</span> <span
  m='2035970'>the</span> <span m='2036270'>size</span> <span
  m='2036750'>transform</span> <span m='2037620'>to</span> <span
  m='2037770'>be</span> <span m='2037920'>implemented</span> <span
  m='2039120'>is</span> <span m='2039720'>a</span> <span
  m='2039780'>product</span> <span m='2040950'>of</span> <span
  m='2041700'>numbers.</span> <span m='2042840'>And</span> <span
  m='2043710'>it</span> <span m='2043830'>turns</span> <span
  m='2044220'>out</span> <span m='2044730'>that</span> <span
  m='2045150'>the</span> <span m='2045270'>more</span> <span
  m='2046320'>numbers--</span> <span m='2047880'>the</span> <span
  m='2047970'>more</span> <span m='2048420'>terms</span> <span
  m='2048900'>in</span> <span m='2048989'>the</span> <span
  m='2049130'>decomposition--</span> <span m='2050670'>the</span> <span
  m='2050790'>greater</span> <span m='2051179'>the</span> <span
  m='2051330'>efficiency</span> <span m='2052380'>that</span> <span
  m='2052560'>can</span> <span m='2052739'>be</span> <span
  m='2052889'>obtained</span> <span m='2053580'>in</span> <span
  m='2053969'>implementing</span> <span m='2054570'>the</span> <span
  m='2054760'>transform.</span> <span m='2056600'>In</span> <span
  m='2056670'>that</span> <span m='2056880'>case,</span> <span
  m='2057239'>generally</span> <span m='2057929'>one</span> <span
  m='2058170'>would</span> <span m='2058320'>think</span> <span
  m='2058679'>of</span> <span m='2059489'>these</span> <span
  m='2059820'>numbers</span> <span m='2060420'>as</span> <span
  m='2060600'>primes,</span> <span m='2061290'>since</span> <span
  m='2061679'>that</span> <span m='2062010'>is</span> <span
  m='2062790'>the</span> <span m='2062880'>biggest</span> <span
  m='2063179'>decomposition</span> <span m='2064020'>of</span> <span
  m='2064110'>any</span> <span m='2064290'>number</span> <span
  m='2064620'>that</span> <span m='2064710'>we</span> <span
  m='2064860'>can</span> <span m='2065010'>carry</span> <span
  m='2065429'>out.</span> </p><p><span m='2066030'>But</span> <span
  m='2066179'>in</span> <span m='2066300'>fact,</span> <span
  m='2067010'>for</span> <span m='2067170'>the</span> <span
  m='2067290'>derivation,</span> <span m='2068250'>it</span> <span
  m='2068570'>is</span> <span m='2069060'>not</span> <span m='2069300'>a</span>
  <span m='2069330'>requirement</span> <span m='2070469'>that</span> <span
  m='2070620'>the</span> <span m='2070710'>p's</span> <span
  m='2071370'>be</span> <span m='2071520'>primes.</span> <span
  m='2072960'>So</span> <span m='2073139'>let's</span> <span
  m='2073409'>think</span> <span m='2073650'>of</span> <span
  m='2073770'>N,</span> <span m='2074159'>then,</span> <span
  m='2074400'>as</span> <span m='2074520'>decomposed</span> <span
  m='2075239'>as</span> <span m='2075360'>a</span> <span
  m='2075420'>product</span> <span m='2076170'>of</span> <span
  m='2077219'>p1</span> <span m='2077670'>times</span> <span
  m='2077989'>p2,</span> <span m='2078469'>et</span> <span
  m='2078570'>cetera,</span> <span m='2079020'>through</span> <span
  m='2079270'>p</span> <span m='2079590'>sub-Nu,</span> <span
  m='2081900'>which</span> <span m='2082290'>we</span> <span
  m='2082500'>can</span> <span m='2082679'>alternatively</span> <span
  m='2083429'>write</span> <span m='2083969'>as</span> <span
  m='2084670'>p1</span> <span m='2085530'>times</span> <span
  m='2085980'>q1,</span> <span m='2087630'>where</span> <span
  m='2087870'>q1</span> <span m='2088530'>is</span> <span
  m='2088739'>then</span> <span m='2088889'>represented</span> <span
  m='2089670'>by</span> <span m='2090150'>the</span> <span
  m='2090270'>product</span> <span m='2090810'>of</span> <span
  m='2091650'>the</span> <span m='2092070'>remaining</span> <span
  m='2092670'>terms.</span> <span m='2094889'>And</span> <span
  m='2096510'>we</span> <span m='2096750'>can</span> <span
  m='2097080'>proceed,</span> <span m='2099420'>essentially,</span> <span
  m='2100260'>along</span> <span m='2100860'>a</span> <span
  m='2100950'>root</span> <span m='2101220'>similar</span> <span
  m='2101880'>to</span> <span m='2102900'>the</span> <span
  m='2103050'>decimation</span> <span m='2103770'>in</span> <span
  m='2103860'>time</span> <span m='2104400'>algorithms</span> <span
  m='2105450'>or</span> <span m='2106200'>along</span> <span
  m='2106530'>a</span> <span m='2106590'>root</span> <span
  m='2106830'>similar</span> <span m='2107310'>to</span> <span
  m='2107460'>the</span> <span m='2107550'>decimation</span> <span
  m='2108150'>in</span> <span m='2108210'>frequency</span> <span
  m='2108870'>algorithms.</span> </p><p><span m='2109890'>Let</span> <span
  m='2110040'>me</span> <span m='2110160'>just</span> <span
  m='2110400'>indicate</span> <span m='2110910'>the</span> <span
  m='2111000'>strategy</span> <span m='2112200'>paralleling</span> <span
  m='2113190'>the</span> <span m='2113460'>decimation</span> <span
  m='2114180'>in</span> <span m='2114300'>time</span> <span
  m='2115290'>form</span> <span m='2115830'>of</span> <span
  m='2115980'>the</span> <span m='2116130'>algorithm,</span> <span
  m='2116640'>as</span> <span m='2116790'>we</span> <span
  m='2116910'>discussed</span> <span m='2117370'>that</span> <span
  m='2117490'>for</span> <span m='2117690'>N,</span> <span m='2118080'>a</span>
  <span m='2118140'>power</span> <span m='2118560'>of</span> <span
  m='2118650'>two.</span> <span m='2120490'>In</span> <span
  m='2120610'>that</span> <span m='2120790'>case,</span> <span
  m='2121720'>we</span> <span m='2122380'>decomposed</span> <span
  m='2123760'>p1</span> <span m='2124360'>is</span> <span
  m='2124510'>equal</span> <span m='2124810'>to</span> <span
  m='2124930'>two,</span> <span m='2125320'>and</span> <span
  m='2125440'>q1</span> <span m='2125920'>is</span> <span
  m='2126070'>equal</span> <span m='2126310'>to</span> <span
  m='2126400'>N</span> <span m='2126610'>over</span> <span
  m='2126880'>two.</span> <span m='2128140'>And</span> <span
  m='2128710'>we</span> <span m='2128920'>decompose</span> <span
  m='2129820'>the</span> <span m='2129970'>original</span> <span
  m='2130360'>sequence</span> <span m='2131560'>into</span> <span
  m='2131800'>two</span> <span m='2132040'>sub-sequences,</span> <span
  m='2133840'>one</span> <span m='2134080'>consisting</span> <span
  m='2134620'>of</span> <span m='2134740'>the</span> <span
  m='2134890'>even</span> <span m='2135190'>numbered</span> <span
  m='2135520'>points,</span> <span m='2136000'>the</span> <span
  m='2136150'>other</span> <span m='2136360'>consisting</span> <span
  m='2137050'>of</span> <span m='2137200'>the</span> <span
  m='2137350'>odd</span> <span m='2137560'>numbered</span> <span
  m='2137920'>points.</span> </p><p><span m='2139180'>More</span> <span
  m='2139360'>generally,</span> <span m='2140140'>we</span> <span
  m='2140350'>would</span> <span m='2140470'>decompose</span> <span
  m='2141400'>the</span> <span m='2141520'>sequence</span> <span
  m='2143170'>into</span> <span m='2143770'>a</span> <span
  m='2143860'>set</span> <span m='2144130'>of</span> <span
  m='2144220'>sub-sequences</span> <span m='2146440'>consisting</span> <span
  m='2147430'>of</span> <span m='2147880'>every</span> <span
  m='2148480'>p1th</span> <span m='2149110'>point.</span> <span
  m='2151820'>So</span> <span m='2152300'>how</span> <span
  m='2152450'>many</span> <span m='2152660'>sequences</span> <span
  m='2153290'>are</span> <span m='2153470'>there?</span> <span
  m='2153870'>Well,</span> <span m='2154250'>there</span> <span
  m='2154550'>are</span> <span m='2154700'>p1</span> <span
  m='2155270'>sequences.</span> <span m='2156950'>And</span> <span
  m='2157100'>the</span> <span m='2157220'>length</span> <span
  m='2157550'>of</span> <span m='2157670'>each</span> <span
  m='2157850'>sequence</span> <span m='2158660'>is</span> <span
  m='2159240'>q1.</span> </p><p><span m='2160370'>For</span> <span
  m='2160550'>example,</span> <span m='2161310'>if</span> <span
  m='2161440'>p1</span> <span m='2161870'>was</span> <span
  m='2161990'>equal</span> <span m='2162290'>to</span> <span
  m='2162410'>two,</span> <span m='2162800'>and</span> <span
  m='2162890'>q1</span> <span m='2163340'>was</span> <span m='2163490'>N</span>
  <span m='2163640'>over</span> <span m='2163910'>two,</span> <span
  m='2165110'>this</span> <span m='2165320'>would</span> <span
  m='2165500'>be</span> <span m='2165740'>every</span> <span
  m='2166100'>other</span> <span m='2166370'>point.</span> <span
  m='2167440'>That's</span> <span m='2167660'>choosing</span> <span
  m='2168020'>the</span> <span m='2168110'>even</span> <span
  m='2168350'>numbered</span> <span m='2168620'>points</span> <span
  m='2168950'>and</span> <span m='2169040'>the</span> <span
  m='2169160'>odd</span> <span m='2169340'>numbered</span> <span
  m='2169700'>points.</span> <span m='2170750'>There</span> <span
  m='2170930'>would</span> <span m='2171080'>be</span> <span
  m='2171260'>two</span> <span m='2171830'>sub-sequences,</span> <span
  m='2173720'>each</span> <span m='2174200'>sub-sequence</span> <span
  m='2175040'>of</span> <span m='2175220'>length</span> <span
  m='2175580'>N</span> <span m='2175760'>over</span> <span
  m='2176010'>two.</span> </p><p><span m='2177820'>More</span> <span
  m='2177970'>generally,</span> <span m='2178540'>then,</span> <span
  m='2179530'>if</span> <span m='2179800'>we</span> <span
  m='2179980'>had,</span> <span m='2180490'>say,</span> <span
  m='2180970'>N</span> <span m='2181210'>equal</span> <span
  m='2181480'>to</span> <span m='2181600'>12,</span> <span
  m='2182920'>and</span> <span m='2183670'>p1</span> <span
  m='2184150'>equal</span> <span m='2184480'>to</span> <span
  m='2184630'>three,</span> <span m='2187420'>we</span> <span
  m='2187570'>would</span> <span m='2187690'>generate</span> <span
  m='2188830'>three</span> <span m='2189610'>sub-sequences,</span> <span
  m='2192220'>each</span> <span m='2192520'>consisting</span> <span
  m='2193090'>of</span> <span m='2193180'>four</span> <span
  m='2193510'>points</span> <span m='2195250'>chosen</span> <span
  m='2196090'>by</span> <span m='2196510'>selecting</span> <span
  m='2197380'>every</span> <span m='2198420'>p1th,</span> <span
  m='2198970'>or</span> <span m='2199180'>every</span> <span
  m='2199450'>third</span> <span m='2199780'>point.</span> <span
  m='2200590'>So</span> <span m='2201070'>one</span> <span
  m='2201360'>sub</span> <span m='2201630'>sequence,</span> <span
  m='2202180'>which</span> <span m='2202390'>I've</span> <span
  m='2202860'>denoted</span> <span m='2203320'>here</span> <span
  m='2203590'>by</span> <span m='2203890'>A,</span> <span
  m='2204700'>would</span> <span m='2204850'>be</span> <span
  m='2205000'>this</span> <span m='2205240'>point</span> <span
  m='2205640'>and</span> <span m='2205810'>this</span> <span
  m='2206020'>one</span> <span m='2206260'>and</span> <span
  m='2206380'>this</span> <span m='2206560'>one</span> <span
  m='2206800'>and</span> <span m='2206950'>that</span> <span
  m='2207220'>one.</span> <span m='2208520'>The</span> <span
  m='2208620'>second</span> <span m='2208840'>sub-sequence</span> <span
  m='2209740'>would</span> <span m='2209950'>be</span> <span
  m='2210100'>the</span> <span m='2210220'>sub-sequence</span> <span
  m='2210940'>B,</span> <span m='2212080'>which</span> <span
  m='2212860'>is</span> <span m='2213100'>comprised</span> <span
  m='2213640'>of</span> <span m='2213730'>this</span> <span
  m='2213940'>point,</span> <span m='2214300'>this,</span> <span
  m='2214705'>this,</span> <span m='2215110'>and</span> <span
  m='2215260'>that.</span> </p><p><span m='2216320'>And</span> <span
  m='2216400'>the</span> <span m='2216490'>third</span> <span
  m='2217060'>sub-sequence</span> <span m='2217840'>would</span> <span
  m='2218110'>be</span> <span m='2218880'>sub-sequence</span> <span
  m='2219640'>C,</span> <span m='2220000'>which</span> <span
  m='2220210'>is</span> <span m='2220330'>this</span> <span
  m='2220540'>point,</span> <span m='2220870'>this</span> <span
  m='2221050'>point,</span> <span m='2221540'>that</span> <span
  m='2221680'>point,</span> <span m='2222220'>and</span> <span
  m='2222370'>that</span> <span m='2222580'>point.</span> <span
  m='2224830'>All</span> <span m='2224890'>right,</span> <span
  m='2225140'>so</span> <span m='2225550'>we</span> <span
  m='2225740'>decompose</span> <span m='2226630'>the</span> <span
  m='2226780'>original</span> <span m='2227200'>sequence,</span> <span
  m='2227800'>then,</span> <span m='2228190'>into</span> <span
  m='2228550'>p1</span> <span m='2229150'>sequences,</span> <span
  m='2230320'>each</span> <span m='2230590'>of</span> <span
  m='2230710'>length</span> <span m='2231040'>q1.</span> <span
  m='2233020'>Given</span> <span m='2233320'>that,</span> <span
  m='2233710'>we</span> <span m='2233950'>can</span> <span
  m='2234370'>organize</span> <span m='2235540'>the</span> <span
  m='2235690'>sum</span> <span m='2236260'>involved</span> <span
  m='2237190'>in</span> <span m='2237910'>the</span> <span
  m='2238120'>discrete</span> <span m='2238510'>Fourier</span> <span
  m='2238930'>transform</span> <span m='2241240'>by</span> <span
  m='2241690'>decomposing</span> <span m='2242590'>the</span> <span
  m='2242680'>sum</span> <span m='2243760'>into</span> <span
  m='2244240'>separate</span> <span m='2244780'>sums,</span> <span
  m='2246040'>involving</span> <span m='2247060'>each</span> <span
  m='2247360'>one</span> <span m='2247900'>of</span> <span
  m='2248140'>these</span> <span m='2248770'>p1</span> <span
  m='2249290'>sub-sequences.</span> </p><p><span m='2252600'>In</span> <span
  m='2252720'>particular,</span> <span m='2253840'>if</span> <span
  m='2254100'>we</span> <span m='2254310'>think</span> <span
  m='2254700'>of</span> <span m='2255960'>the</span> <span
  m='2256470'>argument</span> <span m='2257460'>p1</span> <span
  m='2257970'>times</span> <span m='2258360'>r,</span> <span
  m='2259980'>as</span> <span m='2260190'>r</span> <span
  m='2260820'>ranges</span> <span m='2261900'>from</span> <span
  m='2262680'>zero</span> <span m='2263910'>to</span> <span
  m='2264030'>q1</span> <span m='2264570'>minus</span> <span
  m='2265020'>one,</span> <span m='2266235'>we're</span> <span
  m='2266640'>selecting,</span> <span m='2267660'>with</span> <span
  m='2267840'>this</span> <span m='2268050'>argument,</span> <span
  m='2269240'>every</span> <span m='2269550'>p1th</span> <span
  m='2270120'>point,</span> <span m='2270930'>starting</span> <span
  m='2271740'>with</span> <span m='2271920'>the</span> <span
  m='2272010'>zero-eth</span> <span m='2272460'>point.</span> <span
  m='2274470'>If</span> <span m='2274590'>we</span> <span
  m='2274710'>think</span> <span m='2274920'>of</span> <span
  m='2275010'>the</span> <span m='2275160'>argument</span> <span
  m='2275610'>p1</span> <span m='2276090'>r</span> <span m='2276360'>plus</span>
  <span m='2276720'>one,</span> <span m='2277890'>as</span> <span
  m='2278040'>r</span> <span m='2278310'>runs</span> <span
  m='2278640'>from</span> <span m='2278820'>zero</span> <span
  m='2279210'>to</span> <span m='2279360'>q1</span> <span
  m='2279780'>minus</span> <span m='2280170'>one,</span> <span
  m='2280740'>we're</span> <span m='2280920'>then</span> <span
  m='2281130'>collecting</span> <span m='2281670'>together</span> <span
  m='2282870'>the</span> <span m='2283530'>terms,</span> <span
  m='2284640'>which</span> <span m='2285120'>are</span> <span
  m='2285360'>every</span> <span m='2285660'>p1th</span> <span
  m='2286160'>point,</span> <span m='2286590'>starting</span> <span
  m='2287040'>with</span> <span m='2287190'>the</span> <span
  m='2287280'>first</span> <span m='2287580'>point.</span> <span m='2288680'>Et
  cetera,</span> <span m='2289380'>we</span> <span m='2289560'>can</span> <span
  m='2289710'>proceed</span> <span m='2291390'>to</span> <span
  m='2291690'>decompose</span> <span m='2292410'>this</span> <span
  m='2292740'>into</span> <span m='2293100'>a</span> <span
  m='2293160'>set</span> <span m='2293520'>of</span> <span m='2294090'>p1</span>
  <span m='2295800'>sub-sums,</span> <span m='2297510'>as</span> <span
  m='2297780'>I've</span> <span m='2297930'>indicated</span> <span
  m='2298500'>here.</span> </p><p><span m='2300030'>Or</span> <span
  m='2300510'>when</span> <span m='2300750'>we</span> <span
  m='2300870'>combine</span> <span m='2301350'>these</span> <span
  m='2301590'>together,</span> <span m='2302460'>then,</span> <span
  m='2303870'>we</span> <span m='2304020'>can</span> <span
  m='2304170'>express</span> <span m='2305190'>x</span> <span
  m='2305460'>of</span> <span m='2305590'>k,</span> <span m='2306240'>the</span>
  <span m='2306360'>DFT,</span> <span m='2307740'>as</span> <span
  m='2307950'>a</span> <span m='2308010'>double</span> <span
  m='2308400'>sum,</span> <span m='2310890'>where</span> <span
  m='2311610'>we</span> <span m='2313510'>have</span> <span
  m='2314020'>the</span> <span m='2314170'>terms</span> <span
  m='2314920'>involving</span> <span m='2316000'>the</span> <span
  m='2316300'>separate</span> <span m='2316780'>sub</span> <span
  m='2317100'>sequences</span> <span m='2318970'>and</span> <span
  m='2319120'>then</span> <span m='2319750'>the</span> <span
  m='2319900'>multiplication</span> <span m='2321130'>by</span> <span
  m='2321640'>a</span> <span m='2321700'>power</span> <span
  m='2322150'>of</span> <span m='2322270'>W</span> <span m='2323290'>to</span>
  <span m='2323590'>combine</span> <span m='2325180'>the</span> <span
  m='2325480'>computation</span> <span m='2326260'>on</span> <span
  m='2326410'>these</span> <span m='2326530'>sub-sequences</span> <span
  m='2327370'>together</span> <span m='2328240'>to</span> <span
  m='2328420'>obtain</span> <span m='2329110'>the</span> <span
  m='2329200'>DFT.</span> <span m='2330430'>These</span> <span
  m='2330700'>terms,</span> <span m='2331120'>of</span> <span
  m='2331240'>course,</span> <span m='2332380'>are</span> <span
  m='2332590'>obtained</span> <span m='2333070'>by</span> <span
  m='2333250'>the</span> <span m='2333370'>fact</span> <span
  m='2333940'>that</span> <span m='2334810'>this</span> <span
  m='2334960'>power</span> <span m='2335350'>of</span> <span
  m='2335440'>W</span> <span m='2335830'>is</span> <span m='2335950'>p1</span>
  <span m='2336240'>r</span> <span m='2336610'>plus</span> <span
  m='2336910'>one.</span> <span m='2337730'>In</span> <span
  m='2337840'>the</span> <span m='2337930'>next</span> <span
  m='2338110'>sum,</span> <span m='2338500'>it</span> <span
  m='2338590'>will</span> <span m='2338740'>be</span> <span
  m='2338920'>p1</span> <span m='2339310'>r</span> <span m='2339460'>plus</span>
  <span m='2339790'>two,</span> <span m='2340290'>p1 r</span> <span
  m='2340660'>plus</span> <span m='2340930'>three,</span> <span m='2341200'>et
  cetera.</span> </p><p><span m='2342220'>We</span> <span
  m='2342310'>decompose</span> <span m='2343000'>that</span> <span
  m='2343180'>into</span> <span m='2343390'>a</span> <span
  m='2343480'>product</span> <span m='2344290'>of</span> <span
  m='2345250'>two</span> <span m='2345430'>powers</span> <span
  m='2345880'>of</span> <span m='2346000'>W.</span> <span m='2347050'>And</span>
  <span m='2347860'>then</span> <span m='2348430'>one</span> <span
  m='2348640'>of</span> <span m='2348760'>those</span> <span
  m='2349030'>terms--</span> <span m='2350620'>since</span> <span
  m='2350920'>it</span> <span m='2351040'>doesn't</span> <span
  m='2351310'>depend</span> <span m='2351700'>on</span> <span
  m='2351880'>r--</span> <span m='2352210'>can</span> <span
  m='2352390'>be</span> <span m='2352540'>removed</span> <span
  m='2352930'>from</span> <span m='2353110'>the</span> <span
  m='2353200'>sum</span> <span m='2353450'>on</span> <span m='2353620'>r</span>
  <span m='2354070'>and</span> <span m='2354280'>shows</span> <span
  m='2354640'>up</span> <span m='2354880'>in</span> <span
  m='2355030'>this</span> <span m='2355140'>second</span> <span
  m='2355510'>sum.</span> <span m='2357051'>Well</span> <span
  m='2357460'>I</span> <span m='2357580'>would</span> <span
  m='2357730'>suggest--</span> <span m='2358630'>that's</span> <span
  m='2358870'>a</span> <span m='2358960'>somewhat</span> <span
  m='2359860'>rapid</span> <span m='2360220'>treatment--</span> <span
  m='2360640'>I</span> <span m='2360700'>would</span> <span
  m='2360850'>suggest</span> <span m='2361300'>just</span> <span
  m='2361480'>simply</span> <span m='2362410'>working</span> <span
  m='2362740'>through</span> <span m='2362950'>that</span> <span
  m='2363160'>for</span> <span m='2363280'>an</span> <span
  m='2363370'>example.</span> </p><p><span m='2364010'>And</span> <span
  m='2364150'>I</span> <span m='2364210'>think</span> <span
  m='2364420'>it</span> <span m='2364480'>will</span> <span
  m='2364600'>be</span> <span m='2364750'>clear</span> <span
  m='2365680'>how</span> <span m='2366310'>this</span> <span
  m='2366520'>original</span> <span m='2366970'>sum</span> <span
  m='2367450'>is</span> <span m='2367630'>decomposed</span> <span
  m='2368290'>into</span> <span m='2368530'>this</span> <span
  m='2368740'>one.</span> <span m='2371180'>All</span> <span
  m='2371240'>right,</span> <span m='2371510'>well</span> <span
  m='2372080'>now,</span> <span m='2372650'>just</span> <span
  m='2372920'>as</span> <span m='2373070'>we</span> <span m='2373220'>did</span>
  <span m='2373610'>in</span> <span m='2374120'>both</span> <span
  m='2374390'>the</span> <span m='2374480'>decimation</span> <span
  m='2375140'>in</span> <span m='2375230'>time</span> <span
  m='2375620'>and</span> <span m='2375710'>decimation</span> <span
  m='2376340'>in</span> <span m='2376430'>frequency</span> <span
  m='2377060'>forms</span> <span m='2377480'>of</span> <span
  m='2377600'>the</span> <span m='2377750'>algorithm</span> <span
  m='2379550'>for</span> <span m='2379760'>powers</span> <span
  m='2380180'>of</span> <span m='2380300'>two,</span> <span
  m='2381710'>we</span> <span m='2381920'>can</span> <span
  m='2382520'>recognize</span> <span m='2383930'>this</span> <span
  m='2384620'>power</span> <span m='2385280'>of</span> <span m='2385670'>W
  sub-N</span> <span m='2387320'>as</span> <span m='2387500'>a</span> <span
  m='2387560'>different</span> <span m='2387950'>power</span> <span
  m='2389540'>of</span> <span m='2390170'>a</span> <span m='2390950'>W</span>
  <span m='2391700'>with</span> <span m='2391910'>a</span> <span
  m='2391970'>different</span> <span m='2392300'>subscript.</span> <span
  m='2393830'>In</span> <span m='2393950'>particular,</span> <span
  m='2394640'>W</span> <span m='2395060'>sub-N</span> <span
  m='2396130'>to</span> <span m='2396230'>the</span> <span m='2396350'>p1</span>
  <span m='2396980'>rk,</span> <span m='2398000'>as</span> <span
  m='2398180'>I</span> <span m='2398300'>have</span> <span
  m='2398600'>here,</span> <span m='2400760'>is</span> <span
  m='2400940'>equal</span> <span m='2401300'>to</span> <span
  m='2401510'>e</span> <span m='2401610'>to</span> <span m='2401690'>the</span>
  <span m='2401840'>j</span> <span m='2402080'>two</span> <span
  m='2402290'>pi</span> <span m='2402560'>over</span> <span
  m='2402740'>capital-N</span> <span m='2403490'>times</span> <span
  m='2403790'>p1</span> <span m='2404510'>rk.</span> </p><p><span
  m='2406730'>But</span> <span m='2406970'>N</span> <span m='2407660'>is</span>
  <span m='2407900'>equal</span> <span m='2408470'>to</span> <span
  m='2409550'>p1</span> <span m='2410390'>times</span> <span
  m='2410840'>q1.</span> <span m='2412310'>That's</span> <span
  m='2412490'>the</span> <span m='2412610'>way</span> <span
  m='2412760'>we</span> <span m='2412940'>originally</span> <span
  m='2413420'>decomposed</span> <span m='2414190'>it.</span> <span
  m='2415670'>And</span> <span m='2416450'>the</span> <span
  m='2416570'>p1's</span> <span m='2417200'>cancel</span> <span
  m='2417710'>out.</span> <span m='2419210'>And</span> <span
  m='2419330'>we're</span> <span m='2419450'>left</span> <span
  m='2419780'>with</span> <span m='2419930'>e</span> <span m='2420190'>to
  the</span> <span m='2420320'>j</span> <span m='2420560'>two</span> <span
  m='2420800'>pi</span> <span m='2421280'>over</span> <span
  m='2421580'>q1</span> <span m='2422330'>times</span> <span
  m='2422690'>rk</span> <span m='2423950'>or</span> <span
  m='2424130'>equivalently,</span> <span m='2425390'>W</span> <span
  m='2426060'>sub-q1</span> <span m='2427130'>to</span> <span
  m='2427250'>the</span> <span m='2427400'>rk.</span> </p><p><span
  m='2429680'>So</span> <span m='2432200'>substituting</span> <span
  m='2433100'>this</span> <span m='2433610'>for</span> <span
  m='2433890'>W</span> <span m='2434250'>sub-N</span> <span
  m='2435280'>to</span> <span m='2435440'>the</span> <span m='2435740'>p1</span>
  <span m='2436280'>r</span> <span m='2436490'>k</span> <span
  m='2437510'>in</span> <span m='2437930'>the</span> <span
  m='2438050'>previous</span> <span m='2438590'>expression,</span> <span
  m='2439820'>what</span> <span m='2439970'>results</span> <span
  m='2440630'>is</span> <span m='2440810'>then</span> <span m='2440930'>x</span>
  <span m='2441170'>of</span> <span m='2441450'>k</span> <span
  m='2442490'>expressed</span> <span m='2443390'>as</span> <span
  m='2444680'>a</span> <span m='2444740'>sum</span> <span
  m='2445070'>from</span> <span m='2445240'>l equals</span> <span
  m='2445550'>zero,</span> <span m='2445820'>p1</span> <span
  m='2446210'>minus</span> <span m='2446600'>one,</span> <span
  m='2446960'>of</span> <span m='2447320'>these</span> <span
  m='2447560'>powers</span> <span m='2448430'>of</span> <span
  m='2448580'>W</span> <span m='2448890'>sub-N.</span> <span
  m='2450320'>But</span> <span m='2450470'>then</span> <span
  m='2450650'>the</span> <span m='2450740'>important</span> <span
  m='2451250'>thing</span> <span m='2451820'>is</span> <span
  m='2452630'>that</span> <span m='2452750'>the</span> <span
  m='2452960'>inner</span> <span m='2453230'>sum</span> <span
  m='2454610'>involves</span> <span m='2455570'>q1</span> <span
  m='2456260'>point</span> <span m='2456620'>sequences.</span> <span
  m='2459240'>This</span> <span m='2459380'>factor</span> <span
  m='2460130'>is</span> <span m='2460310'>W sub-q1</span> <span
  m='2461080'>to</span> <span m='2461420'>the</span> <span
  m='2461570'>rk.</span> <span m='2462710'>And</span> <span
  m='2462830'>in</span> <span m='2462950'>fact,</span> <span
  m='2463820'>this</span> <span m='2464030'>entire</span> <span
  m='2464900'>summation</span> <span m='2466160'>is</span> <span
  m='2466520'>a</span> <span m='2466610'>q1</span> <span
  m='2467360'>point</span> <span m='2467940'>DFT.</span> </p><p><span
  m='2469730'>So</span> <span m='2470270'>pursuing</span> <span
  m='2470870'>this,</span> <span m='2471110'>then,</span> <span
  m='2472010'>what</span> <span m='2472430'>we</span> <span
  m='2472790'>basically</span> <span m='2473900'>decomposed</span> <span
  m='2474790'>the</span> <span m='2475610'>computation</span> <span
  m='2476510'>into</span> <span m='2477650'>is</span> <span
  m='2477800'>the</span> <span m='2477920'>computation</span> <span
  m='2480050'>of</span> <span m='2480780'>p1</span> <span m='2482710'>q1</span>
  <span m='2483500'>point</span> <span m='2484100'>DFT's.</span> <span
  m='2486890'>We</span> <span m='2487070'>obtained</span> <span
  m='2487760'>the</span> <span m='2487910'>q1</span> <span
  m='2488350'>point</span> <span m='2488900'>DFT's</span> <span
  m='2489620'>and</span> <span m='2489740'>then</span> <span
  m='2489890'>combined</span> <span m='2490460'>them,</span> <span
  m='2490970'>according</span> <span m='2491570'>to</span> <span
  m='2492470'>the</span> <span m='2492620'>expression</span> <span
  m='2493320'>as</span> <span m='2493370'>we</span> <span
  m='2493520'>have</span> <span m='2493820'>here.</span> <span
  m='2494900'>This</span> <span m='2495200'>would</span> <span
  m='2495410'>then</span> <span m='2495650'>lead</span> <span
  m='2496070'>to</span> <span m='2496220'>the</span> <span
  m='2496340'>generalization</span> <span m='2497360'>of</span> <span
  m='2497750'>the</span> <span m='2497840'>butterfly</span> <span
  m='2498380'>computation</span> <span m='2499280'>as</span> <span
  m='2499460'>we</span> <span m='2499580'>had</span> <span m='2499700'>it</span>
  <span m='2499910'>for</span> <span m='2500780'>the</span> <span
  m='2501020'>radix</span> <span m='2501420'>two</span> <span
  m='2501710'>algorithms.</span> </p><p><span m='2503780'>And</span> <span
  m='2504200'>if</span> <span m='2504410'>you</span> <span
  m='2504500'>count</span> <span m='2504830'>up</span> <span
  m='2505040'>the</span> <span m='2505280'>number</span> <span
  m='2505610'>of</span> <span m='2505670'>multiplies</span> <span
  m='2506360'>and</span> <span m='2506480'>adds,</span> <span
  m='2507290'>again,</span> <span m='2508130'>you'll</span> <span
  m='2508280'>see</span> <span m='2508580'>that</span> <span
  m='2508730'>there</span> <span m='2508860'>is</span> <span
  m='2508910'>some</span> <span m='2509090'>computational</span> <span
  m='2509960'>efficiency</span> <span m='2511130'>that</span> <span
  m='2511310'>results</span> <span m='2511730'>from</span> <span
  m='2511910'>doing</span> <span m='2512270'>this.</span> <span
  m='2513380'>And</span> <span m='2513920'>then,</span> <span
  m='2514190'>just</span> <span m='2514460'>as</span> <span
  m='2514580'>we</span> <span m='2514730'>did</span> <span
  m='2515090'>with</span> <span m='2515480'>the</span> <span
  m='2515690'>radix</span> <span m='2516050'>two</span> <span
  m='2516320'>algorithms,</span> <span m='2517580'>we</span> <span
  m='2517880'>can</span> <span m='2518840'>continue</span> <span
  m='2519440'>to</span> <span m='2519620'>decompose</span> <span
  m='2520610'>these</span> <span m='2520850'>transforms</span> <span
  m='2522590'>so</span> <span m='2522800'>that</span> <span
  m='2523340'>we</span> <span m='2523520'>have</span> <span
  m='2523850'>q1</span> <span m='2525080'>is</span> <span
  m='2525230'>given</span> <span m='2525590'>by</span> <span
  m='2525800'>the</span> <span m='2525920'>product</span> <span
  m='2526310'>p2</span> <span m='2526820'>times</span> <span
  m='2528200'>p3</span> <span m='2529310'>through</span> <span
  m='2529640'>p</span> <span m='2530000'>sub-Nu.</span> <span
  m='2531560'>This</span> <span m='2532340'>product</span> <span
  m='2534050'>we</span> <span m='2535010'>denote</span> <span
  m='2535460'>as</span> <span m='2535650'>q2.</span> </p><p><span
  m='2536990'>And</span> <span m='2537740'>then</span> <span
  m='2538130'>we</span> <span m='2538340'>can</span> <span
  m='2538490'>proceed</span> <span m='2539450'>to</span> <span
  m='2539600'>decompose</span> <span m='2540920'>these</span> <span
  m='2541190'>transforms--</span> <span m='2542030'>these</span> <span
  m='2542240'>q1</span> <span m='2542780'>point</span> <span
  m='2543080'>transforms--</span> <span m='2545270'>into</span> <span
  m='2546290'>p2</span> <span m='2548450'>q2</span> <span
  m='2548990'>point</span> <span m='2549320'>transforms.</span> <span
  m='2550610'>Then</span> <span m='2550820'>we</span> <span
  m='2550970'>can</span> <span m='2551120'>decompose</span> <span
  m='2551720'>the</span> <span m='2551840'>q2</span> <span
  m='2552290'>point</span> <span m='2552530'>transforms,</span> <span
  m='2553280'>et cetera.</span> <span m='2554570'>If</span> <span
  m='2554780'>you</span> <span m='2554900'>do</span> <span
  m='2555140'>this,</span> <span m='2555930'>then</span> <span
  m='2556400'>what</span> <span m='2556640'>you'll</span> <span
  m='2556790'>find--</span> <span m='2557330'>and</span> <span
  m='2557420'>the</span> <span m='2557510'>counting</span> <span
  m='2558110'>is</span> <span m='2558320'>done</span> <span m='2558890'>a</span>
  <span m='2558920'>little</span> <span m='2559130'>more</span> <span
  m='2559280'>carefully</span> <span m='2560030'>in</span> <span
  m='2560180'>the</span> <span m='2560270'>text--</span> <span
  m='2562160'>what</span> <span m='2562370'>you'll</span> <span
  m='2562520'>find</span> <span m='2563180'>is</span> <span
  m='2563450'>that</span> <span m='2564290'>the</span> <span
  m='2564380'>number</span> <span m='2564830'>of</span> <span
  m='2564950'>multiplies</span> <span m='2565700'>and</span> <span
  m='2565820'>adds</span> <span m='2566360'>involved</span> <span
  m='2567470'>in</span> <span m='2567590'>computing</span> <span
  m='2568430'>the</span> <span m='2568520'>discrete</span> <span
  m='2568910'>Fourier</span> <span m='2569330'>transform</span> <span
  m='2570440'>this</span> <span m='2570680'>way</span> <span
  m='2571820'>is</span> <span m='2572030'>proportional</span> <span
  m='2573410'>to</span> <span m='2573620'>N</span> <span
  m='2574970'>times</span> <span m='2575610'>a</span> <span
  m='2575720'>sum</span> <span m='2576950'>of</span> <span
  m='2577700'>the</span> <span m='2577790'>factors</span> <span
  m='2579080'>involved</span> <span m='2579950'>in</span> <span
  m='2580490'>the</span> <span m='2580580'>decomposition</span> <span
  m='2581770'>of</span> <span m='2581940'>N.</span> <span
  m='2583660'>I've</span> <span m='2583790'>indicated</span> <span
  m='2584660'>an</span> <span m='2584780'>additional</span> <span
  m='2585230'>factor</span> <span m='2585710'>here</span> <span
  m='2586010'>of</span> <span m='2586130'>minus</span> <span
  m='2586650'>Nu.</span> </p><p><span m='2587630'>Depending</span> <span
  m='2588140'>on</span> <span m='2588260'>how</span> <span
  m='2588500'>you</span> <span m='2588650'>choose</span> <span
  m='2589070'>to</span> <span m='2589190'>count</span> <span
  m='2589520'>multiplies</span> <span m='2590240'>and</span> <span
  m='2590330'>adds,</span> <span m='2591620'>this</span> <span
  m='2591890'>factor</span> <span m='2592310'>of</span> <span
  m='2592400'>minus</span> <span m='2592850'>Nu</span> <span
  m='2593210'>either</span> <span m='2593510'>shows</span> <span
  m='2593900'>up</span> <span m='2594140'>or</span> <span
  m='2594320'>not.</span> <span m='2595130'>In</span> <span
  m='2595220'>fact,</span> <span m='2595790'>to</span> <span
  m='2595910'>make</span> <span m='2596150'>this</span> <span
  m='2596390'>expression</span> <span m='2598560'>consistent</span> <span
  m='2599460'>with</span> <span m='2599760'>what</span> <span
  m='2600660'>we</span> <span m='2601100'>obtained</span> <span
  m='2601830'>for</span> <span m='2603060'>the</span> <span
  m='2603180'>power</span> <span m='2603570'>of</span> <span
  m='2603690'>two</span> <span m='2603930'>algorithms,</span> <span
  m='2605340'>the</span> <span m='2605760'>minus</span> <span
  m='2606140'>Nu</span> <span m='2606440'>should</span> <span
  m='2606690'>be</span> <span m='2606840'>in</span> <span
  m='2607050'>here.</span> <span m='2607470'>And</span> <span
  m='2607650'>it's</span> <span m='2607770'>simply</span> <span
  m='2608190'>a</span> <span m='2608250'>question</span> <span
  m='2608970'>of</span> <span m='2609900'>whether</span> <span
  m='2610470'>you</span> <span m='2610680'>count</span> <span
  m='2611100'>or</span> <span m='2611190'>don't</span> <span
  m='2611460'>count</span> <span m='2611800'>some</span> <span
  m='2611940'>multiplications</span> <span m='2612870'>by</span> <span
  m='2613050'>unity.</span> </p><p><span m='2614730'>Well</span> <span
  m='2615120'>OK,</span> <span m='2615480'>that's</span> <span
  m='2615720'>a</span> <span m='2615780'>very</span> <span
  m='2616320'>quick</span> <span m='2617430'>treatment--</span> <span
  m='2618210'>discussion--</span> <span m='2619110'>of</span> <span
  m='2620160'>the</span> <span m='2620610'>generalization</span> <span
  m='2621630'>of</span> <span m='2622020'>the</span> <span
  m='2622230'>radix</span> <span m='2622560'>two</span> <span
  m='2622770'>algorithms</span> <span m='2623520'>to</span> <span
  m='2623910'>more</span> <span m='2624120'>arbitrary</span> <span
  m='2624660'>radix.</span> <span m='2625800'>And</span> <span
  m='2626910'>there,</span> <span m='2627450'>as</span> <span
  m='2627690'>I</span> <span m='2627810'>indicated,</span> <span
  m='2628410'>are</span> <span m='2628530'>some</span> <span
  m='2628740'>examples</span> <span m='2629490'>of</span> <span
  m='2629670'>this,</span> <span m='2630540'>which</span> <span
  m='2630870'>are</span> <span m='2631050'>given</span> <span
  m='2631590'>in</span> <span m='2631740'>the</span> <span
  m='2631850'>text.</span> <span m='2632730'>Although,</span> <span
  m='2633270'>in</span> <span m='2633420'>fact,</span> <span
  m='2634210'>what</span> <span m='2634290'>you'll</span> <span
  m='2634440'>find</span> <span m='2635580'>is</span> <span
  m='2635790'>that</span> <span m='2636120'>in</span> <span
  m='2636330'>most</span> <span m='2636600'>practical</span> <span
  m='2637500'>contexts,</span> <span m='2638850'>it</span> <span
  m='2639030'>is</span> <span m='2639180'>a</span> <span
  m='2639270'>radix</span> <span m='2639580'>two</span> <span
  m='2639990'>algorithm</span> <span m='2640920'>that</span> <span
  m='2641280'>is</span> <span m='2642240'>the</span> <span
  m='2642780'>most</span> <span m='2643470'>efficient</span> <span
  m='2644130'>to</span> <span m='2644280'>use.</span> </p><p><span
  m='2645480'>And</span> <span m='2646650'>I</span> <span
  m='2646800'>indicate,</span> <span m='2647310'>incidentally,</span> <span
  m='2648210'>that</span> <span m='2648600'>if</span> <span
  m='2649290'>you</span> <span m='2649620'>are</span> <span
  m='2649710'>faced</span> <span m='2650040'>with</span> <span
  m='2650130'>the</span> <span m='2650220'>problem</span> <span
  m='2650700'>of</span> <span m='2650790'>transforming</span> <span
  m='2651480'>data,</span> <span m='2652950'>which</span> <span
  m='2653370'>is</span> <span m='2653550'>of</span> <span m='2653700'>a</span>
  <span m='2653760'>length</span> <span m='2654210'>which</span> <span
  m='2654480'>is</span> <span m='2654570'>not</span> <span m='2654780'>a</span>
  <span m='2654840'>power</span> <span m='2655260'>of</span> <span
  m='2655410'>two,</span> <span m='2655890'>it</span> <span
  m='2656090'>of</span> <span m='2656310'>course</span> <span
  m='2656610'>can</span> <span m='2656760'>always</span> <span
  m='2657060'>be</span> <span m='2657210'>made</span> <span
  m='2657750'>to</span> <span m='2657870'>be</span> <span m='2658050'>of</span>
  <span m='2658140'>length</span> <span m='2658830'>power</span> <span
  m='2659220'>of</span> <span m='2659410'>two</span> <span m='2660180'>by</span>
  <span m='2660480'>simply</span> <span m='2660930'>augmenting</span> <span
  m='2661470'>the</span> <span m='2661560'>sequence</span> <span
  m='2662040'>with</span> <span m='2662190'>zeros.</span> <span
  m='2664470'>Well</span> <span m='2664980'>this</span> <span
  m='2665430'>concludes,</span> <span m='2666060'>then,</span> <span
  m='2666630'>the</span> <span m='2666960'>discussion</span> <span
  m='2667860'>of</span> <span m='2668430'>the</span> <span
  m='2668820'>FFT</span> <span m='2669480'>algorithms,</span> <span
  m='2670650'>the</span> <span m='2670830'>computation</span> <span
  m='2671850'>of</span> <span m='2672570'>the</span> <span
  m='2672660'>discrete</span> <span m='2673080'>Fourier</span> <span
  m='2673530'>transform.</span> <span m='2675120'>And</span> <span
  m='2676080'>there</span> <span m='2676650'>are,</span> <span
  m='2677700'>I</span> <span m='2677820'>hope,</span> <span m='2678900'>a</span>
  <span m='2678960'>number</span> <span m='2679500'>of</span> <span
  m='2679740'>issues</span> <span m='2680280'>which</span> <span
  m='2680910'>you</span> <span m='2681420'>will</span> <span
  m='2682380'>have</span> <span m='2682560'>an</span> <span
  m='2682650'>opportunity</span> <span m='2683550'>to</span> <span
  m='2683850'>dwell</span> <span m='2684210'>on</span> <span
  m='2684420'>some</span> <span m='2684960'>as</span> <span
  m='2685200'>you</span> <span m='2685320'>read</span> <span
  m='2685560'>through</span> <span m='2686010'>the</span> <span
  m='2686130'>text</span> <span m='2686700'>and</span> <span
  m='2687390'>as</span> <span m='2687570'>your</span> <span
  m='2687690'>attention</span> <span m='2688200'>will</span> <span
  m='2688350'>be</span> <span m='2688470'>drawn</span> <span
  m='2688740'>to</span> <span m='2688950'>in</span> <span m='2689010'>the</span>
  <span m='2689100'>study</span> <span m='2689430'>guide.</span> <span
  m='2690330'>Thank</span> <span m='2690570'>you.</span> </p><p><span
  m='2694770'>[MUSIC PLAYING]</span> </p>
embedded_media:
  - uid: fd93ff783243d4c0ee1b5959a57b5c0e
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: MITRES_6_008S11_lec20.pdf
    title: MITRES_6_008S11_lec20.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-20-computation-of-the-discrete-fourier-transform-part-3/MITRES_6_008S11_lec20.pdf
  - uid: da71b75dbabb2a885db7e976c1e75afd
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: xRLaQ4My3ms
  - uid: fef4ee2b646bc9cda2787f77ad23fc5c
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-20-computation-discrete/id481803782?i=108362006
  - uid: b95b43bef0833bb1bacc61c2bd3e8656
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec20_300k.mp4'
  - uid: 77512493ffbfa51eb2f8473fd155e80d
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/xRLaQ4My3ms/default.jpg'
  - uid: 7220361aa0e063e174c846b9e16685aa
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: xRLaQ4My3ms
  - uid: 4c3d78a60dc818ac933d93c22661c1bf
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: xRLaQ4My3ms.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-20-computation-of-the-discrete-fourier-transform-part-3/xRLaQ4My3ms.srt
  - uid: a0116d256c4adacd530451f41ac96f4e
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: xRLaQ4My3ms.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-20-computation-of-the-discrete-fourier-transform-part-3/xRLaQ4My3ms.pdf
  - uid: b9f1a3ecc308f4b3ae1fd68dbac6c985
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 1a15b82db3b3ae8da0a5c3612b53412d
    parent_uid: 040463c7a951ba8c31ecca7c0a08d9ac
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
