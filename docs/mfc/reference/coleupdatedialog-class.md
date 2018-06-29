---
title: Класс COleUpdateDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0208a24b69c1884d72c0ae525ce95b3d3258271
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079978"
---
# <a name="coleupdatedialog-class"></a>Класс COleUpdateDialog
Используется в особых случаях в диалоговом окне OLE "Изменить ссылки", которое используется при необходимости обновления только существующих связанных или внедренных объектов в документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Создает объект `COleUpdateDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Отображает **изменить ссылки** диалоговое окно в режиме обновления.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о конкретных OLE диалоговым окнам см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
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
  
##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog  
 Создает объект `COleUpdateDialog`.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pDoc*  
 Указывает на документ, содержащий ссылки, может потребоваться обновление.  
  
 *bUpdateLinks*  
 Флаг, определяющий, является ли связанные объекты должны быть обновлены.  
  
 *bUpdateEmbeddings*  
 Флаг, определяющий, является ли внедренные объекты должны быть обновлены.  
  
 *pParentWnd*  
 Указывает на объект window родительского или владелец (типа `CWnd`), которому принадлежит объект диалогового окна. Если это **NULL**, родительское окно диалогового окна будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleUpdateDialog` объекта. Чтобы открыть диалоговое окно, вызовите [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс должен использоваться вместо `COleLinksDialog` при необходимости обновления только существующих связанных или внедренных элементов.  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 Появляется диалоговое окно Изменение связей в режим обновления.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- **IDOK** Если диалоговое окно успешно возвращен.  
  
- **IDCANCEL** Если ни один из элементов в текущем документе связанным или внедренным необходимо обновить.  
  
- **IDABORT** Если произошла ошибка. Если **IDABORT** будет возвращен, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функции-члена для получения дополнительных сведений о типе возникшей ошибки. Для получения списка возможных ошибок [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) функции в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Все ссылки и/или внедряемые объекты обновляются, если пользователь выбирает кнопку "Отмена".  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)
