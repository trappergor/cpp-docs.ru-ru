---
title: "Класс CWordArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- INT
- UINT
- indexed arrays
- arrays [C++], indexed
- WORD data type
- CWordArray class
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 26
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd6c26c49c6b46449ec6d7da42b9166d17d563da
ms.lasthandoff: 02/24/2017

---
# <a name="cwordarray-class"></a>Класс CWordArray
Поддерживает массивы 16-разрядных слов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>Члены  
 Функции-члены `CWordArray` похожи на функции-члены класса [CObArray](../../mfc/reference/cobarray-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObArray`. Если вы видите [CObject](../../mfc/reference/cobject-class.md) указатель как параметр функции или возвращаемого значения, замените **WORD**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 , например, преобразуется в  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Создает пустой массив.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Возвращает значение по указанному индексу.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Возвращает количество элементов в массиве.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Разрешает доступ к элементам в массиве. Может быть **NULL**.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Возвращает количество элементов в массиве.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Возвращает самый большой допустимый индекс.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Определяет, пуст ли массив.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Удаляет все элементы из этого массива.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Удаляет элемент по указанному индексу.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Задает число элементов, которые будут храниться в этом массиве.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 `CWordArray`включает в себя [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос для поддержки сериализации и записи элементов в дамп. Если массив слов сохраняется в архив с помощью перегруженного оператора вставки или [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функция-член, каждый элемент является, в свою очередь, сериализуются.  
  
> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубины контекста дампа 1 или выше.  
  
 Дополнительные сведения об использовании `CWordArray`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>Интерфейс ICommandSource  
 Управляет команды, отправляемые из исходного объекта команды пользовательского элемента управления.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC, [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команду сообщения пользовательского интерфейса в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации, можно позволить пользователю управлять ссылку на `ICommandSource` объект.  
  
 В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 Добавляет обработчик команды объект источника команды.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
 `cmdHandler`  
 Дескриптор метода обработчика команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет обработчик команды `cmdHandler` с исходным объектом команды и сопоставление обработчика для `cmdID`.  
  
 В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `AddCommandHandler`.  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 Добавляет группу обработчиков команд объект источника команды.  
  
```  
void AddCommandRangeHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазона идентификатор команды.  
  
 `cmdHandler`  
 Дескриптор метода обработчика сообщений, с которым сопоставляются команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сопоставляет непрерывный диапазон идентификаторов команд обработчику одно сообщение и добавляет его к объекту источника команды. Используется для обработки нескольких связанных кнопок с одного метода.  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 Добавляет группу обработчики сообщений команды интерфейса пользователя на объект источника команды.  
  
```  
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,   
    unsigned int cmdIDMax,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазона идентификатор команды.  
  
 `cmdHandler`  
 Дескриптор метода обработчика сообщений, с которым сопоставляются команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод непрерывный диапазон идентификаторов команд сопоставляется сообщение обработчика команды интерфейса одного пользователя и добавляет его к объекту источника команды. Используется для обработки нескольких связанных кнопок с одного метода.  
  
##  <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
 Добавляет обработчик сообщений команды интерфейса пользователя объект источника команды.  
  
```  
void AddCommandUIHandler(
    unsigned int cmdID,   
    CommandUIHandler^ cmdUIHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
 `cmdUIHandler`  
 Дескриптор метод обработки сообщений команды интерфейса пользователя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет обработчик пользовательского интерфейса команды сообщение `cmdHandler` с исходным объектом команды и сопоставляет обработчика `cmdID`.  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 Посылает сообщение, не дожидаясь его обработки.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Параметры  
 `command`  
 Идентификатор команды сообщения для публикации.  
  
### <a name="remarks"></a>Примечания  
 Этот метод асинхронно отправляет сообщение, сопоставляется с Идентификатором, указанным параметром `command`. Он вызывает [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) чтобы поместить сообщение в очередь сообщений и затем возвращает окно без ожидания соответствующее окно для обработки сообщения.  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 Удаляет обработчик команды из исходного объекта команды.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет обработчик команды сопоставляется `cmdID` из исходного объекта команды.  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 Удаляет группу обработчиков команд из исходного объекта команды.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазона идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу обработчиков сообщений, сопоставляется с указанных идентификаторов команд, `cmdIDMin` и `cmdIDMax`, из объекта источника команды.  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 Удаляет группу обработчики сообщений команды интерфейса пользователя из исходного объекта команды.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазона идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу пользователя интерфейс сообщения обработчиков команд, сопоставляется с указанных идентификаторов команд, `cmdIDMin` и `cmdIDMax`, из объекта источника команды.  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет сопоставлен обработчик сообщений команд пользовательского интерфейса `cmdID` из исходного объекта команды.  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 Отправляет сообщение и ожидает его для обработки перед возвратом.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Параметры  
 `command`  
 Идентификатор команды отправляемого сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод синхронно отправляет сообщение сопоставляется с Идентификатором, указанным параметром `command`. Он вызывает [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) чтобы поместить сообщение в очередь сообщений окна и ожидает, пока процедуры окна обработала сообщение перед возвратом.  
  
##  <a name="icommandtarget_interface"></a>Интерфейс ICommandTarget  
 Предоставляет интерфейс для получения команд из исходного объекта команды пользовательского элемента управления.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команду сообщения пользовательского интерфейса в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, пользовательский элемент управления дать ссылку на объект.  
  
 В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 Инициализирует целевой объект команды.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdSource`  
 Дескриптор исходный объект команды.  
  
### <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команду сообщения пользовательского интерфейса в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC.  
  
 Этот метод инициализирует целевой объект команды и связывает его с исходным объектом указанную команду `cmdSource`. Он должен быть вызван в реализацию класса пользовательского элемента управления. При инициализации, необходимо зарегистрировать обработчики команд в исходный объект команды путем вызова [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) в `Initialize` реализации. В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `Initialize` для этого.  
  
##  <a name="icommandui_interface"></a>Интерфейс ICommandUI  
 Управляет команд пользовательского интерфейса.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI`Аналогично [класс CCmdUI](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, взаимодействие с компонентами .NET.  
  
 `ICommandUI`используется внутри `ON_UPDATE_COMMAND_UI` обработчик - производного класса. При активировании пользователем приложения (выбирает или щелчков мышью) меню, каждый элемент меню отображается как включен или отключен. Цель каждой команде меню предоставляет эти сведения при реализации `ON_UPDATE_COMMAND_UI` обработчика. Для каждого объекты команд пользовательского интерфейса в приложении используйте окно свойств для создания записи сопоставления сообщений и прототип функции для каждого обработчика.  
  
 Дополнительные сведения о том, как `ICommandUI` интерфейс используется маршрутизация команд см. в разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Дополнительные сведения об управлении команд пользовательского интерфейса в MFC см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="check"></a>ICommandUI::Check  
 Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает элемент интерфейса пользователя для этой команды для соответствующих проверки состояния. Задайте `Check` следующие значения:  
  
|Термин|Определение|  
|----------|----------------|  
|0|Снять|  
|1|Установить|  
|2|Неопределенное значение|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 Указывает механизму маршрутизации команд для продолжения рассылки текущее сообщение по цепочке обработчиков.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Примечания  
 Это функция дополнительный член, который должен использоваться в сочетании с [ON_COMMAND_EX](http://msdn.microsoft.com/library/0bb49090-aee8-4203-87c8-dd001d3dd26e) обработчик, который возвращает `FALSE`. Дополнительные сведения см. в разделе техническое Примечание [TN006: схемы сообщений](../../mfc/tn006-message-maps.md).  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 Включает или отключает элемент интерфейса пользователя для этой команды.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство включает или отключает элемент интерфейса пользователя для этой команды. Задайте `Enabled` для `TRUE` для включения элемента, `FALSE` его отключить.  
  
##  <a name="id"></a>ICommandUI::ID  
 Получает идентификатор объекта интерфейса пользователя, представленного `ICommandUI` объекта.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство возвращает идентификатор пункта меню, кнопки панели инструментов (дескриптор) или другой объект интерфейса пользователя, представленного `ICommandUI` объекта.  
  
##  <a name="index"></a>ICommandUI::Index  
 Возвращает индекс объекта интерфейса пользователя, представленного `ICommandUI` объекта.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство возвращает индекс (дескриптор) пункта меню, кнопки панели инструментов или другой объект интерфейса пользователя, представленного `ICommandUI` объекта.  
  
##  <a name="radio"></a>ICommandUI::Radio  
 Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает элемент интерфейса пользователя для этой команды для соответствующих проверки состояния. Задайте `Radio` для `TRUE` для включения элемента; в противном случае `FALSE`.  
  
##  <a name="text"></a>ICommandUI::Text  
 Задает текст элемента интерфейса пользователя для этой команды.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает текст элемента интерфейса пользователя для этой команды. Задайте `Text` дескриптор строки текста.  
  
##  <a name="iview_interface"></a>Интерфейс IView  
 Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений элемента управления.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>Примечания  
 `IView`реализует несколько методов, `CWinFormsView` использует для перенаправления общих уведомлений для размещенного элемента управления. Это [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) и [OnActivateView](../../mfc/reference/iview-interface.md).  
  
 `IView`Аналогично [CView](../../mfc/reference/cview-class.md), но используется только с элементами управления и управляемых представлений.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 Вызывается по MFC, когда представление активируется или деактивируется.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>Параметры  
 `activate`  
 Указывает, является ли представление активируется или деактивируется.  
  
##  <a name="oninitialupdate"></a>IView::OnInitialUpdate  
 Вызывается платформой после представления впервые присоединяется к документу, но до первоначального отображения представления.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 После изменения просмотр документа вызван MFC.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет представлению обновления экрана для отражения изменений.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




