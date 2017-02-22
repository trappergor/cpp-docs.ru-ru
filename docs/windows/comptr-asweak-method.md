---
title: "Метод ComPtr::AsWeak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak - метод"
ms.assetid: 23e29dcd-39cb-423f-abe6-6df4428213bf
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ComPtr::AsWeak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает слабую ссылку на текущий объект.  
  
## Синтаксис  
  
```  
HRESULT AsWeak(  
   _Out_ WeakRef* pWeakRef  
);  
```  
  
#### Параметры  
 `pWeakRef`  
 Когда эта операция завершится, указатель на объект слабой ссылки.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ComPtr](../windows/comptr-class.md)