# Duty
tamrin haye dars mabahes vizhe

pip install geopandas matplotlib

import geopandas as gpd
import matplotlib.pyplot as plt

# بارگذاری داده‌های نقشه
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

# انتخاب قاره آسیا
asia = world[world['continent'] == 'Asia']

# ایجاد یک فیلتر برای کشور ایران
iran = asia[asia['name'] == 'Iran']

# ایجاد نقشه
fig, ax = plt.subplots(figsize=(10, 10))

# رسم قاره آسیا با رنگ روشن
asia.plot(ax=ax, color='lightgrey')

# رنگ‌آمیزی کشور ایران با رنگ دلخواه
iran.plot(ax=ax, color='orange')

# افزودن عنوان
plt.title('Map of Asia with Iran Highlighted')

# نمایش نقشه
plt.show()
