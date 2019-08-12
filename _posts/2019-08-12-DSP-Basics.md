---
layout: post
title: Music Signal Processing and Analog-to-Digital Conversion Basics
mathjax: true
comments: true
tags: DSP
---


## Introduction to Digital Signal Processing (DSP)
Digital Signal Processing (DSP) is an area of computer science that focuses on the study and use of operations on digital signals. Signals apply to speech, music, electric voltage, images, temperature, and more. My interest is primarily in audio signals related to music, but the fundamental concepts are all the same. Using the techniques formed from the field of DSP can help us do some pretty amazing things with signals. After giving a brief summary on a few ways that DSP applies to music, we'll talk about the conversion process that allows continuous signals to be converted into digital signals vice versa. 
## DSP for Music
Digital Signal Processing for Music or Music Signal Processing has a lot of interesting applications. An interesting area of DSP for Music relates to the inner workings of digital audio workstations (DAWs) like Pro Tools, FL Studio, Logic, and Abelton. These software tools are driven by systems designed to apply effects such as delay, reverb, equalization, and distortion to audio signals. Your favorite songs make great use of these effects driven by DSP. Other interesting areas of DSP for music are sound recognition, audio fingerprinting, sound synthesis, music generation, audio source separation, and more. As you see with a few of the aforementioned topics, DSP can be used in tandem with other fields of study like artificial intelligence.

## Signal Basics
A **signal** can be defined as a function that describes the relationship between any physical quantity and one or more independent variables. 
\\[s(t) = 10\\]
\\[s(x, y, z) = 4x + 3y - 8xz^2\\]
A good example is an audio signal, which describes the relationship between frequency and time.
\\[\sum_{i=1}^{N} A_i(t)sin[2\pi F_i (t)t + \theta_i(t)]\\]
In this case, we describe a signal that can be represented as the sum of multiple sinusoids with different amplitudes and frequencies, where {\\(A_i(t)\\)}, {\\(F_i(t)\\)}, and {\\(\theta_i(t)\\)} are the sets of amplitudes, frequencies, and phases, respectively. **Amplitude** can be defined as the height from the center line to the peak of a sinusoidal function. A **frequency** can be described the number of occurrences of a repeating event over a unit of time. The frequency of an audio signal is measured in **Hz** and describes the range of signals that can be heard by the human ear.  **Phase** describes the relative value of some real variable $t$ within the span of a full period. A **period** describes the length of one cycle of the sinusoidal curve. The natural period of a sine curve is \\(2\pi\\).
	
A signal itself can be **discrete** or **continuous**. A continuous signal has an infinite number of values between an interval \\((a,b)\\), where as a discrete signal is defined as a function that only holds values for specific values of time within an interval. An example of a continuous-time sinusoidal signal would be
\\[\Omega = 2\pi F\\]
\\[x_a(t) = A \cos(\Omega t + \theta), -\infty < t < \infty\\]
where \\(A\\) is the amplitude of the sinusoid, \\(\omega\\) is the frequency in radians per second, \\(\theta\\) is the phase in radians.
An example of a discrete-time sinusoidal signal would be
	
\\[\omega = 2\pi f\\]
\\[x(n) = A\cos(2\omega n + \theta ), -\infty < t < \infty\\]
where \\(f\\) is described in terms of periods per sample.

## A/D Conversion Process
### Sampling
**Sampling** involves taking samples from a continuous signal at discrete time instants. In practice, signals are typically sampled **periodically**. Periodic sampling can be described by the function
\\[x(n) = x_a(nT)\\]
where \\(x(n)\\) is a discrete-time signal observed by taking samples from the continuous-time signal $x_a(t)$ every $T$ seconds. $T$ can also be referred to as the *sample period* or *sample interval*, where as \\(1/T\\) is referred to as the *sampling rate*. **44.1kHz**, **48kHz**, and **88.2kHz** are some typical sample rate, where **44.1kHz** is often used in audio-related applications.
	
How do we ensure that we have the right sampling rate to reconstruct a continuous signal from a discrete one? We achieve this by using the sampling theorem that states 
	
\\[F_s > 2F_{max}\\] 
where \\(F_s\\) is the sampling rate and \\(F_{max}\\) is the max frequency of a signal over time. This ensures that we avoid **aliasing**, which can be described as the distortion that comes from the results of signal reconstruction varying from the original continuous signal.
### Quantization and Coding
**Quantization** is the conversion of a sample at time $n$ from a continuous signal to a discrete-valued quantity at time $n$. This process turns a discrete-time, continuous value signal to a discrete-time, discrete-value signal. **Coding** translates each discrete value into binary sequences.

## Application

In music, the analog to digital conversion process is often used during the recording process. Music is often produced on computers using analog recording, so it must be converted to a digital format that can be used for CDs and different types of music files. That's it for now! Feel free to leave comments, suggestions, and feedback below!  
