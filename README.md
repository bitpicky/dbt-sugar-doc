# Introduction

{% hint style="warning" %}
 **Development of an MVP version is currently underway** and happening on [bitpicky/dbt-sugar](https://github.com/bitpicky/dbt-sugar). **We absolutely would welcome any help from feature requests, discussion in issues, help with database connector testing etc.**  
  
If you're more the chatty person you can also join the community on our [Discord](https://discord.gg/cQB49ejbCA).
{% endhint %}

## What is dbt-sugar?

dbt-sugar is a command line interface tool that allows users of [dbt](https://www.getdbt.com/) to perform tasks such as **adding column and model documentation** and **test enforcement** directly from the CLI across a variety of dbt projects.

### Overview of Features

#### Documentation Task

* document a model
* document columns of a model \(and propagate description across fields that are identically named, we call this "homogeneise",
* add common `dbt` builtin tests such as `unique` or `not_null`,
* add tags

