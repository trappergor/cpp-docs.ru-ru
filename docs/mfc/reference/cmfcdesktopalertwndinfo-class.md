---
title: "Класс CMFCDesktopAlertWndInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs: C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5771f092ec99020128e8d4ba5feba72e6ec0635c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcdesktopalertwndinfo-class"></a>Класс CMFCDesktopAlertWndInfo
`CMFCDesktopAlertWndInfo` Класс используется с [класс CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md). Определяет элементы управления, которые отображаются, если всплывает окно оповещения.  
  
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
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Дескриптор значка, который отображается.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|Идентификатор команды, связанные со ссылкой на окно оповещения.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Текст, отображаемый в окне предупреждения с рабочего стола.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Ссылки, которая отображается в окне предупреждения с рабочего стола.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCDesktopAlertWndInfo` Передается класс [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) метод для указания элементов, которые отображаются в окне по умолчанию окно оповещения. Диалоговое окно по умолчанию может содержать три элемента:  
  
-   Значок, который устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Метку или текст сообщения, которое устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Связь, которая устанавливается путем вызова [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Чтобы задать команду, которая выполняется при щелчке ссылки, вызовите [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Если диалоговое окно по умолчанию недостаточно, можно создать настраиваемое диалоговое окно и передать его в [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) вместо использования этого класса. Дополнительные сведения см. в разделе [CMFCDesktopAlertDialog класса](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных элементов в `CMFCDesktopAlertWndInfo` класса. В примере показано значение дескриптор значка, отображаемого, текст, отображаемый на окно оповещения, ссылки, которая отображается в окне предупреждения с рабочего стола и идентификатор команды, связанный со ссылкой на окно оповещения. Данный пример является частью [Desktop предупреждения демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `src`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon  
 Дескриптор значка, который отображается.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID  
 Идентификатор команды, связанные со ссылкой на окно оповещения.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Примечания  
 Идентификатор команды отправляется владелец во всплывающем окне, когда пользователь щелкает ссылку, заданные [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 Текст, отображаемый в окне предупреждения с рабочего стола.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 Ссылки, которая отображается в окне предупреждения с рабочего стола.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь щелкает ссылку, команда, имеет [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) идентификатор команды, которые будут отправляться на владельца всплывающего окна.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [Класс CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)
