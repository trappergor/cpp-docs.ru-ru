---
title: "Класс CMFCMenuButton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton class
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 65c334ce68dbbbae2b21da2c40aa9420cdeb51bd
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubutton-class"></a>Класс CMFCMenuButton
Кнопку, которая отображает контекстное меню и сообщает, какие пункты выбирает в меню пользователь.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Создает объект `CMFCMenuButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Вызывается платформой для перевода оконных сообщений перед их отправкой. (Переопределяет `CMFCButton::PreTranslateMessage`.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Изменение размера кнопки в зависимости от размера текста и изображений.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Указывает, следует ли для отображения всплывающего меню системы по умолчанию или использовать [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Указывает, будет ли отображаться во всплывающем меню под или рядом с кнопкой.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Указывает, изменяется ли кнопки меню свое состояние после пользователь отпускает кнопку.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Дескриптор вложенного меню Windows.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Идентификатор, который указывает, какой элемент пользователь выбрал во всплывающем меню.|  
  
## <a name="remarks"></a>Примечания  
 `CMFCMenuButton` Класс является производным от [класса CMFCButton](../../mfc/reference/cmfcbutton-class.md) в свою очередь, производный от [CButton класса](../../mfc/reference/cbutton-class.md). Таким образом, можно использовать `CMFCMenuButton` в коде так же, как бы `CButton`.  
  
 При создании `CMFCMenuButton`, необходимо передать в дескрипторе связанные во всплывающем меню. Затем вызовите функцию `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`проверяет, что размер кнопки достаточно для включения стрелку, указывающую на расположение, в котором будет отображаться всплывающего окна — а именно, под или рядом с кнопкой.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует дескриптор меню, подключенное к кнопке, размер кнопки в зависимости от размера текста и изображений, и задать всплывающее меню, отображаемой платформой. Этот фрагмент кода является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#38;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#39;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 Создает новый [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) объекта.  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 Отображает платформу переменную-член типа Boolean, указывающее, какие во всплывающем меню.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_bOSMenu` — `TRUE`, платформа вызывает унаследованный `TrackPopupMenu` метод для данного объекта. В противном случае — платформа вызывает [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 Переменная член типа Boolean, указывающее расположение контекстного меню.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Примечания  
 Когда пользователь нажимает кнопку меню, приложение показывает всплывающее меню. Платформа будет отображаться во всплывающем меню рядом с кнопкой или справа от кнопки. Эта кнопка также имеет маленькую стрелку, которая указывает, где отображаются во всплывающем меню. Если `m_bRightArrow` — `TRUE`, платформа отображаются во всплывающем меню справа от кнопки. В противном случае — отображаются во всплывающем меню рядом с кнопкой.  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 Нажатии переменную-член типа Boolean, указывающее, отображается ли кнопка меню, когда пользователь делает выбор в раскрывающемся меню.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `m_bStayPressed` член является `FALSE`, кнопки меню не становятся нажата при использовании нажимает кнопку. В этом случае платформа отображается только во всплывающем меню.  
  
 Если `m_bStayPressed` член является `TRUE`, становится нажата кнопка меню, когда пользователь нажимает кнопку. Он остается нажатой до, после закрытия всплывающего меню, путем выбора или отмены пользователем.  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 Дескриптор вложенного меню.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Примечания  
 Платформа отображает меню обозначается переменную-член, когда пользователь нажимает кнопку меню.  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 Целое число, указывающее, какой элемент пользователь выбирает из контекстного меню.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой переменной-члена равно нулю, если пользователь отменяет меню без выбора или при возникновении ошибки.  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 Вызывается платформой для перевода оконных сообщений перед их отправкой.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pMsg`  
 Указывает [MSG](../../mfc/reference/msg-structure1.md) структура, содержащая сообщение для обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение был преобразован и не удалось отправить; 0, если сообщение не был преобразован и следует перенаправить.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 Изменение размера кнопки в соответствии с его размер шрифта и размера образа.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCalcOnly`  
 Логический параметр, указывающий, является ли этот метод изменяет размер кнопки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) объект, который указывает новый размер кнопки.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции и `bCalcOnly` — `TRUE`, `SizeToContent` рассчитает новый размер кнопки.  
  
 Новый размер кнопки вычисляется в соответствии с текст кнопки, изображения и стрелка. Платформа также добавляет в предопределенных полей 10 точек для горизонтального края и 5 точек для вертикального края.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)

