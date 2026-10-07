# CSV Asteroid Mining Processor

## Basic Premise

Create a Python program in `main.py` that processes data collected from asteroid mining scans. Each row of the provided CSV file contains the amount of three different resources found on an asteroid.

Your program will read `input_asteroid_data.csv`, calculate new numerical values for every asteroid, and write the processed data to a new file named `output_asteroid_data.csv`.

Each resource has a different cargo value:

- Ore is worth **2 points per unit**
- Crystal is worth **5 points per unit**
- Gas is worth **3 points per unit**

For each asteroid:

```text
total_units = ore_units + crystal_units + gas_units

cargo_value = (ore_units × 2) + (crystal_units × 5) + (gas_units × 3)
```

For example:

```text
AST-001,42,18,27
```

should produce:

```text
total_units = 87
cargo_value = 255
```

## Basic File Structure

Your starter folder will contain:

```text
basic/
├── main.py
└── input_asteroid_data.csv
```

After running the completed program, it should also contain `output_asteroid_data.csv`.


## Basic Requirements

* [ ] Use Python's `csv` module to read `input_asteroid_data.csv` and process every asteroid row.
* [ ] Use the existing CSV headers to access `asteroid_id`, `ore_units`, `crystal_units`, and `gas_units`.
* [ ] Convert the three resource values from strings into integers before performing calculations.
* [ ] Calculate `total_units` for every asteroid by adding its ore, crystal, and gas units.
* [ ] Calculate `cargo_value` using the provided resource point values.
* [ ] Add `total_units` and `cargo_value` to each asteroid's processed data.
* [ ] Write the processed data to a new file named `output_asteroid_data.csv` without changing the original input file.
* [ ] Write the headers `asteroid_id`, `ore_units`, `crystal_units`, `gas_units`, `total_units`, and `cargo_value` to the output file.

The beginning of `output_asteroid_data.csv` should look similar to:

```csv
asteroid_id,ore_units,crystal_units,gas_units,total_units,cargo_value
AST-001,42,18,27,87,255
AST-002,15,33,21,69,258
```

> Fully completing the Basic Requirements earns **16/20 marks, or 80%**.

## Basic Assessment — 16 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| Reading CSV Data | Uses the `csv` module to read the provided file and process every asteroid row. | 2 |
| Using Headers | Correctly accesses the asteroid data using the provided CSV headers. | 2 |
| Numeric Processing | Converts the resource values to integers and correctly calculates `total_units`. | 3 |
| Cargo Value | Correctly calculates `cargo_value` using the provided ore, crystal, and gas values. | 3 |
| Updating Row Data | Adds both calculated values to the correct asteroid data. | 2 |
| Writing the Output File | Creates `output_asteroid_data.csv` without overwriting the original input file. | 2 |
| Output Headers | Writes all six required headers and preserves the original asteroid data in the output. | 2 |
|  | **Total** | **16** |

## Advanced Premise

Extend your Basic program so that it can add new asteroids to the existing dataset and then regenerate the processed output.

The program should still process `input_asteroid_data.csv` using the same calculations from the Basic activity, but it should also allow the user to add new asteroid records before the program finishes.

The program should always process the input file at least once, even if the user chooses not to add any new asteroids.

After processing the existing data, the program should ask:

```text
Would you like to add another asteroid? (yes/no):
```

If the user enters `yes`, the program should ask for the new asteroid's:

- Asteroid ID
- Ore units
- Crystal units
- Gas units

The new asteroid should be added to `input_asteroid_data.csv`, and `output_asteroid_data.csv` should then be updated so that it includes the newly added asteroid and its calculated `total_units` and `cargo_value`.

The program should then continue to ask whether another asteroid should be added until the user enters `no`.

If the user enters `no`, the program should exit safely.

## Advanced File Structure

Your starter folder will contain:

```text
advanced/
├── main.py
└── input_asteroid_data.csv
```

After the program runs, the folder should also contain `output_asteroid_data.csv`.

Any new asteroid records should remain saved in `input_asteroid_data.csv`.

## Advanced Requirements

* [ ] Process `input_asteroid_data.csv` and create or update `output_asteroid_data.csv` at least once every time the program runs.
* [ ] After processing the data, ask the user whether they want to add another asteroid.
* [ ] If the user chooses to add an asteroid, collect an asteroid ID, ore units, crystal units, and gas units using `input()`.
* [ ] Validate the entered resource values so only valid numeric values are accepted, and prevent expected input errors from crashing the program.
* [ ] Add the new asteroid as a new row in `input_asteroid_data.csv` without removing the existing asteroid records.
* [ ] Reprocess the asteroid data after each new asteroid is added so `output_asteroid_data.csv` includes the new asteroid's `total_units` and `cargo_value`.
* [ ] Continue asking whether another asteroid should be added until the user enters a valid `no` response.
* [ ] Validate the yes/no response and allow the user to correct invalid responses. When the user chooses `no`, exit the program safely.

For example:

```text
Processing asteroid data...

Would you like to add another asteroid? (yes/no): yes

Enter asteroid ID: AST-031
Enter ore units: 40
Enter crystal units: 20
Enter gas units: 10

Asteroid added.
Output data updated.

Would you like to add another asteroid? (yes/no): no

Program finished.
```

If the user immediately chooses not to add an asteroid:

```text
Processing asteroid data...

Would you like to add another asteroid? (yes/no): no

Output data updated.

Program finished.
```

`output_asteroid_data.csv` should still have been created or updated using the existing input data so that running the program again does not erase previously added asteroids from the file.

## Advanced Assessment — 4 Marks

| Assessment Item | Criteria | Marks |
|---|---|---:|
| Initial Processing | Processes the existing input data and creates or updates the output file before requiring any new asteroid input. | 1 |
| Adding Asteroids | Collects new asteroid data and correctly appends each new record to `input_asteroid_data.csv`. | 1 |
| Updating Processed Data | Reprocesses the dataset after additions so `output_asteroid_data.csv` includes all existing and newly added asteroids with the required calculations. | 1 |
| Validation and Safe Exit | Validates numeric and yes/no input, handles expected errors without crashing, continues accepting asteroids as requested, and exits safely when the user chooses `no`. | 1 |
|  | **Total** | **4** |