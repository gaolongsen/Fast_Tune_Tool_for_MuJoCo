# **Fast Tune Tool When you Build up Your MuJoCo Environment**

<img src="https://github.com/JackTony123/picx-images-hosting/raw/master/mujoco.67xg5uq8bg.webp" style="zoom: 10%;" />

You can also find a good-view version for this instruction in my [blog](https://longsengao.com/blog/2024/FastTune/).

When I build up a new MuJoCo environment or need to modify the environment based on the previous environment, especially I want to insert a new `body` or `geom` with a **precise position and rotation** , sometimes it's difficult because of the complexity of the high-DoF model and waste me lots of time​​. Here you can use the tool I support here to help you find your desired placement in quick.

**Preparations**: Please refer the `mujoco-py` setup in my previous blog through this **[link](https://longsengao.com/blog/2024/MuJoCo/)** to install related dependencies.

**How to use:**

1. Drag the `Fast_Tune.py` file in any location on your PC (suggested to put it on the same location of your MuJoCo `xml` file.)

2. Change the two lines on the code  with your own MuJoCo environment file and referred frame:

   ```python
   ref_body_name = "satellite" # Change your refered frame
   xml_test_name = "/home/wam/sat_demo.xml"  # Change your own environment file location 
   ```

3. Then run the file. You will see the scenario like the following:

![](https://github.com/JackTony123/picx-images-hosting/raw/master/tune-(1).8ad96bjcyw.gif)

You can use  `←` `→` `↑` `↓` `F` `B`  on your keyboard to change the frame location; And `Q`/`W`, `A`/`S`, `Z`/`X` to change the row, pitch, yaw roation of the frame. You need to put the frame on your desired location and rotation. Then afterthat, record the data on the right-head dashboard as 

![](https://github.com/JackTony123/picx-images-hosting/raw/master/dash_data.3uuu12gwor.webp)



Note that when the frame is moving, the data on this area is also changing. `W-position` means the position of moving frame relative to the world frame in X, Y, Z; `B-position` means the position of moving frame relative to your specific frame in X, Y, Z;n Similar to  `W-Rotation` and `B-Rotation`. Based on this information, you can change your `xml` in a quick time.



Additionally, I also test in another project and find the effect is good.

![](https://github.com/JackTony123/picx-images-hosting/raw/master/pos_4.5q7etoz6pw.png)
