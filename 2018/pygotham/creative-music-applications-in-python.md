# "Create Music Applications in Python" by Dror Ayalon

[Soundscape](https://soundsca.pe)

Looping music/sound has a meditative value.
What if you built an automatic looper?


## Finding repeated sounds

* Look for onset strength repetitions (beats, usually)
* Auto-correlate audio to find similar segments
* 2D convolution to reduce dimensionality of data for real-time processing
* Most prominent note or scale throug spectral analysis
* Amplitude measurement


## Soundscape

Built a Django web application to allow people to record loops and find similar loops to use together.


## Miscellaneous

Default stack:

* `numpy`
* `scipy`
* `librosa`
* `pyaudio`

More useful tools:

* `pandas`
* `pydub`
* `ffmpeg`
* `Django`
* `madmom`
* `audioread`
* `soundfile`
* Google's Magenta
* `textgenrnn`

Dror's packages:

* `AudioOwl`
* `MixingBear`
