---
order_index: null
title: 'Lecture 15: Design of IIR Digital Filters, Part 2'
template_type: Tabbed
uid: ffedfbd0f8c1194b93e04316f92eb16f
parent_uid: d9271fc3fc7001a84584e76665b89755
technical_location: >-
  https://ocw.mit.edu/resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-15-design-of-iir-digital-filters-part-2
short_url: lecture-15-design-of-iir-digital-filters-part-2
inline_embed_id: '47412899lecture15:designofiirdigitalfilters,part274327240'
about_this_resource_text: >-
  <p><strong>Topics covered:</strong> Digital filter design using the bilinear
  transformation, frequency warping introduced by the bilinear transformation,
  algorithmic design procedures for IIR filters.</p>
  <p><strong>Instructor:</strong> Prof. Alan V. Oppenheim</p>
related_resources_text: >-
  <p>Design of IIR Digital Filters, Part 2 (<a
  href="./resolveuid/6b38f1882661a41b7699b95163d92933">PDF</a>)</p>
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
  m='22510'>[MUSIC PLAYING]</span> </p><p></p><p><span m='48920'>ALAN
  OPPENHEIM:</span> <span m='49070'>Last</span> <span m='49220'>time,</span>
  <span m='49490'>we</span> <span m='49610'>introduced</span> <span
  m='50150'>the</span> <span m='50420'>topic</span> <span m='50900'>of</span>
  <span m='50990'>digital</span> <span m='51320'>filter</span> <span
  m='51710'>design,</span> <span m='52430'>and</span> <span m='52790'>we</span>
  <span m='53000'>discussed</span> <span m='54080'>two</span> <span
  m='54290'>design</span> <span m='54710'>techniques</span> <span
  m='55340'>which</span> <span m='55790'>permitted</span> <span
  m='56240'>us</span> <span m='56960'>to</span> <span m='57170'>obtain</span>
  <span m='57650'>digital</span> <span m='58010'>filter</span> <span
  m='58400'>designs</span> <span m='59030'>from</span> <span
  m='59210'>analog</span> <span m='59900'>or</span> <span
  m='60110'>continuous</span> <span m='60680'>time</span> <span
  m='60980'>designs.</span> <span m='62360'>In</span> <span
  m='62450'>particular,</span> <span m='63260'>the</span> <span
  m='63620'>first</span> <span m='64340'>technique</span> <span
  m='64910'>that</span> <span m='65300'>we</span> <span
  m='65450'>discussed</span> <span m='66770'>was</span> <span
  m='67280'>basically</span> <span m='68000'>mapping</span> <span
  m='68870'>differentials</span> <span m='69860'>in</span> <span
  m='70280'>a</span> <span m='70400'>linear</span> <span
  m='70730'>constant</span> <span m='70980'>coefficient</span> <span
  m='71750'>differential</span> <span m='72380'>equation</span> <span
  m='73375'>to</span> <span m='73680'>differences</span> <span
  m='74720'>in</span> <span m='75050'>a</span> <span m='75290'>linear</span>
  <span m='75590'>constant</span> <span m='76010'>coefficient</span> <span
  m='76610'>difference</span> <span m='77000'>equation.</span> <span
  m='78620'>We</span> <span m='78770'>found</span> <span m='79140'>that</span>
  <span m='79250'>that</span> <span m='79460'>corresponded</span> <span
  m='80720'>basically</span> <span m='81320'>to</span> <span m='81500'>a</span>
  <span m='81560'>mapping</span> <span m='82010'>from</span> <span
  m='82160'>the</span> <span m='82310'>s</span> <span m='82520'>plane</span>
  <span m='83270'>to</span> <span m='83390'>the</span> <span m='83480'>z</span>
  <span m='83690'>plane.</span> <span m='85070'>But</span> <span
  m='85370'>we</span> <span m='85520'>saw</span> <span m='85880'>also</span>
  <span m='86420'>that</span> <span m='86840'>it</span> <span
  m='87710'>was</span> <span m='87890'>not</span> <span m='88100'>a</span> <span
  m='88160'>good</span> <span m='88370'>technique</span> <span
  m='90110'>for</span> <span m='90290'>two</span> <span m='90800'>basic</span>
  <span m='91280'>reasons.</span> <span m='92190'>One</span> <span
  m='92540'>is</span> <span m='92750'>that</span> <span m='93140'>it</span>
  <span m='93320'>didn't</span> <span m='93950'>correspond</span> <span
  m='94700'>to</span> <span m='94850'>mapping</span> <span m='95900'>the</span>
  <span m='96140'>frequency</span> <span m='96740'>characteristic</span> <span
  m='97940'>from</span> <span m='98120'>the</span> <span m='98210'>j</span>
  <span m='98510'>omega</span> <span m='98820'>axis</span> <span
  m='99830'>to</span> <span m='99920'>the</span> <span m='100040'>unit</span>
  <span m='100340'>circle.</span> <span m='101960'>And</span> <span
  m='102080'>second</span> <span m='102470'>of</span> <span
  m='102590'>all,</span> <span m='102980'>and</span> <span
  m='103220'>perhaps</span> <span m='103610'>even</span> <span
  m='103850'>more</span> <span m='104060'>serious,</span> <span
  m='105230'>it</span> <span m='105350'>didn't</span> <span
  m='105650'>result</span> <span m='106310'>in</span> <span m='106430'>a</span>
  <span m='106490'>mapping</span> <span m='107150'>of</span> <span
  m='107660'>stable</span> <span m='108230'>analog</span> <span
  m='108740'>filters</span> <span m='109370'>to</span> <span
  m='109490'>stable</span> <span m='109880'>digital</span> <span
  m='110270'>filters.</span> </p><p><span m='112700'>The</span> <span
  m='112790'>second</span> <span m='113180'>technique</span> <span
  m='113810'>that</span> <span m='114200'>we</span> <span
  m='114380'>discussed</span> <span m='115040'>was</span> <span
  m='115400'>the</span> <span m='115520'>technique</span> <span
  m='116120'>of</span> <span m='116450'>impulse and</span> <span
  m='116900'>invariance,</span> <span m='117830'>where</span> <span
  m='118040'>basically,</span> <span m='119180'>the</span> <span
  m='119810'>discrete</span> <span m='120260'>time</span> <span
  m='120590'>filter</span> <span m='121160'>is</span> <span
  m='121340'>designed</span> <span m='122480'>by</span> <span
  m='123800'>sampling</span> <span m='124580'>periodically</span> <span
  m='125810'>the</span> <span m='126080'>impulse</span> <span
  m='126530'>response</span> <span m='127190'>of</span> <span
  m='127370'>the</span> <span m='127460'>continuous</span> <span
  m='128060'>time</span> <span m='128360'>filter.</span> <span
  m='129650'>And</span> <span m='130460'>we</span> <span m='130580'>saw</span>
  <span m='130970'>that</span> <span m='131150'>what</span> <span
  m='131360'>this</span> <span m='131540'>corresponded</span> <span
  m='132320'>to</span> <span m='133280'>was</span> <span
  m='133490'>basically</span> <span m='134420'>a</span> <span
  m='134480'>mapping</span> <span m='135350'>of</span> <span
  m='135890'>the</span> <span m='135980'>system</span> <span
  m='136430'>function</span> <span m='137120'>for</span> <span
  m='137510'>the</span> <span m='137630'>continuous</span> <span
  m='138230'>time</span> <span m='138530'>filter</span> <span
  m='139820'>to</span> <span m='140210'>a</span> <span m='140270'>system</span>
  <span m='140690'>function</span> <span m='141290'>for</span> <span
  m='141440'>the</span> <span m='141530'>digital</span> <span
  m='141950'>filter,</span> <span m='143120'>which</span> <span
  m='143690'>preserved</span> <span m='144560'>the</span> <span
  m='144680'>residues</span> <span m='146330'>and</span> <span
  m='146900'>mapped</span> <span m='147230'>the</span> <span
  m='147350'>poles</span> <span m='148010'>of</span> <span m='148340'>the</span>
  <span m='148580'>continuous</span> <span m='149210'>time</span> <span
  m='149510'>filter</span> <span m='151340'>at</span> <span
  m='151730'>poles</span> <span m='152060'>at</span> <span m='152150'>s
  sub</span> <span m='152615'>k</span> <span m='153320'>to</span> <span
  m='153410'>poles</span> <span m='153950'>of</span> <span m='154100'>the</span>
  <span m='154220'>digital</span> <span m='154580'>filter</span> <span
  m='155150'>at</span> <span m='155530'>e</span> <span m='155810'>to</span>
  <span m='155960'>the</span> <span m='156110'>s</span> <span
  m='156350'>sub</span> <span m='156470'>k</span> <span
  m='156950'>capital</span> <span m='157430'>T.</span> </p><p><span
  m='158570'>Well,</span> <span m='159320'>let</span> <span m='159500'>me</span>
  <span m='159800'>remind</span> <span m='160310'>you</span> <span
  m='160730'>again</span> <span m='161330'>of</span> <span m='162200'>the</span>
  <span m='162410'>advantages</span> <span m='163040'>and</span> <span
  m='163160'>disadvantages</span> <span m='164270'>of</span> <span
  m='164390'>this</span> <span m='164570'>technique</span> <span
  m='165440'>by</span> <span m='165710'>illustrating</span> <span
  m='166370'>it</span> <span m='166550'>with</span> <span m='166760'>a</span>
  <span m='166820'>simple</span> <span m='167180'>example.</span> <span
  m='170420'>Let's</span> <span m='170890'>take</span> <span
  m='171160'>the</span> <span m='171250'>case</span> <span m='171820'>of</span>
  <span m='172420'>a</span> <span m='172480'>simple,</span> <span
  m='173260'>second</span> <span m='173710'>order</span> <span
  m='174340'>analog</span> <span m='174970'>filter,</span> <span
  m='175690'>let's</span> <span m='175930'>say</span> <span
  m='176140'>with</span> <span m='176350'>one</span> <span m='176590'>0</span>
  <span m='177220'>and</span> <span m='177340'>two</span> <span
  m='177580'>poles,</span> <span m='178720'>so</span> <span
  m='178930'>that</span> <span m='179350'>the</span> <span
  m='179530'>analog</span> <span m='180010'>system</span> <span
  m='180400'>function</span> <span m='181060'>is</span> <span
  m='181240'>given</span> <span m='181540'>by</span> <span m='181780'>S</span>
  <span m='181960'>plus</span> <span m='182320'>a</span> <span
  m='182830'>divided</span> <span m='183340'>by</span> <span m='183760'>S</span>
  <span m='184030'>plus</span> <span m='184330'>a</span> <span
  m='184510'>squared</span> <span m='185500'>plus</span> <span
  m='185820'>b</span> <span m='185980'>squared.</span> <span
  m='187900'>For</span> <span m='187990'>the</span> <span
  m='188110'>impulse</span> <span m='188500'>invariant</span> <span
  m='189100'>design</span> <span m='189520'>procedure,</span> <span
  m='190660'>we</span> <span m='190810'>want</span> <span m='191140'>to</span>
  <span m='191530'>expand</span> <span m='192160'>this</span> <span
  m='192790'>into</span> <span m='193090'>a</span> <span
  m='193150'>partial</span> <span m='193570'>fraction</span> <span
  m='194080'>expansion.</span> <span m='195550'>And</span> <span
  m='196270'>in</span> <span m='196450'>that</span> <span
  m='196660'>form,</span> <span m='197410'>this</span> <span
  m='197980'>system</span> <span m='198430'>function</span> <span
  m='198940'>becomes</span> <span m='199660'>a</span> <span
  m='200005'>1/2--</span> <span m='200350'>1/2</span> <span m='200650'>as</span>
  <span m='200770'>the</span> <span m='200860'>residu3--</span> <span
  m='202090'>divided</span> <span m='202600'>by</span> <span m='203080'>S</span>
  <span m='203380'>plus</span> <span m='203710'>a</span> <span
  m='203890'>plus</span> <span m='204250'>jb.</span> <span m='205120'>The</span>
  <span m='205210'>pole</span> <span m='205750'>is</span> <span
  m='206110'>then</span> <span m='206360'>at</span> <span
  m='206500'>minus</span> <span m='206980'>a</span> <span
  m='207460'>minus</span> <span m='207880'>jb,</span> <span
  m='209170'>plus</span> <span m='209710'>a</span> <span
  m='209800'>residue</span> <span m='210340'>of</span> <span
  m='210460'>1/2</span> <span m='211600'>over</span> <span m='212230'>S</span>
  <span m='212680'>plus</span> <span m='213040'>a</span> <span
  m='213250'>minus</span> <span m='213670'>jb,</span> <span m='214410'>in</span>
  <span m='214510'>other</span> <span m='214720'>words,</span> <span
  m='215050'>a</span> <span m='215110'>pole</span> <span m='215560'>at</span>
  <span m='215680'>minus</span> <span m='216160'>a</span> <span
  m='216820'>plus</span> <span m='217330'>jb.</span> </p><p><span
  m='219730'>All</span> <span m='219790'>right.</span> <span
  m='220030'>Well,</span> <span m='220450'>mapping</span> <span
  m='221560'>this</span> <span m='221950'>analog</span> <span
  m='222520'>system</span> <span m='222940'>function</span> <span
  m='223750'>to</span> <span m='223930'>the</span> <span
  m='224050'>digital</span> <span m='224440'>system</span> <span
  m='224860'>function,</span> <span m='226090'>we</span> <span
  m='226210'>maintain</span> <span m='227320'>the</span> <span
  m='227440'>residue</span> <span m='229060'>and</span> <span
  m='229180'>map</span> <span m='229780'>the</span> <span m='229900'>pole</span>
  <span m='230560'>at</span> <span m='230770'>minus</span> <span
  m='231220'>a</span> <span m='231670'>minus</span> <span m='232110'>jb</span>
  <span m='233350'>to</span> <span m='233530'>a</span> <span
  m='233590'>pole</span> <span m='234010'>in</span> <span m='234100'>the</span>
  <span m='234190'>z</span> <span m='234430'>plane</span> <span
  m='234940'>at</span> <span m='235310'>e</span> <span m='235530'>to</span>
  <span m='235600'>the</span> <span m='235720'>minus</span> <span
  m='236170'>a</span> <span m='236350'>capital</span> <span m='236890'>T</span>
  <span m='237330'>e</span> <span m='237510'>to</span> <span
  m='237570'>the</span> <span m='237670'>minus</span> <span m='238060'>jb</span>
  <span m='238520'>capital</span> <span m='238960'>T.</span> <span
  m='240160'>So</span> <span m='240760'>the</span> <span
  m='240880'>resulting</span> <span m='241900'>digital</span> <span
  m='242650'>transfer</span> <span m='243160'>function</span> <span
  m='244240'>has</span> <span m='244540'>these</span> <span
  m='244720'>same</span> <span m='245080'>residues,</span> <span
  m='246880'>and</span> <span m='247060'>it</span> <span m='247150'>has</span>
  <span m='247390'>poles</span> <span m='248470'>which</span> <span
  m='248860'>are</span> <span m='249220'>at</span> <span m='249580'>e</span>
  <span m='249730'>to</span> <span m='249790'>the</span> <span
  m='249880'>minus</span> <span m='250270'>aT</span> <span m='250930'>e to
  the</span> <span m='251140'>minus</span> <span m='251500'>jgT,</span> <span
  m='253330'>and</span> <span m='253810'>e</span> <span m='254130'>to</span>
  <span m='254200'>the</span> <span m='254290'>minus</span> <span
  m='254680'>aT</span> <span m='255715'>e</span> <span m='255970'>to</span>
  <span m='256120'>the</span> <span m='256209'>plus</span> <span
  m='256769'>jbT.</span> <span m='258399'>And</span> <span
  m='258850'>this</span> <span m='259060'>system</span> <span
  m='259450'>function,</span> <span m='260290'>we</span> <span
  m='260470'>can</span> <span m='260649'>now</span> <span
  m='261880'>recombine.</span> <span m='263320'>We</span> <span
  m='263440'>can</span> <span m='263590'>recombine</span> <span
  m='264130'>the</span> <span m='264220'>two</span> <span
  m='264460'>terms.</span> <span m='265510'>And</span> <span
  m='266080'>the</span> <span m='266230'>resulting</span> <span
  m='266800'>digital</span> <span m='267580'>transfer</span> <span
  m='268090'>function</span> <span m='268870'>is</span> <span
  m='269290'>as</span> <span m='269470'>I've</span> <span
  m='269590'>indicated</span> <span m='270160'>here.</span> </p><p><span
  m='271490'>Now,</span> <span m='272470'>this</span> <span
  m='272860'>illustrates</span> <span m='273490'>one</span> <span
  m='273700'>of</span> <span m='273790'>the</span> <span
  m='273910'>important</span> <span m='274390'>points,</span> <span
  m='275180'>which</span> <span m='275380'>is</span> <span m='276160'>the</span>
  <span m='276250'>fact</span> <span m='276850'>that</span> <span
  m='277840'>the</span> <span m='277960'>poles</span> <span
  m='278770'>got</span> <span m='279010'>mapped</span> <span
  m='279610'>according</span> <span m='280150'>to</span> <span
  m='280570'>a</span> <span m='280630'>mapping</span> <span
  m='281420'>which</span> <span m='281620'>is</span> <span m='282310'>of</span>
  <span m='282430'>the</span> <span m='282550'>form</span> <span
  m='282940'>z</span> <span m='283270'>equals</span> <span m='283660'>e</span>
  <span m='283880'>to</span> <span m='284020'>the</span> <span
  m='284200'>s</span> <span m='284950'>capital</span> <span m='285430'>T.</span>
  <span m='286420'>But</span> <span m='286630'>notice</span> <span
  m='287290'>that,</span> <span m='287490'>in</span> <span
  m='287590'>fact,</span> <span m='287970'>the</span> <span m='288080'>0</span>
  <span m='288780'>didn't</span> <span m='289030'>get</span> <span
  m='289240'>mapped</span> <span m='289600'>in</span> <span
  m='289690'>the</span> <span m='289780'>same</span> <span
  m='290110'>way.</span> <span m='290770'>The</span> <span m='290910'>0</span>
  <span m='291460'>at</span> <span m='291610'>minus</span> <span
  m='292060'>a</span> <span m='292860'>got</span> <span
  m='293070'>mapped,</span> <span m='293520'>for</span> <span
  m='293680'>this</span> <span m='293860'>particular</span> <span
  m='294430'>example,</span> <span m='295450'>to a</span> <span
  m='295610'>0</span> <span m='296200'>at</span> <span m='296350'>e</span> <span
  m='296540'>to</span> <span m='296650'>the</span> <span m='296740'>minus</span>
  <span m='297180'>aT</span> <span m='297320'>t</span> <span
  m='298110'>cosine</span> <span m='298660'>bT.</span> <span
  m='300070'>So</span> <span m='300880'>in</span> <span m='300970'>fact,</span>
  <span m='301460'>it's</span> <span m='301570'>not</span> <span
  m='301780'>a</span> <span m='301840'>mapping</span> <span m='302500'>of</span>
  <span m='302680'>S</span> <span m='303190'>to</span> <span
  m='303310'>z,</span> <span m='303820'>although</span> <span
  m='304660'>the</span> <span m='304780'>poles</span> <span m='305320'>of</span>
  <span m='305440'>the</span> <span m='305560'>analog</span> <span
  m='306010'>system</span> <span m='306430'>function</span> <span
  m='307420'>get</span> <span m='307570'>mapped</span> <span
  m='307870'>to</span> <span m='307960'>poles</span> <span m='308560'>of</span>
  <span m='308680'>the</span> <span m='308770'>digital</span> <span
  m='309220'>system</span> <span m='309640'>function</span> <span
  m='310180'>according</span> <span m='310630'>to</span> <span
  m='310780'>the</span> <span m='310870'>mapping</span> <span
  m='311350'>z</span> <span m='311630'>equals</span> <span m='312070'>e
  to</span> <span m='312220'>the</span> <span m='312370'>sT.</span> </p><p><span
  m='313790'>Well,</span> <span m='314260'>what</span> <span
  m='314470'>this</span> <span m='314650'>example</span> <span
  m='315190'>looks</span> <span m='315460'>like</span> <span
  m='316450'>in</span> <span m='317770'>the</span> <span
  m='319330'>frequency</span> <span m='319900'>domain,</span> <span
  m='321640'>I've</span> <span m='321790'>indicated</span> <span
  m='322390'>here.</span> <span m='323500'>Here</span> <span
  m='323830'>is</span> <span m='323980'>the s</span> <span
  m='324310'>plane</span> <span m='324670'>plot</span> <span
  m='325150'>of</span> <span m='325900'>the</span> <span m='325990'>two</span>
  <span m='326230'>poles</span> <span m='326920'>and</span> <span
  m='327040'>the</span> <span m='327130'>0</span> <span m='327760'>from</span>
  <span m='327910'>the</span> <span m='328060'>analog</span> <span
  m='328540'>system</span> <span m='328960'>function.</span> <span
  m='330250'>And</span> <span m='331120'>the</span> <span
  m='331360'>result</span> <span m='332050'>of</span> <span
  m='332680'>the</span> <span m='332800'>mapping</span> <span
  m='334290'>or</span> <span m='334570'>the</span> <span
  m='334750'>result</span> <span m='335320'>of</span> <span
  m='336430'>applying</span> <span m='336880'>the</span> <span
  m='336970'>impulse</span> <span m='337360'>invariant</span> <span
  m='337870'>procedure</span> <span m='340180'>are</span> <span
  m='340660'>the</span> <span m='341410'>poles</span> <span
  m='341770'>and</span> <span m='341890'>0s,</span> <span
  m='342610'>which</span> <span m='342910'>are</span> <span
  m='343060'>indicated</span> <span m='343630'>here</span> <span
  m='343840'>in</span> <span m='343930'>the</span> <span m='344020'>z</span>
  <span m='344230'>plane.</span> </p><p><span m='346830'>Well,</span> <span
  m='347340'>to</span> <span m='347790'>see</span> <span m='348090'>what</span>
  <span m='348240'>happens</span> <span m='348660'>to</span> <span
  m='348780'>the</span> <span m='348870'>frequency</span> <span
  m='349440'>response,</span> <span m='350400'>for</span> <span
  m='350580'>this</span> <span m='350970'>particular</span> <span
  m='351600'>analog</span> <span m='352140'>example,</span> <span
  m='353340'>we</span> <span m='353520'>have</span> <span m='354210'>a</span>
  <span m='354270'>resonance</span> <span m='355110'>at</span> <span
  m='355980'>a</span> <span m='356040'>frequency</span> <span
  m='356970'>corresponding</span> <span m='357900'>to</span> <span
  m='358290'>the</span> <span m='358410'>vertical</span> <span
  m='358830'>position</span> <span m='359550'>of</span> <span
  m='359700'>these</span> <span m='359910'>poles.</span> <span
  m='361020'>And</span> <span m='361200'>that's</span> <span
  m='361680'>the</span> <span m='361800'>resonance</span> <span
  m='362520'>that</span> <span m='362640'>we</span> <span m='362820'>have</span>
  <span m='363150'>here</span> <span m='363630'>in</span> <span
  m='364230'>the</span> <span m='364440'>magnitude</span> <span
  m='365040'>of</span> <span m='365130'>the</span> <span
  m='365280'>analog</span> <span m='365730'>system</span> <span
  m='366150'>function.</span> <span m='367640'>And</span> <span
  m='367800'>one</span> <span m='367980'>of</span> <span m='368100'>the</span>
  <span m='368220'>important</span> <span m='369060'>aspects</span> <span
  m='369990'>of</span> <span m='370860'>the</span> <span
  m='371040'>impulse</span> <span m='371490'>invariant</span> <span
  m='372000'>procedure,</span> <span m='372600'>which</span> <span
  m='372840'>I</span> <span m='372930'>pointed</span> <span
  m='373320'>out</span> <span m='373470'>last</span> <span
  m='373830'>time,</span> <span m='375030'>is</span> <span
  m='375270'>that,</span> <span m='376860'>except</span> <span
  m='377400'>for</span> <span m='377610'>aliasing--</span> <span
  m='378210'>and</span> <span m='378300'>that's</span> <span m='378480'>a</span>
  <span m='378570'>big</span> <span m='378900'>except</span> <span
  m='379380'>for--</span> <span m='379980'>except</span> <span
  m='380430'>for</span> <span m='380640'>aliasing,</span> <span
  m='382080'>the</span> <span m='382320'>frequency</span> <span
  m='382950'>response</span> <span m='384750'>has</span> <span
  m='385380'>the</span> <span m='385500'>same</span> <span
  m='385890'>general</span> <span m='386370'>shape</span> <span
  m='387060'>in</span> <span m='387210'>the</span> <span
  m='387300'>discrete</span> <span m='387780'>domain</span> <span
  m='388470'>as</span> <span m='388680'>it</span> <span m='388770'>does</span>
  <span m='389280'>in</span> <span m='389430'>the</span> <span
  m='389520'>continuous</span> <span m='390150'>domain.</span> </p><p><span
  m='391020'>So</span> <span m='391680'>the</span> <span
  m='392340'>corresponding</span> <span m='393270'>discrete</span> <span
  m='393750'>time</span> <span m='394050'>frequency</span> <span
  m='394590'>response</span> <span m='395400'>is</span> <span
  m='396300'>as</span> <span m='396780'>I've</span> <span
  m='396990'>indicated</span> <span m='397560'>here.</span> <span
  m='398070'>We</span> <span m='398250'>have</span> <span m='398400'>a</span>
  <span m='398460'>resonance</span> <span m='399600'>corresponding</span> <span
  m='400380'>to</span> <span m='400530'>these</span> <span
  m='401160'>pole</span> <span m='401400'>locations.</span> <span
  m='403470'>But</span> <span m='403920'>whereas</span> <span
  m='404730'>this</span> <span m='404970'>frequency</span> <span
  m='405540'>response</span> <span m='406380'>drops</span> <span
  m='406830'>off</span> <span m='407460'>asymptotically</span> <span
  m='408360'>to</span> <span m='408510'>0,</span> <span m='410460'>this</span>
  <span m='410670'>frequency</span> <span m='411180'>response</span> <span
  m='411930'>drops</span> <span m='412320'>off</span> <span m='412560'>to</span>
  <span m='412680'>some</span> <span m='412980'>value,</span> <span
  m='413730'>non-zero</span> <span m='414390'>value,</span> <span
  m='415380'>and</span> <span m='415530'>then</span> <span
  m='415830'>continues</span> <span m='416400'>back</span> <span
  m='416700'>up</span> <span m='416880'>again,</span> <span
  m='417270'>basically</span> <span m='418320'>because</span> <span
  m='419070'>this</span> <span m='419280'>frequency</span> <span
  m='419790'>response</span> <span m='420360'>has</span> <span
  m='420600'>to</span> <span m='420720'>be</span> <span
  m='420870'>periodic.</span> <span m='422100'>But</span> <span
  m='422340'>in</span> <span m='422460'>particular,</span> <span
  m='423660'>the</span> <span m='423780'>value</span> <span
  m='425010'>which</span> <span m='425610'>this</span> <span
  m='425820'>frequency</span> <span m='426330'>response</span> <span
  m='426870'>decays</span> <span m='427470'>to</span> <span m='429090'>is</span>
  <span m='430910'>dictated</span> <span m='431630'>in</span> <span
  m='431840'>part</span> <span m='432470'>by</span> <span m='433220'>the</span>
  <span m='433370'>effect</span> <span m='433790'>of</span> <span
  m='433910'>aliasing.</span> </p><p><span m='435140'>And</span> <span
  m='435650'>you</span> <span m='435830'>can</span> <span m='436010'>see</span>
  <span m='436280'>here</span> <span m='436580'>that</span> <span
  m='436790'>in</span> <span m='436910'>comparing</span> <span
  m='437480'>this</span> <span m='437720'>value</span> <span
  m='438830'>to</span> <span m='438950'>this</span> <span m='439250'>one,</span>
  <span m='440120'>this</span> <span m='440480'>is</span> <span
  m='440690'>higher.</span> <span m='441260'>And</span> <span
  m='441410'>the</span> <span m='441500'>reason</span> <span
  m='441860'>it's</span> <span m='442010'>higher</span> <span
  m='442460'>is</span> <span m='442640'>because</span> <span
  m='443000'>of</span> <span m='443090'>the</span> <span
  m='443240'>effect</span> <span m='443550'>of</span> <span
  m='443690'>aliasing.</span> <span m='445040'>So</span> <span
  m='445890'>there</span> <span m='446070'>is</span> <span m='446210'>the</span>
  <span m='446330'>advantage</span> <span m='446900'>to</span> <span
  m='447080'>impulse</span> <span m='447500'>invariance</span> <span
  m='448610'>that</span> <span m='449360'>the</span> <span
  m='449630'>frequency</span> <span m='450320'>axis</span> <span
  m='451490'>is</span> <span m='452000'>a</span> <span m='452240'>scaled</span>
  <span m='452690'>replica</span> <span m='453260'>of</span> <span
  m='453470'>the</span> <span m='453620'>analog</span> <span
  m='454100'>frequency</span> <span m='454700'>axis.</span> <span
  m='455630'>But</span> <span m='455870'>then</span> <span
  m='456300'>there's</span> <span m='456800'>a</span> <span
  m='457010'>distortion</span> <span m='457610'>that's</span> <span
  m='457760'>introduced,</span> <span m='458750'>which</span> <span
  m='459020'>is</span> <span m='459770'>the</span> <span
  m='459890'>effect</span> <span m='460250'>of</span> <span
  m='460340'>aliasing.</span> </p><p><span m='462460'>There's</span> <span
  m='463000'>another</span> <span m='463630'>technique</span> <span
  m='464470'>which</span> <span m='464770'>is</span> <span m='465280'>a</span>
  <span m='465550'>very</span> <span m='465820'>important</span> <span
  m='466540'>and</span> <span m='466960'>commonly</span> <span
  m='467470'>used</span> <span m='467770'>technique</span> <span
  m='468820'>for</span> <span m='469270'>designing</span> <span
  m='470200'>digital</span> <span m='470590'>filters,</span> <span
  m='471830'>which</span> <span m='472420'>avoids</span> <span
  m='472900'>the</span> <span m='472990'>problem</span> <span
  m='473590'>the</span> <span m='473710'>problem</span> <span
  m='474130'>of</span> <span m='474250'>aliasing,</span> <span
  m='475210'>but</span> <span m='475360'>it</span> <span
  m='475480'>avoids</span> <span m='475900'>that</span> <span
  m='476080'>problem</span> <span m='476530'>at</span> <span m='476620'>a</span>
  <span m='476680'>price.</span> <span m='478480'>That</span> <span
  m='478660'>technique</span> <span m='479320'>is</span> <span
  m='480400'>referred</span> <span m='480790'>to</span> <span
  m='481240'>as</span> <span m='481930'>the</span> <span
  m='482980'>bilinear</span> <span m='483520'>transformation</span> <span
  m='485350'>and</span> <span m='486070'>basically</span> <span
  m='487150'>involves</span> <span m='488080'>mapping</span> <span
  m='488590'>from</span> <span m='488770'>the s</span> <span
  m='489100'>plane</span> <span m='489430'>to</span> <span m='489550'>the</span>
  <span m='489670'>z</span> <span m='489880'>plane</span> <span
  m='490960'>by</span> <span m='491950'>applying--</span> <span
  m='492910'>by</span> <span m='493180'>relating</span> <span
  m='493750'>s</span> <span m='494170'>and</span> <span m='494350'>z</span>
  <span m='494770'>according</span> <span m='495280'>to</span> <span
  m='495520'>the</span> <span m='495640'>bilinear</span> <span
  m='496180'>transformation,</span> <span m='497160'>a</span> <span
  m='497500'>bilinear</span> <span m='497830'>transformation.</span> <span
  m='500110'>There,</span> <span m='500530'>in</span> <span
  m='500680'>fact,</span> <span m='501190'>is</span> <span m='501850'>an</span>
  <span m='501970'>interesting</span> <span m='502480'>way</span> <span
  m='502930'>of</span> <span m='503470'>deriving</span> <span
  m='504370'>this</span> <span m='504550'>technique,</span> <span
  m='505570'>which</span> <span m='505780'>is</span> <span
  m='505900'>somewhat</span> <span m='506380'>similar</span> <span
  m='507550'>to</span> <span m='507970'>the</span> <span
  m='508120'>technique</span> <span m='508750'>involving</span> <span
  m='509290'>mapping</span> <span m='509680'>differentials</span> <span
  m='510400'>to</span> <span m='510520'>differences.</span> <span
  m='511660'>But</span> <span m='512169'>of</span> <span
  m='512320'>course,</span> <span m='512650'>the</span> <span
  m='512740'>bilinear</span> <span m='513250'>transformation</span> <span
  m='514090'>will</span> <span m='514240'>turn</span> <span
  m='514510'>out</span> <span m='514690'>to</span> <span m='514809'>be a</span>
  <span m='515200'>much</span> <span m='515440'>more</span> <span
  m='515650'>useful</span> <span m='516039'>technique.</span> </p><p><span
  m='517940'>This</span> <span m='518049'>technique</span> <span
  m='518440'>can</span> <span m='518620'>be</span> <span
  m='518740'>derived--</span> <span m='519340'>and</span> <span
  m='519460'>we</span> <span m='519580'>won't</span> <span m='519760'>be</span>
  <span m='519880'>going</span> <span m='520150'>through</span> <span
  m='520360'>this</span> <span m='520570'>in</span> <span
  m='520659'>detail</span> <span m='521200'>here,</span> <span
  m='521500'>although</span> <span m='522370'>we</span> <span
  m='522549'>do</span> <span m='523030'>in</span> <span m='523210'>the</span>
  <span m='523299'>text--</span> <span m='525040'>this</span> <span
  m='525220'>can</span> <span m='525400'>be</span> <span
  m='525550'>derived</span> <span m='526810'>essentially</span> <span
  m='527830'>by</span> <span m='528550'>beginning</span> <span
  m='529390'>with</span> <span m='529990'>a</span> <span
  m='530470'>continuous</span> <span m='531130'>time</span> <span
  m='531760'>differential</span> <span m='532390'>equation,</span> <span
  m='533830'>integrating</span> <span m='534430'>the</span> <span
  m='534550'>equation</span> <span m='535150'>to</span> <span
  m='535270'>obtain</span> <span m='536080'>an</span> <span
  m='536410'>integral</span> <span m='536890'>equation,</span> <span
  m='538160'>and</span> <span m='538180'>then</span> <span
  m='538540'>approximating</span> <span m='540160'>the</span> <span
  m='540340'>integrals,</span> <span m='541570'>using</span> <span
  m='542020'>the</span> <span m='542110'>trapezoidal</span> <span
  m='542800'>rule.</span> <span m='543250'>In</span> <span
  m='543370'>other</span> <span m='543580'>words,</span> <span
  m='543790'>replacing</span> <span m='544390'>the</span> <span
  m='544510'>integrals</span> <span m='544960'>by</span> <span
  m='545170'>sums,</span> <span m='546250'>using</span> <span
  m='546580'>the</span> <span m='546640'>trapezoidal</span> <span
  m='547330'>rule</span> <span m='547570'>for</span> <span
  m='547780'>integration,</span> <span m='549010'>the</span> <span
  m='549130'>resulting</span> <span m='549670'>equation</span> <span
  m='550540'>is</span> <span m='550810'>then</span> <span m='551470'>a</span>
  <span m='551530'>difference</span> <span m='551950'>equation.</span> <span
  m='553300'>And</span> <span m='553660'>that</span> <span
  m='553870'>difference</span> <span m='554260'>equation</span> <span
  m='555460'>will</span> <span m='555610'>then</span> <span
  m='556090'>represent</span> <span m='556670'>the</span> <span
  m='556780'>digital</span> <span m='557170'>filter,</span> <span
  m='558280'>and</span> <span m='558940'>that</span> <span
  m='559180'>digital</span> <span m='559570'>filter,</span> <span
  m='560230'>as</span> <span m='560410'>it</span> <span m='560470'>turns</span>
  <span m='560860'>out,</span> <span m='561190'>can</span> <span
  m='561340'>be</span> <span m='561460'>related</span> <span
  m='561940'>back</span> <span m='562210'>to</span> <span m='562330'>the</span>
  <span m='562480'>analog</span> <span m='562930'>filter.</span> <span
  m='563320'>The</span> <span m='563410'>system</span> <span
  m='563830'>functions</span> <span m='564280'>can</span> <span
  m='564460'>be</span> <span m='564610'>related</span> <span
  m='565570'>through</span> <span m='566080'>a</span> <span
  m='566140'>transformation</span> <span m='567160'>from</span> <span
  m='567370'>s</span> <span m='567880'>to</span> <span m='568030'>z,</span>
  <span m='568970'>which</span> <span m='569140'>is,</span> <span
  m='569350'>in</span> <span m='569440'>fact,</span> <span m='569810'>the</span>
  <span m='569850'>bilinear</span> <span m='570400'>transformation.</span>
  </p><p><span m='572910'>So</span> <span m='573770'>the</span> <span
  m='574460'>technique</span> <span m='574970'>then</span> <span
  m='575870'>is</span> <span m='576020'>basically</span> <span
  m='577130'>to</span> <span m='577640'>begin</span> <span
  m='578030'>with</span> <span m='578180'>an</span> <span
  m='578270'>analog</span> <span m='578780'>system</span> <span
  m='579200'>function,</span> <span m='580520'>convert</span> <span
  m='580970'>that</span> <span m='581510'>to</span> <span m='581960'>a</span>
  <span m='582290'>digital</span> <span m='583160'>system</span> <span
  m='583640'>function,</span> <span m='584900'>and</span> <span
  m='585080'>do</span> <span m='585320'>that</span> <span m='585890'>by</span>
  <span m='586400'>replacing</span> <span m='587120'>s</span> <span
  m='588430'>by</span> <span m='588863'>a</span> <span
  m='589296'>bilinear</span> <span m='589730'>transformation,</span> <span
  m='591230'>where</span> <span m='591440'>the</span> <span
  m='591560'>bilinear</span> <span m='592070'>transformation</span> <span
  m='593060'>is</span> <span m='593510'>as</span> <span m='593750'>I've</span>
  <span m='593900'>indicated</span> <span m='594500'>here.</span> <span
  m='595700'>There's</span> <span m='595910'>a</span> <span
  m='595940'>parameter,</span> <span m='597020'>capital</span> <span
  m='597455'>T,</span> <span m='597890'>that</span> <span m='598550'>I've</span>
  <span m='598790'>introduced,</span> <span m='599480'>and</span> <span
  m='599630'>it's</span> <span m='599780'>a</span> <span
  m='599840'>parameter</span> <span m='600950'>that</span> <span
  m='601100'>comes</span> <span m='601490'>in,</span> <span
  m='601850'>basically,</span> <span m='602720'>because</span> <span
  m='603410'>of</span> <span m='603830'>what's</span> <span
  m='604130'>involved</span> <span m='604820'>in</span> <span
  m='605240'>applying</span> <span m='605720'>the</span> <span
  m='605840'>integration</span> <span m='606950'>or</span> <span
  m='607310'>applying</span> <span m='607640'>the</span> <span
  m='607730'>trapezoidal</span> <span m='608660'>rule</span> <span
  m='609560'>to</span> <span m='609800'>implementing</span> <span
  m='610370'>the</span> <span m='610520'>integration.</span> <span
  m='612380'>But</span> <span m='613310'>this</span> <span
  m='613580'>then</span> <span m='613910'>is</span> <span m='614120'>the</span>
  <span m='614210'>general</span> <span m='614600'>form</span> <span
  m='615140'>of</span> <span m='615290'>the</span> <span
  m='615410'>transformation.</span> <span m='617300'>Or</span> <span
  m='618080'>expressing</span> <span m='618710'>z</span> <span
  m='619280'>instead</span> <span m='619940'>as</span> <span m='620120'>a</span>
  <span m='620180'>function</span> <span m='620600'>of</span> <span
  m='620720'>s,</span> <span m='621380'>we</span> <span m='621530'>obtain</span>
  <span m='621920'>z</span> <span m='622310'>equals</span> <span
  m='623000'>1</span> <span m='623270'>plus</span> <span m='623630'>sT</span>
  <span m='624260'>over</span> <span m='624560'>2</span> <span
  m='625340'>divided</span> <span m='625760'>by</span> <span m='626000'>1</span>
  <span m='626270'>minus</span> <span m='626870'>sT</span> <span
  m='627380'>over</span> <span m='627630'>2.</span> </p><p><span
  m='628980'>So</span> <span m='629580'>one</span> <span
  m='629910'>important</span> <span m='630450'>aspect</span> <span
  m='630960'>of</span> <span m='631050'>this</span> <span
  m='631320'>then,</span> <span m='631950'>which,</span> <span
  m='632310'>in</span> <span m='632430'>fact,</span> <span m='632730'>is</span>
  <span m='632880'>different</span> <span m='633660'>than</span> <span
  m='634080'>the</span> <span m='634200'>impulse</span> <span
  m='634620'>invariant</span> <span m='635130'>procedure,</span> <span
  m='636630'>is</span> <span m='636810'>that</span> <span m='637370'>it,</span>
  <span m='637470'>in</span> <span m='637590'>fact,</span> <span
  m='637950'>does</span> <span m='638280'>correspond</span> <span
  m='639720'>to</span> <span m='639870'>a</span> <span m='639930'>mapping</span>
  <span m='640890'>from</span> <span m='641130'>s</span> <span
  m='641670'>to</span> <span m='641790'>z.</span> <span m='642240'>It's</span>
  <span m='642420'>a</span> <span m='642480'>mapping</span> <span
  m='642930'>of</span> <span m='643110'>the s</span> <span
  m='643440'>plane</span> <span m='643890'>to</span> <span m='644040'>the</span>
  <span m='644160'>z</span> <span m='644370'>plane,</span> <span
  m='644940'>which</span> <span m='645120'>is</span> <span m='645270'>not</span>
  <span m='645480'>quite</span> <span m='645840'>what</span> <span
  m='645990'>the</span> <span m='646110'>impulse</span> <span
  m='646500'>invariant</span> <span m='646980'>method</span> <span
  m='647340'>is.</span> <span m='648760'>Well,</span> <span
  m='649110'>recalling</span> <span m='649980'>that</span> <span
  m='650400'>there</span> <span m='650820'>are</span> <span
  m='652090'>two</span> <span m='652410'>guidelines</span> <span
  m='653190'>that</span> <span m='653310'>we</span> <span m='653430'>set</span>
  <span m='653700'>down</span> <span m='653970'>last</span> <span
  m='654330'>time,</span> <span m='655680'>we'd</span> <span
  m='655890'>like</span> <span m='656220'>to</span> <span
  m='656580'>verify,</span> <span m='658000'>first</span> <span
  m='658260'>of</span> <span m='658380'>all,</span> <span
  m='658930'>whether</span> <span m='659610'>the</span> <span
  m='659700'>bilinear</span> <span m='660270'>transformation</span> <span
  m='662110'>in</span> <span m='662210'>fact</span> <span
  m='662430'>preserves</span> <span m='663180'>the</span> <span
  m='663300'>characteristics,</span> <span m='664830'>the</span> <span
  m='664920'>frequency</span> <span m='665430'>characteristics--</span> <span
  m='666210'>that</span> <span m='666360'>is,</span> <span
  m='666510'>whether</span> <span m='666750'>it</span> <span
  m='666870'>maps</span> <span m='667230'>from</span> <span
  m='667380'>the</span> <span m='667470'>j</span> <span m='667770'>omega</span>
  <span m='668060'>axis</span> <span m='669090'>to</span> <span
  m='669210'>the</span> <span m='669300'>unit</span> <span
  m='669600'>circle,</span> <span m='670260'>first.</span> <span
  m='671250'>And</span> <span m='671370'>second</span> <span
  m='671730'>of</span> <span m='671850'>all,</span> <span m='672300'>does</span>
  <span m='672390'>it</span> <span m='672510'>map</span> <span
  m='673020'>stable</span> <span m='673980'>analog</span> <span
  m='674520'>filters</span> <span m='675000'>to</span> <span
  m='675150'>stable</span> <span m='675540'>digital</span> <span
  m='675930'>filters?</span> </p><p><span m='677730'>Well,</span> <span
  m='677940'>let's</span> <span m='678330'>look</span> <span
  m='678540'>at</span> <span m='678630'>the</span> <span m='678720'>first</span>
  <span m='679170'>question</span> <span m='679640'>first.</span> <span
  m='681150'>Let's</span> <span m='681600'>look</span> <span
  m='681870'>at</span> <span m='681930'>the</span> <span m='682050'>unit</span>
  <span m='682350'>circle</span> <span m='682980'>and</span> <span
  m='683130'>inquire</span> <span m='683820'>as</span> <span
  m='684060'>to</span> <span m='684210'>what</span> <span m='684510'>part</span>
  <span m='684960'>of</span> <span m='686040'>the</span> <span
  m='686190'>s</span> <span m='686460'>plane</span> <span m='687330'>the</span>
  <span m='687450'>unit</span> <span m='687720'>circle</span> <span
  m='688110'>came</span> <span m='688440'>from.</span> <span
  m='689580'>So</span> <span m='690120'>we</span> <span m='690300'>have,</span>
  <span m='690990'>then,</span> <span m='691550'>z</span> <span
  m='691830'>equals</span> <span m='692190'>e</span> <span m='692290'>to</span>
  <span m='692370'>the</span> <span m='692460'>j</span> <span
  m='692700'>omega</span> <span m='693480'>on</span> <span m='693660'>the</span>
  <span m='693750'>unit</span> <span m='694050'>circle.</span> <span
  m='695380'>And</span> <span m='695880'>so</span> <span m='696960'>we</span>
  <span m='697080'>want</span> <span m='697290'>to</span> <span
  m='697380'>inquire</span> <span m='697920'>as</span> <span
  m='698040'>to</span> <span m='698190'>what</span> <span
  m='698430'>values</span> <span m='698940'>of</span> <span m='699060'>s</span>
  <span m='702245'>land</span> <span m='703160'>on</span> <span
  m='703310'>the</span> <span m='703400'>unit</span> <span
  m='703700'>circle</span> <span m='704510'>through</span> <span
  m='704750'>the</span> <span m='704870'>bilinear</span> <span
  m='705440'>transformation.</span> <span m='706610'>And</span> <span
  m='706730'>we</span> <span m='706880'>do</span> <span m='707060'>that</span>
  <span m='707300'>simply</span> <span m='707720'>by</span> <span
  m='707930'>substituting</span> <span m='709210'>z</span> <span
  m='709630'>equals</span> <span m='710650'>e</span> <span m='711050'>to
  the</span> <span m='711170'>j</span> <span m='711420'>omega,</span> <span
  m='712820'>so</span> <span m='713060'>that</span> <span m='713870'>s</span>
  <span m='714110'>is</span> <span m='714260'>equal</span> <span
  m='714560'>to</span> <span m='714680'>2</span> <span m='714920'>over</span>
  <span m='715130'>capital</span> <span m='715410'>T</span> <span
  m='716030'>times</span> <span m='716360'>1</span> <span
  m='716570'>minus</span> <span m='716960'>e</span> <span m='717060'>to</span>
  <span m='717140'>the</span> <span m='717250'>minus j</span> <span
  m='717590'>omega</span> <span m='718790'>divided</span> <span
  m='719210'>by</span> <span m='719360'>1</span> <span m='719600'>plus</span>
  <span m='719910'>e</span> <span m='720050'>to</span> <span
  m='720140'>the</span> <span m='720230'>minus j</span> <span
  m='720590'>omega.</span> </p><p><span m='722030'>And</span> <span
  m='722180'>now</span> <span m='722630'>we</span> <span m='722840'>can</span>
  <span m='726360'>change</span> <span m='727230'>this</span> <span
  m='727530'>term</span> <span m='728250'>and</span> <span
  m='728580'>likewise</span> <span m='729270'>the</span> <span
  m='729360'>denominator</span> <span m='730080'>term</span> <span
  m='731070'>by</span> <span m='731280'>factoring</span> <span
  m='731970'>out</span> <span m='732660'>e</span> <span m='733065'>to</span>
  <span m='733470'>the</span> <span m='734220'>minus</span> <span
  m='734475'>j</span> <span m='734730'>omega</span> <span m='736140'>over</span>
  <span m='736470'>2.</span> <span m='738630'>And</span> <span
  m='738840'>then</span> <span m='739500'>this</span> <span
  m='739770'>numerator</span> <span m='740370'>term</span> <span
  m='740760'>becomes</span> <span m='741980'>e</span> <span m='742290'>to</span>
  <span m='742470'>the</span> <span m='742680'>plus</span> <span
  m='743460'>j</span> <span m='743970'>omega</span> <span m='744690'>over</span>
  <span m='745020'>2</span> <span m='746130'>minus</span> <span
  m='747260'>e</span> <span m='747360'>to</span> <span m='747450'>the</span>
  <span m='747570'>minus</span> <span m='747990'>j</span> <span
  m='748430'>omega</span> <span m='749310'>over</span> <span
  m='749620'>2.</span> <span m='752190'>And</span> <span m='752940'>we</span>
  <span m='753120'>recognize</span> <span m='753750'>this</span> <span
  m='753930'>numerator</span> <span m='754530'>then</span> <span
  m='754920'>as</span> <span m='755160'>2j</span> <span m='755950'>times</span>
  <span m='756160'>sine</span> <span m='756570'>omega</span> <span
  m='756960'>over</span> <span m='757230'>2.</span> </p><p><span
  m='758490'>Well,</span> <span m='758940'>likewise,</span> <span
  m='759540'>we</span> <span m='759690'>can</span> <span m='760380'>carry</span>
  <span m='760740'>out</span> <span m='760860'>a</span> <span
  m='760950'>similar</span> <span m='761520'>manipulation</span> <span
  m='762360'>with</span> <span m='762510'>the</span> <span
  m='762570'>denominator</span> <span m='763260'>term.</span> <span
  m='764580'>The</span> <span m='764670'>result</span> <span
  m='765120'>then</span> <span m='765960'>is</span> <span m='766260'>that</span>
  <span m='766950'>this</span> <span m='767160'>can</span> <span
  m='767340'>be</span> <span m='767490'>rewritten</span> <span
  m='768240'>as</span> <span m='768480'>2</span> <span m='768720'>over</span>
  <span m='769110'>capital</span> <span m='769545'>T</span> <span
  m='770400'>times</span> <span m='770760'>j</span> <span
  m='772230'>times</span> <span m='772710'>the</span> <span
  m='772830'>tangent</span> <span m='773520'>of</span> <span
  m='773700'>omega</span> <span m='774090'>over</span> <span
  m='774390'>2.</span> <span m='775980'>Well,</span> <span
  m='776610'>since</span> <span m='776880'>omega</span> <span
  m='778020'>ranges</span> <span m='778650'>from</span> <span
  m='778830'>0</span> <span m='779220'>to</span> <span m='779440'>2</span> <span
  m='779610'>pi,</span> <span m='780840'>this</span> <span m='781320'>is</span>
  <span m='781890'>always</span> <span m='782340'>a</span> <span
  m='782400'>real</span> <span m='782700'>number,</span> <span
  m='783570'>tangent</span> <span m='783960'>omega</span> <span
  m='784260'>over</span> <span m='784530'>2.</span> <span m='785460'>And</span>
  <span m='786330'>consequently,</span> <span m='787290'>we</span> <span
  m='787470'>can</span> <span m='787620'>rewrite</span> <span
  m='788100'>this</span> <span m='788460'>as</span> <span m='788670'>j</span>
  <span m='789360'>times</span> <span m='789660'>a</span> <span
  m='789720'>real</span> <span m='789960'>number</span> <span
  m='790290'>capital</span> <span m='790740'>Omega.</span> </p><p><span
  m='792450'>All</span> <span m='792510'>right.</span> <span
  m='792810'>Well,</span> <span m='793200'>what</span> <span
  m='793350'>does</span> <span m='793470'>that</span> <span
  m='793680'>say?</span> <span m='794080'>It</span> <span m='794100'>says</span>
  <span m='795000'>that</span> <span m='795330'>if</span> <span
  m='795480'>z</span> <span m='795750'>is</span> <span m='795900'>on</span>
  <span m='796050'>the</span> <span m='796140'>unit</span> <span
  m='796440'>circle,</span> <span m='798000'>then</span> <span
  m='798210'>s</span> <span m='799800'>is</span> <span m='799950'>going</span>
  <span m='800070'>to</span> <span m='800160'>be</span> <span
  m='800310'>of</span> <span m='800430'>the</span> <span m='800520'>form</span>
  <span m='800850'>j</span> <span m='801210'>times</span> <span
  m='801780'>a</span> <span m='801840'>real</span> <span
  m='802110'>number.</span> <span m='803040'>And</span> <span
  m='803190'>that</span> <span m='803370'>has</span> <span m='803610'>to</span>
  <span m='803760'>have</span> <span m='803880'>been,</span> <span
  m='804140'>then,</span> <span m='804300'>the</span> <span m='804390'>j</span>
  <span m='804660'>omega</span> <span m='804930'>axis.</span> <span
  m='806490'>So</span> <span m='807570'>s</span> <span m='807810'>equal</span>
  <span m='808080'>to</span> <span m='808200'>j</span> <span
  m='808440'>omega</span> <span m='809250'>means</span> <span
  m='809520'>z</span> <span m='809910'>equals</span> <span m='810390'>e</span>
  <span m='810490'>to</span> <span m='810600'>the</span> <span
  m='810720'>j</span> <span m='810990'>omega,</span> <span
  m='812250'>where</span> <span m='813090'>capital</span> <span
  m='813540'>Omega</span> <span m='814200'>and</span> <span
  m='814380'>little</span> <span m='814680'>omega</span> <span
  m='815670'>are</span> <span m='815790'>related</span> <span
  m='816660'>by</span> <span m='817140'>capital</span> <span
  m='817650'>Omega</span> <span m='818490'>equal</span> <span
  m='818850'>to</span> <span m='819000'>2</span> <span m='819300'>over</span>
  <span m='819550'>capital</span> <span m='819896'>T</span> <span
  m='821010'>times</span> <span m='821310'>the</span> <span
  m='821430'>tangent</span> <span m='822090'>of</span> <span
  m='822270'>little</span> <span m='822510'>omega</span> <span
  m='822930'>over</span> <span m='823200'>2.</span> </p><p><span
  m='824820'>Well,</span> <span m='825180'>that</span> <span
  m='825390'>says</span> <span m='825810'>that,</span> <span
  m='826080'>indeed,</span> <span m='827060'>the</span> <span
  m='827160'>j</span> <span m='827400'>omega</span> <span m='827820'>axis</span>
  <span m='828990'>gets</span> <span m='829200'>mapped</span> <span
  m='829770'>to</span> <span m='829890'>the</span> <span m='829980'>unit</span>
  <span m='830250'>circle,</span> <span m='830670'>and</span> <span
  m='830790'>vice</span> <span m='831060'>versa.</span> <span
  m='832260'>And</span> <span m='832500'>in</span> <span m='832590'>fact,</span>
  <span m='833800'>the</span> <span m='834570'>entire</span> <span
  m='835350'>j</span> <span m='835620'>omega</span> <span m='836040'>axis</span>
  <span m='837090'>gets</span> <span m='837300'>mapped</span> <span
  m='837860'>to</span> <span m='838050'>exactly</span> <span
  m='838650'>once</span> <span m='838950'>around</span> <span
  m='839280'>the</span> <span m='839370'>unit</span> <span
  m='839670'>circle.</span> <span m='841300'>Well,</span> <span
  m='841660'>let's</span> <span m='841930'>look</span> <span
  m='842140'>at</span> <span m='842230'>the</span> <span
  m='842350'>mapping</span> <span m='843060'>in</span> <span m='843700'>a</span>
  <span m='844130'>little</span> <span m='844420'>more</span> <span
  m='844690'>detail.</span> <span m='846850'>Here</span> <span
  m='847060'>we</span> <span m='847210'>have</span> <span m='847990'>the</span>
  <span m='848140'>s</span> <span m='848350'>plane,</span> <span
  m='849340'>and</span> <span m='849460'>here</span> <span m='849670'>we</span>
  <span m='849820'>have</span> <span m='850480'>the</span> <span
  m='850600'>z</span> <span m='850840'>plane.</span> <span m='852970'>We</span>
  <span m='853150'>have</span> <span m='853720'>the</span> <span
  m='854590'>relationship</span> <span m='855370'>between</span> <span
  m='855730'>the</span> <span m='855830'>j</span> <span m='856125'>omega</span>
  <span m='856420'>axis</span> <span m='857200'>and</span> <span
  m='857320'>the</span> <span m='857410'>unit</span> <span
  m='857710'>circle,</span> <span m='858850'>that</span> <span
  m='859000'>the</span> <span m='859090'>j</span> <span m='859420'>omega</span>
  <span m='859780'>axis</span> <span m='861100'>gets</span> <span
  m='861340'>mapped</span> <span m='862390'>to</span> <span
  m='862510'>the</span> <span m='862630'>unit</span> <span
  m='862930'>circle.</span> </p><p><span m='864010'>And</span> <span
  m='864130'>in</span> <span m='864250'>fact,</span> <span m='864940'>as</span>
  <span m='866080'>capital</span> <span m='866560'>Omega</span> <span
  m='867820'>runs</span> <span m='868120'>from</span> <span
  m='868270'>minus</span> <span m='868690'>infinity</span> <span
  m='869680'>to</span> <span m='869780'>plus</span> <span
  m='870010'>infinity,</span> <span m='872200'>we</span> <span
  m='873070'>map</span> <span m='873910'>exactly</span> <span
  m='875050'>once</span> <span m='875620'>around</span> <span
  m='876550'>the</span> <span m='876610'>unit</span> <span
  m='876910'>circle.</span> <span m='879090'>Now,</span> <span
  m='879110'>that's</span> <span m='879320'>an</span> <span
  m='879380'>important</span> <span m='880400'>point</span> <span
  m='881090'>for</span> <span m='881240'>two</span> <span
  m='881450'>reasons.</span> <span m='882800'>One</span> <span
  m='882920'>is</span> <span m='883070'>that,</span> <span
  m='883250'>obviously,</span> <span m='883760'>there's</span> <span
  m='883940'>no</span> <span m='884120'>aliasing</span> <span
  m='885140'>involved</span> <span m='885780'>anymore,</span> <span
  m='886760'>because</span> <span m='887930'>the</span> <span
  m='888050'>entire</span> <span m='888590'>j</span> <span
  m='888830'>omega</span> <span m='889250'>axis</span> <span
  m='889940'>ended</span> <span m='890270'>up</span> <span
  m='891470'>once</span> <span m='891740'>around</span> <span
  m='892010'>the</span> <span m='892130'>unit</span> <span
  m='892370'>circle.</span> <span m='892760'>That</span> <span
  m='892860'>is,</span> <span m='893030'>there</span> <span
  m='893150'>was</span> <span m='893300'>nothing</span> <span
  m='893660'>that</span> <span m='893780'>got</span> <span
  m='893990'>added</span> <span m='894320'>on</span> <span m='894400'>to</span>
  <span m='894590'>something</span> <span m='894980'>else</span> <span
  m='895220'>that</span> <span m='895310'>got</span> <span
  m='895520'>added</span> <span m='895790'>on</span> <span m='895910'>to</span>
  <span m='896030'>something</span> <span m='896450'>else,</span> <span
  m='897230'>as</span> <span m='897380'>it</span> <span m='897470'>did</span>
  <span m='897740'>with</span> <span m='897890'>the</span> <span
  m='898010'>impulse</span> <span m='898430'>invariant</span> <span
  m='899180'>method.</span> </p><p><span m='901500'>The</span> <span
  m='901620'>second</span> <span m='902010'>point</span> <span
  m='902730'>is</span> <span m='903000'>that</span> <span m='904380'>that</span>
  <span m='904680'>axis</span> <span m='905340'>is</span> <span
  m='905520'>infinitely</span> <span m='906090'>long.</span> <span
  m='907200'>The</span> <span m='907320'>unit</span> <span
  m='907620'>circle</span> <span m='908370'>only</span> <span
  m='908700'>has</span> <span m='908880'>a</span> <span m='908940'>finite</span>
  <span m='909390'>circumference.</span> <span m='911020'>So</span> <span
  m='911280'>clearly,</span> <span m='912210'>something</span> <span
  m='912750'>has</span> <span m='912990'>to</span> <span
  m='913110'>happen.</span> <span m='913650'>Something</span> <span
  m='914100'>has</span> <span m='914310'>to</span> <span m='914430'>be</span>
  <span m='914610'>distorted</span> <span m='915720'>in</span> <span
  m='915840'>order</span> <span m='916080'>to</span> <span m='916200'>fit</span>
  <span m='916470'>all</span> <span m='916770'>of</span> <span
  m='916860'>that</span> <span m='917520'>onto</span> <span
  m='917910'>just</span> <span m='918180'>this</span> <span
  m='918390'>little</span> <span m='918660'>bit.</span> <span
  m='919590'>In</span> <span m='919710'>particular,</span> <span
  m='921390'>the</span> <span m='922200'>mapping,</span> <span
  m='923160'>if</span> <span m='923310'>we</span> <span m='923430'>draw</span>
  <span m='923850'>it,</span> <span m='924030'>between</span> <span
  m='924540'>little</span> <span m='924840'>omega,</span> <span
  m='925830'>angular</span> <span m='926250'>frequency</span> <span
  m='927060'>around</span> <span m='927390'>the</span> <span
  m='927480'>unit</span> <span m='927780'>circle,</span> <span
  m='928860'>and</span> <span m='928980'>distance</span> <span
  m='929430'>along</span> <span m='929760'>the</span> <span m='929850'>j</span>
  <span m='930060'>omega</span> <span m='930420'>axis,</span> <span
  m='931560'>looks</span> <span m='932100'>as</span> <span
  m='932280'>I've</span> <span m='932430'>indicated</span> <span
  m='933030'>here,</span> <span m='933900'>which,</span> <span
  m='934140'>of</span> <span m='934230'>course,</span> <span
  m='934560'>is</span> <span m='934680'>a</span> <span
  m='934740'>nonlinear</span> <span m='935370'>curve.</span> <span
  m='937250'>Well,</span> <span m='937510'>let</span> <span m='937660'>me</span>
  <span m='937810'>return</span> <span m='938590'>to</span> <span
  m='938710'>that</span> <span m='938950'>in</span> <span m='939040'>a</span>
  <span m='939100'>second.</span> </p><p><span m='940810'>An</span> <span
  m='940930'>additional</span> <span m='941410'>point</span> <span
  m='941770'>about</span> <span m='942040'>the</span> <span
  m='942130'>bilinear</span> <span m='942670'>transformation,</span> <span
  m='943850'>which</span> <span m='944140'>I'll</span> <span
  m='944250'>state</span> <span m='945010'>simply</span> <span
  m='945850'>and</span> <span m='946390'>leave</span> <span m='946690'>it</span>
  <span m='946960'>to</span> <span m='947080'>you</span> <span
  m='947230'>to</span> <span m='947320'>verify,</span> <span
  m='949000'>is</span> <span m='949240'>that</span> <span m='949840'>the</span>
  <span m='949960'>bilinear</span> <span m='950440'>transformation</span> <span
  m='951220'>has</span> <span m='951460'>the</span> <span
  m='951550'>property</span> <span m='952900'>that</span> <span
  m='953020'>the</span> <span m='953110'>left</span> <span m='953530'>1/2</span>
  <span m='953830'>of</span> <span m='953920'>the</span> <span
  m='954280'>s</span> <span m='954380'>plane</span> <span m='955930'>gets</span>
  <span m='956170'>mapped</span> <span m='956770'>to</span> <span
  m='956890'>the</span> <span m='957070'>interior</span> <span
  m='957730'>of</span> <span m='957850'>the</span> <span m='957940'>unit</span>
  <span m='958240'>circle,</span> <span m='959500'>and</span> <span
  m='959620'>the</span> <span m='959740'>right</span> <span
  m='960010'>half</span> <span m='960340'>of</span> <span m='960430'>the</span>
  <span m='960760'>s</span> <span m='960860'>plane</span> <span
  m='961630'>gets</span> <span m='961870'>mapped</span> <span
  m='962470'>to</span> <span m='962590'>the</span> <span
  m='962740'>exterior</span> <span m='963400'>of</span> <span
  m='963460'>the</span> <span m='963580'>unit</span> <span
  m='963850'>circle.</span> <span m='965450'>Well,</span> <span
  m='966410'>that's</span> <span m='966650'>good,</span> <span
  m='967280'>because</span> <span m='968180'>that</span> <span
  m='968420'>says</span> <span m='968900'>that,</span> <span
  m='969050'>if</span> <span m='969200'>we</span> <span m='969350'>have</span>
  <span m='969530'>poles</span> <span m='970400'>or</span> <span
  m='970590'>0s--</span> <span m='971840'>but</span> <span
  m='972050'>poles</span> <span m='972410'>is</span> <span
  m='972530'>what</span> <span m='972680'>we</span> <span
  m='972800'>really</span> <span m='973070'>care</span> <span
  m='973340'>about</span> <span m='973580'>right</span> <span
  m='973820'>now--</span> <span m='974630'>we</span> <span
  m='974750'>have</span> <span m='974840'>poles</span> <span
  m='975410'>in</span> <span m='975530'>the</span> <span m='975620'>left</span>
  <span m='975890'>1/2</span> <span m='976160'>of</span> <span
  m='976250'>the</span> <span m='976580'>s</span> <span m='976680'>plane,</span>
  <span m='977570'>they'll</span> <span m='977810'>end</span> <span
  m='978020'>up</span> <span m='978230'>inside</span> <span
  m='978710'>the</span> <span m='978830'>unit</span> <span
  m='979100'>circle.</span> <span m='980190'>So</span> <span
  m='980270'>if</span> <span m='980390'>we</span> <span m='980510'>have</span>
  <span m='980930'>a</span> <span m='980990'>stable</span> <span
  m='981530'>analog</span> <span m='982040'>filter,</span> <span
  m='983030'>we'll</span> <span m='983210'>end</span> <span m='983390'>up</span>
  <span m='983540'>with</span> <span m='983690'>a</span> <span
  m='983720'>stable</span> <span m='984170'>digital</span> <span
  m='984530'>filter.</span> <span m='986120'>If</span> <span
  m='986240'>we</span> <span m='986330'>have</span> <span m='986750'>an</span>
  <span m='986900'>unstable</span> <span m='987500'>analog</span> <span
  m='987980'>filter,</span> <span m='988550'>corresponding</span> <span
  m='989210'>to</span> <span m='989300'>poles</span> <span m='989660'>on</span>
  <span m='989750'>the</span> <span m='989810'>right</span> <span
  m='990050'>1/2</span> <span m='990320'>of</span> <span m='990410'>the</span>
  <span m='990740'>s</span> <span m='990840'>plane,</span> <span
  m='991640'>then</span> <span m='992240'>we'll</span> <span
  m='992450'>end</span> <span m='992660'>up</span> <span m='993050'>with</span>
  <span m='993500'>an</span> <span m='993680'>unstable</span> <span
  m='994280'>digital</span> <span m='994640'>filter,</span> <span
  m='995090'>corresponding</span> <span m='995780'>to</span> <span
  m='995900'>poles</span> <span m='996440'>outside</span> <span
  m='996920'>the</span> <span m='997040'>unit</span> <span
  m='997310'>circle.</span> </p><p><span m='999250'>All</span> <span
  m='999340'>right.</span> <span m='999610'>Well,</span> <span
  m='1000120'>now,</span> <span m='1000540'>returning</span> <span
  m='1001500'>to</span> <span m='1002700'>the</span> <span
  m='1003210'>mapping</span> <span m='1003900'>of</span> <span
  m='1004050'>the</span> <span m='1004140'>j</span> <span
  m='1004380'>omega</span> <span m='1004740'>axis</span> <span
  m='1005790'>to</span> <span m='1007170'>digital</span> <span
  m='1007680'>frequency,</span> <span m='1008550'>the</span> <span
  m='1008670'>mapping</span> <span m='1009000'>from</span> <span
  m='1009180'>analog</span> <span m='1009600'>frequency</span> <span
  m='1010110'>to</span> <span m='1010530'>digital</span> <span
  m='1010980'>frequency,</span> <span m='1012210'>one</span> <span
  m='1012360'>of</span> <span m='1012480'>the</span> <span
  m='1012600'>important</span> <span m='1013110'>aspects</span> <span
  m='1013770'>of</span> <span m='1013860'>the</span> <span
  m='1013980'>bilinear</span> <span m='1014490'>transformation</span> <span
  m='1016050'>is</span> <span m='1016230'>that</span> <span
  m='1016440'>that</span> <span m='1016710'>mapping</span> <span
  m='1017880'>ends</span> <span m='1018210'>up</span> <span
  m='1018600'>as</span> <span m='1018780'>a</span> <span
  m='1018840'>nonlinear</span> <span m='1019470'>mapping.</span> <span
  m='1022340'>Well,</span> <span m='1022940'>what</span> <span
  m='1023120'>are</span> <span m='1023150'>the</span> <span
  m='1023270'>consequences</span> <span m='1024109'>of</span> <span
  m='1024230'>that?</span> <span m='1024800'>Let's</span> <span
  m='1025250'>take</span> <span m='1025520'>a</span> <span
  m='1025550'>look</span> <span m='1025849'>at</span> <span
  m='1026089'>it</span> <span m='1026390'>in</span> <span m='1026990'>a</span>
  <span m='1027050'>little</span> <span m='1027290'>more</span> <span
  m='1027530'>detail.</span> <span m='1029540'>And</span> <span
  m='1030290'>in</span> <span m='1030410'>addition</span> <span
  m='1030829'>to</span> <span m='1030950'>pointing</span> <span
  m='1031369'>out</span> <span m='1032119'>some</span> <span
  m='1032390'>of</span> <span m='1032480'>the</span> <span
  m='1032599'>problems</span> <span m='1032899'>that</span> <span
  m='1033200'>that</span> <span m='1033530'>raises,</span> <span
  m='1034640'>this</span> <span m='1035390'>offers</span> <span
  m='1035839'>us</span> <span m='1036079'>an</span> <span
  m='1036200'>opportunity</span> <span m='1037550'>to</span> <span
  m='1038180'>indicate</span> <span m='1039230'>how,</span> <span
  m='1039680'>in</span> <span m='1039800'>fact,</span> <span
  m='1040430'>this</span> <span m='1040609'>distortion</span> <span
  m='1041839'>can</span> <span m='1041990'>be</span> <span
  m='1042079'>taken</span> <span m='1042470'>into</span> <span
  m='1042710'>account</span> <span m='1043460'>in</span> <span
  m='1044210'>implementing</span> <span m='1044869'>a</span> <span
  m='1044930'>digital</span> <span m='1045319'>filter</span> <span
  m='1045680'>design.</span> </p><p><span m='1047490'>So</span> <span
  m='1047900'>here</span> <span m='1048319'>is</span> <span
  m='1048770'>the</span> <span m='1050720'>frequency</span> <span
  m='1051350'>mapping</span> <span m='1052040'>of</span> <span
  m='1052190'>the</span> <span m='1052280'>bilinear</span> <span
  m='1052790'>transformation.</span> <span m='1054060'>This</span> <span
  m='1054140'>is</span> <span m='1054260'>digital</span> <span
  m='1054650'>frequency.</span> <span m='1055940'>Here</span> <span
  m='1056120'>is</span> <span m='1056210'>analog</span> <span
  m='1056750'>frequency.</span> <span m='1058280'>And</span> <span
  m='1059030'>this</span> <span m='1059240'>curve,</span> <span
  m='1059810'>of</span> <span m='1059930'>course,</span> <span
  m='1060200'>goes</span> <span m='1060440'>out</span> <span
  m='1060620'>to</span> <span m='1060800'>infinity</span> <span
  m='1061730'>in</span> <span m='1061850'>capital</span> <span
  m='1062300'>Omega</span> <span m='1063010'>and</span> <span
  m='1063170'>asymptotically</span> <span m='1064010'>approaches</span> <span
  m='1064520'>pi,</span> <span m='1065600'>as</span> <span m='1065750'>it</span>
  <span m='1065840'>does</span> <span m='1066110'>that,</span> <span
  m='1066530'>in</span> <span m='1066710'>little</span> <span
  m='1066950'>omega.</span> <span m='1067820'>That</span> <span
  m='1068000'>says</span> <span m='1068360'>that</span> <span
  m='1068510'>the</span> <span m='1068630'>top</span> <span
  m='1068960'>1/2</span> <span m='1069290'>of</span> <span
  m='1069380'>the</span> <span m='1069470'>j</span> <span
  m='1069725'>omega</span> <span m='1069980'>axis</span> <span
  m='1071000'>gets</span> <span m='1071210'>mapped</span> <span
  m='1071720'>to</span> <span m='1071870'>the</span> <span
  m='1072020'>upper</span> <span m='1072320'>1/2</span> <span
  m='1072890'>of</span> <span m='1073040'>the</span> <span
  m='1073160'>unit</span> <span m='1073430'>circle.</span> </p><p><span
  m='1075260'>Well,</span> <span m='1075650'>suppose</span> <span
  m='1076550'>that</span> <span m='1076880'>we</span> <span
  m='1077120'>had,</span> <span m='1078020'>say,</span> <span
  m='1078350'>an</span> <span m='1078470'>analog</span> <span
  m='1079280'>filter</span> <span m='1080210'>frequency</span> <span
  m='1080780'>response</span> <span m='1082220'>that</span> <span
  m='1082850'>was,</span> <span m='1083720'>let's</span> <span
  m='1083930'>say,</span> <span m='1084110'>linear</span> <span
  m='1084710'>in</span> <span m='1084860'>frequency.</span> <span
  m='1086720'>Would</span> <span m='1087350'>the</span> <span
  m='1087500'>corresponding</span> <span m='1088310'>digital</span> <span
  m='1089720'>frequency</span> <span m='1090230'>response</span> <span
  m='1090830'>also</span> <span m='1091190'>be</span> <span m='1091340'>linear
  in</span> <span m='1091820'>frequency?</span> <span m='1093150'>Well,</span>
  <span m='1093650'>the</span> <span m='1093800'>answer</span> <span
  m='1094100'>to</span> <span m='1094220'>that,</span> <span
  m='1094460'>unfortunately,</span> <span m='1095270'>is</span> <span
  m='1095420'>no.</span> <span m='1096650'>In</span> <span
  m='1096770'>other</span> <span m='1096980'>words,</span> <span
  m='1097940'>a</span> <span m='1098870'>frequency</span> <span
  m='1099440'>characteristic</span> <span m='1100730'>along</span> <span
  m='1101120'>this</span> <span m='1101360'>axis</span> <span
  m='1102800'>will</span> <span m='1102950'>get</span> <span
  m='1103190'>distorted</span> <span m='1104060'>as</span> <span
  m='1104300'>it</span> <span m='1104390'>gets</span> <span
  m='1104630'>reflected</span> <span m='1105750'>through</span> <span
  m='1106280'>this</span> <span m='1106490'>nonlinear</span> <span
  m='1107150'>curve.</span> <span m='1108500'>For</span> <span
  m='1108710'>example,</span> <span m='1110420'>let's</span> <span
  m='1111050'>look</span> <span m='1111470'>specifically</span> <span
  m='1112670'>at</span> <span m='1114590'>a</span> <span
  m='1115340'>linear</span> <span m='1116330'>analog</span> <span
  m='1117500'>frequency</span> <span m='1118040'>characteristic,</span> <span
  m='1119120'>as</span> <span m='1119270'>I've</span> <span
  m='1119420'>indicated</span> <span m='1120020'>here</span> <span
  m='1121160'>which</span> <span m='1121340'>might,</span> <span
  m='1121740'>for</span> <span m='1121850'>example,</span> <span
  m='1122400'>be</span> <span m='1122450'>the</span> <span
  m='1122570'>frequency</span> <span m='1123050'>response</span> <span
  m='1123530'>of</span> <span m='1123620'>a</span> <span
  m='1123680'>differentiator.</span> <span m='1124820'>That,</span> <span
  m='1125000'>in</span> <span m='1125120'>fact,</span> <span
  m='1125420'>is</span> <span m='1125990'>the</span> <span
  m='1126080'>kind</span> <span m='1126260'>of</span> <span
  m='1126350'>frequency</span> <span m='1126830'>response</span> <span
  m='1127610'>that</span> <span m='1127730'>a</span> <span
  m='1127790'>differentiator</span> <span m='1128630'>might</span> <span
  m='1128870'>have.</span> </p><p><span m='1130700'>As</span> <span
  m='1130970'>we</span> <span m='1131150'>reflect</span> <span
  m='1131690'>that</span> <span m='1132590'>through</span> <span
  m='1132770'>this</span> <span m='1132950'>nonlinear</span> <span
  m='1133610'>curve,</span> <span m='1135140'>because</span> <span
  m='1135500'>of</span> <span m='1135620'>the</span> <span
  m='1135710'>fact</span> <span m='1136100'>that</span> <span
  m='1136230'>that's</span> <span m='1136490'>nonlinear,</span> <span
  m='1137750'>we</span> <span m='1137900'>don't</span> <span
  m='1138230'>maintain</span> <span m='1139310'>the</span> <span
  m='1139430'>linearity</span> <span m='1140480'>of</span> <span
  m='1141170'>the</span> <span m='1141320'>analog</span> <span
  m='1142100'>frequency</span> <span m='1142640'>response.</span> <span
  m='1144050'>Now,</span> <span m='1144320'>if</span> <span
  m='1144500'>it</span> <span m='1144590'>happened</span> <span
  m='1145130'>that</span> <span m='1145730'>this</span> <span
  m='1145910'>was</span> <span m='1146060'>the</span> <span
  m='1146180'>kind</span> <span m='1146390'>of</span> <span
  m='1146480'>frequency</span> <span m='1146990'>response</span> <span
  m='1147530'>that</span> <span m='1147650'>we</span> <span
  m='1147800'>wanted,</span> <span m='1149090'>we</span> <span
  m='1149240'>could</span> <span m='1149390'>get</span> <span
  m='1149660'>that</span> <span m='1150080'>from</span> <span
  m='1150290'>an</span> <span m='1150380'>analog</span> <span
  m='1150860'>differentiator.</span> <span m='1152880'>But</span> <span
  m='1154310'>more</span> <span m='1154550'>typically,</span> <span
  m='1155300'>what</span> <span m='1155540'>we</span> <span
  m='1155690'>might</span> <span m='1155960'>be</span> <span
  m='1156110'>interested</span> <span m='1156650'>in</span> <span
  m='1157160'>is</span> <span m='1158060'>a</span> <span
  m='1158150'>digital</span> <span m='1158570'>differentiator</span> <span
  m='1159530'>which</span> <span m='1160310'>would</span> <span
  m='1160460'>have,</span> <span m='1160760'>say,</span> <span
  m='1161180'>a</span> <span m='1161270'>linear</span> <span
  m='1161630'>frequency</span> <span m='1162170'>characteristic.</span> <span
  m='1163740'>And</span> <span m='1164090'>one</span> <span
  m='1164330'>of</span> <span m='1164390'>the</span> <span
  m='1164480'>important</span> <span m='1164960'>aspects</span> <span
  m='1165620'>of</span> <span m='1165770'>the</span> <span
  m='1165860'>bilinear</span> <span m='1166400'>transformation</span> <span
  m='1168200'>is</span> <span m='1168410'>that</span> <span
  m='1168980'>we</span> <span m='1169100'>couldn't</span> <span
  m='1169520'>design</span> <span m='1170030'>that</span> <span
  m='1170840'>by</span> <span m='1171470'>designing--</span> <span
  m='1172220'>by</span> <span m='1172610'>mapping</span> <span
  m='1173120'>over</span> <span m='1173540'>an</span> <span
  m='1173720'>analog</span> <span m='1175550'>differentiator</span> <span
  m='1176750'>to</span> <span m='1176900'>a</span> <span
  m='1176960'>digital</span> <span m='1177430'>differentiator,</span> <span
  m='1178610'>using</span> <span m='1178940'>the</span> <span
  m='1179000'>bilinear</span> <span m='1179510'>transformation.</span>
  </p><p><span m='1180770'>Now,</span> <span m='1180890'>that's</span> <span
  m='1181130'>in</span> <span m='1181220'>contrast</span> <span
  m='1182180'>to</span> <span m='1182270'>the</span> <span
  m='1182420'>impulse</span> <span m='1182810'>invariant</span> <span
  m='1183380'>design</span> <span m='1183800'>procedure,</span> <span
  m='1185090'>where,</span> <span m='1186080'>in</span> <span
  m='1186230'>fact,</span> <span m='1187220'>for</span> <span
  m='1187580'>an</span> <span m='1187700'>impulse</span> <span
  m='1187955'>invariant</span> <span m='1189050'>design,</span> <span
  m='1190520'>if</span> <span m='1190670'>we</span> <span
  m='1190820'>have</span> <span m='1191060'>a</span> <span
  m='1191120'>band-limited</span> <span m='1191870'>filter</span> <span
  m='1192950'>that</span> <span m='1193220'>is</span> <span
  m='1193490'>linear</span> <span m='1194090'>over</span> <span
  m='1194390'>some</span> <span m='1194600'>part</span> <span
  m='1194900'>of</span> <span m='1194990'>the</span> <span
  m='1195080'>frequency</span> <span m='1195620'>band,</span> <span
  m='1196700'>impulse</span> <span m='1197180'>invariance</span> <span
  m='1197960'>would</span> <span m='1198170'>maintain</span> <span
  m='1198710'>the</span> <span m='1198800'>linearity</span> <span
  m='1199580'>of</span> <span m='1199730'>the</span> <span
  m='1199850'>frequency</span> <span m='1200330'>characteristics.</span> <span
  m='1201690'>So</span> <span m='1201950'>that's</span> <span
  m='1202190'>an</span> <span m='1202280'>important</span> <span
  m='1203630'>distinction</span> <span m='1204320'>between</span> <span
  m='1204710'>these</span> <span m='1204920'>two</span> <span
  m='1205070'>methods</span> <span m='1205620'>and,</span> <span
  m='1205720'>in</span> <span m='1205820'>fact,</span> <span
  m='1206120'>a</span> <span m='1206180'>drawback</span> <span
  m='1206930'>to</span> <span m='1207050'>the</span> <span
  m='1207140'>bilinear</span> <span m='1207680'>transformation.</span>
  </p><p><span m='1209890'>Well,</span> <span m='1210190'>where</span> <span
  m='1210520'>might</span> <span m='1210790'>we</span> <span
  m='1211000'>be</span> <span m='1211180'>able</span> <span
  m='1211420'>to</span> <span m='1211570'>tolerate</span> <span
  m='1212560'>this</span> <span m='1212800'>kind</span> <span m='1213100'>of
  a</span> <span m='1213250'>nonlinear</span> <span
  m='1213850'>distortion</span> <span m='1214700'>in</span> <span
  m='1214850'>the</span> <span m='1214930'>frequency</span> <span
  m='1215500'>axis?</span> <span m='1216760'>One</span> <span
  m='1216970'>place</span> <span m='1217540'>we</span> <span
  m='1217690'>could</span> <span m='1218620'>is</span> <span
  m='1219340'>when</span> <span m='1220060'>the</span> <span
  m='1220360'>desired</span> <span m='1222240'>digital</span> <span
  m='1222630'>filter</span> <span m='1223830'>is</span> <span
  m='1224520'>piecewise</span> <span m='1225150'>constant,</span> <span
  m='1226380'>in</span> <span m='1226530'>which</span> <span
  m='1226770'>case</span> <span m='1227490'>that</span> <span
  m='1227790'>will</span> <span m='1227940'>get</span> <span
  m='1228150'>reflected</span> <span m='1228960'>into</span> <span
  m='1229500'>a</span> <span m='1229560'>piecewise</span> <span
  m='1230190'>constant</span> <span m='1230820'>analog</span> <span
  m='1231390'>filter.</span> <span m='1232350'>And</span> <span
  m='1232470'>let</span> <span m='1232620'>me</span> <span
  m='1232980'>indicate</span> <span m='1233520'>that</span> <span
  m='1233760'>more</span> <span m='1233970'>explicitly.</span> </p><p><span
  m='1242130'>Let's</span> <span m='1242640'>suppose</span> <span
  m='1243750'>that</span> <span m='1244440'>we</span> <span
  m='1244650'>were</span> <span m='1244830'>interested</span> <span
  m='1245520'>in</span> <span m='1245700'>designing</span> <span
  m='1247970'>a</span> <span m='1248310'>digital</span> <span
  m='1249570'>filter,</span> <span m='1250140'>which</span> <span
  m='1250380'>was</span> <span m='1250530'>a</span> <span m='1250560'>low</span>
  <span m='1250770'>pass</span> <span m='1251160'>filter.</span> <span
  m='1252150'>Here's</span> <span m='1252510'>the</span> <span
  m='1252600'>magnitude</span> <span m='1253140'>axis,</span> <span
  m='1254220'>and</span> <span m='1254340'>here's</span> <span
  m='1254550'>the</span> <span m='1254640'>frequency</span> <span
  m='1255240'>axis.</span> <span m='1256260'>And</span> <span
  m='1256980'>the</span> <span m='1257190'>digital</span> <span
  m='1257580'>low</span> <span m='1257790'>pass</span> <span
  m='1258150'>filter</span> <span m='1259200'>was</span> <span
  m='1259650'>unity,</span> <span m='1260310'>say,</span> <span
  m='1260590'>in</span> <span m='1260670'>the</span> <span
  m='1260760'>passband,</span> <span m='1262330'>a</span> <span
  m='1263310'>rapid</span> <span m='1263730'>cutoff</span> <span
  m='1264570'>at</span> <span m='1264840'>the</span> <span
  m='1265020'>passband</span> <span m='1265710'>edge,</span> <span
  m='1266080'>and</span> <span m='1266250'>then</span> <span
  m='1266400'>0.</span> <span m='1267810'>Well,</span> <span
  m='1268740'>clearly,</span> <span m='1270500'>this</span> <span
  m='1271070'>part</span> <span m='1271400'>being</span> <span
  m='1271700'>constant</span> <span m='1272750'>gets</span> <span
  m='1273020'>reflected</span> <span m='1274010'>through</span> <span
  m='1274220'>this</span> <span m='1274400'>nonlinear</span> <span
  m='1274970'>frequency</span> <span m='1275540'>curve</span> <span
  m='1276530'>into</span> <span m='1277280'>a</span> <span
  m='1277520'>constant</span> <span m='1278750'>analog</span> <span
  m='1279590'>frequency</span> <span m='1280130'>characteristic.</span> <span
  m='1282590'>Similarly,</span> <span m='1283280'>the</span> <span
  m='1283580'>stopband</span> <span m='1284690'>gets</span> <span
  m='1284930'>reflected</span> <span m='1285750'>into</span> <span
  m='1286370'>a</span> <span m='1286460'>constant</span> <span
  m='1288230'>amplitude,</span> <span m='1289220'>in</span> <span
  m='1289340'>this</span> <span m='1289490'>case,</span> <span
  m='1289730'>0,</span> <span m='1290930'>in</span> <span m='1291080'>the</span>
  <span m='1291200'>analog</span> <span m='1291840'>frequency</span> <span
  m='1292400'>response.</span> </p><p><span m='1293090'>And</span> <span
  m='1293210'>what's</span> <span m='1293510'>the</span> <span
  m='1293660'>effect</span> <span m='1294680'>of</span> <span
  m='1295850'>this</span> <span m='1296300'>nonlinear</span> <span
  m='1297110'>distortion</span> <span m='1297680'>in</span> <span
  m='1297770'>the</span> <span m='1297860'>frequency</span> <span
  m='1298430'>axis?</span> <span m='1299540'>The</span> <span
  m='1299660'>only</span> <span m='1299900'>effect</span> <span
  m='1300230'>that</span> <span m='1300350'>it</span> <span
  m='1300470'>has</span> <span m='1301130'>is</span> <span
  m='1301400'>that</span> <span m='1302630'>the</span> <span
  m='1303260'>cutoff</span> <span m='1303740'>frequency</span> <span
  m='1304280'>of</span> <span m='1304370'>the</span> <span
  m='1304490'>filter</span> <span m='1305990'>or,</span> <span
  m='1306490'>in</span> <span m='1306630'>the</span> <span
  m='1306680'>more</span> <span m='1306860'>general</span> <span
  m='1307310'>case,</span> <span m='1308120'>the</span> <span
  m='1308210'>frequencies</span> <span m='1309140'>at</span> <span
  m='1309290'>which</span> <span m='1310070'>the</span> <span
  m='1311510'>piecewise</span> <span m='1312680'>constant</span> <span
  m='1313130'>characteristic</span> <span m='1313910'>changes</span> <span
  m='1314390'>from</span> <span m='1314600'>one</span> <span
  m='1314810'>piece</span> <span m='1315110'>to</span> <span
  m='1315260'>another</span> <span m='1316850'>gets</span> <span
  m='1317420'>changed</span> <span m='1318110'>according</span> <span
  m='1318710'>to</span> <span m='1319580'>this</span> <span
  m='1319940'>frequency</span> <span m='1320870'>warping</span> <span
  m='1321600'>characteristic.</span> <span m='1322560'>So</span> <span
  m='1323330'>this</span> <span m='1323780'>cutoff</span> <span
  m='1324170'>frequency</span> <span m='1325490'>gets</span> <span
  m='1325970'>converted</span> <span m='1326690'>into</span> <span
  m='1327380'>a</span> <span m='1327470'>new</span> <span
  m='1327650'>cutoff</span> <span m='1328070'>frequency,</span> <span
  m='1329330'>where</span> <span m='1329780'>the</span> <span
  m='1329960'>analog</span> <span m='1330410'>cutoff</span> <span
  m='1330740'>frequency</span> <span m='1331520'>is</span> <span
  m='1331670'>related</span> <span m='1332090'>to</span> <span
  m='1332210'>the</span> <span m='1332300'>digital</span> <span
  m='1332780'>cutoff</span> <span m='1333110'>frequency</span> <span
  m='1334370'>according</span> <span m='1334820'>to</span> <span
  m='1334940'>that</span> <span m='1335180'>curve.</span> </p><p><span
  m='1337620'>Now--</span> <span m='1341076'>and</span> <span
  m='1341470'>so</span> <span m='1341680'>one</span> <span m='1341830'>of</span>
  <span m='1341890'>the</span> <span m='1341980'>things</span> <span
  m='1342250'>that that</span> <span m='1342550'>says</span> <span
  m='1343010'>is</span> <span m='1343150'>that</span> <span
  m='1343540'>for</span> <span m='1344200'>the</span> <span
  m='1344290'>filter</span> <span m='1344680'>design,</span> <span
  m='1346330'>if</span> <span m='1347020'>we</span> <span
  m='1347170'>wanted</span> <span m='1347500'>to</span> <span
  m='1347650'>design</span> <span m='1349180'>an</span> <span
  m='1349330'>ideal</span> <span m='1351040'>digital</span> <span
  m='1351430'>filter,</span> <span m='1352540'>an</span> <span
  m='1352660'>ideal</span> <span m='1353140'>digital</span> <span
  m='1353530'>low</span> <span m='1353740'>pass</span> <span
  m='1354100'>filter,</span> <span m='1355330'>then</span> <span
  m='1355610'>to</span> <span m='1355780'>decide</span> <span
  m='1356290'>on</span> <span m='1356380'>the</span> <span
  m='1356470'>specifications</span> <span m='1357850'>for</span> <span
  m='1358300'>the</span> <span m='1358540'>ideal</span> <span
  m='1359140'>analog</span> <span m='1359710'>filter,</span> <span
  m='1360760'>we</span> <span m='1360880'>would</span> <span
  m='1361120'>simply</span> <span m='1361540'>pre-warp--</span> <span
  m='1362590'>what's</span> <span m='1362770'>called</span> <span
  m='1363080'>pre-warping--</span> <span m='1364390'>pre-warp</span> <span
  m='1365410'>the</span> <span m='1365500'>cutoff</span> <span
  m='1365920'>frequency</span> <span m='1367210'>to</span> <span
  m='1367630'>an</span> <span m='1367780'>analog</span> <span
  m='1368290'>cutoff</span> <span m='1368710'>frequency,</span> <span
  m='1369590'>which</span> <span m='1369760'>would</span> <span
  m='1369910'>get</span> <span m='1370120'>unraveled</span> <span
  m='1370780'>back</span> <span m='1371080'>to</span> <span
  m='1371200'>the</span> <span m='1371320'>right</span> <span
  m='1371560'>cutoff</span> <span m='1371950'>frequency</span> <span
  m='1373030'>when</span> <span m='1373240'>we</span> <span
  m='1373330'>go</span> <span m='1373540'>through</span> <span
  m='1374110'>the</span> <span m='1374800'>bilinear</span> <span
  m='1375310'>transformation.</span> <span m='1377410'>Now,</span> <span
  m='1377920'>we</span> <span m='1378040'>know</span> <span
  m='1378250'>that</span> <span m='1378400'>there</span> <span
  m='1378610'>aren't</span> <span m='1379600'>ideal</span> <span
  m='1380050'>filters.</span> <span m='1380700'>And</span> <span
  m='1381070'>so,</span> <span m='1381340'>in</span> <span
  m='1381430'>fact,</span> <span m='1382240'>we're,</span> <span m='1382660'>in
  general,</span> <span m='1383230'>faced</span> <span m='1383560'>with</span>
  <span m='1383680'>the</span> <span m='1383800'>problem</span> <span
  m='1384490'>of</span> <span m='1385390'>approximating</span> <span
  m='1386410'>a</span> <span m='1386500'>characteristic</span> <span
  m='1387310'>like</span> <span m='1387580'>that.</span> </p><p><span
  m='1388540'>But</span> <span m='1389320'>if</span> <span
  m='1389500'>the</span> <span m='1389590'>specifications</span> <span
  m='1390970'>for</span> <span m='1391120'>the</span> <span
  m='1391210'>filter</span> <span m='1391750'>are</span> <span
  m='1392350'>still</span> <span m='1393040'>piecewise</span> <span
  m='1393610'>constant,</span> <span m='1395050'>then,</span> <span
  m='1395500'>in</span> <span m='1395650'>fact,</span> <span
  m='1396410'>we</span> <span m='1396490'>can</span> <span
  m='1396700'>still</span> <span m='1398330'>concentrate</span> <span
  m='1399440'>just</span> <span m='1399710'>simply</span> <span
  m='1400370'>on</span> <span m='1400790'>a</span> <span
  m='1400850'>pre-warping</span> <span m='1401690'>of</span> <span
  m='1401870'>the</span> <span m='1401960'>critical</span> <span
  m='1402410'>frequencies.</span> <span m='1404060'>And</span> <span
  m='1404750'>the</span> <span m='1406130'>piecewise</span> <span
  m='1406700'>constant</span> <span m='1407960'>portions</span> <span
  m='1408560'>of</span> <span m='1408620'>the</span> <span
  m='1408740'>frequency</span> <span m='1409280'>response</span> <span
  m='1410150'>will</span> <span m='1410270'>then</span> <span
  m='1410480'>fall</span> <span m='1411050'>in</span> <span
  m='1411170'>the</span> <span m='1411260'>correct</span> <span
  m='1411590'>places.</span> <span m='1412490'>And</span> <span
  m='1412580'>let</span> <span m='1412700'>me</span> <span
  m='1412880'>illustrate</span> <span m='1413420'>that</span> <span
  m='1415070'>by</span> <span m='1416480'>showing</span> <span
  m='1416900'>a</span> <span m='1416960'>more</span> <span
  m='1417200'>realistic</span> <span m='1418130'>kind</span> <span
  m='1418400'>of</span> <span m='1418730'>filter</span> <span
  m='1419150'>frequency</span> <span m='1419720'>response.</span> <span
  m='1433250'>Well,</span> <span m='1433610'>that's</span> <span
  m='1434210'>pretty</span> <span m='1434420'>close.</span> <span
  m='1435740'>All</span> <span m='1435830'>right.</span> </p><p><span
  m='1436370'>Here</span> <span m='1437120'>we</span> <span
  m='1437360'>have</span> <span m='1438080'>what</span> <span
  m='1438440'>would</span> <span m='1438620'>be</span> <span
  m='1438800'>more</span> <span m='1439040'>typical</span> <span
  m='1439820'>of</span> <span m='1440660'>the</span> <span
  m='1441590'>digital</span> <span m='1442010'>filter</span> <span
  m='1442580'>that</span> <span m='1442880'>we</span> <span
  m='1443120'>would</span> <span m='1443600'>design</span> <span
  m='1444080'>and</span> <span m='1444200'>implement--</span> <span
  m='1445940'>some</span> <span m='1446420'>allowed</span> <span
  m='1446780'>tolerance</span> <span m='1447440'>in</span> <span
  m='1447530'>the</span> <span m='1447620'>passband,</span> <span
  m='1449070'>some</span> <span m='1449360'>allowed</span> <span
  m='1449690'>tolerance</span> <span m='1450290'>in</span> <span
  m='1450380'>the</span> <span m='1450470'>stopband,</span> <span
  m='1452020'>a</span> <span m='1452160'>passband</span> <span
  m='1453260'>cutoff</span> <span m='1453680'>frequency,</span> <span
  m='1454580'>and</span> <span m='1454700'>a</span> <span
  m='1454760'>stopband</span> <span m='1455360'>cutoff</span> <span
  m='1455720'>frequency.</span> <span m='1457680'>Well,</span> <span
  m='1458060'>if</span> <span m='1458270'>that</span> <span
  m='1458780'>was</span> <span m='1459170'>our</span> <span
  m='1459350'>desired</span> <span m='1459950'>digital</span> <span
  m='1460370'>filter,</span> <span m='1461900'>then</span> <span
  m='1462080'>how</span> <span m='1462290'>would</span> <span
  m='1462410'>those</span> <span m='1462650'>specifications</span> <span
  m='1463700'>translate</span> <span m='1464390'>to</span> <span
  m='1464540'>an</span> <span m='1464630'>analog</span> <span
  m='1465110'>filter?</span> <span m='1466500'>Well,</span> <span
  m='1467060'>if</span> <span m='1467480'>the</span> <span
  m='1467600'>deviation</span> <span m='1468680'>in</span> <span
  m='1469280'>the</span> <span m='1469580'>digital</span> <span
  m='1470030'>filter</span> <span m='1470780'>was</span> <span
  m='1471110'>between</span> <span m='1471560'>1</span> <span
  m='1472070'>and</span> <span m='1472220'>1</span> <span
  m='1472430'>minus</span> <span m='1472790'>delta</span> <span
  m='1473160'>sub</span> <span m='1473575'>p,</span> <span
  m='1474860'>then</span> <span m='1475370'>that</span> <span
  m='1475640'>would</span> <span m='1475820'>get</span> <span
  m='1476000'>converted</span> <span m='1476900'>into</span> <span
  m='1477620'>specifications</span> <span m='1478880'>on</span> <span
  m='1479000'>the</span> <span m='1479120'>analog</span> <span
  m='1479570'>filter,</span> <span m='1480050'>likewise</span> <span
  m='1480710'>between</span> <span m='1481100'>1</span> <span
  m='1481610'>and</span> <span m='1481730'>1</span> <span
  m='1481970'>minus</span> <span m='1482360'>delta</span> <span
  m='1482660'>sub</span> <span m='1482950'>p.</span> <span
  m='1484880'>The</span> <span m='1485210'>passband</span> <span
  m='1485900'>cutoff</span> <span m='1486440'>edge</span> <span
  m='1487400'>would</span> <span m='1487640'>get</span> <span
  m='1487820'>reflected</span> <span m='1488750'>through</span> <span
  m='1488960'>this</span> <span m='1489170'>nonlinear</span> <span
  m='1489800'>curve</span> <span m='1490840'>to</span> <span
  m='1491320'>a</span> <span m='1491390'>new</span> <span
  m='1491750'>analog</span> <span m='1492410'>cutoff</span> <span
  m='1492770'>frequency.</span> </p><p><span m='1494390'>Likewise,</span> <span
  m='1495320'>the</span> <span m='1495440'>transition</span> <span
  m='1496070'>region</span> <span m='1496820'>would</span> <span
  m='1497570'>get</span> <span m='1497720'>reflected</span> <span
  m='1498350'>into</span> <span m='1498740'>a</span> <span
  m='1498800'>new</span> <span m='1498980'>transition</span> <span
  m='1499610'>region.</span> <span m='1500780'>If</span> <span
  m='1501320'>this</span> <span m='1501590'>frequency</span> <span
  m='1502220'>characteristic</span> <span m='1503030'>was,</span> <span
  m='1503180'>let's</span> <span m='1503360'>say,</span> <span
  m='1503540'>linear</span> <span m='1503990'>in</span> <span
  m='1504080'>the</span> <span m='1504170'>transition</span> <span
  m='1504800'>region,</span> <span m='1505760'>of</span> <span
  m='1505880'>course,</span> <span m='1506210'>it</span> <span
  m='1506330'>wouldn't</span> <span m='1506660'>end</span> <span
  m='1506870'>up</span> <span m='1507050'>linear</span> <span
  m='1507980'>in</span> <span m='1508100'>this</span> <span
  m='1508250'>transition</span> <span m='1508790'>region.</span> <span
  m='1509120'>But</span> <span m='1509270'>who</span> <span
  m='1509420'>cares?</span> <span m='1511430'>The</span> <span
  m='1511520'>stopband</span> <span m='1512570'>edge</span> <span
  m='1513170'>would</span> <span m='1513320'>get</span> <span
  m='1513500'>reflected</span> <span m='1514160'>into</span> <span
  m='1514460'>a</span> <span m='1514520'>new</span> <span
  m='1514670'>stopband</span> <span m='1515360'>edge.</span> <span
  m='1516170'>And</span> <span m='1516290'>finally,</span> <span
  m='1517130'>the</span> <span m='1517400'>stopband</span> <span
  m='1518030'>specifications,</span> <span m='1519950'>let's</span> <span
  m='1520220'>say,</span> <span m='1520550'>delta</span> <span
  m='1520940'>sub</span> <span m='1521255'>s,</span> <span
  m='1521860'>would</span> <span m='1521990'>get</span> <span
  m='1522200'>mapped</span> <span m='1522740'>to</span> <span
  m='1523310'>the</span> <span m='1523430'>same</span> <span
  m='1523730'>stopband</span> <span m='1524270'>specifications,</span> <span
  m='1525200'>delta</span> <span m='1525510'>sub</span> <span
  m='1525810'>s.</span> </p><p><span m='1526710'>Furthermore,</span> <span
  m='1527480'>notice</span> <span m='1528620'>that</span> <span
  m='1529190'>if,</span> <span m='1529580'>let's</span> <span
  m='1529850'>say,</span> <span m='1530090'>we</span> <span
  m='1530270'>had</span> <span m='1530450'>an</span> <span
  m='1530570'>optimum</span> <span m='1531050'>filter</span> <span
  m='1531680'>which</span> <span m='1532100'>turns</span> <span
  m='1532430'>out</span> <span m='1532580'>to</span> <span m='1532700'>be</span>
  <span m='1532850'>equal</span> <span m='1533180'>ripple</span> <span
  m='1534200'>for</span> <span m='1534350'>the</span> <span
  m='1534470'>digital</span> <span m='1534860'>case,</span> <span
  m='1535850'>then</span> <span m='1536450'>that</span> <span
  m='1536660'>would</span> <span m='1536810'>correspond</span> <span
  m='1537710'>to</span> <span m='1539195'>an</span> <span
  m='1539450'>equal</span> <span m='1539750'>ripple</span> <span
  m='1540050'>filter</span> <span m='1540590'>in</span> <span
  m='1540740'>the</span> <span m='1540860'>analog</span> <span
  m='1541310'>case.</span> <span m='1542000'>Or</span> <span
  m='1542660'>said</span> <span m='1542930'>another</span> <span
  m='1543230'>way,</span> <span m='1543680'>if</span> <span
  m='1543950'>we</span> <span m='1544070'>were</span> <span
  m='1544250'>able</span> <span m='1544490'>to</span> <span
  m='1544640'>design</span> <span m='1545420'>an</span> <span
  m='1545540'>equal</span> <span m='1545810'>ripple</span> <span
  m='1546140'>analog</span> <span m='1546650'>filter,</span> <span
  m='1547690'>then</span> <span m='1547850'>map</span> <span
  m='1548160'>through</span> <span m='1548360'>the</span> <span
  m='1548450'>bilinear</span> <span m='1548960'>transformation,</span> <span
  m='1550040'>that</span> <span m='1550220'>would</span> <span
  m='1550370'>likewise</span> <span m='1550940'>result</span> <span
  m='1551810'>in</span> <span m='1552260'>an</span> <span
  m='1552410'>equal</span> <span m='1552710'>ripple</span> <span
  m='1553490'>digital</span> <span m='1553850'>filter.</span> <span
  m='1555480'>So</span> <span m='1555830'>the</span> <span
  m='1555950'>important</span> <span m='1556580'>point</span> <span
  m='1556910'>here</span> <span m='1557150'>then</span> <span
  m='1557570'>is</span> <span m='1557870'>that</span> <span
  m='1558620'>we</span> <span m='1558830'>can,</span> <span
  m='1561050'>for</span> <span m='1561380'>piecewise</span> <span
  m='1562040'>constant</span> <span m='1563000'>frequency</span> <span
  m='1563540'>characteristics</span> <span m='1565280'>and</span> <span
  m='1565400'>specifications,</span> <span m='1566930'>it</span> <span
  m='1567050'>really</span> <span m='1567380'>is</span> <span
  m='1567500'>only</span> <span m='1567740'>the</span> <span
  m='1567860'>critical</span> <span m='1568310'>frequencies</span> <span
  m='1569000'>that</span> <span m='1569120'>we</span> <span
  m='1569240'>care</span> <span m='1569510'>about,</span> <span
  m='1569810'>the</span> <span m='1569990'>edge</span> <span
  m='1570170'>of</span> <span m='1570230'>the</span> <span
  m='1570350'>passband,</span> <span m='1570980'>the</span> <span
  m='1571100'>edge</span> <span m='1571280'>of</span> <span
  m='1571340'>the</span> <span m='1571460'>stopband,</span> <span
  m='1572180'>and</span> <span m='1572300'>in the</span> <span
  m='1572540'>multiple</span> <span m='1573020'>band</span> <span
  m='1573290'>case,</span> <span m='1573590'>of</span> <span
  m='1573680'>course,</span> <span m='1573960'>there</span> <span
  m='1574090'>will</span> <span m='1574190'>be</span> <span m='1574460'>a</span>
  <span m='1574550'>number</span> <span m='1574880'>of</span> <span
  m='1575000'>those.</span> </p><p><span m='1575990'>By</span> <span
  m='1576200'>pre-warping</span> <span m='1576980'>those</span> <span
  m='1577760'>through</span> <span m='1578270'>this</span> <span
  m='1578570'>arctangent</span> <span m='1579320'>curve</span> <span
  m='1580670'>into</span> <span m='1581000'>the</span> <span
  m='1581120'>corresponding</span> <span m='1582440'>analog</span> <span
  m='1583670'>critical</span> <span m='1584090'>frequencies,</span> <span
  m='1585770'>if</span> <span m='1586280'>this</span> <span
  m='1586550'>filter</span> <span m='1586970'>is</span> <span
  m='1587090'>then</span> <span m='1587300'>designed</span> <span
  m='1588140'>and</span> <span m='1588350'>mapped</span> <span
  m='1588980'>to</span> <span m='1589130'>a</span> <span
  m='1589220'>digital</span> <span m='1589610'>filter,</span> <span
  m='1590600'>using</span> <span m='1590900'>the</span> <span
  m='1590990'>bilinear</span> <span m='1591560'>transformation,</span> <span
  m='1593060'>then</span> <span m='1593810'>the</span> <span
  m='1594040'>passband</span> <span m='1594710'>and</span> <span
  m='1594830'>stopband</span> <span m='1595400'>edges</span> <span
  m='1595910'>will</span> <span m='1596060'>fall</span> <span
  m='1596600'>at</span> <span m='1596690'>the</span> <span
  m='1596810'>frequencies</span> <span m='1597830'>that</span> <span
  m='1598100'>we</span> <span m='1598250'>want.</span> <span
  m='1599240'>And</span> <span m='1601190'>this</span> <span
  m='1601460'>point</span> <span m='1601790'>again</span> <span
  m='1602060'>will</span> <span m='1602180'>be</span> <span
  m='1602360'>emphasized</span> <span m='1603680'>in</span> <span
  m='1603800'>the</span> <span m='1603890'>next</span> <span
  m='1604160'>lecture,</span> <span m='1604950'>when</span> <span
  m='1605300'>I</span> <span m='1605420'>show</span> <span m='1610220'>a</span>
  <span m='1610250'>design</span> <span m='1610640'>example</span> <span
  m='1611210'>comparing</span> <span m='1611750'>impulse</span> <span
  m='1612170'>invariance</span> <span m='1612770'>in</span> <span
  m='1612860'>the</span> <span m='1612920'>bilinear</span> <span
  m='1613430'>transformation.</span> <span m='1615060'>So</span> <span
  m='1615980'>the</span> <span m='1616340'>key</span> <span
  m='1616610'>point</span> <span m='1617000'>then</span> <span
  m='1617450'>about</span> <span m='1618950'>the</span> <span
  m='1619040'>bilinear</span> <span m='1619490'>transformation</span> <span
  m='1621110'>is</span> <span m='1621320'>that</span> <span
  m='1621650'>it</span> <span m='1621800'>avoids</span> <span
  m='1622250'>the</span> <span m='1622340'>problem</span> <span
  m='1622790'>of</span> <span m='1622880'>aliasing</span> <span
  m='1624140'>at</span> <span m='1624260'>a</span> <span
  m='1624320'>price.</span> <span m='1625460'>The</span> <span
  m='1625550'>price</span> <span m='1625970'>is</span> <span
  m='1626360'>that</span> <span m='1626510'>there's</span> <span
  m='1626720'>a</span> <span m='1626780'>distortion</span> <span
  m='1627380'>in</span> <span m='1627470'>the</span> <span
  m='1627560'>frequency</span> <span m='1628130'>axis.</span> <span
  m='1629090'>And</span> <span m='1629270'>so</span> <span
  m='1629930'>consequently,</span> <span m='1630800'>we</span> <span
  m='1630920'>can</span> <span m='1631070'>only</span> <span
  m='1631340'>use</span> <span m='1631610'>the</span> <span
  m='1631700'>bilinear</span> <span m='1632210'>transformation</span> <span
  m='1633650'>to</span> <span m='1633770'>design</span> <span
  m='1634280'>filters</span> <span m='1634910'>that</span> <span
  m='1635060'>can</span> <span m='1635210'>tolerate</span> <span
  m='1635750'>that</span> <span m='1635960'>distortion.</span> <span
  m='1637460'>Typically,</span> <span m='1638510'>that</span> <span
  m='1638900'>means</span> <span m='1639420'>designing</span> <span
  m='1640280'>piecewise</span> <span m='1640820'>constant</span> <span
  m='1641330'>digital</span> <span m='1641660'>filters.</span> </p><p><span
  m='1644550'>All</span> <span m='1644640'>right.</span> <span
  m='1644910'>Well,</span> <span m='1645840'>that</span> <span
  m='1646800'>basically</span> <span m='1648720'>concludes</span> <span
  m='1649530'>the</span> <span m='1649680'>discussion</span> <span
  m='1650610'>of</span> <span m='1651570'>the</span> <span
  m='1651750'>design</span> <span m='1652260'>techniques</span> <span
  m='1653550'>that</span> <span m='1653700'>correspond</span> <span
  m='1654840'>to</span> <span m='1655020'>mapping</span> <span
  m='1656160'>analog</span> <span m='1656940'>filter</span> <span
  m='1657330'>designs</span> <span m='1658080'>to</span> <span
  m='1658230'>digital</span> <span m='1658590'>filter</span> <span
  m='1658950'>designs.</span> <span m='1661110'>There</span> <span
  m='1661560'>is</span> <span m='1662190'>one</span> <span
  m='1663060'>final</span> <span m='1663450'>class</span> <span
  m='1663810'>of</span> <span m='1663900'>techniques</span> <span
  m='1664590'>that</span> <span m='1664920'>I</span> <span
  m='1665040'>would</span> <span m='1665220'>like</span> <span
  m='1665700'>to</span> <span m='1666570'>just</span> <span
  m='1666930'>comment</span> <span m='1667440'>on</span> <span
  m='1667830'>somewhat</span> <span m='1668250'>briefly.</span> <span
  m='1669450'>And</span> <span m='1670170'>that</span> <span
  m='1670440'>is</span> <span m='1671190'>the</span> <span
  m='1671460'>class</span> <span m='1671820'>of</span> <span
  m='1671940'>techniques</span> <span m='1672540'>that</span> <span
  m='1672660'>correspond</span> <span m='1673380'>to</span> <span
  m='1673680'>algorithmic</span> <span m='1674400'>design.</span> </p><p><span
  m='1675780'>Now,</span> <span m='1677010'>there</span> <span
  m='1677370'>are</span> <span m='1678330'>algorithmic</span> <span
  m='1678960'>design</span> <span m='1679350'>procedures</span> <span
  m='1680730'>for</span> <span m='1681180'>analog</span> <span
  m='1681750'>filters.</span> <span m='1682690'>And</span> <span
  m='1683280'>the</span> <span m='1683370'>same</span> <span
  m='1684960'>algorithmic</span> <span m='1685860'>procedures</span> <span
  m='1686970'>can</span> <span m='1687150'>likewise</span> <span
  m='1687720'>be</span> <span m='1687870'>used</span> <span
  m='1688110'>for</span> <span m='1688260'>digital</span> <span
  m='1688650'>filters.</span> <span m='1689760'>Since</span> <span
  m='1690180'>we</span> <span m='1690390'>have</span> <span
  m='1690600'>to</span> <span m='1690720'>go</span> <span
  m='1690960'>through</span> <span m='1691200'>an</span> <span
  m='1691290'>algorithmic</span> <span m='1691890'>procedure--</span> <span
  m='1692770'>in</span> <span m='1692790'>fact,</span> <span
  m='1693630'>there</span> <span m='1693740'>is</span> <span
  m='1693900'>no</span> <span m='1694650'>advantage,</span> <span
  m='1695490'>in</span> <span m='1695640'>that</span> <span
  m='1695850'>case,</span> <span m='1696830'>to</span> <span
  m='1696960'>first</span> <span m='1697350'>designing</span> <span
  m='1697890'>the</span> <span m='1698010'>analog</span> <span
  m='1698490'>filter</span> <span m='1699330'>and</span> <span
  m='1699450'>then</span> <span m='1699840'>mapping</span> <span
  m='1700230'>that</span> <span m='1700410'>over</span> <span
  m='1700650'>to</span> <span m='1700770'>the</span> <span
  m='1700890'>digital</span> <span m='1701280'>filter.</span> <span
  m='1702150'>Rather,</span> <span m='1702480'>for</span> <span
  m='1702630'>these</span> <span m='1702840'>algorithmic</span> <span
  m='1703410'>techniques,</span> <span m='1704650'>it</span> <span
  m='1704670'>makes</span> <span m='1704940'>more</span> <span
  m='1705180'>sense</span> <span m='1706050'>to</span> <span
  m='1706170'>just</span> <span m='1706380'>simply</span> <span
  m='1706950'>apply</span> <span m='1707340'>them</span> <span
  m='1707490'>directly</span> <span m='1708390'>to</span> <span
  m='1708510'>the</span> <span m='1708630'>design</span> <span
  m='1709050'>of</span> <span m='1709140'>a</span> <span
  m='1709200'>digital</span> <span m='1709560'>filter.</span> </p><p><span
  m='1711460'>Well,</span> <span m='1711810'>there</span> <span
  m='1712140'>are</span> <span m='1712380'>a</span> <span
  m='1712410'>number</span> <span m='1712710'>of</span> <span
  m='1712800'>techniques,</span> <span m='1713400'>actually</span> <span
  m='1714030'>a</span> <span m='1714090'>fairly</span> <span
  m='1714450'>long</span> <span m='1714750'>list,</span> <span
  m='1716070'>many</span> <span m='1716400'>of</span> <span
  m='1716520'>them</span> <span m='1717330'>simple</span> <span
  m='1717990'>modifications</span> <span m='1718890'>of</span> <span
  m='1719010'>others.</span> <span m='1719940'>There</span> <span
  m='1720300'>are</span> <span m='1720540'>only</span> <span
  m='1720840'>two</span> <span m='1721110'>that</span> <span
  m='1721260'>I</span> <span m='1721380'>want</span> <span m='1721920'>to</span>
  <span m='1722430'>point</span> <span m='1722730'>to</span> <span
  m='1723150'>in</span> <span m='1723300'>this</span> <span
  m='1723510'>lecture.</span> <span m='1724650'>When</span> <span
  m='1724980'>we</span> <span m='1725160'>talk</span> <span
  m='1725460'>about</span> <span m='1725700'>the</span> <span
  m='1725820'>design</span> <span m='1726210'>of</span> <span
  m='1726270'>finite</span> <span m='1726690'>impulse</span> <span
  m='1727080'>response</span> <span m='1727590'>filters,</span> <span
  m='1728490'>there</span> <span m='1728820'>are</span> <span
  m='1729000'>some</span> <span m='1729180'>additional</span> <span
  m='1729600'>algorithmic</span> <span m='1730800'>design</span> <span
  m='1731190'>procedures</span> <span m='1731910'>that</span> <span
  m='1732270'>we'll</span> <span m='1732510'>point</span> <span
  m='1732810'>to.</span> </p><p><span m='1734400'>Well,</span> <span
  m='1734910'>the</span> <span m='1735030'>first</span> <span
  m='1735630'>algorithmic</span> <span m='1736290'>design</span> <span
  m='1736710'>procedure,</span> <span m='1737910'>which</span> <span
  m='1738880'>I</span> <span m='1739150'>am</span> <span
  m='1739470'>restricting,</span> <span m='1740310'>in</span> <span
  m='1740430'>my</span> <span m='1740610'>discussion</span> <span
  m='1741450'>here,</span> <span m='1741930'>to</span> <span
  m='1742170'>the</span> <span m='1742290'>design</span> <span
  m='1742680'>of</span> <span m='1742770'>infinite</span> <span
  m='1743160'>impulse</span> <span m='1743580'>response</span> <span
  m='1744650'>filters,</span> <span m='1746260'>the</span> <span
  m='1746280'>first</span> <span m='1746880'>is</span> <span
  m='1747870'>simply</span> <span m='1748860'>designing</span> <span
  m='1749430'>the</span> <span m='1749520'>filter</span> <span
  m='1750630'>to</span> <span m='1750750'>minimize</span> <span
  m='1751650'>the</span> <span m='1751770'>mean</span> <span
  m='1752010'>square</span> <span m='1752440'>error</span> <span
  m='1753210'>between</span> <span m='1754080'>the</span> <span
  m='1754260'>desired</span> <span m='1754800'>frequency</span> <span
  m='1755400'>characteristic,</span> <span m='1756300'>the</span> <span
  m='1756450'>desired</span> <span m='1756900'>frequency</span> <span
  m='1757410'>response,</span> <span m='1758550'>and</span> <span
  m='1759300'>the</span> <span m='1759600'>actual</span> <span
  m='1760080'>frequency</span> <span m='1760590'>response.</span> <span
  m='1762340'>So</span> <span m='1763200'>let's</span> <span
  m='1763410'>assume</span> <span m='1763830'>that</span> <span
  m='1763950'>we</span> <span m='1764100'>have</span> <span
  m='1764400'>some</span> <span m='1764640'>desired</span> <span
  m='1765150'>frequency</span> <span m='1765690'>response,</span> <span
  m='1766360'>H sub</span> <span m='1766715'>d</span> <span
  m='1767070'>of</span> <span m='1767270'>e to</span> <span
  m='1767410'>the</span> <span m='1767520'>j</span> <span
  m='1767720'>omega.</span> <span m='1769080'>We</span> <span
  m='1769290'>would</span> <span m='1769440'>like</span> <span
  m='1769830'>to</span> <span m='1769980'>match</span> <span
  m='1770400'>that</span> <span m='1770970'>with</span> <span
  m='1772170'>the</span> <span m='1772500'>frequency</span> <span
  m='1773070'>response</span> <span m='1773880'>of</span> <span
  m='1774810'>the</span> <span m='1775800'>rational</span> <span
  m='1776310'>transfer</span> <span m='1776850'>function.</span> </p><p><span
  m='1779100'>It,</span> <span m='1779490'>of</span> <span
  m='1779640'>course,</span> <span m='1781230'>isn't</span> <span
  m='1781530'>possible</span> <span m='1782520'>to</span> <span
  m='1783000'>attempt</span> <span m='1783360'>to</span> <span
  m='1783480'>do</span> <span m='1783690'>that</span> <span
  m='1784230'>at</span> <span m='1784580'>an</span> <span
  m='1784740'>arbitrary</span> <span m='1785370'>number</span> <span
  m='1785700'>of</span> <span m='1785790'>frequencies.</span> <span
  m='1787180'>So</span> <span m='1787680'>we</span> <span m='1787950'>can</span>
  <span m='1788940'>pick</span> <span m='1789210'>out</span> <span
  m='1790110'>some</span> <span m='1790470'>set</span> <span
  m='1790710'>of</span> <span m='1790800'>frequencies,</span> <span
  m='1791670'>omega</span> <span m='1792100'>sub</span> <span
  m='1792450'>i,</span> <span m='1793250'>at</span> <span
  m='1793470'>which</span> <span m='1793950'>we</span> <span
  m='1794190'>would</span> <span m='1794760'>like</span> <span
  m='1795540'>to</span> <span m='1795660'>minimize</span> <span
  m='1796710'>the</span> <span m='1796890'>error</span> <span
  m='1797430'>between</span> <span m='1798000'>the</span> <span
  m='1798090'>desired</span> <span m='1798990'>frequency</span> <span
  m='1799530'>response</span> <span m='1800550'>and</span> <span
  m='1800670'>the</span> <span m='1800790'>actual</span> <span
  m='1801210'>frequency</span> <span m='1801690'>response.</span> <span
  m='1804100'>The</span> <span m='1804280'>error,</span> <span
  m='1804760'>then,</span> <span m='1805810'>which</span> <span
  m='1806230'>we'll</span> <span m='1806440'>be</span> <span
  m='1806590'>using,</span> <span m='1807310'>or</span> <span
  m='1807870'>one</span> <span m='1808110'>error</span> <span
  m='1808380'>which</span> <span m='1808600'>is</span> <span
  m='1808750'>used,</span> <span m='1809380'>is</span> <span
  m='1809890'>the</span> <span m='1810070'>error</span> <span
  m='1810240'>that</span> <span m='1810340'>corresponds</span> <span
  m='1810970'>to</span> <span m='1811060'>minimization</span> <span
  m='1811660'>of</span> <span m='1811720'>the</span> <span
  m='1811810'>mean</span> <span m='1812020'>square</span> <span
  m='1812380'>error</span> <span m='1813310'>is</span> <span
  m='1813940'>the</span> <span m='1814030'>mean</span> <span
  m='1814270'>square</span> <span m='1814650'>difference</span> <span
  m='1815710'>between</span> <span m='1816730'>the</span> <span
  m='1816820'>magnitude</span> <span m='1818320'>of</span> <span
  m='1818950'>the</span> <span m='1819130'>actual</span> <span
  m='1819640'>transfer</span> <span m='1820150'>function</span> <span
  m='1821410'>and</span> <span m='1822130'>the</span> <span
  m='1822220'>magnitude</span> <span m='1823150'>of</span> <span
  m='1823720'>the</span> <span m='1823840'>desired</span> <span
  m='1824920'>transfer</span> <span m='1825400'>function.</span> </p><p><span
  m='1826670'>So</span> <span m='1827410'>this</span> <span
  m='1827740'>error,</span> <span m='1828220'>then,</span> <span
  m='1828610'>summed</span> <span m='1829120'>over</span> <span
  m='1829540'>the</span> <span m='1829660'>frequency</span> <span
  m='1830230'>points</span> <span m='1831220'>at</span> <span
  m='1831340'>which</span> <span m='1831880'>we</span> <span
  m='1832000'>specify</span> <span m='1833080'>the</span> <span
  m='1833170'>desired</span> <span m='1833650'>frequency</span> <span
  m='1834190'>response,</span> <span m='1835840'>this</span> <span
  m='1836080'>error,</span> <span m='1836740'>m</span> <span
  m='1837160'>is</span> <span m='1837310'>to</span> <span m='1837430'>be</span>
  <span m='1837550'>minimized.</span> <span m='1839320'>Well,</span> <span
  m='1840010'>how</span> <span m='1840220'>do</span> <span m='1840310'>we</span>
  <span m='1840490'>pick</span> <span m='1841330'>H?</span> <span
  m='1842260'>Well,</span> <span m='1842440'>the</span> <span
  m='1842560'>general</span> <span m='1842950'>form</span> <span
  m='1843270'>for</span> <span m='1843520'>H</span> <span m='1844420'>is</span>
  <span m='1845110'>as</span> <span m='1845650'>a</span> <span
  m='1845740'>rational</span> <span m='1846550'>function--</span> <span
  m='1847190'>that's</span> <span m='1847600'>what</span> <span
  m='1848050'>we've</span> <span m='1848260'>been</span> <span
  m='1848410'>restricting</span> <span m='1848890'>ourselves</span> <span
  m='1849370'>to</span> <span m='1849640'>throughout</span> <span
  m='1850030'>the</span> <span m='1850120'>discussion--</span> <span
  m='1851560'>the</span> <span m='1851680'>rational</span> <span
  m='1852340'>function</span> <span m='1852820'>of</span> <span
  m='1852910'>z,</span> <span m='1854860'>and</span> <span
  m='1855430'>expressed,</span> <span m='1856000'>for</span> <span
  m='1856180'>example,</span> <span m='1856660'>in</span> <span
  m='1856780'>cascade</span> <span m='1857410'>form,</span> <span
  m='1858610'>involving</span> <span m='1859240'>second</span> <span
  m='1859660'>order</span> <span m='1859900'>sections,</span> <span
  m='1860830'>that</span> <span m='1861040'>is,</span> <span
  m='1862600'>two</span> <span m='1862810'>coefficients</span> <span
  m='1863500'>for the</span> <span m='1863650'>0s</span> <span
  m='1864760'>and</span> <span m='1864880'>two</span> <span
  m='1865060'>coefficients</span> <span m='1865750'>for</span> <span
  m='1865870'>the</span> <span m='1865960'>poles,</span> <span
  m='1867070'>with</span> <span m='1867700'>capital</span> <span
  m='1868180'>K</span> <span m='1868660'>sections</span> <span
  m='1869290'>all</span> <span m='1869460'>together.</span> </p><p><span
  m='1871240'>So</span> <span m='1871600'>basically</span> <span
  m='1872200'>what</span> <span m='1872350'>the</span> <span
  m='1872440'>procedure</span> <span m='1873190'>then</span> <span
  m='1873430'>consists</span> <span m='1873970'>of--</span> <span
  m='1874210'>it's</span> <span m='1874320'>somewhat</span> <span
  m='1874960'>brute</span> <span m='1875170'>force--</span> <span
  m='1876370'>is</span> <span m='1877090'>to</span> <span
  m='1877210'>specify</span> <span m='1878260'>the</span> <span
  m='1878440'>order</span> <span m='1878740'>of</span> <span
  m='1878830'>the</span> <span m='1878950'>filter.</span> <span
  m='1880720'>We</span> <span m='1880840'>then</span> <span
  m='1881080'>have</span> <span m='1881710'>a</span> <span
  m='1881770'>set</span> <span m='1882010'>of</span> <span
  m='1882100'>coefficients</span> <span m='1883240'>which</span> <span
  m='1883510'>we</span> <span m='1883660'>need</span> <span
  m='1883870'>to</span> <span m='1883990'>solve</span> <span
  m='1884350'>for.</span> <span m='1886030'>We</span> <span
  m='1886270'>have</span> <span m='1886750'>a</span> <span
  m='1886840'>set</span> <span m='1887110'>of</span> <span
  m='1887200'>equations</span> <span m='1890360'>which</span> <span
  m='1890890'>result</span> <span m='1891670'>from</span> <span
  m='1892780'>minimizing</span> <span m='1894130'>this</span> <span
  m='1894700'>error</span> <span m='1895000'>function.</span> <span
  m='1896960'>And</span> <span m='1897440'>by</span> <span
  m='1897650'>solving</span> <span m='1898130'>that</span> <span
  m='1898310'>set</span> <span m='1898520'>of</span> <span
  m='1898580'>equations,</span> <span m='1900050'>by</span> <span
  m='1900230'>minimizing</span> <span m='1901490'>this</span> <span
  m='1901730'>error,</span> <span m='1904930'>what</span> <span
  m='1905170'>results</span> <span m='1905710'>then</span> <span
  m='1906130'>are</span> <span m='1906370'>values</span> <span
  m='1906880'>for</span> <span m='1907000'>the</span> <span
  m='1907120'>parameters,</span> <span m='1907990'>which</span> <span
  m='1908350'>provide</span> <span m='1909430'>the</span> <span
  m='1909520'>parameters</span> <span m='1910180'>for</span> <span
  m='1910270'>the</span> <span m='1910390'>filter</span> <span
  m='1910750'>that</span> <span m='1910870'>we</span> <span
  m='1910990'>want</span> <span m='1911170'>to</span> <span
  m='1911230'>implement.</span> </p><p><span m='1913520'>Well,</span> <span
  m='1914030'>one</span> <span m='1914270'>of</span> <span
  m='1914390'>the</span> <span m='1915050'>issues</span> <span
  m='1915860'>with</span> <span m='1916070'>this</span> <span
  m='1916460'>method,</span> <span m='1917060'>one</span> <span
  m='1917270'>of</span> <span m='1917360'>the</span> <span
  m='1917450'>difficulties</span> <span m='1918170'>with</span> <span
  m='1918380'>it,</span> <span m='1918650'>of</span> <span
  m='1918800'>course,</span> <span m='1919860'>is</span> <span
  m='1920060'>that--</span> <span m='1920600'>and</span> <span
  m='1920930'>you</span> <span m='1921110'>can</span> <span
  m='1921230'>kind</span> <span m='1921440'>of</span> <span
  m='1921500'>imagine</span> <span m='1922040'>that</span> <span
  m='1922160'>this</span> <span m='1922340'>is</span> <span
  m='1922460'>what's</span> <span m='1922670'>going</span> <span
  m='1922820'>to</span> <span m='1922880'>happen--</span> <span
  m='1924020'>is</span> <span m='1924200'>that,</span> <span
  m='1924680'>if</span> <span m='1925250'>you</span> <span
  m='1925640'>take</span> <span m='1926600'>this</span> <span
  m='1926810'>rational</span> <span m='1927350'>function</span> <span
  m='1929570'>and</span> <span m='1929870'>put</span> <span
  m='1930110'>it</span> <span m='1930380'>into</span> <span
  m='1930680'>this</span> <span m='1930920'>equation</span> <span
  m='1932180'>and</span> <span m='1932330'>minimize</span> <span
  m='1932840'>this</span> <span m='1933080'>error,</span> <span
  m='1934430'>you</span> <span m='1934590'>end</span> <span
  m='1934790'>up</span> <span m='1934940'>with</span> <span m='1935060'>a</span>
  <span m='1935120'>set</span> <span m='1935330'>of</span> <span
  m='1935390'>equations</span> <span m='1936020'>for</span> <span
  m='1936110'>the</span> <span m='1936230'>a</span> <span m='1936450'>sub</span>
  <span m='1936560'>k's,</span> <span m='1936900'>b sub</span> <span
  m='1937280'>k,</span> <span m='1937670'>c</span> <span m='1937880'>sub</span>
  <span m='1937970'>k,</span> <span m='1938180'>and</span> <span m='1938310'>d
  sub</span> <span m='1938650'>k,</span> <span m='1939500'>but</span> <span
  m='1939670'>it's</span> <span m='1940220'>a</span> <span
  m='1940280'>set</span> <span m='1940670'>of</span> <span
  m='1940820'>nonlinear</span> <span m='1941450'>equations.</span> <span
  m='1942870'>And</span> <span m='1942920'>basically</span> <span
  m='1943610'>what</span> <span m='1943790'>the</span> <span
  m='1943970'>algorithmic</span> <span m='1944600'>part</span> <span
  m='1944990'>of</span> <span m='1945140'>this</span> <span
  m='1945320'>design</span> <span m='1945740'>procedure</span> <span
  m='1946550'>amounts</span> <span m='1947030'>to</span> <span
  m='1947900'>is</span> <span m='1948260'>algorithmically</span> <span
  m='1949640'>solving</span> <span m='1950600'>this</span> <span
  m='1950780'>nonlinear</span> <span m='1951350'>set</span> <span
  m='1951560'>of</span> <span m='1951650'>equations.</span> </p><p><span
  m='1953910'>Well,</span> <span m='1954170'>let</span> <span
  m='1954350'>me</span> <span m='1954530'>just</span> <span
  m='1955010'>illustrate,</span> <span m='1955640'>with</span> <span
  m='1956030'>one</span> <span m='1956570'>simple</span> <span
  m='1956990'>example,</span> <span m='1958160'>how</span> <span
  m='1960370'>this</span> <span m='1960770'>procedure--</span> <span
  m='1961580'>what</span> <span m='1962030'>type</span> <span
  m='1962300'>of</span> <span m='1962360'>filter</span> <span
  m='1962750'>this</span> <span m='1962930'>procedure</span> <span
  m='1963710'>might</span> <span m='1963950'>lead</span> <span
  m='1964190'>to.</span> <span m='1964580'>I</span> <span
  m='1964700'>don't</span> <span m='1965390'>want</span> <span
  m='1965570'>to,</span> <span m='1965810'>obviously,</span> <span
  m='1966290'>go</span> <span m='1966470'>through</span> <span
  m='1966680'>all</span> <span m='1966830'>the</span> <span
  m='1966950'>details</span> <span m='1967730'>of</span> <span
  m='1968060'>solving</span> <span m='1968540'>the</span> <span
  m='1968660'>equations.</span> <span m='1969780'>But</span> <span
  m='1969830'>let's</span> <span m='1970010'>just</span> <span
  m='1970220'>quickly</span> <span m='1970610'>look</span> <span
  m='1970820'>at</span> <span m='1970910'>an</span> <span
  m='1971030'>example.</span> <span m='1973650'>This</span> <span
  m='1973850'>is</span> <span m='1974030'>an</span> <span
  m='1974120'>example</span> <span m='1974990'>incidentally</span> <span
  m='1975740'>that</span> <span m='1977540'>is</span> <span
  m='1977780'>taken</span> <span m='1978200'>from</span> <span
  m='1978800'>a</span> <span m='1978890'>paper</span> <span
  m='1979730'>by</span> <span m='1980300'>Professor</span> <span
  m='1980780'>Kenneth</span> <span m='1981080'>Steiglitz,</span> <span
  m='1981800'>at</span> <span m='1981890'>Princeton</span> <span
  m='1982340'>University.</span> </p><p><span m='1983870'>And</span> <span
  m='1984560'>the</span> <span m='1984680'>objective</span> <span
  m='1985250'>here</span> <span m='1985640'>was</span> <span
  m='1985940'>to</span> <span m='1986090'>design</span> <span
  m='1986600'>what's</span> <span m='1986810'>called</span> <span
  m='1987650'>a</span> <span m='1987710'>format</span> <span
  m='1988280'>filter,</span> <span m='1988790'>which</span> <span
  m='1989000'>is</span> <span m='1989120'>used</span> <span
  m='1989450'>for</span> <span m='1989570'>speech</span> <span
  m='1989870'>synthesis.</span> <span m='1991610'>And</span> <span
  m='1992660'>the</span> <span m='1992960'>frequency</span> <span
  m='1993650'>characteristic--</span> <span m='1995990'>the</span> <span
  m='1996290'>aspects</span> <span m='1996770'>of</span> <span
  m='1996860'>the</span> <span m='1996950'>frequency</span> <span
  m='1997400'>characteristic</span> <span m='1998120'>that</span> <span
  m='1998240'>were</span> <span m='1998450'>important</span> <span
  m='1999610'>were</span> <span m='1999920'>to</span> <span
  m='2000100'>have</span> <span m='2000730'>peaks</span> <span
  m='2001780'>at</span> <span m='2002560'>this</span> <span
  m='2002800'>frequency</span> <span m='2003640'>and</span> <span
  m='2003790'>this</span> <span m='2003970'>frequency</span> <span
  m='2004870'>and</span> <span m='2005020'>this</span> <span
  m='2005230'>frequency--</span> <span m='2006640'>those</span> <span
  m='2006880'>are</span> <span m='2006940'>the</span> <span
  m='2007060'>peaks</span> <span m='2007360'>that,</span> <span
  m='2007540'>incidentally,</span> <span m='2008080'>correspond</span> <span
  m='2008740'>to</span> <span m='2008830'>the</span> <span
  m='2008950'>resonances</span> <span m='2009550'>of</span> <span
  m='2009610'>the</span> <span m='2009730'>vocal</span> <span
  m='2010090'>tract--</span> <span m='2011140'>and</span> <span
  m='2011500'>to</span> <span m='2011650'>have</span> <span
  m='2012370'>valleys</span> <span m='2013450'>in between</span> <span
  m='2014020'>those</span> <span m='2014290'>peaks.</span> <span
  m='2015580'>Well,</span> <span m='2016180'>one</span> <span
  m='2016420'>of</span> <span m='2016510'>the</span> <span
  m='2016600'>things</span> <span m='2016990'>that</span> <span
  m='2017140'>you</span> <span m='2017260'>can</span> <span
  m='2017380'>see</span> <span m='2017710'>from</span> <span
  m='2018160'>the</span> <span m='2018280'>kind</span> <span
  m='2018490'>of</span> <span m='2018580'>filter</span> <span
  m='2019360'>that</span> <span m='2019570'>we're</span> <span
  m='2019720'>talking</span> <span m='2020140'>about</span> <span
  m='2020410'>designing</span> <span m='2020980'>here</span> <span
  m='2022390'>is</span> <span m='2022660'>that</span> <span
  m='2023410'>this</span> <span m='2024220'>isn't</span> <span
  m='2024490'>piecewise</span> <span m='2025090'>constant.</span> <span
  m='2026750'>And</span> <span m='2027130'>in</span> <span
  m='2027250'>fact,</span> <span m='2027710'>it's</span> <span
  m='2027730'>not</span> <span m='2027990'>band-limited.</span> <span
  m='2029410'>And</span> <span m='2029920'>it</span> <span
  m='2030460'>tends</span> <span m='2030760'>to</span> <span
  m='2030910'>have--</span> <span m='2031240'>it's</span> <span
  m='2031390'>not</span> <span m='2031600'>arbitrary,</span> <span
  m='2032200'>of</span> <span m='2032320'>course,</span> <span
  m='2032770'>but</span> <span m='2033040'>it's</span> <span
  m='2033220'>a</span> <span m='2033250'>much</span> <span
  m='2033520'>more</span> <span m='2033700'>general</span> <span
  m='2035020'>frequency</span> <span m='2035860'>characteristic</span> <span
  m='2036700'>shape</span> <span m='2037600'>than</span> <span
  m='2038110'>we</span> <span m='2038320'>had</span> <span
  m='2038590'>been</span> <span m='2038740'>talking</span> <span
  m='2039190'>about</span> <span m='2039790'>in</span> <span
  m='2040180'>discussing</span> <span m='2040990'>the</span> <span
  m='2041080'>previous</span> <span m='2041560'>methods,</span> <span
  m='2041980'>in</span> <span m='2042070'>particular,</span> <span
  m='2043270'>than</span> <span m='2043450'>we</span> <span
  m='2043570'>had</span> <span m='2043730'>been</span> <span
  m='2043870'>talking</span> <span m='2044290'>about</span> <span
  m='2044710'>in</span> <span m='2044860'>discussing</span> <span
  m='2045400'>the</span> <span m='2045550'>bilinear</span> <span
  m='2045960'>transformation.</span> </p><p><span m='2048310'>Well,</span> <span
  m='2048820'>the</span> <span m='2048940'>procedure</span> <span
  m='2049480'>that</span> <span m='2049810'>was</span> <span
  m='2050020'>used,</span> <span m='2050350'>then,</span> <span
  m='2050920'>was</span> <span m='2052030'>to</span> <span
  m='2052150'>specify</span> <span m='2053210'>the</span> <span
  m='2054310'>values</span> <span m='2055090'>of</span> <span
  m='2055270'>the</span> <span m='2055389'>desired</span> <span
  m='2055900'>frequency</span> <span m='2056469'>response</span> <span
  m='2057760'>and</span> <span m='2057880'>to</span> <span
  m='2058000'>try</span> <span m='2058210'>to</span> <span
  m='2058300'>specify</span> <span m='2058960'>them</span> <span
  m='2059139'>in</span> <span m='2059230'>such</span> <span m='2059530'>a</span>
  <span m='2059620'>way</span> <span m='2060100'>that</span> <span
  m='2060850'>the</span> <span m='2061210'>frequency</span> <span
  m='2061840'>characteristic</span> <span m='2062710'>was</span> <span
  m='2062860'>more</span> <span m='2063100'>or</span> <span
  m='2063159'>less</span> <span m='2063820'>forced</span> <span
  m='2064719'>to</span> <span m='2064810'>go</span> <span
  m='2065080'>through</span> <span m='2066219'>the</span> <span
  m='2066699'>proper</span> <span m='2067120'>values</span> <span
  m='2067929'>at</span> <span m='2068199'>the</span> <span
  m='2068290'>important</span> <span m='2068710'>frequencies.</span> <span
  m='2069980'>So</span> <span m='2070090'>what</span> <span
  m='2070239'>was</span> <span m='2070389'>specified,</span> <span
  m='2071360'>then,</span> <span m='2071650'>was</span> <span
  m='2071889'>a</span> <span m='2071949'>point</span> <span
  m='2072280'>here.</span> <span m='2072940'>The</span> <span
  m='2073030'>frequency</span> <span m='2073480'>response</span> <span
  m='2073960'>was</span> <span m='2074050'>specified</span> <span
  m='2074620'>to</span> <span m='2074730'>have</span> <span
  m='2074860'>that</span> <span m='2075100'>value</span> <span
  m='2075520'>there,</span> <span m='2076600'>one</span> <span
  m='2076870'>here</span> <span m='2077739'>to</span> <span
  m='2078429'>get</span> <span m='2078670'>us</span> <span
  m='2078790'>heading</span> <span m='2079090'>toward</span> <span
  m='2079330'>the</span> <span m='2079449'>resonance,</span> <span
  m='2080650'>three</span> <span m='2080889'>points</span> <span
  m='2081639'>at</span> <span m='2082060'>the</span> <span
  m='2082179'>peak</span> <span m='2082420'>of</span> <span
  m='2082480'>the</span> <span m='2082570'>resonance</span> <span
  m='2083830'>there,</span> <span m='2085540'>three</span> <span
  m='2085810'>points</span> <span m='2086250'>to</span> <span
  m='2086380'>force</span> <span m='2087010'>the</span> <span
  m='2087100'>frequency</span> <span m='2087580'>response</span> <span
  m='2088090'>back</span> <span m='2088389'>down</span> <span
  m='2088690'>again,</span> <span m='2089770'>another</span> <span
  m='2090130'>three</span> <span m='2090400'>to</span> <span
  m='2090520'>bring</span> <span m='2090760'>it</span> <span
  m='2090850'>back</span> <span m='2091150'>up</span> <span
  m='2091270'>for</span> <span m='2091389'>the</span> <span
  m='2091480'>second</span> <span m='2091870'>resonance,</span> <span
  m='2093190'>a</span> <span m='2093250'>few</span> <span
  m='2093489'>points</span> <span m='2094120'>distributed</span> <span
  m='2094840'>along</span> <span m='2095199'>here</span> <span
  m='2095530'>to</span> <span m='2095830'>provide</span> <span
  m='2096250'>a</span> <span m='2096340'>general</span> <span
  m='2096760'>characteristic</span> <span m='2098470'>to</span> <span
  m='2100000'>tend</span> <span m='2100420'>toward</span> <span
  m='2100930'>the</span> <span m='2101020'>next</span> <span
  m='2101290'>resonance,</span> <span m='2102420'>three</span> <span
  m='2102670'>points</span> <span m='2103040'>at</span> <span
  m='2103120'>this</span> <span m='2103360'>resonance,</span> <span
  m='2104080'>and</span> <span m='2104260'>then</span> <span
  m='2104620'>a</span> <span m='2104680'>few</span> <span
  m='2104920'>points</span> <span m='2105340'>to</span> <span
  m='2105460'>have</span> <span m='2105640'>the</span> <span
  m='2105730'>frequency</span> <span m='2106240'>response</span> <span
  m='2106720'>taper</span> <span m='2107110'>off.</span> </p><p><span
  m='2109350'>Well,</span> <span m='2109860'>what</span> <span
  m='2110070'>was</span> <span m='2110280'>used</span> <span
  m='2111000'>was</span> <span m='2111600'>a</span> <span
  m='2111660'>total</span> <span m='2112260'>of</span> <span
  m='2113010'>three</span> <span m='2113340'>second</span> <span
  m='2113730'>order</span> <span m='2114000'>sections.</span> <span
  m='2114990'>And</span> <span m='2115860'>the</span> <span
  m='2115950'>resulting</span> <span m='2116430'>frequency</span> <span
  m='2116970'>response</span> <span m='2117480'>that</span> <span
  m='2117570'>was</span> <span m='2117750'>obtained</span> <span
  m='2118860'>is</span> <span m='2119490'>what</span> <span
  m='2119910'>is</span> <span m='2120990'>shown</span> <span
  m='2121380'>here</span> <span m='2121850'>in</span> <span
  m='2122040'>solid</span> <span m='2122520'>lines.</span> <span
  m='2123910'>And</span> <span m='2124290'>you</span> <span
  m='2124470'>can</span> <span m='2124650'>see</span> <span
  m='2124920'>that,</span> <span m='2125070'>in</span> <span
  m='2125160'>fact,</span> <span m='2125550'>that's</span> <span
  m='2125940'>a</span> <span m='2126000'>reasonably</span> <span
  m='2126990'>good</span> <span m='2127260'>fit</span> <span
  m='2128040'>to</span> <span m='2128430'>the</span> <span
  m='2128550'>points</span> <span m='2128940'>that</span> <span
  m='2129030'>were</span> <span m='2129150'>specified.</span> <span
  m='2130530'>This</span> <span m='2130890'>particular</span> <span
  m='2131460'>example</span> <span m='2133080'>I</span> <span
  m='2133260'>chose</span> <span m='2133590'>to</span> <span
  m='2133680'>illustrate</span> <span m='2134850'>primarily,</span> <span
  m='2135570'>because</span> <span m='2136470'>it</span> <span
  m='2136640'>is</span> <span m='2136920'>one</span> <span m='2137100'>of</span>
  <span m='2137190'>the</span> <span m='2137280'>harder</span> <span
  m='2137700'>examples</span> <span m='2139380'>involving</span> <span
  m='2139890'>the</span> <span m='2139980'>minimization</span> <span
  m='2140640'>of</span> <span m='2140700'>mean</span> <span
  m='2140940'>square</span> <span m='2141300'>error.</span> <span
  m='2142500'>And</span> <span m='2142620'>in</span> <span
  m='2142740'>fact,</span> <span m='2143650'>in</span> <span
  m='2143750'>terms</span> <span m='2143970'>of</span> <span
  m='2144060'>computer</span> <span m='2144570'>time</span> <span
  m='2145200'>on</span> <span m='2145650'>an</span> <span m='2145770'>IBM</span>
  <span m='2146250'>36065,</span> <span m='2148830'>this</span> <span
  m='2149040'>particular</span> <span m='2149610'>example</span> <span
  m='2150120'>required</span> <span m='2150930'>approximately</span> <span
  m='2151680'>2</span> <span m='2151880'>and</span> <span m='2152080'>1/2</span>
  <span m='2152280'>minutes.</span> <span m='2153280'>So</span> <span
  m='2153690'>that's</span> <span m='2154170'>a</span> <span
  m='2154230'>reasonable</span> <span m='2155100'>amount</span> <span
  m='2155400'>of</span> <span m='2155490'>computation,</span> <span
  m='2157030'>but</span> <span m='2157740'>one</span> <span
  m='2157920'>of</span> <span m='2158040'>the</span> <span
  m='2158340'>important</span> <span m='2159150'>aspects</span> <span
  m='2159750'>to</span> <span m='2159990'>it</span> <span m='2160200'>is</span>
  <span m='2160440'>that</span> <span m='2161100'>it</span> <span
  m='2161220'>allows</span> <span m='2161850'>the</span> <span
  m='2162000'>design,</span> <span m='2162630'>and</span> <span
  m='2162810'>it</span> <span m='2162930'>allowed</span> <span
  m='2163290'>the</span> <span m='2163410'>design,</span> <span
  m='2164400'>of</span> <span m='2164550'>a</span> <span
  m='2164610'>somewhat</span> <span m='2165480'>general</span> <span
  m='2166290'>frequency</span> <span m='2167700'>shape,</span> <span
  m='2168240'>frequency</span> <span m='2168720'>characteristic.</span>
  </p><p><span m='2170990'>All</span> <span m='2171080'>right.</span> <span
  m='2171470'>So</span> <span m='2172100'>that</span> <span
  m='2172460'>is</span> <span m='2173240'>one</span> <span
  m='2173600'>algorithmic</span> <span m='2174320'>method.</span> <span
  m='2175670'>And</span> <span m='2176990'>it,</span> <span
  m='2177260'>in</span> <span m='2177410'>fact,</span> <span
  m='2177740'>is</span> <span m='2177860'>a</span> <span m='2177920'>good</span>
  <span m='2178160'>method.</span> <span m='2178580'>It's</span> <span
  m='2178760'>one</span> <span m='2178970'>of</span> <span
  m='2179030'>the</span> <span m='2179120'>methods</span> <span
  m='2179690'>that</span> <span m='2180020'>is</span> <span
  m='2180230'>commonly</span> <span m='2180740'>used,</span> <span
  m='2181520'>particularly</span> <span m='2182150'>when</span> <span
  m='2182300'>the</span> <span m='2182390'>frequency--</span> <span
  m='2183050'>when</span> <span m='2183620'>some</span> <span
  m='2183860'>of</span> <span m='2183920'>the</span> <span
  m='2184070'>other</span> <span m='2184280'>methods--</span> <span
  m='2184670'>the</span> <span m='2184790'>bilinear</span> <span
  m='2185300'>transformation</span> <span m='2186320'>or</span> <span
  m='2186530'>impulse</span> <span m='2186950'>invariance</span> <span
  m='2187550'>can't</span> <span m='2187820'>be</span> <span
  m='2187970'>used,</span> <span m='2188870'>because</span> <span
  m='2189560'>the</span> <span m='2189770'>filter</span> <span
  m='2190220'>isn't</span> <span m='2190490'>of</span> <span
  m='2190610'>a</span> <span m='2190640'>simple</span> <span
  m='2191000'>form.</span> <span m='2192530'>But</span> <span
  m='2193340'>one</span> <span m='2193550'>of</span> <span
  m='2193700'>the</span> <span m='2194240'>major</span> <span
  m='2194660'>disadvantages</span> <span m='2195560'>to</span> <span
  m='2195830'>it</span> <span m='2196700'>is</span> <span m='2196880'>the</span>
  <span m='2197000'>fact</span> <span m='2197570'>that</span> <span
  m='2198050'>the</span> <span m='2198230'>equations</span> <span
  m='2199730'>that</span> <span m='2199880'>result</span> <span
  m='2200840'>are</span> <span m='2200960'>not</span> <span
  m='2201240'>linear</span> <span m='2201590'>equations.</span> <span
  m='2202790'>And</span> <span m='2203030'>in</span> <span
  m='2203180'>general,</span> <span m='2203660'>solving</span> <span
  m='2204110'>nonlinear</span> <span m='2204710'>equations</span> <span
  m='2205610'>is</span> <span m='2206240'>a</span> <span
  m='2206300'>fairly</span> <span m='2206690'>difficult</span> <span
  m='2207380'>algorithmic</span> <span m='2208070'>job.</span> </p><p><span
  m='2209970'>Well,</span> <span m='2210510'>there's</span> <span
  m='2210990'>an</span> <span m='2211080'>alternative</span> <span
  m='2212220'>to</span> <span m='2212370'>that,</span> <span
  m='2213300'>which</span> <span m='2213870'>is</span> <span
  m='2214980'>a</span> <span m='2215010'>method</span> <span
  m='2215820'>which</span> <span m='2216060'>is</span> <span
  m='2216150'>commonly</span> <span m='2216720'>referred</span> <span
  m='2217140'>to</span> <span m='2217560'>as</span> <span
  m='2217890'>least</span> <span m='2218250'>squares</span> <span
  m='2219060'>inverse</span> <span m='2219660'>design.</span> <span
  m='2221790'>And</span> <span m='2222090'>in</span> <span
  m='2222210'>that</span> <span m='2222390'>design</span> <span
  m='2222810'>procedure,</span> <span m='2224700'>we</span> <span
  m='2224940'>can</span> <span m='2226900'>imagine</span> <span
  m='2227470'>specifying</span> <span m='2228670'>a</span> <span
  m='2229180'>desired</span> <span m='2230140'>impulse</span> <span
  m='2230650'>response.</span> <span m='2232540'>And</span> <span
  m='2232660'>in</span> <span m='2232780'>this</span> <span
  m='2233020'>case,</span> <span m='2234010'>we</span> <span
  m='2234400'>restrict</span> <span m='2236830'>the</span> <span
  m='2237430'>filter</span> <span m='2237760'>transfer</span> <span
  m='2238300'>function</span> <span m='2239490'>to</span> <span
  m='2239650'>have</span> <span m='2240250'>no</span> <span
  m='2240490'>0s</span> <span m='2241600'>and</span> <span
  m='2241750'>only</span> <span m='2242080'>poles.</span> </p><p><span
  m='2244430'>Well,</span> <span m='2244660'>it</span> <span
  m='2244750'>turns</span> <span m='2245140'>out--</span> <span
  m='2245440'>and</span> <span m='2245560'>I</span> <span
  m='2245620'>don't</span> <span m='2245920'>want</span> <span
  m='2246610'>to</span> <span m='2246970'>elaborate</span> <span
  m='2247510'>on</span> <span m='2247600'>the</span> <span
  m='2247690'>details--</span> <span m='2248890'>but</span> <span
  m='2249370'>basically,</span> <span m='2249940'>the</span> <span
  m='2250030'>way</span> <span m='2250210'>this</span> <span
  m='2250360'>procedure</span> <span m='2250930'>is</span> <span
  m='2251050'>set</span> <span m='2251320'>up</span> <span m='2252490'>is</span>
  <span m='2253660'>to</span> <span m='2255250'>consider</span> <span
  m='2256180'>a</span> <span m='2256240'>system</span> <span
  m='2257560'>whose</span> <span m='2257710'>system</span> <span
  m='2258190'>function</span> <span m='2258880'>is</span> <span
  m='2259120'>the</span> <span m='2259300'>inverse</span> <span
  m='2260140'>of</span> <span m='2260260'>H</span> <span m='2260530'>of</span>
  <span m='2260620'>z,</span> <span m='2261440'>so</span> <span
  m='2261630'>that</span> <span m='2261820'>that</span> <span
  m='2262030'>system</span> <span m='2262390'>is</span> <span
  m='2262460'>in</span> <span m='2262600'>all</span> <span m='2262780'>0</span>
  <span m='2263180'>system,</span> <span m='2265320'>and</span> <span
  m='2265470'>then</span> <span m='2266250'>choose</span> <span
  m='2266610'>as</span> <span m='2266760'>an</span> <span
  m='2266880'>input</span> <span m='2267240'>to</span> <span
  m='2267390'>that</span> <span m='2267630'>system</span> <span
  m='2268500'>the</span> <span m='2268620'>desired</span> <span
  m='2269280'>unit</span> <span m='2269550'>sample</span> <span
  m='2269970'>response.</span> <span m='2271290'>Now,</span> <span
  m='2272400'>we</span> <span m='2272550'>have</span> <span
  m='2272970'>the</span> <span m='2273090'>desired</span> <span
  m='2273540'>unit</span> <span m='2273780'>sample</span> <span
  m='2274170'>response</span> <span m='2274680'>is</span> <span
  m='2274800'>the</span> <span m='2274920'>input.</span> <span
  m='2276660'>We've</span> <span m='2276810'>got</span> <span
  m='2277170'>the</span> <span m='2277290'>reciprocal</span> <span
  m='2278370'>of</span> <span m='2279090'>the</span> <span
  m='2279300'>filter</span> <span m='2280140'>that</span> <span
  m='2280500'>we're</span> <span m='2280650'>going</span> <span
  m='2280920'>to</span> <span m='2281040'>implement</span> <span
  m='2283010'>in</span> <span m='2283170'>this</span> <span
  m='2284220'>as</span> <span m='2284670'>the</span> <span
  m='2284970'>system</span> <span m='2285420'>function.</span> </p><p><span
  m='2286950'>And</span> <span m='2287130'>if,</span> <span
  m='2287400'>in</span> <span m='2287550'>fact,</span> <span
  m='2288630'>the</span> <span m='2289710'>realized</span> <span
  m='2290520'>unit</span> <span m='2290820'>sample</span> <span
  m='2291240'>response</span> <span m='2291900'>was</span> <span
  m='2292230'>exactly</span> <span m='2292800'>equal</span> <span
  m='2293100'>to</span> <span m='2293250'>the</span> <span
  m='2293370'>desired</span> <span m='2293970'>unit</span> <span
  m='2294240'>sample</span> <span m='2294630'>response,</span> <span
  m='2295770'>what</span> <span m='2295920'>would</span> <span
  m='2296070'>the</span> <span m='2296190'>output</span> <span
  m='2296610'>be?</span> <span m='2298360'>Well,</span> <span
  m='2298690'>it</span> <span m='2298750'>would</span> <span
  m='2298930'>be</span> <span m='2299170'>a</span> <span m='2299230'>unit</span>
  <span m='2299560'>sample,</span> <span m='2300460'>because</span> <span
  m='2300910'>this</span> <span m='2301180'>would</span> <span
  m='2301300'>be</span> <span m='2301480'>exactly</span> <span
  m='2301990'>the</span> <span m='2302140'>inverse</span> <span
  m='2302680'>of</span> <span m='2302770'>this</span> <span
  m='2303310'>unit</span> <span m='2303580'>sample</span> <span
  m='2303940'>response.</span> <span m='2305590'>Well,</span> <span
  m='2305950'>let's</span> <span m='2306220'>think</span> <span
  m='2306400'>of</span> <span m='2306490'>the</span> <span
  m='2306640'>output</span> <span m='2306970'>as</span> <span
  m='2307120'>g</span> <span m='2307360'>of</span> <span m='2307480'>n.</span>
  <span m='2309670'>And</span> <span m='2310720'>ideally,</span> <span
  m='2311650'>g of n</span> <span m='2312520'>should</span> <span
  m='2312730'>be</span> <span m='2313420'>an</span> <span
  m='2313510'>impulse,</span> <span m='2313765'>a</span> <span
  m='2314020'>unit</span> <span m='2314320'>sample.</span> <span
  m='2316390'>Well,</span> <span m='2316750'>in</span> <span
  m='2316900'>general,</span> <span m='2317260'>of</span> <span
  m='2317350'>course,</span> <span m='2317650'>it</span> <span
  m='2317770'>won't</span> <span m='2318040'>be,</span> <span
  m='2318790'>since</span> <span m='2319360'>H sub</span> <span
  m='2319660'>d</span> <span m='2319860'>of n</span> <span m='2320560'>we</span>
  <span m='2320710'>won't</span> <span m='2320920'>be</span> <span
  m='2321040'>able</span> <span m='2321280'>to</span> <span
  m='2321400'>fit</span> <span m='2321610'>exactly</span> <span
  m='2322180'>by</span> <span m='2322720'>a</span> <span
  m='2322780'>model</span> <span m='2323170'>of</span> <span
  m='2323260'>that</span> <span m='2323470'>form.</span> </p><p><span
  m='2324530'>So</span> <span m='2325000'>let's</span> <span
  m='2325270'>consider</span> <span m='2325720'>the</span> <span
  m='2325930'>error,</span> <span m='2327400'>which</span> <span
  m='2327610'>is</span> <span m='2327760'>the</span> <span
  m='2327880'>mean</span> <span m='2328120'>square</span> <span
  m='2328480'>difference</span> <span m='2329500'>between</span> <span
  m='2330010'>g of n</span> <span m='2331240'>and</span> <span
  m='2331650'>a</span> <span m='2331720'>unit</span> <span
  m='2332080'>sample.</span> <span m='2333280'>And</span> <span
  m='2333670'>that</span> <span m='2334000'>then</span> <span
  m='2334480'>is</span> <span m='2335200'>the</span> <span
  m='2335380'>error</span> <span m='2335770'>that</span> <span
  m='2335920'>we</span> <span m='2336070'>minimize.</span> <span
  m='2337150'>So</span> <span m='2337900'>the</span> <span
  m='2338020'>idea</span> <span m='2338350'>behind</span> <span
  m='2338710'>the</span> <span m='2338770'>least</span> <span
  m='2338980'>squares</span> <span m='2339280'>inverse</span> <span
  m='2339730'>design</span> <span m='2340930'>is</span> <span
  m='2341050'>basically</span> <span m='2341650'>to</span> <span
  m='2341770'>design</span> <span m='2342970'>the</span> <span
  m='2344320'>inverse</span> <span m='2345250'>to</span> <span
  m='2345400'>the</span> <span m='2345520'>desired</span> <span
  m='2347110'>unit</span> <span m='2347410'>sample</span> <span
  m='2347800'>response,</span> <span m='2349270'>do</span> <span
  m='2349480'>that</span> <span m='2349780'>by</span> <span
  m='2349960'>minimizing</span> <span m='2350590'>the</span> <span
  m='2350680'>mean</span> <span m='2350890'>square</span> <span
  m='2351280'>error</span> <span m='2352540'>between</span> <span
  m='2353020'>the</span> <span m='2353140'>output</span> <span
  m='2353710'>of</span> <span m='2353860'>this</span> <span
  m='2354040'>inverse</span> <span m='2354430'>system</span> <span
  m='2355360'>and</span> <span m='2355480'>the</span> <span
  m='2355570'>desired</span> <span m='2356110'>output.</span> <span
  m='2356590'>And</span> <span m='2356680'>the</span> <span
  m='2356800'>desired</span> <span m='2357310'>output,</span> <span
  m='2357580'>of</span> <span m='2357640'>course,</span> <span
  m='2357970'>is</span> <span m='2358110'>a</span> <span m='2358150'>unit</span>
  <span m='2358450'>sample.</span> </p><p><span m='2361030'>Well,</span> <span
  m='2362260'>there's</span> <span m='2362860'>the</span> <span
  m='2363130'>legitimate</span> <span m='2363670'>question</span> <span
  m='2364300'>as</span> <span m='2364480'>to</span> <span
  m='2364600'>whether</span> <span m='2364900'>that</span> <span
  m='2365740'>is</span> <span m='2366490'>a</span> <span
  m='2366790'>reasonable</span> <span m='2367630'>error</span> <span
  m='2367930'>criterion</span> <span m='2368680'>to</span> <span
  m='2368800'>use.</span> <span m='2369730'>It's,</span> <span
  m='2370030'>of</span> <span m='2370150'>course,</span> <span
  m='2370450'>a</span> <span m='2370510'>possible</span> <span
  m='2370870'>error</span> <span m='2371230'>criterion</span> <span
  m='2371950'>to</span> <span m='2372070'>use.</span> <span
  m='2373360'>But</span> <span m='2373780'>one</span> <span
  m='2374050'>could</span> <span m='2374230'>ask,</span> <span
  m='2374470'>why</span> <span m='2374710'>in</span> <span
  m='2374800'>the</span> <span m='2374890'>world</span> <span
  m='2375310'>would</span> <span m='2375490'>you</span> <span
  m='2375550'>want</span> <span m='2375760'>to</span> <span
  m='2375820'>set</span> <span m='2376090'>up</span> <span
  m='2376240'>the</span> <span m='2376330'>problem</span> <span
  m='2376810'>that</span> <span m='2376990'>way?</span> <span
  m='2378160'>Well,</span> <span m='2378250'>there's</span> <span
  m='2378400'>a</span> <span m='2378460'>very</span> <span
  m='2378700'>good</span> <span m='2378880'>reason.</span> <span
  m='2380200'>The</span> <span m='2380290'>reason</span> <span
  m='2380710'>is</span> <span m='2381250'>that,</span> <span
  m='2381370'>if</span> <span m='2381490'>you</span> <span m='2381580'>do</span>
  <span m='2381850'>that,</span> <span m='2383250'>minimize</span> <span
  m='2383830'>this</span> <span m='2384070'>error</span> <span
  m='2385670'>in</span> <span m='2385790'>terms</span> <span
  m='2386360'>of</span> <span m='2386540'>these</span> <span
  m='2386750'>coefficients,</span> <span m='2388820'>the</span> <span
  m='2389030'>equations</span> <span m='2389660'>that</span> <span
  m='2389780'>result</span> <span m='2390650'>are</span> <span
  m='2390800'>linear</span> <span m='2391190'>equations.</span> <span
  m='2392360'>And</span> <span m='2392480'>linear</span> <span
  m='2392870'>equations</span> <span m='2393740'>are</span> <span
  m='2394220'>simple</span> <span m='2394670'>equations</span> <span
  m='2395210'>to</span> <span m='2395360'>solve,</span> <span
  m='2395990'>as</span> <span m='2396140'>opposed</span> <span
  m='2396470'>to</span> <span m='2396590'>nonlinear</span> <span
  m='2397130'>equations.</span> </p><p><span m='2398340'>So</span> <span
  m='2398390'>this</span> <span m='2398630'>is</span> <span m='2398780'>a</span>
  <span m='2398840'>technique</span> <span m='2399770'>that,</span> <span
  m='2399950'>in</span> <span m='2400130'>fact,</span> <span
  m='2400580'>turns</span> <span m='2400940'>out</span> <span
  m='2401180'>to</span> <span m='2401330'>be</span> <span m='2401690'>a</span>
  <span m='2401780'>good</span> <span m='2402020'>technique</span> <span
  m='2402680'>for</span> <span m='2403280'>a</span> <span
  m='2403370'>wide</span> <span m='2403730'>variety</span> <span
  m='2404600'>of</span> <span m='2404690'>filters.</span> <span
  m='2406190'>It</span> <span m='2406310'>has</span> <span
  m='2406640'>the</span> <span m='2406760'>important</span> <span
  m='2407240'>advantage</span> <span m='2408650'>that</span> <span
  m='2408950'>it</span> <span m='2409100'>leads</span> <span
  m='2409490'>to</span> <span m='2409640'>a</span> <span m='2409700'>set</span>
  <span m='2410090'>of</span> <span m='2410240'>linear</span> <span
  m='2410630'>equations,</span> <span m='2412340'>as</span> <span
  m='2412520'>opposed</span> <span m='2413030'>to</span> <span
  m='2413960'>the</span> <span m='2414080'>minimization</span> <span
  m='2414920'>of</span> <span m='2415040'>mean</span> <span
  m='2415250'>square</span> <span m='2415640'>error,</span> <span
  m='2416330'>which</span> <span m='2416510'>leads</span> <span
  m='2416780'>to</span> <span m='2416900'>a</span> <span m='2416960'>set</span>
  <span m='2417200'>of</span> <span m='2417290'>nonlinear</span> <span
  m='2417860'>equations.</span> </p><p><span m='2419430'>Well,</span> <span
  m='2419750'>this</span> <span m='2419960'>is</span> <span
  m='2420050'>just</span> <span m='2420320'>a</span> <span
  m='2420440'>very</span> <span m='2420800'>quick</span> <span
  m='2421070'>glimpse</span> <span m='2421730'>at</span> <span
  m='2423110'>two</span> <span m='2423530'>algorithmic</span> <span
  m='2424160'>design</span> <span m='2424550'>procedures.</span> <span
  m='2425210'>As</span> <span m='2425360'>I</span> <span m='2426110'>said</span>
  <span m='2426380'>previously,</span> <span m='2427260'>there</span> <span
  m='2427370'>are</span> <span m='2427400'>some</span> <span
  m='2427640'>others,</span> <span m='2428000'>which</span> <span
  m='2428180'>we</span> <span m='2428330'>won't</span> <span
  m='2428540'>be</span> <span m='2428660'>going</span> <span
  m='2428990'>into,</span> <span m='2429440'>some</span> <span
  m='2429710'>of</span> <span m='2429830'>which</span> <span
  m='2430070'>are</span> <span m='2430130'>described</span> <span
  m='2430700'>in</span> <span m='2430790'>the</span> <span
  m='2430880'>text.</span> <span m='2431840'>And</span> <span
  m='2432500'>there</span> <span m='2432860'>are</span> <span
  m='2433100'>a</span> <span m='2433160'>few</span> <span
  m='2433550'>related</span> <span m='2434090'>to</span> <span
  m='2434330'>finite</span> <span m='2434750'>impulse</span> <span
  m='2435140'>response</span> <span m='2435650'>filters</span> <span
  m='2436610'>that</span> <span m='2436820'>we'll</span> <span
  m='2437030'>be</span> <span m='2437300'>discussing</span> <span
  m='2437900'>in</span> <span m='2437990'>a</span> <span
  m='2438050'>number</span> <span m='2438350'>of</span> <span
  m='2438440'>lectures.</span> <span m='2439820'>In</span> <span
  m='2439940'>the</span> <span m='2440000'>next</span> <span
  m='2440270'>lecture,</span> <span m='2441390'>what</span> <span
  m='2441770'>I</span> <span m='2441860'>would</span> <span
  m='2442040'>like</span> <span m='2442250'>to</span> <span
  m='2442370'>do</span> <span m='2442940'>is</span> <span
  m='2444200'>review</span> <span m='2445400'>the</span> <span
  m='2445610'>impulse</span> <span m='2446110'>invariant</span> <span
  m='2446640'>and</span> <span m='2446750'>bilinear</span> <span
  m='2447680'>design</span> <span m='2448100'>procedures,</span> <span
  m='2448790'>since</span> <span m='2449060'>those</span> <span
  m='2449360'>are</span> <span m='2449630'>the</span> <span
  m='2449750'>two</span> <span m='2450170'>major</span> <span
  m='2451250'>design</span> <span m='2451670'>procedures</span> <span
  m='2452420'>for</span> <span m='2453110'>infinite</span> <span
  m='2453440'>impulse</span> <span m='2453830'>response</span> <span
  m='2454340'>filters,</span> <span m='2455240'>review</span> <span
  m='2455900'>those</span> <span m='2456140'>two</span> <span
  m='2456350'>procedures</span> <span m='2457370'>through</span> <span
  m='2457610'>a</span> <span m='2457670'>design</span> <span
  m='2458060'>example.</span> <span m='2458800'>Thank</span> <span
  m='2459000'>you.</span> </p><p><span m='2464100'>[MUSIC PLAYING]</span>
  </p><p></p>
