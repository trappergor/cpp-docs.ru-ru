---
title: Включение и отключение служб поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
ms.openlocfilehash: d91f08accf1a8be69f63d6bbcaa4c620d68c1077
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033035"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Включение и отключение служб поставщика

Отдельные службы OLE DB можно включить или отключить по умолчанию для всех приложений, которые обращаются к одним поставщиком. Это делается путем добавления OLEDB_SERVICES запись реестра в разделе CLSID поставщика с значение DWORD, указывающее служб, чтобы включить или отключить, как показано в следующей таблице.

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