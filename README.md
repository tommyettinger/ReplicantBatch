# ReplicantBatch
You see libGDX 1.13.0 flipped over on its back. It can't right itself...

# Flip it over!
You can't do that.

# Well, why not?
GWT's SpriteBatch is, like, totes broken.

# Eh?
Totes McGoats. On a boat.

# Well we can replace it, can't we?
What, you mean, like a cybernetic replica of a human?

# No, GWT super-sourcing.
Ah, replacing specific classes with improved versions.

# Yeah, I mean, what else are we going to do?
Use libGDX 1.12.1? Like some kind of farm animal?

# I'm a human being. Let's do this.

This depends on libGDX 1.13.0 . This should be available by at least JitPack.
Because this is for GWT, you will need a `:sources` dependency, but that is
all you need! You don't need to add anything to core.

If using JitPack, you may want a more recent commit hash,
typically the most-recent non-SNAPSHOT version
[on JitPack.io](https://jitpack.io/#tommyettinger/ReplicantBatch).

```groovy
// this doesn't need a dependency in the core module.
// In the html module:
implementation 'com.github.tommyettinger:replicantbatch:0.0.1:sources'
```

You may also need to change any dependency on a third-party 1.12.1 backend for GWT to
the official 1.13.0 backend:

```groovy
//// Remove or comment out these lines, if you have them:
//  implementation "com.github.tommyettinger:gdx-backend-gwt:1.1210.1"
//  implementation "com.github.tommyettinger:gdx-backend-gwt:1.1210.1:sources"
//// Change the above to this:
  implementation "com.badlogicgames.gdx:gdx-backend-gwt:1.13.0"
  implementation "com.badlogicgames.gdx:gdx-backend-gwt:1.13.0:sources"
//// If you already depend on the above official backend, version 1.13.0 ,
//// then you don't need to change anything.
```

You will also need this GWT inherits line in your `GdxDefinition.gwt.xml` file:

```xml
<inherits name="com.github.tommyettinger.replicant" />
```

The order this is placed might matter, since this replaces libGDX sources. You should
add the above `inherits` line below any `inherits` line for libGDX.

If this doesn't make sense to you, you probably don't need this library!
Just use libGDX 1.12.1 instead! Or whatever version comes after 1.13.0 .

# Credits

All the work here was by Tomski, in [this pull request](https://github.com/libgdx/libgdx/pull/7486)!

# License

[Apache License 2.0](LICENSE), the same as libGDX.
