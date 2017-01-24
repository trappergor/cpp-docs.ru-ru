---
title: "Практическое руководство. Предоставление контейнера STL/CLR из сборки | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR - контейнеры [STL/CLR]"
  - "STL/CLR, проблемы нескольких сборок"
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Предоставление контейнера STL/CLR из сборки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Контейнеры STL\/CLR, например `list` и `map` реализованы как классы ссылочного шаблона.  Поскольку шаблоны C\+\+ экземпляры во время компиляции, 2 класса шаблона, совпадают сигнатуру, но в разных сборках фактически различные типы.  Это означает, что классы\-шаблоны нельзя использовать через границы сборки.  
  
 Чтобы задать совместное использование нескольких сборок, контейнеры STL\/CLR реализуют универсальный интерфейс <xref:System.Collections.Generic.ICollection%601>.  С помощью этого универсального интерфейса, все языки, поддерживающих универсальные шаблоны, включая C\+\+, C\# и Visual Basic, могут получить контейнеры STL\/CLR.  
  
 В этом разделе показано, как отображать элементы нескольких контейнеров STL\/CLR, написанных на языке C — A. на C\+\+ `StlClrClassLibrary` с именем сборки.  На экране отображается 2 сборки для получения `StlClrClassLibrary`.  Первая сборка написана на языке C\+\+ и втором в C\#.  
  
 Если обе сборки записываются в C\+\+, доступ к универсальный интерфейс контейнера с помощью своего typedef `generic_container`.  Например, если имеется контейнере типа `cliext::vector<int>`, его универсальный интерфейс выглядит следующим образом: `cliext::vector<int>::generic_container`.  Аналогичным образом можно получить через итератор универсальным интерфейсом с помощью typedef `generic_iterator`, как в: `cliext::vector<int>::generic_iterator`.  
  
 Поскольку эти typedef объявляются в файлах заголовка C\+\+, сборки, написанные на других языках, не могут использовать их.  Поэтому, чтобы получить универсальный интерфейс для `cliext::vector<int>` в C\# или любом другом языке .NET, используйте `System.Collections.Generic.ICollection<int>`.  Для итерации данной коллекции используйте цикл `foreach`.  
  
 В следующей таблице перечислены универсальный интерфейс, каждый контейнер STL\/CLR реализует:  
  
|Контейнер STL\/CLR|Интерфейс Generic|  
|------------------------|-----------------------|  
|deque\<T\>|ICollection\<T\>|  
|hash\_map\<K, V\>|IDictionary\<K, V\>|  
|hash\_multimap\<K, V\>|IDictionary\<K, V\>|  
|hash\_multiset\<T\>|ICollection\<T\>|  
|hash\_set\<T\>|ICollection\<T\>|  
|list\<T\>|ICollection\<T\>|  
|КАРТА\<K, V\>|IDictionary\<K, V\>|  
|multimap\<K, V\>|IDictionary\<K, V\>|  
|multiset\<T\>|ICollection\<T\>|  
|set\<T\>|ICollection\<T\>|  
|vector\<T\>|ICollection\<T\>|  
  
> [!NOTE]
>  Поскольку `queue`, `priority_queue` и контейнеры `stack` не поддерживают итераторы, они не реализуют универсальные интерфейсы и не могут быть полученной доступ между сборкой.  
  
## Пример 1  
  
### Описание  
 В этом примере мы объявляем класс C\+\+, который содержит закрытых сведений о членах STL\/CLR.  Затем мы объявляем открытые методы, чтобы предоставить доступ к закрытым коллекциям класса.  Рекомендуется делаем его в 2 различными способами, один для клиентов C\+\+ — один для других клиентов .NET.  
  
### Код  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Пример 2  
  
### Описание  
 В этом примере мы снабжаем класс объявлен в пример.  Для создания клиентов для использования этой библиотеки классов мы используем инструмента **mt.exe** чтобы внедрить файл манифеста в библиотеке DLL.  Дополнительные сведения см. в комментариях к коду.  
  
 Дополнительные сведения о средстве очевидных и параллельных сборок см. в разделе [Построение изолированных приложений и параллельных сборок C\/C\+\+](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### Код  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Пример 3  
  
### Описание  
 В этом примере мы создадим клиент C\+\+, который использует созданную библиотеку классов в примерах 1 и 2.  Этот клиент использует typedef `generic_container` контейнеров STL\/CLR для итерации контейнерами и отображать их содержимое.  
  
### Код  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### Output  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## Пример 4  
  
### Описание  
 В этом примере мы создадим клиент C\#, использующий созданную библиотеку классов в примерах 1 и 2.  Этот клиент использует методы <xref:System.Collections.Generic.ICollection%601> контейнеров STL\/CLR для итерации контейнерами и отображать их содержимое.  
  
### Код  
  
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
  
### Output  
  
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
  
## См. также  
 [Библиотека STL\/CLR](../dotnet/stl-clr-library-reference.md)