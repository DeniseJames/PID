Udacity PID Controller Project 4 – Term 2

1.	Describe the effect each of the P, I, D components had in your implementation.
The Proportional error component accounts for present values of the error. When the P-error is large and positive, the control output will also be large and positive.  Increasing Kp increases the speed of the PID control system.  Making Kp to large causes the car to go off the road.

The Integral error component accounts for all of the past values of the error.  It was determined that this component is not necessary in this project, making the PID a PD also.

The Derivative error component accounts for the probable future value of the error.   A larger value of Kd helps with fast turns on the track.


2.	Describe how the final hyperparameters were chosen.
After two weeks of learning how to use micro websockets for windows and visual studio 2017, I started with the well thought out parameters in the lecture, Kp = 0.2, Ki = 0.004, and Kd = 3.0.  I used the main.cpp initial throttle of 0.3 and the car runs okay on the track. There is a sinusoidal motion to the car.   I noticed that the Ki term is close to zero so next I set it to zero.  The simulator is no difference than using Ki= 0.004.  A PD controller is sufficient.  Ki = 0 for the rest of the manual tests.
Next I set the throttle to 0.5 for a higher speed.  The car cross over onto the red and white stripes in the simulator.  I will look for better Kp and Kd parameters at this speed.  I attempted to make Kp smaller from 0.2 to 0.1.  The car went off the road.  Making Kp so small I will not have a PD but just a D controller.  With (Kp = 1, Ki = 0.0, Kd = 30) the steering oscillates to max angle and negative max angle.  The final parameters used are Kp = 1, Ki = 0.0, Kd = 2.0.  A video of the simulation is found at this link https://youtu.be/WFKWUOEqhdE 

I ran many simulations on slightly increasing Kp and increasing Kd to arrive on this value with throttle = 0.5.  
