TODOs:
* [ ] Find examples of use of all type classes.

Pages tagged with `#todo`:
```dataview
LIST FROM #todo AND "Designing Drasil's Chunks 2025"
```

```dataview
TABLE WITHOUT ID string(ol) AS "Missing reference", join(rows.file.link, ", ") AS "Referees"
FLATTEN file.outlinks AS ol
WHERE contains(file.path, "Designing Drasil's Chunks 2025")
  AND !ol.file
  AND regexmatch(".+\.(png|jpe?g|gif|bmp|svg|webp).+", lower(string(ol))) = false
GROUP BY ol
SORT ol ASC
```
