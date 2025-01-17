# TestEnv

[![Build Status](https://github.com/JuliaTesting/TestEnv.jl/workflows/CI/badge.svg)](https://github.com/JuliaTesting/TestEnv.jl/actions)
[![Coverage](https://codecov.io/gh/JuliaTesting/TestEnv.jl/branch/main/graph/badge.svg)](https://codecov.io/gh/JuliaTesting/TestEnv.jl)
[![Code Style: Blue](https://img.shields.io/badge/code%20style-blue-4495d1.svg)](https://github.com/invenia/BlueStyle)
[![ColPrac: Contributor's Guide on Collaborative Practices for Community Packages](https://img.shields.io/badge/ColPrac-Contributor's%20Guide-blueviolet)](https://github.com/SciML/ColPrac)


This is a 1-function package: `TestEnv.activate()`.

Consider this package has as a test-only dependency of **ChainRulesCore.jl**.
Not a main dependency

```julia
julia> using TestEnv;

julia> TestEnv.activate();

julia> using ChainRulesCore
```

You an also pass in the name of a package, to activate that package and it's test dependencies:
`TestEnv.activate("Javis")` for example would activate Javis.jl's test environment.

Finally you can pass in a function to run in this environment.
```julia
using TestEnv, ReTest
TestEnv.activate("Example") do
    retest()
end
```


