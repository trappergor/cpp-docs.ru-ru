---
title: Класс CJumpList
ms.date: 03/27/2019
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
helpviewer_keywords:
- CJumpList [MFC], CJumpList
- CJumpList [MFC], AbortList
- CJumpList [MFC], AddDestination
- CJumpList [MFC], AddKnownCategory
- CJumpList [MFC], AddTask
- CJumpList [MFC], AddTasks
- CJumpList [MFC], AddTaskSeparator
- CJumpList [MFC], ClearAll
- CJumpList [MFC], ClearAllDestinations
- CJumpList [MFC], CommitList
- CJumpList [MFC], GetDestinationList
- CJumpList [MFC], GetMaxSlots
- CJumpList [MFC], GetRemovedItems
- CJumpList [MFC], InitializeList
- CJumpList [MFC], SetAppID
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
ms.openlocfilehash: 98d6bec3d33c9060ebb741111dff793f64cc7cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372333"
---
# <a name="cjumplist-class"></a>Класс CJumpList

A `CJumpList` — это список ярлыков, выявленный при нажатии кнопки «правой кнопки» на значок в панели задач.

## <a name="syntax"></a>Синтаксис

```
class CJumpList;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|Формирует объект `CJumpList`.|
|[CJumpList:::](#_dtorcjumplist)|Уничтожает объект `CJumpList` .|

|Имя|Описание|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|Прерывает транзакцию по созданию списка без фиксации.|
|[CJumpList::AddDestination](#adddestination)|Перегружен. Добавляет пункт назначения в список.|
|[CJumpList::AddKnownКатегория](#addknowncategory)|Приложения известной категории к списку.|
|[CJumpList::AddTask](#addtask)|Перегружен. Добавляет элементы в категорию канонических задач.|
|[CJumpList::AddTasks](#addtasks)|Добавляет элементы в категорию канонических задач.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Добавляет сепаратор между задачами.|
|[CJumpList::ClearAll](#clearall)|Удаляет все задачи и назначения, которые были добавлены в текущий `CJumpList` экземпляр до сих пор.|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Удаляет все направления, которые были добавлены `CJumpList` в текущий экземпляр до сих пор.|
|[CJumpList::CommitList](#commitlist)|Завершает транзакцию создания списка и фиксирует отчетный список в связанный магазин (реестр в данном случае).|
|[CJumpList::GetDestinationList](#getdestinationlist)|Извлекает указатель интерфейса в список назначения.|
|[CJumplist:GetmaxSlots](#getmaxslots)|Извлекает максимальное количество элементов, включая заголовки категорий, которые могут отображаться в меню назначения вызывающей заявки.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Возвращает массив элементов, представляющих удаленные направления.|
|[CJumpList::InitializeList](#initializelist)|Начинается транзакция по созданию списка.|
|[CJumpList:: SetAppID](#setappid)|Устанавливает идентификатор модели пользователя приложения для списка, который будет построен.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

## <a name="cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>CJumpList:::

Уничтожает объект `CJumpList` .

```
~CJumpList();
```

## <a name="cjumplistabortlist"></a><a name="abortlist"></a>CJumpList::AbortList

Прерывает транзакцию по созданию списка без фиксации.

```
void AbortList();
```

### <a name="remarks"></a>Remarks

Вызов этого метода имеет `CJumpList` тот `CommitList`же эффект, что и уничтожение без вызова.

## <a name="cjumplistadddestination"></a><a name="adddestination"></a>CJumpList::AddDestination

Добавляет пункт назначения в список.

```
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,
    LPCTSTR strDestinationPath);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellItem* pShellItem);

BOOL AddDestination(
    LPCTSTR strCategoryName,
    IShellLink* pShellLink);
```

### <a name="parameters"></a>Параметры

*lpcszКатегорияName*<br/>
Упогоняет название категории. Если указанная категория не существует, она будет создана.

*strDestinationPath*<br/>
Определяет файл пути к месту назначения.

*strCategoryName*<br/>
Упогоняет название категории. Если указанная категория не существует, она будет создана.

*pShellItem*<br/>
Осведряй элемент Shell, представляющий место назначения.

*pShellLink*<br/>
Опознавательный улика Shell, представляющая место назначения, на исполнивого.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Экземпляр `CJumpList` внутренне аккумулирует добавленные назначения и `CommitList`после этого фиксирует их внутри .

## <a name="cjumplistaddknowncategory"></a><a name="addknowncategory"></a>CJumpList::AddKnownКатегория

Приложения известной категории к списку.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Параметры

*Категории*<br/>
Определяет известный тип категории. Может быть либо KDC_RECENT, либо KDC_KNOWN.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Известные категории — это категории частых и недавних, которые мы автоматически вычислим для каждого приложения, которое использует `SHAddToRecentDocs` (или косвенно использует его в качестве оболочки, которая будет называться от имени приложения в некоторых сценариях).

## <a name="cjumplistaddtask"></a><a name="addtask"></a>CJumpList::AddTask

Добавляет элементы в категорию канонических задач.

```
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,
    LPCTSTR strCommandLineArgs,
    LPCTSTR strTitle,
    LPCTSTR strIconLocation,
    int iIconIndex);

