---
title: Источник данных. Определение схемы источника данных (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: c419a3ac2d870e6a85675492ee6c9b726427a0e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395980"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>Источник данных. Определение схемы источника данных (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Чтобы задать элементы данных в вашей `CRecordset` объектов, вам нужно знать схемы источника данных, к которому вы подключаетесь. Определение схемы источника данных предполагает получение списка таблиц в источнике данных, список столбцов в каждой таблице, тип данных каждого столбца и наличия индексов.

## <a name="see-also"></a>См. также

[Источник данных (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Источник данных. Управление подключениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)