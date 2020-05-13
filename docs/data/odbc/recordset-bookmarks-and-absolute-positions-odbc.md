---
title: Набор записей. Закладки и абсолютное позиционирование (ODBC)
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: 77c8bbaf7c0bc21dab62c3785364e72656287815
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367071"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Набор записей. Закладки и абсолютное позиционирование (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

При навигации по рекорду, вам часто требуется способ возвращения к определенной записи. Закладка записи и абсолютная позиция предоставляют два таких метода.

В этом разделе рассматриваются следующие вопросы.

- [Как использовать закладки](#_core_bookmarks_in_mfc_odbc).

- [Как установить текущий рекорд, используя абсолютные позиции.](#_core_absolute_positions_in_mfc_odbc)

## <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a>Закладки в МФЦ ODBC

Закладка однозначно идентифицирует запись. При навигации по набору записей вы не всегда можете полагаться на абсолютную позицию записи, поскольку записи могут быть удалены из набора записей. Надежный способ отслеживания положения записи заключается в использовании ее закладки. Функциями участника класса `CRecordset` поставок для:

- Получение закладки текущей записи, так что вы можете сохранить его в переменной ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).

- Быстро ехидная запись, указав ее закладку, которую вы сохранили ранее в переменной ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).

Следующий пример иллюстрирует, как использовать эти функции члена для обозначения текущей записи, а затем вернуться к ней:

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

Вам не нужно извлекать базовый тип данных из объекта [класса CDBVariant.](../../mfc/reference/cdbvariant-class.md) Присвоить значение `GetBookmark` и вернуться к `SetBookmark`этой закладке с .

> [!NOTE]
> В зависимости от драйвера ODBC и типа записей закладки могут не поддерживаться. Вы можете легко определить, поддерживаются ли закладки, позвонив [в CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Кроме того, если закладки поддерживаются, необходимо явно `CRecordset::useBookmarks` выбрать их реализацию, указав опцию в функции [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) member. Вы также должны проверить сохранение закладок после определенных операций recordset. Например, если `Requery` вы имеете набор записей, закладки могут быть недействительными. Позвоните [CDatabase::GetBookmarkPersistenceenceenceenceenceence,](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) чтобы проверить, можете ли вы безопасно позвонить `SetBookmark`.

## <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a>Абсолютные позиции в МФЦ ODBC

Помимо закладок, класс `CRecordset` позволяет установить текущий рекорд, указав ординаторскую позицию. Это называется абсолютным позиционированием.

> [!NOTE]
> Абсолютное позиционирование не доступно только на передних рекордах. Для получения дополнительной информации о форвардных рекордах см. [Recordset (ODBC).](../../data/odbc/recordset-odbc.md)

Чтобы переместить текущий указатель рекорда, используя абсолютное положение, позвоните [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition). Когда вы передаете `SetAbsolutePosition`значение, запись, соответствующая этому обыденное положение, становится текущей записью.

> [!NOTE]
> Абсолютная позиция записи потенциально ненадежна. Если пользователь удаляет записи из набора записей, обухатое положение любых последующих записей изменяется. Закладки являются рекомендуемым методом перемещения текущей записи. Для получения дополнительной информации смотрите [закладки в МФЦ ODBC](#_core_bookmarks_in_mfc_odbc).

Для получения дополнительной информации о навигации recordset [см.](../../data/odbc/recordset-scrolling-odbc.md)

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)
