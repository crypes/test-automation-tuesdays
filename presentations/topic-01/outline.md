# Topic 1: Foundations & Tooling
## WebdriverIO + Cucumber + TypeScript

### Learning Objectives
By the end of this session, participants will be able to:
- Set up a WebdriverIO project with Cucumber and TypeScript
- Write Gherkin feature files with proper syntax
- Implement step definitions using TypeScript
- Run BDD tests and interpret results

### Presentation Outline (15-20 minutes)

1. **Introduction to BDD (3 min)**
   - What is Behavior-Driven Development?
   - Benefits of BDD for teams
   - The triple-A: Arrange, Act, Assert vs Given, When, Then

2. **Tool Overview (3 min)**
   - WebdriverIO: The automation engine
   - Cucumber: The BDD framework
   - TypeScript: Type safety for maintainable tests
   - Why this combination works well

3. **Live Demo: Project Setup (8 min)**
   - Run `npm init wdio@latest .`
   - Select TypeScript option
   - Select Cucumber framework
   - Walk through generated files

4. **Writing Your First Feature (5 min)**
   - Gherkin syntax basics
   - Creating a .feature file
   - Mapping scenarios to step definitions

5. **Q&A and Next Steps (1 min)**
   - Preview of Topic 2 (Advanced BDD Patterns)

### Demo Script Steps (10-15 minutes)

**Prerequisites:**
- Node.js 18+ installed
- Chrome browser available

**Step 1: Initialize Project (2 min)**
```bash
mkdir wdio-cucumber-demo && cd wdio-cucumber-demo
npm init wdio@latest .
# Select: TypeScript, Cucumber, Chrome, add sample tests
```

**Step 2: Explore Generated Files (2 min)**
- Show wdio.conf.ts
- Show features/ folder structure
- Show step-definitions/

**Step 3: Run Sample Tests (2 min)**
```bash
npm run wdio
```
Show passing tests in terminal.

**Step 4: Create Custom Feature (5 min)**
Create `features/login.feature`:
```gherkin
Feature: Login Functionality
  Scenario: Successful login
    Given I am on the login page
    When I enter valid credentials
    Then I should see the welcome message
```

Create step definitions in `features/step-definitions/login.steps.ts`:
```typescript
import { Given, When, Then } from '@wdio/cucumber-framework';

Given(/^I am on the login page$/, async () => {
    await browser.url('https://the-internet.herokuapp.com/login');
});

When(/^I enter valid credentials$/, async () => {
    await $('#username').setValue('tomsmith');
    await $('#password').setValue('SuperSecretPassword!');
    await $('button[type="submit"]').click();
});

Then(/^I should see the welcome message$/, async () => {
    await expect($('#flash')).toHaveText(expect.stringContaining('You logged into a secure area!'));
});
```

**Step 5: Run and Debug (4 min)**
- Run the new test
- Show how to debug with `--inspect`
- Show generated cucumber report

### Resources for Demo
- Demo site: http://the-internet.herokuapp.com
- Test credentials: tomsmith / SuperSecretPassword!

### Common Pitfalls to Mention
- Forgetting `await` on async operations
- Using arrow functions with Cucumber World (context loss)
- Not matching step definition regex exactly

### Assessment Questions
1. What is the purpose of the Given step?
2. When should you use Scenario Outline vs Scenario?
3. How do you share data between steps?
