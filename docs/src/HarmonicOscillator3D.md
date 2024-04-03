```@meta
CurrentModule = Antique
```

# Isotropic Harmonic Oscillator 3D

The isotropic harmonic oscillator is the most frequently used model in quantum physics.

## Definitions

This model is described with the time-independent Schrödinger equation
```math
  \hat{H} \psi(r) = E \psi(xr),
```
and the Hamiltonian
```math
  \hat{H} = - \frac{\hbar^2}{2m} \nabla^2 + V(r).
```
Parameters are specified with the following struct.

#### Parameters
```@docs; canonical=false
Antique.HarmonicOscillator3D
```

#### Potential
```@docs; canonical=false
Antique.V(::HarmonicOscillator3D, ::Any)
```

#### Eigen Values
```@docs; canonical=false
Antique.E(::HarmonicOscillator3D)
```

#### Eigen Functions
```@docs; canonical=false
Antique.ψ(::HarmonicOscillator3D, ::Any, ::Any, ::Any)
```

#### Radial Functions
```@docs; canonical=false
Antique.R(::HarmonicOscillator3D, ::Any)
```

#### Associated Laguerre Polynomials
```@docs; canonical=false
Antique.L(::HarmonicOscillator3D, ::Any)
```

#### Spherical Harmonics
```@docs; canonical=false
Antique.Y(::HarmonicOscillator3D, ::Any, ::Any)
```

#### Associated Legendre Polynomials
```@docs; canonical=false
Antique.P(::HarmonicOscillator3D, ::Any)
```

## Usage & Examples

[Install Antique.jl](@ref Install) for the first use and run `using Antique` before each use. The energy `E()`, wavefunction `ψ()`, potential `V()` and some other functions are suppoted. In this system, the model is generated by `HarmonicOscillator3D` and several parameters `k`, `m` and `ℏ` are set as optional arguments.

```@example HO3D
using Antique
HO3D = HarmonicOscillator3D(k=1.0, m=1.0, ℏ=1.0)
; # hide
```

Parameters:

```@repl HO3D
HO3D.k
HO3D.m
HO3D.ℏ
```

Eigen values:

```@repl HO3D
E(HO3D, n=0)
E(HO3D, n=1)
```

## Testing

Unit testing and Integration testing were done using computer algebra system ([Symbolics.jl](https://symbolics.juliasymbolics.org/stable/)) and numerical integration ([QuadGK.jl](https://juliamath.github.io/QuadGK.jl/stable/)). The test script is [here](https://github.com/ohno/Antique.jl/blob/main/test/HarmonicOscillator3D.jl).

```@eval
using Markdown
using Antique
Markdown.parse(Antique.load("../../test/result/HarmonicOscillator3D.log"))
```