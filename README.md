# MIACE
MI-ACE and MI-SMF Target Characterization Algorithms
Matlab Implementation

****************************************************************

NOTE: If MI-ACE or MI-SMF Algorithms are used in any publication or presentation, the following reference must be cited:  
A. Zare, C. Jiao, T. Glenn, "Multiple Instance Hyperspectral Target Characterization," IEEE Trans. on Pattern Analysis and Machine Intelligence, To Appear.  

****************************************************************

The command to run either MI-SMF or MI-ACE:   

[optTarget, optObjVal, b_mu, sig_inv_half, init_t] = miTarget(dataBags, labels, parameters)

Inputs:  
+dataBags - cell array where each cell is a bag containing a NxD matrix of instances where N is the number of instances in the bag and D is the dimensionality of each instance  
+labels -  binary values, the same length as dataBags, indicates positive bag with '1'  and negative bags with '0'  
+parameters - parameters structure that can be set using miTargetParameters.m  
    *parameters.methodFlag: set to 0 for MI-SMF, 1 for MI-ACE  
    *parameters.initType: set to 1 for best positive instance based on objective function value  

Outputs:   
+optTarget: estimated target concept  
+optObjVal: Final Objective Function value  
+b_mu: Background Mean to be used in ACE or SMF detector with test data  
+sig_inv_half: Square root of background covariance, Use sig_inv_half'*sig_inv_half as covariance in ACE or SMF detector with test data   
+init_t: initial target concept   

****************************************************************

Files explanation:  
Latest Revision: Sept. 2017

+ace_det.m : ACE Target Detector Code  
+ace_det_local.m : ACE Target Detector Code that takes in a mask for HSI  
+Demo_MUUFLGulfport.m: Demo script to run MI-SMF and MI-ACE on MUUFLGulfport Hyperspectral Data  
+Demo_SimulatedHSIData.m: Demo script to run MI-SMF and MI-ACE on simulated Hyperspectral Data  
+FUMI: sub-module containing repository to generate simulated hyperspectral data, This repository can be found here: https://github.com/TigerSense/FUMI  
Please see: https://git-scm.com/book/en/v2/Git-Tools-Submodules for cloning a repository with submodules
+MUUFLGulfport: sub-module containing repository for MUUFL Gulfport hyperspectral data, This repository can be found here: https://github.com/TigerSense/MUUFLGulfport  
Please see: https://git-scm.com/book/en/v2/Git-Tools-Submodules for cloning a repository with submodules  
Note: This repository contains several large files! Be sure you have space and want to clone before doing so.  
+LICENSE: License for this code  
+miTarget.m: Main MI-SMF and MI-ACE function and implementation  
+miTargetParameters.m:  Function to set miTarget parameters  
+README.md: This file  
+smf_det.m: SMF Target Detector Code


