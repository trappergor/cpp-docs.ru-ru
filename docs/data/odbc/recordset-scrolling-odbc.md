---
title: Набор записей. Прокрутка (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
ms.openlocfilehash: 5df8151664bd7e726087cb5323c1e4622264ad23
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040060"
---
# <a name="recordset-scrolling-odbc"></a>Набор записей. Прокрутка (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

После открытия набора записей, вы должны получить доступ к записям для отображения значений, выполнять вычисления, создавать отчеты и так далее. Прокрутка позволяет переходить от записи к записи в пределах набора записей.

Содержание раздела:

- [Переход от одной записи к другой в наборе записей](#_core_scrolling_from_one_record_to_another).

- [В разделе новые обстоятельства прокрутка и не поддерживается](#_core_when_scrolling_is_supported).

##  <a name="_core_scrolling_from_one_record_to_another"></a> Переход от одной записи в другую

Класс `CRecordset` предоставляет `Move` функции-члены для прокрутки в наборе записей. Эти функции наборов строк для перемещения текущей записи. Если вы реализовали выборка строк, `Move` операция изменяет положение набора записей по размеру набора строк. Если вы не реализовали строк выборки, вызов `Move` функция изменяет положение набора записей по одной записи каждый раз. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
>  При перемещении по набору записей, удаленные записи не могут быть пропущены. Дополнительные сведения см. в разделе [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) функция-член.

В дополнение к `Move` функции, `CRecordset` предоставляет функции-члены для проверки ли были прокручены за пределами или выполнен набор записей.

Чтобы определить, возможна ли прокрутка в наборе записей, вызовите `CanScroll` функция-член.

#### <a name="to-scroll"></a>Для прокрутки

1. Пересылать одну запись или набор строк: вызовите [MoveNext](../../mfc/reference/crecordset-class.md#movenext) функция-член.

1. Назад на одну запись или набор строк: вызовите [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) функция-член.

1. Для первой записи в наборе записей: вызовите [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) функция-член.

1. К последней записи в наборе записей или к последнему набору строк: вызовите [MoveLast](../../mfc/reference/crecordset-class.md#movelast) функция-член.

1. *N* записей относительно текущей позиции: вызовите [переместить](../../mfc/reference/crecordset-class.md#move) функция-член.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Для проверки на конце или в начале набора записей

1. Были прокручены за последней записью? Вызовите [IsEOF](../../mfc/reference/crecordset-class.md#iseof) функция-член.

1. Были прокручены перед первой записью (Перемещение назад)? Вызовите [IsBOF](../../mfc/reference/crecordset-class.md#isbof) функция-член.

В следующем примере кода используется `IsBOF` и `IsEOF` для определения границ набора записей, во время прокрутки в любом направлении.

```
// Open a recordset; first record is current
CCustSet rsCustSet( NULL );
rsCustSet.Open( );

if( rsCustSet.IsBOF( ) )
    return;
    // The recordset is empty

// Scroll to the end of the recordset, past
// the last record, so no record is current
while ( !rsCustSet.IsEOF( ) )
    rsCustSet.MoveNext( );

// Move to the last record
rsCustSet.MoveLast( );

// Scroll to beginning of the recordset, before
// the first record, so no record is current
while( !rsCustSet.IsBOF( ) )
    rsCustSet.MovePrev( );

// First record is current again
rsCustSet.MoveFirst( );
```

`IsEOF` возвращает ненулевое значение, если набор записей располагается за последней записью. `IsBOF` возвращает ненулевое значение, если набор записей располагается перед первой записью (перед всеми записями). В любом случае отсутствует текущий запись для работы. При вызове метода `MovePrev` при `IsBOF` уже TRUE или вызвать `MoveNext` при `IsEOF` уже имеет значение TRUE, платформа создает `CDBException`. Можно также использовать `IsBOF` и `IsEOF` для проверки на пустой набор записей.

Дополнительные сведения о перемещении по набору записей, см. в разделе [набор записей: Закладки и абсолютное позиционирование (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="_core_when_scrolling_is_supported"></a> Когда поддерживается перемещение

Изначально SQL предоставлен только прямую прокрутку, но ODBC расширяет возможности переходов. Доступные уровень поддержки для прокрутки зависит от драйверов ODBC, приложение работает с уровень соответствия драйвера ODBC API, и ли библиотека курсоров ODBC загружена в память. Дополнительные сведения см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [ODBC: Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!TIP]
>  Вы можете управлять, следует ли использовать библиотеку курсоров. См. в разделе *bUseCursorLib* и *dwOptions* параметров [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open).

> [!NOTE]
>  В отличие от классов MFC DAO, классы MFC ODBC не предоставляют набор `Find` функции для поиска следующей (или предыдущей) записи, которая удовлетворяет указанным критериям.

## <a name="see-also"></a>См. также

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)