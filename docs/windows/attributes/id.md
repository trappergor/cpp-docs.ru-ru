---
title: ID (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 79e49b2c074cd82323c74489e33812c10c442c61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168061"
---
# <a name="id"></a>идентификатор

Задает параметр *DISPID* для функции-члена (свойства или метода в интерфейсе или DISP).

## <a name="syntax"></a>Синтаксис

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации для метода интерфейса.

## <a name="remarks"></a>Remarks

Атрибут **ID** C++ имеет те же функциональные возможности, что и атрибут [ID](/windows/win32/Midl/id) MIDL.

## <a name="example"></a>Пример

Пример использования **идентификатора**см. в примере для [привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[В поле](in-cpp.md)<br/>
[out](out-cpp.md)
