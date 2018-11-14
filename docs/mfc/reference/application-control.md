---
title: Управление приложением
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 55a5dcad21502e7aff7427dbdad41d25298356e7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518922"
---
# <a name="application-control"></a>Управление приложением

OLE требует существенного контроля над приложениями и их объекты. OLE системные библиотеки DLL должны иметь возможность запуска и выпускать приложения автоматически координации работы и изменением объектов и т. д. Функции в этом разделе соответствует этим требованиям. В дополнение к их вызова OLE системные библиотеки DLL, эти функции должен вызываться иногда также приложениями.

### <a name="application-control"></a>Управление приложением

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|Указывает, можно ли завершить приложение.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Извлекает текущий фильтр сообщений приложения.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Извлекает текущий флаг пользовательских элементов управления.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Устанавливает или снимает флаг пользовательских элементов управления.|
|[AfxOleLockApp](#afxolelockapp)|Увеличивает платформы глобальный счетчик количества активных объектов в приложении.|
|[AfxOleLockControl](#afxolelockcontrol)| Блокирует фабрики класса указанного элемента управления. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Уменьшает счетчик количества активных объектов в приложении платформы.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Разблокирует фабрики класса указанного элемента управления. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Регистрирует сервер в системном реестре OLE.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Реализует пользовательский интерфейс для *typename* команда объектов.|

##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp

Указывает, можно ли завершить приложение.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если приложение можно будет завершать работу; в противном случае 0.

### <a name="remarks"></a>Примечания

Приложения не следует прервать, при наличии ссылки на медиафайл к своим объектам. Глобальные функции `AfxOleLockApp` и `AfxOleUnlockApp` увеличения и уменьшения, соответственно, счетчик ссылок на объекты приложения. Приложение не следует прервать, когда этот счетчик не равно нулю. Если счетчик имеет ненулевое значение, главное окно приложения скрывается (не уничтоженный), когда пользователь выбирает закрыть из меню системы или выхода из меню "файл". Платформа вызывает эту функцию `CFrameWnd::OnClose`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter

Извлекает текущий фильтр сообщений приложения.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий фильтр сообщений.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы получить доступ к текущим `COleMessageFilter`-объект, производной от, так же, как можно вызвать `AfxGetApp` доступ к объекту текущего приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок**: afxwin.h

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl

Извлекает текущий флаг пользовательских элементов управления.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользователь находится в элемент управления приложения; в противном случае 0.

### <a name="remarks"></a>Примечания

Пользователь находится в элемент управления приложения, если пользователь явным образом открыть или создать новый документ. Пользователь также находится в элемент управления, если приложение не было запущено с OLE системные библиотеки DLL — другими словами, если пользователь запустил приложение в оболочке системы.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl

Устанавливает или снимает флаг пользовательских элементов управления, как описано в справочнике по `AfxOleGetUserCtrl`.

```
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>Параметры

*bUserCtrl*<br/>
Указывает, является ли флаг пользовательских элементов управления нужно установить или очистить.

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию, когда пользователь создает или загружает документ, но не в том случае, если документ загружен или созданных с помощью косвенных действие, как загрузка внедренного объекта из приложения-контейнера.

Эта функция вызывается в том случае, если другие действия в приложении следует поместить пользователя в элементе управления приложения.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp

Увеличивает платформы глобальный счетчик количества активных объектов в приложении.

```
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>Примечания

Платформа поддерживает счетчик количество объектов, которые активны в приложение. `AfxOleLockApp` И `AfxOleUnlockApp` функции, соответственно, увеличения и уменьшения этого числа.

Когда пользователь пытается закрыть приложение, имеющее активных объектов — приложение, для которого не равно нулю число активных объектов — framework скрывает приложение из представления пользователя, а не полностью завершать работу. `AfxOleCanExitApp` Функции указывает, можно ли завершить приложение.

Вызовите `AfxOleLockApp` из любой объект, который предоставляет интерфейсы OLE, в том случае, если было бы нежелательным для этого объекта будет уничтожен во время ее использования клиентским приложением. Также вызвать `AfxOleUnlockApp` в деструкторе любого объекта, который вызывает `AfxOleLockApp` в конструкторе. По умолчанию `COleDocument` (и производных классах) автоматически блокировать и разблокировать приложение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  AfxOleUnlockApp

Уменьшает число платформы активных объектов в приложении.

```
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>Примечания

См. в разделе `AfxOleLockApp` для получения дополнительных сведений.

Когда число активных объектов достигает нуля, `AfxOleOnReleaseAllObjects` вызывается.

### <a name="example"></a>Пример

См. в примере [AfxOleLockApp](#afxolelockapp).

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

Блокирует фабрики класса указанного элемента управления, таким образом, чтобы динамически созданные данные, связанные с элементом управления остается в памяти.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Класс уникальный идентификатор элемента управления.

*lpszProgID*<br/>
Уникальный идентификатор программы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика класса элемента управления было успешно заблокировано; в противном случае 0.

### <a name="remarks"></a>Примечания

Это позволяет существенно ускорить отображение элементов управления. Например, после создания элемента управления в диалоговом окне и заблокировать элемент управления с `AfxOleLockControl`, необходимо создать и остановите его снова каждый раз, видима или уничтожения диалогового окна. Если пользователь открывает и закрывает диалоговое окно повторно, блокировку к элементам управления может значительно повысить производительность. Когда будете готовы удалить элемент управления, вызовите `AfxOleUnlockControl`.

### <a name="example"></a>Пример

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[AfxOleUnlockControl](#afxoleunlockcontrol)

##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass

Эта функция позволяет зарегистрировать сервер в системном реестре OLE.

```
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,
    LPCTSTR lpszClassName,
    LPCTSTR lpszShortTypeName,
    LPCTSTR lpszLongTypeName,
    OLE_APPTYPE nAppType = OAT_SERVER,
    LPCTSTR* rglpszRegister = NULL,
    LPCTSTR* rglpszOverwrite = NULL);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Ссылка на идентификатор сервера OLE класса.

*lpszClassName*<br/>
Указатель на строку, содержащую имя класса объектов сервера.

*lpszShortTypeName*<br/>
Указатель на строку, содержащую короткое имя типа объекта сервера, например «Диаграмма».

*lpszLongTypeName*<br/>
Указатель на строку, содержащую длинное имя типа объекта сервера, например «Microsoft Excel 5.0 диаграммы».

*nAppType*<br/>
Значение, взятое из перечисления OLE_APPTYPE, указав тип OLE-приложения. Ниже перечислены возможные значения:

- OAT_INPLACE_SERVER сервер имеет полный сервер пользовательского интерфейса.

- OAT_SERVER сервер поддерживает только внедрения.

- OAT_CONTAINER контейнер поддерживает ссылки на внедряемые объекты.

- OAT_DISPATCH_OBJECT `IDispatch`-поддержкой объекта.

*rglpszRegister*<br/>
Массив указателей на строки, представляющие разделы и значения, которое необходимо добавить в системный реестр OLE, если нет существующего значения для ключей не найдены.

*rglpszOverwrite*<br/>
Массив указателей на строки, представляющие разделы и значения, которое необходимо добавить в системный реестр OLE, если реестр содержит существующие значения для указанных ключей.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если класс сервера успешно зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Большинство приложений может использовать `COleTemplateServer::Register` для регистрации типов документов приложения. Если формат системного реестра приложения не соответствует стандартным образом, можно использовать `AfxOleRegisterServerClass` для большего контроля.

Реестр состоит из набора ключей и значений. *RglpszRegister* и *rglpszOverwrite* аргументы представляют собой массивы указателей на строки, состоящий из ключа и значения разделенных **NULL** символ ( `'\0'`). Каждый из этих строк может содержать подстановочных параметров которого местах отмечаются последовательности символов *%1* через *%5*.

Символы заполняются следующим образом:

|Символ|Значение|
|------------|-----------|
|%1|Идентификатор класса, представлен в виде строки|
|%2|Имя класса|
|%3|Путь к исполняемому файлу|
|%4|Краткое имя типа|
|%5|Имя типа Long|

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu

Реализует пользовательский интерфейс для *typename* команда объектов.

```
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,
    CMenu* pMenu,
    UINT iMenuItem,
    UINT nIDVerbMin,
    UINT nIDVerbMax = 0,
    UINT nIDConvert = 0);
```

### <a name="parameters"></a>Параметры

*pClient*<br/>
Указатель на элемент клиента OLE.

*pMenu*<br/>
Указатель на объект меню обновления.

*iMenuItem*<br/>
Индекс обновляемого элемента меню.

*nIDVerbMin*<br/>
Идентификатор команды, соответствующий первичный глагол.

*nIDVerbMax*<br/>
Идентификатор команды, соответствующее последней команды.

*nIDConvert*<br/>
Идентификатор для пункта меню Convert.

### <a name="remarks"></a>Примечания

Если сервер распознает только первичный глагол, становится пункта меню «Команда *typename* объекта» и *nIDVerbMin* команда отправляется в том случае, когда пользователь выбирает команду. Если сервер распознает несколько команд, а затем пункт меню становится " *typename* объекта» и список всех команд подменю появляется, когда пользователь выбирает команду. Когда пользователь выбирает команду в подменю *nIDVerbMin* отправляется, если выбирается первая команда, *nIDVerbMin* + 1 отправляется в том случае, если вторая команда выбран и т. д. Значение по умолчанию `COleDocument` реализации автоматически обрабатывает эту функцию.

Необходимо иметь следующую инструкцию в сценарий ресурсов приложения клиента (. Версия-Кандидат) файла.

**#include \<afxolecl.rc >**

### <a name="requirements"></a>Требования

**Заголовок**: afxole.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl

Разблокирует фабрики класса указанного элемента управления.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Класс уникальный идентификатор элемента управления.

*lpszProgID*<br/>
Уникальный идентификатор программы элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если фабрика класса элемента управления был успешно разблокирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Элемент управления заблокирован с `AfxOleLockControl`, таким образом, чтобы динамически созданные данные, связанные с элементом управления остается в памяти. Это может значительно ускорить отображение элемента управления, так как не элемент управления должны создаваться и уничтожаться, каждый раз, он отображается. Когда будете готовы удалить элемент управления, вызовите `AfxOleUnlockControl`.

### <a name="example"></a>Пример

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[AfxOleLockControl](#afxolelockcontrol)

