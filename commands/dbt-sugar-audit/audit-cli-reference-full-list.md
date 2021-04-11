# audit CLI reference \(full-list\)

### Model Name:

You can target a specific model by passing the `-m/--model` argument followed by the name of the dbt model that you want to audit like so: `dbt-sugar -m orders`

### Syrup

The `--syrup` argument controls the configuration you wish dbt-sugar to use \(see [how to configure your `sugar_config.yml`](../../installation-and-configuration/configuration/sugar-config.md)\). Normally, you will have specified a **default syrup** in your `sugar_config.yaml` but you may want to override it on-demand. To do so, you can pass `--syrup maple_syrup` on the `dbt-sugar audit` CLI call and dbt-sugar will use this config for that specific run instead of your default one. **Note: if you have not set up a default syrup, dbt-sugar will error and demand that you define one or pass it via the CLI for each use \(see** [**sugar\_config setup**](../../installation-and-configuration/configuration/sugar-config.md)**\)**.

