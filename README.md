# Introduction

{% hint style="warning" %}
 **dbt-sugar is very much under active development. Development happens on** [bitpicky/dbt-sugar](https://github.com/bitpicky/dbt-sugar). **We absolutely would welcome any help from feature requests, discussion in issues, help with database connector testing to actual code changes! 🤗.**  
  
Join the community on our [Discord](https://discord.com/invite/cQB49ejbCA).
{% endhint %}

## What is dbt-sugar?

dbt-sugar is a command-line interface tool that allows users of [dbt](https://www.getdbt.com/) to perform tasks such as **adding column and model documentation, enforce test coverage and tags \(more to come\)** directly from the CLI across a variety of dbt projects. Check out the [project roadmap ](https://github.com/bitpicky/dbt-sugar/blob/main/ROADMAP.md)if you want to know what is coming!

### Here's the tool in action

![dbt-sugar in action](.gitbook/assets/document_fct_orders.gif)

### Overview of Current Features

#### Documentation Task

* document a model's description
* document columns of a model \(and propagate description across fields that are identically named, we call this "homogenise" and it is the main reason behind why we built dbt-sugar,
* add common `dbt` builtin tests such as `unique` or `not_null`,
* add tags

#### Audit Task

* get a model or project level summary of the number of columns that are documented and tested.

### What has recently changed?

We maintain and keep our CHANGELOG up to date on the [GitHub repository](https://github.com/bitpicky/dbt-sugar/). Head over [there](https://github.com/bitpicky/dbt-sugar/blob/main/CHANGELOG.md) if you want to see all the changes since the last release.

