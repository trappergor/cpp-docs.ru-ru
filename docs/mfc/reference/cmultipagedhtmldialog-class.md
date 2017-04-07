---
title: "Класс CMultiPageDHtmlDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog class
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c00af20731b2c47a0074366722da3f4a0711ef85
ms.lasthandoff: 02/24/2017

---
# <a name="cmultipagedhtmldialog-class"></a>Класс CMultiPageDHtmlDialog
Многостраничное диалоговое окно последовательно отображает несколько HTML-страниц и обрабатывает события каждой страницы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Создает объект многостраничное диалоговое окно DHTML (мастера в стиле).|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Уничтожает объект многостраничное диалоговое окно DHTML.|  
  
## <a name="remarks"></a>Примечания  
 — Это механизм [схема событий DHTML и URL-адрес](http://msdn.microsoft.com/en-us/2a7332f0-79d7-46e4-b816-0a618c46777a), который содержит [встроенные схемы событий](http://msdn.microsoft.com/library/5346210f-f8b7-4e28-9d2c-d9d7fd42421d) для каждой страницы.  
  
## <a name="example"></a>Пример  
 Это многостраничное диалоговое окно предполагается три ресурсы HTML, определяющих функции простого типа мастера. На первой странице имеется `Next` кнопки, второй **Prev** и `Next` кнопки, а в третьем **Prev** кнопки. При нажатии одной из кнопок вызывает функцию обработчика событий [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) для загрузки соответствующего новой страницы.  
  
 Соответствующие части объявления класса (в CMyMultiPageDlg.h):  
  
 [!code-cpp[NVC_MFCDocView&#181;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Соответствующие части реализации класса (в CMyMultipageDlg.cpp):  
  
 [!code-cpp[NVC_MFCDocView&#182;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
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
  
##  <a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Создает объект многостраничное диалоговое окно DHTML (мастера в стиле).  
  
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
 Завершающим нулем строка, представляющая имя ресурс шаблона диалоговых окон.  
  
 `szHtmlResID`  
 Завершающим нулем строка, представляющая имя ресурса HTML.  
  
 `pParentWnd`  
 Указатель на объект окна родительского или владелец (типа [CWnd](../../mfc/reference/cwnd-class.md)), которому принадлежит объект диалогового окна. Если это **NULL**, главное окно приложения имеет значение родительского окна объекта диалогового окна.  
  
 `nIDTemplate`  
 Содержит идентификатор ресурс шаблона диалоговых окон.  
  
 `nHtmlResID`  
 Содержит идентификатор ресурса HTML.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Уничтожает объект многостраничное диалоговое окно DHTML.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>См. также  
 [Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

