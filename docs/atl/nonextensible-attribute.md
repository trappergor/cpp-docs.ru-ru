---
title: нерасширяемый атрибут
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: fda2a0d43144b6e9832e061e7198b3f3e65f8b86
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500113"
---
# <a name="nonextensible-attribute"></a>нерасширяемый атрибут

Если сдвоенный интерфейс не будет расширяться во время выполнения (то есть вы не будете предоставлять методы или свойства через `IDispatch::Invoke` , которые недоступны через таблицу vtable), следует применить **нерасширяемый** атрибут к определению интерфейса. Этот атрибут предоставляет сведения для клиентских языков (например, Visual Basic), которые можно использовать для включения полной проверки кода во время компиляции. Если этот атрибут не указан, ошибки могут остаться скрытыми в коде клиента до времени выполнения.

Дополнительные сведения о **нерасширяемых** атрибутах и примерах см. в разделе [нерасширяемость](../windows/attributes/nonextensible.md).

## <a name="see-also"></a>См. также раздел

[Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)
