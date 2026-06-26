#  ARL SCOUT: The Situated Corpus of Understanding Transactions

## SCOUT Contents

Unique Commanders (human participants) are named as `p{exp}.{ID}` where `{exp}` is the experiment number (1-4) and `{ID}` is the Commander's ID assigned within that experiment. For example, the Commander `p1.01` is the first Commander in Experiment 1. Each Commander completed three trials {train, main1, main2}. The `data/main_trial_distribution.xlsx` file notes which counting task was completed in each main trial.

The data and annotation files from each Commander's trials are divided by type over five directories within the `data/` directory of this repository:

- [transcripts/](#transcripts)
- [iSCOUT/](#iSCOUT)
- [maps/](#maps)
- [dialogue_structure/](#dialogue-structure)
- [AMR/](#AMR)
- [Video-SCOUT](#Video-SCOUT)




## transcripts

Transcripts between the Commander, DM, and RN are supplied in two formats: an .xlsx spreadsheet and a .txt tab-delimited file. Commanders who completed all three trials (train, main1, main2) have the following transcript files (Commander p1.01 shown below):
```
└─── data/transcripts/
     └─── p1.01_train_transcript.xlsx
     └─── p1.01_main1_transcript.xlsx
     └─── p1.01_main2_transcript.xlsx
     └─── tab-delimited/p1.01_train_transcript.txt
     └─── tab-delimited/p1.01_main1_transcript.txt
     └─── tab-delimited/p1.01_main2_transcript.txt
```

A snapshot of the spreadsheet `p1.01_main1_transcript.xlsx` is below, showing the transcribed speech of the Commander and RN aligned to the DM text messages (Col. C - F). Each row is an utterance with a timestamp (Col. B), and is given a unique ID (Col. A).

<p align="center"><img src="media/transcript-example.png" width="750"></p>

A snapshot of the corresponding tab-delimited file `tab-delimited/p1.01_main1_transcript.txt` is below:

```
id  time     stream     text
0    0        CMD       "(calibrate)"
1    14.22    RN        "<no speech>"
2    20.36    DM->CMD   "calibration complete"
3    31.01    CMD       "i'm ready"
4    50.59    DM->CMD   "I'm also ready. Would you like me to send a picture 
                        so you can see the room?"
5    55.2     CMD       "send a picture"
6    61.63    DM->RN    "photo"
7    62.04    RN        "image sent"
...
```

Transcripts from Experiment 4 contain additional columns for the raw ASR results (Col. C) and intermediary normalized forms (Col. D), in addition to the final corrected utterance (Col. E). A snapshot of the spreadsheet `p4.p01_train_transcript.xlsx` is below:

<p align="center"><img src="media/transcript-exp4-example.png" width="850"></p>

The Commander text in the Experiment 4 tab-delimited files contains the corrected utterance (Col E.)

## iSCOUT

New files were created to supplement the transcripts with the images of SCOUT (iSCOUT), and are similarly supplied in two formats: an .xlsx spreadsheet and a .txt tab-delimited file. There is additionally a directory containing each image taken per trial. Commanders who completed all three trials (train, main1, main2) have the following iSCOUT files (Commander p1.01 shown below):

```
└─── data/iSCOUT/
     └─── p1.01_train_iscout.xlsx
     └─── p1.01_main1_iscout.xlsx
     └─── p1.01_main2_iscout.xlsx
     └─── tab-delimited/p1.01_train_iscout.txt
     └─── tab-delimited/p1.01_main1_iscout.txt
     └─── tab-delimited/p1.01_main2_iscout.txt
     └─── images/p1.01_train/
           └─── frame000.jpg
           └─── ...
           └─── frame012.jpg
     └─── images/p1.01_main1/
           └─── frame000.jpg
           └─── ...
           └─── frame021.jpg
     └─── images/p1.01_main2/
          └─── frame000.jpg
          └─── ...
          └─── frame035.jpg
```

Images are given their own row in the iscout spreadsheet with the ID prefix "i" and a unique three digit id cooresponding to the image filename. A snapshot of the spreadsheet `p1.01_main1_iscout.xlsx` is below. The image filename takes on the prefix "frame" followed by the three digit id. The image filenames appear in Col. G at the point in time the images were taken.

<p align="center"><img src="media/iscout.png" width="750"></p>

Clicking on the image name will open the image in a picture viewer on your machine. Below is `images/p1.01_main1/frame000.jpg`:

<p align="center"><img src="media/image-example.jpg" width="350"></p>

A snapshot of the corresponding tab-delimited file `tab-delimited/p1.01_train_iscout.txt` is below:

```
id  time     stream     text
0    0        CMD       "(calibrate)"
1    14.22    RN        "<no speech>"
2    20.36    DM->CMD   "calibration complete"
3    31.01    CMD       "i'm ready"
4    50.59    DM->CMD   "I'm also ready. Would you like me to send a picture 
                        so you can see the room?"
5    55.2     CMD       "send a picture"
6    61.63    DM->RN    "photo"
i000 63.63    IMAGE     "frame000"
7    62.04    RN        "image sent"
...
```


## maps

Snapshots of what the LIDAR map looked like at the end of each trial are included for a subset of the trials. Due to how the LIDAR and visualization functionality was implemented, some snapshots show a subset of the environment rather than the complete environment. Rendered maps of the complete environment are annotated for each trial, showing the objects of interest that were scanned by the LIDAR for that particular trial.

At this time, LIDAR and annotated maps are only available for Experiment 1. Commanders who completed all three trials (train, main1, main2) in Experiment 1 have the following transcript files (Commander p1.01 shown below):

```
└─── data/maps/
     └─── LIDAR/
          └─── p1.01_train_lidar.png
          └─── p1.01_main1_lidar.png
          └─── p1.01_main2_lidar.png
     └─── maps-marked/
          └─── p1.01_train_map.png
          └─── p1.01_main1_map.png
          └─── p1.01_main2_map.png
     └─── maps-text/
          └─── p1.01_train_map.txt
          └─── p1.01_main1_map.txt
          └─── p1.01_main2_map.txt
```

Below is the snapshot for a shoe-counting trial, showing doorways and shoes that were scanned in red, and doorways and shoes that were not scanned in dashed blue lines.

<p align="center"><img src="media/map-example.png" width="750"></p>

A text version of the annotated floor plan has been assembled where each target entity (e.g., doorway, shovel, etc.) was mapped to a unique identifier (e.g., 'door1') and denoted as scanned or not scanned (`data/maps/ids_main.png` and `data/maps/ids_train.png` show the mapping.) A snapshot from `maps-text/p1.01_main1_map.txt` is below:

```
door1	not-scanned
door2	not-scanned
door3	not-scanned
door4	not-scanned
door5	not-scanned
door6	scanned
...
```

Images of the fully annotated maps and legends are available in the following files
```
└─── data/maps/
     └─── legend-main.png
     └─── legend-trian.png
     └─── map-main.png
     └─── map-trian.png
```


## dialogue-structure

Dialogue Structure annotations have been conducted on every transcript, and are similarly supplied in two formats: an .xlsx spreadsheet and a .txt tab-delimited file. Commanders who completed all three trials (train, main1, main2) have the following annotated dialogue structures files (Commander p1.01 shown below):
```
└─── data/dialogue-structure/
     └─── p1.01_train_dialogue-structure.xlsx
     └─── p1.01_main1_dialogue-structure.xlsx
     └─── p1.01_main2_dialogue-structure.xlsx
     └─── tab-delimited/p1.01_train_dialogue-structure.txt
     └─── tab-delimited/p1.01_main1_dialogue-structure.txt
     └─── tab-delimited/p1.01_main2_dialogue-structure.txt
```

Annotations were conducted post-experimentation by duplicating the .xlsx transcript spreadsheet and adding extra columns. A snapshot of the spreadsheet `p1.01_main1_dialogue-structure.xlsx` is below. Transaction units are annotated in Col. G, Antecedents in Col. H, Relations in Col. I, and any contextual information required for understanding the annotation denoted in Col. J.

<p align="center"><img src="media/annotations.png" width="850"></p>

A snapshot of the corresponding tab-delimited file `p1.01_train_dialogue-structure.txt` is below:

```
ID.  time    stream   text                                             TU ant. relation
...
222  1054.31 CMD      "robot proceed through the doorway"              28 None None
223  1061.9  CMD      "turn a hundred and eighty degrees to the right" 28 222  continue
224  1063.78 CMD      "and take a picture"                             28 223  continue
225  1070.54 DM->CMD  "processing. . ."                                28 224* processing
226  1077.99 DM->CMD  "I see more than one doorway."                   28 222  missing-info
227  1079.46 DM->CMD  "The one to my left?"                            28 222  req-clar
228  1081.34 CMD      "the doorway to your left"                       28 227  clar-repair
...
```

## AMR

Abstract meaning representation (AMR) annotation has been conducted on a subset of sentences from Experiments 1--3. New files were created to supplement the transcripts with a column that indicates if the utterance has been annotated with AMR, and a hyperlink to an individual .txt file with the AMR annotations. Commanders who completed all three trials (train, main1, main2) have the following annotated spreadsheet files (Commander p1.09 shown below); however, only a subset of utterances have been annotated, and are listed in `data/AMR/StandardAMR/` and `data/AMR/DialogueAMR/`:

```
└─── data/AMR/
     └─── p1.09_train_AMR.xlsx
     └─── p1.09_main1_AMR.xlsx
     └─── p1.09_main2_AMR.xlsx
     └─── StandardAMR/
     	  └─── p1.09_main1_s92.txt
     	  └─── ...
     	  └─── p1.09_main1_s11.txt
     └─── DialogueAMR/
          └─── p1.09_main1_s92.txt
          └─── ...
          └─── p1.09_main1_s111.txt
     
```


A snapshot of the spreadsheet `p1.09_main1_AMR.xlsx` is below. The utterances with Standard-AMR and Dialogue-AMR are linked in Col. G and Col. H respectively. Clicking on the text opens the file with the annotation.

<p align="center"><img src="media/amr.png" width="850"></p>

Below is the contents of `Standard-AMR/p1.09_main1_s101.txt`:
```
p1.09_main1_s101
# ::tok executing ...
# ::snt executing...
(e / execute-02
	:ARG0 (i / i))

```

Below is the contents of `Dialogue-AMR/p1.09_main1_s101.txt`:
```
p1.09_main1_s101
# ::tok executing ...
# ::snt executing...
(a / assert-SA
	:ARG0 (r / robot-dm)
	:ARG1 (d / do-02
		:ARG0 r
		:complete -
		:ongoing +
		:time (n / now))
	:ARG2 (c / commander))
```

Additionally, all the Standard-AMR and Dialogue-AMR are compiled into two files: `Standard-AMR/Standard-AMR-All.txt` and `Dialogue-AMR/Dialogue-AMR-All.txt`


## Video-SCOUT

### Full Trial Videos and Subtitles

Full-length .mp4 videos from the robot’s front-facing camera were created for a subset of the trials. Accompanying each video is an .srt subtitle file containing the dialogue between the Commander and the Robot (Dialogue Manager). At this time, full trial videos with subtitles are only available for Experiments 1 and 2. Commanders who completed all three trials (train, main1, main2) have the following video and subtitle files (Commander p1.01 shown below):
```
└─── data/Video-SCOUT/video-trials/
     └─── p1.01_train_stream.mp4
     └─── p1.01_train_stream.srt
     └─── p1.01_main1_stream.mp4
     └─── p1.01_main1_stream.srt
     └─── p1.01_main2_stream.mp4
     └─── p1.01_main2_stream.srt
```

Each trial video runs the entire length of the trial, which was capped at 20 minutes. Some videos are longer due to technical difficulties. The iSCOUT images requested by the Commander are contained within the entirely of these videos. A sample clip from p1.01_main1.mp4 is shown below, displaying its respective subtitle file.

<p><video src="media/video-example.mp4" width="320" height="240" controls></video></p>

(If the video doesn't display, you can find it here: [https://gitlab.sitcore.net/bot-language/scout/-/blob/master/media/video-example.mp4](https://gitlab.sitcore.net/bot-language/scout/-/blob/master/media/video-example.mp4))

The subtitle files can be added as a subtitle track to the videos using media players, e.g., VLC. If opening the .mp4 in VLC, the subtitle track should load automatically if it is in the same directory as the .mp4.

Below is the start of `p1.01_main1_stream.srt`:

```
1
00:00:20.36 --> 00:00:25.36
Robot: "calibration complete"

2
00:00:31.01 --> 00:00:36.01
CMD: "i'm ready"

3
00:00:50.59 --> 00:00:55.59
Robot: "I'm also ready.  Would you like me to send a picture so you can see the room?"

4
00:00:55.20 --> 00:01:00.20
CMD: "send a picture"

5
00:01:02.93 --> 00:01:07.93
CMD: "do a three hundred and sixty degree spin"

6
00:01:05.17 --> 00:01:10.17
Robot: "sent"

...
```


### TU Videos and Subtitles

TU Videos were created by segmenting the trial video into clips containing the beginning and end of each TU. TU annotations and timestamps were obtained from the SCOUT dialogue structure spreadsheets. Each TU Video is a segment from the full video of the robot's front-facing camera, clipped to include a single TU. Accompanying each TU Video, is the clipped subtitle file containing the dialogue between the Commander and the Robot (Dialogue Manager) for that TU. The subtitle files can be added as a subtitle track to the videos using media players, e.g., VLC. If opening the .mp4 in VLC, the subtitle track should load automatically if it is in the same directory as the .mp4..

Commanders who completed all three trials (train, main1, main2) have the following video and subtitles files for each of their TUs (Commander p1.01 shown below):
```
└─── data/Video-SCOUT/video-tus/p1.01_main1/
     └─── p1.01_main1_TU1.mp4
     └─── p1.01_main1_TU1.srt
     └─── p1.01_main1_TU2.mp4
     └─── p1.01_main1_TU2.srt
     └─── ...
     └─── p1.01_main1_TU23.mp4
     └─── p1.01_main1_TU23.srt
```

The timestamp for the first utterance of each TU .srt file is 0:00:00 so it can play with the video clip. Below is `p1.01_main1_TU2.srt` in its entirety:

```
0
00:00:00.00 --> 00:00:05.00
CMD: "i'm ready"

1
00:00:19.58 --> 00:00:24.58
Robot: "I'm also ready.  Would you like me to send a picture so you can see the room?"

2
00:00:24.19 --> 00:00:29.19
CMD: "send a picture"

3
00:00:34.16 --> 00:00:39.16
Robot: "sent"
```

