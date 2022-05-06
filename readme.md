main.cpp consists of 

    void throwInvalidFileError(std::string fileName)
        throws file does not exist exception

    void help()
        outputs help on terminal
    [TERMINAL COMMAND:] ./yourcode.out help

    void processSound(const char *audioFile, const char* outputFile)
        It calls libaudioAPI
        and outputs top 3 possibilities of given audio input 


Matrix.hpp consists of
class Matrix

    int n => represents number of rows
    int m => represents number of columns
    vector<vector> mat => represents Matrix

    operator+ => adds other matrix to self and returns their sum
    operator- => subtracts other matrix from self and returns their difference
    operator* => multiplies other matrix with self and return their product
    operator+= => adds other matrix to self
    operator-= => subtracts other matrix from self
    operator*= => multiplies other matrix from self

    applyRelu => applies relu elementwise
    applyTanh => applies tanh elementwise

    applyMaxPool => creates a new matrix as a result of max pooling of a given stride on matrix
    applyAvgPool => creates a new matrix as a result of average pooling of a given stride on matrix

    productPthread => calls pthreadProduct with its respective argument
    pthreadProduct => 
    if threadDepth == 0:
        It only do normal matrix multiplication
    else:
        It breaks martices into 4 sub matrices and call itself recursively till threadDepth > 0. Finally it merges submatrices into one.

    istream &operator>> => Inputs matrix
    ostream &operator<< => Outputs matrix


Vector.hpp consists of
class Vector

    int n => represents number of elements in vector
    vector vec => represents vector

    applySoftMax => applies softMax function on elements of vector
    applySigmoid => applies sigmoid function on elements of vector


    istream &operator>> => Inputs vector
    ostream &operator<< => Outputs vector

MKL.hpp and OpenBlas.hpp both consists of

    addProduct function for Mat3 += Mat1 * Mat2 using cblas_degmm function.

How to install mkl library in linux (ubuntu):

    sudo apt-get update
    sudo apt-get install intel-mkl-full


How to install openblas library in linux (ubuntu):

    sudo apt-get update
    sudo apt-get install libopenblas-dev

To set path of shared library and run:

    export LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH
    make
    ./yourcode.out extractedAudioFile.txt outputFile.txt

Makefile:

    g++ -fopenmp main.cpp -lmkl_intel_lp64 -lmkl_core -lmkl_gnu_thread -lopenblas -lpthread -o yourcode.out