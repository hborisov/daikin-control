# Controlling Daikin Air Conditioner

## /aircon/set_control_info

mandatory parameters:

* pow 
  * 1 means switch on
  * 0 - switch off
  
* mode 
  * 1 - auto
  * 2 - drying
  * 3 - cooling
  * 4 - heating
  * 5 - heating
  * 6 - fan

* stemp - desired temperature
  * example: stemp=22.0

* f_rate - fan speed
  * A - auto
  * 3 - first step
  * 4 -
  * 5 -
  * 6 - 
  * 7 - last step

* f_dir - fan direction (swing mode)
  * 0 - all wings stopped
  * 1 - vertical wings motion
  * 2 - horizontal wings motion
  * 3 - vertical and horizontal wings motion
    
* shum - humidity
  * 0

Example request:

GET http://192.168.1.111/aircon/set_control_info?mode=3&stemp=22.0&f_dir=0&f_rate=A&pow=0&shum=0

## /aircon/get_sensor_info

response:
ret=OK,htemp=27.0,hhum=-,otemp=25.5,err=0,cmpfreq=0

htemp - inside temperature
otemp - outside temperature

## /aircon/get_control_info

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=5,f_dir=0,b_f_rate=5,b_f_dir=0,dfr1=5,dfr2=5,dfr3=5,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

## Links

* https://github.com/ael-code/daikin-control - good API description
* https://github.com/ael-code/daikin-aricon-pylib
* https://github.com/home-assistant/core/pull/11840/files

## Examples

http://192.168.1.111/aircon/set_control_info?dfr4=5&shum=0&dfr6=5&dt2=M&b_stemp=22.0&dt5=25.0&dfr5=5&dt1=25.0&f_dir=0&dfr2=5&dhh=50&dfr3=5&dt3=22.0&dfd5=0&dfd7=0&b_shum=0&dh1=AUTO&b_f_rate=5&dh3=0&dfd4=0&pow=1&dfdh=0&dt4=25.0&dh4=0&dfrh=5&dfd1=0&adv=&mode=3&b_f_dir=0&dh5=0&dh2=50&stemp=22.0&dfr7=5&dfr1=5&f_rate=5&dfd3=0&dt7=25.0&dh7=AUTO&dfd6=0&dfd2=0&b_mode=3

http://192.168.1.111/aircon/set_control_info?dfr4=5&shum=0&dfr6=5&dt2=M&b_stemp=22.0&dt5=25.0&dfr5=5&dt1=25.0&f_dir=0&dfr2=5&dhh=50&dfr3=5&dt3=21.0&dfd5=0&dfd7=0&b_shum=0&dh1=AUTO&b_f_rate=5&dh3=0&dfd4=0&pow=1&dfdh=0&dt4=25.0&dh4=0&dfrh=5&dfd1=0&adv=&mode=3&b_f_dir=0&dh5=0&dh2=50&stemp=21.0&dfr7=5&dfr1=5&f_rate=5&dfd3=0&dt7=25.0&dh7=AUTO&dfd6=0&dfd2=0&b_mode=3

http://192.168.1.111/aircon/set_control_info?b_f_rate=5&f_rate=5&dt3=22.0&dfr7=5&dfr5=5&dt1=25.0&dh7=AUTO&dfr6=5&dfr2=5&shum=0&mode=3&dh5=0&dfr4=5&dfdh=0&dt7=25.0&dh4=0&dfd4=0&dfr1=5&dh3=0&b_mode=3&dfd2=0&b_shum=0&dfd5=0&dhh=50&pow=1&f_dir=0&dt2=M&dfr3=5&b_f_dir=0&dt4=25.0&dfd1=0&b_stemp=22.0&dfd3=0&dh2=50&dfd6=0&stemp=22.0&dfrh=5&dfd7=0&adv=&dh1=AUTO&dt5=25.0


stop
http://192.168.1.111/aircon/set_control_info?dfr1=5&stemp=22.0&f_rate=5&dh2=50&b_f_rate=5&b_mode=3&b_f_dir=0&dh5=0&dfd3=0&dfr5=5&dt1=25.0&dfd4=0&dfd1=0&b_stemp=22.0&dh3=0&dh4=0&f_dir=0&dh7=AUTO&dt2=M&dt3=22.0&dfrh=5&dfr7=5&dt4=25.0&dfd6=0&dfd7=0&dfd5=0&b_shum=0&dfr6=5&mode=3&dh1=AUTO&dt7=25.0&dfr4=5&shum=0&dfr2=5&dfdh=0&adv=&dhh=50&dt5=25.0&dfd2=0&dfr3=5&pow=0


ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=5,f_dir=0,b_f_rate=5,b_f_dir=0,dfr1=5,dfr2=5,dfr3=5,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=7,f_dir=0,b_f_rate=7,b_f_dir=0,dfr1=5,dfr2=5,dfr3=7,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=6,f_dir=0,b_f_rate=6,b_f_dir=0,dfr1=5,dfr2=5,dfr3=6,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=4,f_dir=0,b_f_rate=4,b_f_dir=0,dfr1=5,dfr2=5,dfr3=4,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=3,f_dir=0,b_f_rate=3,b_f_dir=0,dfr1=5,dfr2=5,dfr3=3,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

ret=OK,pow=1,mode=3,adv=,stemp=22.0,shum=0,dt1=22.0,dt2=M,dt3=22.0,dt4=22.0,dt5=22.0,dt7=22.0,dh1=0,dh2=0,dh3=0,dh4=0,dh5=0,dh7=0,dhh=50,b_mode=3,b_stemp=22.0,b_shum=0,alert=255,f_rate=A,f_dir=0,b_f_rate=A,b_f_dir=0,dfr1=5,dfr2=5,dfr3=A,dfr4=5,dfr5=5,dfr6=5,dfr7=5,dfrh=5,dfd1=0,dfd2=0,dfd3=0,dfd4=0,dfd5=0,dfd6=0,dfd7=0,dfdh=0

http://192.168.1.111/aircon/set_control_info
?dfr4=5
dfr6=5
dfr5=5
dfr2=5
dfr3=5
dfrh=5
dfr7=5
dfr1=5
dt2=M
dt5=25.0
dt1=25.0
dt3=22.0
dt4=25.0
shum=0
b_shum=0
b_stemp=22.0
f_dir=0
dhh=50
dfd1=0
dfd4=0
dfd3=0
dfd5=0
dfd7=0
dfd6=0
dfd2=0
dfdh=0
dh1=AUTO
dh2=50
dh3=0
dh4=0
dh5=0
dh7=AUTO
b_f_rate=5
pow=1
adv=
mode=3
b_f_dir=0
stemp=22.0
f_rate=5
dt7=25.0
b_mode=3
