---
title: smoothsw.ini
---
When one or more set of swingl/swingh (or lswing/hswing) files are present, ProffieOS will activate the
SmoothSwing V1 or V2 algorithms. To decide which one to use, it will read a file called
"smoothsw.ini", which can contain the following variables: (listed with their default values)
```
# SmoothSwing algorithm version, you probably want to set this to 2.
Version=2

# Degrees of rotations per second required to reach full volume.
# Default is 450.0 (any value)
SwingSensitivity=450

# Smoothswing volume multiplier (defaults to 3x normal volume)
# Default is 3.0 (value between 1 and 5)
MaxSwingVolume=3.0

# What percent the hum sound will decrease as swing increases
# Default is 75.0 (value between 1 and 100)
MaximumHumDucking=75

# Non-linear swing response (higher values make it more non-linear)
# Values greater than 1 will result in the Smoothswing sound staying quieter 
# at lower speeds and then ramping up quickly to full volume a higher speeds. 
# Values less than 1 will result in the Smoothswing volume ramping up quickly 
# at lower speeds and then staying there as you approach full speed. 
# the default is 1.75 (any value)
SwingSharpness=1.75

# Degrees per second needed to register as a smoothswing.
# Default is 20.0 (1 to 360)
SwingStrengthThreshold=20

# Length of first transition in degrees.
# Default is 45.0 (1 to 360)
Transition1Degrees=45

# Length of second transition in degrees.
# Default is 160.0 (1 to 360)
Transition2Degrees=160.0

# If not zero, swngNNN.wav or swngNNN.wav will
# be played when we reach this swing speed.
# Unit is degrees per second, 450 is a reasonable value.
# Default is 0.0
AccentSwingSpeedThreshold=450

# If not zero AND accent swings are on, this defines the threshold for when
# a swing is considered a slash. Unit is degrees per second **per second**.
# NOTE - While 260 is the default value, it is subjective.
# Something like 100 might work better.
# The higher the accent swing threshold, the higher the slash threshold will need to be.
AccentSlashAccelerationThreshold=260.0

# NOTES
# 1. The length of the smoothswing pair wavs has nothing to do with 
# the length of the swing movement or how it transitions. 
# Try setting the SwingSensitivity number so that you're not 
# detecting motion for smaller movements.


# 2. If you find that the same swing pair sounds play for subsequent swings, 
# try adjusting SwingSensitivity. If the saber is moving faster than the threshold velocity,
# it is going to be playing one of the smoothswing pairs on loop.
# The algorithm only picks a new swing pair of swingl and swingh sounds when it thinks 
# it's safe to do so (when you're not in the middle of a swing).
```