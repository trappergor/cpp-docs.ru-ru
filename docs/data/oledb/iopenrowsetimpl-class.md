---
title: Класс IOpenRowsetImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
- CreateRowset method
- OpenRowset method
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dd3281aa21cfd20caa902572e9ad39e16a18e6f6
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269830"
---
# <a name="iopenrowsetimpl-class"></a>Класс IOpenRowsetImpl
Предоставляет реализацию для `IOpenRowset` интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
### <a name="parameters"></a>Параметры  
 *SessionClass*  
 Ваш класс, производный от `IOpenRowsetImpl`.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CreateRowset](#createrowset)|Создает объект набора строк. Не вызывается непосредственно пользователем.|  
|[OpenRowset](#openrowset)|Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. (Не в ATLDB. H)|  
  
## <a name="remarks"></a>Примечания  
 [IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx) интерфейс является обязательным для объекта сеанса. Она открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса.  
  
## <a name="createrowset"></a> IOpenRowsetImpl::CreateRowset
Создает объект набора строк. Не вызывается непосредственно пользователем. См. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/library/ms716724.aspx) в *справочнике программиста OLE DB.*  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Параметры  
 *RowsetClass*  
 Член класса шаблона, представляющий пользователя класса набора строк. Как правило, создаются с помощью мастера.  
  
 *pRowsetObj*  
 [out] Указатель на объект набора строк. Обычно этот параметр не используется, но он может использоваться, если необходимо выполнить дополнительные действия в наборе строк перед его передачей в COM-объект. Время существования *pRowsetObj* привязана к *ppRowset*.  
  
 Другие параметры, см. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/library/ms716724.aspx) в *Справочник программиста OLE DB по.*  

## <a name="openrowset"></a> IOpenRowsetImpl::OpenRowset
Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/library/ms716724.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Этот метод не найден в ATLDB. З. Он создается с помощью мастера объекта ATL, при создании поставщика.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
