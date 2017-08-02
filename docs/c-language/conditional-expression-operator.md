---
title: "Оператор условного выражения | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 1b7f7bae193af30a5ea9a4d8c9d176ce6763d8ec
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="conditional-expression-operator"></a>Оператор Conditional-Expression
В языке C есть один тернарный оператор: оператор условного выражения (**? :**).  
  
## <a name="syntax"></a>Синтаксис  
 *conditional-expression*:  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**   *expression*  **:**  *conditional-expression*  
  
 Выражение *logical-OR-expression* может иметь целочисленный тип, тип с плавающей запятой или тип указателя. Оно вычисляется с точки зрения эквивалентности значению 0. Точка последовательности следует за выражением *logical-OR-expression*. Вычисление операндов продолжается следующим образом.  
  
-   Если *logical-OR-expression* не равно 0, вычисляется выражение *expression*. Результат вычисления общего выражения определяется нетерминальным выражением *expression*. (Это означает, что *expression* вычисляется только в том случае, когда *logical-OR-expression* имеет значение true.)  
  
-   Если *logical-OR-expression* равно 0, вычисляется выражение *conditional-expression*. Тогда результатом общего выражения является значение *conditional-expression*. (Это означает, что *conditional-expression* вычисляется только в том случае, когда *logical-OR-expression* имеет значение false.)  
  
 Обратите внимание, что из выражений *expression* и *conditional-expression* вычисляется только одно.  
  
 Тип результата условной операции зависит от типа операнда *expression* или *conditional-expression*, как показано ниже.  
  
-   Если *expression* или *conditional-expression* имеет целочисленный тип или тип с плавающей запятой (типы выражений могут отличаться), оператор выполняет обычные арифметические преобразования. После преобразования тип результата совпадает с типом операндов.  
  
-   Если *expression* и *conditional-expression* имеют одинаковый тип структуры, объединения или указателя, результат получит такой же тип структуры, объединения или указателя.  
  
-   Если оба операнда имеют тип `void`, результат будет принадлежать типу `void`.  
  
-   Если какой-либо из операндов является указателем на объект любого типа, а второй операнд является указателем на `void`, указатель на объект преобразуется в указатель на `void`, и результатом является указатель на `void`.  
  
-   Если одно из выражений *expression* или *conditional-expression* является указателем, а другое — константным выражением со значением 0, результат будет иметь тип указателя.  
  
 При сравнении типов для указателей не учитываются квалификаторы типов (например, **const** или `volatile`), на который указывают эти указатели, но тип результата наследует квалификаторы от обоих компонентов условного выражения.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показаны варианты использования условного оператора.  
  
```  
j = ( i < 0 ) ? ( -i ) : ( i );  
```  
  
 В этом примере абсолютное значение `i` присваивается `j`. Если значение `i` меньше 0, значение `-i` присваивается `j`. Если значение `i` больше или равно 0, значение `i` присваивается `j`.  
  
```  
void f1( void );  
void f2( void );  
int x;  
int y;  
    .  
    .  
    .  
( x == y ) ? ( f1() ) : ( f2() );  
```  
  
 В этом примере объявляется две функции `f1` и `f2` и две переменные `x` и `y`. Далее в программе, если две переменные имеют одинаковое значение, вызывается функция `f1`. В противном случае вызывается функция `f2`.  
  
## <a name="see-also"></a>См. также  
 [Условный оператор: ? :](../cpp/conditional-operator-q.md)
