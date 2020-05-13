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
ms.openlocfilehash: 38a625c73a17ecae4d8adc61e8c56bc4bdda67f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320073"
---
# <a name="odbc-and-mfc"></a>ODBC и MFC

> [!NOTE]
> Чтобы использовать классы баз данных MFC, необходимо иметь соответствующий драйвер ODBC для вашего источника данных. Последним драйвером Microsoft ODBC для сервера S'L — Это [Microsoft ODBC Driver 13 для сервера S'L.](https://www.microsoft.com/download/details.aspx?id=50420) Большинство поставщиков баз данных предоставляют драйвер ODBC для Windows.

Эта тема представляет основные концепции классов баз данных библиотеки Microsoft Foundation Classes (MFC) и содержит обзор совместной работы классов. Для получения дополнительной информации о ODBC и MFC, см.

- [Подключение к источнику данных](connecting-to-a-data-source.md)

- [Выбор и манипулирование записями](selecting-and-manipulating-records.md)

- [Отображение и манипулирование данными в форме](displaying-and-manipulating-data-in-a-form.md)

- [Работа с документами и представлениями](working-with-documents-and-views.md)

- [Доступ к ODBC и SQL](access-to-odbc-and-sql.md)

- [Далее в рубрике О классах МФЦ ODBC](further-reading-about-the-mfc-odbc-classes.md)

Классы баз данных MFC, основанные на ODBC, предназначены для обеспечения доступа к любой базе данных, для которой доступен драйвер ODBC. Поскольку классы используют ODBC, приложение может получить доступ к данным в различных форматах данных и различных локальных/удаленных конфигурациях. Вам не нужно писать специальный код для обработки различных систем управления базами данных (DBMSs). До тех пор, пока у пользователей есть соответствующий драйвер ODBC для данных, к которым они хотят получить доступ, они могут использовать вашу программу для управления данными в таблицах, хранящихся там.

## <a name="see-also"></a>См. также раздел

[Открытая связь с базами данных (ODBC)](open-database-connectivity-odbc.md)
