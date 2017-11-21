---
title: "Набор записей: Блокировка (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3c9e8336e0ef26c1547d5bc495dfbb3e89e7ee91
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="recordset-locking-records-odbc"></a>Набор записей: блокировка (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Содержание раздела:  
  
-   [Типы блокировки записи](#_core_record.2d.locking_modes).  
  
-   [Как блокировать записи в наборе записей, во время обновления](#_core_locking_records_in_your_recordset).  
  
 При использовании набора записей для обновления записей в источнике данных, приложение может блокировать запись, чтобы другие пользователи не могли обновлять запись одновременно. Состояние записи, обновляемой двумя пользователями в то же время не определено, если система гарантировать, что два пользователя не может обновить записи одновременно.  
  
> [!NOTE]
>  Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовая выборка не был реализован. Если реализована массовая выборка строк, некоторые данные не применяется. Например, невозможно вызвать **изменить** и **обновление** функции-члены. Дополнительные сведения о массовой выборке строк см. в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a>Режимы блокировки записей  
 Классы баз данных предоставляют два [режимы блокировки записей](../../mfc/reference/crecordset-class.md#setlockingmode):  
  
-   Оптимистическая блокировка (по умолчанию)  
  
-   Пессимистическая блокировка  
  
 Обновление записи происходит в три этапа:  
  
1.  Начать операцию, вызвав [изменить](../../mfc/reference/crecordset-class.md#edit) функции-члена.  
  
2.  Вы меняете соответствующие поля текущей записи.  
  
3.  Операция завершена и обычно выполняется обновление — путем вызова [обновление](../../mfc/reference/crecordset-class.md#update) функции-члена.  
  
 Оптимистическая блокировка блокирует запись в источнике данных только во время **обновление** вызова. При использовании оптимистической блокировки в многопользовательской среде, то приложение должно обрабатывать **обновление** условие сбоя. Пессимистическая блокировка блокирует запись сразу после вызова **изменить** и не высвобождается только после вызова **обновление** (сбои обозначаются с помощью `CDBException` механизма, а не по значению **FALSE** возвращенных **обновление**). Пессимистическая блокировка имеет потенциальные проблемы с производительностью для других пользователей, так как одновременный доступ к той же записи придется ждать завершения приложения **обновление** процесса.  
  
##  <a name="_core_locking_records_in_your_recordset"></a>Блокировка записей в наборе записей  
 Если вы хотите изменить объекта набора записей [режим блокировки](#_core_record.2d.locking_modes) по умолчанию, необходимо изменить режим перед вызовом метода **изменить**.  
  
#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>Чтобы изменить текущий режим блокировки для набора записей  
  
1.  Вызовите [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) функция-член, указав **CRecordset::pessimistic** или **CRecordset::optimistic**.  
  
 Новый режим блокировки остается в силе до повторного изменения или закрытии набора записей.  
  
> [!NOTE]
>  Относительно немного драйверов ODBC в настоящее время поддерживает пессимистичных блокировок.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)