---
title: Практическое руководство. Определение и использование перечислений в C++/CLI
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: cf3bb23069b2692c0ca4ce270a5b8060195becf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370176"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Практическое руководство. Определение и использование перечислений в C++/CLI

Эта тема обсуждается в се-квадри.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Определение базового типа enum

По умолчанию базовым типом перечисления `int`является .  Тем не менее, вы можете указать тип, `long`который `__int32`будет `__int64`подписан или неподписанных `int`форм , `short`, , или .  Также можно использовать `char`.

```cpp
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

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Как конвертировать между управляемыми и стандартными перечислениями

Не существует стандартного преобразования между enum и интегральным типом; литья не требуется.

```cpp
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

Следующие операторы действительны на перечислениях в СЗ/CLI:

|Оператор|
|--------------|
|В >\<  >  \<|
|+ -|
|&#124; и &|
|++ --|
|sizeof|

Операторы &#124; и & - определяются только для перечислений с интегральными базовыми типами, не включая бул.  Оба оперы должны быть типа перечисления.

Компилятор не проводит статическую или динамическую проверку результата операции enum; операция может привести к значению, не в пределах допустимого перечисления enum.

> [!NOTE]
> В неуправляемом коде, значительно отличающаяся от управляемых классов экумов в СЗ11, вводятся типы классов enum. В частности, тип класса C-11 не поддерживает тех же операторов, что и управляемый тип класса enum в c q/CLI, а исходный код СЗ/CLI должен обеспечивать спецификацию доступности в управляемых декларациях класса enum, чтобы отличить их от неуправляемых (C-11) деклараций класса enum. Для получения более подробной информации о классах enum в си/CLI, C q/CX и C-11 [см.](../extensions/enum-class-cpp-component-extensions.md)

```cpp
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

```cpp
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

## <a name="see-also"></a>См. также раздел

[Класс перечисления](../extensions/enum-class-cpp-component-extensions.md)
