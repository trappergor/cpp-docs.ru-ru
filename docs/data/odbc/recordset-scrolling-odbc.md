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
ms.openlocfilehash: 931051296dff495939fcbd894102a1b00e48ee90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366939"
---
# <a name="recordset-scrolling-odbc"></a>Набор записей. Прокрутка (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

После открытия набора записей необходимо получить доступ к записям для отображения значений, вычислений, создания отчетов и так далее. Прокрутка позволяет перемещаться от записи к записи в пределах вашего рекорда.

В этом разделе рассматриваются следующие вопросы.

- [Как прокрутить от одной записи к другой в рекорде](#_core_scrolling_from_one_record_to_another).

- [При каких обстоятельствах прокрутка является и не поддерживается.](#_core_when_scrolling_is_supported)

## <a name="scrolling-from-one-record-to-another"></a><a name="_core_scrolling_from_one_record_to_another"></a>Прокрутка от одной записи к другой

Класс `CRecordset` предоставляет `Move` функции члена для прокрутки в пределах набора записей. Эти функции перемещаются текущей записью по строкам. Если вы реализовали объемный `Move` ряд извлечения, операция переопределяет запись, установленную размером строки. Если вы не реализовали объемный ряд `Move` извлечения, вызов функции перемещает запись, установленную на одну запись каждый раз. Для получения дополнительной информации о массовом строке извлечения, см [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!NOTE]
> При перемещении через набор записей удаленные записи могут не быть пропущены. Для получения дополнительной [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) информации см.

В дополнение `Move` к `CRecordset` функциям, предоставляет функции члена для проверки ли вы прокрутили мимо конца или впереди начала вашего рекорда.

Чтобы определить, возможна ли прокрутка в `CanScroll` вашем наборе записей, позвоните в функцию участника.

#### <a name="to-scroll"></a>Прокрутка

1. Вперед одну запись или один ряд: вызов функции участника [MoveNext.](../../mfc/reference/crecordset-class.md#movenext)

1. Назад одна запись или один ряд: вызов функции участника [MovePrev.](../../mfc/reference/crecordset-class.md#moveprev)

1. К первой записи в записи: позвоните в функцию участника [MoveFirst.](../../mfc/reference/crecordset-class.md#movefirst)

1. До последней записи в наборе записей или до последнего набора строк: позвоните в функцию участника [MoveLast.](../../mfc/reference/crecordset-class.md#movelast)

1. *N* записывает относительно текущего положения: вызов функции участника [Move.](../../mfc/reference/crecordset-class.md#move)

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Проверить конец или начало рекорда

1. Вы прокрутили последнюю запись? Позвоните в функцию участника [IsEOF.](../../mfc/reference/crecordset-class.md#iseof)

1. Вы прокрутили впереди первой записи (перемещение назад)? Позвоните в функцию участника [IsBOF.](../../mfc/reference/crecordset-class.md#isbof)

Следующий пример `IsBOF` кода `IsEOF` использует и для обнаружения пределов записи при прокрутке в любом направлении.

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

`IsEOF`возвращает ненулевое значение, если рекордет расположен мимо последней записи. `IsBOF`возвращает ненулевое значение, если рекордет расположен раньше первой записи (до всех записей). В любом случае, нет текущего отчета для работы. Если вы `MovePrev` `IsBOF` звоните, когда `MoveNext` `IsEOF` уже правда или вызова, `CDBException`когда уже true, рамки бросает . Вы также `IsBOF` можете `IsEOF` использовать и проверить на пустой рекорд.

Для получения дополнительной информации о навигации, установленной записью, [см.](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

## <a name="when-scrolling-is-supported"></a><a name="_core_when_scrolling_is_supported"></a>При поддержке прокрутки

В первоначальном виде, S'L предоставилтолько только вперед прокрутки, но ODBC расширяет возможности прокрутки. Доступный уровень поддержки прокрутки зависит от драйверов ODBC, с помощью которого работает ваше приложение, от уровня соответствия API API драйвера и от того, загружается ли библиотека ODBC Cursor в память. Для получения дополнительной информации, см [ODBC](../../data/odbc/odbc-basics.md) и [ODBC: ODBC Курсор библиотека](../../data/odbc/odbc-the-odbc-cursor-library.md).

> [!TIP]
> Вы можете контролировать, используется ли библиотека курсора. Смотрите параметры *bUseCursorLib* и *dwOptions* на [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open).

> [!NOTE]
> В отличие от классов MFC DAO, классы MFC `Find` ODBC не предоставляют набор функций для определения местонахождения следующей (или предыдущей) записи, отвечающего определенным критериям.

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetОшибка](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
