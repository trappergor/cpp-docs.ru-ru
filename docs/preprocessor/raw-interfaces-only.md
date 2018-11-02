---
title: raw_interfaces_only
ms.date: 11/04/2016
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: c07401036261b9f93bb2c07dcf3aff1ecf72e2fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519357"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**Конкретных C++**

Отключает создание функций оболочки обработки ошибок и [свойство](../cpp/property-cpp.md) объявления, в которых используются такие функции оболочки.

## <a name="syntax"></a>Синтаксис

```
raw_interfaces_only
```

## <a name="remarks"></a>Примечания

**Raw_interfaces_only** атрибут приводит также к префикс по умолчанию, используемое для именования удалены функции, не являющийся свойством. Как правило, используется префикс **raw_**. Если этот атрибут задан, имена функций берутся непосредственно из библиотеки типов.

Этот атрибут позволяет предоставлять только низкоуровневое содержимое библиотеки типов.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)