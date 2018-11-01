---
title: Структура MSG
ms.date: 11/04/2016
f1_keywords:
- MSG
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
ms.openlocfilehash: 1a953f8d0d685e25beedd2d401e227c934414208
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499819"
---
# <a name="msg-structure"></a>Структура MSG

`MSG` Структура содержит информацию сообщения из очереди сообщений потока.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagMSG {     // msg
    HWND hwnd;
    UINT message;
    WPARAM wParam;
    LPARAM lParam;
    DWORD time;
    POINT pt;
} MSG;
```

#### <a name="parameters"></a>Параметры

*HWND*<br/>
Идентифицирует окна, Оконная процедура которого получает сообщение.

*message*<br/>
Указывает номер сообщения.

*wParam*<br/>
Задает дополнительные сведения о сообщении. Точный смысл зависит от значения `message` член.

*lParam*<br/>
Задает дополнительные сведения о сообщении. Точный смысл зависит от значения `message` член.

*time*<br/>
Указывает время, по которому было сгенерировано сообщение.

*pt*<br/>
Указывает положение курсора в экранных координатах, когда было сгенерировано сообщение.

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

