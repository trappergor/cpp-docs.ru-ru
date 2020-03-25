---
title: ODBC и MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 94a3455324a52b789bcfcf192b698a3c42b37c00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213197"
---
# <a name="odbc-and-mfc"></a>ODBC и MFC

> [!NOTE]
>  Для использования классов баз данных MFC необходимо иметь соответствующий драйвер ODBC для источника данных. Последним драйвером Microsoft ODBC для SQL Server является [драйвер Microsoft ODBC Driver 13 для SQL Server](https://www.microsoft.com/download/details.aspx?id=50420). Большинство поставщиков баз данных предоставляют драйвер ODBC для Windows.

В этом разделе рассматриваются основные понятия классов базы данных на основе ODBC библиотеки Microsoft Foundation Classes (MFC) и приводятся общие сведения о совместной работе классов. Дополнительные сведения о ODBC и MFC см. в следующих разделах:

- [Подключение к источнику данных](connecting-to-a-data-source.md)

- [Выбор и операции с записями](selecting-and-manipulating-records.md)

- [Отображение и обработка данных в форме](displaying-and-manipulating-data-in-a-form.md)

- [Работа с документами и представлениями](working-with-documents-and-views.md)

- [Доступ к ODBC и SQL](access-to-odbc-and-sql.md)

- [Дополнительные сведения о классах ODBC MFC](further-reading-about-the-mfc-odbc-classes.md)

Классы баз данных MFC на основе ODBC предназначены для предоставления доступа к любой базе данных, для которой доступен драйвер ODBC. Поскольку классы используют ODBC, приложение может обращаться к данным в различных форматах данных, а также в разных локальных и удаленных конфигурациях. Нет необходимости писать специальный код для работы с различными системами управления базами данных (СУБД). Если у пользователей есть соответствующий драйвер ODBC для данных, к которым они хотят получить доступ, они могут использовать программу для работы с данными в таблицах, хранящихся там.

## <a name="see-also"></a>См. также раздел

[Интерфейс ODBC](open-database-connectivity-odbc.md)
