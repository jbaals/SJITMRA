# Instances of the Research Article "Optimal assignment of shipments to milk-runs for just-in-time part supply under uncertain due dates"

This repository includes 70 instances, which where used in the computational study of the research article "Optimal assignment of shipments to milk-runs for just-in-time part supply under uncertain due dates" by Julian Baals, Simon Emde, and Ola Jabali.

The folders ´shipments_120´ and ´shipments_120_2´ include the instances with 120 shipments. The folder ´shipments_400´ includes the instances with 400 shipments.

The ´.json´-files are structures as follows

- an array called ´suppliers´, which includes ´supplier´-objects with the attributes
    - an ´id´ as identifier for the supplier
    - an array ´shipments´, which includes the information about the shipments. The ´shipment´-objects have the following structure
        - an ´id´ as identifier for the shipment
        - a ´capDemand´ corresponding to the shipment's capacity demand
        - an array ´dueDate´ for the due date of the shipment in each scenario
        - an earliness cost per time unit ´earlinessCpTU´
        - a tardiness cost per time unit ´tardinessCpTU´
        - a ´reschedulingCosts´ correspnding to the rescheduling cost of the shipment (independent from the scenario)
    - an array ´timeWindows´ (not used in the paper)
    - an earliness cost per time unit ´earlinessCpTU´ (not used in the paper)
    - a tardiness cost per time unit ´tardinessCpTU´ (not used in the paper)
- an array called ´travelTimes´, which includes travel times between the suppliers (only used for instance generation, not in the model solved in the paper)
- an array called ´probabilities´, which includes the probability of each scenario
- an array called ´routeSets´, which includes an array for each set of ´routes. routeSets[0]´ corresponds to the routes that are used in the CRS-instances, ´routes. routeSets[1]´ to the RRS-instances, and ´routes. routeSets[2]´ to the MRS-instances. Note that the folder ´shipments_120_2´ only includes CRS- and RRS-instances. Only the RRS-instances were used in the paper. Instance Shipment120-RRS-10 in the paper coresponds to instances_shipments_120_2_0_instance.json, Shipment120-RRS-11 to instances_shipments_120_2_1_instance.json and so on. A route is described by a tuple with
    - ´item1´ points to the time window in the files top level attribute ´timeWindows´, and
    - ´item2´ points to the suppliers id, (i.e., ´suppliers.id´).
- an array called ´timeWindows´, which includes the ´start´ and ´end´ of each time window.