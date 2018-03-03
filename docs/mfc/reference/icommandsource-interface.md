---
title: "Интерфейс руководство. | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc8ad34ccce059caca8e86a014622e29c14022ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="icommandsource-interface"></a>Интерфейс руководство.
Управляет команды, отправляемые из исходного объекта команды в пользовательском элементе управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Добавляет обработчик команд объект источника команды.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Добавляет группу обработчики команд объект источника команды.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Добавляет группу обработчики сообщений команды пользовательского интерфейса на объект источника команды.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Добавляет обработчик сообщений команды интерфейса пользователя объект источника команды.|  
|[ICommandSource::PostCommand](#postcommand)|Отправляет сообщение, не ожидая его обработки.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Удаляет обработчик команд из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Удаляет группу обработчики команд из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Удаляет группу обработчики сообщений команды пользовательского интерфейса из исходного объекта команды.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Удаляет обработчик сообщения команды интерфейс пользователя из исходного объекта команды.|  
|[ICommandSource::SendCommand](#sendcommand)|Отправляет сообщение и ожидает его обработки перед возвратом.|  
  
### <a name="remarks"></a>Примечания  
 Если разместить пользовательский элемент управления в представлении MFC [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды пользовательского интерфейса сообщения в пользовательский элемент управления мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации [интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md), вы предоставляете ссылку на пользовательский элемент управления `ICommandSource` объекта.  
  
 В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
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
Этот метод добавляет cmdHandler обработчик команд в исходный объект команды и сопоставляется cmdID обработчик.
В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование AddCommandHandler.

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

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

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
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

## <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler
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
Этот метод добавляет cmdHandler обработчика сообщения пользовательского интерфейса команды исходный объект команды и сопоставляется cmdID обработчик.

## <a name="postcommand"></a>ICommandSource::PostCommand
Отправляет сообщение, не ожидая его обработки.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>Параметры
`command`  
Идентификатор команды сообщения должны быть учтены.
### <a name="remarks"></a>Примечания
Этот метод асинхронно отправляет сообщение, сопоставлен с Идентификатором, указанным параметром команды. Он вызывает CWnd::PostMessage, чтобы поместить сообщение в очередь сообщений окна и возвращается без ожидания соответствующее окно для обработки сообщения.


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
Удаляет обработчик команд из исходного объекта команды.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Параметры
`cmdID`  
Идентификатор команды.
### <a name="remarks"></a>Примечания
Этот метод удаляет обработчик команд, сопоставленный с cmdID исходный объект команды.


## <a name="removecommandrangecommandhandler"></a>ICommandSource::RemoveCommandRangeHandler 
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
Этот метод удаляет группу обработчики сообщений, сопоставленный с указанных идентификаторов команд, cmdIDMin и cmdIDMax, исходный объект команды.

## <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler 
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
Этот метод удаляет группу пользователя интерфейс сообщения обработчики команд, сопоставленный с указанных идентификаторов команд, cmdIDMin и cmdIDMax, исходный объект команды.

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
Удаляет обработчик сообщения команды интерфейс пользователя из исходного объекта команды.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Параметры
`cmdID`  
Идентификатор команды.
### <a name="remarks"></a>Примечания
Этот метод удаляет cmdID, полученного из исходного объекта команды обработчик сообщения команды пользовательского интерфейса.

## <a name="sendcommand"></a>ICommandSource::SendCommand 
Отправляет сообщение и ожидает его обработки перед возвратом.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>Параметры
`command`  
Идентификатор команды отправляемого сообщения.
### <a name="remarks"></a>Примечания
Этот метод синхронно отправляет сообщение, сопоставлен с Идентификатором, указанным параметром команды. Он вызывает CWnd::SendMessage, чтобы поместить сообщение в очередь сообщений окна и ожидает, пока сообщение обработано процедуры окна перед возвратом.
## <a name="see-also"></a>См. также  
 [Как: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [Интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md)
