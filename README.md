# SanFran_Real_Estate (san_francisco_housing)

Analysis for a one-click service for people to buy properties and then rent them in San Francisco. Using data visualization, aggregation, interactive visualizations, and geospatial analysis, to find properties in the San Francisco market that are viable investment opportunities.

---

## Technologies

This project leverages python 3.7 with the following:

* [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/) - JupyterLab is a web-based user interface designed for data analysis.

* [pandas](https://github.com/pandas-dev/pandas) - Flexible and powerful data analysis / manipulation library for Python.

* [dotenv](https://pypi.org/project/python-dotenv/) - Python-dotenv reads key-value pairs from a .env file and can set them as environment variables.

* [plotly.express](https://plotly.com/python/plotly-express/) - The plotly.express module contains functions that can create entire figures at once.

---

### Installation Guide

Before running the application first install the following dependencies.

```python
  pip install jupyterlab
  pip install pandas
  pip install dotenv
  pip install plotly.express
```

---

## Examples

** Loading the .env file, Reading API Key, Setting API Access. **
```
load_dotenv()

# Read in your MAPBOX_API_KEY
mapbox_api_access_token = os.getenv("MAPBOX_API_ACCESS_TOKEN")

# Confirm the availability of your Mapbox API access token by checking its type
print(type(mapbox_api_access_token))

# Set your Mapbox API access token
px.set_mapbox_access_token(mapbox_api_access_token)

```
** Creating a visual aggregation explore the housing units by year. **
```
housing_units_by_year.hvplot.bar(
            title = "Housing Units in San Francisco from 2010 to 2016",
            x = "year",
            y = "housing_units",
            xlabel = "Year",
            ylabel = "Housing Units",
            fill_color = "blue",
            ylim = [365000, 385000],
            width = 550,
            height = 250,
            hover_cols = ["sale_price_sqr_foot", "gross_rent"],
            hover_color = "green"
        ).opts(
            yformatter="%.0f"
        )

```

** Createing a scatter mapbox to analyze neighborhood info.**
```
mapbox = px.scatter_mapbox(
    all_neighborhoods_df,
    lat="Lat",
    lon="Lon",
    size="sale_price_sqr_foot",
    color="gross_rent",
    size_max=25,
    zoom=11
)

mapbox

```

---

## Usage

To use the SanFran_Real_Estate application simply clone the repository and run the **san_francisco_housing.py** with:

```python
python san_francisco_housing.py
```

Below you will find screenshot demonstrations.

![Housing Units By Year](Images/zoomed-housing-units-by-year.png)

![Average Sale Price Per SQFT](Images/avg-sale-px-sq-foot-gross-rent.png)

![Pricing Info By Neighborhood](Images/pricing-info-by-neighborhood.png)

![MapBox Plot of San Francisco](Images/mapbox-plot.png)

---

## Contributors

Brought to you by Robert Giannini.
LinkedIn: https://www.linkedin.com/in/robertgianninijr/

---

## License

MIT 
 
