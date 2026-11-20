<a href="https://wojiaonioo.github.io"><img src="assets/banner.svg" width="100%" alt="Haoyang Tang. Differentiable ocean models on GPUs. Physical oceanography, Chinese Academy of Sciences."></a>

<p>
<a href="https://wojiaonioo.github.io">Homepage</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="https://wojiaonioo.github.io/assets/tanghaoyang-cv-en.pdf">CV (PDF)</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="mailto:tanghy@idsse.ac.cn">tanghy@idsse.ac.cn</a>
</p>

### DEFgcm

I am the sole developer of DEFgcm, which implements the ocean discretizations of MITgcm in PyTorch so that one program computes model integrations and their gradients on GPUs. Over the South China Sea, its integrations match MITgcm's to within the difference between two MITgcm runs that differ only in summation order.

<img src="assets/flow.webp" width="100%" alt="Particle animation of 29 days of surface currents, MITgcm on the left and DEFgcm on the right">
<sub>29 days of surface currents, South China Sea and western Pacific at 1/32°. MITgcm left, DEFgcm right; the two differ by about as much as two MITgcm runs that differ only in the order of their global sums.</sub>

On a 960×960×90 grid, four A800 GPUs run a hydrostatic step 1.6 times as fast as MITgcm on 768 CPU cores. In South China Sea twin experiments, 4D-Var with these gradients lowers the forecast error three days after the assimilation window by 40% on average. A network trained online through the model recovers 81% of the 4D-Var improvement from one gradient evaluation, on 13 test windows after its training period. 4D-Var needs about 11 evaluations of J and its gradient to reach the error of the network, which needs only one. Details on the [homepage](https://wojiaonioo.github.io/?lang=en#hybrid).
