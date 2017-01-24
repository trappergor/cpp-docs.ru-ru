---
title: "Предупреждение компилятора C4368 | Microsoft Docs"
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
  - "C4368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4368"
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается определить "член" в управляемом "типе": смешанные типы не поддерживаются  
  
 Включать неуправляемые члены данных в типы CLR нельзя.  
  
 Однако можно объявить указатель на собственный тип и элемент управления ее время существования в конструкторе и деструкторе и завершение управляемого класса.  Дополнительные сведения см. в разделе [Деструкторы и завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Это предупреждение всегда выдается как ошибка.  Для отключения предупреждения C4368 следует использовать прагма\-директиву [warning](../../preprocessor/warning.md).  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4368:  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```