---
title: "Предупреждение компилятора (уровень 1) C4376 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4376"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4376"
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4376
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

спецификатор доступа "устаревший\_спецификатор": более не поддерживается: вместо этого следует использовать "новый\_спецификатор"  
  
 Дополнительные сведения о указание типа и специальных возможностей члена в метаданных см. в разделах [Видимость типа](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [Видимость члена](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) в [Практическое руководство. Определение и использование классов и структур](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C4376.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```