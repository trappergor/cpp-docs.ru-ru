---
title: Класс CMFCToolBarEditBoxButton
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: bf71bb508bf0327a7fdf34b128bdb825323cd3a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525727"
---
# <a name="cmfctoolbareditboxbutton-class"></a>Класс CMFCToolBarEditBoxButton

Кнопки панели инструментов, содержащий элемент управления редактированием ( [класс CEdit](../../mfc/reference/cedit-class.md)).

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Создает объект `CMFCToolBarEditBoxButton`.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Указывает, может ли пользователь растянуть кнопки во время настройки. (Переопределяет [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Копирует свойства другую кнопку панели инструментов для текущей кнопки. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Создает новый элемент управления кнопки.|
|`CMFCToolBarEditBoxButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении с указанным идентификатором команды.|
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Получает текст элемента управления панели инструментов первого изменения с указанным идентификатором команды.|
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Получает идентификатор ресурса в контекстном меню, связанный с кнопкой.|
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Получает прямоугольник, ограничивающий части изменить поле "Изменить".|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Возвращает указатель на поле ввода, которое внедрено в кнопке.|
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Извлекает дескриптор окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Извлекает область клиентской области кнопки, которую необходимо перерисовать. (Переопределяет [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Определяет, отображается ли граница кнопки, когда пользователь нажимает кнопку. (Переопределяет [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Определяет, имеют ли поле кнопки изменения плоский стиль.|
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Указывает, обрабатывает ли кнопки [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщения. (Переопределяет [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для заданного контекста устройств и состояние закрепления. (Переопределяет [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается платформой при вставке кнопки в панели инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Вызывается платформой, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Вызывается платформой, когда родительский инструментов обрабатывает wm_ctlcolor-сообщение. (Переопределяет [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Вызывается платформой для отрисовки кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Вызывается платформой для отрисовки кнопки **команды** области **Настройка** диалоговое окно. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Вызывается платформой при изменении глобального шрифта. (Переопределяет [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Вызывается платформой при перемещении родительской панели инструментов. (Переопределяет [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Вызывается платформой при кнопка становится видимым или невидимым. (Переопределяет [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Вызывается платформой при панели родительского изменении ее размера или положения и это изменение приводит к изменить размер кнопки. (Переопределяет [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Вызывается платформой, когда родительский инструментов обновляет его текст подсказки. (Переопределяет [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Заполняет предоставленный `CAccessibilityData` объект с данные специальных возможностей с помощью кнопки панели инструментов. (Переопределяет [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|Задает текст в элементе управления кнопки.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Находит «изменить» элемента управления, имеет заданный идентификатор команды, который задает текст в элементе управления этой кнопки.|
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Указывает идентификатор ресурса в контекстном меню, связанный с кнопкой.|
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Задает плоский внешний вид кнопок поле редактирования в приложении.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Задает стиль кнопки. (Переопределяет [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Примечания

Чтобы добавить поле кнопка «Изменить» на панель инструментов, выполните следующие действия.

1. Зарезервируйте идентификатор фиктивный ресурс для кнопки в панели инструментов к родительскому ресурсу.

2. Создать `CMFCToolBarEditBoxButton` объекта.

3. В обработчике сообщений, который обрабатывает сообщение AFX_WM_RESETTOOLBAR, заменить фиктивные кнопку "Создать поле" поле со списком с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md).

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarEditBoxButton` . В примере для указания, что пользователь можно растянуть кнопки во время настройки, указать, что граница кнопки отображается, когда пользователь нажимает кнопку, текст в элементе текстового поля, указать плоский внешний вид для кнопки поле изменения в приложения Проверка подлинности и укажите в поле редактирования стиль панели инструментов.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbareditboxbutton.h

##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched

Указывает, может ли пользователь растянуть кнопки во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию платформа позволяет пользователю выполнить растяжение кнопки панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопку панели инструментов поле редактирования во время настройки.

##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton

Создает [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объекта.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
[in] Указывает идентификатор элемента управления.

*iImage*<br/>
[in] Указывает отсчитываемый от нуля индекс изображения панели инструментов. Образ находится в [класс CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта, [класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) класс поддерживает.

*dwStyle*<br/>
[in] Указывает стиль редактирования элемента управления.

*iWidth*<br/>
[in] Задает ширину в пикселях элемента управления.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию устанавливает стиль элемента управления редактирования следующие комбинации:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Ширина элемента управления по умолчанию — 150 пикселей.

##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom

Копирует свойства другую кнопку панели инструментов для текущей кнопки.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Ссылка «источник» из которого необходимо скопировать.

### <a name="remarks"></a>Примечания

Этот метод используется для копирования другую кнопку панели инструментов, чтобы эта кнопка панели инструментов. *src* должен иметь тип `CMFCToolBarEditBoxButton`.

##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit

Создает новый элемент управления кнопки.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Указывает родительского окна элемента управления. Он не должен иметь значение NULL.

*Rect*<br/>
[in] Задает размер и положение элемента управления поля ввода.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный редактирования элемента управления; возвращается значение NULL, если сбой создания элемента управления и вложения.

### <a name="remarks"></a>Примечания

При создании `CMFCToolBarEditBoxButton` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `CreateEdit`, который создает элемент управления Windows и присоединяет его к `CMFCToolBarEditBoxButton` объекта.

##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd

Извлекает первый `CMFCToolBarEditBoxButton` объект в приложении с указанным идентификатором команды.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды для получения кнопки.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarEditBoxButton` объект в приложении, имеющий заданный идентификатор команды, или значение NULL, если объект не существует.

### <a name="remarks"></a>Примечания

Этот метод служебной программы используется методами, такими как [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) и [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) для задания или получения текст на первой панели инструментов поле редактирования элемент управления с указанным идентификатором команды.

##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll

Получает текст элемента управления панели инструментов первого изменения с указанным идентификатором команды.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор команды, кнопки, из которого необходимо извлечь содержимое.

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий текст элемента управления панели инструментов первого изменения с указанным идентификатором команды.

### <a name="remarks"></a>Примечания

Этот метод возвращает пустую строку, если не `CMFCToolBarEditBoxButton` объекты имеют идентификатор указанной команды.

##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID

Получает идентификатор ресурса в контекстном меню, связанный с кнопкой.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса, связанный с кнопкой, или 0, если кнопка имеет связанный контекстное меню не контекстного меню.

### <a name="remarks"></a>Примечания

Инфраструктура использует идентификатор ресурса для создания в контекстном меню, когда пользователь щелкает правой кнопкой мыши на кнопке.

##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder

Получает прямоугольник, ограничивающий части изменить поле "Изменить".

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Параметры

*rectBorder*<br/>
[out] Ссылку на `CRect` объект, получающий ограничивающего прямоугольника.

### <a name="remarks"></a>Примечания

Этот метод извлекает ограничивающий прямоугольник элемента управления редактированием в координатах клиентской области окна. Он расширяет размер прямоугольника в каждом направлении на один пиксель.

[CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) метод вызывается этот метод при рисовании границы вокруг `CMFCToolBarEditBoxButton` объекта.

##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox

Возвращает указатель на [класс CEdit](../../mfc/reference/cedit-class.md) элемент управления, который внедряется в кнопке.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [класс CEdit](../../mfc/reference/cedit-class.md) элемент управления, содержащий кнопку. Он принимает значение NULL, если `CEdit` еще не был создан элемент управления.

### <a name="remarks"></a>Примечания

Создании `CEdit` элемента управления, используя [CMFCToolBarEditBoxButton::CreateEdit](#createedit).

##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd

Извлекает дескриптор окна, связанный с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор окна, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод переопределяет [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) метода, возвращая дескриптор окна элемента управления edit части поле "Изменить".

##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect

Извлекает область клиентской области кнопки, которую необходимо перерисовать.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CRect` , указывающий область, необходимо перерисовать.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), путем включения в регионе области текста метки.

##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder

Определяет, отображается ли граница кнопки, когда пользователь нажимает кнопку.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка отображает граница при выборе; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), возвращая ненулевое значение, если элемент управления является видимым.

##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode

Определяет, имеют ли поле кнопки изменения плоский стиль.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки имеют плоский; в противном случае — 0.

### <a name="remarks"></a>Примечания

По умолчанию поле кнопки изменения имеют плоский стиль. Используйте [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) метод, чтобы изменить стиль плоского представления для вашего приложения.

##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand

Указывает, обрабатывает ли кнопки [WM_COMMAND](/windows/desktop/menurc/wm-command) сообщения.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*iNotifyCode*<br/>
[in] Сообщение уведомления, который связан с командой.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопки обрабатывает сообщение WM_COMMAND, или FALSE для указания, что сообщения должны обрабатываться родительской панели инструментов.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда он собирается отправить [WM_COMMAND](/windows/desktop/menurc/wm-command) родительское окно.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)), обрабатывая [EN_UPDATE](/windows/desktop/Controls/en-update) уведомлений. Для каждого поля ввода с таким же Идентификатором команды, что и этот объект он задает его текст метки текстовую метку этого объекта.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage

