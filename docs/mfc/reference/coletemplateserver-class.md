---
title: "Класс COleTemplateServer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [C++], implementing
- servers, OLE
- OLE server applications, managing server documents
- link containers [C++]
- visual editing, servers
- OLE link containers
- COleTemplateServer class
- OLE server applications, COleTemplateServer class
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea82939cd0e8a8ba5612c65d238be8ae9996ef08
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coletemplateserver-class"></a>Класс COleTemplateServer
Используется для OLE-серверов визуального редактирования, серверов автоматизации и контейнеров связей (приложений, поддерживающих ссылки на внедряемые объекты).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Создает объект `COleTemplateServer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Подключается к основной шаблон документа `COleObjectFactory` объекта.|  
|[COleTemplateServer::Unregister](#unregister)|Отменяет регистрацию шаблона связанный документ.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Регистрирует тип документа в системном реестре OLE.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является производным от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); как правило, можно использовать `COleTemplateServer` напрямую, вместо создания собственного производного класса. `COleTemplateServer`использует [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объектов для управления документами на сервере. Использование `COleTemplateServer` при реализации всего сервера, то есть сервер, могут выполняться как отдельное приложение. Полные серверы обычно являются несколько приложений интерфейса (MDI) документа, несмотря на то, что поддерживаются однооконный интерфейс (SDI) приложения. Один `COleTemplateServer` объектов необходим для каждого типа документа server поддерживает приложения; то есть, серверное приложение поддерживает листов и диаграмм, необходимо иметь два `COleTemplateServer` объектов.  
  
 `COleTemplateServer`переопределяет `OnCreateInstance` функция-член определяется `COleObjectFactory`. Эта функция-член вызывается платформой для создания объекта C++ соответствующего типа.  
  
 Дополнительные сведения о серверах см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer  
 Создает объект `COleTemplateServer`.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание использования `COleTemplateServer` см. в разделе [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) Общие сведения о классе.  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 Подключает шаблон документа, на который указывает `pDocTemplate` в базовом [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) объекта.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Ссылка на идентификатор класса OLE, запрашивающий шаблона.  
  
 `pDocTemplate`  
 Указатель на шаблон документа.  
  
 `bMultiInstance`  
 Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Если **TRUE**, для каждого запроса создать объект запускаются несколько экземпляров приложения.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="unregister"></a>COleTemplateServer::Unregister  
 Отменяет регистрацию шаблона связанный документ.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если успешно; в противном случае — FALSE.  
  
### <a name="remarks"></a>Примечания  
 EnterRemarks  
  
##  <a name="updateregistry"></a>COleTemplateServer::UpdateRegistry  
 Загружает сведения о типе файла из строки шаблонов документов и помещает эти сведения в системном реестре OLE.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `nAppType`  
 Значение из **OLE_APPTYPE** перечисления, определенного в AFXDISP. З. Он может иметь одно из следующих значений:  
  
- `OAT_INPLACE_SERVER`Сервер имеет всего сервера пользовательского интерфейса.  
  
- `OAT_SERVER`Сервер поддерживает только внедрения.  
  
- `OAT_CONTAINER`Контейнер поддерживает ссылки на внедренные объекты.  
  
- `OAT_DISPATCH_OBJECT`Объект `IDispatch`-поддержкой.  
  
- **OAT_DOC_OBJECT_SERVER** Server поддерживает внедрение и модели компонентов объект документа.  
  
 `rglpszRegister`  
 Список записей, которые записываются в реестр только в том случае, если нет никаких записей.  
  
 `rglpszOverwrite`  
 Список записей, которые записываются в реестр, независимо от того, существуют ли какие-либо предыдущей записи.  
  
 `bRegister`  
 Определяет, является ли класс для регистрации. Если `bRegister` — **TRUE**, класс регистрируется в системном реестре. В противном случае — отменяет регистрацию класса.  
  
### <a name="remarks"></a>Примечания  
 Сведения о регистрации загружается посредством вызова [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Получить подстроки — это определяемый индексы **regFileTypeId**, **regFileTypeName**, и **fileNewName**, как описано в `GetDocString` ссылаются на страницы.  
  
 Если **regFileTypeId** подстроки пуст или если вызов `GetDocString` не по любой другой причине, эта функция будет невозможна, а сведения о файле не будут сохранены в реестре.  
  
 Сведения в аргументах `rglpszRegister` и `rglpszOverwrite` записывается в реестр посредством вызова [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Сведения по умолчанию, которое регистрируется, если оба аргумента **NULL**, подходит для большинства приложений. Сведения о структуре информации из этих аргументов в разделе `AfxOleRegisterServerClass`.  
  
 Дополнительные сведения см. в разделе [реализации интерфейса IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory-класс](../../mfc/reference/coleobjectfactory-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Класса, производного от COleServerItem](../../mfc/reference/coleserveritem-class.md)

