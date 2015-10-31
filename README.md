### Carthage git submodule POC

This repo uses two repo's from Github:

 * [Mast](https://github.com/Mast-Swift/Mast) 
 * [Mast-HBar](https://github.com/Mast-Swift/Mast-HBar.git) 

to see whether Carthage will recursively download Git submodules within those repo's.

This repo is related to [Carthage-847](https://github.com/Carthage/Carthage/issues/847) in that I was curious whether I'd see the same problem or not.

To reproduce:

```
git clone https://github.com/lottadot/carthagesubmodulepoc.git
cd carthagesubmodulepoc
carthage bootstrap --verbose
```

And see the following:

```
$ carthage bootstrap -verbose
*** No Cartfile.resolved found, updating dependencies
*** Fetching Mast-HBar
*** Fetching Mast
*** Fetching taylor
*** Fetching SwiftSockets
*** Fetching CocoaAsyncSocket
*** Checking out taylor at "0.3.0"
*** Checking out CocoaAsyncSocket at "6e018ddf7c456106f898efae66ea5e5c94737a96"
*** Checking out Mast-HBar at "e1bb2ae2dce1829e30cf7ca5084c3531ab0874c1"
*** Checking out Mast at "4952c86ee819fc8775b34a5b8655cd7ec53a00ce"
*** Checking out SwiftSockets at "fbcce96a193d8ef657fbad435c0e92c44a5a14a4"
Parse error: expected submodule commit SHA in ls-tree output: 
$ carthage version
0.9.4
```
