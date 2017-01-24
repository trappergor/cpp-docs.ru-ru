---
title: "Метод ComPtr::ReleaseAndGetAddressOf | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf - метод"
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ComPtr::ReleaseAndGetAddressOf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Освобождает интерфейс, связанный с данным ComPtr, а затем извлекает адрес данных\-члена [ptr\_](../windows/comptr-ptr-data-member.md), который содержит указатель на интерфейс, который был освобожден.  
  
## Синтаксис  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## Возвращаемое значение  
 Адрес данных\-члена [ptr\_](../windows/comptr-ptr-data-member.md) этого ComPtr.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)   
 [Элемент данных ComPtr::ptr\_](../windows/comptr-ptr-data-member.md)