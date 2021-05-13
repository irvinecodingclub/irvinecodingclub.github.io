---
layout: post
title:  "Coding Music with Sonic Pi"
image: assets/images/music.png
image2: assets/images/music2.png
permalink: /codingmusic
course: true
comments: false
excerpt: "Coding with a language that leads to music coming out."
---

Coding with a language that leads to music coming out.


| Instructor  | &nbsp;&nbsp;&nbsp;Date&nbsp; | &nbsp;&nbsp; &nbsp;&nbsp;Zoom ID &nbsp; |  
| :---        |    :----   |          :--- |   
| Sophia Dai  | Summer,2021   |&nbsp;&nbsp; 890 1539 2821 &nbsp; &nbsp; |

<br/>


**What it is**: Coding with a language that leads to music coming out  
**Prerequisites**: Musical knowledge, basic knowledge of all the notes, more advanced knowledge of chords, progressions, scales, arpeggios, and melodies  
**Required Tools**: Sonic Pi (desktop or mac)  
**Recommended Tools**: Piano keyboard (if you don’t have perfect pitch)  

## Course Introduction and Demo

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQ5wqIRB5-_nJeDC6j4nUqlKtM6aCmcpN6ZVaVs0DtIcDZuC4_bZpjYwsAHqDalACkJfBJ91JvnTHC5/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<!-- Begin Article

## Week 1: Notes, Chords, Release, Sustain, Bleh

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTSlc-is3W8eVVUZ6iKI_t-zDxPUSlI_1BR0px8VekVX0DKxjnXz8v3YxuAd_8VVMcnB6umh1lY6NwF/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


{% highlight python linenos %}
Harry Potter:
in_thread do
  1.times do
    use_synth :kalimba
    play :E, amp: 5
    sleep 0.6
    play :A, release: 2, amp: 3
    sleep 0.8
    play :C5, release: 0.5, amp: 3
    sleep 0.3
    play :B, amp: 3
    sleep 0.6
    play :A, release: 2, amp: 3
    sleep 0.95
    play :E5, release: 0.7, amp: 3
    sleep 0.6
    play :D5, release: 2, amp: 3
    sleep 1.4
    play :B, release: 2, amp: 3
    sleep 1.1
    play :A, release: 2, amp: 3
    sleep 0.7
    play :C5, release: 0.5, amp: 3
    sleep 0.3
    play :B, amp: 3
    sleep 0.6
    play :A, release: 1.5, amp: 3
    sleep 1
    play :Bb, amp: 3
    sleep 0.6
    play :E, release: 3, amp: 3
  end
end

in_thread do
  1.times do
    use_synth :hollow
    sleep 0.6
    play :A3, release: 1.5
    sleep 1.7
    play :A3, release: 2, amp: 0.7
    play :E3, release: 2.2, amp: 0.7
    sleep 1.6
    play :A3, release: 1.4
    sleep 1.35
    play :E3, release: 2, amp: 0.7
    sleep 2.7
    play :A3, release: 3.2, amp: 0.7
    sleep 1.65
    play :A3, release: 3, amp: 0.7
    play :E3, release: 3, amp: 0.6
    play :B3, release: 3, amp: 0.5
    sleep 1.5
    play :Ds3, amp: 0.5
  end
end

Dre Speedrun:
define :bass do
  play :Bb3, release: 0.5
  sleep 0.45
  play :Bb3, release: 0.35
  sleep 0.3
  play :Ab3, release: 0.6
  sleep 0.55
  play :Bb3, release: 0.45
  sleep 0.4
  play :Bb3, release: 0.45
  sleep 0.4
  play :Ab3, release: 0.5
  sleep 0.45
  play :Ab3, release: 0.3
  sleep 0.25
  play :Bb3, release: 0.3
  sleep 0.25
  play :Bb3, release: 0.25
  sleep 0.2
  play :Ab3, release: 0.45
  sleep 0.45
end

define :chords do
  play :F, sustain: 3.7, amp: 0.2
  sleep 3.7
end

define :climax do
  play :Ab, release: 0.25, amp: 3
  sleep 0.2
  play :Db5, release: 0.225, amp: 3
  sleep 0.175
  play :Eb5, release: 0.4, amp: 3
  sleep 0.35
  play :Bb, release: 0.45, amp: 3
  sleep 0.35
end

in_thread do
  loop do
    use_synth :growl
    bass
  end
end

in_thread do
  loop do
    chords
  end
end

loop do
  sleep 6.25
  climax
end

{% endhighlight %}

================================================== -->


## Week 2: Synths, Samples, FX

## Week 3&4: Variables, Loops, If Else, Functions

## Week 5: Rings, Ticks

## Week 6: Minecraft, Live Coding
