---
title: "Предупреждение (уровень 4) C4702 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4702
dev_langs: C++
helpviewer_keywords: C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ef7420f3699363d33d195e2455ab9fddf88de40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4702"></a>Предупреждение компилятора (уровень 4) C4702
недостижимый код  
  
 Это предупреждение отображается в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: недостижимый код. Когда компилятор (внутреннюю) обнаруживает недостижимый код, он создает C4702, предупреждение уровня 4.  
  
 Для кода, который допустим в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET удалите недостижимый код или убедиться, что все исходный код доступен для определенного потока выполнения.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>Пример  
 При компиляции с параметром **/GX**, **параметр/EHc**, **/EHsc**, или **/EHac** и используя внешние функции C, код может стать недоступным из-за extern C функции считаются недоступными, поэтому блок catch недостижим.  Если вы считаете, что это предупреждение не является допустимым, так как функция, можно вызывать, компиляция с **/EHa** или **/EHs**, в зависимости от исключения.  
  
 Дополнительные сведения см. в разделе [/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C4702.  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```