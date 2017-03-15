---
title: "Метод HANDLETraits::Close | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close - метод"
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод HANDLETraits::Close
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Закрывает указанный дескриптор.  
  
## Синтаксис  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### Параметры  
 `h`  
 Дескриптор, который необходимо закрыть.  
  
## Возвращаемое значение  
 **true**, если дескриптор `h` закрыт успешно; в противном случае — значение **false**.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## См. также  
 [Структура HANDLETraits](../windows/handletraits-structure.md)