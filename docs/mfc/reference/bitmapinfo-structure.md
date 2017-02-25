---
title: "Структура BITMAPINFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAPINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAPINFO - структура"
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Структура BITMAPINFO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `BITMAPINFO` определяет измерения и данные о цвете для файла DIB Windows \(DIB\).  
  
## Синтаксис  
  
```  
typedef struct tagBITMAPINFO {  
   BITMAPINFOHEADER bmiHeader;  
   RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### Параметры  
 `bmiHeader`  
 Определяет структуру [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376), которая содержит сведения об измерениях и формате DIB \(цвета.  
  
 `bmiColors`  
 Определяется массив [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) или типов данных `DWORD`, определяющие цвета в различных форматах.  
  
## Заметки  
 DIB \(состоит из 2 определенных частей: структура `BITMAPINFO`, описание измерения и цвета растровых изображений и массив байтов, который определяет пиксели в различных форматах.  Биты в массиве упаковываны вместе, но каждой линии сканирования необходимо начало нулями для выполнения на границе `LONG`.  Если высота положительному числу, координата растрового изображения нижний левый угол.  Если высота отрицательное, координата верхний левый угол.  
  
 *упаковыванное растровое изображение* растровое изображение, массив байтов следует сразу за структура `BITMAPINFO`.  Упаковыванные растровые изображения используется одним указателем.  
  
 Дополнительные сведения о структуре и соответствующие значения `BITMAPINFO` для членов структуры `BITMAPINFOHEADER` и `RGBQUAD` см. в следующих разделах в документации [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="b5dd2e8c9cedbac12eb858bd01a029a2" class\="tgtSentence"\>Структура BITMAPINFO\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
-   [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) структура  
  
-   [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) структура  
  
## Требования  
 **Заголовок:** wingdi.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)