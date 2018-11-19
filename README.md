# AmbisonicsDRIR
SOFA Convention - Ambisonics Directional Room Impulse Response


## Description

Room Impulse Response (RIR) measurements are one of the most common ways to capture acoustic characteristics of a given space. When performed with microphone arrays, the RIRs inherently contain directional information. Due to the growing interest in Ambisonics and audio for Virtual Reality, new spherical microphone arrays recently hit the market. Accordingly, several databases of Directional RIRs (DRIRs) measured with such arrays, referred to as Ambisonics DRIRs, have been publicly released. However, there is no format consensus among databases. With the aim of improving interoperability, we propose an exchange format for Ambisonics DRIRs, as a new Spatially Oriented Format for Acoustics (SOFA) convention

For more information, check the article:
Pérez-López, A., & De Muynke, J. (2018, May). [Ambisonics Directional Room Impulse Response as a New Convention of the Spatially Oriented Format for Acoustics](https://zenodo.org/record/1299894). In Audio Engineering Society Convention 144. Audio Engineering Society.

## Version 0.2

_AmbisonicsDRIR_ convention is based on _GeneralFIRE_, with the following modifications:

+ Mandatory global attribute 'AmbisonicsOrder'
+ Mandatory Data.IR attributes 'ChannelOrdering' and 'Normalization'
+ ListenerUp and ListenerView are mandatory
+ SourceUp and SourceView are mandatory


| Name                          | Default | Flags | Dimensions | Type | Comment |
|-------------------------------|---------|-------|------------|------|---------|
| GLOBAL:Conventions            |         |       |            |      |         |
| GLOBAL:Version                |         |       |            |      |         |
| GLOBAL:SOFAConventions        |         |       |            |      |         |
| GLOBAL:SOFAConventionsVersion |         |       |            |      |         |
| GLOBAL:APIName                |         |       |            |      |         |
| GLOBAL:APIVersion             |         |       |            |      |         |
| GLOBAL:ApplicationName        |         |       |            |      |         |
| GLOBAL:ApplicationVersion     |         |       |            |      |         |
| GLOBAL:AuthorContact          |         |       |            |      |         |
| GLOBAL:Comment                |         |       |            |      |         |
| GLOBAL:DataType               |         |       |            |      |         |
| GLOBAL:History                |         |       |            |      |         |
| GLOBAL:License                |         |       |            |      |         |
| GLOBAL:Organization           |         |       |            |      |         |
| GLOBAL:References             |         |       |            |      |         |
| GLOBAL:RoomType               |         |       |            |      |         |
| GLOBAL:Origin                 |         |       |            |      |         |
| GLOBAL:DateCreated            |         |       |            |      |         |
| GLOBAL:DateModified           |         |       |            |      |         |
| GLOBAL:Title                  |         |       |            |      |         |
| ListenerPosition              |         |       |            |      |         |
| ListenerPosition:Type         |         |       |            |      |         |
| ListenerPosition:Units        |         |       |            |      |         |
| ReceiverPosition              |         |       |            |      |         |
| ReceiverPosition:Type         |         |       |            |      |         |
| ReceiverPosition:Units        |         |       |            |      |         |
| SourcePosition                |         |       |            |      |         |
| SourcePosition:Type           |         |       |            |      |         |
| SourcePosition:Units          |         |       |            |      |         |
| EmitterPosition               |         |       |            |      |         |
| EmitterPosition:Type          |         |       |            |      |         |
| EmitterPosition:Units         |         |       |            |      |         |
| Data.IR                       |         |       |            |      |         |
| Data.SamplingRate             |         |       |            |      |         |
| Data.SamplingRate:Units       |         |       |            |      |         |
| Data.Delay                    |         |       |            |      |         |
| GLOBAL:DatabaseName           |         |       |            |      |         |
| GLOBAL:ListenerShortName      |         |       |            |      |         |
| GLOBAL:ListenerDescription    |         |       |            |      |         |
| GLOBAL:SourceDescription      |         |       |            |      |         |
| GLOBAL:SourceManufacturer     |         |       |            |      |         |
| SourceManufacturer            |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |
|                               |         |       |            |      |         |



## Implementations

- [Matlab](https://github.com/jdemuynke/API_MO)
- [Python](https://github.com/andresperezlopez/pysofaconventions)
- [C++](https://github.com/andresperezlopez/API_Cpp)



