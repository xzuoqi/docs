---
sidebar_position: 4
---

# Quick Validation

After users install the AXCL driver according to [Environment Installation](./env_install), users can use this document to quickly validate the model inference and benchmark of the Radxa AICore AX-M1.

:::tip
`axcl-smi` tool usage details, please refer to [**AXCL-SMI Tool Usage**](./axcl-smi)
:::

## Inference Test

Here, we simply use the Radxa AICore AX-M1 to validate the YOLOv8 inference, and the detailed code can be referenced to [ax_yolov8_steps.cc](https://github.com/AXERA-TECH/axcl-samples/blob/main/examples/axcl/ax_yolov8_steps.cc)。

<NewCodeBlock tip="Host" type="Device">

```bash
pip3 install -U "huggingface_hub[cli]"
huggingface-cli download AXERA-TECH/YOLOv8 --local-dir ./YOLOv8
```

</NewCodeBlock>

<NewCodeBlock tip="Host" type="Device">

```bash
cd YOLOv8
./axcl_yolov8 --model ./ax650/yolov8s.axmodel --image ./football.jpg
```

</NewCodeBlock>

```bash
(.venv) rock@rock-5b-plus:~/ssd/axera/YOLOv8$ ./axcl_yolov8 --model ./ax650/yolov8s.axmodel --image ./football.jpg
--------------------------------------
model file : ./ax650/yolov8s.axmodel
image file : ./football.jpg
img_h, img_w : 640 640
--------------------------------------
axclrtEngineCreateContextt is done.
axclrtEngineGetIOInfo is done.

grpid: 0

input size: 1
    name:   images
        1 x 640 x 640 x 3


output size: 3
    name: /model.22/Concat_output_0
        1 x 80 x 80 x 144

    name: /model.22/Concat_1_output_0
        1 x 40 x 40 x 144

    name: /model.22/Concat_2_output_0
        1 x 20 x 20 x 144

==================================================

Engine push input is done.
--------------------------------------
post process cost time:5.02 ms
--------------------------------------
Repeat 1 times, avg time 4.54 ms, max_time 4.54 ms, min_time 4.54 ms
--------------------------------------
detection num: 7
 0:  93%, [ 757,  215, 1131, 1156], person
 0:  93%, [   0,  354,  311, 1104], person
 0:  93%, [1351,  342, 1627, 1032], person
 0:  91%, [ 488,  478,  661,  998], person
32:  87%, [ 773,  889,  829,  939], sports ball
32:  77%, [1231,  876, 1280,  922], sports ball
 0:  60%, [1840,  690, 1906,  809], person
--------------------------------------

```

<div style={{textAlign: 'center'}}>
   <img src="/en/img/aicore-ax-m1/yolov8_out.webp"/>
   yolov8 demo output
</div>

## Model Benchmark

`axcl_run_model` tool can directly infer any compiled axmodel, please refer to the following instructions for usage.

<NewCodeBlock tip="Host" type="Device">

```bash
axcl_run_model --help
```

</NewCodeBlock>

```bash
rock@rock-5b-plus:~$ axcl_run_model --help
usage: axcl_run_model --model=string [options] ...
options:
  -m, --model            path to a model file (string)
  -r, --repeat           repeat times running a model (int [=1])
  -w, --warmup           repeat times before running a model to warming up (int [=1])
  -s, --sleep            sleep millisecond after running a model once (int [=0])
  -v, --vnpu             type of Visual-NPU inited {0=Disable, 1=STD, 2=BigLittle, 3=LittleBig} (int [=0])
  -a, --affinity         npu affinity when running a model (int [=7])
  -p, --parallel         parallel run model using all affinity npu cores (int [=0])
  -b, --batch            the batch will running (int [=0])
  -g, --group            the selected group of shapes (int [=0])
  -i, --input-folder     the folder of each inputs (folders) located (string [=])
  -o, --output-folder    the folder of each outputs (folders) will saved in (string [=])
  -l, --list             the list of inputs which will test (string [=])
  -c, --config           axcl config file "axcl.json" path (string [=/usr/local/axcl/axcl.json])
  -d, --device           axcl device index (int [=0])
  -x, --api              api, 0="axcl runtime", 1="axcl native" (int [=0])
      --verify           verify outputs after running model
  -?, --help             print this message
```

### Download Precompiled Model

As an example, download the pre-compiled yolov8 axmodel model from [AXERA Huggingface](https://huggingface.co/AXERA-TECH).

<NewCodeBlock tip="Host" type="Device">

```bash
wget https://huggingface.co/AXERA-TECH/YOLOv8/resolve/main/ax650/yolov8s.axmodel
```

</NewCodeBlock>

### Model Benchmark

Use `axcl_run_model` tool to run the specified model for a specified number of inference loops to get the inference time of the model.

<NewCodeBlock tip="Host" type="Device">

```bash
axcl_run_model --model yolov8s.axmodel -r 100
```

</NewCodeBlock>

```bash
rock@rock-5b-plus:~$ axcl_run_model --model yolov8s.axmodel -r 100
   Run AxModel:
         model: yolov8s.axmodel
          type: 3 Core
          vnpu: Disable
        warmup: 1
        repeat: 100
         batch: { auto: 1 }
    axclrt ver: 1.0.0
   pulsar2 ver: 3.2-patch1 34eb86c7
      tool ver: 0.0.1
      cmm size: 11821670 Bytes
  ---------------------------------------------------------------------------
  min =   4.222 ms   max =   4.787 ms   avg =   4.562 ms  median =   4.547 ms
   5% =   4.379 ms   90% =   4.698 ms   95% =   4.726 ms     99% =   4.787 ms
  ---------------------------------------------------------------------------
```
