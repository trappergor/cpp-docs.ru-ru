---
title: Оператор continue в С | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue
dev_langs:
- C++
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f474d24bd6057165a50cc6edaca5db5462f6459
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383554"
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