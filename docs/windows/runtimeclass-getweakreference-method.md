---
title: "Метод RuntimeClass::GetWeakReference | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetWeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetWeakReference - метод"
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод RuntimeClass::GetWeakReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Получает указатель на объект слабой ссылки для текущего объекта RuntimeClass.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### Параметры  
 `weakReference`  
 Когда эта операция завершится, указатель на объект слабой ссылки.  
  
## Возвращаемое значение  
 Всегда значение S\_ОК.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)