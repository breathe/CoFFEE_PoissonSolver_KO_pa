CoFFEE v1.1 software package with modified file '/PoissonSolver/PS_3D_cy/ps3d.pyx' for performing Kumagai-Oba potential alignment method (doi: 10.1103/PhysRevB.89.195205). For original version of the CoFFEE software package, see here: https://www.sciencedirect.com/science/article/pii/S0010465518300158

This version of the CoFFEE poisson solver is used in the defect corrections workflow here: https://github.com/skw32/DefectCorrectionsNotebook

README from original CoFFEE_1.1 package
----------------------------------------------------------

CoFFEE: Corrections For Formation Energy and Eigenvalues
is a complete electrostatic corrections package applicable 
to charged defects in 3D (bulk), 2D (slabs, 2D materials) and
1D (nanowires, nanoribbons) systems. The code is released 
under the BSD license. Please cite the following paper if 
you use this code in your work:
https://arxiv.org/abs/1705.01491

The UserGuide.pdf helps you run through the installation,
examples and in setup of your input files for the code.

----------------------------------------------------------

DEPENDENCIES:

1. SciPy (https://www.scipy.org/install.html)
2. NumPy (https://docs.scipy.org/doc/numpy/user/install.html)
3. mpi4py (https://mpi4py.scipy.org/docs/usrman/install.html)
4. matplotlib (http://matplotlib.org/users/installing.html)
(5. Cython, if you wish to make any changes to the Poisson solver)

----------------------------------------------------------

INSTALL:

Run the following command from the CoFFEE folder:

python setup.py build_ext -b PoissonSolver/

This checks for the dependencies and compiles the 
C routines in the folders: 
PoissonSolver/MV_2D_cy/,
PoissonSolver/MV_1D_cy/ and
PoissonSolver/PS_3D_cy/

If you have Cython intalled, this command will first 
Cythonize the .pyx files present in these directories,
and then compile the .c file generated. 

On compiling the C code, this creates the following .so files in 
the PoissonSolver/ folder:
matvec1D.so
matvec2D.so
ps3D.so

(In case these file names have changed for some reason, you would have to 
rename them to the above.)

Run clean.py to remove the .so files before recompilation.

---------------------------------------------------------

To report current bugs or problems, contact 
Mit H. Naik: mitn@iisc.ac.in or 
Manish Jain: mjain@iisc.ac.in

---------------------------------------------------------
