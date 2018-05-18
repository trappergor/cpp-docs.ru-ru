---
title: Создание простого поставщика только для чтения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2662a071f443967b921c4a8db27713bc7c3e8bb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения
При создании поставщика OLE DB, используя мастер проектов ATL и мастер поставщика ATL OLE DB, можно добавить другие функциональные возможности, которые требуется поддерживать. Запуск создания поставщика необходимо узнать, какие данные будут отправляться объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Для правильной разработки заранее ускорит реализации и тестирования.  
  
 Пример состоит из двух частей:  
  
-   В первой части показано как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.  
  
-   Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) путем добавления `IRowsetLocate` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)