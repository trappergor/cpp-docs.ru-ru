---
title: "IRunnableObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IRunnableObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "контейнеры, running controls"
  - "элементы управления [ATL], выполнение"
  - "элементы управления [C++], container running in ATL"
  - "IRunnableObject, ATL -реализация"
  - "IRunnableObjectImpl class"
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRunnableObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию для интерфейса [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IRunnableObjectImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IRunnableObjectImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IRunnableObjectImpl::GetRunningClass](../Topic/IRunnableObjectImpl::GetRunningClass.md)|Возвращает идентификатор CLSID выполнению элемента управления.  Реализация библиотеки ATL задает CLSID для `GUID_NULL` и возвращает **E\_UNEXPECTED**.|  
|[IRunnableObjectImpl::IsRunning](../Topic/IRunnableObjectImpl::IsRunning.md)|Определяет, если элемент управления работает.  Реализация библиотеки ATL возвращает **TRUE**.|  
|[IRunnableObjectImpl::LockRunning](../Topic/IRunnableObjectImpl::LockRunning.md)|Блокирует элемент управления в состояние выполнения.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IRunnableObjectImpl::Run](../Topic/IRunnableObjectImpl::Run.md)|Принудительно вызывает элемент управления выполнять.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IRunnableObjectImpl::SetContainedObject](../Topic/IRunnableObjectImpl::SetContainedObject.md)|Указывает, что элемент управления внедрения.  Реализация библиотеки ATL возвращает `S_OK`.|  
  
## Заметки  
 Интерфейс [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) предоставляет контейнер для определения, является ли элемент управления работает, то принудительно его запустить или блокирует его в состояние выполнения.  Класс `IRunnableObjectImpl` предоставляет реализацию по умолчанию для интерфейса и реализуется **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)