# pytorch_cuda_tutorial
The repository is to study pytorch cuda extension.  

## Download libtorch    
  
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
   - Add the path to the Libtorch include directory
   - ${LibtorchDir}/include && ${LibtorchDir}/include/torch/csrc/api/include.
5. Configure library directories
   - Configuration Peroperties -> Linker -> General -> Additional Library -> Directories
   - Add the to the Libtorch library directory  
   - ${LibtorchDir}/lib  
6. Configure linker inputs  
   - Configuration Properties -> Linker -> Input -> Additional Dependencies
   - torch.lib, torch_cpu.lib, torch_cuda.lib(optional, if you use CUDA), c10.lib
7. Add the DLL path to environment variables
   - Configuration Properties -> Debugging -> Environment
   - PATH=%PATH%;${LibtorchDir}lib
8. Setting up Pytorch integration(optional)
   - install python with advanced options -> "Download debug binaries" or "install debug binaries"
   - Add python include directory "${PythonDir}/include"(see 4)
   - Add python library directory "${PythonDir}/libs" (see 5)
   - Add python library dependency python{version}.lib. (if you use debug mode also add python{version}_d.lib)  

