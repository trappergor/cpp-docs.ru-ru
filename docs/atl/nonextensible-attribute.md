---
title: nonextensible-атрибут
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: cc57acb8bd7bc3e32c764606da651f57316ceabf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811853"
---
# <a name="nonextensible-attribute"></a>nonextensible-атрибут

Сдвоенный интерфейс не будут действовать во время выполнения (то есть не предоставляют методы или свойства с помощью `IDispatch::Invoke` , которые недоступны через таблице vtable), необходимо применить **nonextensible** атрибут в интерфейс Определение. Этот атрибут содержит сведения для клиентских языков (например, Visual Basic), которые могут использоваться для включения проверки полный код во время компиляции. Если этот атрибут не задан, ошибки могут оставаться скрытым в клиентском коде до времени выполнения.

Дополнительные сведения о **nonextensible** атрибут и пример, см. в разделе [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>См. также

[Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)
