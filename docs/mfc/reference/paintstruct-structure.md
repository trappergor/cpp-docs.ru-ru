---
title: "Структура PAINTSTRUCT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PAINTSTRUCT
dev_langs: C++
helpviewer_keywords: PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92583bba3dca60caa2895966a87571dc60805475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="paintstruct-structure"></a>Структура PAINTSTRUCT
`PAINTSTRUCT` Структура содержит сведения, которые можно использовать для рисования клиентской области окна.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>Параметры  
 *hdc*  
 Определяет контекст отображения для рисования.  
  
 *fErase*  
 Указывает, должна ли фон перерисовку. Не является 0, если приложение перерисовываться в фоновом режиме. Приложение отвечает за рисование фон, если класс окна Windows создается без кисть фона (см. в описании **hbrBackground** членом [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры в Windows SDK).  
  
 *rcPaint*  
 Указывает верхний слева и сокращения правой углов прямоугольника, в котором запрашивается рисования.  
  
 *fRestore*  
 Зарезервированный элемент. Он используется системой операционной системой Windows.  
  
 *fIncUpdate*  
 Зарезервированный элемент. Он используется системой операционной системой Windows.  
  
 *rgbReserved [16]*  
 Зарезервированный элемент. Зарезервированные блок памяти, используется системой Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

