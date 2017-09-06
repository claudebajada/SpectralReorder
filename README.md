Function that spectrally reorders a similarity matrix and outputs the
spectrum of eigenvalues and eigenvectors

Function supplemental to the text of: "The Spectral Transformation in
Neuroimaging: A review and MATLAB tool" Bajada et al (in prep)

Matlab implementation partially based on an algorithm published in supplemetary text of:
Johansen-Berg et al. (2004) PNAS 10.1073/pnas.0403743101.
For in depth mathematical background, see:
Barnard, S.T., Pothen, A., & Simon, H.D. (1995) Numer. Linear Algebra Appl. 2,317-334
For a tutorial on the different approaches please see:
von Luxburg, U. (2007) Statistics and Computing 17 (4), 2007

Here we implement 4 different methods:
method = 'geig' Based on the generalised spectral decomposition of the
un-normalised Laplacian (default approach)
method = 'sym' Based on the spectral decomposition of the normalised
symmetric Laplacian - results should match geig
method = 'rw' Based on the spectral decomposition of the normalised
non-symmetric (random-walk) Laplacian
method = 'unnorm' Based on the spectral decomposition of the
un-normalised Laplacian


Function takes the form:
[sortedB, p, v2, v3D, sortedEigenValues , sortedEigenVectors] = spectral_reorder(B,method);

B = similarity matrix (accepts values between -1 and 1)
sortedB = spectrally reordered matrix
p = the reordering vector that allows you to reorder your subjects in the
same way as your matrix (sortedB)
v2 = Fiedler vector (eigen vector corresponding to the second smallest
eigenvalue)
v3D = First 3 smaller eigenvectors (the first one is the Fiedler vector)
sortedEigenValues = the complete set of sorted eigenvalues
sortedEigenVectors = the complete set of sorted eigenvectors
 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
 
 
If you only assign one output
(i.e. of the form sortedB = extract_spectral_reorder(B), only the spectrally reordered matrix
- not the reordering vector or the other outputs - will be produced)
 
Created by:
Claude J. Bajada - University of Manchester
Nelson Trujillo-Barreto - University of Manchester

Edited by:
Owen Falzon - University of Malta
 
Neuroscience and Aphasia Research Unit (NARU)
University of Manchester
 2014