---
title: " Markers in React Maps control | Syncfusion "

component: "Maps"

description: "Learn here all about Markers feature of Syncfusion React Maps control and more."
---

# Markers in React Maps control

Markers are notes that are used to leave a message on the Maps. It indicates or marks a specific location with desired symbols on the Maps. It can be enabled by setting the [`visible`](../api/maps/markerSettingsModel/#visible) property of the [`markerSettings`](../api/maps/markerSettingsModel/) property to "**true**".

## Adding marker

To add the markers, the [`dataSource`](../api/maps/markerSettingsModel/#datasource) property of the [`markerSettings`](../api/maps/markerSettingsModel/) property has a list of objects that contains the data for markers. Using this property, any number of markers can be added to the layers of the Maps. By default, it displays the markers based on the specified latitude and longitude in the given data source. Each data source object contains the following list of properties.

* latitude - The latitude point which determines the X location of the marker.
* longitude - The longitude point which determines the Y location of the marker.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                            <MarkerDirective visible={true}
                                            height={20}
                                            width={20}
                                            animationDuration={0}
                                            dataSource={[
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998 },
                                                { latitude: 59.88893689676585, longitude: -109.3359375 },
                                                { latitude: -6.64607562172573, longitude: -55.54687499999999 }
                                            ]}>
                            </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Adding marker template

The Marker can be added as a template in the Maps component. The [`template`](../api/maps/markerSettingsModel/#template) property of the [`markerSettings`](../api/maps/markerSettingsModel/) property is used to set the HTML element or id of an element as a template.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                                        <MarkerDirective visible={true}
                                            height={30}
                                            width={30}
                                            template='<div id="marker1">Europe</div>'
                                            dataSource={[{ latitude: 49.95121990866204, longitude: 18.468749999999998 }]}
                                        >
                                        </MarkerDirective>
                                        <MarkerDirective visible={true}
                                            height={30}
                                            width={30}
                                            template='<div id="marker2">North America</div>'
                                            dataSource={[{ latitude: 59.88893689676585, longitude: -109.3359375 }]}
                                        >
                                        </MarkerDirective>
                                        <MarkerDirective visible={true}
                                            height={30}
                                            width={30}
                                            template='<div id="marker3">South America</div>'
                                            dataSource={[{ latitude: -6.64607562172573, longitude: -55.54687499999999 }]}
                                        >
                                        </MarkerDirective>
                                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Customization

The following properties are available in [`markerSettings`](../api/maps/markerSettingsModel/) property to customize the Markers of the Maps component.

* [`border`](../api/maps/markerSettingsModel/#border) - To customize the color, width and opacity of the border for the markers in Maps.
* [`fill`](../api/maps/markerSettingsModel/#fill) - To apply the color for markers in Maps.
* [`dashArray`](../api/maps/markerSettingsModel/#dasharray) - To define the pattern of dashes and gaps that is applied to the outline of the markers in Maps.
* [`height`](../api/maps/markerSettingsModel/#height) - To customize the height of the markers in Maps.
* [`width`](../api/maps/markerSettingsModel/#width) - To customize the width of the markers in Maps.
* [`offset`](../api/maps/markerSettingsModel/#offset) - To customize the position of the markers in Maps.
* [`opacity`](../api/maps/markerSettingsModel/#opacity) - To customize the transparency of the markers in Maps.
* [`animationDelay`](../api/maps/markerSettingsModel/#animationdelay) - To change the time delay in the transition for markers.
* [`animationDuration`](../api/maps/markerSettingsModel/#animationduration) - To change the time duration of animation for markers.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                            <MarkerDirective visible={true}
                                            height={20}
                                            width={20}
                                            animationDuration={1000}
                                            animationDelay={100}
                                            opacity={0.9}
                                            shape="Balloon"
                                            dashArray="1"
                                            border={{
                                                color: 'green',
                                                width: 2
                                            }}
                                            dataSource={[
                                                { latitude: 37.0000, longitude: -120.0000, city: 'California' },
                                                { latitude: 40.7127, longitude: -74.0059, city: 'New York' },
                                                { latitude: 42, longitude: -93, city: 'Iowa' }
                                            ]}>
                            </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Marker shapes

The Maps component supports the following marker shapes. To set the shape of the marker, the [`shape`](../api/maps/markerSettingsModel/#shape) property in [`markerSettings`](../api/maps/markerSettingsModel) property is used.

* Balloon
* Circle
* Cross
* Diamond
* Image
* Rectangle
* Start
* Triangle
* VerticalLine
* HorizontalLine

### Rendering marker shape as image

To render a marker as an image in Maps, set the [`shape`](../api/maps/markerSettingsModel/#shape) property of [`markerSettings`](../api/maps/markerSettingsModel/) as "**Image**" and specify the path of the image to [`imageUrl`](../api/maps/markerSettingsModel/#imageurl) property. There is another way to render a marker as an image using the [`imageUrlValuePath`](../api/maps/markerSettingsModel/#imageurlvaluepath) property of the [`markerSettings`](../api/maps/markerSettingsModel/) property. Bind the field name that contains the path of the image in the data source to the [`imageUrlValuePath`](../api/maps/markerSettingsModel/#imageurlvaluepath) property.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                            <MarkerDirective visible={true}
                                            shape="Image"
                                            imageUrl="maps/default-map/ballon.png"
                                            height={10}
                                            width={10}
                                            dataSource={[
                                                { latitude: 37.0000, longitude: -120.0000, city: 'California' },
                                                { latitude: 40.7127, longitude: -74.0059, city: 'New York' },
                                                { latitude: 42, longitude: -93, city: 'Iowa' }
                                            ]}>
                            </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Multiple marker groups

Multiple groups of markers can be added to the Maps by adding multiple [`MarkerDirective`](../api/maps/markerSettingsModel) in the [`MarkersDirective`](../api/maps/layerSettingsModel/#markersettings) and the customization for the markers can be done with the [`MarkerDirective`](../api/maps/markerSettingsModel) property.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                        <MarkerDirective visible={true} shape= "Diamond" height={15} fill="green" width={15}
                                        dataSource={[
                                            { latitude: 37.0000, longitude: -120.0000, name:'California'},
                                            { latitude: 40.7127, longitude: -74.0059, name:"New York" },
                                            { latitude: 42, longitude: -93, name:'Iowa' }
                                        ]}>
                                        </MarkerDirective>
                        <MarkerDirective visible={true} height={10} width={10} fill="blue" shape= "Circle"
                                        dataSource={[
                                            { latitude: 19.228825, longitude: 72.854118, name: "Mumbai"},
                                            { latitude: 28.610001, longitude: 77.230003, name: "Delhi"},
                                            { latitude: 13.067439, longitude: 80.237617, name: "Chennai"}
                                        ]}>
                        </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Customize marker shapes from data source

### Bind different colors and shapes to the marker from data source

Using the [`shapeValuePath`](../api/maps/markerSettingsModel/#shapevaluepath) and [`colorValuePath`](../api/maps/markerSettingsModel/#colorvaluepath) properties, the color and shape of the marker can be applied from the given data source. Bind the data source to the [`dataSource`](../api/maps/markerSettingsModel/#datasource) property of the [`markerSettings`](../api/maps/markerSettingsModel/) property and set the field names that contains the shape and color values in the data source to the [`shapeValuePath`](../api/maps/markerSettingsModel/#shapevaluepath) and [`colorValuePath`](../api/maps/markerSettingsModel/#colorvaluepath) properties.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                        <MarkerDirective visible={true}
                                            shape= {'Circle'} shapeValuePath= {'shape'} colorValuePath= {'color'}
                                            dataSource={[
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe', color:'red', shape:'Triangle' },
                                                { latitude: 59.88893689676585, longitude: -109.3359375, name:'North America',
                                                color:'blue', shape:'Pentagon' },
                                                { latitude: -6.64607562172573, longitude: -55.54687499999999, name:'South America',
                                                color:'green', shape:'InvertedTriangle' }
                                                ]}
                                        >
                                        </MarkerDirective>
                                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

### Setting value path from the data source

The latitude and longitude values are used to determine the location of each marker in the Maps. The [`latitudeValuePath`](../api/maps/markerSettingsModel/#latitudevaluepath) and [`longitudeValuePath`](../api/maps/markerSettingsModel/#longitudevaluepath) properties are used to specify the value path that presents in the data source of the marker. In the following example, the field name from the data source is set to the [`latitudeValuePath`](../api/maps/markerSettingsModel/#latitudevaluepath) and [`longitudeValuePath`](../api/maps/markerSettingsModel/#longitudevaluepath) properties.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                            <MarkerDirective visible={true}
                                            latitudeValuePath = "latitude"
                                            longitudeValuePath= "longitude"
                                            dataSource={[
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998 },
                                                { latitude: 59.88893689676585, longitude: -109.3359375},
                                                { latitude: -6.64607562172573, longitude: -55.54687499999999 }
                                            ]}>
                            </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Marker zooming

The Maps can be initially scaled to the center value based on the marker distance. This can be achieved by setting the [`shouldZoomInitially`](../api/maps/zoomSettingsModel/#shouldzoominitially) property in [`zoomSettings`](../api/maps/zoomSettingsModel/) as "**true**".

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject, Zoom } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps" zoomSettings= {{enable: true, horizontalAlignment:'Near', shouldZoomInitially: true}}>
                <Inject services={[Marker, Zoom]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map}>
                        <MarkersDirective>
                        <MarkerDirective visible={true}
                                            shape= {'Circle'}
                                            dataSource={[
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 59.88893689676585, longitude: -109.3359375, name:'North America' },
                                                { latitude: -6.64607562172573, longitude: -55.54687499999999, name:'South America'}
                                                ]}
                                        >
                                        </MarkerDirective>
                                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Marker clustering

Maps provide support to cluster the markers when they overlap each other. The number on a cluster indicates how many overlapped markers it contains. If zooming is performed on any of the cluster locations in Maps, the number on the cluster will decrease, and the individual markers will be seen on the map. When zooming out, the overlapping marker will increase. So that it can cluster again and increase the count over the cluster.

To enable clustering in markers, set the [`allowClustering`](../api/maps/markerClusterSettingsModel/#allowclustering) property of [`markerClusterSettings`](../api/maps/markerClusterSettingsModel) as "**true**" and customization of clustering can be done with the [`markerClusterSettings`](../api/maps/markerClusterSettingsModel) property.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import { cluster } from 'marker-cluster.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject, MapsTooltip, Zoom } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps" useGroupingSeparator={true} format='n' zoomSettings={{ enable: true  }} titleSettings={{ text: 'Top 13 largest cities in the World', textStyle: { size: '16px' } }}>
                    <Inject services={[Marker, MapsTooltip, Zoom]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map} shapeSettings={{ fill: '#C1DFF5' }} markerClusterSettings={{ allowClustering: true, shape: 'Circle', height: 30, width: 30, labelStyle: { color: 'white' }, }}>
                            <MarkersDirective>
                                <MarkerDirective visible={true} dataSource={cluster} shape='Balloon' tooltipSettings={{ visible: true, valuePath: 'area', }} height={15} width={15} animationDuration={0}>
                                </MarkerDirective>
                            </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Customization of marker cluster

The following properties are available to customize the marker clustering in the Maps component.

* [`border`](../api/maps/markerClusterSettingsModel/#border) - To customize the color, width and opacity of the border of cluster in Maps.
* [`connectorLineSettings`](../api/maps/connectorLineSettingsModel/) - To customize the connector line in cluster separating the markers.
* [`dashArray`](../api/maps/markerClusterSettingsModel/#dasharray) - To customize the dash array for the marker cluster in Maps.
* [`fill`](../api/maps/markerClusterSettingsModel/#fill) - Applies the color of the cluster in Maps.
* [`height`](../api/maps/markerClusterSettingsModel/#height) - To customize the height of the marker cluster in Maps.
* [`imageUrl`](../api/maps/markerClusterSettingsModel/#imageurl) - To customize the URL path for the marker cluster when the cluster shape is set as image in Maps.
* [`labelStyle`](../api/maps/markerClusterSettingsModel/#labelstyle) - To customize the text in marker cluster.
* [`offset`](../api/maps/markerClusterSettingsModel/#offset) - To customize the offset position for the marker cluster in Maps.
* [`opacity`](../api/maps/markerClusterSettingsModel/#opacity) - To customize the opacity of the marker cluster.
* [`shape`](../api/maps/markerClusterSettingsModel/#shape) - To customize the shape for the cluster of markers.
* [`width`](../api/maps/markerClusterSettingsModel/#width) - To customize the width of the marker cluster in Maps.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import { cluster } from 'marker-cluster.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, Point, MarkerDirective, Marker, Inject, MapsTooltip, Zoom } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps" useGroupingSeparator={true} format='n' zoomSettings={{ enable: true  }} titleSettings={{ text: 'Top 13 largest cities in the World', textStyle: { size: '16px' } }}>
                    <Inject services={[Marker, MapsTooltip, Zoom]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map} shapeSettings={{ fill: '#C1DFF5' }} markerClusterSettings={{  
                            allowClustering: true,
                            allowClusterExpand: true,
                            shape: 'Circle',
                            height: 40,
                            width: 40,
                            labelStyle : { color: 'white'},
                            offset: new Point(10, 20),
                            opacity: 0.9,
                            fill: 'green',
                            connectorLineSettings: {
                                color: 'orange',
                                opacity: 0.8,
                                width: 2
                            }
                           }}>
                            <MarkersDirective>
                                <MarkerDirective visible={true} dataSource={cluster} shape='Balloon' tooltipSettings={{ visible: true, valuePath: 'area', }} height={15} width={15} animationDuration={0}>
                                </MarkerDirective>
                            </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Expanding the marker cluster

The cluster is formed by grouping an identical and non-identical marker from the surrounding area. By clicking on the cluster and setting the [`allowClusterExpand`](../api/maps/markerClusterSettingsModel/#allowclusterexpand) property in [`markerClusterSettings`](../api/maps/markerClusterSettingsModel) as **true**" to expand the identical markers. If zoom in any of the locations of the cluster, the number on the cluster will decrease and the overlapping marker will be split into an individual marker on the map. When performing zoom out, it will increase the marker count and then cluster it again.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, Marker, Inject, Zoom } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps" zoomSettings= {{enable: true, mouseWheelZoom : true }}>
                    <Inject services={[Marker, Zoom]} />
                    <LayersDirective>
                        <LayerDirective shapeData={world_map} markerClusterSettings={{ allowClustering: true,  allowClusterExpand: true,shape: 'Circle', height: 40, width: 40, labelStyle: { color: 'white' }, }}>
                            <MarkersDirective>
                                <MarkerDirective visible={true} dataSource={[
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 49.95121990866204, longitude: 18.468749999999998, name:'Europe' },
                                                { latitude: 59.88893689676585, longitude: -109.3359375, name:'North America' },
                                                { latitude: -6.64607562172573, longitude: -55.54687499999999, name:'South America'}
                                                ]}  animationDuration={0}>
                                </MarkerDirective>
                            </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}

## Tooltip for marker

Tooltip is used to display more information about a marker on mouse over or touch end event. This can be enabled separately for marker by setting the [`visible`](../api/maps/tooltipSettingsModel/#visible) property of [`tooltipSettings`](../api/maps/tooltipSettingsModel) property to "**true**". The [`valuePath`](../api/maps/tooltipSettingsModel/#valuepath) property in the [`tooltipSettings`](../api/maps/tooltipSettingsModel) takes the field name that presents in dataSource and displays that value as tooltip text. The following example illustrates enabling the tooltip for the marker.

{% tab template="maps/default-map", compileJsx=true, sourceFiles="app/**/*.tsx" %}

```tsx
import { usa_map } from 'usa.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, MarkersDirective, MarkerDirective, MapsTooltip, Marker, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
                <MapsComponent id="maps">
                <Inject services={[Marker, MapsTooltip]} />
                    <LayersDirective>
                        <LayerDirective shapeData={usa_map}>
                        <MarkersDirective>
                            <MarkerDirective visible={true}
                                            height={20}
                                            width={20}
                                            animationDuration={0}
                                            tooltipSettings={{
                                                visible: true,
                                                valuePath:'city'
                                            }}
                                            dataSource={[
                                                { latitude: 40.7424509, longitude: -74.0081468, city: 'New York' }
                                            ]}>
                            </MarkerDirective>
                        </MarkersDirective>
                        </LayerDirective>
                    </LayersDirective>
                </MapsComponent>,
            document.getElementById("maps") as HTMLElement
);
```

{% endtab %}