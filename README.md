# weheartgaming/motion

[Motion](https://github.com/Motion-Project/motion) is a program that monitors the video signal from one or more cameras and is able to detect if a significant part of the picture has changed. Or in other words, it can detect motion.

# Usage

```sh
docker run \
	-d \
	--name=motion \
	--restart=unless-stopped \
	--device='/dev/video0:/dev/video0' \
	-v '</path/to/config>:/etc/motion' \
	-v '</path/to/media>:/media' \
	-p 8080:8080 \
	weheartgaming/motion
```

# Config

https://motion-project.github.io/motion_config.html#The_Config_Files

motion.conf

```
stream_port 8080
stream_localhost off
target_dir /media/
```

# Parameters

* `--device='/dev/video0:/dev/video0'` - Give the container access the webcam
* `-v '/home/user/motion/config:/etc/motion'` - The location of the config folder
* `-v '/home/user/motion/media:/media'` - The location of the pictures being saved
