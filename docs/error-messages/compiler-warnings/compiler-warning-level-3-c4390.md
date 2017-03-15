---
title: "Предупреждение (уровень 3) C4390 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: dd04b9faa2ed1376b821dedb6270950e1b035df5
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4390"></a>Предупреждение компилятора (уровень 3) C4390
";": обнаружен пустой контролируемый оператор; это правильно?  
  
 После управляющего оператора, не содержащего обнаружено точкой с запятой.  
  
 Если C4390 возникает в результате использования макроса, следует использовать [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить предупреждение C4390 в модуль, содержащий макрос.  
  
 Следующий пример приводит к возникновению ошибки C4390:  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```
