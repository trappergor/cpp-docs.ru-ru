---
title: "Метод RuntimeClassBaseT::AsIID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID - метод"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Метод RuntimeClassBaseT::AsIID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### Параметры  
 `T`  
 Тип, реализующий идентификатор интерфейса, заданный параметром `riid`.  
  
 `implements`  
 Переменная типа, указанного в параметре `T` шаблона.  
  
 `riid`  
 Извлекаемый идентификатор интерфейса.  
  
 `ppvObject`  
 Если операция выполнена успешно, то указатель\-на\-указатель на интерфейс, заданный параметром `riid`.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Заметки  
 Извлекает указатель на заданный идентификатор интерфейса.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)