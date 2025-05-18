# TensorflowJS converter for Apple Silicon

This repo provides instructions for installing and using the [`@tensorflow/tfjs-converter`](https://www.npmjs.com/package/@tensorflow/tfjs-converter) script, specifically the `tensorflowjs_converter` script.

Thanks to this stack overflow answer: https://stackoverflow.com/a/73771779

## 0. Setup pyenv + clone this repo

This won't be covered here, but you need pyenv to be setup and working.

Clone this repo with:

```sh
git clone https://github.com/benjamingwynn/tfjs-converter-macos-arm.git
```

## 1. Use Python 3.11

The docs say to use Python 3.6.8, ignore them as you Pip won't be able to get/build a macos ARM version of some native dependencies which are compatible with 3.6.

Instead, with pyenv, use 3.11 so that pip can get/build compatible dependencies:

```sh
pyenv install 3.11
pyenv local 3.11
```

Validate with:

```sh
python --version
```

## 2. Make a virtual environment for pip to install its repo to

Create a virtual env:

```sh
python -m venv venv
```

Activate it with:

```sh
. venv/bin/activate
```

Your shell should now have "(venv)" in its prompt.

## 3. Install the requirements

```sh
pip install -r requirements.txt
```

Or alternatively if you didn't clone the repo:

```sh
pip install tensorflow_hub jax scipy jaxlib etils "tensorflow==2.16.1" "tensorflow-macos==2.16.1" tensorflow_decision_forests && pip install --no-deps tensorflowjs
```

## 4. Run the program

```sh
tensorflowjs_converter --help
```

If you close your shell and reopen it in this repo, rerun `. venv/bin/activate` to be able to use the `tensorflowjs_converter` command, or you can access it directly at `venv/bin/tensorflowjs_converter`
