---
title: Оператор Dontusenewusemake::operator new | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99e82de06f64816521c47c78648108a9ae815279
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443232"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>Оператор DontUseNewUseMake::operator new

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Параметры

*__unnamed0*<br/>
Неименованный параметр, который определяет количество байт памяти для выделения.

*Размещение*<br/>
Выделяемый тип.

## <a name="return-value"></a>Возвращаемое значение

Предоставляет способ передачи дополнительных аргументов при перегрузке оператора **новый**.

## <a name="remarks"></a>Примечания

Перегружает оператор **новый** и предотвращает использование в `RuntimeClass`.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс DontUseNewUseMake](../windows/dontusenewusemake-class.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)