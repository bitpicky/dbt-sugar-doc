# Installation & Update

## Get dbt-sugar!

{% hint style="info" %}
**Python 3.6 and up**

dbt-sugar is written in python and is compatible with versions of python 3.6 and up.
{% endhint %}

### Install Using Pipx \(strongly recommended\)

`pipx` is a \(fairly new\) way to install python packages and apps **globally** while keeping each of them in their separate virtual environments under the hood. Just like `brew` it will allow you to access dbt-sugar globally, but **unlike \`brew\` it will keep dbt-sugar in its own virtual environent and prevent it from being bullied by other apps you may have set up globally**. Best of both worlds!

1. If you do not have `pipx` on your machine, install it with brew first by doing: `brew install pipx`.
2. Once `pipx` is set on your machine you can use it to install dbt-sugar in a very similar way to how you would generally install python packages with the well known `pip` manager.

```text
pipx install dbt-sugar
dbt-sugar --version
```

If dbt-sugar installed properly running the second command provided in the snippet above should print the version of dbt-sugar that is currently installed on your machine. **You're all set! On to configuring dbt-sugar!**

### Installing dbt-sugar in a virtual environment of your choice

If `pipx` isn't for you and you prefer to manage your virtual environment yourself, the following method is also perfectly fine although it requires you and your team to know about managing virtual environments.

1. dbt-sugar is distributed via the [Python Index PyPI](https://pypi.org/).
2. we **strongly** recommend that you set up and run dbt-sugar from a **virtual environment** as dbt-sugar has a few dependencies and things could get messy real quick if you install it in your global python. If you are not too familiar with how to set up virtual environments, here is a [fantastic resource from Real Python](https://realpython.com/python-virtual-environments-a-primer/) on how to set up and manage python virtual environments that we recommend to read before going down this path.
3. create your virtual environment with your tool of choice,
4. activate it and run the following commands to install dbt-sugar:

```text
pip install dbt-sugar
dbt-sugar --version
```

If all went according to plan, the second command in the snippet above should make dbt-sugar print it's version. **You're all set! Now get configuring!**

