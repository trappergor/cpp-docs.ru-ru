---
title: Класс CWordArray
ms.date: 11/04/2016
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
ms.openlocfilehash: 9b2888c82ad9522925ffbd53923d3988863f56ca
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565364"
---
# <a name="cwordarray-class"></a>Класс CWordArray

Поддерживает массивы 16-разрядных слов.

## <a name="syntax"></a>Синтаксис

```
class CWordArray : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CWordArray` похожи на функции-члены класса [CObArray](../../mfc/reference/cobarray-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObArray`. Если вы видите [CObject](../../mfc/reference/cobject-class.md) указатель в качестве параметра функции или возвращаемого значения, заменить слово.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

, например, преобразуется в

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Создает пустой массив.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Возвращает значение по указанному индексу.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Возвращает количество элементов в массиве.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
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

|name|Описание|
|----------|-----------------|
|[CObArray::operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

`CWordArray` включает в себя [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос для поддержки сериализации и записи элементов в дамп. Если массив слов хранится в архив с помощью перегруженного оператора вставки или [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функция-член, каждый элемент является, в свою очередь, сериализации.

> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Если вам требуется дамп отдельных элементов в массиве, необходимо задать глубины контекста дампа 1 или выше.

Дополнительные сведения об использовании `CWordArray`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

##  <a name="icommandsource_interface"></a>  Интерфейс ICommandSource

Управляет команды, отправляемые из исходного объекта команды в пользовательский элемент управления.

```
interface class ICommandSource
```

### <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представлении MFC [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды сообщения пользовательского интерфейса для пользовательского элемента управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации, вы предоставляете пользовательский элемент управления ссылку `ICommandSource` объекта.

См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

Добавляет обработчик команд объект источника команды.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

*cmdHandler*<br/>
Дескриптор метода обработчика команды.

### <a name="remarks"></a>Примечания

Этот метод добавляет обработчик команд *cmdHandler* к исходному объекту команды и сопоставляет обработчик, который *cmdID*.

См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `AddCommandHandler`.

##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler

Добавляет группу обработчиков команд объект источника команды.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатор команды.

*cmdIDMax*<br/>
Конечный индекс диапазона идентификатор команды.

*cmdHandler*<br/>
Дескриптор метода обработчика сообщений, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Этот метод сопоставляет непрерывный диапазон идентификаторов команд обработчику одно сообщение и добавляет его на объект источника команды. Используется для обработки нескольких связанных кнопок с одним методом.

##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler

Добавляет группу обработчики сообщений команды интерфейса пользователя объект источника команды.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатор команды.

*cmdIDMax*<br/>
Конечный индекс диапазона идентификатор команды.

*cmdHandler*<br/>
Дескриптор метода обработчика сообщений, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Этот метод сопоставляет непрерывный диапазон идентификаторов команд обработчика сообщений команда интерфейс одного пользователя и добавляет его на объект источника команды. Используется для обработки нескольких связанных кнопок с одним методом.

##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler

Добавляет обработчик сообщений команды интерфейса пользователя объект источника команды.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

*cmdUIHandler*<br/>
Дескриптор методу обработчика сообщений команды интерфейса пользователя.

### <a name="remarks"></a>Примечания

Этот метод добавляет обработчик сообщений команды интерфейса пользователя *cmdHandler* к исходному объекту команды и сопоставляет обработчик, который *cmdID*.

##  <a name="postcommand"></a>  ICommandSource::PostCommand

Отправляет сообщение, не дожидаясь его обработки.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды сообщение для публикации.

### <a name="remarks"></a>Примечания

Этот метод асинхронно передает сообщение сопоставляется с Идентификатором, указанным параметром *команда*. Он вызывает [CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage) должен разместить сообщение в очередь сообщений окна и затем возвращает, не дожидаясь соответствующее окно для обработки сообщения.

##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler

Удаляет обработчик команд из исходного объекта команды.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик команд, сопоставляются с *cmdID* из исходного объекта команды.

##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler

Удаляет группу обработчиков команд из исходного объекта команды.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатор команды.

*cmdIDMax*<br/>
Конечный индекс диапазона идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу обработчиков сообщений, сопоставляются с идентификаторы команд, определяемое *cmdIDMin* и *cmdIDMax*, из исходного объекта команды.

##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler

Удаляет группу обработчики сообщений команды интерфейса пользователя из исходного объекта команды.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*cmdIDMin*<br/>
Начальный индекс диапазона идентификатор команды.

*cmdIDMax*<br/>
Конечный индекс диапазона идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет группу пользователя интерфейс сообщение обработчиков команд, сопоставляются с идентификаторы команд, определяемое *cmdIDMin* и *cmdIDMax*, из исходного объекта команды.

##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler

Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.

### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик пользовательского интерфейса команды сообщения сопоставляется с *cmdID* из исходного объекта команды.

##  <a name="sendcommand"></a>  ICommandSource::SendCommand

Отправляет сообщение и ожидает его обработки перед возвратом.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды отправляемое сообщение.

### <a name="remarks"></a>Примечания

Этот метод синхронно отправляет сообщение, сопоставляется с Идентификатором, указанным параметром *команда*. Он вызывает [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) должен разместить сообщение в очередь сообщений окна и ожидает, пока сообщение обработано процедуры окно перед возвращением.

##  <a name="icommandtarget_interface"></a>  Интерфейс ICommandTarget

Предоставляет пользовательский элемент управления с помощью интерфейса для получения команд из исходного объекта команды.

```
interface class ICommandTarget
```

### <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды сообщения пользовательского интерфейса для пользовательского элемента управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, вы предоставляете пользовательский элемент управления, ссылка на объект.

См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="initialize"></a>  ICommandTarget::Initialize

Инициализирует целевой объект команды.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Параметры

*cmdSource*<br/>
Дескриптор объект источника команды.

### <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды сообщения пользовательского интерфейса для пользовательского элемента управления, чтобы тот мог обрабатывать команды MFC.

Этот метод инициализирует целевой объект команды и связывает его с исходным объектом указанную команду *cmdSource*. Он должен вызываться в реализацию класса пользовательского элемента управления. При инициализации, необходимо зарегистрировать обработчики команд с исходным объектом команды путем вызова [ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md) в `Initialize` реализации. См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `Initialize` для этого.

##  <a name="icommandui_interface"></a>  Интерфейс ICommandUI

Управляет команд пользовательского интерфейса.

```
interface class ICommandUI
```

### <a name="remarks"></a>Примечания

Этот интерфейс предоставляет методы и свойства, которые управляют команд пользовательского интерфейса. `ICommandUI` аналогичен [класс CCmdUI](../../mfc/reference/ccmdui-class.md), за исключением того, что `ICommandUI` используется для приложений MFC, взаимодействие с компонентами .NET.

`ICommandUI` используется в рамках `ON_UPDATE_COMMAND_UI` обработчик - производного класса. При активации пользователем приложения (выбирает или щелчков мыши) меню, а каждый пункт меню отображается как включена или отключена. Цель каждой команды меню предоставляет эти сведения, реализовав `ON_UPDATE_COMMAND_UI` обработчика. Для каждого из объектов пользовательского интерфейса команды в приложении используйте окно свойств для создания записи схемы сообщений и прототип функции для каждого обработчика.

Дополнительные сведения о том, как `ICommandUI` в маршрутизации команд используется интерфейс, см. в разделе [как: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Дополнительные сведения о об управлении команд пользовательского интерфейса в MFC, см. в разделе [класс CCmdUI](../../mfc/reference/ccmdui-class.md).

##  <a name="check"></a>  ICommandUI::Check

Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.

```
property UICheckState Check;
```

### <a name="remarks"></a>Примечания

Это свойство задает элемент пользовательского интерфейса для этой команды для проверки соответствующего состояния. Задайте `Check` следующие значения:

|Термин|Определение|
|----------|----------------|
|0|Снимите флажок|
|1|службы "Функции Azure"|
|2|Задайте в неопределенном состоянии|

##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting

Указывает механизму маршрутизации команды продолжить маршрутизацию текущее сообщение по цепочке обработчиков.

```
void ContinueRouting();
```

### <a name="remarks"></a>Примечания

Это функция дополнительный член, который должен использоваться в сочетании с [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) обработчик, который возвращает значение FALSE. Дополнительные сведения см. в разделе техническое Примечание [TN006: Схемы сообщений](../../mfc/tn006-message-maps.md).

##  <a name="enabled"></a>  ICommandUI::Enabled

Включает или отключает элемент интерфейса пользователя для этой команды.

```
property bool Enabled;
```

### <a name="remarks"></a>Примечания

Это свойство включает или отключает элемент интерфейса пользователя для этой команды. Задайте `Enabled` значение true, чтобы активировать элемент, FALSE, чтобы отключить его.

##  <a name="id"></a>  ICommandUI::ID

Получает идентификатор объекта пользовательского интерфейса, представленного `ICommandUI` объекта.

```
property unsigned int ID;
```

### <a name="remarks"></a>Примечания

Это свойство получает идентификатор (дескриптор) для пункта меню, кнопки панели инструментов или других объекта пользовательского интерфейса, представленного `ICommandUI` объекта.

##  <a name="index"></a>  ICommandUI::Index

Получает индекс объекта пользовательского интерфейса, представленного `ICommandUI` объекта.

```
property unsigned int Index;
```

### <a name="remarks"></a>Примечания

Это свойство возвращает индекс (дескриптор) элемента меню, кнопки панели инструментов или других объекта пользовательского интерфейса, представленного `ICommandUI` объекта.

##  <a name="radio"></a>  ICommandUI::Radio

Задает элемент пользовательского интерфейса для этой команды соответствующий проверки состояния.

```
property bool Radio;
```

### <a name="remarks"></a>Примечания

Это свойство задает элемент пользовательского интерфейса для этой команды для проверки соответствующего состояния. Задайте `Radio` значение true, чтобы включить элемент; в противном случае — значение FALSE.

##  <a name="text"></a>  ICommandUI::Text

Задает текст элемента интерфейса пользователя для этой команды.

```
property String^ Text;
```

### <a name="remarks"></a>Примечания

Это свойство задает текст элемента интерфейса пользователя для этой команды. Задайте `Text` на дескриптор строки текста.

##  <a name="iview_interface"></a>  Интерфейс IView

Реализует несколько методов, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) использует для отправки уведомлений в представление элемента управления.

```
interface class IView
```

### <a name="remarks"></a>Примечания

`IView` реализует несколько методов, `CWinFormsView` использует для пересылки общих уведомлений для размещенного элемента управления. Это [OnInitialUpdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) и [OnActivateView](../../mfc/reference/iview-interface.md).

`IView` аналогичен [CView](../../mfc/reference/cview-class.md), но используется только с управляемых представлений и элементов управления.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="onactivateview"></a>  IView::OnActivateView

Вызывается средой MFC, когда представление активируется или деактивируется.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>Параметры

*активировать*<br/>
Указывает, является ли представление активируется или деактивируется.

##  <a name="oninitialupdate"></a>  IView::OnInitialUpdate

Вызвано структурой после представления впервые присоединяется к документу, но до изначально отображается представление.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>  IView::OnUpdate

Вызывается средой MFC, после изменения этого представления документа.

```
void OnUpdate();
```

### <a name="remarks"></a>Примечания

Эта функция позволяет представлению обновления экрана для отражения изменений.

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
