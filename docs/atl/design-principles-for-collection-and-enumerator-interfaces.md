---
title: "Разработка коллекции и интерфейсы перечислителя (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8709274e1b95816dee01b4457993521dde5d5213
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Принципы разработки для сбора и интерфейсы перечислителя
Существуют принципы другую структуру каждого типа интерфейса:  
  
-   Предоставляет интерфейс коллекции *случайных* доступ к *один* элементов в коллекции посредством **элемент** метод, он дает клиентам возможность обнаружения, количество элементов, содержащихся в коллекции через **число** свойство, и зачастую позволяет клиентам добавлять и удалять элементы.  
  
-   Предоставляет интерфейс перечислителя *последовательной* доступ к *несколько* элементов в коллекции, он не допускал клиента для обнаружения, количество элементов, содержащихся в коллекции (пока перечислитель перестанет возврат элементы), и он не предоставляет каким-либо образом, добавление или удаление элементов.  
  
 Каждый тип интерфейса играет другую роль в предоставлении доступа к элементам в коллекции.  
  
## <a name="see-also"></a>См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)

