From: michael-tn/mpi-hello-world:ompi3
Bootstrap: shub

%post
echo "************************************************************"
echo "Installling mpiBench from https://github.com/LLNL/mpiBench"
echo "************************************************************"
	git clone https://github.com/LLNL/mpiBench
	cd mpiBench
	make
	
%runscript
	exec /mpiBench/mpiBench
