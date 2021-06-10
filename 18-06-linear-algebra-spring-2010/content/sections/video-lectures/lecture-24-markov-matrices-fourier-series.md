---
order_index: null
title: 'Lecture 24: Markov matrices; fourier series'
template_type: Tabbed
uid: f7be9e0b3fedac90071a0f982ac10293
parent_uid: 6b1f662457366951bfe85945521b0299
technical_location: >-
  https://ocw.mit.edu/courses/mathematics/18-06-linear-algebra-spring-2010/video-lectures/lecture-24-markov-matrices-fourier-series
short_url: lecture-24-markov-matrices-fourier-series
inline_embed_id: '27027154lecture24:markovmatrices;fourierseries83423210'
about_this_resource_text: >-
  <div class="vidpad"><p>Like differential equations, Markov matrices describe
  changes over time. Once again, the eigenvalues and eigenvectors describe the
  long term behavior of the system. In this session we also learn about Fourier
  series, which describe periodic functions as points in an infinite dimensional
  vector space.</p> <p>These video lectures of Professor Gilbert Strang teaching
  18.06 were  recorded in Fall 1999 and do not correspond precisely to the
  current  edition of the textbook. However, this book is still the best
  reference  for more information on the topics covered in each lecture.</p>
  <p>Strang, Gilbert. <em>Introduction to Linear Algebra</em>. 5th ed. <a
  href="http://www.wellesleycambridge.com/">Wellesley-Cambridge Press</a>, 2016.
  ISBN: 9780980232776.</p> <p><strong>Instructor/speaker:</strong> Prof. Gilbert
  Strang</p></div>
related_resources_text: >-
  <p><a href="resolveuid/81d6a1cd707c29b29d6540b3e79d5433"
  target="_blank">Readings</a><br /><a
  href="resolveuid/81d6a1cd707c29b29d6540b3e79d5433#Table_of_Contents"
  target="_blank">Table of Contents</a></p>
