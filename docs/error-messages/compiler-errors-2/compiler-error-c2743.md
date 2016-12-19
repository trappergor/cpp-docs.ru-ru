---
title: "Ошибка компилятора C2743 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2743"
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": невозможно перехватить собственный тип с деструктором \_\_clrcall или конструктором копии  
  
 Модуль, компилированный с использованием параметра **\/clr** \(но не **\/clr:pure**\), выполнил попытку перехвата исключения собственного типа там, где деструктор типа или конструктор копии используют соглашение о вызовах \_`_clrcall`.  
  
 При компиляции с параметром **\/clr** \(но не **\/clr:pure**\) обработчик исключений ожидает, что функции\-члены собственного типа будут использовать соглашение [\_\_cdecl](../Topic/__cdecl.md), а не [\_\_clrcall](../../cpp/clrcall.md).  Собственные типы с функциями\-членами, использующими соглашение о вызове `__clrcall`, не могут перехватываться в модулях, компилируемых с параметром **\/clr**.  
  
 Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2743.  
  
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