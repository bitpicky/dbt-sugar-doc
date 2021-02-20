---
description: Helps you document a model (both for model- and column-level descriptions)
---

# dbt-sugar doc

## dbt-sugar doc

### How to run dbt-sugar doc?

dbt-sugar guide you through the process of documenting a model by asking you a series of question such as whether you want to add a model-level description, column-level description, tests and tags. To start documenting a model, make sure you navigate to where your `sugar_config.yml` resides as dbt-sugar needs to run from your dbt-sugar's project location. To see how to configure the `sugar_config.yml` head over to the [Sugar Config](../../installation-and-configuration/configuration/sugar-config.md) page. 

* open a terminal window
* if you have installed dbt-sugar in a virtual environment, activate it
* navigate to your dbt-sugar folder \(the folder in which you have created your \`sugar\_config.yml\`. For example:

```
cd ~/dbt_sugar
```

Call `dbt-sugar doc` and pass the following arguments:

* `--model` the name of the dbt model you want to document
* optionally, you can pass a `--syrup` which is the name of the config \(See [Sugar Config](../../installation-and-configuration/configuration/sugar-config.md) for more information\) you want dbt-sugar to use \(syrups generally contain information such as which dbt\_projects are in scope and where these projects live on your machine\). 
* If you have configured a default syrup in your `sugar_config.yml` you do not have to pass a syrup to the CLI for every run!

```text
dbt-sugar doc --model my_sweet_model --syrup maple_syrup
```

