# ssd_nanogpt
Applies Simple Self-Distillation to nanoGPT for improved performance.

Sorry, results turned out to be not statistically significant.

Here's the run command anyway:

```
python3.10 train.py config/train_shakespeare_char.py \
  --device=cpu --compile=False --eval_iters=20 --log_interval=1 \
  --block_size=64 --batch_size=12 --n_layer=4 --n_head=4 --n_embd=128 \
  --max_iters=2000 --lr_decay_iters=2000 --dropout=0.0 \
  --self_distill=True \
  --ssd_iters=100 \
  --ssd_prompt_len=0 --ssd_gen_len=32 \
  --ssd_lr=5e-7 \
  --distill_temp=0.6 \
  --top_p=0.9
  ```
