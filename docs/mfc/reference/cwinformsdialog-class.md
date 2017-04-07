---
title: "Класс CWinFormsDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsDialog class
- Windows Forms [C++], MFC support
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 86768a849b0112f7c4f8b6b2a694b80065169575
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsdialog-class"></a>Класс CWinFormsDialog
Программа-оболочка для класса диалогового окна MFC, в котором размещается пользовательский элемент управления Windows Forms.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>Параметры  
 `TManagedControl`  
 .NET Framework пользовательский элемент управления, отображаемый в приложении MFC.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Создает объект `CWinFormsDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Извлекает ссылку на пользовательский элемент управления Windows Forms.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Получает дескриптор окна для пользовательского элемента управления Windows Forms.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Приведение типа как ссылка на пользовательский элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 `CWinFormsDialog`является оболочкой для класса диалогового окна MFC ( [CDialog](../../mfc/reference/cdialog-class.md)), на котором размещается пользовательский элемент управления Windows Forms. Это позволяет отображать элементы управления .NET Framework в модальное или немодальное диалоговом окне MFC.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) и [размещение пользователя управления формы Windows Forms в диалоговом окне MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog  
 Создает объект `CWinFormsDialog`.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDTemplate`  
 Содержит идентификатор ресурс шаблона диалоговых окон поле. Использование редактора диалоговых окон для создания шаблона диалогового окна и сохранить его в файле скрипта ресурсов приложения. Дополнительные сведения о шаблонах диалогового окна в разделе [класс CDialog](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>CWinFormsDialog::GetControl  
 Извлекает ссылку на пользовательский элемент управления Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент управления Windows Forms в диалоговом окне MFC.  
  
##  <a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle  
 Получает дескриптор окна для пользовательского элемента управления Windows Forms.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор окна для пользовательского элемента управления Windows Forms.  
  
##  <a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog  
 Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, указывающее, является ли приложение установило фокус ввода для элемента управления в диалоговом окне. Если `OnInitDialog` возвращает ненулевое значение, Windows устанавливает фокус ввода на первый элемент управления в диалоговом окне. Данный метод может вернуть 0 только в том случае, если приложение явно задал фокус ввода для элемента управления в диалоговом окне.  
  
### <a name="remarks"></a>Примечания  
 При создании в диалоговом окне MFC (с помощью [создать](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), или [DoModal](../../mfc/reference/cdialog-class.md#domodal) метод наследуется от [CDialog](../../mfc/reference/cdialog-class.md)), `WM_INITDIALOG` отправляется сообщение, и этот метод вызывается. Он создает экземпляр элемента управления Windows Forms в диалоговом окне и изменяет размер окна в соответствии с размером элемента управления пользователя. Затем он размещает новый элемент управления в диалоговом окне MFC.  
  
 Переопределите эту функцию-член, если необходимо выполнять специальную обработку при инициализации диалоговое окно. Дополнительные сведения об использовании этого метода см. в разделе [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>CWinFormsDialog::operator-&gt;  
 Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.  
  
 Сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>CWinFormsDialog::operator TManagedControl ^  
 Приведение типа как ссылка на пользовательский элемент управления Windows Forms.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор приводит тип как ссылку на элемент управления Windows Forms. Используется для передачи `CWinFormsDialog<``TManagedControl``>` диалоговое окно функции, которые принимают указатель на объект элемента управления Windows Forms пользователь.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [CDialog-класс](../../mfc/reference/cdialog-class.md)

