# 安装

下载地址：https://ollama.com/

默认選項安装即可。

# 下载模型

在终端窗口輸入命令，下载需要的模型。

例如本項目默认使用的大語言模型是`qwen2.5-7b`，嵌入模型是`bge-m3`，可通過以下命令下载：
```
ollama pull qwen2.5:7b-instruct-q4_K_M
ollama pull bge-m3:latest
```

*注：MacOS系统m1/m2芯片，16G以上内存，建议使用qwen2.5-7b模型。Windows系统30/40系列N卡，12G以上显存，可使用qwen2.5-14b或更大的量化模型*

# 运行

可直接双击Ollama图標启動服務，也可通過命令行启動：
```
ollama serve
```

# 配置

## 開启API

Windows系统启動服務前需要先配置系统环境变量，否則访問API服務报403错误：
```
OLLAMA_HOST=0.0.0.0
OLLAMA_ORIGINS=*
```
配置方法：
右键“我的電腦”->属性->高級系统设置->环境变量->系统变量->新建。
在`变量名`和`变量值`中分别填入`OLLAMA_HOST`和`0.0.0.0`，即完成對`OLLAMA_HOST`环境变量的配置。其餘环境变量同理。

MacOS系统通過以下命令设置环境变量：
```
launchctl setenv OLLAMA_HOST "0.0.0.0"
launchctl setenv OLLAMA_ORIGINS "*"
```

*启動後默认监聽端口：11434*

# 常用设置

## 1. 解决外网访問的問題
```
OLLAMA_HOST=0.0.0.0
```

## 2. 解决Windows系统默认將模型下载到C盘的問題
```
OLLAMA_MODELS=E:\OllamaModels
```

## 3. 设置模型加载到内存中保留2小時
*默认情況下，模型在卸载之前會在内存中保留 5 分鐘*
```
OLLAMA_KEEP_ALIVE=2h
```

## 4. 修改默认端口
```
OLLAMA_HOST=0.0.0.0:8000
```

## 5. 设置多個用户並发請求
```
OLLAMA_NUM_PARALLEL=2
```

## 6. 设置同時加载多個模型
```
OLLAMA_MAX_LOADED_MODELS=2
```
