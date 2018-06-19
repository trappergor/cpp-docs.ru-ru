---
title: Класс CSnapInItemImpl | Документы Microsoft
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
ms.openlocfilehash: 759917497f06f80cde97f4e1bba9f3711add94a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366462"
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
 `T`  
 Класс, производный от `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **Значение TRUE,** Если объект является расширением оснастки; в противном случае **FALSE**.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Добавляет пункты меню в контекстное меню.|  
|[CSnapInItemImpl::Command](#command)|Вызывается средой консоль, при выборе пункта меню.|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Добавляет страницы свойств оснастки.|  
|[CSnapInItemImpl::FillData](#filldata)|Копирует сведения об объекте оснастки в указанном потоке.|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Извлекает **RESULTDATAITEM** структуры оснастки.|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Определяет тип представления, используемые на панели «результат».|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Извлекает **SCOPEDATAITEM** структуры оснастки.|  
|[CSnapInItemImpl::Notify](#notify)|Вызывается средой консоль, чтобы уведомить оснастку для действий со стороны пользователя.|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Вызывается, чтобы узнать, поддерживает ли узел оснастки страницы свойств.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Изменяет флаги вставки меню для объекта оснастки.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Задает сведения о указанную кнопку панели инструментов.|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Обновляет состояние пункта контекстного меню.|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Обновляет состояние указанную кнопку панели инструментов.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Имя объекта оснастки.|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows **RESULTDATAITEM** структура, используемая `CSnapInItemImpl` объекта.|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows **SCOPEDATAITEM** структура, используемая `CSnapInItemImpl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CSnapInItemImpl` Предоставляет базовую реализацию для объекта оснастки узла, например добавление пунктов меню и панелей инструментов и команд для узла оснастки в соответствующий обработчик функцию перенаправления. Эти возможности реализуются с помощью нескольких разных интерфейсов и сопоставления типов. Реализация по умолчанию обрабатывает уведомлений, отправляемых путем определения правильный экземпляр производного класса, а затем перенаправить сообщение на правильный экземпляр объекта узла.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h  
  
##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems  
 Этот метод реализует функцию Win32 [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841).  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Параметры  
 *piCallback*  
 [in] Указатель на **IContextMenuCallback** , добавление элементов в контекстном меню.  
  
 `pInsertionAllowed`  
 [in, out] Определяет определено в консоли управления MMC, пункт меню вставки точки, которые можно использовать. Это может быть сочетанием следующих флагов:  
  
- **CCM_INSERTIONALLOWED_TOP** может вставлять элементы в верхней части контекстного меню.  
  
- **CCM_INSERTIONALLOWED_NEW** может вставлять элементы в подменю «создать».  
  
- **CCM_INSERTIONALLOWED_TASK** может вставлять элементы в подменю «задача».  
  
- **CCM_INSERTIONALLOWED_VIEW** может вставлять элементы в меню «Вид» панели инструментов или в подменю представление контекстного меню панели результатов.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объект данных для области контекст области.  
  
- **CCT_RESULT** объект данных для области контекст результата.  
  
- **CCT_SNAPIN_MANAGER** объект данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="command"></a>  CSnapInItemImpl::Command  
 Этот метод реализует функцию Win32 [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842).  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Параметры  
 *lCommandID*  
 [in] Указывает идентификатор команды для элемента меню.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объект данных для области контекст области.  
  
- **CCT_RESULT** объект данных для области контекст результата.  
  
- **CCT_SNAPIN_MANAGER** объект данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages  
 Этот метод реализует функцию Win32 [IExtendPropertySheet::CreatePropertyPages](http://msdn.microsoft.com/library/aa814846).  
  
```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Параметры  
 *lpProvider*  
 [in] Указатель на **IPropertySheetCallback** интерфейса.  
  
 *Дескриптор*  
 [in] Указывает дескриптор, используемый для маршрута **MMCN_PROPERTY_CHANGE** сообщения уведомления в класс соответствующие данные.  
  
 *pUnk*  
 [in] Указатель на **IExtendPropertySheet** интерфейса на объект, содержащий контекстные сведения об узле.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объект данных для области контекст области.  
  
