---
order_index: null
title: >-
  Lecture 13: Network Structures for Finite Impulse Response (FIR) Systems and
  Parameter Quantization Effects in Digital Filter Structures
template_type: Tabbed
uid: f571f16c74146803a56d0a7730131c58
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-13-network-structures-for-finite-impulse-response-fir-systems-and-parameter-quantization-effects-in-digital-filter-structures
short_url: >-
  lecture-13-network-structures-for-finite-impulse-response-fir-systems-and-parameter-quantization-effects-in-digital-filter-structures
inline_embed_id: >-
  4900580lecture13:networkstructuresforfiniteimpulseresponse(fir)systemsandparameterquantizationeffectsindigitalfilterstructures80186011
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Direct form FIR filters, efficient
  implementation of FIR filters with linear phase, frequency sampling structure,
  effects of parameter-quantization in digital filter implementation.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Network Structures for Finite Impulse Response (FIR) Systems and Parameter
  Quantization Effects in Digital Filter Structures (<a
  href="./resolveuid/f3394c024819bc75cd63a4b298b488d8">PDF</a>)</p>
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
  m='24150'>[MUSIC PLAYING]</span> </p><p></p><p><span m='51270'>The</span>
  <span m='51370'>last</span> <span m='51700'>lecture</span> <span
  m='52300'>we</span> <span m='52480'>consider</span> <span
  m='53020'>some</span> <span m='53200'>basic</span> <span
  m='53560'>structures</span> <span m='54430'>for</span> <span
  m='54880'>infinite</span> <span m='55300'>impulse</span> <span
  m='55720'>response</span> <span m='56560'>and</span> <span
  m='56980'>actually</span> <span m='57430'>also</span> <span
  m='57760'>for</span> <span m='57880'>finite</span> <span
  m='58300'>impulse</span> <span m='58690'>response</span> <span
  m='59530'>systems.</span> <span m='61660'>In</span> <span
  m='61780'>this</span> <span m='61990'>lecture,</span> <span m='62720'>I</span>
  <span m='62800'>would</span> <span m='62950'>like</span> <span
  m='63220'>to</span> <span m='63700'>focus</span> <span
  m='64150'>specifically</span> <span m='65170'>on</span> <span
  m='65500'>finite</span> <span m='65920'>impulse</span> <span
  m='66340'>response</span> <span m='66820'>systems</span> <span
  m='68710'>and</span> <span m='69340'>indicate,</span> <span
  m='70040'>to</span> <span m='70150'>show,</span> <span m='70930'>that</span>
  <span m='71470'>for</span> <span m='72340'>that</span> <span
  m='72580'>class</span> <span m='72940'>of</span> <span
  m='73060'>systems,</span> <span m='73930'>there</span> <span
  m='74380'>are</span> <span m='75070'>some</span> <span
  m='75640'>structures</span> <span m='76840'>that</span> <span
  m='76990'>specifically</span> <span m='77980'>exploit</span> <span
  m='78550'>properties</span> <span m='79390'>of</span> <span
  m='79690'>FIR,</span> <span m='80320'>or</span> <span m='80620'>finite</span>
  <span m='80980'>impulse</span> <span m='81370'>response,</span> <span
  m='81820'>systems.</span> </p><p><span m='83990'>First</span> <span
  m='84190'>of</span> <span m='84280'>all,</span> <span m='85580'>let's</span>
  <span m='85780'>consider</span> <span m='86680'>the</span> <span
  m='86980'>general</span> <span m='87430'>form</span> <span m='88090'>of</span>
  <span m='88600'>a</span> <span m='88960'>finite</span> <span
  m='89680'>impulse</span> <span m='90130'>response</span> <span
  m='90610'>system.</span> <span m='92170'>One</span> <span m='92350'>of</span>
  <span m='92650'>the</span> <span m='92770'>characteristics</span> <span
  m='93670'>of</span> <span m='93760'>a</span> <span m='93820'>finite</span>
  <span m='94210'>impulse</span> <span m='94600'>response</span> <span
  m='95050'>system,</span> <span m='95720'>of</span> <span
  m='95820'>course,</span> <span m='96260'>is</span> <span m='96310'>the</span>
  <span m='96400'>fact</span> <span m='96820'>that</span> <span
  m='97330'>the</span> <span m='97480'>impulse</span> <span
  m='97900'>response</span> <span m='98800'>has</span> <span
  m='99520'>only</span> <span m='99850'>a</span> <span m='99910'>finite</span>
  <span m='100330'>number</span> <span m='100840'>of</span> <span
  m='100990'>nonzero</span> <span m='101590'>samples,</span> <span
  m='102850'>or</span> <span m='103270'>equivalently</span> <span
  m='104530'>the</span> <span m='104650'>system</span> <span
  m='105070'>function</span> <span m='106540'>involves</span> <span
  m='107070'>a</span> <span m='107140'>sum</span> <span m='108070'>only</span>
  <span m='108460'>over</span> <span m='108760'>a</span> <span
  m='108820'>finite</span> <span m='109330'>range.</span> <span
  m='109900'>So</span> <span m='110770'>the</span> <span
  m='110860'>system</span> <span m='111250'>function</span> <span
  m='111640'>in</span> <span m='111760'>general</span> <span
  m='112270'>for</span> <span m='112420'>a</span> <span m='112480'>finite</span>
  <span m='112870'>impulse</span> <span m='113290'>response</span> <span
  m='113740'>system</span> <span m='114880'>is</span> <span m='115060'>of</span>
  <span m='115150'>this</span> <span m='115420'>form.</span> <span
  m='116410'>And</span> <span m='116770'>the</span> <span
  m='116890'>difference</span> <span m='117280'>equation</span> <span
  m='118150'>for</span> <span m='118330'>this</span> <span
  m='118440'>system</span> <span m='119440'>is</span> <span
  m='119570'>that</span> <span m='119710'>the</span> <span
  m='119830'>form</span> <span m='120460'>of</span> <span m='120640'>a</span>
  <span m='120670'>sum</span> <span m='121120'>from</span> <span
  m='121300'>k</span> <span m='121630'>will</span> <span m='121750'>0</span>
  <span m='122290'>to</span> <span m='122440'>capital</span> <span
  m='122950'>N</span> <span m='123100'>minus</span> <span m='123490'>1</span>
  <span m='123880'>of</span> <span m='125050'>h</span> <span
  m='125320'>of</span> <span m='125490'>k,</span> <span m='125830'>the</span>
  <span m='125950'>unit</span> <span m='126190'>sample</span> <span
  m='126610'>response,</span> <span m='127660'>x</span> <span
  m='128135'>of</span> <span m='128610'>n</span> <span m='128979'>minus</span>
  <span m='129360'>k.</span> </p><p><span m='130550'>We've</span> <span
  m='130710'>stressed</span> <span m='131050'>the</span> <span
  m='131170'>fact,</span> <span m='131500'>of</span> <span
  m='131590'>course,</span> <span m='132190'>in</span> <span m='132730'>a</span>
  <span m='132790'>variety</span> <span m='133300'>of</span> <span
  m='133390'>the</span> <span m='133540'>earlier</span> <span
  m='133900'>lectures,</span> <span m='135010'>that</span> <span
  m='135790'>the</span> <span m='135910'>difference</span> <span
  m='136330'>equation</span> <span m='136930'>for</span> <span
  m='137110'>a</span> <span m='137170'>finite</span> <span
  m='137590'>impulse</span> <span m='138040'>response</span> <span
  m='138490'>system,</span> <span m='139510'>in</span> <span
  m='139630'>fact,</span> <span m='140410'>corresponds</span> <span
  m='141160'>to</span> <span m='141280'>the</span> <span
  m='141400'>convolution</span> <span m='142150'>sum</span> <span
  m='142810'>for</span> <span m='143620'>finite</span> <span
  m='144010'>impulse</span> <span m='144400'>response</span> <span
  m='144880'>systems,</span> <span m='146170'>or</span> <span
  m='147010'>the</span> <span m='147190'>coefficients</span> <span
  m='148180'>in</span> <span m='148330'>the</span> <span
  m='148390'>difference</span> <span m='148780'>equation</span> <span
  m='149470'>are,</span> <span m='149800'>in</span> <span
  m='149920'>fact,</span> <span m='150520'>the</span> <span
  m='150610'>values</span> <span m='151330'>of</span> <span
  m='151480'>the</span> <span m='151570'>unit</span> <span
  m='151870'>sample</span> <span m='152260'>response.</span> </p><p><span
  m='154690'>Now,</span> <span m='155170'>for</span> <span m='155320'>a</span>
  <span m='155380'>finite</span> <span m='155770'>impulse</span> <span
  m='156160'>response</span> <span m='156610'>system</span> <span
  m='157090'>we</span> <span m='157390'>can,</span> <span m='157700'>of</span>
  <span m='157800'>course,</span> <span m='158140'>talk</span> <span
  m='158500'>about</span> <span m='159100'>the</span> <span
  m='159190'>same</span> <span m='160030'>types</span> <span
  m='160360'>of</span> <span m='160450'>structures</span> <span
  m='161260'>that</span> <span m='161590'>we</span> <span
  m='161740'>talked</span> <span m='162100'>about</span> <span
  m='162550'>in</span> <span m='162670'>a</span> <span
  m='162730'>previous</span> <span m='163210'>lecture.</span> <span
  m='164200'>For</span> <span m='164380'>example,</span> <span
  m='164920'>we</span> <span m='165100'>can</span> <span
  m='165250'>generate</span> <span m='166330'>a</span> <span
  m='167080'>direct</span> <span m='167500'>form</span> <span
  m='167860'>structure</span> <span m='169090'>from</span> <span
  m='169870'>the</span> <span m='169990'>difference</span> <span
  m='170380'>equation,</span> <span m='171040'>or</span> <span
  m='171190'>equivalently</span> <span m='172150'>from</span> <span
  m='172900'>the</span> <span m='173020'>z</span> <span
  m='173230'>transform.</span> <span m='175300'>And</span> <span
  m='175690'>we</span> <span m='175840'>see</span> <span m='176110'>that</span>
  <span m='176260'>the</span> <span m='176350'>direct</span> <span
  m='176710'>form</span> <span m='177010'>structure</span> <span
  m='178120'>corresponds</span> <span m='179620'>to</span> <span
  m='179770'>generating</span> <span m='180880'>a</span> <span
  m='181030'>weighted</span> <span m='182020'>combination</span> <span
  m='183340'>of</span> <span m='183520'>delayed</span> <span
  m='184380'>inputs</span> <span m='185470'>where</span> <span
  m='185980'>the</span> <span m='186100'>weighting</span> <span
  m='186490'>coefficients</span> <span m='187420'>are</span> <span
  m='187780'>the</span> <span m='187900'>values</span> <span
  m='188410'>in</span> <span m='188500'>the</span> <span m='188560'>unit</span>
  <span m='188860'>sample</span> <span m='189250'>response</span> <span
  m='189760'>h</span> <span m='190000'>of</span> <span m='190330'>n.</span>
  </p><p><span m='191270'>So</span> <span m='192370'>for</span> <span
  m='192910'>a</span> <span m='193000'>general</span> <span
  m='193390'>direct</span> <span m='193750'>form</span> <span
  m='194080'>structure,</span> <span m='195130'>we</span> <span
  m='195310'>have</span> <span m='196510'>x</span> <span m='196780'>of</span>
  <span m='196900'>n,</span> <span m='197860'>x</span> <span
  m='198100'>of</span> <span m='198190'>n</span> <span m='198340'>minus</span>
  <span m='198760'>1</span> <span m='199150'>at</span> <span
  m='199240'>the</span> <span m='199390'>output</span> <span
  m='199750'>of</span> <span m='199840'>this</span> <span
  m='200050'>delay,</span> <span m='200710'>x</span> <span m='200980'>of</span>
  <span m='201070'>n</span> <span m='201220'>minus</span> <span
  m='201640'>2,</span> <span m='202460'>et</span> <span
  m='202755'>cetera,</span> <span m='203590'>x</span> <span m='203830'>of</span>
  <span m='203920'>n</span> <span m='204040'>minus</span> <span
  m='204430'>1</span> <span m='204700'>multiplied</span> <span
  m='205300'>by</span> <span m='205510'>h</span> <span m='205780'>of</span>
  <span m='205940'>1,</span> <span m='207130'>x</span> <span
  m='207490'>of</span> <span m='207760'>n</span> <span
  m='208240'>multiplied</span> <span m='208810'>by</span> <span
  m='208990'>h</span> <span m='209230'>of</span> <span m='209320'>0,</span>
  <span m='210340'>down</span> <span m='210610'>through</span> <span
  m='210850'>the</span> <span m='210940'>chain.</span> <span
  m='211990'>The</span> <span m='212110'>results</span> <span
  m='213040'>added</span> <span m='213370'>up</span> <span m='213520'>at</span>
  <span m='213610'>the</span> <span m='213760'>output</span> <span
  m='214660'>to</span> <span m='215050'>produce</span> <span
  m='215800'>the</span> <span m='215950'>overall</span> <span
  m='216430'>output</span> <span m='216970'>y</span> <span m='217270'>of</span>
  <span m='217370'>n.</span> </p><p><span m='218770'>So</span> <span
  m='219280'>this</span> <span m='220090'>is</span> <span m='220240'>what</span>
  <span m='220450'>would</span> <span m='220600'>correspond</span> <span
  m='221530'>to</span> <span m='221740'>applying</span> <span
  m='222190'>the</span> <span m='222280'>notion</span> <span
  m='222790'>of</span> <span m='222910'>a</span> <span m='222970'>direct</span>
  <span m='223330'>form</span> <span m='223630'>structure</span> <span
  m='224860'>to</span> <span m='225490'>a</span> <span m='225820'>finite</span>
  <span m='226270'>impulse</span> <span m='226690'>response</span> <span
  m='227170'>system.</span> <span m='228290'>Likewise,</span> <span
  m='228790'>we</span> <span m='228910'>could</span> <span
  m='229030'>talk</span> <span m='229360'>about</span> <span m='229690'>a</span>
  <span m='229930'>transposed</span> <span m='230800'>form</span> <span
  m='231490'>of</span> <span m='231640'>this</span> <span
  m='231850'>network.</span> <span m='232840'>We</span> <span
  m='232960'>could</span> <span m='233140'>also</span> <span
  m='233830'>talk</span> <span m='234190'>about</span> <span m='234940'>a</span>
  <span m='235150'>cascade</span> <span m='235870'>form</span> <span
  m='236200'>realization</span> <span m='237040'>of</span> <span
  m='237160'>a</span> <span m='237220'>finite</span> <span
  m='237640'>impulse</span> <span m='238060'>response</span> <span
  m='238570'>filter,</span> <span m='239480'>simply</span> <span
  m='239800'>by</span> <span m='240010'>factoring</span> <span
  m='240640'>this</span> <span m='241060'>into</span> <span m='241390'>a</span>
  <span m='241480'>product,</span> <span m='242380'>not</span> <span
  m='242560'>a</span> <span m='242650'>poles</span> <span m='243070'>and</span>
  <span m='243310'>zeros,</span> <span m='244330'>because,</span> <span
  m='244630'>of</span> <span m='244690'>course,</span> <span
  m='245060'>there</span> <span m='245110'>aren't</span> <span
  m='245420'>poles</span> <span m='246220'>for</span> <span m='246370'>a</span>
  <span m='246430'>finite</span> <span m='246790'>impulse</span> <span
  m='247150'>response</span> <span m='247600'>system,</span> <span
  m='248440'>but</span> <span m='248740'>as</span> <span m='248920'>a</span>
  <span m='248950'>cascade</span> <span m='249700'>of</span> <span
  m='249820'>zeros,</span> <span m='250720'>either</span> <span
  m='251110'>implemented</span> <span m='251680'>as</span> <span
  m='251830'>first</span> <span m='252190'>or</span> <span
  m='252250'>second</span> <span m='252610'>order</span> <span
  m='252850'>sections.</span> </p><p><span m='255100'>Something</span> <span
  m='255580'>to</span> <span m='255730'>give</span> <span m='255910'>some</span>
  <span m='256089'>thought</span> <span m='256390'>to</span> <span
  m='256600'>incidentally</span> <span m='257620'>is</span> <span
  m='258550'>whether</span> <span m='258940'>for</span> <span
  m='259120'>a</span> <span m='259180'>finite</span> <span
  m='259630'>impulse</span> <span m='260050'>response</span> <span
  m='260500'>system</span> <span m='261610'>you</span> <span
  m='261760'>can</span> <span m='261970'>generate</span> <span
  m='262660'>a</span> <span m='262840'>parallel</span> <span
  m='263380'>form</span> <span m='263710'>structure</span> <span
  m='264790'>like</span> <span m='265060'>the</span> <span
  m='265180'>parallel</span> <span m='265660'>form</span> <span
  m='265930'>structure</span> <span m='266650'>that</span> <span
  m='267010'>we</span> <span m='267130'>talked</span> <span
  m='267460'>about</span> <span m='267730'>last</span> <span
  m='268060'>time.</span> <span m='268960'>The</span> <span
  m='269110'>answer</span> <span m='269410'>to</span> <span
  m='269560'>that,</span> <span m='269770'>in</span> <span
  m='269860'>fact,</span> <span m='270220'>is</span> <span m='270370'>no.</span>
  <span m='271540'>And</span> <span m='271690'>it's</span> <span
  m='271840'>tied</span> <span m='272140'>to</span> <span m='272230'>the</span>
  <span m='272350'>fact</span> <span m='272740'>that</span> <span
  m='272860'>an</span> <span m='272980'>FIR</span> <span
  m='273460'>system</span> <span m='273910'>doesn't</span> <span
  m='274240'>have</span> <span m='274450'>any</span> <span
  m='274690'>poles.</span> <span m='275650'>Although</span> <span
  m='276130'>as</span> <span m='276310'>we'll</span> <span m='276460'>see</span>
  <span m='277240'>later</span> <span m='277600'>on</span> <span
  m='277750'>in</span> <span m='277840'>this</span> <span
  m='278050'>lecture,</span> <span m='278750'>there</span> <span
  m='278890'>is</span> <span m='279790'>a</span> <span
  m='279910'>structure</span> <span m='280840'>that</span> <span
  m='281140'>is</span> <span m='281650'>of</span> <span m='281800'>the</span>
  <span m='281920'>form</span> <span m='282520'>of</span> <span
  m='282700'>a</span> <span m='282760'>parallel</span> <span
  m='283300'>form</span> <span m='284170'>for</span> <span
  m='284350'>implementing</span> <span m='285020'>FIR</span> <span
  m='285580'>systems.</span> </p><p><span m='287380'>So</span> <span
  m='287740'>the</span> <span m='287860'>first</span> <span
  m='288160'>point</span> <span m='288490'>then</span> <span
  m='288850'>is</span> <span m='289120'>that</span> <span m='289690'>we</span>
  <span m='289810'>can</span> <span m='289960'>apply</span> <span
  m='290290'>many</span> <span m='290590'>of</span> <span m='290680'>the</span>
  <span m='290800'>ideas</span> <span m='291880'>of</span> <span
  m='292000'>the</span> <span m='292120'>previous</span> <span
  m='292600'>lecture</span> <span m='293650'>to</span> <span
  m='294640'>FIR</span> <span m='295210'>systems.</span> <span
  m='296290'>But</span> <span m='296530'>in</span> <span
  m='296710'>addition,</span> <span m='297590'>there</span> <span
  m='297760'>are</span> <span m='297910'>some</span> <span
  m='298120'>properties</span> <span m='299050'>of</span> <span
  m='299170'>some</span> <span m='299440'>FIR</span> <span
  m='299980'>systems</span> <span m='301060'>that</span> <span
  m='301210'>lead</span> <span m='301660'>to</span> <span m='301900'>some</span>
  <span m='302140'>specific</span> <span m='303490'>network</span> <span
  m='303910'>structures</span> <span m='305110'>that</span> <span
  m='305350'>in</span> <span m='305530'>general</span> <span
  m='306010'>can't</span> <span m='306340'>be</span> <span
  m='306490'>used</span> <span m='306910'>for</span> <span
  m='307120'>implementing</span> <span m='307900'>IIR,</span> <span
  m='308710'>or</span> <span m='309160'>recursive,</span> <span
  m='309730'>systems.</span> </p><p><span m='311960'>The</span> <span
  m='312060'>first</span> <span m='312280'>of</span> <span
  m='312400'>these</span> <span m='313000'>that</span> <span
  m='313300'>I'd</span> <span m='313450'>like</span> <span m='313660'>to</span>
  <span m='313750'>talk</span> <span m='314110'>about</span> <span
  m='315040'>is</span> <span m='316480'>directed</span> <span
  m='317020'>specifically</span> <span m='318280'>toward</span> <span
  m='318700'>the</span> <span m='318880'>implementation</span> <span
  m='319960'>of</span> <span m='320440'>linear</span> <span
  m='320860'>phase</span> <span m='321620'>FIR</span> <span
  m='322180'>systems.</span> <span m='324300'>Now</span> <span
  m='324580'>recall</span> <span m='325300'>from</span> <span
  m='325840'>several</span> <span m='327190'>lectures</span> <span
  m='327970'>ago--</span> <span m='328510'>and</span> <span
  m='328750'>we've</span> <span m='329320'>again</span> <span
  m='329980'>raised</span> <span m='330310'>this</span> <span
  m='330520'>point</span> <span m='330940'>a</span> <span
  m='331000'>number</span> <span m='331360'>of</span> <span
  m='331480'>times--</span> <span m='331795'>that</span> <span
  m='332770'>one</span> <span m='332980'>of</span> <span m='333040'>the</span>
  <span m='333160'>differences</span> <span m='334000'>between</span> <span
  m='334610'>IIR</span> <span m='335460'>and</span> <span m='335650'>FIR</span>
  <span m='336160'>systems</span> <span m='337450'>is</span> <span
  m='337690'>that</span> <span m='338140'>because</span> <span
  m='338590'>of</span> <span m='338680'>the</span> <span m='338800'>fact</span>
  <span m='339400'>that</span> <span m='339610'>the</span> <span
  m='339730'>impulse</span> <span m='340210'>response</span> <span
  m='341440'>of</span> <span m='341560'>an</span> <span m='341620'>FIR</span>
  <span m='342130'>system</span> <span m='342880'>is</span> <span
  m='343090'>a</span> <span m='343180'>finite</span> <span
  m='343690'>length,</span> <span m='345900'>those</span> <span
  m='346170'>systems</span> <span m='346830'>can</span> <span
  m='346980'>in</span> <span m='347070'>fact</span> <span m='347430'>be</span>
  <span m='347580'>designed</span> <span m='348210'>to</span> <span
  m='348330'>have</span> <span m='348720'>exactly</span> <span
  m='349350'>linear</span> <span m='349710'>phase,</span> <span
  m='350730'>whereas</span> <span m='351420'>the</span> <span
  m='351510'>corresponding</span> <span m='352230'>statement</span> <span
  m='352920'>of</span> <span m='353070'>course</span> <span m='353400'>is</span>
  <span m='353520'>not</span> <span m='353730'>true</span> <span
  m='354630'>for</span> <span m='354720'>the</span> <span m='354840'>case</span>
  <span m='355260'>of</span> <span m='355590'>infinite</span> <span
  m='356010'>impulse</span> <span m='356400'>response</span> <span
  m='356850'>systems.</span> </p><p><span m='359510'>In</span> <span
  m='359630'>particular,</span> <span m='360590'>a</span> <span
  m='361010'>linear</span> <span m='361400'>phase</span> <span
  m='362330'>finite</span> <span m='362720'>impulse</span> <span
  m='363140'>response</span> <span m='363590'>system</span> <span
  m='364760'>is</span> <span m='364910'>one</span> <span m='365480'>for</span>
  <span m='365690'>which</span> <span m='366170'>the</span> <span
  m='366530'>values</span> <span m='367310'>in</span> <span
  m='367460'>the</span> <span m='367550'>unit</span> <span
  m='367820'>sample</span> <span m='368270'>response</span> <span
  m='369480'>satisfy</span> <span m='370210'>a</span> <span
  m='370320'>certain</span> <span m='370670'>symmetry</span> <span
  m='371180'>condition,</span> <span m='372290'>namely</span> <span
  m='372980'>the</span> <span m='373100'>symmetry</span> <span
  m='373550'>condition</span> <span m='374210'>as</span> <span
  m='374780'>I've</span> <span m='375200'>indicated</span> <span
  m='375880'>it</span> <span m='375950'>here,</span> <span m='376490'>h</span>
  <span m='376810'>of</span> <span m='377130'>n</span> <span
  m='377450'>equal</span> <span m='377900'>to</span> <span m='378320'>h</span>
  <span m='378680'>of</span> <span m='378920'>capital</span> <span
  m='379460'>N</span> <span m='379910'>minus</span> <span m='380330'>1</span>
  <span m='380900'>minus</span> <span m='381250'>little</span> <span
  m='381610'>n,</span> <span m='382250'>where</span> <span
  m='382430'>capital</span> <span m='382940'>N</span> <span m='383240'>is</span>
  <span m='383510'>the</span> <span m='383630'>length</span> <span
  m='384230'>of</span> <span m='384860'>the</span> <span
  m='385340'>finite</span> <span m='386000'>length</span> <span
  m='386300'>impulse</span> <span m='386720'>response.</span> <span
  m='388520'>For</span> <span m='388700'>example,</span> <span
  m='389930'>a</span> <span m='390170'>finite,</span> <span m='390980'>a</span>
  <span m='391160'>linear</span> <span m='391520'>phase</span> <span
  m='392100'>FIR</span> <span m='392930'>impulse</span> <span
  m='393410'>response</span> <span m='394310'>as</span> <span
  m='394490'>one</span> <span m='394670'>example</span> <span
  m='395750'>might</span> <span m='396170'>look,</span> <span
  m='396530'>as</span> <span m='396740'>I've</span> <span
  m='396890'>indicated</span> <span m='397610'>here,</span> <span
  m='398670'>where</span> <span m='399140'>I've</span> <span
  m='399410'>drawn</span> <span m='399710'>it</span> <span m='399830'>for</span>
  <span m='400310'>capital</span> <span m='400850'>N</span> <span
  m='401150'>equal</span> <span m='401510'>to</span> <span m='401730'>9.</span>
  <span m='402980'>And</span> <span m='403700'>this</span> <span
  m='403880'>symmetry</span> <span m='404420'>property</span> <span
  m='405470'>says</span> <span m='406370'>that</span> <span m='407150'>h</span>
  <span m='407450'>of</span> <span m='407550'>0,</span> <span
  m='408590'>if</span> <span m='408710'>I</span> <span
  m='408800'>substitute</span> <span m='409310'>n</span> <span
  m='409430'>equals</span> <span m='409730'>0,</span> <span m='410750'>is</span>
  <span m='410900'>equal</span> <span m='411260'>to</span> <span
  m='411470'>h</span> <span m='411710'>of</span> <span m='411800'>capital</span>
  <span m='412250'>N</span> <span m='412370'>minus</span> <span
  m='412790'>1,</span> <span m='413240'>or</span> <span m='413780'>h</span>
  <span m='414020'>of</span> <span m='414110'>8.</span> <span
  m='415370'>And</span> <span m='415520'>we</span> <span m='415640'>can</span>
  <span m='415790'>see</span> <span m='416060'>that</span> <span
  m='416210'>that's</span> <span m='416570'>the</span> <span
  m='416690'>symmetry</span> <span m='417170'>that</span> <span
  m='417320'>we</span> <span m='417470'>have.</span> </p><p><span
  m='418700'>And</span> <span m='419360'>then</span> <span
  m='419540'>likewise,</span> <span m='420260'>the</span> <span
  m='420350'>linear</span> <span m='420740'>phase</span> <span
  m='421400'>property</span> <span m='422390'>says</span> <span
  m='423140'>that</span> <span m='423470'>as</span> <span m='423980'>I</span>
  <span m='424130'>go</span> <span m='424370'>through</span> <span
  m='424610'>the</span> <span m='424760'>impulse</span> <span
  m='425180'>response</span> <span m='426230'>from</span> <span
  m='426410'>both</span> <span m='426770'>ends,</span> <span m='427680'>I</span>
  <span m='427700'>see</span> <span m='428090'>identical</span> <span
  m='428660'>values</span> <span m='429110'>so</span> <span
  m='429260'>that</span> <span m='429770'>these</span> <span
  m='430010'>values</span> <span m='430460'>are</span> <span
  m='430550'>identical.</span> <span m='431570'>Then</span> <span
  m='431750'>these</span> <span m='431960'>values</span> <span
  m='432350'>are</span> <span m='432470'>identical.</span> <span
  m='433080'>Then</span> <span m='433220'>these</span> <span
  m='433430'>values</span> <span m='433820'>are</span> <span
  m='433910'>identical.</span> <span m='434900'>These,</span> <span
  m='435800'>and,</span> <span m='436040'>of</span> <span
  m='436160'>course,</span> <span m='436730'>this</span> <span
  m='436940'>one</span> <span m='437120'>is</span> <span
  m='437240'>identical</span> <span m='437750'>to</span> <span
  m='437930'>itself.</span> <span m='439700'>And</span> <span
  m='439880'>that</span> <span m='440150'>then</span> <span m='440480'>is</span>
  <span m='440690'>the</span> <span m='440810'>general</span> <span
  m='441200'>symmetry</span> <span m='442130'>of</span> <span
  m='442700'>a</span> <span m='443450'>linear</span> <span
  m='443840'>phase</span> <span m='445040'>FIR</span> <span
  m='446480'>impulse</span> <span m='446930'>response.</span> </p><p><span
  m='450120'>Well,</span> <span m='450530'>in</span> <span
  m='450620'>fact,</span> <span m='451310'>to</span> <span
  m='452330'>stress</span> <span m='452750'>once</span> <span
  m='453050'>again</span> <span m='453650'>that</span> <span
  m='454430'>the</span> <span m='454670'>phase</span> <span m='455210'>is</span>
  <span m='455420'>indeed</span> <span m='455810'>linear,</span> <span
  m='457250'>we</span> <span m='457400'>can</span> <span
  m='457760'>consider</span> <span m='459170'>generating</span> <span
  m='460190'>a</span> <span m='460430'>unit</span> <span
  m='460760'>sample</span> <span m='461180'>response</span> <span
  m='461750'>or</span> <span m='461840'>impulse</span> <span
  m='462230'>response</span> <span m='462740'>h1</span> <span
  m='463130'>of</span> <span m='463340'>n,</span> <span m='464270'>which</span>
  <span m='464870'>corresponds</span> <span m='465800'>to</span> <span
  m='465980'>this</span> <span m='466190'>unit</span> <span
  m='466490'>sample</span> <span m='466910'>response</span> <span
  m='468440'>shifted</span> <span m='469280'>so</span> <span
  m='469550'>that</span> <span m='469910'>it's</span> <span
  m='470090'>centered</span> <span m='470480'>around</span> <span
  m='470780'>the</span> <span m='470930'>origin,</span> <span
  m='472580'>in</span> <span m='472670'>which</span> <span
  m='472940'>case</span> <span m='473470'>h</span> <span m='473840'>of</span>
  <span m='474320'>n</span> <span m='475740'>is</span> <span
  m='476070'>equal</span> <span m='476550'>to</span> <span m='476880'>h1</span>
  <span m='477570'>of</span> <span m='477870'>n</span> <span
  m='478170'>plus</span> <span m='478950'>capital</span> <span
  m='479430'>N</span> <span m='479730'>minus</span> <span m='480120'>1.</span>
  <span m='480570'>Or</span> <span m='480750'>in</span> <span
  m='480840'>this</span> <span m='480990'>case,</span> <span m='482970'>h</span>
  <span m='483440'>of</span> <span m='483910'>n</span> <span
  m='484380'>is</span> <span m='484560'>h1</span> <span m='485010'>of</span>
  <span m='485130'>n</span> <span m='485580'>shifted</span> <span
  m='486030'>to</span> <span m='486180'>the</span> <span m='486300'>right</span>
  <span m='487290'>by</span> <span m='487500'>4.</span> <span
  m='489060'>And</span> <span m='490710'>consequently,</span> <span
  m='492000'>the</span> <span m='492090'>frequency</span> <span
  m='492690'>response</span> <span m='494130'>for</span> <span
  m='494280'>this</span> <span m='494460'>system,</span> <span
  m='495990'>or</span> <span m='496250'>the</span> <span
  m='496710'>Fourier</span> <span m='496810'>transform</span> <span
  m='497490'>of</span> <span m='497610'>the</span> <span m='497700'>unit</span>
  <span m='497940'>sample</span> <span m='498330'>response</span> <span
  m='499710'>is</span> <span m='500340'>the</span> <span
  m='500500'>Fourier</span> <span m='500820'>transform</span> <span
  m='501750'>of</span> <span m='501900'>the</span> <span m='502020'>unit</span>
  <span m='502260'>sample</span> <span m='502620'>response</span> <span
  m='503100'>of</span> <span m='503190'>this</span> <span
  m='503370'>system</span> <span m='504690'>multiplied</span> <span
  m='505560'>by</span> <span m='505980'>e</span> <span m='506180'>to</span>
  <span m='506340'>the</span> <span m='506460'>j</span> <span
  m='506730'>omega</span> <span m='507400'>capital</span> <span
  m='507930'>N</span> <span m='508080'>minus</span> <span m='508440'>1</span>
  <span m='508620'>over</span> <span m='508830'>2.</span> <span
  m='510270'>That</span> <span m='511020'>is</span> <span m='511470'>just</span>
  <span m='511740'>due</span> <span m='511920'>to</span> <span
  m='512070'>the</span> <span m='512190'>fact</span> <span
  m='512940'>that</span> <span m='513090'>these</span> <span
  m='513330'>two</span> <span m='513480'>unit</span> <span
  m='513809'>sample</span> <span m='514200'>responses</span> <span
  m='514950'>are</span> <span m='515100'>related</span> <span
  m='515580'>to</span> <span m='515730'>each</span> <span
  m='515909'>other</span> <span m='516150'>by</span> <span m='516360'>a</span>
  <span m='516419'>linear</span> <span m='516780'>shift.</span> </p><p><span
  m='518500'>Now,</span> <span m='519120'>this</span> <span
  m='519360'>unit</span> <span m='519630'>sample</span> <span
  m='520020'>response</span> <span m='520530'>is</span> <span
  m='520679'>even.</span> <span m='521850'>That</span> <span
  m='522030'>is</span> <span m='522200'>it's</span> <span m='522360'>even</span>
  <span m='522630'>about</span> <span m='523049'>n</span> <span
  m='523230'>equals</span> <span m='523500'>0.</span> <span
  m='524670'>And</span> <span m='524790'>consequently,</span> <span
  m='526260'>its</span> <span m='526730'>Fourier</span> <span
  m='526860'>transform</span> <span m='527940'>is</span> <span
  m='528660'>a</span> <span m='528750'>real</span> <span
  m='529470'>function</span> <span m='530070'>of</span> <span
  m='530250'>omega.</span> <span m='531810'>So</span> <span
  m='532740'>this</span> <span m='532980'>is</span> <span
  m='533130'>real.</span> <span m='534390'>And</span> <span
  m='534540'>consequently,</span> <span m='535470'>the</span> <span
  m='535590'>phase</span> <span m='536040'>associated</span> <span
  m='537180'>with</span> <span m='537690'>the</span> <span
  m='537960'>causal</span> <span m='538500'>system</span> <span
  m='539190'>h</span> <span m='539460'>of</span> <span m='539580'>n</span> <span
  m='540510'>is</span> <span m='541110'>just</span> <span
  m='541350'>simply</span> <span m='541830'>this</span> <span
  m='542040'>linear</span> <span m='542400'>phase</span> <span
  m='542760'>term,</span> <span m='543260'>e</span> <span m='543385'>to</span>
  <span m='543510'>the</span> <span m='543600'>j</span> <span
  m='543810'>omega</span> <span m='544290'>N</span> <span
  m='544500'>minus</span> <span m='544860'>1</span> <span m='545040'>over</span>
  <span m='545280'>2.</span> <span m='546420'>So</span> <span
  m='547260'>this</span> <span m='547470'>is</span> <span m='547590'>an</span>
  <span m='547710'>argument,</span> <span m='548220'>again,</span> <span
  m='549150'>that</span> <span m='550020'>stresses</span> <span
  m='550590'>the</span> <span m='550710'>fact</span> <span
  m='551490'>that</span> <span m='551910'>if</span> <span m='552720'>the</span>
  <span m='552840'>unit</span> <span m='553110'>sample</span> <span
  m='553470'>response</span> <span m='553980'>has</span> <span
  m='554220'>this</span> <span m='554350'>symmetry,</span> <span
  m='555540'>then</span> <span m='556020'>the</span> <span
  m='556140'>phase</span> <span m='556590'>of</span> <span m='556710'>the</span>
  <span m='556800'>system</span> <span m='557580'>is</span> <span
  m='557730'>linear.</span> </p><p><span m='559470'>Now,</span> <span
  m='559680'>how</span> <span m='559890'>can</span> <span m='560040'>we</span>
  <span m='560160'>exploit</span> <span m='560670'>this</span> <span
  m='561150'>in</span> <span m='561300'>the</span> <span
  m='561420'>implementation</span> <span m='562440'>of</span> <span
  m='564210'>finite</span> <span m='564600'>impulse</span> <span
  m='564990'>response</span> <span m='565440'>systems?</span> <span
  m='567070'>Well,</span> <span m='567570'>let's</span> <span
  m='568140'>look,</span> <span m='568720'>first</span> <span
  m='568980'>of</span> <span m='569130'>all,</span> <span m='569710'>at</span>
  <span m='570360'>the</span> <span m='570600'>general</span> <span
  m='571050'>expression</span> <span m='571950'>for</span> <span
  m='572400'>the</span> <span m='572520'>z</span> <span
  m='572730'>transform</span> <span m='573420'>of</span> <span
  m='573540'>the</span> <span m='573630'>system,</span> <span
  m='574260'>h</span> <span m='574650'>of</span> <span m='575010'>z</span> <span
  m='575370'>given</span> <span m='575670'>by</span> <span m='575900'>a</span>
  <span m='575940'>sum</span> <span m='576420'>of</span> <span
  m='576570'>h</span> <span m='576810'>of</span> <span m='576940'>n</span> <span
  m='577410'>z</span> <span m='577980'>to</span> <span m='578130'>the</span>
  <span m='578220'>minus</span> <span m='578690'>n.</span> <span
  m='580280'>And</span> <span m='580470'>essentially</span> <span
  m='581100'>the</span> <span m='581280'>idea</span> <span m='582180'>in</span>
  <span m='582300'>exploiting</span> <span m='582960'>this</span> <span
  m='583100'>symmetry</span> <span m='584460'>for</span> <span
  m='585120'>the</span> <span m='585270'>implementation</span> <span
  m='586410'>of</span> <span m='587030'>FIR</span> <span
  m='587610'>systems</span> <span m='589020'>is</span> <span
  m='589260'>to</span> <span m='589380'>take</span> <span
  m='589650'>advantage</span> <span m='590160'>of</span> <span
  m='590250'>the</span> <span m='590340'>fact</span> <span
  m='591240'>that</span> <span m='591660'>because</span> <span
  m='593610'>roughly</span> <span m='594270'>half</span> <span
  m='594630'>of</span> <span m='594720'>the</span> <span
  m='594840'>values</span> <span m='595560'>in</span> <span m='595710'>h</span>
  <span m='595845'>of</span> <span m='595980'>n</span> <span
  m='596250'>are</span> <span m='596400'>identical,</span> <span
  m='598540'>we</span> <span m='598960'>should</span> <span m='599290'>be</span>
  <span m='599470'>able</span> <span m='600250'>to</span> <span
  m='600550'>implement</span> <span m='601090'>the</span> <span
  m='601210'>system</span> <span m='601930'>with</span> <span
  m='602380'>essentially</span> <span m='603100'>only</span> <span
  m='603400'>half</span> <span m='603700'>the</span> <span
  m='603820'>number</span> <span m='604120'>of</span> <span
  m='604210'>multiplies</span> <span m='605350'>that</span> <span
  m='605500'>would</span> <span m='605650'>be</span> <span
  m='605800'>required</span> <span m='606790'>in</span> <span
  m='607240'>a</span> <span m='607300'>more</span> <span
  m='607510'>general</span> <span m='607980'>FIR</span> <span
  m='608500'>system.</span> </p><p><span m='610360'>Well,</span> <span
  m='610600'>to</span> <span m='610750'>show</span> <span m='611020'>how</span>
  <span m='611170'>this</span> <span m='611410'>works,</span> <span
  m='612400'>let's</span> <span m='613270'>work</span> <span
  m='613570'>through</span> <span m='613840'>this</span> <span
  m='614320'>for</span> <span m='615310'>the</span> <span m='615400'>case</span>
  <span m='615820'>where</span> <span m='616030'>we</span> <span
  m='616180'>assume</span> <span m='616960'>that</span> <span
  m='617170'>capital</span> <span m='617710'>N,</span> <span
  m='618070'>the</span> <span m='618160'>number</span> <span
  m='618460'>of</span> <span m='618550'>non-zero</span> <span
  m='619090'>points</span> <span m='619630'>in</span> <span
  m='619720'>the</span> <span m='619780'>unit</span> <span
  m='620050'>sample</span> <span m='620440'>response,</span> <span
  m='621730'>is</span> <span m='622180'>even.</span> <span m='624130'>In</span>
  <span m='624250'>the</span> <span m='624340'>previous</span> <span
  m='624730'>example,</span> <span m='625210'>we'd</span> <span
  m='625390'>considered</span> <span m='625810'>capital</span> <span
  m='626230'>N</span> <span m='626380'>odd.</span> <span m='627430'>Here,</span>
  <span m='627970'>in</span> <span m='628150'>working</span> <span
  m='628480'>through</span> <span m='628690'>this</span> <span
  m='628900'>let's</span> <span m='629110'>assume</span> <span
  m='629440'>that</span> <span m='629530'>capital</span> <span
  m='629815'>N</span> <span m='630100'>is</span> <span m='630250'>even.</span>
  <span m='630710'>And</span> <span m='630850'>a</span> <span
  m='630880'>similar</span> <span m='631270'>derivation</span> <span
  m='631960'>would</span> <span m='632080'>apply</span> <span
  m='633100'>and</span> <span m='633220'>has</span> <span m='633340'>gone</span>
  <span m='633580'>through</span> <span m='633760'>in</span> <span
  m='633850'>the</span> <span m='633940'>text</span> <span m='634390'>for</span>
  <span m='634750'>capital</span> <span m='635260'>N</span> <span
  m='635440'>odd.</span> </p><p><span m='637920'>OK,</span> <span
  m='638330'>well,</span> <span m='638750'>we</span> <span m='638930'>can</span>
  <span m='639380'>express</span> <span m='640550'>the</span> <span
  m='640790'>transfer</span> <span m='641330'>function</span> <span
  m='641870'>h</span> <span m='642140'>of</span> <span m='642230'>z</span> <span
  m='643400'>as</span> <span m='643610'>a</span> <span m='643670'>sum</span>
  <span m='644210'>from</span> <span m='644690'>n</span> <span
  m='644840'>equals</span> <span m='645110'>0</span> <span m='645560'>to</span>
  <span m='645710'>capital</span> <span m='646160'>N</span> <span
  m='646280'>over</span> <span m='646520'>2</span> <span m='647270'>minus</span>
  <span m='647690'>1</span> <span m='648130'>of</span> <span m='649010'>h</span>
  <span m='649280'>of</span> <span m='649400'>n</span> <span m='649595'>z</span>
  <span m='649790'>to</span> <span m='649910'>the</span> <span
  m='650000'>minus</span> <span m='650420'>n--</span> <span
  m='651500'>those</span> <span m='651980'>are</span> <span
  m='652820'>the</span> <span m='652910'>first</span> <span
  m='653300'>half</span> <span m='653600'>points,</span> <span
  m='655010'>the</span> <span m='655130'>first</span> <span
  m='655400'>half</span> <span m='655700'>of</span> <span m='655820'>the</span>
  <span m='656450'>non-zero</span> <span m='657050'>points--</span> <span
  m='658280'>plus</span> <span m='658560'>the</span> <span m='658640'>sum</span>
  <span m='659630'>over</span> <span m='660170'>the</span> <span
  m='660290'>second</span> <span m='660710'>half</span> <span
  m='661010'>of</span> <span m='661100'>the</span> <span
  m='661190'>non-zero</span> <span m='661760'>points</span> <span
  m='662630'>from</span> <span m='662810'>capital</span> <span
  m='663260'>N</span> <span m='663380'>over</span> <span m='663590'>2</span>
  <span m='664070'>to</span> <span m='664190'>capital</span> <span
  m='664670'>N</span> <span m='664790'>minus</span> <span m='665180'>1.</span>
  <span m='666350'>And</span> <span m='666470'>basically</span> <span
  m='667070'>where</span> <span m='667220'>we</span> <span
  m='667340'>want</span> <span m='667460'>to</span> <span m='667550'>get</span>
  <span m='667790'>to</span> <span m='668750'>is</span> <span
  m='669710'>to</span> <span m='669860'>exploit</span> <span
  m='670370'>the</span> <span m='670490'>fact</span> <span
  m='671330'>that</span> <span m='671540'>these</span> <span
  m='671840'>points</span> <span m='673310'>are</span> <span
  m='673430'>numerically</span> <span m='674030'>equal</span> <span
  m='674630'>to</span> <span m='674780'>these,</span> <span
  m='675890'>except</span> <span m='676310'>that</span> <span
  m='676460'>the</span> <span m='676610'>index</span> <span
  m='677120'>runs</span> <span m='677420'>in</span> <span m='677510'>the</span>
  <span m='677630'>other</span> <span m='677840'>direction.</span> </p><p><span
  m='679400'>Well</span> <span m='679730'>to</span> <span
  m='679880'>develop</span> <span m='680300'>that</span> <span
  m='680510'>formally,</span> <span m='682100'>let's</span> <span
  m='682580'>manipulate</span> <span m='683240'>this</span> <span
  m='683450'>sum</span> <span m='684620'>by</span> <span m='685790'>using</span>
  <span m='686210'>a</span> <span m='686270'>substitution</span> <span
  m='687020'>of</span> <span m='687080'>variables.</span> <span
  m='688280'>In</span> <span m='688400'>particular,</span> <span
  m='689370'>let's</span> <span m='689510'>make</span> <span
  m='689750'>the</span> <span m='689840'>substitution</span> <span
  m='690560'>of</span> <span m='690620'>variables</span> <span
  m='691790'>that</span> <span m='692030'>r</span> <span m='692660'>is</span>
  <span m='692870'>equal</span> <span m='693260'>to</span> <span
  m='693650'>capital</span> <span m='694190'>N</span> <span
  m='694670'>minus</span> <span m='695090'>1</span> <span
  m='695690'>minus</span> <span m='696050'>little</span> <span
  m='696340'>n,</span> <span m='697190'>or</span> <span
  m='697400'>equivalently</span> <span m='698750'>that</span> <span
  m='698900'>little</span> <span m='699230'>n</span> <span m='700220'>is</span>
  <span m='700370'>equal</span> <span m='700700'>to</span> <span
  m='700850'>capital</span> <span m='701360'>N</span> <span
  m='702350'>minus</span> <span m='702770'>1</span> <span
  m='705240'>minus</span> <span m='705600'>r.</span> <span m='707520'>If</span>
  <span m='707610'>we</span> <span m='707730'>do</span> <span
  m='707940'>that,</span> <span m='708840'>then</span> <span
  m='710220'>changing</span> <span m='710670'>this</span> <span
  m='710820'>to</span> <span m='710970'>a</span> <span
  m='711030'>summation</span> <span m='711660'>on</span> <span
  m='711780'>r,</span> <span m='713010'>where</span> <span m='713250'>we</span>
  <span m='713460'>have</span> <span m='714570'>that</span> <span
  m='715170'>little</span> <span m='715560'>n</span> <span m='716220'>is</span>
  <span m='716370'>equal</span> <span m='716670'>to</span> <span
  m='716790'>capital</span> <span m='717270'>N</span> <span
  m='717390'>over</span> <span m='717630'>2,</span> <span
  m='718980'>little</span> <span m='719145'>n</span> <span
  m='719310'>equal</span> <span m='719570'>to</span> <span
  m='719700'>capital</span> <span m='720180'>N</span> <span
  m='720300'>over</span> <span m='720540'>2,</span> <span m='721430'>r</span>
  <span m='722000'>is</span> <span m='722220'>equal</span> <span
  m='722550'>to</span> <span m='722670'>capital</span> <span m='723120'>N</span>
  <span m='723210'>over</span> <span m='723450'>2</span> <span
  m='723690'>minus</span> <span m='724110'>1,</span> <span m='725070'>as</span>
  <span m='726030'>I've</span> <span m='726150'>indicated</span> <span
  m='726720'>here.</span> <span m='727840'>And</span> <span
  m='727890'>when</span> <span m='728040'>little</span> <span
  m='728310'>n</span> <span m='728490'>is</span> <span m='728640'>equal</span>
  <span m='728850'>to</span> <span m='728970'>capital</span> <span
  m='729450'>N</span> <span m='729570'>minus</span> <span m='729960'>1,</span>
  <span m='730380'>little</span> <span m='731220'>r</span> <span
  m='731820'>is</span> <span m='732000'>equal</span> <span m='732390'>to</span>
  <span m='733170'>0.</span> </p><p><span m='734520'>So</span> <span
  m='735480'>this</span> <span m='735930'>gets</span> <span
  m='736170'>converted</span> <span m='736620'>to</span> <span
  m='736800'>a</span> <span m='736860'>sum</span> <span m='737420'>from</span>
  <span m='737580'>r</span> <span m='737820'>equals</span> <span
  m='738090'>0</span> <span m='739000'>to</span> <span m='739140'>capital</span>
  <span m='739590'>N</span> <span m='739710'>over</span> <span
  m='739920'>2</span> <span m='740130'>minus</span> <span m='740560'>1.</span>
  <span m='741450'>h</span> <span m='742230'>of</span> <span
  m='742710'>what</span> <span m='742950'>was</span> <span m='743450'>n,</span>
  <span m='744180'>which</span> <span m='744390'>is</span> <span
  m='744510'>now</span> <span m='744810'>capital</span> <span
  m='745350'>N</span> <span m='745470'>minus</span> <span m='745830'>1</span>
  <span m='746040'>minus</span> <span m='746430'>r</span> <span
  m='746940'>substituted</span> <span m='747660'>in</span> <span
  m='747810'>here.</span> <span m='748770'>And</span> <span
  m='748890'>then</span> <span m='749550'>capital</span> <span
  m='750030'>N</span> <span m='750240'>minus</span> <span m='750630'>1</span>
  <span m='750990'>minus</span> <span m='751410'>r</span> <span
  m='751860'>again</span> <span m='752460'>substituted</span> <span
  m='753210'>for</span> <span m='753390'>little</span> <span
  m='753590'>n.</span> <span m='755370'>Basically,</span> <span
  m='756450'>what</span> <span m='756570'>we've</span> <span
  m='756780'>done</span> <span m='757050'>is</span> <span
  m='757170'>reduce</span> <span m='757530'>this</span> <span
  m='758120'>to</span> <span m='758310'>a</span> <span m='758370'>sum</span>
  <span m='759210'>over</span> <span m='759420'>the</span> <span
  m='759510'>same</span> <span m='759840'>limits</span> <span
  m='760290'>as</span> <span m='760470'>we</span> <span m='760620'>have</span>
  <span m='760920'>here</span> <span m='761700'>and</span> <span
  m='761850'>with</span> <span m='762390'>the</span> <span
  m='762720'>indices</span> <span m='763350'>running</span> <span
  m='763860'>in</span> <span m='763980'>the</span> <span
  m='764100'>opposite</span> <span m='764580'>direction.</span> </p><p><span
  m='765900'>And</span> <span m='766020'>now,</span> <span m='766650'>we</span>
  <span m='766830'>can</span> <span m='766980'>recognize</span> <span
  m='768930'>that</span> <span m='769440'>because</span> <span
  m='769950'>of</span> <span m='770040'>the</span> <span
  m='770130'>symmetry</span> <span m='770730'>property,</span> <span
  m='771630'>because</span> <span m='772020'>of</span> <span
  m='772110'>the</span> <span m='772230'>fact</span> <span
  m='772560'>that</span> <span m='772650'>we're</span> <span
  m='772770'>talking</span> <span m='773130'>about</span> <span
  m='773310'>a</span> <span m='773370'>linear</span> <span
  m='773760'>phase</span> <span m='774060'>system,</span> <span
  m='775890'>h</span> <span m='776280'>of</span> <span m='776430'>capital</span>
  <span m='776970'>N</span> <span m='777360'>minus</span> <span
  m='777780'>1</span> <span m='778230'>minus</span> <span m='778680'>r</span>
  <span m='779640'>is</span> <span m='779820'>equal</span> <span
  m='780180'>to</span> <span m='783580'>h</span> <span m='783820'>of</span>
  <span m='783950'>r.</span> <span m='785530'>That's</span> <span
  m='785980'>the</span> <span m='786100'>symmetry</span> <span
  m='786610'>property</span> <span m='787630'>that</span> <span
  m='788020'>corresponds</span> <span m='789040'>to</span> <span
  m='789160'>stating</span> <span m='789670'>that</span> <span
  m='789790'>the</span> <span m='789910'>system</span> <span
  m='790300'>is</span> <span m='790390'>linear</span> <span
  m='790720'>phase.</span> </p><p><span m='793100'>All</span> <span
  m='793190'>right,</span> <span m='793550'>well,</span> <span
  m='794300'>so</span> <span m='794870'>here</span> <span m='795110'>we</span>
  <span m='795260'>have</span> <span m='795530'>a</span> <span
  m='795560'>sum</span> <span m='795890'>from</span> <span m='796030'>n</span>
  <span m='796170'>equals</span> <span m='796400'>0</span> <span
  m='796610'>to</span> <span m='796820'>N</span> <span m='796970'>over</span>
  <span m='797180'>2</span> <span m='797390'>minus</span> <span
  m='797780'>1.</span> <span m='798160'>Some</span> <span
  m='798350'>things</span> <span m='798650'>involving</span> <span
  m='799190'>h</span> <span m='799385'>of</span> <span m='799580'>n.</span>
  <span m='800480'>Here</span> <span m='800630'>we</span> <span
  m='800780'>have</span> <span m='801000'>a</span> <span m='801020'>sum</span>
  <span m='801440'>from</span> <span m='801920'>r</span> <span
  m='802160'>equals</span> <span m='802430'>0</span> <span m='803200'>to</span>
  <span m='803300'>N</span> <span m='803450'>over</span> <span
  m='803660'>2</span> <span m='803870'>minus</span> <span m='804230'>1,</span>
  <span m='804560'>some</span> <span m='804740'>things</span> <span
  m='805010'>involving</span> <span m='805490'>h</span> <span
  m='805730'>of</span> <span m='805850'>r.</span> <span m='807870'>This</span>
  <span m='808490'>index</span> <span m='808910'>of</span> <span
  m='809000'>summation,</span> <span m='809510'>of</span> <span
  m='809600'>course,</span> <span m='809900'>is</span> <span
  m='809990'>just</span> <span m='810200'>a</span> <span m='810260'>dummy</span>
  <span m='810590'>variable.</span> <span m='811590'>And</span> <span
  m='811730'>we</span> <span m='811880'>can</span> <span
  m='812030'>change</span> <span m='812390'>it</span> <span
  m='812480'>back</span> <span m='812720'>to</span> <span m='812840'>n</span>
  <span m='813050'>if</span> <span m='813170'>we</span> <span
  m='813290'>want</span> <span m='813560'>to,</span> <span
  m='814100'>which</span> <span m='814280'>we</span> <span m='814400'>do.</span>
  </p><p><span m='815570'>So</span> <span m='816800'>rewriting</span> <span
  m='817760'>these</span> <span m='818060'>two</span> <span
  m='818300'>sum,</span> <span m='818810'>in</span> <span
  m='818900'>particular</span> <span m='819740'>rewriting</span> <span
  m='820340'>this</span> <span m='820580'>one</span> <span m='821150'>in</span>
  <span m='821300'>terms</span> <span m='822050'>now</span> <span
  m='822410'>of</span> <span m='822530'>a</span> <span
  m='822590'>summation</span> <span m='823190'>on</span> <span
  m='823340'>n,</span> <span m='824540'>this</span> <span
  m='825020'>becomes</span> <span m='825710'>the</span> <span
  m='825830'>sum</span> <span m='826190'>from</span> <span m='826340'>n</span>
  <span m='826490'>equals</span> <span m='826760'>0</span> <span
  m='827810'>to</span> <span m='827960'>capital</span> <span m='828410'>N</span>
  <span m='828500'>over</span> <span m='828710'>2</span> <span
  m='828890'>minus</span> <span m='829310'>1,</span> <span m='829850'>h</span>
  <span m='830660'>of</span> <span m='830780'>n</span> <span m='831170'>z</span>
  <span m='831500'>to</span> <span m='831620'>the</span> <span
  m='831710'>minus</span> <span m='832130'>capital</span> <span
  m='832610'>N</span> <span m='832790'>minus</span> <span m='833150'>1</span>
  <span m='833690'>minus</span> <span m='834060'>little</span> <span
  m='834350'>n.</span> <span m='835480'>This</span> <span m='835670'>sum,</span>
  <span m='836690'>of</span> <span m='836810'>course,</span> <span
  m='837350'>stays</span> <span m='837770'>the</span> <span
  m='837860'>same.</span> <span m='839090'>And</span> <span
  m='839210'>now,</span> <span m='839750'>because</span> <span
  m='840500'>we</span> <span m='840680'>have</span> <span m='841070'>h</span>
  <span m='841200'>of</span> <span m='841330'>n</span> <span
  m='841940'>appearing</span> <span m='842420'>in</span> <span
  m='842510'>both</span> <span m='842810'>of</span> <span
  m='842900'>these</span> <span m='843080'>sums,</span> <span
  m='844340'>we</span> <span m='844460'>can</span> <span
  m='844640'>combine</span> <span m='845090'>this</span> <span
  m='845270'>together</span> <span m='846320'>into</span> <span
  m='846590'>a</span> <span m='846650'>single</span> <span
  m='847010'>summation,</span> <span m='848540'>from</span> <span
  m='848720'>0</span> <span m='849125'>to</span> <span m='849710'>N</span> <span
  m='849830'>over</span> <span m='850040'>2</span> <span m='850250'>minus</span>
  <span m='850640'>1</span> <span m='851067'>of</span> <span m='852590'>h</span>
  <span m='852860'>of</span> <span m='852980'>n,</span> <span
  m='853730'>the</span> <span m='853850'>values</span> <span
  m='854510'>in</span> <span m='854660'>the</span> <span m='854720'>unit</span>
  <span m='855020'>sample</span> <span m='855410'>response,</span> <span
  m='857260'>times</span> <span m='858030'>z</span> <span m='858340'>to</span>
  <span m='858460'>the</span> <span m='858550'>minus</span> <span
  m='858970'>n</span> <span m='859540'>plus</span> <span m='859830'>z</span>
  <span m='859970'>to</span> <span m='860110'>the</span> <span
  m='860230'>minus</span> <span m='860680'>capital</span> <span
  m='861190'>N</span> <span m='861700'>minus</span> <span m='862090'>1</span>
  <span m='862690'>minus</span> <span m='863020'>little</span> <span
  m='863320'>n.</span> </p><p><span m='864880'>Notice</span> <span
  m='865300'>now</span> <span m='865930'>that</span> <span m='866710'>we</span>
  <span m='867100'>only</span> <span m='868000'>have</span> <span
  m='868760'>in</span> <span m='868960'>this</span> <span
  m='869110'>summation</span> <span m='871140'>half</span> <span
  m='871710'>the</span> <span m='871830'>terms</span> <span
  m='872700'>that</span> <span m='872820'>we</span> <span m='873000'>had</span>
  <span m='873180'>originally.</span> <span m='873810'>In</span> <span
  m='873930'>other</span> <span m='874110'>words,</span> <span
  m='874540'>there</span> <span m='874770'>are</span> <span
  m='875610'>capital</span> <span m='876060'>N</span> <span
  m='876190'>over</span> <span m='876450'>2</span> <span
  m='877560'>different</span> <span m='878190'>coefficients</span> <span
  m='879360'>that</span> <span m='879480'>we're</span> <span
  m='879630'>using,</span> <span m='880580'>whereas</span> <span
  m='881230'>in</span> <span m='881430'>the</span> <span
  m='882150'>direct</span> <span m='882510'>form</span> <span
  m='882840'>implementation,</span> <span m='884220'>there</span> <span
  m='884400'>were</span> <span m='884550'>capital</span> <span
  m='885030'>N</span> <span m='885780'>coefficients</span> <span
  m='886440'>that</span> <span m='886530'>we</span> <span m='886710'>were</span>
  <span m='886800'>using.</span> <span m='887610'>And</span> <span
  m='887760'>here,</span> <span m='887970'>we're</span> <span
  m='888140'>exploiting</span> <span m='888990'>the</span> <span
  m='889080'>symmetry</span> <span m='889830'>in</span> <span
  m='889950'>the</span> <span m='890040'>coefficients.</span> </p><p><span
  m='892530'>Well,</span> <span m='892970'>let's</span> <span
  m='893180'>see</span> <span m='893420'>what</span> <span
  m='893600'>this</span> <span m='893780'>implies</span> <span
  m='894620'>in</span> <span m='894770'>terms</span> <span m='895220'>of</span>
  <span m='895340'>a</span> <span m='895370'>filter</span> <span
  m='895760'>structure.</span> <span m='897610'>Here,</span> <span
  m='898160'>I've</span> <span m='898520'>simply</span> <span
  m='898970'>rewritten,</span> <span m='899900'>again,</span> <span
  m='900870'>the</span> <span m='901070'>general</span> <span
  m='901520'>form</span> <span m='902210'>for</span> <span m='903200'>the</span>
  <span m='903320'>transfer</span> <span m='903830'>function</span> <span
  m='904940'>assuming</span> <span m='905420'>that</span> <span
  m='905570'>the</span> <span m='905660'>system</span> <span
  m='906050'>is</span> <span m='906170'>linear</span> <span
  m='906530'>phase,</span> <span m='907590'>as</span> <span
  m='907940'>we've</span> <span m='908120'>just</span> <span
  m='908300'>previously</span> <span m='908900'>worked</span> <span
  m='909230'>out.</span> <span m='909860'>This</span> <span m='910040'>is</span>
  <span m='910130'>just</span> <span m='910310'>simply</span> <span
  m='910730'>a</span> <span m='910760'>rewrite</span> <span m='911420'>of</span>
  <span m='911870'>the</span> <span m='911990'>previous</span> <span
  m='913280'>expression.</span> </p><p><span m='914720'>And</span> <span
  m='914840'>let's</span> <span m='915080'>look</span> <span
  m='915290'>at</span> <span m='915410'>this,</span> <span m='916250'>for</span>
  <span m='916460'>example,</span> <span m='917030'>I</span> <span
  m='917870'>had</span> <span m='917990'>assumed</span> <span
  m='918430'>that</span> <span m='918740'>that</span> <span
  m='918860'>capital</span> <span m='919310'>N</span> <span
  m='919460'>was</span> <span m='920330'>even.</span> <span m='921230'>So</span>
  <span m='921830'>let's</span> <span m='922130'>choose</span> <span
  m='922550'>as</span> <span m='922700'>an</span> <span
  m='922790'>example</span> <span m='923330'>capital</span> <span
  m='923770'>N</span> <span m='923900'>equal</span> <span m='924200'>to</span>
  <span m='924320'>8,</span> <span m='925700'>in</span> <span
  m='925790'>which</span> <span m='926060'>case</span> <span
  m='926870'>this</span> <span m='927080'>expression</span> <span
  m='927680'>becomes</span> <span m='928340'>a</span> <span
  m='928430'>sum</span> <span m='929250'>from</span> <span m='929400'>n</span>
  <span m='929600'>equals</span> <span m='929870'>0</span> <span
  m='930320'>to</span> <span m='930470'>3,</span> <span m='931100'>h</span>
  <span m='932240'>of</span> <span m='932420'>n,</span> <span
  m='933050'>z</span> <span m='933370'>to</span> <span m='933470'>the</span>
  <span m='933590'>minus</span> <span m='934070'>n</span> <span
  m='934460'>plus</span> <span m='934730'>z</span> <span m='935000'>to</span>
  <span m='935120'>the</span> <span m='935240'>minus--</span> <span
  m='936710'>capital</span> <span m='937130'>N</span> <span
  m='937250'>minus</span> <span m='937550'>1</span> <span m='937730'>is</span>
  <span m='937810'>7,</span> <span m='938240'>so</span> <span
  m='938510'>minus</span> <span m='938810'>7</span> <span
  m='939560'>minus</span> <span m='939950'>n.</span> </p><p><span
  m='943050'>Well,</span> <span m='943500'>how</span> <span
  m='943650'>many</span> <span m='943860'>delays</span> <span
  m='945210'>are</span> <span m='945660'>involved</span> <span
  m='946560'>in</span> <span m='946890'>implementing</span> <span
  m='947550'>this</span> <span m='947660'>system</span> <span
  m='948090'>function?</span> <span m='950220'>Apparently,</span> <span
  m='951300'>there</span> <span m='951720'>are</span> <span
  m='952590'>seven</span> <span m='953340'>delays</span> <span
  m='953850'>involved</span> <span m='955770'>whether</span> <span
  m='956190'>or</span> <span m='956220'>not</span> <span m='956700'>the</span>
  <span m='956820'>system</span> <span m='957210'>is</span> <span
  m='957300'>linear</span> <span m='957660'>phase.</span> <span
  m='958290'>And</span> <span m='958500'>that</span> <span
  m='958740'>shouldn't</span> <span m='959070'>be</span> <span
  m='959220'>surprising</span> <span m='959910'>because</span> <span
  m='960840'>the</span> <span m='960930'>length</span> <span
  m='961230'>of</span> <span m='961320'>the</span> <span
  m='961440'>impulse</span> <span m='961890'>response</span> <span
  m='962820'>is</span> <span m='962910'>still</span> <span m='963260'>8.</span>
  <span m='964700'>So</span> <span m='965330'>seven</span> <span
  m='965720'>delays</span> <span m='966230'>in</span> <span
  m='966350'>general</span> <span m='966830'>are</span> <span
  m='966980'>required,</span> <span m='968120'>but</span> <span
  m='968420'>only</span> <span m='968810'>four</span> <span
  m='970040'>coefficients</span> <span m='970790'>are</span> <span
  m='970880'>required.</span> </p><p><span m='972770'>And</span> <span
  m='972980'>to</span> <span m='973100'>see</span> <span m='973340'>what</span>
  <span m='973550'>structure</span> <span m='974180'>is</span> <span
  m='974360'>implied</span> <span m='974810'>by</span> <span
  m='975050'>this,</span> <span m='975980'>we</span> <span
  m='976070'>recognize</span> <span m='977210'>that</span> <span
  m='978060'>h</span> <span m='978350'>of</span> <span m='978500'>z</span> <span
  m='979070'>is</span> <span m='979250'>constructed</span> <span
  m='981140'>by</span> <span m='981830'>summing</span> <span m='983030'>a</span>
  <span m='983090'>system</span> <span m='984680'>which</span> <span
  m='984920'>corresponds</span> <span m='985700'>to</span> <span
  m='985880'>a</span> <span m='985940'>delay.</span> <span
  m='986900'>Looking</span> <span m='987200'>at</span> <span
  m='987290'>this</span> <span m='987470'>expression</span> <span
  m='987950'>for</span> <span m='988130'>n</span> <span m='988380'>equal</span>
  <span m='988550'>0,</span> <span m='990410'>no</span> <span
  m='990650'>delay.</span> <span m='991650'>n</span> <span
  m='991820'>equal</span> <span m='992040'>0</span> <span
  m='992300'>substituted</span> <span m='993020'>in</span> <span
  m='993440'>gives</span> <span m='993710'>us</span> <span m='993820'>a</span>
  <span m='993920'>transfer</span> <span m='994820'>function</span> <span
  m='995240'>of</span> <span m='995350'>1.</span> <span m='996440'>Plus</span>
  <span m='996950'>a</span> <span m='997040'>delay</span> <span
  m='998110'>with</span> <span m='998300'>n</span> <span m='998440'>equal</span>
  <span m='998630'>0</span> <span m='998930'>substituted</span> <span
  m='999650'>in</span> <span m='1000100'>of</span> <span m='1000670'>7.</span>
  <span m='1004600'>The</span> <span m='1004750'>output</span> <span
  m='1005050'>of</span> <span m='1005140'>those</span> <span
  m='1005380'>two</span> <span m='1005560'>delays</span> <span
  m='1006250'>added</span> <span m='1006550'>together</span> <span
  m='1007210'>and</span> <span m='1007360'>multiplied</span> <span
  m='1008110'>by</span> <span m='1008590'>h</span> <span m='1008980'>of</span>
  <span m='1009300'>0,</span> <span m='1010360'>and</span> <span
  m='1011440'>consequently,</span> <span m='1012520'>if</span> <span
  m='1012670'>we</span> <span m='1012790'>consider</span> <span
  m='1013450'>a</span> <span m='1013510'>chain</span> <span
  m='1013870'>of</span> <span m='1013990'>delays</span> <span
  m='1015310'>as</span> <span m='1015460'>I've</span> <span
  m='1015610'>drawn</span> <span m='1015970'>here,</span> <span
  m='1017440'>we</span> <span m='1017560'>have</span> <span
  m='1018460'>the</span> <span m='1018610'>output</span> <span
  m='1019780'>before</span> <span m='1020170'>we</span> <span
  m='1020260'>go</span> <span m='1020470'>through</span> <span
  m='1020710'>any</span> <span m='1020890'>delays</span> <span
  m='1023290'>added</span> <span m='1024550'>to</span> <span
  m='1025240'>the</span> <span m='1025420'>output</span> <span
  m='1027000'>from</span> <span m='1027869'>the</span> <span
  m='1027960'>seventh</span> <span m='1028530'>delay--</span> <span
  m='1029550'>that's</span> <span m='1029910'>looking</span> <span
  m='1030240'>at</span> <span m='1030329'>this</span> <span
  m='1030510'>expression</span> <span m='1031050'>for</span> <span
  m='1031230'>n</span> <span m='1031329'>equal</span> <span
  m='1031589'>0--</span> <span m='1033339'>and</span> <span
  m='1034030'>the</span> <span m='1034150'>result</span> <span
  m='1034569'>of</span> <span m='1034660'>that</span> <span
  m='1034869'>summation</span> <span m='1036010'>multiplied</span> <span
  m='1036790'>by</span> <span m='1037300'>h</span> <span m='1037599'>of</span>
  <span m='1037900'>0</span> <span m='1043770'>to</span> <span
  m='1043859'>form</span> <span m='1044940'>the</span> <span
  m='1045030'>first</span> <span m='1045359'>term</span> <span
  m='1045690'>in</span> <span m='1045780'>this</span> <span
  m='1045970'>sum.</span> </p><p><span m='1047630'>To</span> <span
  m='1047829'>form</span> <span m='1048119'>the</span> <span
  m='1048200'>next</span> <span m='1048500'>term</span> <span
  m='1048770'>in</span> <span m='1048870'>the</span> <span
  m='1048950'>sum</span> <span m='1049310'>for</span> <span m='1049520'>n</span>
  <span m='1049700'>equals</span> <span m='1049970'>1,</span> <span
  m='1051180'>we</span> <span m='1051230'>have</span> <span
  m='1052520'>the</span> <span m='1052670'>output</span> <span
  m='1053030'>of</span> <span m='1053120'>one</span> <span
  m='1053360'>delay</span> <span m='1054920'>plus</span> <span
  m='1055370'>the</span> <span m='1055550'>output</span> <span
  m='1056000'>from</span> <span m='1056210'>the</span> <span
  m='1056300'>7th</span> <span m='1057110'>minus</span> <span
  m='1057560'>1th</span> <span m='1058130'>delay.</span> <span
  m='1058640'>That</span> <span m='1058820'>is</span> <span
  m='1058940'>the</span> <span m='1059030'>6th</span> <span
  m='1059510'>delay.</span> <span m='1060680'>So</span> <span
  m='1060950'>we</span> <span m='1061130'>have</span> <span
  m='1062150'>this</span> <span m='1062390'>output,</span> <span
  m='1063140'>the</span> <span m='1063260'>output</span> <span
  m='1063650'>from</span> <span m='1063800'>the</span> <span
  m='1063890'>first</span> <span m='1064220'>delay,</span> <span
  m='1065970'>and</span> <span m='1066050'>this</span> <span
  m='1066290'>output,</span> <span m='1067250'>the</span> <span
  m='1067400'>output</span> <span m='1067790'>from</span> <span
  m='1068000'>the</span> <span m='1068110'>6th</span> <span
  m='1068600'>delay.</span> <span m='1071550'>And</span> <span
  m='1072630'>now</span> <span m='1072930'>that</span> <span
  m='1073320'>is</span> <span m='1073500'>multiplied</span> <span
  m='1075420'>by</span> <span m='1077130'>h</span> <span m='1077580'>of</span>
  <span m='1077730'>1</span> <span m='1078750'>coefficient,</span> <span
  m='1079510'>which</span> <span m='1079620'>is</span> <span
  m='1079710'>h</span> <span m='1079950'>of</span> <span m='1080100'>1,</span>
  <span m='1081920'>to</span> <span m='1082020'>form</span> <span
  m='1082770'>the</span> <span m='1082860'>next</span> <span
  m='1083160'>term</span> <span m='1083430'>in</span> <span
  m='1083520'>the</span> <span m='1083610'>sum.</span> </p><p><span
  m='1084810'>And</span> <span m='1085470'>if</span> <span m='1085650'>we</span>
  <span m='1085770'>go</span> <span m='1086040'>through</span> <span
  m='1086580'>the</span> <span m='1086850'>remaining</span> <span
  m='1087660'>terms</span> <span m='1088020'>in</span> <span
  m='1088110'>the</span> <span m='1088200'>sum,</span> <span
  m='1089310'>we</span> <span m='1089430'>have</span> <span
  m='1089640'>the</span> <span m='1089760'>output</span> <span
  m='1090120'>from</span> <span m='1090300'>the</span> <span
  m='1090390'>2nd</span> <span m='1090750'>delay</span> <span
  m='1091380'>and</span> <span m='1091500'>the</span> <span
  m='1091620'>output</span> <span m='1092010'>from</span> <span
  m='1092190'>the</span> <span m='1092280'>5th</span> <span
  m='1092610'>delay</span> <span m='1093720'>added</span> <span
  m='1093990'>together.</span> <span m='1096520'>That</span> <span
  m='1097030'>multiplied</span> <span m='1097870'>by</span> <span
  m='1098410'>h</span> <span m='1098710'>of</span> <span m='1098840'>2.</span>
  <span m='1100940'>The</span> <span m='1101090'>output</span> <span
  m='1101570'>from</span> <span m='1101960'>the</span> <span
  m='1102830'>3rd</span> <span m='1103280'>delay</span> <span
  m='1105130'>and</span> <span m='1105580'>the</span> <span
  m='1105730'>output</span> <span m='1106120'>from</span> <span
  m='1106330'>the</span> <span m='1106420'>4th</span> <span
  m='1106810'>delay</span> <span m='1109880'>added</span> <span
  m='1110180'>together</span> <span m='1110990'>and</span> <span
  m='1111140'>that</span> <span m='1111650'>multiplied</span> <span
  m='1112370'>by</span> <span m='1112760'>h</span> <span m='1112970'>of</span>
  <span m='1113180'>3.</span> <span m='1114440'>That</span> <span
  m='1114650'>forms</span> <span m='1115040'>the</span> <span
  m='1115190'>individual</span> <span m='1115760'>terms</span> <span
  m='1116180'>in</span> <span m='1116270'>this</span> <span
  m='1116420'>sum.</span> <span m='1117690'>And</span> <span
  m='1117710'>now</span> <span m='1118280'>we</span> <span
  m='1118430'>want</span> <span m='1118640'>finally</span> <span
  m='1119360'>to</span> <span m='1119510'>add</span> <span
  m='1119780'>those</span> <span m='1120080'>together.</span> <span
  m='1121260'>So</span> <span m='1122420'>we</span> <span m='1122600'>can</span>
  <span m='1123290'>simply</span> <span m='1123800'>add</span> <span
  m='1124070'>those</span> <span m='1124310'>together</span> <span
  m='1125480'>at</span> <span m='1125630'>their</span> <span
  m='1125840'>outputs</span> <span m='1130030'>to</span> <span
  m='1130150'>form</span> <span m='1131020'>the</span> <span
  m='1131170'>output</span> <span m='1132850'>y</span> <span
  m='1133260'>of</span> <span m='1133390'>n.</span> </p><p><span
  m='1135670'>So</span> <span m='1136290'>here</span> <span
  m='1136560'>is</span> <span m='1136710'>a</span> <span
  m='1136770'>structure</span> <span m='1138450'>which</span> <span
  m='1139290'>implements</span> <span m='1140070'>a</span> <span
  m='1140130'>finite</span> <span m='1140550'>impulse</span> <span
  m='1140940'>response</span> <span m='1141510'>system</span> <span
  m='1142740'>of</span> <span m='1142950'>order</span> <span
  m='1143290'>8,</span> <span m='1143700'>or</span> <span m='1143850'>of</span>
  <span m='1143940'>length</span> <span m='1144240'>8.</span> <span
  m='1145650'>It</span> <span m='1145770'>involves</span> <span
  m='1146580'>seven</span> <span m='1147000'>delays,</span> <span
  m='1147570'>which</span> <span m='1147720'>of</span> <span
  m='1147810'>course</span> <span m='1148080'>the</span> <span
  m='1148170'>direct</span> <span m='1148500'>form</span> <span
  m='1148830'>also</span> <span m='1149190'>involves.</span> <span
  m='1150270'>But</span> <span m='1150420'>the</span> <span
  m='1150540'>important</span> <span m='1151020'>aspect</span> <span
  m='1151620'>of</span> <span m='1151770'>it</span> <span m='1152340'>is</span>
  <span m='1152520'>that</span> <span m='1152940'>it</span> <span
  m='1153090'>involves</span> <span m='1154200'>only</span> <span
  m='1154530'>half</span> <span m='1154830'>the</span> <span
  m='1154920'>number</span> <span m='1155250'>of</span> <span
  m='1155310'>multiplies</span> <span m='1156600'>that</span> <span
  m='1157110'>the</span> <span m='1157320'>direct</span> <span
  m='1157710'>form</span> <span m='1158490'>would</span> <span
  m='1158940'>normally</span> <span m='1159420'>require.</span> <span
  m='1160500'>Taking</span> <span m='1160800'>advantage</span> <span
  m='1161370'>of</span> <span m='1161460'>the</span> <span
  m='1161580'>fact</span> <span m='1161910'>that</span> <span
  m='1162000'>it's</span> <span m='1162120'>a</span> <span
  m='1162180'>linear</span> <span m='1162540'>phase</span> <span
  m='1162870'>system</span> <span m='1163320'>then,</span> <span
  m='1164130'>we're</span> <span m='1164310'>able</span> <span
  m='1164970'>to</span> <span m='1165240'>implement</span> <span
  m='1165780'>the</span> <span m='1165880'>system</span> <span
  m='1166500'>with</span> <span m='1166680'>half</span> <span
  m='1166980'>the</span> <span m='1167070'>number</span> <span
  m='1167370'>of</span> <span m='1167430'>multiplies</span> <span
  m='1168160'>than</span> <span m='1168360'>would</span> <span
  m='1168540'>be</span> <span m='1168660'>required</span> <span
  m='1169200'>in</span> <span m='1169290'>general.</span> </p><p><span
  m='1171370'>All</span> <span m='1171470'>right,</span> <span
  m='1171630'>so</span> <span m='1171900'>this</span> <span
  m='1172110'>is</span> <span m='1172260'>one</span> <span
  m='1172680'>structure.</span> <span m='1173550'>I</span> <span
  m='1173790'>stress</span> <span m='1174210'>again</span> <span
  m='1175080'>that</span> <span m='1175290'>it's</span> <span
  m='1175470'>not</span> <span m='1175680'>the</span> <span
  m='1175830'>only</span> <span m='1176100'>structure</span> <span
  m='1176730'>for</span> <span m='1177210'>implementing</span> <span
  m='1177750'>a</span> <span m='1177810'>linear</span> <span
  m='1178140'>phase</span> <span m='1178440'>system.</span> <span
  m='1179490'>Clearly,</span> <span m='1180330'>we</span> <span
  m='1180450'>can</span> <span m='1180600'>generate</span> <span
  m='1181230'>another</span> <span m='1181590'>structure,</span> <span
  m='1182940'>linear</span> <span m='1183300'>phase</span> <span
  m='1183570'>structure,</span> <span m='1184620'>by</span> <span
  m='1184800'>simply</span> <span m='1185250'>applying</span> <span
  m='1185670'>the</span> <span m='1185760'>transposition</span> <span
  m='1186540'>theorem</span> <span m='1187380'>to</span> <span
  m='1187500'>this</span> <span m='1187680'>structure.</span> <span
  m='1188370'>And</span> <span m='1188550'>we</span> <span
  m='1188670'>would</span> <span m='1188820'>end</span> <span
  m='1189060'>up</span> <span m='1189540'>with</span> <span m='1189750'>a</span>
  <span m='1189840'>transposed</span> <span m='1190530'>configuration.</span>
  <span m='1191550'>And</span> <span m='1191700'>an</span> <span
  m='1191820'>example</span> <span m='1192300'>of</span> <span
  m='1192390'>that</span> <span m='1192750'>is</span> <span
  m='1192870'>shown</span> <span m='1193170'>in</span> <span
  m='1193260'>the</span> <span m='1193350'>text.</span> <span
  m='1193900'>I</span> <span m='1194000'>won't</span> <span
  m='1194070'>bother</span> <span m='1194370'>going</span> <span
  m='1194610'>through</span> <span m='1194880'>it.</span> <span
  m='1195520'>But</span> <span m='1195810'>the</span> <span
  m='1195960'>important</span> <span m='1196410'>aspect</span> <span
  m='1196980'>here</span> <span m='1197730'>is</span> <span
  m='1197940'>that</span> <span m='1198470'>we</span> <span
  m='1198600'>were</span> <span m='1198780'>able</span> <span
  m='1199110'>to</span> <span m='1199290'>exploit--</span> <span
  m='1200490'>in</span> <span m='1200580'>the</span> <span
  m='1200640'>case</span> <span m='1200910'>a</span> <span
  m='1201000'>finite</span> <span m='1201450'>impulse</span> <span
  m='1201840'>response</span> <span m='1202290'>systems</span> <span
  m='1203200'>we're</span> <span m='1203370'>able</span> <span
  m='1203610'>to</span> <span m='1203790'>exploit</span> <span
  m='1204840'>the</span> <span m='1205410'>linear</span> <span
  m='1205770'>phase</span> <span m='1206130'>characteristics</span> <span
  m='1207120'>of</span> <span m='1207270'>the</span> <span
  m='1207390'>system,</span> <span m='1207870'>if</span> <span
  m='1208470'>we're</span> <span m='1208590'>talking</span> <span
  m='1209010'>about</span> <span m='1209250'>a</span> <span
  m='1209280'>system</span> <span m='1209760'>that</span> <span
  m='1209880'>is</span> <span m='1210030'>linear</span> <span
  m='1210360'>phase.</span> </p><p><span m='1213980'>The</span> <span
  m='1214050'>second</span> <span m='1214890'>structure</span> <span
  m='1216150'>that</span> <span m='1216990'>is</span> <span
  m='1218860'>peculiar</span> <span m='1219670'>to</span> <span
  m='1219970'>find</span> <span m='1220320'>an</span> <span
  m='1220420'>impulse</span> <span m='1220840'>response</span> <span
  m='1221320'>systems</span> <span m='1222610'>and</span> <span
  m='1223180'>in</span> <span m='1223330'>some</span> <span
  m='1223600'>instances</span> <span m='1224470'>has</span> <span
  m='1225040'>some</span> <span m='1225280'>advantages</span> <span
  m='1226660'>is</span> <span m='1226810'>a</span> <span
  m='1226870'>structure</span> <span m='1227800'>that</span> <span
  m='1228280'>is</span> <span m='1228670'>often</span> <span
  m='1229030'>referred</span> <span m='1229510'>to</span> <span
  m='1230020'>as</span> <span m='1230500'>a</span> <span
  m='1230560'>frequency</span> <span m='1231130'>sampling</span> <span
  m='1231670'>structure.</span> <span m='1232870'>The</span> <span
  m='1232990'>reason</span> <span m='1233320'>for</span> <span
  m='1233470'>that</span> <span m='1233980'>being</span> <span
  m='1234880'>that</span> <span m='1235030'>the</span> <span
  m='1235150'>coefficients</span> <span m='1235870'>in</span> <span
  m='1235930'>the</span> <span m='1236020'>structure</span> <span
  m='1237190'>correspond</span> <span m='1238120'>to</span> <span
  m='1238270'>samples</span> <span m='1239230'>of</span> <span
  m='1239830'>the</span> <span m='1239920'>frequency</span> <span
  m='1240490'>response</span> <span m='1241030'>of</span> <span
  m='1241120'>the</span> <span m='1241210'>system.</span> <span
  m='1242140'>And</span> <span m='1242260'>I'll</span> <span
  m='1242410'>indicate</span> <span m='1242860'>in</span> <span
  m='1242980'>a</span> <span m='1243010'>few</span> <span
  m='1243220'>minutes</span> <span m='1243580'>why</span> <span
  m='1244240'>that</span> <span m='1244840'>might</span> <span
  m='1245110'>be</span> <span m='1245290'>an</span> <span
  m='1245380'>advantage.</span> <span m='1246340'>But</span> <span
  m='1246520'>first</span> <span m='1247000'>let's</span> <span
  m='1247480'>look</span> <span m='1247840'>at</span> <span
  m='1248440'>what</span> <span m='1248800'>the</span> <span
  m='1248920'>specific</span> <span m='1249490'>structure</span> <span
  m='1250000'>is</span> <span m='1250180'>that's</span> <span
  m='1250390'>involved.</span> </p><p><span m='1252690'>A</span> <span
  m='1253170'>frequency</span> <span m='1253710'>sampling</span> <span
  m='1254220'>structure</span> <span m='1255720'>is</span> <span
  m='1255900'>derived</span> <span m='1256620'>by</span> <span
  m='1257460'>essentially</span> <span m='1261020'>implementing</span> <span
  m='1261920'>the</span> <span m='1262040'>system,</span> <span
  m='1262700'>or</span> <span m='1262970'>inquiry</span> <span
  m='1263410'>as</span> <span m='1263540'>to</span> <span
  m='1263660'>what</span> <span m='1263840'>the</span> <span
  m='1263960'>implementation</span> <span m='1264770'>would</span> <span
  m='1264920'>be,</span> <span m='1265940'>if</span> <span m='1266390'>we</span>
  <span m='1266570'>specify</span> <span m='1267260'>the</span> <span
  m='1267380'>system</span> <span m='1267950'>in</span> <span
  m='1268100'>terms,</span> <span m='1268850'>rather</span> <span
  m='1269250'>than</span> <span m='1269380'>of</span> <span
  m='1269510'>the</span> <span m='1269600'>unit</span> <span
  m='1269870'>sample</span> <span m='1270260'>response,</span> <span
  m='1271310'>of</span> <span m='1271880'>the</span> <span
  m='1272180'>discrete</span> <span m='1272600'>Fourier</span> <span
  m='1273020'>transform</span> <span m='1273980'>coefficients.</span> <span
  m='1275510'>We</span> <span m='1275600'>recall,</span> <span
  m='1276390'>and</span> <span m='1276710'>I</span> <span
  m='1276830'>hope</span> <span m='1277070'>that</span> <span
  m='1277220'>this</span> <span m='1277400'>is</span> <span
  m='1277550'>second</span> <span m='1277910'>nature</span> <span
  m='1278540'>to</span> <span m='1278690'>you</span> <span m='1278780'>by</span>
  <span m='1278960'>now,</span> <span m='1280910'>in</span> <span
  m='1281000'>general</span> <span m='1281450'>we</span> <span
  m='1281600'>have</span> <span m='1281750'>a</span> <span
  m='1281810'>unit</span> <span m='1282080'>sample</span> <span
  m='1282470'>response.</span> <span m='1284130'>This</span> <span
  m='1284240'>is</span> <span m='1284330'>a</span> <span
  m='1284420'>finite</span> <span m='1284810'>impulse</span> <span
  m='1285200'>response</span> <span m='1285680'>system.</span> <span
  m='1286380'>So</span> <span m='1286490'>this</span> <span
  m='1286670'>is</span> <span m='1286790'>a</span> <span
  m='1286850'>finite</span> <span m='1287270'>length</span> <span
  m='1287480'>sequence.</span> </p><p><span m='1288650'>So</span> <span
  m='1289310'>we</span> <span m='1289520'>can</span> <span
  m='1289700'>describe</span> <span m='1290240'>it</span> <span
  m='1290450'>in</span> <span m='1290600'>terms</span> <span
  m='1291170'>of</span> <span m='1291680'>it's</span> <span
  m='1291890'>discrete</span> <span m='1292310'>Fourier</span> <span
  m='1292730'>transform.</span> <span m='1294020'>And</span> <span
  m='1294140'>the</span> <span m='1294230'>discrete</span> <span
  m='1294590'>Fourier</span> <span m='1294950'>transform</span> <span
  m='1295520'>coefficients</span> <span m='1296420'>are</span> <span
  m='1296570'>referred</span> <span m='1296930'>to</span> <span
  m='1297200'>as</span> <span m='1297320'>h</span> <span m='1297560'>of</span>
  <span m='1297650'>k.</span> <span m='1299390'>Or</span> <span
  m='1299750'>we</span> <span m='1299930'>can</span> <span
  m='1300380'>describe</span> <span m='1300920'>it</span> <span
  m='1301520'>as</span> <span m='1301700'>we</span> <span m='1301850'>can</span>
  <span m='1302000'>describe</span> <span m='1302780'>almost</span> <span
  m='1303200'>all</span> <span m='1303350'>sequences</span> <span
  m='1304580'>in</span> <span m='1304670'>terms</span> <span
  m='1305120'>of</span> <span m='1305235'>its</span> <span m='1305350'>z</span>
  <span m='1305600'>transform,</span> <span m='1306560'>or</span> <span
  m='1306950'>a</span> <span m='1307100'>system</span> <span
  m='1307640'>in</span> <span m='1307790'>terms</span> <span
  m='1308090'>of</span> <span m='1308180'>its</span> <span
  m='1308300'>system</span> <span m='1308660'>function.</span> </p><p><span
  m='1310890'>The</span> <span m='1310980'>z</span> <span
  m='1311160'>transform</span> <span m='1311940'>is</span> <span
  m='1312060'>the</span> <span m='1312180'>sum</span> <span
  m='1312780'>of</span> <span m='1313140'>h</span> <span m='1313490'>of</span>
  <span m='1313615'>n</span> <span m='1313740'>times</span> <span
  m='1314030'>e</span> <span m='1314200'>to</span> <span m='1314280'>the</span>
  <span m='1314370'>minus,</span> <span m='1314770'>n</span> <span
  m='1314940'>as</span> <span m='1315060'>it</span> <span
  m='1315150'>always</span> <span m='1315570'>is.</span> <span
  m='1316590'>And</span> <span m='1317880'>the</span> <span
  m='1319950'>unit</span> <span m='1320280'>sample</span> <span
  m='1320760'>response</span> <span m='1322140'>can</span> <span
  m='1322320'>be</span> <span m='1322530'>expressed</span> <span
  m='1323400'>in</span> <span m='1323520'>terms</span> <span
  m='1324270'>of</span> <span m='1324630'>the</span> <span
  m='1324840'>discrete</span> <span m='1325320'>Fourier</span> <span
  m='1325740'>transform</span> <span m='1326430'>coefficients</span> <span
  m='1328320'>in</span> <span m='1328470'>terms</span> <span
  m='1328950'>of</span> <span m='1329040'>the</span> <span
  m='1329160'>sum</span> <span m='1329640'>of</span> <span m='1329730'>H</span>
  <span m='1330000'>of</span> <span m='1330120'>k</span> <span
  m='1330570'>W</span> <span m='1330960'>sub</span> <span m='1331260'>N</span>
  <span m='1331560'>to</span> <span m='1331680'>the</span> <span
  m='1331800'>minus</span> <span m='1332160'>n</span> <span
  m='1332370'>k.</span> <span m='1333510'>We</span> <span
  m='1333630'>have</span> <span m='1333810'>the</span> <span
  m='1333900'>1/N</span> <span m='1334920'>out</span> <span
  m='1335100'>in</span> <span m='1335190'>front.</span> <span
  m='1336640'>And</span> <span m='1338130'>again,</span> <span
  m='1339030'>this</span> <span m='1339360'>term</span> <span
  m='1339780'>R</span> <span m='1340020'>sub</span> <span
  m='1340230'>capital</span> <span m='1340710'>N</span> <span
  m='1340920'>then</span> <span m='1341400'>to</span> <span
  m='1341550'>just</span> <span m='1341760'>simply</span> <span
  m='1342090'>truncate</span> <span m='1342780'>h</span> <span
  m='1343110'>of</span> <span m='1343470'>n</span> <span
  m='1343830'>after</span> <span m='1344340'>capital</span> <span
  m='1344880'>N</span> <span m='1345210'>points.</span> <span
  m='1346170'>That</span> <span m='1346320'>is</span> <span
  m='1346470'>to</span> <span m='1346590'>extract</span> <span
  m='1346980'>one</span> <span m='1347160'>period</span> <span
  m='1347610'>from</span> <span m='1348300'>the</span> <span
  m='1348390'>periodic</span> <span m='1349440'>function</span> <span
  m='1350250'>that</span> <span m='1350400'>this</span> <span
  m='1350550'>sum</span> <span m='1350850'>generates.</span> </p><p><span
  m='1352470'>Now,</span> <span m='1353100'>we</span> <span
  m='1353280'>can</span> <span m='1353460'>substitute</span> <span
  m='1354885'>h</span> <span m='1355290'>of</span> <span m='1355740'>n</span>
  <span m='1357200'>expressed</span> <span m='1357770'>in</span> <span
  m='1357860'>terms</span> <span m='1358550'>of</span> <span
  m='1359020'>its</span> <span m='1359210'>discrete</span> <span
  m='1359660'>Fourier</span> <span m='1360080'>transform</span> <span
  m='1361580'>into</span> <span m='1361910'>this</span> <span
  m='1362150'>expression.</span> <span m='1364850'>The</span> <span
  m='1364970'>R</span> <span m='1365330'>sub</span> <span m='1365435'>N</span>
  <span m='1365540'>of</span> <span m='1365930'>n</span> <span
  m='1366320'>will</span> <span m='1366470'>disappear</span> <span
  m='1367100'>because</span> <span m='1367640'>we're</span> <span
  m='1367760'>only</span> <span m='1368000'>summing</span> <span
  m='1368480'>from</span> <span m='1368660'>n</span> <span
  m='1368780'>equal</span> <span m='1368990'>0</span> <span
  m='1369320'>to</span> <span m='1369410'>capital</span> <span
  m='1369860'>N</span> <span m='1370010'>minus</span> <span
  m='1370430'>1.</span> <span m='1371730'>And</span> <span m='1372110'>if</span>
  <span m='1372380'>we</span> <span m='1372500'>substitute</span> <span
  m='1373160'>this</span> <span m='1373970'>in</span> <span
  m='1374150'>here</span> <span m='1376040'>and</span> <span
  m='1376490'>interchange</span> <span m='1377270'>the</span> <span
  m='1377420'>order</span> <span m='1377720'>in</span> <span
  m='1377840'>which</span> <span m='1378050'>we</span> <span
  m='1378170'>evaluate</span> <span m='1378800'>the</span> <span
  m='1378920'>sums,</span> <span m='1380570'>then</span> <span
  m='1381260'>the</span> <span m='1381380'>resulting</span> <span
  m='1381890'>expression</span> <span m='1382520'>for</span> <span
  m='1382640'>the</span> <span m='1382730'>z</span> <span
  m='1382940'>transform</span> <span m='1383960'>for</span> <span
  m='1384110'>the</span> <span m='1384200'>system</span> <span
  m='1384590'>function</span> <span m='1385760'>is</span> <span
  m='1386570'>the</span> <span m='1386690'>sum</span> <span
  m='1387020'>from</span> <span m='1387200'>K</span> <span
  m='1387395'>equal</span> <span m='1387590'>0</span> <span
  m='1387980'>to</span> <span m='1388100'>N</span> <span
  m='1388280'>minus</span> <span m='1388700'>1</span> <span
  m='1389390'>of</span> <span m='1389690'>the</span> <span
  m='1390080'>DFT</span> <span m='1390710'>values.</span> <span
  m='1392510'>And</span> <span m='1393470'>this</span> <span
  m='1393740'>term</span> <span m='1394160'>and</span> <span
  m='1394250'>this</span> <span m='1394490'>term</span> <span
  m='1395990'>are</span> <span m='1396380'>involved</span> <span
  m='1396950'>in</span> <span m='1397040'>the</span> <span
  m='1397100'>sum</span> <span m='1397430'>on</span> <span m='1397610'>n.</span>
  <span m='1398750'>And</span> <span m='1399350'>they</span> <span
  m='1399500'>result</span> <span m='1399950'>in</span> <span
  m='1400040'>the</span> <span m='1400130'>sum</span> <span
  m='1400460'>from</span> <span m='1400610'>0</span> <span m='1400910'>to</span>
  <span m='1401000'>capital</span> <span m='1401480'>N</span> <span
  m='1401630'>minus</span> <span m='1402020'>1</span> <span
  m='1402380'>of</span> <span m='1402740'>z</span> <span m='1402950'>to</span>
  <span m='1403100'>the</span> <span m='1403190'>minus</span> <span
  m='1403610'>1,</span> <span m='1404120'>W</span> <span
  m='1404750'>capital</span> <span m='1405230'>N</span> <span
  m='1405590'>to</span> <span m='1405950'>the</span> <span
  m='1406040'>minus</span> <span m='1406400'>k.</span> <span
  m='1407210'>That</span> <span m='1407450'>raised</span> <span
  m='1407780'>to</span> <span m='1407900'>the</span> <span
  m='1408050'>n-th</span> <span m='1408230'>power.</span> </p><p><span
  m='1409910'>Well,</span> <span m='1410630'>this</span> <span
  m='1410810'>is</span> <span m='1410930'>the</span> <span
  m='1411050'>kind</span> <span m='1411320'>of</span> <span
  m='1411410'>summation</span> <span m='1412370'>that</span> <span
  m='1412730'>we've</span> <span m='1412910'>been</span> <span
  m='1413060'>carrying</span> <span m='1413570'>out</span> <span
  m='1413810'>again</span> <span m='1414110'>and</span> <span
  m='1414200'>again,</span> <span m='1414630'>particularly</span> <span
  m='1415160'>in</span> <span m='1415250'>talking</span> <span
  m='1415700'>about</span> <span m='1416360'>finite</span> <span
  m='1416810'>length</span> <span m='1417020'>sequences.</span> <span
  m='1418400'>And</span> <span m='1419180'>hopefully,</span> <span
  m='1420230'>this</span> <span m='1420440'>is</span> <span
  m='1420920'>another</span> <span m='1421970'>kind</span> <span
  m='1422180'>of</span> <span m='1422270'>summation</span> <span
  m='1422870'>that</span> <span m='1423020'>by</span> <span
  m='1423170'>now</span> <span m='1423380'>you</span> <span
  m='1423530'>carry</span> <span m='1423890'>around</span> <span
  m='1424220'>in</span> <span m='1424280'>your</span> <span
  m='1424400'>hip</span> <span m='1424550'>pocket.</span> <span
  m='1426050'>It's</span> <span m='1426230'>the</span> <span
  m='1426320'>sum</span> <span m='1427070'>from</span> <span
  m='1427280'>0</span> <span m='1427760'>to</span> <span
  m='1427940'>capital</span> <span m='1428360'>N</span> <span
  m='1428510'>minus</span> <span m='1428870'>1</span> <span
  m='1429035'>of</span> <span m='1429200'>something</span> <span
  m='1429560'>of</span> <span m='1429650'>the</span> <span
  m='1429770'>form</span> <span m='1430100'>alpha</span> <span
  m='1430490'>to</span> <span m='1430640'>the</span> <span m='1430820'>n,</span>
  <span m='1431150'>where</span> <span m='1431390'>the</span> <span
  m='1431510'>alpha</span> <span m='1431810'>happens</span> <span
  m='1432230'>to</span> <span m='1432350'>be</span> <span
  m='1432470'>that.</span> <span m='1433730'>And</span> <span
  m='1433850'>that</span> <span m='1434030'>sums</span> <span
  m='1434450'>up</span> <span m='1434720'>to</span> <span m='1435500'>1</span>
  <span m='1435830'>minus</span> <span m='1436330'>z</span> <span
  m='1436430'>to</span> <span m='1436460'>the</span> <span
  m='1436550'>minus</span> <span m='1437480'>capital</span> <span
  m='1438000'>N</span> <span m='1439340'>times--</span> <span
  m='1441996'>let's</span> <span m='1442450'>see,</span> <span
  m='1442620'>1</span> <span m='1442840'>minus</span> <span m='1443280'>z</span>
  <span m='1443550'>to</span> <span m='1443710'>the</span> <span
  m='1444400'>minus</span> <span m='1444820'>capital</span> <span
  m='1445360'>N</span> <span m='1446320'>and</span> <span
  m='1446470'>actually</span> <span m='1447970'>W</span> <span
  m='1448600'>sub</span> <span m='1448720'>capital</span> <span
  m='1449260'>N</span> <span m='1450070'>to</span> <span m='1450400'>the</span>
  <span m='1450490'>minus</span> <span m='1451330'>k</span> <span
  m='1452110'>capital</span> <span m='1452680'>N.</span> </p><p><span
  m='1453490'>That</span> <span m='1453610'>is</span> <span
  m='1453790'>it</span> <span m='1453880'>sums</span> <span
  m='1454300'>up</span> <span m='1455050'>to</span> <span
  m='1455260'>this</span> <span m='1455500'>alpha</span> <span
  m='1456370'>raised</span> <span m='1456720'>to</span> <span
  m='1456850'>the</span> <span m='1456940'>capital</span> <span
  m='1457195'>N-th</span> <span m='1457690'>power</span> <span
  m='1459580'>divided</span> <span m='1460120'>by</span> <span
  m='1460630'>1</span> <span m='1460900'>minus</span> <span m='1461290'>W</span>
  <span m='1461710'>sub</span> <span m='1462130'>N</span> <span
  m='1462190'>to</span> <span m='1462250'>the</span> <span
  m='1462340'>minus</span> <span m='1462760'>k</span> <span
  m='1463240'>times</span> <span m='1463540'>z</span> <span
  m='1463760'>to</span> <span m='1463910'>the</span> <span
  m='1463990'>minus</span> <span m='1464390'>1.</span> <span
  m='1465980'>Well,</span> <span m='1466600'>what</span> <span
  m='1466760'>does</span> <span m='1467010'>W</span> <span
  m='1467490'>sub</span> <span m='1468640'>capital</span> <span
  m='1469180'>N</span> <span m='1469640'>to</span> <span m='1469800'>any</span>
  <span m='1469960'>integer</span> <span m='1470440'>multiple</span> <span
  m='1471340'>of</span> <span m='1471520'>capital</span> <span
  m='1472030'>N?</span> <span m='1472870'>That's</span> <span
  m='1473110'>just</span> <span m='1473320'>simply</span> <span
  m='1473680'>equal</span> <span m='1473950'>to</span> <span
  m='1474070'>unity.</span> <span m='1475180'>So</span> <span
  m='1475810'>this</span> <span m='1476020'>term</span> <span
  m='1476350'>disappears.</span> <span m='1477320'>And</span> <span
  m='1477340'>we</span> <span m='1477490'>end</span> <span m='1477670'>up</span>
  <span m='1477820'>simply</span> <span m='1478210'>with</span> <span
  m='1478360'>1</span> <span m='1478570'>minus</span> <span m='1478890'>z</span>
  <span m='1479030'>to</span> <span m='1479170'>the</span> <span
  m='1479290'>minus</span> <span m='1479710'>n</span> <span
  m='1480400'>divided</span> <span m='1480850'>by</span> <span
  m='1481060'>this.</span> </p><p><span m='1482770'>All</span> <span
  m='1482860'>right,</span> <span m='1483130'>so</span> <span
  m='1484540'>combining</span> <span m='1485080'>this</span> <span
  m='1485260'>together,</span> <span m='1486970'>we</span> <span
  m='1487120'>can</span> <span m='1487300'>then</span> <span
  m='1487450'>express</span> <span m='1487990'>h</span> <span
  m='1488260'>of</span> <span m='1488350'>z</span> <span m='1489790'>as</span>
  <span m='1490850'>1</span> <span m='1491220'>minus</span> <span
  m='1491800'>z</span> <span m='1491900'>to</span> <span m='1492000'>the</span>
  <span m='1492100'>minus</span> <span m='1492250'>capital</span> <span
  m='1492790'>N,</span> <span m='1494710'>we</span> <span
  m='1494830'>have</span> <span m='1494980'>this</span> <span
  m='1495130'>1/N,</span> <span m='1495850'>which</span> <span
  m='1496060'>we</span> <span m='1496180'>have</span> <span
  m='1496390'>to</span> <span m='1496480'>account</span> <span
  m='1496810'>for</span> <span m='1497110'>somehow,</span> <span
  m='1498490'>and</span> <span m='1498610'>then</span> <span
  m='1498820'>finally</span> <span m='1499300'>a</span> <span
  m='1499390'>sum</span> <span m='1499750'>from</span> <span
  m='1499930'>0</span> <span m='1500320'>to</span> <span m='1500440'>N</span>
  <span m='1500620'>minus</span> <span m='1500980'>1</span> <span
  m='1501430'>of</span> <span m='1501550'>H</span> <span m='1501670'>of</span>
  <span m='1501790'>k,</span> <span m='1502930'>divided</span> <span
  m='1503410'>by</span> <span m='1504520'>this</span> <span
  m='1504760'>factor.</span> <span m='1507740'>And</span> <span
  m='1508300'>so</span> <span m='1508540'>this</span> <span
  m='1508870'>is</span> <span m='1509260'>an</span> <span
  m='1509380'>expression</span> <span m='1510520'>for</span> <span
  m='1510970'>the</span> <span m='1511090'>z</span> <span
  m='1511330'>transform</span> <span m='1512080'>of</span> <span
  m='1512170'>the</span> <span m='1512290'>system,</span> <span
  m='1513400'>or</span> <span m='1513550'>the</span> <span
  m='1513640'>transfer</span> <span m='1514090'>function</span> <span
  m='1514480'>of</span> <span m='1514570'>the</span> <span
  m='1514660'>system,</span> <span m='1515890'>where</span> <span
  m='1516010'>the</span> <span m='1516130'>coefficients</span> <span
  m='1517030'>in</span> <span m='1517120'>that</span> <span
  m='1517300'>expression</span> <span m='1518530'>are</span> <span
  m='1519030'>the</span> <span m='1519220'>discrete</span> <span
  m='1519640'>Fourier</span> <span m='1520050'>transform</span> <span
  m='1520720'>values</span> <span m='1521230'>H</span> <span
  m='1521470'>of</span> <span m='1521600'>k.</span> </p><p><span
  m='1523210'>The</span> <span m='1523310'>discrete</span> <span
  m='1523670'>Fourier</span> <span m='1524030'>transform</span> <span
  m='1524600'>values,</span> <span m='1525140'>as</span> <span
  m='1525500'>we've</span> <span m='1525680'>stressed</span> <span
  m='1526100'>several</span> <span m='1526490'>times,</span> <span
  m='1527490'>in</span> <span m='1527510'>fact</span> <span
  m='1528060'>are</span> <span m='1528140'>samples</span> <span
  m='1530230'>on</span> <span m='1530350'>the</span> <span
  m='1530440'>unit</span> <span m='1530740'>circle</span> <span
  m='1532210'>of</span> <span m='1532525'>the</span> <span m='1532840'>z</span>
  <span m='1533170'>transform.</span> <span m='1534640'>So</span> <span
  m='1535300'>these</span> <span m='1536290'>coefficients,</span> <span
  m='1537100'>the</span> <span m='1537220'>H</span> <span m='1537460'>of</span>
  <span m='1537550'>k's</span> <span m='1538390'>are</span> <span
  m='1539110'>in</span> <span m='1539260'>effect</span> <span
  m='1540370'>samples</span> <span m='1541270'>of</span> <span
  m='1541420'>the</span> <span m='1541540'>frequency</span> <span
  m='1542050'>response</span> <span m='1542530'>of</span> <span
  m='1542620'>the</span> <span m='1542710'>system.</span> <span
  m='1543530'>In</span> <span m='1543630'>other</span> <span
  m='1543730'>words,</span> <span m='1544550'>they</span> <span
  m='1544720'>are</span> <span m='1544960'>frequency</span> <span
  m='1545560'>samples.</span> <span m='1546610'>And</span> <span
  m='1546700'>consequently,</span> <span m='1547480'>the</span> <span
  m='1547600'>structure</span> <span m='1548440'>that</span> <span
  m='1548590'>this</span> <span m='1548800'>implies</span> <span
  m='1549910'>is</span> <span m='1550330'>usually</span> <span
  m='1550750'>referred</span> <span m='1551110'>to</span> <span
  m='1551470'>as</span> <span m='1551770'>a</span> <span
  m='1551830'>frequency</span> <span m='1552340'>sampling</span> <span
  m='1552820'>structure.</span> </p><p><span m='1555330'>Well,</span> <span
  m='1555870'>let's</span> <span m='1556140'>look</span> <span
  m='1556380'>at</span> <span m='1556800'>what</span> <span
  m='1557100'>the</span> <span m='1557280'>specific</span> <span
  m='1557850'>structure</span> <span m='1558420'>is.</span> <span
  m='1559950'>We</span> <span m='1560100'>can</span> <span
  m='1560280'>view</span> <span m='1560520'>this</span> <span
  m='1560910'>as</span> <span m='1561090'>a</span> <span
  m='1561150'>cascade</span> <span m='1562140'>of</span> <span
  m='1562890'>the</span> <span m='1562980'>system</span> <span
  m='1563430'>that</span> <span m='1563550'>implements</span> <span
  m='1564060'>this</span> <span m='1564330'>term</span> <span
  m='1566720'>in</span> <span m='1566850'>cascade</span> <span
  m='1567480'>with</span> <span m='1567600'>the</span> <span
  m='1567720'>system</span> <span m='1568080'>that</span> <span
  m='1568200'>implements</span> <span m='1569060'>this</span> <span
  m='1569280'>summation.</span> <span m='1571620'>This</span> <span
  m='1571890'>term</span> <span m='1572280'>is</span> <span
  m='1572340'>simply</span> <span m='1572790'>implemented</span> <span
  m='1573720'>by</span> <span m='1574880'>a</span> <span m='1574980'>gain</span>
  <span m='1575730'>of</span> <span m='1576660'>unity</span> <span
  m='1577680'>in</span> <span m='1577770'>the</span> <span
  m='1577860'>forward</span> <span m='1578280'>direction,</span> <span
  m='1580660'>and</span> <span m='1580840'>then</span> <span
  m='1581290'>a</span> <span m='1581635'>gain</span> <span m='1581980'>of</span>
  <span m='1582730'>minus</span> <span m='1583200'>z</span> <span
  m='1583320'>to</span> <span m='1583480'>the</span> <span
  m='1583570'>minus</span> <span m='1584050'>capital</span> <span
  m='1584590'>N--</span> <span m='1585130'>I</span> <span
  m='1585280'>happen</span> <span m='1585570'>to</span> <span
  m='1585670'>have</span> <span m='1585880'>the</span> <span
  m='1586030'>arrow</span> <span m='1586360'>here</span> <span
  m='1586840'>in</span> <span m='1586960'>the</span> <span
  m='1587020'>reverse</span> <span m='1587380'>direction,</span> <span
  m='1587980'>which</span> <span m='1588160'>is</span> <span
  m='1588280'>wrong.</span> <span m='1591140'>This</span> <span
  m='1591210'>is</span> <span m='1591280'>as</span> <span m='1591410'>an</span>
  <span m='1591530'>arrow,</span> <span m='1592160'>again,</span> <span
  m='1592460'>in</span> <span m='1592550'>the</span> <span
  m='1592640'>forward</span> <span m='1593030'>direction.</span> <span
  m='1594530'>That</span> <span m='1594710'>just</span> <span
  m='1594860'>simply</span> <span m='1595250'>implements</span> <span
  m='1595760'>the</span> <span m='1595850'>system,</span> <span
  m='1596810'>1</span> <span m='1597050'>minus</span> <span m='1597440'>z</span>
  <span m='1597590'>to</span> <span m='1597740'>the</span> <span
  m='1597830'>minus</span> <span m='1598670'>capital</span> <span
  m='1599180'>N.</span> </p><p><span m='1600876'>And</span> <span
  m='1601580'>that</span> <span m='1602270'>I</span> <span
  m='1602360'>guess</span> <span m='1603000'>makes</span> <span
  m='1603290'>enough</span> <span m='1603560'>of</span> <span
  m='1603680'>a</span> <span m='1603700'>mess</span> <span
  m='1603945'>out</span> <span m='1604190'>of</span> <span
  m='1604310'>it,</span> <span m='1604430'>so</span> <span
  m='1604580'>that</span> <span m='1605870'>hopefully</span> <span
  m='1606380'>you</span> <span m='1606530'>can</span> <span
  m='1606920'>at</span> <span m='1607040'>least</span> <span
  m='1607340'>see</span> <span m='1607760'>what</span> <span
  m='1607940'>direction</span> <span m='1608390'>that</span> <span
  m='1608540'>arrow</span> <span m='1608840'>goes</span> <span
  m='1609170'>in.</span> </p><p><span m='1609770'>This</span> <span
  m='1609980'>then</span> <span m='1610190'>implements</span> <span
  m='1611000'>that</span> <span m='1611240'>piece.</span> <span
  m='1613070'>To</span> <span m='1613160'>implement</span> <span
  m='1613870'>this</span> <span m='1614110'>sum,</span> <span
  m='1615140'>well,</span> <span m='1615610'>this</span> <span
  m='1615790'>sum</span> <span m='1616220'>implies</span> <span
  m='1616820'>a</span> <span m='1616880'>parallel</span> <span
  m='1617390'>combination</span> <span m='1618470'>of</span> <span
  m='1619220'>systems,</span> <span m='1620550'>each</span> <span
  m='1620690'>system</span> <span m='1621380'>implementing</span> <span
  m='1622250'>one</span> <span m='1622460'>of</span> <span
  m='1622520'>these</span> <span m='1622850'>pieces.</span> <span
  m='1623960'>So</span> <span m='1624140'>if</span> <span m='1624260'>we</span>
  <span m='1624350'>look</span> <span m='1624560'>at</span> <span
  m='1624650'>this,</span> <span m='1624860'>say,</span> <span
  m='1625100'>for</span> <span m='1625280'>k</span> <span
  m='1625710'>equal</span> <span m='1625850'>0,</span> <span
  m='1627320'>we</span> <span m='1627470'>have</span> <span m='1627590'>a</span>
  <span m='1627650'>coefficient</span> <span m='1628520'>of</span> <span
  m='1628610'>0</span> <span m='1629240'>as</span> <span m='1629390'>I've</span>
  <span m='1629570'>indicated</span> <span m='1630140'>here</span> <span
  m='1631320'>and</span> <span m='1631340'>a</span> <span
  m='1631705'>pole.</span> <span m='1632790'>And</span> <span
  m='1632900'>where</span> <span m='1633065'>is</span> <span
  m='1633230'>the</span> <span m='1633350'>pole?</span> <span
  m='1633680'>Well,</span> <span m='1633980'>the</span> <span
  m='1634070'>pole</span> <span m='1634400'>for</span> <span
  m='1634550'>k</span> <span m='1634850'>equal</span> <span m='1634970'>0</span>
  <span m='1635540'>is</span> <span m='1635900'>at</span> <span
  m='1636140'>W</span> <span m='1636277'>sub</span> <span m='1636690'>N</span>
  <span m='1636930'>to</span> <span m='1637050'>the</span> <span
  m='1637130'>minus</span> <span m='1637430'>0.</span> <span
  m='1639290'>For</span> <span m='1639440'>k</span> <span
  m='1639680'>equal</span> <span m='1639920'>to</span> <span
  m='1640040'>1,</span> <span m='1640290'>it's</span> <span
  m='1640520'>at</span> <span m='1640700'>W</span> <span m='1640880'>sub</span>
  <span m='1641060'>N</span> <span m='1641240'>to</span> <span
  m='1641340'>the</span> <span m='1641450'>minus</span> <span
  m='1641870'>1</span> <span m='1642440'>and</span> <span m='1642860'>on</span>
  <span m='1643130'>through.</span> </p><p><span m='1644090'>So</span> <span
  m='1644510'>the</span> <span m='1644630'>system</span> <span
  m='1645110'>that</span> <span m='1645230'>implements</span> <span
  m='1645770'>this</span> <span m='1646010'>sum</span> <span
  m='1646910'>is</span> <span m='1647210'>then</span> <span m='1648110'>a</span>
  <span m='1648200'>parallel</span> <span m='1648740'>combination</span> <span
  m='1650150'>of</span> <span m='1650270'>first</span> <span
  m='1650690'>order</span> <span m='1650960'>poles,</span> <span
  m='1652670'>where</span> <span m='1653600'>the</span> <span
  m='1653840'>coefficient</span> <span m='1654470'>in</span> <span
  m='1654530'>the</span> <span m='1654620'>feedback</span> <span
  m='1655190'>path</span> <span m='1655730'>is</span> <span m='1655910'>W</span>
  <span m='1656285'>sub</span> <span m='1656472'>N</span> <span
  m='1656660'>to</span> <span m='1656780'>the</span> <span
  m='1656870'>minus</span> <span m='1657310'>k.</span> <span
  m='1658800'>And</span> <span m='1659360'>the</span> <span
  m='1659530'>gain</span> <span m='1660980'>in</span> <span
  m='1661220'>the</span> <span m='1661310'>forward</span> <span
  m='1661760'>path,</span> <span m='1662390'>which</span> <span
  m='1662660'>can</span> <span m='1662810'>be</span> <span
  m='1662930'>placed</span> <span m='1663290'>either</span> <span
  m='1663530'>before</span> <span m='1664070'>or</span> <span
  m='1664220'>after</span> <span m='1664580'>the</span> <span
  m='1664670'>pole,</span> <span m='1665510'>are</span> <span
  m='1665720'>the</span> <span m='1665810'>frequency</span> <span
  m='1666350'>samples</span> <span m='1667110'>H</span> <span
  m='1667310'>of</span> <span m='1667410'>0,</span> <span m='1667850'>H</span>
  <span m='1668090'>of</span> <span m='1668210'>1,</span> <span
  m='1668990'>down</span> <span m='1669260'>through</span> <span
  m='1669710'>H</span> <span m='1669980'>of</span> <span m='1670085'>n</span>
  <span m='1670190'>minus</span> <span m='1670630'>1.</span> </p><p><span
  m='1672470'>And</span> <span m='1672680'>then,</span> <span
  m='1672930'>of</span> <span m='1673030'>course,</span> <span
  m='1673350'>we</span> <span m='1673370'>have</span> <span
  m='1673550'>the</span> <span m='1673640'>gain</span> <span
  m='1673910'>of</span> <span m='1674000'>1/N,</span> <span
  m='1675290'>which</span> <span m='1675490'>has</span> <span
  m='1675710'>to</span> <span m='1675830'>go</span> <span
  m='1676010'>someplace.</span> <span m='1677150'>And</span> <span
  m='1677990'>for</span> <span m='1678140'>now,</span> <span
  m='1678380'>let's</span> <span m='1678620'>just</span> <span
  m='1679040'>leave</span> <span m='1679280'>it</span> <span
  m='1679370'>at</span> <span m='1679460'>the</span> <span
  m='1679610'>end.</span> </p><p><span m='1682090'>I</span> <span
  m='1682210'>stress</span> <span m='1682600'>also</span> <span
  m='1683440'>that</span> <span m='1684130'>these,</span> <span
  m='1684610'>of</span> <span m='1684730'>course,</span> <span
  m='1685090'>are</span> <span m='1685180'>complex</span> <span
  m='1688480'>poles,</span> <span m='1688930'>because</span> <span
  m='1690010'>W</span> <span m='1690370'>sub</span> <span m='1690527'>N</span>
  <span m='1691000'>to</span> <span m='1691150'>an</span> <span
  m='1691240'>integer</span> <span m='1691570'>power</span> <span
  m='1691870'>is</span> <span m='1691990'>in</span> <span
  m='1692080'>general</span> <span m='1692470'>complex.</span> <span
  m='1693670'>We</span> <span m='1693820'>can,</span> <span
  m='1694160'>of</span> <span m='1694260'>course,</span> <span
  m='1694480'>redraw</span> <span m='1694960'>this</span> <span
  m='1695140'>structure</span> <span m='1695590'>by</span> <span
  m='1695770'>combining</span> <span m='1696820'>complex</span> <span
  m='1697330'>conjugate</span> <span m='1697870'>poles</span> <span
  m='1698230'>together.</span> <span m='1699550'>And</span> <span
  m='1700450'>the</span> <span m='1700990'>structure</span> <span
  m='1701440'>that</span> <span m='1701590'>results</span> <span
  m='1702250'>is</span> <span m='1703060'>indicated</span> <span
  m='1703660'>in</span> <span m='1703780'>the</span> <span
  m='1703870'>text.</span> <span m='1704570'>I</span> <span
  m='1704590'>won't</span> <span m='1704890'>bother</span> <span
  m='1705280'>to</span> <span m='1705400'>do</span> <span
  m='1705550'>that</span> <span m='1705790'>here.</span> <span
  m='1706720'>But</span> <span m='1707200'>there</span> <span
  m='1707500'>are</span> <span m='1707660'>a</span> <span
  m='1707680'>couple</span> <span m='1707980'>of</span> <span
  m='1708070'>points</span> <span m='1708460'>about</span> <span
  m='1708790'>this</span> <span m='1708940'>structure</span> <span
  m='1709720'>that</span> <span m='1709960'>I'd</span> <span
  m='1710110'>like</span> <span m='1710320'>to</span> <span
  m='1710440'>draw</span> <span m='1710680'>your</span> <span
  m='1710860'>attention</span> <span m='1711340'>to.</span> </p><p><span
  m='1713960'>First</span> <span m='1714320'>of</span> <span
  m='1714470'>all,</span> <span m='1715040'>we</span> <span
  m='1715160'>started</span> <span m='1715790'>with</span> <span
  m='1715970'>a</span> <span m='1716030'>finite</span> <span
  m='1716420'>impulse</span> <span m='1716810'>response</span> <span
  m='1717260'>system.</span> <span m='1720330'>Obviously,</span> <span
  m='1721350'>we've</span> <span m='1721560'>ended</span> <span
  m='1721800'>up</span> <span m='1721920'>with</span> <span m='1722040'>a</span>
  <span m='1722100'>finite</span> <span m='1722490'>impulse</span> <span
  m='1722850'>response</span> <span m='1723360'>system.</span> <span
  m='1724140'>But</span> <span m='1725280'>the</span> <span
  m='1725400'>system</span> <span m='1726280'>appears</span> <span
  m='1726690'>to</span> <span m='1726810'>have</span> <span
  m='1726990'>some</span> <span m='1727150'>poles</span> <span
  m='1727620'>in</span> <span m='1727740'>it.</span> <span
  m='1729150'>That</span> <span m='1729300'>is</span> <span
  m='1729510'>its</span> <span m='1729630'>a</span> <span
  m='1729690'>recursive</span> <span m='1730230'>structure,</span> <span
  m='1731460'>and</span> <span m='1731910'>it</span> <span
  m='1732060'>has</span> <span m='1732600'>in</span> <span
  m='1732720'>fact</span> <span m='1733410'>capital</span> <span
  m='1733890'>N</span> <span m='1734070'>poles</span> <span
  m='1735150'>involved</span> <span m='1735690'>in</span> <span
  m='1735780'>the</span> <span m='1735900'>implementation,</span> <span
  m='1737370'>although</span> <span m='1737940'>presumably</span> <span
  m='1738630'>the</span> <span m='1738750'>overall</span> <span
  m='1739230'>system</span> <span m='1739650'>function</span> <span
  m='1740370'>has</span> <span m='1740580'>only</span> <span
  m='1740850'>zeros.</span> </p><p><span m='1743140'>Well,</span> <span
  m='1743230'>how</span> <span m='1743380'>can</span> <span
  m='1743530'>that</span> <span m='1743740'>be?</span> <span
  m='1746290'>Very</span> <span m='1746590'>simply</span> <span
  m='1747430'>because</span> <span m='1748630'>if</span> <span
  m='1748810'>you</span> <span m='1748930'>look</span> <span
  m='1749170'>at</span> <span m='1749290'>this</span> <span
  m='1749530'>term,</span> <span m='1751100'>this</span> <span
  m='1751240'>term</span> <span m='1751660'>has</span> <span
  m='1752560'>capital</span> <span m='1753100'>N</span> <span
  m='1753280'>zeros</span> <span m='1755160'>equally</span> <span
  m='1755610'>distributed</span> <span m='1756330'>around</span> <span
  m='1756660'>the</span> <span m='1756750'>unit</span> <span
  m='1757020'>circle</span> <span m='1758690'>in</span> <span
  m='1758850'>angle.</span> <span m='1759870'>And</span> <span
  m='1759990'>in</span> <span m='1760140'>fact,</span> <span
  m='1761500'>a</span> <span m='1761960'>zero</span> <span m='1762360'>is</span>
  <span m='1762480'>occurring</span> <span m='1763290'>exactly</span> <span
  m='1763980'>at</span> <span m='1764070'>the</span> <span
  m='1764160'>location</span> <span m='1765060'>where</span> <span
  m='1765360'>each</span> <span m='1765600'>of</span> <span
  m='1765660'>these</span> <span m='1765870'>poles</span> <span
  m='1766230'>occur.</span> <span m='1767310'>So</span> <span
  m='1767520'>that,</span> <span m='1767730'>in</span> <span
  m='1767880'>fact,</span> <span m='1768720'>this</span> <span
  m='1768960'>piece</span> <span m='1769970'>in</span> <span
  m='1770100'>cascade</span> <span m='1771150'>with</span> <span
  m='1771330'>this</span> <span m='1772890'>cancels</span> <span
  m='1773460'>out</span> <span m='1774060'>this</span> <span
  m='1774990'>feedback</span> <span m='1775590'>loop,</span> <span
  m='1776070'>or</span> <span m='1776250'>this</span> <span
  m='1776490'>pole</span> <span m='1777480'>simply</span> <span
  m='1777870'>cancels</span> <span m='1778410'>out</span> <span
  m='1778680'>one</span> <span m='1778890'>of</span> <span
  m='1778980'>the</span> <span m='1779100'>zeros</span> <span
  m='1780210'>from</span> <span m='1780870'>this</span> <span
  m='1781140'>term.</span> <span m='1782130'>This</span> <span
  m='1782370'>one</span> <span m='1782580'>cancels</span> <span
  m='1783090'>out</span> <span m='1783240'>another</span> <span
  m='1783540'>zero</span> <span m='1784470'>and</span> <span
  m='1784710'>on</span> <span m='1784950'>down</span> <span
  m='1785220'>through</span> <span m='1785400'>the</span> <span
  m='1785520'>chain.</span> </p><p><span m='1786630'>So</span> <span
  m='1787070'>in</span> <span m='1787170'>the</span> <span
  m='1787290'>overall</span> <span m='1787710'>system</span> <span
  m='1788130'>function,</span> <span m='1789280'>there</span> <span
  m='1789360'>are</span> <span m='1789570'>no</span> <span
  m='1789780'>poles.</span> <span m='1790680'>There</span> <span
  m='1790770'>are</span> <span m='1790860'>only</span> <span
  m='1791100'>zeros.</span> <span m='1792330'>And</span> <span
  m='1793320'>what</span> <span m='1793470'>happens</span> <span
  m='1794040'>in</span> <span m='1794130'>effect</span> <span
  m='1794700'>is</span> <span m='1794910'>that</span> <span
  m='1795090'>these</span> <span m='1795360'>poles</span> <span
  m='1795930'>are</span> <span m='1796050'>used</span> <span
  m='1796380'>to</span> <span m='1796500'>cancel</span> <span
  m='1796980'>out</span> <span m='1797280'>different</span> <span
  m='1797640'>zeros</span> <span m='1798270'>appearing</span> <span
  m='1798870'>in</span> <span m='1798990'>this</span> <span
  m='1799170'>first</span> <span m='1799470'>path.</span> </p><p><span
  m='1800790'>That</span> <span m='1801210'>suggests</span> <span
  m='1801750'>one</span> <span m='1801930'>of</span> <span
  m='1802020'>the</span> <span m='1802110'>problems,</span> <span
  m='1802650'>in</span> <span m='1802740'>fact,</span> <span
  m='1803250'>with</span> <span m='1803420'>the</span> <span
  m='1803460'>frequency</span> <span m='1803940'>sampling</span> <span
  m='1804420'>structure</span> <span m='1805440'>because</span> <span
  m='1806100'>it</span> <span m='1806220'>requires</span> <span
  m='1808170'>poles,</span> <span m='1809910'>as</span> <span
  m='1810120'>I've</span> <span m='1810300'>drawn</span> <span
  m='1810630'>it</span> <span m='1810690'>here</span> <span
  m='1811050'>actually</span> <span m='1811500'>on</span> <span
  m='1811740'>the</span> <span m='1811800'>unit</span> <span
  m='1812130'>circle--</span> <span m='1813570'>in</span> <span
  m='1814140'>an</span> <span m='1814260'>actual</span> <span
  m='1814620'>implementation</span> <span m='1815400'>obviously</span> <span
  m='1815860'>that</span> <span m='1816000'>would</span> <span
  m='1816120'>be</span> <span m='1816240'>slightly</span> <span
  m='1816660'>of</span> <span m='1816870'>the</span> <span
  m='1816960'>unit</span> <span m='1817260'>circle--</span> <span
  m='1818250'>but</span> <span m='1818550'>it</span> <span
  m='1818730'>involves</span> <span m='1819720'>implementing</span> <span
  m='1820320'>poles</span> <span m='1821400'>to</span> <span
  m='1821520'>cancel</span> <span m='1822030'>out</span> <span
  m='1822360'>the</span> <span m='1822480'>zeros</span> <span
  m='1823020'>appearing</span> <span m='1823740'>in</span> <span
  m='1823980'>this</span> <span m='1824490'>term</span> <span
  m='1824970'>1</span> <span m='1825200'>minus</span> <span m='1825530'>z</span>
  <span m='1825655'>to</span> <span m='1825780'>the</span> <span
  m='1825900'>minus</span> <span m='1826185'>n.</span> </p><p><span
  m='1827400'>And</span> <span m='1828090'>that</span> <span
  m='1828360'>has</span> <span m='1828570'>some</span> <span
  m='1828750'>drawbacks</span> <span m='1830550'>from</span> <span
  m='1831030'>a</span> <span m='1831090'>number</span> <span
  m='1831390'>of</span> <span m='1831480'>points</span> <span
  m='1831840'>of</span> <span m='1831900'>view.</span> <span
  m='1832540'>In</span> <span m='1832560'>fact,</span> <span
  m='1833050'>it</span> <span m='1833070'>has</span> <span
  m='1833250'>some</span> <span m='1833610'>drawbacks--</span> <span
  m='1834720'>we</span> <span m='1834930'>won't</span> <span
  m='1835110'>analyze</span> <span m='1835620'>this,</span> <span
  m='1835890'>but</span> <span m='1836100'>it</span> <span
  m='1836160'>turns</span> <span m='1836460'>out</span> <span
  m='1836640'>to</span> <span m='1836760'>be</span> <span
  m='1837540'>true</span> <span m='1837960'>that</span> <span
  m='1838770'>due</span> <span m='1838980'>to</span> <span
  m='1839130'>finite</span> <span m='1839520'>register</span> <span
  m='1839970'>length</span> <span m='1840240'>effects</span> <span
  m='1840630'>there</span> <span m='1840810'>are</span> <span
  m='1840840'>some</span> <span m='1841050'>drawbacks.</span> </p><p><span
  m='1842670'>But</span> <span m='1843150'>there</span> <span
  m='1843480'>are</span> <span m='1843690'>also</span> <span
  m='1844020'>some</span> <span m='1844230'>advantages</span> <span
  m='1845400'>to</span> <span m='1845760'>this</span> <span
  m='1845970'>kind</span> <span m='1846210'>of</span> <span
  m='1846270'>structure.</span> <span m='1847870'>And</span> <span
  m='1848670'>the</span> <span m='1848790'>advantages</span> <span
  m='1849410'>in</span> <span m='1849540'>some</span> <span
  m='1849990'>situations</span> <span m='1851370'>outweigh</span> <span
  m='1852510'>the</span> <span m='1852630'>disadvantage,</span> <span
  m='1853470'>the</span> <span m='1853710'>main</span> <span
  m='1853950'>disadvantage,</span> <span m='1854580'>of</span> <span
  m='1854670'>canceling</span> <span m='1855210'>out</span> <span
  m='1855780'>zeros</span> <span m='1856200'>with</span> <span
  m='1856320'>poles</span> <span m='1856740'>or</span> <span
  m='1856800'>poles</span> <span m='1857130'>with</span> <span
  m='1857310'>zeroes.</span> </p><p><span m='1858870'>One</span> <span
  m='1858990'>of</span> <span m='1859050'>the</span> <span
  m='1859140'>first</span> <span m='1859500'>advantages</span> <span
  m='1860400'>is</span> <span m='1860580'>that</span> <span
  m='1860790'>the</span> <span m='1860880'>coefficients</span> <span
  m='1861660'>that</span> <span m='1861750'>are</span> <span
  m='1861870'>involved</span> <span m='1863490'>involve</span> <span
  m='1864180'>frequency</span> <span m='1864720'>samples.</span> <span
  m='1866770'>Now,</span> <span m='1867810'>in</span> <span
  m='1868290'>many</span> <span m='1868560'>situations</span> <span
  m='1869760'>what</span> <span m='1869970'>we</span> <span
  m='1870120'>would</span> <span m='1870270'>like</span> <span
  m='1870510'>to</span> <span m='1870660'>implement</span> <span
  m='1872130'>is</span> <span m='1872730'>a</span> <span
  m='1872790'>system</span> <span m='1873630'>in</span> <span
  m='1873810'>which</span> <span m='1874140'>perhaps</span> <span
  m='1874920'>a</span> <span m='1875010'>large</span> <span
  m='1875400'>number</span> <span m='1875670'>of</span> <span
  m='1875760'>the</span> <span m='1875850'>frequency</span> <span
  m='1876360'>samples</span> <span m='1876870'>happen</span> <span
  m='1877170'>to</span> <span m='1877260'>be</span> <span
  m='1877380'>zero.</span> <span m='1879180'>Imagine</span> <span
  m='1879600'>for</span> <span m='1879750'>example,</span> <span
  m='1880540'>implementing</span> <span m='1881010'>a</span> <span
  m='1881220'>very</span> <span m='1881430'>narrow</span> <span
  m='1881820'>band,</span> <span m='1882690'>low</span> <span
  m='1882900'>pass</span> <span m='1883260'>or</span> <span
  m='1883350'>bandpass,</span> <span m='1883950'>filter</span> <span
  m='1885420'>and</span> <span m='1885540'>specifying</span> <span
  m='1886290'>the</span> <span m='1886410'>filter</span> <span
  m='1886830'>in</span> <span m='1886950'>such</span> <span m='1887220'>a</span>
  <span m='1887310'>way</span> <span m='1888270'>that</span> <span
  m='1888420'>the</span> <span m='1888510'>frequency</span> <span
  m='1889050'>samples</span> <span m='1889830'>in-band</span> <span
  m='1890690'>are</span> <span m='1890840'>non-zero</span> <span
  m='1892260'>and</span> <span m='1892350'>the</span> <span
  m='1892440'>frequency</span> <span m='1892890'>samples</span> <span
  m='1893430'>out</span> <span m='1893620'>of</span> <span
  m='1893740'>band</span> <span m='1894360'>are</span> <span
  m='1894600'>equal</span> <span m='1894900'>to</span> <span
  m='1895020'>zero.</span> </p><p><span m='1896340'>In</span> <span
  m='1896460'>that</span> <span m='1896700'>case,</span> <span
  m='1897570'>most</span> <span m='1897990'>of</span> <span
  m='1898080'>the</span> <span m='1898170'>coefficients</span> <span
  m='1899280'>are</span> <span m='1899430'>coefficients</span> <span
  m='1900120'>which</span> <span m='1900330'>are</span> <span
  m='1900390'>zero</span> <span m='1900810'>coefficients.</span> <span
  m='1902280'>And</span> <span m='1902370'>consequently,</span> <span
  m='1903690'>there</span> <span m='1903870'>will</span> <span
  m='1903990'>be</span> <span m='1904200'>only</span> <span m='1904500'>a</span>
  <span m='1904560'>few</span> <span m='1904860'>of</span> <span
  m='1904980'>these</span> <span m='1905190'>paths</span> <span
  m='1905580'>that</span> <span m='1905730'>we</span> <span
  m='1905850'>have</span> <span m='1906060'>to</span> <span
  m='1906150'>implement,</span> <span m='1907290'>so</span> <span
  m='1907530'>that</span> <span m='1908400'>in</span> <span
  m='1908550'>that</span> <span m='1908760'>situation</span> <span
  m='1909540'>where</span> <span m='1909780'>perhaps</span> <span
  m='1910380'>a</span> <span m='1910440'>large</span> <span
  m='1910770'>number</span> <span m='1911070'>of</span> <span
  m='1911130'>frequency</span> <span m='1911670'>samples</span> <span
  m='1912240'>are</span> <span m='1912360'>zero--</span> <span
  m='1914130'>in</span> <span m='1914220'>fact,</span> <span
  m='1914860'>the</span> <span m='1914910'>number</span> <span
  m='1915150'>of</span> <span m='1915210'>multiplications</span> <span
  m='1916380'>involved</span> <span m='1917640'>in</span> <span
  m='1917760'>implementing</span> <span m='1918300'>the</span> <span
  m='1918420'>system,</span> <span m='1919710'>and</span> <span
  m='1919890'>in</span> <span m='1919980'>fact,</span> <span
  m='1920380'>the</span> <span m='1920480'>number</span> <span
  m='1920640'>of</span> <span m='1920730'>delays</span> <span
  m='1921180'>involved</span> <span m='1921840'>in</span> <span
  m='1921960'>implementing</span> <span m='1922500'>the</span> <span
  m='1922590'>system,</span> <span m='1923550'>might</span> <span
  m='1923850'>be</span> <span m='1924120'>significantly</span> <span
  m='1924930'>reduced.</span> </p><p><span m='1927270'>Another</span> <span
  m='1927870'>advantage</span> <span m='1928440'>to</span> <span
  m='1928590'>a</span> <span m='1928650'>frequency</span> <span
  m='1929160'>sampling</span> <span m='1929640'>structure</span> <span
  m='1931290'>is</span> <span m='1932670'>the</span> <span
  m='1932910'>fact</span> <span m='1933480'>that</span> <span
  m='1933840'>it</span> <span m='1934020'>is</span> <span
  m='1934170'>basically</span> <span m='1935250'>a</span> <span
  m='1935340'>parallel</span> <span m='1935910'>form</span> <span
  m='1936270'>structure.</span> <span m='1937590'>And</span> <span
  m='1937740'>that</span> <span m='1937950'>can</span> <span
  m='1938100'>be</span> <span m='1938250'>exploited</span> <span
  m='1939360'>in</span> <span m='1939510'>terms</span> <span
  m='1940320'>of</span> <span m='1940860'>implementation</span> <span
  m='1942330'>of</span> <span m='1943410'>a</span> <span
  m='1943470'>large</span> <span m='1943860'>number</span> <span
  m='1944220'>of</span> <span m='1944310'>filters,</span> <span
  m='1945000'>or</span> <span m='1945480'>in</span> <span
  m='1945660'>terms</span> <span m='1945990'>of</span> <span
  m='1946050'>the</span> <span m='1946140'>implementation</span> <span
  m='1946830'>of</span> <span m='1946980'>a</span> <span
  m='1947040'>filter</span> <span m='1947430'>bank.</span> <span
  m='1948510'>Let</span> <span m='1948630'>me</span> <span
  m='1948930'>state</span> <span m='1949380'>more</span> <span
  m='1949530'>specifically</span> <span m='1950220'>what</span> <span
  m='1950340'>I</span> <span m='1950430'>mean</span> <span m='1950700'>by</span>
  <span m='1950880'>that.</span> </p><p><span m='1953410'>In</span> <span
  m='1953650'>this</span> <span m='1953770'>system</span> <span
  m='1954220'>function,</span> <span m='1956160'>this</span> <span
  m='1956460'>piece</span> <span m='1958050'>and</span> <span
  m='1958320'>this</span> <span m='1958560'>piece,</span> <span
  m='1958980'>except</span> <span m='1959370'>for</span> <span
  m='1959490'>the</span> <span m='1959610'>H</span> <span m='1959790'>of</span>
  <span m='1959970'>k's,</span> <span m='1961170'>are</span> <span
  m='1961350'>tied</span> <span m='1961830'>only</span> <span
  m='1962250'>to</span> <span m='1962400'>the</span> <span
  m='1962520'>fact</span> <span m='1963150'>that</span> <span
  m='1963300'>the</span> <span m='1963420'>unit</span> <span
  m='1963690'>sample</span> <span m='1964080'>response</span> <span
  m='1964590'>of</span> <span m='1964680'>the</span> <span
  m='1964770'>system</span> <span m='1965430'>is</span> <span
  m='1965610'>of</span> <span m='1965700'>length</span> <span
  m='1966160'>capital</span> <span m='1966660'>N.</span> <span
  m='1967840'>So</span> <span m='1968080'>that</span> <span
  m='1968710'>if</span> <span m='1968950'>I</span> <span
  m='1969100'>implement</span> <span m='1970120'>a</span> <span
  m='1970240'>large</span> <span m='1970750'>number</span> <span
  m='1971080'>of</span> <span m='1971170'>systems</span> <span
  m='1972610'>whose</span> <span m='1973540'>impulse</span> <span
  m='1973990'>response</span> <span m='1974480'>is</span> <span
  m='1974590'>of</span> <span m='1974710'>length</span> <span
  m='1974960'>capital</span> <span m='1975490'>N,</span> <span
  m='1976480'>the</span> <span m='1976600'>systems</span> <span
  m='1977650'>will</span> <span m='1977830'>look</span> <span
  m='1978040'>identical</span> <span m='1979060'>from</span> <span
  m='1979300'>the</span> <span m='1979450'>input</span> <span
  m='1980410'>up</span> <span m='1980680'>to</span> <span m='1980800'>the</span>
  <span m='1980920'>point</span> <span m='1981760'>where</span> <span
  m='1982120'>I</span> <span m='1982270'>do</span> <span m='1982450'>the</span>
  <span m='1982570'>multiplication</span> <span m='1983950'>by</span> <span
  m='1984310'>the</span> <span m='1984430'>frequency</span> <span
  m='1984970'>samples.</span> </p><p><span m='1986740'>Consequently,</span>
  <span m='1987670'>if</span> <span m='1987850'>I</span> <span
  m='1987940'>were</span> <span m='1988060'>to</span> <span
  m='1988150'>implement</span> <span m='1988930'>a</span> <span
  m='1988990'>large</span> <span m='1989380'>number</span> <span
  m='1989740'>of</span> <span m='1989800'>filters</span> <span
  m='1990280'>simultaneously.</span> <span m='1992230'>I</span> <span
  m='1992380'>can</span> <span m='1992650'>use</span> <span
  m='1993910'>in</span> <span m='1994060'>common</span> <span
  m='1994720'>for</span> <span m='1994960'>all</span> <span
  m='1995200'>of</span> <span m='1995290'>those</span> <span
  m='1995500'>systems</span> <span m='1996640'>the</span> <span
  m='1996760'>part</span> <span m='1997150'>of</span> <span
  m='1997270'>this</span> <span m='1997480'>structure</span> <span
  m='1998110'>from</span> <span m='1998290'>the</span> <span
  m='1998470'>input</span> <span m='1999550'>to</span> <span
  m='1999910'>the</span> <span m='2000090'>output</span> <span
  m='2000720'>of</span> <span m='2001380'>the</span> <span
  m='2001520'>poles.</span> <span m='2003510'>And</span> <span
  m='2003630'>then</span> <span m='2003810'>simply</span> <span
  m='2004230'>draw</span> <span m='2004650'>off</span> <span
  m='2004980'>those</span> <span m='2005280'>outputs,</span> <span
  m='2006390'>multiply</span> <span m='2007320'>by</span> <span
  m='2007950'>the</span> <span m='2008070'>required</span> <span
  m='2008730'>frequency</span> <span m='2009270'>samples,</span> <span
  m='2010320'>sum</span> <span m='2010650'>the</span> <span
  m='2010800'>outputs,</span> <span m='2011620'>and</span> <span
  m='2012000'>that</span> <span m='2012240'>implements</span> <span
  m='2012780'>the</span> <span m='2012870'>filter.</span> </p><p><span
  m='2013860'>Consequently,</span> <span m='2014640'>I'm</span> <span
  m='2014760'>able</span> <span m='2015000'>to</span> <span
  m='2015150'>share</span> <span m='2016380'>among</span> <span
  m='2016890'>all</span> <span m='2017100'>of</span> <span
  m='2017190'>the</span> <span m='2017280'>filters</span> <span
  m='2017850'>in</span> <span m='2017940'>the</span> <span
  m='2018030'>filter</span> <span m='2018420'>bank</span> <span
  m='2019770'>these</span> <span m='2020010'>delays,</span> <span
  m='2021480'>these</span> <span m='2021810'>delays,</span> <span
  m='2022860'>and</span> <span m='2023070'>the</span> <span
  m='2023160'>multiplications</span> <span m='2024540'>by</span> <span
  m='2025170'>powers</span> <span m='2025590'>of</span> <span
  m='2025730'>W.</span> <span m='2026700'>And</span> <span
  m='2027210'>the</span> <span m='2027390'>only</span> <span
  m='2027870'>additional</span> <span m='2028290'>coefficients</span> <span
  m='2029640'>and</span> <span m='2030120'>the</span> <span
  m='2030270'>only</span> <span m='2030510'>additional</span> <span
  m='2030900'>pieces</span> <span m='2031320'>that</span> <span
  m='2031440'>come</span> <span m='2031710'>in</span> <span
  m='2032850'>that</span> <span m='2033000'>differ</span> <span
  m='2033360'>between</span> <span m='2033750'>the</span> <span
  m='2033840'>filters</span> <span m='2034230'>and</span> <span
  m='2034320'>the</span> <span m='2034410'>filter</span> <span
  m='2034770'>bank</span> <span m='2035580'>are</span> <span
  m='2035790'>the</span> <span m='2035910'>coefficients</span> <span
  m='2037170'>that</span> <span m='2037430'>I</span> <span
  m='2037560'>multiply</span> <span m='2038130'>these</span> <span
  m='2038340'>outputs</span> <span m='2038850'>by.</span> <span
  m='2039620'>I</span> <span m='2039760'>need</span> <span m='2039870'>to</span>
  <span m='2039990'>multiply</span> <span m='2040500'>by</span> <span
  m='2040650'>the</span> <span m='2040740'>coefficients</span> <span
  m='2041520'>and</span> <span m='2041610'>then</span> <span
  m='2041730'>form</span> <span m='2042060'>the</span> <span
  m='2042120'>linear</span> <span m='2042450'>combination.</span> </p><p><span
  m='2044070'>So</span> <span m='2045150'>that</span> <span
  m='2045420'>then</span> <span m='2046110'>are</span> <span
  m='2046500'>the</span> <span m='2046650'>two</span> <span
  m='2047370'>primary</span> <span m='2048750'>advantages</span> <span
  m='2049380'>to</span> <span m='2049530'>frequency</span> <span
  m='2050010'>sampling</span> <span m='2050520'>structures.</span> <span
  m='2051630'>And</span> <span m='2052020'>in</span> <span
  m='2052139'>fact,</span> <span m='2052409'>frequency</span> <span
  m='2052889'>sampling</span> <span m='2053340'>structures</span> <span
  m='2054000'>have</span> <span m='2054120'>found</span> <span
  m='2055020'>application</span> <span m='2056370'>primarily</span> <span
  m='2057120'>for</span> <span m='2057300'>those</span> <span
  m='2057570'>two</span> <span m='2057739'>reasons.</span> </p><p><span
  m='2061060'>Well,</span> <span m='2061570'>there</span> <span
  m='2062080'>are</span> <span m='2063100'>lots</span> <span
  m='2063760'>of</span> <span m='2064810'>other</span> <span
  m='2066070'>structures</span> <span m='2067000'>that</span> <span
  m='2067389'>one</span> <span m='2067630'>can</span> <span
  m='2067810'>talk</span> <span m='2068139'>about,</span> <span
  m='2069159'>both</span> <span m='2069639'>for</span> <span
  m='2069909'>a</span> <span m='2069929'>finite</span> <span
  m='2070300'>impulse</span> <span m='2070750'>response</span> <span
  m='2071560'>an</span> <span m='2071830'>infinite</span> <span
  m='2072250'>impulse</span> <span m='2072639'>response</span> <span
  m='2073120'>systems.</span> <span m='2074330'>And</span> <span
  m='2074650'>as</span> <span m='2074830'>I</span> <span
  m='2074920'>stressed</span> <span m='2075370'>at</span> <span
  m='2075460'>the</span> <span m='2075580'>end</span> <span
  m='2075760'>of</span> <span m='2075850'>the</span> <span
  m='2075940'>last</span> <span m='2076300'>lecture,</span> <span
  m='2077380'>the</span> <span m='2077830'>discussion</span> <span
  m='2078639'>of</span> <span m='2078760'>structures</span> <span
  m='2079420'>in</span> <span m='2079540'>general</span> <span
  m='2080230'>and</span> <span m='2080350'>the</span> <span
  m='2080469'>kinds</span> <span m='2080800'>of</span> <span
  m='2080889'>structures</span> <span m='2081400'>that</span> <span
  m='2081520'>can</span> <span m='2081670'>be</span> <span
  m='2081790'>generated</span> <span m='2084420'>is</span> <span
  m='2085030'>very</span> <span m='2085300'>vast.</span> <span
  m='2085989'>In</span> <span m='2086110'>fact,</span> <span
  m='2086770'>it</span> <span m='2086889'>seems</span> <span
  m='2087909'>that</span> <span m='2088900'>new</span> <span
  m='2089110'>structures</span> <span m='2089710'>are</span> <span
  m='2089770'>generated</span> <span m='2090400'>faster</span> <span
  m='2091179'>than</span> <span m='2091810'>they</span> <span
  m='2091960'>can</span> <span m='2092139'>be</span> <span
  m='2092290'>evaluated.</span> <span m='2093610'>And</span> <span
  m='2094600'>I</span> <span m='2094929'>would</span> <span
  m='2095110'>like</span> <span m='2095290'>to</span> <span
  m='2095409'>terminate</span> <span m='2096010'>the</span> <span
  m='2096100'>discussion</span> <span m='2097480'>of</span> <span
  m='2097810'>specific</span> <span m='2098380'>structures</span> <span
  m='2099550'>with</span> <span m='2099820'>just</span> <span
  m='2100120'>the</span> <span m='2100270'>ones</span> <span
  m='2100540'>that</span> <span m='2100660'>I've</span> <span
  m='2100780'>shown</span> <span m='2101110'>you</span> <span
  m='2101470'>in</span> <span m='2101650'>the</span> <span
  m='2101740'>previous</span> <span m='2102190'>lecture</span> <span
  m='2102820'>and</span> <span m='2103780'>the</span> <span
  m='2104470'>ones</span> <span m='2104800'>that</span> <span
  m='2104920'>I've</span> <span m='2105040'>shown</span> <span
  m='2105310'>for</span> <span m='2105460'>finite</span> <span
  m='2105820'>impulse</span> <span m='2106150'>response</span> <span
  m='2106570'>systems</span> <span m='2107050'>in</span> <span
  m='2107140'>this</span> <span m='2107350'>lecture.</span> </p><p><span
  m='2109440'>To</span> <span m='2109770'>conclude</span> <span
  m='2110280'>that</span> <span m='2110400'>discussion</span> <span
  m='2111330'>of</span> <span m='2112290'>digital</span> <span
  m='2112650'>networks</span> <span m='2113280'>and</span> <span
  m='2113400'>digital</span> <span m='2113730'>filter</span> <span
  m='2114090'>structures,</span> <span m='2115590'>I'd</span> <span
  m='2115950'>like</span> <span m='2116430'>to</span> <span
  m='2116730'>focus</span> <span m='2117210'>finally</span> <span
  m='2118050'>on</span> <span m='2118740'>just</span> <span m='2118980'>a</span>
  <span m='2119070'>few</span> <span m='2119310'>of</span> <span
  m='2119430'>the</span> <span m='2119550'>issues,</span> <span
  m='2119970'>one</span> <span m='2120180'>primarily,</span> <span
  m='2121560'>involved</span> <span m='2122490'>in</span> <span
  m='2123030'>the</span> <span m='2123270'>comparison</span> <span
  m='2124290'>of</span> <span m='2124350'>filter</span> <span
  m='2124740'>structures.</span> <span m='2125940'>Now</span> <span
  m='2126330'>we've</span> <span m='2126480'>talked</span> <span
  m='2126810'>about</span> <span m='2127080'>different</span> <span
  m='2127350'>structures.</span> <span m='2128790'>One</span> <span
  m='2128940'>of</span> <span m='2129060'>the</span> <span
  m='2129180'>things</span> <span m='2129570'>that</span> <span
  m='2129720'>obviously</span> <span m='2130620'>is</span> <span
  m='2130800'>true</span> <span m='2131250'>is</span> <span
  m='2131430'>that</span> <span m='2131790'>from</span> <span
  m='2131970'>a</span> <span m='2132030'>strictly</span> <span
  m='2132390'>mathematical</span> <span m='2133170'>point</span> <span
  m='2133470'>of</span> <span m='2133530'>view,</span> <span
  m='2134400'>all</span> <span m='2134640'>of</span> <span
  m='2134760'>these</span> <span m='2134910'>structures,</span> <span
  m='2135660'>different</span> <span m='2136350'>ways</span> <span
  m='2136650'>of</span> <span m='2136770'>implementing</span> <span
  m='2137520'>the</span> <span m='2137640'>same</span> <span
  m='2138120'>transfer</span> <span m='2138630'>function,</span> <span
  m='2139710'>obviously</span> <span m='2140340'>implement</span> <span
  m='2141300'>the</span> <span m='2141390'>same</span> <span
  m='2141690'>transfer</span> <span m='2142140'>function.</span> <span
  m='2142980'>That</span> <span m='2143130'>is</span> <span
  m='2143820'>algebraically</span> <span m='2144930'>or</span> <span
  m='2145080'>theoretically,</span> <span m='2146670'>all</span> <span
  m='2147270'>of</span> <span m='2147360'>the</span> <span
  m='2147450'>structures</span> <span m='2148890'>from</span> <span
  m='2149430'>an</span> <span m='2149550'>input</span> <span
  m='2149850'>output</span> <span m='2150270'>point</span> <span
  m='2150540'>of</span> <span m='2150630'>view</span> <span
  m='2151110'>are</span> <span m='2151260'>indistinguishable.</span> <span
  m='2152670'>In</span> <span m='2152760'>other</span> <span
  m='2152970'>words,</span> <span m='2153370'>they</span> <span
  m='2153390'>generate</span> <span m='2153870'>the</span> <span
  m='2153960'>same</span> <span m='2154230'>transfer</span> <span
  m='2154680'>function.</span> </p><p><span m='2156820'>On</span> <span
  m='2156840'>the</span> <span m='2156930'>other</span> <span
  m='2157110'>hand,</span> <span m='2157540'>there</span> <span
  m='2157770'>are</span> <span m='2158040'>a</span> <span
  m='2158070'>variety</span> <span m='2158610'>of</span> <span
  m='2158730'>issues</span> <span m='2159630'>when</span> <span
  m='2159840'>one</span> <span m='2160050'>considers</span> <span
  m='2160590'>the</span> <span m='2160710'>practical</span> <span
  m='2161280'>implementation</span> <span m='2162060'>of</span> <span
  m='2162150'>digital</span> <span m='2162510'>filters</span> <span
  m='2163590'>that</span> <span m='2163770'>have</span> <span
  m='2164010'>to</span> <span m='2164130'>be</span> <span
  m='2164280'>considered</span> <span m='2166590'>in</span> <span
  m='2167250'>choosing</span> <span m='2168900'>different</span> <span
  m='2169200'>filter</span> <span m='2169560'>structures.</span> <span
  m='2171330'>One</span> <span m='2171540'>of</span> <span
  m='2171630'>them</span> <span m='2171990'>I</span> <span
  m='2172170'>suggested</span> <span m='2173250'>last</span> <span
  m='2173610'>time</span> <span m='2174090'>to</span> <span
  m='2174240'>be</span> <span m='2174660'>the</span> <span
  m='2174780'>number</span> <span m='2175080'>of</span> <span
  m='2175170'>delays</span> <span m='2175620'>involved.</span> <span
  m='2176160'>And</span> <span m='2176250'>we</span> <span
  m='2176370'>saw</span> <span m='2176640'>the</span> <span
  m='2176730'>difference</span> <span m='2177180'>between</span> <span
  m='2178350'>non-canonic</span> <span m='2179430'>and</span> <span
  m='2179550'>canonic</span> <span m='2179970'>form</span> <span
  m='2180270'>structures.</span> <span m='2182460'>Delays</span> <span
  m='2183100'>mean</span> <span m='2183330'>registers.</span> <span
  m='2183960'>And</span> <span m='2184050'>registers</span> <span
  m='2184620'>mean</span> <span m='2184830'>hardware.</span> </p><p><span
  m='2186450'>In</span> <span m='2186690'>talking</span> <span
  m='2187050'>about</span> <span m='2187260'>linear</span> <span
  m='2187590'>phase</span> <span m='2187950'>filters,</span> <span
  m='2188400'>we</span> <span m='2188520'>saw</span> <span
  m='2188910'>that</span> <span m='2189330'>if</span> <span
  m='2189630'>we</span> <span m='2189750'>exploit</span> <span
  m='2190200'>the</span> <span m='2190290'>linear</span> <span
  m='2190620'>phase</span> <span m='2190950'>property,</span> <span
  m='2192030'>then</span> <span m='2192420'>we</span> <span
  m='2192630'>can</span> <span m='2192870'>reduce</span> <span
  m='2193260'>the</span> <span m='2193380'>number</span> <span
  m='2193650'>of</span> <span m='2193740'>multiplications</span> <span
  m='2194670'>involved</span> <span m='2195480'>by</span> <span
  m='2195690'>half.</span> <span m='2196860'>And</span> <span
  m='2197460'>multiplications,</span> <span m='2198480'>again,</span> <span
  m='2200100'>mean</span> <span m='2200310'>hardware</span> <span
  m='2201000'>or</span> <span m='2201150'>speed</span> <span
  m='2201630'>or</span> <span m='2201750'>something</span> <span
  m='2202140'>of</span> <span m='2202200'>that</span> <span
  m='2202410'>sort</span> <span m='2202860'>in</span> <span
  m='2202980'>terms</span> <span m='2203310'>of</span> <span
  m='2203400'>the</span> <span m='2203520'>implementation.</span> </p><p><span
  m='2205840'>Another</span> <span m='2206040'>common</span> <span
  m='2206430'>characteristic</span> <span m='2207600'>that</span> <span
  m='2207870'>can</span> <span m='2208020'>be</span> <span
  m='2208170'>focused</span> <span m='2208710'>on</span> <span
  m='2208980'>in</span> <span m='2209100'>comparing</span> <span
  m='2209580'>structures</span> <span m='2210900'>is</span> <span
  m='2211650'>what</span> <span m='2211950'>you</span> <span
  m='2212100'>could</span> <span m='2212250'>refer</span> <span
  m='2212610'>to</span> <span m='2212790'>as</span> <span
  m='2212910'>modularity.</span> <span m='2214350'>It's</span> <span
  m='2214470'>particularly</span> <span m='2215130'>important</span> <span
  m='2215760'>in</span> <span m='2215850'>hardware</span> <span
  m='2216300'>implementation</span> <span m='2217050'>of</span> <span
  m='2217140'>digital</span> <span m='2217500'>filters,</span> <span
  m='2218490'>where</span> <span m='2218880'>perhaps</span> <span
  m='2219630'>you</span> <span m='2219780'>would</span> <span
  m='2219930'>like</span> <span m='2220170'>your</span> <span
  m='2220290'>structure</span> <span m='2221520'>to</span> <span
  m='2222450'>have</span> <span m='2222660'>stages</span> <span
  m='2223380'>in</span> <span m='2223530'>it</span> <span
  m='2223980'>that</span> <span m='2224370'>are</span> <span
  m='2224640'>identical,</span> <span m='2225760'>so</span> <span
  m='2225900'>that</span> <span m='2226860'>the</span> <span
  m='2227160'>implications</span> <span m='2227970'>in</span> <span
  m='2228060'>terms</span> <span m='2228570'>of</span> <span
  m='2228720'>the</span> <span m='2228840'>hardware</span> <span
  m='2229470'>are</span> <span m='2229770'>that</span> <span
  m='2230470'>a</span> <span m='2230550'>section</span> <span
  m='2231150'>or</span> <span m='2231270'>sections</span> <span
  m='2231780'>can</span> <span m='2231930'>be</span> <span
  m='2232050'>multiplexed</span> <span m='2232830'>and</span> <span
  m='2233310'>therefore</span> <span m='2233940'>used</span> <span
  m='2234240'>over</span> <span m='2234480'>and</span> <span
  m='2234570'>over</span> <span m='2234870'>again.</span> </p><p><span
  m='2236910'>And</span> <span m='2237540'>another</span> <span
  m='2238350'>issue,</span> <span m='2239650'>which</span> <span
  m='2240000'>is</span> <span m='2240210'>the</span> <span
  m='2240330'>one</span> <span m='2240510'>that</span> <span
  m='2240630'>I'd</span> <span m='2240780'>like</span> <span
  m='2240960'>to</span> <span m='2241080'>direct</span> <span
  m='2241440'>our</span> <span m='2241560'>attention</span> <span
  m='2242040'>to</span> <span m='2242250'>finally</span> <span
  m='2243450'>are</span> <span m='2244110'>the</span> <span
  m='2244500'>effect</span> <span m='2245850'>of</span> <span
  m='2246150'>finite</span> <span m='2246540'>register</span> <span
  m='2247140'>length</span> <span m='2248460'>on</span> <span
  m='2248700'>the</span> <span m='2248790'>characteristics</span> <span
  m='2249900'>of</span> <span m='2250050'>the</span> <span
  m='2250140'>system.</span> <span m='2251640'>And</span> <span
  m='2252330'>these</span> <span m='2252630'>characteristics,</span> <span
  m='2253740'>or</span> <span m='2253890'>the</span> <span
  m='2254010'>finite</span> <span m='2254340'>register</span> <span
  m='2254790'>length</span> <span m='2255110'>effects,</span> <span
  m='2256150'>in</span> <span m='2256170'>fact,</span> <span
  m='2256750'>are</span> <span m='2256860'>very</span> <span
  m='2257280'>heavily</span> <span m='2257880'>dependent</span> <span
  m='2258660'>on</span> <span m='2258840'>the</span> <span
  m='2258930'>filter</span> <span m='2259260'>structures</span> <span
  m='2259800'>that</span> <span m='2259920'>are</span> <span
  m='2259980'>used.</span> </p><p><span m='2261720'>There</span> <span
  m='2261840'>are</span> <span m='2261870'>two</span> <span
  m='2262080'>kinds</span> <span m='2262380'>of</span> <span
  m='2262440'>finite</span> <span m='2262830'>register</span> <span
  m='2263280'>length</span> <span m='2263550'>effects.</span> <span
  m='2264780'>One</span> <span m='2264990'>of</span> <span
  m='2265110'>them</span> <span m='2265710'>has</span> <span
  m='2266010'>to</span> <span m='2266130'>do</span> <span
  m='2266340'>with</span> <span m='2266490'>the</span> <span
  m='2266580'>fact</span> <span m='2267330'>that</span> <span
  m='2269220'>arithmetic</span> <span m='2270570'>in</span> <span
  m='2270690'>a</span> <span m='2270750'>digital</span> <span
  m='2271140'>filter,</span> <span m='2272220'>specifically</span> <span
  m='2273150'>in</span> <span m='2273540'>a</span> <span
  m='2273660'>recursive</span> <span m='2274200'>digital</span> <span
  m='2274590'>filter,</span> <span m='2275610'>has</span> <span
  m='2276030'>to</span> <span m='2276330'>be</span> <span
  m='2276510'>done,</span> <span m='2276960'>of</span> <span
  m='2277080'>course,</span> <span m='2277350'>with</span> <span
  m='2277470'>finite</span> <span m='2277860'>register</span> <span
  m='2278340'>length,</span> <span m='2278880'>and</span> <span
  m='2279120'>it</span> <span m='2279210'>has</span> <span m='2279480'>to</span>
  <span m='2279600'>be</span> <span m='2279840'>truncated.</span> <span
  m='2280980'>In</span> <span m='2281070'>other</span> <span
  m='2281280'>words,</span> <span m='2282060'>multiplications,</span> <span
  m='2283230'>the</span> <span m='2283350'>result</span> <span
  m='2283800'>of</span> <span m='2284540'>B</span> <span m='2284760'>bits</span>
  <span m='2285060'>times</span> <span m='2285330'>B</span> <span
  m='2285540'>bits</span> <span m='2285840'>results</span> <span
  m='2286180'>in</span> <span m='2286350'>2B</span> <span
  m='2286830'>bits.</span> <span m='2287730'>If</span> <span
  m='2287850'>this</span> <span m='2288030'>goes</span> <span
  m='2288300'>on</span> <span m='2288660'>indefinitely,</span> <span
  m='2289410'>obviously</span> <span m='2289890'>the</span> <span
  m='2290010'>register</span> <span m='2290490'>length</span> <span
  m='2291060'>grows</span> <span m='2291450'>indefinitely.</span> </p><p><span
  m='2292710'>And</span> <span m='2292830'>so</span> <span
  m='2297420'>the</span> <span m='2297510'>results</span> <span
  m='2297840'>of</span> <span m='2297930'>arithmetic</span> <span
  m='2298440'>have</span> <span m='2298680'>to</span> <span
  m='2298800'>be</span> <span m='2298890'>truncated</span> <span
  m='2299580'>or</span> <span m='2299730'>rounded.</span> <span
  m='2300630'>And</span> <span m='2300780'>this</span> <span
  m='2300960'>generates</span> <span m='2301860'>some</span> <span
  m='2302760'>noise</span> <span m='2303450'>or</span> <span
  m='2303540'>essentially</span> <span m='2304230'>noise</span> <span
  m='2304920'>in</span> <span m='2305460'>the</span> <span
  m='2305580'>filter</span> <span m='2305880'>output.</span> <span
  m='2307230'>And</span> <span m='2308220'>the</span> <span
  m='2308310'>second</span> <span m='2308730'>thing</span> <span
  m='2309090'>is</span> <span m='2309240'>the</span> <span
  m='2309360'>fact</span> <span m='2310170'>that</span> <span
  m='2310320'>coefficients</span> <span m='2311700'>have</span> <span
  m='2311940'>to</span> <span m='2312090'>be</span> <span
  m='2313230'>represented</span> <span m='2313980'>in</span> <span
  m='2314130'>finite</span> <span m='2314580'>register</span> <span
  m='2315030'>length.</span> <span m='2315480'>That</span> <span
  m='2315750'>is</span> <span m='2316050'>coefficients</span> <span
  m='2316950'>or</span> <span m='2317100'>parameters</span> <span
  m='2317760'>have</span> <span m='2317970'>to</span> <span
  m='2318060'>be</span> <span m='2318150'>truncated.</span> </p><p><span
  m='2319410'>What</span> <span m='2319680'>I</span> <span
  m='2319800'>would</span> <span m='2319920'>like</span> <span
  m='2320130'>to</span> <span m='2320280'>do</span> <span m='2320790'>in</span>
  <span m='2321030'>closing</span> <span m='2321480'>the</span> <span
  m='2321540'>lecture</span> <span m='2322230'>is</span> <span
  m='2322980'>just</span> <span m='2323400'>briefly</span> <span
  m='2324030'>give</span> <span m='2324270'>you</span> <span
  m='2324630'>a</span> <span m='2324690'>glimpse</span> <span
  m='2325410'>into</span> <span m='2325950'>some</span> <span
  m='2326220'>of</span> <span m='2326310'>the</span> <span
  m='2326430'>issues</span> <span m='2327030'>of</span> <span
  m='2327840'>the</span> <span m='2328050'>coefficient,</span> <span
  m='2328950'>or</span> <span m='2329100'>parameter,</span> <span
  m='2329730'>quantization</span> <span m='2331230'>and</span> <span
  m='2332490'>not</span> <span m='2333000'>delve</span> <span
  m='2333810'>any</span> <span m='2334110'>in</span> <span
  m='2334260'>any</span> <span m='2334440'>more</span> <span
  m='2334620'>detail</span> <span m='2335640'>into</span> <span
  m='2336300'>the</span> <span m='2336660'>relatively</span> <span
  m='2337500'>complex</span> <span m='2338160'>issue</span> <span
  m='2338640'>of</span> <span m='2338790'>finite</span> <span
  m='2339210'>register</span> <span m='2339660'>length</span> <span
  m='2339870'>effects.</span> <span m='2341130'>But</span> <span
  m='2341520'>let's</span> <span m='2342150'>focus</span> <span
  m='2342570'>just</span> <span m='2342840'>a</span> <span
  m='2342900'>little</span> <span m='2343200'>bit,</span> <span
  m='2343920'>just</span> <span m='2344160'>a</span> <span
  m='2344220'>little,</span> <span m='2345540'>on</span> <span
  m='2346470'>the</span> <span m='2346560'>effects</span> <span
  m='2346920'>of</span> <span m='2347040'>parameter</span> <span
  m='2347640'>quantization.</span> <span m='2350720'>In</span> <span
  m='2350840'>particular,</span> <span m='2352040'>we</span> <span
  m='2352250'>have,</span> <span m='2352550'>of</span> <span
  m='2352670'>course,</span> <span m='2353240'>the</span> <span
  m='2353630'>general</span> <span m='2354110'>form</span> <span
  m='2354650'>for</span> <span m='2355100'>a</span> <span
  m='2355160'>system</span> <span m='2355610'>function</span> <span
  m='2356210'>as</span> <span m='2356390'>a</span> <span
  m='2356450'>ratio</span> <span m='2356870'>of</span> <span
  m='2356930'>polynomials</span> <span m='2358460'>in</span> <span
  m='2358640'>z</span> <span m='2358850'>to</span> <span m='2359000'>the</span>
  <span m='2359120'>minus</span> <span m='2359510'>1,</span> <span
  m='2359948'>where</span> <span m='2361700'>the</span> <span
  m='2361820'>denominator</span> <span m='2362480'>polynomial,</span> <span
  m='2363500'>as</span> <span m='2363650'>we've</span> <span
  m='2363860'>been</span> <span m='2363980'>writing</span> <span
  m='2364400'>it,</span> <span m='2364880'>is</span> <span m='2365040'>of</span>
  <span m='2365150'>the</span> <span m='2365240'>form</span> <span
  m='2365630'>1</span> <span m='2365840'>minus</span> <span
  m='2366260'>the</span> <span m='2366380'>sum</span> <span
  m='2366920'>of</span> <span m='2367280'>a</span> <span m='2367580'>sub</span>
  <span m='2367700'>k</span> <span m='2368060'>times</span> <span
  m='2368430'>z</span> <span m='2368575'>to</span> <span m='2368720'>the</span>
  <span m='2368840'>minus</span> <span m='2369220'>k.</span> </p><p><span
  m='2371820'>Well,</span> <span m='2372390'>let's</span> <span
  m='2372690'>imagine</span> <span m='2373680'>that</span> <span
  m='2374190'>what</span> <span m='2374370'>we</span> <span
  m='2374520'>would</span> <span m='2374670'>like</span> <span
  m='2374940'>to</span> <span m='2375090'>do</span> <span m='2376260'>or</span>
  <span m='2376560'>that</span> <span m='2376710'>it's</span> <span
  m='2376860'>reasonable</span> <span m='2378270'>to</span> <span
  m='2379470'>tie</span> <span m='2380220'>the</span> <span
  m='2380910'>investigation</span> <span m='2381870'>of</span> <span
  m='2381990'>H</span> <span m='2382150'>of</span> <span m='2382310'>z</span>
  <span m='2382830'>in</span> <span m='2382950'>terms</span> <span
  m='2383310'>of</span> <span m='2383400'>parameter</span> <span
  m='2384020'>errors</span> <span m='2384990'>to</span> <span
  m='2385650'>the</span> <span m='2385860'>accuracy,</span> <span
  m='2387480'>with</span> <span m='2387750'>which</span> <span
  m='2388620'>the</span> <span m='2388800'>poles</span> <span
  m='2389310'>of</span> <span m='2389400'>the</span> <span
  m='2389490'>transfer</span> <span m='2389970'>function</span> <span
  m='2390600'>can</span> <span m='2390780'>be</span> <span
  m='2390930'>placed.</span> <span m='2392800'>We</span> <span
  m='2392920'>can</span> <span m='2393070'>express</span> <span
  m='2394480'>this</span> <span m='2394690'>polynomial,</span> <span
  m='2395750'>the</span> <span m='2395860'>denominator</span> <span
  m='2396460'>polynomial,</span> <span m='2397740'>in</span> <span
  m='2397870'>factored</span> <span m='2398350'>form,</span> <span
  m='2399070'>where,</span> <span m='2399250'>of</span> <span
  m='2399370'>course,</span> <span m='2399700'>each</span> <span
  m='2399940'>of</span> <span m='2400060'>the</span> <span
  m='2400150'>factors</span> <span m='2401260'>involves</span> <span
  m='2402100'>the</span> <span m='2402220'>poles</span> <span
  m='2402640'>of</span> <span m='2402730'>the</span> <span
  m='2402820'>system</span> <span m='2403540'>explicitly.</span> </p><p><span
  m='2406000'>And</span> <span m='2406120'>now</span> <span
  m='2406600'>as</span> <span m='2406900'>we</span> <span
  m='2407020'>talk</span> <span m='2407320'>about</span> <span
  m='2407560'>implementing</span> <span m='2408160'>this</span> <span
  m='2408280'>system,</span> <span m='2410210'>the</span> <span
  m='2410300'>coefficients</span> <span m='2411950'>in</span> <span
  m='2412460'>the</span> <span m='2412580'>denominator</span> <span
  m='2413210'>polynomial,</span> <span m='2414220'>and</span> <span
  m='2414380'>in</span> <span m='2414470'>the</span> <span
  m='2414560'>numerator</span> <span m='2415040'>polynomial</span> <span
  m='2415740'>also,</span> <span m='2417370'>have</span> <span
  m='2417670'>errors</span> <span m='2418480'>due</span> <span
  m='2418750'>to</span> <span m='2418840'>the</span> <span
  m='2418990'>fact</span> <span m='2419650'>that</span> <span
  m='2419860'>they</span> <span m='2420010'>have</span> <span
  m='2420250'>to</span> <span m='2420370'>be</span> <span
  m='2420490'>represented</span> <span m='2421420'>in</span> <span
  m='2421570'>a</span> <span m='2421630'>finite</span> <span
  m='2422050'>register</span> <span m='2422570'>length.</span> <span
  m='2423980'>So</span> <span m='2424670'>we</span> <span m='2424790'>can</span>
  <span m='2424940'>represent</span> <span m='2425540'>that</span> <span
  m='2426410'>as</span> <span m='2427100'>the</span> <span
  m='2427220'>coefficient</span> <span m='2428210'>that</span> <span
  m='2428540'>we</span> <span m='2428750'>actually</span> <span
  m='2429920'>arrive</span> <span m='2430340'>at</span> <span
  m='2431240'>is</span> <span m='2431390'>the</span> <span
  m='2431480'>coefficient</span> <span m='2432200'>that</span> <span
  m='2432290'>we</span> <span m='2432470'>really</span> <span
  m='2432800'>want</span> <span m='2433790'>plus</span> <span
  m='2434360'>some</span> <span m='2434630'>error.</span> </p><p><span
  m='2435800'>And</span> <span m='2435920'>consequently,</span> <span
  m='2437630'>the</span> <span m='2437750'>pole</span> <span
  m='2438110'>location,</span> <span m='2438800'>the</span> <span
  m='2438890'>location</span> <span m='2439700'>of</span> <span
  m='2439850'>each</span> <span m='2440060'>of</span> <span
  m='2440120'>the</span> <span m='2440210'>poles,</span> <span
  m='2441230'>the</span> <span m='2441380'>i-th</span> <span
  m='2441620'>pole,</span> <span m='2441920'>for</span> <span
  m='2442130'>example,</span> <span m='2443850'>is</span> <span
  m='2443960'>where</span> <span m='2444260'>we</span> <span
  m='2444440'>want</span> <span m='2444710'>it</span> <span
  m='2445400'>plus</span> <span m='2446000'>some</span> <span
  m='2446270'>deviation.</span> <span m='2448880'>Now,</span> <span
  m='2449260'>we</span> <span m='2449440'>can</span> <span
  m='2449590'>examine</span> <span m='2450490'>what</span> <span
  m='2450760'>this</span> <span m='2451000'>deviation</span> <span
  m='2451750'>is</span> <span m='2453070'>by</span> <span
  m='2454000'>essentially</span> <span m='2455050'>assuming</span> <span
  m='2456400'>that</span> <span m='2456970'>the</span> <span
  m='2457090'>variation</span> <span m='2458080'>in</span> <span
  m='2458230'>these</span> <span m='2458380'>parameters</span> <span
  m='2459400'>is</span> <span m='2459490'>small.</span> <span
  m='2461590'>And</span> <span m='2461980'>expressing</span> <span
  m='2463390'>this</span> <span m='2463630'>error</span> <span
  m='2464260'>in</span> <span m='2464410'>terms</span> <span
  m='2465070'>of</span> <span m='2465790'>the</span> <span
  m='2465880'>partial</span> <span m='2466330'>derivatives</span> <span
  m='2467590'>of</span> <span m='2468160'>the</span> <span
  m='2468280'>pole</span> <span m='2468580'>locations</span> <span
  m='2469840'>expressed</span> <span m='2470470'>in</span> <span
  m='2470590'>terms</span> <span m='2470950'>of</span> <span
  m='2471010'>the</span> <span m='2471100'>coefficients</span> <span
  m='2471970'>a</span> <span m='2472120'>sub</span> <span m='2472375'>k.</span>
  <span m='2473320'>In</span> <span m='2473440'>other</span> <span
  m='2473620'>words,</span> <span m='2474620'>we</span> <span
  m='2474640'>can</span> <span m='2474820'>express</span> <span
  m='2475960'>the</span> <span m='2476080'>movement</span> <span
  m='2477340'>of</span> <span m='2477490'>the</span> <span
  m='2477610'>pole</span> <span m='2479380'>in</span> <span
  m='2479500'>terms</span> <span m='2480130'>of</span> <span
  m='2480640'>the</span> <span m='2480730'>movement</span> <span
  m='2481270'>of</span> <span m='2481360'>the</span> <span
  m='2481450'>coefficients</span> <span m='2483220'>as</span> <span
  m='2483505'>a</span> <span m='2483790'>sum</span> <span m='2484390'>of</span>
  <span m='2485290'>the</span> <span m='2485410'>partial</span> <span
  m='2485860'>derivative</span> <span m='2486730'>of</span> <span
  m='2487750'>the</span> <span m='2487870'>pole,</span> <span
  m='2489280'>the</span> <span m='2489430'>i-th</span> <span
  m='2489700'>pole--</span> <span m='2490150'>that's</span> <span
  m='2490330'>the</span> <span m='2490390'>one</span> <span
  m='2490540'>we're</span> <span m='2490630'>talking</span> <span
  m='2490960'>about</span> <span m='2491260'>here--</span> <span
  m='2491620'>with</span> <span m='2491860'>respect</span> <span
  m='2492220'>to</span> <span m='2492340'>the</span> <span
  m='2492430'>k-th</span> <span m='2492730'>coefficient</span> <span
  m='2493900'>times</span> <span m='2494500'>the</span> <span
  m='2494680'>error</span> <span m='2495070'>in</span> <span
  m='2495190'>the</span> <span m='2495280'>k-th</span> <span
  m='2495550'>coefficient.</span> </p><p><span m='2497810'>Well,</span> <span
  m='2498400'>this</span> <span m='2498550'>can</span> <span
  m='2498730'>be</span> <span m='2498850'>tracked</span> <span
  m='2499210'>through--</span> <span m='2499540'>and</span> <span
  m='2499630'>this</span> <span m='2499810'>is</span> <span
  m='2499930'>done</span> <span m='2500200'>in</span> <span
  m='2500320'>the</span> <span m='2500470'>text.</span> <span
  m='2500950'>I</span> <span m='2501040'>won't</span> <span
  m='2501220'>go</span> <span m='2501400'>through</span> <span
  m='2501610'>the</span> <span m='2501760'>algebra--</span> <span
  m='2502750'>but</span> <span m='2502960'>basically,</span> <span
  m='2503800'>the</span> <span m='2503890'>result</span> <span
  m='2504400'>is</span> <span m='2505330'>that</span> <span
  m='2505840'>this</span> <span m='2506050'>partial</span> <span
  m='2506500'>derivative</span> <span m='2507790'>can</span> <span
  m='2508000'>be</span> <span m='2508360'>expressed</span> <span
  m='2509230'>in</span> <span m='2509380'>this</span> <span
  m='2509590'>form</span> <span m='2509890'>where</span> <span
  m='2510430'>the</span> <span m='2510550'>important</span> <span
  m='2510970'>thing</span> <span m='2511450'>to</span> <span
  m='2511570'>focus</span> <span m='2512080'>on</span> <span
  m='2513040'>is</span> <span m='2513190'>that</span> <span
  m='2513460'>what's</span> <span m='2513730'>involved</span> <span
  m='2514210'>in</span> <span m='2514330'>the</span> <span
  m='2514420'>denominator</span> <span m='2515680'>is</span> <span
  m='2516310'>the</span> <span m='2516610'>product</span> <span
  m='2517390'>of</span> <span m='2517570'>the</span> <span
  m='2517690'>difference</span> <span m='2518500'>in</span> <span
  m='2518620'>the</span> <span m='2518710'>pole</span> <span
  m='2518950'>locations.</span> <span m='2521390'>Let's</span> <span
  m='2521530'>assume,</span> <span m='2522020'>for</span> <span
  m='2522100'>example,</span> <span m='2523040'>that</span> <span
  m='2523390'>all</span> <span m='2523630'>of</span> <span
  m='2523750'>the</span> <span m='2523840'>poles</span> <span
  m='2524530'>are</span> <span m='2524620'>clustered</span> <span
  m='2525400'>inside</span> <span m='2525850'>a</span> <span
  m='2525910'>circle</span> <span m='2527290'>of</span> <span
  m='2527950'>radius</span> <span m='2528490'>epsilon.</span> <span
  m='2529450'>In</span> <span m='2529570'>other</span> <span
  m='2529720'>words,</span> <span m='2530060'>the</span> <span
  m='2530160'>largest</span> <span m='2530530'>distance</span> <span
  m='2531040'>between</span> <span m='2531460'>the</span> <span
  m='2531550'>poles</span> <span m='2532600'>is</span> <span
  m='2532750'>epsilon.</span> </p><p><span m='2534780'>What</span> <span
  m='2534970'>that</span> <span m='2535180'>says</span> <span
  m='2535570'>then</span> <span m='2536260'>is</span> <span
  m='2536500'>that</span> <span m='2537880'>when</span> <span
  m='2538090'>we</span> <span m='2538300'>substitute</span> <span
  m='2539050'>that</span> <span m='2540010'>in</span> <span
  m='2540370'>for</span> <span m='2540550'>this</span> <span
  m='2540760'>expression,</span> <span m='2542350'>the</span> <span
  m='2542500'>absolute</span> <span m='2542950'>value</span> <span
  m='2543760'>of</span> <span m='2544540'>the</span> <span
  m='2545650'>change</span> <span m='2546070'>in</span> <span
  m='2546160'>the</span> <span m='2546250'>pole</span> <span
  m='2546490'>location</span> <span m='2547240'>with</span> <span
  m='2547420'>respect</span> <span m='2548380'>to</span> <span
  m='2548860'>a</span> <span m='2548920'>change</span> <span
  m='2549640'>in</span> <span m='2550030'>the</span> <span
  m='2550120'>coefficient</span> <span m='2551570'>has</span> <span
  m='2551880'>in</span> <span m='2552030'>the</span> <span
  m='2552110'>denominator</span> <span m='2553180'>epsilon</span> <span
  m='2554110'>raised</span> <span m='2554380'>to</span> <span
  m='2554530'>the</span> <span m='2554680'>n-th</span> <span
  m='2554860'>power.</span> <span m='2556220'>Well,</span> <span
  m='2556370'>what</span> <span m='2556490'>does</span> <span
  m='2556610'>that</span> <span m='2556790'>mean?</span> </p><p><span
  m='2558000'>What</span> <span m='2558080'>it</span> <span
  m='2558170'>means</span> <span m='2558860'>is</span> <span
  m='2559070'>that</span> <span m='2560120'>if</span> <span
  m='2560330'>the</span> <span m='2560480'>poles</span> <span
  m='2561290'>are</span> <span m='2561410'>clustered</span> <span
  m='2563280'>within</span> <span m='2563520'>a</span> <span
  m='2563580'>radius</span> <span m='2564180'>within</span> <span
  m='2564390'>a</span> <span m='2564450'>circle</span> <span
  m='2565140'>of</span> <span m='2565290'>radius</span> <span
  m='2565710'>epsilon,</span> <span m='2568000'>for</span> <span
  m='2568210'>any</span> <span m='2568480'>given</span> <span
  m='2568810'>pole</span> <span m='2570010'>the</span> <span
  m='2570130'>higher</span> <span m='2570640'>the</span> <span
  m='2570850'>order</span> <span m='2571330'>of</span> <span
  m='2571450'>the</span> <span m='2571570'>polynomial</span> <span
  m='2573260'>that</span> <span m='2573310'>we</span> <span
  m='2573460'>use</span> <span m='2573760'>to</span> <span
  m='2573880'>implement</span> <span m='2574420'>the</span> <span
  m='2574510'>pole,</span> <span m='2575680'>the</span> <span
  m='2575980'>greater</span> <span m='2576490'>the</span> <span
  m='2576640'>sensitivity</span> <span m='2577720'>of</span> <span
  m='2577870'>the</span> <span m='2577960'>pole</span> <span
  m='2578200'>location</span> <span m='2578890'>with</span> <span
  m='2579040'>respect</span> <span m='2579400'>to</span> <span
  m='2579520'>the</span> <span m='2579620'>coefficient.</span> <span
  m='2580990'>So</span> <span m='2581710'>this</span> <span
  m='2581920'>says</span> <span m='2582790'>that</span> <span
  m='2583960'>if</span> <span m='2584380'>we</span> <span
  m='2584650'>implement</span> <span m='2585790'>the</span> <span
  m='2585880'>poles</span> <span m='2586300'>of</span> <span
  m='2586390'>the</span> <span m='2586480'>system,</span> <span
  m='2587050'>or</span> <span m='2587200'>when</span> <span
  m='2587440'>we</span> <span m='2587560'>implement</span> <span
  m='2587980'>the</span> <span m='2588100'>poles</span> <span
  m='2588430'>of</span> <span m='2588520'>the</span> <span
  m='2588610'>system,</span> <span m='2589600'>it</span> <span
  m='2589750'>obviously</span> <span m='2590530'>is</span> <span
  m='2590980'>better</span> <span m='2592150'>to</span> <span
  m='2592420'>implement</span> <span m='2593020'>the</span> <span
  m='2593110'>poles</span> <span m='2594460'>through</span> <span
  m='2594880'>a</span> <span m='2594970'>lower</span> <span
  m='2595390'>order</span> <span m='2595630'>polynomial</span> <span
  m='2596620'>rather</span> <span m='2596980'>than</span> <span
  m='2597130'>through</span> <span m='2597370'>a</span> <span
  m='2597400'>higher</span> <span m='2597730'>order</span> <span
  m='2597970'>polynomial.</span> </p><p><span m='2599750'>What</span> <span
  m='2599870'>does</span> <span m='2600020'>this</span> <span
  m='2600200'>mean</span> <span m='2600410'>in</span> <span
  m='2600500'>terms</span> <span m='2600830'>of</span> <span
  m='2600890'>the</span> <span m='2600980'>filter</span> <span
  m='2601340'>structures</span> <span m='2601850'>we've</span> <span
  m='2601970'>been</span> <span m='2602120'>talking</span> <span
  m='2602540'>about?</span> <span m='2603410'>It</span> <span
  m='2603530'>means</span> <span m='2603800'>basically</span> <span
  m='2604970'>that</span> <span m='2605120'>the</span> <span
  m='2605240'>direct</span> <span m='2605630'>form</span> <span
  m='2605930'>structures</span> <span m='2606770'>are</span> <span
  m='2606920'>the</span> <span m='2607040'>most</span> <span
  m='2607310'>sensitive,</span> <span m='2609410'>that</span> <span
  m='2609950'>the</span> <span m='2610040'>cascade</span> <span
  m='2610910'>form</span> <span m='2611210'>structures</span> <span
  m='2612320'>are</span> <span m='2612500'>certainly</span> <span
  m='2612950'>less</span> <span m='2613220'>sensitive</span> <span
  m='2614180'>than</span> <span m='2614420'>the</span> <span
  m='2614510'>direct</span> <span m='2614900'>form</span> <span
  m='2615200'>structure,</span> <span m='2616370'>and</span> <span
  m='2617060'>the</span> <span m='2617180'>parallel</span> <span
  m='2617660'>form</span> <span m='2617990'>structure</span> <span
  m='2618530'>in</span> <span m='2618650'>terms</span> <span
  m='2618950'>of</span> <span m='2619040'>the</span> <span
  m='2619160'>implementation</span> <span m='2619880'>of</span> <span
  m='2619970'>the</span> <span m='2620060'>poles</span> <span
  m='2621260'>have</span> <span m='2621470'>the</span> <span
  m='2621590'>same</span> <span m='2621980'>type</span> <span
  m='2622310'>of</span> <span m='2622400'>hypersensitivity</span> <span
  m='2623360'>as</span> <span m='2623510'>the</span> <span
  m='2623600'>cascade</span> <span m='2624200'>form</span> <span
  m='2624720'>and</span> <span m='2624770'>likewise</span> <span
  m='2625520'>are</span> <span m='2625640'>less</span> <span
  m='2625850'>sensitive</span> <span m='2626810'>than</span> <span
  m='2626990'>the</span> <span m='2627080'>direct</span> <span
  m='2627440'>form.</span> </p><p><span m='2629450'>Even</span> <span
  m='2630230'>in</span> <span m='2630980'>the</span> <span
  m='2631100'>cascade</span> <span m='2631760'>form</span> <span
  m='2632090'>structure,</span> <span m='2633180'>though,</span> <span
  m='2633920'>there's</span> <span m='2634100'>some</span> <span
  m='2634280'>flexibility.</span> <span m='2635300'>And</span> <span
  m='2635900'>there</span> <span m='2636290'>are</span> <span
  m='2637010'>some</span> <span m='2637220'>issues</span> <span
  m='2637640'>with</span> <span m='2637820'>regard</span> <span
  m='2638750'>to</span> <span m='2639080'>how</span> <span
  m='2639650'>the</span> <span m='2639770'>poles</span> <span
  m='2640130'>are</span> <span m='2640250'>implemented.</span> <span
  m='2641330'>And</span> <span m='2641840'>let</span> <span
  m='2642050'>me</span> <span m='2642500'>close</span> <span
  m='2642830'>the</span> <span m='2642920'>lecture</span> <span
  m='2643340'>by</span> <span m='2643580'>just</span> <span
  m='2643940'>giving</span> <span m='2644300'>you</span> <span
  m='2645470'>some</span> <span m='2645710'>indication</span> <span
  m='2646670'>of</span> <span m='2647300'>what</span> <span
  m='2647660'>some</span> <span m='2647960'>of</span> <span
  m='2648080'>the--</span> <span m='2648380'>in</span> <span
  m='2648500'>particular</span> <span m='2648950'>what</span> <span
  m='2649100'>two</span> <span m='2649310'>of</span> <span
  m='2649370'>the</span> <span m='2649490'>possibilities</span> <span
  m='2650300'>might</span> <span m='2650570'>be.</span> </p><p><span
  m='2657040'>Based</span> <span m='2657520'>on</span> <span
  m='2657730'>the</span> <span m='2658150'>discussion</span> <span
  m='2659110'>that</span> <span m='2659650'>we've</span> <span
  m='2659830'>just</span> <span m='2660070'>gone</span> <span
  m='2660370'>through,</span> <span m='2662380'>the</span> <span
  m='2662530'>indication</span> <span m='2663190'>is</span> <span
  m='2663670'>that</span> <span m='2664030'>we</span> <span
  m='2664210'>would</span> <span m='2664390'>want</span> <span
  m='2664570'>to</span> <span m='2664660'>implement,</span> <span
  m='2666520'>or</span> <span m='2666920'>it</span> <span
  m='2667030'>might</span> <span m='2667240'>be</span> <span
  m='2667390'>it</span> <span m='2667510'>advantageous</span> <span
  m='2668350'>from</span> <span m='2668590'>the</span> <span
  m='2668680'>point</span> <span m='2668920'>of</span> <span
  m='2668980'>view</span> <span m='2669130'>of</span> <span
  m='2669190'>parameter</span> <span m='2669670'>quantization,</span> <span
  m='2671230'>to</span> <span m='2671680'>implement</span> <span
  m='2673090'>a</span> <span m='2673150'>system</span> <span
  m='2673990'>as</span> <span m='2674170'>a</span> <span
  m='2674230'>cascade</span> <span m='2675010'>or</span> <span
  m='2675160'>parallel</span> <span m='2675610'>combination</span> <span
  m='2676750'>of</span> <span m='2677410'>first</span> <span
  m='2677770'>or</span> <span m='2677860'>second</span> <span
  m='2678220'>order</span> <span m='2678460'>sections.</span> <span
  m='2678940'>And</span> <span m='2679030'>let's</span> <span
  m='2679240'>make</span> <span m='2679450'>them</span> <span
  m='2679540'>second</span> <span m='2679900'>order</span> <span
  m='2680170'>sections.</span> </p><p><span m='2681760'>Let's</span> <span
  m='2682240'>look</span> <span m='2682540'>once</span> <span
  m='2682810'>again</span> <span m='2683470'>at</span> <span
  m='2684070'>the</span> <span m='2684400'>implementation</span> <span
  m='2685540'>of</span> <span m='2685960'>a</span> <span
  m='2686260'>simple</span> <span m='2687070'>second</span> <span
  m='2687460'>order</span> <span m='2687700'>pole</span> <span
  m='2688060'>pair.</span> <span m='2689090'>I've</span> <span
  m='2689500'>neglected</span> <span m='2690130'>the</span> <span
  m='2690250'>implementation</span> <span m='2690970'>of</span> <span
  m='2691090'>the</span> <span m='2691180'>zeros.</span> <span
  m='2692140'>But</span> <span m='2692770'>clearly</span> <span
  m='2693190'>the</span> <span m='2693310'>point</span> <span
  m='2693640'>that</span> <span m='2693760'>I'm</span> <span
  m='2693910'>about</span> <span m='2694210'>to</span> <span
  m='2694330'>make</span> <span m='2694630'>extends</span> <span
  m='2695140'>also</span> <span m='2696040'>for</span> <span
  m='2696160'>the</span> <span m='2696280'>implementation</span> <span
  m='2697270'>of</span> <span m='2697660'>two</span> <span
  m='2697840'>poles</span> <span m='2698260'>and</span> <span
  m='2698350'>two</span> <span m='2698540'>zeros.</span> </p><p><span
  m='2699970'>Here,</span> <span m='2700450'>I</span> <span
  m='2700630'>have</span> <span m='2701050'>implemented</span> <span
  m='2702100'>in</span> <span m='2702790'>what</span> <span
  m='2703060'>we</span> <span m='2703270'>had</span> <span
  m='2703390'>referred</span> <span m='2703780'>to</span> <span
  m='2703990'>as</span> <span m='2704300'>direct</span> <span
  m='2704530'>form,</span> <span m='2705730'>a</span> <span
  m='2706000'>second</span> <span m='2706420'>order</span> <span
  m='2706660'>section</span> <span m='2707470'>which</span> <span
  m='2707680'>we</span> <span m='2707800'>might</span> <span
  m='2708040'>use</span> <span m='2708520'>in</span> <span m='2709000'>a</span>
  <span m='2709150'>cascade</span> <span m='2709780'>form</span> <span
  m='2710230'>or</span> <span m='2710380'>parallel</span> <span
  m='2710860'>form</span> <span m='2711220'>realization,</span> <span
  m='2713140'>which</span> <span m='2713350'>implements</span> <span
  m='2714250'>the</span> <span m='2715210'>complex</span> <span
  m='2715810'>pole</span> <span m='2716140'>pair</span> <span
  m='2716800'>at</span> <span m='2717610'>radius</span> <span
  m='2718120'>r,</span> <span m='2718720'>an</span> <span
  m='2718900'>angle</span> <span m='2719350'>plus,</span> <span
  m='2720220'>and</span> <span m='2720340'>minus</span> <span
  m='2720780'>theta.</span> <span m='2722790'>In</span> <span
  m='2723140'>the</span> <span m='2723440'>actual</span> <span
  m='2723950'>implementation</span> <span m='2725030'>of</span> <span
  m='2725420'>a</span> <span m='2725540'>cascade</span> <span
  m='2726140'>or</span> <span m='2726230'>parallel</span> <span
  m='2726680'>form</span> <span m='2726980'>structure</span> <span
  m='2727760'>using</span> <span m='2728120'>a</span> <span
  m='2728180'>second</span> <span m='2728540'>order</span> <span
  m='2728780'>section</span> <span m='2729440'>of</span> <span
  m='2729590'>this</span> <span m='2729830'>form,</span> <span
  m='2730730'>it</span> <span m='2731130'>is</span> <span
  m='2731510'>these</span> <span m='2731780'>coefficients</span> <span
  m='2733220'>that</span> <span m='2733550'>are</span> <span
  m='2733730'>quantized</span> <span m='2734900'>to</span> <span
  m='2734990'>fit</span> <span m='2735290'>within</span> <span
  m='2735800'>a</span> <span m='2735860'>finite</span> <span
  m='2736310'>register</span> <span m='2736820'>length.</span> </p><p><span
  m='2739140'>We</span> <span m='2739290'>see</span> <span
  m='2739500'>then</span> <span m='2739980'>that</span> <span
  m='2740130'>the</span> <span m='2740250'>quantization</span> <span
  m='2741060'>of</span> <span m='2741120'>the</span> <span
  m='2741210'>coefficients</span> <span m='2742320'>for</span> <span
  m='2742500'>this</span> <span m='2742830'>particular</span> <span
  m='2743370'>network</span> <span m='2743850'>form</span> <span
  m='2745080'>corresponds</span> <span m='2745890'>to</span> <span
  m='2746010'>quantizing</span> <span m='2746910'>the</span> <span
  m='2747000'>parameter</span> <span m='2747280'>r</span> <span
  m='2747560'>squared</span> <span m='2748800'>and</span> <span
  m='2748950'>quantizing</span> <span m='2749820'>the</span> <span
  m='2749910'>parameter</span> <span m='2750870'>2r</span> <span
  m='2751380'>cosine</span> <span m='2751990'>theta.</span> <span
  m='2753850'>What</span> <span m='2753970'>this</span> <span
  m='2754180'>implies</span> <span m='2755020'>in</span> <span
  m='2755140'>the</span> <span m='2755230'>z-plane</span> <span
  m='2756610'>is</span> <span m='2756880'>that</span> <span
  m='2758470'>for,</span> <span m='2759770'>let's</span> <span
  m='2759910'>say,</span> <span m='2760640'>a</span> <span
  m='2760740'>choice</span> <span m='2761200'>of</span> <span
  m='2761380'>register</span> <span m='2761890'>length</span> <span
  m='2762310'>for</span> <span m='2762460'>this</span> <span
  m='2762610'>particular</span> <span m='2763180'>case</span> <span
  m='2763720'>equal</span> <span m='2764050'>to</span> <span
  m='2764170'>3,</span> <span m='2765220'>for</span> <span
  m='2765400'>3-bit</span> <span m='2765880'>register</span> <span
  m='2766390'>length,</span> <span m='2767960'>the</span> <span
  m='2769620'>pole</span> <span m='2769920'>locations</span> <span
  m='2770910'>which</span> <span m='2771090'>can</span> <span
  m='2771270'>be</span> <span m='2771420'>implemented</span> <span
  m='2771990'>with</span> <span m='2772170'>that</span> <span
  m='2772380'>system</span> <span m='2774140'>are</span> <span
  m='2774410'>restricted</span> <span m='2775700'>to</span> <span
  m='2775820'>fall</span> <span m='2776330'>at</span> <span
  m='2776480'>the</span> <span m='2776630'>intersection</span> <span
  m='2777440'>of</span> <span m='2777620'>the</span> <span
  m='2777710'>grid</span> <span m='2777980'>points</span> <span
  m='2778700'>that</span> <span m='2778820'>I've</span> <span
  m='2779000'>indicated</span> <span m='2779570'>here</span> <span
  m='2780950'>due</span> <span m='2781130'>to</span> <span
  m='2781220'>the</span> <span m='2781340'>fact</span> <span
  m='2782000'>that</span> <span m='2782150'>quantization</span> <span
  m='2783260'>of</span> <span m='2783470'>the</span> <span
  m='2783560'>parameter</span> <span m='2784160'>r</span> <span
  m='2784460'>cosine</span> <span m='2785070'>theta</span> <span
  m='2786050'>implies</span> <span m='2787400'>that</span> <span
  m='2787760'>we</span> <span m='2787910'>must</span> <span
  m='2788260'>lie</span> <span m='2788960'>along</span> <span
  m='2789890'>lines</span> <span m='2790820'>equally</span> <span
  m='2791270'>spaced</span> <span m='2791900'>along</span> <span
  m='2792320'>the</span> <span m='2792410'>horizontal</span> <span
  m='2793100'>axis.</span> </p><p><span m='2793980'>Recall</span> <span
  m='2794300'>that</span> <span m='2794420'>r</span> <span
  m='2794570'>cosine</span> <span m='2795150'>theta</span> <span
  m='2796010'>is</span> <span m='2796130'>just</span> <span
  m='2796370'>the</span> <span m='2796490'>real</span> <span
  m='2796790'>part</span> <span m='2797180'>of</span> <span
  m='2797300'>the</span> <span m='2797420'>pole</span> <span
  m='2797630'>location.</span> <span m='2799190'>And</span> <span
  m='2799310'>quantization</span> <span m='2800030'>of</span> <span
  m='2800120'>the</span> <span m='2800210'>parameter</span> <span
  m='2800870'>r</span> <span m='2801100'>squared</span> <span
  m='2802190'>corresponds</span> <span m='2803660'>to</span> <span
  m='2804020'>the</span> <span m='2804140'>requirement</span> <span
  m='2805310'>that</span> <span m='2805790'>the</span> <span
  m='2805910'>poles</span> <span m='2806300'>must</span> <span
  m='2806560'>lie</span> <span m='2807140'>along</span> <span
  m='2807650'>circles,</span> <span m='2808880'>which</span> <span
  m='2809180'>are</span> <span m='2809300'>spaced</span> <span
  m='2810050'>according</span> <span m='2810620'>to</span> <span
  m='2810740'>the</span> <span m='2810830'>quantization</span> <span
  m='2811610'>of</span> <span m='2811730'>r</span> <span
  m='2811880'>square.</span> <span m='2813260'>So</span> <span
  m='2814250'>the</span> <span m='2814340'>realizable</span> <span
  m='2815120'>pole</span> <span m='2815450'>positions</span> <span
  m='2816320'>with</span> <span m='2816500'>a</span> <span
  m='2816560'>second</span> <span m='2816890'>order</span> <span
  m='2817130'>section</span> <span m='2817760'>in</span> <span
  m='2817910'>the</span> <span m='2818030'>form</span> <span
  m='2818990'>that</span> <span m='2819350'>I</span> <span
  m='2819990'>indicated</span> <span m='2820580'>on</span> <span
  m='2820670'>the</span> <span m='2820760'>previous</span> <span
  m='2821180'>slide</span> <span m='2822890'>are</span> <span
  m='2823520'>given</span> <span m='2824120'>by</span> <span
  m='2824390'>the</span> <span m='2824480'>constellation,</span> <span
  m='2825650'>or</span> <span m='2825800'>by</span> <span m='2825950'>the</span>
  <span m='2826100'>intersection</span> <span m='2826880'>of</span> <span
  m='2827030'>the</span> <span m='2827120'>grid</span> <span
  m='2827360'>points,</span> <span m='2828050'>that</span> <span
  m='2828170'>we</span> <span m='2828350'>have</span> <span
  m='2828560'>shown</span> <span m='2828920'>here.</span> </p><p><span
  m='2831150'>Another</span> <span m='2831840'>possible</span> <span
  m='2833220'>implementation</span> <span m='2834330'>for</span> <span
  m='2835020'>a</span> <span m='2835290'>second</span> <span
  m='2835710'>order</span> <span m='2836400'>pole</span> <span
  m='2836730'>pair</span> <span m='2837810'>is</span> <span
  m='2838530'>the</span> <span m='2838890'>so-called</span> <span
  m='2839550'>coupled</span> <span m='2839970'>form</span> <span
  m='2840480'>implementation.</span> <span m='2842040'>I</span> <span
  m='2842140'>won't</span> <span m='2842460'>justify</span> <span
  m='2844470'>here</span> <span m='2844860'>by</span> <span
  m='2845070'>inspection</span> <span m='2845760'>that</span> <span
  m='2846360'>the</span> <span m='2846450'>transfer</span> <span
  m='2846960'>function</span> <span m='2848100'>is</span> <span
  m='2848400'>given</span> <span m='2848910'>by</span> <span
  m='2849240'>the</span> <span m='2849330'>same</span> <span
  m='2849630'>expression</span> <span m='2850360'>as</span> <span
  m='2850560'>for</span> <span m='2850710'>the</span> <span
  m='2850830'>direct</span> <span m='2851190'>form</span> <span
  m='2851490'>structure</span> <span m='2852330'>that</span> <span
  m='2852480'>I</span> <span m='2852570'>showed</span> <span
  m='2852870'>previously,</span> <span m='2854190'>but,</span> <span
  m='2854460'>in</span> <span m='2854610'>fact,</span> <span
  m='2855040'>it</span> <span m='2855140'>is.</span> <span
  m='2855970'>And</span> <span m='2856020'>the</span> <span
  m='2856110'>poles</span> <span m='2856500'>in</span> <span
  m='2856620'>this</span> <span m='2856830'>case</span> <span
  m='2857580'>fall</span> <span m='2858120'>at,</span> <span
  m='2858970'>again,</span> <span m='2859420'>are</span> <span
  m='2859590'>equal</span> <span m='2860280'>to</span> <span
  m='2860500'>e</span> <span m='2860850'>to</span> <span m='2860940'>the</span>
  <span m='2861030'>j</span> <span m='2861300'>theta</span> <span
  m='2861810'>and</span> <span m='2861990'>r</span> <span m='2862290'>e</span>
  <span m='2862500'>to</span> <span m='2862560'>the</span> <span
  m='2862650'>minus</span> <span m='2862830'>j</span> <span
  m='2863010'>theta.</span> <span m='2864516'>But</span> <span
  m='2864880'>now,</span> <span m='2865710'>the</span> <span
  m='2865830'>coefficients</span> <span m='2866580'>we</span> <span
  m='2866730'>see</span> <span m='2867360'>are</span> <span m='2867855'>r</span>
  <span m='2868350'>cosine</span> <span m='2869000'>theta</span> <span
  m='2869880'>and</span> <span m='2870030'>r</span> <span
  m='2870270'>sine</span> <span m='2870720'>theta.</span> </p><p><span
  m='2871850'>Quantization</span> <span m='2872550'>of</span> <span
  m='2872640'>r</span> <span m='2872820'>cosine</span> <span
  m='2873390'>theta</span> <span m='2873900'>implies,</span> <span
  m='2875190'>as</span> <span m='2875370'>it</span> <span m='2875460'>did</span>
  <span m='2875640'>previously,</span> <span m='2877340'>that</span> <span
  m='2877500'>the</span> <span m='2877620'>poles</span> <span
  m='2878040'>must</span> <span m='2878310'>lie</span> <span
  m='2878580'>along</span> <span m='2879150'>lines</span> <span
  m='2879810'>equally</span> <span m='2880200'>spaced</span> <span
  m='2880590'>along</span> <span m='2880860'>the</span> <span
  m='2880950'>horizontal</span> <span m='2881580'>axis.</span> <span
  m='2882390'>Quantization</span> <span m='2883260'>of</span> <span
  m='2883380'>r</span> <span m='2883560'>sine</span> <span
  m='2883950'>theta</span> <span m='2884400'>implies</span> <span
  m='2884910'>that</span> <span m='2885000'>the</span> <span
  m='2885090'>poles</span> <span m='2885450'>must</span> <span
  m='2885690'>line</span> <span m='2885990'>along</span> <span
  m='2886680'>lines</span> <span m='2887490'>equally</span> <span
  m='2887880'>spaced</span> <span m='2888390'>along</span> <span
  m='2888690'>the</span> <span m='2888780'>vertical,</span> <span
  m='2889380'>or</span> <span m='2889530'>imaginary,</span> <span
  m='2890190'>axes.</span> <span m='2891270'>And</span> <span
  m='2891420'>so</span> <span m='2892020'>for</span> <span
  m='2892230'>that</span> <span m='2892740'>case,</span> <span
  m='2895050'>the</span> <span m='2895830'>choice</span> <span
  m='2896220'>of</span> <span m='2896340'>realizable</span> <span
  m='2897060'>pole</span> <span m='2897320'>positions</span> <span
  m='2898080'>are</span> <span m='2898230'>governed</span> <span
  m='2898680'>by</span> <span m='2899550'>the</span> <span
  m='2899670'>constellation</span> <span m='2900720'>of</span> <span
  m='2900840'>grid</span> <span m='2901110'>points</span> <span
  m='2901920'>that</span> <span m='2902040'>I've</span> <span
  m='2902190'>indicated</span> <span m='2902790'>here.</span> </p><p><span
  m='2903840'>So</span> <span m='2904740'>this</span> <span
  m='2905040'>is</span> <span m='2905220'>just</span> <span
  m='2905460'>simply,</span> <span m='2906810'>this</span> <span
  m='2907140'>last</span> <span m='2908400'>issue,</span> <span
  m='2909510'>is</span> <span m='2909660'>just</span> <span
  m='2909870'>simply</span> <span m='2910470'>an</span> <span
  m='2910620'>introduction</span> <span m='2911520'>to</span> <span
  m='2911640'>the</span> <span m='2911760'>fact</span> <span
  m='2912870'>that</span> <span m='2913290'>even</span> <span
  m='2913740'>given</span> <span m='2914580'>the</span> <span
  m='2914700'>notion</span> <span m='2915390'>that</span> <span
  m='2915570'>the</span> <span m='2915660'>cascade</span> <span
  m='2916290'>form</span> <span m='2916620'>structure</span> <span
  m='2917160'>is</span> <span m='2917310'>better</span> <span
  m='2917580'>than</span> <span m='2917730'>the</span> <span
  m='2917820'>direct</span> <span m='2918150'>form</span> <span
  m='2918480'>structure,</span> <span m='2919620'>there</span> <span
  m='2919920'>are</span> <span m='2920190'>additional</span> <span
  m='2920700'>issues</span> <span m='2921300'>involved</span> <span
  m='2922140'>in</span> <span m='2922440'>specifically</span> <span
  m='2923610'>how</span> <span m='2923790'>to</span> <span
  m='2923910'>implement</span> <span m='2924660'>a</span> <span
  m='2924720'>pole</span> <span m='2925080'>pair,</span> <span
  m='2925890'>or</span> <span m='2926520'>a</span> <span m='2926640'>pole</span>
  <span m='2926955'>zero</span> <span m='2927270'>combination</span> <span
  m='2928590'>in</span> <span m='2928710'>order</span> <span
  m='2929010'>to</span> <span m='2929190'>account</span> <span
  m='2929610'>for</span> <span m='2929790'>parameter</span> <span
  m='2930270'>quantization</span> <span m='2930960'>effects.</span> </p><p><span
  m='2932990'>There</span> <span m='2933380'>are</span> <span
  m='2933650'>lots</span> <span m='2934070'>of</span> <span
  m='2934370'>remaining</span> <span m='2934880'>issues,</span> <span
  m='2935510'>as</span> <span m='2935720'>you'll</span> <span
  m='2935840'>see</span> <span m='2936050'>in</span> <span
  m='2936170'>the</span> <span m='2936260'>text,</span> <span
  m='2937160'>related</span> <span m='2937640'>to</span> <span
  m='2938480'>both</span> <span m='2938750'>the</span> <span
  m='2938870'>issues</span> <span m='2939260'>of</span> <span
  m='2939350'>digital</span> <span m='2939710'>filter</span> <span
  m='2940100'>structures</span> <span m='2941300'>and</span> <span
  m='2941630'>the</span> <span m='2941750'>effects</span> <span
  m='2942320'>of</span> <span m='2942830'>parameter</span> <span
  m='2943490'>and</span> <span m='2943610'>arithmetic</span> <span
  m='2945510'>finite</span> <span m='2945900'>register</span> <span
  m='2946380'>length</span> <span m='2946680'>effects,</span> <span
  m='2947580'>which</span> <span m='2947790'>we</span> <span
  m='2947940'>won't</span> <span m='2948150'>be</span> <span
  m='2948270'>going</span> <span m='2948570'>into</span> <span
  m='2949110'>in</span> <span m='2949260'>this</span> <span
  m='2949410'>set</span> <span m='2949650'>of</span> <span
  m='2949770'>lectures.</span> <span m='2950740'>But</span> <span
  m='2951030'>you</span> <span m='2951180'>should</span> <span
  m='2951390'>at</span> <span m='2951480'>least</span> <span
  m='2951720'>be</span> <span m='2951840'>aware</span> <span
  m='2952320'>be</span> <span m='2952500'>aware</span> <span
  m='2952950'>of</span> <span m='2953100'>their</span> <span
  m='2953310'>existence.</span> <span m='2954720'>In</span> <span
  m='2955350'>the</span> <span m='2955440'>next</span> <span
  m='2956010'>several</span> <span m='2956460'>lectures,</span> <span
  m='2957550'>we'll</span> <span m='2957840'>begin</span> <span
  m='2958470'>on</span> <span m='2958800'>a</span> <span m='2958890'>new</span>
  <span m='2959040'>topic,</span> <span m='2959970'>namely</span> <span
  m='2960480'>a</span> <span m='2960570'>discussion</span> <span
  m='2961350'>of</span> <span m='2961770'>some</span> <span
  m='2962040'>of</span> <span m='2962160'>the</span> <span
  m='2962280'>issues</span> <span m='2962820'>involved</span> <span
  m='2963900'>in</span> <span m='2964410'>the</span> <span
  m='2964530'>design</span> <span m='2965610'>of</span> <span
  m='2966000'>digital</span> <span m='2966360'>filters.</span> <span
  m='2967090'>Thank</span> <span m='2967220'>you.</span> </p><p><span
  m='2967820'>[MUSIC PLAYING]</span> </p><p></p>
