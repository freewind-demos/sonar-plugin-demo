Sonar Custom Plugin Demo
========================

TODO

Build the plugin
----------------

```
mvn package
```

Notice there will be a `jar` file generated, we will use it later.

Sonar Server
-------------

```
brew install sonar
```

Copy the generated plugin jar file to `<sonar-path>/libexec/extensions/plugins` and start the sonar server:

```
sonar start
```

Open <http://localhost:9000>

Configure
---------

Login to sonar server as `admin/admin`.

### Check if the plugin installed

`Administration` -> `System` -> `Update Center` -> `Installed`, see if the plugin is listed there

### Activate rules

The new custom rules not active by default.

We should search them and activate them one by one.

`Rules` -> `Search` -> keywords -> click on the results -> `Active`

**Question**: can we active all the rules of a plugin just one time?

Run on a project
----------------

Go to a maven project, e.g.:

1. <https://github.com/java-demos/mars-rover-with-if-else-demo>
2. <https://github.com/java-demos/mars-rover-with-enum-demo>

and run:

```
mvn sonar:sonar
```

It will scan the project and send the results to the sonar server.

Open <http://localhost:9000> you will see the results and check if the code breaks your rule.

Articles
--------

1. Writing custom Java plugins: <http://docs.sonarqube.org/display/PLUG/Writing+Custom+Java+Rules+101#WritingCustomJavaRules101-Testingacustomplugin>


