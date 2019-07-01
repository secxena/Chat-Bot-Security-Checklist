<h1 align="center">
<br>
  <img src="data/cc.png" alt="Chat-Bot-Security-Checklist" width="270">
  <br>
    <br>
  Chat-bot Security Checklist
  <br>
</h1>

<h4 align="center">The Chat-Bot Security Checklist is an exhaustive list of all elements you need to have before launching your chat-bot  to production.</h4>

<p align="center">
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="PRs Welcome">
  </a>
    <a href="https://github.com">
    <img src="https://img.shields.io/github/contributors/apoorvrajsaxena/Chat-Bot-Security-Checklist.svg" alt="Contributors">
  </a>
      <a href="https://github.com/">
    <img src="https://img.shields.io/badge/Chat_Bot_Security_Checklist-followed-brightgreen.svg?style=flat-square" alt="Chat‑bot_Checklist followed">
</a>
    <a href="https://creativecommons.org/publicdomain/zero/1.0/">
    <img src="https://img.shields.io/badge/license-CC0-green.svg?style=flat-square" alt="CC0">
  </a>
</p>

<p align="center">
  <a href="#how-to-use">How To Use</a> • <a href="#contributing">Contributing</a> • <a href="">Website</a> • <a href="https://www.producthunt.com/">Product Hunt</a>
</p>

It is based on Chat-bot developers' years of experience, with the additions coming from some other open-source checklists.

## Table of Contents

