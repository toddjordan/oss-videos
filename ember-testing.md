# Intro to Ember Testing

### Overview

A three minute video that introduces Ember testing. We'll differentiate
the three types of tests in Ember, how they are different, and when to
use them.

### Viewer assumptions

Someone who has an written an Ember application, but not tests.
They're familiar with Ember basics: models, routes, components, and
computed properties.

### Questions we want to answer

* What is testing and how Ember makes testing easy
* The three types of testing Ember provides
* When to write unit tests
* When to write component integration tests
* When to write acceptance tests

### Transcript

Automated tests run your application logic and serve several functions:

- Verify functionality works as designed
- Reduce the need to manually verify that all functionality works
- Guard code against regressions

Ember provides out of the box automated test support.

There are three kinds of tests that Ember provides interfaces for: Acceptance, Integration, and Unit.  

Acceptance Tests verify the fully working web application. They start the Ember application, and simulate user iteractions such as visiting pages, filling out forms, and clicking buttons.  They make assertions based on content on the screen.  Use acceptance tests when you want to test screen transitions and interactions between different parts of the screen.

Examples include:
- Navigating to various pages within your application.
- Testing Page-Level Error handling, such as 404

To create an acceptance test, simply run `ember generate acceptance-test <route name>`, and ember will create an acceptance test that visits the page identified by the name you give the test.

Integration Tests verify groups of objects working together with the framework. They utilize Ember's container to load dependent objects, but do not run intializers or make use of the router.  Use integration tests when you want to test out component declarations via the template, or when you want to test other Ember classes, such as services, that have dependencies injected from the Ember container.

Component Integration tests are created automatically when you create a component.  Typing `ember generate component <component name>` will create a test file along with the component JavaScript and template.

Unit tests only run objects that you either instantiate or declare.  It does not use a fully hydrated container, and you cannot render components in template syntax like you can in integration tests.  Use unit tests when you want to test specific blocks of logic contained within a specific function or object in isolation.  

Unit tests are created automatically when you generate ember objects, such as route handlers, services, and utility classes.

Ember runs and reports test output using a framework called Testem.  Testem can execute tests in major browsers, as well as in a simulated browser called PhantomJS.  Out of the box, you can run your PhantomJS tests by typing `ember test`, or `ember t` for short.  Since PhantomJS doesn't run a classic browser, they can be run from the command line.  When you type `ember test --server`, or `ember t -s` for short, ember-cli will launch a browser window to run all browser tests, and listen for changes to Ember files.  Using this command, you can have tests executing while you develop your application.
