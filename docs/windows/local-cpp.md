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
ms.openlocfilehash: a19e58e68b7f03269c002072859c2410a38c397b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597622"
---
# <a name="local-c"></a>local (C++)

При использовании в заголовке интерфейс позволяет использовать как генератор заголовка компилятора MIDL. При использовании в отдельной функции, обозначает локальной процедуры, для которого создаются без заглушек.

## <a name="syntax"></a>Синтаксис

```cpp
[local]
```

## <a name="remarks"></a>Примечания

**Локального** атрибут C++ имеет ту же функциональность, что [локального](http://msdn.microsoft.com/library/windows/desktop/aa367071) описании атрибута MIDL.

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

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[call_as](../windows/call-as.md)  