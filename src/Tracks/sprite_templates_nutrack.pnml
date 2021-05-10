/* $Id$ */

/*
 * This file is part of the Swedish RailSet.
 * Swedish RailSet is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, version 2.
 * Swedish RailSet is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
 * See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with Swedish RailSet. If not, see <http://www.gnu.org/licenses/>.
 */

// Default ground tile template (re-use as needed)
template ground_tile(x, y) { [x, y, 64, 31, -31, 0, 9] }

// track_type underlays
template tmpl_underlay_straight() {
	[ 75,  0, 64,31, -31,   0]
	[  0,  0, 64,31, -31,   0]
}
template tmpl_underlay_slope() {
	[ 75, 40, 64,39, -31,  -8]
	[150, 40, 64,23, -31,   0]
	[225, 40, 64,23, -31,   0]
	[300, 40, 64,39, -30,  -9]
}
template tmpl_underlay_diagonal() {
	[150,  0, 64,31, -31,   0]
	[225,  0, 64,31, -31,   0]
	[  0, 40, 64,31, -31,   0]			
	[300,  0, 64,31, -31,   0]
}

template tmpl_underlay_track_types() {
	tmpl_underlay_straight()

	tmpl_underlay_diagonal()

	tmpl_underlay_slope()
	
	// x - crossing
	[  0,120, 64,31, -31,   0]
	
	// underlay for crossings w/o tracks
	[  0, 80, 64,31, -31,   0, ANIM]
	[225, 80, 64,31, -31,   0, ANIM]
	[150, 80, 64,31, -31,   0, ANIM]
	[ 75, 80, 64,31, -31,   0, ANIM]
	[300, 80, 64,31, -31,   0, ANIM]
}
template tmpl_overlay_straight() {
	[  0,155, 40,21, -19,   5]
	[ 50,155, 40,21, -19,   5]
}
template tmpl_overlay_slopes() {
	[  0,195, 64,39, -32,  -8]
	[ 75,195, 64,23, -31,   1]
	[150,195, 64,23, -31,   1]
	[225,195, 64,39, -31,  -8]
}
template tmpl_overlay_diagonal() {
	[100,155, 40, 7, -19,   4]
	[150,155, 40, 7, -19,  20]
	[200,155, 12,19,  11,   6]			
	[250,155, 12,19, -21,   6]
}


// track_type overlays
template tmpl_overlay_track_types() {
    tmpl_overlay_straight()
    tmpl_overlay_diagonal()
    tmpl_overlay_slopes()
}

template tmpl_bridges_underlay() {
	tmpl_underlay_straight()
	tmpl_underlay_slope()
	tmpl_underlay_diagonal()
}

// bridge surface overlays
template tmpl_bridges_overlay() {
//    tmpl_overlay_straight()
//    tmpl_overlay_slopes()
//    tmpl_overlay_diagonal()
	tmpl_bridges_underlay()
}

// track_type tunnel tracks
template tmpl_tunnel_tracks() {
	[ 75,  0, 64,31, -31,   0]
	[  0,  0, 64,31, -31,   0]
	[ 75,  0, 64,31, -31,   0]
	[  0,  0, 64,31, -31,   0]
}
// track_type level crossings
template tmpl_level_crossing_track_types_empty() {
	[  0,155, 40,21, -20,   5]
	[ 50,155, 40,21, -20,   5]

	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
	[  0,240, 10,10,   0,   0]
}
template tmpl_rails_crossing(x,y) {
	[   x,  y, 44,23, -21,   4]
	[x+50,  y, 44,23, -21,   4]
}
template tmpl_level_crossing_track_types_open(y) {
    tmpl_rails_crossing(5, 5)

	[  0,  y,  5,12,  -3,  -8]
	[ 50,  y,  8,21,  -5, -14]

	[100,  y,  6,23,  -7, -20]
	[150,  y,  5,12,  -5,  -8]

	[200,  y,  7,21,   3, -15]
	[250,  y,  5,12,  -1,  -8]

	[300,  y,  5,12,  -3, -10]
	[350,  y,  8,22,  -3, -19]
}
template tmpl_level_crossing_track_types_closed(y) {
    tmpl_rails_crossing(5, 5)

	[  0,  y,  5,12,  -3,  -8]
	[ 50,  y, 19,19,  -4,  -6]

	[100,  y, 23,17, -24,  -9, ANIM]
	[150,  y,  5,12,  -5,  -8]

	[200,  y, 25,14,   3,  -9]
	[250,  y,  5,12,  -1,  -8]

	[300,  y,  5,12,  -3, -10]
	[350,  y, 19,14, -15, -11, ANIM]
}

