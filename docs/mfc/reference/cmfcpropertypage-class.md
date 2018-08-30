---
title: Класс CMFCPropertyPage | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b552417af72b24cddae9055d436a56f771c48743
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203451"
---
# <a name="cmfcpropertypage-class"></a>Класс CMFCPropertyPage
`CMFCPropertyPage` Класс поддерживает отображение всплывающих меню на странице свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Создает объект `CMFCPropertyPage`.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyPage::OnSetActive`|Эта функция-член вызывается платформой при страницы, выбранный пользователем и становится активной страницей. (Переопределяет [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Преобразует сообщения окна перед их диспетчеризацией в [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Дополнительные сведения и синтаксис методов, см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Примечания  
 `CMFCPropertyPage` Класс представляет отдельные страницы вкладки свойств, также известный как диалоговое окно вкладки.  
  
 Используйте `CMFCPropertyPage` класса вместе с [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) класса. Чтобы использовать меню на странице свойств, замените все вхождения `CPropertyPage` класса `CMFCPropertyPage` класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertypage.h  
  
##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage  
 Создает объект `CMFCPropertyPage`.  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDTemplate*  
 Идентификатор ресурса шаблона для этой страницы.  
  
 *nIDCaption*  
 Идентификатор ресурса метки для размещения на вкладке этой страницы. Если значение равно 0, то имя получается из шаблон диалогового окна для этой страницы. Значение по умолчанию — 0.  
  
 *lpszTemplateName*  
 Указывает имя шаблона для этой страницы. Не может принимать значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах конструктора, см. в разделе [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)
