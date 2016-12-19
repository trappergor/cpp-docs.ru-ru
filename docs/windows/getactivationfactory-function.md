---
title: "Функция GetActivationFactory | Microsoft Docs"
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
  - "module/Microsoft::WRL::Details::GetActivationFactory"
  - "client/ABI::Windows::Foundation::GetActivationFactory"
  - "client/Windows::Foundation::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory - функция"
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция GetActivationFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает фабрику активации для типа, указанного в параметре шаблона.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### Параметры  
 `T`  
 Параметр шаблона, который определяет тип фабрики активации.  
  
 `activatableClassId`  
 Имя класса, который фабрика активации может создать.  
  
 `factory`  
 Когда эта операция завершается, ссылка на фабрику активации для типа `T`.  
  
## Возвращаемое значение  
 S\_OK, если операция завершилась удачно; в противном случае возвращается ошибка HRESULT, показывающая причину неудачного завершения операции.  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Windows::Foundation  
  
## См. также  
 [Пространство имен Windows::Foundation](../Topic/Windows::Foundation%20Namespace.md)