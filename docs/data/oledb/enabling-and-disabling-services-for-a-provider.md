---
title: Включение и отключение служб поставщика
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: ca621b005dd0bad60c70298e4d49abce6fb8d1d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665456"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Включение и отключение служб поставщика

Отдельные службы OLE DB можно включить или отключить по умолчанию для всех приложений, которые обращаются к одним поставщиком. Это делается путем добавления OLEDB_SERVICES запись реестра в разделе CLSID поставщика с `DWORD` значение, указывающее службы, чтобы включить или отключить, как показано в следующей таблице.

|Службы по умолчанию включен|Значение ключевого слова|
|------------------------------|-------------------|
|Все службы (по умолчанию)|0xFFFFFFFF|
|Все, за исключением и автоматического зачисления|0xFFFFFFFE|
|Все, кроме клиентский курсор|0xfffffffb|
|Все, кроме пулов, автоматического зачисления и клиентских курсоров|0xfffffff0|
|Нет служб|0x00000000|
|Ни один агрегат, все службы отключены|\<отсутствует ключ >|

## <a name="see-also"></a>См. также

[Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)