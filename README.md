# MFA_SEA_vehicles_model
For using the model, please download all files into the folder that you use to run your python programs. 
The file open the file 'MFA_SEA_model_supplementary_python' and run it first form line 1-181 and then run the second part. 
For running different scenarios, please activate the scenario name you would like to use, e.g., 
in the following 8 lines, scenario S70 is activated, which means that the vehicle outflows from the use stock will be used according to scenario S70.
Similar procedure has to be employed for the vehicle inflows to the use phase and the component outflows from the use phase that are both indicated in the same format.

1  #################################
####################################
outflow_df = S70_out          #1
#outflow_df = S100_out         #2
#outflow_df = S70D_out         #3
#outflow_df = S70D_CE_plus_out #4
#outflow_df = S100D_CE_plus_out #5
####################################

For using changes in recycling rates or the degree of component reuse, you will need to change values in the following passage. 
As an example, if you change the year from 2052 to 2025 the improved transfer-coefficients (improved recycling) will be employed from the year 2025. 
As the program runs only until the year 2050, setting 'if year < 2052' means that no improvements will be employed in relation to the transfer-coefficients.
By the 'ev_battery_r' or 'ev_motors_r' the transfer-coefficients will be directly changed from the specific year onwards.

#recycling rates for components (diversion to recycling processes)
        try:
            if year < 2052: #2025
                ev_battery_r = 0.45 
                ev_motors_r = 0.45  
                other_powertrain_to_other_powertrain_components = 0.45
                other_powertrain_to_regulated_components = other_powertrain_to_other_powertrain_components   #has to sum to one
                other_powertrain_to_dismantled_elvs = (1-(other_powertrain_to_regulated_components + other_powertrain_to_other_powertrain_components))

...

Similarly, the code has to be adapted accordingly for the recycling rates for components and the component diversion rate that is also described in the python code.

#recycling rates for components (diversion to recycling processes)
        try:
            if year < 2052: #2025
                ev_battery_r = 0.45 
                ev_motors_r = 0.45  
                other_powertrain_to_other_powertrain_components = 0.45
                other_powertrain_to_regulated_components = other_powertrain_to_other_powertrain_components   #has to sum to one
                other_powertrain_to_dismantled_elvs = (1-(other_powertrain_to_regulated_components + other_powertrain_to_other_powertrain_components))

In the case of questions, please let me know, writing to alexej.parchomenko@outlook.de

kind regards, 
Alexej Parchomenko
