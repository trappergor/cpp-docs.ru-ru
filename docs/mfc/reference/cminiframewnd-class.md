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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1229f5405c9eeb90abcdc54108ed26e28d94f0e0
ms.lasthandoff: 02/24/2017

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
|[CMiniFrameWnd::CreateEx](#createex)|Создает `CMiniFrameWnd` объект (с дополнительными параметрами) после создания экземпляра.|  
  
## <a name="remarks"></a>Примечания  
 Эти окна минифрейма ведут себя как обычный фрейм окна, за исключением того, что они не имеют кнопки свертывания/развертывания окна или меню и вам необходимо только одним щелчком системное меню, чтобы закрыть их.  
  
 Для использования `CMiniFrameWnd` объекта, сначала определить объект. Затем вызовите [создать](#create) функции-члена для отображения окна области.  
  
 Дополнительные сведения об использовании `CMiniFrameWnd` объектов, см. в статье [закрепления и плавающей панели инструментов](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecminiframewnda--cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 Создает `CMiniFrameWnd` объекта, но не удалось создать окно.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы создать окно, вызовите [CMiniFrameWnd::Create](#create).  
  
##  <a name="a-namecreatea--cminiframewndcreate"></a><a name="create"></a>CMiniFrameWnd::Create  
 Окна области Windows создает и присоединяет его к `CMiniFrameWnd` объекта.  
  
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
 Указывает строку символом null, что имена классов Windows. Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) функции. Если **NULL**, класс окна регистрируется для вас платформой. MFC предоставляет класс по умолчанию следующие стили и атрибуты:  
  
-   Задает стиль бит **CS_DBLCLKS**, которая отправляет дважды щелкнуть сообщение процедуре окна, при двойном щелчке мыши.  
  
-   Задает стиль bits **CS_HREDRAW** и **CS_VREDRAW**, который прямое содержимое клиентской области перерисовку при изменении размера окна.  
  
-   Задает класс курсор стандарта Windows **IDC_ARROW**.  
  
-   Задает кисть фона класса **NULL**, поэтому окна не удалит его задний план.  
  
-   Задает значок класса стандартные, роли отметок флага значок логотипа Windows.  
  
-   Задает окно положение и размер по умолчанию, обозначенный в Windows.  
  
 `lpWindowName`  
 Указывает символ нулем строка, содержащая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. Они могут включать стили стандартное окно и один или несколько из следующих специальных стилей:  
  
- **MFS_MOVEFRAME** позволяет окна области для перемещения, щелкнув любой края окна, не только заголовок.  
  
- **MFS_4THICKFRAME** отключает изменение размера окна области.  
  
- **MFS_SYNCACTIVE** синхронизирует активации окна области для активации родительского окна.  
  
- **MFS_THICKFRAME** позволяет окна области выйдет небольшой разрешить содержимое клиентской области.  
  
- **MFS_BLOCKSYSMENU** запрещают доступ к меню «система» и меню для элемента управления и преобразует их в рамках caption (заголовок).  
  
 В разделе [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание значений стилей возможных окон. Типичный комбинация, используемая для windows минифрейма, **WS_POPUP | WS_CAPTION | WS_SYSMENU**.  
  
 `rect`  
 A `RECT` структуры, указав нужные размеры окна.  
  
 `pParentWnd`  
 Указывает для родительского окна. Используйте **NULL** для окон верхнего уровня.  
  
 `nID`  
 Если окна области создается как дочернего окна, это идентификатор дочернего элемента управления; в противном случае — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 **Создание** инициализирует окна имя класса и имя окна и регистрирует значения по умолчанию для его стиль и родительским.  
  
##  <a name="a-namecreateexa--cminiframewndcreateex"></a><a name="createex"></a>CMiniFrameWnd::CreateEx  
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
 Указывает на строку символом null, что имена классов Windows ( [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры). Имя класса может быть любое имя, зарегистрированное с глобальным [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) функции или какие-либо имена предопределенных класс элемента управления. Оно не должно быть **NULL**.  
  
 `lpWindowName`  
 Указывает символ нулем строка, содержащая имя окна.  
  
 `dwStyle`  
 Задает атрибуты стилей окна. В разделе [стили окна](../../mfc/reference/window-styles.md) и [CWnd::Create](../../mfc/reference/cwnd-class.md#create) описание возможных значений.  
  
 `rect`  
 Размер и положение окна в координатах клиента из `pParentWnd`.  
  
 `pParentWnd`  
 Указывает объект родительского окна.  
  
 `nID`  
 Идентификатор дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `CreateEx` Параметры задают **WNDCLASS**, стиль окна и (при необходимости) начальное положение и размер окна. `CreateEx`также указывает в окне родительский (если есть) и идентификатор.  
  
 Когда `CreateEx` выполняет Windows отправляет [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), и [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) сообщения в окно.  
  
 Чтобы расширить возможности обработки сообщений по умолчанию, создайте класс, производный от `CMiniFrameWnd`, Добавление нового класса схемы сообщений и обеспечивает функции-члены выше сообщений. Переопределение `OnCreate`, например, для выполнения инициализации, необходимые для нового класса.  
  
 Переопределение дальнейшей **на***сообщения* обработчиков для добавления функций в производном классе сообщений.  
  
 Если **WS_VISIBLE** задан стиль, Windows отправляет окну все необходимые для активации и отображение окна сообщения. Если стиль окна указывает заголовок окна, заголовок окна указывает `lpszWindowName` параметр отображается в строке заголовка.  
  
 `dwStyle` Параметр может иметь любое сочетание [стили окна](../../mfc/reference/window-styles.md).  
  
 Старый стиль windows элементов палитры больше не поддерживаются. При запуске приложения MFC в предыдущих версиях Windows, поддерживаемой старого стиля, которое не было кнопка закрытия «X», но больше не поддерживается в Visual C++ .NET. Только новые `WS_EX_TOOLWINDOW` стиль теперь поддерживается; описание этого стиля см. в разделе [расширенные стили окна](../../mfc/reference/extended-window-styles.md).  
  
## <a name="see-also"></a>См. также  
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)

