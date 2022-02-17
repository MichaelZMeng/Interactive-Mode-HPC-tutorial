## Interactive-Mode-HPC-tutorial
Interactive Mode (HPC) tutorial on Bash

## 1. Sign in your Discovery7 account
```
$ ssh -Y *******@discovery7.dartmouth.edu
```

## srun manual
```
$ man srun
```
## 2. Set working directory

## 3. After configuring files, run the interactive mode
```
$ srun --pty /bin/bash
```
If the error is
```
Package bash-completion was not found in the pkg-config search path.
Perhaps you should add the directory containing `bash-completion.pc'
to the PKG_CONFIG_PATH environment variable
No package 'bash-completion' found
bash: /yum: No such file or directory
```
install the package
```
$ conda install -c conda-forge bash-completion
```
Proceed ([y]/n)?
```
y
```

## 4. Interactive Mode
```
$ srun --pty /bin/bash
```
if error appears again
```
ç^Csrun: Cancelled pending job step with signal 2
srun: error: Unable to create step for job 1257531: Job/step already completing or completed
```
add your file at the end
```
$ srun --pty /bin/bash snakemake.sbatch
```
## Checking job priorities
```
$ squeue
```
## Checking all available partitions
```
$ sinfo
```
## SLURM
If running on the cluster, please edit the cluster.json config file to match your cluster configuration. Once complete, submit the given sbatch file to the cluster.
```
$ sbatch snakemake.sbatch
```
