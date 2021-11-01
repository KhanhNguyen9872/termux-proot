![Running a sandboxed Termux environment](https://raw.githubusercontent.com/Yonle/termux-proot/master/screenshot.png)

# termux-proot
A sandboxed, 2nd termux, isolated or jailed termux environment with proot

Test something out in sandboxed environment with 0% Afraid of getting bricked in your real termux. Human is curious, Ain't we?

## Setup & Installation
Before installing, We need these 3 packages to be installed in your Termux:
 * `curl` for fetching & downloading latest termux bootstrap.
 * `unzip` for unzipping Termux Bootstrap.
 * `proot` for start sandboxed environment.

These required packages will be installed if you don't have them.

And finally, set up sandboxed environment:

```sh
curl -sLO git.io/termux-proot.sh
chmod +x termux-proot.sh

# Will setup by itself & start sandboxed environment
./termux-proot.sh
```

## Uninstalling
Uninstalling termux-proot is literally, very easy. 

```sh
rm termux-proot.sh

# The command below can use for reinstalling.
proot -0 rm -rf $PREFIX/../../sandbox
```

## Environment Variables
termux-proot also has it's own environment variables and it's changeable. They are:

 * `TERMUX_SANDBOX_PATH` - Path to where Termux sandbox folder located. Default is `$PREFIX/../../sandbox`
 * `TERMUX_SANDBOX_APPPATH` - A variable that used to simulate Termux app path. Default is `/data/data/com.termux`
 * `TERMUX_SANDBOX_ENV` - A variable that used to reveal a environment variable to guest. Can used like `TERMUX_SANDBOX_ENV="FOO=BAR BAR=FOO" ./termux-proot.sh`
 * `TERMUX_SANDBOX_PROOT_OPTIONS` - A variable that used to add some proot arguments. Can used like `TERMUX_SANDBOX_PROOT_OPTIONS="-b /sdcard" ./termux-proot.sh`

## Community
- [Telegram group](https://t.me/yonlecoder)
