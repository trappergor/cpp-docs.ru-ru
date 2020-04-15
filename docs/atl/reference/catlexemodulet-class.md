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
ms.openlocfilehash: a20a02a467d74a89e3cda176a6a15961be4ffd61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318987"
---
# <a name="catlexemodulet-class"></a>Класс CAtlExeModuleT

Этот класс представляет собой модуль для приложения.

## <a name="syntax"></a>Синтаксис

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс происходит `CAtlExeModuleT`от .

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Конструктор.|
|[CAtlExeModuleT::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT::InitializeCom](#initializecom)|Инициализирует COM.|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Сравнивает командную строку и при необходимости выполняет регистрацию.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Этот метод вызывается сразу после выхода цикла сообщения.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается непосредственно перед входом в цикл сообщения.|
|[CAtlExeModuleT:RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса.|
|[CAtlExeModuleT:RevokeClassObjects](#revokeclassobjects)|Отменяет объект класса.|
|[CAtlExeModuleT::Run](#run)|Этот метод выполняет код в модуле EXE для инициализации, запуска цикла сообщений и очистки.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Этот метод выполняет цикл сообщения.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Не инициирует COM.|
|[CAtlExeModuleT:Разблокировка](#unlock)|Утилищает количество блокировки модуля.|
|[CAtlExeModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска EXE.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Флаг, указывающий на задержку выключения модуля.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Значение паузы, используемое для обеспечения того, чтобы все объекты были освобождены до завершения работы.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Значение тайм-аута, используемое для задержки разгрузки модуля.|

## <a name="remarks"></a>Remarks

`CAtlExeModuleT`представляет модуль для приложения (EXE) и содержит код, поддерживающий создание EXE, обработку командной строки, регистрацию объектов класса, запуск цикла сообщений и очистку на выходе.

Этот класс предназначен для повышения производительности при постоянном создании и уничтожении объектов COM на сервере EXE. После выпуска последнего объекта COM EXE ждет продолжительность, указанная [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) данных. Если в течение этого периода нет активности (т.е. не создаются объекты COM), инициируется процесс завершения работы.

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) данных является флагом, используемым для определения того, должен ли EXE использовать механизм, определенный выше. Если он установлен на ложный, то модуль будет немедленно прекращено.

Для получения дополнительной информации о модулях в ATL, [см.](../../atl/atl-module-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT

Конструктор.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Remarks

Если модуль EXE не может быть инициализирован, WinMain немедленно вернется без дальнейшей обработки.

## <a name="catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT::

Деструктор

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

## <a name="catlexemoduletinitializecom"></a><a name="initializecom"></a>CAtlExeModuleT::InitializeCom

Инициализирует COM.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Этот метод вызывается от конструктора и может быть переопределен, чтобы инициализировать COM таким образом, чтобы отличаться от реализации по умолчанию. Реализация по умолчанию вызывает `CoInitializeEx(NULL, COINIT_MULTITHREADED)` или `CoInitialize(NULL)` зависит от конфигурации проекта.

Преодоление этого метода обычно требует переопределения [CAtlExeModuleT::Un initializeCom](#uninitializecom).

## <a name="catlexemoduletm_bdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown

Флаг, указывающий на задержку выключения модуля.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>Remarks

Подробнее о ней можно ознакомиться с [обзором CAtlExeModuleT.](../../atl/reference/catlexemodulet-class.md)

## <a name="catlexemoduletm_dwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause

Значение паузы, используемое для обеспечения того, чтобы все объекты исчезли до завершения работы.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>Remarks

Измените это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) для установки количества миллисекунд, используемых в качестве значения паузы для выключения сервера. Значение по умолчанию составляет 1000 миллисекунд.

## <a name="catlexemoduletm_dwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut

Значение тайм-аута, используемое для задержки разгрузки модуля.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>Remarks

Измените это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) для определения количества миллисекунд, используемых в качестве значения тайм-аута для выключения сервера. Значение по умолчанию — 5000 миллисекунд. Более подробную информацию можно узнать из [обзора CAtlExeModuleT.](../../atl/reference/catlexemodulet-class.md)

## <a name="catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine

Сравнивает командную строку и при необходимости выполняет регистрацию.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Параметры

*lpCmdLine*<br/>
Командная строка перешла к приложению.

*pnRetCode*<br/>
HRESULT, соответствующий регистрации (если она состоялась).

### <a name="return-value"></a>Возвращаемое значение

Верните истинное, если приложение должно продолжать работать, в противном случае ложно.

### <a name="remarks"></a>Remarks

Этот метод называется от [CAtlExeModuleT::WinMain](#winmain) и может быть переопределен для обработки коммутаторов командной строки. Реализация по умолчанию проверяет **аргументы командной** строки /RegServer и **/UnRegServer** и выполняет регистрацию или нерегистрацию.

## <a name="catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop

Этот метод вызывается сразу после выхода цикла сообщения.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Переопределить этот метод для выполнения пользовательского очистки приложений. Реализация по умолчанию вызывает [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).

## <a name="catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop

Этот метод вызывается непосредственно перед входом в цикл сообщения.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Значение прошло как параметр *nShowCmd* в WinMain.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Переопределить этот метод, чтобы добавить пользовательский код инициализации для приложения. Реализация по умолчанию регистрирует объекты класса.

## <a name="catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT:RegisterClassObjects

Регистрирует объект класса с помощью OLE, чтобы другие приложения могли подключиться к нему.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Параметры

*dwClsКонтекст*<br/>
Определяет контекст, в котором должен быть запущен объект класса. Возможные значения : CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER.

*dwFlags*<br/>
Определяет типы соединения с объектом класса. Возможные значения — REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE.

### <a name="return-value"></a>Возвращаемое значение

Возвраты S_OK на успех, S_FALSE, если не было классов для регистрации, или ошибка HRESULT при сбое.

## <a name="catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>CAtlExeModuleT:RevokeClassObjects

Удаляет объект класса.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвраты S_OK на успех, S_FALSE, если не было классов для регистрации, или ошибка HRESULT при сбое.

## <a name="catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT::Run

Этот метод выполняет код в модуле EXE для инициализации, запуска цикла сообщений и очистки.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может быть одним из значений, обсуждаемых в разделе [WinMain.](/windows/win32/api/winbase/nf-winbase-winmain) По умолчанию SW_HIDE.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Этот метод можно переопределить. Тем не менее, на практике лучше переопределить [CAtlExeModuleT: :PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), или [CAtlExeModuleT: :PostMessageLoop](#postmessageloop) вместо.

## <a name="catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop

Этот метод выполняет цикл сообщения.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>Remarks

Этот метод может быть отменен, чтобы изменить поведение цикла сообщений.

## <a name="catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom

Не инициирует COM.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>Remarks

По умолчанию этот метод просто вызывает [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize) и вызывается из деструктора. Переопределить этот метод, если вы переопределить [CAtlExeModuleT::InitializeCom](#initializecom).

## <a name="catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT:Разблокировка

Утилищает количество блокировки модуля.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, которое может быть полезно для диагностики или тестирования.

## <a name="catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT::WinMain

Этот метод реализует код, необходимый для запуска EXE.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Параметры

*nShowCmd*<br/>
Определяет, как будет отображаться окно. Этот параметр может быть одним из значений, обсуждаемых в разделе [WinMain.](/windows/win32/api/winbase/nf-winbase-winmain)

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение возврата исполнителя.

### <a name="remarks"></a>Remarks

Этот метод можно переопределить. Если переопределение [CAtlExeModuleT: :PreMessageLoop,](#premessageloop) [CAtlExeModuleT: :PostMessageLoop](#postmessageloop), или [CAtlExeModuleT::RunMessageLoop](#runmessageloop) не обеспечивает достаточной `WinMain` гибкости, можно переопределить функцию с помощью этого метода.

## <a name="see-also"></a>См. также раздел

[Образец ATLDuck](../../overview/visual-cpp-samples.md)<br/>
[Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
