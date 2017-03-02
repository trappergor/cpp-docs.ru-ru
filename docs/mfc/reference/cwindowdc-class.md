---
title: "Класс CWindowDC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
dev_langs:
- C++
helpviewer_keywords:
- device contexts, window
- screen output classes
- CWindowDC class
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
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
ms.openlocfilehash: 8a941e1b6f8a398706498ec5d1ce1bfc9156f115
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowdc-class"></a>Класс CWindowDC
Производное от `CDC`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Создает объект `CWindowDC`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|`HWND` К которому `CWindowDC` присоединен.|  
  
## <a name="remarks"></a>Примечания  
 Вызывает функцию Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)во время создания и [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) во время удаления. Это означает, что `CWindowDC` объект производит доступ к области весь экран [CWnd](../../mfc/reference/cwnd-class.md) (клиент и неклиентской области).  
  
 Дополнительные сведения об использовании `CWindowDC`, в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Требования  
 Заголовок: afxwin.h  
  
##  <a name="a-namecwindowdca--cwindowdccwindowdc"></a><a name="cwindowdc"></a>CWindowDC::CWindowDC  
 Создает `CWindowDC` объект, который обращается к весь экран области (клиент и неклиентской) `CWnd` объекта, на который указывает `pWnd`.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Окно которого клиентской области, будет получать доступ к объекту контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функцию Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Исключения (типа `CResourceException`) возникает, если Windows `GetWindowDC` вызов завершается с ошибкой. Контекст устройства доступны не в том случае, если все его контексты устройств доступны уже выделена Windows. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#188;](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="a-namemhwnda--cwindowdcmhwnd"></a><a name="m_hwnd"></a>CWindowDC::m_hWnd  
 `HWND` Из `CWnd` указатель используется для создания `CWindowDC` объекта.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hWnd`защищенные переменная типа `HWND`.  
  
### <a name="example"></a>Пример  
  В примере показано [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>См. также  
 [CDC-класс](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)

