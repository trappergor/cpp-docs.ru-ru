---
title: "Предупреждение компилятора (уровень 3) C4580 | Microsoft Docs"
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
  - "C4580"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4580"
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4580
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовать \[attribute\] не рекомендуется; вместо этого в качестве базового класса укажите System::Attribute или Platform::Metadata  
  
 [attribute](../../windows/attribute.md) больше не является предпочтительным синтаксисом для создания пользовательских атрибутов.  Дополнительные сведения см. в разделе [Пользовательские атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).  Для кода CLR атрибуты должны быть производными от [System::Attribute](assetId:///System::Attribute?qualifyHint=False&autoUpgrade=True).  Для кода среды выполнения Windows атрибуты должны быть производными от `Platform::Metadata`.  
  
## Пример  
 В следующем примере показано возникновение ошибки C3454 и приводятся сведения по ее устранению.  
  
```  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```