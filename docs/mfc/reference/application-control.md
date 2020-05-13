---
title: Управление приложением
ms.date: 11/04/2016
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
ms.openlocfilehash: 7e18b4504ddbfdd9a4399f33c34c6e6e9900233b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752854"
---
# <a name="application-control"></a>Управление приложением

OLE требует существенного контроля над приложениями и их объектами. DLL системы OLE должны быть в состоянии автоматически запускать и выпускать приложения, координировать их производство и модификацию объектов и так далее. Функции в этой теме отвечают этим требованиям. Помимо того, что эти функции называются DLL системой OLE, эти функции иногда должны вызываться приложениями.

### <a name="application-control"></a>Управление приложением

|||
|-|-|
|[AfxOleCanExitApp](#afxolecanexitapp)|Указывает, может ли приложение быть завершено.|
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|Извлекает текущий фильтр сообщения приложения.|
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|Извлекает текущий флаг управления пользователем.|
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|Устанавливает или очищает флаг управления пользователем.|
|[AfxOleLockApp](#afxolelockapp)|Приравливывает глобальное количество активных объектов в приложении.|
|[AfxOleLockControl](#afxolelockcontrol)| Блокирует фабрику классов указанного элемента управления. |
|[AfxOleUnlockApp](#afxoleunlockapp)|Утилищает количество активных объектов в приложении.|
|[AfxOleUnlockControl](#afxoleunlockcontrol)| Открывает фабрику класса указанного элемента управления. |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|Регистрирует сервер в реестре системы OLE.|
|[AfxOleSetEditMenu](#afxoleseteditmenu)|Реализует пользовательский интерфейс для команды *typename* Object.|

## <a name="afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp

Указывает, может ли приложение быть завершено.

```
BOOL AFXAPI AfxOleCanExitApp();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если приложение может выйти; в противном случае 0.

### <a name="remarks"></a>Remarks

Приложение не должно прекращаться, если есть невыполненные ссылки на его объекты. Глобальные `AfxOleLockApp` функции и `AfxOleUnlockApp` приращения и декременты, соответственно, счетчик ссылок на объекты приложения. Приложение не должно прекращаться, когда этот счетчик является ненулевым. Если счетчик незеро, основное окно приложения скрыто (не уничтожено), когда пользователь выбирает Close from the system menu или Exit from the File menu. Платформа вызывает эту `CFrameWnd::OnClose`функцию в .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter

Извлекает текущий фильтр сообщения приложения.

```
COleMessageFilter* AFXAPI AfxOleGetMessageFilter();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий фильтр сообщения.

### <a name="remarks"></a>Remarks

Вызовите эту функцию для доступа к объекту, полученному из текущего, `COleMessageFilter`точно так же, как вы могли бы вызвать `AfxGetApp` доступ к текущему объекту приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]

[!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок**: afxwin.h

## <a name="afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl

Извлекает текущий флаг управления пользователем.

```
BOOL AFXAPI AfxOleGetUserCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь контролирует приложение; в противном случае 0.

### <a name="remarks"></a>Remarks

Пользователь контролирует приложение, когда пользователь явно открыл или создал новый документ. Пользователь также контролирует, если приложение не было запущено DLL системы OLE - другими словами, если пользователь запустил приложение с системной оболочкой.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl

Устанавливает или очищает флаг управления пользователем, который объясняется в ссылке для `AfxOleGetUserCtrl`.

```cpp
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl);
```

### <a name="parameters"></a>Параметры

*bUserCtrl*<br/>
Определяет, должен ли быть установлен или очищен флаг управления пользователем.

### <a name="remarks"></a>Remarks

Платформа вызывает эту функцию, когда пользователь создает или загружает документ, но не когда документ загружается или создается с помощью косвенного действия, такого как загрузка встроенного объекта из контейнерного приложения.

Вызовите эту функцию, если другие действия в приложении должны поставить пользователя под контроль приложения.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp

Приравливывает глобальное количество активных объектов в приложении.

```cpp
void AFXAPI AfxOleLockApp();
```

### <a name="remarks"></a>Remarks

В фреймворке ведется подсчет количества объектов, активных в приложении. И `AfxOleLockApp` `AfxOleUnlockApp` функции, соответственно, приращения и decrement этого счета.

Когда пользователь пытается закрыть приложение с активными объектами - приложением, для которого количество активных объектов не является нулевым, - фреймворк скрывает приложение от представления пользователя, а не полностью закрывает его. Функция `AfxOleCanExitApp` указывает, может ли приложение завершить работу.

Вызов `AfxOleLockApp` с любого объекта, который предоставляет интерфейсы OLE, если это было бы нежелательно для этого объекта, который будет уничтожен при использовании клиентского приложения. Также `AfxOleUnlockApp` позвоните в деструктор любого объекта, который вызывает `AfxOleLockApp` в конструкторе. По умолчанию `COleDocument` (и производные классы) автоматически блокируют и разблокируют приложение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp

Декретирует количество активных объектов в приложении.

```cpp
void AFXAPI AfxOleUnlockApp();
```

### <a name="remarks"></a>Remarks

Дополнительная информация. `AfxOleLockApp`

Когда количество активных объектов `AfxOleOnReleaseAllObjects` достигает нуля, вызывается.

### <a name="example"></a>Пример

Смотрите пример [AfxOleLockApp](#afxolelockapp).

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxolelockcontrol"></a>AfxOleLockControl

Блокирует фабрику классов указанного элемента управления таким образом, чтобы динамически созданные данные, связанные с элементом управления, оставались в памяти.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
Уникальный идентификатор класса управления.

*lpszProgID*<br/>
Уникальный идентификатор программы управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если класс завод управления был успешно заблокирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Это может значительно ускорить отображение элементов управления. Например, как только вы создаете элемент управления в `AfxOleLockControl`диалоговом поле и блокируете элемент управления, вам не нужно создавать и убивать его снова каждый раз, когда диалог отображается или разрушается. Если пользователь открывает и закрывает диалоговую будку повторно, блокировка элементов управления может значительно повысить производительность. Когда вы будете готовы уничтожить `AfxOleUnlockControl`элемент управления, позвоните.

### <a name="example"></a>Пример

```cpp
// Starts and locks control's (Microsoft Calendar) class factory.
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass

Эта функция позволяет зарегистрировать сервер в реестре системы OLE.

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

*clsid*<br/>
Ссылка на идентификатор класса OLE сервера.

*lpszClassName*<br/>
Указатель на строку, содержащую классовое имя объектов сервера.

*lpszShortTypeName*<br/>
Указатель на строку, содержащую короткое имя типа объекта сервера, например "График".

*lpszLongTypeName*<br/>
Указатель на строку, содержащую длинное имя типа объекта сервера, например "Microsoft Excel 5.0 Chart".

*nAppType*<br/>
Значение, взятое из OLE_APPTYPE перечисления, с указанием типа приложения OLE. Возможны следующие значения:

- OAT_INPLACE_SERVER Сервер имеет полный пользовательский интерфейс сервера.

- OAT_SERVER Server поддерживает только встраивание.

- OAT_CONTAINER контейнер поддерживает ссылки на встраивания.

- OAT_DISPATCH_OBJECT-способный `IDispatch`объект.

*rglpszRegister*<br/>
Массив указателей на строки, представляющие ключи и значения, которые будут добавлены в реестр системы OLE, если не найдено существующих значений для ключей.

*rglpszOverwrite*<br/>
Массив указателей на строки, представляющие ключи и значения, которые будут добавлены в реестр системы OLE, если реестр содержит существующие значения для данных ключей.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если класс сервера успешно зарегистрирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Большинство приложений `COleTemplateServer::Register` могут использоваться для регистрации типов документов приложения. Если формат системного реестра приложения не соответствует обычному шаблону, можно использовать `AfxOleRegisterServerClass` для большего контроля.

Реестр состоит из набора ключей и значений. Аргументы *rglpszRegister* и *rglpszOverwrite* представляют собой массивы указателей на строки, каждый **NULL** из которых `'\0'`состоит из ключа и значения, разделенного персонажем NULL (). Каждая из этих строк может иметь сменные параметры, места которых отмечены последовательностями *символов %1* до *%5*.

Символы заполняются следующим образом:

|Символ|Значение|
|------------|-----------|
|%1|Идентификатор класса, отформатированный как строка|
|%2|Имя класса|
|%3|Путь к исполняемому файлу|
|%4|Имя короткого типа|
|%5|Длинное имя типа|

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu

Реализует пользовательский интерфейс для команды *typename* Object.

```cpp
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
Указатель на клиент ole пункта.

*pMenu*<br/>
Указатель на объект меню, который будет обновлен.

*iMenuItem*<br/>
Индекс элемента меню, который будет обновлен.

*nIDVerbMin*<br/>
Идентификатор команды, соответствующий основному глаголу.

*nIDVerbMax*<br/>
Идентификатор команды, соответствующий последнему глаголу.

*nIDПреобразование*<br/>
Идентификатор для элемента меню «Преобразование».

### <a name="remarks"></a>Remarks

Если сервер распознает только основной глагол, элемент меню становится «объектом *глагов типа»,* а команда *nIDVerbMin* отправляется, когда пользователь выбирает команду. Если сервер распознает несколько глаголов, то элемент меню становится «объектом *типа»,* и submenu, перечисляющий все глаголы, появляется, когда пользователь выбирает команду. Когда пользователь выбирает глагол из подменю, *nIDVerbMin* отправляется, если выбран первый глагол, *nIDVerbMin* No 1 отправляется, если выбран второй глагол, и так далее. Реализация `COleDocument` по умолчанию автоматически обрабатывает эту функцию.

Вы должны иметь следующее заявление в скрипте ресурса приложения вашего клиента (. RC) файл:

**#include \<>afxolecl.rc**

### <a name="requirements"></a>Требования

**Заголовок**: afxole.h

## <a name="afxoleunlockcontrol"></a><a name="afxoleunlockcontrol"></a>AfxOleUnlockControl

Открывает фабрику класса указанного элемента управления.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
Уникальный идентификатор класса управления.

*lpszProgID*<br/>
Уникальный идентификатор программы управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если класс завод управления был успешно разблокирован; в противном случае 0.

### <a name="remarks"></a>Remarks

Элемент управления заблокирован `AfxOleLockControl`с помощью, так что динамически созданные данные, связанные с элементом управления остается в памяти. Это может значительно ускорить отображение элемента управления, поскольку элемент управления не должен создаваться и разрушаться каждый раз, когда он отображается. Когда вы будете готовы уничтожить `AfxOleUnlockControl`элемент управления, позвоните.

### <a name="example"></a>Пример

```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
