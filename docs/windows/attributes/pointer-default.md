---
title: pointer_default (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e8ddf566082bfded1f20a2bfe04e7cef0b5dc14
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791112"
---
# <a name="pointerdefault"></a>pointer_default

Указывает атрибут указатель по умолчанию для всех указателей, за исключением верхнего уровня указателей, которые отображаются в списках параметров.

## <a name="syntax"></a>Синтаксис

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Значение, описывающее тип указателя: **ptr**, **ref**, или **уникальный**.

## <a name="remarks"></a>Примечания

**Pointer_default** атрибут C++ имеет ту же функциональность, что [pointer_default](/windows/desktop/Midl/pointer-default) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](defaultvalue.md) использовать образец **pointer_default**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)  