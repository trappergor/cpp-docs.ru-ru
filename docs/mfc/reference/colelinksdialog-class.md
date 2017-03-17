---
title: "Класс COleLinksDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- Edit Links dialog box
- COleLinksDialog class
- dialog boxes, OLE
- OLE Edit Links dialog box
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
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
ms.openlocfilehash: ed256b3a4d3236863e3dcccb7614949f650f058b
ms.lasthandoff: 02/24/2017

---
# <a name="colelinksdialog-class"></a>Класс COleLinksDialog
Используется для диалогового окна OLE "Изменить ссылки".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Создает объект `COleLinksDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|Отображение диалогового окна OLE изменить ссылки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Структура типа **OLEUIEDITLINKS** , контролирует поведение диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleLinksDialog` когда необходимо вызвать это диалоговое окно предназначено. После `COleLinksDialog` объект был создан, можно использовать [m_el](#m_el) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_el` Структуры имеет тип **OLEUIEDITLINKS**. Дополнительные сведения об использовании этого класса диалогового окна в разделе [DoModal](#domodal) функции-члена.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="domodal"></a>COleLinksDialog::DoModal  
 Отображение диалогового окна OLE изменить ссылки.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил диалоговое окно.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные диалоговыми окнами, задав члены [m_el](#m_el) структуры, необходимо сделать это до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
##  <a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog  
 Создает объект `COleLinksDialog`.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указывает для документов OLE, со ссылками для редактирования.  
  
 `pView`  
 Указывает текущее представление на `pDoc`.  
  
 `dwFlags`  
 Создание флаг, который содержит либо 0 или **ELF_SHOWHELP** для указания, будет ли отображаться при откроется диалоговое окно "Справка".  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleLinksDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 Структура типа **OLEUIEDITLINKS** используется для управления поведением диалоговое окно Изменение связей.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно изменить члены этой структуры, либо непосредственно, либо с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)

