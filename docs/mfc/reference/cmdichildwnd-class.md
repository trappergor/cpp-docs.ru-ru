---
title: "Класс CMDIChildWnd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWnd
dev_langs:
- C++
helpviewer_keywords:
- MDI [C++], child windows
- windows [C++], MDI
- CMDIChildWnd class
- child windows, CMDIChildWnd class
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 240af1fe5f3afa4cdb7d4d585dc74cc4836799cc
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd-класс
Предоставляет функции дочернего окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Создает объект `CMDIChildWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|Создает дочернего окна Windows MDI, связанные с `CMDIChildWnd` объекта.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Возвращает родительский объект фрейма MDI клиентского окна MDI.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Активирует этого дочернего окна MDI.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Удаляет этот дочернего окна MDI.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Увеличивает этот дочернего окна MDI.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Восстановление этого дочернего окна MDI из развернутой или свернутой размер.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Задает маркеры для ресурсов меню и сочетаний клавиш.|  
  
## <a name="remarks"></a>Примечания  
 У дочернего окна MDI похож типичный фрейме окна, за исключением того, что дочернее окно MDI-приложения отображается в окне фрейма MDI, а не на рабочем столе. У дочернего окна MDI имеет свои собственные строки меню, но вместо этого использует меню Окно области MDI. Платформа автоматически изменяет меню фрейма MDI для представления дочернее окно текущего активного интерфейса MDI.  
  
 Чтобы создать полезные дочернего окна MDI в приложении, создайте класс, производный от `CMDIChildWnd`. Добавьте переменные-члены для производного класса для хранения данных, относящихся к конкретному приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.  
  
 Для создания дочернего окна MDI тремя способами:  
  
-   Непосредственно создавать его с помощью **создать**.  
  
-   Непосредственно создавать его с помощью `LoadFrame`.  
  
-   Косвенно создайте его через шаблон документа.  
  
 Перед вызовом метода **создать** или `LoadFrame`, необходимо создать объект фреймового окна в куче C++ с помощью **новый** оператор. Перед вызовом метода **создать** можно также зарегистрировать класс окна с [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) глобальные функции для установки значок и класс стили рамки.  
  
 Используйте **создать** для передачи параметров создания фрейма как интерпретации аргументов функции-члена.  
  
 `LoadFrame`требуется меньшее число аргументов, чем **создать**и вместо этого получает большую часть значений по умолчанию из ресурсов, включая заголовок, значок, таблицы сочетаний клавиш и меню фрейма. Должны быть доступны `LoadFrame`, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, **IDR_MAINFRAME**).  
  
 Если `CMDIChildWnd` объект содержит представления и документы, они создаются неявно платформой вместо программистом. `CDocTemplate` Объект организует Создание рамки, создавать представления, содержащего и подключение представлений для соответствующих документов. Параметры `CDocTemplate` конструктор указывать `CRuntimeClass` трех классов участвующих (документа, рамки и представления). Объект `CRuntimeClass` объект используется платформой для динамического создания новых кадров, задаваемых пользователем (например, с помощью команды новый файл или нового окна MDI).  
  
 Окна фрейма класс, производный от `CMDIChildWnd` должны быть объявлены с `DECLARE_DYNCREATE` в порядке для указанных выше `RUNTIME_CLASS` механизм для правильной работы.  
  
 `CMDIChildWnd` Класс наследует большую часть реализацию по умолчанию от `CFrameWnd`. Подробный список этих функций можно найти [CFrameWnd](../../mfc/reference/cframewnd-class.md) Описание класса. `CMDIChildWnd` Класс имеет следующие дополнительные возможности:  
  
-   В сочетании с `CMultiDocTemplate` класса, несколько `CMDIChildWnd` объекты из одного шаблона документа используют то же меню, сохранение системных ресурсов Windows.  
  
-   Активный дочернего окна меню MDI полностью заменяет меню Окно области MDI и заголовок дочернее окно текущего активного MDI добавляется заголовок окна фрейма MDI. Примеры MDI дочернего окна функций, реализованных в сочетании с окне фрейма MDI см `CMDIFrameWnd` Описание класса.  
  
 Не используйте C++ **удаление** оператор уничтожении окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow` . `CFrameWnd` Реализацию `PostNcDestroy` приведет к удалению объекта C++ при уничтожении окна. Когда пользователь закрывает окно области по умолчанию `OnClose` обработчик вызовет `DestroyWindow`.  
  
 Дополнительные сведения о `CMDIChildWnd`, в разделе [окна фрейма](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecmdichildwnda--cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd  
 Вызов для создания `CMDIChildWnd` объекта.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов **создать** создание видимого окна.  
  
### <a name="example"></a>Пример  
  В примере показано [CMDIChildWnd::Create](#create).  
  
##  <a name="a-namecreatea--cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd::Create  
 Вызов этой функции-члена для создания дочернего окна Windows MDI и присоединить его к `CMDIChildWnd` объекта.  
  
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
 `lpszClassName`  
 Указывает на строку символом null, что имена классов Windows ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры). Имя класса может быть любое имя, зарегистрированное в [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) глобальной функции. Должно быть **NULL** для стандартного `CMDIChildWnd`.  
  
 `lpszWindowName`  
 Указывает символ нулем строка, представляющая имя окна. Использовать как текст строки заголовка.  
  
 `dwStyle`  
 Задает окно [стиль](../../mfc/reference/window-styles.md) атрибуты. **WS_CHILD** стиля является обязательным.  
  
 `rect`  
 Содержит размер и положение окна. `rectDefault` Значение позволяет указать размер и положение нового Windows `CMDIChildWnd`.  
  
 `pParentWnd`  
 Указывает родительского окна. Если **NULL**, используется главного окна приложения.  
  
 `pContext`  
 Указывает [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) структуры. Этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Активный кадр дочернюю MDI можно определить заголовок окна родительского фрейма. Эта функция отключена, отключив **FWS_ADDTOTITLE** бит стиля рамки дочернего окна.  
  
 Платформа вызывает эту функцию-член в ответ на команды пользователя для создания дочернего окна и инфраструктура использует `pContext` параметр для правильного подключения дочернее окно приложения. При вызове **создать**, `pContext` может быть **NULL**.  
  
### <a name="example"></a>Пример  
 Пример 1.  
  
 [!code-cpp[NVC_MFCWindowing&#7;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Пример  
 Пример 2:  
  
 [!code-cpp[NVC_MFCWindowing №&8;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing №&9;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="a-namegetmdiframea--cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame  
 Эта функция вызывается для возврата родительского фрейма MDI.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель кадра родительского окна MDI.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемые кадр является два родительских удалены из `CMDIChildWnd` и является родительским для окна типа **MDICLIENT** , управляющий `CMDIChildWnd` объекта. Вызов [GetParent](../../mfc/reference/cwnd-class.md#getparent) функция-член для возврата `CMDIChildWnd` этого объекта немедленно **MDICLIENT** родительский элемент в качестве временного `CWnd` указателя.  
  
### <a name="example"></a>Пример  
  В примере показано [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="a-namemdiactivatea--cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd::MDIActivate  
 Вызовите эту функцию-член для активации дочернего окна MDI независимо от окно области MDI.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Примечания  
 Когда кадр становится активным, также будут активированы дочернее окно, последний раз была активирована.  
  
### <a name="example"></a>Пример  
  В примере показано [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="a-namemdidestroya--cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy  
 Вызовите эту функцию-член для уничтожения дочернего окна MDI.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член удаляет заголовок дочернего окна в окне фрейма и деактивирует дочернего окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#10;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="a-namemdimaximizea--cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize  
 Вызовите эту функцию-член для максимизации дочернего окна MDI.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Примечания  
 Если дочернее окно развернуто, Windows изменяет его, чтобы сделать свою клиентскую область заполнил клиентскую область окна фрейма. Windows размещает элемент управления меню дочернего окна в строке меню фрейма, чтобы пользователь мог восстановить или закрытия дочернего окна и добавляет заголовок дочернего окна с заголовком окна фрейма.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&11;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="a-namemdirestorea--cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd::MDIRestore  
 Вызовите эту функцию-член для восстановления из развернутой или свернутой размер дочернего окна MDI.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#12;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="a-namesethandlesa--cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd::SetHandles  
 Задает маркеры для ресурсов меню и сочетаний клавиш.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Параметры  
 `hMenu`  
 Дескриптор ресурса меню.  
  
 `hAccel`  
 Дескриптор ресурса сочетаний клавиш.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для ресурсов меню и сочетаний клавиш, используемых дочернего окна MDI объекта набора.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [MFC примера MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd-класс](../../mfc/reference/cmdiframewnd-class.md)

