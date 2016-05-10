# ||  Ritzcoin  ||
Ritzcoin the new cryptocurrency

## What is Ritzcoin?
Ritzcoin is a cryptocurrency like Bitcoin. Taking development cues from Bitcoin and Litecoin, Ritzcoin currently employs a simplified variant of scrypt.

http://ritzcoin.com/

## License 
Ritzcoin is released under the terms of the MIT license. See [COPYING](COPYING)
for more information or see http://opensource.org/licenses/MIT.

## Development and contributions
Development is ongoing, and the development team, as well as other volunteers, can freely work in their own trees and submit pull requests when features or bug fixes are ready.

## Frequently Asked Questions

### How much Ritzcoin can exist? 
Early 2025 (approximately ten years after release) there will be approximately 150,000,000 coins.
Each subsequent block will grant 70 coins to encourage miners to continue to secure the network and make up for lost wallets on hard drives/phones/lost encryption passwords/etc.

### How to get Ritzcoin?
Ritzcoin uses a simplified variant of the scrypt key derivation function as its proof of work with a target time of one minute per block and difficulty readjustment after every block. The block rewards are fixed and halve every 1,000,000 blocks. Starting with the 142,858th block, a permanent reward of 70 Dogecoin per block will be paid. 

Originally, a different payout scheme was envisioned with block rewards being determined by taking the maximum reward as per the block schedule and applying the result of a Mersenne Twister pseudo-random number generator to arrive at a number between 0 and the maximum reward. This was changed, starting with block 145,000, to prevent large pools from gaming the system and mining only high reward blocks. At the same time, the difficulty retargeting was also changed from four hours to once per block (every minute), implementing an algorithm to lessen the impact of sudden increases and decreases of network hashing rate.

###Development tips and tricks
---------------------------

**compiling for debugging**

Run configure with the --enable-debug option, then make. Or run configure with
CXXFLAGS="-g -ggdb -O0" or whatever debug flags you need.

**debug.log**

If the code is behaving strangely, take a look in the debug.log file in the data directory;
error and debugging messages are written there.

The -debug=... command-line option controls debugging; running with just -debug will turn
on all categories (and give you a very large debug.log file).

The Qt code routes qDebug() output to debug.log under category "qt": run with -debug=qt
to see it.

**testnet and regtest modes**

Run with the -testnet option to run with "play dogecoins" on the test network, if you
are testing multi-machine code that needs to operate across the internet.

If you are testing something that can run on one machine, run with the -regtest option.
In regression test mode, blocks can be created on-demand; see qa/rpc-tests/ for tests
that run in -regtest mode.

**DEBUG_LOCKORDER**

Dogecoin Core is a multithreaded application, and deadlocks or other multithreading bugs
can be very difficult to track down. Compiling with -DDEBUG_LOCKORDER (configure
CXXFLAGS="-DDEBUG_LOCKORDER -g") inserts run-time checks to keep track of which locks
are held, and adds warnings to the debug.log file if inconsistencies are detected.
