# doc CLI reference

### Model Name

The `-m/--model` argument followed by the name of the model you want to document allows dbt-sugar to know which model you wish to document.

### Syrup

The `--syrup` argument controls the configuration you wish dbt-sugar to use \(see how to configure your `sugar_config.yml`\). Normally, you will have specified a **default syrup** in your `sugar_config.yaml` but you may want to override it on-demand. To do so you can pass `--syrup maple_syrup` on the `dbt-sugar doc` CLI call and dbt-sugar will use this config for that specific call instead of your default one. **Note: if you have not set up a default syrup, dbt-sugar will error and demand that you define one or pass it via the CLI for each use \(see sugar\_config setup\)**.

### Target

The `--target` argument allows you to override the default target that would normally be specified in dbt's `profiles.yml` for the profile associated with the dbt\_project in which the model you wish to document resides. **You generally want to avoid using this as it may lead to surprising behaviour**. It is best to set a `target:` variable in your `profiles.yml` for each dbt project you plan to have in dbt-sugar's scope \(see [dbt documentation](https://docs.getdbt.com/dbt-cli/configure-your-profile/)\).

