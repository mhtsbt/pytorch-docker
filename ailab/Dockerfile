FROM nvidia/cuda:10.2-base-ubuntu18.04

RUN apt-get update
RUN apt-get install -y git python3 nano python3-pip libsm6 libxrender-dev screen tmux sudo htop ffmpeg python-opengl rsync

RUN git config --global user.email "matthias.hutsebaut@gmail.com"
RUN git config --global user.name "mhtsbt"
RUN git config --global credential.helper 'cache –timeout 28800'

RUN pip3 install --no-cache-dir torch tensorflow-gpu numpy tensorboard matplotlib Pillow tabulate ray pandas opencv-python gym[atari] gym ray[tune] tensorboardX

COPY bash_aliases /root/.bash_aliases

# ENV VARS
ENV MKL_NUM_THREADS=2
ENV NUMEXPR_NUM_THREADS=2
ENV OMP_NUM_THREADS=2

CMD ["tail","-f","/dev/null"]
