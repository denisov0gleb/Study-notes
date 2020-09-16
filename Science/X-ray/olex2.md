# Olex2 #

<!-- vim-markdown-toc GFM -->

* [Usage](#usage)
* [CIF](#cif)
* [Commands](#commands)
	- [Bonding information](#bonding-information)
	- [Molecule growing](#molecule-growing)
	- [Names, labels](#names-labels)
	- [Atom selection](#atom-selection)
	- [Cell and symmetry](#cell-and-symmetry)
* [Images](#images)
* [Keybindings](#keybindings)

<!-- vim-markdown-toc -->

## Usage ##

Open *.res* file.


## CIF ##

`twin` - search for twinning in centrosymentrical groups.

`basf 0.5` - **???**

`isor value` - **???**

`fvar` - link two or more atoms through a free variable (usually the chemical occupancy for different parts).

`omit -4 value` - omit any reflections with 2theta more than **value**.


## Commands ##

### Bonding information ###

`htab` - generate *.lst* file with main information + the D...A distance in the end (not
included in *cif* file).

`pipi` - print the distance between centers of the aromatic rings (centroid-to-centroid distance).

`esd` - print the distance between two selected atoms, including the error.


### Molecule growing ###

`pack #` - change packing parameter

`compaq` - moves all atoms or fragments of the asymmetric unit as close to each other as possible.


### Names, labels ###

`name type` - rename selected to the *type*

`name type1 type2` - rename *type1* to *type2*

`name -s=suffix` - rename selected suffixes.

`Legend` - show/hide legend

`labels` - show/hide labels

`labels -p` - show/hide parts

`showp value` - show only requested parts


### Atom selection ###

`envi r-2.7 atom` - print a list of atoms within a sphere of radius **r** around the atom (named or selected).

`-h` - including hydrogens

`-q` - including Q-peaks


### Cell and symmetry ###

cell - show/hide cell


## Images ##

`save model name` - generate *.oxm* file for image storage


## Keybindings ##

**<F3>** - show/hide labels

**Ctrl+R** - refine structure

**Ctrl+H* - toggle between show H, show H with internal h-bonds, hide H.

**Ctrl+T** - toggle between show structure only, structure + text, only text.

