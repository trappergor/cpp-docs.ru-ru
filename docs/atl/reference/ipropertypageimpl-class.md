---
title: Класс Ипропертипажеимпл
ms.date: 11/04/2016
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
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
ms.openlocfilehash: 69842e77aecaa94be66432e5fbba437a6fa3c5a4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864987"
---
# <a name="ipropertypageimpl-class"></a>Класс Ипропертипажеимпл

Этот класс реализует `IUnknown` и предоставляет реализацию интерфейса [ипропертипаже](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) по умолчанию.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPropertyPageImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IPropertyPageImpl`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Ипропертипажеимпл:: Ипропертипажеимпл](#ipropertypageimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Ипропертипажеимпл:: Activate](#activate)|Создает окно диалогового окна для страницы свойств.|
|[Ипропертипажеимпл:: Apply](#apply)|Применяет текущие значения страницы свойств к базовым объектам, заданным с помощью `SetObjects`. Реализация ATL возвращает S_OK.|
|[Ипропертипажеимпл::D еактивате](#deactivate)|Уничтожает окно, созданное с помощью `Activate`.|
|[Ипропертипажеимпл:: Жетпажеинфо](#getpageinfo)|Извлекает сведения о странице свойств.|
|[Ипропертипажеимпл:: Help](#help)|Вызывает справку Windows для страницы свойств.|
|[Ипропертипажеимпл:: Испажедирти](#ispagedirty)|Указывает, изменилась ли страница свойств с момента ее активации.|
|[Ипропертипажеимпл:: Move](#move)|Определяет положение и изменяет размер диалогового окна страницы свойств.|
|[Ипропертипажеимпл:: Сетдирти](#setdirty)|Помечает состояние страницы свойств как измененное или неизмененное.|
|[Ипропертипажеимпл:: Сетобжектс](#setobjects)|Предоставляет массив `IUnknown`ных указателей для объектов, связанных со страницей свойств. Эти объекты получают текущие значения страницы свойств с помощью вызова метода `Apply`.|
|[Ипропертипажеимпл:: Сетпажесите](#setpagesite)|Предоставляет страницу свойств с указателем `IPropertyPageSite`, через который страница свойств взаимодействует с рамкой свойства.|
|[Ипропертипажеимпл:: показывать](#show)|Делает диалоговое окно страницы свойств видимым или невидимым.|
|[Ипропертипажеимпл:: TranslateAccelerator](#translateaccelerator)|Обрабатывает заданное нажатие клавиши.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Description|
|----------|-----------------|
|[Ипропертипажеимпл:: m_bDirty](#m_bdirty)|Указывает, изменилось ли состояние страницы свойств.|
|[Ипропертипажеимпл:: m_dwDocString](#m_dwdocstring)|Хранит идентификатор ресурса, связанный с текстовой строкой, описывающей страницу свойств.|
|[Ипропертипажеимпл:: m_dwHelpContext](#m_dwhelpcontext)|Содержит идентификатор контекста для раздела справки, связанного со страницей свойств.|
|[Ипропертипажеимпл:: m_dwHelpFile](#m_dwhelpfile)|Хранит идентификатор ресурса, связанный с именем файла справки, описывающего страницу свойств.|
|[Ипропертипажеимпл:: m_dwTitle](#m_dwtitle)|Хранит идентификатор ресурса, связанный с текстовой строкой, отображаемой на вкладке страницы свойств.|
|[Ипропертипажеимпл:: m_nObjects](#m_nobjects)|Хранит количество объектов, связанных со страницей свойств.|
|[Ипропертипажеимпл:: m_pPageSite](#m_ppagesite)|Указывает на интерфейс `IPropertyPageSite`, через который страница свойств взаимодействует с рамкой свойства.|
|[Ипропертипажеимпл:: m_ppUnk](#m_ppunk)|Указывает на массив `IUnknown`ных указателей на объекты, связанные со страницей свойств.|
|[Ипропертипажеимпл:: m_size](#m_size)|Сохраняет высоту и ширину диалогового окна страницы свойств в пикселях.|

## <a name="remarks"></a>Remarks

Интерфейс [ипропертипаже](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) позволяет объекту управлять определенной страницей свойств в пределах страницы свойств. Класс `IPropertyPageImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown`, отправляя сведения в устройство дампа в отладочных сборках.

Руководство по **сопутствующим статьям** [ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IPropertyPage`

`IPropertyPageImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="activate"></a>Ипропертипажеимпл:: Activate

Создает окно диалогового окна для страницы свойств.

```
HRESULT Activate(
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```

### <a name="remarks"></a>Remarks

По умолчанию диалоговое окно всегда является немодальным, независимо от значения параметра *бмодал* .

См. раздел [ипропертипаже:: Activate](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-activate) в Windows SDK.

##  <a name="apply"></a>Ипропертипажеимпл:: Apply

Применяет текущие значения страницы свойств к базовым объектам, заданным с помощью `SetObjects`.

```
HRESULT Apply();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK.

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: Apply](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-apply) в Windows SDK.

##  <a name="deactivate"></a>Ипропертипажеимпл::D еактивате

