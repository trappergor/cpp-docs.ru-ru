---
title: Структура PAINTSTRUCT
ms.date: 11/04/2016
f1_keywords:
- PAINTSTRUCT
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
ms.openlocfilehash: f1b901ef26c61adbedb3bbe56808cd94bdfad30d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694651"
---
# <a name="paintstruct-structure"></a>Структура PAINTSTRUCT

`PAINTSTRUCT` Структура содержит сведения, который может использоваться для рисования клиентской области окна.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagPAINTSTRUCT {
    HDC hdc;
    BOOL fErase;
    RECT rcPaint;
    BOOL fRestore;
    BOOL fIncUpdate;
    BYTE rgbReserved[16];
} PAINTSTRUCT;
```

#### <a name="parameters"></a>Параметры

*hdc*<br/>
Идентифицирует контекста отображения, используемый для рисования.

*fErase*<br/>
Указывает, должен ли фон перерисовку. Это не 0, если приложение перерисовывать в фоновом режиме. Приложение отвечает за рисование фона, если класс окна Windows создается без кисть фона (см. в описании `hbrBackground` членом [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) структуры в пакете SDK для Windows).

*rcPaint*<br/>
Указывает в верхнем левом углу и снижайте правой углов прямоугольника, в котором запрашивается заливку.

*fRestore*<br/>
Зарезервированным членом. Он используется внутренним образом Windows.

*fIncUpdate*<br/>
Зарезервированным членом. Он используется внутренним образом Windows.

*rgbReserved [16]*<br/>
Зарезервированным членом. Зарезервированным блоком памяти, используется системой Windows.

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

