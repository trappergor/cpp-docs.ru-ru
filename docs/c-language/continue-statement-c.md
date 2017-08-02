---
title: "Оператор continue в С | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- continue
dev_langs:
- C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
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
ms.openlocfilehash: a8db43c8f6648cac30ebba0ed1cd55d425716439
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="continue-statement-c"></a>Оператор continue (C)
Оператор `continue` передает элемент управления в следующую итерацию ближайшего внешнего оператора `do`, `for` или `while`, в которой она отображается, минуя все оставшиеся операторы в теле оператора `do`, `for` или `while`.  
  
## <a name="syntax"></a>Синтаксис  
 `jump-statement`:  
 `continue;`  
  
 Следующая итерация оператора `do`, `for` или `while` определяется следующим образом.  
  
-   В операторе `do` или `while` следующая итерация начинается с повторного вычисления выражения оператора `do` или `while`.  
  
-   Оператор `continue` в операторе `for` приводит к вычислению выражения цикла оператора `for`. Затем компилятор повторно вычисляет условное выражение и в зависимости от результата либо завершает, либо выполняет итерацию тела оператора. Дополнительные сведения об операторе `for` и его нетерминальных символах см. в статье [Оператор for](../c-language/for-statement-c.md).  
  
 Ниже приводится пример оператора `continue`.  
  
```  
while ( i-- > 0 )   
{  
    x = f( i );  
    if ( x == 1 )  
        continue;  
    y += x * x;  
}  
```  
  
 В этом примере тело оператора выполняется при `i` больше 0. Для первой переменной `f(i)` присваивается значение `x`; затем, если `x` равно 1, выполняется оператор `continue`. Остальные операторы в теле игнорируются, и выполнение возобновляется в начале цикла с вычисления теста цикла.  
  
## <a name="see-also"></a>См. также  
 [Оператор continue](../cpp/continue-statement-cpp.md)
