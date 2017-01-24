---
title: "Функция ActivationFactoryCallback | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::ActivationFactoryCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactoryCallback - функция"
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция ActivationFactoryCallback
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### Параметры  
 `activationId`  
 Дескриптор строки, которая указывает имя класса среды выполнения.  
  
 `ppFactory`  
 Когда эта операция будет завершена, фабрика активации, соответствующая параметру `activationId`.  
  
## Возвращаемое значение  
 В случае успеха возвращает значение S\_OK; в противном случае значение типа HRESULT, описывающее тип сбоя.  Обычными сбоями HRESULT являются CLASS\_E\_CLASSNOTAVAILABLE и E\_INVALIDARG.  
  
## Примечания  
 Получает фабрику активации для указанного идентификатора активации.  
  
 Среда выполнения Windows вызывает данную функцию обратного вызова, чтобы запросить объект, указанный по имени класса среды выполнения.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)