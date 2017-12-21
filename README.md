## Using CWRUCoin

### Download or Build Executables
To use CWRUCoin, you need to either download prebuilt executables for your platform, or build them from here. Instructions for building from source can be found below or on Google, and there's a bounty on creating full-fledged Build Guides for most platforms - if that happens, the guides will be linked here.

If you download the executables, extract the files to wherever your heart desires on your number machine.

###Starting Daemon
In order to communicate with all the rest of the CWRUCoin nodes, you need to start up the Daemon process named cwrucoind in raw builds. You'll see a terminal open up and begin to sync data with the peer nodes. On Windows, there's also a premade shortcut outside the reference folder named "Daemon" - click that. LEAVE THE DAEMON RUNNING while you are working with CWRUCoins in any way.

If you can't connect to the blockchain peers, check your firewall. Open up TCP ports "10900 Euclid Avenue" and "11340 students at CWRU" so you can communicate with the nodes and wallet services. </p>

###Starting Wallet 
To save, send, or recieve CWRUCoins, you need a wallet. Open up simplewalletd (or click the wallet shortcut). You'll see another terminal open up asking you to open or generate a wallet. If you don't have a wallet, generate a new one. Remember to write down the name and password you choose. IF you lose those, you're pretty much screwed. If you have a wallet already, open it up.</p>

Once you have a wallet open, you're free to do anything you want. Type "help" to see all the stuff you can do.

###Mining CWRUCoin
You can start mining from either the Daemon or Wallet terminal using the start_mining command. In the daemon you  must specify a wallet address, and you can set the number of threads to mine with using [number_of_threads]. In the wallet, you can only add the [number_of_threads], as the wallet will use your currently loaded wallet address automatically.


## Building CWRUCoin

### On *nix

Dependencies: GCC 4.7.3 or later, CMake 2.8.6 or later, and Boost 1.55. Grab them from apt-get. 

To build, cd to the GitHub project directory, and run `make`. The resulting executables can be found in `build/release/src`.

**Advanced options:**
* Parallel build: run `make -j<number of threads>` instead of `make`.
* Debug build: run `make build-debug`.
* Test suite: run `make test-release` to run tests in addition to building. Running `make test-debug` will do the same to the debug version.
* Building with Clang: it may be possible to use Clang instead of GCC, but this may not work everywhere. To build, run `export CC=clang CXX=clang++` before running `make`.

### On Windows
Dependencies: MSVC 2013 or later, CMake 2.8.6 or later, and Boost 1.55. You may download them from:

* http://www.microsoft.com/
* http://www.cmake.org/
* http://www.boost.org/

To build, change to a directory where this file is located, and run these commands: 
```
mkdir build
cd build
cmake -G "Visual Studio 12 Win64" ..
```

Then, open the resulting Visual Studio Project file, select your target platform, and click Build. The resulting .exes can be found in `build/release/src`.
Good luck!