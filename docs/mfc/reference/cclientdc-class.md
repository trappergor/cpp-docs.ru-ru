---
title: "Класс CClientDC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CClientDC
dev_langs:
- C++
helpviewer_keywords:
- CClientDC class
- device contexts, client area
- client-area device context
- CDC class, device contexts for client areas
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 619bed4d31994bde8464ad710e9f050d6ba0696a
ms.lasthandoff: 02/24/2017

---
# <a name="cclientdc-class"></a>CClientDC-класс
Отвечает за вызов функций Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) во время создания и [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) во время удаления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Создает `CClientDC` подключен объект `CWnd`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND` Окна, для которого данный `CClientDC` является допустимым.|  
  
## <a name="remarks"></a>Примечания  
 Это означает, что контекст устройства, связанный с `CClientDC` объект является клиентской области окна.  
  
 Дополнительные сведения о `CClientDC`, в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-namecclientdca--cclientdccclientdc"></a><a name="cclientdc"></a>CClientDC::CClientDC  
 Создает `CClientDC` объекта, который обращается к клиентской области [CWnd](../../mfc/reference/cwnd-class.md) указывает `pWnd`.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Окно которого клиентской области, будет получать доступ к объекту контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функцию Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
 Исключения (типа `CResourceException`) возникает, если Windows `GetDC` вызов завершается с ошибкой. Контекст устройства доступны не в том случае, если все его контексты устройств доступны уже выделена Windows. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#42;](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="a-namemhwnda--cclientdcmhwnd"></a><a name="m_hwnd"></a>CClientDC::m_hWnd  
 `HWND` Из `CWnd` указатель, используемый для создания `CClientDC` объекта.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hWnd`является защищенной переменной.  
  
### <a name="example"></a>Пример  
  В примере показано [CClientDC::CClientDC](#cclientdc).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)

