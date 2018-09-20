---
title: immediatebind | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.immediatebind
dev_langs:
- C++
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc4c42132b2b964d0606fc3287e9d9fd98d64370
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400746"
---
# <a name="immediatebind"></a>immediatebind

Указывает, что базы данных будет немедленно оповещаться обо всех изменений свойства объекта привязки данных.

## <a name="syntax"></a>Синтаксис

```cpp
[immediatebind]
```

## <a name="remarks"></a>Примечания

**Immediatebind** атрибут C++ имеет ту же функциональность, что [immediatebind](/windows/desktop/Midl/immediatebind) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [bindable](../windows/bindable.md) пример демонстрирует использование **immediatebind**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[defaultbind](../windows/defaultbind.md)<br/>
[displaybind](../windows/displaybind.md)<br/>
[requestedit](../windows/requestedit.md)  