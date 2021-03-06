Installation on Windows
-----------------------

.. contents::
   :local:
   :depth: 1


Prerequisites
^^^^^^^^^^^^^

We tested on Windows8.1 64bit and Windows10 64bit.

The following software are required for installation:

* Required software.

  * Python 2.7: PIP
  * Microsoft Visual C++ 2015 Redistributable

* Recommended.

  * CUDA Toolkit 8.0 / cuDNN 6.0 (for NVIDIA GPU users)


Setup environment
^^^^^^^^^^^^^^^^^

Python2.7
"""""""""

In this instruction, we use `miniconda <https://conda.io/miniconda.html>`_.

Get and install the windows binary from `here <https://repo.continuum.io/miniconda/Miniconda2-latest-Windows-x86_64.exe>`_


And then install required packages from command prompt.

.. code-block:: doscon

    > conda install scipy scikit-image ipython


If your network is using proxy and setup fails, configure proxy server with environment variable and try install again.

.. code-block:: doscon

    > SET HTTP_PROXY=http://(enter the address of the http proxy server here)
    > SET HTTPS_PROXY=https://(enter the address of the https proxy server here)


Microsoft Visual C++ 2015 Redistributable
"""""""""""""""""""""""""""""""""""""""""

Get and install from `here <https://www.microsoft.com/en-us/download/details.aspx?id=52685>`_


CUDA Toolkit 8.0 / cuDNN 6.0
""""""""""""""""""""""""""""

If you are using a NVIDIA GPU, execution speed will be drastically improved by installing the following software.

`CUDA Toolkit <https://developer.nvidia.com/cuda-downloads>`_

`cuDNN <https://developer.nvidia.com/cudnn>`_

To install cuDNN, copy bin, include and lib to C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v8.0


Install
^^^^^^^

Install CPU package.

.. code-block:: doscon

    > pip install nnabla


If you are using a NVIDIA GPU, you can also install the CUDA/cuDNN package.

.. code-block:: doscon

    > pip install nnabla_ext_cuda


Check for running.

.. code-block:: doscon

    > ipython
    
    In [1]: import nnabla
    2017-06-06 21:36:07,101 [nnabla][Level 99]: Initializing CPU extension...
    
    In [2]: exit
    
    >


Check for running (CUDA/cuDNN).

.. code-block:: doscon

    > ipython
    
    In [1]: import nnabla_ext.cuda.cudnn
    2017-06-16 18:42:18,881 [nnabla][Level 99]: Initializing CPU extension...
    2017-06-16 18:42:19,923 [nnabla][Level 99]: Initializing CUDA extension...
    2017-06-16 18:42:20,243 [nnabla][Level 99]: Initializing cuDNN extension...
    
    In [2]: exit
    
    >


Run an Example
^^^^^^^^^^^^^^

Download NNabla repository from `here <https://github.com/sony/nnabla/archive/master.zip>`_, unzip it and move to example directory.

.. code-block:: doscon

    > cd nnabla\examples\vision\mnist


Run MNIST classification

.. code-block:: doscon

    nnabla\examples\vision\mnist > python classification.py


Run MNIST classification with CUDA/cuDNN

.. code-block:: doscon

    nnabla\examples\vision\mnist > python classification.py -c cuda.cudnn


FAQ
^^^

Q. Scikit-image installation takes a long time.
"""""""""""""""""""""""""""""""""""""""""""""""

Depending on the environment, it will take a long time.  Please wait.

Q. Failed to install Scipy during installation.
"""""""""""""""""""""""""""""""""""""""""""""""

Please install scipy using "conda install" before "pip install nnabla".

