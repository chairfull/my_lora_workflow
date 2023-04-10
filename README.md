# Current LoRA workflow

Most of my public LoRA's are here: https://civitai.com/user/chairfull

## 1) Training Data

Image quality seems to be big part in how well they turn out, so I try to use the highest quality images I can find.

I don't crop them, except to remove text or other people.

Many images are over 2000x3000. Some >8000x5000.

### Finding images
(TODO)

## 2) Kohya
I used: https://github.com/Linaqruf/kohya-trainer (Dreambooth method, top one.)

I use the Google colab version as my GPU sucks, but I assume it works the same if you downloaded.

Used BLIP to auto caption the images. (Took <1 minute.)

Leave pretty much all the settings values at their default, except:
  * For pre trained model download: `Stable-Diffusion-v1-5`.
  * For VAE model download: `stablediffusion.vae.pt`
  * Set `pretrained_model_name_or_path` to `/content/pretrained_model/Stable-Diffusion-v1-5.safetensors`
  * Set `vae` to `/content/vae/stablediffusion.vae.pt`
  * Set `class_token` to `man`.
