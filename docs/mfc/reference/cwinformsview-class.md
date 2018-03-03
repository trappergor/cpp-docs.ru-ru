---
title: "Класс CWinFormsView | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb68e906a06d18b41d97851d8d91717ac3dd78b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cwinformsview-class"></a>Класс CWinFormsView
Предоставляет универсальную функцию для размещения элементов управления Windows Forms в качестве представления MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinFormsView : public CView;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinFormsView::CWinFormsView](#cwinformsview)|Создает объект `CWinFormsView`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinFormsView::GetControl](#getcontrol)|Извлекает указатель на элемент управления Windows Forms.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|name||  
|----------|-|  
|[Элемент управления CWinFormsView::operator ^](#operator_control)|Приводит тип как указатель на элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 MFC использует `CWinFormsView` класса для размещения элемента управления .NET Framework Windows Forms в пределах представления MFC. Элемент управления является дочерним элементом собственного представления и занимает всю клиентскую область представления MFC. Результат аналогичен `CFormView` представление, что позволяет воспользоваться преимуществами конструктора Windows Forms и времени выполнения для создания расширенных представлений на основе форм.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в тех проектах, которые динамически связываются с MFC (проекты, в которых определена AFXDLL).  
  
> [!NOTE]
>  CWinFormsView не поддерживает разделитель окна MFC ( [класса CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)). В настоящее время только Windows Forms разделителя поддержка элемента управления.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="cwinformsview"></a>CWinFormsView::CWinFormsView  
 Создает объект `CWinFormsView`.  
  
```  
CWinFormsView(System::Type^ pManagedViewType);  
```  
  
### <a name="parameters"></a>Параметры  
 `pManagedViewType`  
 Указатель на тип данных пользовательского элемента управления Windows Forms.   
  
### <a name="example"></a>Пример  
 В следующем примере `CUserView` класс наследует от `CWinFormsView` и передает тип `UserControl1` для `CWinFormsView` конструктор. `UserControl1`является пользовательского элемента управления в ControlLibrary1.dll.  
  
 [!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]  
  
 [!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]  
  
##  <a name="getcontrol"></a>CWinFormsView::GetControl  
 Извлекает указатель на элемент управления Windows Forms.  
  
```  
System::Windows::Forms::Control^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `System.Windows.Forms.Control`.  
  
### <a name="remarks"></a>Примечания  
 Пример демонстрирует использование Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_control"></a>Элемент управления CWinFormsView::operator ^  
 Приводит тип как указатель на элемент управления Windows Forms.  
  
```  
operator System::Windows::Forms::Control^() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор позволяет передавать `CWinFormsView` представление для функции, которые принимают указатель на элемент управления Windows Forms типа <xref:System.Windows.Forms.Control>.  
  
### <a name="example"></a>Пример  
  В разделе [CWinFormsView::GetControl](#getcontrol).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md)   
 [Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)
