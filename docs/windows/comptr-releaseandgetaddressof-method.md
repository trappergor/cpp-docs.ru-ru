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
ms.openlocfilehash: e3efdce7cde39431a8d6f097aace2ed2f5a66b4d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589951"
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

[Класс ComPtr](../windows/comptr-class.md)  
[Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)