---
title: Класс Кмфктулбаредитбоксбуттон
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
ms.openlocfilehash: 3e988d789ca6a038ce41bca829850f6509fd9df1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504727"
---
# <a name="cmfctoolbareditboxbutton-class"></a>Класс Кмфктулбаредитбоксбуттон

Кнопка на панели инструментов, содержащая элемент управления "поле ввода" ( [класс CEdit](../../mfc/reference/cedit-class.md)).

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кмфктулбаредитбоксбуттон:: Кмфктулбаредитбоксбуттон](#cmfctoolbareditboxbutton)|Создает объект `CMFCToolBarEditBoxButton`.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кмфктулбаредитбоксбуттон:: Канбестретчед](#canbestretched)|Указывает, может ли пользователь растянуть кнопку во время настройки. (Переопределяет [CMFCToolBarButton:: канбестретчед](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[Кмфктулбаредитбоксбуттон:: CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов в текущую кнопку. (Переопределяет [CMFCToolBarButton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::`[Кмфктулбаредитбоксбуттон:: креатидит](#createedit)|Создает новый элемент управления "поле ввода" в кнопке.|
|`CMFCToolBarEditBoxButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[Кмфктулбаредитбоксбуттон:: Жетбикмд](#getbycmd)|Извлекает из приложения `CMFCToolBarEditBoxButton` первый объект с указанным идентификатором команды.|
|[Кмфктулбаредитбоксбуттон:: Жетконтентсалл](#getcontentsall)|Извлекает текст первого элемента управления ToolBar панели инструментов, имеющего указанный идентификатор команды.|
|[Кмфктулбаредитбоксбуттон:: Жетконтекстменуид](#getcontextmenuid)|Возвращает идентификатор ресурса контекстного меню, связанного с кнопкой.|
|[Кмфктулбаредитбоксбуттон:: Жетедитбордер](#geteditborder)|Извлекает ограничивающий прямоугольник в части кнопки "Изменить".|
|`CMFCToolBarEditBoxButton::`[Кмфктулбаредитбоксбуттон:: жетедитбокс](#geteditbox)|Возвращает указатель на элемент управления "поле ввода", внедренный в кнопку.|
|[Кмфктулбаредитбоксбуттон:: "HWND"](#gethwnd)|Получает маркер окна, связанный с кнопкой панели инструментов. (Переопределяет [CMFCToolBarButton::-HWND](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[Кмфктулбаредитбоксбуттон:: Жетинвалидатерект](#getinvalidaterect)|Извлекает область клиентской области кнопки, которую необходимо перерисовать. (Переопределяет [CMFCToolBarButton:: жетинвалидатерект](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|
|`CMFCToolBarEditBoxButton::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфктулбаредитбоксбуттон:: Хавехотбордер](#havehotborder)|Определяет, отображается ли граница кнопки при нажатии пользователем кнопки. (Переопределяет [CMFCToolBarButton:: хавехотбордер](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[Кмфктулбаредитбоксбуттон:: Исфлатмоде](#isflatmode)|Определяет, имеют ли кнопки поля редактирования плоский стиль.|
|[Кмфктулбаредитбоксбуттон:: Нотификомманд](#notifycommand)|Указывает, обрабатывает ли кнопка сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) . (Переопределяет [CMFCToolBarButton:: нотификомманд](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[Кмфктулбаредитбоксбуттон:: Онаддтокустомизепаже](#onaddtocustomizepage)|Вызывается структурой при добавлении кнопки в диалоговое окно " **Настройка** ". (Переопределяет [CMFCToolBarButton:: онаддтокустомизепаже](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Вызывается платформой для вычисления размера кнопки для указанного контекста устройства и состояния закрепления. (Переопределяет [CMFCToolBarButton:: онкалкулатесизе](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[Кмфктулбаредитбоксбуттон:: Ончанжепарентвнд](#onchangeparentwnd)|Вызывается структурой при вставке кнопки в новую панель инструментов. (Переопределяет [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[Кмфктулбаредитбоксбуттон:: OnClick](#onclick)|Вызывается структурой при нажатии пользователем кнопки мыши. (Переопределяет [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[Кмфктулбаредитбоксбуттон:: Онктлколор](#onctlcolor)|Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_CTLCOLOR. (Переопределяет [CMFCToolBarButton:: онктлколор](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Вызывается платформой для рисования кнопки с использованием указанных стилей и параметров. (Переопределяет [CMFCToolBarButton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Вызывается платформой для нарисовании кнопки в области **команды** диалогового окна " **Настройка** ". (Переопределяет [CMFCToolBarButton:: ондравонкустомизелист](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[Кмфктулбаредитбоксбуттон:: Онглобалфонтсчанжед](#onglobalfontschanged)|Вызывается платформой при изменении глобального шрифта. (Переопределяет [CMFCToolBarButton:: онглобалфонтсчанжед](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[Кмфктулбаредитбоксбуттон:: OnMove](#onmove)|Вызывается структурой при перемещении родительской панели инструментов. (Переопределяет [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[Кмфктулбаредитбоксбуттон:: onShow](#onshow)|Вызывается структурой, когда кнопка станет видимой или невидимой. (Переопределяет [CMFCToolBarButton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[Кмфктулбаредитбоксбуттон:: OnSize](#onsize)|Вызвано структурой при изменении размера или расположения родительской панели инструментов, и это изменение приводит к изменению размера кнопки. (Переопределяет [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[Кмфктулбаредитбоксбуттон:: Онупдатетултип](#onupdatetooltip)|Вызывается структурой, когда родительская панель инструментов обновляет текст подсказки. (Переопределяет [CMFCToolBarButton:: онупдатетултип](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Считывает этот объект из архива или записывает его в архив. (Переопределяет [CMFCToolBarButton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Заполняет предоставленный `CAccessibilityData` объект данными специальных возможностей из кнопки панели инструментов. (Переопределяет [CMFCToolBarButton:: сетаккдата](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::`[Кмфктулбаредитбоксбуттон:: сетконтентс](#setcontents)|Задает текст в элементе управления "поле ввода" кнопки.|
|`CMFCToolBarEditBoxButton::`[Кмфктулбаредитбоксбуттон:: сетконтентсалл](#setcontentsall)|Выполняет поиск кнопки элемента управления "Правка" с указанным ИДЕНТИФИКАТОРом команды и задает текст в элементе управления "поле ввода" для этой кнопки.|
|[Кмфктулбаредитбоксбуттон:: Сетконтекстменуид](#setcontextmenuid)|Указывает идентификатор ресурса контекстного меню, связанного с кнопкой.|
|[Кмфктулбаредитбоксбуттон:: Сетфлатмоде](#setflatmode)|Задает плоский внешний вид кнопок поля ввода в приложении.|
|`CMFCToolBarEditBoxButton::`[Кмфктулбаредитбоксбуттон:: SetStyle](#setstyle)|Задает стиль кнопки. (Переопределяет [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Примечания

Чтобы добавить кнопку поля ввода на панель инструментов, выполните следующие действия.

1. Зарезервируйте идентификатор фиктивного ресурса для кнопки на родительском ресурсе панели инструментов.

2. `CMFCToolBarEditBoxButton` Создайте объект.

3. В обработчике сообщений, который обрабатывает сообщение AFX_WM_RESETTOOLBAR, замените фиктивную кнопку новой кнопкой со списком с помощью [CMFCToolBar:: реплацебуттон](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Дополнительные сведения см. в разделе [Пошаговое руководство: Размещение элементов управления на](../../mfc/walkthrough-putting-controls-on-toolbars.md)панелях инструментов.

## <a name="example"></a>Пример

В приведенном ниже примере демонстрируется использование различных методов класса `CMFCToolBarEditBoxButton` . В примере показано, как указать, что пользователь может растянуть кнопку во время настройки, указать, что граница кнопки отображается при нажатии пользователем кнопки, задать текст в элементе управления "текстовое поле", задать плоский внешний вид кнопок редактирования в приложения сположение и укажите стиль элемента управления "поле ввода" панели инструментов.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Требования

**Заголовок:** афкстулбаредитбоксбуттон. h

##  <a name="canbestretched"></a>Кмфктулбаредитбоксбуттон:: Канбестретчед

Указывает, может ли пользователь растянуть кнопку во время настройки.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает значение TRUE.

### <a name="remarks"></a>Примечания

По умолчанию платформа не позволяет пользователю растянуть кнопку на панели инструментов во время настройки. Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: канбестретчед](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), позволяя пользователю растянуть кнопку панели инструментов поля ввода во время настройки.

##  <a name="cmfctoolbareditboxbutton"></a>Кмфктулбаредитбоксбуттон:: Кмфктулбаредитбоксбуттон

Конструирует объект [кмфктулбаредитбоксбуттон](../../mfc/reference/cmfctoolbareditboxbutton-class.md) .

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
окне Указывает идентификатор элемента управления.

*иимаже*<br/>
окне Указывает отсчитываемый от нуля индекс изображения панели инструментов. Изображение находится в объекте [класса кмфктулбаримажес](../../mfc/reference/cmfctoolbarimages-class.md) , который обслуживает класс класса [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) .

*двстиле*<br/>
окне Задает стиль элемента управления Edit.

*ивидс*<br/>
окне Задает ширину элемента управления "поле ввода" в пикселях.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию устанавливает стиль элемента управления Edit в следующую комбинацию:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Ширина элемента управления по умолчанию составляет 150 пикселей.

##  <a name="copyfrom"></a>Кмфктулбаредитбоксбуттон:: CopyFrom

Копирует свойства другой кнопки панели инструментов в текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
окне Ссылка на кнопку источника, из которой производится копирование.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен иметь тип `CMFCToolBarEditBoxButton`.

##  <a name="createedit"></a>Кмфктулбаредитбоксбуттон:: Креатидит

Создает новый элемент управления "поле ввода" в кнопке.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Задает родительское окно элемента управления "поле ввода". Оно не должно иметь значение NULL.

*rect*<br/>
окне Задает размер и расположение элемента управления "поле ввода".

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный элемент управления "поле ввода"; имеет значение NULL, если создание и вложение элемента управления завершилось ошибкой.

### <a name="remarks"></a>Примечания

`CMFCToolBarEditBoxButton` Объект создается в два этапа. Сначала вызовите конструктор, а затем вызовите метод `CreateEdit`, который создает элемент управления Windows Edit и присоединяет его `CMFCToolBarEditBoxButton` к объекту.

##  <a name="getbycmd"></a>Кмфктулбаредитбоксбуттон:: Жетбикмд

Извлекает из приложения `CMFCToolBarEditBoxButton` первый объект с указанным идентификатором команды.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор команды для извлечения.

### <a name="return-value"></a>Возвращаемое значение

Первый `CMFCToolBarEditBoxButton` объект в приложении с указанным идентификатором команды или значение null, если такой объект не существует.

### <a name="remarks"></a>Примечания

Этот общий служебный метод используется такими методами, как [кмфктулбаредитбоксбуттон:: сетконтентсалл](#setcontentsall) и [Кмфктулбаредитбоксбуттон:: жетконтентсалл](#getcontentsall) , для установки или получения текста первого элемента управления ToolBar панели инструментов, имеющего указанный идентификатор команды.

##  <a name="getcontentsall"></a>Кмфктулбаредитбоксбуттон:: Жетконтентсалл

Извлекает текст первого элемента управления ToolBar панели инструментов, имеющего указанный идентификатор команды.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор команды для получения содержимого.

### <a name="return-value"></a>Возвращаемое значение

`CString` Объект, содержащий текст первого элемента управления ToolBar панели инструментов, имеющего указанный идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод возвращает пустую строку, если `CMFCToolBarEditBoxButton` ни один из объектов не имеет указанного идентификатора команды.

##  <a name="getcontextmenuid"></a>Кмфктулбаредитбоксбуттон:: Жетконтекстменуид

Возвращает идентификатор ресурса контекстного меню, связанного с кнопкой.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса контекстного меню, связанного с кнопкой, или 0, если кнопка не имеет связанного контекстного меню.

### <a name="remarks"></a>Примечания

Платформа использует идентификатор ресурса для создания контекстного меню, когда пользователь щелкает правой кнопкой мыши кнопку.

##  <a name="geteditborder"></a>Кмфктулбаредитбоксбуттон:: Жетедитбордер

Извлекает ограничивающий прямоугольник в части кнопки "Изменить".

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Параметры

*ректбордер*<br/>
заполняет Ссылка на `CRect` объект, который получает ограничивающий прямоугольник.

### <a name="remarks"></a>Примечания

Этот метод получает ограничивающий прямоугольник элемента управления "поле ввода" в клиентских координатах. Он расширяет размер прямоугольника в каждом направлении на один пиксель.

Метод [CMFCVisualManager:: ондраведитбордер](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) вызывает этот метод при рисовании границы вокруг `CMFCToolBarEditBoxButton` объекта.

##  <a name="geteditbox"></a>Кмфктулбаредитбоксбуттон:: Жетедитбокс

Возвращает указатель на элемент управления [класса CEdit](../../mfc/reference/cedit-class.md) , внедренный в кнопку.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент управления [класса CEdit](../../mfc/reference/cedit-class.md) , который содержит кнопка. Если элемент управления еще не `CEdit` создан, он имеет значение null.

### <a name="remarks"></a>Примечания

Чтобы создать `CEdit` элемент управления, вызовите [кмфктулбаредитбоксбуттон:: креатидит](#createedit).

##  <a name="gethwnd"></a>Кмфктулбаредитбоксбуттон:: "HWND"

Получает маркер окна, связанный с кнопкой панели инструментов.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Возвращаемое значение

Маркер окна, связанный с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод переопределяет метод [CMFCToolBarButton::](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) getHandler, возвращая дескриптор окна элемента управления "поле ввода" кнопки "Изменить".

##  <a name="getinvalidaterect"></a>Кмфктулбаредитбоксбуттон:: Жетинвалидатерект

Извлекает область клиентской области кнопки, которую необходимо перерисовать.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Возвращаемое значение

`CRect` Объект, указывающий регион, который необходимо перерисовать.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [CMFCToolBarButton:: жетинвалидатерект](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), включая в области область Метки текста.

##  <a name="havehotborder"></a>Кмфктулбаредитбоксбуттон:: Хавехотбордер

Определяет, отображается ли граница кнопки при нажатии пользователем кнопки.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если при выборе кнопки отображается ее граница. в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [CMFCToolBarButton:: хавехотбордер](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), возвращая ненулевое значение, если элемент управления является видимым.

##  <a name="isflatmode"></a>Кмфктулбаредитбоксбуттон:: Исфлатмоде

Определяет, имеют ли кнопки поля редактирования плоский стиль.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопки имеют плоский стиль; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

По умолчанию кнопки поля редактирования имеют плоский стиль. Используйте метод [кмфктулбаредитбоксбуттон:: сетфлатмоде](#setflatmode) , чтобы изменить внешний вид неструктурированного стиля для приложения.

##  <a name="notifycommand"></a>Кмфктулбаредитбоксбуттон:: Нотификомманд

Указывает, обрабатывает ли кнопка сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) .

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Параметры

*инотификоде*<br/>
окне Сообщение уведомления, связанное с командой.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка обрабатывает сообщение WM_COMMAND, или значение FALSE, чтобы указать, что сообщение должно быть обработано родительской панелью инструментов.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, когда отправляет сообщение [WM_COMMAND](/windows/win32/menurc/wm-command) в родительское окно.

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: нотификомманд](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) путем обработки уведомления [EN_UPDATE](/windows/win32/Controls/en-update) . Для каждого поля редактирования, имеющего тот же идентификатор команды, что и этот объект, он устанавливает в качестве текстовой метки текстовую метку этого объекта.

##  <a name="onaddtocustomizepage"></a>Кмфктулбаредитбоксбуттон:: Онаддтокустомизепаже

Вызывается структурой при добавлении кнопки в диалоговое окно " **Настройка** ".

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онаддтокустомизепаже](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) путем копирования свойств элемента управления "поле ввода" на любой панели инструментов, которая имеет тот же идентификатор команды, что и этот объект. Этот метод не выполняет никаких действий, если ни одна панель инструментов не содержит элемент управления "поле ввода", имеющий тот же идентификатор команды, что и этот объект.

Дополнительные сведения о диалоговом окне « **Настройка** » см. в разделе [класс кмфктулбарскустомизедиалог](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>Кмфктулбаредитбоксбуттон:: Ончанжепарентвнд

Вызывается структурой при вставке кнопки в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Указатель на новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: ончанжепарентвнд](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) путем повторного создания внутреннего `CEdit` объекта.

##  <a name="onclick"></a>Кмфктулбаредитбоксбуттон:: OnClick

Вызывается структурой при нажатии пользователем кнопки мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
окне Использующ.

*бделай*<br/>
окне Использующ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если кнопка обрабатывает сообщение щелчка; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), возвращая ненулевое значение, `CEdit` если внутренний объект является видимым.

##  <a name="onctlcolor"></a>Кмфктулбаредитбоксбуттон:: Онктлколор

Вызывается структурой, когда родительская панель инструментов обрабатывает сообщение WM_CTLCOLOR.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
окне Контекст устройства, на котором отображается кнопка.

*нктлколор*<br/>
окне Использующ.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор кисти глобального окна.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса ( [CMFCToolBarButton:: онктлколор](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), устанавливая цвет текста и фона предоставленного контекста устройства на глобальный цвет текста и фона соответственно.

Дополнительные сведения о глобальных параметрах, доступных для приложения, см. в разделе [Структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>Кмфктулбаредитбоксбуттон:: Онглобалфонтсчанжед

Вызывается платформой при изменении глобального шрифта.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онглобалфонтсчанжед](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)), изменяя шрифт элемента управления на цвет из глобального шрифта.

Дополнительные сведения о глобальных параметрах, доступных для приложения, см. в разделе [Структура AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>Кмфктулбаредитбоксбуттон:: OnMove

Вызывается структурой при перемещении родительской панели инструментов.

```
virtual void OnMove();
```

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию ( [CMFCToolBarButton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), обновляя положение внутреннего `CEdit` объекта

##  <a name="onshow"></a>Кмфктулбаредитбоксбуттон:: onShow

Вызывается структурой, когда кнопка станет видимой или невидимой.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
окне Указывает, является ли кнопка видимой. Если этот параметр имеет значение TRUE, кнопка является видимой. В противном случае кнопка не отображается.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton::](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)onShow), отображая кнопку, если *БШОВ* имеет значение true. В противном случае этот метод скрывает кнопку.

##  <a name="onsize"></a>Кмфктулбаредитбоксбуттон:: OnSize

Вызвано структурой при изменении размера или расположения родительской панели инструментов, и это изменение приводит к изменению размера кнопки.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Параметры

*исизе*<br/>
окне Новая ширина кнопки в пикселях.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию класса по умолчанию [CMFCToolBarButton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), обновляя размер и расположение внутреннего `CEdit` объекта.

##  <a name="onupdatetooltip"></a>Кмфктулбаредитбоксбуттон:: Онупдатетултип

Вызывается структурой, когда родительская панель инструментов обновляет текст подсказки.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Параметры

*пвндпарент*<br/>
окне Использующ.

*ибуттониндекс*<br/>
окне Использующ.

*вндтултип*<br/>
окне Элемент управления, отображающий текст подсказки.

*str*<br/>
заполняет `CString` Объект, получающий обновленный текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод обновляет текст подсказки; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса ( [CMFCToolBarButton:: онупдатетултип](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), отображая текст подсказки, связанный с частью редактирования кнопки. Если внутренний `CEdit` объект имеет значение null или маркер `CEdit` окна объекта не определяет существующее окно, этот метод не выполняет никаких действий и возвращает значение false.

##  <a name="setcontents"></a>Кмфктулбаредитбоксбуттон:: Сетконтентс

Задает текст в элементе управления "текстовое поле".

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Параметры

*сконтентс*<br/>
окне Задает новый заданный текст.

##  <a name="setcontentsall"></a>Кмфктулбаредитбоксбуттон:: Сетконтентсалл

Находит объект [кмфктулбаредитбоксбуттон](../../mfc/reference/cmfctoolbareditboxbutton-class.md) с указанным идентификатором команды и задает указанный текст в текстовом поле.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Указывает идентификатор команды элемента управления, для которого будет изменен текст.

*стрконтентс*<br/>
окне Задает новый заданный текст.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если текст был задан; 0, `CMFCToolBarEditBoxButton` если элемент управления с указанным идентификатором команды не существует.

##  <a name="setcontextmenuid"></a>Кмфктулбаредитбоксбуттон:: Сетконтекстменуид

Указывает идентификатор ресурса контекстного меню, связанного с кнопкой.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Параметры

*уикмд*<br/>
окне Идентификатор ресурса контекстного меню.

### <a name="remarks"></a>Примечания

Платформа использует идентификатор ресурса для создания контекстного меню, когда пользователь щелкает правой кнопкой мыши кнопку панели инструментов.

##  <a name="setflatmode"></a>Кмфктулбаредитбоксбуттон:: Сетфлатмоде

Задает плоский внешний вид кнопок поля ввода в приложении.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Параметры

*бфлат*<br/>
окне Плоский стиль для кнопок поля ввода. Если этот параметр имеет значение TRUE, вид плоского стиля включен; в противном случае внешний вид неструктурированного стиля отключается.

### <a name="remarks"></a>Примечания

Для кнопок поля ввода по умолчанию используется плоский стиль, равный TRUE. Используйте метод [кмфктулбаредитбоксбуттон:: исфлатмоде](#isflatmode) , чтобы получить плоский внешний вид для приложения.

##  <a name="setstyle"></a>Кмфктулбаредитбоксбуттон:: SetStyle

Задает стиль элемента управления "поле ввода" панели инструментов.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Параметры

*нстиле*<br/>
окне Новый стиль для задания.

### <a name="remarks"></a>Примечания

Этот метод задает [CMFCToolBarButton:: m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) для *нстиле* он также отключает текстовое поле, когда приложение находится в режиме настройки, и включает его, если приложение не находится в режиме настройки (см [. раздел CMFCToolBar:: сеткустомиземоде](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) и [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Список допустимых флагов стиля см. в разделе [стили элементов управления панели инструментов](../../mfc/reference/toolbar-control-styles.md) .

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar:: Реплацебуттон](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство: Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
