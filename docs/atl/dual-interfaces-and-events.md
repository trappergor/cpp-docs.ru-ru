---
title: "Сдвоенные интерфейсы и события | Документы Microsoft"
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
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 87774f0237eb42c4bd2f97185230b3c869688ca8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dual-interfaces-and-events"></a>Сдвоенные интерфейсы и события
Хотя можно создать интерфейс события как гигабитных, существует ряд причин для правильной разработки не делать. Фундаментальные причина заключается в том, что источник события только запустит событие виртуальной таблице или с помощью `Invoke`, но не оба. Если источник события запускает событие как вызов метода vtable прямой `IDispatch` методы никогда не будет использоваться и очевидно, что интерфейс должно было интерфейс чисто vtable. Если источник событий событие как вызов `Invoke`, не будут использоваться методы vtable и представляет очистки, что интерфейс должно было диспетчерский интерфейс. При указании интерфейсов событий как duals будет требование клиентам реализовать интерфейс, который никогда не будет использоваться.  
  
> [!NOTE]
>  Этот аргумент не применяется к сдвоенные интерфейсы в целом. С точки зрения реализации duals — это быстрый, удобный и хорошо поддерживается способ реализации интерфейсов, которые доступны для широкого диапазона клиентов.  
  
 Дальнейшей существует причин, чтобы избежать двух событий интерфейсов; Internet Explorer, ни Visual Basic поддерживают их.  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

