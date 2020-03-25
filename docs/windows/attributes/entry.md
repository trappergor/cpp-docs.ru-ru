---
title: запись (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 9bdfc64506f26ee4e9876920821883a0fa12bc7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167099"
---
# <a name="entry"></a>entry

Указывает экспортированную функцию или константу в модуле, определяя точку входа в библиотеке DLL.

## <a name="syntax"></a>Синтаксис

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
Идентификатор точки входа.

## <a name="remarks"></a>Remarks

Атрибут **entry** C++ имеет те же функциональные возможности, что и атрибут MIDL [элемента](/windows/win32/Midl/entry) .

## <a name="example"></a>Пример

Пример использования **записи**см. в примере для [idl_module](idl-module.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Атрибут `idl_module`|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)
