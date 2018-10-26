---
title: Включение и отключение служб поставщика | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c9b255e715a635494e3acc34124871e90ceca8f7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055376"
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