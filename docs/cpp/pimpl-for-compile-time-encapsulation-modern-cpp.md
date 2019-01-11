---
title: Pimpl для инкапсуляции времени компиляции (современный C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 6e114e2802dd4b2e5d1497867e2224be90c4752d
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220690"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Pimpl для инкапсуляции времени компиляции (современный C++)

*Pimpl идиому* — это современный C++ способ скрыть реализацию, чтобы свести к минимуму взаимозависимость и для отдельных интерфейсов. Pimpl — сокращение «указатель на реализацию.» Может уже быть знакомы с этой концепцией, но по-другому, например как Чеширский Кот или брандмауэр компилятора идиому она известна.

## <a name="why-use-pimpl"></a>Зачем использовать pimpl?

Вот, как pimpl идиому можно улучшить жизненный цикл разработки программного обеспечения:

- Минимизация компиляции зависимости.

- Разделение интерфейс и реализацию.

- Переносимость.

## <a name="pimpl-header"></a>Pimpl заголовка

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

Pimpl идиому предотвращает каскадные перестроения и макеты непрочные объекта. Она хорошо подходит для (транзитивно) популярных типов.

## <a name="pimpl-implementation"></a>Реализация Pimpl

Определение `impl` класс в CPP-файле.

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

Рассмотрите возможность добавления поддержки для специализации замены не создающие исключения.

## <a name="see-also"></a>См. также

[Возвращение к C++ (современный C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)
