---
title: "Класс CMiniFrameWnd | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd class
- mini-frame windows
- toolbars [C++]
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 7a7119a7317e8837c7ce672b2607a4e37b5239f5
ms.lasthandoff: 03/31/2017

---
# <a name="cminiframewnd-class"></a>Класс CMiniFrameWnd
Представляет фреймовое окно половинной высоты по сравнению с тем, которое стандартно отображается на плавающих панелях инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Создает объект `CMiniFrameWnd`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|Создает `CMiniFrameWnd` объект после создания экземпляра.|  
|[CMiniFrameWnd::CreateEx](#createex)|Создает `CMiniFrameWnd` объекта (с дополнительными параметрами) после построения.|  
  
## <a name="remarks"></a>Примечания  
 Эти окна ведут себя как обычный фреймов, за исключением того, что они не имеют свернуть или развернуть кнопки или меню и вам необходимо только одним щелчком в системном меню, чтобы закрыть их.  
  
 Для использования `CMiniFrameWnd` объекта, сначала Определите объект. Затем вызовите [создать](#create) функции-члена для отображения окна области.  
  
 Дополнительные сведения об использовании `CMiniFrameWnd` объектов, см. в статье [стыковка и плавающей панели инструментов](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 Создает `CMiniFrameWnd` объекта, но не удалось создать окно.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Для создания окна, вызовите [CMiniFrameWnd::Create](#create).  
  
##  <a name="create"></a>CMiniFrameWnd::Create  
 Создает окно области Windows и прикрепляет его к `CMiniFrameWnd` объекта.  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `lpClassName`  
 Указывает строку символом null, с именем класса Windows. Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) функции. Если **NULL**, класс окна будет зарегистрирована автоматически платформой. MFC предоставляет класса по умолчанию следующие атрибуты и стили:  
  
-   Задает стиль бит **CS_DBLCLKS**, которая отправляет дважды щелкните сообщения в процедуру при двойном щелчке мыши.  
  
-   Задает стиль bits **CS_HREDRAW** и **CS_VREDRAW**, который прямое содержимое клиентской области перерисовку при изменении размера окна.  
  
-   Задает класс курсор к стандарту Windows **IDC_ARROW**.  
  
-   Задает класс кисть фона **NULL**, поэтому не удалит его фона окна.  
  
-   Задает значок класса стандартные, нетерпеливых флаг значка логотипа Windows.  
  
-   Задает окна по умолчанию размер и положение, как указано в Windows.  
  
 `lpWindowName`  
 Указатель на завершающуюся значением null строка, содержащая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. Они могут включать стили стандартное окно и один или несколько из следующих специальных стилей:  
  
- **MFS_MOVEFRAME** позволяет переместить, щелкнув любой границы окна, не только заголовок окна области.  
  
- **MFS_4THICKFRAME** отключает изменение размера окна области.  
  
- **MFS_SYNCACTIVE** синхронизирует активации окна области для активации родительского окна.  
  
- **MFS_THICKFRAME** позволяет соответствовать требованиям малой разрешить содержимое клиентской области окна области.  
  
- **MFS_BLOCKSYSMENU** запрещают доступ к меню системы и элемента управления меню и преобразует их в часть заголовка (заголовок).  
  
 В разделе [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание значений стилей окон невозможно. Типичные сочетание, используемый для окна **WS_POPUP | WS_CAPTION | WS_SYSMENU**.  
  
 `rect`  
 Объект `RECT` структуры, указав нужные размеры окна.  
  
 `pParentWnd`  
 Указатель на родительское окно. Используйте **NULL** для окон верхнего уровня.  
  
 `nID`  
 Если окно области создается как дочернего окна, это идентификатор дочернего элемента управления; в противном случае — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Создание** инициализирует окна имя класса и имя окна и регистрирует значения по умолчанию для его стиль и родительского элемента.  
  
##  <a name="createex"></a>CMiniFrameWnd::CreateEx  
 Создает объект `CMiniFrameWnd`.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Задает расширенный стиль `CMiniFrameWnd` создается. Применить любой из [расширенные стили окна](../../mfc/reference/extended-window-styles.md) окна.  
  
 `lpClassName`  
 Указывает строку завершающуюся значением null, с именем класса Windows ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры). Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) функции или какие-либо имена предопределенных класс элемента управления. Он не должен быть **NULL**.  
  
 `lpWindowName`  
 Указатель на завершающуюся значением null строка, содержащая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. В разделе [стили окна](../../mfc/reference/window-styles.md) и [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание возможных значений.  
  
 `rect`  
 Размер и положение окна в клиентские координаты `pParentWnd`.  
  
 `pParentWnd`  
 Указывает объект родительского окна.  
  
 `nID`  
 Идентификатор дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 `CreateEx` Параметры определяют **WNDCLASS**, стиль окна и (необязательно) начальное положение и размер окна. `CreateEx`также указывает окна родительского (если таковые имеются) и идентификатор.  
  
 Когда `CreateEx` выполняет Windows отправляет [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) сообщения в окно.  
  
 Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CMiniFrameWnd`, добавить схему сообщений к новому классу, а функции-члены для сообщениях выше. Переопределить `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Переопределить дальнейшей **на***сообщение* обработчиков для обеспечения дополнительной функциональности производного класса сообщений.  
  
 Если **WS_VISIBLE** задан стиль, Windows посылает окне все необходимые для активации и отображение окна сообщения. Если стиль окна указывает строку заголовка, заголовок окна указывает `lpszWindowName` параметр отображается в заголовке окна.  
  
 `dwStyle` Параметр может иметь любое сочетание [стили окна](../../mfc/reference/window-styles.md).  
  
 Старый стиль windows элементов палитры больше не поддерживаются. Старый стиль, который не имел кнопки «X» закрыть, поддерживались при запуске приложения MFC в предыдущих версиях Windows, но больше не поддерживается в Visual C++ .NET. Только новые `WS_EX_TOOLWINDOW` стиль теперь поддерживается; описание этого стиля см. в разделе [расширенные стили окна](../../mfc/reference/extended-window-styles.md).  
  
## <a name="see-also"></a>См. также  
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)

