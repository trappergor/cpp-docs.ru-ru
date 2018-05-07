---
title: Предупреждение (уровень 1) C4382 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c02f0cb2d22aebb9af31844aec3bf68b97c3442e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4382"></a>Предупреждение компилятора (уровень 1) C4382
вызов «тип»: тип с деструктором __clrcall или конструктором копии может быть перехвачен только в/CLR: pure модуля  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 При компиляции с параметром **/CLR** (не **/CLR: pure**), обработка исключений ожидает, что функции-члены собственного типа будут использовать [__cdecl](../../cpp/cdecl.md) и не [__clrcall](../../cpp/clrcall.md). Собственные типы с функциями-членами с помощью `__clrcall` соглашение о вызовах, не может быть перехвачено в модуле, скомпилированном с **/CLR**.  
  
 Если исключение будет перехвачено в модуле, скомпилированном с **/CLR: pure**, можно игнорировать это предупреждение.  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4382.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```