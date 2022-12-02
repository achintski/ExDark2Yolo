# ExDark2Yolo
### 将ExDark注释的格式数据转换成YOLO格式数据
简体中文 | [English](./README_en.md)
  - ExDark的数据目录结构如下:
    ```text
      ExDark_dataset
        ├── annotations
        │   ├── Bicycle
        │   ├── Boat
        │   ...
        └── images
            ├── Bicycle
            ├── Boat
            ...
    ```
    
  - 转换:
    ```shell
    python exDark2Yolo.py --annotations-dir dataset/annotations \
                          --images-dir dataset/images \
                          --ratio 8:1:1 \
                          --output-dir output
    ```
    - `--annotations-dir`：ExDark的标注目录。
    - `--images-dir`：ExDark的图像目录。
    - `--ratio`：（可选）train/test/val之间的比例，默认为8:1:1。
    - `--output-dir`: （可选）图像和转换后的yolo标注的输出目录。

  - 转换后的目录结构（输出目录）:
    ```text
      output
        ├── images
        │   ├── test
        │   ├── train
        │   └── val
        └── labels
            ├── test
            ├── train
            └── val
    ```