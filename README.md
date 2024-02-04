# SoundID EQ Converter

Convert speaker profile generated by SoundID Reference Measure to EqualizerAPO configuration file.

Sometimes SoundID Reference does not work with your output device or a specific audio pipeline configuration, and this script might come in handy.

## Requirements

- [Python](https://www.python.org/downloads/) 3.9+ for running this script
- [SoundID Reference Measure](https://store.sonarworks.com/collections/soundid-reference), a valid license, and a microphone on the measuring device to create a profile
- [EqualizerAPO](https://sourceforge.net/projects/equalizerapo/) installed on the playback device to apply the profile

## Application Notes

WARNING: Although we try to clamp the total gain, this script might still generate unexpected high gain values. **Please check the generated configuration file before applying it to your system**, otherwise it might permanently damage your ear or your audio equipment. I'm not responsible for any damage caused by using this script.

This script has only been validated with a stereo (2.0) configuration because I'm poor. If you have a multi-channel setup, please send me an exported profile so I can test and fix the script.

## Usage

0. Create a speaker profile using SoundID Reference Measure
0. Load the speaker profile to SoundID Reference using any output device
0. Select your target mode and dry/wet ratio (these configuration will be baked in)
0. On the left sidebar, click on the "…" menu -> Export -> Dolby Atoms Renderer
0. Save the exported profile to your desired location (by default in `%AppData%\Sonarworks\SoundID Reference\Sonarworks Projects\Exported Presets`)
0. Run the converter: `python3 convert.py <exported-profile.txt> <config.txt>`
0. Put the generated file to `%ProgramFiles%\EqualizerAPO\config\config.txt`
0. Profit

If you have multiple audio devices with EqualizerAPO APO enabled, you need to add a `Device: ` line to the generated configuration file to make the configuration apply to the correct device. The line can be copied from the Configurator app with the "Copy Device command to clipboard" button.
