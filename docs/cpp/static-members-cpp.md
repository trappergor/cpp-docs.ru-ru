---
title: Статические члены (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: c18b29cf69c2f899fbf06c7cb75ebbd2242ab427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178565"
---
# <a name="static-members-c"></a>Статические члены (C++)

Классы могут содержать статические данные-члены и функции-члены. Если элемент данных объявлен как **статический**, только одна копия данных сохраняется для всех объектов класса.

Статические данные-члены не входят в состав объектов указанного типа класса. В результате объявление статических данных-члена не является определением. Данные-член объявляются в области видимости класса, однако определение выполняется в области видимости файла. Такие статические члены имеют внешнюю компоновку; Проиллюстрируем это на примере.

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

Для того чтобы существовал статический член, не обязательно, чтобы существовали любые объекты типа класса. Доступ к статическим членам также можно получить с помощью выбора члена ( **.** операторы и **->** ). Пример:

```cpp
BufferedOutput Console;

long nBytes = Console.bytecount;
```

В предыдущем случае не ссылка на объект (`Console`) не вычисляется; возвращается значение статического объекта `bytecount`.

Статические данные-члены подчиняются правилам доступа члена класса, поэтому закрытый доступ к ним допускается только для функций и дружественных объектов класса-члена. Эти правила описаны в разделе [Управление доступом к членам](../cpp/member-access-control-cpp.md). Имеется исключение: статические данные-члены должны быть определены в области видимости файла, вне зависимости от их ограничений доступа. Если данные-член необходимо инициализировать явным образом, инициализатор должен быть предоставлен в определении.

Тип статического члена не квалифицируется его именем класса. Таким образом, тип `BufferedOutput::bytecount` является **длинным**.

## <a name="see-also"></a>См. также раздел

[Классы и структуры](../cpp/classes-and-structs-cpp.md)
