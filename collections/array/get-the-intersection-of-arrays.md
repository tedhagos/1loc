~~~ javascript
// space: O(n)
// time: O(n)
const getIntersection = (...arr) => [...(arr.flat().reduce((map, v) => map.set(v, (map.get(v) || 0) + 1), new Map()))].reduce((acc, [v, count]) => void (count === arr.length && acc.push(v)) || acc, []);

// getIntersection([1, 2, 3], [2, 3, 4, 5]) returns [2, 3]
// getIntersection([1, 2, 3], [2, 3, 4, 5], [1, 3, 5]) returns [3]
~~~