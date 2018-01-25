# mpi_benchmark
I am exploring containers for HPC. While Docker is the most popular container, it is not suitable for HPC due to security concerns (see https://fosterelli.co/privilege-escalation-via-docker.html) in supercomputer centers and due to penalties for the performance.
Shifter and Singularity are two alternatives for the HPC use case.

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
 * From an existing Docker image
 ` `
 
 ## Shifter
 
 http://www.nersc.gov/users/software/using-shifter-and-docker/using-shifter-at-nersc/

  
