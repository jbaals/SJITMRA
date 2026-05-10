# Instances for "Optimal assignment of shipments to milk-runs for just-in-time part supply under uncertain due dates"

This repository contains 70 computational instances used in the research article: 
*"Optimal assignment of shipments to milk-runs for just-in-time part supply under uncertain due dates"* by Julian Baals, Simon Emde, and Ola Jabali.

## Repository Structure

The instances are organized into folders based on the number of shipments:
* `shipments_120`: Instances containing 120 shipments.
* `shipments_120_2`: Instances containing 120 shipments (includes only CRS and RRS route sets).
* `shipments_400`: Instances containing 400 shipments.

## JSON File Schema

Each `.json` file is structured as follows:

### `suppliers` (Array)
An array of `supplier` objects, each containing:
- **`id`**: Unique identifier for the supplier.
- **`shipments`** (Array): Detailed shipment information. Each object includes:
    - **`id`**: Identifier for the shipment.
    - **`capDemand`**: The capacity demand of the shipment.
    - **`dueDate`** (Array): The due date for the shipment across different scenarios.
    - **`earlinessCpTU`**: Earliness cost per time unit.
    - **`tardinessCpTU`**: Tardiness cost per time unit.
    - **`reschedulingCosts`**: The cost of rescheduling (independent of the scenario).
- **`timeWindows`** (Array): *Not used in the paper.*
- **`earlinessCpTU`**: *Not used in the paper.*
- **`tardinessCpTU`**: *Not used in the paper.*

### `travelTimes` (Array)
Contains travel times between suppliers. 
*(Note: This is used for instance generation only and is not part of the model solved in the paper).*

### `probabilities` (Array)
The probability associated with each scenario.

### `routeSets` (Array)
An array containing different sets of routes:
- `routeSets[0]`: CRS instances.
*   `routeSets[1]`: RRS instances.
*   `routeSets[2]`: MRS instances.
*(Note: The `shipments_120_2` folder only includes CRS and RRS).*

**Route Definition:** Each route is a tuple `(item1, item2)` where:
- `item1`: A reference to a time window index from the top-level `timeWindows` attribute.
- `item2`: An array with references to supplier IDs (`suppliers.id`).

### `timeWindows` (Array)
Defines the `start` and `end` timestamps for each time window.

## Instance Mapping Reference

To map instances mentioned in the paper to the files in this repository:
- **Paper Instance** `Shipment120-{CRS, MRS, RRS}-0` $\rightarrow$ **File** `instances_shipments_120_0_instance.json`
- **Paper Instance** `Shipment120-{CRS, MRS, RRS}-1` $\rightarrow$ **File** `instances_shipments_120_1_instance.json`
*(and so on...)*

- **Paper Instance** `Shipment120-RRS-10` $\rightarrow$ **File** `instances_shipments_120_2_0_instance.json`
- **Paper Instance** `Shipment120-RRS-11` $\rightarrow$ **File** `instances_shipments_120_2_1_instance.json`
*(and so on...)*

- **Paper Instance** `Shipment400-{CRS, MRS, RRS}-0` $\rightarrow$ **File** `instances_shipments_400_0_instance.json`
- **Paper Instance** `Shipment400-{CRS, MRS, RRS}-1` $\rightarrow$ **File** `instances_shipments_400_1_instance.json`
*(and so on...)*