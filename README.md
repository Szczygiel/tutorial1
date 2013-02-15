tutorial1
=========

tutorial1


using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            
            //POCZATEK DRUKOWANIA LICZB PIERWSZYCH NA EKRANIE MONITORA

            int ktoraLP = 1; //ktora liczba ma byc teraz obliczona
            int kolejnaL = 2; //kolejna sprawdzana liczba (czy jest l.pierwsza)
            int UstalonaIloscLP; 

            Program ppp = new Program();

           
            UstalonaIloscLP = ppp.IloscLP();

            Console.WriteLine();

          
            while (ktoraLP <= UstalonaIloscLP)
                
            {
               if (ppp.czyLP(kolejnaL))
               {
                   Console.WriteLine("Liczba pierwsza nr " + ktoraLP + " to: " + kolejnaL);
                   ktoraLP++;
                   Console.Read();
                   Console.Read();
               }
               
                kolejnaL++; //sprawdzi teraz kolejna liczbe naturalna
                
            }
            
         
            Console.WriteLine();
            Console.WriteLine("To wszystkie liczby pierwsze, o ktore prosile/-as.");
            Console.WriteLine();
            Console.WriteLine("Sa to " + UstalonaIloscLP + " najmniejsze liczby pierwsze.");
            Console.Read();
            Console.Read();


            //KONIEC DRUKOWANIA NA EKRANIE LICZB PIERWSZYCH

           
        }

        
        Int32 IloscLP()

            //Ustalenie ile liczb pierwszych ma potem wyswietlac - na podstawie informacji input z klawiatury usera

        {
            int ileLP; //ile liczb pierwszych ma wyswietlic
         
            //program pyta usera o ilosc kolejnych liczb pierwszych do ustalenia
            Console.WriteLine("Ile kolejnych najmniejszych liczb pierwszych chcesz ustalic? ");

            ileLP = Convert.ToInt16(Console.ReadLine());

         
            //ustalilismy, ze userowi zostanie wyswietlonych na ekranie pierwsze ileLP liczb pierwszych.
            //jezeli ileLP=1 wowczas userowi wyswietli tylko liczbe pierwsza = 2
            //jezeli ileLP=2 wowczas userowi wyswietli liczby pierwsze = 2 i 3
            //jezeli ileLP=3 wowczas userowi wyswietli liczby pierwsze = 2 , 3 i 5
            // itd.

            return ileLP;

            // Koniec ustalania - znamy juz ilosc liczb pierwszych, ktora program wyswietli - jako funkcja IloscLP

        }



        //---------STWIERDZENIE CZY LICZBA JEST L.PIERWSZA CZY ZLOZONA (START)---------------------------------------

        //przyklad: czyLP(4) powinno dac wartosc "False" z typu binarnego; czyLP(5) da wartosc "True"
        Boolean czyLP(int myliczba)     
        {
            //zwraca wartość TRUE or FALSE mowiaca czy "myliczba" jest liczba pierwsza

            Boolean czyLPpom; //czy liczba pierwsza
            
            
            int licz = 2; //pod licz podstawia kolejne liczby od 2 do myliczba-1 i sprawdza podzielnosc; podzielnosc --> nie jest liczba pierwsza

            czyLPpom = true; //zakladamy na poczatku ze mamy do czynienia z l.pierwsza; jesli bedzie podzielnosc to sie to zmieni pozniej

            while (licz < myliczba)
            
            {
                if (myliczba%licz == 0)
                {
                    czyLPpom = false; // tutaj moze dojsc do przestawienia wartosci czyLPpom wskazujac ze nie jest to l.pierwsza
                    licz=myliczba; //podnosi licznik tak, aby juz dalej nie sprawdzal podzielnosci bo tak czy inaczej nie jest to l.pierwsza
                    //wyskakuje dzieki temu z petli while
                }
                
                if (myliczba%licz != 0)
                    licz++; // gdy nie stwierdzi podzielnosci, po prostu sprawdza podzielnosc dla kolejnych mianownikow
            }

               //po wyjsciu z petli juz jest wiadomo czy mamy do czynienia z l.pierwsza; wskazuje na to zmienna czyLPpom 

            if (myliczba == 1)
                czyLPpom = false;

            return czyLPpom;
        }
        //------------------------------------------------------------------
        
    }
}
