---
layout: default
---

##  FT_PREPARE_MESH

Note that this reference documentation is identical to the help that is displayed in MATLAB when you type "help ft_prepare_mesh".

`<html>``<pre>`
    `<a href=/reference/ft_prepare_mesh>``<font color=green>`FT_PREPARE_MESH`</font>``</a>` creates a triangulated surface mesh for the volume
    conduction model. The mesh can either be selected manually from raw
    mri data or can be generated starting from a segmented volume
    information stored in the mri structure. `<a href=/reference/ft_prepare_mesh>``<font color=green>`FT_PREPARE_MESH`</font>``</a>` can be used
    to create a cortex hull, i.e. the smoothed envelope around the pial
    surface created by freesurfer. The result is a bnd structure which
    contains the information about all segmented surfaces related to mri
    sand are expressed in world coordinates.
 
    Use as
    bnd = ft_prepare_mesh(cfg, mri)
    bnd = ft_prepare_mesh(cfg, seg)
    bnd = ft_prepare_mesh(cfg)  # for cortexhull
 
    Configuration option
    cfg.method      = string, can be 'interactive', 'projectmesh', 'iso2mesh', 'isosurface',
                      'headshape', 'hexahedral', 'tetrahedral', 'cortexhull'
    cfg.tissue      = cell-array with tissue types or numeric vector with integer values
    cfg.numvertices = numeric vector, should have same number of elements as cfg.tissue
    cfg.downsample  = integer number (default = 1, i.e. no downsampling), see `<a href=/reference/ft_volumedownsample>``<font color=green>`FT_VOLUMEDOWNSAMPLE`</font>``</a>`
    cfg.spmversion  = string, 'spm2', 'spm8', 'spm12' (default = 'spm8')
 
    For method 'headshape you should specify
    cfg.headshape   = a filename containing headshape, a Nx3 matrix with surface
                      points, or a structure with a single or multiple boundaries
 
    For method 'cortexhull' you should specify
    cfg.headshape   = sting, filename containing the pial surface computed by freesurfer recon-all
 
    To facilitate data-handling and distributed computing you can use
    cfg.inputfile   =  ...
    cfg.outputfile  =  ...
    If you specify one of these (or both) the input data will be read from a *.mat
    file on disk and/or the output data will be written to a *.mat file. These mat
    files should contain only a single variable, corresponding with the
    input/output structure.
 
    Example
    mri             = ft_read_mri('Subject01.mri');
 
    cfg             = [];
    cfg.output      = {'scalp', 'skull', 'brain'};
    segmentation    = ft_volumesegment(cfg, mri);
 
    cfg             = [];
    cfg.tissue      = {'scalp', 'skull', 'brain'};
    cfg.numvertices = [800, 1600, 2400];
    bnd             = ft_prepare_mesh(cfg, segmentation);
 
    cfg             = [];
    cfg.method      = 'cortexhull';
    cfg.headshape   = '/path/to/surf/lh.pial';
    cfg.fshome      = '/path/to/freesurfer dir';
    cortex_hull     = ft_prepare_mesh(cfg);
 
    See also `<a href=/reference/ft_volumesegment>``<font color=green>`FT_VOLUMESEGMENT`</font>``</a>`, `<a href=/reference/ft_prepare_headmodel>``<font color=green>`FT_PREPARE_HEADMODEL`</font>``</a>`, `<a href=/reference/ft_plot_mesh>``<font color=green>`FT_PLOT_MESH`</font>``</a>`
`</pre>``</html>`
