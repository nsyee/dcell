![DCell](https://github.com/celluloid/dcell/raw/master/logo.png)
=====
[![Build Status](http://travis-ci.org/celluloid/dcell.png)](http://travis-ci.org/celluloid/dcell)
[![Dependency Status](https://gemnasium.com/celluloid/dcell.png)](https://gemnasium.com/celluloid/dcell)

> "�I�u�W�F�N�g�̓l�b�g���[�N����đ��̒[����ɑ��݂���I�u�W�F�N�g�ɑ΂��ē��ߓI�Ƀ��b�Z�[�W�𑗂邱�Ƃ��ł��܂��B�l�b�g���[�N�ɂ܂��ʓ|�Ȃ��Ƃ��C�ɂ�����K�v�͖������A�I�u�W�F�N�g��T�����ƂɐS�z���邱�Ƃ��Ȃ����A�����C�ɂ���K�v�͖����ł��B����͂܂��ɂ����ׂ�̃I�u�W�F�N�g�Ƀ��b�Z�[�W�𑗂�悤�Ȃ��ƂȂ̂ł��B"

> "Objects can message objects transparently that live on other machines
> over the network, and you don't have to worry about the networking gunk,
> and you don't have to worry about finding them, and you don't have to
> worry about anything. It's just as if you messaged an object that's
> right next door."
> _--Steve Jobs describing the NeXT Portable Distributed Object system_

DCell��Ruby�ŕ��U�A�v���P�[�V�������\�z����Ȍ��ŊȒP�ȕ��@�ł��B�����炩DRb�Ǝ��Ă��܂����ADCell��Ruby�I�u�W�F�N�g���l�b�g���[�N�T�[�r�X�̂悤�ɊȒP�ɐG�ꂳ���Ă���܂����A���̂ǂ�Ruby�I�u�W�F�N�g�Ƃ����l�ɁA�������ꂽ�I�u�W�F�N�g���Ăяo���܂��B
�������Ȃ���ADRb�Ƃ͈قȂ�A�V�X�e����̂��ׂẴI�u�W�F�N�g�͕��s�ł��B��߂�ꂽ�m�[�h�ɑ΂��ĉp���̂���T�[�r�X�𐶐�/�o�^���邱�Ƃ��ł��܂����A�����ւ̃n���h�����l�����A���̃I�u�W�F�N�g�Ɠ��l�ɂ��������l�b�g���[�N���̃n���h�����������Ƃ��ł��܂��B


DCell is a simple and easy way to build distributed applications in Ruby.
Somewhat similar to DRb, DCell lets you easily expose Ruby objects as network
services, and call them remotely just like you would any other Ruby object.
However, unlike DRb all objects in the system are concurrent. You can create
and register several available services on a given node, obtain handles to
them, and easily pass these handles around the network just like any other
objects.

DCell��[Celluloid][celluloid]�̕��U�^�̊g���ł���AErlang�ɑ������������ƂƂ���Ruby�ɕ��s�I�u�W�F�N�g��񋟂��܂��B����́A�I�u�W�F�N�g�Q���Ǘ����ăI�u�W�F�N�g���N���b�V�������ۂ͍ċN���������葼�̃I�u�W�F�N�g�ƌ��т�����N���b�V�������ꍇ�ɃC�x���g�ʒm����M����悤�ȋ@�\�ł��B�����̓����̂������ŁA�拭�őϏ�Q���̂��镪�U�V�X�e�������ȒP�ɍ\�z���邱�Ƃ��ł��܂��B

DCell is a distributed extension to [Celluloid][celluloid], which provides
concurrent objects for Ruby with many of the features of Erlang, such as the
ability to supervise objects and restart them when they crash, and also link to
other objects and receive event notifications of when they crash. This makes
it easier to build robust, fault-tolerant distributed systems.

DCell�̓��b�Z�[�W���O�v���g�R����[0MQ][zeromq]���g�p���Ă��܂��B0MQ�̓m�[�h�Ԃ̔񓯊��ʐM�ɑ΂��Ċ拭�őϏ�Q��������u���[�J�[�̗v��Ȃ��g�����X�|�[�g��񋟂��܂��BDCell��[Celluloid::ZMQ][celluloid-zmq]���C�u�����̏�ɍ\�z����Ă���A[ffi-rzmq][ffi-rzmq]���C�u�������ݍ���"Celluloid"�w���̃��b�p�[��񋟂��܂��B

DCell uses the [0MQ][zeromq] messaging protocol which provides a robust,
fault-tolerant brokerless transport for asynchronous messages sent between
nodes. DCell is built on top of the [Celluloid::ZMQ][celluloid-zmq] library,
which provides a Celluloid-oriented wrapper around the underlying
[ffi-rzmq][ffi-rzmq] library.

[Please see the DCell Wiki](https://github.com/celluloid/dcell/wiki)
for more detailed documentation and usage notes.

Like DCell? [Join the Celluloid Google Group][googlegroup]

[celluloid]: http://celluloid.io/
[zeromq]: http://www.zeromq.org/
[celluloid-zmq]: https://github.com/celluloid/celluloid-zmq
[ffi-rzmq]: https://github.com/chuckremes/ffi-rzmq
[googlegroup]: http://groups.google.com/group/celluloid-ruby

### Is it any good?

[Yes.](http://news.ycombinator.com/item?id=3067434)

### Is It "Production Ready™"?

Not entirely, but eager early adopters are welcome!

Supported Platforms
-------------------

DCell works on Ruby 1.9.3, JRuby 1.6, and Rubinius 2.0.

DCell requires Ruby 1.9 mode on all interpreters. This works out of the
box on MRI/YARV, and requires the following flags elsewhere:

* JRuby: --1.9 command line option, or JRUBY_OPTS=--1.9 environment variable
* rbx: -X19 command line option

Contributing to DCell
-------------------------

* Fork this repository on github
* Make your changes and send me a pull request
* If I like them I'll merge them
* If I've accepted a patch, feel free to ask for commit access

Copyright
---------

Copyright (c) 2012 Tony Arcieri. Distributed under the MIT License.
See LICENSE.txt for further details.
