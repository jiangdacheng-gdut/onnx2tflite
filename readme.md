# ONNX->TFLite tools

## How to use
```python
# base
python converter --weights "./your_model.onnx"

# give save path
python converter --weights "./your_model.onnx" --outpath "./save_path"
python converter --weights "./your_model.onnx" --outpath "./tflitemodel.tflite"

# quantitative model weight, only weight
python converter --weights "./your_model.onnx" --weigthquant

# quantitative model weight, include input and output
python converter --weights "./your_model.onnx" --int8 --imgroot "./dataset_path" # recommend
python converter --weights "./your_model.onnx" --int8 # generate random data, instead of read from image file
```

## 注意(Caution)
- please use [comfirm_acc.py](./test/comfirm_acc.py) comfirm output is correct after convertion, because some of methods rely on practice.
- tools is going on update.
- only support 2D CNN, may be support more types of CNN or transformer in the future.
- 因为大部分是靠实践经验的，所以转换完成最好使用[comfirm_acc.py](./test/comfirm_acc.py)确认转换精度。
- 目前还没有更新完，我需要一点时间。。。
- 目前只支持2D卷积网络
---

## 添加新算子时，API查询地址(API reference docs)
- onnx_api : https://github.com/onnx/onnx/blob/main/docs/Operators.md
- tensorflow_api : https://tensorflow.google.cn/api_docs/python/tf
- keras_api : https://keras.io/search.html
---

## 已验证的模型列表(support models)
- Resnet
- Densenet
- Mobilenet
- Alexnet
- VGG
- UNet\FPN
- YOLOX
- YOLOV5
- normal CNN