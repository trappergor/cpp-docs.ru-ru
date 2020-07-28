---
title: Классы и структуры (C++)
ms.date: 05/07/2019
helpviewer_keywords:
- C++, classes and structs
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: d593f6575fec64aa0eb14c7aa0fcbb5c4eb66691
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220604"
---
# <a name="classes-and-structs-c"></a>Классы и структуры (C++)

В этом разделе приводится информация о классах и структурах C++. В C++ эти конструкции идентичны, за исключением того факта, что структуры по умолчанию открыты для доступа, а классы — закрыты.

Классы и структуры являются конструкциями, в которых пользователь определяет собственные типы. Классы и структуры могут включать данные-члены и функции-члены, позволяющие описывать состояние и поведение данного типа.

В этой статье содержатся следующие разделы:

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [Общие сведения о членах класса](../cpp/class-member-overview.md)

- [Управление доступом к членам](../cpp/member-access-control-cpp.md)

- [Наследование](../cpp/inheritance-cpp.md)

- [Статический члены](../cpp/static-members-cpp.md)

- [Преобразования определяемого пользователем типа](../cpp/user-defined-type-conversions-cpp.md)

- [Изменяемые члены данных (изменяемый спецификатор)](../cpp/mutable-data-members-cpp.md)

- [Объявления вложенных классов](../cpp/nested-class-declarations.md)

- [Анонимные типы классов](../cpp/anonymous-class-types.md)

- [Указатели на члены](../cpp/pointers-to-members.md)

- [Этот указатель](../cpp/this-pointer.md)

- [Битовые поля C++](../cpp/cpp-bit-fields.md)

Существует три типа классов: структура, класс и объединение. Они объявляются с помощью ключевых слов [struct](../cpp/struct-cpp.md), [Class](../cpp/class-cpp.md)и [Union](../cpp/unions.md) . В следующей таблице показаны различия между этими тремя типами классов.

Дополнительные сведения о объединениях см. в разделе [объединения](../cpp/unions.md). Сведения о классах и структурах в C++/CLI и C++/CX см. в разделе [классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md).

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>Управление доступом и ограничения для структур, классов и объединений

|Структуры|Классы|Объединения|
|----------------|-------------|------------|
|ключ класса**`struct`**|ключ класса**`class`**|ключ класса**`union`**|
|Доступ по умолчанию: public (открытый).|Доступ по умолчанию: private (закрытый).|Доступ по умолчанию: public (открытый).|
|Нет ограничений на использование|Нет ограничений на использование|Используется только один член за один раз|

## <a name="see-also"></a>См. также

[Справочник по языку C++](../cpp/cpp-language-reference.md)
