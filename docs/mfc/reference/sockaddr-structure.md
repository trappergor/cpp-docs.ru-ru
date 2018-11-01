---
title: Структура SOCKADDR
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
ms.openlocfilehash: 68d5261c6520b5baee8495b72a0b9d234a35a185
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543849"
---
# <a name="sockaddr-structure"></a>Структура SOCKADDR

`SOCKADDR` Структура используется для хранения адреса протокола Интернета (IP) для компьютера, участвующих в связи сокеты Windows.

## <a name="syntax"></a>Синтаксис

```
struct sockaddr {
    unsigned short sa_family;
    char sa_data[14];
};
```

#### <a name="parameters"></a>Параметры

*sa_family*<br/>
Семейство адресов сокета.

*sa_data*<br/>
Максимальный размер всех структур адрес разных сокета.

## <a name="remarks"></a>Примечания

Пакет разработчика Microsoft TCP/IP сокеты поддерживает только адрес доменов Интернета. Фактически ввести значения для каждой части адреса, используйте `SOCKADDR_IN` структуру данных, которая предназначена для формат этого адреса. `SOCKADDR` И `SOCKADDR_IN` структур данных имеют одинаковый размер. Нужно просто привести переключиться между типами две структуры.

## <a name="requirements"></a>Требования

**Заголовок:** winsock2.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Структура SOCKADDR_IN](../../mfc/reference/sockaddr-in-structure.md)<br/>
[CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)<br/>
[CSocket::Create](../../mfc/reference/csocket-class.md#create)

