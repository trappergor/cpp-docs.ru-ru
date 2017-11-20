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
ms.openlocfilehash: 54a596ce7821d89096836a0edbaf810d6c3f4a2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Источник данных. Определение схемы источника данных (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Чтобы задать элементы данных в вашей `CRecordset` объектов, необходимо знать схему источника данных, к которому вы подключаетесь. Определение схемы источника данных предполагает получение списка таблиц в источнике данных, список столбцов в каждой таблице, тип данных каждого столбца и наличия индексов.  
  
## <a name="see-also"></a>См. также  
 [Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)