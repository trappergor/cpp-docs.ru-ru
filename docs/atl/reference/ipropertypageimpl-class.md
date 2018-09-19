---
title: Класс IPropertyPageImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b07609b792b7080e2c4c432ed435381007ba286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075232"
---
# <a name="ipropertypageimpl-class"></a>Класс IPropertyPageImpl

Этот класс реализует `IUnknown` и предоставляет реализацию по умолчанию [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) интерфейс.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPropertyPageImpl`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::Activate](#activate)|Создание диалогового окна страницы свойств.|
|[IPropertyPageImpl::Apply](#apply)|Применяется к базовые объекты, заданные с помощью текущих значений свойств страницы `SetObjects`. Реализация ATL, возвращается значение s_ок.|
|[IPropertyPageImpl::Deactivate](#deactivate)|Уничтожает окно, созданных с помощью `Activate`.|
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Извлекает сведения о странице свойств.|
|[IPropertyPageImpl::Help](#help)|Вызывает справку Windows для страницы свойств.|
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Указывает, был ли изменен на страницу свойств, так как она была активирована.|
|[IPropertyPageImpl::Move](#move)|Размещает и изменяет размер в диалоговом окне страницы свойств.|
|[IPropertyPageImpl::SetDirty](#setdirty)|Флаги состояния страницы свойств как измененные или без изменений.|
|[IPropertyPageImpl::SetObjects](#setobjects)|Предоставляет целый ряд `IUnknown` указатели для объектов, связанных со страницей свойств. Эти объекты получают текущие значения свойств страницы посредством вызова `Apply`.|
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Предоставляет странице свойств с `IPropertyPageSite` указатель, через который на страницу свойств взаимодействует с кадре свойств.|
|[IPropertyPageImpl::Show](#show)|Делает диалоговое окно страницы свойств видимым или невидимым.|
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Обрабатывает указанный нажатие клавиши.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Указывает, изменилось ли состояние на странице свойств.|
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Хранит идентификатор ресурса, связанный со строкой с текстовым описанием страницы свойств.|
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Хранит идентификатор контекста для раздела справки, связанное со страницей свойств.|
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Хранит идентификатор ресурса, связанный с именем файла справки, описывающий страницы свойств.|
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Хранит идентификатор ресурса, связанный со строкой с текстовым, отображается на вкладке страницы свойств.|
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Хранит число объектов, связанный со страницей свойств.|
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|Указывает на `IPropertyPageSite` интерфейс, через который на страницу свойств взаимодействует с кадре свойств.|
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Указывает на массив `IUnknown` указатели на объекты, связанные со страницей свойств.|
|[IPropertyPageImpl::m_size](#m_size)|Хранит высоту и ширину в диалоговом окне страницы свойств в пикселях.|

## <a name="remarks"></a>Примечания

[IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) интерфейс позволяет объекту управлять заданной страницы свойств в окне свойств. Класс `IPropertyPageImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="activate"></a>  IPropertyPageImpl::Activate

Создание диалогового окна страницы свойств.

```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Примечания

По умолчанию диалоговое окно всегда является немодальным, независимо от значения *bModal* параметра.

См. в разделе [IPropertyPage::Activate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-activate) в Windows SDK.

##  <a name="apply"></a>  IPropertyPageImpl::Apply

Применяется к базовые объекты, заданные с помощью текущих значений свойств страницы `SetObjects`.

```
HRESULT Apply();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::Apply](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-apply) в Windows SDK.

##  <a name="deactivate"></a>  IPropertyPageImpl::Deactivate

Уничтожает созданные с помощью диалогового окна [активировать](#activate).

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::Deactivate](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-deactivate) в Windows SDK.

##  <a name="getpageinfo"></a>  IPropertyPageImpl::GetPageInfo

Заполняет *pPageInfo* структуру с сведения, содержащиеся в элементах данных.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Примечания

`GetPageInfo` Загружает строку ресурсов, связанных с [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile), и [m_dwTitle](#m_dwtitle).

См. в разделе [IPropertyPage::GetPageInfo](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) в Windows SDK.

##  <a name="help"></a>  IPropertyPageImpl::Help

Вызывает справку Windows для страницы свойств.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::Help](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-help) в Windows SDK.

##  <a name="ipropertypageimpl"></a>  IPropertyPageImpl::IPropertyPageImpl

Конструктор.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Примечания

Инициализирует все члены данных.

##  <a name="ispagedirty"></a>  IPropertyPageImpl::IsPageDirty

Указывает, был ли изменен на страницу свойств, так как она была активирована.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Примечания

`IsPageDirty` Возвращает S_OK, если страница была изменена, так как она была активирована.

##  <a name="m_bdirty"></a>  IPropertyPageImpl::m_bDirty

Указывает, изменилось ли состояние на странице свойств.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>  IPropertyPageImpl::m_nObjects

Хранит число объектов, связанный со страницей свойств.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>  IPropertyPageImpl::m_dwHelpContext

Хранит идентификатор контекста для раздела справки, связанное со страницей свойств.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>  IPropertyPageImpl::m_dwDocString

Хранит идентификатор ресурса, связанный со строкой с текстовым описанием страницы свойств.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>  IPropertyPageImpl::m_dwHelpFile

Хранит идентификатор ресурса, связанный с именем файла справки, описывающий страницы свойств.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>  IPropertyPageImpl::m_dwTitle

Хранит идентификатор ресурса, связанный со строкой с текстовым, отображается на вкладке страницы свойств.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>  IPropertyPageImpl::m_pPageSite

Указывает на [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) интерфейс, через который на страницу свойств взаимодействует с кадре свойств.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>  IPropertyPageImpl::m_ppUnk

Указывает на массив `IUnknown` указатели на объекты, связанные со страницей свойств.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>  IPropertyPageImpl::m_size

Хранит высоту и ширину в диалоговом окне страницы свойств в пикселях.

```
SIZE m_size;
```

##  <a name="move"></a>  IPropertyPageImpl::Move

Размещает и изменяет размер в диалоговом окне страницы свойств.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::Move](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-move) в Windows SDK.

##  <a name="setdirty"></a>  IPropertyPageImpl::SetDirty

Флаги состояния страницы свойств как измененные или без изменений, в зависимости от значения *bDirty*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*bDirty*<br/>
[in] Значение TRUE, если состояние страницы свойств помечается как измененный. В противном случае он помечается как без изменений.

### <a name="remarks"></a>Примечания

При необходимости `SetDirty` информирует кадра, который был изменен на страницу свойств.

##  <a name="setobjects"></a>  IPropertyPageImpl::SetObjects

Предоставляет целый ряд `IUnknown` указатели для объектов, связанных со страницей свойств.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::SetObjects](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setobjects) в Windows SDK.

##  <a name="setpagesite"></a>  IPropertyPageImpl::SetPageSite

Предоставляет странице свойств с [IPropertyPageSite](/windows/desktop/api/ocidl/nn-ocidl-ipropertypagesite) указатель, через который на страницу свойств взаимодействует с кадре свойств.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::SetPageSite](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-setpagesite) в Windows SDK.

##  <a name="show"></a>  IPropertyPageImpl::Show

Делает диалоговое окно страницы свойств видимым или невидимым.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::Show](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-show) в Windows SDK.

##  <a name="translateaccelerator"></a>  IPropertyPageImpl::TranslateAccelerator

Обрабатывает нажатие клавиши, указанный в `pMsg`.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Примечания

См. в разделе [IPropertyPage::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)<br/>
[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
