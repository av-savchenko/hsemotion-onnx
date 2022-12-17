# HSEmotionONNX Python Library for Facial Emotion Recognition
[![Downloads](https://static.pepy.tech/personalized-badge/hsemotion_onnx?period=total&units=international_system&left_color=grey&right_color=blue&left_text=pip%20installs)](https://pepy.tech/project/hsemotion_onnx)
[![pypi package](https://img.shields.io/badge/version-v0.3.1-blue)](https://pypi.org/project/hsemotion_onnx)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/classifying-emotions-and-engagement-in-online/facial-expression-recognition-on-affectnet)](https://paperswithcode.com/sota/facial-expression-recognition-on-affectnet?p=classifying-emotions-and-engagement-in-online)

## License

The code of HSEmotionONNX Python Library is released under the Apache-2.0 License. There is no limitation for both academic and commercial usage.

## Installing

```
    python setup.py install
```

It is also possible to install it via pip:
```
    pip install hsemotion-onnx
```


## Usage

```
    from hsemotion_onnx.facial_emotions import HSEmotionRecognizer
    model_name='enet_b0_8_best_afew'
    fer=HSEmotionRecognizer(model_name=model_name)
    emotion,scores=fer.predict_emotions(face_img,logits=False)
```

The following values of `model_name` parameter are supported:
- enet_b0_8_best_vgaf
- enet_b0_8_best_afew
- enet_b0_8_va_mtl
- enet_b2_8
- enet_b2_7

The method `predict_emotions` returns both the string value of predicted emotions (Anger, Contempt, Disgust, Fear, Happiness, Neutral, Sadness, or Surprise) and scores at the output of the last layer. 
If the `logits` parameter is set to `True` (by default), the logits are returned, otherwise, the posterior probabilities are estimated from the logits using softmax.


The versions of this method for a batch of images are also available
```
    emotions,scores=fer.predict_multi_emotions(face_img_list,logits=False)
```

Complete usage examples are available in the [demo folder](demo). It is necessary to install [mediapipe](https://google.github.io/mediapipe/) to run the demo script.

The details about training of the models are available in the [main repository](https://github.com/HSE-asavchenko/face-emotion-recognition)
