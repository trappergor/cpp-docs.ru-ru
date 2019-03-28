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
ms.openlocfilehash: 9296912c97b1efb5f7cbd1ed9f769d0222d5f85c
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565312"
---
# <a name="cjumplist-class"></a>Класс CJumpList

Объект `CJumpList` список ярлыков, отображаемый при щелчке правой кнопкой мыши значок в панели задач.

## <a name="syntax"></a>Синтаксис

```
class CJumpList;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CJumpList::CJumpList](#cjumplist)|Создает объект `CJumpList`.|
|[CJumpList:: ~ CJumpList](#_dtorcjumplist)|Уничтожает объект `CJumpList`.|

|name|Описание|
|----------|-----------------|
|[CJumpList::AbortList](#abortlist)|Прерывает транзакцию список стандартных без фиксации.|
|[CJumpList::AddDestination](#adddestination)|Перегружен. Добавляет в список назначения.|
|[CJumpList::AddKnownCategory](#addknowncategory)|Добавляет категорию известные в список.|
|[CJumpList::AddTask](#addtask)|Перегружен. Добавляет элементы в каноническую категорию задач.|
|[CJumpList::AddTasks](#addtasks)|Добавляет элементы в каноническую категорию задач.|
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Добавляет разделитель между задачами.|
|[CJumpList::ClearAll](#clearall)|Удаляет все задачи и назначения, которые были добавлены к текущему экземпляру `CJumpList` данный момент.|
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Удаляет все назначения, которые были добавлены к текущему экземпляру `CJumpList` данный момент.|
|[CJumpList::CommitList](#commitlist)|Завершает транзакцию список стандартных и фиксирует сообщаемые списка связанных хранилище (реестр, в данном случае).|
|[CJumpList::GetDestinationList](#getdestinationlist)|Извлекает указатель интерфейса на целевой список.|
|[CJumpList::GetMaxSlots](#getmaxslots)|Возвращает максимальное число элементов, включая заголовки категорий, которые могут отображать в целевом меню вызывающего приложения.|
|[CJumpList::GetRemovedItems](#getremoveditems)|Возвращает массив элементов, представляющих удалены назначения.|
|[CJumpList::InitializeList](#initializelist)|Начинает транзакцию построение списка.|
|[CJumpList::SetAppID](#setappid)|Задает идентификатор модели пользователя приложения для списка, который будет использоваться для построения.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CJumpList](../../mfc/reference/cjumplist-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

##  <a name="_dtorcjumplist"></a>  CJumpList:: ~ CJumpList

Уничтожает объект `CJumpList`.

```
~CJumpList();
```

##  <a name="abortlist"></a>  CJumpList::AbortList

Прерывает транзакцию список стандартных без фиксации.

```
void AbortList();
```

### <a name="remarks"></a>Примечания

Вызов этого метода имеет тот же эффект, что уничтожение `CJumpList` без вызова `CommitList`.

##  <a name="adddestination"></a>  CJumpList::AddDestination

Добавляет в список назначения.

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

*lpcszCategoryName*<br/>
Задает имя категории. Если указанная категория не существует, он будет создан.

*strDestinationPath*<br/>
Указывает путь к файлу назначения.

*strCategoryName*<br/>
Задает имя категории. Если указанная категория не существует, он будет создан.

*pShellItem*<br/>
Указывает элемент оболочки, представляющий добавляемый назначения.

*pShellLink*<br/>
Указывает ссылку оболочки, представляющий добавляемый назначения.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Экземпляр `CJumpList` внутренне накапливает добавлена назначения и затем фиксирует их в `CommitList`.

##  <a name="addknowncategory"></a>  CJumpList::AddKnownCategory

Добавляет категорию известные в список.

```
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```

### <a name="parameters"></a>Параметры

*category*<br/>
Указывает тип известные категории. Может быть KDC_RECENT или KDC_KNOWN.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Известные категории приведены категории частые и последние, мы автоматически вычисляет для каждого приложения, использующего `SHAddToRecentDocs` (или косвенно используется как оболочка назову его от имени приложения, в некоторых сценариях).

##  <a name="addtask"></a>  CJumpList::AddTask

Добавляет элементы в каноническую категорию задач.

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
Указывает целевой объект пути.

*strCommandLineArgs*<br/>
Задает аргументы командной строки для исполняемого файла, указанного *strTargetExecutablePath*.

*strTitle*<br/>
Имя задачи, которое будет отображаться в списке.

*strIconLocation*<br/>
Расположение значка, который будет отображаться в целевом списке, а также название.

*iIconIndex*<br/>
Индекс значка.

*pShellLink*<br/>
Ссылка оболочки, которая представляет задачу, которую нужно добавить.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Экземпляр `CJumpList` накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Элементы задач будет отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над всех других категорий, по мере заполнения в пользовательском Интерфейсе.

##  <a name="addtasks"></a>  CJumpList::AddTasks

Добавляет элементы в каноническую категорию задач.

```
BOOL AddTasks(IObjectArray* pObjectCollection);
```

### <a name="parameters"></a>Параметры

*pObjectCollection*<br/>
Коллекция задач, которые необходимо добавить.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Экземпляр CJumpList накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Элементы задач будет отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над всех других категорий, по мере заполнения в пользовательском Интерфейсе.

##  <a name="addtaskseparator"></a>  CJumpList::AddTaskSeparator

Добавляет разделитель между задачами.

```
BOOL AddTaskSeparator();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если успешно; значение 0, если это не так.

