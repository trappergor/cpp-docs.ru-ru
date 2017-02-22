---
title: "Предупреждение компилятора C4430 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4430"
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора C4430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

отсутствует спецификатор типа — предполагается int.Примечание. C\+\+ не поддерживает int по умолчанию  
  
 Это ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C\+\+ 2005: все объявления должны явно содержать тип; тип int больше не предполагается по умолчанию.  
  
 С4430 всегда выводится в качестве ошибки.  Возможно отключение этого предупреждения с помощью прагма\-директивы `#pragma warning` или параметра **\/wd**; дополнительные сведения см. в разделе [warning](../../preprocessor/warning.md) или [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(уровень предупреждений\)](../../build/reference/compiler-option-warning-level.md).  
  
## Пример  
 В следующем примере формируется сообщение об ошибке С4430.  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```