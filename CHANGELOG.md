### 1.9.0

* Cascalog now uses the Eclipse Public License, vs the old GNU Public License!
* Support for Cascading 2.0 (Hadoop planner only, for now)
  * Trap now trap the problem argument vs the entire tuple.
* Sinkmode options are now :keep, :update and :replace
* Extensive documentation of functions in cascalog.ops
* Builds are now tested against clojure 1.4 in addition to 1.2 and 1.3.

### 1.8.4

* Add project-wide jobconf settings in job-conf.clj.
* optional docstring and metadata support on defparallelagg and defparallelbuf.
* def*ops now present proper argument list metadata.
* Added cascalog.ops/partial
* fixed :sinkmode op
* defaggregateop no longer fails when returning nil
* Better error reporting on parametrized ops (variadic args aren't supported; this now throws an error.)
* MUCH better error messaging on failed tests. Here's the old way:

    expected: (= (map multi-set (map doublify set1)) (map multi-set (map doublify set2)))
      actual: (not (= ({[2.0] 1}) ({[1.0] 1})))

vs the new:

    expected: (= input output)
    actual: (not (= [[2.0]] [[1.0]]))