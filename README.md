# Udacity-Path-Planning

CarND-Path-Planning-Project

Goal: Design a smooth path planner which safely can drive in a 3 lanes highway without colliding with other cars; 
and in the same time passing slower vehicle by smooth manuvering through lane change. 

Available Data: Car's localization
                Sensor fusion data
                
Given Values/ Initialization: 
  Speed (Max):  50 MPH; Actual: 49.5 MPH
  Acceleration (Max): 10 m/s^2
  Jerk (Max): 10 m/s^3
  Lane Width: 4
  m/s to MPH conversion factor: 2.24
  Message refresh rate: 0.02s
  Waypoint step grid: 30m
  Incremental speed per step: 0.224
  Vehicle prefferred lane: 1(Middle)
  Vehicle left lane:  0
  Vehicle right lane: 2
  
  
Implementation:
  Sesnsor data received relative to our vehicle in each iteration helps in generating the true speed and future speed of the other vehicles. 
  Depending on these values, if our vehicle is within 30m from the front vehicle, too_close flag is true. If other vehicles are also in that margin, 
  then left_close or right_close flag is true. If our vehicle, experiences another vehicle ahead and is withinn the margin, then it changes lane to left or right, provided they are safe and allowed; else it will slow down its speed. 
  If our vehicle is moving in left or right lanes and there are no obstructions, it will come back to centre lane(prefferred lane).
  For smooth lane change or trajectory generation (also driving within lane) is possible via spline library.
  