- **CCT_RESULT** объект данных для области контекст результата.  
  
- **CCT_SNAPIN_MANAGER** объект данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
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
 `cf`  
 [in] Формат (текст форматированного текста и форматированного текста с OLE-элементы) из буфера обмена.  
  
 `pStream`  
 [in] Указатель на поток, содержащий данные объекта.  
  
### <a name="remarks"></a>Примечания  
 Чтобы правильно реализовать эту функцию, скопируйте правильные сведения в поток ( `pStream`), в зависимости от формата буфера обмена, обозначенном `cf`.  
  
##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType  
 Вызывайте эту функцию для извлечения типа представления для объекта оснастки панель результатов.  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>Параметры  
 *ppViewType*  
 [out] Указатель на адрес тип возвращаемого представления.  
  
 *pViewOptions*  
 [out] Указатель на **MMC_VIEW_OPTIONS** перечисления, который предоставляет консоль с параметрами, заданными владельца оснасткой. Это значение может быть одним из следующих:  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0x00000001 сообщает консоли отказ от предоставления стандартный список вариантов представления в **представление** меню. Позволяет оснастку для отображения только на панели представления результатов свои собственные пользовательские представления. Это только флага, определенные в данный момент.  
  
- **MMC_VIEW_OPTIONS_NONE** = 0 позволяет параметры представления по умолчанию.  
  
##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo  
 Эта функция вызывается для получения **SCOPEDATAITEM** структуры оснастки.  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pScopeDataItem*  
 [out] Указатель на **SCOPEDATAITEM** структуры `CSnapInItemImpl` объекта.  
  
##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo  
 Эта функция вызывается для получения **RESULTDATAITEM** структуры оснастки.  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pResultDataItem*  
 [out] Указатель на **RESULTDATAITEM** структуры `CSnapInItemImpl` объекта.  
  
##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName  
 Содержит строку, отображаемую для элемента узла.  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem  
 `SCOPEDATAITEM` Структура объекта данных оснастки.  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem  
 [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165) структуру объекта данных оснастки.  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>  CSnapInItemImpl::Notify  
 Вызывается, когда объект оснастки ответных пользователем.  
  
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
 `event`  
 [in] Определяет действие, выполненное пользователем. Возможны следующие уведомления:  
  
- **MMCN_ACTIVATE** отправляется, когда окно является активации и деактивации.  
  
- **MMCN_ADD_IMAGES** отправлено Добавление изображения на панель «результат».  
  
- **MMCN_BTN_CLICK** посылается, когда пользователь нажимает одну из кнопок панели инструментов.  
  
- **MMCN_CLICK** посылается, когда пользователь нажимает кнопку мыши на элемент представления списка.  
  
- **MMCN_DBLCLICK** посылается, когда пользователь дважды щелкает мышью для элемента представления списка.  
  
- **MMCN_DELETE** отправлено для информирования оснастки, объект должен быть удален.  
  
- **MMCN_EXPAND** отправляется, когда папку необходимо разворачивать и сворачивать.  
  
- **MMCN_MINIMIZED** отправляется, когда окно является Свертывание или развертывание.  
  
- **MMCN_PROPERTY_CHANGE** предупреждения объект оснастки, представление объектов оснастки будет изменена.  
  
- **MMCN_REMOVE_CHILDREN** отправляется, когда оснастка необходимо удалить все поддерево, она добавлена ниже указанного узла.  
  
- **MMCN_RENAME** делать переименования, отправляемые в первый раз и запрос для переименования и второй раз.  
  
- **MMCN_SELECT** отправляется, когда выбран элемент в области представления области или результат.  
  
