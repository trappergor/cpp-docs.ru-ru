---
title: "CComPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtr class"
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Интеллектуальное класс указателя для управления указатели интерфейса модели COM.  
  
## Синтаксис  
  
```  
  
      template<  
   class T   
>  
class CComPtr  
```  
  
#### Параметры  
 `T`  
 Интерфейс модели COM, указывающие тип указателя, которую необходимо сохранить.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)|Конструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComPtr::operator \=](../Topic/CComPtr::operator%20=.md)|Присвоит указатель на указатель члена.|  
  
## Заметки  
 `CComPtr` и [CComQIPtr](../../atl/reference/ccomqiptr-class.md) использования библиотеки ATL управлять указатели интерфейса модели COM.  Оба являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md), и оба выполняют автоматическую подсчет ссылок.  
  
 **CComPtr** И классы [CComQIPtr](../../atl/reference/ccomqiptr-class.md) могут помочь исключить утечки памяти с помощью автоматического подсчета ссылок.  Следующие функции оба выполняют одни и те же логической операции; однако обратите внимание, что вторая версия может быть менее подвержена ошибкам с помощью класса **CComPtr**:  
  
 [!CODE [NVC_ATL_Utilities#130](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#130)]  
  
 [!CODE [NVC_ATL_Utilities#131](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#131)]  
  
 В построениях отладки, связь atlsd.lib для трассировки кода.  
  
## Иерархия наследования  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [Class Overview](../../atl/atl-class-overview.md)