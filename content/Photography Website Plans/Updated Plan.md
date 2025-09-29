---
title: Updated plans to website
publish: "true"
tags:
  - feature
  - component
---
## Encrypting My Gallery (Soon™)

I’m cooking up something a little nerdy and a little theatrical for the gallery: **encrypted images that only get decrypted in memory** — right when they need to be shown. Translation: the files live encrypted on the server, and when someone views an image the site decrypts it **only in RAM**, serves it to the browser, and never writes the decrypted file to disk.

Why do this? Because encrypted images look rad (glitch art energy) and because I want to make casual downloads harder — not impossible, but harder. The idea is to treat the image like a secret you whisper into someone’s ear, not a poster you hand out.

What to expect:

- You’ll still be able to view the images normally in your browser.
    
- The site keeps the original encrypted file safe at rest.
    
- Decrypted data exists only briefly in memory during viewing, then it’s gone.
    
- It’s a blend of art, privacy, and a tiny bit of theater.
    

Sneak peek: I’m experimenting with ephemeral keys and in-memory decryption to balance user experience and performance. More details (and maybe a demo) coming soon. 👀

---

### Quick Tech Sidebar (For the curious)

Short, non-snoozy version of what “decrypt in RAM” actually means and what it doesn’t do:

- **What it does:** The server or client decrypts the image into memory (RAM) when needed and doesn’t save that plaintext file to disk. This reduces the risk of someone grabbing the original file from server storage or cache.
    
- **What it doesn’t do:** It can’t stop someone from taking a screenshot of what’s shown on their screen or a motivated user from capturing the decoded stream. Think of it as prevention for casual downloads, not a forensic-proof vault.
    
- **Real mitigations I’m testing:** ephemeral keys, short-lived sessions, streaming decryption, avoiding browser cache, and subtle UX nudges (like disabling easy “save image as” flows). Performance is the tricky part — gotta keep pages snappy.