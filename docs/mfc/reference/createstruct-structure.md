---
title: "Структура CREATESTRUCT | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATESTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CREATESTRUCT - структура"
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура CREATESTRUCT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CREATESTRUCT` определяет параметры инициализации, передаваемые в процедуру окна приложения.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `lpCreateParams`  
 Указывает на данные, используемые для создания окна.  
  
 `hInstance`  
 Определяет дескриптор модуля экземпляра модуля, имеющий новое окно.  
  
 `hMenu`  
 Определяет меню, которые будут использоваться новое окно.  Если дочернее окно, содержащее идентификатор целые числа  
  
 `hwndParent`  
 Определяет окно с новое окно.  Этот элемент **NULL**, если новое окно окном верхнего уровня.  
  
 `cy`  
 Задает высоту нового окна.  
  
 `cx`  
 Задает ширину нового окна.  
  
 `y`  
 Задает координату y верхнего левого угла нового окна.  Координаты относительно родительскому окну, если новое окно дочернее окно; в противном случае относительно начала координат экрана.  
  
 `x`  
 Задает координату x верхнего левого угла нового окна.  Координаты относительно родительскому окну, если новое окно дочернее окно; в противном случае относительно начала координат экрана.  
  
 `style`  
 Определяет [стиль](../../mfc/reference/styles-used-by-mfc.md) нового окна.  
  
 `lpszName`  
 Указывает на объединения завершенной строку, которая указывает имя нового окна.  
  
 `lpszClass`  
 Указывает на объединения завершенной строку, которая указывает имя класса Windows нового окна \(структуры [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576); дополнительные сведения см. в разделе, посвященном [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 `dwExStyle`  
 Указывает [расширенный стиль](../Topic/Extended%20Window%20Styles.md) для нового окна.  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../Topic/CWnd::OnCreate.md)