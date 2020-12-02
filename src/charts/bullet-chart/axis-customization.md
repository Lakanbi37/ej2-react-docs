---
title: "Bullet Chart Axis Customization | React "

component: "Bullet Chart"

description: "Bullet Chart axis includes different customizations such as majortick and minortick, axis label, axis range."
---

# Axis Customization

## MajorTickLines and MinorTickLines Customization

You can customize the `width`, `color`, and `size` of minor and major tick lines using the
[`majorTickLines`](../api/bullet-chart/majorTickLinesSettingsModel/) and
[`minorTickLines`](../api/bullet-chart/minorTickLinesSettingsModel/) properties of the bullet-chart.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Revenue'
                        majorTickLines={{ color: 'blue', width: 5}}
                        minorTickLines={{ width: 4, color: 'red'}}
                        minimum={0}
                        maximum={30}
                        interval={5}
                        dataSource={[{value: 23, target: 22}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={20} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={25} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={30} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Tick Placement

You can place major and minor ticks `inside` or `outside` the ranges using the [`tickPosition`](../api/bullet-chart/bulletChartModel/#tickposition) property of bullet-chart.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Revenue'
                        tickPosition='inside'
                        minimum={0}
                        maximum={30}
                        interval={5}
                        dataSource={[{value: 23, target: 22}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={20} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={25} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={30} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Label Format

***Axis Label Format***

Axis numeric labels can be formatted by using the [`labelFormat`](../api/bullet-chart/bulletChartModel/#labelformat)property. Axis labels support all globalize formats. The following table describes the result of applying some commonly used label formats on numeric axis values.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Revenue'
                        labelFormat='c'
                        minimum={0}
                        maximum={30}
                        interval={5}
                        dataSource={[{value: 23, target: 22}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={20} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={25} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={30} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

The following 'Table' describes the result of applying some commonly used 'Label' formats on Numeric axis values.

<!-- markdownlint-disable MD033 -->
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The Number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The Number is rounded to 2 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1000.0</td>
<td>The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1000.00</td>
<td>The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
</table>

## GroupingSeparator

To separate groups of thousands, use the [`enableGroupSeparator`](../api/bullet-chart/bulletChartModel/#enablegroupseparator) property of bullet-chart.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Sales Rate'
                        enableGroupSeparator={true}
                        minimum={0}
                        maximum={2500}
                        interval={250}
                        dataSource={[{value: 1500, target: 1300}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={500} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={1500} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={2500} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Custom Label Format

You can also customize the axis label format using a placeholder like ${value}K, in which the value represents the axis label, e.g. $20K.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Sales Rate'
                        labelFormat='${value}K'
                        minimum={0}
                        maximum={2500}
                        interval={250}
                        dataSource={[{value: 1500, target: 1300}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={500} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={1500} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={2500} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Label Placement

You can customize the axis labels `inside` or `outside` the bullet-chart using the [`labelPosition`](../api/bullet-chart/bulletChartModel/#labelposition) property.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Revenue'
                        labelPosition='inside'
                        minimum={0}
                        maximum={30}
                        interval={5}
                        dataSource={[{value: 23, target: 22}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={20} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={25} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={30} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Opposed Position

To place an axis opposite to its original position,
set the [`opposedPosition`](../api/bullet-chart/bulletChartModel/#opposedposition) property to true.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Revenue'
                        majorTickLines={{ color: 'blue', width: 5}}
                        minorTickLines={{ width: 4, color: 'red'}}
                        opposedPosition={true}
                        minimum={0}
                        maximum={30}
                        interval={5}
                        dataSource={[{value: 23, target: 22}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={20} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={25} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={30} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Category Label

You can display the x axis label by mapping the `categoryField` from dataSource of a bullet-chart. It is a more efficient way to understand data.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Sales Rate'
                        categoryField='category'
                        minimum={0}
                        maximum={2500}
                        interval={250}
                        dataSource={[{value: 1500, target: 1300, category: 'Product A'}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={500} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={1500} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={2500} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}

## Category Label Customization

You can customize the category label by using the `categoryLabelStyle` property of the bullet-chart.

{% tab template="bullet-chart/axis-customization/axis", sourceFiles="app/**/*.tsx", compileJsx=true %}

```tsx
import { BulletChartComponent, Inject} from '@syncfusion/ej2-react-charts';
import { BulletRangeCollectionDirective, BulletRangeDirective} from '@syncfusion/ej2-react-charts';
import * as React from "react";
import * as ReactDOM from "react-dom";

class App extends React.Component<{}, {}>{
  render() {
    return (<BulletChartComponent id='ranges'
                        animation={{ enable: false }}
                        valueField='value'
                        targetField='target'
                        title='Sales Rate'
                        categoryField='category'
                        categoryLabelStyle={{ color:'Orange' }}
                        minimum={0}
                        maximum={2500}
                        interval={250}
                        dataSource={[{value: 1500, target: 1300, category: 'Product A'}]}>
                        <BulletRangeCollectionDirective>
                            <BulletRangeDirective end={500} color='red' ></BulletRangeDirective>
                            <BulletRangeDirective end={1500} color='blue'></BulletRangeDirective>
                            <BulletRangeDirective end={2500} color='green'></BulletRangeDirective>
                        </BulletRangeCollectionDirective>

            </BulletChartComponent>);
  }
};
ReactDOM.render(<App />, document.getElementById("charts"));
```

{% endtab %}