---
title: Класс CCommonDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19f8c0aa6aaa4980466918eac2649cc246b2e6ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ccommondialog-class"></a>Класс CCommonDialog
Базовый класс для классов, которые инкапсулируют функцию общих диалоговых окон Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|Создает объект `CCommonDialog`.|  
  
## <a name="remarks"></a>Примечания  
 Следующие классы инкапсулируют функцию общих диалоговых окон Windows:  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [Диалоговое окно CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog  
 Создает объект `CCommonDialog`.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) полные сведения.  
  
## <a name="see-also"></a>См. также  
 [CDialog-класс](../../mfc/reference/cdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFileDialog](../../mfc/reference/cfiledialog-class.md)   
 [Класс CFontDialog](../../mfc/reference/cfontdialog-class.md)   
 [Класс CColorDialog](../../mfc/reference/ccolordialog-class.md)   
 [Класс CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)   
 [Класс CPrintDialog](../../mfc/reference/cprintdialog-class.md)   
 [Класс CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
