---
description: where dbt-sugar's sweetness lives.
---

# Sugar Config

The `sugar_config.yml` contains all the information necessary for dbt-sugar to know how to deal with your dbt models as well as setting up behavioural settings for dbt-sugar. 

The `sugar_config.yml` holds what we call "syrups".

## What are syrups?

Syrups are dbt-sugars configurations profiles. You may only have one if you maintain only one dbt project, but you may have as many as you need if your setup interacts with different dbt projects for which you want different sets of controls.

The `sugar_config.yml` looks something like this:

{% tabs %}
{% tab title="sugar\_config.yml" %}
```yaml
defaults:
  syrup: syrup_1
  target: dev
syrups:
  - name: syrup_1
    dbt_projects:
      - name: dbt_sugar_test
        path: "./tests/test_dbt_project/dbt_sugar_test"
        excluded_tables:
          - table_a
        excluded_folders:
          - folder_a
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
For now, dbt-sugar can only manage one dbt project per syrup. It is a known limitation and we plan to allow support for multiple projects \(hence the use of plural\) in a later feature release. Stay tuned!
{% endhint %}

### defaults

The defaults section allows you to declare which of the syrups you would like dbt-sugar to use as default so that you do not have to pass the `--syrup` CLI argument for the run type that you plan to execute most of the time.

### syrups

Syrups are a list of entries made of a **name** which is how you will refer to the syrup you want dbt-sugar to use at runtime. Each **syrup** entry is made of a list of **dbt\_projects**. This is how you tell dbt-sugar where to find the dbt project you want it to sugar coat. It **must contain** the `name` of your dbt  project and a `path` to that dbt project. It can also contain a series of other settings, which are listed below:

#### excluded\_tables:

You may have a use case where you do not want dbt-sugar to consider some of your dbt models \(tables\). You can simply list those and dbt-sugar will ignore everything about it. For example, it will not attempt to document it, nor will it look up its definitions, tests, and tags in the case where you want to homogenise column definitions across all your dbt models.

#### excluded\_folders:

A bit like `excluded_tables` but to exclude entire folders.

