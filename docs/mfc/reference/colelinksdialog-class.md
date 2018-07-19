---
title: Класс COleLinksDialog | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5dd17c0541b573cba40146c55b46d14143209c87
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853882"
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
|[COleLinksDialog::DoModal](#domodal)|Отображает диалоговое окно OLE изменить ссылки.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Структура типа OLEUIEDITLINKS, которое управляет поведением окна.|  
  
## <a name="remarks"></a>Примечания  
 Создайте объект класса `COleLinksDialog` при необходимости вызвать это диалоговое окно. После `COleLinksDialog` объект был создан, можно использовать [m_el](#m_el) структуры для инициализации значения или состояния элементов управления в диалоговом окне. `m_el` Структуры имеет тип OLEUIEDITLINKS. Дополнительные сведения об использовании этого класса диалогового окна см. в разделе [DoModal](#domodal) функция-член.  
  
> [!NOTE]
>  Контейнер, созданный мастером код приложения использует этот класс.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) структуры в пакете Windows SDK.  
  
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
  
##  <a name="domodal"></a>  COleLinksDialog::DoModal  
 Отображает диалоговое окно OLE изменить ссылки.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- IDOK, если было успешно отображено диалоговое окно.  
  
- IDCANCEL, если пользователь отменил диалоговое окно.  
  
- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите `COleDialog::GetLastError` функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) функции в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Если вы хотите инициализировать различных диалоговых путем определения участников [m_el](#m_el) структуры, необходимо сделать это перед вызовом `DoModal`, но после создания объекта диалогового окна.  
  
##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog  
 Создает объект `COleLinksDialog`.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pDoc*  
 Указывает на документ OLE, со ссылками для редактирования.  
  
 *pView*  
 Указывает на текущее представление на *pDoc*.  
  
 *dwFlags*  
 Создание флаг, который содержит 0 или ELF_SHOWHELP, чтобы указать, будет ли отображаться при откроется диалоговое окно кнопку "Справка".  
  
 *pParentWnd*  
 Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если он имеет значение NULL, родительского окна окно присваивается главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleLinksDialog` объекта. Чтобы отобразить диалоговое окно, вызовите [DoModal](#domodal) функции.  
  
##  <a name="m_el"></a>  COleLinksDialog::m_el  
 Структура типа OLEUIEDITLINKS используется для управления поведением диалогового окна "Изменить ссылки".  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Примечания  
 Члены этой структуры можно изменить напрямую или с помощью функций-членов.  
  
 Дополнительные сведения см. в разделе [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) структуры в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDialog](../../mfc/reference/coledialog-class.md)
