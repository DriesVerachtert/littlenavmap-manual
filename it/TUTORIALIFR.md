## Building an IFR Flight Plan with Approach Procedures {#tutorial-ifr}

This tutorial will show you how to create a more complex IFR flight plan including approach procedures. It introduces the advanced airport search functionality and the automatic flight plan calculation.

While this tutorial looks quite lengthy it is normally a matter of half a minute to get a flight plan if you know where to go. The planning effort shown here is bigger to highlight some of the more advanced features of the program.

You should at least read through the VFR tutorial [Building a VFR Flight Plan](TUTORIALVFR.md).

The flight plan will go across the UK using an IFR capable aircraft. Its maximum range should be more than 600 nautical miles including reserves and a cruise altitude of 10,000 feet.

I will not go into detailed fuel planning procedures in this tutorial. That is another story for another time.

The tutorial assumes the following preconditions:

* You left your aircraft at `Bembridge (EGHJ)` at the end of the last flight or treat this as you home base.
* You don't know where you want to fly today.
* You know the requirements for your aircraft:
 * Range
 * Minimum runway length
 * Hard runways
 * Need a parking spot at the destination
 * Fuel for flying back

### Cleanup Search {#tutorial-ifr-cleanup}

Go to the dock window `Search` and follow the steps below:

* Right click into the result table and select `Reset Search` ![Reset Search](../images/icons/clear.png) to get rid of all search criteria that may affect the query.
* Click the menu button  ![Menu Button](../images/icons/menubutton.png) and make sure that the search groups `Facilities`, `Runway`, `Parking` and `Distance from Mark` are checked. Deselect all others you don't need.

![Prepare Search](../images/tutorial/ifrsearchprep.jpg)

### Assign Departure {#tutorial-ifr-assign-departure}

Now look for the departure airport:

* Enter `EGHJ` in the `ICAO Code` search field on the top left \(case does not matter\).
* Right click on the airport in the result table.
* Choose `Set as Flight Plan Departure` ![Set as Flight Plan Departure](../images/icons/airportroutestart.png). This will assign a default runway as a start position.

![Assign Departure](../images/tutorial/ifrseldeparture.jpg)

Your flight plan has one entry now. This is already sufficient if you want to fly a pattern and like to see distance, speed and time information to the airport.

Starting from a runway is not quite realistic. Let's select a parking position:

* Go to `Flight Plan` -&gt; `Select a Start Position for Departure` ![Select a Start Position for Departure](../images/icons/parkingstartset.png).
* Choose one of the GA small ramp positions.
* Click `Ok` and the position will be highlighted on the map.

![Assign Parking](../images/tutorial/ifrselparking.jpg)

Alternatively you can also select the start position directly on the map's context menu as described in the [VFR tutorial](TUTORIALVFR.md).

