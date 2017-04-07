---
title: "Класс COleMessageFilter | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- COleMessageFilter class
- OLE [C++], managing concurrency
- message filters [C++]
- OLE applications [C++], managing interactions
- OLE messages
- applications [OLE], managing interactions
- messages [C++], OLE
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
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
ms.openlocfilehash: d91ed300bb6cade5d804fe4a74dfe6cc2e4384fe
ms.lasthandoff: 02/24/2017

---
# <a name="colemessagefilter-class"></a>Класс COleMessageFilter
Управляет параллелизмом, требуемым для взаимодействия приложений OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Создает объект `COleMessageFilter`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Переводит приложение в состоянии занятости.|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Включает и отключает диалоговым окном, которое появляется, когда вызванная приложение занято.|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Включает и отключает диалоговым окном, которое появляется, когда вызванная приложение не отвечает.|  
|[COleMessageFilter::EndBusyState](#endbusystate)|Завершает занят состояния приложения.|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Вызывается платформой для обработки сообщений, пока вызов OLE.|  
|[COleMessageFilter::Register](#register)|Регистрирует фильтр сообщений OLE системные библиотеки DLL.|  
|[COleMessageFilter::Revoke](#revoke)|Отменяет регистрацию фильтра сообщений с помощью OLE системные библиотеки DLL.|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Определяет, этому приложению ответ на вызов OLE.|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Определяет, как долго приложение ожидает ответа на вызов OLE.|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|Определяет ответ вызывающему приложению работающее приложение.|  
  
## <a name="remarks"></a>Примечания  
 `COleMessageFilter` Класс полезен в приложения визуального редактирования сервера и контейнера, а также приложений OLE-автоматизации. Для серверных приложений, которые вызываются этот класс может использоваться, чтобы сделать приложение «занят», чтобы входящие вызовы от других приложений контейнера либо отменить или повторить позже. Этот класс также можно определить действие, выполняемое вызывающего приложения при вызываемой приложение занято.  
  
 Распространенным вариантом применения является для серверного приложения для вызова [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) при было бы опасно для документа или других доступного объекта OLE будут уничтожены. Эти вызовы осуществляются в [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) во время обновления пользовательского интерфейса.  
  
 По умолчанию `COleMessageFilter` объект выделяется при инициализации приложения. Его можно извлечь с помощью [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
 Это дополнительно класс; редко требуется работать непосредственно с ним.  
  
 Дополнительные сведения см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="beginbusystate"></a>COleMessageFilter::BeginBusyState  
 Эта функция вызывается для начала состоянии занятости.  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>Примечания  
 Она работает совместно с [EndBusyState](#endbusystate) для контроля состояния занятости приложения. Функция [SetBusyReply](#setbusyreply) определяет приложения ответа на вызов приложения, если он занят.  
  
 `BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, счетчик, который определяет, является ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` могут приводить в состоянии занятости. Для отмены состоянии занятости, необходимо вызвать `EndBusyState` такое же количество раз `BeginBusyState` был вызван.  
  
 По умолчанию платформа переходит в состоянии занятости во время простоя обработки выполняется путем [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Во время обработки приложения **ON_COMMANDUPDATEUI** уведомления, входящие звонки обрабатываются позже, после завершения обработки бездействия.  
  
##  <a name="colemessagefilter"></a>COleMessageFilter::COleMessageFilter  
 Создает объект `COleMessageFilter`.  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>COleMessageFilter::EnableBusyDialog  
 Включает и выключает занят диалоговое окно отображается после истечения срока действия задержки ожидающих сообщений (см. [SetRetryReply](#setretryreply)) во время вызова OLE.  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableBusy*  
 Указывает, включен ли диалоговое окно «занят».  
  
##  <a name="enablenotrespondingdialog"></a>COleMessageFilter::EnableNotRespondingDialog  
 Включает и выключает «не отвечает» диалоговое окно отображается, если сообщение клавиатуры или мыши находится в состоянии ожидания во время OLE вызова и вызова истекло.  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableNotResponding*  
 Указывает, включен ли диалоговое окно «не отвечает».  
  
##  <a name="endbusystate"></a>COleMessageFilter::EndBusyState  
 Эта функция вызывается для завершения состоянии занятости.  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>Примечания  
 Она работает совместно с [BeginBusyState](#beginbusystate) для контроля состояния занятости приложения. Функция [SetBusyReply](#setbusyreply) определяет приложения ответа на вызов приложения, если он занят.  
  
 `BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, счетчик, который определяет, является ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` могут приводить в состоянии занятости. Для отмены состоянии занятости, необходимо вызвать `EndBusyState` такое же количество раз `BeginBusyState` был вызван.  
  
 По умолчанию платформа переходит в состоянии занятости во время простоя обработки выполняется путем [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Хотя приложение обрабатывает `ON_UPDATE_COMMAND_UI` уведомления, входящие звонки обрабатываются после завершения обработки бездействия.  
  
##  <a name="onmessagepending"></a>COleMessageFilter::OnMessagePending  
 Вызывается платформой для обработки сообщений, пока вызов OLE.  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель ожидающих сообщений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающее приложение ожидает завершения вызова, платформа вызывает `OnMessagePending` с указателем ожидающих сообщений. По умолчанию платформа отправляет `WM_PAINT` сообщения, чтобы окно обновления могут возникнуть во время вызова, который занимает много времени.  
  
 Необходимо зарегистрировать фильтр сообщений посредством вызова функции для [зарегистрировать](#register) перед может стать активным.  
  
##  <a name="register"></a>COleMessageFilter::Register  
 Регистрирует фильтр сообщений OLE системные библиотеки DLL.  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Фильтр сообщений не оказывает влияния, если не зарегистрирован с помощью системных библиотек DLL. Обычно в коде инициализации приложения регистрирует фильтр сообщений приложения. Другие фильтр сообщений, зарегистрированные с приложением, должны быть отозваны, прежде чем завершится выполнение программы с помощью вызова [отозвать](#revoke).  
  
 Фильтр сообщений по умолчанию платформа framework автоматически зарегистрирован во время инициализации и отменяется при завершении.  
  
##  <a name="revoke"></a>COleMessageFilter::Revoke  
 Отменяет предыдущую регистрацию выполняется путем вызова [зарегистрировать](#register).  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Фильтр сообщений должен быть отозван, прежде чем завершится выполнение программы.  
  
 Фильтр сообщений по умолчанию, который создан и зарегистрирован автоматически платформой, также автоматически отменяется.  
  
##  <a name="setbusyreply"></a>COleMessageFilter::SetBusyReply  
 Эта функция задает приложения «занят ответ.»  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>Параметры  
 *nBusyReply*  
 Значение из `SERVERCALL` перечисления, определенного в COMPOBJ. З. Он может иметь одно из следующих значений:  
  
- **SERVERCALL_ISHANDLED** приложение может принимать вызовы, но может завершиться ошибкой при обработке определенного вызова.  
  
- **SERVERCALL_REJECTED** приложение, возможно, никогда не смогут обработать вызов.  
  
- **SERVERCALL_RETRYLATER** приложение является временно в состоянии, в котором он не может обработать вызов.  
  
### <a name="remarks"></a>Примечания  
 [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) функции контроля состояния занятости приложения.  
  
 Когда приложение была сделана занятости с помощью вызова `BeginBusyState`, он отвечает на вызовы OLE системные библиотеки DLL со значением определяется последний параметр `SetBusyReply`. Вызывающее приложение использует занят ответ чтобы определить, какие действия предпринять.  
  
 По умолчанию — занят ответ **SERVERCALL_RETRYLATER**. Этот ответ приводит к как можно быстрее повторить вызов вызывающего приложения.  
  
##  <a name="setmessagependingdelay"></a>COleMessageFilter::SetMessagePendingDelay  
 Определяет, как долго вызывающее приложение ожидает ответа от вызываемой приложения перед выполнением дальнейших действий.  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>Параметры  
 `nTimeout`  
 Количество миллисекунд задержки ожидающих сообщений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция работает в сочетании с [SetRetryReply](#setretryreply).  
  
##  <a name="setretryreply"></a>COleMessageFilter::SetRetryReply  
 Определяет действие, вызывающее приложение при получении занят ответа с именем приложения.  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nRetryReply`  
 Количество миллисекунд между повторными попытками.  
  
### <a name="remarks"></a>Примечания  
 При вызываемой приложения означает, что занят, вызывающее приложение может определить подождать, пока сервер больше не занят, повторите сразу или повторите попытку через заданный интервал времени. Может также быть принято решение полностью отмены вызова.  
  
 Ответ вызывающей контролируется функциями `SetRetryReply` и [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply`Определяет время ожидания между повторными попытками для определенного вызова вызывающему приложению. `SetMessagePendingDelay`Определяет, как долго вызывающее приложение ожидает ответа от сервера перед выполнением дополнительные действия.  
  
 Обычно значения по умолчанию приемлемы, а не обязательно должны быть изменены. Платформа framework повторяет вызов каждый `nRetryReply` миллисекунд, пока вызов идет через или задержка ожидающих сообщений истек. Значение 0 для `nRetryReply` указывает немедленный повтор и – 1 указывает отмены вызова.  
  
 При истечении срока действия задержки ожидающих сообщений, OLE «занят диалоговое окно» (см. [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) отображается, чтобы выбрать пользователя можно отменить или повторить вызов. Вызов [EnableBusyDialog](#enablebusydialog) включить или отключить это диалоговое окно.  
  
 Когда сообщение клавиатуры или мыши находится в состоянии ожидания во время вызова и вызова истекло (превышено задержки ожидающих сообщений), откроется диалоговое окно «не отвечает». Вызов [EnableNotRespondingDialog](#enablenotrespondingdialog) включить или отключить это диалоговое окно. Обычно это состояние дел означает, что что-то пошло не так, и пользователь получает нетерпеливый.  
  
 При отключении диалоговые окна текущего «повтора ответ» всегда используется для вызовов занят приложений.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)

