# doc CLI reference \(full-list\)

### Model Name

The `-m/--model` argument followed by the name of the model you want to document allows dbt-sugar to know which model you wish to document.

### Syrup

The `--syrup` argument controls the configuration you wish dbt-sugar to use \(see [how to configure your `sugar_config.yml`](../../installation-and-configuration/configuration/sugar-config.md)\). Normally, you will have specified a **default syrup** in your `sugar_config.yaml` but you may want to override it on-demand. To do so, you can pass `--syrup maple_syrup` on the `dbt-sugar doc` CLI call and dbt-sugar will use this config for that specific run instead of your default one. **Note: if you have not set up a default syrup, dbt-sugar will error and demand that you define one or pass it via the CLI for each use \(see** [**sugar\_config setup**](../../installation-and-configuration/configuration/sugar-config.md)**\)**.

### Target

dbt-sugar will **read the dbt profile associated with the dbt project you want it to manage.** It does so well, because you declare the profile dbt should use when running models for you in your dbt\_project.yml file \(for more info check the [dbt project documentation](https://docs.getdbt.com/reference/dbt_project.yml/)\). You also generally declare a **target** in your dbt\_profile.yml file \(see [dbt documentation](https://docs.getdbt.com/dbt-cli/configure-your-profile/)\). dbt-sugar figures it all out for you, how sweet is that?!

The `--target` argument allows you to override the default target that would normally be specified in [dbt's `profiles.yml`](https://docs.getdbt.com/dbt-cli/configure-your-profile/) for the profile associated with the [dbt\_project ](https://docs.getdbt.com/reference/dbt_project.yml/)associated to the model you want to document. **It is best practice to avoid using the \`--target\` argument unless you know what you are doing as it can lead to surprises \(ADD LINK TO CAVEATS AND GOTCHAS\).** It is best to set a `target:` variable in your `profiles.yml` for each dbt project you plan to have in dbt-sugar's scope \(see [dbt documentation](https://docs.getdbt.com/dbt-cli/configure-your-profile/)\).

### Schema

Although dbt-sugar will figure out the database schema in which your model lives from the [dbt\_profiles.yml](https://docs.getdbt.com/dbt-cli/configure-your-profile/) you may want to override it. If so, you can pass the `--schema` argument followed by the name of the schema you wish to target. **It is best not to use this argument unless you have a good reason to as dbt-sugar will make a database call to see if the table you want to document exists in your database's metadata.** If you point to a schema which does not contain that dbt model, dbt-sugar will error.

