---
title: Инициализация массивов
ms.date: 11/04/2016
helpviewer_keywords:
- initializing arrays [C++]
- arrays [C++], initializing
ms.assetid: 41efe5f0-15b5-4f49-9196-c4902f8fc705
ms.openlocfilehash: e055e7759865fc151176097c6f0afd9ee237f4c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447090"
---
# <a name="initializing-arrays"></a>Инициализация массивов

Если класс имеет конструктор, массивы этого класса инициализируются конструктором. Если число элементов в списке инициализаторов меньше числа элементов в массиве, для остальных элементов используется конструктор по умолчанию. Если конструктор по умолчанию для класса не определен, список инициализаторов должен быть полным, т. е. для каждого элемента массива должен иметься один инициализатор.

Рассмотрим класс `Point`, определяющий два конструктора:

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

Первый элемент `aPoint` создается с помощью конструктора `Point( int, int )`, а оставшиеся два элемента — с помощью конструктора по умолчанию.

Массивы статических членов (ли **const** или нет) могут инициализироваться в своих определениях (вне объявления класса). Пример:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```