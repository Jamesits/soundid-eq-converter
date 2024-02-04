# SoundID EQ Converter

Convert speaker profile generated by SoundID Reference Measure to EqualizerAPO configuration file.

Sometimes SoundID Reference does not work with your output device or a specific audio pipeline configuration, and this script might come in handy.

## Requirements

- [Python](https://www.python.org/downloads/) 3.9+ for running this script
- [SoundID Reference Measure](https://store.sonarworks.com/collections/soundid-reference), a valid license, and a microphone on the measuring device to create a profile
- [EqualizerAPO](https://sourceforge.net/projects/equalizerapo/) installed on the playback device to apply the profile

## Usage

0. Create a speaker profile using SoundID Reference Measure
0. Load the speaker profile to SoundID Reference using any output device
0. Select your target mode and Dry/Wet ratio
0. On the left sidebar, click on the "…" menu -> Export -> Dolby Atoms Renderer
0. Save the file to your desired location
0. Run the converter: `python3 convert.py <path-to-exported-file> <output-path>`
0. Put the generated file to `%ProgramFiles%\EqualizerAPO\config\config.txt`
0. Profit
