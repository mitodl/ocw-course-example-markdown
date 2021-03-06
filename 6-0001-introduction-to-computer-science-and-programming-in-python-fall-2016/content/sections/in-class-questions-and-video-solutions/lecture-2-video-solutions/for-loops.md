---
order_index: null
title: For Loops
template_type: Embed
uid: fd2e2e45802d0a8d766a7ed5f77db5a3
parent_uid: 01c07d8fbd4064402253a19dcc1754ea
technical_location: >-
  https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/in-class-questions-and-video-solutions/lecture-2-video-solutions/for-loops
short_url: for-loops
inline_embed_id: 55742778forloops66366568
about_this_resource_text: >-
  <p><strong>Description:</strong> This in-class question demonstrates For Loops
  and Break statements in Python.</p> <p><strong>Instructor:</strong> Dr. Ana
  Bell</p>
related_resources_text: ''
transcript: >-
  <p><span m='790'>The</span> <span m='880'>following</span> <span
  m='1300'>content</span> <span m='1870'>is</span> <span
  m='1990'>provided</span> <span m='2440'>under</span> <span m='2710'>a</span>
  <span m='2770'>Creative</span> <span m='3190'>Commons</span> <span
  m='3580'>license.</span> <span m='4730'>Your</span> <span
  m='4870'>support</span> <span m='5380'>will</span> <span m='5530'>help</span>
  <span m='5770'>MIT</span> <span m='6220'>OpenCourseWare</span> <span
  m='7030'>continue</span> <span m='7540'>to</span> <span m='7630'>offer</span>
  <span m='8050'>high</span> <span m='8290'>quality</span> <span
  m='8770'>educational</span> <span m='9400'>resources</span> <span
  m='10030'>for</span> <span m='10210'>free.</span> <span m='11390'>To</span>
  <span m='11410'>make</span> <span m='11620'>a</span> <span
  m='11650'>donation</span> <span m='12370'>or</span> <span
  m='12610'>view</span> <span m='13060'>additional</span> <span
  m='13480'>materials</span> <span m='13990'>from</span> <span
  m='14200'>hundreds</span> <span m='14590'>of</span> <span m='14710'>MIT</span>
  <span m='15130'>courses,</span> <span m='16219'>visit</span> <span
  m='16450'>MIT</span> <span m='16870'>OpenCourseWare</span> <span
  m='17880'>at</span> <span m='18120'>ocw.mit.edu.</span> </p><p><span
  m='23830'>PROFESSOR: So</span> <span m='24010'>now</span> <span
  m='24190'>we</span> <span m='24310'>have</span> <span m='24520'>this</span>
  <span m='25270'>last</span> <span m='25630'>exercise.</span> <span
  m='27880'>I'm</span> <span m='28030'>creating</span> <span m='28420'>a</span>
  <span m='28480'>mysum.</span> <span m='30310'>I'm</span> <span
  m='30430'>going</span> <span m='30670'>to</span> <span m='30760'>go</span>
  <span m='31000'>through</span> <span m='31300'>all</span> <span
  m='31480'>of</span> <span m='31600'>these</span> <span m='31810'>values</span>
  <span m='32439'>and</span> <span m='32560'>you</span> <span
  m='32680'>guys</span> <span m='32890'>have</span> <span
  m='33040'>already</span> <span m='33280'>told</span> <span m='33490'>me</span>
  <span m='33640'>what</span> <span m='33760'>values</span> <span
  m='34150'>these</span> <span m='34360'>are,</span> <span m='34660'>5,</span>
  <span m='35500'>7,</span> <span m='36580'>9,</span> <span m='37450'>not
  11.</span> <span m='39640'>And</span> <span m='39760'>I'm</span> <span
  m='39850'>going</span> <span m='40060'>to</span> <span m='40210'>add</span>
  <span m='40750'>to</span> <span m='40870'>mysum.</span> <span
  m='41440'>So</span> <span m='41540'>I'm</span> <span m='41640'>going</span>
  <span m='41650'>to</span> <span m='41740'>keep</span> <span m='41920'>a</span>
  <span m='41980'>running</span> <span m='42280'>sum</span> <span
  m='43180'>adding</span> <span m='43510'>all</span> <span m='43660'>of</span>
  <span m='43750'>these</span> <span m='43930'>values</span> <span
  m='44320'>together.</span> </p><p><span m='47090'>So</span> <span
  m='47560'>the</span> <span m='47680'>very</span> <span m='47950'>first</span>
  <span m='48220'>time</span> <span m='48460'>through</span> <span
  m='48640'>the</span> <span m='48760'>loop,</span> <span m='50140'>mysum</span>
  <span m='51010'>gets</span> <span m='51310'>the</span> <span
  m='51430'>value</span> <span m='52540'>of</span> <span m='52930'>5.</span>
  <span m='55410'>That's</span> <span m='55700'>this</span> <span
  m='56030'>line</span> <span m='56270'>here.</span> <span m='57480'>The</span>
  <span m='57580'>next</span> <span m='57650'>thing</span> <span
  m='58160'>I</span> <span m='58310'>see</span> <span m='58580'>inside</span>
  <span m='58970'>this</span> <span m='59120'>loop</span> <span
  m='59390'>is</span> <span m='59810'>an</span> <span m='59930'>if</span> <span
  m='60110'>statement.</span> <span m='61280'>If</span> <span
  m='61550'>mysum</span> <span m='62000'>is</span> <span m='62090'>equal</span>
  <span m='62300'>to</span> <span m='62420'>5.</span> <span
  m='63510'>That's</span> <span m='63770'>true.</span> <span m='66330'>So</span>
  <span m='66530'>I'm</span> <span m='66650'>going</span> <span
  m='66800'>to</span> <span m='66860'>go</span> <span m='67100'>inside</span>
  <span m='67520'>this</span> <span m='67700'>if</span> <span
  m='67850'>statement.</span> <span m='68840'>The</span> <span
  m='68900'>next</span> <span m='69140'>thing</span> <span m='69320'>I</span>
  <span m='69410'>see</span> <span m='69740'>is</span> <span m='69890'>a</span>
  <span m='69950'>break.</span> </p><p><span m='73220'>If</span> <span
  m='73310'>I</span> <span m='73400'>see</span> <span m='73550'>this</span>
  <span m='73730'>break</span> <span m='74030'>am</span> <span
  m='74180'>I</span> <span m='74320'>evaluating--</span> <span
  m='75300'>am</span> <span m='75460'>I</span> <span m='75560'>evaluating</span>
  <span m='76100'>this line</span> <span m='76430'>or</span> <span
  m='76490'>not?</span> <span m='78180'>No,</span> <span
  m='78620'>exactly.</span> <span m='79600'>Because</span> <span
  m='80570'>whenever</span> <span m='80900'>Python</span> <span
  m='81280'>sees</span> <span m='81530'>break,</span> <span
  m='81980'>it's</span> <span m='82160'>going</span> <span m='82430'>to</span>
  <span m='83780'>say,</span> <span m='83990'>I'm</span> <span
  m='84080'>going</span> <span m='84200'>to</span> <span m='84260'>stop</span>
  <span m='84560'>right</span> <span m='84740'>here,</span> <span
  m='85170'>exit</span> <span m='85520'>out</span> <span m='85640'>of</span>
  <span m='85730'>the</span> <span m='85850'>loop</span> <span
  m='86510'>that</span> <span m='86630'>I'm</span> <span
  m='86720'>currently</span> <span m='87140'>in,</span> <span
  m='88460'>and</span> <span m='88670'>go</span> <span m='88880'>to</span> <span
  m='89060'>the</span> <span m='89360'>statement</span> <span
  m='89750'>that's</span> <span m='89960'>immediately</span> <span
  m='90380'>right</span> <span m='90560'>after</span> <span m='90860'>it.</span>
  </p><p><span m='92220'>So</span> <span m='92270'>what</span> <span
  m='92390'>this</span> <span m='92570'>is</span> <span m='92660'>going</span>
  <span m='92810'>to</span> <span m='92900'>print</span> <span
  m='93230'>is</span> <span m='93410'>mysum.</span> <span m='94820'>And</span>
  <span m='95210'>that's</span> <span m='95450'>the</span> <span
  m='95840'>exercise</span> <span m='96440'>we</span> <span
  m='96590'>were</span> <span m='96740'>looking</span> <span
  m='97100'>at.</span> <span m='97280'>Let's</span> <span m='97460'>see</span>
  <span m='97850'>how</span> <span m='98090'>the</span> <span
  m='98210'>class</span> <span m='98630'>did.</span> <span
  m='101540'>Pretty</span> <span m='101750'>good.</span> <span
  m='105370'>Hopefully</span> <span m='105690'>if</span> <span
  m='105780'>you</span> <span m='105870'>answered</span> <span
  m='106170'>one</span> <span m='106320'>of</span> <span
  m='106410'>these,</span> <span m='108450'>the</span> <span
  m='108540'>explanation</span> <span m='109140'>was--</span> <span
  m='110010'>was</span> <span m='110130'>all</span> <span
  m='110190'>right.</span> <span m='110370'>If</span> <span
  m='110550'>not,</span> <span m='110970'>just</span> <span m='111150'>go</span>
  <span m='111300'>back</span> <span m='111600'>and</span> <span
  m='111720'>try</span> <span m='111870'>to</span> <span m='111960'>work</span>
  <span m='112200'>through</span> <span m='112380'>it</span> <span
  m='112470'>step</span> <span m='112710'>by</span> <span
  m='112860'>step.</span> </p>
