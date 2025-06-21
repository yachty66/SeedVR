1. Launch four h100 sxm (gpu_4x_h100_sxm5) on lambdalabs 
2. git clone https://github.com/yachty66/SeedVR.git
3. pip install -r requirements.txt
4. pip install flash_attn==2.5.9.post1 --no-build-isolation
5. apex

pip uninstall -y apex
git clone https://github.com/NVIDIA/apex
cd apex

6. take the `setup_apex_for_lambda.py` and replace the `setup.py` file in the apex folder with it
7. python setup.py install --user --cpp_ext --cuda_ext
8. upload a video and name it video.mp4
9. run `downloader.py` 
10. apt-get update
11. apt-get install -y ffmpeg
12. PYTHONPATH=. torchrun --nproc-per-node=4 projects/inference_seedvr2_7b.py --video_path input_folder --output_dir output_folder --seed 2 --res_h 720 --res_w 1280 --sp_size 2

