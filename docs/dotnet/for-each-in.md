---
title: for each, in
description: C++/CLI для каждого, в описании инструкции и примерах.
ms.date: 09/25/2020
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: 7f228a773dfcbe791e26ea3e1bd8cfba7f3ab028
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413923"
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

*identifier*<br/>
Переменная итерации, представляющая элемент коллекции.  Если `identifier` является [оператором отслеживаемой ссылки](../extensions/tracking-reference-operator-cpp-component-extensions.md), можно изменить элемент.

*expression*<br/>
Выражение массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его в тип `identifier`.

*инструкции*<br/>
Один или несколько операторов для выполнения.

### <a name="remarks"></a>Remarks

Оператор `for each` используется для итерации по коллекции. Можно изменять элементы в коллекции, но нельзя добавлять или удалять элементы.

*Инструкции* выполняются для каждого элемента в массиве или коллекции. После завершения итерации всех элементов коллекции управление передается следующему оператору после блока `for each`.

`for each` и `in` являются [контекстно-зависимыми ключевыми словами](../extensions/context-sensitive-keywords-cpp-component-extensions.md).

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

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Remarks

Синтаксис среды CLR аналогичен синтаксису **всех сред выполнения** , за исключением следующего.

*expression*<br/>
Выражение управляемого массива или коллекция. Элемент коллекции должен быть таким, чтобы компилятор мог преобразовать его из <xref:System.Object> в тип *идентификатора* .

результатом вычисления *выражения* является тип, который реализует <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> или тип, определяющий `GetEnumerator` метод, который либо возвращает тип, который реализует, либо <xref:System.Collections.IEnumerator> объявляет все методы, определенные в `IEnumerator` .

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

```Output
abcd

Testing
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)\
[Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
