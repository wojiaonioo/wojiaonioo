<a href="https://wojiaonioo.github.io"><img src="assets/banner.svg" width="100%" alt="Haoyang Tang. Differentiable ocean models on GPUs. Physical oceanography, Chinese Academy of Sciences."></a>

<p>
<a href="https://wojiaonioo.github.io">Homepage</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="https://wojiaonioo.github.io/assets/tanghaoyang-cv-en.pdf">CV (PDF)</a>&nbsp;&nbsp;|&nbsp;&nbsp;<a href="mailto:tanghy@idsse.ac.cn">tanghy@idsse.ac.cn</a>
</p>

### TorchOcean

I rebuilt the ocean discretizations of MITgcm in PyTorch and CUDA so that one GPU program computes forward integrations and their gradients, for 4D-Var data assimilation and for training neural networks inside the model.

<img src="assets/flow.webp" width="100%" alt="Particle animation of 29 days of surface currents, MITgcm on the left and TorchOcean on the right">
<sub>29 days of surface currents, South China Sea and western Pacific at 1/32°. MITgcm left, TorchOcean right; the difference between them stays at the size of MITgcm's own rounding differences.</sub>

On a 960×960×90 grid, two A800 GPUs take as long per step as MITgcm on about 668 CPU cores. In South China Sea twin experiments, 4D-Var with these gradients reduces three-day forecast errors by 31% over 52 windows, and the same reverse integration trains a network that produces the initial state. Details on the [homepage](https://wojiaonioo.github.io).
