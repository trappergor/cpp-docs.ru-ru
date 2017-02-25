---
title: "Ошибка компилятора C3465 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3465"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3465"
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3465
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

для использования типа "тип" необходима ссылка на сборку "сборка"  
  
 Перенаправление типов будет работать для клиентского приложения до перекомпиляции клиента. При перекомпиляции потребуется ссылка для каждой сборки, содержащей определение типа, используемого в клиентском приложении.  
  
 Для получения дополнительной информации см. [Перенаправление типов \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Пример  
 В следующем примере выполняется построение сборки, содержащей новое расположение типа.  
  
```  
// C3465.cpp // compile with: /clr /LD public ref class R { public: ref class N {}; };  
```  
  
## Пример  
 В следующем примере выполняет построение сборки, которая обычно содержит определение типа, но теперь содержит синтаксис перенаправления для типа.  
  
```  
// C3465_b.cpp // compile with: /clr /LD #using "C3465.dll" [ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3465.  
  
```  
// C3465_c.cpp // compile with: /clr // C3465 expected #using "C3465_b.dll" // Uncomment the following line to resolve. // #using "C3465.dll" int main() { R^ r = gcnew R(); }  
```