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

### Αλλαγή παραμέτρων και benchmarks
Αλλάζω τιμές των παραμέτρων και παρατηρώ την αλλαγή στην απόδοση του προγράμματος(μέσω της αλλαγής των CPI):  
* L1 icache size
* L1 icache associativity
* L1 dcache size
* L1 dcache associativity
* L2 cache size
* L2 cache associativity
* Cache line size
#### Αλλαγή μεγέθους L1 icache 
Όλα τα benchmarks εκτός από το mcf είχαν αρχικά πολύ χαμηλό L1 icache miss rate οπότε περιμένουμε να υπάρχει ουσιαστική αλλαγή μόνο στην απόδοση του mcf
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/isize.png?raw=true)
Πράγματι παρατηρείται 10% επιτάχυνση στην περίπτωση του mcf ενώ στα υπόλοιπα η αλλαγή δεν είναι καθόλου σημαντική. Η παρατήρηση αυτή μπορεί να εξηγηθεί στην περίπτωση που το mcf περιέχει ένα πολύ μεγάλο for loop ,που επαναλαμβάνεται πολλές φορές, το οποίο δεν χωρούσε να φορτωθεί ολόκληρο στην icache και με το που αυξήθηκε το μέγεθος αυτής χωράει. Πράγματι παρατηρώ πλέον πολύ χαμηλό icache miss rate και στο mcf, αντίστοιχο με τα άλλα benchmarks.
#### Αλλαγή associativity L1 icache 
Περιμένουμε ποιοτικά ανάλογα αποτελέσματα με αυτά από την αύξηση του μεγέθους της icache για το mcf αλλά αύξηση του CPI για τα υπόλοιπα
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/ia.png?raw=true)
Πράγματι παρατηρείται ανάλογη(ποιοτικά και **ποσοτικά**) επιτάχυνση για το mcf με αυτήν από την αύξηση μεγέθους , αποτέλεσμα πολύ σημαντικό για τις σχεδιαστικές μας αποφάσεις αφού η αύξηση του associativity είναι πιο φθηνή διαδικασία από την αύξηση του μεγέθους της μνήμης. Βέβαια παρατηρείται ελάχιστη αύξηση του CPI για τα άλλα benchmarks αφού η αύξηση του associativity σαν διαδικασία αυξάνει την πολυπλοκότητα και το hit-time για την icache.
#### Αλλαγή μεγέθους, associativity L1 dcache 
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/dsize.png?raw=true)
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/da.png?raw=true)
Με την αλλαγή στο μέγεθος και το associativity βλέπω επιτάχυνση μόλις πάνω από 1% στο bzip στο οποίο μειώνεται το miss-rate στην dcache. Στα άλλα benchmarks δεν βλέπω καμία αισθητή διαφορά.
#### Αλλαγή μεγέθους L2 cache 
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/l2size.png?raw=true)
Με την αλλαγή στο μέγεθος της L2 cache βλέπω πάλι επιτάχυνση ~1.7% στο bzip και ταυτόχρονα μείωση του miss rate στην L2 του bzip ενώ στα υπόλοιπα benchmarks πάλι δεν βλέπω κάποια αισθητή διαφορά.
#### Αλλαγή associativity L2 cache 
![1G](https://github.com/kostino/ComputerArchitectureLab2/blob/master/bench%20images/l2a.png?raw=true)
Με την αύξηση του associativity της L2 σε 16-way η υλοποίηση πλέον είναι πολύ πολύπλοκη οπότε έχω **επιβράδυνση** σε όλα τα benchmarks. Ξεκάθαρα δεν αξίζει η αύξηση του associativity πάνω από 8-way.
### Κριτική εργασίας


### Πηγές
*
