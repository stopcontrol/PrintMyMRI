# PrintMyMRI
Brain tissue 3D printing workflow 

# Prerequisites

* A Source:
Structural MRI Scan of your Brain (eg. T1WI) or a [Demo Scan](https://data.idoimaging.com/nifti/1010_brain_mr_02.nii.gz)

* An awesome segmentation and surface reconstruction algorithm:
[Freesurfer](https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall)

* Another comprehensive neuroscience library to use as a little helper, especially to combine single segmented (subcortical) structures from freesurfer into a integrated surface model.
This works for any collection of segmented Regions and helps to combound them to a single modell e.g. combining left and right hemispheres with the cerebellum and the brain stem:
[FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation)

* Something to smooth the surface of your segmented and combounded model:
[Meshlab](https://www.meshlab.net/)

* A nice 3d Slicer:
[Cura](https://ultimaker-cura.de.malavida.com/#gref)

* Optional and a little advanced CAD software for further edits (free for Students):
[Fusion 360](https://www.autodesk.co.uk/campaigns/education/fusion-360)

* Optional free MRI Viewer (comes with Plugins for segmentation eg. if you want to do it that way):
[Mango](http://ric.uthscsa.edu/mango/mango.html)


# Segmentation and surface reconstruction

[Install, source, export](https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall5.3) and [license](https://surfer.nmr.mgh.harvard.edu/registration.html) (free!) Freesurfer. Find a Mac installation Demo [here](https://surfer.nmr.mgh.harvard.edu/fswiki/DownloadAndInstall?action=AttachFile&do=get&target=installFS_demo.mp4).

Troubleshooting: 
Problems with exporting Freeesurfers Home Directory? The way you d it is stated wrong in the FS-Wiki. Using the current version you may have to change export from 

```bash
export FREESURFER_HOME=/Applications/freesurfer
```

to

```bash
export FREESURFER_HOME=/Applications/freesurfer/7.1.1/
```

where /7.1.1 stands for the release number you want to work with (latest at time of writing: 7.1.1). This is an example solution for Mac.

then again try to source your FS copy

```bash
source $FREESURFER_HOME/SetUpFreeSurfer.sh
```
Now you should see something similar to

```
Setting up environment for FreeSurfer/FS-FAST (and FSL)
FREESURFER_HOME /usr/local/freesurfer
FSFAST_HOME     /usr/local/freesurfer/fsfast
FSF_OUTPUT_FORMAT nii
SUBJECTS_DIR    /usr/local/freesurfer/subjects
MNI_DIR         /usr/local/freesurfer/mni
```

Now it's time to [license](https://surfer.nmr.mgh.harvard.edu/registration.html) your FS copy for free.
