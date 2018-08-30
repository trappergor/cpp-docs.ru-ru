---
title: Структура CREATESTRUCT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 594f71d5166261dbb1bb08422a564157bfce2721
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203665"
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
 *lpCreateParams*  
 Указывает данные, используемые для создания окна.  
  
 *hInstance*  
 Определяет дескриптор модуля, которому принадлежит окно, новый экземпляр модуля.  
  
 *hMenu*  
 Идентифицирует меню для использования нового окна. Если дочернее окно, содержащее целочисленный идентификатор.  
  
 *hwndParent*  
 Определяет окно, которому принадлежит новое окно. Этот элемент имеет значение NULL, если новое окно является окном верхнего уровня.  
  
 *CY*  
 Высота нового окна.  
  
 *CX*  
 Ширина нового окна.  
  
 *y*  
 Указывает y координата левого верхнего нового окна. Координаты указываются относительно родительского окна, если новое окно — дочернее окно; в противном случае координаты определяются относительно экрана.  
  
 *x*  
 Указывает Координата по оси x верхнего левого угла нового окна. Координаты указываются относительно родительского окна, если новое окно — дочернее окно; в противном случае координаты определяются относительно экрана.  
  
 *Стиль*  
 Указывает новое окно [стиля](../../mfc/reference/styles-used-by-mfc.md).  
  
 *lpszName*  
 Указатель на заканчивающуюся нулем строку, указывающее имя нового окна.  
  
 *lpszClass*  
 Указывает на заканчивающуюся нулем строку, указывающее имя класса новое окно Windows ( [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуры; Дополнительные сведения см. в Windows SDK).  
  
 *dwExStyle*  
 Указывает [расширенный стиль](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) для нового окна.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


