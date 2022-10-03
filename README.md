# Text to Image Generation using DALL-E Mini

This is an educational code sample for text to image generation using hugging face's DALLE-mini model.

## Setup

To code have some preqistes which are quite heavy and may crash your system if its not adequetly with resources. The recomoded configuration is either use a machine with more than 8GB RAM and 8 core processors or best to use Google collab.

### Libraries need to install:

```bash
!pip install -q git+https://github.com/huggingface/transformers.git

!pip install -q git+https://github.com/patil-suraj/vqgan-jax.git

!pip install -q git+https://github.com/borisdayma/dalle-mini.git
```

### Wandb API key

You will need a key to use the WANdb API which could be easily be generated from the https://wandb.ai/authorize.

You just need to signup and it will generate an API token for your profile.

## Tweaking parameters

To generate images with different parameters like `Number of predictions`, `temperture` etc make changes to below function and run it once before running image generation function.

```bash
def set_img_gen_parameter(npred):
  
  # number of predictions
  n_predictions = npred

  # We can customize top_k/top_p used for generating samples
  gen_top_k = None
  gen_top_p = None
  temperature = 0.85
  cond_scale = 3.0

  return n_predictions, gen_top_k, gen_top_p, temperature, cond_scale
```

## Genrate image(s)

To generate image(s) for a text input trigger below function with text

```bash
text_description = "A Cat with a hat."
generate_text_to_image(text_description)
```



