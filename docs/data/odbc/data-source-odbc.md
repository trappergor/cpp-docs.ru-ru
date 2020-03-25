---
title: Источник данных (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: ed9eeb8f5ef0d53846761062cf2c6575d2eaf9e6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213308"
---
# <a name="data-source-odbc"></a>Источник данных (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

В терминах базы данных источником данных является конкретный набор данных, информация, необходимая для доступа к этим данным, и расположение источника данных, которое можно описать с помощью имени источника данных. Для работы с классом [CDatabase](../../mfc/reference/cdatabase-class.md)источник данных должен быть настроен с помощью администратора ODBC. Примеры источников данных включают удаленную базу данных, работающую на Microsoft SQL Server по сети или в файле Microsoft Access в локальном каталоге. Из приложения можно получить доступ к любому источнику данных, для которого имеется драйвер ODBC.

В приложении одновременно может быть активным один или несколько источников данных, каждый из которых представлен объектом `CDatabase`. Кроме того, можно иметь несколько одновременных подключений к любому источнику данных. Вы можете подключиться к удаленному и локальному источникам данных в зависимости от установленных драйверов и возможностей драйверов ODBC. Дополнительные сведения об источниках данных и администраторах ODBC см. в разделе [Администратор](../../data/odbc/odbc-administrator.md) [ODBC и](../../data/odbc/odbc-basics.md) ODBC.

Следующие разделы содержат дополнительные сведения об источниках данных.

- [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>См. также раздел

[Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)
