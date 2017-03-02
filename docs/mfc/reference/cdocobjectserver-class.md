---
title: "Класс CDocObjectServer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServer
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServer class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 75fb0ba49d105a673e862ed3044e85ac9e990e9c
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserver-class"></a>Класс CDocObjectServer
Реализует дополнительные интерфейсы OLE, необходимые для преобразования стандартного сервера `COleDocument` в полноценный сервер DocObject: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`и `IPrint`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Создает объект `CDocObjectServer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Активирует сервер объект документа, но не отображается.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Отображение представления DocObject.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Восстанавливает состояние представления DocObject.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Сохраняет состояние представления DocObject.|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServer`является производным от `CCmdTarget` и тесно сотрудничает с `COleServerDoc` предоставление интерфейсов.  
  
 Сервер DocObject документ может содержать [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) объектов, которые представляют собой интерфейс сервера с элементами DocObject.  
  
 Чтобы настроить сервер DocObject, создать собственный производный класс от `CDocObjectServer` и переопределите его функций настройки представления, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), и [OnSaveViewState](#onsaveviewstate). Необходимо будет предоставлять новый экземпляр класса в ответ на вызовы framework.  
  
 Дополнительные сведения о DocObjects в разделе [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. См. также [Интернет первые шаги: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
 Также см. в следующей статье базы знаний:  
  
-   Q247382: PRB: всплывающие подсказки для элементов управления в документ ActiveX сервера скрыты по контейнер документов ActiveX  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
##  <a name="a-nameactivatedocobjecta--cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 Эта функция вызывается для активации (но не показывать) сервера объект документа.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Примечания  
 `ActivateDocObject`вызовы `IOleDocumentSite` **ActivateMe** метода, но не показывает представление, поскольку он ожидает специальные инструкции для настройки и отображения представления, указанного в вызове [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Вместе `ActivateDocObject` и `OnActivateView` активации и отобразить представление DocObject. Активация DocObject отличается от других видов активации на месте OLE. Активации DocObject обходит отображения границы штриховки на месте и оформления объекта (например, маркеров), игнорирует функции экстент объектов и рисует полосы прокрутки прямоугольника представление, в отличие от их рисования за границы этого прямоугольника (как в обычном активации на месте).  
  
##  <a name="a-namecdocobjectservera--cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 Создает и инициализирует объект `CDocObjectServer`.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pOwner*  
 Указатель на документ сайта клиента, клиент сервер DocObject.  
  
 `pDocSite`  
 Указатель на `IOleDocumentSite` интерфейс, реализованный контейнером.  
  
### <a name="remarks"></a>Примечания  
 При активном DocObject клиента сайта OLE-интерфейс ( `IOleDocumentSite`) является то, что позволяет серверу DocObject для связи с его клиентом (контейнера). Когда сервер DocObject активируется, сначала она проверяет, что контейнер реализует `IOleDocumentSite` интерфейса. В этом случае [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) вызывается, чтобы узнать, поддерживает ли контейнер DocObjects. По умолчанию `GetDocObjectServer` возвращает **NULL**. Необходимо переопределить `COleServerDoc::GetDocObjectServer` для создания нового `CDocObjectServer` объекта или производного объекта собственные, с помощью указателей на `COleServerDoc` контейнера и его `IOleDocumentSite` интерфейс в качестве аргументов, передаваемых конструктору.  
  
##  <a name="a-nameonactivateviewa--cdocobjectserveronactivateview"></a><a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 Эта функция вызывается для отображения представления DocObject.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ошибки или предупреждения. По умолчанию возвращает **значение NOERROR** при успехе; в противном случае — **E_FAIL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает окно фрейма на месте, рисует полосы прокрутки в представлении, настраивает меню сервере совместно с его контейнером, добавляет элементы управления frame, задает активный объект затем наконец показано окно фрейма на месте и с фокусом.  
  
##  <a name="a-nameonapplyviewstatea--cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 Переопределите эту функцию для восстановления состояния представления DocObject.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект, из которого для сериализации состояния представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда представление отображается в первый раз после его установки. `OnApplyViewState`Указывает, что представление, чтобы инициализировать себя повторно, согласно данным в `CArchive` объекта, сохраненные с [OnSaveViewState](#onsaveviewstate). Данные в представлении необходимо проверить `CArchive` объекта контейнера не пытаться интерпретировать данные состояния представления каким-либо образом.  
  
 Можно использовать `OnSaveViewState` для хранения постоянных информации состояния представления элемента. При переопределении `OnSaveViewState` для хранения информации, необходимо переопределить `OnApplyViewState` прочитать эту информацию и применять его для просмотра, когда вновь активируется.  
  
##  <a name="a-nameonsaveviewstatea--cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 Переопределите эту функцию для сохранения сведений о представлении DocObject дополнительный состоянии.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 A `CArchive` объекта для сериализации состояния представления.  
  
### <a name="remarks"></a>Примечания  
 Состояние может включать такие свойства, как тип представления, масштаба, вставки и точке выбора и т. д. Контейнер обычно вызывает эту функцию перед деактивацией представления. Сохраненное состояние позже может быть восстановлена до [OnApplyViewState](#onapplyviewstate).  
  
 Можно использовать `OnSaveViewState` для хранения постоянных информации состояния представления элемента. При переопределении `OnSaveViewState` для хранения информации, необходимо переопределить `OnApplyViewState` прочитать эту информацию и применять его для просмотра, когда вновь активируется.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)

