# Assignment 1 (Flying Robots, 2025/2026)

The goal of this assignment is to build a dynamics simulator for the Bitcraze Crazyflie 2.1 robot. This simulator will be extended in the upcoming assignments to test controls, state estimation, and motion planning.

## Requirements

- Do not use any external libraries or std for the core code (for visualization, debugging, verification you can of course use what you want). (Reason: We will need to run parts of the code on-board the STM32 later.)
- For rotations, use quaternions.
- Write your code modular, i.e., have at least one module for the mathematical operations that you need, and one for the multirotor dynamics.
- Use operator overloading for your math primitives.
- Use SI units throughout.

## Deliverables (by Nov 14, 10am)

1. Your code.
    - if you use github, add "whoenig" and "OmarMElsayed"
    - if you use TUB gitlab, add "whoenig" and "omarelsayed" with at least the Reporter role

2. A comparison/validation of the dynamics using the provided synthetic dataset. To this end, plot the position error, velocity error, rotation error, angular velocity error for the full trajectory.
3. A comparison/validation of your implemented dynamics with the provided real-world flight data. To this end, plot the position error, velocity error, rotation error, angular velocity error over k=1...10, where k is the number of consecutive time-steps.
4. A table or plot that demonstrates the trade-off simulation runtime vs. step-size vs. simulation quality for two of the following:
    a) Pure Euler integration,
    b) Pure RK4 integration,
    c) Exponential map for quaternion integration, Euler otherwise
    d) Exponential map for quaternion integration, RK4 otherwise

(Grading will happen during the discussion session.)

## Useful Information

### Parameters for synthetic_flight_data_known_params.csv

- mass: 25g
- inertia: diag([15e-6, 15e-6, 30e-6])
- arm length: 5cm
- kappa_f: 1e-10
- kappa_tau: 1e-12

### Parameters for synthetic_flight_data.csv

- mass: 34.0g
- magnitude kappa_f: 1e-10
- magnitude kappa_tau: 1e-12
- rest to be determined as part of the assignment based on datasheets

### Parameters for real_flight_data.csv

- mass: 34.7g
- rest to be determined as part of the assignment based on datasheets

## Recommended Resources

- Class material (slides, demo code)
- Quaternion math:
    - https://imrclab.github.io/kidyco/so3.html
    - https://users.aalto.fi/~ssarkka/pub/quat.pdf
    - https://faculty.sites.iastate.edu/jia/files/inline-files/quaternion.pdf
    - https://www.ashwinnarayan.com/post/how-to-integrate-quaternions/
- Multirotor specifications:
    - https://www.bitcraze.io/documentation/hardware/crazyflie_2_1/crazyflie_2_1-datasheet.pdf
    - https://www.research-collection.ethz.ch/handle/20.500.11850/214143
    - https://www.bitcraze.io/documentation/repository/crazyflie-firmware/master/functional-areas/pwm-to-thrust/
