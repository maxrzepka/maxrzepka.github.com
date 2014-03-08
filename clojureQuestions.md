Q How to SNAPSHOT jar dependencies
A use :repositories {"sonatype-oss-public" "https://oss.sonatype.org/content/repositories/snapshots/"}

Q How to instaiate a regexp from a string ?
A (. java.util.regex.Pattern (compile s))

Q test if a regexp exists ?
A (re-find #"your regexp" "test string")

Q Use of as-> ?
A (as-> [[1 1 1] 2 3] x (nth x 0) (map inc x))
A instead of (-> [[1 1 1] 2 3] (nth 0) (#(map inc %)))

Q difference between (:require _ :refer [_]]) and (:use _ :only [_]) ?
R (:require [carica.core :refer [configurer resources]])

Q Get all methods of a Java Class
A (map #(.getName %) (.getMethods (class your_object)))

Q How to convert var to a symbol #'codox.reader/read-namespaces --> read-namespaces ?

Q How to log any error on ring server ?
T ring-stackware

Q Macro usage ( toolfinger ) ,
Q (defn haz? [coll element] (boolean (some (conj #{} element) coll)))
Q (defmacro haz? [coll elem] `(boolean (some #{~elem} ~coll)))


Q arglist usage ?
Q(defmacro defmapop
Q  {:arglists '([name doc-string? attr-map? [fn-args*] body])}
Q  [& args]
Q  (defop-helper 'cascalog.workflow/map args))

Q How to print lastr exception ?
A (use 'clojure.stacktrace) (print-stack-trace *e 5)  (print-cause-trace *e 3) 

Q Why use :use :require instead of use or require in namespace declaration ?

Q usage of (def ^{:dynamic true} *mongo-config* {}) ?

Q How works protocol dispatch order ?

Q How to measure performance of function ? be more specific !!

Q Number of loc ?  distinct / set which one is more efficient ?
H add cgrand's citation

Q Why protocol remove ifs ? , map or set do the job. in fact any dispatch mecanism ?

Q why in enlive  [:div #{[:h3 :a] :p}] is not equivalent to #{[:div :h3 :a] [:div :p]} ?

Q How to call private functions ?
A #'namespace/fct-name

Q How to test enlive transformation or select at the repl ?
A (h/sniptest "<div>some text<a>link</a> another text <br><pre>code 1</pre><pre>code 2</pre></div>" [:div :pre] (h/content "found"))
A (h/select (h/html-snippet  "<div>some text<a>link</a> another text <br><pre>code 1</pre><pre>code 2</pre></div>" [:div :pre]))
T enlive

Q How to select a from containing a submit button ?
A Use predicate has
A ([[:form (h/has [[#{:input :button} (h/attr= :type "submit")]])]])
T enlive

Q How save a sequence into a file ?
A (spit "filename" (apply str coll))

Q Syntax of condp ?
A (condp = x 2 (sth) 3 (sth2) 100)

Q Save clojure code in file
A (spit "file" (pr-str code))

Q Get back clojure code from file
A (def code (read-string (slurp "file")))

Q Difference between read-string and load-string ?
A load-string evaluate loaded code

Q Get current classpath ?
A  (println (seq (.getURLs (java.lang.ClassLoader/getSystemClassLoader))))
A  (.getURLs (->  (java.lang.Thread/currentThread)  (.getContextClassLoader)))

Q How to do string search ?
A (re-find #"regexp" "text")

Q list all functions of namespace
A (map first (ns-publics 'yourNamespace))

Q split for collection similar to (.split sentence " ")
A (remove separator (partition-by #{separator} coll))
H partition-by

Q boolean : Which values are false ?
A false nil
T core

Q transpose in 3 words ?
A (fn[coll] (apply map list coll))
H transpose : inverse line column definition?
T core

Q extract diagonal from a 2 dimensional array (square)
H take-nth
A (take size (take-nth (dec size) (drop (dec size) (flatten square))))
A (take-nth (inc size) square)
T core

Q What the difference between conj and cons ?
A cons : append a element at the head of the coll
A conj[oin] append to a coll a variable number of elements
T core

Q group by first column a collection 2-tuple ?
A (reduce (fn[m [k v]] (update-in m [k] conj v)) {} coll)
T core

Q list 2-uple to hash ?
A (into {} [[k1 v1] [k2 v2] [k3 v3]])
T core

Q How to set breakpoint in swank ?
A add code (swank.core/break)

Q Get lines of file ?
A (line-seq (java.io.BufferedReader. (java.io.FileReader. "filepath")))
T core

Q Union of 2 sets ?
A (reduce conj s1 s2)

Q How to add dependencies in classpath ?
A (use '[cemerick.pomegranate :only (add-dependencies)])
A  (add-dependencies :coordinates '[[org.clojure/core.logic "0.6.8"]]
A                    :repositories (merge cemerick.pomegranate.aether/maven-central
A                                     {"clojars" "http://clojars.org/repo"}))
A  repositories option  not needed if already present in ~/.m2/
W cemerick.pomegranate is not in classpath inside a lein project
T lein
