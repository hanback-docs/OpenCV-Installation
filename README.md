# OpenCV 설치 (OpenCV Installation)
> ###### 이 과정은 OpenCV 4.2.x 버전 설치에 대한 안내이므로 이 외 버전에서는 예기치 못한 문제가 발생할 수 있습니다.
> ###### This process is a guide about to install 4.2.x version, so unexpected problems can occur in other versions.
   
<br>

## 1. 의존성 라이브러리 설치 (Installs dependency libraries)
    sudo apt install -y build-essential cmake libavcodec-dev 
    sudo apt install -y libavformat-dev libavutil-dev libeigen3-dev 
    sudo apt install -y libglew-dev libgtk2.0-dev libgtk-3-dev 
    sudo apt install -y libjpeg-dev libpng-dev libpostproc-dev 
    sudo apt install -y libswscale-dev libtbb-dev libtiff5-dev 
    sudo apt install -y libv4l-dev libxvidcore-dev libx264-dev 
    sudo apt install -y zlib1g-dev libgstreamer1.0-dev 
    sudo apt install -y libgstreamer-plugins-base1.0-dev libatlas-base-dev pkg-config
    sudo apt install -y libtbb2 mesa-utils libgl1-mesa-dri gfortran
    
<br><br>

## 2. 설치 파일 다운로드 (Download the installation file)
    wget -O opencv.zip https://github.com/opencv/opencv/archive/4.2.0.zip
    wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/4.2.0.zip
    unzip opencv.zip
    unzip opencv_contrib.zip
    
<br><br>

## 3. 빌드 환경 설정 (Set the build configuration)
    cd opencv-4.2.0
    mkdir build
    cd build
    make -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_CUDA=ON -D OPENCV_DNN_CUDA=ON -D CUDA_FAST_MATH=ON -D CUDA_ARCH_BIN=${ARCH_BIN} -D CUDA_ARCH_PTX="" -D ENABLE_FAST_MATH=ON -D WITH_CUBLAS=ON -D WITH_CUFFT=ON -D WITH_NVCUVID=ON -D WITH_FFMPEG=ON -D WITH_LIBV4L=ON -D WITH_V4L=ON -D WITH_GSTREAMER=ON -D WITH_GSTREAMER_0_10=OFF -D WITH_GTK=ON -D WITH_OPENGL=ON -D BUILD_JASPER=ON -D ENABLE_FAST_MATH=ON -D OPENCV_ENABLE_NONFREE=ON -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D BUILD_opencv_python_tests=OFF -D INSTALL_TESTS=OFF -D INSTALL_C_EXAMPLES=OFF -D INSTALL_PYTHON_EXAMPLES=YES -D BUILD_NEW_PYTHON_SUPPORT=ON -D BUILD_opencv_python3=ON -D OPENCV_GENERATE_PKGCONFIG=ON -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules -D BUILD_EXAMPLES=OFF -D WITH_TBB=ON -D BUILD_TBB=ON ../
    
<br><br>

## 4. 빌드 및 설치 (Build and install)
    make -j4
    sudo make install

