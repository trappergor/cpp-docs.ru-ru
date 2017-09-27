---
title: "Функции со списками аргументов переменных (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], variable number of
- variable argument lists
- declarators, functions
- argument lists [C++], variable number of
- declaring functions, variables
- function calls, variable number of arguments
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: e7a1f434b9c286bfa625d703023080f55586f0a8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="functions-with-variable-argument-lists--c"></a>Функции с переменным аргументом списками (C++)
Функции, в объявлениях которых в качестве последнего члена указано многоточие (...), могут принимать переменное число аргументов. В таких случаях C++ обеспечивает проверку типа только для явно объявленных аргументов. Переменные списки аргументов можно использовать, если функция должна быть настолько универсальной, что могут изменяться даже количество и типы аргументов. Семейство функций приведен пример функции, использующие списки аргументов переменных. `printf` *списка объявления аргументов*  
  
## <a name="functions-with-variable-arguments"></a>Функции с переменными аргументами  
 Для доступа к аргументам, следующим после объявленных, используйте макрос, содержащийся в стандартном включаемом файле STDARG.H, как описано ниже.  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Microsoft C++ допускает указывать многоточие в качестве аргумента, если это последний аргумент и перед многоточием стоит запятая. Поэтому объявление `int Func( int i, ... );` допускается, а объявление `int Func( int i ... );` — нет.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 В объявлении функции, которая принимает переменное число аргументов, требуется по крайней мере один аргумент-местозаполнитель, даже если он не используется. Если этот аргумент-местозаполнитель не указан, доступ к остальным аргументам невозможен.  
  
 Если аргументы типа `char` передаются как переменные аргументы, они преобразуются в тип `int`. Аналогично, если аргументы типа **float** передаются как переменные аргументы, они преобразуются в тип **двойные**. Для аргументов остальных типов могут выполняться обычные восходящие приведения целочисленных типов и типов с плавающей запятой. В разделе [стандартные преобразования](standard-conversions.md) для получения дополнительной информации.  
  
 Функции, которым необходимы списки с переменным количеством аргументов, объявляются с многоточием (...) в списках аргументов. Обращаться к аргументам, которые передаются в таких списках, можно при помощи типов и макросов, описанных во включаемом файле STDARG.H. Дополнительные сведения об этих макросах см. в разделе [va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). в документации по библиотеке времени выполнения C.  
  
 В следующем примере показано, каким образом макросы взаимодействуют с типом (объявлены в STDARG. H): 
  
```  
// variable_argument_lists.cpp  
#include <stdio.h>  
#include <stdarg.h>  
  
//  Declaration, but not definition, of ShowVar.  
void ShowVar( char *szTypes, ... );  
int main() {  
   ShowVar( "fcsi", 32.4f, 'a', "Test string", 4 );  
}  
  
//  ShowVar takes a format string of the form  
//   "ifcs", where each character specifies the  
//   type of the argument in that position.  
//  
//  i = int  
//  f = float  
//  c = char  
//  s = string (char *)  
//  
//  Following the format specification is a variable   
//  list of arguments. Each argument corresponds to   
//  a format character in the format string to which   
// the szTypes parameter points   
void ShowVar( char *szTypes, ... ) {  
   va_list vl;  
   int i;  
  
   //  szTypes is the last argument specified; you must access   
   //  all others using the variable-argument macros.  
   va_start( vl, szTypes );  
  
   // Step through the list.  
   for( i = 0; szTypes[i] != '\0'; ++i ) {  
      union Printable_t {  
         int     i;  
         float   f;  
         char    c;  
         char   *s;  
      } Printable;  
  
      switch( szTypes[i] ) {   // Type to expect.  
         case 'i':  
            Printable.i = va_arg( vl, int );  
            printf_s( "%i\n", Printable.i );  
         break;  
  
         case 'f':  
             Printable.f = va_arg( vl, double );  
             printf_s( "%f\n", Printable.f );  
         break;  
  
         case 'c':  
             Printable.c = va_arg( vl, char );  
             printf_s( "%c\n", Printable.c );  
         break;  
  
         case 's':  
             Printable.s = va_arg( vl, char * );  
             printf_s( "%s\n", Printable.s );  
         break;  
  
         default:  
         break;  
      }  
   }  
   va_end( vl );  
}  
//Output:   
// 32.400002  
// a  
// Test string  
```  
  
 Приведенный выше пример иллюстрирует следующие важные правила:  
  
1.  Перед тем как обращаться к аргументам из списка переменной длины, необходимо установить его маркер в качестве переменной типа `va_list`. В приведенном выше примере этот маркер имеет имя `vl`.  
  
2.  К отдельным аргументам можно обращаться при помощи макроса `va_arg`. Макросу `va_arg` необходимо указать тип получаемых аргументов, чтобы он мог перенести из стека нужное количество байтов. Если вы ошибетесь и укажете другой тип, а его размер не будет совпадать с типом, который вызывающая программа передает макросу `va_arg`, это может привести к непредсказуемым результатам.  
  
3.  Результат, полученный при помощи макроса `va_arg`, необходимо явным образом преобразовывать в нужный вам тип.  
  
 Для завершения обработки списка с переменным количеством аргументов необходимо вызвать макрос.`va_end`
