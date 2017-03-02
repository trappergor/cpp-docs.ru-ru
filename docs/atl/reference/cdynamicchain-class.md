---
title: "Класс CDynamicChain | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicChain
- ATL.CDynamicChain
- CDynamicChain
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4da97d0b3d72400d7e285fde187e6860759900af
ms.lasthandoff: 02/24/2017

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
|[CDynamicChain::CallChain](#callchain)|Направляет сообщение Windows для сопоставления сообщений другим объектом.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Удаляет элемент карты сообщений из коллекции.|  
|[CDynamicChain::SetChainEntry](#setchainentry)|Добавляет в коллекцию элемент карты сообщений или изменяет существующую запись.|  
  
## <a name="remarks"></a>Примечания  
 `CDynamicChain`Управляет коллекцией схемы сообщений, включение сообщение Windows, должны направляться во время выполнения для сопоставления сообщений другим объектом.  
  
 Чтобы добавить поддержку динамического цепочки сообщений карт, выполните следующие действия:  
  
-   Создайте производный класс от `CDynamicChain`. В схеме сообщений укажите [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) макрос в цепочке в схеме сообщений по умолчанию другого объекта.  
  
-   Каждый класс, вы хотите связываться по цепочке с [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`позволяет объекту предоставлять его схемы сообщений на другие объекты.  
  
-   Вызов `CDynamicChain::SetChainEntry` определить, какие объекта и сопоставление сообщений, вы хотите цепочки.  
  
 Например предположим, что класс определяется следующим образом:  
  
 [!code-cpp[NVC_ATL_Windowing&#88;](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 Затем клиент вызывает `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing&#89;](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 где `chainedObj` — цепные объект, является экземпляром класса, производного от `CMessageMap`. Теперь если `myCtl` получает сообщение, которое не обрабатывается `OnPaint` или `OnSetFocus`, процедура окна направляет сообщение `chainedObj`в схеме сообщений по умолчанию.  
  
 Дополнительные сведения о цепочках карты сообщения в разделе [схемы сообщений](../../atl/message-maps-atl.md) в статье «Классы окон ATL».  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-namecallchaina--cdynamicchaincallchain"></a><a name="callchain"></a>CDynamicChain::CallChain  
 Направляет сообщение Windows для сопоставления сообщений другим объектом.  
  
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
 [in] Уникальный идентификатор, связанный с помощью связанных объекта и его сопоставления сообщений.  
  
 `hWnd`  
 [in] Дескриптор окна получаемого сообщения.  
  
 `uMsg`  
 [in] Сообщение отправлено в окно.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lResult`  
 [out] Результат обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сообщение является полностью обработан; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Для вызова процедуры окна `CallChain`, необходимо указать [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) макрос в сопоставлении сообщений. Например, в разделе [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Обзор.  
  
 `CallChain`требуется предыдущего вызова [SetChainEntry](#setchainentry) для связывания `dwChainID` значение с помощью объекта и его сопоставления сообщений.  
  
##  <a name="a-namecdynamicchaina--cdynamicchaincdynamicchain"></a><a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 Конструктор.  
  
```
CDynamicChain();
```  
  
##  <a name="a-namedtora--cdynamicchaincdynamicchain"></a><a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 Деструктор  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-nameremovechainentrya--cdynamicchainremovechainentry"></a><a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 Удаляет указанное сообщение карты из коллекции.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwChainID`  
 [in] Уникальный идентификатор, связанный с помощью связанных объекта и его сопоставления сообщений. Изначально определить это значение путем вызова [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если в схеме сообщений успешно удален из коллекции. В противном случае — **FALSE**.  
  
##  <a name="a-namesetchainentrya--cdynamicchainsetchainentry"></a><a name="setchainentry"></a>CDynamicChain::SetChainEntry  
 Добавляет в коллекцию указанное сообщение карты.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwChainID`  
 [in] Уникальный идентификатор, связанный с помощью связанных объекта и его сопоставления сообщений.  
  
 `pObject`  
 [in] Указатель на объект цепные объявление схемы сообщений. Этот объект должен быть производным от [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Идентификатор схемы сообщений в связанных объектов. Значение по умолчанию — 0, который определяет сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Чтобы указать альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), передайте `msgMapID`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если в схеме сообщений успешно добавлен в коллекцию. В противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Если `dwChainID` значение уже существует в коллекции, его связанного объекта и схемы сообщений заменяются `pObject` и `dwMsgMapID`соответственно. В противном случае добавляется новая запись.  
  
## <a name="see-also"></a>См. также  
 [Класс CWindowImpl](../../atl/reference/cwindowimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

