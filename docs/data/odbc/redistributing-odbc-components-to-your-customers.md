---
title: Распространение компонентов ODBC среди клиентов
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: 1a6ec6f5fdd3c32080d357ca58d31ccea271b7a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330080"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Распространение компонентов ODBC среди клиентов

Если включить возможности программ администратора ODBC в приложение, необходимо также передать пользователям файлы, которые этих программ. Эти файлы ODBC находятся в каталоге \OS\System компакт-диска Visual C++. Файл Redistrb.wri и лицензионное соглашение, в том же каталоге содержат список файлов ODBC, которые можно распространить повторно.

См. в документации по всем драйверам ODBC, которые планируется поставлять. Необходимо определить, какие библиотеки DLL и другие файлы для отправки. Стоит также прочесть [распространение компонентов ODBC среди клиентов](../../data/odbc/redistributing-odbc-components-to-your-customers.md), который описывается распространение компонентов ODBC.

Кроме того необходимо включить еще один файл в большинстве случаев. Odbccr32.dll является библиотека курсоров ODBC. Эта библиотека предоставляет драйверам первого уровня возможность прямой и обратной прокрутки. Он также предоставляет возможность поддержки моментальные снимки. Дополнительные сведения о библиотеку курсоров ODBC, см. в разделе [ODBC: Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).

Дополнительные сведения об использовании ODBC и классы баз данных в следующих разделах.

- [ODBC. Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC. Настройка источника данных ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC. Прямой вызов функций ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>См. также

[Основы ODBC](../../data/odbc/odbc-basics.md)<br/>
[Администратор ODBC](../../data/odbc/odbc-administrator.md)