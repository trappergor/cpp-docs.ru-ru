---
title: Класс IRowsetImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs:
- C++
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59793d206f8b53d57347070cbfccd6d98ff2c005
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321959"
---
# <a name="irowsetimpl-class"></a>Класс IRowsetImpl
Предоставляет реализацию интерфейса `IRowset`.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*>>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IRowsetImpl`.  
  
 *RowsetInterface*  
 Класс, производный от `IRowsetImpl`.  
  
 *RowClass*  
 Единица хранения для `HROW`.  
  
 *MapClass*  
 Единица хранения для всех дескрипторов строк, удерживаемые поставщика.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddRefRows](#addrefrows)|Добавляет счетчик ссылок в дескриптор существующей строки.|  
|[CreateRow](#createrow)|Вызывается средой [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) выделить новый `HROW`. Не вызывается непосредственно пользователем.|  
|[GetData](#getdata)|Извлекает данные из копии строки в наборе строк.|  
|[GetDBStatus](#getdbstatus)|Возвращает состояние для указанного поля.|  
|[GetNextRows](#getnextrows)|Последовательно извлекает строки с запоминанием предыдущей позиции.|  
|[IRowsetImpl](#irowsetimpl)|Конструктор. Не вызывается непосредственно пользователем.|  
|[RefRows](#refrows)|Вызывается средой [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Не вызывается непосредственно пользователем.|  
|[ReleaseRows](#releaserows)|Высвобождает строки.|  
|[Свойство RestartPosition](#restartposition)|Перемещает позицию следующей выборки в его начальное положение; то есть его положение при первом набора строк создан.|  
|[SetDBStatus](#setdbstatus)|Задает флаги состояния для указанного поля.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bCanFetchBack](#bcanfetchback)|Указывает, поддерживает ли поставщик обратной выборки.|  
|[m_bCanScrollBack](#bcanscrollback)|Указывает ли поставщик может включать его курсор прокрутки назад.|  
|[m_bReset](#breset)|Указывает, ли поставщик сбросить его положение курсора. Это имеет особое значение при прокрутке в обратном направлении или выборка в обратном направлении [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m_iRowset](#irowset)|Индекс для набора строк, представляющий курсор.|  
|[m_rgRowHandles](#rgrowhandles)|Список дескрипторов строк.|  
  
## <a name="remarks"></a>Примечания  
 [IRowset](https://msdn.microsoft.com/library/ms720986.aspx) — это базовый интерфейс набора строк.  

## <a name="addrefrows"></a> IRowsetImpl::AddRefRows
Добавляет счетчик ссылок в дескриптор существующей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::AddRefRows](https://msdn.microsoft.com/library/ms719619.aspx) в *справочнике программиста OLE DB*.  

## <a name="createrow"></a> IRowsetImpl::CreateRow
Вспомогательный метод, вызываемый [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) выделить новый `HROW`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>Параметры  
 *lRowsOffset*  
 Позиция курсора создаваемой строки.  
  
 *cRowsObtained*  
 Ссылка передается обратно пользователю, указывающее число созданных строк.  
  
 *rgRows*  
 Массив `HROW`s возвращается вызывающей стороне с дескрипторами только что созданной строки.  
  
### <a name="remarks"></a>Примечания  
 Если строка существует, этот метод вызывает [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и возвращает. В противном случае выделяет новый экземпляр переменной шаблона RowClass и добавляет ее к [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="getdata"></a> IRowsetImpl::GetData
Извлекает данные из копии строки в наборе строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::GetData](https://msdn.microsoft.com/library/ms716988.aspx) в *справочнике программиста OLE DB*.  
  
 Некоторые параметры соответствуют *Справочник программиста OLE DB по* параметры разные имена, которые описаны в `IRowset::GetData`:  
  
|Параметры шаблона OLE DB|*Справочник программиста OLE DB по* параметров|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|*pData*|  
  
### <a name="remarks"></a>Примечания  
 Также обрабатывает преобразование данных с помощью преобразования данных OLE DB для библиотеки DLL. 

## <a name="getdbstatus"></a> IRowsetImpl::GetDBStatus
Возвращает флаги состояния DBSTATUS для указанного поля.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] *currentRow*  
 Текущая строка.  
  
 [in] *columnNames*  
 Столбец, для которого запрашивается состояние.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx) флаги для столбца. 

## <a name="getnextrows"></a> IRowsetImpl::GetNextRows
Последовательно извлекает строки с запоминанием предыдущей позиции.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetNextRows )(HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::GetNextRows](https://msdn.microsoft.com/library/ms709827.aspx) в *справочнике программиста OLE DB*. 

## <a name="irowsetimpl"></a> IRowsetImpl::IRowsetImpl
Конструктор.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
IRowsetImpl();  
  
```  
  
