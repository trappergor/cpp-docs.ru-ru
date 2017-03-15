---
title: "Метод RuntimeClassBaseT::GetImplementedIIDS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetImplementedIIDS - метод"
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Метод RuntimeClassBaseT::GetImplementedIIDS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### Параметры  
 `T`  
 Тип параметра `implements`.  
  
 `implements`  
 Указатель на тип, заданный параметром `T`.  
  
 `iidCount`  
 Максимальное количество получаемых идентификаторов интерфейсов.  
  
 `iids`  
 Если эта операция завершается успешно, то массив идентификаторов интерфейса реализуется типом `T`.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Заметки  
 Извлекает массив идентификаторов интерфейсов, которые реализуются указанным типом.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)