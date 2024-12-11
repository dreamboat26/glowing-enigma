[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/kmader/chess-alpha-zero/master?urlpath=lab)
[![Demo Notebook](https://img.shields.io/badge/launch-demo_notebook-red.svg)](https://mybinder.org/v2/gh/kmader/chess-alpha-zero/master?filepath=notebooks%2Fdemo.ipynb)

About
=====

Chess reinforcement learning by [AlphaGo Zero](https://deepmind.com/blog/alphago-zero-learning-scratch/) methods.

This project is based on these main resources:
1) DeepMind's Oct 19th publication: [Mastering the Game of Go without Human Knowledge](https://www.nature.com/articles/nature24270.epdf?author_access_token=VJXbVjaSHxFoctQQ4p2k4tRgN0jAjWel9jnR3ZoTv0PVW4gB86EEpGqTRDtpIz-2rmo8-KG06gqVobU5NSCFeHILHcVFUeMsbvwS-lxjqQGg98faovwjxeTUgZAUMnRQ).
2) The great Reversi development of the DeepMind ideas that @mokemokechicken did in his repo: https://github.com/mokemokechicken/reversi-alpha-zero
3) DeepMind just released a new version of AlphaGo Zero (named now AlphaZero) where they master chess from scratch:
https://arxiv.org/pdf/1712.01815.pdf. In fact, in chess AlphaZero outperformed Stockfish after just 4 hours (300k steps) Wow!

See the [wiki](https://github.com/Akababa/Chess-Zero/wiki) for more details.

Environment
-----------

* Python 3.6.3
* tensorflow-gpu: 1.3.0
* Keras: 2.0.8

![img](https://user-images.githubusercontent.com/4205182/34333105-ada817c6-e8fe-11e7-8c01-5958aaf264c1.gif)

![img](https://user-images.githubusercontent.com/4205182/34323276-ecd2a7b6-e806-11e7-856a-4e2394bd75df.gif)

![partida1](https://user-images.githubusercontent.com/17341905/33597844-ea53c8ae-d9a0-11e7-8564-4b9b0f35a221.gif)

![partida3](https://user-images.githubusercontent.com/17341905/34030278-8796f7c6-e16c-11e7-9ba4-97af15f2cde5.gif)

### Reinforcement Learning

This AlphaGo Zero implementation consists of three workers: `self`, `opt` and `eval`.

* `self` is Self-Play to generate training data by self-play using BestModel.
* `opt` is Trainer to train model, and generate next-generation models.
* `eval` is Evaluator to evaluate whether the next-generation model is better than BestModel. If better, replace BestModel.

Data
-----

* `data/model/model_best_*`: BestModel.
* `data/model/next_generation/*`: next-generation models.
* `data/play_data/play_*.json`: generated training data.
* `logs/main.log`: log file.

If you want to train the model from the beginning, delete the above directories.

How to use
==========

Setup
-------
### install libraries
```bash
pip install -r requirements.txt
```

If you want to use GPU, follow [these instructions](https://www.tensorflow.org/install/) to install with pip3.

Make sure Keras is using Tensorflow and you have Python 3.6.3+. Depending on your environment, you may have to run python3/pip3 instead of python/pip.
