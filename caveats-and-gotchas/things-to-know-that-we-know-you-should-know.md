# Things to Know That We Know You Should Know

## Can dbt-sugar stop messing with other model columns' definitions?

Right now, no. We built dbt-sugar with a strong opinion that a column name should mean one thing and only one thing across all your dbt models. Achieving this opinion is particularly hard without a tool like dbt-sugar and that is why we built it. **However,** **we know this might not work for everyone \(especially users with more mature warehouses\), we plan to allow for this feature to be turned off in the `sugar_config.yml` in the next feature release of dbt sugar.**

## Can dbt-sugar manage more than one dbt projects at a time?

The short answer is yes! You can create as many [**syrups**](../installation-and-configuration/configuration/sugar-config.md) as you have dbt projects. However, since dbt-sugar attempts to homogenise column definitions across your entire dbt project and since you may manage multiple dbt project in your data-warehouse and **still** want to homogenise across multiple projects, the long answer is "Yes, but it will have limitations.

We plan to allow more than one dbt project per syrup \(scope\) in a future 

## Can dbt-sugar add ALL THE TESTS?

Currently no, dbt-sugar only supports dbt's builting **uniqueness and not null tests.** The reason for that is because we currently re-implemented those tests in our codebase \(I know, that's bad\). **We are hard at work and looking into a solution that will allow users to add any tests,** this means any of the tests that your dbt project has scope over \(builtins but also tests coming from macros etc\). It's not trivial, as it requires diving a bit into dbt's internals and potentially being bitten by the yet to be stable API --some discussion on this is [happening here](https://github.com/bitpicky/dbt-sugar/issues/65).

## Can the audit task report on models that are not yet documented?

Currently no, we designed the `audit` task to be fast and to cost no warehouse credits. This means, we derive coverage statistics only for those models that have at least a model-level description in any of the `schema.yml` files. However, we agree that this may not be useful when you are just getting started or when you have a lot of un-documented models. We will be working on a solution in the next feature release. To learn more about this you can check [issue \#210](https://github.com/bitpicky/dbt-sugar/issues/210).

