---
title: "Схема (доступ к данным MFC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7892d994c60e4434ee63cc26f7b1208c442088e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="schema--mfc-data-access"></a>Схема (доступ к данным MFC)
Схема базы данных дает описание действующей структуры таблиц и представлений в базе данных. В общем случае код, созданный мастером, предполагает,  что схема для таблицы или таблиц, доступных по набору записей,не изменяется, но классы базы данных могут работать с определенными изменениями схемы, такие как добавление, переупорядочивание или удаление несвязанных столбцов. При изменении таблицы, необходимо вручную обновить набор записей для таблицы, а затем выполнить повторную компиляцию приложения.  
  
 Также можно дописать код, созданный мастером, для работы с базой данных, схема которой полностью не известна во время компиляции. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [Доступ к данным программирования (MFC/ATL)](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [Набор записей (ODBC)](../data/odbc/recordset-odbc.md)