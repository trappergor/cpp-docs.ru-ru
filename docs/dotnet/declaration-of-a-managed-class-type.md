---
title: Объявление управляемых типов классов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- classes [C++], managed
- class keyword [C++], CLR
- __value keyword
- value types, declaring
- value keyword [C++]
- managed classes
- interface class keyword
- ref keyword [C++]
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f9ceb0867fbdfbbdb46075662fca802d1ee0bba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393676"
---
# <a name="declaration-of-a-managed-class-type"></a>Объявление управляемых типов классов

Способ объявления ссылочного типа класса изменилось с управляемых расширений для C++ в Visual C++.

В управляемых расширениях предшествовало ссылочный класс `__gc` ключевое слово. В новом синтаксисе `__gc` ключевое слово заменяется одним из двух составных ключевых слов: `ref class` или `ref struct`. Выбор `struct` или `class` указывает общий (для `struct`) или private (для `class`) уровень доступа по умолчанию, его члены, объявленные в начальном разделе без метки основной части типа.

Аналогичным образом, в управляемых расширениях типу значения классов предшествовало `__value` ключевое слово. В новом синтаксисе `__value` ключевое слово заменяется одним из двух составных ключевых слов: `value class` или `value struct`.

Тип интерфейса, в управляемых расширениях указывалась с ключевым словом `__interface`. В новом синтаксисе, оно будет заменено `interface class`.

Например следующие объявления класса в управляемых расширений:

```
public __gc class Block {};     // reference class
public __value class Vector {}; // value class
public __interface IFooBar {};  // interface class
```

В новом синтаксисе те же объявления выглядят следующим образом:

```
public ref class Block {};         // reference class
public value class Vector {};      // value class
public interface class IFooBar {}; // interface class
```

## <a name="specifying-the-class-as-abstract"></a>Определение класса как абстрактный

В управляемых расширениях поместить ключевое слово `__abstract` перед `class` ключевое слово (до или после `__gc`) чтобы указать, что класс является неполным и что объекты класса не может создаваться в рамках программы:

```
public __gc __abstract class Shape {};
public __gc __abstract class Shape2D: public Shape {};
```

В новом синтаксисе вами `abstract` контекстное ключевое слово после имени класса и перед тело класса, базовый класс производным списком или точкой с запятой.

```
public ref class Shape abstract {};
public ref class Shape2D abstract : public Shape{};
```

Само собой семантическое значение не изменяется.

## <a name="specifying-the-class-as-sealed"></a>Определение класса как запечатанный

В управляемых расширениях поместить ключевое слово `__sealed` перед `class` ключевое слово (до или после `__gc`) для указания, что объекты класса не может наследоваться от:

```
public __gc __sealed class String {};
```

В новом синтаксисе вами `sealed` контекстное ключевое слово после имени класса и перед тело класса, базовый класс производным списком или точкой с запятой.

Можно создать производный класс и запечатать его. Например `String` класс является неявно производным от `Object`. Запечатывание класс преимущество заключается в том, что он поддерживает статическое разрешение (то есть во время компиляции) всех вызовов виртуальных функций через запечатанного объекта ссылочного класса. Это обусловлено `sealed` описатель гарантирует, что `String` дескриптора отслеживания не может ссылаться на производный класс, который предоставляет переопределения экземпляров виртуального метода, вызываемого. Вот пример запечатанного класса в новом синтаксисе:

```
public ref class String sealed {};
```

Также можно определить класс одновременно как абстрактный и запечатанный — это особое состояние, указывающее, статический класс. Это описывается в документации по CLR следующим образом:

«Объект типа, который является оба `abstract` и `sealed` должен содержать только статические члены и являться тем, что в некоторых языках называется пространством имен.»

Например вот объявление абстрактного запечатанного класса с использованием синтаксиса управляемых расширений:

```
public __gc __sealed __abstract class State {
public:
   static State() {}
   static bool inParamList();

private:
   static bool ms_inParam;
};
```

а вот это объявление, преобразуются в новый синтаксис:

```
public ref class State abstract sealed {
public:
   static State();
   static bool inParamList();

private:
   static bool ms_inParam;
};
```

## <a name="clr-inheritance-specifying-the-base-class"></a>CLR наследования: Указание базового класса

В модели объектов CLR поддерживается только общедоступный одиночное наследование. Тем не менее управляемых расширений сохраняются интерпретацию ISO-C++ по умолчанию базового класса без ключевого слова доступа как и при указании закрытого наследования. Это означало, что каждое объявление наследования CLR должна была обеспечить `public` ключевое слово, чтобы переопределить стандартную интерпретацию.

```
// Managed Extensions: error: defaults to private derivation
__gc class Derived : Base {};
```

В определении нового синтаксиса отсутствие ключевого слова доступа указывает открытого наследования в определении наследования со средой CLR. Таким образом `public` слово доступа теперь является необязательным. Хотя это не требует каких-либо изменений управляемых расширений для кода C++, создать список этого изменения для обеспечения полноты.

```
// New syntax: ok: defaults to public derivation
ref class Derived : Base{};
```

## <a name="see-also"></a>См. также

[Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[abstract](../windows/abstract-cpp-component-extensions.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)