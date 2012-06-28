![DCell](https://github.com/celluloid/dcell/raw/master/logo.png)
=====
[![Build Status](http://travis-ci.org/celluloid/dcell.png)](http://travis-ci.org/celluloid/dcell)
[![Dependency Status](https://gemnasium.com/celluloid/dcell.png)](https://gemnasium.com/celluloid/dcell)

> "オブジェクトはネットワークを介して他の端末上に存在するオブジェクトに対して透過的にメッセージを送ることができます。ネットワークにまつわる面倒なことを気にかける必要は無いし、オブジェクトを探すことに心配することもないし、何も気にする必要は無いです。それはまさにすぐ隣りのオブジェクトにメッセージを送るようなことなのです。"

> "Objects can message objects transparently that live on other machines
> over the network, and you don't have to worry about the networking gunk,
> and you don't have to worry about finding them, and you don't have to
> worry about anything. It's just as if you messaged an object that's
> right next door."
> _--Steve Jobs describing the NeXT Portable Distributed Object system_

DCellはRubyで分散アプリケーションを構築する簡潔で簡単な方法です。いくらかDRbと似ていますが、DCellはRubyオブジェクトをネットワークサービスのように簡単に触れさせてくれますし、他のどのRubyオブジェクトとも同様に、遠く離れたオブジェクトを呼び出します。
しかしながら、DRbとは異なり、システム上のすべてのオブジェクトは並行です。定められたノードに対して可用性のあるサービスを生成/登録することができますし、それらへのハンドラを獲得し、他のオブジェクトと同様にそうしたネットワーク中のハンドルを扱うことができます。


DCell is a simple and easy way to build distributed applications in Ruby.
Somewhat similar to DRb, DCell lets you easily expose Ruby objects as network
services, and call them remotely just like you would any other Ruby object.
However, unlike DRb all objects in the system are concurrent. You can create
and register several available services on a given node, obtain handles to
them, and easily pass these handles around the network just like any other
objects.

DCellは[Celluloid][celluloid]の分散型の拡張であり、Erlangに多く備わる特徴とともにRubyに並行オブジェクトを提供します。それは、オブジェクト群を管理してオブジェクトがクラッシュした際は再起動させたり他のオブジェクトと結びつけたりクラッシュした場合にイベント通知を受信するような機能です。それらの特徴のおかげで、頑強で耐障害性のある分散システムをより簡単に構築することができます。

DCell is a distributed extension to [Celluloid][celluloid], which provides
concurrent objects for Ruby with many of the features of Erlang, such as the
ability to supervise objects and restart them when they crash, and also link to
other objects and receive event notifications of when they crash. This makes
it easier to build robust, fault-tolerant distributed systems.

DCellはメッセージングプロトコルに[0MQ][zeromq]を使用しています。0MQはノード間の非同期通信に対して頑強で耐障害性がありブローカーの要らないトランスポートを提供します。DCellは[Celluloid::ZMQ][celluloid-zmq]ライブラリの上に構築されており、[ffi-rzmq][ffi-rzmq]ライブラリを包み込んだ"Celluloid"指向のラッパーを提供します。

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

### Is It "Production Ready邃｢"?

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
