---
title: "Класс CWordArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5804df97c54a111a02b79dc849c20c91ba8176b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cwordarray-class"></a>Класс CWordArray
Поддерживает массивы 16-разрядных слов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>Участники  
 Функции-члены `CWordArray` похожи на функции-члены класса [CObArray](../../mfc/reference/cobarray-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObArray`. Если вы видите [CObject](../../mfc/reference/cobject-class.md) указатель как параметр функции или возвращаемого значения, замените **WORD**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 , например, преобразуется в  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Создает пустой массив.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CObArray::operator &#91; &#93;](../../mfc/reference/cobarray-class.md#operator_at)|Получает или задает элемент с указанным индексом.|  
  
## <a name="remarks"></a>Примечания  
 `CWordArray`включает в себя [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос для поддержки сериализации и записи элементов в дамп. Если массив слов хранится в архив с помощью перегруженного оператора вставки или [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функция-член, каждый элемент является, в свою очередь, сериализации.  
  
> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.  
  
 Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубины контекста дампа 1 или выше.  
  
 Дополнительные сведения об использовании `CWordArray`, см. в статье [коллекции](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcoll.h  
  
##  <a name="icommandsource_interface"></a>Интерфейс руководство.  
 Управляет команды, отправляемые из исходного объекта команды в пользовательском элементе управления.  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>Примечания  
 Если разместить пользовательский элемент управления в представлении MFC [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды пользовательского интерфейса сообщения в пользовательский элемент управления мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации, можно позволить пользователю управлять ссылку на `ICommandSource` объекта.  
  
 В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
 Добавляет обработчик команд объект источника команды.  
  
```  
void AddCommandHandler(
    unsigned int cmdID,  
    CommandHandler^ cmdHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
 `cmdHandler`  
 Дескриптор метода обработчика команд.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет обработчик команд `cmdHandler` с исходным объектом команды и сопоставляет обработчика `cmdID`.  
  
 В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `AddCommandHandler`.  
  
##  <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
 Добавляет группу обработчики команд объект источника команды.  
  
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
 Конечный индекс диапазон Идентификаторов команд.  
  
 `cmdHandler`  
 Дескриптор метода обработчика сообщений, с которыми связаны команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сопоставляет непрерывный диапазон идентификаторов команд обработчику одно сообщение и добавляет его в исходный объект команды. Используется для обработки нескольких связанных кнопок с помощью одного метода.  
  
##  <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
 Добавляет группу обработчики сообщений команды пользовательского интерфейса на объект источника команды.  
  
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
 Конечный индекс диапазон Идентификаторов команд.  
  
 `cmdHandler`  
 Дескриптор метода обработчика сообщений, с которыми связаны команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод сопоставляет непрерывный диапазон идентификаторов команд обработчик сообщения команды интерфейса одного пользователя и добавляет его в исходный объект команды. Используется для обработки нескольких связанных кнопок с помощью одного метода.  
  
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
 Дескриптор метод обработчика сообщения пользовательского интерфейса команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет обработчик сообщений команды пользовательского интерфейса `cmdHandler` с исходным объектом команды и сопоставляет обработчика `cmdID`.  
  
##  <a name="postcommand"></a>ICommandSource::PostCommand  
 Отправляет сообщение, не ожидая его обработки.  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Параметры  
 `command`  
 Идентификатор команды сообщения должны быть учтены.  
  
### <a name="remarks"></a>Примечания  
 Этот метод асинхронно отправляет сообщение, сопоставлен с Идентификатором, указанным параметром `command`. Он вызывает [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) чтобы поместить сообщение в очередь сообщений и затем возвращает окна без ожидания соответствующее окно для обработки сообщения.  
  
##  <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 Удаляет обработчик команд из исходного объекта команды.  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет обработчик команд, сопоставлен `cmdID` из исходного объекта команды.  
  
##  <a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
 Удаляет группу обработчики команд из исходного объекта команды.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазон Идентификаторов команд.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу обработчики сообщений, сопоставлен указаны идентификаторы команд по `cmdIDMin` и `cmdIDMax`, из исходного объекта команды.  
  
##  <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
 Удаляет группу обработчики сообщений команды пользовательского интерфейса из исходного объекта команды.  
  
```  
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,  
    unsigned int cmdIDMax);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdIDMin`  
 Начальный индекс диапазона идентификатор команды.  
  
 `cmdIDMax`  
 Конечный индекс диапазон Идентификаторов команд.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет группу пользователя интерфейс сообщения обработчики команд, сопоставлен указаны идентификаторы команд по `cmdIDMin` и `cmdIDMax`, из исходного объекта команды.  
  
##  <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 Удаляет обработчик сообщения команды интерфейс пользователя из исходного объекта команды.  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdID`  
 Идентификатор команды.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет сопоставлен обработчик сообщения команды пользовательского интерфейса `cmdID` из исходного объекта команды.  
  
##  <a name="sendcommand"></a>ICommandSource::SendCommand  
 Отправляет сообщение и ожидает его обработки перед возвратом.  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>Параметры  
 `command`  
 Идентификатор команды отправляемого сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод синхронно отправляет сообщение, сопоставлен с Идентификатором, указанным параметром `command`. Он вызывает [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) чтобы поместить сообщение в очередь сообщений окна и ожидает, пока этой процедуры окна обработала сообщение перед возвратом.  
  
##  <a name="icommandtarget_interface"></a>Интерфейс ICommandTarget  
 Пользовательский элемент управления предоставляет интерфейс для получения команд из исходного объекта команды.  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>Примечания  
 Если разместить пользовательский элемент управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды пользовательского интерфейса сообщения в пользовательский элемент управления мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, вы предоставляете пользовательский элемент управления, ссылка на объект.  
  
 В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 Инициализирует целевой объект команды.  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>Параметры  
 `cmdSource`  
 Дескриптор исходный объект команды.  
  
### <a name="remarks"></a>Примечания  
 Если разместить пользовательский элемент управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды пользовательского интерфейса сообщения в пользовательский элемент управления мог обрабатывать команды MFC.  
  
 Этот метод инициализирует целевой объект команды и связывает его с исходным объектом указанную команду `cmdSource`. Он должен вызываться в реализацию класса пользовательского элемента управления. При инициализации, необходимо зарегистрировать обработчики команд с исходным объектом команды путем вызова [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) в `Initialize` реализации. В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `Initialize` для этого.  
  
##  <a name="icommandui_interface"></a>Интерфейс ICommandUI  
 Управляет команд пользовательского интерфейса.  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>Примечания  
 Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI`Аналогично [CCmdUI-класс](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, совместимые с компоненты .NET.  
  
 `ICommandUI`используется в рамках `ON_UPDATE_COMMAND_UI` обработчика в производном классе,. При активации пользователем приложения (включению или щелчки) меню, каждый элемент меню отображается как включена или отключена. Целевой каждой команды меню предоставляет эти сведения, реализовав `ON_UPDATE_COMMAND_UI` обработчика. Для каждого из объектов интерфейса пользователя команду в приложении используйте окно свойств для создания записи сопоставления сообщения и прототип функции для каждого обработчика.  
  
 Дополнительные сведения о том, как `ICommandUI` интерфейс используется маршрутизация команд см. в разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Дополнительные сведения об управлении команд пользовательского интерфейса в MFC см. в разделе [CCmdUI-класс](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="check"></a>ICommandUI::Check  
 Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает элемент интерфейса пользователя для этой команды для состояния соответствующего флажка. Задать `Check` следующие значения:  
  
|Термин|Определение|  
|----------|----------------|  
|0|Снимите флажок|  
|1|Флажок|  
|2|Неопределенное значение|  
  
##  <a name="continuerouting"></a>ICommandUI::ContinueRouting  
 Указывает механизму маршрутизации команд продолжить маршрутизацию текущее сообщение по цепочке обработчиков.  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Примечания  
 Это — это функция дополнительный член, который должен использоваться в сочетании с [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) обработчик, который возвращает `FALSE`. Дополнительные сведения см. в разделе техническое Примечание [TN006: схемы сообщений](../../mfc/tn006-message-maps.md).  
  
##  <a name="enabled"></a>ICommandUI::Enabled  
 Включает или отключает элементами пользовательского интерфейса для этой команды.  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство включает или отключает элементами пользовательского интерфейса для этой команды. Задать `Enabled` для `TRUE` чтобы активировать элемент, `FALSE` отключить ее.  
  
##  <a name="id"></a>ICommandUI::ID  
 Возвращает идентификатор объекта интерфейса пользователя, представленного `ICommandUI` объекта.  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство возвращает идентификатор элемента меню, кнопки панели инструментов (дескриптор) или другой объект интерфейса пользователя, представленного `ICommandUI` объекта.  
  
##  <a name="index"></a>ICommandUI::Index  
 Возвращает индекс объекта интерфейса пользователя, представленного `ICommandUI` объекта.  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство возвращает индекс (дескриптор) элемента меню, кнопки панели инструментов или другого объекта интерфейса пользователя, представленного `ICommandUI` объекта.  
  
##  <a name="radio"></a>ICommandUI::Radio  
 Задает состояние соответствующего флажка элемента интерфейса пользователя для этой команды.  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает элемент интерфейса пользователя для этой команды для состояния соответствующего флажка. Задать `Radio` для `TRUE` чтобы активировать элемент; в противном случае `FALSE`.  
  
##  <a name="text"></a>ICommandUI::Text  
 Задает текст элемента интерфейса пользователя для этой команды.  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>Примечания  
 Это свойство задает текст элемента интерфейса пользователя для этой команды. Задать `Text` дескриптор строки текста.  
  
##  <a name="iview_interface"></a>Интерфейс IView  
 Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений управляемого элемента управления.  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>Примечания  
 `IView`реализует несколько методов, `CWinFormsView` используется для перенаправления общих уведомлений для размещенного управляемого элемента управления. Это [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) и [OnActivateView](../../mfc/reference/iview-interface.md).  
  
 `IView`Аналогично [CView](../../mfc/reference/cview-class.md), но используется только с управляемых представления и элементы управления.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="onactivateview"></a>IView::OnActivateView  
 Вызывается средой MFC, когда представление активируется или деактивируется.  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>Параметры  
 `activate`  
 Указывает, является ли представление активируется или деактивируется.  
  
##  <a name="oninitialupdate"></a>IView::OnInitialUpdate  
 Вызывается платформой после представление впервые присоединяется к документу, но до первоначального отображения представления.  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="onupdate"></a>IView::OnUpdate  
 После изменения представления документа вызван MFC.  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция обеспечивает представление, чтобы обновить его отображение, чтобы отразить изменения.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



