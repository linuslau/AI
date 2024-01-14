# Llama2 Distribution

- [Llama2 Distribution](#llama2-distribution)
  - [Install WSL](#install-wsl)
  - [Install Miniconda](#install-miniconda)
  - [Download Model](#download-model)
  - [Download Llama2](#download-llama2)
  - [Install Dependency](#install-dependency)
  - [Run Interface](#run-interface)
  - [Errors](#errors)
    - [Due to Host Memory Size (16G), Not GPU Memory Size](#due-to-host-memory-size-16g-not-gpu-memory-size)
    - [Run example\_text\_completion with Max\_Batch\_Size 4](#run-example_text_completion-with-max_batch_size-4)

## Install WSL

Refer to [002_WSL](../../00_Setup/Notes/002_WSL.md)

## Install Miniconda

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
```

For more detail, refer to [003_Miniconda](../../00_Setup/Notes/003_Miniconda.md)

## Download Model

```
git clone https://huggingface.co/meta-llama/Llama-2-7b
git clone https://huggingface.co/meta-llama/Llama-2-7b-chat
```

## Download Llama2

```
git clone https://github.com/facebookresearch/llama.git
```

## Install Dependency

```
cd llama
sudo pip install -e .
```

## Run Interface

* Run example_text_completion.py
  
  ```
  torchrun --nproc_per_node 1 example_text_completion.py --ckpt_dir ../share/models/Llama-2-7b/ --tokenizer_path ../share/models/Llama-2-7b/tokenizer.model --max_seq_len 128 --max_batch_size 4
  ```
  
  ![10_Run_example_text_completion](../00_Llama/Images/00_Llama2_Distribution_On_WSL/10_Run_example_text_completion.png)
  ![11_Run_example_text_completion_Memory](../00_Llama/Images/00_Llama2_Distribution_On_WSL/11_Run_example_text_completion_Memory.png)
  ![12_Run_example_text_completion_Memory_GPU](../00_Llama/Images/00_Llama2_Distribution_On_WSL/12_Run_example_text_completion_Memory_GPU.png)
  ![13_Run_example_text_completion_Memory_GPU](../00_Llama/Images/00_Llama2_Distribution_On_WSL/13_Run_example_text_completion_Memory_GPU.png)
  ![14_Run_example_text_completion_Result](../00_Llama/Images/00_Llama2_Distribution_On_WSL/14_Run_example_text_completion_Result.png)

* Run example_chat_completion.py
  
  ```
  torchrun --nproc_per_node 1 example_chat_completion.py --ckpt_dir ../share/models/Llama-2-7b-chat/ --tokenizer_path ../share/models/Llama-2-7b-chat/tokenizer.model --max_seq_len 512 --max_batch_size 6
  ```
  
  ![20_example_chat_completion](../00_Llama/Images/00_Llama2_Distribution_On_WSL/20_example_chat_completion.png)
  ![21_example_chat_completion_GPU_Memory](../00_Llama/Images/00_Llama2_Distribution_On_WSL/21_example_chat_completion_GPU_Memory.png)
  ![23_example_chat_completion_Result](../00_Llama/Images/00_Llama2_Distribution_On_WSL/23_example_chat_completion_Result.png)

## Errors

### Due to Host Memory Size (16G), Not GPU Memory Size
* Error Message
![00_CUDA_Out_Of_Memory_Error]
(../00_Llama/Images/00_Llama2_Distribution_On_WSL/00_CUDA_Out_Of_Memory_Error.png)
* Memory Usage Change
![01_CUDA_Out_Of_Memory_Memory_Consumption_1](../00_Llama/Images/00_Llama2_Distribution_On_WSL/01_CUDA_Out_Of_Memory_Memory_Consumption_1.png)
![02_CUDA_Out_Of_Memory_Memory_Consumption_2](../00_Llama/Images/00_Llama2_Distribution_On_WSL/02_CUDA_Out_Of_Memory_Memory_Consumption_2.png)
![03_CUDA_Out_Of_Memory_Memory_Consumption_3](../00_Llama/Images/00_Llama2_Distribution_On_WSL/03_CUDA_Out_Of_Memory_Memory_Consumption_3.png)
![04_CUDA_Out_Of_Memory_Memory_Consumption_4](../00_Llama/Images/00_Llama2_Distribution_On_WSL/04_CUDA_Out_Of_Memory_Memory_Consumption_4.png)
![05_CUDA_Out_Of_Memory_Memory_Consumption_5](../00_Llama/Images/00_Llama2_Distribution_On_WSL/05_CUDA_Out_Of_Memory_Memory_Consumption_5.png)
![06_CUDA_Out_Of_Memory_Memory_Consumption_6](../00_Llama/Images/00_Llama2_Distribution_On_WSL/06_CUDA_Out_Of_Memory_Memory_Consumption_6.png)
![07_CUDA_Out_Of_Memory_Memory_Consumption_7](../00_Llama/Images/00_Llama2_Distribution_On_WSL/07_CUDA_Out_Of_Memory_Memory_Consumption_7.png)

### Run example_text_completion with Max_Batch_Size 4

![30_Run_example_text_completion_Max_Batch_Size_4_Memory](../00_Llama/Images/00_Llama2_Distribution_On_WSL/30_Run_example_text_completion_Max_Batch_Size_4_Memory.png)
![31_Run_example_text_completion_Max_Batch_Size_4_Memory_GPU](../00_Llama/Images/00_Llama2_Distribution_On_WSL/31_Run_example_text_completion_Max_Batch_Size_4_Memory_GPU.png)
![32_Run_example_text_completion_Max_Batch_Size_4_Error](../00_Llama/Images/00_Llama2_Distribution_On_WSL/32_Run_example_text_completion_Max_Batch_Size_4_Error.png)