---
title: "TN001: Регистрация класса Window | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.registration
dev_langs: C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8278a1dd22a242834fd4559c580820ae6e69e21d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tn001-window-class-registration"></a>TN001. Регистрация класса Window
Эта заметка описывает MFC подпрограммы, которые регистрируют специальные [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es, необходимые для Microsoft Windows. Определенные `WNDCLASS` описаны атрибуты, используемые MFC и Windows.  
  
## <a name="the-problem"></a>Проблема  
 Атрибуты [CWnd](../mfc/reference/cwnd-class.md) объекта, например `HWND` обработки в Windows, хранятся в двух местах: объект window и `WNDCLASS`. Имя `WNDCLASS` передается Общие окна создания функции например [CWnd::Create](../mfc/reference/cwnd-class.md#create) и [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) в `lpszClassName` параметра.  
  
 Это `WNDCLASS` должны быть зарегистрированы посредством одного из четырех средств:  
  
-   Неявно с помощью предоставляемой MFC `WNDCLASS`.  
  
-   Неявно с Создание подкласса элемента управления Windows (или других элементов управления).  
  
-   Явным образом путем вызова MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) или [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
-   Явным образом, вызвав процедуру Windows [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586).  
  
## <a name="wndclass-fields"></a>Например, WNDCLASS поля  
 `WNDCLASS` Структура состоит из различных полей, которые описывают класс окна. В следующей таблице показаны поля и указывает, как они используются в приложениях MFC:  
  
|Поле|Описание|  
|-----------|-----------------|  
|`lpfnWndProc`|Процедура окна должен быть`AfxWndProc`|  
|`cbClsExtra`|не используется (должно быть равно нулю)|  
|`cbWndExtra`|не используется (должно быть равно нулю)|  
|`hInstance`|автоматически заполняется [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|  
|`hIcon`|значок окна фрейма, см. ниже|  
|`hCursor`|курсор, когда указатель мыши находится на окно, см. ниже|  
|`hbrBackground`|цвет фона, см. ниже|  
|`lpszMenuName`|не используется (должен иметь значение NULL)|  
|`lpszClassName`|Имя класса, см. ниже|  
  
## <a name="provided-wndclasses"></a>Предоставленный WNDCLASSes  
 Более ранних версиях MFC (до MFC 4.0), предоставляется несколько предопределенных классов окон. Эти классы окон больше не предоставляются по умолчанию. Приложения должны использовать `AfxRegisterWndClass` с соответствующими параметрами.  
  
 Если приложение содержит ресурс с Идентификатором указанного ресурса (например, AFX_IDI_STD_FRAME), MFC использует этот ресурс. В противном случае он будет использовать ресурсов по умолчанию. Для значка используется значок стандартного приложения и для курсора, используется стандартная стрелка курсора.  
  
 Два значка поддержки приложений MDI с типами одного документа: один значок для основного приложения, другой значок для преобразованного в значок документа или MDIChild windows. Для нескольких типов документов с помощью разных значков, необходимо зарегистрировать дополнительные `WNDCLASS`es или используйте [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) функции.  
  
 `CFrameWnd::LoadFrame`Регистрирует `WNDCLASS` с помощью идентификатора значок, который указан в качестве первого параметра и следующие стандартные атрибуты:  
  
-   стиль класса: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;  
  
-   значок AFX_IDI_STD_FRAME  
  
-   курсор в виде стрелки  
  
-   Цвет фона COLOR_WINDOW  
  
 Значения цвета фона и курсор для [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) не используется с клиентской области `CMDIFrameWnd` полностью охвачен **MDICLIENT** окна. Корпорация Майкрософт не поддерживается создание подклассов **MDICLIENT** окна таким образом используйте стандартные цвета и типы курсора, если это возможно.  
  
## <a name="subclassing-and-superclassing-controls"></a>Подклассы и элементы управления создание суперклассов  
 Если вы подкласс или суперкласса Windows элемента управления (например, [CButton](../mfc/reference/cbutton-class.md)) после создания класса автоматически получает `WNDCLASS` атрибутов, предоставленных в реализации Windows этого элемента управления.  
  
## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass-функция  
 MFC предоставляет вспомогательные функции для регистрации класса окна. Имея набор атрибутов (стили класса окна, курсор, Фоновая кисть и значок), синтетические имя создается и регистрируется результирующий класс окна. Например:  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```  
  
 Эта функция возвращает временной строки созданного окна зарегистрированного имени класса. Дополнительные сведения об этой функции см. в разделе [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).  
  
 Возвращаемая строка является указателем временный буфер статическая строка. Он является допустимым до следующего вызова `AfxRegisterWndClass`. Если вы хотите сохранить эту строку вокруг, сохранить ее в [CString](../atl-mfc-shared/using-cstring.md) переменной, как показано в примере:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);

...  
```  
  
 `AfxRegisterWndClass`вызывает исключение [CResourceException](../mfc/reference/cresourceexception-class.md) Если класс окна не удалось зарегистрировать (из-за некорректных параметров, или недостаточно памяти Windows).  
  
## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass и функции AfxRegisterClass  
 Если вы хотите сделать что-либо более сложными чем `AfxRegisterWndClass` предоставляет, можно вызвать Windows API `RegisterClass` или функции MFC `AfxRegisterClass`. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` функции принимают `lpszClassName` строковое имя для класс окна в качестве первого параметра. Можно использовать любое имя класса окна зарегистрированных, независимо от метода, который использовался для его регистрации.  
  
 Очень важно использовать `AfxRegisterClass` (или `AfxRegisterWndClass`) в библиотеке DLL для Win32. Win32 не может отменить регистрацию автоматически классы зарегистрированы библиотекой DLL, поэтому необходимо явно отменить регистрацию классов при завершении библиотеки DLL. С помощью `AfxRegisterClass` вместо `RegisterClass` это выполняется автоматически. `AfxRegisterClass`хранит список уникальных классов зарегистрирован для библиотеки DLL и автоматически отменять их при завершении библиотеки DLL. При использовании `RegisterClass` в библиотеку DLL, необходимо убедиться, что все классы не зарегистрированы, при завершении библиотеки DLL (в вашей [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) функции). Невыполнение этого требования может привести к `RegisterClass` неожиданному сбою, когда другое клиентское приложение пытается использовать библиотеку DLL.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

