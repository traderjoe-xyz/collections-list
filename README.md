# Joepegs Collections List

This repo contains logos, banners, and collection info for the Joepegs marketplace. May be deprecated in future.

## Add new collections

Add collection info to the `joepegs.collections.json` like the below example.

1. **Contract addresses should be checksummed.**

- If it is all lower-case it is likely not correct.
- Enter it into snowtrace, and then copy the address from the UI.

2. `symbol` can be found from snowtrace.

3. `description` can be the length of tweet, but no hard limits.

```
"collections": {
    "0x880Fe52C6bc4FFFfb92D6C03858C97807a900691": {
      "bannerURI": "https://raw.githubusercontent.com/traderjoe-xyz/collections-list/main/images/0x880Fe52C6bc4FFFfb92D6C03858C97807a900691/banner.png",
      "description": "Avalanche Party Animals is a collection of 10,000 unique, NFTs, who are breaking the dance floor on the Avalanche Blockchain and can’t wait to finally enter the Party Animals Mansion. APA are based on the unofficial Avalanche mascot, Wolfie. We hope to bring it to its rightful place as the official mascot and by doing so, also bring recognition to the platform. Each Party Animal is hand-drawn by our talented artist anxd is randomly generated from numerous of assets. All of them are unique, but some are simply legendary.",
      "discordURI": "https://t.co/BkdreWVBMTt",
      "logoURI": "https://raw.githubusercontent.com/traderjoe-xyz/collections-list/main/images/0x880Fe52C6bc4FFFfb92D6C03858C97807a900691/logo.png",
      "name": "Party Animals",
      "symbol": "APA",
      "twitterURI": "https://twitter.com/apa_nft",
      "verified": "verified_trusted",
      "websiteURI": "https://partyanimalsxyz.com//"
    },
    ...
},
```

4. Add `banner.png` into the location like `images/<address>/banner.png`.

- Should be `1440x240px` size
- **must** be renamed `banner.png`

5. Add `logo.png` into the location like `images/<address>/logo.png`.

- Should be `200x200px` size
- **must** be renamed `logo.png`

6. The `verified` field can be `unverified, verified, verified_trusted` to denote number of ticks. Obviously if they are `unverified` ticks, murloc will come ask you what you're doing.

7. `JSON` files are similar to lists; make sure you add a `,` to the previous entry like so:

```
    collections: {
        "<some collection address>": {
            some collection ...
        }, // add this comma here
        "<your new collection address>": {
            some collection ...
        }, // don't add comma here
    }
```

## Updating

You can in fact add files and change JSON file directly in github on browser.

- When saving changes always select Pull Request (PR).
- Name the branch after the collection you are adding or fixing, e.g. `add-APA` or `fix-APA`.
- Don't worry about versioning.

## NFT SZN

**NFT SZN** is a campaign to promote Nft trading on our platform. When launched:

- Partners agree to lower `% Royalty Fees` for their collections.
- Joepegs will lower `% Platform Fees` for participating partners. (default is 2.5%)
- Participating partners will also receive a visible `NFT SZN` badge on the platform.

Participating partners will be configured as follows:

```
    "0x8ef...": {
        ...,

        // nftSzn config is for front-end display only:
        //      royalty fee:  ~~5%~~    2.5%
        //      platform fee: ~~2.5%~~  0%
        "nftSzn": {
            "royaltyFee":           0.05,       // regular 5% royalty fee
            "campaignRoyaltyFee":   0.025,      // campaign 2.5% fee
            "platformFee":          0.025,      // regular 2.5% platform fee
            "campaignPlatformFee":  0,          // campaign 0% platform fee
        }
    },

```

## Artist Showcase

**Showcase** is a feature to promote visibility for unique NFTs on our homepage.

- It shows artist NFT on homepage carousel.
- When clicked, it can direct to an external URL belonging to the artist.
- To apply, partners have to post link to nft and tag us on twitter or instagram.
- Ops team select for the list, to be updated e.g. weekly.
- Suggest no more than 7 items.

```
showcase: [
    {
        // <collectionId>-<tokenId>
	    itemId: '0x6af53a162deb0d3abfd4f47bd6c9615b08d553fd-51',
        // any URL
    	externalUrl: 'https://artist.website.com'
    }
]
```

**VERY IMPT** should ensure external URL doesn't have any malicious code.
