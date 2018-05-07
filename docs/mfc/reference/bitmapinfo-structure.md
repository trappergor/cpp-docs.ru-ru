---
title: Структура BITMAPINFO | Документы Microsoft
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
ms.openlocfilehash: e061802cbcd8926a146e5765cc9ecfd9bf917295
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bitmapinfo-structure"></a>Структура BITMAPINFO
`BITMAPINFO` Определяет структуру измерения и цвет шрифта для аппаратно независимые Windows точечного рисунка (DIB).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>Параметры  
 `bmiHeader`  
 Указывает [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) структуру, содержащую сведения об измерениях и цветовой формат аппаратно независимый точечный рисунок.  
  
 `bmiColors`  
 Указывает массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) или `DWORD` типы данных, которые определяют цвета в битовой карте.  
  
## <a name="remarks"></a>Примечания  
 Аппаратно независимый точечный рисунок состоит из двух отдельных частей: `BITMAPINFO` структура, описывающая размеры и цвета точечного рисунка и массив байтов, определяющих пиксели в битовой карте. Биты в массиве упакованы вместе, но каждой строки должно дополняются нулями до конца на `LONG` границ. При положительном Высота растрового изображения находятся левого нижнего угла. Если высота имеет отрицательное значение, то источником является верхнего левого угла.  
  
 Объект *упакованный растрового изображения* — это битовая карта, где массив байтов непосредственно за `BITMAPINFO` структуры. Упакованный растровые изображения для ссылки на один указатель.  
  
 Дополнительные сведения о `BITMAPINFO` структуры и соответствующие значения для элементов `BITMAPINFOHEADER` и `RGBQUAD` структуры, в следующих разделах документации по пакету Windows SDK.  
  
- [Структура BITMAPINFO](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) структуры  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) структуры  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

