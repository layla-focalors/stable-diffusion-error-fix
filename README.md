# stable-diffusion-error-fix
stable diffusion :: torch _ [ Torch is not able to use GPU; add --skip-torch-cuda-test to COMMANDLINE_ARGS variable to disable this check ] fix solution   

First of all, this document does not provide a specific program or SW. It's just my solution, please refer to it   

### Trying Model
https://github.com/AUTOMATIC1111/stable-diffusion-webui   

### My System
1. Enterprise GPU - NVIDIA RTX 6000 ( Multi )
2. Ubuntu 22.04
3. Cuda 11.6

### Solution
1.USE NVIDIA-SMI TO CHECK THE CUDA VERSION. ( 11.6 for me )
2. Find "prepare_environment" in the module/launch_utils.py file. (ctrl+f for vsc)
3. [ torch_index_url = os.environ.get('TORCH_INDEX_URL', "https://download.pytorch.org/whl/cu118")] In this part, change the value of {cu118} to the cuda version that we saw in 1 earlier. (In my case, the workaround may not work for cu116, example 11.8 -> cu118, 11.6 -> cu116,

Just it all.  
i success to run ubuntu cluster server and it work great  

Originally, I wanted to provide the source code, but I don't think it's possible due to the security of my place. Sorry
