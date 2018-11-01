---
title: литерал (C + +/ CLI и C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
ms.openlocfilehash: d58df1bb6a6ec1e53ee434cf60a8caf3d557eeb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521052"
---
# <a name="literal-ccli-and-ccx"></a>литерал (C + +/ CLI и C + +/ CX)

Переменная (элемент данных) с пометкой **литерала** в **/CLR** компиляции являются собственными эквивалентами из **статический const** переменной.

## <a name="all-platforms"></a>Все платформы

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

## <a name="remarks"></a>Примечания

Член данных помечен как **литерала** должны инициализироваться при объявлении и значение должно быть целочисленной константой, перечислением или строковый тип. Преобразование из типа выражения инициализации в тип статического константного элемента данных не должно требовать определенного пользователем преобразования.

Во время выполнения для полей литералов память не выделяется; компилятор только вставляет свое значение в метаданные класса.

Переменная, помеченная как **статический const** не будут доступны в метаданных другим компиляторам.

Дополнительные сведения см. в разделе [статический](../cpp/storage-classes-cpp.md) и [const](../cpp/const-cpp.md).

**литерал** является контекстно-зависимые ключевым словом. См. в разделе [контекстные ключевые слова](../windows/context-sensitive-keywords-cpp-component-extensions.md) Дополнительные сведения.

## <a name="example"></a>Пример

В этом примере показано, что **литерала** подразумевает переменной **статических**.

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

## <a name="example"></a>Пример

В следующем примере показано влияние литералов в метаданных.

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Обратите внимание на разницу в метаданных для `sc` и `lit`: директива `modopt` применяется к `sc` и поэтому она может игнорироваться другими компиляторами.

```
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)
```

```
.field public static literal int32 lit = int32(0x0000000A)
```

## <a name="example"></a>Пример

В следующем примере, созданная в C# ссылается на метаданные, созданные в предыдущем примере и показывается влияние **литерала** и **статический const** переменных:

```cs
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

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)