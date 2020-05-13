---
title: ref class и ref struct (C++/CLI и C++/CX)
ms.date: 05/30/2019
ms.topic: reference
f1_keywords:
- ref class
- value class
- ref struct
- value struct
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
ms.openlocfilehash: 78cf7cf16c4ccf29f72038fd79c5d7a1689c05ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172572"
---
# <a name="ref-class-and-ref-struct--ccli-and-ccx"></a>ref class и ref struct (C++/CLI и C++/CX)

Расширения **ref class** или **ref struct** объявляют класс или структуру со *временем жизни объекта*, которое администрируется автоматически. Когда объект становится недоступным или выходит за пределы области, память освобождается.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="syntax"></a>Синтаксис

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};
```

### <a name="parameters"></a>Параметры

*class_access*<br/>
(Необязательно) Доступность класса или структуры вне сборки. Возможные значения: **public** и **private** (**private** — значение по умолчанию). Вложенные классы и структуры не могут иметь описатель *class_access*.

*name*<br/>
Имя класса или структуры.

*modifier*<br/>
(Необязательно) Допустимые модификаторы — [abstract](abstract-cpp-component-extensions.md) и [sealed](sealed-cpp-component-extensions.md).

*inherit_access*<br/>
(Необязательно) Доступность *base_type*. Единственная разрешенная доступность — **public** (**public** — значение по умолчанию).

*base_type*<br/>
(Необязательно) Базовый тип. Однако тип значения не может действовать как базовый тип.

Дополнительные сведения см. в описаниях этого параметра для конкретного языка в разделах "Среда выполнения Windows" и "Среда CLR".

### <a name="remarks"></a>Remarks

Специальные возможности по умолчанию элемента объекта, объявленного с помощью **ref class** или **value class**, являются **private**. Специальные возможности по умолчанию элемента объекта, объявленного с помощью **ref struct** или **value struct**, являются **public**.

Когда ссылочный тип наследует от другого ссылочного типа, виртуальные функции в базовом классе необходимо явно переопределить (с помощью [override](override-cpp-component-extensions.md)) или скрыть (с помощью[new (new slot in vtable)](new-new-slot-in-vtable-cpp-component-extensions.md)). Функции производного класса должны также быть явно помечены как **virtual**.

Для обнаружения во время компиляции, является ли тип **ref class** или **ref struct**, а также **value class** или **value struct**, используйте `__is_ref_class (type)`, `__is_value_class (type)` или `__is_simple_value_class (type)`. Подробные сведения см. в статье [Compiler Support for Type Traits (C++/CLI and C++/CX)](compiler-support-for-type-traits-cpp-component-extensions.md) (Поддержка характеристик типов компилятором (C++/CLI and C++/CX)).

Дополнительные сведения о классах и структурах см. в разделе

- [Практическое руководство. Определение и использование классов и структур (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [Семантика стека C++ для ссылочных типов](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [Классы и структуры (C++)](../cpp/classes-and-structs-cpp.md)

- [Деструкторы и методы завершения в методах: определение и использование классов и структур (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [Пользовательские операторы (C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [Заданные пользователем преобразования (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [Практическое руководство. Создание программы-оболочки собственного класса для использования в C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [Универсальные классы (C++/CLI)](generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Remarks

См. разделы [Классы и структуры ссылки (C++/CX)](../cppcx/ref-classes-and-structs-c-cx.md) и [Классы и структуры значений (C++/CX)](../cppcx/value-classes-and-structs-c-cx.md).

### <a name="parameters"></a>Параметры

*base_type*<br/>
(Необязательно) Базовый тип. **ref class** или **ref struct** могут наследовать от произвольного числа (включая 0) интерфейсов и от ноля или одного типа **ref**. **value class** или **value struct** могут наследовать только от произвольного числа (включая 0) интерфейсов.

Если объект объявлен с помощью ключевых слов **ref class** или **ref struct**, он доступен дескриптору объекта, т. е. указателю счетчика ссылок на объект. Если объявленная переменная выходит за пределы области, компилятор автоматически удаляет базовый объект. Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только его дескриптор.

При объявлении объекта с помощью ключевых слов **value class** или **value struct** время жизни объявленного объекта не контролируется. Этот объект аналогичен любому другому стандартному классу или структуре C++.

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Remarks

В следующей таблице перечислены отличия от синтаксиса, показанного в разделе **Все среды выполнения**, которые характерны для C++/CLI.

### <a name="parameters"></a>Параметры

*base_type*<br/>
(Необязательно) Базовый тип. **ref class** или **ref struct** может наследовать от произвольного числа (включая 0) управляемых интерфейсов и от ноля или одного типа ref. **value class** или **value struct** может наследовать только от произвольного числа (включая 0) управляемых интерфейсов.

Ключевые слова **ref class** и **ref struct** сообщают компилятору, что класс или структура должны выделяться в куче. Когда объект используется в качестве параметра в вызове или хранится в переменной, фактически передается или хранится только ссылка на него.

Ключевые слова **value class** и **value struct** сообщают компилятору, что значение выделенного класса или структуры передается функциям или сохраняется в элементах.

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
