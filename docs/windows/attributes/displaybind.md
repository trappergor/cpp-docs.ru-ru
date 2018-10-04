---
title: displaybind (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.displaybind
dev_langs:
- C++
helpviewer_keywords:
- displaybind attribute
ms.assetid: b3d70396-78e4-43d9-9583-16ddb8c9bb1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc4b017a225a17011a832007ac875e3495ea5f48
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791089"
---
# <a name="displaybind"></a>displaybind

Указывает свойство, которое должно отображаться пользователю как связываемая.

## <a name="syntax"></a>Синтаксис

```cpp
[displaybind]
```

## <a name="remarks"></a>Примечания

**Displaybind** атрибут C++ имеет ту же функциональность, что [displaybind](/windows/desktop/Midl/displaybind) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) пример демонстрирует использование **displaybind**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)  