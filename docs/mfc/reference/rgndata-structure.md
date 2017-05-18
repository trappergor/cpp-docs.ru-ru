---
title: "Структура RGNDATA | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 93a7c79f175e22dcb0b40cb39b157cfe21a98e93
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="rgndata-structure"></a>Структура RGNDATA
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
 Указывает произвольного размера буфера, который содержит [RECT](../../mfc/reference/rect-structure1.md) структур, составляющих области.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)


