---
title: "Предупреждение (уровни 1 и 4) C4112 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8a2c08b6c4bc8e1f2cf20e0236f76b5cd3020de4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Предупреждение компилятора (уровни 1 и 4) C4112
\#строки требуется целое число между 1 и числом  
  
 [#Line](../../preprocessor/hash-line-directive-c-cpp.md) директива указывает целочисленный параметр, который находится за пределами допустимого диапазона.  
  
 Если указанный параметр имеет значение меньше 1, счетчик строк сбрасывается до 1. Если указанный параметр больше, чем *номер*, представляющий определенный компилятором предел, то счетчик строк не изменяется. Это предупреждение уровня 1 в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение уровня 4 в расширениях Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C4112:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```
