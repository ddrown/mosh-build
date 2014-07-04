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

As well as the files (extracted from the packages):
* bin/mosh-client.{arm,x86,mips}.{pie,nopie}
* share/terminfo/\*

The terminfo files come from the ncurses package

Options:
add `-e PACKAGE_NAME=com.mosh.kosh.bagosh` to the command line if your terminfo will be in a different package.  mosh-client will expect them in /data/data/$PACKAGE\_NAME/files/share/terminfo/

## To build a modified mosh:

    OUTPUTDIR=~/target
    mkdir $OUTPUTDIR
    docker run -i -t -v $OUTPUTDIR:/target ddrown/mosh-build /home/admin/shell
    [make modifications]
    /home/admin/build
