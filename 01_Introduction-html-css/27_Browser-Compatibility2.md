### Article Overview
- **Author**: Jeremy Keith  
- **Title**: Web browsers on iOS  
- **Core Thesis**: On iOS devices, Safari (powered by WebKit) is the **only real browser** users can install. Other "browsers" like Chrome and Firefox are just reskinned versions using Apple's WebKit engine due to App Store restrictions. This creates a browser engine monopoly that the author calls contradictory, hypocritical, and indefensible.

### Key Facts Table

| Aspect                        | Details on iOS                                                                 | Comparison to macOS / Other Platforms                  | Author's View |
|-------------------------------|--------------------------------------------------------------------------------|-------------------------------------------------------|---------------|
| **Available Browsers**       | Only Safari (WebKit) can be installed as a true browser                       | Multiple engines allowed (Chrome, Firefox, Edge, etc.) | Monopoly on iOS |
| **Third-party "Browsers"**   | Chrome, Firefox, Edge, etc. must use WebKit (they are skins of Safari)        | Can use their own rendering engines (Blink, Gecko)    | Not real alternatives |
| **App Store Rule**           | Guideline 2.5.6 requires all browsers to use WebKit                           | No such restriction                                   | Enforced exclusivity |
| **Apple's Justification**    | Safety and security                                                           | Same justification not applied to macOS               | Inconsistent / Hypocritical |
| **Impact on Users**          | No real choice of browser engine on iPhone or iPad                             | Full choice on Mac, Windows, Android                  | Limits freedom |
| **Impact on Web Developers** | iOS testing effectively means testing only Safari/WebKit                      | True cross-browser testing possible elsewhere         | Reduces competition & innovation |

### Main Arguments & Critique Table

| Point                          | Explanation                                                                 | Historical Parallel                          | Conclusion by Author |
|--------------------------------|-----------------------------------------------------------------------------|----------------------------------------------|----------------------|
| **Browser Monopoly**          | All iOS browsers share the same rendering engine (WebKit)                   | Microsoft's bundling of Internet Explorer in the 1990s | Anti-competitive |
| **OS Convergence**            | iOS and macOS are becoming more similar in features and form factor         | Future risk: Apple may lock down macOS too   | Dangerous precedent |
| **Hypocrisy**                 | Safety/security argument used only for iOS, ignored on macOS                | Microsoft was fined for similar behavior     | Indefensible |
| **Developer Awareness**       | Many experienced devs know this; newer devs may be surprised                | —                                            | Should be common knowledge |
| **User Experience**           | Users buying Apple devices (iPhone, iPad, Mac) have choice on only one     | Not tolerated on desktops                    | Contradictory |

### Important Quotes
- "Safari is the only browser that can be installed on iOS devices — not just the one that ships with them, but the only one that can be installed."
- "You buy a computing device from Apple. It might be a MacBook. It might be an iPad. It might be an iPhone. But you can only install your choice of web browser on one of those devices. For now."
- "It is contradictory. It is hypocritical. It is indefensible."

### Implications for Web Developers
- **Testing**: On iOS, you're essentially testing Safari only — true multi-engine testing isn't possible.
- **Web Standards**: Reduced competition may slow improvements and innovation in WebKit.
- **Broader Web**: Highlights issues around openness, user choice, and the "Web is for Everyone" principle when one company controls mobile browser engines.