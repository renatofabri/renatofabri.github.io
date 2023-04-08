The app comes with mock data.

Files:
    Has two input file fields that can be interacted with.
    Polyline Coordinates:
        Upload a file that has ordered coordinates that can compose a polyline.
    Input Points:
        Upload a file that has coordinates to calculate offset and station.

Cartesian Plane:
    Plots the polyline along with the input points from the files uploaded.
    The canvas is limited by the ranges x: -400-400, y: -400-400.

Segments:
    Lists the points that can have a perpendicular offset with a set of coordinates.
    Output example:
        point: 0,0 -> the input point
        closest segment: s3 -> which section is closest to the point given
        closest segment coordinates: -46,-29 — 53,31 -> which coordinates set the closest segment
        offset: 0.9588581747726866 -> distance between the point and the line
        station (length from start): 321.5755059911897 -> distance from the begining of the polyline and the offset


Troubleshooting:
    Q: A point provided in the input file is missing in the Segments section but is displayed in the Cartesian Plane
    A: Means that it is not possible to make a perpendicular line with the station. The following message is shown in
       the browser's console: "Uncaught Error: Cannot plot a perpendicular line to the polyline"
