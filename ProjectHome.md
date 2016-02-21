The thirft-gwt project provides a [GWT](http://code.google.com/webtoolkit/) library and a [Thrift](http://thrift.apache.org/) compiler patch to allow GWT applications to interoperate with Thrift.

## Download thrift-gwt ##

You can find the latest patched Thrift compiler and GWT library at:

  * [Thrift 0.7.0 compiler patched with GWT generator](http://code.google.com/p/thrift-gwt/downloads/detail?name=thrift-gwt-0.7.0-rev2.exe)
  * [Thrift library for GWT](http://code.google.com/p/thrift-gwt/downloads/detail?name=libthrift-gwt-rev2.jar)

The latest release is **rev2** (still very early work...), released November 2, 2011.

## Start using thrift-gwt ##

  1. Generate Thrift classes using the compiler: `thrift.exe -gen gwt MyDefinitionFile.thrift`
  1. Import the Thrift module in your GWT module: `<inherits name="org.apache.thrift.Thrift"/>`

That's it, you're done!

You can have a look at the [Tutorial GWT project](http://code.google.com/p/thrift-gwt/source/browse/#svn%2Ftrunk%2Ftutorial%2Fgwt) to see thrift-gwt in action:
  * [Using the Thrift client](http://code.google.com/p/thrift-gwt/source/browse/trunk/tutorial/gwt/src/tutorial/client/Tutorial.java)
  * [Exposing a Thrift service as a Servlet](http://code.google.com/p/thrift-gwt/source/browse/trunk/tutorial/gwt/src/tutorial/server/CalculatorServlet.java)

## Useful information ##
  * The library is known to work with **GWT 2.4**. It may or may not work with older versions of GWT.
  * On the client side, you way want to use **TNativeJSONProtocol** instead of **TJSONProtocol**. It uses eval() to speed up deserialization, and is much faster.

This projects mainly aims at providing a Thrift client for GWT. However, the GWT generator still creates service **Processor** interfaces and the **TServlet** class is still included in the library. This allows for a simple solution to the basic GWT Client / Java Server use case.

## Limitations ##
  * **JSONProtocol** is the only supported protocol.
  * No support for **binary** type.







