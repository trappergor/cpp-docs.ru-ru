---
title: "Глобальные константы в C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 766e1a6f48ecf3f64110e64d916c50d92c89345d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="global-constants-in-c"></a>Глобальные константы в C++
Глобальные константы в C++ имеют статическую связь. Это отличается от C. При попытке использования глобальных констант в C++ в нескольких файлах можно получить неразрешенная внешняя ошибка. Компилятор оптимизирует глобальные константы, не оставляя места для переменной.  
  
 Один из способов устранения этой ошибки является включение инициализации констант в файл заголовка и ввести этот заголовок в CPP-файлов при необходимости, как если бы он был прототип функции. Другой вариант — присвоить переменной неконстантное и использовать ссылку на константу при оценке его.  
  
 Следующий пример приводит к возникновению ошибки C2019:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 Затем:  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)