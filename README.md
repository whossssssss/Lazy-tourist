# 🌍 Lazy Tourist - 智能旅行路线规划工具

![System Architecture](https://raw.githubusercontent.com/yourusername/lazy-tourist/main/docs/architecture.png)

## 📌 项目简介

**Lazy Tourist** 是一款基于Python开发的智能旅行助手，帮助旅行者快速发现城市热门景点并自动生成优化路线。只需输入城市名称，即可获得：

- 该城市最受欢迎的景点列表
- 景点的详细信息和评分
- 智能规划的游览路线
- 一键生成导航链接

## ✨ 功能特性

- 🏙️ 城市景点智能推荐
- ⭐ 基于评分的景点排序
- 🗺️ 自动路线规划
- 🔗 快速导航链接生成
- 🖥️ 简洁的交互式界面

## 🛠️ 技术架构

```plantuml
@startuml LazyTourist-Architecture
skinparam monochrome true
skinparam shadowing false
skinparam defaultFontName Arial
skinparam defaultFontSize 14

left to right direction

rectangle "Frontend" {
  rectangle "Jupyter UI" as ui {
    rectangle "City Input"
    rectangle "Attractions List"
    rectangle "Route Button"
    rectangle "Results Display"
  }
}

rectangle "Backend" {
  rectangle "DeepSeek API" as deepseek {
    rectangle "Attraction Data"
    rectangle "Route Planning"
  }
  
  rectangle "Nominatim" as nominatim {
    rectangle "Geocoding"
  }
}

ui --> deepseek : 1. Request Attractions\n2. Get Route Plans
ui --> nominatim : Get Coordinates

note right of deepseek
  • REST API
  • JSON format
  • API key secured
end note

note left of ui
  • ipywidgets based
  • Pure presentation
  • No business logic
end note
@enduml
```

## 🚀 快速开始

### 安装依赖

```bash
pip install ipywidgets requests geopy
```

### 使用方法

1. 运行Jupyter Notebook
```bash
jupyter notebook
```

2. 导入并初始化应用
```python
from lazy_tourist import LazyTouristApp
app = LazyTouristApp()
```

3. 按照界面提示操作：
   - 输入城市名称
   - 从列表选择感兴趣的景点
   - 生成优化路线

## 📝 使用示例

![Demo Screenshot](https://raw.githubusercontent.com/yourusername/lazy-tourist/main/docs/demo.gif)

1. 输入"Paris"搜索巴黎景点
2. 选择埃菲尔铁塔、卢浮宫等景点
3. 生成最优游览路线
4. 获取路线详情和导航链接

## 🤝 贡献指南

欢迎提交Pull Request或Issue！

## 📄 许可证

MIT License

---

**Happy Traveling!** ✈️🌎
