# https://youtu.be/3H8oWgPDijc
# https://colab.research.google.com/drive/19JrrHsRPY1dRTsVoUWIgRNvNRRcJpecI?usp=sharing
# DATASET :
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import statsmodels.api as sm
from statsmodels.stats.outliers_influence import variance_inflation_factor

from scipy.stats import shapiro
from scipy.stats import pearsonr
from scipy.stats import chi2_contingency

from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

-----------------------------------------------------------------------------------------
np.random.seed(10)

jumlah_data = 100

biaya_iklan = np.random.randint(10, 100, jumlah_data)
diskon = np.random.randint(5, 50, jumlah_data)

penjualan = (
    biaya_iklan * 2.5 +
    diskon * 1.8 +
    np.random.normal(0, 20, jumlah_data)
)

kategori = np.random.choice(
    ['Makanan', 'Minuman', 'Snack'],
    jumlah_data
)

df = pd.DataFrame({
    'Biaya_Iklan': biaya_iklan,
    'Diskon': diskon,
    'Penjualan': penjualan,
    'Kategori': kategori
})

df.head()
