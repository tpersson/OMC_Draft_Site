# The Beta-Beat GUI Optics Panel

The `Optics Panel` provides graphical interface to compare the computed optics to the nominal model.
There are in total three main tabs for the optics panel:

- The [Optics](#Optics Tab) tab, where a tree menu (on the left) provides many physical properties to be displayed.
- The [Segment-by-Segment: Segment](#Segment-by-Segment: Segment Tab) tab, to have a look at properties in a pre-defined segment of the machine.
- The [Segment-by-Segment: Element](#Segment-by-Segment: Element Tab) tab, to have a look at properties for a pre-defined list of elements in the machine.

## Optics Tab

By default, the user is taken to the `Optics` tab.
A wide variety of computed physical properties can be visualized across the entire machine.

!!! todo
    Include a screenshot with the main optics tab.

## Segment-by-Segment: Segment Tab

A list of pre-defined segments of the machine can be selected to view properties across said segment.

!!! todo
    Include a screenshot of segment selection.

In the event that one wants to visualize a specific, non pre-defined segment, it is possible to create a new one.
To do so:

- In the `Optics` tab, pick the start BPM by clicking on a BPM point on the optics chart.
- Pick the end BPM by clicking on another BPM point.
- A pop-up appears in which the name of the new segment has to be entered.

!!! todo
    Include a screenshot of the new segment creation dialogue.

Clicking `Go` will call for another python script and take you to the `Segment-by-Segment` tab to view the results.

## Segment-by-Segment: Element Tab

Pre-defined lists of elements can be selected to view properties across said elements.
The working is similar to the one for different [segments](#Segment-by-Segment: Segment).

!!! todo
    Include a screenshot of the element tab.

## Computing Corrections

The `Correction` button at the bottom left of the optics panel can be used to calculate the optics corrections for the beam process.

The settings dialogue offers a wide range of different options for corrections.
This will call different external python scripts again.

These scripts calculate corrections for beta-beat, coupling and horizontal and vertical dispersion using the computed response matrices.
The following methods implement different correction algorithms:

- `Coupling`: Single beam correction of coupling resonances and vertical dispersion.
- `Global correction`: Single beam correction of phase, beta and horizontal dispersion.
- `Iterative correction`: Two-beams version of the global correction.
- `Chromatic coupling`: Single beam correction of chromatic coupling using skew sextupoles at dispersive locations.

??? note
    The `Iterative correction` method is currently not compatible and thus disabled.

The results are outputted in the `changeparameters` files.
These files store the magnet names and corresponding correction strengths.

They are also displayed in the [Correction Panel](correction_panel.md).