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

I mostly BLIP to auto caption the images.  
Recently I started upping the word count from `15-75` to `30-100`, and the results have seemed a tinge better?

Leave pretty much all the settings values at their default, except:
  * For pre trained model download: `Stable-Diffusion-v1-5`.
  * For VAE model download: `stablediffusion.vae.pt`
  * Set `pretrained_model_name_or_path` to `/content/pretrained_model/Stable-Diffusion-v1-5.safetensors`
  * Set `vae` to `/content/vae/stablediffusion.vae.pt`
  * Set `class_token` to `man`.

# Experiments

## Higher quality through tokens
Tokens in the captions, with the exception of the `class_token` are what you **don't** want trained as part of your model:  
So for a man: `a man, in a red hat, in a forest` would only extract the `man` not the `red hat` or `forest`.  
Theoretically, this should work for style and image quality, so for old images I might add: `blurry, old image, scan, jpeg artifacts, low quality` in hopes the model will pull a sharper image.
