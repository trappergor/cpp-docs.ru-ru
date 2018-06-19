---
title: Структура RGNDATA | Документы Microsoft
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
ms.openlocfilehash: 591c2dd65fdb9dde00f0ac1373c39affbe82da85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373512"
---
# <a name="rgndata-structure"></a>Структура RGNDATA
`RGNDATA` Структура содержит заголовок и массив прямоугольников, составляющие области. Эти прямоугольники отсортированный сверху вниз слева направо, не перекрываются.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Параметры  
 *rdh*  
 Указывает [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) структуры. (Дополнительные сведения о структуре см. в Windows SDK.) Члены этой структуры, укажите тип области (если он является прямоугольный или форме трапеции), число прямоугольники, составляющие области, размер буфера, который содержит прямоугольник структуры, и так далее.  
  
 `Buffer`  
 Указывает произвольного размера буфера, содержащего [RECT](../../mfc/reference/rect-structure1.md) структур, составляющих области.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

