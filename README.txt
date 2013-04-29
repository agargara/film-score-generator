Film Score Generator
David Cummings

As the name implies, the goal of the program is to automatically score a given video file. Music clips are analyzed and tagged with various aspects. The program analyzes a video as it plays and tries to select appropriate music clips from the database to match. 

You can see a short demo of the program in action here: 
http://vimeo.com/22379628
Note that the second half of the demo uses pre-made music to accompany the automatic film score.

Usage:
1. Put any number of audio clips in samples directory.
2. Use _audioAnalysis.maxpat to analyze each sample and add it to the sample database. See below for the list of traits.
3. Open _filmscoregenerator.maxpat and load a movie file. Make sure to turn on DAC.

Audio traits:
    Trait		Number		Meaning
    -------------------------------------------------
    USER DEFINED:
    Type		0-4			0 is drums, 1 is sfx, 2 is melodic, 3 is harmonic, 4 is other/mixed
    Voices		1-16		Number of voices in clip
    Speed		0-255		Speed of internal rhythms, 0 is slowest, 255 is fastest.
    Key			0-24		0 is NA, 1 through 12 is A through A flat major, 13-24 is A through A flat minor
    Angst		0-255		0 is happiest, 255 is most angsty
    Loop		0-1			0 is not a loop, 1 is a loop

    ANALYZED:
    BPM			20-400		Beats Per Minute
    Length		(ms)		Length of clip
    Brightness	0-???		Brightness of clip
    Gain		0-1			Average gain
    Noisiness	0-1			Noisiness of clip
    Punch		0-16 Hz		Calculated by number of onsets per second.
    Frequency	0-16000 Hz	Average frequency of clip

Mapping:
    VIDEO				AUDIO
    ------------------------------
    Rate of change		BPM/Speed
    Brightness			Brightness/Frequency
    Variation in frame	Noisiness/Punch
    Saturation			Angst
    Hue					Punch