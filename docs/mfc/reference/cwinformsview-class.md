---
title: "Класс CWinFormsView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsView class
- Windows Forms [C++], MFC support
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
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
ms.sourcegitcommit: 6c49d711da747e4c6cbad0f883d93196b6a98057
ms.openlocfilehash: 7aadcc1aa887cb6be1ddbb8f3797c4a9e1af5b6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsview-class"></a>Класс CWinFormsView
Предоставляет универсальную функцию для размещения элементов управления Windows Forms в качестве представления MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Создает объект `CWinFormsView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Извлекает указатель на элемент управления Windows Forms.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя||  
|----------|-|  
|[Элемент управления CWinFormsView::operator ^](#operator_control)|Приведение типа как указатель на элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 MFC использует `CWinFormsView` класса для размещения элемента управления .NET Framework Windows Forms в пределах представления MFC. Элемент управления является дочерним для собственного представления и занимают всю клиентскую область представления MFC. Результат аналогичен `CFormView` представление, что позволяет воспользоваться преимуществами конструктора Windows Forms и времени выполнения для создания расширенных представлений на основе форм.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (проекты, в которых определена AFXDLL).  
  
> [!NOTE]
>  CWinFormsView не поддерживает окна-разделителя MFC ( [класса CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)). В настоящее время только Windows Forms Splitter поддержка элемента управления.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="a-namecwinformsviewa--cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 Создает объект `CWinFormsView`.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Параметры  
 `pManagedViewType`  
 Указатель на тип данных пользовательского элемента управления Windows Forms.   
  
### <a name="example"></a>Пример  
 В следующем примере `CUserView` класс наследует от `CWinFormsView` и передает тип `UserControl1` для `CWinFormsView` конструктор. `UserControl1`является пользовательским элементом управления в ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed&#1;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed&#2;](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="a-namegetcontrola--cwinformsviewgetcontrol"></a><a name="getcontrol"></a>CWinFormsView::GetControl  
 Извлекает указатель на элемент управления Windows Forms.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `System.Windows.Forms.Control`.  
  
### <a name="remarks"></a>Примечания  
 Пример использования Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="a-nameoperatorcontrola--cwinformsviewoperator-control"></a><a name="operator_control"></a>Элемент управления CWinFormsView::operator ^  
 Приведение типа как указатель на элемент управления Windows Forms.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор позволяет передавать `CWinFormsView` представление функции, которые принимают указатель на элемент управления Windows Forms типа <xref:System.Windows.Forms.Control>.</xref:System.Windows.Forms.Control>  
  
### <a name="example"></a>Пример  
  В разделе [CWinFormsView::GetControl](#getcontrol).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)   
 [Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)

