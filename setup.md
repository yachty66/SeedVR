1. Launch two h100 sxm with runpod/pytorch:2.2.0-py3.10-cuda12.1.1-devel-ubuntu22.04 on runpod
2. git clone https://github.com/yachty66/SeedVR.git
3. pip install -r requirements.txt
4. pip install flash_attn==2.5.9.post1 --no-build-isolation
5. install apex:
git clone https://github.com/NVIDIA/apex
cd apex
pip install -v --disable-pip-version-check --no-cache-dir --no-build-isolation --config-settings "--build-option=--cpp_ext" --config-settings "--build-option=--cuda_ext" ./
6. upload a video and name it video.mp4
7. run `downloader.py` 
8. apt-get update
9. apt-get install -y ffmpeg
8. PYTHONPATH=. torchrun --nproc-per-node=2 projects/inference_seedvr2_3b.py --video_path input_folder --output_dir output_folder --seed 2 --res_h 720 --res_w 1280 --sp_size 2

PYTHONPATH=. torchrun --nproc-per-node=2 projects/inference_seedvr2_7b.py --video_path input_folder --output_dir output_folder --seed 2 --res_h 720 --res_w 1280 --sp_size 2


PYTHONPATH=. torchrun --nproc-per-node=2 projects/inference_seedvr2_7b.py --video_path input_folder --output_dir output_folder --seed 2 --res_h 720 --res_w 1280 --sp_size 2

PYTHONPATH=. torchrun --nproc-per-node=4 projects/inference_seedvr2_7b.py --video_path input_folder --output_dir output_folder --seed 2 --res_h 720 --res_w 1280 --sp_size 2
