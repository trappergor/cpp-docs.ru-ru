---
title: "Класс CMFCPropertyPage | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage::PreTranslateMessage method
- CMFCPropertyPage::CreateObject method
- CMFCPropertyPage class
- CMFCPropertyPage::OnSetActive method
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0e9cdfa8a98c034839fac119c828cf1b92a1867a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertypage-class"></a>Класс CMFCPropertyPage
`CMFCPropertyPage` Класс поддерживает отображение всплывающих меню на странице свойств.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Создает объект `CMFCPropertyPage`.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCPropertyPage::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyPage::OnSetActive`|Эта функция-член вызывается инфраструктурой при выбранной пользователем страницы и становится активной страницей. (Переопределяет [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Преобразует оконных сообщений перед их отправкой [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) функции Windows. Дополнительные сведения и синтаксиса см. в разделе [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Переопределяет `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Примечания  
 `CMFCPropertyPage` Класс представляет отдельные страницы вкладки свойств, также известные как диалоговое окно вкладки.  
  
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
  
##  <a name="cmfcpropertypage"></a>CMFCPropertyPage::CMFCPropertyPage  
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
 `nIDTemplate`  
 Идентификатор ресурса шаблона для этой страницы.  
  
 `nIDCaption`  
 Идентификатор ресурса метки для размещения на вкладке для этой страницы. Если значение равно 0, имя берется из шаблона поля диалогового окна для этой страницы. Значение по умолчанию — 0.  
  
 `lpszTemplateName`  
 Указывает имя шаблона для этой страницы. Не может быть `NULL`.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о параметрах конструктора см. в разделе [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

