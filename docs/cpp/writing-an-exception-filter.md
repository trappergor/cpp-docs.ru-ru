---
title: "Написание фильтра исключений | Документы Microsoft"
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
- exception handling, filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
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
ms.openlocfilehash: 07bce97cdac37a920716e72f88bdda2d164fc479
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="writing-an-exception-filter"></a>Написание фильтра исключений
Исключение можно обработать посредством перехода на уровень обработчика исключений или путем продолжения выполнения. Вместо использования кода обработчика исключений для обработки исключения и передачи управления дальше, можно использовать *фильтра* устранить проблему и возвращая значение -1, возобновить Обычный поток без очистки стека.  
  
> [!NOTE]
>  После некоторых исключений возобновление невозможно. Если *фильтра* вычисляет значение -1 для такого исключения, система создает новое исключение. При вызове [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), определить, будет ли исключение.  
  
 Например, следующий код использует функции, вызываемой *фильтра* выражения: Эта функция обрабатывает проблему и затем возвращает значение -1, возобновить Обычный поток управления:  
  
```  
// exceptions_Writing_an_Exception_Filter.cpp  
#include <windows.h>  
int main() {  
   int Eval_Exception( int );  
  
   __try {}  
  
   __except ( Eval_Exception( GetExceptionCode( ))) {  
      ;  
   }  
  
}  
void ResetVars( int ) {}  
int Eval_Exception ( int n_except ) {  
   if ( n_except != STATUS_INTEGER_OVERFLOW &&   
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions  
   return EXCEPTION_CONTINUE_SEARCH;  
  
   // Execute some code to clean up problem  
   ResetVars( 0 );   // initializes data to 0  
   return EXCEPTION_CONTINUE_EXECUTION;  
}  
```  
  
 Рекомендуется использовать вызов функции в *фильтра* выражение всякий раз, когда *фильтра* должен выполнить какие-либо сложные. Вычисление выражения приводит к выполнению функции, в данном случае — `Eval_Exception`.  
  
 Обратите внимание на использование [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) для определения исключения. Эту функцию необходимо вызывать внутри фильтра. `Eval_Exception`не удается вызвать **GetExceptionCode**, но должна содержать передаваемый ей код исключения.  
  
 Если исключение не вызвано переполнением при операции с целыми числами или числами с плавающей запятой, этот обработчик передает управление другому обработчику. В этом случае обработчик вызывает функцию (`ResetVars` — это только пример, а не функция API), чтобы сбросить некоторые глобальные переменные. *Оператор блок-2*, в этом примере является пустым, никогда не запускается из-за `Eval_Exception` никогда не возвращает результат EXCEPTION_EXECUTE_HANDLER (1).  
  
 Вызов функции — хороший способ работы со сложными выражениями фильтров. Удобны также две другие функции языка C:  
  
-   условный оператор;  
  
-   оператор "запятая".  
  
 Условный оператор часто полезен, поскольку его можно использовать для проверки конкретного кода возврата и последующего возврата одного из двух различных значений. Например, фильтр в следующем коде распознает только исключение `STATUS_INTEGER_OVERFLOW`.  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 Цель условного оператора в этом случае — в основном, обеспечить ясность, так как следующий код дает такие же результаты.  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 Условный оператор больше подходит в ситуациях, когда требуется фильтр будет сравнивать значение -1, EXCEPTION_CONTINUE_EXECUTION.  
  
 Оператор "запятая" позволяет выполнить несколько независимых операций в одном выражении. Результат, грубо говоря, представляет собой результат выполнения нескольких инструкций с последующим возвратом значения последнего выражения. Например, в следующем коде код исключения сохраняется в переменной и затем проверяется.  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>См. также  
 [Написание обработчика исключений](../cpp/writing-an-exception-handler.md)   
 [Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
