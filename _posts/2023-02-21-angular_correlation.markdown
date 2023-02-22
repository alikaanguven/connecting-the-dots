---
layout: post
title:  "Angular Correlations and The First Insight Behind X17 Existence"
date:   2023-02-21 17:29:00 +0300
categories: jekyll update
---


In this post Lorentz transformations, effects of boosting on opening angles, and how the former two can help making a new discovery will be covered.  
First things first.  

### Lorentz Transformations

Lorentz transformations are the special relativistic transformations that account for rotations and relativistic boosts. It describes how a constant motion in one reference frame is seen from another reference frame including the special relativistic effects.

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/frames.png" /></div>


The motion in the inertial frame of reference $S$ can be described in another inertial reference frame $S'$ as below:

$$
\begin{equation}
(p')^\mu = \Lambda^\mu_\nu p^\nu,
\end{equation}
$$

where $p'$ is the 4-momentum in the frame $S$, $p$ is the 4-momentum in the frame $S$, and $\Lambda$ is the Lorentz transformation matrix. If we assume that $S'$ moves in the $\hat{x}$ direction with a relativistic speed , then we can write the transformation, and inverse transformation matrices as:

$$
\begin{align}
\Lambda &= 

\begin{pmatrix}
    \gamma & -\gamma \beta &  &  \\
    -\gamma \beta & \gamma &  &  \\
     &  &  1 &  \\
     & & & 1 \\
\end{pmatrix} \\ \nonumber \\


\Lambda^{-1} &= 

\begin{pmatrix}
    \gamma & +\gamma \beta &  &  \\
    +\gamma \beta & \gamma &  &  \\
     &  &  1 &  \\
     & & & 1 \\
\end{pmatrix} \\
\end{align}
$$

An object that is not moving in the $S'$ frame has the following 4-momentum in $S$ frame:

$$
\begin{equation}
    p = \Lambda^{-1} p' = 
    \begin{pmatrix}
        \gamma & +\gamma \beta &  &  \\
        +\gamma \beta & \gamma &  &  \\
        &  &  1 &  \\
        & & & 1 \\
    \end{pmatrix} 
    \begin{pmatrix}
        E' \\
        0 \\
        0 \\
        0 \\
    \end{pmatrix} = 
    \begin{pmatrix}
        \gamma E'  \\
        \beta \gamma E' \\
        0 \\
        0 \\
    \end{pmatrix}
\end{equation}
$$

As expected it is moving in the direction $\hat{x}$ of $S$ frame. Using this simple transformation one can obtain how a 2-body decay is seen in the $S$ frame. Just like every phenomena in physics nuclear decays should conserve the momentum and energy. Therefore, if a particle decays at rest into two particles with the same mass, say an electron and a positron, these should have the same energy, and the same momentum, but pointing in the opposite direction. Now, if we put the unstable particle in the reference frame $S'$ motionless, we can describe how the observer at $S$ sees its decay. Before we move on let's give $S$, and $S'$ aliasses which are widely used by the physics communities LAB frame, and the Center of mass (CM) frame. The latter is called center of mass frame as the body decays the only thing that remains stationary will be the center of mass of the particles. Starting with the 4-momenta in the CM frame:

$$
\begin{equation}
    p'_{e_+} = 
    \begin{pmatrix}
        E'  \\
        p_x' \\
        p_y' \\
        0 \\
    \end{pmatrix}, \quad

    p'_{e_-} = 
    \begin{pmatrix}
        E'  \\
        -p_x' \\
        -p_y' \\
        0 \\
    \end{pmatrix}
\end{equation}
$$

Let's see the same 4-momenta in the LAB frame:

$$
\begin{equation}
    p_{e_+} = 
    \begin{pmatrix}
        \gamma E' + \beta \gamma p_x'  \\
        \beta \gamma E' + \gamma p_x' \\
        p_y' \\
        0 \\
    \end{pmatrix}, \quad

    p_{e_-} = 
    \begin{pmatrix}
        \gamma E' - \beta \gamma p_x'  \\
        \beta \gamma E' - \gamma p_x' \\
        -p_y' \\
        0 \\
    \end{pmatrix}
\end{equation}
$$

Out of curiosity, let's check the angle between the $e^+$ and $e^-$:

$$
\small
\begin{equation}
cos(\theta) = \frac{\vec{p_{e^+}} \cdot \vec{p_{e^-}}}{\lvert \lvert \vec{p_{e^+}} \rvert \rvert \ \lvert \lvert \vec{p_{e^-}} \rvert \rvert} = \frac{(\beta^2 \gamma^2 E'^2 - \gamma^2 p'^{2}_{x}) + p'^{2}_{y}}{\sqrt{\beta^2 \gamma^2 E'^2 + 2 \beta \gamma^2 E' p'_x + \gamma^2 p'^2_x + p'^2_y} \sqrt{\beta^2 \gamma^2 E'^2 - 2 \beta \gamma^2 E' p'_x + \gamma^2 p'^2_x + p'^2_y} }
\end{equation}
$$  

Phew! Fotunately we have computers and don't need to go through all this pain again. Let's see some examples:

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/boost1.png" /></div>
<br/><br/>
<div style="text-align: center"><img src="assets/images/pair_angular_correlation/boost2.png" /></div>


In the figures above you might notice X17 frame. For now, just think of X17 as a particle that decays at rest, therefore when I reference X17 frame I am talking about the CM frame. The second figure shows the minimum angle that is measured at the LAB frame, whereas at the CM frame we know that the opening angle always equals to $180^\circ$. There is an easier method to find the minimum opening angle. If the $e^+e^-$ pair moves on an axis perpendicular to the axis of boost, then the minimum opening angle calculation is as follows:

$$
\begin{equation}
    \begin{pmatrix}
        \gamma & +\gamma \beta &  &  \\
        +\gamma \beta & \gamma &  &  \\
        &  &  1 &  \\
        & & & 1 \\
    \end{pmatrix} 
    \begin{pmatrix}
        E' \\
        0 \\
        p'_y \\
        0 \\
    \end{pmatrix} = 
    \begin{pmatrix}
        E' \gamma \\
        E' \gamma \beta \\
        p'_y \\
        0 \\
    \end{pmatrix}
\end{equation}
$$

$$
\begin{equation}
    \theta_{\pm} = atan(\frac{p'_y}{\pm E' \gamma \beta} )
\end{equation}
$$
  
When we perform a Monte-Carlo (MC) simulation, and assume a uniform distribution for the angular distribution of the $e^+e^-$ pair at the CM frame, we see a modified distribution in the LAB frame.

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/histo1.png" /></div>



Say we observe them both in a decay, as in the figure below. Then what we could infer is that we might be observing a decay at rest, and another decay in a boosted frame. However, this is not always the case and this should never be generalized. Here, we only give this picture as a toy model:

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/histo2.png" /></div>

<br><br/>
### A More Realistic Picture: Hypothetical X17 Particle

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/ATOMKI.png" /></div>
*Reference:* [*arXiv:1608.03591*](https://arxiv.org/abs/1608.03591)  

In 2016 at ATOMKI laboratories in Hungary, scientist observed an anomaly in the $^8Be$ decay. They bombarded a $^7Li$ target with protons and measured an excess of particles scattering with large opening angles. According to the theory they were expexting only an anisotropic distribution of $e^+e^-$ particles which emerge from internal pair creation (IPC) events via the decay of excited $$^8Be^*$$ atoms. They found that this excess can be explained if the $$^8Be^*$$ atom first decays into a hypothetical boson ($X17$) and then the boson decays into $e^+e^-$ pairs. Since the X17 decays in a moving CM frame the angular distributions measured will accrete in the larger angles. We will not cover all the details of the experiment, but only show how such a distribution can be generated and analysed on your PC.

We first need to generate an anisotropic distribution to simulate the IPC events. Since I am not a nuclear physicists I can't really tell why a nuclear decay is anisotropic, and calculate the angular distributions. What I can do is to guess an equation, generate some background IPC events, and then fit it.

$$
\begin{equation}
W(\theta) = A_0 + 0.56A_1cos(\theta) + 0.23A_2cos(\theta)^2,
\end{equation}
$$

where the parameters are $A_0=1$, $A_1=0.56$, $A_2=0.23$ could be a starting point. To generate random samples following a custom function, one needs to input a uniform random variable in the inverse cumulative distribution function. After that, each uniform random variable that your computer generates will be accurately matched to your custom distribution function. See them below:

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/custom_pdf.png" /></div>

These account for the IPC events. Now, adding X17 decay signals in the picture, we obtain the following histogram:

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/histo3.png" /></div>

Here, the red histogram shows the distribution of the anisotropic IPC distribution, and the blue one is the distribution of all the generated signals (including the X17 decays). To get these histograms, I generated 10,000 IPC events, and 400 X17 decays.

The next step is the background subtraction from the signal region and measure the statistical significance of the signals. A simple calssic method to do that is "the sideband subtraction". The background is fitted in the regions where the signals is not expected to be present, and then this fitted level is subtracted from the total measurements, leaving only the signals. Then the significances of the measuremetns can be evaluated. Both of these results can be seen below:

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/histo4.png" /></div>

<div style="text-align: center"><img src="assets/images/pair_angular_correlation/histo5.png" /></div>

<br><br/>

These calculations were only a mere demonstration of the subject which might draw interest of some people, and perhaps help them make great discoveries someday.
  
**N.B.** You can find the code that is used to generate the plots [here](https://www.github.com/alikaanguven/connecting-the-dots.github.io/tree/mainassets/notebooks/pair_angular_correlations).