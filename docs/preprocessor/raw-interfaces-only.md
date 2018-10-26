---
title: raw_interfaces_only | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 789c9179b2ba48f5c3796f709931728bc756aaaa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075038"
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