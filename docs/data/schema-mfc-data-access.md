---
title: Схема (доступ к данным MFC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7ff1759203593cd556a91cbe17b93388488a2b07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091248"
---
# <a name="schema--mfc-data-access"></a>Схема (доступ к данным MFC)

Схема базы данных дает описание действующей структуры таблиц и представлений в базе данных. В общем случае код, созданный мастером, предполагает,  что схема для таблицы или таблиц, доступных по набору записей,не изменяется, но классы базы данных могут работать с определенными изменениями схемы, такие как добавление, переупорядочивание или удаление несвязанных столбцов. При изменении таблицы, необходимо вручную обновить набор записей для таблицы, а затем выполнить повторную компиляцию приложения.  
  
Также можно дописать код, созданный мастером, для работы с базой данных, схема которой полностью не известна во время компиляции. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## <a name="see-also"></a>См. также  

[Доступ к данным, программирование (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Набор записей (ODBC)](../data/odbc/recordset-odbc.md)