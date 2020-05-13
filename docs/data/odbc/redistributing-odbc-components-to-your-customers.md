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
ms.openlocfilehash: 0d4d3948add665c54be3d3b0596a7a6fc0e414f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212736"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Распространение компонентов ODBC среди клиентов

Если вы включили функциональные возможности программ администратора ODBC в приложение, необходимо также передать пользователям файлы, на которых выполняются эти программы. Эти файлы ODBC находятся в каталоге \Ос\систем визуального C++ компакт-диска. Файл Редистрб. Ври и лицензионное соглашение в одном каталоге содержат список файлов ODBC, которые можно распространять повторно.

Обратитесь к документации по любым драйверам ODBC, которые планируется поставлять. Необходимо определить, какие библиотеки DLL и другие файлы следует поставлять. Кроме того, следует ознакомиться [с распространением компонентов ODBC для клиентов](../../data/odbc/redistributing-odbc-components-to-your-customers.md), в которых объясняется, как распространять компоненты ODBC.

Кроме того, в большинстве случаев необходимо включить еще один файл. Odbccr32. dll — это библиотека курсоров ODBC. Эта библиотека предоставляет драйверам уровня 1 возможности прямой и обратной прокрутки. Он также предоставляет возможность поддержки моментальных снимков. Дополнительные сведения о библиотеке курсоров ODBC см. [в разделе ODBC: Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).

В следующих разделах приводятся дополнительные сведения об использовании ODBC с классами базы данных.

- [ODBC. Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC. Настройка источника данных ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC. Прямой вызов функций API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>См. также раздел

[Основы ODBC](../../data/odbc/odbc-basics.md)<br/>
[Администратор ODBC](../../data/odbc/odbc-administrator.md)
