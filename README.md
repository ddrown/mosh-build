## To download build environment:

    docker pull ddrown/mosh-build

## To build mosh binaries:

    OUTPUTDIR=~/target
    mkdir $OUTPUTDIR
    docker run -v $OUTPUTDIR:/target ddrown/mosh-build

This will create 7 packages in $OUTPUTDIR: 
* mosh\_\*\_arm.ipk.pie
* mosh\_\*\_arm.ipk.nopie
* mosh\_\*\_x86.ipk.pie
* mosh\_\*\_x86.ipk.nopie
* mosh\_\*\_mips.ipk.pie
* mosh\_\*\_mips.ipk.nopie
* ncurses\*\_arm.ipk

The ncurses package is provided for the terminfo files

## To build a modified mosh:

    OUTPUTDIR=~/target
    mkdir $OUTPUTDIR
    docker run -i -t -v $OUTPUTDIR:/target ddrown/mosh-build /home/admin/shell
    [make modifications]
    /home/admin/build
