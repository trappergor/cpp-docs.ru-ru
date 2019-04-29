---
title: Класс CMFCRibbonQuickAccessToolBarDefaultState
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: 0ea9ec8de0b657fa4e7c601f9c3e676f550defa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380264"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>Класс CMFCRibbonQuickAccessToolBarDefaultState

Вспомогательный класс, который управляет состоянием по умолчанию для быстрого доступа, расположенный на панели ленты ( [класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)).

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Создает объект `CMFCRibbonQuickAccessToolbarDefaultState`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Добавляет команду в состояние по умолчанию для быстрого доступа. Это не приводит к изменению самой панели инструментов.|
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Копирует свойства одного быстрого доступа к другому.|
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Удаляет все команды из панели быстрого доступа. Это не приводит к изменению самой панели инструментов.|

## <a name="remarks"></a>Примечания

После создания панели инструментов быстрого доступа в приложении, мы рекомендуем задать состояние по умолчанию, вызвав [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Это состояние по умолчанию восстанавливается в том случае, когда пользователь щелкает **Сброс** кнопку **Настройка** странице вашего приложения **параметры** диалоговое окно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Пример

Следующий пример демонстрирует создание объекта класса `CMFCRibbonQuickAccessToolbarDefaultState` класс и как добавить команды в состояние по умолчанию для быстрого доступа.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonquickaccesstoolbar.h

##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand

Добавляет команду в состояние по умолчанию для быстрого доступа.

```
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Параметры

*[in] uiCmd*<br/>
Указывает идентификатор команды.

*[in] bIsVisible*<br/>
Задает видимость команды, когда панель быстрого доступа находится в состоянии по умолчанию.

### <a name="remarks"></a>Примечания

Добавление команды на CMFCRibbonQuickAccessToolBarDefaultState выполняет три результата. Во-первых Каждая добавленная команда значится на раскрывающийся список в правой части панели инструментов быстрого доступа. Таким образом пользователь может легко добавить или удалить команды из панели быстрого доступа. Во-вторых, сбрасывается в панель быстрого доступа для отображения только тех команд, которые перечислены как видимый в состояние по умолчанию при нажатии **Сброс** кнопку **Настройка** диалоговое окно. Третий, если не был вызван [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), панель быстрого доступа использует видимые команды из этого списка как видимые команды по умолчанию при первом запуске приложения пользователем. После добавления всех команд, которые должны вызывать [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) следует задать этот экземпляр как состояние по умолчанию для быстрого доступа, панели ленты.

##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom

Копирует свойства одного быстрого доступа к другому.

```
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
[in] Ссылка на источник `CMFCRibbonQuickAccessToolBarDefaultState` для копирования.

### <a name="remarks"></a>Примечания

Этот метод копирует каждой команды в источнике `CMFCRibbonQuickAccessToolBarDefaultState` объект данному объекту с помощью [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) метод.

##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

Создает объект состояния по умолчанию панель быстрого доступа.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Примечания

По умолчанию список команд, новый экземпляр [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) содержит пуст.

##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll

Очищает список команд по умолчанию в панели быстрого доступа.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Эта функция удаляет из данного экземпляра, все команды, предыдущие обращения для [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) добавлен.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
