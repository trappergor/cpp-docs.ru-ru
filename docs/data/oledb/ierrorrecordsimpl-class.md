---
title: Класс IErrorRecordsImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0d0425e7765cf09abb870cb39720cf43c8c74174
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105469"
---
# <a name="ierrorrecordsimpl-class"></a>Класс IErrorRecordsImpl
Реализует OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) интерфейс, добавление записей, а также получение записей из элемента данных ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) типа **CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IErrorRecordsImpl`.  
  
 `RecordClass`  
 Класс, представляющий объект OLE DB error.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|Возвращает строку описания ошибки из записи об ошибке.|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|Возвращает ошибку, GUID из записи об ошибке.|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|Возвращает идентификатор контекста справки из записи об ошибке.|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|Возвращает полный путь файла справки из записи об ошибке.|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|Возвращает исходный код ошибки из записи об ошибке.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|Добавляет запись в объект ошибки OLE DB.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Возвращает основные сведения об ошибке, например, код возврата и номер ошибки поставщика.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Возвращает указатель интерфейса на объект настраиваемой ошибки.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Возвращает [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) указатель интерфейса на указанную запись.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Возвращает параметры ошибок.|  
|[GetRecordCount](../../mfc/reference/cdaorecordset-class.md#getrecordcount)|Возвращает число записей в записи объект OLE DB.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|Массив записей ошибок.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)