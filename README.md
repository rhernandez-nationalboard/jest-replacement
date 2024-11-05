# jest-replacement

### Frameworks we're looking at
- Jest
- Vitest & RTL (React Testing Library)
- Mocha
- Enzyme
- Jasmine

### Jest
- Total Tests Suites (2)
- Suite Runtime: 8.668
- Wizard.spec.tsx runtime: 5.722
- Language-select.spec.tsx: 6.242
- Replacing with ESBuild: 11 sec sometimes 4.533
- Replacing with SWC: 8s - 5s

### Vitest
- Total Tests Suites (2)
- Suite Runtime: 3.2s
- Pro
  - On save will only rerun affected test
  - wizard.spec.tsx runtime on save: 565ms

### Mocha
- Cons
  - Missing support for mocks. Supplemental libraries such as sinon do not seem to support mocking modules.

### Enzyme
- Not considering as it seems more like a replacement for React Testing Library

### Jasime
- Pros
  - Straightforward api
  - Assertion and mocking all included
- Cons
  - Challenging async testing