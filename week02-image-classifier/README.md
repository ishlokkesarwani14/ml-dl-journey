# Week 1: Is it a Bird? — Image Classifier

A binary image classifier built with fastai, based on Jeremy Howard's "Is it a bird?" 
lesson from Practical Deep Learning for Coders.

## What it does
Takes an image and predicts whether it's a bird or not, using transfer learning 
on a pretrained resnet18 model — trained on images pulled live from a web search.

## Stack
- fastai / PyTorch
- resnet18 (pretrained, fine-tuned)
- Kaggle Notebooks (GPU: T4 x2)

## The build was not smooth — real issues hit and fixed:
- **GPU incompatibility**: Kaggle's default P100 GPU (compute capability 6.0) wasn't 
  supported by the installed PyTorch version — switched to T4 x2 (7.5) to fix.
- **Rate limiting**: DuckDuckGo image search got rate-limited mid-download — added 
  a retry-with-backoff wrapper around the search function.
- **Package rename**: `duckduckgo_search` was renamed to `ddgs` — updated imports 
  and pip install accordingly.
- **fastai/torchvision version mismatch**: a missing `tvpad` function in the 
  installed torchvision broke fastai's image resize step — patched by manually 
  binding the function from `torchvision.transforms.functional` before training.

## Result
Model successfully classifies bird vs. non-bird images with high confidence 
after 3 epochs of fine-tuning.

## Next steps
Week 7 will rebuild a neural network from scratch using only NumPy, to understand 
what's happening under the hood of `vision_learner.fine_tune()`.
