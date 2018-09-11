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
ms.openlocfilehash: b910ce2416dc345e2a36c9858f260ef5b42c2cc8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203326"
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

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[call_as](../windows/call-as.md)  