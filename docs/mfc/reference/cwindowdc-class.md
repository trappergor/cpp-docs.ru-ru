---
title: Класс CWindowDC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40566ab94c9708d7b31f88de0f96b4fc33675534
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212525"
---
# <a name="cwindowdc-class"></a>Класс CWindowDC
Производное от `CDC`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|Создает объект `CWindowDC`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|HWND, к которому `CWindowDC` подключен.|  
  
## <a name="remarks"></a>Примечания  
 Вызывает функцию Windows [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc)во время создания и [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) во время уничтожения. Это означает, что `CWindowDC` объект производит доступ к целой области экрана [CWnd](../../mfc/reference/cwnd-class.md) (клиентские и неклиентские области).  
  
 Дополнительные сведения об использовании `CWindowDC`, см. в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Требования  
 Заголовок: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 Создает `CWindowDC` объект, который обращается к целой области экрана (клиентские и неклиентские) `CWnd` объекта, на который указывает *pWnd*.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Окно которого клиентской области, будут получать доступ к объекту контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функцию Windows [GetWindowDC](/windows/desktop/api/winuser/nf-winuser-getwindowdc).  
  
 Исключения (типа `CResourceException`) создается, если Windows `GetWindowDC` вызов завершается ошибкой. Контекст устройства не могут быть доступны в том случае, если Windows уже выделен все контексты его доступных устройств. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd  
 HWND `CWnd` указатель используется для создания `CWindowDC` объекта.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hWnd` является защищенной переменной типа HWND.  
  
### <a name="example"></a>Пример  
  См. в примере [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>См. также  
 [Класс CDC](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)
