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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 5d7b6a0c31a8c4ff63b3cfc1fa58c08879e37f58
ms.lasthandoff: 04/04/2017

---
# <a name="application-information-and-management"></a>Сведения о приложении и управление им
При написании приложения, создается один [CWinApp](../../mfc/reference/cwinapp-class.md)-производного объекта. В некоторых случаях требуется получить сведения об этом объекте из вне `CWinApp`-производного объекта. Или может потребоваться доступ к объектам другие глобальные «диспетчер».
  
 Библиотеки классов Microsoft Foundation предоставляет следующие глобальные функции для выполнения этих задач:  
  
### <a name="application-information-and-management-functions"></a>Сведения о приложении и функции управления  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|Создает новый поток.|  
|[AfxContextMenuManager](#afxcontextmenumanager)|Указатель на глобальную [контекстное меню диспетчера](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Прерывает выполнение текущего потока.|  
|[AfxFindResourceHandle](#afxfindresourcehandle)|Обходит цепочку ресурсов и найдите определенный идентификатор ресурса, ресурс и тип ресурса. |
|[AfxFreeLibrary](#afxfreelibrary)|Уменьшает счетчик ссылок модуля загрузить библиотеку динамической компоновки (DLL). Когда число ссылок достигает нуля, модуль не имеет сопоставления.|  
|[AfxGetApp](#afxgetapp)|Возвращает указатель на приложение одного `CWinApp` объекта.|  
|[AfxGetAppName](#afxgetappname)|Возвращает строку, содержащую имя приложения.|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Возвращает `HINSTANCE` представляющий этот экземпляр приложения.|  
|[AfxGetMainWnd](#afxgetmainwnd)|Возвращает указатель для текущего окна «main», отличных от OLE приложения или окна фрейма на месте серверного приложения.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|Возвращает `HINSTANCE` в источник по умолчанию ресурсы приложения. Используется для прямого доступа к ресурсам приложения.|  
|[AfxGetThread](#afxgetthread)|Извлекает указатель на текущий [CWinThread](../../mfc/reference/cwinthread-class.md) объекта.|  
|[AfxInitRichEdit](#afxinitrichedit)|Инициализирует версии 1.0 rich элемент управления для приложения.|  
|[AfxInitRichEdit2](#afxinitrichedit2)|Инициализирует версии 2.0 и более поздних rich элемент управления для приложения.| 
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Определяет, является ли заданное окно расширенным объектом фрейма.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Определяет, является ли заданное окно объект панели инструментов.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Указатель на глобальную [manager клавиатуры](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Сопоставляет модуль DLL и возвращает дескриптор, который может использоваться для получения адреса функции DLL.|  
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Указатель на глобальную [отделяемого меню диспетчер](cmenutearoffmanager-class.md).|
|[AfxMouseManager](#afxmousemanager)|Указатель на глобальную [мыши manager](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|Регистрирует класс окна в библиотеку DLL, которая использует MFC.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|Регистрирует класс окна Windows для дополняют автоматически зарегистрирован с MFC.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|Наборы `HINSTANCE` дескриптора, в котором загружаются по умолчанию ресурсы приложения.|  
|[AfxShellManager](#afxshellmanager)|Указатель на глобальную [диспетчер оболочки](cshellmanager-class.md). |
|[AfxSocketInit](#afxsocketinit)|Вызывается `CWinApp::InitInstance` переопределение, чтобы инициализировать Windows Sockets.|  
|[AfxUserToolsManager](#afxusertoolsmanager)|Указатель на глобальную [средства диспетчера пользователей](cusertoolsmanager-class.md).|
|[AfxWinInit](#afxwininit)|Вызывается методом библиотека MFC предоставляет `WinMain` функции как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации Графическим пользовательским интерфейсом приложения для инициализации MFC. Должен вызываться непосредственно для консольных приложений, использующих MFC.|  
  

  
##  <a name="afxbeginthread"></a>AfxBeginThread  
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
 Указывает функцию управления рабочего потока. Не может быть **NULL**. Эта функция должна быть объявлен следующим образом:  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 RUNTIME_CLASS объекта, производного от [CWinThread](../../mfc/reference/cwinthread-class.md).  
  
 *pParam*  
 Параметр должен быть передан функции управления, как показано в параметр, чтобы объявление функции в `pfnThreadProc`.  
  
 `nPriority`  
 Необходимый приоритет потока. Полный список и описание доступных приоритетов см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в Windows SDK.  
  
 `nStackSize`  
 Указывает размер в байтах стека для нового потока. Если значение равно 0, размер стека по умолчанию используется тот же размер стека, что и для создания потока.  
  
 `dwCreateFlags`  
 Указывает дополнительный флаг, которое контролирует создание потока. Этот флаг может содержать одно из двух значений:  
  
- **CREATE_SUSPENDED** запуска потока с одного счетчик приостановок. Используйте **CREATE_SUSPENDED** Если необходимо инициализировать все данные-член `CWinThread` объект, такой как [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) или любым членам производного класса, перед началом потока. После инициализации вашей используйте [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) для запуска выполнения потока. Поток не будет выполняться до `CWinThread::ResumeThread` вызывается.  
  
- **0** запустить поток сразу после создания.  
  
 `lpSecurityAttrs`  
 Указывает на [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) структура, которая задает атрибуты безопасности для потока. Если **NULL**, атрибуты тот же уровень безопасности, как будет использоваться создаваемого потока. Дополнительные сведения о структуре см. в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект вновь созданный поток или **NULL** в случае возникновения сбоя.  
  
### <a name="remarks"></a>Примечания  
 Первая форма `AfxBeginThread` создает рабочий поток. Вторая форма создает поток, который может быть записан как потока пользовательского интерфейса или рабочий поток.  
  
 `AfxBeginThread`Создает новый `CWinThread` объекта, вызывает его [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) для запуска выполнения потока и возвращает указатель на поток. Проверяет вносятся во всей процедуры, убедитесь, что все объекты, освобожденных должным образом вызывать любую часть создания. Чтобы завершить поток, вызовите [AfxEndThread](#afxendthread) из потока или возврата из функции управления рабочего потока.  
  
 Многопоточность необходимо включить для приложения; в противном случае функция завершится ошибкой. Дополнительные сведения о включении многопоточность посвящены [/MD, / MT, /LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md) под *параметры компилятора Visual C++*.  
  
 Дополнительные сведения о `AfxBeginThread`, см. в статьях [Многопоточность: создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [Многопоточность: создание потоков пользовательского интерфейса](../../parallel/multithreading-creating-user-interface-threads.md).  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CSocket::Attach](../../mfc/reference/csocket-class.md#attach).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  

## <a name="afxcontextmenumanager"></a>AfxContextMenuManager
Указатель на глобальную [контекстное меню диспетчера](ccontextmenumanager-class.md).  
   
### <a name="syntax"></a>Синтаксис    
```  
CContextMenuManager* afxContextMenuManager;  
```     
### <a name="requirements"></a>Требования  
 **Заголовок:** afxcontextmenumanager.h     

### <a name="see-also"></a>См. также   
 [Класс CContextMenuManager](ccontextmenumanager-class.md)

  
##  <a name="afxendthread"></a>AfxEndThread  
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
 Должна вызываться из потока, подлежащего прерыванию.  
  
 Дополнительные сведения о `AfxEndThread`, см. в статье [Многопоточность: прерывание потоков](../../parallel/multithreading-terminating-threads.md).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Используйте `AfxFindResourceHandle` для последовательного цепочку ресурсов и найдите определенного типа ресурса, ресурс идентификатор и ресурсов.  
   
### <a name="syntax"></a>Синтаксис    
```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );  
```
### <a name="parameters"></a>Параметры  
 `lpszName`  
 Указатель на строку, содержащую идентификатор ресурса.    
 *lpszType*  
 Указатель на тип ресурса. Список типов ресурсов см. в разделе [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) в Windows SDK.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор модуля, содержащего ресурс.  
   
### <a name="remarks"></a>Примечания  
 `AfxFindResourceHandle`Находит определенного ресурса и возвращает дескриптор модуля, содержащего ресурс. Ресурс может быть любое расширение загрузки библиотеки DLL. `AfxFindResourceHandle`Указывает, какой из них имеет ресурса.  
  
 Модули ищутся в следующем порядке:  
  
1.  Главный модуль (если он является расширением DLL).  
  
2.  Модули несистемных.  
  
3.  Модули, зависящие от языка.  
  
4.  Главный модуль (если это системных DLL).  
  
5.  Системные модули.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
  
##  <a name="afxfreelibrary"></a>AfxFreeLibrary  
 Оба `AfxFreeLibrary` и `AfxLoadLibrary` поддерживает счетчик ссылок для каждого модуля загрузить библиотеки.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>Параметры  
 *hInstLib*  
 Дескриптор библиотеки загруженного модуля. [AfxLoadLibrary](#afxloadlibrary) возвращает этот дескриптор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если функция выполнена успешно; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 `AfxFreeLibrary`уменьшает счетчик ссылок модуля загрузить библиотеку динамической компоновки (DLL). Когда число ссылок достигает нуля, модуль не сопоставляется с адресном пространстве вызывающего процесса и дескриптор недействителен. Этот счетчик увеличивается каждый раз `AfxLoadLibrary` вызывается.  
  
 До отмены сопоставления модуля библиотеки, система включает библиотеку DLL для отсоединения от процессов, используя его. Это дает возможность очистить ресурсы, выделенные текущего процесса, библиотеки DLL. После возврата функции точки входа, модуль библиотеки удаляется из адресного пространства текущего процесса.  
  
 Используйте `AfxLoadLibrary` для сопоставления модуль DLL.  
  
 Обязательно используйте `AfxFreeLibrary` и `AfxLoadLibrary` (вместо функций Win32 **FreeLibrary** и **LoadLibrary**) Если приложение использует несколько потоков. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения, не приведет к повреждению глобального состояния MFC.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [AfxLoadLibrary](#afxloadlibrary).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdll_.h  
  
##  <a name="afxgetapp"></a>AfxGetApp  
 Указатель, возвращаемый этой функцией можно использовать для доступа к сведений о приложении, например код основного диспетчеризации сообщений или самое верхнее окно.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на один `CWinApp` объекта для приложения.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод возвращает значение NULL, это может означать, что главное окно приложения еще не была инициализирована полностью. Он также может указывать на проблему.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxgetappname"></a>AfxGetAppName  
 Эта функция возвращает строку можно использовать для диагностических сообщений или в качестве корня для имен временной строки.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нулем строка, содержащая имя приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 Эта функция позволяет получить дескриптор экземпляра текущего приложения.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Для текущего экземпляра приложения. При вызове из библиотеки DLL, связанном с версией USRDLL MFC, `HINSTANCE` возвращается к библиотеке DLL.  
  
### <a name="remarks"></a>Примечания  
 `AfxGetInstanceHandle`всегда возвращает `HINSTANCE` исполняемого файла (. (EXE), если она вызывается из библиотеки DLL связанные с версией USRDLL MFC. В этом случае он возвращает `HINSTANCE` на библиотеку DLL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxgetmainwnd"></a>AfxGetMainWnd  
 Если приложение является OLE-сервер, эта функция вызывается для получения указатель active главного окна приложения, а не непосредственно ссылается на [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) члена объекта приложения.  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если объект, находящийся на месте на сервере active внутри контейнера и этот контейнер активна, эта функция возвращает указатель на объект window фрейма, содержащего активный документ на месте.  
  
 Если нет объекта, который активен на месте в контейнере или приложения не является OLE-сервер, эта функция просто возвращает `m_pMainWnd` объекта приложения.  
  
 Если `AfxGetMainWnd` вызывается из основного потока приложения, он возвращает главное окно приложения в соответствии с приведенными выше правилами. Если функция вызывается из второго потока в приложении, функция возвращает главного окна связанного с потоком, в которой был сделан вызов.  
  
### <a name="remarks"></a>Примечания  
 Если приложение не является сервером OLE, то при вызове этой функции является эквивалентом непосредственно ссылается на `m_pMainWnd` членом объекта приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 Эта функция используется для определения, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра узла по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Примечания  
 Если включить перенаправление системного реестра, платформа перенаправляет доступ из **HKCR** для **HKEY_CURRENT_USER\Software\Classes**. Только платформы MFC и ATL, подвержены перенаправления.  
  
 Чтобы изменить перенаправляет ли приложение доступ к реестру, используйте [AfxSetPerUserRegistration](#afxsetperuserregistration).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxstat_.h    
  
##  <a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 Используйте `HINSTANCE` дескриптор, возвращаемый этой функцией, напрямую получать доступ к ресурсам приложения, например, в вызовах функции Windows **FindResource**.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HINSTANCE` Дескриптора, в котором загружаются по умолчанию ресурсы приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxgetthread"></a>AfxGetThread  
 Эта функция вызывается для получения указателя на [CWinThread](../../mfc/reference/cwinthread-class.md) объект, представляющий текущий выполняемый поток.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий выполняемый поток; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Должно вызываться из в нужный поток.  
  
> [!NOTE]
>  При переносе проекта MFC вызова `AfxGetThread` из Visual C++ версии 4.2, 5.0 или 6.0, `AfxGetThread` вызовы [AfxGetApp](#afxgetapp) Если найден ни один поток. В Visual c + .NET и более поздних версиях `AfxGetThread` возвращает **NULL** Если ни один поток не был найден. Если вы хотите потока приложения, необходимо вызвать метод `AfxGetApp`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxinitrichedit"></a>AfxInitRichEdit  
 Эта функция вызывается для инициализации элемента управления форматированным редактированием (версия 1.0) для приложения.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция предназначена для обеспечения обратной совместимости. Приложения, созданные с помощью Visual C++ .NET и последующего использования [AfxInitRichEdit2](#afxinitrichedit2).  
  
 `AfxInitRichEdit`Загружает RICHED32. Библиотеки DLL для инициализации версии 1.0 управления rich edit. Для использования версии 2.0 и 3.0 элемента управления rich edit, библиотеки RICHED20. Библиотека DLL должна быть загружена. Это достигается с помощью вызова [AfxInitRichEdit2](#afxinitrichedit2). Если ресурсы диалогового окна с помощью управления rich edit, созданные до Visual C++ .NET, элементы управления форматированным редактированием автоматически являются версии 1.0. Версия 2.0, элементов управления rich edit, вставленный с помощью редактора ресурсов Visual C++ .NET.  
  
 Чтобы обновить элементы управления форматированным редактированием в существующих приложениях Visual C++ до версии 2.0, откройте. RC-файле как текст, измените имя класса каждого управления rich edit из «RICHEDIT» на «RichEdit20a». Затем замените вызов `AfxInitRichEdit` с `AfxInitRichEdit2`.  
  
 Эта функция также инициализирует библиотеки общих элементов управления, если библиотека еще не уже инициализирован для процесса. Если используется элемент управления форматированием непосредственно из приложения MFC, следует вызывать эту функцию, чтобы гарантировать, что MFC инициализации среды выполнения элемента управления форматированным редактированием. Если вызвать метод Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется для вызова этой функции, но в некоторых случаях может возникнуть необходимость.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 Эта функция вызывается для инициализации элемента управления форматированным редактированием (версии 2.0 или более поздней версии) для приложения.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для загрузки библиотеки RICHED20. Библиотеки DLL и инициализируйте версии 2.0 широкий набор функций управления edit. Если вызвать метод Create [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), или [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), обычно не требуется для вызова этой функции, но в некоторых случаях может возникнуть необходимость.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  

  ## <a name="afxisextendedframeclass"></a>AfxIsExtendedFrameClass
Определяет, является ли заданное окно расширенным объектом фрейма.  
   
### <a name="syntax"></a>Синтаксис    
```  
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );  
```
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на объект, который является производным от `CWnd`.  
   
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если предоставленное окно является расширенным объектом фрейма; в противном случае `FALSE`.  
   
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `TRUE` , если `pWnd` является производным от одного из следующих классов:  
  
-   `CFrameWndEx`  
  
-   `CMDIFrameWndEx`  
  
-   `COleIPFrameWndEx`  
  
-   `COleDocIPFrameWndEx`  
  
-   `CMDIChildWndEx`  
  
 Этот метод полезен, когда требуется проверить, что параметр функции или метода является окном расширенного фрейма.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  
   
### <a name="see-also"></a>См. также  
 [CWnd-класс](cwnd-class.md)   
 [Класс CFrameWndEx](cframewndex-class.md)   

## <a name="afxismfctoolbar"></a>AfxIsMFCToolBar
Определяет, является ли заданное окно объект панели инструментов.  
   
### <a name="syntax"></a>Синтаксис    
```  
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);  
```
### <a name="parameters"></a>Параметры  
 [in] `pWnd`  
 Указатель на объект, который является производным от `CWnd`.  
   
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если предоставленное окно является объект панели инструментов; в противном случае `FALSE`.  
   
### <a name="remarks"></a>Примечания  
 Этот метод возвращает `TRUE` Если `pWnd` является производным от `CMFCToolBar`. Этот метод полезен, когда необходимо проверить, является ли параметр функции или метода `CMFCToolBar` объекта.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxpriv.h  
   
### <a name="see-also"></a>См. также  
 [CWnd-класс](cwnd-class.md)   
 [Класс CMFCToolBar](cmfctoolbar-class.md)

 
## <a name="afxkeyboardmanager"></a>AfxKeyboardManager
Указатель на глобальную [manager клавиатуры](ckeyboardmanager-class.md).  
   
### <a name="syntax"></a>Синтаксис    
```  
CKeyboardManager* afxKeyboardManager;  
```  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxkeyboardmanager.h  
   
### <a name="see-also"></a>См. также  

 [Макросы, глобальные функции и глобальные переменные](mfc-macros-and-globals.md)   
 [Класс CKeyboardManager](ckeyboardmanager-class.md)


##  <a name="afxloadlibrary"></a>AfxLoadLibrary  
 Используйте `AfxLoadLibrary` для сопоставления модуль DLL.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>Параметры  
 *lpszModuleName*  
 Указывает на строку, завершающуюся значением null, содержащее имя модуля (либо. Библиотеки DLL или. EXE-файла). Указанное имя является имя файла модуля.  
  
 Если строка указывает путь, но файл не существует в указанном каталоге, функция завершается с ошибкой.  
  
 Если путь не указан и указано расширение имени файла, расширение по умолчанию. Библиотека DLL будет добавлено. Однако строка имя файла может включать конечные символ точки (.) для указания, что имя модуля не имеет расширения. Если путь не указан, функция выполняет поиск файла в следующей последовательности:  
  
-   Каталог, из которого загружен приложения.  
  
-   Текущий каталог.  
  
- **Windows 95/98:** в системном каталоге Windows. **Windows NT:** системный каталог Windows 32-разрядной. Имя этого каталога хранится в папке SYSTEM32.  
  
- **Только для Windows NT:** 16-разрядной версии Windows системный каталог. Функции Win32, Получает путь этот каталог не существует, но он выполняется. Этот каталог называется системы.  
  
-   Каталог Windows.  
  
-   Каталоги, которые перечислены в переменной среды PATH.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращается дескриптор для модуля. Если функция завершается с ошибкой, возвращается значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Возвращает дескриптор, который может использоваться в [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) при получении адреса функции DLL. `AfxLoadLibrary`может также использоваться для сопоставления другие исполняемые модули.  
  
 Каждый процесс поддерживает счетчик ссылок для каждого модуля загрузить библиотеки. Этот счетчик увеличивается каждый раз `AfxLoadLibrary` вызывается и уменьшается на единицу при каждом `AfxFreeLibrary` вызывается. Когда число ссылок достигает нуля, модуль не сопоставляется с адресном пространстве вызывающего процесса и дескриптор недействителен.  
  
 Обязательно используйте `AfxLoadLibrary` и `AfxFreeLibrary` (вместо функций Win32 **LoadLibrary** и **FreeLibrary**) Если приложение использует несколько потоков и динамически загружает библиотеки DLL расширения. С помощью `AfxLoadLibrary` и `AfxFreeLibrary` гарантирует, что код запуска и завершения работы, который выполняется при загрузке и выгрузке библиотеки DLL расширения не приведет к повреждению глобального состояния MFC.  
  
 С помощью `AfxLoadLibrary` в приложении необходимо создать динамическую ссылку, чтобы версия библиотеки DLL MFC; файл заголовка для `AfxLoadLibrary`, Afxdll_.h, — только включенным, если связанный приложению в виде библиотеки DLL MFC. Это сделано намеренно, так как можно создать ссылку на версию библиотеки DLL MFC, позволяющий использовать или создать библиотека DLL-расширения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_DLLUser #1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser #2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser #3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdll_.h  
   
## <a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager
Указатель на глобальную [отделяемого меню диспетчер](cmenutearoffmanager-class.md).  
   
### <a name="syntax"></a>Синтаксис    
```  
CMenuTearOffManager* g_pTearOffMenuManager;  
```  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmenutearoffmanager.h  
   
### <a name="see-also"></a>См. также     
 [Класс CMenuTearOffManager](cmenutearoffmanager-class.md)
 
## <a name="afxmousemanager"></a>AfxMouseManager
Указатель на глобальную [мыши manager](cmousemanager-class.md).  
   
### <a name="syntax"></a>Синтаксис  
  ```  
CMouseManager* afxMouseManager;  
```  
### <a name="requirements"></a>Требования  
 **Заголовок:** afxmousemanager.h  
   
### <a name="see-also"></a>См. также  
 [Класс CMouseManager](cmousemanager-class.md)
 

  
##  <a name="afxregisterclass"></a>AfxRegisterClass  
 Эту функцию можно используйте для регистрации классов окон в библиотеке DLL, которое использует MFC.  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>Параметры  
 *lpWndClass*  
 Указатель на [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуру, содержащую сведения о классе окно для регистрации. Дополнительные сведения о структуре см. в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если класс является успешно зарегистрирован; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 При использовании этой функции, класса автоматически отменяется, при выгрузке библиотеки DLL.  
  
 В построениях, не Входящего в `AfxRegisterClass` идентификатор представляет собой макрос, который сопоставляется с функцией Windows **RegisterClass**, так как классы, зарегистрированные в приложении отменяется автоматически. Если вы используете `AfxRegisterClass` вместо **RegisterClass**, код можно использовать без изменений в приложении и в библиотеке DLL.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_DLL #3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass  
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
 Задает стиль класса Windows или сочетание стили, созданные с помощью побитового или ( **|**) оператора для класса окна. Список стилей класса см. в разделе [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) структуры в Windows SDK. Если **NULL**, значения по умолчанию будет задаваться следующим образом:  
  
-   Задает стиль мыши **CS_DBLCLKS**, которая отправляет дважды щелкните сообщения в процедуру при двойном щелчке мыши.  
  
-   Задает стиль стрелки курсоров стандарта Windows **IDC_ARROW**.  
  
-   Задает кисть фона **NULL**, поэтому не удалит его фона окна.  
  
-   Задает значок для стандартных, нетерпеливых флаг значок эмблемы Windows.  
  
 `hCursor`  
 Указывает дескриптор ресурса курсор, устанавливаемые в каждом окне, созданные на основе класса окна. Если используется значение по умолчанию для **0**, вы получите стандартной **IDC_ARROW** курсора.  
  
 *hbrBackground*  
 Указывает дескриптор ресурса кисти, устанавливаемые в каждом окне, созданные на основе класса окна. Если используется значение по умолчанию для **0**, будет иметь **NULL** кисть фона, а также на окно будет, по умолчанию не удаляют его фона при обработке [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  
  
 `hIcon`  
 Указывает дескриптор ресурс значка, устанавливаемые в каждом окне, созданные на основе класса окна. Если используется значение по умолчанию для **0**, появится значок эмблемы Windows стандартные, нетерпеливых флаг.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нулем строка, содержащая имя класса. Можно передать имя класса для **создать** функции-члена `CWnd` или других **CWnd -**производные классы для создания окна. Имя создается путем библиотеки классов Microsoft Foundation.  
  
> [!NOTE]
>  Возвращаемое значение является указателем на статический буфер. Чтобы сохранить эту строку, назначьте его `CString` переменной.  
  
### <a name="remarks"></a>Примечания  
 Библиотеки классов Microsoft Foundation автоматически регистрирует несколько классов стандартного окна. Эта функция вызывается в том случае, если вы хотите зарегистрировать свои собственные классы окон.  
  
 Имя, зарегистрированное для класса `AfxRegisterWndClass` исключительно зависит от параметров. При вызове метода `AfxRegisterWndClass` несколько раз с идентичными параметрами регистрируются только при первом вызове класс. Последующие вызовы `AfxRegisterWndClass` с идентичными параметрами просто возвращают classname уже зарегистрирован.  
  
 При вызове метода `AfxRegisterWndClass` для нескольких классах, производных от CWnd с идентичными параметрами, вместо класса отдельное окно для каждого класса, каждый класс использует один класс. Это может вызвать проблемы, если **CS_CLASSDC** используется стиль класса. Вместо нескольких **CS_CLASSDC** классы окон, вы получаете один **CS_CLASSDC** класс окна и всех windows на C++, использующих, что класс совместного использования одного контроллера домена. Чтобы избежать этой проблемы, вызовите [AfxRegisterClass](#afxregisterclass) для регистрации класса.  
  
 Ссылаться на техническое Примечание [TN001: регистрация класса Window](../../mfc/tn001-window-class-registration.md) Дополнительные сведения о регистрации класса окна и `AfxRegisterWndClass` функции.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
  
##  <a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 Задает, перенаправляет ли приложение доступ к реестру на **HKEY_CURRENT_USER** ( **HKCU**) узла.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Указывает, что данные реестра, направляются **HKCU** узла; `FALSE` указывает, что приложение записывает данные реестра узла по умолчанию. Узел по умолчанию является **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Примечания  
 Прежде чем [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], приложения, доступ к реестру, обычно используют **HKEY_CLASSES_ROOT** узла. Однако в [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], необходимо запустить приложение в режиме с повышенными правами на запись в **HKCR**.  
  
 Этот метод позволяет вашему приложению для чтения и записи в реестр без запуска в режиме с повышенными правами, перенаправляя доступ к реестру из **HKCR** для **HKCU**. Дополнительные сведения см. в разделе [страницы свойств компоновщика](../../ide/linker-property-pages.md).  
  
 Если включить перенаправление системного реестра, платформа перенаправляет доступ из **HKCR** для **HKEY_CURRENT_USER\Software\Classes**. Только платформы MFC и ATL, подвержены перенаправления.  
  
 Реализация по умолчанию обращается к в раздел реестра **HKCR**.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxstat_.h    
  
##  <a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 Эта функция позволяет задать `HINSTANCE` дескриптор, который определяет, где загружаются по умолчанию ресурсы приложения.  
  
```  
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>Параметры  
 `hInstResource`  
 Дескриптор экземпляра или модуля. Файл EXE или DLL, из которого загружаются ресурсы приложения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing #135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  

## <a name="afxshellmanager"></a>AfxShellManager
Указатель на глобальную [диспетчер оболочки](cshellmanager-class.md).  
   
### <a name="syntax"></a>Синтаксис    
```  
CShellManager* afxShellManager;  
```  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxshellmanager.h  
   
### <a name="see-also"></a>См. также  
 [Класс CShellManager](cshellmanager-class.md)
  
##  <a name="afxsocketinit"></a>AfxSocketInit  
 Вызовите эту функцию в вашей `CWinApp::InitInstance` переопределение, чтобы инициализировать Windows Sockets.  
  
```  
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 `lpwsaData`  
 Указатель на [WSADATA](../../mfc/reference/wsadata-structure.md) структуры. Если `lpwsaData` не равно `NULL`, затем адрес `WSADATA` структура заполняется путем вызова метода `WSAStartup`. Эта функция также гарантирует, что `WSACleanup` вызывается автоматически перед завершением работы приложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 При использовании сокетов второстепенных потоков в приложении MFC статически скомпонованной MFC, необходимо вызвать метод `AfxSocketInit` в каждый поток, который использует сокеты для инициализации библиотеки сокета. По умолчанию `AfxSocketInit` вызывается только в основном потоке.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxsock.h  

## <a name="afxusertoolsmanager"></a>AfxUserToolsManager
Указатель на глобальную [средства диспетчера пользователей](cusertoolsmanager-class.md).  
   
### <a name="syntax"></a>Синтаксис    
```  
CUserToolsManager* afxUserToolsManager;  
```  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxusertoolsmanager.h  
   
### <a name="see-also"></a>См. также  
 [Класс CUserToolsManager](cusertoolsmanager-class.md)
 
  
##  <a name="afxwininit"></a>AfxWinInit  
 Эта функция вызывается с библиотека MFC предоставляет `WinMain` функции как часть [CWinApp](../../mfc/reference/cwinapp-class.md) инициализации Графическим пользовательским интерфейсом приложения для инициализации MFC.  
  
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
 Дескриптор предыдущий экземпляр приложения. Для приложения на основе Win32, этот параметр всегда является **NULL**.  
  
 `lpCmdLine`  
 Точки в строку, завершающуюся значением null, указание командной строки для приложения.  
  
 `nCmdShow`  
 Указывает, как отображается в главном окне графического пользовательского интерфейса приложения.  
  
### <a name="remarks"></a>Примечания  
 Для консольного приложения, который не используется библиотека MFC предоставляет `WinMain` функции, необходимо вызвать метод `AfxWinInit` непосредственно для инициализации MFC.  
  
 При вызове метода `AfxWinInit` самостоятельно, необходимо объявить экземпляр `CWinApp` класса. Для консольного приложения, вы можете не являются производными класса из `CWinApp` и вместо этого используйте экземпляр `CWinApp` напрямую. Этот способ подходит, если вы решили оставить все функциональные возможности для вашего приложения в собственной реализации функции **основной**.  
  
> [!NOTE]
>  При создании контекста активации для сборки, MFC использует ресурса манифеста, предоставляемый модулем пользователя. Контекст активации по умолчанию создается в `AfxWinInit`. Дополнительные сведения см. в разделе [поддержка контекстов активации в состоянии модуля MFC](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFC_AfxWinInit #1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxwin.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [Класс CWinApp](../../mfc/reference/cwinapp-class.md)

