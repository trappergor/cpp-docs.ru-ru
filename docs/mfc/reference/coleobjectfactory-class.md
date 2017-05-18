---
title: "COleObjectFactory-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
dev_langs:
- C++
helpviewer_keywords:
- OLE, class factory
- OLE class factory
- COleObjectFactory class
- objects [C++], creating OLE
- OLE objects
- object creation, OLE objects
- class factories, COleObjectFactory class
- OLE objects, creating
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 643d17ccdefb60b561e7e5488753a6dbf778c69f
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coleobjectfactory-class"></a>COleObjectFactory-класс
Реализует фабрику класса OLE, которая создает OLE-объекты, такие как серверы, объекты автоматизации и документы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Создает объект `COleObjectFactory`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|КОД объектов, создаваемых этой фабрики класса возвращает OLE.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Определяет, является ли допустимым лицензии элемента управления.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Указывает, регистрируется ли фабрику объектов OLE системные библиотеки DLL.|  
|[Команда COleObjectFactory::Register](#register)|Регистрирует данную фабрику объектов OLE системные библиотеки DLL.|  
|[COleObjectFactory::RegisterAll](#registerall)|Регистрирует все фабрики приложения объекта OLE системные библиотеки DLL.|  
|[COleObjectFactory::Revoke](#revoke)|Отменяет регистрацию фабрику объектов OLE системные библиотеки DLL.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Отменяет регистрации фабрики объект приложения с OLE системные библиотеки DLL.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|Отменяет регистрацию всех фабрик объектов приложения.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Регистрирует данную фабрику объектов OLE системного реестра.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Регистрирует все фабрики объект приложения в системном реестре OLE.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Уникальный ключ запросов из библиотеки DLL элемента управления.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Вызывается платформой для создания нового объекта типа для этой фабрики.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Проверяет соответствие ключа, встроенного в контейнере ключа, встроенного в элементе управления.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Проверяет, что элемент управления лицензирован для использования во время разработки.|  
  
## <a name="remarks"></a>Примечания  
 `COleObjectFactory` Класс содержит функции-члены для выполнения следующих функций:  
  
-   Управление регистрацией объектов.  
  
-   Обновление регистрации системы OLE, а также регистрации во время выполнения, что объекты работают и Готово к получению сообщения, информирующего о OLE.  
  
-   Применение лицензирования, ограничивая использование элемента управления для лицензированных разработчики во время разработки и лицензированные приложения во время выполнения.  
  
-   Регистрация фабрик объектов управления в системном реестре OLE.  
  
 Дополнительные сведения о создании объекта см. в статьях [объектов данных и источников данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md) и [объекты и источники данных: Создание и уничтожение](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Дополнительные сведения о регистрации, см. в статье [регистрации](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>COleObjectFactory::COleObjectFactory  
 Создает `COleObjectFactory` объекта, инициализирует его в виде незарегистрированные объект фабрики и добавляет его в список фабрик.  
  
```  
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    LPCTSTR lpszProgID);

 
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    int nFlags,  
    LPCTSTR lpszProgID);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Ссылка на идентификатор класса OLE, который представляет этот объект фабрики.  
  
 `pRuntimeClass`  
 Указатель на класс времени выполнения объектов C++, созданные данной фабрикой.  
  
 `bMultiInstance`  
 Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Если **TRUE**, для каждого запроса создать объект запускаются несколько экземпляров приложения.  
  
 `nFlags`  
 Содержит один или несколько из следующих флагов:  
  
- **afxRegDefault** задает модель потоков для ThreadingModel = подразделения.  
  
- **afxRegInsertable** позволяет элементу управления в **вставить объект** диалоговое окно для OLE-объекты.  
  
- `afxRegApartmentThreading`Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
- **afxRegFreeThreading** задает модель потоков в реестре, ThreadingModel = Free.  
  
     Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` для задания ThreadingModel = Both. В разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Дополнительные сведения о потоковой модели регистрации.  
  
 `lpszProgID`  
 Указатель на строку, содержащую идентификатор устные программы, например «Microsoft Excel».  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать объект, тем не менее, необходимо зарегистрировать его.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclassid"></a>COleObjectFactory::GetClassID  
 Возвращает ссылку на идентификатор класса OLE, представляющий этой фабрики.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представляет ссылку на идентификатор класса OLE этой фабрики.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlicensekey"></a>COleObjectFactory::GetLicenseKey  
 Запрашивает уникальное лицензионный ключ из элемента управления DLL и сохраняет его в `BSTR` указывает `pbstrKey`.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 Зарезервировано для будущего использования.  
  
 `pbstrKey`  
 Указатель на `BSTR` , будут храниться лицензионный ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка лицензионный ключ не **NULL**; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция возвращает значение 0 и значение Nothing в `BSTR`. При использовании MFC ActiveX автоматически при создании проекта автоматически предоставляет переопределение, которое извлекает ключ лицензии для элемента управления.  
  
##  <a name="islicensevalid"></a>COleObjectFactory::IsLicenseValid  
 Определяет, является ли допустимым лицензии элемента управления.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если successul; в противном случае — значение false.  
  
##  <a name="isregistered"></a>COleObjectFactory::IsRegistered  
 Возвращает ненулевое значение, если фабрика зарегистрирован OLE системные библиотеки DLL.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика зарегистрирована; в противном случае — 0.  
  
##  <a name="oncreateobject"></a>COleObjectFactory::OnCreateObject  
 Вызывается платформой для создания нового объекта.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на созданный объект. Она может вызвать исключение памяти в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для создания объекта из-за отличных от [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) передано в конструктор.  
  
##  <a name="register"></a>Команда COleObjectFactory::Register  
 Регистрирует данную фабрику объектов OLE системные библиотеки DLL.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика успешно зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="registerall"></a>COleObjectFactory::RegisterAll  
 Регистрирует все фабрики приложения объекта OLE системные библиотеки DLL.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрик успешно зарегистрировано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="revoke"></a>COleObjectFactory::Revoke  
 Отменяет регистрацию фабрику объектов OLE системные библиотеки DLL.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа автоматически вызывает данную функцию, прежде чем приложение завершит работу. При необходимости вызывать его из переопределения события [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>COleObjectFactory::RevokeAll  
 Отменяет все регистрации приложения объект фабрики с OLE системные библиотеки DLL.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа автоматически вызывает данную функцию, прежде чем приложение завершит работу. При необходимости вызывать его из переопределения события [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>COleObjectFactory::UnregisterAll  
 Отменяет регистрацию всех фабрик объектов приложения.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
##  <a name="updateregistry"></a>COleObjectFactory::UpdateRegistry  
 Регистрирует все фабрики объект приложения в системном реестре OLE.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProgID`  
 Указатель на строку, содержащую идентификатор восприятия программы, например «Excel.Document.5.»  
  
 `bRegister`  
 Определяет, является ли объект фабрики класса элемента управления должна быть зарегистрирована.  
  
### <a name="remarks"></a>Примечания  
 Выполните краткое обсуждение две формы для этой функции.  
  
- **UpdateRegistry (** `lpszProgID` **)** регистрирует фабрику этот объект в системном реестре OLE. Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
- **UpdateRegistry (** `bRegister` **)** overridable эту форму функции. Если `bRegister` — **TRUE**, эта функция регистрирует класс элемента управления в системном реестре. В противном случае — отменяет регистрацию класса.  
  
     При использовании MFC ActiveX автоматически при создании проекта автоматически предоставляет переопределение, чтобы это чисто виртуальную функцию.  
  
##  <a name="updateregistryall"></a>COleObjectFactory::UpdateRegistryAll  
 Регистрирует все фабрики объект приложения в системном реестре OLE.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegister`  
 Определяет, является ли объект фабрики класса элемента управления должна быть зарегистрирована.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрик успешно обновлены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="verifylicensekey"></a>COleObjectFactory::VerifyLicenseKey  
 Проверяет, что контейнер поставляется с лицензией на использование элемента управления OLE.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrKey`  
 A `BSTR` хранения контейнера версию строки лицензии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если лицензия времени выполнения является допустимым; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Версия по умолчанию вызывает [GetLicenseKey](#getlicensekey) для получения копии элемента управления, строка лицензии и сравнивает его со строкой в `bstrKey`. Если две строки совпадают, функция возвращает ненулевое значение; в противном случае она возвращает 0.  
  
 Можно переопределить эту функцию для проверки настроенного лицензии.  
  
 Функция [VerifyUserLicense](#verifyuserlicense) проверяет лицензию во время разработки.  
  
##  <a name="verifyuserlicense"></a>COleObjectFactory::VerifyUserLicense  
 Проверка лицензий во время разработки для элемента управления OLE.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если во время разработки лицензия действительна; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)

