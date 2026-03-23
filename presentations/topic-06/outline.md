# Topic 6: Cross-Browser Testing & Selenium Grid
## Learning Objectives
By the end of this session, participants will be able to:
- Configure WebdriverIO for multiple browsers
- Understand Selenium Grid architecture
- Integrate with cloud testing services (BrowserStack, Sauce Labs)

### Presentation Outline (15-20 minutes)

1.  **Introduction: Why Cross-Browser Testing? (3 min)**
    - Browser compatibility challenges
    - User experience consistency
    - Market share considerations

2.  **Multi-Browser Configuration (5 min)**
    - Setting up capabilities in wdio.conf.ts
    - Running tests across Chrome, Firefox, Safari, Edge
    - Headless vs headed execution

3.  **Selenium Grid & Cloud Services (7 min)**
    - On-premise Grid setup
    - Cloud providers (BrowserStack, Sauce Labs)
    - Cost/benefit analysis
    - Configuration for cloud services

4.  **Demo: Cross-Browser Test Run (5 min)**
    - Configure wdio for 2-3 browsers
    - Run simultaneously
    - Review results

5.  **Q&A / Wrap-Up (2 min)**

### Demo Script

**Step 1: Configure Capabilities (2 min)**
```typescript
export const config = {
    capabilities: [
        {
            browserName: 'chrome',
            'goog:chromeOptions': {
                args: ['--headless', '--window-size=1920,1080']
            }
        },
        {
            browserName: 'firefox',
            'moz:firefoxOptions': {
                args: ['-headless']
            }
        }
    ]
};
```

**Step 2: Run Cross-Browser Tests (3 min)**
```bash
npm run wdio
# Observe tests running in parallel on multiple browsers
```

### Resources
- WebdriverIO cloud services docs
- BrowserStack/Sauce Labs integration guides
