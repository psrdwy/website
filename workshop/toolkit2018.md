---
layout: default
---

# Advanced MEG/EEG toolkit at the Donders


On 9-13 April 2018 we will host the “Advanced MEG/EEG toolkit” at the Donders Institute in Nijmegen.

This intense 5-day toolkit course will teach you advanced MEG and EEG data analysis skills. Preprocessing, frequency analysis, source reconstruction, connectivity and various statistical methods will be covered. The toolkit will consist of a number of lectures, followed by hands-on sessions in which you will be tutored through the complete analysis of MEG and EEG data sets, and there will also be plenty of opportunity to interact and ask questions to us about your research and data. On the final day you will have the opportunity to work on your own dataset under supervision of the tutors.

Organizer: Robert Oostenveld, with the help of many colleagues.
 
## Detailed Program


### Monday April 9, 2018


 | 09:00-09:30 | Registration, handouts and coffee                                                                            |           
 | ----------- | ---------------------------------                                                                            |           
 | 09:30-09:45 | Welcome                                                                                                      |           
 | 09:45-10:45 | Introduction to EEG/MEG and introduction to the FieldTrip toolbox ({{ :workshop:toolkit2018_introduction.pdf | Lecture}}) | 
 | 10:45-11:00 | Coffee Break                                                                                                 |           
 | 11:00-12:00 | Data acquisition demonstration in the EEG and MEG labs                                                       |           
 | 12:00-13:00 | Lunch                                                                                                        |           
 | 13:00-15:00 | Pre-processing ([Hands-on](/tutorial/eventrelatedaveraging))                                                 |           
 | 15:00-15:15 | Tea Break                                                                                                    |           
 | 15:15-16:30 | Time frequency analysis of power ({{ :workshop:toolkit2018_frequency.pdf                                     | Lecture}}) | 
 | 16:30-17:15 | Wrap-up-the-day: special topics, general questions and answers                                               |           

### Tuesday April 10, 2018

 | 09:00-11:00                              | Time-frequency analysis of power ([Hands-on](/tutorial/timefrequencyanalysis)) |           
 | -----------                              | ------------------------------------------------------------------------------ |           
 | 11:00-11:15                              | Coffee Break                                                                   |           
 | 11:15-12:15                              | Spontaneous EEG and sleep ({{ :workshop:toolkit2018_sleep.pdf                  | Lecture}}) | 
 | 12:15-13:15                              | Lunch                                                                          |           
 | 13:15-15:15                              | Analysis of continuous EEG data ([Hands-on](/tutorial/sleep))                  |           
 | 15:15-15:30                              | Tea break                                                                      |           
 | 15:30-16:30                              | Forward and inverse ({{ :workshop:toolkit2018_forward_inverse.pdf              | Lecture}}) | 
 | 16:30-17:15                              | Wrap-up-the-day: special topics, general questions and answers                 |           
 |                                          |                                                                                |           
 | 18:30-22:00	Drinks & dinner at Mi Barrio |                                                                               


### Wednesday April 11, 2018

 
 | 09:00-10:00 | Connectivity analysis in MEG and EEG data ({{ :workshop:toolkit2018_connectivity.pdf   | Lecture}}) | 
 | ----------- | ------------------------------------------------------------------------------------   | ---------- | 
 | 10:00-10:45 | Analysis of sensor- and source-level connectivity ([Hands-on](/tutorial/connectivity)) |           
 | 10:45-11:00 | Coffee Break                                                                           |           
 | 11:00-12:15 | Analysis of sensor- and source-level connectivity ([Hands-on](/tutorial/connectivity)) |           
 | 12:15-13:00 | Lunch                                                                                  |           
 | 13:00-14:15 | Source reconstruction using beamformers ({{ :workshop:toolkit2018_beamforming.pdf      | Lecture}}) | 
 | 14:15-15:00 | Beamforming ([Hands-on](/tutorial/beamformer))                                         |           
 | 15:00-15:15 | Tea Break                                                                              |           
 | 15:30-16:30 | Beamforming ([Hands-on](/tutorial/beamformer))                                         |           
 | 16:30-17:15 | Wrap-up-the-day: special topics, general questions and answers                         |           

### Thursday April 12, 2018

 | 09:00-10:30 | Statistics using non-parametric randomization techniques ({{ :workshop:toolkit2018_statistics.pdf             | Lecture}})          | 
 | ----------- | -------------------------------------------------------------------------------------------------             | ----------          | 
 | 10:30-10:45 | Coffee break                                                                                                  |                    
 | 10:45-12:00 | Statistics using non-parametric randomization techniques ([Hands-on](/tutorial/cluster_permutation_timelock)) |                    
 | 12:00-13:00 | Lunch                                                                                                         |                    
 | 13:00-14:00 | Statistics using non-parametric randomization techniques ([Hands-on](/tutorial/cluster_permutation_timelock)) |                    
 | 14:00-15:00 | Large scale analyses and open science ({{ :workshop:toolkit2018_open_science.pdf                              | Lecture and demo}}) | 
 | 15:00-15:15 | Tea break                                                                                                     |                    
 | 15:15-17:15 | FieldTrip playground part 1                                                                                   |                    
 | 17:15-18:00 | Wrap-up-the-day: special topics, general questions and answers                                                |                    
 |             |                                                                                                               |                    
 | 18:00-23:00 | Pizza, drinks, joint projects and hacking (optional)                                                          |                    
### Friday April 13, 2018

 | 09:30-12:00 | FieldTrip playground part 2         | 
 | ----------- | ---------------------------         | 
 | 12:00-13:00 | Lunch                               | 
 | 13:00-14:30 | FieldTrip playground part 3         | 
 | 14:30-14:45 | Tea break, testimonials, evaluation | 

## Getting started with the hands-on sessions

For the hands-on sessions we will use MATLAB R2016b, which you can start from the Desktop shortcut. To ensure that everything runs smooth, we will work with a clean and well-tested version of FieldTrip that we have installed on all computers and that we will bring on on a USB stick. Importantly, the tutorial data does not have to be downloaded but will also be distributed on the computers and available on the USB stick.

`<note warning>`
Please do not use another MATLAB version than 2016b. It should be available on all hands-on computers.
`</note>`

A recent copy of FieldTrip and the data have been preinstalled on the computer and you do not have to download anything. Also, it should NOT be necessary to execute the following lines of code. These are only needed if you DO NOT start the MATLAB from the Desktop shortcut. In other words, you will probably always want to start MATLAB from the Desktop shortcut.

    restoredefaultpath
    addpath("H:\common\matlab\fieldtrip")
    ft_defaults
    
    cd D:\toolkit2018


The restoredefaultpath command clears your path, keeping only the
official MATLAB toolboxes. The addpath statement adds the
present working directory, i.e. the directory containing the fieldtrip
main functions. The ft_defaults command ensures that all required
subdirectories are added to the path.

`<note warning>`
In general, please do NOT use the graphical path management tool from MATLAB. In this hands-on session we'll manage the path from the command line, but in general you are much better off using the startup.m file than the path GUI.

Furthermore, please do NOT add fieldtrip with all subdirectories, subdirectories will be added automatically when needed, and only when needed (see this [FAQ](/faq/should_i_add_fieldtrip_with_all_subdirectories_to_my_matlab_path)).
`</note>`