---
title: "Метод HString::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::Attach"
dev_langs: 
  - "C++"
ms.assetid: 69451979-0014-4959-bc5c-1e4ab6fb28e4
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# Метод HString::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Связывает указанный объект HString с текущим объектом HString.  
  
## Синтаксис  
  
```  
  
void Attach(  
       HSTRING hstr  
       ) throw()  
```  
  
#### Параметры  
 `hstr`  
 Существующий объект HString.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HString](../windows/hstring-class.md)