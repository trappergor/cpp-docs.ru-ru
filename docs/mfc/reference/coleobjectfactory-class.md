---
title: COleObjectFactory-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd68493c9be5eb0bff63504cf49b38b9a2f216d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory-класс
Реализует фабрику класса OLE, которая создает OLE-объекты, такие как серверы, объекты автоматизации и документы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Создает объект `COleObjectFactory`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|КОД объектов, создаваемых данной фабрикой класса возвращает OLE.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Определяет, является ли допустимым лицензии элемента управления.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Указывает, регистрируется ли фабрику объектов OLE системные библиотеки DLL.|  
|[COleObjectFactory::Register](#register)|Регистрирует это фабрику объектов OLE системные библиотеки DLL.|  
|[COleObjectFactory::RegisterAll](#registerall)|Регистрирует все фабрики приложения объект OLE системные библиотеки DLL.|  
|[COleObjectFactory::Revoke](#revoke)|Отменяет регистрацию фабрику объектов с OLE системные библиотеки DLL.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Отменяет регистрации фабрики объект приложения с OLE системные библиотеки DLL.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|Отменяет регистрацию всех фабрик объект приложения.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Регистрирует фабрику этот объект в системном реестре OLE.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|Регистрирует все приложения объект фабрики в системном реестре OLE.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Запрашивает уникальный ключ из библиотеки DLL элемента управления.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Вызывается платформой для создания нового объекта типа для этой фабрики.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Ключ, внедренный в элемент управления проверяет, соответствует ли ключ, внедренных в контейнере.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Проверяет, что элемент управления лицензирован для использования во время разработки.|  
  
## <a name="remarks"></a>Примечания  
 `COleObjectFactory` Класс содержит функции-члены для выполнения следующих функций:  
  
-   Управление объектов регистрации.  
  
-   Обновление регистрации системы OLE, а также во время выполнения регистрации, информирующие OLE, что объекты, запущены и Готово к получению сообщения.  
  
-   Применение лицензирования путем ограничения использования элемента управления для разработчиков, лицензированных во время разработки и лицензированные приложения во время выполнения.  
  
-   Регистрация элемента управления объект фабрики в системном реестре OLE.  
  
 Дополнительные сведения о создании объекта см. в статьях [объектов данных и источники данных (OLE)](../../mfc/data-objects-and-data-sources-ole.md) и [объекты и источники данных: Создание и уничтожение](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Дополнительные сведения о регистрации см. в статье [регистрации](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 Создает `COleObjectFactory` объекта, инициализирует его как фабрику объектов незарегистрированные и добавляет его в список фабрик.  
  
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
 Указатель на класс среды выполнения объектов C++, которые могут быть созданы данной фабрикой.  
  
 `bMultiInstance`  
 Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Если **TRUE**, запуск нескольких экземпляров приложения для каждого запроса для создания объекта.  
  
 `nFlags`  
 Содержит один или несколько из следующих флагов:  
  
- **afxRegDefault** задает потоковую модель ThreadingModel = подразделения.  
  
- **afxRegInsertable** позволяет элементу управления отображаются в **вставить объект** диалоговое окно для OLE-объекты.  
  
- `afxRegApartmentThreading` Задает модель потоков в реестре, ThreadingModel = подразделения.  
  
- **afxRegFreeThreading** задает потоковую модель в реестре, ThreadingModel = Free.  
  
     Можно объединить два флага `afxRegApartmentThreading` и `afxRegFreeThreading` для задания ThreadingModel = Both. В разделе [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) в Windows SDK, Дополнительные сведения о потоковой модели регистрации.  
  
 `lpszProgID`  
 Указатель на строку, содержащую идентификатор устные программа, например «Microsoft Excel».  
  
### <a name="remarks"></a>Примечания  
 Чтобы использовать объект, тем не менее, необходимо зарегистрировать его.  
  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в Windows SDK.  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 Возвращает ссылку на идентификатор класса OLE, который представляет этой фабрики.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Представляет ссылку на идентификатор класса OLE этой фабрики.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в Windows SDK.  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 Запрашивает уникальное лицензионный ключ из библиотеки DLL элемента управления и сохраняет его в `BSTR` , на который указывает `pbstrKey`.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 Зарезервировано для будущего использования.  
  
 `pbstrKey`  
 Указатель на `BSTR` , будет хранить лицензионный ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка лицензионный ключ не **NULL**; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция возвращает значение 0 и имеет значение Nothing в `BSTR`. При использовании автоматически ActiveX MFC для создания проекта автоматически предоставляет переопределения, которое извлекает ключ лицензии для элемента управления.  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 Определяет, является ли допустимым лицензии элемента управления.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если successul; в противном случае — значение false.  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 Возвращает ненулевое значение, если фабрика зарегистрирован OLE системные библиотеки DLL.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика зарегистрирована; в противном случае — 0.  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 Вызывается платформой для создания нового объекта.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на созданный объект. В случае неудачи выбрасывает исключение памяти.  
  
### <a name="remarks"></a>Примечания  
 Переопределить эту функцию для создания объекта из что-то отличное от [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) передается конструктору.  
  
##  <a name="register"></a>  COleObjectFactory::Register  
 Регистрирует это фабрику объектов OLE системные библиотеки DLL.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрика успешно зарегистрирована; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается методом [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 Регистрирует все фабрики приложения объект OLE системные библиотеки DLL.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрик успешной регистрации; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается методом [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="revoke"></a>  COleObjectFactory::Revoke  
 Отменяет регистрацию фабрику объектов с OLE системные библиотеки DLL.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа автоматически вызывает эту функцию перед завершением работы приложения. При необходимости вызывать его из переопределения события [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 Отменяет все регистрации фабрики объект приложения с OLE системные библиотеки DLL.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа автоматически вызывает эту функцию перед завершением работы приложения. При необходимости вызывать его из переопределения события [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll  
 Отменяет регистрацию всех фабрик объект приложения.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 Регистрирует все приложения объект фабрики в системном реестре OLE.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszProgID`  
 Указатель на строку, содержащую идентификатор программы понятное, например «Excel.Document.5.»  
  
 `bRegister`  
 Определяет, является ли объект фабрики класса элемента управления должна быть зарегистрирована.  
  
### <a name="remarks"></a>Примечания  
 Выполните краткое обсуждения две формы для этой функции.  
  
- **Функцию UpdateRegistry (** `lpszProgID` **)** регистрирует фабрику этот объект в системном реестре OLE. Эта функция обычно вызывается методом [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
- **Функцию UpdateRegistry (** `bRegister` **)** является переопределяемым эту форму функции. Если `bRegister` — **TRUE**, эта функция регистрирует класс элемента управления в системном реестре. В противном случае — отменяет регистрацию класса.  
  
     При использовании автоматически ActiveX MFC для создания проекта автоматически предоставляет переопределение, чтобы этот чистой виртуальной функции.  
  
##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll  
 Регистрирует все приложения объект фабрики в системном реестре OLE.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bRegister`  
 Определяет, является ли объект фабрики класса элемента управления должна быть зарегистрирована.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если фабрик были успешно обновлены; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция обычно вызывается методом [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) при запуске приложения.  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 Проверяет, что контейнер лицензия на использование элемента управления OLE.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `bstrKey`  
 Объект `BSTR` хранения контейнера версию строки лицензии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если лицензия времени выполнения является допустимым; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Версия по умолчанию вызывает [GetLicenseKey](#getlicensekey) для получения копии элемента управления по лицензии строку и сравнивает его со строки в `bstrKey`. Если две строки совпадают, функция возвращает ненулевое значение; в противном случае она возвращает 0.  
  
 Можно переопределить эту функцию для проверки, пользовательские лицензии.  
  
 Функция [VerifyUserLicense](#verifyuserlicense) проверяет лицензии во время разработки.  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 Проверка лицензий во время разработки для элемента управления OLE.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если допустима лицензии во время разработки; в противном случае — 0.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
