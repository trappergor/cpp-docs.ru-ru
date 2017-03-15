---
title: "Класс IErrorRecordsImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IErrorRecordsImpl"
  - "ATL.IErrorRecordsImpl"
  - "IErrorRecordsImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IErrorRecordsImpl - класс"
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс IErrorRecordsImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует интерфейс OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx), а для записи и извлечения записи из элемента данных \([m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)\)`RecordClass`**\>** типа  **CAtlArray\<**.  
  
## Синтаксис  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IErrorRecordsImpl`.  
  
 `RecordClass`  
 Класс, представляющий объект ошибки OLE DB.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Получает строку описания ошибки записи ошибок.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Получает ошибку GUID из записи ошибок.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Получает контекстный идентификатор справки из записи ошибок.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Возвращает полный путь к файлу справки из записи ошибок.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Получает исходный код ошибки из записи ошибок.|  
  
### Методы Interface  
  
|||  
|-|-|  
|[AddErrorRecord](../Topic/IErrorRecordsImpl::AddErrorRecord.md)|Добавляет запись в объект ошибки OLE DB.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Возвращает основные сведения об ошибке, например номер кода возврата и ошибок, связанных с поставщиком.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Возвращает указатель на интерфейс объекта настраиваемой ошибки.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Возвращает указатель интерфейса [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) для конкретной записи.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Возвращает параметры ошибки.|  
|[GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Возвращает число записей в объекте набора записей OLE DB.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Массив записей ошибок.|  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)