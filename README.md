# Implementation of MICCAI 2023 paper with id 1151: Learning Enhancement From Degradation: A Diffusion Model For Fundus Image Enhancement. 

## Train
For training LED, you need to update few lines in configs/train_led.yaml
```yaml
    train_good_image_dir: # update to training hq images directrory
    train_bad_image_dir: # update to training lq images directrory
    train_degraded_image_dir: # update to training degraded images directrory
    val_good_image_dir:  # update to validation hq images directrory
    val_bad_image_dir: # update to validation lq images directrory
```
Please note that ``train_degraded_image_dir`` should contain degraded high-qualty images by any data-driven methods. We will inculde related codes in our future workspace. However, you can consider using some existing repos instead, like [CUT](https://github.com/taesungp/contrastive-unpaired-translation) or [CycleGAN](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix).

To train LED, simply  run
```bash
accelerate launch  --mixed_precision fp16 --gpu_ids 0 --num_processes 1 script/train.py 
```

## Evaluation
The evaluation codes are under code review and will be relased by pre-trained weights.