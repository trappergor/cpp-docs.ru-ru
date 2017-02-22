---
title: "Класс checked_array_iterator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/checked_array_iterator"
  - "checked_array_iterator"
  - "std::checked_array_iterator"
  - "std.checked_array_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked_array_iterator"
  - "checked_array_iterator - класс"
  - "checked_array_iterator, синтаксис"
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# Класс checked_array_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс `checked_array_iterator` предоставляет возможность преобразовать массив или указатель в проверенный итератор.  Используйте этот класс в качестве оболочки \(с помощью функции [make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)\) для необработанных указателей или массивов, как способ целенаправленного выполнения проверки и управления непроверенными предупреждениями об указателях вместо глобального отключения данных предупреждений.  При необходимости можно использовать непроверенная версию данного класса, [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md).  
  
> [!NOTE]
>  Этот класс является предоставляемым Microsoft расширением стандартной библиотеки C\+\+.  Код, реализованный с помощью этой функции, нельзя перенести в стандартные среды сборки C, не поддерживающие это расширение Microsoft.  Пример создания кода, не требующего использования данного класса — это второй пример, представленный ниже.  
  
## Синтаксис  
  
```  
template <class _Iterator>  
    class checked_array_iterator;  
```  
  
## Заметки  
 Этот класс определяется в пространстве имен [stdext](../Topic/stdext%20Namespace.md).  
  
 Дополнительные сведения и пример кода функции проверяемого итератора см. в статье [Проверяемые итераторы](../standard-library/checked-iterators.md).  
  
## Пример  
 В следующем примере показано, как задать и использовать проверенный итератор массива.  
  
 Если назначение не может вместить все скопированные элементы \(например, в случае изменения строки\):  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
```  
  
 по  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));  
```  
  
 Произойдет ошибка исполняющей среды.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
```  
  
  **\( 0 1 2 3 4 \)**  
**\( 0 1 2 3 4 \)**   
## Пример  
 Чтобы исключить потребность в применении класса `checked_array_iterator` при использовании алгоритмов стандартной библиотеки C\+\+, попробуйте применить `vector` вместо динамически выделяемого массива.  В следующем примере показано, как это сделать.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
```  
  
  **0 1 2 3 4 5 6 7 8 9**   
### Конструкторы  
  
|||  
|-|-|  
|[checked\_array\_iterator](../Topic/checked_array_iterator::checked_array_iterator.md)|Формирование итератора `checked_array_iterator` по умолчанию или итератора `checked_array_iterator` из базового итератора.|  
  
### Typedefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/checked_array_iterator::difference_type.md)|Тип, обеспечивающий разницу между двумя итераторами `checked_array_iterator`, которые ссылаются на элементы в одном контейнере.|  
|[pointer](../Topic/checked_array_iterator::pointer.md)|Тип, содержащий указатель на элемент, к которому обращается итератор `checked_array_iterator`.|  
|[ссылка](../Topic/checked_array_iterator::reference.md)|Тип, содержащий ссылку на элемент, к которому обращается итератор `checked_array_iterator`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[База](../Topic/checked_array_iterator::base.md)|Восстановление базового итератора из соответствующего итератора `checked_array_iterator`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/checked_array_iterator::operator==.md)|Проверка двух итераторов `checked_array_iterator` на равенство.|  
|[operator\!\=](../Topic/checked_array_iterator::operator!=.md)|Проверка двух итераторов `checked_array_iterator` на неравенство.|  
|[Оператор \<](../Topic/checked_array_iterator::operator%3C.md)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше итератора `checked_array_iterator` с правой стороны.|  
|[Оператор \>](../Topic/checked_array_iterator::operator%3E.md)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше итератора `checked_array_iterator` с правой стороны.|  
|[Оператор \<\=](../Topic/checked_array_iterator::operator%3C=.md)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора меньше или равен итератору `checked_array_iterator` с правой стороны.|  
|[Оператор \>\=](../Topic/checked_array_iterator::operator%3E=.md)|Проверка на то, что итератор `checked_array_iterator` с левой стороны оператора больше или равен итератора `checked_array_iterator` с правой стороны.|  
|[operator\*](../Topic/checked_array_iterator::operator*.md)|Возвращение элемента, к которому обращается `checked_array_iterator`.|  
|[operator\-\>](../Topic/checked_array_iterator::operator-%3E.md)|Возвращение указателя на элемент, к которому обращается `checked_array_iterator`.|  
|[operator\+\+](../Topic/checked_array_iterator::operator++.md)|Увеличение `checked_array_iterator` до следующего элемента.|  
|[operator\-\-](../Topic/checked_array_iterator::operator--.md)|Уменьшение `checked_array_iterator` до предыдущего элемента.|  
|[operator \+\=](../Topic/checked_array_iterator::operator+=.md)|Добавление заданного смещения к итератору `checked_array_iterator`.|  
|[operator \+](../Topic/checked_array_iterator::operator+.md)|Добавление смещения к итератору и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.|  
|[operator\-\=](../Topic/checked_array_iterator::operator-=.md)|Уменьшение заданного смещения из `checked_array_iterator`.|  
|[operator\-](../Topic/checked_array_iterator::operator-.md)|Уменьшение смещения из итератора и возврат нового итератора `checked_array_iterator`, который обращается к вставленному элементу в новой позиции смещения.|  
|[operator&#91;&#93;](../Topic/checked_array_iterator::operator.md)|Возврат ссылки на смещение элемента из элемента, к которому обращается `checked_array_iterator`, на указанное число позиций.|  
  
## Требования  
 **Заголовок:** \<iterator\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [\<iterator\>](../standard-library/iterator.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)