# Original repository
https://github.com/beardypig/pymp4

# What have i modified
1. Add more file support, such like 'vpcc' encoding;
2. Fix some bugs
3. Improve some methods, such like BoxUtil.find, you can find out children, entries and sboxs in the box now;

# Why not push request to the original repository
There are too much incompatible code with the origin, so i decide to create a new one.


# pymp4
Python MP4 box parser and toolkit

# Usage

`pymp4` is based on the excellent parsing library [construct](https://github.com/construct/construct).

```python
>>> from pymp4.parser import Box
>>> from io import BytesIO

>>> Box.build(dict(
    type=b"ftyp",
    major_brand="iso5",
    minor_version=1,
    compatible_brands=["iso5", "avc1"]))
b'\x00\x00\x00\x18ftypiso5\x00\x00\x00\x01iso5avc1'

>>> ftyp = Box.parse(b'\x00\x00\x00\x18ftypiso5\x00\x00\x00\x01iso5avc1')
>>> print(ftyp)
Container:
    type = ftyp
    major_brand = iso5
    minor_version = 1
    compatible_brands = ListContainer:
        iso5
        avc1

```
