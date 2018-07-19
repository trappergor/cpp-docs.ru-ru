---
title: Класс COleUpdateDialog | Документация Майкрософт
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
ms.openlocfilehash: fc5d51bfeb18b51be5a54c51046e3cd420fb1cb8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852111"
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
 Флаг, который определяет, является ли связанные объекты должны быть обновлены.  
  
 *bUpdateEmbeddings*  
 Флаг, который определяет, является ли внедренные объекты должны быть обновлены.  
  
 *pParentWnd*  
 Указывает на объект окна родительский объект или владельца (типа `CWnd`), которому принадлежит объект диалогового окна. Если это значение NULL, родительского окна окно будет присвоено главного окна приложения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает только `COleUpdateDialog` объекта. Чтобы отобразить диалоговое окно, вызовите [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Этот класс следует использовать вместо `COleLinksDialog` при необходимости обновления только существующих связанных или внедренных элементов.  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 Появляется диалоговое окно Изменение связей в режим обновления.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние завершения для диалогового окна. Одно из следующих значений:  
  
- IDOK, если диалоговое окно успешно возвращен.  
  
- IDCANCEL, если ни один из связанных или внедренных элементов в текущем документе необходимо обновить.  
  
- IDABORT, если произошла ошибка. Если возвращается IDABORT, вызовите [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) функция-член для получения дополнительных сведений о типе возникшей ошибки. Список возможных ошибок, см. в разделе [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) функции в пакете Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Все ссылки и (или) векторные представления обновляются, если пользователь выбирает кнопки "Отмена".  
  
## <a name="see-also"></a>См. также  
 [Пример MFC OCLIENT](../../visual-cpp-samples.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)