- **MMCN_SHOW** отправляется, когда выбирается элемент области или выбран в первый раз.  
  
- **MMCN_VIEW_CHANGE** отправляется, когда оснастки можно обновить все представления при изменении.  
  
 `arg`  
 [in] Зависит от типа уведомления.  
  
 `param`  
 [in] Зависит от типа уведомления.  
  
 *pComponentData*  
 [out] Указатель на объект, реализующий **IComponentData**. Этот параметр является **NULL** Если уведомления не направляются от **IComponentData::Notify**.  
  
 *pComponent*  
 [out] Указатель на объект, реализующий **IComponent**. Этот параметр является **NULL** Если уведомления не направляются от **IComponent::Notify**.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объект данных для области контекст области.  
  
- **CCT_RESULT** объект данных для области контекст результата.  
  
- **CCT_SNAPIN_MANAGER** объект данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor  
 Вызывается, чтобы узнать, поддерживает ли узел оснастки страницы свойств.  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags  
 Вызывайте эту функцию, чтобы изменить меню вставки флаги, заданные `pInsertionAllowed`, для объекта оснастки.  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>Параметры  
 *bBeforeInsertion*  
 [in] Ненулевое значение, если функция должна вызываться перед элементы добавляются в контекстное меню; в противном случае — 0.  
  
 `pInsertionAllowed`  
 [in, out] Определяет определено в консоли управления MMC, пункт меню вставки точки, которые можно использовать. Это может быть сочетанием следующих флагов:  
  
- **CCM_INSERTIONALLOWED_TOP** может вставлять элементы в верхней части контекстного меню.  
  
- **CCM_INSERTIONALLOWED_NEW** может вставлять элементы в подменю «создать».  
  
- **CCM_INSERTIONALLOWED_TASK** может вставлять элементы в подменю «задача».  
  
- **CCM_INSERTIONALLOWED_VIEW** может вставлять элементы в меню «Вид» панели инструментов или в подменю представление контекстного меню панели результатов.  
  
### <a name="remarks"></a>Примечания  
 При разработке основной оснастки можно сбросить любые из флагов вставки как способ ограничить вид меню, которые можно добавить расширение сторонних разработчиков. Например, основная оснастка можно очистить **CCM_INSERTIONALLOWED_NEW** флаг для предотвращения добавления своих собственных создать новые пункты меню расширения.  
  
 Не следует пытаться установки битов в `pInsertionAllowed` , изначально были очищены. Будущие версии MMC может использовать bits, в настоящее время не определен, поэтому не следует изменять битов, которые в настоящее время не определены.  
  
##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo  
 Эта функция вызывается для изменения любого стиля кнопок панели инструментов объекта оснастки до создания панели инструментов.  
  
```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Кнопки панели инструментов, которому присваивается идентификатор.  
  
 `fsState`  
 [in] Флаги состояния кнопки. Может иметь одно или несколько из следующих:  
  
- `TBSTATE_CHECKED` Эта кнопка имеет **TBSTYLE_CHECKED** стиля и нажат.  
  
- `TBSTATE_ENABLED` Кнопки, принимающее вводимые пользователем данные. Кнопка, которая не поддерживает это состояние не принимает ввод данных пользователем и отображается серым цветом.  
  
- `TBSTATE_HIDDEN` Кнопка не отображается и не может реагировать на действия пользователя.  
  
- `TBSTATE_INDETERMINATE` Кнопка отображается серым цветом.  
  
- `TBSTATE_PRESSED` Кнопка нажата.  
  
- `TBSTATE_WRAP` Кнопки ставится разрыв строки. Кнопки также должен иметь `TBSTATE_ENABLED`.  
  
 *Тип_файловой_системы*  
 [in] Флаги состояния кнопки. Может иметь одно или несколько из следующих:  
  
- `TBSTYLE_BUTTON` Создает стандартные клавиши.  
  
- `TBSTYLE_CHECK` Создает кнопку переключения между нажатия и не нажата состояния при каждом щелчке по нему. Эта кнопка имеет другой цвет фона, когда он находится в нажатом состоянии.  
  
- `TBSTYLE_CHECKGROUP` Создает кнопку с галочкой, остается в нажатом положении, пока не нажата кнопка другой группы.  
  
- `TBSTYLE_GROUP` Создает кнопку, которая остается в нажатом положении, пока не нажата кнопка другой группы.  
  
- `TBSTYLE_SEP` Создает разделителя, предоставляя небольшой разрыв между группы кнопок. Кнопки, которая имеет этот стиль не реагировать на действия пользователя.  
  
##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState  
 Эта функция вызывается для изменения пункта меню перед его вставкой в контекстное меню объекта оснастки.  
  
```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 [in] Идентификатор элемента меню.  
  
 `pBuf`  
 [in] Указатель на строку для пункт меню, чтобы обновить.  
  
 `flags`  
 [in] Указывает новый флаги состояния. Это может быть сочетанием следующих флагов:  
  
