---
title: "Структура CREATESTRUCT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
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
ms.openlocfilehash: ec72d4725cb7e5959369b24a6ff7f0e3e9da1ca7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="createstruct-structure"></a>Структура CREATESTRUCT
`CREATESTRUCT` Определяет структуру параметров инициализации, передаваемые в процедуру окна приложения.  
  
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
 Указывает данные, которые используются для создания окна.  
  
 `hInstance`  
 Идентифицирует дескриптор экземпляра модуля, которому принадлежит окно нового модуля.  
  
 `hMenu`  
 Определяет меню для использования нового окна. Если дочернее окно, содержащее целочисленный идентификатор.  
  
 `hwndParent`  
 Определяет окно, которому принадлежит новое окно. Этот член представляет **NULL** Если новое окно является окном верхнего уровня.  
  
 `cy`  
 Высота нового окна.  
  
 `cx`  
 Задает ширину нового окна.  
  
 `y`  
 Задает координату y верхнего левого угла нового окна. Координаты указываются относительно родительского окна, если новое окно является окном дочернего; в противном случае координаты указываются относительно начала координат экрана.  
  
 `x`  
 Задает координату x левого верхнего угла новое окно. Координаты указываются относительно родительского окна, если новое окно является окном дочернего; в противном случае координаты указываются относительно начала координат экрана.  
  
 `style`  
 Указывает новое окно [стиль](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Указывает нулем строка, указывающая имя нового окна.  
  
 `lpszClass`  
 Указывает нулем строка, указывающая имя класса Windows новое окно ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры; Дополнительные сведения см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
 `dwExStyle`  
 Указывает [расширенный стиль](../../mfc/reference/extended-window-styles.md) для нового окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



