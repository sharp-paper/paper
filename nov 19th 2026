project_title:communcate robot caw with rasberry pi

goal: camera working


hardware components:rasberry pi 5, sunfounder carmera FPC cable

software: 
         language:python3
         libraries:picamera2, flask, vilib
process:
       Command:rpicam-hello --list-cameras
       Result:Available cameras
        Modes: 'SGBRG10_CSI2P' : 640x480 [62.50 fps - (16, 0)/2560x1920 crop]
                             1296x972 [46.34 fps - (0, 0)/2592x1944 crop]
                             1920x1080 [32.81 fps - (348, 434)/1928x1080 crop]
                             2592x1944 [15.63 fps - (0, 0)/2592x1944 crop]
       Command:rpicam-jpeg -o photo.jpg --width 2592 --height 1944
       Result:[0:01:28.640083728] [1912]  WARN V4L2 v4l2_pixelformat.cpp:346 Unsupported V4L2 pixel format Nc30
              [0:01:28.640114509] [1912]  WARN V4L2 v4l2_pixelformat.cpp:346 Unsupported V4L2 pixel format Nc12
             Mode selection for 2592:1944:12:P
             SGBRG10_CSI2P,640x480/0 - Score: 7832
              SGBRG10_CSI2P,1296x972/0 - Score: 5536
              SGBRG10_CSI2P,1920x1080/0 - Score: 4238.67
               SGBRG10_CSI2P,2592x1944/0 - Score: 1000
             Stream configuration adjusted
           [0:01:28.640345577] [1909]  INFO Camera camera.cpp:1216 configuring streams: (0) 2592x1944-YUV420/sYCC (1) 2592x1944-GBRG_PISP_COMP1/RAW
          [0:01:28.641469464] [1912]  INFO RPI pisp.cpp:1502 Sensor: /base/axi/pcie@1000120000/rp1/i2c@88000/ov5647@36 - Selected sensor format: 2592x1944-SGBRG10_1X10/RAW - Selected CFE format: 2592x1944-PC1g/RAW
Still capture image received
Command: open photo.jpg
Result:The file /Users/youngjinseong/photo.jpg does not exist.

try other way 

(in macbook terminral) Command:scp youngjinseong@youngjinseong.local:~/photo.jpg ~/photo.jpg && open ~/photo.jpg
Result: I can check with macbook preview <img width="2592" height="1944" alt="photo" src="https://github.com/user-attachments/assets/52d2f68c-0bd7-4cba-8798-148c140d1bc3" />
Reason(why not work):I entered command on rasberry pi terminal, not the macbook. to watch photo, I should use macbook terminal

Seoncd goal:live streaming

Command:nano camera_test.py
Enter code: import time
from vilib import Vilib


def main():
    Vilib.camera_start(vflip=False, hflip=False)
    Vilib.display(local=False, web=True)
    print("Enter  http://youngjinseong.local:9000/mjpgz.")
    print("for quit, press control C.")
    try:
        while True:
            time.sleep(1)
    except KeyboardInterrupt:
        pass
    finally:
        Vilib.camera_close()


if __name__ == "__main__":
    main()
Command:sudo python3 camera_test.py
result::~ $ sudo python3 camera_test.py
vilib 0.3.20 launching ...
picamera2 0.3.38

Web display on:
      http://10.0.0.225:9000/mjpg

Starting web streaming ...
Enter  http://youngjinseong.local:9000/mjpgz.
for quit, press control C.
 * Serving Flask app 'vilib.vilib'
 * Debug mode: off

Enter http://youngjinseong.local:9000/mjpgz.
result:This site can’t be reached
 try safari brower
 works
 https://youtube.com/shorts/jBL0OiOdb6Y?feature=share








