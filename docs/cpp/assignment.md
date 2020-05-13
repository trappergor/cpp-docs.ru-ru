---
title: Назначение
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
ms.openlocfilehash: f1697a8de3dff6c46de01db6bbff5447c03b6282
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190707"
---
# <a name="assignment"></a>Назначение

Оператор присваивания ( **=** ), строго говоря, является бинарным оператором. Его объявление идентично объявлению любого другого бинарного оператора, со следующими исключениями:

- Он должен быть нестатической функцией-членом. **Оператор =** не может быть объявлен как функция, не являющийся членом.
- Он не наследуется производными классами.
- Компилятор может создать функцию **operator =** по умолчанию для типов классов, если она не существует.

В следующем примере показано, как объявить оператор присваивания:

```cpp
class Point
{
public:
    int _x, _y;

    // Right side of copy assignment is the argument.
    Point& operator=(const Point&);
};

// Define copy assignment operator.
Point& Point::operator=(const Point& otherPoint)
{
    _x = otherPoint._x;
    _y = otherPoint._y;

    // Assignment operator returns left side of assignment.
    return *this;
}

int main()
{
    Point pt1, pt2;
    pt1 = pt2;
}
```

Переданный аргумент является правой стороной выражения. Оператор возвращает объект для сохранения поведения оператора присваивания, который после завершения присваивания возвращает значение левой части. Это позволяет создавать цепочки назначений, например:

```cpp
pt1 = pt2 = pt3;
```

Оператор присваивания копии не следует путать с конструктором копии. Второй метод вызывается во время создания нового объекта из существующего.

```cpp
// Copy constructor is called--not overloaded copy assignment operator!
Point pt3 = pt1;

// The previous initialization is similar to the following:
Point pt4(pt1); // Copy constructor call.
```

> [!NOTE]
> Рекомендуется следовать [правилам трех](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) , чтобы класс, определяющий оператор присваивания копии, также явно определял конструктор копии, деструктор и, начиная с c++ 11, конструктор перемещения и оператор присваивания перемещения.

## <a name="see-also"></a>См. также раздел

- [Перегрузка операторов](../cpp/operator-overloading.md)
- [Конструкторы копий и операторы присваивания копий (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)
