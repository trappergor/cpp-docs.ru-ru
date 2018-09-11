---
title: retval | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ff83b156054774a06a371e7832dc73dc95a579c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221262"
---
# <a name="retval"></a>retval

Назначает параметр, который получает возвращаемое значение члена.

## <a name="syntax"></a>Синтаксис

```cpp
[retval]
```

## <a name="remarks"></a>Примечания

**Retval** атрибут C++ имеет ту же функциональность, что [retval](/windows/desktop/Midl/retval) описании атрибута MIDL.

**retval** должны располагаться на последний аргумент в объявлении функции.

## <a name="example"></a>Пример

См. в примере [bindable](../windows/bindable.md) использовать образец **retval**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**out**|
|**Недопустимые атрибуты**|**in**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  