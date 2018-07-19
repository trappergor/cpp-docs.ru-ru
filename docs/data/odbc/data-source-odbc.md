---
title: Источник данных (ODBC) | Документы Microsoft
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
ms.openlocfilehash: 842a8bf3faadcf96b4f44441e45dc94d5679f9f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087878"
---
# <a name="data-source-odbc"></a>Источник данных (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 В терминах баз данных источник данных представляет собой определенный набор данных, сведения, необходимые для доступа к ним и расположение источника данных, которое можно описать с помощью имени источника данных. Для работы с классом [CDatabase](../../mfc/reference/cdatabase-class.md), источник данных должен быть настроен с помощью администратора Open Database Connectivity (ODBC). Примерами источников данных являются к удаленной базе данных на Microsoft SQL Server через сеть или файл Microsoft Access в локальном каталоге. Из своего приложения можно получить доступ к любому источнику данных, для которой имеется драйвер ODBC.  
  
 Имеется один или несколько источников данных, активных в приложении за один раз, каждый из которых представлен `CDatabase` объекта. Также можно иметь несколько одновременных подключений к любому источнику данных. Можно подключиться к удаленным и с локальным источником данных, в зависимости от установленных драйверов и возможности драйверов ODBC. Дополнительные сведения об источниках данных и администраторе ODBC см. в разделе [ODBC](../../data/odbc/odbc-basics.md) и [администратор ODBC](../../data/odbc/odbc-administrator.md).  
  
 В следующих разделах описаны более источники данных:  
  
-   [Источник данных. Управление соединениями (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)  
  
-   [Источник данных. Определение схемы источника данных (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)