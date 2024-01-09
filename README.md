# Usage

You can run BirdNET via the command line. You can add a few parameters that affect the output.

The input parameters include:

```
--i, Path to input file.
--o, Path to output file. Defaults to result.csv.
--lat, Recording location latitude. Set -1 to ignore.
--lon, Recording location longitude. Set -1 to ignore.
--week, Week of the year when the recording was made. Values in [1, 48] (4 weeks per month). Set -1 to ignore.
--overlap, Overlap in seconds between extracted spectrograms. Values in [0.0, 2.9]. Defaults tp 0.0.
--sensitivity, Detection sensitivity; Higher values result in higher sensitivity. Values in [0.5, 1.5]. Defaults to 1.0.
--min_conf, Minimum confidence threshold. Values in [0.01, 0.99]. Defaults to 0.1.
--custom_list, Path to text file containing a list of species. Not used if not provided.
```

Note: A custom species list needs to contain one species label per line. Take a look at the `model/label.txt` for the correct species label. Only labels from this text file are valid. You can find an example of a valid custom list in the 'example' folder.

Here are two example commands to run this BirdNET version:

```

python analyze.py --i "example\american-goldfinch-songs-7am-180718-62312.mp3" --lat 35.4244 --lon -120.7463 --week 18

python analyze.py --i "example\american-goldfinch-songs-7am-180718-62312.mp3" --lat 47.6766 --lon -122.294 --week 11 --overlap 1.5 --min_conf 0.25 --sensitivity 1.25 --custom_list 'example/custom_species_list.txt'

```

Note: Please make sure to provide lat, lon, and week. BirdNET will work without these values, but the results might be less reliable.

The results of the anlysis will be stored in a result file in CSV format. All confidence values are raw prediction scores and should be post-processed to eliminate occasional false-positive results.

# Contact us

Please don't hesitate to contact us if you have any issues with the code or if you have any other remarks or questions.

We are always open for a collaboration with you.

