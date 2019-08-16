---
title: усесжетластеррор (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: b14316bd929f4b41b13a76c41e94b31b7534e9d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513891"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Сообщает вызывающему, что при возникновении ошибки при вызове этой функции вызывающий объект может вызвать метод `GetLastError` , чтобы получить код ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Примечания

Атрибут **усесжетластеррор** C++ имеет те же функциональные возможности, что и атрибут [усесжетластеррор](/windows/win32/Midl/usesgetlasterror) MIDL.

## <a name="example"></a>Пример

Пример использования **усесжетластеррор**см. в примере [idl_module](idl-module.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|атрибут **module**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)