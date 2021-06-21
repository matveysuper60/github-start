
'''python
import numpy as np       
import pandas as pd      
import os  
import math
speed_power = pd.read_excel('Приложение к заданию.xlsx' , 'Load')
user_power = pd.read_excel('Приложение к заданию.xlsx' , 'Сurve')
speed_time = pd.read_excel('Приложение к заданию.xlsx' , 'Wind')
def array_round(x):
    y = np.array([])
    for j in x:
        if (j +0.5) // 1 == j // 1:
            mround = j // 1 
            y = np.append(y , mround)
        else:
            mround = ((j + 0.5) // 1) - 0.5
            y = np.append(y , mround)
    return y
effective_speed = []
a = np.array(speed_time)
for i in range(len(a)):
    speed = ((a[i][1])**2 + (a[i][2])**2)** 0.5
    effective_speed.append(speed)
effective_speed_round = array_round(effective_speed)
x = len(effective_speed_round)
effective_speed_round = effective_speed_round.reshape(x, 1)
speed_power = np.array(speed_power)
P_itog = []
for i in effective_speed_round:
    for j in speed_power:
        if i[0] == j[0]:
            P_itog = np.append(P_itog , j[1])
P_itog = pd.DataFrame(P_itog)
P_fuel = np.array([])
for i in power_date:
    add_P = power_date[i][1] - power_date[i][2]
    if add_P < 0:
        add_P = 0
    P_fuel = np.append(P_fuel , add_P)
P  = pd.DataFrame(P)
chart_P = pd.concat([auxiliary_date , P] , axis = 1)
chart_c = np.array([])
for P in P_fuel:
    C = 12.5 + (0.2 * P)
    chart_c = np.append(chart_c , C)
c_itog = sum(chart_c)
c_itog


'''
