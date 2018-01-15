---
title: "Структура CREATESTRUCT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CREATESTRUCT
dev_langs: C++
helpviewer_keywords: CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97ca66036930963028681b6179ac7176b0350166
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="createstruct-structure"></a>Структура CREATESTRUCT
`CREATESTRUCT` Структура определяет параметры инициализации, передаваемые в процедуру окна приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `lpCreateParams`  
 Указывает на данные, который будет использоваться для создания окна.  
  
 `hInstance`  
 Определяет дескриптор экземпляра модуля модуля, которому принадлежит новое окно.  
  
 `hMenu`  
 Идентифицирует меню, чтобы использоваться в новом окне. Если дочернее окно содержит целочисленный идентификатор.  
  
 `hwndParent`  
 Идентифицирует окно, которому принадлежит новое окно. Этот член представляет **NULL** Если новое окно является окном верхнего уровня.  
  
 `cy`  
 Задает высоту области окна.  
  
 `cx`  
 Задает ширину нового окна.  
  
 `y`  
 Задает координату y верхнего левого угла нового окна. Координаты указываются относительно родительского окна, если новое окно дочернего окна; в противном случае координаты указываются относительно начала координат экрана.  
  
 `x`  
 Задает координату x левого верхнего угла нового окна. Координаты указываются относительно родительского окна, если новое окно дочернего окна; в противном случае координаты указываются относительно начала координат экрана.  
  
 `style`  
 Указывает новое окно [стиль](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Указывает нулем строка, указывающая имя нового окна.  
  
 `lpszClass`  
 Указывает на строку символом null, указывающее имя класса новое окно Windows ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры; Дополнительные сведения см. в Windows SDK).  
  
 `dwExStyle`  
 Указывает [расширенный стиль](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) для нового окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


