---
title: "Метод ActivationFactory::GetRuntimeClassName | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName - метод"
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод ActivationFactory::GetRuntimeClassName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает имя класса среды выполнения для объекта, который создает текущий ActivationFactory.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
#### Параметры  
 `runtimeName`  
 Когда эта операция завершается, дескриптор строки, содержащей имя класса среды выполнения для объекта, который создает текущий ActivationFactory.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение S\_OK; в противном случае значение типа HRESULT, описывающее тип сбоя.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)