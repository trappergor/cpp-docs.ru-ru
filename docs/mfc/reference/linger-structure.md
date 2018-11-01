---
title: Структура LINGER
ms.date: 11/04/2016
f1_keywords:
- LINGER
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
ms.openlocfilehash: 78f1a5ce993373ea9e477262f0779515c52dbd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495322"
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

