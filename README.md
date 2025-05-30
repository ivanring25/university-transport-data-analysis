# Анализ пассажиропотока общественного транспорта Санкт-Петербурга
## О работе
Анализ данных о работе маршрутов за период 01.04.2024–02.04.2025. Включает:
- Предобработку данных
- Выявление паттернов пассажиропотока
- Прогнозирование загрузки
- Кластеризацию маршрутов

### 1. Предобработка
- Объединены 3 источника данных (190K строк)
- Удалены аномалии: 
  - Строки с `нет совпадения` (20 % данных)
  - Выбросы через **IQR + Z-оценку** 
- Добавлены признаки: час/день недели

### 2. Анализ
- **Топ-5 маршрутов**: №12, №42, №28, №43, №15
- **Пиковые часы**: 
  - Будни: 7:00-9:00 и 16:00-18:00
- **Сезонность**: Недельные циклы с пиком в пятницу

### 3. Прогнозирование (ARIMA)
- Ряд стационарен (p-value=1.1e-25)
- Ошибки прогноза: 
  - MAE = 589.88, RMSE = 667.3

### 4. Кластеризация (K-Means)
- 5 кластера маршрутов:


## Визуализации
- Тепловые карты загрузки по часам/дням
- Графики временных рядов
- Боксплоты до/после обработки

## Технологии
Python, Pandas, Scikit-learn, Statsmodels, Matplotlib/Seaborn
