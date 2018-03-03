---
title: "Класс CJumpList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11b28199155c0ac3bd90cda8fb830ea6f8894dde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cjumplist-class"></a>Класс CJumpList
Объект `CJumpList` список ярлыков, отображаемый при щелчке правой кнопкой мыши значок в панели задач.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Создает объект `CJumpList`.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Уничтожает объект `CJumpList`.|  
  
|name|Описание:|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Прерывает выполнение транзакции построение списка без фиксации.|  
|[CJumpList::AddDestination](#adddestination)|Перегружен. Добавляет в список назначения.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Добавляет к списку известных категории.|  
|[CJumpList::AddTask](#addtask)|Перегружен. Добавляет элементы в канонической категорию задач.|  
|[CJumpList::AddTasks](#addtasks)|Добавляет элементы в канонической категорию задач.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Добавляет разделитель между задачами.|  
|[CJumpList::ClearAll](#clearall)|Удаляет все задачи и назначения, которые были добавлены к текущему экземпляру `CJumpList` к текущему моменту.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Удаляет все назначения, которые были добавлены в текущий экземпляр `CJumpList` к текущему моменту.|  
|[CJumpList::CommitList](#commitlist)|Завершает транзакцию построение списка и фиксирует обнаруженную список связанных хранилище (реестре в данном случае).|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Получает указатель интерфейса на целевой список.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Возвращает максимальное число элементов, включая заголовки категории, которые можно отобразить в меню назначения вызывающему приложению.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Возвращает массив элементов, представляющих удалить назначения.|  
|[CJumpList::InitializeList](#initializelist)|Начинает транзакцию построение списка.|  
|[CJumpList::SetAppID](#setappid)|Задает идентификатор модели пользователя приложения для списка, который будет использоваться для построения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>CJumpList:: ~ CJumpList  
 Уничтожает объект `CJumpList`.  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>CJumpList::AbortList  
 Прерывает выполнение транзакции построение списка без фиксации.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода действует так же, как уничтожение `CJumpList` без вызова `CommitList`.  
  
##  <a name="adddestination"></a>CJumpList::AddDestination  
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
 `lpcszCategoryName`  
 Задает имя категории. Если указанная категория не существует, он будет создан.  
  
 `strDestinationPath`  
 Указывает путь к файлу назначения.  
  
 `strCategoryName`  
 Задает имя категории. Если указанная категория не существует, он будет создан.  
  
 `pShellItem`  
 Указывает элемент оболочки, представляющий добавляемый назначения.  
  
 `pShellLink`  
 Указывает ссылку оболочки, представляющий добавляемый назначения.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Экземпляр `CJumpList` внутренне накапливает добавлены назначения и затем фиксирует их в `CommitList`.  
  
##  <a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 Добавляет к списку известных категории.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Параметры  
 `category`  
 Указывает тип известной категории. Может быть как `KDC_RECENT`, или `KDC_KNOWN`.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Известные категории являются частые и последние категории, которые будет автоматически вычислять для каждого приложения, которое использует `SHAddToRecentDocs` (или неявно используется как оболочка будет вызывать его от имени приложения, в некоторых сценариях).  
  
##  <a name="addtask"></a>CJumpList::AddTask  
 Добавляет элементы в канонической категорию задач.  
  
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
 `strTargetExecutablePath`  
 Указывает путь к целевой задачи.  
  
 `strCommandLineArgs`  
 Задает аргументы командной строки, заданные strTargetExecutablePath исполняемого файла.  
  
 `strTitle`  
 Имя задачи, которое будет отображаться в списке.  
  
 `strIconLocation`  
 Расположение значка, который будет отображаться в целевом списке, а также заголовок.  
  
 `iIconIndex`  
 Индекс значка.  
  
 `pShellLink`  
 Оболочка ссылку, которая представляет задачу, которую нужно добавить.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Экземпляр `CJumpList` накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Задача элементы будут отображаться в категории в нижней части меню конечного приложения. Эта категория имеет приоритет над всех категорий по мере заполнения в пользовательском Интерфейсе.  
  
##  <a name="addtasks"></a>CJumpList::AddTasks  
 Добавляет элементы в канонической категорию задач.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Параметры  
 `pObjectCollection`  
 Коллекция задачи для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Экземпляр CJumpList накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Задача элементы будут отображаться в категории в нижней части меню конечного приложения. Эта категория имеет приоритет над всех категорий по мере заполнения в пользовательском Интерфейсе.  
  
##  <a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 Добавляет разделитель между задачами.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если он прошел успешно, 0, если это не так.  
  
##  <a name="cjumplist"></a>CJumpList::CJumpList  
 Создает объект `CJumpList`.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoCommit`  
 Если этот параметр имеет значение FALSE список автоматически не зафиксированные в деструктор.  
  
##  <a name="clearall"></a>CJumpList::ClearAll  
 Удаляет все задачи и назначения, которые были добавлены к текущему экземпляру `CJumpList` к текущему моменту.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает и освобождает все данные и внутренних интерфейсов.  
  
##  <a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 Удаляет все назначения, которые будут добавлены в текущий экземпляр CJumpList к текущему моменту.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается в том случае, если необходимо удалить все адреса, которые были добавлены к текущему моменту в текущем сеансе построение списка назначения и снова добавьте другие назначения. Если внутренний `ICustomDestinationList` был инициализирован, он остается активным.  
  
##  <a name="commitlist"></a>CJumpList::CommitList  
 Завершает транзакцию построение списка и фиксирует обнаруженную список связанных хранилище (реестре в данном случае).  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Фиксация является атомарной. При сбое фиксации, будет возвращена ошибка.  Когда `CommitList` вызывается текущий список удаленных элементов будут очищены. Вызов этого метода сброс объекта не имеет активной транзакции построение списка. Чтобы обновить список, `BeginList` должен быть вызван повторно.  
  
##  <a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 Получает указатель интерфейса на целевой список.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Если список переходов не был инициализирован, или зафиксирована или прервана, возвращаемое значение будет `NULL`.  
  
##  <a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 Возвращает максимальное число элементов, включая заголовки категории, которые можно отобразить в меню назначения вызывающему приложению.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Приложения только может сообщить число элементов и заголовки категорий в сочетании вплоть до этого значения. Если вызовы `AppendCategory`, `AppendKnownCategory`, или `AddUserTasks` превышает указанное значение, они будет возвращена ошибка.  
  
##  <a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 Возвращает массив элементов, представляющих удалить назначения.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Удалить назначения будут получены во время инициализации список переходов. При создании новой целевой список, приложения должны сначала обработать списка удаленных мест назначения, очистка свои данные отслеживания для любого элемента, возвращенный перечислителем удален список. Если приложение пытается поместить элемент, который был удален в транзакции, этот вызов текущего `BeginList` работы, вызов метода, который повторно добавить этот элемент не удастся, убедитесь, что приложения этом соблюдаются удален список.  
  
##  <a name="initializelist"></a>CJumpList::InitializeList  
 Начинает транзакцию построение списка.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Не требуется явно вызывать этот метод, если только вы хотите получить указатель на `ICustomDestinationList` с помощью `GetDestinationList`, число доступных ячеек с помощью `GetMaxSlots`, или список удаленных элементов с помощью `GetRemovedItems`.  
  
##  <a name="setappid"></a>CJumpList::SetAppID  
 Задает идентификатор модели пользователя приложения для списка, который будет использоваться для построения.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Параметры  
 `strAppID`  
 Строка, задающая идентификатор модели пользователя приложения.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
