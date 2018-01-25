# mpi_benchmark
I am exploring containers for HPC. While Docker is the most popular container, it is not suitable for HPC due to security concerns (see https://fosterelli.co/privilege-escalation-via-docker.html) in supercomputer centers and due to penalties for the performance.
Shifter and Singularity are two alternatives for the HPC use case.

## Docker

Docker containers can be used with Shifter and Singularity. You can create or explore repositories at https://hub.docker.com/.

### Resources
 * Tips on writing a Dockerfile:
   ** Best practices: https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/
   ** Optimizing: https://medium.com/@esotericmeans/optimizing-your-dockerfile-dc4b7b527756

## Singularity

### Resources
  * An introductory presentation by G.M. Kurtzer, the developer of Singularity.
    
    video: http://singularity.lbl.gov/
    slides: http://www.hpcadvisorycouncil.com/events/2017/stanford-workshop/pdf/GMKurtzer_Singularity_Keynote_Tuesday_02072017.pdf

### How to install on Mac?

http://singularity.lbl.gov/install-mac

#### Troubleshooting
* ```installer: The install failed (The Installer encountered an error that caused the installation to fail. Contact the software manufacturer for assistance.)```

  Go to Preferences and allow the application.
* ```E: You don't have enough free space in /var/cache/apt/archives/.```

  Use `--sandbox` while building the image and `--writable` while running the shell

 #### How to use Singularity?
 * From an existing Docker image: `singularity build lolcow.simg docker://godlovedc/lolcow`
 * From an existing Singularity image: `singularity build mpi_benchmark.simg shub://keceli/mpi_benchmark:ompi_2.1.0`
 * From a Singularity recipe (You need sudo access): `sudo singularity build myimage.simg Singularity`
 
 Check: http://singularity.lbl.gov/quickstart
 
 ## Shifter
 
 http://www.nersc.gov/users/software/using-shifter-and-docker/using-shifter-at-nersc/

  
