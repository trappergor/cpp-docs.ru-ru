---
title: "Оператор switch (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default"
  - "default_cpp"
  - "switch"
  - "switch_cpp"
  - "case"
  - "case_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case - ключевое слово [C++], в операторах switch"
  - "default - ключевое слово [C++]"
  - "switch - ключевое слово [C++]"
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор switch (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет выбирать между несколькими разделами кода в зависимости от значения целочисленного выражения.  
  
## Синтаксис  
  
```  
  
      switch ( expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## Заметки  
 *Выражение* должно быть целого типа или типа класса, для которого имеется точно выраженное преобразование к целочисленному типу.  Восходящее приведение целого типа выполняется, как описано в разделе [Восходящие приведение целого типа](../misc/integral-promotions.md).  
  
 Тело оператора `switch` состоит из ряда меток **case** и необязательной метки **default**.  Никакие два константных выражения в операторах **case** не могут иметь одно и то же значение.  Метка **default** может появляться только один раз.  Операторы с меткой не являются синтаксическим требованием, однако без них инструкция `switch` не имеет значения.   Оператор по умолчанию не всегда стоит в конце; он может отображаться в любой части оператора switch.  Метка case или default может отображаться только внутри оператора switch.  
  
 *Константное\-выражение* в каждой метке **случая** преобразуется в тип *выражение* и сравнивается с *выражением* на равенство.  Управление передается оператору, у которого **константное\-выражение** *случая* соответствует значению *выражения*.  Поведение, полученное в результате, показано в следующей таблице.  
  
### Поведение оператора switch  
  
|Условие|Действие|  
|-------------|--------------|  
|Преобразованное значение соответствует значению выражения управления с повышенным уровнем.|Управление передается оператору, следующему за этой меткой.|  
|Ни одна из констант не соответствуют константам в метках **случаев**; метка **default** присутствует.|Управление передается метке **default**.|  
|Ни одна из констант не соответствуют константам в метках **случаев**; метка **default** не присутствует.|Управление передается оператору, следующему за оператором `switch`.|  
  
 Если соответствующее выражение найдено, элементу управления не препятствуют последующие метки **case** или **default**.  Оператор [break](../cpp/break-statement-cpp.md) используется для остановки выполнения и контроля передачи в оператор после оператора `switch`.  Без оператора **break** будет выполнен каждый оператор из сопоставленной метки **case** в конце `switch`, включая **default**.  Например:  
  
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
  
 В предыдущем примере `capa` увеличивается инкрементно, если `c` — `A` в верхнем регистре.  Оператор `break` после `capa++` завершает выполнение `switch`, а элемент правления передается циклу `while`.  Без оператора `break` объекты `lettera` и `nota` также должны быть инкрементированы.  Аналогичную цель преследует оператор `break` для `case 'a'`.  Если `c` — в нижнем регистре `a`, `lettera` увеличивается постепенно, а оператор `break` завершает тело оператора `switch`.  Если параметр `c` не является `a` или `A`, выполняется оператор `default`.  
  
 Внутренний блок оператора `switch` может содержать определения с инициализациями при условии их доступности, то есть они должны не обходиться всеми возможными путями выполнения.  Имена, добавленные с помощью этих объявлений, имеют локальную область видимости.  Например:  
  
```  
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
  
 Оператор `switch` может быть вложенным.  В таких случаях метки **case** или **default** связываются с максимально близким оператором `switch`, который содержит их.  
  
## Блок, относящийся только к системам Microsoft  
 Microsoft C не ограничивает количество значений case в операторе `switch`.  Это число ограничивается только объемом доступной памяти.  ANSI C требует, чтобы в операторе `switch` можно было использовать не менее 257 меток case.  
  
 В Microsoft C расширения Microsoft по умолчанию включены.  Используйте параметр компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) для отключения этих расширений.  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [Инструкции выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) Using Labels in the case Statement](http://msdn.microsoft.com/ru-ru/a6ff057d-1aee-42ed-a28d-ee6a565b3197)