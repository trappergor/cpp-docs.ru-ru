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
ms.openlocfilehash: a9b1bd896157d7f11792a5a6514e30ecd3d46a19
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336261"
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
 *bmiHeader*  
 Указывает [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) структуру, содержащую сведения об измерениях и цвет формат аппаратно независимый точечный рисунок.  
  
 *bmiColors*  
 Указывает массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) или типы данных DWORD, определяющие цвета в точечном рисунке.  
  
## <a name="remarks"></a>Примечания  
 Аппаратно независимый точечный рисунок состоит из двух отдельных частей: `BITMAPINFO` структуру, которая содержит описание измерений и цветов точечного рисунка и массив байтов, определяющих пиксели в точечном рисунке. Группируется биты в массиве, но каждой строки должен быть нули для нее закончится **LONG** границ. При положительном высоту исходного растрового изображения является нижнего левого угла. Если высота отрицательное, то источником является верхнего левого угла.  
  
 Объект *упакованный точечного рисунка* является точечным рисунком, где массив байтов непосредственно за `BITMAPINFO` структуры. Упакованный точечных рисунков для ссылки на один указатель.  
  
 Дополнительные сведения о `BITMAPINFO` структурировать и соответствующие значения для членов `BITMAPINFOHEADER` и `RGBQUAD` структур, см. в следующих разделах электронной документации по Windows SDK.  
  
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

