---
title: Класс CDocObjectServer | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 701cfc2f8a88f57a1c50c9c4310ecd21154ef09a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337870"
---
# <a name="cdocobjectserver-class"></a>Класс CDocObjectServer
Реализует дополнительные интерфейсы OLE, необходимые для преобразования стандартного сервера `COleDocument` в полноценный сервер DocObject: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`и `IPrint`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Создает объект `CDocObjectServer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Активирует сервер объект документа, но не отображается.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|Отображает представление DocObject.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Восстанавливает состояние представления DocObject.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Сохраняет состояние представления DocObject.|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServer` является производным от `CCmdTarget` и работает в тесном сотрудничестве с `COleServerDoc` предоставление интерфейсов.  
  
 DocObject серверного документа может содержать [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) объекты, которые представляют собой интерфейс сервер DocObject элементов.  
  
 Чтобы настроить сервер DocObject, собственный производный класс от `CDocObjectServer` и переопределите его представление функций настройки, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), и [OnSaveViewState ](#onsaveviewstate). Необходимо будет предоставлять новый экземпляр класса в ответ на вызовы framework.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. Также см. в разделе [Internet первые шаги: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
 Также см. в следующей статье базы знаний:  
  
-   Q247382: PRB: всплывающие подсказки для элементов управления на сервере документов ActiveX скрыты по контейнер ActiveX  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
##  <a name="activatedocobject"></a>  CDocObjectServer::ActivateDocObject  
 Вызывайте эту функцию для активации (но не показывать) сервера объект документа.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Примечания  
 `ActivateDocObject` вызовы `IOleDocumentSite` `ActivateMe` метод, но не содержит представление, так как он ожидает инструкциями о том, как установить и отобразить представление, учитывая в вызове [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Вместе `ActivateDocObject` и `OnActivateView` активации и отображает представление DocObject. Активация DocObject отличается от других видов активации OLE на месте. Активация DocObject обходит отображения границы штриховки на месте и крайние элементы объекта (например, маркеры изменения размера), игнорирует функции экстент объектов и рисует полосы прокрутки в представлении прямоугольника в отличие от их рисования за пределами этого прямоугольника (как обычный Активация на месте).  
  
##  <a name="cdocobjectserver"></a>  CDocObjectServer::CDocObjectServer  
 Создает и инициализирует объект `CDocObjectServer`.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pOwner*  
 Указатель на документ узла клиента, который является клиент для сервер DocObject.  
  
 *pDocSite*  
 Указатель на `IOleDocumentSite` интерфейс реализован контейнером.  
  
### <a name="remarks"></a>Примечания  
 При активном DocObject клиента сайта интерфейс OLE ( `IOleDocumentSite`) позволяет серверу DocObject для связи с его клиентом (контейнер). Когда сервер DocObject активируется, сначала она проверяет, что контейнер реализует `IOleDocumentSite` интерфейс. Если Да, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) вызывается, чтобы определить, поддерживает ли контейнер DocObjects. По умолчанию `GetDocObjectServer` возвращает значение NULL. Необходимо переопределить `COleServerDoc::GetDocObjectServer` для создания нового `CDocObjectServer` объекта или производного объекта, собственные, с помощью указателей на `COleServerDoc` контейнера и его `IOleDocumentSite` интерфейс как аргументы в конструктор.  
  
##  <a name="onactivateview"></a>  CDocObjectServer::OnActivateView  
 Вызывайте эту функцию, чтобы отобразить представление DocObject.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает сообщение об ошибке или предупреждения. По умолчанию возвращает значение NOERROR успешного выполнения; в противном случае — значение E_FAIL.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает окно фрейма на месте, рисует полосы прокрутки в представлении, настраивает меню, сервер использует совместно с его контейнером, добавляет элементы управления фрейма, задает активный объект, а затем и, наконец показано окно фрейма на месте и устанавливает фокус.  
  
##  <a name="onapplyviewstate"></a>  CDocObjectServer::OnApplyViewState  
 Переопределите эту функцию, чтобы восстановить состояние представления DocObject.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 *ar*  
 Объект `CArchive` объект, из которого требуется выполнить сериализацию состояния представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда представление отображается в первый раз после его установки. `OnApplyViewState` Указывает, что представление повторной инициализацией в соответствии с данными в `CArchive` объекта, ранее сохраненных с [OnSaveViewState](#onsaveviewstate). Представление должно проверить их в `CArchive` объекта, так как контейнер не будет пытаться интерпретировать данные о состоянии представления любым способом.  
  
 Можно использовать `OnSaveViewState` для хранения постоянных сведения, относящиеся к состояние вашего представления. При переопределении `OnSaveViewState` для хранения информации, необходимо переопределить `OnApplyViewState` прочитать эту информацию и применить его к представлению, когда он активирован вновь.  
  
##  <a name="onsaveviewstate"></a>  CDocObjectServer::OnSaveViewState  
 Переопределите эту функцию для сохранения сведений о представлении DocObject дополнительный состоянии.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 *ar*  
 Объект `CArchive` объекта, в который сериализуется состояние представления.  
  
### <a name="remarks"></a>Примечания  
 Состояние может включать такие свойства, как тип представления, коэффициент масштабирования, вставки и выбора точки и т. д. Контейнер обычно вызывает эту функцию перед деактивацией представления. Сохраненное состояние можно восстановить позже через [OnApplyViewState](#onapplyviewstate).  
  
 Можно использовать `OnSaveViewState` для хранения постоянных сведения, относящиеся к состояние вашего представления. При переопределении `OnSaveViewState` для хранения информации, необходимо переопределить `OnApplyViewState` прочитать эту информацию и применить его к представлению, когда он активирован вновь.  
  
## <a name="see-also"></a>См. также  
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
