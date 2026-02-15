# obsTools
Jupyter notebooks of LBT observing planning tools.

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

MODS field visualization and blind offset star calculation uses `astroquery.gais` and the Gaia TAP+ database. 
Our code is based in part on the Gaia Archive tutorial that uses the Gaia TAP+ 
(http://astroquery.readthedocs.io/en/latest/gaia/gaia.html#module-astroquery.gaia)

