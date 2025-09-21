# matplotlib_with_python
used pandas and matplotlib( subplot and line plot)
# to run the programm convert the readme to .py format

#this is the dataset use for this exercise

dict = ('''month_number  facecream  facewash  ...  moisturizer  total_units  total_profit
0              1       2500      1500  ...         1500        21100        211000
1              2       2630      1200  ...         1200        18330        183300
2              3       2140      1340  ...         1340        22470        224700
3              4       3400      1130  ...         1130        22270        222700
4              5       3600      1740  ...         1740        20960        209600
5              6       2760      1555  ...         1555        20140        201400
6              7       2980      1120  ...         1120        29550        295500
7              8       3700      1400  ...         1400        36140        361400
8              9       3540      1780  ...         1780        23400        234000
9             10       1990      1890  ...         1890        26670        266700
10            11       2340      2100  ...         2100        41280        412800
11            12       2900      1760  ...         1760        30020        300200''')



import matplotlib.pyplot as pl
import numpy as np
import pandas as pd
#for reading the data
data = pd.read_csv(r"C:\Users\ameht\Downloads\company_sales_data (4).csv")
to_find_row = data.iloc[[3,4]]

print(data)



# for Reading Total profit of all months and show it using a line plot
total_pro = data['total_profit']
month_ = data['month_number']

pl.plot( month_, total_pro)
pl.title("Total Profit of All Months")
pl.xlabel('month')
pl.ylabel('total profit')
pl.show()

#2: Read data for Bathing soap and facewash of all months and display it using the Subplot
bath_facewash = data[['month_number','bathingsoap', 'facewash']]
# to display using the subplot
bath_soap = data['bathingsoap']
month_ = data['month_number']

pl.subplot( 1,2,1)
pl.plot(month_,bath_soap)
pl.title("bathingsoap amount/Months")
pl.xlabel('month')
pl.ylabel('bathsoap')

face_wash = data['facewash']
month_ = data['month_number']

pl.subplot( 1,2,2)
pl.plot(month_, face_wash)
pl.title("facewash amount/month")
pl.xlabel('month')
pl.ylabel('facewash')


pl.show()
