---
title: Класс CMessageMap | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 187d9964da0929516207a67b0e3a769649fc375b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cmessagemap-class"></a>Класс CMessageMap
Этот класс позволяет схемы сообщений объекта для доступа к другим объектом.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Обращается к схеме сообщений в `CMessageMap`-производного класса.|  
  
## <a name="remarks"></a>Примечания  
 `CMessageMap` — Абстрактный базовый класс, позволяющий объекта сообщения сопоставляется доступ к другим объектом. Чтобы объекту предоставлять его схемы сообщений, его класс должен быть производным от `CMessageMap`.  
  
 ATL использует `CMessageMap` содержится поддержки windows и цепочки карты динамическое сообщение. Например, любого класса, содержащего [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) объект должен быть производным от `CMessageMap`. Приведенный ниже код взят из [SUBEDIT](../../visual-cpp-samples.md) образца. Через [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` автоматически наследуется от класса `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Так как окно автономной `m_EditCtrl`, использует схемы сообщений в содержащего класса `CAtlEdit` является производным от `CMessageMap`.  
  
 Дополнительные сведения о схемах сообщений см. в разделе [схемы сообщений](../../atl/message-maps-atl.md) в статье «Классы окон ATL».  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 Обращается к схеме сообщений, определяется `dwMsgMapID` в `CMessageMap`-производного класса.  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>Параметры  
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
  
 `dwMsgMapID`  
 [in] Идентификатор схемы сообщений, которая будет обрабатывать сообщения. Сопоставление сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), определяется 0. Альтернативную схему сообщений, объявленных с [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), определяется `msgMapID`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сообщение обработано полностью, в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Вызывается в процедуру [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) объекта или объекта, динамически цепочки в схему сообщений.  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicChain](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
