---
title: Метод HANDLETraits::Close | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1b36d4feea61e9a79978cc86dca29a7ad14846a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594040"
---
# <a name="handletraitsclose-method"></a>Метод HANDLETraits::Close

Закрывает указанный дескриптор.

## <a name="syntax"></a>Синтаксис

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*h*  
Чтобы закрыть дескриптор.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** Если обрабатывать *h* Закрыто успешно; в противном случае — значение **false**.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>См. также

[Структура HANDLETraits](../windows/handletraits-structure.md)