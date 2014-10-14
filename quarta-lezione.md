Argomenti:

1. riprendere le funzioni composte: modello di valutazione ad alberi -> visibilità delle variabili
2. riprendere i problemi proposti la settimana scorsa, ed introdurre i costrutti condizionali
3. varie ed eventuali 
4. Ricorsione

Un procedimento ricorsivo è un algoritmo che, per giungere a conclusione, necessita di richiamare se stesso, generando così una sequenza di chiamate che termina solo quando viene soddisfatta una condizione particolare. Quando ciò avviene, quella chiamata viene soprannominata passo base.
Il calcolo del fattoriale di un numero n, poichè è descrivibile in termini di se stesso (n! = n*(n-1)!) è un procedimento che può essere descritto mediante un algoritmo ricorsivo.

N.B. Se possibile, è preferibile evitare questo tipo di algoritmi, poichè risultano molto lenti e tendono a consumare grandi quantità di memoria stack. Questo problema è dovuto alle continue chiamate alla stessa funzione, comportamento che impedisce la liberazione della memoria fino a quando non viene raggiunto il passo base. Inoltre, le continue operazioni svolte sulla memoria contribuiscono a rallentare l'esecuzione del programma. Nel caso del calcolo del fattoriale mediante procedimento ricorsivo, non sarà quindi possibile calcolare il fattoriale di numeri troppo elevati poichè la memoria stack verrà esaurita. Una soluzione migliore per il calcolo del fattoriale consiste, perciò, nell'utilizzo di istruzioni iterative.

Esempi per calcolo del fattoriale mediante procedimento ricorsivo:

Esempio in C:

        #include <stdio.h>
        double fattoriale (double x)
        {
          if (x>0)
            return x*(fattoriale(x-1));     //Visto che all'interno dell'if c'è solo 1 istruzione, posso omettere le graffe
          else
            if (x==0)
              return 1;
            else
              return -1; 					//Non è possibile fare il fattoriale di un numero negativo
        }
      
        void main()
        {
          double result=fattoriale (-1);
          if (result!=-1)             //!= significa diverso
            printf("%f", result);
          else
            printf("Errore");
        }
       
 Esempio in Java:
 
        public class Fattoriale{
    
          public static double fattoriale (double x)
          {
            if (x>0)
              return x*(fattoriale(x-1));     //Visto che all'interno dell'if c'è solo 1 istruzione, posso omettere le graffe
            else
              if (x==0)
                return 1;
              else
                return -1;					//Non è possibile fare il fattoriale di un numero negativo
          }
    
          public static void main(String []args){
            double result=fattoriale(1);
            if (result!=-1)         //!= significa diverso
              System.out.println(result);
            else
              System.out.println("Errore");

          }
        }

Esempio in Python
	
        def fattoriale (x):
          if x>0:
            return x*(fattoriale(x-1))
          else:
            if x==0:
              return 1
            else:
              print "Errore"
              
