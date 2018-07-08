
# Merkle Root


```python
# Merkle Root Example

from helper import double_sha256, merkle_parent_level

hex_hashes = [
    'c117ea8ec828342f4dfb0ad6bd140e03a50720ece40169ee38bdc15d9eb64cf5',
    'c131474164b412e3406696da1ee20ab0fc9bf41c8f05fa8ceea7a08d672d7cc5',
    'f391da6ecfeed1814efae39e7fcb3838ae0b02c02ae7d0a5848a66947c0727b0',
    '3d238a92a94532b946c90e19c49351c763696cff3db400485b813aecb8a13181',
    '10092f2633be5f3ce349bf9ddbde36caa3dd10dfa0ec8106bce23acbff637dae',
    '7d37b3d54fa6a64869084bfd2e831309118b9e833610e6228adacdbd1b4ba161',
    '8118a77e542892fe15ae3fc771a4abfd2f5d5d5997544c3487ac36b5c85170fc',
    'dff6879848c2c9b62fe652720b8df5272093acfaa45a43cdb3696fe2466a3877',
    'b825c0745f46ac58f7d3759e6dc535a1fec7820377f24d4c2c6ad2cc55c0cb59',
    '95513952a04bd8992721e9b7e2937f1c04ba31e0469fbe615a78197f68f52b7c',
    '2e6d722e5e4dbdf2447ddecc9f7dabb8e299bae921c99ad5b0184cd9eb8e5908',
    'b13a750047bc0bdceb2473e5fe488c2596d7a7124b4e716fdd29b046ef99bbf0',
]

current_level = [bytes.fromhex(x) for x in hex_hashes]
while len(current_level) > 1:
    current_level = merkle_parent_level(current_level)
print(current_level[0].hex())
```

### Try it

#### Calculate the Merkle Root given these hashes
```
42f6f52f17620653dcc909e58bb352e0bd4bd1381e2955d19c00959a22122b2e
94c3af34b9667bf787e1c6a0a009201589755d01d02fe2877cc69b929d2418d4
959428d7c48113cb9149d0566bde3d46e98cf028053c522b8fa8f735241aa953
a9f27b99d5d108dede755710d4a1ffa2c74af70b4ca71726fa57d68454e609a2
62af110031e29de1efcad103b3ad4bec7bdcf6cb9c9f4afdd586981795516577
766900590ece194667e9da2984018057512887110bf54fe0aa800157aec796ba
e8270fb475763bc8d855cfe45ed98060988c1bdcad2ffc8364f783c98999a208
921b8cfd3e14bf41f028f0a3aa88c813d5039a2b1bceb12208535b0b43a5d09e
15535864799652347cec66cba473f6d8291541238e58b2e03b046bc53cfe1321
1c8af7c502971e67096456eac9cd5407aacf62190fc54188995666a30faf99f0
3311f8acc57e8a3e9b68e2945fb4f53c07b0fa4668a7e5cda6255c21558c774d
```


```python
# Exercise 4.1

from helper import double_sha256, merkle_parent_level
hex_hashes = [
    '42f6f52f17620653dcc909e58bb352e0bd4bd1381e2955d19c00959a22122b2e',
    '94c3af34b9667bf787e1c6a0a009201589755d01d02fe2877cc69b929d2418d4',
    '959428d7c48113cb9149d0566bde3d46e98cf028053c522b8fa8f735241aa953',
    'a9f27b99d5d108dede755710d4a1ffa2c74af70b4ca71726fa57d68454e609a2',
    '62af110031e29de1efcad103b3ad4bec7bdcf6cb9c9f4afdd586981795516577',
    '766900590ece194667e9da2984018057512887110bf54fe0aa800157aec796ba',
    'e8270fb475763bc8d855cfe45ed98060988c1bdcad2ffc8364f783c98999a208',
    '921b8cfd3e14bf41f028f0a3aa88c813d5039a2b1bceb12208535b0b43a5d09e',
    '15535864799652347cec66cba473f6d8291541238e58b2e03b046bc53cfe1321',
    '1c8af7c502971e67096456eac9cd5407aacf62190fc54188995666a30faf99f0',
    '3311f8acc57e8a3e9b68e2945fb4f53c07b0fa4668a7e5cda6255c21558c774d',
]

# bytes.fromhex to get all the hashes in binary
# initialize current level to be the hashes
# loop until current_level has only 1 element
    # make the current level the parent level
# print the root's hex
```

### Test Driven Exercise


```python
def merkle_root(hash_list):
    '''Takes a list of binary hashes and returns the merkle root
    '''
    # current level starts as hash_list
    # loop until there's exactly 1 element
        # current level becomes the merkle parent level
    # return the 1st item of current_level
    pass
```
