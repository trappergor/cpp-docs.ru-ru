---
title: Метод ComPtr::ReleaseAndGetAddressOf | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f4aee13808fd55c42319aab90c13af7922ed9d2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394846"
---
# <a name="comptrreleaseandgetaddressof-method"></a>Метод ComPtr::ReleaseAndGetAddressOf

Освобождает интерфейс, связанный с данным **ComPtr** , а затем извлекает адрес [ptr_](../windows/comptr-ptr-data-member.md) элемент данных, который содержит указатель на интерфейс, который был выпущен.

## <a name="syntax"></a>Синтаксис

```cpp
T** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>Возвращаемое значение

Адрес [ptr_](../windows/comptr-ptr-data-member.md) данными-членом это **ComPtr**.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)<br/>
[Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)