# Eigen Coding Challenge
This is my submission for the Eigen Coding Challenge. Inside, you'll find the following contents:

1. `eigen-app`, a simple Flask app with a file uploader
2. `processor.py`, the backend module, which can also be called as a script

## `processor.py`
The processor incorporates two implementations of Latent Dirichlet Allocation, one from [Gensim](https://radimrehurek.com/gensim/) and the other from [Ariddell](https://github.com/lda-project/lda/tree/master).

Neither is perfect, though the Gensim implementation appears to be a bit more robust and produces topics for which words are more similarly related. However, the Flask application only calls Aridell's implementation because the output is simpler to work with. I would imagine that the differences between the two come from sampling methods and multithreading/async quirks.

## Usage
To run, initialize virtual environment, which will install necessary dependencies.

```shell
./init_env.sh```

To launch the app, call `flask run` and navigate to `127.0.0.1:5000` in your preferred browser.

You can also call the topic generator directly from within the `processors` directory.

## TODOs
* Robust handling of invalid/corrupt files, redundant file names, etc.
* Multilingual support
* Phrase-based LDA implementation. Currently working only with unigrams, which is really not so useful. The bag-of-words assumption that LDA rests on is quite limited, unfortunately
* Cleaning up the Flask app itself so that it's not horrendous
