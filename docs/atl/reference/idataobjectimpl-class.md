---
title: "IDataObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data transfer [C++]"
  - "data transfer [C++], Uniform Data Transfer"
  - "IDataObject, ATL -реализация"
  - "IDataObjectImpl class"
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IDataObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для поддержки равномерную передачу данных и управление соединениями.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IDataObjectImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IDataObjectImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDataObjectImpl::DAdvise](../Topic/IDataObjectImpl::DAdvise.md)|Устанавливает соединение между объектом данных и получатель advise.  Это позволяет приемник advise для получения уведомлений изменений в объекте.|  
|[IDataObjectImpl::DUnadvise](../Topic/IDataObjectImpl::DUnadvise.md)|Завершает соединение установлено с помощью ранее `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](../Topic/IDataObjectImpl::EnumDAdvise.md)|Создает перечислитель для итерации по текущим вспомогательным соединениям.|  
|[IDataObjectImpl::EnumFormatEtc](../Topic/IDataObjectImpl::EnumFormatEtc.md)|Создает перечислитель для прохода по **FORMATETC** структуры данных, поддерживаемые объектом.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](../Topic/IDataObjectImpl::FireDataChange.md)|Отправляет уведомление об изменениях обратно к каждому посоветуйте приемник.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](../Topic/IDataObjectImpl::GetCanonicalFormatEtc.md)|Извлекает логическую структуру, которая подходит **FORMATETC** одно, более сложным.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IDataObjectImpl::GetData](../Topic/IDataObjectImpl::GetData.md)|Передает данные из объекта данных клиенту.  Данные описаны в структуре **FORMATETC** и Переключены через структуру **STGMEDIUM**.|  
|[IDataObjectImpl::GetDataHere](../Topic/IDataObjectImpl::GetDataHere.md)|Подобно `GetData`, за исключением того, что клиент должен выбрать структуру **STGMEDIUM**.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](../Topic/IDataObjectImpl::QueryGetData.md)|Определяет, поддерживает ли объект данных указанную структуру **FORMATETC** для передачи данных.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IDataObjectImpl::SetData](../Topic/IDataObjectImpl::SetData.md)|Передает данные от клиента в объект данных.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Интерфейс [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) предоставляет методы для передачи данных формы поддержки.  `IDataObject` использует структуры [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) и [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) стандартного формата для получения и хранения данных.  
  
 `IDataObject` также управляет соединениями, чтобы advise приемникам для обработки уведомлений об изменении данных.  Для этого клиента для получения уведомлений об изменении данных из объекта данных, клиент должен реализовать интерфейс [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) вызванного объекта получателем advise.  Если после этого клиент вызывает метод **IDataObject::DAdvise**, устанавливается соединение между объектом данных и получателем advise.  
  
 Класс `IDataObjectImpl` предоставляет реализацию по умолчанию `IDataObject` и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)