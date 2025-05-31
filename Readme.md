## uvc-gadget

> **NOTE**: This repository was originally forked from https://github.com/climberhunt/uvc-gadget, which itself was forked from https://github.com/wlhe/uvc-gadget, which is a fork from the original project... so it's a little bit of a mess here. Anyways, this little aside at the top of the README is the only bit that I have updated in the README so far.
>
> To be perfectly honest, I am still trying to learn the ins-and-outs of uvc-gadget and OTG usage before I feel confident enough to make the README actually comprehensible to humans who are not neck-deep in this stuff. I love good documentation, but I hate misleading or hard-to-read documentation.
>
> Anyways, check out https://github.com/geerlingguy/pi-webcam for the downstream and user-friendly usage of this project.
>
> The main thing is you can choose once (for now) between 720p or 1080p when you set this up—the project currently defaults to 720p, but if you want to switch to 1080p, then BEFORE you run this stuff, find the code with 'For 720p' and comment those parts out, and find the code with 'For 1080p' and uncomment those parts. I hope to make this all so much simpler in the future, allowing easier selection.
>
> – geerlingguy

**Upstream project [uvc-gadget](http://git.ideasonboard.org/uvc-gadget.git) has been updated and continuous maintenance**

**Please refer to http://git.ideasonboard.org/uvc-gadget.git**

UVC gadget userspace enhancement sample application

Fork from  
[uvc-gadget.git](http://git.ideasonboard.org/uvc-gadget.git)  
Apply enhancement Bhupesh Sharma's patchset  
[UVC gadget test application enhancements](https://www.spinics.net/lists/linux-usb/msg84376.html)  
and Robert Baldyga's patchset  
[Bugfixes for UVC gadget test application](https://www.spinics.net/lists/linux-usb/msg99220.html)  

## How to use

    Usage: ./uvc-gadget [options]
    
    Available options are
        -b             Use bulk mode
        -d             Do not use any real V4L2 capture device
        -f <format>    Select frame format
                0 = V4L2_PIX_FMT_YUYV
                1 = V4L2_PIX_FMT_MJPEG
        -h             Print this help screen and exit
        -i image       MJPEG image
        -m             Streaming mult for ISOC (b/w 0 and 2)
        -n             Number of Video buffers (b/w 2 and 32)
        -o <IO method> Select UVC IO method:
                0 = MMAP
                1 = USER_PTR
        -r <resolution> Select frame resolution:
                0 = 360p, VGA (640x360)
                1 = 720p, WXGA (1280x720)
        -s <speed>     Select USB bus speed (b/w 0 and 2)
                0 = Full Speed (FS)
                1 = High Speed (HS)
                2 = Super Speed (SS)
        -t             Streaming burst (b/w 0 and 15)
        -u device      UVC Video Output device
        -v device      V4L2 Video Capture device

## Build  

- host:  
    make
- Cross compile:  
    make ARCH=arch CROSS_COMPILE=cross_compiler  
    eg:  
    make ARCH=arm CROSS_COMPILE=arm-hisiv600-linux-  
- or:  
    set ARCH, CROSS_COMPILE, KERNEL_DIR in Makefile

## Change log

- Apply patchset [Bugfixes for UVC gadget test application](https://www.spinics.net/lists/linux-usb/msg99220.html)  

- Apply patchset [UVC gadget test application enhancements](https://www.spinics.net/lists/linux-usb/msg84376.html)  

- Add Readme/.gitignore and documentations  
  Copy linux-3.18.y/drivers/usb/gadget/function/uvc.h into repository, change include path for build

### Initial

- Fork(copy) from [uvc-gadget.git](http://git.ideasonboard.org/uvc-gadget.git)
