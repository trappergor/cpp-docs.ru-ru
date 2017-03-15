---
title: "Класс CSnapInItemImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInItemImpl
- ATL.CSnapInItemImpl
- ATL::CSnapInItemImpl
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9148ee71ba03a1a0492d390378c64f988e6e0f39
ms.lasthandoff: 02/24/2017

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
 **Значение TRUE,** , если объект является расширением оснастки; в противном случае **FALSE**.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Добавляет пункты меню в контекстное меню.|  
|[CSnapInItemImpl::Command](#command)|При выборе пункта меню вызывается консоли.|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Добавляет страницы свойств оснастки.|  
|[CSnapInItemImpl::FillData](#filldata)|Копирует сведения об объекте оснастки в указанном потоке.|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Извлекает **RESULTDATAITEM** структуры оснастки.|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Определяет тип представления, используемые на панели «результат».|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Извлекает **SCOPEDATAITEM** структуры оснастки.|  
|[CSnapInItemImpl::Notify](#notify)|Вызывается из консоли, чтобы уведомить оснастки из действия, предпринятые пользователем.|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Вызывается, чтобы узнать, поддерживает ли узел оснастки страницы свойств.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Изменяет флаги меню вставки для объекта оснастки.|  
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
 `CSnapInItemImpl`Предоставляет базовую реализацию для объекта оснастки узел, например добавление элементов меню и панелей инструментов и пересылки команд для узла оснастки к соответствующим функциям обработки. Эти функции реализуются с помощью нескольких различных интерфейсов и сопоставления типов. Реализация по умолчанию обрабатывает уведомления, отправленные для объекта узла путем определения правильный экземпляр производного класса, а затем перенаправления сообщения к нужному экземпляру.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsnap.h  
  
##  <a name="a-nameaddmenuitemsa--csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a>CSnapInItemImpl::AddMenuItems  
 Этот метод реализует функцию Win32 [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841).  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Параметры  
 *piCallback*  
 [in] Указатель на **IContextMenuCallback** , можно добавить элементы в контекстное меню.  
  
 `pInsertionAllowed`  
 [in, out] Идентифицирует консоли управления MMC, определенные пункта меню вставки точки, которые можно использовать. Это может быть сочетанием флагов, следующие:  
  
- **CCM_INSERTIONALLOWED_TOP** элементы могут вставляться в верхней части контекстного меню.  
  
- **CCM_INSERTIONALLOWED_NEW** элементы могут быть вставлены в подменю «создать».  
  
- **CCM_INSERTIONALLOWED_TASK** элементы могут быть вставлены в подменю «задача».  
  
- **CCM_INSERTIONALLOWED_VIEW** можно вставлять элементы, в меню Вид панели инструментов или в подменю представление контекстного меню панели результатов.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объекта данных для области панели контекста.  
  
- **CCT_RESULT** объекта данных для контекста панели результатов.  
  
- **CCT_SNAPIN_MANAGER** объекта данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="a-namecommanda--csnapinitemimplcommand"></a><a name="command"></a>CSnapInItemImpl::Command  
 Этот метод реализует функцию Win32 [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842).  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Параметры  
 *lCommandID*  
 [in] Указывает идентификатор команды элемента меню.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объекта данных для области панели контекста.  
  
- **CCT_RESULT** объекта данных для контекста панели результатов.  
  
- **CCT_SNAPIN_MANAGER** объекта данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="a-namecreatepropertypagesa--csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages  
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
 [in] Указывает дескриптор, который используется для маршрута **MMCN_PROPERTY_CHANGE** уведомление в класс соответствующие данные.  
  
 *pUnk*  
 [in] Указатель на **IExtendPropertySheet** интерфейса на объект, содержащий контекстные сведения об узле.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объекта данных для области панели контекста.  
  
- **CCT_RESULT** объекта данных для контекста панели результатов.  
  
- **CCT_SNAPIN_MANAGER** объекта данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="a-namecsnapinitemimpla--csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl  
 Создает объект `CSnapInItemImpl`.  
  
```
CSnapInItemImpl();
```  
  
##  <a name="a-namefilldataa--csnapinitemimplfilldata"></a><a name="filldata"></a>CSnapInItemImpl::FillData  
 Эта функция вызывается для получения сведений об элементе.  
  
```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 [in] Формат (текст, форматированный текст или форматированный текст с OLE-элементы) из буфера обмена.  
  
 `pStream`  
 [in] Указатель на поток, содержащий данные объекта.  
  
### <a name="remarks"></a>Примечания  
 Для правильной реализации этой функции, скопируйте правильные сведения в поток ( `pStream`), в зависимости от формат буфера обмена, обозначенными `cf`.  
  
##  <a name="a-namegetresultviewtypea--csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType  
 Эта функция вызывается для получения типа представления для объекта оснастки панель результатов.  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>Параметры  
 *ppViewType*  
 [out] Указатель на адрес тип возвращаемого представления.  
  
 *pViewOptions*  
 [out] Указатель на **MMC_VIEW_OPTIONS** перечисления, которая предоставляет параметры, указанные владельца оснасткой консоли. Это значение может быть одним из следующих:  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0x00000001 сообщает воздержаться от представления стандартный список вариантов представления в консоли **представление** меню. Позволяет оснастки для отображения только в области представления результатов собственные настраиваемые представления. Это единственный флага, определенные в данный момент.  
  
- **MMC_VIEW_OPTIONS_NONE** = 0 позволяет параметры представления по умолчанию.  
  
##  <a name="a-namegetscopepaneinfoa--csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo  
 Эта функция вызывается для получения **SCOPEDATAITEM** структуры оснастки.  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pScopeDataItem*  
 [out] Указатель на **SCOPEDATAITEM** структуры `CSnapInItemImpl` объекта.  
  
##  <a name="a-namegetresultpaneinfoa--csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo  
 Эта функция вызывается для получения **RESULTDATAITEM** структуры оснастки.  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>Параметры  
 *pResultDataItem*  
 [out] Указатель на **RESULTDATAITEM** структуры `CSnapInItemImpl` объекта.  
  
##  <a name="a-namembstrdisplaynamea--csnapinitemimplmbstrdisplayname"></a><a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName  
 Содержит строку, отображаемую для узла элемента.  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="a-namemscopedataitema--csnapinitemimplmscopedataitem"></a><a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem  
 `SCOPEDATAITEM` Структура объекта данных оснастки.  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="a-namemresultdataitema--csnapinitemimplmresultdataitem"></a><a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem  
 [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165) структуру объекта данных оснастки.  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="a-namenotifya--csnapinitemimplnotify"></a><a name="notify"></a>CSnapInItemImpl::Notify  
 Вызывается, когда объект оснастки применялась пользователем.  
  
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
  
- **MMCN_ACTIVATE** посылается, когда окно является активации и деактивации.  
  
- **MMCN_ADD_IMAGES** отправляется Добавление изображений в панель «результат».  
  
- **MMCN_BTN_CLICK** посылается, когда пользователь нажимает одну из кнопок панели инструментов.  
  
- **MMCN_CLICK** посылается, когда пользователь нажимает кнопку мыши на элемент представления списка.  
  
- **MMCN_DBLCLICK** при двойном щелчке мышью элемента представления списка.  
  
- **MMCN_DELETE** отправляются для информирования оснастки, объект должен быть удален.  
  
- **MMCN_EXPAND** посылается, когда папки необходимо разворачивать и сворачивать.  
  
- **MMCN_MINIMIZED** посылается, когда окно будет свернуто или развернуто.  
  
- **MMCN_PROPERTY_CHANGE** предупреждения объект оснастки, представление объекта оснастки будет изменена.  
  
- **MMCN_REMOVE_CHILDREN** посылается, когда оснастка необходимо удалить все поддерево добавил ниже указанного узла.  
  
- **MMCN_RENAME** отправляется выполнить переименование во время запроса для переименования и второй раз.  
  
- **MMCN_SELECT** при выборе элемента в области представления области или результат.  
  
- **MMCN_SHOW** посылается, когда выбирается элемент области или выбран в первый раз.  
  
- **MMCN_VIEW_CHANGE** посылается, когда оснастки можно обновить все представления при внесении изменений.  
  
 `arg`  
 [in] Зависит от типа уведомления.  
  
 `param`  
 [in] Зависит от типа уведомления.  
  
 *pComponentData*  
 [out] Указатель на объект, реализующий **IComponentData**. Этот параметр является **NULL** Если уведомления не направляются из **IComponentData::Notify**.  
  
 *pComponent*  
 [out] Указатель на объект, реализующий **IComponent**. Этот параметр является **NULL** Если уведомления не направляются из **IComponent::Notify**.  
  
 `type`  
 [in] Указывает тип объекта. Он может принимать одно из следующих значений:  
  
- **CCT_SCOPE** объекта данных для области панели контекста.  
  
- **CCT_RESULT** объекта данных для контекста панели результатов.  
  
- **CCT_SNAPIN_MANAGER** объекта данных для оснастки диспетчера контекста.  
  
- **CCT_UNINITIALIZED** объект данных имеет недопустимый тип.  
  
##  <a name="a-namequerypagesfora--csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor  
 Вызывается, чтобы узнать, поддерживает ли узел оснастки страницы свойств.  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="a-namesetmenuinsertionflagsa--csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags  
 Эта функция вызывается для изменения меню вставки флаги, заданные `pInsertionAllowed`, для объекта оснастки.  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>Параметры  
 *bBeforeInsertion*  
 [in] Ненулевое значение, если функция должна вызываться перед элементы добавляются в контекстное меню; в противном случае — 0.  
  
 `pInsertionAllowed`  
 [in, out] Идентифицирует консоли управления MMC, определенные пункта меню вставки точки, которые можно использовать. Это может быть сочетанием флагов, следующие:  
  
- **CCM_INSERTIONALLOWED_TOP** элементы могут вставляться в верхней части контекстного меню.  
  
- **CCM_INSERTIONALLOWED_NEW** элементы могут быть вставлены в подменю «создать».  
  
- **CCM_INSERTIONALLOWED_TASK** элементы могут быть вставлены в подменю «задача».  
  
- **CCM_INSERTIONALLOWED_VIEW** можно вставлять элементы, в меню Вид панели инструментов или в подменю представление контекстного меню панели результатов.  
  
### <a name="remarks"></a>Примечания  
 При разработке основная оснастка можно сбросить любые из флагов вставки как ограничение вид меню, которые можно добавить расширение независимых производителей. Например, основная оснастка можно очистить **CCM_INSERTIONALLOWED_NEW** флаг для расширения не могут добавлять свои собственные создать новые элементы меню.  
  
 Не следует пытаться битов `pInsertionAllowed` , изначально были очищены. Будущие версии MMC может использовать bits, в настоящее время не определены, поэтому не следует изменять биты, которые в настоящее время не определены.  
  
##  <a name="a-namesettoolbarbuttoninfoa--csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo  
 Эта функция позволяет изменить стили кнопки панели инструментов объекта оснастки, до создания панели инструментов.  
  
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
  
- `TBSTATE_CHECKED`Кнопка имеет **TBSTYLE_CHECKED** стиля и нажат.  
  
- `TBSTATE_ENABLED`Кнопки, принимающее вводимые пользователем данные. Кнопка, которая не имеет это состояние не принимает входные данные пользователя и отображается серым цветом.  
  
- `TBSTATE_HIDDEN`Кнопка не отображается и не может реагировать на действия пользователя.  
  
- `TBSTATE_INDETERMINATE`Кнопка отображается серым цветом.  
  
- `TBSTATE_PRESSED`Кнопка нажата.  
  
- `TBSTATE_WRAP`Кнопки ставится разрыв строки. Необходимо также иметь кнопки `TBSTATE_ENABLED`.  
  
 *Тип_файловой_системы*  
 [in] Флаги состояния кнопки. Может иметь одно или несколько из следующих:  
  
- `TBSTYLE_BUTTON`Создает стандартные кнопки.  
  
- `TBSTYLE_CHECK`Создает кнопку, которая переключает между состояниями нажатой и не нажатой при каждом щелчке по нему. Кнопка имеет другой цвет фона, когда он находится в нажатом состоянии.  
  
- `TBSTYLE_CHECKGROUP`Создает кнопку с галочкой, остается в нажатом положении, пока не будет нажата другая кнопка в группе.  
  
- `TBSTYLE_GROUP`Создает кнопку, которая остается в нажатом положении, пока не будет нажата другая кнопка в группе.  
  
- `TBSTYLE_SEP`Создает разделитель, предоставляя небольшой разрыв между группы кнопок. Кнопка с этим стилем не реагировать на действия пользователя.  
  
##  <a name="a-nameupdatemenustatea--csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState  
 Эта функция используется для изменения пункта меню перед вставкой в контекстном меню объекта оснастки.  
  
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
 [in] Указатель на строку для элемента меню Обновить.  
  
 `flags`  
 [in] Задает новый флаги состояния. Это может быть сочетанием флагов, следующие:  
  
- **MF_POPUP** указывает, что подменю, в контекстном меню. Положение курсора, дальнейшей подменю и пункты могут быть добавлены в этот подменю с помощью его **lCommandID** как их **IInsertionPointID**.  
  
- **MF_BITMAP** и `MF_OWNERDRAW` этих флагов не допускаются и приведет к возвращаемым значением `E_INVALIDARG`.  
  
- **MF_SEPARATOR** рисует горизонтальную линию разделения. Только **IContextMenuProvider** разрешается добавление элементов меню с **MF_SEPARATOR** значение.  
  
- **MF_CHECKED** устанавливает флажок рядом с элементом меню.  
  
- **MF_DISABLED** отключает пункт меню, чтобы не может быть установлен, но этот флаг не серого цвета, его.  
  
- `MF_ENABLED`Включает элемент меню, ее можно будет выбрать, восстановив его из состояния выделенный серым цветом.  
  
- **MF_GRAYED** отключает пункт меню, неподходящие идентификаторы, не могут быть выбраны.  
  
- **MF_MENUBARBREAK** работает так же, как **MF_MENUBREAK** флаг для строки меню. Раскрывающееся меню, подменю или контекстном меню новый столбец отделена от старого столбца вертикальной линии.  
  
- **MF_MENUBREAK** помещает элемент на новой строке (для строки меню) или в новом столбце (для раскрывающееся меню, подменю или контекстном меню) без разделения столбцов.  
  
- **MF_UNCHECKED** не установлен флажок рядом с элементом (по умолчанию).  
  
 Следующие группы флагов нельзя использовать вместе:  
  
- **MF_DISABLED**, `MF_ENABLED`, и **MF_GRAYED**.  
  
- **MF_MENUBARBREAK** и **MF_MENUBREAK**.  
  
- **MF_CHECKED** и **MF_UNCHECKED**.  
  
##  <a name="a-nameupdatetoolbarbuttona--csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton  
 Эта функция вызывается для изменить кнопки панели инструментов, оснастка объекта перед его отображением.  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>Параметры  
 `id`  
 Указывает идентификатор кнопки панели инструментов кнопку обновления.  
  
 `fsState`  
 Указывает состояние кнопки панели инструментов. Если задать это состояние, вернуть **TRUE**. Это может быть сочетанием флагов, следующие:  
  
- **ВКЛЮЧИТЬ** кнопки, принимающее вводимые пользователем данные. Кнопка, которая не имеет это состояние не принимает входные данные пользователя и отображается серым цветом.  
  
- **Проверка** кнопка имеет **проверки** стиля и нажат.  
  
- **СКРЫТЫЕ** кнопка не отображается и не может реагировать на действия пользователя.  
  
- **НЕОПРЕДЕЛЕННЫЙ** кнопка отображается серым цветом.  
  
- **BUTTONPRESSED** нажатии кнопки.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

