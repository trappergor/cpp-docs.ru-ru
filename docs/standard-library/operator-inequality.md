---
title: "operator!= | Microsoft Docs"
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
  - "std::!="
  - "!="
  - "std::operator!="
  - "std.operator!="
  - "std.!="
  - "operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= - оператор"
  - "Оператор !="
  - "operator!="
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator!=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  В этом разделе в документации Visual C\+\+ как нефункциональный пример контейнеров, используемых в стандартной библиотеке C\+\+.  Дополнительные сведения см. в разделе [Контейнеров STL](../standard-library/stl-containers.md).  
  
 В `operator!=` для сравнения 2 объекта класса шаблона [Контейнер](../Topic/Sample%20Container%20Class.md).  
  
## Синтаксис  
  
```  
  
   template<class Ty>  
bool operator!=(  
   const Container <Ty>& _Left,  
   const Container <Ty>& _Right  
);  
```  
  
## Возвращаемое значение  
 Возвращает **\!**\(\_*Left* **\=\=** `_Right`\).  
  
## См. также  
 [\<sample container\>](../standard-library/sample-container.md)