---
title: Практическое руководство. Определение и использование перечислений в C++выполняет
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 9787b7b96f83b2926c65209254c88eb56fe1a8ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387387"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Практическое руководство. Определение и использование перечислений в C++выполняет

В этом разделе обсуждаются перечислений в C++выполняет.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Указание базового типа перечисления

По умолчанию базовым типом перечисления является `int`.  Тем не менее, можно указать тип со знаком или без знака форм `int`, `short`, `long`, `__int32`, или `__int64`.  Можно также использовать `char`.

```
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**Вывод**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Как выполнять преобразование между управляемыми и стандартными перечислениями

Нет стандартного преобразования между перечисления и целочисленный тип; Приведение является обязательным.

```
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**Вывод**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>Операторы и перечисления

Допустимы следующие операторы для перечислений в C++выполняет:

|Оператор|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

Операторы &#124; ^ & ~ ++--определены только для перечислений с целочисленным базовые типы, не включая bool.  Оба операнда должны быть типа перечисления.

Компилятор выполняет статический или динамический Проверка результата операции перечисления; операция может привести к значению за пределами допустимых перечислителей перечисления.

> [!NOTE]
>  C ++ 11 доступны типы классов перечислений в неуправляемом коде которые значительно отличаются от классов управляемое перечисление в C++выполняет. В частности, тип класса перечисление C ++ 11 не поддерживает те же операторы управляемое перечисление класса в качестве типа C++выполняет, и C++/интерфейса командной строки исходного кода необходимо указать спецификатор специальных возможностей в управляемое перечисление объявления классов, чтобы отличать их от неуправляемые (C ++ 11) объявления классов перечислений. Дополнительные сведения о классах enum в C++выполняет, C++/CX и C ++ 11, см. в разделе [класс перечисления](../extensions/enum-class-cpp-component-extensions.md).

```
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**Вывод**

```Output
4
1
True
```

## <a name="see-also"></a>См. также

[Класс перечисления](../extensions/enum-class-cpp-component-extensions.md)
