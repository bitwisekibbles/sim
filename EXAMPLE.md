# Sim Examples

#### feedhelloworld.sim
```Batchfile
:: no need to set mode because feed is default
:: print hello world to the feed
print "Hello World"
:: halt to admire our creation
pause
:: ensure closure
exit
```


#### dynamichelloworld.sim
```Batchfile
:: enter terminal dynamic mode
mode dynamic
:: declare a string holding hello world so we can do operations on it
var hw = "Hello World"
:: print var hw to center screen offset by half horizontal length
print hw, (HCENTER - (length(hw) / 2)), VCENTER
:: halt to look at our beauty
pause
:: ensure closure
exit
```
