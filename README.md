# jEmojiTable

jEmojiTable is a simple JTable (grid) that lets a user pick an emoji. You can load the built-in font "OpenMoji" 
if you don't have a font that can render emojis. Using jEmojiTable is straightforward:

1. Typically, embed the table in a JScrollPane
2. Specify the number of columns wide
3. Specify the font (optionally load and specify the OpenMoji font if needed)
4. Optionally prune out emojis that don't render well with the OpenMoji font
5. Optionally specify a listener that receives a callback when the user double-clicks an emoji

```
EmojiTable table = new EmojiTable(8, new Font("OpenMoji", Font.PLAIN, 34), true);  //8 columns wide, OpenEmoji, prune un-renderable emojis
table.setRowHeight(42);
table.setDoubleClickListener(this);
        
scrollPane.add(table);  //scroll pane is a JScrollPane added to a JPanel somewhere
scrollPane.setViewportView(table);
```

An example in the Test Packages provides a simple demo using the OpenMoji font.

## Emoji Object

The Emoji class provided by [emoji-java library](https://github.com/vdurmont/emoji-java) holds the representation of the emojis in the table
and is returned to the listener. A description and unicode String of the emoji can be obtained from this class.

## Fonts

Most fonts won't render emojis properly so you'll need to specify a font that will. A good font to use is included, simply call
this function before setting up your table:

	OpenMojiFont.load();
	
Set your table row height appropriately based on the font size you use (see example).

Note: there is no support for color emojis. Java renders only vector fonts.


## Example

The EmojiTableExample class provides a simple example of the table in a JFrame with a listener.

![Demo Screenshot](https://github.com/kkieffer/jEmojiTable/blob/master/demo.jpg "Demo Screenshot")


## Getting Started

* Build and Run using Maven:  "mvn package"
* Navigate to the "target" directory
* Run: java -cp classes:test-classes com.kevinnovate.jemojitable.EmojiTableExample

## Third Party Resources

* The [emoji-java library](https://github.com/vdurmont/emoji-java) is a dependency included in the pom file
* The [openmoji font](https://openmoji.org) is included in the package (Creative Commons License)

## License

This project is licensed under the MIT License - see the LICENSE file for details. All third party libraries and source code retain their Copyright and license
as specified in their license or source comments (see links above).







