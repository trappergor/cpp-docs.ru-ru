---
title: "Метод ActivationFactory::GetIids | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids - метод"
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ActivationFactory::GetIids
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает массив идентификаторов реализованного интерфейса.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### Параметры  
 `iidCount`  
 Когда эта операция завершится, число идентификаторов интерфейса в массиве `iids`.  
  
 `iids`  
 Когда эта операция завершится, массив идентификаторов реализованного интерфейса.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение S\_OK; в противном случае значение типа HRESULT, описывающее тип сбоя.  E\_OUTOFMEMORY является возможной ошибкой HRESULT.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)