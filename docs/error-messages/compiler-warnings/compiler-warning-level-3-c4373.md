---
title: "Предупреждение компилятора (уровень 3) C4373 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4373"
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

%$S: виртуальная функция переопределяет "%$pS", предыдущие версии компилятора не выполняли переопределение, когда параметры отличались только квалификаторами const или volatile  
  
 Ваше приложение содержит метод в производном классе, который переопределяет виртуальный метод в базовом классе, и параметры в переопределяющем методе отличаются от параметров виртуального метода только по квалификатору [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md). Это означает, что компилятор должен привязать ссылку на функцию к методу в базовом или производном классе.  
  
 Версии компилятора до [!INCLUDE[cpp_orcas_long](../../error-messages/compiler-warnings/includes/cpp_orcas_long_md.md)] привязывают функцию к методу в базовом классе, а затем выдают предупреждение. Последующие версии компилятора игнорируют квалификатор `const` или `volatile`, привязывают функцию к методу в производном классе, а затем выдают предупреждение `C4373`. Поведение в последнем случае соответствует стандарту C\+\+.  
  
## Пример  
 Следующий пример кода приводит к возникновению ошибки C4373.  
  
```  
// c4373.cpp // compile with: /c /W3 #include <stdio.h> struct Base { virtual void f(int i) { printf("base\n"); } }; struct Derived : Base { void f(const int i) {  // C4373 printf("derived\n"); } }; void main() { Derived d; Base* p = &d; p->f(1); }  
```  
  
```Output  
производные  
```