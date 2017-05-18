---
title: "Класс CDynamicChain | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 54137760f2c1ee0f93fd8ad21238710f4b6a4a56
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="cdynamicchain-class"></a>Класс CDynamicChain
Этот класс предоставляет методы, поддерживающие динамические цепочки схемы сообщений.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Конструктор.|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Направляет сообщение Windows для схемы сообщений другим объектом.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Удаляет элемент карты сообщений из коллекции.|  
|[CDynamicChain::SetChainEntry](#setchainentry)|Добавляет в коллекцию элемент карты сообщений или изменяет существующую запись.|  
  
## <a name="remarks"></a>Примечания  
 `CDynamicChain`Управляет коллекцией схемы сообщений, позволяя сообщение Windows направить во время выполнения, в схеме сообщений другим объектом.  
  
 Чтобы добавить поддержку для динамического построения цепочки для схем сообщений, выполните следующее:  
  
-   Создайте производный класс от `CDynamicChain`. В схеме сообщений, укажите [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) макрос, привязанные к схеме сообщений по умолчанию другого объекта.  
  
-   Каждый класс, который требуется существует цепочки от [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`позволяет объекту предоставлять его схемы сообщений с другими объектами.  
  
-   Вызовите `CDynamicChain::SetChainEntry` для которого объект и сопоставления сообщений, вы хотите цепочки для идентификации.  
  
 Например предположим, что класс определяется следующим образом:  
  
 [!code-cpp[NVC_ATL_Windowing #88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 Затем клиент вызывает `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing #89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 где `chainedObj` цепочек объектом и является экземпляром класса, производного от `CMessageMap`. Теперь если `myCtl` получает сообщение, которое не обрабатывается `OnPaint` или `OnSetFocus`, процедуру окна направляет сообщение `chainedObj`в схеме сообщений по умолчанию.  
  
 Дополнительные сведения о цепочки карты сообщения в разделе [схемы сообщений](../../atl/message-maps-atl.md) в статье «Классы окон ATL».  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 Направляет сообщение Windows для схемы сообщений другим объектом.  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>Параметры  
 `dwChainID`  
 [in] Уникальный идентификатор, связанный с объектом цепочек и схему сообщений.  
  
 `hWnd`  
 [in] Дескриптор окна, получаемого сообщения.  
  
 `uMsg`  
 [in] Сообщение, отправленное окну.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lResult`  
 [out] Результат обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если полностью обработан; в противном случае — сообщение **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Для вызова процедуры окна `CallChain`, необходимо указать [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) макрос в схему сообщений. Пример см. в разделе [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Обзор.  
  
 `CallChain`требуется предыдущего вызова [SetChainEntry](#setchainentry) связываемый `dwChainID` значение с объектом и схему сообщений.  
  
##  <a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 Конструктор.  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 Деструктор  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 Удаляет указанное сообщение карты из коллекции.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwChainID`  
 [in] Уникальный идентификатор, связанный с объектом цепочек и схему сообщений. Первоначально определении этого значения путем вызова [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сопоставление сообщений успешно удален из коллекции. В противном случае **FALSE**.  
  
##  <a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 Указанное сообщение карта добавляется в коллекцию.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwChainID`  
 [in] Уникальный идентификатор, связанный с объектом цепочек и схему сообщений.  
  
 `pObject`  
 [in] Указатель на объект цепочек объявление схемы сообщений. Этот объект должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Идентификатор схемы сообщений в связанных объектов. Значение по умолчанию — 0, который определяет схему сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Чтобы указать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), передайте `msgMapID`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сопоставление сообщений успешно добавлен в коллекцию. В противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если `dwChainID` значение уже существует в коллекции, его связанный объект и схему сообщений заменяются `pObject` и `dwMsgMapID`соответственно. В противном случае — добавить новый элемент.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

