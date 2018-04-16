---
title: 'Набор записей: Закладки и абсолютное позиционирование (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SetAbsolutePosition
dev_langs:
- C++
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b206e5d09d86613af0585df7510b0f88397984a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>Набор записей. Закладки и абсолютное позиционирование (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 При перемещении по набору записей, часто требуется иметь возможность вернуться к конкретной записи. Существуют два метода: закладки и абсолютное позиционирование записи.  
  
 Содержание раздела:  
  
-   [Описание использования закладок](#_core_bookmarks_in_mfc_odbc).  
  
-   [Как задать текущей записи при помощи абсолютное позиционирование](#_core_absolute_positions_in_mfc_odbc).  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a>Закладки в MFC ODBC  
 Закладка однозначно определяет запись. При переходе по набору записей нельзя всегда полагаться на абсолютное положение записи, поскольку записи могут быть удалены из набора записей. Надежный способ для отслеживания позиции записи является использование закладок. Класс `CRecordset` предоставляет функции-члены для:  
  
-   Установка закладки для текущей записи, его можно сохранить в переменной ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).  
  
-   Быстрое перемещение к определенной записи с помощью указания ее закладки, ранее сохраненной в переменной ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).  
  
 Следующий пример иллюстрирует использование этих функций-членов для пометки текущей записи и последующего возврата к ней:  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 Необходимо извлечь из базового типа данных [CDBVariant-класс](../../mfc/reference/cdbvariant-class.md) объекта. Присвойте значение с `GetBookmark` и вернуться к закладке с `SetBookmark`.  
  
> [!NOTE]
>  В зависимости от драйвера ODBC и тип набора записей закладки может быть прекращена. Можно легко определить, поддерживаются ли закладки, вызвав [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark). Кроме того, поддерживаются ли закладки, необходимо явно выбрать их реализации, указав **CRecordset::useBookmarks** в диалоговом окне [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) функции-члена. Необходимо также проверить наличие закладок после определенных операций по набору записей. Например если вы **Requery** набор записей закладки могут нет сохраниться. Вызовите [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) для проверки, можно ли осуществить безопасный вызов `SetBookmark`.  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a>Абсолютное позиционирование ODBC в библиотеке MFC  
 Помимо закладок класс `CRecordset` позволяет использовать текущую запись, указав его порядковому номеру. Это называется абсолютного позиционирования.  
  
> [!NOTE]
>  Абсолютное позиционирование не доступен на наборы последовательного доступа. Дополнительные сведения о наборах последовательного доступа см. в разделе [записей (ODBC)](../../data/odbc/recordset-odbc.md).  
  
 Чтобы переместить указатель текущей записи, с помощью абсолютное положение, вызовите [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition). При передаче значения в `SetAbsolutePosition`, запись, соответствующую, порядковый номер становится текущей записи.  
  
> [!NOTE]
>  Абсолютное позиционирование записи может оказаться потенциально ненадежным. Если пользователь удалит записи из набора записей, изменяет порядковый номер всех последующих записей. Закладки-это рекомендуемый метод для перемещения к текущей записи. Дополнительные сведения см. в разделе [закладки в MFC ODBC](#_core_bookmarks_in_mfc_odbc).  
  
 Дополнительные сведения о перемещении по набору записей см. в разделе [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)