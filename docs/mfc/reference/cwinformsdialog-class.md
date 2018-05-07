---
title: Класс CWinFormsDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7596140f48b62a63189444bee6fb363552766fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Возвращает дескриптор окна для пользовательского элемента управления Windows Forms.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Приводит тип как ссылку на пользовательский элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 `CWinFormsDialog` Представляет оболочку для класса диалогового окна MFC ( [CDialog](../../mfc/reference/cdialog-class.md)), на котором размещается пользовательский элемент управления Windows Forms. Это позволяет отображать модальные и немодальные диалоговом окне MFC элементов управления .NET Framework.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) и [размещение пользовательского элемента управления формы Windows в диалоговом окне MFC](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog  
 Создает объект `CWinFormsDialog`.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDTemplate`  
 Содержит идентификатор ресурса шаблона диалогового окна поле. Использование редактора диалоговых окон для создания шаблона диалогового окна и сохранить его в файл скрипта ресурсов приложения. Дополнительные сведения о шаблонах диалогового окна см. в разделе [класса CDialog](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl  
 Извлекает ссылку на пользовательский элемент управления Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на элемент управления Windows Forms в диалоговом окне MFC.  
  
##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle  
 Возвращает дескриптор окна для пользовательского элемента управления Windows Forms.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор окна для пользовательского элемента управления Windows Forms.  
  
##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog  
 Инициализирует диалоговое окно MFC, создание и размещение пользовательского элемента управления Windows Forms на нем.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, которое определяет, будет ли приложение фокус ввода для элемента управления в диалоговом окне. Если `OnInitDialog` возвращает ненулевое Windows устанавливает фокус ввода на первый элемент управления в диалоговом окне. Этот метод может вернуть 0 только в том случае, если приложение задан явно фокус ввода для элемента управления в диалоговом окне.  
  
### <a name="remarks"></a>Примечания  
 При создании в диалоговом окне MFC (с помощью [создать](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), или [DoModal](../../mfc/reference/cdialog-class.md#domodal) метод наследуется от [CDialog](../../mfc/reference/cdialog-class.md)), `WM_INITDIALOG` отправляется сообщение, и этот метод вызывается. Он создает экземпляр элемента управления Windows Forms в диалоговом окне и изменяет размер диалогового окна можно использовать размер пользовательского элемента управления. Затем он размещает новый элемент управления в диалоговом окне MFC.  
  
 Переопределите эту функцию-член, если необходимо выполнить специальную обработку при инициализации диалоговым окном. Дополнительные сведения об использовании этого метода см. в разделе [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;  
 Заменяет [CWinFormsDialog::GetControl](#getcontrol) в выражениях.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.  
  
 Сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>  CWinFormsDialog::operator TManagedControl ^  
 Приводит тип как ссылку на пользовательский элемент управления Windows Forms.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор приводит тип как ссылку на элемент управления Windows Forms. Используется для передачи `CWinFormsDialog<TManagedControl>` для функции, которые принимают указатель на объект элемента управления Windows Forms пользователя используется диалоговое окно.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)   
 [Класс CDialog](../../mfc/reference/cdialog-class.md)
