---
title: 'Набор записей: Прокрутка (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 19058ec3d9a7840fc0e90be84f2734c49f2c8e85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096211"
---
# <a name="recordset-scrolling-odbc"></a>Набор записей. Прокрутка (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 После открытия набора записей требуется получить доступ к записям для отображения значений, выполнения расчетов, создания отчетов и т. д. Прокрутка позволяет переходить от записи к записи в наборе записей.  
  
 Содержание раздела:  
  
-   [Переход от одной записи к другой в наборе записей](#_core_scrolling_from_one_record_to_another).  
  
-   [В разделе что обстоятельствах прокрутки и не поддерживается](#_core_when_scrolling_is_supported).  
  
##  <a name="_core_scrolling_from_one_record_to_another"></a> Переход от одной записи в другую  
 Класс `CRecordset` предоставляет **переместить** функции-члены для прокрутки в наборе записей. Эти функции текущая запись перемещается по строкам. Если применяется выборка строк, **переместить** операция изменяет положение набора записей по размеру набора строк. При получении вызова строк не реализована **переместить** функция изменяет положение набора записей по одной записи каждый раз. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  При перемещении по набору записей, удаленные записи не могут быть пропущены. Дополнительные сведения см. в разделе [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) функции-члена.  
  
 В дополнение к **переместить** функции, `CRecordset` предоставляет функции-члены для проверки, ли переход после конца или до начала набора записей.  
  
 Чтобы определить, возможна ли прокрутка в наборе записей, вызовите `CanScroll` функции-члена.  
  
#### <a name="to-scroll"></a>Для прокрутки  
  
1.  Вперед на одну запись или набор строк: вызовите [MoveNext](../../mfc/reference/crecordset-class.md#movenext) функции-члена.  
  
2.  Назад на одну запись или набор строк: вызовите [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) функции-члена.  
  
3.  К первой записи в наборе записей: вызовите [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) функции-члена.  
  
4.  К последней записи в наборе записей или к последнему набору строк: вызовите [MoveLast](../../mfc/reference/crecordset-class.md#movelast) функции-члена.  
  
5.  *N* записей относительно текущей позиции: вызовите [переместить](../../mfc/reference/crecordset-class.md#move) функции-члена.  
  
#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>Для проверки на начало или конец набора записей  
  
1.  Выполнен переход за последней записью? Вызовите [IsEOF](../../mfc/reference/crecordset-class.md#iseof) функции-члена.  
  
2.  Выполнена прокрутка перед первой записью (Перемещение назад)? Вызовите [IsBOF](../../mfc/reference/crecordset-class.md#isbof) функции-члена.  
  
 Следующий пример кода использует `IsBOF` и `IsEOF` для определения границ набора записей при прокрутке в любом направлении.  
  
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
  
 `IsEOF` возвращает ненулевое значение, если набор записей располагается за последней записью. `IsBOF` возвращает ненулевое значение, если набор записей располагается перед первой записью (перед всеми записями). В любом случае отсутствует текущая запись. для работы с. При вызове метода `MovePrev` при `IsBOF` уже **TRUE** или вызвать `MoveNext` при `IsEOF` уже **TRUE**, платформа создает `CDBException`. Можно также использовать `IsBOF` и `IsEOF` для проверки на пустой набор записей.  
  
 Дополнительные сведения о перемещении по набору записей см. в разделе [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="_core_when_scrolling_is_supported"></a> Когда поддерживается перемещение  
 Изначально SQL обеспечивалось только перемещение вперед, однако ODBC расширяет возможности переходов. Возможный уровень поддержки перемещения зависит от драйверов ODBC, приложение работает с помощью драйвера ODBC, уровня API соответствия и ли загружаются в память библиотека курсоров ODBC. Дополнительные сведения см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [ODBC: библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
> [!TIP]
>  Можно выбрать, следует ли использовать библиотеку курсоров. В разделе `bUseCursorLib` и `dwOptions` параметры [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open).  
  
> [!NOTE]
>  В отличие от классов MFC DAO, классы MFC ODBC не предоставляют набор **найти** функции для поиска следующей (или предыдущей) записи, которая отвечает указанным критериям.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)   
 [CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)   
 [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)