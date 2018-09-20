---
title: RECT Structure1 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa77af9dd97afc2e9b0cfb94c1fd4c69a50f309b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419598"
---
# <a name="rect-structure1"></a>RECT Structure1

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
