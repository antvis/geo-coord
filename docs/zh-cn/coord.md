# Coord

设置坐标系类型，同时允许进行各种坐标系变换，默认为笛卡尔坐标系。

```
import { getCoord } from '@antv/coord';

const geoCoord = getCoord('geo');

```

#### 参数

type: string
坐标系的类型，具体包括：

| type | 说明 |
| :--- | :--- |
| `rect` | 默认类型，直角坐标系，由 x, y 两个垂直的维度构成。 |
| `polar` | 极坐标系，由角度和半径 2 个维度构成。 |
| `theta` | 一种半径固定的极坐标系，常用于饼图。 |
| `helix` | 螺旋坐标系，常用于周期性数据。 |
| `geo` | 地理坐标系 |

#### coordCfg


### geoCoord

```
export interface GeoCFG {
  center?:number[]; // 中心经纬度
  zoom?:number; // 缩放等级
  projection?:string; //  默认 EPSG3857(webMercator) 投影字符串 EPSG3857  | EPSG4326 
}
```
## method
### getZoom()
获取地图的缩放等级
 geoCoord.getZoom();
### setZoom()
设置地图缩放等级
 ``` 
 geoCoord.setZoom(8);
 ```
### setCenter(lng ,lat) 
参数 ：  lng 经度，lat 纬度
        or array [lng,lat]
        or Lnglat

 始终地图中心经纬度
 ``` 
 geoCoord.setCenter(112.32,36);

 ```

 ### convertPoint 
 经纬度坐标转换成画布像素坐标

```
geoCoord.convertPoint({x:110,y:20})

```

 ### invertPoint
 
 画布坐标转换成经纬度坐标

 ```
geoCoord.invertPoint({x:0,y:0}])

```

 ### distance 

 计算两个经纬度直接的距离
 

 ```
 geoCoord.distance(lnglat1,lng1lat2)
 ```



