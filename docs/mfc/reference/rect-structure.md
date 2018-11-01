---
title: Структура RECT
ms.date: 11/04/2016
f1_keywords:
- LPRECT
- RECT
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
ms.openlocfilehash: 1cb997fc0f1ec89eabf5e4d2c2c5ccb15e3bafec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549020"
---
# <a name="rect-structure"></a>Структура RECT

`RECT` Структура определяет координаты верхнего левого и правого нижнего углов прямоугольника.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagRECT {
    LONG left;
    LONG top;
    LONG right;
    LONG bottom;
} RECT;
```

## <a name="members"></a>Участники

`left`<br/>
Задает координату по оси x верхнего левого угла прямоугольника.

`top`<br/>
Указывает Координата по оси y верхнего левого угла прямоугольника.

`right`<br/>
Задает координату по оси x нижнего правого угла прямоугольника.

`bottom`<br/>
Задает координату по оси y правого нижнего угла прямоугольника.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** windef.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)