- **MF_POPUP** указывает, что это меню, вложенного в контекстном меню. Пункты меню, положение курсора и дальнейшей подменю могут быть добавлены в этом подменю с помощью его **lCommandID** как их **IInsertionPointID**.  
  
- **MF_BITMAP** и `MF_OWNERDRAW` эти флаги запрещено и приведет к возвращаемым значением `E_INVALIDARG`.  
  
- **MF_SEPARATOR** рисует горизонтальной разделительной линии. Только **IContextMenuProvider** разрешается добавление элементов меню с помощью **MF_SEPARATOR** значение.  
  
- **MF_CHECKED** устанавливает флажок рядом с пунктом меню.  
  
- **MF_DISABLED** отключает пункт меню, чтобы он не может быть выбран, но флаг не серого цвета, его.  
  
- `MF_ENABLED` Включает элемент меню, ее можно будет выбрать, восстановив его из состояния выделена серым цветом.  
  
- **MF_GRAYED** отключает пункт меню, неподходящие идентификаторы, не могут быть выбраны.  
  
- **MF_MENUBARBREAK** работает так же, как **MF_MENUBREAK** флаг для строки меню. Раскрывающееся меню, подменю или контекстного меню новый столбец отделяется от старого вертикальной линией.  
  
- **MF_MENUBREAK** размещает элемент на новую строку (для строки меню) или в новом столбце (для раскрывающееся меню, подменю или контекстного меню) без разделения столбцов.  
  
- **MF_UNCHECKED** не установлен флажок рядом с элементом (по умолчанию).  
  
 Следующие группы флаги не могут использоваться совместно:  
  
- **MF_DISABLED**, `MF_ENABLED`, и **MF_GRAYED**.  
  
- **MF_MENUBARBREAK** и **MF_MENUBREAK**.  
  
- **MF_CHECKED** и **MF_UNCHECKED**.  
  
##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton  
 Вызывайте эту функцию, чтобы изменить кнопки панели инструментов, объекта оснастки, перед отображением.  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 Указывает идентификатор кнопки панели инструментов кнопку обновления.  
  
 `fsState`  
 Указывает состояние кнопки панели инструментов. Если это состояние, задаваемое возвращают **TRUE**. Это может быть сочетанием следующих флагов:  
  
- **ВКЛЮЧИТЬ** кнопки, принимающее вводимые пользователем данные. Кнопка, которая не поддерживает это состояние не принимает ввод данных пользователем и отображается серым цветом.  
  
- **Проверка** кнопка имеет **ПРОВЕРЯЕТСЯ** стиля и нажат.  
  
- **СКРЫТЫЙ** кнопка не отображается и не может реагировать на действия пользователя.  
  
- **НЕОПРЕДЕЛЕННОЕ** кнопка отображается серым цветом.  
  
- **BUTTONPRESSED** нажатии кнопки.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
