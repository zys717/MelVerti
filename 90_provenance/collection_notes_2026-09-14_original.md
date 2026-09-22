# 数据收集清单 — 2026-09-14

保存位置：/Users/zhangyunshi/Downloads/Industry/supplementary

| 数据 | 文件/子目录 | 核验 |
|---|---|---|
| ABS 2021 SA1 GDA2020 边界 | ABS_SA1_2021：官方ZIP及original解压文件 | ZIP CRC通过；全国61,845条，维州15,482条 |
| PLAN_UGB | Vicmap_Planning/PLAN_UGB.geojson | 完整服务130条，原始线几何 |
| PLAN_ZONE | Vicmap_Planning/PLAN_ZONE.geojson | 指定31个LGA，20,968条，ID无重复 |
| PLAN_OVERLAY | Vicmap_Planning/PLAN_OVERLAY.geojson | 指定31个LGA，99,758条，ID无重复 |
| PLAN_CODELIST | Vicmap_Planning/PLAN_CODELIST.json | 完整代码表4,114条 |
| 三机场参考点 | Airports/airport_reference_points.geojson | YMML、YMEN、YMMB；附3份官方原始航图 |

规划数据来源：[Vicmap Planning FeatureServer](https://services-ap1.arcgis.com/P744lA0wf4LlBZ84/ArcGIS/rest/services/Vicmap_Planning/FeatureServer)，发布者Vicmap_Prod。服务元数据与许可原文保存在service_item.json，本服务声明CC BY 4.0。GeoJSON请求输出坐标为EPSG:4326；未简化几何，未加buffer，未裁剪到UGB，保留所有原始属性与状态。Zoning及overlay按用户列出的31个LGA筛选；Merri-bek已匹配当前名称。下载数量与服务器返回的ID数量一致。

ABS来源：[2021官方数字边界](https://www.abs.gov.au/statistics/standards/australian-statistical-geography-standard-asgs/edition-3-july-2021-june-2026/access-and-downloads/digital-boundary-files)。下载全国原始包，未重建或裁剪边界。人口连接字段为SA1_CODE21，对应已有表SA1_CODE_2021。

机场来源：[Airservices DAP 03SEP2026航图目录](https://www.airservicesaustralia.com/aip/pending/dap/dap_03SEP2026.htm)。各点保留原始度分秒、十进制度及来源URL。按Melbourne、Essendon、Moorabbin三个机场收集。未设定缓冲半径，buffer_radius_m为null。

源数据说明：PLAN_OVERLAY中的OBJECTID 39038、46170在服务GeoJSON导出中返回空几何，但原生Esri JSON仍含坐标环；已另存PLAN_OVERLAY_null_geometry_source.json保全这两条原生几何（服务坐标系见元数据），没有自行修复。PLAN_UGB是线图层，不是可直接裁剪的面。以上只进行数据收集与完整性检查，未运行模型或改动RP。

详细查询范围和数量见Vicmap_Planning/download_manifest.json；文件校验值见SHA256SUMS.txt。
