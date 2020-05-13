---
title: усесжетластеррор (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: f58929db01a1710e811a973c0559ad29b242b4eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166137"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Сообщает вызывающему, что при возникновении ошибки при вызове этой функции вызывающий объект может вызвать `GetLastError`, чтобы получить код ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Remarks

Атрибут **усесжетластеррор** C++ имеет те же функциональные возможности, что и атрибут [усесжетластеррор](/windows/win32/Midl/usesgetlasterror) MIDL.

## <a name="example"></a>Пример

Пример использования **усесжетластеррор**см. в примере [idl_module](idl-module.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|атрибут **module**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)
