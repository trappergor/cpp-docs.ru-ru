---
title: usesgetlasterror (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: 9f050bbf69edf1ab8327a283299cb5e687ce5380
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032210"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Вызывающий объект о том, есть ли ошибки при вызове этой функции, затем вызывающий объект затем можно вызвать `GetLastError` для получения кода ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Примечания

**Usesgetlasterror** атрибут C++ имеет ту же функциональность, что [usesgetlasterror](/windows/desktop/Midl/usesgetlasterror) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [idl_module](idl-module.md) примере образец демонстрирует использование **usesgetlasterror**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**модуль** атрибут|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)