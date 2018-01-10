---
title: "Структура BITMAPINFO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BITMAPINFO
dev_langs: C++
helpviewer_keywords: BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9d704fec4a6ae0a95bd393b4a7fffa24884711e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

