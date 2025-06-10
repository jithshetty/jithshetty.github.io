---
title: "Using Flyway For Database Deployment"
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Benifits of using Flyway For Database Deployment"
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

# Using Flyway For Database Deployment

**Flyway Database Migration:**

- Flyway helps to implement automated and version-based database migrations.
- Keeps the target database in Sync with the Migration folder where sql scripts are present.
- We will be using Community Distro with the command line version of Flyway (Maven option also available)

How flyway works..

[](https://lh7-us.googleusercontent.com/gHvlgsFfhREg05d5ICIf7ZWf-eaboL6OX1-w_L3mG-5Gq5kv8WXnVtehu6eWTPkxhG7eHrA5LFH1W42gjkZoD-jKgFNDdxMcN7xIqPjQnqd2UuRe9sqiL-n5SrrcD0coiafycdzCZsYu3LRxsPzEwEk)

**Useful Commands:**

flyway migrate - Migrate the changes to target Database

flyway info - To describe database migration pending changes

flyway undo - To run undo scripts (Not available with community edition)

Flyway repair - To repair failed migrations

**Script File Naming Convention:**

1. Versioned Scripts - V1.2__Create_Column.sql
2. Repeatable Scripts - R__V_MGP_APP_RAW_DATA.sql
3. Undo Scripts - U1.2__Create_Column.sql

**Common Usage:**

Error on Invalid File Name

[](https://lh7-us.googleusercontent.com/e3UV3PJZHF4iUUD-Uq0WUBgi7Fvh3FFUp1RWni-RIjyq09wVDS8IHcPedzBlQLsWOMUxEKi-FZNBkhDQLJcSMDbTRtUx9oM2f30jNofIPlht3v17A8EZXM1ej8D9aty9AA8G_ZQAvFYZmrgCQ6Rlw5Y)

Flyway Info

[](https://lh7-us.googleusercontent.com/UzmVYl5-3k-FziJEkTSIlsP8EnRam8h1qR3kL77110SAvS8xJhBfLtONODR4ZrWyEo-oBWy528SxjstbjkiCp1KN4kOet8ZLn5LG1ndSQp2tFEtP6B0MY15vYaQSqgk8VaVfwM6woiOkQNQXKicSw_Y)

Flyway Repair

[](https://lh7-us.googleusercontent.com/146TZn8ZHAIAaF_jVQ67G-GjfFEgeohFvw-lOgTOwIUYpSFbCKjoFY5Zq1oC_MWXc7TgbeD4OH5BerP5zJy-68HIjFirm3-VBXL43mSlJmrGoHmKk4XHPQCyMaOCHhAUG-QLHQZP8bypSMmlyfieKPk)

[](https://lh7-us.googleusercontent.com/R6EMCJPx2cQB1sNxAfABQllRHMTt-2hKKf7Qpe_2CkiiCWV-nR8hSzUR_DqOmY7hkE3k2_3jeikSeV3Cbi1PGAwoIQ9xyJIgW2hpMlZVdoNc42MJAEOIIUKa-53Ww1rjZAln2BMoAn3YH9R82CBO60s)

Flyway Migrate

[](https://lh7-us.googleusercontent.com/37MY59kNv9z0OA8LZeO5wRGY31PVepKszkILQLDGyzp8CENhfJQXzL8zhBfe3hCMpcyRoG2gXTrqA595MWWsxyc9xrtwiVzu00uVUwkElnGNDstmnBEh3UwH0yDUN4EAswGIw8xT0mBDtixb4M7QL34)

[](https://lh7-us.googleusercontent.com/SSLNT9tpcvCbhw1XoEuYLGLXzUoZ6jmof6nTobU5qAahljUqpY-W5DcwkxSVNNmP60rc2S9ndauhKQFF8XPJbdNNFNwQYNDM847hCTSVFR17VzwEJQJx4A1EKwWNJpfHJrHMJvluTE99hOEPXtPPYpw)

**Things to Note:**

- Transaction Rollback Supported for DML statements in script. For DDL not supported, since Oracle does not support.
- If success files are modified - Shows Failed - Can repair only checksum, description

**Open Items:**

- CI deploy process using flyway?
- Rollback?