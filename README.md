# time-to-full
time to full guage for venus os large node red dashboard

this is a pretty basic flow I created to create a guage on the node red dashboard in venus os large, to show the calculated time to full when charging the battery bank. For lithium batteries, which have a fairly flat charging curve, this will be fairly close to accurate. For lead acid or agm chemistries, the charging curve drops off pretty rapidly the closer they get to full, so the results will be less accurate the higher the soc.

some configuration will be neccesary. Settings and how to adjust them can be found in the comment nodes as follows:
 
 1. Set full SOC: Set the value to the desired SOC when considered full. For most this will be set to 100.
 2. Set multiplier: this value will be equal to 1% of the battery bank amp hr capacity. For example, if you have a 400ah bank, then this setting would be 4
 3. Set charge efficiency: for most lithium batteries this will be around 1.04. Lead acid are usually around 1.24. AGM may be slightly lower around 1.20. Use the value provided by your battery manufacturer.
 4. Set averaging time: set this value to the amount of time you would like the flow to output a calculated result. Calculations are constantly being fed to the averaging node, the amount of time (in seconds) that you set here determines how many sets of calculation arrays are averaged to produce the result on the dashboard.
 
 when the battery bank is fully charged (100% soc) or there is no charge current into the batteries, the guage will read zero.
