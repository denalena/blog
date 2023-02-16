---
title: Make some noise!
date: 2023-01-18
---

Whenever I'm inside and I hear rain, it's really calming to me. Even storms manage to bring me peace. Sometimes, when I have difficulties to sleep, and it's not coincidentally raining outside, I might turn on some noise source. There are infinite options to choose from of course: iOS has it built in, there is airplane ambient noise readily available on Spotify and YouTube, and one of my favorites is the "Rain on a Tent" preset on [mynoise.net](https://mynoise.net/NoiseMachines/campingRainNoiseGenerator.php). 

On the other hand, during the day I noticed that the microphone of one of my co-workers has quite the high noise floor, and every time they unmute themselves in a call, I immediately start feeling a little more comfy because of that noise. Not long after that, I saw [an article](https://www.washingtonpost.com/wellness/2022/11/14/brown-noise-adhd-focus/) floating around [on HN](https://news.ycombinator.com/item?id=33685567#33690209) about how listening to the low rumble brown noise could help calming the mind.

In a nutshell, brown noise is static noise where you mostly hear the lower frequencies, I recommend reading the article to learn more about it.

> "I just feel like my brain is being hugged"

That article was a nice read, but as usual on HN, the real treasure is found in the comments. And I wasn't disappointed this time as well, something piqued my interest: a discussion emerged about how people like to play noise [from their command line](https://news.ycombinator.com/item?id=33687737).

> "This also helps cover up constant early morning construction and traffic. If I can help it I just use: play -n synth brown on any linux system with sox installed... it's definitely the cleanest sound I've found."

And this was quite the revelation to me. I really like to speed up my workflows because it minimizes the chance that I get distracted, and being able to fire up some concentrating noise in a quick way is really valuable to me. Also I really like that it's generated on the fly. So I listened to the different presets that people created and gathered the ones that sound the nicest to me, and here they are:

```
play -n -c 5 synth brown vol -17dB
        
play -n -n --combine merge synth brownnoise band -n 550 550 vol -17dB
        
play -n -n --combine merge synth '24:00:00' brownnoise band -n 750 750 tremolo 50 1 vol -17dB
        
play -c 2 --null synth brownnoise reverb bass 6 treble -3
        
play -c 2 --null synth brownnoise reverb bass 10 treble -6

play -n -n --combine merge synth brownnoise band -n 550 550 tremolo 50 1 vol -17dB reverb bass 10 treble -6

play -n -n --combine merge synth brownnoise band -n 150 150 tremolo 50 1 reverb bass 10 treble -6
```

Note that I added `vol -17dB` to almost all of them to make them a bit quieter by default. It's quite fun to experiment with the different options available and to find comfy settings for oneself. I usually go with the last one, and have it readily available in a `noise.sh` that is in a directory from my `$PATH`. Also, I bound it to the keystroke `ctrl+n` via my `.inputrc`.

I find myself to run this quite frequently now during work and I'm really thankful for finding out about it, so here I am, spreading the noise.