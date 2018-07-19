---
title: Включение и отключение служб поставщика | Документы Microsoft
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
ms.openlocfilehash: ef36e35234aa4878e30e70748a5b2ba2975c38dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099736"
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>Включение и отключение служб поставщика
Отдельные службы OLE DB можно включить или отключить по умолчанию для всех приложений, обращающихся к одного поставщика. Это делается путем добавления **OLEDB_SERVICES** записи реестра при использовании поставщика с CLSID, с `DWORD` значение, указывающее службы, чтобы включить или отключить, как показано в следующей таблице.  
  
|Включены службы по умолчанию|Значение ключевого слова|  
|------------------------------|-------------------|  
|Все службы (по умолчанию)|0xFFFFFFFF|  
|Все, за исключением и автоматического зачисления|0xFFFFFFFE|  
|Все, кроме клиентских курсоров|0xfffffffb|  
|Все, кроме пулов автоматического зачисления и клиентских курсоров|0xfffffff0|  
|Нет служб|0x00000000|  
|Ни один агрегат все службы отключены|\<отсутствует ключ >|  
  
## <a name="see-also"></a>См. также  
 [Включение и отключение служб OLE DB](../../data/oledb/enabling-and-disabling-ole-db-services.md)