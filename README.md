# Filament-calculator
## Calculates remaining lenght of filament left on the spool.

formula:
# Conversions
weight_kg = weight_g / 1000
density_kg_m3 = density_g_cm3 * 1000
diameter_m = diameter_mm / 1000
# Area
area = math.pi * (diameter_m / 2) ** 2
# Length
length_m = weight_kg / (density_kg_m3 * area)
