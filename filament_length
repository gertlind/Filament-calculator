import math
import argparse
import sys


def filament_length(weight_g, density_g_cm3, diameter_mm):
    weight_kg = weight_g / 1000
    density_kg_m3 = density_g_cm3 * 1000
    diameter_m = diameter_mm / 1000

    area = math.pi * (diameter_m / 2) ** 2
    length_m = weight_kg / (density_kg_m3 * area)

    return length_m


def main():
    parser = argparse.ArgumentParser(
        description="Calculate 3D filament length"
    )

    parser.add_argument(
        "-w", "--weight",
        type=float,
        required=True,
        help="Total spool weight (g)"
    )

    parser.add_argument(
        "-s", "--spool",
        type=float,
        required=False,
        default=0,
        help="Empty spool weight (g)"
    )

    parser.add_argument(
        "-d", "--density",
        type=float,
        required=True,
        help="Density (g/cm³)"
    )

    parser.add_argument(
        "-m", "--diameter",
        type=float,
        required=True,
        help="Diameter (mm)"
    )

    args = parser.parse_args()

    filament_weight = args.weight - args.spool

    if filament_weight <= 0:
        print("Error: spool weight must be less than total weight", file=sys.stderr)
        sys.exit(1)

    length = filament_length(filament_weight, args.density, args.diameter)

    print(f"Filament weight: {filament_weight:.0f} g")
    print(f"Filament length: {length:.2f} meters")


if __name__ == "__main__":
    main()
