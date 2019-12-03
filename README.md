# Εργασία Δεύτερου Εργαστηρίου Αρχιτεκτονικής Υπολογιστών ΤΗΜΜΥ 2019

**Βλάχος Άγγελος** ΑΕΜ : 9087  
**Τριαρίδης Κωνσταντίνος** ΑΕΜ : 9159

### Περιεχόμενα
1. [Καταγραφή βασικών χαρακτηριστικών συστήματος στο starter_se](https://github.com/kostino/ComputerArchitectureLab2#Καταγραφή-βασικών-χαρακτηριστικών-συστήματος-στο-starter_se)
2. [Εύρεση στοιχείων για  default υποσύστημα μνήμης από αρχείο config.ini](https://github.com/kostino/ComputerArchitectureLab2#Εύρεση-στοιχείων-για-default-υποσύστημα-μνήμης-από-αρχείο-config.ini)
3. [Διαφορετικά μοντέλα in-order cpu στον gem-5 ](https://github.com/kostino/ComputerArchitectureLab2#διαφορετικά-μοντέλα-in-order-cpu-στον-gem-5) και [benchmarks σε δικό μας πρόγραμμα](https://github.com/kostino/ComputerArchitectureLab2#Benchmarks-σε-δικό-μας-πρόγραμμα-σε-timingsimplecpu-και-minorcpu)  
  a) Εκτέλεση προγράμματος σε TimingSimpleCPU , MinorCPU και σύγκριση αποτελεσμάτων  
  b) Ερμηνεία των αποτελεσμάτων , βάσει των διαφορών των μοντέλων  
  c) Αλλαγή παραμέτρων CPU, memory στο ίδιο μοντέλο και σύγκριση αποτελεσμάτων  
4. [Κριτική Εργασίας](https://github.com/kostino/ComputerArchitectureLab2#Κριτική-εργασίας)  


### Καταγραφή βασικών χαρακτηριστικών συστήματος στο starter_se


### Εύρεση στοιχείων για default υποσύστημα μνήμης από αρχείο config.ini

Από [system.cpu.dcache] size 64KB 2-way-associative
```python
size=65536
assoc=2
```
Από [system.cpu.icache] size 32KB 2-way-associative
```python
size=32768
assoc=2
```
Από [system.l2] size 2MB 8-way-associative
```python
size=2097152
assoc=8
```
Από [system] cache line size 64B
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