embedded_media:
  - uid: 6b38f1882661a41b7699b95163d92933
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: MITRES_6_008S11_lec15.pdf
    title: MITRES_6_008S11_lec15.pdf
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-15-design-of-iir-digital-filters-part-2/MITRES_6_008S11_lec15.pdf
  - uid: da4a7d3e8d8886cd9f6e9a74cad19a92
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: ZbYAZLQHXSg
  - uid: 9b772931fc0721e6ad78663acda71d51
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: >-
      http://itunes.apple.com/us/itunes-u/lecture-15-design-iir-digital/id481803782?i=108361994
  - uid: 4bcee74e4e4c977786cd493799b6256a
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MITRES.6-008/MITRES6_008_lec15_300k.mp4'
  - uid: 12d15d0a98f99bc84c618980bf6efa9f
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/ZbYAZLQHXSg/default.jpg'
  - uid: 1feb6c47380197a674865336dce78311
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: ZbYAZLQHXSg
  - uid: e6e67a49590540d902dc327322ca828c
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: ZbYAZLQHXSg.srt
    title: 3play caption file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-15-design-of-iir-digital-filters-part-2/ZbYAZLQHXSg.srt
  - uid: d15c0a3b79581b2c24c72e8a437bc3d9
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: ZbYAZLQHXSg.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      /resources/res-6-008-digital-signal-processing-spring-2011/video-lectures/lecture-15-design-of-iir-digital-filters-part-2/ZbYAZLQHXSg.pdf
  - uid: 521148b221b7481dbe7d6c05f666ce40
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: a4aab482ddfb0c1c63403f720b645749
    parent_uid: ffedfbd0f8c1194b93e04316f92eb16f
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: res-6-008-digital-signal-processing-spring-2011
type: course
layout: video
---
