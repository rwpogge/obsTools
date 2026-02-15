# obsTools
Jupyter notebooks of LBT observing planning tools.

## Tools

### `BlindOffsetCalc`

Jupyter notebook to identify candidate blind offset reference
stars for a target. Uses the Gaia catalog to provide high-precision
star positions including proper motion corrections.

### `LBT_visCalc`

Jupyter notebook to make target visibility plots for the LBT on
a giving observing night, including nightly circumstances (sunset/rise,
moonrise/set, twilight, etc.).

### `modsADRCalc`

Jupyter notebook to compute atmospheric differential refraction (ADR)
effects for MODS targets.  Plots the ADR effect given a particular
slit, position angle, and range of hour angles.  Helps to visualize
the importance of ADR for a given target to plan for orienting the
slit along the parallactic angle at mid-exposure.

### `modsPlan`

EXPERIMENTAL observing planning tool for MODS that uses the Gaia
catalog to identify likely guide stars and blind offset stars for
a target.

Current state is a "sandbox" for working out the steps needed for
a possible way to select guide stars when setting the optimal slit
position angle on the fly.


## Dependencies

### astropy

Source: https://www.astropy.org/

Most of these notebooks reply on modules from the `astropy` project:
 * `astropy.coordinates`
 * `astropy.units`
 * `astropy.time`
 * `astropy.visualization`
   
### thorsky

Source: https://github.com/jrthorstensen/thorsky

Visibility planning tools use John Thorstensen's `thorsky` package. `thorsky` is built on `astropy.coordinates`,
`astropy.time`, and `astropy.units` and comprises of two classes, `thorskyclasses3` and `thorskyutil`, the latter 
of which uses faster but sufficiently accurate versions of analgous functions from `astropy.coordinates` that are 
high-precision but slow (LST, moon and sun  positions, and barycentric calculations). We don't need high precision f
or this type of calculation.

Other dependences are `dateutils` and `pytz` which come with the Anaconda distro so should be transparent.

**Note**: it needs `astropy` 5.2 or later as a bug in 5.1 kills this package at initialization.

See the `thorsky` documentation if you need to dig deeper, change the observatory site, etc.

### astroquery

Source: https://astroquery.readthedocs.io/en/latest/

MODS field visualization and blind offset star calculation uses `astroquery.gaia` and the Gaia TAP+ database. 
Our code is based in part on the Gaia Archive tutorial that uses the Gaia TAP+ 
(http://astroquery.readthedocs.io/en/latest/gaia/gaia.html#module-astroquery.gaia)

