# Εργασία Δεύτερου Εργαστηρίου Αρχιτεκτονικής Υπολογιστών ΤΗΜΜΥ 2019

**Βλάχος Άγγελος** ΑΕΜ : 9087  
**Τριαρίδης Κωνσταντίνος** ΑΕΜ : 9159

### Περιεχόμενα
1. [Καταγραφή βασικών χαρακτηριστικών συστήματος στο starter_se](https://github.com/kostino/ComputerArchitectureLab1#Καταγραφή-βασικών-χαρακτηριστικών-συστήματος-στο-starter_se)
2. [Επαλήθευση ερ.1 από αρχεία config.ini, config.json](https://github.com/kostino/ComputerArchitectureLab1#επαλήθευση-ερ1-από-αρχεία-configini-configjson)
3. [Διαφορετικά μοντέλα in-order cpu στον gem-5 ](https://github.com/kostino/ComputerArchitectureLab1#διαφορετικά-μοντέλα-in-order-cpu-στον-gem-5) και [benchmarks σε δικό μας πρόγραμμα](https://github.com/kostino/ComputerArchitectureLab1#Benchmarks-σε-δικό-μας-πρόγραμμα-σε-timingsimplecpu-και-minorcpu)  
  a) Εκτέλεση προγράμματος σε TimingSimpleCPU , MinorCPU και σύγκριση αποτελεσμάτων  
  b) Ερμηνεία των αποτελεσμάτων , βάσει των διαφορών των μοντέλων  
  c) Αλλαγή παραμέτρων CPU, memory στο ίδιο μοντέλο και σύγκριση αποτελεσμάτων  
4. [Κριτική Εργασίας](https://github.com/kostino/ComputerArchitectureLab1#Κριτική-εργασίας)  


### Καταγραφή βασικών χαρακτηριστικών συστήματος στο starter_se


### Επαλήθευση ερ.1 από αρχεία config.ini, config.json

```python
type=MinorCPU
```

```python
clock=250
```

```python
mem_ranges=0:2147483647
memories=system.mem_ctrls0 system.mem_ctrls1
```

```python
cache_line_size=64
```
### Διαφορετικά μοντέλα in-order cpu στον gem-5

###  Benchmarks σε δικό μας πρόγραμμα σε TimingSimpleCPU και MinorCPU


### Αλλαγή παραμέτρων CPU , memory και ερμηνεία αποτελεσμάτων

### Κριτική εργασίας

```zsh
$ brew install gcc-7
$ export PATH=/usr/local/bin:$PATH
$ cd /usr/local/bin
$ ln -s  gcc-7  gcc

```

### Πηγές
* [Gem5 Documentation](http://gem5.org/Main_Page)  
* [The Arm Research Starter Kit: System Modeling using gem5](https://github.com/arm-university/arm-gem5-rsk/blob/master/gem5_rsk.pdf)
