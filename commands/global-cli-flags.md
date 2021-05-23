# Global CLI Flags

## Version

The `--version` flag returns information about the currently installed version of dbt-sugar.

```bash
➜ dbt-sugar --version
  Installed dbt-sugar version: 0.1.0-a.4
         Latest dbt-sugar version: 0.0.0
```

## Config Path

You can override the default location where dbt-sugar expects your `sugar_config.yml` by passing a path after the `--config-path` CLI argument like so:

```bash
dbt-sugar <command> --config-path path/to/my/sugar_config.yml
```

## Profiles Path

You can override the default location where dbt-sugar expects your dbt `profiles.yml` by passing a path to the `--profiles-path` CLI argument like so:

```bash
dbt-sugar <command> --profiles-dir path/to/my/dbt/profiles.yml
```

## Log Level & Verbosity

You can choose the level of verbosity of the app in the following ways:

* `--log-level debug` will set dbt-sugar's logger to throw `debug` level messages.
* `-vv/--verbose` will make sure that error traceback go back to a lot more levels before the error. If you do not understand the default non-verbose tracebacks or if they do not give you enough information about the bug/error, then `--verbose` is definitely an option to try.



