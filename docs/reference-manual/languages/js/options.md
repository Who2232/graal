
## Graal.js Options

On the command line, `--js.<property>=<value>` sets options that tune language features and extensions.
The following options are currently supported:
   * `--js.annex-b`: enables ECMAScript Annex B web compatibility features. Boolean value, default is `true`.
   * `--js.array-sort-inherited`: defines whether `Array.protoype.sort` should sort inherited keys (implementation-defined behavior). Boolean value, default is `true`.
   * `--js.atomics`: enables *ES2017 Atomics*. Boolean value, default is `true`.
   * `--js.ecmascript-version`: emulates a specific ECMAScript version. Integer value (`5`-`9`), default is the latest version.
   * `--js.intl-402`: enables ECMAScript Internationalization API. Boolean value, default is `false`.
   * `--js.regexp-static-result`: provides static `RegExp` properties containing results of the last successful match, e.g.: `RegExp.$1` (legacy). Boolean value, default is `true`.
   * `--js.shared-array-buffer`: enables *ES2017 SharedArrayBuffer*. Boolean value, default is `false`.
   * `--js.strict`: enables strict mode for all scripts. Boolean value, default is `false`.
   * `--js.timezone`: sets the local time zone. String value, default is the system default.
   * `--js.v8-compatibility-mode`: provides better compatibility with Google's V8 engine. Boolean value, default is `false`.
Use `--help:languages` to see the full list of available options.

See the [Polyglot Reference]({{ "/docs/reference-manual/polyglot/" | relative_url }}) for information on how to set options programmatically when embedding.

### GraalVM Options

`--jvm` executes the application on the JVM instead of the native image.

`--jvm.<option>` passes JVM options to GraalVM (e.g. `--jvm.Xmx<size>`).
List available JVM options with `--jvm.help`.
System properties can be set as follows: `--jvm.D<name>=<value>`.
For example, `--jvm.Dgraal.TraceTruffleCompilation=true` will print finished compilations.

Likewise, `--native.<option>` passes VM options and system properties to the native image.
List available VM options with `--native.help`.

`--compiler.<property>=<value>` passes settings to the compiler.
For example, `--compiler.CompilationThreshold=<Integer>` sets the minimum number of invocations or loop iterations before a function is compiled.

### Polyglot Options

`--polyglot` enables you to interoperate with other programming languages.

`--<languageID>.<property>=<value>` passes options to guest languages through the Graal Polyglot SDK.
Use `--help:languages` to find out which options are available.