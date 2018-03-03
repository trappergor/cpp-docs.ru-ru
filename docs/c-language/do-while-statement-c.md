---
title: "Оператор do-while в С | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26a7cef5e023c0fb0d5e24fe68fed6b33bc8ae75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="do-while-statement-c"></a>Оператор do-while (C)
Оператор `do-while` позволяет повторять выполнение оператора или составного оператора до тех пор, пока указанное выражение не станет ложным.  
  
## <a name="syntax"></a>Синтаксис  
 *оператор-итерации*:  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 *expression* в операторе `do-while` вычисляется после выполнения тела цикла. Поэтому тело цикла всегда выполняется по крайней мере один раз.  
  
 Выражение *expression* должно иметь арифметический тип или тип указателя. Выполнение происходит следующим образом:  
  
1.  Выполняется тело оператора.  
  
2.  Затем вычисляется значение *expression*. Если *expression* имеет значение false, выполнение оператора `do-while` завершается и управление передается следующему оператору программы. Если *expression* имеет значение true (то есть не равно нулю), процесс повторяется с шага 1.  
  
 Выполнение оператора `do-while` также прерывается, когда в теле оператора выполняется оператор **break**, `goto` или `return`.  
  
 Ниже приводится пример оператора `do-while`.  
  
```  
do   
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```  
  
 В этом операторе `do-while` два оператора `y = f( x );` и `x--;` выполняются независимо от начального значения переменной `x`. Затем вычисляется выражение `x > 0`. Если `x` больше 0, тело оператора выполняется еще раз и снова вычисляется выражение `x > 0`. Тело оператора многократно выполняется, пока значение переменной `x` остается больше 0. Выполнение оператора `do-while` завершается, когда значение переменной `x` становится равным 0 или отрицательным. Тело цикла выполняется по крайней мере один раз.  
  
## <a name="see-also"></a>См. также  
 [Оператор do-while (C)](../cpp/do-while-statement-cpp.md)