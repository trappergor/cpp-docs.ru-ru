---
title: "Метод ActivationFactory::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface - метод"
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод ActivationFactory::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает указатель на заданный интерфейс.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `ppvObject`  
 Когда эта операция завершена, указатель на интерфейс, указанный параметром `riid`.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение S\_OK; в противном случае значение типа HRESULT, описывающее тип сбоя.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)