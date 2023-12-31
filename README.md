
# MusicLyricsGPT
Generate your own Music Lyrics GPT

Generate music lyrics based on trained themes and phrases. Music lyrics is a complex thought process that gets the theme from previous trained hits to get right words and phrases to struck right chord of music lovers. Model was trained using MillionSong lyrics dataset of Spotify: 
#Columbia University Research: 

https://www.researchgate.net/publication/220723656_The_Million_Song_Dataset

http://millionsongdataset.com/pages/getting-dataset/#subset

The model repository for training/finetuning medium-sized GPTs with 5000 iterations. It is a rewrite of [nanoGPT](assets/nanogpt.jpg)/[minGPT](https://github.com/karpathy/minGPT). The code itself is plain and readable: `train.py` is a ~300-line boilerplate training loop and `model.py` a ~300-line GPT model definition, which can optionally load the GPT-2 weights from OpenAI. That's it.

Train new models from scratch, or finetune pretrained checkpoints (e.g. biggest one currently available as a starting point would be the GPT-2 1.3B model from OpenAI).

Deploy and Run:

$ python .\data\lyrics\prepare.py

$ python train.py config/train_lyrics.py --device=cpu --compile=False --eval_iters=20 --log_interval=1 --block_size=64 --batch_size=12 --n_layer=4 --n_head=4 --n_embd=128 
--max_iters=2000 --lr_decay_iters=2000 --dropout=0.0

$ python .\sample.py --out_dir=out-lyrics --device='cpu'  --start="strange love"
