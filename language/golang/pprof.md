Then use the pprof tool to look at the heap profile:
> go tool pprof http://localhost:6060/debug/pprof/heap


Or to look at a 30-second CPU profile:
> go tool pprof http://localhost:6060/debug/pprof/profile


Or to look at the goroutine blocking profile:  
> go tool pprof http://localhost:6060/debug/pprof/block


> go tool pprof --pdf http://127.0.0.1:6000/debug/pprof/profile > cpu.pdf
> go tool pprof --pdf http://127.0.0.1:6000/debug/pprof/heap > memory.pdf
> go tool pprof --pdf http://127.0.0.1:6000/debug/pprof/goroutine > gorotine.pdf
