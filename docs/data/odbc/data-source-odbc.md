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
ms.openlocfilehash: b435c65bab565e109d37e1dd24e051993cbb30c8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038399"
---
# <a name="data-source-odbc"></a>Источник данных (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

В терминах баз данных источник данных имеет определенный набор данных, сведения, необходимые для доступа к этим данным, а также расположение источника данных, которые можно описать с помощью имени источника данных. Для работы с классом [CDatabase](../../mfc/reference/cdatabase-class.md), источник данных должен быть настроен с помощью администратора Open Database Connectivity (ODBC). Примерами источников данных являются удаленной базе данных, запущенной на сервере Microsoft SQL Server через сеть или файл Microsoft Access в локальном каталоге. Из своего приложения можно получить доступ к любому источнику данных, для которого у вас есть драйвер ODBC.

Имеется один или несколько источников данных, активных в приложении за один раз, каждый из которых представлен `CDatabase` объекта. Также может иметь несколько одновременных подключений к любому источнику данных. Можно соединиться с удаленным и для локальных источников данных, в зависимости от установленных драйверов и возможности драйверов ODBC. Дополнительные сведения об источниках данных и администратор ODBC см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [администратор ODBC](../../data/odbc/odbc-administrator.md).

В следующих разделах более об источниках данных:

- [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>См. также

[Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)