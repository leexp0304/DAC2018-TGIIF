# Prerequisites

Please follow the steps below to modify the boot setting and install the package.
The file you need is attached.

1.  Copy and change the devicetree.dtb in the SD\_CARD.

2.  Stop the autostart at the booting stage, and then use type the cmds below:
     setenv bootargs 'console=ttyPS0,115200 mem=256M root=/dev/mmcblk0p2 rw earlyprintk rootfstype=ext4 rootwait devtmpfs.mount=1 uio_pdrv_genirq.of_id="generic-uio"'
     setenv fdt_high 0x10000000
     setenv initrd_high 0x10000000
     saveenv
     pri
and then type cmd: reset  
system shall boot successfully, After the linux get started, using 'free -h' to make sure that system available memory is 256M.

3. Install the dnndk package.
copy and unzip the dnndk-lib.zip to the board.
use cmd: sudo ./install.sh to install the dnndk package. Make sure that you see the successful info without any warning or error.

4. Run our code in ipynb.
