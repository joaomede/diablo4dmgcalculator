# diablo4 damage calculator

A web-based damage calculator built using Vue.js and Vuetify. This tool allows users to calculate damage based on various parameters such as weapon damage, skill percentage, main stats, additives, vulnerable damage, critical strike damage, global multipliers, and reduction damage.

## Features

- Switch between flat damage and weapon damage with skill percentage.
- Add multiple additives and global multipliers.
- Save and load profiles for different builds.
- Calculate final damage considering various factors.

## How to Use

1. **Select or Create a Profile**: Use the dropdown to select an existing profile or create a new one.
2. **Input Damage Parameters**:
    - Toggle between "Use Flat Damage" and the traditional method.
    - Enter values for weapon damage, skill percentage, or flat damage.
    - Fill in main stats, additives, vulnerable damage, critical strike damage, and global multipliers.
3. **Calculate Damage**: Click the "Calculate" button to see the result.
4. **Save Profile**: Save your current setup for future use.
5. **Delete Profile**: Remove an existing profile if no longer needed.

## Damage Calculation Formula

The final damage is calculated using the following formula:

$$
\text{Final Damage} = \text{Base Damage} \times (1 + \text{Total Additives}) \times (1 + \text{Vulnerable Bonus}) \times (1 + \text{Critical Strike Bonus}) \times (1 + \text{Main Stat Bonus}) \times (1 + \text{Total Global Multipliers}) \times \text{Reduction Multiplier}
$$

Where:

- **Base Damage**:
  - If using flat damage: `Flat Damage`
  - Otherwise: 
    $$
    \text{Weapon Damage} \times \left( \frac{\text{Skill Percentage}}{100} \right)
    $$

- **Total Additives**: Sum of all additive values divided by 100.
- **Vulnerable Bonus**: `Vulnerable / 100`
- **Critical Strike Bonus**: `Critical Strike Damage / 100`
- **Main Stat Bonus**: `Main Stats / 1000`
- **Total Global Multipliers**: Sum of all global multiplier values divided by 100.
- **Reduction Multiplier**: `(100 - Reduction Damage) / 100`

## Example

If you have the following inputs:

- Weapon Damage: 100
- Skill Percentage: 150
- Main Stats: 200
- Additives: [{name: "Additive 1", value: 20}]
- Vulnerable: 30
- Critical Strike Damage: 50
- Global Multipliers: [{name: "Multiplier 1", value: 10}]
- Reduction Damage: 20

The calculation would be:

$$
\text{Base Damage} = 100 \times \left( \frac{150}{100} \right) = 150
$$

$$
\text{Total Additives} = \frac{20}{100} = 0.2
$$

$$
\text{Vulnerable Bonus} = \frac{30}{100} = 0.3
$$

$$
\text{Critical Strike Bonus} = \frac{50}{100} = 0.5
$$

$$
\text{Main Stat Bonus} = \frac{200}{1000} = 0.2
$$

$$
\text{Total Global Multipliers} = \frac{10}{100} = 0.1
$$

$$
\text{Reduction Multiplier} = \frac{100 - 20}{100} = 0.8
$$

$$
\text{Final Damage} = 150 \times (1 + 0.2) \times (1 + 0.3) \times (1 + 0.5) \times (1 + 0.2) \times (1 + 0.1) \times 0.8
$$

$$
\text{Final Damage} = 150 \times 1.2 \times 1.3 \times 1.5 \times 1.2 \times 1.1 \times 0.8 \approx 292.32
$$

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/joaomede/Diablo4_SimpleDamageCalculator
    ```

2. Open `index.html` in your web browser.

## License

This project is licensed under the MIT License.
