---
title: "Предупреждение компилятора (уровень 1) C4382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4382"
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

генерация исключения "тип" : тип с деструктором \_\_clrcall или конструктором копирования может быть перехвачен только в модуле с параметром \/clr:pure  
  
 При компиляции с параметром **\/clr** \(но не **\/clr:pure**\) обработчик исключений ожидает, что функции\-члены собственного типа будут использовать соглашение [\_\_cdecl](../Topic/__cdecl.md), а не [\_\_clrcall](../../cpp/clrcall.md).  Собственные типы с функциями\-членами, использующими соглашение о вызове `__clrcall`, не могут перехватываться в модулях, компилируемых с параметром **\/clr**.  
  
 Если исключение будет перехвачено в модуле, скомпилированном с параметром **\/clr:pure**, то это предупреждение можно пропустить.  
  
 Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
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