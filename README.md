# Cypress Web Automation Framework

## Table of Contents

- [Prerequiesites](#prerequiesites)
- [Install Cypress](#install-cypress)
- [Run Cypress](#run-cypress)
- [Locators](#locators)

## Prerequiesites

Cypress requires `Nodejs` Run Time Environment. First we need to install `Nodejs`.

## Install Cypress

```js
npm i -D cypress
```

## Run Cypress

Through Cypress Application
```bash
npx open cypress
```

Thorugh Terminal
```bash
npx cypress run
```

## Locators

- There are 3 main locators. `get` `contains` `find`
- It's better to use test id `data-*` attributes (`data-test`, `data-cy`, `data-testid`)
- For static contents better to use contains method
```bash
// select by id
cy.get('#login-button')

// select by class
cy.get('.submit-button')

// select by tag name
cy.get('button')

// select by attribute
cy.get('[type="submit"]')
cy.get('[data-test="username"]') // Recommended practice

// select by text
cy.contains('Sign in')
cy.contains('button', 'Sign in') // More specific

// celecting by combination (attribute & class)
cy.get('input[name="email"].input-field')

// using parent-child relationships
cy.get('.form-container').find('input[name="email"]')

// using within() for scoped queries
cy.get('.login-form').within(() => {
  cy.get('input[name="username"]')
})

// using eq() to select indexed elements
cy.get('li').eq(2) // Selects the third list item

// using first(), last(), and nth-child()
cy.get('button').first() // Selects the first button
cy.get('button').last() // Selects the last button
cy.get('li:nth-child(2)') // Selects the second list item

// using filter() for specific element
cy.get('button').filter('.primary') // Selects buttons with class 'primary'

// using children() and parent()
cy.get('.list').children('li') // Gets all `li` inside `.list`
cy.get('li').parent() // Gets the parent of an `li`
```
