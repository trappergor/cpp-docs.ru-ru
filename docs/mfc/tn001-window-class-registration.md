---
title: "TN001. Регистрация класса Window | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterClass - функция"
  - "TN001"
  - "WNDCLASS"
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# TN001. Регистрация класса Window
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта заметка описаны процедуры MFC, регистрирующие специальное [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) es необходимо Microsoft Windows.  Обсуждаются особые атрибуты `WNDCLASS`, используемые MFC и Windows.  
  
## Проблема  
 Атрибуты объекта [CWnd](../Topic/CWnd%20Class.md), как дескриптор `HWND` в Windows 2, хранятся в двух местах: объект окна и `WNDCLASS`.  Имя `WNDCLASS` передается общим функциям создания окна, например [CWnd::Create](../Topic/CWnd::Create.md) и [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) в параметре `lpszClassName`.  
  
 Это `WNDCLASS` должны быть зарегистрированы с помощью одного из 4 означает:  
  
-   Неявно с помощью `WNDCLASS` предоставленного MFC.  
  
-   Создание подкласса для управления неявно с Windows \(или какой\-либо другой элемент управления\).  
  
-   Явно, вызвав MFC [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) или [AfxRegisterClass](../Topic/AfxRegisterClass.md).  
  
-   Явно, вызвав процедуру [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) Windows.  
  
## Поля WNDCLASS  
 Структура `WNDCLASS` состоит из двух полей, описывающие класса окна.  В следующей таблице показаны поля и определяет, как они используются в приложении MFC.  
  
|Поле|Описание|  
|----------|--------------|  
|`lpfnWndProc`|обработчик окна, должно быть `AfxWndProc`|  
|`cbClsExtra`|не используется \(ноль\).|  
|`cbWndExtra`|не используется \(ноль\).|  
|`hInstance`|автоматически, залитый с [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|  
|`hIcon`|Значок для фреймовых windows см. ниже|  
|`hCursor`|курсор, когда указатель мыши находится над полем см. ниже|  
|`hbrBackground`|цвет фона см. ниже|  
|`lpszMenuName`|не используется \(NULL\).|  
|`lpszClassName`|имя класса см. ниже|  
  
## В WNDCLASSes  
 Более ранние версии MFC MFC \(до 4.0\), при условии, что несколько предварительно определенных классов окна.  Эти классы окна больше не предоставляемые по умолчанию.  Приложения должны использовать `AfxRegisterWndClass` с соответствующими параметрами.  
  
 Если приложение предоставляет ресурс с идентификатором указанного ресурса \(например, AFX\_IDI\_STD\_FRAME\), MFC использует этот ресурс.  В противном случае он будет использовать ресурса по умолчанию.  Для Значка стандартный значок приложения используется и для курсора, используется стандартный курсор стрелки.  
  
 2 Значка поддерживают приложения MDI с типами одного документа. один Значок для основного приложения, другой Значок для иконических документа или окна MDIChild.  Для типов многооконного с различными Значками необходимо зарегистрировать дополнительные `WNDCLASS` es или использовать функции [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
 `CFrameWnd::LoadFrame` регистрирует `WNDCLASS` с помощью Значка идентификатор был определен как первый параметр и следующие стандартные атрибуты:  
  
-   стиль класса: CS\_DBLCLKS &#124; CS\_HREDRAW &#124; CS\_VREDRAW;  
  
-   Значок AFX\_IDI\_STD\_FRAME  
  
-   курсор стрелки  
  
-   Цвет фона COLOR\_WINDOW  
  
 Не используются значения цвета фона и курсор для [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), поскольку клиентскую область `CMDIFrameWnd` полностью покрыта окном **MDICLIENT**.  Корпорация Майкрософт не ободряет создание подкласса для окна **MDICLIENT**, чтобы использовать стандартные цвета и типы курсора, когда это возможно.  
  
## Создание подкласса для управления и Суперкласс  
 Если подкласс суперкласс или элемент управления Windows \(например, [CButton](../mfc/reference/cbutton-class.md)\), а затем класс автоматически используется атрибуты `WNDCLASS`, описанном в реализации Windows этого элемента управления.  
  
## Функция AfxRegisterWndClass  
 MFC предоставляет вспомогательную функцию для регистрации класса окна.  Данные набор атрибутов \(стиля класса окна, курсора, кисти фона и значок\), создается синтетическое имя, и результирующий класс окна зарегистрирован.  Например:  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle, HCURSOR hCursor, HBRUSH hbrBackground, HICON hIcon);  
```  
  
 Эта функция возвращает временная строка созданного зарегистрированного имени класса окна.  Дополнительные сведения об этой функции см. в разделе [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md).  
  
 Возвращаемая строка статический временный указатель на буфер строк.  Она является допустимой до следующего вызова `AfxRegisterWndClass`.  Чтобы сохранить эту строку по тексту, сохранить в переменной [CString](../atl-mfc-shared/using-cstring.md), как показано в следующем примере:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);  
...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);  
...  
```  
  
 `AfxRegisterWndClass` создает [CResourceException](../mfc/reference/cresourceexception-class.md), если класс окна не удалось для регистрации, \(или из\-за плохих параметров или нехватка памяти Windows\).  
  
## Функции RegisterClass и AfxRegisterClass  
 Если требуется сделать что\-нибудь более чем изощрять, какие `AfxRegisterWndClass` предоставляет, можно вызвать API `RegisterClass` Windows или функция `AfxRegisterClass` MFC.  `CWnd`, функции [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` принимает строковое имя `lpszClassName` класса окна в качестве первого параметра.  Можно использовать любое зарегистрированное имя класса окна, независимо от метода, используемого для регистрации.  
  
 Важно использовать `AfxRegisterClass` \(или `AfxRegisterWndClass`\) в библиотеке DLL в Win32.  Win32 не автоматически выполняет регистрацию зарегистрированные классы библиотек DLL, поэтому явно классы регистрацию, когда библиотека DLL завершено.  С помощью `AfxRegisterClass` вместо `RegisterClass` это осуществляется автоматически автоматически.  `AfxRegisterClass` ведет список уникальных классов, зарегистрированных в библиотеку DLL и будет автоматически регистрацию, когда библиотека DLL заканчивается.  При использовании `RegisterClass` в библиотеку DLL, необходимо убедиться, что все классы незарегистрированный, когда библиотека DLL завершения \(в функции [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) \).  Невыполнение этого требования может вызвать `RegisterClass` сбой неопределенным, если другое клиентское приложение пытается использовать библиотеку DLL.  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)