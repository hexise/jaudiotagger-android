Jaudiotagger for Android
======================
This is Jaudiotagger library for Android. Jaudiotagger is an Audio Tagging library.

This is a pure java library, you can compile the source to JAR file by yourself.

The compiled JAR library works on Android platform, has been tested on API level 14 and above.

<h2>Source</h2>

The source code is based on Jaudiotagger library version 2.2.3.

Only few changes were made to fit for Android platform. The changes will be listed below.

For more information about Jaudiotagger, please refer to this link: http://www.jthink.net/jaudiotagger/

<h2>Changes comparing to official library</h2>

- org.jaudiotagger.tag.TagOptionSingleton:

   setAndroid() and isAndroid() methods are deleted, this library works and only works on Android.
   
- Image handling related classes have been removed. You can use your own image handling logic based on Android API.

   Removed classes: 
   
   - org.jaudiotagger.tag.images.ImageHandler;
   - org.jaudiotagger.tag.images.StandardImageHandler;
   - org.jaudiotagger.tag.images.AndroidImageHandler;
   - org.jaudiotagger.tag.images.ImageHandlingFactory;
   - org.jaudiotagger.tag.images.Images;

- Artwork related classes have been modified.

   Removed classes:
   
   - org.jaudiotagger.tag.images.StandardArtwork;
   
   Modifed classes:
   
   - org.jaudiotagger.tag.images.ArtworkFactory: now only support AndroidArtwork.
   
- org.jaudiotagger.utils.tree.DefaultTreeModel:

   Importing from java.awt.* and reference to java.beans.XMLEncoder are removed.
   
- org.jaudiotagger.tag.datatype:

   In method readByteArray(), only android related logic are kept.
   
- org.jaudiotagger.tag.asf.AbstractAsfTagImageField:

   Method getImage() has been removed since it depends on javax.imageio.ImageIO.
   
- org.jaudiotagger.audio.mp3.MP3File:

   Reference to sun.nio.ch.DirectBuffer has been fixed.
   
   Fix FileChannel.map() error related to [Android bug 53637](https://code.google.com/p/android/issues/detail?id=53637), returned java.nio.MappedByteBufferAdapter does not work well on Android IceCreamSandwich and JellyBean. Use ByteBuffer.allocate() instead.
   
- org.jaudiotagger.logging.LogFormatter:

   This class is removed since it is unnecessary for Android platform.

- org.jaudiotagger.tag.reference.GenreTypes

   Support genres 148–191 which were added in Winamp 5.6.
   
<h2>License</h2>

This library is licensed under LGPL([Lesser General Public License](http://www.gnu.org/copyleft/lesser.html)), same license as Jaudiotagger official library.
