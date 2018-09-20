---
title: локальный (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0b45106609c4bc93684e0d89737bb0753e36fb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421093"
---
# <a name="local-c"></a>local (C++)

При использовании в заголовке интерфейс позволяет использовать как генератор заголовка компилятора MIDL. При использовании в отдельной функции, обозначает локальной процедуры, для которого создаются без заглушек.

## <a name="syntax"></a>Синтаксис

```cpp
[local]
```

## <a name="remarks"></a>Примечания

**Локального** атрибут C++ имеет ту же функциональность, что [локального](/windows/desktop/Midl/local) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [call_as](../windows/call-as.md) пример демонстрирует использование **локального**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`dispinterface`|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты интерфейса](../windows/interface-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[call_as](../windows/call-as.md)  