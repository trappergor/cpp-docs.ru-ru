---
title: 'Набор записей: Объединение (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0be740a57f5c455b971dd23575401c666bf0723c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093315"
---
# <a name="recordset-performing-a-join-odbc"></a>Набор записей. Объединение (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
## <a name="what-a-join-is"></a>То, что соединение представляет  
 Операция объединения, часто выполняется доступ к данным, позволяет работать с данными из нескольких таблиц с одним объектом набора записей с помощью. Объединение двух или более таблиц приводит записей, который может содержать столбцы из каждой таблицы, но отображается в виде одной таблицы в приложение. В одних случаях объединяются все столбцы из всех таблиц, но иногда SQL **ВЫБЕРИТЕ** предложение в соединении используются только некоторые столбцы из каждой таблицы. Классы баз данных поддерживают объединения только для чтения, но не поддерживают обновляемые объединения.  
  
 Чтобы выбрать записи, содержащие столбцы из соединяемых таблиц, необходимы следующие элементы:  
  
-   Список таблиц, содержащий имена всех соединяемых таблиц.  
  
-   Список столбцов, содержащий имена всех участвующих столбцов. Столбцы с тем же именем, но из различных таблиц уточняется именем таблицы.  
  
-   Фильтр (SQL **ГДЕ** предложение), указывает столбцы, по которым происходит объединение таблиц. Этот фильтр принимает форму «Table1.KeyCol = Table2.KeyCol» и фактически выполняет соединение.  
  
 Можно объединить больше двух таблиц таким же образом, приравнивания нескольких пар столбцов, каждая пара объединить с помощью ключевого слова SQL **AND**.  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Объявление класса для предопределенного запроса (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)   
 [Набор записей: Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Набор записей. Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)