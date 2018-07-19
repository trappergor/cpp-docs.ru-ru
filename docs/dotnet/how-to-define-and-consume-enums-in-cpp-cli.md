---
title: 'Как: определение и использование перечислений в C + +/ CLI | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5c30b679b24e574d359a1f838785f0196f290d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131521"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Практическое руководство. Определение и использование перечислений в C++/CLI
В этом разделе обсуждаются перечислений в C + +/ CLI.  
  
## <a name="specifying-the-underlying-type-of-an-enum"></a>Указание базового типа перечисления  
 По умолчанию является базовым типом перечисления `int`.  Тем не менее, можно указать тип со знаком или без формы `int`, `short`, `long`, `__int32`, или `__int64`.  Можно также использовать `char`.  
  
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
  
## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Преобразование между управляемыми и стандартными перечислениями  
 Нет стандартного преобразования между перечисление и целочисленный тип; приведение не требуется.  
  
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
 Допустимы следующие операторы для перечислений в C + +/ CLI:  
  
|Оператор|  
|--------------|  
|== != \< > \<= >=|  
|+ -|  
|&#124; ^ & ~|  
|++ --|  
|sizeof|  
  
 Операторы &#124; ^ & ~ ++--определены только для перечислений с целочисленным базовые типы, не включая bool.  Оба операнда должны быть типа перечисления.  
  
 Компилятор выполняет статической или динамической проверки не результата операции перечисления; операция может привести значение за пределами допустимых перечислителей перечисления.  
  
> [!NOTE]
>  C ++ 11 доступны типы классов перечислений в неуправляемом коде которых значительно отличаются от классов управляемых перечислений в C + +/ CLI. В частности, тип класса C ++ 11 enum не поддерживает те же операторы как управляемое перечисление тип класса в C + +/ CLI и C + +/ CLI исходного кода необходимо указать спецификатор специальных возможностей в управляемое перечисление объявлений класса, чтобы отличать их от неуправляемого (C++ 11) объявления класса enum. Дополнительные сведения о классов перечислений в C + +/ CLI, C + +/ CX и C ++ 11. в разделе [класс перечисления](../windows/enum-class-cpp-component-extensions.md).  
  
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
 [Класс перечисления](../windows/enum-class-cpp-component-extensions.md)