---
title: Разработка коллекции и интерфейсы перечислителя (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05649cce0e80af6f54327545cef7b663d69babf9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354923"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Принципы разработки для сбора и интерфейсы перечислителя
Существуют принципы другую структуру каждого типа интерфейса:  
  
-   Предоставляет интерфейс коллекции *случайных* доступ к *один* элементов в коллекции посредством **элемент** метод, он дает клиентам возможность обнаружения, количество элементов, содержащихся в коллекции через **число** свойство, и зачастую позволяет клиентам добавлять и удалять элементы.  
  
-   Предоставляет интерфейс перечислителя *последовательной* доступ к *несколько* элементов в коллекции, он не допускал клиента для обнаружения, количество элементов, содержащихся в коллекции (пока перечислитель перестанет возврат элементы), и он не предоставляет каким-либо образом, добавление или удаление элементов.  
  
 Каждый тип интерфейса играет другую роль в предоставлении доступа к элементам в коллекции.  
  
## <a name="see-also"></a>См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)

