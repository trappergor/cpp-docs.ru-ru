---
title: "ODBC и MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 48dd657d4cf1b315b29fda881b949dea29204f24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-mfc"></a>ODBC и MFC
> [!NOTE]
>  Чтобы использовать классы баз данных MFC, необходимо иметь соответствующий драйвер ODBC для источника данных. Последние версии Microsoft ODBC driver for SQL Server — [Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=50420). Большинство поставщиков базы данных укажите драйвер ODBC для Windows. 
  
 В этом разделе Основные понятия классов баз данных на основе ODBC библиотеки Microsoft Foundation Classes (MFC) и общие сведения о работе этих классов. Дополнительные сведения об ODBC и MFC см. в следующих разделах:  
  
-   [Подключение к источнику данных](connecting-to-a-data-source.md)  
  
-   [Выбор и операции с записями](selecting-and-manipulating-records.md)  
  
-   [Отображение и обработка данных в форме](displaying-and-manipulating-data-in-a-form.md)  
  
-   [Работа с документами и представлениями](working-with-documents-and-views.md)  
  
-   [Доступ к ODBC и SQL](access-to-odbc-and-sql.md)  
  
-   [Дополнительные сведения о классах ODBC MFC](further-reading-about-the-mfc-odbc-classes.md)  
  
 Классы баз данных MFC на основе ODBC предназначены для предоставления доступа к любой базе данных, для которого доступен драйвера ODBC. Классы используют ODBC, приложение может обращаться к данным во многих различных форматов данных и различные конфигурации локальной или удаленной. Необходимо написать код особой обработки других СУБД (СУБД). При условии, что у пользователей есть соответствующий драйвер ODBC для данных, которые они хотят получить доступ, они могут использовать программы для работы с данными, хранящимися в таблицах.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ODBC](open-database-connectivity-odbc.md)