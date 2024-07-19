# AFR

## Theory

λ - air-fuel ratio (AFR)
* accepted stoichiometric AFR: 14.7:1
* calculated stoichiometric AFR: 16.673:1
  
λ = measured AFR _or_ stoichiometric AFR (1.0 indicating stoich)

* `λ=0.86 (12.5) maximum power (from 11.5 to 13.2)     high CO, high HC, low NOx`
* `λ=1.00 (14.7) complete burn                         closed-loop target`
* `λ=1.05 (15.4) best fuel economy                     low CO, low HC, high NOx`
* `λ=1.12 (16.5) best combustion efficiency            low CO, low HC, low NOx`

## Sensors

### Narrow-band sensor

1 Vpp working range
Sharp drop characteristic:

  * `1V   : AFR 12.5:1..14.0:1 (0.86..0.95) rich`
  * `1V-0V: AFR 14.0:1..15.4:1 (0.95..1.05) stoich`
  * `0V   : AFR 15.4:1..16.5:1 (1.05..1.12) lean`

### Wide-band sensor

5 Vpp working range
Constant slope characteristic:

`AFR = Voltage * 2 + 10`

# Mix

Input:
    Key assembly
    Thermals
        IAT
        Water
        Oil
        EGT (on diesel)
    Pressures
        Fuel
        Oil
        Water/Ethanol
    Gasses
        Intake flow
            v: AFM
                vane-type, analog, linear resistor
                Karman vortex-type, analog, optocoupler
            v: MAF - measures mass
                hot-wire - digital out to warm up, analog, atmosensor
                hot-film - differential hot-wire
            v: MAP - measures density
                in the intake manifold
            most cars: MAF+MAP
        Exhaust oxygen
            v: narrowband (rich/OK/lean)
            v: Wideband O2 (actual λ)
            most cars have dual:
                upstream (after exhaust manifold)
                downstream (after catalytic converter)
    Position
        Throttle
            v: variable resistor
            v: hall-effect
        Crank
        Cam
            Count:
                1 (OHV, CIH, SOHC)
                2 (DOHC, VR-DOHC, V-OHC)
                4 (V-DOHC)
            v: variable reluctance
            v: hall-effect
    Acoustic
        Knock

Output
    Throttle
    Fans
        Radiator
    Fuel
        Injectors 1-8
    Ignition
        Coils 1-8
        v: individual CnP/CoP
        v: wasted spark
    Needles
        RPM
            v: digital
                LPF?
            v: analog

    VVT?
    VVL?

Tables
        VE map (volumetric efficiency) - reads VE, injects according to that
            max 30% offset
        wideband reas back lambda
        λ target map: - checks against wideband
        injector map
