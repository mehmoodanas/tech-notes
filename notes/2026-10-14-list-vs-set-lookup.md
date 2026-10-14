# List vs set membership in Python: I measured how fast the gap grows

*14 October 2026*

A classic advice line in Python code reviews is "use a set for membership checks". It is well known, but how big is the difference in practice? Instead of repeating a news item, I ran a small experiment and report only what I measured.

## Setup

- Python 3.12.10 on Windows 11, standard library only (`timeit`, best of 5 repeats)
- Container holds the integers `0..n-1`; 200 random keys, all present, are looked up with `k in container`
- Compared a `list` (linear scan) against a `set` (hash lookup)
- Script: [2026-10-14-membership-bench.py](code/2026-10-14-membership-bench.py)

## Results (nanoseconds per lookup)

| n | list | set | list / set |
|---:|---:|---:|---:|
| 100 | 378 | 27 | 14x |
| 1,000 | 4,061 | 39 | 106x |
| 10,000 | 40,493 | 39 | 1,042x |
| 100,000 | 446,649 | 42 | 10,724x |

## Reading the numbers

- The list cost grows roughly in proportion to n (each 10x in size gives about 10x in time), matching the documented linear-time behaviour of `in` on lists.
- The set cost stays almost flat at about 30-40 ns, consistent with average constant-time hash lookups.
- Even at 100 items the set is already about 14x faster, so the habit pays off early.

## Caveats

- These are single-machine, single-run-set numbers; exact values will differ by CPU and Python version, but the shape should hold.
- Keys here were always present and the data were small ints. Missing keys make list lookups slower still (full scan); hashing expensive objects makes sets slower.
- Building a set has a cost (and uses more memory), so for a single lookup in a small list a plain `list` is fine. Convert once when you will check many times.

## Sources

- [Python docs: time complexity of common operations](https://wiki.python.org/moin/TimeComplexity)
- [Python docs: `timeit` module](https://docs.python.org/3/library/timeit.html)
- Own measurements (script linked above)
