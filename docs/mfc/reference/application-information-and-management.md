---
title: Сведения о приложении и управление им
description: Ссылка на функции и управления приложениями и управление мфизионными функциями microsoft Foundation Class Library (MFC).
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: fc0b4b09f6c48da68bebe4a2825f49bcf6ab7e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372502"
---
# <a name="application-information-and-management"></a>Сведения о приложении и управление им

Когда вы пишете приложение, вы создаете один объект, полученный [от CWinApp.](../../mfc/reference/cwinapp-class.md) Иногда вы можете получить информацию об этом `CWinApp`объекте из-за пределов объекта, полученного. Или вам может понадобиться доступ к другим глобальным объектам "менеджер".

Библиотека класса Фонда Майкрософт предоставляет следующие глобальные функции, которые помогут вам выполнить следующие задачи:

## <a name="application-information-and-management-functions"></a>Функции по информации и управлению приложениями

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Создает новый поток.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Указатель на [глобальный менеджер меню контекста.](ccontextmenumanager-class.md)|
|[AfxEndThread](#afxendthread)|Прекращает текущий поток.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Ходит по цепочке ресурсов и находит определенный ресурс по идентификатору ресурсов и типу ресурсов. |
|[AfxFreeLibrary](#afxfreelibrary)|Декретирует количество ссылок на загруженный модуль библиотеки динамической связи (DLL). Когда количество ссылок достигает нуля, модуль не отображается.|
|[AfxGetApp](#afxgetapp)|Возвращает указатель на один `CWinApp` объект приложения.|
|[AfxGetAppName](#afxgetappname)|Возвращает строку, содержащую имя приложения.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Возвращает HINSTANCE, представляющий этот экземпляр приложения.|
|[AfxGetMainWnd](#afxgetmainwnd)|Возвращает указатель в текущее "основное" окно приложения, не являющегося OLE, или окно кадрового окна серверного приложения.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Используйте эту функцию, чтобы определить, перенаправляет ли приложение доступ к узле **HKEY_CURRENT_USER** **(HKCU)**.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Возвращает HINSTANCE в источник ресурсов по умолчанию приложения. Используйте для прямого доступа к ресурсам приложения.|
|[AfxGetThread](#afxgetthread)|Извлекает указатель на текущий объект [CWinThread.](../../mfc/reference/cwinthread-class.md)|
|[AfxInitRichEdit](#afxinitrichedit)|Инициализирует версию 1.0 богатый элемент управления реитритом для приложения.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Инициализирует версию 2.0 и позже богатый элемент управления редектовированным элементом для приложения.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Определяет, является ли заданное окно расширенным объектом фрейма.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Определяет, является ли данное окно объектом панели инструментов.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Указатель на глобальный [менеджер клавиатуры](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Карты dLL модуль и возвращает ручку, которая может быть использована для получения адреса функции DLL.|
|[AfxLoadLibraryEx](#afxloadlibraryex)|Карты dLL модуль с использованием указанных параметров, и возвращает ручку, которая может быть использована для получения адреса функции DLL.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Указатель на глобальный [менеджер меню отрыва.](cmenutearoffmanager-class.md)|
|[AfxMouse](#afxmousemanager)|Указатель на глобального [менеджера мыши.](cmousemanager-class.md)|
|[AfxRegisterClass](#afxregisterclass)|Регистрирует класс окон в DLL, используюемом MFC.|
|[AfxRegisterWndClass](#afxregisterwndclass)|Регистрирует класс окна Windows в дополнение к тем, которые автоматически регистрируются MFC.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Устанавливает, перенаправляет ли приложение доступ **HKEY_CURRENT_USER** к HKEY_CURRENT_USER **(HKCU**) узла.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Устанавливает ручку HINSTANCE, где загружаются ресурсы приложения по умолчанию.|
|[AfxShellManager](#afxshellmanager)|Указатель на глобальный [менеджер оболочки.](cshellmanager-class.md) |
|[AfxSocketInit](#afxsocketinit)|Вызывается `CWinApp::InitInstance` в переопределение для инициализации Windows розетки.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Указатель на глобальный [менеджер пользовательских инструментов.](cusertoolsmanager-class.md)|
|[AfxWinInit](#afxwininit)|Вызывается mFC-функция, как `WinMain` часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации приложения на основе ГРАФИЧЕСКОго интерфейса, для инициализации MFC. Должны быть вызваны непосредственно для консольных приложений, которые используют MFC.|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a>Afxbeginthread

Вызовите эту функцию, чтобы создать новый поток.

```cpp
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Параметры

*pfnThreadProc*\
Указывает на функцию управления для рабочего потока. Указатель не может быть NULL. Эта функция должна быть объявлена следующим образом:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*\
В RUNTIME_CLASS объекта, полученного из [CWinThread](../../mfc/reference/cwinthread-class.md).

*pParam*\
Параметр для передачи в функцию управления.

*nПриоритет*\
Приоритет, который должен установить для потока. Полный список и описание доступных приоритетов можно найти в [SDK Windows.](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)

*nStackРазмер*\
Упоняет размер байтов стека для нового потока. Если 0, размер стека по умолчанию по умолчанию к тому же размеру стека, как создание потока.

*dwCreateFlags*\
Определяет дополнительный флаг, который контролирует создание потока. Этот флаг может содержать одно из двух значений:

- CREATE_SUSPENDED Начать поток с подсчетом приопром 1. Используйте CREATE_SUSPENDED, если вы хотите инициализировать любые данные члена `CWinThread` объекта, такие как [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) или любые члены вашего производного класса, до начала работы потока. Как только ваша инициализация будет завершена, используйте [CWinThread::ResumeThread,](../../mfc/reference/cwinthread-class.md#resumethread) чтобы запустить работу потока. Поток не будет выполняться до тех пор, пока `CWinThread::ResumeThread` не будет вызван.

- **0** Запустите поток сразу после создания.

*lpSecurityAttrs*\
Указывает на [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) структуру, которая определяет атрибуты безопасности для потока. Если NULL, используются те же атрибуты безопасности, что и поток создания. Для получения дополнительной информации об этой структуре см.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный объект потока или NULL, если происходит сбой.

### <a name="remarks"></a>Remarks

Первая форма `AfxBeginThread` создает рабочую нить. Вторая форма создает поток, который может служить в качестве потока пользовательского интерфейса или рабочего потока.

`AfxBeginThread`создает новый `CWinThread` объект, вызывает функцию [CreateThread,](../../mfc/reference/cwinthread-class.md#createthread) чтобы начать выполнение потока, и возвращает указатель в поток. Проверки проводятся на протяжении всей процедуры, чтобы убедиться, что все объекты расположены должным образом, если какая-либо часть создания не удастся. Чтобы закончить поток, вызов [Иквы](#afxendthread) Из потока или вернуться из функции управления рабочего потока.

Мультипоточность должна быть включена приложением; в противном случае эта функция не сработает. Для получения дополнительной информации о включении многопоточности см./ [MD, /MT, /LD (Использовать библиотеку времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md).

Для получения `AfxBeginThread`дополнительной информации о , см. статьи [Многопоточность: Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [многопоточность: Создание пользователь-интерфейс темы](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Пример

Смотрите пример [для CSocket::Прикрепите](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a>AfxContextMenuManager

Указатель на [глобальный менеджер меню контекста.](ccontextmenumanager-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxcontextmenumanager.h

## <a name="afxendthread"></a><a name="afxendthread"></a>AfxEndThread

Вызовите эту функцию, чтобы завершить в настоящее время выполняется поток.

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Параметры

*nЭкзиткоид*\
Определяет код выхода потока.

*bУдалить*\
Удаляет объект потока из памяти.

### <a name="remarks"></a>Remarks

Необходимо вызываться из потока, который должен быть завершен.

Для получения `AfxEndThread`дополнительной информации о , см. [Multithreading: Terminating Threads](../../parallel/multithreading-terminating-threads.md)

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a>AfxFindResourceHandle

Используйте `AfxFindResourceHandle` для ходьбы по цепочке ресурсов и найдите определенный ресурс по идентификатору ресурсов и типу ресурсов.

### <a name="syntax"></a>Синтаксис

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Параметры

*lpszName*\
Указатель на строку, содержащую идентификатор ресурса.
*lpszType*\
Указатель на тип ресурса. Список типов ресурсов [можно](/windows/win32/api/winbase/nf-winbase-findresourcea) найти в SDK Windows.

### <a name="return-value"></a>Возвращаемое значение

Ручка к модулю, содержащей ресурс.

### <a name="remarks"></a>Remarks

`AfxFindResourceHandle`находит определенный ресурс и возвращает ручку в модуль, содержащий ресурс. Ресурс может быть в любом расширенном DLL MFC, который загружается. `AfxFindResourceHandle`говорит вам, какой из них имеет ресурс.

Модульы ищутся в этом порядке:

1. Основной модуль, если это расширение MFC DLL.

1. Несистемные модули.

1. Языковые модули.

1. Основной модуль, если это система DLL.

1. Системные модули.

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a>AfxFreeLibrary

И `AfxFreeLibrary` `AfxLoadLibrary` для каждого загруженного библиотечного модуля и вести подсчет ссылок.

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Параметры

*hInstLib*\
Ручка загруженного библиотечного модуля. [AfxLoadLibrary](#afxloadlibrary) возвращает эту ручку.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если функция удавляется; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

`AfxFreeLibrary`декретирует количество ссылок на загруженную библиотеку динамической связи (DLL). Когда количество ссылок достигает нуля, модуль не отображается из адресного пространства процесса вызова, и ручка больше не действительна. Это количество ссылок приравняно каждый раз, когда `AfxLoadLibrary` вызывается.

Перед тем, как отсоединить модуль библиотеки, система позволяет DLL отделиться от процессов, использующих его. Это дает DLL возможность очистки ресурсов, выделяемых на текущий процесс. После возвращения функции начальной точки модуль библиотеки удаляется из адресного пространства текущего процесса.

Используется `AfxLoadLibrary` для картирования модуля DLL.

Обязательно используйте `AfxFreeLibrary` `AfxLoadLibrary` и (вместо функций `FreeLibrary` Win32 и) `LoadLibrary`если ваше приложение использует несколько потоков. Использование `AfxLoadLibrary` `AfxFreeLibrary` и обеспечение того, чтобы код запуска и выключения, выполняемый при загрузке и выгрузке расширения MFC, не поручивал глобальное состояние MFC.

### <a name="example"></a>Пример

Смотрите пример [Для AfxLoadLibrary](#afxloadlibrary).

### <a name="requirements"></a>Требования

  **Заголовок** afxdll_.h

## <a name="afxgetapp"></a><a name="afxgetapp"></a>AfxGetApp

Указатель, возвращенный этой функцией, может использоваться для доступа к информации приложения, такой как основной код отправки сообщений или верхнее окно.

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на единый `CWinApp` объект для приложения.

### <a name="remarks"></a>Remarks

Если этот метод возвращает NULL, это может означать, что основное окно приложения еще не полностью инициализировано. Это также может указывать на проблему.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a>AfxGetAppName

Возвращается строка может быть использована для диагностических сообщений или в качестве корня для временных имен строк.

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Возвращаемое значение

Строка с нулевым завершением, содержащая имя приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGetInstanceHandle

Эта функция позволяет получить экземпляр ручки текущего приложения.

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

В настоящее время экземпляр приложения. Если вызов из DLL, связанный с версией UsRDLL MFC, возвращается HINSTANCE в DLL.

### <a name="remarks"></a>Remarks

`AfxGetInstanceHandle`всегда возвращает HINSTANCE вашего исполняемого файла (. EXE), если он не называется из Внутри DLL, связанных с версией USRDLL MFC. В этом случае он возвращает HINSTANCE в DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a>AfxGetMainWnd

Если ваше приложение является сервером OLE, позвоните по этой функции, чтобы получить указатель на активное основное окно приложения. Используйте этот результат вместо того, чтобы напрямую ссылаться на [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) член омнитель объекта приложения.

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на объект окна кадра, содержащий активный документ на месте, если у сервера есть объект, активный внутри активного контейнера.

Если в контейнере нет объекта, работаемого в контейнере, или ваше приложение не является сервером OLE, эта функция возвращает *m_pMainWnd* объекта приложения.

Если `AfxGetMainWnd` вызов из основного потока приложения возвращает основное окно приложения в соответствии с вышеуказанными правилами. Если функция вызывается из вторичного потока в приложении, функция возвращает основное окно, связанное с потоком, сделавшую вызовом.

### <a name="remarks"></a>Remarks

Если ваше приложение не является сервером OLE, то вызов этой функции эквивалентен непосредственно муляжам *m_pMainWnd* члену объекта приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPerUserРегистрация

Используйте эту функцию, чтобы определить, перенаправляет ли приложение доступ к узле **HKEY_CURRENT_USER** **(HKCU)**.

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает, что информация о реестре направляется в узлы HKCU. FALSE указывает, что приложение записывает информацию о реестре в узлы по умолчанию. Узла по умолчанию **HKEY_CLASSES_ROOT** **(HKCR).**

### <a name="remarks"></a>Remarks

Если вы включите перенаправление реестра, платформа перенаправляет доступ от **HKCR** на **HKEY_CURRENT_USER «Software»Classes**. Перенаправлением влияют только системы MFC и ATL.

Чтобы изменить, перенаправляет ли приложение доступ к реестру, используйте [AfxSetPerUserRegistration.](#afxsetperuserregistration)

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGetResourceHandle

Используйте ручку HINSTANCE, возвращенную этой функцией, для прямого доступа к `FindResource`ресурсам приложения, например, при вызовах к функции Windows.

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка HINSTANCE, где загружаются ресурсы приложения по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a>AfxGetThread

Вызовите эту функцию, чтобы получить указатель на объект [CWinThread,](../../mfc/reference/cwinthread-class.md) представляющий в настоящее время исполняемый поток.

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на в настоящее время выполняет сяочие поток; в противном случае NULL.

### <a name="remarks"></a>Remarks

Должен быть вызван изнутри потока.

> [!NOTE]
> Если вы переносите проект `AfxGetThread` MFC, вызывая из версий Visual C', 4.2, 5.0 или 6.0, звоните в `AfxGetThread` [AfxGetApp,](#afxgetapp) если нить не найдена. В более поздних версиях `AfxGetThread` компилятора возвращается NULL, если поток не найден. Если требуется поток приложения, `AfxGetApp`необходимо позвонить.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a>AfxInitRichEdit

Вызовите эту функцию, чтобы инициализировать богатый элемент управления речами (версия 1.0) для приложения.

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Remarks

Эта функция предусмотрена для обратной совместимости. Новые приложения должны использовать [AfxInitRichEdit2](#afxinitrichedit2).

`AfxInitRichEdit`нагрузки RICHED32. DLL для инициализации версии 1.0 богатого управления ревертритом. Для использования версии 2.0 и 3.0 богатого управления редемик, RICHED20. DLL должен быть загружен. Он загружается, делая звонок на [AfxInitRichEdit2](#afxinitrichedit2).

Чтобы обновить богатые элементы управления элементами элемента управления в существующих приложениях Visual C', чтобы обновить версию 2.0, откройте . RC файл как текст, изменить название класса каждого богатого элемента управления редактирования с "RICHEDIT" на "RichEdit20a". Затем замените `AfxInitRichEdit` вызов `AfxInitRichEdit2`на .

Эта функция также инициализирует общую библиотеку управления, если библиотека еще не была инициализирована для процесса. Если вы используете богатый элемент управления правком непосредственно из приложения MFC, позвоните по этой функции, чтобы гарантировать, что MFC правильно инициализировал арочные сроки выполнения управления исправом. Если вы `Create` называете метод [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), вы, как правило, не нужно называть эту функцию, но в некоторых случаях это может быть необходимо.

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a>AfxInitRichEdit2

Вызовите эту функцию, чтобы инициализировать богатый элемент управления редектовированным элементом управления (версия 2.0 и более позднее) для приложения.

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Remarks

Вызовите эту функцию для загрузки RICHED20. DLL и инициализация версии 2.0 богатого управления ревертритом. Если вы `Create` называете метод [CRichEditCtrl,](../../mfc/reference/cricheditctrl-class.md) [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), вы, как правило, не нужно называть эту функцию, но в некоторых случаях это может быть необходимо.

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a>AfxisExtendedFrameClass

Определяет, является ли заданное окно расширенным объектом фрейма.

### <a name="syntax"></a>Синтаксис

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Параметры

*pWnd*\
(в) Указатель на объект, который является `CWnd`производным от .

### <a name="return-value"></a>Возвращаемое значение

TRUE, если предоставленное окно является расширенным объектом кадра; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод возвращает TRUE, если *pWnd* происходит от одного из следующих классов:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Этот метод полезен, когда требуется проверить, что параметр функции или метода является окном расширенного фрейма.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a>AfxisMFCToolBar

Определяет, является ли данное окно объектом панели инструментов.

### <a name="syntax"></a>Синтаксис

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*\
(в) Указатель на объект, который является `CWnd`производным от .

### <a name="return-value"></a>Возвращаемое значение

TRUE, если предоставленное окно является объектом панели инструментов; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод `TRUE` возвращается, если `CMFCToolBar` *pWnd* происходит от . Этот метод полезен, когда необходимо проверить, что `CMFCToolBar` параметр функции или метода является объектом.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a>AfxKeyboardManager

Указатель на глобальный [менеджер клавиатуры](ckeyboardmanager-class.md).

### <a name="syntax"></a>Синтаксис

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxkeyboardmanager.h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a>AfxLoadLibrary

Используется `AfxLoadLibrary` для картирования модуля DLL.

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Параметры

*lpszModuleName*\
Указывает на нулевую строку, содержащую название модуля (либо . DLL или . ФАЙЛ EXE). Указанное имя является файловым названием модуля.

Если строка определяет путь, но файл не существует в указанном каталоге, функция выходит из строя.

Если путь не указан и расширение имени файла опущено, расширение по умолчанию . DLL придатим. Тем не менее, строка имя файла может включать символ точки отставания (.), чтобы указать, что имя модуля не имеет расширения. Когда путь не указан, функция использует [порядок поиска для настольных приложений.](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно работает, значение возврата является ручкой модуля. При сбое значение возврата null.

### <a name="remarks"></a>Remarks

Он возвращает ручку, которая может быть использована в [GetProcAddress,](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) чтобы получить адрес функции DLL. `AfxLoadLibrary`также может использоваться для картирования других исполняемых модулей.

Каждый процесс поддерживает подсчет ссылок для каждого загруженного модуля библиотеки. Это количество ссылок приравняно каждый раз, `AfxLoadLibrary` `AfxFreeLibrary` когда вызывается и устраняется каждый раз, когда вызывается. Когда количество ссылок достигает нуля, модуль не отображается из адресного пространства процесса вызова, и ручка больше не действительна.

Не забудьте `AfxLoadLibrary` `AfxFreeLibrary` использовать и (вместо `LoadLibrary` функций `FreeLibrary`Win32 и ) если ваше приложение использует несколько потоков, и если он динамически загружает расширение MFC DLL. Использование `AfxLoadLibrary` `AfxFreeLibrary` и гарантирует, что код запуска и выключения, выполняемый при загрузке и выгрузке расширения MFC, не портит глобальное состояние MFC.

Использование `AfxLoadLibrary` в приложении требует динамической ссылки на DLL версию MFC. Файл заголовка `AfxLoadLibrary`для , Afxdll_.h, включен только в том случае, если MFC связан с приложением в качестве DLL. Это требование является дизайном, потому что вы должны ссылку на версию DLL MFC для использования или создания расширения MFC DLLs.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdll_.h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a>AfxLoadLibraryEx

Используется `AfxLoadLibraryEx` для картирования модуля DLL.

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>Параметры

*lpFileName*\
Указывает на нулевую строку, содержащую название модуля (либо . DLL или . ФАЙЛ EXE). Указанное имя является файловым названием модуля.

Если строка определяет путь, но файл не существует в указанном каталоге, функция выходит из строя.

Если путь не указан и расширение имени файла опущено, расширение по умолчанию . DLL придатим. Тем не менее, строка имя файла может включать символ точки отставания (.), чтобы указать, что имя модуля не имеет расширения. Когда путь не указан, функция использует [порядок поиска для настольных приложений.](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)

*hFile*\
Этот параметр зарезервирован для использования в будущем. Это должно быть NULL.

*Dwflags*\
Действие, необходимое при загрузке модуля. Если флаги не указаны, поведение этой `AfxLoadLibrary` функции идентично функции. Возможные значения этого параметра описаны в документации [LoadLibraryEx.](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно работает, значение возврата является ручкой модуля. При сбое значение возврата null.

### <a name="remarks"></a>Remarks

`AfxLoadLibraryEx`возвращает ручку, которая может быть использована в [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) для получения адреса функции DLL. `AfxLoadLibraryEx`также может использоваться для картирования других исполняемых модулей.

Каждый процесс поддерживает подсчет ссылок для каждого загруженного модуля библиотеки. Это количество ссылок приравняно каждый раз, `AfxLoadLibraryEx` `AfxFreeLibrary` когда вызывается и устраняется каждый раз, когда вызывается. Когда количество ссылок достигает нуля, модуль не отображается из адресного пространства процесса вызова, и ручка больше не действительна.

Не забудьте `AfxLoadLibraryEx` `AfxFreeLibrary` использовать и (вместо `LoadLibraryEx` функций `FreeLibrary`Win32 и ) если ваше приложение использует несколько потоков, и если он динамически загружает расширение MFC DLL. Использование `AfxLoadLibraryEx` `AfxFreeLibrary` и обеспечение того, чтобы код запуска и выключения, выполняемый при загрузке и выгрузке расширения MFC, не поручивал глобальное состояние MFC.

Использование `AfxLoadLibraryEx` в приложении требует динамической ссылки на DLL версию MFC. Файл заголовка `AfxLoadLibraryEx`для , Afxdll_.h, включен только в том случае, если MFC связан с приложением в качестве DLL. Это требование является дизайном, потому что вы должны ссылку на версию DLL MFC для использования или создания расширения MFC DLLs.

### <a name="requirements"></a>Требования

  **Заголовок** afxdll_.h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager

Указатель на глобальный [менеджер меню отрыва.](cmenutearoffmanager-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmenutearoffmanager.h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a>AfxMouse

Указатель на глобального [менеджера мыши.](cmousemanager-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmousemanager.h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a>AfxRegisterClass

Используйте эту функцию для регистрации классов окон в DLL, который использует MFC.

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Параметры

*lpWndClass*\
Указатель на структуру [WNDCLASS,](/windows/win32/api/winuser/ns-winuser-wndclassw) содержащую информацию о зарегистрированном классе окон. Для получения дополнительной информации об этой структуре см.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если класс успешно зарегистрирован; в противном случае FALSE.

### <a name="remarks"></a>Remarks

При использовании этой функции класс автоматически не регистрируется при выгрузке DLL.

В не-DLL сборки, `AfxRegisterClass` идентификатор определяется как `RegisterClass`макрос, что карты для функции Windows , так как классы, зарегистрированные в приложении автоматически незарегистрированы. Если вы `AfxRegisterClass` используете вместо `RegisterClass`этого, ваш код может быть использован без изменений как в приложении, так и в DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a>AfxRegisterWndClass

Позволяет зарегистрировать свои собственные классы окон.

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Параметры

*nКлассСтиль*\
Определяет стиль класса Windows или комбинацию стилей, созданных с помощью оператора bitwise-OR** (&#124;) **для класса окон. Список стилей классов можно [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) узнать в sDK Windows. Если NULL, по умолчанию устанавливаются следующим образом:

- Устанавливает стиль мыши на CS_DBLCLKS, который отправляет сообщения с двойным нажатием кнопки на процедуру окна, когда пользователь дважды щелкает мышью.

- Устанавливает стиль курсора стрелки в стандартное IDC_ARROW Windows.

- Устанавливает фоновую кисть на NULL, чтобы окно не стирало фон.

- Устанавливает значок к стандарту, размахивая флагом значок логотипwindows.

*hCursor*\
Обращайтесь к ручке ресурса курсора, который будет установлен в каждом окне, созданном из класса окон. Если вы используете значение по умолчанию **0,** вы получите стандартный курсор IDC_ARROW.

*hbrBackground*\
Обращайте ручку ресурсу кисти, которая будет установлена в каждом окне, созданном из класса окон. Если вы используете значение значение **0,** то у вас будет фоновая кисть NULL, и по умолчанию ваше окно не будет стирать фон при обработке [WM_ERASEBKGND.](/windows/win32/winmsg/wm-erasebkgnd)

*hIcon*\
Обращайтесь к ручке ресурса значка, который будет установлен в каждом окне, созданном из класса окон. Если вы используете значение по умолчанию **0,** вы получите стандартный значок логотипа Windows с развевающимся флагом.

### <a name="return-value"></a>Возвращаемое значение

Строка с нулевым завершением, содержащая имя класса. Это имя класса можно `Create` передать функции участника `CWnd` или другим классам **CWnd-** derived для создания окна. Имя генерируется библиотекой класса Microsoft Foundation.

> [!NOTE]
> Значение возврата является указателем на статический буфер. Чтобы сохранить эту строку, `CString` присвоите ее переменной.

### <a name="remarks"></a>Remarks

Библиотека класса Фонда Майкрософт автоматически регистрирует для вас несколько стандартных классов окон. Позвоните в эту функцию, если вы хотите зарегистрировать свои собственные классы окон.

Имя, зарегистрированное `AfxRegisterWndClass` для класса, зависит исключительно от параметров. Если вы `AfxRegisterWndClass` звоните несколько раз с одинаковыми параметрами, он регистрирует класс только при первом вызове. Позже `AfxRegisterWndClass` звонки с идентичными параметрами возвращают уже зарегистрированное имя класса.

Если вы `AfxRegisterWndClass` призываете к нескольким классам с идентичными параметрами с одинаковыми параметрами, вместо того, чтобы получить отдельный класс окон для каждого класса, каждый класс разделяет один и тот же класс окон. Этот общий доступ может вызвать проблемы при использовании стиля CS_CLASSDC класса. Вместо нескольких классов CS_CLASSDC окон, вы в конечном итоге только один класс CS_CLASSDC окна. Все окна СЗ, которые используют этот класс, имеют один и тот же DC. Чтобы избежать этой проблемы, позвоните [в AfxRegisterClass](#afxregisterclass) для регистрации класса.

Обратитесь к Техническому примечанию [TN001: Регистрация класса окон](../../mfc/tn001-window-class-registration.md) для получения дополнительной информации о регистрации класса окон и функции. `AfxRegisterWndClass`

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPeruserРегистрация

Устанавливает, перенаправляет ли приложение доступ **HKEY_CURRENT_USER** к HKEY_CURRENT_USER **(HKCU**) узла.

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*\
(в) TRUE указывает, что информация о реестре направляется в узлы HKCU. FALSE указывает, что приложение записывает информацию о реестре в узлы по умолчанию. Узла по умолчанию **HKEY_CLASSES_ROOT** **(HKCR).**

### <a name="remarks"></a>Remarks

До Windows Vista приложения, которые пользовались регистром, обычно использовали **HKEY_CLASSES_ROOT** узла. Однако, с Windows Vista или более поздними операционными системами, вы должны запустить приложение в повышенном режиме, чтобы написать в HKCR.

Этот метод позволяет приложению читать и записываться в реестр без работы в повышенном режиме. Он работает путем перенаправления доступа к реестру от HKCR к HKCU. Для получения дополнительной информации смотрите [страницы свойств Linker](../../build/reference/linker-property-pages.md).

Если вы включите перенаправление реестра, платформа перенаправляет доступ от HKCR на **HKEY_CURRENT_USER «Software»Classes**. Перенаправлением влияют только системы MFC и ATL.

Реализация по умолчанию получает доступ к реестру в соответствии с HKCR.

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSetResourceHandle

Используйте эту функцию для установки ручки HINSTANCE, которая определяет, где загружаются ресурсы приложения по умолчанию.

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Параметры

*hInstResource*\
Экземпляр или модуль ручкой для . Файл EXE или DLL, из которого загружаются ресурсы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a>AfxShellManager

Указатель на глобальный [менеджер оболочки.](cshellmanager-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxshellmanager.h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a>AfxSocketInit

Вызовите эту `CWinApp::InitInstance` функцию в переопределение для инициализации Windows Sockets.

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Параметры

*lpwsaData*\
Указатель на структуру [WSADATA.](/windows/win32/api/winsock2/ns-winsock2-wsadata) Если *lpwsaData* не равна NULL, то `WSADATA` адрес структуры заполняется `WSAStartup`вызовом . Эта функция также `WSACleanup` гарантирует, что требуется для вас, прежде чем приложение завершается.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Remarks

При использовании разъемов MFC во вторичных потоках в `AfxSocketInit` статично связанном приложении MFC необходимо вызвать каждый поток, который использует розетки для инициализации библиотек розетки. По умолчанию, `AfxSocketInit` называется только в основном потоке.

### <a name="requirements"></a>Требования

  **Заголовок** afxsock.h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a>AfxUserToolsManager

Указатель на глобальный [менеджер пользовательских инструментов.](cusertoolsmanager-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxusertoolsmanager.h

## <a name="afxwininit"></a><a name="afxwininit"></a>AfxWinInit

Эта функция называется функцией `WinMain` MFC, поставляемой, как часть инициализации [CWinApp](../../mfc/reference/cwinapp-class.md) приложения на основе ГРАФИЧЕСКОго интерфейса, для инициализации MFC.

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Параметры

*hInstance*\
Ручка работаемого в настоящее время модуля.

*hPrevInstance*\
Ручка к предыдущему экземпляру приложения. Для приложения на основе Win32 этот параметр всегда является **NULL.**

*lpCmdLine*\
Указывает на нулевую строку, определяющую командную строку для приложения.

*nCmdShow*\
Определяет, как будет отображаться основное окно приложения GUI.

### <a name="remarks"></a>Remarks

Для консольного приложения, которое не использует `WinMain` функцию MFC-поставленной, необходимо позвонить `AfxWinInit` непосредственно для инициализации MFC.

Если вы `AfxWinInit` называете себя, вы `CWinApp` должны объявить экземпляр класса. Для консольного приложения можно отказаться от `CWinApp` получения собственного `CWinApp` класса и вместо этого использовать экземпляр напрямую. Этот метод подходит, если вы решите оставить все функциональные возможности для вашего приложения в вашей реализации **основного**.

> [!NOTE]
> При созданиеконтекста активации для сборки MFC использует манифестресурс, предоставляемый пользовательским модулем. Контекст активации создается в `AfxWinInit`. Для получения дополнительной информации смотрите [поддержка контекстов активации в состоянии модуля MFC](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="see-also"></a>См. также раздел

[Макрос и Глобалс](mfc-macros-and-globals.md)\
[Класс CWinApp](cwinapp-class.md)\
[Класс CContextMenuManager](ccontextmenumanager-class.md)\
[Класс CWnd](cwnd-class.md)\
[Класс CFrameWndEx](cframewndex-class.md)\
[Класс CMFCToolBar](cmfctoolbar-class.md)\
[Класс CKeyboardManager](ckeyboardmanager-class.md)\
[Класс CMenuTearOffManager](cmenutearoffmanager-class.md)\
[Класс CMouseManager](cmousemanager-class.md)\
[Класс CShellManager](cshellmanager-class.md)\
[Класс CUserToolsManager](cusertoolsmanager-class.md)
