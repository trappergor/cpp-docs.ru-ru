---
title: "Метод InterfaceTraits::FillArrayWithIid | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid - метод"
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод InterfaceTraits::FillArrayWithIid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### Параметры  
 `index`  
 Указатель на поле, содержащее значение индекса с отсчетом от нуля.  
  
 `iids`  
 Массив идентификаторов интерфейсов.  
  
## Примечания  
 Присваивает идентификатор интерфейса `Base` к элементу массива, указанному аргументом индекса.  
  
 Вопреки имени этого API, изменяется только один элемент массива; не весь массив.  
  
 Дополнительные сведения о `Base` см. в разделе Общедоступные определения типов в [Структура InterfaceTraits](../windows/interfacetraits-structure.md).  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Структура InterfaceTraits](../windows/interfacetraits-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)