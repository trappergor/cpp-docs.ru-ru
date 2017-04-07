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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0cbc95bc492c69549a15bba3f4594e293be1c9f7
ms.lasthandoff: 04/01/2017

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
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Включает и отключает диалоговым окном, появляется, когда вызываемый приложение занято.|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Включает и отключает диалоговым окном, которое появляется при вызываемой приложение не отвечает.|  
|[COleMessageFilter::EndBusyState](#endbusystate)|Завершает занят состояния приложения.|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Вызывается платформой для обработки сообщений, пока вызов OLE не выполняется.|  
|[COleMessageFilter::Register](#register)|Регистрирует фильтр сообщений OLE системные библиотеки DLL.|  
|[COleMessageFilter::Revoke](#revoke)|Отменяет регистрацию фильтр сообщений с OLE системные библиотеки DLL.|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Определяет, этому приложению ответ на вызов OLE.|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Определяет, как долго приложение ожидает ответа на вызов OLE.|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|Определяет ответ вызывающему приложению работающее приложение.|  
  
## <a name="remarks"></a>Примечания  
 `COleMessageFilter` Класс полезен в приложения визуального редактирования сервера и контейнера, а также приложений OLE-автоматизации. Для серверных приложений, которые вызываются этот класс может использоваться, чтобы сделать приложение «занят», чтобы входящие вызовы от других приложений контейнера отменено или повторно отправлен позже. Этот класс может также использоваться для определения действий, для выполнения вызывающем приложении при вызываемой приложение занято.  
  
 Распространенным вариантом применения является для серверного приложения для вызова [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) при было бы опасно для документа или других доступного объекта OLE будут уничтожены. Эти вызовы осуществляются в [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) во время обновления пользовательского интерфейса.  
  
 По умолчанию `COleMessageFilter` объект выделяется при инициализации приложения. Его можно извлечь с помощью [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
 Это дополнительно класс; редко требуется работать с ним напрямую.  
  
 Дополнительные сведения см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="beginbusystate"></a>COleMessageFilter::BeginBusyState  
 Вызывайте эту функцию, чтобы начать занятое состояние.  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>Примечания  
 Оно работает в сочетании с [EndBusyState](#endbusystate) для контроля состояния занятости приложения. Функция [SetBusyReply](#setbusyreply) определяет приложения ответа на вызов приложения, если оно занято.  
  
 `BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, в счетчике, который определяет, является ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` могут приводить к созданию занятое состояние. Для отмены занятое состояние, необходимо вызвать `EndBusyState` одинаковое количество раз `BeginBusyState` был вызван.  
  
 По умолчанию платформа вводит занятое состояние во время простоя обработки, которая выполняется путем [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). При обработке приложения **ON_COMMANDUPDATEUI** уведомления входящих вызовов обрабатываются позже, после завершения обработки бездействия.  
  
##  <a name="colemessagefilter"></a>COleMessageFilter::COleMessageFilter  
 Создает объект `COleMessageFilter`.  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>COleMessageFilter::EnableBusyDialog  
 Включает и отключает занят диалоговым окном, которое отображается после истечения срока действия задержки ожидающих сообщений (в разделе [SetRetryReply](#setretryreply)) во время вызова OLE.  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableBusy*  
 Указывает, включен ли диалоговое окно «занят».  
  
##  <a name="enablenotrespondingdialog"></a>COleMessageFilter::EnableNotRespondingDialog  
 Включает и отключает «не отвечает» диалоговым окном, которое отображается, если сообщение клавиатуры или мыши ожидает во время OLE вызова и вызова истекло.  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnableNotResponding*  
 Указывает, включен ли диалоговое окно «не отвечает».  
  
##  <a name="endbusystate"></a>COleMessageFilter::EndBusyState  
 Эта функция вызывается для завершения занятое состояние.  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>Примечания  
 Оно работает в сочетании с [BeginBusyState](#beginbusystate) для контроля состояния занятости приложения. Функция [SetBusyReply](#setbusyreply) определяет приложения ответа на вызов приложения, если оно занято.  
  
 `BeginBusyState` И `EndBusyState` вызовы увеличения и уменьшения, соответственно, в счетчике, который определяет, является ли приложение занято. Например, два вызова к `BeginBusyState` и один вызов `EndBusyState` могут приводить к созданию занятое состояние. Для отмены занятое состояние, необходимо вызвать `EndBusyState` одинаковое количество раз `BeginBusyState` был вызван.  
  
 По умолчанию платформа вводит занятое состояние во время простоя обработки, которая выполняется путем [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Хотя приложение обрабатывает `ON_UPDATE_COMMAND_UI` уведомления входящих вызовов обрабатываются после завершения обработки бездействия.  
  
##  <a name="onmessagepending"></a>COleMessageFilter::OnMessagePending  
 Вызывается платформой для обработки сообщений, пока вызов OLE не выполняется.  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель ожидающих сообщений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающее приложение ожидает завершения вызова, платформа вызывает `OnMessagePending` с указателем ожидающих сообщений. По умолчанию платформа отправляет `WM_PAINT` сообщений, чтобы окно могут обновляться во время вызова, который занимает больше времени.  
  
 Необходимо зарегистрировать фильтр сообщений с помощью вызова [зарегистрировать](#register) перед может стать активным.  
  
##  <a name="register"></a>COleMessageFilter::Register  
 Регистрирует фильтр сообщений OLE системные библиотеки DLL.  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Фильтр сообщений действует только после его регистрации в системные библиотеки DLL. Обычно код инициализации приложения регистрирует фильтр сообщений приложения. Любой другой фильтр сообщений, зарегистрированные для приложения, которые должны быть отозваны, перед завершением работы программы путем вызова [отозвать](#revoke).  
  
 Фильтр сообщений по умолчанию платформа framework автоматически регистрируются во время инициализации и отменяется при завершении.  
  
##  <a name="revoke"></a>COleMessageFilter::Revoke  
 Отменяет предыдущую регистрацию выполняется путем вызова [зарегистрировать](#register).  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Фильтр сообщений должны быть отозваны, перед завершением работы программы.  
  
 Фильтр сообщений по умолчанию, который создан и зарегистрирован автоматически платформой, также автоматически отменяется.  
  
##  <a name="setbusyreply"></a>COleMessageFilter::SetBusyReply  
 Эта функция задает приложения «занят ответ.»  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>Параметры  
 *nBusyReply*  
 Значение из `SERVERCALL` перечисления, который определен в COMPOBJ. З. Он может иметь одно из следующих значений:  
  
- **SERVERCALL_ISHANDLED** приложения могут принимать вызовы, но может завершиться ошибкой при обработке определенного вызова.  
  
- **SERVERCALL_REJECTED** приложение, вероятно, никогда не будет обрабатывать вызов.  
  
- **SERVERCALL_RETRYLATER** приложение является временно в состоянии, в котором он не может обработать вызов.  
  
### <a name="remarks"></a>Примечания  
 [BeginBusyState](#beginbusystate) и [EndBusyState](#endbusystate) функции управления состоянием занятости приложения.  
  
 Если приложения были внесены занят с помощью вызова `BeginBusyState`, он реагирует на запросы из DLL-библиотеки OLE системы со значением, последний параметр `SetBusyReply`. Вызывающему приложению использует этот ответ занят, чтобы определить, какое действие необходимо выполнить.  
  
 По умолчанию — занят ответ **SERVERCALL_RETRYLATER**. Этот ответ приводит к как можно быстрее повторить вызов вызывающего приложения.  
  
##  <a name="setmessagependingdelay"></a>COleMessageFilter::SetMessagePendingDelay  
 Определяет, как долго вызывающее приложение ожидает ответа от вызванной приложением перед выполнением дополнительных действий.  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>Параметры  
 `nTimeout`  
 Количество миллисекунд для задержки ожидающих сообщений.  
  
### <a name="remarks"></a>Примечания  
 Эта функция работает в сочетании с [SetRetryReply](#setretryreply).  
  
##  <a name="setretryreply"></a>COleMessageFilter::SetRetryReply  
 Определяет действие, вызывающее приложение при получении занят ответа от вызванной приложения.  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nRetryReply`  
 Количество миллисекунд между повторными попытками.  
  
### <a name="remarks"></a>Примечания  
 При вызываемой приложения указывает, что он занят, вызывающему приложению может потребоваться подождать, пока сервер больше не будет загружен, повторите прямо сейчас, или повторить попытку через заданный интервал. Он также может возникнуть необходимость отмены вызова вообще.  
  
 Управляет ответ вызывающей функции `SetRetryReply` и [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply`Определяет время ожидания между повторными попытками для данного вызова вызывающему приложению. `SetMessagePendingDelay`Определяет, как долго вызывающее приложение ожидает ответа от сервера перед выполнением дополнительные действия.  
  
 Обычно значения по умолчанию являются допустимыми и не обязательно должны быть изменены. Платформа повторяет вызов каждый `nRetryReply` миллисекунд до его вызов направляется или истек срок действия задержки ожидающих сообщений. Значение 0 для `nRetryReply` указывает немедленная повторная попытка и - 1 указывает, отмены вызова.  
  
 При истечении срока действия задержки ожидающих сообщений, OLE «занят диалоговым окном» (см. [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) отображается, чтобы пользователь может выбрать отменить или повторить вызов. Вызовите [EnableBusyDialog](#enablebusydialog) для включения или отключения данным диалоговым окном.  
  
 Когда сообщение клавиатуры или мыши находится в состоянии ожидания во время вызова и вызова превышено время ожидания (превышает задержки ожидающих сообщений), откроется диалоговое окно «не отвечает». Вызовите [EnableNotRespondingDialog](#enablenotrespondingdialog) для включения или отключения данным диалоговым окном. Обычно это состояние дел указывает, что пошло так, и пользователь получает поспешит.  
  
 При отключении диалоговые окна текущего «повторить ответ» всегда используется для вызовов занят приложений.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

