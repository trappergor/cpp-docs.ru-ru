---
title: "Класс CJumpList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxadv/CJumpList
- CJumpList
dev_langs:
- C++
helpviewer_keywords:
- CJumpList class
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3662bd00f7c757df3a77f5920c48389bbd749fb
ms.lasthandoff: 02/24/2017

---
# <a name="cjumplist-class"></a>Класс CJumpList
A `CJumpList` список ярлыков, отображаемый при щелчке правой кнопкой мыши значок в панели задач.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|Создает объект `CJumpList`.|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|Уничтожает объект `CJumpList`.|  
  
|Имя|Описание|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|Прерывает выполнение транзакции построение списка без фиксации.|  
|[CJumpList::AddDestination](#adddestination)|Перегружен. Добавляет в список назначения.|  
|[CJumpList::AddKnownCategory](#addknowncategory)|Добавляет к списку известных категории.|  
|[CJumpList::AddTask](#addtask)|Перегружен. Добавляет элементы в канонической категорию задач.|  
|[CJumpList::AddTasks](#addtasks)|Добавляет элементы в канонической категорию задач.|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|Добавляет разделитель между задачами.|  
|[CJumpList::ClearAll](#clearall)|Удаляет все задачи и назначения, которые были добавлены в текущий экземпляр `CJumpList` данный момент.|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|Удаляет все назначения, которые были добавлены в текущий экземпляр `CJumpList` данный момент.|  
|[CJumpList::CommitList](#commitlist)|Завершает транзакцию построение списка и фиксирует полученные списка связанных хранилище (реестр, в данном случае).|  
|[CJumpList::GetDestinationList](#getdestinationlist)|Получает указатель интерфейса на целевой список.|  
|[CJumpList::GetMaxSlots](#getmaxslots)|Получает максимальное количество элементов, включая заголовки категории, которые отображаются в меню назначения вызывающему приложению.|  
|[CJumpList::GetRemovedItems](#getremoveditems)|Возвращает массив элементов, представляющих удалить назначения.|  
|[CJumpList::InitializeList](#initializelist)|Начинает транзакцию построение списка.|  
|[CJumpList::SetAppID](#setappid)|Задает идентификатор модели приложения пользователя для списка, который будет построен.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxadv.h  
  
##  <a name="a-namedtorcjumplista--cjumplistcjumplist"></a><a name="_dtorcjumplist"></a>CJumpList:: ~ CJumpList  
 Уничтожает объект `CJumpList`.  
  
```  
~CJumpList();
```  
  
##  <a name="a-nameabortlista--cjumplistabortlist"></a><a name="abortlist"></a>CJumpList::AbortList  
 Прерывает выполнение транзакции построение списка без фиксации.  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов этого метода действует так же, как удаление `CJumpList` без вызова `CommitList`.  
  
##  <a name="a-nameadddestinationa--cjumplistadddestination"></a><a name="adddestination"></a>CJumpList::AddDestination  
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
 Экземпляр `CJumpList` внутренне накапливает добавлены назначения и затем сохраняет их в `CommitList`.  
  
##  <a name="a-nameaddknowncategorya--cjumplistaddknowncategory"></a><a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 Добавляет к списку известных категории.  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>Параметры  
 `category`  
 Указывает тип известных категории. Может быть либо `KDC_RECENT`, или `KDC_KNOWN`.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Известные категории являются частые и последние категорий, будет автоматически вычислять для каждого приложения, которое использует `SHAddToRecentDocs` (или косвенно использует как оболочка будет вызывать из имени приложения, в некоторых сценариях).  
  
##  <a name="a-nameaddtaska--cjumplistaddtask"></a><a name="addtask"></a>CJumpList::AddTask  
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
 Указывает путь назначения задач.  
  
 `strCommandLineArgs`  
 Задает аргументы командной строки для исполняемого файла, указанного strTargetExecutablePath.  
  
 `strTitle`  
 Имя задачи, который будет отображаться в списке.  
  
 `strIconLocation`  
 Расположение значка, который будет отображаться в целевом списке, а также заголовок.  
  
 `iIconIndex`  
 Индекс значка.  
  
 `pShellLink`  
 Ссылка на оболочку, представляющий задачи для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Экземпляр `CJumpList` накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Элементы задач будут отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над других категорий при заполнении пользовательского интерфейса.  
  
##  <a name="a-nameaddtasksa--cjumplistaddtasks"></a><a name="addtasks"></a>CJumpList::AddTasks  
 Добавляет элементы в канонической категорию задач.  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>Параметры  
 `pObjectCollection`  
 Набор задач для добавления.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Экземпляр CJumpList накапливает указанной задачи и добавляет их в список назначения во время `CommitList`. Элементы задач будут отображаться в категории в нижней части меню назначения приложения. Эта категория имеет приоритет над других категорий при заполнении пользовательского интерфейса.  
  
##  <a name="a-nameaddtaskseparatora--cjumplistaddtaskseparator"></a><a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 Добавляет разделитель между задачами.  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если он завершается успешно, 0, если это не так.  
  
##  <a name="a-namecjumplista--cjumplistcjumplist"></a><a name="cjumplist"></a>CJumpList::CJumpList  
 Создает объект `CJumpList`.  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoCommit`  
 Если этот параметр имеет значение FALSE списка автоматически не зафиксированы в деструкторе.  
  
##  <a name="a-nameclearalla--cjumplistclearall"></a><a name="clearall"></a>CJumpList::ClearAll  
 Удаляет все задачи и назначения, которые были добавлены в текущий экземпляр `CJumpList` данный момент.  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод очищает и освобождает все данные и внутренних интерфейсов.  
  
##  <a name="a-nameclearalldestinationsa--cjumplistclearalldestinations"></a><a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 Удаляет все назначения, которые будут добавлены в текущий экземпляр CJumpList данный момент.  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается в том случае, если необходимо удалить все адреса, которые были добавлены до сих в текущем сеансе построение списка назначения и снова добавьте другие назначения. Если внутренний `ICustomDestinationList` был инициализирован, он остается активным.  
  
##  <a name="a-namecommitlista--cjumplistcommitlist"></a><a name="commitlist"></a>CJumpList::CommitList  
 Завершает транзакцию построение списка и фиксирует полученные списка связанных хранилище (реестр, в данном случае).  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Фиксация является атомарной. Если фиксация завершается неудачей, будет возвращена ошибка.  Когда `CommitList` вызывается текущий список удаленных элементов будут очищены. Вызов этого метода сброс объекта не имеет активной транзакции построение списка. Чтобы обновить список, `BeginList` должен вызываться снова.  
  
##  <a name="a-namegetdestinationlista--cjumplistgetdestinationlist"></a><a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 Получает указатель интерфейса на целевой список.  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Если список переходов не инициализирован, или зафиксирована или прервана, возвращаемое значение будет `NULL`.  
  
##  <a name="a-namegetmaxslotsa--cjumplistgetmaxslots"></a><a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 Получает максимальное количество элементов, включая заголовки категории, которые отображаются в меню назначения вызывающему приложению.  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Приложения могут сообщать только количество элементов и объединять до этого значения заголовков категорий. Если вызовы `AppendCategory`, `AppendKnownCategory`, или `AddUserTasks` превышает указанное значение, они будут возвращать ошибки.  
  
##  <a name="a-namegetremoveditemsa--cjumplistgetremoveditems"></a><a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 Возвращает массив элементов, представляющих удалить назначения.  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Удален назначения будут получены во время инициализации списка переходов. При создании новой целевой список, предполагается, что сначала обработать список удаленных назначения, очистка свои данные отслеживания для любого элемента, возвращенный перечислителем список удаленных приложений. Если приложение пытается поместить элемент, который просто был удален в транзакцию, которая текущего вызова `BeginList` работу, вызов метода, который повторно добавлен этот элемент не удастся, убедитесь, что приложения соблюдение удален список.  
  
##  <a name="a-nameinitializelista--cjumplistinitializelist"></a><a name="initializelist"></a>CJumpList::InitializeList  
 Начинает транзакцию построение списка.  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Не требуется явно вызывать этот метод, если вы хотите получить указатель `ICustomDestinationList` с помощью `GetDestinationList`, число доступных ячеек с помощью `GetMaxSlots`, или список удаленных элементов с помощью `GetRemovedItems`.  
  
##  <a name="a-namesetappida--cjumplistsetappid"></a><a name="setappid"></a>CJumpList::SetAppID  
 Задает идентификатор модели приложения пользователя для списка, который будет построен.  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>Параметры  
 `strAppID`  
 Строка, задающая идентификатор модели приложения пользователя.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

