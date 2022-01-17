FROM python:3.9
COPY . /GFPGAN
WORKDIR /GFPGAN
RUN apt-get update
RUN apt-get install ffmpeg libsm6 libxext6  -y
RUN pip install torch==1.10
RUN pip install opencv-python
RUN pip install basicsr
RUN pip install facexlib
RUN pip install -r requirements.txt
RUN python setup.py develop
RUN pip install realesrgan
RUN wget https://github.com/TencentARC/GFPGAN/releases/download/v0.2.0/GFPGANCleanv1-NoCE-C2.pth -P  experiments/pretrained_models
#ENTRYPOINT ["python", "inference_gfpgan.py", "--save_root" ,"/results","--upscale", "2", "--test_path"]
CMD python inference_gfpgan.py --save_root results --upscale 2 --test_path inputs_tests