
# Diffusion-Gaussian-Mixture-Audio-Denoise

## Abstract
Recent diffusion models achieved promising performances in audio-denoising tasks. The unique property of the reverse process could recover super clean signals. However, the distribution of real-world noises does not comply with single Gaussian distribution and is even unknown. The sampling of Gaussian noise conditions limits its application scenarios. In other words, one single Gaussian distribution is not enough to represent the original noise distribution. To overcome these challenges, this paper proposes DiffGMM, a denoising model based on the diffusion and Gaussian mixture models. We employ the reverse process to estimate parameters for the Gaussian mixture model. Given a noisy audio signal, we first use a 1D-U-Net to extract features and train linear layers to estimate parameters for the Gaussian mixing model, and we can approximate the real noise distribution. The noisy signal is continuously subtracted from the estimated noise to output clean audio signals. Extensive experimental results demonstrate that the proposed DiffGMM model achieves state-of-the-art performance.

<img src="photo/IMG.png" alt="sound representation" title="sound representation" />


## Samples

For prediction, the noisy voice audios are converted into numpy time series of windows slightly above 1 second. Each time serie is converted into a magnitude spectrogram and a phase spectrogram via STFT transforms. Noisy voice spectrograms are passed into the U-Net network that will predict the noise model for each window (cf graph below). Prediction time for one window once converted to magnitude spectrogram is around 80 ms using classical CPU.

<img src="img/flow_prediction.png" alt="flow prediction part 1" title="flow prediction part 1" />

Then the model is subtracted from the noisy voice spectrogram (here I apply a direct subtraction as it was sufficient for my task, we could imagine to train a second network to adapt the noise model, or applying a matching filter such as performed in signal processing). The "denoised" magnitude spectrogram is combined with the initial phase as input for the inverse Short Time Fourier Transform (ISTFT). Our denoised time serie can be then converted to audio (cf graph below).

<img src="img/flow_prediction_part2.png" alt="flow prediction part 2" title="flow prediction part 2" />

Let's have a look at the performance on validation datas!

Below I display some results from validation examples for Alarm/Insects/Vaccum cleaner/Bells noise.
For each of them I display the initial noisy voice spectrogram, the denoised spectrogram predicted by the network, and the true clean voice spectrogram. We can see that the network is well able to generalize the noise modelling, and produce a slightly smoothed version of the voice spectrogram, very close to the true clean voice spectrogram.

More examples of spectrogram denoising on validation data are displayed in the initial gif on top of the
repository.

<img src="img/validation_spec_examples.png" alt="validation examples" title="Spectrogram validation examples" />

Let's hear the results converted back to sounds:

> Audios for Alarm example:

[Input example alarm](https://vbelz.github.io/Speech-enhancement/demo_data/validation/noisy_voice_alarm39.wav)

[Predicted output example alarm](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_pred_alarm39.wav)

[True output example alarm](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_alarm39.wav)

> Audios for Insects example:

[Input example insects](https://vbelz.github.io/Speech-enhancement/demo_data/validation/noisy_voice_insect41.wav)

[Predicted output example insects](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_pred_insect41.wav)

[True output example insects](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_insect41.wav)

> Audios for Vaccum cleaner example:

[Input example vaccum cleaner](https://vbelz.github.io/Speech-enhancement/demo_data/validation/noisy_voice_vaccum35.wav)

[Predicted output example vaccum cleaner](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_pred_vaccum35.wav)

[True output example vaccum cleaner](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_vaccum35.wav)

> Audios for Bells example:

[Input example bells](https://vbelz.github.io/Speech-enhancement/demo_data/validation/noisy_voice_bells28.wav)

[Predicted output example bells](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_pred_bells28.wav)

[True output example bells](https://vbelz.github.io/Speech-enhancement/demo_data/validation/voice_bells28.wav)

Below I show the corresponding displays converting back to time series:

<img src="img/validation_timeserie_examples.png" alt="validation examples timeserie" title="Time serie validation examples" />

You can have a look at these displays/audios in the jupyter notebook `demo_predictions.ipynb` that I provide in the `./demo_data` folder.

Below, I show the corresponding gif of the spectrogram denoising gif (top of the repository) in the time serie domain.

<img src="img/denoise_ts_10classes.gif" alt="Timeserie denoising" title="Speech enhancement"/>

As an testing, I applied to some voices blended with many noises at a high level.
The network appeared to work surprisingly well for the denoising. The total time to denoise a 5 seconds audio was around 4 seconds (using classical CPU).

Below some examples:

> Example 1:

<img src="docs/005.png" alt="audio denoising" title="audio denoising samples"/>

> Example 2:

<img src="docs/007.png" alt="audio denoising" title="audio denoising samples"/>

> Example 3:

<img src="docs/293.png" alt="audio denoising" title="audio denoising samples"/>

> Example 4:

<img src="docs/426.png" alt="audio denoising" title="audio denoising samples"/>

> Example 5:

<img src="docs/432.png" alt="audio denoising" title="audio denoising samples"/>


## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
