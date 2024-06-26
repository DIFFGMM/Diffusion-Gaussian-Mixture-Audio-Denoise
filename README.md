
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
> Raw audio
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/13a86efd-1037-4ecb-bd7c-6ee831012a7f)
> Group Truth
[GT](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/36c768c8-ae3a-4604-b021-ac3128defb42)
Predicted audio
[Predicted output example ](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/52ae25ae-c8a5-4328-b454-462f7a6f649a) 

> Example 2:
> Raw audio
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/716e7cbb-c07f-4c27-93ba-ed10f93ff8fd)
> Group Truth
>[GT](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/86c3e751-8287-40fc-a0eb-9aefbd812e41)
> Predicted audio
[Predicted output example ](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/84a7304f-8c3c-4c44-a004-b78b888d8179
)

> Example 3:
Raw audio
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/133dab48-39ac-4fb1-ba84-327d435966d8)
Group Truth
> [GT](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/1fc260d8-20d7-4b99-a062-023cbe918233)
 Predicted audio
[Predicted output example ](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/cfb78867-d029-4ef8-b140-c61aad5734a4)

> Example 4:
Raw audio
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/2b650eb8-40c3-4a3f-97fa-e282efd864c2)
Group Truth
[GT](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/6ea45108-ef9f-4fbb-98e5-a8e0ad6f6b4e)
Predicted audio
[Predicted output example ](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/a95974ab-44a4-4946-ba01-256554d78bcd)

> Example 5:
Raw audio
[Input example](https://github.com/PuWang-LP/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/ca134157-65a8-4184-ad41-b2876fa41f67)
Group Truth
> [GT](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/0a246944-ed55-434f-b172-39aee4836418)
Predicted audio
[Predicted output example](https://github.com/DIFFGMM/Diffusion-Gaussian-Mixture-Audio-Denoise/assets/117755153/3cb540f2-f56c-4737-8e9c-4b81525ebcd2)



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
