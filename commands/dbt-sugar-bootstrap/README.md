---
description: the easy way to kick strart all your docs!
---

# dbt-sugar bootstrap

{% hint style="success" %}
**New in version `0.1.0`**
{% endhint %}

## What is dbt-sugar bootstrap?

The `bootstrap` task is a way to quickly generate model descriptor files \(`schema.yml`\) for all the models of your dbt project. It can sometimes be daunting if you have not documented many models to get started. **No more excuses with the bootstrap task**. 

Running `bootstrap` is as easy as this:

```text
dbt-sugar bootstrap
```

## When to run the bootstrap task?

1. Anytime you want to kick start documentation for any of your models. 
2. Any time you want to make sure that the [audit task](../dbt-sugar-audit/) is 100% accurate. This is because the audit task does not check your database by default so it only knows about coverage for models which have no entry anywhere in `schema.yml` files \(see [audit task for more info](../dbt-sugar-audit/)\). 

## What does bootstrap really do?

1. First, dbt-sugar will collect all the information about any of the already documented models and keep this safely under its arm! 
2. dbt-sugar will ping your database to get the list of columns of all of your dbt models.
3. If a model's column is already documented, great, if a column is not documented, dbt-sugar will add an entry for it with a place holder that will reads _"No description for this column."_ If the column is already documented in another model \(see step 1\), dbt-sugar will populate it with this description \(this is because dbt-sugar is opinionated [see FAQ](../../caveats-and-gotchas/things-to-know-that-we-know-you-should-know.md#can-dbt-sugar-stop-messing-with-other-model-columns-definitions)\).
4. The same happens for models too. If a model is undocumented, dbt-sugar will add an entry for it \(with it's columns as described in the steps above\).



