# ClojureDart Unit Testing

## Setup

* create simple flutter project using `https://github.com/Tensegritics/ClojureDart/blob/main/doc/flutter-quick-start.md`
* add a simple test file

## Discoveries so far...

1. Tests are not compiled when running `clj -M -m cljd.build flutter`.
2. If test file is saved while project is running in the simulator tests are compiled to `test/cljd-out/hello/hello-test_test.dart`
3. Running `flutter test` results in:

```
00:00 +0: loading /Users/user/dev/hello/test/cljd-out/hello/hello-test_test.dart                             test/cljd-out/hello/hello-test_test.dart:2:8: Error: Error when reading
'/Users/user/dev/hello/lib/cljd-out/cljd/core.dart': No such file or directory
import "../../..//Users/user/dev/hello/lib/cljd-out/cljd/core.dart" as Uedhlcoc_core;
       ^
test/cljd-out/hello/hello-test_test.dart:3:8: Error: Error when reading
'/Users/user/dev/hello/lib/cljd-out/cljd/test.dart': No such file or directory
import "../../..//Users/user/dev/hello/lib/cljd-out/cljd/test.dart" as Uedhlcoc_test;
       ^
test/cljd-out/hello/hello-test_test.dart:11:78: Error: Undefined name 'symbol'.
final dc.List<dc.dynamic> fl$1=(dc.List<dc.dynamic>.filled(2, (Uedhlcoc_core.symbol.$_invoke$2("cljd.test",
"*groups*", )), ));
                                                                             ^^^^^^
test/cljd-out/hello/hello-test_test.dart:12:43: Error: Undefined name '$STAR_groups$STAR_'.
final dc.dynamic coll7303$1=Uedhlcoc_test.$STAR_groups$STAR_;
                                          ^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:15:33: Error: 'ICollection$iface' isn't a type.
if((coll7303$1 is Uedhlcoc_core.ICollection$iface)){
                                ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:16:38: Error: 'ICollection$iface' isn't a type.
$if_$1=((coll7303$1 as Uedhlcoc_core.ICollection$iface).$_conj$1(o7304$1, ));
                                     ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:18:24: Error: Undefined name 'ICollection'.
$if_$1=((Uedhlcoc_core.ICollection.extensions((coll7303$1 as dc.dynamic), ) as
Uedhlcoc_core.ICollection$ext).$_conj$1((coll7303$1 as dc.dynamic), o7304$1, ));
                       ^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:18:94: Error: 'ICollection$ext' isn't a type.
$if_$1=((Uedhlcoc_core.ICollection.extensions((coll7303$1 as dc.dynamic), ) as
Uedhlcoc_core.ICollection$ext).$_conj$1((coll7303$1 as dc.dynamic), o7304$1, ));
                                                                                             ^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:21:21: Error: 'PersistentHashMap' isn't a type.
final Uedhlcoc_core.PersistentHashMap $1=Uedhlcoc_core.$_map_lit(fl$1, );
                    ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:21:56: Error: Method not found: '$_map_lit'.
final Uedhlcoc_core.PersistentHashMap $1=Uedhlcoc_core.$_map_lit(fl$1, );
                                                       ^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:22:60: Error: Method not found: 'push_dynamic_bindings'.
final dc.dynamic prev_bindings$7998_$AUTO_$1=Uedhlcoc_core.push_dynamic_bindings($1, );
                                                           ^^^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:24:78: Error: Undefined name 'symbol'.
final dc.List<dc.dynamic> fl$2=(dc.List<dc.dynamic>.filled(2, (Uedhlcoc_core.symbol.$_invoke$2("cljd.test",
"*groups*", )), ));
                                                                             ^^^^^^
test/cljd-out/hello/hello-test_test.dart:25:43: Error: Undefined name '$STAR_groups$STAR_'.
final dc.dynamic coll7303$2=Uedhlcoc_test.$STAR_groups$STAR_;
                                          ^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:28:33: Error: 'ICollection$iface' isn't a type.
if((coll7303$2 is Uedhlcoc_core.ICollection$iface)){
                                ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:29:38: Error: 'ICollection$iface' isn't a type.
$if_$2=((coll7303$2 as Uedhlcoc_core.ICollection$iface).$_conj$1(o7304$2, ));
                                     ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:31:24: Error: Undefined name 'ICollection'.
$if_$2=((Uedhlcoc_core.ICollection.extensions((coll7303$2 as dc.dynamic), ) as
Uedhlcoc_core.ICollection$ext).$_conj$1((coll7303$2 as dc.dynamic), o7304$2, ));
                       ^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:31:94: Error: 'ICollection$ext' isn't a type.
$if_$2=((Uedhlcoc_core.ICollection.extensions((coll7303$2 as dc.dynamic), ) as
Uedhlcoc_core.ICollection$ext).$_conj$1((coll7303$2 as dc.dynamic), o7304$2, ));
                                                                                             ^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:34:21: Error: 'PersistentHashMap' isn't a type.
final Uedhlcoc_core.PersistentHashMap $2=Uedhlcoc_core.$_map_lit(fl$2, );
                    ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:34:56: Error: Method not found: '$_map_lit'.
final Uedhlcoc_core.PersistentHashMap $2=Uedhlcoc_core.$_map_lit(fl$2, );
                                                       ^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:35:60: Error: Method not found: 'push_dynamic_bindings'.
final dc.dynamic prev_bindings$7998_$AUTO_$2=Uedhlcoc_core.push_dynamic_bindings($2, );
                                                           ^^^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:37:26: Error: 'PersistentHashMap' isn't a type.
late final Uedhlcoc_core.PersistentHashMap? $try_$1;
                         ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:39:54: Error: Undefined name 'list'.
final dc.dynamic values$8872_$AUTO_$1=(Uedhlcoc_core.list.$_invoke$2(1, 1, ));
                                                     ^^^^
test/cljd-out/hello/hello-test_test.dart:40:85: Error: Undefined name '$EQ_'.
final dc.dynamic result$8873_$AUTO_$1=(Uedhlcoc_core.apply.$_invoke$2(Uedhlcoc_core.$EQ_,
values$8872_$AUTO_$1, ));
                                                                                    ^^^^
test/cljd-out/hello/hello-test_test.dart:40:54: Error: Undefined name 'apply'.
final dc.dynamic result$8873_$AUTO_$1=(Uedhlcoc_core.apply.$_invoke$2(Uedhlcoc_core.$EQ_,
values$8872_$AUTO_$1, ));
                                                     ^^^^^
test/cljd-out/hello/hello-test_test.dart:44:83: Error: Couldn't find constructor 'Keyword'.
final dc.List<dc.dynamic> fl$3=(dc.List<dc.dynamic>.filled(6, const Uedhlcoc_core.Keyword(null, "type",
3318123983, ), ));
                                                                                  ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:45:29: Error: Couldn't find constructor 'Keyword'.
fl$3[1]=const Uedhlcoc_core.Keyword(null, "fail", 4066245304, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:46:29: Error: Couldn't find constructor 'Keyword'.
fl$3[2]=const Uedhlcoc_core.Keyword(null, "actual", 852479220, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:47:55: Error: Undefined name 'symbol'.
fl$3[3]=(Uedhlcoc_core.list.$_invoke$2((Uedhlcoc_core.symbol.$_invoke$2(null, "not", )),
Uedhlcoc_core.cons((Uedhlcoc_core.symbol.$_invoke$2(null, "=", )), values$8872_$AUTO_$1, ), ));
                                                      ^^^^^^
test/cljd-out/hello/hello-test_test.dart:47:124: Error: Undefined name 'symbol'.
fl$3[3]=(Uedhlcoc_core.list.$_invoke$2((Uedhlcoc_core.symbol.$_invoke$2(null, "not", )),
Uedhlcoc_core.cons((Uedhlcoc_core.symbol.$_invoke$2(null, "=", )), values$8872_$AUTO_$1, ), ));
                                                                                                    ^^^^^^
test/cljd-out/hello/hello-test_test.dart:47:104: Error: Method not found: 'cons'.
fl$3[3]=(Uedhlcoc_core.list.$_invoke$2((Uedhlcoc_core.symbol.$_invoke$2(null, "not", )),
Uedhlcoc_core.cons((Uedhlcoc_core.symbol.$_invoke$2(null, "=", )), values$8872_$AUTO_$1, ), ));
                                                                                                    ^^^^
test/cljd-out/hello/hello-test_test.dart:47:24: Error: Undefined name 'list'.
fl$3[3]=(Uedhlcoc_core.list.$_invoke$2((Uedhlcoc_core.symbol.$_invoke$2(null, "not", )),
Uedhlcoc_core.cons((Uedhlcoc_core.symbol.$_invoke$2(null, "=", )), values$8872_$AUTO_$1, ), ));
                       ^^^^
test/cljd-out/hello/hello-test_test.dart:48:29: Error: Couldn't find constructor 'Keyword'.
fl$3[4]=const Uedhlcoc_core.Keyword(null, "message", 1042898137, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:50:23: Error: Method not found: '$_map_lit'.
$try_$1=Uedhlcoc_core.$_map_lit(fl$3, );
                      ^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:53:83: Error: Couldn't find constructor 'Keyword'.
final dc.List<dc.dynamic> fl$4=(dc.List<dc.dynamic>.filled(6, const Uedhlcoc_core.Keyword(null, "type",
3318123983, ), ));
                                                                                  ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:54:29: Error: Couldn't find constructor 'Keyword'.
fl$4[1]=const Uedhlcoc_core.Keyword(null, "error", 465527971, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:55:29: Error: Couldn't find constructor 'Keyword'.
fl$4[2]=const Uedhlcoc_core.Keyword(null, "stacktrace", 1805465879, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:57:29: Error: Couldn't find constructor 'Keyword'.
fl$4[4]=const Uedhlcoc_core.Keyword(null, "exception", 2303443619, );
                            ^^^^^^^
test/cljd-out/hello/hello-test_test.dart:59:23: Error: Method not found: '$_map_lit'.
$try_$1=Uedhlcoc_core.$_map_lit(fl$4, );
                      ^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:61:48: Error: Method not found: 'result'.
final dc.dynamic r$8894_$AUTO_$1=Uedhlcoc_test.result($try_$1, );
                                               ^^^^^^
test/cljd-out/hello/hello-test_test.dart:63:78: Error: Undefined name 'symbol'.
final dc.List<dc.dynamic> fl$5=(dc.List<dc.dynamic>.filled(3, (Uedhlcoc_core.symbol.$_invoke$2(null, "=", )),
));
                                                                             ^^^^^^
test/cljd-out/hello/hello-test_test.dart:66:21: Error: 'PersistentList' isn't a type.
final Uedhlcoc_core.PersistentList $3=Uedhlcoc_core.$_list_lit(fl$5, );
                    ^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:66:53: Error: Method not found: '$_list_lit'.
final Uedhlcoc_core.PersistentList $3=Uedhlcoc_core.$_list_lit(fl$5, );
                                                    ^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:67:40: Error: Method not found: 'cljd_test_matcher'.
final dc.dynamic cast$1=(Uedhlcoc_test.cljd_test_matcher($3, ) as dc.dynamic);
                                       ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:70:15: Error: Method not found: 'restore_dynamic_bindings'.
Uedhlcoc_core.restore_dynamic_bindings(prev_bindings$7998_$AUTO_$2, );
              ^^^^^^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:73:15: Error: Method not found: 'restore_dynamic_bindings'.
Uedhlcoc_core.restore_dynamic_bindings(prev_bindings$7998_$AUTO_$1, );
              ^^^^^^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:76:20: Error: Undefined name '$STAR_in_test$STAR_'.
if(((Uedhlcoc_test.$STAR_in_test$STAR_!=false)&&(Uedhlcoc_test.$STAR_in_test$STAR_!=null))){
                   ^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:76:64: Error: Undefined name '$STAR_in_test$STAR_'.
if(((Uedhlcoc_test.$STAR_in_test$STAR_!=false)&&(Uedhlcoc_test.$STAR_in_test$STAR_!=null))){
                                                               ^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:79:78: Error: Undefined name 'symbol'.
final dc.List<dc.dynamic> fl$6=(dc.List<dc.dynamic>.filled(2, (Uedhlcoc_core.symbol.$_invoke$2("cljd.test",
"*in-test*", )), ));
                                                                             ^^^^^^
test/cljd-out/hello/hello-test_test.dart:81:21: Error: 'PersistentHashMap' isn't a type.
final Uedhlcoc_core.PersistentHashMap $4=Uedhlcoc_core.$_map_lit(fl$6, );
                    ^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:81:56: Error: Method not found: '$_map_lit'.
final Uedhlcoc_core.PersistentHashMap $4=Uedhlcoc_core.$_map_lit(fl$6, );
                                                       ^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:82:60: Error: Method not found: 'push_dynamic_bindings'.
final dc.dynamic prev_bindings$7998_$AUTO_$3=Uedhlcoc_core.push_dynamic_bindings($4, );
                                                           ^^^^^^^^^^^^^^^^^^^^^
test/cljd-out/hello/hello-test_test.dart:86:15: Error: Method not found: 'restore_dynamic_bindings'.
Uedhlcoc_core.restore_dynamic_bindings(prev_bindings$7998_$AUTO_$3, );
              ^^^^^^^^^^^^^^^^^^^^^^^^
00:01 +0 -1: loading /Users/user/dev/hello/test/cljd-out/hello/hello-test_test.dart [E]
  Failed to load "/Users/user/dev/hello/test/cljd-out/hello/hello-test_test.dart": Compilation failed for testPath=/Users/user/dev/hello/test/cljd-out/hello/hello-test_test.dart
  Exception: the Dart compiler exited unexpectedly.
  package:flutter_tools/src/base/common.dart 10:3  throwToolExit
  package:flutter_tools/src/compile.dart 784:9     DefaultResidentCompiler._compile.<fn>
  dart:async/zone.dart 1434:47                     _rootRunUnary
  dart:async/zone.dart 1335:19                     _CustomZone.runUnary
```

