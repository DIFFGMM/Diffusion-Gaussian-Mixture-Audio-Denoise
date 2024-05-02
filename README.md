
# Diffusion-Gaussian-Mixture-Audio-Denoise

## Abstract
Recent diffusion models achieved promising performances in audio-denoising tasks. The unique property of the reverse process could recover super clean signals. However, the distribution of real-world noises does not comply with single Gaussian distribution and is even unknown. The sampling of Gaussian noise conditions limits its application scenarios. In other words, one single Gaussian distribution is not enough to represent the original noise distribution. To overcome these challenges, this paper proposes DiffGMM, a denoising model based on the diffusion and Gaussian mixture models. We employ the reverse process to estimate parameters for the Gaussian mixture model. Given a noisy audio signal, we first use a 1D-U-Net to extract features and train linear layers to estimate parameters for the Gaussian mixing model, and we can approximate the real noise distribution. The noisy signal is continuously subtracted from the estimated noise to output clean audio signals. Extensive experimental results demonstrate that the proposed DiffGMM model achieves state-of-the-art performance.

<img src="photo/IMG.png" alt="sound" title="sound" />


## Samples


Let's hear the results converted back to sounds:

> Audios for VoiceBank + DEMAND example:
>
> 
> Example 1:
> 
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/13a86efd-1037-4ecb-bd7c-6ee831012a7f)

[Predicted output example ](audio/prediction denoisy audio/p232_005.mp4)

> Example 2:


[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/716e7cbb-c07f-4c27-93ba-ed10f93ff8fd)

[Predicted output example ](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/636b8c44-5e79-47c0-8f01-81ee75249ca8)

> Example 3:

[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/133dab48-39ac-4fb1-ba84-327d435966d8)

[Predicted output example ](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/3803a889-6570-457b-809f-b1a76466932c)

> Example 4:

[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/2b650eb8-40c3-4a3f-97fa-e282efd864c2)

[Predicted output example ](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/00b36c98-f224-4439-91b9-1ef0cf1b9df6)

> Example 5:

[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/ca134157-65a8-4184-ad41-b2876fa41f67)

[Predicted output example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/f88014de-d2a8-4869-bf5c-f1fd1015e36b)



Below some examples:

> Example 1:

<img src="spectrograms/005.png" alt="audio denoising" title="audio denoising samples"/>

> Example 2:

<img src="spectrograms/007.png" alt="audio denoising" title="audio denoising samples"/>

> Example 3:

<img src="spectrograms/293.png" alt="audio denoising" title="audio denoising samples"/>

> Example 4:

<img src="spectrograms/426.png" alt="audio denoising" title="audio denoising samples"/>

> Example 5:

<img src="spectrograms/432.png" alt="audio denoising" title="audio denoising samples"/>


## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
