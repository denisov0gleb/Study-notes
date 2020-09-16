# Shape2.1 #

Download free [Shape2.1 program](http://www.ee.ub.edu/index.php?option=com_jdownloads&view=viewcategories&Itemid=529)

<!-- vim-markdown-toc GFM -->

* [Input file structure](#input-file-structure)
	- [User defined reference shape](#user-defined-reference-shape)
	- [Most popular chemical polyhedrons](#most-popular-chemical-polyhedrons)
	- [Input examples](#input-examples)
		+ [Example 1](#example-1)
		+ [Example 2 with reference](#example-2-with-reference)
* [Output file](#output-file)
	- [Output examples](#output-examples)
		+ [Example 1](#example-1-1)
		+ [Example 2 with reference](#example-2-with-reference-1)

<!-- vim-markdown-toc -->

## Input file structure ##

Takes *.dat* file at input with max 40 characters file name.

Comment lines starts with `!` symbol.

`Spaces` and `tabs` are ignored.

| Field                    | Description                                                                              |
| ---                      | ---                                                                                      |
| Title *(optional)*       | Starts with `$` at the first column. Max 80 characters                                   |
| Comments *(optional)*    | Starts with `!`, can be placed anywhere.                                                 |
| Keywords *(optional)*    | One line for each keyword.                                                               |
| Size of polyhedron       | Two integer: number of vertices, central atom position or 0 if not exists.               |
| Reference polyhedra code | Up to 12                                                                                 |
| Data set                 | Starts with a label up to 15 characters. One line per atom with label up to 4 character. |


### User defined reference shape ###

The *.ref* file contains:
* abbrevation for the name of the ideal shape (<= 12 characters).
* a description line (<= 50 characters).
* symmetry label (<= 5 characters).
* coordinates of the vertices atoms. The central atom if present must **always be at the end**!


### Most popular chemical polyhedrons ###

| Vertices number | Code | Label   | Shape                               | Symmetry       |
| :---:           | ---  | ---     | ---                                 | ---            |
| **4**           | 1    | SP-4    | Square                              | D<sub>4h</sub> |
|                 | 2    | T-4     | Tetrahedron                         | T<sub>d</sub>  |
|                 | 3    | SS-4    | Seesaw or *cis*-divacant octahedron | C<sub>2v</sub> |
|                 | 4    | vTBPY-4 | Axially vacant trigonal bipyramid   | C<sub>3v</sub> |
| **6**           | 1    | HP-6    | Hexagon                             | D<sub>6h</sub> |
|                 | 2    | PPY-6   | Pentagonal pyramid                  | C<sub>5v</sub> |
|                 | 3    | OC-6    | Octahedron                          | O<sub>h</sub>  |
|                 | 4    | TPR-6   | Trigonal prism                      | D<sub>3h</sub> |
|                 | 5    | JPPY-5  | Johnson pentagonal pyramid (J2)     | C<sub>5v</sub> |


### Input examples ###

#### Example 1 ####

```
$ PtL4 structures
! Ligands	Metal
	4	5
! Tetrahedron	Square
	2	1
ABOXIY
N 3.9023 7.5659 14.2563
C 3.9912 8.8145 16.4883
S 1.0864 9.0325 13.3242
Cl 1.4893 10.6356 16.0313
Pt 2.7159 8.9642 15.0153
!ABZLPT10
! P 3.9891 1.7349 -5.9463
! N 2.5932 -0.3213 -2.3836
! N 3.9661 2.1385 -2.8787
! Cl 2.6450 -1.1044 -5.4688
! Pt 3.3098 0.6621 -4.0608
ACACPT
O 0.6294 1.3760 -1.2703
O -0.6294 -1.3760 1.2703
O -1.7613 0.9024 0.3486
O 1.7613 -0.9024 -0.3486
Pt 0.0000 0.0000 0.0000
```

#### Example 2 with reference ####

**Input file**: *example08.dat*

```
$ Cyclen complexes in cis conformation
%path
	6		5
	4		0
TUKWEB
N4	2.04091 3.92389 10.64074
N3	-0.83988 4.13831 10.95260
N1	2.23124 4.94238 13.37296
N6	2.07351 2.22997 13.43397
Zn1	0.62860 3.58403 12.61024
N5	-0.85563 1.90834 12.62380
N2	-0.64030 5.09248 13.74584
NAXJIF
N2	1.57673 0.92781 9.50033
N3	2.08309 1.65282 6.59555
N1	1.20034 3.81264 10.25045
N4	1.64134 4.56300 7.29441
Ag1	0.31080 2.65820 8.13611
S1	-1.91668 3.16393 9.58508
S3	-1.13006 1.56080 6.07099
```


**Ideal polyhedron file**: *example08.ref*

```
dvCU
Divacant cube
C2v
	0.000 0.000 0.000
	0.000 0.000 1.000
	0.000 1.000 0.000
	1.000 0.000 0.000
	1.000 1.000 0.000
	1.000 1.000 1.000
	0.500 0.500 0.500
```

## Output file ##

**Shape** generate *.tab* file

### Output examples ###

#### Example 1 ####

```
--------------------------------------------------------------------------------
S H A P E v2.1 Continuous Shape Measures calculation
(c) 2013 Electronic Structure Group, Universitat de Barcelona
Contact: llunell@ub.edu
--------------------------------------------------------------------------------
PtL4 structures
T-4 2 Td Tetrahedron
SP-4 1 D4h Square
Structure [ML4 ]	T-4	SP-4
	ABOXIY	,	31.375,	0.970
	ACACPT	,	33.440,	0.160
```

#### Example 2 with reference ####

**Output file**: *example08.tab*

```
--------------------------------------------------------------------------------
S H A P E v2.1 Continuous Shape Measures calculation
(c) 2013 Electronic Structure Group, Universitat de Barcelona
Contact: llunell@ub.edu
--------------------------------------------------------------------------------
Cyclen complexes in cis conformation
TPR-6 4 D3h Trigonal prism
dvCU 0 C2v Divacant cube
Minimal distorsion path analysis:
	from TPR-6 (0%) to dvCU (100%)
Deviation threshold to calculate Generalized Coordinate: 10.000%
Structure [ML6 ]	TPR-6	dvCU	DevPath	GenCoord
	TUKWEB	,	1.967,	3.699,	3.8,	43.7
	NAXJIF	,	6.955,	0.602,	7.0,	82.8
```

Other files generated: *example08.pth*, *example08.csv* (see Example 5 in manual).
