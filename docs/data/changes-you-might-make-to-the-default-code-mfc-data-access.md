---
title: Изменения можно вносить в код по умолчанию (доступ к данным MFC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b54b585d2f179cfedf69cd3236228c0cb1ebe7c1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035153"
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>Изменения, которые можно вносить в код по умолчанию (доступ к данным MFC)

[Мастер приложений MFC](../mfc/reference/database-support-mfc-application-wizard.md) создает класс записей, выбирающий все записи в одной таблице. Часто требуется изменить такое поведение одним или несколькими из следующих способов:  
  
- Задание фильтра или порядка сортировки для набора записей. Это можно сделать `OnInitialUpdate` после создания объекта набора записей в но перед его `Open` вызывается функция-член. Дополнительные сведения см. в разделе [набор записей: фильтрация записей (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) и [набор записей: сортировка записей (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
- Параметризация набора записей. Укажите значение фактического параметра времени выполнения после фильтра. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
- Передача настроенной строки SQL для [откройте](../mfc/reference/crecordset-class.md#open) функция-член. Описание можно выполнить с помощью этого способа, см. в разделе [SQL: инструкция SQL Настройка набора записей (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>См. также  

[Использование представления записей](../data/using-a-record-view-mfc-data-access.md)