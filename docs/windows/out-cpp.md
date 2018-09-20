---
title: out (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b90222faedf298f75bfea72c661a3f23f26eaed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394891"
---
# <a name="out-c"></a>out (C++)

Определяет параметры-указатели, которые возвращаются из вызываемой процедуры в вызывающую (от сервера к клиенту).

## <a name="syntax"></a>Синтаксис

```cpp
[out]
```

## <a name="remarks"></a>Примечания

**Out** атрибут C++ имеет ту же функциональность, что [out](/windows/desktop/Midl/out-idl) описании атрибута MIDL.

## <a name="example"></a>Пример

Просмотрите пример с [bindable](../windows/bindable.md) , чтобы увидеть, как можно использовать **out**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты параметра](../windows/parameter-attributes.md)<br/>
[defaultvalue](../windows/defaultvalue.md)<br/>
[id](../windows/id.md)  