BOOL AddTask(IShellLink* pShellLink);
```

### <a name="parameters"></a>Параметры

*strTargetExecutablePath*<br/>
Определяет путь целевой задачи.

*strCommandLineArgs*<br/>
Определяет аргументы командной строки исполняемых, указанные *strTargetExecutablePath.*

*strTitle*<br/>
Имя задачи, которое будет отображаться в списке назначения.

*strIconLocation*<br/>
Расположение значка, которое будет отображаться в списке назначения вместе с заголовком.

*iIconIndex*<br/>
Индекс иконок.

*pShellLink*<br/>
Shell Link, представляющая задачу, которую необходимо добавить.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Экземпляр `CJumpList` накапливает указанные задачи и добавляет `CommitList`их в список назначения во время . Элементы задач будут отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над всеми другими категориями, когда она заполняется в uI.

## <a name="cjumplistaddtasks"></a><a name="addtasks"></a>CJumpList::AddTasks

Добавляет элементы в категорию канонических задач.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Параметры

*pObjectCollection*<br/>
Набор задач, которые необходимо добавить.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Экземпляр CJumpList аккумулирует определенные задачи и `CommitList`добавляет их в список назначения во время. Элементы задач будут отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над всеми другими категориями, когда она заполняется в uI.

## <a name="cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>CJumpList::AddTaskSeparator

Добавляет сепаратор между задачами.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если он успешно, 0, если это не так.

## <a name="cjumplistcjumplist"></a><a name="cjumplist"></a>CJumpList::CJumpList

Формирует объект `CJumpList`.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoCommit*<br/>
Если этот параметр FALSE, список не зачисляется автоматически в деструктор.

## <a name="cjumplistclearall"></a><a name="clearall"></a>CJumpList::ClearAll

Удаляет все задачи и назначения, которые были добавлены в текущий `CJumpList` экземпляр до сих пор.

```
void ClearAll();
```

### <a name="remarks"></a>Remarks

Этот метод очищает и выпускает все данные и внутренние интерфейсы.

## <a name="cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>CJumpList::ClearAllDestinations

Удаляет все направления, которые были добавлены в текущий экземпляр CJumpList до сих пор.

```
void ClearAllDestinations();
```

### <a name="remarks"></a>Remarks

Позвоните в эту функцию, если вам нужно удалить все направления, которые были добавлены до сих пор в текущей сессии здания списка назначения и добавить другие направления снова. Если внутреннее `ICustomDestinationList` было инициализировано, оно осталось живым.

## <a name="cjumplistcommitlist"></a><a name="commitlist"></a>CJumpList::CommitList

Завершает транзакцию по созданию списка и фиксирует отчетный список в связанный магазин (реестр в данном случае).

```
BOOL CommitList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Коммит атомный. Ошибка будет возвращена при сходе коммина.  При `CommitList` вызове текущий список удаленных элементов будет очищен. Вызов этого метода сбрасывает объект таким образом, чтобы у него не было активной транзакции по созданию списка. Чтобы обновить список, `BeginList` необходимо вызвать еще раз.

## <a name="cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>CJumpList::GetDestinationList

Извлекает указатель интерфейса в список назначения.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Если список прыжков не был инициализирован или был зафиксирован или прерван, возвращенное значение будет NULL.

## <a name="cjumplistgetmaxslots"></a><a name="getmaxslots"></a>CJumplist:GetmaxSlots

Извлекает максимальное количество элементов, включая заголовки категорий, которые могут отображаться в меню назначения вызывающей заявки.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Приложения могут сообщать только о нескольких элементах и заголовках категорий, объединенных до этого значения. Если `AppendCategory`звонки, `AppendKnownCategory`или `AddUserTasks` превысить этот номер, они будут возвращать сбой.

## <a name="cjumplistgetremoveditems"></a><a name="getremoveditems"></a>CJumpList::GetRemovedItems

Возвращает массив элементов, представляющих удаленные направления.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Удаленные направления извлекаются во время инициализации списка прыжков. При формировании нового списка назначения приложения должны сначала обработать список удаленных пунктов назначения, очистив данные отслеживания для любого элемента, возвращенного удаленным регистратором списка. Если приложение пытается предоставить элемент, который только что был удален `BeginList` в транзакции, к которой начал текущий вызов, вызов метода, который повторно добавил этот элемент, не удастся, чтобы убедиться, что приложения уважают удаленный список.

## <a name="cjumplistinitializelist"></a><a name="initializelist"></a>CJumpList::InitializeList

Начинается транзакция по созданию списка.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Вам не нужно звонить по этому методу явно, если вы `ICustomDestinationList` `GetDestinationList`не хотите получить указатель `GetMaxSlots`на использование, количество `GetRemovedItems`доступных слотов с использованием, или список удаленных элементов с использованием.

## <a name="cjumplistsetappid"></a><a name="setappid"></a>CJumpList:: SetAppID

Устанавливает идентификатор модели пользователя приложения для списка, который будет построен.

```
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Параметры

*strAppID*<br/>
Строка, опозиваемый идентификатором модели пользователя приложения.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
