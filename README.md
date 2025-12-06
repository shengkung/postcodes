# Global Postcodes Collection

**A comprehensive collection of postal codes from countries around the world** (全球郵遞區號資料集合)

---

## Introduction

This repository contains postal code (ZIP code) data for multiple countries in JSON format. The data is organized by administrative regions (provinces, states, cities, districts) and is ready to use in web applications, APIs, or any project requiring postal code validation and lookup.

本專案提供多個國家的郵遞區號（郵政編碼）資料，採用 JSON 格式。資料按行政區域（省、州、市、區）組織，可直接用於網站應用程式、API 或任何需要郵遞區號驗證和查詢的專案。

---

## Features

- ✅ **Multiple Countries** - Coverage for Asia-Pacific region (多國支援 - 涵蓋亞太地區)
- ✅ **Structured Data** - Hierarchical organization by region (結構化資料 - 按區域階層組織)
- ✅ **JSON Format** - Easy to parse and integrate (JSON 格式 - 易於解析和整合)
- ✅ **UTF-8 Encoding** - Full support for international characters (UTF-8 編碼 - 完整支援國際字元)
- ✅ **Ready to Use** - No additional processing required (即用型 - 無需額外處理)

---

## Available Countries

| Country | File | Regions | Description |
|---------|------|---------|-------------|
| 🇹🇼 Taiwan | `Taiwan.json` | 22 counties/cities | Complete postal codes for all districts (完整的鄉鎮市區郵遞區號) |
| 🇨🇳 China | `China.json` | 34 provinces | Major cities and provinces (主要城市和省份) |
| 🇯🇵 Japan | `Japan.json` | 47 prefectures | All prefectures with cities/towns/villages (所有都道府縣及市町村) |
| 🇵🇭 Philippines | `Philippines.json` | 81 provinces | Complete provincial coverage (完整省份覆蓋) |

---

## Data Structure

### Taiwan Example

```json
{
  "台北市": {
    "中正區": "100",
    "大同區": "103",
    "中山區": "104"
  },
  "新北市": {
    "板橋區": "220",
    "三重區": "241"
  }
}
```

### China Example

```json
{
  "北京市": {
    "北京市": "1100"
  },
  "廣東省": {
    "廣州市": "4401",
    "深圳市": "4403"
  }
}
```

### Japan Example

```json
{
  "東京都": {
    "千代田区": "CHIYODA KU",
    "新宿区": "SHINJUKU KU"
  }
}
```

### Philippines Example

```json
{
  "National Capital Region (NCR)": {
    "Manila": "1000",
    "Quezon City": "1100"
  }
}
```

---

## Usage

### JavaScript / Node.js

```javascript
// Load the data
const taiwanPostcodes = require('./Taiwan.json');

// Get postcode for a specific district
const postcode = taiwanPostcodes['台北市']['中正區'];
console.log(postcode); // Output: 100

// List all cities
const cities = Object.keys(taiwanPostcodes);
console.log(cities);

// List all districts in a city
const districts = Object.keys(taiwanPostcodes['台北市']);
console.log(districts);
```

### PHP

```php
// Load the data
$json = file_get_contents('Taiwan.json');
$postcodes = json_decode($json, true);

// Get postcode for a specific district
$postcode = $postcodes['台北市']['中正區'];
echo $postcode; // Output: 100

// Get all cities
$cities = array_keys($postcodes);
print_r($cities);

// Get all districts in a city
$districts = array_keys($postcodes['台北市']);
print_r($districts);
```

### Python

```python
import json

# Load the data
with open('Taiwan.json', 'r', encoding='utf-8') as f:
    postcodes = json.load(f)

# Get postcode for a specific district
postcode = postcodes['台北市']['中正區']
print(postcode)  # Output: 100

# Get all cities
cities = list(postcodes.keys())
print(cities)

# Get all districts in a city
districts = list(postcodes['台北市'].keys())
print(districts)
```

---

## Use Cases

- **E-commerce Websites** - Validate shipping addresses (電商網站 - 驗證配送地址)
- **Address Forms** - Auto-fill postal codes (地址表單 - 自動填入郵遞區號)
- **Logistics Systems** - Route planning and delivery zones (物流系統 - 路線規劃與配送區域)
- **Data Validation** - Verify address completeness (資料驗證 - 驗證地址完整性)
- **Geographic Analysis** - Regional data mapping (地理分析 - 區域資料對應)
- **API Development** - Postal code lookup services (API 開發 - 郵遞區號查詢服務)

---

## Installation

### Direct Download

Download the JSON file you need and include it in your project.

直接下載所需的 JSON 檔案並放入你的專案中。

### Git Clone

```bash
git clone https://github.com/shengkung/postcodes.git
cd postcodes
```

---

## Data Updates

The postal code data is periodically updated to reflect changes in administrative regions. If you notice any errors or outdated information, please submit an issue or pull request.

郵遞區號資料會定期更新以反映行政區域變更。如果你發現任何錯誤或過時資訊，請提交 issue 或 pull request。

---

## Contributing

Contributions are welcome! If you have postal code data for additional countries or updates to existing data:

1. Fork this repository
2. Add or update the JSON file
3. Ensure the data follows the existing format
4. Submit a pull request

歡迎貢獻！如果你有其他國家的郵遞區號資料或現有資料的更新：

1. Fork 此專案
2. 新增或更新 JSON 檔案
3. 確保資料遵循現有格式
4. 提交 pull request

---

## Data Format Guidelines

When contributing new country data, please follow these guidelines:

貢獻新國家資料時，請遵循以下準則：

- **File Naming**: Use English country name (e.g., `Taiwan.json`, `Japan.json`)
- **Encoding**: UTF-8 with BOM or without BOM
- **Structure**: Hierarchical JSON object (Province/State → City/District → Postcode)
- **Formatting**: Minified or pretty-printed (both acceptable)
- **Keys**: Use official local names in native language
- **Values**: Use official postal codes as strings

---

## Future Plans

- [ ] Add more countries (USA, UK, Canada, Australia, etc.)
- [ ] Include latitude/longitude coordinates
- [ ] Add English translations for region names
- [ ] Create API endpoints for online queries
- [ ] Provide search and autocomplete examples

---

## Data Sources

The data in this repository is compiled from official postal service sources and publicly available datasets:

- **Taiwan**: Chunghwa Post (中華郵政)
- **China**: China Post (中国邮政)
- **Japan**: Japan Post (日本郵便)
- **Philippines**: Philippine Postal Corporation (PHLPost)

---

## License

MIT License - Feel free to use this data in your projects, both commercial and non-commercial.

MIT 授權 - 可自由在商業或非商業專案中使用這些資料。

---

## Disclaimer

While we strive to keep the data accurate and up-to-date, postal codes may change over time due to administrative reorganizations. Always verify critical data with official sources.

儘管我們致力於保持資料準確和最新，但郵遞區號可能因行政區域重組而變更。關鍵資料請務必與官方來源核對。

---

## Version

- **Version**: 1.0.0
- **Last Updated**: December 2025
- **Data Coverage**: Taiwan, China, Japan, Philippines

---

## Author

- [簡盛弓 (Carter Chein)](https://www.facebook.com/shengkung)

---

## Links

- [奈思創藝網頁設計](http://www.nim.com.tw)
- [Report Issues](https://github.com/shengkung/postcodes/issues)
- [Submit Data](https://github.com/shengkung/postcodes/pulls)

---

## Star History

If you find this project useful, please consider giving it a ⭐ on GitHub!

如果你覺得這個專案有用，請考慮在 GitHub 上給它一個星星！⭐

