<B>Code repository:</B> https://github.com/prisms-center/plasticity

<B>What is PRISMS Plasticity?</B>

  It is a Finite Element Method (FEM) code for solving boundary value 
  problems arising in <B>Continuum Plasticity</B> and <B>Crystal Plasticity</B>. 
  It is build on top of the deal.II open source finite element 
  library [http://www.dealii.org]
  
  This code is developed by the PRedictive Integrated Structural
  Materials Science (PRISMS) Center [http://www.prisms-center.org/]
  at University of Michigan which is supported by the U.S. Department 
  of Energy (DOE), Office of Basic Energy Sciences, Division of Materials Sciences 
  and Engineering under Award #DE-SC0008637

<B>Installation:</B>

  1) Install deal.II (version 8.2.1 currently supported)<br>
     + Download Binaries (OSX and Linux) or  Virtual Machine (VMI) from https://www.dealii.org/download.html <br>
     (OR) <br>
     + Configure, compile and install the deal.II library with the 
     following configuration flags. Dependencies are MPI, p4est,
     PETSc libraries.<br>
     -DDEAL_II_WITH_MPI=ON, -DDEAL_II_WITH_LAPACK=ON, -DDEAL_II_WITH_P4EST=ON, -DDEAL_II_WITH_PETSC=ON

     Download: http://www.dealii.org/download.html <br>
     Installation instructions: http://www.dealii.org/8.2.1/readme.html <br>
     Installation instructions for external packages (P4EST, PETSC): https://www.dealii.org/developer/external-libs/

  2) Clone the PRISMS Plasticity GitHub repo https://github.com/prisms-center/plasticity<br>
  + $ git clone git@github.com:prisms-center/plasticity.git <br>
  (OR) <br>
  + $ git clone https://github.com/prisms-center/plasticity.git <br>
  and <br>
  + $ cd plasticity <br>
  + $ git checkout master <br>

<B>Usage:</B>

  Running plasticity applications, for example simple tension
  boundary value problem with continuum plasticity material model:<br> 
  + $ cd applications/continuumPlasticity/simpleTension <br>
  For debug mode [default mode, very slow]: <br>
  + $ cmake CMakeLists.txt -DCMAKE_BUILD_TYPE=Debug <br>
  For optimized mode:<br>
  + $ cmake CMakeLists.txt -DCMAKE_BUILD_TYPE=Release <br>
  and <br>
  + $ make <br><br>
  Execution (serial runs): <br>
  + $ make run <br>
  Execution (parallel runs): <br>
  + $ mpirun -np nprocs ./main <br>
  [here nprocs denotes the number of processors]
  
  Updates: Since plasticity code is still under active development,
  regular code and documentation updates are pushed to the upstream
  repo (https://github.com/prisms-center/plasticity) and we strongly
  recommend users to synchronize their respective clones/forks at regular
  intervals or when requested by the developers through the
  announcements on the mailing list. 

<B>Visualization</B> 

  Output of the primal fields and postprocessed fields is in standard vtk 
  format (parallel:*.pvtu, serial:*.vtu files) which can be visualized with the 
  following open source applications:
  1. VisIt (https://wci.llnl.gov/simulation/computer-codes/visit/downloads)
  2. Paraview (http://www.paraview.org/download/)

<B>Getting started:</B>

  Examples of various boundary value problems are located under the 
  applications/ folder. Easiest way to get started on the code is to 
  run the applications.

  Applications are intended to serve as (1) Demonstration of the
  capabilities of this library, (2) Provide a framework for
  further development of specialized/advanced applications by
  users. 

  Application or code under development/testing is preceded by an
  underscore. 

  List of folders:
  + src/: material models (continuum plasticity and crystal plasticity), 
  ellipticBVP (base class for parallel implementation of elliptic 
  boundary value problems), enrichment models (enhanced strain), 
  utility (static condensation class, crystal orientations and grain 
  information IO)
  + applications/: continuum plasticity and crystal plasticity
  + utils/: IntegrationTools (developed by the PRISMS center and available at
  https://github.com/prisms-center/IntegrationTools) and json headers 
  + docs/: Formulations, user manuals, etc in PDF format
  + html/: HTML documentation generated by doxygen

<B>Documentation:</B>

  Detailed mathematical formulations, example simulations, code documentation, etc, provided:
  + Open html/index.html in any web browser <br>
  (OR)<br>
  + https://htmlpreview.github.io/?https://raw.githubusercontent.com/prisms-center/plasticity/master/html/index.html
 	
<B>License:</B>

  GNU Lesser General Public License (LGPL). Please see the file
  LICENSE for details.

<B>Mailing List:</B>
  
 + prismsplasticity.users@umich.edu	
 + prismsplasticity.dev@umich.edu  

<B>Further information, questions, issues and bugs:</B>

  Contact the developers at prismsplasticity.dev@umich.edu  



