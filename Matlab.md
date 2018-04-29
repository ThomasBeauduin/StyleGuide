Matlab Style Guide
==================

## Naming conventions

### Variables
- Write variable names in mixed case starting with lower case (matlab interpretates underscores as subscript in legend, .., hence, avoid it for variables).  
e.g. linearity, credibleThreat, qualityOfLife
- Use the prefix n for variables representing the number of objects.  
e.g. nFiles, nSegments, nColumns, mRows (yes m)
- avoid plurals in naming arrays or multiple data.   
e.g. point -> pointArray, PointList
- Prefix iterator variable names with i, j, k etc.  
e.g. iPoints, iFiles, iSegments

### Constants
- no real constants in matlab, hence, same conventions as variables.
- if indispensable make them uppercase using underscore to separate words.  
e.g. MAX_ITERATIONS, COLOR_RED
- Constants can be prefixed by a common type name.  
e.g. COLOR_RED, COLOR_GREEN, COLOR_BLUE

### Structures
- Structure names should begin with a capital letter  
e.g. Segment.length, Acme.sourceName
- field names should follow variables conventions.
- Array of cells are a Neanderthal approach to structuring data, hence, seperate it from structures by writing it in full upper-case. 

### Functions
- Write names of functions in lower case (like matlab).  
e.g. linspace, meshgrid, ..
- In specially long/akward cases use mixed cases  
e.g. predictSeaLevel, publishHelpPages
- Name functions that have a single output based on the output.  
e.g. mean, standardError
- Functions with no output or which only return a handle should be named after what they do.  
e.g. plot, transform, ..
- using the prefix init where an object or a variable is established.  
e.g. initProblemState, initOptiProblem
- Use the prefix is for Boolean functions.  
e.g. isOverPriced, isComplete, ..

## Layout
- Short single statement if, for or while statements can be written on one line.
- Write one executable statement per line of code (can speed execution).
- Use structures for function arguments.
- Organize m-files that have some generality in toolboxes.
- Write a test script for every function.
- 

## Documentation

> example
``` matlab
function [Gmm, P] = cvGmmTrain(X, K, maxIter, verbose)
% cvGmmTrain - Train Gaussian Mixture Models (GMM)
%
% Synopsis
%   [Gmm, [P]] = cvGmmTrain(X, K, [maxIter], [verbose])
%
% Description
%   cvGmmTrain trains Gaussian Mixture Models (GMM) using the Expectation
%   Maximization (EM) algorithm. 
%
% Inputs ([]s are optional)
%   (matrix) X        D x N matrix representing feature vectors by 
%                     columns where D is the number of dimensions and N
%                     is the number of vectors. 
%   (scalar) K        The number of mixtures (clusters). 
%   (scalar) [maxIter = 10] 
%                     The maximum number of iterations of EM algorithm.
%   (bool)   [verbose = 0]
%                     Show progress or not. 
%
% Outputs ([]s are optional)
%   (struct) Gmm      The Gaussian Mixture Model (GMM)
%   - (cell)   Mu     K cell arrays where each cell contains a D x 1 
%                     vector representing a mean vector in the mixture. 
%   - (cell)   Sigma  K cell arrays where each cell contains a D x D
%                     matrix representiang a covariance matrix in the
%                     mixture. 
%   (vector) [P]      K x 1 vector representing the estimated prior 
%                     probabilities for mixtures. 
%
% Examples
%   X = [1 0 -1
%         1 0 -1];
%   Gmm = cvGmmTrain(X, 3);
%
% See also
%   cvGaussPdf
%
% Requirements
%   kmeans (Statistics Toolbox)

% References
%   [1] Xuedong Huang, et al. "Spoken Language Processing, "
%   Prentice Hall PTR, 2001. 
%
% Authors
%   Naotoshi Seo <sonots(at)sonots.com>
%
% License
%   The program is free for non-commercial academic use. Please 
%   contact the authors if you are interested in using the software
%   for commercial purposes. The software must not modified or
%   re-distributed without prior permission of the authors.
%
% Changes
%   04/01/2006  First Edition
```






