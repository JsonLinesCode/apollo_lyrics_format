# Merging and versions
To make music collaboration easier, Apollo can be compared to a simple versionning system with *branches* that everyone can merge with the following obligations.

Note that this is a discreet and facultative system : an artist can always manage and create Apollo projects without using the versionning.

## Version
A version of lyrics is a snapshot of every text content, music of a lyrics project. 
### Version vs. History
History is stored locally and stores the 20 last changes of **each version** of each **Apollo project**. It allows the user to undo an unwanted change.
It does not save nor can recover :
- Media replacements (backtracks, album covers).

While every media is saved separately in each **version**.

However its cannot be used as a real **milestone** or **backup**. Its is highly untrustable compared to a **version.** 
- History is reset after a merge but last history can be accessed in the back up version.
- History is never shared when you share an `.ollo` file.
- It is highly recommended to create a new version to change the backtrack music  
## Terms
At the creation of an Apollo project file, the author is considered as **main author**. The project behavior will strictly follow the rules mentionned in [Ownership](#ownership).

The first lyrics version then created - even if considered by the main author as draft - is called **main version**.
## Functionning
To merge an Apollo version, one can just import or open a `.ollo` file on its device using either:
- The saved files history on the Apollo application
- The dedicated importing system on the Apollo application
- Any other dedicated system that will be implemented in the future (i.e a cloud browsing system)

The author can now access the Versionning menu by clicking the **three dots** on the top right corner then by selecting **Versions**. 

### To merge a version into another one
1. The author must checkout the target version. 
2. The author must select the version to merge in the versionning menu.
3. The author is then prompted to review any merge change and can decide, through the A/B menu which change can be accepted or not.
4. He can now accept the merge.

- A version before the merge will automatically be created after a successful merging.
## Rules
### Ownership
- The **main version** (original lyrics) must always be present in the `.ollo` package. By the way, [Authentication](./AUTH.md) should prevent an opposite behavior. It cannot be removed.
- No one else than the main author can edit the main version of an .ollo file. The latter is considered as **original lyrics**.
- Any new version will be set with the **main author** as co-author

### Merging ownership
- Author of a merged version is added as **co-author** of the target version
## Advice
Its is **highly recommended** (thus non obliged) for the **main author** to consider the **main version** as the final / original version of their work.

As there are no version limitations the following work process can be useful and is **highly recommended** (and follows the application concept) :
1. The main author creates the main version.
2. The main author works freely on the main version as a draft.
3. When a step of advancement is judged reached the main author can create a **Step version**. 
4. (optional) For any other **step**, **experiment** a version can be created.
5. (optional) The main author can then export (and optionally publish) the `.ollo` file for review or active collaborating.
6. Any version satisfying the main author can then be merged / partially merged into the main version.
