---
title: Схема (доступ к данным MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
ms.openlocfilehash: 0eac4f47c3d00c34c1aadaef18202a95f831ad82
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209097"
---
# <a name="schema--mfc-data-access"></a>Схема (доступ к данным MFC)

Схема базы данных дает описание действующей структуры таблиц и представлений в базе данных. В общем случае код, созданный мастером, предполагает,  что схема для таблицы или таблиц, доступных по набору записей,не изменяется, но классы базы данных могут работать с определенными изменениями схемы, такие как добавление, переупорядочивание или удаление несвязанных столбцов. При изменении таблицы, необходимо вручную обновить набор записей для таблицы, а затем выполнить повторную компиляцию приложения.

Также можно дописать код, созданный мастером, для работы с базой данных, схема которой полностью не известна во время компиляции. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>См. также раздел

[Программирование доступа к данным (библиотеки MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Набор записей (ODBC)](../data/odbc/recordset-odbc.md)
