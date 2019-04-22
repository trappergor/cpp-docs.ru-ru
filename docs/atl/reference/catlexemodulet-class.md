---
title: Класс CAtlExeModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: 87e526a10c9bcd6a52f4544c50344c5145cfa732
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769554"
---
# <a name="catlexemodulet-class"></a>Класс CAtlExeModuleT

Этот класс представляет модуль для приложения.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `CAtlExeModuleT`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Конструктор.|
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAtlExeModuleT::InitializeCom](#initializecom)|Инициализирующий COM.|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Этот метод вызывается сразу после выхода из цикла обработки сообщений.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается непосредственно перед ввода цикл обработки сообщений.|
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса.|
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса.|
|[CAtlExeModuleT::Run](#run)|Этот метод выполняет код в модуле exe-файла для инициализации, запустить цикл обработки сообщений и очистки.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Этот метод выполняется цикл обработки сообщений.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Отменяет инициализацию COM.|
|[CAtlExeModuleT::Unlock](#unlock)|Уменьшает счетчик блокировки модуля.|
|[CAtlExeModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска файла EXE.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Флаг, указывающий, что должно быть задержка завершения работы модуля.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Приостановка значение, используемое для убедитесь, что все объекты освобождаются перед завершением работы.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Значение времени ожидания, чтобы задержать выгрузки модуля.|

## <a name="remarks"></a>Примечания

`CAtlExeModuleT` Представляет модуль для приложения (EXE) и содержит код, который поддерживает создание exe-файла, обработки командной строки, регистрация класса объектов, запускает цикл сообщений и очистки при выходе.

Этот класс предназначен для повышения производительности, когда COM-объекты в EXE-сервер постоянно создаются и удаляются. После выхода последнего объекта COM, EXE-файла ожидает в течение времени, определенного [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) данные-член. Если не выполняет никаких действий в течение этого периода (то есть объекты COM не создаются), инициируется процесс завершения работы.

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) данные-член — это флаг, используемый для определения того, если exe-файла следует использовать механизм, определенный выше. Если он имеет значение false, модуль прекращается немедленно.

Дополнительные сведения о модулях в ATL, см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="catlexemodulet"></a>  CAtlExeModuleT::CAtlExeModuleT

Конструктор.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Примечания

Если не удалось инициализировать модуль exe-файла, без дополнительной обработки немедленно вернет WinMain.

##  <a name="dtor"></a>  CAtlExeModuleT:: ~ CAtlExeModuleT

Деструктор

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="initializecom"></a>  CAtlExeModuleT::InitializeCom

Инициализирующий COM.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод вызывается из конструктора и можно переопределить, чтобы инициализировать COM образом отличается от реализации по умолчанию. Реализация по умолчанию либо вызывает `CoInitializeEx(NULL, COINIT_MULTITHREADED)` или `CoInitialize(NULL)` в зависимости от конфигурации проекта.

Переопределение этого метода обычно требуется переопределение [CAtlExeModuleT::UninitializeCom](#uninitializecom).

##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown

Флаг, указывающий, что должно быть задержка завершения работы модуля.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Примечания

См. в разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) подробные сведения.

##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause

Приостановка значение, используемое для убедитесь, что все объекты прошли перед завершением работы.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Примечания

Изменить это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) задать количество миллисекунд, используемым в качестве значения паузы для завершения работы сервера. Значение по умолчанию — 1000 миллисекунд.

##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut

Значение времени ожидания, чтобы задержать выгрузки модуля.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Примечания

Изменить это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) определить количество миллисекунд, используемым в качестве значения времени ожидания для завершения работы сервера. Значение по умолчанию — 5000 миллисекунд. См. в разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) для получения дополнительных сведений.

##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine

Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*lpCmdLine*<br/>
Командной строки, передаваемые от приложения.

*pnRetCode*<br/>
Значение HRESULT, соответствующее регистрации (если она была выполнена).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если приложения должны продолжать работу, в противном случае — значение false.

### <a name="remarks"></a>Примечания

Этот метод вызывается из [CAtlExeModuleT::WinMain](#winmain) и может быть переопределен для обработки параметров командной строки. Реализация по умолчанию проверяет наличие **/regserver** и **параметром/Register** аргументы командной строки и выполняет регистрации или отмены регистрации.

##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop

Этот метод вызывается сразу после выхода из цикла обработки сообщений.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Переопределите этот метод для выполнения очистки пользовательского приложения. По умолчанию реализация вызывает [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).

##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop

Этот метод вызывается непосредственно перед ввода цикл обработки сообщений.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Значения, переданного как *nShowCmd* параметр в WinMain.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы добавить пользовательский код инициализации для приложения. Реализация по умолчанию регистрирует объекты класса.

##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects

Регистрирует объект класса с OLE, поэтому другие приложения могли подключиться к нему.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Параметры

*dwClsContext*<br/>
Определяет контекст, в котором будет выполняться объект класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER.

*dwFlags*<br/>
Определяет типы подключения к объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха, S_FALSE, если нет классов, чтобы зарегистрировать или ошибку HRESULT в случае сбоя.

##  <a name="revokeclassobjects"></a>  CAtlExeModuleT::RevokeClassObjects

Удаляет объект класса.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK в случае успеха, S_FALSE, если нет классов, чтобы зарегистрировать или ошибку HRESULT в случае сбоя.

##  <a name="run"></a>  CAtlExeModuleT::Run

Этот метод выполняет код в модуле exe-файла для инициализации, запустить цикл обработки сообщений и очистки.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может принимать одно из значений, рассматриваемые в [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) раздел. По умолчанию SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод может быть переопределен. Однако на практике это лучше для переопределения [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), или [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Вместо этого.

##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop

Этот метод выполняется цикл обработки сообщений.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Примечания

Этот метод может быть переопределен для изменения поведения цикла обработки сообщений.

##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom

Отменяет инициализацию COM.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод просто вызывает [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize) и вызывается из деструктора. Переопределите этот метод, если переопределить [CAtlExeModuleT::InitializeCom](#initializecom).

##  <a name="unlock"></a>  CAtlExeModuleT::Unlock

Уменьшает счетчик блокировки модуля.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, которое может быть полезно для диагностики или тестирования.

##  <a name="winmain"></a>  CAtlExeModuleT::WinMain

Этот метод реализует код, необходимый для запуска файла EXE.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может принимать одно из значений, рассматриваемые в [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) раздел.

### <a name="return-value"></a>Возвращаемое значение

Возвращает возвращаемое значение исполняемый файл.

### <a name="remarks"></a>Примечания

Этот метод может быть переопределен. Если переопределение [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), или [CAtlExeModuleT::RunMessageLoop](#runmessageloop) не обеспечивают необходимую гибкость , можно переопределить `WinMain` функцию с помощью этого метода.

## <a name="see-also"></a>См. также

[Образец ATLDuck](../../overview/visual-cpp-samples.md)<br/>
[Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