Вызывается платформой при добавлении кнопки **Настройка** диалоговое окно.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) путем копирования из поля ввода в любой панели инструментов, который имеет тот же идентификатор команды, что и данный объект свойства. Если нет панель инструментов содержит элемент управления поля редактирования, имеет тот же идентификатор команды, что и этот объект, этот метод не выполняет никаких действий.

Дополнительные сведения о **Настройка** диалоговом окне см. в разделе [класс CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd

Вызывается платформой при вставке кнопки в панели инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Указатель на нового родительского окна.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), повторно создав внутренний `CEdit` объекта.

##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick

Вызывается платформой, когда пользователь нажимает кнопку мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Не используется.

*bDelay*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки обрабатывает сообщение щелкните; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), возвращая ненулевое значение, если внутренний `CEdit` объект является видимым.

##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor

Вызывается платформой, когда родительский инструментов обрабатывает wm_ctlcolor-сообщение.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
[in] Контекст устройства, которое отображает кнопки.

*nCtlColor*<br/>
[in] Не используется.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор к кисти глобального окна.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), задав цвета текста и фона контекста устройства, предоставленный глобальный текста и фона, соответственно.

Дополнительные сведения о глобальных параметров, доступных для приложения, см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged

Вызывается платформой при изменении глобального шрифта.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) путем изменения шрифта элемента управления, глобальные шрифта.

