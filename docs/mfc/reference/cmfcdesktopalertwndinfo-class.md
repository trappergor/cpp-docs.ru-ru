---
title: "Класс CMFCDesktopAlertWndInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo class
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7013a7c9b29c6dc9e6324ca0490a667ed79c88f7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndinfo-class"></a>Класс CMFCDesktopAlertWndInfo
`CMFCDesktopAlertWndInfo` Класс используется вместе с [CMFCDesktopAlertWnd класса](../../mfc/reference/cmfcdesktopalertwnd-class.md). Определяет элементы управления, которые отображаются, если всплывает окно оповещения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Дескриптор, отображается значок.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Идентификатор команды, связанные со ссылкой на окно оповещения.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Текст, отображаемый в окне предупреждения рабочего стола.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Ссылки, которая отображается в окне предупреждения рабочего стола.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCDesktopAlertWndInfo` Передается класс [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) метод, чтобы задать элементы, отображаемые в диалоговом окне по умолчанию окно оповещения. Диалоговое окно по умолчанию может содержать три элемента:  
  
-   Значок, который устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Метку или текст сообщения, которое устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Связь, которая устанавливается посредством вызова [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Чтобы задать команду, которая выполняется при щелчке ссылки, вызовите [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Если диалоговое окно по умолчанию недостаточно, можно создать пользовательское диалоговое окно и передать его в [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) метода вместо использования этого класса. Дополнительные сведения см. в разделе [CMFCDesktopAlertDialog класса](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных элементов в `CMFCDesktopAlertWndInfo` класса. В примере показано значение дескриптора значка, отображаемого, текст, который отображается на окно оповещения, ссылки, которая отображается в окне предупреждения рабочего стола и идентификатор команды, связанный со ссылкой на окно оповещения. Этот пример является частью [рабочего стола обстановки-пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDesktopAlertDialog.h  
  
##  <a name="a-nameoperatoreqa--cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemhicona--cmfcdesktopalertwndinfomhicon"></a><a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon  
 Дескриптор, отображается значок.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemnurlcmdida--cmfcdesktopalertwndinfomnurlcmdid"></a><a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID  
 Идентификатор команды, связанные со ссылкой на окно оповещения.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Примечания  
 Идентификатор команды отправляется владельцу всплывающего окна при щелчке по ссылке, указанной в [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="a-namemstrtexta--cmfcdesktopalertwndinfomstrtext"></a><a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 Текст, отображаемый в окне предупреждения рабочего стола.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemstrurla--cmfcdesktopalertwndinfomstrurl"></a><a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 Ссылки, которая отображается в окне предупреждения рабочего стола.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает ссылку, команда, имеет [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) идентификатор команды будут отправляться владельца всплывающего окна.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

