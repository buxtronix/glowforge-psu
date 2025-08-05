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

A lot of basic teardown information can be found in [this post]
(https://community.openglow.org/t/reverse-engineering-pr0n/242)
from Scott.

The power supply is a custom unit which provides several voltages
required by the machine:

 * 3.3v for logic and control board.
 * 12v for various accessories (pump, fans, motors, etc)
 * 40v for highwer power components (more fans, peltier perhaps?)
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

TODO: Add part numbers for connectors and cables

## HV circuit description

TODO: Describe HV principle, operation and parts.

## HV circuit troubleshooting

## Testing the supply

TODO: Add kicad design for breakout board.

TODO: Add info on extending cables outside the GF machine.

