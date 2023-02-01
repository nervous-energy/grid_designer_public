# Grid Designer Public -- COMING SOON
Public Repo for Grid Designer Web App

##Contains main business logic for the app.

The code allows you to specify a grid design, and then test it against demand data for an entire year.
For every hour of the year the sim:

1. Calculates energy output from nuclear power
2. Uses weather data to compute the energy output from the grid's renewables.
3. Uses these values to attempt to meet the power demand.
4. If there is an energy shortfall, the grid will attempt to use any storage power available.
5. If demand still can't be met, it is assumed the gap will be made up by fossil fuels.
6. When there is a surplus of energy the excess is used to recharge any grid batteries.

**The sim outputs:**
- Hourly output data by source (Solar, Onshore Wind, Offshore Wind, Nuclear, Fossil Fuels) -- GROUPED BY DAY
- The number of hours of "green uptime" per day -- that is, hours where no fossil fuels were required.
- Attempts calculates the **effective** contributio to the grid by each source.
- The % of green uptime for the year.
- The total CO2 released in a year
- The build and estimated yearly operating costs for the designed grid (excluding fossil fuels)


##Limitations
- Due to the licensing of some of the reference sources used by the app, these cannot be included.
- In general, the sim makes very favourable assumptions about renewables.
- Solar power outputs are computed using a monthly average reference source, rather than daily data.
- Solar power makes no account of weather conditions and always assumes optimal, cloudless days
- Wind Turbine power curves are modelled using a simplifed straight-line approach.
- Wind Turbine output assumes turbines can turn into the wind immediately, wake effects are not counted.
- High speed wind gusts that cause turbines to brake are ignored.


In the web app, all of these calculations are being done on the client.

*This software and its defaults have been tuned to the UK, but could be used anywhere*