See also [Set as Flight Plan Departure](MAPDISPLAY.md#set-as-flight-plan-departure)

### Search for Destination {#tutorial-ifr-search-dest}

Now look for a suitable destination airport:

* Right click on `EGHJ` in the search result again.
* Select `Set Center for Distance Search` ![Set Center for Distance Search](../images/icons/mark.png). You can also do this in the map. This is the center point for the spatial search.
* Clear the `ICAO Code` search field now \(it is a common mistake to leave the text fields filled when doing distance searches which will give you an empty result table\).

We will now look for airports that are in range of the aircraft but not too close. Also, certain criteria have to be fulfilled, like having parking spots that fit the aircraft and a runway which is long enough.

You can also find airports in aircraft range by using the range rings where you can right click into the map on your departure airport and select `Show Range Rings` ![Show Range Rings](../images/icons/rangerings.png), although this function does not allow the detailed airport filters.

We will use the spatial search instead of range rings since we'd like to see only suitable airports for out aircraft.

Check the following in the airport search tab:

1. `Rating`: We'd like to get airports that are either add-ons or have basic scenery requirements, like taxiways, parking spots and more. Everything else is boring.
2. `Procedures`: Show only airports that have procedures to spice up the approach a bit.
3. Deselect `Military` and `Closed` \(click the checkboxes twice\): This will return only civilian airports and avoid airports that have all runways closed.
4. Also check `Avgas` so we can fill up for our return trip and don't have beg for fuel at a nearby road.
5. In the combo box `Any or no Ramp` select `At least Ramp GA small`. This will include only airports in the result that have suitable parking spots.
6. In the combo box `Any Surface` select `Any is Hard` to avoid airports having only soft surfaced runways.
7. Select a minimum runway length of 2,500 feet for your aircraft in the field `Runways:` `Min:`.

See also [Search Dock Window - Airports and Navaids](SEARCH.md).

You can also limit the maximum runway length if you are looking for a short landing challenge, but not now.

The search result changes on the fly while doing all these adjustments, though we are not there yet:

* Check `Distance:` to activate the spatial search.
* Change the maximum distance to 600 and the minimum to 400 nautical miles \(to avoid short hops\). The result table will now update with a small delay since the distance search is more complex.
* To find only airports north of your position select `North` in the combo box `Any Direction`. Note that the search result is sorted by distance with the closest airport first.
* Choose an airport for your trip. We use `Wick (EGPC)` for this tutorial.
* ![Search for Destination](../images/tutorial/ifrsearchdest.jpg)
* Right click on Wick in the result table.
* Select `Show Information` ![Show Information](../images/icons/globals.png). This will fill the tabs in the dock window `Information`.
* Select the tab `Weather` and look for the wind direction to get an idea of the expected landing runway. Start AS16 or Active Sky Next if you are using these.

For this tutorial we assume that the winds favor runway 13.

See also [Weather](WEATHER.md).

### Select an Approach Procedure {#tutorial-ifr-select-approach}

We'll select an approach procedure now:

* Go back to the search result.
* Right click on the airport Wick again. Select `Show Procedures` ![Show Procedures](../images/icons/approach.png). This will pop up the procedure search tab.
* Choose `Runway 13` in the `All Runways` combo box to see only approaches for 13.
* Select `Expand All` in the context menu to see also the transitions for each approach.
* Choose `Approach VORDME 13 FD13` using `Transition (Full) WIK10` since we expect to land on runway 13 and arrive from south.

The top label in the procedure search shows `Wick (EGPC) Approach VORDME 13 FD13 Transition (Full) WIK10` for the selected approach and/or transition. You can also see a preview on the map.

![Procedure Search Tree](../images/tutorial/ifrprocselect.jpg)

Right click on the transition and select `Show Approach and Transition on Map` ![Show Approach and Transition on Map](../images/icons/showonmap.png). This will center the procedure on the map. You can hover the mouse over the waypoints of the approach to see more information in a tooltip. You can also click on the legs in the procedure tree to see the respective start and end points.

![Procedure Preview](../images/tutorial/ifrprocpreview.jpg)

The procedure looks sufficiently complicated to make an interesting approach.

More information on procedure search: [Search Dock Window - Procedures](SEARCHPROCS.md). Also see [Procedures](APPROACHES.md) for general information on procedures.

If you like what you see right click again on the transition and select `Use EGPC and Approach and Transition as Destination` ![Use EGPC and Approach and Transition as Destination](../images/icons/routeadd.png).

This will do two things:

1. Add Wick as the destination airport to the flight plan. Any previous destination in the flight plan will be replaced.
2. Add the approach and its transition to the flight plan. The procedure legs use a dark blue color and the missed approach legs use a dark red color in the flight plan table. Flight plan en route legs are black. Again, any previous procedure is replaced with this new one.

**About adding transition and approaches:** Approaches and transitions are closely related which is already indicated by the tree structure in the procedure search tab. You can add an approach alone but a transition always belongs to an approach.

You have to select the transition to add or show both, approach and transition.

### Calculate a Flight Plan {#tutorial-ifr-calculate-flight-plan}

Now we have the departure airport, an approach procedure and the destination all connected by a line. Next is the en route part of the flight plan:

* Set `IFR` as the flight plan type in the dock window `Flight Plan`. This allows the automatic flight plan calculation to adjust the cruise altitude.
* Click `Flight Plan` -&gt; `Calculate low Altitude` ![Calculate low Altitude](../images/icons/routelow.png) to start the automatic flight plan calculation for Victor airways. The calculation will create a route from your departure airport to the intial fix of the transition.

The flight plan cruise altitude is automatically adjusted according to the hemispherical rule \(the rule can be changed in `Tools` -&gt; `Options` ![Options](../images/icons/settings.png) on the tab `Flight Plan`\), the altitude restrictions of the airways and the flight plan type \(`VFR` or `IFR`\). You can see the minimum altitude for each airway segment in the flight plan table in the column `Restriction`.

The altitude can also be adjusted according to the hemispherical rule by clicking `Flight Plan` -&gt; `Adjust Flight Plan Altitude` ![Adjust Flight Plan Altitude](../images/icons/routeadjustalt.png).

Now the minimum altitude of 16,000 feet is a bit too high.

Therefore, try an alternate calculation method which limits your cruise altitude:

* Enter 10,000 feet in the `Flight plan altitude` field.
* Click on `Flight Plan` -&gt; `Calculate based on given Altitude` ![Calculate based on given Altitude](../images/icons/routealt.png). This will result in a flight plan that uses only airways having a minimum altitude below or equal to 10,000 feet. Note that you can get a mix of Victor and Jet airways depending on used altitude. The calculation might also fail if you set the cruise altitude too low.

![Calculate Flight Plan](../images/tutorial/ifrcalcalt.jpg)

Use this flight plan for now.

Save the plan using `File` -&gt; `Save Flight Plan` ![Save Flight Plan](../images/icons/filesave.png). The program usually finds the right directory for the flight plans and gives a sensible name by default.

The waypoints of the approach procedure are not saved in the flight plan. You have to select the approach in your GPS or FMC in the simulator or fly it by radio navaids and a stopwatch.

What _Little Navmap_ saves in the PLN are the procedure names which allows the program to restore the approach when loading the PLN file.

The top label in the flight plan dock window reads now:

```none
Bembridge (EGHJ) Parking 1, Ramp GA Small to Wick (EGPC)
Via WIK10 and VORDME FD13 to runway 13
517 nm, 5 h 10 m, Low Altitude
```
Adjust the ground speed in the flight plan dock window according to the used aircraft to get a better time estimate.

The plan might look different, depending if you use stock navaids or navdata updates.

![Flight Plan](../images/tutorial/ifrflightplan.jpg)

Now you can check if you pass through any airspaces:

* Enable airspaces by selecting `Map` -&gt; `Airspaces` -&gt; `Show Airspaces` ![Show Airspaces](../images/icons/airspace.png) if not already done.
* Check `Map` -&gt; `Airspaces` -&gt; `At flight plan cruise altitude` ![At flight plan cruise altitude](../images/icons/airspaceroutealt.png) in the menu or the toolbar menu button.

![Select Airspaces](../images/tutorial/ifrairspacesel.jpg)

This will display only airspaces on the map that are relevant for your cruise altitude. You can also select `Below 10000 ft only` to see all relevant airspaces in the climb or descent phase. Use the tooltips on the map to get information about airspaces like type, minimum and maximum altitude.

![Airspaces](../images/tutorial/ifrairspaces.jpg)

### Flying {#tutorial-ifr-flying}

Open the dialog `Connect` using `Tools` -&gt; `Flight Simulator Connection` ![Flight Simulator Connection](../images/icons/network.png) and check if `Connect automatically` is selected. Enable, if not.

_Litte Navmap_ will find the simulator no matter if it is already started or if it is started later. Click `Connect`.

See also [Connecting to a Flight Simulator](CONNECT.md).

Enable `Map` -&gt; `Center Aircraft` ![New Flight Plan](../images/icons/centeraircraft.png). The map will jump to the simulator aircraft and keep it centered. This will happen only if an active flight is loaded, i.e. the simulator is not in the opening screen.

Start the simulator if not already done, load the flight plan and go flying.

### Top of Descent {#tutorial-ifr-top-of-descent}

A top of descent indication is displayed on the map and in the elevation profile which also shows the distance from top of descent to the destination. This number includes the distance of approach procedures \(excluding holds\).

Note that altitude restrictions are not considered yet in the top of descent calculation.

You can change the descent rule in `Tools` -&gt; `Options` ![Options](../images/icons/settings.png) on the tab `Flight Plan`. The default is 3 nautical miles for 1,000 feet.

![Top of Descent Indicator](../images/tutorial/ifrtod.jpg)

The tab `Progress` in the dock window `Simulator Aircraft` will show the distance to the top of descent in the `Flight Plan Progress` section:

|Flight Plan Progress|
|---|---|
|To Destination: |74 nm|
|Time and Date: |21.05.17 12:33 UTC|
|Local Time: |14:33 CEST|
|**TOD to Destination:**|**64 nm**|
|**To Top of Descent:**|**10,1 nm**|

The section `Altitude` will show the vertical path deviation after passing the top of descent:

|Altitude|
|---|---|
|Indicated: |5,090 ft|
|Actual: |5,051 ft|
|Above Ground: |5,051 ft|
|Ground Elevation: |0 ft|
|**Vertical Path Dev.:**|**-511 ft below ▲**|

### Changing Procedures {#tutorial-ifr-changing-procedures}

Now the weather has changed requiring an approach to runway 31:

* Right click on the destination airport at the bottom of the flight plan table.
* Choose `Show Procedures` ![Show Procedures](../images/icons/approach.png).
* Then change the runway filter to `Runway 31`.
* Expand the approach VORDME 31 to see the transition.
* Select the transition.

The label on top of the window shows now `Approach VORDME 31 FD31 Transition (Full) CHINN`.

* Right click on the selected transition.
* Choose `Use EGPC and Approach and Transition as Destination` ![Use EGPC and Approach and Transition as Destination](../images/icons/routeadd.png) from the context menu which will replace the current procedure in your flight plan with the new one.

The top label in the flight plan dock window reads now:

```none
Bembridge (EGHJ) Parking 1, Ramp GA Small to Wick (EGPC)
Via CHINN and VORDME FD31 to runway 31
526 nm, 5 h 15 m, Low Altitude
```

To completely get rid of a procedure:

* Select any leg of the procedure in the flight plan table.
* Right click and choose `Delete selected Leg or Procedure` ![Delete selected Leg or Procedure](../images/icons/routedeleteleg.png) to remove the whole procedure. Alternatively press the `Del` key.

If ATC clears you to the initial fix of the procedure:

1. Delete any intermediate waypoints between your current aircraft position and the initial fix of the procedure: Right click in the flight plan table and select `Delete selected Leg or Procedure` ![Delete selected Leg or Procedure](../images/icons/routedeleteleg.png) for all waypoints between your current aircraft position and the initial fix or start of the procedure. Avoid deleting your approach \(you can also right click on a flight plan waypoint on the map and delete it from the context menu\).
3. Then right click on your aircraft on the map and select `Add Position to Flight Plan` ![Add Position to Flight Plan](../images/icons/routeadd.png).

This will give a direct connection from your current aircraft position to the start of the procedure which you can use to get course and distance to the intial fix.

Below: After changing the approach procedure and adding a user defined waypoint at the aircraft position to the flight plan. Now we get course and altitude indications for a direct leg to the start of the transition \(43 nm and 314 degrees magnetic course\).

![Changed Approach](../images/tutorial/ifrapproach.jpg)

### Going Missed {#tutorial-ifr-going-missed}

I recommend hiding the missed approaches on the map by unchecking `Map` -&gt; `Show Missed Approaches` ![Show Missed Approaches](../images/icons/missed.png "Show Missed Approaches"). This helps uncluttering the map display.

* **If the missed approach is not shown:** The progress window shows distance and time to destination. Activating the next leg \(shown in magenta color\) will stop if the destination \(i.e. the runway threshold\) is reached, even when passing the threshold.
* **If the missed is shown and the aircraft passes the runway threshold:**  The first leg of the missed approach is activated and simulator aircraft progress will display the remaining distance to the end of the missed procedure.
