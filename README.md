# go-kubectx

Simply 5x-10x faster alternative to famous [kubectx](https://github.com/ahmetb/kubectx). Uses client-go.

### Dependencies
Requires [fzf](https://github.com/junegunn/fzf) same as original kubectx.

### Install
Using go mod, requires go>=1.13
```
git clone git@github.com:aca/go-kubectx.git

# Using go mod, requires Go>=1.13
(cd go-kubectx/cmd/kubens && go install)
(cd go-kubectx/cmd/kubectx && go install)

# Using Docker - also cross-compiles for other OS's
cd go-kubectx && ./build.sh

files will be output into the output directory after build.
```

### Benchmarks

| Command | Mean [ms] | Min [ms] | Max [ms] | Relative |
|:---|---:|---:|---:|---:|
| `/usr/bin/kubectx minikube` | 98.9 ± 12.1 | 84.8 | 138.6 | 5.35 ± 0.89 |
| `/home/rok/bin/kubectx minikube` | 18.5 ± 2.1 | 15.6 | 27.1 | 1.00 |


| Command | Mean [ms] | Min [ms] | Max [ms] | Relative |
|:---|---:|---:|---:|---:|
| `/usr/bin/kubens kube-system` | 258.6 ± 20.7 | 237.9 | 300.9 | 5.73 ± 1.78 |
| `/home/rok/bin/kubens kube-system` | 45.1 ± 13.6 | 32.3 | 120.0 | 1.00 |
