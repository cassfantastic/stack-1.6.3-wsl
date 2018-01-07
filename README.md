# stack-1.6.3-wsl
Binary of stack 1.6.3 compiled using (GHC 8.0.2 compiled with --disable-large-address-space)

Stack hangs for about 6 seconds on every run (including stack --version) when using the official distribution on WSL, due to some syscall stuff I don't entirely understand - GHC8 requests 1TB of ram as virtual memory, I think, and while Linux and Windows handle this fine individually, the translation between Linux calls and Windows calls in the Windows Subsystem for Linux botches something and takes about six seconds on every run of stack, and GHC compiled without the --disable-large-address-space flag takes approximately 10x longer to compile anything. The newest fast-ring beta version of Windows 10 (v17069) is supposed to fix this, but I haven't tried it yet. 

The WSL-friendly GHC can be obtained [here](https://github.com/sgraf812/ghc-dlas). I'm hoping to compile GHC 8.2.2 for linux the same way.
