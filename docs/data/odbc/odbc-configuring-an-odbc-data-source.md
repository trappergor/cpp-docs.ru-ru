---
title: 'ODBC: Настройка источника данных ODBC | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9a0cd385596f62432f16b7e5abc4259a267dd76
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080316"
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC. Настройка источника данных ODBC

Чтобы использовать [источника данных](../../data/odbc/data-source-odbc.md) с приложением, вы разработали, необходимо использовать администратор ODBC для ее настройки. Администратор ODBC следит за доступные источники данных и данные о соединении в реестре Windows. Используйте администратор ODBC для добавления, изменения и удаления источников данных в **источников данных** диалоговое окно, а также добавление и удаление драйверов ODBC.

> [!NOTE]
>  Эти сведения применимы при использовании классов MFC объекта доступа к данным (DAO) для доступа к ODBC и при использовании классам ODBC библиотеки MFC.

Администратор ODBC устанавливается автоматически вместе с поддержкой базы данных библиотеки Microsoft Foundation Classes (MFC). Дополнительные сведения о программе администратора ODBC, см. в разделе [администратор ODBC](../../data/odbc/odbc-administrator.md) и интерактивной системы справки по Справочник по API ODBC.

Сведения о способах написания программ установки и администрирования ODBC для приложений баз данных MFC[см](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).

## <a name="see-also"></a>См. также

[Основы ODBC](../../data/odbc/odbc-basics.md)<br/>
[ODBC. Прямой вызов функций API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)