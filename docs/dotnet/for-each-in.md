---
title: for each, in
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: f1f5523eb22bd8a839da9b3f73dd6c3718b4fd63
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825800"
---
# <a name="for-each-in"></a>for each, in

Выполняет итерацию по массиву или коллекции. Это нестандартное ключевое слово доступно как в C++/CLI, так и в собственных проектах C++. Однако его использование не рекомендуется. Вместо этого рекомендуется использовать стандартный [основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md) .

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="syntax"></a>Синтаксис

> **for each (** *type* *идентификатор* **типа в** *выражении* **) {**\
> &nbsp;&nbsp;&nbsp;&nbsp;*инструкции*\
> **}**

### <a name="parameters"></a>Параметры

*type*<br/>
Тип параметра `identifier`.

*идентификатор*<br/>
Переменная итерации, представляющая элемент коллекции.  Если `identifier` является [оператором отслеживаемой ссылки](../extensions/tracking-reference-operator-cpp-component-extensions.md), можно изменить элемент.

*expression*<br/>
Выражение массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его в тип `identifier`.

*инструкции*<br/>
Один или несколько операторов для выполнения.

### <a name="remarks"></a>Примечания

Оператор `for each` используется для итерации по коллекции. Можно изменять элементы в коллекции, но добавление или удаление элементов невозможно.

*Инструкции* выполняются для каждого элемента в массиве или коллекции. После завершения итерации всех элементов коллекции управление передается следующему оператору после блока `for each`.

`for each`и `in` являются [контекстно-зависимыми ключевыми словами](../extensions/context-sensitive-keywords-cpp-component-extensions.md).

Дополнительные сведения

- [Перебор элементов коллекции стандартной библиотеки C++ с использованием цикла for each](../dotnet/iterating-over-stl-collection-by-using-for-each.md)

- [Практическое руководство. Перебор элементов массивов с использованием цикла for each](../dotnet/how-to-iterate-over-arrays-with-for-each.md)

- [Практическое руководство. Перебор элементов универсальной коллекции с использованием цикла for each](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)

- [Практическое руководство. Перебор элементов определенной пользователем коллекции с использованием цикла for each](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

### <a name="example"></a>Пример

В этом примере показано использование `for each` для итерации по строке.

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

**Выходные данные**

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Среда CLR

**Замечания**

Синтаксис среды CLR аналогичен синтаксису **всех сред выполнения** , за исключением следующего.

*expression*<br/>
Выражение управляемого массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его из <xref:System.Object> в тип *идентификатора* .

результатом вычисления *выражения* является тип, который реализует <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>или тип, `GetEnumerator` определяющий метод, который либо возвращает тип, который реализует <xref:System.Collections.IEnumerator> , либо объявляет все методы, определенные в. `IEnumerator`

### <a name="requirements"></a>Требования

Параметр компилятора: **/clr**

### <a name="example"></a>Пример

В этом примере показано использование `for each` для итерации по строке.

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

**Выходные данные**

```Output
abcd

Testing
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)
