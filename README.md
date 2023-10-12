# LBL-AQUALOC-Dataset
The LBL-AQUALOC-Dataset includes measurements from LBL, a mono camera, a PS, and a low-cost MEMS-IMU.

The public underwater dataset AQUALOC collected ten sequence data in the scene of underwater archaeological sites. To address the lack of LBL data, we constructed a new dataset, LBL-AQUALOC, using a semi-physical simulation. This new dataset includes measurements from LBL, a mono camera, a PS, and a low-cost MEMS-IMU,  packaged in Rosbag format.

Underwater Visual-Inertial Data:

The sequences of the archaeological sites were captured in the Mediterranean Sea near Corsica. In total, 10 sequences were documented, with 3 from the first site and 7 from the second. The first site was approximately 270 meters deep and had remnants of an old shipwreck. The second site was around 380 meters deep. As shown in Fig.  \ref{ROV underwater challenging environment }, the underwater archaeological environment has characteristics such as low light, weak texture, repetitive texture, dynamic object interference, as well as turbidity caused by seabed sediment, and interference caused by the movement of mechanical arms. In such environment, visual information faces significant challenges. 
![uw_sensor1](https://github.com/SYSU-CPNTLab/LBL-AQUALOC-Dataset/assets/74598384/a608253c-2f64-4040-b75e-270ccfc7deda)
Fig. 1 (a) Data acquisition equipment ROV. And underwater challenging environment, (b) low light, (c) archaeological sites, (d) texture repetitive, (e) robotic arm, (f) sandy cloud, (g) dynamic object. Reproduced with permission of \cite{ferrera2019aqualoc}, Copyright © 2019, © SAGE Publications

Simulation of LBL Measurements:

The trajectory obtained from Colmap is used as the ground truth of the AUV motion trajectory. We further simulate the position of the acoustic buoy, the sound speed profile file (assuming that the sound speed changes uniformly with depth), and the time of arrival (TOA) at each moment (adding measurement deviation to TOA). The final simulated LBL measurements include the buoy number, buoy position information, arrival time, and average sound speed obtained by the AUV at each moment. These acoustic measurements are time-synchronized with visual-inertial measurements. Through LBL measurements, we can calculate the acoustic positioning accuracy results at the centimeter level, as well as the corresponding slant-range information.

![image](https://github.com/SYSU-CPNTLab/LBL-AQUALOC-Dataset/assets/74598384/ab781c1e-11ab-4ecb-8301-8121cb1e24da)


LBL-AQUALOC-Dataset download link: coming soon.

