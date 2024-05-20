# Initial Investigation Report

**Date:** MAY 18 2024 
**All Rights Reserved.**

**0x845C3060d208dA2E0A4BC6F2Aa73ec59F88dd70f**

## Executive Summary
The preliminary investigation has identified a significant cluster created using software from a single programmer, aimed at executing low-cost transactions specifically for the L0 drop. This cluster is facilitated by tools designed to generate and manipulate wallets and transactions, primarily to bypass transaction fees.

## Findings

### 1. Cluster Origin and Tools
- The cluster has been generated using software developed by a single programmer, referred to as "from Sybil for Sybils":
  - GitHub Repository: [zaivanza GitHub](https://github.com/zaivanza?tab=repositories)
- The software is designed solely to perform low-cost transactions to benefit from L0 drops.

### 2. Software Utilization Process
- **Wallet Generation:**
  - `generate_evm_wallet`: [GitHub Link](https://github.com/zaivanza/generate_evm_wallet)

- **Minimizing Wallet Intersection:**
  - Tools used to manage wallet interactions and minimize collision, mainly from OKX exchange:
    - [all-in-one](https://github.com/zaivanza/all-in-one)
    - [okx-whitelist](https://github.com/zaivanza/okx-whitelist)
    - [all-in-one-v2](https://github.com/zaivanza/all-in-one-v2)
    - [aio-cex](https://github.com/zaivanza/aio-cex)

- **Transaction Route Creation:**
  - `all-in-one-v2`: [GitHub Link](https://github.com/zaivanza/all-in-one-v2) - Utilizes randomizers making pattern detection challenging but possible.

- **Community Engagement and Software Distribution:**
  - Community Channels:
    - [code_hodlmodeth Telegram](https://t.me/code_hodlmodeth)
    - [hodlmodeth Telegram](https://t.me/hodlmodeth)
    - [scripts_hodlmod_bot Telegram](https://t.me/scripts_hodlmod_bot)
  - Published Software:
    - `zerius-aio`: [GitHub Link](https://github.com/zaivanza/zerius-aio)
    - `nogem.app-aio`: [GitHub Link](https://github.com/zaivanza/nogem.app-aio)
  - These tools remove transaction fees, making transactions almost free and widely adopted by the Sybil community.

<details>
  <summary>Sybil apps Contracts</summary>

NOGEM_CONTRACTS = {
    "nova": "0x7564b019e013d90302BdD6FB6C9763d5989bEd0c",
    "fantom": "0x076FC64046E50A78267563470A159B6AbDDe9192",
    "mantle": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "gnosis": "0x612361f307751BE1B7B73cE6Af4d613754a64C2B",
    "tenet": "0x61b9aaFB29fE7391fa29c61d9cD5BcB9dE1e07C6",
    "telos": "0x92E5b93af8fB4eE8b1db0ac8dF85a6Bfa15651eE",
    "arbitrum": "0x96e1Bf9e743407B909A281210C58cE0990AacEd9",
    "celo": "0xEE9E828C04bA68c28eD7B29425380A2Ff8b5e3Ae",
    "beam": "0xa5A3C7719590F675552b3D257947AA2A5bfbC4db",
    "klaytn": "0x36c83bf151078404bf4927aef40c14fd862b88e4",
    "okx": "0xA194aa46612FEF6C3263986C02652e54b5Fd780c",
    "aurora": "0x01fC53d4C349704970D3Cb3B25505B9E4452AC42",
    "opbnb": "0xCcb4cA93560994b6F2760B99d8fCe6Aeddd9fc00",
    "core": "0x1f55dbaE710b9Ed5b1cBc8d4F5F4dfb6d966a2A2",
    "rari": "0x77DbDd3c9Ea256F7570ec754f2819f1b9cfA6185",
    "conflux": "0x36c83bf151078404bf4927aef40c14fd862b88e4",
    "zora": "0x1Ba667B038b8fAee90F1E41a84d79A9c8E0837fD",
    "horiz0n": "0xe4D8aBB420033F64289048184Bbd1Ae175E578F6",
    "optimism": "0x68217eAd11a77f559E29460a4665257a6A163877",
    "manta": "0xa2F3809254dD9Bd7E5c31e7E5D4b423a7d610BeD",
    "fuse": "0x1Ba667B038b8fAee90F1E41a84d79A9c8E0837fD",
    # "moonriver": "",
    # "moonbeam": "",
    "kava": "0xfa0aCcf6386942e7aC8Ab00Fc7C91f8b641AfA79",
    "polygon": "0xa6ce244C423Af2bCef522fc5Fbc1df28528Da2e0",
    "loot": "0x34EA96D233aFA4083eD7da9EA30893094af82F21",
    "bsc": "0xcd5cA2b4a23046f3c1c9c5ABFe9ED8737b77BFBd",
    "avalanche": "0xe25D5dCfA8Be6e7933A1335d1A23FB3A67f1a16A",
    "orderly": "0x59FBcA19b8d71FC264Bf2D97506e6a37E64AF510",
    "xpla": "0xfED33D64740122fB090352eAf7B497D092fC2A0f",
    "astar": "0x7D8083C47DE0CB33180e1B130F6de78a41AeBe75",
    "base": "0x8D5ba31f120157369ED4474338beA521109B1200",
    "metis": "0x13e541AD6987572B7A586b46Fb95b9f0fce78230",
    "viction": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "zksync": "0xBEc36178ff53DEac60B741174057EA7587f35b03",
    "linea": "0xB77F101f3382d55d56B43b2bc6Cf86E3E0d2CDbd",
    "scroll": "0x6aa62615C117CEd068093D4c7BFf78289ceA945A",
    "blast": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "mode": "0x92214B740B394894B38Ed80a1659eea862Ce89cd",
}

NOGEM_REFUEL_CONTRACTS = {
    "fantom": "0xa6ce244C423Af2bCef522fc5Fbc1df28528Da2e0",
    "mantle": "0x6D594b9FCb39E7E8942b431C0826BEeaE25bA39a",
    "gnosis": "0x92E5b93af8fB4eE8b1db0ac8dF85a6Bfa15651eE",
    "tenet": "0x711b03d666D4D0DbDa70aB52a269Ef8B0FfAb443",
    "telos": "0x0A7a3C0f088fdfBe92Fabdc5CB0279faC07CA553",
    "arbitrum": "0x663f02eb2d47f6993366fa61f8dfa27efbae85d4",
    "celo": "0xfa0accf6386942e7ac8ab00fc7c91f8b641afa79",
    "beam": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "klaytn": "0x6d594b9fcb39e7e8942b431c0826beeae25ba39a",
    "okx": "0x5bF3487c5fE99907A9a0d7f32D05eB3B2B8a0143",
    "aurora": "0x6D594b9FCb39E7E8942b431C0826BEeaE25bA39a",
    "astar": "0xA991694fd6d9DA350cdFD6D3f9c8E125Ce5B3185",
    "opbnb": "0xCeeB6BF11C6160D7cA3F531ce49329Ee82bed6d7",
    "core": "0xe4D8aBB420033F64289048184Bbd1Ae175E578F6",
    "rari": "0x982Db01501C862eCC8f1C9BDF4A48d7742C822Fa",
    "conflux": "0x8c1943a30e5a0072903fdb90bf424bdb7095c80e",
    "zora": "0xAE3474976AB102077d399f360d695719fd2F1525",
    "horiz0n": "0xe4D8aBB420033F64289048184Bbd1Ae175E578F6",
    "optimism": "0x6d594b9fcb39e7e8942b431c0826beeae25ba39a",
    "manta": "0x5bF3487c5fE99907A9a0d7f32D05eB3B2B8a0143",
    "fuse": "0xE7Dba4c592114f821822a7e9eA490541C6121Abb",
    "moonriver": "0x7D8083C47DE0CB33180e1B130F6de78a41AeBe75",
    "kava": "0x2212291025d65D6cFe91De3f0e1a6cAd4dC4AE36",
    "polygon": "0xf705B54bAA04A6C3306BD5421A49f9F4DC27c4C4",
    "loot": "0xAc9319982Bf2E64e4C41146c912a35F237180375",
    "bsc": "0x9f865ccCbb885d3770b2786cEB5c727Eb31e47ed",
    "avalanche": "0x1Ad837f828be78C4CF90BCe5426d592f7e8c1a6f",
    "orderly": "0xd575825c903AAc4D04439600B6d0d22f0E3a9367",
    "xpla": "0x59FBcA19b8d71FC264Bf2D97506e6a37E64AF510",
    "linea": "0x2809702F7900748fd579bF7d2B44b17437110cc7",
    "base": "0xC2b7ED18184d3EAa08bD03418d2929D452dbd6Fa",
    "blast": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "mode": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    "scroll": "0x5c36F7A7090877B6c3EB2C554865f7F125B8f312",
} 

NOGEM_FILLER_CONTRACTS = {
    "arbitrum": "0x2212291025d65D6cFe91De3f0e1a6cAd4dC4AE36",
    "polygon": "0x2809702f7900748fd579bf7d2b44b17437110cc7",
    "bsc": "0xE7Dba4c592114f821822a7e9eA490541C6121Abb",
    "optimism": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "fantom": "0x6D594b9FCb39E7E8942b431C0826BEeaE25bA39a",
    "core": "0xfb7ef0bbd8bfb5f129f995fbc34f4d786ccc63cf",
    "nova": "0xe4D8aBB420033F64289048184Bbd1Ae175E578F6",
    "mantle": "0xd8c12333aC7b6e24416F9175E242bD302f4dFd19",
    "avalanche": "0x9020Cb8D5516497F25e5Cd0877f563fe9Ed2daEa",
    "base": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "linea": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "scroll": "0x9cE5f55c5CF1EA63D1CB3ac4EfC7FBe07e83916B",
    "zora": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "astar": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "aurora": "0xfb7ef0bbd8bfb5f129f995fbc34f4d786ccc63cf",
    "celo": "0xA991694fd6d9DA350cdFD6D3f9c8E125Ce5B3185",
    "conflux": "0xfb7ef0bbd8bfb5f129f995fbc34f4d786ccc63cf",
    "fuse": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "gnosis": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    # "harmony": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    "kava": "0x5E4bca80c6af462DE4d7678c59B558873f0049d0",
    "klaytn": "0x5359a9a6351147Ba66a2C750c746743d73BdBeDD",
    "manta": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "metis": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    # "moonbeam": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    # "moonriver": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "opbnb": "0xAc9319982Bf2E64e4C41146c912a35F237180375",
    # "polygon_zkevm": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "telos": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "tenet": "0xFb7EF0BbD8bFB5f129F995FbC34F4D786cCC63CF",
    "horizen": "0xE1ba542dBCB25351557F4Cc7dFa743877A38a1e0",
    "okx": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    "orderly": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    "rari": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    #"viction": "0x36c83bf151078404bf4927AeF40C14FD862B88e4",
    "xpla": "0xE73c6F1B6F43142Ea545053DaAB6Fc2c514DfeAA",
    #"loot": "0xE1ba542dBCB25351557F4Cc7dFa743877A38a1e0"
}


Zerius contracts
contracts = {
    'ethereum': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41', 
    'optimism': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41', 
    'bsc': '0x250c34D06857b9C0A036d44F86d2c1Abe514B3Da', 
    'polygon': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41', 
    'arbitrum': '0x250c34D06857b9C0A036d44F86d2c1Abe514B3Da', 
    'avalanche': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41', 
    'base': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41',
    'zora': '0x178608fFe2Cca5d36f3Fc6e69426c4D3A5A74A41',
    'scroll': '0xEB22C3e221080eAD305CAE5f37F0753970d973Cd',
    'zksync': '0x7dA50bD0fb3C2E868069d9271A2aeb7eD943c2D6',
    'linea': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'nova': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'metis': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'moonbeam': '0x4c5AeDA35d8F0F7b67d6EB547eAB1df75aA23Eaf',
    'polygon_zkevm': '0x4c5AeDA35d8F0F7b67d6EB547eAB1df75aA23Eaf',
    'core': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'celo': '0x4c5AeDA35d8F0F7b67d6EB547eAB1df75aA23Eaf',
    'harmony': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'canto': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'fantom': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'gnosis': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
    'mantle': '0x5188368a92B49F30f4Cf9bEF64635bCf8459c7A7',
}
REFUEL_CONTRACTS = {
    'optimism'      : '0x2076BDd52Af431ba0E5411b3dd9B5eeDa31BB9Eb',
    'bsc'           : '0x5B209E7c81DEaad0ffb8b76b696dBb4633A318CD',
    'arbitrum'      : '0x412aea168aDd34361aFEf6a2e3FC01928Fba1248',
    'polygon'       : '0x2ef766b59e4603250265EcC468cF38a6a00b84b3',
    'polygon_zkevm' : '0xBAf5C493a4c364cBD2CA83C355E75F0ff7042945',
    'zksync'        : '0xec8afef7afe586eb523c228b6baf3171b1f6dd95',
    'avalanche'     : '0x5B209E7c81DEaad0ffb8b76b696dBb4633A318CD',
    'gnosis'        : '0x1fe2c567169d39CCc5299727FfAC96362b2Ab90E',
    'fantom'        : '0xBFd3539e4e0b1B29e8b08d17f30F1291C837a18E',
    'nova'          : '0x3Fc5913D35105f338cEfcB3a7a0768c48E2Ade8E',
    'harmony'       : '0x5B209E7c81DEaad0ffb8b76b696dBb4633A318CD', # unavailable : need to convert it to a one-address
    'core'          : '0xB47D82aA70f839dC27a34573f135eD6dE6CED9A5',
    'celo'          : '0xFF21d5a3a8e3E8BA2576e967888Deea583ff02f8',
    'moonbeam'      : '0xb0bea3bB2d6EDDD2014952ABd744660bAeF9747d',
    'base'          : '0x9415AD63EdF2e0de7D8B9D8FeE4b939dd1e52F2C',
    'scroll'        : '0xB074f8D92b930D3415DA6bA80F6D38f69ee4B9cf',
    'zora'          : '0x1fe2c567169d39CCc5299727FfAC96362b2Ab90E',
    'linea'         : '0x5B209E7c81DEaad0ffb8b76b696dBb4633A318CD',
    'metis'         : '0x1b07F1f4F860e72c9367e718a30e38130114AD22',
    'mantle'        : '0x4F1C698e5cA32b28030E9d9F17C164F27aB5D866',
   }

</details>

### 3. Verification
This list has been cross-verified using the latest snapshot from the L0 team, clearly stating all users of the contracts.

### 4. Evidence
- **Zerius Software:**
  - Released: 19 October 2023 (Proof of Release and Activity: refer to attached figures)
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/1.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/1.png" alt="1.png" style="width: 100px;"/>
  </a>
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/2.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/2.png" alt="2.png" style="width: 100px;"/>
  </a>
  
- **NOGEM Software:**
  - Released: 22 March 2024 (Proof of Release and Activity: refer to attached figures)
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/3.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/3.png" alt="3.png" style="width: 100px;"/>
  </a>
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/4.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/4.png" alt="4.png" style="width: 100px;"/>
  </a>

- **Random Wallet Patterns:**
  - Examples of wallet generation patterns are depicted in the attached figures.
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/5.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/5.png" alt="5.png" style="width: 100px;"/>
  </a>
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/6.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/6.png" alt="6.png" style="width: 100px;"/>
  </a>
  <a href="https://raw.githubusercontent.com/tiahrttric/lz/main/7.png" target="_blank">
      <img src="https://raw.githubusercontent.com/tiahrttric/lz/main/7.png" alt="7.png" style="width: 100px;"/>
  </a>
  
## Conclusion
After excluding previously marked Sybil addresses, 44,543 addresses remain for further analysis, with distinct clusters of 50 or more addresses each. Deeper investigation is deemed unnecessary as nearly all users interacting with these contracts are identified as Sybils, proficient in using command lines, coding, and multi-accounts.

### Additional Evidence

**Sybil Wallets List:**

You can view the list of sybil wallets [here](https://raw.githubusercontent.com/tiahrttric/lz/main/sybil_wallets.txt).


**All Rights Reserved**

**Used only public source**
