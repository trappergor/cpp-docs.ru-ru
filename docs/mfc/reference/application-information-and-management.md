---
title: "Сведения о приложении и управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cc9adde202f211d6e0a536e949b42772f0890ef6
ms.lasthandoff: 02/24/2017

---
# <a name="application-information-and-management"></a>Сведения о приложении и управление им
При написании приложения, можно создать один [CWinApp](../../mfc/reference/cwinapp-class.md)-производный объект. Время от времени требуется получить сведения об этом объекте из вне `CWinApp`-производный объект.  
  
 Библиотеки классов Microsoft Foundation предоставляет следующие глобальные функции для выполнения этих задач:  
  
### <a name="application-information-and-management-functions"></a>Сведения о приложении и функции управления  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|Создает новый поток.|  
|[AfxEndThread](#afxendthread)|Завершает текущий поток.|  
|[AfxFreeLibrary](#afxfreelibrary)|Уменьшает счетчик ссылок модуля загрузки библиотеки динамической компоновки (DLL); Когда число ссылок достигает нуля, модуль не имеет сопоставления.|  
|[AfxGetApp](#afxgetapp)|Возвращает указатель на приложение одного `CWinApp` объекта.|  
|[AfxGetAppName](#afxgetappname)|Возвращает строку, содержащую имя приложения.|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Возвращает `HINSTANCE` представляющий этот экземпляр приложения.|  
|[AfxGetMainWnd](#afxgetmainwnd)|Возвращает указатель текущего окна «main» приложения, отличных от OLE или серверного приложения окна фрейма на месте.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|Возвращает `HINSTANCE` источник по умолчанию ресурсы приложения. Используется для прямого доступа к ресурсам приложения.|  
|[AfxGetThread](#afxgetthread)|Извлекает указатель на текущий [CWinThread](../../mfc/reference/cwinthread-class.md) объекта.|  
|[AfxInitRichEdit](#afxinitrichedit)|Инициализирует версии 1.0 форматированным редактированием управления приложения.|  
|[AfxInitRichEdit2](#afxinitrichedit2)|Инициализирует версии 2.0 и более поздних форматированным редактированием управления приложения.|  
|[AfxLoadLibrary](#afxloadlibrary)|Сопоставляет модуль DLL и возвращает дескриптор, который может использоваться для получения адреса функции DLL.|  
|[AfxRegisterClass](#afxregisterclass)|Регистрирует класс окна в библиотеку DLL, которая использует MFC.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|Регистрирует класс окна Windows для дополнения автоматически зарегистрированным в MFC.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|Наборы `HINSTANCE` дескриптор, где загружаются по умолчанию ресурсы приложения.|  
|[AfxSocketInit](#afxsocketinit)|Вызывается `CWinApp::InitInstance` переопределение для инициализации Windows Sockets.|  
|[AfxWinInit](#afxwininit)|Вызывается библиотека MFC предоставляет `WinMain` функции, как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации приложения на основе графического интерфейса пользователя, инициализировать MFC. Должен вызываться непосредственно для консольных приложений, использующих MFC.|  
  

  
##  <a name="a-nameafxbeginthreada--afxbeginthread"></a><a name="afxbeginthread"></a>AfxBeginThread  
 Эта функция вызывается для создания нового потока.  
  
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
 `pfnThreadProc`  
 Указывает на функцию управления для рабочего потока. Не может быть **NULL**. Эта функция должна быть объявлен следующим образом:  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 RUNTIME_CLASS объекта, производного от [CWinThread](../../mfc/reference/cwinthread-class.md).  
  
 *pParam*  
 Параметр, передаваемый в функцию управления как показано в параметре объявление функции в `pfnThreadProc`.  
  
 `nPriority`  
 Требуемый приоритет потока. Полный список и описание доступных приоритеты см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nStackSize`  
 Указывает размер в байтах стека для нового потока. Если значение равно 0, размер стека по умолчанию используется тот же размер стека, что и для создания потока.  
  
 `dwCreateFlags`  
 Указывает дополнительный флаг, который управляет созданием потока. Этот флаг может содержать одно из двух значений:  
  
- **CREATE_SUSPENDED** запуска потока с одного счетчик приостановок. Используйте **CREATE_SUSPENDED** чтобы инициализировать любые данные, член `CWinThread` объект, такой как [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) или любым членам производного класса, перед началом потока. После завершения своей инициализации использовать [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) для запуска выполнения потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.  
  
- **0** запустить поток сразу же после создания.  
  
 `lpSecurityAttrs`  
 Указывает [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая задает атрибуты безопасности для потока. Если **NULL**, атрибуты те же параметры безопасности, как будет использовано для создаваемого потока. Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект вновь созданный поток или **NULL** при сбое.  
  
### <a name="remarks"></a>Примечания  
 Первая форма `AfxBeginThread` создает рабочий поток. Вторая форма создает поток, который может быть записан как потока пользовательского интерфейса или как рабочий поток.  
  
 `AfxBeginThread`Создает новый `CWinThread` объекта, вызывает его [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) для запуска выполнения потока и возвращает указатель на поток. Проверяет вносятся во всей процедуры, убедитесь, что все объекты, освобожденных должным образом вызывать любую часть создания. Чтобы завершить поток, вызовите [AfxEndThread](#afxendthread) из потока или возврат из функции управления рабочего потока.  
  
 Многопоточность должна быть включена для приложения; в противном случае функция завершится ошибкой. Дополнительные сведения о включении многопоточности см. [/MD, / MT, /LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md) под *параметры компилятора Visual C++*.  
  
 Дополнительные сведения о `AfxBeginThread`, см. в статьях [Многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md).  
  
### <a name="example"></a>Пример  
 В примере показано [CSocket::Attach](../../mfc/reference/csocket-class.md#attach).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxendthreada--afxendthread"></a><a name="afxendthread"></a>AfxEndThread  
 Эта функция вызывается для завершения текущего потока.  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>Параметры  
 *nExitCode*  
 Указывает код завершения потока.  
  
 *bDelete*  
 Удаляет объект потока из памяти.  
  
### <a name="remarks"></a>Примечания  
 Должен вызываться из потока, подлежащего прерыванию.  
  
 Дополнительные сведения о `AfxEndThread`, см. в статье [Многопоточность: прерывание потоков](../../parallel/multithreading-terminating-threads.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxfreelibrarya--afxfreelibrary"></a><a name="afxfreelibrary"></a>AfxFreeLibrary  
 Оба `AfxFreeLibrary` и `AfxLoadLibrary` поддерживает счетчик ссылок для каждого модуля загрузки библиотеки.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>Параметры  
 *hInstLib*  
 Дескриптор библиотеки загруженного модуля. [AfxLoadLibrary](#afxloadlibrary) возвращает этот дескриптор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если функция выполнена успешно; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `AfxFreeLibrary`уменьшает счетчик ссылок модуля загрузки библиотеки динамической компоновки (DLL). Когда число ссылок достигает нуля, модуль не имеет сопоставления из адресного пространства процесса вызова и дескриптор недействителен. Этот счетчик увеличивается каждый раз `AfxLoadLibrary` вызывается.  
  
 До отмены сопоставления коллекции модуль библиотеки, система включает библиотеку DLL для отсоединения от процессов, с его помощью. Это дает возможность очистить ресурсы, выделенные от имени текущего процесса библиотеки DLL. После возврата функции точки входа библиотеки модуля удаляется из адресного пространства для текущего процесса.  
  
 Используйте `AfxLoadLibrary` для сопоставления DLL-модуля.  
  
 Обязательно используйте `AfxFreeLibrary` и `AfxLoadLibrary` (вместо функций Win32 **FreeLibrary** и **LoadLibrary**) Если приложение использует несколько потоков. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке Библиотеки расширения, не приведет к повреждению глобального состояния MFC.  
  
### <a name="example"></a>Пример  
 В примере показано [AfxLoadLibrary](#afxloadlibrary).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdll_.h  
  
##  <a name="a-nameafxgetappa--afxgetapp"></a><a name="afxgetapp"></a>AfxGetApp  
 Указатель, возвращенный этой функции можно использовать для доступа к данным приложения, такие как кодом главного диспетчеризации сообщений или самое верхнее окно.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на один `CWinApp` объекта для приложения.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод возвращает значение NULL, это может указывать, applicationâ€™ s главное окно еще не была инициализирована полностью. Он также может указывать на проблему.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#126;](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxgetappnamea--afxgetappname"></a><a name="afxgetappname"></a>AfxGetAppName  
 Строка, возвращаемая этой функцией можно использовать для диагностические сообщения или в качестве корневого для имен временной строки.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Завершающим нулем строка, содержащая имя приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#127;](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxgetinstancehandlea--afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 Эта функция позволяет получить дескриптор экземпляра текущего приложения.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Для текущего экземпляра приложения. При вызове из библиотеки DLL, связанной с MFC, версии USRDLL `HINSTANCE` возвращается к библиотеке DLL.  
  
### <a name="remarks"></a>Примечания  
 `AfxGetInstanceHandle`всегда возвращает `HINSTANCE` исполняемого файла (. (EXE), если он вызывается из библиотеки DLL связаны с версии USRDLL MFC. В этом случае она возвращает `HINSTANCE` на библиотеку DLL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#128;](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxgetmainwnda--afxgetmainwnd"></a><a name="afxgetmainwnd"></a>AfxGetMainWnd  
 Если приложение является OLE-сервер, эта функция вызывается для извлечения указателя активное окно основного приложения, а не непосредственно ссылается [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) член объекта приложения.  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если на сервере имеется объект, являющийся на месте активный внутри контейнера и этот контейнер активна, эта функция возвращает указатель к объекту окна фрейма, содержащего активный документ на месте.  
  
 Если нет, является активным на месте в контейнере объекта или приложения не является OLE-сервер, эта функция просто возвращает `m_pMainWnd` объекта приложения.  
  
 Если `AfxGetMainWnd` вызывается из основного потока приложения, он возвращает главное окно приложения в соответствии с приведенными выше правилами. Если функция вызывается из второго потока в приложении, функция возвращает главного окна, связанный с потоком вызывающего.  
  
### <a name="remarks"></a>Примечания  
 Если приложение не является OLE-сервер, то при вызове этой функции является эквивалентом непосредственно ссылается `m_pMainWnd` член объекта приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#129;](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxgetperuserregistrationa--afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Примечания  
 Если включить перенаправление системного реестра, платформа перенаправляет доступ из **HKCR** для **HKEY_CURRENT_USER\Software\Classes**. Только платформы MFC и ATL, подвержены перенаправления.  
  
 Чтобы изменить перенаправляет ли приложение доступ к реестру, используйте [AfxSetPerUserRegistration](#afxsetperuserregistration).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxstat_.h    
  
##  <a name="a-nameafxgetresourcehandlea--afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 Используйте `HINSTANCE` дескриптор, возвращаемый этой функцией напрямую получать доступ к ресурсам приложения, например, в вызовах функции Windows **FindResource**.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Дескриптора, где загружаются по умолчанию ресурсы приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#130;](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxgetthreada--afxgetthread"></a><a name="afxgetthread"></a>AfxGetThread  
 Эта функция вызывается для получения указателя на [CWinThread](../../mfc/reference/cwinthread-class.md) объект, представляющий текущий выполняемый поток.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий выполняемый поток; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Должно вызываться из в нужный поток.  
  
> [!NOTE]
>  При переносе проекта MFC вызова `AfxGetThread` из Visual C++ версии 4.2, 5.0 или 6.0, `AfxGetThread` вызовов [AfxGetApp](#afxgetapp) Если ни один поток не найден. В Visual c + .NET и более поздних версиях `AfxGetThread` возвращает **NULL** Если ни один поток не найдены. Если требуется, чтобы поток приложения, необходимо вызвать метод `AfxGetApp`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#132;](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxinitrichedita--afxinitrichedit"></a><a name="afxinitrichedit"></a>AfxInitRichEdit  
 Эта функция вызывается для инициализации управления rich edit (версия 1.0) для приложения.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция предназначена для обеспечения обратной совместимости. Приложения, созданные с помощью Visual C++ .NET и последующего использования [AfxInitRichEdit2](#afxinitrichedit2).  
  
 `AfxInitRichEdit`Загружает RICHED32. Библиотеки DLL инициализации версии 1.0 управления rich edit. Для использования версии 2.0 и 3.0 для управления rich edit, библиотеки RICHED20. Библиотека должна быть загружена. Это достигается с помощью вызова [AfxInitRichEdit2](#afxinitrichedit2). При наличии диалоговых ресурсов с помощью управления rich edit, созданных до Visual C++ .NET, элементы управления форматированным редактированием, автоматически версии 1.0. Вставка с помощью редактора ресурсов Visual C++ .NET элементов управления rich edit, версия 2.0.  
  
 Чтобы обновить элементы управления форматированным редактированием в существующих приложениях Visual C++ до версии 2.0, откройте. RC-файл в текстовом, измените имя класса каждого управления rich edit из «RICHEDIT» на «RichEdit20a». Затем замените вызов `AfxInitRichEdit` с `AfxInitRichEdit2`.  
  
 Эта функция также инициализирует библиотеки общих элементов управления, если библиотека еще не была инициализирована для процесса. При использовании управления rich edit непосредственно из приложения MFC, следует вызвать эту функцию, чтобы гарантировать, что MFC инициализации среды выполнения элемента управления форматированным редактированием. Если вызвать метод Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется вызывать данную функцию, но в некоторых случаях может возникнуть необходимость.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxinitrichedit2a--afxinitrichedit2"></a><a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 Эта функция вызывается для инициализации управления rich edit (версии 2.0 или более поздней версии) для приложения.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для загрузки библиотеки RICHED20. Библиотеки DLL и версии 2.0 богатыми инициализации поля ввода. Если вызвать метод Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется вызывать данную функцию, но в некоторых случаях может возникнуть необходимость.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxloadlibrarya--afxloadlibrary"></a><a name="afxloadlibrary"></a>AfxLoadLibrary  
 Используйте `AfxLoadLibrary` для сопоставления DLL-модуля.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>Параметры  
 *lpszModuleName*  
 Указывает нулем строка, содержащая имя модуля (либо. Библиотеки DLL или. EXE-файла). Указанное имя является имя файла модуля.  
  
 Если строка указывает путь, но файл не существует в указанном каталоге, функция завершается с ошибкой.  
  
 Если путь не указан, а расширение имени файла отсутствует, модуль по умолчанию. Библиотека DLL добавляется. Тем не менее строка имя файла может содержать конечные символ точки (.) для указания, что расширения не имеет имя модуля. Если путь не указан, функция выполняет поиск файла в следующей последовательности:  
  
-   Каталог, из которого загружен приложения.  
  
-   Текущий каталог.  
  
- **Windows 95/98:** системном каталоге Windows. **Windows NT:** системном каталоге Windows 32-разрядной. Имя этого каталога сохраняется в папке SYSTEM32.  
  
- **Только для Windows NT:** каталог системы 16-разрядной версии Windows. Нет функции Win32, которая получает путь каталога, но он выполняется. Этот каталог называется системы.  
  
-   Каталог Windows.  
  
-   Каталоги, которые перечислены в переменной среды PATH.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращается дескриптор модуля. Если функция завершается с ошибкой, то возвращаемое значение равно NULL.  
  
### <a name="remarks"></a>Примечания  
 Возвращает маркер, который может использоваться в [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) при получении адреса функции DLL. `AfxLoadLibrary`может также использоваться для сопоставления другие исполняемые модули.  
  
 Каждый процесс поддерживает счетчик ссылок для каждого модуля загрузки библиотеки. Этот счетчик увеличивается каждый раз `AfxLoadLibrary` вызывается и уменьшается на единицу при каждом `AfxFreeLibrary` вызывается. Когда число ссылок достигает нуля, модуль не имеет сопоставления из адресного пространства процесса вызова и дескриптор недействителен.  
  
 Обязательно используйте `AfxLoadLibrary` и `AfxFreeLibrary` (вместо функций Win32 **LoadLibrary** и **FreeLibrary**) Если приложение использует несколько потоков, и если он динамически загружает расширение DLL. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения не приведет к повреждению глобального состояния MFC.  
  
 С помощью `AfxLoadLibrary` в приложении требуется динамическую ссылку на версию библиотеки DLL MFC; файл заголовка для `AfxLoadLibrary`, Afxdll_.h, является только включенным, если связанный приложению в виде библиотеки DLL MFC. Это сделано намеренно, так как имеется ссылка на версию библиотеки DLL MFC для использования или создания библиотеки DLL расширения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_DLLUser&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&#2;](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&#3;](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdll_.h  
   
  
##  <a name="a-nameafxregisterclassa--afxregisterclass"></a><a name="afxregisterclass"></a>AfxRegisterClass  
 Эту функцию можно используйте для регистрации классов окон в библиотеке DLL, которое использует MFC.  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>Параметры  
 *lpWndClass*  
 Указатель на [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуру, содержащую сведения о классе окна для регистрации. Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если класс является успешно зарегистрирован; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 При использовании этой функции класса автоматически отменяется, когда выгружается DLL.  
  
 В сборках не DLL `AfxRegisterClass` идентификатор представляет собой макрос, который сопоставляется с функцией Windows **RegisterClass**, поскольку классы, зарегистрированные в приложении автоматически отменяется. Если вы используете `AfxRegisterClass` вместо **RegisterClass**, код можно использовать без изменений в приложении и в библиотеке DLL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_DLL&#3;](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxregisterwndclassa--afxregisterwndclass"></a><a name="afxregisterwndclass"></a>AfxRegisterWndClass  
 Позволяет регистрировать свои собственные классы окон.  
  
```  
 
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>Параметры  
 *nClassStyle*  
 Задает стиль класса Windows или сочетание стили, созданные с помощью побитового или ( **|**) оператора для класса окна. Список стилей класса, в разделе [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Если **NULL**, значения по умолчанию задается следующим образом:  
  
-   Задает стиль мыши **CS_DBLCLKS**, которая отправляет дважды щелкнуть сообщение процедуре окна, при двойном щелчке мыши.  
  
-   Задает стиль стрелки курсоров стандарта Windows **IDC_ARROW**.  
  
-   Задает кисть фона **NULL**, поэтому окна не удалит его задний план.  
  
-   Задает значок для стандартных, роли отметок флаг значок логотипа Windows.  
  
 `hCursor`  
 Указывает дескриптор ресурса курсора, устанавливаемые в каждом окне, созданный из класса окна. Если используется стандартное **0**, вы получите стандартный **IDC_ARROW** курсора.  
  
 *hbrBackground*  
 Указывает дескриптор ресурса кисти устанавливаемых в каждом окне, созданный из класса окна. Если используется стандартное **0**, будет иметь **NULL** кисть фона и отобразится окно, по умолчанию не удалить его задний план при обработке [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  
  
 `hIcon`  
 Указывает дескриптор ресурс значка, устанавливаемые в каждом окне, созданный из класса окна. Если используется стандартное **0**, вы получите стандартных, роли отметок флаг значок логотипа Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Завершающим нулем строка, содержащая имя класса. Можно передать имя класса для **создать** функции-члена `CWnd` или других **CWnd -**производные классы для создания окна. Имя формируется библиотеки Microsoft Foundation Class.  
  
> [!NOTE]
>  Возвращаемое значение является указателем на статический буфер. Чтобы сохранить эту строку, назначьте его `CString` переменной.  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation автоматически регистрирует несколько классов стандартное окно. Эта функция вызывается в том случае, если вы хотите зарегистрировать свой собственный класс окна.  
  
 Имя, зарегистрированное для класса, `AfxRegisterWndClass` исключительно зависит от параметров. При вызове метода `AfxRegisterWndClass` несколько раз с идентичными параметрами регистрируются только при первом вызове класс. Последующие вызовы `AfxRegisterWndClass` с идентичными параметрами просто возвращают classname уже зарегистрирован.  
  
 При вызове метода `AfxRegisterWndClass` для нескольких классы, производные от CWnd с идентичными параметрами, вместо получения класса отдельное окно для каждого класса, каждый класс использует один класс. Это может вызвать проблемы, если **CS_CLASSDC** используется стиль класса. Вместо нескольких **CS_CLASSDC** классы окон, вы получите одно **CS_CLASSDC** класс окна и всех windows на C++, использующие, что класс совместного использования одного контроллера домена. Чтобы избежать этой проблемы, вызовите [AfxRegisterClass](#afxregisterclass) для регистрации класса.  
  
 См. Техническое Примечание [TN001: регистрация класса Window](../../mfc/tn001-window-class-registration.md) Дополнительные сведения о регистрации класса окна и `AfxRegisterWndClass` функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#134;](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxsetperuserregistrationa--afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра в узел по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Примечания  
 Прежде чем [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], приложения, которые обращаются к реестру, обычно используют **HKEY_CLASSES_ROOT** узла. Однако при использовании [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], необходимо запустить приложение в режиме с повышенными правами на запись в **HKCR**.  
  
 Этот метод позволяет вашему приложению для чтения и записи в реестр без запуска в режиме с повышенными правами, перенаправляя доступ к реестру из **HKCR** для **HKCU**. Дополнительные сведения см. в разделе [страницы свойств компоновщика](../../ide/linker-property-pages.md).  
  
 Если включить перенаправление системного реестра, платформа перенаправляет доступ из **HKCR** для **HKEY_CURRENT_USER\Software\Classes**. Только платформы MFC и ATL, подвержены перенаправления.  
  
 Реализация по умолчанию обращается к разделе реестра **HKCR**.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxstat_.h    
  
##  <a name="a-nameafxsetresourcehandlea--afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 Эта функция позволяет задать `HINSTANCE` дескриптор, который определяет, где загружаются по умолчанию ресурсы приложения.  
  
```  
 
void  
AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>Параметры  
 `hInstResource`  
 Дескриптор экземпляра или модуля. Файл EXE или DLL, из которого загружаются ресурсы приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#135;](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="a-nameafxsocketinita--afxsocketinit"></a><a name="afxsocketinit"></a>AfxSocketInit  
 Эта функция вызывается вашей `CWinApp::InitInstance` переопределение для инициализации Windows Sockets.  
  
```  
 
BOOL  
AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `lpwsaData`  
 Указатель на [WSADATA](../../mfc/reference/wsadata-structure.md) структуры. Если `lpwsaData` не равен `NULL`, то адрес `WSADATA` структура заполняется при вызове `WSAStartup`. Эта функция также гарантирует, что `WSACleanup` вызывается автоматически до завершения приложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При использовании сокеты MFC в дополнительных потоках в приложении MFC статически скомпонованной, необходимо вызвать `AfxSocketInit` каждого потока, которая использует сокеты инициализировать библиотеку сокетов. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxsock.h  
  
##  <a name="a-nameafxwininita--afxwininit"></a><a name="afxwininit"></a>AfxWinInit  
 Эта функция вызывается библиотека MFC предоставляет `WinMain` функции, как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации приложения на основе графического интерфейса пользователя, инициализировать MFC.  
  
```  
 
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор текущего выполняемого модуля.  
  
 *hPrevInstance*  
 Дескриптор предыдущего экземпляра приложения. Для приложения на базе Win32, этот параметр всегда будет **NULL**.  
  
 `lpCmdLine`  
 Указывает нулем строка, задающая командной строки для приложения.  
  
 `nCmdShow`  
 Указывает, как будет показано главное окно приложения с пользовательским Интерфейсом.  
  
### <a name="remarks"></a>Примечания  
 Для консольного приложения, который не используется библиотека MFC предоставляет `WinMain` функции, необходимо вызвать метод `AfxWinInit` непосредственно для инициализации MFC.  
  
 При вызове метода `AfxWinInit` самостоятельно, следует объявить экземпляр `CWinApp` класса. Для консольного приложения, вы можете не создать собственный производный класс от `CWinApp` и вместо этого используйте экземпляр `CWinApp` напрямую. Этот метод подходит, если вы решите оставить все функциональные возможности для приложения в своей реализации **основной**.  
  
> [!NOTE]
>  При создании контекста активации для сборки, MFC использует ресурса манифеста, предоставленной модулем пользователя. Контекст активации по умолчанию создается в `AfxWinInit`. Дополнительные сведения см. в разделе [поддержка контекстов активации в состоянии модуля MFC](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_AfxWinInit&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp-класс](../../mfc/reference/cwinapp-class.md)

