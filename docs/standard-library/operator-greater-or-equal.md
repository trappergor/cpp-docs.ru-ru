---
title: "operator&gt;= | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "operator>="
  - "std::>="
  - "std.operator>="
  - ">="
  - "std.>="
  - "std::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ">= - оператор, сравнение конкретных объектов"
  - "Оператор >="
  - "operator>="
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator&gt;=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  В этом разделе в документации Visual C\+\+ как нефункциональный пример контейнеров, используемых в стандартной библиотеке C\+\+.  Дополнительные сведения см. в разделе [Контейнеров STL](../standard-library/stl-containers.md).  
  
 В **operator\>\=** для сравнения 2 объекта класса шаблона [Контейнер](../Topic/Sample%20Container%20Class.md).  
  
## Синтаксис  
  
```  
  
   template<class Ty>  
bool operator>=(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Возвращаемое значение  
 Возвращает \_Right \_Left \< \( **\!**\).  
  
## См. также  
 [\<sample container\>](../standard-library/sample-container.md)