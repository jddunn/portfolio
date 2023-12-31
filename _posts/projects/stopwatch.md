---
title: 'Stopwatch'
coverImage: '/assets/projects/stopwatch-site-demo-1.png'
excerpt: 'Web app built with the Affectiva API that automatically curates YouTube content based on detected emotions (through computer vision)'
date: '2016'
createdDate: '2016'
tags: 'javascript,ai,computer vision,webcam,youtube'
ogImage:
  url: '/assets/projects/stopwatch-site-demo-1.png'
---

<a class="md-link" href="https://github.com/jddunn/stopwatch" target="_blank" style="text-align: center">GitHub link</a>

StopWatch is a web app that automatically goes through curated content from YouTube based off of the emotional states detected in the viewer by the webcam, utilizing the Affectiva SDK. Made with Bootstrap and jQuery. I created Stopwatch for a weekend hackathon project, with a prompt based around incorporating 'search' with 'video.'

### Image gallery

<a href="/assets/projects/stopwatch-site-demo-2.png" target="_blank"><img src="/assets/projects/stopwatch-site-demo-2.png" class="img-shadow" style="display: block; margin-left: auto; margin-right: auto;" width="320" alt="Stopwatch site demo 2"></img></a>

<a href="/assets/projects/stopwatch-site-demo-3.png" target="_blank"><img src="/assets/projects/stopwatch-site-demo-2.png" style="display: block; margin-left: auto; margin-right: auto;" width="320" alt="Stopwatch site demo 3"></img></a>

<a href="/assets/projects/stopwatch-site-demo-4.png" target="_blank"><img src="/assets/projects/stopwatch-site-demo-4.png" style="display: block; margin-left: auto; margin-right: auto;" width="320" alt="Stopwatch site demo 4"></img></a>

If positive feelings are detected in the viewer, then the current video in the playlist continues playing. If it reaches the end, then the most similar video found on YouTube to the video is played next. If negative emotions are detected, then the current video is skipped, and the next video in the randomized playlist of 50 videos (generated from keywords specified by the user) is played.