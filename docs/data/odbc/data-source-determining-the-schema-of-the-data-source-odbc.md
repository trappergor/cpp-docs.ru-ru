---
title: "Источник данных: Определение схемы источника данных (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fc425cf767db6939223288ebe74dcbc7fd4cf5b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Источник данных. Определение схемы источника данных (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Чтобы задать элементы данных в вашей `CRecordset` объектов, необходимо знать схему источника данных, к которому вы подключаетесь. Определение схемы источника данных предполагает получение списка таблиц в источнике данных, список столбцов в каждой таблице, тип данных каждого столбца и наличия индексов.  
  
## <a name="see-also"></a>См. также  
 [Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)