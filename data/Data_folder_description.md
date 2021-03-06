## This folder contains:
#### `OmX.XXXXX_AsX.XXXXX_mvaX.XXXXX_mvb..._hX.XXXXX_OdeX.XXXXX_Peaks_KN_s2.00_z1.00_ng40.00_b050.npy`
- 101 files where: 
    - OmX.XXXXX_AsX.XXXXX_mvaX.XXXXX_mvb..._hX.XXXXX_OdeX.XXXXX is the cosmological model
    - Peaks: refers to the statistics used, i.e. peak counts of lensing convergence maps
    - KN: 'Kappa Noisy', with LSST-like noise
        - s2.00: 'smoothing = 2 '
        - z1.00: 'redshift = 1'
        - ng40.00: 'galaxy number density = 40/arcmin^(-2)'
        - b050: '#bins = 50'
    - each file has dimension (10001 , Nbins), where the first 2 rows are the bins centers (1 row = Kappa bins centers, 2 row= S/N bins centers) and the others are the values of the peak counts for the 9999 realisations of the convergence maps for each cosmology. (i.e. 101 cosmological models, each one with 9999 different realisations)

#### `Peaks_KN_s2.00_z1.00_ng40.00_b050.npy`
- peaks value for the fiducial massless model used to compute the covariance matrix. 
- this file has dimension (10001 , Nbins), where the first 2 rows are the bins centers (1 row = Kappa bins centers, 2 row= S/N bin centers) and the others are the values of the peak counts for the 9999 realisations of the fiducial massless model Om0.29997_As2.10000_mva0.00000_mvb0.00000_mvc0.00000_h0.70000_Ode0.69995_Peaks_KN_s2.00_z1.00_ng40.00_b050


#### `MassiveNuS_params.txt`
- file that associates the file_names OmX.XXXXX_AsX.XXXXX_mvaX.XXXXX_mvb..._hX.XXXXX_OdeX.XXXXX to the parameters values
- this file has dimension (101 , 5) where 101 is the number of cosmologies and the columns are respectevely (file_names , M_nu , Omega_m , A_s , sigma_8)


#### `data_scaled_100subsample.npy` 
- file of peaks values scaled for LSST sky coverage of shape (101,100,50) where:
    - LSST scaling: (12.25/20000) 
    - 101 is the number of cosmological models
    - 100 is the number of the subsample of realisations for each model
    - 50 is the number of bins

#### `data_scaled_100subsample_means.npy`
- means of `data_scaled_100.npy` over the 100 realisations, shape: (101,50) 
- N.B: the label '100subsample' is used to remark the fact that these means are taken over just a subsample (100 real.) of the 9999 full set of realisations available for each cosmology.

#### `params.npy` 
- numpy file that contains the cosmological parameter with dimension (101,3) where: 101 is the number of cosmologies, the columns are respectively the params (M_nu , Omega_m , A_s)


#### `covariance.npy`
- numpy file containing the covariance of the peaks values from `Peaks_KN_s2.00_z1.00_ng40.00_b050.npy`, shape: (Nbins,Nbins)

#### `theta.cloud.npy`, `peaks.cloud.npy`, `score.cloud.npy` 
- numpy files that contain the parameters, peak counts, and scores for the cloud setup. 
- these files are not included in the github repo due to their size but you can download them at https://www.dropbox.com/s/p7h8v7sf6tac60c/cloud.zip?dl=0

#### `theta.skewers.npy`, `peaks.skewers.npy`, `score.skewers.npy` 
- numpy files that contain the parameters, peak counts, and scores for the skewers setup.
- these files are not included in the github repo due to their size but you can download them at https://www.dropbox.com/s/yii8ysqsq0ydmhd/skewers.zip?dl=0

 



__N.B: For the scaled data with the full set of realisations see the link in the README__
