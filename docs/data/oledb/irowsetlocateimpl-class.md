---
title: Класс IRowsetLocateImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl
dev_langs:
- C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: db8d0b5d81a53a71413998b39947eb71a1bd508a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111033"
---
# <a name="irowsetlocateimpl-class"></a>Класс IRowsetLocateImpl
Реализует OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) интерфейс, который извлекает строки из набора строк.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
       T,   
       RowsetInterface,   
       RowClass,   
       MapClass>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetLocateImpl`.  
  
 `RowsetInterface`  
 Класс, производный от `IRowsetImpl`.  
  
 `RowClass`  
 Устройство хранения для **HROW**.  
  
 `MapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые поставщика.  
  
 `BookmarkKeyType`  
 Тип закладки, например значение типа LONG или строки. Обычные закладки должен иметь длину не менее двух байтов. (Single-byte длина должна быть зарезервирована для OLE DB [стандартные закладки](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK_FIRST**, **DBBMK_LAST**, и **DBBMK_INVALID**.)  
  
 `BookmarkType`  
 Механизм сопоставления для поддержания связи закладки для данных.  
  
 `BookmarkMapClass`  
 Устройство хранения для все дескрипторы строк, удерживаемые закладки.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|Сравнивает две закладки.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Извлекает строки, начиная со строки, указанной в качестве смещения относительно закладки.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Извлекает строки, которые соответствуют указанной закладки.|  
|[хэш](../../data/oledb/irowsetlocateimpl-hash.md)|Возвращает хэш-значения для указанного закладки.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|Массив закладки.|  
  
## <a name="remarks"></a>Примечания  
 `IRowsetLocateImpl` Шаблоны OLE DB реализует [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) интерфейса. `IRowsetLocate` используется для выборки строки из набора строк. Набор строк, который не реализует этот интерфейс является `sequential` набора строк. Когда `IRowsetLocate` присутствует в наборе строк столбца с номером 0 — это закладка для строки; чтение этой статьи будет получать значение закладки, который может использоваться для изменения положения в той же строке.  
  
 `IRowsetLocateImpl` используется для реализации поддержки закладок в поставщиках. Закладки представляют собой заполнители (индексы для набора строк), позволяющие потребителю быстро вернуться к строке, позволяя высокоскоростной доступ к данным. Поставщик определяет закладки возможности однозначно идентифицировать строку. С помощью `IRowsetLocateImpl` методы, можно сравнить закладки, строк выборки, смещение выборки строк по закладке и возвращает хэш-значения для закладки.  
  
 Поддерживает закладки OLE DB в наборе строк, чтобы наследовать от этого класса набора строк.  
  
 Сведения о реализации поддержки закладок см. в разделе [поставщик поддерживает для закладок](../../data/oledb/provider-support-for-bookmarks.md) в *Visual C++ Руководство программиста* и [закладки](https://msdn.microsoft.com/en-us/library/ms709728.aspx) в *Справочника программиста OLE DB* в пакет SDK платформы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок**: atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md)   
 [Закладки](https://msdn.microsoft.com/en-us/library/ms709728.aspx)