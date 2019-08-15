---
title: запись (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 71abf4f183255fa137b43ac9cabd88d15c3fc85d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490901"
---
# <a name="entry"></a>entry

Указывает экспортированную функцию или константу в модуле, определяя точку входа в библиотеке DLL.

## <a name="syntax"></a>Синтаксис

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Параметры

*id*<br/>
Идентификатор точки входа.

## <a name="remarks"></a>Примечания

Атрибут **entry** C++ имеет те же функциональные возможности, что и атрибут MIDL [элемента](/windows/win32/Midl/entry) .

## <a name="example"></a>Пример

Пример использования **записи**см. в примере для [idl_module](idl-module.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|`idl_module`версию|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)