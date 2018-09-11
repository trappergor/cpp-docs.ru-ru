---
title: в (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.in
dev_langs:
- C++
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c447147802d91df0f280a82c61d919ee673970a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222994"
---
# <a name="in-c"></a>in (C++)

Указывает, что параметр передается из вызывающей процедуры вызываемой процедуры.

## <a name="syntax"></a>Синтаксис

```cpp
[in]
```

## <a name="remarks"></a>Примечания

**В** атрибут C++ имеет ту же функциональность, что [в](/windows/desktop/Midl/in) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [bindable](../windows/bindable.md) пример демонстрирует использование **в**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**retval**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[defaultvalue](../windows/defaultvalue.md)  
[id](../windows/id.md)  
[out](../windows/out-cpp.md)  