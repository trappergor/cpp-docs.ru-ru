---
title: Создание простого поставщика только для чтения | Документация Майкрософт
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
ms.openlocfilehash: 9f951fba45b23b7e4dde92fc11f2faabb53bd43d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101570"
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения

При создании поставщика OLE DB, используя мастер проектов ATL и мастер поставщика ATL OLE DB, можно добавить другие функциональные возможности, которые должны поддерживаться. Начните разработку вашего поставщика с помощью проверки какие данные будут отправляться объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Качественная разработка поставщика будет быструю реализацию и тестирование.  
  
Пример состоит из двух частей:  
  
- В первой части показан как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.  
  
- Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) , добавив `IRowsetLocate` интерфейс.  
  
## <a name="see-also"></a>См. также  

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)