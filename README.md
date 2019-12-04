# Εργασία Δεύτερου Εργαστηρίου Αρχιτεκτονικής Υπολογιστών ΤΗΜΜΥ 2019

**Βλάχος Άγγελος** ΑΕΜ : 9087  
**Τριαρίδης Κωνσταντίνος** ΑΕΜ : 9159

### Περιεχόμενα
1. [Καταγραφή αποτελεσμάτων benchmarks για default τιμές](https://github.com/kostino/ComputerArchitectureLab2#καταγραφή-αποτελεσμάτων-benchmarks-για-default-τιμές)
2. [Εύρεση στοιχείων για  default υποσύστημα μνήμης από αρχείο config.ini](https://github.com/kostino/ComputerArchitectureLab2#Εύρεση-στοιχείων-για-default-υποσύστημα-μνήμης-από-αρχείο-configini)
3. [Αλλαγή ρολογιού στα 1GHz και σύγκριση χρόνου εκτέλεσης](https://github.com/kostino/ComputerArchitectureLab2#αλλαγή-ρολογιού-στα-1ghz-και-σύγκριση-χρόνου-εκτέλεσης)  
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
Από [system.l2] **L2 cache** : size 2MB 8-way-associative
```python
size=2097152
assoc=8
```
Από [system] **cache line size** : 64B
```python
cache_line_size=64
```

### Καταγραφή αποτελεσμάτων benchmarks για default τιμές
|                       |   bzip  |   mcf  |  hmmer |  sjeng  |   libm  |
|:---------------------:|:-------:|:------:|:------:|:-------:|:-------:|
|   Execution time(ms)  |  83.982 | 64.955 | 59.396 | 513.528 | 174.671 |
|          CPI          |  1.6797 | 1.2991 | 1.1879 | 10.2706 |  3.4934 |
| L1 icache missrate(%) |  0.0077 | 2.3612 | 0.0221 |  0.0020 |  0.0094 |
| L1 dcache missrate(%) |  1.4798 | 0.2108 | 0.1637 | 12.1831 |  6.0972 |
|  L2 cache missrate(%) | 28.2163 | 5.5046 | 7.7760 | 99.9972 | 99.9944 |

![Time](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/time.png?raw=true)
![CPI](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/cpi.png?raw=true)
![Icache](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/icache.png?raw=true)
![Dcache](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/dcache.png?raw=true)
![L2](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/l2.png?raw=true)

### Αλλαγή ρολογιού στα 1GHz και σύγκριση χρόνου εκτέλεσης
Μειώνοντας το ρολόι στο μισό περιμένω να δω διπλασιασμό του χρόνου εκτέλεσης δηλαδή επιτάχυνση από 1 σε 2 GHz περίπου 100%.  
Σε κάποια benchmarks παρατηρείται αυτό ενώ σε άλλα όχι :  

|                               |   bzip  |   mcf   |  hmmer  |  sjeng  |   libm  |
|:-----------------------------:|:-------:|:-------:|:-------:|:-------:|:-------:|
| Χρόνος εκτέλεσης στα 2GHz(ms) |  83.982 |  64.955 |  59.396 | 513.528 | 174.671 |
| Χρόνος εκτέλεσης στα 1GHz(ms) | 161.025 | 127.942 | 118.530 | 704.056 | 262.327 |
| Επιτάχυνση από 1 σε 2 GHz(%)  | 91.7    | 96.9    | 99.5    | 37.1    | 50.1    |

![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/step%201/Default%202GHz/images/1g.png?raw=true)
### Κριτική εργασίας


### Πηγές
*
