---
title: "Класс CAnimationTimerEventHandler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
dev_langs: C++
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 35e59a74be574913b6605bd9bce0934280bbb542
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="canimationtimereventhandler-class"></a>Класс CAnimationTimerEventHandler
Реализует обратный вызов, используемый API анимации, когда происходит событие расчета времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|Создает экземпляр `CAnimationTimerEventHandler` обратного вызова.|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Обрабатывает события, происходящие после завершения обновления анимации. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.)|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Обрабатывает события, происходящие до начала обновления анимации. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Обрабатывает события, которые возникают, когда частота кадров отрисовки для анимации падает ниже частота кадров минимальное нежелательно. (Переопределяет `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.)|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации на маршруте события.|  
  
## <a name="remarks"></a>Примечания  
 Этот обработчик событий, которое передается IUIAnimationTimer::SetTimerEventHandler при вызове CAnimationController::EnableAnimationTimerEventHandler.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 Создает экземпляр CAnimationTimerEventHandler обратного вызова.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>Параметры  
 `pAnimationController`  
 Указатель на контроллер анимации, который будет получать события.  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 Обрабатывает события, происходящие после завершения обновления анимации.  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.  
  
##  <a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 Обрабатывает события, происходящие до начала обновления анимации.  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.  
  
##  <a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 Обрабатывает события, которые возникают, когда частота кадров отрисовки для анимации падает ниже частота кадров минимальное нежелательно.  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>Параметры  
 `fps`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL.  
  
##  <a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 Содержит указатель на контроллер анимации на маршруте события.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Параметры  
 `pAnimationController`  
 Указатель на контроллер анимации, который будет получать события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
