---
title: 'Набор записей: Объединение (ODBC) | Документация Майкрософт'
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
ms.openlocfilehash: 60a2a06e5b6f2ba72c0cf5c7997a20e5df88d7e6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062149"
---
# <a name="recordset-performing-a-join-odbc"></a>Набор записей. Объединение (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

## <a name="what-a-join-is"></a>Что соединение представляет собой

Операция объединения, обычной задачей доступа к данным, позволяет работать с данными более чем из одной таблицы, с помощью объекта одно подмножество записей. Соединения двух или более таблиц создается набор записей, который может содержать столбцы из каждой таблицы, но отображается в виде одной таблицы, чтобы приложения. Иногда объединяются все столбцы всех таблиц, но иногда SQL **ВЫБЕРИТЕ** предложение в соединении использует только некоторые столбцы из каждой таблицы. Классы баз данных поддерживают соединения только для чтения, но не поддерживают обновляемые объединения.

Для выбора записей, содержащих столбцы из соединенных таблиц, вам потребуется следующее:

- Список таблиц, содержащий имена всех соединяемых таблиц.

- Список столбцов, содержащий имена всех участвующих столбцов. Столбцы с одинаковым именем, но из разных таблиц, уточняются именем таблицы.

- Фильтр (SQL **ГДЕ** предложение), указывает столбцы, на которых производится соединение. Этот фильтр принимает форму «Table1.KeyCol = Table2.KeyCol» и фактически выполняет соединение.

Можно объединить более двух таблиц таким же образом путем приравнивания нескольких пар столбцов, каждая пара объединить с помощью ключевого слова SQL **AND**.

## <a name="see-also"></a>См. также

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Объявление класса для предопределенного запроса (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[Набор записей. Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Набор записей. Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)