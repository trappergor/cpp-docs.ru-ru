---
title: Move-функция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc1d0c7ed8655037eebfc12097789253b3027e9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603899"
---
# <a name="move-function"></a>Move - функция

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>Параметры

*T*  
Тип аргумента.

*arg*  
Аргумент для перемещения.

## <a name="return-value"></a>Возвращаемое значение

Параметр *arg* после ссылка или rvalue атрибутами, если таковые имеются, будут удалены.

## <a name="remarks"></a>Примечания

Перемещает указанный аргумент из одного расположения в другое.

Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)