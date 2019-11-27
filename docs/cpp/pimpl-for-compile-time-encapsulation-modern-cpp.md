---
title: Pimpl для инкапсуляции времени компиляции (современный C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: f1eb06ad3a52be486f085babf699677951b1ee71
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245177"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl для инкапсуляции времени компиляции (современный C++)

*Идиома Пимпл* — это современный C++ метод скрытия реализации, для минимального связывания и разделения интерфейсов. Пимпл является коротким для "указателя на реализацию". Возможно, вы уже знакомы с концепцией, но знаете ее по другим именам, таким как Чешир Cat или идиома брандмауэра компилятора.

## <a name="why-use-pimpl"></a>Зачем использовать Пимпл?

Вот как пимплная идиома может улучшить жизненный цикл разработки программного обеспечения:

- Минимизация зависимостей компиляции.

- Разделение интерфейса и реализации.

- Компакт.

## <a name="pimpl-header"></a>Заголовок Пимпл

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Идиом Пимпл позволяет избежать перестроения каскадных и нестабильнымных макетов объектов. Он хорошо подходит для (транзитивно) популярных типов.

## <a name="pimpl-implementation"></a>Реализация Пимпл

Определите класс `impl` в cpp – файле.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Рекомендации

Рассмотрите возможность добавления поддержки для специализации, не создающей исключение.

## <a name="see-also"></a>См. также:

[Добро пожаловать обратно вC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
