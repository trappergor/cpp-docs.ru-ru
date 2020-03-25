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
ms.openlocfilehash: 9a25c0fe4c1f08d376824fbc02211d22c7c14435
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212970"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Набор записей. Закладки и абсолютное позиционирование (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

При переходе по набору записей часто требуется способ возврата к определенной записи. Закладка и абсолютное положение записи предоставляют два таких метода.

В этом разделе рассматриваются следующие вопросы.

- [Как использовать закладки](#_core_bookmarks_in_mfc_odbc).

- [Как задать текущую запись с помощью абсолютных положений](#_core_absolute_positions_in_mfc_odbc).

##  <a name="bookmarks-in-mfc-odbc"></a><a name="_core_bookmarks_in_mfc_odbc"></a>Закладки в MFC ODBC

Закладка однозначно определяет запись. При переходе по набору записей нельзя всегда полагаться на абсолютное положение записи, поскольку записи могут быть удалены из набора записей. Надежный способ контролировать расположение записи — использовать ее закладку. Класс `CRecordset` предоставляет функции элементов для:

- Получение закладки текущей записи, поэтому ее можно сохранить в переменной (-[закладке](../../mfc/reference/crecordset-class.md#getbookmark)).

- Быстрое перемещение в заданную запись путем указания ее закладки, сохраненной ранее в переменной ([сетбукмарк](../../mfc/reference/crecordset-class.md#setbookmark)).

В следующем примере показано, как использовать эти функции элементов для пометки текущей записи и последующего возврата к ней.

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

Не нужно извлекать базовый тип данных из объекта [класса кдбвариант](../../mfc/reference/cdbvariant-class.md) . Присвойте значение с `GetBookmark` и вернитесь к этой закладке с помощью `SetBookmark`.

> [!NOTE]
>  В зависимости от используемого драйвера ODBC и типа набора записей закладки могут не поддерживаться. Можно легко определить, поддерживаются ли закладки, вызвав метод [CRecordset:: канбукмарк](../../mfc/reference/crecordset-class.md#canbookmark). Более того, если закладки поддерживаются, необходимо явно выбрать их реализацию, указав параметр `CRecordset::useBookmarks` в функции элемента [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) . Также следует проверить сохраняемость закладок после выполнения определенных операций с набором записей. Например, если `Requery` набор записей, закладки могут стать недействительными. Вызовите метод [CDatabase:: жетбукмаркперсистенце](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) , чтобы проверить, можно ли безопасно вызвать `SetBookmark`.

##  <a name="absolute-positions-in-mfc-odbc"></a><a name="_core_absolute_positions_in_mfc_odbc"></a>Абсолютные позиции в MFC ODBC

Помимо закладок, класс `CRecordset` позволяет задать текущую запись, указав порядковую точку. Это называется абсолютным позиционированием.

> [!NOTE]
>  Абсолютное позиционирование недоступно для наборов записей с последовательным входом. Дополнительные сведения о наборах записей последовательного доступа см. в разделе [набор записей (ODBC)](../../data/odbc/recordset-odbc.md).

Чтобы переместить указатель текущей записи с помощью абсолютной позиции, вызовите метод [CRecordset:: сетабсолутепоситион](../../mfc/reference/crecordset-class.md#setabsoluteposition). При передаче значения в `SetAbsolutePosition`запись, соответствующая этой порядковой позицией, станет текущей записью.

> [!NOTE]
>  Абсолютное положение записи является потенциально ненадежным. Если пользователь удаляет записи из набора записей, порядковый номер последующих изменений записей. Для перемещения текущей записи рекомендуется использовать закладки. Дополнительные сведения см. [в разделе закладки в MFC ODBC](#_core_bookmarks_in_mfc_odbc).

Дополнительные сведения о переходе по набору записей см. в разделе [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)
