---
title: Оператор switch (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cea2c7e4bff895f9ccabc044ed5b7f5ae506b32
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="switch-statement-c"></a>Оператор switch (C++)
Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>Примечания  
 *Выражение* должен иметь целочисленный тип или тип класса, для которого имеется однозначное преобразование в целочисленный тип. Выполняется восходящее приведение, как описано в [стандартные преобразования](standard-conversions.md).  
  
 `switch` Тела оператора состоит из ряда **случай** и необязательной метки **по умолчанию** метки. Никакие два константных выражения в **случай** операторы могут оценивать то же значение. **По умолчанию** метки может использоваться только один раз. Операторы с меткой не являются синтаксическим требованием, однако без них инструкция `switch` не имеет значения.   Оператор по умолчанию не всегда стоит в конце; он может отображаться в любой части оператора switch. Метка case или default может отображаться только внутри оператора switch.  
  
 *Константное выражение* в каждом **случай** метки преобразуется в тип *выражение* и сравнивается с *выражение* для равенство. Управление передается оператору, **случай** *константное выражение* совпадает со значением *выражение*. Поведение, полученное в результате, показано в следующей таблице.  
  
### <a name="switch-statement-behavior"></a>Поведение оператора switch  
  
|Условие|Действие|  
|---------------|------------|  
|Преобразованное значение соответствует значению выражения управления с повышенным уровнем.|Управление передается оператору, следующему за этой меткой.|  
|Ни одна из констант не соответствуют константам в **случай** метки; **по умолчанию** имеется метка.|Управление передается **по умолчанию** метки.|  
|Ни одна из констант не соответствуют константам в **случай** меток; **по умолчанию** метки не указан.|Управление передается оператору, следующему за оператором `switch`.|  
  
 Если соответствующее выражение найдено, элемент управления не препятствуют последующие **случай** или **по умолчанию** метки. [Разрыв](../cpp/break-statement-cpp.md) оператор используется для остановки выполнения и контроля передачи инструкции после `switch` инструкции. Без **разрыв** каждый оператор из сопоставленной **случай** метки в конец `switch`, в том числе **по умолчанию**, выполняется. Пример:  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 В предыдущем примере `capa` увеличивается инкрементно, если `c` — `A` в верхнем регистре. Оператор `break` после `capa++` завершает выполнение `switch`, а элемент правления передается циклу `while`. Без `break` инструкции, выполнение будет «проваливания» к следующему оператору с меткой, чтобы `lettera` и `nota` также должны быть инкрементированы. Аналогичную цель преследует оператор `break` для `case 'a'`. Если `c` — в нижнем регистре `a`, `lettera` увеличивается постепенно, а оператор `break` завершает тело оператора `switch`. Если параметр `c` не является `a` или `A`, выполняется оператор `default`.  

 **Visual Studio 2017 и более поздних версий:** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)) `[[fallthrough]]` задан в стандарт C ++ 17. Он может использоваться в `switch` инструкции как указание компилятору (или кому-либо в коде), поведение проходом предназначено. Компилятор Visual C++ в настоящее время не предупреждать о fallthrough поведение, поэтому этот атрибут имеет поведение компилятора не влияет. Обратите внимание, что атрибут применяется к пустой оператор в оператор с меткой; Иными словами, точка с запятой не требуется.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 г 15,3 и более поздних версий** (с [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): оператор switch может вызвать и инициализировать переменную, область действия которого ограничивается в блок оператора switch:

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 Внутренний блок оператора `switch` может содержать определения с инициализациями при условии их доступности, то есть они должны не обходиться всеми возможными путями выполнения. Имена, добавленные с помощью этих объявлений, имеют локальную область видимости. Пример:  
  
```cpp  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 Оператор `switch` может быть вложенным. В таких случаях **случай** или **по умолчанию** метки связать с ближайшим `switch` инструкцию, которая содержит их.  

 
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Microsoft C не ограничивает количество значений case в операторе `switch`. Это число ограничивается только объемом доступной памяти. ANSI C требует, чтобы в операторе `switch` можно было использовать не менее 257 меток case.  
  
 В Microsoft C расширения Microsoft по умолчанию включены. Используйте [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора для отключения этих расширений.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Операторы выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 