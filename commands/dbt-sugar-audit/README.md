# dbt-sugar audit

## dbt-sugar audit

The `audit` task allows you to get quick statistics about the documentation and testing coverage of your dbt project. It comes in two flavours: project- and model-level. For both flavours we report **documentation coverage** \(the percentage of documented vs undocumented columns\) and **test coverage** \(the percentage of columns with _at least one test_ on them\). At the project-level we roll up those proportions across models to give you a summary of the state of the project and you can dig in more by running `dbt-sugar audit`  on a specific model.

{% hint style="danger" %}
the `audit` task can currently only report on models that have at least a model-level description or entry in model descriptor files \(`schema.yml`\). It is a known limitation and we will work on a more thorough approach in the next feature release \(see [issue \#210](https://github.com/bitpicky/dbt-sugar/issues/210)\)
{% endhint %}

### project-level audit

You can get a high-level overview of your dbt project's documentation and test coverage. You can get it by running the following command:

```text
dbt-sugar audit --syrup jaffle_shop
```

and you should get a report that looks something like this:

```text
       ____    __
  ____/ / /_  / /_      _______  ______ _____ ______
 / __  / __ \/ __/_____/ ___/ / / / __ `/ __ `/ ___/
/ /_/ / /_/ / /_/_____(__  ) /_/ / /_/ / /_/ / /
\__,_/_.___/\__/     /____/\__,_/\__, /\__,_/_/
                                /____/

Getting sweetness out of the cupboard 🍬!

[04/11/21 21:48:26] Running audit of dbt project in ./test_dbt_project/jaffle_shop.

    Documentation Coverage

     Model Name   % coverage
 ────────────────────────────
      customers         40.0
         orders         55.6
  stg_customers        100.0
     stg_orders        100.0
   stg_payments          0.0

          Total         40.0

        Test Coverage

     Model Name   % coverage
 ────────────────────────────
      customers         20.0
         orders         33.3
  stg_customers        100.0
     stg_orders        100.0
   stg_payments        100.0

          Total         47.4
```

### model-level audit

While the project-level audit is a quick way to get an overview of the documentation and test coverage quality of your models you may want to drill down on one specific model to get an output **at the column level**. To do so, you run the following command:

```text
dbt-sugar audit -m orders --syrup jaffle_shop
```

and you will get a report that looks like this:

```text
       ____    __
  ____/ / /_  / /_      _______  ______ _____ ______
 / __  / __ \/ __/_____/ ___/ / / / __ `/ __ `/ ___/
/ /_/ / /_/ / /_/_____(__  ) /_/ / /_/ / /_/ / /
\__,_/_.___/\__/     /____/\__,_/\__, /\__,_/_/
                                /____/

Getting sweetness out of the cupboard 🍬!

[04/11/21 21:51:25] Running audit of model orders.

       Documentation Coverage

  Undocumented Columns   % coverage
 ───────────────────────────────────
  bank_transfer_amount
         coupon_amount
    credit_card_amount
      gift_card_amount

                 Total         55.6

            Test Coverage

      Untested Columns   % coverage
 ───────────────────────────────────
  bank_transfer_amount
         coupon_amount
    credit_card_amount
           customer_id
      gift_card_amount
            order_date

                 Total         33.3
```



