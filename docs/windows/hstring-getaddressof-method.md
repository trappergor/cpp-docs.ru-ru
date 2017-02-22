---
title: "Метод HString::GetAddressOf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf"
dev_langs: 
  - "C++"
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# Метод HString::GetAddressOf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает указатель на базовый дескриптор HSTRING.  
  
## Синтаксис  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## Возвращаемое значение  
 Указатель на базовый дескриптор HSTRING.  
  
## Примечания  
 После этой операции строковое значение основного дескриптора HSTRING будет уничтожено.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс HString](../windows/hstring-class.md)