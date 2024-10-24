#### Overview

This multi-session EEG dataset for studying human visual processing (datasetNAME) contains:

1. 122-channel EEG data collected on 29 participants during natural visual stimulation;
2. totally 90 sessions for 1.5 hours each;
3. each session consists of 4 RSVP runs and 4 low-speed presentation runs;
4. each participant completed between 1 to 5 sessions on different days, around one week apart.

More details about the dataset are described as follows.

#### Participants

32 participants were recruited from college students in Beijing, of which 4 were female, and 28 were male, with an age range of 21-33 years.
99 sessions were conducted, but 9 were corrupted, resulting in 29 subject remaining.
They were paid and gave written informed consent. 
The study was conducted under the approval of the XXXXXXXXXXXXXXXXXXX如：Institutional Review Board of Peking University. 

#### Experimental Procedures

1. RSVP experiment:
During the RSVP experiment, the participants were shown images at a rate of 5 Hz, and each run consisted of 2,000 trials. There were 20 image categories, with 100 images in each category, making up the 2,000 stimuli. The 100 images in each category were further divided into five image sequences, resulting in 100 image sequences per run. Each sequence was composed of 20 images from the same class, and the 100 sequences were presented in a pseudo-random order. 

After every 50 sequences, there was a break for the participants to rest. Each rapid serial sequence lasted approximately 7.5 seconds, starting with a 750ms blank screen with a white fixation cross, followed by 20 or 21 images presented at 5 Hz with a 50% duty cycle. The sequence ended with another 750ms blank screen. 

After the rapid serial sequence, there was a 2-second interval during which participants were instructed to blink and then report whether a special image appeared in the sequence using a keyboard. During each run, 20 sequences were randomly inserted with additional special images at random positions. 
The special images are logos for brain-computer interfaces.

2. Low-speed experiment:
During the low-speed experiment, each run consisted of 100 trials, with 1 second per image for a slower paradigm. The 100 stimuli were presented in a pseudo-random order and included 20 image categories, each containing 5 images. A break was given to the participants after every 20 images for them to rest.

Each image was displayed for 1 second and was followed by 11 choice boxes (1 correct class box, 9 random class boxes, and 1 reject box). Participants were required to select the correct class of the displayed image using a mouse to increase their engagement. After the selection, a white fixation cross was displayed for 1 second in the centre of the screen to remind participants to pay attention to the upcoming task.

#### Stimuli

The stimuli are from two image databases, ImageNet and PASCAL.
The final set consists of 10,000 images, with 500 images for each class.

#### Annotations

In the derivatives/annotations folder, there are additional information of datasetNAME:

1. Videos of two paradigms.
2. Dataset_info: Main features of datasetNAME.
3. Experiment_schedule: Schedule of each session. 
4. Stimuli_source: Source categories of ImageNet and PASCAL.
5. Subject_info: Age and sex of participants.
6. Task_event: The meaning of eventID.

#### Preprocessing

The EEG signals were pre-processed using the MNE package, version 1.3.1, with Python 3.9.16. 
The data was sampled at a rate of 250 Hz with a bandpass filter applied between 0.1 and 100 Hz. 
A notch filter was used to remove 50 Hz power frequency.
Epochs were created for each trial ranging from 0 to 500 ms relative to stimulus onset. 
No further preprocessing or artefact correction methods were applied in technical validation. However, researchers may want to consider widely used preprocessing steps such as baseline correction or eye movement correction. 
After the preprocessing, each session resulted in two matrices: RSVP EEG data matrix of shape (8,000 image conditions × 122 EEG channels × 125 EEG time points) and low-speed EEG data matrix of shape (400 image conditions × 122 EEG channels × 125 EEG time points).


