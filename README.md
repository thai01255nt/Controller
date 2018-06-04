# Project building a controller #

## Each CRITERIA ##

### 1. Implemented body rate control in C++. ###

I implemented function `BodyRateControl` in line (96 - 127) of `QuadControl.cpp`.

From pqr cmd and current pqr I computed error of pqr, and used it to calculate angular acceleration (multipled by kpPQR). Then i computed Moment cmd (angular acceleration multipled by I *Moment of Inertial*).

### 2. Implement roll pitch control in C++. ###

I implemented function `RollPitchControl` in line (130 - 168) of `QuadControl.cpp`.

