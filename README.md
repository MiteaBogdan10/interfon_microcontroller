Timpii t2, t3 şi t7 reprezintă timpul petrecut în starea RING, OPEN şi ERR. În continuare se 
prezintă descrierea detaliată a fiecărei stări: 

0. FMSG. Mesaj de întâmpinare sau primul mesaj – First MeSsaGe. Şterge LCD-ul şi apoi afişează 
mesajul:   Pe linia 1 a LCD-ului:   Suna la 1..8,    
           Pe linia 2 a LCD-ului:   C pentru cod:
           
Din starea FMSG se trece necondiţionat în starea WAIT. Necondiţionat înseamnă că tranziţia nu 
depinde de nici una din intrări. . 

1. WAIT. Interfonul aşteaptă introducerea unui caracter de la tastatură.  
a. Dacă s-a apăsat o cifră între 1 şi 8 se va şterge LCD-ul, se va afişa mesajul „Sun la a”, unde 
‚a’ este numărul apartamentului introdus anterior şi se va trece în starea RING. Tranziţia în 
starea RING se va abrevia cu „→ RING”. În general trecerea în starea stare se va abrevia cu  
→ stare. 
b. Dacă se apasă ‚C’ se şterge LCD-ul, se afișează „Cod=” şi  → COD1.  
c. Dacă se apasă ceva diferit de 1..8 sau ‚C’, nu se afişa nimic şi se rămâne în WAIT pe durată 
nedeterminată; timpul nu contează în starea WAIT.
  
2. RING. Interfonul va suna la apartamentul corespunzător cifrei apăsate în starea WAIT. Ar trebui ca 
interfonul să trimită către apartamentul ‚a’ semnalul care face ca postul din apartamentul ‚a’ să 
sune.  
a. Dacă din apartamentul ‚a’ se activează  semnalul de acceptare cmd se va șterge LCD-ul, se 
va afişă mesajul „Deschis!,  iar apoi → OPEN.  
b. Dacă t2 > 15 secunde && cmd=’0’,apoi → FMSG.   

3. OPEN. Se activează semnalul care deschide broasca.  
a. Dacă timpul petrecut în starea OPEN t3 > 5s → FMSG. 

4. COD1 – prima cifra a codului.  
a. Dacă tasta k este o cifra zecimală aceasta se va memora, se va afişa caracterul ‚*’ şi apoi → 
COD2.  
b. Dacă se apasă o tastă care nu este cifră zecimală, caracterul corespunzător nu se va afişa şi 
→ FMSG.  

5. COD2 – a doua cifră a codului.  
a. Dacă tasta k este o cifra zecimală aceasta se va memora, se va afişa caracterul ‚*’ şi apoi → 
COD3.  
b. Dacă se apasă o tastă care nu este cifră zecimală, caracterul corespunzător nu se va afişa şi 
→ FMSG.  

6. COD3 – a treia cifră a codului.  
a. Dacă tasta k este o cifra zecimală se va afişa ‚*’.  Apoi se va şterge LCD-ul şi se va verifica 
dacă cele trei cifre reprezintă codul de acces. 
i. Dacă DA, se afișează Deschis!,  iar apoi → OPEN 
ii. Dacă NU, se afișează „Cod invalid”,  iar apoi → ERR 
b. Dacă se apasă o tastă care nu este cifră zecimală, caracterul corespunzător nu se va afişa şi 
→ FMSG. 

7. ERR – eroare.  
a. Dacă timpul petrecut în starea ERR t7>5s → FMSG. 
