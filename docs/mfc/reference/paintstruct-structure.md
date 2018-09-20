---
title: Структура PAINTSTRUCT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 531dbc3c0e9b609aeaf5d9179491aa0fb3990363
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382925"
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
Указывает, должен ли фон перерисовку. Это не 0, если приложение перерисовывать в фоновом режиме. Приложение отвечает за рисование фона, если класс окна Windows создается без кисть фона (см. в описании `hbrBackground` членом [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуры в пакете SDK для Windows).

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

