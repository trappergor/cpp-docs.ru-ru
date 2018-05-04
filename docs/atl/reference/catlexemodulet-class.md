---
title: Класс CAtlExeModuleT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22510da8c1377411b289b940e1b8e196533c93a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|Конструктор.|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::InitializeCom](#initializecom)|Инициализирует COM.|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|Этот метод вызывается сразу после выхода из цикла обработки сообщений.|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|Этот метод вызывается сразу перед вводом в цикл обработки сообщений.|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|Регистрирует объект класса.|  
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|Отменяет объекта класса.|  
|[CAtlExeModuleT::Run](#run)|Этот метод выполняет код в модуле exe-файла для инициализации, запустить цикл обработки сообщений и очистки.|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|Этот метод выполняет цикл обработки сообщений.|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|Отменяет инициализацию COM.|  
|[CAtlExeModuleT::Unlock](#unlock)|Уменьшает счетчик блокировки модуля.|  
|[CAtlExeModuleT::WinMain](#winmain)|Этот метод реализует код, необходимый для запуска файла EXE.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|Флаг, указывающий, что должно быть задержки, завершение работы модуля.|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|Приостановка значение, используемое для убедитесь, что все объекты освобождаются перед завершением работы.|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|Значение времени ожидания, чтобы задержать выгрузки модуля.|  
  
## <a name="remarks"></a>Примечания  
 `CAtlExeModuleT` Представляет модуль для приложения (EXE) и содержит код, который поддерживает создание exe-файла, обработки командной строки, регистрация класса объектов, запускает цикл сообщений и очистка при выходе.  
  
 Этот класс предназначен для повышения производительности при COM-объекты в EXE-сервер постоянно создаются и удаляются. После выпуска последнего объекта COM, EXE-файла, ожидает в течение периода времени, заданные [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) члена данных. Если в течение этого периода неактивности (то есть не COM-объекты создаются), инициируется процесс завершения работы.  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) член данных — флаг, используемый для определения, если исполняемый ФАЙЛ следует использовать механизм, определенный выше. Если свойство имеет значение false, модуль прерывается немедленно.  
  
 Дополнительные сведения о модулях в ATL см. в разделе [модульные классы ATL](../../atl/atl-module-classes.md).  
  
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
 Если не удалось инициализировать модуль EXE, WinMain немедленно вернет без дополнительной обработки.  
  
##  <a name="dtor"></a>  CAtlExeModuleT:: ~ CAtlExeModuleT  
 Деструктор  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="initializecom"></a>  CAtlExeModuleT::InitializeCom  
 Инициализирует COM.  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается из конструктора и его можно переопределить, чтобы инициализировать COM образом отличается от реализации по умолчанию. Реализация по умолчанию либо вызывает **CoInitializeEx (значение NULL, COINIT_MULTITHREADED)** или **CoInitialize(NULL)** в зависимости от конфигурации проекта.  
  
 Переопределение этого метода обычно требуется переопределение [CAtlExeModuleT::UninitializeCom](#uninitializecom).  
  
##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown  
 Флаг, указывающий, что должно быть задержки, завершение работы модуля.  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) подробные сведения.  
  
##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause  
 Приостановка значение, используемое для убедитесь, что все объекты являются прошли перед завершением работы.  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>Примечания  
 Изменить это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) для установки количества миллисекунд, используется как значение паузы для завершения работы сервера. Значение по умолчанию — 1 000 миллисекунд.  
  
##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut  
 Значение времени ожидания, чтобы задержать выгрузки модуля.  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>Примечания  
 Изменить это значение после вызова [CAtlExeModuleT::InitializeCom](#initializecom) определить число миллисекунд, используется как значение времени ожидания для завершения работы сервера. Значение по умолчанию — 5000 миллисекунд. В разделе [CAtlExeModuleT Обзор](../../atl/reference/catlexemodulet-class.md) для получения дополнительных сведений.  
  
##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine  
 Выполняет синтаксический анализ командной строки и при необходимости выполняет регистрацию.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpCmdLine`  
 Из командной строки, передаваемые в приложение.  
  
 `pnRetCode`  
 Значение HRESULT, соответствующее регистрации (если она выполнялась).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если приложения должны продолжать работу, в противном случае — значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается из [CAtlExeModuleT::WinMain](#winmain) и может быть переопределен для обработки параметров командной строки. Реализация по умолчанию проверяет наличие **/regserver** и **/unregserver** аргументы командной строки и выполняет регистрации или отмены регистрации.  
  
##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop  
 Этот метод вызывается сразу после выхода из цикла обработки сообщений.  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для выполнения очистки пользовательское приложение. Реализация по умолчанию вызывает [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects).  
  
##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop  
 Этот метод вызывается сразу перед вводом в цикл обработки сообщений.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Значение, переданное в качестве `nShowCmd` параметр в WinMain.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, чтобы добавить пользовательский код инициализации для приложения. Реализация по умолчанию регистрирует объекты класса.  
  
##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects  
 Регистрирует объект класса с OLE, чтобы другие приложения могли подключиться к нему.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *dwClsContext*  
 Указывает контекст, в котором будет выполняться объекта класса. Возможные значения: CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER или CLSCTX_LOCAL_SERVER.  
  
 `dwFlags`  
 Определяет типы подключения к такому объекту класса. Возможные значения: REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE или REGCLS_MULTI_SEPARATE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех, S_FALSE, если бы не классы для регистрации или ошибку HRESULT при сбое.  
  
##  <a name="revokeclassobjects"></a>  CAtlExeModuleT::RevokeClassObjects  
 Удаляет объект класса.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех, S_FALSE, если бы не классы для регистрации или ошибку HRESULT при сбое.  
  
##  <a name="run"></a>  CAtlExeModuleT::Run  
 Этот метод выполняет код в модуле exe-файла для инициализации, запустить цикл обработки сообщений и очистки.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздела. Значение по умолчанию SW_HIDE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен. Однако на практике это лучше для переопределения [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](#runmessageloop), или [CAtlExeModuleT::PostMessageLoop](#postmessageloop) Вместо этого.  
  
##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop  
 Этот метод выполняет цикл обработки сообщений.  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен для изменения поведения в цикл обработки сообщений.  
  
##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom  
 Отменяет инициализацию COM.  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот метод вызывает [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) и вызывается из деструктора. Переопределите этот метод, если необходимо переопределить [CAtlExeModuleT::InitializeCom](#initializecom).  
  
##  <a name="unlock"></a>  CAtlExeModuleT::Unlock  
 Уменьшает счетчик блокировки модуля.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, которое могут быть полезны для диагностики и тестирования.  
  
##  <a name="winmain"></a>  CAtlExeModuleT::WinMain  
 Этот метод реализует код, необходимый для запуска файла EXE.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nShowCmd`  
 Указывает, как будет отображаться окно. Этот параметр может иметь одно из значений, описанных в [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) раздела.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает возвращаемое значение исполняемый файл.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть переопределен. При переопределении метода [CAtlExeModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::PostMessageLoop](#postmessageloop), или [CAtlExeModuleT::RunMessageLoop](#runmessageloop) не обеспечивает достаточную гибкость , можно переопределить `WinMain` функции с помощью этого метода.  
  
## <a name="see-also"></a>См. также  
 [Образец ATLDuck](../../visual-cpp-samples.md)   
 [Класс CAtlModuleT](../../atl/reference/catlmodulet-class.md)   
 [Класс CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
