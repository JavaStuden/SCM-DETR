# SCM-DETR
# Procambarus clarkii Gonad Dataset

本数据集用于小龙虾（Procambarus clarkii）性别检测研究，主要基于小龙虾性腺区域图像进行目标检测与分类标注。数据集可用于训练和评估小龙虾性腺识别、雌雄判别以及相关水产养殖智能检测模型。

## 数据集简介

数据集中包含小龙虾图像及其对应标注文件，标注格式采用 YOLO 目标检测格式。每张图像对应一个同名 `.txt` 标注文件，标注内容包括类别编号以及归一化后的目标框坐标。

YOLO 标注格式如下：

```text
class_id x_center y_center width height
```

其中 `x_center`、`y_center`、`width`、`height` 均为相对于图像宽高归一化后的数值。

## 类别映射

| 类别编号 | 类别名称 | 说明 |
| --- | --- | --- |
| 0 | cray | 小龙虾目标 |
| 1 | female | 雌性性腺目标 |
| 2 | male | 雄性性腺目标 |

## 数据集结构

解压后数据集目录结构如下：

```text
Procambarus-clarkii-Gonad-Dataset/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
└── labels/
    ├── train/
    ├── val/
    └── test/
```

各子集规模如下：

| 子集 | 图像数量 | 标签数量 |
| --- | ---: | ---: |
| train | 4000 | 4000 |
| val | 497 | 497 |
| test | 500 | 500 |

数据集中共包含 4997 张图像及 4997 个标注文件。

## 标注统计

按目标实例数量统计，各类别数量如下：

| 类别编号 | 类别名称 | 目标数量 |
| --- | --- | ---: |
| 0 | cray | 5051 |
| 1 | female | 2865 |
| 2 | male | 2078 |

## 数据集文件

当前数据集压缩包本地路径为：

```text
F:\2025110317-代刘斌-ViT\Procambarus-clarkii-Gonad-Dataset.zip
```

压缩包大小约为 3.52 GB。解压后根目录名称为：

```text
Procambarus-clarkii-Gonad-Dataset
```

## 使用说明

使用前请先解压数据集压缩包，并在训练配置文件中指定图像目录和标签目录。若使用 YOLO 系列目标检测模型，可按照 `images/train`、`images/val`、`images/test` 与对应 `labels` 目录组织训练、验证和测试流程。

类别配置示例：

```yaml
names:
  0: cray
  1: female
  2: male
```

## Citation

如果该数据集用于论文、项目或公开报告，请在使用时注明数据集名称：

```text
Procambarus clarkii Gonad Dataset
```
