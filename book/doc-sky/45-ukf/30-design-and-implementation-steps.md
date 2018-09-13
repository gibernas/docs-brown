# Steps to Design and Implement a Kalman Filter on a Robot {#ukf-design-and-implementation-steps status=draft}

To apply a Kalman Filter (linear KF or UKF) to a specific robot, there are certain parts of the algorithm that we need to define.

1. **State Vector:** The first aspect of the KF design process specific to the robot application is the selection of state variables to track in the state vector.
2. **Motion Model:** The motion model of the robot demands careful thought when designing a KF, as it determines the state transition function.
3. **Measurement Model:** The robot's sensor suite plays a significant role in how the robot forms state estimates. Its sensors determine the measurement function.
4. **Process Noise and Measurement Covariance Matrices:** The process noise and measurement covariance matrices must be determined from the motion model and sensor suite, respectively.
5. **Initialization of the Filter:** The filter must have initial values on which to perform the predictions and measurement updates.
6. **Asynchronous Inputs:** Sometimes, the KF has to be adapted to handle asynchronous inputs from real-world sensors, whose data rates are not strictly fixed.
7. **Tuning and Testing:** Finally, once a filter is implemented, it is a good idea to tune and test it in simulation and then on the real robot, quantifying its performance if possible.

We will be going over these design decisions and implementation details step-by-step as you implement your filters in one and three spatial dimensions on the drone.