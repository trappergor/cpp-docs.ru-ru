---
title: Сведения о приложении и управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1867f044c143fc0e5fbb06705bf45b8fa729a5cc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068974"
---
# <a name="application-information-and-management"></a>Сведения о приложении и управление им

При написании приложения, вы создаете один [CWinApp](../../mfc/reference/cwinapp-class.md)-объект, производный от. В некоторых случаях требуется получить сведения об этом объекте, из за пределами `CWinApp`-объект, производный от. Или может потребоваться доступ к другим объектам глобального «диспетчер».

Библиотеки Microsoft Foundation Class предоставляет следующие глобальные функции для выполнения этих задач:

### <a name="application-information-and-management-functions"></a>Сведения о приложении и функции управления

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Создает новый поток.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Указатель на глобальную [меню диспетчера контекста](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Прерывает выполнение текущего потока.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Проверяет цепочку ресурсов и найти определенный идентификатор ресурса, ресурс и тип ресурса. |
|[AfxFreeLibrary](#afxfreelibrary)|Уменьшает счетчик ссылок модуля загруженной библиотеки динамической компоновки (DLL). Когда число ссылок достигает нуля, модуль не имеет сопоставления.|
|[AfxGetApp](#afxgetapp)|Возвращает указатель на приложение единого `CWinApp` объекта.|
|[AfxGetAppName](#afxgetappname)|Возвращает строку, содержащую имя приложения.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Возвращает HINSTANCE, представляющий этот экземпляр приложения.|
|[AfxGetMainWnd](#afxgetmainwnd)|Возвращает указатель на текущее окно «main», отличных от OLE приложения или окне фрейма на месте серверного приложения.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Эта функция используется для определения, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Возвращает HINSTANCE источник по умолчанию ресурсы приложения. Используется для прямого доступа к ресурсам приложения.|
|[AfxGetThread](#afxgetthread)|Извлекает указатель на текущий [CWinThread](../../mfc/reference/cwinthread-class.md) объекта.|
|[AfxInitRichEdit](#afxinitrichedit)|Инициализирует версии 1.0 с форматированием управления приложения.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Инициализирует версии 2.0 и более поздних версий элемент управления rich edit для приложения.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Определяет, является ли заданное окно расширенным объектом фрейма.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Определяет, является ли заданное окно объект панели инструментов.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Указатель на глобальную [manager клавиатуры](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Сопоставляет модуль DLL и возвращает дескриптор, который может использоваться для получения адреса функции DLL.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Указатель на глобальную [manager меню отделяемый](cmenutearoffmanager-class.md).|
|[AfxMouseManager](#afxmousemanager)|Указатель на глобальную [manager мыши](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|Регистрирует класс окна в библиотеку DLL, которая использует MFC.|
|[AfxRegisterWndClass](#afxregisterwndclass)|Регистрирует класс окна Windows в дополнение к зарегистрированным автоматически с MFC.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Задает дескриптор HINSTANCE, в котором загружаются по умолчанию ресурсы приложения.|
|[AfxShellManager](#afxshellmanager)|Указатель на глобальную [диспетчер оболочки](cshellmanager-class.md). |
|[AfxSocketInit](#afxsocketinit)|Вызывается `CWinApp::InitInstance` переопределение, чтобы инициализировать Windows Sockets.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Указатель на глобальную [средства диспетчера пользователей](cusertoolsmanager-class.md).|
|[AfxWinInit](#afxwininit)|Вызывается библиотека MFC предоставляет `WinMain` функции, как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации приложения на базе графического интерфейса пользователя, для инициализации MFC. Должен быть вызван непосредственно для консольных приложений, использующих MFC.|

##  <a name="afxbeginthread"></a>  AfxBeginThread

Вызывайте эту функцию для создания нового потока.

```
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

*pfnThreadProc*<br/>
Указывает на функцию управления для рабочего потока. Не может принимать значение NULL. Это функция должна быть объявлена следующим образом:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
RUNTIME_CLASS объекта, производного от [CWinThread](../../mfc/reference/cwinthread-class.md).

*pParam*<br/>
Параметр для передачи в функцию управления как показано в параметре к объявлению функции в *pfnThreadProc*.

*nPriority*<br/>
Желаемый приоритет потока. Полный список и описание имеющихся приоритетов, см. в разделе [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в пакете Windows SDK.

*nStackSize*<br/>
Указывает размер в байтах стека для нового потока. Если значение равно 0, размер стека по умолчанию тот же размер стека, что и для создания потока.

*dwCreateFlags*<br/>
Задает дополнительный флажок, контролирующий создание потока. Этот флаг может содержать одно из двух значений:

- CREATE_SUSPENDED запускает поток со счетчик приостановок одного. Используйте CREATE_SUSPENDED, если вы хотите инициализировать данные члена объекта `CWinThread` объект, например [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) или любого члена производного класса, до запуска потока. После завершения инициализации использовать [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) для запуска потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.

- **0** запустить поток сразу после создания.

*lpSecurityAttrs*<br/>
Указывает на [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) структура, задающая атрибуты безопасности для потока. Если значение равно NULL, будет использоваться те же атрибуты безопасности, что и для создания потока. Дополнительные сведения об этой структуре см. в разделе Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный объект потока, или значение NULL, если происходит сбой.

### <a name="remarks"></a>Примечания

В первой форме `AfxBeginThread` создает рабочий поток. Вторая форма создает поток, который может быть записан как UI-потоке или как рабочий поток.

`AfxBeginThread` Создает новый `CWinThread` объекта, вызывает его [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) функцию до запуска выполнения потока и возвращает указатель на поток. Проверки выполняются на протяжении процедуры, чтобы убедиться в том, что все объекты, освобожденные должным образом вызывать любую часть создания. Чтобы завершить поток, вызовите [AfxEndThread](#afxendthread) из в пределах потока или возврата из функции управления рабочего потока.

Многопоточность должна быть включена приложением; в противном случае функция завершится ошибкой. Дополнительные сведения о включении многопоточности см [/MD, / MT, /LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md) под *параметры компилятора Visual C++*.

Дополнительные сведения о `AfxBeginThread`, см. в статьях [Многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Пример

См. в примере [CSocket::Attach](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager

Указатель на глобальную [меню диспетчера контекста](ccontextmenumanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxcontextmenumanager.h

### <a name="see-also"></a>См. также

[Класс CContextMenuManager](ccontextmenumanager-class.md)

##  <a name="afxendthread"></a>  AfxEndThread

Вызывайте эту функцию на завершение текущего потока.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Параметры

*nExitCode*<br/>
Указывает код выхода потока.

*bDelete*<br/>
Удаляет объект потока из памяти.

### <a name="remarks"></a>Примечания

Должен вызываться из потока, подлежащего прерыванию.

Дополнительные сведения о `AfxEndThread`, см. в статье [Многопоточность: Завершение потоков](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Используйте `AfxFindResourceHandle` цепочку ресурсов и поиска определенного типа ресурса, ресурс идентификатор и ресурсов.

### <a name="syntax"></a>Синтаксис

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, содержащую идентификатор ресурса.
*lpszType*<br/>
Указатель на тип ресурса. Список типов ресурсов, см. в разделе [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор модуля, содержащего ресурс.

### <a name="remarks"></a>Примечания

`AfxFindResourceHandle` поиск определенного ресурса и возвращает дескриптор модуля, содержащего ресурс. Ресурс может находиться в любой библиотеки DLL, вы загрузили расширения MFC. `AfxFindResourceHandle` Указывает, какой из них имеет ресурса.

Модули производится поиск в указанном порядке:

1. Главный модуль (если это библиотеки DLL расширения MFC).

1. Несистемный модули.

1. Модули для конкретного языка.

1. Главный модуль (если она является системной библиотеки DLL).

1. Системные модули.

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

### <a name="see-also"></a>См. также

[Макросы и глобальные объекты](mfc-macros-and-globals.md)

##  <a name="afxfreelibrary"></a>  AfxFreeLibrary

Оба `AfxFreeLibrary` и `AfxLoadLibrary` поддерживает счетчик ссылок для каждого модуля в загруженной библиотеки.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Параметры

*hInstLib*<br/>
Дескриптор модуля загруженной библиотеки. [AfxLoadLibrary](#afxloadlibrary) возвращает этот дескриптор.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если функция выполнилась успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

`AfxFreeLibrary` уменьшает счетчик ссылок модуля загруженной библиотеки динамической компоновки (DLL). Когда число ссылок достигает нуля, модуль, не имеет сопоставления из адресного пространства вызывающего процесса и дескриптор недействителен. Этот счетчик ссылок увеличивается каждый раз `AfxLoadLibrary` вызывается.

До отмены сопоставления модуль библиотеки, система позволяет библиотеку DLL для отсоединения от процессов, с его помощью. Это дает возможность очистить ресурсы, выделенные от имени текущего процесса библиотеки DLL. После возвращения функции точки входа, модуль библиотеки удаляется из адресного пространства текущего процесса.

Используйте `AfxLoadLibrary` для сопоставления модуль DLL.

Обязательно используйте `AfxFreeLibrary` и `AfxLoadLibrary` (вместо функций Win32 `FreeLibrary` и `LoadLibrary`) Если приложение использует несколько потоков. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения MFC не приведет к повреждению глобального состояния MFC.

### <a name="example"></a>Пример

См. в примере [AfxLoadLibrary](#afxloadlibrary).

### <a name="requirements"></a>Требования

  **Заголовок** afxdll_.h

##  <a name="afxgetapp"></a>  AfxGetApp

Указатель, возвращенный при помощи этой функции можно использовать для доступа к информации приложения, такие как код главной диспетчеризации сообщений или самое верхнее окно.

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на один `CWinApp` объекта для приложения.

### <a name="remarks"></a>Примечания

Если этот метод возвращает значение NULL, это может означать, что главное окно приложения еще не была инициализирована полностью. Он также может указывать на проблему.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

Строка, возвращаемая этой функцией можно использовать для диагностических сообщений или в качестве корневого для имен временной строки.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Возвращаемое значение

Завершающаяся нулем строка, содержащая имя приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle

Эта функция позволяет получить дескриптор экземпляра текущего приложения.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

HINSTANCE на текущий экземпляр приложения. Если вызывается в библиотеке DLL, связанной с версией USRDLL MFC, возвращается HINSTANCE на библиотеку DLL.

### <a name="remarks"></a>Примечания

`AfxGetInstanceHandle` всегда возвращает значение HINSTANCE исполняемого файла (. (EXE), если он вызывается из библиотеки DLL соединенные USRDLL версия MFC. В этом случае он возвращает HINSTANCE на библиотеку DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd

Если приложение является OLE-сервер, вызовите эту функцию для получения указатель active главное окно приложения, а не непосредственно ссылается на [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) члена объекта приложения.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Возвращаемое значение

Если на сервере объект, являющийся на месте активный внутри контейнера и этот контейнер активна, эта функция возвращает указатель на объект окна фрейма, который содержит активный документ на месте.

Если отсутствует объект, который активен на месте в контейнере или приложение не является OLE-сервер, эта функция просто возвращает *m_pMainWnd* объекта приложения.

Если `AfxGetMainWnd` вызывается из основного потока приложения, он возвращает главное окно приложения в соответствии с правилами выше. Если функция вызывается из второго потока в приложении, функция возвращает главное окно, связанный с потоком, в которой был сделан вызов.

### <a name="remarks"></a>Примечания

Если приложение не является OLE-сервер, то вызов этой функции эквивалентно непосредственно ссылается на *m_pMainWnd* членом объекта приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

Эта функция используется для определения, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что данные реестра направляется на узел HKCU; Значение FALSE указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Примечания

Если вы включили функцию перенаправления реестра, платформа перенаправляет доступ из **HKCR** для **HKEY_CURRENT_USER\Software\Classes**. Перенаправление влияет только на платформах MFC и ATL.

Чтобы изменить, перенаправляет ли приложение доступ к реестру, используйте [AfxSetPerUserRegistration](#afxsetperuserregistration).

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

Используйте обрабатывать объект HINSTANCE, возвращаемой этой функцией, для доступа к ресурсам приложения напрямую, например, в вызовах Windows функция `FindResource`.

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор HINSTANCE, в котором загружаются по умолчанию ресурсы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxgetthread"></a>  AfxGetThread

Вызывайте эту функцию для получения указателя на [CWinThread](../../mfc/reference/cwinthread-class.md) объект, представляющий текущий выполняемый поток.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущем потоке; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Должно вызываться из в нужный поток.

> [!NOTE]
>  При переносе проекта MFC вызова `AfxGetThread` из Visual C++ версии 4.2, 5.0 или 6.0, `AfxGetThread` вызовы [AfxGetApp](#afxgetapp) Если ни один поток не найден. В более поздних версиях компилятора `AfxGetThread` возвращает NULL, если ни один поток не был найден. Если требуется, чтобы поток приложения, необходимо вызвать `AfxGetApp`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxinitrichedit"></a>  AfxInitRichEdit

Вызывайте эту функцию для инициализации элемента управления форматированным редактированием (версия 1.0) для приложения.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Примечания

Эта функция предназначена для обеспечения обратной совместимости. Новые приложения должны использовать [AfxInitRichEdit2](#afxinitrichedit2).

`AfxInitRichEdit` Загружает RICHED32. Библиотека DLL для инициализации элемента управления форматированным редактированием версии 1.0. Для использования версии 2.0 и 3.0 элемента управления форматированным редактированием, библиотеки RICHED20. Библиотеки DLL должен быть загружен. Это достигается с помощью вызова [AfxInitRichEdit2](#afxinitrichedit2).

Чтобы обновить элементы управления форматированным редактированием в существующих приложениях Visual C++ до версии 2.0, откройте. RC-файл как текст, измените имя класса каждого управления форматированным редактированием из «RICHEDIT» для «RichEdit20a». Затем замените вызов `AfxInitRichEdit` с `AfxInitRichEdit2`.

Эта функция инициализирует библиотеки общих элементов управления, также в том случае, если библиотека еще не инициализирован для процесса. Если вы используете управления форматированным редактированием непосредственно из приложения MFC, следует вызывать эту функцию, чтобы убедиться, что MFC инициализации среды выполнения элемента управления форматированным редактированием. При вызове метода Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется для вызова этой функции, но в некоторых случаях может быть обязательно.

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2

Вызывайте эту функцию для инициализации элемента управления форматированным редактированием (версия 2.0 и более поздние версии) для приложения.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для загрузки библиотеки RICHED20. Поле ввода DLL и инициализация широкий набор функций версии 2.0. При вызове метода Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется для вызова этой функции, но в некоторых случаях может быть обязательно.

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

  ## <a name="afxisextendedframeclass"></a>  AfxIsExtendedFrameClass
Определяет, является ли заданное окно расширенным объектом фрейма.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Указатель на объект, который является производным от `CWnd`.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если предоставленное окно является расширенным объектом фрейма; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает значение TRUE, если *pWnd* является производным от одного из следующих классов:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Этот метод полезен, когда требуется проверить, что параметр функции или метода является окном расширенного фрейма.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

### <a name="see-also"></a>См. также

[Класс CWnd](cwnd-class.md)<br/>
[Класс CFrameWndEx](cframewndex-class.md)

## <a name="afxismfctoolbar"></a> AfxIsMFCToolBar

Определяет, является ли заданное окно объект панели инструментов.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
[in] Указатель на объект, который является производным от `CWnd`.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если предоставленное окно является объект панели инструментов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод возвращает `TRUE` Если *pWnd* является производным от `CMFCToolBar`. Этот метод полезен, когда потребуется проверить, что параметр функции или метода является `CMFCToolBar` объекта.

### <a name="requirements"></a>Требования

**Заголовок:** afxpriv.h

### <a name="see-also"></a>См. также

[Класс CWnd](cwnd-class.md)<br/>
[Класс CMFCToolBar](cmfctoolbar-class.md)

## <a name="afxkeyboardmanager"></a> AfxKeyboardManager

Указатель на глобальную [manager клавиатуры](ckeyboardmanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxkeyboardmanager.h

### <a name="see-also"></a>См. также

[Макросы, глобальные функции и глобальные переменные](mfc-macros-and-globals.md)<br/>
[Класс CKeyboardManager](ckeyboardmanager-class.md)

##  <a name="afxloadlibrary"></a>  AfxLoadLibrary

Используйте `AfxLoadLibrary` для сопоставления модуль DLL.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Параметры

*lpszModuleName*<br/>
Указывает на заканчивающуюся нулем строку, содержащую имя модуля (либо. Библиотеки DLL или. EXE-файла). Указанное имя является имя файла модуля.

Если в строке указан путь, но файл не существует в указанном каталоге, то функция завершается с ошибкой.

Если путь не указан, а расширение имени файла указан, модуль по умолчанию. Добавляется библиотеки DLL. Тем не менее строка filename может включать конечные символ точки (.) чтобы указать, что имя модуля не имеет расширения. Если путь не указан, функция выполняет поиск файла в следующей последовательности:

- Каталог, из которого загружен приложения.

- Текущий каталог.

- **Windows 95/98:** системном каталоге Windows. **Windows NT:** системный каталог Windows 32-разрядной. Этот каталог называется SYSTEM32.

- **Только для Windows NT:** 16-разрядных Windows системный каталог. Нет функции Win32, который получает путь к каталогу, в этом, но в ней выполнялся поиск. Этот каталог называется системы.

- Каталог Windows.

- Каталоги, которые перечислены в переменной среды PATH.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращается дескриптор модуля. Если функция завершается с ошибкой, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Возвращает дескриптор, который может использоваться в [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) при получении адреса функции DLL. `AfxLoadLibrary` может также использоваться для сопоставления других исполняемых модулей.

Каждый процесс поддерживает счетчик ссылок для каждого модуля в загруженной библиотеки. Этот счетчик ссылок увеличивается каждый раз `AfxLoadLibrary` вызывается и уменьшается на единицу каждый раз `AfxFreeLibrary` вызывается. Когда число ссылок достигает нуля, модуль, не имеет сопоставления из адресного пространства вызывающего процесса и дескриптор недействителен.

Обязательно используйте `AfxLoadLibrary` и `AfxFreeLibrary` (вместо функций Win32 `LoadLibrary` и `FreeLibrary`) Если приложение использует несколько потоков, и если она динамически загружает библиотеки DLL расширения MFC. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` следит за тем, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения MFC не приведет к повреждению глобального состояния MFC.

С помощью `AfxLoadLibrary` в приложении требуется динамическая компоновка версии библиотеки DLL MFC; файл заголовка для `AfxLoadLibrary`, Afxdll_.h, является только включенным, если связанный приложению в виде библиотеки DLL MFC. Это сделано намеренно, так как вам нужно связать с версией библиотеки DLL для MFC, необходимо использовать или создать DLL-расширения MFC.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdll_.h

## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

Указатель на глобальную [manager меню отделяемый](cmenutearoffmanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmenutearoffmanager.h

### <a name="see-also"></a>См. также

[Класс CMenuTearOffManager](cmenutearoffmanager-class.md)

## <a name="afxmousemanager"></a>  AfxMouseManager

Указатель на глобальную [manager мыши](cmousemanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmousemanager.h

### <a name="see-also"></a>См. также

[Класс CMouseManager](cmousemanager-class.md)

##  <a name="afxregisterclass"></a>  AfxRegisterClass

Эта функция используется для регистрации классов окон в библиотеку DLL, которая использует MFC.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Параметры

*lpWndClass*<br/>
Указатель на [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуру, содержащую сведения о классе окно для регистрации. Дополнительные сведения об этой структуре см. в разделе Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если класс успешно зарегистрирован; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если вы используете эту функцию, класс автоматически отменяется, при выгрузке библиотеки DLL.

В сборках не DLL `AfxRegisterClass` идентификатор определяется как макрос, который сопоставляется с функцией Windows `RegisterClass`, так как классы, зарегистрированные в приложении отменяется автоматически. Если вы используете `AfxRegisterClass` вместо `RegisterClass`, код можно использовать без изменений в приложении и в библиотеке DLL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass

Позволяет регистрировать свои собственные классы окон.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Параметры

*nClassStyle*<br/>
Задает стиль класса Windows или сочетание стили, созданные с помощью побитового или ( **&#124;**) оператора для класса окна. Список стилей класса, см. в разделе [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуры в пакете Windows SDK. Если значение равно NULL, значения по умолчанию устанавливается следующим образом:

- Устанавливает стиль мыши CS_DBLCLKS, которая отправляет дважды щелкните сообщения в процедуру при двойном щелчке мыши.

- Задает стиль стрелок курсора для стандартных IDC_ARROW Windows.

- Задает кисть фона значение NULL, поэтому окна не приведет к удалению фоном.

- Задает значок для стандартных, машет флаг значок эмблемы Windows.

*hCursor*<br/>
Указывает дескриптор для ресурса курсора, устанавливаемые в каждом окне, созданный из класса окна. Если использовать значение по умолчанию **0**, вы получите стандартный курсор IDC_ARROW.

*hbrBackground*<br/>
Указывает дескриптор для ресурса кисти, устанавливаемые в каждом окне, созданный из класса окна. Если использовать значение по умолчанию **0**, будет иметь значение NULL фоновую кисть и окна по умолчанию не удалит его фона при обработке [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd).

*hIcon*<br/>
Указывает дескриптор для ресурса значка, устанавливаемые в каждом окне, созданный из класса окна. Если использовать значение по умолчанию **0**, вы получите значок эмблемы Windows стандартные, машет флаг.

### <a name="return-value"></a>Возвращаемое значение

Завершающаяся нулем строка, содержащая имя класса. Можно передать это имя класса для `Create` функции-члена в `CWnd` или других **CWnd -** производные классы для создания окна. Имя создается библиотекой классов Microsoft Foundation.

> [!NOTE]
>  Возвращаемое значение указывает на статический буфер. Чтобы сохранить эту строку, назначить его `CString` переменной.

### <a name="remarks"></a>Примечания

Библиотеки Microsoft Foundation Class автоматически регистрирует несколько классов стандартное окно. Эта функция вызывается в том случае, если вы хотите зарегистрировать свои собственные классы окон.

Имя, зарегистрированное для класса `AfxRegisterWndClass` исключительно зависит от параметров. При вызове метода `AfxRegisterWndClass` несколько раз с идентичными параметрами, она только регистрирует класс при первом вызове. Последующие вызовы `AfxRegisterWndClass` с идентичными параметрами просто возвращают имя класса уже зарегистрирован.

Если вы вызываете `AfxRegisterWndClass` для нескольких классы, производные от CWnd, с идентичными параметрами, вместо получения класса отдельное окно для каждого класса, каждый класс использует один класс. Это может вызвать проблемы, если используется стиль класса CS_CLASSDC. Вместо нескольких классов окон CS_CLASSDC вы получите один класс CS_CLASSDC окна и всех windows на C++, использующих этот общий ресурс класса одного контроллера домена. Чтобы избежать этой проблемы, вызовите [AfxRegisterClass](#afxregisterclass) для регистрации класса.

См. в техническом примечании [TN001: регистрация класса Window](../../mfc/tn001-window-class-registration.md) Дополнительные сведения о регистрации класса окна и `AfxRegisterWndClass` функции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration

Задает, перенаправляет ли приложение доступ к реестру **HKEY_CURRENT_USER** ( **HKCU**) узла.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Значение TRUE указывает, что данные реестра направляется на узел HKCU; Значение FALSE указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Примечания

До появления Windows Vista приложения, обращавшиеся к реестр, обычно используется **HKEY_CLASSES_ROOT** узла. Тем не менее с Windows Vista или более поздних операционных системах, необходимо запустить приложение в режиме с повышенными правами для записи в HKCR.

Этот метод позволяет вашему приложению для чтения и записи в реестр без запуска в режиме с повышенными правами, перенаправляя доступ к реестру из HKCR в HKCU. Дополнительные сведения см. в разделе [Linker Property Pages](../../ide/linker-property-pages.md).

Если вы включили функцию перенаправления реестра, платформа перенаправляет доступ из HKCR для **HKEY_CURRENT_USER\Software\Classes**. Перенаправление влияет только на платформах MFC и ATL.

Реализация по умолчанию обращается к реестра в HKCR.

### <a name="requirements"></a>Требования

  **Заголовок** afxstat_.h

##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle

Эта функция используется для задания HINSTANCE дескриптора, который определяет, где загружаются по умолчанию ресурсы приложения.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Параметры

*hInstResource*<br/>
Дескриптор экземпляра или модуля. Файл EXE или DLL, из которого загружаются ресурсы приложения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="afxshellmanager"></a>  AfxShellManager

Указатель на глобальную [диспетчер оболочки](cshellmanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxshellmanager.h

### <a name="see-also"></a>См. также

[Класс CShellManager](cshellmanager-class.md)

##  <a name="afxsocketinit"></a>  AfxSocketInit

Вызовите эту функцию в вашей `CWinApp::InitInstance` переопределение, чтобы инициализировать Windows Sockets.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Параметры

*lpwsaData*<br/>
Указатель на [WSADATA](../../mfc/reference/wsadata-structure.md) структуры. Если *lpwsaData* не равно NULL, то адрес `WSADATA` структура заполнена, путем вызова `WSAStartup`. Эта функция также гарантирует, что `WSACleanup` вызывается автоматически перед завершением работы приложения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

С помощью сокетов MFC в второстепенных потоков в приложении MFC статически скомпонованной необходимо вызвать метод `AfxSocketInit` в каждом потоке, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.

### <a name="requirements"></a>Требования

  **Заголовок** afxsock.h

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager

Указатель на глобальную [средства диспетчера пользователей](cusertoolsmanager-class.md).

### <a name="syntax"></a>Синтаксис

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Требования

**Заголовок:** afxusertoolsmanager.h

### <a name="see-also"></a>См. также

[Класс CUserToolsManager](cusertoolsmanager-class.md)

##  <a name="afxwininit"></a>  AfxWinInit

Эта функция вызывается библиотека MFC предоставляет `WinMain` функции, как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации приложения на базе графического интерфейса пользователя, для инициализации MFC.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Параметры

*hInstance*<br/>
Дескриптор текущего выполняемого модуля.

*hPrevInstance*<br/>
Дескриптор к предыдущему экземпляру приложения. Для приложения на базе Win32, этот параметр всегда является **NULL**.

*lpCmdLine*<br/>
Указатель на заканчивающуюся нулем строку, указав в командной строке для приложения.

*nCmdShow*<br/>
Указывает, как будет показано главное окно приложения с графическим Интерфейсом.

### <a name="remarks"></a>Примечания

Для консольного приложения, который не использует предоставляемую MFC `WinMain` функцию, необходимо вызвать `AfxWinInit` непосредственно к инициализации MFC.

При вызове метода `AfxWinInit` самостоятельно, следует объявить экземпляр `CWinApp` класса. Для консольного приложения, вы можете не собственный производный класс от `CWinApp` и вместо этого используйте экземпляр `CWinApp` напрямую. Этот метод подходит, если вы решили оставить все функциональные возможности для вашего приложения в своей реализации **основной**.

> [!NOTE]
>  При создании контекста активации для сборки, MFC использует ресурс манифеста, предоставляемых модулем пользователя. Контекст активации создается в `AfxWinInit`. Дополнительные сведения см. в разделе [поддержка контекстов активации в состоянии модуля MFC](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxwin.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Класс CWinApp](../../mfc/reference/cwinapp-class.md)
