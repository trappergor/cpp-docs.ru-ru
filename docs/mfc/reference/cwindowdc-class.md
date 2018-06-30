---
title: Класс CWindowDC | Документы Microsoft
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
ms.openlocfilehash: 8b757da27f2b4ae79a0192df0598f833b3d1e7b9
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121546"
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
|[CWindowDC::m_hWnd](#m_hwnd)|HWND, к которому `CWindowDC` присоединен.|  
  
## <a name="remarks"></a>Примечания  
 Вызывает функцию Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)во время создания и [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) во время удаления. Это означает, что `CWindowDC` объект производит доступ к области весь экран [CWnd](../../mfc/reference/cwnd-class.md) (клиент и неклиентской областей).  
  
 Дополнительные сведения об использовании `CWindowDC`, в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>Требования  
 Заголовок: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 Создает `CWindowDC` объект, который обращается к весь экран области (клиент и неклиентской) `CWnd` объекта, на который указывает *pWnd*.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Окно которого клиентской области, будут обращаться к объект контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функции Windows [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947).  
  
 Исключения (типа `CResourceException`) выдается, если Windows `GetWindowDC` вызов завершается с ошибкой. На контекст устройства не могут быть доступны в том случае, если Windows уже выделена все контексты его доступных устройств. Приложение конкурирует за пять общих отображения контексты, доступные в любой момент времени в Windows.  
  
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
  Далее приведен пример [CWindowDC::CWindowDC](#cwindowdc).  
  
## <a name="see-also"></a>См. также  
 [CDC-класс](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)
