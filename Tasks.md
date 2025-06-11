# Решения тренировочных задач

## 1
### Входные данные: В единственной строке входных данных заданы целочисленные a и b (1 ≤ a,b ≤ 1000).
### Выходные данные: Выведите a+b.
```csharp
using System.Collections.Generic;
using System.Linq;
using System;

namespace Learn{
    class Program
    {
        static void Main(string[] args)
        {
			      string stringInput = Console.ReadLine();
			      string[] stringArrayInput = stringInput.Split(' ');
			      Console.WriteLine(int.Parse(stringArrayInput[0]) + int.Parse(stringArrayInput[1]));
            Console.ReadLine();
		    }
	  }
}
```

## 2
### Входные данные: В первой строке задано целое число n (1 ≤ n ≤ 10000). Вторая строка содержит n целых чисел, каждое от 1 до 10000, включительно.
### Выходные данные: Выведите искомую сумму.
```csharp
using System.Collections.Generic;
using System.Linq;
using System;

namespace Learn{
    class Program
    {
        static void Main(string[] args)
        {
            short count = short.Parse(Console.ReadLine());
            string[] stringArrayInput = Console.ReadLine().Split(' ');
            uint summ = 0;
            foreach (string temp in stringArrayInput)
            {
                summ += uint.Parse(temp);
            }
            Console.WriteLine(summ);
            Console.ReadLine();
		}
	}
}
```

## 3
### Входные данные: В первой строке задано целое число n (1 ≤ n ≤ 10000). Вторая строка содержит n целых чисел, каждое от 1 до 10000 включительно.
### Выходные данные: Выведите искомую альтернированную сумму.
###Альтернированной суммой заданной последовательности n чисел a1, a2,..., an называется число s=a1-a2+a3-a4+.... 
###В альтернированной сумме знаки слагаемых чередуются, альтернация начинается со знака "+". По заданной последовательности целых чисел выведите ее альтернированную сумму.
```csharp
using System.Collections.Generic;
using System.Linq;
using System;

namespace Learn{
    class Program
    {
        static void Main(string[] args)
        {
            int count = short.Parse(Console.ReadLine());
            string[] stringArrayInput = Console.ReadLine().Split(' ');
            int summ = 0;
            bool flagPlus = true;
            foreach (string temp in stringArrayInput)
            {
                //summ += flagPlus?  int.Parse(temp) : (int.Parse(temp) * -1);
                summ += int.Parse(temp) * (flagPlus ? 1 : -1);
                flagPlus = !flagPlus;
            }
            Console.WriteLine(summ);
            Console.ReadLine();
		}
	}
}
```

## 4
### Входные данные: В первой строке задано целое число y (1000 ≤ y ≤ 2100).
### Выходные данные: Выведите 0 или 1 в соответствии с условием задачи.
### Год является високосным, если он кратен 4 и при этом не кратен 100, либо кратен 400. 
### Так, годы 1700, 1800 и 1900 не были високосными, так как они кратны 100 и не кратны 400. Год 2000 — високосный, так как он кратен 400. 2100, 2200 и 2300 — не високосные.
```csharp
using System.Collections.Generic;
using System.Linq;
using System;

namespace Learn{
    class Program
    {
        static void Main(string[] args)
        {
            uint UintInput = uint.Parse(Console.ReadLine());

            bool flag = (((UintInput % 4) == 0 && (UintInput % 100) != 0) || (UintInput % 400) == 0);

            byte isLeap = flag? (byte)1 : (byte)0;

            Console.WriteLine(isLeap);

            Console.ReadLine();
		}
	}
}
```

## 5
### Входные данные: В первой строке записано целое число n (1 ≤ n ≤ 10000). Вторая строка содержит последовательность целых чисел a1, a2,..., an (-10000 ≤ ai ≤ 10000).
### Выходные данные: Выведите искомый индекс.

```csharp
using System.Collections.Generic;
using System.Linq;
using System;

namespace Learn{
    class Program
    {
        static void Main(string[] args)
        {
            short shortInput = short.Parse(Console.ReadLine());
            string[] strInput = Console.ReadLine().Split(' ');
            int min = 10000;
            foreach (string element in strInput)
            {
                min = int.Parse(element) < min ? int.Parse(element) : min;
            }
            int result = 0;
            for (int i = 0; i < shortInput; i++)
            {
                if (int.Parse(strInput[i]) == min)
                {
                    result = i + 1;
                    break;
                }
            }
            Console.WriteLine(result);
            Console.ReadLine();
        }
    }
}
```
