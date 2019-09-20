---
title: Класс Иолеобжектимпл
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: ded158b0ec862de5b0d0b23dd4b9edb50ad577ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495733"
---
# <a name="ioleobjectimpl-class"></a>Класс Иолеобжектимпл

Этот класс реализует `IUnknown` и является основным интерфейсом, через который контейнер взаимодействует с элементом управления.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IOleObjectImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Иолеобжектимпл:: Advise](#advise)|Устанавливает вспомогательное соединение с элементом управления.|
|[Иолеобжектимпл:: Close](#close)|Изменяет состояние элемента управления с "работает" на "Загружено".|
|[Иолеобжектимпл::D Оверб](#doverb)|Указывает элементу управления выполнить одно из его перечисленных действий.|
|[Иолеобжектимпл::D Овербдискардундо](#doverbdiscardundo)|Указывает элементу управления отменить любое состояние отмены, которое оно обслуживает.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Указывает элементу управления удалить пользовательский интерфейс из представления.|
|[Иолеобжектимпл::D Овербинплацеактивате](#doverbinplaceactivate)|Запускает элемент управления и устанавливает его окно, но не устанавливает пользовательский интерфейс элемента управления.|
|[Иолеобжектимпл::D Овербопен](#doverbopen)|Приводит к открытию элемента управления для редактирования в отдельном окне.|
|[Иолеобжектимпл::D Овербпримари](#doverbprimary)|Выполняет указанное действие, когда пользователь дважды щелкает элемент управления. Элемент управления определяет действие, обычно для активации элемента управления на месте.|
|[Иолеобжектимпл::D Овербшов](#doverbshow)|Показывает недавно вставленный элемент управления для пользователя.|
|[Иолеобжектимпл::D Овербуиактивате](#doverbuiactivate)|Активирует элемент управления на месте и отображает пользовательский интерфейс элемента управления, например меню и панели инструментов.|
|[Иолеобжектимпл:: Енумадвисе](#enumadvise)|Перечисляет советы по вспомогательным соединениям элемента управления.|
|[Иолеобжектимпл:: Енумвербс](#enumverbs)|Перечисляет действия для элемента управления.|
|[Иолеобжектимпл:: Жетклиентсите](#getclientsite)|Извлекает клиентский сайт элемента управления.|
|[Иолеобжектимпл:: Жетклипбоарддата](#getclipboarddata)|Извлекает данные из буфера обмена. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеобжектимпл:: расширение](#getextent)|Извлекает экстент отображаемой области элемента управления.|
|[Иолеобжектимпл:: Жетмискстатус](#getmiscstatus)|Возвращает состояние элемента управления.|
|[Иолеобжектимпл:: моникер](#getmoniker)|Извлекает моникер элемента управления. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеобжектимпл:: Жетусерклассид](#getuserclassid)|Получает идентификатор класса элемента управления.|
|[Иолеобжектимпл:: Жетусертипе](#getusertype)|Извлекает имя пользовательского типа элемента управления.|
|[Иолеобжектимпл:: Инитфромдата](#initfromdata)|Инициализирует элемент управления из выбранных данных. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеобжектимпл:: Исуптодате](#isuptodate)|Проверяет, является ли элемент управления актуальным. Реализация ATL возвращает значение S_OK.|
|[Иолеобжектимпл:: Онпоствербдискардундо](#onpostverbdiscardundo)|Вызывается методом [довербдискардундо](#doverbdiscardundo) после отклонения состояния отмены.|
|[Иолеобжектимпл:: Онпоствербхиде](#onpostverbhide)|Вызывается методом [довербхиде](#doverbhide) после скрытия элемента управления.|
|[Иолеобжектимпл:: Онпоствербинплацеактивате](#onpostverbinplaceactivate)|Вызывается методом [довербинплацеактивате](#doverbinplaceactivate) после активации элемента управления на месте.|
|[Иолеобжектимпл:: Онпоствербопен](#onpostverbopen)|Вызывается методом [довербопен](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.|
|[Иолеобжектимпл:: Онпоствербшов](#onpostverbshow)|Вызывается методом [довербшов](#doverbshow) после того, как элемент управления стал видимым.|
|[Иолеобжектимпл:: Онпоствербуиактивате](#onpostverbuiactivate)|Вызывается методом [довербуиактивате](#doverbuiactivate) после активации пользовательского интерфейса элемента управления.|
|[Иолеобжектимпл:: Онпревербдискардундо](#onpreverbdiscardundo)|Вызывается методом [довербдискардундо](#doverbdiscardundo) , прежде чем состояние отмены отклоняется.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Вызывается методом [довербхиде](#doverbhide) перед скрытием элемента управления.|
|[Иолеобжектимпл:: Онпревербинплацеактивате](#onpreverbinplaceactivate)|Вызывается методом [довербинплацеактивате](#doverbinplaceactivate) перед активацией элемента управления на месте.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Вызывается методом [довербопен](#doverbopen) перед открытием элемента управления для редактирования в отдельном окне.|
|[Иолеобжектимпл:: Онпревербшов](#onpreverbshow)|Вызывается методом [довербшов](#doverbshow) , прежде чем элемент управления станет видимым.|
|[Иолеобжектимпл:: Онпревербуиактивате](#onpreverbuiactivate)|Вызывается методом [довербуиактивате](#doverbuiactivate) перед активацией пользовательского интерфейса элемента управления.|
|[Иолеобжектимпл:: Сетклиентсите](#setclientsite)|Сообщает элементу управления о своем клиентском сайте в контейнере.|
|[Иолеобжектимпл:: Сетколорсчеме](#setcolorscheme)|Рекомендует использовать цветовую схему для приложения элемента управления, если таковая имеется. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеобжектимпл:: Сетекстент](#setextent)|Задает экстент отображаемой области элемента управления.|
|[Иолеобжектимпл:: Сесостнамес](#sethostnames)|Сообщает элементу управления имена приложения контейнера и документа контейнера.|
|[Иолеобжектимпл:: Сетмоникер](#setmoniker)|Указывает элементу управления, что это моникер. Реализация ATL возвращает значение E_NOTIMPL.|
|[Иолеобжектимпл:: unadvise](#unadvise)|Удаляет вспомогательное соединение с элементом управления.|
|[Иолеобжектимпл:: Update](#update)|Обновляет элемент управления. Реализация ATL возвращает значение S_OK.|

## <a name="remarks"></a>Примечания

Интерфейс [иолеобжект](/windows/win32/api/oleidl/nn-oleidl-ioleobject) — это основной интерфейс, через который контейнер взаимодействует с элементом управления. Класс `IOleObjectImpl` предоставляет реализацию этого интерфейса по умолчанию и реализует `IUnknown` , отправляя сведения в устройство дампа в отладочных сборках.

**Связанные статьи** [Учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

##  <a name="advise"></a>Иолеобжектимпл:: Advise

Устанавливает вспомогательное соединение с элементом управления.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) в Windows SDK.

##  <a name="close"></a>Иолеобжектимпл:: Close

Изменяет состояние элемента управления с "работает" на "Загружено".

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>Примечания

Деактивирует элемент управления и удаляет окно элемента управления, если оно существует. Если элемент данных класса элемента управления [ккомконтролбасе:: m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) имеет значение true, а параметр *двсавеоптион* — OLECLOSE_SAVEIFDIRTY или OLECLOSE_PROMPTSAVE, свойства элемента управления сохраняются перед закрытием.

Указатели, удерживаемые в элементах данных класса Control [ккомконтролбасе:: m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) и [Ккомконтролбасе:: m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) , освобождаются, а элементы данных [ккомконтролбасе:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [ккомконтролбасе:: m_ Бвндлесс](../../atl/reference/ccomcontrolbase-class.md#m_bwndless)и [ккомконтролбасе:: m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) имеют значение false.

См. раздел [иолеобжект:: Close](/windows/win32/api/oleidl/nf-oleidl-ioleobject-close) в Windows SDK.

##  <a name="doverb"></a>Иолеобжектимпл::D Оверб

Указывает элементу управления выполнить одно из его перечисленных действий.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>Примечания

В зависимости от значения `iVerb`, одна из вспомогательных функций ATL `DoVerb` вызывается следующим образом:

|*иверб* Значений|Вызвана вспомогательная функция Доверб|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[довербдискардундо](#doverbdiscardundo)|
|OLEIVERB_HIDE|[довербхиде](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[довербинплацеактивате](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[довербопен](#doverbopen)|
|OLEIVERB_PRIMARY|[довербпримари](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[довербшов](#doverbshow)|
|OLEIVERB_UIACTIVATE|[довербуиактивате](#doverbuiactivate)|

См. раздел [иолеобжект::D оверб](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

##  <a name="doverbdiscardundo"></a>Иолеобжектимпл::D Овербдискардундо

Указывает элементу управления отменить любое состояние отмены, которое оно обслуживает.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="doverbhide"></a>Иолеобжектимпл::D Овербхиде

Деактивирует и удаляет пользовательский интерфейс элемента управления и скрывает элемент управления.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="doverbinplaceactivate"></a>Иолеобжектимпл::D Овербинплацеактивате

Запускает элемент управления и устанавливает его окно, но не устанавливает пользовательский интерфейс элемента управления.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Активирует элемент управления на месте путем вызова [ккомконтролбасе:: инплацеактивате](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Если элемент данных `m_bWindowOnly` класса элемента управления не имеет значения true `DoVerbInPlaceActivate` , сначала пытается активировать элемент управления как безоконный (возможно только в том случае, если контейнер поддерживает [иолеинплацеситевиндовлесс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless)). Если это не удается, функция пытается активировать элемент управления с помощью расширенных функций (возможно, только если контейнер поддерживает [иолеинплацеситикс](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)). Если это не удается, функция пытается активировать элемент управления без расширенных функций (возможно только в том случае, если контейнер поддерживает [иолеинплацесите](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)). Если активация прошла успешно, функция уведомляет контейнер, что элемент управления был активирован.

##  <a name="doverbopen"></a>Иолеобжектимпл::D Овербопен

Приводит к открытию элемента управления для редактирования в отдельном окне.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="doverbprimary"></a>Иолеобжектимпл::D Овербпримари

Определяет действие, выполняемое при двойном щелчке элемента управления пользователем.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

По умолчанию задано отображение страниц свойств. Это можно переопределить в классе элемента управления, чтобы вызвать другое поведение при двойном щелчке. Например, воспроизведение видео или переход по месту на месте.

##  <a name="doverbshow"></a>Иолеобжектимпл::D Овербшов

Указывает контейнеру, что элемент управления должен быть видимым.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

##  <a name="doverbuiactivate"></a>Иолеобжектимпл::D Овербуиактивате

Активирует пользовательский интерфейс элемента управления и уведомляет контейнер о том, что его меню заменяются составными меню.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>Параметры

*пркпосрек*<br/>
окне Указатель на прямоугольник, в который контейнер хочет нарисовать элемент управления.

*хвндпарент*<br/>
окне Маркер окна, содержащего элемент управления. Не используется в реализации ATL.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

##  <a name="enumadvise"></a>Иолеобжектимпл:: Енумадвисе

Предоставляет перечисление зарегистрированных вспомогательных соединений для этого элемента управления.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: енумадвисе](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumadvise) в Windows SDK.

##  <a name="enumverbs"></a>Иолеобжектимпл:: Енумвербс

Предоставляет перечисление зарегистрированных действий (глаголов) для этого элемента управления путем `OleRegEnumVerbs`вызова метода.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>Примечания

Вы можете добавлять команды в rgsный файл проекта. Например, см. раздел ЦИРККТЛ. RGS в образце [Circ](../../overview/visual-cpp-samples.md) .

См. раздел [иолеобжект:: енумвербс](/windows/win32/api/oleidl/nf-oleidl-ioleobject-enumverbs) в Windows SDK.

##  <a name="getclientsite"></a>Иолеобжектимпл:: Жетклиентсите

Помещает указатель в элемент данных класса элемента управления [ккомконтролбасе:: m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) в *ппклиентсите* и увеличивает счетчик ссылок на указатель.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: жетклиентсите](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclientsite) в Windows SDK.

##  <a name="getclipboarddata"></a>Иолеобжектимпл:: Жетклипбоарддата

Извлекает данные из буфера обмена.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: жетклипбоарддата](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) в Windows SDK.

##  <a name="getextent"></a>Иолеобжектимпл:: расширение

Получает отображаемый размер выполняемого элемента управления в единицах HIMETRIC (0,01 мм на единицу).

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Примечания

Размер хранится в элементе управления Data Control Member [ккомконтролбасе:: m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).

См. раздел [иолеобжект:: "](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getextent) в Windows SDK.

##  <a name="getmiscstatus"></a>Иолеобжектимпл:: Жетмискстатус

Возвращает указатель на зарегистрированную информацию о состоянии для элемента управления путем `OleRegGetMiscStatus`вызова.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>Примечания

Сведения о состоянии включают варианты поведения, поддерживаемые элементом управления и данными представления. Вы можете добавить сведения о состоянии в rgsный файл проекта.

См. раздел [иолеобжект:: жетмискстатус](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) в Windows SDK.

##  <a name="getmoniker"></a>Иолеобжектимпл:: моникер

Извлекает моникер элемента управления.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. [иолеобжект:: a моникер](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmoniker) в Windows SDK.

##  <a name="getuserclassid"></a>Иолеобжектимпл:: Жетусерклассид

Возвращает идентификатор класса элемента управления.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: жетусерклассид](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getuserclassid) в Windows SDK.

##  <a name="getusertype"></a>Иолеобжектимпл:: Жетусертипе

Возвращает имя пользовательского типа элемента управления путем вызова `OleRegGetUserType`.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>Примечания

Имя типа пользователя используется для вывода элементов пользовательского интерфейса, например меню и диалоговых окон. Имя пользовательского типа можно изменить в RGS-файле проекта.

См. раздел [иолеобжект:: жетусертипе](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getusertype) в Windows SDK.

##  <a name="initfromdata"></a>Иолеобжектимпл:: Инитфромдата

Инициализирует элемент управления из выбранных данных.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: инитфромдата](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) в Windows SDK.

##  <a name="isuptodate"></a>Иолеобжектимпл:: Исуптодате

Проверяет, является ли элемент управления актуальным.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: исуптодате](/windows/win32/api/oleidl/nf-oleidl-ioleobject-isuptodate) в Windows SDK.

##  <a name="onpostverbdiscardundo"></a>Иолеобжектимпл:: Онпоствербдискардундо

Вызывается методом [довербдискардундо](#doverbdiscardundo) после отклонения состояния отмены.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после удаления состояния отмены.

##  <a name="onpostverbhide"></a>Иолеобжектимпл:: Онпоствербхиде

Вызывается методом [довербхиде](#doverbhide) после скрытия элемента управления.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после скрытия элемента управления.

##  <a name="onpostverbinplaceactivate"></a>Иолеобжектимпл:: Онпоствербинплацеактивате

Вызывается методом [довербинплацеактивате](#doverbinplaceactivate) после активации элемента управления на месте.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после того, как элемент управления будет активирован на месте.

##  <a name="onpostverbopen"></a>Иолеобжектимпл:: Онпоствербопен

Вызывается методом [довербопен](#doverbopen) после открытия элемента управления для редактирования в отдельном окне.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после открытия элемента управления для редактирования в отдельном окне.

##  <a name="onpostverbshow"></a>Иолеобжектимпл:: Онпоствербшов

Вызывается методом [довербшов](#doverbshow) после того, как элемент управления стал видимым.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после того, как элемент управления станет видимым.

##  <a name="onpostverbuiactivate"></a>Иолеобжектимпл:: Онпоствербуиактивате

Вызывается методом [довербуиактивате](#doverbuiactivate) после активации пользовательского интерфейса элемента управления.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Переопределите этот метод с помощью кода, который должен выполняться после активации пользовательского интерфейса элемента управления.

##  <a name="onpreverbdiscardundo"></a>Иолеобжектимпл:: Онпревербдискардундо

Вызывается методом [довербдискардундо](#doverbdiscardundo) , прежде чем состояние отмены отклоняется.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить отклонения состояния отмены, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide

Вызывается методом [довербхиде](#doverbhide) перед скрытием элемента управления.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить скрытие элемента управления, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="onpreverbinplaceactivate"></a>Иолеобжектимпл:: Онпревербинплацеактивате

Вызывается методом [довербинплацеактивате](#doverbinplaceactivate) перед активацией элемента управления на месте.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить активацию элемента управления на месте, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="onpreverbopen"></a>Иолеобжектимпл:: Онпревербопен

Вызывается методом [довербопен](#doverbopen) перед открытием элемента управления для редактирования в отдельном окне.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить открытие элемента управления для редактирования в отдельном окне, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="onpreverbshow"></a>Иолеобжектимпл:: Онпревербшов

Вызывается методом [довербшов](#doverbshow) , прежде чем элемент управления станет видимым.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить видимость элемента управления, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="onpreverbuiactivate"></a>Иолеобжектимпл:: Онпревербуиактивате

Вызывается методом [довербуиактивате](#doverbuiactivate) перед активацией пользовательского интерфейса элемента управления.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Чтобы предотвратить активацию пользовательского интерфейса элемента управления, Переопределите этот метод, чтобы он возвращал ошибку HRESULT.

##  <a name="setclientsite"></a>Иолеобжектимпл:: Сетклиентсите

Сообщает элементу управления о своем клиентском сайте в контейнере.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>Примечания

Затем метод возвращает значение S_OK.

См. раздел [иолеобжект:: сетклиентсите](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setclientsite) в Windows SDK.

##  <a name="setcolorscheme"></a>Иолеобжектимпл:: Сетколорсчеме

Рекомендует использовать цветовую схему для приложения элемента управления, если таковая имеется.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: сетколорсчеме](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) в Windows SDK.

##  <a name="setextent"></a>Иолеобжектимпл:: Сетекстент

Задает экстент отображаемой области элемента управления.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>Примечания

В противном случае `SetExtent` сохраняет значение, на которое указывает `psizel`, в элементе управления Data класса Member [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Это значение находится в единицах HIMETRIC (0,01 мм на единицу).

Если элемент данных класса элемента управления [ккомконтролбасе:: m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) имеет значение true `SetExtent` , также сохраняет значения, на которые `psizel` указывает, в элементе управления элемент данных класса Control [ккомконтролбасе:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).

Если элемент данных класса элемента управления [ккомконтролбасе:: m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) имеет значение true `SetExtent` , `SendOnDataChange` вызывает `SendOnViewChange` и, чтобы уведомить все приемники уведомлений, зарегистрированные с помощью держателя рекомендаций, что размер элемента управления изменился.

См. раздел [иолеобжект:: сетекстент](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setextent) в Windows SDK.

##  <a name="sethostnames"></a>Иолеобжектимпл:: Сесостнамес

Сообщает элементу управления имена приложения контейнера и документа контейнера.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: сесостнамес](/windows/win32/api/oleidl/nf-oleidl-ioleobject-sethostnames) в Windows SDK.

##  <a name="setmoniker"></a>Иолеобжектимпл:: Сетмоникер

Указывает элементу управления, что это моникер.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOTIMPL.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: сетмоникер](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setmoniker) в Windows SDK.

##  <a name="unadvise"></a>Иолеобжектимпл:: unadvise

Удаляет вспомогательное соединение, `m_spOleAdviseHolder` хранящееся в элементе данных класса элемента управления.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) в Windows SDK.

##  <a name="update"></a>Иолеобжектимпл:: Update

Обновляет элемент управления.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

### <a name="remarks"></a>Примечания

См. раздел [иолеобжект:: Update](/windows/win32/api/oleidl/nf-oleidl-ioleobject-update) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс CComControl](../../atl/reference/ccomcontrol-class.md)<br/>
[Интерфейсы элементов управления ActiveX](/windows/win32/com/activex-controls-interfaces)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
