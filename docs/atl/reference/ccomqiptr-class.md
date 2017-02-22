---
title: "CComQIPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComQIPtr"
  - "ATL::CComQIPtr"
  - "CComQIPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtr class"
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComQIPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Интеллектуальное класс указателя для управления указатели интерфейса модели COM.  
  
## Синтаксис  
  
```  
  
      template<  
   class T,  
   const IID* piid = &__uuidof(T)  
>  
class CComQIPtr: public CComPtr<T>  
```  
  
#### Параметры  
 `T`  
 Интерфейс модели COM, указывающие тип указателя, которую необходимо сохранить.  
  
 `piid`  
 Указатель на идентификатор IID `T`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)|Конструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComQIPtr::operator \=](../Topic/CComQIPtr::operator%20=.md)|Присвоит указатель на указатель члена.|  
  
## Заметки  
 `CComQIPtr` и [CComPtr](../../atl/reference/ccomptr-class.md) использования библиотеки ATL управлять указатели интерфейса модели COM, оба они являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md).  Оба класса выполняют автоматическую ссылку подсчитывая через вызовы к `AddRef` и **Выпуск**.  Перегруженные операторы выполняют операции указателя.  
  
## Иерархия наследования  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## Требования  
 **Header:**  atlcomcli.h  
  
## См. также  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [CComPtrBase Class](../../atl/reference/ccomptrbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits Class](../Topic/CComQIPtrElementTraits%20Class.md)