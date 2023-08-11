# Apollo lyrics format

## Introduction

This repository is dedicated to research concerning the format and architecture of exported lyrics and additionnal content (see [Additional content](#additionnal-content)) in addition to its code parallel (used in Apollo source code)  using the multiplatform application Apollo.

Even though the latter is (as these lines are written) closed source, building an open source format seemed more than convenient for future re-use, file exploitation or even similar research. 

The author reserves the right to voluntarily censor or hide any file, protocol or system for security or other concerns and may fairly indicate it by courtesy.

This file currently does not follow any conventional rule of writing, due to a lack of time. Read it as a rough draft.
## NB
Apollo export file format, including lyrics and any additionnal content will be refered in the following lines as "**Apollo file architecture**". 

## License
Note that this respository is published using a Copyleft license. **Any use is allowed**, but the user is obliged to publish its reuse, modified or not, as an **available Open Source repository.** Apollo is not intended to become a business: please respect this obligation.

## Goals
The Apollo lyrics architecture must follow the following rules :
- Fast and quick to learn
- Lightweight: the package (lyrics + content) will be compressed, however, package content must use convenient file formats to fit on a mobile device without losing any quality
- Scalable: for now, lyrics and additionnal content are simple. However, their use might vary or even reach bigger sizes. (see [Migration](#migration))
- Limitations : in order to prevent an euphoric architecture or file expansion, the Apollo file architecture bust be constrained to the following [limitations](#limitations).

## Limitations
The Apollo file architecture is **NOT INTENDED** to deal with any other medias than **AUDIO FILES** (including recordings and backing tracks), **PICTURES** (including album covers, artist profile pictures), **TEXT FILES** (including metadata, but also any kind of encryption that might be use to secure and authenticate a song).

**VIDEOS**, **EXECUTABLES** or any other format not previously mentionned shall not be used for this project.

However, a direct linking / embed to any unsupported type of file is supported.

## Migration
The Apollo file architecture must **mention or contain a tag indicating its version and a minimal application version.**

- **Minor features addition or fixes** shall be designed *on the file side* to not cause any failure *on the application side* even with a downgrade of an upgrade of the latter.
- **Major features addition or fixes** shall be designed *on both sides* to require a **minimum application version** but to not cause any failure after an application upgrade.
- **Security or major flaws fixes** must be designed to prevent the user from using and sharing it, for instance with prompts during the import. A clear blacklist of faulty versions must be established and **publicly published**. 
## Additionnal content
Current additionnal contents follows :
- **Backing track**
- **Album cover**


## Architecture
Now that the main guidelines are stated, refer to [ARCHITECTURE.md](./ARCHITECTURE.md) and its code parallel [CODE_ARCHITECTURE.md](./CODE_ARCHITECTURE.md) to learn about the practical structure.