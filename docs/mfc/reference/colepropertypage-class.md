---
title: Класс COlePropertyPage
ms.date: 11/04/2016
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
ms.openlocfilehash: 55f4b7304d0b50004585b55142804e0bb4234c16
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271259"
---
# <a name="colepropertypage-class"></a>Класс COlePropertyPage

Используется для отображения свойств пользовательского элемента управления в графическом интерфейсе подобно диалоговому окну.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Создает объект `COlePropertyPage`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Указывает, ли пользователь изменил значение в элементе управления.|
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Возвращает массив объектов, изменяется на страницу свойств.|
|[COlePropertyPage::GetPageSite](#getpagesite)|Возвращает указатель на страницу свойств `IPropertyPageSite` интерфейс.|
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Определяет, какие элементы управления не включайте кнопки "Применить".|
|[COlePropertyPage::IsModified](#ismodified)|Указывает, изменил ли пользователь на страницу свойств.|
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Вызывается платформой, когда пользователь редактирует свойство.|
|[COlePropertyPage::OnHelp](#onhelp)|Вызывается платформой, когда пользователь вызывает справку.|
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Вызывается платформой при инициализации страницы свойств.|
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Вызывается платформой, когда выбран другой элемент управления OLE с новыми свойствами.|
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Вызывается платформой, когда фрейм свойства предоставляет страничный сайт.|
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Задает флаг, указывающий, ли пользователь изменил значение в элементе управления.|
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Задает ресурс диалогового окна страницы свойств.|
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Задает текст краткое справки на странице свойств, имя его файле справки и его контекст справки.|
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающее, является ли он изменен на страницу свойств.|
|[COlePropertyPage::SetPageName](#setpagename)|Задает имя страницы свойств (заголовок).|

## <a name="remarks"></a>Примечания

Например страницы свойств может включать элемент управления редактирования, который позволяет пользователю просматривать и изменять свойство заголовка для элемента управления.

Каждое свойство элемента управления пользовательских или стандартных может иметь элемент управления диалогового окна, который позволяет пользователю элемента управления просмотреть текущее значение свойства и при необходимости изменить это значение.

Дополнительные сведения об использовании `COlePropertyPage`, см. в статье [элементы управления ActiveX: Страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="colepropertypage"></a>  COlePropertyPage::COlePropertyPage

Создает объект `COlePropertyPage`.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>Параметры

*idDlg*<br/>
Идентификатор ресурса шаблона диалогового окна.

*idCaption*<br/>
Идентификатор ресурса для заголовка страницы свойств.

### <a name="remarks"></a>Примечания

При реализации подкласс `COlePropertyPage`, следует использовать конструктор ваш подкласс `COlePropertyPage` конструктор для определения ресурса шаблона диалогового окна на основанную на страницу свойств и строкового ресурса, содержащего его заголовок.

##  <a name="getcontrolstatus"></a>  COlePropertyPage::GetControlStatus

Определяет, изменил ли пользователь значение свойства элемента управления страницы с идентификатором указанного ресурса.

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса для элемента управления страницы свойств.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если значение элемента управления был изменен; в противном случае — значение FALSE.

##  <a name="getobjectarray"></a>  COlePropertyPage::GetObjectArray

Возвращает массив объектов, изменяется на страницу свойств.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>Параметры

*pnObjects*<br/>
Указатель на длинное целое без знака, который будет получать число объектов, изменяется на странице.

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `IDispatch` указатели, которые используются для доступа к свойствам каждого элемента управления на странице свойств. Вызывающий объект не должен освободить эти указатели на интерфейс.

### <a name="remarks"></a>Примечания

Каждый объект страницы свойств содержит массив указателей на `IDispatch` интерфейсы объектов редактируемой страницы. Эта функция задает его *pnObjects* аргумента для числа элементов в этом массиве и возвращает указатель на первый элемент массива.

##  <a name="getpagesite"></a>  COlePropertyPage::GetPageSite

Получает указатель на страницу свойств `IPropertyPageSite` интерфейс.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на страницу свойств `IPropertyPageSite` интерфейс.

### <a name="remarks"></a>Примечания

Взаимодействие, чтобы пользователи могут просматривать и изменять свойства элемента управления, элементов управления и контейнеры. Элемент управления предоставляет страницы свойств, каждый из которых является OLE-объекта, позволяет пользователю изменять связанным набором свойств. Контейнер предоставляет свойство кадра, который отображается на страницах свойств. Для каждой страницы фрейм свойства предоставляет страницу сайта, которая поддерживает `IPropertyPageSite` интерфейс.

##  <a name="ignoreapply"></a>  COlePropertyPage::IgnoreApply

Определяет, какие элементы управления не включайте кнопки "Применить".

```
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор элемента управления нужно игнорировать.

### <a name="remarks"></a>Примечания

Кнопка "Применить" страницы свойств включена только в том случае, если значения элементов управления страницы свойств были изменены. Эта функция используется для выбора элементов управления, которые не вызывают кнопки «Применить» включить, если их значения изменяются.

##  <a name="ismodified"></a>  COlePropertyPage::IsModified

Определяет, изменился ли пользователь с любого значения на странице свойств.

```
BOOL IsModified();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если был изменен на страницу свойств.

##  <a name="oneditproperty"></a>  COlePropertyPage::OnEditProperty

Платформа вызывает эту функцию, когда определенное свойство для редактирования.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации изменяемого свойства.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение FALSE. Переопределения этой функции должны возвращать значение TRUE.

### <a name="remarks"></a>Примечания

Вы можете переопределить его, чтобы установить фокус на соответствующий элемент управления на странице. Реализация по умолчанию не выполняет никаких действий и возвращает значение FALSE.

##  <a name="onhelp"></a>  COlePropertyPage::OnHelp

Платформа вызывает эту функцию, когда пользователь запрашивает справку в Интернете.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>Параметры

*lpszHelpDir*<br/>
Каталог, содержащий файл справки на странице свойств.

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Его необходимо переопределите в том случае, если страницы свойств необходимо выполнить любое специальное действие, когда пользователь получает доступ к справке. Реализация по умолчанию не выполняет никаких действий и возвращает значение FALSE. Это указывает, что платформа для вызова WinHelp.

##  <a name="oninitdialog"></a>  COlePropertyPage::OnInitDialog

Эта функция вызывается платформой при инициализации диалогового окна страницы свойств.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Его необходимо переопределите в том случае, если любое специальное действие является обязательным при инициализации диалогового окна. По умолчанию реализация вызывает `CDialog::OnInitDialog` и возвращает значение FALSE.

##  <a name="onobjectschanged"></a>  COlePropertyPage::OnObjectsChanged

Вызывается платформой, когда выбран другой элемент управления OLE с новыми свойствами.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>Примечания

При просмотре свойств элемента управления OLE в среде разработчика, немодальное диалоговое окно используется для отображения страницы его свойств. Если выбран другой элемент управления, другой набор страницы свойств должны отображаться на новый набор свойств. Платформа вызывает эту функцию для уведомления на странице изменения.

Переопределите эту функцию для получения уведомлений о это действие и выполнения каких-либо специальных действий.

##  <a name="onsetpagesite"></a>  COlePropertyPage::OnSetPageSite

Платформа вызывает эту функцию, когда фрейм свойства предоставляет веб-узел страницы странице свойств.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию загружает заголовок страницы и пытается определить размер страницы из ресурса диалогового окна. Переопределите эту функцию, если страницы свойств требует никаких дальнейших действий; переопределение должно вызывать реализацию базового класса.

##  <a name="setcontrolstatus"></a>  COlePropertyPage::SetControlStatus

Изменяет состояние элемента управления страницы свойств.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Содержит идентификатор элемента управления страницы свойств.

*bDirty*<br/>
Указывает, если поле страницы свойств были изменены. Значение TRUE, если поле было изменено, значение FALSE, если он не был изменен.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если указанный элемент управления установлен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если состояние элемента управления страницы свойств "грязные", при закрытии страницы свойств или выбирается кнопки "Применить", свойства элемента управления будет обновляться соответствующим значением.

##  <a name="setdialogresource"></a>  COlePropertyPage::SetDialogResource

Задает ресурс диалогового окна страницы свойств.

```
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>Параметры

*hDialog*<br/>
Дескриптор для ресурса диалогового окна страницы свойств.

##  <a name="sethelpinfo"></a>  COlePropertyPage::SetHelpInfo

Указывает, во всплывающей подсказке, имя файла справки и контекст справки для страницы свойств.

```
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>Параметры

*lpszDocString*<br/>
Строка, содержащая краткое справочную информацию для отображения в строке состояния или другом расположении.

*lpszHelpFile*<br/>
Имя файла справки на странице свойств.

*dwHelpContext*<br/>
Контекст справки для страницы свойств.

##  <a name="setmodifiedflag"></a>  COlePropertyPage::SetModifiedFlag

Указывает, изменил ли пользователь на страницу свойств.

```
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bModified*<br/>
Указывает новое значение измененного флага в окне свойств.

##  <a name="setpagename"></a>  COlePropertyPage::SetPageName

Задает имя страницы свойств, которая фрейм свойства обычно будет отображаться на вкладке этой страницы.

```
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>Параметры

*lpszPageName*<br/>
Указатель на строку, содержащую имя страницы свойств.

## <a name="see-also"></a>См. также

[Пример CIRC3 MFC](../../visual-cpp-samples.md)<br/>
[Пример MFC TESTHELP](../../visual-cpp-samples.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDialog](../../mfc/reference/cdialog-class.md)
