---
title: CMFCDesktopAlertWnd Class
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: 3ff74f5025d888077b51f8191f043237597dfdbe
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776977"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

`CMFCDesktopAlertWnd` Класс реализует функциональные возможности немодальное диалоговое окно, которое отображается на экране, чтобы информировать пользователей о событии.

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCDesktopAlertWnd::Create](#create)|Создает и инициализирует окно оповещения.|
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Возвращает скорость анимации.|
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|Возвращает тип анимации.|
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Возвращает время ожидания автоматическое закрытие.|
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Возвращает высоту заголовка.|
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Возвращает позицию последнего допустимым окно оповещения на экране.|
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|Возвращает уровень прозрачности.|
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Определяет, отображается ли окно оповещения с помощью маленького заголовка.|
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Вызывается платформой по нажатию кнопки ссылки на меню рабочего стола оповещения.|
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|Эта функция-член вызывается платформой, когда пользователь выбирает элемент меню, когда дочерний элемент управления отправляет сообщение уведомления, или при переводе сочетания клавиш. (Переопределяет [CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Задает новый скорость анимации.|
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|Задает тип анимации.|
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Задает время ожидания автоматическое закрытие.|
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Переключение между малого и обычный субтитры.|
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|Задает уровень прозрачности.|

## <a name="remarks"></a>Примечания

Окно оповещения может быть прозрачным, он может присутствовать анимационными эффектами, и он может исчезнуть (после истечения указанной задержки или когда пользователь закрывает его, нажав кнопку "Закрыть").

Окно оповещения также могут содержать диалоговое окно по умолчанию, который в свою очередь содержит значок, текст сообщения (метки) и ссылку. Кроме того окно оповещения может содержать настраиваемое диалоговое окно из ресурсов приложения.

Создать окно оповещения в два этапа. Во-первых, вызовите конструктор для создания `CMFCDesktopAlertWnd` объекта. Во-вторых, вызовите [CMFCDesktopAlertWnd::Create](#create) функцию-член для создания окна и присоединить его к `CMFCDesktopAlertWnd` объекта.

`CMFCDesktopAlertWnd` Объект создает специальные дочерние диалоговое окно, которое заполняет клиентскую область окна классических оповещений. Диалоговое окно является владельцем всех элементов управления, расположенные на нем.

Чтобы отобразить пользовательские диалоговые окна во всплывающем окне, выполните следующие действия.

1. Создайте производный класс от класса `CMFCDesktopAlertDialog`.

1. Создайте шаблон дочернего диалогового окна в ресурсах.

1. Вызовите [CMFCDesktopAlertWnd::Create](#create) используется идентификатор ресурса шаблона диалогового окна и указатель на сведения о классе среды выполнения производного класса.

1. Программировать пользовательские диалоговые окна для обработки всех уведомлений, поступающих от размещенных элементов управления, или размещенные элементы управления для обработки этих уведомлений напрямую.

Следующие функции используются для управления поведением окно оповещения:

- Задать тип анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype). Допустимые значения: раскрыть и слайд эффект затухания.

- Задать скорость кадров анимации, вызвав [CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed).

- Задать уровень прозрачности, вызвав [CMFCDesktopAlertWnd::SetTransparency](#settransparency).

- Изменить размер заголовка к меньшему, вызвав [CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption). Меньшего заголовка — 7 пикселов в высоту.

## <a name="example"></a>Пример

Следующий пример демонстрирует использование различных методов `CMFCDesktopAlertWnd` класс для настройки `CMFCDesktopAlertWnd` объекта. В примере показано, как задать тип анимации, прозрачность всплывающее окно, укажите, что окно оповещения отображает малого заголовка и время, по истечении автоматически закрывает окно оповещения. В примере также как создать и инициализировать окно оповещения. Этот фрагмент кода является частью [Desktop оповещения демонстрационного](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDesktopAlertWnd.h

##  <a name="create"></a>  CMFCDesktopAlertWnd::Create

Создает и инициализирует окно оповещения.

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>Параметры

*pWndOwner*<br/>
[in, out] Указывает владельца окна оповещения. Этот владелец будет получать все уведомления для окно оповещения. Это значение не может иметь значение NULL.

*uiDlgResID*<br/>
[in] Указывает идентификатор ресурса окно оповещения.

*hMenu*<br/>
[in] Указывает меню, которое отображается при нажатии кнопки меню. Если значение равно NULL, кнопка меню не отображается.

*ptPos*<br/>
[in] Определяет исходную позицию, где отображается окно оповещения, с помощью координат экрана. Если этот параметр (-1, -1), окно оповещения, отображается в правом нижнем углу экрана.

*pRTIDlgBar*<br/>
[in] Сведения о классе среды выполнения для класса пользовательского диалогового окна, охватывающую клиентской области окна оповещения.

*params*<br/>
[in] Указывает параметры, которые используются для создания окне оповещения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно оповещения был создан успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для создания окне оповещения. Клиентской области окна оповещений содержит дочерние диалоговое окно, которое содержит все элементы управления, которые отображаются для пользователя.

По первой перегрузке метода создает окне оповещения, содержащий дочерний диалоговое окно, которое загружается из ресурсов приложения. По первой перегрузке метода можно также указать сведения о классе среды выполнения для класса пользовательского диалогового окна.

Вторая перегрузка метода создает окне оповещения, содержащий элементы управления по умолчанию. Можно указать, какие элементы управления должны отображаться, изменив [класс CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).

##  <a name="getanimationspeed"></a>  CMFCDesktopAlertWnd::GetAnimationSpeed

Возвращает скорость анимации.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Скорость анимации окно оповещения, в миллисекундах.

### <a name="remarks"></a>Примечания

Скорость анимации описывает, как быстро открывает окно оповещения и закрывает.

##  <a name="getanimationtype"></a>  CMFCDesktopAlertWnd::GetAnimationType

Возвращает тип анимации.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Возвращаемое значение

Один из следующих типов анимации:

- NO_ANIMATION

- UNFOLD

- СЛАЙД

- ИСЧЕЗАНИЕ

- SYSTEM_DEFAULT_ANIMATION

##  <a name="getautoclosetime"></a>  CMFCDesktopAlertWnd::GetAutoCloseTime

Возвращает время ожидания автоматическое закрытие.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Возвращаемое значение

Время в миллисекундах, после чего автоматически закроется окно оповещения.

### <a name="remarks"></a>Примечания

Этот метод позволяет определить, сколько времени должно пройти, прежде чем автоматически закроется окно оповещения.

##  <a name="getcaptionheight"></a>  CMFCDesktopAlertWnd::GetCaptionHeight

Возвращает высоту заголовка.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Возвращаемое значение

Высота в пикселях заголовка.

### <a name="remarks"></a>Примечания

Этот метод может быть переопределен в производном классе. Реализация по умолчанию либо: возвращает значение высоты меньшего заголовка (7 в пикселях), если всплывающем окне должны отображаться меньшего заголовка, или значение, полученное от функции Windows API `GetSystemMetrics(SM_CYSMCAPTION)`.

##  <a name="getlastpos"></a>  CMFCDesktopAlertWnd::GetLastPos

Возвращает позицию последнего окно оповещения на экране.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Точка, в экранных координатах.

### <a name="remarks"></a>Примечания

Этот метод возвращает позицию последнего допустимым окна предупреждения на экране.

##  <a name="gettransparency"></a>  CMFCDesktopAlertWnd::GetTransparency

Возвращает уровень прозрачности.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Возвращаемое значение

Уровень прозрачности от 0 до 255 включительно. Чем больше значение, дополнительные непрозрачную окна.

### <a name="remarks"></a>Примечания

Этот метод позволяет получить текущий уровень прозрачности окна оповещения.

##  <a name="hassmallcaption"></a>  CMFCDesktopAlertWnd::HasSmallCaption

Определяет, имеет ли окно оповещения малого заголовка или заголовок обычного размера.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если всплывающее окно отображается с помощью маленького заголовка; Значение FALSE, если Откроется всплывающее окно с заголовком обычный.

### <a name="remarks"></a>Примечания

Этот метод позволяет определить, имеет ли всплывающее окно малого заголовка или заголовок обычного размера. По умолчанию меньшего заголовка — 7 пикселов в высоту. Высоту заголовка обычного размера можно получить путем вызова функции Windows API `GetSystemMetrics(SM_CYCAPTION)`.

##  <a name="onbeforeshow"></a>  CMFCDesktopAlertWnd::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Параметры

[in] *CPoint &*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="onclicklinkbutton"></a>  CMFCDesktopAlertWnd::OnClickLinkButton

Вызывается платформой по нажатию кнопки ссылки на меню рабочего стола оповещения.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
[in] Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

Всегда имеет значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе, если вы хотите получать уведомления, когда пользователь щелкает ссылку на окно оповещения.

##  <a name="oncommand"></a>  CMFCDesktopAlertWnd::OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

[in] *wParam*<br/>

[in] *lParam*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="ondraw"></a>  CMFCDesktopAlertWnd::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

[in] *основного контроллера домена*<br/>

### <a name="remarks"></a>Примечания

##  <a name="processcommand"></a>  CMFCDesktopAlertWnd::ProcessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Параметры

[in] *hwnd*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="setanimationspeed"></a>  CMFCDesktopAlertWnd::SetAnimationSpeed

Задает новый скорость анимации.

```
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Параметры

*nSpeed*<br/>
[in] Указывает новый скорость анимации, в миллисекундах.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы задать скорость анимации для окна оповещения. Скорость анимации по умолчанию — 30 миллисекунд.

##  <a name="setanimationtype"></a>  CMFCDesktopAlertWnd::SetAnimationType

Задает тип анимации.

```
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Параметры

*type*<br/>
[in] Указывает тип анимации.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы задать тип анимации. Можно указать одно из следующих значений.

- NO_ANIMATION

- UNFOLD

- СЛАЙД

- ИСЧЕЗАНИЕ

- SYSTEM_DEFAULT_ANIMATION

##  <a name="setautoclosetime"></a>  CMFCDesktopAlertWnd::SetAutoCloseTime

Задает время ожидания автоматическое закрытие.

```
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Параметры

*nTime*<br/>
[in] Время в миллисекундах, прошедшее до оповещений окно автоматически закрывается.

### <a name="remarks"></a>Примечания

Окно оповещения автоматически закрывается после указанного времени, если пользователь не взаимодействует с окном.

##  <a name="setsmallcaption"></a>  CMFCDesktopAlertWnd::SetSmallCaption

Переключение между малого и обычного размера заголовков.

```
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Параметры

*bSmallCaption*<br/>
[in] Значение TRUE, чтобы указать, что окно оповещения отображает маленького заголовка; в противном случае — значение FALSE, чтобы указать, что окно оповещения отображается заголовок обычного размера.

### <a name="remarks"></a>Примечания

Этот метод используется для отображения небольших или обычного размера заголовка. По умолчанию меньшего заголовка — 7 пикселов в высоту. Размер заголовка регулярных можно получить путем вызова функции Windows API `GetSystemMetrics(SM_CYCAPTION)`.

##  <a name="settransparency"></a>  CMFCDesktopAlertWnd::SetTransparency

Задает уровень прозрачности всплывающего окна.

```
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Параметры

*nTransparency*<br/>
[in] Задает уровень прозрачности. Это значение должно быть в диапазоне от 0 до 255 включительно. Чем больше значение, дополнительные непрозрачную окна.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать уровень прозрачности всплывающего окна.

##  <a name="getdialogsize"></a>  CMFCDesktopAlertWnd::GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)
