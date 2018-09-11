---
title: usesgetlasterror | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39052024224b1a78a84b2d9503957b8fff09b96f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208295"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Вызывающий объект о том, есть ли ошибки при вызове этой функции, затем вызывающий объект затем можно вызвать `GetLastError` для получения кода ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Примечания

**Usesgetlasterror** атрибут C++ имеет ту же функциональность, что [usesgetlasterror](/windows/desktop/Midl/usesgetlasterror) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [idl_module](../windows/idl-module.md) примере образец демонстрирует использование **usesgetlasterror**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**модуль** атрибут|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  