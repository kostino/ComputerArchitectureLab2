# Εργασία Δεύτερου Εργαστηρίου Αρχιτεκτονικής Υπολογιστών ΤΗΜΜΥ 2019

**Βλάχος Άγγελος** ΑΕΜ : 9087  
**Τριαρίδης Κωνσταντίνος** ΑΕΜ : 9159

### Περιεχόμενα
1. [Καταγραφή αποτελεσμάτων benchmarks για default τιμές](https://github.com/kostino/ComputerArchitectureLab2#Καταγραφή-βασικών-χαρακτηριστικών-συστήματος-στο-starter_se)
2. [Εύρεση στοιχείων για  default υποσύστημα μνήμης από αρχείο config.ini](https://github.com/kostino/ComputerArchitectureLab2#Εύρεση-στοιχείων-για-default-υποσύστημα-μνήμης-από-αρχείο-configini)
3. [Διαφορετικά μοντέλα in-order cpu στον gem-5 ](https://github.com/kostino/ComputerArchitectureLab2#διαφορετικά-μοντέλα-in-order-cpu-στον-gem-5) και [benchmarks σε δικό μας πρόγραμμα](https://github.com/kostino/ComputerArchitectureLab2#Benchmarks-σε-δικό-μας-πρόγραμμα-σε-timingsimplecpu-και-minorcpu)  
  a) Εκτέλεση προγράμματος σε TimingSimpleCPU , MinorCPU και σύγκριση αποτελεσμάτων  
  b) Ερμηνεία των αποτελεσμάτων , βάσει των διαφορών των μοντέλων  
  c) Αλλαγή παραμέτρων CPU, memory στο ίδιο μοντέλο και σύγκριση αποτελεσμάτων  
4. [Κριτική Εργασίας](https://github.com/kostino/ComputerArchitectureLab2#Κριτική-εργασίας)  

### Εύρεση στοιχείων για default υποσύστημα μνήμης από αρχείο config.ini

Από [system.cpu.dcache] **L1 Data cache** : size 64KB 2-way-associative
```python
size=65536
assoc=2
```
Από [system.cpu.icache] **L1 Instruction cache** : size 32KB 2-way-associative
```python
size=32768
assoc=2
```
Από [system.l2]**L2 cache** : size 2MB 8-way-associative
```python
size=2097152
assoc=8
```
Από [system] **scache line size** : 64B
```python
cache_line_size=64
```

### Καταγραφή αποτελεσμάτων benchmarks για default τιμές
![Time](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/time.png?raw=true)
![CPI](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/cpi.png?raw=true)
![Icache](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/icache.png?raw=true)
![Dcache](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/dcache.png?raw=true)
![L2](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/l2.png?raw=true)

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
