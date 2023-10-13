# LBL-AQUALOC-Dataset
The LBL-AQUALOC-Dataset includes measurements from LBL, a mono camera, a PS, and a low-cost MEMS-IMU.

The public underwater dataset AQUALOC collected ten sequence data in the scene of underwater archaeological sites. To address the lack of LBL data, we constructed a new dataset, LBL-AQUALOC, using a semi-physical simulation. This new dataset includes measurements from LBL, a mono camera, a PS, and a low-cost MEMS-IMU,  packaged in Rosbag format.

## 1.Underwater Visual-Inertial Data:

The sequences of the archaeological sites were captured in the Mediterranean Sea near Corsica. In total, 10 sequences were documented, with 3 from the first site and 7 from the second. The first site was approximately 270 meters deep and had remnants of an old shipwreck. The second site was around 380 meters deep. As shown in Fig.  \ref{ROV underwater challenging environment }, the underwater archaeological environment has characteristics such as low light, weak texture, repetitive texture, dynamic object interference, as well as turbidity caused by seabed sediment, and interference caused by the movement of mechanical arms. In such environment, visual information faces significant challenges. 
![uw_sensor1](https://github.com/SYSU-CPNTLab/LBL-AQUALOC-Dataset/assets/74598384/a608253c-2f64-4040-b75e-270ccfc7deda)
Fig. 1 (a) Data acquisition equipment ROV. And underwater challenging environment, (b) low light, (c) archaeological sites, (d) texture repetitive, (e) robotic arm, (f) sandy cloud, (g) dynamic object. Reproduced with permission of \cite{ferrera2019aqualoc}, Copyright © 2019, © SAGE Publications

## 2.Simulation of LBL Measurements:

The trajectory obtained from Colmap is used as the ground truth of the AUV motion trajectory. We further simulate the position of the acoustic buoy, the sound speed profile file (assuming that the sound speed changes uniformly with depth), and the time of arrival (TOA) at each moment (adding measurement deviation to TOA). The final simulated LBL measurements include the buoy number, buoy position information, arrival time, and average sound speed obtained by the AUV at each moment. These acoustic measurements are time-synchronized with visual-inertial measurements. Through LBL measurements, we can calculate the acoustic positioning accuracy results at the centimeter level, as well as the corresponding slant-range information.

![auv](https://github.com/SYSU-CPNTLab/LBL-AQUALOC-Dataset/assets/74598384/dc754d58-46a4-48cf-bab9-1aa774418dd7)
Fig. 2 Application scenarios of Acoustic-VINS and sensors related to positioning and perception.

## 3. Dataset Details
The dataset is released in the form of rosbag and currently there are 10 rosbags available:

| name | duration | size |
| :--: | :------: | :--: |
| LBL_AQUALOC_sequence_1.bag | 14'39" | 10.5GB |
| LBL_AQUALOC_sequence_2.bag | 7'29" | 5.4GB |
| LBL_AQUALOC_sequence_3.bag | 5'16" | 3.8GB |
| LBL_AQUALOC_sequence_4.bag | 11'09" | 8.0GB |
| LBL_AQUALOC_sequence_5.bag | 3'19" | 2.4GB |
| LBL_AQUALOC_sequence_6.bag | 2'49" | 2.0GB |
| LBL_AQUALOC_sequence_7.bag | 9'29" | 6.8GB |
| LBL_AQUALOC_sequence_8.bag | 7'49" | 5.6GB |
| LBL_AQUALOC_sequence_9.bag | 5'49" | 4.2GB |
| LBL_AQUALOC_sequence_10.bag | 11'54" | 8.5GB |


The data items within the rosbag are listed below:
| topic | type | frequency | description |
| :---: | :--: | :-------: | :---------: |
| /cam0/image_raw | sensor_msgs/Image | 20Hz | right camera |
| /cam1/image_raw | sensor_msgs/Image | 20Hz | left camera |
| /imu0 | sensor_msgs/Imu | 200Hz | IMU |
| /external_trigger | gvins/LocalSensorExternalTrigger | - | publish when VI-Sensor is trigger. 
| /ublox_driver/receiver_lla | sensor_msgs/NavSatFix | 10Hz | Receiver's GNSS solution (brief). |
| /ublox_driver/receiver_pvt | gnss_comm/GnssPVTSolnMsg | 10Hz | Receiver's GNSS solution (verbose). [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/GnssPVTSolnMsg.msg) |
| /ublox_driver/range_meas | gnss_comm/GnssMeasMsg | 10Hz | GNSS raw measurement. [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/GnssMeasMsg.msg) | 
| /ublox_driver/ephem | gnss_comm/GnssEphemMsg | - | The broadcast ephemeris of GPS, Galileo and BeiDou. [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/GnssEphemMsg.msg) |
| /ublox_driver/glo_ephem | gnss_comm/GnssGloEphemMsg | - | The broadcast ephemeris of GLONASS. [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/GnssGloEphemMsg.msg) | 
| /ublox_driver/iono_params | gnss_comm/StampedFloat64Array | - | The broadcast ionospheric parameters. [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/StampedFloat64Array.msg) | 
| /ublox_driver/time_pulse_info | gnss_comm/GnssTimePulseInfoMsg | 1Hz | The time information of next PPS signal. [definition](https://github.com/HKUST-Aerial-Robotics/gnss_comm/blob/main/msg/GnssTimePulseInfoMsg.msg).


## 4.Download link
LBL-AQUALOC-Dataset download link: coming soon.

