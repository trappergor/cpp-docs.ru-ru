---
title: Класс CMultiPageDHtmlDialog | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be83e3791121bdea4d7f650f7d6801517df31ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmultipagedhtmldialog-class"></a>Класс CMultiPageDHtmlDialog
Многостраничное диалоговое окно последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Создает объект многостраничное диалоговое окно DHTML (мастер стиль).|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Уничтожает объект многостраничное диалоговое окно DHTML.|  
  
## <a name="remarks"></a>Примечания  
 Лучше всего для этого [схема событий DHTML и URL-адрес](dhtml-event-maps.md), который содержит встроенные схемы событий для каждой страницы.  
  
## <a name="example"></a>Пример  
 Это многостраничное диалоговое окно предполагается три ресурса HTML, определяющих функции простого типа мастера. На первой странице `Next` кнопки, второй **Prev** и `Next` кнопки, а третья **Prev** кнопки. При нажатии одной из кнопок вызывает функцию обработчика событий [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) загрузить соответствующий новой страницы.  
  
 Соответствующие части объявления класса (в CMyMultiPageDlg.h):  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Соответствующие части реализации класса (в CMyMultipageDlg.cpp):  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Создает объект многостраничное диалоговое окно DHTML (мастер стиль).  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTemplateName`  
 Нулем строка, представляющая имя ресурса шаблона диалогового окна.  
  
 `szHtmlResID`  
 Нулем строка, представляющая имя ресурса HTML.  
  
 `pParentWnd`  
 Указатель на объект window родительского или владелец (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурса шаблона диалогового окна.  
  
 `nHtmlResID`  
 Содержит идентификатор ресурса HTML.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Уничтожает объект многостраничное диалоговое окно DHTML.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