4. Running `dart test` results in:

```
Could not find a file named "pubspec.yaml" in "/Users/user/.pub-cache/hosted/pub.dartlang.org/_fe_analyzer_shared-38.0.0"
```

5. Adding `_fe_analyzer_shared: 38.0.0` to the flutter `pubspec.yaml` and running `flutter pub get` still yields `"/Users/user/.pub-cache/hosted/pub.dartlang.org/_fe_analyzer_shared-38.0.0"` because the dependency is added to flutter but not dart.
6. Creating a simple dart project using `https://github.com/Tensegritics/ClojureDart/blob/main/doc/quick-start.md` and adding `_fe_analyzer_shared` to it's `pubspec.yaml` allows `dart test` to find the dependency. However re-running `dart test` in flutter results in another `Could not find a file named "pubspec.yaml"...` error.
7. Repeating `6` for each missing dependency and then running `dart test` results in:

```
The Flutter SDK is not available.
#0      BoundSdkSource.getDirectory (package:pub/src/source/sdk.dart:125:7)
#1      SystemCache.load (package:pub/src/system_cache.dart:113:52)
#2      Entrypoint._createPackageGraph (package:pub/src/entrypoint.dart:112:63)
#3      Entrypoint.packageGraph (package:pub/src/entrypoint.dart:107:54)
#4      getExecutableForCommand (package:pub/src/executable.dart:338:19)
#5      TestCommand.run (package:dartdev/src/commands/test.dart:32:36)
#6      CommandRunner.runCommand (package:args/command_runner.dart:209:27)
#7      DartdevRunner.runCommand (package:dartdev/dartdev.dart:232:30)
#8      CommandRunner.run.<anonymous closure> (package:args/command_runner.dart:119:25)
#9      new Future.sync (dart:async/future.dart:296:31)
#10     CommandRunner.run (package:args/command_runner.dart:119:14)
#11     runDartdev (package:dartdev/dartdev.dart:67:29)
#12     main (file:///opt/s/w/ir/cache/builder/sdk/pkg/dartdev/bin/dartdev.dart:11:9)
#13     _delayEntrypointInvocation.<anonymous closure> (dart:isolate-patch/isolate_patch.dart:293:32)
#14     _RawReceivePortImpl._handleMessage (dart:isolate-patch/isolate_patch.dart:192:12)
```
