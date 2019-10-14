# program
这里存放C#代码





using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace test
{
    class Program
    {
        static void Main(string[] args)
        {
            int number1 = 0, number2 = 0;
            string str1,str2="";
            Console.WriteLine("若输入整数请输入y");
            if (Console.ReadLine() == "y")
            {
                Console.WriteLine("请输入一个整数");

                while (true)
                {
                    try
                    {
                        number1 = Convert.ToInt32(Console.ReadLine());
                        break;
                    }
                    catch
                    {
                        Console.WriteLine("输入的不是整数！");
                    }
                }
                Console.WriteLine("请输入一个运算符");
                string x = Console.ReadLine();

                Console.WriteLine("请输入一个整数");
                while (true)
                {
                    try
                    {
                        number2 = Convert.ToInt32(Console.ReadLine());
                        break;
                    }
                    catch
                    {
                        Console.WriteLine("输入的不是整数！");
                    }
                }


                calculator c = new calculator();
                Console.WriteLine(c.Equals(number1, number2) ? "两个整数相等" : "两个整数不相等");
                switch (x)
                {
                    case "+":
                        Console.WriteLine(c.Add(number1, number2));
                        break;
                    case "-":
                        Console.WriteLine(c.Sub(number1, number2));
                        break;
                    case "*":
                        Console.WriteLine(c.Mult(number1, number2));
                        break;
                    case "/":
                        Console.WriteLine(c.Divide(number1, number2));
                        break;

                    default: Console.WriteLine("输入运算符错误！");
                        break;
                }
            }
            else
            {
                Console.WriteLine("请输入一个字符串");
                str1=Console.ReadLine();
                Console.WriteLine("请输入一个运算符");
                string x = Console.ReadLine();
                Console.WriteLine("请输入一个字符串");
                str2=Console.ReadLine();
                calculator c = new calculator();
                switch (x)
                {
                    case "+":
                            Console.WriteLine(c.AddStr(str1, str2));
                            break;
                    case "-":
                            Console.WriteLine(c.SubStr(str1, str2));
                            break;
                    default: Console.WriteLine("输入运算符错误！");
                            break;
                }
            }

        }
    }
    class calculator
    {
        public int Add(int a, int b)
        {
            int c = a + b;
            return c;
        }
        public string AddStr(string a,string b)
        {
            return string.Concat(a, b);
        }
        public int Sub(int a, int b)
        {
            int c = a - b;
            return c;
        }
        public string SubStr(string a, string b)
        {
            return a.Replace(b, "");
        }
        public int Mult(int a, int b)
        {
            int c = a * b;
            return c;
        }
        public int Divide(int a, int b)
        {
            int c = a / b;
            return c;
        }
        public bool Equals(int a, int b)
        {
            if (a == b)
                return true;
            else
                return false;
        }
    }
    
    
}
