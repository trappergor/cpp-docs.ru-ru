---
title: Атрибут nonextensible | Документация Майкрософт
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
ms.openlocfilehash: 1112f533e2e38dd90b1693e8bd31e5896ebca5e7
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848441"
---
# <a name="nonextensible-attribute"></a>nonextensible-атрибут
Сдвоенный интерфейс не будут действовать во время выполнения (то есть не предоставляют методы или свойства с помощью `IDispatch::Invoke` , которые недоступны через таблице vtable), необходимо применить **nonextensible** атрибут в интерфейс Определение. Этот атрибут содержит сведения для клиентских языков (например, Visual Basic), которые могут использоваться для включения проверки полный код во время компиляции. Если этот атрибут не задан, ошибки могут оставаться скрытым в клиентском коде до времени выполнения.  
  
 Дополнительные сведения о **nonextensible** атрибут и пример, см. в разделе [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

