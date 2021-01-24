---
description: Helps you document a model (both for model- and column-level descriptions)
---

# dbt-sugar doc

## dbt-sugar doc

### How to run dbt-sugar doc?

dbt-sugar guide you through the process of documenting a model by asking you a series of question such as whether you want to add a model-level description, column-level description, tests and tags. To start documenting a model, make sure you navigate to where your `sugar_config.yml` resides \(ADD LINK TO CONFIG PAGE WHEN ITS AVAILABLE\).

* open a terminal window
* if you have installed dbt-sugar in a virtual environment, activate it
* navigate to your dbt-sugar folder \(the folder in which you have created your \`sugar\_config.yml\`. For example:

```
cd ~/dbt_sugar
```

Call `dbt-sugar doc` and pass the following arguments:

* `--model` the name of the dbt model you want to document
* optionally, you can pass a `--syrup` which is the name of the config \(ADD LINK TO CONFIGURING RECIPIES WHEN WRITTEN\) you want dbt-sugar to use \(syrups generally contain information such as which dbt\_projects are in scope and where these projects live on your machine\).

```text
dbt-sugar doc --model my_sweet_model --syrup default
```



