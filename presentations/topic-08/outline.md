# Topic 8: Mobile Web & Responsive Testing
## Learning Objectives
By the end of this session, participants will be able to:
- Test responsive designs at different viewports
- Use device emulation in WebdriverIO
- Understand mobile-specific testing considerations

### Presentation Outline (15-20 minutes)

1.  **Introduction: Mobile Testing (3 min)**
    - Mobile traffic statistics
    - Responsive vs adaptive design
    - Testing challenges on mobile

2.  **Viewport Emulation (5 min)**
    - Chrome DevTools device emulation
    - Setting viewport sizes in WebdriverIO
    - Common breakpoints (mobile, tablet, desktop)

3.  **Mobile-Specific Testing (5 min)**
    - Touch events vs click events
    - Mobile navigation patterns
    - Performance on mobile networks
    - Orientation testing

4.  **Demo: Responsive Test (5 min)**
    - Configure tests for multiple viewports
    - Run tests emulating mobile devices

5.  **Q&A / Wrap-Up (2 min)**

### Demo Script

**Step 1: Configure Viewport (2 min)**
```typescript
export const config = {
    capabilities: [{
        browserName: 'chrome',
        'goog:chromeOptions': {
            mobileEmulation: {
                deviceName: 'iPhone X'
            }
        }
    }]
};
```

**Step 2: Dynamic Viewport Change (2 min)**
```typescript
await browser.setWindowSize(375, 812); // iPhone X size
// Run mobile-specific assertions
await browser.setWindowSize(1920, 1080); // Desktop
```

**Step 3: Test Touch Events (1 min)**
```typescript
await browser.touchAction({
    action: 'tap',
    x: 100,
    y: 200
});
```

### Resources
- WebdriverIO mobile docs
- Chrome DevTools mobile emulation guide
