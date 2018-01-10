---
title: "Включение и отключение служб поставщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc6b3d7cc8e80eaa24c2e2dd9b4e23e79dfb09f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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