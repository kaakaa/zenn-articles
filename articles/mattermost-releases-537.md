---
title: "Mattermost 5.37ã®æ°æ©è½"
emoji: "ð"
type: "tech" # tech: æè¡è¨äº / idea: ã¢ã¤ãã¢
topics: ["mattermost", "releases"]
published: true
date: 2021-07-17T13:30:00+09:00
draft: false
toc: true
---

Mattermost è¨äºã¾ã¨ã: https://blog.kaakaa.dev/tags/mattermost/

# ã¯ããã«

2021/07/16 ã« Mattermost v5.37.0 ããªãªã¼ã¹ããã¾ããã

æ¬è¨äºã¯ãåäººçã«æ°ã«ãªã£ãæ°ããæ©è½ãªã©ãåããã¦ã¿ããã¨ãç®çã¨ãã¦ãã¾ãã
å¤æ´åå®¹ã®è©³ç´°ã«ã¤ãã¦ã¯å¬å¼ã®ãªãªã¼ã¹ãç¢ºèªãã¦ãã ããã

- [Mattermost v5\.37 is now available \- Upgrade today](https://mattermost.com/blog/mattermost-v5-37/)
- [Mattermost Changelog](https://docs.mattermost.com/install/self-managed-changelog.html#release-v5-37-extended-support-release)

---

## [ã¢ããã°ã¬ã¼ãæã®æ³¨æäºé ](https://docs.mattermost.com/administration/changelog.html#important-upgrade-notes)

* æ¬ãã¼ã¸ã§ã³ãããè¿ä¿¡æ©è½ã®æãããã¿æ©è½ãå©ç¨å¯è½ã«ãªãã¾ããããã¾ã ãã¼ã¿çã®ãããã°ãæ®ã£ã¦ããå¯è½æ§ãããã[æ¢ç¥ã®åé¡](https://docs.mattermost.com/messaging/organizing-conversations.html#known-issues)ç­ãææ¡ããä¸ã§å©ç¨ãããã¨ãæ¨å¥¨ããã¦ãã¾ã
* æ¬ãã¼ã¸ã§ã³ãããEmoji v13.0ã«åºã¥ãçµµæå­ãå©ç¨ã§ããããã«ãªãã¾ãããæ°ããè¿½å ãããçµµæå­ã¨ååã®ã«ã¹ã¿ã çµµæå­ããã§ã«ç»é²ããã¦ããå ´åãã¢ãããã¼ãã«ããæ¢å­ã®ã«ã¹ã¿ã çµµæå­ã®åå®¹ãä¸æ¸ãããã¾ã
* Incident Collaborationãã©ã°ã¤ã³ãå¨ã¨ãã£ã·ã§ã³ã§å©ç¨å¯è½ã¨ããããã«ãææ°ã®Incident Collaborationãã©ã°ã¤ã³ã®æä½åä½ãã¼ã¸ã§ã³ã v5.37 ã«å¼ãä¸ãããã¦ãã¾ããIncident Collaborationãã©ã°ã¤ã³ãã¢ãããã¼ãããéã¯æ³¨æãã¦ãã ããã
* é·æãµãã¼ããã¼ã¸ã§ã³ã§ããMattermost v5.31ã¯2021/10/15ã«ãµãã¼ãçµäºã¨ãªãã¾ããv5.31ãå©ç¨ãã¦ããã¦ã¼ã¶ã¼ã¯ãv5.37ä»¥éã®ãã¼ã¸ã§ã³ã¸ã¢ããã°ã¬ã¼ãããå¿è¦ãããã¾ãã

---

åæ©è½ã®è¦åºãåã®è¨å·ã¯ããã®æ©è½ãå©ç¨å¯è½ãªã¨ãã£ã·ã§ã³ãè¡¨ãã¦ãã¾ãã

- `Cloud`: [Mattermost Cloud](https://mattermost.com/pricing-cloud/)
- `E20/E10`: [Enterprise E20/E10](https://mattermost.com/pricing-self-managed/)

è¦åºãã®åã«ä½ããªãå ´åãTeam Edition(OSS ç)ã§ãå©ç¨å¯è½ãªæ©è½ã§ãã

## Collapsed Reply Threads (ãã¼ã¿ç)

[Get early access to the Mattermost Collapsed Reply Threads beta](https://mattermost.com/blog/collapsed-reply-threads-beta/)

Mattermostã®[Feature Requestãã©ã¼ã©ã ã§ãæãäººæ°ã®ãã£ã](https://mattermost.uservoice.com/forums/306457-general/suggestions/19572469-make-threads-collapsible)è¿ä¿¡ã¹ã¬ããã®æãããã¿æ©è½(Collapsed Reply Threads)ããã¼ã¿çã¨ãã¦å©ç¨ã§ããããã«ãªãã¾ããã  
æ¬æ©è½ãæå¹ã«ãããã¨ã§ãæç¨¿ã¸ã®è¿ä¿¡ããã£ã³ãã«åã«è¡¨ç¤ºãããªããªãããã£ã³ãã«åã®ä¼è©±ããããã¯ãã¨ã«ææ¡ãããããªãã¾ãã

å®éã®åä½ã®æ§å­ã¯ã[å¬å¼ãã­ã¥ã¡ã³ã](https://docs.mattermost.com/messaging/organizing-conversations.html)ã§ç¢ºèªã§ãã¾ãã

![collapsed-threads-demo](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/collapsed-threads-demo.webp)
(ä¸è¨ç»åã¯[å¬å¼ãã­ã°](https://mattermost.com/blog/mattermost-v5-37/#collapsed)ãã)

---

æ¬æ©è½ãæå¹ã«ããã«ã¯ãã¾ãã**ã·ã¹ãã ã³ã³ã½ã¼ã« > å®é¨çæ©è½ > æ©è½ > è¿ä¿¡ã¹ã¬ããã®æãããã¿** ã **æå¹(ããã©ã«ãOff)** ã¨ãªã£ã¦ããå¿è¦ãããã¾ãã

![collapsed-threads-system-console](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/collapsed-threads-system-console.png)

ä¸è¨è¨­å®ãæå¹ã«ããä¸ã§ã**ã¢ã«ã¦ã³ãè¨­å® > è¡¨ç¤º > è¿ä¿¡ã¹ã¬ããã®æãããã¿ (ãã¼ã¿ç)** ã **On** ã«è¨­å®ãããã¨ã§ã¢ã«ã¦ã³ããã¨ã«æ©è½ãæå¹ã«ãªãã¾ãã

![collapsed-threads-account-setting](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/collapsed-threads-account-setting.png)

æ¬æ©è½ã¯ã¾ã ãã¼ã¿çã®æ®µéã®ãããæ¢ç¥ã®åé¡ãå«ããåé¡ãçºçããå¯è½æ§ãèæ®ãã¦å©ç¨ããæ¹ãè¯ãããã§ãã

https://docs.mattermost.com/messaging/organizing-conversations.html#known-issues

## Incident Collaborationã®æ¹å

ä»æã[Mattermost Incident Collaboration Plugin](https://github.com/mattermost/mattermost-plugin-incident-collaboration)ã®æ¹åãããã¾ãã

### å¨ã¨ãã£ã·ã§ã³ã§å©ç¨å¯è½ã«

ä»ã¾ã§Mattermost Cloudã¨Enterprise E20ãã©ã³ã§ããå©ç¨ã§ããªãã£ãIncident CollaborationãOSSçã®Team Edition(Enterprise E0)ãå«ãå¨ã¨ãã£ã·ã§ã³ã§å©ç¨å¯è½ã«ãªãã¾ããã
Team Editionã§ã¯Playbookã1ã¤ããä½æã§ããªããªã©å¶éã¯ããã¾ãããæ©è½ã®ä½¿ç¨æã®ç¢ºèªãªã©ã¯ã§ããããã«ãªãã¾ãã

https://mattermost.com/pricing-self-managed/

![incident-all-edition](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-all-edition.png)

Incident Collaborationãã©ã°ã¤ã³ã¯ã**ã¡ã¤ã³ã¡ãã¥ã¼ > ãã¼ã±ãããã¬ã¼ã¹** ããç°¡åã«ã¤ã³ã¹ãã¼ã«ã§ãã¾ãã

![incident-install](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-install.png)

ã¤ã³ã¹ãã¼ã«ãå®äºããã¨ãä¸è¨ç»åä¸­ã®`Install`ãã¿ã³ã`Configure`ãã¿ã³ã«å¤ããã®ã§ã`Configure`ãã¿ã³ãã¯ãªãã¯ãã¦è¨­å®ç»é¢ã¸ç§»åãã**ãã©ã°ã¤ã³ãæå¹ã«ãã** ã **æå¹** ã«ãããã¨ã§ãã©ã°ã¤ã³ãå©ç¨å¯è½ã«ãªãã¾ãã

![incident-system-console](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-system-console.png)

ãã©ã°ã¤ã³ãæå¹ã«ããã¨ **ã¡ã¤ã³ã¡ãã¥ã¼ > Incident Collaboration**ããIncident Collaborationãã©ã°ã¤ã³ãå©ç¨ãããã¨ãã§ããããã«ãªãã¾ãã

### ãã¬ã¤ããã¯ã­ã¼ã¯ã¼ãã®ç£è¦

ãã¬ã¤ããã¯ã«é¢ããã­ã¼ã¯ã¼ããè¨­å®ãããã¨ãã§ããããã«ãªããMattermostä¸ã§è¨­å®ãããã­ã¼ã¯ã¼ããå«ãã¡ãã»ã¼ã¸ãæç¨¿ãããéã«ãã¬ã¤ããã¯ã®éå§ãä¿ãã¡ãã»ã¼ã¸ãèªåã§è¡¨ç¤ºã§ããããã«ãªãã¾ããã

ã­ã¼ã¯ã¼ããè¨­å®ããã«ã¯ã**ã¡ã¤ã³ã¡ãã¥ã¼ > Incident Collaboration > Playbooksã¿ã**ããã­ã¼ã¯ã¼ããè¨­å®ããããã¬ã¤ããã¯ãé¸ã³ã**Edit > Actions > Prompt to run the playbook when a user posts a message > Containing any of these keywords**ã«ã­ã¼ã¯ã¼ããå¥åãã¾ãã

![incident-keyword-setting](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-keyword-setting.png)

è¨­å®ããã­ã¼ã¯ã¼ããå«ãæç¨¿ãè¡ãã¨ãPlaybook Botããã¬ã¤ããã¯ã®éå§ãä¿ãã¡ãã»ã¼ã¸ãæç¨¿ãã¾ãã

![incident-keyword-react](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-keyword-react.png)

`Yes, run playbook`ãé¸æããã¨ãä½æãããã¬ã¤ããã¯ã®åå®¹ãæå®ããã¢ã¼ãã«ãéãã¾ãã

![incident-keyword-modal](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-keyword-modal.png)

åå®¹ãå¥åãã`Start run`ãã¿ã³ãæ¼ãã¨ã¤ã³ã·ãã³ãä½æã®ãã£ããã¨ãªã£ãæç¨¿ã¨ã¨ãã«ãã¬ã¤ããã¯ãéå§ã§ãã¾ãã

![incident-keyword-creation](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-keyword-creation.png)

### (E10/E20/Cloud) Retrospectiveã¬ãã¼ã

ä½æãããã¬ã¤ããã¯ã«é¢ããRetrospective(æ¯ãè¿ã)ã¬ãã¼ããä½æã§ããããã«ãªãã¾ãããRetrospectiveã¬ãã¼ããPublishããã¨ããã£ã³ãã«ã«åå®¹ãæç¨¿ããã¾ãã

![incident-retro](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-retro.png)

Playbookã®è¨­å®ãããRetrospectiveã¬ãã¼ãã®ãã³ãã¬ã¼ãç­ãè¨­å®ã§ãã¾ãã

![incident-retro-template](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-retro-template.png)

### (E20/Clout) Playbookããã·ã¥ãã¼ã
ãã¬ã¤ããã¯ã®éå»ã®å®è¡çµæãææ¡ããããã®ããã·ã¥ãã¼ããè¡¨ç¤ºã§ããããã«ãªãã¾ãããã¤ã³ã·ãã³ãã®çºçé »åº¦ãã¤ã³ã·ãã³ãå¯¾å¿ã®åå èæ°ãå¯¾å¿ã«ããã£ãæéãªã©ãä¿¯ç°ãããã¨ã§ãã¤ã³ã·ãã³ãå¯¾å¿æ¹éã®æ¹åããªã½ã¼ã¹å²ãå½ã¦ã®è¦ç´ãç­ã«å½¹ç«ã¦ããã¨ãã§ãã¾ãã

![incident-dashboard](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/incident-dashboard.png)

## çµµæå­ã®ã¹ã­ã³ãã¼ã³é¸æ

Emoji 13.0ã«åºã¥ãçµµæå­ãå©ç¨ã§ããããã«ãªããçµµæå­ããã«ã¼ããçµµæå­ãé¸æããéã«ã¹ã­ã³ãã¼ã³ï¼èã®è²ï¼ãé¸æã§ããããã«ãªãã¾ããã

![emoji-skin-tone](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/emoji-skin-tone.webp)

(ç»åã¯[å¬å¼ãã­ã°](https://mattermost.com/blog/mattermost-v5-37/#emoji)ãã)

## Focalboard Plugin

[Focalboard](https://www.focalboard.com/)ã«ãæ¹åãããã¾ãã

ç¾å¨ãMattermost Pluginã¨ãã¦å©ç¨ã§ããFocalboardã®ææ°ãã¼ã¸ã§ã³ã¯ `v0.7.0` ã§ããã®ãã¼ã¸ã§ã³ã®ã¤ã³ã¹ãã¼ã«æ¹æ³ã«ã¤ãã¦ã¯ä»¥ä¸ã®å¬å¼ãã­ã¥ã¡ã³ããåç§ãã¦ãã ããããã
https://www.focalboard.com/download/mattermost/latest-plugin/

Focalboardèªä½ã¯åæ¥[`v0.8.0`](https://github.com/mattermost/focalboard/releases/tag/v0.8.0)ããªãªã¼ã¹ããã¦ãã¾ãã

### ãã­ããã£å¤ã«ãããã¼ãã«ã®ã°ã«ã¼ãã³ã°
ä½æããã¿ã¹ã¯ããã¼ãã«è¡¨ç¤ºããéã«ãã¿ã¹ã¯ã«è¨­å®ãããã­ããã£ã®å¤ãã¨ã«ã°ã«ã¼ãåãã¦è¡¨ç¤ºãããã¨ãã§ããããã«ãªãã¾ããã
ä»¥ä¸ã®ä¾ã§ã¯ã`Priority`ãã­ããã£ãã°ã«ã¼ãã³ã°ã®å¯¾è±¡ã¨ããå ´åã«ã**Priorityç¡ã**ã**High**ã**Medium**ã**Low** ã§ã°ã«ã¼ãåãããã¿ã¹ã¯ãè¡¨ç¤ºãã¦ãã¾ãã

![focalboard-grouping](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/focalboard-grouping.png)

### ãã­ããã£ã¿ã¤ãã®è¿½å 
ã¿ã¹ã¯ã«è¨­å®ãããã­ããã£ã®ã¿ã¤ãã«ããã«ãã»ã¬ã¯ããäººç©ããã§ãã¯ããã¯ã¹ãè¿½å ããã¾ããã

![focalboard-property-type](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/focalboard-property-type.png)

## ãã®ä»ã®å¤æ´

### ãã£ã³ãã«åæ¿ãã¤ã¢ã­ã°ã®æ¹å

Mattermostä¸ã§ `Ctrl(Cmd) + K` ãå¥åãããã¨ã§éã **ãã£ã³ãã«åæ¿** ãã¤ã¢ã­ã°ã«ãæè¿éãããã£ã³ãã«ãè¡¨ç¤ºãããããã«ãªãã¾ããã

![channel-switcher](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/channel-switcher.png)

### ã«ã¹ã¿ã ã¹ãã¼ã¿ã¹ã®æå¹æéè¨­å®

ã«ã¹ã¿ã ã¹ãã¼ã¿ã¹ãè¨­å®ããéã«ãã¹ãã¼ã¿ã¹ã®æå¹æéãè¨­å®ã§ããããã«ãªãã¾ããã

![custom-status](https://blog.kaakaa.dev/images/posts/mattermost/releases-5.37/custom-status.png)

### `platform` ãã¤ããªã®å»æ­¢

ä»¥åãMattermostãµã¼ãã¼ã¯ `mattermost/platform` ã¨ãããªãã¸ããªã§ç®¡çããã¦ãããå½æã®åæ®ã§Mattermostãµã¼ãã¼ç®¡çç¨ã®CLIãã¼ã«ã¨ãã¦`platform`ãã¤ããªã¨ãããã®ãæ®ã£ã¦ãã¾ãããä»åã®ãªãªã¼ã¹ã§ãã®`platform`ãã¤ããªã`--platform`ãªãã·ã§ã³ãå©ç¨ã§ããªããªãã¾ããã
ç¾å¨ã§ã¯ããªãã¸ããªã¯[`mattermost/mattermost-server`](https://github.com/mattermost/mattermost-server)ã«ç§»è¡ãããMattermostãµã¼ãã¼ç®¡çç¨ã®CLIãã¼ã«ã¨ãã¦`mattermost`ãã¤ããªãå©ç¨å¯è½ã«ãªã£ã¦ãããããä»å¾ã¯`mattermost`ãã¤ããªãä½¿ç¨ãããã¨ãæ¨å¥¨ããã¦ãã¾ãã

## ãã®ä»ã®ãããã¯

### Mattermost Dockathon

Mattermostã®å¬å¼ãã­ã¥ã¡ã³ããµã¤ãã§ãã [https://docs.mattermost.com](https://docs.mattermost.com) ã®æ§æãªã©ãæ¹åããä½æ¥­ãéå§ãã¦ããããã§ãããã«ä¼´ããä»æä¸æ¬ãã **Mattermost Docathon** ã¨ãããã­ã¥ã¡ã³ãæ¹åã®ããã®ã¤ãã³ããéå¬ããããã§ãã

[Join Us for our First Mattermost 'Docathon' and win swag and more\!](https://mattermost.com/blog/docathon-2021/)

ãã®ã¤ãã³ãæéä¸­ã®ã³ã³ããªãã¥ã¼ããå¤ãã£ãä¸ä½5åã«Mattermostã­ã´å¥ãAirPod Proããã¬ã¼ã³ããããããã§ãã1ä»¶ã®ã¿ã®ã³ã³ããªãã¥ã¼ãã§ãã°ããºãããããããã§ãã

### Mattermost v6.0

åæã®è¨äºã§å°ãè§¦ããMattermot v6.0ã«ã¤ãã¦ãå¬å¼ãã­ã°ã§ç´¹ä»ãããã¾ããã

[Looking ahead to Mattermost v6\.0, which ships Fall 2021](https://mattermost.com/blog/looking-forward-to-mattermost-v6-0/)

ãã¼ã¿çããGA(Generally Available)ã«ææ ¼äºå®ã®æ©è½ããå»æ­¢äºå®ã®æ©è½ãªã©ãç´¹ä»ããã¦ãã¾ãã

## ãããã«

æ¬¡ã®`v5.38`ã®ãªãªã¼ã¹ã¯ 2021/08/16(Mon)ãäºå®ãã¦ãã¾ãã

---

[Mattermost æ¥æ¬èª\(@mattermost_jp\)ãã \| Twitter](https://twitter.com/mattermost_jp?lang=ja) ã§ Mattermost ã«é¢ããæ¥æ¬èªã®æå ±ãæä¾ãã¦ãã¾ãã
