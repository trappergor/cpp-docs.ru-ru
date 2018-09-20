---
title: 'TN001: Регистрация класса окна | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6818cb66f7ae9498ca13ac895a84e3b22c0c482
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426098"
---
# <a name="tn001-window-class-registration"></a>TN001. Регистрация класса Window

Эта заметка описывает процедуры MFC, зарегистрировать специальную [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)es, необходимые для Microsoft Windows. Определенные `WNDCLASS` рассматриваются атрибуты, используемые MFC и Windows.

## <a name="the-problem"></a>Проблема

Атрибуты [CWnd](../mfc/reference/cwnd-class.md) объекта, например `HWND` обрабатывать в Windows, хранятся в двух местах: объект окна и `WNDCLASS`. Имя `WNDCLASS` передается на общие окно создания функции, например [CWnd::Create](../mfc/reference/cwnd-class.md#create) и [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) в *lpszClassName* параметра.

Это `WNDCLASS` должен быть зарегистрирован одним из четырех способов:

- Неявно с помощью предоставляемой MFC `WNDCLASS`.

- Неявно, путем создания подклассов, элемент управления Windows (или другой элемент управления).

- Явно, путем вызова MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) или [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).

- Явно, путем вызова подпрограммы Windows [RegisterClass](https://msdn.microsoft.com/library/windows/desktop/ms633586).

## <a name="wndclass-fields"></a>Например, WNDCLASS поля

`WNDCLASS` Структура состоит из различных полей, которые описывают класс окна. В следующей таблице показаны поля и указывает, как они используются в приложениях MFC:

|Поле|Описание|
|-----------|-----------------|
|*lpfnWndProc*|Процедура окна должен быть `AfxWndProc`|
|*cbClsExtra*|не используется (должен быть равен нулю)|
|*cbWndExtra*|не используется (должен быть равен нулю)|
|*hInstance*|автоматически заполняется [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|
|*hIcon*|значок для окна фрейма, см. ниже|
|*hCursor*|курсор, когда указатель мыши находится на окно, см. ниже|
|*hbrBackground*|цвет фона, см. ниже|
|*lpszMenuName*|не используется (должен иметь значение NULL)|
|*lpszClassName*|Имя класса, см. ниже|

## <a name="provided-wndclasses"></a>Предоставленный WNDCLASSes

Более ранних версиях MFC (MFC 4.0), предоставляются несколько предопределенных классов окон. Эти классы окон больше не предоставляются по умолчанию. Приложения должны использовать `AfxRegisterWndClass` с соответствующими параметрами.

Если приложение предоставляет ресурс с указанным Идентификатором ресурса (например, AFX_IDI_STD_FRAME), MFC использует этот ресурс. В противном случае он будет использовать стандартный ресурс. Для значка используется значок стандартного приложения, и для курсора, используется стандартная стрелка курсор.

Два значка поддержки приложений MDI с типами одного документа: один значок для основного приложения, другие значок преобразованного в значок документа/MDIChild windows. Для нескольких типов документов с помощью разных значков, необходимо зарегистрировать дополнительные `WNDCLASS`es или используйте [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) функции.

`CFrameWnd::LoadFrame` Регистрирует `WNDCLASS` используется идентификатор значка, можно указать в качестве первого параметра и следующие стандартные атрибуты:

- стиль класса: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- значок AFX_IDI_STD_FRAME

- курсор в виде стрелки

- Цвет фона COLOR_WINDOW

Значения цвета фона и курсор для [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) не используются с момента клиентской области `CMDIFrameWnd` полностью **MDICLIENT** окна. Майкрософт не поддерживается создание подклассов **MDICLIENT** окно, поэтому используйте стандартные цвета и типы курсоров, если это возможно.

## <a name="subclassing-and-superclassing-controls"></a>Подклассы и создание надклассов элементов управления

Если вы подкласс или суперкласса Windows элемента управления (например, [CButton](../mfc/reference/cbutton-class.md)) затем класс автоматически получает `WNDCLASS` атрибутов, предоставляемых в Windows реализация этого элемента управления.

## <a name="the-afxregisterwndclass-function"></a>Afxregisterwndclass-функция

MFC предоставляет вспомогательную функцию для регистрации класса окна. Определенный набор атрибутов (стили класса окна, курсор, кисть фона и значок), создается имени синтетические и результирующий класс окна зарегистрирован. Например, примененная к объекту директива

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Эта функция возвращает временной строки от имени созданного окна зарегистрированного класса. Дополнительные сведения об этой функции см. в разделе [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Возвращаемая строка является временный указатель на буфер, статическая строка. Он является допустимым до следующего вызова `AfxRegisterWndClass`. Если вы хотите сохранить эту строку вокруг, сохраните его в [CString](../atl-mfc-shared/using-cstring.md) переменной, как в следующем примере:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` вызывает исключение [CResourceException](../mfc/reference/cresourceexception-class.md) Если класс окна не удалось зарегистрировать (из-за неправильных параметров, или недостаточно памяти Windows).

## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass и AfxRegisterClass функции

Если вы хотите сделать что-то более сложными. чем `AfxRegisterWndClass` предоставляет, можно вызвать Windows API `RegisterClass` или функции MFC `AfxRegisterClass`. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` функции принимают *lpszClassName* строковое имя для класса окна в качестве первого параметра. Можно использовать любое имя класса окна зарегистрированных, независимо от метода, который использовался для его регистрации.

Очень важно использовать `AfxRegisterClass` (или `AfxRegisterWndClass`) в библиотеке DLL на Win32. Win32 не может отменить регистрацию автоматически классы, которые зарегистрированы с DLL, поэтому необходимо явно отменить регистрацию классов при завершении библиотеки DLL. С помощью `AfxRegisterClass` вместо `RegisterClass` это выполняется автоматически. `AfxRegisterClass` хранит список уникальные классы, зарегистрированные для библиотеки DLL и автоматически отменять их при завершении работы библиотеки DLL. При использовании `RegisterClass` в библиотеке DLL, необходимо убедиться, что все классы не зарегистрированы, при завершении библиотеки DLL (в вашей [DllMain](/windows/desktop/Dlls/dllmain) функции). Невыполнение этого требования может привести к `RegisterClass` неожиданному сбою, если другой клиентское приложение пытается использовать библиотеки DLL.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)

