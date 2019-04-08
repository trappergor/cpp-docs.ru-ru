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
ms.openlocfilehash: 9b7d04e2eb8bbb1adf96e05282861ef33e20434a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031184"
---
# <a name="odbc-and-mfc"></a>ODBC и MFC

> [!NOTE]
>  Чтобы использовать классы баз данных MFC, необходимо иметь соответствующий драйвер ODBC для источника данных. Последние версии Microsoft ODBC driver для SQL Server является [Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/download/details.aspx?id=50420). Большинство поставщиков базы данных предоставляют драйвер ODBC для Windows.

В этом разделе, основные понятия баз данных на основе ODBC классы библиотеки Microsoft Foundation Classes (MFC) и общие сведения о работе этих классов. Дополнительные сведения об ODBC и MFC см. в разделах:

- [Подключение к источнику данных](connecting-to-a-data-source.md)

- [Выбор и операции с записями](selecting-and-manipulating-records.md)

- [Отображение и обработка данных в форме](displaying-and-manipulating-data-in-a-form.md)

- [Работа с документами и представлениями](working-with-documents-and-views.md)

- [Доступ к ODBC и SQL](access-to-odbc-and-sql.md)

- [Дополнительные сведения о классах ODBC MFC](further-reading-about-the-mfc-odbc-classes.md)

Классы баз данных MFC на основе ODBC предназначены для предоставления доступа к любой базе данных, для которого доступен драйвер ODBC. Поскольку классы используют ODBC, приложения могут получать к ним множество различных форматов данных и различные конфигурации локальной или удаленной. Необходимо написать код особой обработки систем управления другой базе данных (СУБД). До тех пор, пока у пользователей есть соответствующий драйвер ODBC для данных, которые требуется сделать доступными, их можно использовать программы для работы с данными, хранящимися в таблицах.

## <a name="see-also"></a>См. также

[Интерфейс ODBC (ODBC)](open-database-connectivity-odbc.md)