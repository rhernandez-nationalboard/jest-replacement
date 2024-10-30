# jest-replacement

### Frameworks we're looking at
- Jest
- Vitest & RTL (React Testing Library)
- Mocha
- Jasmine

### Frameworks we're not considering
- Puppeteer
- Webdriver IO
- Cypress
- Story Book


Reason: These are higher level automation / ui testing frameworks. We're specifically looking to narrow down on the unit test side of things.


### Mocha
- Pros
  - Strong organization structure
  - Lightwieght and simple
- Cons
  - No support for assertions, spies, and mocks by default. Usually Chai is paired with Mocha to cover these missing aspects.
- Weaker documentation

### Jasime
- Pros
  - Straightforward api
  - Assertion and mocking all included
- Cons
  - Challenging async testing