---
title: Класс COleControlContainer
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: 83171e012db7ef2cce459d35cfc689746afd062c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749029"
---
# <a name="colecontrolcontainer-class"></a>Класс COleControlContainer

Играет роль контейнера для элементов управления ActiveX.

## <a name="syntax"></a>Синтаксис

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeControlContainer:: COleControlContainer](#colecontrolcontainer)|Формирует объект `COleControlContainer`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeControlContainer::AttachControlSite](#attachcontrolsite)|Создает сайт управления, размещенный контейнером.|
|[ColeControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Информирует все размещенные элементы управления о том, что изменилось свойство окружающего.|
|[ColeControlcontainer:CheckDlgButton](#checkdlgbutton)|Изменяет указанное управление кнопкой.|
|[ColeControlcontainer::CheckRadioButton](#checkradiobutton)|Выбирает указанную кнопку радио группы.|
|[ColeControlContainer::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|
|[ColeControlcontainer::CreateOleFont](#createolefont)|Создает шрифт OLE.|
|[ColeControlContainer::FindItem](#finditem)|Возвращает пользовательский сайт указанного элемента управления.|
|[ColeControlContainer::FreezeAllEvents](#freezeallevents)|Определяет, принимает ли сайт управления события.|
|[ColeControlcontainer::GetAmbientProp](#getambientprop)|Извлекает указанное свойство окружающей среды.|
|[ColeControlcontainer::GetDlgItem](#getdlgitem)|Извлекает указанный элемент управления диалогом.|
|[ColeControlContainer::GetDlgItemInt](#getdlgitemint)|Извлекает значение заданного элемента управления диалогом.|
|[ColeControlcontainer::GetDlgItemtext](#getdlgitemtext)|Извлекает подпись указанного элемента управления диалогом.|
|[ColeControlContainer::HandleSetFocus](#handlesetfocus)|Определяет, обрабатывает ли контейнер WM_SETFOCUS сообщений.|
|[ColeControlContainer::HandlewindowlessMessage](#handlewindowlessmessage)|Обрабатывает сообщения, отправленные в управление без окон.|
|[ColeControlcontainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Определяет состояние указанной кнопки.|
|[ColeControlcontainer::Onpaint](#onpaint)|Позвонил, чтобы перекрасить часть контейнера.|
|[ColeControlcontainer::OnuIActivate](#onuiactivate)|Вызывается, когда элемент управления вот-вот будет на месте активирован.|
|[ColeControlcontainer:OnuiDeactivate](#onuideactivate)|Вызывается, когда элемент управления вот-вот будет отключен.|
|[ColeControlContainer::ScrollChildren](#scrollchildren)|Вызывается инфраструктурой при получении сообщений прокрутки из окна ребенка.|
|[ColeControlcontainer::SendDlgItemMessage](#senddlgitemmessage)|Отправляет сообщение указанному элементу управления.|
|[ColeControlContainer::SetDlgItemInt](#setdlgitemint)|Устанавливает значение указанного элемента управления.|
|[ColeControlcontainer::SetDlgItemText](#setdlgitemtext)|Устанавливает текст указанного элемента управления.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeControlContainer::m_crBack](#m_crback)|Цвет фона контейнера.|
|[ColeControlContainer::m_crFore](#m_crfore)|Цвет переднего плана контейнера.|
|[ColeControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Список поддерживаемых сайтов управления.|
|[ColeControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Количество размещенных элементов управления без окон.|
|[ColeControlContainer::m_pOleFont](#m_polefont)|Указатель на шрифт OLE пользовательского сайта управления.|
|[ColeControlContainer::m_pSiteCapture](#m_psitecapture)|Указатель на место управления захватом.|
|[ColeControlContainer::m_pSiteFocus](#m_psitefocus)|Указатель на элемент управления, который в настоящее время имеет фокус ввода.|
|[ColeControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Указатель на элемент управления, который в настоящее время на месте активирован.|
|[ColeControlContainer::m_pWnd](#m_pwnd)|Указатель на окно, реализующее контейнер управления.|
|[ColeControlContainer::m_siteMap](#m_sitemap)|Карта сайта.|

## <a name="remarks"></a>Remarks

Это делается путем предоставления поддержки для одного `COleControlSite`или нескольких сайтов управления ActiveX (реализованных). `COleControlContainer`полностью реализует интерфейсы [IOleInPlaceFrame](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe) и [IOleContainer,](/windows/win32/api/oleidl/nn-oleidl-iolecontainer) что позволяет содержать элементы управления ActiveX для выполнения их квалификации в качестве на месте элементов.

Как правило, этот класс `COccManager` используется `COleControlSite` в сочетании с пользовательским контейнером управления ActiveX и для реализации пользовательских сайтов с пользовательскими сайтами для одного или нескольких элементов управления ActiveX.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>Требования

**Заголовок:** afxocc.h

## <a name="colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>ColeControlContainer::AttachControlSite

Вызывается по системе для создания и присоединения сайта управления.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на объект `CWnd`.

*nIDC*<br/>
Идентификатор элемента управления, который будет прикреплен.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, если вы хотите настроить этот процесс.

> [!NOTE]
> Используйте первую форму этой функции, если вы статически ссылок на библиотеку MFC. Используйте вторую форму, если вы динамически ссылок на библиотеку MFC.

## <a name="colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>ColeControlContainer::BroadcastAmbientPropertyChange

Информирует все размещенные элементы управления о том, что изменилось свойство окружающего.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки изменяемого свойства окружающего.

### <a name="remarks"></a>Remarks

Эта функция вызывается инфраструктурой при изменении значения свойства окружающего. Переопределить эту функцию, чтобы настроить это поведение.

## <a name="colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>ColeControlcontainer:CheckDlgButton

Изменяет текущее состояние кнопки.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>Параметры

*nIDButton*<br/>
Идентификатор кнопки, который будет изменен.

*Nпроверьте*<br/>
Определяет состояние кнопки. Может применяться один из перечисленных ниже типов.

- BST_CHECKED устанавливает состояние кнопки для проверки.

- BST_INDETERMINATE устанавливает состояние кнопки в серое, указывая на неопределенное состояние. Используйте это значение только в том случае, если кнопка имеет BS_3STATE или BS_AUTO3STATE стиль.

- BST_UNCHECKED устанавливает состояние кнопки для очистки.

## <a name="colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>ColeControlcontainer::CheckRadioButton

Выберите указанную кнопку радио в группе и очищает оставшиеся кнопки в группе.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>Параметры

*nIDFirstButton*<br/>
Определяет идентификатор первой кнопки радио в группе.

*nIDLastButton*<br/>
Определяет идентификатор последней кнопки радио в группе.

*nIDCheckButton*<br/>
Определяет идентификатор радиокнопки для проверки.

## <a name="colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>ColeControlContainer:: COleControlContainer

Формирует объект `COleControlContainer`.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указатель на родительское окно контейнера управления.

### <a name="remarks"></a>Remarks

После успешного создания объекта добавьте пользовательский сайт `AttachControlSite`управления с вызовом.

## <a name="colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>ColeControlContainer::CreateControl

Создает элемент управления ActiveX, `COleControlSite` размещенный указанным объектом.

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>Параметры

*pWndCtrl*<br/>
Указатель на объект окна, представляющий элемент управления.

*clsid*<br/>
Уникальный идентификатор класса управления.

*lpszWindowName*<br/>
Указатель на текст, который отображается в элементе управления. Устанавливает значение свойства подписи или текста элемента управления (если таковое имеется). Если NULL, свойство подписи или текста элемента управления не изменяется.

*dwStyle*<br/>
Стили Windows. Доступные стили перечислены в разделе **Замечания.**

*rect*<br/>
Определяет размер и положение элемента управления. Это может быть `CRect` либо `RECT` объект, либо структура.

*nID*<br/>
Упоняет идентификатор окна ребенка элемента управления.

*pPersist*<br/>
Указатель на `CFile` содержащее постоянное состояние для управления. Значение по умолчанию является NULL, что указывает на то, что элемент управления инициализирует себя без восстановления его состояния от постоянного хранилища. Если не NULL, то он должен `CFile`быть указателем на объект, содержащий постоянные данные элемента управления, в виде потока или хранилища. Эти данные могли быть сохранены при предыдущей активации клиента. Может `CFile` содержать другие данные, но должен иметь свой указатель на чтение-запись, установленный `CreateControl`на первый байт стойких данных во время вызова.

*bХранение*<br/>
Указывает, следует ли интерпретировать данные `IStorage` в `IStream` *pPersist* как или данные. Если данные в *pPersist* является хранилищем, *bStorage* должно быть правдой. Если данные в *pPersist* является потоком, *bStorage* должен быть FALSE. Значение по умолчанию — FALSE.

*bstrLicKey*<br/>
Дополнительные данные ключей лицензии. Эти данные необходимы только для создания элементов управления, требующих ключа лицензии времени выполнения. Если элемент управления поддерживает лицензирование, необходимо предоставить ключ лицензии для создания элемента управления для достижения успеха. Значение по умолчанию — NULL.

*ppNewSite*<br/>
Указатель на существующий сайт управления, на который будет размещен создаваемый элемент управления. Значение по умолчанию является NULL, что указывает на то, что новый участок управления будет автоматически создан и подключен к новому элементу управления.

*Ppt*<br/>
Указатель на `POINT` структуру, содержащую верхний левый угол элемента управления. Размер элемента определяется значением *psize.* Значения *ppt* и *psize* являются необязательным методом определения размера и положения элемента управления.

*psize*<br/>
Указатель на `SIZE` структуру, содержащую размер элемента управления. Верхний левый угол определяется значением *ppt.* Значения *ppt* и *psize* являются необязательным методом определения размера и положения элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Поддерживается `CreateControl`только подмножество флагов Windows *dwStyle:*

- WS_VISIBLE создает окно, которое изначально видно. Требуется, если вы хотите, чтобы элемент управления был виден немедленно, как обычные окна.

- WS_DISABLED создает окно, которое изначально отключено. Отключенное окно не может получать ввод от пользователя. Может быть установлен, если элемент управления имеет свойство enabled.

- WS_BORDER создает окно с тонкой линией границы. Может быть установлен, если контроль имеет свойство BorderStyle.

- WS_GROUP определяет первый элемент управления группой элементов управления. Пользователь может изменить фокус клавиатуры с одного элемента управления в группе на другой, используя клавиши направления. Все элементы управления, определяемые со стилем WS_GROUP после первого элемента управления принадлежат одной и той же группе. Следующий элемент управления со стилем WS_GROUP завершает группу и запускает следующую группу.

- WS_TABSTOP определяет элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает на ключ TAB. Нажатие клавиши TAB изменяет фокус клавиатуры на следующий элемент управления стилем WS_TABSTOP.

Используйте вторую перегрузку для создания элементов управления размером с непосредствение.

## <a name="colecontrolcontainercreateolefont"></a><a name="createolefont"></a>ColeControlcontainer::CreateOleFont

Создает шрифт OLE.

```cpp
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
Указатель на шрифт, который будет использоваться контейнером управления.

## <a name="colecontrolcontainerfinditem"></a><a name="finditem"></a>ColeControlContainer::FindItem

Находит пользовательский сайт, на котором размещаетуказанный элемент.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор найденного элемента.

### <a name="return-value"></a>Возвращаемое значение

Указатель на пользовательский сайт указанного элемента.

## <a name="colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>ColeControlContainer::FreezeAllEvents

Определяет, будет ли контейнер игнорировать события с присоединенных контрольных участков или принимать их.

```cpp
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>Параметры

*bFreeze*<br/>
Nonzero, если события будут обработаны; в противном случае 0.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Контроль не требуется, чтобы остановить события стрельбы, если требуется контрольный контейнер. Он может продолжать стрельбу, но все последующие события будут проигнорированы контейнером управления.

## <a name="colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>ColeControlcontainer::GetAmbientProp

Извлекает значение указанного свойства окружающей среды.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>Параметры

*pSite*<br/>
Указатель на контрольное место, с которого будет извлечено свойство окружающего.

*Dispid*<br/>
Идентификатор отправки желаемого свойства окружающей среды.

*pVarResult*<br/>
Указатель на значение окружающего свойства.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>ColeControlcontainer::GetDlgItem

Извлекает указатель на указанное окно управления или дочернее окно в диалоговом окне или другом окне.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификация элемента диалога для извлечения.

*phWnd*<br/>
Указатель на рукоятку объекта окна указанного элемента диалога.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно элемента диалога.

## <a name="colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>ColeControlContainer::GetDlgItemInt

Получает значение переведенного текста данного элемента управления.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*lpTrans*<br/>
Указатель на переменную Boolean, которая получает значение успеха/неудачи функции (TRUE указывает на успех, FALSE указывает на сбой).

*bПодписанный*<br/>
Определяет, должна ли функция изучить текст для знака минус в начале и вернуть подписанное значение integer, если он находит один. Если *параметр bSigned* является правдивым, указывая, что значение, которое необходимо получить, является подписанным значением integer, отбросьте значение возврата в тип **int.** Чтобы получить расширенную информацию об ошибке, позвоните [getLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="return-value"></a>Возвращаемое значение

В случае успеха переменная, указанная *lpTrans,* устанавливается в TRUE, а значение возврата — переведенное значение текста управления.

Если функция выходит из строя, переменная, указанная *lpTrans,* устанавливается на FALSE, а значение возврата равно нулю. Обратите внимание, что, поскольку ноль является возможным переведенным значением, значение возврата нуля само по себе не указывает на сбой.

Если *lpTrans* является NULL, функция не возвращает никакой информации об успехе или сбое.

### <a name="remarks"></a>Remarks

Функция переводит извлеченный текст, зачистка любых дополнительных пробелов в начале текста, а затем преобразования десятичных цифр. Функция перестает переводить, когда она достигает конца текста или сталкивается с нечисленностьным персонажем.

Эта функция возвращается с нулем, если переведенное значение превышает INT_MAX (для подписанных номеров) или UINT_MAX (для неподписанных номеров).

## <a name="colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>ColeControlcontainer::GetDlgItemtext

Извлекает текст данного элемента управления.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*lpStr*<br/>
Указатель на текст управления.

*nMaxCount*<br/>
Определяет максимальную длину, в символах, строки, которые будут скопированы в буфер, на который указывает *lpStr*. Если длина строки превышает предел, строка усечена.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата определяет количество символов, скопированных в буфер, не включая термин null.

Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенную информацию об ошибке, позвоните [getLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## <a name="colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>ColeControlContainer::HandleSetFocus

Определяет, обрабатывает ли контейнер WM_SETFOCUS сообщений.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контейнер обрабатывает WM_SETFOCUS сообщений; в противном случае ноль.

## <a name="colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>ColeControlContainer::HandlewindowlessMessage

Обрабатывает оконные сообщения для управления без окон.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор для сообщения окна, предоставляемый Windows.

*wParam*<br/>
Параметр сообщения; предоставлена Windows. Определяет дополнительную информацию, конкретную для сообщений. Содержание этого параметра зависит от значения параметра *сообщения.*

*lParam*<br/>
Параметр сообщения; предоставлена Windows. Определяет дополнительную информацию, конкретную для сообщений. Содержание этого параметра зависит от значения параметра *сообщения.*

*plResult*<br/>
Код результатов Windows. Опознавательный результат обработки сообщений и зависит от отправленного сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха, иначе — 0.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить обработку сообщений управления без окон.

## <a name="colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>ColeControlcontainer::IsDlgButtonChecked

Определяет состояние указанной кнопки.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>Параметры

*nIDButton*<br/>
Идентификатор управления кнопкой.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата из кнопки, созданной в стиле BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON или BS_3STATE. Может применяться один из перечисленных ниже типов.

- BST_CHECKED кнопка проверяется.

- BST_INDETERMINATE кнопка сера, указывая на неопределенное состояние (применяется только в том случае, если кнопка имеет BS_3STATE или BS_AUTO3STATE стиль).

- BST_UNCHECKED кнопка очищается.

### <a name="remarks"></a>Remarks

Если кнопка является элементом управления тремя состояниями, функция элемента определяет, затемнена она, проверена или нет.

## <a name="colecontrolcontainerm_crback"></a><a name="m_crback"></a>ColeControlContainer::m_crBack

Цвет фона контейнера.

```
COLORREF m_crBack;
```

## <a name="colecontrolcontainerm_crfore"></a><a name="m_crfore"></a>ColeControlContainer::m_crFore

Цвет переднего плана контейнера.

```
COLORREF m_crFore;
```

## <a name="colecontrolcontainerm_listsitesorwnds"></a><a name="m_listsitesorwnds"></a>ColeControlContainer::m_listSitesOrWnds

Список контрольных объектов, размещенных контейнером.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

## <a name="colecontrolcontainerm_nwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>ColeControlContainer::m_nWindowlessControls

Количество элементов управления без окон, размещенных в контейнере управления.

```
int m_nWindowlessControls;
```

## <a name="colecontrolcontainerm_polefont"></a><a name="m_polefont"></a>ColeControlContainer::m_pOleFont

Указатель на шрифт OLE пользовательского сайта управления.

```
LPFONTDISP m_pOleFont;
```

## <a name="colecontrolcontainerm_psitecapture"></a><a name="m_psitecapture"></a>ColeControlContainer::m_pSiteCapture

Указатель на место управления захватом.

```
COleControlSite* m_pSiteCapture;
```

## <a name="colecontrolcontainerm_psitefocus"></a><a name="m_psitefocus"></a>ColeControlContainer::m_pSiteFocus

Указатель на сайт управления, который в настоящее время имеет фокус ввода.

```
COleControlSite* m_pSiteFocus;
```

## <a name="colecontrolcontainerm_psiteuiactive"></a><a name="m_psiteuiactive"></a>ColeControlContainer::m_pSiteUIActive

Указатель на активированный сайт управления.

```
COleControlSite* m_pSiteUIActive;
```

## <a name="colecontrolcontainerm_pwnd"></a><a name="m_pwnd"></a>ColeControlContainer::m_pWnd

Указатель на объект окна, связанный с контейнером.

```
CWnd* m_pWnd;
```

## <a name="colecontrolcontainerm_sitemap"></a><a name="m_sitemap"></a>ColeControlContainer::m_siteMap

Карта сайта.

```
CMapPtrToPtr m_siteMap;
```

## <a name="colecontrolcontaineronpaint"></a><a name="onpaint"></a>ColeControlcontainer::Onpaint

Вызывается в рамках для обработки WM_PAINT запросов.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, используемый контейнером.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было обработано; в противном случае ноль.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы настроить процесс покраски.

## <a name="colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>ColeControlcontainer::OnuIActivate

Вызывается рамки, когда сайт управления, указал на *pSite*, вот-вот будет активирован анайтерна на месте.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Параметры

*pSite*<br/>
Указатель на контрольный участок вот-вот будет на месте активирован.

### <a name="remarks"></a>Remarks

Активация на месте означает, что основное меню контейнера заменяется композитным меню на месте.

## <a name="colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>ColeControlcontainer:OnuiDeactivate

Вызывается рамки, когда контрольный сайт, указал на *pSite*, вот-вот будет отключена.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>Параметры

*pSite*<br/>
Указатель на контрольный участок вот-вот будет отключен.

### <a name="remarks"></a>Remarks

Когда это уведомление получено, контейнер должен переустановить свой пользовательский интерфейс и сосредоточиться.

## <a name="colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>ColeControlContainer::ScrollChildren

Вызывается инфраструктурой при получении сообщений прокрутки из окна ребенка.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>Параметры

*dx*<br/>
Сумма, в пикселях, прокрутки вдоль оси x.

*Dy*<br/>
Сумма, в пикселях, прокрутки вдоль y-оси.

## <a name="colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>ColeControlcontainer::SendDlgItemMessage

Отправляет сообщение указанному элементу управления.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Определяет идентификатор элемента управления, который получает сообщение.

*message*<br/>
Упоняет сообщение, необходимое для отправки.

*wParam*<br/>
Определяет дополнительную информацию, конкретную для сообщений.

*lParam*<br/>
Определяет дополнительную информацию, конкретную для сообщений.

## <a name="colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>ColeControlContainer::SetDlgItemInt

Устанавливает текст элемента управления в диалоговом поле на строковое представление заданного значения рядового значения.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*nValue*<br/>
Значение, необходимое для отображения.

*bПодписанный*<br/>
Определяет, подписан или не подписан параметр *nValue.* Если этот параметр является правдой, *nValue* подписан. Если этот параметр является правдой, а *nValue* меньше нуля, перед первой цифрой в строке помещается знак минус. Если этот параметр FALSE, *nValue* не подписан.

## <a name="colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>ColeControlcontainer::SetDlgItemText

Устанавливает текст указанного элемента управления, используя текст, содержащийся в *lpszString*.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления.

*lpszString*<br/>
Указатель на текст управления.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)<br/>
[Класс COccManager](../../mfc/reference/coccmanager-class.md)
