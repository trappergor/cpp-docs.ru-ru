---
title: nonextensible-атрибут | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40b4b79701862ca07e704aca098419479923ef1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="nonextensible-attribute"></a>nonextensible-атрибут
Сдвоенный интерфейс не будет распространяться во время выполнения (то есть не предоставляют методы или свойства с помощью **IDispatch::Invoke** , которые недоступны через таблице vtable), его следует применять **nonextensible** атрибут в определении интерфейса. Этот атрибут содержит сведения для клиентских языков (например, Visual Basic), которые можно использовать для включения проверки весь код во время компиляции. Если этот атрибут не задан, ошибки могут оставаться скрытым в коде клиента до времени выполнения.  
  
 Дополнительные сведения о **nonextensible** атрибут и пример см. в разделе [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

