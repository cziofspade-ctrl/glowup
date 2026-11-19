# Weather SVG Pack

给 Claude / Codex 直接调用的天气 SVG 集合。

## 目录

- `animated/`：动画 SVG
- `static/`：静态 SVG

主体来源：Meteocons by Bas Milius，MIT。
本仓库使用 `ikku47/weather_icons_animated` 中打包的 upstream production assets。
`frost.svg` 单独来自 `Makin-Things/weather-icons`，同为 MIT。

## 必需映射

| 天气 | 文件名 | 来源 slug |
| --- | --- | --- |
| 晴（白天） | clear-day.svg | clear-day |
| 晴（夜间） | clear-night.svg | **starry-night**，特意选月亮 + 星星版本 |
| 多云（白天） | partly-cloudy-day.svg | partly-cloudy-day |
| 阴 | overcast.svg | overcast |
| 雨 | rain.svg | rain |
| 雷阵雨 | thunderstorm.svg | thunderstorms |
| 雪 | snow.svg | snow |
| 雾 | fog.svg | fog |
| 风 | wind.svg | wind |
| 霾 | haze.svg | haze |

额外附带 `dust.svg`，可把“沙尘”与“霾”分开识别。

## 可选映射

| 天气 | 文件名 | 来源 slug |
| --- | --- | --- |
| 多云（夜间） | partly-cloudy-night.svg | partly-cloudy-night |
| 大雨 / 暴雨 | heavy-rain.svg | extreme-rain |
| 雨夹雪 / 冻雨倾向 | sleet.svg | sleet |
| 冰雹 | hail.svg | hail |
| 霜 | frost.svg | Makin-Things frost |
| 彩虹 | rainbow.svg | rainbow |
| 日出 | sunrise.svg | sunrise |
| 日落 | sunset.svg | sunset |
| 星空 | starry.svg | starry-night |
| 台风 / 飓风 | hurricane.svg | hurricane |

## 给 AI 的使用建议

- 优先使用 `animated/` 做状态栏、小型天气组件。
- `prefers-reduced-motion`、低性能模式或大量重复节点时切换到 `static/`。
- SVG 可以 inline 后改尺寸、部分颜色或动画，但不要破坏原有 viewBox。
- 夜间晴与星空目前都基于 `starry-night`，是有意为之。
- 如需“普通无星月亮”，Meteocons 也有原始 `clear-night`，可另行加入。

## Sources

- Meteocons: https://meteocons.com/
- Upstream GitHub: https://github.com/basmilius/meteocons
- Asset package: https://github.com/ikku47/weather_icons_animated
- Frost supplement: https://github.com/Makin-Things/weather-icons