##  <a name="cjumplist"></a>  CJumpList::CJumpList

Создает объект `CJumpList`.

```
CJumpList(BOOL bAutoCommit = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoCommit*<br/>
Если этот параметр имеет значение FALSE списка автоматически не фиксируются в деструкторе.

##  <a name="clearall"></a>  CJumpList::ClearAll

Удаляет все задачи и назначения, которые были добавлены к текущему экземпляру `CJumpList` данный момент.

```
void ClearAll();
```

### <a name="remarks"></a>Примечания

Этот метод очищает и высвобождает все данные и внутренних интерфейсов.

##  <a name="clearalldestinations"></a>  CJumpList::ClearAllDestinations

Удаляет все назначения моменту были добавлены на текущий экземпляр CJumpList.

```
void ClearAllDestinations();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается в том случае, если необходимо удалить все назначения, которые были добавлены до сих в текущем сеансе построения списка назначения и снова добавьте другие назначения. Если внутренний `ICustomDestinationList` был инициализирован, он остается активным.

##  <a name="commitlist"></a>  CJumpList::CommitList

Завершает транзакцию список стандартных и фиксирует сообщаемые списка связанных хранилище (реестр, в данном случае).

```
BOOL CommitList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Фиксация является атомарной. Если фиксация завершается сбоем, будет возвращена ошибка.  Когда `CommitList` вызывается текущий список удаленных элементов будут очищены. Вызов этого метода сбрасывает объект, таким образом, чтобы он не имеет активной транзакции построения списка. Чтобы обновить список, `BeginList` должен вызываться снова.

##  <a name="getdestinationlist"></a>  CJumpList::GetDestinationList

Извлекает указатель интерфейса на целевой список.

```
ICustomDestinationList* GetDestinationList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Если список переходов не был инициализирован, или зафиксирована или прервана, возвращаемое значение будет иметь значение NULL.

##  <a name="getmaxslots"></a>  CJumpList::GetMaxSlots

Возвращает максимальное число элементов, включая заголовки категорий, которые могут отображать в целевом меню вызывающего приложения.

```
UINT GetMaxSlots() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Приложения может сообщать только несколько элементов и объединять до достижения этого значения заголовков категорий. Если вызовы `AppendCategory`, `AppendKnownCategory`, или `AddUserTasks` превышает это число, они будут возвращать ошибки.

##  <a name="getremoveditems"></a>  CJumpList::GetRemovedItems

Возвращает массив элементов, представляющих удалены назначения.

```
IObjectArray* GetRemovedItems();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Удалено назначений извлекаются во время инициализации из списка переходов. При создании нового списка назначения, приложения должны сначала обработать список удаленных назначения, очистка свои данные отслеживания для любого элемента, возвращенный перечислителем удален список. Если приложение пытается поместить элемент, который был удален в транзакцию, которая текущий вызов `BeginList` к работе, вызов метода, который повторно добавить этот элемент не удастся, убедитесь, что приложения соблюдение списке удален.

##  <a name="initializelist"></a>  CJumpList::InitializeList

Начинает транзакцию построение списка.

```
BOOL InitializeList();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Не нужно явно вызывать этот метод, если вы хотите получить указатель на `ICustomDestinationList` с помощью `GetDestinationList`, количество доступных слотов с помощью `GetMaxSlots`, или список удаленных элементов с помощью `GetRemovedItems`.

##  <a name="setappid"></a>  CJumpList::SetAppID

Задает идентификатор модели пользователя приложения для списка, который будет использоваться для построения.

```
void SetAppID(LPCTSTR strAppID);
```

### <a name="parameters"></a>Параметры

*strAppID*<br/>
Строка, задающая идентификатор модели пользователя приложения.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
