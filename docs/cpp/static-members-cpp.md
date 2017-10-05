---
title: "Статические члены (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 568ceedfcc3cd470cdd9003dfb41c691f9986f25
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="static-members-c"></a>Статические члены (C++)
Классы могут содержать статические данные-члены и функции-члены. Если данные-член объявлены как **статических**, для всех объектов класса поддерживается только одна копия данных.
  
 Статические данные-члены не входят в состав объектов указанного типа класса. В результате объявление статических данных-члена не является определением. Данные-член объявляются в области видимости класса, однако определение выполняется в области видимости файла. Такие статические члены имеют внешнюю компоновку; Это показано в приведенном ниже примере.  
  
```  
// static_data_members.cpp  
class BufferedOutput  
{  
public:  
   // Return number of bytes written by any object of this class.  
   short BytesWritten()  
   {  
      return bytecount;  
   }  
  
   // Reset the counter.  
   static void ResetCount()  
   {  
      bytecount = 0;  
   }  
  
   // Static member declaration.  
   static long bytecount;  
};  
  
// Define bytecount in file scope.  
long BufferedOutput::bytecount;  
  
int main()  
{  
}  
```  
  
 В предыдущем примере член `bytecount` объявляется в классе `BufferedOutput`, однако его определение должно находиться за пределами объявления класса.  
  
 На статические данные-члены можно ссылаться без указания ссылок на объект типа класса. Число байтов, записываемых с помощью объектов `BufferedOutput`, можно получить следующим образом.  
  
```  
long nBytes = BufferedOutput::bytecount;  
```  
  
 Для того чтобы существовал статический член, не обязательно, чтобы существовали любые объекты типа класса. Статические члены можно получить с помощью выбора члена (**.** и ** -> **) операторы. Пример:  
  
```  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 В предыдущем случае не ссылка на объект (`Console`) не вычисляется; возвращается значение статического объекта `bytecount`.  
  
 Статические данные-члены подчиняются правилам доступа члена класса, поэтому закрытый доступ к ним допускается только для функций и дружественных объектов класса-члена. Эти правила описаны в [управления доступом к членам](../cpp/member-access-control-cpp.md). Имеется исключение: статические данные-члены должны быть определены в области видимости файла, вне зависимости от их ограничений доступа. Если данные-член необходимо инициализировать явным образом, инициализатор должен быть предоставлен в определении.  
  
 Тип статического члена не квалифицируется его именем класса. Таким образом, `BufferedOutput::bytecount` имеет тип `long`.  
  
## <a name="see-also"></a>См. также  
 [Классы и структуры](../cpp/classes-and-structs-cpp.md)
