---
title: Класс COleMessageFilter | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 585044a5da8ca3ce8b2650801558b19bf1d5ef59
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427801"
---
# <a name="colemessagefilter-class"></a>Класс COleMessageFilter

Управляет параллелизмом, требуемым для взаимодействия приложений OLE.

## <a name="syntax"></a>Синтаксис

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Создает объект `COleMessageFilter`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Помещает приложение в состоянии занятости.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Включает и отключает диалоговое окно, которое появляется, когда вызванная приложение занято.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Включает и отключает диалоговое окно, которое появляется, когда вызываемого приложения не отвечает.|
|[COleMessageFilter::EndBusyState](#endbusystate)|Завершает занятое состояние приложения.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Вызывается платформой для обработки сообщений, пока вызов OLE не выполняется.|
|[COleMessageFilter::Register](#register)|Регистрирует фильтр сообщений OLE системные библиотеки DLL.|
|[COleMessageFilter::Revoke](#revoke)|Отменяет регистрацию фильтра сообщений с OLE системные библиотеки DLL.|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Определяет, этому приложению ответ на вызов OLE.|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Определяет, как долго приложение ожидает ответа на вызов OLE.|
|[COleMessageFilter::SetRetryReply](#setretryreply)|Определяет ответ вызывающему приложению работающее приложение.|

## <a name="remarks"></a>Примечания

`COleMessageFilter` Класс полезен в приложения визуального редактирования сервера и контейнера, а также приложений OLE-автоматизации. Для серверных приложений, которые вызываются этот класс можно использовать, чтобы сделать приложение «busy», чтобы входящие вызовы от других приложений контейнера отменена или повторно отправлен позже. Этот класс также может использоваться для определения действий, выполняемый в вызывающем приложении, при вызываемого приложения занят.

Распространенным вариантом применения является для серверного приложения для вызова [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) когда было бы опасно для документа или других доступных OLE-объекта будут уничтожены. Эти вызовы осуществляются в [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) во время обновления пользовательского интерфейса.

По умолчанию `COleMessageFilter` объект выделяется при инициализации приложения. Его можно получить с помощью [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

Это расширенный класс; редко бывает нужно работать с ним напрямую.

Дополнительные сведения см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState

Вызывайте эту функцию, чтобы начать занятое состояние.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Примечания

Работает в сочетании с [EndBusyState](#endbusystate) для управления занятое состояние приложения. Функция [SetBusyReply](#setbusyreply) определяет ответа приложения для вызова приложения в том случае, когда он занят.

`BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, счетчик, определяющий, будет ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` будет иметь занятое состояние. Чтобы отменить занятое состояние, необходимо вызвать `EndBusyState` такое же количество раз `BeginBusyState` был вызван.

По умолчанию платформа вводит состоянии занятости во время простоя обработки, которую выполняет [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Хотя приложение обрабатывает ON_COMMANDUPDATEUI уведомления, входящие вызовы, обрабатываются позже, после успешного завершения обработки простоя.

##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter

Создает объект `COleMessageFilter`.

```
COleMessageFilter();
```

##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog

Включает и отключает занят диалоговом окне, которая отображается по истечении срока действия задержки ожидающих сообщений (см. в разделе [SetRetryReply](#setretryreply)) во время вызова OLE.

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableBusy*<br/>
Указывает, включена ли диалоговое окно «занят».

##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog

Включает и отключает «не отвечает» диалоговое окно, которое отображается, если сообщение клавиатуры или мыши находится в состоянии ожидания во время OLE и вызовами обнаружил превышение времени ожидания.

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableNotResponding*<br/>
Указывает, включена ли диалоговое окно «не отвечает».

##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState

Вызывайте эту функцию, чтобы завершить занятое состояние.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Примечания

Работает в сочетании с [BeginBusyState](#beginbusystate) для управления занятое состояние приложения. Функция [SetBusyReply](#setbusyreply) определяет ответа приложения для вызова приложения в том случае, когда он занят.

`BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, счетчик, определяющий, будет ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` будет иметь занятое состояние. Чтобы отменить занятое состояние, необходимо вызвать `EndBusyState` такое же количество раз `BeginBusyState` был вызван.

По умолчанию платформа вводит состоянии занятости во время простоя обработки, которую выполняет [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Пока приложение обрабатывает ON_UPDATE_COMMAND_UI уведомления, входящие вызовы, обрабатываются после завершения обработки бездействия.

##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending

Вызывается платформой для обработки сообщений, пока вызов OLE не выполняется.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на ожидающих сообщений.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Если вызывающее приложение ожидает вызов, чтобы завершить, платформа вызывает `OnMessagePending` с указателем на ожидающих сообщений. По умолчанию платформа отправляет сообщения WM_PAINT таким образом, чтобы окно обновления могут возникнуть во время вызова, который занимает много времени.

Необходимо зарегистрировать ваш фильтр сообщений посредством вызова [зарегистрировать](#register) прежде, чем он может стать активным.

##  <a name="register"></a>  COleMessageFilter::Register

Регистрирует фильтр сообщений OLE системные библиотеки DLL.

```
BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Фильтр сообщений не оказывает влияния, если не зарегистрирован с помощью системных библиотек DLL. Обычно код инициализации приложения регистрирует фильтр сообщений приложения. Любой другой фильтр сообщений, зарегистрированные для приложения, которые должны быть отозваны, перед завершением работы программы путем вызова [отозвать](#revoke).

Фильтр сообщений по умолчанию платформы автоматически зарегистрирован во время инициализации и отозваны при завершении.

##  <a name="revoke"></a>  COleMessageFilter::Revoke

Отменяет предыдущую регистрацию выполнить путем вызова [зарегистрировать](#register).

```
void Revoke();
```

### <a name="remarks"></a>Примечания

Фильтр сообщений должны быть отозваны, перед завершением работы программы.

Фильтр сообщений по умолчанию, который создается и регистрируется автоматически платформой, также автоматически отменяется.

##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply

Эта функция задает приложения «занят ответить.»

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Параметры

*nBusyReply*<br/>
Значение из `SERVERCALL` перечисления, который определен в COMPOBJ. З. Он может содержать любое из следующих значений:

- SERVERCALL_ISHANDLED приложения могут принимать вызовы, но может завершиться ошибкой при обработке определенного вызова.

- SERVERCALL_REJECTED приложение, скорее всего, никогда не сможет обработать вызов.

- SERVERCALL_RETRYLATER приложения временно находится в состоянии, в котором он не может обработать вызов.

### <a name="remarks"></a>Примечания

[BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) функции управления занятое состояние приложения.

Когда приложение уже внесено занят вызовом `BeginBusyState`, он отвечает на вызовы от OLE системные библиотеки DLL со значением, определяется последний параметр `SetBusyReply`. Вызывающее приложение использует занят ответ, чтобы определить какое действие следует предпринять.

По умолчанию занят ответа является SERVERCALL_RETRYLATER. Этот ответ позволяет вызывающей приложению предусматривать возможность повторного вызова как можно скорее.

##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay

Определяет, как долго вызывающее приложение ожидает ответа от вызываемого приложения, прежде чем выполнять дальнейшие действия.

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Параметры

*nвремя ожидания*<br/>
Количество миллисекунд задержки ожидающих сообщений.

### <a name="remarks"></a>Примечания

Эта функция работает в сочетании с [SetRetryReply](#setretryreply).

##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply

Определяет действие вызывающего приложения при получении ответа, занят из вызываемого приложения.

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Параметры

*nRetryReply*<br/>
Число миллисекунд между повторными попытками.

### <a name="remarks"></a>Примечания

Если вызываемого приложения указывает, что он занят, вызывающему приложению может потребоваться подождать, пока сервер больше не занят, чтобы повторить попытку прямо сейчас или повторить попытку через заданный интервал. Он также может решить отменить вызов полностью.

Ответ вызывающей стороны, контролируется функциями `SetRetryReply` и [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` Определяет время ожидания между повторными попытками для определенного вызова вызывающему приложению. `SetMessagePendingDelay` Определяет, как долго вызывающее приложение ожидает ответ от сервера, прежде чем выполнять другие действия.

Обычно значения по умолчанию являются допустимыми и не обязательно должны быть изменены. Платформа повторяет вызов каждый *nRetryReply* миллисекунд, пока вызов идет через или истек срок действия задержки ожидающих сообщений. Значение 0 для *nRetryReply* указывает немедленный повтор и - 1 указывает отмены вызова.

Когда истек срок действия задержки ожидающих сообщений, OLE «занят диалоговое окно» (см. в разделе [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) отображается таким образом, пользователь может отменить или повторить вызов. Вызовите [EnableBusyDialog](#enablebusydialog) включить или отключить это диалоговое окно.

Если ожидается сообщение клавиатуры или мыши во время вызова и вызова истекло (превышено задержка ожидающих сообщений), откроется диалоговое окно «не отвечает». Вызовите [EnableNotRespondingDialog](#enablenotrespondingdialog) включить или отключить это диалоговое окно. Обычно это состояние дел указывает, что что-то пошло не так, и пользователь получает поспешит.

При отключении диалоговые окна текущего «повторить ответа» всегда используется для вызовов к приложениям занят.

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
