---
title: "Предупреждение компилятора (уровень 3) C4398 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4398"
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 3) C4398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переменная: глобальный объект для каждого процесса может работать неправильно с несколькими доменами приложений; рассмотрите возможность использования \_\_declspec\(appdomain\)  
  
 Виртуальная функция с вызываемым преобразованием [\_\_clrcall](../../cpp/clrcall.md) в машинный тип вызывает создание таблицы виртуальных методов для каждого домена приложения.  Такие переменные могут некорректно взаимодействовать при использовании в множественных доменах приложений.  
  
 Можно устранить это предупреждение, скомпилировав с **\/clr:pure**, который создает глобальные переменные для каждого домена приложения по умолчанию, или явным созданием переменной `__declspec(appdomain)`.  
  
 Дополнительные сведения см. в разделах [appdomain](../Topic/appdomain.md) и [Домены приложений и Visual C\+\+](../../dotnet/application-domains-and-visual-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4398:  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```