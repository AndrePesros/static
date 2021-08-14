using DocumentFormat.OpenXml.Office.CustomUI;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp2
{
    class Program
    {
        static string menu()
        {
            Console.Clear();
            Console.WriteLine("               MENU               ");
            Console.WriteLine(" ");
            Console.WriteLine("Jogar = 1 - Placar = 2 - Sair = 9 \n");
            return Console.ReadLine();
        }

        

        static int[] Jogar()
        {
            int cara = 1, coroa = 2;
            Console.Clear();
            Console.WriteLine("          Jogar           ");
            Console.WriteLine(" ");
            Console.WriteLine("Cara "+cara+" - Coroa  "+coroa+"       \n");

            int[] lista = new int[2];       
            
            lista[0] = cara;
            lista[1] = coroa;
            for (int cont = 1; cont < 1; cont++)
            {
                Random sorteio = new Random();
                
                int Sorteio = sorteio.Next(lista[0], lista[1]);
                Console.WriteLine("Escolha cara ou coroa ");
                lista[cont] = int.Parse(Console.ReadLine());
                lista[Sorteio] = cont;
                Console.WriteLine(Sorteio);

            }
            return lista;
        }

        static void Placar(int[] lista)
        {
            
            
            
            for (int cont = 0; cont < 1; cont++)
            {
                Console.Clear();
                Console.WriteLine("       PLacar               ");
                Console.WriteLine(" ");
                Console.WriteLine("Cara {0} Coroa {0}", lista[cont]);
            }
            Console.WriteLine("\n<--  Fim de JOGO  -->");
            Console.ReadKey();
        }


        static void Main(string[] args)
        {

            int[] lista = new int[2];
            string opcao = "";

            while (opcao != "9")
            {
                opcao = menu();

                switch (opcao)
                {
                    case "1":
                        lista = Jogar();
                        break;

                    case "2":
                        Placar(lista);
                        break;
                }
            }
        }
    }
}
