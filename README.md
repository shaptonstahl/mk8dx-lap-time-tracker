# Mario Kart 8 Deluxe Lap Time Tracker

Inputs screenshots of final times, extracts lap time and other stats, then stores them in a formatted Excel file.

This is perfect for tracking all of your lap times!

The type of screen capture is determined by looking at small parts of the image using [ocrs](https://github.com/robertknight/ocrs).

The details are pulled out of the image using [OpenAI](https://platform.openai.com/).

## Installation

It's recommended that you run Python in a virtual environment. This has been tested with Python 3.9.21.

Load the required packages with:

`pip install -r ./requirements.txt`

You will need an OpenAI API key. Set the environment variable `OPENAI_API_KEY` to your API key.
One way to do this is to create a plain text file named `.env` in the same folder as the script.
It should contain the line:

`OPENAI_API_KEY = "myverylongkeygoeshere"`

The script will read the API key from the file.

## Usage

Normal usage will look like:

`python ./update_mk8dx_excel_data.py --folder_to_process ./data/test_images -cache_file_name ./cache.pkl -target_excel_file ./MK8DX_lap_times.xlsx`

or

`python ./update_mk8dx_excel_data.py -f ./data/test_images -c ./cache.pkl -t ./MK8DX_lap_times.xlsx`

## Debugging

For debugging you might run:

`python ./update_mk8dx_excel_data.py -f ./data/test_images -c ./cache.pkl -t ./MK8DX_lap_times.xlsx --verbose --debug`

Paths should be specified with forward slashes ('/').