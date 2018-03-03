---
title: "nonextensible-атрибут | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af16748bb3b2048ce854ccc7a03b2400039184a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nonextensible-attribute"></a>nonextensible-атрибут
Сдвоенный интерфейс не будет распространяться во время выполнения (то есть не предоставляют методы или свойства с помощью **IDispatch::Invoke** , которые недоступны через таблице vtable), его следует применять **nonextensible** атрибут в определении интерфейса. Этот атрибут содержит сведения для клиентских языков (например, Visual Basic), которые можно использовать для включения проверки весь код во время компиляции. Если этот атрибут не задан, ошибки могут оставаться скрытым в коде клиента до времени выполнения.  
  
 Дополнительные сведения о **nonextensible** атрибут и пример см. в разделе [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

