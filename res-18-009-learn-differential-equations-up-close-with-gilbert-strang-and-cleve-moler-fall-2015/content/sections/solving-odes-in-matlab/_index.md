---
uid: 8ee92c27f02bfd86d2629f4ce23755ef
title: Solving ODEs in MATLAB
course_id: >-
  res-18-009-learn-differential-equations-up-close-with-gilbert-strang-and-cleve-moler-fall-2015
type: course
layout: course_section
menu:
  leftnav:
    identifier: 8ee92c27f02bfd86d2629f4ce23755ef
    name: Solving ODEs in MATLAB
    weight: 110
is_media_gallery: true
---

Solving ODEs in MATLAB®
-----------------------

[Cleve Moler](http://www.mathworks.com/company/aboutus/founders/clevemoler.html) introduces computation for differential equations and explains the MATLAB ODE suite and its mathematical background. The video series starts with Euler method and builds up to Runge Kutta and includes hands-on MATLAB exercises.{{< video-gallery-item href="/sections/solving-odes-in-matlab/euler-ode1" section="Solving ODEs in MATLAB" title="Euler, ODE1" description="Descriptions: ODE1 implements Eulers method. It provides an introduction to numerical methods for ODEs and to the MATLAB ® suite of ODE solvers. Exponential growth and compound interest are used as examples. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/aW-e04zwTnc/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/midpoint-method-ode2" section="Solving ODEs in MATLAB" title="Midpoint Method, ODE2" description="Description: ODE2 implements a midpoint method with two function evaluations per step. This method is twice as accurate as Eulers method. A nonlinear equation defining the sine function provides an example. An exercise involves implementing a related trapezoid method. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/x0Ap2kDsGRQ/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/classical-runge-kutta-ode4" section="Solving ODEs in MATLAB" title="Classical Runge-Kutta, ODE4" description="Description: ODE4 implements the classic Runge-Kutta method, which is the most widely used numerical method for ODEs over the past 100 years. Its major shortcoming is the lack of an error estimate. A simple model of the growth of a flame is an example that is used here and in later videos. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/Mva9UIz_wwA/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/order-naming-conventions" section="Solving ODEs in MATLAB" title="Order, Naming Conventions" description="Description: The digits in the name of a MATLAB ® ODE solver reflect its order and resulting accuracy. A method is said to have order p if cutting the step size in half reduces the error in one step by a factor of two to the power p+1. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/6O9D6am_RK4/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/estimating-error-ode23" section="Solving ODEs in MATLAB" title="Estimating Error, ODE23" description="Description: ODE23 compares methods of order two and three to automatically choose the step size and maintain a specified accuracy. It is the simplest MATLAB ® solver that has modern features such as automatic error estimate and continuous interpolant. ODE23 is suitable for coarse accuracy requirements such as computer graphics. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/ScZMBOB_qYQ/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/ode45" section="Solving ODEs in MATLAB" title="ODE45" description="Description: ODE45 is usually the function of choice among the ODE solvers. It compares methods of orders four and five to estimate error and determine step size. ODE45 is so accurate that its default behavior is to use its interpolant to provide results at intermediate points. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/DkOgvZywshI/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/stiffness-ode23s-ode15s" section="Solving ODEs in MATLAB" title="Stiffness, ODE23s, ODE15s" description="Descriptions: A problem is said to be stiff if the solution being sought varies slowly, but there are nearby solutions that vary rapidly, so the numerical method must take small steps to obtain satisfactory results. The flame model demonstrates stiffness. ODE solvers with names ending in s, such as ODE23s and ODE15s, employ implicit methods and are intended for stiff problems. These methods require more work per step, but take many fewer steps. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/gwmIksA7aXM/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/systems-of-equations" section="Solving ODEs in MATLAB" title="Systems of Equations" description="Descriptions: An ordinary differential equation involving higher order derivatives is rewritten as a vector system involving only first order derivatives. The classic Van der Pol nonlinear oscillator is provided as an example. The VdP equation becomes stiff as the parameter is increased. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/NNhVVk244ZA/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/the-matlab-ode-suite" section="Solving ODEs in MATLAB" title="The MATLAB ODE Suite" description="Descriptions: The MATLAB ® documentation provides two charts summarizing the features of each of the seven functions in the MATLAB ODE suite. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/cQKR5m5pTTg/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/tumbling-box" section="Solving ODEs in MATLAB" title="Tumbling Box" description="Descriptions: Throw a rectangular object with sides of three different lengths (such as a cereal box), into the air. You can get the box to tumble stably about its longest axis, or about its shortest axis. But if you try to make it tumble about it middle axis, you will find the motion is unstable. The model of the angular momentum is a nonlinear system of three differential equations. There are six critical points: the four corresponding to the long and short axes are stable; the two corresponding to the middle axis are unstable. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/ttCKLZ2fWWE/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/predator-prey-equations" section="Solving ODEs in MATLAB" title="Predator-Prey Equations" description="Descriptions: The classic Lotka-Volterra model of predator-prey competition, which describes interactions between foxes and rabbits, or big fish and little fish, is the foundation of mathematical ecology. It has also been applied to many other fields, including economics. The model is a nonlinear system of two equations, where one species grows exponentially and the other decays exponentially in the absence of the other. The one nonzero critical point is stable. All solutions are periodic. The program predprey provides an app for studying the model. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/zrFJKy5l_PY/default.jpg" >}} {{< video-gallery-item href="/sections/solving-odes-in-matlab/lorenz-attractor-and-chaos" section="Solving ODEs in MATLAB" title="Lorenz Attractor and Chaos" description="Descriptions: The Lorenz chaotic attractor was discovered by Edward Lorenz in 1963 when he was investigating a simplified model of atmospheric convection. It is a nonlinear system of three differential equations. With the most commonly used values of three parameters, there are two unstable critical points. The solutions remain bounded, but orbit chaotically around these two points. The program lorenzgui provides an app for investigating the Lorenz attractor. The resulting 3-D plot looks like a butterfly. Related MATLAB code files can be downloaded from MATLAB Central Instructor: Cleve Moler" thumbnail="https://img.youtube.com/vi/Q_f1vRLAENA/default.jpg" >}}