// fences
template tmpl_fences(y) { 
//fence drawing on diagonals is and has always been broken, the fences on both sides really need to be moved apart 4 px horizontally and 2 px vertically (1 "TTD unit", see also:
//	- https://www.tt-forums.net/viewtopic.php?f=26&t=61584
//	- https://bugs.openttd.org/task/5309
// need to move both sides half of that to compensate, or (todo) write a patch
// commented offsets are perfect for the front fence on diagonals
//	[  0,  y, 33,22, -30,  -6]
	[  0,  y, 33,22, -32,  -7]
//	[ 48,  y, 33,22,  -2,  -6]
	[ 48,  y, 33,22,  0,  -7]
	[ 93,  y,  8,32,  -3, -19] // verticals are OK as-is
	[112,  y, 65, 9, -32, -10] // same for horizontals
//	[192,  y, 33,15, -29,  -7]
	[192,  y, 33,15, -31,  -8]
//	[240,  y, 33,15,  -1,  -7]
	[240,  y, 33,15,  1,  -8]
//	[288,  y, 33,30, -30, -14]
	[288,  y, 33,30, -32, -15]
//	[350,  y, 33,30,  -2, -14]
	[350,  y, 33,30,  0, -15]
}

// gui
template tmpl_gui(y) {
	[  0,  0, 20, 20, 0, 0]
	[ 25,  0, 20, 20, 0, 0]
	[ 50,  0, 20, 20, 0, 0]
	[ 75,  0, 20, 20, 0, 0]
	[100,  0, 20, 20, 0, 0]
	[125,  y, 20, 20, 0, 0]
	[150,  0, 20, 20, 0, 0]
	[175,  0, 20, 20, 0, 0]
	
	[200,  0, 32, 32, 0, 0]
	[250,  0, 32, 32, 0, 0]
	[300,  0, 32, 32, 0, 0]
	[350,  0, 32, 32, 0, 0]
	[400,  0, 32, 32, 0, 0]
	[450,  y, 32, 32, 0, 0]
	[500,  0, 32, 32, 0, 0]
	[550,  0, 32, 32, 0, 0]
}

template tmpl_tunnel_overlaytracks(y) {
	[  0, y, 25, 31, -23,  -3]
	[ 91, y, 14, 12, -23,   5]
	[169, y, 11, 12,  12,   5]
 	[246, y, 25, 31,   0,  -3]
 }

 template tmpl_tunnel_overlays(y) {
	[ 40, y, 28, 31,  -7, -37]
	[117, y, 38, 23,  -9, -33]
	[192, y, 38, 22, -26, -34]
	[295, y, 28, 31, -19, -38]
}

template tmpl_no_fences() {
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
	[  1, 26,  1, 1,    0,  0]
}

//additional depot templates from modular depots

template tmpl_depot_modular_2() {
[118,128, 64,31, -31, -4]
[118, 8, 64,56, -9, -40]  //0, -2
[ 37,128, 64,31, -31, -4]
[ 37, 8, 64,56, -53, -40] //0, -2
[ 37, 68, 64,56, -53, -40] //0 -2
[118, 68, 64,56, -9, -40] //0 -2
}


