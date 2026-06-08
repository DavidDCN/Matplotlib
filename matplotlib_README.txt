╔══════════════════════════════════════════════════════════════════╗
║     MATPLOTLIB TUTORIAL — GLOBAL POPULATION & ECONOMY           ║
║                  README & SETUP GUIDE                            ║
╚══════════════════════════════════════════════════════════════════╝


─────────────────────────────────────────────────────────────────
  WHAT IS THIS?
─────────────────────────────────────────────────────────────────
  A Jupyter Notebook tutorial covering 7 chart types using
  matplotlib, numpy, and pandas — all applied to global
  population and economic data.

  File: matplotlib_tutorial.ipynb


─────────────────────────────────────────────────────────────────
  NOTEBOOK STRUCTURE
─────────────────────────────────────────────────────────────────
  Cell 1  →  Imports          (run this first!)
  Cell 2  →  Line Graph       Population growth models (linear vs exponential)
  Cell 3  →  Bar Graph        Average GDP per capita by world region
  Cell 4  →  Line Graph       gdp_trends.csv — 8 countries, 1995-2023
  Cell 5  →  Histogram        Life expectancy distribution (88 countries)
  Cell 6  →  Pie Chart Basic  Countries per continent
  Cell 7  →  Pie Chart Adv.   Total population by income group
  Cell 8  →  Box Plot         HDI scores by continent
  Cell 9  →  Summary          Quick reference tables

  Each chart = 1 Markdown cell (explanation) + 1 Code cell (runnable)


─────────────────────────────────────────────────────────────────
  DATASETS INCLUDED
─────────────────────────────────────────────────────────────────
  gdp_trends.csv
  ├── 29 rows (years 1995–2023)
  ├── 8 country columns: USA, China, Germany, Japan,
  │   India, Brazil, Nigeria, Australia
  └── Values: GDP per capita in USD
      (includes realistic recession dips: 2001, 2009, 2020)

  world_population.csv
  ├── 88 rows (one per country)
  ├── Continents: Africa (18), Asia (22), Europe (18),
  │   N.America (12), S.America (12), Oceania (6)
  └── Columns:
        Country, Continent
        Population(M)    ← ~30% stored as strings e.g. "45.3M"
        LifeExpectancy   ← range: 56–85 years
        GDP_per_capita   ← range: $300–$60,000
        HDI              ← range: 0.30–0.97
        IncomeGroup      ← Low / Lower middle / Upper middle / High
        BirthRate, DeathRate, UrbanPop(%)


─────────────────────────────────────────────────────────────────
  WHAT EACH CHART TEACHES
─────────────────────────────────────────────────────────────────
  1. LINE GRAPH
     plt.figure(figsize, dpi)        resize canvas
     plt.plot(x, y, 'r^--')          colour/marker/line shorthand
     np.arange(start, stop, step)    evenly spaced array
     array[:n]  /  array[n:]         plot partial data ranges
     plt.xticks(values, labels=[])   custom tick labels
     plt.savefig()                   export chart

  2. BAR GRAPH
     plt.bar(labels, values)         basic vertical bar chart
     bar.set_hatch('/')              texture patterns per bar
     for bar in container            iterate to style each bar

  3. REAL-WORLD LINE GRAPH
     pd.read_csv()                   load CSV → DataFrame
     for col in df.columns           auto-plot all countries
     df['Year'][::3]                 every 3rd year as ticks

  4. HISTOGRAM
     plt.hist(data, bins=[...])      frequency distribution
     Custom bins list                set exact bucket edges
     plt.xticks(bins)                align ticks to edges

  5. PIE CHART — BASIC
     df.loc[condition].count()[0]    filter + count rows
     plt.pie(values, autopct=...)    pie with % labels
     '%.2f %%'                       2 decimal places + %

  6. PIE CHART — ADVANCED
     plt.style.use('ggplot')         built-in theme
     List comprehension              clean "45.3M" → 45.3
     df.loc[cond, col].sum()         sum a column after filter
     explode=(0.4, 0.1, ...)         pull slices outward
     pctdistance=0.75                move % labels inward

  7. BOX PLOT
     plt.boxplot([s1, s2, ...])      median, IQR, outliers
     patch_artist=True               enable fill colour
     medianprops={'linewidth':3}     style median line
     zip(boxes['boxes'], colors)     colour each box uniquely


─────────────────────────────────────────────────────────────────
  INSTALLATION
─────────────────────────────────────────────────────────────────
  pip install matplotlib numpy pandas jupyter

  Launch:
    jupyter notebook        (classic)
    jupyter lab             (modern UI — pip install jupyterlab)

  Open:  matplotlib_tutorial.ipynb


─────────────────────────────────────────────────────────────────
  HOW TO RUN
─────────────────────────────────────────────────────────────────
  Run all at once:   Kernel → "Restart & Run All"
  Run one cell:      Shift+Enter  (run + move down)
                     Ctrl+Enter   (run + stay)

  Always run the Imports cell (Cell 1) first!


─────────────────────────────────────────────────────────────────
  COMMON MISTAKES & FIXES
─────────────────────────────────────────────────────────────────
  ✗  plt.save_fig()                  WRONG — doesn't exist
  ✓  plt.savefig()                   CORRECT

  ✗  plt.savefig() after show()      saves a blank image
  ✓  plt.savefig() before show()     saves the actual chart

  ✗  df['col']>a & df['col']<b       operator precedence bug
  ✓  (df['col']>a) & (df['col']<b)   wrap each condition

  ✗  df.columns()                    .columns is NOT callable
  ✓  df.columns                      no parentheses


─────────────────────────────────────────────────────────────────
  QUICK REFERENCE — plt.plot() shorthand
─────────────────────────────────────────────────────────────────
  COLOURS:   r  g  b  y  k  c  m  w
  MARKERS:   .  o  ^  v  s  *  +  x  D
  LINES:     -   --   -.   :

  Examples:
    'r^--'   red triangles, dashed
    'g.'     green dots, solid
    'b'      solid blue, no marker


─────────────────────────────────────────────────────────────────
  Libraries: matplotlib.org · numpy.org · pandas.pydata.org
