---
title: Конструирование коллекции и интерфейсы перечислителя (ATL) | Документация Майкрософт
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
ms.openlocfilehash: ab8b42804ca892c80971928b869e09ccdf479d68
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851331"
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Принципы проектирования для сбора и интерфейсы перечислителя
Существуют принципы проектирования каждого типа интерфейса.  
  
-   Предоставляет интерфейс коллекции *случайных* доступ к *единый* элемента в коллекции с помощью `Item` метод, он дает клиентам возможность выяснить, сколько элементов в коллекции с помощью `Count` свойство, и часто позволяет клиентам добавлять и удалять элементы.  
  
-   Предоставляет интерфейс перечислителя *последовательной* доступ к *несколько* элементов в коллекции, он не позволяет клиенту определять, сколько элементов находятся в коллекции (пока перечислитель останавливает возврат элементы), и он не предоставляет никакого способа добавления или удаления элементов.  
  
 Каждый тип интерфейса играет другую роль в предоставлении доступа к элементам в коллекции.  
  
## <a name="see-also"></a>См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)

