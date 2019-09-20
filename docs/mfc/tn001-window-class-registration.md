---
title: 'TN001: Регистрация класса окна'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: 95e35ddd6f55c955bc2adb7b4db2460ae84a6dc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513544"
---
# <a name="tn001-window-class-registration"></a>TN001: Регистрация класса окна

В этом заметке описываются подпрограммы MFC, регистрирующие специальные [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw)ES, необходимые для Microsoft Windows. Обсуждаются определенные `WNDCLASS` атрибуты, используемые MFC и Windows.

## <a name="the-problem"></a>Проблема

Атрибуты объекта [CWnd](../mfc/reference/cwnd-class.md) , такие как `HWND` обработчик в Windows, хранятся в двух местах: объекте `WNDCLASS`Window и. Имя `WNDCLASS` передается в функции создания окон общего вида, такие как [CWnd:: Create](../mfc/reference/cwnd-class.md#create) и [CFrameWnd:: Create](../mfc/reference/cframewnd-class.md#create) в параметре *лпсзкласснаме* .

Это `WNDCLASS` должно быть зарегистрировано одним из четырех способов:

- Неявно с помощью предоставленного `WNDCLASS`MFC.

- Неявным образом путем подкласса элемента управления Windows (или другого элемента управления).

- Явным образом, вызвав MFC [афксрегистервндкласс](../mfc/reference/application-information-and-management.md#afxregisterwndclass) или [афксрегистеркласс](../mfc/reference/application-information-and-management.md#afxregisterclass).

- Явно, вызвав подпрограммы Windows [registerClass](/windows/win32/api/winuser/nf-winuser-registerclassw).

## <a name="wndclass-fields"></a>Поля ВНДКЛАСС

`WNDCLASS` Структура состоит из различных полей, описывающих класс окна. В следующей таблице показаны поля и указано, как они используются в приложении MFC.

|Поле|Описание|
|-----------|-----------------|
|*лпфнвндпрок*|оконная процедура, должна быть`AfxWndProc`|
|*кбклсекстра*|не используется (должно быть равно нулю)|
|*кбвндекстра*|не используется (должно быть равно нулю)|
|*hInstance*|автоматически заполняется [афксжетинстанцехандле](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|
|*hIcon*|значок для окон фрейма см. ниже|
|*хкурсор*|курсор для времени, когда указатель мыши наведен на окно, см. ниже|
|*хбрбаккграунд*|цвет фона, см. ниже|
|*лпсзменунаме*|не используется (должно быть NULL)|
|*лпсзкласснаме*|имя класса, см. ниже|

## <a name="provided-wndclasses"></a>Предоставлено Вндклассес

Более ранние версии MFC (до MFC 4,0) предоставляли несколько предопределенных классов окон. Эти классы окон больше не предоставляются по умолчанию. Приложения должны использовать `AfxRegisterWndClass` с соответствующими параметрами.

Если приложение предоставляет ресурс с указанным ИДЕНТИФИКАТОРом ресурса (например, AFX_IDI_STD_FRAME), MFC будет использовать этот ресурс. В противном случае будет использоваться ресурс по умолчанию. Для значка используется стандартный значок приложения, и для курсора используется стандартный курсор со стрелкой.

Два значка поддерживают MDI-приложения с одним типом документа: один значок для основного приложения, второй — для значка Document/Мдичилд Windows. Для нескольких типов документов с разными значками необходимо зарегистрировать дополнительные `WNDCLASS`ES или использовать функцию [CFrameWnd:: лоадфраме](../mfc/reference/cframewnd-class.md#loadframe) .

`CFrameWnd::LoadFrame`будет регистрироваться `WNDCLASS` с использованием идентификатора значка, указанного в качестве первого параметра, и следующих стандартных атрибутов:

- стиль класса: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- значок AFX_IDI_STD_FRAME

- курсор со стрелкой

- Цвет фона COLOR_WINDOW

Значения цвета фона и курсора для [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) не используются, так как клиентская область элемента `CMDIFrameWnd` полностью охватывается окном **мдиклиент** . Корпорация Майкрософт не рекомендует подклассировать окно **мдиклиент** , поэтому по возможности используйте стандартные цвета и типы курсоров.

## <a name="subclassing-and-superclassing-controls"></a>Подклассировать и классы элементов управления

Если подкласс или суперкласс является элементом управления Windows (например, [кбуттон](../mfc/reference/cbutton-class.md)), то класс автоматически получает `WNDCLASS` атрибуты, предоставленные в реализации Windows этого элемента управления.

## <a name="the-afxregisterwndclass-function"></a>Функция Афксрегистервндкласс

MFC предоставляет вспомогательную функцию для регистрации класса окна. При наличии набора атрибутов (стиль класса окна, курсор, фоновая кисть и значок) создается искусственное имя и регистрируется результирующий класс окна. Например, примененная к объекту директива

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Эта функция возвращает временную строку созданного имени класса зарегистрированного окна. Дополнительные сведения об этой функции см. в разделе [афксрегистервндкласс](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Возвращаемая строка является временным указателем на статический строковый буфер. Он действителен до следующего вызова `AfxRegisterWndClass`. Если вы хотите сохранить эту строку вокруг, сохраните ее в переменной [CString](../atl-mfc-shared/using-cstring.md) , как показано в следующем примере:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass`вызовет исключение [кресаурцеексцептион](../mfc/reference/cresourceexception-class.md) , если не удалось зарегистрировать класс окна (из-за неверных параметров или из-за нехватки памяти Windows).

## <a name="the-registerclass-and-afxregisterclass-functions"></a>Функции RegisterClass и Афксрегистеркласс

Если вы хотите сделать что-то более сложное `AfxRegisterWndClass` , чем предоставляемое, можно вызвать API `RegisterClass` Windows или функцию `AfxRegisterClass`MFC. Функции `CWnd`,[CFrameWnd](../mfc/reference/cframewnd-class.md) and [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` принимают в качестве первого параметра имя *lpszClassName* строки для класса Window. Можно использовать любое имя зарегистрированного класса окна, независимо от метода, который вы использовали для его регистрации.

В библиотеке DLL в Win32 `AfxRegisterClass` важно использовать `AfxRegisterWndClass`(или). Win32 не выполняет автоматическую отмену регистрации классов, зарегистрированных в библиотеке DLL, поэтому при завершении работы библиотеки необходимо явно отменить регистрацию классов. При использовании `AfxRegisterClass` `RegisterClass` вместо этого выполняется автоматическая обработка. `AfxRegisterClass`поддерживает список уникальных классов, зарегистрированных в библиотеке DLL, и автоматически отменяет их регистрацию при завершении работы библиотеки DLL. При использовании `RegisterClass` в библиотеке DLL необходимо обеспечить отмену регистрации всех классов при завершении работы библиотеки DLL (в функции [DllMain](/windows/win32/Dlls/dllmain) ). В противном случае это может `RegisterClass` привести к непредвиденному сбою, если другое клиентское приложение пытается использовать вашу библиотеку DLL.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
