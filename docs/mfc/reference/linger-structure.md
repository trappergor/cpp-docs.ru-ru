---
title: Структура LINGER | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dda3aab3c4a967c82a699058868edc8fc183984
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386383"
---
# <a name="linger-structure"></a>Структура LINGER

`LINGER` Структура используется для управления параметры SO_LINGER и SO_DONTLINGER `CAsyncSocket::GetSockOpt`.

## <a name="syntax"></a>Синтаксис

```
struct linger {
    u_short l_onoff;            // option on/off
    u_short l_linger;           // linger time
};
```

## <a name="remarks"></a>Примечания

Установка параметра SO_DONTLINGER предотвращает блокировку функция-член `Close` при ожидании неотправленные данные для отправки. Установка этого параметра эквивалентно установке SO_LINGER с `l_onoff` присвоено значение 0.

## <a name="requirements"></a>Требования

**Заголовок:** winsock2.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)<br/>
[CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

