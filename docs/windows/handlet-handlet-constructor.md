---
title: Конструктор HandleT::HandleT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d84bde2a9c83dedf6fa509101dddff85bd27999
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426124"
---
# <a name="handlethandlet-constructor"></a>Конструктор HandleT::HandleT

Инициализирует новый экземпляр класса **HandleT** класса.

## <a name="syntax"></a>Синтаксис

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()  
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор.

## <a name="remarks"></a>Примечания

Первый конструктор инициализирует **HandleT** объект, который не является допустимым дескриптором для объекта. Второй конструктор создает новый **HandleT** объект из параметра *h*.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HandleT](../windows/handlet-class.md)