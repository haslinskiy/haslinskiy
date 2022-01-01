using System;
using System.Linq;
using System.Text.RegularExpressions;


namespace codewars4
{
    class Program
    {
        //not working need fix


        public static string DuplicateEncode(string word)
        {
            char[] arr = word.Select(i => char.Parse(i.ToString())).ToArray();
            int[] mouse = new int[arr.Length];


             for (int i = 0; i < arr.Length; i++)
             {
                 for (int j = 0; j < arr.Length; j++)
                 {
                    if (i == j) { }
                    else 
                    { 
                        if (arr[i] == arr[j])
                        {
                           mouse [j] = 1;
                        }

                    }
                }
            }
            for (int i=0; i < arr.Length ; i++) 
            {
                if (mouse[i] == 1)
                    arr[i] = ')';
                else
                    arr[i] = '(';
            } 


            word = string.Join("", arr);

            Console.WriteLine(word);

            return word;
        }

        static void Main(string[] args)
        {
            string input = "anya";

            DuplicateEncode(input);
        }
    }
}
