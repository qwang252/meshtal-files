%import a meshtal file twice, divide the data of these two files

%change working directory to the folder containing meshtal files
cd Desktop/pyne
%create a python script
ipython
from pyne.MCNP import Meshtal
%create a Meshtal object d1 and reads the data in meshtal file
d1=Meshtal("meshtal")
%create another Meshtal object d2 and reads the data in meshtal file
d2=Meshtal("meshtal")
%read file
t1=d1.tally[24]
t2=d2.tally[24]
t1/=t2
t1.tags["neutron results"][:]// : stands for all
%expect 1 everywhere
