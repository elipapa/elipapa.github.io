---
layout: post
title: Installing Torch on a macbook
---
[Torch](http://torch.ch) is the latest linear algebra environment that has got everybody excited. Its syntax is as expressive as matlab/octave but it has a faster backend (Lua/C) and, apparently, is well suited to working with neural network. Some of the big deep learning labs (Facebook in NYC, Google Deepmind) have embraced it for fast prototyping of their latest deep learning ML algorithms. 
Here is what I did to install the environment on my macbook. 


The setup is actually quite simple. Just use [torch's ezinstall](https://github.com/torch/ezinstall)

To start:

	luajit -ltorch
	# or, using the improved LuaJIT interpreter:
	th -lparallel -loptim -lpl -limage


All good so far. Not to worry though: there is always a hiccup. 
In this case it is the parallel package. To install it you need to force homebrew to use an old version of zeromq (namely 2.2.0)

    brew install homebrew/versions/zeromq22
    brew unlink zeromq
    brew link zeromq22 --force

Now the parallel package installation finally works smoothly:

    luarocks install parallel

Return to the normal state:
    
    brew unlink zeromq22
    brew link zeromq

Finally to install iTorch, run

	luarocks install lzmq
	luarocks install uuid
	luarocks install lbase64
	luarocks install itorch

