---
title: MSG Structure1 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2819faa25e2dbd41d6578d60780d13011bb645c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388398"
---
# <a name="msg-structure1"></a>MSG Structure1

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

