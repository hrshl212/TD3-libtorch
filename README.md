# TD3-Pytorch-C++-
TD3 algorithm using libtorch in simple environment

This is an implementation of the twin-delayed deep deterministic (TD3) policy gradient algorithm for the C++ API of Pytorch. It uses a simple TestEnvironment to test the algorithm. Below is a small visualization of the environment, the algorithm is tested in.

![This is an image](/img/epoch_4.gif)


Fig. 1: The agent in testing mode.

Build
You first need to install LibTorch. For a clean installation from Anaconda, checkout this short tutorial, or this tutorial, to only install the binaries.

Do

mkdir build
cd build
cmake -DCMAKE_PREFIX_PATH=/absolut/path/to/libtorch ..
make
Run
Run the executable with

cd build
./train_ppo
It should produce something like shown below.



Fig. 2: From left to right, the agent for successive epochs in training mode as it takes actions in the environment to reach the goal.

The algorithm can also be used in test mode, once trained. Therefore, run

cd build
./test_ppo
Visualization
The results are saved to data/data.csv and can be visualized by running python plot.py.
