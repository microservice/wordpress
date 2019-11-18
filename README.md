# _Wordpress_ Open Microservice

> Allows interaction with the WordPress API

[![Open Microservice Specification Version](https://img.shields.io/badge/Open%20Microservice-1.0-477bf3.svg)](https://openmicroservices.org) [![Open Microservices Spectrum Chat](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/open-microservices) [![Open Microservices Code of Conduct](https://img.shields.io/badge/Contributor%20Covenant-v1.4%20adopted-ff69b4.svg)](https://github.com/oms-services/.github/blob/master/CODE_OF_CONDUCT.md) [![Open Microservices Commitzen](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com) 
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

## Introduction

This project is an example implementation of the [Open Microservice Specification](https://openmicroservices.org), a standard originally created at [Storyscript](https://storyscript.io) for building highly-portable "microservices" that expose the events, actions, and APIs inside containerized software.

## Getting Started

The `oms` command-line interface allows you to interact with Open Microservices. If you're interested in creating an Open Microservice the CLI also helps validate, test, and debug your `oms.yml` implementation!

See the [oms-cli](https://github.com/microservices/oms) project to learn more!

### Installation

```
npm install -g @microservices/oms
```

## Usage

### Open Microservices CLI Usage

Once you have the [oms-cli](https://github.com/microservices/oms) installed, you can run any of the following commands from within this project's root directory:

#### Actions

##### posts

> Find posts
##### Action Arguments

| Argument Name | Type | Required | Default | Description |
|:------------- |:---- |:-------- |:--------|:----------- |
| author | `int` | `false` | None | The id of the author |
| status | `string` | `false` | None | The status of the post |
| page | `int` | `false` | None | Pagination parameter |
| per_page | `int` | `false` | None | Number of posts per page |
| url | `string` | `true` | None | The Wordpress website url |
| username | `string` | `true` | None | WordPress username |
| password | `string` | `true` | None | WordPress password |

``` shell
oms run posts \ 
    -a author='*****' \ 
    -a status='*****' \ 
    -a page='*****' \ 
    -a per_page='*****' \ 
    -e url=$url \ 
    -e username=$username \ 
    -e password=$password
```

##### newpost

> Create a new post
##### Action Arguments

| Argument Name | Type | Required | Default | Description |
|:------------- |:---- |:-------- |:--------|:----------- |
| title | `string` | `true` | None | The title of the post |
| content | `string` | `true` | None | The content of the post |
| status | `string` | `false` | None | The status of the post |
| url | `string` | `true` | None | The Wordpress website url |
| username | `string` | `true` | None | WordPress username |
| password | `string` | `true` | None | WordPress password |

``` shell
oms run newpost \ 
    -a title='*****' \ 
    -a content='*****' \ 
    -a status='*****' \ 
    -e url=$url \ 
    -e username=$username \ 
    -e password=$password
```

##### updatepost

> Update a post
##### Action Arguments

| Argument Name | Type | Required | Default | Description |
|:------------- |:---- |:-------- |:--------|:----------- |
| id | `int` | `true` | None | The id of the post |
| title | `string` | `false` | None | The title of the post |
| content | `string` | `false` | None | The content of the post |
| status | `string` | `false` | None | The status of the post |
| url | `string` | `true` | None | The Wordpress website url |
| username | `string` | `true` | None | WordPress username |
| password | `string` | `true` | None | WordPress password |

``` shell
oms run updatepost \ 
    -a id='*****' \ 
    -a title='*****' \ 
    -a content='*****' \ 
    -a status='*****' \ 
    -e url=$url \ 
    -e username=$username \ 
    -e password=$password
```

##### deletepost

> Delete a post
##### Action Arguments

| Argument Name | Type | Required | Default | Description |
|:------------- |:---- |:-------- |:--------|:----------- |
| id | `int` | `true` | None | The id of the post |
| url | `string` | `true` | None | The Wordpress website url |
| username | `string` | `true` | None | WordPress username |
| password | `string` | `true` | None | WordPress password |

``` shell
oms run deletepost \ 
    -a id='*****' \ 
    -e url=$url \ 
    -e username=$username \ 
    -e password=$password
```

## Contributing

All suggestions in how to improve the specification and this guide are very welcome. Feel free share your thoughts in the Issue tracker, or even better, fork the repository to implement your own ideas and submit a pull request.

[![Edit wordpress on CodeSandbox](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/github/oms-services/wordpress)

This project is guided by [Contributor Covenant](https://github.com/oms-services/.github/blob/master/CODE_OF_CONDUCT.md). Please read out full [Contribution Guidelines](https://github.com/oms-services/.github/blob/master/CONTRIBUTING.md).

## Additional Resources

* [Install the CLI](https://github.com/microservices/oms) - The OMS CLI helps developers create, test, validate, and build microservices.
* [Example OMS Services](https://github.com/oms-services) - Examples of OMS-compliant services written in a variety of languages.
* [Example Language Implementations](https://github.com/microservices) - Find tooling & language implementations in Node, Python, Scala, Java, Clojure.
* [Storyscript Hub](https://hub.storyscript.io) - A public registry of OMS services.
* [Community Chat](https://spectrum.chat/open-microservices) - Have ideas? Questions? Join us on Spectrum.
