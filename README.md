## FTCVuforiaDemo

This linear opmode demonstrates one way to use Vuforia to track target images.
Place any of the four 2016/17 images on the field perimeter. 

1) Point the robot towards a target using the Gamepad Joysticks
2) Verify that the target information appears on the Driver Station
3) Hold the Left Bumper to track to the target
 
### All drive system components are located in the Robot_OmniDrive class.

The opmode assumes a three wheel omni-directional drive system, but it can be adapted to work with any omni drive (eg: mecanum).  
Robot motion is defined by three axes: Axial / Lateral/ Yaw.  
Actual motor speeds are calculated from these three axis motions.

### All navigation components are located in the Robot_Navigation class
 
A simplified tracking approach is used, whereby the robot can be made to approach to within a set distance of any visible target.  
Target localization is converted into a set of 6 values which can be used directly to navigate to the target.
  
robotX - Distance from target along X axis in mm. (will be negative)
robotY - Offset from target centerline along Y axis in mm. (can be + or -)
robotBearing - Direction Robot is pointing. (+ is CCW from x axis)
targetRange - Distance from robot centroid to target center in mm.
targetBearing - Direction from robot centroid to target center (+ is CCW from x axis)
relativeBearing - Angle from robot bearing to target bearing in degrees (+ is CCW)

A standoff TARGET_DISTANCE is defined in the TeleopOpMode to indicate how closely the robot should approach the target. 
The standdoff distance is measured from the center of the robot to the target in mm.

### Telemetry Display

Telemetry Data displays robot and target information whenever a target is "visible"
A sample display is shown here:

Visible     blue near
Robot       [X]:[Y] (B) [-400mm]:[-300mm] (12°)",
Target      [R] (B):(RB) [500mm] (-10f°):(22°)",
- Turn      <<< CCW 22°
- Strafe    LEFT 300mm
- Distance  400mm
Axes        A[0.23], L[-0.11], Y[-0.42]
Wheels      L[0.2], R[0.3], B[-0.31]

 
 




