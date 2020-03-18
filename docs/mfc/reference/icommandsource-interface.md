---
title: Интерфейс ICommandSource
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: a57ca6f36546a17b9a35ebea875ff01b43de1332
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445708"
---
# <a name="icommandsource-interface"></a>Интерфейс ICommandSource

Управляет командами, отправленными из исходного объекта команды в пользовательский элемент управления.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandSource
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[ICommandSource:: Аддкоммандхандлер](#addcommandhandler)|Добавляет обработчик команд в исходный объект команды.|
|[ICommandSource:: Аддкоммандранжехандлер](#addcommandrangehandler)|Добавляет группу обработчиков команд в исходный объект команды.|
|[ICommandSource:: Аддкоммандранжеуихандлер](#addcommandrangeuihandler)|Добавляет группу обработчиков сообщений команд пользовательского интерфейса в исходный объект команды.|
|[ICommandSource:: Аддкоммандуихандлер](#addcommandrangeuihandler)|Добавляет обработчик сообщений командной строки пользовательского интерфейса в исходный объект команды.|
|[ICommandSource::P Осткомманд](#postcommand)|Отправляет сообщение, не дожидаясь его обработки.|
|[ICommandSource:: Ремовекоммандхандлер](#removecommandhandler)|Удаляет обработчик команд из объекта источника команды.|
|[ICommandSource:: Ремовекоммандранжехандлер](#removecommandrangehandler)|Удаляет группу обработчиков команд из объекта источника команды.|
|[ICommandSource:: Ремовекоммандранжеуихандлер](#removecommandrangeuihandler)|Удаляет группу обработчиков сообщений команд пользовательского интерфейса из объекта источника команды.|
|[ICommandSource:: Ремовекоммандуихандлер](#removecommandrangeuihandler)|Удаляет обработчик сообщений командной строки пользовательского интерфейса из объекта источника команды.|
|[ICommandSource:: Сендкомманд](#sendcommand)|Отправляет сообщение и ожидает его обработки перед возвратом.|

### <a name="remarks"></a>Remarks

При размещении пользовательского элемента управления в представлении MFC [класс квинформсвиев](../../mfc/reference/cwinformsview-class.md) направляет команды и обновляет сообщения пользовательского интерфейса команды в пользовательский элемент управления, чтобы разрешить обработку команд MFC (например, элементы меню фрейма и кнопки панели инструментов). Реализуя [интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md), вы предоставляете пользовательскому элементу управления ссылку на объект `ICommandSource`.

См. раздел [как добавить маршрутизацию команд в элемент управления Windows Forms,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) чтобы получить пример использования `ICommandTarget`.

Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Требования

**Заголовок:** афксвинформс. h (определен в сборке atlmfc\lib\mfcmifc80.dll)

## <a name="addcommandhandler"></a>ICommandSource:: Аддкоммандхандлер

Добавляет обработчик команд в исходный объект команды.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
*кмдхандлер*<br/>
Дескриптор метода обработчика команд.

### <a name="remarks"></a>Remarks

Этот метод добавляет обработчик команд Кмдхандлер в исходный объект команды и сопоставляет обработчик с cmdID.
См. раздел [как добавить маршрутизацию команд в элемент управления Windows Forms,](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) чтобы получить пример использования аддкоммандхандлер.

## <a name="addcommandrangehandler"></a>ICommandSource:: Аддкоммандранжехандлер

Добавляет группу обработчиков команд в исходный объект команды.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Параметры

*кмдидмин*<br/>
Начальный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдидмакс*<br/>
Конечный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдхандлер*<br/>
Дескриптор метода обработчика сообщений, с которым сопоставлены команды.
### <a name="remarks"></a>Remarks

Этот метод сопоставляет непрерывный диапазон идентификаторов команд с одним обработчиком сообщений и добавляет его в исходный объект команды. Используется для обработки группы связанных кнопок с помощью одного метода.

## <a name="addcommandrangeuihandler"></a>ICommandSource:: Аддкоммандранжеуихандлер

Добавляет группу обработчиков сообщений команд пользовательского интерфейса в исходный объект команды.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*кмдидмин*<br/>
Начальный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдидмакс*<br/>
Конечный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдхандлер*<br/>
Дескриптор метода обработчика сообщений, с которым сопоставлены команды.

### <a name="remarks"></a>Remarks

Этот метод сопоставляет непрерывный диапазон идентификаторов команд с одним обработчиком командного сообщения пользовательского интерфейса и добавляет его в исходный объект команды. Используется для обработки группы связанных кнопок с помощью одного метода.

## <a name="addcommanduihandler"></a>ICommandSource:: Аддкоммандуихандлер

Добавляет обработчик сообщений командной строки пользовательского интерфейса в исходный объект команды.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
*кмдуихандлер*<br/>
Дескриптор метода обработчика командного сообщения пользовательского интерфейса.

### <a name="remarks"></a>Remarks

Этот метод добавляет обработчик сообщений команды пользовательского интерфейса Кмдхандлер в исходный объект команды и сопоставляет обработчик с cmdID.

## <a name="postcommand"></a>ICommandSource::P Осткомманд

Отправляет сообщение, не дожидаясь его обработки.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды сообщения, которое необходимо опубликовать.
### <a name="remarks"></a>Remarks

Этот метод асинхронно отправляет сообщение, сопоставленное с ИДЕНТИФИКАТОРом, указанным командой. Он вызывает CWnd::P Остмессаже, чтобы поместить сообщение в очередь сообщений окна, а затем возвращает, не дожидаясь обработки сообщения соответствующим окном.

## <a name="removecommandhandler"></a>ICommandSource:: Ремовекоммандхандлер

Удаляет обработчик команд из объекта источника команды.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
### <a name="remarks"></a>Remarks

Этот метод удаляет обработчик команд, сопоставленный с cmdID, из объекта источника команды.

## <a name="removecommandrangehandler"></a>ICommandSource:: Ремовекоммандранжехандлер

Удаляет группу обработчиков команд из объекта источника команды.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*кмдидмин*<br/>
Начальный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдидмакс*<br/>
Конечный индекс диапазона ИДЕНТИФИКАТОРов команд.
### <a name="remarks"></a>Remarks

Этот метод удаляет группу обработчиков сообщений, сопоставленную с идентификаторами команд, указанными в Кмдидмин и Кмдидмакс, из объекта источника команды.

## <a name="removecommandrangeuihandler"></a>ICommandSource:: Ремовекоммандранжеуихандлер

Удаляет группу обработчиков сообщений команд пользовательского интерфейса из объекта источника команды.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Параметры

*кмдидмин*<br/>
Начальный индекс диапазона ИДЕНТИФИКАТОРов команд.
*кмдидмакс*<br/>
Конечный индекс диапазона ИДЕНТИФИКАТОРов команд.
### <a name="remarks"></a>Remarks

Этот метод удаляет группу обработчиков сообщений команд пользовательского интерфейса, сопоставленных с идентификаторами команд, указанными в Кмдидмин и Кмдидмакс, из объекта источника команды.

## <a name="removecommanduihandler"></a>ICommandSource:: Ремовекоммандуихандлер

Удаляет обработчик сообщений командной строки пользовательского интерфейса из объекта источника команды.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
### <a name="remarks"></a>Remarks

Этот метод удаляет обработчик сообщений команды пользовательского интерфейса, сопоставленный с cmdID из исходного объекта команды.

## <a name="sendcommand"></a>ICommandSource:: Сендкомманд

Отправляет сообщение и ожидает его обработки перед возвратом.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды отправляемого сообщения.
### <a name="remarks"></a>Remarks

Этот метод синхронно отправляет сообщение, сопоставленное с ИДЕНТИФИКАТОРом, указанным командой. Он вызывает метод CWnd:: SendMessage, чтобы поместить сообщение в очередь сообщений окна, и ожидает, пока эта процедура окна не обработает сообщение перед возвратом.
## <a name="see-also"></a>См. также раздел

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md)
