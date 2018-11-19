# AmbisonicsDRIR
SOFA Convention - Ambisonics Directional Room Impulse Response


## Description

Room Impulse Response (RIR) measurements are one of the most common ways to capture acoustic characteristics of a given space. When performed with microphone arrays, the RIRs inherently contain directional information. Due to the growing interest in Ambisonics and audio for Virtual Reality, new spherical microphone arrays recently hit the market. Accordingly, several databases of Directional RIRs (DRIRs) measured with such arrays, referred to as Ambisonics DRIRs, have been publicly released. However, there is no format consensus among databases. With the aim of improving interoperability, we propose an exchange format for Ambisonics DRIRs, as a new Spatially Oriented Format for Acoustics (SOFA) convention

For more information, check the article:
Pérez-López, A., & De Muynke, J. (2018, May). [Ambisonics Directional Room Impulse Response as a New Convention of the Spatially Oriented Format for Acoustics](https://zenodo.org/record/1299894). In Audio Engineering Society Convention 144. Audio Engineering Society.

## Version 0.2

_AmbisonicsDRIR_ convention is based on _GeneralFIRE_, with the following modifications:

+ Global SOFAConventions attribute 'AmbisonicsDRIR'
+ Mandatory global attribute 'AmbisonicsOrder'
+ Mandatory Data.IR attributes 'ChannelOrdering' and 'Normalization'
+ ListenerUp and ListenerView are mandatory
+ SourceUp and SourceView are mandatory

Furthermore, the variable _Receiver_ makes reference to the virtual Ambisonics Microphones. In that sense,
no position information is needed, and the values of that field will be ommited.
Furthermore, the value of the dimension _R_ depends on the Ambisonics Order (_L_). 
The following expression should be met. _R_ = power(_L_ + _1_, _2_).


| Name                              | Default                                            | Flags | Dimensions | Type      | Comment                                                                                                                                                               |
|-----------------------------------|----------------------------------------------------|-------|------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GLOBAL:Conventions                | SOFA                                               | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:Version                    | 1.0                                                | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:SOFAConventions            | AmbisonicsDRIR                                     | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:SOFAConventionsVersion     | 0.2                                                | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:APIName                    |                                                    | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:APIVersion                 |                                                    | rm    |            | attribute |                                                                                                                                                                       |
| GLOBAL:ApplicationName            |                                                    |       |            | attribute |                                                                                                                                                                       |
| GLOBAL:ApplicationVersion         |                                                    |       |            | attribute |                                                                                                                                                                       |
| GLOBAL:AuthorContact              |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:Comment                    |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:DataType                   | FIRE                                               | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:History                    |                                                    |       |            | attribute |                                                                                                                                                                       |
| GLOBAL:License                    | No license provided, ask the author for permission | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:Organization               |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:References                 |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:RoomType                   | reverberant                                        | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:Origin                     |                                                    |       |            | attribute |                                                                                                                                                                       |
| GLOBAL:DateCreated                |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:DateModified               |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:Title                      |                                                    | m     |            | attribute |                                                                                                                                                                       |
| GLOBAL:AmbisonicsOrder            | 1                                                  | m     |            | attribute | Degree of the Spherical Harmonic Expansion.                                                                                                                           |
| GLOBAL:AmbisonicsMicrophoneModel  |                                                    |       |            |           | Information about microphone used for the recordings                                                                                                                  |
| GLOBAL:AmbisonicsConversionMethod |                                                    |       |            |           | Information about the Ambisonics transform prodecure                                                                                                                  |
| ListenerPosition                  | [0 0 0]                                            | m     | IC,MC      | double    | ListenerPosition describes the real position of the microphone in the room (useful if positioned off the center of the loudspeakers arrangement for example). M represents the number of positions of the Ambisonics microphone|
| ListenerPosition:Type             | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| ListenerPosition:Units            | meter                                              | m     |            | attribute |                                                                                                                                                                       |
| ListenerUp                        | [0 0 1]                                            | m     | IC,MC      | double    |                                                                                                                                                                       |
| ListenerUp:Type                   | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| ListenerUp:Units                  | meter                                              | m     |            | attribute |                                                                                                                                                                       |
| ListenerView                      | [1 0 0]                                            | m     | IC,MC      | double    |                                                                                                                                                                       |
| ListenerView:Type                 | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| ListenerView:Units                | meter                                              | m     |            | attribute |                                                                                                                                                                       |
| ReceiverPosition                  | [0 0 0]                                            | m     | rCI,rCM    | double    | Not applicable,(receivers are spherical harmonics)                                                                                                                    |
| ReceiverPosition:Type             | cartesian                                          | m     |            | attribute | Not applicable,(receivers are spherical harmonics)                                                                                                                    |
| ReceiverPosition:Units            | metre                                              | m     |            | attribute |  Not applicable,(receivers are spherical harmonics)                                                                                                                   |
| SourcePosition                    | [0 0 1]                                            | m     | IC,MC      | double    | By definition, there is only one source (loudspeaker array) with several loudspeakers (emitters). This variable controls the general offset of the loudspeaker array. |
| SourcePosition:Type               | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| SourcePosition:Units              | meter                              | m     |            | attribute |                                                                                                                                                                       |
| SourceUp                          | [0 0 1]                                            | m     | IC, MC     | double    |                                                                                                                                                                       |
| SourceUp:Type                     | meter                                              | m     |            | attribute |                                                                                                                                                                       |
| SourceUp:Units                    | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| SourceView                        | [1 0 0]                                            | m     | IC, MC     | double    |                                                                                                                                                                       |
| SourceView:Type                   | meter                                              | m     |            | attribute |                                                                                                                                                                       |
| SourceView:Units                  | cartesian                                          | m     |            | attribute |                                                                                                                                                                       |
| EmitterPosition                   | [0 0 0]                                            | m     | eCI, eCM   | double    | Each speaker position is represented as an emitter. Use EmitterPosition to represent the position of a particular speaker, wrt to SourcePosition which may contain the physical coordinates of the loudspeakers arrangement in the room. Size of EmitterPosition determines E.  M dimension not needed since there is always one only source (in this convention, M is not related to emitters but to receivers instead)|
| EmitterPosition:Type              | spherical                                          | m     |            | attribute |                                                                                                                                                                       |
| EmitterPosition:Units             | degree, degree, metre                              | m     |            | attribute |                                                                                                                                                                       |
| Data.IR                           | 0                                                  | m     | mREn       | double    |                                                                                                                                                                       |
| Data.IR:ChannelOrdering           | acn                                                | m     |            | attribute | Describes the ordering relationship between Spherical Harmonics. Must be one of: 'acn', 'sid' or 'fuma'                                                               |
| Data.IR:Normalization             | sn3d                                               | m     |            | attribute | Describes the amplitude relationship between Spherical Harmonics. Must be one of: 'sn3d' , 'n3d', 'fuma' or 'maxn'                                                    |
| Data.SamplingRate                 | 48000                                              | m     | I          | double    |                                                                                                                                                                       |
| Data.SamplingRate:Units           | hertz                                              | m     |            | attribute |                                                                                                                                                                       |
| Data.Delay                        | 0                                                  | m     | IRE,MRE    | double    | Additional delay of each Ambisonics IR (in samples)                                                                                                                   |


## Implementations

- [Matlab](https://github.com/jdemuynke/API_MO)
- [Python](https://github.com/andresperezlopez/pysofaconventions)
- [C++](https://github.com/andresperezlopez/API_Cpp)


## Reference files

[BINCI project](https://zenodo.org/record/1417727)


