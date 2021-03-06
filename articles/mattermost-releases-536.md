---
title: "Mattermost 5.36ã®æ°æ©è½"
emoji: "ð"
type: "tech" # tech: æè¡è¨äº / idea: ã¢ã¤ãã¢
topics: ["mattermost", "releases"]
published: true
date: 2021-06-18T07:30:00+09:00
draft: false
toc: true
---

Mattermost è¨äºã¾ã¨ã: https://blog.kaakaa.dev/tags/mattermost/

# ã¯ããã«

2021/06/16 ã« Mattermost v5.36.0 ããªãªã¼ã¹ããã¾ããã 

æ¬è¨äºã¯ãåäººçã«æ°ã«ãªã£ãæ°ããæ©è½ãªã©ãåããã¦ã¿ããã¨ãç®çã¨ãã¦ãã¾ãããã
å¤æ´åå®¹ã®è©³ç´°ã«ã¤ãã¦ã¯å¬å¼ã®ãªãªã¼ã¹ãç¢ºèªãã¦ãã ããã

- [Mattermost v5\.36 is now available \- Upgrade today to try the new features](https://mattermost.com/blog/mattermost-release-v5-36/)
- [Mattermost Changelog](https://docs.mattermost.com/administration/changelog.html#release-v5-36-feature-release)

## MatterCon 2021

[MatterCon 2021 \- Learn about the latest and greatest from Mattermost\!](https://mattermost.com/events/mattercon-2021/)

Mattermostã®Virtualã³ãã¥ããã£ã¤ãã³ãã§ããMatterConãæ¥é±6/22-24ã®éã§éå¬ããã¾ãã
èª°ã§ãç¡æã§åå ã§ããã¤ãã³ãã®ããã§ãä¸è¨ã®ãµã¤ãããåå ç»é²ã§ãã¾ãã

MatterConã¯ãä»ã¾ã§ãã³ãã¥ããã£ã¡ã³ãéå®ã§å¹´ã«ä¸åãªãã©ã¤ã³ã§éå¬ããã¦ããã¤ãã³ãã§ããããã³ã­ãç¦ã¨ãããã¨ãããVirtualéå¬ã§ãããªãã¯ãªã¤ãã³ãã«ãªã£ãããã§ãã([éå»ã®MatterCons](https://handbook.mattermost.com/contributors/mattercon#past-mattercons))

Mattermostã¯ãã«ãªã¢ã¼ãã®ä¼ç¤¾ã®ãããç¤¾å¡ãã³ãã¥ããã£ã¡ã³ãã¼ãåæçãªã³ãã¥ãã±ã¼ã·ã§ã³ãè¡ãå ´ã¨ããã®ãMatterConã®ä¸»ãªç®çã§ããããã®ä»ã«ããã«ãªã¢ã¼ãã®ä¼ç¤¾ãªãã§ã¯ã®ç¥è¦ã®ç´¹ä»ããæ°æ©è½ã®ãã¢ãã­ã¼ãããããMattermoståã®Open Source Fridayãã­ã¸ã§ã¯ãã«ã¤ãã¦ã®ç´¹ä»ãªã©ãããããã§ãã

---

åæ©è½ã®è¦åºãåã®è¨å·ã¯ããã®æ©è½ãå©ç¨å¯è½ãªã¨ãã£ã·ã§ã³ãè¡¨ãã¦ãã¾ãã

- `Cloud`: [Mattermost Cloud](https://mattermost.com/pricing-cloud/)
- `E20/E10`: [Enterprise E20/E10](https://mattermost.com/pricing-self-managed/)

è¦åºãã®åã«ä½ããªãå ´åãTeam Edition(OSS ç)ã§ãå©ç¨å¯è½ãªæ©è½ã§ãã

## Focalboard Plugin

ä»¥åããéçºãé²ãããã¦ããNotion, Trello, Asanaã¯ã­ã¼ã³ã®Kanbanãã¼ã«ã§ãã[Focalboard](https://www.focalboard.com/)ããMattermost Pluginã¨ãã¦å©ç¨ã§ããããã«ãªãã¾ããã

Focalboard Mattermost Pluginã«ã¤ãã¦ã¯ãä»¥ä¸ã®è¨äºã«ä½¿ã£ã¦ã¿ãææ³ãæ¸ãã¦ãã¾ãã
[Focalboardã®Mattermostãã©ã°ã¤ã³ã«ã¤ãã¦](https://zenn.dev/kaakaa/articles/mattermost-focalboard-plugin)

ä¸è¨ã®è¨äºã§ã¯ããã©ã°ã¤ã³ãã¤ã³ã¹ãã¼ã«ããæ¹æ³ã¨ãã¦`.tar.gz`ãã¡ã¤ã«ãã¢ããã­ã¼ãããæ¹æ³ãç´¹ä»ãã¦ãã¾ããããMarketplaceããæ°ã¯ãªãã¯ã§ã¤ã³ã¹ãã¼ã«ããæé ãå¬å¼ã®YouTubeãã£ã³ãã«ã§1åç¨åº¦ã®åç»ã¨ãã¦ç´¹ä»ããã¦ãã¾ãã

https://youtu.be/V_pLVc4K-1g

Mattermostã¸ã®ãã­ã­ã·ã¨ãã¦nginxãApacheãä½¿ç¨ãã¦ããå ´åã¯ãè¿½å ã®è¨­å®ãå¿è¦ã«ãªãã¾ãã

[How to configure the NGINX or Apache web proxy to enable the Focalboard plugin Â· Discussion \#566 Â· mattermost/focalboard](https://github.com/mattermost/focalboard/discussions/566)

## (E20/Cloud) Incident Collaborationã®æ¹å

ä»æã[Mattermost Incident Collaboration Plugin](https://github.com/mattermost/mattermost-plugin-incident-collaboration)ã®æ¹åãããã¾ãã

### ãã¼ã å¨ä½ã«å¯¾ããPlaybookã¢ã¯ã»ã¹æ¨©è¨­å®

ä½æãããPlaybookã«å¯¾ããã¢ã¯ã»ã¹æ¨©ãè¨­å®ããéã«ãã¡ã³ãã¼åä½ã®ã¢ã¯ã»ã¹æ¨©è¨­å®ã ãã§ãªãããã¼ã å¨ä½ã«å¯¾ããã¢ã¯ã»ã¹æ¨©ãè¨­å®ã§ããããã«ãªãã¾ããã

![incident-edit-team](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/incident-edit-team.png)

### Playbookä½ææ¨©éã®ç®¡ç

Playbookãä½æã§ããæ¨©éãã¡ã³ãã¼åä½ã§è¨­å®ã§ããããã«ãªãã¾ããã

![incident-create-permission](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/incident-create-permission.png)

### Welcomeã¡ãã»ã¼ã¸

Playbookã«Welcomeã¡ãã»ã¼ã¸ãè¨­å®ã§ããããã«ãªãã¾ããã
Welcomeã¡ãã»ã¼ã¸ã¯ãPlaybookãåã«ä½æããããã£ã³ãã«ã«å§ããåå ããæã«è¡¨ç¤ºãããã¡ãã»ã¼ã¸ã§ããã¤ã³ã·ãã³ãå¯¾å¿æã«æè­ãã¦ããã¦æ¬²ãããã¨ããè¦ã¦ããã¦ã»ãããµã¤ãã¸ã®ãªã³ã¯ãªã©ãæå®ãã¦ãããã¨ã§ãç¡é§ãªã³ãã¥ãã±ã¼ã·ã§ã³ãåæ¸ãããã¨ãæå¾ã§ãã¾ãã

![incident-welcome-setting](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/incident-welcome-setting.png)
![incident-welcome-message](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/incident-welcome-message.png)

## ç ´å£çå¤æ´

### é«å¯ç¨ã¢ã¼ãã®éä¿¡ãã´ã·ãããã­ãã³ã«ã«

åç¨çãå©ç¨ãã¦ããã¦ã¼ã¶ã¼ã§ã[å¯ç¨æ§ãé«ããããã®ã¯ã©ã¹ã¿ãªã³ã°æ©è½](https://docs.mattermost.com/deployment/cluster.html#high-availability-cluster-e20)ãå©ç¨ãã¦ããå ´åã«ãã¯ã©ã¹ã¿éã®éä¿¡ã[ã´ã·ãããã­ãã³ã«](https://ja.wikipedia.org/wiki/%E3%82%B4%E3%82%B7%E3%83%83%E3%83%97%E3%83%97%E3%83%AD%E3%83%88%E3%82%B3%E3%83%AB)ã§è¡ãããããã«ãªãã¾ãããä»ã¾ã§ã¯ã´ã·ãããã­ãã³ã«ã®ä½¿ç¨ã¯ãªãã·ã§ã³ã§ãããããã®ãªãã·ã§ã³ãå»æ­¢ãããã´ã·ãããã­ãã³ã«ã®ã¿ãç¨ããããããã«ãªãã¾ããã¯ã©ã¹ã¿æ§æã§ã¯ãå¨ã¦ã®ãã¼ããåããã­ãã³ã«ãå©ç¨ãã¦éä¿¡ãã¦ããå¿è¦ããããããç¾å¨ã´ã·ãããã­ãã³ã«ãå©ç¨ãã¦ããªãå ´åã¯ãã´ã·ãããã­ãã³ã«ãä½¿ç¨ããã¢ããã°ã¬ã¼ããè¡ãããä¸åº¦å¨ã¦ã®ãã¼ããã·ã£ãããã¦ã³ãã¦ããã¢ãã°ã¬ã¼ãããå¿è¦ãããããã§ãã

https://docs.mattermost.com/administration/changelog.html#important-upgrade-notes

## ãã®ä»ã®ãããã¯

### Collapsed Reply Thread

è¦æã®å¤ãè¿ä¿¡ã®æãç³ã¿æ©è½(Collapsed Reply Thread)ããæ¥æãªãªã¼ã¹ããããã¼ã¸ã§ã³ãããã¼ã¿çã®æ©è½ã¨ãã¦å©ç¨å¯è½ã«ãªãäºå®ã§ããã¾ããã¯ã©ã¦ãçã§ã¯ä»æã®ãªãªã¼ã¹ããå©ç¨å¯è½ã«ãªãäºå®ã§ãã

![collapsed-thread-announce](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/collapsed-thread-announce.png)

Mattermostã³ãã¥ããã£ç¨ã®ãã£ããã§ã¯ãã§ã«å©ç¨å¯è½ã«ãªã£ã¦ãã¾ãã**ã¢ã«ã¦ã³ãè¨­å® > è¡¨ç¤º > è¿ä¿¡ã¹ã¬ããã®æãããã¿** ããæå¹ã«ãããã¨ãã§ãã¾ãã

https://community.mattermost.com

![collapsed-thread-setting](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.36/collapsed-thread-setting.png)


### Mattermost 6.0?

Mattermostã®JIRAãè¦ãã¨ã`v6.0(Sep 15)`ã¨ãããã¼ã¸ã§ã³ãè¦ãã¾ãã9æã«ã¡ã¸ã£ã¼ãã¼ã¸ã§ã³ã¢ãããè¡ãããã®ããããã¾ããã  

https://mattermost.atlassian.net/browse/MM-36539?jql=project%20%3D%20%22MM%22%20AND%20fixVersion%20%3D%20%22v6.0%20(Sep%2015)%22

## ãããã«

æ¬¡ã®`v5.37`ã®ãªãªã¼ã¹ã¯ 2021/07/16(Fri)ãäºå®ãã¦ãã¾ãã

---

[Mattermost æ¥æ¬èª\(@mattermost_jp\)ãã \| Twitter](https://twitter.com/mattermost_jp?lang=ja) ã§ Mattermost ã«é¢ããæ¥æ¬èªã®æå ±ãæä¾ãã¦ãã¾ãã
