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
ms.openlocfilehash: add135c353366ed54a24c63fcce2101c49d24fe7
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338585"
---
# <a name="cclientdc-class"></a>Класс CClientDC
Берет на себя вызов функций Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) во время создания и [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) во время уничтожения.  
  
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
 Конструктор вызывает функцию Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
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
