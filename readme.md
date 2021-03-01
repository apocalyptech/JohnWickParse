## ~~Fortnite~~ Borderlands 3 Asset Parser

This program is able to parse pak, uexp and uasset files, and offers way to manage them.

This is a fork of [SirWaddles's JohnWickParse](https://github.com/SirWaddles/JohnWickParse)
project, which is intended primarily as a Fortnite tool.  At some point in late-ish 2020,
Fortnight updated the way they pack their data files, and the original JWP code was updated
to only work with that newer packing method.  Borderlands 3 still uses the original way,
and this fork offers various improvements useful to BL3 modders.  You can still use
official JWP releases up through 5.0.2 (which was released on July 23, 2020), but releases
after that point will probably not work with BL3.

As with the original JWP, which was intended only as a Fortnite tool, this fork will almost
certainly work just fine on other UE4 games, so feel free to give it a try if your UE4
game hasn't moved to the newer packing method yet.

It offers four commands that can read these files
 * `serialize <asset_path>` will turn a uexp/uasset pair into a .json file, reading the UObject properties. `<asset_path>` has no extension.
 * `filelist <pak_path>` will create a text file, listing all of the files contained in a .pak file.
 * `extract <pak_path> <pattern>` will extract all of the files where `<pattern>` is in the internal path name, into the corresponding directory in the current working folder.
 * `texture <asset_path>` will convert a DXT5 asset file into a png image file.

Any operations on a pak file require that the `key.txt` file contains the encryption key for the pak file, as a hexadecimal string and no leading newline.

Note however that there is limited support for all of the properties that can be serialized, and the parser may panic if it attempts to parse an unknown tag type.
