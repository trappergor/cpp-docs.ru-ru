---
title: "Класс CAtlExeModuleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlExeModuleT<T>
- CAtlExeModuleT
- ATL.CAtlExeModuleT<T>
- ATL::CAtlExeModuleT
- ATL.CAtlExeModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 24ee6c4dfb13c31377bdd7d4f57a92d4f11ad4b8
ms.lasthandoff: 02/24/2017

---
# <a name="catlexemodulet-class"></a>Класс CAtlExeModuleT
Этот класс представляет модуль для приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Ваш класс, производный от `CAtlExeModuleT`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Конструктор.|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](#initializecom)|Инициализирует COM.|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Анализирует командную строку и выполняет регистрацию, при необходимости.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Этот метод вызывается сразу после выхода из цикла обработки сообщений.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается сразу перед вводом в цикл обработки сообщений.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса.|  
|[CAtlExeModuleT::Run](#run)|Этот метод выполняет код в модуль EXE для инициализации, запустить цикл обработки сообщений и очистки.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Этот метод выполняется цикл обработки сообщений.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Отменяет инициализацию объекта COM.|  
|[CAtlExeModuleT::Unlock](#unlock)|Уменьшает счетчик блокировки модуля.|  
|[CAtlExeModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для выполнения exe-файла.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Флаг, указывающий, что должно быть задержки, завершение работы модуля.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Приостановка значение используется, чтобы убедиться, что все объекты освобождаются перед завершением работы.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Значение времени ожидания, чтобы задержать выгрузки модуля.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlExeModuleT`Представляет модуль для приложения (EXE) и содержит код, который поддерживает создание exe-файла, обработки командной строки, регистрацию объектов класса, запускает цикл сообщений и очистки при выходе.  
  
 Этот класс предназначен для повышения производительности при COM-объектов в EXE-сервер постоянно создаются и уничтожаются. После выхода последнего объекта COM, exe-ФАЙЛ ожидает время, определяемое [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) данные-член. Если нет никаких действий в течение этого периода (то есть не COM создаются объекты), инициируется процесс завершения работы.  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) член данных — флаг, используемый для определения, если exe-ФАЙЛ должен использовать механизм, определенный выше. Если он имеет значение false, модуль прерывается немедленно.  
  
 Дополнительные сведения о модулях в ATL см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-namecatlexemoduleta--catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 Конструктор.  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Если не удалось инициализировать модуль EXE, WinMain немедленно вернет без дальнейшей обработки.  
  
##  <a name="a-namedtora--catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 Деструктор  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-nameinitializecoma--catlexemoduletinitializecom"></a><a name="initializecom"></a>CAtlExeModuleT::InitializeCom  
 Инициализирует COM.  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается из конструктора и может быть переопределен для инициализации COM образом отличается от реализации по умолчанию. Реализация по умолчанию либо вызывает **CoInitializeEx (NULL, COINIT_MULTITHREADED)** или **CoInitialize(NULL)** в зависимости от конфигурации проекта.  
  
 Переопределение этого метода обычно требуется переопределение [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="a-namembdelayshutdowna--catlexemoduletmbdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 Флаг, указывающий, что должно быть задержки, завершение работы модуля.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) подробные сведения.  
  
##  <a name="a-namemdwpausea--catlexemoduletmdwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 Приостановка значение используется, чтобы убедиться, что все объекты прошли перед завершением работы.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Примечания  
 Это значение можно изменить после вызова метода [CAtlExeModuleT::InitializeCom](#initializecom) для установки используется как значение паузы для завершения работы сервера в миллисекундах. Значение по умолчанию — 1000 миллисекунд.  
  
##  <a name="a-namemdwtimeouta--catlexemoduletmdwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 Значение времени ожидания, чтобы задержать выгрузки модуля.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Примечания  
 Это значение можно изменить после вызова метода [CAtlExeModuleT::InitializeCom](#initializecom) определить число миллисекунд, используется как значение времени ожидания для завершения работы сервера. Значение по умолчанию — 5000 миллисекунд. В разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) подробнее.  
  
##  <a name="a-nameparsecommandlinea--catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 Анализирует командную строку и выполняет регистрацию, при необходимости.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpCmdLine`  
 В командной строке, передаются приложению.  
  
 `pnRetCode`  
 Значение HRESULT, соответствующее регистрации (если она выполнялась).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если приложение следует продолжить выполнение, в противном случае — false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается из [CAtlExeModuleT::WinMain](#winmain) и может быть переопределен для обработки командной строки. Реализация по умолчанию проверяет наличие **/regserver** и **/UnRegServer** аргументы командной строки и выполняет регистрации или отмены регистрации.  
  
##  <a name="a-namepostmessageloopa--catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 Этот метод вызывается сразу после выхода из цикла обработки сообщений.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы выполнить очистку пользовательского приложения. Реализация по умолчанию вызывает [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="a-namepremessageloopa--catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 Этот метод вызывается сразу перед вводом в цикл обработки сообщений.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Значение, передаваемое как `nShowCmd` параметр в WinMain.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы добавить пользовательский код инициализации для приложения. Реализация по умолчанию регистрирует объекты класса.  
  
##  <a name="a-nameregisterclassobjectsa--catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 Регистрирует объект класса OLE, другие приложения для подключения к нему.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwClsContext*  
 Указывает контекст, в котором будет выполняться объекта класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER.  
  
 `dwFlags`  
 Определяет типы подключения к объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех, S_FALSE, если нет классов, чтобы зарегистрировать или HRESULT ошибки в случае сбоя.  
  
##  <a name="a-namerevokeclassobjectsa--catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>CAtlExeModuleT::RevokeClassObjects  
 Удаляет объект класса.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех, S_FALSE, если нет классов, чтобы зарегистрировать или HRESULT ошибки в случае сбоя.  
  
##  <a name="a-nameruna--catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT::Run  
 Этот метод выполняет код в модуль EXE для инициализации, запустить цикл обработки сообщений и очистки.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздел. По умолчанию SW_HIDE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен. Однако на практике лучше переопределить [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), или [CAtlExeModuleT::PostMessageLoop](#postmessageloop) вместо.  
  
##  <a name="a-namerunmessageloopa--catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 Этот метод выполняется цикл обработки сообщений.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно переопределить для изменения поведения в цикл обработки сообщений.  
  
##  <a name="a-nameuninitializecoma--catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 Отменяет инициализацию объекта COM.  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывает [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) и вызывается из деструктора. Переопределите этот метод, если необходимо переопределить [CAtlExeModuleT::InitializeCom](#initializecom).  
  
##  <a name="a-nameunlocka--catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT::Unlock  
 Уменьшает счетчик блокировки модуля.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="a-namewinmaina--catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT::WinMain  
 Этот метод реализует код, необходимый для выполнения exe-файла.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздел.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает возвращаемое значение исполняемый файл.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен. При переопределении метода [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), или [CAtlExeModuleT::RunMessageLoop](#runmessageloop) не обеспечивает достаточную гибкость, можно переопределить `WinMain` функции с помощью этого метода.  
  
## <a name="see-also"></a>См. также  
 [Образец ATLDuck](../../visual-cpp-samples.md)   
 [Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)   
 [Класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

