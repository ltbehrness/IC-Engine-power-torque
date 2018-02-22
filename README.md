# IC-Engine-power-torque
Project 1 consists in writing your own 0-D simulation software for the operation of an internal combustion engine. Students must hand in their original code as well as a short report detailing the analysis of a particular engine. 
Overview


Project 1 consists in writing your own 0-D simulation software for the operation of an internal
combustion engine. Students must hand in their original code as well as a short report detailing the
analysis of a particular engine.

Scope

Your code will simulate the torque and power output of a spark ignited engine, capturing at least the
following physical processes:
• heat transfer from the engine
• piston friction (due to the piston skirt, the piston rings, and the gas loading)
• finite heat release with a Wiebe function (graduate students only)

The goal is to simulate the brake torque vs. RPM and brake power vs. RPM of a spark-ignited,
naturally-aspirated, internal combustion engine for a specific set of engine geometric and operational
parameters. The report you produce will use your own code to compute those curves specific,
chosen/assigned parameters.

You can find the mathematical models of those basic processes in the recommended textbook by
Ferguson and Kirkpatrick, Internal Combustion Engines, sections 8.5 (heat transfer), 6.6 (friction), and
9.5 (heat release).
The model you will solve assumes all the gas in the cylinder is at the same pressure and temperature
(this is often referred to as a single zone model). The model is then simply derived by the 1st law of
thermodynamics. For a constant mass:

dE=dQ−dW

The internal energy of an ideal gas is
dE=mCv dT=Cvd(PV / R)=(Cv/R)d(PV )=(d(PV )/(γ−1))=(VdP+PdV )/(γ−1)

The indicated work is dW I=PdV . (You will first compute the indicated work and power and in a
second step subtract the work and power due to friction.) The heat transfer to and from the fluid is that
due to heat transfer and combustion, dQ=dQHT+dQcomb . Combining the different element, you get

[PdV + VdP]/(γ−1) = dQHT+dQcomb−PdV

which can be rewritten, in terms of derivatives with respect to the angle θ , for pressure and
indicated work as

dP/dθ = ( γ−1)/V (dQHT/d θ  + dQcomb / dθ )−γ P/V (dV/dθ)

dWI/d θ = P dV/dθ

Some notes


Justify the values you assume for any parameter
you need, but don’t have in this list. The parameters correspond to the EJ203 boxer 4 engine found in a
2003 subaru forester.
• Bore, 99.5 mm
• Stroke, 79.0 mm
• 4 pistons
• Assume a flat piston crown and flat head
• Connecting rod length, 131.5 mm
• Compression ratio, 10:1
• Naturally aspirated, Intake pressure = atmospheric pressure = 1 atm
• Standard, ideal gas, air properties, γ=1.4 , Cv=0.7175 kJ /kg. K ,
Cp=1.0045 kJ /kg.K
