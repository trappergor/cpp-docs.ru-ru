---
title: Класс CClientDC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c767b39874ff64082d8533f92a9e006f69835c97
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205939"
---
# <a name="cclientdc-class"></a>Класс CClientDC
Берет на себя вызов функций Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) во время создания и [ReleaseDC](/windows/desktop/api/winuser/nf-winuser-releasedc) во время уничтожения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Создает `CClientDC` объекта, подключенных к `CWnd`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|HWND окна, для которого данный `CClientDC` является допустимым.|  
  
## <a name="remarks"></a>Примечания  
 Это означает, что контекст устройства, связанный с `CClientDC` объект является клиентской области окна.  
  
 Дополнительные сведения о `CClientDC`, см. в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cclientdc"></a>  CClientDC::CClientDC  
 Создает `CClientDC` объект, который обращается к клиентской области [CWnd](../../mfc/reference/cwnd-class.md) , на которые указывают *pWnd*.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Окно которого клиентской области, будут получать доступ к объект контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функцию Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc).  
  
 Исключения (типа `CResourceException`) создается, если Windows `GetDC` вызов завершается ошибкой. Контекст устройства не могут быть доступны в том случае, если Windows уже выделен все контексты его доступных устройств. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CClientDC::m_hWnd  
 `HWND` Из `CWnd` указатель, используемый для создания `CClientDC` объекта.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 *m_hWnd* является защищенной переменной.  
  
### <a name="example"></a>Пример  
  См. в примере [CClientDC::CClientDC](#cclientdc).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)
