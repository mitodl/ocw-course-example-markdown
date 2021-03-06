---
order_index: null
title: Comparisons
template_type: Embed
uid: 65aaf4468cd399bbe70987a4b31ced35
parent_uid: 666db218db6d8103cdcf41e2960132be
technical_location: >-
  https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/in-class-questions-and-video-solutions/lecture-2/comparisons
short_url: comparisons
inline_embed_id: 21302523comparisons56781227
about_this_resource_text: >-
  <p><strong>Description:</strong> This in-class exercise demonstrates how
  conditionals and comparisons work in Python.</p>
  <p><strong>Instructor:</strong> Dr. Ana Bell</p>
related_resources_text: ''
transcript: >-
  <p><span m="790">The</span> <span m="880">following</span> <span
  m="1300">content</span> <span m="1870">is</span> <span
  m="1990">provided</span> <span m="2440">under</span> <span m="2710">a</span>
  <span m="2770">Creative</span> <span m="3190">Commons</span> <span
  m="3580">license.</span> <span m="4730">Your</span> <span
  m="4870">support</span> <span m="5380">will</span> <span m="5530">help</span>
  <span m="5770">MIT</span> <span m="6220">OpenCourseWare</span> <span
  m="7030">continue</span> <span m="7540">to</span> <span m="7630">offer</span>
  <span m="8050">high-quality</span> <span m="8770">educational</span> <span
  m="9400">resources</span> <span m="10030">for</span> <span
  m="10210">free.</span> <span m="11390">To</span> <span m="11410">make</span>
  <span m="11620">a</span> <span m="11650">donation</span> <span
  m="12370">or</span> <span m="12610">view</span> <span
  m="13060">additional</span> <span m="13480">materials</span> <span
  m="13990">from</span> <span m="14200">hundreds</span> <span
  m="14590">of</span> <span m="14710">MIT</span> <span m="15130">courses,</span>
  <span m="16219">visit</span> <span m="16450">MIT</span> <span
  m="16870">OpenCourseWare</span> <span m="17880">at</span> <span
  m="18010">ocw.mit.edu.</span></p><p><span m="22690">ANA BELL:</span> <span
  m="22885">So</span> <span m="24070">I'm</span> <span m="24220">creating</span>
  <span m="24610">a</span> <span m="24670">variable</span> <span
  m="25270">called</span> <span m="26265">pset_time</span> <span
  m="27340">and</span> <span m="27430">I'm</span> <span
  m="27580">assigning</span> <span m="27970">it</span> <span m="28060">to</span>
  <span m="28210">be</span> <span m="28330">the</span> <span
  m="28450">value</span> <span m="28960">15.</span> <span m="30340">I'm</span>
  <span m="30430">creating</span> <span m="30760">a</span> <span
  m="30820">variable</span> <span m="31630">named</span> <span
  m="31870">sleep_time.</span> <span m="32560">I'm</span> <span
  m="32800">assigning</span> <span m="33220">it</span> <span m="33310">to</span>
  <span m="33460">be</span> <span m="33550">the</span> <span
  m="33670">value</span> <span m="34420">8.</span> <span m="36700">I'm</span>
  <span m="36850">going</span> <span m="37000">to</span> <span
  m="37090">print</span> <span m="37420">the</span> <span m="37570">value</span>
  <span m="38170">of</span> <span m="39730">this</span> <span
  m="40480">expression</span> <span m="41110">here.</span> <span
  m="42050">And</span> <span m="42170">the</span> <span m="42290">expression
  is</span> <span m="42750">a</span> <span m="42820">conditional</span> <span
  m="43450">that</span> <span m="43600">says,</span> <span m="44640">is</span>
  <span m="44800">sleep_time</span> <span m="45430">greater</span> <span
  m="45700">than</span> <span m="45850">pset_time?</span></p><p><span
  m="47230">So</span> <span m="47380">in</span> <span m="47470">Python,</span>
  <span m="47860">you're</span> <span m="47950">just</span> <span
  m="48100">going</span> <span m="48280">to</span> <span
  m="48340">replace</span> <span m="48730">these</span> <span
  m="50320">variables</span> <span m="50830">with</span> <span
  m="50980">their</span> <span m="51130">values.</span> <span
  m="52000">So</span> <span m="52180">is</span> <span m="52440">8</span> <span
  m="53800">greater</span> <span m="54100">than</span> <span
  m="54280">15?</span> <span m="55510">And</span> <span m="55630">that's</span>
  <span m="55810">false,</span> <span m="56530">so</span> <span
  m="57580">perfect.</span> <span m="59380">And</span> <span
  m="59530">then</span> <span m="62590">one</span> <span
  m="62800">operation</span> <span m="63220">on</span> <span
  m="63640">Booleans</span> <span m="64209">derive</span> <span
  m="64599">as</span> <span m="64750">true.</span> <span m="65310">Drink</span>
  <span m="65540">is</span> <span m="65680">false.</span></p><p><span
  m="66680">I'm</span> <span m="66850">using</span> <span m="67150">the</span>
  <span m="67270">AND</span> <span m="67750">operator</span> <span
  m="69310">to</span> <span m="69400">figure</span> <span m="69670">out</span>
  <span m="69850">if</span> <span m="70060">I</span> <span
  m="71020">should</span> <span m="71170">drink</span> <span
  m="71530">and</span> <span m="71680">derive,</span> <span m="73360">and</span>
  <span m="73840">I'm</span> <span m="73930">going</span> <span
  m="74140">to</span> <span m="74230">print</span> <span m="74460">out</span>
  <span m="75830">false.</span> <span m="77440">So,</span> <span
  m="78190">perfect,</span> <span m="78610">people</span> <span
  m="78850">are</span> <span m="78940">getting</span> <span m="79240">it.</span>
  <span m="80050">Great</span> <span m="80200">job,</span> <span
  m="80440">guys.</span></p>
embedded_media:
  - uid: 16612616698925ef9f0a8af1b9793267
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: lniF6ys2CIk
  - uid: 6123f1f2020a58ca84ed270199535eae
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: lniF6ys2CIk.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/6123f1f2020a58ca84ed270199535eae_lniF6ys2CIk.srt
  - uid: ac677a6b04c164d2a7abb7adefa21838
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: lniF6ys2CIk.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/ac677a6b04c164d2a7abb7adefa21838_lniF6ys2CIk.pdf
  - uid: be3486512ee9749f55249b57afe88c99
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 2477b2b77ad1b10813e24b11f7ff3fb8
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
  - uid: a78070c41e782e6c04be67a96e016327
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: lniF6ys2CIk
  - uid: 3a7553a88596bcd91a9323b79830a5b0
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/lniF6ys2CIk/default.jpg'
  - uid: ea60593e7865d7720d3a8822ffbc1c1a
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: 'https://itunes.apple.com/us/itunes-u/id1192805159'
  - uid: 35fbd648496844d94ebb360e63579866
    parent_uid: 65aaf4468cd399bbe70987a4b31ced35
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: >-
      https://archive.org/download/MIT6.0001F16/MIT6_0001F16_Lecture_02_exercise_02_300k.mp4
course_id: 6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016
type: course
layout: video
---
