---
title: "Метод ClassFactory::QueryInterface | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory::QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface - метод"
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ClassFactory::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает указатель на интерфейс, указанный параметром.  
  
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
 Когда эта операция завершается, указатель на интерфейс, указанный параметром `riid`.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение S\_OK; в противном случае значение типа HRESULT, описывающее тип сбоя.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ClassFactory](../windows/classfactory-class.md)