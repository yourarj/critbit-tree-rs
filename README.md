# critbit-tree-rs
critbit tree rust implementation

This project aims at decoding and documenting the backbone of serum dex. critbit.

Disclaimer: All the initial source code is borrowed from [serum project](https://github.com/project-serum/serum-dex/blob/master/dex/src/critbit.rs). I have modified/enhanced it as required. Sole intention is to help understand the implementation and architecture

## critbit tree 
A crit-bit tree stores a prefix-free set of bit strings: a set of 64-bit integers, for example, or a set of variable-length 0-terminated byte strings.

A crit-bit tree supports the following operations (and more!) at high speed:

- See whether a string x is in the tree.
- Add x to the tree.
- Remove x from the tree.
- Find the lexicographically smallest string in the tree larger than x, if there is one.
- Find all suffixes of x in the tree, i.e., all strings - in the tree that have x as a prefix. Of course, this can take a long time if there are many such strings, but each string is found quickly. 

A crit-bit tree can be used as a high-speed associative array. For example, an array mapping 54 to 1, 19 to 2, 99 to 3, 85 to 4, and 88 to 5 can be stored as a crit-bit tree containing 54=1, 19=2, 99=3, 85=4, and 88=5. The smallest string in the crit-bit tree larger than 85= is 85=4. 