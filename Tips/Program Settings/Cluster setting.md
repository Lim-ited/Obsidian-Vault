Hook error / Error propagation
=> Effective distance reduction


CPU
교내 접속 IP : 1.233.219.95
외부 접속 IP : 49.50.134.23 

GPU
교내 접속 IP : 1.233.213.110
외부 접속 IP : 49.50.134.23

ssh hmlim@1.233.219.95
ssh hmlim@49.50.134.23 -p 2244

Login node
module avail 
python3 -m venv py313-env


test.py
from mpi4py import MPI

comm = MPI.COMM_WORLD z
rank = comm.Get_rank()
size = comm.Get_size()

print(f'MPI size={size}, rank={rank}')



run.sh

#! /usr/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=128
#SBATCM --cpus-per-task=1

export OMP_NUM_THREADS=$SLURM_CPUS_PER_TASK
mipexec python3 test.py > out.dat


(env) [hmlim@shor ~]$ sbatch run.sh



[hmlim@shor ~]$ python3 -m venv env
[hmlim@shor ~]$ ls
env
[hmlim@shor ~]$ . ./env/bin/activate
(env) [hmlim@shor ~]$ pip install mpi4py



run.sh
#!/usr/bin/bash
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=128
#SBATCH --cpus-per-task=1

module load python/python-3.13.13
module load gcc15/openmpi-5.0.10
export OMP_NUM_THREADS=$SLURM_CPUS_PER_TASK
mpiexec python3 test.py > out.dat



test.py
from mpi4py import MPI

comm = MPI.COMM_WORLD
rank = comm.Get_rank()
size = comm.Get_size()

print(f'MPI size={size}, rank={rank}')



ssh-keygen -t ed25519
cat .sssh/id_ed5519.pub

vi .ssh/authorizedkeys

sbatch
squeue
