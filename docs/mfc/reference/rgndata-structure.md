---
title: Структура RGNDATA | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c539feaac9cac5bca3a41868cc03379a63bf6bb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204363"
---
# <a name="rgndata-structure"></a>Структура RGNDATA
`RGNDATA` Структура содержит заголовок и массив прямоугольников, которые составляют регион. Эти прямоугольники, отсортированный сверху вниз слева направо, не перекрываются.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rdh*  
 Указывает [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader) структуры. (Дополнительные сведения об этой структуре см. в разделе Windows SDK.) Члены этой структуры укажите тип области (если он является прямоугольной или форме трапеции), количеством прямоугольников, составляющие области, размер буфера, который содержит прямоугольник структуры, и так далее.  
  
 *буфер*  
 Указывает буфер произвольного размера, который содержит [RECT](../../mfc/reference/rect-structure1.md) структур, составляющих области.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

