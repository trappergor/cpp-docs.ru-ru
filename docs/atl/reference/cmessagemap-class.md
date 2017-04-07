---
title: "Класс CMessageMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 22
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
ms.openlocfilehash: f0b40c73101463b934e3fcf299171bea142fe838
ms.lasthandoff: 02/24/2017

---
# <a name="cmessagemap-class"></a>Класс CMessageMap
Этот класс позволяет схемы сообщений объекта для доступа к другим объектом.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Обращается к схеме сообщений в `CMessageMap`-производного класса.|  
  
## <a name="remarks"></a>Примечания  
 `CMessageMap`Представляет абстрактный базовый класс, обеспечивающий объекта сообщений сопоставляет доступ к другим объектом. Чтобы объекту предоставлять его схемы сообщений, его класс должен быть производным от `CMessageMap`.  
  
 Использует ATL `CMessageMap` содержится поддержка windows и цепочки карты динамическое сообщение. Например, любой класс со [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) объект должен быть производным от `CMessageMap`. Следующий код взят из [SUBEDIT](../../visual-cpp-samples.md) образца. Через [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` автоматически наследуется от класса `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing&#90;](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Поскольку содержащееся окно `m_EditCtrl`, будет использовать схему сообщений в содержащий класс `CAtlEdit` является производным от `CMessageMap`.  
  
 Дополнительные сведения о схемах сообщений см. в разделе [сопоставляет сообщение](../../atl/message-maps-atl.md) в статье «Классы окон ATL».  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage  
 Обращается к схеме сообщений, идентифицируемый `dwMsgMapID` в `CMessageMap`-производного класса.  
  
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
 [in] Дескриптор окна получаемого сообщения.  
  
 `uMsg`  
 [in] Сообщение отправлено в окно.  
  
 `wParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 [in] Дополнительные сведения для конкретного сообщения.  
  
 `lResult`  
 [out] Результат обработки сообщения.  
  
 `dwMsgMapID`  
 [in] Идентификатор схемы сообщений, которая будет обрабатывать сообщения. Схемы сообщений по умолчанию, объявленные с [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), определяется 0. Альтернативную схему сообщений, объявленные с [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), определяется `msgMapID`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** Если сообщение является полностью обработано; в противном случае — **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Вызывается в процедуру [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) объекта или объекта, динамически цепочки в схеме сообщений.  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicChain](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

