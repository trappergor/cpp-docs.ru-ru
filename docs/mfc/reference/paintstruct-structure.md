---
title: Структура PAINTSTRUCT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- PAINTSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75a3db6c6beb18afe2303b464fcab290b2e132fc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338214"
---
# <a name="paintstruct-structure"></a>Структура PAINTSTRUCT
`PAINTSTRUCT` Структура содержит сведения, который может использоваться для рисования клиентской области окна.  
  
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
 Идентифицирует контекста отображения, используемый для рисования.  
  
 *fErase*  
 Указывает, должен ли фон перерисовку. Это не 0, если приложение перерисовывать в фоновом режиме. Приложение отвечает за рисование фона, если класс окна Windows создается без кисть фона (см. в описании `hbrBackground` членом [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры в пакете SDK для Windows).  
  
 *rcPaint*  
 Указывает в верхнем левом углу и снижайте правой углов прямоугольника, в котором запрашивается заливку.  
  
 *fRestore*  
 Зарезервированным членом. Он используется внутренним образом Windows.  
  
 *fIncUpdate*  
 Зарезервированным членом. Он используется внутренним образом Windows.  
  
 *rgbReserved [16]*  
 Зарезервированным членом. Зарезервированным блоком памяти, используется системой Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)

