
For this project we will use our Flywoo bench, which is quite small but still is able to do awesome things.

PHOTO

### Prepare the Pi Zero

We chose to do this with a Raspberry Pi Zero because of its size factor. It is very underpowered and this aspect presents challenges, but I think it is okay as a platform to mess with. For a serious application we will need a more powerful drone / companion computer.

Refer to [[Setup RPi Zero as Companion computer]] for details.

### Attach Pi to Drone

With a 3D printed case and some plastic wraps, it is pretty good.

PHOTO

### Code

Due to the fact that the MAVRos library required a code change and therefore re-compiling, we chose to go another road, different from the SITL project. We chose to go pure MAVLink.

The setup is quite nice, thanks to `gomavlib` library for `golang`. I love golang and it is the language i'm most comfortable with. It is also very good news that we can build any complex drone program with pure go.

Before attempting to do any code, I should've read the entire MAVLink documentation, which would have saved some time.

The main problem is that I missed the `Heartbeat Protocol`. This is simple: if a MAVLink component doesn't emit a heartbeat, then it will be ignored by other MAVLink components. Therefore, the Pi commands weren't recognized by the drone.
