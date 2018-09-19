---
title: Источник данных (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6ad24a7be5c46c8019b22629003306ea99c56fd3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106977"
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