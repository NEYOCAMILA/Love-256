
{
  "name": "Camila Artwork #1",
  "description": "This is a unique digital artwork from Camila series.",
  "image": "https://ipfs.io/ipfs/QmSomeIPFSHash",
  "attributes": [
    {
      "trait_type": "Background",
      "value": "Blue"
    },
    {
      "trait_type": "Art Style",
      "value": "Abstract"
    }
  ]
}uint256 public maxSupply = 1000;  // Example max supply of 1000 NFTs

function createNFT(address recipient, string memory tokenURI) public onlyOwner returns (uint256) {
    require(tokenCounter < maxSupply, "Max supply reached");
    tokenCounter += 1;
    uint256 newTokenId = tokenCounter;
    _safeMint(recipient, newTokenId);
    _setTokenURI(newTokenId, tokenURI);
    return newTokenId;
}