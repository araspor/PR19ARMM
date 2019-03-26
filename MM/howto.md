# Navodila za branje podatkov
Install pandas (enako kot numpy, matplotlib, itd.)
```python
import pandas as pd
# ne vzamemo vseh stolpcev
stolpci = [0, 1, 4, 5, 6, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 23, 24, 31, 32, 33, 47, 48, 49, 58, 59, 60, 65, 83, 89, 90, 91, 99, 100]
mesec = ['Januar', 'Februar', 'Marec', 'April', 'Maj', 'Junij', 'Julij', 'Avgust', 'September', 'Oktober', 'November', 'December']
dtype = {'B-Datum prve registracije vozila': 'str',
         '2A-Datum prve registracije vozila v SLO': 'str',
         'Status vozila (id)': 'float',
         'Status vozila (opis)': 'str',
         'Izvajalna enota prve registracije': 'str',
         'C-Starost uporabnika vozila': 'float',
         'C-Ali je uporabnik pravna ali fizicna oseba': 'str',
         'C-Spol uporabnika (ce gre za fizicno osebo)': 'str',
         'C-Ali je uporabnik tudi lastnik vozila': 'str',
         'C1.3-Upravna enota uporabnika vozila (oznaka)': 'str',
         'C1.3-Upravna enota uporabnika vozila (opis)': 'str',
         'C1.3-Obcina uporabnika vozila (oznaka)': 'str',
         'C1.3-Obcina uporabnika vozila (opis)': 'str',
         'C2-Starost lastnika vozila': 'float',
         'C2-Ali je lastnik pravna ali fizicna oseba': 'str',
         'C2-Spol lastnika (ce gre za fizicno osebo)': 'str',
         'D.1-Znamka': 'str',
         'D.4.2-Drzava (opis)': 'str',
         'D.4.2-Drzava (koda)':'str',
         'G-Masa vozila': 'float',
         'J-Kategorija in vrsta vozila (oznaka)': 'str',
         'J-Kategorija in vrsta vozila (opis)': 'str',
         'P.1.2-Nazivna moc': 'str',
         'P.1.3-Vrsta goriva (opis)': 'str',
         'P.1.3-Vrsta goriva (oznaka)': 'str',
         'R-Barva vozila (oznaka)': 'str',
         'R-Barva vozila (opis)': 'str',
         'S.1-Stevilo sedezev (vkljucno z vozniskim)': 'float',
         'U.3-V voznji': 'str',
         'V.8-Kombinirana poraba goriva': 'float',
         'Y.1-Dolzina': 'float',
         'Y.2-Sirina': 'float',
         'Y.3-Visina': 'float',
         'Komerc. oznaka  do prvega /': 'str',
         '5A-Leto izdelave': 'str'}

# BRANJE MESECEV (2015, 2018, 2019)
df1801 = pd.read_csv("../data/2018/Podatki_012018.csv", encoding = 'latin1', sep=';', usecols=stolpci, decimal =',', dtype=dtype)
# df1802 = ... vsak mesec posebej
# df18 = [df1801, df1802, ...] dataframe od vsakega meseca v list
# data = pd.concat(df18) zdruzi vse mesece

# BRANJE 2012
df12 = pd.read_csv("../data/2012/Vozila2012-1stRegs.csv", encoding = 'cp1252', usecols=range(1,54),sep=';', decimal =',', dtype=dtype)
# usecols = tiste stolpce, ki jih želimo; stolpec 0 = ID; nevem tocnu kjre bomo
rabla ma ush nje
# df12[df12['Starost uporabnika'] > 0]  # npr. ce zelimo use uporabnike, ki
imajo vpisano leto starosti
```
