## Music-Visualizer: Only spectrum
Modified by Niccolò Perego and Riccarto Di Palma, 28/9/2023

Visualizing spectrum of music.

<!-- [![An example of the visualization](/demo.gif)](https://www.youtube.com/watch?v=OXY-12lkqgE)

### [Demo video](https://www.youtube.com/watch?v=OXY-12lkqgE). -->

## How to install
1. Download this repository and save it to your machine (e.g. ~/code/Music-Visualizer)
2. Install [FFmpeg](https://ffmpeg.org/download.html) on your machine, if it is not already installed.

If you are working on linux and in an environment with ffmpeg (for example if you have opencv in it), it most likely will be outdated and will cause an error over the drange parameter. To avoid this, install the most recent static version found <a href="https://johnvansickle.com/ffmpeg/">here</a> and follow this <a href="https://www.johnvansickle.com/ffmpeg/faq/">guide</a> for the installation. Then use the --ffmpeg argument when lauching the script to specify the updated version of ffmpeg, avoiding the one in the environment.

## Introductory usage
- Take a look at all the available options
    ```sh
    python Music-Visualizer -h
    ```
- Single file
    ```sh
    python Music-Visualizer -i music.mp3
    ```
    ```sh
    python Music-Visualizer -i full/path/to/the/music.m4a
    ```
    With custom output dir:
    ```sh
    python Music-Visualizer -i music.wav -o abs/path/to/the/folder
    ```
    With custom ffmpeg:
    ```sh
    python Music-Visualizer -i music.wav -ff ~/ffmpeg/bin/ffmpeg.exe
    ```
- Multiple files
    ```sh
    python Music-Visualizer -i folder/of/music
    ```
- Using GPU
    - AMD:
        ```sh
        python Music-Visualizer -i folder/of/music -g a
        ```
    - NVIDIA:
        ```sh
        python Music-Visualizer -i folder/of/music -g n
        ```
    Lossless render (full quality):
    ```sh
    python Music-Visualizer -i folder/of/music -g n -q 0
    ```
- 60 frames per second
    ```sh
    python Music-Visualizer -i music.m4a -r 60
    ```

## Customized style
- custom title font:
    - Linux:
        ```sh
        python Music-Visualizer -i music.m4a -tf ~/.fonts/Arial.ttf
        ```
    - Windows:
        ```sh
        python Music-Visualizer -i music.m4a -tf C\:/Windows/Fonts/Arial.ttf
        ```
    - MacOS:
        ```sh
        python Music-Visualizer -i music.m4a -tf /Library/Fonts/Arial.ttf
        ```
- color scheme:
    ```sh
    python Music-Visualizer -i music.m4a -pc #fafbfa -wcl #3280c9 -wcr #32c958 -vc #ee2020
    ```

## Limitations
- The only resolution option available is HD (1280x720)

## Troubleshooting
- if you encounter this error message `Option 'rate' not found`, search for "#BUG" in `main/main.py` and follow the written instructions
- if `--vol_color` showing wrong color, check the comments near the end of the file `main/arg_parser.py`

## License
This project is licensed under the MIT license.
