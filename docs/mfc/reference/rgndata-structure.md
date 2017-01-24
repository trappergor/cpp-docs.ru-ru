---
title: "Структура RGNDATA | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RGNDATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RGNDATA - структура"
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура RGNDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `RGNDATA` Структура содержит заголовок и массив прямоугольников, составляющие области. Эти прямоугольники, отсортированный сверху вниз слева направо, не перекрываются.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 
    typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rdh*  
 Указывает [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) структуры. (Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) Члены этой структуры укажите тип области (если он является прямоугольной или форме трапеции), количеством прямоугольников, составляющие области, размер буфера, который содержит прямоугольник структуры, и так далее.  
  
 `Buffer`  
 Указывает произвольного размера буфера, который содержит [RECT](RECT%20Structure1.md) структур, составляющих области.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#CreateFromData)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#GetRegionData)

