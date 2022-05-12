# robot-framework-dockerfile

```
nvidia-docker run --runtime=nvidia -it \
                  --env=LOCAL_USER_ID="$(id -u)" \
                  -v /home/sam/DASC/PX4-Autopilot:/src/PX4-Autopilot:rw \
                  -v /home/sam/DASC/px4_ros_bridge:/src/px4_ros_bridge:rw \
                  -e SDL_VIDEODRIVER=$SDL_VIDEODRIVER_VALUE \
                  -e SDL_HINT_CUDA_DEVICE='0' \
                  --net=host \
                  --env="DISPLAY=$DISPLAY" \
                  --env="QT_X11_NO_MITSHM=1" \
                  --volume="/tmp/.X11-unix:/tmp/.X11-unix:rw" \
                  -env="XAUTHORITY=$XAUTH" \
                  --volume="$XAUTH:$XAUTH" \
                  --name=px4_sim_nvidia chenrc98/px4-dev-ros2-foxy-nvidia:latest bash
```
