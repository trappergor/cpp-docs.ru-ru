---
title: Инициализация классов и структур без конструкторов (C++)
ms.date: 10/17/2018
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 4f696f4fc8862b953e40a03c96b88d1a0b7f720b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547333"
---
# <a name="initializing-classes-and-structs-without-constructors-c"></a>Инициализация классов и структур без конструкторов (C++)

Не всегда обязательно определять конструктор для класса (особенно для относительно простых классов). Пользователи могут использовать для объектов класса или структур унифицированную инициализацию, как показано в следующем примере:

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

Обратите внимание, что когда класс или структура не имеет конструктора, предоставляет элементов списка в порядке, что элементы объявлены в классе. Если класс имеет конструктор, предоставляющих элементы в порядке указания параметров.

## <a name="see-also"></a>См. также

[Классы и структуры](../cpp/classes-and-structs-cpp.md)<br/>
[Конструкторы](../cpp/constructors-cpp.md)
