clojure-swissrailwaynet
=======================

The swiss public transportation system graph consisting of approximately 15000 nodes and 15000 edges given as clojure datastructure. Well suited for graph search algorithm performance tests

Specs
=====

The net consists 14376 nodes as well as 15463 edges.

A node is a map with the following keys

:y - y coordinate in swiss topo coordinates (http://en.wikipedia.org/wiki/Swiss_coordinate_system)
:x - x coordinate in swiss topo coordinates (http://en.wikipedia.org/wiki/Swiss_coordinate_system)
:bez1 - Offical name from swiss public transportation agency (BAV - http://www.bav.admin.ch/)
:bez2 - not relevant
:uic - international duty point identifier
:didok - swiss duty point identifier

Usage
=====

For reading-in the files define a clojure reader function

<pre>
(defn frm-load
  "Load a clojure form from file."
  [#^java.io.File file]
  (with-open [r (java.io.PushbackReader. 
     (java.io.FileReader. file))] 
     (let [rec (read r)]
      rec)))
</pre>

and read in the files 
* swiss-public-transportation-net-nodes.dat and 
* swiss-public-transportation-net-edges.dat
