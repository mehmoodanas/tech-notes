import timeit, sys, platform, random
print(sys.version.split()[0], platform.platform())
for n in (100,1_000,10_000,100_000):
    data=list(range(n)); s=set(data); t=tuple(data)
    random.seed(1); keys=[random.randrange(n) for _ in range(200)]
    def f_list():
        for k in keys: k in data
    def f_set():
        for k in keys: k in s
    r=5
    tl=min(timeit.repeat(f_list,number=20,repeat=r))/20/200*1e9
    ts=min(timeit.repeat(f_set,number=20,repeat=r))/20/200*1e9
    print(f"n={n:>7} list={tl:10.1f} ns/lookup  set={ts:7.1f} ns/lookup  ratio={tl/ts:8.1f}x")
