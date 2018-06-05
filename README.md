# Project building a controller #

## Each CRITERIA ##

### 1. Implemented body rate control in C++. ###

I implemented function `BodyRateControl` in line (96 - 127) of `QuadControl.cpp`.

From pqr cmd and current pqr I computed error of pqr, and used it to calculate angular acceleration (multipled by kpPQR). Then i computed Moment cmd (angular acceleration multipled by I *Moment of Inertial*).

### 2. Implement roll pitch control in C++. ###

I implemented function `RollPitchControl` in line (130 - 168) of `QuadControl.cpp`.

I calculate Rotation matrix from attitude. And then i used two equation below to compute Pc and Qc:

`equation 1`

![equation1](./animations/rollpitch_equation1.png)

`equation 2`

![equation2](./animations/rollpitch_equation2.png)

But i can't understand where we have equation 2.

### 3. Implement altitude controller in C++. ###

1. I computed the Force in world-frame from error Z, erro Z dot, integratedAltitudeError, accelZCmd.
2. I add GRAVITY on it.
3. I divide it by R(2,2) of Rotation-Matrix to convert into body-frame. It's thrustcmd what we need.

### 4. Implement lateral position control in C++. ###

I computed accel-cmd from error (x,y), erro (x,y) dot, accelCmdFF (it's same altitude control).

### 5. Implement yaw control in C++. ###

I computed YawRateCmd only from error of yaw (YawCmd - Yaw).

### 6. Implement calculating the motor commands given commanded thrust and moments in C++. ###

1. From Pc, Qc, Rc, i computed p_dot_cmd, q_dot_cmd, r_dot_cmd.
2. Use equation below to calculate c_bar,p_bar,q_bar,r_bar. And then computed omegas.
 ![equation](./animations/omega_equation.png)
 
## Test scenarios. ##
 
`scenario2`
 
![scenario2](./animations/scenario2.gif)
![output](./animations/)

`scenario03`
 
![scenario3](./animations/scenario2.gif)
![output](./animations/)
 
`scenario04`

![scenario4](./animations/scenario4.gif)
![output](./animations/)
 
`scenario05`

![scenario5](./animations/scenario5.gif)
![output](./animations/)
 
 