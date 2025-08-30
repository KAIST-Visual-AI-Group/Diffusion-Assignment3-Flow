<div align=center>
  <h1>
  Flow Matching and Rectified Flow
  </h1>
  <p>
    <a href=https://mhsung.github.io/kaist-cs492d-fall-2025/ target="_blank"><b>KAIST CS492(C): Diffusion and Flow Models (Fall 2025)</b></a><br>
    Programming Assignment 3
  </p>
</div> 

<div align=center>
  <p>
    Instructor: <a href=https://mhsung.github.io target="_blank"><b>Minhyuk Sung</b></a> (mhsung [at] kaist.ac.kr)<br>
    TA: <a href=https://dvelopery0115.github.io target="_blank"><b>Seungwoo Yoo</b></a>  (dreamy1534 [at] kaist.ac.kr)<br>
    Credit: <a href=https://63days.github.io target="_blank"><b>Juil Koo</b></a>  (63days [at] kaist.ac.kr)<br>
  </p>
</div>

<div align=center>
   <img src="./assets/trajectory_visualization.png">
</div>


## Abstract
Flow Matching (FM) is a novel generative framework that shares similarities with diffusion models, particularly in how both tackle the Optimal Transport problem through an iterative process. Similar to diffusion models, FM also splits the sampling process into several time-dependent steps. At first glance, FM and diffusion models may seem almost identical due to their shared iterative sampling approach. However, the key differences lie in the objectve function and the choice of trajectories in FM. 

Regading the objective function, diffusion models predict the injected noise during training. In contrast, Flow Matching predicts the displacement between the data distribution and the prior distribution. 

Moreover, Flow Matching is developed from the perspective of _flow_, a time-dependent transformation function that corresponds to the forward pass in diffusion models. Unlike diffuison models, where the forward pass is fixed to ensure that every intermediate distribution also follows a Gaussian distribution, FM offers much greater flexibility in the choice of _flow_. This flexibility allows for the use of simpler trajectories, such as linear interpolation over time, between the data distribution and the prior distribution. Experimental results have sohwn that the FM objective and its simpler trajectory are highly effective in modeling the data distribution, Making FM a compelling alternative to diffusion models.

Furthermore, the concept of flows and their inducing vector fields gives rise to a technique known as rectification—a training-based approach for accelerating sampling in flow models. The key idea of rectification is to straighten the trajectories that transport the prior distribution to the target distribution, thereby reducing the number of inference steps required to generate new samples.

In this assignment, we will take a deep dive into the core components of the Flow Matching and Rectified Flow frameworks by implementing them step-by-step.

## Setup

Clone this repository and upload the notebook file `flow_matching.ipynb` to [Google Colab](https://colab.research.google.com).  
**All instructions—including task descriptions and submission guidelines—are provided in the notebook file. Please follow them carefully to complete the tasks.**
