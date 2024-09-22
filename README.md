# pytorch_cuda_tutorial
The repository is to study pytorch cuda extension.  

Download libtorch    
  
Debug:  
https://download.pytorch.org/libtorch/{cuda_version}/libtorch-win-shared-with-deps-debug-{pytorch_version}%2B{cuda_version}.zip  

Release:  
https://download.pytorch.org/libtorch/{cuda_version}/libtorch-win-shared-with-deps-{pytorch_version}%2B{cuda_version}.zip
  
## Environment
Platform: Windows 10  
Tool: MSVC 2022 17.8.5  
  
### Configure Libtorch in MSVC  
1. Install libtorch. (use above link.)
2. Install MSVC with c/c++ devlopment support.
3. Create new project.(Console or Empty).
4. Configure include directory.
   - Configuration Properties -> C/C++ -> General -> Additional Include Directories.  
   - Add the Path to the Libtorch include directory
   - ${LibtorchDir}/include && ${LibtorchDir}/include/torch/csrc/api/include.
5. Configure Library Directories

