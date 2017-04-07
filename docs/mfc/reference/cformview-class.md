---
title: "Класс CFormView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- views, containing controls
- CFormView class
- form views
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 82b38b04aa3cf2368d41ee20847c952c3082d4e4
ms.lasthandoff: 02/24/2017

---
# <a name="cformview-class"></a>Класс CFormView
Базовый класс, используемый для представлений формы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|Создает объект `CFormView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Используется для синхронизации во время инициализации.|  
  
## <a name="remarks"></a>Примечания  
 По сути, представление формы — это представление, содержащее элементы управления. Эти элементы управления располагаются на основе ресурса шаблона диалогового окна. Используйте `CFormView`, если вы хотите задействовать формы в своем приложении. Эти представления поддерживает прокрутку, при необходимости, с помощью [CScrollView](../../mfc/reference/cscrollview-class.md) функциональные возможности.  
  
 При использовании [создание приложений на основе форм](../../mfc/reference/creating-a-forms-based-mfc-application.md), можно создать класс представления на `CFormView`, делая приложение на основе форм.  
  
 Можно также добавить новые [разделы формы](../../mfc/form-views-mfc.md) в документ представление-приложения. Даже если ваше приложение изначально не поддерживает формы, при вставке новой формы Visual C++ обеспечит их поддержку.  
  
 Приложения на основе форм рекомендуется создавать с помощью мастера приложений MFC и команды Add Class. Если необходимо создать приложение на основе форм без использования этих методов см. в разделе [создание приложений на основе форм](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="cformview"></a>CFormView::CFormView  
 Создает объект `CFormView`.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTemplateName`  
 Содержит нулем строку, имя ресурса шаблона диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурса шаблона диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 При создании объекта типа производным от `CFormView`, вызовите один из конструкторов для создания объекта представления и определения ресурса диалогового окна, лежащие в основе представления. Ресурс можно определить по имени (передавать строку в качестве аргумента конструктору) или по его Идентификатору (pass целое число без знака в качестве аргумента).  
  
 Представление формы окна и дочерние элементы управления не создаются до `CWnd::Create` вызывается. `CWnd::Create`вызывается платформой как часть документа и представления процесс создания, который определяется шаблон документа.  
  
> [!NOTE]
>  Производный класс *необходимо* предоставить свой собственный конструктор. В конструкторе, вызвав конструктор, `CFormView::CFormView`, имя ресурса или идентификатор в качестве аргумента, как показано в предыдущем Общие сведения о классе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#90;](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView&#91;](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>CFormView::IsInitDlgCompleted  
 Используется MFC, чтобы убедиться, что инициализация завершена до выполнения других операций.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если инициализация для этого диалогового окна была завершена.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [Пример MFC приложения](../../visual-cpp-samples.md)   
 [Класс CScrollView](../../mfc/reference/cscrollview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)   
 [Класс CScrollView](../../mfc/reference/cscrollview-class.md)

