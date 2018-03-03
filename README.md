# HCP Pipelines 

The HCP Pipelines product is a set of tools (primarily, but not exclusively,
shell scripts) for processing MRI images for the [Human Connectome Project][HCP]. 
Among other things, these tools implement the Minimal Preprocessing Pipeline 
(MPP) described in [Glasser et al. 2013][GlasserEtAl]

For further information, please see:

* The [Release Notes, Installation, and Usage][release-install-use] document
  for the current release,
* The [FAQ][FAQ], and
* Other documentation in the project [Wiki][wiki]

Discussion of HCP Pipeline usage and improvements can be posted to the 
hcp-users discussion list. Sign up for hcp-users at 
[http://humanconnectome.org/contact/#subscribe][hcp-users-subscribe]


<!-- References -->

[HCP]: http://www.humanconnectome.org
[GlasserEtAl]: http://www.ncbi.nlm.nih.gov/pubmed/23668970
[release-install-use]: https://github.com/Washington-University/Pipelines/wiki/v3.4.0-Release-Notes,-Installation,-and-Usage
[FAQ]: https://github.com/Washington-University/Pipelines/wiki/FAQ
[wiki]: https://github.com/Washington-University/Pipelines/wiki
[hcp-users-subscribe]: http://humanconnectome.org/contact/#subscribe

# Difference from main repo

This repository and the changes made, were done in order to create a BIDS-application for the HCP pipelines.  The reasons for the commits are:
- remove local-affine-method.  See this discussion: https://www.mail-archive.com/hcp-users@humanconnectome.org/msg05803.html.  The option `-local-affine-method` is not included in the latest release of connectome-workbench, so shouldn't be included in the pipelines*. 
- add option for non-gpu.  The latest version assumes that DWI data will be analysed on GPU.  I added an option to "turn off GPU" when using the bids-app.
- use freesurfer 6.0 (from fs-6 branch on pipelines)


*_I've tried to compile connectome-wb (that would allow local-affine) from source in a container for 6 days on Ubuntu 14.04, 16.04, 17.10, with much debugging and I couldn't get it to work, so unless someone else wants to try, this is definitely the best option until a new compiled version is released._
