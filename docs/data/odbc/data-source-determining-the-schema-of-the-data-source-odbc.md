---
title: Источник данных. Определение схемы источника данных (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: ed6500c5718cf90b39600b12659a3090fe9532ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580789"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Источник данных. Определение схемы источника данных (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Чтобы задать элементы данных в вашей `CRecordset` объектов, вам нужно знать схемы источника данных, к которому вы подключаетесь. Определение схемы источника данных предполагает получение списка таблиц в источнике данных, список столбцов в каждой таблице, тип данных каждого столбца и наличия индексов.

## <a name="see-also"></a>См. также

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)