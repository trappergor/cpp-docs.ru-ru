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
ms.openlocfilehash: eed7abbbb40c532ad596f683b6ed2c98a0cadf9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322086"
---
# <a name="icommandsource-interface"></a>Интерфейс ICommandSource

Управляет команды, отправляемые из исходного объекта команды в пользовательский элемент управления.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandSource
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Добавляет обработчик команд объект источника команды.|
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Добавляет группу обработчиков команд объект источника команды.|
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Добавляет группу обработчики сообщений команды интерфейса пользователя объект источника команды.|
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Добавляет обработчик сообщений команды интерфейса пользователя объект источника команды.|
|[ICommandSource::PostCommand](#postcommand)|Отправляет сообщение, не дожидаясь его обработки.|
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Удаляет обработчик команд из исходного объекта команды.|
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Удаляет группу обработчиков команд из исходного объекта команды.|
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Удаляет группу обработчики сообщений команды интерфейса пользователя из исходного объекта команды.|
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.|
|[ICommandSource::SendCommand](#sendcommand)|Отправляет сообщение и ожидает его обработки перед возвратом.|

### <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представлении MFC [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды сообщения пользовательского интерфейса для пользовательского элемента управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации [интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md), вы предоставляете ссылку на пользовательский элемент управления `ICommandSource` объекта.

См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определенных в сборке atlmfc\lib\mfcmifc80.dll)

## <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

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

Этот метод добавляет cmdHandler обработчика команды с исходным объектом команды и сопоставляет обработчик cmdID.
См. практическое руководство по [ Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование AddCommandHandler.

## <a name="addcommandrangehandler"></a> ICommandSource::AddCommandRangeHandler

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

## <a name="addcommandrangeuihandler"></a> ICommandSource::AddCommandRangeUIHandler

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

## <a name="addcommanduihandler"></a> ICommandSource::AddCommandUIHandler

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

Этот метод добавляет cmdHandler обработчик сообщений для пользователя интерфейс команда объект источника команды и сопоставляет обработчик cmdID.

## <a name="postcommand"></a> ICommandSource::PostCommand

Отправляет сообщение, не дожидаясь его обработки.
```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды сообщение для публикации.
### <a name="remarks"></a>Примечания

Этот метод асинхронно отправляет сообщение, сопоставляется с Идентификатором, указанным параметром команды. Он вызывает CWnd::PostMessage для размещения сообщения в очередь сообщений окна и затем возвращается без ожидания соответствующее окно для обработки сообщения.

## <a name="removecommandhandler"></a> ICommandSource::RemoveCommandHandler

Удаляет обработчик команд из исходного объекта команды.
```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик команды, сопоставленный с cmdID объект источника команды.

## <a name="removecommandrangehandler"></a> ICommandSource::RemoveCommandRangeHandler

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

Этот метод удаляет группу обработчиков сообщений, сопоставляются с идентификаторы команд, заданного cmdIDMin и cmdIDMax из исходного объекта команды.

## <a name="removecommandrangeuihandler"></a> ICommandSource::RemoveCommandRangeUIHandler

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

Этот метод удаляет группу пользователя интерфейс сообщение обработчиков команд, сопоставляются с идентификаторы команд, заданного cmdIDMin и cmdIDMax из исходного объекта команды.

## <a name="removecommanduihandler"></a> ICommandSource::RemoveCommandUIHandler

Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды.
### <a name="remarks"></a>Примечания

Этот метод удаляет обработчик пользовательского интерфейса команды сообщения сопоставляется cmdID из исходного объекта команды.

## <a name="sendcommand"></a> ICommandSource::SendCommand

Отправляет сообщение и ожидает его обработки перед возвратом.
```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Параметры

*command*<br/>
Идентификатор команды отправляемое сообщение.
### <a name="remarks"></a>Примечания

Этот метод синхронно отправляет сообщение, сопоставляется с Идентификатором, указанным параметром команды. Он вызывает CWnd::SendMessage должен разместить сообщение в очередь сообщений окна и ожидает, пока сообщение обработано процедуры окно перед возвращением.
## <a name="see-also"></a>См. также

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md)
