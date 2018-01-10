---
title: "Класс COleLinksDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs: C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9b998cc18ac0c357b57bc841f6db13700b078063
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colelinksdialog-class"></a>Класс COleLinksDialog
Используется для диалогового окна OLE "Изменить ссылки".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Создает объект `COleLinksDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|Отображение диалогового окна OLE изменение связей.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Структура типа **OLEUIEDITLINKS** , управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создание объекта класса `COleLinksDialog` при необходимости вызовите данным диалоговым окном. После `COleLinksDialog` объект был создан, можно использовать [m_el](#m_el) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_el` Структуры имеет тип **OLEUIEDITLINKS**. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функции-члена.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) структуры в Windows SDK.  
  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
 Отображение диалогового окна OLE изменение связей.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если успешно откроется диалоговое окно.  
  
- **IDCANCEL** Если пользователь отменил это диалоговое окно.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите `COleDialog::GetLastError` функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалоговых окон, задав члены [m_el](#m_el) структуры, необходимо сделать это перед вызовом `DoModal`, но после создания объекта диалогового окна.  
  
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
 Указывает документ OLE, который содержит ссылки, который нужно изменить.  
  
 `pView`  
 Указывает текущее представление на `pDoc`.  
  
 `dwFlags`  
 Создание флаг, который содержит либо 0 или **ELF_SHOWHELP** для указания, будет ли отображаться при откроется диалоговое окно "Справка".  
  
 `pParentWnd`  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского диалогового окна.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleLinksDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 Структура типа **OLEUIEDITLINKS** используется для управления поведением диалогового окна «Изменить ссылки».  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить напрямую или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) структуры в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
