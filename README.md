# ngx-utility-app

The all you wanted in your angular application is here in this library

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.0.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).


# ngx-utility [![npm version](https://badge.fury.io/js/ngx-utility.svg)](https://badge.fury.io/js/ngx-utility)

The all you wanted directives, pipes and services in your angular application is here in this library.

Simple example using ngx-utility: https://mauliksojitra.github.io/ngx-utility

## Table of Contents
* [Installation](#installation)
* [Usage](#usage)
* [API](#api)

## Installation

First you need to install the npm module:

```sh
npm install ngx-utility --save
```
---
## Usage

#### 1. Import the `AngularUtilityModule`:

Finally, you can use ngx-translate in your Angular project. You have to import `AngularUtilityModule.forRoot()` in the root NgModule of your application.

The [`forRoot`](https://angular.io/docs/ts/latest/guide/ngmodule.html#!#core-for-root) static method is a convention that provides and configures services at the same time.
Make sure you only call this method in the root module of your application, most of the time called `AppModule`.


```ts
import {BrowserModule} from '@angular/platform-browser';
import {NgModule} from '@angular/core';
import {AngularUtilityModule} from 'ngx-utility/core';

@NgModule({
    imports: [
        BrowserModule,
        AngularUtilityModule.forRoot()
    ],
    bootstrap: [AppComponent]
})
export class AppModule { }
```

##### SharedModule

If you use a [`SharedModule`](https://angular.io/docs/ts/latest/guide/ngmodule.html#!#shared-modules) that you import in multiple other feature modules,
you can export the `AngularUtilityModule` to make sure you don't have to import it in every module.

```ts
@NgModule({
    exports: [
        CommonModule,
        AngularUtilityModule
    ]
})
export class SharedModule { }
```

> Note: Never call a `forRoot` static method in the `SharedModule`. You might end up with different instances of the service in your injector tree. But you can use `forChild` if necessary.

## API

##### Use the pipe or the directive:

This is how you do it with the **pipe**:

- `join`

And in your component define `param` like this:

```ts
param = [{value: 'one'},{value: 'two'},{value: 'three'}];
```

```html
<div>{{ param | join:'value' }}</div>
```

- `capitalize`

And in your component define `param` like this:

If we want first 2 laters in capital that time add one extra parameter

```ts
param = {value: 'one'};
```

```html
<div>{{ param.value | join }}</div>
<div>{{ 'name' | join }}</div>

<div>{{ param.value | join : 2 }}</div>
<div>{{ 'name' | join : 2 }}</div>
```


This is how you use the **directive**:

- `OnlyNumber`

Params
    `OnlyNumber` : to use this directive add 'true' and for stop use 'false' 
    `allowKeyList` : if you want to allow some value then add ['keycode'] 

```html
<input type="text" OnlyNumber="true" [allowKeyList]="[109, 102]">
```


- `NumberRange`

Params
    `NumberRange` : to use this directive add 'true' and for stop use 'false' 
    `min` : set minimum number  
    `max` : set maximum number

```html
<input type="number" NumberRange="true" [min]="-5" [max]="100">
```