# Topic 5: CI/CD Integration (GitHub Actions & WDIO)
## Learning Objectives
By the end of this session, participants will be able to:
- Set up GitHub Actions workflows for WebdriverIO tests
- Configure headless browser testing in CI
- Upload artifacts (screenshots, reports) from CI runs

### Presentation Outline (15-20 minutes)

1.  **Introduction: Why CI/CD for Tests? (3 min)**
    - Automating test execution
    - Fast feedback on code changes
    - Shift-left testing

2.  **GitHub Actions Basics (5 min)**
    - Workflow files (.github/workflows/)
    - Triggers (push, PR, schedule)
    - Jobs, steps, runners
    - YAML syntax overview

3.  **WebdriverIO in GitHub Actions (7 min)**
    - Setting up Node.js environment
    - Running headless Chrome
    - Handling secrets (API keys, tokens)
    - Artifact upload for reports/screenshots

4.  **Demo: Complete CI Workflow (5 min)**
    - Create .github/workflows/ci.yml
    - Push and observe test execution
    - Review artifacts

5.  **Q&A / Wrap-Up (2 min)**

### Demo Script

**Step 1: Create Workflow File (2 min)**
Create `.github/workflows/ci.yml`:
```yaml
name: WebdriverIO CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20.x'
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Run WebdriverIO tests
      run: npm run wdio
    
    - name: Upload artifacts
      if: always()
      uses: actions/upload-artifact@v4
      with:
        name: test-results
        path: results/
```

**Step 2: Push and Verify (3 min)**
- Commit and push to GitHub
- Show Actions tab in GitHub UI
- Review test execution logs

### Resources
- GitHub Actions docs
- WebdriverIO CI/CD integration guide
