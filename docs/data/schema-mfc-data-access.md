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
ms.openlocfilehash: 2dcfb5d22cf84fed7313686c943fbbd7c7ce1c84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512493"
---
# <a name="schema--mfc-data-access"></a>Схема (доступ к данным MFC)

Схема базы данных дает описание действующей структуры таблиц и представлений в базе данных. В общем случае код, созданный мастером, предполагает,  что схема для таблицы или таблиц, доступных по набору записей,не изменяется, но классы базы данных могут работать с определенными изменениями схемы, такие как добавление, переупорядочивание или удаление несвязанных столбцов. При изменении таблицы, необходимо вручную обновить набор записей для таблицы, а затем выполнить повторную компиляцию приложения.

Также можно дописать код, созданный мастером, для работы с базой данных, схема которой полностью не известна во время компиляции. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>См. также

[Доступ к данным, программирование (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Набор записей (ODBC)](../data/odbc/recordset-odbc.md)