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
$ carthage bootstrap --verbose
*** Checking out Mast at "4952c86ee819fc8775b34a5b8655cd7ec53a00ce"
Parse error: expected submodule commit SHA in ls-tree output: 
```
