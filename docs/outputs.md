# :material-file-chart: Model Outputs

CityBEM V2 includes a **modular, configurable, and scalable** output-generation system designed for large urban simulations.  
Users can flexibly choose which variables to export to support storage efficiency, visualization workflows, and large-scale scenario analysis.

All outputs are controlled through:

```
:material-file-document-outline: Input_City_Scale_Result_Selection.txt
```

In this configuration file, each output variable is assigned **Y (Yes)** or **N (No)** to determine whether it will be:

- **Included in the single consolidated output file**, and/or  
- **Exported as a separate transient file**

This structure provides full customization over how simulation data is recorded and managed.

---

## :material-file-table-box-multiple: Output Modes

CityBEM supports two complementary output-generation modes.

---

### :material-file-document-outline: 1. Single Output File per Urban Area

A unified file is produced containing **all buildings** in the simulation domain.

<div class="admonition note">
<p class="admonition-title">Format</p>

- <b>Columns:</b> Activated output variables  
- <b>Rows:</b> Time-series values over the simulation duration  
</div>

**Best for**

- city-level diagnostics  
- machine-learning pipelines  
- aggregated statistical analysis  
- fast post-processing  

---

### :material-file-multiple: 2. Separate File per Output Variable

Each activated variable is exported to its **own transient file**, enabling fine-grained control and lightweight visualization.

<div class="admonition note">
<p class="admonition-title">Format</p>

- <b>Columns:</b> Building IDs  
- <b>Rows:</b> Transient simulation values  
</div>

**Best for**

- GIS dashboards  
- time-series visualization  
- animation and rendering  
- multi-building comparison  

---

## :material-table: Output Variable Index

CityBEM V2 provides an extensive set of output variables to support various analyses, including thermal behavior, solar radiation, photovoltaic generation, and microclimate interactions.

Each variable corresponds directly to a line in:

```
Input_City_Scale_Result_Selection.txt
```

Use:

- **Y** → Enable output  
- **N** → Disable output  

---

### :material-format-list-bulleted-type: Output Variables Table

## **Outputs Table**

<table>
  <thead>
    <tr>
      <th>Symbol</th>
      <th>Description</th>
      <th>Unit</th>
      <th>SingleFile</th>
      <th>SeparateFile</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>TA</code></td><td>Ambient air temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>GHI</code></td><td>Global solar radiation</td><td>W/m²</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>WS</code></td><td>Wind speed</td><td>m/s</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>WD</code></td><td>Wind direction</td><td>°</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>RH</code></td><td>Outdoor relative humidity</td><td>%</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TG</code></td><td>Ground temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TDP</code></td><td>Dew point temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HCVE</code></td><td>Exterior convective heat coefficient</td><td>W/m²·K</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HCVI</code></td><td>Interior convective heat coefficient</td><td>W/m²·K</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>TIN</code></td><td>Indoor air temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HUIN</code></td><td>Indoor air humidity</td><td>%</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>TWLI</code></td><td>Wall interior temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TWLE</code></td><td>Wall exterior temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>TWNI</code></td><td>Window interior temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TWNE</code></td><td>Window exterior temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>TEXC</code></td><td>Combined facade exterior temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TMS</code></td><td>Thermal mass surface temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TFLS</code></td><td>Floor surface temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TRFE</code></td><td>Roof exterior surface temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>QIHL</code></td><td>Internal heat load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>QWL</code></td><td>Wall transmitted heat</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>QWN</code></td><td>Window transmitted heat</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>QINF</code></td><td>Infiltration thermal load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>QTHM</code></td><td>Thermal mass heat load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>QFLR</code></td><td>Floor heat load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>HVLD</code></td><td>HVAC thermal load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>STRW</code></td><td>Solar transmitted through window</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>SABT</code></td><td>Solar absorbed by thermal mass</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>QNV</code></td><td>Natural ventilation heat load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>QMV</code></td><td>Mechanical ventilation heat load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>FNV</code></td><td>Natural ventilation mass flow</td><td>kg/s</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>FMV</code></td><td>Mechanical ventilation mass flow</td><td>kg/s</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>ORAR</code></td><td>Outdoor recirculation airflow ratio</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TSYS</code></td><td>Supply air temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>THLD</code></td><td>Total thermal load</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>HVPWC</code></td><td>HVAC power consumption</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>LIPOC</code></td><td>Lighting power consumption</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>APPOC</code></td><td>Appliances power consumption</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>TOPOC</code></td><td>Total electricity consumption</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>WNTR</code></td><td>Window transmittance</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>WNALB</code></td><td>Window albedo</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>WNABS</code></td><td>Window absorptance</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>THSTI</code></td><td>Thermal stress index</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>HEENV</code></td><td>Heat emission from envelope</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HEZON</code></td><td>Heat emission from zone</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HEAHU</code></td><td>Heat emission from AHU</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HEHVC</code></td><td>Heat emission from HVAC</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>HETOT</code></td><td>Total heat emission</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>ALFCT</code></td><td>All face temperatures</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>GHGOP</code></td><td>Operational GHG emissions</td><td>kg CO₂</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>GHGEE</code></td><td>Embodied GHG emissions</td><td>kg CO₂</td><td>NA</td><td>Y/N</td></tr>

    <tr><td><code>HVACP</code></td><td>HVAC power</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>FANPO</code></td><td>Fan power</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>GREEN</code></td><td>Green roof output</td><td>-</td><td>Y/N</td><td>Y/N</td></tr>

    <tr><td><code>ROFPV</code></td><td>Rooftop PV power output</td><td>W</td><td>Y/N</td><td>Y/N</td></tr>
    <tr><td><code>ROPVT</code></td><td>Rooftop PV cell temperature</td><td>°C</td><td>Y/N</td><td>Y/N</td></tr>
  </tbody>
</table>

---

## :material-cog-outline: Notes & Recommendations

- The output engine is optimized for **large datasets** (50,000+ buildings).  
- Selecting only required variables reduces output size and improves performance.  
- Both output modes can be enabled **simultaneously** when needed.  
- Separate-file mode is ideal for GPU-accelerated or real-time dashboards.

---