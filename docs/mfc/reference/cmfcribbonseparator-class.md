---
title: "Класс CMFCRibbonSeparator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonSeparator::GetThisClass
- CMFCRibbonSeparator.CreateObject
- CMFCRibbonSeparator::CreateObject
- CMFCRibbonSeparator
- CreateObject
- CMFCRibbonSeparator.GetThisClass
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator class
- GetThisClass method
- CreateObject method
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
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
ms.openlocfilehash: 98a58d43b5e6299f26521d873caec06d4581f7b3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonseparator-class"></a>Класс CMFCRibbonSeparator
Реализует разделителя ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Создает объект `CMFCRibbonSeparator`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Добавляет разделитель для **команды** список **Настройка** диалоговое окно. (Переопределяет [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonSeparator::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Метод копирования, который задает разделитель член переменных из другого объекта.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Возвращает размер разделителя.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Указывает, является ли разделитель.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Указывает, является ли знак табуляции.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Вызывается системой для рисования разделителя на ленте или в панель быстрого доступа.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Вызывается системой для рисования разделителя в **команды** списка.|  
  
## <a name="remarks"></a>Примечания  
 Разделитель ленты — вертикальной или горизонтальной линией, логически разделяет ленте элементов. Разделитель элементов могут быть нарисованы на элемент управления ленты, главное приложение меню, строки состояния ленты и панель быстрого доступа.  
  
 Необходимо использовать разделитель в приложении, создайте новый объект и добавьте его в меню основного приложения, как показано ниже:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Вызов [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) Добавление разделителей в панели ленты. Выделение и внутренним образом добавить разделители `AddSeparator` метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbaseribbonelement.h  
  
##  <a name="a-nameaddtolistboxa--cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox  
 Добавляет разделитель для **команды** список **Настройка** диалоговое окно.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndListBox`  
 Указатель на **команды** списка, куда добавляется разделитель.  
  
 [in] `bDeep`  
 Не обрабатывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс строки, в поле со списком, определяемое `pWndListBox`.  
  
##  <a name="a-namecmfcribbonseparatora--cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator  
 Создает объект `CMFCRibbonSeparator`.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsHoriz`  
 Если `TRUE`, разделитель является горизонтальной; Если `FALSE`, вертикального разделителя.  
  
### <a name="remarks"></a>Примечания  
 В меню приложения используются горизонтальные разделители. Вертикальные разделители используются в панели инструментов.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создания объекта `CMFCRibbonSeparator` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp&19;](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="a-namecopyfroma--cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom  
 Метод копирования, который задает разделитель член переменных из другого объекта.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Src`  
 Исходный элемент ленты для копирования из.  
  
##  <a name="a-namegetregularsizea--cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize  
 Возвращает размер разделителя.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на содержимое устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер разделителя в контексте данного устройства.  
  
##  <a name="a-nameisseparatora--cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator  
 Указывает, является ли разделитель.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE` к этому классу.  
  
##  <a name="a-nameistabstopa--cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop  
 Указывает, является ли знак табуляции.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE` к этому классу.  
  
### <a name="remarks"></a>Примечания  
 Разделитель ленты не табуляции.  
  
##  <a name="a-nameondrawa--cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCRibbonSeparator::OnDraw  
 Вызывается системой для рисования разделителя на ленте или в панель быстрого доступа.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
##  <a name="a-nameondrawonlista--cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList  
 Вызывается системой для рисования разделителя в **команды** списка.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|[in] `pDC`|Указатель на контекст устройства.|  
|[in] `strText`|Текст, отображаемый в списке.|  
|[in] `nTextOffset`|Расстояние между текстом и левого края ограничивающего прямоугольника.|  
|[in] `rect`|Указывает ограничивающий прямоугольник.|  
|[in] `bIsSelected`|Не обрабатывается.|  
|[in] `bHighlighted`|Не обрабатывается.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)

