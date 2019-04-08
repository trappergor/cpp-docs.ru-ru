---
title: PTR (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: 2c712a2d9c85e0fe8fd8c4dbad5c7f48812ab1a2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030132"
---
# <a name="ptr"></a>ptr

Определяет указатель как полный указатель.

## <a name="syntax"></a>Синтаксис

```cpp
[ptr]
```

## <a name="remarks"></a>Примечания

**Ptr** атрибут C++ имеет ту же функциональность, что [ptr](/windows/desktop/Midl/ptr) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](defaultvalue.md) использовать образец **ptr**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса **typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)