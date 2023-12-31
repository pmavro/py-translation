
# py-translation

## Description
The py-translation project is designed to facilitate language transcription through the Whisper model by OpenAI in a more user-friendly format. Furthermore, the program provides a .srt output file (for timestamped subtitles) and a plain-text file (for reading/writing purposes). The program also includes an inbuilt translation service through Google Translator (potentially more into the future), allowing the end-user to ultimately convert an audio file of any language into translated English text.

## Installation

Prior to downloading the repository, you require:

- An installation of Python 3.10 or higher
- [CUDA Toolkit 11](https://developer.nvidia.com/cuda-toolkit-archive) - Tested with [CUDA Toolkit 11.8.0](https://developer.nvidia.com/cuda-11-8-0-download-archive)
- [cuBLAS for CUDA 11](https://developer.nvidia.com/cublas) - Installed through the CUDA Toolkit
- [cuDNN 8 for CUDA 11](https://developer.nvidia.com/rdp/cudnn-archive) - Tested with [cuDNN v8.9.5 for CUDA 11.x](https://developer.nvidia.com/rdp/cudnn-archive#a-collapse895-118)
- An ffmpeg installation with the PATH environment variable assigned (This can be done through [Chocolatey](https://chocolatey.org/install) with the command `choco install ffmpeg` or manually through the [official FFmpeg site](https://ffmpeg.org/download.html))

After downloading/cloning the repository, run the setup.bat file in the directory. Alternatively, run this in the command-line/terminal to install the requirements for the program:
```
python -m pip install -r requirements.txt
python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

## Usage

Run `main.py` to start the application. The script supports multiple languages for translation however only accepts English as an input for most of its' inputs. You must also have a `.wav`, `.mp3` or `.flac` file present in the `inputs` directory prior to running the script (for transcription).

Keys for API-enabled services (currently Microsoft Translator and ChatGPT) must be input into the `keys.txt` file present in the `settings` directory following the `=` sign.

The program can be started through the terminal command:
```
python3 main.py
```

By the conclusion of the script, your directory should house one or more of these files:

- `output.srt` (subtitling file, made for SubRip)
- `final_text_output.txt` (raw text post-filtering)
- `final_text.txt` (like final_text_output, however unique lines only (cleanest file))
- `translated.txt` (translated version of final_text, only available after translation is done)

## Supported Languages for Translation

`languages.txt` contains a list of supported languages for translation of the provided file, including but not limited to English, Spanish, French, and many others.

## Contributing
Contributions are welcome! Please submit pull requests or open issues to propose changes or report bugs.

## Acknowledgements
All rights reserved to appropriate parties, including but not limited to OpenAI, the developers behind [stable](https://github.com/jianfch/stable-ts) and [fast](https://github.com/SYSTRAN/faster-whisper) Whisper, and the parties behind the included libraries.

## License
[MIT License](https://choosealicense.com/licenses/mit/)

## Contact
For support or to report issues, contact `pmavro05@gmail.com`.