transcript: >-
  <p><span m="0">--</span> <span m="7950">two,</span> <span m="8580">one</span>
  <span m="9610">and</span> <span m="10190">--</span> <span
  m="10450">okay.</span> <span m="11240">Here</span> <span m="11910">is</span>
  <span m="12380">a</span> <span m="12520">lecture</span> <span
  m="13200">on</span> <span m="13620">the</span> <span
  m="13780">applications</span> <span m="15390">of</span> <span
  m="17650">eigenvalues</span> <span m="18910">and,</span> <span
  m="19610">if</span> <span m="19790">I</span> <span m="19900">can</span> <span
  m="20610">--</span> <span m="20690">so</span> <span m="20850">that</span>
  <span m="21120">will</span> <span m="21290">be</span> <span
  m="21500">Markov</span> <span m="22070">matrices.</span> <span
  m="24070">I'll</span> <span m="24760">tell</span> <span m="25090">you</span>
  <span m="25190">what</span> <span m="25390">a</span> <span
  m="25440">Markov</span> <span m="26000">matrix</span> <span
  m="26510">is,</span> <span m="27260">so</span> <span m="27720">this</span>
  <span m="28240">matrix</span> <span m="29020">A</span> <span
  m="29450">will</span> <span m="29670">be</span> <span m="29870">a</span> <span
  m="29950">Markov</span> <span m="30590">matrix</span> <span
  m="32070">and</span> <span m="36210">I'll</span> <span
  m="36440">explain</span> <span m="36880">how</span> <span
  m="37060">they</span> <span m="37220">come</span> <span m="37470">in</span>
  <span m="37580">applications.</span></p><p><span m="38890">And</span> <span
  m="39080">--</span> <span m="39180">and</span> <span m="39370">then</span>
  <span m="39560">if</span> <span m="39710">I</span> <span m="39840">have</span>
  <span m="40100">time,</span> <span m="40560">I</span> <span
  m="40670">would</span> <span m="40860">like</span> <span m="41190">to</span>
  <span m="41360">say</span> <span m="41720">a</span> <span
  m="41800">little</span> <span m="42060">bit</span> <span
  m="42250">about</span> <span m="42560">Fourier</span> <span
  m="43060">series,</span> <span m="43860">which</span> <span
  m="44270">is</span> <span m="44410">a</span> <span m="44510">fantastic</span>
  <span m="45230">application</span> <span m="46060">of</span> <span
  m="46560">the</span> <span m="46800">projection</span> <span
  m="47460">chapter.</span></p><p><span m="48540">Okay.</span></p><p><span
  m="49100">What's</span> <span m="49780">a</span> <span m="49860">Markov</span>
  <span m="50340">matrix?</span></p><p><span m="50930">Can</span> <span
  m="51100">I</span> <span m="51200">just</span> <span m="51750">write</span>
  <span m="52120">down</span> <span m="52410">a</span> <span
  m="52520">typical</span> <span m="53050">Markov</span> <span
  m="53550">matrix,</span> <span m="54210">say</span> <span m="55050">.1,</span>
  <span m="60580">.2,</span> <span m="61460">.7,</span> <span
  m="61940">.01,</span> <span m="62470">.99</span> <span m="63170">0,</span>
  <span m="63710">let's</span> <span m="64019">say,</span> <span
  m="64709">.3,</span> <span m="66760">.3,</span> <span m="67250">.4.</span>
  <span m="68820">Okay.</span> <span m="69970">There's</span> <span
  m="70590">a</span> <span m="71000">--</span> <span m="71400">a</span> <span
  m="71550">totally</span> <span m="71990">just</span> <span
  m="72260">invented</span> <span m="72970">Markov</span> <span
  m="73470">matrix.</span> <span m="76640">What</span> <span
  m="77320">makes</span> <span m="77620">it</span> <span m="77750">a</span>
  <span m="77820">Markov</span> <span m="78310">matrix?</span></p><p><span
  m="79540">Two</span> <span m="79840">properties</span> <span
  m="80700">that</span> <span m="81050">this</span> <span m="81060">--</span>
  <span m="81080">this</span> <span m="81310">matrix</span> <span
  m="81840">has.</span></p><p><span m="82510">So</span> <span
  m="82730">two</span> <span m="82960">properties</span> <span
  m="83650">are</span> <span m="84280">--</span> <span m="84970">one,</span>
  <span m="86480">every</span> <span m="87680">entry</span> <span
  m="88250">is</span> <span m="88890">greater</span> <span
  m="89290">equal</span> <span m="89610">zero.</span></p><p><span
  m="90430">All</span> <span m="90800">entries</span> <span
  m="95840">greater</span> <span m="96180">than</span> <span m="96410">or</span>
  <span m="96500">equal</span> <span m="96780">to</span> <span
  m="96860">zero.</span></p><p><span m="98720">And,</span> <span
  m="99310">of</span> <span m="99450">course,</span> <span
  m="100680">when</span> <span m="101500">I</span> <span
  m="101610">square</span> <span m="102020">the</span> <span
  m="102150">matrix,</span> <span m="103100">the</span> <span
  m="103250">entries</span> <span m="103640">will</span> <span
  m="103750">still</span> <span m="104040">be</span> <span
  m="104180">greater/equal</span> <span m="104840">zero.</span></p><p><span
  m="105660">I'm</span> <span m="105860">going</span> <span m="106030">to</span>
  <span m="106090">be</span> <span m="106210">interested</span> <span
  m="106780">in</span> <span m="106920">the</span> <span
  m="107040">powers</span> <span m="107690">of</span> <span
  m="107800">this</span> <span m="108060">matrix.</span></p><p><span
  m="110150">And</span> <span m="110780">this</span> <span
  m="111010">property,</span> <span m="111500">of</span> <span
  m="111610">course,</span> <span m="111910">is</span> <span
  m="112060">going</span> <span m="112230">to</span> <span m="112330">--</span>
  <span m="112530">stay</span> <span m="112950">there.</span></p><p><span
  m="114250">It</span> <span m="114990">--</span> <span m="115460">really</span>
  <span m="115780">Markov</span> <span m="116370">matrices</span> <span
  m="117020">you'll</span> <span m="117230">see</span> <span
  m="117880">are</span> <span m="118200">connected</span> <span
  m="118870">to</span> <span m="119320">probability</span> <span
  m="120940">ideas</span> <span m="122280">and</span> <span
  m="122850">probabilities</span> <span m="123840">are</span> <span
  m="123940">never</span> <span m="124230">negative.</span></p><p><span
  m="125120">The</span> <span m="125310">other</span> <span
  m="125570">property</span> <span m="126230">--</span> <span
  m="126420">do</span> <span m="126620">you</span> <span m="127080">see</span>
  <span m="127350">the</span> <span m="127510">other</span> <span
  m="127720">property</span> <span m="128220">in</span> <span
  m="128360">there?</span></p><p><span m="129669">If</span> <span
  m="129910">I</span> <span m="130060">add</span> <span m="130380">down</span>
  <span m="130620">the</span> <span m="130750">columns,</span> <span
  m="131460">what</span> <span m="131720">answer</span> <span
  m="132110">do</span> <span m="132230">I</span> <span
  m="132320">get?</span></p><p><span m="133590">One.</span></p><p><span
  m="134490">So</span> <span m="134810">all</span> <span
  m="135230">columns</span> <span m="136160">add</span> <span
  m="136760">to</span> <span m="136900">one.</span></p><p><span
  m="137640">All</span> <span m="138680">columns</span> <span
  m="139970">add</span> <span m="144290">to</span> <span
  m="145100">one.</span></p><p><span m="148900">And</span> <span
  m="149670">actually</span> <span m="150320">when</span> <span
  m="150510">I</span> <span m="150600">square</span> <span m="151010">the</span>
  <span m="151130">matrix,</span> <span m="151580">that</span> <span
  m="151740">will</span> <span m="151860">be</span> <span m="152010">true</span>
  <span m="152320">again.</span></p><p><span m="153820">So</span> <span
  m="154280">that</span> <span m="155510">the</span> <span
  m="156350">powers</span> <span m="156920">of</span> <span m="157160">my</span>
  <span m="157430">matrix</span> <span m="158290">are</span> <span
  m="158550">all</span> <span m="158920">Markov</span> <span
  m="159440">matrices,</span> <span m="160780">and</span> <span
  m="161590">I'm</span> <span m="161780">interested</span> <span
  m="162330">in,</span> <span m="162730">always,</span> <span
  m="163330">the</span> <span m="163530">eigenvalues</span> <span
  m="164820">and</span> <span m="165040">the</span> <span
  m="165170">eigenvectors.</span> <span m="166520">And</span> <span
  m="167450">this</span> <span m="167830">question</span> <span
  m="168370">of</span> <span m="168590">steady</span> <span
  m="169180">state</span> <span m="169970">will</span> <span
  m="170330">come</span> <span m="170540">up.</span></p><p><span
  m="170780">You</span> <span m="170920">remember</span> <span
  m="171290">we</span> <span m="171410">had</span> <span
  m="171630">steady</span> <span m="172060">state</span> <span
  m="172550">for</span> <span m="172730">differential</span> <span
  m="173300">equations</span></p><p><span m="173860">last</span> <span
  m="174180">time?</span> <span m="174940">When</span> <span
  m="175450">--</span> <span m="175600">what</span> <span m="176080">was</span>
  <span m="176260">the</span> <span m="176380">steady</span> <span
  m="176750">state</span> <span m="177060">--</span> <span
  m="177080">what</span> <span m="177200">was</span> <span m="177320">the</span>
  <span m="177460">eigenvalue?</span> <span m="179100">What</span> <span
  m="179950">was</span> <span m="180120">the</span> <span
  m="180270">eigenvalue</span> <span m="181180">in</span> <span
  m="181380">the</span> <span m="181480">differential</span> <span
  m="182100">equation</span> <span m="182640">case</span> <span
  m="183240">that</span> <span m="183750">led</span> <span m="184060">to</span>
  <span m="184210">a</span> <span m="184260">steady</span> <span
  m="184630">state?</span></p><p><span m="185620">It</span> <span
  m="185850">was</span> <span m="186310">lambda</span> <span
  m="186730">equals</span> <span m="187150">zero.</span></p><p><span
  m="188360">When</span> <span m="188570">--</span> <span m="189140">you</span>
  <span m="189270">remember</span> <span m="189590">that</span> <span
  m="189720">we</span> <span m="189850">did</span> <span m="190020">an</span>
  <span m="190160">example</span> <span m="190850">and</span> <span
  m="191020">one</span> <span m="191210">of</span> <span m="191290">the</span>
  <span m="191440">eigenvalues</span> <span m="192200">was</span> <span
  m="192380">lambda</span> <span m="192770">equals</span> <span
  m="193150">zero,</span> <span m="194040">and</span> <span
  m="194600">that</span> <span m="195000">--</span> <span m="195180">so</span>
  <span m="195370">then</span> <span m="195570">we</span> <span
  m="195700">had</span> <span m="195870">an</span> <span m="196020">E</span>
  <span m="196330">to</span> <span m="196440">the</span> <span
  m="196550">zero</span> <span m="197000">T,</span> <span m="198020">a</span>
  <span m="198580">constant</span> <span m="199170">one</span> <span
  m="199730">--</span> <span m="200140">as</span> <span m="200800">time</span>
  <span m="201150">went</span> <span m="201350">on,</span> <span
  m="201840">there</span> <span m="202270">that</span> <span
  m="202580">thing</span> <span m="202830">stayed</span> <span
  m="203300">steady.</span></p><p><span m="204430">Now</span> <span
  m="204650">what</span> <span m="205060">--</span> <span m="205090">in</span>
  <span m="205330">the</span> <span m="206290">powers</span> <span
  m="207220">case,</span> <span m="208100">it's</span> <span
  m="208510">not</span> <span m="208790">a</span> <span m="208820">zero</span>
  <span m="209260">eigenvalue.</span></p><p><span m="210760">Actually</span>
  <span m="211140">with</span> <span m="211340">powers</span> <span
  m="211860">of</span> <span m="211980">a</span> <span m="212040">matrix,</span>
  <span m="212590">a</span> <span m="212640">zero</span> <span
  m="213030">eigenvalue,</span> <span m="213740">that</span> <span
  m="213970">part</span> <span m="214200">is</span> <span
  m="214330">going</span> <span m="214500">to</span> <span m="214580">die</span>
  <span m="214980">right</span> <span m="215230">away.</span></p><p><span
  m="216570">It's</span> <span m="216930">an</span> <span
  m="217090">eigenvalue</span> <span m="217950">of</span> <span
  m="218160">one</span> <span m="219450">that's</span> <span
  m="220470">all</span> <span m="220790">important.</span></p><p><span
  m="221710">So</span> <span m="221930">this</span> <span
  m="222210">steady</span> <span m="222620">state</span> <span
  m="223090">will</span> <span m="223340">correspond</span> <span
  m="224520">--</span> <span m="224540">will</span> <span m="224720">be</span>
  <span m="225010">totally</span> <span m="225480">connected</span> <span
  m="226180">with</span> <span m="226910">an</span> <span
  m="227290">eigenvalue</span> <span m="228070">of</span> <span
  m="228200">one</span> <span m="228650">and</span> <span m="228800">its</span>
  <span m="229000">eigenvector.</span> <span m="229910">In</span> <span
  m="230160">fact,</span> <span m="230420">the</span> <span
  m="230530">steady</span> <span m="230930">state</span> <span
  m="231320">will</span> <span m="231630">be</span> <span m="232340">the</span>
  <span m="232700">eigenvector</span> <span m="233510">for</span> <span
  m="233640">that</span> <span m="233880">eigenvalue.</span> <span
  m="235260">Okay.</span> <span m="236670">So</span> <span
  m="237160">that's</span> <span m="237410">what's</span> <span
  m="237640">coming.</span></p><p><span m="238580">Now,</span> <span
  m="239590">for</span> <span m="240240">some</span> <span
  m="240510">reason</span> <span m="240990">then</span> <span
  m="241970">that</span> <span m="243060">we</span> <span m="243200">have</span>
  <span m="243480">to</span> <span m="243630">see,</span> <span
  m="244390">this</span> <span m="244780">matrix</span> <span
  m="245490">has</span> <span m="245870">an</span> <span
  m="246010">eigenvalue</span> <span m="246720">of</span> <span
  m="246830">one.</span></p><p><span m="248210">This</span> <span
  m="248540">property,</span> <span m="249210">that</span> <span
  m="249440">the</span> <span m="249590">columns</span> <span
  m="250180">all</span> <span m="250480">add</span> <span m="250720">to</span>
  <span m="250850">one</span> <span m="251360">--</span> <span
  m="252040">turns</span> <span m="252410">out</span> <span m="252940">--</span>
  <span m="253560">guarantees</span> <span m="254430">that</span> <span
  m="254610">one</span> <span m="255040">is</span> <span m="255260">an</span>
  <span m="255410">eigenvalue,</span> <span m="256680">so</span> <span
  m="257430">that</span> <span m="257700">you</span> <span m="257880">can</span>
  <span m="258070">actually</span> <span m="258500">find</span> <span
  m="258880">the</span> <span m="259010">eigenvalue</span> <span
  m="259310">--</span> <span m="259600">find</span> <span m="259890">that</span>
  <span m="260120">eigenvalue</span> <span m="260779">of</span> <span
  m="260800">a</span> <span m="260950">Markov</span> <span
  m="261399">matrix</span> <span m="261920">without</span> <span
  m="263050">computing</span> <span m="264060">any</span> <span
  m="264330">determinants</span> <span m="265080">of</span> <span
  m="265220">A</span> <span m="265370">minus</span> <span
  m="265790">lambda</span> <span m="266200">I</span> <span m="266740">--</span>
  <span m="267640">that</span> <span m="267970">matrix</span> <span
  m="268480">will</span> <span m="268780">have</span> <span m="268980">an</span>
  <span m="269100">eigenvalue</span> <span m="269800">of</span> <span
  m="269900">one,</span> <span m="270310">and</span> <span m="270430">we</span>
  <span m="270540">want</span> <span m="270750">to</span> <span
  m="270820">see</span> <span m="271030">why.</span></p><p><span
  m="272270">And</span> <span m="272820">then</span> <span m="273160">the</span>
  <span m="273320">other</span> <span m="273540">thing</span> <span
  m="273810">is</span> <span m="274280">--</span> <span m="275850">so</span>
  <span m="276020">the</span> <span m="276160">key</span> <span
  m="276450">points</span> <span m="276870">--</span> <span
  m="276890">let</span> <span m="276980">me</span> <span m="277170">--</span>
  <span m="277190">let</span> <span m="277370">me</span> <span
  m="277480">write</span> <span m="277760">these</span> <span
  m="278000">underneath.</span></p><p><span m="279190">The</span> <span
  m="279310">key</span> <span m="279570">points</span> <span
  m="280060">are</span> <span m="280670">--</span> <span m="281020">the</span>
  <span m="281780">key</span> <span m="282050">points</span> <span
  m="282760">are</span> <span m="283860">lambda</span> <span
  m="284640">equal</span> <span m="285110">one</span> <span m="285680">is</span>
  <span m="285940">an</span> <span m="286060">eigenvalue.</span></p><p><span
  m="293760">I'll</span> <span m="294020">add</span> <span m="294320">in</span>
  <span m="294500">a</span> <span m="294580">little</span> <span
  m="294980">--</span> <span m="295150">an</span> <span
  m="295390">additional</span> <span m="296020">--</span> <span
  m="296180">well,</span> <span m="296410">a</span> <span
  m="296690">thing</span> <span m="296980">about</span> <span
  m="297220">eigenvalues</span> <span m="298170">--</span> <span
  m="299030">key</span> <span m="299250">point</span> <span
  m="299640">two,</span> <span m="300390">the</span> <span
  m="300700">other</span> <span m="301050">eigenval-</span> <span
  m="301710">values</span> <span m="302360">--</span> <span
  m="302400">all</span> <span m="302750">other</span> <span
  m="305540">eigenvalues</span> <span m="305970">are,</span> <span
  m="309380">in</span> <span m="309580">magnitude,</span> <span
  m="310700">smaller</span> <span m="311370">than</span> <span
  m="311510">one</span> <span m="311880">--</span> <span m="312340">in</span>
  <span m="312530">absolute</span> <span m="312920">value,</span> <span
  m="313280">smaller</span> <span m="313680">than</span> <span
  m="313840">one.</span></p><p><span m="314630">Well,</span> <span
  m="314990">there</span> <span m="315170">could</span> <span
  m="315370">be</span> <span m="315530">some</span> <span
  m="315790">exceptional</span> <span m="316550">case</span> <span
  m="317270">when</span> <span m="317880">--</span> <span m="318390">when</span>
  <span m="318890">an</span> <span m="319110">eigen</span> <span
  m="319450">--</span> <span m="319500">another</span> <span
  m="319920">eigenvalue</span> <span m="320560">might</span> <span
  m="320820">have</span> <span m="321440">magnitude</span> <span
  m="322380">equal</span> <span m="322800">one.</span></p><p><span
  m="323300">It</span> <span m="323560">never</span> <span m="323970">has</span>
  <span m="324250">an</span> <span m="324410">eigenvalue</span> <span
  m="325130">larger</span> <span m="325560">than</span> <span
  m="325780">one.</span></p><p><span m="326690">So</span> <span
  m="326920">these</span> <span m="327240">two</span> <span
  m="327460">facts</span> <span m="328140">--</span> <span
  m="328160">somehow</span> <span m="328630">we</span> <span
  m="328800">ought</span> <span m="328930">to</span> <span m="329080">--</span>
  <span m="329230">linear</span> <span m="329560">algebra</span> <span
  m="329960">ought</span> <span m="330180">to</span> <span
  m="330310">tell</span> <span m="330560">us.</span></p><p><span
  m="332600">And</span> <span m="332840">then,</span> <span m="333170">of</span>
  <span m="333270">course,</span> <span m="333590">linear</span> <span
  m="334040">algebra</span> <span m="334440">is</span> <span
  m="334550">going</span> <span m="334710">to</span> <span
  m="334820">tell</span> <span m="335090">us</span> <span m="335440">what</span>
  <span m="336030">the</span> <span m="336560">--</span> <span
  m="336660">what's</span> <span m="337160">--</span> <span
  m="337220">what</span> <span m="337470">happens</span> <span
  m="338320">if</span> <span m="338670">I</span> <span m="338810">take</span>
  <span m="339480">--</span> <span m="339770">if</span> <span
  m="340010">--</span> <span m="340040">you</span> <span
  m="340210">remember</span> <span m="340680">when</span> <span
  m="340870">I</span> <span m="340990">solve</span> <span m="342050">--</span>
  <span m="342720">when</span> <span m="343010">I</span> <span
  m="343110">multiply</span> <span m="343720">by</span> <span
  m="343990">A</span> <span m="344370">time</span> <span m="344720">after</span>
  <span m="345070">time</span> <span m="345760">the</span> <span
  m="346070">K-th</span> <span m="346450">thing</span> <span
  m="347280">is</span> <span m="347710">A</span> <span m="347980">to</span>
  <span m="348090">the</span> <span m="348260">K</span> <span
  m="349190">u0</span> <span m="350970">and</span> <span m="351770">I'm</span>
  <span m="351930">asking</span> <span m="352400">what's</span> <span
  m="352760">special</span> <span m="353270">about</span> <span
  m="353680">this</span> <span m="354200">--</span> <span
  m="354940">these</span> <span m="355240">powers</span> <span
  m="355740">of</span> <span m="355890">A,</span> <span m="358810">and</span>
  <span m="359110">very</span> <span m="359420">likely</span> <span
  m="359880">the</span> <span m="360200">quiz</span> <span
  m="360700">will</span> <span m="360910">have</span> <span m="361240">a</span>
  <span m="361480">problem</span> <span m="362080">to</span> <span
  m="362250">computer</span> <span m="363050">s-</span> <span
  m="363600">to</span> <span m="363830">computer</span> <span
  m="364270">some</span> <span m="364520">powers</span> <span
  m="365060">of</span> <span m="365200">A</span> <span m="365800">or</span>
  <span m="366420">--</span> <span m="366440">or</span> <span
  m="366490">applied</span> <span m="366890">to</span> <span
  m="367050">an</span> <span m="367150">initial</span> <span
  m="367550">vector.</span></p><p><span m="368570">So,</span> <span
  m="368980">you</span> <span m="369140">remember</span> <span
  m="369460">the</span> <span m="369630">general</span> <span
  m="370110">form?</span></p><p><span m="371040">The</span> <span
  m="371220">general</span> <span m="371600">form</span> <span
  m="372070">is</span> <span m="372440">that</span> <span
  m="372600">there's</span> <span m="372820">some</span> <span
  m="373280">amount</span> <span m="374180">of</span> <span
  m="374580">the</span> <span m="374730">first</span> <span
  m="375180">eigenvalue</span> <span m="376010">to</span> <span
  m="376160">the</span> <span m="376290">K-th</span> <span
  m="376760">power</span> <span m="377660">times</span> <span
  m="378010">the</span> <span m="378140">first</span> <span
  m="378480">eigenvector,</span> <span m="379820">and</span> <span
  m="381150">another</span> <span m="382290">amount</span> <span
  m="382790">of</span> <span m="383020">the</span> <span
  m="383120">second</span> <span m="383620">eigenvalue</span> <span
  m="384340">to</span> <span m="384490">the</span> <span m="384600">K-th</span>
  <span m="384990">power</span> <span m="385340">times</span> <span
  m="385620">the</span> <span m="385720">second</span> <span
  m="386200">eigenvector</span> <span m="386800">and</span> <span
  m="386920">so</span> <span m="387080">on.</span></p><p><span
  m="387430">A</span> <span m="389400">--</span> <span m="389650">just</span>
  <span m="390140">--</span> <span m="390700">my</span> <span
  m="390870">conscience</span> <span m="391470">always</span> <span
  m="391860">makes</span> <span m="392150">me</span> <span m="392300">say</span>
  <span m="392570">at</span> <span m="392670">least</span> <span
  m="392950">once</span> <span m="393360">per</span> <span
  m="393580">lecture</span> <span m="394380">that</span> <span
  m="395280">this</span> <span m="396150">requires</span> <span
  m="397620">a</span> <span m="398100">complete</span> <span
  m="398570">set</span> <span m="398780">of</span> <span
  m="398920">eigenvectors,</span> <span m="400060">otherwise</span> <span
  m="400960">we</span> <span m="401100">might</span> <span m="401370">not</span>
  <span m="401620">be</span> <span m="401810">able</span> <span
  m="401990">to</span> <span m="402090">expand</span> <span m="402640">u0</span>
  <span m="403080">in</span> <span m="403170">the</span> <span
  m="403320">eigenvectors</span> <span m="404020">and</span> <span
  m="404110">we</span> <span m="404240">couldn't</span> <span
  m="404500">get</span> <span m="404680">started.</span></p><p><span
  m="405840">But</span> <span m="406090">once</span> <span
  m="406390">we're</span> <span m="406550">started</span> <span
  m="407020">with</span> <span m="407190">u0</span> <span m="407870">when</span>
  <span m="408090">K</span> <span m="408340">is</span> <span
  m="408500">zero,</span> <span m="409410">then</span> <span
  m="410290">every</span> <span m="410910">A</span> <span
  m="412030">brings</span> <span m="412380">in</span> <span
  m="412600">these</span> <span m="412830">lambdas.</span></p><p><span
  m="413880">And</span> <span m="414080">now</span> <span m="414270">you</span>
  <span m="414450">can</span> <span m="414640">see</span> <span
  m="414850">what</span> <span m="415020">the</span> <span
  m="415130">steady</span> <span m="415480">state</span> <span
  m="415770">is</span> <span m="415920">going</span> <span m="416080">to</span>
  <span m="416140">be.</span></p><p><span m="416830">If</span> <span
  m="417050">lambda</span> <span m="417530">one</span> <span
  m="417830">is</span> <span m="417980">one</span> <span m="418700">--</span>
  <span m="419100">so</span> <span m="419300">lambda</span> <span
  m="419780">one</span> <span m="420040">equals</span> <span
  m="420390">one</span> <span m="421630">to</span> <span m="422140">the</span>
  <span m="422290">K-th</span> <span m="422670">power</span> <span
  m="424060">and</span> <span m="424660">these</span> <span
  m="424890">other</span> <span m="425200">eigenvalues</span> <span
  m="426280">are</span> <span m="427150">smaller</span> <span
  m="427900">than</span> <span m="428060">one</span> <span m="428620">--</span>
  <span m="430280">so</span> <span m="430480">I've</span> <span
  m="430800">sort</span> <span m="431030">of</span> <span
  m="431370">scratched</span> <span m="432250">over</span> <span
  m="432540">the</span> <span m="432700">equation</span> <span
  m="433310">there</span> <span m="433680">to</span> <span m="433990">--</span>
  <span m="434560">we</span> <span m="434910">had</span> <span
  m="435250">this</span> <span m="435620">term,</span> <span
  m="436110">but</span> <span m="436380">what</span> <span
  m="436600">happens</span> <span m="437040">to</span> <span
  m="437120">this</span> <span m="437400">term</span> <span m="437860">--</span>
  <span m="438260">if</span> <span m="438530">the</span> <span
  m="438640">lambda's</span> <span m="439210">smaller</span> <span
  m="439560">than</span> <span m="439750">one,</span> <span
  m="440210">then</span> <span m="440530">the</span> <span m="440770">--</span>
  <span m="440860">when</span> <span m="441110">--</span> <span
  m="441180">as</span> <span m="441370">we</span> <span m="441510">take</span>
  <span m="441880">powers,</span> <span m="442470">as</span> <span
  m="442630">we</span> <span m="443170">iterate</span> <span
  m="444200">as</span> <span m="444450">we</span> <span m="444820">--</span>
  <span m="445160">as</span> <span m="445410">we</span> <span
  m="445910">go</span> <span m="446070">forward</span> <span
  m="446540">in</span> <span m="446700">time,</span> <span
  m="447370">this</span> <span m="447750">goes</span> <span m="448020">to</span>
  <span m="448110">zero,</span> <span m="449210">Can</span> <span
  m="449600">I</span> <span m="449690">just</span> <span m="450150">--</span>
  <span m="450760">having</span> <span m="451030">scratched</span> <span
  m="451510">over</span> <span m="451720">it,</span> <span m="451790">I</span>
  <span m="451870">might</span> <span m="452070">as</span> <span
  m="452180">well</span> <span m="452370">scratch</span> <span
  m="452860">right?</span> <span m="452880">further.</span></p><p><span
  m="454050">That</span> <span m="454430">term</span> <span
  m="454830">and</span> <span m="454940">all</span> <span m="455110">the</span>
  <span m="455260">other</span> <span m="455470">terms</span> <span
  m="455870">are</span> <span m="455960">going</span> <span m="456240">to</span>
  <span m="456300">zero</span> <span m="456880">because</span> <span
  m="457680">all</span> <span m="457960">the</span> <span
  m="458110">other</span> <span m="458350">eigenvalues</span> <span
  m="459020">are</span> <span m="459130">smaller</span> <span
  m="459540">than</span> <span m="459750">one</span> <span m="460180">and</span>
  <span m="460500">the</span> <span m="460590">steady</span> <span
  m="460990">state</span> <span m="461960">that</span> <span
  m="462580">we're</span> <span m="462740">approaching</span> <span
  m="463500">is</span> <span m="463970">just</span> <span m="464810">--</span>
  <span m="465440">whatever</span> <span m="465960">there</span> <span
  m="466140">was</span> <span m="466740">--</span> <span m="467240">this</span>
  <span m="467490">was</span> <span m="467760">--</span> <span
  m="467800">this</span> <span m="468050">was</span> <span m="468240">the</span>
  <span m="468690">--</span> <span m="468780">this</span> <span
  m="468980">is</span> <span m="469150">the</span> <span m="469510">x1</span>
  <span m="470310">part</span> <span m="471440">of</span> <span
  m="473170">un-</span> <span m="474280">of</span> <span m="474690">the</span>
  <span m="474830">initial</span> <span m="475190">condition</span> <span
  m="475700">u0</span> <span m="475890">--</span> <span m="476990">is</span>
  <span m="477890">the</span> <span m="478310">steady</span> <span
  m="478890">state.</span></p><p><span m="485120">This</span> <span
  m="485370">much</span> <span m="485660">we</span> <span m="485850">know</span>
  <span m="486190">from</span> <span m="486650">general</span> <span
  m="487420">--</span> <span m="487900">from</span> <span m="488100">--</span>
  <span m="488130">you</span> <span m="488240">know,</span> <span
  m="488350">what</span> <span m="488540">we've</span> <span
  m="488750">already</span> <span m="489120">done.</span></p><p><span
  m="491390">So</span> <span m="491620">I</span> <span m="491910">want</span>
  <span m="492160">to</span> <span m="492240">see</span> <span
  m="492650">why</span> <span m="493450">--</span> <span m="493490">let's</span>
  <span m="494070">at</span> <span m="494240">least</span> <span
  m="494530">see</span> <span m="494830">number</span> <span
  m="495120">one,</span> <span m="495740">why</span> <span m="496180">one</span>
  <span m="496520">is</span> <span m="496680">an</span> <span
  m="496850">eigenvalue.</span> <span m="498160">And</span> <span
  m="498850">then</span> <span m="499010">there's</span> <span
  m="499190">actually</span> <span m="499980">--</span> <span
  m="500580">in</span> <span m="500760">this</span> <span
  m="501020">chapter</span> <span m="501490">we're</span> <span
  m="501690">interested</span> <span m="502160">not</span> <span
  m="502360">only</span> <span m="502590">in</span> <span
  m="502760">eigenvalues,</span> <span m="503370">but</span> <span
  m="503510">also</span> <span m="503820">eigenvectors.</span></p><p><span
  m="505390">And</span> <span m="505640">there's</span> <span
  m="505810">something</span> <span m="506250">special</span> <span
  m="506820">about</span> <span m="507120">the</span> <span
  m="507270">eigenvector.</span></p><p><span m="508760">Let</span> <span
  m="508930">me</span> <span m="509060">write</span> <span
  m="509300">down</span> <span m="509500">what</span> <span
  m="509690">that</span> <span m="509900">is.</span></p><p><span
  m="510800">The</span> <span m="511080">eigenvector</span> <span
  m="512870">x1</span> <span m="515440">--</span> <span m="516700">x1</span>
  <span m="517010">is</span> <span m="517140">the</span> <span
  m="517299">eigenvector</span> <span m="518679">and</span> <span
  m="519380">all</span> <span m="519669">its</span> <span
  m="519929">components</span> <span m="520610">are</span> <span
  m="520750">positive,</span> <span m="521909">so</span> <span
  m="522330">the</span> <span m="522480">steady</span> <span
  m="522890">state</span> <span m="523559">is</span> <span
  m="524300">positive,</span> <span m="526360">if</span> <span
  m="527520">the</span> <span m="527660">start</span> <span
  m="528090">was.</span></p><p><span m="529100">If</span> <span
  m="529270">the</span> <span m="529370">start</span> <span
  m="529750">was</span> <span m="529980">--</span> <span m="530130">so</span>
  <span m="530530">--</span> <span m="531480">well,</span> <span
  m="531780">actually,</span> <span m="532620">in</span> <span
  m="533400">general,</span> <span m="534030">I</span> <span
  m="534190">--</span> <span m="534780">this</span> <span
  m="535670">might</span> <span m="536330">have</span> <span m="536640">a</span>
  <span m="537010">--</span> <span m="537050">might</span> <span
  m="537280">have</span> <span m="537530">some</span> <span
  m="538600">component</span> <span m="539600">zero</span> <span
  m="540170">always,</span> <span m="540710">but</span> <span
  m="540940">no</span> <span m="541390">negative</span> <span
  m="541910">components</span> <span m="542550">in</span> <span
  m="542670">that</span> <span m="542890">eigenvector.</span></p><p><span
  m="543880">Okay.</span> <span m="544410">Can</span> <span m="544810">I</span>
  <span m="545630">come</span> <span m="546360">to</span> <span
  m="546500">that</span> <span m="546790">point?</span></p><p><span
  m="548470">How</span> <span m="548760">can</span> <span m="548980">I</span>
  <span m="549080">look</span> <span m="549360">at</span> <span
  m="549450">that</span> <span m="549680">matrix</span> <span
  m="550250">--</span> <span m="551370">so</span> <span m="551550">that</span>
  <span m="551750">was</span> <span m="551920">just</span> <span
  m="552190">an</span> <span m="552350">example.</span></p><p><span
  m="555280">How</span> <span m="555650">could</span> <span m="555920">I</span>
  <span m="556680">be</span> <span m="557210">sure</span> <span
  m="558010">--</span> <span m="558430">how</span> <span m="558810">can</span>
  <span m="559010">I</span> <span m="559270">see</span> <span
  m="560070">that</span> <span m="560340">a</span> <span
  m="560400">matrix</span> <span m="560980">--</span> <span m="561000">if</span>
  <span m="561100">the</span> <span m="561240">columns</span> <span
  m="561850">add</span> <span m="562270">to</span> <span m="562390">zero</span>
  <span m="563230">--</span> <span m="563280">add</span> <span
  m="563520">to</span> <span m="563630">one,</span> <span
  m="564140">sorry</span> <span m="564590">--</span> <span m="564750">if</span>
  <span m="564890">the</span> <span m="565010">columns</span> <span
  m="565470">add</span> <span m="565690">to</span> <span m="565810">one,</span>
  <span m="567190">this</span> <span m="568380">property</span> <span
  m="569100">means</span> <span m="569860">that</span> <span
  m="570290">lambda</span> <span m="570930">equal</span> <span
  m="571320">one</span> <span m="571590">is</span> <span m="571750">an</span>
  <span m="571900">eigenvalue.</span></p><p><span m="572780">Okay.</span> <span
  m="573540">So</span> <span m="574760">let's</span> <span
  m="575540">just</span> <span m="575730">think</span> <span
  m="575940">that</span> <span m="576160">through.</span></p><p><span
  m="577080">What</span> <span m="577250">I</span> <span
  m="577500">saying</span> <span m="578150">about</span> <span
  m="578900">--</span> <span m="579040">let</span> <span m="579240">me</span>
  <span m="579510">ca-</span> <span m="580030">let</span> <span
  m="580340">me</span> <span m="580490">look</span> <span m="580700">at</span>
  <span m="580820">A,</span> <span m="581760">and</span> <span
  m="582400">if</span> <span m="582530">I</span> <span m="582700">believe</span>
  <span m="583260">that</span> <span m="583420">one</span> <span
  m="583800">is</span> <span m="583960">an</span> <span
  m="584100">eigenvalue,</span> <span m="584940">then</span> <span
  m="585180">I</span> <span m="585300">should</span> <span m="585550">be</span>
  <span m="585770">able</span> <span m="585940">to</span> <span
  m="586050">subtract</span> <span m="586700">off</span> <span
  m="587020">one</span> <span m="587460">times</span> <span
  m="587810">the</span> <span m="587950">identity</span> <span
  m="588990">and</span> <span m="589590">then</span> <span m="589770">I</span>
  <span m="589850">would</span> <span m="590050">get</span> <span
  m="590250">a</span> <span m="590310">matrix</span> <span
  m="591040">that's,</span> <span m="591460">what,</span> <span
  m="591720">-.9,</span> <span m="596150">-.01</span> <span
  m="596980">and</span> <span m="597460">-.6</span> <span m="598250">--</span>
  <span m="599160">wh-</span> <span m="599440">I</span> <span
  m="599680">took</span> <span m="599990">the</span> <span
  m="600090">ones</span> <span m="600430">away</span> <span
  m="601070">and</span> <span m="601350">the</span> <span
  m="601550">other</span> <span m="601800">parts,</span> <span
  m="602190">of</span> <span m="602310">course,</span> <span
  m="602700">are</span> <span m="603010">still</span> <span
  m="603510">what</span> <span m="603670">they</span> <span
  m="603790">were,</span> <span m="605380">and</span> <span
  m="606630">this</span> <span m="606830">is</span> <span
  m="606970">still</span> <span m="607490">.2</span> <span m="608550">and</span>
  <span m="608790">.7</span> <span m="610170">and</span> <span
  m="611270">--</span> <span m="611430">okay,</span> <span
  m="612150">what's</span> <span m="613010">--</span> <span
  m="614200">what's</span> <span m="614400">up</span> <span
  m="614570">with</span> <span m="614710">this</span> <span
  m="614940">matrix</span> <span m="615470">now?</span></p><p><span
  m="615700">I've</span> <span m="615850">shifted</span> <span
  m="616420">the</span> <span m="616540">matrix,</span> <span
  m="617050">this</span> <span m="617270">Markov</span> <span
  m="617750">matrix</span> <span m="618300">by</span> <span
  m="618720">one,</span> <span m="619380">by</span> <span m="619560">the</span>
  <span m="619710">identity,</span> <span m="622940">and</span> <span
  m="623160">what</span> <span m="623330">do</span> <span m="623440">I</span>
  <span m="623530">want</span> <span m="623710">to</span> <span
  m="623770">prove?</span></p><p><span m="624350">I</span> <span
  m="625370">--</span> <span m="626390">what</span> <span m="626880">is</span>
  <span m="627020">it</span> <span m="627160">that</span> <span
  m="627310">I</span> <span m="627410">believe</span> <span
  m="627810">this</span> <span m="628030">matrix</span> <span
  m="628760">--</span> <span m="628940">about</span> <span
  m="629270">this</span> <span m="629450">matrix?</span></p><p><span
  m="630760">I</span> <span m="630880">believe</span> <span
  m="631220">it's</span> <span m="631380">singular.</span></p><p><span
  m="633190">Singular</span> <span m="633780">will</span> <span
  m="634100">--</span> <span m="634410">if</span> <span m="634640">A</span>
  <span m="635050">minus</span> <span m="635540">I</span> <span
  m="635850">is</span> <span m="636010">singular,</span> <span
  m="636580">that</span> <span m="636850">tells</span> <span
  m="637220">me</span> <span m="637660">that</span> <span m="637950">one</span>
  <span m="638300">is</span> <span m="638460">an</span> <span
  m="638610">eigenvalue,</span> <span m="639210">right?</span></p><p><span
  m="640020">The</span> <span m="640200">eigenvalues</span> <span
  m="641170">are</span> <span m="641340">the</span> <span
  m="641500">numbers</span> <span m="641960">that</span> <span
  m="642130">I</span> <span m="642250">subtract</span> <span
  m="642880">off</span> <span m="643390">--</span> <span m="643420">the</span>
  <span m="643560">shifts</span> <span m="644290">--</span> <span
  m="645010">the</span> <span m="645130">numbers</span> <span
  m="645420">that</span> <span m="645560">I</span> <span
  m="645640">subtract</span> <span m="646160">from</span> <span
  m="646310">the</span> <span m="646400">diagonal</span> <span
  m="647300">--</span> <span m="647880">to</span> <span m="648020">make</span>
  <span m="648240">it</span> <span m="648370">singular.</span></p><p><span
  m="648810">Now</span> <span m="648980">why</span> <span m="649250">is</span>
  <span m="649380">that</span> <span m="649580">matrix</span> <span
  m="650030">singular?</span></p><p><span m="650610">I</span> <span
  m="652190">--</span> <span m="653780">we</span> <span m="654190">could</span>
  <span m="654370">compute</span> <span m="654750">its</span> <span
  m="654920">determinant,</span> <span m="655570">but</span> <span
  m="656400">we</span> <span m="656560">want</span> <span m="656810">to</span>
  <span m="656880">see</span> <span m="657140">a</span> <span
  m="657210">reason</span> <span m="658160">that</span> <span
  m="658590">would</span> <span m="658760">work</span> <span
  m="659060">for</span> <span m="659240">every</span> <span
  m="659520">Markov</span> <span m="660000">matrix</span> <span
  m="660550">not</span> <span m="660820">just</span> <span
  m="661220">this</span> <span m="661930">particular</span> <span
  m="662950">random</span> <span m="663980">example.</span></p><p><span
  m="665550">So</span> <span m="665770">what</span> <span m="666130">is</span>
  <span m="666290">it</span> <span m="666420">about</span> <span
  m="666690">that</span> <span m="666920">matrix?</span></p><p><span
  m="667780">Well,</span> <span m="668170">I</span> <span
  m="668290">guess</span> <span m="668640">you</span> <span
  m="668780">could</span> <span m="668920">look</span> <span
  m="669110">at</span> <span m="669190">its</span> <span
  m="669370">columns</span> <span m="669910">now</span> <span
  m="670610">--</span> <span m="671040">what</span> <span m="671180">do</span>
  <span m="671270">they</span> <span m="671440">add</span> <span
  m="671660">up</span> <span m="671820">to?</span></p><p><span
  m="673010">Zero.</span></p><p><span m="673390">The</span> <span
  m="673550">columns</span> <span m="674040">add</span> <span
  m="674290">to</span> <span m="674390">zero,</span> <span m="675620">so</span>
  <span m="680280">all</span> <span m="680680">columns</span> <span
  m="681500">--</span> <span m="681660">let</span> <span m="681870">me</span>
  <span m="681990">put</span> <span m="682220">all</span> <span
  m="682740">columns</span> <span m="683250">now</span> <span
  m="683860">of</span> <span m="684240">--</span> <span m="684310">of</span>
  <span m="684670">--</span> <span m="685240">of</span> <span
  m="686150">A</span> <span m="686810">minus</span> <span m="687260">I</span>
  <span m="688470">add</span> <span m="689800">to</span> <span
  m="690030">zero,</span> <span m="691080">and</span> <span
  m="691970">then</span> <span m="692230">I</span> <span m="692450">want</span>
  <span m="692700">to</span> <span m="694090">realize</span> <span
  m="695430">that</span> <span m="695770">this</span> <span
  m="696150">means</span> <span m="696870">A</span> <span
  m="697350">minus</span> <span m="697870">I</span> <span m="698770">is</span>
  <span m="699860">singular.</span> <span m="705400">Okay.</span> <span
  m="707790">Why?</span></p><p><span m="709560">So</span> <span
  m="709720">I</span> <span m="709800">could</span> <span m="709970">I</span>
  <span m="709990">--</span> <span m="710230">you</span> <span
  m="710520">know,</span> <span m="710640">that</span> <span
  m="710810">could</span> <span m="710970">be</span> <span m="711100">a</span>
  <span m="711250">quiz</span> <span m="711780">question,</span> <span
  m="712210">a</span> <span m="712280">sort</span> <span m="712470">of</span>
  <span m="712610">theoretical</span> <span m="713270">quiz</span> <span
  m="713590">question.</span></p><p><span m="714280">If</span> <span
  m="714410">I</span> <span m="714480">give</span> <span m="714730">you</span>
  <span m="714860">a</span> <span m="714930">matrix</span> <span
  m="715490">and</span> <span m="715590">I</span> <span m="715690">tell</span>
  <span m="715920">you</span> <span m="716070">all</span> <span
  m="716300">its</span> <span m="716450">columns</span> <span
  m="716900">add</span> <span m="717190">to</span> <span m="717260">zero,</span>
  <span m="718650">give</span> <span m="719530">me</span> <span
  m="719660">a</span> <span m="719730">reason,</span> <span
  m="720740">because</span> <span m="721310">it</span> <span
  m="721420">is</span> <span m="721630">true,</span> <span
  m="722440">that</span> <span m="722810">the</span> <span
  m="722910">matrix</span> <span m="723460">is</span> <span
  m="723590">singular.</span></p><p><span m="726270">Okay.</span></p><p><span
  m="726940">I</span> <span m="727020">guess</span> <span
  m="727370">actually</span> <span m="727950">--</span> <span
  m="727970">now</span> <span m="728200">what</span> <span m="728470">--</span>
  <span m="729290">I</span> <span m="729390">think</span> <span
  m="729680">of</span> <span m="729890">--</span> <span m="729910">you</span>
  <span m="729990">know,</span> <span m="730110">I'm</span> <span
  m="730290">thinking</span> <span m="730530">of</span> <span
  m="730640">two</span> <span m="730860">or</span> <span m="730960">three</span>
  <span m="731220">ways</span> <span m="731680">to</span> <span
  m="731820">see</span> <span m="732110">that.</span></p><p><span
  m="737370">How</span> <span m="737710">would</span> <span
  m="737930">you</span> <span m="738040">do</span> <span
  m="738260">it?</span></p><p><span m="738410">We</span> <span
  m="738540">don't</span> <span m="738690">want</span> <span
  m="738850">to</span> <span m="738940">take</span> <span m="739200">its</span>
  <span m="739390">determinant</span> <span
  m="740370">somehow.</span></p><p><span m="741880">For</span> <span
  m="742020">the</span> <span m="742130">matrix</span> <span
  m="742650">to</span> <span m="742760">be</span> <span
  m="742950">singular,</span> <span m="743780">well,</span> <span
  m="744520">it</span> <span m="745030">means</span> <span
  m="745490">that</span> <span m="745750">these</span> <span
  m="746230">three</span> <span m="746690">columns</span> <span
  m="747900">are</span> <span m="748790">dependent,</span> <span
  m="749490">right?</span></p><p><span m="751180">The</span> <span
  m="751290">determinant</span> <span m="751790">will</span> <span
  m="751950">be</span> <span m="752090">zero</span> <span m="752440">when</span>
  <span m="752590">those</span> <span m="752820">three</span> <span
  m="753020">columns</span> <span m="753530">are</span> <span
  m="753620">dependent.</span></p><p><span m="754260">You</span> <span
  m="754390">see,</span> <span m="754590">we're</span> <span
  m="754870">--</span> <span m="755200">we're</span> <span m="755420">at</span>
  <span m="755520">a</span> <span m="755590">point</span> <span
  m="755870">in</span> <span m="755950">this</span> <span
  m="756160">course,</span> <span m="756480">now,</span> <span
  m="756650">where</span> <span m="756840">we</span> <span
  m="757030">have</span> <span m="757690">several</span> <span
  m="758490">ways</span> <span m="758830">to</span> <span m="758950">look</span>
  <span m="759170">at</span> <span m="759260">an</span> <span
  m="759430">idea.</span></p><p><span m="760100">We</span> <span
  m="760210">can</span> <span m="760360">take</span> <span m="760620">the</span>
  <span m="760710">determinant</span> <span m="761350">--</span> <span
  m="761370">here</span> <span m="761570">we</span> <span
  m="761690">don't</span> <span m="761870">want</span> <span
  m="762110">to.</span></p><p><span m="762390">B-</span> <span
  m="763450">but</span> <span m="763610">we</span> <span m="763740">met</span>
  <span m="764030">singular</span> <span m="764530">before</span> <span
  m="764930">that</span> <span m="765460">--</span> <span
  m="765810">those</span> <span m="766110">columns</span> <span
  m="766570">are</span> <span m="766690">dependent.</span></p><p><span
  m="767830">So</span> <span m="768070">how</span> <span m="768300">do</span>
  <span m="768440">I</span> <span m="768580">see</span> <span
  m="768930">that</span> <span m="769120">those</span> <span
  m="769480">columns</span> <span m="769990">are</span> <span
  m="770080">dependent?</span></p><p><span m="770670">They</span> <span
  m="770840">all</span> <span m="771140">add</span> <span m="771380">to</span>
  <span m="771480">zero.</span></p><p><span m="777020">Let's</span> <span
  m="777320">see,</span> <span m="777730">whew</span> <span m="779080">--</span>
  <span m="780440">well,</span> <span m="781290">oh,</span> <span
  m="781520">actually,</span> <span m="781990">what</span> <span
  m="782320">--</span> <span m="785070">another</span> <span
  m="785470">thing</span> <span m="785710">I</span> <span m="785800">know</span>
  <span m="786150">is</span> <span m="786340">that</span> <span
  m="786480">the</span> <span m="786650">--</span> <span m="787010">I</span>
  <span m="787210">would</span> <span m="787690">like</span> <span
  m="787920">to</span> <span m="788030">be</span> <span m="788250">able</span>
  <span m="788420">to</span> <span m="788490">show</span> <span
  m="788840">is</span> <span m="788970">that</span> <span m="789100">the</span>
  <span m="789220">rows</span> <span m="789640">are</span> <span
  m="789740">dependent.</span></p><p><span m="791410">Maybe</span> <span
  m="791690">that's</span> <span m="791990">easier.</span></p><p><span
  m="794250">If</span> <span m="794440">I</span> <span m="794540">know</span>
  <span m="794820">that</span> <span m="794980">all</span> <span
  m="795190">the</span> <span m="795300">columns</span> <span
  m="795760">add</span> <span m="795940">to</span> <span m="796010">zero,</span>
  <span m="796370">that's</span> <span m="796900">my</span> <span
  m="797090">information,</span> <span m="798040">how</span> <span
  m="798480">do</span> <span m="798650">I</span> <span m="798830">see</span>
  <span m="799570">that</span> <span m="799930">those</span> <span
  m="800540">three</span> <span m="800960">rows</span> <span
  m="801540">are</span> <span m="802170">linearly</span> <span
  m="802890">dependent?</span></p><p><span m="805120">What</span> <span
  m="805300">--</span> <span m="805330">what</span> <span
  m="805590">combination</span> <span m="806390">of</span> <span
  m="806520">those</span> <span m="806830">rows</span> <span
  m="807460">gives</span> <span m="807830">the</span> <span
  m="807920">zero</span> <span m="808680">row?</span></p><p><span
  m="810210">How</span> <span m="810480">--</span> <span m="810500">how</span>
  <span m="810770">could</span> <span m="810990">I</span> <span
  m="811080">combine</span> <span m="811670">those</span> <span
  m="812070">three</span> <span m="812400">rows</span> <span
  m="812900">--</span> <span m="812920">those</span> <span
  m="813110">three</span> <span m="813320">row</span> <span
  m="813540">vectors</span> <span m="815030">to</span> <span
  m="815950">produce</span> <span m="816380">the</span> <span
  m="816480">zero</span> <span m="817410">row</span> <span
  m="818070">vector?</span></p><p><span m="818930">And</span> <span
  m="819090">that</span> <span m="819270">would</span> <span
  m="819430">tell</span> <span m="819680">me</span> <span
  m="820190">those</span> <span m="820620">rows</span> <span
  m="821180">are</span> <span m="821620">dependent,</span> <span
  m="822360">therefore</span> <span m="822650">the</span> <span
  m="822800">columns</span> <span m="823240">are</span> <span
  m="823320">dependent,</span> <span m="823910">the</span> <span
  m="824010">matrix</span> <span m="824500">is</span> <span
  m="824620">singular,</span> <span m="825070">the</span> <span
  m="825200">determinant</span> <span m="825790">is</span> <span
  m="825920">zero</span> <span m="826460">--</span> <span
  m="826530">well,</span> <span m="826940">you</span> <span
  m="827110">see</span> <span m="827310">it.</span></p><p><span
  m="827890">I</span> <span m="828050">just</span> <span m="828260">add</span>
  <span m="828540">the</span> <span m="828630">rows.</span></p><p><span
  m="829010">One</span> <span m="829540">times</span> <span
  m="829870">that</span> <span m="830090">row</span> <span
  m="830380">plus</span> <span m="830650">one</span> <span
  m="831010">times</span> <span m="831310">that</span> <span
  m="831520">row</span> <span m="831760">plus</span> <span m="831990">one</span>
  <span m="832320">times</span> <span m="832610">that</span> <span
  m="832820">row</span> <span m="833210">--</span> <span m="833770">it's</span>
  <span m="834660">the</span> <span m="835160">zero</span> <span
  m="835540">row.</span></p><p><span m="836990">The</span> <span
  m="837130">rows</span> <span m="837500">are</span> <span
  m="837590">dependent.</span></p><p><span m="838960">In</span> <span
  m="839180">a</span> <span m="839250">way,</span> <span m="839640">that</span>
  <span m="839870">one</span> <span m="840450">one</span> <span
  m="840930">one,</span> <span m="842050">because</span> <span
  m="842740">it's</span> <span m="842900">multiplying</span> <span
  m="843470">the</span> <span m="843580">rows,</span> <span m="844300">is</span>
  <span m="844530">like</span> <span m="845570">an</span> <span
  m="846640">eigenvector</span> <span m="847170">in</span> <span
  m="847320">the</span> <span m="847550">--</span> <span m="847810">it's</span>
  <span m="848030">in</span> <span m="848150">the</span> <span
  m="848280">left</span> <span m="848640">null</span> <span
  m="848830">space,</span> <span m="849230">right?</span></p><p><span
  m="850700">One</span> <span m="851040">one</span> <span m="851320">one</span>
  <span m="851630">is</span> <span m="851770">in</span> <span
  m="851890">the</span> <span m="852000">left</span> <span
  m="852340">null</span> <span m="852520">space.</span></p><p><span
  m="852870">It's</span> <span m="853230">singular</span> <span
  m="853750">because</span> <span m="857140">the</span> <span
  m="857270">rows</span> <span m="858080">are</span> <span
  m="859250">dependent</span> <span m="860820">--</span> <span
  m="863190">and</span> <span m="863480">can</span> <span m="863670">I</span>
  <span m="863750">just</span> <span m="864030">keep</span> <span
  m="864300">the</span> <span m="864440">reasoning</span> <span
  m="864950">going?</span></p><p><span m="865380">Because</span> <span
  m="867250">this</span> <span m="868310">vector</span> <span
  m="869710">one</span> <span m="871040">one</span> <span m="871570">one</span>
  <span m="872290">is</span> <span m="872760">--</span> <span
  m="872790">it's</span> <span m="873000">not</span> <span m="873240">in</span>
  <span m="873350">the</span> <span m="873470">null</span> <span
  m="873710">space</span> <span m="874140">of</span> <span m="874250">the</span>
  <span m="874360">matrix,</span> <span m="874940">but</span> <span
  m="875120">it's</span> <span m="875310">in</span> <span m="875440">the</span>
  <span m="875560">null</span> <span m="875750">space</span> <span
  m="876040">of</span> <span m="876130">the</span> <span
  m="876260">transpose</span> <span m="877100">--</span> <span
  m="877410">is</span> <span m="877670">in</span> <span m="878410">the</span>
  <span m="879020">null</span> <span m="879320">space</span> <span
  m="880450">of</span> <span m="881340">the</span> <span
  m="881540">transpose.</span></p><p><span m="883160">And</span> <span
  m="883400">that's</span> <span m="883670">good</span> <span
  m="883840">enough.</span> <span m="885600">If</span> <span
  m="885890">we</span> <span m="886100">have</span> <span m="886290">a</span>
  <span m="886350">square</span> <span m="886740">matrix</span> <span
  m="887540">--</span> <span m="887570">if</span> <span m="887690">we</span>
  <span m="887780">have</span> <span m="887880">a</span> <span
  m="887980">square</span> <span m="888340">matrix</span> <span
  m="888890">and</span> <span m="889030">the</span> <span m="889120">rows</span>
  <span m="889510">are</span> <span m="889600">dependent,</span> <span
  m="890490">that</span> <span m="890880">matrix</span> <span
  m="891370">is</span> <span m="891500">singular.</span></p><p><span
  m="892930">So</span> <span m="893580">it</span> <span m="894000">turned</span>
  <span m="894350">out</span> <span m="894740">that</span> <span
  m="895090">the</span> <span m="895560">immediate</span> <span
  m="896730">guy</span> <span m="897370">we</span> <span m="897570">could</span>
  <span m="897780">identify</span> <span m="898630">was</span> <span
  m="898950">one</span> <span m="899200">one</span> <span
  m="899410">one.</span></p><p><span m="900470">Of</span> <span
  m="900610">course,</span> <span m="901680">the</span> <span
  m="902820">--</span> <span m="904650">there</span> <span
  m="904770">will</span> <span m="904930">be</span> <span
  m="905090">somebody</span> <span m="905570">in</span> <span
  m="905730">the</span> <span m="905840">null</span> <span
  m="906060">space,</span></p><p><span m="906480">too.</span> <span
  m="907300">And</span> <span m="908070">actually,</span> <span
  m="908540">who</span> <span m="908890">will</span> <span m="909190">it</span>
  <span m="909300">be?</span></p><p><span m="910280">So</span> <span
  m="910520">what's</span> <span m="911070">--</span> <span m="911260">so</span>
  <span m="911870">--</span> <span m="913110">so</span> <span
  m="913390">now</span> <span m="913590">I</span> <span m="913720">want</span>
  <span m="913910">to</span> <span m="913960">ask</span> <span
  m="914380">about</span> <span m="914660">the</span> <span
  m="914780">null</span> <span m="915040">space</span> <span
  m="915450">of</span> <span m="915660">--</span> <span m="915830">of</span>
  <span m="915990">the</span> <span m="916090">matrix</span> <span
  m="916580">itself.</span></p><p><span m="917400">What</span> <span
  m="918090">combination</span> <span m="918980">of</span> <span
  m="919080">the</span> <span m="919200">columns</span> <span
  m="919790">gives</span> <span m="920070">zero?</span></p><p><span
  m="920890">I</span> <span m="921040">--</span> <span m="921200">I</span> <span
  m="921480">don't</span> <span m="921650">want</span> <span
  m="921800">to</span> <span m="921870">compute</span> <span
  m="922280">it</span> <span m="922340">because</span> <span m="922610">I</span>
  <span m="922690">just</span> <span m="922910">made</span> <span
  m="923150">up</span> <span m="923270">this</span> <span
  m="923450">matrix</span> <span m="923900">and</span> <span
  m="923980">--</span> <span m="924830">it</span> <span m="925780">will</span>
  <span m="925970">--</span> <span m="926130">it</span> <span
  m="926190">would</span> <span m="926360">take</span> <span
  m="926570">me</span> <span m="926680">a</span> <span m="926760">while</span>
  <span m="927560">--</span> <span m="928020">it</span> <span
  m="928130">looks</span> <span m="928410">sort</span> <span
  m="928610">of</span> <span m="928770">doable</span> <span
  m="929270">because</span> <span m="929500">it's</span> <span
  m="929690">three</span> <span m="929890">by</span> <span
  m="930100">three</span> <span m="930500">but</span> <span
  m="930810">wh-</span> <span m="931390">my</span> <span m="931610">point</span>
  <span m="931950">is,</span> <span m="932410">what</span> <span
  m="933710">--</span> <span m="934720">what</span> <span
  m="935090">vector</span> <span m="935510">is</span> <span m="935660">it</span>
  <span m="935950">if</span> <span m="936150">we</span> <span
  m="936330">--</span> <span m="936410">once</span> <span
  m="936740">we've</span> <span m="936910">found</span> <span
  m="937260">it,</span> <span m="937350">what</span> <span
  m="937520">have</span> <span m="937620">we</span> <span m="937780">got</span>
  <span m="938440">that's</span> <span m="938830">in</span> <span
  m="939000">the</span> <span m="939380">--</span> <span m="939410">in</span>
  <span m="939550">the</span> <span m="939660">null</span> <span
  m="939870">space</span> <span m="940230">of</span> <span
  m="940360">A?</span></p><p><span m="941360">It's</span> <span
  m="941600">the</span> <span m="941770">eigenvector,</span> <span
  m="942600">right?</span></p><p><span m="944060">That's</span> <span
  m="944320">where</span> <span m="944610">we</span> <span
  m="944750">find</span> <span m="945060">X</span> <span
  m="945290">one.</span></p><p><span m="946060">Then</span> <span
  m="947480">X</span> <span m="948480">one,</span> <span m="949030">the</span>
  <span m="949370">eigenvector,</span> <span m="950770">is</span> <span
  m="951330">in</span> <span m="951500">the</span> <span m="951610">null</span>
  <span m="951820">space</span> <span m="952160">of</span> <span
  m="952300">A.</span> <span m="954350">That's</span> <span
  m="954640">the</span> <span m="954820">eigenvector</span> <span
  m="955650">corresponding</span> <span m="956550">to</span> <span
  m="956690">the</span> <span m="956860">eigenvalue</span></p><p><span
  m="957690">one.</span> <span m="958470">Right?</span></p><p><span
  m="958980">That's</span> <span m="959190">how</span> <span
  m="959330">we</span> <span m="959460">find</span> <span
  m="959810">eigenvectors.</span></p><p><span m="961330">So</span> <span
  m="961840">those</span> <span m="962400">three</span> <span
  m="962650">columns</span> <span m="963120">must</span> <span
  m="963410">be</span> <span m="963570">dependent</span> <span
  m="964410">--</span> <span m="965280">some</span> <span
  m="965600">combination</span> <span m="966240">of</span> <span
  m="966350">columns</span> <span m="966860">--</span> <span
  m="966890">of</span> <span m="967030">those</span> <span
  m="967280">three</span> <span m="967480">columns</span> <span
  m="967900">is</span> <span m="968090">the</span> <span m="968180">zero</span>
  <span m="968560">column</span> <span m="969250">and</span> <span
  m="969620">that</span> <span m="970170">--</span> <span m="970200">the</span>
  <span m="970360">three</span> <span m="970800">components</span> <span
  m="971570">in</span> <span m="971740">that</span> <span
  m="971930">combination</span> <span m="972510">are</span> <span
  m="972630">the</span> <span m="972820">eigenvector.</span></p><p><span
  m="974020">And</span> <span m="974780">that</span> <span m="975180">guy</span>
  <span m="975420">is</span> <span m="975570">the</span> <span
  m="975700">steady</span> <span m="976080">state.</span></p><p><span
  m="977250">Okay.</span></p><p><span m="978280">So</span> <span
  m="978460">I'm</span> <span m="978950">happy</span> <span
  m="979590">about</span> <span m="980070">the</span> <span m="980470">--</span>
  <span m="981110">the</span> <span m="981380">thinking</span> <span
  m="981870">here,</span> <span m="983320">but</span> <span m="984840">I</span>
  <span m="984980">haven't</span> <span m="985470">given</span> <span
  m="985970">--</span> <span m="986010">I</span> <span m="986160">haven't</span>
  <span m="986660">completed</span> <span m="987280">it</span> <span
  m="987340">because</span> <span m="987580">I</span> <span
  m="987690">haven't</span> <span m="988170">found</span> <span
  m="988560">x1.</span> <span m="989620">But</span> <span m="990670">it's</span>
  <span m="991050">there.</span></p><p><span m="992560">Can</span> <span
  m="992790">I</span> <span m="992970">--</span> <span m="993110">another</span>
  <span m="993660">thought</span> <span m="994260">came</span> <span
  m="994570">to</span> <span m="994700">me</span> <span m="994860">as</span>
  <span m="995030">I</span> <span m="995120">was</span> <span
  m="995360">doing</span> <span m="995650">this,</span> <span
  m="996330">another</span> <span m="996970">little</span> <span
  m="997260">comment</span> <span m="998020">that</span> <span
  m="998470">--</span> <span m="998780">you</span> <span m="999210">--</span>
  <span m="999280">about</span> <span m="999620">eigenvalues</span> <span
  m="1000400">and</span> <span m="1000600">eigenvectors,</span> <span
  m="1001500">because</span> <span m="1002180">of</span> <span
  m="1002490">A</span> <span m="1002780">and</span> <span m="1002940">A</span>
  <span m="1003100">transpose.</span></p><p><span m="1005330">What</span> <span
  m="1005600">can</span> <span m="1005770">you</span> <span
  m="1005910">tell</span> <span m="1006170">me</span> <span
  m="1006350">about</span> <span m="1006610">eigenvalues</span> <span
  m="1007550">of</span> <span m="1007730">A</span> <span m="1008260">--</span>
  <span m="1010800">of</span> <span m="1013340">A</span> <span
  m="1014070">and</span> <span m="1014770">eigenvalues</span> <span
  m="1015640">of</span> <span m="1015760">A</span> <span
  m="1015910">transpose?</span></p><p><span m="1021350">Whoops.</span> <span
  m="1024960">They're</span> <span m="1025130">the</span> <span
  m="1025260">same.</span></p><p><span m="1025660">They're</span> <span
  m="1028099">--</span> <span m="1028300">so</span> <span
  m="1028470">this</span> <span m="1028579">is</span> <span m="1028780">a</span>
  <span m="1028869">little</span> <span m="1029119">comment</span> <span
  m="1029569">--</span> <span m="1029589">we</span> <span m="1029859">--</span>
  <span m="1030300">it's</span> <span m="1030520">useful,</span> <span
  m="1031079">since</span> <span m="1031800">eigenvalues</span> <span
  m="1032880">are</span> <span m="1032970">generally</span> <span
  m="1033369">not</span> <span m="1033619">easy</span> <span
  m="1033890">to</span> <span m="1034000">find</span> <span
  m="1034530">--</span> <span m="1034550">it's</span> <span
  m="1034720">always</span> <span m="1035119">useful</span> <span
  m="1035500">to</span> <span m="1035619">know</span> <span
  m="1036170">some</span> <span m="1036470">cases</span> <span
  m="1036990">where</span> <span m="1038180">you've</span> <span
  m="1038730">got</span> <span m="1039000">them,</span> <span
  m="1039180">where</span> <span m="1039660">--</span> <span
  m="1040210">and</span> <span m="1040440">this</span> <span
  m="1040660">is</span> <span m="1040910">--</span> <span m="1041270">if</span>
  <span m="1041510">you</span> <span m="1041670">know</span> <span
  m="1041869">the</span> <span m="1042020">eigenvalues</span> <span
  m="1042740">of</span> <span m="1042880">A,</span> <span
  m="1043089">then</span> <span m="1043339">you</span> <span
  m="1043460">know</span> <span m="1043680">the</span> <span
  m="1043829">eigenvalues</span> <span m="1044380">of</span> <span
  m="1044510">A</span> <span m="1044670">transpose.</span></p><p><span
  m="1045260">eigenvalues</span> <span m="1045770">of</span> <span
  m="1045890">A</span> <span m="1046020">transpose</span> <span
  m="1046700">are</span> <span m="1047060">the</span> <span
  m="1047210">same.</span></p><p><span m="1052560">And</span> <span
  m="1053050">can</span> <span m="1053320">I</span> <span
  m="1053390">just,</span> <span m="1053960">like,</span> <span
  m="1054310">review</span> <span m="1054760">why</span> <span
  m="1055000">that</span> <span m="1055230">is?</span></p><p><span
  m="1057890">So</span> <span m="1058130">to</span> <span
  m="1058240">find</span> <span m="1058610">the</span> <span
  m="1058780">eigenvalues</span> <span m="1060500">of</span> <span
  m="1061190">A,</span> <span m="1062160">this</span> <span
  m="1062430">would</span> <span m="1062630">be</span> <span
  m="1062950">determinate</span> <span m="1063730">of</span> <span
  m="1063890">A</span> <span m="1064280">minus</span> <span
  m="1065020">lambda</span> <span m="1065650">I</span> <span
  m="1066380">equals</span> <span m="1067130">zero,</span> <span
  m="1067900">that</span> <span m="1068380">gives</span> <span
  m="1068600">me</span> <span m="1068760">an</span> <span
  m="1068860">eigenvalue</span> <span m="1069590">of</span> <span
  m="1069750">A</span> <span m="1071620">--</span> <span m="1073490">now</span>
  <span m="1073720">how</span> <span m="1073960">can</span> <span
  m="1074170">I</span> <span m="1074250">get</span> <span m="1074950">A</span>
  <span m="1075210">transpose</span> <span m="1075900">into</span> <span
  m="1076080">the</span> <span m="1076210">picture</span> <span
  m="1076630">here?</span></p><p><span m="1078520">I'll</span> <span
  m="1078730">use</span> <span m="1079130">the</span> <span
  m="1079260">fact</span> <span m="1079740">that</span> <span
  m="1079920">the</span> <span m="1080040">determinant</span> <span
  m="1080690">of</span> <span m="1080830">a</span> <span
  m="1080900">matrix</span> <span m="1081700">and</span> <span
  m="1082010">the</span> <span m="1082100">determinant</span> <span
  m="1082720">of</span> <span m="1082830">its</span> <span
  m="1083020">transpose</span> <span m="1083820">are</span> <span
  m="1084900">the</span> <span m="1085430">same.</span></p><p><span
  m="1086690">The</span> <span m="1086820">determinant</span> <span
  m="1087270">of</span> <span m="1087350">a</span> <span
  m="1087420">matrix</span> <span m="1087900">equals</span> <span
  m="1088270">the</span> <span m="1088370">determinant</span> <span
  m="1088810">of</span> <span m="1089240">a</span> <span m="1089410">--</span>
  <span m="1089550">of</span> <span m="1089720">the</span> <span
  m="1089840">transpose.</span></p><p><span m="1090520">That</span> <span
  m="1090700">was</span> <span m="1091000">property</span> <span
  m="1091730">ten,</span> <span m="1092400">the</span> <span
  m="1092640">very</span> <span m="1092950">last</span> <span
  m="1093510">guy</span> <span m="1093950">in</span> <span
  m="1094140">our</span> <span m="1094270">determinant</span> <span
  m="1094850">list.</span></p><p><span m="1095860">So</span> <span
  m="1096330">I'll</span> <span m="1096510">transpose</span> <span
  m="1097090">that</span> <span m="1097310">matrix.</span></p><p><span
  m="1098280">This</span> <span m="1098580">leads</span> <span
  m="1099070">to</span> <span m="1100320">--</span> <span m="1101680">I</span>
  <span m="1102070">just</span> <span m="1102360">take</span> <span
  m="1102580">the</span> <span m="1102680">matrix</span> <span
  m="1103150">and</span> <span m="1103290">transpose</span> <span
  m="1103950">it,</span> <span m="1104690">but</span> <span
  m="1105460">now</span> <span m="1105750">what</span> <span
  m="1105920">do</span> <span m="1106030">I</span> <span m="1106140">get</span>
  <span m="1106450">when</span> <span m="1106670">I</span> <span
  m="1106790">transpose</span> <span m="1107660">lambda</span> <span
  m="1108170">I?</span></p><p><span m="1109520">I</span> <span
  m="1109630">just</span> <span m="1109880">get</span> <span
  m="1110070">lambda</span> <span m="1110700">I.</span></p><p><span
  m="1113920">So</span> <span m="1114130">that's</span> <span
  m="1114720">--</span> <span m="1115010">that's</span> <span
  m="1115390">all</span> <span m="1115560">there</span> <span
  m="1115660">was</span> <span m="1115980">to</span> <span
  m="1116120">the</span> <span m="1116210">reasoning.</span></p><p><span
  m="1117800">The</span> <span m="1117950">reasoning</span> <span
  m="1118460">is</span> <span m="1118630">that</span> <span
  m="1118770">the</span> <span m="1118920">eigenvalues</span> <span
  m="1119600">of</span> <span m="1119740">A</span> <span
  m="1120000">solved</span> <span m="1120520">that</span> <span
  m="1120740">equation.</span></p><p><span m="1122370">The</span> <span
  m="1122510">determinant</span> <span m="1123110">of</span> <span
  m="1123210">a</span> <span m="1123290">matrix</span> <span
  m="1123800">is</span> <span m="1123950">the</span> <span
  m="1124070">determinant</span> <span m="1124530">of</span> <span
  m="1124640">its</span> <span m="1124810">transpose,</span> <span
  m="1125870">so</span> <span m="1126120">that</span> <span
  m="1126290">gives</span> <span m="1126460">me</span> <span
  m="1126610">this</span> <span m="1126820">equation</span> <span
  m="1127480">and</span> <span m="1127590">that</span> <span
  m="1127800">tells</span> <span m="1128100">me</span> <span
  m="1128250">that</span> <span m="1128450">the</span> <span
  m="1128590">same</span> <span m="1128990">lambdas</span> <span
  m="1130160">are</span> <span m="1130890">eigenvalues</span> <span
  m="1131710">of</span> <span m="1131840">A</span> <span
  m="1131980">transpose.</span></p><p><span m="1133240">So</span> <span
  m="1133450">that,</span> <span m="1134300">backing</span> <span
  m="1135080">up</span> <span m="1135240">to</span> <span m="1135350">the</span>
  <span m="1135460">Markov</span> <span m="1135990">case,</span> <span
  m="1136660">one</span> <span m="1137470">is</span> <span m="1137650">an</span>
  <span m="1137830">eigenvalue</span> <span m="1138710">of</span> <span
  m="1138880">A</span> <span m="1139070">transpose</span> <span
  m="1139930">and</span> <span m="1140060">we</span> <span
  m="1140200">actually</span> <span m="1140540">found</span> <span
  m="1140880">its</span> <span m="1141060">eigenvector,</span> <span
  m="1141800">one</span> <span m="1142030">one</span> <span
  m="1142230">one,</span> <span m="1143100">and</span> <span
  m="1143690">that</span> <span m="1143930">tell</span> <span
  m="1144340">us</span> <span m="1144620">that</span> <span
  m="1144780">one</span> <span m="1145290">is</span> <span
  m="1145480">also</span> <span m="1145980">an</span> <span
  m="1146100">eigenvalue</span> <span m="1146810">of</span> <span
  m="1146920">A</span> <span m="1147500">--</span> <span m="1147590">but,</span>
  <span m="1147770">of</span> <span m="1147820">course,</span> <span
  m="1148090">it</span> <span m="1148200">has</span> <span m="1148360">a</span>
  <span m="1148450">different</span> <span m="1148810">eigenvector,</span> <span
  m="1149910">the</span> <span m="1150330">--</span> <span
  m="1150360">the</span> <span m="1150520">left</span> <span
  m="1150850">null</span> <span m="1151020">space</span> <span
  m="1151350">isn't</span> <span m="1151600">the</span> <span
  m="1151710">same</span> <span m="1151990">as</span> <span
  m="1152090">the</span> <span m="1152220">null</span> <span
  m="1152430">space</span> <span m="1153010">and</span> <span
  m="1153400">we</span> <span m="1153530">would</span> <span
  m="1153690">have</span> <span m="1153900">to</span> <span
  m="1154030">find</span> <span m="1154400">it.</span></p><p><span
  m="1154750">So</span> <span m="1154950">there's</span> <span
  m="1155160">some</span> <span m="1155500">vector</span> <span
  m="1156590">here</span> <span m="1157870">which</span> <span
  m="1158240">is</span> <span m="1158380">x1</span> <span
  m="1159310">that</span> <span m="1159680">produces</span> <span
  m="1160440">zero</span></p><p><span m="1160960">zero</span> <span
  m="1161530">zero.</span> <span m="1162460">Actually,</span> <span
  m="1163120">it</span> <span m="1163230">wouldn't</span> <span
  m="1163490">be</span> <span m="1163620">that</span> <span
  m="1163820">hard</span> <span m="1164040">to</span> <span
  m="1164120">find,</span> <span m="1164490">you</span> <span
  m="1164570">know,</span> <span m="1164700">I</span> <span
  m="1164870">--</span> <span m="1164900">as</span> <span m="1165080">I'm</span>
  <span m="1165340">talking</span> <span m="1165860">I'm</span> <span
  m="1165970">thinking,</span> <span m="1166210">okay,</span> <span
  m="1166520">I</span> <span m="1166700">going</span> <span
  m="1166860">to</span> <span m="1166950">follow</span> <span
  m="1167330">through</span> <span m="1167970">and</span> <span
  m="1168240">actually</span> <span m="1168680">find</span> <span
  m="1169080">it?</span></p><p><span m="1169440">Well,</span> <span
  m="1170060">I</span> <span m="1170240">can</span> <span
  m="1170510">tell</span> <span m="1171490">from</span> <span
  m="1172010">this</span> <span m="1172270">one</span> <span
  m="1172480">--</span> <span m="1172500">look,</span> <span
  m="1172750">if</span> <span m="1172920">I</span> <span m="1173040">put</span>
  <span m="1173290">a</span> <span m="1173360">point</span> <span
  m="1173740">six</span> <span m="1174200">there</span> <span
  m="1175150">and</span> <span m="1175710">a</span> <span
  m="1175770">point</span> <span m="1176200">seven</span> <span
  m="1176610">there,</span> <span m="1177650">that's</span> <span
  m="1178340">what</span> <span m="1178610">--</span> <span
  m="1178630">then</span> <span m="1179020">I'll</span> <span
  m="1179200">be</span> <span m="1179420">okay</span> <span
  m="1179910">in</span> <span m="1180030">the</span> <span
  m="1180140">last</span> <span m="1180520">row,</span> <span
  m="1180930">right?</span></p><p><span m="1183510">Now</span> <span
  m="1183910">I</span> <span m="1184810">only</span> <span m="1185220">--</span>
  <span m="1185250">remains</span> <span m="1185730">to</span> <span
  m="1185860">find</span> <span m="1186180">one</span> <span
  m="1186440">guy.</span></p><p><span m="1187840">And</span> <span
  m="1188190">let</span> <span m="1188290">me</span> <span
  m="1188410">take</span> <span m="1188670">the</span> <span
  m="1188790">first</span> <span m="1189190">row,</span> <span
  m="1189430">then.</span></p><p><span m="1189860">Minus</span> <span
  m="1190460">point</span> <span m="1190830">54</span> <span
  m="1191710">plus</span> <span m="1192130">point</span> <span
  m="1192460">21</span> <span m="1192800">--</span> <span
  m="1193500">there's</span> <span m="1193880">some</span> <span
  m="1194140">big</span> <span m="1194530">number</span> <span
  m="1194920">going</span> <span m="1195190">in</span> <span
  m="1195340">there,</span> <span m="1195960">right?</span></p><p><span
  m="1196790">So</span> <span m="1197020">I</span> <span m="1197150">have</span>
  <span m="1197810">--</span> <span m="1197950">just</span> <span
  m="1198230">to</span> <span m="1198330">make</span> <span
  m="1198520">the</span> <span m="1198640">first</span> <span
  m="1198970">row</span> <span m="1199170">come</span> <span
  m="1199420">out</span> <span m="1199640">zero,</span> <span
  m="1200320">I'm</span> <span m="1200670">getting</span> <span
  m="1200990">minus</span> <span m="1201390">point</span> <span
  m="1201670">54</span> <span m="1202290">plus</span> <span
  m="1202720">point</span> <span m="1203160">21,</span> <span
  m="1203980">so</span> <span m="1204130">that</span> <span
  m="1204330">was</span> <span m="1204480">minus</span> <span
  m="1205130">point</span> <span m="1205450">33</span> <span
  m="1207290">and</span> <span m="1208080">what</span> <span
  m="1208560">--</span> <span m="1208660">what</span> <span
  m="1208950">do</span> <span m="1209060">I</span> <span
  m="1209160">want?</span></p><p><span m="1209420">Like</span> <span
  m="1209650">thirty</span> <span m="1209950">three</span> <span
  m="1210160">hundred?</span></p><p><span m="1211350">This</span> <span
  m="1211520">is</span> <span m="1211640">the</span> <span
  m="1211760">first</span> <span m="1212230">time</span> <span
  m="1212590">in</span> <span m="1212680">the</span> <span
  m="1212750">history</span> <span m="1213190">of</span> <span
  m="1213290">linear</span> <span m="1213610">algebra</span> <span
  m="1213980">that</span> <span m="1214140">an</span> <span
  m="1214310">eigenvector</span> <span m="1214630">has</span> <span
  m="1215140">every</span> <span m="1215420">had</span> <span
  m="1216060">a</span> <span m="1216320">component</span> <span
  m="1216980">thirty</span> <span m="1217450">three</span> <span
  m="1217970">hundred.</span></p><p><span m="1218980">But</span> <span
  m="1219730">I</span> <span m="1219870">guess</span> <span
  m="1220200">it's</span> <span m="1220430">true.</span></p><p><span
  m="1221030">Because</span> <span m="1221330">then</span> <span
  m="1221570">I</span> <span m="1221710">multiply</span> <span
  m="1222260">by</span> <span m="1222500">minus</span> <span
  m="1222970">one</span> <span m="1223210">over</span> <span
  m="1223390">a</span> <span m="1223430">hundred</span> <span
  m="1223940">--</span> <span m="1224170">oh</span> <span m="1224310">no,</span>
  <span m="1224760">it</span> <span m="1224820">was</span> <span
  m="1225040">point</span> <span m="1225570">33.</span> <span
  m="1226830">So</span> <span m="1227280">is</span> <span
  m="1227390">this</span> <span m="1227630">just</span> <span
  m="1227860">--</span> <span m="1227880">oh,</span> <span
  m="1228690">shoot.</span></p><p><span m="1229180">Only</span> <span
  m="1229540">33.</span> <span m="1230800">Okay.</span></p><p><span
  m="1231880">Only</span> <span m="1232210">33.</span> <span
  m="1233030">Okay,</span> <span m="1233530">so</span> <span
  m="1233720">there's</span> <span m="1234010">the</span> <span
  m="1234170">eigenvector.</span></p><p><span m="1235610">Oh,</span> <span
  m="1235850">and</span> <span m="1235960">notice</span> <span
  m="1236730">that</span> <span m="1236910">it</span> <span
  m="1237270">--</span> <span m="1237650">that</span> <span
  m="1237880">it</span> <span m="1238050">turned</span> <span
  m="1238410">--</span> <span m="1238430">did</span> <span
  m="1238630">turn</span> <span m="1238920">out,</span> <span
  m="1239150">at</span> <span m="1239250">least,</span> <span
  m="1240030">to</span> <span m="1240390">be</span> <span m="1240570">all</span>
  <span m="1240780">positive.</span></p><p><span m="1242940">So</span> <span
  m="1243060">that</span> <span m="1243280">was,</span> <span
  m="1243540">like,</span> <span m="1243860">the</span> <span
  m="1244000">theory</span> <span m="1244710">--</span> <span
  m="1244740">predicts</span> <span m="1245120">that</span> <span
  m="1245370">part,</span> <span m="1245700">too.</span></p><p><span
  m="1245990">I</span> <span m="1246080">won't</span> <span
  m="1246510">give</span> <span m="1246820">the</span> <span
  m="1246990">proof</span> <span m="1247390">of</span> <span
  m="1247480">that</span> <span m="1247760">part.</span></p><p><span
  m="1248500">So</span> <span m="1249100">30</span> <span m="1249130">--</span>
  <span m="1249480">33</span> <span m="1250000">--</span> <span
  m="1250600">point</span> <span m="1250970">six</span> <span
  m="1251280">33</span> <span m="1251850">point</span> <span
  m="1252160">seven.</span></p><p><span m="1252770">Okay.</span></p><p><span
  m="1253420">Now</span> <span m="1254670">those</span> <span
  m="1255390">are</span> <span m="1255440">the</span> <span
  m="1255570">ma-</span> <span m="1255800">that's</span> <span
  m="1256070">the</span> <span m="1256180">linear</span> <span
  m="1256500">algebra</span> <span m="1256910">part.</span></p><p><span
  m="1258750">Can</span> <span m="1258920">I</span> <span m="1259000">get</span>
  <span m="1259230">to</span> <span m="1259350">the</span> <span
  m="1259500">applications?</span></p><p><span m="1260980">Where</span> <span
  m="1261210">do</span> <span m="1261280">these</span> <span
  m="1261510">Markov</span> <span m="1261970">matrices</span> <span
  m="1262610">come</span> <span m="1262860">from?</span></p><p><span
  m="1263120">Because</span> <span m="1263360">that's</span> <span
  m="1263780">--</span> <span m="1263800">that's</span> <span
  m="1264030">part</span> <span m="1264280">of</span> <span
  m="1264350">this</span> <span m="1264580">course</span> <span
  m="1264930">and</span> <span m="1265070">absolutely</span> <span
  m="1265990">part</span> <span m="1266360">of</span> <span
  m="1266420">this</span> <span m="1266640">lecture.</span></p><p><span
  m="1267570">Okay.</span> <span m="1268080">So</span> <span
  m="1268340">where's</span> <span m="1268820">--</span> <span
  m="1268930">what's</span> <span m="1269370">an</span> <span
  m="1269510">application</span> <span m="1270260">of</span> <span
  m="1270330">Markov</span> <span m="1270770">matrices?</span></p><p><span
  m="1272390">Okay.</span> <span m="1277600">Markov</span> <span
  m="1278150">matrices</span> <span m="1278760">--</span> <span
  m="1278780">so,</span> <span m="1279090">my</span> <span
  m="1279930">equation,</span> <span m="1280640">then,</span> <span
  m="1281180">that</span> <span m="1281480">I'm</span> <span
  m="1281630">solving</span> <span m="1282250">and</span> <span
  m="1282380">studying</span> <span m="1283130">is</span> <span
  m="1283450">this</span> <span m="1283660">equation</span> <span
  m="1284350">u(k+1)=Auk.</span> <span m="1288290">And</span> <span
  m="1288970">now</span> <span m="1289530">A</span> <span m="1289810">is</span>
  <span m="1289990">a</span> <span m="1290060">Markov</span> <span
  m="1290620">matrix.</span></p><p><span m="1291280">A</span> <span
  m="1291400">is</span> <span m="1291660">Markov.</span> <span
  m="1296060">And</span> <span m="1296260">I</span> <span
  m="1296320">want</span> <span m="1296550">to</span> <span
  m="1296600">give</span> <span m="1296800">an</span> <span
  m="1296910">example.</span></p><p><span m="1299110">Can</span> <span
  m="1299350">I</span> <span m="1299440">just</span> <span
  m="1299910">create</span> <span m="1300410">an</span> <span
  m="1300570">example?</span></p><p><span m="1301190">It'll</span> <span
  m="1301340">be</span> <span m="1301500">two</span> <span m="1301690">by</span>
  <span m="1301880">two.</span></p><p><span m="1304120">And</span> <span
  m="1305040">it's</span> <span m="1305400">one</span> <span
  m="1305690">I've</span> <span m="1306050">used</span> <span
  m="1307180">before</span> <span m="1308110">because</span> <span
  m="1308450">it</span> <span m="1308590">seems</span> <span
  m="1308870">to</span> <span m="1308990">me</span> <span m="1309140">to</span>
  <span m="1309230">bring</span> <span m="1309580">out</span> <span
  m="1309800">the</span> <span m="1309950">idea.</span></p><p><span
  m="1310990">It's</span> <span m="1311440">--</span> <span
  m="1311880">because</span> <span m="1312190">we</span> <span
  m="1312290">have</span> <span m="1312460">two</span> <span
  m="1312620">by</span> <span m="1312810">two,</span> <span
  m="1313060">we</span> <span m="1313240">have</span> <span
  m="1313640">two</span> <span m="1314710">states,</span> <span
  m="1315740">let's</span> <span m="1316120">say</span> <span
  m="1317470">California</span> <span m="1318800">and</span> <span
  m="1318920">Massachusetts.</span></p><p><span m="1321510">And</span> <span
  m="1322760">I'm</span> <span m="1323250">looking</span> <span
  m="1323630">at</span> <span m="1323740">the</span> <span
  m="1323840">populations</span> <span m="1324730">in</span> <span
  m="1324840">those</span> <span m="1325120">two</span> <span
  m="1325310">states,</span> <span m="1325740">the</span> <span
  m="1325850">people</span> <span m="1326500">in</span> <span
  m="1326690">those</span> <span m="1326960">two</span> <span
  m="1327150">states,</span> <span m="1327880">California</span> <span
  m="1328720">and</span> <span m="1328810">Massachusetts.</span></p><p><span
  m="1330900">And</span> <span m="1331990">my</span> <span
  m="1332520">matrix</span> <span m="1333140">A</span> <span
  m="1333500">is</span> <span m="1333690">going</span> <span
  m="1333860">to</span> <span m="1333950">tell</span> <span
  m="1334240">me</span> <span m="1335030">in</span> <span m="1335640">a</span>
  <span m="1335660">--</span> <span m="1336090">in</span> <span
  m="1336640">a</span> <span m="1336690">year,</span> <span
  m="1337040">some</span> <span m="1337890">movement</span> <span
  m="1338260">has</span> <span m="1338460">happened.</span></p><p><span
  m="1339230">Some</span> <span m="1339480">people</span> <span
  m="1339840">stayed</span> <span m="1340260">in</span> <span
  m="1340380">Massachusetts,</span> <span m="1341180">some</span> <span
  m="1341350">people</span> <span m="1341660">moved</span> <span
  m="1341960">to</span> <span m="1342060">California,</span> <span
  m="1342990">some</span> <span m="1343420">smart</span> <span
  m="1343770">people</span> <span m="1344050">moved</span> <span
  m="1344270">from</span> <span m="1344470">California</span> <span
  m="1345030">to</span> <span m="1345120">Massachusetts,</span> <span
  m="1346300">some</span> <span m="1346780">people</span> <span
  m="1347080">stayed</span> <span m="1347380">in</span> <span
  m="1347540">California</span> <span m="1348200">and</span> <span
  m="1348340">made</span> <span m="1348550">a</span> <span
  m="1348590">billion.</span></p><p><span m="1349240">Okay.</span> <span
  m="1349740">So</span> <span m="1350700">that</span> <span
  m="1351240">--</span> <span m="1351260">there's</span> <span
  m="1351440">a</span> <span m="1351510">matrix</span> <span
  m="1352100">there</span> <span m="1352360">with</span> <span
  m="1352540">four</span> <span m="1352930">entries</span> <span
  m="1356150">and</span> <span m="1356630">those</span> <span
  m="1356970">tell</span> <span m="1357240">me</span> <span
  m="1357910">the</span> <span m="1358470">fractions</span> <span
  m="1359510">of</span> <span m="1359750">my</span> <span
  m="1359950">population</span> <span m="1360980">--</span> <span
  m="1361130">so</span> <span m="1361260">I'm</span> <span
  m="1361370">making</span> <span m="1361690">--</span> <span
  m="1361710">I'm</span> <span m="1361810">going</span> <span
  m="1361960">to</span> <span m="1362000">use</span> <span
  m="1362240">fractions,</span> <span m="1363510">so</span> <span
  m="1364020">they</span> <span m="1364280">won't</span> <span
  m="1364490">be</span> <span m="1364620">negative,</span> <span
  m="1365140">of</span> <span m="1365260">course,</span> <span
  m="1365690">because</span> <span m="1365990">--</span> <span
  m="1366280">because</span> <span m="1366490">only</span> <span
  m="1366780">positive</span> <span m="1367390">people</span> <span
  m="1368070">are</span> <span m="1368500">in-</span> <span
  m="1368690">involved</span> <span m="1369190">here</span> <span
  m="1369770">--</span> <span m="1370190">and</span> <span
  m="1370590">they'll</span> <span m="1370810">add</span> <span
  m="1370970">up</span> <span m="1371100">to</span> <span
  m="1371230">one,</span> <span m="1371550">because</span> <span
  m="1371920">I'm</span> <span m="1372090">accounting</span> <span
  m="1372710">for</span> <span m="1372910">all</span> <span
  m="1373140">people.</span></p><p><span m="1374620">So</span> <span
  m="1374790">that's</span> <span m="1375070">why</span> <span
  m="1375420">I</span> <span m="1375580">have</span> <span
  m="1375810">these</span> <span m="1376090">two</span> <span
  m="1376510">key</span> <span m="1376790">properties.</span></p><p><span
  m="1377830">The</span> <span m="1378030">entries</span> <span
  m="1378570">are</span> <span m="1378700">greater</span> <span
  m="1379060">equal</span> <span m="1379330">zero</span> <span
  m="1379650">because</span> <span m="1380470">I'm</span> <span
  m="1380810">looking</span> <span m="1381190">at</span> <span
  m="1381350">probabilities.</span></p><p><span m="1382890">Do</span> <span
  m="1383060">they</span> <span m="1383200">move,</span> <span
  m="1383670">do</span> <span m="1383780">they</span> <span
  m="1383970">stay?</span></p><p><span m="1386050">Those</span> <span
  m="1386290">probabilities</span> <span m="1387030">are</span> <span
  m="1387160">all</span> <span m="1387470">between</span> <span
  m="1387840">zero</span> <span m="1388170">and</span> <span
  m="1388270">one.</span></p><p><span m="1389130">And</span> <span
  m="1389520">the</span> <span m="1389610">probabilities</span> <span
  m="1390340">add</span> <span m="1390680">to</span> <span
  m="1390810">one</span> <span m="1391160">because</span> <span
  m="1391660">everybody's</span> <span m="1392290">accounted</span> <span
  m="1392750">for.</span></p><p><span m="1392990">I'm</span> <span
  m="1393080">not</span> <span m="1393660">losing</span> <span
  m="1394380">anybody,</span> <span m="1395020">gaining</span> <span
  m="1395470">anybody</span> <span m="1396000">in</span> <span
  m="1396900">this</span> <span m="1397100">Markov</span> <span
  m="1397550">chain.</span></p><p><span m="1397970">It's</span> <span
  m="1398430">--</span> <span m="1399030">it</span> <span
  m="1399600">conserves</span> <span m="1401080">the</span> <span
  m="1401220">total</span> <span m="1401550">population.</span></p><p><span
  m="1402620">Okay.</span> <span m="1402990">So</span> <span
  m="1403270">what</span> <span m="1403480">would</span> <span
  m="1403630">be</span> <span m="1403860">a</span> <span
  m="1403950">typical</span> <span m="1404380">matrix,</span> <span
  m="1404870">then?</span></p><p><span m="1405450">So</span> <span
  m="1405640">this</span> <span m="1405890">would</span> <span
  m="1406120">be</span> <span m="1406680">u,</span> <span
  m="1408230">California</span> <span m="1410330">and</span> <span
  m="1410830">u</span> <span m="1411320">Massachusetts</span> <span
  m="1412920">at</span> <span m="1413610">time</span> <span m="1414350">t</span>
  <span m="1414820">equal</span> <span m="1415380">k+1.</span> <span
  m="1416740">And</span> <span m="1417510">it's</span> <span
  m="1417720">some</span> <span m="1417920">matrix,</span> <span
  m="1419380">which</span> <span m="1419950">we'll</span> <span
  m="1420680">think</span> <span m="1421120">of,</span> <span
  m="1421700">times</span> <span m="1422820">u</span> <span
  m="1423490">California</span> <span m="1424760">and</span> <span
  m="1425300">u</span> <span m="1425680">Massachusetts</span> <span
  m="1427220">at</span> <span m="1427900">time</span> <span
  m="1428390">k.</span></p><p><span m="1431280">And</span> <span
  m="1431460">notice</span> <span m="1431940">this</span> <span
  m="1432140">matrix</span> <span m="1432850">is</span> <span
  m="1433080">going</span> <span m="1433240">to</span> <span
  m="1433310">stay</span> <span m="1433740">the</span> <span
  m="1433870">same,</span> <span m="1434460">you</span> <span
  m="1434560">know,</span> <span m="1434840">forever.</span></p><p><span
  m="1437480">So</span> <span m="1437680">that's</span> <span
  m="1438060">a</span> <span m="1439280">severe</span> <span
  m="1440020">limitation</span> <span m="1440900">on</span> <span
  m="1441050">the</span> <span m="1441210">example.</span></p><p><span
  m="1441940">The</span> <span m="1442050">example</span> <span
  m="1442670">has</span> <span m="1442960">a</span> <span m="1443010">--</span>
  <span m="1443040">the</span> <span m="1443330">same</span> <span
  m="1443850">Markov</span> <span m="1444330">matrix,</span> <span
  m="1445090">the</span> <span m="1445290">same</span> <span
  m="1445630">probabilities</span> <span m="1446360">act</span> <span
  m="1446820">at</span> <span m="1446920">every</span> <span
  m="1447220">time.</span></p><p><span m="1448660">Okay.</span> <span
  m="1449010">So</span> <span m="1449170">what's</span> <span
  m="1449440">a</span> <span m="1449510">reasonable,</span> <span
  m="1450090">say</span> <span m="1450450">--</span> <span
  m="1451030">say</span> <span m="1451710">point</span> <span
  m="1452480">nine</span> <span m="1453120">of</span> <span
  m="1453240">the</span> <span m="1453370">people</span> <span
  m="1454470">in</span> <span m="1454940">California</span> <span
  m="1455700">at</span> <span m="1456090">time</span> <span m="1456440">k</span>
  <span m="1456750">stay</span> <span m="1457130">there.</span></p><p><span
  m="1459410">And</span> <span m="1460660">point</span> <span
  m="1461370">one</span> <span m="1462490">of</span> <span
  m="1462800">the</span> <span m="1462910">people</span> <span
  m="1463420">in</span> <span m="1463690">California</span> <span
  m="1464440">move</span> <span m="1464670">to</span> <span
  m="1464790">Massachusetts.</span></p><p><span m="1466930">Notice</span> <span
  m="1467290">why</span> <span m="1467530">that</span> <span
  m="1467740">column</span> <span m="1468110">added</span> <span
  m="1468390">to</span> <span m="1468520">one,</span> <span
  m="1468900">because</span> <span m="1469420">we've</span> <span
  m="1469620">now</span> <span m="1469860">accounted</span> <span
  m="1470360">for</span> <span m="1470580">all</span> <span
  m="1470760">the</span> <span m="1470840">people</span> <span
  m="1471200">in</span> <span m="1471320">California</span> <span
  m="1472170">at</span> <span m="1472490">time</span> <span
  m="1472830">k.</span></p><p><span m="1473890">Nine</span> <span
  m="1474280">tenths</span> <span m="1474640">of</span> <span
  m="1474750">them</span> <span m="1474930">are</span> <span
  m="1475040">still</span> <span m="1475510">in</span> <span
  m="1475620">California,</span> <span m="1476250">one</span> <span
  m="1476520">tenth</span> <span m="1476930">are</span> <span
  m="1478540">here</span> <span m="1479390">at</span> <span
  m="1479910">time</span> <span m="1480190">k+1.</span> <span
  m="1481220">Okay.</span></p><p><span m="1482130">What</span> <span
  m="1482320">about</span> <span m="1482820">the</span> <span
  m="1483010">people</span> <span m="1483940">who</span> <span
  m="1484090">are</span> <span m="1484220">in</span> <span
  m="1484310">Massachusetts?</span></p><p><span m="1485120">This</span> <span
  m="1485470">is</span> <span m="1485630">going</span> <span
  m="1485800">to</span> <span m="1485850">multiply</span> <span
  m="1486310">column</span> <span m="1486650">two,</span> <span
  m="1486880">right,</span> <span m="1487530">by</span> <span
  m="1487840">our</span> <span m="1488410">fundamental</span> <span
  m="1488980">rule</span> <span m="1489440">of</span> <span
  m="1489750">multiplying</span> <span m="1490550">matrix</span> <span
  m="1491000">by</span> <span m="1491170">vector,</span> <span
  m="1492370">it's</span> <span m="1493220">the</span> <span
  m="1493440">--</span> <span m="1493730">it's</span> <span
  m="1493960">the</span> <span m="1494530">population</span> <span
  m="1495290">in</span> <span m="1495430">Massachusetts.</span></p><p><span
  m="1497050">Shall</span> <span m="1497330">we</span> <span
  m="1497500">say</span> <span m="1498130">that</span> <span
  m="1498360">--</span> <span m="1498650">that</span> <span
  m="1499430">after</span> <span m="1500200">the</span> <span
  m="1501180">Red</span> <span m="1501900">Sox,</span> <span
  m="1503630">fail</span> <span m="1504880">again,</span> <span
  m="1506350">eight</span> <span m="1507490">--</span> <span
  m="1507530">only</span> <span m="1508150">80</span> <span
  m="1508680">percent</span> <span m="1509120">of</span> <span
  m="1509180">the</span> <span m="1509280">people</span> <span
  m="1509600">in</span> <span m="1509700">Massachusetts</span> <span
  m="1510540">stay</span> <span m="1511630">and</span> <span
  m="1512280">20</span> <span m="1512620">percent</span> <span
  m="1513660">move</span> <span m="1514190">to</span> <span
  m="1514330">California.</span></p><p><span m="1515120">Okay.</span> <span
  m="1515870">So</span> <span m="1516400">again,</span> <span
  m="1517100">this</span> <span m="1517820">adds</span> <span
  m="1518220">to</span> <span m="1518350">one,</span> <span
  m="1518730">which</span> <span m="1518960">accounts</span> <span
  m="1519520">for</span> <span m="1520360">all</span> <span
  m="1520730">people</span> <span m="1521100">in</span> <span
  m="1521190">Massachusetts</span> <span m="1522030">where</span> <span
  m="1522480">they</span> <span m="1522700">are.</span></p><p><span
  m="1523070">So</span> <span m="1523270">there</span> <span
  m="1523510">is</span> <span m="1523610">a</span> <span
  m="1523670">Markov</span> <span m="1524150">matrix.</span> <span
  m="1526770">Non-negative</span> <span m="1527140">entries</span> <span
  m="1527550">adding</span> <span m="1527920">to</span> <span
  m="1528050">one.</span></p><p><span m="1528400">What's</span> <span
  m="1528710">the</span> <span m="1528820">steady</span> <span
  m="1529180">state?</span></p><p><span m="1529980">If</span> <span
  m="1530250">everybody</span> <span m="1530850">started</span> <span
  m="1531310">in</span> <span m="1531440">Massachusetts,</span> <span
  m="1532590">say,</span> <span m="1533040">at</span> <span
  m="1533350">--</span> <span m="1533500">you</span> <span
  m="1533570">know,</span> <span m="1533680">when</span> <span
  m="1533820">the</span> <span m="1533920">Pilgrims</span> <span
  m="1534410">showed</span> <span m="1534690">up</span> <span
  m="1534870">or</span></p><p><span m="1534980">something.</span> <span
  m="1535600">Then</span> <span m="1536600">where</span> <span
  m="1537980">are</span> <span m="1538180">they</span> <span
  m="1538730">now?</span></p><p><span m="1540280">Where</span> <span
  m="1540660">are</span> <span m="1540780">they</span> <span
  m="1541260">at</span> <span m="1541540">time</span> <span
  m="1542600">100,</span> <span m="1543450">let's</span> <span
  m="1543660">say,</span> <span m="1544300">or</span> <span
  m="1544600">maybe</span> <span m="1545180">--</span> <span
  m="1545360">I</span> <span m="1545420">don't</span> <span
  m="1545440">know,</span> <span m="1545640">how</span> <span
  m="1545710">many</span> <span m="1545920">years</span> <span
  m="1546210">since</span> <span m="1546440">the</span> <span
  m="1546530">Pilgrims?</span> <span m="1547210">300</span> <span
  m="1547440">and</span> <span m="1547560">something.</span></p><p><span
  m="1549090">Or</span> <span m="1549480">--</span> <span m="1549500">and</span>
  <span m="1549950">actually</span> <span m="1550310">where</span> <span
  m="1550600">will</span> <span m="1550730">they</span> <span
  m="1550910">be,</span> <span m="1551220">like,</span> <span
  m="1551520">way</span> <span m="1551970">out</span> <span m="1553010">a</span>
  <span m="1553670">million</span> <span m="1554060">years</span> <span
  m="1554340">from</span> <span m="1554500">now?</span></p><p><span
  m="1554820">I</span> <span m="1555670">--</span> <span m="1556530">I</span>
  <span m="1556720">could</span> <span m="1558470">multiply</span> <span
  m="1560300">--</span> <span m="1560980">take</span> <span
  m="1561230">the</span> <span m="1561330">powers</span> <span
  m="1561750">of</span> <span m="1561840">this</span> <span
  m="1562050">matrix.</span></p><p><span m="1563360">In</span> <span
  m="1563500">fact,</span> <span m="1563960">you'll</span> <span
  m="1564370">--</span> <span m="1564410">you</span> <span
  m="1564670">would</span> <span m="1564950">--</span> <span
  m="1565000">ought</span> <span m="1565170">to</span> <span
  m="1565230">be</span> <span m="1565450">able</span> <span
  m="1565630">to</span> <span m="1566010">figure</span> <span
  m="1566680">out</span> <span m="1567040">what</span> <span
  m="1567350">is</span> <span m="1567740">the</span> <span
  m="1567840">hundredth</span> <span m="1568300">power</span> <span
  m="1568630">of</span> <span m="1568700">that</span> <span
  m="1568930">matrix?</span></p><p><span m="1570490">Why</span> <span
  m="1570760">don't</span> <span m="1570880">we</span> <span
  m="1570990">do</span> <span m="1571190">that?</span></p><p><span
  m="1572520">But</span> <span m="1572720">let</span> <span
  m="1572930">me</span> <span m="1573480">follow</span> <span
  m="1574220">the</span> <span m="1574400">steady</span> <span
  m="1574750">state.</span></p><p><span m="1575050">So</span> <span
  m="1575280">what</span> <span m="1575890">--</span> <span
  m="1576010">what's</span> <span m="1576280">my</span> <span
  m="1576460">starting</span> <span m="1577090">--</span> <span
  m="1577760">my</span> <span m="1578000">starting</span> <span
  m="1578620">u</span> <span m="1578940">Cal,</span> <span m="1580320">u</span>
  <span m="1581360">Mass</span> <span m="1582610">at</span> <span
  m="1583380">time</span> <span m="1583750">zero</span> <span
  m="1585060">is,</span> <span m="1585610">shall</span> <span
  m="1585920">we</span> <span m="1586100">say</span> <span m="1587000">--</span>
  <span m="1588560">shall</span> <span m="1588690">we</span> <span
  m="1588820">put</span> <span m="1589050">anybody</span> <span
  m="1589550">in</span> <span m="1589750">California?</span></p><p><span
  m="1590400">Let's</span> <span m="1590640">make</span> <span
  m="1590940">--</span> <span m="1591360">let's</span> <span
  m="1591550">make</span> <span m="1591810">zero</span> <span
  m="1592300">there,</span> <span m="1592920">and</span> <span
  m="1593600">say</span> <span m="1593960">the</span> <span
  m="1594090">population</span> <span m="1594780">of</span> <span
  m="1594840">Massachusetts</span> <span m="1595830">is</span> <span
  m="1596380">--</span> <span m="1596400">let's</span> <span
  m="1596570">say</span> <span m="1596760">a</span> <span
  m="1596810">thousand</span> <span m="1597370">just</span> <span
  m="1597630">to</span> <span m="1598080">--</span> <span
  m="1598530">okay.</span> <span m="1603330">So</span> <span
  m="1603990">the</span> <span m="1604540">population</span> <span
  m="1605130">is</span> <span m="1605480">--</span> <span m="1606030">so</span>
  <span m="1606530">the</span> <span m="1606630">populations</span> <span
  m="1607330">are</span> <span m="1607430">zero</span> <span
  m="1607900">and</span> <span m="1607990">a</span> <span
  m="1608040">thousand</span> <span m="1608580">at</span> <span
  m="1608710">the</span> <span m="1608810">start.</span></p><p><span
  m="1609400">What</span> <span m="1609660">can</span> <span
  m="1609820">you</span> <span m="1609960">tell</span> <span
  m="1610230">me</span> <span m="1610430">about</span> <span
  m="1610820">this</span> <span m="1611180">population</span> <span
  m="1611910">after</span> <span m="1612500">--</span> <span
  m="1612790">after</span> <span m="1613320">k</span> <span
  m="1613620">steps?</span></p><p><span m="1615990">What</span> <span
  m="1616280">will</span> <span m="1616690">u</span> <span
  m="1617200">Cal</span> <span m="1617720">plus</span> <span
  m="1618160">u</span> <span m="1618340">Mass</span> <span
  m="1619110">add</span> <span m="1619480">to?</span></p><p><span
  m="1621420">A</span> <span m="1621540">thousand.</span></p><p><span
  m="1622790">Those</span> <span m="1623130">thousand</span> <span
  m="1623680">people</span> <span m="1624200">are</span> <span
  m="1624490">always</span> <span m="1625020">accounted</span> <span
  m="1625530">for.</span></p><p><span m="1626260">But</span> <span
  m="1626740">--</span> <span m="1627340">so</span> <span m="1627690">u</span>
  <span m="1627880">Mass</span> <span m="1628320">will</span> <span
  m="1628510">start</span> <span m="1628870">dropping</span> <span
  m="1629430">from</span> <span m="1629640">a</span> <span
  m="1629720">thousand</span> <span m="1630350">and</span> <span
  m="1630370">u</span> <span m="1630590">Cal</span> <span
  m="1631040">will</span> <span m="1631180">start</span> <span
  m="1631520">growing.</span></p><p><span m="1631930">Actually,</span> <span
  m="1632340">we</span> <span m="1632480">could</span> <span
  m="1632650">see</span> <span m="1633160">--</span> <span
  m="1633620">why</span> <span m="1633840">don't</span> <span
  m="1633960">we</span> <span m="1634100">figure</span> <span
  m="1634420">out</span> <span m="1634570">what</span> <span
  m="1634740">it</span> <span m="1634860">is</span> <span
  m="1635060">after</span> <span m="1635360">one?</span></p><p><span
  m="1636420">After</span> <span m="1636730">one</span> <span
  m="1637040">time</span> <span m="1637360">step,</span> <span
  m="1638280">what</span> <span m="1639030">are</span> <span
  m="1639090">the</span> <span m="1639220">populations</span> <span
  m="1640550">at</span> <span m="1641220">time</span> <span
  m="1641600">one?</span></p><p><span m="1644890">So</span> <span
  m="1645070">what</span> <span m="1645260">happens</span> <span
  m="1645670">in</span> <span m="1645810">one</span> <span
  m="1646080">step?</span></p><p><span m="1646530">You</span> <span
  m="1646670">multiply</span> <span m="1647180">once</span> <span
  m="1647520">by</span> <span m="1647690">that</span> <span
  m="1647950">matrix</span> <span m="1648840">and,</span> <span
  m="1649440">let's</span> <span m="1649640">see,</span> <span
  m="1650230">zero</span> <span m="1650820">times</span> <span
  m="1651200">this</span> <span m="1651440">column</span> <span
  m="1651810">--</span> <span m="1651830">so</span> <span
  m="1651980">it's</span> <span m="1652140">just</span> <span
  m="1652330">a</span> <span m="1652400">thousand</span> <span
  m="1652940">times</span> <span m="1653230">this</span> <span
  m="1653460">column,</span> <span m="1653840">so</span> <span
  m="1653990">I</span> <span m="1654090">think</span> <span
  m="1654350">we're</span> <span m="1654480">getting</span> <span
  m="1654810">200</span> <span m="1655950">and</span> <span
  m="1656340">800.</span> <span m="1659940">So</span> <span
  m="1660160">after</span> <span m="1660490">the</span> <span
  m="1660610">first</span> <span m="1660910">step,</span> <span
  m="1661310">200</span> <span m="1661820">people</span> <span
  m="1662210">have</span> <span m="1662680">--</span> <span
  m="1662860">are</span> <span m="1663310">in</span> <span
  m="1663410">California.</span></p><p><span m="1664760">Now</span> <span
  m="1665160">at</span> <span m="1665270">the</span> <span
  m="1665380">following</span> <span m="1666120">step,</span> <span
  m="1666770">I'll</span> <span m="1667060">multiply</span> <span
  m="1667570">again</span> <span m="1668010">by</span> <span
  m="1668180">this</span> <span m="1668430">matrix</span> <span
  m="1669620">--</span> <span m="1669650">more</span> <span
  m="1669990">people</span> <span m="1670310">will</span> <span
  m="1670480">move</span> <span m="1670750">to</span> <span
  m="1671720">California.</span></p><p><span m="1672740">Some</span> <span
  m="1673110">people</span> <span m="1673440">will</span> <span
  m="1673600">move</span> <span m="1673900">back.</span></p><p><span
  m="1674340">Twenty</span> <span m="1674700">people</span> <span
  m="1675190">will</span> <span m="1675380">come</span> <span
  m="1675590">back</span> <span m="1676610">and,</span> <span
  m="1679810">the</span> <span m="1680100">--</span> <span
  m="1680390">the</span> <span m="1680500">net</span> <span
  m="1680690">result</span> <span m="1681070">will</span> <span
  m="1681210">be</span> <span m="1681390">that</span> <span
  m="1681540">the</span> <span m="1681650">California</span> <span
  m="1682190">population</span> <span m="1682720">will</span> <span
  m="1682820">be</span> <span m="1683010">above</span> <span
  m="1683370">200</span> <span m="1684380">and</span> <span
  m="1684810">the</span> <span m="1684890">Massachusetts</span> <span
  m="1685650">below</span> <span m="1686030">800</span> <span
  m="1687070">and</span> <span m="1687660">they'll</span> <span
  m="1687810">still</span> <span m="1688140">add</span> <span
  m="1688310">up</span> <span m="1688440">to</span> <span m="1688570">a</span>
  <span m="1688620">thousand.</span></p><p><span
  m="1690300">Okay.</span></p><p><span m="1690690">I</span> <span
  m="1690760">do</span> <span m="1690940">that</span> <span m="1691160">a</span>
  <span m="1691210">few</span> <span m="1691420">times.</span></p><p><span
  m="1694100">I</span> <span m="1694180">do</span> <span m="1694350">that</span>
  <span m="1694550">100</span> <span m="1694960">times.</span></p><p><span
  m="1695500">What's</span> <span m="1695980">the</span> <span
  m="1696080">population?</span></p><p><span m="1698220">Well,</span> <span
  m="1698640">okay,</span> <span m="1698970">to</span> <span
  m="1699120">answer</span> <span m="1699480">any</span> <span
  m="1699820">question</span> <span m="1700210">like</span> <span
  m="1700430">that,</span> <span m="1700770">I</span> <span
  m="1700910">need</span> <span m="1701130">the</span> <span
  m="1701250">eigenvalues</span> <span m="1701920">and</span> <span
  m="1702100">eigenvectors,</span></p><p><span m="1702820">right?</span> <span
  m="1703200">As</span> <span m="1703320">soon</span> <span
  m="1703520">as</span> <span m="1703650">I've</span> <span
  m="1703910">--</span> <span m="1704090">I've</span> <span
  m="1704230">created</span> <span m="1704610">an</span> <span
  m="1704730">example,</span> <span m="1705640">but</span> <span
  m="1706060">as</span> <span m="1706150">soon</span> <span
  m="1706340">as</span> <span m="1706440">I</span> <span m="1706520">want</span>
  <span m="1706710">to</span> <span m="1706780">solve</span> <span
  m="1707210">anything,</span> <span m="1708080">I</span> <span
  m="1708380">have</span> <span m="1708570">to</span> <span
  m="1708690">find</span> <span m="1709010">eigenvalues</span> <span
  m="1709650">and</span> <span m="1709780">eigenvectors</span> <span
  m="1710520">of</span> <span m="1710650">that</span> <span
  m="1710910">matrix.</span></p><p><span m="1711610">Okay.</span></p><p><span
  m="1712230">So</span> <span m="1712440">let's</span> <span
  m="1712680">do</span> <span m="1712840">it.</span></p><p><span
  m="1713890">So</span> <span m="1714130">there's</span> <span
  m="1714410">the</span> <span m="1714520">matrix</span> <span
  m="1715210">.9,</span> <span m="1718540">.2,</span> <span
  m="1718980">.1,</span> <span m="1719260">.8</span> <span
  m="1719600">and</span> <span m="1719820">tell</span> <span
  m="1720010">me</span> <span m="1720150">its</span> <span
  m="1720330">eigenvalues.</span></p><p><span m="1723150">Lambda</span> <span
  m="1723680">equals</span> <span m="1724270">--</span> <span
  m="1724290">so</span> <span m="1724530">tell</span> <span
  m="1724720">me</span> <span m="1724850">one</span> <span
  m="1725100">eigenvalue?</span> <span m="1726390">One,</span> <span
  m="1727170">thanks.</span></p><p><span m="1728680">And</span> <span
  m="1729080">tell</span> <span m="1729270">me</span> <span
  m="1729410">the</span> <span m="1729570">other</span> <span
  m="1729720">one.</span></p><p><span m="1733120">What's</span> <span
  m="1733330">the</span> <span m="1733470">other</span> <span
  m="1733730">eigenvalue</span> <span m="1734060">--</span> <span
  m="1735300">from</span> <span m="1736340">the</span> <span
  m="1736550">trace</span> <span m="1737170">or</span> <span
  m="1737330">the</span> <span m="1737480">determinant</span> <span
  m="1738520">--</span> <span m="1738940">from</span> <span
  m="1739110">the</span> <span m="1739240">--</span> <span m="1739370">I</span>
  <span m="1739610">--</span> <span m="1739690">the</span> <span
  m="1739830">trace</span> <span m="1740240">is</span> <span
  m="1740400">what</span> <span m="1740740">--</span> <span
  m="1741180">is,</span> <span m="1741580">like,</span> <span
  m="1741780">easier.</span></p><p><span m="1742510">So</span> <span
  m="1742680">the</span> <span m="1742810">trace</span> <span
  m="1743210">of</span> <span m="1743290">that</span> <span
  m="1743500">matrix</span> <span m="1744030">is</span> <span
  m="1744170">one</span> <span m="1744390">point</span> <span
  m="1744700">seven.</span></p><p><span m="1746110">So</span> <span
  m="1746330">the</span> <span m="1746480">other</span> <span
  m="1746740">eigenvalue</span> <span m="1747460">is</span> <span
  m="1748320">point</span> <span m="1748860">seven.</span></p><p><span
  m="1750040">And</span> <span m="1750260">it</span> <span m="1750430">--</span>
  <span m="1750450">notice</span> <span m="1750810">that</span> <span
  m="1750950">it's</span> <span m="1751150">less</span> <span
  m="1751430">than</span> <span m="1751560">one.</span></p><p><span
  m="1753540">And</span> <span m="1753830">notice</span> <span
  m="1754200">that</span> <span m="1754560">that</span> <span
  m="1754670">determinant</span> <span m="1755200">is</span> <span
  m="1755370">point</span> <span m="1756990">72-.02,</span> <span
  m="1757780">which</span> <span m="1758120">is</span> <span
  m="1758280">point</span> <span m="1758570">seven.</span></p><p><span
  m="1758960">Right.</span> <span m="1759490">Okay.</span></p><p><span
  m="1760190">Now</span> <span m="1760420">to</span> <span
  m="1760520">find</span> <span m="1760790">the</span> <span
  m="1760930">eigenvectors.</span> <span m="1761900">This</span> <span
  m="1762210">is</span> <span m="1762340">--</span> <span m="1762360">so</span>
  <span m="1762600">that's</span> <span m="1762860">lambda</span> <span
  m="1763250">one</span> <span m="1764000">and</span> <span
  m="1764610">the</span> <span m="1764760">eigenvector</span> <span
  m="1765100">--</span> <span m="1766120">I'll</span> <span
  m="1766490">subtract</span> <span m="1767180">one</span> <span
  m="1767920">from</span> <span m="1768450">the</span> <span
  m="1768570">diagonal,</span> <span m="1769230">right?</span></p><p><span
  m="1769950">So</span> <span m="1770260">can</span> <span m="1770410">I</span>
  <span m="1770500">do</span> <span m="1770670">that</span> <span
  m="1770910">in</span> <span m="1771010">light</span> <span
  m="1771340">let</span> <span m="1771660">--</span> <span m="1771680">in</span>
  <span m="1771820">light</span> <span m="1772140">here?</span></p><p><span
  m="1773440">Subtract</span> <span m="1774020">one</span> <span
  m="1774410">from</span> <span m="1774580">the</span> <span
  m="1774690">diagonal,</span> <span m="1775240">I</span> <span
  m="1775300">have</span> <span m="1775450">minus</span> <span
  m="1775980">point</span> <span m="1776280">one</span> <span
  m="1776830">and</span> <span m="1776990">minus</span> <span
  m="1777430">point</span> <span m="1777810">two,</span> <span
  m="1778410">and</span> <span m="1778640">of</span> <span
  m="1778720">course</span> <span m="1778970">these</span> <span
  m="1779290">are</span> <span m="1779400">still</span></p><p><span
  m="1779730">there.</span> <span m="1780940">And</span> <span
  m="1781790">I'm</span> <span m="1781890">looking</span> <span
  m="1782350">for</span> <span m="1782710">its</span> <span
  m="1783140">--</span> <span m="1784220">here's</span> <span
  m="1784710">--</span> <span m="1784740">here's</span> <span
  m="1785250">--</span> <span m="1785290">this</span> <span
  m="1785540">is</span> <span m="1785700">going</span> <span
  m="1785860">to</span> <span m="1785910">be</span> <span m="1786070">x1.</span>
  <span m="1787360">It's</span> <span m="1788040">the</span> <span
  m="1788740">null</span> <span m="1789150">space</span> <span
  m="1789850">of</span> <span m="1790120">A</span> <span
  m="1790430">minus</span> <span m="1790930">I.</span></p><p><span
  m="1792170">Okay,</span> <span m="1792670">everybody</span> <span
  m="1793150">sees</span> <span m="1793580">that</span> <span
  m="1793760">it's</span> <span m="1794070">two</span> <span
  m="1794840">and</span> <span m="1795250">one.</span></p><p><span
  m="1796820">Okay?</span></p><p><span m="1797940">And</span> <span
  m="1798260">now</span> <span m="1798490">how</span> <span
  m="1798710">about</span> <span m="1798950">--</span> <span
  m="1798980">so</span> <span m="1799190">that</span> <span
  m="1799350">--</span> <span m="1799450">and</span> <span m="1799660">it</span>
  <span m="1799800">--</span> <span m="1799820">notice</span> <span
  m="1800210">that</span> <span m="1800590">that</span> <span
  m="1800790">eigenvector</span> <span m="1801670">is</span> <span
  m="1802010">positive.</span></p><p><span m="1803160">And</span> <span
  m="1803400">actually,</span> <span m="1804250">we</span> <span
  m="1804410">can</span> <span m="1804600">jump</span> <span
  m="1805080">to</span> <span m="1805340">infinity</span> <span
  m="1805990">right</span> <span m="1806270">now.</span></p><p><span
  m="1808770">What's</span> <span m="1809080">the</span> <span
  m="1809200">population</span> <span m="1810710">at</span> <span
  m="1811370">infinity?</span></p><p><span m="1814100">It's</span> <span
  m="1814330">a</span> <span m="1814420">multiple</span> <span
  m="1815200">--</span> <span m="1815220">this</span> <span
  m="1815490">is</span> <span m="1815790">--</span> <span
  m="1815820">this</span> <span m="1816070">eigenvector</span> <span
  m="1816780">is</span> <span m="1816900">giving</span> <span
  m="1817170">the</span> <span m="1817290">steady</span> <span
  m="1817630">state.</span> <span m="1819910">It's</span> <span
  m="1820160">some</span> <span m="1820380">multiple</span> <span
  m="1820870">of</span> <span m="1820990">this,</span> <span
  m="1821380">and</span> <span m="1821540">how</span> <span
  m="1821760">is</span> <span m="1821870">that</span> <span
  m="1822020">multiple</span> <span m="1822420">decided?</span></p><p><span
  m="1823280">By</span> <span m="1823940">adding</span> <span
  m="1824470">up</span> <span m="1824590">to</span> <span m="1824710">a</span>
  <span m="1824770">thousand</span> <span m="1825230">people.</span></p><p><span
  m="1826940">So</span> <span m="1827170">the</span> <span
  m="1827300">steady</span> <span m="1827700">state,</span> <span
  m="1828230">the</span> <span m="1828350">c1x1</span> <span
  m="1829550">--</span> <span m="1829870">this</span> <span
  m="1830040">is</span> <span m="1830180">the</span> <span
  m="1830330">x1,</span> <span m="1831200">but</span> <span
  m="1832450">that</span> <span m="1833240">adds</span> <span
  m="1833520">up</span> <span m="1833700">to</span> <span
  m="1833860">three,</span> <span m="1834470">so</span> <span
  m="1834710">I</span> <span m="1834920">really</span> <span
  m="1835370">want</span> <span m="1835990">two</span> <span
  m="1836700">--</span> <span m="1836740">it's</span> <span
  m="1837070">going</span> <span m="1837480">to</span> <span
  m="1837530">be</span> <span m="1837700">two</span> <span
  m="1837910">thirds</span> <span m="1838270">of</span> <span
  m="1838370">a</span> <span m="1838440">thousand</span> <span
  m="1839090">and</span> <span m="1839320">one</span> <span
  m="1839560">third</span> <span m="1839820">of</span> <span
  m="1839900">a</span> <span m="1839950">thousand,</span> <span
  m="1840930">making</span> <span m="1841810">a</span> <span
  m="1841900">total</span> <span m="1842250">of</span> <span
  m="1842350">the</span> <span m="1842470">thousand</span></p><p><span
  m="1842980">people.</span> <span m="1843550">That'll</span> <span
  m="1843960">be</span> <span m="1844120">the</span> <span
  m="1844220">steady</span> <span m="1844600">state.</span></p><p><span
  m="1845480">That's</span> <span m="1845820">really</span> <span
  m="1846160">all</span> <span m="1846430">I</span> <span
  m="1846490">need</span> <span m="1846760">to</span> <span
  m="1846890">know</span> <span m="1847130">at</span> <span
  m="1847250">infinity.</span></p><p><span m="1848390">But</span> <span
  m="1848620">if</span> <span m="1848770">I</span> <span m="1848870">want</span>
  <span m="1849110">to</span> <span m="1849190">know</span> <span
  m="1849380">what's</span> <span m="1849670">happened</span> <span
  m="1850160">after</span> <span m="1850790">just</span> <span
  m="1851110">a</span> <span m="1851190">finite</span> <span
  m="1851710">number</span> <span m="1851960">like</span> <span
  m="1852150">100</span> <span m="1852650">steps,</span> <span
  m="1853280">I'd</span> <span m="1853560">better</span> <span
  m="1853820">find</span> <span m="1854100">this</span> <span
  m="1854320">eigenvector.</span></p><p><span m="1855380">So</span> <span
  m="1855640">can</span> <span m="1855830">I</span> <span m="1856110">--</span>
  <span m="1856570">can</span> <span m="1856740">I</span> <span
  m="1857020">look</span> <span m="1857520">at</span> <span
  m="1857710">--</span> <span m="1857840">I'll</span> <span
  m="1858000">subtract</span> <span m="1858610">point</span> <span
  m="1858890">seven</span> <span m="1859280">time</span> <span
  m="1859700">--</span> <span m="1859910">ti-</span> <span
  m="1860130">from</span> <span m="1860410">the</span> <span
  m="1860530">diagonal</span> <span m="1861950">and</span> <span
  m="1862730">I'll</span> <span m="1862890">get</span> <span
  m="1863110">that</span> <span m="1863970">and</span> <span
  m="1864710">I'll</span> <span m="1864960">look</span> <span
  m="1865250">at</span> <span m="1865400">the</span> <span
  m="1865830">null</span> <span m="1866250">space</span> <span
  m="1866720">of</span> <span m="1866830">that</span> <span
  m="1867100">one</span> <span m="1868180">and</span> <span m="1869250">I</span>
  <span m="1869280">--</span> <span m="1869330">and</span> <span
  m="1869390">this</span> <span m="1869620">is</span> <span
  m="1869770">going</span> <span m="1869940">to</span> <span
  m="1869990">give</span> <span m="1870240">me</span> <span
  m="1870540">x2,</span> <span m="1871280">now,</span> <span
  m="1871560">and</span> <span m="1871730">what</span> <span
  m="1871940">is</span> <span m="1872100">it?</span></p><p><span
  m="1873540">So</span> <span m="1873790">what's</span> <span
  m="1874170">in</span> <span m="1874360">the</span> <span
  m="1874470">null</span> <span m="1874700">space</span> <span
  m="1875100">of</span> <span m="1875170">--</span> <span
  m="1875190">that's</span> <span m="1875390">certainly</span> <span
  m="1875730">singular,</span> <span m="1876380">so</span> <span
  m="1876490">I</span> <span m="1876600">know</span> <span m="1876770">my</span>
  <span m="1876950">calculation</span> <span m="1877710">is</span> <span
  m="1877830">right,</span> <span m="1878460">and</span> <span
  m="1879280">--</span> <span m="1880920">one</span> <span
  m="1881220">and</span> <span m="1881390">minus</span> <span
  m="1881790">one.</span></p><p><span m="1884290">One</span> <span
  m="1884530">and</span> <span m="1884670">minus</span> <span
  m="1885090">one.</span></p><p><span m="1886240">So</span> <span
  m="1886450">I'm</span> <span m="1886620">prepared</span> <span
  m="1887150">now</span> <span m="1887590">to</span> <span
  m="1888900">write</span> <span m="1889940">down</span> <span
  m="1890580">the</span> <span m="1890700">solution</span> <span
  m="1891450">after</span> <span m="1891830">100</span> <span
  m="1892210">time</span></p><p><span m="1892470">steps.</span> <span
  m="1893180">The</span> <span m="1893430">--</span> <span
  m="1893460">the</span> <span m="1893630">populations</span> <span
  m="1894330">after</span> <span m="1894630">100</span> <span
  m="1894980">time</span> <span m="1895240">steps,</span></p><p><span
  m="1895670">right?</span> <span m="1896420">Can</span> <span
  m="1897130">--</span> <span m="1897150">can</span> <span m="1897340">we</span>
  <span m="1897470">remember</span> <span m="1897920">the</span> <span
  m="1898060">point</span> <span m="1898430">one</span> <span
  m="1898940">--</span> <span m="1898970">the</span> <span m="1899170">--</span>
  <span m="1899290">the</span> <span m="1899490">one</span> <span
  m="1899930">with</span> <span m="1900100">this</span> <span
  m="1900350">two</span> <span m="1900520">one</span> <span
  m="1900920">eigenvector</span> <span m="1901970">and</span> <span
  m="1902270">the</span> <span m="1902350">point</span> <span
  m="1902690">seven</span> <span m="1903100">with</span> <span
  m="1903240">the</span> <span m="1903340">minus</span> <span
  m="1903730">one</span> <span m="1903980">one</span> <span
  m="1904270">eigenvector.</span></p><p><span m="1904930">So</span> <span
  m="1905150">I'll</span> <span m="1905440">--</span> <span
  m="1905480">let</span> <span m="1905570">me</span> <span m="1905880">--</span>
  <span m="1906160">I'll</span> <span m="1906280">just</span> <span
  m="1906460">write</span> <span m="1906650">it</span> <span
  m="1906770">above</span> <span m="1907070">here.</span></p><p><span
  m="1908960">u</span> <span m="1909550">after</span> <span m="1910060">k</span>
  <span m="1910410">steps</span> <span m="1911090">is</span> <span
  m="1911290">some</span> <span m="1911670">multiple</span> <span
  m="1912800">of</span> <span m="1913270">one</span> <span m="1913810">to</span>
  <span m="1913960">the</span> <span m="1914100">k</span> <span
  m="1914960">times</span> <span m="1915540">the</span> <span
  m="1915680">two</span> <span m="1916010">one</span> <span
  m="1916380">eigenvector</span> <span m="1917610">and</span> <span
  m="1918000">some</span> <span m="1918350">multiple</span> <span
  m="1919360">of</span> <span m="1919740">point</span> <span
  m="1920140">seven</span> <span m="1920800">to</span> <span
  m="1920950">the</span> <span m="1921100">k</span> <span
  m="1922000">times</span> <span m="1922860">the</span> <span
  m="1923370">minus</span> <span m="1923870">one</span> <span
  m="1924230">one</span> <span m="1924590">eigenvector.</span> <span
  m="1927430">Right?</span></p><p><span m="1929910">That's</span> <span
  m="1930250">--</span> <span m="1930580">I</span> <span m="1930760">--</span>
  <span m="1931290">this</span> <span m="1931500">is</span> <span
  m="1931670">how</span> <span m="1931950">I</span> <span
  m="1932110">take</span> <span m="1932540">--</span> <span
  m="1932660">how</span> <span m="1932910">powers</span> <span
  m="1933420">of</span> <span m="1933540">a</span> <span
  m="1933600">matrix</span> <span m="1934100">work.</span></p><p><span
  m="1935010">When</span> <span m="1935310">I</span> <span
  m="1935380">apply</span> <span m="1935720">those</span> <span
  m="1936030">powers</span> <span m="1936540">to</span> <span
  m="1936720">a</span> <span m="1936820">u0,</span> <span
  m="1938490">what</span> <span m="1939550">I</span> <span m="1939720">--</span>
  <span m="1939740">so</span> <span m="1940160">it's</span> <span
  m="1940360">u0,</span> <span m="1941360">which</span> <span
  m="1941700">was</span> <span m="1942700">zero</span> <span
  m="1943440">a</span> <span m="1943500">thousand</span> <span
  m="1944100">--</span> <span m="1946390">that</span> <span
  m="1946690">has</span> <span m="1947020">to</span> <span m="1947130">be</span>
  <span m="1947700">corrected</span> <span m="1948610">k=0.</span> <span
  m="1949220">So</span> <span m="1949350">I'm</span> <span
  m="1949500">plugging</span> <span m="1949930">in</span> <span
  m="1950140">k=0</span> <span m="1951050">and</span> <span m="1951130">I</span>
  <span m="1951210">get</span> <span m="1951430">c1</span> <span
  m="1952090">times</span> <span m="1952420">two</span> <span
  m="1952600">one</span> <span m="1953510">and</span> <span
  m="1954130">c2</span> <span m="1954900">times</span> <span
  m="1955720">minus</span> <span m="1956190">one</span> <span
  m="1956500">one.</span></p><p><span m="1958640">Two</span> <span
  m="1958850">equations,</span> <span m="1960360">two</span> <span
  m="1961040">constants,</span> <span m="1962990">certainly</span> <span
  m="1964990">independent</span> <span m="1965640">eigenvectors,</span> <span
  m="1967550">so</span> <span m="1968610">there's</span> <span
  m="1968850">a</span> <span m="1968960">solution</span> <span
  m="1969710">and</span> <span m="1970100">you</span> <span
  m="1970270">see</span> <span m="1970520">what</span> <span
  m="1970740">it</span> <span m="1970860">is?</span></p><p><span
  m="1971770">Let's</span> <span m="1971970">see,</span> <span
  m="1972120">I</span> <span m="1972200">guess</span> <span
  m="1972420">we</span> <span m="1972610">already</span> <span
  m="1972970">figured</span> <span m="1973440">that</span> <span
  m="1973660">c1</span> <span m="1974700">was</span> <span m="1975560">a</span>
  <span m="1975830">thousand</span> <span m="1976450">over</span> <span
  m="1976720">three,</span> <span m="1977360">I</span> <span
  m="1977420">think</span> <span m="1977690">--</span> <span
  m="1977710">did</span> <span m="1977840">we</span> <span
  m="1978000">think</span> <span m="1978250">that</span> <span
  m="1978440">had</span> <span m="1978600">to</span> <span m="1978660">be</span>
  <span m="1978770">a</span> <span m="1978850">thousand</span> <span
  m="1979390">over</span> <span m="1979620">three?</span></p><p><span
  m="1982200">And</span> <span m="1982540">maybe</span> <span
  m="1982950">c2</span> <span m="1983870">would</span> <span
  m="1984080">be</span> <span m="1984680">--</span> <span
  m="1985840">excuse</span> <span m="1986140">me,</span> <span
  m="1986330">let</span> <span m="1986500">--</span> <span
  m="1986530">get</span> <span m="1986680">an</span> <span
  m="1986800">eraser</span> <span m="1987390">--</span> <span
  m="1987920">we</span> <span m="1988150">can</span> <span m="1988400">--</span>
  <span m="1988930">I</span> <span m="1989040">just</span> <span
  m="1989310">--</span> <span m="1989330">I</span> <span
  m="1989430">think</span> <span m="1989680">we've</span> <span
  m="1989910">--</span> <span m="1989930">get</span> <span m="1990090">it</span>
  <span m="1990400">here.</span> <span m="1991330">c2,</span> <span
  m="1992110">we</span> <span m="1992340">want</span> <span
  m="1992560">to</span> <span m="1992610">get</span> <span m="1992810">a</span>
  <span m="1992880">zero</span> <span m="1993320">here,</span> <span
  m="1994260">so</span> <span m="1994780">maybe</span> <span
  m="1995340">we</span> <span m="1995590">need</span> <span
  m="1996330">plus</span> <span m="1997580">two</span> <span
  m="1998340">thousand</span> <span m="1998860">over</span> <span
  m="1999110">three.</span></p><p><span m="2001400">I</span> <span
  m="2001490">think</span> <span m="2001730">that</span> <span
  m="2002030">has</span> <span m="2002310">to</span> <span
  m="2002430">work.</span></p><p><span m="2002840">Two</span> <span
  m="2003110">times</span> <span m="2003420">a</span> <span
  m="2003510">thousand</span> <span m="2004000">over</span> <span
  m="2004220">three</span> <span m="2004850">minus</span> <span
  m="2005480">two</span> <span m="2005670">thousand</span> <span
  m="2006010">over</span> <span m="2006180">three,</span> <span
  m="2006490">that'll</span> <span m="2006770">give</span> <span
  m="2006970">us</span> <span m="2007110">the</span> <span
  m="2007190">zero</span> <span m="2008100">and</span> <span
  m="2008660">a</span> <span m="2008740">thousand</span> <span
  m="2009160">over</span> <span m="2009400">three</span> <span
  m="2010010">and</span> <span m="2010160">the</span> <span
  m="2010280">two</span> <span m="2010490">thousand</span> <span
  m="2010860">over</span> <span m="2011060">three</span> <span
  m="2011470">will</span> <span m="2011640">give</span> <span
  m="2011830">us</span> <span m="2012020">three</span> <span
  m="2012260">thousand</span> <span m="2012710">over</span> <span
  m="2012910">three,</span></p><p><span m="2013290">the</span> <span
  m="2013420">thousand.</span> <span m="2014160">So</span> <span
  m="2014810">this</span> <span m="2015160">is</span> <span
  m="2015350">what</span> <span m="2015930">we</span> <span
  m="2016250">approach</span> <span m="2017010">--</span> <span
  m="2017820">this</span> <span m="2018340">part,</span> <span
  m="2018790">with</span> <span m="2018950">the</span> <span
  m="2019060">point</span> <span m="2019420">seven</span> <span
  m="2020470">to</span> <span m="2021000">the</span> <span
  m="2021130">k-th</span> <span m="2021510">power</span> <span
  m="2022000">is</span> <span m="2022200">the</span> <span
  m="2022290">part</span> <span m="2022580">that's</span> <span
  m="2022840">disappearing.</span> <span m="2025050">That's</span> <span
  m="2025910">--</span> <span m="2025960">that's</span> <span
  m="2026700">Markov</span> <span m="2027390">matrices.</span></p><p><span
  m="2028280">Okay.</span></p><p><span m="2028770">That's</span> <span
  m="2028990">an</span> <span m="2029080">example</span> <span
  m="2029760">of</span> <span m="2030090">where</span> <span
  m="2030320">they</span> <span m="2030480">come</span> <span
  m="2030770">from,</span> <span m="2032610">from</span> <span
  m="2033180">modeling</span> <span m="2034370">movement</span> <span
  m="2035320">of</span> <span m="2035440">people</span> <span
  m="2036610">with</span> <span m="2037160">no</span> <span
  m="2038400">gain</span> <span m="2039460">or</span> <span
  m="2039580">loss,</span> <span m="2040220">with</span> <span
  m="2040760">total</span> <span m="2041360">--</span> <span
  m="2041550">total</span> <span m="2041900">count</span> <span
  m="2042270">conserved.</span></p><p><span m="2043690">Okay.</span></p><p><span
  m="2044440">I</span> <span m="2044900">--</span> <span m="2045170">just</span>
  <span m="2045550">if</span> <span m="2045760">I</span> <span
  m="2045850">can</span> <span m="2046030">add</span> <span
  m="2046250">one</span> <span m="2046480">more</span> <span
  m="2046700">comment,</span> <span m="2047260">because</span> <span
  m="2047580">you'll</span> <span m="2047760">see</span> <span
  m="2047990">Markov</span> <span m="2048460">matrices</span> <span
  m="2049510">in</span> <span m="2050659">electrical</span> <span
  m="2051550">engineering</span> <span m="2052110">courses</span> <span
  m="2053500">and</span> <span m="2054330">often</span> <span
  m="2055120">you'll</span> <span m="2055469">see</span> <span
  m="2056239">them</span> <span m="2056770">--</span> <span
  m="2056790">sorry,</span> <span m="2056949">here's</span> <span
  m="2057130">my</span> <span m="2057290">little</span> <span
  m="2057560">comment.</span></p><p><span m="2059679">Sometimes</span> <span
  m="2060500">--</span> <span m="2060520">in</span> <span m="2060639">a</span>
  <span m="2060719">lot</span> <span m="2060949">of</span> <span
  m="2061050">applications</span> <span m="2061780">they</span> <span
  m="2061929">prefer</span> <span m="2062280">to</span> <span
  m="2062360">work</span> <span m="2062610">with</span> <span
  m="2062760">row</span> <span m="2063050">vectors.</span></p><p><span
  m="2065590">So</span> <span m="2065860">they</span> <span
  m="2066199">--</span> <span m="2066750">instead</span> <span
  m="2067190">of</span> <span m="2067350">--</span> <span
  m="2067500">this</span> <span m="2068020">was</span> <span
  m="2068219">natural</span> <span m="2068719">for</span> <span
  m="2068929">us,</span> <span m="2069170">right?</span></p><p><span
  m="2069480">For</span> <span m="2069630">all</span> <span
  m="2069770">the</span> <span m="2069880">eigenvectors</span> <span
  m="2070550">to</span> <span m="2070639">be</span> <span
  m="2070790">column</span> <span m="2071190">vectors.</span></p><p><span
  m="2072429">So</span> <span m="2072639">our</span> <span
  m="2072909">columns</span> <span m="2073550">added</span> <span
  m="2074409">to</span> <span m="2074870">one</span> <span m="2075400">in</span>
  <span m="2075650">the</span> <span m="2075719">Markov</span> <span
  m="2076170">matrix.</span></p><p><span m="2077139">Just</span> <span
  m="2077400">so</span> <span m="2077600">you</span> <span
  m="2077760">don't</span> <span m="2078020">think,</span> <span
  m="2078360">well,</span> <span m="2078719">what</span> <span
  m="2079210">--</span> <span m="2079889">what's</span> <span
  m="2080610">going</span> <span m="2080860">on?</span></p><p><span
  m="2081820">If</span> <span m="2082650">we</span> <span
  m="2083010">work</span> <span m="2083290">with</span> <span
  m="2083469">row</span> <span m="2083800">vectors</span> <span
  m="2084440">and</span> <span m="2084570">we</span> <span
  m="2084690">multiply</span> <span m="2086050">vector</span> <span
  m="2086889">times</span> <span m="2087239">matrix</span> <span
  m="2088170">--</span> <span m="2088199">so</span> <span
  m="2088330">we're</span> <span m="2089389">multiplying</span> <span
  m="2089909">from</span> <span m="2090080">the</span> <span
  m="2090179">left</span> <span m="2090770">--</span> <span
  m="2091179">then</span> <span m="2092130">it'll</span> <span
  m="2092500">be</span> <span m="2092900">the</span> <span
  m="2093360">then</span> <span m="2093800">we'll</span> <span
  m="2093980">be</span> <span m="2094120">using</span> <span
  m="2094510">the</span> <span m="2094650">transpose</span> <span
  m="2095409">of</span> <span m="2095600">--</span> <span m="2095679">of</span>
  <span m="2095800">this</span> <span m="2096050">matrix</span> <span
  m="2096840">and</span> <span m="2097180">it'll</span> <span
  m="2097370">be</span> <span m="2097650">the</span> <span
  m="2097780">rows</span> <span m="2098350">that</span> <span
  m="2098520">add</span> <span m="2098770">to</span> <span
  m="2098890">one.</span></p><p><span m="2100100">So</span> <span
  m="2100610">in</span> <span m="2101320">other</span> <span
  m="2101830">textbooks,</span> <span m="2102890">you'll</span> <span
  m="2103400">see</span> <span m="2104160">--</span> <span
  m="2104420">instead</span> <span m="2104810">of</span> <span
  m="2104930">col-</span> <span m="2105390">columns</span> <span
  m="2105970">adding</span> <span m="2106300">to</span> <span
  m="2106420">one,</span> <span m="2106700">you'll</span> <span
  m="2106860">see</span> <span m="2107080">rows</span> <span
  m="2107400">add</span> <span m="2107410">to</span> <span
  m="2107420">one.</span> <span m="2108200">Okay.</span> <span
  m="2109320">Fine.</span></p><p><span m="2110410">Okay,</span> <span
  m="2110800">that's</span> <span m="2111290">what</span> <span
  m="2111540">I</span> <span m="2111600">wanted</span> <span
  m="2111890">to</span> <span m="2111990">say</span> <span
  m="2112170">about</span> <span m="2112440">Markov,</span> <span
  m="2113030">now</span> <span m="2113400">I</span> <span
  m="2113500">want</span> <span m="2113710">to</span> <span
  m="2113780">say</span> <span m="2114060">something</span> <span
  m="2114690">about</span> <span m="2115450">projections</span> <span
  m="2116670">and</span> <span m="2117260">even</span> <span
  m="2117560">leading</span> <span m="2118040">in</span> <span
  m="2118340">--</span> <span m="2118380">a</span> <span
  m="2118460">little</span> <span m="2118860">into</span> <span
  m="2119100">Fourier</span> <span m="2119570">series.</span></p><p><span
  m="2122190">Because</span> <span m="2122740">--</span> <span
  m="2123130">but</span> <span m="2123360">before</span> <span
  m="2123790">any</span> <span m="2123970">Fourier</span> <span
  m="2124460">stuff,</span> <span m="2124960">let</span> <span
  m="2125150">me</span> <span m="2125320">make</span> <span m="2125580">a</span>
  <span m="2125670">comment</span> <span m="2126070">about</span> <span
  m="2126370">projections.</span></p><p><span m="2128150">This</span> <span
  m="2128360">--</span> <span m="2128380">so</span> <span
  m="2128510">this</span> <span m="2128640">is</span> <span m="2128770">a</span>
  <span m="2128850">comment</span> <span m="2129300">about</span> <span
  m="2129660">projections</span> <span m="2131260">onto</span> <span
  m="2132880">--</span> <span m="2133310">with</span> <span
  m="2134340">an</span> <span m="2135220">orthonormal</span> <span
  m="2136150">basis.</span></p><p><span m="2142420">So,</span> <span
  m="2142820">of</span> <span m="2142990">course,</span> <span
  m="2143680">the</span> <span m="2144270">basis</span> <span
  m="2144760">vectors</span> <span m="2145320">are</span> <span
  m="2145580">q1</span> <span m="2146370">up</span> <span m="2146560">to</span>
  <span m="2147040">qn.</span> <span m="2149770">Okay.</span></p><p><span
  m="2150860">I</span> <span m="2151010">have</span> <span m="2151390">a</span>
  <span m="2151450">vector</span> <span m="2151870">b.</span></p><p><span
  m="2152330">Let</span> <span m="2153740">--</span> <span
  m="2155150">let</span> <span m="2155500">me</span> <span
  m="2155740">imagine</span> <span m="2156610">--</span> <span
  m="2157000">let</span> <span m="2157130">me</span> <span
  m="2157250">imagine</span> <span m="2157690">this</span> <span
  m="2157900">is</span> <span m="2158080">a</span> <span
  m="2158140">basis.</span></p><p><span m="2158700">Let</span> <span
  m="2158820">--</span> <span m="2159070">let's</span> <span
  m="2159310">say</span> <span m="2159510">I'm</span> <span
  m="2159720">in</span> <span m="2159850">n</span> <span m="2160060">by</span>
  <span m="2160240">n.</span></p><p><span m="2160640">I'm</span> <span
  m="2160860">--</span> <span m="2160890">I've</span> <span
  m="2161120">got,</span> <span m="2161510">eh,</span> <span
  m="2164330">n</span> <span m="2165100">orthonormal</span> <span
  m="2165880">vectors,</span> <span m="2166660">I'm</span> <span
  m="2166900">in</span> <span m="2167080">n</span> <span
  m="2167320">dimensional</span> <span m="2167900">space</span> <span
  m="2168460">so</span> <span m="2168600">they're</span> <span
  m="2168810">a</span> <span m="2168860">complete</span> <span
  m="2169330">--</span> <span m="2169350">they're</span> <span
  m="2169490">a</span> <span m="2169540">basis</span> <span
  m="2170270">--</span> <span m="2171110">any</span> <span
  m="2171460">vector</span> <span m="2172550">v</span> <span
  m="2173530">could</span> <span m="2173930">be</span> <span
  m="2174090">expanded</span> <span m="2174760">in</span> <span
  m="2174870">this</span> <span m="2175090">basis.</span></p><p><span
  m="2176170">So</span> <span m="2176390">any</span> <span
  m="2176630">vector</span> <span m="2177100">v</span> <span
  m="2178090">is</span> <span m="2178460">some</span> <span
  m="2178920">combination,</span> <span m="2179810">some</span> <span
  m="2180240">amount</span> <span m="2180770">of</span> <span
  m="2180940">q1</span> <span m="2182050">plus</span> <span
  m="2182660">some</span> <span m="2182870">amount</span> <span
  m="2183280">of</span> <span m="2183410">q2</span> <span
  m="2184650">plus</span> <span m="2185370">some</span> <span
  m="2185600">amount</span> <span m="2186330">of</span> <span
  m="2186780">qn.</span> <span m="2188060">So</span> <span m="2189060">--</span>
  <span m="2189080">so</span> <span m="2189250">any</span> <span
  m="2189560">v.</span></p><p><span m="2195220">I</span> <span
  m="2195390">just</span> <span m="2195630">want</span> <span
  m="2195910">you</span> <span m="2196030">to</span> <span
  m="2196630">tell</span> <span m="2197020">me</span> <span
  m="2197170">what</span> <span m="2197460">those</span> <span
  m="2198600">amounts</span> <span m="2199430">are.</span></p><p><span
  m="2201740">What</span> <span m="2202030">are</span> <span
  m="2202380">x1</span> <span m="2202650">--</span> <span
  m="2203110">what's</span> <span m="2203360">x1,</span> <span
  m="2203850">for</span> <span m="2204090">example?</span></p><p><span
  m="2206510">So</span> <span m="2206680">I'm</span> <span
  m="2206810">looking</span> <span m="2207170">for</span> <span
  m="2208260">the</span> <span m="2208980">expansion.</span></p><p><span
  m="2209980">This</span> <span m="2210150">is</span> <span
  m="2210320">--</span> <span m="2210340">this</span> <span
  m="2210570">is</span> <span m="2210720">really</span> <span
  m="2211000">our</span> <span m="2211150">projection.</span></p><p><span
  m="2211900">I</span> <span m="2212000">could</span> <span
  m="2212290">--</span> <span m="2212350">I</span> <span
  m="2212530">could</span> <span m="2212740">really</span> <span
  m="2213040">use</span> <span m="2213290">the</span> <span
  m="2213380">word</span> <span m="2213780">expansion.</span></p><p><span
  m="2216330">I'm</span> <span m="2216550">expanding</span> <span
  m="2217850">the</span> <span m="2218130">vector</span> <span
  m="2218740">in</span> <span m="2218910">the</span> <span
  m="2219000">basis.</span></p><p><span m="2221450">And</span> <span
  m="2221730">the</span> <span m="2221840">special</span> <span
  m="2222290">thing</span> <span m="2222510">about</span> <span
  m="2222800">the</span> <span m="2222890">basis</span> <span
  m="2223410">is</span> <span m="2224020">that</span> <span
  m="2224240">it's</span> <span m="2224400">orthonormal.</span></p><p><span
  m="2225770">So</span> <span m="2226070">that</span> <span
  m="2226330">should</span> <span m="2226770">give</span> <span
  m="2226980">me</span> <span m="2227460">a</span> <span
  m="2227660">special</span> <span m="2228690">formula</span> <span
  m="2229350">for</span> <span m="2229650">the</span> <span
  m="2229840">answer,</span> <span m="2230470">for</span> <span
  m="2230700">the</span> <span m="2230840">coefficients.</span></p><p><span
  m="2232220">So</span> <span m="2232440">how</span> <span m="2232660">do</span>
  <span m="2232770">I</span> <span m="2232870">get</span> <span
  m="2233210">x1?</span> <span m="2234010">What</span> <span
  m="2234240">--</span> <span m="2234260">what's</span> <span
  m="2234490">a</span> <span m="2234580">formula</span> <span
  m="2235030">for</span> <span m="2235240">x1?</span> <span m="2238250">I</span>
  <span m="2238420">could</span> <span m="2238990">--</span> <span
  m="2239260">I</span> <span m="2239440">can</span> <span m="2239680">go</span>
  <span m="2239880">through</span> <span m="2240200">the</span> <span
  m="2240350">projection</span> <span m="2241480">--</span> <span
  m="2243040">the</span> <span m="2243360">Q</span> <span
  m="2243700">transpose</span> <span m="2244490">Q,</span> <span
  m="2245410">all</span> <span m="2245680">that</span> <span
  m="2246090">--</span> <span m="2246940">normal</span> <span
  m="2247650">equations,</span> <span m="2249070">but</span> <span
  m="2250130">--</span> <span m="2251450">and</span> <span
  m="2251750">I'll</span> <span m="2251880">get</span> <span
  m="2252110">--</span> <span m="2252140">I'll</span> <span
  m="2252390">come</span> <span m="2252620">out</span> <span
  m="2252860">with</span> <span m="2253020">this</span> <span
  m="2253250">nice</span> <span m="2253600">answer</span> <span
  m="2253960">that</span> <span m="2254160">I</span> <span
  m="2254300">think</span> <span m="2254580">I</span> <span
  m="2254670">can</span> <span m="2254860">see</span> <span
  m="2255090">right</span> <span m="2255350">away.</span></p><p><span
  m="2256060">How</span> <span m="2256350">can</span> <span m="2256570">I</span>
  <span m="2256660">pick</span> <span m="2257090">--</span> <span
  m="2258370">get</span> <span m="2258530">a</span> <span
  m="2258580">hold</span> <span m="2258830">of</span> <span
  m="2258920">x1</span> <span m="2259830">and</span> <span
  m="2260050">get</span> <span m="2260250">these</span> <span
  m="2260500">other</span> <span m="2260780">x-s</span> <span
  m="2261240">out</span> <span m="2261500">of</span> <span
  m="2261590">the</span> <span m="2261740">equation?</span></p><p><span
  m="2262920">So</span> <span m="2263170">how</span> <span
  m="2263380">can</span> <span m="2263550">I</span> <span m="2263630">get</span>
  <span m="2263840">a</span> <span m="2263980">nice,</span> <span
  m="2264600">simple</span> <span m="2265020">formula</span> <span
  m="2265480">for</span> <span m="2265680">x1?</span></p><p><span
  m="2267460">And</span> <span m="2267730">then</span> <span
  m="2267890">we</span> <span m="2267990">want</span> <span
  m="2268320">to</span> <span m="2268400">see,</span> <span
  m="2268740">sure,</span> <span m="2269310">we</span> <span
  m="2269490">knew</span> <span m="2269680">that</span> <span
  m="2269910">all</span> <span m="2270050">the</span> <span
  m="2270150">time.</span></p><p><span m="2270800">Okay.</span> <span
  m="2271250">So</span> <span m="2271490">what's</span> <span
  m="2271780">x1?</span> <span m="2272610">The</span> <span
  m="2272950">good</span> <span m="2273200">way</span> <span
  m="2273520">is</span> <span m="2274250">take</span> <span
  m="2274660">the</span> <span m="2274800">inner</span> <span
  m="2275030">product</span> <span m="2275490">of</span> <span
  m="2275610">everything</span> <span m="2277010">with</span> <span
  m="2277910">q1.</span> <span m="2279020">Take</span> <span
  m="2279730">the</span> <span m="2279850">inner</span> <span
  m="2280040">product</span> <span m="2280390">of</span> <span
  m="2280470">that</span> <span m="2280660">whole</span> <span
  m="2281010">equation,</span> <span m="2281580">every</span> <span
  m="2281880">term,</span> <span m="2282430">with</span> <span
  m="2282760">q1.</span> <span m="2283850">What</span> <span
  m="2284480">will</span> <span m="2284670">happen</span> <span
  m="2285570">to</span> <span m="2285930">that</span> <span
  m="2286180">last</span> <span m="2286530">term?</span></p><p><span
  m="2288370">The</span> <span m="2288480">inner</span> <span
  m="2288690">product</span> <span m="2289170">--</span> <span
  m="2289190">when</span> <span m="2289330">--</span> <span
  m="2289390">if</span> <span m="2289570">I</span> <span m="2289670">take</span>
  <span m="2289970">the</span> <span m="2290090">dot</span> <span
  m="2290360">product</span> <span m="2290790">with</span> <span
  m="2290960">q1</span> <span m="2291560">I</span> <span m="2291650">get</span>
  <span m="2292770">zero,</span> <span m="2293640">right?</span></p><p><span
  m="2293970">Because</span> <span m="2294520">this</span> <span
  m="2294810">basis</span> <span m="2295320">was</span> <span
  m="2295530">orthonormal.</span></p><p><span m="2297160">If</span> <span
  m="2297300">I</span> <span m="2297390">take</span> <span
  m="2297640">the</span> <span m="2297750">dot</span> <span
  m="2297990">product</span> <span m="2298430">with</span> <span
  m="2298610">q2</span> <span m="2299100">I</span> <span m="2299180">get</span>
  <span m="2299430">zero.</span></p><p><span m="2300330">If</span> <span
  m="2300490">I</span> <span m="2300580">take</span> <span
  m="2300810">the</span> <span m="2300920">dot</span> <span
  m="2301160">product</span> <span m="2301530">with</span> <span
  m="2301710">q1</span> <span m="2302230">I</span> <span m="2302330">get</span>
  <span m="2303260">one.</span></p><p><span m="2304570">So</span> <span
  m="2305190">that</span> <span m="2305440">tells</span> <span
  m="2305680">me</span> <span m="2305800">what</span> <span
  m="2305970">x1</span> <span m="2306420">is.</span> <span m="2306920">q1</span>
  <span m="2307800">transpose</span> <span m="2308740">v,</span> <span
  m="2309480">that's</span> <span m="2310110">taking</span> <span
  m="2310430">the</span> <span m="2310560">dot</span> <span
  m="2310820">product,</span> <span m="2311250">is</span> <span
  m="2311980">x1</span> <span m="2313410">times</span> <span
  m="2314420">q1</span> <span m="2315330">transpose</span> <span
  m="2316400">q1</span> <span m="2317410">plus</span> <span m="2318990">a</span>
  <span m="2319160">bunch</span> <span m="2319430">of</span> <span
  m="2319540">zeroes.</span> <span m="2321060">And</span> <span
  m="2322500">this</span> <span m="2322740">is</span> <span m="2322890">a</span>
  <span m="2322980">one,</span> <span m="2323460">so</span> <span
  m="2323700">I</span> <span m="2323810">can</span> <span
  m="2324050">forget</span> <span m="2324450">that.</span></p><p><span
  m="2325330">I</span> <span m="2325430">get</span> <span m="2325630">x1</span>
  <span m="2326050">immediately.</span></p><p><span m="2327820">So</span> <span
  m="2328150">--</span> <span m="2328220">do</span> <span m="2328590">you</span>
  <span m="2328970">see</span> <span m="2329070">what</span> <span
  m="2329240">I'm</span> <span m="2329370">saying</span> <span
  m="2329810">--</span> <span m="2329840">is</span> <span
  m="2330060">that</span> <span m="2330220">I</span> <span
  m="2330600">have</span> <span m="2331130">an</span> <span
  m="2331260">orthonormal</span> <span m="2332010">basis,</span> <span
  m="2333070">then</span> <span m="2333960">the</span> <span
  m="2334660">coefficient</span> <span m="2335800">that</span> <span
  m="2335980">I</span> <span m="2336090">need</span> <span
  m="2336570">for</span> <span m="2336790">each</span> <span
  m="2337130">basis</span> <span m="2337590">vector</span> <span
  m="2338450">is</span> <span m="2338760">a</span> <span
  m="2338850">cinch</span> <span m="2339220">to</span></p><p><span
  m="2339340">find.</span> <span m="2340070">Let</span> <span
  m="2340570">me</span> <span m="2340750">--</span> <span m="2340790">let</span>
  <span m="2340910">me</span> <span m="2341020">just</span> <span
  m="2341760">--</span> <span m="2342310">I</span> <span m="2342490">have</span>
  <span m="2342730">to</span> <span m="2343310">put</span> <span
  m="2343830">this</span> <span m="2344070">into</span> <span
  m="2344290">matrix</span> <span m="2344800">language,</span> <span
  m="2345300">too,</span> <span m="2345580">so</span> <span
  m="2345750">you'll</span> <span m="2345890">see</span> <span
  m="2346090">it</span> <span m="2346250">there</span> <span
  m="2346520">also.</span></p><p><span m="2347350">If</span> <span
  m="2347540">I</span> <span m="2347650">write</span> <span
  m="2347980">that</span> <span m="2348270">first</span> <span
  m="2348600">equation</span> <span m="2349160">in</span> <span
  m="2349290">matrix</span> <span m="2349820">language,</span> <span
  m="2350360">what</span> <span m="2350570">--</span> <span
  m="2350690">what</span> <span m="2350960">is</span> <span
  m="2351140">it?</span></p><p><span m="2352010">I'm</span> <span
  m="2352210">writing</span> <span m="2352730">--</span> <span
  m="2352760">in</span> <span m="2352920">matrix</span> <span
  m="2353410">language,</span> <span m="2353870">this</span> <span
  m="2354070">equation</span> <span m="2354630">says</span> <span
  m="2355430">I'm</span> <span m="2355880">taking</span> <span
  m="2356450">these</span> <span m="2356790">columns</span> <span
  m="2357730">--</span> <span m="2358160">are</span> <span m="2358590">--</span>
  <span m="2359020">are</span> <span m="2359150">you</span> <span
  m="2359470">guys</span> <span m="2359780">good</span> <span
  m="2359980">at</span> <span m="2360100">this</span> <span
  m="2360330">now?</span></p><p><span m="2360620">I'm</span> <span
  m="2360780">taking</span> <span m="2361140">those</span> <span
  m="2361430">columns</span> <span m="2362040">times</span> <span
  m="2362410">the</span> <span m="2362580">Xs</span> <span
  m="2364340">and</span> <span m="2365530">getting</span> <span
  m="2366370">V,</span> <span m="2367430">right?</span></p><p><span
  m="2369180">That's</span> <span m="2369440">the</span> <span
  m="2369540">matrix</span> <span m="2370030">form.</span></p><p><span
  m="2370440">Okay,</span> <span m="2370860">that's</span> <span
  m="2371110">the</span> <span m="2371200">matrix</span> <span
  m="2371840">Q.</span> <span m="2373450">Qx</span> <span m="2374380">is</span>
  <span m="2374930">v.</span></p><p><span m="2377470">What's</span> <span
  m="2377720">the</span> <span m="2377830">solution</span> <span
  m="2378390">to</span> <span m="2378470">that</span> <span
  m="2378700">equation?</span></p><p><span m="2381570">It's</span> <span
  m="2381830">--</span> <span m="2381860">of</span> <span
  m="2382000">course,</span> <span m="2382380">it's</span> <span
  m="2382580">x</span> <span m="2382900">equal</span> <span m="2383460">Q</span>
  <span m="2383700">inverse</span> <span m="2384200">v.</span></p><p><span
  m="2384920">So</span> <span m="2385110">x</span> <span m="2385520">is</span>
  <span m="2386320">Q</span> <span m="2386860">inverse</span> <span
  m="2387370">v,</span> <span m="2387890">but</span> <span
  m="2388260">what's</span> <span m="2388600">the</span> <span
  m="2388700">point?</span></p><p><span m="2391000">Q</span> <span
  m="2391320">inverse</span> <span m="2391880">in</span> <span
  m="2392010">this</span> <span m="2392280">case</span> <span
  m="2392750">is</span> <span m="2393220">going</span> <span
  m="2393390">to</span> <span m="2393440">--</span> <span m="2393470">is</span>
  <span m="2393620">simple.</span></p><p><span m="2394060">I</span> <span
  m="2394140">don't</span> <span m="2394390">have</span> <span
  m="2394590">to</span> <span m="2394800">work</span> <span
  m="2395240">to</span> <span m="2395430">invert</span> <span
  m="2396200">this</span> <span m="2396690">matrix</span> <span
  m="2397330">Q,</span> <span m="2398220">because</span> <span
  m="2398990">of</span> <span m="2399070">the</span> <span
  m="2399200">fact</span> <span m="2399670">that</span> <span
  m="2399940">the</span> <span m="2400330">--</span> <span
  m="2400360">these</span> <span m="2401060">columns</span> <span
  m="2401810">are</span> <span m="2402020">orthonormal,</span> <span
  m="2403110">I</span> <span m="2403380">know</span> <span
  m="2403650">the</span> <span m="2403810">inverse</span> <span
  m="2404340">to</span> <span m="2404470">that.</span></p><p><span
  m="2405110">And</span> <span m="2405340">it</span> <span m="2405490">is</span>
  <span m="2406490">Q</span> <span m="2407190">transpose.</span> <span
  m="2410070">When</span> <span m="2411100">you</span> <span
  m="2411220">see</span> <span m="2411480">a</span> <span m="2411590">Q,</span>
  <span m="2412430">a</span> <span m="2412540">square</span> <span
  m="2412960">matrix</span> <span m="2413560">with</span> <span
  m="2413750">that</span> <span m="2413930">letter</span> <span
  m="2414330">Q,</span> <span m="2415050">the</span> <span m="2415490">--</span>
  <span m="2415510">that</span> <span m="2415810">just</span> <span
  m="2416100">triggers</span> <span m="2416730">--</span> <span
  m="2417090">Q</span> <span m="2417360">inverse</span> <span
  m="2417800">is</span> <span m="2417960">the</span> <span
  m="2418070">same</span> <span m="2418370">as</span> <span m="2418520">Q</span>
  <span m="2418730">transpose.</span></p><p><span m="2419670">So</span> <span
  m="2419890">the</span> <span m="2420010">first</span> <span
  m="2420400">component,</span> <span m="2421000">then</span> <span
  m="2421420">--</span> <span m="2422100">the</span> <span
  m="2422190">first</span> <span m="2422540">component</span> <span
  m="2423060">of</span> <span m="2423180">x</span> <span m="2423860">is</span>
  <span m="2424430">the</span> <span m="2424570">first</span> <span
  m="2425030">row</span> <span m="2425490">times</span> <span
  m="2425970">v,</span> <span m="2426780">and</span> <span
  m="2427240">what's</span> <span m="2427480">that?</span></p><p><span
  m="2429550">The</span> <span m="2429690">first</span> <span
  m="2430470">component</span> <span m="2431310">of</span> <span
  m="2431410">this</span> <span m="2431660">answer</span> <span
  m="2432650">is</span> <span m="2433340">the</span> <span
  m="2433460">first</span> <span m="2433930">row</span> <span
  m="2434340">of</span> <span m="2434470">Q</span> <span
  m="2434730">transpose.</span></p><p><span m="2436570">That's</span> <span
  m="2436840">just</span> <span m="2437380">--</span> <span
  m="2438560">that's</span> <span m="2438860">just</span> <span
  m="2439150">q1</span> <span m="2439630">transpose</span> <span
  m="2440860">times</span> <span m="2441350">v.</span></p><p><span
  m="2442110">So</span> <span m="2442840">that's</span> <span
  m="2443240">what</span> <span m="2443490">we</span> <span
  m="2444090">concluded</span> <span m="2444980">here,</span> <span
  m="2445310">too.</span></p><p><span m="2446320">Okay.</span></p><p><span
  m="2449590">So</span> <span m="2450100">--</span> <span m="2452750">so</span>
  <span m="2452940">nothing</span> <span m="2453310">Fourier</span> <span
  m="2453830">here.</span></p><p><span m="2455090">The</span> <span
  m="2455620">--</span> <span m="2455830">the</span> <span
  m="2456070">key</span> <span m="2456780">ingredient</span> <span
  m="2457530">here</span> <span m="2457950">was</span> <span
  m="2458730">that</span> <span m="2459050">the</span> <span
  m="2459170">q-s</span> <span m="2459570">are</span> <span
  m="2459650">orthonormal.</span></p><p><span m="2461460">And</span> <span
  m="2461850">now</span> <span m="2462210">that's</span> <span
  m="2462630">what</span> <span m="2463020">Fourier</span> <span
  m="2463480">series</span> <span m="2463910">are</span> <span
  m="2463990">built</span> <span m="2464320">on.</span></p><p><span
  m="2464900">So</span> <span m="2465130">now,</span> <span
  m="2465610">in</span> <span m="2466080">the</span> <span
  m="2466170">remaining</span> <span m="2467160">time,</span> <span
  m="2468320">let</span> <span m="2468520">me</span> <span
  m="2468640">say</span> <span m="2468900">something</span> <span
  m="2469190">about</span> <span m="2469470">Fourier</span> <span
  m="2469860">series.</span></p><p><span m="2471760">Okay.</span></p><p><span
  m="2472400">So</span> <span m="2472600">Fourier</span> <span
  m="2473070">series</span> <span m="2478020">is</span> <span
  m="2478840">--</span> <span m="2480120">well,</span> <span
  m="2481080">we've</span> <span m="2481270">got</span> <span
  m="2481470">a</span> <span m="2481520">function</span> <span
  m="2482120">f</span> <span m="2482350">of</span> <span
  m="2482500">x.</span></p><p><span m="2485150">And</span> <span
  m="2485430">we</span> <span m="2485570">want</span> <span
  m="2485790">to</span> <span m="2485850">write</span> <span
  m="2486180">it</span> <span m="2486700">as</span> <span m="2487120">a</span>
  <span m="2487210">combination</span> <span m="2488020">of</span> <span
  m="2488140">--</span> <span m="2488160">maybe</span> <span
  m="2488450">it</span> <span m="2488550">has</span> <span m="2488790">a</span>
  <span m="2488890">constant</span> <span m="2489490">term.</span></p><p><span
  m="2490900">And</span> <span m="2491000">then</span> <span
  m="2491160">it</span> <span m="2491290">has</span> <span
  m="2491680">some</span> <span m="2492470">cos(x)</span> <span
  m="2493810">in</span> <span m="2493960">it.</span></p><p><span
  m="2494910">And</span> <span m="2495100">it</span> <span
  m="2495230">has</span> <span m="2495560">some</span> <span
  m="2495940">sin(x)</span> <span m="2496780">in</span> <span
  m="2496950">it.</span></p><p><span m="2498120">And</span> <span
  m="2498290">it</span> <span m="2498410">has</span> <span
  m="2498670">some</span> <span m="2499060">cos(2x)</span> <span
  m="2500480">in</span> <span m="2500640">it.</span></p><p><span
  m="2502330">And</span> <span m="2502560">a</span> <span m="2502580">--</span>
  <span m="2502860">and</span> <span m="2503140">some</span> <span
  m="2503360">sin(2x),</span> <span m="2504600">and</span> <span
  m="2504920">forever.</span></p><p><span m="2510780">So</span> <span
  m="2510970">what's</span> <span m="2511570">--</span> <span
  m="2511730">what's</span> <span m="2512100">the</span> <span
  m="2512210">difference</span> <span m="2512650">between</span> <span
  m="2513140">this</span> <span m="2513930">type</span> <span
  m="2514600">problem</span> <span m="2515100">and</span> <span
  m="2515210">the</span> <span m="2515290">one</span> <span
  m="2515490">above</span> <span m="2515760">it?</span></p><p><span
  m="2516900">This</span> <span m="2517150">one's</span> <span
  m="2517410">infinite,</span> <span m="2518860">but</span> <span
  m="2520570">the</span> <span m="2520990">key</span> <span
  m="2521330">property</span> <span m="2522090">of</span> <span
  m="2522420">things</span> <span m="2522870">being</span> <span
  m="2523140">orthogonal</span> <span m="2524790">is</span> <span
  m="2525740">still</span> <span m="2526110">true</span> <span
  m="2526520">for</span> <span m="2526730">sines</span> <span
  m="2527120">and</span> <span m="2527280">cosines,</span> <span
  m="2528300">so</span> <span m="2528750">it's</span> <span
  m="2529020">the</span> <span m="2529140">property</span> <span
  m="2529630">that</span> <span m="2529790">makes</span> <span
  m="2530110">Fourier</span> <span m="2530530">series</span> <span
  m="2530920">work.</span></p><p><span m="2531170">So</span> <span
  m="2531260">that's</span> <span m="2531510">called</span> <span
  m="2531770">a</span> <span m="2531820">Fourier</span> <span
  m="2532290">series.</span></p><p><span m="2532860">Better</span> <span
  m="2533070">write</span> <span m="2533350">his</span> <span
  m="2533570">name</span> <span m="2533860">up.</span></p><p><span
  m="2534620">Fourier</span> <span m="2535070">series.</span> <span
  m="2542170">So</span> <span m="2542520">it</span> <span m="2542650">was</span>
  <span m="2542900">Joseph</span> <span m="2543310">Fourier</span> <span
  m="2543790">who</span> <span m="2544040">realized</span> <span
  m="2544860">that,</span> <span m="2545010">hey,</span> <span
  m="2545640">I</span> <span m="2545960">could</span> <span
  m="2546570">work</span> <span m="2547050">in</span> <span
  m="2547330">function</span> <span m="2547820">space.</span></p><p><span
  m="2549870">Instead</span> <span m="2550240">of</span> <span
  m="2550330">a</span> <span m="2550400">vector</span> <span
  m="2550830">v,</span> <span m="2551180">I</span> <span
  m="2551260">could</span> <span m="2551430">have</span> <span
  m="2551590">a</span> <span m="2551650">function</span> <span
  m="2552140">f</span> <span m="2552290">of</span> <span
  m="2552430">x.</span></p><p><span m="2553970">Instead</span> <span
  m="2554390">of</span> <span m="2554480">orthogonal</span> <span
  m="2555570">vectors,</span> <span m="2556430">q1,</span> <span
  m="2557180">q2</span> <span m="2557470">,</span> <span m="2557710">q3,</span>
  <span m="2558590">I</span> <span m="2558920">could</span> <span
  m="2559160">have</span> <span m="2559440">orthogonal</span> <span
  m="2560140">functions,</span> <span m="2561110">the</span> <span
  m="2561410">constant,</span> <span m="2562180">the</span> <span
  m="2562290">cos(x),</span> <span m="2563240">the</span> <span
  m="2563350">sin(x),</span> <span m="2564440">the</span> <span
  m="2564760">s-</span> <span m="2564970">cos(2x),</span> <span
  m="2565370">but</span> <span m="2565720">infinitely</span> <span
  m="2566140">many</span> <span m="2566450">of</span> <span
  m="2566530">them.</span></p><p><span m="2567450">I</span> <span
  m="2567570">need</span> <span m="2567880">infinitely</span> <span
  m="2568330">many,</span> <span m="2568660">because</span> <span
  m="2569060">my</span> <span m="2569290">space</span> <span
  m="2569930">is</span> <span m="2570410">infinite</span> <span
  m="2570950">dimensional.</span></p><p><span m="2572440">So</span> <span
  m="2572610">this</span> <span m="2572790">is,</span> <span
  m="2572950">like,</span> <span m="2573210">the</span> <span
  m="2573320">moment</span> <span m="2573960">in</span> <span
  m="2574160">which</span> <span m="2575210">we</span> <span
  m="2575910">leave</span> <span m="2576470">finite</span> <span
  m="2576970">dimensional</span> <span m="2577500">vector</span> <span
  m="2577860">spaces</span> <span m="2578730">and</span> <span
  m="2579040">go</span> <span m="2579240">to</span> <span
  m="2579330">infinite</span> <span m="2579800">dimensional</span> <span
  m="2580240">vector</span> <span m="2580680">spaces</span> <span
  m="2581340">and</span> <span m="2581560">our</span> <span
  m="2581710">basis</span> <span m="2582550">--</span> <span
  m="2583090">so</span> <span m="2583290">the</span> <span
  m="2583640">vectors</span> <span m="2584470">are</span> <span
  m="2584710">now</span> <span m="2585120">functions</span> <span
  m="2585990">--</span> <span m="2587250">and</span> <span m="2587410">of</span>
  <span m="2587490">course,</span> <span m="2587780">there</span> <span
  m="2587800">are</span> <span m="2587900">so</span> <span
  m="2588090">many</span> <span m="2588410">functions</span> <span
  m="2588960">that</span> <span m="2589170">it's</span> <span
  m="2589530">--</span> <span m="2589650">that</span> <span
  m="2589830">we've</span> <span m="2590000">got</span> <span
  m="2590170">an</span> <span m="2590290">infin-</span> <span
  m="2590720">infinite</span> <span m="2591320">dimensional</span> <span
  m="2591840">space</span> <span m="2592500">--</span> <span
  m="2593620">and</span> <span m="2594070">the</span> <span
  m="2594150">basis</span> <span m="2595010">vectors</span> <span
  m="2595820">are</span> <span m="2596090">functions,</span> <span
  m="2596670">too.</span> <span m="2597320">a0,</span> <span
  m="2598080">the</span> <span m="2598230">constant</span> <span
  m="2598780">function</span> <span m="2599200">one</span> <span
  m="2599740">--</span> <span m="2599890">so</span> <span m="2600040">my</span>
  <span m="2600210">basis</span> <span m="2601290">is</span> <span
  m="2602070">one</span> <span m="2602800">cos(x),</span> <span
  m="2605400">sin(x),</span> <span m="2605680">cos(2x),</span> <span
  m="2605870">sin(2x)</span> <span m="2606140">and</span> <span
  m="2606330">so</span> <span m="2606550">on.</span></p><p><span
  m="2609190">And</span> <span m="2609640">the</span> <span
  m="2609780">reason</span> <span m="2610430">Fourier</span> <span
  m="2610950">series</span> <span m="2611500">is</span> <span
  m="2611670">a</span> <span m="2611780">success</span> <span
  m="2612710">is</span> <span m="2613210">that</span> <span
  m="2613420">those</span> <span m="2613720">are</span> <span
  m="2613820">orthogonal.</span></p><p><span m="2615170">Okay.</span> <span
  m="2615760">Now</span> <span m="2616010">what</span> <span
  m="2616170">do</span> <span m="2616260">I</span> <span m="2616350">mean</span>
  <span m="2616590">by</span> <span m="2616770">orthogonal?</span></p><p><span
  m="2620110">I</span> <span m="2620250">know</span> <span
  m="2620430">what</span> <span m="2620620">it</span> <span
  m="2620710">means</span> <span m="2620970">for</span> <span
  m="2621140">two</span> <span m="2621390">vectors</span> <span
  m="2621970">to</span> <span m="2622080">be</span> <span
  m="2622250">orthogonal</span> <span m="2623130">--</span> <span
  m="2624490">y</span> <span m="2624750">transpose</span> <span
  m="2625330">x</span> <span m="2625570">equals</span> <span
  m="2625900">zero,</span> <span m="2626180">right?</span></p><p><span
  m="2626870">Dot</span> <span m="2627120">product</span> <span
  m="2627520">equals</span> <span m="2627850">zero.</span></p><p><span
  m="2628600">But</span> <span m="2628840">what's</span> <span
  m="2629200">the</span> <span m="2629330">dot</span> <span
  m="2629640">product</span> <span m="2630100">of</span> <span
  m="2630210">functions?</span></p><p><span m="2632070">I'm</span> <span
  m="2632310">claiming</span> <span m="2632850">that</span> <span
  m="2633040">whatever</span> <span m="2633540">it</span> <span
  m="2633610">is,</span> <span m="2634290">the</span> <span
  m="2634510">dot</span> <span m="2634830">product</span> <span
  m="2635320">--</span> <span m="2635340">or</span> <span m="2635440">we</span>
  <span m="2635620">would</span> <span m="2636200">more</span> <span
  m="2636740">likely</span> <span m="2637160">use</span> <span
  m="2637470">the</span> <span m="2637570">word</span> <span
  m="2637920">inner</span> <span m="2638220">product</span> <span
  m="2638930">of,</span> <span m="2639520">say,</span> <span
  m="2639840">cos(x)</span> <span m="2640550">with</span> <span
  m="2640740">sin(x)</span> <span m="2641450">is</span> <span
  m="2641690">zero.</span></p><p><span m="2642430">And</span> <span
  m="2642640">cos(x)</span> <span m="2643280">with</span> <span
  m="2643500">cos(2x),</span> <span m="2644380">also</span> <span
  m="2644750">zero.</span></p><p><span m="2646340">So</span> <span
  m="2646740">I</span> <span m="2646870">--</span> <span m="2647010">let</span>
  <span m="2647160">me</span> <span m="2647290">tell</span> <span
  m="2647460">you</span> <span m="2647580">what</span> <span
  m="2647740">I</span> <span m="2647810">mean</span> <span m="2648170">by</span>
  <span m="2648380">that,</span> <span m="2648780">by</span> <span
  m="2649370">that</span> <span m="2649630">dot</span> <span
  m="2649860">product.</span></p><p><span m="2650410">Well,</span> <span
  m="2650730">how</span> <span m="2650930">do</span> <span m="2651050">I</span>
  <span m="2651130">compute</span> <span m="2651550">a</span> <span
  m="2651650">dot</span> <span m="2651900">product?</span></p><p><span
  m="2652850">So,</span> <span m="2653340">let's</span> <span
  m="2653650">just</span> <span m="2653860">remember</span> <span
  m="2654590">for</span> <span m="2654750">vectors</span> <span
  m="2655730">v</span> <span m="2656360">trans-</span> <span
  m="2656970">v</span> <span m="2657240">transpose</span> <span
  m="2657910">w</span> <span m="2659170">for</span> <span
  m="2660080">vectors,</span> <span m="2660650">so</span> <span
  m="2661020">this</span> <span m="2661210">was</span> <span
  m="2661370">vectors,</span> <span m="2663050">v</span> <span
  m="2664160">transpose</span> <span m="2664740">w</span> <span
  m="2665160">was</span> <span m="2665650">v1w1</span> <span
  m="2669820">+...+vnwn.</span> <span m="2673510">Okay.</span></p><p><span
  m="2674140">Now</span> <span m="2674350">functions.</span></p><p><span
  m="2680100">Now</span> <span m="2680340">I</span> <span
  m="2680460">have</span> <span m="2680680">two</span> <span
  m="2680860">functions,</span> <span m="2681410">let's</span> <span
  m="2681660">call</span> <span m="2681870">them</span> <span
  m="2682030">f</span> <span m="2682180">and</span> <span
  m="2682350">g.</span></p><p><span m="2685260">What's</span> <span
  m="2685910">with</span> <span m="2686090">them</span> <span
  m="2686380">now?</span></p><p><span m="2686700">The</span> <span
  m="2686830">vectors</span> <span m="2687420">had</span> <span
  m="2687720">n</span> <span m="2687970">components,</span> <span
  m="2688560">but</span> <span m="2688690">the</span> <span
  m="2688810">functions</span> <span m="2689730">have</span> <span
  m="2690160">a</span> <span m="2690250">whole,</span> <span
  m="2690890">like,</span> <span m="2691410">continuum.</span> <span
  m="2693060">To</span> <span m="2693220">graph</span> <span
  m="2693620">the</span> <span m="2693740">function,</span> <span
  m="2694160">I</span> <span m="2694250">just</span> <span
  m="2694530">don't</span> <span m="2694790">have</span> <span
  m="2694990">n</span> <span m="2695280">points,</span> <span
  m="2695640">I've</span> <span m="2695780">got</span> <span
  m="2695990">this</span> <span m="2696170">whole</span> <span
  m="2696540">graph.</span></p><p><span m="2697780">So</span> <span
  m="2697910">I</span> <span m="2698020">have</span> <span
  m="2698160">functions</span> <span m="2698940">--</span> <span
  m="2699780">I'm</span> <span m="2700010">really</span> <span
  m="2700330">trying</span> <span m="2700630">to</span> <span
  m="2700690">ask</span> <span m="2701040">you</span> <span
  m="2701150">what's</span> <span m="2701590">the</span> <span
  m="2701800">inner</span> <span m="2702100">product</span> <span
  m="2702650">of</span> <span m="2702840">this</span> <span
  m="2703360">function</span> <span m="2703840">f</span> <span
  m="2704170">with</span> <span m="2704330">another</span> <span
  m="2704680">function</span></p><p><span m="2705170">g?</span> <span
  m="2706130">And</span> <span m="2706880">I</span> <span
  m="2706910">want</span> <span m="2707120">to</span> <span
  m="2707190">make</span> <span m="2707450">it</span> <span
  m="2708100">parallel</span> <span m="2708980">to</span> <span
  m="2709090">this</span> <span m="2709630">the</span> <span
  m="2709730">best</span> <span m="2710050">I</span> <span
  m="2710130">can.</span></p><p><span m="2711870">So</span> <span
  m="2712480">the</span> <span m="2713090">best</span> <span
  m="2713580">parallel</span> <span m="2714280">is</span> <span
  m="2714530">to</span> <span m="2714660">multiply</span> <span
  m="2716160">f</span> <span m="2716890">(x)</span> <span
  m="2717960">times</span> <span m="2718730">g(x)</span> <span
  m="2720080">at</span> <span m="2720640">every</span> <span
  m="2720980">x</span> <span m="2721910">--</span> <span m="2723060">and</span>
  <span m="2723250">here</span> <span m="2723520">I</span> <span
  m="2723600">just</span> <span m="2723830">had</span> <span
  m="2723990">n</span> <span m="2724300">multiplications,</span> <span
  m="2725120">but</span> <span m="2725270">here</span> <span
  m="2725520">I'm</span> <span m="2725600">going</span> <span
  m="2725770">to</span> <span m="2725840">have</span> <span m="2726110">a</span>
  <span m="2726240">whole</span> <span m="2726520">range</span> <span
  m="2726880">of</span> <span m="2726990">x-s,</span> <span
  m="2728330">and</span> <span m="2729890">here</span> <span
  m="2730350">I</span> <span m="2730480">added</span> <span
  m="2730970">the</span> <span m="2731060">results.</span></p><p><span
  m="2731980">What</span> <span m="2732220">do</span> <span m="2732310">I</span>
  <span m="2732430">do</span> <span m="2732660">here?</span></p><p><span
  m="2734600">So</span> <span m="2734780">what's</span> <span
  m="2735100">the</span> <span m="2735290">analog</span> <span
  m="2736000">of</span> <span m="2736160">addition</span> <span
  m="2737330">when</span> <span m="2737890">you</span> <span
  m="2737980">have</span> <span m="2738380">--</span> <span
  m="2738400">when</span> <span m="2738540">you're</span> <span
  m="2738700">in</span> <span m="2738790">a</span> <span
  m="2738860">continuum?</span></p><p><span m="2740350">It's</span> <span
  m="2740610">integration.</span></p><p><span m="2741830">So</span> <span
  m="2742180">that</span> <span m="2742700">the</span> <span
  m="2743310">--</span> <span m="2743710">the</span> <span
  m="2744070">dot</span> <span m="2744350">product</span> <span
  m="2744780">of</span> <span m="2744890">two</span> <span
  m="2745110">functions</span> <span m="2746370">will</span> <span
  m="2747020">be</span> <span m="2747630">the</span> <span
  m="2747820">integral</span> <span m="2748260">of</span> <span
  m="2748360">those</span> <span m="2748640">functions,</span> <span
  m="2749170">dx.</span> <span m="2752240">Now</span> <span m="2752530">I</span>
  <span m="2752670">have</span> <span m="2752850">to</span> <span
  m="2752990">say</span> <span m="2753310">--</span> <span
  m="2753330">say,</span> <span m="2753900">well,</span> <span
  m="2754220">what</span> <span m="2754390">are</span> <span
  m="2754480">the</span> <span m="2754630">limits</span> <span
  m="2755010">of</span> <span m="2755130">integration?</span></p><p><span
  m="2756800">And</span> <span m="2757310">for</span> <span
  m="2757490">this</span> <span m="2758430">Fourier</span> <span
  m="2759190">series,</span> <span m="2760510">this</span> <span
  m="2761670">function</span> <span m="2762390">f(x)</span> <span
  m="2762740">--</span> <span m="2763980">if</span> <span m="2764950">I'm</span>
  <span m="2765100">going</span> <span m="2765240">to</span> <span
  m="2765300">have</span> <span m="2765910">--</span> <span
  m="2766190">if</span> <span m="2766350">that</span> <span
  m="2766540">right</span> <span m="2766770">hand</span> <span
  m="2767020">side</span> <span m="2767360">is</span> <span
  m="2767520">going</span> <span m="2767680">to</span> <span
  m="2767750">be</span> <span m="2768000">f(x),</span> <span
  m="2769230">that</span> <span m="2770140">function</span> <span
  m="2770740">that</span> <span m="2770910">I'm</span> <span
  m="2771070">seeing</span> <span m="2771390">on</span> <span
  m="2771490">the</span> <span m="2771570">right,</span> <span
  m="2771920">all</span> <span m="2772100">those</span> <span
  m="2772390">sines</span> <span m="2772870">and</span> <span
  m="2773030">cosines,</span> <span m="2773590">they're</span> <span
  m="2773790">all</span> <span m="2774010">periodic,</span> <span
  m="2775190">with</span> <span m="2775800">--</span> <span
  m="2776130">with</span> <span m="2776380">period</span> <span
  m="2776810">two</span> <span m="2776990">pi.</span></p><p><span
  m="2778210">So</span> <span m="2778760">--</span> <span m="2779060">so</span>
  <span m="2779290">that's</span> <span m="2779580">what</span> <span
  m="2779740">f(x)</span> <span m="2780280">had</span> <span
  m="2780400">better</span> <span m="2780680">be.</span></p><p><span
  m="2781650">So</span> <span m="2781890">I'll</span> <span
  m="2782120">integrate</span> <span m="2782700">from</span> <span
  m="2782870">zero</span> <span m="2783210">to</span> <span
  m="2783360">two</span> <span m="2783530">pi.</span></p><p><span
  m="2784870">My</span> <span m="2785060">--</span> <span m="2785100">all</span>
  <span m="2785300">--</span> <span m="2785330">everything</span> <span
  m="2785950">--</span> <span m="2786330">is</span> <span m="2786670">on</span>
  <span m="2786850">the</span> <span m="2786960">interval</span> <span
  m="2787340">zero</span> <span m="2787650">two</span> <span
  m="2787870">pi</span> <span m="2788180">now,</span> <span
  m="2789160">because</span> <span m="2790640">if</span> <span
  m="2791000">I'm</span> <span m="2791140">going</span> <span
  m="2791320">to</span> <span m="2791370">use</span> <span
  m="2791710">these</span> <span m="2792180">sines</span> <span
  m="2792570">and</span> <span m="2792730">cosines,</span> <span
  m="2793690">then</span> <span m="2794680">f(x)</span> <span
  m="2796310">is</span> <span m="2796890">equal</span> <span
  m="2797270">to</span> <span m="2797370">f(x+2pi).</span> <span
  m="2799950">This</span> <span m="2801100">is</span> <span
  m="2801360">periodic</span> <span m="2801970">--</span> <span
  m="2805180">periodic</span> <span m="2805860">functions.</span></p><p><span
  m="2808250">Okay.</span></p><p><span m="2809800">So</span> <span
  m="2810000">now</span> <span m="2810260">I</span> <span
  m="2810380">know</span> <span m="2810640">what</span> <span
  m="2811820">--</span> <span m="2812770">I've</span> <span
  m="2812920">got</span> <span m="2813110">all</span> <span
  m="2813300">the</span> <span m="2813390">right</span> <span
  m="2813950">words</span> <span m="2814580">now.</span></p><p><span
  m="2816120">I've</span> <span m="2816300">got</span> <span
  m="2816490">a</span> <span m="2816530">vector</span> <span
  m="2816970">space,</span> <span m="2817730">but</span> <span
  m="2817920">the</span> <span m="2818010">vectors</span> <span
  m="2818450">are</span> <span m="2818550">functions.</span></p><p><span
  m="2820490">I've</span> <span m="2820760">got</span> <span
  m="2821740">inner</span> <span m="2822410">products</span> <span
  m="2823610">and</span> <span m="2824370">--</span> <span
  m="2824400">and</span> <span m="2824590">the</span> <span
  m="2824690">inner</span> <span m="2824860">product</span> <span
  m="2825230">gives</span> <span m="2825450">a</span> <span
  m="2825540">number,</span> <span m="2825950">all</span> <span
  m="2826070">right.</span></p><p><span m="2827760">It</span> <span
  m="2827950">just</span> <span m="2828170">happens</span> <span
  m="2828510">to</span> <span m="2828620">be</span> <span m="2828750">an</span>
  <span m="2828880">integral</span> <span m="2829420">instead</span> <span
  m="2829830">of</span> <span m="2829970">a</span> <span
  m="2830060">sum.</span></p><p><span m="2832260">I've</span> <span
  m="2832530">got</span> <span m="2832910">--</span> <span
  m="2833070">and</span> <span m="2833180">that</span> <span
  m="2833190">--</span> <span m="2833210">then</span> <span m="2833340">I</span>
  <span m="2833410">have</span> <span m="2833590">the</span> <span
  m="2833730">idea</span> <span m="2834030">of</span> <span
  m="2834110">orthogonality</span> <span m="2835230">--</span> <span
  m="2835860">because,</span> <span m="2836380">actually,</span> <span
  m="2837200">just</span> <span m="2837560">--</span> <span
  m="2837580">let's</span> <span m="2837820">just</span> <span
  m="2838060">check.</span></p><p><span m="2838470">Orthogonality</span> <span
  m="2839780">--</span> <span m="2839810">if</span> <span m="2840020">I</span>
  <span m="2840150">take</span> <span m="2840550">the</span> <span
  m="2840680">integral</span> <span m="2841450">--</span> <span
  m="2841480">s-</span> <span m="2841640">I</span> <span m="2841890">--</span>
  <span m="2841910">let</span> <span m="2842280">me</span> <span
  m="2842400">do</span> <span m="2842590">sin(x)</span> <span
  m="2843310">times</span> <span m="2843670">cos(x)</span> <span
  m="2845040">--</span> <span m="2845890">sin(x)</span> <span
  m="2846240">times</span> <span m="2846620">cos(x)</span> <span
  m="2848410">dx</span> <span m="2849120">from</span> <span
  m="2849510">zero</span> <span m="2849800">to</span> <span
  m="2849950">two</span> <span m="2850140">pi</span> <span m="2850660">--</span>
  <span m="2854680">I</span> <span m="2854840">think</span> <span
  m="2855090">we</span> <span m="2855200">get</span> <span
  m="2855420">zero.</span></p><p><span m="2856700">That's</span> <span
  m="2857110">the</span> <span m="2857250">differential</span> <span
  m="2857880">of</span> <span m="2858010">that,</span> <span
  m="2858390">so</span> <span m="2858610">it</span> <span
  m="2858700">would</span> <span m="2858960">be</span> <span
  m="2859290">one</span> <span m="2859660">half</span> <span
  m="2860670">sine</span> <span m="2861370">x</span> <span
  m="2861670">squared,</span> <span m="2862200">was</span> <span
  m="2862310">that</span> <span m="2862470">right?</span></p><p><span
  m="2867220">Between</span> <span m="2867700">zero</span> <span
  m="2868080">and</span> <span m="2868200">two</span> <span
  m="2868370">pi</span> <span m="2868800">--</span> <span
  m="2870100">and,</span> <span m="2870470">of</span> <span
  m="2870580">course,</span> <span m="2871130">we</span> <span
  m="2871260">get</span> <span m="2871460">zero.</span></p><p><span
  m="2872910">And</span> <span m="2873430">the</span> <span
  m="2873620">same</span> <span m="2873910">would</span> <span
  m="2874050">be</span> <span m="2874220">true</span> <span
  m="2875350">with</span> <span m="2875980">a</span> <span
  m="2876050">little</span> <span m="2876340">more</span> <span
  m="2876960">--</span> <span m="2878150">some</span> <span
  m="2878400">trig</span> <span m="2878780">identities</span> <span
  m="2879390">to</span> <span m="2879520">help</span> <span
  m="2879760">us</span> <span m="2879930">out</span> <span m="2880310">--</span>
  <span m="2880520">of</span> <span m="2880700">every</span> <span
  m="2881030">other</span> <span m="2881280">pair.</span></p><p><span
  m="2882430">So</span> <span m="2882660">we</span> <span
  m="2882850">have</span> <span m="2883570">now</span> <span
  m="2884170">an</span> <span m="2884340">orthonormal</span> <span
  m="2885140">infinite</span> <span m="2885650">basis</span> <span
  m="2886590">for</span> <span m="2886960">function</span> <span
  m="2887450">space,</span> <span m="2888560">and</span> <span
  m="2889200">all</span> <span m="2889400">we</span> <span
  m="2889530">want</span> <span m="2889760">to</span> <span
  m="2889840">do</span> <span m="2890160">is</span> <span
  m="2890500">express</span> <span m="2891100">a</span> <span
  m="2891190">function</span> <span m="2892280">in</span> <span
  m="2892790">that</span></p><p><span m="2892980">basis.</span> <span
  m="2894090">And</span> <span m="2895030">so</span> <span m="2895390">I</span>
  <span m="2895580">--</span> <span m="2895630">the</span> <span
  m="2895760">end</span> <span m="2896000">of</span> <span m="2896040">my</span>
  <span m="2896210">lecture</span> <span m="2896650">is,</span> <span
  m="2896930">okay,</span> <span m="2898020">what</span> <span
  m="2898510">is</span> <span m="2898720">a1?</span> <span
  m="2900120">What's</span> <span m="2901360">the</span> <span
  m="2901520">coefficient</span> <span m="2902240">--</span> <span
  m="2902260">how</span> <span m="2902440">much</span> <span
  m="2902820">cos(x)</span> <span m="2903700">is</span> <span
  m="2903970">there</span> <span m="2904210">in</span> <span
  m="2904320">a</span> <span m="2904380">function</span> <span
  m="2905840">compared</span> <span m="2907420">to</span> <span
  m="2907800">the</span> <span m="2907960">other</span> <span
  m="2908150">harmonics?</span></p><p><span m="2910230">How</span> <span
  m="2910500">much</span> <span m="2911180">constant</span> <span
  m="2911980">is</span> <span m="2912120">in</span> <span
  m="2912250">that</span> <span m="2912490">function?</span></p><p><span
  m="2912940">That'll</span> <span m="2913220">--</span> <span
  m="2913390">that</span> <span m="2913670">would</span> <span
  m="2913990">be</span> <span m="2914190">an</span> <span
  m="2914300">easy</span> <span m="2914610">question.</span></p><p><span
  m="2915310">The</span> <span m="2915440">answer</span> <span
  m="2915800">a0</span> <span m="2916220">will</span> <span
  m="2916440">come</span> <span m="2916680">out</span> <span
  m="2916870">to</span> <span m="2916950">be</span> <span m="2917120">the</span>
  <span m="2917290">average</span> <span m="2917770">value</span> <span
  m="2918180">of</span> <span m="2918340">f.</span></p><p><span
  m="2919110">That's</span> <span m="2919390">the</span> <span
  m="2919520">amount</span> <span m="2919860">of</span> <span
  m="2919960">the</span> <span m="2920080">constant</span> <span
  m="2920620">that's</span> <span m="2920840">in</span> <span
  m="2921010">there,</span> <span m="2921280">its</span> <span
  m="2921430">average</span> <span m="2921840">value.</span></p><p><span
  m="2922630">But</span> <span m="2922820">let's</span> <span
  m="2923100">take</span> <span m="2923390">a1</span> <span
  m="2923910">as</span> <span m="2924060">more</span> <span
  m="2924290">typical.</span></p><p><span m="2925350">How</span> <span
  m="2925700">will</span> <span m="2925940">I</span> <span
  m="2926050">get</span> <span m="2926330">--</span> <span
  m="2926350">here's</span> <span m="2926650">the</span> <span
  m="2926840">end</span> <span m="2927130">of</span> <span
  m="2927190">the</span> <span m="2927320">lecture,</span> <span
  m="2927680">then</span> <span m="2928030">--</span> <span
  m="2928170">how</span> <span m="2928440">do</span> <span m="2928590">I</span>
  <span m="2928700">get</span> <span m="2929040">a1?</span> <span
  m="2932070">The</span> <span m="2932210">first</span> <span
  m="2932690">Fourier</span> <span m="2933150">coefficient.</span></p><p><span
  m="2934720">Okay.</span></p><p><span m="2936350">I</span> <span
  m="2936510">do</span> <span m="2936880">just</span> <span
  m="2937180">as</span> <span m="2937320">I</span> <span m="2937430">did</span>
  <span m="2937640">in</span> <span m="2937740">the</span> <span
  m="2937830">vector</span> <span m="2938220">case.</span> <span
  m="2939790">I</span> <span m="2940020">take</span> <span
  m="2940340">the</span> <span m="2940470">inner</span> <span
  m="2940690">product</span> <span m="2941160">of</span> <span
  m="2941270">everything</span> <span m="2941940">with</span> <span
  m="2942170">cos(x)</span> <span m="2943850">Take</span> <span
  m="2944960">the</span> <span m="2945080">inner</span> <span
  m="2945290">product</span> <span m="2945660">of</span> <span
  m="2945750">everything</span> <span m="2946210">with</span> <span
  m="2946370">cos(x).</span> <span m="2947010">Then</span> <span
  m="2947210">on</span> <span m="2947350">the</span> <span
  m="2947460">left</span> <span m="2948060">--</span> <span
  m="2948800">on</span> <span m="2948940">the</span> <span
  m="2949040">left</span> <span m="2949480">I</span> <span
  m="2949640">have</span> <span m="2949890">--</span> <span
  m="2949910">the</span> <span m="2950000">inner</span> <span
  m="2950210">product</span> <span m="2950700">is</span> <span
  m="2950970">the</span> <span m="2951100">integral</span> <span
  m="2952360">of</span> <span m="2953590">f(x)</span> <span
  m="2953990">times</span> <span m="2954420">cos(x)</span> <span
  m="2955060">cx.</span> <span m="2958740">And</span> <span
  m="2959030">on</span> <span m="2959170">the</span> <span
  m="2959260">right,</span> <span m="2959820">what</span> <span
  m="2960090">do</span> <span m="2960180">I</span> <span
  m="2960290">have?</span></p><p><span m="2962080">When</span> <span
  m="2962320">I</span> <span m="2962560">--</span> <span m="2962670">so</span>
  <span m="2962820">what</span> <span m="2962990">I</span> <span
  m="2963150">--</span> <span m="2963170">when</span> <span m="2963400">I</span>
  <span m="2963490">say</span> <span m="2963740">take</span> <span
  m="2964060">the</span> <span m="2964190">inner</span> <span
  m="2964410">product</span> <span m="2964790">with</span> <span
  m="2964970">cos(x),</span> <span m="2965710">let</span> <span
  m="2965820">me</span> <span m="2965960">put</span> <span m="2966200">it</span>
  <span m="2966350">in</span> <span m="2966730">ordinary</span> <span
  m="2967330">calculus</span> <span m="2967940">words.</span></p><p><span
  m="2968850">Multiply</span> <span m="2969620">by</span> <span
  m="2969830">cos(x)</span> <span m="2970770">and</span> <span
  m="2970930">integrate.</span></p><p><span m="2972610">That's</span> <span
  m="2972880">what</span> <span m="2973070">inner</span> <span
  m="2973270">products</span> <span m="2973700">are.</span></p><p><span
  m="2974540">So</span> <span m="2974750">if</span> <span m="2974840">I</span>
  <span m="2974920">multiply</span> <span m="2975440">that</span> <span
  m="2975620">whole</span> <span m="2975830">thing</span> <span
  m="2976020">by</span> <span m="2976190">cos(x)</span> <span
  m="2976940">and</span> <span m="2977110">I</span> <span
  m="2977190">integrate,</span> <span m="2978110">I</span> <span
  m="2978480">get</span> <span m="2978790">a</span> <span
  m="2978890">whole</span> <span m="2979330">lot</span> <span
  m="2979620">of</span> <span m="2979670">zeroes.</span> <span
  m="2980990">The</span> <span m="2981670">only</span> <span
  m="2982090">thing</span> <span m="2982340">that</span> <span
  m="2982560">survives</span> <span m="2983260">is</span> <span
  m="2983430">that</span> <span m="2983750">term.</span></p><p><span
  m="2985830">All</span> <span m="2986060">the</span> <span
  m="2986210">others</span> <span m="2986520">disappear.</span></p><p><span
  m="2987250">So</span> <span m="2987540">--</span> <span m="2987610">and</span>
  <span m="2987770">that</span> <span m="2988050">term</span> <span
  m="2988460">is</span> <span m="2988780">a1</span> <span
  m="2989760">times</span> <span m="2990240">the</span> <span
  m="2990360">integral</span> <span m="2990820">of</span> <span
  m="2991000">cos(x)</span> <span m="2992310">squared</span> <span
  m="2993950">dx</span> <span m="2994950">zero</span> <span
  m="2995470">to</span> <span m="2995590">2pi</span> <span
  m="2997140">equals</span> <span m="2999260">--</span> <span
  m="2999750">so</span> <span m="2999950">this</span> <span
  m="3000180">was</span> <span m="3000320">the</span> <span
  m="3000430">left</span> <span m="3000770">side</span> <span
  m="3001150">and</span> <span m="3001270">this</span> <span
  m="3001440">is</span> <span m="3001580">all</span> <span
  m="3001790">that's</span> <span m="3002000">left</span> <span
  m="3002310">on</span> <span m="3002430">the</span> <span
  m="3002510">right-hand</span> <span m="3003000">side.</span></p><p><span
  m="3004840">And</span> <span m="3005770">this</span> <span
  m="3006410">is</span> <span m="3006870">not</span> <span
  m="3007190">zero</span> <span m="3007540">of</span> <span
  m="3007630">course,</span> <span m="3008080">because</span> <span
  m="3008310">it's</span> <span m="3008860">the</span> <span
  m="3009140">length</span> <span m="3009700">of</span> <span
  m="3009880">the</span> <span m="3010010">function</span> <span
  m="3010730">squared,</span> <span m="3011640">it's</span> <span
  m="3011900">the</span> <span m="3012000">inner</span> <span
  m="3012180">product</span> <span m="3012530">with</span> <span
  m="3012760">itself,</span> <span m="3013570">and</span> <span
  m="3014020">--</span> <span m="3014220">and</span> <span m="3014450">a</span>
  <span m="3014530">simple</span> <span m="3014980">calculation</span> <span
  m="3016030">gives</span> <span m="3016490">that</span> <span
  m="3016740">answer</span> <span m="3017170">to</span> <span
  m="3017280">be</span> <span m="3017550">pi.</span></p><p><span
  m="3018050">So</span> <span m="3020400">that's</span> <span
  m="3020710">an</span> <span m="3020850">easy</span> <span
  m="3021220">integral</span> <span m="3021770">and</span> <span
  m="3021900">it</span> <span m="3022010">turns</span> <span
  m="3022280">out</span> <span m="3022480">to</span> <span m="3022540">be</span>
  <span m="3022730">pi,</span> <span m="3023360">so</span> <span
  m="3023740">that</span> <span m="3023950">a1</span> <span
  m="3024770">is</span> <span m="3025360">one</span> <span
  m="3025900">over</span> <span m="3026200">pi</span> <span
  m="3026980">times</span> <span m="3027520">there</span> <span
  m="3027950">--</span> <span m="3027980">times</span> <span
  m="3028330">this</span> <span m="3029010">integral.</span></p><p><span
  m="3031900">So</span> <span m="3032120">there</span> <span
  m="3032550">is,</span> <span m="3032780">actually</span> <span
  m="3033280">--</span> <span m="3033300">that's</span> <span
  m="3033570">Euler's</span> <span m="3034130">famous</span> <span
  m="3034610">formula</span> <span m="3035490">for</span> <span
  m="3036090">the</span> <span m="3036590">--</span> <span m="3036620">or</span>
  <span m="3036770">maybe</span> <span m="3037130">Fourier</span> <span
  m="3037640">found</span> <span m="3037940">it</span> <span
  m="3038560">--</span> <span m="3039110">for</span> <span
  m="3039420">the</span> <span m="3039630">coefficients</span> <span
  m="3040500">in</span> <span m="3040650">a</span> <span
  m="3040710">Fourier</span> <span m="3041110">series.</span></p><p><span
  m="3043980">And</span> <span m="3044270">you</span> <span
  m="3044410">see</span> <span m="3044910">that</span> <span
  m="3045120">it's</span> <span m="3045360">exactly</span> <span
  m="3046760">an</span> <span m="3046960">expansion</span> <span
  m="3047940">in</span> <span m="3048180">an</span> <span
  m="3048310">orthonormal</span> <span m="3048960">basis.</span></p><p><span
  m="3050790">Okay,</span> <span m="3051100">thanks.</span></p><p><span
  m="3051540">So</span> <span m="3051710">I'll</span> <span
  m="3051850">do</span> <span m="3052030">a</span> <span m="3052150">quiz</span>
  <span m="3052490">review</span> <span m="3053240">on</span> <span
  m="3053660">Monday</span> <span m="3054660">and</span> <span
  m="3055390">then</span> <span m="3055620">the</span> <span
  m="3055740">quiz</span> <span m="3056040">itself</span> <span
  m="3056660">in</span> <span m="3056860">Walker</span> <span
  m="3057580">on</span> <span m="3058140">Wednesday.</span></p><p><span
  m="3059200">Okay,</span> <span m="3059520">see</span> <span
  m="3059740">you</span> <span m="3059840">Monday.</span></p><p><span
  m="3060590">Thanks.</span></p>
