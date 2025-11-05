FROM ros:humble-perception

RUN sudo apt-get update
RUN sudo apt-get install -y ros-humble-slam-toolbox ros-humble-tf-transformations ros-humble-cv-bridge
RUN sudo apt-get install -y python3-pip
RUN pip3 install eventlet==0.33.3 Flask==1.1.1 Flask-SocketIO==4.1.0 python-socketio==4.2.0 python-engineio==3.13.0 gevent-websocket==0.10.1 Jinja2==3.0.3 itsdangerous==2.0.1 werkzeug==2.0.3 numpy==1.23.5 pillow opencv-contrib-python transforms3d setuptools==70