### <a name="remarks"></a>Примечания  
 Обычно не требуется вызывать этот метод напрямую.  

## <a name="refrows"></a> IRowsetImpl::RefRows
Вызывается средой [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) увеличивается или выпуска счетчик ссылок в дескриптор существующей строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT RefRows(DBCOUNTITEM cRows,  
   const HROWrghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::AddRefRows](https://msdn.microsoft.com/library/ms719619.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  

## <a name="releaserows"></a> IRowsetImpl::ReleaseRows
Высвобождает строки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBROWOPTIONS rgRowOptions[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::ReleaseRows](https://msdn.microsoft.com/library/ms719771.aspx) в *справочнике программиста OLE DB*.  

## <a name="restartposition"></a> IRowsetImpl::RestartPosition
Перемещает позицию следующей выборки в его начальное положение; то есть его положение при первом набора строк создан.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowset::RestartPosition](https://msdn.microsoft.com/library/ms712877.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Положение в наборе строк не определено до `GetNextRow` вызывается. Вы можете переместить назад в rowet путем вызова `RestartPosition` и затем выборку и прокрутку в обратном направлении.  

## <a name="setdbstatus"></a> IRowsetImpl::SetDBStatus
Задает флаги состояния DBSTATUS для указанного поля.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
```  
  
#### <a name="parameters"></a>Параметры  
 *statusFlags*  
 [DBSTATUS](https://msdn.microsoft.com/library/ms722617.aspx) флажки, которые нужно установить для столбца.  
  
 *currentRow*  
 Текущая строка.  
  
 *columnInfo*  
 Столбец, для которой задается состояние.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Поставщик переопределяет эту функцию для предоставления специальной обработки для DBSTATUS_S_ISNULL и DBSTATUS_S_DEFAULT. 

## <a name="bcanfetchback"></a> IRowsetImpl::m_bCanFetchBack
Указывает, поддерживает ли поставщик обратной выборки.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bCanFetchBack:1;  
  
```  
  
### <a name="remarks"></a>Примечания  
 Связанная с `DBPROP_CANFETCHBACKWARDS` свойство в `DBPROPSET_ROWSET` группы. Поставщик должен поддерживать `DBPROP_CANFETCHBACKWARDS` для `m_bCanFetchBackwards` быть **true**.  

## <a name="bcanscrollback"></a> IRowsetImpl::m_bCanScrollBack
Указывает ли поставщик может включать его курсор прокрутки назад.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned  m_bCanScrollBack:1;  
  
```  
  
### <a name="remarks"></a>Примечания  
 Связанная с `DBPROP_CANSCROLLBACKWARDS` свойство в `DBPROPSET_ROWSET` группы. Поставщик должен поддерживать `DBPROP_CANSCROLLBACKWARDS` для `m_bCanFetchBackwards` быть **true**. 

## <a name="breset"></a> IRowsetImpl::m_bReset
Битовый флаг, используемый для определения того, если положение курсора определяется в наборе строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
### <a name="remarks"></a>Примечания  
 Если потребитель вызывает метод [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) с отрицательным `lOffset` или *cRows* и `m_bReset` имеет значение true, `GetNextRows` перемещается в конец набора строк. Если `m_bReset` имеет значение false, получатель принимает код ошибки, в соответствии со спецификацией OLE DB. `m_bReset` Флаг получает значение **true** при первоначальном создании набора строк, и когда потребитель вызывает [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md). Он возвращает значение **false** при вызове `GetNextRows`. 

## <a name="irowset"></a> IRowsetImpl::m_iRowset
Индекс для набора строк, представляющий курсор.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
DBROWOFFSET m_iRowset;  
  
```  

## <a name="rgrowhandles"></a> IRowsetImpl::m_rgRowHandles
Сопоставления дескрипторов строк, в настоящее время содержатся поставщиком в ответ на `GetNextRows`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
MapClass  
 m_rgRowHandles;  
  
```  
  
### <a name="remarks"></a>Примечания  
 Дескрипторы строк удаляются путем вызова `ReleaseRows`. См. в разделе [Обзор IRowsetImpl](../../data/oledb/irowsetimpl-class.md) для определения *MapClass*.  

## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)    
 [Класс CSimpleRow](../../data/oledb/csimplerow-class.md)
