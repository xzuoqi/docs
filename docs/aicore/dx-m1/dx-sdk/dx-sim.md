---
sidebar_position: 3
---

# DX-SIM 推理模拟器

## 介绍

**DX-SIM（模型模拟器）** 通过在 X86 PC 上模拟 DEEPX NPU 硬件功能，实现在 X86 PC 上模拟推理 DXNN 模型。

## 安装方法

请在 DX-M1 SDK [资源下载](../download.md)页面下载 DX-SIM 安装包并解压

<NewCodeBlock tip="X86 PC" type="PC">

```bash
mkdir dx_simulator
tar -xvf dx_simulator_v2.14.5.tar.gz -C dx_simulator && cd dx_simulator
```

</NewCodeBlock>

安装 DX-SIM

<NewCodeBlock tip="X86 PC" type="PC">

```bash
# install prerequisites
./scripts/install_prerequisites.sh

# install python
./scripts/install_python.sh

# install dx_simulator
pip3 install dx_simulator-2.14.5-cp311-cp311-linux_x86_64.whl --force-reinstall
```

</NewCodeBlock>

## 使用方法

### Simulator Class

- 使用 `Simulator` 类，初始化模拟变量

```python
from dx_simulator import Simulator

simulator = Simulator(
    model_path="path/to/graph.dxnn",
    use_gpu=True, # If you want to run the model with gpu.
)
```

### 模拟推理

模拟推理使用 Simulator.run() 函数

- `output_names` 是模型输出的名字列表
- `input_feed` 是一个包含模型输入名字与输入数据的字典

```bash
outputs = simulator.run(
    output_names=["output1", "output2"],
    input_feed={"input": input_array},
)
```

### 生成参考数据

如果您想生成参考数据以与 NPU 的运行时输出进行比较，请参考以下方法

```python
from dx_simulator import Simulator

image_path = "/path/to/image.png"
model_path = "/path/to/graph.dxnn"
save_dir = "/path/to/save_dir"

# Initialize simulator.
simulator = Simulator(
    model_path=model_path,
    mode="debug",
)

# Generate reference data.
simulator.make_gt_with_image_file(
    image_path=image_path,
    save_dir=save_dir,
)
```

### 图片预处理

在使用模拟器进行推理时，输入数据与 NPU 相同，**要求为 `uint8` 类型**。因此，在进行预处理操作时需要注意以下几点：

- 模拟器的输入数据必须为 `uint8` 类型；
- 不能在预处理阶段使用 `Mul`、`Add` 等操作（即乘法、加法），否则数据格式将无法满足 `uint8` 要求；
- 类似的操作（包括 `Normalize`）应当在配置文件中指定，由 **NPU 侧处理**；
- 预处理完成后，**必须进行类型转换为 `np.uint8`**，以确保模拟器能够正确接受输入。

以下是一个示例代码片段，用于构造模拟器前的预处理流程：

```python
import cv2
import numpy as np
from dx_simulator import Simulator

simulator = Simulator(model_path="graph.dxnn", mode="inference")
preprocess = simulator.get_preprocessing() # This can be easily used as image preprocessing module.

input_image = cv2.imread("image.png")
preprocessed_image = preprocess(input_image) # Preprocess an image
outputs = simulator.run(
    output_names=["output1", "output2", "output3"],
    input_feed={"input": preprocessed_image.astype(np.uint8)}
)
```

### Simulator 类成员函数

```bash
from dx_simulator import Simulator
simulator = Simulator(model_path="graph.dxnn")
output = simulator.run(output_names, data) # Run NPU simulation
preprocess = simulator.get_preprocessing() # Return simulator's input preprocessing module
input_metadata = simulator.get_inputs() # Return model's input metadata
output_metadata = simulator.get_outputs() # Return model's output names
```

### 参考代码

更多 DX-SIM 使用请参考 DX-SIM SDK 中 `example` 下的示例代码

```bash
.
├── compiled_results
│   ├── mobilenetv2.dxnn
│   ├── yolov5face.dxnn
│   ├── yolov5pose.dxnn
│   └── yolov5s.dxnn
├── example_classification.py
├── example_generate_ref.py
├── example_yolov5face.py
├── example_yolov5pose.py
├── example_yolov5s.py
└── images
    ├── baseball.jpg
    └── gold_fish.jpg
```