Дополнительные сведения о глобальных параметров, доступных для приложения, см. в разделе [структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove

Вызывается платформой при перемещении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновив позицию внутреннего `CEdit` объекта

##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow

Вызывается платформой при кнопка становится видимым или невидимым.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
[in] Указывает, видима ли кнопка. Если этот параметр имеет значение TRUE, то кнопка отображается. В противном случае кнопка не видна.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)), отображая кнопку, если *bShow* имеет значение TRUE. В противном случае этот метод скрывает кнопку.

##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize

Вызывается платформой при панели родительского изменении ее размера или положения и это изменение приводит к изменить размер кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*iSize*<br/>
[in] Новая ширина кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), обновив размер и положение внутреннего `CEdit` объекта.

##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip

Вызывается платформой, когда родительский инструментов обновляет его текст подсказки.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
[in] Не используется.

*iButtonIndex*<br/>
[in] Не используется.

*wndToolTip*<br/>
[in] Элемент управления, отображающий текст всплывающей подсказки.

*str*<br/>
[out] Объект `CString` объект, получающий обновленный подсказку.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод обновляет текст подсказки; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, который связан с редактирования части кнопки. Если внутренний `CEdit` объект имеет значение NULL или дескриптор `CEdit` объекта не определяет существующему окну, этот метод не выполняет никаких действий и возвращает значение FALSE.

##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents

Задает текст в элементе текстового поля.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Параметры

*sContents*<br/>
[in] Указывает новый текст для задания.

##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll

Находит [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) объект, который имеет заданный идентификатор команды и задает указанный текст в пределах соответствующего текстового поля.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Указывает идентификатор команды элемента управления, для которого будет изменен текст.

*strContents*<br/>
[in] Указывает новый текст для задания.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текст был задан; 0, если `CMFCToolBarEditBoxButton` элемента управления с помощью указанного идентификатора команды не существует.

##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID

Указывает идентификатор ресурса в контекстном меню, связанный с кнопкой.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
[in] Идентификатор ресурса в контекстном меню.

### <a name="remarks"></a>Примечания

Инфраструктура использует идентификатор ресурса для создания в контекстном меню при щелчке кнопки панели инструментов.

##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode

Задает плоский внешний вид кнопок поле редактирования в приложении.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Параметры

*bFlat*<br/>
[in] Плоский стиль кнопки поля редактирования. Если этот параметр имеет значение TRUE, включен плоский внешний вид; в противном случае плоский внешний вид отключен.

### <a name="remarks"></a>Примечания

Плоский стиль по умолчанию для кнопки изменения поле имеет значение TRUE. Используйте [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) метод для извлечения плоский внешний вид для вашего приложения.

##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle

Задает стиль панели инструментов редактирования поля элемента управления.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*nStyle*<br/>
[in] Чтобы задать новый стиль.

### <a name="remarks"></a>Примечания

Этот метод задает [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) для *nStyle* он также отключает текстовое поле, когда приложение находится в режиме настройки и включает его, если приложение не находится в режиме настройки (см. [ CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) и [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). См. в разделе [стили элемента управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) список флагов допустимое значение стиля.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)

