---
title: Local (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.local
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
ms.openlocfilehash: 853331ce191f8fe41d5967d2d625a3dac8543a4d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514412"
---
# <a name="local-c"></a>local (C++)

При использовании в заголовке интерфейса позволяет использовать компилятор MIDL в качестве генератора заголовков. При использовании в отдельной функции обозначает локальную процедуру, для которой заглушки не создаются.

## <a name="syntax"></a>Синтаксис

```cpp
[local]
```

## <a name="remarks"></a>Примечания

**Локальный** C++ атрибут имеет те же функциональные возможности, что и [локальный](/windows/win32/Midl/local) атрибут MIDL.

## <a name="example"></a>Пример

Пример использования **локального**объекта см. в разделе [call_as](call-as.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|`dispinterface`|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[call_as](call-as.md)