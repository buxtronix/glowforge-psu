# Documenting the Glowforge Power Supply

This repository aims to contain a collection of information on the
power supply within the Glowforge Pro.

These power supplies frequently fail, and there is little documentation
that can assist when trying to repair them.

[Scott Wiederhold](https://community.openglow.org/u/scottw514/summary) has
done a remarkable job at trying to reverse engineer the GF in order to
produce an Open Source replacement controller and his
[OpenGlow forum](http://community.openglow.org/) contains a lot of
photos, teardowns and information.

I have been trying to repair a broken power supply myself, and wanted
to combine a bunch of information from various posts, as well as what
myself and others found.

> [!CAUTION]
> This information involves working with lethal voltages (400-22,000 volts)
> and high power laser radiation!
> It is intended only for people who are sufficiently experienced in
> working with high voltage electronics and understand the necessary
> precautions.

> [!WARNING]
> The information contained here is provided on a "best effort" basis
> and is not guaranteed to be accurate. Consider this information to
> be a starting point where you should then use your best judgement
> and double checks before relying on anything.

## References

Some links to relevant information, mostly on OpenGlow:

 * [Teardown of power components](https://community.openglow.org/t/reverse-engineering-pr0n/242/2)
 * [High voltage troubleshooting](https://community.openglow.org/t/laser-not-firing/680/2)
 * [Testing HV output](https://community.openglow.org/t/gf-not-fire-working-process/847/2)
 * [Analysis/photos of GF boards](https://community.openglow.org/t/list-of-ics-on-the-control-board/988)
 * [OpenGlow schematic](https://community.openglow.org/t/openglow-prototype-2-schematics/255)

## Extracting the supply

The power supply is quite difficult to get out, as it wedged into a tight
corner and attached using cables with very little slack.

Ken S has made [two](https://www.youtube.com/watch?v=dVIbavUEy1M)
[videos](https://www.youtube.com/watch?v=0B0-IHG0M_s) of the removal
process which is very involved and will probably take an hour.
At one point the machine is flipped upside down - take great care
to ensure the gantry is secure as you dont want it crashing to
one side during the flip.

## Basic information.

A lot of basic teardown information can be found in
[this post](https://community.openglow.org/t/reverse-engineering-pr0n/242)
from Scott.

The power supply is a custom unit which provides several voltages
required by the machine:

 * 3.3v for logic and control board.
 * 12v for various accessories (pump, fans, motors, etc)
 * 40v for higher power components (more fans, peltier perhaps?)
 * 12-22kV for the laser tube.

It also has some control signals which communicate over the ribbon
cable. The 12v, 40v, and HV outputs are only enabled when the right
control signals are set.

It's possible to control the PSU when outside the machine, per
[this post](https://community.openglow.org/t/gf-not-fire-working-process/847/2)

## Opening the PSU

Remove the screws attaching the top lid (where the ribbon cable and HV red
wire are).

Remove the panel on the side by undoing the 4 screws holding it on.

In that panel you can access two cable bundles between the top and bottom
boards. Unplug these from the bottom board.

Remove the top cover and attached board. Take care with the red and white
wires. The red HV wire has a grommet that splits apart when the cable tie
is removed.

The top board is screwed into the lid with 8 Phillips head screws. You will
need to use a driver with a thin shaft to remove the center one as there
is not much space. Be careful not to damage or crack the core of the
flyback transformer.

## Connectors

These are the connectors on the PSU. You could create extension cables in order
to run the machine with the PSU outside of it for testing.

__Molex mini-fit jr 6-way__ is the large 6-pin connector to the daughterboard [Digikey link](https://www.digikey.com/en/products/detail/molex/0766500076/2115933)
  
__TE Connectivity Economy 2.5 4 way__ is the smaller one next to it [Digikey link](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/1744417-4/4730270) [mating connector](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/1969588-4/5021426)

__Molex 30-way 1mm ribbon cable__ note top on on side bottom on the other [Digikey link](https://www.digikey.com/en/products/detail/molex/0152670468/4427333)

## HV circuit description

TODO: Describe HV principle, operation and parts.

## HV circuit troubleshooting

## Testing the supply

Using an appropriate dummy load and sending the right control signals,
the various outputs on the supply can be enabled for testing.

Scott has [a post](https://community.openglow.org/t/gf-not-fire-working-process/847/2)
covering this procedure.

Setting the various signals on the ribbon cable can be tricky. I designed a
breakout board which brings these connections into a regular header socket,
and also acts as a passthrough to the control board for verify operation
when installed.

Designs and Gerbers are [available here](breakout-pcb/).


TODO: Add info on extending cables outside the GF machine.

