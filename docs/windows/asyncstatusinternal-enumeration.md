---
title: "Перечисление AsyncStatusInternal | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::AsyncStatusInternal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncStatusInternal - перечисление"
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Перечисление AsyncStatusInternal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
enum AsyncStatusInternal;  
```  
  
## Заметки  
 Определяет сопоставление между внутренними перечислениями для состояний асинхронных операций и перечислением **Windows::Foundation::AsyncStatus**.  
  
## Члены  
 `_Created`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Created  
  
 `_Started`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Started  
  
 `_Completed`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Completed  
  
 `_Cancelled`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Cancelled  
  
 `_Error`  
 Эквивалентно ::Windows::Foundation::AsyncStatus::Error  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)