embedded_media:
  - uid: f3394c024819bc75cd63a4b298b488d8
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: MITRES_6_008S11_lec13.pdf
    title: MITRES_6_008S11_lec13.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-13-network-structures-for-finite-impulse-response-fir-systems-and-parameter-quantization-effects-in-digital-filter-structures/MITRES_6_008S11_lec13.pdf
  - uid: ef60876b56145a775fda86c477289101
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: AsSsGjaBbas
  - uid: 6d23a451eb398687543b3043fec78644
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-13-network-structures/id481803782?i=108362001
  - uid: cbd6330abad12e6a8c528532d0e759bc
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec13_300k.mp4'
  - uid: 08555241c0c72463ee2f8ad188e8a9a7
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/AsSsGjaBbas/default.jpg'
  - uid: d624436cd817aad1436188c498f3ff71
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: AsSsGjaBbas
  - uid: 13e62102c7b2f550b6f7839a706c3280
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: AsSsGjaBbas.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-13-network-structures-for-finite-impulse-response-fir-systems-and-parameter-quantization-effects-in-digital-filter-structures/AsSsGjaBbas.srt
  - uid: 4260578ccde71f509549a31a9d2e3e97
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: AsSsGjaBbas.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-13-network-structures-for-finite-impulse-response-fir-systems-and-parameter-quantization-effects-in-digital-filter-structures/AsSsGjaBbas.pdf
  - uid: 997f0953735357c1b8289ad227fe1b6b
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: c257f4858d6030129219f0feb2cbcbb3
    parent_uid: f571f16c74146803a56d0a7730131c58
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
