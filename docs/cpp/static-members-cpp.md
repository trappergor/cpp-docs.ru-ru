---
title: Статические члены (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fba58883db0f5936a8f3dedc1e0c4a19fb0aafa9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086204"
---
# <a name="static-members-c"></a>Статические члены (C++)

Классы могут содержать статические данные-члены и функции-члены. Если данные-член, объявленный как **статический**, только одна копия данных сохраняется для всех объектов данного класса.

Статические данные-члены не входят в состав объектов указанного типа класса. В результате объявление статических данных-члена не является определением. Данные-член объявляются в области видимости класса, однако определение выполняется в области видимости файла. Такие статические члены имеют внешнюю компоновку; Это показано в приведенном ниже примере.

```cpp
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

```cpp
long nBytes = BufferedOutput::bytecount;
```

Для того чтобы существовал статический член, не обязательно, чтобы существовали любые объекты типа класса. Статические члены также может осуществляться с помощью выбора члена (**.** и **->**) операторы. Пример:

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

В предыдущем случае не ссылка на объект (`Console`) не вычисляется; возвращается значение статического объекта `bytecount`.

Статические данные-члены подчиняются правилам доступа члена класса, поэтому закрытый доступ к ним допускается только для функций и дружественных объектов класса-члена. Эти правила описываются в [управления доступом к членам](../cpp/member-access-control-cpp.md). Имеется исключение: статические данные-члены должны быть определены в области видимости файла, вне зависимости от их ограничений доступа. Если данные-член необходимо инициализировать явным образом, инициализатор должен быть предоставлен в определении.

Тип статического члена не квалифицируется его именем класса. Таким образом, тип `BufferedOutput::bytecount` — **long**.

## <a name="see-also"></a>См. также

[Классы и структуры](../cpp/classes-and-structs-cpp.md)