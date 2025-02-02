# State Persistence

## State Persistence

For state maintenance, state persistence allows Maps to save the current modal value in browser cookies. This action is handled through the [`enablePersistence`](../api/maps#enablepersistence) property which is set to **false** by default. When this property is set to true, some of the Maps component model values are preserved even after the page is refreshed.

```tsx

import { world_map } from 'world-map.ts';
import * as React from "react";
import * as ReactDOM from "react-dom";
import { MapsComponent, LayersDirective, LayerDirective, Zoom, Inject } from '@syncfusion/ej2-react-maps';

ReactDOM.render(
            <MapsComponent id="maps" enablePersistence={true} zoomSettings={ { enable: true } }>
            <Inject services={[Zoom]}/>
                <LayersDirective>
                    <LayerDirective shapeData={world_map}>
                    </LayerDirective>
                </LayersDirective>
            </MapsComponent>,
document.getElementById("maps") as HTMLElement
);

```
