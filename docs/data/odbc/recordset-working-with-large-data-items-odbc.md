---
title: Набор записей. Работа с большими элементами данных (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 872fa7229738314b86b6ae6c0d5dc5a5562b27f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360604"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>Набор записей. Работа с большими элементами данных (ODBC)

Эта тема относится как к классам MFC ODBC, так и к классам DFC DAO.

> [!NOTE]
> Если вы используете классы MFC DAO, управляйте большими элементами данных с классом [CByteArray,](../../mfc/reference/cbytearray-class.md) а не [классом CLongBinary.](../../mfc/reference/clongbinary-class.md) Если вы используете классы MFC ODBC с `CLongBinary` объемным извлечения строки, используйте, а `CByteArray`не. Для получения дополнительной информации о массовом строке извлечения, см [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Предположим, что ваша база данных может хранить большие части данных, такие как бит-карты (фотографии сотрудников, карты, фотографии продуктов, объекты OLE и так далее). Этот вид данных часто называют двоичным большим объектом (или BLOB), потому что:

- Каждое значение поля является большим.

- В отличие от чисел и других простых типов данных, он не имеет предсказуемого размера.

- Данные бесформенны с точки зрения вашей программы.

В этой теме объясняется, какую поддержку предоставляют классы баз данных для работы с такими объектами.

## <a name="managing-large-objects"></a><a name="_core_managing_large_objects"></a>Управление крупными объектами

Записи имеют два способа решения особой сложности управления бинарными крупными объектами. Вы можете использовать класс [CByteArray](../../mfc/reference/cbytearray-class.md) или вы можете использовать класс [CLongBinary.](../../mfc/reference/clongbinary-class.md) В целом, `CByteArray` является предпочтительным способом управления большими двоичными данными.

`CByteArray`требует больше накладных расходов, чем, `CLongBinary` но более способны, как описано в классе [CByteArray](#_core_the_cbytearray_class). `CLongBinary`кратко описано в [классе CLongBinary.](#_core_the_clongbinary_class)

Подробную информацию `CByteArray` об использовании для работы с крупными элементами данных можно узнать в [Technical Note 45.](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)

## <a name="cbytearray-class"></a><a name="_core_the_cbytearray_class"></a>Класс CByteArray

`CByteArray`является одним из классов сбора MFC. Объект `CByteArray` хранит динамический массив байтов – массив может расти при необходимости. Класс обеспечивает быстрый доступ по индексу, как и встроенные массивы СЗ. `CByteArray`объекты могут быть сериализованы и сброшены для диагностических целей. Класс поставляет функции участника для получения и установки указанных байтов, вставки и апгвейра байтов, а также удаления одного байта или всех байтов. Эти средства упрощают разбор двоичных данных. Например, если двоичный объект является объектом OLE, возможно, вам придется работать через некоторые байты заголовка, чтобы достичь фактического объекта.

## <a name="using-cbytearray-in-recordsets"></a><a name="_core_using_cbytearray_in_recordsets"></a>Использование CByteArray в рекордных наборах

Предоставляя полевому члену данных `CByteArray`вашего типа recordset, вы предоставляете фиксированную базу, из которой [RFX](../../data/odbc/record-field-exchange-rfx.md) может управлять передачей такого объекта между вашим рекордным набором и источником данных, с помощью которого можно манипулировать данными внутри объекта. RFX нужен конкретный сайт для получения данных, и вам нужен способ доступа к базовым данным.

Подробную информацию `CByteArray` об использовании для работы с крупными элементами данных можно узнать в [Technical Note 45.](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)

## <a name="clongbinary-class"></a><a name="_core_the_clongbinary_class"></a>Класс CLongBinary

Объект [CLongBinary](../../mfc/reference/clongbinary-class.md) представляет собой простую оболочку вокруг ручки `HGLOBAL` к блоку хранения, выделенного на куче. Когда он связывает столбец таблицы, содержащий двоичный `HGLOBAL` большой объект, RFX выделяет ручку, когда `CLongBinary` ей нужно передать данные в набор записей, и хранит ручку в поле рекорда.

В свою очередь, `HGLOBAL` вы `m_hData`используете ручку, для работы с самими данными, работающими на нем, как и на любой ручке данных. Здесь [CByteArray](../../mfc/reference/cbytearray-class.md) добавляет возможности.

> [!CAUTION]
> Объекты CLongBinary не могут использоваться в качестве параметров в функциональных вызовах. Кроме того, их реализация, которая вызывает, `::SQLGetData`обязательно замедляет прокрутку производительности для прокрутки снимок. Это также может быть верно, когда вы используете `::SQLGetData` вызов себя для извлечения динамических столбцов схемы.

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Рекордная полевая биржа (RFX)](../../data/odbc/record-field-exchange-rfx.md)