1. **[CLient Side Security](#Client-Security)**
    1. [OS Platform](#OS-Platforms)
    2. [Messaging Platforms](#Messaging-platforms)
    3. [Custom-Website Platform](#Custom-Web-Platform)
2. **[NLP Technology Secuirty](#NLP-security)**
    1. [Intent Classifiers](#Intent-Classifiers)
    2. [Dialog Mangement System](#Dialog-Management-System)
    3. [Conversation Records](#Conversation-Records)
3. **[Backend + Infrastructure](#Back-end-Infrastructure)**
    1. [OWASP Top 10](#OWASP-Top-10)
    2. [Licensing](#Licesnsing)

---

## How to use?

All items in the **Chat-bot Security Checklist** are must for majority of the projects.exception can only be made for regulatory reason. you can use this checklist to implement three layered defense to your Chat-bot product. Each point in the list is marked as low medium and high.

* ![Low][low_img] means that the item is **recommended** but can be omitted in some particular situations.
* ![Medium][medium_img] means that the item is **highly recommended** and can eventually be omitted in some really particular cases. Some elements, if omitted, can have bad repercussions.
* ![High][high_img] means that the item **can't be omitted** by any reason. You may leave a huge vulnerability open to the world. The testing priority needs to be on these elements first.


---

Before diving right into the checklist, let's ask a question why Chat-bot needs security
and what's different with them? And the answer is, most of the components are same like your Infrastructure, Back-end, your middleware and dev-ops practices all are same, only thing that differs is Language and conversational components of the chat-bot which isn't common in mainstream applications that where the focus of this checklist.

# Client-Security

You might need to deploy your chat-bot to a social platform or you might need a dedicated mobile app or a web SDK that can be used to use your chat-bot in other businesses. In any case, When you are running your code in a machine you have no control, you need to take some measures to insure few things.
Here's some pointers according to their platforms that you need to think about when deploying your Chat-bot -

## OS-Platforms
* [ ] **Data:** ![Medium][medium_img] You need to make sure that your customers Data is not available to other apps. and you should also encrypt the data so that it can't be stolen even under physical access.
  * 📖 [Securing Data on Android](https://www.futurelearn.com/courses/secure-android-app-development/0/steps/21592)
  * 📖 [Securing Data on iOS](https://medium.com/ios-os-x-development/securing-user-data-with-keychain-for-ios-e720e0f9a8e2)


* [ ] **Authentication:**![High][high_img]
 There are two type of authentication that You might need.
 * You want to make sure that No, Non-user can access your platform.
    * 📖 [Here's how you can choose good authentication ](https://www.freecodecamp.org/news/evaluating-authentication-as-a-service-providers-6903895a8450/)
  *  When your users device requesting private information you must ensure that your user is requesting the information instead of malicious user with device access.
  You can do this using FaceID and TouchID they are becoming more and more common with new smartphones.
    * 📖 [biometric authentication on Android App](https://proandroiddev.com/5-steps-to-implement-biometric-authentication-in-android-dbeb825aeee8)

    * 📖 [biometric authentication on iOS App](https://medium.com/we-talk-it/face-id-and-touch-id-biometric-authentication-ca1678fc338)
    * 📖 [biometric authentication on Cross Platform App](https://medium.com/react-native-training/integrate-touch-id-and-face-id-to-your-react-native-app-707e7db17edc)
  * Developing in-house authentication Management system can be vulnerable at times considering you haven't got it pentested yet.So if possible for your organization you can go for a AaaS Provider.
    * 📖 [Auth as a service providers](https://www.freecodecamp.org/news/evaluating-authentication-as-a-service-providers-6903895a8450/)  
* [ ] **Hard-coding:**![High][high_img] Make sure you are not storing your secrets on your code.
Any API access token with admin privilege should not be hard-coded in your App.
  * 📖 [Hard-coded credentials case study](https://www.zdnet.com/article/tens-of-thousands-of-cars-left-exposed-to-thieves-due-to-a-hardcoded-password/)


## Messaging-platforms

* [ ] **Channel Authorization:**  ![Medium][medium_img] Chat-bots have this unqiue feature of being available to everyone by deploying the bot on multiple channel like Skype for Business, Microsoft Teams, Facebook, Slack etc. So If you are planning to deploy your chat-bot in any of the platform your organization must make sure to restrict features which shouldn't be available to all.

* [ ] **Channel Authentication:** ![Low][low_img] You should check if your customer is using your platform instead of someone else from his/her account.you can do this using 2-Factor Authentication like OTP SMS or Email,Google Authenticator.

* [ ] **regulatory Data Protection:**![High][high_img] Every regulation restrict customer data ownership to yourself so if you are asking PII(Personally identifiable information) or ePHI(Electronic protected health information) from your customer you must restrict that particular intent to your native channel only.
Because you don't have custom SLAs to any of these channel provider, you can't solely own the private data it'll be shared with them.

## Custom-Web-Platform
* [ ] **Front-end Security**![High][high_img]
If you are providing a chat-bot as a service company than you must think of secure deploybility for that reason you might sdk for platform like web,android,iOS etc.  than you need your Client side security + All the things that needed to secure you sdk.

* [ ] **Authentication:**![High][high_img] You must you if your customer is using your platform.


# NLP-Security

## Intent-Classifiers
* [ ] **Intent Segregation:**![High][high_img] You must you if your customer is using your platform.

* [ ] **Permissioned Intent:**![High][high_img] You must you if your customer is using your platform.



## Dialog-Management-System
* [ ] **Authorization:** ![medium][medium_img] You must check who is the user if your customer is using your platform.
Role Management

  * Customer
    * Unauthenticated customer
    * Authenticated Non-Premium customer
    * Premium customer

If your chat-bot also have functionality for Internal users then you should have these roles.

* Internal Roles
  * Developer/tester
  * Admin


* [ ] **Language generation Constraint:**![medium][medium_img] you should not directly use your customer input.

## Conversation-Records
* [ ] **Life Cycle Management:**![High][high_img] You must you if your customer is using your platform.
* [ ] **PII and PHI Redaction:**![High][high_img] You must you if your customer is using your platform.
* [ ] **Administration:** [High][high_img] You must you if your customer is using your platform.


# Back-end-Infrastructure

## OWASP-TOP-10
* [ ] **Injection:**
* [ ] **Broken Authentication:**
* [ ] **Sensitive data exposure:**
* [ ] **XML External Entities:**
* [ ] **Broken Access control:**
* [ ] **Security misconfigurations:**
* [ ] **Cross Site Scripting (XSS):**
* [ ] **Insecure Deserialization:**
* [ ] **vulnerabilities:**
* [ ] **Insufficient logging and monitoring:**

## Licensing
* [ ] **SLAs:** Check


---

## Chat-bot Security Checklist Badge

If you want to show you are following the rules of the Chat-Bot Checklist, put this badge on your README file!

➔ [![Chat_Bot_Security_Checklist followed](https://img.shields.io/badge/Chat_Bot_Security_Checklist-followed-brightgreen.svg)](https://github.com/apoorvrajsaxena/Chat-Bot-Security-Checklist)

```md
[![Chat‑Bot_Checklist followed](https://img.shields.io/badge/Chat_Bot_Security_Checklist-followed-brightgreen.svg)](https://github.com/apoorvrajsaxena/Chat-Bot-Security-Checklist)
```

**[⬆ back to top](#table-of-contents)**

---

## Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **Chat-Bot Security Checklist** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file.

#### 2. `develop`

This branch will be used to make some significant changes to the structure, content if needed. It is preferable to use the master branch to fix small errors or add a new item.

## Support

If you have any question or suggestion, don't hesitate to use Twitter:

* [Twitter](https://twitter.com/secxena)

## Author

**[Apoorv Raj Saxena](https://github.com/apoorvrajsaxena)**

## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](.github/CONTRIBUTING.md).
<a href="https://github.com/apoorvrajsaxena/Chat-Bot-Security-Checklist/graphs/contributors"><img src="https://opencollective.com/Chat-Bot-Security-Checklist/contributors.svg?width=890" /></a>


## Backers

🙏 [[Become a backer](https://opencollective.com/Chat-Bot-Security-Checklist#backer)]


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/Chat-Bot-Security-Checklist#sponsor)]

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ back to top](#table-of-contents)**

[low_img]: data/low.svg
[medium_img]: data/medium.svg
[high_img]: data/high.svg
