---
title: Класс CMFCLinkCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc83e5abf09102af8f27b1ee73fc78ed162b9335
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfclinkctrl-class"></a>Класс CMFCLinkCtrl
`CMFCLinkCtrl` Класс отображает кнопку в виде гиперссылки и вызывает целевой объект связи при нажатии кнопки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Отображает указанный URL-адрес в виде текста кнопки.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Задает протокол, неявное (например, «http:») URL-адреса.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Изменение размеров кнопки для хранения текста кнопки или точечного рисунка.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Вызывается платформой перед рисованием прямоугольника фокуса кнопки.|  
  
## <a name="remarks"></a>Примечания  
 При нажатии кнопки, который является производным от `CMFCLinkCtrl` класса, платформа передает URL-адрес кнопки в качестве параметра для `ShellExecute` метод. Затем `ShellExecute` метод открывает целевой URL-адрес.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как задать размер `CMFCLinkCtrl` объекта и как задать URL-адрес и всплывающей подсказки в `CMFCLinkCtrl` объекта. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 Вызывается платформой перед рисованием прямоугольника фокуса кнопки.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectClient`  
 Прямоугольник, ограничивающий управления ссылками.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод, если вы хотите использовать собственный код для отрисовки прямоугольника фокуса кнопки.  
  
##  <a name="seturl"></a>CMFCLinkCtrl::SetURL  
 Отображает указанный URL-адрес в виде текста кнопки.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszURL`  
 Текст кнопки для отображения.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 Задает протокол, неявное (например, «http:») URL-адреса.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPrefix`  
 Префикс URL-протокол.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать префикс URL-адреса. Префикс не отображается на поверхности кнопок, но его можно использовать для перейдите к целевой URL-адрес.  
  
##  <a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 Изменение размеров кнопки для хранения текста кнопки или точечного рисунка.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bVCenter`  
 `TRUE`Чтобы центрировать текст и кнопки растрового изображения по вертикали между верхней и нижней части элемента управления ссылки; в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
 [in] `bHCenter`  
 `TRUE`Чтобы центрировать текст и кнопки растрового изображения по горизонтали между левой и правой стороны элемента управления ссылки; в противном случае `FALSE`. Значение по умолчанию — `FALSE`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) , содержащий новый размер элемента управления ссылки.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс классах-оболочках](../../mfc/reference/clinkctrl-class.md)   
 [Класс CMFCButton](../../mfc/reference/cmfcbutton-class.md)
