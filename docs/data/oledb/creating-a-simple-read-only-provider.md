---
title: "Создание простого поставщика только для чтения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 67ffacffde8dc13e49a09358efcafefd751619ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения
При создании поставщика OLE DB, используя мастер проектов ATL и мастер поставщика ATL OLE DB, можно добавить другие функциональные возможности, которые требуется поддерживать. Запуск создания поставщика необходимо узнать, какие данные будут отправляться объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Для правильной разработки заранее ускорит реализации и тестирования.  
  
 Пример состоит из двух частей:  
  
-   В первой части показано как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.  
  
-   Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) путем добавления `IRowsetLocate` интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)