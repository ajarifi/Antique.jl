```@meta
CurrentModule = Antique
```

# Spherical Oscillator

The spherical oscillator (3D isotropic harmonic oscillator) is the most frequently used model in quantum physics. This model uses a spherical coordinate system.

## Definitions

This model is described with the time-independent Schrödinger equation
```math
  \hat{H} \psi(r) = E \psi(r),
```
and the Hamiltonian
```math
  \hat{H} = - \frac{\hbar^2}{2\mu} \nabla^2 + V(r).
```
Parameters are specified with the following struct.

#### Parameters
```@docs; canonical=false
Antique.SphericalOscillator
```

#### Potential
```@docs; canonical=false
Antique.V(::SphericalOscillator, ::Any)
```

#### Eigen Values
```@docs; canonical=false
Antique.E(::SphericalOscillator)
```

#### Eigen Functions
```@docs; canonical=false
Antique.ψ(::SphericalOscillator, ::Any, ::Any, ::Any)
```

#### Radial Functions
```@docs; canonical=false
Antique.R(::SphericalOscillator, ::Any)
```

#### Generalized Laguerre Polynomials
!!! note
    The generalized Laguerre polynomials $L_n^{(\alpha)}(x)$, not the associated Laguerre polynomials $L_n^{k}(x)$, are used in this model. 

```@docs; canonical=false
Antique.L(::SphericalOscillator, ::Any)
```

#### Spherical Harmonics
```@docs; canonical=false
Antique.Y(::SphericalOscillator, ::Any, ::Any)
```

#### Associated Legendre Polynomials
```@docs; canonical=false
Antique.P(::SphericalOscillator, ::Any)
```

## Usage & Examples

[Install Antique.jl](@ref Install) for the first use and run `using Antique` before each use. The energy `E()`, wavefunction `ψ()`, potential `V()` and some other functions are suppoted. In this system, the model is generated by `SphericalOscillator` and several parameters `k`, `μ` and `ℏ` are set as optional arguments.

```@example SO
using Antique
SO = SphericalOscillator(k=1.0, μ=1.0, ℏ=1.0)
; # hide
```

Parameters:

```@repl SO
SO.k
SO.μ
SO.ℏ
```

Eigen values:

```@repl SO
E(SO, n=0)
E(SO, n=1)
E(SO, n=2)
E(SO, n=0, l=1)
E(SO, n=1, l=1)
E(SO, n=2, l=1)
```

## Testing

Unit testing and Integration testing were done using computer algebra system ([Symbolics.jl](https://symbolics.juliasymbolics.org/stable/)) and numerical integration ([QuadGK.jl](https://juliamath.github.io/QuadGK.jl/stable/)). The test script is [here](https://github.com/ohno/Antique.jl/blob/main/test/SphericalOscillator.jl).

```@eval
using Markdown
using Antique
Markdown.parse(Antique.load("../../test/result/SphericalOscillator.log"))
```
