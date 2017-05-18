---
title: "Интерфейс ICommandSource | Документы Microsoft"
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
- ICommandSource interface
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f923a8a42327cb74ce9323f72aae90c7411da27c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="icommandsource-interface"></a>Интерфейс ICommandSource
Управляет команды, отправляемые из исходного объекта команды пользовательского элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Добавляет обработчик команды объект источника команды.|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Добавляет группу обработчиков команд объект источника команды.|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Добавляет группу обработчики сообщений команды интерфейса пользователя на объект источника команды.|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Добавляет обработчик сообщений команды интерфейса пользователя объект источника команды.|  
|[ICommandSource::PostCommand](#postcommand)|Посылает сообщение, не дожидаясь его обработки.|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Удаляет обработчик команды из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Удаляет группу обработчиков команд из исходного объекта команды.|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Удаляет группу обработчики сообщений команды интерфейса пользователя из исходного объекта команды.|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.|  
|[ICommandSource::SendCommand](#sendcommand)|Отправляет сообщение и ожидает его для обработки перед возвратом.|  
  
### <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC, [класс CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команду сообщения пользовательского интерфейса в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации [интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md), предоставить ссылку на пользовательский элемент управления `ICommandSource` объекта.  
  
 В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
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
Этот метод добавляет объект источника команды cmdHandler обработчик команды и сопоставляет обработчик cmdID.
В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](https://msdn.microsoft.com/library/y33d8624.aspx) пример использования AddCommandHandler.

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

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

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
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
Дескриптор метод обработки сообщений команды интерфейса пользователя.

### <a name="remarks"></a>Примечания
Этот метод добавляет объект источника команды cmdHandler обработчик сообщений пользователя интерфейса командной и сопоставляет обработчик cmdID.

## <a name="postcommand"></a>ICommandSource::PostCommand
Посылает сообщение, не дожидаясь его обработки.
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>Параметры
`command`  
Идентификатор команды сообщения для публикации.
### <a name="remarks"></a>Примечания
Этот метод асинхронно отправляет сообщение сопоставляется с Идентификатором, указанным параметром команды. Он вызывает CWnd::PostMessage, чтобы поместить сообщение в очередь сообщений окна и затем возвращается без ожидания соответствующее окно для обработки сообщения.


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
Удаляет обработчик команды из исходного объекта команды.
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Параметры
`cmdID`  
Идентификатор команды.
### <a name="remarks"></a>Примечания
Этот метод удаляет обработчик команды, сопоставленный с cmdID исходный объект команды.


## <a name="removecommandrangecommandhandler"></a>ICommandSource::RemoveCommandRangeHandler 
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
Этот метод удаляет группу обработчиков сообщений, сопоставленный с указанных идентификаторов команд, cmdIDMin и cmdIDMax, исходный объект команды.

## <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler 
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
Этот метод удаляет группу пользователя интерфейс сообщения обработчиков команд, сопоставленный с указанных идентификаторов команд, cmdIDMin и cmdIDMax, исходный объект команды.

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
Удаляет обработчик сообщений команды интерфейса пользователя из исходного объекта команды.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>Параметры
`cmdID`  
Идентификатор команды.
### <a name="remarks"></a>Примечания
Этот метод удаляет обработчик пользовательского интерфейса команды сообщение cmdID, полученного из исходного объекта команды.

## <a name="sendcommand"></a>ICommandSource::SendCommand 
Отправляет сообщение и ожидает его для обработки перед возвратом.
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>Параметры
`command`  
Идентификатор команды отправляемого сообщения.
### <a name="remarks"></a>Примечания
Этот метод синхронно отправляет сообщение сопоставляется с Идентификатором, указанным параметром команды. Он вызывает CWnd::SendMessage, чтобы поместить сообщение в очередь сообщений окна и ожидает, пока сообщение обработано, процедура окна перед возвратом.
## <a name="see-also"></a>См. также  
 [Практическое руководство: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [Интерфейс ICommandTarget](../../mfc/reference/icommandtarget-interface.md)

