---
title: "Класс COleUpdateDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- Update dialog
- links [C++], updating
- updating OLE links
- OLE dialog boxes, Edit Link
- OLE link updating
- COleUpdateDialog class
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8066a8dc9e572c14e9423af62d340e249351ac11
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coleupdatedialog-class"></a>Класс COleUpdateDialog
Используется в особых случаях в диалоговом окне OLE "Изменить ссылки", которое используется при необходимости обновления только существующих связанных или внедренных объектов в документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Создает объект `COleUpdateDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Отображает **изменить ссылки** диалоговое окно в режиме обновления.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о диалоговых окнах OLE конкретных см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxodlgs.h  
  
##  <a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
 Создает объект `COleUpdateDialog`.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указывает для документа, содержащего ссылки, которое необходимо обновить.  
  
 *bUpdateLinks*  
 Флаг, определяющий, является ли связанные объекты должны быть обновлены.  
  
 *bUpdateEmbeddings*  
 Флаг, определяющий, является ли внедренные объекты должны быть обновлены.  
  
 `pParentWnd`  
 Указывает на объект окна родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleUpdateDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс следует использовать вместо `COleLinksDialog` возникает необходимость обновления только существующих связанных или внедренных элементов.  
  
##  <a name="domodal"></a>COleUpdateDialog::DoModal  
 Появляется диалоговое окно Изменение связей в режим обновления.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если диалоговое окно успешно возвращен.  
  
- **IDCANCEL** Если ни один из связанных или внедренных элементов в текущем документе необходимо обновить.  
  
- **IDABORT** произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок см. в разделе [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) работать в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Все ссылки и (или) внедрений обновляются, если пользователь выбирает кнопку "Отмена".  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

