---
title: "Класс ComPtrRefBase | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRefBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRefBase - класс"
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс ComPtrRefBase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### Параметры  
 `T`  
 Тип [ComPtr\<T\>](../windows/comptr-class.md) или тип, производный от него, не просто интерфейс, представленный ComPtr.  
  
## Заметки  
 Представляет базовый класс для класса [ComPtrRef](../Topic/ComPtrRef%20Class.md).  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`InterfaceType`|Синоним для типа параметра `T` шаблона.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор ComPtrRefBase::operator IInspectable\*\*](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Приводит текущий элемент данных [ptr\_](../windows/comptrrefbase-ptr-data-member.md) к указателю\-на\-указатель\-на интерфейс IInspectable.|  
|[Оператор ComPtrRefBase::operator IUnknown\*\*](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Приводит текущие данные\-член [ptr\_](../windows/comptrrefbase-ptr-data-member.md) к указателю\-на\-указатель\-на интерфейс IUnknown.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных ComPtrRefBase::ptr\_](../windows/comptrrefbase-ptr-data-member.md)|Указатель на тип, указанный в текущем параметре шаблона.|  
  
## Иерархия наследования  
 `ComPtrRefBase`  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)