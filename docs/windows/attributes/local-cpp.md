---
title: Local (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: d3710eee748a43a1daa5c07d8b3feb6beb8f64fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214751"
---
# <a name="local-c"></a>local (C++)

При использовании в заголовке интерфейса позволяет использовать компилятор MIDL в качестве генератора заголовков. При использовании в отдельной функции обозначает локальную процедуру, для которой заглушки не создаются.

## <a name="syntax"></a>Синтаксис

```cpp
[local]
```

## <a name="remarks"></a>Remarks

**Локальный** C++ атрибут имеет те же функциональные возможности, что и [локальный](/windows/win32/Midl/local) атрибут MIDL.

## <a name="example"></a>Пример

Пример использования **локального**объекта см. в разделе [call_as](call-as.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|`dispinterface`|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[call_as](call-as.md)
