---
title: Метод EventTargetArray::End | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::End
dev_langs:
- C++
helpviewer_keywords:
- End method
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 341333b0c4f51c42004ad638a5a8f4fcb7d7e466
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596495"
---
# <a name="eventtargetarrayend-method"></a>Метод EventTargetArray::End

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
ComPtr<IUnknown>* End();
```

## <a name="return-value"></a>Возвращаемое значение

Адрес последнего элемента в массиве внутренних обработчиков событий.

## <a name="remarks"></a>Примечания

Возвращает адрес последнего элемента в массиве внутренних обработчиков событий.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс EventTargetArray](../windows/eventtargetarray-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)