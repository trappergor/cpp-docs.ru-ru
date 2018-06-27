---
title: CClientDC-класс | Документы Microsoft
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
ms.openlocfilehash: b4f013589b509781d217e521b680f1d529189a0a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954270"
---
# <a name="cclientdc-class"></a>CClientDC-класс
Отвечает за вызов функций Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) во время создания и [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) во время удаления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|Создает `CClientDC` подключен объект `CWnd`.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND` Окна, для которого данный `CClientDC` является допустимым.|  
  
## <a name="remarks"></a>Примечания  
 Это означает, что контекст устройства, связанный с `CClientDC` объект находится в клиентской области окна.  
  
 Дополнительные сведения о `CClientDC`, в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cclientdc"></a>  CClientDC::CClientDC  
 Создает `CClientDC` объекта, который обращается к клиентской области [CWnd](../../mfc/reference/cwnd-class.md) , на который указывает *pWnd*.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Окно которого клиентской области, будут обращаться к объект контекста устройства.  
  
### <a name="remarks"></a>Примечания  
 Конструктор вызывает функции Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871).  
  
 Исключения (типа `CResourceException`) выдается, если Windows `GetDC` вызов завершается с ошибкой. На контекст устройства не могут быть доступны в том случае, если Windows уже выделена все контексты его доступных устройств. Приложение конкурирует за пять общих отображения контексты, доступные в любой момент времени в Windows.  
  
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
  Далее приведен пример [CClientDC::CClientDC](#cclientdc).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CDC](../../mfc/reference/cdc-class.md)
