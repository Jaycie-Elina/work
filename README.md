# 员工离职预测项目

## 项目简介

本项目旨在通过机器学习模型预测员工离职的可能性。我们使用了两种不同的模型：**随机森林分类器（Random Forest Classifier）** 和 **逻辑回归（Logistic Regression）**。通过对比不同模型的性能，我们选择了最优的模型进行预测。项目的主要步骤包括数据预处理、特征工程、模型训练与调参、模型评估等。

### 数据集
数据集包含了员工的个人信息、工作环境、工作满意度等特征，目标变量是员工是否离职（Attrition）。数据集经过预处理后，用于训练和测试模型。

### 模型
1. **随机森林分类器**：通过网格搜索和交叉验证对模型进行调参，找到最优的模型参数。
2. **逻辑回归**：通过不同的预处理方法（如归一化、对数归一化）和是否使用 SMOTE 过采样技术，评估模型的性能。

### 评估指标
模型的评估指标包括准确率、交叉验证准确率、精确率、召回率、F1分数等。

---

## 项目脉络图

```py
employee-attrition-prediction/
├── data/                     # 数据集文件夹
│ ├── pfm_train.csv           # 原始数据集
│ ├── df_drop.csv             # 预处理后的删去部分变量数据集
│ └── df.csv                  # 预处理后的全部变量数据集
├── code/                     # 代码文件夹
│ ├── preprocess.ipynb        # 数据预处理代码
│ ├── LR.ipynb                # 逻辑回归模型训练与评估代码
│ ├── rfc.ipynb               # 随机森林模型训练与调参代码
│ ├── rfc_smote.ipynb         # SMOTE采样后随机森林模型训练与调参代码
│ └── draw.ipynb              # 数据可视化画图代码
├── requirements.txt          # 依赖包列表
├── README.md                 # 项目说明文件
```
---

## 复现说明

### 运行环境
- **Python 版本**: 3.9.13
- **操作系统**: 推荐使用 Windows 10 或 Linux/Ubuntu 20.04

### 依赖包及版本
以下是项目运行所需的 Python 包及其版本：
- `numpy`: 1.21.5
- `pandas`: 1.4.2
- `scikit-learn`: 1.0.2
- `imbalanced-learn`: 0.9.0
- `matplotlib`: 3.5.1
- `plotnine`: 0.10.1

可以通过以下命令安装所需的依赖包：
```bash
pip install -r code/requirements.txt
```




---

## 复现步骤
### 1. 克隆项目仓库
首先，克隆项目仓库到本地:
```bash
git clone https://github.com/your-username/employee-attrition-prediction.git
cd employee-attrition-prediction
```
### 2. 准备数据集
确保数据集文件 `df.csv`、`df_drop.csv` 和 `pfm_train.csv` 位于项目目录中。这些文件分别包含原始数据和经过预处理后的数据。

### 3. 数据预处理
运行 `preprocess.ipynb` 文件，进行数据清洗、特征选择、归一化等预处理操作。预处理后的数据将保存在 `df_drop.csv` 中。

### 4. 模型训练与评估

逻辑回归模型：运行 `LR.ipynb` 文件，使用不同的预处理方法（如归一化、对数归一化）和是否使用 SMOTE 过采样技术，训练和评估逻辑回归模型。

随机森林模型：运行 `rfc.ipynbr`, `rfc_smote.ipynb` 文件，通过网格搜索和交叉验证对随机森林模型进行调参，并评估模型性能。

### 5. 数据可视化
运行 `draw.ipynb` 文件，生成模型训练过程中的可视化图表，如准确率变化图、特征重要性图等。