Уничтожает окно диалогового окна, созданного с помощью [активации](#activate).

```
HRESULT Deactivate();
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже::D еактивате](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-deactivate) в Windows SDK.

##  <a name="getpageinfo"></a>Ипропертипажеимпл:: Жетпажеинфо

Заполняет структуру *ппажеинфо* данными, содержащимися в элементах данных.

```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Remarks

`GetPageInfo` загружает строковые ресурсы, связанные с [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile)и [m_dwTitle](#m_dwtitle).

См. раздел [ипропертипаже:: жетпажеинфо](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-getpageinfo) в Windows SDK.

##  <a name="help"></a>Ипропертипажеимпл:: Help

Вызывает справку Windows для страницы свойств.

```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: Help](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-help) в Windows SDK.

##  <a name="ipropertypageimpl"></a>Ипропертипажеимпл:: Ипропертипажеимпл

Конструктор.

```
IPropertyPageImpl();
```

### <a name="remarks"></a>Remarks

Инициализирует все элементы данных.

##  <a name="ispagedirty"></a>Ипропертипажеимпл:: Испажедирти

Указывает, изменилась ли страница свойств с момента ее активации.

```
HRESULT IsPageDirty(void);
```

### <a name="remarks"></a>Remarks

`IsPageDirty` возвращает S_OK, если страница изменилась с момента ее активации.

##  <a name="m_bdirty"></a>Ипропертипажеимпл:: m_bDirty

Указывает, изменилось ли состояние страницы свойств.

```
BOOL m_bDirty;
```

##  <a name="m_nobjects"></a>Ипропертипажеимпл:: m_nObjects

Хранит количество объектов, связанных со страницей свойств.

```
ULONG m_nObjects;
```

##  <a name="m_dwhelpcontext"></a>Ипропертипажеимпл:: m_dwHelpContext

Содержит идентификатор контекста для раздела справки, связанного со страницей свойств.

```
DWORD m_dwHelpContext;
```

##  <a name="m_dwdocstring"></a>Ипропертипажеимпл:: m_dwDocString

Хранит идентификатор ресурса, связанный с текстовой строкой, описывающей страницу свойств.

```
UINT m_dwDocString;
```

##  <a name="m_dwhelpfile"></a>Ипропертипажеимпл:: m_dwHelpFile

Хранит идентификатор ресурса, связанный с именем файла справки, описывающего страницу свойств.

```
UINT m_dwHelpFile;
```

##  <a name="m_dwtitle"></a>Ипропертипажеимпл:: m_dwTitle

Хранит идентификатор ресурса, связанный с текстовой строкой, отображаемой на вкладке страницы свойств.

```
UINT m_dwTitle;
```

##  <a name="m_ppagesite"></a>Ипропертипажеимпл:: m_pPageSite

Указывает на интерфейс [ипропертипажесите](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) , через который страница свойств взаимодействует с рамкой свойства.

```
IPropertyPageSite* m_pPageSite;
```

##  <a name="m_ppunk"></a>Ипропертипажеимпл:: m_ppUnk

Указывает на массив `IUnknown`ных указателей на объекты, связанные со страницей свойств.

```
IUnknown** m_ppUnk;
```

##  <a name="m_size"></a>Ипропертипажеимпл:: m_size

Сохраняет высоту и ширину диалогового окна страницы свойств в пикселях.

```
SIZE m_size;
```

##  <a name="move"></a>Ипропертипажеимпл:: Move

Определяет положение и изменяет размер диалогового окна страницы свойств.

```
HRESULT Move(LPCRECT pRect);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: Move](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-move) в Windows SDK.

##  <a name="setdirty"></a>Ипропертипажеимпл:: Сетдирти

Помечает состояние страницы свойств как измененное или неизмененное, в зависимости от значения *бдирти*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Параметры

*бдирти*<br/>
окне Если значение — TRUE, состояние страницы свойств помечается как измененное. В противном случае он помечается как неизмененный.

### <a name="remarks"></a>Remarks

При необходимости `SetDirty` информирует кадр о том, что изменилась страница свойств.

##  <a name="setobjects"></a>Ипропертипажеимпл:: Сетобжектс

Предоставляет массив `IUnknown`ных указателей для объектов, связанных со страницей свойств.

```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: сетобжектс](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setobjects) в Windows SDK.

##  <a name="setpagesite"></a>Ипропертипажеимпл:: Сетпажесите

Предоставляет страницу свойств с указателем [ипропертипажесите](/windows/win32/api/ocidl/nn-ocidl-ipropertypagesite) , через который страница свойств взаимодействует с рамкой свойства.

```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: сетпажесите](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-setpagesite) в Windows SDK.

##  <a name="show"></a>Ипропертипажеимпл:: показывать

Делает диалоговое окно страницы свойств видимым или невидимым.

```
HRESULT Show(UINT nCmdShow);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: показывать](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-show) в Windows SDK.

##  <a name="translateaccelerator"></a>Ипропертипажеимпл:: TranslateAccelerator

Обрабатывает нажатие клавиши, заданное в `pMsg`.

```
HRESULT TranslateAccelerator(MSG* pMsg);
```

### <a name="remarks"></a>Remarks

См. раздел [ипропертипаже:: TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-ipropertypage-translateaccelerator) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс IPropertyPage2Impl](../../atl/reference/ipropertypage2impl-class.md)<br/>
[Класс IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
