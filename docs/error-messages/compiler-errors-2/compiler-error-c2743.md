---
title: "Ошибка компилятора C2743 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2743
dev_langs:
- C++
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29826dde6b9f92dd01e3a6420eed0d836660121f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2743"></a>Ошибка компилятора C2743
«Тип»: невозможно перехватить собственный тип с деструктором __clrcall или конструктором копии  
  
 Модуль компиляции с **/CLR** была предпринята попытка перехвата исключения собственного типа там, где деструктор или конструктор копии этого типа используют `__clrcall` соглашение о вызовах.  
  
 При компиляции с параметром **/CLR**, обработка исключений ожидает, что функции-члены собственного типа будут использовать [__cdecl](../../cpp/cdecl.md) и не [__clrcall](../../cpp/clrcall.md). Собственные типы с функциями-членами с помощью `__clrcall` соглашение о вызовах, не может быть перехвачено в модуле, скомпилированном с **/CLR**.  
  
 Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2743.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```