embedded_media:
  - uid: da0426a6eb5b65848eb60c6e89192a74
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: 3Play-3PlayYouTubeid-MP4
    title: 3Play-3Play YouTube id
    type: 3Play
    media_location: mrvBnZIEsZY
  - uid: 86c7111d6b74fc876f3a70164581d0b2
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: mrvBnZIEsZY.srt
    title: 3play caption file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/bad72996d1e129055544ac4897e4266c_mrvBnZIEsZY.srt
  - uid: 853fadcd3f0c611ef65d59226b737317
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: mrvBnZIEsZY.pdf
    title: 3play pdf file
    type: null
    technical_location: >-
      https://open-learning-course-data-production.s3.amazonaws.com/6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016/1bbe737a47db4c783c9029578fd82778_mrvBnZIEsZY.pdf
  - uid: e403ddbdca5f15e462aaac15d19011d2
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Caption-3Play YouTube id-SRT
    title: Caption-3Play YouTube id-SRT-English - US
    type: Caption
  - uid: 386fcf258ee38a6b63fc699120ababca
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Transcript-3Play YouTube id-PDF
    title: Transcript-3Play YouTube id-PDF-English - US
    type: Transcript
  - uid: 66e8bec287cd2bcb6ddc8f798435838f
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Video-YouTube-Stream
    title: Video-YouTube-Stream
    type: Video
    media_location: mrvBnZIEsZY
  - uid: ff54798973232dd6f1cd6eab608bdba7
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Thumbnail-YouTube-JPG
    title: Thumbnail-YouTube-JPG
    type: Thumbnail
    media_location: 'https://img.youtube.com/vi/mrvBnZIEsZY/default.jpg'
  - uid: 94f8c62bc98e941eba53e309c207703e
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Video-iTunesU-MP4
    title: Video-iTunes U-MP4
    type: Video
    media_location: 'https://itunes.apple.com/us/itunes-u/id1192805159'
  - uid: bd4ed980fd49a8b91b946dde9f6f11d4
    parent_uid: fd2e2e45802d0a8d766a7ed5f77db5a3
    id: Video-InternetArchive-MP4
    title: Video-Internet Archive-MP4
    type: Video
    media_location: >-
      https://archive.org/download/MIT6.0001F16/MIT6_0001F16_Lecture_02_exercise_05_300k.mp4
course_id: 6-0001-introduction-to-computer-science-and-programming-in-python-fall-2016
type: course
layout: video
---
