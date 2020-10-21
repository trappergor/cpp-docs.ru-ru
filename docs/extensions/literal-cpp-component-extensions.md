---
title: Literal (C++/CLI)
description: Ключевое слово Literal — это ключевое слово Microsoft C++/CLI, зависящее от контекста, для константы времени компиляции.
ms.date: 10/20/2020
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.openlocfilehash: 2d71a535252ba51f89407670b474a34b407eaffc
ms.sourcegitcommit: 59b7c18703d1ffd66827db0e2eeece490d3d8789
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92337217"
---
# <a name="literal-ccli"></a>`literal` (C++/CLI)

Переменная (член данных), помеченная как **`literal`** в **`/clr`** компиляции, является константой времени компиляции. Это собственный эквивалент [`const`](/dotnet/csharp/language-reference/keywords/const) переменной C#.

## <a name="all-platforms"></a>Все платформы

### <a name="remarks"></a>Remarks

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Remarks

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

## <a name="common-language-runtime"></a>Среда CLR

## <a name="remarks"></a>Remarks

Член данных, помеченный как, **`literal`** должен быть инициализирован при объявлении. И значение должно быть константным целым, перечислением или строковым типом. Преобразование из типа выражения инициализации в тип **`literal`** элемента данных не может требовать определенного пользователем преобразования.

Не выделяется память для **`literal`** поля во время выполнения; компилятор вставляет в метаданные класса только его значение. **`literal`** Значение рассматривается как константа времени компиляции. Ближайший эквивалент в стандартном C++ — **`constexpr`** , но элемент данных не может находиться **`constexpr`** в c++/CLI.

Переменная, помеченная как, **`literal`** отличается от помеченной **`static const`** . **`static const`** Элемент данных не становится доступным в метаданных для других компиляторов. Дополнительные сведения см. в разделах [`static`](../cpp/storage-classes-cpp.md) и [`const`](../cpp/const-cpp.md).

**`literal`** контекстно-зависимое ключевое слово. Дополнительные сведения см. в разделе [контекстно-зависимые ключевые слова](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Примеры

В этом примере показано, что **`literal`** переменная подразумевает **`static`** .

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

В следующем примере показан результат действия **`literal`** в метаданных.

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Обратите внимание на разницу в метаданных для `sc` и `lit`: директива `modopt` применяется к `sc` и поэтому она может игнорироваться другими компиляторами.

```MSIL
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x00000001)
```

```MSIL
.field public static literal int32 lit = int32(0x00000000)
```

Следующий пример, созданный в C#, ссылается на метаданные, созданные в предыдущем примере, и демонстрирует результат **`literal`** **`static const`** переменных и.

```csharp
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также статью

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
