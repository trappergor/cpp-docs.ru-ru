---
title: Класс CDocObjectServer | Документы Microsoft
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
ms.openlocfilehash: 2d9951fd087619371e24f06822774cec005787c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367410"
---
# <a name="cdocobjectserver-class"></a>Класс CDocObjectServer
Реализует дополнительные интерфейсы OLE, необходимые для преобразования стандартного сервера `COleDocument` в полноценный сервер DocObject: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`и `IPrint`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
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
|[CDocObjectServer::OnActivateView](#onactivateview)|Отображает представление DocObject.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|Восстанавливает состояние представления DocObject.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|Сохраняет состояние представления DocObject.|  
  
## <a name="remarks"></a>Примечания  
 `CDocObjectServer` является производным от `CCmdTarget` и работает в тесном сотрудничестве с `COleServerDoc` чтобы предоставить доступ к интерфейсам.  
  
 DocObject серверного документа может содержать [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) объектов, которые представляют элементы DocObject интерфейс сервера.  
  
 Чтобы настроить сервер DocObject, создать собственный класс, от `CDocObjectServer` и переопределить свои функции настройки представления, [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), и [OnSaveViewState ](#onsaveviewstate). Необходимо будет предоставить новый экземпляр класса в ответ на вызовы framework.  
  
 Дополнительные сведения о DocObjects см. в разделе [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) и [COleCmdUI](../../mfc/reference/colecmdui-class.md) в *Справочник по библиотеке MFC*. См. также [первые шаги в Интернете: активные документы](../../mfc/active-documents-on-the-internet.md) и [активные документы](../../mfc/active-documents-on-the-internet.md).  
  
 Также см. в следующей статье базы знаний:  
  
-   Q247382: PRB: подсказки для элементов управления в документ ActiveX Server скрыты по контейнер ActiveX  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdocob.h  
  
##  <a name="activatedocobject"></a>  CDocObjectServer::ActivateDocObject  
 Эта функция вызывается для активации (но не показывать) сервера объект документа.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Примечания  
 `ActivateDocObject` вызовы `IOleDocumentSite` **ActivateMe** метода, но не содержит представление, так как он ожидает инструкциями о том, как установить и отобразить представление, учитывая в вызове [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Вместе `ActivateDocObject` и `OnActivateView` активации и отображает представление DocObject. DocObject активации отличается от других видов OLE встроенной активации. Активация DocObject обходит отображения границы штриховки на месте и оформления объекта (например, маркеры изменения размера), игнорирует функции экстент объектов и рисует полосы прокрутки внутри прямоугольника представление, в отличие от их рисования за пределами этого прямоугольника (как обычный Активация на месте).  
  
##  <a name="cdocobjectserver"></a>  CDocObjectServer::CDocObjectServer  
 Создает и инициализирует объект `CDocObjectServer`.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pOwner*  
 Указатель на документ сайта клиента, который является клиент для сервер DocObject.  
  
 `pDocSite`  
 Указатель на `IOleDocumentSite` интерфейс, реализуемый контейнера.  
  
### <a name="remarks"></a>Примечания  
 При включенном DocObject клиент сайта OLE-интерфейс ( `IOleDocumentSite`) является то, что позволяет сервер DocObject для связи с его клиентом (контейнер). При активации сервер DocObject сначала проверяется, что контейнер реализует `IOleDocumentSite` интерфейса. В этом случае [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) вызывается, чтобы узнать, поддерживает ли контейнер DocObjects. По умолчанию `GetDocObjectServer` возвращает **NULL**. Необходимо переопределить `COleServerDoc::GetDocObjectServer` для создания нового `CDocObjectServer` или производного объекта собственные, с помощью указателей на `COleServerDoc` контейнера и его `IOleDocumentSite` интерфейс в качестве аргументов, передаваемых конструктору.  
  
##  <a name="onactivateview"></a>  CDocObjectServer::OnActivateView  
 Вызывайте эту функцию, чтобы отобразить представление DocObject.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ошибку или предупреждение значение. По умолчанию возвращает **значение NOERROR** Если успешно; в противном случае — **E_FAIL**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает окно фрейма на месте, рисует полосы прокрутки в представлении, настраивает меню сервера являются общими с его контейнером, добавляет элементы управления frame, задает активный объект затем наконец показано окно фрейма на месте и устанавливает фокус ввода.  
  
##  <a name="onapplyviewstate"></a>  CDocObjectServer::OnApplyViewState  
 Переопределите эту функцию, чтобы восстановить состояние представления DocObject.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объект, из которого для сериализации состояния представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается, когда представление отображается в первый раз после создания его экземпляра. `OnApplyViewState` Указывает, что представление повторной инициализацией в соответствии с данными в `CArchive` объект, сохраненный ранее с [OnSaveViewState](#onsaveviewstate). Данные в представлении необходимо проверить `CArchive` объекта, так как контейнер не пытается интерпретировать данные состояния представления каким-либо образом.  
  
 Можно использовать `OnSaveViewState` для хранения информации постоянное состояние этого представления. При переопределении `OnSaveViewState` для хранения данных, необходимо переопределить `OnApplyViewState` прочитать эту информацию и примените его к представлению, когда активирована вновь.  
  
##  <a name="onsaveviewstate"></a>  CDocObjectServer::OnSaveViewState  
 Переопределите эту функцию для сохранения сведений о представлении DocObject лишние состоянии.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 `ar`  
 Объект `CArchive` объекта, в который выполняется сериализация состояния представления.  
  
### <a name="remarks"></a>Примечания  
 Состояние может включать такие свойства, как тип представления, масштаб, вставки и выбора точки и т. д. Обычно контейнер вызывает эту функцию перед деактивацией представления. Сохраненное состояние позже может быть восстановлена до [OnApplyViewState](#onapplyviewstate).  
  
 Можно использовать `OnSaveViewState` для хранения информации постоянное состояние этого представления. При переопределении `OnSaveViewState` для хранения данных, необходимо переопределить `OnApplyViewState` прочитать эту информацию и примените его к представлению, когда активирована вновь.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
