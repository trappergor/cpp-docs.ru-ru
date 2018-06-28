---
title: CMDIChildWnd-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 037a6091f11ad12a8f4e46ccb837c48f1f9a685b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040851"
---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd-класс
Предоставляет функции дочернего окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Создает объект `CMDIChildWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|Создает дочернее окно MDI-приложения Windows, связанные с `CMDIChildWnd` объекта.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Возвращает родительский клиентское MDI окно рамки MDI.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Активирует этого дочернего окна MDI.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Удаляет этот дочернего окна MDI.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Развертывает это дочернее окно MDI.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Восстанавливает это дочернее окно MDI из развернутого или свернутого размер.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Задает дескрипторы для ресурсов меню и сочетаний клавиш.|  
  
## <a name="remarks"></a>Примечания  
 Дочернего окна MDI похож типичный фрейме окна, за исключением того, дочернее окно MDI-приложения отображается в окне фрейма MDI, а не на рабочем столе. Дочернего окна MDI не имеет свои собственные строки меню, но вместо этого использует меню окна фрейма MDI. Платформа автоматически изменяет меню фрейма MDI для представления дочернее окно текущего активного интерфейса MDI.  
  
 Чтобы создать полезные дочернее окно MDI для приложения, создайте класс, производный от `CMDIChildWnd`. Добавьте переменные-члены в производный класс для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Для создания дочернего окна MDI тремя способами:  
  
-   Непосредственно создать его с помощью `Create`.  
  
-   Непосредственно создать его с помощью `LoadFrame`.  
  
-   Косвенно составить через шаблон документа.  
  
 Перед вызовом метода `Create` или `LoadFrame`, необходимо создать объект окна фрейма в куче, с помощью C++ **новый** оператор. Перед вызовом метода `Create` можно также зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции, чтобы задать значок и класс стили рамки.  
  
 Используйте `Create` функции-члена для передачи как интерпретации аргументов параметры создания фрейма.  
  
 `LoadFrame` требуется меньшее количество аргументов, чем `Create`и вместо этого извлекает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицу сочетаний клавиш и меню опорного кадра. Чтобы быть доступным, `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Если `CMDIChildWnd` объект содержит представления и документы, они создаются неявно платформой вместо программистом. `CDocTemplate` Объект организует Создание фрейма, создания представлений, содержащих и соединение представлений в соответствующий документ. Параметры `CDocTemplate` укажите конструктор `CRuntimeClass` из трех классов участвующих (документа, фрейма и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, задаваемых пользователем (например, с помощью команды создания файла или команду создания окна MDI).  
  
 Окна фрейма класс, производный от `CMDIChildWnd` должны быть объявлены с `DECLARE_DYNCREATE` в порядке для указанных выше `RUNTIME_CLASS` механизм для правильной работы.  
  
 `CMDIChildWnd` Класс наследует большую часть его реализация по умолчанию из `CFrameWnd`. Подробный список этих функций можно найти [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIChildWnd` Класс имеет следующие дополнительные возможности:  
  
-   В сочетании с `CMultiDocTemplate` класса, несколько `CMDIChildWnd` объекты из одного шаблона документа используют то же меню, сохранение системных ресурсов Windows.  
  
-   Текущий активный дочернего окна меню MDI полностью заменяет меню Окно области MDI и заголовок дочернее окно текущего активного интерфейса MDI добавляется заголовок окна фрейма MDI. Примеры MDI дочернего окна функций, реализованных в сочетании с окном фрейма MDI см `CMDIFrameWnd` Описание класса.  
  
 Не используйте C++ **удалить** оператор для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow`. `CFrameWnd` Реализация `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, значение по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CMDIChildWnd`, в разделе [фреймов](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd  
 Вызов для создания `CMDIChildWnd` объекта.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите **создать** создание видимого окна.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMDIChildWnd::Create](#create).  
  
##  <a name="create"></a>  CMDIChildWnd::Create  
 Вызовите эту функцию-член для создания дочернего окна Windows MDI и присоединить его к `CMDIChildWnd` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszClassName*  
 Указывает строку символом null, с именем класса Windows ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры). Имя класса может быть любое имя, зарегистрированное в [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальной функции. Должно быть **NULL** для стандартного `CMDIChildWnd`.  
  
 *lpszWindowName*  
 Указатель на завершающуюся значением null строка, представляющая имя окна. Использовать в качестве текста для заголовка окна.  
  
 *dwStyle*  
 Задает окно [стиль](../../mfc/reference/styles-used-by-mfc.md#window-styles) атрибуты. **WS_CHILD** стиль.  
  
 *Rect*  
 Содержит размер и положение окна. `rectDefault` Значение позволяет Windows указать размер и положение нового `CMDIChildWnd`.  
  
 *pParentWnd*  
 Указывает родительского окна. Если **NULL**, используемый в главное окно приложения.  
  
 *pContext*  
 Указывает [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Текущий активный кадр дочернюю MDI можно определить заголовок родительское окно фрейма. Эта функция отключена, отключив **FWS_ADDTOTITLE** бит стиля дочернего окна фрейма.  
  
 Платформа вызывает эту функцию-член в ответ на команду пользователя, чтобы создать дочернее окно, и платформа использует *pContext* параметра для правильного подключения дочернего окна приложения. При вызове `Create`, *pContext* может быть **NULL**.  
  
### <a name="example"></a>Пример  
 Пример 1.  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Пример  
 Пример 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame  
 Эта функция вызывается для возврата родительского фрейма MDI.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на родительское окно фрейма MDI.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый кадр является два родительских удалены из `CMDIChildWnd` и является родителем окна типа **MDICLIENT** , управляющий `CMDIChildWnd` объекта. Вызовите [GetParent](../../mfc/reference/cwnd-class.md#getparent) функция-член для возврата `CMDIChildWnd` этого объекта немедленно **MDICLIENT** родительский элемент в качестве временного `CWnd` указателя.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate  
 Вызовите эту функцию-член для активации дочернего окна MDI независимо от окно области MDI.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Примечания  
 Когда кадр становится активным, также будут активированы дочернее окно, последний раз была активирована.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy  
 Вызовите эту функцию-член уничтожении дочернего окна MDI.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член удаляет заголовок дочернего окна из окна фрейма и деактивирует дочернего окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize  
 Вызовите эту функцию-член для максимизации дочернего окна MDI.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Примечания  
 Когда развернуто дочернее окно Windows изменяет его, чтобы изменения клиентской области заполнения клиентской области окна фрейма. Windows размещает дочернего окна элемента управления меню в строке меню фрейма, чтобы пользователь мог восстановить или закрыть дочернее окно и добавляет заголовок дочернего окна с заголовком окна фрейма.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore  
 Вызовите эту функцию-член для восстановления из развернутого или свернутого размера дочернего окна MDI.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles  
 Задает дескрипторы для ресурсов меню и сочетаний клавиш.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Параметры  
 *hMenu*  
 Дескриптор ресурса меню.  
  
 *hAccel*  
 Дескриптор ресурса сочетаний клавиш.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию для задания меню и сочетаний клавиш ресурсы, используемые объектом дочерние окна MDI.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Пример MFC MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)
