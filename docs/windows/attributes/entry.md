---
title: запись (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: b6c34a603f3ba8abaf070759a22ddf2b8e9c2106
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663259"
---
# <a name="entry"></a>entry

Указывает экспортированной функции или константы в модуле, определяя точки входа в библиотеку DLL.

## <a name="syntax"></a>Синтаксис

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Параметры

*id*<br/>
Идентификатор точки входа.

## <a name="remarks"></a>Примечания

**Запись** атрибут C++ имеет ту же функциональность, что [запись](/windows/desktop/Midl/entry) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [idl_module](idl-module.md) для пример использования **запись**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Атрибут `idl_module`|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)