embedded_media:
  - uid: e5f2b96d7ab78c048157bd74c8add5f7
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: 18.06_L24.jpg
    title: 18.06_L24.jpg
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/18-06-linear-algebra-spring-2010/e5f2b96d7ab78c048157bd74c8add5f7_18.06_L24.jpg
  - uid: 5e5df2444c2016e7d092a5e7608e9b45
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: lGGDIGizcQ0
  - uid: edc700fed598d3a9db871c21baa42157
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: 'https://itunes.apple.com/us/itunes-u/id354869137'
  - uid: cedb5f2cce695c110220eae88dc44385
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: 'http://www.archive.org/download/MIT18.06S05_MP4/24.mp4'
  - uid: 71c0d4e5040487e1e04c80291ad7ef21
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Video-VideoLecturesnet-Stream
    title: Video-VideoLectures.net-Stream
    type: Video
    media_location: 'http://videolectures.net/mit1806s05_linear_algebra/'
  - uid: db3cbe72a15f0aa2a950d8044f6ce7f5
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Thumbnail-OCW-JPG
    title: Thumbnail-OCW-JPG
    type: Thumbnail
  - uid: c0d6547947c89b6b51a7fecc0824ea23
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/lGGDIGizcQ0/default.jpg'
  - uid: 1456ae2121008739ada9a2aeda6e999c
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: lGGDIGizcQ0
  - uid: 82cfb3a5759673fdd3ad2c0a9bdc8880
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: lGGDIGizcQ0.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/18-06-linear-algebra-spring-2010/82cfb3a5759673fdd3ad2c0a9bdc8880_lGGDIGizcQ0.srt
  - uid: a77a2a3a8c01d73741727acb73bffb69
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: lGGDIGizcQ0.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/18-06-linear-algebra-spring-2010/a77a2a3a8c01d73741727acb73bffb69_lGGDIGizcQ0.pdf
  - uid: e2c6594c523bf76777bbf2933d4b1c64
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 9db287b4e3b327816b2bd88225927683
    parent_uid: f7be9e0b3fedac90071a0f982ac10293
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
course_id: 18-06-linear-algebra-spring-2010
type: course
layout: video
---