---
title: Структура BITMAPINFO | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e114af97385241674cf9baa4f8d9883acdadef3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405961"
---
# <a name="bitmapinfo-structure"></a>Структура BITMAPINFO

`BITMAPINFO` Структура определяет измерения и сведения о цвете для Windows аппаратно независимый точечный рисунок (DIB).

## <a name="syntax"></a>Синтаксис

```
typedef struct tagBITMAPINFO {
    BITMAPINFOHEADER bmiHeader;
    RGBQUAD bmiColors[1];
} BITMAPINFO;
```

#### <a name="parameters"></a>Параметры

*bmiHeader*<br/>
Указывает [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) структуру, содержащую сведения об измерениях и цвет формат аппаратно независимый точечный рисунок.

*bmiColors*<br/>
Указывает массив [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) или типы данных DWORD, определяющие цвета в точечном рисунке.

## <a name="remarks"></a>Примечания

Аппаратно независимый точечный рисунок состоит из двух отдельных частей: `BITMAPINFO` структуру, которая содержит описание измерений и цветов точечного рисунка и массив байтов, определяющих пиксели в точечном рисунке. Группируется биты в массиве, но каждой строки должен быть нули для нее закончится **LONG** границ. При положительном высоту исходного растрового изображения является нижнего левого угла. Если высота отрицательное, то источником является верхнего левого угла.

Объект *упакованный точечного рисунка* является точечным рисунком, где массив байтов непосредственно за `BITMAPINFO` структуры. Упакованный точечных рисунков для ссылки на один указатель.

Дополнительные сведения о `BITMAPINFO` структурировать и соответствующие значения для членов `BITMAPINFOHEADER` и `RGBQUAD` структур, см. в следующих разделах электронной документации по Windows SDK.

- [Структура BITMAPINFO](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo)

- [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) структуры

- [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad) структуры

## <a name="requirements"></a>Требования

**Заголовок:** wingdi.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)<br/>
[BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)<br/>
[RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)

