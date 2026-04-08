# Filament-calculator
## Calculates remaining lenght of filament left on the spool.

# Conversions
weight_kg = weight_g / 1000

density_kg_m3 = density_g_cm3 * 1000

diameter_m = diameter_mm / 1000
# Area
area = math.pi * (diameter_m / 2) ** 2
# Length
length_m = weight_kg / (density_kg_m3 * area)

# Example
python length_calc.py -w 1000 -d 1.26 -m 1.75

Filament length: 329.96 meters
