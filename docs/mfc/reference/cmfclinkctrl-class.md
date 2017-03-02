---
title: "Класс CMFCLinkCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl class
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
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
ms.openlocfilehash: 8c926c0ef611470b137d2bb897c012a85645c90c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclinkctrl-class"></a>Класс CMFCLinkCtrl
`CMFCLinkCtrl` Класс отображает кнопку в виде гиперссылки и вызывает целевой объект связи при нажатии кнопки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Отображает указанный URL-адрес в виде текста кнопки.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Задает неявный протокол (например, «http:») URL-адреса.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Изменение размеров кнопки для хранения текста кнопки или точечный рисунок.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Вызывается средой перед рисованием прямоугольника фокуса кнопки.|  
  
## <a name="remarks"></a>Примечания  
 При нажатии кнопки, который является производным от `CMFCLinkCtrl` класс, платформа передает URL-адрес кнопки в качестве параметра `ShellExecute` метод. Затем `ShellExecute` метод открывает целевой URL-адрес.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как задать размер `CMFCLinkCtrl` объекта и как задать URL-адрес и всплывающей подсказки в `CMFCLinkCtrl` объекта. Этот пример является частью [пример создания новых элементов управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls №&9;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#10;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxlinkctrl.h  
  
##  <a name="a-nameondrawfocusrecta--cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 Вызывается средой перед рисованием прямоугольника фокуса кнопки.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Прямоугольник, ограничивающий элемент управления для связи.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если требуется использовать собственный код для отрисовки прямоугольника фокуса кнопки.  
  
##  <a name="a-nameseturla--cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl::SetURL  
 Отображает указанный URL-адрес в виде текста кнопки.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszURL`  
 Текст кнопки для отображения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameseturlprefixa--cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 Задает неявный протокол (например, «http:») URL-адреса.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPrefix`  
 Префикс URL-адреса протокола.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать префикс URL-адреса. Префикс не отображается на поверхности кнопки, но его можно использовать для справки перейдите к целевой URL-адрес.  
  
##  <a name="a-namesizetocontenta--cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 Изменение размеров кнопки для хранения текста кнопки или точечный рисунок.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bVCenter`  
 `TRUE`Чтобы центрировать текст и кнопки точечного рисунка по вертикали между верхней и нижней части элемента управления ссылки; в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] `bHCenter`  
 `TRUE`Чтобы центрировать текст и кнопки растрового изображения по горизонтали между левую и правую части элемента управления ссылки; в противном случае — `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий новый размер элемента управления ссылки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс классах-оболочках](../../mfc/reference/clinkctrl-class.md)   
 [Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)

