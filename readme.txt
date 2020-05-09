Install OpenCV 4.1.2 on Raspbian Buster:-
$ chmod +x *.sh
$ ./download_opencv.sh
$ ./install_deps.sh
$ ./build_opencv.sh
$ cd ~/opencv/opencv-4.1.2/build
$ sudo make install


Check you can run "test.py" file using both python 2 and 3 to verify that OpenCV python bindings were successfully installed:-
$ wget "https://upload.wikimedia.org/wikipedia/en/7/7d/Lenna_%28test_image%29.png" -O lenna.jpg
$ python2 test.py lenna.jpg
$ python3 test.py lenna.jpg


WARNING: Users of boards with 1GB of memory
Compiling is very memory intensive, you will likely need to increase your swap size. Assuming you have a reasonably large SD card (>16GB to be safe), follow the procedure below to increase your swap size from the default 100MB to 2GB:-
$ sudo dphys-swapfile swapoff
$ sudo sed -i 's:CONF_SWAPSIZE=.*:CONF_SWAPSIZE=2048:g' /etc/dphys-swapfile
$ sudo reboot
