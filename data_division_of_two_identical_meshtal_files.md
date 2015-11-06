"""this is to import the same meshtal file twice and the divide the 
data of these two files.
"""

from pyne.MCNP import Meshtal
%create a Meshtal object d1 and reads the data in meshtal file
d1=Meshtal("meshtal")
%create another Meshtal object d2 and reads the data in meshtal file
d2=Meshtal("meshtal")
%read file
t1=d1.tally[24]
t2=d2.tally[24]
t1/=t2
t1.tags["neutron results"][:]   // : stands for all
%expect 1 everywhere
