#  ARL SCOUT: The Situated Corpus of Understanding Transactions

The Situated Corpus Of Understanding Transactions (SCOUT) is a multi-modal collection of human-robot dialogue in the task domain of collaborative exploration. The corpus was constructed from multi-phased Wizard-of-Oz experiments where human participants gave verbal instructions to a remotely-located robot to move and gather information about its surroundings. Each dialogue involved a human Commander, a Dialogue Manager (DM), and a Robot Navigator (RN), and took place in physical or simulated environments.

<p align="center"><img src="media/stats-poster.png" width="1000"></p>

SCOUT contains **Transcripts** of human-robot dialogues, aligned with the **Images** taken by the robot at the request of the Commander. The transcripts have been annotated with **Dialogue Structure**, including Transcaction Units (TUs), Antecedents, and Relations. A subset of utterances have been annotated with **Dialogue Semantics** including Standard-AMR and Dialogue-AMR. A subset of the **Maps** have been curated that depict the LIDAR Maps at the end of the dialogue and have been annotated as Exploration Maps.


## Contents
- [Experimental Design](#experimental-design)
- [SCOUT Contents](#scout-contents)
- [Citation](#citation)
- [Publications Using SCOUT](#publications-using-scout)
- [License](#license)

## Experimental Design

Our human-robot collaboration exercise is an exploration-and-search task in which human participants (who assume the role of 'Commander') work with their remotely-located robot teammate to explore an unknown area under low-bandwidth conditions--a situation representative of various inhospitable remote environments. This constraint prevents live-video streaming of the robot's perspective to the human or remote teleoperation of the robot.

In the first three experiments, robot control was conducted through “Wizard-of-Oz” (WoZ) methodology. One Wizard handled the robot's dialogue understanding and processing capabilities as the Dialogue Manager (DM) Wizard, and the other handled the robot's movement as the Robot Navigator (RN) Wizard.

<p align="center"><img src="media/bl-method.png" width="550"></p>

The DM-Wizard listened to the participant's speech and generated text-based responses and resolved miscommunication in what is called the left conversational floor. Once the DM-Wizard deemed a participant's instruction was well-formed, the DM-Wizard translated the instruction into a more rigid natural language instruction and passed it to the RN-Wizard to execute. This took place in the right conversational floor, where only the DM-Wizard and RN-Wizard communicated. The RN-Wizard informed the DM-Wizard through spoken language to indicate completion or complication in executing an instruction; the DM-Wizard in turn informed the participant of this completion or complication via text.

<p align="center"><img src="media/WoZ.png" width="550"></p>

The roles of dialogue manager and robot navigator changed over the course of the experimentation, from Wizard-of-Oz confederates to fully automated systems building upon the prior experimental findings.

| | Experiment 1 | Experiment 2 | Experiment 3 | Experiment 4 |
|---|---|---|---|---|
| Dialogue Processing | wizard + keyboard | wizard + button GUI | wizard + button GUI | ASR + auto-DM |
| Robot Behaviors | wizard + joystick | wizard + joystick | wizard + joystick | wizard + joystick | 
| Robot & Environment | physical | physical | virtual | virtual |

Commanders were given three resources: a robot, a map, and photographs. The robot, a Clearpath Jackal, was located in a remote environment, and it could understand spoken, natural language instructions from the participant (via the DM and RN). The verbal instructions were issued to the robot through a push-to-talk interface, and the robot responded through text messages. The map was a 2D, birds-eye view LIDAR map of the environment, which dynamically updated as the robot moved through the space. The photos were taken from the robot's front-facing RGB camera, showing the view directly in front of it. Below is a screenshot of the view seen by the human Commander.

<p align="center"><img src="media/scout-setup.png" width="600"></p>


## SCOUT Contents

Unique Commanders (human participants) are named as `p{exp}.{ID}` where `{exp}` is the experiment number (1-4) and `{ID}` is the Commander's ID assigned within that experiment. For example, the Commander `p1.01` is the first Commander in Experiment 1. Each Commander completed three trials {train, main1, main2}. The `data/main_trial_distribution.xlsx` file notes which counting task was completed in each main trial.

The data and annotation files are divided by type over five directories with the `data/` directory of this repository:

- [Transcripts](https://github.com/USArmyResearchLab/ARL-SCOUT/tree/main/scout_contents.md#transcripts)
- [iSCOUT (images)](https://github.com/USArmyResearchLab/ARL-SCOUT/tree/main/scout_contents.md#iscout)
- [Maps](https://github.com/USArmyResearchLab/ARL-SCOUT/tree/main/scout_contents.md#maps)
- [Dialogue Structure](https://github.com/USArmyResearchLab/ARL-SCOUT/tree/main/scout_contents.md#dialogue-structure)
- [AMR (Dialogue Semantics)](https://github.com/USArmyResearchLab/ARL-SCOUT/tree/main/scout_contents.md#amr)

Clicking on each of the links above will redirect you to a detailed overview of the data nomenclature, structure, and format.

## Citation

Please cite the following paper to reference the SCOUT data release ([link to pdf paper](https://aclanthology.org/2024.lrec-main.1259.pdf)):

```
@inproceedings{lukin2024scout,
    title = {{SCOUT: A Situated and Multi-Modal Human-Robot Dialogue Corpus}},
    booktitle = {{The Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING)}},
    author = {Lukin, Stephanie M., and Bonial, Claire N. and Marge, Matthew and Hudson, Taylor and Hayes, Cory J. and Pollard, Kimberly A. and Baker, Anthony and Foots, Ashley and Artstein, Ron and Gervits, Felix and Abrams, Mitchell and Henry, Cassidy and Donatelli, Lucia and Leuski, Anton and Hill, Susan G. and Traum, David and Voss, Clare R.},
    year = {2024}
}
```


## Publications Using SCOUT

SCOUT has been used in a number of publications and research areas. 

- Bonial, Claire*, Stephanie M. Lukin*, Mitchell Abrams, Anthony Baker, Lucia Donatelli, Ashley Foots, Cory J. Hayes, Cassidy Henry, Taylor Hudson, Matthew Marge, Kimberly A. Pollard, Ron Artstein, David Traum, Clare R. Voss. [📎 "Human-Robot Dialogue Annotation for Multi-Modal Common Ground."](https://arxiv.org/pdf/2411.12829) Journal on Language Resources and Evaluation (LREV). 2024.

**Dialogue Structure**

- Bonial, Claire, Taylor Hudson, Anthony L. Baker, Stephanie M. Lukin, and David Traum [📎 "Making Sense of Stop."](https://www.areaworkshop.org/wp-content/uploads/2022/07/Bonial-etal-2022.pdf) Annotation, Recognition and Evaluation of Actions Workshop. 2022.

- Bonial, Claire, Mitchell Abrams, Anthony L. Baker, Taylor Hudson, Stephanie M. Lukin, David Traum, and Clare R. Voss. [📎 "Context Is Key: Annotating Situated Dialogue Relations in Multi-floor Dialogue."](http://semdial.org/anthology/Z21-Bonial_semdial_0006.pdf) In Proceedings of the 25th Workshop on the Semantics and Pragmatics of Dialogue. 2021.

- Traum, David, Cassidy Henry, Stephanie Lukin, Ron Artstein, Felix Gervits, Kimberly A. Pollard, Claire Bonial, Su Lei, Clare Voss, Matthew Marge, Cory J. Hayes, Susan G. Hill. [📎 "Dialogue structure annotation for multifloor interaction."](https://aclanthology.org/L18-1017.pdf) Proceedings of the Eleventh International Conference on Language Resources and Evaluation; European Language Resources Association (LREC). 2018.

- Bonial, Claire, Stephanie M. Lukin, Ashley Foots, Cassidy Henry, Matthew Marge, Kimberly A. Pollard, Ron Artstein, David Traum, and Clare Voss. [📎 "Human-robot dialogue and collaboration in search and navigation."](https://pure.rug.nl/ws/portalfiles/portal/65256401/book_of_proceedings.pdf#page=14) Annotation, Recognition and Evaluation of Actions 28 (2018): 6.

**Abstract Meaning Representation**

- Bonial, Claire, Lucia Donatelli, Mitchell Abrams, Stephanie M. Lukin, Stephen Tratz, Matthew Marge, Ron Artstein, David Traum, and Clare Voss. [📎 "Dialogue-AMR: Abstract Meaning Representation for Dialogue."](https://aclanthology.org/2020.lrec-1.86.pdf) In Proceedings of the Twelfth Language Resources and Evaluation Conference. 2020.


**Participant Analysis**

- Lukin, Stephanie M., Kimberly A. Pollard, Claire Bonial, Taylor Hudson, Ron Artstein,  Clare Voss,  David Traum. [📎 "Navigating to Success in Multi-Modal Human-Robot Collaboration."](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10309403) IEEE International Symposium on Robot and Human Interactive Communication (RO-MAN). 2023.

- Pollard, Kimberly A., Stephanie M. Lukin, Matthew Marge, Ashley Foots, and Susan G. Hill. [📎 "How we talk with robots: Eliciting minimally-constrained speech to build natural language interfaces and capabilities."](https://journals.sagepub.com/doi/pdf/10.1177/1541931218621037) In Proceedings of the Human Factors and Ergonomics Society Annual Meeting, vol. 62, no. 1, pp. 160-164. Sage CA: Los Angeles, CA: SAGE Publications, 2018.

- Lukin, Stephanie, Kimberly Pollard, Claire Bonial, Matthew Marge, Cassidy Henry, Ron Artstein, David Traum, and Clare Voss. [📎 "Consequences and Factors of Stylistic Differences in Human-Robot Dialogue."](https://aclanthology.org/W18-5012.pdf) In Proceedings of the 19th Annual SIGdial Meeting on Discourse and Dialogue, pp. 110-118. 2018.


**Demonstrations**

- Marge, Matthew, Stephen Nogar, Cory J. Hayes, Stephanie M. Lukin, Jesse Bloecker, Eric Holder, and Clare Voss. [📎 "A Research Platform for Multi-Robot Dialogue with Humans."](https://aclanthology.org/N19-4.pdf#page=144) NAACL HLT 2019 (2019): 132.

- Lukin, Stephanie, Felix Gervits, Cory Hayes, Pooja Moolchandani, Anton Leuski, John G. Rogers III, Carlos Sanchez Amaro, Matthew Marge, Clare Voss, and David Traum. [📎 "ScoutBot: A Dialogue System for Collaborative Navigation."](https://aclanthology.org/P18-4016.pdf) In Proceedings of ACL 2018, System Demonstrations, pp. 93-98. 2018.

**Experimental Design**

- Marge, Matthew, Claire Bonial, Stephanie Lukin, and Clare Voss. [📎 "Bot Language (Summary Technical Report, Oct 2016--Sep 2021)."](https://apps.dtic.mil/sti/trecms/pdf/AD1194759.pdf) DEVCOM Army Research Laboratory. 2023.

- Marge, Matthew, Claire Bonial, Stephanie Lukin, Cory Hayes, Ashley Foots, Ron Artstein, Cassidy Henry, Kimberly Pollard, Carla Gordon, Felix Gervits, Anton Leuski, Susan Hill, Clare Voss, David Traum. [📎 "Balancing efficiency and coverage in human-robot dialogue collection."](https://arxiv.org/abs/1810.02017) arXiv preprint arXiv:1810.02017 (2018).

- Bonial, Claire, Matthew Marge, Ashley Foots, Felix Gervits, Cory J. Hayes, Cassidy Henry, Susan G. Hill et al. [📎 "Laying down the yellow brick road: Development of a wizard-of-oz interface for collecting human-robot dialogue."](https://arxiv.org/abs/1710.06406) AAAI Fall Symposium. 2017.

- Marge, Matthew, Claire Bonial, Brendan Byrne, Taylor Cassidy, A William Evans, Susan G. Hill, and Clare Voss. [📎 "Applying the Wizard-Of-Oz Technique to Multimodal Human-Robot Dialogue."](https://arxiv.org/pdf/1703.03714.pdf) IEEE International Symposium on Robot and Human Interactive Communication (RO-MAN). 2016.



## License

ARL SCOUT is licensed under the Creative Commons Zero 1.0 Universal (CC0 1.0) license. Please see [LICENSE](license) for details.

