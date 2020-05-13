---
title: ODBC и классы баз данных
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 6511aab9bb048882fe9c3398dd17f769eb16220c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320067"
---
# <a name="odbc-and-the-database-classes"></a>ODBC и классы баз данных

Классы баз данных MFC ODBC инкапсулируют функцию функции ODBC API, которые обычно делают сами в функциях членов классов [CDatabase](../../mfc/reference/cdatabase-class.md) и [CRecordset.](../../mfc/reference/crecordset-class.md) Например, сложные последовательности вызовов ODBC, привязка возвращенных записей к местам хранения, обработка условий ошибок и другие операции управляются для вас классами баз данных. В результате используется значительно более простой классовый интерфейс для управления записями через объект записи.

> [!NOTE]
> Источники данных ODBC доступны через классы MFC ODBC, как описано в этой теме, или через классы MFC Data Access Object (DAO).

Хотя классы баз данных инкапсулируют функциональность ODBC, они не обеспечивают единого отображения функций ODBC API. Классы баз данных обеспечивают более высокий уровень абстракции, смоделированный по объектам доступа к данным, найденным в Microsoft Access и Microsoft Visual Basic. Для получения дополнительной информации [см.](../../data/odbc/odbc-and-mfc.md)

## <a name="see-also"></a>См. также раздел

[Основы ODBC](../../data/odbc/odbc-basics.md)
