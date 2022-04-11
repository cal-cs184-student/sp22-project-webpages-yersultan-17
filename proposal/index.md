---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
classes:
  - landing
---

# Soccer Ball Simulator: Proposal
***

# Summary

Our goal is to create a physics simulation of a soccer ball being kicked into a goal. We hope to build upon the code infrastructure provided in Project 4 (clothsim) and extend its functionality. In addition to modeling the soccer ball and the goal with all the forces, torques, momenta, etc, we also hope to experiment with different numerical integration techniques (Runge Kutta methods, Adams-Bashforth, Predictor/Corrector, etc) and see how they affect how realistic is the simulation. 

**Team members:** Saagar Sanghavi, Rishi Parikh, Raiymbek Akshulakov, Yersultan Sapar.

# Problem Description

Many applications of graphics include rendering the graphics and physics of sports. Popular video games such as NBA2K and FIFA build on these principles to make hyper-realistic video games. Our problem is to render a simple high order simulator that models the movement of a ball, including its spin, rotation, and acceleration. In sports, there are a lot of factors that affect the trajectory and impact of a ball that cannot be modeled by simple kinematics. Some examples include a curved shot in soccer that goes around blockers or topspin in volleyball which changes the trajectory. In this problem we aim to tackle the following challenges:
- Modeling an accurate ball created using springs (to represent the give and compressibility of a ball) with an air pressure force within the ball
- The acceleration and spin due to an external force accounting for friction and conservation of momentum. This could be similar to a foot kicking a soccer ball. 
- A soccer net made using pinned particles and spring forces to render a realistic movement of the net when the ball hits the goal. 
- Graphics and background for the ball. 
- Different numerical integration methods to simulate movement. 

# Goals & Deliverables

As it was outlined in the summary, our main goal is to create a realistic simulation of various soccer elements. Those include the realistic dynamics of a soccer ball and goal nets. 

## Baseline plan (planned deliverables)

**Soccer ball** - for the ball, our first priority goal is to simulate the physics of the ball – the flow of the ball during the spin, bouncing out of the surfaces.   

**Soccer net** - for the net, our goal is to simulate a realistic net response from the ball hitting the net as well as bouncing from the net polls.

**Deliverables:** a demo with simplistic recreations of various soccer goals with an apparent ball spin like in both cases below. 

## Quality Assessment

There doesn’t seem any way to mathematically define a precise metric for the performance of our simulation. However, one possibility to measure the performance would be to just observe the visual similarity between the real-life scenes and their recreations. Another way to check the performance is to try to predict the future path of the ball and to calculate to what degree the ball diverges from it. This method still suffers from the dependence of the path on the type of the ball and in practice, the ball is often not fully rigid which makes the prediction of the actual path hard to pre-compute. Regardless, the analysis of the trajectory is a useful tool for assessing the effectiveness of our simulation. 

## Aspirational plan
	
In addition to everything outlined above, we hope to add some additions in the future:

**Not fully rigid ball** - in reality, the soccer ball is not really rigid and does temporarily deform when the kick is strong enough. Moreover, it greatly affects the ball spin too so adding a spring-mass system to represent the ball will hopefully make it more realistic.

**Addition of RL** - one way to extend the project would be to set up a reinforcement learning to make an automated agent be able hit the targets with the ball and avoid the obstacles


## Main questions we would like to answer

- Would the rigid model of the soccer ball be enough to recreate famous free-kicks with a huge amount of spin?
- How the addition of non-rigidness will affect the spin and bouncing effects 
- Which reward function works best for the agent for the task of kicking the ball towards some target


# Schedule

| Finish by              | Tasks |
|------------------------|-------|
| Apr 19                 | Setup C++ infrastructure, modifying Project 4 starter code to fit to our needs.  Write out mathematical models of truncated icosahedron, spring-mass models, equations for wind/air resistance etc. Identify all relevant forces and torques that affect dynamics and write out equations of motion for our setup. |
| Apr 26 - Milestone due | Start coding up the logic for physics constraints and forces and motion. Use Verlet integration to simulate for now (implemented in project 4 already). By Milestone, shoot to complete basic implementation of physics in the game simulation. If time allows, start experimenting with different numerical ODE solving techniques. |
| May 3                  | Add GUI elements, user controls, customizability. Render textures/shading and visual effects. Experimenting with different numerical ODE solving techniques: Runge Kutta, Linear Multi-step methods, Predictor-Corrector Methods, etc. Report results on how they affect the simulation and whether or not some methods are advantageous to others. |
| May 10 - Deadline      |  Finish the rest of the project, buffer time to debug. Finish up report and simulation graphics. Finalize all shaders/textures/GUI elements, etc. Polish and submit. |

## Workload Distribution
What each person will be responsible for (note that these are meant to align with the individual’s strengths)

**Rishi:** graphics for rendering the images, visuals, shading effects, etc.  
**Saagar:** physics modeling of the soccer ball, construction of meshes and figures, 3D geometry, numerical integration methods  
**Yersultan:** setting up C++ infrastructure (extending code from Project 4), wind effects for soccer simulation  
**Raiymbek:** mathematical modeling, numerical integration methods, write-up of results and website  

# Resources

- CS184 Project 4 starter code 
- FIFA 21 game - inspiration for video game animations 
- We hope that our simulator can be run from laptop setup with cs184 imports 

