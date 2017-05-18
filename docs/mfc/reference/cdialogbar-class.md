---
title: "CDialogBar-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- dialog bars, Windows modeless dialog box
- CDialogBar class
- dialog boxes, modeless
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 33dc5f5f4d345745a4b9435e725f411f4387e287
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogbar-class"></a>CDialogBar-класс
Предоставляет функциональные возможности немодального диалогового окна Windows на панели элементов управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Создает объект `CDialogBar`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Создает панель диалогового окна Windows и присоединяет его к `CDialogBar` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Панель диалогового окна напоминает диалоговое окно содержит стандартные элементы управления Windows, пользователь может перейти между. Другой схожесть существует создания шаблона диалогового окна для представления панели диалогового окна.  
  
 Создание и использование диалоговой панели похож на создание и использование `CFormView` объекта. Во-первых, используйте [редактор диалоговых окон](../../windows/dialog-editor.md) для определения шаблона диалогового окна в стиле **WS_CHILD** и другие стили отсутствуют. Шаблон не должен иметь стиль **WS_VISIBLE**. В коде приложения вызовите конструктор для создания `CDialogBar` , а затем вызвать **создать** для создания окна диалоговая панель и присоединить его к `CDialogBar` объекта.  
  
 Дополнительные сведения о `CDialogBar`, см. в статье [диалоговые](../../mfc/dialog-bars.md) и [Технические заметки 31](../../mfc/tn031-control-bars.md), панелей элементов управления.  
  
> [!NOTE]
>  В текущем выпуске `CDialogBar` не может размещать элементы управления Windows Forms. Дополнительные сведения об элементах управления Windows Forms в Visual C++ см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле afxext.h  
  
##  <a name="cdialogbar"></a>CDialogBar::CDialogBar  
 Создает объект `CDialogBar`.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>CDialogBar::Create  
 Загружает ресурс шаблона диалоговых окон, указанного в `lpszTemplateName` или `nIDTemplate`, создает окно Панель диалогового окна, задает его стиль и связывает его с `CDialogBar` объекта.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительский `CWnd` объекта.  
  
 `lpszTemplateName`  
 Указатель на имя `CDialogBar` шаблона диалоговых ресурсов объекта.  
  
 `nStyle`  
 Стиль панели инструментов. Существуют следующие стили дополнительных инструментов поддерживается:  
  
- `CBRS_TOP`Панель находится в верхней части окна фрейма.  
  
- `CBRS_BOTTOM`Панель элементов управления — в нижней части окна фрейма.  
  
- `CBRS_NOALIGN`При изменении размера родительской панели элементов управления не перемещен.  
  
- `CBRS_TOOLTIPS`Панель отображает всплывающие подсказки.  
  
- **CBRS_SIZE_DYNAMIC** панели элементов управления является динамическим.  
  
- **CBRS_SIZE_FIXED** предопределенной панели элементов управления.  
  
- **CBRS_FLOATING** плавающей панели элементов управления.  
  
- `CBRS_FLYBY`Строка состояния отображает сведения о кнопке.  
  
- **CBRS_HIDE_INPLACE** панель управления не отображается для пользователя.  
  
 `nID`  
 Идентификатор элемента управления панели диалогового окна.  
  
 `nIDTemplate`  
 Идентификатор ресурса `CDialogBar` шаблона диалогового объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 При указании `CBRS_TOP` или `CBRS_BOTTOM` стиль выравнивания диалоговая панель ширина, окна фрейма, а высота это ресурс, заданный параметром `nIDTemplate`. При указании `CBRS_LEFT` или `CBRS_RIGHT` стиль выравнивания диалоговая панель высота, окна фрейма, а ширина — это ресурс, заданный параметром `nIDTemplate`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCMessageMaps&#13;](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)   
 [CControlBar-класс](../../mfc/reference/ccontrolbar-class.md)

