---
title: рекуестедит (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requestedit
helpviewer_keywords:
- requestedit attribute
ms.assetid: b3c24790-3c4a-4646-8722-03d7b51172ee
ms.openlocfilehash: ec9e516157f2b6ea2a64875f30d2b03412c6eb46
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214569"
---
# <a name="requestedit"></a>requestedit

Указывает, что свойство поддерживает уведомление `OnRequestEdit`.

## <a name="syntax"></a>Синтаксис

```cpp
[requestedit]
```

## <a name="remarks"></a>Remarks

Атрибут **рекуестедит** C++ имеет те же функциональные возможности, что и атрибут [рекуестедит](/windows/win32/Midl/requestedit) MIDL.

## <a name="example"></a>Пример

Пример использования **рекуестедит**см. в примере для [привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)
