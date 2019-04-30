---
title: Класс IRowsetLocateImpl
ms.date: 11/04/2016
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
ms.openlocfilehash: e3513084697a60a33b9fa2ab02222a9b332cce79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408850"
---
# <a name="irowsetlocateimpl-class"></a>Класс IRowsetLocateImpl

Реализует OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) интерфейс, который извлекает строки из набора строк.

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

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetLocateImpl`.

*RowsetInterface*<br/>
Класс, производный от `IRowsetImpl`.

*RowClass*<br/>
Единица хранения для `HROW`.

*MapClass*<br/>
Единица хранения для всех дескрипторов строк, удерживаемые поставщика.

*BookmarkKeyType*<br/>
Тип закладки, например LONG или строки. Обычные закладки должно иметь длину по крайней мере два байта. (Однобайтовой длины зарезервирован для OLE DB [стандартный закладки](/previous-versions/windows/desktop/ms712954(v=vs.85))`DBBMK_FIRST`, `DBBMK_LAST`, и `DBBMK_INVALID`.)

*BookmarkType*<br/>
Механизм сопоставления для поддержания связи закладку для данных.

*BookmarkMapClass*<br/>
Единица хранения для всех дескрипторов строк, удерживаемые закладки.

## <a name="requirements"></a>Требования

**Заголовок**: atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[Compare](#compare)|Сравнивает два закладки.|
|[GetRowsAt](#getrowsat)|Извлекает строки, начиная со строки, указанной в качестве смещения относительно закладки.|
|[GetRowsByBookmark](#getrowsbybookmark)|Извлекает строки, которые соответствуют указанной закладки.|
|[хэш](#hash)|Возвращает хэш-значения для указанного закладки.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|Массив закладки.|

## <a name="remarks"></a>Примечания

`IRowsetLocateImpl` представляет собой реализацию шаблонов OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) интерфейс. `IRowsetLocate` используется для получения строки из набора строк. Набор строк, который не реализует этот интерфейс является `sequential` набора строк. Когда `IRowsetLocate` присутствует в наборе строк, столбец 0 — это закладка для строки; чтение этой статьи будет получать значение закладки, который может использоваться для изменения положения в той же строке.

`IRowsetLocateImpl` используется для реализации поддержки закладок в поставщиках. Закладки являются заполнителями (индексы для набора строк), которые позволяют потребителю быстро вернуться к строке, позволяя высокоскоростной доступ к данным. Поставщик определяет, что уникально можно закладки идентификации строки. С помощью `IRowsetLocateImpl` методы, вы можете сравнить закладки, строк выборки, смещение, выборки строк по закладке и возвращать хэш-значения для закладки.

Поддерживает закладки OLE DB в наборе строк, чтобы наследовать от этого класса набора строк.

Сведения о реализации поддержки закладки, см. в разделе [поставщик поддерживает для закладок](../../data/oledb/provider-support-for-bookmarks.md) в *Visual C++ Programmer's Guide* и [закладки](/previous-versions/windows/desktop/ms709728(v=vs.85)) в *Справочнике программиста OLE DB* в пакет SDK платформы.

## <a name="compare"></a> IRowsetLocateImpl::Compare

Сравнивает два закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetLocate::Compare](/previous-versions/windows/desktop/ms709539(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Одно из закладки может быть стандартный определяемых OLE DB [стандартный закладки](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST`, `DBBMK_LAST`, или `DBBMK_INVALID`). Значение, возвращаемое в `pComparison` показывает связь между двумя закладки:

- DBCOMPARE_LT (`cbBookmark1` перед `cbBookmark2`.)

- DBCOMPARE_EQ (`cbBookmark1` равен `cbBookmark2`.)

- DBCOMPARE_GT (`cbBookmark1` после `cbBookmark2`.)

- DBCOMPARE_NE (закладки, равно и не упорядоченными.)

- DBCOMPARE_NOTCOMPARABLE (невозможно сравнить закладки.)

## <a name="getrowsat"></a> IRowsetLocateImpl::GetRowsAt

Извлекает строки, начиная со строки, указанной в качестве смещения относительно закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IRowsetLocate::GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

Чтобы получить от позиции курсора вместо этого используйте [IRowset::GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85)).

`IRowsetLocateImpl::GetRowsAt` не изменяет положение курсора.

## <a name="getrowsbybookmark"></a> IRowsetLocateImpl::GetRowsByBookmark

Извлекает один или несколько строк, соответствующих указанным закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
[in] Соответствует *hChapter* параметр [IRowsetLocate::GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85)).

Другие параметры, см. в разделе [IRowsetLocate::GetRowsByBookmark](/previous-versions/windows/desktop/ms725420(v=vs.85)) в *Справочник программиста OLE DB по*.

### <a name="remarks"></a>Примечания

Закладки может быть значение вами или OLE DB [стандартный закладки](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST` или `DBBMK_LAST`). не изменяет положение курсора.

## <a name="hash"></a> IRowsetLocateImpl::Hash

Возвращает хэш-значения для указанного закладки.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>Параметры

*hReserved*<br/>
[in] Соответствует *hChapter* параметр [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697(v=vs.85)).

Другие параметры, см. в разделе [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697(v=vs.85)) в *Справочник программиста OLE DB по*.

## <a name="rgbookmarks"></a> IRowsetLocateImpl::m_rgBookmarks

Массив закладки.

### <a name="syntax"></a>Синтаксис

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate:IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85))
[Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[Закладки](/previous-versions/windows/desktop/ms709728(v=vs.85))