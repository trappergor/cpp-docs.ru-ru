---
title: "Оператор while в С | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- while
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: 7
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
ms.openlocfilehash: e383ae0646bdf15c38f6537de0adec9bb9468486
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="while-statement-c"></a>Оператор while (C)
Оператор `while` позволяет повторять выполнение оператора до тех пор, пока указанное выражение не станет ложным.  
  
## <a name="syntax"></a>Синтаксис  
 *оператор-итерации*:  
 **while (**  *expression*  **)**  *statement*  
  
 Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:  
  
1.  Вычисляется значение *expression*.  
  
2.  Если *expression* изначально ложно, тело оператора `while` не выполняется ни одного раза и управление передается из оператора `while` следующему оператору в программе.  
  
     Если *expression* имеет значение True (то есть не равно нулю), выполняется тело оператора и процесс повторяется с шага 1.  
  
 Выполнение оператора `while` прерывается, если в теле оператора выполняется оператор **break**, `goto` или `return`. Для прерывания одного цикла итерации без выхода из `while` используйте оператор **continue**. Оператор **continue** передает управление в следующую итерацию оператора `while`.  
  
 Ниже приводится пример оператора `while`.  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 В этом примере производится копирование символов из `string2` в `string1`. Если значение `i` больше или равно 0, значение `string2[i]` присваивается элементу `string1[i]` и значение переменной `i` уменьшается на единицу. Когда значение переменной `i` становится равным 0 (или меньше 0), выполнение оператора `while` прекращается.  
  
## <a name="see-also"></a>См. также  
 [Оператор while (C++)](../cpp/while-statement-cpp.md)
