Gradle Wire Plugin
==================

A Gradle plugin to automatically build protobuf classes using Square's Wire library.

This is a temporary repo.  It is a direct copy of a plugin implementation that will be merged into the official Wire repository "soon".  We'd like to use this "sooner", so here we are.

The purpose of hosting this here is to repackage the plugn and publish it as a snapshot to Sonatype, enabling easy use in our projects until this code gets an official release.

Again, there is no original code here - this is a repackaging of a pull request that has been pending for several months.

https://github.com/square/wire/pull/177

Usage
-----

In your app's `build.gradle` file:

```gradle
apply task 'com.bendb.wire'

buildScript {
  repositories {
    maven { url "https://oss.sonatype.org/content/repositories/snapshots/" }
  }

  dependencies {
    classpath "com.bendb.gradle:wire-gradle-plugin:1.6.1-SNAPSHOT"
  }
}

dependencies {
  compile 'com.squareup.wire:wire-runtime:1.6.1'
}
```

Place your protobuf definitions underneath `src/main/proto`.  On build, Wire will generate Java classes for your protos underneath `build/generated/proto`.

Credits
-------

All code here is written by Jeff Davidson (@jpd236 on GitHub), and is copyright 2014-2015 Square, made available under the Apache 2.0 license.
