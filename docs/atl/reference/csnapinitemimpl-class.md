---
title: Класс CSnapInItemImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c56f8fe711980e038281baca7618bff08f0d3d9b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764947"
---
# <a name="csnapinitemimpl-class"></a>Класс CSnapInItemImpl

Этот класс предоставляет методы для реализации объект узла оснастки.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Параметры

*T*  
Ваш класс, производный от `CSnapInItemImpl`.

*bIsExtension*  
Значение TRUE, если объект является расширением оснастки; в противном случае — значение FALSE.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Добавляет пункты меню в контекстное меню.|
|[CSnapInItemImpl::Command](#command)|Вызывается средой консоли, когда выбран пользовательский пункт меню.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Добавляет страницы в лист свойств оснастки.|
|[CSnapInItemImpl::FillData](#filldata)|Копирует сведения об объекте оснастки в указанный поток.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Извлекает `RESULTDATAITEM` структуры оснастки.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Определяет тип представления, используемые на панели результатов.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Извлекает `SCOPEDATAITEM` структуры оснастки.|
|[CSnapInItemImpl::Notify](#notify)|Вызывается средой консоли, чтобы уведомить оснастки действий, выполняемых пользователем.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Вызывается, чтобы определить, поддерживает ли узел оснастки страницы свойств.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Изменяет флаги вставки меню для объекта оснастки.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Задает сведения о указанной кнопки панели инструментов.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Обновляет состояние для контекстного меню.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Обновляет состояние для указанной кнопки панели инструментов.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Имя объекта оснастки.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows `RESULTDATAITEM` структуру, используемую `CSnapInItemImpl` объекта.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows `SCOPEDATAITEM` структуру, используемую `CSnapInItemImpl` объекта.|

## <a name="remarks"></a>Примечания

`CSnapInItemImpl` Предоставляет базовую реализацию для объекта оснастки узла, например добавление элементов меню и панелей инструментов и пересылки команд для узла – – оснастка к соответствующим функциям обработки. Эти возможности реализуются с помощью нескольких различных интерфейсов и сопоставления типов. Реализация по умолчанию обрабатывает уведомления, отправляемые объект узла путем определения правильного экземпляра производного класса, а затем пересылки сообщения к нужному экземпляру.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems

Этот метод реализует функцию Win32 [IExtendContextMenu::AddMenuItems](https://msdn.microsoft.com/library/aa814841).

```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*piCallback*  
[in] Указатель на `IContextMenuCallback` , способную добавлять пункты в контекстное меню.

*pInsertionAllowed*  
[in, out] Идентифицирует определенные в консоли управления MMC, пункт меню точки вставки, которые могут использоваться. Это может быть сочетанием следующих флагов:

- CCM_INSERTIONALLOWED_TOP элементы могут быть вставлены в верхней части контекстного меню.

- CCM_INSERTIONALLOWED_NEW элементы могут вставляться в подменю «создать».

- CCM_INSERTIONALLOWED_TASK элементы могут вставляться в подменю «задача».

- Можно вставлять элементы CCM_INSERTIONALLOWED_VIEW, в меню "Вид" панели инструментов или в представлении подменю контекстное меню панели результатов.

*type*  
[in] Указывает тип объекта. Он может иметь одно из следующих значений:

- Объект данных CCT_SCOPE для контекста панели области.

- Объект данных CCT_RESULT для области контекст результата.

- Объект данных CCT_SNAPIN_MANAGER для оснастки диспетчера контекста.

- Объект данных CCT_UNINITIALIZED имеет недопустимый тип.

##  <a name="command"></a>  CSnapInItemImpl::Command

Этот метод реализует функцию Win32 [IExtendContextMenu::Command](https://msdn.microsoft.com/library/aa814842).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*lCommandID*  
[in] Указывает идентификатор команды этого пункта меню.

*type*  
[in] Указывает тип объекта. Он может иметь одно из следующих значений:

- Объект данных CCT_SCOPE для контекста панели области.

- Объект данных CCT_RESULT для области контекст результата.

- Объект данных CCT_SNAPIN_MANAGER для оснастки диспетчера контекста.

- Объект данных CCT_UNINITIALIZED имеет недопустимый тип.

##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages

Этот метод реализует функцию Win32 [IExtendPropertySheet::CreatePropertyPages](https://msdn.microsoft.com/library/aa814846).

```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*lpProvider*  
[in] Указатель на `IPropertySheetCallback` интерфейс.

*Дескриптор*  
[in] Указывает дескриптор, используемый для отправки уведомляющего сообщения MMCN_PROPERTY_CHANGE в класс соответствующие данные.

*pUnk*  
[in] Указатель на `IExtendPropertySheet` интерфейса на объект, содержащий контекстные сведения об узле.

*type*  
[in] Указывает тип объекта. Он может иметь одно из следующих значений:

- Объект данных CCT_SCOPE для контекста панели области.

- Объект данных CCT_RESULT для области контекст результата.

- Объект данных CCT_SNAPIN_MANAGER для оснастки диспетчера контекста.

- Объект данных CCT_UNINITIALIZED имеет недопустимый тип.

##  <a name="csnapinitemimpl"></a>  CSnapInItemImpl::CSnapInItemImpl

Создает объект `CSnapInItemImpl`.

```
CSnapInItemImpl();
```

##  <a name="filldata"></a>  CSnapInItemImpl::FillData

Эта функция вызывается для получения сведений об элементе.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Параметры

*CF*  
[in] Формат (текст, форматированного текста или форматированного текста с помощью элементов OLE) буфера обмена.

*pStream*  
[in] Указатель на поток, содержащий данные объекта.

### <a name="remarks"></a>Примечания

Чтобы правильно реализовать эту функцию, скопируйте правильные данные в поток (*pStream*), в зависимости от формате буфера обмена, указываемом *cf*.

##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType

Вызывайте эту функцию для извлечения типа представления для результатов объекта оснастки.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Параметры

*ppViewType*  
[out] Указатель на адрес типа возвращаемого представления.

*pViewOptions*  
[out] Указатель на MMC_VIEW_OPTIONS перечисления, который предоставляет консоль с характеристиками, заданными параметром-владельца оснастки. Это значение может быть одно из следующих значений:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 указывает воздержаться от представления стандартного списка вариантов представления в консоли **представление** меню. Позволяет оснастку для отображения свои собственные пользовательские представления только в области представления результатов. Это единственный флага, определенные в данный момент.

- MMC_VIEW_OPTIONS_NONE = 0 разрешает параметры представления по умолчанию.

##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo

Вызывайте эту функцию для получения `SCOPEDATAITEM` структуры оснастки.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Параметры

*pScopeDataItem*  
[out] Указатель на `SCOPEDATAITEM` структуры `CSnapInItemImpl` объекта.

##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo

Вызывайте эту функцию для получения `RESULTDATAITEM` структуры оснастки.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Параметры

*pResultDataItem*  
[out] Указатель на `RESULTDATAITEM` структуры `CSnapInItemImpl` объекта.

##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName

Содержит строка, отображаемая для элемента узла.

```
CComBSTR m_bstrDisplayName;
```

##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem

`SCOPEDATAITEM` Структуру объекта данных оснастки.

```
SCOPEDATAITEM m_scopeDataItem;
```

##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem

[RESULTDATAITEM](https://msdn.microsoft.com/library/aa815165) структуру объекта данных оснастки.

```
RESULTDATAITEM m_resultDataItem;
```

##  <a name="notify"></a>  CSnapInItemImpl::Notify

Вызывается, когда объект оснастки обрабатываемое пользователем.

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>Параметры

*event*  
[in] Определяет действие, выполненное пользователем. Возможны следующие уведомления:

- MMCN_ACTIVATE отправляется, когда окно, активации и деактивации.

- MMCN_ADD_IMAGES отправляемые Добавление изображений в области результатов.

- MMCN_BTN_CLICK отправляется, когда пользователь нажимает одну из кнопок панели инструментов.

- MMCN_CLICK отправляется, когда пользователь нажимает кнопку мыши на элемент представления списка.

- MMCN_DBLCLICK отправляется, когда пользователь дважды щелкает кнопкой мыши на элемент представления списка.

- MMCN_DELETE отправлено для информирования оснастки, который объект должен быть удален.

- MMCN_EXPAND отправляется, когда папку необходимо разворачивать и сворачивать.

- MMCN_MINIMIZED отправляется, когда окно будет свернуто или развернуто на весь экран.

- MMCN_PROPERTY_CHANGE получать уведомление объект оснастки, представление объекта оснастки будет изменена.

- MMCN_REMOVE_CHILDREN отправляется, когда необходимо удалить все поддерево эта оснастка в него добавлена ниже указанного узла.

- MMCN_RENAME отправляются в первый раз запрос для переименования, а второй раз, чтобы выполнить переименование.

- При выборе элемента в области представления области или результирующем отправить MMCN_SELECT.

- MMCN_SHOW отправляется, когда элемент области является выделением или отменой выделения в первый раз.

- MMCN_VIEW_CHANGE отправляется, когда оснастки можно обновить все представления при внесении изменений.

*arg*  
[in] Зависит от типа уведомления.

*param*  
[in] Зависит от типа уведомления.

*pComponentData*  
[out] Указатель на объект, реализующий интерфейс `IComponentData`. Этот параметр имеет значение NULL, если уведомление не перенаправляется из `IComponentData::Notify`.

*pComponent*  
[out] Указатель на объект, реализующий `IComponent`. Этот параметр имеет значение NULL, если уведомление не перенаправляется из `IComponent::Notify`.

*type*  
[in] Указывает тип объекта. Он может иметь одно из следующих значений:

- Объект данных CCT_SCOPE для контекста панели области.

- Объект данных CCT_RESULT для области контекст результата.

- Объект данных CCT_SNAPIN_MANAGER для оснастки диспетчера контекста.

- Объект данных CCT_UNINITIALIZED имеет недопустимый тип.

##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor

Вызывается, чтобы определить, поддерживает ли узел оснастки страницы свойств.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags

Вызывайте эту функцию, чтобы изменить меню вставки флаги, заданные *pInsertionAllowed*, для объекта оснастки.

```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Параметры

*bBeforeInsertion*  
[in] Ненулевое значение, если функция должна вызываться перед элементы добавляются в контекстное меню; в противном случае 0.

*pInsertionAllowed*  
[in, out] Идентифицирует определенные в консоли управления MMC, пункт меню точки вставки, которые могут использоваться. Это может быть сочетанием следующих флагов:

- CCM_INSERTIONALLOWED_TOP элементы могут быть вставлены в верхней части контекстного меню.

- CCM_INSERTIONALLOWED_NEW элементы могут вставляться в подменю «создать».

- CCM_INSERTIONALLOWED_TASK элементы могут вставляться в подменю «задача».

- Можно вставлять элементы CCM_INSERTIONALLOWED_VIEW, в меню "Вид" панели инструментов или в представлении подменю контекстное меню панели результатов.

### <a name="remarks"></a>Примечания

Если вы разрабатываете основная оснастка, вы можете сбросить любой из флагов вставки как способ ограничить тип команды меню, которые можно добавить в стороннем расширении. Например основная оснастка снять флаг CCM_INSERTIONALLOWED_NEW для расширения не могут добавлять свои собственные создать новые элементы меню.

Не следует пытаться установки битов в *pInsertionAllowed* , изначально были очищены. Будущие версии MMC может использовать bits, в настоящее время не определены, поэтому не следует изменять bits, которые в настоящее время не определены.

##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo

Вызывайте эту функцию, чтобы изменить все стили кнопок панели инструментов, объекта оснастки, перед созданием панели инструментов.

```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Параметры

*id*  
[in] Идентификатор кнопки панели инструментов, чтобы задать.

*fsState*  
[in] Флаги состояния кнопки. Может иметь одно или несколько из следующих:

- TBSTATE_CHECKED кнопки имеет стиль TBSTYLE_CHECKED и нажат.

- TBSTATE_ENABLED кнопки принимает входные данные пользователя. Кнопка, которая не поддерживает это состояние не принимает ввод данных пользователем и отображается серым цветом.

- TBSTATE_HIDDEN кнопка не отображается и не может принимать ввод данных пользователем.

- TBSTATE_INDETERMINATE кнопки отображается серым цветом.

- TBSTATE_PRESSED кнопка нажата.

- Разрыв строки типа TBSTATE_WRAP ниже кнопки. Кнопки необходимо также иметь TBSTATE_ENABLED.

*fsType*  
[in] Флаги состояния кнопки. Может иметь одно или несколько из следующих:

- TBSTYLE_BUTTON создает стандартные кнопки.

- Создает TBSTYLE_CHECK кнопки переключения между состояниями нажатого и нажата не каждый раз пользователь нажимает ее. Кнопка имеет другой цвет фона, когда он находится в нажатом состоянии.

- TBSTYLE_CHECKGROUP создает кнопку проверки, которая остается нажатия клавиш еще одну кнопку в группе.

- TBSTYLE_GROUP создает кнопку, которая остается нажатия клавиш еще одну кнопку в группе.

- TBSTYLE_SEP создает разделитель, предоставляя небольшой разрыв между группами кнопки. Кнопки, содержащей этот стиль не ввода данных пользователем.

##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState

Вызывайте эту функцию для изменения элемента меню перед его вставкой в контекстном меню объекта оснастки.

```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Параметры

*id*  
[in] Идентификатор элемента меню.

*pBuf*  
[in] Указатель на строку для обновляемого элемента меню.

*flags*  
[in] Указывает новые флаги состояния. Это может быть сочетанием следующих флагов:

- MF_POPUP указывает, что это меню, вложенного в контекстном меню. Элементы меню, положение курсора и дальнейшей подменю могут добавляться это подменю, используя его `lCommandID` как их `IInsertionPointID`.

- MF_BITMAP и MF_OWNERDRAW эти флаги не допускаются и будут приводить возвращаемое значение E_INVALIDARG.

- MF_SEPARATOR рисует горизонтальной разделительной линии. Только `IContextMenuProvider` разрешается добавление элементов меню с набором MF_SEPARATOR.

- MF_CHECKED устанавливает флажок рядом с элементом меню.

- Отключает MF_DISABLED пункта меню, поэтому он не может быть выбран, но этот флаг не серого цвета, его.

- MF_ENABLED включает элемент меню, чтобы ее можно выбрать, восстановив его из состояния затененный.

- MF_GRAYED отключает пункт меню, окраску в серый цвет его, не могут быть выбраны.

- Функции MF_MENUBARBREAK так же, как MF_MENUBREAK флаг для строки меню. Для раскрывающегося меню, подменю или контекстного меню новый столбец отделяется от старого вертикальной линией.

- MF_MENUBREAK помещает элемент на новой строке (для строки меню) или в новом столбце (для раскрывающегося меню, подменю или контекстного меню) без разделения столбцов.

- MF_UNCHECKED не помещает флажок рядом с элементом (по умолчанию).

Следующие группы флаги не предусматривают совместное использование:

- MF_DISABLED MF_ENABLED и MF_GRAYED.

- MF_MENUBARBREAK и MF_MENUBREAK.

- MF_CHECKED и MF_UNCHECKED.

##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton

Вызывайте эту функцию, чтобы изменить кнопки панели инструментов, объекта оснастки, перед его отображением.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Параметры

*id*  
Указывает идентификатор кнопки панели инструментов кнопку обновления.

*fsState*  
Указывает состояние кнопки панели инструментов. Если задать это состояние, возвращает значение TRUE. Это может быть сочетанием следующих флагов:

- ВКЛЮЧЕНО кнопки принимает ввод данных пользователем. Кнопка, которая не поддерживает это состояние не принимает ввод данных пользователем и отображается серым цветом.

- ПРОВЕРЯЕТСЯ, УСТАНОВЛЕН стиль кнопки и нажат.

- HIDDEN кнопка не отображается и не может принимать ввод данных пользователем.

- НЕОПРЕДЕЛЕННОЕ кнопки отображается серым цветом.

- BUTTONPRESSED кнопка нажата.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
