---
title: "Изменения можно вносить в код по умолчанию (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 197277a68131c9d63e3eab2f1404cf97169be1f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)
[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) создает класс записей, выбирающий все записи в одной таблице. Часто требуется изменить такое поведение одним или несколькими из следующих способов:  
  
-   Задание фильтра или порядка сортировки для набора записей. Для этого в `OnInitialUpdate` после создания объекта набора записей перед вызовом его **откройте** вызвать функцию-член. Дополнительные сведения см. в разделе [набор записей: фильтрация записей (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) и [набор записей: сортировка записей (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Параметризация набора записей. Укажите значение фактического параметра времени выполнения после фильтра. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Передача настроенной строки SQL для [откройте](../mfc/reference/crecordset-class.md#open) функции-члена. Описание можно выполнить с помощью этого метода см. в разделе [SQL: инструкция SQL Настройка набора записей (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [Использование представления записей](../data/using-a-record-view-mfc-data-access.md)