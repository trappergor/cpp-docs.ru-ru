---
title: "Класс COleTemplateServer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs: C++
helpviewer_keywords:
- COleTemplateServer [MFC], COleTemplateServer
- COleTemplateServer [MFC], ConnectTemplate
- COleTemplateServer [MFC], Unregister
- COleTemplateServer [MFC], UpdateRegistry
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4bf5f696eeff3e4e26a9d77714c0d5a6f093aaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coletemplateserver-class"></a>Класс COleTemplateServer
Используется для OLE-серверов визуального редактирования, серверов автоматизации и контейнеров связей (приложений, поддерживающих ссылки на внедряемые объекты).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|Создает объект `COleTemplateServer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|Подключается к основному шаблон документа `COleObjectFactory` объекта.|  
|[COleTemplateServer::Unregister](#unregister)|Отменяет регистрацию шаблона связанный документ.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|Регистрирует тип документа в системном реестре OLE.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является производным от класса [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); как правило, можно использовать `COleTemplateServer` напрямую вместо создания собственного производного класса. `COleTemplateServer`использует [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объектов для управления документами на сервере. Используйте `COleTemplateServer` при реализации всего сервера, то есть сервера, которая может выполняться как отдельное приложение. Полные серверы обычно являются нескольким приложениям интерфейса (MDI) документа, несмотря на то, что поддерживаются однооконный интерфейс (SDI) приложения. Один `COleTemplateServer` объекта необходим для каждого типа документа server поддерживает приложения; то есть, если серверное приложение поддерживает листы и диаграммы, необходимо иметь два `COleTemplateServer` объектов.  
  
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
 Краткое описание использования `COleTemplateServer` см. в описании [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) Общие сведения о классе.  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 Подключает шаблон документа, на который указывает `pDocTemplate` к базовому объекту [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) объекта.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>Параметры  
 `clsid`  
 Ссылка на шаблон запрашивает идентификатора класса OLE.  
  
 `pDocTemplate`  
 Указатель на шаблон документа.  
  
 `bMultiInstance`  
 Указывает, является ли один экземпляр приложения может поддерживать несколько экземпляров. Если **TRUE**, запуск нескольких экземпляров приложения для каждого запроса для создания объекта.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [раздел CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) в Windows SDK.  
  
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
 Значение из **OLE_APPTYPE** перечисления, который определен в AFXDISP. З. Он может иметь одно из следующих значений:  
  
- `OAT_INPLACE_SERVER`Сервер имеет всего сервера пользовательского интерфейса.  
  
- `OAT_SERVER`Сервер поддерживает только внедрения.  
  
- `OAT_CONTAINER`Контейнер поддерживает ссылки на внедренные объекты.  
  
- `OAT_DISPATCH_OBJECT`Объект `IDispatch`-поддержкой.  
  
- **OAT_DOC_OBJECT_SERVER** Server поддерживает как встраивание и модели компонентов объект документа.  
  
 `rglpszRegister`  
 Список записей, которые записываются в реестр только в том случае, если нет никаких записей.  
  
 `rglpszOverwrite`  
 Список записей, которые записываются в реестр, независимо от того, существуют ли какие-либо предыдущей записи.  
  
 `bRegister`  
 Определяет, является ли класс должны быть зарегистрированы. Если `bRegister` — **TRUE**, класс регистрируется в системном реестре. В противном случае — отменяет регистрацию класса.  
  
### <a name="remarks"></a>Примечания  
 Сведения о регистрации загружается с помощью вызова [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Получить подстроки, являются определяется индексы **regFileTypeId**, **regFileTypeName**, и **fileNewName**, как описано в `GetDocString` в справочнике по.  
  
 Если **regFileTypeId** подстроки пуст или если вызов `GetDocString` завершается с ошибкой по другой причине, эта функция завершается с ошибкой и данные файла не указан в реестре.  
  
 Сведения в аргументах `rglpszRegister` и `rglpszOverwrite` записывается в реестр посредством вызова [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass). Сведения по умолчанию, который регистрируется, если оба аргумента **NULL**, подходит для большинства приложений. Сведения о структуре информации из этих аргументов см. в разделе `AfxOleRegisterServerClass`.  
  
 Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory-класс](../../mfc/reference/coleobjectfactory-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Класс COleServerItem](../../mfc/reference/coleserveritem-class.md)
