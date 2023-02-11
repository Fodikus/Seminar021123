# Seminar021123
Домашняя работа №5 к семинару "Знакомство с языками программирования"

# Задача 34: Задайте массив заполненный случайными положительными трёхзначными числами. Напишите программу, которая покажет количество чётных чисел в массиве.
```
void InputArray(int[] array)
{
    for (int i = 0; i < array.Length; i++)
        array[i] = new Random().Next(100, 999);
}

int NumberEven(int[] array)
{
    int nummaEven = 0;
    foreach (int i in array)
    {
        if (i % 2==0)
            nummaEven ++;
    }
    return nummaEven;
}

Console.Clear();
Console.Write("Введите кол-во элементов: ");
int n = Convert.ToInt32(Console.ReadLine());
int[] array = new int[n];
InputArray(array);
int s = NumberEven(array);
Console.WriteLine($"Количество чётных чисел в массиве: [{string.Join(", ", array)}] -> {s} ");
```

# Задача 36: Задайте одномерный массив, заполненный случайными числами. Найдите сумму элементов, стоящих на нечётных позициях.
```
void InputArray(int[] array)
{
    for (int i = 0; i < array.Length; i++)
        array[i] = new Random().Next(-100, 100);
}

int SummaUneven(int[] array)
{
    int summaUneven = 0;
    for (int i = 1; i < array.Length; i+=2)
        summaUneven += array[i];
    return summaUneven;
}

Console.Clear();
Console.Write("Введите кол-во элементов: ");
int n = Convert.ToInt32(Console.ReadLine());
int[] array = new int[n];
InputArray(array);
int s = SummaUneven(array);
Console.WriteLine($"Сумма элементов, стоящих на нечётных позициях: [{string.Join(", ", array)}] -> {s} ");
```

# Задача 38: Задайте массив вещественных(дробных) чисел. Найдите разницу между максимальным и минимальным элементов массива.
```
void InputArray(double[] array)
{
    for (int i = 0; i < array.Length; i++)
        array[i] = new Random().Next(-100*100, 100*100)/100.0;
}

Console.Clear();
Console.Write("Введите кол-во элементов: ");
int n = Convert.ToInt32(Console.ReadLine());
double[] array = new double[n];
InputArray(array);
double min = 0;
double max = 0;
foreach (double i in array)  // Поиск максимального и минимального значения
{
    if (min > i) min = i;
    if (max < i) max = i;
}
double result = max - min;
Console.WriteLine($"Разница между максимальной и минимальным элементом массива: [{string.Join("; ", array)}] -> {Math.Round(result, 2)} ");
```

Массивы(https://acmp.ru/asp/do/index.asp?main=task&id_course=1&id_section=5&id_topic=114&id_problem=703)
```
void InputArray(int[] array)
{
    for (int i = 0; i < array.Length; i++)
        array[i] = new Random().Next(1, 31);
}

Console.Clear();
Console.Write("Введите кол-во элементов: ");
int n = Convert.ToInt32(Console.ReadLine());
while ((n < 1) || (n > 100))
{
    Console.WriteLine($"Вы ошиблись! Количество элементов целочисленного массива не должно быть меньше 1 и превышать 100! \nВведите кол-во элементов: ");
    n = Convert.ToInt32(Console.ReadLine());
}

int[] array = new int[n];
InputArray(array);
Console.WriteLine($"Начальный массив: [{string.Join(" ", array)}]");

int summaEven = 0;
int summaUneven = 0;
foreach (int i in array)
{
    if (i % 2==0)
        summaEven ++;
    else
        summaUneven ++;
}

int[] arrayThrees = new int[summaUneven];
int[] arrayFours = new int[summaEven];
int n1 = 0;
int n2 = 0;
foreach (int i in array)
{
    if (i % 2==0)
    {   
        arrayFours[n1] = i;
        n1++;
    }
    else
    {
        arrayThrees[n2] = i;
        n2++;
    }
}

Console.WriteLine($"Дни в которые Вася получил тройки: [{string.Join(" ", arrayThrees)}]");
Console.WriteLine($"Дни в которые Вася получил четверки: [{string.Join(" ", arrayFours)}]");

string result = "YES";
if (arrayThrees.Length > arrayFours.Length)
{
    result = "NO";
}
Console.WriteLine($"Расчитывать результат английского языка на 4? {result}");
```
