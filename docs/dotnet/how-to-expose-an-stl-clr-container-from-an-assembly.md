---
title: "Как: предоставлять контейнера STL/CLR из сборки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84505edf0877a5ae20d28906dde7f4c709574034
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Практическое руководство. Предоставление контейнера STL/CLR из сборки
Контейнеры STL/CLR, такие как `list` и `map` реализованы как классы ссылки шаблонов. Поскольку C++ шаблонов создаются во время компиляции, два шаблона класса, которые точно такой же сигнатурой, но находятся в разных сборках, это разные типы. Это означает, что классы шаблонов не может использоваться за пределами сборки.  
  
 Чтобы для управления доступом между сборками возможна, контейнеры STL/CLR реализовывать универсальный интерфейс <xref:System.Collections.Generic.ICollection%601>. С помощью этого универсального интерфейса, все языки, которые поддерживает универсальные шаблоны, включая C++, C# и Visual Basic, можно получить доступ к контейнеры STL/CLR.  
  
 В этом разделе показано, как отображение элементов несколькими контейнерами STL/CLR, записанных в сборке C++ с именем `StlClrClassLibrary`. Далее показано два сборкам получать доступ к `StlClrClassLibrary`. Первая сборка языке C++, а вторая в C#.  
  
 Если обе сборки на языке C++, можно получить доступ к универсальный интерфейс контейнера с помощью его `generic_container` typedef. Например, если у вас есть контейнер типа `cliext::vector<int>`, то его универсальный интерфейс: `cliext::vector<int>::generic_container`. Аналогичным образом можно получить итератор через универсальный интерфейс с помощью `generic_iterator` typedef, как: `cliext::vector<int>::generic_iterator`.  
  
 Поскольку эти определения типов, объявляются в файлах заголовка C++, их нельзя использовать в сборках, написанных на других языках. Таким образом Чтобы получить доступ к универсальному интерфейсу для `cliext::vector<int>` в C# или любом другом языке .NET, используйте `System.Collections.Generic.ICollection<int>`. Для перебора этой коллекции, используйте `foreach` цикла.  
  
 В следующей таблице перечислены универсальный интерфейс, который реализует каждый контейнер STL/CLR:  
  
|Контейнера STL/CLR|Универсальный интерфейс|  
|------------------------|-----------------------|  
|deque < T\>|Интерфейс ICollection < T\>|  
|hash_map < K, V >|IDictionary < K, V >|  
|hash_multimap < K, V >|IDictionary < K, V >|  
|hash_multiset < T\>|Интерфейс ICollection < T\>|  
|hash_set < T\>|Интерфейс ICollection < T\>|  
|список < T\>|Интерфейс ICollection < T\>|  
|карта < K, V >|IDictionary < K, V >|  
|Множественное сопоставление < K, V >|IDictionary < K, V >|  
|MULTISET < T\>|Интерфейс ICollection < T\>|  
|Задайте < T\>|Интерфейс ICollection < T\>|  
|Vector < T\>|Интерфейс ICollection < T\>|  
  
> [!NOTE]
>  Поскольку `queue`, `priority_queue`, и `stack` контейнеры не поддерживают итераторы, их следует реализовывать универсальные интерфейсы и не может быть получен между сборками.  
  
## <a name="example-1"></a>Пример 1  
  
### <a name="description"></a>Описание:  
 В этом примере необходимо объявить класс C++, содержащей закрытые данные члена STL/CLR. Затем необходимо объявить открытые методы для предоставления доступа к коллекциям закрытый класс. Мы делаем его двумя различными способами, один для клиентов C++ и один для других клиентов .NET.  
  
### <a name="code"></a>Код  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="example-2"></a>Пример 2  
  
### <a name="description"></a>Описание:  
 В этом примере мы реализовали класса, объявленного в примере 1. Чтобы клиенты на использование этой библиотеки классов, мы используем инструмента манифеста **mt.exe** встроено в файл манифеста в библиотеку DLL. Дополнительные сведения см. в разделе комментариев кода.  
  
 Дополнительные сведения о средстве манифеста и side-by-side сборок см. в разделе [Построение изолированных приложений C/C++ и сборок Side-by-side](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### <a name="code"></a>Код  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example-3"></a>Пример 3  
  
### <a name="description"></a>Описание:  
 В этом примере мы создадим C++ клиент, использующий библиотеку классов, созданных в примерах 1 и 2. Этот клиент использует `generic_container` определения типов контейнеров STL/CLR для выполнения итерации по контейнеров и для отображения их содержимого.  
  
### <a name="code"></a>Код  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="output"></a>Вывод  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## <a name="example-4"></a>Пример 4  
  
### <a name="description"></a>Описание:  
 В этом примере мы создадим клиент C#, использующий библиотеку классов, созданных в примерах 1 и 2. Этот клиент использует <xref:System.Collections.Generic.ICollection%601> методы из контейнеров STL/CLR для выполнения итерации по контейнеров и для отображения их содержимого.  
  
### <a name="code"></a>Код  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)