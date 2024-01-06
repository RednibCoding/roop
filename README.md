# RednibCoding version of ROOP, No NSFW Filter, No ERRORS ;)
Based on the work of [based9based](https://github.com/based9based/roop)

# Important
Roop needs python version 3.11.x because it still depends on distutils (which was removed in higher python versions like 3.12 and above).

# Roop

> Take a video and replace the face in it with a face of your choice. You only need one image of the desired face. No dataset, no training.

[![Build Status](https://img.shields.io/github/actions/workflow/status/s0md3v/roop/ci.yml.svg?branch=main)](https://github.com/s0md3v/roop/actions?query=workflow:ci)

## Installation

Be aware, the installation needs technical skills and is not for beginners. Please do not open platform and installation related issues on GitHub. We have a very helpful.

Contents:
- [1.-Installation](./readme/1.-Installation.md) - It is more likely to work on your computer, but will be quite slow
- [1.1-Setup-Linux](./readme/1.1-Setup-Linux.md)
- [1.2-Setup-MacOS](./readme/1.2-Setup-MacOS.md)
- [1.2-Setup-Windows](./readme/1.3-Setup-Windows.md)
- [Acceleration](./readme/2.-Acceleration.md) - Unleash the full potential of your CPU and GPU

## Usage

Start the program with arguments:

```
python run.py [options]

-h, --help                                                                 show this help message and exit
-s SOURCE_PATH, --source SOURCE_PATH                                       select an source image
-t TARGET_PATH, --target TARGET_PATH                                       select an target image or video
-o OUTPUT_PATH, --output OUTPUT_PATH                                       select output file or directory
--frame-processor FRAME_PROCESSOR [FRAME_PROCESSOR ...]                    frame processors (choices: face_swapper, face_enhancer, ...)
--keep-fps                                                                 keep target fps
--keep-frames                                                              keep temporary frames
--skip-audio                                                               skip target audio
--many-faces                                                               process every face
--reference-face-position REFERENCE_FACE_POSITION                          position of the reference face
--reference-frame-number REFERENCE_FRAME_NUMBER                            number of the reference frame
--similar-face-distance SIMILAR_FACE_DISTANCE                              face distance used for recognition
--temp-frame-format {jpg,png}                                              image format used for frame extraction
--temp-frame-quality [0-100]                                               image quality used for frame extraction
--output-video-encoder {libx264,libx265,libvpx-vp9,h264_nvenc,hevc_nvenc}  encoder used for the output video
--output-video-quality [0-100]                                             quality used for the output video
--max-memory MAX_MEMORY                                                    maximum amount of RAM in GB
--execution-provider {cpu} [{cpu} ...]                                     available execution provider (choices: cpu, ...)
--execution-threads EXECUTION_THREADS                                      number of execution threads
-v, --version                                                              show program's version number and exit
```


### Headless

Using the `-s/--source`, `-t/--target` and `-o/--output` argument will run the program in headless mode.

CPU:
```
python run.py --target ./data/test_video.mp4 --source ./data/test_pic.png -o ./data/swapped.mp4 --frame-processor face_swapper face_enhancer
```
GPU:
```
python run.py --target ./data/test_video.mp4 --source ./data/test_pic.png -o ./data/swapped.mp4 --execution-provider cuda --frame-processor face_swapper face_enhancer
```
etc. 

> Note: change `./data/test_video.mp4` to your .mp4 file and `./data/test_pic.png` to you face image file.


## Disclaimer

This software is designed to contribute positively to the AI-generated media industry, assisting artists with tasks like character animation and models for clothing.

We are aware of the potential ethical issues and have implemented measures to prevent the software from being used for inappropriate content, such as nudity.

Users are expected to follow local laws and use the software responsibly. If using real faces, get consent and clearly label deepfakes when sharing. The developers aren't liable for user actions.


## Licenses

Our software uses a lot of third party libraries as well pre-trained models. The users should keep in mind that these third party components have their own license and terms, therefore our license is not being applied.


## Credits

- [deepinsight](https://github.com/deepinsight) for their [insightface](https://github.com/deepinsight/insightface) project which provided a well-made library and models.
- all developers behind the libraries used in this project