---
title: Включение и отключение служб поставщика
ms.date: 07/30/2019
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: a74f8a8b099a30cf25007547e8059c77728435f9
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2019
ms.locfileid: "79544462"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Включение и отключение служб поставщика

Отдельные службы OLE DB могут быть включены или отключены по умолчанию для всех приложений, обращающихся к одному поставщику. Это можно сделать, добавив запись реестра OLEDB_SERVICES в CLSID поставщика, указав значение DWORD, указывающее службы для включения или отключения, как показано в следующей таблице.

|Службы по умолчанию включены|Значение DWORD|
|------------------------------|-------------------|
|Все службы, за исключением клиентских курсоров и пулов|0xfffffffa|
|Все службы, кроме клиентского курсора|0xfffffffb|
|Все службы, кроме пулов и автоматического прикрепления|0xfffffffc|
|Все службы, кроме пулов|0xfffffffe|
|Все службы (по умолчанию)|0xFFFFFFFF|
|Нет служб|0x00000000|
|Без агрегирования, все службы отключены|Нет OLEDB_Services записи реестра|

## <a name="see-also"></a>См. также:

[Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)
