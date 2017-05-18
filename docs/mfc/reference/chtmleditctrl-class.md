---
title: "Класс CHtmlEditCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl class
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4aca52508663e94ee9a1b55843ad05613aa40b0b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrl-class"></a>Класс CHtmlEditCtrl
Предоставляет функциональные возможности элемента управления ActiveX WebBrowser в окне MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Создает объект `CHtmlEditCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|Создает элемент управления WebBrowser ActiveX и присоединяет его к `CHtmlEditCtrl` объекта. Эта функция автоматически переводит элемент управления WebBrowser ActiveX в режиме редактирования.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Извлекает [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейс на документ, загруженных в элемента управления WebBrowser в контейнере.|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Получает URL-адрес документа по умолчанию для загрузки в элемента управления WebBrowser в контейнере.|  
  
## <a name="remarks"></a>Примечания  
 Размещенного элемента управления WebBrowser, элемент управления автоматически переводится в режим редактирования, после его создания.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxhtml.h  
  
##  <a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 Создает объект `CHtmlEditCtrl`.  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="create"></a>CHtmlEditCtrl::Create  
 Создает элемент управления WebBrowser ActiveX и присоединяет его к `CHtmlEditCtrl` объекта. Режим редактирования WebBrowser ActiveX, элемент управления автоматически переходит к документу по умолчанию и затем помещается в этой функцией.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszWindowName`  
 Этот параметр не используется.  
  
 `dwStyle`  
 Этот параметр не используется.  
  
 `rect`  
 Задает размер и положение элемента управления.  
  
 `pParentWnd`  
 Указывает элемент управления родительского окна. Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор элемента управления.  
  
 `pContext`  
 Этот параметр не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
##  <a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 Извлекает [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) интерфейс на документ, загруженных в содержащегося элемента управления WebBrowser  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `ppDocument`  
 Интерфейс документа.  
  
##  <a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 Получает URL-адрес документа по умолчанию для загрузки в элемента управления WebBrowser в контейнере.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)


